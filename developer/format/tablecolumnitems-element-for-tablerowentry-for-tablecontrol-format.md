---
title: Элемент TableColumnItems для TableRowEntry для TableControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d43684ce-7c3d-4d14-8dbd-061c111ee805
caps.latest.revision: 12
ms.openlocfilehash: faa9ba78397e713400f6072df9915f20d966bb37
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859450"
---
# <a name="tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format"></a><span data-ttu-id="5fb86-102">Элемент TableColumnItems для элемента TableRowEntry для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="5fb86-102">TableColumnItems Element for TableRowEntry for TableControl (Format)</span></span>

<span data-ttu-id="5fb86-103">Определяет свойства или скрипты, значения которых отображаются в строке.</span><span class="sxs-lookup"><span data-stu-id="5fb86-103">Defines the properties or scripts whose values are displayed in a row.</span></span>

<span data-ttu-id="5fb86-104">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) TableRowEntries элемента конфигурации для элемента TableRowEntry TableControl (формат) TableRowEntries для TableControl (формат) Элемент TableColumnItems для TableControlEntry для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="5fb86-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format) TableColumnItems Element for TableControlEntry for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5fb86-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5fb86-105">Syntax</span></span>

```xml
TableColumnItems>
  <TableColumnItem>...</TableColumnItem>
</TableColumnItems>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5fb86-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5fb86-106">Attributes and Elements</span></span>

<span data-ttu-id="5fb86-107">В следующих разделах атрибуты, дочерние элементы и родительский элемент `TableColumnItems` элемент.</span><span class="sxs-lookup"><span data-stu-id="5fb86-107">The following sections describe the attributes, child elements, and parent element of the `TableColumnItems` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5fb86-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5fb86-108">Attributes</span></span>

<span data-ttu-id="5fb86-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="5fb86-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5fb86-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5fb86-110">Child Elements</span></span>

|<span data-ttu-id="5fb86-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="5fb86-111">Element</span></span>|<span data-ttu-id="5fb86-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5fb86-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5fb86-113">Элемент TableColumnItem для TableColumnItems для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="5fb86-113">TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="5fb86-114">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="5fb86-114">Required element.</span></span><br /><br /> <span data-ttu-id="5fb86-115">Определяет свойство или скрипта, значение которого отображается в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="5fb86-115">Defines the property or script whose value is displayed in a column of the row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5fb86-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5fb86-116">Parent Elements</span></span>

|<span data-ttu-id="5fb86-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="5fb86-117">Element</span></span>|<span data-ttu-id="5fb86-118">Описание</span><span class="sxs-lookup"><span data-stu-id="5fb86-118">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5fb86-119">Элемент TableRowEntry для TableRowEntries для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="5fb86-119">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentroes-for-tablecontrol-format.md)|<span data-ttu-id="5fb86-120">Определяет данные, которые отображаются в строке таблицы.</span><span class="sxs-lookup"><span data-stu-id="5fb86-120">Defines the data that is displayed in a row of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5fb86-121">Замечания</span><span class="sxs-lookup"><span data-stu-id="5fb86-121">Remarks</span></span>

<span data-ttu-id="5fb86-122">Объект `TableColumnItem` элемент является обязательным для каждого столбца, строки.</span><span class="sxs-lookup"><span data-stu-id="5fb86-122">A `TableColumnItem` element is required for each column of the row.</span></span> <span data-ttu-id="5fb86-123">Первая запись отображается в первом столбце, вторая запись второго столбца и т. д.</span><span class="sxs-lookup"><span data-stu-id="5fb86-123">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

<span data-ttu-id="5fb86-124">Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="5fb86-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="5fb86-125">Пример</span><span class="sxs-lookup"><span data-stu-id="5fb86-125">Example</span></span>

<span data-ttu-id="5fb86-126">В следующем примере показан `TableColumnItems` элемент, определяющий три свойства [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) объекта.</span><span class="sxs-lookup"><span data-stu-id="5fb86-126">The following example shows a `TableColumnItems` element that defines three properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItems>
  <TableColumnItem>
    <PropertyName>Status</PropertyName>
  </TableColumnItem>
  <TableColumnItem>
    <PropertyName>Name</PropertyName>
  </TableColumnItem>
  <TableColumnItem>
    <PropertyName>DisplayName</PropertyName>
  </TableColumnItem>
</TableColumnItems>

```

## <a name="see-also"></a><span data-ttu-id="5fb86-127">См. также</span><span class="sxs-lookup"><span data-stu-id="5fb86-127">See Also</span></span>

[<span data-ttu-id="5fb86-128">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="5fb86-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="5fb86-129">Элемент TableColumnItem (формат)</span><span class="sxs-lookup"><span data-stu-id="5fb86-129">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="5fb86-130">Элемент TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="5fb86-130">TableRowEntry Element (Format)</span></span>](./tablerowentry-element-for-tablerowentroes-for-tablecontrol-format.md)

[<span data-ttu-id="5fb86-131">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="5fb86-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
