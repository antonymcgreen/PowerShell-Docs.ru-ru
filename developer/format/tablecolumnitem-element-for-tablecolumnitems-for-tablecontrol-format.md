---
title: Элемент TableColumnItem для TableColumnItems для TableControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef8395aa-4b31-48c0-a0b8-b481fd0b3738
caps.latest.revision: 15
ms.openlocfilehash: 159f943f6bfb33c5403b5714380631351523789f
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58056997"
---
# <a name="tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format"></a><span data-ttu-id="ff624-102">Элемент TableColumnItem для элемента TableColumnItems для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="ff624-102">TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>

<span data-ttu-id="ff624-103">Определяет свойство или скрипта, значение которого отображается в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="ff624-103">Defines the property or script whose value is displayed in the column of the row.</span></span>

<span data-ttu-id="ff624-104">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) TableRowEntries элемента конфигурации для элемента TableRowEntry TableControl (формат) TableRowEntries для TableControl (формат) Элемент TableColumnItems для TableControlEntry для элемента TableColumnItem TableControl (формат) TableColumnItems для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="ff624-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format) TableColumnItems Element for TableControlEntry for TableControl (Format) TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ff624-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff624-105">Syntax</span></span>

```xml
<TableColumnItem>
  <Alignment>Left, Right, or Center</Alignment>
  <PropertyName>Nameof.NetProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</TableColumnItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ff624-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ff624-106">Attributes and Elements</span></span>

<span data-ttu-id="ff624-107">В следующих разделах атрибуты, дочерние элементы и родительский элемент `TableColumnItem` элемент.</span><span class="sxs-lookup"><span data-stu-id="ff624-107">The following sections describe the attributes, child elements, and parent element of the `TableColumnItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ff624-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ff624-108">Attributes</span></span>

<span data-ttu-id="ff624-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="ff624-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ff624-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ff624-110">Child Elements</span></span>

|<span data-ttu-id="ff624-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="ff624-111">Element</span></span>|<span data-ttu-id="ff624-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ff624-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ff624-113">Выравнивание элемента для TableColumnItem для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="ff624-113">Alignment Element for TableColumnItem for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="ff624-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ff624-114">Optional element.</span></span><br /><br /> <span data-ttu-id="ff624-115">Определяет способ отображения данных в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="ff624-115">Defines how the data in a column of the row is displayed.</span></span>|
|[<span data-ttu-id="ff624-116">Элемент FormatString для TableColumnItem для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="ff624-116">FormatString Element for TableColumnItem for TableControl (Format)</span></span>](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="ff624-117">Задает шаблон формата, который используется для форматирования данных в столбец строки.</span><span class="sxs-lookup"><span data-stu-id="ff624-117">Specifies a format pattern that is used to format the data in the column of the row.</span></span>|
|[<span data-ttu-id="ff624-118">Элемент PropertyName для TableColumnItem для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="ff624-118">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="ff624-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ff624-119">Optional element.</span></span><br /><br /> <span data-ttu-id="ff624-120">Указывает имя свойства, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="ff624-120">Specifies the name of the property whose value is displayed.</span></span>|
|[<span data-ttu-id="ff624-121">Элемент ScriptBlock для TableColumnItem для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="ff624-121">ScriptBlock Element for TableColumnItem for TableControl (Format)</span></span>](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="ff624-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ff624-122">Optional element.</span></span><br /><br /> <span data-ttu-id="ff624-123">Указывает сценарий, значение которого отображается в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="ff624-123">Specifies the script whose value is displayed in the column of a row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ff624-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ff624-124">Parent Elements</span></span>

|<span data-ttu-id="ff624-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="ff624-125">Element</span></span>|<span data-ttu-id="ff624-126">Описание</span><span class="sxs-lookup"><span data-stu-id="ff624-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ff624-127">Элемент TableColumnItems для TableControlEntry для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="ff624-127">TableColumnItems Element for TableControlEntry for TableControl (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="ff624-128">Определяет свойства или скрипты, значения которых отображаются в строке.</span><span class="sxs-lookup"><span data-stu-id="ff624-128">Defines the properties or scripts whose values are displayed in the row.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ff624-129">Замечания</span><span class="sxs-lookup"><span data-stu-id="ff624-129">Remarks</span></span>

<span data-ttu-id="ff624-130">В каждом столбце строки можно указать свойства объекта или скрипта.</span><span class="sxs-lookup"><span data-stu-id="ff624-130">You can specify a property of an object or a script in each column of the row.</span></span> <span data-ttu-id="ff624-131">Если нет дочерних элементов не заданы, элемент — это заполнитель, а данные не отображаются.</span><span class="sxs-lookup"><span data-stu-id="ff624-131">If no child elements are specified, the item is a placeholder, and no data is displayed.</span></span>

<span data-ttu-id="ff624-132">Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="ff624-132">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="ff624-133">Пример</span><span class="sxs-lookup"><span data-stu-id="ff624-133">Example</span></span>

<span data-ttu-id="ff624-134">В этом примере показано `TableColumnItem` элемент, который отображает значение `Status` свойство [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) объекта.</span><span class="sxs-lookup"><span data-stu-id="ff624-134">This example shows a `TableColumnItem` element that displays the value of the `Status` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a><span data-ttu-id="ff624-135">См. также</span><span class="sxs-lookup"><span data-stu-id="ff624-135">See Also</span></span>

[<span data-ttu-id="ff624-136">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="ff624-136">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="ff624-137">Выравнивание элемента для TableColumnItem для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="ff624-137">Alignment Element for TableColumnItem for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="ff624-138">Элемент TableColumnItems (формат)</span><span class="sxs-lookup"><span data-stu-id="ff624-138">TableColumnItems Element (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="ff624-139">Элемент FormatString для TableColumnItem для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="ff624-139">FormatString Element for TableColumnItem for TableControl (Format)</span></span>](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="ff624-140">Элемент PropertyName для TableColumnItem для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="ff624-140">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="ff624-141">Элемент ScriptBlock для TableColumnItem для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="ff624-141">ScriptBlock Element for TableColumnItem for TableControl (Format)</span></span>](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="ff624-142">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="ff624-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
