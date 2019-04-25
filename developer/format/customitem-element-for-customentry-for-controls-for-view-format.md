---
title: Элемент CustomItem для CustomEntry для элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33cb5350-73ef-4b79-a879-0edf051869e4
caps.latest.revision: 7
ms.openlocfilehash: 174ba6a14819f823ec39f72e49a626e781221d8c
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066387"
---
# <a name="customitem-element-for-customentry-for-controls-for-view-format"></a><span data-ttu-id="065f3-102">Элемент CustomItem для элемента CustomEntry для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="065f3-102">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>

<span data-ttu-id="065f3-103">Определяет, какие данные отображаются с помощью элемента управления и как он отображается.</span><span class="sxs-lookup"><span data-stu-id="065f3-103">Defines what data is displayed by the control and how it is displayed.</span></span> <span data-ttu-id="065f3-104">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="065f3-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="065f3-105">Конфигурации элемента (формат) элемент ViewDefinitions (формат) представление элемента (формат) элементы управления элемента (формат) элемент управления для элементов управления для элемента представления (формат) пользовательский элемент управления для элемента управления для элементов управления для элемента CustomEntries представления (формат) для Пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для элементов управления для элемента представления (формат) CustomItem для CustomEntry для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="065f3-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="065f3-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="065f3-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...<Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="065f3-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="065f3-107">Attributes and Elements</span></span>

<span data-ttu-id="065f3-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `CustomItem` элемент.</span><span class="sxs-lookup"><span data-stu-id="065f3-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span> <span data-ttu-id="065f3-109">Дополнительные сведения см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="065f3-109">For more information, see Remarks.</span></span>

### <a name="attributes"></a><span data-ttu-id="065f3-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="065f3-110">Attributes</span></span>

<span data-ttu-id="065f3-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="065f3-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="065f3-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="065f3-112">Child Elements</span></span>

|<span data-ttu-id="065f3-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="065f3-113">Element</span></span>|<span data-ttu-id="065f3-114">Описание</span><span class="sxs-lookup"><span data-stu-id="065f3-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="065f3-115">Элемент ExpressionBinding для CustomItem для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="065f3-115">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="065f3-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="065f3-116">Optional element.</span></span><br /><br /> <span data-ttu-id="065f3-117">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="065f3-117">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="065f3-118">Элемент Frame для CustomItem для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="065f3-118">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="065f3-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="065f3-119">Optional element.</span></span><br /><br /> <span data-ttu-id="065f3-120">Определяет способ отображения данных, таких как данные сдвига влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="065f3-120">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|
|[<span data-ttu-id="065f3-121">Элемент новой строки для CustomItem для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="065f3-121">NewLine Element for CustomItem for Controls for View (Format)</span></span>](./newline-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="065f3-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="065f3-122">Optional element.</span></span><br /><br /> <span data-ttu-id="065f3-123">Добавляет пустой строки для отображения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="065f3-123">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="065f3-124">Текстовый элемент для CustomItem для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="065f3-124">Text Element for CustomItem for Controls for View (Format)</span></span>](./text-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="065f3-125">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="065f3-125">Optional element.</span></span><br /><br /> <span data-ttu-id="065f3-126">Добавляет текст, таких как круглые скобки или квадратные скобки, отображение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="065f3-126">Adds text, such as parentheses or brackets, to the display of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="065f3-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="065f3-127">Parent Elements</span></span>

|<span data-ttu-id="065f3-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="065f3-128">Element</span></span>|<span data-ttu-id="065f3-129">Описание</span><span class="sxs-lookup"><span data-stu-id="065f3-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="065f3-130">Элемент CustomEntry для CustomEntries для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="065f3-130">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="065f3-131">Предоставляет определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="065f3-131">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="065f3-132">Замечания</span><span class="sxs-lookup"><span data-stu-id="065f3-132">Remarks</span></span>

<span data-ttu-id="065f3-133">При указании дочерние элементы `CustomItem` элемент, имейте в виду следующее:</span><span class="sxs-lookup"><span data-stu-id="065f3-133">When specifying the child elements of the `CustomItem` element, keep the following in mind:</span></span>

- <span data-ttu-id="065f3-134">Дочерние элементы должны добавляться в следующей последовательности: `ExpressionBinding`, `NewLine`, `Text`, и `Frame`.</span><span class="sxs-lookup"><span data-stu-id="065f3-134">The child elements must be added in the following sequence: `ExpressionBinding`, `NewLine`, `Text`, and `Frame`.</span></span>

- <span data-ttu-id="065f3-135">Не ограничено максимальное число последовательности, которые можно указать.</span><span class="sxs-lookup"><span data-stu-id="065f3-135">There is no maximum limit to the number of sequences that you can specify.</span></span>

- <span data-ttu-id="065f3-136">В каждой последовательности не ограничено максимальное число `ExpressionBinding` элементы, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="065f3-136">In each sequence, there is no maximum limit to the number of `ExpressionBinding` elements that you can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="065f3-137">См. также</span><span class="sxs-lookup"><span data-stu-id="065f3-137">See Also</span></span>

[<span data-ttu-id="065f3-138">Элемент ExpressionBinding для CustomItem для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="065f3-138">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="065f3-139">Элемент Frame для CustomItem для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="065f3-139">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="065f3-140">Элемент новой строки для CustomItem для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="065f3-140">NewLine Element for CustomItem for Controls for View (Format)</span></span>](./newline-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="065f3-141">Текстовый элемент для CustomItem для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="065f3-141">Text Element for CustomItem for Controls for View (Format)</span></span>](./text-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="065f3-142">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="065f3-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
