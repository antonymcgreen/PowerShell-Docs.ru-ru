---
title: Элемент Таблехеадерс (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9fa2b6f-b99a-42de-9779-44e9cb583f71
caps.latest.revision: 15
ms.openlocfilehash: bd44fcf4878c858afe81fb071ce72f627ac465dc
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361823"
---
# <a name="tableheaders-element-format"></a><span data-ttu-id="b177c-102">Элемент TableHeaders (формат)</span><span class="sxs-lookup"><span data-stu-id="b177c-102">TableHeaders Element (Format)</span></span>

<span data-ttu-id="b177c-103">Определяет заголовки для столбцов таблицы.</span><span class="sxs-lookup"><span data-stu-id="b177c-103">Defines the headers for the columns of a table.</span></span>

<span data-ttu-id="b177c-104">Элемент Виевдефинитионс (Format) представления (Format) Таблеконтрол элемент (Format) Таблехеадерс для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="b177c-104">ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b177c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b177c-105">Syntax</span></span>

```xml
<TableHeaders>
  <TableColumnHeader>...</TableColumnHeader>
</TableHeaders>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="b177c-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b177c-106">Attributes and Elements</span></span>

<span data-ttu-id="b177c-107">В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы элемента `TableHeaders`.</span><span class="sxs-lookup"><span data-stu-id="b177c-107">The following sections describe the attributes, child elements, and parent elements of the `TableHeaders` element.</span></span> <span data-ttu-id="b177c-108">Должен существовать дочерний элемент для каждого свойства объекта, который должен быть отображен.</span><span class="sxs-lookup"><span data-stu-id="b177c-108">There must be a child element for each property of the object that is to be displayed.</span></span> <span data-ttu-id="b177c-109">Сведения о заголовке столбца отображаются в том порядке, в котором указаны дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="b177c-109">The column header information is displayed in the order that the child elements are specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="b177c-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b177c-110">Attributes</span></span>

<span data-ttu-id="b177c-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="b177c-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b177c-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b177c-112">Child Elements</span></span>

|<span data-ttu-id="b177c-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="b177c-113">Element</span></span>|<span data-ttu-id="b177c-114">Описание</span><span class="sxs-lookup"><span data-stu-id="b177c-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b177c-115">Элемент Таблеколумнхеадер (Format)</span><span class="sxs-lookup"><span data-stu-id="b177c-115">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="b177c-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="b177c-116">Optional element.</span></span><br /><br /> <span data-ttu-id="b177c-117">Определяет метку, ширину и выравнивание данных для столбца табличного представления.</span><span class="sxs-lookup"><span data-stu-id="b177c-117">Defines the label, the width, and the alignment of the data for a column of a table view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b177c-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b177c-118">Parent Elements</span></span>

|<span data-ttu-id="b177c-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="b177c-119">Element</span></span>|<span data-ttu-id="b177c-120">Описание</span><span class="sxs-lookup"><span data-stu-id="b177c-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b177c-121">Элемент Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="b177c-121">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="b177c-122">Определяет формат таблицы для представления.</span><span class="sxs-lookup"><span data-stu-id="b177c-122">Defines a table format for a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b177c-123">Замечания</span><span class="sxs-lookup"><span data-stu-id="b177c-123">Remarks</span></span>

<span data-ttu-id="b177c-124">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="b177c-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="b177c-125">Пример</span><span class="sxs-lookup"><span data-stu-id="b177c-125">Example</span></span>

<span data-ttu-id="b177c-126">В этом примере показан элемент `TableHeaders`, определяющий два заголовка столбцов.</span><span class="sxs-lookup"><span data-stu-id="b177c-126">This example shows a `TableHeaders` element that defines two column headers.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b177c-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="b177c-127">See Also</span></span>

[<span data-ttu-id="b177c-128">Создание табличного представления</span><span class="sxs-lookup"><span data-stu-id="b177c-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="b177c-129">Элемент Таблеколумнхеадер (Format)</span><span class="sxs-lookup"><span data-stu-id="b177c-129">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="b177c-130">Элемент Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="b177c-130">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="b177c-131">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="b177c-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
