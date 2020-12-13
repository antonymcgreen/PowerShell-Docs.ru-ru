---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)
description: Элемент SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)
ms.openlocfilehash: 3ecf7fde99b9ee66a153eea416792f351ff62af3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647927"
---
# <a name="selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="1d3e6-103">Элемент SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="1d3e6-103">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="1d3e6-104">Определяет условие, которое должно существовать для расширения объектов коллекции этого определения.</span><span class="sxs-lookup"><span data-stu-id="1d3e6-104">Defines the condition that must exist to expand the collection objects of this definition.</span></span>

<span data-ttu-id="1d3e6-105">Элемент конфигурации (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс элемент (Format) Енумерабликспансион элемент (Format) Ентриселектедби элемент для енумерабликспансион (Format) SelectionCondition для EntrySelectedBy в EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="1d3e6-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1d3e6-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1d3e6-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1d3e6-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1d3e6-107">Attributes and Elements</span></span>

<span data-ttu-id="1d3e6-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionCondition` элемента.</span><span class="sxs-lookup"><span data-stu-id="1d3e6-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span> <span data-ttu-id="1d3e6-109">Необходимо указать один `PropertyName` `ScriptBlock` элемент или.</span><span class="sxs-lookup"><span data-stu-id="1d3e6-109">You must specify a single `PropertyName` or `ScriptBlock` element.</span></span> <span data-ttu-id="1d3e6-110">`SelectionSetName`Элементы и `TypeName` являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="1d3e6-110">The `SelectionSetName` and `TypeName` elements are optional.</span></span> <span data-ttu-id="1d3e6-111">Можно указать один из этих элементов.</span><span class="sxs-lookup"><span data-stu-id="1d3e6-111">You can specify one of either element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1d3e6-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1d3e6-112">Attributes</span></span>

<span data-ttu-id="1d3e6-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1d3e6-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1d3e6-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1d3e6-114">Child Elements</span></span>

|<span data-ttu-id="1d3e6-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="1d3e6-115">Element</span></span>|<span data-ttu-id="1d3e6-116">Описание</span><span class="sxs-lookup"><span data-stu-id="1d3e6-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1d3e6-117">Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="1d3e6-117">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="1d3e6-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="1d3e6-118">Optional element.</span></span><br /><br /> <span data-ttu-id="1d3e6-119">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="1d3e6-119">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="1d3e6-120">Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="1d3e6-120">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="1d3e6-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="1d3e6-121">Optional element.</span></span><br /><br /> <span data-ttu-id="1d3e6-122">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="1d3e6-122">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="1d3e6-123">Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="1d3e6-123">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="1d3e6-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="1d3e6-124">Optional element.</span></span><br /><br /> <span data-ttu-id="1d3e6-125">Указывает набор типов .NET, которые инициируют условие.</span><span class="sxs-lookup"><span data-stu-id="1d3e6-125">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="1d3e6-126">Элемент TypeName для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="1d3e6-126">TypeName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="1d3e6-127">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="1d3e6-127">Optional element.</span></span><br /><br /> <span data-ttu-id="1d3e6-128">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="1d3e6-128">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="1d3e6-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1d3e6-129">Parent Elements</span></span>

|<span data-ttu-id="1d3e6-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="1d3e6-130">Element</span></span>|<span data-ttu-id="1d3e6-131">Описание</span><span class="sxs-lookup"><span data-stu-id="1d3e6-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1d3e6-132">Элемент EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="1d3e6-132">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="1d3e6-133">Определяет, какие объекты коллекции .NET разворачиваются этим определением.</span><span class="sxs-lookup"><span data-stu-id="1d3e6-133">Defines which .NET collection objects are expanded by this definition.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1d3e6-134">Комментарии</span><span class="sxs-lookup"><span data-stu-id="1d3e6-134">Remarks</span></span>

<span data-ttu-id="1d3e6-135">Каждое определение должно иметь по крайней мере одно определенное имя типа, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="1d3e6-135">Each definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="1d3e6-136">При определении условия выбора применяются следующие требования.</span><span class="sxs-lookup"><span data-stu-id="1d3e6-136">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="1d3e6-137">Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.</span><span class="sxs-lookup"><span data-stu-id="1d3e6-137">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="1d3e6-138">Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.</span><span class="sxs-lookup"><span data-stu-id="1d3e6-138">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="1d3e6-139">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для воспроизведения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="1d3e6-139">For more information about how to use selection conditions, see [Defining Conditions for Diplaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="1d3e6-140">Дополнительные сведения о других компонентах расширенного представления см. в разделе [широкие представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="1d3e6-140">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1d3e6-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="1d3e6-141">See Also</span></span>

[<span data-ttu-id="1d3e6-142">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="1d3e6-142">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="1d3e6-143">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="1d3e6-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
