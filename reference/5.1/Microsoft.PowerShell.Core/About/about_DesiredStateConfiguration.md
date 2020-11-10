---
description: Краткое введение в функцию настройки требуемого состояния PowerShell (DSC).
keywords: powershell,командлет
Locale: en-US
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_desiredstateconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_DesiredStateConfiguration
ms.openlocfilehash: 5d088934ffc953ad19be401bce72f6287f0fde07
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94387028"
---
# <a name="about_desiredstateconfiguration"></a>about_DesiredStateConfiguration

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ

Краткое введение в функцию настройки требуемого состояния PowerShell (DSC).

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

DSC — это платформа управления в PowerShell, которая позволяет развертывать данные конфигурации для служб программного обеспечения и управлять ими, а также управлять средой, в которой выполняются эти службы.

DSC предоставляет набор расширений языка PowerShell, новых командлетов и ресурсов, которые можно использовать для декларативного указания того, как должно быть настроено состояние программной среды. Кроме того, с ее помощью можно поддерживать действующие конфигурации и управлять ими.

DSC представлен в PowerShell 4,0.

Подробные сведения о DSC см. в статье [Общие сведения о настройке требуемого состояния PowerShell](/powershell/scripting/dsc/overview/overview).

## <a name="developing-dsc-resources-with-classes"></a>РАЗРАБОТКА РЕСУРСОВ DSC С ПОМОЩЬЮ КЛАССОВ

Начиная с PowerShell 5,0 можно разрабатывать ресурсы DSC с помощью классов.
Дополнительные сведения см. в статьях [about_Classes](about_Classes.md)и [запись пользовательского ресурса DSC с помощью классов PowerShell](/powershell/scripting/dsc/resources/authoringresourceclass).

## <a name="using-dsc"></a>ИСПОЛЬЗОВАНИЕ DSC

Чтобы использовать DSC для настройки среды, сначала определите блок сценария PowerShell с помощью ключевого слова Configuration, за которым следует идентификатор, который, в свою очередь, за которым следует пара фигурных скобок, разделяющих блок. Внутри блока конфигурации можно определить блоки узлов, указывающие состояние требуемой конфигурации для каждого узла (компьютера) в среде. Блок узла начинается с ключевого слова Node, за которым следует имя целевого компьютера, который может быть переменной. После имени компьютера поступит фигурные скобки, разделяющие блок узла. Внутри блока Node можно определить блоки ресурсов для настройки определенных ресурсов. Блок ресурсов начинается с имени типа ресурса, за которым следует идентификатор, который необходимо указать для этого блока, за которым следуют фигурные скобки, разделяющие блок, как показано в следующем примере.

```powershell
Configuration MyWebConfig {
    # Parameters are optional
    param ($MachineName, $WebsiteFilePath)
    # A Configuration block can have one or more Node blocks
    Node $MachineName
    {
        # Next, specify one or more resource blocks
        # WindowsFeature is one of the resources you can use in a Node block
        # This example ensures the Web Server (IIS) role is installed
        WindowsFeature IIS
        {
            # To ensure that the role is not installed, set Ensure to "Absent"
            Ensure = "Present"
            Name = "Web-Server" # Use the Name property from Get-WindowsFeature
        }

        # You can use the File resource to create files and folders
        # "WebDirectory" is the name you want to use to refer to this instance
        File WebDirectory
        {
            Ensure = "Present"  # You can also set Ensure to "Absent"
            Type = "Directory" # Default is "File"
            Recurse = $true
            SourcePath = $WebsiteFilePath
            DestinationPath = "C:\inetpub\wwwroot"

            # Ensure that the IIS block is successfully run first before
            # configuring this resource
            DependsOn = "[WindowsFeature]IIS"  # Use for dependencies
        }
    }
}
```

Чтобы создать конфигурацию, вызовите блок конфигурации так же, как при вызове функции PowerShell, передав все ожидаемые параметры (два в примере выше). Например, в этом случае:

```powershell
MyWebConfig -MachineName "TestMachine" -WebsiteFilePath `
  "\\filesrv\WebFiles" -OutputPath "C:\Windows\system32\temp"
# OutputPath is optional
```

При этом создается MOF-файл для каждого узла по указанному пути. Эти MOF-файлы указывают требуемую конфигурацию для каждого узла. Затем используйте следующий командлет для анализа MOF-файлов конфигурации, отправки каждого узла соответствующей конфигурации и внедрения этих конфигураций. Обратите внимание, что вам не нужно создавать отдельный MOF-файл для ресурсов DSC на основе классов.

```powershell
Start-DscConfiguration -Verbose -Wait -Path "C:\Windows\system32\temp"
```

## <a name="using-dsc-to-maintain-configuration-state"></a>ИСПОЛЬЗОВАНИЕ DSC ДЛЯ ОБСЛУЖИВАНИЯ СОСТОЯНИЯ КОНФИГУРАЦИИ

В DSC конфигурация — идемпотентными. Это означает, что при использовании DSC для одной и той же конфигурации несколько раз результирующее состояние конфигурации всегда будет одинаковым. По этой причине, если вы подозреваете, что все узлы в вашей среде были смещены от желаемого состояния конфигурации, можно снова применить ту же конфигурацию DSC еще раз, чтобы вернуть их в нужное состояние. Нет необходимости изменять скрипт конфигурации для адресации только тех ресурсов, состояние которых смещено от требуемого состояния.

В следующем примере показано, как проверить фактическое состояние конфигурации на данном узле, смещенное от последней конфигурации DSC, заданной на узле. В этом примере проверяется конфигурация локального компьютера.

```powershell
$session = New-CimSession -ComputerName "localhost"
Test-DscConfiguration -CimSession $session
```

## <a name="built-in-dsc-resources"></a>ВСТРОЕННЫЕ РЕСУРСЫ DSC

В скриптах конфигурации можно использовать следующие встроенные ресурсы:

|Имя                  |Свойства                                         |
|----------------------|---------------------------------------------------|
|Файл                  |{DestinationPath, атрибуты, контрольная сумма, содержимое...}|
|Архив               |{Назначение, путь, контрольная сумма, учетные данные...}       |
|Среда           |{Name, DependsOn, убедитесь, что путь...}                 |
|Группа                 |{GroupName, Credential, DependsOn, описание...} |
|Журнал                   |{Message, DependsOn, PsDscRunAsCredential}         |
|Пакет               |{Name, Path, ProductId, arguments...}              |
|Реестр              |{Key, ValueName, DependsOn, убедитесь, что...}             |
|Скрипт                |{Надстрочный, SetScript, TestScript, Credential...}  |
|Служба               |{Name, Буилтинаккаунт, Credentials, DEPENDENCIES...}|
|Пользователь                  |{UserName, DependsOn, описание, отключено...}    |
|WaitForAll            |{NodeName, ResourceName, DependsOn, Псдскрунаск...}|
|WaitForAny            |{NodeName, ResourceName, DependsOn, Псдскрунаск...}|
|WaitForSome           |{NodeCount, NodeName, ResourceName, DependsOn...}  |
|WindowsFeature        |{Name, Credential, DependsOn, убедитесь, что...}           |
|WindowsOptionalFeature|{Name, DependsOn, обязательно, LogLevel...}             |
|WindowsProcess        |{Аргументы, путь, учетные данные, DependsOn...}        |

Чтобы получить список доступных ресурсов DSC в системе, выполните `Get-DscResource` командлет.

> [!NOTE]
> В версиях PowerShell до 7.0 `Get-DscResource` не находит ресурсы DSC на основе класса.

В примере в этом разделе показано, как использовать ресурсы File и WindowsFeature. Чтобы просмотреть все свойства, которые можно использовать с ресурсом, Вставьте курсор в ключевое слово ресурса (например, файл) в скрипте конфигурации в интегрированной среде сценариев PowerShell, удерживая нажатой <kbd>клавишу CTRL</kbd> + <kbd>пробел</kbd> .

## <a name="find-more-resources"></a>НАЙТИ ДОПОЛНИТЕЛЬНЫЕ РЕСУРСЫ

Вы можете скачать, установить и узнать о многих других доступных ресурсах DSC, созданных с помощью PowerShell и сообщества пользователей DSC, а также корпорацией Майкрософт. Посетите [коллекция PowerShell](https://www.powershellgallery.com/) , чтобы просмотреть и узнать о доступных ресурсах DSC.

## <a name="see-also"></a>СМ. ТАКЖЕ

[Общие сведения о настройке требуемого состояния PowerShell](/powershell/scripting/dsc/overview/overview)

[Встроенные ресурсы настройки требуемого состояния PowerShell](/powershell/scripting/dsc/resources/resources)

[Создание пользовательских ресурсов настройки требуемого состояния PowerShell](/powershell/scripting/dsc/resources/authoringResource)
