---
title: Элемент ScriptBlock для ListItem для ListControl (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 74e30938-00ef-46fd-84e5-f0a83706a50e
caps.latest.revision: 11
ms.openlocfilehash: 76b600256af3f957f7fe0578f9fef810262aa5d5
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364813"
---
# <a name="scriptblock-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="a8123-102">Элемент ScriptBlock для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="a8123-102">ScriptBlock Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="a8123-103">Указывает скрипт, значение которого отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="a8123-103">Specifies the script whose value is displayed in the row.</span></span>

<span data-ttu-id="a8123-104">Элемент Configuration (Format) Виевдефинитионс элемент представления (Format) элемент ListControl (Format) элемент Листентриес для ListControl (Format) Листентри для Листентриес для ListControl (Format) элемент ListItems для Листентри для ListControl (Format) элемент ListItem для элементов ListItem для ListControl (Format) элемент ScriptBlock для элемента ListItem для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="a8123-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ScriptBlock Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a8123-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a8123-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a8123-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a8123-106">Attributes and Elements</span></span>

<span data-ttu-id="a8123-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `ScriptBlock`.</span><span class="sxs-lookup"><span data-stu-id="a8123-107">The following sections describe the attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a8123-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a8123-108">Attributes</span></span>

<span data-ttu-id="a8123-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="a8123-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a8123-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a8123-110">Child Elements</span></span>

<span data-ttu-id="a8123-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="a8123-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a8123-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a8123-112">Parent Elements</span></span>

|<span data-ttu-id="a8123-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="a8123-113">Element</span></span>|<span data-ttu-id="a8123-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a8123-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a8123-115">Элемент ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="a8123-115">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="a8123-116">Определяет свойство или скрипт, значение которого отображается в строке представления списка.</span><span class="sxs-lookup"><span data-stu-id="a8123-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a8123-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="a8123-117">Text Value</span></span>

<span data-ttu-id="a8123-118">Укажите скрипт, значение которого отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="a8123-118">Specify the script whose value is displayed in the row.</span></span>

## <a name="remarks"></a><span data-ttu-id="a8123-119">Замечания</span><span class="sxs-lookup"><span data-stu-id="a8123-119">Remarks</span></span>

<span data-ttu-id="a8123-120">Если этот элемент указан, нельзя указать элемент [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) .</span><span class="sxs-lookup"><span data-stu-id="a8123-120">When this element is specified, you cannot specify the [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element.</span></span>

<span data-ttu-id="a8123-121">Дополнительные сведения об указании скриптов в представлении списка см. в разделе [представление списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="a8123-121">For more information about specifying scripts in a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="a8123-122">Пример</span><span class="sxs-lookup"><span data-stu-id="a8123-122">Example</span></span>

<span data-ttu-id="a8123-123">В следующем примере показано, как указать свойство, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="a8123-123">The following example shows how to specify the property whose value is displayed.</span></span>

```xml
<ListItem>
  <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="a8123-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="a8123-124">See Also</span></span>

[<span data-ttu-id="a8123-125">Элемент PropertyName для ListItem для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="a8123-125">PropertyName Element for ListItem for ListControl (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="a8123-126">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="a8123-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="a8123-127">Элемент ListItem для элементов ListItem для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="a8123-127">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="a8123-128">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="a8123-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
