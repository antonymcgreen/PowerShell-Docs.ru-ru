---
title: Элемент Таблеколумнхеадер (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49ff3062-6396-4aa8-919b-3fd3ac60899a
caps.latest.revision: 19
ms.openlocfilehash: d3ad7fa563def17d43ce4dc64d155b65b650521f
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361853"
---
# <a name="tablecolumnheader-element-format"></a><span data-ttu-id="d342d-102">Элемент TableColumnHeader (формат)</span><span class="sxs-lookup"><span data-stu-id="d342d-102">TableColumnHeader Element (Format)</span></span>

<span data-ttu-id="d342d-103">Определяет метку, ширину столбца, а также выравнивание метки для столбца таблицы.</span><span class="sxs-lookup"><span data-stu-id="d342d-103">Defines the label, the width of the column, and the alignment of the label for a column of the table.</span></span>

<span data-ttu-id="d342d-104">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Таблеконтрол элемент (Format) Таблехеадерс для Таблеконтрол (Format) Таблеколумнхеадер для Таблехеадерс в TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="d342d-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element for TableHeaders for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d342d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d342d-105">Syntax</span></span>

```xml
<TableColumnHeader>
  <Label>DisplayedLabel</Label>
  <Width>NumberOfCharacters</Width>
  <Alignment>Left, Right, or Centered</Alignment>
</TableColumnHeader>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d342d-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d342d-106">Attributes and Elements</span></span>

<span data-ttu-id="d342d-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `TableColumnHeader`.</span><span class="sxs-lookup"><span data-stu-id="d342d-107">The following sections describe attributes, child elements, and the parent element of the `TableColumnHeader` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d342d-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d342d-108">Attributes</span></span>

<span data-ttu-id="d342d-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="d342d-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d342d-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d342d-110">Child Elements</span></span>

|<span data-ttu-id="d342d-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="d342d-111">Element</span></span>|<span data-ttu-id="d342d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="d342d-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d342d-113">Элемент Label для Таблеколумнхеадер для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="d342d-113">Label Element For TableColumnHeader for TableControl (Format)</span></span>](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)|<span data-ttu-id="d342d-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d342d-114">Optional element.</span></span><br /><br /> <span data-ttu-id="d342d-115">Определяет метку, отображаемую в верхней части столбца.</span><span class="sxs-lookup"><span data-stu-id="d342d-115">Defines the label that is displayed at the top of the column.</span></span> <span data-ttu-id="d342d-116">Если метка не указана, то используется имя свойства, значение которого отображается в строках.</span><span class="sxs-lookup"><span data-stu-id="d342d-116">If no label is specified, the name of the property whose value is displayed in the rows is used.</span></span>|
|[<span data-ttu-id="d342d-117">Элемент Width для Таблеколумнхеадер для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="d342d-117">Width Element for TableColumnHeader for TableControl (Format)</span></span>](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)|<span data-ttu-id="d342d-118">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d342d-118">Required element.</span></span><br /><br /> <span data-ttu-id="d342d-119">Задает ширину (в символах) столбца.</span><span class="sxs-lookup"><span data-stu-id="d342d-119">Specifies the width (in characters) of the column.</span></span>|
|[<span data-ttu-id="d342d-120">Элемент Alignment для Таблеколумнхеадер для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="d342d-120">Alignment Element for TableColumnHeader for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)|<span data-ttu-id="d342d-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d342d-121">Optional element.</span></span><br /><br /> <span data-ttu-id="d342d-122">Задает способ отображения метки столбца.</span><span class="sxs-lookup"><span data-stu-id="d342d-122">Specifies how the label of the column is displayed.</span></span> <span data-ttu-id="d342d-123">Если выравнивание не задано, то метка выравнивается слева.</span><span class="sxs-lookup"><span data-stu-id="d342d-123">If no alignment is specified, the label is aligned on the left.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d342d-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d342d-124">Parent Elements</span></span>

|<span data-ttu-id="d342d-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="d342d-125">Element</span></span>|<span data-ttu-id="d342d-126">Описание</span><span class="sxs-lookup"><span data-stu-id="d342d-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d342d-127">Элемент Таблехеадерс (Format)</span><span class="sxs-lookup"><span data-stu-id="d342d-127">TableHeaders Element (Format)</span></span>](./tableheaders-element-format.md)|<span data-ttu-id="d342d-128">Определяет столбцы табличного представления.</span><span class="sxs-lookup"><span data-stu-id="d342d-128">Defines the columns of a table view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d342d-129">Замечания</span><span class="sxs-lookup"><span data-stu-id="d342d-129">Remarks</span></span>

<span data-ttu-id="d342d-130">Укажите заголовок для каждого столбца таблицы.</span><span class="sxs-lookup"><span data-stu-id="d342d-130">Specify a header for each column of the table.</span></span> <span data-ttu-id="d342d-131">Столбцы отображаются в том порядке, в котором определены элементы `TableColumnHeader`.</span><span class="sxs-lookup"><span data-stu-id="d342d-131">The columns are displayed in the order in which the `TableColumnHeader` elements are defined.</span></span>

<span data-ttu-id="d342d-132">Таблица должна иметь то же количество `TableColumnHeader` элементов, что и элементы `TableRowEntry`.</span><span class="sxs-lookup"><span data-stu-id="d342d-132">A table must have the same number of `TableColumnHeader` elements as `TableRowEntry` elements.</span></span> <span data-ttu-id="d342d-133">Заголовок столбца определяет, как будет отображаться текст в верхней части таблицы.</span><span class="sxs-lookup"><span data-stu-id="d342d-133">The column header defines how the text at the top of the table is displayed.</span></span> <span data-ttu-id="d342d-134">Записи строки определяют, какие данные отображаются в строках таблицы.</span><span class="sxs-lookup"><span data-stu-id="d342d-134">The row entries define what data is displayed in the rows of the table.</span></span>

<span data-ttu-id="d342d-135">Дополнительные сведения о компонентах табличного представления см. в разделе [табличное представление](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="d342d-135">For more information about the components of a table view, see [Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="d342d-136">Пример</span><span class="sxs-lookup"><span data-stu-id="d342d-136">Example</span></span>

<span data-ttu-id="d342d-137">В следующем примере показаны два элемента `TableColumnHeader`.</span><span class="sxs-lookup"><span data-stu-id="d342d-137">The following example shows two `TableColumnHeader` elements.</span></span> <span data-ttu-id="d342d-138">Первый элемент определяет столбец, метка которого равна "Column 1", имеет ширину 16 символов, а метка — слева.</span><span class="sxs-lookup"><span data-stu-id="d342d-138">The first element defines a column whose label is "Column 1", has a width of 16 characters, and whose label is aligned on the left.</span></span> <span data-ttu-id="d342d-139">Второй элемент определяет столбец, метка которого равна «Column 2», имеет ширину 10 символов, а метка — по центру столбца.</span><span class="sxs-lookup"><span data-stu-id="d342d-139">The second element defines a column whose label is "Column 2", has a width of 10 characters, and whose label is centered in the column.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="d342d-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="d342d-140">See Also</span></span>

[<span data-ttu-id="d342d-141">Элемент Alignment для Таблеколумнхеадер для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="d342d-141">Alignment Element for TableColumnHeader for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)

[<span data-ttu-id="d342d-142">Создание табличного представления</span><span class="sxs-lookup"><span data-stu-id="d342d-142">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="d342d-143">Элемент Label для Таблеколумнхеадер для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="d342d-143">Label Element for TableColumnHeader for TableControl (Format)</span></span>](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)

[<span data-ttu-id="d342d-144">Элемент Таблехеадерс для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="d342d-144">TableHeaders Element for TableControl (Format)</span></span>](./tableheaders-element-format.md)

[<span data-ttu-id="d342d-145">Ширина для Таблеколумнхеадер элемента Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="d342d-145">Width for TableColumnHeader for TableControl Element (Format)</span></span>](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)

[<span data-ttu-id="d342d-146">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="d342d-146">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
