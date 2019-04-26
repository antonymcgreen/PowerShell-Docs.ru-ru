---
title: Элемент SelectionSetName для EntrySelectedBy для TableControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5dd0bd5d-f206-4cc6-a0f8-70700ee2c4b7
caps.latest.revision: 8
ms.openlocfilehash: 819906127e81355c45103ede85ef3608e1c1cfeb
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62063927"
---
# <a name="selectionsetname-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="b5e8d-102">Элемент SelectionSetName для элемента EntrySelectedBy для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="b5e8d-102">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="b5e8d-103">Указывает, что набор .NET вводит использование этой записи таблицы представления.</span><span class="sxs-lookup"><span data-stu-id="b5e8d-103">Specifies a set of .NET types the use this entry of the table view.</span></span> <span data-ttu-id="b5e8d-104">Количество наборов выбора, которые можно задать для записи не ограничено.</span><span class="sxs-lookup"><span data-stu-id="b5e8d-104">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="b5e8d-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) элемент TableRowEntries (формат) элемент TableRowEntry (формат) элемент EntrySelectedBy (формат) SelectionSetName элемент конфигурации для EntrySelectedBy для TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="b5e8d-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format) SelectionSetName Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b5e8d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b5e8d-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b5e8d-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b5e8d-107">Attributes and Elements</span></span>

<span data-ttu-id="b5e8d-108">Атрибуты, дочерние и родительские элементы в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="b5e8d-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b5e8d-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b5e8d-109">Attributes</span></span>

<span data-ttu-id="b5e8d-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="b5e8d-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b5e8d-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b5e8d-111">Child Elements</span></span>

<span data-ttu-id="b5e8d-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="b5e8d-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b5e8d-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b5e8d-113">Parent Elements</span></span>

|<span data-ttu-id="b5e8d-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="b5e8d-114">Element</span></span>|<span data-ttu-id="b5e8d-115">Описание</span><span class="sxs-lookup"><span data-stu-id="b5e8d-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b5e8d-116">Элемент EntrySelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="b5e8d-116">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="b5e8d-117">Определяет типы .NET, использующих эту запись или условие, которое должен существовать для данной записи для использования.</span><span class="sxs-lookup"><span data-stu-id="b5e8d-117">Defines the .NET types that use this entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b5e8d-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="b5e8d-118">Text Value</span></span>

<span data-ttu-id="b5e8d-119">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="b5e8d-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="b5e8d-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="b5e8d-120">Remarks</span></span>

<span data-ttu-id="b5e8d-121">Выбор наборов обычно используются, когда необходимо определить группу объектов, которые используются в нескольких представлениях.</span><span class="sxs-lookup"><span data-stu-id="b5e8d-121">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="b5e8d-122">Например можно создать представление таблицы и представления списка для одного набора объектов.</span><span class="sxs-lookup"><span data-stu-id="b5e8d-122">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="b5e8d-123">Дополнительные сведения об определении наборов выбора см. в разделе [определение задает объектов для представления](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="b5e8d-123">For more information about defining selection sets, see [Defining Sets of objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="b5e8d-124">При указании выбора для записи, невозможно указать имя типа.</span><span class="sxs-lookup"><span data-stu-id="b5e8d-124">If you specify a selection set for an entry, you cannot specify a type name.</span></span> <span data-ttu-id="b5e8d-125">Дополнительные сведения о том, как задать тип .NET, см. в разделе [элемент TypeName для EntrySelectedBy для TableRowEntry (формат)](./typename-element-for-entryselectedby-for-tablecontrol-format.md).</span><span class="sxs-lookup"><span data-stu-id="b5e8d-125">For more information about how to specify a .NET type, see [TypeName Element for EntrySelectedBy for TableRowEntry (Format)](./typename-element-for-entryselectedby-for-tablecontrol-format.md).</span></span>

<span data-ttu-id="b5e8d-126">Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="b5e8d-126">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b5e8d-127">См. также</span><span class="sxs-lookup"><span data-stu-id="b5e8d-127">See Also</span></span>

[<span data-ttu-id="b5e8d-128">Элемент EntrySelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="b5e8d-128">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="b5e8d-129">Определение наборов объектов для представления</span><span class="sxs-lookup"><span data-stu-id="b5e8d-129">Defining Sets of objects for a View</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="b5e8d-130">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="b5e8d-130">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="b5e8d-131">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5e8d-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
