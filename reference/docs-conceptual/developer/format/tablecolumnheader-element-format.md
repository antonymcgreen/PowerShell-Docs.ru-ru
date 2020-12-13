---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент TableColumnHeader (формат)
description: Элемент TableColumnHeader (формат)
ms.openlocfilehash: 30368512875b7c5c4cf3c686f3d09540dea1bd26
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651533"
---
# <a name="tablecolumnheader-element-format"></a><span data-ttu-id="f11f7-103">Элемент TableColumnHeader (формат)</span><span class="sxs-lookup"><span data-stu-id="f11f7-103">TableColumnHeader Element (Format)</span></span>

<span data-ttu-id="f11f7-104">Определяет метку, ширину столбца, а также выравнивание метки для столбца таблицы.</span><span class="sxs-lookup"><span data-stu-id="f11f7-104">Defines the label, the width of the column, and the alignment of the label for a column of the table.</span></span>

<span data-ttu-id="f11f7-105">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Таблеконтрол элемент (Format) Таблехеадерс для Таблеконтрол (Format) Таблеколумнхеадер для Таблехеадерс в TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="f11f7-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element for TableHeaders for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f11f7-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f11f7-106">Syntax</span></span>

```xml
<TableColumnHeader>
  <Label>DisplayedLabel</Label>
  <Width>NumberOfCharacters</Width>
  <Alignment>Left, Right, or Centered</Alignment>
</TableColumnHeader>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f11f7-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f11f7-107">Attributes and Elements</span></span>

<span data-ttu-id="f11f7-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TableColumnHeader` элемента.</span><span class="sxs-lookup"><span data-stu-id="f11f7-108">The following sections describe attributes, child elements, and the parent element of the `TableColumnHeader` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f11f7-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f11f7-109">Attributes</span></span>

<span data-ttu-id="f11f7-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f11f7-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f11f7-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f11f7-111">Child Elements</span></span>

|<span data-ttu-id="f11f7-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="f11f7-112">Element</span></span>|<span data-ttu-id="f11f7-113">Описание</span><span class="sxs-lookup"><span data-stu-id="f11f7-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f11f7-114">Элемент Label для Таблеколумнхеадер для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="f11f7-114">Label Element For TableColumnHeader for TableControl (Format)</span></span>](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)|<span data-ttu-id="f11f7-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f11f7-115">Optional element.</span></span><br /><br /> <span data-ttu-id="f11f7-116">Определяет метку, отображаемую в верхней части столбца.</span><span class="sxs-lookup"><span data-stu-id="f11f7-116">Defines the label that is displayed at the top of the column.</span></span> <span data-ttu-id="f11f7-117">Если метка не указана, то используется имя свойства, значение которого отображается в строках.</span><span class="sxs-lookup"><span data-stu-id="f11f7-117">If no label is specified, the name of the property whose value is displayed in the rows is used.</span></span>|
|[<span data-ttu-id="f11f7-118">Элемент Width для элемента TableColumnHeader для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="f11f7-118">Width Element for TableColumnHeader for TableControl (Format)</span></span>](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)|<span data-ttu-id="f11f7-119">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f11f7-119">Required element.</span></span><br /><br /> <span data-ttu-id="f11f7-120">Задает ширину (в символах) столбца.</span><span class="sxs-lookup"><span data-stu-id="f11f7-120">Specifies the width (in characters) of the column.</span></span>|
|[<span data-ttu-id="f11f7-121">Элемент Alignment для TableColumnHeader для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="f11f7-121">Alignment Element for TableColumnHeader for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)|<span data-ttu-id="f11f7-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f11f7-122">Optional element.</span></span><br /><br /> <span data-ttu-id="f11f7-123">Задает способ отображения метки столбца.</span><span class="sxs-lookup"><span data-stu-id="f11f7-123">Specifies how the label of the column is displayed.</span></span> <span data-ttu-id="f11f7-124">Если выравнивание не задано, то метка выравнивается слева.</span><span class="sxs-lookup"><span data-stu-id="f11f7-124">If no alignment is specified, the label is aligned on the left.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f11f7-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f11f7-125">Parent Elements</span></span>

|<span data-ttu-id="f11f7-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="f11f7-126">Element</span></span>|<span data-ttu-id="f11f7-127">Описание</span><span class="sxs-lookup"><span data-stu-id="f11f7-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f11f7-128">Элемент TableHeaders (формат)</span><span class="sxs-lookup"><span data-stu-id="f11f7-128">TableHeaders Element (Format)</span></span>](./tableheaders-element-format.md)|<span data-ttu-id="f11f7-129">Определяет столбцы табличного представления.</span><span class="sxs-lookup"><span data-stu-id="f11f7-129">Defines the columns of a table view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f11f7-130">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f11f7-130">Remarks</span></span>

<span data-ttu-id="f11f7-131">Укажите заголовок для каждого столбца таблицы.</span><span class="sxs-lookup"><span data-stu-id="f11f7-131">Specify a header for each column of the table.</span></span> <span data-ttu-id="f11f7-132">Столбцы отображаются в том порядке, в котором `TableColumnHeader` определены элементы.</span><span class="sxs-lookup"><span data-stu-id="f11f7-132">The columns are displayed in the order in which the `TableColumnHeader` elements are defined.</span></span>

<span data-ttu-id="f11f7-133">Таблица должна иметь то же количество элементов, `TableColumnHeader` что и `TableRowEntry` элементы.</span><span class="sxs-lookup"><span data-stu-id="f11f7-133">A table must have the same number of `TableColumnHeader` elements as `TableRowEntry` elements.</span></span> <span data-ttu-id="f11f7-134">Заголовок столбца определяет, как будет отображаться текст в верхней части таблицы.</span><span class="sxs-lookup"><span data-stu-id="f11f7-134">The column header defines how the text at the top of the table is displayed.</span></span> <span data-ttu-id="f11f7-135">Записи строки определяют, какие данные отображаются в строках таблицы.</span><span class="sxs-lookup"><span data-stu-id="f11f7-135">The row entries define what data is displayed in the rows of the table.</span></span>

<span data-ttu-id="f11f7-136">Дополнительные сведения о компонентах табличного представления см. в разделе [табличное представление](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="f11f7-136">For more information about the components of a table view, see [Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="f11f7-137">Пример</span><span class="sxs-lookup"><span data-stu-id="f11f7-137">Example</span></span>

<span data-ttu-id="f11f7-138">В следующем примере показаны два `TableColumnHeader` элемента.</span><span class="sxs-lookup"><span data-stu-id="f11f7-138">The following example shows two `TableColumnHeader` elements.</span></span> <span data-ttu-id="f11f7-139">Первый элемент определяет столбец, метка которого равна "Column 1", имеет ширину 16 символов, а метка — слева.</span><span class="sxs-lookup"><span data-stu-id="f11f7-139">The first element defines a column whose label is "Column 1", has a width of 16 characters, and whose label is aligned on the left.</span></span> <span data-ttu-id="f11f7-140">Второй элемент определяет столбец, метка которого равна «Column 2», имеет ширину 10 символов, а метка — по центру столбца.</span><span class="sxs-lookup"><span data-stu-id="f11f7-140">The second element defines a column whose label is "Column 2", has a width of 10 characters, and whose label is centered in the column.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f11f7-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="f11f7-141">See Also</span></span>

[<span data-ttu-id="f11f7-142">Элемент Alignment для TableColumnHeader для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="f11f7-142">Alignment Element for TableColumnHeader for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)

[<span data-ttu-id="f11f7-143">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="f11f7-143">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="f11f7-144">Элемент Label для элемента TableColumnHeader для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="f11f7-144">Label Element for TableColumnHeader for TableControl (Format)</span></span>](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)

[<span data-ttu-id="f11f7-145">Элемент Таблехеадерс для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="f11f7-145">TableHeaders Element for TableControl (Format)</span></span>](./tableheaders-element-format.md)

[<span data-ttu-id="f11f7-146">Ширина для Таблеколумнхеадер элемента Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="f11f7-146">Width for TableColumnHeader for TableControl Element (Format)</span></span>](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)

[<span data-ttu-id="f11f7-147">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="f11f7-147">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
