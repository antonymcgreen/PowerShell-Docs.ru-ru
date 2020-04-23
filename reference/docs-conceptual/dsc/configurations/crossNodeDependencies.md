---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Указание межузловых зависимостей
ms.openlocfilehash: 62e553d894897ae1908745c2788b7b7b9cbe50ff
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "71954111"
---
# <a name="specifying-cross-node-dependencies"></a><span data-ttu-id="c70d5-103">Указание межузловых зависимостей</span><span class="sxs-lookup"><span data-stu-id="c70d5-103">Specifying cross-node dependencies</span></span>

> <span data-ttu-id="c70d5-104">Область применения: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="c70d5-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="c70d5-105">DSC предоставляет специальные ресурсы, **WaitForAll**, **WaitForAny** и **WaitForSome**, которые можно использовать в конфигурациях для указания зависимостей от конфигураций на других узлах.</span><span class="sxs-lookup"><span data-stu-id="c70d5-105">DSC provides special resources, **WaitForAll**, **WaitForAny**, and **WaitForSome** that can be used in configurations to specify dependencies on configurations on other nodes.</span></span> <span data-ttu-id="c70d5-106">Поведение этих ресурсов описано ниже.</span><span class="sxs-lookup"><span data-stu-id="c70d5-106">The behavior of these resources is as follows:</span></span>

- <span data-ttu-id="c70d5-107">**WaitForAll** — успешное выполнение, если указанный ресурс находится в нужном состоянии на всех целевых узлах, определенных в свойстве **NodeName**.</span><span class="sxs-lookup"><span data-stu-id="c70d5-107">**WaitForAll**: Succeeds if the specified resource is in the desired state on all target nodes defined in the **NodeName** property.</span></span>
- <span data-ttu-id="c70d5-108">**WaitForAny** — успешное выполнение, если указанный ресурс находится в нужном состоянии как минимум на одном из целевых узлов, определенных в свойстве **NodeName**.</span><span class="sxs-lookup"><span data-stu-id="c70d5-108">**WaitForAny**: Succeeds if the specified resource is in the desired state on at least one of the target nodes defined in the **NodeName** property.</span></span>
- <span data-ttu-id="c70d5-109">**WaitForSome** — указывает свойство **NodeCount** в дополнение к свойству **NodeName**.</span><span class="sxs-lookup"><span data-stu-id="c70d5-109">**WaitForSome**: Specifies a **NodeCount** property in addition to a **NodeName** property.</span></span> <span data-ttu-id="c70d5-110">Ресурс выполняется успешно, если он находится в нужном состоянии на минимальном количестве узлов (определяется свойством **NodeCount**), заданных свойством **NodeName**.</span><span class="sxs-lookup"><span data-stu-id="c70d5-110">The resource succeeds if the resource is in the desired state on a minimum number of nodes (specified by **NodeCount**) defined by the **NodeName** property.</span></span>

## <a name="syntax"></a><span data-ttu-id="c70d5-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c70d5-111">Syntax</span></span>

<span data-ttu-id="c70d5-112">Ресурсы **WaitForAll** и **WaitForAny** используют одинаковый синтаксис.</span><span class="sxs-lookup"><span data-stu-id="c70d5-112">The **WaitForAll** and **WaitForAny** resources share the same syntax.</span></span> <span data-ttu-id="c70d5-113">Замените \<ResourceType\> в примере ниже на **WaitForAny** или **WaitForAll**.</span><span class="sxs-lookup"><span data-stu-id="c70d5-113">Replace \<ResourceType\> in the example below with either **WaitForAny** or **WaitForAll**.</span></span>
<span data-ttu-id="c70d5-114">Необходимо отформатировать имя [ResourceType]ResourceName подобно ключевому слову **DependsOn**.</span><span class="sxs-lookup"><span data-stu-id="c70d5-114">Like the **DependsOn** keyword, you will need to format the name as "[ResourceType]ResourceName".</span></span> <span data-ttu-id="c70d5-115">Если ресурс принадлежит отдельной [конфигурации](configurations.md), включите **ConfigurationName** в отформатированную строку [ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName].</span><span class="sxs-lookup"><span data-stu-id="c70d5-115">If the resource belongs to a separate [Configuration](configurations.md), include the **ConfigurationName** in the formatted string "[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]".</span></span> <span data-ttu-id="c70d5-116">**NodeName** является компьютером или узлом, на котором ожидается текущий ресурс.</span><span class="sxs-lookup"><span data-stu-id="c70d5-116">The **NodeName** is the computer, or Node, on which the current resource should wait.</span></span>

```
<ResourceType> [string] #ResourceName
{
    ResourceName = [string]
    NodeName = [string]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential]]
    [ RetryCount = [Uint32] ]
    [ RetryIntervalSec = [Uint64] ]
    [ ThrottleLimit = [Uint32]]
}
```

<span data-ttu-id="c70d5-117">Ресурс **WaitForSome** имеет подобный приведенному выше примеру синтаксис, но содержит ключ **NodeCount**.</span><span class="sxs-lookup"><span data-stu-id="c70d5-117">The **WaitForSome** resource has a similar syntax to the example above, but adds the **NodeCount** key.</span></span> <span data-ttu-id="c70d5-118">Ключ **NodeCount** указывает количество узлов, на которых следует ожидать текущий ресурс.</span><span class="sxs-lookup"><span data-stu-id="c70d5-118">The **NodeCount** indicates how many Nodes the current resource should wait on.</span></span>

```
WaitForSome [String] #ResourceName
{
    NodeCount = [UInt32]
    NodeName = [string[]]
    ResourceName = [string]
    [DependsOn = [string[]]]
    [PsDscRunAsCredential = [PSCredential]]
    [RetryCount = [UInt32]]
    [RetryIntervalSec = [UInt64]]
    [ThrottleLimit = [UInt32]]
}
```

<span data-ttu-id="c70d5-119">Все ресурсы **WaitForXXXX** используют следующие разделы синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="c70d5-119">All **WaitForXXXX** share the following syntax keys.</span></span>

|<span data-ttu-id="c70d5-120">Свойство</span><span class="sxs-lookup"><span data-stu-id="c70d5-120">Property</span></span>|  <span data-ttu-id="c70d5-121">Description</span><span class="sxs-lookup"><span data-stu-id="c70d5-121">Description</span></span>   |
|---------|---------------------|
| <span data-ttu-id="c70d5-122">RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="c70d5-122">RetryIntervalSec</span></span>| <span data-ttu-id="c70d5-123">Количество секунд перед повторной попыткой.</span><span class="sxs-lookup"><span data-stu-id="c70d5-123">The number of seconds before retrying.</span></span> <span data-ttu-id="c70d5-124">Минимальное значение — 1.</span><span class="sxs-lookup"><span data-stu-id="c70d5-124">Minimum is 1.</span></span>|
| <span data-ttu-id="c70d5-125">RetryCount</span><span class="sxs-lookup"><span data-stu-id="c70d5-125">RetryCount</span></span>| <span data-ttu-id="c70d5-126">Максимальное число повторных попыток.</span><span class="sxs-lookup"><span data-stu-id="c70d5-126">The maximum number of times to retry.</span></span>|
| <span data-ttu-id="c70d5-127">ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="c70d5-127">ThrottleLimit</span></span>| <span data-ttu-id="c70d5-128">Количество одновременно подключаемых компьютеров.</span><span class="sxs-lookup"><span data-stu-id="c70d5-128">Number of machines to connect simultaneously.</span></span> <span data-ttu-id="c70d5-129">Значение по умолчанию — `New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="c70d5-129">Default is `New-CimSession` default.</span></span>|
| <span data-ttu-id="c70d5-130">DependsOn</span><span class="sxs-lookup"><span data-stu-id="c70d5-130">DependsOn</span></span> | <span data-ttu-id="c70d5-131">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="c70d5-131">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="c70d5-132">Дополнительные сведения см. в разделе [DependsOn](resource-depends-on.md).</span><span class="sxs-lookup"><span data-stu-id="c70d5-132">For more information, see [DependsOn](resource-depends-on.md)</span></span>|
| <span data-ttu-id="c70d5-133">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="c70d5-133">PsDscRunAsCredential</span></span> | <span data-ttu-id="c70d5-134">См. статью [Запуск DSC с учетными данными пользователя](./runAsUser.md).</span><span class="sxs-lookup"><span data-stu-id="c70d5-134">See [Using DSC with User Credentials](./runAsUser.md)</span></span> |

## <a name="using-waitforxxxx-resources"></a><span data-ttu-id="c70d5-135">Использование ресурсов WaitForXXXX</span><span class="sxs-lookup"><span data-stu-id="c70d5-135">Using WaitForXXXX resources</span></span>

<span data-ttu-id="c70d5-136">Каждый ресурс **WaitForXXXX** ожидает выполнения указанных ресурсов на указанном узле.</span><span class="sxs-lookup"><span data-stu-id="c70d5-136">Each **WaitForXXXX** resource waits for the specified resources to complete on the specified Node.</span></span>
<span data-ttu-id="c70d5-137">После этого другие ресурсы в той же конфигурации могут *зависеть от* ресурса **WaitForXXXX** с помощью ключа **DependsOn**.</span><span class="sxs-lookup"><span data-stu-id="c70d5-137">Other resources in the same Configuration can then *depend on* the **WaitForXXXX** resource using the **DependsOn** key.</span></span>

<span data-ttu-id="c70d5-138">Например, в следующей конфигурации целевой узел ожидает завершения выполнения ресурса **xADDomain** на узле **MyDC** не более чем с 30 повторными попытками (с интервалом 15 секунд), прежде чем присоединиться к домену.</span><span class="sxs-lookup"><span data-stu-id="c70d5-138">For example, in the following configuration, the target node is waiting for the **xADDomain** resource to finish on the **MyDC** node with maximum number of 30 retries, at 15-second intervals, before the target node can join the domain.</span></span>

<span data-ttu-id="c70d5-139">По умолчанию ресурсы **WaitForXXX** выполняют одну попытку, а затем выдают ошибку.</span><span class="sxs-lookup"><span data-stu-id="c70d5-139">By default the **WaitForXXX** resources try one time and then fail.</span></span> <span data-ttu-id="c70d5-140">Хотя это необязательно, обычно требуется указать **RetryCount** и **RetryIntervalSec**.</span><span class="sxs-lookup"><span data-stu-id="c70d5-140">Although it is not required, you will typically want to specify a **RetryCount** and **RetryIntervalSec**.</span></span>

```powershell
Configuration JoinDomain
{
    Import-DscResource -Module xComputerManagement, xActiveDirectory

    Node myDC
    {
        WindowsFeature InstallAD
        {
            Ensure = 'Present'
            Name = 'AD-Domain-Services'
        }

        xADDomain NewDomain
        {
            DomainName = 'Contoso.com'
            DomainAdministratorCredential = (Get-Credential)
            SafemodeAdministratorPassword = (Get-Credential)
            DatabasePath = "C:\Windows\NTDS"
            LogPath = "C:\Windows\NTDS"
            SysvolPath = "C:\Windows\Sysvol"
        }
    }

    Node myDomainJoinedServer
    {
        WaitForAll DC
        {
            ResourceName      = '[xADDomain]NewDomain'
            NodeName          = 'MyDC'
            RetryIntervalSec  = 15
            RetryCount        = 30
        }

        xComputer JoinDomain
        {
            Name             = 'myPC'
            DomainName       = 'Contoso.com'
            Credential       = (Get-Credential)
            DependsOn        ='[WaitForAll]DC'
        }
    }
}
```

<span data-ttu-id="c70d5-141">При компиляции конфигурации создаются два MOF-файла.</span><span class="sxs-lookup"><span data-stu-id="c70d5-141">When you compile the Configuration, two ".mof" files are generated.</span></span> <span data-ttu-id="c70d5-142">Примените их на целевые узлы с помощью командлета [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration)</span><span class="sxs-lookup"><span data-stu-id="c70d5-142">Apply both ".mof" files to the target Nodes using the [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet</span></span>

> [!NOTE]
> <span data-ttu-id="c70d5-143">Ресурсы **WaitForXXX** используют удаленное управление Windows, чтобы проверить состояние других узлов.</span><span class="sxs-lookup"><span data-stu-id="c70d5-143">**WaitForXXX** resources use Windows Remote Management to check the state of other Nodes.</span></span>
> <span data-ttu-id="c70d5-144">Дополнительные сведения о требованиях к безопасности и портах для WinRM см. в разделе [Вопросы обеспечения безопасности удаленного взаимодействия PowerShell](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6).</span><span class="sxs-lookup"><span data-stu-id="c70d5-144">For more information about port and security requirements for WinRM, see [PowerShell Remoting Security Considerations](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6).</span></span>

## <a name="see-also"></a><span data-ttu-id="c70d5-145">См. также:</span><span class="sxs-lookup"><span data-stu-id="c70d5-145">See Also</span></span>

- [<span data-ttu-id="c70d5-146">Конфигурации DSC</span><span class="sxs-lookup"><span data-stu-id="c70d5-146">DSC Configurations</span></span>](configurations.md)
- [<span data-ttu-id="c70d5-147">Использование зависимостей ресурсов с DependsOn</span><span class="sxs-lookup"><span data-stu-id="c70d5-147">Use Resource Dependencies</span></span>](resource-depends-on.md)
- [<span data-ttu-id="c70d5-148">Ресурсы DSC</span><span class="sxs-lookup"><span data-stu-id="c70d5-148">DSC Resources</span></span>](../resources/resources.md)
- [<span data-ttu-id="c70d5-149">Настройка локального диспетчера конфигураций</span><span class="sxs-lookup"><span data-stu-id="c70d5-149">Configuring The Local Configuration Manager</span></span>](../managing-nodes/metaConfig.md)
