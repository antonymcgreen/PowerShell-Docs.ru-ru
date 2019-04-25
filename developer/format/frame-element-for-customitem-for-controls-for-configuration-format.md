---
title: Рамку элемента CustomItem для элементов управления для конфигурации (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d879c8ce-679d-4622-bc43-c207f6413871
caps.latest.revision: 9
ms.openlocfilehash: b11b154a94daccead57bdfb5e579e1de2c190c09
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065569"
---
# <a name="frame-element-for-customitem-for-controls-for-configuration-format"></a><span data-ttu-id="366bd-102">Элемент Frame для элемента CustomItem для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="366bd-102">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>

<span data-ttu-id="366bd-103">Определяет способ отображения данных, таких как данные сдвига влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="366bd-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="366bd-104">Этот элемент используется при определении общего элемента управления, который может использоваться все представления в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="366bd-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="366bd-105">Конфигурации (формат) элементы управления элемента конфигурации (формат) элемента управления для элементов управления для элемента конфигурации (формат) пользовательский элемент управления для элемента управления для элемента конфигурации (формат) CustomEntries пользовательский элемент управления для конфигурации ( Элемент CustomEntry Format) для пользовательский элемент управления для элементов управления для элемента конфигурации (формат) CustomItem для CustomEntry для элементов управления для фрейма элемента конфигурации для CustomItem для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="366bd-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration Frame Element for CustomItem for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="366bd-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="366bd-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="366bd-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="366bd-107">Attributes and Elements</span></span>

<span data-ttu-id="366bd-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `Frame` элемент.</span><span class="sxs-lookup"><span data-stu-id="366bd-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="366bd-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="366bd-109">Attributes</span></span>

<span data-ttu-id="366bd-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="366bd-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="366bd-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="366bd-111">Child Elements</span></span>

|<span data-ttu-id="366bd-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="366bd-112">Element</span></span>|<span data-ttu-id="366bd-113">Описание</span><span class="sxs-lookup"><span data-stu-id="366bd-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="366bd-114">Обязательный элемент</span><span class="sxs-lookup"><span data-stu-id="366bd-114">Required Element</span></span>|
|[<span data-ttu-id="366bd-115">Элемент FirstLineHanging для кадра для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="366bd-115">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="366bd-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="366bd-116">Optional element.</span></span><br /><br /> <span data-ttu-id="366bd-117">Указывает количество символов, первая строка данных сдвигается влево.</span><span class="sxs-lookup"><span data-stu-id="366bd-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="366bd-118">Элемент FirstLineIndent для кадра для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="366bd-118">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="366bd-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="366bd-119">Optional element.</span></span><br /><br /> <span data-ttu-id="366bd-120">Указывает количество символов, первая строка данных сдвигается вправо.</span><span class="sxs-lookup"><span data-stu-id="366bd-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="366bd-121">Элемент LeftIndent для кадра для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="366bd-121">LeftIndent Element for Frame for Controls for Configuration (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="366bd-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="366bd-122">Optional element.</span></span><br /><br /> <span data-ttu-id="366bd-123">Указывает количество символов, данные сдвигается от левого поля.</span><span class="sxs-lookup"><span data-stu-id="366bd-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="366bd-124">Элемент RightIndent для кадра для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="366bd-124">RightIndent Element for Frame for Controls for Configuration (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="366bd-125">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="366bd-125">Optional element.</span></span><br /><br /> <span data-ttu-id="366bd-126">Указывает количество символов, данные сдвигается от правого поля.</span><span class="sxs-lookup"><span data-stu-id="366bd-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="366bd-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="366bd-127">Parent Elements</span></span>

|<span data-ttu-id="366bd-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="366bd-128">Element</span></span>|<span data-ttu-id="366bd-129">Описание</span><span class="sxs-lookup"><span data-stu-id="366bd-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="366bd-130">Элемент CustomItem для CustomEntry для элементов управления для конфигурации</span><span class="sxs-lookup"><span data-stu-id="366bd-130">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="366bd-131">Определяет, какие данные отображаются с помощью элемента управления и как он отображается.</span><span class="sxs-lookup"><span data-stu-id="366bd-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="366bd-132">Замечания</span><span class="sxs-lookup"><span data-stu-id="366bd-132">Remarks</span></span>

<span data-ttu-id="366bd-133">Нельзя указать [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) и [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) элементы в одном `Frame` элемент.</span><span class="sxs-lookup"><span data-stu-id="366bd-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="366bd-134">См. также</span><span class="sxs-lookup"><span data-stu-id="366bd-134">See Also</span></span>

[<span data-ttu-id="366bd-135">Элемент FirstLineHanging для кадра для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="366bd-135">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="366bd-136">Элемент FirstLineIndent для кадра для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="366bd-136">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="366bd-137">Элемент LeftIndent для кадра для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="366bd-137">LeftIndent Element for Frame for Controls for Configuration (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="366bd-138">Элемент RightIndent для кадра для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="366bd-138">RightIndent Element for Frame for Controls for Configuration (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="366bd-139">Элемент CustomItem для CustomEntry для элементов управления для конфигурации</span><span class="sxs-lookup"><span data-stu-id="366bd-139">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="366bd-140">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="366bd-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
