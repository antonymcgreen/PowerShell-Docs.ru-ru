---
title: Элемент Селектионкондитион для Ентриселектедби для Таблеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 912f3e63-e4d5-41ce-8710-6dfd8c885dc2
caps.latest.revision: 12
ms.openlocfilehash: 2faca6021dc26878869bdd2d35bc4ffc64d0fe7b
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368393"
---
# <a name="selectioncondition-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="7a178-102">Элемент SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="7a178-102">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="7a178-103">Определяет условие, которое должно существовать для использования в этом определении табличного представления.</span><span class="sxs-lookup"><span data-stu-id="7a178-103">Defines the condition that must exist to use for this definition of the table view.</span></span> <span data-ttu-id="7a178-104">Количество условий выбора, которое можно указать для определения таблицы, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="7a178-104">There is no limit to the number of selection conditions that can be specified for a table definition.</span></span>

<span data-ttu-id="7a178-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Ентриселектедби для Таблеровентри (Format) Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="7a178-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7a178-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7a178-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7a178-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7a178-107">Attributes and Elements</span></span>

<span data-ttu-id="7a178-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента Селектионкондитион.</span><span class="sxs-lookup"><span data-stu-id="7a178-108">The following sections describe attributes, child elements, and the parent element of the SelectionCondition element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7a178-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7a178-109">Attributes</span></span>

<span data-ttu-id="7a178-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="7a178-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7a178-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7a178-111">Child Elements</span></span>

|<span data-ttu-id="7a178-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="7a178-112">Element</span></span>|<span data-ttu-id="7a178-113">Описание</span><span class="sxs-lookup"><span data-stu-id="7a178-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7a178-114">Элемент PropertyName для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="7a178-114">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)|<span data-ttu-id="7a178-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="7a178-115">Optional element.</span></span><br /><br /> <span data-ttu-id="7a178-116">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="7a178-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="7a178-117">Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="7a178-117">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="7a178-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="7a178-118">Optional element.</span></span><br /><br /> <span data-ttu-id="7a178-119">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="7a178-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="7a178-120">Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="7a178-120">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="7a178-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="7a178-121">Optional element.</span></span><br /><br /> <span data-ttu-id="7a178-122">Указывает набор типов .NET, которые активируют условие.</span><span class="sxs-lookup"><span data-stu-id="7a178-122">Specifies the set of .NET types that trigger the condition.</span></span>|
|[<span data-ttu-id="7a178-123">Элемент TypeName для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="7a178-123">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="7a178-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="7a178-124">Optional element.</span></span><br /><br /> <span data-ttu-id="7a178-125">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="7a178-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="7a178-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7a178-126">Parent Elements</span></span>

|<span data-ttu-id="7a178-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="7a178-127">Element</span></span>|<span data-ttu-id="7a178-128">Описание</span><span class="sxs-lookup"><span data-stu-id="7a178-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7a178-129">Элемент Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="7a178-129">EntrySelectedBy Element for TableRowEntry (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="7a178-130">Определяет типы .NET, которые используют эту запись таблицы, или условие, которое должно существовать для использования этой записи.</span><span class="sxs-lookup"><span data-stu-id="7a178-130">Defines the .NET types that use this table entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7a178-131">Замечания</span><span class="sxs-lookup"><span data-stu-id="7a178-131">Remarks</span></span>

<span data-ttu-id="7a178-132">Каждая запись списка должна иметь по крайней мере одно определенное имя типа, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="7a178-132">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="7a178-133">При определении условия выбора применяются следующие требования.</span><span class="sxs-lookup"><span data-stu-id="7a178-133">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="7a178-134">Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.</span><span class="sxs-lookup"><span data-stu-id="7a178-134">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="7a178-135">Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.</span><span class="sxs-lookup"><span data-stu-id="7a178-135">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="7a178-136">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="7a178-136">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="7a178-137">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="7a178-137">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7a178-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="7a178-138">See Also</span></span>

[<span data-ttu-id="7a178-139">Создание табличного представления</span><span class="sxs-lookup"><span data-stu-id="7a178-139">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="7a178-140">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="7a178-140">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="7a178-141">Элемент Ентриселектедби (Format)</span><span class="sxs-lookup"><span data-stu-id="7a178-141">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="7a178-142">Элемент PropertyName для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="7a178-142">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[<span data-ttu-id="7a178-143">Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="7a178-143">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="7a178-144">Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="7a178-144">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="7a178-145">Элемент TypeName для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="7a178-145">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="7a178-146">Создание файла форматирования и типов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7a178-146">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
