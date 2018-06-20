---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс DSC WaitForSome
ms.openlocfilehash: 08a5b96bee0b1b4475470e0d857dca79dee2b02e
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2018
ms.locfileid: "34190236"
---
# <a name="dsc-waitforsome-resource"></a><span data-ttu-id="075bd-103">Ресурс DSC WaitForSome</span><span class="sxs-lookup"><span data-stu-id="075bd-103">DSC WaitForSome Resource</span></span>

> <span data-ttu-id="075bd-104">Область применения: Windows PowerShell 5.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="075bd-104">Applies To: Windows PowerShell 5.0 and later</span></span>

<span data-ttu-id="075bd-105">Ресурс настройки требуемого состояния **WaitForAny** можно использовать в блоке узла в [конфигурации DSC](configurations.md) для определения зависимостей от конфигураций на других узлах.</span><span class="sxs-lookup"><span data-stu-id="075bd-105">The **WaitForAny** Desired State Configuration (DSC) resource can be used within a node block in a [DSC configuration](configurations.md) to specify dependencies on configurations on other nodes.</span></span>

<span data-ttu-id="075bd-106">Ресурс выполняется успешно, если ресурс, указанный свойством **ResourceName**, находится в требуемом состоянии на минимальном числе узлов (определяется свойством **NodeCount**), заданных свойством **NodeName**.</span><span class="sxs-lookup"><span data-stu-id="075bd-106">This resource succeeds if the resource specified by the **ResourceName** property is in the desired state on a minimum number of nodes (specified by **NodeCount**) defined by the **NodeName** property.</span></span>


## <a name="syntax"></a><span data-ttu-id="075bd-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="075bd-107">Syntax</span></span>

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

## <a name="properties"></a><span data-ttu-id="075bd-108">Свойства</span><span class="sxs-lookup"><span data-stu-id="075bd-108">Properties</span></span>

|  <span data-ttu-id="075bd-109">Свойство</span><span class="sxs-lookup"><span data-stu-id="075bd-109">Property</span></span>  |  <span data-ttu-id="075bd-110">Описание</span><span class="sxs-lookup"><span data-stu-id="075bd-110">Description</span></span>   |
|---|---|
| <span data-ttu-id="075bd-111">NodeCount</span><span class="sxs-lookup"><span data-stu-id="075bd-111">NodeCount</span></span>| <span data-ttu-id="075bd-112">Минимальное количество узлов, которые должны быть в требуемом состоянии для успешного выполнения этого ресурса.</span><span class="sxs-lookup"><span data-stu-id="075bd-112">The minimum number of nodes that must be in the desired state for this resource to succeed.</span></span>|
| <span data-ttu-id="075bd-113">NodeName</span><span class="sxs-lookup"><span data-stu-id="075bd-113">NodeName</span></span>| <span data-ttu-id="075bd-114">Целевые узлы ресурса, с которым настраивается отношение зависимости.</span><span class="sxs-lookup"><span data-stu-id="075bd-114">The target nodes of the resource to depend on.</span></span>|
| <span data-ttu-id="075bd-115">ResourceName</span><span class="sxs-lookup"><span data-stu-id="075bd-115">ResourceName</span></span>| <span data-ttu-id="075bd-116">Имя ресурса, с которым настраивается отношение зависимости.</span><span class="sxs-lookup"><span data-stu-id="075bd-116">The resource name to depend on.</span></span> <span data-ttu-id="075bd-117">Если этот ресурс принадлежит другой конфигурации, имя следует указать в формате "[__тип ресурса__]__имя ресурса__::[__имя конфигурации__]::[__имя конфигурации__]".</span><span class="sxs-lookup"><span data-stu-id="075bd-117">If this resource belongs to a different configuration, format the name as "[__ResourceType__]__ResourceName__::[__ConfigurationName__]::[__ConfigurationName__]"</span></span>|
| <span data-ttu-id="075bd-118">RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="075bd-118">RetryIntervalSec</span></span>| <span data-ttu-id="075bd-119">Количество секунд перед повторной попыткой.</span><span class="sxs-lookup"><span data-stu-id="075bd-119">The number of seconds before retrying.</span></span> <span data-ttu-id="075bd-120">Минимальное значение — 1.</span><span class="sxs-lookup"><span data-stu-id="075bd-120">Minimum is 1.</span></span>|
| <span data-ttu-id="075bd-121">RetryCount</span><span class="sxs-lookup"><span data-stu-id="075bd-121">RetryCount</span></span>| <span data-ttu-id="075bd-122">Максимальное число повторных попыток.</span><span class="sxs-lookup"><span data-stu-id="075bd-122">The maximum number of times to retry.</span></span>|
| <span data-ttu-id="075bd-123">ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="075bd-123">ThrottleLimit</span></span>| <span data-ttu-id="075bd-124">Количество одновременно подключаемых компьютеров.</span><span class="sxs-lookup"><span data-stu-id="075bd-124">Number of machines to connect simultaneously.</span></span> <span data-ttu-id="075bd-125">Значение по умолчанию — New-CimSession.</span><span class="sxs-lookup"><span data-stu-id="075bd-125">Default is new-cimsession default.</span></span>|
| <span data-ttu-id="075bd-126">DependsOn</span><span class="sxs-lookup"><span data-stu-id="075bd-126">DependsOn</span></span> | <span data-ttu-id="075bd-127">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="075bd-127">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="075bd-128">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — __ResourceName__, а его тип — __ResourceType__, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="075bd-128">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|
| <span data-ttu-id="075bd-129">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="075bd-129">PsDscRunAsCredential</span></span> | <span data-ttu-id="075bd-130">См. статью [Запуск DSC с учетными данными пользователя](https://docs.microsoft.com/powershell/dsc/runasuser).</span><span class="sxs-lookup"><span data-stu-id="075bd-130">See [Using DSC with User Credentials](https://docs.microsoft.com/powershell/dsc/runasuser)</span></span> |


## <a name="example"></a><span data-ttu-id="075bd-131">Пример</span><span class="sxs-lookup"><span data-stu-id="075bd-131">Example</span></span>

<span data-ttu-id="075bd-132">Пример использования этого ресурса см. в статье [Указание межузловых зависимостей](crossNodeDependencies.md).</span><span class="sxs-lookup"><span data-stu-id="075bd-132">For an example of how to use this resource, see [Specifying cross-node dependencies](crossNodeDependencies.md)</span></span>