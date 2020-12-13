---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент SelectionSetName для элемента EntrySelectedBy для элемента ListControl (формат)
description: Элемент SelectionSetName для элемента EntrySelectedBy для элемента ListControl (формат)
ms.openlocfilehash: 413a77f7ba06fe952e574061e58d0b5d80c5b3c4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651824"
---
# <a name="selectionsetname-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="f87b3-103">Элемент SelectionSetName для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="f87b3-103">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="f87b3-104">Задает набор объектов .NET для записи списка.</span><span class="sxs-lookup"><span data-stu-id="f87b3-104">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="f87b3-105">Количество наборов выбора, которые можно указать для записи, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="f87b3-105">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="f87b3-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент (Format) Ентриселектедби для листентри (Format) Селектионсетнаме для EntrySelectedBy в ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f87b3-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f87b3-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f87b3-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f87b3-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f87b3-108">Attributes and Elements</span></span>

<span data-ttu-id="f87b3-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемента.</span><span class="sxs-lookup"><span data-stu-id="f87b3-109">The following sections describe attributes, child elements, and parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f87b3-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f87b3-110">Attributes</span></span>

<span data-ttu-id="f87b3-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f87b3-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f87b3-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f87b3-112">Child Elements</span></span>

<span data-ttu-id="f87b3-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f87b3-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f87b3-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f87b3-114">Parent Elements</span></span>

|<span data-ttu-id="f87b3-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="f87b3-115">Element</span></span>|<span data-ttu-id="f87b3-116">Описание</span><span class="sxs-lookup"><span data-stu-id="f87b3-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f87b3-117">Элемент Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="f87b3-117">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="f87b3-118">Определяет типы .NET, которые используют эту запись списка или условие, которое должно существовать для использования этой записи.</span><span class="sxs-lookup"><span data-stu-id="f87b3-118">Defines the .NET types that use this list entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f87b3-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="f87b3-119">Text Value</span></span>

<span data-ttu-id="f87b3-120">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="f87b3-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="f87b3-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f87b3-121">Remarks</span></span>

<span data-ttu-id="f87b3-122">Каждая запись списка должна иметь по крайней мере одно определенное имя типа, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="f87b3-122">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="f87b3-123">Наборы выбора обычно используются, если требуется определить группу объектов, используемых в нескольких представлениях.</span><span class="sxs-lookup"><span data-stu-id="f87b3-123">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="f87b3-124">Например, может потребоваться создать табличное представление и представление списка для одного и того же набора объектов.</span><span class="sxs-lookup"><span data-stu-id="f87b3-124">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="f87b3-125">Дополнительные сведения об определении наборов выбора см. [в разделе Определение наборов объектов для представления](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="f87b3-125">For more information about defining selection sets, see [Defining Sets of objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="f87b3-126">Дополнительные сведения о компонентах представления списка см. [в разделе Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="f87b3-126">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="f87b3-127">Пример</span><span class="sxs-lookup"><span data-stu-id="f87b3-127">Example</span></span>

<span data-ttu-id="f87b3-128">В следующем примере показано, как задать набор выбора для записи в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="f87b3-128">The following example shows how to specify a selection set for an entry of a list view.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>
  </EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="f87b3-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="f87b3-129">See Also</span></span>

[<span data-ttu-id="f87b3-130">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="f87b3-130">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="f87b3-131">Элемент Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="f87b3-131">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="f87b3-132">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="f87b3-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
