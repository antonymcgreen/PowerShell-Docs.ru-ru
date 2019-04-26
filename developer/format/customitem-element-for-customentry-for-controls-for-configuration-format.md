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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066436"
---
# <a name="customitem-element-for-customentry-for-controls-for-configuration-format"></a><span data-ttu-id="d02ac-102">Элемент CustomItem для элемента CustomEntry для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="d02ac-102">CustomItem Element for CustomEntry for Controls for Configuration (Format)</span></span>

<span data-ttu-id="d02ac-103">Определяет, какие данные отображаются с помощью элемента управления и как он отображается.</span><span class="sxs-lookup"><span data-stu-id="d02ac-103">Defines what data is displayed by the control and how it is displayed.</span></span> <span data-ttu-id="d02ac-104">Этот элемент используется при определении общего элемента управления, который может использоваться все представления в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="d02ac-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="d02ac-105">Конфигурации (формат) элементы управления элемента конфигурации (формат) элемента управления для элементов управления для элемента конфигурации (формат) пользовательский элемент управления для элемента управления для элемента конфигурации (формат) CustomEntries пользовательский элемент управления для конфигурации ( Элемент CustomEntry Format) для пользовательский элемент управления для элементов управления для элемента конфигурации (формат) CustomItem для CustomEntry для элементов управления для конфигурации</span><span class="sxs-lookup"><span data-stu-id="d02ac-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration</span></span>

## <a name="syntax"></a><span data-ttu-id="d02ac-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d02ac-106">Syntax</span></span>

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <NewLine/>
  <Text>TextToDisplay</Text>
  <Frame>...</Frame>
</CustomItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d02ac-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d02ac-107">Attributes and Elements</span></span>

<span data-ttu-id="d02ac-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `CustomItem` элемент.</span><span class="sxs-lookup"><span data-stu-id="d02ac-108">The following sections describe attributes, child elements, and the parent element of the `CustomItem` element.</span></span> <span data-ttu-id="d02ac-109">Дополнительные сведения см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="d02ac-109">For more information, see Remarks.</span></span>

### <a name="attributes"></a><span data-ttu-id="d02ac-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d02ac-110">Attributes</span></span>

<span data-ttu-id="d02ac-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="d02ac-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d02ac-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d02ac-112">Child Elements</span></span>

|<span data-ttu-id="d02ac-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="d02ac-113">Element</span></span>|<span data-ttu-id="d02ac-114">Описание</span><span class="sxs-lookup"><span data-stu-id="d02ac-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d02ac-115">Элемент ExpressionBinding для CustomItem для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="d02ac-115">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="d02ac-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d02ac-116">Optional element.</span></span><br /><br /> <span data-ttu-id="d02ac-117">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="d02ac-117">Defines the data that is displayed by the control.</span></span>|
|[<span data-ttu-id="d02ac-118">Элемент Frame для CustomItem для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="d02ac-118">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="d02ac-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d02ac-119">Optional element.</span></span><br /><br /> <span data-ttu-id="d02ac-120">Определяет способ отображения данных, таких как данные сдвига влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="d02ac-120">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|
|[<span data-ttu-id="d02ac-121">Элемент новой строки для CustomItem для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="d02ac-121">NewLine Element for CustomItem for Controls for Configuration (Format)</span></span>](./newline-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="d02ac-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d02ac-122">Optional element.</span></span><br /><br /> <span data-ttu-id="d02ac-123">Добавляет пустой строки для отображения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d02ac-123">Adds a blank line to the display of the control.</span></span>|
|[<span data-ttu-id="d02ac-124">Текстовый элемент для CustomItem для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="d02ac-124">Text Element for CustomItem for Controls for Configuration (Format)</span></span>](./text-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="d02ac-125">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d02ac-125">Optional element.</span></span><br /><br /> <span data-ttu-id="d02ac-126">Добавляет текст, таких как круглые скобки или квадратные скобки, отображение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d02ac-126">Adds text, such as parentheses or brackets, to the display of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d02ac-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d02ac-127">Parent Elements</span></span>

|<span data-ttu-id="d02ac-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="d02ac-128">Element</span></span>|<span data-ttu-id="d02ac-129">Описание</span><span class="sxs-lookup"><span data-stu-id="d02ac-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d02ac-130">Элемент CustomEntry для пользовательский элемент управления для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="d02ac-130">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="d02ac-131">Предоставляет определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d02ac-131">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d02ac-132">Замечания</span><span class="sxs-lookup"><span data-stu-id="d02ac-132">Remarks</span></span>

<span data-ttu-id="d02ac-133">При указании дочерние элементы `CustomItem` элемент, имейте в виду следующее:</span><span class="sxs-lookup"><span data-stu-id="d02ac-133">When specifying the child elements of the `CustomItem` element, keep the following in mind:</span></span>

- <span data-ttu-id="d02ac-134">Дочерние элементы должны добавляться в следующей последовательности: `ExpressionBinding`, `NewLine`, `Text`, и `Frame`.</span><span class="sxs-lookup"><span data-stu-id="d02ac-134">The child elements must be added in the following sequence: `ExpressionBinding`, `NewLine`, `Text`, and `Frame`.</span></span>

- <span data-ttu-id="d02ac-135">Не ограничено максимальное число последовательности, которые можно указать.</span><span class="sxs-lookup"><span data-stu-id="d02ac-135">There is no maximum limit to the number of sequences that you can specify.</span></span>

- <span data-ttu-id="d02ac-136">В каждой последовательности не ограничено максимальное число `ExpressionBinding` элементы, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="d02ac-136">In each sequence, there is no maximum limit to the number of `ExpressionBinding` elements that you can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="d02ac-137">См. также</span><span class="sxs-lookup"><span data-stu-id="d02ac-137">See Also</span></span>

[<span data-ttu-id="d02ac-138">Элемент ExpressionBinding для CustomItem для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="d02ac-138">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="d02ac-139">Элемент Frame для CustomItem для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="d02ac-139">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="d02ac-140">Элемент новой строки для CustomItem для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="d02ac-140">NewLine Element for CustomItem for Controls for Configuration (Format)</span></span>](./newline-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="d02ac-141">Текстовый элемент для CustomItem для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="d02ac-141">Text Element for CustomItem for Controls for Configuration (Format)</span></span>](./text-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="d02ac-142">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="d02ac-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
