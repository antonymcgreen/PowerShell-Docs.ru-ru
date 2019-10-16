---
title: Элемент Кустомитем для Кустоментри для элементов управления конфигурации (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73fb11ee-0ebd-477a-ac36-acdfbb32e70d
caps.latest.revision: 7
ms.openlocfilehash: bd0cb69770817ec215ddb1862a43a838baddefcf
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364033"
---
# <a name="customitem-element-for-customentry-for-controls-for-configuration-format"></a><span data-ttu-id="16c4b-102">Элемент CustomItem для элемента CustomEntry для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="16c4b-102">CustomItem Element for CustomEntry for Controls for Configuration (Format)</span></span>

<span data-ttu-id="16c4b-103">Определяет, какие данные отображаются элементом управления и как они отображаются.</span><span class="sxs-lookup"><span data-stu-id="16c4b-103">Defines what data is displayed by the control and how it is displayed.</span></span> <span data-ttu-id="16c4b-104">Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="16c4b-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="16c4b-105">Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control в конфигурации (Format) Кустоментриес для ошибка customcontrol для конфигурации ( Format) элемент Кустоментри для ошибка customcontrol элементов управления для элемента конфигурации (Format) Кустомитем для Кустоментри для элементов управления в конфигурации</span><span class="sxs-lookup"><span data-stu-id="16c4b-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration</span></span>

## <a name="syntax"></a><span data-ttu-id="16c4b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16c4b-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...</Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="16c4b-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="16c4b-107">Attributes and Elements</span></span>

<span data-ttu-id="16c4b-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `CustomItem`.</span><span class="sxs-lookup"><span data-stu-id="16c4b-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span> <span data-ttu-id="16c4b-109">Дополнительные сведения см. в разделе Примечания.</span><span class="sxs-lookup"><span data-stu-id="16c4b-109">For more information, see Remarks.</span></span>

### <a name="attributes"></a><span data-ttu-id="16c4b-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="16c4b-110">Attributes</span></span>

<span data-ttu-id="16c4b-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="16c4b-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="16c4b-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="16c4b-112">Child Elements</span></span>

|<span data-ttu-id="16c4b-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="16c4b-113">Element</span></span>|<span data-ttu-id="16c4b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="16c4b-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="16c4b-115">Элемент ExpressionBinding для Кустомитем для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="16c4b-115">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="16c4b-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="16c4b-116">Optional element.</span></span><br /><br /> <span data-ttu-id="16c4b-117">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="16c4b-117">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="16c4b-118">Элемент Frame для элемента управления Кустомитем для Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="16c4b-118">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="16c4b-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="16c4b-119">Optional element.</span></span><br /><br /> <span data-ttu-id="16c4b-120">Определяет способ отображения данных, например сдвиг данных влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="16c4b-120">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|
|[<span data-ttu-id="16c4b-121">Элемент новой строки для элементов управления Кустомитем для Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="16c4b-121">NewLine Element for CustomItem for Controls for Configuration (Format)</span></span>](./newline-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="16c4b-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="16c4b-122">Optional element.</span></span><br /><br /> <span data-ttu-id="16c4b-123">Добавляет пустую строку к отображению элемента управления.</span><span class="sxs-lookup"><span data-stu-id="16c4b-123">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="16c4b-124">Текстовый элемент для Кустомитем элементов управления для конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="16c4b-124">Text Element for CustomItem for Controls for Configuration (Format)</span></span>](./text-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="16c4b-125">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="16c4b-125">Optional element.</span></span><br /><br /> <span data-ttu-id="16c4b-126">Добавляет текст, например круглые скобки или квадратные скобки, к отображаемому элементу управления.</span><span class="sxs-lookup"><span data-stu-id="16c4b-126">Adds text, such as parentheses or brackets, to the display of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="16c4b-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="16c4b-127">Parent Elements</span></span>

|<span data-ttu-id="16c4b-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="16c4b-128">Element</span></span>|<span data-ttu-id="16c4b-129">Описание</span><span class="sxs-lookup"><span data-stu-id="16c4b-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="16c4b-130">Элемент Кустоментри для ошибка customcontrol для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="16c4b-130">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="16c4b-131">Предоставляет определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="16c4b-131">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="16c4b-132">Замечания</span><span class="sxs-lookup"><span data-stu-id="16c4b-132">Remarks</span></span>

<span data-ttu-id="16c4b-133">При указании дочерних элементов элемента `CustomItem` учитывайте следующее:</span><span class="sxs-lookup"><span data-stu-id="16c4b-133">When specifying the child elements of the `CustomItem` element, keep the following in mind:</span></span>

- <span data-ttu-id="16c4b-134">Дочерние элементы должны быть добавлены в следующей последовательности: `ExpressionBinding`, `NewLine`, `Text` и `Frame`.</span><span class="sxs-lookup"><span data-stu-id="16c4b-134">The child elements must be added in the following sequence: `ExpressionBinding`, `NewLine`, `Text`, and `Frame`.</span></span>

- <span data-ttu-id="16c4b-135">Максимальное число последовательностей, которое можно указать, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="16c4b-135">There is no maximum limit to the number of sequences that you can specify.</span></span>

- <span data-ttu-id="16c4b-136">В каждой последовательности нет максимального ограничения числа элементов `ExpressionBinding`, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="16c4b-136">In each sequence, there is no maximum limit to the number of `ExpressionBinding` elements that you can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="16c4b-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="16c4b-137">See Also</span></span>

[<span data-ttu-id="16c4b-138">Элемент ExpressionBinding для Кустомитем для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="16c4b-138">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="16c4b-139">Элемент Frame для элемента управления Кустомитем для Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="16c4b-139">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="16c4b-140">Элемент новой строки для элементов управления Кустомитем для Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="16c4b-140">NewLine Element for CustomItem for Controls for Configuration (Format)</span></span>](./newline-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="16c4b-141">Текстовый элемент для Кустомитем элементов управления для конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="16c4b-141">Text Element for CustomItem for Controls for Configuration (Format)</span></span>](./text-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="16c4b-142">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="16c4b-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
