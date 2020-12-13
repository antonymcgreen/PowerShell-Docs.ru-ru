---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент Width для элемента TableColumnHeader для элемента TableControl (формат)
description: Элемент Width для элемента TableColumnHeader для элемента TableControl (формат)
ms.openlocfilehash: bde84f1d33b3d6b3b8c4462f870f978611cb434b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658250"
---
# <a name="width-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="f63ef-103">Элемент Width для элемента TableColumnHeader для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="f63ef-103">Width Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="f63ef-104">Определяет ширину (в символах) столбца.</span><span class="sxs-lookup"><span data-stu-id="f63ef-104">Defines the width (in characters) of a column.</span></span>

<span data-ttu-id="f63ef-105">Элемент конфигурации (Format) Виевдефинитионс элемента представления (Format) элемент Таблеконтрол (Format) элемент Таблехеадерс для Таблеконтрол (Format) Таблеколумнхеадер элемент Таблехеадерс для TableControl (формат) элемент TableColumnHeader для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="f63ef-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element TableHeaders for TableControl (Format) Width Element for TableColumnHeader for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f63ef-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f63ef-106">Syntax</span></span>

```xml
<Width>NumberOfCharacters</Width>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f63ef-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f63ef-107">Attributes and Elements</span></span>

<span data-ttu-id="f63ef-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Width` элемента, используемого при определении заголовков столбцов.</span><span class="sxs-lookup"><span data-stu-id="f63ef-108">The following sections describe the attributes, child elements, and parent element of the `Width` element used when defining column headers.</span></span>

### <a name="attributes"></a><span data-ttu-id="f63ef-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f63ef-109">Attributes</span></span>

<span data-ttu-id="f63ef-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f63ef-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f63ef-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f63ef-111">Child Elements</span></span>

<span data-ttu-id="f63ef-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f63ef-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f63ef-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f63ef-113">Parent Elements</span></span>

|<span data-ttu-id="f63ef-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="f63ef-114">Element</span></span>|<span data-ttu-id="f63ef-115">Описание</span><span class="sxs-lookup"><span data-stu-id="f63ef-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f63ef-116">Элемент Таблеколумнхеадер для Таблехеадерс для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="f63ef-116">TableColumnHeader Element for TableHeaders for TableControl (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="f63ef-117">Определяет метку, ширину и выравнивание данных для столбца таблицы.</span><span class="sxs-lookup"><span data-stu-id="f63ef-117">Defines a label, width, and alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f63ef-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="f63ef-118">Text Value</span></span>

<span data-ttu-id="f63ef-119">Когда это возможно, укажите ширину (в символах), превышающую длину отображаемых значений свойств.</span><span class="sxs-lookup"><span data-stu-id="f63ef-119">When at all possible, specify a width (in characters) that is greater than the length of the displayed property values.</span></span>

## <a name="remarks"></a><span data-ttu-id="f63ef-120">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f63ef-120">Remarks</span></span>

<span data-ttu-id="f63ef-121">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="f63ef-121">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="f63ef-122">Пример</span><span class="sxs-lookup"><span data-stu-id="f63ef-122">Example</span></span>

<span data-ttu-id="f63ef-123">В следующем примере показан `TableColumnHeader` элемент, ширина которого составляет 16 символов.</span><span class="sxs-lookup"><span data-stu-id="f63ef-123">The following example shows a `TableColumnHeader` element whose width is 16 characters.</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="f63ef-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="f63ef-124">See Also</span></span>

[<span data-ttu-id="f63ef-125">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="f63ef-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="f63ef-126">Элемент Таблеколумнхеадер для Таблехеадер для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="f63ef-126">TableColumnHeader Element for TableHeader for TableControl (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="f63ef-127">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="f63ef-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
