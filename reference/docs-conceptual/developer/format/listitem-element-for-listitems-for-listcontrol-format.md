---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ListItem для элемента ListItems для элемента ListControl (формат)
description: Элемент ListItem для элемента ListItems для элемента ListControl (формат)
ms.openlocfilehash: 999491b7851aa4fa21667ad376d7e9853500ca08
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666558"
---
# <a name="listitem-element-for-listitems-for-listcontrol-format"></a><span data-ttu-id="d9a43-103">Элемент ListItem для элемента ListItems для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="d9a43-103">ListItem Element for ListItems for ListControl (Format)</span></span>

<span data-ttu-id="d9a43-104">Определяет свойство или скрипт, значение которого отображается в строке представления списка.</span><span class="sxs-lookup"><span data-stu-id="d9a43-104">Defines the property or script whose value is displayed in a row of the list view.</span></span>

<span data-ttu-id="d9a43-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес для ListControl (Format) Листентри элемент для ListControl (Format) элемент списка элементов для ListControl (Format) для элемента (формат)</span><span class="sxs-lookup"><span data-stu-id="d9a43-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format) ListItem for ListControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d9a43-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d9a43-106">Syntax</span></span>

```xml
<ListItem>
  <PropertyName>PropertyToDisplay</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <Label>LabelToDisplay</Label>
  <FormatString>FormatPattern</FormatString>
  <ItemSelectionCondition>...</ItemSelectionCondition>
</ListItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d9a43-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d9a43-107">Attributes and Elements</span></span>

<span data-ttu-id="d9a43-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ListItem` элемента.</span><span class="sxs-lookup"><span data-stu-id="d9a43-108">The following sections describe the attributes, child elements, and parent element of the `ListItem` element.</span></span> <span data-ttu-id="d9a43-109">Можно указать только одно свойство или скрипт.</span><span class="sxs-lookup"><span data-stu-id="d9a43-109">Only one property or script can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="d9a43-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d9a43-110">Attributes</span></span>

<span data-ttu-id="d9a43-111">None</span><span class="sxs-lookup"><span data-stu-id="d9a43-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="d9a43-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d9a43-112">Child Elements</span></span>

|<span data-ttu-id="d9a43-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="d9a43-113">Element</span></span>|<span data-ttu-id="d9a43-114">Описание</span><span class="sxs-lookup"><span data-stu-id="d9a43-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d9a43-115">Элемент FormatString для ListItem для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="d9a43-115">FormatString Element for ListItem for ListControl (Format)</span></span>](./formatstring-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="d9a43-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d9a43-116">Optional element.</span></span><br /><br /> <span data-ttu-id="d9a43-117">Задает строку формата, определяющую способ отображения значения свойства или скрипта.</span><span class="sxs-lookup"><span data-stu-id="d9a43-117">Specifies a format string that defines how the property or script value is displayed.</span></span>|
|[<span data-ttu-id="d9a43-118">Элемент ItemSelectionCondition для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="d9a43-118">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="d9a43-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d9a43-119">Optional element.</span></span><br /><br /> <span data-ttu-id="d9a43-120">Определяет условие, которое должно существовать для использования этого элемента списка.</span><span class="sxs-lookup"><span data-stu-id="d9a43-120">Defines the condition that must exist for this list item to be used.</span></span>|
|[<span data-ttu-id="d9a43-121">Элемент Label для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="d9a43-121">Label Element for ListItem for ListControl (Format)</span></span>](./label-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="d9a43-122">Необязательный элемент</span><span class="sxs-lookup"><span data-stu-id="d9a43-122">Optional element</span></span><br /><br /> <span data-ttu-id="d9a43-123">Задает метку, которая отображается слева от значения свойства или скрипта в строке.</span><span class="sxs-lookup"><span data-stu-id="d9a43-123">Specifies the label that is displayed to the left of the property or script value in the row.</span></span>|
|[<span data-ttu-id="d9a43-124">Элемент PropertyName для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="d9a43-124">PropertyName Element for ListItem for ListControl (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="d9a43-125">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d9a43-125">Optional element.</span></span><br /><br /> <span data-ttu-id="d9a43-126">Указывает свойство .NET, значение которого отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="d9a43-126">Specifies the .NET property whose value is displayed in the row.</span></span>|
|[<span data-ttu-id="d9a43-127">Элемент ScriptBlock для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="d9a43-127">ScriptBlock Element for ListItem for ListControl (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="d9a43-128">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d9a43-128">Optional element.</span></span><br /><br /> <span data-ttu-id="d9a43-129">Указывает скрипт, значение которого отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="d9a43-129">Specifies the script whose value is displayed in the row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d9a43-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d9a43-130">Parent Elements</span></span>

|<span data-ttu-id="d9a43-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="d9a43-131">Element</span></span>|<span data-ttu-id="d9a43-132">Описание</span><span class="sxs-lookup"><span data-stu-id="d9a43-132">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d9a43-133">Элемент ListItems для элемента управления "список" (формат)</span><span class="sxs-lookup"><span data-stu-id="d9a43-133">ListItems Element for List Control (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="d9a43-134">Определяет свойства и скрипты, значения которых отображаются в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="d9a43-134">Defines the properties and scripts whose values are displayed in the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d9a43-135">Комментарии</span><span class="sxs-lookup"><span data-stu-id="d9a43-135">Remarks</span></span>

<span data-ttu-id="d9a43-136">Дополнительные сведения о компонентах представления списка см. [в разделе Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="d9a43-136">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="d9a43-137">Пример</span><span class="sxs-lookup"><span data-stu-id="d9a43-137">Example</span></span>

<span data-ttu-id="d9a43-138">В этом примере показаны XML-элементы, определяющие три строки представления списка.</span><span class="sxs-lookup"><span data-stu-id="d9a43-138">This example shows the XML elements that define three rows of the list view.</span></span> <span data-ttu-id="d9a43-139">В первых двух строках отображается значение свойства .NET, а в последней строке — значение, созданное сценарием.</span><span class="sxs-lookup"><span data-stu-id="d9a43-139">The first two rows display the value of a .NET property, and the last row displays a value generated by a script.</span></span>

```xml
<ListEntry>
    <ListItems>
      <ListItem>
        <Label>Property1: </Label>
        <PropertyName>DotNetProperty1</PropertyName>
      </ListItem>
      <ListItem>
        <PropertyName>DotNetProperty2</PropertyName>
      </ListItem>
      <ListItem>
        <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
      </ListItem>
    </ListItems>
</ListEntry>

```

## <a name="see-also"></a><span data-ttu-id="d9a43-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="d9a43-140">See Also</span></span>

[<span data-ttu-id="d9a43-141">Элемент ListItems (формат)</span><span class="sxs-lookup"><span data-stu-id="d9a43-141">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="d9a43-142">Элемент FormatString для ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="d9a43-142">FormatString Element for ListItem (Format)</span></span>](./formatstring-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="d9a43-143">Элемент Label для ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="d9a43-143">Label Element for ListItem (Format)</span></span>](./label-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="d9a43-144">Элемент PropertyName для ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="d9a43-144">PropertyName Element for ListItem (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="d9a43-145">Элемент ScriptBlock для ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="d9a43-145">ScriptBlock Element for ListItem (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="d9a43-146">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="d9a43-146">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="d9a43-147">Создание файла форматирования и типов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d9a43-147">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
