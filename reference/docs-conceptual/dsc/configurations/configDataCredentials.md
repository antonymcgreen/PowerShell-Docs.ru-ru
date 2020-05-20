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
# <a name="credentials-options-in-configuration-data"></a><span data-ttu-id="90902-103">Параметры учетных данных в данных конфигурации</span><span class="sxs-lookup"><span data-stu-id="90902-103">Credentials Options in Configuration Data</span></span>

> <span data-ttu-id="90902-104">Область применения: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="90902-104">Applies To: Windows PowerShell 5.0</span></span>

## <a name="plain-text-passwords-and-domain-users"></a><span data-ttu-id="90902-105">Пароли в виде простого текста и пользователи домена</span><span class="sxs-lookup"><span data-stu-id="90902-105">Plain Text Passwords and Domain Users</span></span>

<span data-ttu-id="90902-106">При использовании конфигураций DSC, содержащих незашифрованные учетные данные, выдается сообщение об ошибке из-за указания паролей в виде простого текста.</span><span class="sxs-lookup"><span data-stu-id="90902-106">DSC configurations containing a credential without encryption will generate an error message about plain text passwords.</span></span> <span data-ttu-id="90902-107">Кроме того, DSC выдает предупреждение при использовании учетных данных домена.</span><span class="sxs-lookup"><span data-stu-id="90902-107">Also, DSC will generate a warning when using domain credentials.</span></span> <span data-ttu-id="90902-108">Чтобы не получать такие ошибки и предупреждения, используйте следующие ключевые слова в данных конфигурации DSC.</span><span class="sxs-lookup"><span data-stu-id="90902-108">To suppress these error and warning messages use the DSC configuration data keywords:</span></span>

- <span data-ttu-id="90902-109">**PsDscAllowPlainTextPassword**</span><span class="sxs-lookup"><span data-stu-id="90902-109">**PsDscAllowPlainTextPassword**</span></span>
- <span data-ttu-id="90902-110">**PsDscAllowDomainUser**</span><span class="sxs-lookup"><span data-stu-id="90902-110">**PsDscAllowDomainUser**</span></span>

> [!NOTE]
> <span data-ttu-id="90902-111">Хранение и передача незашифрованных паролей с простым текстом обычно являются небезопасными.</span><span class="sxs-lookup"><span data-stu-id="90902-111">Storing/transmitting plaintext passwords unencrypted is generally not secure.</span></span> <span data-ttu-id="90902-112">Рекомендуется использовать методы защиты учетных данных, описанные далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="90902-112">Securing credentials by using the techniques covered later in this topic is recommended.</span></span> <span data-ttu-id="90902-113">Служба Azure Automation DSC позволяет вам централизованно управлять учетными данными, включать их в конфигурации и обеспечивать безопасное хранение.</span><span class="sxs-lookup"><span data-stu-id="90902-113">The Azure Automation DSC service allows you to centrally manage credentials to be compiled in configurations and stored securely.</span></span> <span data-ttu-id="90902-114">Дополнительные сведения: [Компиляция конфигураций DSC/ресурсы-контейнеры учетных данных](/azure/automation/automation-dsc-compile#credential-assets)</span><span class="sxs-lookup"><span data-stu-id="90902-114">For information, see: [Compiling DSC Configurations / Credential Assets](/azure/automation/automation-dsc-compile#credential-assets)</span></span>

## <a name="handling-credentials-in-dsc"></a><span data-ttu-id="90902-115">Обработка учетных данных в DSC</span><span class="sxs-lookup"><span data-stu-id="90902-115">Handling Credentials in DSC</span></span>

<span data-ttu-id="90902-116">По умолчанию ресурсы DSC запускаются от имени `Local System`.</span><span class="sxs-lookup"><span data-stu-id="90902-116">DSC configuration resources run as `Local System` by default.</span></span> <span data-ttu-id="90902-117">При этом некоторые ресурсы требуют учетных данных, например, если ресурсу `Package` необходимо установить программное обеспечение с помощью учетной записи определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="90902-117">However, some resources need a credential, for example when the `Package` resource needs to install software under a specific user account.</span></span>

<span data-ttu-id="90902-118">В более ранних ресурсах для этого использовалось прописываемое в коде свойство `Credential`.</span><span class="sxs-lookup"><span data-stu-id="90902-118">Earlier resources used a hard-coded `Credential` property name to handle this.</span></span> <span data-ttu-id="90902-119">В WMF 5.0 для всех ресурсов было добавлено автоматическое свойство `PsDscRunAsCredential`.</span><span class="sxs-lookup"><span data-stu-id="90902-119">WMF 5.0 added an automatic `PsDscRunAsCredential` property for all resources.</span></span> <span data-ttu-id="90902-120">Дополнительные сведения об использовании `PsDscRunAsCredential` см. в разделе [Запуск DSC с учетными данными пользователя](runAsUser.md).</span><span class="sxs-lookup"><span data-stu-id="90902-120">For information about using `PsDscRunAsCredential`, see [Running DSC with user credentials](runAsUser.md).</span></span> <span data-ttu-id="90902-121">Новые и настраиваемые ресурсы позволяют использовать это автоматическое свойство вместо создания отдельного свойства для учетных данных.</span><span class="sxs-lookup"><span data-stu-id="90902-121">Newer resources and custom resources can use this automatic property instead of creating their own property for credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="90902-122">Некоторые виды ресурсов используют множество учетных данных для определенной цели. Такие ресурсы имеют собственные свойства учетных данных.</span><span class="sxs-lookup"><span data-stu-id="90902-122">The design of some resources are to use multiple credentials for a specific reason, and they will have their own credential properties.</span></span>

<span data-ttu-id="90902-123">Чтобы найти доступные свойства учетных данных ресурса, используйте `Get-DscResource -Name ResourceName -Syntax` или Intellisense в интегрированной среде сценариев (`CTRL+SPACE`).</span><span class="sxs-lookup"><span data-stu-id="90902-123">To find the available credential properties on a resource use either `Get-DscResource -Name ResourceName -Syntax` or the Intellisense in the ISE (`CTRL+SPACE`).</span></span>

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

<span data-ttu-id="90902-124">В этом примере используется ресурс [Group](../resources/resources.md) из встроенного модуля ресурсов DSC `PSDesiredStateConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="90902-124">This example uses a [Group](../resources/resources.md) resource from the `PSDesiredStateConfiguration` built-in DSC resource module.</span></span> <span data-ttu-id="90902-125">Он может создавать локальные группы, а также добавлять и удалять члены.</span><span class="sxs-lookup"><span data-stu-id="90902-125">It can create local groups and add or remove members.</span></span> <span data-ttu-id="90902-126">Этот ресурс принимает как свойство `Credential`, так и автоматическое свойство `PsDscRunAsCredential`,</span><span class="sxs-lookup"><span data-stu-id="90902-126">It accepts both the `Credential` property and the automatic `PsDscRunAsCredential` property.</span></span> <span data-ttu-id="90902-127">но использует только свойство `Credential`.</span><span class="sxs-lookup"><span data-stu-id="90902-127">However, the resource only uses the `Credential` property.</span></span>

<span data-ttu-id="90902-128">См. дополнительные сведения о свойстве `PsDscRunAsCredential` и [запуске DSC с учетными данными пользователя](runAsUser.md).</span><span class="sxs-lookup"><span data-stu-id="90902-128">For more information about the `PsDscRunAsCredential` property, see [Running DSC with user credentials](runAsUser.md).</span></span>

## <a name="example-the-group-resource-credential-property"></a><span data-ttu-id="90902-129">Пример: свойство учетных данных для ресурса Group</span><span class="sxs-lookup"><span data-stu-id="90902-129">Example: The Group resource Credential property</span></span>

<span data-ttu-id="90902-130">DSC выполняется в качестве `Local System`, поэтому уже имеет разрешения на изменение локальных пользователей и групп.</span><span class="sxs-lookup"><span data-stu-id="90902-130">DSC runs under `Local System`, so it already has permissions to change local users and groups.</span></span> <span data-ttu-id="90902-131">Если в локальную учетную группу добавляется новый пользователь, учетные данные не требуются.</span><span class="sxs-lookup"><span data-stu-id="90902-131">If the member added is a local account, then no credential is necessary.</span></span> <span data-ttu-id="90902-132">Но если ресурс `Group` добавляет учетную запись домена в локальную группу, учетные данные необходимы.</span><span class="sxs-lookup"><span data-stu-id="90902-132">If the `Group` resource adds a domain account to the local group, then a credential is necessary.</span></span>

<span data-ttu-id="90902-133">Анонимные запросы к Active Directory не допускаются.</span><span class="sxs-lookup"><span data-stu-id="90902-133">Anonymous queries to Active Directory are not allowed.</span></span> <span data-ttu-id="90902-134">Свойство `Credential` ресурса `Group` — это учетная запись домена, которая используется для запросов к Active Directory.</span><span class="sxs-lookup"><span data-stu-id="90902-134">The `Credential` property of the `Group` resource is the domain account used to query Active Directory.</span></span> <span data-ttu-id="90902-135">В большинстве случаев это может быть универсальная учетная запись пользователя, поскольку пользователи по умолчанию могут *читать* большинство объектов в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="90902-135">For most purposes this could be a generic user account, because by default users can *read* most of the objects in Active Directory.</span></span>

## <a name="example-configuration"></a><span data-ttu-id="90902-136">Пример конфигурации</span><span class="sxs-lookup"><span data-stu-id="90902-136">Example Configuration</span></span>

<span data-ttu-id="90902-137">В следующем примере кода DSC используется для добавления пользователя домена в локальную группу:</span><span class="sxs-lookup"><span data-stu-id="90902-137">The following example code uses DSC to populate a local group with a domain user:</span></span>

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

<span data-ttu-id="90902-138">Этот код вызывает ошибку и предупреждение:</span><span class="sxs-lookup"><span data-stu-id="90902-138">This code generates both an error and warning message:</span></span>

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

<span data-ttu-id="90902-139">В этом примере есть две проблемы:</span><span class="sxs-lookup"><span data-stu-id="90902-139">This example has two issues:</span></span>

1. <span data-ttu-id="90902-140">Ошибка с указанием на то, что использовать пароли в виде простого текста не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="90902-140">An error explains that plain text passwords are not recommended</span></span>
2. <span data-ttu-id="90902-141">Предупреждение с рекомендацией не использовать доменные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="90902-141">A warning advises against using a domain credential</span></span>

<span data-ttu-id="90902-142">Флаги **PSDSCAllowPlainTextPassword** и **PSDSCAllowDomainUser** подавляют ошибку и предупреждают пользователя о риске.</span><span class="sxs-lookup"><span data-stu-id="90902-142">The flags **PSDSCAllowPlainTextPassword** and **PSDSCAllowDomainUser** suppress the error and warning informing the user of the risk involved.</span></span>

## <a name="psdscallowplaintextpassword"></a><span data-ttu-id="90902-143">PSDSCAllowPlainTextPassword</span><span class="sxs-lookup"><span data-stu-id="90902-143">PSDSCAllowPlainTextPassword</span></span>

<span data-ttu-id="90902-144">В первом сообщении об ошибке находится URL-адрес документации.</span><span class="sxs-lookup"><span data-stu-id="90902-144">The first error message has a URL with documentation.</span></span> <span data-ttu-id="90902-145">Он содержит инструкции по шифрованию паролей с использованием структуры [ConfigurationData](./configData.md) и сертификата.</span><span class="sxs-lookup"><span data-stu-id="90902-145">This link explains how to encrypt passwords using a [ConfigurationData](./configData.md) structure and a certificate.</span></span> <span data-ttu-id="90902-146">Дополнительные сведения о сертификатах в DSC см. в [этой записи](https://aka.ms/certs4dsc).</span><span class="sxs-lookup"><span data-stu-id="90902-146">For more information on certificates and DSC [read this post](https://aka.ms/certs4dsc).</span></span>

<span data-ttu-id="90902-147">Чтобы принудительно использовать пароль в виде простого текста, необходимо добавить в раздел данных конфигурации ресурса ключ `PsDscAllowPlainTextPassword` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="90902-147">To force a plain text password, the resource requires the `PsDscAllowPlainTextPassword` keyword in the configuration data section as follows:</span></span>

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

### <a name="localhostmof"></a><span data-ttu-id="90902-148">localhost.mof</span><span class="sxs-lookup"><span data-stu-id="90902-148">localhost.mof</span></span>

<span data-ttu-id="90902-149">Флаг **PSDSCAllowPlainTextPassword** требует осведомленности пользователя о риске хранения паролей в виде простого текста в MOF-файле.</span><span class="sxs-lookup"><span data-stu-id="90902-149">The **PSDSCAllowPlainTextPassword** flag requires that the user acknowledge the risk of storing plain text passwords in a MOF file.</span></span> <span data-ttu-id="90902-150">В созданном MOF-файле, даже если использовался объект **PSCredential**, содержащий **SecureString**, пароли по-прежнему отображаются в виде обычного текста.</span><span class="sxs-lookup"><span data-stu-id="90902-150">In the generated MOF file, even though a **PSCredential** object containing a **SecureString** was used, the passwords still appear as plain text.</span></span> <span data-ttu-id="90902-151">Это единственный случай, когда учетные данные предоставляются.</span><span class="sxs-lookup"><span data-stu-id="90902-151">This is the only time the credentials are exposed.</span></span> <span data-ttu-id="90902-152">Получение доступа к этому MOF-файлу дает любому пользователю доступ к учетной записи администратора.</span><span class="sxs-lookup"><span data-stu-id="90902-152">Gaining access to this MOF file gives anyone access to the Administrator account.</span></span>

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

### <a name="credentials-in-transit-and-at-rest"></a><span data-ttu-id="90902-153">Учетные данные при передаче и хранении</span><span class="sxs-lookup"><span data-stu-id="90902-153">Credentials in transit and at rest</span></span>

- <span data-ttu-id="90902-154">Флаг **PSDscAllowPlainTextPassword** позволяет компилировать MOF-файлы, содержащие пароли в виде открытого текста.</span><span class="sxs-lookup"><span data-stu-id="90902-154">The **PSDscAllowPlainTextPassword** flag allows the compilation of MOF files that contain passwords in clear text.</span></span> <span data-ttu-id="90902-155">Соблюдайте меры предосторожности при сохранении MOF-файлов, которые содержат пароли в виде открытого текста.</span><span class="sxs-lookup"><span data-stu-id="90902-155">Take precautions when storing MOF files containing clear text passwords.</span></span>
- <span data-ttu-id="90902-156">При доставке MOF-файла на узел в режиме **отправки** WinRM шифрует сообщение для защиты пароля в виде открытого текста, если вы не переопределите значение по умолчанию с помощью параметра **AllowUnencrypted**.</span><span class="sxs-lookup"><span data-stu-id="90902-156">When the MOF file is delivered to a Node in **Push** mode, WinRM encrypts the communication to protect the clear text password unless you override the default with the **AllowUnencrypted** parameter.</span></span>
  - <span data-ttu-id="90902-157">Шифрование MOF-файла с сертификатом защищает его при хранении, прежде чем он применится к узлу.</span><span class="sxs-lookup"><span data-stu-id="90902-157">Encrypting the MOF with a certificate protects the MOF file at rest before it has been applied to a node.</span></span>
- <span data-ttu-id="90902-158">В режиме **получения** можно настроить опрашиваемый сервер Windows так, чтобы использовать HTTPS для шифрования трафика с помощью протокола, указанного в IIS.</span><span class="sxs-lookup"><span data-stu-id="90902-158">In **Pull** mode, you can configure Windows pull server to use HTTPS to encrypt traffic using the protocol specified in Internet Information Server.</span></span> <span data-ttu-id="90902-159">Дополнительные сведения см. в статьях [Настройка опрашивающего клиента DSC](../pull-server/pullclient.md) и [Защита MOF-файла](../pull-server/secureMOF.md).</span><span class="sxs-lookup"><span data-stu-id="90902-159">For more information, see the articles [Setting up a DSC pull client](../pull-server/pullclient.md) and [Securing MOF files with Certificates](../pull-server/secureMOF.md).</span></span>
  - <span data-ttu-id="90902-160">В службе [Настройка состояния службы автоматизации Azure](/azure/automation/automation-dsc-overview) трафик запроса всегда шифруется.</span><span class="sxs-lookup"><span data-stu-id="90902-160">In the [Azure Automation State Configuration](/azure/automation/automation-dsc-overview) service, Pull traffic is always encrypted.</span></span>
- <span data-ttu-id="90902-161">Начиная с PowerShell 5.0, на узле MOF-файлы хранятся в зашифрованном состоянии.</span><span class="sxs-lookup"><span data-stu-id="90902-161">On the Node, MOF files are encrypted at rest Beginning in PowerShell 5.0.</span></span>
  - <span data-ttu-id="90902-162">В PowerShell 4.0 MOF-файлы не хранятся в зашифрованном состоянии, если они не зашифрованы с помощью сертификата при их отправке на узел или извлечении с него.</span><span class="sxs-lookup"><span data-stu-id="90902-162">In PowerShell 4.0 MOF files are unencrypted at rest unless they are encrypted with a certificate when they pushed or pulled to the Node.</span></span>

<span data-ttu-id="90902-163">**Корпорация Майкрософт не рекомендует использовать пароли в виде простого текста из-за серьезной угрозы безопасности.**</span><span class="sxs-lookup"><span data-stu-id="90902-163">**Microsoft advises to avoid plain text passwords due to the significant security risk.**</span></span>

## <a name="domain-credentials"></a><span data-ttu-id="90902-164">Учетные данные домена</span><span class="sxs-lookup"><span data-stu-id="90902-164">Domain Credentials</span></span>

<span data-ttu-id="90902-165">Выполнив сценарий конфигурации из примера еще раз (с шифрованием или без), вы снова получите предупреждение о том, что использовать доменную учетную запись в качестве учетных данных не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="90902-165">Running the example configuration script again (with or without encryption), still generates the warning that using a domain account for a credential is not recommended.</span></span> <span data-ttu-id="90902-166">Пользуясь для этой цели локальной учетной записью, вы защитите от риска доменные учетные данные, которые можно использовать на других серверах.</span><span class="sxs-lookup"><span data-stu-id="90902-166">Using a local account eliminates potential exposure of domain credentials that could be used on other servers.</span></span>

<span data-ttu-id="90902-167">**Используя учетные данные с ресурсами DSC, по возможности отдавайте предпочтение локальной учетной записи, а не доменной.**</span><span class="sxs-lookup"><span data-stu-id="90902-167">**When using credentials with DSC resources, prefer a local account over a domain account when possible.**</span></span>

<span data-ttu-id="90902-168">Если свойство `Username` учетных данных содержит \\ или \@, DSC будет рассматривать их как доменную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="90902-168">If there is a '\\' or '\@' in the `Username` property of the credential, then DSC will treat it as a domain account.</span></span> <span data-ttu-id="90902-169">Исключение составляют значения localhost, 127.0.0.1 и ::1 в доменной части имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="90902-169">There is an exception for "localhost", "127.0.0.1", and "::1" in the domain portion of the user name.</span></span>

## <a name="psdscallowdomainuser"></a><span data-ttu-id="90902-170">PSDscAllowDomainUser</span><span class="sxs-lookup"><span data-stu-id="90902-170">PSDscAllowDomainUser</span></span>

<span data-ttu-id="90902-171">В приведенном выше примере ресурса `Group` DSC для запроса к домену Active Directory *требуется* доменная учетная запись.</span><span class="sxs-lookup"><span data-stu-id="90902-171">In the DSC `Group` resource example above, querying an Active Directory domain *requires* a domain account.</span></span> <span data-ttu-id="90902-172">В этом случае добавьте свойство `PSDscAllowDomainUser` в блок `ConfigurationData` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="90902-172">In this case add the `PSDscAllowDomainUser` property to the `ConfigurationData` block as follows:</span></span>

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

<span data-ttu-id="90902-173">После этого сценарий конфигурации создаст MOF-файл без ошибок или предупреждений.</span><span class="sxs-lookup"><span data-stu-id="90902-173">Now the configuration script will generate the MOF file with no errors or warnings.</span></span>
