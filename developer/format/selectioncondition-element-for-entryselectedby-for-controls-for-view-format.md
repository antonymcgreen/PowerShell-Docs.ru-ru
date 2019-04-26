---
title: Элемент SelectionCondition для EntrySelectedBy для элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2623407e-fa10-4d27-a804-204f6d50ef22
caps.latest.revision: 6
ms.openlocfilehash: ea15e647a9dd7a7064718a0c536c4a3178d62d95
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064241"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-view-format"></a><span data-ttu-id="6ee8b-102">Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="6ee8b-102">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>

<span data-ttu-id="6ee8b-103">Определяет условие, которое должен существовать для определение элемента управления для использования.</span><span class="sxs-lookup"><span data-stu-id="6ee8b-103">Defines a condition that must exist for the control definition to be used.</span></span> <span data-ttu-id="6ee8b-104">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="6ee8b-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="6ee8b-105">Конфигурации элемента (формат) элемент ViewDefinitions (формат) представление элемента (формат) элементы управления элемента (формат) элемент управления для элементов управления для элемента представления (формат) пользовательский элемент управления для элемента управления для элементов управления для элемента CustomEntries представления (формат) для Пользовательский элемент управления для элементов управления для элемента представления (формат) CustomEntry для CustomEntries для элементов управления для элемента представления (формат) EntrySelectedBy для CustomEntry для элементов управления для элемента представления (формат) SelectionCondition для EntrySelectedBy для элементов управления (представление Формат)</span><span class="sxs-lookup"><span data-stu-id="6ee8b-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6ee8b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6ee8b-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6ee8b-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6ee8b-107">Attributes and Elements</span></span>

<span data-ttu-id="6ee8b-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `SelectionCondition` элемент.</span><span class="sxs-lookup"><span data-stu-id="6ee8b-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6ee8b-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6ee8b-109">Attributes</span></span>

<span data-ttu-id="6ee8b-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="6ee8b-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6ee8b-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6ee8b-111">Child Elements</span></span>

|<span data-ttu-id="6ee8b-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="6ee8b-112">Element</span></span>|<span data-ttu-id="6ee8b-113">Описание</span><span class="sxs-lookup"><span data-stu-id="6ee8b-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6ee8b-114">Элемент PropertyName для SelectionCondition для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="6ee8b-114">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="6ee8b-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="6ee8b-115">Optional element.</span></span><br /><br /> <span data-ttu-id="6ee8b-116">Задает свойство .NET, которое активирует условие.</span><span class="sxs-lookup"><span data-stu-id="6ee8b-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="6ee8b-117">Элемент ScriptBlock для SelectionCondition для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="6ee8b-117">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="6ee8b-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="6ee8b-118">Optional element.</span></span><br /><br /> <span data-ttu-id="6ee8b-119">Указывает сценарий, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="6ee8b-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="6ee8b-120">Элемент SelectionSetName для SelectionCondition для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="6ee8b-120">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="6ee8b-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="6ee8b-121">Optional element.</span></span><br /><br /> <span data-ttu-id="6ee8b-122">Указывает набор типов .NET, которые инициируют условие.</span><span class="sxs-lookup"><span data-stu-id="6ee8b-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="6ee8b-123">TypeName-элемент для SelectionCondition для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="6ee8b-123">TypeName Element for SelectionCondition for Controls for View (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="6ee8b-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="6ee8b-124">Optional element.</span></span><br /><br /> <span data-ttu-id="6ee8b-125">Указывает тип .NET, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="6ee8b-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="6ee8b-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6ee8b-126">Parent Elements</span></span>

|<span data-ttu-id="6ee8b-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="6ee8b-127">Element</span></span>|<span data-ttu-id="6ee8b-128">Описание</span><span class="sxs-lookup"><span data-stu-id="6ee8b-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6ee8b-129">Элемент EntrySelectedBy для CustomEntry для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="6ee8b-129">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="6ee8b-130">Определяет типы .NET, которые используют это определение элемента управления или условие, которое должен существовать для данного определения для использования.</span><span class="sxs-lookup"><span data-stu-id="6ee8b-130">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6ee8b-131">Замечания</span><span class="sxs-lookup"><span data-stu-id="6ee8b-131">Remarks</span></span>

<span data-ttu-id="6ee8b-132">При определении условию выбора, применяются следующие требования:</span><span class="sxs-lookup"><span data-stu-id="6ee8b-132">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="6ee8b-133">Условию выбора, необходимо указать имя как минимум одно свойство или блок скрипта, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="6ee8b-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="6ee8b-134">Условию выбора можно указать любое число типов .NET или выбора задает, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="6ee8b-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="6ee8b-135">Дополнительные сведения об использовании условий выборки см. в разделе [определение условий при отображении данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="6ee8b-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6ee8b-136">См. также</span><span class="sxs-lookup"><span data-stu-id="6ee8b-136">See Also</span></span>

[<span data-ttu-id="6ee8b-137">Элемент PropertyName для SelectionCondition для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="6ee8b-137">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="6ee8b-138">Элемент ScriptBlock для SelectionCondition для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="6ee8b-138">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="6ee8b-139">Элемент SelectionSetName для SelectionCondition для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="6ee8b-139">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="6ee8b-140">TypeName-элемент для SelectionCondition для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="6ee8b-140">TypeName Element for SelectionCondition for Controls for View (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="6ee8b-141">Элемент EntrySelectedBy для CustomEntry для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="6ee8b-141">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="6ee8b-142">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ee8b-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
