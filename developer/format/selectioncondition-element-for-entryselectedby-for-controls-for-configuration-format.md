---
title: Элемент SelectionCondition для EntrySelectedBy для элементов управления для конфигурации (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f23ef405-0f1e-4607-b3f4-4017b7ead106
caps.latest.revision: 7
ms.openlocfilehash: a5098da55d0a63272a121b973cb05e26dc47e3e1
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854150"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format"></a><span data-ttu-id="d0286-102">Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="d0286-102">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

<span data-ttu-id="d0286-103">Определяет условие, которое должен существовать для общего определения элемента управления для использования.</span><span class="sxs-lookup"><span data-stu-id="d0286-103">Defines a condition that must exist for a common control definition to be used.</span></span> <span data-ttu-id="d0286-104">Этот элемент используется при определении общего элемента управления, который может использоваться все представления в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="d0286-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="d0286-105">Конфигурации (формат) элементы управления элемента конфигурации (формат) элемента управления для элементов управления для элемента конфигурации (формат) пользовательский элемент управления для элемента управления для элемента конфигурации (формат) CustomEntries пользовательский элемент управления для элементов управления для Элемент конфигурации (формат) CustomEntry для пользовательский элемент управления для элементов управления для элемента конфигурации (формат) EntrySelectedBy для CustomEntry для элементов управления для элемента конфигурации (формат) SelectionCondition для EntrySelectedBy для CustomEntry для Конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="d0286-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d0286-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d0286-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d0286-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d0286-107">Attributes and Elements</span></span>

<span data-ttu-id="d0286-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `SelectionCondition` элемент.</span><span class="sxs-lookup"><span data-stu-id="d0286-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d0286-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d0286-109">Attributes</span></span>

<span data-ttu-id="d0286-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="d0286-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d0286-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d0286-111">Child Elements</span></span>

|<span data-ttu-id="d0286-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="d0286-112">Element</span></span>|<span data-ttu-id="d0286-113">Описание</span><span class="sxs-lookup"><span data-stu-id="d0286-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d0286-114">Элемент PropertyName для SelectionCondition для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="d0286-114">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="d0286-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d0286-115">Optional element.</span></span><br /><br /> <span data-ttu-id="d0286-116">Задает свойство .NET, которое активирует условие.</span><span class="sxs-lookup"><span data-stu-id="d0286-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="d0286-117">Элемент ScriptBlock для SelectionCondition для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="d0286-117">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="d0286-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d0286-118">Optional element.</span></span><br /><br /> <span data-ttu-id="d0286-119">Указывает сценарий, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="d0286-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="d0286-120">Элемент SelectionSetName для SelectionCondition для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="d0286-120">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="d0286-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d0286-121">Optional element.</span></span><br /><br /> <span data-ttu-id="d0286-122">Указывает набор типов .NET, которые инициируют условие.</span><span class="sxs-lookup"><span data-stu-id="d0286-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="d0286-123">TypeName-элемент для SelectionCondition для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="d0286-123">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="d0286-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d0286-124">Optional element.</span></span><br /><br /> <span data-ttu-id="d0286-125">Указывает тип .NET, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="d0286-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d0286-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d0286-126">Parent Elements</span></span>

|<span data-ttu-id="d0286-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="d0286-127">Element</span></span>|<span data-ttu-id="d0286-128">Описание</span><span class="sxs-lookup"><span data-stu-id="d0286-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d0286-129">Элемент EntrySelectedBy для CustomEntry для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="d0286-129">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="d0286-130">Определяет типы .NET, использующих эта запись общее определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d0286-130">Defines the .NET types that use this entry of the common control definition.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d0286-131">Замечания</span><span class="sxs-lookup"><span data-stu-id="d0286-131">Remarks</span></span>

<span data-ttu-id="d0286-132">При определении условию выбора, должен следовать приведенным ниже рекомендациям:</span><span class="sxs-lookup"><span data-stu-id="d0286-132">The following guidelines must be followed when defining a selection condition:</span></span>

- <span data-ttu-id="d0286-133">Условию выбора, необходимо указать имя как минимум одно свойство или блок скрипта, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="d0286-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="d0286-134">Условию выбора можно указать любое число типов .NET или выбора задает, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="d0286-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="d0286-135">Дополнительные сведения об использовании условий выборки см. в разделе [определение условий при отображении данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="d0286-135">For more information about how selection conditions can be used, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d0286-136">См. также</span><span class="sxs-lookup"><span data-stu-id="d0286-136">See Also</span></span>

[<span data-ttu-id="d0286-137">Элемент PropertyName для SelectionCondition для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="d0286-137">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="d0286-138">Элемент ScriptBlock для SelectionCondition для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="d0286-138">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="d0286-139">Элемент SelectionSetName для SelectionCondition для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="d0286-139">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="d0286-140">TypeName-элемент для SelectionCondition для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="d0286-140">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="d0286-141">Элемент EntrySelectedBy для CustomEntry для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="d0286-141">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="d0286-142">Написание форматирования Windows PowerShell и типы файлов</span><span class="sxs-lookup"><span data-stu-id="d0286-142">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
