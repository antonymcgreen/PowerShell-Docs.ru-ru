---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент SelectionSetName для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)
description: Элемент SelectionSetName для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)
ms.openlocfilehash: 074f810f5a3cbad61ee8be69408967758f0591df
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651878"
---
# <a name="selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="8d704-103">Элемент SelectionSetName для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="8d704-103">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="8d704-104">Указывает набор типов .NET, развернутых этим определением.</span><span class="sxs-lookup"><span data-stu-id="8d704-104">Specifies the set of .NET types that are expanded by this definition.</span></span>

<span data-ttu-id="8d704-105">Элемент конфигурации (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс элемент (Format) Енумерабликспансион элемент (Format) Ентриселектедби элемент для енумерабликспансион (Format) SelectionSetName для EntrySelectedBy в EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="8d704-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8d704-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d704-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="8d704-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8d704-107">Attributes and Elements</span></span>

<span data-ttu-id="8d704-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемента.</span><span class="sxs-lookup"><span data-stu-id="8d704-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8d704-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8d704-109">Attributes</span></span>

<span data-ttu-id="8d704-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8d704-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8d704-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8d704-111">Child Elements</span></span>

<span data-ttu-id="8d704-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8d704-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8d704-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8d704-113">Parent Elements</span></span>

|<span data-ttu-id="8d704-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="8d704-114">Element</span></span>|<span data-ttu-id="8d704-115">Описание</span><span class="sxs-lookup"><span data-stu-id="8d704-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8d704-116">Элемент EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="8d704-116">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="8d704-117">Определяет объекты коллекции .NET, развернутые этим определением.</span><span class="sxs-lookup"><span data-stu-id="8d704-117">Defines the .NET collection objects that are expanded by this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="8d704-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="8d704-118">Text Value</span></span>

<span data-ttu-id="8d704-119">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="8d704-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="8d704-120">Комментарии</span><span class="sxs-lookup"><span data-stu-id="8d704-120">Remarks</span></span>

<span data-ttu-id="8d704-121">Каждое определение должно указывать одно или несколько имен типов, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="8d704-121">Each definition must specify one or more type names, a selection set, or a selection condition.</span></span>

<span data-ttu-id="8d704-122">Наборы выбора обычно используются, если требуется определить группу объектов, используемых в нескольких представлениях.</span><span class="sxs-lookup"><span data-stu-id="8d704-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="8d704-123">Например, может потребоваться создать табличное представление и представление списка для одного и того же набора объектов.</span><span class="sxs-lookup"><span data-stu-id="8d704-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="8d704-124">Дополнительные сведения об определении наборов выбора см. [в разделе Определение наборов объектов для представления](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="8d704-124">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8d704-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="8d704-125">See Also</span></span>

[<span data-ttu-id="8d704-126">Определение наборов выделенных фрагментов</span><span class="sxs-lookup"><span data-stu-id="8d704-126">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="8d704-127">Элемент EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="8d704-127">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)

[<span data-ttu-id="8d704-128">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d704-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
