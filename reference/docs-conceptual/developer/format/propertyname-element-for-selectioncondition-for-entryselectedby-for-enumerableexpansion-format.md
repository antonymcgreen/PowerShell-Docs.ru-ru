---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)
description: Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)
ms.openlocfilehash: 8e28118894661b50e90a5ccc86a36fbbe77e4b03
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665844"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="4aa46-103">Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="4aa46-103">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="4aa46-104">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="4aa46-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="4aa46-105">При наличии этого свойства или при его вычислении `true` условие выполняется, и используется определение.</span><span class="sxs-lookup"><span data-stu-id="4aa46-105">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span>

<span data-ttu-id="4aa46-106">Элемент конфигурации (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс элемент (Format) Енумерабликспансион элемент (Format) Ентриселектедби элемент для енумерабликспансион (Format) SelectionCondition для EntrySelectedBy для EnumerableExpansion (Format) элемент PropertyName для SelectionCondition для EntrySelectedBy в EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="4aa46-106">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4aa46-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4aa46-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4aa46-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4aa46-108">Attributes and Elements</span></span>

<span data-ttu-id="4aa46-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.</span><span class="sxs-lookup"><span data-stu-id="4aa46-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4aa46-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4aa46-110">Attributes</span></span>

<span data-ttu-id="4aa46-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4aa46-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4aa46-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4aa46-112">Child Elements</span></span>

<span data-ttu-id="4aa46-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4aa46-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4aa46-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4aa46-114">Parent Elements</span></span>

|<span data-ttu-id="4aa46-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="4aa46-115">Element</span></span>|<span data-ttu-id="4aa46-116">Описание</span><span class="sxs-lookup"><span data-stu-id="4aa46-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4aa46-117">Элемент SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="4aa46-117">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="4aa46-118">Определяет условие, которое должно существовать для расширения объектов коллекции этого определения.</span><span class="sxs-lookup"><span data-stu-id="4aa46-118">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="4aa46-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="4aa46-119">Text Value</span></span>

<span data-ttu-id="4aa46-120">Укажите имя свойства .NET.</span><span class="sxs-lookup"><span data-stu-id="4aa46-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="4aa46-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="4aa46-121">Remarks</span></span>

<span data-ttu-id="4aa46-122">Условие выбора должно указывать по крайней мере одно имя свойства или скрипт для вычисления, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="4aa46-122">The selection condition must specify at least one property name or a script to evaluate, but cannot specify both.</span></span> <span data-ttu-id="4aa46-123">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="4aa46-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4aa46-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="4aa46-124">See Also</span></span>

[<span data-ttu-id="4aa46-125">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="4aa46-125">Defining Conditions for When Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="4aa46-126">Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="4aa46-126">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="4aa46-127">Элемент SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="4aa46-127">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="4aa46-128">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="4aa46-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
