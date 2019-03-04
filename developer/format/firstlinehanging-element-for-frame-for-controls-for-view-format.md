---
title: Элемент FirstLineHanging для кадра для элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53694f08-57f7-4185-b443-1636a0918afc
caps.latest.revision: 8
ms.openlocfilehash: 387340cd9b0aae2ad0419b187d96ab4fee183d5a
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858720"
---
# <a name="firstlinehanging-element-for-frame-for-controls-for-view-format"></a><span data-ttu-id="45f38-102">Элемент FirstLineHanging для элемента Frame для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="45f38-102">FirstLineHanging Element for Frame for Controls for View (Format)</span></span>

<span data-ttu-id="45f38-103">Указывает количество символов, первая строка данных сдвигается влево.</span><span class="sxs-lookup"><span data-stu-id="45f38-103">Specifies how many characters the first line of data is shifted to the left.</span></span> <span data-ttu-id="45f38-104">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="45f38-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="45f38-105">Конфигурации элемента (формат) элемент ViewDefinitions (формат) представление элемента (формат) элементы управления элемента (формат) элемент управления для элементов управления для элемента представления (формат) пользовательский элемент управления для элемента управления для элементов управления для элемента CustomEntries представления (формат) для Пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для элементов управления для элемента представления (формат) CustomItem для CustomEntry для элементов управления для элемента представления (формат) кадра для CustomItem для элементов управления для элемента FirstLineHanging представление (формат) Кадр элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="45f38-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) Frame Element for CustomItem for Controls for View (Format) FirstLineHanging Element of Frame of Controls of View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="45f38-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="45f38-106">Syntax</span></span>

```xml
<FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="45f38-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="45f38-107">Attributes and Elements</span></span>

<span data-ttu-id="45f38-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `FirstLineHanging` элемент.</span><span class="sxs-lookup"><span data-stu-id="45f38-108">The following sections describe attributes, child elements, and parent element of the `FirstLineHanging` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="45f38-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="45f38-109">Attributes</span></span>

<span data-ttu-id="45f38-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="45f38-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="45f38-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="45f38-111">Child Elements</span></span>

<span data-ttu-id="45f38-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="45f38-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="45f38-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="45f38-113">Parent Elements</span></span>

|<span data-ttu-id="45f38-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="45f38-114">Element</span></span>|<span data-ttu-id="45f38-115">Описание</span><span class="sxs-lookup"><span data-stu-id="45f38-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="45f38-116">Элемент Frame для CustomItem для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="45f38-116">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="45f38-117">Определяет способ отображения данных, таких как данные сдвига влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="45f38-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="45f38-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="45f38-118">Text Value</span></span>

<span data-ttu-id="45f38-119">Укажите количество символов, которые нужно сместить первая строка данных.</span><span class="sxs-lookup"><span data-stu-id="45f38-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="45f38-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="45f38-120">Remarks</span></span>

<span data-ttu-id="45f38-121">Если этот элемент указан, нельзя указать [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="45f38-121">If this element is specified, you cannot specify the [FirstLineIndent](./firstlineindent-element-for-frame-for-controls-for-view-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="45f38-122">См. также</span><span class="sxs-lookup"><span data-stu-id="45f38-122">See Also</span></span>

[<span data-ttu-id="45f38-123">Элемент FirstLineIndent для кадра для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="45f38-123">FirstLineIndent Element for Frame for Controls for View (Format)</span></span>](./firstlineindent-element-for-frame-for-controls-for-view-format.md)

[<span data-ttu-id="45f38-124">Элемент Frame для CustomItem для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="45f38-124">Frame Element for CustomItem for Controls for View (Format)</span></span>](./frame-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="45f38-125">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="45f38-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
