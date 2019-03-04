---
title: Элемент SelectionSetName для SelectionCondition для EntrySelectedBy для ListEntry (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eae67e47-6c60-4741-8430-78d2cb6067b1
caps.latest.revision: 10
ms.openlocfilehash: ccfc0b772ad3b2d1979c7c832a5153de870035d7
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862200"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format"></a><span data-ttu-id="92bf9-102">Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="92bf9-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

<span data-ttu-id="92bf9-103">Указывает набор типов .NET, которые активируют условие.</span><span class="sxs-lookup"><span data-stu-id="92bf9-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="92bf9-104">При наличии любого из типов в этом наборе, условие выполняется, и объект отображается с использованием этого определения представления "list".</span><span class="sxs-lookup"><span data-stu-id="92bf9-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this definition of the list view.</span></span>

<span data-ttu-id="92bf9-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемент (формат) элемента ListControl (формат) элемент ListEntries (формат) элемент ListEntry (формат) EntrySelectedBy элемент конфигурации для элемента SelectionCondition ListEntry (формат) для EntrySelectedBy элемента SelectionSetName ListEntry (формат) для SelectionCondition для EntrySelectedBy для ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="92bf9-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="92bf9-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="92bf9-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="92bf9-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="92bf9-107">Attributes and Elements</span></span>

<span data-ttu-id="92bf9-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемент.</span><span class="sxs-lookup"><span data-stu-id="92bf9-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="92bf9-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="92bf9-109">Attributes</span></span>

<span data-ttu-id="92bf9-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="92bf9-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="92bf9-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="92bf9-111">Child Elements</span></span>

<span data-ttu-id="92bf9-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="92bf9-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="92bf9-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="92bf9-113">Parent Elements</span></span>

|<span data-ttu-id="92bf9-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="92bf9-114">Element</span></span>|<span data-ttu-id="92bf9-115">Описание</span><span class="sxs-lookup"><span data-stu-id="92bf9-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="92bf9-116">Элемент SelectionCondition для EntrySelectedBy для ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="92bf9-116">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="92bf9-117">Определяет условие, которое должна существовать, чтобы использовать это определение представления "list".</span><span class="sxs-lookup"><span data-stu-id="92bf9-117">Defines the condition that must exist to use this definition of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="92bf9-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="92bf9-118">Text Value</span></span>

<span data-ttu-id="92bf9-119">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="92bf9-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="92bf9-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="92bf9-120">Remarks</span></span>

<span data-ttu-id="92bf9-121">Условию выбора можно указать набора или типа .NET Framework, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="92bf9-121">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="92bf9-122">Дополнительные сведения об использовании условий выборки см. в разделе [определение условий при отображении данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="92bf9-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="92bf9-123">Выбор наборов представляют собой общие группы объектов .NET, которые могут использоваться с любого представления, который определяет файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="92bf9-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="92bf9-124">Дополнительные сведения о создании и ссылки на наборы выделения см. в разделе [определение задает объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="92bf9-124">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="92bf9-125">Дополнительные сведения о других компонентах представления списка, см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="92bf9-125">For more information about other components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="92bf9-126">См. также</span><span class="sxs-lookup"><span data-stu-id="92bf9-126">See Also</span></span>

[<span data-ttu-id="92bf9-127">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="92bf9-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="92bf9-128">Определение условия при отображении данных</span><span class="sxs-lookup"><span data-stu-id="92bf9-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="92bf9-129">Элемент SelectionCondition для EntrySelectedBy для ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="92bf9-129">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="92bf9-130">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="92bf9-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
