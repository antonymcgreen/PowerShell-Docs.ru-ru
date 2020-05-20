---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Параметры учетных данных в данных конфигурации
ms.openlocfilehash: aac27f1ff4b4287b53745fa3b946fb3de84771c2
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "75870563"
---
# <a name="credentials-options-in-configuration-data"></a>Параметры учетных данных в данных конфигурации

> Область применения: Windows PowerShell 5.0

## <a name="plain-text-passwords-and-domain-users"></a>Пароли в виде простого текста и пользователи домена

При использовании конфигураций DSC, содержащих незашифрованные учетные данные, выдается сообщение об ошибке из-за указания паролей в виде простого текста. Кроме того, DSC выдает предупреждение при использовании учетных данных домена. Чтобы не получать такие ошибки и предупреждения, используйте следующие ключевые слова в данных конфигурации DSC.

- **PsDscAllowPlainTextPassword**
- **PsDscAllowDomainUser**

> [!NOTE]
> Хранение и передача незашифрованных паролей с простым текстом обычно являются небезопасными. Рекомендуется использовать методы защиты учетных данных, описанные далее в этом разделе. Служба Azure Automation DSC позволяет вам централизованно управлять учетными данными, включать их в конфигурации и обеспечивать безопасное хранение. Дополнительные сведения: [Компиляция конфигураций DSC/ресурсы-контейнеры учетных данных](/azure/automation/automation-dsc-compile#credential-assets)

## <a name="handling-credentials-in-dsc"></a>Обработка учетных данных в DSC

По умолчанию ресурсы DSC запускаются от имени `Local System`. При этом некоторые ресурсы требуют учетных данных, например, если ресурсу `Package` необходимо установить программное обеспечение с помощью учетной записи определенного пользователя.

В более ранних ресурсах для этого использовалось прописываемое в коде свойство `Credential`. В WMF 5.0 для всех ресурсов было добавлено автоматическое свойство `PsDscRunAsCredential`. Дополнительные сведения об использовании `PsDscRunAsCredential` см. в разделе [Запуск DSC с учетными данными пользователя](runAsUser.md). Новые и настраиваемые ресурсы позволяют использовать это автоматическое свойство вместо создания отдельного свойства для учетных данных.

> [!NOTE]
> Некоторые виды ресурсов используют множество учетных данных для определенной цели. Такие ресурсы имеют собственные свойства учетных данных.

Чтобы найти доступные свойства учетных данных ресурса, используйте `Get-DscResource -Name ResourceName -Syntax` или Intellisense в интегрированной среде сценариев (`CTRL+SPACE`).

```powershell
Get-DscResource -Name Group -Syntax
```

```Output
Group [String] #ResourceName
{
    GroupName = [string]
    [Credential = [PSCredential]]
    [DependsOn = [string[]]]
    [Description = [string]]
    [Ensure = [string]{ Absent | Present }]
    [Members = [string[]]]
    [MembersToExclude = [string[]]]
    [MembersToInclude = [string[]]]
    [PsDscRunAsCredential = [PSCredential]]
}
```

В этом примере используется ресурс [Group](../resources/resources.md) из встроенного модуля ресурсов DSC `PSDesiredStateConfiguration`. Он может создавать локальные группы, а также добавлять и удалять члены. Этот ресурс принимает как свойство `Credential`, так и автоматическое свойство `PsDscRunAsCredential`, но использует только свойство `Credential`.

См. дополнительные сведения о свойстве `PsDscRunAsCredential` и [запуске DSC с учетными данными пользователя](runAsUser.md).

## <a name="example-the-group-resource-credential-property"></a>Пример: свойство учетных данных для ресурса Group

DSC выполняется в качестве `Local System`, поэтому уже имеет разрешения на изменение локальных пользователей и групп. Если в локальную учетную группу добавляется новый пользователь, учетные данные не требуются. Но если ресурс `Group` добавляет учетную запись домена в локальную группу, учетные данные необходимы.

Анонимные запросы к Active Directory не допускаются. Свойство `Credential` ресурса `Group` — это учетная запись домена, которая используется для запросов к Active Directory. В большинстве случаев это может быть универсальная учетная запись пользователя, поскольку пользователи по умолчанию могут *читать* большинство объектов в Active Directory.

## <a name="example-configuration"></a>Пример конфигурации

В следующем примере кода DSC используется для добавления пользователя домена в локальную группу:

```powershell
Configuration DomainCredentialExample
{
    param
    (
        [PSCredential] $DomainCredential
    )
    Import-DscResource -ModuleName PSDesiredStateConfiguration

    node localhost
    {
        Group DomainUserToLocalGroup
        {
            GroupName        = 'ApplicationAdmins'
            MembersToInclude = 'contoso\alice'
            Credential       = $DomainCredential
        }
    }
}

$cred = Get-Credential -UserName contoso\genericuser -Message "Password please"
DomainCredentialExample -DomainCredential $cred
```

Этот код вызывает ошибку и предупреждение:

```
ConvertTo-MOFInstance : System.InvalidOperationException error processing property 'Credential' OF
TYPE 'Group': Converting and storing encrypted passwords as plain text is not recommended.
For more information on securing credentials in MOF file, please refer to MSDN blog:
https://go.microsoft.com/fwlink/?LinkId=393729

At line:11 char:9
+   Group
At line:341 char:16
+     $aliasId = ConvertTo-MOFInstance $keywordName $canonicalizedValue
+                ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [Write-Error], InvalidOperationException
    + FullyQualifiedErrorId : FailToProcessProperty,ConvertTo-MOFInstance
WARNING: It is not recommended to use domain credential for node 'localhost'. In order to suppress
the warning, you can add a property named 'PSDscAllowDomainUser' with a value of $true to your DSC
configuration data for node 'localhost'.

Compilation errors occurred while processing configuration
'DomainCredentialExample'. Please review the errors reported in error stream and modify your
configuration code appropriately.
At C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules\PSDesiredStateConfiguration\PSDesiredStateConfiguration.psm1:3917 char:5
+     throw $ErrorRecord
+     ~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (DomainCredentialExample:String) [], InvalidOperationException
    + FullyQualifiedErrorId : FailToProcessConfiguration
```

В этом примере есть две проблемы:

1. Ошибка с указанием на то, что использовать пароли в виде простого текста не рекомендуется.
2. Предупреждение с рекомендацией не использовать доменные учетные данные.

Флаги **PSDSCAllowPlainTextPassword** и **PSDSCAllowDomainUser** подавляют ошибку и предупреждают пользователя о риске.

## <a name="psdscallowplaintextpassword"></a>PSDSCAllowPlainTextPassword

В первом сообщении об ошибке находится URL-адрес документации. Он содержит инструкции по шифрованию паролей с использованием структуры [ConfigurationData](./configData.md) и сертификата. Дополнительные сведения о сертификатах в DSC см. в [этой записи](https://aka.ms/certs4dsc).

Чтобы принудительно использовать пароль в виде простого текста, необходимо добавить в раздел данных конфигурации ресурса ключ `PsDscAllowPlainTextPassword` следующим образом:

```powershell
$password = "ThisIsAPlaintextPassword" | ConvertTo-SecureString -asPlainText -Force
$username = "contoso\Administrator"
[PSCredential] $credential = New-Object System.Management.Automation.PSCredential($username,$password)

Configuration DomainCredentialExample
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration

    node localhost
    {
        Group DomainUserToLocalGroup
        {
            GroupName        = 'ApplicationAdmins'
            MembersToInclude = 'contoso\alice'
            Credential       = $credential
        }
    }
}

$cd = @{
    AllNodes = @(
        @{
            NodeName = 'localhost'
            PSDscAllowPlainTextPassword = $true
        }
    )
}

DomainCredentialExample -ConfigurationData $cd
```

### <a name="localhostmof"></a>localhost.mof

Флаг **PSDSCAllowPlainTextPassword** требует осведомленности пользователя о риске хранения паролей в виде простого текста в MOF-файле. В созданном MOF-файле, даже если использовался объект **PSCredential**, содержащий **SecureString**, пароли по-прежнему отображаются в виде обычного текста. Это единственный случай, когда учетные данные предоставляются. Получение доступа к этому MOF-файлу дает любому пользователю доступ к учетной записи администратора.

```
/*
@TargetNode='localhost'
@GeneratedBy=Administrator
@GenerationDate=01/31/2019 06:43:13
@GenerationHost=Server01
*/

instance of MSFT_Credential as $MSFT_Credential1ref
{
Password = "ThisIsAPlaintextPassword";
 UserName = "Administrator";

};

instance of MSFT_GroupResource as $MSFT_GroupResource1ref
{
ResourceID = "[Group]DomainUserToLocalGroup";
 MembersToInclude = {
    "contoso\\alice"
};
 Credential = $MSFT_Credential1ref;
 SourceInfo = "::11::9::Group";
 GroupName = "ApplicationAdmins";
 ModuleName = "PSDesiredStateConfiguration";

ModuleVersion = "1.0";

 ConfigurationName = "DomainCredentialExample";

};
```

### <a name="credentials-in-transit-and-at-rest"></a>Учетные данные при передаче и хранении

- Флаг **PSDscAllowPlainTextPassword** позволяет компилировать MOF-файлы, содержащие пароли в виде открытого текста. Соблюдайте меры предосторожности при сохранении MOF-файлов, которые содержат пароли в виде открытого текста.
- При доставке MOF-файла на узел в режиме **отправки** WinRM шифрует сообщение для защиты пароля в виде открытого текста, если вы не переопределите значение по умолчанию с помощью параметра **AllowUnencrypted**.
  - Шифрование MOF-файла с сертификатом защищает его при хранении, прежде чем он применится к узлу.
- В режиме **получения** можно настроить опрашиваемый сервер Windows так, чтобы использовать HTTPS для шифрования трафика с помощью протокола, указанного в IIS. Дополнительные сведения см. в статьях [Настройка опрашивающего клиента DSC](../pull-server/pullclient.md) и [Защита MOF-файла](../pull-server/secureMOF.md).
  - В службе [Настройка состояния службы автоматизации Azure](/azure/automation/automation-dsc-overview) трафик запроса всегда шифруется.
- Начиная с PowerShell 5.0, на узле MOF-файлы хранятся в зашифрованном состоянии.
  - В PowerShell 4.0 MOF-файлы не хранятся в зашифрованном состоянии, если они не зашифрованы с помощью сертификата при их отправке на узел или извлечении с него.

**Корпорация Майкрософт не рекомендует использовать пароли в виде простого текста из-за серьезной угрозы безопасности.**

## <a name="domain-credentials"></a>Учетные данные домена

Выполнив сценарий конфигурации из примера еще раз (с шифрованием или без), вы снова получите предупреждение о том, что использовать доменную учетную запись в качестве учетных данных не рекомендуется. Пользуясь для этой цели локальной учетной записью, вы защитите от риска доменные учетные данные, которые можно использовать на других серверах.

**Используя учетные данные с ресурсами DSC, по возможности отдавайте предпочтение локальной учетной записи, а не доменной.**

Если свойство `Username` учетных данных содержит \\ или \@, DSC будет рассматривать их как доменную учетную запись. Исключение составляют значения localhost, 127.0.0.1 и ::1 в доменной части имени пользователя.

## <a name="psdscallowdomainuser"></a>PSDscAllowDomainUser

В приведенном выше примере ресурса `Group` DSC для запроса к домену Active Directory *требуется* доменная учетная запись. В этом случае добавьте свойство `PSDscAllowDomainUser` в блок `ConfigurationData` следующим образом:

```powershell
$password = "ThisIsAPlaintextPassword" | ConvertTo-SecureString -asPlainText -Force
$username = "contoso\Administrator"
[PSCredential] $credential = New-Object System.Management.Automation.PSCredential($username,$password)

Configuration DomainCredentialExample
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration

    node localhost
    {
        Group DomainUserToLocalGroup
        {
            GroupName        = 'ApplicationAdmins'
            MembersToInclude = 'contoso\alice'
            Credential       = $credential
        }
    }
}

$cd = @{
    AllNodes = @(
        @{
            NodeName = 'localhost'
            PSDscAllowDomainUser = $true
            PSDscAllowPlainTextPassword = $true
        }
    )
}

DomainCredentialExample -ConfigurationData $cd
```

После этого сценарий конфигурации создаст MOF-файл без ошибок или предупреждений.
