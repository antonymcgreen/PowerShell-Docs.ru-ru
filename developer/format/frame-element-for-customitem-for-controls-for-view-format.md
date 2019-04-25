---
title: Рамку элемента CustomItem для элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5729091-78a9-4bc1-abac-210bc20c6dbe
caps.latest.revision: 7
ms.openlocfilehash: f93dc20a9c5f87c14605578062b1e60f5a3d25cf
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065722"
---
# <a name="frame-element-for-customitem-for-controls-for-view-format"></a><span data-ttu-id="d97e6-102">Элемент Frame для элемента CustomItem для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="d97e6-102">Frame Element for CustomItem for Controls for View (Format)</span></span>

<span data-ttu-id="d97e6-103">Определяет способ отображения данных, таких как данные сдвига влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="d97e6-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="d97e6-104">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="d97e6-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="d97e6-105">Конфигурации элемента (формат) элемент ViewDefinitions (формат) представление элемента (формат) элементы управления элемента (формат) элемент управления для элементов управления для элемента представления (формат) пользовательский элемент управления для элемента управления для элементов управления для элемента CustomEntries представления (формат) для Пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для элементов управления для элемента представления (формат) CustomItem для CustomEntry для элементов управления для элемента представления (формат) кадра для CustomItem для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="d97e6-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) Frame Element for CustomItem for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d97e6-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d97e6-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d97e6-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d97e6-107">Attributes and Elements</span></span>

<span data-ttu-id="d97e6-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `Frame` элемент.</span><span class="sxs-lookup"><span data-stu-id="d97e6-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d97e6-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d97e6-109">Attributes</span></span>

<span data-ttu-id="d97e6-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="d97e6-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d97e6-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d97e6-111">Child Elements</span></span>

|<span data-ttu-id="d97e6-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="d97e6-112">Element</span></span>|<span data-ttu-id="d97e6-113">Описание</span><span class="sxs-lookup"><span data-stu-id="d97e6-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="d97e6-114">Обязательный элемент</span><span class="sxs-lookup"><span data-stu-id="d97e6-114">Required Element</span></span>|
|[<span data-ttu-id="d97e6-115">Элемент FirstLineHanging кадра элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="d97e6-115">FirstLineHanging Element of Frame of Controls of View (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="d97e6-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d97e6-116">Optional element.</span></span><br /><br /> <span data-ttu-id="d97e6-117">Указывает количество символов, первая строка сдвигается влево.</span><span class="sxs-lookup"><span data-stu-id="d97e6-117">Specifies how many characters the first line is shifted to the left.</span></span>|
|[<span data-ttu-id="d97e6-118">Элемент FirstLineIndent кадра элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="d97e6-118">FirstLineIndent Element of Frame of Controls of View (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="d97e6-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d97e6-119">Optional element.</span></span><br /><br /> <span data-ttu-id="d97e6-120">Указывает количество символов, первая строка сдвигается вправо.</span><span class="sxs-lookup"><span data-stu-id="d97e6-120">Specifies how many characters the first line is shifted to the right.</span></span>|
|[<span data-ttu-id="d97e6-121">Элемент LeftIndent кадра элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="d97e6-121">LeftIndent Element of Frame of Controls of View (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="d97e6-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d97e6-122">Optional element.</span></span><br /><br /> <span data-ttu-id="d97e6-123">Указывает количество символов, данные сдвигается от левого поля.</span><span class="sxs-lookup"><span data-stu-id="d97e6-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="d97e6-124">Элемент RightIndent кадра элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="d97e6-124">RightIndent Element of Frame of Controls of View (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-view-format.md)|<span data-ttu-id="d97e6-125">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d97e6-125">Optional element.</span></span><br /><br /> <span data-ttu-id="d97e6-126">Указывает количество символов, данные сдвигается от правого поля.</span><span class="sxs-lookup"><span data-stu-id="d97e6-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d97e6-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d97e6-127">Parent Elements</span></span>

|<span data-ttu-id="d97e6-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="d97e6-128">Element</span></span>|<span data-ttu-id="d97e6-129">Описание</span><span class="sxs-lookup"><span data-stu-id="d97e6-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d97e6-130">Элемент CustomItem для CustomEntry для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="d97e6-130">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="d97e6-131">Определяет, какие данные отображаются с помощью элемента управления и как он отображается.</span><span class="sxs-lookup"><span data-stu-id="d97e6-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d97e6-132">Замечания</span><span class="sxs-lookup"><span data-stu-id="d97e6-132">Remarks</span></span>

<span data-ttu-id="d97e6-133">Нельзя указать [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) и [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md) элементы в одном `Frame` элемент.</span><span class="sxs-lookup"><span data-stu-id="d97e6-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="d97e6-134">См. также</span><span class="sxs-lookup"><span data-stu-id="d97e6-134">See Also</span></span>

[<span data-ttu-id="d97e6-135">Элемент FirstLineHanging кадра элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="d97e6-135">FirstLineHanging Element of Frame of Controls of View (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="d97e6-136">Элемент FirstLineIndent кадра элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="d97e6-136">FirstLineIndent Element of Frame of Controls of View (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="d97e6-137">Элемент LeftIndent кадра элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="d97e6-137">LeftIndent Element of Frame of Controls of View (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="d97e6-138">Элемент RightIndent кадра элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="d97e6-138">RightIndent Element of Frame of Controls of View (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="d97e6-139">Элемент CustomItem для CustomEntry для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="d97e6-139">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="d97e6-140">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="d97e6-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
