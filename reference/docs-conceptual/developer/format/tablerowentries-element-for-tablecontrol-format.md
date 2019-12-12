---
title: Элемент Таблеровентриес для Таблеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d10b68ca-256c-4c58-b503-73f7777b39ae
caps.latest.revision: 15
ms.openlocfilehash: 88de19be02de4933f892e02093403a82ccdd5788
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368153"
---
# <a name="tablerowentries-element-for-tablecontrol-format"></a><span data-ttu-id="727f0-102">Элемент TableRowEntries для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="727f0-102">TableRowEntries Element for TableControl (Format)</span></span>

<span data-ttu-id="727f0-103">Определяет строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="727f0-103">Defines the rows of the table.</span></span>

<span data-ttu-id="727f0-104">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Таблеконтрол элемент (Format) Таблеровентриес для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="727f0-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="727f0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="727f0-105">Syntax</span></span>

```xml
<TableRowEntries>
  <TableRowEntry>...</TableRowEntry>
</TableRowEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="727f0-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="727f0-106">Attributes and Elements</span></span>

<span data-ttu-id="727f0-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `TableRowEntries`.</span><span class="sxs-lookup"><span data-stu-id="727f0-107">The following sections describe the attributes, child elements, and parent element of the `TableRowEntries` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="727f0-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="727f0-108">Attributes</span></span>

<span data-ttu-id="727f0-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="727f0-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="727f0-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="727f0-110">Child Elements</span></span>

|<span data-ttu-id="727f0-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="727f0-111">Element</span></span>|<span data-ttu-id="727f0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="727f0-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="727f0-113">Элемент Таблеровентри для Таблеровентриес для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="727f0-113">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="727f0-114">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="727f0-114">Required element.</span></span><br /><br /> <span data-ttu-id="727f0-115">Определяет данные, отображаемые в строке таблицы.</span><span class="sxs-lookup"><span data-stu-id="727f0-115">Defines the data that is displayed in a row of the table.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="727f0-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="727f0-116">Parent Elements</span></span>

|<span data-ttu-id="727f0-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="727f0-117">Element</span></span>|<span data-ttu-id="727f0-118">Описание</span><span class="sxs-lookup"><span data-stu-id="727f0-118">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="727f0-119">Элемент Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="727f0-119">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="727f0-120">Определяет формат таблицы для представления.</span><span class="sxs-lookup"><span data-stu-id="727f0-120">Defines a table format for a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="727f0-121">Замечания</span><span class="sxs-lookup"><span data-stu-id="727f0-121">Remarks</span></span>

<span data-ttu-id="727f0-122">Необходимо указать один или несколько элементов `TableRowEntry` для табличного представления.</span><span class="sxs-lookup"><span data-stu-id="727f0-122">You must specify one or more `TableRowEntry` elements for the table view.</span></span> <span data-ttu-id="727f0-123">Максимальное ограничение числа элементов `TableRowEntry`, которые могут быть добавлены, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="727f0-123">There is no maximum limit to the number of `TableRowEntry` elements that can be added nor is their order significant.</span></span>

<span data-ttu-id="727f0-124">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="727f0-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="727f0-125">Пример</span><span class="sxs-lookup"><span data-stu-id="727f0-125">Example</span></span>

<span data-ttu-id="727f0-126">В следующем примере показан элемент `TableRowEntries`, определяющий строку, в которой отображаются значения двух свойств объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="727f0-126">The following example shows a `TableRowEntries` element that defines a row that displays the values of two properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="727f0-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="727f0-127">See Also</span></span>

[<span data-ttu-id="727f0-128">Создание табличного представления</span><span class="sxs-lookup"><span data-stu-id="727f0-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="727f0-129">Элемент Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="727f0-129">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="727f0-130">Элемент Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="727f0-130">TableRowEntry Element (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="727f0-131">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="727f0-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
