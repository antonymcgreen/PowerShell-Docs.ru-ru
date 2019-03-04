---
title: Элемент SelectionCondition для EntrySelectedBy для EnumerableExpansion (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8c012115-9241-4851-9015-841eb508faf3
caps.latest.revision: 10
ms.openlocfilehash: d6adf2fa62384d671fd6a07dd185a941daa44cec
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858290"
---
# <a name="selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="0e85b-102">Элемент SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="0e85b-102">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="0e85b-103">Определяет условие, которое должно существовать разверните коллекцию объектов данного определения.</span><span class="sxs-lookup"><span data-stu-id="0e85b-103">Defines the condition that must exist to expand the collection objects of this definition.</span></span>

<span data-ttu-id="0e85b-104">Элемент (формат) элемент DefaultSettings (формат) элемент EnumerableExpansions (формат) элемент EnumerableExpansion (формат) EntrySelectedBy элемента конфигурации для элемента SelectionCondition EnumerableExpansion (формат) EntrySelectedBy для EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="0e85b-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0e85b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0e85b-105">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0e85b-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0e85b-106">Attributes and Elements</span></span>

<span data-ttu-id="0e85b-107">Ниже описаны атрибуты, дочерние элементы и родительский элемент `SelectionCondition` элемент.</span><span class="sxs-lookup"><span data-stu-id="0e85b-107">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span> <span data-ttu-id="0e85b-108">Необходимо указать один `PropertyName` или `ScriptBlock` элемент.</span><span class="sxs-lookup"><span data-stu-id="0e85b-108">You must specify a single `PropertyName` or `ScriptBlock` element.</span></span> <span data-ttu-id="0e85b-109">`SelectionSetName` И `TypeName` элементы являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="0e85b-109">The `SelectionSetName` and `TypeName` elements are optional.</span></span> <span data-ttu-id="0e85b-110">Можно указать один из любой из элементов.</span><span class="sxs-lookup"><span data-stu-id="0e85b-110">You can specify one of either element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0e85b-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0e85b-111">Attributes</span></span>

<span data-ttu-id="0e85b-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="0e85b-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0e85b-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0e85b-113">Child Elements</span></span>

|<span data-ttu-id="0e85b-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="0e85b-114">Element</span></span>|<span data-ttu-id="0e85b-115">Описание</span><span class="sxs-lookup"><span data-stu-id="0e85b-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0e85b-116">Элемент PropertyName для SelectionCondition для EntrySelectedBy для EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="0e85b-116">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="0e85b-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="0e85b-117">Optional element.</span></span><br /><br /> <span data-ttu-id="0e85b-118">Задает свойство .NET, которое активирует условие.</span><span class="sxs-lookup"><span data-stu-id="0e85b-118">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="0e85b-119">Элемент ScriptBlock для SelectionCondition для EntrySelectedBy для EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="0e85b-119">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="0e85b-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="0e85b-120">Optional element.</span></span><br /><br /> <span data-ttu-id="0e85b-121">Указывает сценарий, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="0e85b-121">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="0e85b-122">Элемент SelectionSetName для SelectionCondition для EntrySelectedBy для EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="0e85b-122">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="0e85b-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="0e85b-123">Optional element.</span></span><br /><br /> <span data-ttu-id="0e85b-124">Указывает набор типов .NET, которые инициируют условие.</span><span class="sxs-lookup"><span data-stu-id="0e85b-124">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="0e85b-125">TypeName-элемент для SelectionCondition для EntrySelectedBy для EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="0e85b-125">TypeName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="0e85b-126">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="0e85b-126">Optional element.</span></span><br /><br /> <span data-ttu-id="0e85b-127">Указывает тип .NET, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="0e85b-127">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="0e85b-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0e85b-128">Parent Elements</span></span>

|<span data-ttu-id="0e85b-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="0e85b-129">Element</span></span>|<span data-ttu-id="0e85b-130">Описание</span><span class="sxs-lookup"><span data-stu-id="0e85b-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0e85b-131">Элемент EntrySelectedBy для EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="0e85b-131">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="0e85b-132">Определяет, какие объекты коллекции .NET расширяются согласно этому определению.</span><span class="sxs-lookup"><span data-stu-id="0e85b-132">Defines which .NET collection objects are expanded by this definition.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0e85b-133">Замечания</span><span class="sxs-lookup"><span data-stu-id="0e85b-133">Remarks</span></span>

<span data-ttu-id="0e85b-134">Каждое определение должно иметь, по крайней мере одно имя типа, выбора или условия выбора, определенного.</span><span class="sxs-lookup"><span data-stu-id="0e85b-134">Each definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="0e85b-135">При определении условию выбора, применяются следующие требования:</span><span class="sxs-lookup"><span data-stu-id="0e85b-135">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="0e85b-136">Условию выбора, необходимо указать имя как минимум одно свойство или блок скрипта, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="0e85b-136">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="0e85b-137">Условию выбора можно указать любое число типов .NET или выбора задает, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="0e85b-137">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="0e85b-138">Дополнительные сведения об использовании условий выборки см. в разделе [определения условия для данных Diplaying](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="0e85b-138">For more information about how to use selection conditions, see [Defining Conditions for Diplaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="0e85b-139">Дополнительные сведения о других компонентах широкое представление, см. в разделе [широкое представление](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="0e85b-139">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0e85b-140">См. также</span><span class="sxs-lookup"><span data-stu-id="0e85b-140">See Also</span></span>

[<span data-ttu-id="0e85b-141">Определение условия при отображении данных</span><span class="sxs-lookup"><span data-stu-id="0e85b-141">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="0e85b-142">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e85b-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
