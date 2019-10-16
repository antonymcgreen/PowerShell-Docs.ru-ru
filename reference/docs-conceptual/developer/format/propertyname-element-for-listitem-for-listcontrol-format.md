---
title: Элемент PropertyName для ListItem для ListControl (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01ae8cbe-acdc-4043-bd6e-1118a5691a55
caps.latest.revision: 12
ms.openlocfilehash: 405184f7bdbf1955f1df7766bf2723c244dcc27f
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362383"
---
# <a name="propertyname-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="f7db4-102">Элемент PropertyName для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="f7db4-102">PropertyName Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="f7db4-103">Указывает свойство .NET, значение которого отображается в списке.</span><span class="sxs-lookup"><span data-stu-id="f7db4-103">Specifies the .NET property whose value is displayed in the list.</span></span>

<span data-ttu-id="f7db4-104">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент (Format) элемент списка ListItem (Format) элемент ListItem (Format) PropertyName элемент для ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="f7db4-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) ListItems Element (Format) ListItem Element (Format) PropertyName Element for ListItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f7db4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f7db4-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f7db4-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f7db4-106">Attributes and Elements</span></span>

<span data-ttu-id="f7db4-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `PropertyName`.</span><span class="sxs-lookup"><span data-stu-id="f7db4-107">The following sections describe the attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f7db4-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f7db4-108">Attributes</span></span>

<span data-ttu-id="f7db4-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="f7db4-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f7db4-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f7db4-110">Child Elements</span></span>

<span data-ttu-id="f7db4-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="f7db4-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f7db4-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f7db4-112">Parent Elements</span></span>

|<span data-ttu-id="f7db4-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="f7db4-113">Element</span></span>|<span data-ttu-id="f7db4-114">Описание</span><span class="sxs-lookup"><span data-stu-id="f7db4-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f7db4-115">Элемент ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="f7db4-115">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="f7db4-116">Определяет свойство или скрипт, значение которого отображается в строке представления списка.</span><span class="sxs-lookup"><span data-stu-id="f7db4-116">Defines the property or script whose value is displayed in the row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f7db4-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="f7db4-117">Text Value</span></span>

<span data-ttu-id="f7db4-118">Укажите имя свойства, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="f7db4-118">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="f7db4-119">Замечания</span><span class="sxs-lookup"><span data-stu-id="f7db4-119">Remarks</span></span>

<span data-ttu-id="f7db4-120">Если этот элемент указан, нельзя указать элемент [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) .</span><span class="sxs-lookup"><span data-stu-id="f7db4-120">When this element is specified, you cannot specify the [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element.</span></span>

<span data-ttu-id="f7db4-121">В дополнение к отображению значения свойства можно также указать метку для значения или строку формата, которую можно использовать для изменения отображения значения.</span><span class="sxs-lookup"><span data-stu-id="f7db4-121">In addition to displaying the property value, you can also specify a label for the value or a format string that can be used to change the display of the value.</span></span> <span data-ttu-id="f7db4-122">Дополнительные сведения об указании данных в представлении списка см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="f7db4-122">For more information about specifying data in a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="f7db4-123">Пример</span><span class="sxs-lookup"><span data-stu-id="f7db4-123">Example</span></span>

<span data-ttu-id="f7db4-124">В следующем примере показано, как указать метку и свойство, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="f7db4-124">The following example shows how to specify the label and property whose value is displayed.</span></span>

```xml
ListItem>
  <Label>NameOfProperty</Label>
  <PropertyName>.NetTypeProperty</PropertyName>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="f7db4-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="f7db4-125">See Also</span></span>

[<span data-ttu-id="f7db4-126">Элемент ScriptBlock для ListItem для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="f7db4-126">ScriptBlock Element for ListItem for ListControl (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="f7db4-127">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="f7db4-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="f7db4-128">Элемент ListItem для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="f7db4-128">ListItem Element for ListControl(Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="f7db4-129">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="f7db4-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
