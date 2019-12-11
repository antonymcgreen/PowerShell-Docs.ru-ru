---
ms.date: 01/17/2019
keywords: dsc,powershell,конфигурация,установка
title: Перезагрузка узла
ms.openlocfilehash: 22c63fab9b6646f522f8531b46a43a94ff883552
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "71954031"
---
# <a name="reboot-a-node"></a><span data-ttu-id="eab0a-103">Перезагрузка узла</span><span class="sxs-lookup"><span data-stu-id="eab0a-103">Reboot a Node</span></span>

> [!NOTE]
> <span data-ttu-id="eab0a-104">В этом разделе рассказывается о том, как перезагрузить узел.</span><span class="sxs-lookup"><span data-stu-id="eab0a-104">This topic talks about how to reboot a Node.</span></span> <span data-ttu-id="eab0a-105">Для успешной перезагрузки необходимо правильно настроить параметры **ActionAfterReboot** и **RebootNodeIfNeeded** локального диспетчера конфигураций.</span><span class="sxs-lookup"><span data-stu-id="eab0a-105">In order for the reboot to be successful the **ActionAfterReboot** and **RebootNodeIfNeeded** LCM settings need to be configured properly.</span></span>
> <span data-ttu-id="eab0a-106">Описание параметров локального диспетчера конфигураций см. в разделе [Настройка локального диспетчера конфигураций](../managing-nodes/metaConfig.md) или [Настройка локального диспетчера конфигураций (версия 4)](../managing-nodes/metaConfig4.md).</span><span class="sxs-lookup"><span data-stu-id="eab0a-106">To read about Local Configuration Manager settings, see [Configure the Local Configuration Manager](../managing-nodes/metaConfig.md), or [Configure the Local Configuration Manager (v4)](../managing-nodes/metaConfig4.md).</span></span>

<span data-ttu-id="eab0a-107">Узлы можно перезагрузить из ресурса с помощью флага `$global:DSCMachineStatus`.</span><span class="sxs-lookup"><span data-stu-id="eab0a-107">Nodes can be rebooted from within a resource, by using the `$global:DSCMachineStatus` flag.</span></span> <span data-ttu-id="eab0a-108">Установка этого флага как `1` в функции `Set-TargetResource` принуждает LCM перезапускать узел непосредственно после метода **Set** текущего ресурса.</span><span class="sxs-lookup"><span data-stu-id="eab0a-108">Setting this flag to `1` in the `Set-TargetResource` function forces the LCM to reboot the Node directly after the **Set** method of the current resource.</span></span> <span data-ttu-id="eab0a-109">При указании этого флага ресурс **PendingReboot** в модуле ресурсов DSC [ComputerManagementDsc](https://github.com/PowerShell/ComputerManagementDsc) обнаруживает, что ожидается перезагрузка за пределами DSC.</span><span class="sxs-lookup"><span data-stu-id="eab0a-109">Using this flag, the **PendingReboot** resource in the [ComputerManagementDsc](https://github.com/PowerShell/ComputerManagementDsc) DSC Resource module detects if a reboot is pending outside of DSC.</span></span>

<span data-ttu-id="eab0a-110">Ваши [конфигурации](configurations.md) могут выполнять действия, требующие перезагрузки узла.</span><span class="sxs-lookup"><span data-stu-id="eab0a-110">Your [configurations](configurations.md) may perform steps that require the Node to reboot.</span></span> <span data-ttu-id="eab0a-111">Сюда могут входить такие вещи, как:</span><span class="sxs-lookup"><span data-stu-id="eab0a-111">This could include things such as:</span></span>

- <span data-ttu-id="eab0a-112">обновления Windows;</span><span class="sxs-lookup"><span data-stu-id="eab0a-112">Windows updates</span></span>
- <span data-ttu-id="eab0a-113">установка ПО;</span><span class="sxs-lookup"><span data-stu-id="eab0a-113">Software install</span></span>
- <span data-ttu-id="eab0a-114">переименование файлов;</span><span class="sxs-lookup"><span data-stu-id="eab0a-114">File renames</span></span>
- <span data-ttu-id="eab0a-115">переименование компьютеров.</span><span class="sxs-lookup"><span data-stu-id="eab0a-115">Computer rename</span></span>

<span data-ttu-id="eab0a-116">Ресурс **PendingReboot** проверяет конкретные места на компьютере, чтобы определить, ожидается ли перезагрузка.</span><span class="sxs-lookup"><span data-stu-id="eab0a-116">The **PendingReboot** resource checks specific computer locations to determine if a reboot is pending.</span></span> <span data-ttu-id="eab0a-117">Если узлу требуется перезагрузка за пределами DSC, ресурс **PendingReboot** задает флаг `$global:DSCMachineStatus` как `1`, вызывая принудительную перезагрузку и устраняя состояние ожидания.</span><span class="sxs-lookup"><span data-stu-id="eab0a-117">If the Node requires a reboot outside of DSC, the **PendingReboot** resource sets the `$global:DSCMachineStatus` flag to `1` forcing a reboot and resolving the pending condition.</span></span>

> [!NOTE]
> <span data-ttu-id="eab0a-118">Любой ресурс DSC может заставить LCM перезапустить узел, установив этот флаг в функции `Set-TargetResource`.</span><span class="sxs-lookup"><span data-stu-id="eab0a-118">Any DSC resource can instruct the LCM to reboot the node by setting this flag in the `Set-TargetResource` function.</span></span> <span data-ttu-id="eab0a-119">Дополнительные сведения см. в разделе [Написание пользовательских ресурсов DSC с использованием MOF](../resources/authoringResourceMOF.md).</span><span class="sxs-lookup"><span data-stu-id="eab0a-119">For more information, see [Writing a custom DSC resource with MOF](../resources/authoringResourceMOF.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="eab0a-120">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eab0a-120">Syntax</span></span>

```
PendingReboot [String] #ResourceName
{
    Name = [string]
    [DependsOn = [string[]]]
    [PsDscRunAsCredential = [PSCredential]]
    [SkipCcmClientSDK = [bool]]
    [SkipComponentBasedServicing = [bool]]
    [SkipPendingComputerRename = [bool]]
    [SkipPendingFileRename = [bool]]
    [SkipWindowsUpdate = [bool]]
}
```

## <a name="properties"></a><span data-ttu-id="eab0a-121">Свойства</span><span class="sxs-lookup"><span data-stu-id="eab0a-121">Properties</span></span>

| <span data-ttu-id="eab0a-122">Свойство</span><span class="sxs-lookup"><span data-stu-id="eab0a-122">Property</span></span> | <span data-ttu-id="eab0a-123">Описание</span><span class="sxs-lookup"><span data-stu-id="eab0a-123">Description</span></span> |
| --- | --- |
| <span data-ttu-id="eab0a-124">Name</span><span class="sxs-lookup"><span data-stu-id="eab0a-124">Name</span></span>| <span data-ttu-id="eab0a-125">Обязательный параметр, который должен быть уникальным для каждого экземпляра ресурса в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="eab0a-125">Required parameter that must be unique per instance of the resource within a configuration.</span></span>|
| <span data-ttu-id="eab0a-126">SkipComponentBasedServicing</span><span class="sxs-lookup"><span data-stu-id="eab0a-126">SkipComponentBasedServicing</span></span> | <span data-ttu-id="eab0a-127">Пропускать перезагрузки, активируемые компонентом Component-Based Servicing.</span><span class="sxs-lookup"><span data-stu-id="eab0a-127">Skip reboots triggered by the Component-Based Servicing component.</span></span> |
| <span data-ttu-id="eab0a-128">SkipWindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="eab0a-128">SkipWindowsUpdate</span></span> | <span data-ttu-id="eab0a-129">Пропускать перезагрузки, активируемые обновлениями Windows.</span><span class="sxs-lookup"><span data-stu-id="eab0a-129">Skip reboots triggered by Windows Update.</span></span>|
| <span data-ttu-id="eab0a-130">SkipPendingFileRename</span><span class="sxs-lookup"><span data-stu-id="eab0a-130">SkipPendingFileRename</span></span> | <span data-ttu-id="eab0a-131">Пропускать перезагрузки, активируемые переименованием файлов.</span><span class="sxs-lookup"><span data-stu-id="eab0a-131">Skip pending file rename reboots.</span></span> |
| <span data-ttu-id="eab0a-132">SkipCcmClientSDK</span><span class="sxs-lookup"><span data-stu-id="eab0a-132">SkipCcmClientSDK</span></span> | <span data-ttu-id="eab0a-133">Пропускать перезагрузки, активируемые клиентами Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="eab0a-133">Skip reboots triggered by the ConfigMgr client.</span></span> |
| <span data-ttu-id="eab0a-134">SkipComputerRename</span><span class="sxs-lookup"><span data-stu-id="eab0a-134">SkipComputerRename</span></span> | <span data-ttu-id="eab0a-135">Пропускать перезагрузки, активируемые переименованием компьютера.</span><span class="sxs-lookup"><span data-stu-id="eab0a-135">Skip reboots triggered by Computer renames.</span></span> |
| <span data-ttu-id="eab0a-136">PSDSCRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="eab0a-136">PSDSCRunAsCredential</span></span> | <span data-ttu-id="eab0a-137">Поддерживается в версии 5.</span><span class="sxs-lookup"><span data-stu-id="eab0a-137">Supported in v5.</span></span> <span data-ttu-id="eab0a-138">Ресурс выполняется в контексте указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="eab0a-138">Executes the resource as the specified user.</span></span> |
| <span data-ttu-id="eab0a-139">DependsOn</span><span class="sxs-lookup"><span data-stu-id="eab0a-139">DependsOn</span></span> | <span data-ttu-id="eab0a-140">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="eab0a-140">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="eab0a-141">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — **ResourceName**, а его тип — **ResourceType**, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="eab0a-141">For example, if the ID of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> <span data-ttu-id="eab0a-142">Дополнительные сведения см. в разделе [Использование DependsOn](resource-depends-on.md).</span><span class="sxs-lookup"><span data-stu-id="eab0a-142">For more information, see [Using DependsOn](resource-depends-on.md)</span></span>|

## <a name="example"></a><span data-ttu-id="eab0a-143">Пример</span><span class="sxs-lookup"><span data-stu-id="eab0a-143">Example</span></span>

<span data-ttu-id="eab0a-144">В следующем примере Microsoft Exchange устанавливается с помощью ресурса [xExchange](https://github.com/PowerShell/xExchange).</span><span class="sxs-lookup"><span data-stu-id="eab0a-144">The following example installs Microsoft Exchange using the [xExchange](https://github.com/PowerShell/xExchange) resource.</span></span>
<span data-ttu-id="eab0a-145">На протяжении установки ресурс **PendingReboot** используется для перезагрузки узла.</span><span class="sxs-lookup"><span data-stu-id="eab0a-145">Throughout the install, the **PendingReboot** resource is used to reboot the Node.</span></span>

> [!NOTE]
> <span data-ttu-id="eab0a-146">В этом примере требуются учетные данные учетной записи, имеющей права на добавление сервера Exchange в лесе.</span><span class="sxs-lookup"><span data-stu-id="eab0a-146">This example requires the credential of an account that has rights to add an Exchange server to the forest.</span></span> <span data-ttu-id="eab0a-147">Дополнительные сведения об использовании учетных данных в DSC см. в разделе [Обработка учетных данных в DSC](../configurations/configDataCredentials.md).</span><span class="sxs-lookup"><span data-stu-id="eab0a-147">For more information on using credentials in DSC, see [Handling Credentials in DSC](../configurations/configDataCredentials.md)</span></span>

```powershell
$ConfigurationData = @{
    AllNodes = @(
        @{
            NodeName                    = '*'
            PSDSCAllowPlainTextPassword = $true
        },
        @{
            NodeName = 'DSCPULL-1'
        }
    )
}

Configuration Example
{
    param
    (
        [Parameter(Mandatory = $true)]
        [System.Management.Automation.PSCredential]
        $ExchangeAdminCredential
    )

    Import-DscResource -Module xExchange
    Import-DscResource -Module ComputerManagementDsc

    Node $AllNodes.NodeName
    {
        # Copy the Exchange setup files locally
        File ExchangeBinaries
        {
            Ensure          = 'Present'
            Type            = 'Directory'
            Recurse         = $true
            SourcePath      = '\\rras-1\Binaries\E15CU6'
            DestinationPath = 'C:\Binaries\E15CU6'
        }

        # Check if a reboot is needed before installing Exchange
        PendingReboot BeforeExchangeInstall
        {
            Name       = 'BeforeExchangeInstall'
            DependsOn  = '[File]ExchangeBinaries'
        }

        # Do the Exchange install
        xExchInstall InstallExchange
        {
            Path       = 'C:\Binaries\E15CU6\Setup.exe'
            Arguments  = '/mode:Install /role:Mailbox /Iacceptexchangeserverlicenseterms'
            Credential = $ExchangeAdminCredential
            DependsOn  = '[PendingReboot]BeforeExchangeInstall'
        }

        # See if a reboot is required after installing Exchange
        PendingReboot AfterExchangeInstall
        {
            Name      = 'AfterExchangeInstall'
            DependsOn = '[xExchInstall]InstallExchange'
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="eab0a-148">В этом примере предполагается, что вы настроили локальный диспетчер конфигураций, разрешив перезагрузки, и продолжили настройку после перезагрузки.</span><span class="sxs-lookup"><span data-stu-id="eab0a-148">This example assumes that you have configured your Local Configuration Manager to allow reboots and continue the configuration after a reboot.</span></span>

## <a name="where-to-download"></a><span data-ttu-id="eab0a-149">Где скачать</span><span class="sxs-lookup"><span data-stu-id="eab0a-149">Where to Download</span></span>

<span data-ttu-id="eab0a-150">Вы можете скачать ресурсы, используемые в этом разделе, в следующих расположениях или с помощью коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eab0a-150">You can download the resources used in this topic at the following locations, or by using the PowerShell gallery.</span></span>

- [<span data-ttu-id="eab0a-151">ComputerManagementDsc</span><span class="sxs-lookup"><span data-stu-id="eab0a-151">ComputerManagementDsc</span></span>](https://github.com/PowerShell/ComputerManagementDsc)
- [<span data-ttu-id="eab0a-152">xExchange</span><span class="sxs-lookup"><span data-stu-id="eab0a-152">xExchange</span></span>](https://github.com/PowerShell/xExchange)
