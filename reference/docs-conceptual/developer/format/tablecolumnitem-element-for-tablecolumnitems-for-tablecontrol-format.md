---
title: Элемент Таблеколумнитем для Таблеколумнитемс для Таблеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: beadf771f02519394d799a03db374050e3302321
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785172"
---
# <a name="tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format"></a><span data-ttu-id="07855-102">Элемент TableColumnItem для элемента TableColumnItems для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="07855-102">TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>

<span data-ttu-id="07855-103">Определяет свойство или скрипт, значение которого отображается в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="07855-103">Defines the property or script whose value is displayed in the column of the row.</span></span>

<span data-ttu-id="07855-104">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент Таблеконтрол (Format) элемент Таблеровентриес для Таблеконтрол (Format) Таблеровентри для таблеровентриес для TableControl (Format) TableColumnItems для TableControlEntry для TableControl (Format) TableColumnItem для TableColumnItems в TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="07855-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format) TableColumnItems Element for TableControlEntry for TableControl (Format) TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="07855-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="07855-105">Syntax</span></span>

```xml
<TableColumnItem>
  <Alignment>Left, Right, or Center</Alignment>
  <FormatString>FormatPattern</FormatString>
  <PropertyName>Nameof.NetProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</TableColumnItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="07855-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="07855-106">Attributes and Elements</span></span>

<span data-ttu-id="07855-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TableColumnItem` элемента.</span><span class="sxs-lookup"><span data-stu-id="07855-107">The following sections describe the attributes, child elements, and parent element of the `TableColumnItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="07855-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="07855-108">Attributes</span></span>

<span data-ttu-id="07855-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="07855-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="07855-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="07855-110">Child Elements</span></span>

|<span data-ttu-id="07855-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="07855-111">Element</span></span>|<span data-ttu-id="07855-112">Описание</span><span class="sxs-lookup"><span data-stu-id="07855-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="07855-113">Элемент Alignment для TableColumnItem для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="07855-113">Alignment Element for TableColumnItem for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="07855-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="07855-114">Optional element.</span></span><br /><br /> <span data-ttu-id="07855-115">Определяет, как отображаются данные в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="07855-115">Defines how the data in a column of the row is displayed.</span></span>|
|[<span data-ttu-id="07855-116">Элемент FormatString для элемента TableColumnItem для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="07855-116">FormatString Element for TableColumnItem for TableControl (Format)</span></span>](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="07855-117">Задает шаблон формата, используемый для форматирования данных в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="07855-117">Specifies a format pattern that is used to format the data in the column of the row.</span></span>|
|[<span data-ttu-id="07855-118">Элемент PropertyName для элемента TableColumnItem для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="07855-118">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="07855-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="07855-119">Optional element.</span></span><br /><br /> <span data-ttu-id="07855-120">Указывает имя свойства, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="07855-120">Specifies the name of the property whose value is displayed.</span></span>|
|[<span data-ttu-id="07855-121">Элемент ScriptBlock для TableColumnItem для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="07855-121">ScriptBlock Element for TableColumnItem for TableControl (Format)</span></span>](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="07855-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="07855-122">Optional element.</span></span><br /><br /> <span data-ttu-id="07855-123">Задает скрипт, значение которого отображается в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="07855-123">Specifies the script whose value is displayed in the column of a row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="07855-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="07855-124">Parent Elements</span></span>

|<span data-ttu-id="07855-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="07855-125">Element</span></span>|<span data-ttu-id="07855-126">Описание</span><span class="sxs-lookup"><span data-stu-id="07855-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="07855-127">Элемент Таблеколумнитемс для Таблеконтролентри для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="07855-127">TableColumnItems Element for TableControlEntry for TableControl (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="07855-128">Определяет свойства или скрипты, значения которых отображаются в строке.</span><span class="sxs-lookup"><span data-stu-id="07855-128">Defines the properties or scripts whose values are displayed in the row.</span></span>|

## <a name="remarks"></a><span data-ttu-id="07855-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="07855-129">Remarks</span></span>

<span data-ttu-id="07855-130">Можно указать свойство объекта или скрипта в каждом столбце строки.</span><span class="sxs-lookup"><span data-stu-id="07855-130">You can specify a property of an object or a script in each column of the row.</span></span> <span data-ttu-id="07855-131">Если дочерние элементы не указаны, элемент является заполнителем и данные не отображаются.</span><span class="sxs-lookup"><span data-stu-id="07855-131">If no child elements are specified, the item is a placeholder, and no data is displayed.</span></span>

<span data-ttu-id="07855-132">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="07855-132">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="07855-133">Пример</span><span class="sxs-lookup"><span data-stu-id="07855-133">Example</span></span>

<span data-ttu-id="07855-134">В этом примере показан `TableColumnItem` элемент, отображающий значение `Status` свойства объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="07855-134">This example shows a `TableColumnItem` element that displays the value of the `Status` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a><span data-ttu-id="07855-135">См. также</span><span class="sxs-lookup"><span data-stu-id="07855-135">See Also</span></span>

[<span data-ttu-id="07855-136">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="07855-136">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="07855-137">Элемент Alignment для TableColumnItem для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="07855-137">Alignment Element for TableColumnItem for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="07855-138">Элемент Таблеколумнитемс (Format)</span><span class="sxs-lookup"><span data-stu-id="07855-138">TableColumnItems Element (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="07855-139">Элемент FormatString для элемента TableColumnItem для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="07855-139">FormatString Element for TableColumnItem for TableControl (Format)</span></span>](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="07855-140">Элемент PropertyName для элемента TableColumnItem для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="07855-140">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="07855-141">Элемент ScriptBlock для TableColumnItem для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="07855-141">ScriptBlock Element for TableColumnItem for TableControl (Format)</span></span>](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="07855-142">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="07855-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
