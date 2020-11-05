---
ms.date: 12/12/2018
keywords: dsc,powershell,конфигурация,установка
title: Указание межузловых зависимостей
description: DSC предоставляет специальные ресурсы, которые используются в конфигурациях для указания зависимостей от конфигураций на других узлах.
ms.openlocfilehash: a9fc09af922839b37db476c24c113efc5e3e8cb1
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92658503"
---
# <a name="specifying-cross-node-dependencies"></a><span data-ttu-id="57a97-104">Указание межузловых зависимостей</span><span class="sxs-lookup"><span data-stu-id="57a97-104">Specifying cross-node dependencies</span></span>

> <span data-ttu-id="57a97-105">Область применения: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="57a97-105">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="57a97-106">DSC предоставляет специальные ресурсы, **WaitForAll** , **WaitForAny** и **WaitForSome** , которые можно использовать в конфигурациях для указания зависимостей от конфигураций на других узлах.</span><span class="sxs-lookup"><span data-stu-id="57a97-106">DSC provides special resources, **WaitForAll** , **WaitForAny** , and **WaitForSome** that can be used in configurations to specify dependencies on configurations on other nodes.</span></span> <span data-ttu-id="57a97-107">Поведение этих ресурсов описано ниже.</span><span class="sxs-lookup"><span data-stu-id="57a97-107">The behavior of these resources is as follows:</span></span>

- <span data-ttu-id="57a97-108">**WaitForAll**  — успешное выполнение, если указанный ресурс находится в нужном состоянии на всех целевых узлах, определенных в свойстве **NodeName**.</span><span class="sxs-lookup"><span data-stu-id="57a97-108">**WaitForAll** : Succeeds if the specified resource is in the desired state on all target nodes defined in the **NodeName** property.</span></span>
- <span data-ttu-id="57a97-109">**WaitForAny**  — успешное выполнение, если указанный ресурс находится в нужном состоянии как минимум на одном из целевых узлов, определенных в свойстве **NodeName**.</span><span class="sxs-lookup"><span data-stu-id="57a97-109">**WaitForAny** : Succeeds if the specified resource is in the desired state on at least one of the target nodes defined in the **NodeName** property.</span></span>
- <span data-ttu-id="57a97-110">**WaitForSome**  — указывает свойство **NodeCount** в дополнение к свойству **NodeName**.</span><span class="sxs-lookup"><span data-stu-id="57a97-110">**WaitForSome** : Specifies a **NodeCount** property in addition to a **NodeName** property.</span></span> <span data-ttu-id="57a97-111">Ресурс выполняется успешно, если он находится в нужном состоянии на минимальном количестве узлов (определяется свойством **NodeCount** ), заданных свойством **NodeName**.</span><span class="sxs-lookup"><span data-stu-id="57a97-111">The resource succeeds if the resource is in the desired state on a minimum number of nodes (specified by **NodeCount** ) defined by the **NodeName** property.</span></span>

## <a name="syntax"></a><span data-ttu-id="57a97-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="57a97-112">Syntax</span></span>

<span data-ttu-id="57a97-113">Ресурсы **WaitForAll** и **WaitForAny** используют одинаковый синтаксис.</span><span class="sxs-lookup"><span data-stu-id="57a97-113">The **WaitForAll** and **WaitForAny** resources share the same syntax.</span></span> <span data-ttu-id="57a97-114">Замените `<ResourceType>` в примере ниже на **WaitForAny** или **WaitForAll**.</span><span class="sxs-lookup"><span data-stu-id="57a97-114">Replace `<ResourceType>` in the example below with either **WaitForAny** or **WaitForAll**.</span></span> <span data-ttu-id="57a97-115">Необходимо отформатировать имя как `[ResourceType]ResourceName` подобно ключевому слову **DependsOn**.</span><span class="sxs-lookup"><span data-stu-id="57a97-115">Like the **DependsOn** keyword, you will need to format the name as `[ResourceType]ResourceName`.</span></span> <span data-ttu-id="57a97-116">Если ресурс принадлежит отдельной [конфигурации](configurations.md), включите **ConfigurationName** в отформатированную строку `[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]`.</span><span class="sxs-lookup"><span data-stu-id="57a97-116">If the resource belongs to a separate [Configuration](configurations.md), include the **ConfigurationName** in the formatted string `[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]`.</span></span> <span data-ttu-id="57a97-117">**NodeName** является компьютером или узлом, на котором ожидается текущий ресурс.</span><span class="sxs-lookup"><span data-stu-id="57a97-117">The **NodeName** is the computer, or Node, on which the current resource should wait.</span></span>

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

<span data-ttu-id="57a97-118">Ресурс **WaitForSome** имеет подобный приведенному выше примеру синтаксис, но содержит ключ **NodeCount**.</span><span class="sxs-lookup"><span data-stu-id="57a97-118">The **WaitForSome** resource has a similar syntax to the example above, but adds the **NodeCount** key.</span></span> <span data-ttu-id="57a97-119">Ключ **NodeCount** указывает количество узлов, на которых следует ожидать текущий ресурс.</span><span class="sxs-lookup"><span data-stu-id="57a97-119">The **NodeCount** indicates how many Nodes the current resource should wait on.</span></span>

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

<span data-ttu-id="57a97-120">Все ресурсы **WaitForXXXX** используют следующие разделы синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="57a97-120">All **WaitForXXXX** share the following syntax keys.</span></span>

|       <span data-ttu-id="57a97-121">Свойство.</span><span class="sxs-lookup"><span data-stu-id="57a97-121">Property</span></span>       |                                                                           <span data-ttu-id="57a97-122">Описание</span><span class="sxs-lookup"><span data-stu-id="57a97-122">Description</span></span>                                                                           |
| -------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="57a97-123">RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="57a97-123">RetryIntervalSec</span></span>     | <span data-ttu-id="57a97-124">Количество секунд перед повторной попыткой.</span><span class="sxs-lookup"><span data-stu-id="57a97-124">The number of seconds before retrying.</span></span> <span data-ttu-id="57a97-125">Минимальное значение — 1.</span><span class="sxs-lookup"><span data-stu-id="57a97-125">Minimum is 1.</span></span>                                                                                                            |
| <span data-ttu-id="57a97-126">RetryCount</span><span class="sxs-lookup"><span data-stu-id="57a97-126">RetryCount</span></span>           | <span data-ttu-id="57a97-127">Максимальное число повторных попыток.</span><span class="sxs-lookup"><span data-stu-id="57a97-127">The maximum number of times to retry.</span></span>                                                                                                                           |
| <span data-ttu-id="57a97-128">ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="57a97-128">ThrottleLimit</span></span>        | <span data-ttu-id="57a97-129">Количество одновременно подключаемых компьютеров.</span><span class="sxs-lookup"><span data-stu-id="57a97-129">Number of machines to connect simultaneously.</span></span> <span data-ttu-id="57a97-130">Значение по умолчанию — `New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="57a97-130">Default is `New-CimSession` default.</span></span>                                                                              |
| <span data-ttu-id="57a97-131">DependsOn</span><span class="sxs-lookup"><span data-stu-id="57a97-131">DependsOn</span></span>            | <span data-ttu-id="57a97-132">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="57a97-132">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="57a97-133">Дополнительные сведения см. в разделе [DependsOn](resource-depends-on.md).</span><span class="sxs-lookup"><span data-stu-id="57a97-133">For more information, see [DependsOn](resource-depends-on.md)</span></span> |
| <span data-ttu-id="57a97-134">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="57a97-134">PsDscRunAsCredential</span></span> | <span data-ttu-id="57a97-135">См. статью [Запуск DSC с учетными данными пользователя](./runAsUser.md).</span><span class="sxs-lookup"><span data-stu-id="57a97-135">See [Using DSC with User Credentials](./runAsUser.md)</span></span>                                                                                                           |

## <a name="using-waitforxxxx-resources"></a><span data-ttu-id="57a97-136">Использование ресурсов WaitForXXXX</span><span class="sxs-lookup"><span data-stu-id="57a97-136">Using WaitForXXXX resources</span></span>

<span data-ttu-id="57a97-137">Каждый ресурс **WaitForXXXX** ожидает выполнения указанных ресурсов на указанном узле.</span><span class="sxs-lookup"><span data-stu-id="57a97-137">Each **WaitForXXXX** resource waits for the specified resources to complete on the specified Node.</span></span>
<span data-ttu-id="57a97-138">После этого другие ресурсы в той же конфигурации могут *зависеть от* ресурса **WaitForXXXX** с помощью ключа **DependsOn**.</span><span class="sxs-lookup"><span data-stu-id="57a97-138">Other resources in the same Configuration can then *depend on* the **WaitForXXXX** resource using the **DependsOn** key.</span></span>

<span data-ttu-id="57a97-139">Например, в следующей конфигурации целевой узел ожидает завершения выполнения ресурса **xADDomain** на узле **MyDC** не более чем с 30 повторными попытками (с интервалом 15 секунд), прежде чем присоединиться к домену.</span><span class="sxs-lookup"><span data-stu-id="57a97-139">For example, in the following configuration, the target node is waiting for the **xADDomain** resource to finish on the **MyDC** node with maximum number of 30 retries, at 15-second intervals, before the target node can join the domain.</span></span>

<span data-ttu-id="57a97-140">По умолчанию ресурсы **WaitForXXX** выполняют одну попытку, а затем выдают ошибку.</span><span class="sxs-lookup"><span data-stu-id="57a97-140">By default the **WaitForXXX** resources try one time and then fail.</span></span> <span data-ttu-id="57a97-141">Хотя это необязательно, обычно требуется указать **RetryCount** и **RetryIntervalSec**.</span><span class="sxs-lookup"><span data-stu-id="57a97-141">Although it is not required, you will typically want to specify a **RetryCount** and **RetryIntervalSec**.</span></span>

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

<span data-ttu-id="57a97-142">При компиляции конфигурации создаются два MOF-файла.</span><span class="sxs-lookup"><span data-stu-id="57a97-142">When you compile the Configuration, two ".mof" files are generated.</span></span> <span data-ttu-id="57a97-143">Примените их на целевые узлы с помощью командлета [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration)</span><span class="sxs-lookup"><span data-stu-id="57a97-143">Apply both ".mof" files to the target Nodes using the [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet</span></span>

> [!NOTE]
> <span data-ttu-id="57a97-144">Ресурсы **WaitForXXX** используют удаленное управление Windows, чтобы проверить состояние других узлов.</span><span class="sxs-lookup"><span data-stu-id="57a97-144">**WaitForXXX** resources use Windows Remote Management to check the state of other Nodes.</span></span> <span data-ttu-id="57a97-145">Дополнительные сведения о требованиях к безопасности и портах для WinRM см. в разделе [Вопросы обеспечения безопасности удаленного взаимодействия PowerShell](/powershell/scripting/learn/remoting/winrmsecurity).</span><span class="sxs-lookup"><span data-stu-id="57a97-145">For more information about port and security requirements for WinRM, see [PowerShell Remoting Security Considerations](/powershell/scripting/learn/remoting/winrmsecurity).</span></span>

## <a name="see-also"></a><span data-ttu-id="57a97-146">См. также</span><span class="sxs-lookup"><span data-stu-id="57a97-146">See Also</span></span>

- [<span data-ttu-id="57a97-147">Конфигурации DSC</span><span class="sxs-lookup"><span data-stu-id="57a97-147">DSC Configurations</span></span>](configurations.md)
- [<span data-ttu-id="57a97-148">Использование зависимостей ресурсов с DependsOn</span><span class="sxs-lookup"><span data-stu-id="57a97-148">Use Resource Dependencies</span></span>](resource-depends-on.md)
- [<span data-ttu-id="57a97-149">Ресурсы DSC</span><span class="sxs-lookup"><span data-stu-id="57a97-149">DSC Resources</span></span>](../resources/resources.md)
- [<span data-ttu-id="57a97-150">Настройка локального диспетчера конфигураций</span><span class="sxs-lookup"><span data-stu-id="57a97-150">Configuring The Local Configuration Manager</span></span>](../managing-nodes/metaConfig.md)
