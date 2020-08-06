---
title: Элемент Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: d5858145e092dc962174a776889a4f62db366d71
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785342"
---
# <a name="selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="2022c-102">Элемент SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="2022c-102">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="2022c-103">Определяет условие, которое должно существовать для расширения объектов коллекции этого определения.</span><span class="sxs-lookup"><span data-stu-id="2022c-103">Defines the condition that must exist to expand the collection objects of this definition.</span></span>

<span data-ttu-id="2022c-104">Элемент конфигурации (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс элемент (Format) Енумерабликспансион элемент (Format) Ентриселектедби элемент для енумерабликспансион (Format) SelectionCondition для EntrySelectedBy в EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="2022c-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2022c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2022c-105">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2022c-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2022c-106">Attributes and Elements</span></span>

<span data-ttu-id="2022c-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionCondition` элемента.</span><span class="sxs-lookup"><span data-stu-id="2022c-107">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span> <span data-ttu-id="2022c-108">Необходимо указать один `PropertyName` `ScriptBlock` элемент или.</span><span class="sxs-lookup"><span data-stu-id="2022c-108">You must specify a single `PropertyName` or `ScriptBlock` element.</span></span> <span data-ttu-id="2022c-109">`SelectionSetName`Элементы и `TypeName` являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="2022c-109">The `SelectionSetName` and `TypeName` elements are optional.</span></span> <span data-ttu-id="2022c-110">Можно указать один из этих элементов.</span><span class="sxs-lookup"><span data-stu-id="2022c-110">You can specify one of either element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2022c-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2022c-111">Attributes</span></span>

<span data-ttu-id="2022c-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2022c-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2022c-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2022c-113">Child Elements</span></span>

|<span data-ttu-id="2022c-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="2022c-114">Element</span></span>|<span data-ttu-id="2022c-115">Описание</span><span class="sxs-lookup"><span data-stu-id="2022c-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2022c-116">Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="2022c-116">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="2022c-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="2022c-117">Optional element.</span></span><br /><br /> <span data-ttu-id="2022c-118">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="2022c-118">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="2022c-119">Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="2022c-119">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="2022c-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="2022c-120">Optional element.</span></span><br /><br /> <span data-ttu-id="2022c-121">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="2022c-121">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="2022c-122">Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="2022c-122">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="2022c-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="2022c-123">Optional element.</span></span><br /><br /> <span data-ttu-id="2022c-124">Указывает набор типов .NET, которые инициируют условие.</span><span class="sxs-lookup"><span data-stu-id="2022c-124">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="2022c-125">Элемент TypeName для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="2022c-125">TypeName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="2022c-126">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="2022c-126">Optional element.</span></span><br /><br /> <span data-ttu-id="2022c-127">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="2022c-127">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2022c-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2022c-128">Parent Elements</span></span>

|<span data-ttu-id="2022c-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="2022c-129">Element</span></span>|<span data-ttu-id="2022c-130">Описание</span><span class="sxs-lookup"><span data-stu-id="2022c-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2022c-131">Элемент EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="2022c-131">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="2022c-132">Определяет, какие объекты коллекции .NET разворачиваются этим определением.</span><span class="sxs-lookup"><span data-stu-id="2022c-132">Defines which .NET collection objects are expanded by this definition.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2022c-133">Примечания</span><span class="sxs-lookup"><span data-stu-id="2022c-133">Remarks</span></span>

<span data-ttu-id="2022c-134">Каждое определение должно иметь по крайней мере одно определенное имя типа, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="2022c-134">Each definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="2022c-135">При определении условия выбора применяются следующие требования.</span><span class="sxs-lookup"><span data-stu-id="2022c-135">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="2022c-136">Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.</span><span class="sxs-lookup"><span data-stu-id="2022c-136">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="2022c-137">Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.</span><span class="sxs-lookup"><span data-stu-id="2022c-137">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="2022c-138">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для воспроизведения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="2022c-138">For more information about how to use selection conditions, see [Defining Conditions for Diplaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="2022c-139">Дополнительные сведения о других компонентах расширенного представления см. в разделе [широкие представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="2022c-139">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2022c-140">См. также</span><span class="sxs-lookup"><span data-stu-id="2022c-140">See Also</span></span>

[<span data-ttu-id="2022c-141">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="2022c-141">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="2022c-142">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="2022c-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
