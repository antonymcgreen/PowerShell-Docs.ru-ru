---
title: Элемент FirstLineHanging для кадра для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1cdcf66e-96a5-47b5-9269-b4330bde29f2
caps.latest.revision: 6
ms.openlocfilehash: 08db1f2d89c3fe6c1e9a5a522de3071425042c3f
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855620"
---
# <a name="firstlinehanging-element-for-frame-for-groupby-format"></a><span data-ttu-id="96767-102">Элемент FirstLineHanging для элемента Frame для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="96767-102">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>

<span data-ttu-id="96767-103">Указывает количество символов, первая строка данных сдвигается влево.</span><span class="sxs-lookup"><span data-stu-id="96767-103">Specifies how many characters the first line of data is shifted to the left.</span></span> <span data-ttu-id="96767-104">Этот элемент используется при определении того, как отображается группу объектов.</span><span class="sxs-lookup"><span data-stu-id="96767-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="96767-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) пользовательский элемент управления для элемента CustomEntries GroupBy (формат) пользовательский элемент управления для элемента CustomEntry GroupBy (формат) Пользовательский элемент управления для элемента CustomItem GroupBy (формат) для CustomEntry элемента фрейма GroupBy (формат) для CustomItem для элемента FirstLineHanging GroupBy (формат) для кадра для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="96767-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) Frame Element for CustomItem for GroupBy (Format) FirstLineHanging Element for Frame for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="96767-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="96767-106">Syntax</span></span>

```xml
<FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="96767-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="96767-107">Attributes and Elements</span></span>

<span data-ttu-id="96767-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `FirstLineHanging` элемент.</span><span class="sxs-lookup"><span data-stu-id="96767-108">The following sections describe attributes, child elements, and parent element of the `FirstLineHanging` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="96767-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="96767-109">Attributes</span></span>

<span data-ttu-id="96767-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="96767-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="96767-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="96767-111">Child Elements</span></span>

<span data-ttu-id="96767-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="96767-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="96767-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="96767-113">Parent Elements</span></span>

|<span data-ttu-id="96767-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="96767-114">Element</span></span>|<span data-ttu-id="96767-115">Описание</span><span class="sxs-lookup"><span data-stu-id="96767-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="96767-116">Элемент Frame для CustomItem для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="96767-116">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="96767-117">Определяет способ отображения данных, таких как данные сдвига влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="96767-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="96767-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="96767-118">Text Value</span></span>

<span data-ttu-id="96767-119">Укажите количество символов, которые нужно сместить первая строка данных.</span><span class="sxs-lookup"><span data-stu-id="96767-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="96767-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="96767-120">Remarks</span></span>

<span data-ttu-id="96767-121">Если этот элемент указан, нельзя указать [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="96767-121">If this element is specified, you cannot specify the [FirstLineIndent](./firstlineindent-element-for-frame-for-groupby-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="96767-122">См. также</span><span class="sxs-lookup"><span data-stu-id="96767-122">See Also</span></span>

[<span data-ttu-id="96767-123">Элемент FirstLineIndent для кадра для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="96767-123">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>](./firstlineindent-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="96767-124">Элемент Frame для CustomItem для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="96767-124">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="96767-125">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="96767-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
