---
title: Элемент Ентриселектедби для Таблеровентри для Таблеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49623fcf-1238-4d20-a7ce-238d47d9d565
caps.latest.revision: 15
ms.openlocfilehash: 9302bfed0324773cb98d698acdcf608f34ee19c1
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363343"
---
# <a name="entryselectedby-element-for-tablerowentry--for-tablecontrol-format"></a><span data-ttu-id="f462f-102">Элемент EntrySelectedBy для элемента TableRowEntry для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="f462f-102">EntrySelectedBy Element for TableRowEntry  for TableControl (Format)</span></span>

<span data-ttu-id="f462f-103">Определяет типы .NET, использующие это определение табличного представления, или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="f462f-103">Defines the .NET types that use this definition of the table view or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="f462f-104">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Ентриселектедби (формат)</span><span class="sxs-lookup"><span data-stu-id="f462f-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f462f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f462f-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f462f-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f462f-106">Attributes and Elements</span></span>

<span data-ttu-id="f462f-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `EntrySelectedBy`.</span><span class="sxs-lookup"><span data-stu-id="f462f-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f462f-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f462f-108">Attributes</span></span>

<span data-ttu-id="f462f-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="f462f-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f462f-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f462f-110">Child Elements</span></span>

|<span data-ttu-id="f462f-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="f462f-111">Element</span></span>|<span data-ttu-id="f462f-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f462f-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f462f-113">Элемент Селектионкондитион для Ентриселектедби для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="f462f-113">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="f462f-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f462f-114">Optional element.</span></span><br /><br /> <span data-ttu-id="f462f-115">Определяет условие, которое должно существовать, чтобы использовать это определение табличного представления.</span><span class="sxs-lookup"><span data-stu-id="f462f-115">Defines the condition that must exist for this table view definition to be used.</span></span>|
|[<span data-ttu-id="f462f-116">Элемент Селектионсетнаме для Ентриселектедби для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="f462f-116">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="f462f-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f462f-117">Optional element.</span></span><br /><br /> <span data-ttu-id="f462f-118">Задает набор типов .NET, использующих это определение табличного представления.</span><span class="sxs-lookup"><span data-stu-id="f462f-118">Specifies a set of .NET types that use this table view definition.</span></span>|
|[<span data-ttu-id="f462f-119">Элемент TypeName для Ентриселектедби для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="f462f-119">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>](./typename-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="f462f-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f462f-120">Optional element.</span></span><br /><br /> <span data-ttu-id="f462f-121">Указывает тип .NET, использующий это определение табличного представления.</span><span class="sxs-lookup"><span data-stu-id="f462f-121">Specifies a .NET type that uses this table view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f462f-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f462f-122">Parent Elements</span></span>

|<span data-ttu-id="f462f-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="f462f-123">Element</span></span>|<span data-ttu-id="f462f-124">Описание</span><span class="sxs-lookup"><span data-stu-id="f462f-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f462f-125">Элемент Таблеровентри для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="f462f-125">TableRowEntry Element for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="f462f-126">Определяет данные, отображаемые в строке таблицы.</span><span class="sxs-lookup"><span data-stu-id="f462f-126">Defines the data that is displayed in a row of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f462f-127">Замечания</span><span class="sxs-lookup"><span data-stu-id="f462f-127">Remarks</span></span>

<span data-ttu-id="f462f-128">Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения табличного представления.</span><span class="sxs-lookup"><span data-stu-id="f462f-128">You must specify at least one type, selection set, or selection condition for a table view definition.</span></span> <span data-ttu-id="f462f-129">Максимальное количество дочерних элементов, которое можно использовать, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="f462f-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="f462f-130">Условия выбора используются для определения условия, которое должно существовать, чтобы использовать определение, например, если объект имеет определенное свойство или значение конкретного свойства или скрипта равно `true`.</span><span class="sxs-lookup"><span data-stu-id="f462f-130">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="f462f-131">Дополнительные сведения об условиях выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="f462f-131">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="f462f-132">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="f462f-132">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="f462f-133">Пример</span><span class="sxs-lookup"><span data-stu-id="f462f-133">Example</span></span>

<span data-ttu-id="f462f-134">В следующем примере показан элемент `TableRowEntry`, используемый для отображения свойств объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="f462f-134">The following example shows a `TableRowEntry` element that is used to display the properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f462f-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="f462f-135">See Also</span></span>

[<span data-ttu-id="f462f-136">Создание табличного представления</span><span class="sxs-lookup"><span data-stu-id="f462f-136">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="f462f-137">Элемент Селектионкондитион для Ентриселектедби для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="f462f-137">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="f462f-138">Элемент Селектионсетнаме для Ентриселектедби для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="f462f-138">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="f462f-139">Элемент Таблеровентри для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="f462f-139">TableRowEntry Element for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="f462f-140">Элемент TypeName для Ентриселектедби для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="f462f-140">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>](./typename-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="f462f-141">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="f462f-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
