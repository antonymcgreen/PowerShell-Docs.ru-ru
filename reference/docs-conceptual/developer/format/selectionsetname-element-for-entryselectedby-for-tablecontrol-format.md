---
title: Элемент Селектионсетнаме для Ентриселектедби для Таблеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5dd0bd5d-f206-4cc6-a0f8-70700ee2c4b7
caps.latest.revision: 8
ms.openlocfilehash: 819906127e81355c45103ede85ef3608e1c1cfeb
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368323"
---
# <a name="selectionsetname-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="741fd-102">Элемент SelectionSetName для элемента EntrySelectedBy для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="741fd-102">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="741fd-103">Указывает набор типов .NET, которые использует эту запись табличного представления.</span><span class="sxs-lookup"><span data-stu-id="741fd-103">Specifies a set of .NET types the use this entry of the table view.</span></span> <span data-ttu-id="741fd-104">Количество наборов выбора, которые можно указать для записи, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="741fd-104">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="741fd-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Ентриселектедби элемент (Format) Селектионсетнаме элемент для Ентриселектедби для Таблеровентри (формат)</span><span class="sxs-lookup"><span data-stu-id="741fd-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format) SelectionSetName Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="741fd-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="741fd-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="741fd-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="741fd-107">Attributes and Elements</span></span>

<span data-ttu-id="741fd-108">В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="741fd-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="741fd-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="741fd-109">Attributes</span></span>

<span data-ttu-id="741fd-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="741fd-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="741fd-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="741fd-111">Child Elements</span></span>

<span data-ttu-id="741fd-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="741fd-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="741fd-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="741fd-113">Parent Elements</span></span>

|<span data-ttu-id="741fd-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="741fd-114">Element</span></span>|<span data-ttu-id="741fd-115">Описание</span><span class="sxs-lookup"><span data-stu-id="741fd-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="741fd-116">Элемент Ентриселектедби (Format)</span><span class="sxs-lookup"><span data-stu-id="741fd-116">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="741fd-117">Определяет типы .NET, которые используют эту запись, или условие, которое должно существовать для использования этой записи.</span><span class="sxs-lookup"><span data-stu-id="741fd-117">Defines the .NET types that use this entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="741fd-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="741fd-118">Text Value</span></span>

<span data-ttu-id="741fd-119">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="741fd-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="741fd-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="741fd-120">Remarks</span></span>

<span data-ttu-id="741fd-121">Наборы выбора обычно используются, если требуется определить группу объектов, используемых в нескольких представлениях.</span><span class="sxs-lookup"><span data-stu-id="741fd-121">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="741fd-122">Например, может потребоваться создать табличное представление и представление списка для одного и того же набора объектов.</span><span class="sxs-lookup"><span data-stu-id="741fd-122">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="741fd-123">Дополнительные сведения об определении наборов выбора см. [в разделе Определение наборов объектов для представления](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="741fd-123">For more information about defining selection sets, see [Defining Sets of objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="741fd-124">Если для записи указан набор элементов, то нельзя указать имя типа.</span><span class="sxs-lookup"><span data-stu-id="741fd-124">If you specify a selection set for an entry, you cannot specify a type name.</span></span> <span data-ttu-id="741fd-125">Дополнительные сведения об указании типа .NET см. в разделе [элемент TypeName для ентриселектедби для таблеровентри (Format)](./typename-element-for-entryselectedby-for-tablecontrol-format.md).</span><span class="sxs-lookup"><span data-stu-id="741fd-125">For more information about how to specify a .NET type, see [TypeName Element for EntrySelectedBy for TableRowEntry (Format)](./typename-element-for-entryselectedby-for-tablecontrol-format.md).</span></span>

<span data-ttu-id="741fd-126">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="741fd-126">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="741fd-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="741fd-127">See Also</span></span>

[<span data-ttu-id="741fd-128">Элемент Ентриселектедби (Format)</span><span class="sxs-lookup"><span data-stu-id="741fd-128">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="741fd-129">Определение наборов объектов для представления</span><span class="sxs-lookup"><span data-stu-id="741fd-129">Defining Sets of objects for a View</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="741fd-130">Создание табличного представления</span><span class="sxs-lookup"><span data-stu-id="741fd-130">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="741fd-131">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="741fd-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
