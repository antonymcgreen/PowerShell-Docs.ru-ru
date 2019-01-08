---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс DSC WaitForAll
ms.openlocfilehash: 1e891f1aecbdbe641973669f71f22664ad8ea16c
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047659"
---
# <a name="dsc-waitforall-resource"></a><span data-ttu-id="a8cb4-103">Ресурс DSC WaitForAll</span><span class="sxs-lookup"><span data-stu-id="a8cb4-103">DSC WaitForAll Resource</span></span>

> <span data-ttu-id="a8cb4-104">Область применения. Windows PowerShell 5.0 и более поздние версии</span><span class="sxs-lookup"><span data-stu-id="a8cb4-104">Applies To: Windows PowerShell 5.0 and later</span></span>

<span data-ttu-id="a8cb4-105">Ресурс настройки требуемого состояния **WaitForAll** можно использовать в блоке узла в [конфигурации DSC](../../../configurations/configurations.md) для определения зависимостей от конфигураций на других узлах.</span><span class="sxs-lookup"><span data-stu-id="a8cb4-105">The **WaitForAll** Desired State Configuration (DSC) resource can be used within a node block in a [DSC configuration](../../../configurations/configurations.md) to specify dependencies on configurations on other nodes.</span></span>

<span data-ttu-id="a8cb4-106">Этот ресурс выполняется успешно, если ресурс, указанный свойством **ResourceName**, находится в требуемом состоянии на всех целевых узлах, определенных в свойстве **NodeName**.</span><span class="sxs-lookup"><span data-stu-id="a8cb4-106">This resource succeeds if the resource specified by the **ResourceName** property is in the desired state on all target nodes defined in the **NodeName** property.</span></span>

## <a name="syntax"></a><span data-ttu-id="a8cb4-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a8cb4-107">Syntax</span></span>

```
WaitForAll [string] #ResourceName
{
    ResourceName = [string]
    NodeName = [string]
    [ RetryIntervalSec = [Uint64] ]
    [ RetryCount = [Uint32] ]
    [ ThrottleLimit = [Uint32]]
    [ DependsOn = [string[]] ]
}
```

## <a name="properties"></a><span data-ttu-id="a8cb4-108">Свойства</span><span class="sxs-lookup"><span data-stu-id="a8cb4-108">Properties</span></span>

|  <span data-ttu-id="a8cb4-109">Свойство</span><span class="sxs-lookup"><span data-stu-id="a8cb4-109">Property</span></span>  |  <span data-ttu-id="a8cb4-110">Описание</span><span class="sxs-lookup"><span data-stu-id="a8cb4-110">Description</span></span>   |
|---|---|
| <span data-ttu-id="a8cb4-111">ResourceName</span><span class="sxs-lookup"><span data-stu-id="a8cb4-111">ResourceName</span></span>| <span data-ttu-id="a8cb4-112">Имя ресурса, с которым настраивается отношение зависимости.</span><span class="sxs-lookup"><span data-stu-id="a8cb4-112">The resource name to depend on.</span></span> <span data-ttu-id="a8cb4-113">Если этот ресурс принадлежит другой конфигурации, имя следует указать в формате "[__тип ресурса__]__имя ресурса__::[__имя конфигурации__]::[__имя конфигурации__]".</span><span class="sxs-lookup"><span data-stu-id="a8cb4-113">If this resource belongs to a different configuration, format the name as "[__ResourceType__]__ResourceName__::[__ConfigurationName__]::[__ConfigurationName__]"</span></span>|
| <span data-ttu-id="a8cb4-114">NodeName</span><span class="sxs-lookup"><span data-stu-id="a8cb4-114">NodeName</span></span>| <span data-ttu-id="a8cb4-115">Целевые узлы ресурса, с которым настраивается отношение зависимости.</span><span class="sxs-lookup"><span data-stu-id="a8cb4-115">The target nodes of the resource to depend on.</span></span>|
| <span data-ttu-id="a8cb4-116">RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="a8cb4-116">RetryIntervalSec</span></span>| <span data-ttu-id="a8cb4-117">Количество секунд перед повторной попыткой.</span><span class="sxs-lookup"><span data-stu-id="a8cb4-117">The number of seconds before retrying.</span></span> <span data-ttu-id="a8cb4-118">Минимальное значение — 1.</span><span class="sxs-lookup"><span data-stu-id="a8cb4-118">Minimum is 1.</span></span>|
| <span data-ttu-id="a8cb4-119">RetryCount</span><span class="sxs-lookup"><span data-stu-id="a8cb4-119">RetryCount</span></span>| <span data-ttu-id="a8cb4-120">Максимальное число повторных попыток.</span><span class="sxs-lookup"><span data-stu-id="a8cb4-120">The maximum number of times to retry.</span></span>|
| <span data-ttu-id="a8cb4-121">ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="a8cb4-121">ThrottleLimit</span></span>| <span data-ttu-id="a8cb4-122">Количество одновременно подключаемых компьютеров.</span><span class="sxs-lookup"><span data-stu-id="a8cb4-122">Number of machines to connect simultaneously.</span></span> <span data-ttu-id="a8cb4-123">Значение по умолчанию — New-CimSession.</span><span class="sxs-lookup"><span data-stu-id="a8cb4-123">Default is new-cimsession default.</span></span>|
| <span data-ttu-id="a8cb4-124">DependsOn</span><span class="sxs-lookup"><span data-stu-id="a8cb4-124">DependsOn</span></span> | <span data-ttu-id="a8cb4-125">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="a8cb4-125">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="a8cb4-126">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — __ResourceName__, а его тип — __ResourceType__, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="a8cb4-126">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|

## <a name="example"></a><span data-ttu-id="a8cb4-127">Пример</span><span class="sxs-lookup"><span data-stu-id="a8cb4-127">Example</span></span>

<span data-ttu-id="a8cb4-128">Пример использования этого ресурса см. в статье [Указание межузловых зависимостей](../../../configurations/crossNodeDependencies.md).</span><span class="sxs-lookup"><span data-stu-id="a8cb4-128">For an example of how to use this resource, see [Specifying cross-node dependencies](../../../configurations/crossNodeDependencies.md)</span></span>
