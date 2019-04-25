---
title: Элемент TableHeaders (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9fa2b6f-b99a-42de-9779-44e9cb583f71
caps.latest.revision: 15
ms.openlocfilehash: bd44fcf4878c858afe81fb071ce72f627ac465dc
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62075415"
---
# <a name="tableheaders-element-format"></a><span data-ttu-id="4e4a1-102">Элемент TableHeaders (формат)</span><span class="sxs-lookup"><span data-stu-id="4e4a1-102">TableHeaders Element (Format)</span></span>

<span data-ttu-id="4e4a1-103">Определяет заголовков столбцов таблицы.</span><span class="sxs-lookup"><span data-stu-id="4e4a1-103">Defines the headers for the columns of a table.</span></span>

<span data-ttu-id="4e4a1-104">Элемент ViewDefinitions (формат) представления (формат) TableControl-элемент (формат) TableHeaders элемента для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="4e4a1-104">ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4e4a1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4e4a1-105">Syntax</span></span>

```xml
<TableHeaders>
  <TableColumnHeader>...</TableColumnHeader>
</TableHeaders>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="4e4a1-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4e4a1-106">Attributes and Elements</span></span>

<span data-ttu-id="4e4a1-107">В следующих разделах атрибуты, дочерние элементы и родительские элементы из `TableHeaders` элемент.</span><span class="sxs-lookup"><span data-stu-id="4e4a1-107">The following sections describe the attributes, child elements, and parent elements of the `TableHeaders` element.</span></span> <span data-ttu-id="4e4a1-108">Должен быть дочерним для каждого свойства объекта, который должен отображаться.</span><span class="sxs-lookup"><span data-stu-id="4e4a1-108">There must be a child element for each property of the object that is to be displayed.</span></span> <span data-ttu-id="4e4a1-109">Сведения о заголовке столбца отображается в том порядке, что указаны дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="4e4a1-109">The column header information is displayed in the order that the child elements are specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="4e4a1-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4e4a1-110">Attributes</span></span>

<span data-ttu-id="4e4a1-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="4e4a1-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4e4a1-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4e4a1-112">Child Elements</span></span>

|<span data-ttu-id="4e4a1-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="4e4a1-113">Element</span></span>|<span data-ttu-id="4e4a1-114">Описание</span><span class="sxs-lookup"><span data-stu-id="4e4a1-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4e4a1-115">Элемент TableColumnHeader (формат)</span><span class="sxs-lookup"><span data-stu-id="4e4a1-115">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="4e4a1-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4e4a1-116">Optional element.</span></span><br /><br /> <span data-ttu-id="4e4a1-117">Определяет метку, ширину и выравнивания данных для столбца таблицы представления.</span><span class="sxs-lookup"><span data-stu-id="4e4a1-117">Defines the label, the width, and the alignment of the data for a column of a table view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4e4a1-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4e4a1-118">Parent Elements</span></span>

|<span data-ttu-id="4e4a1-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="4e4a1-119">Element</span></span>|<span data-ttu-id="4e4a1-120">Описание</span><span class="sxs-lookup"><span data-stu-id="4e4a1-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4e4a1-121">TableControl-элемент (формат)</span><span class="sxs-lookup"><span data-stu-id="4e4a1-121">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="4e4a1-122">Определяет формат таблицы для представления.</span><span class="sxs-lookup"><span data-stu-id="4e4a1-122">Defines a table format for a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4e4a1-123">Замечания</span><span class="sxs-lookup"><span data-stu-id="4e4a1-123">Remarks</span></span>

<span data-ttu-id="4e4a1-124">Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="4e4a1-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="4e4a1-125">Пример</span><span class="sxs-lookup"><span data-stu-id="4e4a1-125">Example</span></span>

<span data-ttu-id="4e4a1-126">В этом примере показано `TableHeaders` элемент, который определяет два заголовка столбцов.</span><span class="sxs-lookup"><span data-stu-id="4e4a1-126">This example shows a `TableHeaders` element that defines two column headers.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="4e4a1-127">См. также</span><span class="sxs-lookup"><span data-stu-id="4e4a1-127">See Also</span></span>

[<span data-ttu-id="4e4a1-128">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="4e4a1-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="4e4a1-129">Элемент TableColumnHeader (формат)</span><span class="sxs-lookup"><span data-stu-id="4e4a1-129">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="4e4a1-130">TableControl-элемент (формат)</span><span class="sxs-lookup"><span data-stu-id="4e4a1-130">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="4e4a1-131">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e4a1-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
