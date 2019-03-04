---
title: Элемент ScriptBlock для ListItem для ListControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 74e30938-00ef-46fd-84e5-f0a83706a50e
caps.latest.revision: 11
ms.openlocfilehash: 76b600256af3f957f7fe0578f9fef810262aa5d5
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855560"
---
# <a name="scriptblock-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="a1c84-102">Элемент ScriptBlock для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="a1c84-102">ScriptBlock Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="a1c84-103">Указывает сценарий, значение которого отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="a1c84-103">Specifies the script whose value is displayed in the row.</span></span>

<span data-ttu-id="a1c84-104">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемента ListControl (формат) ListEntries элемента конфигурации для элемента ListControl (формат) ListEntry ListEntries для элемента ListControl (формат) ListItems ListEntry для элемента ListControl (формат) ListItem ListItems элемента ListControl (формат) ScriptBlock для ListItem для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="a1c84-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ScriptBlock Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a1c84-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a1c84-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a1c84-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a1c84-106">Attributes and Elements</span></span>

<span data-ttu-id="a1c84-107">В следующих разделах атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемент.</span><span class="sxs-lookup"><span data-stu-id="a1c84-107">The following sections describe the attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a1c84-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a1c84-108">Attributes</span></span>

<span data-ttu-id="a1c84-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="a1c84-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a1c84-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a1c84-110">Child Elements</span></span>

<span data-ttu-id="a1c84-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="a1c84-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a1c84-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a1c84-112">Parent Elements</span></span>

|<span data-ttu-id="a1c84-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="a1c84-113">Element</span></span>|<span data-ttu-id="a1c84-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a1c84-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a1c84-115">Элемент ListItem (формат)</span><span class="sxs-lookup"><span data-stu-id="a1c84-115">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="a1c84-116">Определяет свойство или скрипта, значение которого отображается в строке в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="a1c84-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a1c84-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="a1c84-117">Text Value</span></span>

<span data-ttu-id="a1c84-118">Укажите сценарий, значение которого отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="a1c84-118">Specify the script whose value is displayed in the row.</span></span>

## <a name="remarks"></a><span data-ttu-id="a1c84-119">Замечания</span><span class="sxs-lookup"><span data-stu-id="a1c84-119">Remarks</span></span>

<span data-ttu-id="a1c84-120">Если этот элемент указан, нельзя указать [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="a1c84-120">When this element is specified, you cannot specify the [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element.</span></span>

<span data-ttu-id="a1c84-121">Дополнительные сведения об указании скриптов в виде списка, см. в разделе [представление списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="a1c84-121">For more information about specifying scripts in a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="a1c84-122">Пример</span><span class="sxs-lookup"><span data-stu-id="a1c84-122">Example</span></span>

<span data-ttu-id="a1c84-123">В следующем примере показано, как задано свойство, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="a1c84-123">The following example shows how to specify the property whose value is displayed.</span></span>

```xml
<ListItem>
  <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="a1c84-124">См. также</span><span class="sxs-lookup"><span data-stu-id="a1c84-124">See Also</span></span>

[<span data-ttu-id="a1c84-125">PropertyName элемент ListItem для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="a1c84-125">PropertyName Element for ListItem for ListControl (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="a1c84-126">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="a1c84-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="a1c84-127">Элемент ListItem для ListItems для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="a1c84-127">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="a1c84-128">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="a1c84-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
