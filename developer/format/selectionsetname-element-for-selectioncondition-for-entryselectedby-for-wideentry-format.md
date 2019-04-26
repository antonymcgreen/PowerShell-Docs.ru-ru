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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62075483"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="376b3-102">Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="376b3-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="376b3-103">Указывает набор типов .NET, которые активируют условие.</span><span class="sxs-lookup"><span data-stu-id="376b3-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="376b3-104">При наличии любого из типов в этом наборе, условие выполняется, и объект отображается с использованием этого определения широкое представление.</span><span class="sxs-lookup"><span data-stu-id="376b3-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this definition of the wide view.</span></span>

<span data-ttu-id="376b3-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент WideControl (формат) элемент WideEntries (формат) элемент WideEntry (формат) EntrySelectedBy элемент конфигурации для элемент SelectionCondition WideEntry (формат) для EntrySelectedBy элемента SelectionSetName WideEntry (формат) для SelectionCondition для EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="376b3-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="376b3-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="376b3-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="376b3-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="376b3-107">Attributes and Elements</span></span>

<span data-ttu-id="376b3-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемент.</span><span class="sxs-lookup"><span data-stu-id="376b3-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="376b3-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="376b3-109">Attributes</span></span>

<span data-ttu-id="376b3-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="376b3-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="376b3-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="376b3-111">Child Elements</span></span>

<span data-ttu-id="376b3-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="376b3-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="376b3-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="376b3-113">Parent Elements</span></span>

|<span data-ttu-id="376b3-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="376b3-114">Element</span></span>|<span data-ttu-id="376b3-115">Описание</span><span class="sxs-lookup"><span data-stu-id="376b3-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="376b3-116">Элемент SelectionCondition для EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="376b3-116">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="376b3-117">Определяет условие, которое должен существовать для данного определения для использования.</span><span class="sxs-lookup"><span data-stu-id="376b3-117">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="376b3-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="376b3-118">Text Value</span></span>

<span data-ttu-id="376b3-119">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="376b3-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="376b3-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="376b3-120">Remarks</span></span>

<span data-ttu-id="376b3-121">Условию выбора можно указать набора или типа .NET Framework, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="376b3-121">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="376b3-122">Дополнительные сведения об использовании условий выборки см. в разделе [определение условий при отображении данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="376b3-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="376b3-123">Выбор наборов представляют собой общие группы объектов .NET, которые могут использоваться с любого представления, который определяет файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="376b3-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="376b3-124">Дополнительные сведения о создании и ссылки на наборы выделения см. в разделе [определение задает объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="376b3-124">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="376b3-125">Дополнительные сведения о других компонентах широкое представление, см. в разделе [Создание широкое представление](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="376b3-125">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="376b3-126">См. также</span><span class="sxs-lookup"><span data-stu-id="376b3-126">See Also</span></span>

[<span data-ttu-id="376b3-127">Создание широкое представление</span><span class="sxs-lookup"><span data-stu-id="376b3-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="376b3-128">Определение условия при отображении данных</span><span class="sxs-lookup"><span data-stu-id="376b3-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="376b3-129">Определение наборов Выбор</span><span class="sxs-lookup"><span data-stu-id="376b3-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="376b3-130">Элемент SelectionCondition для EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="376b3-130">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="376b3-131">TypeName-элемент для SelectionCondition для EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="376b3-131">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="376b3-132">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="376b3-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
