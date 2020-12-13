---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент TableColumnItem для элемента TableColumnItems для элемента TableControl (формат)
description: Элемент TableColumnItem для элемента TableColumnItems для элемента TableControl (формат)
ms.openlocfilehash: 8ef5158c9bb9f074d5c58190d4d3b20c10c83744
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659855"
---
# <a name="tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format"></a><span data-ttu-id="02840-103">Элемент TableColumnItem для элемента TableColumnItems для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="02840-103">TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>

<span data-ttu-id="02840-104">Определяет свойство или скрипт, значение которого отображается в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="02840-104">Defines the property or script whose value is displayed in the column of the row.</span></span>

<span data-ttu-id="02840-105">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент Таблеконтрол (Format) элемент Таблеровентриес для Таблеконтрол (Format) Таблеровентри для таблеровентриес для TableControl (Format) TableColumnItems для TableControlEntry для TableControl (Format) TableColumnItem для TableColumnItems в TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="02840-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format) TableColumnItems Element for TableControlEntry for TableControl (Format) TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="02840-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="02840-106">Syntax</span></span>

```xml
<TableColumnItem>
  <Alignment>Left, Right, or Center</Alignment>
  <FormatString>FormatPattern</FormatString>
  <PropertyName>Nameof.NetProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</TableColumnItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="02840-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="02840-107">Attributes and Elements</span></span>

<span data-ttu-id="02840-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TableColumnItem` элемента.</span><span class="sxs-lookup"><span data-stu-id="02840-108">The following sections describe the attributes, child elements, and parent element of the `TableColumnItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="02840-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="02840-109">Attributes</span></span>

<span data-ttu-id="02840-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="02840-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="02840-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="02840-111">Child Elements</span></span>

|<span data-ttu-id="02840-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="02840-112">Element</span></span>|<span data-ttu-id="02840-113">Описание</span><span class="sxs-lookup"><span data-stu-id="02840-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="02840-114">Элемент Alignment для TableColumnItem для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="02840-114">Alignment Element for TableColumnItem for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="02840-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="02840-115">Optional element.</span></span><br /><br /> <span data-ttu-id="02840-116">Определяет, как отображаются данные в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="02840-116">Defines how the data in a column of the row is displayed.</span></span>|
|[<span data-ttu-id="02840-117">Элемент FormatString для элемента TableColumnItem для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="02840-117">FormatString Element for TableColumnItem for TableControl (Format)</span></span>](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="02840-118">Задает шаблон формата, используемый для форматирования данных в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="02840-118">Specifies a format pattern that is used to format the data in the column of the row.</span></span>|
|[<span data-ttu-id="02840-119">Элемент PropertyName для элемента TableColumnItem для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="02840-119">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="02840-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="02840-120">Optional element.</span></span><br /><br /> <span data-ttu-id="02840-121">Указывает имя свойства, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="02840-121">Specifies the name of the property whose value is displayed.</span></span>|
|[<span data-ttu-id="02840-122">Элемент ScriptBlock для TableColumnItem для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="02840-122">ScriptBlock Element for TableColumnItem for TableControl (Format)</span></span>](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="02840-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="02840-123">Optional element.</span></span><br /><br /> <span data-ttu-id="02840-124">Задает скрипт, значение которого отображается в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="02840-124">Specifies the script whose value is displayed in the column of a row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="02840-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="02840-125">Parent Elements</span></span>

|<span data-ttu-id="02840-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="02840-126">Element</span></span>|<span data-ttu-id="02840-127">Описание</span><span class="sxs-lookup"><span data-stu-id="02840-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="02840-128">Элемент Таблеколумнитемс для Таблеконтролентри для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="02840-128">TableColumnItems Element for TableControlEntry for TableControl (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="02840-129">Определяет свойства или скрипты, значения которых отображаются в строке.</span><span class="sxs-lookup"><span data-stu-id="02840-129">Defines the properties or scripts whose values are displayed in the row.</span></span>|

## <a name="remarks"></a><span data-ttu-id="02840-130">Комментарии</span><span class="sxs-lookup"><span data-stu-id="02840-130">Remarks</span></span>

<span data-ttu-id="02840-131">Можно указать свойство объекта или скрипта в каждом столбце строки.</span><span class="sxs-lookup"><span data-stu-id="02840-131">You can specify a property of an object or a script in each column of the row.</span></span> <span data-ttu-id="02840-132">Если дочерние элементы не указаны, элемент является заполнителем и данные не отображаются.</span><span class="sxs-lookup"><span data-stu-id="02840-132">If no child elements are specified, the item is a placeholder, and no data is displayed.</span></span>

<span data-ttu-id="02840-133">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="02840-133">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="02840-134">Пример</span><span class="sxs-lookup"><span data-stu-id="02840-134">Example</span></span>

<span data-ttu-id="02840-135">В этом примере показан `TableColumnItem` элемент, отображающий значение `Status` свойства объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="02840-135">This example shows a `TableColumnItem` element that displays the value of the `Status` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a><span data-ttu-id="02840-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="02840-136">See Also</span></span>

[<span data-ttu-id="02840-137">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="02840-137">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="02840-138">Элемент Alignment для TableColumnItem для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="02840-138">Alignment Element for TableColumnItem for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="02840-139">Элемент Таблеколумнитемс (Format)</span><span class="sxs-lookup"><span data-stu-id="02840-139">TableColumnItems Element (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="02840-140">Элемент FormatString для элемента TableColumnItem для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="02840-140">FormatString Element for TableColumnItem for TableControl (Format)</span></span>](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="02840-141">Элемент PropertyName для элемента TableColumnItem для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="02840-141">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="02840-142">Элемент ScriptBlock для TableColumnItem для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="02840-142">ScriptBlock Element for TableColumnItem for TableControl (Format)</span></span>](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="02840-143">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="02840-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
