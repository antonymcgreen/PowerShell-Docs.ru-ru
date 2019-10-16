---
title: Элемент Фирстлинехангинг для Frame для элементов управления конфигурации (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 679c8bcb-b49d-4bb4-91f5-ea1af6c217e3
caps.latest.revision: 8
ms.openlocfilehash: 4553f95e48a2b1440c00b4951bea56376b00628a
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363173"
---
# <a name="firstlinehanging-element-for-frame-for-controls-for-configuration-format"></a><span data-ttu-id="cabd3-102">Элемент FirstLineHanging для элемента Frame для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="cabd3-102">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>

<span data-ttu-id="cabd3-103">Указывает, сколько знаков первая строка данных смещается влево.</span><span class="sxs-lookup"><span data-stu-id="cabd3-103">Specifies how many characters the first line of data is shifted to the left.</span></span> <span data-ttu-id="cabd3-104">Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="cabd3-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="cabd3-105">Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control в конфигурации (Format) Кустоментриес для ошибка customcontrol для конфигурации ( Формат) элемент Кустоментри для ошибка customcontrol для элементов управления для элемента конфигурации (Format) Кустомитем для Кустоментри элементов управления для элемента "элемент конфигурации" для Кустомитем для элементов управления в конфигурации (формат) Фирстлинехангинг элемента для Frame для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="cabd3-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration Frame Element for CustomItem for Controls for Configuration (Format) FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cabd3-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cabd3-106">Syntax</span></span>

```xml
<FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cabd3-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cabd3-107">Attributes and Elements</span></span>

<span data-ttu-id="cabd3-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `FirstLineHanging`.</span><span class="sxs-lookup"><span data-stu-id="cabd3-108">The following sections describe attributes, child elements, and parent element of the `FirstLineHanging` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="cabd3-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cabd3-109">Attributes</span></span>

<span data-ttu-id="cabd3-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="cabd3-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cabd3-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cabd3-111">Child Elements</span></span>

<span data-ttu-id="cabd3-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="cabd3-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="cabd3-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cabd3-113">Parent Elements</span></span>

|<span data-ttu-id="cabd3-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="cabd3-114">Element</span></span>|<span data-ttu-id="cabd3-115">Описание</span><span class="sxs-lookup"><span data-stu-id="cabd3-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cabd3-116">Элемент Frame для элемента управления Кустомитем для Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="cabd3-116">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="cabd3-117">Определяет способ отображения данных, например сдвиг данных влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="cabd3-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="cabd3-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="cabd3-118">Text Value</span></span>

<span data-ttu-id="cabd3-119">Укажите число символов, на которое необходимо сдвинуть первую строку данных.</span><span class="sxs-lookup"><span data-stu-id="cabd3-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="cabd3-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="cabd3-120">Remarks</span></span>

<span data-ttu-id="cabd3-121">Если этот элемент указан, нельзя указать элемент `FirstLineIndent`.</span><span class="sxs-lookup"><span data-stu-id="cabd3-121">If this element is specified, you cannot specify the `FirstLineIndent` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="cabd3-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="cabd3-122">See Also</span></span>

[<span data-ttu-id="cabd3-123">Элемент Frame для элемента управления Кустомитем для Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="cabd3-123">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="cabd3-124">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="cabd3-124">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
