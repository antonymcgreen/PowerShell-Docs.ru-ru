---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент Label для элемента ListItem для элемента ListControl (формат)
description: Элемент Label для элемента ListItem для элемента ListControl (формат)
ms.openlocfilehash: 01ff34c4129abe2c76a0a21794e756b77bff12bf
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666660"
---
# <a name="label-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="987a7-103">Элемент Label для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="987a7-103">Label Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="987a7-104">Задает метку, которая отображается слева от значения свойства или скрипта в строке.</span><span class="sxs-lookup"><span data-stu-id="987a7-104">Specifies the label that is displayed to the left of the property or script value in the row.</span></span>

<span data-ttu-id="987a7-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес для ListControl (Format) Листентри элемент для элементов ListItem в ListControl (формат) для листентри (Format) элемент ListItem для элементов ListItem для ListControl (Format) элемент Label для элемента SPListItem для ListControl (Format).</span><span class="sxs-lookup"><span data-stu-id="987a7-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems for ListEntry for ListControl Element (Format) ListItem Element for ListItems for ListControl (Format) Label Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="987a7-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="987a7-106">Syntax</span></span>

```xml
<Label>Label for displayed value</Label>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="987a7-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="987a7-107">Attributes and Elements</span></span>

<span data-ttu-id="987a7-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Label` элемента.</span><span class="sxs-lookup"><span data-stu-id="987a7-108">The following sections describe the attributes, child elements, and the parent element of the `Label` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="987a7-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="987a7-109">Attributes</span></span>

<span data-ttu-id="987a7-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="987a7-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="987a7-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="987a7-111">Child Elements</span></span>

<span data-ttu-id="987a7-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="987a7-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="987a7-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="987a7-113">Parent Elements</span></span>

|<span data-ttu-id="987a7-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="987a7-114">Element</span></span>|<span data-ttu-id="987a7-115">Описание</span><span class="sxs-lookup"><span data-stu-id="987a7-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="987a7-116">Элемент ListItem для элемента ListItems для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="987a7-116">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="987a7-117">Определяет свойство или скрипт, значение которого отображается в строке представления списка.</span><span class="sxs-lookup"><span data-stu-id="987a7-117">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="987a7-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="987a7-118">Text Value</span></span>

<span data-ttu-id="987a7-119">Укажите метку, которая будет отображаться слева от значения свойства или скрипта.</span><span class="sxs-lookup"><span data-stu-id="987a7-119">Specify the label to be display to the left of the property or script value.</span></span>

## <a name="remarks"></a><span data-ttu-id="987a7-120">Комментарии</span><span class="sxs-lookup"><span data-stu-id="987a7-120">Remarks</span></span>

<span data-ttu-id="987a7-121">Если метка не указана, отображается имя свойства или скрипт.</span><span class="sxs-lookup"><span data-stu-id="987a7-121">If a label is not specified, the name of the property or the script is displayed.</span></span> <span data-ttu-id="987a7-122">Дополнительные сведения об использовании меток в представлении списка см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="987a7-122">For more information about using labels in a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="987a7-123">Пример</span><span class="sxs-lookup"><span data-stu-id="987a7-123">Example</span></span>

<span data-ttu-id="987a7-124">В следующем примере показано, как добавить метку к строке.</span><span class="sxs-lookup"><span data-stu-id="987a7-124">The following example shows how to add a label to a row.</span></span>

```xml
<ListItem>
  <Label>Property1: </Label>
  <PropertyName>DotNetProperty1</PropertyName>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="987a7-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="987a7-125">See Also</span></span>

[<span data-ttu-id="987a7-126">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="987a7-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="987a7-127">Элемент ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="987a7-127">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="987a7-128">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="987a7-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
