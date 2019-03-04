---
title: Элемент SelectionSetName для EntrySelectedBy для ListControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cff7763c-5ce0-49c1-a480-1249c9f57a13
caps.latest.revision: 11
ms.openlocfilehash: 7fd431b4b1ddecd3a7358c2bf97f299b97162b34
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860160"
---
# <a name="selectionsetname-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="132ca-102">Элемент SelectionSetName для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="132ca-102">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="132ca-103">Задает набор объектов .NET для записи в списке.</span><span class="sxs-lookup"><span data-stu-id="132ca-103">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="132ca-104">Количество наборов выбора, которые можно задать для записи не ограничено.</span><span class="sxs-lookup"><span data-stu-id="132ca-104">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="132ca-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемент (формат) элемента ListControl (формат) элемент ListEntries (формат) элемент ListEntry (формат) EntrySelectedBy элемент конфигурации для элемента SelectionSetName ListEntry (формат) для EntrySelectedBy для ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="132ca-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="132ca-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="132ca-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="132ca-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="132ca-107">Attributes and Elements</span></span>

<span data-ttu-id="132ca-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемент.</span><span class="sxs-lookup"><span data-stu-id="132ca-108">The following sections describe attributes, child elements, and parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="132ca-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="132ca-109">Attributes</span></span>

<span data-ttu-id="132ca-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="132ca-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="132ca-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="132ca-111">Child Elements</span></span>

<span data-ttu-id="132ca-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="132ca-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="132ca-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="132ca-113">Parent Elements</span></span>

|<span data-ttu-id="132ca-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="132ca-114">Element</span></span>|<span data-ttu-id="132ca-115">Описание</span><span class="sxs-lookup"><span data-stu-id="132ca-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="132ca-116">Элемент EntrySelectedBy для ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="132ca-116">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="132ca-117">Определяет типы .NET, использующих этот элемент списка или условие, которое должен существовать для данной записи для использования.</span><span class="sxs-lookup"><span data-stu-id="132ca-117">Defines the .NET types that use this list entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="132ca-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="132ca-118">Text Value</span></span>

<span data-ttu-id="132ca-119">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="132ca-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="132ca-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="132ca-120">Remarks</span></span>

<span data-ttu-id="132ca-121">Каждый элемент списка должен иметь по крайней мере одно имя типа, набора или Выбор условия, определенного.</span><span class="sxs-lookup"><span data-stu-id="132ca-121">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="132ca-122">Выбор наборов обычно используются, когда необходимо определить группу объектов, которые используются в нескольких представлениях.</span><span class="sxs-lookup"><span data-stu-id="132ca-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="132ca-123">Например можно создать представление таблицы и представления списка для одного набора объектов.</span><span class="sxs-lookup"><span data-stu-id="132ca-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="132ca-124">Дополнительные сведения об определении наборов выбора см. в разделе [определение задает объектов для представления](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="132ca-124">For more information about defining selection sets, see [Defining Sets of objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="132ca-125">Дополнительные сведения о компонентах представления списка, см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="132ca-125">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="132ca-126">Пример</span><span class="sxs-lookup"><span data-stu-id="132ca-126">Example</span></span>

<span data-ttu-id="132ca-127">В следующем примере показано задание выбора для записи представления списка.</span><span class="sxs-lookup"><span data-stu-id="132ca-127">The following example shows how to specify a selection set for an entry of a list view.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>
  </EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="132ca-128">См. также</span><span class="sxs-lookup"><span data-stu-id="132ca-128">See Also</span></span>

[<span data-ttu-id="132ca-129">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="132ca-129">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="132ca-130">Элемент EntrySelectedBy для ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="132ca-130">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="132ca-131">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="132ca-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
