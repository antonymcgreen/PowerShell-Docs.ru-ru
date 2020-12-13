---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент TableHeaders (формат)
description: Элемент TableHeaders (формат)
ms.openlocfilehash: 5ac4dccae746c167ebf95add9f3d18030a2b3a99
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659817"
---
# <a name="tableheaders-element-format"></a><span data-ttu-id="e3da2-103">Элемент TableHeaders (формат)</span><span class="sxs-lookup"><span data-stu-id="e3da2-103">TableHeaders Element (Format)</span></span>

<span data-ttu-id="e3da2-104">Определяет заголовки для столбцов таблицы.</span><span class="sxs-lookup"><span data-stu-id="e3da2-104">Defines the headers for the columns of a table.</span></span>

<span data-ttu-id="e3da2-105">Элемент Виевдефинитионс (Format) представления (Format) Таблеконтрол элемент (Format) Таблехеадерс для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="e3da2-105">ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e3da2-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3da2-106">Syntax</span></span>

```xml
<TableHeaders>
  <TableColumnHeader>...</TableColumnHeader>
</TableHeaders>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="e3da2-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e3da2-107">Attributes and Elements</span></span>

<span data-ttu-id="e3da2-108">В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы `TableHeaders` элемента.</span><span class="sxs-lookup"><span data-stu-id="e3da2-108">The following sections describe the attributes, child elements, and parent elements of the `TableHeaders` element.</span></span> <span data-ttu-id="e3da2-109">Должен существовать дочерний элемент для каждого свойства объекта, который должен быть отображен.</span><span class="sxs-lookup"><span data-stu-id="e3da2-109">There must be a child element for each property of the object that is to be displayed.</span></span> <span data-ttu-id="e3da2-110">Сведения о заголовке столбца отображаются в том порядке, в котором указаны дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="e3da2-110">The column header information is displayed in the order that the child elements are specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="e3da2-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e3da2-111">Attributes</span></span>

<span data-ttu-id="e3da2-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e3da2-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e3da2-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e3da2-113">Child Elements</span></span>

|<span data-ttu-id="e3da2-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="e3da2-114">Element</span></span>|<span data-ttu-id="e3da2-115">Описание</span><span class="sxs-lookup"><span data-stu-id="e3da2-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e3da2-116">Элемент TableColumnHeader (формат)</span><span class="sxs-lookup"><span data-stu-id="e3da2-116">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="e3da2-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e3da2-117">Optional element.</span></span><br /><br /> <span data-ttu-id="e3da2-118">Определяет метку, ширину и выравнивание данных для столбца табличного представления.</span><span class="sxs-lookup"><span data-stu-id="e3da2-118">Defines the label, the width, and the alignment of the data for a column of a table view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e3da2-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e3da2-119">Parent Elements</span></span>

|<span data-ttu-id="e3da2-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="e3da2-120">Element</span></span>|<span data-ttu-id="e3da2-121">Описание</span><span class="sxs-lookup"><span data-stu-id="e3da2-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e3da2-122">Элемент TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="e3da2-122">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="e3da2-123">Определяет формат таблицы для представления.</span><span class="sxs-lookup"><span data-stu-id="e3da2-123">Defines a table format for a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e3da2-124">Комментарии</span><span class="sxs-lookup"><span data-stu-id="e3da2-124">Remarks</span></span>

<span data-ttu-id="e3da2-125">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="e3da2-125">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="e3da2-126">Пример</span><span class="sxs-lookup"><span data-stu-id="e3da2-126">Example</span></span>

<span data-ttu-id="e3da2-127">В этом примере показан `TableHeaders` элемент, определяющий два заголовка столбцов.</span><span class="sxs-lookup"><span data-stu-id="e3da2-127">This example shows a `TableHeaders` element that defines two column headers.</span></span>

```xml
<TableHeaders>
  <TableColumnHeader>
    <Label>Column 1</Label)
    <Width>16</Width>
    <Alignment>Left</Alignment>
  </TableColumnHeader>
  <TableColumnHeader>
    <Label>Column 2</Label)
    <Width>10</Width>
    <Alignment>Centered</Alignment>
  </TableColumnHeader>
</TableHeaders>
```

## <a name="see-also"></a><span data-ttu-id="e3da2-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="e3da2-128">See Also</span></span>

[<span data-ttu-id="e3da2-129">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="e3da2-129">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="e3da2-130">Элемент TableColumnHeader (формат)</span><span class="sxs-lookup"><span data-stu-id="e3da2-130">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="e3da2-131">Элемент TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="e3da2-131">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="e3da2-132">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3da2-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
