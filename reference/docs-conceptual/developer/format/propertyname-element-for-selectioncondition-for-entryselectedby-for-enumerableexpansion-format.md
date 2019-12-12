---
title: Элемент PropertyName для Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9ae11924-0072-451e-bf70-c5ffb25dccc0
caps.latest.revision: 13
ms.openlocfilehash: 0c20512e660c8d2b61d063dbd7078b55b23efeb8
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362323"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="172dd-102">Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="172dd-102">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="172dd-103">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="172dd-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="172dd-104">Если это свойство имеется или если оно имеет значение `true`, условие выполняется, и используется определение.</span><span class="sxs-lookup"><span data-stu-id="172dd-104">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span>

<span data-ttu-id="172dd-105">Элемент конфигурации (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс элемент (Format) Енумерабликспансион элемент (Format) Ентриселектедби элемент для енумерабликспансион (Format) SelectionCondition для EntrySelectedBy Енумерабликспансион (Format) PropertyName элемент для Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format)</span><span class="sxs-lookup"><span data-stu-id="172dd-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="172dd-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="172dd-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="172dd-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="172dd-107">Attributes and Elements</span></span>

<span data-ttu-id="172dd-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `PropertyName`.</span><span class="sxs-lookup"><span data-stu-id="172dd-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="172dd-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="172dd-109">Attributes</span></span>

<span data-ttu-id="172dd-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="172dd-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="172dd-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="172dd-111">Child Elements</span></span>

<span data-ttu-id="172dd-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="172dd-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="172dd-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="172dd-113">Parent Elements</span></span>

|<span data-ttu-id="172dd-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="172dd-114">Element</span></span>|<span data-ttu-id="172dd-115">Описание</span><span class="sxs-lookup"><span data-stu-id="172dd-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="172dd-116">Элемент Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format)</span><span class="sxs-lookup"><span data-stu-id="172dd-116">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="172dd-117">Определяет условие, которое должно существовать для расширения объектов коллекции этого определения.</span><span class="sxs-lookup"><span data-stu-id="172dd-117">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="172dd-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="172dd-118">Text Value</span></span>

<span data-ttu-id="172dd-119">Укажите имя свойства .NET.</span><span class="sxs-lookup"><span data-stu-id="172dd-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="172dd-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="172dd-120">Remarks</span></span>

<span data-ttu-id="172dd-121">Условие выбора должно указывать по крайней мере одно имя свойства или скрипт для вычисления, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="172dd-121">The selection condition must specify at least one property name or a script to evaluate, but cannot specify both.</span></span> <span data-ttu-id="172dd-122">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="172dd-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="172dd-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="172dd-123">See Also</span></span>

[<span data-ttu-id="172dd-124">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="172dd-124">Defining Conditions for When Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="172dd-125">Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format)</span><span class="sxs-lookup"><span data-stu-id="172dd-125">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="172dd-126">Элемент Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format)</span><span class="sxs-lookup"><span data-stu-id="172dd-126">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="172dd-127">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="172dd-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
