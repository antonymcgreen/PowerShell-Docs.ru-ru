---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент Types для элемента SelectionSet (формат)
description: Элемент Types для элемента SelectionSet (формат)
ms.openlocfilehash: ff3c24e7f52f862dc416b88d50983196ce907012
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645453"
---
# <a name="types-element-for-selectionset-format"></a><span data-ttu-id="2e4f5-103">Элемент Types для элемента SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="2e4f5-103">Types Element for SelectionSet (Format)</span></span>

<span data-ttu-id="2e4f5-104">Определяет объекты .NET, которые находятся в наборе выбора.</span><span class="sxs-lookup"><span data-stu-id="2e4f5-104">Defines the .NET objects that are in the selection set.</span></span>

<span data-ttu-id="2e4f5-105">Элемент Configuration (Format) Селектионсетс элемент (Format) элемент набора выбора (Format) Types (формат) элемент (Format)</span><span class="sxs-lookup"><span data-stu-id="2e4f5-105">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Types Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2e4f5-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2e4f5-106">Syntax</span></span>

```xml
<Types>
  <TypeName>Nameof.NetType</TypeName>
</Types>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="2e4f5-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2e4f5-107">Attributes and Elements</span></span>

<span data-ttu-id="2e4f5-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Types` элемента.</span><span class="sxs-lookup"><span data-stu-id="2e4f5-108">The following sections describe the attributes, child elements, and the parent element of the `Types` element.</span></span> <span data-ttu-id="2e4f5-109">Должен существовать хотя бы один дочерний элемент, но максимальное количество дочерних элементов, которое можно добавить, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="2e4f5-109">There must be at least one child element, but there is no maximum limit to the number of child elements that can be added.</span></span>

### <a name="attributes"></a><span data-ttu-id="2e4f5-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2e4f5-110">Attributes</span></span>

<span data-ttu-id="2e4f5-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2e4f5-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2e4f5-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2e4f5-112">Child Elements</span></span>

|<span data-ttu-id="2e4f5-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="2e4f5-113">Element</span></span>|<span data-ttu-id="2e4f5-114">Описание</span><span class="sxs-lookup"><span data-stu-id="2e4f5-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2e4f5-115">Элемент TypeName типов (Format)</span><span class="sxs-lookup"><span data-stu-id="2e4f5-115">TypeName Element of Types (Format)</span></span>](./typename-element-for-types-format.md)|<span data-ttu-id="2e4f5-116">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="2e4f5-116">Required element.</span></span><br /><br /> <span data-ttu-id="2e4f5-117">Указывает объект .NET, который принадлежит набору выбора.</span><span class="sxs-lookup"><span data-stu-id="2e4f5-117">Specifies the .NET object that belongs to the selection set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2e4f5-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2e4f5-118">Parent Elements</span></span>

|<span data-ttu-id="2e4f5-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="2e4f5-119">Element</span></span>|<span data-ttu-id="2e4f5-120">Описание</span><span class="sxs-lookup"><span data-stu-id="2e4f5-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2e4f5-121">Элемент SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="2e4f5-121">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="2e4f5-122">Определяет набор объектов .NET, на которые может ссылаться имя набора.</span><span class="sxs-lookup"><span data-stu-id="2e4f5-122">Defines a set of .NET objects that can be referenced by the name of the set.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2e4f5-123">Комментарии</span><span class="sxs-lookup"><span data-stu-id="2e4f5-123">Remarks</span></span>

<span data-ttu-id="2e4f5-124">Объекты, определенные этим элементом, составляют набор выбора, который может использоваться представлением, определением представления (представления могут иметь несколько определений) или при указании условия выбора.</span><span class="sxs-lookup"><span data-stu-id="2e4f5-124">The objects defined by this element make up a selection set that can be used by a view, by a definition of a view (views can have multiple definitions), or when specifying a selection condition.</span></span>  <span data-ttu-id="2e4f5-125">Дополнительные сведения о наборах выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="2e4f5-125">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="2e4f5-126">Пример</span><span class="sxs-lookup"><span data-stu-id="2e4f5-126">Example</span></span>

<span data-ttu-id="2e4f5-127">В этом примере показан `SelectionSet` элемент, определяющий четыре типа .NET.</span><span class="sxs-lookup"><span data-stu-id="2e4f5-127">This example shows a `SelectionSet` element that defines four .NET types.</span></span>

```xml
<SelectionSets>
  <SelectionSet>
    <Name>FileSystemTypes</Name>
    <Types>
     <TypeName>System.IO.DirectoryInfo</TypeName>
     <TypeName>System.IO.FileInfo</TypeName>
     <TypeName>Deserialized.System.IO.DirectoryInfo</TypeName>
     <TypeName>Deserialized.System.IO.FileInfo</TypeName>
    </Types>
  </SelectionSet>
</SelectionSets>
```

## <a name="see-also"></a><span data-ttu-id="2e4f5-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="2e4f5-128">See Also</span></span>

[<span data-ttu-id="2e4f5-129">Определение наборов объектов</span><span class="sxs-lookup"><span data-stu-id="2e4f5-129">Defining Sets of Objects</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="2e4f5-130">Элемент SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="2e4f5-130">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="2e4f5-131">Элемент TypeName типов (Format)</span><span class="sxs-lookup"><span data-stu-id="2e4f5-131">TypeName Element of Types (Format)</span></span>](./typename-element-for-types-format.md)

[<span data-ttu-id="2e4f5-132">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e4f5-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
