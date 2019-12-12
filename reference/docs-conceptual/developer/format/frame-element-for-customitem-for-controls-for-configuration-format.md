---
title: Элемент Frame для Кустомитем элементов управления в конфигурации (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d879c8ce-679d-4622-bc43-c207f6413871
caps.latest.revision: 9
ms.openlocfilehash: b11b154a94daccead57bdfb5e579e1de2c190c09
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363663"
---
# <a name="frame-element-for-customitem-for-controls-for-configuration-format"></a><span data-ttu-id="8eb40-102">Элемент Frame для элемента CustomItem для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="8eb40-102">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>

<span data-ttu-id="8eb40-103">Определяет способ отображения данных, например сдвиг данных влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="8eb40-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="8eb40-104">Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="8eb40-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="8eb40-105">Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control в конфигурации (Format) Кустоментриес для ошибка customcontrol для конфигурации ( Формат) элемент Кустоментри для ошибка customcontrol элементов управления для элемента конфигурации (Format) Кустомитем для Кустоментри для элементов управления для элемента конфигурации Кустомитем для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="8eb40-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration Frame Element for CustomItem for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8eb40-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8eb40-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8eb40-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8eb40-107">Attributes and Elements</span></span>

<span data-ttu-id="8eb40-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `Frame`.</span><span class="sxs-lookup"><span data-stu-id="8eb40-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8eb40-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8eb40-109">Attributes</span></span>

<span data-ttu-id="8eb40-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="8eb40-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8eb40-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8eb40-111">Child Elements</span></span>

|<span data-ttu-id="8eb40-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="8eb40-112">Element</span></span>|<span data-ttu-id="8eb40-113">Описание</span><span class="sxs-lookup"><span data-stu-id="8eb40-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="8eb40-114">Обязательный элемент</span><span class="sxs-lookup"><span data-stu-id="8eb40-114">Required Element</span></span>|
|[<span data-ttu-id="8eb40-115">Элемент Фирстлинехангинг для Frame для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="8eb40-115">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="8eb40-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="8eb40-116">Optional element.</span></span><br /><br /> <span data-ttu-id="8eb40-117">Указывает, сколько знаков первая строка данных смещается влево.</span><span class="sxs-lookup"><span data-stu-id="8eb40-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="8eb40-118">Элемент Фирстлинеиндент для Frame для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="8eb40-118">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="8eb40-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="8eb40-119">Optional element.</span></span><br /><br /> <span data-ttu-id="8eb40-120">Указывает, сколько знаков первая строка данных смещается вправо.</span><span class="sxs-lookup"><span data-stu-id="8eb40-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="8eb40-121">Элемент Лефтиндент для Frame для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="8eb40-121">LeftIndent Element for Frame for Controls for Configuration (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="8eb40-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="8eb40-122">Optional element.</span></span><br /><br /> <span data-ttu-id="8eb40-123">Указывает, сколько символов перемещает данные из левого поля.</span><span class="sxs-lookup"><span data-stu-id="8eb40-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|[<span data-ttu-id="8eb40-124">Элемент Ригхтиндент для Frame для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="8eb40-124">RightIndent Element for Frame for Controls for Configuration (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-configuration-format.md)|<span data-ttu-id="8eb40-125">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="8eb40-125">Optional element.</span></span><br /><br /> <span data-ttu-id="8eb40-126">Указывает, сколько символов перемещает данные с правого края.</span><span class="sxs-lookup"><span data-stu-id="8eb40-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="8eb40-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8eb40-127">Parent Elements</span></span>

|<span data-ttu-id="8eb40-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="8eb40-128">Element</span></span>|<span data-ttu-id="8eb40-129">Описание</span><span class="sxs-lookup"><span data-stu-id="8eb40-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8eb40-130">Элемент Кустомитем для Кустоментри элементов управления для конфигурации</span><span class="sxs-lookup"><span data-stu-id="8eb40-130">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="8eb40-131">Определяет, какие данные отображаются элементом управления и как они отображаются.</span><span class="sxs-lookup"><span data-stu-id="8eb40-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8eb40-132">Замечания</span><span class="sxs-lookup"><span data-stu-id="8eb40-132">Remarks</span></span>

<span data-ttu-id="8eb40-133">Нельзя указывать элементы [фирстлинехангинг](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) и [фирстлинеиндент](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) в одном элементе `Frame`.</span><span class="sxs-lookup"><span data-stu-id="8eb40-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="8eb40-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="8eb40-134">See Also</span></span>

[<span data-ttu-id="8eb40-135">Элемент Фирстлинехангинг для Frame для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="8eb40-135">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="8eb40-136">Элемент Фирстлинеиндент для Frame для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="8eb40-136">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="8eb40-137">Элемент Лефтиндент для Frame для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="8eb40-137">LeftIndent Element for Frame for Controls for Configuration (Format)</span></span>](./leftindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="8eb40-138">Элемент Ригхтиндент для Frame для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="8eb40-138">RightIndent Element for Frame for Controls for Configuration (Format)</span></span>](./rightindent-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="8eb40-139">Элемент Кустомитем для Кустоментри элементов управления для конфигурации</span><span class="sxs-lookup"><span data-stu-id="8eb40-139">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="8eb40-140">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="8eb40-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
