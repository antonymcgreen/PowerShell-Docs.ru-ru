---
title: Элемент EntrySelectedBy для TableRowEntry для TableControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49623fcf-1238-4d20-a7ce-238d47d9d565
caps.latest.revision: 15
ms.openlocfilehash: 9302bfed0324773cb98d698acdcf608f34ee19c1
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066164"
---
# <a name="entryselectedby-element-for-tablerowentry--for-tablecontrol-format"></a><span data-ttu-id="dbc8b-102">Элемент EntrySelectedBy для элемента TableRowEntry для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="dbc8b-102">EntrySelectedBy Element for TableRowEntry  for TableControl (Format)</span></span>

<span data-ttu-id="dbc8b-103">Определяет типы .NET, использовать это определение представления таблицы или условие, которое должен существовать для данного определения для использования.</span><span class="sxs-lookup"><span data-stu-id="dbc8b-103">Defines the .NET types that use this definition of the table view or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="dbc8b-104">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) элемент TableRowEntries (формат) элемент TableRowEntry (формат) EntrySelectedBy элемент конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="dbc8b-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="dbc8b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dbc8b-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="dbc8b-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dbc8b-106">Attributes and Elements</span></span>

<span data-ttu-id="dbc8b-107">Ниже описаны атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемент.</span><span class="sxs-lookup"><span data-stu-id="dbc8b-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="dbc8b-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dbc8b-108">Attributes</span></span>

<span data-ttu-id="dbc8b-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="dbc8b-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="dbc8b-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dbc8b-110">Child Elements</span></span>

|<span data-ttu-id="dbc8b-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="dbc8b-111">Element</span></span>|<span data-ttu-id="dbc8b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="dbc8b-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dbc8b-113">Элемент SelectionCondition для EntrySelectedBy для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="dbc8b-113">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="dbc8b-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="dbc8b-114">Optional element.</span></span><br /><br /> <span data-ttu-id="dbc8b-115">Определяет условие, которое должен существовать для данного определения представления таблицы для использования.</span><span class="sxs-lookup"><span data-stu-id="dbc8b-115">Defines the condition that must exist for this table view definition to be used.</span></span>|
|[<span data-ttu-id="dbc8b-116">Элемент SelectionSetName для EntrySelectedBy для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="dbc8b-116">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="dbc8b-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="dbc8b-117">Optional element.</span></span><br /><br /> <span data-ttu-id="dbc8b-118">Задает набор типов .NET, которые используют это определение представления таблицы.</span><span class="sxs-lookup"><span data-stu-id="dbc8b-118">Specifies a set of .NET types that use this table view definition.</span></span>|
|[<span data-ttu-id="dbc8b-119">TypeName-элемент для EntrySelectedBy для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="dbc8b-119">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>](./typename-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="dbc8b-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="dbc8b-120">Optional element.</span></span><br /><br /> <span data-ttu-id="dbc8b-121">Указывает тип .NET, который использует это определение представления таблицы.</span><span class="sxs-lookup"><span data-stu-id="dbc8b-121">Specifies a .NET type that uses this table view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="dbc8b-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dbc8b-122">Parent Elements</span></span>

|<span data-ttu-id="dbc8b-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="dbc8b-123">Element</span></span>|<span data-ttu-id="dbc8b-124">Описание</span><span class="sxs-lookup"><span data-stu-id="dbc8b-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dbc8b-125">Элемент TableRowEntry для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="dbc8b-125">TableRowEntry Element for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="dbc8b-126">Определяет данные, которые отображаются в строке таблицы.</span><span class="sxs-lookup"><span data-stu-id="dbc8b-126">Defines the data that is displayed in a row of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="dbc8b-127">Замечания</span><span class="sxs-lookup"><span data-stu-id="dbc8b-127">Remarks</span></span>

<span data-ttu-id="dbc8b-128">Необходимо указать по крайней мере один тип, выбора или условию выбора для определения представления таблицы.</span><span class="sxs-lookup"><span data-stu-id="dbc8b-128">You must specify at least one type, selection set, or selection condition for a table view definition.</span></span> <span data-ttu-id="dbc8b-129">Не ограничено максимальное число дочерних элементов, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="dbc8b-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="dbc8b-130">Выбор условия используются для определения условия, которое должен существовать для определения для использования, например, если объект имеет определенное свойство или значение конкретного свойства или скрипт принимает значение `true`.</span><span class="sxs-lookup"><span data-stu-id="dbc8b-130">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="dbc8b-131">Дополнительные сведения об условиях выделения, см. в разделе [определение условий для, когда операция отчета или элемента используется](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="dbc8b-131">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="dbc8b-132">Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="dbc8b-132">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="dbc8b-133">Пример</span><span class="sxs-lookup"><span data-stu-id="dbc8b-133">Example</span></span>

<span data-ttu-id="dbc8b-134">В следующем примере показан `TableRowEntry` элемент, который используется для отображения свойств [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) объекта.</span><span class="sxs-lookup"><span data-stu-id="dbc8b-134">The following example shows a `TableRowEntry` element that is used to display the properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="dbc8b-135">См. также</span><span class="sxs-lookup"><span data-stu-id="dbc8b-135">See Also</span></span>

[<span data-ttu-id="dbc8b-136">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="dbc8b-136">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="dbc8b-137">Элемент SelectionCondition для EntrySelectedBy для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="dbc8b-137">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="dbc8b-138">Элемент SelectionSetName для EntrySelectedBy для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="dbc8b-138">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="dbc8b-139">Элемент TableRowEntry для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="dbc8b-139">TableRowEntry Element for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="dbc8b-140">TypeName-элемент для EntrySelectedBy для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="dbc8b-140">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>](./typename-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="dbc8b-141">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="dbc8b-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
