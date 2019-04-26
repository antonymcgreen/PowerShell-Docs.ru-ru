---
title: Выравнивание элемента для TableColumnHeader для TableControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ff85e83a-c9c2-4c37-accc-e6a27c182f3c
caps.latest.revision: 19
ms.openlocfilehash: 16b41535109ca503e679a135f5ba30054e33de5b
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067014"
---
# <a name="alignment-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="7111e-102">Элемент Alignment для TableColumnHeader для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="7111e-102">Alignment Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="7111e-103">Определяет способ отображения данных в заголовке столбца.</span><span class="sxs-lookup"><span data-stu-id="7111e-103">Defines how the data in a column header is displayed.</span></span>

<span data-ttu-id="7111e-104">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) элемент TableHeaders (формат) элемент TableColumnHeader (формат) выравнивание элемент конфигурации для TableColumnHeader (формат)</span><span class="sxs-lookup"><span data-stu-id="7111e-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element (Format) TableColumnHeader Element (Format) Alignment Element for TableColumnHeader (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7111e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7111e-105">Syntax</span></span>

```xml
<Alignment>AlignmentType</Alignment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7111e-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7111e-106">Attributes and Elements</span></span>

<span data-ttu-id="7111e-107">В следующих разделах атрибуты, дочерние элементы и родительский элемент `Alignment` элемент.</span><span class="sxs-lookup"><span data-stu-id="7111e-107">The following sections describe the attributes, child elements, and parent element of the `Alignment` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7111e-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7111e-108">Attributes</span></span>

<span data-ttu-id="7111e-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="7111e-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7111e-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7111e-110">Child Elements</span></span>

<span data-ttu-id="7111e-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="7111e-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7111e-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7111e-112">Parent Elements</span></span>

|<span data-ttu-id="7111e-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="7111e-113">Element</span></span>|<span data-ttu-id="7111e-114">Описание</span><span class="sxs-lookup"><span data-stu-id="7111e-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7111e-115">Элемент TableColumnHeader (формат)</span><span class="sxs-lookup"><span data-stu-id="7111e-115">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="7111e-116">Определяет метку, ширину и выравнивания данных для столбца таблицы.</span><span class="sxs-lookup"><span data-stu-id="7111e-116">Defines a label, the width, and the alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7111e-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="7111e-117">Text Value</span></span>

<span data-ttu-id="7111e-118">Укажите одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="7111e-118">Specify one of the following values.</span></span> <span data-ttu-id="7111e-119">Эти значения не учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="7111e-119">These values are not case-sensitive.</span></span>

<span data-ttu-id="7111e-120">Выравнивание данных отображаются в столбце слева это значение по умолчанию, если этот элемент не указан.</span><span class="sxs-lookup"><span data-stu-id="7111e-120">Left Aligns the data displayed in the column on the left This is the default if this element is not specified.</span></span>

<span data-ttu-id="7111e-121">По правому данные отображаются в столбце справа.</span><span class="sxs-lookup"><span data-stu-id="7111e-121">Right Aligns the data displayed in the column on the right.</span></span>

<span data-ttu-id="7111e-122">Center центров обработки данных, отображаемых в столбце.</span><span class="sxs-lookup"><span data-stu-id="7111e-122">Center Centers the data displayed in the column.</span></span>

## <a name="remarks"></a><span data-ttu-id="7111e-123">Замечания</span><span class="sxs-lookup"><span data-stu-id="7111e-123">Remarks</span></span>

<span data-ttu-id="7111e-124">Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="7111e-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="7111e-125">Пример</span><span class="sxs-lookup"><span data-stu-id="7111e-125">Example</span></span>

<span data-ttu-id="7111e-126">В этом примере показано `TableColumnHeader` элемента, данные которого по левому краю.</span><span class="sxs-lookup"><span data-stu-id="7111e-126">This example shows a `TableColumnHeader` element whose data is aligned on the left.</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="7111e-127">См. также</span><span class="sxs-lookup"><span data-stu-id="7111e-127">See Also</span></span>

[<span data-ttu-id="7111e-128">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="7111e-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="7111e-129">Элемент TableColumnHeader (формат)</span><span class="sxs-lookup"><span data-stu-id="7111e-129">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="7111e-130">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="7111e-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
