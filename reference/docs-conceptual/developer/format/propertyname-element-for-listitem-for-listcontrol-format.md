---
title: Элемент PropertyName для ListItem для ListControl (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 9ee466d7f73e53b129f8d46f49a21549683bb32c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780837"
---
# <a name="propertyname-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="64d2f-102">Элемент PropertyName для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="64d2f-102">PropertyName Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="64d2f-103">Указывает свойство .NET, значение которого отображается в списке.</span><span class="sxs-lookup"><span data-stu-id="64d2f-103">Specifies the .NET property whose value is displayed in the list.</span></span>

<span data-ttu-id="64d2f-104">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент (Format) элемент списка ListItem (Format) элемент "PropertyName" (Format) ИмяСвойства Element для ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="64d2f-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) ListItems Element (Format) ListItem Element (Format) PropertyName Element for ListItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="64d2f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="64d2f-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="64d2f-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="64d2f-106">Attributes and Elements</span></span>

<span data-ttu-id="64d2f-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.</span><span class="sxs-lookup"><span data-stu-id="64d2f-107">The following sections describe the attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="64d2f-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="64d2f-108">Attributes</span></span>

<span data-ttu-id="64d2f-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="64d2f-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="64d2f-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="64d2f-110">Child Elements</span></span>

<span data-ttu-id="64d2f-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="64d2f-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="64d2f-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="64d2f-112">Parent Elements</span></span>

|<span data-ttu-id="64d2f-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="64d2f-113">Element</span></span>|<span data-ttu-id="64d2f-114">Описание</span><span class="sxs-lookup"><span data-stu-id="64d2f-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="64d2f-115">Элемент ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="64d2f-115">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="64d2f-116">Определяет свойство или скрипт, значение которого отображается в строке представления списка.</span><span class="sxs-lookup"><span data-stu-id="64d2f-116">Defines the property or script whose value is displayed in the row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="64d2f-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="64d2f-117">Text Value</span></span>

<span data-ttu-id="64d2f-118">Укажите имя свойства, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="64d2f-118">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="64d2f-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="64d2f-119">Remarks</span></span>

<span data-ttu-id="64d2f-120">Если этот элемент указан, нельзя указать элемент [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) .</span><span class="sxs-lookup"><span data-stu-id="64d2f-120">When this element is specified, you cannot specify the [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element.</span></span>

<span data-ttu-id="64d2f-121">В дополнение к отображению значения свойства можно также указать метку для значения или строку формата, которую можно использовать для изменения отображения значения.</span><span class="sxs-lookup"><span data-stu-id="64d2f-121">In addition to displaying the property value, you can also specify a label for the value or a format string that can be used to change the display of the value.</span></span> <span data-ttu-id="64d2f-122">Дополнительные сведения об указании данных в представлении списка см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="64d2f-122">For more information about specifying data in a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="64d2f-123">Пример</span><span class="sxs-lookup"><span data-stu-id="64d2f-123">Example</span></span>

<span data-ttu-id="64d2f-124">В следующем примере показано, как указать метку и свойство, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="64d2f-124">The following example shows how to specify the label and property whose value is displayed.</span></span>

```xml
ListItem>
  <Label>NameOfProperty</Label>
  <PropertyName>.NetTypeProperty</PropertyName>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="64d2f-125">См. также</span><span class="sxs-lookup"><span data-stu-id="64d2f-125">See Also</span></span>

[<span data-ttu-id="64d2f-126">Элемент ScriptBlock для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="64d2f-126">ScriptBlock Element for ListItem for ListControl (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="64d2f-127">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="64d2f-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="64d2f-128">Элемент ListItem для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="64d2f-128">ListItem Element for ListControl(Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="64d2f-129">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="64d2f-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
