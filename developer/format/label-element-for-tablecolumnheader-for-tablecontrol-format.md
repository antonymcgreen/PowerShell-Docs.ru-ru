---
title: Метка элемента для TableColumnHeader для TableControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7196f039-2f6a-41fd-b252-5b1623ebb9f9
caps.latest.revision: 11
ms.openlocfilehash: 09183a538c179f19347c3f1ed45b4ad38c2ca451
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58054515"
---
# <a name="label-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="a4f7a-102">Элемент Label для элемента TableColumnHeader для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="a4f7a-102">Label Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="a4f7a-103">Определяет метку, которая отображается в верхней части столбца.</span><span class="sxs-lookup"><span data-stu-id="a4f7a-103">Defines the label that is displayed at the top of a column.</span></span> <span data-ttu-id="a4f7a-104">Этот элемент используется при определении представления таблицы.</span><span class="sxs-lookup"><span data-stu-id="a4f7a-104">This element is used when defining a table view.</span></span>

<span data-ttu-id="a4f7a-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемент (формат) TableControl-элемент (формат) TableHeaders элемент конфигурации для элемента TableColumnHeader TableControl (формат) для TableHeaders для метки элемента TableControl (формат) TableColumnHeader для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="a4f7a-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element for TableHeaders for TableControl (Format) Label Element  for TableColumnHeader for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a4f7a-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a4f7a-106">Syntax</span></span>

```xml
<Label>DisplayedLabel</Label>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="a4f7a-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a4f7a-107">Attributes and Elements</span></span>

<span data-ttu-id="a4f7a-108">В следующих разделах атрибуты, дочерние элементы и родительский элемент `Label` элемент.</span><span class="sxs-lookup"><span data-stu-id="a4f7a-108">The following sections describe the attributes, child elements, and the parent element of the `Label` element.</span></span> <span data-ttu-id="a4f7a-109">Для каждого столбца можно использовать только одну метку.</span><span class="sxs-lookup"><span data-stu-id="a4f7a-109">Only one label is allowed for each column.</span></span>

### <a name="attributes"></a><span data-ttu-id="a4f7a-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a4f7a-110">Attributes</span></span>

<span data-ttu-id="a4f7a-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="a4f7a-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a4f7a-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a4f7a-112">Child Elements</span></span>

<span data-ttu-id="a4f7a-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="a4f7a-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a4f7a-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a4f7a-114">Parent Elements</span></span>

|<span data-ttu-id="a4f7a-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="a4f7a-115">Element</span></span>|<span data-ttu-id="a4f7a-116">Описание</span><span class="sxs-lookup"><span data-stu-id="a4f7a-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a4f7a-117">Элемент TableColumnHeader для TableHeaders для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="a4f7a-117">TableColumnHeader Element for TableHeaders for TableControl  (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="a4f7a-118">Определяет метку, ширину и выравнивания данных для столбца таблицы.</span><span class="sxs-lookup"><span data-stu-id="a4f7a-118">Defines a label, the width, and the alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a4f7a-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="a4f7a-119">Text Value</span></span>

<span data-ttu-id="a4f7a-120">Укажите текст, отображаемый в верхней части столбца таблицы.</span><span class="sxs-lookup"><span data-stu-id="a4f7a-120">Specify the text that is displayed at the top of the column of the table.</span></span> <span data-ttu-id="a4f7a-121">Существуют не запрещенные знаки для метки столбца.</span><span class="sxs-lookup"><span data-stu-id="a4f7a-121">There are no restricted characters for the column label.</span></span>

## <a name="remarks"></a><span data-ttu-id="a4f7a-122">Замечания</span><span class="sxs-lookup"><span data-stu-id="a4f7a-122">Remarks</span></span>

<span data-ttu-id="a4f7a-123">Если метка не указана, используется имя свойства, значение которого отображается в строках.</span><span class="sxs-lookup"><span data-stu-id="a4f7a-123">If no label is specified, the name of the property whose value is displayed in the rows is used.</span></span>

<span data-ttu-id="a4f7a-124">Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="a4f7a-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="a4f7a-125">Пример</span><span class="sxs-lookup"><span data-stu-id="a4f7a-125">Example</span></span>

<span data-ttu-id="a4f7a-126">В этом примере показано `TableColumnHeader` элемент, метка которого является «Столбец 1».</span><span class="sxs-lookup"><span data-stu-id="a4f7a-126">This example shows a `TableColumnHeader` element whose label is "Column 1".</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="a4f7a-127">См. также</span><span class="sxs-lookup"><span data-stu-id="a4f7a-127">See Also</span></span>

[<span data-ttu-id="a4f7a-128">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="a4f7a-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="a4f7a-129">Элемент TableColumnHeader (формат)</span><span class="sxs-lookup"><span data-stu-id="a4f7a-129">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="a4f7a-130">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="a4f7a-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
