---
title: Элемент Label для Таблеколумнхеадер для Таблеконтрол (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: b7b1d6825d3bca0e36b230415d19c2ac48377a46
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785750"
---
# <a name="label-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="c535f-102">Элемент Label для элемента TableColumnHeader для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="c535f-102">Label Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="c535f-103">Определяет метку, отображаемую в верхней части столбца.</span><span class="sxs-lookup"><span data-stu-id="c535f-103">Defines the label that is displayed at the top of a column.</span></span> <span data-ttu-id="c535f-104">Этот элемент используется при определении табличного представления.</span><span class="sxs-lookup"><span data-stu-id="c535f-104">This element is used when defining a table view.</span></span>

<span data-ttu-id="c535f-105">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент Таблеконтрол (Format) элемент Таблехеадерс для Таблеконтрол (Format) Таблеколумнхеадер для Таблехеадерс для TableControl (Format) элемент Label для TableColumnHeader в TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="c535f-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element for TableHeaders for TableControl (Format) Label Element  for TableColumnHeader for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c535f-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c535f-106">Syntax</span></span>

```xml
<Label>DisplayedLabel</Label>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="c535f-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c535f-107">Attributes and Elements</span></span>

<span data-ttu-id="c535f-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Label` элемента.</span><span class="sxs-lookup"><span data-stu-id="c535f-108">The following sections describe the attributes, child elements, and the parent element of the `Label` element.</span></span> <span data-ttu-id="c535f-109">Для каждого столбца допускается только одна метка.</span><span class="sxs-lookup"><span data-stu-id="c535f-109">Only one label is allowed for each column.</span></span>

### <a name="attributes"></a><span data-ttu-id="c535f-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c535f-110">Attributes</span></span>

<span data-ttu-id="c535f-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c535f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c535f-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c535f-112">Child Elements</span></span>

<span data-ttu-id="c535f-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c535f-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c535f-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c535f-114">Parent Elements</span></span>

|<span data-ttu-id="c535f-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="c535f-115">Element</span></span>|<span data-ttu-id="c535f-116">Описание</span><span class="sxs-lookup"><span data-stu-id="c535f-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c535f-117">Элемент Таблеколумнхеадер для Таблехеадерс для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="c535f-117">TableColumnHeader Element for TableHeaders for TableControl  (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="c535f-118">Определяет метку, ширину и выравнивание данных для столбца таблицы.</span><span class="sxs-lookup"><span data-stu-id="c535f-118">Defines a label, the width, and the alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c535f-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="c535f-119">Text Value</span></span>

<span data-ttu-id="c535f-120">Укажите текст, отображаемый в верхней части столбца таблицы.</span><span class="sxs-lookup"><span data-stu-id="c535f-120">Specify the text that is displayed at the top of the column of the table.</span></span> <span data-ttu-id="c535f-121">Для метки столбца нет ограниченных символов.</span><span class="sxs-lookup"><span data-stu-id="c535f-121">There are no restricted characters for the column label.</span></span>

## <a name="remarks"></a><span data-ttu-id="c535f-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="c535f-122">Remarks</span></span>

<span data-ttu-id="c535f-123">Если метка не указана, то используется имя свойства, значение которого отображается в строках.</span><span class="sxs-lookup"><span data-stu-id="c535f-123">If no label is specified, the name of the property whose value is displayed in the rows is used.</span></span>

<span data-ttu-id="c535f-124">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="c535f-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="c535f-125">Пример</span><span class="sxs-lookup"><span data-stu-id="c535f-125">Example</span></span>

<span data-ttu-id="c535f-126">В этом примере показан `TableColumnHeader` элемент, метка которого равна «Column 1».</span><span class="sxs-lookup"><span data-stu-id="c535f-126">This example shows a `TableColumnHeader` element whose label is "Column 1".</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="c535f-127">См. также</span><span class="sxs-lookup"><span data-stu-id="c535f-127">See Also</span></span>

[<span data-ttu-id="c535f-128">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="c535f-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="c535f-129">Элемент TableColumnHeader (формат)</span><span class="sxs-lookup"><span data-stu-id="c535f-129">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="c535f-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="c535f-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
