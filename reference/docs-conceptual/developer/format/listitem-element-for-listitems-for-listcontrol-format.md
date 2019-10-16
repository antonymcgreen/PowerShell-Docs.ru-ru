---
title: Элемент ListItem для элементов ListItem для ListControl (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f96f4f5-8bd5-43ed-95e7-a7358115999a
caps.latest.revision: 11
ms.openlocfilehash: 1e0a1b2d20853650328b8cfd1513a08f7e167cd6
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365133"
---
# <a name="listitem-element-for-listitems-for-listcontrol-format"></a><span data-ttu-id="52a00-102">Элемент ListItem для элемента ListItems для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="52a00-102">ListItem Element for ListItems for ListControl (Format)</span></span>

<span data-ttu-id="52a00-103">Определяет свойство или скрипт, значение которого отображается в строке представления списка.</span><span class="sxs-lookup"><span data-stu-id="52a00-103">Defines the property or script whose value is displayed in a row of the list view.</span></span>

<span data-ttu-id="52a00-104">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес для ListControl (Format) Листентри элемента для ListControl (Format) элемент ListItems для ListControl (Format) Элемент ListItem для элемента ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="52a00-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format) ListItem for ListControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="52a00-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52a00-105">Syntax</span></span>

```xml
<ListItem>
  <PropertyName>PropertyToDisplay</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <Label>LabelToDisplay</Label>
  <FormatString>FormatPattern</FormatString>
  <ItemSelectionCondition>...</ItemSelectionCondition>
</ListItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="52a00-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="52a00-106">Attributes and Elements</span></span>

<span data-ttu-id="52a00-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `ListItem`.</span><span class="sxs-lookup"><span data-stu-id="52a00-107">The following sections describe the attributes, child elements, and parent element of the `ListItem` element.</span></span> <span data-ttu-id="52a00-108">Можно указать только одно свойство или скрипт.</span><span class="sxs-lookup"><span data-stu-id="52a00-108">Only one property or script can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="52a00-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="52a00-109">Attributes</span></span>

<span data-ttu-id="52a00-110">Нет</span><span class="sxs-lookup"><span data-stu-id="52a00-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="52a00-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="52a00-111">Child Elements</span></span>

|<span data-ttu-id="52a00-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="52a00-112">Element</span></span>|<span data-ttu-id="52a00-113">Описание</span><span class="sxs-lookup"><span data-stu-id="52a00-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="52a00-114">Элемент FormatString для ListItem для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="52a00-114">FormatString Element for ListItem for ListControl (Format)</span></span>](./formatstring-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="52a00-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="52a00-115">Optional element.</span></span><br /><br /> <span data-ttu-id="52a00-116">Задает строку формата, определяющую способ отображения значения свойства или скрипта.</span><span class="sxs-lookup"><span data-stu-id="52a00-116">Specifies a format string that defines how the property or script value is displayed.</span></span>|
|[<span data-ttu-id="52a00-117">Элемент Итемселектионкондитион для ListItem для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="52a00-117">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="52a00-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="52a00-118">Optional element.</span></span><br /><br /> <span data-ttu-id="52a00-119">Определяет условие, которое должно существовать для использования этого элемента списка.</span><span class="sxs-lookup"><span data-stu-id="52a00-119">Defines the condition that must exist for this list item to be used.</span></span>|
|[<span data-ttu-id="52a00-120">Элемент Label для ListItem для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="52a00-120">Label Element for ListItem for ListControl (Format)</span></span>](./label-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="52a00-121">Необязательный элемент</span><span class="sxs-lookup"><span data-stu-id="52a00-121">Optional element</span></span><br /><br /> <span data-ttu-id="52a00-122">Задает метку, которая отображается слева от значения свойства или скрипта в строке.</span><span class="sxs-lookup"><span data-stu-id="52a00-122">Specifies the label that is displayed to the left of the property or script value in the row.</span></span>|
|[<span data-ttu-id="52a00-123">Элемент PropertyName для ListItem для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="52a00-123">PropertyName Element for ListItem for ListControl (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="52a00-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="52a00-124">Optional element.</span></span><br /><br /> <span data-ttu-id="52a00-125">Указывает свойство .NET, значение которого отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="52a00-125">Specifies the .NET property whose value is displayed in the row.</span></span>|
|[<span data-ttu-id="52a00-126">Элемент ScriptBlock для ListItem для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="52a00-126">ScriptBlock Element for ListItem for ListControl (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="52a00-127">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="52a00-127">Optional element.</span></span><br /><br /> <span data-ttu-id="52a00-128">Указывает скрипт, значение которого отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="52a00-128">Specifies the script whose value is displayed in the row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="52a00-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="52a00-129">Parent Elements</span></span>

|<span data-ttu-id="52a00-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="52a00-130">Element</span></span>|<span data-ttu-id="52a00-131">Описание</span><span class="sxs-lookup"><span data-stu-id="52a00-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="52a00-132">Элемент ListItems для элемента управления "список" (формат)</span><span class="sxs-lookup"><span data-stu-id="52a00-132">ListItems Element for List Control (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="52a00-133">Определяет свойства и скрипты, значения которых отображаются в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="52a00-133">Defines the properties and scripts whose values are displayed in the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="52a00-134">Замечания</span><span class="sxs-lookup"><span data-stu-id="52a00-134">Remarks</span></span>

<span data-ttu-id="52a00-135">Дополнительные сведения о компонентах представления списка см. [в разделе Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="52a00-135">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="52a00-136">Пример</span><span class="sxs-lookup"><span data-stu-id="52a00-136">Example</span></span>

<span data-ttu-id="52a00-137">В этом примере показаны XML-элементы, определяющие три строки представления списка.</span><span class="sxs-lookup"><span data-stu-id="52a00-137">This example shows the XML elements that define three rows of the list view.</span></span> <span data-ttu-id="52a00-138">В первых двух строках отображается значение свойства .NET, а в последней строке — значение, созданное сценарием.</span><span class="sxs-lookup"><span data-stu-id="52a00-138">The first two rows display the value of a .NET property, and the last row displays a value generated by a script.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="52a00-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="52a00-139">See Also</span></span>

[<span data-ttu-id="52a00-140">Элемент ListItems (формат)</span><span class="sxs-lookup"><span data-stu-id="52a00-140">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="52a00-141">Элемент FormatString для ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="52a00-141">FormatString Element for ListItem (Format)</span></span>](./formatstring-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="52a00-142">Элемент Label для ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="52a00-142">Label Element for ListItem (Format)</span></span>](./label-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="52a00-143">Элемент PropertyName для ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="52a00-143">PropertyName Element for ListItem (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="52a00-144">Элемент ScriptBlock для ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="52a00-144">ScriptBlock Element for ListItem (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="52a00-145">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="52a00-145">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="52a00-146">Создание файла форматирования и типов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="52a00-146">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
