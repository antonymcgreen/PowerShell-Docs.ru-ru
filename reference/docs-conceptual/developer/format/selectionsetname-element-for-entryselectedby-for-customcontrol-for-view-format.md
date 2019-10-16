---
title: Элемент Селектионсетнаме для Ентриселектедби для ошибка customcontrol для представления (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 859d2335-7fcd-4efd-b1cc-3d171e334c6b
caps.latest.revision: 7
ms.openlocfilehash: f4bf820be88919af43eeaf043b3ed8b9c06e1bf2
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364753"
---
# <a name="selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format"></a><span data-ttu-id="e905b-102">Элемент SelectionSetName для элемента EntrySelectedBy для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="e905b-102">SelectionSetName Element for EntrySelectedBy for CustomControl for View (Format)</span></span>

<span data-ttu-id="e905b-103">Задает набор объектов .NET для записи списка.</span><span class="sxs-lookup"><span data-stu-id="e905b-103">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="e905b-104">Количество наборов выбора, которые можно указать для записи, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="e905b-104">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="e905b-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ошибка customcontrol элемент (Format) Кустоментриес для ошибка customcontrol для элемента представления (Format) Кустоментри для Кустоментриес для представления (Format) Ентриселектедби Элемент для Кустоментри для элемента Селектионсетнаме представления (Format) для Ентриселектедби для Кустоментри (Format)</span><span class="sxs-lookup"><span data-stu-id="e905b-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format) SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e905b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e905b-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e905b-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e905b-107">Attributes and Elements</span></span>

<span data-ttu-id="e905b-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `SelectionSetName`.</span><span class="sxs-lookup"><span data-stu-id="e905b-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e905b-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e905b-109">Attributes</span></span>

<span data-ttu-id="e905b-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="e905b-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e905b-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e905b-111">Child Elements</span></span>

<span data-ttu-id="e905b-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="e905b-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e905b-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e905b-113">Parent Elements</span></span>

|<span data-ttu-id="e905b-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="e905b-114">Element</span></span>|<span data-ttu-id="e905b-115">Описание</span><span class="sxs-lookup"><span data-stu-id="e905b-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e905b-116">Элемент Ентриселектедби для Кустоментри для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="e905b-116">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="e905b-117">Определяет типы .NET, которые используют эту настраиваемую запись, или условие, которое должно существовать для использования этой записи.</span><span class="sxs-lookup"><span data-stu-id="e905b-117">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e905b-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="e905b-118">Text Value</span></span>

<span data-ttu-id="e905b-119">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="e905b-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="e905b-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="e905b-120">Remarks</span></span>

<span data-ttu-id="e905b-121">Для каждой записи пользовательского элемента управления должно быть определено по крайней мере одно имя типа, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="e905b-121">Each custom control entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="e905b-122">Наборы выбора обычно используются, если требуется определить группу объектов, используемых в нескольких представлениях.</span><span class="sxs-lookup"><span data-stu-id="e905b-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="e905b-123">Например, может потребоваться создать табличное представление и представление списка для одного и того же набора объектов.</span><span class="sxs-lookup"><span data-stu-id="e905b-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="e905b-124">Дополнительные сведения об определении наборов выбора см. в разделе [Определение наборов выбора](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="e905b-124">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="e905b-125">Дополнительные сведения о компонентах представления пользовательского элемента управления см. в разделе [Создание пользовательских элементов управления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="e905b-125">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e905b-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="e905b-126">See Also</span></span>

[<span data-ttu-id="e905b-127">Элемент Ентриселектедби для Кустоментри для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="e905b-127">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e905b-128">Представление пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="e905b-128">Custom Control View</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="e905b-129">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="e905b-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
