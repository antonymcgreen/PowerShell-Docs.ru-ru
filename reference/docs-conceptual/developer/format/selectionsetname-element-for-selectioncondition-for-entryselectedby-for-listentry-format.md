---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListEntry (формат)
description: Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListEntry (формат)
ms.openlocfilehash: f3193799e67706eb07f0fe1c2cd42cce83f7af57
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651549"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format"></a><span data-ttu-id="d1d64-103">Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="d1d64-103">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

<span data-ttu-id="d1d64-104">Указывает набор типов .NET, которые активируют условие.</span><span class="sxs-lookup"><span data-stu-id="d1d64-104">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="d1d64-105">При наличии любого из типов в этом наборе условие выполняется, и объект отображается с помощью этого определения представления списка.</span><span class="sxs-lookup"><span data-stu-id="d1d64-105">When any of the types in this set are present, the condition is met, and the object is displayed by using this definition of the list view.</span></span>

<span data-ttu-id="d1d64-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент (Format) Ентриселектедби для листентри (Format) селектионкондитион для EntrySelectedBy для ListEntry в SelectionSetName для SelectionCondition (формат)</span><span class="sxs-lookup"><span data-stu-id="d1d64-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d1d64-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d1d64-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d1d64-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d1d64-108">Attributes and Elements</span></span>

<span data-ttu-id="d1d64-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемента.</span><span class="sxs-lookup"><span data-stu-id="d1d64-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d1d64-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d1d64-110">Attributes</span></span>

<span data-ttu-id="d1d64-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d1d64-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d1d64-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d1d64-112">Child Elements</span></span>

<span data-ttu-id="d1d64-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d1d64-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d1d64-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d1d64-114">Parent Elements</span></span>

|<span data-ttu-id="d1d64-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="d1d64-115">Element</span></span>|<span data-ttu-id="d1d64-116">Описание</span><span class="sxs-lookup"><span data-stu-id="d1d64-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d1d64-117">Элемент Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="d1d64-117">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="d1d64-118">Определяет условие, которое должно существовать для использования этого определения представления списка.</span><span class="sxs-lookup"><span data-stu-id="d1d64-118">Defines the condition that must exist to use this definition of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d1d64-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="d1d64-119">Text Value</span></span>

<span data-ttu-id="d1d64-120">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="d1d64-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="d1d64-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="d1d64-121">Remarks</span></span>

<span data-ttu-id="d1d64-122">Условие выбора может указывать набор выбора или тип .NET, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="d1d64-122">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="d1d64-123">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="d1d64-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="d1d64-124">Наборы выбора — это распространенные группы объектов .NET, которые могут использоваться любым представлением, определяемым файлом форматирования.</span><span class="sxs-lookup"><span data-stu-id="d1d64-124">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="d1d64-125">Дополнительные сведения о создании и ссылке на наборы выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="d1d64-125">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="d1d64-126">Дополнительные сведения о других компонентах представления списка см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="d1d64-126">For more information about other components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d1d64-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="d1d64-127">See Also</span></span>

[<span data-ttu-id="d1d64-128">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="d1d64-128">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="d1d64-129">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="d1d64-129">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="d1d64-130">Элемент Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="d1d64-130">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="d1d64-131">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1d64-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
