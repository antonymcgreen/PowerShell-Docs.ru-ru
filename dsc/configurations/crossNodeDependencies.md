---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Указание межузловых зависимостей
ms.openlocfilehash: 1bdfbd9f8a94809d6bf410eff525e1c877fb6aad
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402200"
---
# <a name="specifying-cross-node-dependencies"></a><span data-ttu-id="0424a-103">Указание межузловых зависимостей</span><span class="sxs-lookup"><span data-stu-id="0424a-103">Specifying cross-node dependencies</span></span>

> <span data-ttu-id="0424a-104">Область применения. Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="0424a-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="0424a-105">DSC предоставляет специальные ресурсы, **WaitForAll**, **WaitForAny** и **WaitForSome**, которые можно использовать в конфигурациях для указания зависимостей от конфигураций на других узлах.</span><span class="sxs-lookup"><span data-stu-id="0424a-105">DSC provides special resources, **WaitForAll**, **WaitForAny**, and **WaitForSome** that can be used in configurations to specify dependencies on configurations on other nodes.</span></span> <span data-ttu-id="0424a-106">Поведение этих ресурсов описано ниже.</span><span class="sxs-lookup"><span data-stu-id="0424a-106">The behavior of these resources is as follows:</span></span>

- <span data-ttu-id="0424a-107">**WaitForAll**: Выполняется успешно, если указанный ресурс находится в нужном состоянии на всех целевых узлах, определенных в **NodeName** свойство.</span><span class="sxs-lookup"><span data-stu-id="0424a-107">**WaitForAll**: Succeeds if the specified resource is in the desired state on all target nodes defined in the **NodeName** property.</span></span>
- <span data-ttu-id="0424a-108">**WaitForAny**: Выполняется успешно, если указанный ресурс находится в нужном состоянии на хотя бы один из целевых узлов, определенных в **NodeName** свойство.</span><span class="sxs-lookup"><span data-stu-id="0424a-108">**WaitForAny**: Succeeds if the specified resource is in the desired state on at least one of the target nodes defined in the **NodeName** property.</span></span>
- <span data-ttu-id="0424a-109">**WaitForSome**: Указывает **NodeCount** свойства в дополнение к **NodeName** свойство.</span><span class="sxs-lookup"><span data-stu-id="0424a-109">**WaitForSome**: Specifies a **NodeCount** property in addition to a **NodeName** property.</span></span> <span data-ttu-id="0424a-110">Ресурс выполняется успешно, если он находится в нужном состоянии на минимальном количестве узлов (определяется свойством **NodeCount**), заданных свойством **NodeName**.</span><span class="sxs-lookup"><span data-stu-id="0424a-110">The resource succeeds if the resource is in the desired state on a minimum number of nodes (specified by **NodeCount**) defined by the **NodeName** property.</span></span>

## <a name="syntax"></a><span data-ttu-id="0424a-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0424a-111">Syntax</span></span>

<span data-ttu-id="0424a-112">**WaitForAll** и **WaitForAny** ресурсы используют тот же синтаксис.</span><span class="sxs-lookup"><span data-stu-id="0424a-112">The **WaitForAll** and **WaitForAny** resources share the same syntax.</span></span> <span data-ttu-id="0424a-113">Замените \<ResourceType\> в примере ниже с помощью **WaitForAny** или **WaitForAll**.</span><span class="sxs-lookup"><span data-stu-id="0424a-113">Replace \<ResourceType\> in the example below with either **WaitForAny** or **WaitForAll**.</span></span>
<span data-ttu-id="0424a-114">Как и **DependsOn** ключевое слово, вам потребуется формата имени как «[ResourceType] ResourceName».</span><span class="sxs-lookup"><span data-stu-id="0424a-114">Like the **DependsOn** keyword, you will need to format the name as "[ResourceType]ResourceName".</span></span> <span data-ttu-id="0424a-115">Если ресурс относится к отдельным [конфигурации](configurations.md), включают **ConfigurationName** в форматируемую строку «[ResourceType] ResourceName:: [ConfigurationName]:: [ConfigurationName]».</span><span class="sxs-lookup"><span data-stu-id="0424a-115">If the resource belongs to a separate [Configuration](configurations.md), include the **ConfigurationName** in the formatted string "[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]".</span></span> <span data-ttu-id="0424a-116">**NodeName** компьютером, или узел, на котором нужно подождать текущего ресурса.</span><span class="sxs-lookup"><span data-stu-id="0424a-116">The **NodeName** is the computer, or Node, on which the current resource should wait.</span></span>

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

<span data-ttu-id="0424a-117">**WaitForSome** ресурсов имеет схожий синтаксис в приведенном выше примере, но добавляет **NodeCount** ключ.</span><span class="sxs-lookup"><span data-stu-id="0424a-117">The **WaitForSome** resource has a similar syntax to the example above, but adds the **NodeCount** key.</span></span> <span data-ttu-id="0424a-118">**NodeCount** указывает, сколько узлов, следует ожидать текущий ресурс.</span><span class="sxs-lookup"><span data-stu-id="0424a-118">The **NodeCount** indicates how many Nodes the current resource should wait on.</span></span>

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

<span data-ttu-id="0424a-119">Все **WaitForXXXX** совместно использовать следующие разделы синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="0424a-119">All **WaitForXXXX** share the following syntax keys.</span></span>

<span data-ttu-id="0424a-120">|  Свойство |  Описание || RetryIntervalSec | Количество секунд перед повторной попыткой.</span><span class="sxs-lookup"><span data-stu-id="0424a-120">|  Property  |  Description   | | RetryIntervalSec| The number of seconds before retrying.</span></span> <span data-ttu-id="0424a-121">Минимальное значение — 1. | | RetryCount | Максимальное число повторных попыток. | | ThrottleLimit | Количество одновременно подключаемых компьютеров.</span><span class="sxs-lookup"><span data-stu-id="0424a-121">Minimum is 1.| | RetryCount| The maximum number of times to retry.| | ThrottleLimit| Number of machines to connect simultaneously.</span></span> <span data-ttu-id="0424a-122">Значение по умолчанию — `New-CimSession` по умолчанию. | | DependsOn | Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="0424a-122">Default is `New-CimSession` default.| | DependsOn | Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="0424a-123">Дополнительные сведения см. в разделе [DependsOn](resource-depends-on.md)|| PsDscRunAsCredential | См. в разделе [с помощью DSC с учетными данными пользователя](./runAsUser.md) |</span><span class="sxs-lookup"><span data-stu-id="0424a-123">For more information, see [DependsOn](resource-depends-on.md)| | PsDscRunAsCredential | See [Using DSC with User Credentials](./runAsUser.md) |</span></span>


## <a name="using-waitforxxxx-resources"></a><span data-ttu-id="0424a-124">Использование ресурсов WaitForXXXX</span><span class="sxs-lookup"><span data-stu-id="0424a-124">Using WaitForXXXX resources</span></span>

<span data-ttu-id="0424a-125">Каждый **WaitForXXXX** ресурс ожидает указанные ресурсы для выполнения на указанном узле.</span><span class="sxs-lookup"><span data-stu-id="0424a-125">Each **WaitForXXXX** resource waits for the specified resources to complete on the specified Node.</span></span> <span data-ttu-id="0424a-126">Другие ресурсы в той же конфигурации можно затем *зависят от* **WaitForXXXX** ресурсов с помощью **DependsOn** ключ.</span><span class="sxs-lookup"><span data-stu-id="0424a-126">Other resources in the same Configuration can then *depend on* the **WaitForXXXX** resource using the **DependsOn** key.</span></span>

<span data-ttu-id="0424a-127">Например, в следующей конфигурации целевой узел ожидает завершения выполнения ресурса **xADDomain** на узле **MyDC** не более чем с 30 повторными попытками (с интервалом 15 секунд), прежде чем присоединиться к домену.</span><span class="sxs-lookup"><span data-stu-id="0424a-127">For example, in the following configuration, the target node is waiting for the **xADDomain** resource to finish on the **MyDC** node with maximum number of 30 retries, at 15-second intervals, before the target node can join the domain.</span></span>

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

<span data-ttu-id="0424a-128">При компиляции конфигурации создаются два MOF-файлы.</span><span class="sxs-lookup"><span data-stu-id="0424a-128">When you compile the Configuration, two ".mof" files are generated.</span></span> <span data-ttu-id="0424a-129">Применить оба MOF-файлы на целевые узлы с помощью [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) командлета</span><span class="sxs-lookup"><span data-stu-id="0424a-129">Apply both ".mof" files to the target Nodes using the [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet</span></span>

><span data-ttu-id="0424a-130">**Примечание**. По умолчанию WaitForXXX ресурсы одну попытку и далее завершаются со сбоем.</span><span class="sxs-lookup"><span data-stu-id="0424a-130">**Note:** By default the WaitForXXX resources try one time and then fail.</span></span> <span data-ttu-id="0424a-131">Несмотря на то, что это не обязательно, обычно требуется указать **RetryCount** и **RetryIntervalSec**.</span><span class="sxs-lookup"><span data-stu-id="0424a-131">Although it is not required, you will typically want to specify a **RetryCount** and **RetryIntervalSec**.</span></span>

## <a name="see-also"></a><span data-ttu-id="0424a-132">См. также</span><span class="sxs-lookup"><span data-stu-id="0424a-132">See Also</span></span>

- [<span data-ttu-id="0424a-133">Конфигурации DSC</span><span class="sxs-lookup"><span data-stu-id="0424a-133">DSC Configurations</span></span>](configurations.md)
- [<span data-ttu-id="0424a-134">Использовать зависимости ресурсов</span><span class="sxs-lookup"><span data-stu-id="0424a-134">Use Resource Dependencies</span></span>](resource-depends-on.md)
- [<span data-ttu-id="0424a-135">Ресурсы DSC</span><span class="sxs-lookup"><span data-stu-id="0424a-135">DSC Resources</span></span>](../resources/resources.md)
- [<span data-ttu-id="0424a-136">Настройка локального диспетчера конфигураций</span><span class="sxs-lookup"><span data-stu-id="0424a-136">Configuring The Local Configuration Manager</span></span>](../managing-nodes/metaConfig.md)
