---
title: Элемент FirstLineIndent для кадра для элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec63f4f9-8858-4529-8646-ffbbc278f83e
caps.latest.revision: 7
ms.openlocfilehash: 694c5baaa5e90a772257276ba139d90acf7ec0e3
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066028"
---
# <a name="firstlineindent-element-for-frame-for-controls-for-view-format"></a><span data-ttu-id="58ac0-102">Элемент FirstLineIndent для элемента Frame для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="58ac0-102">FirstLineIndent Element for Frame for Controls for View (Format)</span></span>

<span data-ttu-id="58ac0-103">Указывает количество символов, первая строка данных сдвигается вправо.</span><span class="sxs-lookup"><span data-stu-id="58ac0-103">Specifies how many characters the first line of data is shifted to the right.</span></span> <span data-ttu-id="58ac0-104">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="58ac0-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="58ac0-105">Конфигурации элемента (формат) элемент ViewDefinitions (формат) представление элемента (формат) элементы управления элемента (формат) элемент управления для элементов управления для элемента представления (формат) пользовательский элемент управления для элемента управления для элементов управления для элемента CustomEntries представления (формат) для Пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для элементов управления для элемента представления (формат) CustomItem для CustomEntry для элементов управления для элемента представления (формат) кадра для CustomItem для элементов управления для элемента представления (формат) FirstLineIndent кадра элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="58ac0-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) Frame Element for CustomItem for Controls for View (Format) FirstLineIndent Element of Frame of Controls of View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="58ac0-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="58ac0-106">Syntax</span></span>

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="58ac0-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="58ac0-107">Attributes and Elements</span></span>

<span data-ttu-id="58ac0-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `FirstLineIndent` элемент.</span><span class="sxs-lookup"><span data-stu-id="58ac0-108">The following sections describe attributes, child elements, and parent element of the `FirstLineIndent` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="58ac0-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="58ac0-109">Attributes</span></span>

<span data-ttu-id="58ac0-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="58ac0-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="58ac0-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="58ac0-111">Child Elements</span></span>

<span data-ttu-id="58ac0-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="58ac0-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="58ac0-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="58ac0-113">Parent Elements</span></span>

|<span data-ttu-id="58ac0-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="58ac0-114">Element</span></span>|<span data-ttu-id="58ac0-115">Описание</span><span class="sxs-lookup"><span data-stu-id="58ac0-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="58ac0-116">Элемент Frame для CustomItem для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="58ac0-116">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="58ac0-117">Определяет способ отображения данных, таких как данные сдвига влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="58ac0-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="58ac0-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="58ac0-118">Text Value</span></span>

<span data-ttu-id="58ac0-119">Укажите количество символов, которые нужно сместить первая строка данных.</span><span class="sxs-lookup"><span data-stu-id="58ac0-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="58ac0-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="58ac0-120">Remarks</span></span>

<span data-ttu-id="58ac0-121">Если этот элемент указан, нельзя указать [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="58ac0-121">If this element is specified, you cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-controls-for-view-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="58ac0-122">См. также</span><span class="sxs-lookup"><span data-stu-id="58ac0-122">See Also</span></span>

[<span data-ttu-id="58ac0-123">Элемент FirstLineHanging для кадра для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="58ac0-123">FirstLineHanging Element for Frame for Controls for View (Format)</span></span>](./firstlinehanging-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="58ac0-124">Элемент Frame для CustomItem для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="58ac0-124">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="58ac0-125">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="58ac0-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
