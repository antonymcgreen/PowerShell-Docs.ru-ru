---
title: Элемент ListItem для ListItems для ListControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f96f4f5-8bd5-43ed-95e7-a7358115999a
caps.latest.revision: 11
ms.openlocfilehash: 1e0a1b2d20853650328b8cfd1513a08f7e167cd6
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855160"
---
# <a name="listitem-element-for-listitems-for-listcontrol-format"></a><span data-ttu-id="925f3-102">Элемент ListItem для элемента ListItems для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="925f3-102">ListItem Element for ListItems for ListControl (Format)</span></span>

<span data-ttu-id="925f3-103">Определяет свойство или скрипта, значение которого отображается в строке в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="925f3-103">Defines the property or script whose value is displayed in a row of the list view.</span></span>

<span data-ttu-id="925f3-104">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемента ListControl (формат) ListEntries элемента конфигурации для элемента ListEntry ListControl (формат) для элемента ListControl (формат) ListItems ListControl (формат) ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="925f3-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format) ListItem for ListControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="925f3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="925f3-105">Syntax</span></span>

```xml
<ListItem>
  <PropertyName>PropertyToDisplay</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <Label>LabelToDisplay</Label>
  <FormatString>FormatPattern</FormatString>
  <ItemSelectionCondition>...</ItemSelectionCondition>
</ListItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="925f3-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="925f3-106">Attributes and Elements</span></span>

<span data-ttu-id="925f3-107">В следующих разделах атрибуты, дочерние элементы и родительский элемент `ListItem` элемент.</span><span class="sxs-lookup"><span data-stu-id="925f3-107">The following sections describe the attributes, child elements, and parent element of the `ListItem` element.</span></span> <span data-ttu-id="925f3-108">Можно указать только одно свойство или скрипт.</span><span class="sxs-lookup"><span data-stu-id="925f3-108">Only one property or script can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="925f3-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="925f3-109">Attributes</span></span>

<span data-ttu-id="925f3-110">Нет</span><span class="sxs-lookup"><span data-stu-id="925f3-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="925f3-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="925f3-111">Child Elements</span></span>

|<span data-ttu-id="925f3-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="925f3-112">Element</span></span>|<span data-ttu-id="925f3-113">Описание</span><span class="sxs-lookup"><span data-stu-id="925f3-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="925f3-114">Элемент FormatString для ListItem для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="925f3-114">FormatString Element for ListItem for ListControl (Format)</span></span>](./formatstring-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="925f3-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="925f3-115">Optional element.</span></span><br /><br /> <span data-ttu-id="925f3-116">Задает строку формата, который определяет способ отображения значения свойства или скрипт.</span><span class="sxs-lookup"><span data-stu-id="925f3-116">Specifies a format string that defines how the property or script value is displayed.</span></span>|
|[<span data-ttu-id="925f3-117">Элемент ItemSelectionCondition для ListItem для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="925f3-117">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="925f3-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="925f3-118">Optional element.</span></span><br /><br /> <span data-ttu-id="925f3-119">Определяет условие, которое должен существовать для данного элемента списка для использования.</span><span class="sxs-lookup"><span data-stu-id="925f3-119">Defines the condition that must exist for this list item to be used.</span></span>|
|[<span data-ttu-id="925f3-120">Элемент Label для ListItem для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="925f3-120">Label Element for ListItem for ListControl (Format)</span></span>](./label-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="925f3-121">Необязательный элемент</span><span class="sxs-lookup"><span data-stu-id="925f3-121">Optional element</span></span><br /><br /> <span data-ttu-id="925f3-122">Указывает метку, которая отображается слева от значения свойства или сценарий, в строке.</span><span class="sxs-lookup"><span data-stu-id="925f3-122">Specifies the label that is displayed to the left of the property or script value in the row.</span></span>|
|[<span data-ttu-id="925f3-123">PropertyName элемент ListItem для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="925f3-123">PropertyName Element for ListItem for ListControl (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="925f3-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="925f3-124">Optional element.</span></span><br /><br /> <span data-ttu-id="925f3-125">Задает свойство .NET, значение которого отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="925f3-125">Specifies the .NET property whose value is displayed in the row.</span></span>|
|[<span data-ttu-id="925f3-126">Элемент ScriptBlock для ListItem для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="925f3-126">ScriptBlock Element for ListItem for ListControl (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="925f3-127">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="925f3-127">Optional element.</span></span><br /><br /> <span data-ttu-id="925f3-128">Указывает сценарий, значение которого отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="925f3-128">Specifies the script whose value is displayed in the row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="925f3-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="925f3-129">Parent Elements</span></span>

|<span data-ttu-id="925f3-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="925f3-130">Element</span></span>|<span data-ttu-id="925f3-131">Описание</span><span class="sxs-lookup"><span data-stu-id="925f3-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="925f3-132">ListItems элемент управления "список" (формат)</span><span class="sxs-lookup"><span data-stu-id="925f3-132">ListItems Element for List Control (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="925f3-133">Определяет свойства и скрипты, значения которых отображаются в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="925f3-133">Defines the properties and scripts whose values are displayed in the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="925f3-134">Замечания</span><span class="sxs-lookup"><span data-stu-id="925f3-134">Remarks</span></span>

<span data-ttu-id="925f3-135">Дополнительные сведения о компонентах представления списка, см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="925f3-135">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="925f3-136">Пример</span><span class="sxs-lookup"><span data-stu-id="925f3-136">Example</span></span>

<span data-ttu-id="925f3-137">В этом примере показаны элементы XML, которые определяют три строки в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="925f3-137">This example shows the XML elements that define three rows of the list view.</span></span> <span data-ttu-id="925f3-138">Первые две строки отображения значения свойства .NET, а последняя строка выводит значение, созданные с помощью сценария.</span><span class="sxs-lookup"><span data-stu-id="925f3-138">The first two rows display the value of a .NET property, and the last row displays a value generated by a script.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="925f3-139">См. также</span><span class="sxs-lookup"><span data-stu-id="925f3-139">See Also</span></span>

[<span data-ttu-id="925f3-140">Элемент ListItems (формат)</span><span class="sxs-lookup"><span data-stu-id="925f3-140">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="925f3-141">Элемент FormatString для ListItem (формат)</span><span class="sxs-lookup"><span data-stu-id="925f3-141">FormatString Element for ListItem (Format)</span></span>](./formatstring-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="925f3-142">Элемент Label для ListItem (формат)</span><span class="sxs-lookup"><span data-stu-id="925f3-142">Label Element for ListItem (Format)</span></span>](./label-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="925f3-143">PropertyName элемент ListItem (формат)</span><span class="sxs-lookup"><span data-stu-id="925f3-143">PropertyName Element for ListItem (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="925f3-144">Элемент ScriptBlock для ListItem (формат)</span><span class="sxs-lookup"><span data-stu-id="925f3-144">ScriptBlock Element for ListItem (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="925f3-145">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="925f3-145">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="925f3-146">Написание форматирования Windows PowerShell и типы файлов</span><span class="sxs-lookup"><span data-stu-id="925f3-146">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
