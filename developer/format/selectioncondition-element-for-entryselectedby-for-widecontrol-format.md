---
title: Элемент SelectionCondition для EntrySelectedBy для WideControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7a9f086-b1ca-4400-9be7-9ec1ec8880f3
caps.latest.revision: 11
ms.openlocfilehash: f20679e3392b99a049c075f24c7712262bab08e1
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064004"
---
# <a name="selectioncondition-element-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="49c5e-102">Элемент SelectionCondition для элемента EntrySelectedBy для элемента WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="49c5e-102">SelectionCondition Element for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="49c5e-103">Определяет условие, которое должен существовать для данного определения для использования.</span><span class="sxs-lookup"><span data-stu-id="49c5e-103">Defines the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="49c5e-104">Нет ограничений на число условий выборки, которые могут быть указаны для определения расширенных запись.</span><span class="sxs-lookup"><span data-stu-id="49c5e-104">There is no limit to the number of selection conditions that can be specified for a wide entry definition.</span></span>

<span data-ttu-id="49c5e-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент WideControl (формат) элемент WideEntries (формат) элемент WideEntry (формат) EntrySelectedBy элемент конфигурации для элемент SelectionCondition WideEntry (формат) для EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="49c5e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="49c5e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49c5e-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="49c5e-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="49c5e-107">Attributes and Elements</span></span>

<span data-ttu-id="49c5e-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `SelectionCondition` элемент.</span><span class="sxs-lookup"><span data-stu-id="49c5e-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span> <span data-ttu-id="49c5e-109">Необходимо указать один `PropertyName` или `ScriptBlock` элемент.</span><span class="sxs-lookup"><span data-stu-id="49c5e-109">You must specify a single `PropertyName` or `ScriptBlock` element.</span></span> <span data-ttu-id="49c5e-110">`SelectionSetName` И `TypeName` элементы являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="49c5e-110">The `SelectionSetName` and `TypeName` elements are optional.</span></span> <span data-ttu-id="49c5e-111">Можно указать один из любой из элементов.</span><span class="sxs-lookup"><span data-stu-id="49c5e-111">You can specify one of either element.</span></span>

### <a name="attributes"></a><span data-ttu-id="49c5e-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="49c5e-112">Attributes</span></span>

<span data-ttu-id="49c5e-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="49c5e-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="49c5e-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="49c5e-114">Child Elements</span></span>

|<span data-ttu-id="49c5e-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="49c5e-115">Element</span></span>|<span data-ttu-id="49c5e-116">Описание</span><span class="sxs-lookup"><span data-stu-id="49c5e-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="49c5e-117">Элемент PropertyName для SelectionCondition для EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="49c5e-117">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="49c5e-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="49c5e-118">Optional element.</span></span><br /><br /> <span data-ttu-id="49c5e-119">Задает свойство .NET, которое активирует условие.</span><span class="sxs-lookup"><span data-stu-id="49c5e-119">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="49c5e-120">Элемент ScriptBlock для SelectionCondition для EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="49c5e-120">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="49c5e-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="49c5e-121">Optional element.</span></span><br /><br /> <span data-ttu-id="49c5e-122">Указывает блок скрипта, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="49c5e-122">Specifies the script block that triggers the condition.</span></span>|
|[<span data-ttu-id="49c5e-123">Элемент SelectionSetName для SelectionCondition для EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="49c5e-123">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="49c5e-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="49c5e-124">Optional element.</span></span><br /><br /> <span data-ttu-id="49c5e-125">Указывает набор типов .NET, которые инициируют условие.</span><span class="sxs-lookup"><span data-stu-id="49c5e-125">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="49c5e-126">TypeName-элемент для SelectionCondition для EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="49c5e-126">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="49c5e-127">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="49c5e-127">Optional element.</span></span><br /><br /> <span data-ttu-id="49c5e-128">Указывает тип .NET, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="49c5e-128">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="49c5e-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="49c5e-129">Parent Elements</span></span>

|<span data-ttu-id="49c5e-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="49c5e-130">Element</span></span>|<span data-ttu-id="49c5e-131">Описание</span><span class="sxs-lookup"><span data-stu-id="49c5e-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="49c5e-132">Элемент EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="49c5e-132">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="49c5e-133">Определяет типы .NET, использующих эту запись широкий или условие, которое должен существовать для данной записи для использования.</span><span class="sxs-lookup"><span data-stu-id="49c5e-133">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="49c5e-134">Замечания</span><span class="sxs-lookup"><span data-stu-id="49c5e-134">Remarks</span></span>

<span data-ttu-id="49c5e-135">Каждый расширенный запись должна иметь по крайней мере одно имя типа, набора или Выбор условия, определенного.</span><span class="sxs-lookup"><span data-stu-id="49c5e-135">Each wide entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="49c5e-136">При определении условию выбора, применяются следующие требования:</span><span class="sxs-lookup"><span data-stu-id="49c5e-136">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="49c5e-137">Условию выбора, необходимо указать имя как минимум одно свойство или блок скрипта, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="49c5e-137">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="49c5e-138">Условию выбора можно указать любое число типов .NET или выбора задает, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="49c5e-138">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="49c5e-139">Дополнительные сведения об использовании условий выборки см. в разделе [определение условий для, когда операция отчета или элемента используется](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="49c5e-139">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="49c5e-140">Дополнительные сведения о других компонентах широкое представление, см. в разделе [Создание широкое представление](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="49c5e-140">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="49c5e-141">См. также</span><span class="sxs-lookup"><span data-stu-id="49c5e-141">See Also</span></span>

[<span data-ttu-id="49c5e-142">Создание широкое представление</span><span class="sxs-lookup"><span data-stu-id="49c5e-142">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="49c5e-143">Определение условия при отображении данных</span><span class="sxs-lookup"><span data-stu-id="49c5e-143">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="49c5e-144">Элемент EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="49c5e-144">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="49c5e-145">Элемент PropertyName для SelectionCondition для EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="49c5e-145">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="49c5e-146">Элемент ScriptBlock для SelectionCondition для EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="49c5e-146">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="49c5e-147">Элемент SelectionSetName для SelectionCondition для EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="49c5e-147">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="49c5e-148">TypeName-элемент для SelectionCondition для EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="49c5e-148">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="49c5e-149">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="49c5e-149">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
