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
ms.openlocfilehash: e18564c10898c73128e0a4bc7d077e7c7ffb1c22
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862330"
---
# <a name="entryselectedby-element-for-tablerowentry--for-tablecontrol-format"></a><span data-ttu-id="d3b54-102">Элемент EntrySelectedBy для элемента TableRowEntry для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="d3b54-102">EntrySelectedBy Element for TableRowEntry  for TableControl (Format)</span></span>

<span data-ttu-id="d3b54-103">Определяет типы .NET, использовать это определение представления таблицы или условие, которое должен существовать для данного определения для использования.</span><span class="sxs-lookup"><span data-stu-id="d3b54-103">Defines the .NET types that use this definition of the table view or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="d3b54-104">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) элемент TableRowEntries (формат) элемент TableRowEntry (формат) EntrySelectedBy элемент конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="d3b54-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d3b54-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d3b54-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d3b54-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d3b54-106">Attributes and Elements</span></span>

<span data-ttu-id="d3b54-107">Ниже описаны атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемент.</span><span class="sxs-lookup"><span data-stu-id="d3b54-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d3b54-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d3b54-108">Attributes</span></span>

<span data-ttu-id="d3b54-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="d3b54-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d3b54-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d3b54-110">Child Elements</span></span>

|<span data-ttu-id="d3b54-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="d3b54-111">Element</span></span>|<span data-ttu-id="d3b54-112">Описание</span><span class="sxs-lookup"><span data-stu-id="d3b54-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d3b54-113">Элемент SelectionCondition для EntrySelectedBy для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="d3b54-113">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="d3b54-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d3b54-114">Optional element.</span></span><br /><br /> <span data-ttu-id="d3b54-115">Определяет условие, которое должен существовать для данного определения представления таблицы для использования.</span><span class="sxs-lookup"><span data-stu-id="d3b54-115">Defines the condition that must exist for this table view definition to be used.</span></span>|
|[<span data-ttu-id="d3b54-116">Элемент SelectionSetName для EntrySelectedBy для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="d3b54-116">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="d3b54-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d3b54-117">Optional element.</span></span><br /><br /> <span data-ttu-id="d3b54-118">Задает набор типов .NET, которые используют это определение представления таблицы.</span><span class="sxs-lookup"><span data-stu-id="d3b54-118">Specifies a set of .NET types that use this table view definition.</span></span>|
|[<span data-ttu-id="d3b54-119">TypeName-элемент для EntrySelectedBy для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="d3b54-119">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>](./typename-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="d3b54-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d3b54-120">Optional element.</span></span><br /><br /> <span data-ttu-id="d3b54-121">Указывает тип .NET, который использует это определение представления таблицы.</span><span class="sxs-lookup"><span data-stu-id="d3b54-121">Specifies a .NET type that uses this table view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d3b54-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d3b54-122">Parent Elements</span></span>

|<span data-ttu-id="d3b54-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="d3b54-123">Element</span></span>|<span data-ttu-id="d3b54-124">Описание</span><span class="sxs-lookup"><span data-stu-id="d3b54-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d3b54-125">Элемент TableRowEntry для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="d3b54-125">TableRowEntry Element for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentroes-for-tablecontrol-format.md)|<span data-ttu-id="d3b54-126">Определяет данные, которые отображаются в строке таблицы.</span><span class="sxs-lookup"><span data-stu-id="d3b54-126">Defines the data that is displayed in a row of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d3b54-127">Замечания</span><span class="sxs-lookup"><span data-stu-id="d3b54-127">Remarks</span></span>

<span data-ttu-id="d3b54-128">Необходимо указать по крайней мере один тип, выбора или условию выбора для определения представления таблицы.</span><span class="sxs-lookup"><span data-stu-id="d3b54-128">You must specify at least one type, selection set, or selection condition for a table view definition.</span></span> <span data-ttu-id="d3b54-129">Не ограничено максимальное число дочерних элементов, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="d3b54-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="d3b54-130">Выбор условия используются для определения условия, которое должен существовать для определения для использования, например, если объект имеет определенное свойство или значение конкретного свойства или скрипт принимает значение `true`.</span><span class="sxs-lookup"><span data-stu-id="d3b54-130">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="d3b54-131">Дополнительные сведения об условиях выделения, см. в разделе [определение условий для, когда операция отчета или элемента используется](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="d3b54-131">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="d3b54-132">Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="d3b54-132">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="d3b54-133">Пример</span><span class="sxs-lookup"><span data-stu-id="d3b54-133">Example</span></span>

<span data-ttu-id="d3b54-134">В следующем примере показан `TableRowEntry` элемент, который используется для отображения свойств [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) объекта.</span><span class="sxs-lookup"><span data-stu-id="d3b54-134">The following example shows a `TableRowEntry` element that is used to display the properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="d3b54-135">См. также</span><span class="sxs-lookup"><span data-stu-id="d3b54-135">See Also</span></span>

[<span data-ttu-id="d3b54-136">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="d3b54-136">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="d3b54-137">Элемент SelectionCondition для EntrySelectedBy для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="d3b54-137">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="d3b54-138">Элемент SelectionSetName для EntrySelectedBy для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="d3b54-138">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="d3b54-139">Элемент TableRowEntry для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="d3b54-139">TableRowEntry Element for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentroes-for-tablecontrol-format.md)

[<span data-ttu-id="d3b54-140">TypeName-элемент для EntrySelectedBy для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="d3b54-140">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>](./typename-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="d3b54-141">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3b54-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
