---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент PropertyName для элемента ListItem для элемента ListControl (формат)
description: Элемент PropertyName для элемента ListItem для элемента ListControl (формат)
ms.openlocfilehash: 30cd48f9549e1a091776cd5f8395e1a71314ea1b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665980"
---
# <a name="propertyname-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="8927f-103">Элемент PropertyName для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="8927f-103">PropertyName Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="8927f-104">Указывает свойство .NET, значение которого отображается в списке.</span><span class="sxs-lookup"><span data-stu-id="8927f-104">Specifies the .NET property whose value is displayed in the list.</span></span>

<span data-ttu-id="8927f-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент (Format) элемент списка ListItem (Format) элемент "PropertyName" (Format) ИмяСвойства Element для ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="8927f-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) ListItems Element (Format) ListItem Element (Format) PropertyName Element for ListItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8927f-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8927f-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8927f-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8927f-107">Attributes and Elements</span></span>

<span data-ttu-id="8927f-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.</span><span class="sxs-lookup"><span data-stu-id="8927f-108">The following sections describe the attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8927f-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8927f-109">Attributes</span></span>

<span data-ttu-id="8927f-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8927f-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8927f-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8927f-111">Child Elements</span></span>

<span data-ttu-id="8927f-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8927f-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8927f-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8927f-113">Parent Elements</span></span>

|<span data-ttu-id="8927f-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="8927f-114">Element</span></span>|<span data-ttu-id="8927f-115">Описание</span><span class="sxs-lookup"><span data-stu-id="8927f-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8927f-116">Элемент ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="8927f-116">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="8927f-117">Определяет свойство или скрипт, значение которого отображается в строке представления списка.</span><span class="sxs-lookup"><span data-stu-id="8927f-117">Defines the property or script whose value is displayed in the row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="8927f-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="8927f-118">Text Value</span></span>

<span data-ttu-id="8927f-119">Укажите имя свойства, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="8927f-119">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="8927f-120">Комментарии</span><span class="sxs-lookup"><span data-stu-id="8927f-120">Remarks</span></span>

<span data-ttu-id="8927f-121">Если этот элемент указан, нельзя указать элемент [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) .</span><span class="sxs-lookup"><span data-stu-id="8927f-121">When this element is specified, you cannot specify the [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element.</span></span>

<span data-ttu-id="8927f-122">В дополнение к отображению значения свойства можно также указать метку для значения или строку формата, которую можно использовать для изменения отображения значения.</span><span class="sxs-lookup"><span data-stu-id="8927f-122">In addition to displaying the property value, you can also specify a label for the value or a format string that can be used to change the display of the value.</span></span> <span data-ttu-id="8927f-123">Дополнительные сведения об указании данных в представлении списка см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="8927f-123">For more information about specifying data in a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="8927f-124">Пример</span><span class="sxs-lookup"><span data-stu-id="8927f-124">Example</span></span>

<span data-ttu-id="8927f-125">В следующем примере показано, как указать метку и свойство, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="8927f-125">The following example shows how to specify the label and property whose value is displayed.</span></span>

```xml
ListItem>
  <Label>NameOfProperty</Label>
  <PropertyName>.NetTypeProperty</PropertyName>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="8927f-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="8927f-126">See Also</span></span>

[<span data-ttu-id="8927f-127">Элемент ScriptBlock для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="8927f-127">ScriptBlock Element for ListItem for ListControl (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="8927f-128">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="8927f-128">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="8927f-129">Элемент ListItem для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="8927f-129">ListItem Element for ListControl(Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="8927f-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="8927f-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
