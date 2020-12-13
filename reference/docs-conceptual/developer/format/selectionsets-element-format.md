---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент SelectionSets (формат)
description: Элемент SelectionSets (формат)
ms.openlocfilehash: e5c928dfb82bc6963b4a87aef9ec06d34cacfdcb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654922"
---
# <a name="selectionsets-element-format"></a><span data-ttu-id="e2a23-103">Элемент SelectionSets (формат)</span><span class="sxs-lookup"><span data-stu-id="e2a23-103">SelectionSets Element (Format)</span></span>

<span data-ttu-id="e2a23-104">Определяет общие наборы объектов .NET, которые могут использоваться всеми представлениями файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="e2a23-104">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span> <span data-ttu-id="e2a23-105">Представления и элементы управления файла форматирования могут ссылаться на полный набор объектов, используя только имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="e2a23-105">The views and controls of the formatting file can reference the complete set of objects by using only the name of the selection set.</span></span>

<span data-ttu-id="e2a23-106">Формат элемента Селектионсетс элемента конфигурации</span><span class="sxs-lookup"><span data-stu-id="e2a23-106">Configuration Element SelectionSets Element Format</span></span>

## <a name="syntax"></a><span data-ttu-id="e2a23-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2a23-107">Syntax</span></span>

```xml
<SelectionSets>
  <SelectionSet>...</SelectionSet>
</SelectionSets>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e2a23-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e2a23-108">Attributes and Elements</span></span>

<span data-ttu-id="e2a23-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionSets` элемента.</span><span class="sxs-lookup"><span data-stu-id="e2a23-109">The following sections describe the attributes, child elements, and parent element of the `SelectionSets` element.</span></span> <span data-ttu-id="e2a23-110">Каждый дочерний элемент определяет набор объектов, на которые может ссылаться имя набора.</span><span class="sxs-lookup"><span data-stu-id="e2a23-110">Each child element defines a set of objects that can be referenced by the name of the set.</span></span> <span data-ttu-id="e2a23-111">Порядок дочерних элементов не важен.</span><span class="sxs-lookup"><span data-stu-id="e2a23-111">The order of the child elements is not significant.</span></span>

### <a name="attributes"></a><span data-ttu-id="e2a23-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e2a23-112">Attributes</span></span>

<span data-ttu-id="e2a23-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e2a23-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e2a23-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e2a23-114">Child Elements</span></span>

|<span data-ttu-id="e2a23-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="e2a23-115">Element</span></span>|<span data-ttu-id="e2a23-116">Описание</span><span class="sxs-lookup"><span data-stu-id="e2a23-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e2a23-117">Элемент SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="e2a23-117">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="e2a23-118">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e2a23-118">Required element.</span></span><br /><br /> <span data-ttu-id="e2a23-119">Определяет один набор объектов .NET, на который может ссылаться имя набора.</span><span class="sxs-lookup"><span data-stu-id="e2a23-119">Defines a single set of .NET objects that can be referenced by the name of the set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e2a23-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e2a23-120">Parent Elements</span></span>

|<span data-ttu-id="e2a23-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="e2a23-121">Element</span></span>|<span data-ttu-id="e2a23-122">Описание</span><span class="sxs-lookup"><span data-stu-id="e2a23-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e2a23-123">Элемент Configuration</span><span class="sxs-lookup"><span data-stu-id="e2a23-123">Configuration Element</span></span>](./configuration-element-format.md)|<span data-ttu-id="e2a23-124">Представляет элемент верхнего уровня файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="e2a23-124">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e2a23-125">Комментарии</span><span class="sxs-lookup"><span data-stu-id="e2a23-125">Remarks</span></span>

<span data-ttu-id="e2a23-126">Наборы выбора можно использовать при наличии набора связанных объектов, на которые необходимо создать ссылку, используя одно имя, например набор объектов, связанных через наследование.</span><span class="sxs-lookup"><span data-stu-id="e2a23-126">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="e2a23-127">При определении представлений можно указать набор объектов, используя имя набора вместо перечисления всех объектов в каждом представлении.</span><span class="sxs-lookup"><span data-stu-id="e2a23-127">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="e2a23-128">Стандартные наборы выбора задаются по имени при определении представлений файла форматирования или определений представлений.</span><span class="sxs-lookup"><span data-stu-id="e2a23-128">Common selection sets are specified by their name when defining the views of the formatting file or the definitions of the views.</span></span> <span data-ttu-id="e2a23-129">В таких случаях `SelectionSetName` дочерний элемент `ViewSelectedBy` `EntrySelectedBy` элементов и указывает используемый набор.</span><span class="sxs-lookup"><span data-stu-id="e2a23-129">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` and `EntrySelectedBy` elements specifies the set to be used.</span></span> <span data-ttu-id="e2a23-130">Дополнительные сведения о наборах выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="e2a23-130">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e2a23-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="e2a23-131">See Also</span></span>

[<span data-ttu-id="e2a23-132">Элемент настройки</span><span class="sxs-lookup"><span data-stu-id="e2a23-132">Configuration Element</span></span>](./configuration-element-format.md)

[<span data-ttu-id="e2a23-133">Определение наборов выделенных фрагментов</span><span class="sxs-lookup"><span data-stu-id="e2a23-133">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="e2a23-134">Элемент SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="e2a23-134">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="e2a23-135">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2a23-135">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
