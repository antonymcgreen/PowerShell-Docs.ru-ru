---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент TypeName для элемента Types (формат)
description: Элемент TypeName для элемента Types (формат)
ms.openlocfilehash: c656b8e7e5877b72ff2164e5b417857273cada61
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664621"
---
# <a name="typename-element-for-types-format"></a><span data-ttu-id="e5124-103">Элемент TypeName для элемента Types (формат)</span><span class="sxs-lookup"><span data-stu-id="e5124-103">TypeName Element for Types (Format)</span></span>

<span data-ttu-id="e5124-104">Указывает тип .NET объекта, который принадлежит к набору выбора.</span><span class="sxs-lookup"><span data-stu-id="e5124-104">Specifies the .NET type of an object that belongs to the selection set.</span></span>

<span data-ttu-id="e5124-105">Элемент Configuration (Format) Селектионсетс элемент (Format) элемент набора выбора (Format) Types элемент (Format) имя_типа Types (Format)</span><span class="sxs-lookup"><span data-stu-id="e5124-105">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Types Element (Format) TypeName Element of Types (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e5124-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e5124-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e5124-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e5124-107">Attributes and Elements</span></span>

<span data-ttu-id="e5124-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TypeName` элемента.</span><span class="sxs-lookup"><span data-stu-id="e5124-108">The following sections describe the attributes, child elements, and the parent element of the `TypeName` element.</span></span> <span data-ttu-id="e5124-109">`TypeName`В набор выбора необходимо добавить хотя бы один элемент.</span><span class="sxs-lookup"><span data-stu-id="e5124-109">At least one `TypeName` element must be included in the selection set.</span></span>

### <a name="attributes"></a><span data-ttu-id="e5124-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e5124-110">Attributes</span></span>

<span data-ttu-id="e5124-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e5124-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e5124-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e5124-112">Child Elements</span></span>

<span data-ttu-id="e5124-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e5124-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e5124-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e5124-114">Parent Elements</span></span>

|<span data-ttu-id="e5124-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="e5124-115">Element</span></span>|<span data-ttu-id="e5124-116">Описание</span><span class="sxs-lookup"><span data-stu-id="e5124-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e5124-117">Элемент Types (Format)</span><span class="sxs-lookup"><span data-stu-id="e5124-117">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)|<span data-ttu-id="e5124-118">Определяет объекты .NET, которые находятся в наборе выбора.</span><span class="sxs-lookup"><span data-stu-id="e5124-118">Defines the .NET objects that are in the selection set.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e5124-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="e5124-119">Text Value</span></span>

<span data-ttu-id="e5124-120">Укажите полное имя для типа .NET.</span><span class="sxs-lookup"><span data-stu-id="e5124-120">Specify the fully qualified name for the .NET type.</span></span>

## <a name="remarks"></a><span data-ttu-id="e5124-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="e5124-121">Remarks</span></span>

<span data-ttu-id="e5124-122">Наборы выбора можно использовать при наличии набора связанных объектов, на которые необходимо создать ссылку, используя одно имя, например набор объектов, связанных через наследование.</span><span class="sxs-lookup"><span data-stu-id="e5124-122">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="e5124-123">При определении представлений можно указать набор объектов, используя имя набора вместо перечисления всех объектов в каждом представлении.</span><span class="sxs-lookup"><span data-stu-id="e5124-123">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="e5124-124">Стандартные наборы выбора задаются по имени при определении представлений файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="e5124-124">Common selection sets are specified by their name when defining the views of the formatting file.</span></span> <span data-ttu-id="e5124-125">В таких случаях `SelectionSetName` дочерний элемент `ViewSelectedBy` элемента для представления задает набор.</span><span class="sxs-lookup"><span data-stu-id="e5124-125">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` element for the view specifies the set.</span></span> <span data-ttu-id="e5124-126">Однако в разных записях представления также можно указать набор выбора, который применяется только к этой записи представления.</span><span class="sxs-lookup"><span data-stu-id="e5124-126">However, different entries of a view can also specify a selection set that applies to only that entry of the view.</span></span> <span data-ttu-id="e5124-127">Дополнительные сведения о наборах выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="e5124-127">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="e5124-128">Пример</span><span class="sxs-lookup"><span data-stu-id="e5124-128">Example</span></span>

<span data-ttu-id="e5124-129">В следующем примере показан `SelectionSet` элемент, определяющий четыре типа .NET.</span><span class="sxs-lookup"><span data-stu-id="e5124-129">The following example shows a `SelectionSet` element that defines four .NET types.</span></span>

```
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

## <a name="see-also"></a><span data-ttu-id="e5124-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="e5124-130">See Also</span></span>

[<span data-ttu-id="e5124-131">Определение наборов выделенных фрагментов</span><span class="sxs-lookup"><span data-stu-id="e5124-131">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="e5124-132">Элемент SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="e5124-132">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="e5124-133">Элемент SelectionSets (формат)</span><span class="sxs-lookup"><span data-stu-id="e5124-133">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="e5124-134">Элемент Types (Format)</span><span class="sxs-lookup"><span data-stu-id="e5124-134">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="e5124-135">Написание файла форматирования Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5124-135">Writing a Windows PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
