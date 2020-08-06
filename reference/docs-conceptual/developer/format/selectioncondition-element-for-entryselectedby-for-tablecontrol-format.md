---
title: Элемент Селектионкондитион для Ентриселектедби для Таблеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 4a829f9daef22c4b3fd6b21dfb3af2f8539bdeb3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780293"
---
# <a name="selectioncondition-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="8fae7-102">Элемент SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="8fae7-102">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="8fae7-103">Определяет условие, которое должно существовать для использования в этом определении табличного представления.</span><span class="sxs-lookup"><span data-stu-id="8fae7-103">Defines the condition that must exist to use for this definition of the table view.</span></span> <span data-ttu-id="8fae7-104">Количество условий выбора, которое можно указать для определения таблицы, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="8fae7-104">There is no limit to the number of selection conditions that can be specified for a table definition.</span></span>

<span data-ttu-id="8fae7-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Ентриселектедби для таблеровентри (Format) SelectionCondition для EntrySelectedBy в TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="8fae7-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8fae7-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8fae7-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8fae7-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8fae7-107">Attributes and Elements</span></span>

<span data-ttu-id="8fae7-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента Селектионкондитион.</span><span class="sxs-lookup"><span data-stu-id="8fae7-108">The following sections describe attributes, child elements, and the parent element of the SelectionCondition element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8fae7-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8fae7-109">Attributes</span></span>

<span data-ttu-id="8fae7-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8fae7-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8fae7-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8fae7-111">Child Elements</span></span>

|<span data-ttu-id="8fae7-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="8fae7-112">Element</span></span>|<span data-ttu-id="8fae7-113">Описание</span><span class="sxs-lookup"><span data-stu-id="8fae7-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8fae7-114">Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="8fae7-114">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)|<span data-ttu-id="8fae7-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="8fae7-115">Optional element.</span></span><br /><br /> <span data-ttu-id="8fae7-116">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="8fae7-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="8fae7-117">Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="8fae7-117">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="8fae7-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="8fae7-118">Optional element.</span></span><br /><br /> <span data-ttu-id="8fae7-119">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="8fae7-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="8fae7-120">Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="8fae7-120">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="8fae7-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="8fae7-121">Optional element.</span></span><br /><br /> <span data-ttu-id="8fae7-122">Указывает набор типов .NET, которые активируют условие.</span><span class="sxs-lookup"><span data-stu-id="8fae7-122">Specifies the set of .NET types that trigger the condition.</span></span>|
|[<span data-ttu-id="8fae7-123">Элемент TypeName для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="8fae7-123">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="8fae7-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="8fae7-124">Optional element.</span></span><br /><br /> <span data-ttu-id="8fae7-125">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="8fae7-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="8fae7-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8fae7-126">Parent Elements</span></span>

|<span data-ttu-id="8fae7-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="8fae7-127">Element</span></span>|<span data-ttu-id="8fae7-128">Описание</span><span class="sxs-lookup"><span data-stu-id="8fae7-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8fae7-129">Элемент Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="8fae7-129">EntrySelectedBy Element for TableRowEntry (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="8fae7-130">Определяет типы .NET, которые используют эту запись таблицы, или условие, которое должно существовать для использования этой записи.</span><span class="sxs-lookup"><span data-stu-id="8fae7-130">Defines the .NET types that use this table entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8fae7-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="8fae7-131">Remarks</span></span>

<span data-ttu-id="8fae7-132">Каждая запись списка должна иметь по крайней мере одно определенное имя типа, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="8fae7-132">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="8fae7-133">При определении условия выбора применяются следующие требования.</span><span class="sxs-lookup"><span data-stu-id="8fae7-133">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="8fae7-134">Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.</span><span class="sxs-lookup"><span data-stu-id="8fae7-134">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="8fae7-135">Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.</span><span class="sxs-lookup"><span data-stu-id="8fae7-135">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="8fae7-136">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="8fae7-136">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="8fae7-137">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="8fae7-137">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8fae7-138">См. также</span><span class="sxs-lookup"><span data-stu-id="8fae7-138">See Also</span></span>

[<span data-ttu-id="8fae7-139">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="8fae7-139">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="8fae7-140">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="8fae7-140">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="8fae7-141">Элемент Ентриселектедби (Format)</span><span class="sxs-lookup"><span data-stu-id="8fae7-141">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="8fae7-142">Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="8fae7-142">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[<span data-ttu-id="8fae7-143">Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="8fae7-143">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="8fae7-144">Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="8fae7-144">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="8fae7-145">Элемент TypeName для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="8fae7-145">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="8fae7-146">Создание файла форматирования и типов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8fae7-146">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
