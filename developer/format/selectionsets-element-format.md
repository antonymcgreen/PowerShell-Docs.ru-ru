---
title: Элемент SelectionSets (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebbac73a-1c99-4388-9f47-703cd024dc6d
caps.latest.revision: 18
ms.openlocfilehash: a9356635d60d5f8c5d4dec4ec8b7d0aea2b037dd
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853570"
---
# <a name="selectionsets-element-format"></a><span data-ttu-id="82a5d-102">Элемент SelectionSets (формат)</span><span class="sxs-lookup"><span data-stu-id="82a5d-102">SelectionSets Element (Format)</span></span>

<span data-ttu-id="82a5d-103">Определяет общие наборы объектов .NET, которые могут использоваться все представления файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="82a5d-103">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span> <span data-ttu-id="82a5d-104">Представления и элементы управления форматирования файла, используя только имя набора выбора могут ссылаться на полный набор объектов.</span><span class="sxs-lookup"><span data-stu-id="82a5d-104">The views and controls of the formatting file can reference the complete set of objects by using only the name of the selection set.</span></span>

<span data-ttu-id="82a5d-105">Формат элемента SelectionSets элемент конфигурации</span><span class="sxs-lookup"><span data-stu-id="82a5d-105">Configuration Element SelectionSets Element Format</span></span>

## <a name="syntax"></a><span data-ttu-id="82a5d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82a5d-106">Syntax</span></span>

```xml
<SelectionSets>
  <SelectionSet>...</SelectionSet>
</SelectionSets>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="82a5d-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="82a5d-107">Attributes and Elements</span></span>

<span data-ttu-id="82a5d-108">В следующих разделах атрибуты, дочерние элементы и родительский элемент `SelectionSets` элемент.</span><span class="sxs-lookup"><span data-stu-id="82a5d-108">The following sections describe the attributes, child elements, and parent element of the `SelectionSets` element.</span></span> <span data-ttu-id="82a5d-109">Каждый дочерний элемент определяет набор объектов, которые можно ссылаться по имени набора.</span><span class="sxs-lookup"><span data-stu-id="82a5d-109">Each child element defines a set of objects that can be referenced by the name of the set.</span></span> <span data-ttu-id="82a5d-110">Порядок дочерних элементов не имеет значения.</span><span class="sxs-lookup"><span data-stu-id="82a5d-110">The order of the child elements is not significant.</span></span>

### <a name="attributes"></a><span data-ttu-id="82a5d-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="82a5d-111">Attributes</span></span>

<span data-ttu-id="82a5d-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="82a5d-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="82a5d-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="82a5d-113">Child Elements</span></span>

|<span data-ttu-id="82a5d-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="82a5d-114">Element</span></span>|<span data-ttu-id="82a5d-115">Описание</span><span class="sxs-lookup"><span data-stu-id="82a5d-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="82a5d-116">Элемент SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="82a5d-116">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="82a5d-117">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="82a5d-117">Required element.</span></span><br /><br /> <span data-ttu-id="82a5d-118">Определяет один набор объектов .NET, которые можно ссылаться по имени набора.</span><span class="sxs-lookup"><span data-stu-id="82a5d-118">Defines a single set of .NET objects that can be referenced by the name of the set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="82a5d-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="82a5d-119">Parent Elements</span></span>

|<span data-ttu-id="82a5d-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="82a5d-120">Element</span></span>|<span data-ttu-id="82a5d-121">Описание</span><span class="sxs-lookup"><span data-stu-id="82a5d-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="82a5d-122">Элемент конфигурации</span><span class="sxs-lookup"><span data-stu-id="82a5d-122">Configuration Element</span></span>](./configuration-element-format.md)|<span data-ttu-id="82a5d-123">Представляет элемент верхнего уровня файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="82a5d-123">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="82a5d-124">Замечания</span><span class="sxs-lookup"><span data-stu-id="82a5d-124">Remarks</span></span>

<span data-ttu-id="82a5d-125">Выбор наборов можно использовать при наличии набора связанных объектов, которые вы хотите ссылаться, используя одно имя, таких как набор объектов, которые связаны через наследование.</span><span class="sxs-lookup"><span data-stu-id="82a5d-125">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="82a5d-126">При определении представления, можно указать набор объектов, используя имя выбора вместо перечисления всех объектов в каждом представлении.</span><span class="sxs-lookup"><span data-stu-id="82a5d-126">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="82a5d-127">Общие наборы выбора указываются по имени, при определении представлений для форматирования файла или определения представления.</span><span class="sxs-lookup"><span data-stu-id="82a5d-127">Common selection sets are specified by their name when defining the views of the formatting file or the definitions of the views.</span></span> <span data-ttu-id="82a5d-128">В этих случаях `SelectionSetName` дочерний элемент элемента `ViewSelectedBy` и `EntrySelectedBy` элементов указывает набор, который требуется использовать.</span><span class="sxs-lookup"><span data-stu-id="82a5d-128">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` and `EntrySelectedBy` elements specifies the set to be used.</span></span> <span data-ttu-id="82a5d-129">Дополнительные сведения о наборах выделения, см. в разделе [определение задает объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="82a5d-129">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="82a5d-130">См. также</span><span class="sxs-lookup"><span data-stu-id="82a5d-130">See Also</span></span>

[<span data-ttu-id="82a5d-131">Элемент конфигурации</span><span class="sxs-lookup"><span data-stu-id="82a5d-131">Configuration Element</span></span>](./configuration-element-format.md)

[<span data-ttu-id="82a5d-132">Определение наборов Выбор</span><span class="sxs-lookup"><span data-stu-id="82a5d-132">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="82a5d-133">Элемент SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="82a5d-133">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="82a5d-134">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="82a5d-134">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
