---
title: Элемент CustomItem для CustomEntry для элементов управления для конфигурации (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73fb11ee-0ebd-477a-ac36-acdfbb32e70d
caps.latest.revision: 7
ms.openlocfilehash: bd0cb69770817ec215ddb1862a43a838baddefcf
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862940"
---
# <a name="customitem-element-for-customentry-for-controls-for-configuration-format"></a><span data-ttu-id="ed378-102">Элемент CustomItem для элемента CustomEntry для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="ed378-102">CustomItem Element for CustomEntry for Controls for Configuration (Format)</span></span>

<span data-ttu-id="ed378-103">Определяет, какие данные отображаются с помощью элемента управления и как он отображается.</span><span class="sxs-lookup"><span data-stu-id="ed378-103">Defines what data is displayed by the control and how it is displayed.</span></span> <span data-ttu-id="ed378-104">Этот элемент используется при определении общего элемента управления, который может использоваться все представления в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="ed378-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="ed378-105">Конфигурации (формат) элементы управления элемента конфигурации (формат) элемента управления для элементов управления для элемента конфигурации (формат) пользовательский элемент управления для элемента управления для элемента конфигурации (формат) CustomEntries пользовательский элемент управления для конфигурации ( Элемент CustomEntry Format) для пользовательский элемент управления для элементов управления для элемента конфигурации (формат) CustomItem для CustomEntry для элементов управления для конфигурации</span><span class="sxs-lookup"><span data-stu-id="ed378-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration</span></span>

## <a name="syntax"></a><span data-ttu-id="ed378-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ed378-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...</Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ed378-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ed378-107">Attributes and Elements</span></span>

<span data-ttu-id="ed378-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `CustomItem` элемент.</span><span class="sxs-lookup"><span data-stu-id="ed378-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span> <span data-ttu-id="ed378-109">Дополнительные сведения см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="ed378-109">For more information, see Remarks.</span></span>

### <a name="attributes"></a><span data-ttu-id="ed378-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ed378-110">Attributes</span></span>

<span data-ttu-id="ed378-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="ed378-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ed378-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ed378-112">Child Elements</span></span>

|<span data-ttu-id="ed378-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="ed378-113">Element</span></span>|<span data-ttu-id="ed378-114">Описание</span><span class="sxs-lookup"><span data-stu-id="ed378-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ed378-115">Элемент ExpressionBinding для CustomItem для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="ed378-115">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="ed378-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ed378-116">Optional element.</span></span><br /><br /> <span data-ttu-id="ed378-117">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="ed378-117">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="ed378-118">Элемент Frame для CustomItem для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="ed378-118">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="ed378-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ed378-119">Optional element.</span></span><br /><br /> <span data-ttu-id="ed378-120">Определяет способ отображения данных, таких как данные сдвига влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="ed378-120">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|
|[<span data-ttu-id="ed378-121">Элемент новой строки для CustomItem для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="ed378-121">NewLine Element for CustomItem for Controls for Configuration (Format)</span></span>](./newline-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="ed378-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ed378-122">Optional element.</span></span><br /><br /> <span data-ttu-id="ed378-123">Добавляет пустой строки для отображения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ed378-123">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="ed378-124">Текстовый элемент для CustomItem для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="ed378-124">Text Element for CustomItem for Controls for Configuration (Format)</span></span>](./text-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="ed378-125">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ed378-125">Optional element.</span></span><br /><br /> <span data-ttu-id="ed378-126">Добавляет текст, таких как круглые скобки или квадратные скобки, отображение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ed378-126">Adds text, such as parentheses or brackets, to the display of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ed378-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ed378-127">Parent Elements</span></span>

|<span data-ttu-id="ed378-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="ed378-128">Element</span></span>|<span data-ttu-id="ed378-129">Описание</span><span class="sxs-lookup"><span data-stu-id="ed378-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ed378-130">Элемент CustomEntry для пользовательский элемент управления для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="ed378-130">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="ed378-131">Предоставляет определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ed378-131">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ed378-132">Замечания</span><span class="sxs-lookup"><span data-stu-id="ed378-132">Remarks</span></span>

<span data-ttu-id="ed378-133">При указании дочерние элементы `CustomItem` элемент, имейте в виду следующее:</span><span class="sxs-lookup"><span data-stu-id="ed378-133">When specifying the child elements of the `CustomItem` element, keep the following in mind:</span></span>

- <span data-ttu-id="ed378-134">Дочерние элементы должны добавляться в следующей последовательности: `ExpressionBinding`, `NewLine`, `Text`, и `Frame`.</span><span class="sxs-lookup"><span data-stu-id="ed378-134">The child elements must be added in the following sequence: `ExpressionBinding`, `NewLine`, `Text`, and `Frame`.</span></span>

- <span data-ttu-id="ed378-135">Не ограничено максимальное число последовательности, которые можно указать.</span><span class="sxs-lookup"><span data-stu-id="ed378-135">There is no maximum limit to the number of sequences that you can specify.</span></span>

- <span data-ttu-id="ed378-136">В каждой последовательности не ограничено максимальное число `ExpressionBinding` элементы, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="ed378-136">In each sequence, there is no maximum limit to the number of `ExpressionBinding` elements that you can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed378-137">См. также</span><span class="sxs-lookup"><span data-stu-id="ed378-137">See Also</span></span>

[<span data-ttu-id="ed378-138">Элемент ExpressionBinding для CustomItem для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="ed378-138">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="ed378-139">Элемент Frame для CustomItem для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="ed378-139">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="ed378-140">Элемент новой строки для CustomItem для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="ed378-140">NewLine Element for CustomItem for Controls for Configuration (Format)</span></span>](./newline-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="ed378-141">Текстовый элемент для CustomItem для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="ed378-141">Text Element for CustomItem for Controls for Configuration (Format)</span></span>](./text-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="ed378-142">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed378-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
