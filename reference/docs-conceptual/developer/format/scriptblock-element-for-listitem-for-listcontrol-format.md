---
title: Элемент ScriptBlock для ListItem для ListControl (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 249d3e36b4246b7baa410815122f8e30340f1862
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785461"
---
# <a name="scriptblock-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="a31ab-102">Элемент ScriptBlock для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="a31ab-102">ScriptBlock Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="a31ab-103">Указывает скрипт, значение которого отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="a31ab-103">Specifies the script whose value is displayed in the row.</span></span>

<span data-ttu-id="a31ab-104">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (формат) ListControl элемент (Format) Листентриес для ListControl (Format) Листентри элемент для Листентриес в ListControl (Format) элемент ListItem для листентри для элемента списка элементов ListControl в ListControl (Format).</span><span class="sxs-lookup"><span data-stu-id="a31ab-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ScriptBlock Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a31ab-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a31ab-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a31ab-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a31ab-106">Attributes and Elements</span></span>

<span data-ttu-id="a31ab-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемента.</span><span class="sxs-lookup"><span data-stu-id="a31ab-107">The following sections describe the attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a31ab-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a31ab-108">Attributes</span></span>

<span data-ttu-id="a31ab-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a31ab-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a31ab-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a31ab-110">Child Elements</span></span>

<span data-ttu-id="a31ab-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a31ab-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a31ab-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a31ab-112">Parent Elements</span></span>

|<span data-ttu-id="a31ab-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="a31ab-113">Element</span></span>|<span data-ttu-id="a31ab-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a31ab-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a31ab-115">Элемент ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="a31ab-115">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="a31ab-116">Определяет свойство или скрипт, значение которого отображается в строке представления списка.</span><span class="sxs-lookup"><span data-stu-id="a31ab-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a31ab-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="a31ab-117">Text Value</span></span>

<span data-ttu-id="a31ab-118">Укажите скрипт, значение которого отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="a31ab-118">Specify the script whose value is displayed in the row.</span></span>

## <a name="remarks"></a><span data-ttu-id="a31ab-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="a31ab-119">Remarks</span></span>

<span data-ttu-id="a31ab-120">Если этот элемент указан, нельзя указать элемент [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) .</span><span class="sxs-lookup"><span data-stu-id="a31ab-120">When this element is specified, you cannot specify the [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element.</span></span>

<span data-ttu-id="a31ab-121">Дополнительные сведения об указании скриптов в представлении списка см. в разделе [представление списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="a31ab-121">For more information about specifying scripts in a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="a31ab-122">Пример</span><span class="sxs-lookup"><span data-stu-id="a31ab-122">Example</span></span>

<span data-ttu-id="a31ab-123">В следующем примере показано, как указать свойство, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="a31ab-123">The following example shows how to specify the property whose value is displayed.</span></span>

```xml
<ListItem>
  <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="a31ab-124">См. также</span><span class="sxs-lookup"><span data-stu-id="a31ab-124">See Also</span></span>

[<span data-ttu-id="a31ab-125">Элемент PropertyName для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="a31ab-125">PropertyName Element for ListItem for ListControl (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="a31ab-126">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="a31ab-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="a31ab-127">Элемент ListItem для элемента ListItems для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="a31ab-127">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="a31ab-128">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="a31ab-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
