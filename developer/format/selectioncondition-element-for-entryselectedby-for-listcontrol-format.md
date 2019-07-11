---
title: Элемент SelectionCondition для EntrySelectedBy для ListControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7649d5d0-2b56-49b5-a670-dde46caca343
caps.latest.revision: 11
ms.openlocfilehash: f04a07c241268566eaedfe2b299c33d5be4dc19d
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67735084"
---
# <a name="selectioncondition-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="4c37b-102">Элемент SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="4c37b-102">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="4c37b-103">Определяет условие, которое должна существовать, чтобы использовать это определение представления "list".</span><span class="sxs-lookup"><span data-stu-id="4c37b-103">Defines the condition that must exist to use this definition of the list view.</span></span> <span data-ttu-id="4c37b-104">Нет ограничений на число условий выборки, которые могут быть указаны для определения списка.</span><span class="sxs-lookup"><span data-stu-id="4c37b-104">There is no limit to the number of selection conditions that can be specified for a list definition.</span></span>

<span data-ttu-id="4c37b-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемент (формат) элемента ListControl (формат) элемент ListEntries (формат) элемент ListEntry (формат) EntrySelectedBy элемент конфигурации для элемента SelectionCondition ListEntry (формат) для EntrySelectedBy для ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="4c37b-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4c37b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4c37b-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4c37b-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4c37b-107">Attributes and Elements</span></span>

<span data-ttu-id="4c37b-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `SelectionCondition` элемент.</span><span class="sxs-lookup"><span data-stu-id="4c37b-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4c37b-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4c37b-109">Attributes</span></span>

<span data-ttu-id="4c37b-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="4c37b-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4c37b-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4c37b-111">Child Elements</span></span>

|<span data-ttu-id="4c37b-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="4c37b-112">Element</span></span>|<span data-ttu-id="4c37b-113">Описание</span><span class="sxs-lookup"><span data-stu-id="4c37b-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4c37b-114">Элемент PropertyName для SelectionCondition для EntrySelectedBy для ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="4c37b-114">PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="4c37b-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4c37b-115">Optional element.</span></span><br /><br /> <span data-ttu-id="4c37b-116">Задает свойство .NET, которое активирует условие.</span><span class="sxs-lookup"><span data-stu-id="4c37b-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="4c37b-117">Элемент ScriptBlock для SelectionCondition для EntrySelectedBy для ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="4c37b-117">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="4c37b-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4c37b-118">Optional element.</span></span><br /><br /> <span data-ttu-id="4c37b-119">Указывает сценарий, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="4c37b-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="4c37b-120">Элемент SelectionSetName для SelectionCondition для EntrySelectedBy для ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="4c37b-120">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)|<span data-ttu-id="4c37b-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4c37b-121">Optional element.</span></span><br /><br /> <span data-ttu-id="4c37b-122">Указывает набор типов .NET, которые активируют условие.</span><span class="sxs-lookup"><span data-stu-id="4c37b-122">Specifies the set of .NET types that trigger the condition.</span></span>|
|[<span data-ttu-id="4c37b-123">TypeName-элемент для SelectionCondition для EntrySelectedBy для ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="4c37b-123">TypeName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="4c37b-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4c37b-124">Optional element.</span></span><br /><br /> <span data-ttu-id="4c37b-125">Указывает тип .NET, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="4c37b-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4c37b-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4c37b-126">Parent Elements</span></span>

|<span data-ttu-id="4c37b-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="4c37b-127">Element</span></span>|<span data-ttu-id="4c37b-128">Описание</span><span class="sxs-lookup"><span data-stu-id="4c37b-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4c37b-129">Элемент EntrySelectedBy для TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="4c37b-129">EntrySelectedBy Element for TableRowEntry (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="4c37b-130">Определяет типы .NET, использующих этой записи таблицы или условие, которое должен существовать для данной записи для использования.</span><span class="sxs-lookup"><span data-stu-id="4c37b-130">Defines the .NET types that use this table entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4c37b-131">Замечания</span><span class="sxs-lookup"><span data-stu-id="4c37b-131">Remarks</span></span>

<span data-ttu-id="4c37b-132">lWhen при определении условию выбора, применяются следующие требования:</span><span class="sxs-lookup"><span data-stu-id="4c37b-132">lWhen you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="4c37b-133">Условию выбора, необходимо указать имя как минимум одно свойство или блок скрипта, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="4c37b-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="4c37b-134">Условию выбора можно указать любое число типов .NET или выбора задает, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="4c37b-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="4c37b-135">Дополнительные сведения об использовании условий выборки см. в разделе [определение условий при отображении данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="4c37b-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="4c37b-136">Дополнительные сведения о других компонентах представления списка, см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="4c37b-136">For more information about other components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4c37b-137">См. также</span><span class="sxs-lookup"><span data-stu-id="4c37b-137">See Also</span></span>

[<span data-ttu-id="4c37b-138">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="4c37b-138">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="4c37b-139">Определение условия при отображении данных</span><span class="sxs-lookup"><span data-stu-id="4c37b-139">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="4c37b-140">Элемент ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="4c37b-140">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="4c37b-141">Элемент SelectionSetName для EntrySelectedBy для ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="4c37b-141">SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="4c37b-142">TypeName-элемент для EntrySelectedBy для ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="4c37b-142">TypeName Element for EntrySelectedBy for ListEntry (Format)</span></span>](/powershell/developer/format/typename-element-for-entryselectedby-for-listcontrol-format)

[<span data-ttu-id="4c37b-143">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c37b-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
