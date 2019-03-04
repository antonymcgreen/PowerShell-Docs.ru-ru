---
title: Элемент SelectionCondition для EntrySelectedBy для пользовательский элемент управления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 231e9c6d-09ec-4e68-80ee-0c8f7fe1b9f5
caps.latest.revision: 7
ms.openlocfilehash: 49e2c0cf09dfa55b535effcd431e980daf12fac3
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858830"
---
# <a name="selectioncondition-element-for-entryselectedby-for-customcontrol-format"></a><span data-ttu-id="3fee7-102">Элемент SelectionCondition для элемента EntrySelectedBy для элемента CustomControl (формат)</span><span class="sxs-lookup"><span data-stu-id="3fee7-102">SelectionCondition Element for EntrySelectedBy for CustomControl (Format)</span></span>

<span data-ttu-id="3fee7-103">Определяет условие, которое должен существовать для определения элемента управления для использования.</span><span class="sxs-lookup"><span data-stu-id="3fee7-103">Defines a condition that must exist for a control definition to be used.</span></span> <span data-ttu-id="3fee7-104">Этот элемент используется при определении представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="3fee7-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="3fee7-105">Конфигурации элемента (формат) элемент ViewDefinitions (формат) элемент (формат) пользовательский элемент управления элемента представления для элемента представления (формат) CustomEntries для пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для пользовательский элемент управления (представление Элемент CustomItem Format) для CustomEntry для пользовательский элемент управления для элемента представления (формат) EntrySelectedBy для CustomEntry для пользовательский элемент управления для элемента представления (формат) SelectionCondition для EntrySelectedBy для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="3fee7-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) EntrySelectedBy Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3fee7-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3fee7-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3fee7-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3fee7-107">Attributes and Elements</span></span>

<span data-ttu-id="3fee7-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `SelectionCondition` элемент.</span><span class="sxs-lookup"><span data-stu-id="3fee7-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3fee7-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3fee7-109">Attributes</span></span>

<span data-ttu-id="3fee7-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="3fee7-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3fee7-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3fee7-111">Child Elements</span></span>

|<span data-ttu-id="3fee7-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="3fee7-112">Element</span></span>|<span data-ttu-id="3fee7-113">Описание</span><span class="sxs-lookup"><span data-stu-id="3fee7-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3fee7-114">Элемент PropertyName для SelectionCondition для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="3fee7-114">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="3fee7-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3fee7-115">Optional element.</span></span><br /><br /> <span data-ttu-id="3fee7-116">Задает свойство .NET, которое активирует условие.</span><span class="sxs-lookup"><span data-stu-id="3fee7-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="3fee7-117">Элемент ScriptBlock для SelectionCondition для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="3fee7-117">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="3fee7-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3fee7-118">Optional element.</span></span><br /><br /> <span data-ttu-id="3fee7-119">Указывает сценарий, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="3fee7-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="3fee7-120">Элемент SelectionSetName для SelectionCondition для пользовательского элемента управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="3fee7-120">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="3fee7-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3fee7-121">Optional element.</span></span><br /><br /> <span data-ttu-id="3fee7-122">Указывает набор типов .NET, которые инициируют условие.</span><span class="sxs-lookup"><span data-stu-id="3fee7-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="3fee7-123">TypeName-элемент для SelectionCondition для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="3fee7-123">TypeName Element for SelectionCondition for CustomControl for View  (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="3fee7-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3fee7-124">Optional element.</span></span><br /><br /> <span data-ttu-id="3fee7-125">Указывает тип .NET, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="3fee7-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="3fee7-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3fee7-126">Parent Elements</span></span>

|<span data-ttu-id="3fee7-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="3fee7-127">Element</span></span>|<span data-ttu-id="3fee7-128">Описание</span><span class="sxs-lookup"><span data-stu-id="3fee7-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3fee7-129">Элемент EntrySelectedBy для CustomEntry для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="3fee7-129">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="3fee7-130">Определяет типы .NET, которые используют это определение элемента управления или условие, которое должен существовать для данного определения для использования.</span><span class="sxs-lookup"><span data-stu-id="3fee7-130">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3fee7-131">Замечания</span><span class="sxs-lookup"><span data-stu-id="3fee7-131">Remarks</span></span>

<span data-ttu-id="3fee7-132">При определении условию выбора, применяются следующие требования:</span><span class="sxs-lookup"><span data-stu-id="3fee7-132">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="3fee7-133">Условию выбора, необходимо указать имя как минимум одно свойство или блок скрипта, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="3fee7-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="3fee7-134">Условию выбора можно указать любое число типов .NET или выбора задает, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="3fee7-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="3fee7-135">Дополнительные сведения об использовании условий выборки см. в разделе [определение условий при отображении данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="3fee7-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3fee7-136">См. также</span><span class="sxs-lookup"><span data-stu-id="3fee7-136">See Also</span></span>

[<span data-ttu-id="3fee7-137">Элемент PropertyName для SelectionCondition для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="3fee7-137">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="3fee7-138">Элемент ScriptBlock для SelectionCondition для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="3fee7-138">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="3fee7-139">Элемент SelectionSetName для SelectionCondition для пользовательского элемента управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="3fee7-139">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="3fee7-140">TypeName-элемент для SelectionCondition для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="3fee7-140">TypeName Element for SelectionCondition for CustomControl for View  (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="3fee7-141">Элемент EntrySelectedBy для CustomEntry для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="3fee7-141">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="3fee7-142">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="3fee7-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
