---
title: Элемент FirstLineIndent для кадра для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33be3b9e-53c8-433f-8c11-c65b0d46744c
caps.latest.revision: 6
ms.openlocfilehash: 9ba6fc1b9924a4b0d5b56ee15290a2293217403c
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858560"
---
# <a name="firstlineindent-element-for-frame-for-groupby-format"></a><span data-ttu-id="1cbd9-102">Элемент FirstLineIndent для элемента Frame для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="1cbd9-102">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>

<span data-ttu-id="1cbd9-103">Указывает количество символов, первая строка данных сдвигается вправо.</span><span class="sxs-lookup"><span data-stu-id="1cbd9-103">Specifies how many characters the first line of data is shifted to the right.</span></span> <span data-ttu-id="1cbd9-104">Этот элемент используется при определении того, как отображается группу объектов.</span><span class="sxs-lookup"><span data-stu-id="1cbd9-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="1cbd9-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) пользовательский элемент управления для элемента CustomEntries GroupBy (формат) пользовательский элемент управления для элемента CustomEntry GroupBy (формат) Пользовательский элемент управления для элемента CustomItem GroupBy (формат) для CustomEntry элемента фрейма GroupBy (формат) для CustomItem для элемента FirstLineIndent GroupBy (формат) для кадра для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="1cbd9-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) Frame Element for CustomItem for GroupBy (Format) FirstLineIndent Element for Frame for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1cbd9-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1cbd9-106">Syntax</span></span>

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1cbd9-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1cbd9-107">Attributes and Elements</span></span>

<span data-ttu-id="1cbd9-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `FirstLineIndent` элемент.</span><span class="sxs-lookup"><span data-stu-id="1cbd9-108">The following sections describe attributes, child elements, and parent element of the `FirstLineIndent` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1cbd9-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1cbd9-109">Attributes</span></span>

<span data-ttu-id="1cbd9-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="1cbd9-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1cbd9-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1cbd9-111">Child Elements</span></span>

<span data-ttu-id="1cbd9-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="1cbd9-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1cbd9-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1cbd9-113">Parent Elements</span></span>

|<span data-ttu-id="1cbd9-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="1cbd9-114">Element</span></span>|<span data-ttu-id="1cbd9-115">Описание</span><span class="sxs-lookup"><span data-stu-id="1cbd9-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1cbd9-116">Элемент Frame для CustomItem для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="1cbd9-116">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="1cbd9-117">Определяет способ отображения данных, таких как данные сдвига влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="1cbd9-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1cbd9-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="1cbd9-118">Text Value</span></span>

<span data-ttu-id="1cbd9-119">Укажите количество символов, которые нужно сместить первая строка данных.</span><span class="sxs-lookup"><span data-stu-id="1cbd9-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="1cbd9-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="1cbd9-120">Remarks</span></span>

<span data-ttu-id="1cbd9-121">Если этот элемент указан, нельзя указать [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="1cbd9-121">If this element is specified, you cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="1cbd9-122">См. также</span><span class="sxs-lookup"><span data-stu-id="1cbd9-122">See Also</span></span>

[<span data-ttu-id="1cbd9-123">Элемент FirstLineHanging для кадра для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="1cbd9-123">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="1cbd9-124">Элемент Frame для CustomItem для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="1cbd9-124">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="1cbd9-125">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="1cbd9-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
