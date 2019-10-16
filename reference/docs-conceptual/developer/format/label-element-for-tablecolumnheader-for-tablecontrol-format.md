---
title: Элемент Label для Таблеколумнхеадер для Таблеконтрол (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7196f039-2f6a-41fd-b252-5b1623ebb9f9
caps.latest.revision: 11
ms.openlocfilehash: 09183a538c179f19347c3f1ed45b4ad38c2ca451
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365173"
---
# <a name="label-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="d0bc7-102">Элемент Label для элемента TableColumnHeader для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="d0bc7-102">Label Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="d0bc7-103">Определяет метку, отображаемую в верхней части столбца.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-103">Defines the label that is displayed at the top of a column.</span></span> <span data-ttu-id="d0bc7-104">Этот элемент используется при определении табличного представления.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-104">This element is used when defining a table view.</span></span>

<span data-ttu-id="d0bc7-105">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Таблеконтрол элемент (Format) Таблехеадерс для Таблеконтрол (Format) Таблеколумнхеадер элемента для Таблехеадерс в TableControl (Format) элемент Label для Таблеколумнхеадер для Таблеконтрол (формат)</span><span class="sxs-lookup"><span data-stu-id="d0bc7-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element for TableHeaders for TableControl (Format) Label Element  for TableColumnHeader for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d0bc7-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d0bc7-106">Syntax</span></span>

```xml
<Label>DisplayedLabel</Label>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="d0bc7-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d0bc7-107">Attributes and Elements</span></span>

<span data-ttu-id="d0bc7-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `Label`.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-108">The following sections describe the attributes, child elements, and the parent element of the `Label` element.</span></span> <span data-ttu-id="d0bc7-109">Для каждого столбца допускается только одна метка.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-109">Only one label is allowed for each column.</span></span>

### <a name="attributes"></a><span data-ttu-id="d0bc7-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d0bc7-110">Attributes</span></span>

<span data-ttu-id="d0bc7-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d0bc7-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d0bc7-112">Child Elements</span></span>

<span data-ttu-id="d0bc7-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d0bc7-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d0bc7-114">Parent Elements</span></span>

|<span data-ttu-id="d0bc7-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="d0bc7-115">Element</span></span>|<span data-ttu-id="d0bc7-116">Описание</span><span class="sxs-lookup"><span data-stu-id="d0bc7-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d0bc7-117">Элемент Таблеколумнхеадер для Таблехеадерс для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="d0bc7-117">TableColumnHeader Element for TableHeaders for TableControl  (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="d0bc7-118">Определяет метку, ширину и выравнивание данных для столбца таблицы.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-118">Defines a label, the width, and the alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d0bc7-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="d0bc7-119">Text Value</span></span>

<span data-ttu-id="d0bc7-120">Укажите текст, отображаемый в верхней части столбца таблицы.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-120">Specify the text that is displayed at the top of the column of the table.</span></span> <span data-ttu-id="d0bc7-121">Для метки столбца нет ограниченных символов.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-121">There are no restricted characters for the column label.</span></span>

## <a name="remarks"></a><span data-ttu-id="d0bc7-122">Замечания</span><span class="sxs-lookup"><span data-stu-id="d0bc7-122">Remarks</span></span>

<span data-ttu-id="d0bc7-123">Если метка не указана, то используется имя свойства, значение которого отображается в строках.</span><span class="sxs-lookup"><span data-stu-id="d0bc7-123">If no label is specified, the name of the property whose value is displayed in the rows is used.</span></span>

<span data-ttu-id="d0bc7-124">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="d0bc7-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="d0bc7-125">Пример</span><span class="sxs-lookup"><span data-stu-id="d0bc7-125">Example</span></span>

<span data-ttu-id="d0bc7-126">В этом примере показан элемент `TableColumnHeader`, метка которого равна "Column 1".</span><span class="sxs-lookup"><span data-stu-id="d0bc7-126">This example shows a `TableColumnHeader` element whose label is "Column 1".</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="d0bc7-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="d0bc7-127">See Also</span></span>

[<span data-ttu-id="d0bc7-128">Создание табличного представления</span><span class="sxs-lookup"><span data-stu-id="d0bc7-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="d0bc7-129">Элемент Таблеколумнхеадер (Format)</span><span class="sxs-lookup"><span data-stu-id="d0bc7-129">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="d0bc7-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0bc7-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
