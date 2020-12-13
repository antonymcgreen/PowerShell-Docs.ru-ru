---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент SelectionSetName для элемента EntrySelectedBy для элемента CustomControl для элемента View (формат)
description: Элемент SelectionSetName для элемента EntrySelectedBy для элемента CustomControl для элемента View (формат)
ms.openlocfilehash: a158c5476fb3a168a146ce67565c0ed6f7859519
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651909"
---
# <a name="selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format"></a><span data-ttu-id="57545-103">Элемент SelectionSetName для элемента EntrySelectedBy для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="57545-103">SelectionSetName Element for EntrySelectedBy for CustomControl for View (Format)</span></span>

<span data-ttu-id="57545-104">Задает набор объектов .NET для записи списка.</span><span class="sxs-lookup"><span data-stu-id="57545-104">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="57545-105">Количество наборов выбора, которые можно указать для записи, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="57545-105">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="57545-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ошибка customcontrol элемент (Format) Кустоментриес для ошибка customcontrol для элемента кустоментри представления для кустоментриес для представления (Format) ентриселектедби для кустоментри для SelectionSetName for EntrySelectedBy (формат).</span><span class="sxs-lookup"><span data-stu-id="57545-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format) SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="57545-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="57545-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="57545-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="57545-108">Attributes and Elements</span></span>

<span data-ttu-id="57545-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемента.</span><span class="sxs-lookup"><span data-stu-id="57545-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="57545-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="57545-110">Attributes</span></span>

<span data-ttu-id="57545-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="57545-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="57545-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="57545-112">Child Elements</span></span>

<span data-ttu-id="57545-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="57545-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="57545-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="57545-114">Parent Elements</span></span>

|<span data-ttu-id="57545-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="57545-115">Element</span></span>|<span data-ttu-id="57545-116">Описание</span><span class="sxs-lookup"><span data-stu-id="57545-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="57545-117">Элемент Ентриселектедби для Кустоментри для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="57545-117">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="57545-118">Определяет типы .NET, которые используют эту настраиваемую запись, или условие, которое должно существовать для использования этой записи.</span><span class="sxs-lookup"><span data-stu-id="57545-118">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="57545-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="57545-119">Text Value</span></span>

<span data-ttu-id="57545-120">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="57545-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="57545-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="57545-121">Remarks</span></span>

<span data-ttu-id="57545-122">Для каждой записи пользовательского элемента управления должно быть определено по крайней мере одно имя типа, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="57545-122">Each custom control entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="57545-123">Наборы выбора обычно используются, если требуется определить группу объектов, используемых в нескольких представлениях.</span><span class="sxs-lookup"><span data-stu-id="57545-123">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="57545-124">Например, может потребоваться создать табличное представление и представление списка для одного и того же набора объектов.</span><span class="sxs-lookup"><span data-stu-id="57545-124">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="57545-125">Дополнительные сведения об определении наборов выбора см. в разделе [Определение наборов выбора](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="57545-125">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="57545-126">Дополнительные сведения о компонентах представления пользовательского элемента управления см. в разделе [Создание пользовательских элементов управления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="57545-126">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="57545-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="57545-127">See Also</span></span>

[<span data-ttu-id="57545-128">Элемент Ентриселектедби для Кустоментри для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="57545-128">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="57545-129">Представление пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="57545-129">Custom Control View</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="57545-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="57545-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
