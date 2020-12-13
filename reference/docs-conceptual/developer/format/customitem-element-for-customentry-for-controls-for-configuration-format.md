---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент CustomItem для элемента CustomEntry для элемента Controls для элемента Configuration (формат)
description: Элемент CustomItem для элемента CustomEntry для элемента Controls для элемента Configuration (формат)
ms.openlocfilehash: 06c399e982b6ac0fba9c11e20c468fe8bef6f694
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666779"
---
# <a name="customitem-element-for-customentry-for-controls-for-configuration-format"></a><span data-ttu-id="0f051-103">Элемент CustomItem для элемента CustomEntry для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="0f051-103">CustomItem Element for CustomEntry for Controls for Configuration (Format)</span></span>

<span data-ttu-id="0f051-104">Определяет, какие данные отображаются элементом управления и как они отображаются.</span><span class="sxs-lookup"><span data-stu-id="0f051-104">Defines what data is displayed by the control and how it is displayed.</span></span> <span data-ttu-id="0f051-105">Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="0f051-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="0f051-106">Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления Configuration (Format) ошибка customcontrol для элемента Control (формат) Кустоментриес для ошибка customcontrol для элемента Configuration (формат) Кустоментри для ошибка customcontrol для элементов управления конфигурации (Format) Кустомитем для кустоментри для элементов управления конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0f051-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration</span></span>

## <a name="syntax"></a><span data-ttu-id="0f051-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f051-107">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...</Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0f051-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0f051-108">Attributes and Elements</span></span>

<span data-ttu-id="0f051-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `CustomItem` элемента.</span><span class="sxs-lookup"><span data-stu-id="0f051-109">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span> <span data-ttu-id="0f051-110">Дополнительные сведения см. в подразделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="0f051-110">For more information, see Remarks.</span></span>

### <a name="attributes"></a><span data-ttu-id="0f051-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0f051-111">Attributes</span></span>

<span data-ttu-id="0f051-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0f051-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0f051-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0f051-113">Child Elements</span></span>

|<span data-ttu-id="0f051-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="0f051-114">Element</span></span>|<span data-ttu-id="0f051-115">Описание</span><span class="sxs-lookup"><span data-stu-id="0f051-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0f051-116">Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="0f051-116">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="0f051-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="0f051-117">Optional element.</span></span><br /><br /> <span data-ttu-id="0f051-118">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="0f051-118">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="0f051-119">Элемент Frame для элемента CustomItem для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="0f051-119">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="0f051-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="0f051-120">Optional element.</span></span><br /><br /> <span data-ttu-id="0f051-121">Определяет способ отображения данных, например сдвиг данных влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="0f051-121">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|
|[<span data-ttu-id="0f051-122">Элемент NewLine для элемента CustomItem для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="0f051-122">NewLine Element for CustomItem for Controls for Configuration (Format)</span></span>](./newline-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="0f051-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="0f051-123">Optional element.</span></span><br /><br /> <span data-ttu-id="0f051-124">Добавляет пустую строку к отображению элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0f051-124">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="0f051-125">Элемент Text для элемента CustomItem для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="0f051-125">Text Element for CustomItem for Controls for Configuration (Format)</span></span>](./text-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="0f051-126">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="0f051-126">Optional element.</span></span><br /><br /> <span data-ttu-id="0f051-127">Добавляет текст, например круглые скобки или квадратные скобки, к отображаемому элементу управления.</span><span class="sxs-lookup"><span data-stu-id="0f051-127">Adds text, such as parentheses or brackets, to the display of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="0f051-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0f051-128">Parent Elements</span></span>

|<span data-ttu-id="0f051-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="0f051-129">Element</span></span>|<span data-ttu-id="0f051-130">Описание</span><span class="sxs-lookup"><span data-stu-id="0f051-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0f051-131">Элемент CustomEntry для элемента CustomControl для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="0f051-131">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="0f051-132">Предоставляет определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0f051-132">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0f051-133">Комментарии</span><span class="sxs-lookup"><span data-stu-id="0f051-133">Remarks</span></span>

<span data-ttu-id="0f051-134">При указании дочерних элементов `CustomItem` элемента учитывайте следующее:</span><span class="sxs-lookup"><span data-stu-id="0f051-134">When specifying the child elements of the `CustomItem` element, keep the following in mind:</span></span>

- <span data-ttu-id="0f051-135">Дочерние элементы должны быть добавлены в следующей последовательности: `ExpressionBinding` , `NewLine` , `Text` и `Frame` .</span><span class="sxs-lookup"><span data-stu-id="0f051-135">The child elements must be added in the following sequence: `ExpressionBinding`, `NewLine`, `Text`, and `Frame`.</span></span>

- <span data-ttu-id="0f051-136">Максимальное число последовательностей, которое можно указать, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="0f051-136">There is no maximum limit to the number of sequences that you can specify.</span></span>

- <span data-ttu-id="0f051-137">В каждой последовательности не существует максимального ограничения на количество `ExpressionBinding` элементов, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="0f051-137">In each sequence, there is no maximum limit to the number of `ExpressionBinding` elements that you can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="0f051-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="0f051-138">See Also</span></span>

[<span data-ttu-id="0f051-139">Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="0f051-139">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="0f051-140">Элемент Frame для элемента CustomItem для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="0f051-140">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="0f051-141">Элемент NewLine для элемента CustomItem для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="0f051-141">NewLine Element for CustomItem for Controls for Configuration (Format)</span></span>](./newline-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="0f051-142">Элемент Text для элемента CustomItem для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="0f051-142">Text Element for CustomItem for Controls for Configuration (Format)</span></span>](./text-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="0f051-143">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f051-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
