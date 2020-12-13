---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент TableRowEntries для элемента TableControl (формат)
description: Элемент TableRowEntries для элемента TableControl (формат)
ms.openlocfilehash: 1df63e645234da8276c7ccc5af34e81a56475e43
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651478"
---
# <a name="tablerowentries-element-for-tablecontrol-format"></a><span data-ttu-id="738b0-103">Элемент TableRowEntries для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="738b0-103">TableRowEntries Element for TableControl (Format)</span></span>

<span data-ttu-id="738b0-104">Определяет строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="738b0-104">Defines the rows of the table.</span></span>

<span data-ttu-id="738b0-105">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Таблеконтрол элемент (Format) Таблеровентриес для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="738b0-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="738b0-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="738b0-106">Syntax</span></span>

```xml
<TableRowEntries>
  <TableRowEntry>...</TableRowEntry>
</TableRowEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="738b0-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="738b0-107">Attributes and Elements</span></span>

<span data-ttu-id="738b0-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TableRowEntries` элемента.</span><span class="sxs-lookup"><span data-stu-id="738b0-108">The following sections describe the attributes, child elements, and parent element of the `TableRowEntries` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="738b0-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="738b0-109">Attributes</span></span>

<span data-ttu-id="738b0-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="738b0-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="738b0-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="738b0-111">Child Elements</span></span>

|<span data-ttu-id="738b0-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="738b0-112">Element</span></span>|<span data-ttu-id="738b0-113">Описание</span><span class="sxs-lookup"><span data-stu-id="738b0-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="738b0-114">Элемент TableRowEntry для элемента TableRowEntries для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="738b0-114">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="738b0-115">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="738b0-115">Required element.</span></span><br /><br /> <span data-ttu-id="738b0-116">Определяет данные, отображаемые в строке таблицы.</span><span class="sxs-lookup"><span data-stu-id="738b0-116">Defines the data that is displayed in a row of the table.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="738b0-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="738b0-117">Parent Elements</span></span>

|<span data-ttu-id="738b0-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="738b0-118">Element</span></span>|<span data-ttu-id="738b0-119">Описание</span><span class="sxs-lookup"><span data-stu-id="738b0-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="738b0-120">Элемент TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="738b0-120">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="738b0-121">Определяет формат таблицы для представления.</span><span class="sxs-lookup"><span data-stu-id="738b0-121">Defines a table format for a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="738b0-122">Комментарии</span><span class="sxs-lookup"><span data-stu-id="738b0-122">Remarks</span></span>

<span data-ttu-id="738b0-123">Необходимо указать один или несколько `TableRowEntry` элементов для табличного представления.</span><span class="sxs-lookup"><span data-stu-id="738b0-123">You must specify one or more `TableRowEntry` elements for the table view.</span></span> <span data-ttu-id="738b0-124">Максимальное ограничение количества `TableRowEntry` элементов, которое можно добавить, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="738b0-124">There is no maximum limit to the number of `TableRowEntry` elements that can be added nor is their order significant.</span></span>

<span data-ttu-id="738b0-125">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="738b0-125">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="738b0-126">Пример</span><span class="sxs-lookup"><span data-stu-id="738b0-126">Example</span></span>

<span data-ttu-id="738b0-127">В следующем примере показан `TableRowEntries` элемент, определяющий строку, в которой отображаются значения двух свойств объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="738b0-127">The following example shows a `TableRowEntries` element that defines a row that displays the values of two properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableRowEntries>
  <TableRowEntry>
    <EntrySelectedBy>
      <TypeName>System.Diagnostics.Process</TypeName>
    </EntrySelectedBy>
    <TableColumnItems>
      <TableColumnItem>
        <PropertyName> Property for first column</PropertyName>
      </TableColumnItem>
      <TableColumnItem>
        <PropertyName> Property for second column</PropertyName>
      </TableColumnItem>
    </TableColumnItems>
  </TableRowEntry>
</TableRowEntries>

```

## <a name="see-also"></a><span data-ttu-id="738b0-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="738b0-128">See Also</span></span>

[<span data-ttu-id="738b0-129">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="738b0-129">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="738b0-130">Элемент TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="738b0-130">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="738b0-131">Элемент Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="738b0-131">TableRowEntry Element (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="738b0-132">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="738b0-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
