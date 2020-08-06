---
title: Элемент Label для GroupBy (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 07b4d037472a9dd2329e94576ec10f5b82f46b34
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785784"
---
# <a name="label-element-for-groupby-format"></a><span data-ttu-id="ef5f7-102">Элемент Label для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="ef5f7-102">Label Element for GroupBy (Format)</span></span>

<span data-ttu-id="ef5f7-103">Указывает метку, которая отображается при обнаружении новой группы.</span><span class="sxs-lookup"><span data-stu-id="ef5f7-103">Specifies a label that is displayed when a new group is encountered.</span></span>

<span data-ttu-id="ef5f7-104">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (Format) элемент GroupBy для элемента метки представления (Format) для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="ef5f7-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) Label Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ef5f7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ef5f7-105">Syntax</span></span>

```xml
<Label>DisplayedLabel</Label>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ef5f7-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ef5f7-106">Attributes and Elements</span></span>

<span data-ttu-id="ef5f7-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Label` элемента.</span><span class="sxs-lookup"><span data-stu-id="ef5f7-107">The following sections describe the attributes, child elements, and parent element of the `Label` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ef5f7-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ef5f7-108">Attributes</span></span>

<span data-ttu-id="ef5f7-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ef5f7-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ef5f7-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ef5f7-110">Child Elements</span></span>

<span data-ttu-id="ef5f7-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ef5f7-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ef5f7-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ef5f7-112">Parent Elements</span></span>

|<span data-ttu-id="ef5f7-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="ef5f7-113">Element</span></span>|<span data-ttu-id="ef5f7-114">Описание</span><span class="sxs-lookup"><span data-stu-id="ef5f7-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ef5f7-115">Элемент GroupBy для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="ef5f7-115">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="ef5f7-116">Определяет, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="ef5f7-116">Defines how a new group of objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ef5f7-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="ef5f7-117">Text Value</span></span>

<span data-ttu-id="ef5f7-118">Укажите текст, который будет отображаться каждый раз, когда Windows PowerShell встречает новое значение свойства или скрипта.</span><span class="sxs-lookup"><span data-stu-id="ef5f7-118">Specify the text that is displayed whenever Windows PowerShell encounters a new property or script value.</span></span>

## <a name="remarks"></a><span data-ttu-id="ef5f7-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="ef5f7-119">Remarks</span></span>

<span data-ttu-id="ef5f7-120">В дополнение к тексту, указанному этим элементом, Windows PowerShell отображает новое значение, которое запускает группу, и добавляет пустую строку до и после группы.</span><span class="sxs-lookup"><span data-stu-id="ef5f7-120">In addition to the text specified by this element, Windows PowerShell displays the new value that starts the group, and adds a blank line before and after the group.</span></span>

## <a name="example"></a><span data-ttu-id="ef5f7-121">Пример</span><span class="sxs-lookup"><span data-stu-id="ef5f7-121">Example</span></span>

<span data-ttu-id="ef5f7-122">В следующем примере показана метка для новой группы.</span><span class="sxs-lookup"><span data-stu-id="ef5f7-122">The following example shows the label for a new group.</span></span> <span data-ttu-id="ef5f7-123">Отображаемая метка будет выглядеть примерно так:`Service Type: NewValueofProperty`</span><span class="sxs-lookup"><span data-stu-id="ef5f7-123">The displayed label would look similar to this: `Service Type: NewValueofProperty`</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="ef5f7-124">Пример полного файла форматирования, включающего этот элемент, см. в разделе [широкие представления (GroupBy)](./wide-view-groupby.md).</span><span class="sxs-lookup"><span data-stu-id="ef5f7-124">For an example of a complete formatting file that includes this element, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ef5f7-125">См. также</span><span class="sxs-lookup"><span data-stu-id="ef5f7-125">See Also</span></span>

[<span data-ttu-id="ef5f7-126">Элемент GroupBy для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="ef5f7-126">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="ef5f7-127">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="ef5f7-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
