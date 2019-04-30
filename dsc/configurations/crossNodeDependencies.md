---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Указание межузловых зависимостей
ms.openlocfilehash: 1bdfbd9f8a94809d6bf410eff525e1c877fb6aad
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62080209"
---
# <a name="specifying-cross-node-dependencies"></a><span data-ttu-id="6c111-103">Указание межузловых зависимостей</span><span class="sxs-lookup"><span data-stu-id="6c111-103">Specifying cross-node dependencies</span></span>

> <span data-ttu-id="6c111-104">Область применения. Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="6c111-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="6c111-105">DSC предоставляет специальные ресурсы, **WaitForAll**, **WaitForAny** и **WaitForSome**, которые можно использовать в конфигурациях для указания зависимостей от конфигураций на других узлах.</span><span class="sxs-lookup"><span data-stu-id="6c111-105">DSC provides special resources, **WaitForAll**, **WaitForAny**, and **WaitForSome** that can be used in configurations to specify dependencies on configurations on other nodes.</span></span> <span data-ttu-id="6c111-106">Поведение этих ресурсов описано ниже.</span><span class="sxs-lookup"><span data-stu-id="6c111-106">The behavior of these resources is as follows:</span></span>

- <span data-ttu-id="6c111-107">**WaitForAll**. Успешное выполнение, если указанный ресурс находится в нужном состоянии на всех целевых узлах, определенных в свойстве **NodeName**.</span><span class="sxs-lookup"><span data-stu-id="6c111-107">**WaitForAll**: Succeeds if the specified resource is in the desired state on all target nodes defined in the **NodeName** property.</span></span>
- <span data-ttu-id="6c111-108">**WaitForAny**. Успешное выполнение, если указанный ресурс находится в нужном состоянии как минимум на одном из целевых узлов, определенных в свойстве **NodeName**.</span><span class="sxs-lookup"><span data-stu-id="6c111-108">**WaitForAny**: Succeeds if the specified resource is in the desired state on at least one of the target nodes defined in the **NodeName** property.</span></span>
- <span data-ttu-id="6c111-109">**WaitForSome**. Указывает свойство **NodeCount** в дополнение к свойству **NodeName**.</span><span class="sxs-lookup"><span data-stu-id="6c111-109">**WaitForSome**: Specifies a **NodeCount** property in addition to a **NodeName** property.</span></span> <span data-ttu-id="6c111-110">Ресурс выполняется успешно, если он находится в нужном состоянии на минимальном количестве узлов (определяется свойством **NodeCount**), заданных свойством **NodeName**.</span><span class="sxs-lookup"><span data-stu-id="6c111-110">The resource succeeds if the resource is in the desired state on a minimum number of nodes (specified by **NodeCount**) defined by the **NodeName** property.</span></span>

## <a name="syntax"></a><span data-ttu-id="6c111-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c111-111">Syntax</span></span>

<span data-ttu-id="6c111-112">Ресурсы **WaitForAll** и **WaitForAny** используют одинаковый синтаксис.</span><span class="sxs-lookup"><span data-stu-id="6c111-112">The **WaitForAll** and **WaitForAny** resources share the same syntax.</span></span> <span data-ttu-id="6c111-113">Замените \<ResourceType\> в примере ниже на **WaitForAny** или **WaitForAll**.</span><span class="sxs-lookup"><span data-stu-id="6c111-113">Replace \<ResourceType\> in the example below with either **WaitForAny** or **WaitForAll**.</span></span>
<span data-ttu-id="6c111-114">Необходимо отформатировать имя [ResourceType]ResourceName подобно ключевому слову **DependsOn**.</span><span class="sxs-lookup"><span data-stu-id="6c111-114">Like the **DependsOn** keyword, you will need to format the name as "[ResourceType]ResourceName".</span></span> <span data-ttu-id="6c111-115">Если ресурс принадлежит отдельной [конфигурации](configurations.md), включите **ConfigurationName** в отформатированную строку [ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName].</span><span class="sxs-lookup"><span data-stu-id="6c111-115">If the resource belongs to a separate [Configuration](configurations.md), include the **ConfigurationName** in the formatted string "[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]".</span></span> <span data-ttu-id="6c111-116">**NodeName** является компьютером или узлом, на котором ожидается текущий ресурс.</span><span class="sxs-lookup"><span data-stu-id="6c111-116">The **NodeName** is the computer, or Node, on which the current resource should wait.</span></span>

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

<span data-ttu-id="6c111-117">Ресурс **WaitForSome** имеет подобный приведенному выше примеру синтаксис, но содержит ключ **NodeCount**.</span><span class="sxs-lookup"><span data-stu-id="6c111-117">The **WaitForSome** resource has a similar syntax to the example above, but adds the **NodeCount** key.</span></span> <span data-ttu-id="6c111-118">Ключ **NodeCount** указывает количество узлов, на которых следует ожидать текущий ресурс.</span><span class="sxs-lookup"><span data-stu-id="6c111-118">The **NodeCount** indicates how many Nodes the current resource should wait on.</span></span>

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

<span data-ttu-id="6c111-119">Все ресурсы **WaitForXXXX** используют следующие разделы синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="6c111-119">All **WaitForXXXX** share the following syntax keys.</span></span>

<span data-ttu-id="6c111-120">| Свойство | Описание | | RetryIntervalSec| Количество секунд перед повторной попыткой.</span><span class="sxs-lookup"><span data-stu-id="6c111-120">|  Property  |  Description   | | RetryIntervalSec| The number of seconds before retrying.</span></span> <span data-ttu-id="6c111-121">Минимальное значение — 1.| | RetryCount| Максимальное число повторных попыток.| | ThrottleLimit| Количество одновременно подключаемых компьютеров.</span><span class="sxs-lookup"><span data-stu-id="6c111-121">Minimum is 1.| | RetryCount| The maximum number of times to retry.| | ThrottleLimit| Number of machines to connect simultaneously.</span></span> <span data-ttu-id="6c111-122">Значение по умолчанию — `New-CimSession`.| | DependsOn | Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="6c111-122">Default is `New-CimSession` default.| | DependsOn | Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="6c111-123">Дополнительные сведения см. в статье [Использование зависимостей ресурсов с DependsOn](resource-depends-on.md)| | PsDscRunAsCredential | См. в статье [Использование учетных данных с ресурсами DSC](./runAsUser.md) |</span><span class="sxs-lookup"><span data-stu-id="6c111-123">For more information, see [DependsOn](resource-depends-on.md)| | PsDscRunAsCredential | See [Using DSC with User Credentials](./runAsUser.md) |</span></span>


## <a name="using-waitforxxxx-resources"></a><span data-ttu-id="6c111-124">Использование ресурсов WaitForXXXX</span><span class="sxs-lookup"><span data-stu-id="6c111-124">Using WaitForXXXX resources</span></span>

<span data-ttu-id="6c111-125">Каждый ресурс **WaitForXXXX** ожидает выполнения указанных ресурсов на указанном узле.</span><span class="sxs-lookup"><span data-stu-id="6c111-125">Each **WaitForXXXX** resource waits for the specified resources to complete on the specified Node.</span></span> <span data-ttu-id="6c111-126">После этого другие ресурсы в той же конфигурации могут *зависеть от* ресурса **WaitForXXXX** с помощью ключа **DependsOn**.</span><span class="sxs-lookup"><span data-stu-id="6c111-126">Other resources in the same Configuration can then *depend on* the **WaitForXXXX** resource using the **DependsOn** key.</span></span>

<span data-ttu-id="6c111-127">Например, в следующей конфигурации целевой узел ожидает завершения выполнения ресурса **xADDomain** на узле **MyDC** не более чем с 30 повторными попытками (с интервалом 15 секунд), прежде чем присоединиться к домену.</span><span class="sxs-lookup"><span data-stu-id="6c111-127">For example, in the following configuration, the target node is waiting for the **xADDomain** resource to finish on the **MyDC** node with maximum number of 30 retries, at 15-second intervals, before the target node can join the domain.</span></span>

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

<span data-ttu-id="6c111-128">При компиляции конфигурации создаются два MOF-файла.</span><span class="sxs-lookup"><span data-stu-id="6c111-128">When you compile the Configuration, two ".mof" files are generated.</span></span> <span data-ttu-id="6c111-129">Примените их на целевые узлы с помощью командлета [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration)</span><span class="sxs-lookup"><span data-stu-id="6c111-129">Apply both ".mof" files to the target Nodes using the [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet</span></span>

><span data-ttu-id="6c111-130">**Примечание**. По умолчанию ресурсы WaitForXXX выполняют одну попытку, а затем выдают ошибку.</span><span class="sxs-lookup"><span data-stu-id="6c111-130">**Note:** By default the WaitForXXX resources try one time and then fail.</span></span> <span data-ttu-id="6c111-131">Хотя это необязательно, обычно требуется указать **RetryCount** и **RetryIntervalSec**.</span><span class="sxs-lookup"><span data-stu-id="6c111-131">Although it is not required, you will typically want to specify a **RetryCount** and **RetryIntervalSec**.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c111-132">См. также</span><span class="sxs-lookup"><span data-stu-id="6c111-132">See Also</span></span>

- [<span data-ttu-id="6c111-133">Конфигурации DSC</span><span class="sxs-lookup"><span data-stu-id="6c111-133">DSC Configurations</span></span>](configurations.md)
- [<span data-ttu-id="6c111-134">Использование зависимостей ресурсов с DependsOn</span><span class="sxs-lookup"><span data-stu-id="6c111-134">Use Resource Dependencies</span></span>](resource-depends-on.md)
- [<span data-ttu-id="6c111-135">Ресурсы DSC</span><span class="sxs-lookup"><span data-stu-id="6c111-135">DSC Resources</span></span>](../resources/resources.md)
- [<span data-ttu-id="6c111-136">Настройка локального диспетчера конфигураций</span><span class="sxs-lookup"><span data-stu-id="6c111-136">Configuring The Local Configuration Manager</span></span>](../managing-nodes/metaConfig.md)
