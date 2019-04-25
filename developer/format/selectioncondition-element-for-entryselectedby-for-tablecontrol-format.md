---
title: Элемент SelectionCondition для EntrySelectedBy для TableControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 912f3e63-e4d5-41ce-8710-6dfd8c885dc2
caps.latest.revision: 12
ms.openlocfilehash: 2faca6021dc26878869bdd2d35bc4ffc64d0fe7b
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62075670"
---
# <a name="selectioncondition-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="24d21-102">Элемент SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="24d21-102">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="24d21-103">Определяет условие, которое должен существовать для этого определения представления таблицы.</span><span class="sxs-lookup"><span data-stu-id="24d21-103">Defines the condition that must exist to use for this definition of the table view.</span></span> <span data-ttu-id="24d21-104">Нет ограничений на число условий выборки, которые могут быть указаны для определения таблицы.</span><span class="sxs-lookup"><span data-stu-id="24d21-104">There is no limit to the number of selection conditions that can be specified for a table definition.</span></span>

<span data-ttu-id="24d21-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) элемент TableRowEntries (формат) элемент TableRowEntry (формат) EntrySelectedBy элемент конфигурации для TableRowEntry (формат) Элемент SelectionCondition для EntrySelectedBy для TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="24d21-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="24d21-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="24d21-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="24d21-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="24d21-107">Attributes and Elements</span></span>

<span data-ttu-id="24d21-108">Атрибуты, дочерние элементы и родительский элемент элемента SelectionCondition в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="24d21-108">The following sections describe attributes, child elements, and the parent element of the SelectionCondition element.</span></span>

### <a name="attributes"></a><span data-ttu-id="24d21-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="24d21-109">Attributes</span></span>

<span data-ttu-id="24d21-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="24d21-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="24d21-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="24d21-111">Child Elements</span></span>

|<span data-ttu-id="24d21-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="24d21-112">Element</span></span>|<span data-ttu-id="24d21-113">Описание</span><span class="sxs-lookup"><span data-stu-id="24d21-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="24d21-114">Элемент PropertyName для SelectionCondition для EntrySelectedBy для TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="24d21-114">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)|<span data-ttu-id="24d21-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="24d21-115">Optional element.</span></span><br /><br /> <span data-ttu-id="24d21-116">Задает свойство .NET, которое активирует условие.</span><span class="sxs-lookup"><span data-stu-id="24d21-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="24d21-117">Элемент ScriptBlock для SelectionCondition для EntrySelectedBy для TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="24d21-117">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="24d21-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="24d21-118">Optional element.</span></span><br /><br /> <span data-ttu-id="24d21-119">Указывает сценарий, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="24d21-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="24d21-120">Элемент SelectionSetName для SelectionCondition для EntrySelectedBy для TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="24d21-120">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="24d21-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="24d21-121">Optional element.</span></span><br /><br /> <span data-ttu-id="24d21-122">Указывает набор типов .NET, которые активируют условие.</span><span class="sxs-lookup"><span data-stu-id="24d21-122">Specifies the set of .NET types that trigger the condition.</span></span>|
|[<span data-ttu-id="24d21-123">TypeName-элемент для SelectionCondition для EntrySelectedBy для TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="24d21-123">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="24d21-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="24d21-124">Optional element.</span></span><br /><br /> <span data-ttu-id="24d21-125">Указывает тип .NET, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="24d21-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="24d21-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="24d21-126">Parent Elements</span></span>

|<span data-ttu-id="24d21-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="24d21-127">Element</span></span>|<span data-ttu-id="24d21-128">Описание</span><span class="sxs-lookup"><span data-stu-id="24d21-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="24d21-129">Элемент EntrySelectedBy для TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="24d21-129">EntrySelectedBy Element for TableRowEntry (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="24d21-130">Определяет типы .NET, использующих этой записи таблицы или условие, которое должен существовать для данной записи для использования.</span><span class="sxs-lookup"><span data-stu-id="24d21-130">Defines the .NET types that use this table entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="24d21-131">Замечания</span><span class="sxs-lookup"><span data-stu-id="24d21-131">Remarks</span></span>

<span data-ttu-id="24d21-132">Каждый элемент списка должен иметь по крайней мере одно имя типа, набора или Выбор условия, определенного.</span><span class="sxs-lookup"><span data-stu-id="24d21-132">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="24d21-133">При определении условию выбора, применяются следующие требования:</span><span class="sxs-lookup"><span data-stu-id="24d21-133">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="24d21-134">Условию выбора, необходимо указать имя как минимум одно свойство или блок скрипта, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="24d21-134">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="24d21-135">Условию выбора можно указать любое число типов .NET или выбора задает, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="24d21-135">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="24d21-136">Дополнительные сведения об использовании условий выборки см. в разделе [определение условий для, когда операция отчета или элемента используется](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="24d21-136">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="24d21-137">Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="24d21-137">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="24d21-138">См. также</span><span class="sxs-lookup"><span data-stu-id="24d21-138">See Also</span></span>

[<span data-ttu-id="24d21-139">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="24d21-139">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="24d21-140">Определение условия при отображении данных</span><span class="sxs-lookup"><span data-stu-id="24d21-140">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="24d21-141">Элемент EntrySelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="24d21-141">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="24d21-142">Элемент PropertyName для SelectionCondition для EntrySelectedBy для TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="24d21-142">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[<span data-ttu-id="24d21-143">Элемент ScriptBlock для SelectionCondition для EntrySelectedBy для TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="24d21-143">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="24d21-144">Элемент SelectionSetName для SelectionCondition для EntrySelectedBy для TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="24d21-144">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="24d21-145">TypeName-элемент для SelectionCondition для EntrySelectedBy для TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="24d21-145">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="24d21-146">Написание форматирования Windows PowerShell и типы файлов</span><span class="sxs-lookup"><span data-stu-id="24d21-146">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
