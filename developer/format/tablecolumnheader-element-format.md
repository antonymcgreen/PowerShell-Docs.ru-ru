---
title: Элемент TableColumnHeader (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49ff3062-6396-4aa8-919b-3fd3ac60899a
caps.latest.revision: 19
ms.openlocfilehash: d3ad7fa563def17d43ce4dc64d155b65b650521f
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62063815"
---
# <a name="tablecolumnheader-element-format"></a><span data-ttu-id="de90d-102">Элемент TableColumnHeader (формат)</span><span class="sxs-lookup"><span data-stu-id="de90d-102">TableColumnHeader Element (Format)</span></span>

<span data-ttu-id="de90d-103">Определяет метку, ширину столбца и выравнивание метки для столбца таблицы.</span><span class="sxs-lookup"><span data-stu-id="de90d-103">Defines the label, the width of the column, and the alignment of the label for a column of the table.</span></span>

<span data-ttu-id="de90d-104">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) TableHeaders элемента конфигурации для элемента TableColumnHeader TableControl (формат) TableHeaders для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="de90d-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element for TableHeaders for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="de90d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="de90d-105">Syntax</span></span>

```xml
<TableColumnHeader>
  <Label>DisplayedLabel</Label>
  <Width>NumberOfCharacters</Width>
  <Alignment>Left, Right, or Centered</Alignment>
</TableColumnHeader>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="de90d-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="de90d-106">Attributes and Elements</span></span>

<span data-ttu-id="de90d-107">Ниже описаны атрибуты, дочерние элементы и родительский элемент `TableColumnHeader` элемент.</span><span class="sxs-lookup"><span data-stu-id="de90d-107">The following sections describe attributes, child elements, and the parent element of the `TableColumnHeader` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="de90d-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="de90d-108">Attributes</span></span>

<span data-ttu-id="de90d-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="de90d-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="de90d-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="de90d-110">Child Elements</span></span>

|<span data-ttu-id="de90d-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="de90d-111">Element</span></span>|<span data-ttu-id="de90d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="de90d-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="de90d-113">Элемент Label для TableColumnHeader для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="de90d-113">Label Element For TableColumnHeader for TableControl (Format)</span></span>](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)|<span data-ttu-id="de90d-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="de90d-114">Optional element.</span></span><br /><br /> <span data-ttu-id="de90d-115">Определяет метку, которая отображается в верхней части столбца.</span><span class="sxs-lookup"><span data-stu-id="de90d-115">Defines the label that is displayed at the top of the column.</span></span> <span data-ttu-id="de90d-116">Если метка не указана, используется имя свойства, значение которого отображается в строках.</span><span class="sxs-lookup"><span data-stu-id="de90d-116">If no label is specified, the name of the property whose value is displayed in the rows is used.</span></span>|
|[<span data-ttu-id="de90d-117">Ширина элемента для TableColumnHeader для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="de90d-117">Width Element for TableColumnHeader for TableControl (Format)</span></span>](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)|<span data-ttu-id="de90d-118">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="de90d-118">Required element.</span></span><br /><br /> <span data-ttu-id="de90d-119">Ширина столбца (в символах).</span><span class="sxs-lookup"><span data-stu-id="de90d-119">Specifies the width (in characters) of the column.</span></span>|
|[<span data-ttu-id="de90d-120">Выравнивание элемента для TableColumnHeader для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="de90d-120">Alignment Element for TableColumnHeader for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)|<span data-ttu-id="de90d-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="de90d-121">Optional element.</span></span><br /><br /> <span data-ttu-id="de90d-122">Указывает способ отображения метки столбца.</span><span class="sxs-lookup"><span data-stu-id="de90d-122">Specifies how the label of the column is displayed.</span></span> <span data-ttu-id="de90d-123">Если выравнивание не указано, подпись выравнивается в левой части.</span><span class="sxs-lookup"><span data-stu-id="de90d-123">If no alignment is specified, the label is aligned on the left.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="de90d-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="de90d-124">Parent Elements</span></span>

|<span data-ttu-id="de90d-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="de90d-125">Element</span></span>|<span data-ttu-id="de90d-126">Описание</span><span class="sxs-lookup"><span data-stu-id="de90d-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="de90d-127">Элемент TableHeaders (формат)</span><span class="sxs-lookup"><span data-stu-id="de90d-127">TableHeaders Element (Format)</span></span>](./tableheaders-element-format.md)|<span data-ttu-id="de90d-128">Определяет столбцы в табличное представление.</span><span class="sxs-lookup"><span data-stu-id="de90d-128">Defines the columns of a table view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="de90d-129">Замечания</span><span class="sxs-lookup"><span data-stu-id="de90d-129">Remarks</span></span>

<span data-ttu-id="de90d-130">Укажите заголовок для каждого столбца таблицы.</span><span class="sxs-lookup"><span data-stu-id="de90d-130">Specify a header for each column of the table.</span></span> <span data-ttu-id="de90d-131">Столбцы отображаются в порядке, в котором `TableColumnHeader` определенные элементы.</span><span class="sxs-lookup"><span data-stu-id="de90d-131">The columns are displayed in the order in which the `TableColumnHeader` elements are defined.</span></span>

<span data-ttu-id="de90d-132">Таблица должна иметь одинаковое число `TableColumnHeader` элементы, что `TableRowEntry` элементы.</span><span class="sxs-lookup"><span data-stu-id="de90d-132">A table must have the same number of `TableColumnHeader` elements as `TableRowEntry` elements.</span></span> <span data-ttu-id="de90d-133">Заголовок столбца определяет, как отображается текст в верхней части таблицы.</span><span class="sxs-lookup"><span data-stu-id="de90d-133">The column header defines how the text at the top of the table is displayed.</span></span> <span data-ttu-id="de90d-134">Строки определяют, какие данные отображаются в строках таблицы.</span><span class="sxs-lookup"><span data-stu-id="de90d-134">The row entries define what data is displayed in the rows of the table.</span></span>

<span data-ttu-id="de90d-135">Дополнительные сведения о компонентах в табличное представление, см. в разделе [табличное представление](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="de90d-135">For more information about the components of a table view, see [Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="de90d-136">Пример</span><span class="sxs-lookup"><span data-stu-id="de90d-136">Example</span></span>

<span data-ttu-id="de90d-137">В следующем примере показаны два `TableColumnHeader` элементов.</span><span class="sxs-lookup"><span data-stu-id="de90d-137">The following example shows two `TableColumnHeader` elements.</span></span> <span data-ttu-id="de90d-138">Первый элемент определяет столбец, метка которого указано «Столбец 1», имеет ширину 16 символов и метка которого по левому краю.</span><span class="sxs-lookup"><span data-stu-id="de90d-138">The first element defines a column whose label is "Column 1", has a width of 16 characters, and whose label is aligned on the left.</span></span> <span data-ttu-id="de90d-139">Второй элемент определяет столбец, метка которого указано «Столбец 2», шириной 10 символов и которого метка размещается по центру в столбце.</span><span class="sxs-lookup"><span data-stu-id="de90d-139">The second element defines a column whose label is "Column 2", has a width of 10 characters, and whose label is centered in the column.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="de90d-140">См. также</span><span class="sxs-lookup"><span data-stu-id="de90d-140">See Also</span></span>

[<span data-ttu-id="de90d-141">Выравнивание элемента для TableColumnHeader для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="de90d-141">Alignment Element for TableColumnHeader for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)

[<span data-ttu-id="de90d-142">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="de90d-142">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="de90d-143">Элемент Label для TableColumnHeader для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="de90d-143">Label Element for TableColumnHeader for TableControl (Format)</span></span>](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)

[<span data-ttu-id="de90d-144">Элемент TableHeaders для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="de90d-144">TableHeaders Element for TableControl (Format)</span></span>](./tableheaders-element-format.md)

[<span data-ttu-id="de90d-145">Ширина для TableColumnHeader для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="de90d-145">Width for TableColumnHeader for TableControl Element (Format)</span></span>](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)

[<span data-ttu-id="de90d-146">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="de90d-146">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
