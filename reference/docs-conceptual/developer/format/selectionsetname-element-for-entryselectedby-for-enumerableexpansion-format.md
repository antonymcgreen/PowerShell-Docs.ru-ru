---
title: Элемент Селектионсетнаме для Ентриселектедби для Енумерабликспансион (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 936d09f2-2c48-49e8-ab2d-0c8729199a2e
caps.latest.revision: 8
ms.openlocfilehash: 8ba8931ea5e34f610878351396cad42023393ad6
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368333"
---
# <a name="selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="b7fc4-102">Элемент SelectionSetName для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="b7fc4-102">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="b7fc4-103">Указывает набор типов .NET, развернутых этим определением.</span><span class="sxs-lookup"><span data-stu-id="b7fc4-103">Specifies the set of .NET types that are expanded by this definition.</span></span>

<span data-ttu-id="b7fc4-104">Элемент конфигурации (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс элемент (Format) Енумерабликспансион элемент (Format) Ентриселектедби элемент для енумерабликспансион (Format) SelectionSetName для EntrySelectedBy Енумерабликспансион (формат)</span><span class="sxs-lookup"><span data-stu-id="b7fc4-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b7fc4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b7fc4-105">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="b7fc4-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b7fc4-106">Attributes and Elements</span></span>

<span data-ttu-id="b7fc4-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `SelectionSetName`.</span><span class="sxs-lookup"><span data-stu-id="b7fc4-107">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b7fc4-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b7fc4-108">Attributes</span></span>

<span data-ttu-id="b7fc4-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="b7fc4-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b7fc4-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b7fc4-110">Child Elements</span></span>

<span data-ttu-id="b7fc4-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="b7fc4-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b7fc4-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b7fc4-112">Parent Elements</span></span>

|<span data-ttu-id="b7fc4-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="b7fc4-113">Element</span></span>|<span data-ttu-id="b7fc4-114">Описание</span><span class="sxs-lookup"><span data-stu-id="b7fc4-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b7fc4-115">Элемент Ентриселектедби для Енумерабликспансион (Format)</span><span class="sxs-lookup"><span data-stu-id="b7fc4-115">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="b7fc4-116">Определяет объекты коллекции .NET, развернутые этим определением.</span><span class="sxs-lookup"><span data-stu-id="b7fc4-116">Defines the .NET collection objects that are expanded by this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b7fc4-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="b7fc4-117">Text Value</span></span>

<span data-ttu-id="b7fc4-118">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="b7fc4-118">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="b7fc4-119">Замечания</span><span class="sxs-lookup"><span data-stu-id="b7fc4-119">Remarks</span></span>

<span data-ttu-id="b7fc4-120">Каждое определение должно указывать одно или несколько имен типов, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="b7fc4-120">Each definition must specify one or more type names, a selection set, or a selection condition.</span></span>

<span data-ttu-id="b7fc4-121">Наборы выбора обычно используются, если требуется определить группу объектов, используемых в нескольких представлениях.</span><span class="sxs-lookup"><span data-stu-id="b7fc4-121">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="b7fc4-122">Например, может потребоваться создать табличное представление и представление списка для одного и того же набора объектов.</span><span class="sxs-lookup"><span data-stu-id="b7fc4-122">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="b7fc4-123">Дополнительные сведения об определении наборов выбора см. [в разделе Определение наборов объектов для представления](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="b7fc4-123">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b7fc4-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="b7fc4-124">See Also</span></span>

[<span data-ttu-id="b7fc4-125">Определение наборов выбора</span><span class="sxs-lookup"><span data-stu-id="b7fc4-125">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="b7fc4-126">Элемент Ентриселектедби для Енумерабликспансион (Format)</span><span class="sxs-lookup"><span data-stu-id="b7fc4-126">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)

[<span data-ttu-id="b7fc4-127">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7fc4-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
