---
title: Элемент Кустомитем для Кустоментри элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33cb5350-73ef-4b79-a879-0edf051869e4
caps.latest.revision: 7
ms.openlocfilehash: 174ba6a14819f823ec39f72e49a626e781221d8c
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363943"
---
# <a name="customitem-element-for-customentry-for-controls-for-view-format"></a><span data-ttu-id="c873c-102">Элемент CustomItem для элемента CustomEntry для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="c873c-102">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>

<span data-ttu-id="c873c-103">Определяет, какие данные отображаются элементом управления и как они отображаются.</span><span class="sxs-lookup"><span data-stu-id="c873c-103">Defines what data is displayed by the control and how it is displayed.</span></span> <span data-ttu-id="c873c-104">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="c873c-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="c873c-105">Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет управляющий элемент (Format) элемент управления для элементов управления представления (Format) ошибка customcontrol для элементов управления элемента Кустоментриес представления (Format) для Ошибка customcontrol для элемента Кустоментри представления (Format) для Кустоментриес для элементов управления для представления (Format) Кустомитем для Кустоментри для элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="c873c-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c873c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c873c-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...<Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c873c-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c873c-107">Attributes and Elements</span></span>

<span data-ttu-id="c873c-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `CustomItem`.</span><span class="sxs-lookup"><span data-stu-id="c873c-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span> <span data-ttu-id="c873c-109">Дополнительные сведения см. в разделе Примечания.</span><span class="sxs-lookup"><span data-stu-id="c873c-109">For more information, see Remarks.</span></span>

### <a name="attributes"></a><span data-ttu-id="c873c-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c873c-110">Attributes</span></span>

<span data-ttu-id="c873c-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="c873c-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c873c-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c873c-112">Child Elements</span></span>

|<span data-ttu-id="c873c-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="c873c-113">Element</span></span>|<span data-ttu-id="c873c-114">Описание</span><span class="sxs-lookup"><span data-stu-id="c873c-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c873c-115">Элемент ExpressionBinding для Кустомитем элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="c873c-115">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="c873c-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="c873c-116">Optional element.</span></span><br /><br /> <span data-ttu-id="c873c-117">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="c873c-117">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="c873c-118">Элемент Frame для Кустомитем элементов управления для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="c873c-118">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="c873c-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="c873c-119">Optional element.</span></span><br /><br /> <span data-ttu-id="c873c-120">Определяет способ отображения данных, например сдвиг данных влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="c873c-120">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|
|[<span data-ttu-id="c873c-121">Элемент новой строки для элементов управления Кустомитем для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="c873c-121">NewLine Element for CustomItem for Controls for View (Format)</span></span>](./newline-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="c873c-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="c873c-122">Optional element.</span></span><br /><br /> <span data-ttu-id="c873c-123">Добавляет пустую строку к отображению элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c873c-123">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="c873c-124">Текстовый элемент для Кустомитем элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="c873c-124">Text Element for CustomItem for Controls for View (Format)</span></span>](./text-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="c873c-125">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="c873c-125">Optional element.</span></span><br /><br /> <span data-ttu-id="c873c-126">Добавляет текст, например круглые скобки или квадратные скобки, к отображаемому элементу управления.</span><span class="sxs-lookup"><span data-stu-id="c873c-126">Adds text, such as parentheses or brackets, to the display of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="c873c-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c873c-127">Parent Elements</span></span>

|<span data-ttu-id="c873c-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="c873c-128">Element</span></span>|<span data-ttu-id="c873c-129">Описание</span><span class="sxs-lookup"><span data-stu-id="c873c-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c873c-130">Элемент Кустоментри для Кустоментриес элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="c873c-130">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="c873c-131">Предоставляет определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c873c-131">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c873c-132">Замечания</span><span class="sxs-lookup"><span data-stu-id="c873c-132">Remarks</span></span>

<span data-ttu-id="c873c-133">При указании дочерних элементов элемента `CustomItem` учитывайте следующее:</span><span class="sxs-lookup"><span data-stu-id="c873c-133">When specifying the child elements of the `CustomItem` element, keep the following in mind:</span></span>

- <span data-ttu-id="c873c-134">Дочерние элементы должны быть добавлены в следующей последовательности: `ExpressionBinding`, `NewLine`, `Text`и `Frame`.</span><span class="sxs-lookup"><span data-stu-id="c873c-134">The child elements must be added in the following sequence: `ExpressionBinding`, `NewLine`, `Text`, and `Frame`.</span></span>

- <span data-ttu-id="c873c-135">Максимальное число последовательностей, которое можно указать, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="c873c-135">There is no maximum limit to the number of sequences that you can specify.</span></span>

- <span data-ttu-id="c873c-136">В каждой последовательности нет ограничения на количество элементов `ExpressionBinding`, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="c873c-136">In each sequence, there is no maximum limit to the number of `ExpressionBinding` elements that you can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="c873c-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="c873c-137">See Also</span></span>

[<span data-ttu-id="c873c-138">Элемент ExpressionBinding для Кустомитем элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="c873c-138">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="c873c-139">Элемент Frame для Кустомитем элементов управления для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="c873c-139">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="c873c-140">Элемент новой строки для элементов управления Кустомитем для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="c873c-140">NewLine Element for CustomItem for Controls for View (Format)</span></span>](./newline-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="c873c-141">Текстовый элемент для Кустомитем элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="c873c-141">Text Element for CustomItem for Controls for View (Format)</span></span>](./text-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="c873c-142">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="c873c-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
