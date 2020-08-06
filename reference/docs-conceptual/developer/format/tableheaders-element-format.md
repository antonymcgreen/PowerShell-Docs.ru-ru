---
title: Элемент Таблехеадерс (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: b3176cbe1316d5b30cb61831d9915a80389709a5
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787433"
---
# <a name="tableheaders-element-format"></a><span data-ttu-id="5ad09-102">Элемент TableHeaders (формат)</span><span class="sxs-lookup"><span data-stu-id="5ad09-102">TableHeaders Element (Format)</span></span>

<span data-ttu-id="5ad09-103">Определяет заголовки для столбцов таблицы.</span><span class="sxs-lookup"><span data-stu-id="5ad09-103">Defines the headers for the columns of a table.</span></span>

<span data-ttu-id="5ad09-104">Элемент Виевдефинитионс (Format) представления (Format) Таблеконтрол элемент (Format) Таблехеадерс для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="5ad09-104">ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5ad09-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5ad09-105">Syntax</span></span>

```xml
<TableHeaders>
  <TableColumnHeader>...</TableColumnHeader>
</TableHeaders>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="5ad09-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5ad09-106">Attributes and Elements</span></span>

<span data-ttu-id="5ad09-107">В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы `TableHeaders` элемента.</span><span class="sxs-lookup"><span data-stu-id="5ad09-107">The following sections describe the attributes, child elements, and parent elements of the `TableHeaders` element.</span></span> <span data-ttu-id="5ad09-108">Должен существовать дочерний элемент для каждого свойства объекта, который должен быть отображен.</span><span class="sxs-lookup"><span data-stu-id="5ad09-108">There must be a child element for each property of the object that is to be displayed.</span></span> <span data-ttu-id="5ad09-109">Сведения о заголовке столбца отображаются в том порядке, в котором указаны дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="5ad09-109">The column header information is displayed in the order that the child elements are specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="5ad09-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5ad09-110">Attributes</span></span>

<span data-ttu-id="5ad09-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5ad09-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5ad09-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5ad09-112">Child Elements</span></span>

|<span data-ttu-id="5ad09-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="5ad09-113">Element</span></span>|<span data-ttu-id="5ad09-114">Описание</span><span class="sxs-lookup"><span data-stu-id="5ad09-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5ad09-115">Элемент TableColumnHeader (формат)</span><span class="sxs-lookup"><span data-stu-id="5ad09-115">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="5ad09-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="5ad09-116">Optional element.</span></span><br /><br /> <span data-ttu-id="5ad09-117">Определяет метку, ширину и выравнивание данных для столбца табличного представления.</span><span class="sxs-lookup"><span data-stu-id="5ad09-117">Defines the label, the width, and the alignment of the data for a column of a table view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5ad09-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5ad09-118">Parent Elements</span></span>

|<span data-ttu-id="5ad09-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="5ad09-119">Element</span></span>|<span data-ttu-id="5ad09-120">Описание</span><span class="sxs-lookup"><span data-stu-id="5ad09-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5ad09-121">Элемент TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="5ad09-121">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="5ad09-122">Определяет формат таблицы для представления.</span><span class="sxs-lookup"><span data-stu-id="5ad09-122">Defines a table format for a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5ad09-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="5ad09-123">Remarks</span></span>

<span data-ttu-id="5ad09-124">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="5ad09-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="5ad09-125">Пример</span><span class="sxs-lookup"><span data-stu-id="5ad09-125">Example</span></span>

<span data-ttu-id="5ad09-126">В этом примере показан `TableHeaders` элемент, определяющий два заголовка столбцов.</span><span class="sxs-lookup"><span data-stu-id="5ad09-126">This example shows a `TableHeaders` element that defines two column headers.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="5ad09-127">См. также</span><span class="sxs-lookup"><span data-stu-id="5ad09-127">See Also</span></span>

[<span data-ttu-id="5ad09-128">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="5ad09-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="5ad09-129">Элемент TableColumnHeader (формат)</span><span class="sxs-lookup"><span data-stu-id="5ad09-129">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="5ad09-130">Элемент TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="5ad09-130">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="5ad09-131">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ad09-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
