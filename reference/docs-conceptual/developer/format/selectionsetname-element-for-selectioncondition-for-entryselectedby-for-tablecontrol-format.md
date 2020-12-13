---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)
description: Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)
ms.openlocfilehash: 2fb09e27eef1ce5d6e864c72edb595817d91f729
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655037"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="7e77e-103">Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="7e77e-103">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="7e77e-104">Указывает набор типов .NET, которые активируют условие.</span><span class="sxs-lookup"><span data-stu-id="7e77e-104">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="7e77e-105">При наличии любого из типов в этом наборе условие выполняется, и объект отображается с помощью этого определения табличного представления.</span><span class="sxs-lookup"><span data-stu-id="7e77e-105">When any of the types in this set are present, the condition is met, and the object is displayed by using this definition of the table view.</span></span>

<span data-ttu-id="7e77e-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Ентриселектедби для таблеровентри (Format) SelectionCondition для EntrySelectedBy для TableRowEntry в SelectionSetName для SelectionCondition (формат)</span><span class="sxs-lookup"><span data-stu-id="7e77e-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7e77e-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e77e-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7e77e-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7e77e-108">Attributes and Elements</span></span>

<span data-ttu-id="7e77e-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемента.</span><span class="sxs-lookup"><span data-stu-id="7e77e-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7e77e-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7e77e-110">Attributes</span></span>

<span data-ttu-id="7e77e-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7e77e-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7e77e-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7e77e-112">Child Elements</span></span>

<span data-ttu-id="7e77e-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7e77e-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7e77e-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7e77e-114">Parent Elements</span></span>

|<span data-ttu-id="7e77e-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="7e77e-115">Element</span></span>|<span data-ttu-id="7e77e-116">Описание</span><span class="sxs-lookup"><span data-stu-id="7e77e-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7e77e-117">Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="7e77e-117">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="7e77e-118">Определяет условие, которое должно существовать для использования в этом определении табличного представления.</span><span class="sxs-lookup"><span data-stu-id="7e77e-118">Defines the condition that must exist to use for this definition of the table view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7e77e-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="7e77e-119">Text Value</span></span>

<span data-ttu-id="7e77e-120">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="7e77e-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="7e77e-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="7e77e-121">Remarks</span></span>

<span data-ttu-id="7e77e-122">Условие выбора может указывать набор выбора или тип .NET, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="7e77e-122">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="7e77e-123">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="7e77e-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="7e77e-124">Наборы выбора — это распространенные группы объектов .NET, которые могут использоваться любым представлением, определяемым файлом форматирования.</span><span class="sxs-lookup"><span data-stu-id="7e77e-124">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="7e77e-125">Дополнительные сведения о создании и ссылке на наборы выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="7e77e-125">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="7e77e-126">Дополнительные сведения о других компонентах расширенного представления см. [в разделе Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="7e77e-126">For more information about other components of a wide view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7e77e-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="7e77e-127">See Also</span></span>

[<span data-ttu-id="7e77e-128">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="7e77e-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="7e77e-129">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="7e77e-129">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="7e77e-130">Элемент TypeName для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="7e77e-130">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="7e77e-131">Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="7e77e-131">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="7e77e-132">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="7e77e-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
