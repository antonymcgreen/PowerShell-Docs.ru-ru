---
title: Элемент Фирстлинехангинг для Frame для элементов управления конфигурации (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 6c0429a5caa5d20370acff72fa5707ed8cf7ad01
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773748"
---
# <a name="firstlinehanging-element-for-frame-for-controls-for-configuration-format"></a><span data-ttu-id="eda5d-102">Элемент FirstLineHanging для элемента Frame для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="eda5d-102">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>

<span data-ttu-id="eda5d-103">Указывает, сколько знаков первая строка данных смещается влево.</span><span class="sxs-lookup"><span data-stu-id="eda5d-103">Specifies how many characters the first line of data is shifted to the left.</span></span> <span data-ttu-id="eda5d-104">Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="eda5d-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="eda5d-105">Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control (формат) Кустоментриес для ошибка customcontrol для элемента конфигурации (Format) Кустоментри для ошибка customcontrol для элементов управления в конфигурации (Format) Кустомитем элемент для Кустоментри для элементов управления элемента Frame конфигурации для Кустомитем элементов управления для элемента конфигурации (Format) Фирстлинехангинг для Frame для элементов управления конфигурации (Format).</span><span class="sxs-lookup"><span data-stu-id="eda5d-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration Frame Element for CustomItem for Controls for Configuration (Format) FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="eda5d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eda5d-106">Syntax</span></span>

```xml
<FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="eda5d-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="eda5d-107">Attributes and Elements</span></span>

<span data-ttu-id="eda5d-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `FirstLineHanging` элемента.</span><span class="sxs-lookup"><span data-stu-id="eda5d-108">The following sections describe attributes, child elements, and parent element of the `FirstLineHanging` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="eda5d-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="eda5d-109">Attributes</span></span>

<span data-ttu-id="eda5d-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="eda5d-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="eda5d-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="eda5d-111">Child Elements</span></span>

<span data-ttu-id="eda5d-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="eda5d-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="eda5d-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="eda5d-113">Parent Elements</span></span>

|<span data-ttu-id="eda5d-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="eda5d-114">Element</span></span>|<span data-ttu-id="eda5d-115">Описание</span><span class="sxs-lookup"><span data-stu-id="eda5d-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="eda5d-116">Элемент Frame для элемента CustomItem для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="eda5d-116">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="eda5d-117">Определяет способ отображения данных, например сдвиг данных влево или вправо.</span><span class="sxs-lookup"><span data-stu-id="eda5d-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="eda5d-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="eda5d-118">Text Value</span></span>

<span data-ttu-id="eda5d-119">Укажите число символов, на которое необходимо сдвинуть первую строку данных.</span><span class="sxs-lookup"><span data-stu-id="eda5d-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="eda5d-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="eda5d-120">Remarks</span></span>

<span data-ttu-id="eda5d-121">Если этот элемент указан, нельзя указать `FirstLineIndent` элемент.</span><span class="sxs-lookup"><span data-stu-id="eda5d-121">If this element is specified, you cannot specify the `FirstLineIndent` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="eda5d-122">См. также</span><span class="sxs-lookup"><span data-stu-id="eda5d-122">See Also</span></span>

[<span data-ttu-id="eda5d-123">Элемент Frame для элемента CustomItem для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="eda5d-123">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="eda5d-124">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="eda5d-124">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
