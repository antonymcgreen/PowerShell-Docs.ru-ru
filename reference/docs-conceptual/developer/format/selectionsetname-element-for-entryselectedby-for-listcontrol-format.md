---
title: Элемент Селектионсетнаме для Ентриселектедби для ListControl (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cff7763c-5ce0-49c1-a480-1249c9f57a13
caps.latest.revision: 11
ms.openlocfilehash: 7fd431b4b1ddecd3a7358c2bf97f299b97162b34
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362003"
---
# <a name="selectionsetname-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="29f78-102">Элемент SelectionSetName для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="29f78-102">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="29f78-103">Задает набор объектов .NET для записи списка.</span><span class="sxs-lookup"><span data-stu-id="29f78-103">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="29f78-104">Количество наборов выбора, которые можно указать для записи, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="29f78-104">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="29f78-105">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент (Format) Ентриселектедби для Листентри (Format) Селектионсетнаме элемент для Ентриселектедби для Листентри (формат)</span><span class="sxs-lookup"><span data-stu-id="29f78-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="29f78-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="29f78-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="29f78-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="29f78-107">Attributes and Elements</span></span>

<span data-ttu-id="29f78-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `SelectionSetName`.</span><span class="sxs-lookup"><span data-stu-id="29f78-108">The following sections describe attributes, child elements, and parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="29f78-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="29f78-109">Attributes</span></span>

<span data-ttu-id="29f78-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="29f78-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="29f78-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="29f78-111">Child Elements</span></span>

<span data-ttu-id="29f78-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="29f78-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="29f78-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="29f78-113">Parent Elements</span></span>

|<span data-ttu-id="29f78-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="29f78-114">Element</span></span>|<span data-ttu-id="29f78-115">Описание</span><span class="sxs-lookup"><span data-stu-id="29f78-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="29f78-116">Элемент Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="29f78-116">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="29f78-117">Определяет типы .NET, которые используют эту запись списка или условие, которое должно существовать для использования этой записи.</span><span class="sxs-lookup"><span data-stu-id="29f78-117">Defines the .NET types that use this list entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="29f78-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="29f78-118">Text Value</span></span>

<span data-ttu-id="29f78-119">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="29f78-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="29f78-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="29f78-120">Remarks</span></span>

<span data-ttu-id="29f78-121">Каждая запись списка должна иметь по крайней мере одно определенное имя типа, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="29f78-121">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="29f78-122">Наборы выбора обычно используются, если требуется определить группу объектов, используемых в нескольких представлениях.</span><span class="sxs-lookup"><span data-stu-id="29f78-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="29f78-123">Например, может потребоваться создать табличное представление и представление списка для одного и того же набора объектов.</span><span class="sxs-lookup"><span data-stu-id="29f78-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="29f78-124">Дополнительные сведения об определении наборов выбора см. [в разделе Определение наборов объектов для представления](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="29f78-124">For more information about defining selection sets, see [Defining Sets of objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="29f78-125">Дополнительные сведения о компонентах представления списка см. [в разделе Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="29f78-125">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="29f78-126">Пример</span><span class="sxs-lookup"><span data-stu-id="29f78-126">Example</span></span>

<span data-ttu-id="29f78-127">В следующем примере показано, как задать набор выбора для записи в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="29f78-127">The following example shows how to specify a selection set for an entry of a list view.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>
  </EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="29f78-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="29f78-128">See Also</span></span>

[<span data-ttu-id="29f78-129">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="29f78-129">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="29f78-130">Элемент Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="29f78-130">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="29f78-131">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="29f78-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
