---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)
description: Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)
ms.openlocfilehash: 0c9372113a79f75cfbda67acf869164fde894ee3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651588"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="ea019-103">Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="ea019-103">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="ea019-104">Указывает набор типов .NET, которые активируют условие.</span><span class="sxs-lookup"><span data-stu-id="ea019-104">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="ea019-105">При наличии любого из типов в этом наборе условие будет выполнено.</span><span class="sxs-lookup"><span data-stu-id="ea019-105">When any of the types in this set are present, the condition is met.</span></span>

<span data-ttu-id="ea019-106">Элемент конфигурации Дефаултсеттингс элемент (Format) Енумерабликспансионс элемент (Format) Енумерабликспансионс элемент (Format) Ентриселектедби элемент для енумерабликспансион (Format) SelectionCondition для EntrySelectedBy для EnumerableExpansion (Format) SelectionSetName для SelectionCondition в EntrySelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="ea019-106">Configuration Element DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansions Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ea019-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ea019-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ea019-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ea019-108">Attributes and Elements</span></span>

<span data-ttu-id="ea019-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемента.</span><span class="sxs-lookup"><span data-stu-id="ea019-109">The following sections describe attributes, child elements, and parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ea019-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ea019-110">Attributes</span></span>

<span data-ttu-id="ea019-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ea019-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ea019-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ea019-112">Child Elements</span></span>

<span data-ttu-id="ea019-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ea019-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ea019-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ea019-114">Parent Elements</span></span>

|<span data-ttu-id="ea019-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="ea019-115">Element</span></span>|<span data-ttu-id="ea019-116">Описание</span><span class="sxs-lookup"><span data-stu-id="ea019-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ea019-117">Элемент SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="ea019-117">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="ea019-118">Определяет условие, которое должно существовать для расширения объектов коллекции этого определения.</span><span class="sxs-lookup"><span data-stu-id="ea019-118">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ea019-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="ea019-119">Text Value</span></span>

<span data-ttu-id="ea019-120">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="ea019-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="ea019-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ea019-121">Remarks</span></span>

<span data-ttu-id="ea019-122">Условие выбора может указывать набор выбора или тип .NET, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="ea019-122">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="ea019-123">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="ea019-123">For more information about how to use selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="ea019-124">Наборы выбора — это распространенные группы объектов .NET, которые могут использоваться любым представлением, определяемым файлом форматирования.</span><span class="sxs-lookup"><span data-stu-id="ea019-124">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="ea019-125">Дополнительные сведения о создании и ссылке на наборы выбора см. в разделе [Определение наборов выбора](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="ea019-125">For more information about creating and referencing selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ea019-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="ea019-126">See Also</span></span>

[<span data-ttu-id="ea019-127">Определение наборов выделенных фрагментов</span><span class="sxs-lookup"><span data-stu-id="ea019-127">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="ea019-128">Элемент SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="ea019-128">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="ea019-129">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="ea019-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
