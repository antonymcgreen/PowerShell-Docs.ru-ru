---
title: Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Видинтри (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 44c88ce75ae485e1c48ceb08bfd12f739a632996
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787450"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="d3cf6-102">Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="d3cf6-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="d3cf6-103">Указывает набор типов .NET, которые активируют условие.</span><span class="sxs-lookup"><span data-stu-id="d3cf6-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="d3cf6-104">При наличии любого из типов в этом наборе условие выполняется, и объект отображается с помощью этого определения расширенного представления.</span><span class="sxs-lookup"><span data-stu-id="d3cf6-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this definition of the wide view.</span></span>

<span data-ttu-id="d3cf6-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Ентриселектедби для видинтри (Format) селектионкондитион для EntrySelectedBy для WideEntry в SelectionSetName для SelectionCondition (формат)</span><span class="sxs-lookup"><span data-stu-id="d3cf6-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d3cf6-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d3cf6-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d3cf6-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d3cf6-107">Attributes and Elements</span></span>

<span data-ttu-id="d3cf6-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемента.</span><span class="sxs-lookup"><span data-stu-id="d3cf6-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d3cf6-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d3cf6-109">Attributes</span></span>

<span data-ttu-id="d3cf6-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d3cf6-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d3cf6-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d3cf6-111">Child Elements</span></span>

<span data-ttu-id="d3cf6-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d3cf6-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d3cf6-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d3cf6-113">Parent Elements</span></span>

|<span data-ttu-id="d3cf6-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="d3cf6-114">Element</span></span>|<span data-ttu-id="d3cf6-115">Описание</span><span class="sxs-lookup"><span data-stu-id="d3cf6-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d3cf6-116">Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="d3cf6-116">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="d3cf6-117">Определяет условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="d3cf6-117">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d3cf6-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="d3cf6-118">Text Value</span></span>

<span data-ttu-id="d3cf6-119">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="d3cf6-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="d3cf6-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="d3cf6-120">Remarks</span></span>

<span data-ttu-id="d3cf6-121">Условие выбора может указывать набор выбора или тип .NET, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="d3cf6-121">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="d3cf6-122">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="d3cf6-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="d3cf6-123">Наборы выбора — это распространенные группы объектов .NET, которые могут использоваться любым представлением, определяемым файлом форматирования.</span><span class="sxs-lookup"><span data-stu-id="d3cf6-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="d3cf6-124">Дополнительные сведения о создании и ссылке на наборы выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="d3cf6-124">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="d3cf6-125">Дополнительные сведения о других компонентах расширенного представления см. [в разделе Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="d3cf6-125">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d3cf6-126">См. также</span><span class="sxs-lookup"><span data-stu-id="d3cf6-126">See Also</span></span>

[<span data-ttu-id="d3cf6-127">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="d3cf6-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="d3cf6-128">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="d3cf6-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="d3cf6-129">Определение наборов выделенных фрагментов</span><span class="sxs-lookup"><span data-stu-id="d3cf6-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="d3cf6-130">Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="d3cf6-130">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="d3cf6-131">Элемент TypeName для Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="d3cf6-131">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="d3cf6-132">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3cf6-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
