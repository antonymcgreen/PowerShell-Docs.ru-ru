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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854850"
---
# <a name="frame-element-for-customitem-for-groupby-format"></a><span data-ttu-id="3f053-102">Элемент Frame для элемента CustomItem для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="3f053-102">Frame Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="3f053-103">Определяет способ отображения данных, таких как данные сдвига влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="3f053-103">Defines how the data is displayed, such as shifting the data to the left or right.</span></span> <span data-ttu-id="3f053-104">Этот элемент используется при определении того, как отображается группу объектов.</span><span class="sxs-lookup"><span data-stu-id="3f053-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="3f053-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) пользовательский элемент управления для элемента CustomEntries GroupBy (формат) пользовательский элемент управления для элемента CustomEntry GroupBy (формат) Пользовательский элемент управления для элемента CustomItem GroupBy (формат) для CustomEntry элемента фрейма GroupBy (формат) для CustomItem для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="3f053-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) Frame Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3f053-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3f053-106">Syntax</span></span>

```xml
<Frame>
  <LeftIndent>NumberOfCharactersToShift</LeftIndent>
  <RightIndent>NumberOfCharactersToShift</RightIndent>
  <FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
  <FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
  <CustomItem>...</CustomItem>
</Frame>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3f053-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3f053-107">Attributes and Elements</span></span>

<span data-ttu-id="3f053-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `Frame` элемент.</span><span class="sxs-lookup"><span data-stu-id="3f053-108">The following sections describe attributes, child elements, and the parent element of the `Frame` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3f053-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3f053-109">Attributes</span></span>

<span data-ttu-id="3f053-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="3f053-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3f053-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3f053-111">Child Elements</span></span>

|<span data-ttu-id="3f053-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="3f053-112">Element</span></span>|<span data-ttu-id="3f053-113">Описание</span><span class="sxs-lookup"><span data-stu-id="3f053-113">Description</span></span>|
|-------------|-----------------|
|`CustomItem Element`|<span data-ttu-id="3f053-114">Обязательный элемент</span><span class="sxs-lookup"><span data-stu-id="3f053-114">Required Element</span></span>|
|[<span data-ttu-id="3f053-115">Элемент FirstLineHanging для кадра для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="3f053-115">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)|<span data-ttu-id="3f053-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3f053-116">Optional element.</span></span><br /><br /> <span data-ttu-id="3f053-117">Указывает количество символов, первая строка данных сдвигается влево.</span><span class="sxs-lookup"><span data-stu-id="3f053-117">Specifies how many characters the first line of data is shifted to the left.</span></span>|
|[<span data-ttu-id="3f053-118">Элемент FirstLineIndent для кадра для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="3f053-118">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="3f053-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3f053-119">Optional element.</span></span><br /><br /> <span data-ttu-id="3f053-120">Указывает количество символов, первая строка данных сдвигается вправо.</span><span class="sxs-lookup"><span data-stu-id="3f053-120">Specifies how many characters the first line of data is shifted to the right.</span></span>|
|[<span data-ttu-id="3f053-121">Элемент LeftIndent для кадра для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="3f053-121">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)|<span data-ttu-id="3f053-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3f053-122">Optional element.</span></span><br /><br /> <span data-ttu-id="3f053-123">Указывает количество символов, данные сдвигается от левого поля.</span><span class="sxs-lookup"><span data-stu-id="3f053-123">Specifies how many characters the data is shifted away from the left margin.</span></span>|
|<span data-ttu-id="3f053-124">[Элемент RightIndent для кадра для GroupBy (формат)](./rightindent-element-for-frame-for-groupby-format.md)RightIndent элемент</span><span class="sxs-lookup"><span data-stu-id="3f053-124">[RightIndent Element for Frame for GroupBy (Format)](./rightindent-element-for-frame-for-groupby-format.md)RightIndent Element</span></span>|<span data-ttu-id="3f053-125">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3f053-125">Optional element.</span></span><br /><br /> <span data-ttu-id="3f053-126">Указывает количество символов, данные сдвигается от правого поля.</span><span class="sxs-lookup"><span data-stu-id="3f053-126">Specifies how many characters the data is shifted away from the right margin.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="3f053-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3f053-127">Parent Elements</span></span>

|<span data-ttu-id="3f053-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="3f053-128">Element</span></span>|<span data-ttu-id="3f053-129">Описание</span><span class="sxs-lookup"><span data-stu-id="3f053-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3f053-130">Элемент CustomItem для CustomEntry для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="3f053-130">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="3f053-131">Определяет, какие данные отображаются с помощью элемента управления и как он отображается.</span><span class="sxs-lookup"><span data-stu-id="3f053-131">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3f053-132">Замечания</span><span class="sxs-lookup"><span data-stu-id="3f053-132">Remarks</span></span>

<span data-ttu-id="3f053-133">Нельзя указать [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) и [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) элементы в одном `Frame` элемент.</span><span class="sxs-lookup"><span data-stu-id="3f053-133">You cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) and the [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) elements in the same `Frame` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="3f053-134">См. также</span><span class="sxs-lookup"><span data-stu-id="3f053-134">See Also</span></span>

[<span data-ttu-id="3f053-135">Элемент FirstLineHanging для кадра для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="3f053-135">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="3f053-136">Элемент FirstLineIndent для кадра для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="3f053-136">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="3f053-137">Элемент LeftIndent для кадра для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="3f053-137">LeftIndent Element for Frame for GroupBy (Format)</span></span>](./leftindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="3f053-138">Элемент RightIndent для кадра для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="3f053-138">RightIndent Element for Frame for GroupBy (Format)</span></span>](./rightindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="3f053-139">Элемент CustomItem для CustomEntry для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="3f053-139">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="3f053-140">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f053-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
