---
title: Элемент FirstLineHanging для кадра для элементов управления для конфигурации (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 679c8bcb-b49d-4bb4-91f5-ea1af6c217e3
caps.latest.revision: 8
ms.openlocfilehash: 4553f95e48a2b1440c00b4951bea56376b00628a
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065892"
---
# <a name="firstlinehanging-element-for-frame-for-controls-for-configuration-format"></a><span data-ttu-id="77a40-102">Элемент FirstLineHanging для элемента Frame для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="77a40-102">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>

<span data-ttu-id="77a40-103">Указывает количество символов, первая строка данных сдвигается влево.</span><span class="sxs-lookup"><span data-stu-id="77a40-103">Specifies how many characters the first line of data is shifted to the left.</span></span> <span data-ttu-id="77a40-104">Этот элемент используется при определении общего элемента управления, который может использоваться все представления в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="77a40-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="77a40-105">Конфигурации (формат) элементы управления элемента конфигурации (формат) элемента управления для элементов управления для элемента конфигурации (формат) пользовательский элемент управления для элемента управления для элемента конфигурации (формат) CustomEntries пользовательский элемент управления для конфигурации ( Элемент CustomEntry Format) для пользовательский элемент управления для элементов управления для элемента конфигурации (формат) CustomItem для CustomEntry для элементов управления для фрейма элемента конфигурации для CustomItem для элементов управления для элемента FirstLineHanging конфигурации (формат) для кадра для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="77a40-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration Frame Element for CustomItem for Controls for Configuration (Format) FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="77a40-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="77a40-106">Syntax</span></span>

```xml
<FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="77a40-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="77a40-107">Attributes and Elements</span></span>

<span data-ttu-id="77a40-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `FirstLineHanging` элемент.</span><span class="sxs-lookup"><span data-stu-id="77a40-108">The following sections describe attributes, child elements, and parent element of the `FirstLineHanging` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="77a40-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="77a40-109">Attributes</span></span>

<span data-ttu-id="77a40-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="77a40-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="77a40-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="77a40-111">Child Elements</span></span>

<span data-ttu-id="77a40-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="77a40-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="77a40-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="77a40-113">Parent Elements</span></span>

|<span data-ttu-id="77a40-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="77a40-114">Element</span></span>|<span data-ttu-id="77a40-115">Описание</span><span class="sxs-lookup"><span data-stu-id="77a40-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="77a40-116">Элемент Frame для CustomItem для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="77a40-116">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="77a40-117">Определяет способ отображения данных, таких как данные сдвига влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="77a40-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="77a40-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="77a40-118">Text Value</span></span>

<span data-ttu-id="77a40-119">Укажите количество символов, которые нужно сместить первая строка данных.</span><span class="sxs-lookup"><span data-stu-id="77a40-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="77a40-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="77a40-120">Remarks</span></span>

<span data-ttu-id="77a40-121">Если этот элемент указан, нельзя указать `FirstLineIndent` элемент.</span><span class="sxs-lookup"><span data-stu-id="77a40-121">If this element is specified, you cannot specify the `FirstLineIndent` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="77a40-122">См. также</span><span class="sxs-lookup"><span data-stu-id="77a40-122">See Also</span></span>

[<span data-ttu-id="77a40-123">Элемент Frame для CustomItem для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="77a40-123">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="77a40-124">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="77a40-124">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
