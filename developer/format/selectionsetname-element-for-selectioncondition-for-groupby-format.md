---
title: Элемент SelectionSetName для SelectionCondition для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b9a4912-d755-42f3-8058-53c0797e28e4
caps.latest.revision: 6
ms.openlocfilehash: 371913eda2b09ff6788494b68738f2ad53ccb115
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856760"
---
# <a name="selectionsetname-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="05ebd-102">Элемент SelectionSetName для элемента SelectionCondition для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="05ebd-102">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="05ebd-103">Указывает набор типов .NET, которые активируют условие.</span><span class="sxs-lookup"><span data-stu-id="05ebd-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="05ebd-104">При наличии любого из типов в этом наборе, условие выполняется, и объект отображается с помощью этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="05ebd-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this control.</span></span> <span data-ttu-id="05ebd-105">Этот элемент используется при определении того, как отображается группу объектов.</span><span class="sxs-lookup"><span data-stu-id="05ebd-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="05ebd-106">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) пользовательский элемент управления для элемента CustomEntries GroupBy (формат) пользовательский элемент управления для элемента CustomEntry GroupBy (формат) Пользовательский элемент управления для элемента EntrySelectedBy GroupBy (формат) для CustomEntry элемента SelectionCondition GroupBy (формат) для EntrySelectedBy элемента SelectionSetName GroupBy (формат) для SelectionCondition для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="05ebd-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="05ebd-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="05ebd-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="05ebd-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="05ebd-108">Attributes and Elements</span></span>

<span data-ttu-id="05ebd-109">Ниже описаны атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемент.</span><span class="sxs-lookup"><span data-stu-id="05ebd-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="05ebd-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="05ebd-110">Attributes</span></span>

<span data-ttu-id="05ebd-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="05ebd-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="05ebd-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="05ebd-112">Child Elements</span></span>

<span data-ttu-id="05ebd-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="05ebd-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="05ebd-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="05ebd-114">Parent Elements</span></span>

|<span data-ttu-id="05ebd-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="05ebd-115">Element</span></span>|<span data-ttu-id="05ebd-116">Описание</span><span class="sxs-lookup"><span data-stu-id="05ebd-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="05ebd-117">Элемент SelectionCondition для EntrySelectedBy для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="05ebd-117">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="05ebd-118">Определяет условие, которое должен существовать для определение элемента управления для использования.</span><span class="sxs-lookup"><span data-stu-id="05ebd-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="05ebd-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="05ebd-119">Text Value</span></span>

<span data-ttu-id="05ebd-120">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="05ebd-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="05ebd-121">Замечания</span><span class="sxs-lookup"><span data-stu-id="05ebd-121">Remarks</span></span>

<span data-ttu-id="05ebd-122">Выбор наборов представляют собой общие группы объектов .NET, которые могут использоваться с любого представления, который определяет файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="05ebd-122">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="05ebd-123">Дополнительные сведения о создании и ссылки на наборы выделения см. в разделе [определение выбора устанавливается](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="05ebd-123">For more information about creating and referencing selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="05ebd-124">Если этот элемент указан, нельзя указать [TypeName](./typename-element-for-selectioncondition-for-groupby-format.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="05ebd-124">When this element is specified, you cannot specify the [TypeName](./typename-element-for-selectioncondition-for-groupby-format.md) element.</span></span> <span data-ttu-id="05ebd-125">Дополнительные сведения об определении условий выборки см. в разделе [определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="05ebd-125">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="05ebd-126">См. также</span><span class="sxs-lookup"><span data-stu-id="05ebd-126">See Also</span></span>

[<span data-ttu-id="05ebd-127">TypeName-элемент для SelectionCondition для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="05ebd-127">TypeName Element for SelectionCondition for GroupBy (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)

[<span data-ttu-id="05ebd-128">Элемент SelectionCondition для EntrySelectedBy для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="05ebd-128">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="05ebd-129">Определение условия при отображении данных</span><span class="sxs-lookup"><span data-stu-id="05ebd-129">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="05ebd-130">Определение наборов Выбор</span><span class="sxs-lookup"><span data-stu-id="05ebd-130">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="05ebd-131">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="05ebd-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
