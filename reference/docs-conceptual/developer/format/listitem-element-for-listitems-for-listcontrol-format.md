---
title: Элемент ListItem для элементов ListItem для ListControl (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: e72a887e8bd1f93bacb663e3079eeaec34bdfa51
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785682"
---
# <a name="listitem-element-for-listitems-for-listcontrol-format"></a><span data-ttu-id="a56ac-102">Элемент ListItem для элемента ListItems для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="a56ac-102">ListItem Element for ListItems for ListControl (Format)</span></span>

<span data-ttu-id="a56ac-103">Определяет свойство или скрипт, значение которого отображается в строке представления списка.</span><span class="sxs-lookup"><span data-stu-id="a56ac-103">Defines the property or script whose value is displayed in a row of the list view.</span></span>

<span data-ttu-id="a56ac-104">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес для ListControl (Format) Листентри элемент для ListControl (Format) элемент списка элементов для ListControl (Format) для элемента (формат)</span><span class="sxs-lookup"><span data-stu-id="a56ac-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format) ListItem for ListControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a56ac-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a56ac-105">Syntax</span></span>

```xml
<ListItem>
  <PropertyName>PropertyToDisplay</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <Label>LabelToDisplay</Label>
  <FormatString>FormatPattern</FormatString>
  <ItemSelectionCondition>...</ItemSelectionCondition>
</ListItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a56ac-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a56ac-106">Attributes and Elements</span></span>

<span data-ttu-id="a56ac-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ListItem` элемента.</span><span class="sxs-lookup"><span data-stu-id="a56ac-107">The following sections describe the attributes, child elements, and parent element of the `ListItem` element.</span></span> <span data-ttu-id="a56ac-108">Можно указать только одно свойство или скрипт.</span><span class="sxs-lookup"><span data-stu-id="a56ac-108">Only one property or script can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="a56ac-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a56ac-109">Attributes</span></span>

<span data-ttu-id="a56ac-110">Нет</span><span class="sxs-lookup"><span data-stu-id="a56ac-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="a56ac-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a56ac-111">Child Elements</span></span>

|<span data-ttu-id="a56ac-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="a56ac-112">Element</span></span>|<span data-ttu-id="a56ac-113">Описание</span><span class="sxs-lookup"><span data-stu-id="a56ac-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a56ac-114">Элемент FormatString для ListItem для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="a56ac-114">FormatString Element for ListItem for ListControl (Format)</span></span>](./formatstring-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="a56ac-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="a56ac-115">Optional element.</span></span><br /><br /> <span data-ttu-id="a56ac-116">Задает строку формата, определяющую способ отображения значения свойства или скрипта.</span><span class="sxs-lookup"><span data-stu-id="a56ac-116">Specifies a format string that defines how the property or script value is displayed.</span></span>|
|[<span data-ttu-id="a56ac-117">Элемент ItemSelectionCondition для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="a56ac-117">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="a56ac-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="a56ac-118">Optional element.</span></span><br /><br /> <span data-ttu-id="a56ac-119">Определяет условие, которое должно существовать для использования этого элемента списка.</span><span class="sxs-lookup"><span data-stu-id="a56ac-119">Defines the condition that must exist for this list item to be used.</span></span>|
|[<span data-ttu-id="a56ac-120">Элемент Label для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="a56ac-120">Label Element for ListItem for ListControl (Format)</span></span>](./label-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="a56ac-121">Необязательный элемент</span><span class="sxs-lookup"><span data-stu-id="a56ac-121">Optional element</span></span><br /><br /> <span data-ttu-id="a56ac-122">Задает метку, которая отображается слева от значения свойства или скрипта в строке.</span><span class="sxs-lookup"><span data-stu-id="a56ac-122">Specifies the label that is displayed to the left of the property or script value in the row.</span></span>|
|[<span data-ttu-id="a56ac-123">Элемент PropertyName для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="a56ac-123">PropertyName Element for ListItem for ListControl (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="a56ac-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="a56ac-124">Optional element.</span></span><br /><br /> <span data-ttu-id="a56ac-125">Указывает свойство .NET, значение которого отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="a56ac-125">Specifies the .NET property whose value is displayed in the row.</span></span>|
|[<span data-ttu-id="a56ac-126">Элемент ScriptBlock для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="a56ac-126">ScriptBlock Element for ListItem for ListControl (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="a56ac-127">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="a56ac-127">Optional element.</span></span><br /><br /> <span data-ttu-id="a56ac-128">Указывает скрипт, значение которого отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="a56ac-128">Specifies the script whose value is displayed in the row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a56ac-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a56ac-129">Parent Elements</span></span>

|<span data-ttu-id="a56ac-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="a56ac-130">Element</span></span>|<span data-ttu-id="a56ac-131">Описание</span><span class="sxs-lookup"><span data-stu-id="a56ac-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a56ac-132">Элемент ListItems для элемента управления "список" (формат)</span><span class="sxs-lookup"><span data-stu-id="a56ac-132">ListItems Element for List Control (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="a56ac-133">Определяет свойства и скрипты, значения которых отображаются в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="a56ac-133">Defines the properties and scripts whose values are displayed in the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a56ac-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="a56ac-134">Remarks</span></span>

<span data-ttu-id="a56ac-135">Дополнительные сведения о компонентах представления списка см. [в разделе Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="a56ac-135">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="a56ac-136">Пример</span><span class="sxs-lookup"><span data-stu-id="a56ac-136">Example</span></span>

<span data-ttu-id="a56ac-137">В этом примере показаны XML-элементы, определяющие три строки представления списка.</span><span class="sxs-lookup"><span data-stu-id="a56ac-137">This example shows the XML elements that define three rows of the list view.</span></span> <span data-ttu-id="a56ac-138">В первых двух строках отображается значение свойства .NET, а в последней строке — значение, созданное сценарием.</span><span class="sxs-lookup"><span data-stu-id="a56ac-138">The first two rows display the value of a .NET property, and the last row displays a value generated by a script.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="a56ac-139">См. также</span><span class="sxs-lookup"><span data-stu-id="a56ac-139">See Also</span></span>

[<span data-ttu-id="a56ac-140">Элемент ListItems (формат)</span><span class="sxs-lookup"><span data-stu-id="a56ac-140">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="a56ac-141">Элемент FormatString для ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="a56ac-141">FormatString Element for ListItem (Format)</span></span>](./formatstring-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="a56ac-142">Элемент Label для ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="a56ac-142">Label Element for ListItem (Format)</span></span>](./label-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="a56ac-143">Элемент PropertyName для ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="a56ac-143">PropertyName Element for ListItem (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="a56ac-144">Элемент ScriptBlock для ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="a56ac-144">ScriptBlock Element for ListItem (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="a56ac-145">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="a56ac-145">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="a56ac-146">Создание файла форматирования и типов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a56ac-146">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
