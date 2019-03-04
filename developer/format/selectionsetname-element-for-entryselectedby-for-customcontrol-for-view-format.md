---
title: Элемент SelectionSetName для EntrySelectedBy для пользовательский элемент управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 859d2335-7fcd-4efd-b1cc-3d171e334c6b
caps.latest.revision: 7
ms.openlocfilehash: f4bf820be88919af43eeaf043b3ed8b9c06e1bf2
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855030"
---
# <a name="selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format"></a><span data-ttu-id="f6fe0-102">Элемент SelectionSetName для элемента EntrySelectedBy для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="f6fe0-102">SelectionSetName Element for EntrySelectedBy for CustomControl for View (Format)</span></span>

<span data-ttu-id="f6fe0-103">Задает набор объектов .NET для записи в списке.</span><span class="sxs-lookup"><span data-stu-id="f6fe0-103">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="f6fe0-104">Количество наборов выбора, которые можно задать для записи не ограничено.</span><span class="sxs-lookup"><span data-stu-id="f6fe0-104">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="f6fe0-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент пользовательский элемент управления (формат) CustomEntries элемент конфигурации для пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для EntrySelectedBy представление (формат) Элемент для CustomEntry для элемента представления (формат) SelectionSetName для EntrySelectedBy для CustomEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="f6fe0-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format) SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f6fe0-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f6fe0-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f6fe0-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f6fe0-107">Attributes and Elements</span></span>

<span data-ttu-id="f6fe0-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемент.</span><span class="sxs-lookup"><span data-stu-id="f6fe0-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f6fe0-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f6fe0-109">Attributes</span></span>

<span data-ttu-id="f6fe0-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="f6fe0-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f6fe0-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f6fe0-111">Child Elements</span></span>

<span data-ttu-id="f6fe0-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="f6fe0-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f6fe0-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f6fe0-113">Parent Elements</span></span>

|<span data-ttu-id="f6fe0-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="f6fe0-114">Element</span></span>|<span data-ttu-id="f6fe0-115">Описание</span><span class="sxs-lookup"><span data-stu-id="f6fe0-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f6fe0-116">Элемент EntrySelectedBy для CustomEntry для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f6fe0-116">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="f6fe0-117">Определяет типы .NET, использующих этот пользовательскую запись или условие, которое должен существовать для данной записи для использования.</span><span class="sxs-lookup"><span data-stu-id="f6fe0-117">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f6fe0-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="f6fe0-118">Text Value</span></span>

<span data-ttu-id="f6fe0-119">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="f6fe0-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="f6fe0-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="f6fe0-120">Remarks</span></span>

<span data-ttu-id="f6fe0-121">Каждая запись пользовательский элемент управления должен иметь по крайней мере одно имя типа, набора или Выбор условия, определенного.</span><span class="sxs-lookup"><span data-stu-id="f6fe0-121">Each custom control entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="f6fe0-122">Выбор наборов обычно используются, когда необходимо определить группу объектов, которые используются в нескольких представлениях.</span><span class="sxs-lookup"><span data-stu-id="f6fe0-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="f6fe0-123">Например можно создать представление таблицы и представления списка для одного набора объектов.</span><span class="sxs-lookup"><span data-stu-id="f6fe0-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="f6fe0-124">Дополнительные сведения об определении наборов выбора см. в разделе [определение выбора устанавливается](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="f6fe0-124">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="f6fe0-125">Дополнительные сведения о компонентах представления пользовательского элемента управления, см. в разделе [Создание пользовательских элементов управления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="f6fe0-125">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f6fe0-126">См. также</span><span class="sxs-lookup"><span data-stu-id="f6fe0-126">See Also</span></span>

[<span data-ttu-id="f6fe0-127">Элемент EntrySelectedBy для CustomEntry для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f6fe0-127">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="f6fe0-128">Представление пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="f6fe0-128">Custom Control View</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="f6fe0-129">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6fe0-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
