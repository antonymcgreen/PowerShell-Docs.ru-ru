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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62075517"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format"></a><span data-ttu-id="8a741-102">Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="8a741-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

<span data-ttu-id="8a741-103">Указывает набор типов .NET, которые активируют условие.</span><span class="sxs-lookup"><span data-stu-id="8a741-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="8a741-104">При наличии любого из типов в этом наборе, условие выполняется, и объект отображается с использованием этого определения представления "list".</span><span class="sxs-lookup"><span data-stu-id="8a741-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this definition of the list view.</span></span>

<span data-ttu-id="8a741-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемент (формат) элемента ListControl (формат) элемент ListEntries (формат) элемент ListEntry (формат) EntrySelectedBy элемент конфигурации для элемента SelectionCondition ListEntry (формат) для EntrySelectedBy элемента SelectionSetName ListEntry (формат) для SelectionCondition для EntrySelectedBy для ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="8a741-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8a741-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a741-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8a741-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8a741-107">Attributes and Elements</span></span>

<span data-ttu-id="8a741-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемент.</span><span class="sxs-lookup"><span data-stu-id="8a741-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8a741-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8a741-109">Attributes</span></span>

<span data-ttu-id="8a741-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="8a741-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8a741-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8a741-111">Child Elements</span></span>

<span data-ttu-id="8a741-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="8a741-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8a741-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8a741-113">Parent Elements</span></span>

|<span data-ttu-id="8a741-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="8a741-114">Element</span></span>|<span data-ttu-id="8a741-115">Описание</span><span class="sxs-lookup"><span data-stu-id="8a741-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8a741-116">Элемент SelectionCondition для EntrySelectedBy для ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="8a741-116">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="8a741-117">Определяет условие, которое должна существовать, чтобы использовать это определение представления "list".</span><span class="sxs-lookup"><span data-stu-id="8a741-117">Defines the condition that must exist to use this definition of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="8a741-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="8a741-118">Text Value</span></span>

<span data-ttu-id="8a741-119">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="8a741-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="8a741-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="8a741-120">Remarks</span></span>

<span data-ttu-id="8a741-121">Условию выбора можно указать набора или типа .NET Framework, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="8a741-121">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="8a741-122">Дополнительные сведения об использовании условий выборки см. в разделе [определение условий при отображении данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="8a741-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="8a741-123">Выбор наборов представляют собой общие группы объектов .NET, которые могут использоваться с любого представления, который определяет файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="8a741-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="8a741-124">Дополнительные сведения о создании и ссылки на наборы выделения см. в разделе [определение задает объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="8a741-124">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="8a741-125">Дополнительные сведения о других компонентах представления списка, см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="8a741-125">For more information about other components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8a741-126">См. также</span><span class="sxs-lookup"><span data-stu-id="8a741-126">See Also</span></span>

[<span data-ttu-id="8a741-127">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="8a741-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="8a741-128">Определение условия при отображении данных</span><span class="sxs-lookup"><span data-stu-id="8a741-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="8a741-129">Элемент SelectionCondition для EntrySelectedBy для ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="8a741-129">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="8a741-130">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a741-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
