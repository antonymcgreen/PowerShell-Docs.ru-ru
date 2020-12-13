---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)
description: Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)
ms.openlocfilehash: c6466e3ac6e1f194df9172468d26448f9630da6a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655010"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="0d5ff-103">Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="0d5ff-103">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="0d5ff-104">Указывает набор типов .NET, которые активируют условие.</span><span class="sxs-lookup"><span data-stu-id="0d5ff-104">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="0d5ff-105">При наличии любого из типов в этом наборе условие выполняется, и объект отображается с помощью этого определения расширенного представления.</span><span class="sxs-lookup"><span data-stu-id="0d5ff-105">When any of the types in this set are present, the condition is met, and the object is displayed by using this definition of the wide view.</span></span>

<span data-ttu-id="0d5ff-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Ентриселектедби для видинтри (Format) селектионкондитион для EntrySelectedBy для WideEntry в SelectionSetName для SelectionCondition (формат)</span><span class="sxs-lookup"><span data-stu-id="0d5ff-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0d5ff-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d5ff-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0d5ff-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0d5ff-108">Attributes and Elements</span></span>

<span data-ttu-id="0d5ff-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемента.</span><span class="sxs-lookup"><span data-stu-id="0d5ff-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0d5ff-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0d5ff-110">Attributes</span></span>

<span data-ttu-id="0d5ff-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0d5ff-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0d5ff-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0d5ff-112">Child Elements</span></span>

<span data-ttu-id="0d5ff-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0d5ff-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0d5ff-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0d5ff-114">Parent Elements</span></span>

|<span data-ttu-id="0d5ff-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="0d5ff-115">Element</span></span>|<span data-ttu-id="0d5ff-116">Описание</span><span class="sxs-lookup"><span data-stu-id="0d5ff-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0d5ff-117">Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="0d5ff-117">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="0d5ff-118">Определяет условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="0d5ff-118">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="0d5ff-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="0d5ff-119">Text Value</span></span>

<span data-ttu-id="0d5ff-120">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="0d5ff-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="0d5ff-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="0d5ff-121">Remarks</span></span>

<span data-ttu-id="0d5ff-122">Условие выбора может указывать набор выбора или тип .NET, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="0d5ff-122">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="0d5ff-123">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="0d5ff-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="0d5ff-124">Наборы выбора — это распространенные группы объектов .NET, которые могут использоваться любым представлением, определяемым файлом форматирования.</span><span class="sxs-lookup"><span data-stu-id="0d5ff-124">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="0d5ff-125">Дополнительные сведения о создании и ссылке на наборы выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="0d5ff-125">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="0d5ff-126">Дополнительные сведения о других компонентах расширенного представления см. [в разделе Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="0d5ff-126">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0d5ff-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="0d5ff-127">See Also</span></span>

[<span data-ttu-id="0d5ff-128">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="0d5ff-128">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="0d5ff-129">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="0d5ff-129">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="0d5ff-130">Определение наборов выделенных фрагментов</span><span class="sxs-lookup"><span data-stu-id="0d5ff-130">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="0d5ff-131">Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="0d5ff-131">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="0d5ff-132">Элемент TypeName для Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="0d5ff-132">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="0d5ff-133">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="0d5ff-133">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
