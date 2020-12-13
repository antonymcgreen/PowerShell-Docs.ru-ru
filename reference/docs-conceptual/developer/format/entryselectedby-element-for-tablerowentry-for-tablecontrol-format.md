---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент EntrySelectedBy для элемента TableRowEntry для элемента TableControl (формат)
description: Элемент EntrySelectedBy для элемента TableRowEntry для элемента TableControl (формат)
ms.openlocfilehash: 1b7fc60b6fa9864b66e9edfebb3e4a86e287f3f8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645904"
---
# <a name="entryselectedby-element-for-tablerowentry--for-tablecontrol-format"></a><span data-ttu-id="485c1-103">Элемент EntrySelectedBy для элемента TableRowEntry для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="485c1-103">EntrySelectedBy Element for TableRowEntry  for TableControl (Format)</span></span>

<span data-ttu-id="485c1-104">Определяет типы .NET, использующие это определение табличного представления, или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="485c1-104">Defines the .NET types that use this definition of the table view or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="485c1-105">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Ентриселектедби (формат)</span><span class="sxs-lookup"><span data-stu-id="485c1-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="485c1-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="485c1-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="485c1-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="485c1-107">Attributes and Elements</span></span>

<span data-ttu-id="485c1-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемента.</span><span class="sxs-lookup"><span data-stu-id="485c1-108">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="485c1-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="485c1-109">Attributes</span></span>

<span data-ttu-id="485c1-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="485c1-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="485c1-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="485c1-111">Child Elements</span></span>

|<span data-ttu-id="485c1-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="485c1-112">Element</span></span>|<span data-ttu-id="485c1-113">Описание</span><span class="sxs-lookup"><span data-stu-id="485c1-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="485c1-114">Элемент SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="485c1-114">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="485c1-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="485c1-115">Optional element.</span></span><br /><br /> <span data-ttu-id="485c1-116">Определяет условие, которое должно существовать, чтобы использовать это определение табличного представления.</span><span class="sxs-lookup"><span data-stu-id="485c1-116">Defines the condition that must exist for this table view definition to be used.</span></span>|
|[<span data-ttu-id="485c1-117">Элемент SelectionSetName для элемента EntrySelectedBy для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="485c1-117">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="485c1-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="485c1-118">Optional element.</span></span><br /><br /> <span data-ttu-id="485c1-119">Задает набор типов .NET, использующих это определение табличного представления.</span><span class="sxs-lookup"><span data-stu-id="485c1-119">Specifies a set of .NET types that use this table view definition.</span></span>|
|[<span data-ttu-id="485c1-120">Элемент TypeName для элемента EntrySelectedBy для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="485c1-120">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>](./typename-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="485c1-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="485c1-121">Optional element.</span></span><br /><br /> <span data-ttu-id="485c1-122">Указывает тип .NET, использующий это определение табличного представления.</span><span class="sxs-lookup"><span data-stu-id="485c1-122">Specifies a .NET type that uses this table view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="485c1-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="485c1-123">Parent Elements</span></span>

|<span data-ttu-id="485c1-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="485c1-124">Element</span></span>|<span data-ttu-id="485c1-125">Описание</span><span class="sxs-lookup"><span data-stu-id="485c1-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="485c1-126">Элемент Таблеровентри для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="485c1-126">TableRowEntry Element for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="485c1-127">Определяет данные, отображаемые в строке таблицы.</span><span class="sxs-lookup"><span data-stu-id="485c1-127">Defines the data that is displayed in a row of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="485c1-128">Комментарии</span><span class="sxs-lookup"><span data-stu-id="485c1-128">Remarks</span></span>

<span data-ttu-id="485c1-129">Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения табличного представления.</span><span class="sxs-lookup"><span data-stu-id="485c1-129">You must specify at least one type, selection set, or selection condition for a table view definition.</span></span> <span data-ttu-id="485c1-130">Максимальное количество дочерних элементов, которое можно использовать, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="485c1-130">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="485c1-131">Условия выбора используются для определения условия, которое должно существовать, чтобы использовать определение, например, если объект имеет определенное свойство или значение конкретного свойства или скрипта равно `true` .</span><span class="sxs-lookup"><span data-stu-id="485c1-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="485c1-132">Дополнительные сведения об условиях выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="485c1-132">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="485c1-133">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="485c1-133">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="485c1-134">Пример</span><span class="sxs-lookup"><span data-stu-id="485c1-134">Example</span></span>

<span data-ttu-id="485c1-135">В следующем примере показан `TableRowEntry` элемент, используемый для отображения свойств объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="485c1-135">The following example shows a `TableRowEntry` element that is used to display the properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </EntrySelectedBy>
  <TableColumnItems>
    <TableColumnItem>
      <PropertyName>PropertyForFirstColumn</PropertyName>
    </TableColumnItem>
    <TableColumnItem>
      <PropertyName>PropertyForSecondColumn</PropertyName>
    </TableColumnItem>
  </TableColumnItems>
</TableRowEntry>
```

## <a name="see-also"></a><span data-ttu-id="485c1-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="485c1-136">See Also</span></span>

[<span data-ttu-id="485c1-137">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="485c1-137">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="485c1-138">Элемент SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="485c1-138">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="485c1-139">Элемент SelectionSetName для элемента EntrySelectedBy для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="485c1-139">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="485c1-140">Элемент Таблеровентри для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="485c1-140">TableRowEntry Element for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="485c1-141">Элемент TypeName для элемента EntrySelectedBy для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="485c1-141">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>](./typename-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="485c1-142">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="485c1-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
