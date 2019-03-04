---
title: Элемент FirstLineIndent для кадра для элементов управления для конфигурации (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f489720-11f6-4019-940e-07f423d4278d
caps.latest.revision: 6
ms.openlocfilehash: c5b2d971fe1590116f96b024ae8769334768acf2
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856350"
---
# <a name="firstlineindent-element-for-frame-for-controls-for-configuration-format"></a><span data-ttu-id="b479c-102">Элемент FirstLineIndent для элемента Frame для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="b479c-102">FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>

<span data-ttu-id="b479c-103">Указывает количество символов, первая строка данных сдвигается вправо.</span><span class="sxs-lookup"><span data-stu-id="b479c-103">Specifies how many characters the first line of data is shifted to the right.</span></span> <span data-ttu-id="b479c-104">Этот элемент используется при определении общего элемента управления, который может использоваться все представления в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="b479c-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="b479c-105">Конфигурации (формат) элементы управления элемента конфигурации (формат) элемента управления для элементов управления для элемента конфигурации (формат) пользовательский элемент управления для элемента управления для элемента конфигурации (формат) CustomEntries пользовательский элемент управления для конфигурации ( Элемент CustomEntry Format) для пользовательский элемент управления для элементов управления для элемента конфигурации (формат) CustomItem для CustomEntry для элементов управления для фрейма элемента конфигурации для CustomItem для элементов управления для элемента FirstLineIndent конфигурации (формат) для кадра для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="b479c-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration Frame Element for CustomItem for Controls for Configuration (Format) FirstLineIndent Element for Frame for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b479c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b479c-106">Syntax</span></span>

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b479c-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b479c-107">Attributes and Elements</span></span>

<span data-ttu-id="b479c-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `FirstLineIndent` элемент.</span><span class="sxs-lookup"><span data-stu-id="b479c-108">The following sections describe attributes, child elements, and parent element of the `FirstLineIndent` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b479c-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b479c-109">Attributes</span></span>

<span data-ttu-id="b479c-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="b479c-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b479c-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b479c-111">Child Elements</span></span>

<span data-ttu-id="b479c-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="b479c-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b479c-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b479c-113">Parent Elements</span></span>

|<span data-ttu-id="b479c-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="b479c-114">Element</span></span>|<span data-ttu-id="b479c-115">Описание</span><span class="sxs-lookup"><span data-stu-id="b479c-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b479c-116">Элемент Frame для CustomItem для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="b479c-116">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="b479c-117">Определяет способ отображения данных, таких как данные сдвига влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="b479c-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b479c-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="b479c-118">Text Value</span></span>

<span data-ttu-id="b479c-119">Укажите количество символов, которые нужно сместить первая строка данных.</span><span class="sxs-lookup"><span data-stu-id="b479c-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="b479c-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="b479c-120">Remarks</span></span>

<span data-ttu-id="b479c-121">Если этот элемент указан, нельзя указать [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="b479c-121">If this element is specified, you cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="b479c-122">См. также</span><span class="sxs-lookup"><span data-stu-id="b479c-122">See Also</span></span>

[<span data-ttu-id="b479c-123">Элемент FirstLineHanging для кадра для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="b479c-123">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-configuration-format.md)

[<span data-ttu-id="b479c-124">Элемент Frame для CustomItem для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="b479c-124">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="b479c-125">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="b479c-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
