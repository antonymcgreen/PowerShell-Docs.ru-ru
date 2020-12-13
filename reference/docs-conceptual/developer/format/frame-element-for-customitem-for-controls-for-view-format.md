---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент Frame для элемента CustomItem для элемента Controls для элемента View (формат)
description: Элемент Frame для элемента CustomItem для элемента Controls для элемента View (формат)
ms.openlocfilehash: 6f26e19a6894ac213b924108a56cb80f9ffd1143
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652198"
---
# <a name="frame-element-for-customitem-for-controls-for-view-format"></a><span data-ttu-id="87085-103">Элемент Frame для элемента CustomItem для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="87085-103">Frame Element for CustomItem for Controls for View (Format)</span></span>

<span data-ttu-id="87085-104">Определяет способ отображения данных, например сдвиг данных влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="87085-104">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="87085-105">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="87085-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="87085-106">Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет управляющий элемент (Format) элемент управления для элементов управления представления (Format) ошибка customcontrol для элементов управления элемента Кустоментриес View (формат). для элемента Ошибка customcontrol для представления (Format) Кустоментри для Кустоментриес для элементов управления для представления (Format) Кустомитем элемента для Кустоментри для элементов управления элемента Frame (формат) для Кустомитем для элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="87085-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) Frame Element for CustomItem for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="87085-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="87085-107">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="87085-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="87085-108">Attributes and Elements</span></span>

<span data-ttu-id="87085-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Frame` элемента.</span><span class="sxs-lookup"><span data-stu-id="87085-109">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="87085-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="87085-110">Attributes</span></span>

<span data-ttu-id="87085-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="87085-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="87085-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="87085-112">Child Elements</span></span>

|<span data-ttu-id="87085-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="87085-113">Element</span></span>|<span data-ttu-id="87085-114">Описание</span><span class="sxs-lookup"><span data-stu-id="87085-114">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="87085-115">Обязательный элемент</span><span class="sxs-lookup"><span data-stu-id="87085-115">Required Element</span></span>|
|[<span data-ttu-id="87085-116">Элемент Фирстлинехангинг рамки элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="87085-116">FirstLineHanging Element of Frame of Controls of View (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="87085-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="87085-117">Optional element.</span></span><br /><br /> <span data-ttu-id="87085-118">Указывает, сколько знаков первая строка смещается влево.</span><span class="sxs-lookup"><span data-stu-id="87085-118">Specifies how many characters the first line is shifted to the left.</span></span>|
|[<span data-ttu-id="87085-119">Элемент Фирстлинеиндент рамки элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="87085-119">FirstLineIndent Element of Frame of Controls of View (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="87085-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="87085-120">Optional element.</span></span><br /><br /> <span data-ttu-id="87085-121">Указывает, сколько знаков первая строка смещается вправо.</span><span class="sxs-lookup"><span data-stu-id="87085-121">Specifies how many characters the first line is shifted to the right.</span></span>|
|[<span data-ttu-id="87085-122">Элемент Лефтиндент рамки элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="87085-122">LeftIndent Element of Frame of Controls of View (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="87085-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="87085-123">Optional element.</span></span><br /><br /> <span data-ttu-id="87085-124">Указывает, сколько символов перемещает данные из левого поля.</span><span class="sxs-lookup"><span data-stu-id="87085-124">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="87085-125">Элемент Ригхтиндент рамки элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="87085-125">RightIndent Element of Frame of Controls of View (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="87085-126">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="87085-126">Optional element.</span></span><br /><br /> <span data-ttu-id="87085-127">Указывает, сколько символов перемещает данные с правого края.</span><span class="sxs-lookup"><span data-stu-id="87085-127">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="87085-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="87085-128">Parent Elements</span></span>

|<span data-ttu-id="87085-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="87085-129">Element</span></span>|<span data-ttu-id="87085-130">Описание</span><span class="sxs-lookup"><span data-stu-id="87085-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="87085-131">Элемент CustomItem для элемента CustomEntry для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="87085-131">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="87085-132">Определяет, какие данные отображаются элементом управления и как они отображаются.</span><span class="sxs-lookup"><span data-stu-id="87085-132">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="87085-133">Комментарии</span><span class="sxs-lookup"><span data-stu-id="87085-133">Remarks</span></span>

<span data-ttu-id="87085-134">Нельзя указывать элементы [фирстлинехангинг](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) и [фирстлинеиндент](./firstlineindent-element-for-frame-for-controls-for-view-format.md) в одном и том же `Frame` элементе.</span><span class="sxs-lookup"><span data-stu-id="87085-134">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="87085-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="87085-135">See Also</span></span>

[<span data-ttu-id="87085-136">Элемент Фирстлинехангинг рамки элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="87085-136">FirstLineHanging Element of Frame of Controls of View (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="87085-137">Элемент Фирстлинеиндент рамки элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="87085-137">FirstLineIndent Element of Frame of Controls of View (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="87085-138">Элемент Лефтиндент рамки элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="87085-138">LeftIndent Element of Frame of Controls of View (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="87085-139">Элемент Ригхтиндент рамки элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="87085-139">RightIndent Element of Frame of Controls of View (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="87085-140">Элемент CustomItem для элемента CustomEntry для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="87085-140">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="87085-141">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="87085-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
