---
title: Элемент Label для ListItem для ListControl (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c693ff46-d1ad-4dc7-93ac-41ff2fc6c103
caps.latest.revision: 9
ms.openlocfilehash: c1293d5a1f942704ac01388c66bd9009fd340e82
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362893"
---
# <a name="label-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="ae329-102">Элемент Label для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="ae329-102">Label Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="ae329-103">Задает метку, которая отображается слева от значения свойства или скрипта в строке.</span><span class="sxs-lookup"><span data-stu-id="ae329-103">Specifies the label that is displayed to the left of the property or script value in the row.</span></span>

<span data-ttu-id="ae329-104">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент ListControl (Format) элемент Листентриес для ListControl (Format) Листентри для элемента ListControl (Format) для листентри в элементе ListControl ( Format) элемент ListItem для элементов ListItem для элемента ListControl (Format) Метки для ListItem для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ae329-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems for ListEntry for ListControl Element (Format) ListItem Element for ListItems for ListControl (Format) Label Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ae329-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ae329-105">Syntax</span></span>

```xml
<Label>Label for displayed value</Label>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ae329-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ae329-106">Attributes and Elements</span></span>

<span data-ttu-id="ae329-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `Label`.</span><span class="sxs-lookup"><span data-stu-id="ae329-107">The following sections describe the attributes, child elements, and the parent element of the `Label` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ae329-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ae329-108">Attributes</span></span>

<span data-ttu-id="ae329-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="ae329-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ae329-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ae329-110">Child Elements</span></span>

<span data-ttu-id="ae329-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="ae329-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ae329-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ae329-112">Parent Elements</span></span>

|<span data-ttu-id="ae329-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="ae329-113">Element</span></span>|<span data-ttu-id="ae329-114">Описание</span><span class="sxs-lookup"><span data-stu-id="ae329-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ae329-115">Элемент ListItem для элементов ListItem для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ae329-115">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="ae329-116">Определяет свойство или скрипт, значение которого отображается в строке представления списка.</span><span class="sxs-lookup"><span data-stu-id="ae329-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ae329-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="ae329-117">Text Value</span></span>

<span data-ttu-id="ae329-118">Укажите метку, которая будет отображаться слева от значения свойства или скрипта.</span><span class="sxs-lookup"><span data-stu-id="ae329-118">Specify the label to be display to the left of the property or script value.</span></span>

## <a name="remarks"></a><span data-ttu-id="ae329-119">Замечания</span><span class="sxs-lookup"><span data-stu-id="ae329-119">Remarks</span></span>

<span data-ttu-id="ae329-120">Если метка не указана, отображается имя свойства или скрипт.</span><span class="sxs-lookup"><span data-stu-id="ae329-120">If a label is not specified, the name of the property or the script is displayed.</span></span> <span data-ttu-id="ae329-121">Дополнительные сведения об использовании меток в представлении списка см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="ae329-121">For more information about using labels in a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="ae329-122">Пример</span><span class="sxs-lookup"><span data-stu-id="ae329-122">Example</span></span>

<span data-ttu-id="ae329-123">В следующем примере показано, как добавить метку к строке.</span><span class="sxs-lookup"><span data-stu-id="ae329-123">The following example shows how to add a label to a row.</span></span>

```xml
<ListItem>
  <Label>Property1: </Label>
  <PropertyName>DotNetProperty1</PropertyName>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="ae329-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="ae329-124">See Also</span></span>

[<span data-ttu-id="ae329-125">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="ae329-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="ae329-126">Элемент ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="ae329-126">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="ae329-127">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae329-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
