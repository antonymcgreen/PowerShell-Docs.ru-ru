---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)
description: Элемент SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)
ms.openlocfilehash: e93499691dd0046265e43abd26497b2974546083
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655103"
---
# <a name="selectioncondition-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="f8644-103">Элемент SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="f8644-103">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="f8644-104">Определяет условие, которое должно существовать для использования этого определения представления списка.</span><span class="sxs-lookup"><span data-stu-id="f8644-104">Defines the condition that must exist to use this definition of the list view.</span></span> <span data-ttu-id="f8644-105">Количество условий выбора, которое можно указать для определения списка, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="f8644-105">There is no limit to the number of selection conditions that can be specified for a list definition.</span></span>

<span data-ttu-id="f8644-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент (Format) Ентриселектедби для листентри (Format) Селектионкондитион для EntrySelectedBy в ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="f8644-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f8644-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f8644-107">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f8644-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f8644-108">Attributes and Elements</span></span>

<span data-ttu-id="f8644-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionCondition` элемента.</span><span class="sxs-lookup"><span data-stu-id="f8644-109">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f8644-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f8644-110">Attributes</span></span>

<span data-ttu-id="f8644-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f8644-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f8644-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f8644-112">Child Elements</span></span>

|<span data-ttu-id="f8644-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="f8644-113">Element</span></span>|<span data-ttu-id="f8644-114">Описание</span><span class="sxs-lookup"><span data-stu-id="f8644-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f8644-115">Элемент PropertyName для Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="f8644-115">PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="f8644-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f8644-116">Optional element.</span></span><br /><br /> <span data-ttu-id="f8644-117">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="f8644-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="f8644-118">Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="f8644-118">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="f8644-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f8644-119">Optional element.</span></span><br /><br /> <span data-ttu-id="f8644-120">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="f8644-120">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="f8644-121">Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="f8644-121">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)|<span data-ttu-id="f8644-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f8644-122">Optional element.</span></span><br /><br /> <span data-ttu-id="f8644-123">Указывает набор типов .NET, которые активируют условие.</span><span class="sxs-lookup"><span data-stu-id="f8644-123">Specifies the set of .NET types that trigger the condition.</span></span>|
|[<span data-ttu-id="f8644-124">Элемент TypeName для Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="f8644-124">TypeName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="f8644-125">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f8644-125">Optional element.</span></span><br /><br /> <span data-ttu-id="f8644-126">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="f8644-126">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f8644-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f8644-127">Parent Elements</span></span>

|<span data-ttu-id="f8644-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="f8644-128">Element</span></span>|<span data-ttu-id="f8644-129">Описание</span><span class="sxs-lookup"><span data-stu-id="f8644-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f8644-130">Элемент Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="f8644-130">EntrySelectedBy Element for TableRowEntry (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="f8644-131">Определяет типы .NET, которые используют эту запись таблицы, или условие, которое должно существовать для использования этой записи.</span><span class="sxs-lookup"><span data-stu-id="f8644-131">Defines the .NET types that use this table entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f8644-132">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f8644-132">Remarks</span></span>

<span data-ttu-id="f8644-133">Лвхен вы определяете условие выбора, применяются следующие требования.</span><span class="sxs-lookup"><span data-stu-id="f8644-133">lWhen you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="f8644-134">Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.</span><span class="sxs-lookup"><span data-stu-id="f8644-134">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="f8644-135">Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.</span><span class="sxs-lookup"><span data-stu-id="f8644-135">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="f8644-136">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="f8644-136">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="f8644-137">Дополнительные сведения о других компонентах представления списка см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="f8644-137">For more information about other components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f8644-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="f8644-138">See Also</span></span>

[<span data-ttu-id="f8644-139">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="f8644-139">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="f8644-140">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="f8644-140">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="f8644-141">Элемент Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="f8644-141">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="f8644-142">Элемент Селектионсетнаме для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="f8644-142">SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="f8644-143">Элемент TypeName для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="f8644-143">TypeName Element for EntrySelectedBy for ListEntry (Format)</span></span>](/powershell/scripting/developer/format/typename-element-for-entryselectedby-for-listcontrol-format)

[<span data-ttu-id="f8644-144">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8644-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
