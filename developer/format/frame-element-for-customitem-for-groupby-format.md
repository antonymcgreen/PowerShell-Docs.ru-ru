---
title: Рамку элемента для CustomItem GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab2a5379-299d-4c97-86a2-b639ea890fae
caps.latest.revision: 6
ms.openlocfilehash: 7f9066c0fe0954fadff9dc8f0c35a62c6710f516
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065603"
---
# <a name="frame-element-for-customitem-for-groupby-format"></a><span data-ttu-id="5d799-102">Элемент Frame для элемента CustomItem для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5d799-102">Frame Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="5d799-103">Определяет способ отображения данных, таких как данные сдвига влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="5d799-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="5d799-104">Этот элемент используется при определении того, как отображается группу объектов.</span><span class="sxs-lookup"><span data-stu-id="5d799-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="5d799-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) пользовательский элемент управления для элемента CustomEntries GroupBy (формат) пользовательский элемент управления для элемента CustomEntry GroupBy (формат) Пользовательский элемент управления для элемента CustomItem GroupBy (формат) для CustomEntry элемента фрейма GroupBy (формат) для CustomItem для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5d799-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) Frame Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5d799-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d799-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5d799-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5d799-107">Attributes and Elements</span></span>

<span data-ttu-id="5d799-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `Frame` элемент.</span><span class="sxs-lookup"><span data-stu-id="5d799-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5d799-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5d799-109">Attributes</span></span>

<span data-ttu-id="5d799-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="5d799-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5d799-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5d799-111">Child Elements</span></span>

|<span data-ttu-id="5d799-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="5d799-112">Element</span></span>|<span data-ttu-id="5d799-113">Описание</span><span class="sxs-lookup"><span data-stu-id="5d799-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="5d799-114">Обязательный элемент</span><span class="sxs-lookup"><span data-stu-id="5d799-114">Required Element</span></span>|
|[<span data-ttu-id="5d799-115">Элемент FirstLineHanging для кадра для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5d799-115">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)|<span data-ttu-id="5d799-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="5d799-116">Optional element.</span></span><br /><br /> <span data-ttu-id="5d799-117">Указывает количество символов, первая строка данных сдвигается влево.</span><span class="sxs-lookup"><span data-stu-id="5d799-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="5d799-118">Элемент FirstLineIndent для кадра для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5d799-118">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="5d799-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="5d799-119">Optional element.</span></span><br /><br /> <span data-ttu-id="5d799-120">Указывает количество символов, первая строка данных сдвигается вправо.</span><span class="sxs-lookup"><span data-stu-id="5d799-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="5d799-121">Элемент LeftIndent для кадра для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5d799-121">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="5d799-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="5d799-122">Optional element.</span></span><br /><br /> <span data-ttu-id="5d799-123">Указывает количество символов, данные сдвигается от левого поля.</span><span class="sxs-lookup"><span data-stu-id="5d799-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|<span data-ttu-id="5d799-124">[Элемент RightIndent для кадра для GroupBy (формат)](./rightindent-element-for-frame-for-groupby-format.md)RightIndent элемент</span><span class="sxs-lookup"><span data-stu-id="5d799-124">[RightIndent Element for Frame for GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md)RightIndent Element</span></span>|<span data-ttu-id="5d799-125">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="5d799-125">Optional element.</span></span><br /><br /> <span data-ttu-id="5d799-126">Указывает количество символов, данные сдвигается от правого поля.</span><span class="sxs-lookup"><span data-stu-id="5d799-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5d799-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5d799-127">Parent Elements</span></span>

|<span data-ttu-id="5d799-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="5d799-128">Element</span></span>|<span data-ttu-id="5d799-129">Описание</span><span class="sxs-lookup"><span data-stu-id="5d799-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5d799-130">Элемент CustomItem для CustomEntry для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5d799-130">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="5d799-131">Определяет, какие данные отображаются с помощью элемента управления и как он отображается.</span><span class="sxs-lookup"><span data-stu-id="5d799-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5d799-132">Замечания</span><span class="sxs-lookup"><span data-stu-id="5d799-132">Remarks</span></span>

<span data-ttu-id="5d799-133">Нельзя указать [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) и [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) элементы в одном `Frame` элемент.</span><span class="sxs-lookup"><span data-stu-id="5d799-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="5d799-134">См. также</span><span class="sxs-lookup"><span data-stu-id="5d799-134">See Also</span></span>

[<span data-ttu-id="5d799-135">Элемент FirstLineHanging для кадра для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5d799-135">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="5d799-136">Элемент FirstLineIndent для кадра для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5d799-136">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="5d799-137">Элемент LeftIndent для кадра для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5d799-137">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="5d799-138">Элемент RightIndent для кадра для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5d799-138">RightIndent Element for Frame for GroupBy (Format)</span></span>](./rightindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="5d799-139">Элемент CustomItem для CustomEntry для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5d799-139">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="5d799-140">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="5d799-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
