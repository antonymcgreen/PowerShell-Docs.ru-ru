---
title: Элемент Таблеровентриес для Таблеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 4cc5d354df3e552e181a95148caa020f0041db92
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785121"
---
# <a name="tablerowentries-element-for-tablecontrol-format"></a><span data-ttu-id="82516-102">Элемент TableRowEntries для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="82516-102">TableRowEntries Element for TableControl (Format)</span></span>

<span data-ttu-id="82516-103">Определяет строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="82516-103">Defines the rows of the table.</span></span>

<span data-ttu-id="82516-104">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Таблеконтрол элемент (Format) Таблеровентриес для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="82516-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="82516-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82516-105">Syntax</span></span>

```xml
<TableRowEntries>
  <TableRowEntry>...</TableRowEntry>
</TableRowEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="82516-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="82516-106">Attributes and Elements</span></span>

<span data-ttu-id="82516-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TableRowEntries` элемента.</span><span class="sxs-lookup"><span data-stu-id="82516-107">The following sections describe the attributes, child elements, and parent element of the `TableRowEntries` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="82516-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="82516-108">Attributes</span></span>

<span data-ttu-id="82516-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="82516-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="82516-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="82516-110">Child Elements</span></span>

|<span data-ttu-id="82516-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="82516-111">Element</span></span>|<span data-ttu-id="82516-112">Описание</span><span class="sxs-lookup"><span data-stu-id="82516-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="82516-113">Элемент TableRowEntry для элемента TableRowEntries для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="82516-113">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="82516-114">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="82516-114">Required element.</span></span><br /><br /> <span data-ttu-id="82516-115">Определяет данные, отображаемые в строке таблицы.</span><span class="sxs-lookup"><span data-stu-id="82516-115">Defines the data that is displayed in a row of the table.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="82516-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="82516-116">Parent Elements</span></span>

|<span data-ttu-id="82516-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="82516-117">Element</span></span>|<span data-ttu-id="82516-118">Описание</span><span class="sxs-lookup"><span data-stu-id="82516-118">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="82516-119">Элемент TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="82516-119">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="82516-120">Определяет формат таблицы для представления.</span><span class="sxs-lookup"><span data-stu-id="82516-120">Defines a table format for a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="82516-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="82516-121">Remarks</span></span>

<span data-ttu-id="82516-122">Необходимо указать один или несколько `TableRowEntry` элементов для табличного представления.</span><span class="sxs-lookup"><span data-stu-id="82516-122">You must specify one or more `TableRowEntry` elements for the table view.</span></span> <span data-ttu-id="82516-123">Максимальное ограничение количества `TableRowEntry` элементов, которое можно добавить, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="82516-123">There is no maximum limit to the number of `TableRowEntry` elements that can be added nor is their order significant.</span></span>

<span data-ttu-id="82516-124">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="82516-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="82516-125">Пример</span><span class="sxs-lookup"><span data-stu-id="82516-125">Example</span></span>

<span data-ttu-id="82516-126">В следующем примере показан `TableRowEntries` элемент, определяющий строку, в которой отображаются значения двух свойств объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="82516-126">The following example shows a `TableRowEntries` element that defines a row that displays the values of two properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="82516-127">См. также</span><span class="sxs-lookup"><span data-stu-id="82516-127">See Also</span></span>

[<span data-ttu-id="82516-128">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="82516-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="82516-129">Элемент TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="82516-129">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="82516-130">Элемент Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="82516-130">TableRowEntry Element (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="82516-131">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="82516-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
