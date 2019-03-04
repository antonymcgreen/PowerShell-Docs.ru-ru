---
title: Элемент SelectionSetName для EntrySelectedBy для EnumerableExpansion (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 936d09f2-2c48-49e8-ab2d-0c8729199a2e
caps.latest.revision: 8
ms.openlocfilehash: 8ba8931ea5e34f610878351396cad42023393ad6
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862750"
---
# <a name="selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="d66f6-102">Элемент SelectionSetName для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="d66f6-102">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="d66f6-103">Указывает набор типов .NET, которые расширяются в соответствии с этим определением.</span><span class="sxs-lookup"><span data-stu-id="d66f6-103">Specifies the set of .NET types that are expanded by this definition.</span></span>

<span data-ttu-id="d66f6-104">Элемент (формат) элемент DefaultSettings (формат) элемент EnumerableExpansions (формат) элемент EnumerableExpansion (формат) EntrySelectedBy элемента конфигурации для элемента SelectionSetName EnumerableExpansion (формат) EntrySelectedBy для EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="d66f6-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d66f6-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d66f6-105">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="d66f6-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d66f6-106">Attributes and Elements</span></span>

<span data-ttu-id="d66f6-107">Ниже описаны атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемент.</span><span class="sxs-lookup"><span data-stu-id="d66f6-107">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d66f6-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d66f6-108">Attributes</span></span>

<span data-ttu-id="d66f6-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="d66f6-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d66f6-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d66f6-110">Child Elements</span></span>

<span data-ttu-id="d66f6-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="d66f6-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d66f6-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d66f6-112">Parent Elements</span></span>

|<span data-ttu-id="d66f6-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="d66f6-113">Element</span></span>|<span data-ttu-id="d66f6-114">Описание</span><span class="sxs-lookup"><span data-stu-id="d66f6-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d66f6-115">Элемент EntrySelectedBy для EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="d66f6-115">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="d66f6-116">Определяет коллекцию объектов .NET, которые будут развернуты в соответствии с этим определением.</span><span class="sxs-lookup"><span data-stu-id="d66f6-116">Defines the .NET collection objects that are expanded by this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d66f6-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="d66f6-117">Text Value</span></span>

<span data-ttu-id="d66f6-118">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="d66f6-118">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="d66f6-119">Замечания</span><span class="sxs-lookup"><span data-stu-id="d66f6-119">Remarks</span></span>

<span data-ttu-id="d66f6-120">Каждое определение необходимо указать один или несколько имен типов, выбора или условию выбора.</span><span class="sxs-lookup"><span data-stu-id="d66f6-120">Each definition must specify one or more type names, a selection set, or a selection condition.</span></span>

<span data-ttu-id="d66f6-121">Выбор наборов обычно используются, когда необходимо определить группу объектов, которые используются в нескольких представлениях.</span><span class="sxs-lookup"><span data-stu-id="d66f6-121">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="d66f6-122">Например можно создать представление таблицы и представления списка для одного набора объектов.</span><span class="sxs-lookup"><span data-stu-id="d66f6-122">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="d66f6-123">Дополнительные сведения об определении наборов выбора см. в разделе [определение задает объектов для представления](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="d66f6-123">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d66f6-124">См. также</span><span class="sxs-lookup"><span data-stu-id="d66f6-124">See Also</span></span>

[<span data-ttu-id="d66f6-125">Определение наборов Выбор</span><span class="sxs-lookup"><span data-stu-id="d66f6-125">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="d66f6-126">Элемент EntrySelectedBy для EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="d66f6-126">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)

[<span data-ttu-id="d66f6-127">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="d66f6-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
