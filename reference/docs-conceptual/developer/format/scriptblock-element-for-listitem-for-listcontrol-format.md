---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ScriptBlock для элемента ListItem для элемента ListControl (формат)
description: Элемент ScriptBlock для элемента ListItem для элемента ListControl (формат)
ms.openlocfilehash: 0635ac2622cc203a2dc895873621901d956f87da
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664969"
---
# <a name="scriptblock-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="a4917-103">Элемент ScriptBlock для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="a4917-103">ScriptBlock Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="a4917-104">Указывает скрипт, значение которого отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="a4917-104">Specifies the script whose value is displayed in the row.</span></span>

<span data-ttu-id="a4917-105">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (формат) ListControl элемент (Format) Листентриес для ListControl (Format) Листентри элемент для Листентриес в ListControl (Format) элемент ListItem для листентри для элемента списка элементов ListControl в ListControl (Format).</span><span class="sxs-lookup"><span data-stu-id="a4917-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ScriptBlock Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a4917-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a4917-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a4917-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a4917-107">Attributes and Elements</span></span>

<span data-ttu-id="a4917-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемента.</span><span class="sxs-lookup"><span data-stu-id="a4917-108">The following sections describe the attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a4917-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a4917-109">Attributes</span></span>

<span data-ttu-id="a4917-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a4917-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a4917-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a4917-111">Child Elements</span></span>

<span data-ttu-id="a4917-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a4917-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a4917-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a4917-113">Parent Elements</span></span>

|<span data-ttu-id="a4917-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="a4917-114">Element</span></span>|<span data-ttu-id="a4917-115">Описание</span><span class="sxs-lookup"><span data-stu-id="a4917-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a4917-116">Элемент ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="a4917-116">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="a4917-117">Определяет свойство или скрипт, значение которого отображается в строке представления списка.</span><span class="sxs-lookup"><span data-stu-id="a4917-117">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a4917-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="a4917-118">Text Value</span></span>

<span data-ttu-id="a4917-119">Укажите скрипт, значение которого отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="a4917-119">Specify the script whose value is displayed in the row.</span></span>

## <a name="remarks"></a><span data-ttu-id="a4917-120">Комментарии</span><span class="sxs-lookup"><span data-stu-id="a4917-120">Remarks</span></span>

<span data-ttu-id="a4917-121">Если этот элемент указан, нельзя указать элемент [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) .</span><span class="sxs-lookup"><span data-stu-id="a4917-121">When this element is specified, you cannot specify the [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element.</span></span>

<span data-ttu-id="a4917-122">Дополнительные сведения об указании скриптов в представлении списка см. в разделе [представление списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="a4917-122">For more information about specifying scripts in a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="a4917-123">Пример</span><span class="sxs-lookup"><span data-stu-id="a4917-123">Example</span></span>

<span data-ttu-id="a4917-124">В следующем примере показано, как указать свойство, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="a4917-124">The following example shows how to specify the property whose value is displayed.</span></span>

```xml
<ListItem>
  <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="a4917-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="a4917-125">See Also</span></span>

[<span data-ttu-id="a4917-126">Элемент PropertyName для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="a4917-126">PropertyName Element for ListItem for ListControl (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="a4917-127">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="a4917-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="a4917-128">Элемент ListItem для элемента ListItems для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="a4917-128">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="a4917-129">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="a4917-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
