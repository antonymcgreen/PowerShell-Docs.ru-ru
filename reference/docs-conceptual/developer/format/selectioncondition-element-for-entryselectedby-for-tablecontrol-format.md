---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)
description: Элемент SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)
ms.openlocfilehash: 22f304615c6433ffb67f3b4046b645d0c37be8a4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645770"
---
# <a name="selectioncondition-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="89d39-103">Элемент SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="89d39-103">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="89d39-104">Определяет условие, которое должно существовать для использования в этом определении табличного представления.</span><span class="sxs-lookup"><span data-stu-id="89d39-104">Defines the condition that must exist to use for this definition of the table view.</span></span> <span data-ttu-id="89d39-105">Количество условий выбора, которое можно указать для определения таблицы, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="89d39-105">There is no limit to the number of selection conditions that can be specified for a table definition.</span></span>

<span data-ttu-id="89d39-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Ентриселектедби для таблеровентри (Format) SelectionCondition для EntrySelectedBy в TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="89d39-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="89d39-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89d39-107">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="89d39-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="89d39-108">Attributes and Elements</span></span>

<span data-ttu-id="89d39-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента Селектионкондитион.</span><span class="sxs-lookup"><span data-stu-id="89d39-109">The following sections describe attributes, child elements, and the parent element of the SelectionCondition element.</span></span>

### <a name="attributes"></a><span data-ttu-id="89d39-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="89d39-110">Attributes</span></span>

<span data-ttu-id="89d39-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="89d39-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="89d39-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="89d39-112">Child Elements</span></span>

|<span data-ttu-id="89d39-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="89d39-113">Element</span></span>|<span data-ttu-id="89d39-114">Описание</span><span class="sxs-lookup"><span data-stu-id="89d39-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="89d39-115">Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="89d39-115">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)|<span data-ttu-id="89d39-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="89d39-116">Optional element.</span></span><br /><br /> <span data-ttu-id="89d39-117">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="89d39-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="89d39-118">Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="89d39-118">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="89d39-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="89d39-119">Optional element.</span></span><br /><br /> <span data-ttu-id="89d39-120">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="89d39-120">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="89d39-121">Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="89d39-121">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="89d39-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="89d39-122">Optional element.</span></span><br /><br /> <span data-ttu-id="89d39-123">Указывает набор типов .NET, которые активируют условие.</span><span class="sxs-lookup"><span data-stu-id="89d39-123">Specifies the set of .NET types that trigger the condition.</span></span>|
|[<span data-ttu-id="89d39-124">Элемент TypeName для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="89d39-124">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="89d39-125">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="89d39-125">Optional element.</span></span><br /><br /> <span data-ttu-id="89d39-126">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="89d39-126">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="89d39-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="89d39-127">Parent Elements</span></span>

|<span data-ttu-id="89d39-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="89d39-128">Element</span></span>|<span data-ttu-id="89d39-129">Описание</span><span class="sxs-lookup"><span data-stu-id="89d39-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="89d39-130">Элемент Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="89d39-130">EntrySelectedBy Element for TableRowEntry (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="89d39-131">Определяет типы .NET, которые используют эту запись таблицы, или условие, которое должно существовать для использования этой записи.</span><span class="sxs-lookup"><span data-stu-id="89d39-131">Defines the .NET types that use this table entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="89d39-132">Комментарии</span><span class="sxs-lookup"><span data-stu-id="89d39-132">Remarks</span></span>

<span data-ttu-id="89d39-133">Каждая запись списка должна иметь по крайней мере одно определенное имя типа, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="89d39-133">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="89d39-134">При определении условия выбора применяются следующие требования.</span><span class="sxs-lookup"><span data-stu-id="89d39-134">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="89d39-135">Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.</span><span class="sxs-lookup"><span data-stu-id="89d39-135">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="89d39-136">Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.</span><span class="sxs-lookup"><span data-stu-id="89d39-136">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="89d39-137">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="89d39-137">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="89d39-138">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="89d39-138">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="89d39-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="89d39-139">See Also</span></span>

[<span data-ttu-id="89d39-140">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="89d39-140">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="89d39-141">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="89d39-141">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="89d39-142">Элемент Ентриселектедби (Format)</span><span class="sxs-lookup"><span data-stu-id="89d39-142">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="89d39-143">Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="89d39-143">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[<span data-ttu-id="89d39-144">Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="89d39-144">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="89d39-145">Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="89d39-145">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="89d39-146">Элемент TypeName для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="89d39-146">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="89d39-147">Создание файла форматирования и типов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="89d39-147">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
