---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Использование учетных данных с ресурсами DSC
ms.openlocfilehash: fea2e3cad8d081c17853e127203f1d40d98c5de2
ms.sourcegitcommit: bc42c9166857147a1ecf9924b718d4a48eb901e3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2019
ms.locfileid: "66470766"
---
# <a name="use-credentials-with-dsc-resources"></a><span data-ttu-id="da273-103">Использование учетных данных с ресурсами DSC</span><span class="sxs-lookup"><span data-stu-id="da273-103">Use Credentials with DSC Resources</span></span>

> <span data-ttu-id="da273-104">Область применения. Windows PowerShell 5.0, Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="da273-104">Applies To: Windows PowerShell 5.0, Windows PowerShell 5.1</span></span>

<span data-ttu-id="da273-105">Ресурс DSC можно запускать с определенным набором учетных данных. Для этого используется автоматическое свойство **PsDscRunAsCredential** в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="da273-105">You can run a DSC resource under a specified set of credentials by using the automatic **PsDscRunAsCredential** property in the configuration.</span></span> <span data-ttu-id="da273-106">По умолчанию DSC запускает каждый ресурс в качестве системной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="da273-106">By default, DSC runs each resource as the system account.</span></span> <span data-ttu-id="da273-107">Иногда бывает необходим запуск с учетной записью обычного пользователя, например, при установке MSI-пакетов в контексте определенного пользователя, при установке разделов реестра пользователя, доступе к конкретному локальному каталогу пользователя или сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="da273-107">There are times when running as a user is necessary, such as installing MSI packages in a specific user context, setting a user's registry keys, accessing a user's specific local directory, or accessing a network share.</span></span> <span data-ttu-id="da273-108">Согласно требованиям целевого компьютера нужно обязательно указать **SeInteractiveLogonRight** для любой учетной записи, назначенной свойству **PSDSCRunAsCredential**.</span><span class="sxs-lookup"><span data-stu-id="da273-108">The **SeInteractiveLogonRight** is required, by the target machine, for any account you specify to **PSDSCRunAsCredential**.</span></span> <span data-ttu-id="da273-109">Дополнительные сведения см. в статье [Account Rights Constants](/windows/desktop/secauthz/account-rights-constants) (Константы прав учетных записей).</span><span class="sxs-lookup"><span data-stu-id="da273-109">For more information, see [Account Rights Constants](/windows/desktop/secauthz/account-rights-constants).</span></span>

<span data-ttu-id="da273-110">У каждого ресурса есть свойство **PsDscRunAsCredential**, которому можно назначить учетные данные любого пользователя (объект [PSCredential](/dotnet/api/system.management.automation.pscredential)).</span><span class="sxs-lookup"><span data-stu-id="da273-110">Every DSC resource has a **PsDscRunAsCredential** property that can be set to any user credentials (a [PSCredential](/dotnet/api/system.management.automation.pscredential) object).</span></span> <span data-ttu-id="da273-111">Учетные данные можно жестко задать в качестве значения свойства конфигурации или установить в качестве значения [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential). В этом случае пользователю будет предложено ввести учетные данные при компиляции конфигурации (дополнительные сведения о компиляции конфигураций см. в разделе [Конфигурации](configurations.md)).</span><span class="sxs-lookup"><span data-stu-id="da273-111">The credential can be hard-coded as the value of the property in the configuration, or you can set the value to [Get-Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential), which will prompt the user for a credential when the configuration is compiled (for information about compiling configurations, see [Configurations](configurations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="da273-112">В PowerShell 5.0 использование свойства **PsDscRunAsCredential** в конфигурациях, вызывающих составные ресурсы, не поддерживалось.</span><span class="sxs-lookup"><span data-stu-id="da273-112">In PowerShell 5.0, using the **PsDscRunAsCredential** property in configurations calling composite resources was not supported.</span></span> <span data-ttu-id="da273-113">В PowerShell 5.1 свойство **PsDscRunAsCredential** поддерживается в конфигурациях, вызывающих составные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="da273-113">In PowerShell 5.1, the **PsDscRunAsCredential** property is supported in configurations calling composite resources.</span></span> <span data-ttu-id="da273-114">Свойство **PsDscRunAsCredential** недоступно в PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="da273-114">The **PsDscRunAsCredential** property is not available in PowerShell 4.0.</span></span>

<span data-ttu-id="da273-115">В следующем примере `Get-Credential` используется для запроса учетных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="da273-115">In the following example, `Get-Credential` is used to prompt the user for credentials.</span></span> <span data-ttu-id="da273-116">Ресурс **Registry** используется для изменения раздела реестра, указывающего цвет фона для окна командной строки Windows.</span><span class="sxs-lookup"><span data-stu-id="da273-116">The **Registry** resource is used to change the registry key that specifies the background color for the Windows command prompt window.</span></span>

```powershell
Configuration ChangeCmdBackGroundColor
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration

    Node $AllNodes.NodeName
    {
        Registry CmdPath
        {
            Key                  = 'HKEY_CURRENT_USER\SOFTWARE\Microsoft\Command Processor'
            ValueName            = 'DefaultColor'
            ValueData            = '1F'
            ValueType            = 'DWORD'
            Ensure               = 'Present'
            Force                = $true
            Hex                  = $true
            PsDscRunAsCredential = Get-Credential
        }
    }
}

$configData = @{
    AllNodes = @(
        @{
            NodeName             = 'localhost';
            PSDscAllowDomainUser = $true
            CertificateFile      = 'C:\publicKeys\targetNode.cer'
            Thumbprint           = '7ee7f09d-4be0-41aa-a47f-96b9e3bdec25'
        }
    )
}

ChangeCmdBackGroundColor -ConfigurationData $configData
```

> [!NOTE]
> <span data-ttu-id="da273-117">В этом примере предполагается, что у вас есть действительный сертификат в `C:\publicKeys\targetNode.cer` и что отображаемое значение представляет собой отпечаток этого сертификата.</span><span class="sxs-lookup"><span data-stu-id="da273-117">This example assumes that you have a valid certificate at `C:\publicKeys\targetNode.cer`, and that the thumbprint of that certificate is the value shown.</span></span> <span data-ttu-id="da273-118">Сведения о шифровании учетных данных в MOF-файлах конфигурации DSC см. в разделе [Защита MOF-файла](../pull-server/secureMOF.md).</span><span class="sxs-lookup"><span data-stu-id="da273-118">For information about encrypting credentials in DSC configuration MOF files, see [Securing the MOF file](../pull-server/secureMOF.md).</span></span>
