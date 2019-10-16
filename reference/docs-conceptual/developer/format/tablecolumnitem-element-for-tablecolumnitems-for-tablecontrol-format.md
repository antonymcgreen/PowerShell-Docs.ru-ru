---
title: Элемент Таблеколумнитем для Таблеколумнитемс для Таблеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef8395aa-4b31-48c0-a0b8-b481fd0b3738
caps.latest.revision: 15
ms.openlocfilehash: 9e6cffc7476ef01124d95ecbf287d9788b0324c9
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368233"
---
# <a name="tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format"></a><span data-ttu-id="63883-102">Элемент TableColumnItem для элемента TableColumnItems для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="63883-102">TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>

<span data-ttu-id="63883-103">Определяет свойство или скрипт, значение которого отображается в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="63883-103">Defines the property or script whose value is displayed in the column of the row.</span></span>

<span data-ttu-id="63883-104">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Таблеконтрол элемент (Format) Таблеровентриес для Таблеконтрол (Format) Таблеровентри для Таблеровентриес в TableControl (Format) Элемент Таблеколумнитемс для Таблеконтролентри для Таблеконтрол (Format) Таблеколумнитем элемента для Таблеколумнитемс для TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="63883-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format) TableColumnItems Element for TableControlEntry for TableControl (Format) TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="63883-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="63883-105">Syntax</span></span>

```xml
<TableColumnItem>
  <Alignment>Left, Right, or Center</Alignment>
  <FormatString>FormatPattern</FormatString>
  <PropertyName>Nameof.NetProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</TableColumnItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="63883-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="63883-106">Attributes and Elements</span></span>

<span data-ttu-id="63883-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `TableColumnItem`.</span><span class="sxs-lookup"><span data-stu-id="63883-107">The following sections describe the attributes, child elements, and parent element of the `TableColumnItem` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="63883-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="63883-108">Attributes</span></span>

<span data-ttu-id="63883-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="63883-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="63883-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="63883-110">Child Elements</span></span>

|<span data-ttu-id="63883-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="63883-111">Element</span></span>|<span data-ttu-id="63883-112">Описание</span><span class="sxs-lookup"><span data-stu-id="63883-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="63883-113">Элемент Alignment для Таблеколумнитем для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="63883-113">Alignment Element for TableColumnItem for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="63883-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="63883-114">Optional element.</span></span><br /><br /> <span data-ttu-id="63883-115">Определяет, как отображаются данные в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="63883-115">Defines how the data in a column of the row is displayed.</span></span>|
|[<span data-ttu-id="63883-116">Элемент FormatString для Таблеколумнитем для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="63883-116">FormatString Element for TableColumnItem for TableControl (Format)</span></span>](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="63883-117">Задает шаблон формата, используемый для форматирования данных в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="63883-117">Specifies a format pattern that is used to format the data in the column of the row.</span></span>|
|[<span data-ttu-id="63883-118">Элемент PropertyName для Таблеколумнитем для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="63883-118">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="63883-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="63883-119">Optional element.</span></span><br /><br /> <span data-ttu-id="63883-120">Указывает имя свойства, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="63883-120">Specifies the name of the property whose value is displayed.</span></span>|
|[<span data-ttu-id="63883-121">Элемент ScriptBlock для Таблеколумнитем для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="63883-121">ScriptBlock Element for TableColumnItem for TableControl (Format)</span></span>](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)|<span data-ttu-id="63883-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="63883-122">Optional element.</span></span><br /><br /> <span data-ttu-id="63883-123">Задает скрипт, значение которого отображается в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="63883-123">Specifies the script whose value is displayed in the column of a row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="63883-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="63883-124">Parent Elements</span></span>

|<span data-ttu-id="63883-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="63883-125">Element</span></span>|<span data-ttu-id="63883-126">Описание</span><span class="sxs-lookup"><span data-stu-id="63883-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="63883-127">Элемент Таблеколумнитемс для Таблеконтролентри для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="63883-127">TableColumnItems Element for TableControlEntry for TableControl (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="63883-128">Определяет свойства или скрипты, значения которых отображаются в строке.</span><span class="sxs-lookup"><span data-stu-id="63883-128">Defines the properties or scripts whose values are displayed in the row.</span></span>|

## <a name="remarks"></a><span data-ttu-id="63883-129">Замечания</span><span class="sxs-lookup"><span data-stu-id="63883-129">Remarks</span></span>

<span data-ttu-id="63883-130">Можно указать свойство объекта или скрипта в каждом столбце строки.</span><span class="sxs-lookup"><span data-stu-id="63883-130">You can specify a property of an object or a script in each column of the row.</span></span> <span data-ttu-id="63883-131">Если дочерние элементы не указаны, элемент является заполнителем и данные не отображаются.</span><span class="sxs-lookup"><span data-stu-id="63883-131">If no child elements are specified, the item is a placeholder, and no data is displayed.</span></span>

<span data-ttu-id="63883-132">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="63883-132">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="63883-133">Пример</span><span class="sxs-lookup"><span data-stu-id="63883-133">Example</span></span>

<span data-ttu-id="63883-134">В этом примере показан элемент `TableColumnItem`, отображающий значение свойства `Status` объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="63883-134">This example shows a `TableColumnItem` element that displays the value of the `Status` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a><span data-ttu-id="63883-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="63883-135">See Also</span></span>

[<span data-ttu-id="63883-136">Создание табличного представления</span><span class="sxs-lookup"><span data-stu-id="63883-136">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="63883-137">Элемент Alignment для Таблеколумнитем для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="63883-137">Alignment Element for TableColumnItem for TableControl (Format)</span></span>](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="63883-138">Элемент Таблеколумнитемс (Format)</span><span class="sxs-lookup"><span data-stu-id="63883-138">TableColumnItems Element (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="63883-139">Элемент FormatString для Таблеколумнитем для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="63883-139">FormatString Element for TableColumnItem for TableControl (Format)</span></span>](./formatstring-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="63883-140">Элемент PropertyName для Таблеколумнитем для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="63883-140">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="63883-141">Элемент ScriptBlock для Таблеколумнитем для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="63883-141">ScriptBlock Element for TableColumnItem for TableControl (Format)</span></span>](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md)

[<span data-ttu-id="63883-142">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="63883-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
