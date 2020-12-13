---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент Frame для элемента CustomItem для элемента GroupBy (формат)
description: Элемент Frame для элемента CustomItem для элемента GroupBy (формат)
ms.openlocfilehash: 86b51766974ebfcae06583ade237a77c6db92866
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652176"
---
# <a name="frame-element-for-customitem-for-groupby-format"></a><span data-ttu-id="714e2-103">Элемент Frame для элемента CustomItem для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="714e2-103">Frame Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="714e2-104">Определяет способ отображения данных, например сдвиг данных влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="714e2-104">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="714e2-105">Этот элемент используется при определении того, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="714e2-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="714e2-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент GroupBy для элемента "View" (Format) ошибка customcontrol для элемента GroupBy (Format) Кустоментриес для ошибка customcontrol for GroupBy (формат) кустоментри элемент для ошибка customcontrol for GroupBy (формат) кустомитем для кустоментри для кустомитем для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="714e2-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) Frame Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="714e2-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="714e2-107">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="714e2-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="714e2-108">Attributes and Elements</span></span>

<span data-ttu-id="714e2-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Frame` элемента.</span><span class="sxs-lookup"><span data-stu-id="714e2-109">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="714e2-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="714e2-110">Attributes</span></span>

<span data-ttu-id="714e2-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="714e2-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="714e2-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="714e2-112">Child Elements</span></span>

|<span data-ttu-id="714e2-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="714e2-113">Element</span></span>|<span data-ttu-id="714e2-114">Описание</span><span class="sxs-lookup"><span data-stu-id="714e2-114">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="714e2-115">Обязательный элемент</span><span class="sxs-lookup"><span data-stu-id="714e2-115">Required Element</span></span>|
|[<span data-ttu-id="714e2-116">Элемент FirstLineHanging для элемента Frame для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="714e2-116">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)|<span data-ttu-id="714e2-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="714e2-117">Optional element.</span></span><br /><br /> <span data-ttu-id="714e2-118">Указывает, сколько знаков первая строка данных смещается влево.</span><span class="sxs-lookup"><span data-stu-id="714e2-118">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="714e2-119">Элемент FirstLineIndent для элемента Frame для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="714e2-119">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="714e2-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="714e2-120">Optional element.</span></span><br /><br /> <span data-ttu-id="714e2-121">Указывает, сколько знаков первая строка данных смещается вправо.</span><span class="sxs-lookup"><span data-stu-id="714e2-121">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="714e2-122">Элемент LeftIndent для элемента Frame для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="714e2-122">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="714e2-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="714e2-123">Optional element.</span></span><br /><br /> <span data-ttu-id="714e2-124">Указывает, сколько символов перемещает данные из левого поля.</span><span class="sxs-lookup"><span data-stu-id="714e2-124">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|<span data-ttu-id="714e2-125">[Элемент ригхтиндент для Frame для GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md) Ригхтиндент, элемент</span><span class="sxs-lookup"><span data-stu-id="714e2-125">[RightIndent Element for Frame for GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md)RightIndent Element</span></span>|<span data-ttu-id="714e2-126">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="714e2-126">Optional element.</span></span><br /><br /> <span data-ttu-id="714e2-127">Указывает, сколько символов перемещает данные с правого края.</span><span class="sxs-lookup"><span data-stu-id="714e2-127">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="714e2-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="714e2-128">Parent Elements</span></span>

|<span data-ttu-id="714e2-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="714e2-129">Element</span></span>|<span data-ttu-id="714e2-130">Описание</span><span class="sxs-lookup"><span data-stu-id="714e2-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="714e2-131">Элемент CustomItem для элемента CustomEntry для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="714e2-131">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="714e2-132">Определяет, какие данные отображаются элементом управления и как они отображаются.</span><span class="sxs-lookup"><span data-stu-id="714e2-132">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="714e2-133">Комментарии</span><span class="sxs-lookup"><span data-stu-id="714e2-133">Remarks</span></span>

<span data-ttu-id="714e2-134">Нельзя указывать элементы [фирстлинехангинг](./firstlinehanging-element-for-frame-for-groupby-format.md) и [фирстлинеиндент](./firstlineindent-element-for-frame-for-groupby-format.md) в одном и том же `Frame` элементе.</span><span class="sxs-lookup"><span data-stu-id="714e2-134">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="714e2-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="714e2-135">See Also</span></span>

[<span data-ttu-id="714e2-136">Элемент FirstLineHanging для элемента Frame для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="714e2-136">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="714e2-137">Элемент FirstLineIndent для элемента Frame для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="714e2-137">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="714e2-138">Элемент LeftIndent для элемента Frame для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="714e2-138">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="714e2-139">Элемент RightIndent для элемента Frame для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="714e2-139">RightIndent Element for Frame for GroupBy (Format)</span></span>](./rightindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="714e2-140">Элемент CustomItem для элемента CustomEntry для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="714e2-140">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="714e2-141">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="714e2-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
