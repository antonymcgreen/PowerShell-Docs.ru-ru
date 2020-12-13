---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент TableControl (формат)
description: Элемент TableControl (формат)
ms.openlocfilehash: 93e05e22d61504d7781b6f3c07f9a3fd0b3c9e8a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651463"
---
# <a name="tablecontrol-element-format"></a><span data-ttu-id="66d23-103">Элемент TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="66d23-103">TableControl Element (Format)</span></span>

<span data-ttu-id="66d23-104">Определяет формат таблицы для представления.</span><span class="sxs-lookup"><span data-stu-id="66d23-104">Defines a table format for a view.</span></span>

<span data-ttu-id="66d23-105">Элемент Виевдефинитионс (Format) View элемент (Format) Таблеконтрол (формат)</span><span class="sxs-lookup"><span data-stu-id="66d23-105">ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="66d23-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="66d23-106">Syntax</span></span>

```xml
<TableControl>
  <AutoSize/>
  <HideTableHeaders/>
  <TableHeaders>...</TableHeaders>
  <TableRowEntries>...</TableRowEntries>
</TableControl>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="66d23-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="66d23-107">Attributes and Elements</span></span>

<span data-ttu-id="66d23-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TableControl` элемента.</span><span class="sxs-lookup"><span data-stu-id="66d23-108">The following sections describe attributes, child elements, and parent element of the `TableControl` element.</span></span> <span data-ttu-id="66d23-109">Необходимо указать строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="66d23-109">You must specify the rows of the table.</span></span> <span data-ttu-id="66d23-110">Все остальные дочерние элементы являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="66d23-110">All other child elements are optional.</span></span>

### <a name="attributes"></a><span data-ttu-id="66d23-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="66d23-111">Attributes</span></span>

<span data-ttu-id="66d23-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="66d23-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="66d23-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="66d23-113">Child Elements</span></span>

|<span data-ttu-id="66d23-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="66d23-114">Element</span></span>|<span data-ttu-id="66d23-115">Описание</span><span class="sxs-lookup"><span data-stu-id="66d23-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="66d23-116">Элемент AutoSize для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="66d23-116">AutoSize Element for TableControl (Format)</span></span>](./autosize-element-for-tablecontrol-format.md)|<span data-ttu-id="66d23-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="66d23-117">Optional element.</span></span><br /><br /> <span data-ttu-id="66d23-118">Указывает, изменяется ли размер столбца и число столбцов в зависимости от размера данных.</span><span class="sxs-lookup"><span data-stu-id="66d23-118">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>|
|[<span data-ttu-id="66d23-119">Элемент Хидетаблехеадерс для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="66d23-119">HideTableHeaders Element for TableControl (Format)</span></span>](./hidetableheaders-element-format.md)|<span data-ttu-id="66d23-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="66d23-120">Optional element.</span></span><br /><br /> <span data-ttu-id="66d23-121">Указывает, не отображается ли заголовок таблицы.</span><span class="sxs-lookup"><span data-stu-id="66d23-121">Indicates whether the header of the table is not displayed.</span></span>|
|[<span data-ttu-id="66d23-122">Элемент Таблехеадерс для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="66d23-122">TableHeaders Element for TableControl (Format)</span></span>](./tableheaders-element-format.md)|<span data-ttu-id="66d23-123">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="66d23-123">Required element.</span></span><br /><br /> <span data-ttu-id="66d23-124">Определяет метки, ширину и выравнивание данных для столбцов табличного представления.</span><span class="sxs-lookup"><span data-stu-id="66d23-124">Defines the labels, the widths, and the alignment of the data for the columns of the table view.</span></span>|
|[<span data-ttu-id="66d23-125">Элемент TableRowEntries для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="66d23-125">TableRowEntries Element for TableControl (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)|<span data-ttu-id="66d23-126">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="66d23-126">Optional element.</span></span><br /><br /> <span data-ttu-id="66d23-127">Предоставляет определения табличного представления.</span><span class="sxs-lookup"><span data-stu-id="66d23-127">Provides the definitions of the table view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="66d23-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="66d23-128">Parent Elements</span></span>

|<span data-ttu-id="66d23-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="66d23-129">Element</span></span>|<span data-ttu-id="66d23-130">Описание</span><span class="sxs-lookup"><span data-stu-id="66d23-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="66d23-131">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="66d23-131">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="66d23-132">Определяет представление, используемое для отображения элементов одного или нескольких объектов.</span><span class="sxs-lookup"><span data-stu-id="66d23-132">Defines a view that is used to display the members of one or more objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="66d23-133">Комментарии</span><span class="sxs-lookup"><span data-stu-id="66d23-133">Remarks</span></span>

<span data-ttu-id="66d23-134">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="66d23-134">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="66d23-135">Пример</span><span class="sxs-lookup"><span data-stu-id="66d23-135">Example</span></span>

<span data-ttu-id="66d23-136">В этом примере показан `TableControl` элемент, используемый для отображения свойств объекта [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="66d23-136">This example shows a `TableControl` element that is used to display the properties of the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>
    <TableHeaders>...</TableHeaders>
    <TableRowEntries>...</TableRowEntries>
  </TableControl>
</View>

```

## <a name="see-also"></a><span data-ttu-id="66d23-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="66d23-137">See Also</span></span>

[<span data-ttu-id="66d23-138">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="66d23-138">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="66d23-139">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="66d23-139">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="66d23-140">Элемент AutoSize для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="66d23-140">AutoSize Element for TableControl (Format)</span></span>](./autosize-element-for-tablecontrol-format.md)

[<span data-ttu-id="66d23-141">Элемент HideTableHeaders (формат)</span><span class="sxs-lookup"><span data-stu-id="66d23-141">HideTableHeaders Element (Format)</span></span>](./hidetableheaders-element-format.md)

[<span data-ttu-id="66d23-142">Элемент TableHeaders (формат)</span><span class="sxs-lookup"><span data-stu-id="66d23-142">TableHeaders Element (Format)</span></span>](./tableheaders-element-format.md)

[<span data-ttu-id="66d23-143">Элемент Таблеровентриес (Format)</span><span class="sxs-lookup"><span data-stu-id="66d23-143">TableRowEntries Element (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)

[<span data-ttu-id="66d23-144">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="66d23-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
