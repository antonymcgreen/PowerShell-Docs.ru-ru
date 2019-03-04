---
title: Элемент SelectionSetName для SelectionCondition для EntrySelectedBy для WideEntry (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a13a429c-a31b-4e29-828c-c0c0917b5415
caps.latest.revision: 11
ms.openlocfilehash: baea89e4b259611dfa45b6bcf94fa0bf2df6b9de
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854130"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="e02fe-102">Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="e02fe-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="e02fe-103">Указывает набор типов .NET, которые активируют условие.</span><span class="sxs-lookup"><span data-stu-id="e02fe-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="e02fe-104">При наличии любого из типов в этом наборе, условие выполняется, и объект отображается с использованием этого определения широкое представление.</span><span class="sxs-lookup"><span data-stu-id="e02fe-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this definition of the wide view.</span></span>

<span data-ttu-id="e02fe-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент WideControl (формат) элемент WideEntries (формат) элемент WideEntry (формат) EntrySelectedBy элемент конфигурации для элемент SelectionCondition WideEntry (формат) для EntrySelectedBy элемента SelectionSetName WideEntry (формат) для SelectionCondition для EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="e02fe-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e02fe-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e02fe-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e02fe-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e02fe-107">Attributes and Elements</span></span>

<span data-ttu-id="e02fe-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемент.</span><span class="sxs-lookup"><span data-stu-id="e02fe-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e02fe-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e02fe-109">Attributes</span></span>

<span data-ttu-id="e02fe-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="e02fe-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e02fe-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e02fe-111">Child Elements</span></span>

<span data-ttu-id="e02fe-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="e02fe-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e02fe-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e02fe-113">Parent Elements</span></span>

|<span data-ttu-id="e02fe-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="e02fe-114">Element</span></span>|<span data-ttu-id="e02fe-115">Описание</span><span class="sxs-lookup"><span data-stu-id="e02fe-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e02fe-116">Элемент SelectionCondition для EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="e02fe-116">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="e02fe-117">Определяет условие, которое должен существовать для данного определения для использования.</span><span class="sxs-lookup"><span data-stu-id="e02fe-117">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e02fe-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="e02fe-118">Text Value</span></span>

<span data-ttu-id="e02fe-119">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="e02fe-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="e02fe-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="e02fe-120">Remarks</span></span>

<span data-ttu-id="e02fe-121">Условию выбора можно указать набора или типа .NET Framework, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="e02fe-121">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="e02fe-122">Дополнительные сведения об использовании условий выборки см. в разделе [определение условий при отображении данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="e02fe-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="e02fe-123">Выбор наборов представляют собой общие группы объектов .NET, которые могут использоваться с любого представления, который определяет файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="e02fe-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="e02fe-124">Дополнительные сведения о создании и ссылки на наборы выделения см. в разделе [определение задает объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="e02fe-124">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="e02fe-125">Дополнительные сведения о других компонентах широкое представление, см. в разделе [Создание широкое представление](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="e02fe-125">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e02fe-126">См. также</span><span class="sxs-lookup"><span data-stu-id="e02fe-126">See Also</span></span>

[<span data-ttu-id="e02fe-127">Создание широкое представление</span><span class="sxs-lookup"><span data-stu-id="e02fe-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="e02fe-128">Определение условия при отображении данных</span><span class="sxs-lookup"><span data-stu-id="e02fe-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="e02fe-129">Определение наборов Выбор</span><span class="sxs-lookup"><span data-stu-id="e02fe-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="e02fe-130">Элемент SelectionCondition для EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="e02fe-130">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="e02fe-131">TypeName-элемент для SelectionCondition для EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="e02fe-131">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="e02fe-132">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="e02fe-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
