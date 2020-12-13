---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент SelectionSetName для элемента EntrySelectedBy для элемента TableControl (формат)
description: Элемент SelectionSetName для элемента EntrySelectedBy для элемента TableControl (формат)
ms.openlocfilehash: a5a395f718d0e1a2d7f33d120ce4fd2ff787cc34
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651773"
---
# <a name="selectionsetname-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="d5175-103">Элемент SelectionSetName для элемента EntrySelectedBy для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="d5175-103">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="d5175-104">Указывает набор типов .NET, которые использует эту запись табличного представления.</span><span class="sxs-lookup"><span data-stu-id="d5175-104">Specifies a set of .NET types the use this entry of the table view.</span></span> <span data-ttu-id="d5175-105">Количество наборов выбора, которые можно указать для записи, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="d5175-105">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="d5175-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Ентриселектедби элемент (Format) Селектионсетнаме для EntrySelectedBy в TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="d5175-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format) SelectionSetName Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d5175-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5175-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d5175-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d5175-108">Attributes and Elements</span></span>

<span data-ttu-id="d5175-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d5175-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d5175-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d5175-110">Attributes</span></span>

<span data-ttu-id="d5175-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d5175-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d5175-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d5175-112">Child Elements</span></span>

<span data-ttu-id="d5175-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d5175-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d5175-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d5175-114">Parent Elements</span></span>

|<span data-ttu-id="d5175-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="d5175-115">Element</span></span>|<span data-ttu-id="d5175-116">Описание</span><span class="sxs-lookup"><span data-stu-id="d5175-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d5175-117">Элемент Ентриселектедби (Format)</span><span class="sxs-lookup"><span data-stu-id="d5175-117">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="d5175-118">Определяет типы .NET, которые используют эту запись, или условие, которое должно существовать для использования этой записи.</span><span class="sxs-lookup"><span data-stu-id="d5175-118">Defines the .NET types that use this entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d5175-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="d5175-119">Text Value</span></span>

<span data-ttu-id="d5175-120">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="d5175-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="d5175-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="d5175-121">Remarks</span></span>

<span data-ttu-id="d5175-122">Наборы выбора обычно используются, если требуется определить группу объектов, используемых в нескольких представлениях.</span><span class="sxs-lookup"><span data-stu-id="d5175-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="d5175-123">Например, может потребоваться создать табличное представление и представление списка для одного и того же набора объектов.</span><span class="sxs-lookup"><span data-stu-id="d5175-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="d5175-124">Дополнительные сведения об определении наборов выбора см. [в разделе Определение наборов объектов для представления](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="d5175-124">For more information about defining selection sets, see [Defining Sets of objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="d5175-125">Если для записи указан набор элементов, то нельзя указать имя типа.</span><span class="sxs-lookup"><span data-stu-id="d5175-125">If you specify a selection set for an entry, you cannot specify a type name.</span></span> <span data-ttu-id="d5175-126">Дополнительные сведения об указании типа .NET см. в разделе [элемент TypeName для ентриселектедби для таблеровентри (Format)](./typename-element-for-entryselectedby-for-tablecontrol-format.md).</span><span class="sxs-lookup"><span data-stu-id="d5175-126">For more information about how to specify a .NET type, see [TypeName Element for EntrySelectedBy for TableRowEntry (Format)](./typename-element-for-entryselectedby-for-tablecontrol-format.md).</span></span>

<span data-ttu-id="d5175-127">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="d5175-127">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d5175-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="d5175-128">See Also</span></span>

[<span data-ttu-id="d5175-129">Элемент Ентриселектедби (Format)</span><span class="sxs-lookup"><span data-stu-id="d5175-129">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="d5175-130">Определение наборов объектов для представления</span><span class="sxs-lookup"><span data-stu-id="d5175-130">Defining Sets of objects for a View</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="d5175-131">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="d5175-131">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="d5175-132">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="d5175-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
