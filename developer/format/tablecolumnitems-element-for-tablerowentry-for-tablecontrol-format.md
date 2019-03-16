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
ms.openlocfilehash: d05437aaa9652e7f81d0854d1a746acffe145699
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58056912"
---
# <a name="tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format"></a><span data-ttu-id="bb428-102">Элемент TableColumnItems для элемента TableRowEntry для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="bb428-102">TableColumnItems Element for TableRowEntry for TableControl (Format)</span></span>

<span data-ttu-id="bb428-103">Определяет свойства или скрипты, значения которых отображаются в строке.</span><span class="sxs-lookup"><span data-stu-id="bb428-103">Defines the properties or scripts whose values are displayed in a row.</span></span>

<span data-ttu-id="bb428-104">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) TableRowEntries элемента конфигурации для элемента TableRowEntry TableControl (формат) TableRowEntries для TableControl (формат) Элемент TableColumnItems для TableControlEntry для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="bb428-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format) TableColumnItems Element for TableControlEntry for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bb428-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb428-105">Syntax</span></span>

```xml
TableColumnItems>
  <TableColumnItem>...</TableColumnItem>
</TableColumnItems>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bb428-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bb428-106">Attributes and Elements</span></span>

<span data-ttu-id="bb428-107">В следующих разделах атрибуты, дочерние элементы и родительский элемент `TableColumnItems` элемент.</span><span class="sxs-lookup"><span data-stu-id="bb428-107">The following sections describe the attributes, child elements, and parent element of the `TableColumnItems` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bb428-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bb428-108">Attributes</span></span>

<span data-ttu-id="bb428-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="bb428-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bb428-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bb428-110">Child Elements</span></span>

|<span data-ttu-id="bb428-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="bb428-111">Element</span></span>|<span data-ttu-id="bb428-112">Описание</span><span class="sxs-lookup"><span data-stu-id="bb428-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bb428-113">Элемент TableColumnItem для TableColumnItems для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="bb428-113">TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="bb428-114">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="bb428-114">Required element.</span></span><br /><br /> <span data-ttu-id="bb428-115">Определяет свойство или скрипта, значение которого отображается в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="bb428-115">Defines the property or script whose value is displayed in a column of the row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="bb428-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bb428-116">Parent Elements</span></span>

|<span data-ttu-id="bb428-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="bb428-117">Element</span></span>|<span data-ttu-id="bb428-118">Описание</span><span class="sxs-lookup"><span data-stu-id="bb428-118">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bb428-119">Элемент TableRowEntry для TableRowEntries для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="bb428-119">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="bb428-120">Определяет данные, которые отображаются в строке таблицы.</span><span class="sxs-lookup"><span data-stu-id="bb428-120">Defines the data that is displayed in a row of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bb428-121">Замечания</span><span class="sxs-lookup"><span data-stu-id="bb428-121">Remarks</span></span>

<span data-ttu-id="bb428-122">Объект `TableColumnItem` элемент является обязательным для каждого столбца, строки.</span><span class="sxs-lookup"><span data-stu-id="bb428-122">A `TableColumnItem` element is required for each column of the row.</span></span> <span data-ttu-id="bb428-123">Первая запись отображается в первом столбце, вторая запись второго столбца и т. д.</span><span class="sxs-lookup"><span data-stu-id="bb428-123">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

<span data-ttu-id="bb428-124">Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="bb428-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="bb428-125">Пример</span><span class="sxs-lookup"><span data-stu-id="bb428-125">Example</span></span>

<span data-ttu-id="bb428-126">В следующем примере показан `TableColumnItems` элемент, определяющий три свойства [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) объекта.</span><span class="sxs-lookup"><span data-stu-id="bb428-126">The following example shows a `TableColumnItems` element that defines three properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="bb428-127">См. также</span><span class="sxs-lookup"><span data-stu-id="bb428-127">See Also</span></span>

[<span data-ttu-id="bb428-128">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="bb428-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="bb428-129">Элемент TableColumnItem (формат)</span><span class="sxs-lookup"><span data-stu-id="bb428-129">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="bb428-130">Элемент TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="bb428-130">TableRowEntry Element (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="bb428-131">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb428-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
