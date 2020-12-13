---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент Frame для элемента CustomItem для элемента Controls для элемента Configuration (формат)
description: Элемент Frame для элемента CustomItem для элемента Controls для элемента Configuration (формат)
ms.openlocfilehash: 85d095b9b0c25b68b2353bce56b85333aff91b98
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652247"
---
# <a name="frame-element-for-customitem-for-controls-for-configuration-format"></a><span data-ttu-id="4219a-103">Элемент Frame для элемента CustomItem для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="4219a-103">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>

<span data-ttu-id="4219a-104">Определяет способ отображения данных, например сдвиг данных влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="4219a-104">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="4219a-105">Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="4219a-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="4219a-106">Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления Configuration (Format) ошибка customcontrol для элемента Control for Configuration (Format) Кустоментриес элемента для ошибка customcontrol для элементов конфигурации (Format) Кустоментри для ошибка customcontrol for Controls для элемента конфигурации (Format) Кустомитем для кустоментри для элементов управления конфигурации (формат).</span><span class="sxs-lookup"><span data-stu-id="4219a-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration Frame Element for CustomItem for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4219a-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4219a-107">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4219a-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4219a-108">Attributes and Elements</span></span>

<span data-ttu-id="4219a-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Frame` элемента.</span><span class="sxs-lookup"><span data-stu-id="4219a-109">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4219a-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4219a-110">Attributes</span></span>

<span data-ttu-id="4219a-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4219a-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4219a-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4219a-112">Child Elements</span></span>

|<span data-ttu-id="4219a-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="4219a-113">Element</span></span>|<span data-ttu-id="4219a-114">Описание</span><span class="sxs-lookup"><span data-stu-id="4219a-114">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="4219a-115">Обязательный элемент</span><span class="sxs-lookup"><span data-stu-id="4219a-115">Required Element</span></span>|
|[<span data-ttu-id="4219a-116">Элемент FirstLineHanging для элемента Frame для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="4219a-116">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="4219a-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4219a-117">Optional element.</span></span><br /><br /> <span data-ttu-id="4219a-118">Указывает, сколько знаков первая строка данных смещается влево.</span><span class="sxs-lookup"><span data-stu-id="4219a-118">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="4219a-119">Элемент FirstLineIndent для элемента Frame для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="4219a-119">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="4219a-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4219a-120">Optional element.</span></span><br /><br /> <span data-ttu-id="4219a-121">Указывает, сколько знаков первая строка данных смещается вправо.</span><span class="sxs-lookup"><span data-stu-id="4219a-121">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="4219a-122">Элемент LeftIndent для элемента Frame для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="4219a-122">LeftIndent Element for Frame for Controls for Configuration (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="4219a-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4219a-123">Optional element.</span></span><br /><br /> <span data-ttu-id="4219a-124">Указывает, сколько символов перемещает данные из левого поля.</span><span class="sxs-lookup"><span data-stu-id="4219a-124">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="4219a-125">Элемент RightIndent для элемента Frame для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="4219a-125">RightIndent Element for Frame for Controls for Configuration (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="4219a-126">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4219a-126">Optional element.</span></span><br /><br /> <span data-ttu-id="4219a-127">Указывает, сколько символов перемещает данные с правого края.</span><span class="sxs-lookup"><span data-stu-id="4219a-127">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4219a-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4219a-128">Parent Elements</span></span>

|<span data-ttu-id="4219a-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="4219a-129">Element</span></span>|<span data-ttu-id="4219a-130">Описание</span><span class="sxs-lookup"><span data-stu-id="4219a-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4219a-131">Элемент Кустомитем для Кустоментри элементов управления для конфигурации</span><span class="sxs-lookup"><span data-stu-id="4219a-131">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="4219a-132">Определяет, какие данные отображаются элементом управления и как они отображаются.</span><span class="sxs-lookup"><span data-stu-id="4219a-132">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4219a-133">Комментарии</span><span class="sxs-lookup"><span data-stu-id="4219a-133">Remarks</span></span>

<span data-ttu-id="4219a-134">Нельзя указывать элементы [фирстлинехангинг](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) и [фирстлинеиндент](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) в одном и том же `Frame` элементе.</span><span class="sxs-lookup"><span data-stu-id="4219a-134">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="4219a-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="4219a-135">See Also</span></span>

[<span data-ttu-id="4219a-136">Элемент FirstLineHanging для элемента Frame для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="4219a-136">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="4219a-137">Элемент FirstLineIndent для элемента Frame для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="4219a-137">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="4219a-138">Элемент LeftIndent для элемента Frame для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="4219a-138">LeftIndent Element for Frame for Controls for Configuration (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="4219a-139">Элемент RightIndent для элемента Frame для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="4219a-139">RightIndent Element for Frame for Controls for Configuration (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="4219a-140">Элемент Кустомитем для Кустоментри элементов управления для конфигурации</span><span class="sxs-lookup"><span data-stu-id="4219a-140">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="4219a-141">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="4219a-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
