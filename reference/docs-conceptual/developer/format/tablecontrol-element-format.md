---
title: Элемент Таблеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1550b068-dfbc-4ae0-9aa1-72c9a680ec59
caps.latest.revision: 15
ms.openlocfilehash: 3942c008e026b0b99db3c77af4a0152b50fffc4e
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368203"
---
# <a name="tablecontrol-element-format"></a><span data-ttu-id="88b9a-102">Элемент TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="88b9a-102">TableControl Element (Format)</span></span>

<span data-ttu-id="88b9a-103">Определяет формат таблицы для представления.</span><span class="sxs-lookup"><span data-stu-id="88b9a-103">Defines a table format for a view.</span></span>

<span data-ttu-id="88b9a-104">Элемент Виевдефинитионс (Format) View элемент (Format) Таблеконтрол (формат)</span><span class="sxs-lookup"><span data-stu-id="88b9a-104">ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="88b9a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="88b9a-105">Syntax</span></span>

```xml
<TableControl>
  <AutoSize/>
  <HideTableHeaders/>
  <TableHeaders>...</TableHeaders>
  <TableRowEntries>...</TableRowEntries>
</TableControl>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="88b9a-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="88b9a-106">Attributes and Elements</span></span>

<span data-ttu-id="88b9a-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `TableControl`.</span><span class="sxs-lookup"><span data-stu-id="88b9a-107">The following sections describe attributes, child elements, and parent element of the `TableControl` element.</span></span> <span data-ttu-id="88b9a-108">Необходимо указать строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="88b9a-108">You must specify the rows of the table.</span></span> <span data-ttu-id="88b9a-109">Все остальные дочерние элементы являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="88b9a-109">All other child elements are optional.</span></span>

### <a name="attributes"></a><span data-ttu-id="88b9a-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="88b9a-110">Attributes</span></span>

<span data-ttu-id="88b9a-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="88b9a-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="88b9a-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="88b9a-112">Child Elements</span></span>

|<span data-ttu-id="88b9a-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="88b9a-113">Element</span></span>|<span data-ttu-id="88b9a-114">Описание</span><span class="sxs-lookup"><span data-stu-id="88b9a-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="88b9a-115">Элемент AutoSize для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="88b9a-115">AutoSize Element for TableControl (Format)</span></span>](./autosize-element-for-tablecontrol-format.md)|<span data-ttu-id="88b9a-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="88b9a-116">Optional element.</span></span><br /><br /> <span data-ttu-id="88b9a-117">Указывает, изменяется ли размер столбца и число столбцов в зависимости от размера данных.</span><span class="sxs-lookup"><span data-stu-id="88b9a-117">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>|
|[<span data-ttu-id="88b9a-118">Элемент Хидетаблехеадерс для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="88b9a-118">HideTableHeaders Element for TableControl (Format)</span></span>](./hidetableheaders-element-format.md)|<span data-ttu-id="88b9a-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="88b9a-119">Optional element.</span></span><br /><br /> <span data-ttu-id="88b9a-120">Указывает, не отображается ли заголовок таблицы.</span><span class="sxs-lookup"><span data-stu-id="88b9a-120">Indicates whether the header of the table is not displayed.</span></span>|
|[<span data-ttu-id="88b9a-121">Элемент Таблехеадерс для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="88b9a-121">TableHeaders Element for TableControl (Format)</span></span>](./tableheaders-element-format.md)|<span data-ttu-id="88b9a-122">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="88b9a-122">Required element.</span></span><br /><br /> <span data-ttu-id="88b9a-123">Определяет метки, ширину и выравнивание данных для столбцов табличного представления.</span><span class="sxs-lookup"><span data-stu-id="88b9a-123">Defines the labels, the widths, and the alignment of the data for the columns of the table view.</span></span>|
|[<span data-ttu-id="88b9a-124">Элемент Таблеровентриес для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="88b9a-124">TableRowEntries Element for TableControl (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)|<span data-ttu-id="88b9a-125">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="88b9a-125">Optional element.</span></span><br /><br /> <span data-ttu-id="88b9a-126">Предоставляет определения табличного представления.</span><span class="sxs-lookup"><span data-stu-id="88b9a-126">Provides the definitions of the table view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="88b9a-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="88b9a-127">Parent Elements</span></span>

|<span data-ttu-id="88b9a-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="88b9a-128">Element</span></span>|<span data-ttu-id="88b9a-129">Описание</span><span class="sxs-lookup"><span data-stu-id="88b9a-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="88b9a-130">View, элемент (Format)</span><span class="sxs-lookup"><span data-stu-id="88b9a-130">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="88b9a-131">Определяет представление, используемое для отображения элементов одного или нескольких объектов.</span><span class="sxs-lookup"><span data-stu-id="88b9a-131">Defines a view that is used to display the members of one or more objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="88b9a-132">Замечания</span><span class="sxs-lookup"><span data-stu-id="88b9a-132">Remarks</span></span>

<span data-ttu-id="88b9a-133">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="88b9a-133">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="88b9a-134">Пример</span><span class="sxs-lookup"><span data-stu-id="88b9a-134">Example</span></span>

<span data-ttu-id="88b9a-135">В этом примере показан элемент `TableControl`, используемый для отображения свойств объекта [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="88b9a-135">This example shows a `TableControl` element that is used to display the properties of the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="88b9a-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="88b9a-136">See Also</span></span>

[<span data-ttu-id="88b9a-137">Создание табличного представления</span><span class="sxs-lookup"><span data-stu-id="88b9a-137">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="88b9a-138">View, элемент (Format)</span><span class="sxs-lookup"><span data-stu-id="88b9a-138">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="88b9a-139">Элемент AutoSize для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="88b9a-139">AutoSize Element for TableControl (Format)</span></span>](./autosize-element-for-tablecontrol-format.md)

[<span data-ttu-id="88b9a-140">Элемент Хидетаблехеадерс (Format)</span><span class="sxs-lookup"><span data-stu-id="88b9a-140">HideTableHeaders Element (Format)</span></span>](./hidetableheaders-element-format.md)

[<span data-ttu-id="88b9a-141">Элемент Таблехеадерс (Format)</span><span class="sxs-lookup"><span data-stu-id="88b9a-141">TableHeaders Element (Format)</span></span>](./tableheaders-element-format.md)

[<span data-ttu-id="88b9a-142">Элемент Таблеровентриес (Format)</span><span class="sxs-lookup"><span data-stu-id="88b9a-142">TableRowEntries Element (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)

[<span data-ttu-id="88b9a-143">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="88b9a-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
