---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
title: Ресурс DSC WaitForSome
ms.openlocfilehash: 91589c84518a2bd0f4816d11aa011dec1d5305e1
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2019
ms.locfileid: "71952981"
---
# <a name="dsc-waitforsome-resource"></a><span data-ttu-id="ba294-103">Ресурс DSC WaitForSome</span><span class="sxs-lookup"><span data-stu-id="ba294-103">DSC WaitForSome Resource</span></span>

> <span data-ttu-id="ba294-104">Область применения: Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="ba294-104">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="ba294-105">Ресурс настройки требуемого состояния **WaitForSome** можно использовать в блоке узла в [конфигурации DSC](../../../configurations/configurations.md) для определения зависимостей от конфигураций на других узлах.</span><span class="sxs-lookup"><span data-stu-id="ba294-105">The **WaitForSome** Desired State Configuration (DSC) resource can be used within a node block in a [DSC configuration](../../../configurations/configurations.md) to specify dependencies on configurations on other nodes.</span></span>

<span data-ttu-id="ba294-106">Ресурс выполняется успешно, если ресурс, указанный свойством **ResourceName**, находится в требуемом состоянии на минимальном числе узлов (определяется свойством **NodeCount**), заданных свойством **NodeName**.</span><span class="sxs-lookup"><span data-stu-id="ba294-106">This resource succeeds if the resource specified by the **ResourceName** property is in the desired state on a minimum number of nodes (specified by **NodeCount**) defined by the **NodeName** property.</span></span>

> [!NOTE]
> <span data-ttu-id="ba294-107">Ресурс **WaitForSome** использует удаленное управление Windows, чтобы проверить состояние других узлов.</span><span class="sxs-lookup"><span data-stu-id="ba294-107">**WaitForSome** resource uses Windows Remote Management to check the state of other Nodes.</span></span> <span data-ttu-id="ba294-108">Дополнительные сведения о требованиях к безопасности и портах для WinRM см. в разделе [Вопросы обеспечения безопасности удаленного взаимодействия PowerShell](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6).</span><span class="sxs-lookup"><span data-stu-id="ba294-108">For more information about port and security requirements for WinRM, see [PowerShell Remoting Security Considerations](/powershell/scripting/learn/remoting/winrmsecurity?view=powershell-6).</span></span>

## <a name="syntax"></a><span data-ttu-id="ba294-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba294-109">Syntax</span></span>

```Syntax
WaitForSome [String] #ResourceName
{
    NodeCount = [UInt32]
    NodeName = [string[]]
    ResourceName = [string]
    [ RetryCount = [UInt32] ]
    [ RetryIntervalSec = [UInt64] ]
    [ ThrottleLimit = [UInt32] ]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="ba294-110">Свойства</span><span class="sxs-lookup"><span data-stu-id="ba294-110">Properties</span></span>

|<span data-ttu-id="ba294-111">Свойство</span><span class="sxs-lookup"><span data-stu-id="ba294-111">Property</span></span> |<span data-ttu-id="ba294-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ba294-112">Description</span></span> |
|---|---|
|<span data-ttu-id="ba294-113">NodeCount</span><span class="sxs-lookup"><span data-stu-id="ba294-113">NodeCount</span></span> |<span data-ttu-id="ba294-114">Минимальное количество узлов, которые должны быть в требуемом состоянии для успешного выполнения этого ресурса.</span><span class="sxs-lookup"><span data-stu-id="ba294-114">The minimum number of nodes that must be in the desired state for this resource to succeed.</span></span> |
|<span data-ttu-id="ba294-115">NodeName</span><span class="sxs-lookup"><span data-stu-id="ba294-115">NodeName</span></span> |<span data-ttu-id="ba294-116">Целевые узлы ресурса, с которым настраивается отношение зависимости.</span><span class="sxs-lookup"><span data-stu-id="ba294-116">The target nodes of the resource to depend on.</span></span> |
|<span data-ttu-id="ba294-117">ResourceName</span><span class="sxs-lookup"><span data-stu-id="ba294-117">ResourceName</span></span> |<span data-ttu-id="ba294-118">Имя ресурса, с которым настраивается отношение зависимости.</span><span class="sxs-lookup"><span data-stu-id="ba294-118">The resource name to depend on.</span></span> <span data-ttu-id="ba294-119">Если этот ресурс относится к другой конфигурации, то его имя следует отформатировать как `[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]`.</span><span class="sxs-lookup"><span data-stu-id="ba294-119">If this resource belongs to a different configuration, format the name as `[ResourceType]ResourceName::[ConfigurationName]::[ConfigurationName]`.</span></span> |
|<span data-ttu-id="ba294-120">RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="ba294-120">RetryIntervalSec</span></span> |<span data-ttu-id="ba294-121">Количество секунд перед повторной попыткой.</span><span class="sxs-lookup"><span data-stu-id="ba294-121">The number of seconds before retrying.</span></span> <span data-ttu-id="ba294-122">Минимальное значение — 1.</span><span class="sxs-lookup"><span data-stu-id="ba294-122">Minimum is 1.</span></span> |
|<span data-ttu-id="ba294-123">RetryCount</span><span class="sxs-lookup"><span data-stu-id="ba294-123">RetryCount</span></span> |<span data-ttu-id="ba294-124">Максимальное число повторных попыток.</span><span class="sxs-lookup"><span data-stu-id="ba294-124">The maximum number of times to retry.</span></span> |
|<span data-ttu-id="ba294-125">ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="ba294-125">ThrottleLimit</span></span> |<span data-ttu-id="ba294-126">Количество одновременно подключаемых компьютеров.</span><span class="sxs-lookup"><span data-stu-id="ba294-126">Number of machines to connect simultaneously.</span></span> <span data-ttu-id="ba294-127">Значение по умолчанию — `New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="ba294-127">Default is `New-CimSession` default.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="ba294-128">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="ba294-128">Common properties</span></span>

|<span data-ttu-id="ba294-129">Свойство</span><span class="sxs-lookup"><span data-stu-id="ba294-129">Property</span></span> |<span data-ttu-id="ba294-130">Описание</span><span class="sxs-lookup"><span data-stu-id="ba294-130">Description</span></span> |
|---|---|
|<span data-ttu-id="ba294-131">DependsOn</span><span class="sxs-lookup"><span data-stu-id="ba294-131">DependsOn</span></span> |<span data-ttu-id="ba294-132">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="ba294-132">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="ba294-133">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="ba294-133">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="ba294-134">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="ba294-134">PsDscRunAsCredential</span></span> |<span data-ttu-id="ba294-135">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="ba294-135">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="ba294-136">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="ba294-136">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="ba294-137">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="ba294-137">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="ba294-138">Пример</span><span class="sxs-lookup"><span data-stu-id="ba294-138">Example</span></span>

<span data-ttu-id="ba294-139">Пример использования этого ресурса см. в статье [Указание межузловых зависимостей](../../../configurations/crossNodeDependencies.md).</span><span class="sxs-lookup"><span data-stu-id="ba294-139">For an example of how to use this resource, see [Specifying cross-node dependencies](../../../configurations/crossNodeDependencies.md)</span></span>