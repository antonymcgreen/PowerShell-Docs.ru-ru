---
ms.date: 1/17/2019
keywords: dsc,powershell,конфигурация,установка
title: Перезагрузка узла
ms.openlocfilehash: 33ecd98aa62c3dc94a8ff2213fd3e68bf0c05cb7
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "55680744"
---
# <a name="reboot-a-node"></a><span data-ttu-id="26a89-103">Перезагрузка узла</span><span class="sxs-lookup"><span data-stu-id="26a89-103">Reboot a Node</span></span>

> [!NOTE]
> <span data-ttu-id="26a89-104">В этом разделе рассказывается о том, как перезагрузить узел.</span><span class="sxs-lookup"><span data-stu-id="26a89-104">This topic talks about how to reboot a Node.</span></span> <span data-ttu-id="26a89-105">В порядке для перезагрузки для успешной работы **ActionAfterReboot** и **RebootNodeIfNeeded** необходимо правильно настроить параметры локального диспетчера Конфигураций.</span><span class="sxs-lookup"><span data-stu-id="26a89-105">In order for the reboot to be successful the **ActionAfterReboot** and **RebootNodeIfNeeded** LCM settings need to be configured properly.</span></span>
> <span data-ttu-id="26a89-106">Чтобы прочитать о параметры локального диспетчера конфигураций, см. в разделе [настройки локального диспетчера конфигураций](../managing-nodes/metaConfig.md), или [настройки локального диспетчера конфигураций (версия 4)](../managing-nodes/metaConfig4.md).</span><span class="sxs-lookup"><span data-stu-id="26a89-106">To read about Local Configuration Manager settings, see [Configure the Local Configuration Manager](../managing-nodes/metaConfig.md), or [Configure the Local Configuration Manager (v4)](../managing-nodes/metaConfig4.md).</span></span>

<span data-ttu-id="26a89-107">Узлы можно перезагрузить из ресурса, с помощью `$global:DSCMachineStatus` флаг.</span><span class="sxs-lookup"><span data-stu-id="26a89-107">Nodes can be rebooted from within a resource, by using the `$global:DSCMachineStatus` flag.</span></span> <span data-ttu-id="26a89-108">Установка для этого флага `1` в `Set-TargetResource` функция принудительно выполняет LCM перепускать узел непосредственно после **задать** метод текущего ресурса.</span><span class="sxs-lookup"><span data-stu-id="26a89-108">Setting this flag to `1` in the `Set-TargetResource` function forces the LCM to reboot the Node directly after the **Set** method of the current resource.</span></span> <span data-ttu-id="26a89-109">С помощью этого флага **xPendingReboot** ресурсов обнаруживает, если ожидается перезагрузка за пределами DSC.</span><span class="sxs-lookup"><span data-stu-id="26a89-109">Using this flag, the **xPendingReboot** resource detects if a reboot is pending outside of DSC.</span></span>

<span data-ttu-id="26a89-110">Ваш [конфигураций](configurations.md) может выполнять действия, требующие перезагрузки узла.</span><span class="sxs-lookup"><span data-stu-id="26a89-110">Your [configurations](configurations.md) may perform steps that require the Node to reboot.</span></span> <span data-ttu-id="26a89-111">Сюда могут входить такие как вещи:</span><span class="sxs-lookup"><span data-stu-id="26a89-111">This could include things such as:</span></span>

- <span data-ttu-id="26a89-112">Windows: обновления</span><span class="sxs-lookup"><span data-stu-id="26a89-112">Windows updates</span></span>
- <span data-ttu-id="26a89-113">Установка программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="26a89-113">Software install</span></span>
- <span data-ttu-id="26a89-114">Переименовывает файл</span><span class="sxs-lookup"><span data-stu-id="26a89-114">File renames</span></span>
- <span data-ttu-id="26a89-115">Переименование компьютера</span><span class="sxs-lookup"><span data-stu-id="26a89-115">Computer rename</span></span>

<span data-ttu-id="26a89-116">**XPendingReboot** ресурс проверяет расположения конкретного компьютера, чтобы определить, если ожидается перезагрузка.</span><span class="sxs-lookup"><span data-stu-id="26a89-116">The **xPendingReboot** resource checks specific computer locations to determine if a reboot is pending.</span></span> <span data-ttu-id="26a89-117">Если узел требуется перезагрузка за пределами DSC, **xPendingReboot** наборов ресурсов `$global:DSCMachineStatus` флаг `1` Принудительная перезагрузка и устранению такого состояния ожидания.</span><span class="sxs-lookup"><span data-stu-id="26a89-117">If the Node requires a reboot outside of DSC, the **xPendingReboot** resource sets the `$global:DSCMachineStatus` flag to `1` forcing a reboot and resolving the pending condition.</span></span>

> [!NOTE]
> <span data-ttu-id="26a89-118">Любой ресурс DSC можно настроить LCM будет перезапустить узел, установив этот флаг в `Set-TargetResource` функции.</span><span class="sxs-lookup"><span data-stu-id="26a89-118">Any DSC resource can instruct the LCM to reboot the node by setting this flag in the `Set-TargetResource` function.</span></span> <span data-ttu-id="26a89-119">Дополнительные сведения см. в разделе [написание пользовательских ресурсов DSC с использованием MOF](../resources/authoringResourceMOF.md).</span><span class="sxs-lookup"><span data-stu-id="26a89-119">For more information, see [Writing a custom DSC resource with MOF](../resources/authoringResourceMOF.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="26a89-120">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="26a89-120">Syntax</span></span>

```
xPendingReboot [String] #ResourceName
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

## <a name="properties"></a><span data-ttu-id="26a89-121">Свойства</span><span class="sxs-lookup"><span data-stu-id="26a89-121">Properties</span></span>

| <span data-ttu-id="26a89-122">Свойство</span><span class="sxs-lookup"><span data-stu-id="26a89-122">Property</span></span> | <span data-ttu-id="26a89-123">Описание</span><span class="sxs-lookup"><span data-stu-id="26a89-123">Description</span></span> |
| --- | --- |
| <span data-ttu-id="26a89-124">Name</span><span class="sxs-lookup"><span data-stu-id="26a89-124">Name</span></span>| <span data-ttu-id="26a89-125">Обязательный параметр, который должен быть уникальным для каждого экземпляра ресурса в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="26a89-125">Required parameter that must be unique per instance of the resource within a configuration.</span></span>|
| <span data-ttu-id="26a89-126">SkipComponentBasedServicing</span><span class="sxs-lookup"><span data-stu-id="26a89-126">SkipComponentBasedServicing</span></span> | <span data-ttu-id="26a89-127">После перезагрузки Skip, активируемой компонентом Component-Based Servicing.</span><span class="sxs-lookup"><span data-stu-id="26a89-127">Skip reboots triggered by the Component-Based Servicing component.</span></span> |
| <span data-ttu-id="26a89-128">SkipWindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="26a89-128">SkipWindowsUpdate</span></span> | <span data-ttu-id="26a89-129">Пропустить перезагрузки инициируется обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="26a89-129">Skip reboots triggered by Windows Update.</span></span>|
| <span data-ttu-id="26a89-130">SkipPendingFileRename</span><span class="sxs-lookup"><span data-stu-id="26a89-130">SkipPendingFileRename</span></span> | <span data-ttu-id="26a89-131">Пропустить ожидающих файл переименование после перезагрузки.</span><span class="sxs-lookup"><span data-stu-id="26a89-131">Skip pending file rename reboots.</span></span> |
| <span data-ttu-id="26a89-132">SkipCcmClientSDK</span><span class="sxs-lookup"><span data-stu-id="26a89-132">SkipCcmClientSDK</span></span> | <span data-ttu-id="26a89-133">Пропустить перезагрузки инициируется клиента Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="26a89-133">Skip reboots triggered by the ConfigMgr client.</span></span> |
| <span data-ttu-id="26a89-134">SkipComputerRename</span><span class="sxs-lookup"><span data-stu-id="26a89-134">SkipComputerRename</span></span> | <span data-ttu-id="26a89-135">Пропустить перезагрузки активированное, переименования компьютера.</span><span class="sxs-lookup"><span data-stu-id="26a89-135">Skip reboots triggerd by Computer renames.</span></span> |
| <span data-ttu-id="26a89-136">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="26a89-136">PSDSCRunAsCredential</span></span> | <span data-ttu-id="26a89-137">Поддерживается в версии 5.</span><span class="sxs-lookup"><span data-stu-id="26a89-137">Supported in v5.</span></span> <span data-ttu-id="26a89-138">Ресурс выполняется в контексте указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="26a89-138">Executes the resource as the specified user.</span></span> |
| <span data-ttu-id="26a89-139">DependsOn</span><span class="sxs-lookup"><span data-stu-id="26a89-139">DependsOn</span></span> | <span data-ttu-id="26a89-140">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="26a89-140">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="26a89-141">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — **ResourceName**, а его тип — **ResourceType**, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="26a89-141">For example, if the ID of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> <span data-ttu-id="26a89-142">Дополнительные сведения см. в разделе [с помощью DependsOn](resource-depends-on.md)</span><span class="sxs-lookup"><span data-stu-id="26a89-142">For more information, see [Using DependsOn](resource-depends-on.md)</span></span>|

## <a name="example"></a><span data-ttu-id="26a89-143">Пример</span><span class="sxs-lookup"><span data-stu-id="26a89-143">Example</span></span>

<span data-ttu-id="26a89-144">В следующем примере устанавливаются с помощью Microsoft Exchange [xExchange](https://github.com/PowerShell/xExchange) ресурсов.</span><span class="sxs-lookup"><span data-stu-id="26a89-144">The following example installs Microsoft Exchange using the [xExchange](https://github.com/PowerShell/xExchange) resource.</span></span>
<span data-ttu-id="26a89-145">На протяжении установки **xPendingReboot** перепускать узел используется ресурс.</span><span class="sxs-lookup"><span data-stu-id="26a89-145">Throughout the install, the **xPendingReboot** resource is used to reboot the Node.</span></span>

> [!NOTE]
> <span data-ttu-id="26a89-146">В этом примере требуются учетные данные учетной записи, имеющей права на добавление сервера Exchange в лесу.</span><span class="sxs-lookup"><span data-stu-id="26a89-146">This example requires the credential of an account that has rights to add an Exchange server to the forest.</span></span> <span data-ttu-id="26a89-147">Дополнительные сведения об использовании учетных данных в DSC см. в разделе [обработка учетных данных в DSC](../configurations/configDataCredentials.md)</span><span class="sxs-lookup"><span data-stu-id="26a89-147">For more information on using credentials in DSC, see [Handling Credentials in DSC](../configurations/configDataCredentials.md)</span></span>

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
    Import-DscResource -Module xPendingReboot

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
        xPendingReboot BeforeExchangeInstall
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
            DependsOn  = '[xPendingReboot]BeforeExchangeInstall'
        }

        # See if a reboot is required after installing Exchange
        xPendingReboot AfterExchangeInstall
        {
            Name      = 'AfterExchangeInstall'
            DependsOn = '[xExchInstall]InstallExchange'
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="26a89-148">В этом примере предполагается, что вы настроили локальный диспетчер конфигураций для разрешения перезагрузок и продолжить настройку после перезагрузки.</span><span class="sxs-lookup"><span data-stu-id="26a89-148">This example assumes that you have configured your Local Configuration Manager to allow reboots and continue the configuration after a reboot.</span></span>

## <a name="where-to-download"></a><span data-ttu-id="26a89-149">Где можно скачать</span><span class="sxs-lookup"><span data-stu-id="26a89-149">Where to Download</span></span>

<span data-ttu-id="26a89-150">Вы можете загрузить ресурсы, используемые в этом разделе, в следующих расположениях, или с помощью коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="26a89-150">You can download the resources used in this topic at the following locations, or by using the PowerShell gallery.</span></span>

- [<span data-ttu-id="26a89-151">xPendingReboot</span><span class="sxs-lookup"><span data-stu-id="26a89-151">xPendingReboot</span></span>](https://github.com/PowerShell/xPendingReboot)
- [<span data-ttu-id="26a89-152">xExchange</span><span class="sxs-lookup"><span data-stu-id="26a89-152">xExchange</span></span>](https://github.com/PowerShell/xExchange)
