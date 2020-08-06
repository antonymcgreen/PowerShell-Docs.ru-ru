---
title: Элемент Таблеколумнхеадер (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 6296aea5c567663b1c3c0a2cf0a57b21aa5394de
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785189"
---
# <a name="tablecolumnheader-element-format"></a><span data-ttu-id="4be00-102">Элемент TableColumnHeader (формат)</span><span class="sxs-lookup"><span data-stu-id="4be00-102">TableColumnHeader Element (Format)</span></span>

<span data-ttu-id="4be00-103">Определяет метку, ширину столбца, а также выравнивание метки для столбца таблицы.</span><span class="sxs-lookup"><span data-stu-id="4be00-103">Defines the label, the width of the column, and the alignment of the label for a column of the table.</span></span>

<span data-ttu-id="4be00-104">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Таблеконтрол элемент (Format) Таблехеадерс для Таблеконтрол (Format) Таблеколумнхеадер для Таблехеадерс в TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="4be00-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element for TableHeaders for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4be00-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4be00-105">Syntax</span></span>

```xml
<TableColumnHeader>
  <Label>DisplayedLabel</Label>
  <Width>NumberOfCharacters</Width>
  <Alignment>Left, Right, or Centered</Alignment>
</TableColumnHeader>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4be00-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4be00-106">Attributes and Elements</span></span>

<span data-ttu-id="4be00-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TableColumnHeader` элемента.</span><span class="sxs-lookup"><span data-stu-id="4be00-107">The following sections describe attributes, child elements, and the parent element of the `TableColumnHeader` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4be00-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4be00-108">Attributes</span></span>

<span data-ttu-id="4be00-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4be00-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4be00-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4be00-110">Child Elements</span></span>

|<span data-ttu-id="4be00-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="4be00-111">Element</span></span>|<span data-ttu-id="4be00-112">Описание</span><span class="sxs-lookup"><span data-stu-id="4be00-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4be00-113">Элемент Label для Таблеколумнхеадер для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="4be00-113">Label Element For TableColumnHeader for TableControl (Format)</span></span>](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)|<span data-ttu-id="4be00-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4be00-114">Optional element.</span></span><br /><br /> <span data-ttu-id="4be00-115">Определяет метку, отображаемую в верхней части столбца.</span><span class="sxs-lookup"><span data-stu-id="4be00-115">Defines the label that is displayed at the top of the column.</span></span> <span data-ttu-id="4be00-116">Если метка не указана, то используется имя свойства, значение которого отображается в строках.</span><span class="sxs-lookup"><span data-stu-id="4be00-116">If no label is specified, the name of the property whose value is displayed in the rows is used.</span></span>|
|[<span data-ttu-id="4be00-117">Элемент Width для элемента TableColumnHeader для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="4be00-117">Width Element for TableColumnHeader for TableControl (Format)</span></span>](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)|<span data-ttu-id="4be00-118">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4be00-118">Required element.</span></span><br /><br /> <span data-ttu-id="4be00-119">Задает ширину (в символах) столбца.</span><span class="sxs-lookup"><span data-stu-id="4be00-119">Specifies the width (in characters) of the column.</span></span>|
|[<span data-ttu-id="4be00-120">Элемент Alignment для TableColumnHeader для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="4be00-120">Alignment Element for TableColumnHeader for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)|<span data-ttu-id="4be00-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4be00-121">Optional element.</span></span><br /><br /> <span data-ttu-id="4be00-122">Задает способ отображения метки столбца.</span><span class="sxs-lookup"><span data-stu-id="4be00-122">Specifies how the label of the column is displayed.</span></span> <span data-ttu-id="4be00-123">Если выравнивание не задано, то метка выравнивается слева.</span><span class="sxs-lookup"><span data-stu-id="4be00-123">If no alignment is specified, the label is aligned on the left.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4be00-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4be00-124">Parent Elements</span></span>

|<span data-ttu-id="4be00-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="4be00-125">Element</span></span>|<span data-ttu-id="4be00-126">Описание</span><span class="sxs-lookup"><span data-stu-id="4be00-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4be00-127">Элемент TableHeaders (формат)</span><span class="sxs-lookup"><span data-stu-id="4be00-127">TableHeaders Element (Format)</span></span>](./tableheaders-element-format.md)|<span data-ttu-id="4be00-128">Определяет столбцы табличного представления.</span><span class="sxs-lookup"><span data-stu-id="4be00-128">Defines the columns of a table view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4be00-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="4be00-129">Remarks</span></span>

<span data-ttu-id="4be00-130">Укажите заголовок для каждого столбца таблицы.</span><span class="sxs-lookup"><span data-stu-id="4be00-130">Specify a header for each column of the table.</span></span> <span data-ttu-id="4be00-131">Столбцы отображаются в том порядке, в котором `TableColumnHeader` определены элементы.</span><span class="sxs-lookup"><span data-stu-id="4be00-131">The columns are displayed in the order in which the `TableColumnHeader` elements are defined.</span></span>

<span data-ttu-id="4be00-132">Таблица должна иметь то же количество элементов, `TableColumnHeader` что и `TableRowEntry` элементы.</span><span class="sxs-lookup"><span data-stu-id="4be00-132">A table must have the same number of `TableColumnHeader` elements as `TableRowEntry` elements.</span></span> <span data-ttu-id="4be00-133">Заголовок столбца определяет, как будет отображаться текст в верхней части таблицы.</span><span class="sxs-lookup"><span data-stu-id="4be00-133">The column header defines how the text at the top of the table is displayed.</span></span> <span data-ttu-id="4be00-134">Записи строки определяют, какие данные отображаются в строках таблицы.</span><span class="sxs-lookup"><span data-stu-id="4be00-134">The row entries define what data is displayed in the rows of the table.</span></span>

<span data-ttu-id="4be00-135">Дополнительные сведения о компонентах табличного представления см. в разделе [табличное представление](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="4be00-135">For more information about the components of a table view, see [Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="4be00-136">Пример</span><span class="sxs-lookup"><span data-stu-id="4be00-136">Example</span></span>

<span data-ttu-id="4be00-137">В следующем примере показаны два `TableColumnHeader` элемента.</span><span class="sxs-lookup"><span data-stu-id="4be00-137">The following example shows two `TableColumnHeader` elements.</span></span> <span data-ttu-id="4be00-138">Первый элемент определяет столбец, метка которого равна "Column 1", имеет ширину 16 символов, а метка — слева.</span><span class="sxs-lookup"><span data-stu-id="4be00-138">The first element defines a column whose label is "Column 1", has a width of 16 characters, and whose label is aligned on the left.</span></span> <span data-ttu-id="4be00-139">Второй элемент определяет столбец, метка которого равна «Column 2», имеет ширину 10 символов, а метка — по центру столбца.</span><span class="sxs-lookup"><span data-stu-id="4be00-139">The second element defines a column whose label is "Column 2", has a width of 10 characters, and whose label is centered in the column.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="4be00-140">См. также</span><span class="sxs-lookup"><span data-stu-id="4be00-140">See Also</span></span>

[<span data-ttu-id="4be00-141">Элемент Alignment для TableColumnHeader для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="4be00-141">Alignment Element for TableColumnHeader for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)

[<span data-ttu-id="4be00-142">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="4be00-142">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="4be00-143">Элемент Label для элемента TableColumnHeader для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="4be00-143">Label Element for TableColumnHeader for TableControl (Format)</span></span>](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)

[<span data-ttu-id="4be00-144">Элемент Таблехеадерс для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="4be00-144">TableHeaders Element for TableControl (Format)</span></span>](./tableheaders-element-format.md)

[<span data-ttu-id="4be00-145">Ширина для Таблеколумнхеадер элемента Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="4be00-145">Width for TableColumnHeader for TableControl Element (Format)</span></span>](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)

[<span data-ttu-id="4be00-146">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="4be00-146">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
