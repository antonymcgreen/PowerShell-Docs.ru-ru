---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент TableColumnItems для элемента TableRowEntry для элемента TableControl (формат)
description: Элемент TableColumnItems для элемента TableRowEntry для элемента TableControl (формат)
ms.openlocfilehash: 4d600a366d2be1c453f05b301bdf575351dd51c1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667765"
---
# <a name="tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format"></a><span data-ttu-id="33884-103">Элемент TableColumnItems для элемента TableRowEntry для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="33884-103">TableColumnItems Element for TableRowEntry for TableControl (Format)</span></span>

<span data-ttu-id="33884-104">Определяет свойства или скрипты, значения которых отображаются в строке.</span><span class="sxs-lookup"><span data-stu-id="33884-104">Defines the properties or scripts whose values are displayed in a row.</span></span>

<span data-ttu-id="33884-105">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент Таблеконтрол (Format) элемент Таблеровентриес для Таблеконтрол (Format) Таблеровентри для таблеровентриес для TableControl (Format) TableColumnItems для TableControlEntry в TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="33884-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format) TableColumnItems Element for TableControlEntry for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="33884-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="33884-106">Syntax</span></span>

```xml
TableColumnItems>
  <TableColumnItem>...</TableColumnItem>
</TableColumnItems>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="33884-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="33884-107">Attributes and Elements</span></span>

<span data-ttu-id="33884-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TableColumnItems` элемента.</span><span class="sxs-lookup"><span data-stu-id="33884-108">The following sections describe the attributes, child elements, and parent element of the `TableColumnItems` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="33884-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="33884-109">Attributes</span></span>

<span data-ttu-id="33884-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="33884-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="33884-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="33884-111">Child Elements</span></span>

|<span data-ttu-id="33884-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="33884-112">Element</span></span>|<span data-ttu-id="33884-113">Описание</span><span class="sxs-lookup"><span data-stu-id="33884-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="33884-114">Элемент TableColumnItem для элемента TableColumnItems для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="33884-114">TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="33884-115">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="33884-115">Required element.</span></span><br /><br /> <span data-ttu-id="33884-116">Определяет свойство или скрипт, значение которого отображается в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="33884-116">Defines the property or script whose value is displayed in a column of the row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="33884-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="33884-117">Parent Elements</span></span>

|<span data-ttu-id="33884-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="33884-118">Element</span></span>|<span data-ttu-id="33884-119">Описание</span><span class="sxs-lookup"><span data-stu-id="33884-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="33884-120">Элемент TableRowEntry для элемента TableRowEntries для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="33884-120">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="33884-121">Определяет данные, отображаемые в строке таблицы.</span><span class="sxs-lookup"><span data-stu-id="33884-121">Defines the data that is displayed in a row of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="33884-122">Комментарии</span><span class="sxs-lookup"><span data-stu-id="33884-122">Remarks</span></span>

<span data-ttu-id="33884-123">`TableColumnItem`Для каждого столбца строки требуется элемент.</span><span class="sxs-lookup"><span data-stu-id="33884-123">A `TableColumnItem` element is required for each column of the row.</span></span> <span data-ttu-id="33884-124">Первая запись отображается в первом столбце, второй элемент во втором столбце и т. д.</span><span class="sxs-lookup"><span data-stu-id="33884-124">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

<span data-ttu-id="33884-125">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="33884-125">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="33884-126">Пример</span><span class="sxs-lookup"><span data-stu-id="33884-126">Example</span></span>

<span data-ttu-id="33884-127">В следующем примере показан `TableColumnItems` элемент, определяющий три свойства объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="33884-127">The following example shows a `TableColumnItems` element that defines three properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItems>
  <TableColumnItem>
    <PropertyName>Status</PropertyName>
  </TableColumnItem>
  <TableColumnItem>
    <PropertyName>Name</PropertyName>
  </TableColumnItem>
  <TableColumnItem>
    <PropertyName>DisplayName</PropertyName>
  </TableColumnItem>
</TableColumnItems>

```

## <a name="see-also"></a><span data-ttu-id="33884-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="33884-128">See Also</span></span>

[<span data-ttu-id="33884-129">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="33884-129">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="33884-130">Элемент Таблеколумнитем (Format)</span><span class="sxs-lookup"><span data-stu-id="33884-130">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="33884-131">Элемент Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="33884-131">TableRowEntry Element (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="33884-132">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="33884-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
