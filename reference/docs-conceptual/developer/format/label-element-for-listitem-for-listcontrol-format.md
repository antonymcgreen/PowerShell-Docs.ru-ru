---
title: Элемент Label для ListItem для ListControl (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: ad80cc0478e7567b12d264ab661d843248ba48e1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783642"
---
# <a name="label-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="c231b-102">Элемент Label для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="c231b-102">Label Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="c231b-103">Задает метку, которая отображается слева от значения свойства или скрипта в строке.</span><span class="sxs-lookup"><span data-stu-id="c231b-103">Specifies the label that is displayed to the left of the property or script value in the row.</span></span>

<span data-ttu-id="c231b-104">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес для ListControl (Format) Листентри элемент для элементов ListItem в ListControl (формат) для листентри (Format) элемент ListItem для элементов ListItem для ListControl (Format) элемент Label для элемента SPListItem для ListControl (Format).</span><span class="sxs-lookup"><span data-stu-id="c231b-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems for ListEntry for ListControl Element (Format) ListItem Element for ListItems for ListControl (Format) Label Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c231b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c231b-105">Syntax</span></span>

```xml
<Label>Label for displayed value</Label>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c231b-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c231b-106">Attributes and Elements</span></span>

<span data-ttu-id="c231b-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Label` элемента.</span><span class="sxs-lookup"><span data-stu-id="c231b-107">The following sections describe the attributes, child elements, and the parent element of the `Label` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c231b-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c231b-108">Attributes</span></span>

<span data-ttu-id="c231b-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c231b-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c231b-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c231b-110">Child Elements</span></span>

<span data-ttu-id="c231b-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c231b-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c231b-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c231b-112">Parent Elements</span></span>

|<span data-ttu-id="c231b-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="c231b-113">Element</span></span>|<span data-ttu-id="c231b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="c231b-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c231b-115">Элемент ListItem для элемента ListItems для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="c231b-115">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="c231b-116">Определяет свойство или скрипт, значение которого отображается в строке представления списка.</span><span class="sxs-lookup"><span data-stu-id="c231b-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c231b-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="c231b-117">Text Value</span></span>

<span data-ttu-id="c231b-118">Укажите метку, которая будет отображаться слева от значения свойства или скрипта.</span><span class="sxs-lookup"><span data-stu-id="c231b-118">Specify the label to be display to the left of the property or script value.</span></span>

## <a name="remarks"></a><span data-ttu-id="c231b-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="c231b-119">Remarks</span></span>

<span data-ttu-id="c231b-120">Если метка не указана, отображается имя свойства или скрипт.</span><span class="sxs-lookup"><span data-stu-id="c231b-120">If a label is not specified, the name of the property or the script is displayed.</span></span> <span data-ttu-id="c231b-121">Дополнительные сведения об использовании меток в представлении списка см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="c231b-121">For more information about using labels in a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="c231b-122">Пример</span><span class="sxs-lookup"><span data-stu-id="c231b-122">Example</span></span>

<span data-ttu-id="c231b-123">В следующем примере показано, как добавить метку к строке.</span><span class="sxs-lookup"><span data-stu-id="c231b-123">The following example shows how to add a label to a row.</span></span>

```xml
<ListItem>
  <Label>Property1: </Label>
  <PropertyName>DotNetProperty1</PropertyName>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="c231b-124">См. также</span><span class="sxs-lookup"><span data-stu-id="c231b-124">See Also</span></span>

[<span data-ttu-id="c231b-125">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="c231b-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="c231b-126">Элемент ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="c231b-126">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="c231b-127">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="c231b-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
