---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент Label для элемента GroupBy (формат)
description: Элемент Label для элемента GroupBy (формат)
ms.openlocfilehash: ff4b0dec01bb5b472b1813540661791b91568eed
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649790"
---
# <a name="label-element-for-groupby-format"></a><span data-ttu-id="2f94e-103">Элемент Label для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="2f94e-103">Label Element for GroupBy (Format)</span></span>

<span data-ttu-id="2f94e-104">Указывает метку, которая отображается при обнаружении новой группы.</span><span class="sxs-lookup"><span data-stu-id="2f94e-104">Specifies a label that is displayed when a new group is encountered.</span></span>

<span data-ttu-id="2f94e-105">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (Format) элемент GroupBy для элемента метки представления (Format) для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="2f94e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) Label Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2f94e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f94e-106">Syntax</span></span>

```xml
<Label>DisplayedLabel</Label>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2f94e-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2f94e-107">Attributes and Elements</span></span>

<span data-ttu-id="2f94e-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Label` элемента.</span><span class="sxs-lookup"><span data-stu-id="2f94e-108">The following sections describe the attributes, child elements, and parent element of the `Label` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2f94e-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2f94e-109">Attributes</span></span>

<span data-ttu-id="2f94e-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2f94e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2f94e-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2f94e-111">Child Elements</span></span>

<span data-ttu-id="2f94e-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2f94e-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2f94e-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2f94e-113">Parent Elements</span></span>

|<span data-ttu-id="2f94e-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="2f94e-114">Element</span></span>|<span data-ttu-id="2f94e-115">Описание</span><span class="sxs-lookup"><span data-stu-id="2f94e-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2f94e-116">Элемент GroupBy для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="2f94e-116">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="2f94e-117">Определяет, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="2f94e-117">Defines how a new group of objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2f94e-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="2f94e-118">Text Value</span></span>

<span data-ttu-id="2f94e-119">Укажите текст, который будет отображаться каждый раз, когда Windows PowerShell встречает новое значение свойства или скрипта.</span><span class="sxs-lookup"><span data-stu-id="2f94e-119">Specify the text that is displayed whenever Windows PowerShell encounters a new property or script value.</span></span>

## <a name="remarks"></a><span data-ttu-id="2f94e-120">Комментарии</span><span class="sxs-lookup"><span data-stu-id="2f94e-120">Remarks</span></span>

<span data-ttu-id="2f94e-121">В дополнение к тексту, указанному этим элементом, Windows PowerShell отображает новое значение, которое запускает группу, и добавляет пустую строку до и после группы.</span><span class="sxs-lookup"><span data-stu-id="2f94e-121">In addition to the text specified by this element, Windows PowerShell displays the new value that starts the group, and adds a blank line before and after the group.</span></span>

## <a name="example"></a><span data-ttu-id="2f94e-122">Пример</span><span class="sxs-lookup"><span data-stu-id="2f94e-122">Example</span></span>

<span data-ttu-id="2f94e-123">В следующем примере показана метка для новой группы.</span><span class="sxs-lookup"><span data-stu-id="2f94e-123">The following example shows the label for a new group.</span></span> <span data-ttu-id="2f94e-124">Отображаемая метка будет выглядеть примерно так: `Service Type: NewValueofProperty`</span><span class="sxs-lookup"><span data-stu-id="2f94e-124">The displayed label would look similar to this: `Service Type: NewValueofProperty`</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="2f94e-125">Пример полного файла форматирования, включающего этот элемент, см. в разделе [широкие представления (GroupBy)](./wide-view-groupby.md).</span><span class="sxs-lookup"><span data-stu-id="2f94e-125">For an example of a complete formatting file that includes this element, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2f94e-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="2f94e-126">See Also</span></span>

[<span data-ttu-id="2f94e-127">Элемент GroupBy для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="2f94e-127">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="2f94e-128">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f94e-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
