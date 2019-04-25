---
title: Элемент SelectionSetName для SelectionCondition для пользовательский элемент управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a52b05a9-762e-4f1c-ad57-9d1710149722
caps.latest.revision: 10
ms.openlocfilehash: 25d46665ca5df3ddf49af5718d513b84c77988c8
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62075585"
---
# <a name="selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="ea3d2-102">Элемент SelectionSetName для элемента SelectionCondition для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="ea3d2-102">SelectionSetName Element for SelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="ea3d2-103">Указывает набор типов .NET, которые активируют условие.</span><span class="sxs-lookup"><span data-stu-id="ea3d2-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="ea3d2-104">При наличии любого из типов в этом наборе, условие выполняется, и объект отображается с помощью этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ea3d2-104">When any of the types in this set are present, the condition is met and the object is displayed using this control.</span></span> <span data-ttu-id="ea3d2-105">Этот элемент используется при определении представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ea3d2-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="ea3d2-106">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент пользовательский элемент управления (формат) CustomEntries элемент конфигурации для пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для EntrySelectedBy представление (формат) Элемент для CustomEntry для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="ea3d2-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ea3d2-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ea3d2-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ea3d2-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ea3d2-108">Attributes and Elements</span></span>

<span data-ttu-id="ea3d2-109">Ниже описаны атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемент.</span><span class="sxs-lookup"><span data-stu-id="ea3d2-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ea3d2-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ea3d2-110">Attributes</span></span>

<span data-ttu-id="ea3d2-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="ea3d2-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ea3d2-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ea3d2-112">Child Elements</span></span>

<span data-ttu-id="ea3d2-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="ea3d2-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ea3d2-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ea3d2-114">Parent Elements</span></span>

|<span data-ttu-id="ea3d2-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="ea3d2-115">Element</span></span>|<span data-ttu-id="ea3d2-116">Описание</span><span class="sxs-lookup"><span data-stu-id="ea3d2-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ea3d2-117">Элемент SelectionCondition для EntrySelectedBy для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="ea3d2-117">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="ea3d2-118">Определяет условие, которое должен существовать для определение элемента управления для использования.</span><span class="sxs-lookup"><span data-stu-id="ea3d2-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ea3d2-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="ea3d2-119">Text Value</span></span>

<span data-ttu-id="ea3d2-120">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="ea3d2-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="ea3d2-121">Замечания</span><span class="sxs-lookup"><span data-stu-id="ea3d2-121">Remarks</span></span>

<span data-ttu-id="ea3d2-122">Выбор наборов представляют собой общие группы объектов .NET, которые могут использоваться с любого представления, который определяет файл форматирования.</span><span class="sxs-lookup"><span data-stu-id="ea3d2-122">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="ea3d2-123">Дополнительные сведения о создании и ссылки на наборы выделения см. в разделе [определение задает объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="ea3d2-123">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="ea3d2-124">Условию выбора можно указать набора или типа .NET Framework, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="ea3d2-124">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="ea3d2-125">Дополнительные сведения об использовании условий выборки см. в разделе [определение условий при отображении данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="ea3d2-125">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ea3d2-126">См. также</span><span class="sxs-lookup"><span data-stu-id="ea3d2-126">See Also</span></span>

[<span data-ttu-id="ea3d2-127">Элемент SelectionCondition для EntrySelectedBy для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="ea3d2-127">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="ea3d2-128">Определение условия при отображении данных</span><span class="sxs-lookup"><span data-stu-id="ea3d2-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="ea3d2-129">Определение наборов Выбор</span><span class="sxs-lookup"><span data-stu-id="ea3d2-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="ea3d2-130">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="ea3d2-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
