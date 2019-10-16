---
title: Элемент Frame для элемента управления Кустомитем для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5729091-78a9-4bc1-abac-210bc20c6dbe
caps.latest.revision: 7
ms.openlocfilehash: f93dc20a9c5f87c14605578062b1e60f5a3d25cf
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363653"
---
# <a name="frame-element-for-customitem-for-controls-for-view-format"></a><span data-ttu-id="f4c87-102">Элемент Frame для элемента CustomItem для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="f4c87-102">Frame Element for CustomItem for Controls for View (Format)</span></span>

<span data-ttu-id="f4c87-103">Определяет способ отображения данных, например сдвиг данных влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="f4c87-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="f4c87-104">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="f4c87-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="f4c87-105">Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет управляющий элемент (Format) элемент управления для элементов управления представления (Format) ошибка customcontrol для элементов управления элемента Кустоментриес представления (Format) для Ошибка customcontrol для элемента Кустоментри представления (Format) Кустоментриес для элементов управления для элемента Controls представления (Format) Кустомитем для Кустоментри для элементов управления элемента Frame (формат) для кустомитем для элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f4c87-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) Frame Element for CustomItem for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f4c87-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f4c87-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f4c87-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f4c87-107">Attributes and Elements</span></span>

<span data-ttu-id="f4c87-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `Frame`.</span><span class="sxs-lookup"><span data-stu-id="f4c87-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f4c87-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f4c87-109">Attributes</span></span>

<span data-ttu-id="f4c87-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="f4c87-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f4c87-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f4c87-111">Child Elements</span></span>

|<span data-ttu-id="f4c87-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="f4c87-112">Element</span></span>|<span data-ttu-id="f4c87-113">Описание</span><span class="sxs-lookup"><span data-stu-id="f4c87-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="f4c87-114">Обязательный элемент</span><span class="sxs-lookup"><span data-stu-id="f4c87-114">Required Element</span></span>|
|[<span data-ttu-id="f4c87-115">Элемент Фирстлинехангинг рамки элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f4c87-115">FirstLineHanging Element of Frame of Controls of View (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="f4c87-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f4c87-116">Optional element.</span></span><br /><br /> <span data-ttu-id="f4c87-117">Указывает, сколько знаков первая строка смещается влево.</span><span class="sxs-lookup"><span data-stu-id="f4c87-117">Specifies how many characters the first line is shifted to the left.</span></span>|
|[<span data-ttu-id="f4c87-118">Элемент Фирстлинеиндент рамки элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f4c87-118">FirstLineIndent Element of Frame of Controls of View (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="f4c87-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f4c87-119">Optional element.</span></span><br /><br /> <span data-ttu-id="f4c87-120">Указывает, сколько знаков первая строка смещается вправо.</span><span class="sxs-lookup"><span data-stu-id="f4c87-120">Specifies how many characters the first line is shifted to the right.</span></span>|
|[<span data-ttu-id="f4c87-121">Элемент Лефтиндент рамки элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f4c87-121">LeftIndent Element of Frame of Controls of View (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="f4c87-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f4c87-122">Optional element.</span></span><br /><br /> <span data-ttu-id="f4c87-123">Указывает, сколько символов перемещает данные из левого поля.</span><span class="sxs-lookup"><span data-stu-id="f4c87-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="f4c87-124">Элемент Ригхтиндент рамки элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f4c87-124">RightIndent Element of Frame of Controls of View (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="f4c87-125">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f4c87-125">Optional element.</span></span><br /><br /> <span data-ttu-id="f4c87-126">Указывает, сколько символов перемещает данные с правого края.</span><span class="sxs-lookup"><span data-stu-id="f4c87-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f4c87-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f4c87-127">Parent Elements</span></span>

|<span data-ttu-id="f4c87-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="f4c87-128">Element</span></span>|<span data-ttu-id="f4c87-129">Описание</span><span class="sxs-lookup"><span data-stu-id="f4c87-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f4c87-130">Элемент Кустомитем для Кустоментри элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f4c87-130">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="f4c87-131">Определяет, какие данные отображаются элементом управления и как они отображаются.</span><span class="sxs-lookup"><span data-stu-id="f4c87-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f4c87-132">Замечания</span><span class="sxs-lookup"><span data-stu-id="f4c87-132">Remarks</span></span>

<span data-ttu-id="f4c87-133">Нельзя указывать элементы [фирстлинехангинг](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) и [фирстлинеиндент](./firstlineindent-element-for-frame-for-controls-for-view-format.md) в одном элементе `Frame`.</span><span class="sxs-lookup"><span data-stu-id="f4c87-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4c87-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="f4c87-134">See Also</span></span>

[<span data-ttu-id="f4c87-135">Элемент Фирстлинехангинг рамки элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f4c87-135">FirstLineHanging Element of Frame of Controls of View (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="f4c87-136">Элемент Фирстлинеиндент рамки элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f4c87-136">FirstLineIndent Element of Frame of Controls of View (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="f4c87-137">Элемент Лефтиндент рамки элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f4c87-137">LeftIndent Element of Frame of Controls of View (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="f4c87-138">Элемент Ригхтиндент рамки элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f4c87-138">RightIndent Element of Frame of Controls of View (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="f4c87-139">Элемент Кустомитем для Кустоментри элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f4c87-139">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="f4c87-140">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4c87-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
