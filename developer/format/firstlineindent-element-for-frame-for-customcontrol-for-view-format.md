---
title: Элемент FirstLineIndent для кадра для пользовательский элемент управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb4e1564-3fd3-4be3-b93e-ac90480e05c0
caps.latest.revision: 6
ms.openlocfilehash: 3130ecc69f7d1568bcbd392dd24e8cdcc3382905
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065875"
---
# <a name="firstlineindent-element-for-frame-for-customcontrol-for-view-format"></a><span data-ttu-id="f12da-102">Элемент FirstLineIndent для элемента Frame для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="f12da-102">FirstLineIndent Element for Frame for CustomControl for View (Format)</span></span>

<span data-ttu-id="f12da-103">Указывает количество символов, первая строка данных сдвигается вправо.</span><span class="sxs-lookup"><span data-stu-id="f12da-103">Specifies how many characters the first line of data is shifted to the right.</span></span> <span data-ttu-id="f12da-104">Этот элемент используется при определении представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f12da-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="f12da-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемент (формат) элемент пользовательский элемент управления (формат) CustomEntries элемент конфигурации для пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для элемента CustomItem представление (формат) CustomEntry CustomControlView (формат) элемента фрейма для CustomItem для пользовательский элемент управления для элемента FirstLineIndent представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f12da-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for CustomControlView (Format) Frame Element for CustomItem for CustomControl for View (Format) FirstLineIndent Element</span></span>

## <a name="syntax"></a><span data-ttu-id="f12da-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f12da-106">Syntax</span></span>

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f12da-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f12da-107">Attributes and Elements</span></span>

<span data-ttu-id="f12da-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `FirstLineIndent` элемент.</span><span class="sxs-lookup"><span data-stu-id="f12da-108">The following sections describe attributes, child elements, and parent element of the `FirstLineIndent` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f12da-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f12da-109">Attributes</span></span>

<span data-ttu-id="f12da-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="f12da-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f12da-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f12da-111">Child Elements</span></span>

<span data-ttu-id="f12da-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="f12da-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f12da-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f12da-113">Parent Elements</span></span>

|<span data-ttu-id="f12da-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="f12da-114">Element</span></span>|<span data-ttu-id="f12da-115">Описание</span><span class="sxs-lookup"><span data-stu-id="f12da-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f12da-116">Элемент Frame для CustomItem для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f12da-116">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="f12da-117">Определяет способ отображения данных, таких как данные сдвига влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="f12da-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f12da-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="f12da-118">Text Value</span></span>

<span data-ttu-id="f12da-119">Укажите количество символов, которые нужно сместить первая строка данных.</span><span class="sxs-lookup"><span data-stu-id="f12da-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="f12da-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="f12da-120">Remarks</span></span>

<span data-ttu-id="f12da-121">Если этот элемент указан, нельзя указать [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="f12da-121">If this element is specified, you cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="f12da-122">См. также</span><span class="sxs-lookup"><span data-stu-id="f12da-122">See Also</span></span>

[<span data-ttu-id="f12da-123">Элемент FirstLineHanging для кадра для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f12da-123">FirstLineHanging Element for Frame for CustomControl for View (Format)</span></span>](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[<span data-ttu-id="f12da-124">Элемент Frame для CustomItem для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f12da-124">Frame Element for CustomItem for CustomControl for View (Format)</span></span>](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[<span data-ttu-id="f12da-125">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="f12da-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
