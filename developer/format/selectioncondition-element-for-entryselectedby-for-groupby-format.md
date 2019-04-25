---
title: Элемент SelectionCondition для EntrySelectedBy для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6dc2093a-dc54-42c4-ada3-c8d089ba1e8e
caps.latest.revision: 6
ms.openlocfilehash: a6738a7c4c934b2d6a16695a711f7c6c80afdd2d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62075721"
---
# <a name="selectioncondition-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="861ff-102">Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="861ff-102">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="861ff-103">Определяет условие, которое должен существовать для определения элемента управления для использования.</span><span class="sxs-lookup"><span data-stu-id="861ff-103">Defines a condition that must exist for a control definition to be used.</span></span> <span data-ttu-id="861ff-104">Этот элемент используется при определении того, как отображается группу объектов.</span><span class="sxs-lookup"><span data-stu-id="861ff-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="861ff-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) пользовательский элемент управления для элемента CustomEntries GroupBy (формат) пользовательский элемент управления для элемента CustomEntry GroupBy (формат) Пользовательский элемент управления для элемента EntrySelectedBy GroupBy (формат) для CustomEntry элемента SelectionCondition GroupBy (формат) для EntrySelectedBy для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="861ff-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="861ff-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="861ff-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="861ff-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="861ff-107">Attributes and Elements</span></span>

<span data-ttu-id="861ff-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `SelectionCondition` элемент.</span><span class="sxs-lookup"><span data-stu-id="861ff-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="861ff-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="861ff-109">Attributes</span></span>

<span data-ttu-id="861ff-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="861ff-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="861ff-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="861ff-111">Child Elements</span></span>

|<span data-ttu-id="861ff-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="861ff-112">Element</span></span>|<span data-ttu-id="861ff-113">Описание</span><span class="sxs-lookup"><span data-stu-id="861ff-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="861ff-114">Элемент PropertyName для SelectionCondition для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="861ff-114">PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="861ff-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="861ff-115">Optional element.</span></span><br /><br /> <span data-ttu-id="861ff-116">Задает свойство .NET, которое активирует условие.</span><span class="sxs-lookup"><span data-stu-id="861ff-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="861ff-117">Элемент ScriptBlock для SelectionCondition для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="861ff-117">ScriptBlock Element for SelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="861ff-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="861ff-118">Optional element.</span></span><br /><br /> <span data-ttu-id="861ff-119">Указывает сценарий, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="861ff-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="861ff-120">Элемент SelectionSetName для SelectionCondition для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="861ff-120">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="861ff-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="861ff-121">Optional element.</span></span><br /><br /> <span data-ttu-id="861ff-122">Указывает набор типов .NET, которые инициируют условие.</span><span class="sxs-lookup"><span data-stu-id="861ff-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="861ff-123">TypeName-элемент для SelectionCondition для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="861ff-123">TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="861ff-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="861ff-124">Optional element.</span></span><br /><br /> <span data-ttu-id="861ff-125">Указывает тип .NET, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="861ff-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="861ff-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="861ff-126">Parent Elements</span></span>

|<span data-ttu-id="861ff-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="861ff-127">Element</span></span>|<span data-ttu-id="861ff-128">Описание</span><span class="sxs-lookup"><span data-stu-id="861ff-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="861ff-129">Элемент EntrySelectedBy для CustomEntry для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="861ff-129">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="861ff-130">Определяет типы .NET, которые используют это определение элемента управления или условие, которое должен существовать для данного определения для использования.</span><span class="sxs-lookup"><span data-stu-id="861ff-130">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="861ff-131">Замечания</span><span class="sxs-lookup"><span data-stu-id="861ff-131">Remarks</span></span>

<span data-ttu-id="861ff-132">При определении условию выбора, применяются следующие требования:</span><span class="sxs-lookup"><span data-stu-id="861ff-132">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="861ff-133">Условию выбора, необходимо указать имя как минимум одно свойство или блок скрипта, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="861ff-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="861ff-134">Условию выбора можно указать любое число типов .NET или выбора задает, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="861ff-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="861ff-135">Дополнительные сведения об использовании условий выборки см. в разделе [определение условий при отображении данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="861ff-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="861ff-136">См. также</span><span class="sxs-lookup"><span data-stu-id="861ff-136">See Also</span></span>

[<span data-ttu-id="861ff-137">Элемент PropertyName для SelectionCondition для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="861ff-137">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="861ff-138">Элемент ScriptBlock для SelectionCondition для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="861ff-138">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="861ff-139">Элемент SelectionSetName для SelectionCondition для пользовательского элемента управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="861ff-139">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="861ff-140">TypeName-элемент для SelectionCondition для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="861ff-140">TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)

[<span data-ttu-id="861ff-141">Элемент EntrySelectedBy для CustomEntry для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="861ff-141">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="861ff-142">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="861ff-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
