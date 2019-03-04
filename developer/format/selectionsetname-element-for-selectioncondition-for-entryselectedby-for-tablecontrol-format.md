---
title: Элемент SelectionSetName для SelectionCondition для EntrySelectedBy для TableControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17ae4d6b-dc95-4a1d-8e32-31ff084a951f
caps.latest.revision: 10
ms.openlocfilehash: edb163f2b0b5129bd741677dce882888d9bbfd89
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56863280"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="c0239-102">Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="c0239-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="c0239-103">Указывает набор типов .NET, которые активируют условие.</span><span class="sxs-lookup"><span data-stu-id="c0239-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="c0239-104">При наличии любого из типов в этом наборе, условие выполняется, и объект отображается с использованием этого определения представления таблицы.</span><span class="sxs-lookup"><span data-stu-id="c0239-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this definition of the table view.</span></span>

<span data-ttu-id="c0239-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) элемент TableRowEntries (формат) элемент TableRowEntry (формат) EntrySelectedBy элемент конфигурации для TableRowEntry (формат) Элемент SelectionCondition для EntrySelectedBy для элемента SelectionSetName TableRowEntry (формат) SelectionCondition для EntrySelectedBy для TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="c0239-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c0239-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c0239-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c0239-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c0239-107">Attributes and Elements</span></span>

<span data-ttu-id="c0239-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемент.</span><span class="sxs-lookup"><span data-stu-id="c0239-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c0239-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c0239-109">Attributes</span></span>

<span data-ttu-id="c0239-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="c0239-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c0239-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c0239-111">Child Elements</span></span>

<span data-ttu-id="c0239-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="c0239-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c0239-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c0239-113">Parent Elements</span></span>

|<span data-ttu-id="c0239-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="c0239-114">Element</span></span>|<span data-ttu-id="c0239-115">Описание</span><span class="sxs-lookup"><span data-stu-id="c0239-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c0239-116">Элемент SelectionCondition для EntrySelectedBy для TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="c0239-116">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="c0239-117">Определяет условие, которое должен существовать для этого определения представления таблицы.</span><span class="sxs-lookup"><span data-stu-id="c0239-117">Defines the condition that must exist to use for this definition of the table view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c0239-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="c0239-118">Text Value</span></span>

<span data-ttu-id="c0239-119">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="c0239-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="c0239-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="c0239-120">Remarks</span></span>

<span data-ttu-id="c0239-121">Условию выбора можно указать набора или типа .NET Framework, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="c0239-121">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="c0239-122">Дополнительные сведения об использовании условий выборки см. в разделе [определение условий при отображении данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="c0239-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="c0239-123">Выбор наборов представляют собой общие группы объектов .NET, которые могут использоваться с любого представления, который определяет файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="c0239-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="c0239-124">Дополнительные сведения о создании и ссылки на наборы выделения см. в разделе [определение задает объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="c0239-124">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="c0239-125">Дополнительные сведения о других компонентах широкое представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="c0239-125">For more information about other components of a wide view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c0239-126">См. также</span><span class="sxs-lookup"><span data-stu-id="c0239-126">See Also</span></span>

[<span data-ttu-id="c0239-127">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="c0239-127">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="c0239-128">Определение условия при отображении данных</span><span class="sxs-lookup"><span data-stu-id="c0239-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="c0239-129">TypeName-элемент для SelectionCondition для EntrySelectedBy для TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="c0239-129">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="c0239-130">Элемент SelectionCondition для EntrySelectedBy для TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="c0239-130">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="c0239-131">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="c0239-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
