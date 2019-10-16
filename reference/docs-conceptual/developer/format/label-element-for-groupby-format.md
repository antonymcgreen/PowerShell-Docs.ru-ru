---
title: Элемент Label для GroupBy (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3351d237-e8c2-4ec5-9500-4eceadb407c2
caps.latest.revision: 11
ms.openlocfilehash: e7158711c60d13c745bbdfab9b1b9fc7d98b34e2
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365203"
---
# <a name="label-element-for-groupby-format"></a><span data-ttu-id="24ddb-102">Элемент Label для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="24ddb-102">Label Element for GroupBy (Format)</span></span>

<span data-ttu-id="24ddb-103">Указывает метку, которая отображается при обнаружении новой группы.</span><span class="sxs-lookup"><span data-stu-id="24ddb-103">Specifies a label that is displayed when a new group is encountered.</span></span>

<span data-ttu-id="24ddb-104">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (Format) элемент GroupBy для элемента метки представления (Format) для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="24ddb-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) Label Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="24ddb-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="24ddb-105">Syntax</span></span>

```xml
<Label>DisplayedLabel</Label>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="24ddb-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="24ddb-106">Attributes and Elements</span></span>

<span data-ttu-id="24ddb-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `Label`.</span><span class="sxs-lookup"><span data-stu-id="24ddb-107">The following sections describe the attributes, child elements, and parent element of the `Label` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="24ddb-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="24ddb-108">Attributes</span></span>

<span data-ttu-id="24ddb-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="24ddb-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="24ddb-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="24ddb-110">Child Elements</span></span>

<span data-ttu-id="24ddb-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="24ddb-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="24ddb-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="24ddb-112">Parent Elements</span></span>

|<span data-ttu-id="24ddb-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="24ddb-113">Element</span></span>|<span data-ttu-id="24ddb-114">Описание</span><span class="sxs-lookup"><span data-stu-id="24ddb-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="24ddb-115">Элемент GroupBy для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="24ddb-115">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="24ddb-116">Определяет, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="24ddb-116">Defines how a new group of objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="24ddb-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="24ddb-117">Text Value</span></span>

<span data-ttu-id="24ddb-118">Укажите текст, который будет отображаться каждый раз, когда Windows PowerShell встречает новое значение свойства или скрипта.</span><span class="sxs-lookup"><span data-stu-id="24ddb-118">Specify the text that is displayed whenever Windows PowerShell encounters a new property or script value.</span></span>

## <a name="remarks"></a><span data-ttu-id="24ddb-119">Замечания</span><span class="sxs-lookup"><span data-stu-id="24ddb-119">Remarks</span></span>

<span data-ttu-id="24ddb-120">В дополнение к тексту, указанному этим элементом, Windows PowerShell отображает новое значение, которое запускает группу, и добавляет пустую строку до и после группы.</span><span class="sxs-lookup"><span data-stu-id="24ddb-120">In addition to the text specified by this element, Windows PowerShell displays the new value that starts the group, and adds a blank line before and after the group.</span></span>

## <a name="example"></a><span data-ttu-id="24ddb-121">Пример</span><span class="sxs-lookup"><span data-stu-id="24ddb-121">Example</span></span>

<span data-ttu-id="24ddb-122">В следующем примере показана метка для новой группы.</span><span class="sxs-lookup"><span data-stu-id="24ddb-122">The following example shows the label for a new group.</span></span> <span data-ttu-id="24ddb-123">Отображаемая метка будет выглядеть примерно так: `Service Type: NewValueofProperty`</span><span class="sxs-lookup"><span data-stu-id="24ddb-123">The displayed label would look similar to this: `Service Type: NewValueofProperty`</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="24ddb-124">Пример полного файла форматирования, включающего этот элемент, см. в разделе [широкие представления (GroupBy)](./wide-view-groupby.md).</span><span class="sxs-lookup"><span data-stu-id="24ddb-124">For an example of a complete formatting file that includes this element, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="24ddb-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="24ddb-125">See Also</span></span>

[<span data-ttu-id="24ddb-126">Элемент GroupBy для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="24ddb-126">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="24ddb-127">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="24ddb-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
