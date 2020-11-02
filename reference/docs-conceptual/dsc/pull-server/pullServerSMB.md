---
ms.date: 04/11/2018
keywords: dsc,powershell,конфигурация,установка
title: Настройка опрашивающего SMB-сервера DSC
description: Опрашивающий SMB-сервер DSC — это, компьютер, размещающий файловый ресурс SMB, который делает конфигурации DSC или ресурсы DSC доступными для целевых узлов, когда эти узлы запрашивают их.
ms.openlocfilehash: 4ac1b0db719fa124d6fa9a654acb64ec24d9ea41
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92658427"
---
# <a name="setting-up-a-dsc-smb-pull-server"></a>Настройка опрашивающего SMB-сервера DSC

Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0

> [!IMPORTANT]
> Опрашивающий сервер (компонент Windows *служба DSC* ) — поддерживаемый компонент Windows Server, но реализация новых функций и возможностей для него не планируется. Рекомендуется начать перенос управляемых клиентов на [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (включает возможности опрашивающего сервера в Windows Server) или на одно из решений сообщества, указанных [в следующем списке](pullserver.md#community-solutions-for-pull-service).

Опрашивающий [SMB-сервер](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831795(v=ws.11)) DSC — это, компьютер, размещающий файловый ресурс SMB, который делает конфигурации DSC или ресурсы DSC доступными для целевых узлов, когда эти узлы запрашивают их.

Для использования опрашивающего SMB-сервера DSC необходимо выполнить следующее:

- Настроить файловый SMB-ресурс на сервере, с PowerShell 4.0 или более поздней версии.
- Настроить клиент с PowerShell 4.0 или более поздней версии для получения данных с этого файлового SMB-ресурса.

## <a name="using-the-xsmbshare-resource-to-create-an-smb-file-share"></a>Использование ресурса xSmbShare для создания файлового SMB-ресурса

Существует несколько способов настройки файлового SMB-ресурса. Давайте рассмотрим, как это можно сделать с помощью DSC.

### <a name="install-the-xsmbshare-resource"></a>Установка ресурса xSmbShare

Для установки модуля **xSmbShare** используйте командлет [Install-Module](/powershell/module/PowershellGet/Install-Module).

> [!NOTE]
> `Install-Module` включен в модуль **PowerShellGet** , содержащийся в PowerShell 5.0.
> **xSmbShare** содержит ресурс DSC **xSmbShare** , с помощью которого можно создать файловый ресурс SMB.

### <a name="create-the-directory-and-file-share"></a>Создание файлового ресурса и каталога

В следующей конфигурации ресурс **File** используется для создания каталога для ресурса, а ресурс **xSmbShare**  — для настройки ресурса SMB:

```powershell
Configuration SmbShare
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Import-DscResource -ModuleName xSmbShare

    Node localhost
    {

        File CreateFolder
        {
            DestinationPath = 'C:\DscSmbShare'
            Type = 'Directory'
            Ensure = 'Present'
        }

        xSMBShare CreateShare
        {
            Name = 'DscSmbShare'
            Path = 'C:\DscSmbShare'
            FullAccess = 'administrator'
            ReadAccess = 'myDomain\Contoso-Server$'
            FolderEnumerationMode = 'AccessBased'
            Ensure = 'Present'
            DependsOn = '[File]CreateFolder'
        }
    }
}
```

Конфигурация создает каталог `C:\DscSmbShare`, если его еще не существует, и затем использует этот каталог в качестве общего ресурса SMB. Разрешение **FullAccess** должно предоставляться любой учетной записи, которой необходимо записывать или удалять данные на общем ресурсе. Разрешение **ReadAccess** необходимо предоставить всем узлам клиента, которые получают конфигурации и ресурсы DSC из общего ресурса.

> [!NOTE]
> DSC по умолчанию выполняется с системной учетной записью, поэтому у самого компьютера должен быть доступ к общему ресурсу.

### <a name="give-file-system-access-to-the-pull-client"></a>Предоставление файловой системе доступа к опрашивающему клиенту

Предоставление разрешения **ReadAccess** клиенту узла позволяет этому узлу обращаться к SMB-ресурсу, но не к файлам или папкам в этом ресурсе. Следует явно предоставить узлам клиента доступ к папке и вложенным папкам общего ресурса SMB. Сделать это можно с помощью DSC, используя ресурс **cNtfsPermissionEntry** , который содержится в модуле [CNtfsAccessControl](https://www.powershellgallery.com/packages/cNtfsAccessControl/1.2.0).
Следующая конфигурация добавляет блок **cNtfsPermissionEntry** , который предоставляет разрешение ReadAndExecute опрашивающему клиенту:

```powershell
Configuration DSCSMB
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Import-DscResource -ModuleName xSmbShare
    Import-DscResource -ModuleName cNtfsAccessControl

    Node localhost
    {

        File CreateFolder
        {
            DestinationPath = 'C:\DscSmbShare'
            Type = 'Directory'
            Ensure = 'Present'
        }

        xSMBShare CreateShare
        {
            Name = 'DscSmbShare'
            Path = 'C:\DscSmbShare'
            FullAccess = 'administrator'
            ReadAccess = 'myDomain\Contoso-Server$'
            FolderEnumerationMode = 'AccessBased'
            Ensure = 'Present'
            DependsOn = '[File]CreateFolder'
        }

        cNtfsPermissionEntry PermissionSet1
        {
            Ensure = 'Present'
            Path = 'C:\DscSmbShare'
            Principal = 'myDomain\Contoso-Server$'
            AccessControlInformation = @(
                cNtfsAccessControlInformation
                {
                    AccessControlType = 'Allow'
                    FileSystemRights = 'ReadAndExecute'
                    Inheritance = 'ThisFolderSubfoldersAndFiles'
                    NoPropagateInherit = $false
                }
            )
            DependsOn = '[File]CreateFolder'
        }
    }
}
```

## <a name="placing-configurations-and-resources"></a>Размещение конфигураций и ресурсов

Сохраните все MOF-файлы конфигурации и ресурсы DSC, к которым должны обращаться клиентские узлы, в общей папке SMB.

Все MOF-файлы конфигурации должны иметь имена вида *ConfigurationID* .mof, где *ConfigurationID*  — значение свойства **ConfigurationID** LCM целевого узла. Дополнительные сведения о настройке опрашивающих клиентов см. в разделе [Настройка опрашивающего клиента с помощью идентификатора конфигурации](pullClientConfigID.md).

> [!NOTE]
> При использовании опрашивающего SMB-сервера необходимо использовать идентификаторы конфигурации. Имена конфигураций не поддерживаются SMB.

Каждый модуль ресурса необходимо упаковать в ZIP-архив и переименовать согласно следующему шаблону: `{Module Name}_{Module Version}.zip`. Например, модуль с именем xWebAdminstration с версией модуля 3.1.2.0 будет иметь имя "xWebAdministration_3.2.1.0.zip". Каждая версия модуля должна находиться в собственном ZIP-файле. Отдельные версии модуля в ZIP-файле не поддерживаются.
Перед упаковкой модулей ресурсов DSC для опрашиваемого сервера необходимо внести небольшое изменение в структуру каталогов.

Формат модулей, содержащих ресурсы DSC, в WMF 5.0 по умолчанию таков: `{Module Folder}\{Module Version}\DscResources\{DSC Resource Folder}\`.

Перед упаковкой для опрашиваемого сервера просто удалите папку `{Module version}`, чтобы путь стал таким: `{Module Folder}\DscResources\{DSC Resource Folder}\`. Выполнив это изменение, упакуйте папку в ZIP-архив, как описано выше, и поместите ZIP-архивы в папку общего ресурса SMB.

## <a name="creating-the-mof-checksum"></a>Создание контрольной суммы MOF

MOF-файл конфигурации необходимо сопоставить с файлом контрольной суммы, чтобы LCM на целевом узле мог проверить конфигурацию. Для вычисления контрольной суммы вызовите командлет [New-DSCCheckSum](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum). Командлет принимает параметр `Path`, указывающий папку, в которой располагается MOF-файл конфигурации. Командлет создает файл контрольной суммы `ConfigurationMOFName.mof.checksum`, где `ConfigurationMOFName` — имя MOF-файла конфигурации. Если в указанной папке есть несколько MOF-файлов конфигурации, контрольная сумма создается для каждой конфигурации в папке.

Файл контрольной суммы должен находиться в том же каталоге, что и MOF-файл конфигурации (`$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration` по умолчанию), и иметь то же имя, что и у добавленного расширения `.checksum`.

> [!NOTE]
> Если вы измените MOF-файл конфигурации каким-либо образом, потребуется повторно создать файл контрольной суммы.

## <a name="setting-up-a-pull-client-for-smb"></a>Настройка опрашивающего клиента для SMB

Чтобы определить клиент, запрашивающий конфигурации и (или) ресурсы из общей папки SMB, настройте для локального диспетчера конфигураций (LCM) клиента блоки **ConfigurationRepositoryShare** и **ResourceRepositoryShare** , указывающие общую папку для извлечения данных.

Дополнительные сведения о настройке LCM см. в разделе [Настройка опрашивающего клиента с помощью идентификатора конфигурации](pullClientConfigID.md).

> [!NOTE]
> Для простоты в этом примере используется **PSDscAllowPlainTextPassword** , чтобы разрешить передачу пароля в формате открытого текста в параметр **Credential** . Сведения о более безопасной передачи учетных данных см. в разделе [Параметры учетных данных в данных конфигурации](../configurations/configDataCredentials.md). **Следует** указать **ConfigurationID** в блоке **Settings** метаконфигурации опрашивающего сервера SMB, даже если вы просто извлекаете ресурсы.

```powershell
$secpasswd = ConvertTo-SecureString "Pass1Word" -AsPlainText -Force
$mycreds = New-Object System.Management.Automation.PSCredential ("TestUser", $secpasswd)

[DSCLocalConfigurationManager()]
configuration SmbCredTest
{
    Node $AllNodes.NodeName
    {
        Settings
        {
            RefreshMode = 'Pull'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
            ConfigurationID    = '16db7357-9083-4806-a80c-ebbaf4acd6c1'
        }

         ConfigurationRepositoryShare SmbConfigShare
        {
            SourcePath = '\\WIN-E0TRU6U11B1\DscSmbShare'
            Credential = $mycreds
        }

        ResourceRepositoryShare SmbResourceShare
        {
            SourcePath = '\\WIN-E0TRU6U11B1\DscSmbShare'
            Credential = $mycreds

        }
    }
}

$ConfigurationData = @{
    AllNodes = @(
        @{
            #the "*" means "all nodes named in ConfigData" so we don't have to repeat ourselves
            NodeName="localhost"
            PSDscAllowPlainTextPassword = $true
        })
}
```

## <a name="acknowledgements"></a>Благодарности

Выражаю особую благодарность:

- Майку Ф. Роббинсу, чьи записи об использовании SMB для DSC помогли в составлении этой статьи. Ссылка на его блог — [Майк Ф. Роббинс](http://mikefrobbins.com/).
- Сергею Николайчуку, который создал модуль **cNtfsAccessControl** . Исходный код этого модуля доступен по ссылке [cNtfsAccessControl](https://github.com/SNikalaichyk/cNtfsAccessControl).

## <a name="see-also"></a>См. также раздел

[Обзор Windows PowerShell Desired State Configuration](../overview/overview.md)

[Применение конфигураций](enactingConfigurations.md)

[Настройка опрашивающего клиента с помощью идентификатора конфигурации](pullClientConfigID.md)
