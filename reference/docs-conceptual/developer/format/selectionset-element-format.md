---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент SelectionSet (формат)
description: Элемент SelectionSet (формат)
ms.openlocfilehash: 944aa83569ad8ca789746a71f60e5da5c19fbf01
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647876"
---
# <a name="selectionset-element-format"></a><span data-ttu-id="0b25a-103">Элемент SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="0b25a-103">SelectionSet Element (Format)</span></span>

<span data-ttu-id="0b25a-104">Определяет набор объектов .NET, на которые может ссылаться имя набора.</span><span class="sxs-lookup"><span data-stu-id="0b25a-104">Defines a set of .NET objects that can be referenced by the name of the set.</span></span>

<span data-ttu-id="0b25a-105">Элемент Configuration (Format) Селектионсетс элемент (Format) набор выбора (Format)</span><span class="sxs-lookup"><span data-stu-id="0b25a-105">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0b25a-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b25a-106">Syntax</span></span>

```xml
<SelectionSet>
  <Name>SelectionSetName</Name>
  <Types>...</Types>
</SelectionSet>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0b25a-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0b25a-107">Attributes and Elements</span></span>

<span data-ttu-id="0b25a-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionSet` элемента.</span><span class="sxs-lookup"><span data-stu-id="0b25a-108">The following sections describe the attributes, child elements, and the parent element of the `SelectionSet` element.</span></span> <span data-ttu-id="0b25a-109">Каждый набор выбора должен иметь имя и должен указывать объекты .NET набора.</span><span class="sxs-lookup"><span data-stu-id="0b25a-109">Each selection set must have a name, and it must specify the .NET objects of the set.</span></span>

### <a name="attributes"></a><span data-ttu-id="0b25a-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0b25a-110">Attributes</span></span>

<span data-ttu-id="0b25a-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0b25a-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0b25a-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0b25a-112">Child Elements</span></span>

|<span data-ttu-id="0b25a-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="0b25a-113">Element</span></span>|<span data-ttu-id="0b25a-114">Описание</span><span class="sxs-lookup"><span data-stu-id="0b25a-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0b25a-115">Элемент Name для элемента SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="0b25a-115">Name Element for SelectionSet (Format)</span></span>](./name-element-for-selectionset-format.md)|<span data-ttu-id="0b25a-116">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="0b25a-116">Required element.</span></span><br /><br /> <span data-ttu-id="0b25a-117">Задает имя, используемое для ссылки на набор выбора.</span><span class="sxs-lookup"><span data-stu-id="0b25a-117">Specifies the name used to reference the selection set.</span></span>|
|[<span data-ttu-id="0b25a-118">Элемент Types (Format)</span><span class="sxs-lookup"><span data-stu-id="0b25a-118">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)|<span data-ttu-id="0b25a-119">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="0b25a-119">Required element.</span></span><br /><br /> <span data-ttu-id="0b25a-120">Определяет объекты .NET, которые находятся в наборе выбора.</span><span class="sxs-lookup"><span data-stu-id="0b25a-120">Defines the .NET objects that are in the selection set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="0b25a-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0b25a-121">Parent Elements</span></span>

|<span data-ttu-id="0b25a-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="0b25a-122">Element</span></span>|<span data-ttu-id="0b25a-123">Описание</span><span class="sxs-lookup"><span data-stu-id="0b25a-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0b25a-124">Формат элемента Селектионсетс</span><span class="sxs-lookup"><span data-stu-id="0b25a-124">SelectionSets Element Format</span></span>](./selectionsets-element-format.md)|<span data-ttu-id="0b25a-125">Определяет общие наборы объектов .NET, которые могут использоваться всеми представлениями файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="0b25a-125">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0b25a-126">Комментарии</span><span class="sxs-lookup"><span data-stu-id="0b25a-126">Remarks</span></span>

<span data-ttu-id="0b25a-127">Наборы выбора можно использовать при наличии набора связанных объектов, на которые необходимо создать ссылку, используя одно имя, например набор объектов, связанных через наследование.</span><span class="sxs-lookup"><span data-stu-id="0b25a-127">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="0b25a-128">При определении представлений можно указать набор объектов, используя имя набора вместо перечисления всех объектов в каждом представлении.</span><span class="sxs-lookup"><span data-stu-id="0b25a-128">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="0b25a-129">Стандартные наборы выбора задаются по имени при определении представлений файла форматирования или определений представлений.</span><span class="sxs-lookup"><span data-stu-id="0b25a-129">Common selection sets are specified by their name when defining the views of the formatting file or the definitions of the views.</span></span> <span data-ttu-id="0b25a-130">В таких случаях `SelectionSetName` дочерний элемент `ViewSelectedBy` `EntrySelectedBy` элементов и указывает используемый набор.</span><span class="sxs-lookup"><span data-stu-id="0b25a-130">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` and `EntrySelectedBy` elements specifies the set to be used.</span></span> <span data-ttu-id="0b25a-131">Дополнительные сведения о наборах выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="0b25a-131">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="0b25a-132">Пример</span><span class="sxs-lookup"><span data-stu-id="0b25a-132">Example</span></span>

<span data-ttu-id="0b25a-133">В следующем примере показан `SelectionSet` элемент, определяющий четыре типа .NET.</span><span class="sxs-lookup"><span data-stu-id="0b25a-133">The following example shows a `SelectionSet` element that defines four .NET types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="0b25a-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="0b25a-134">See Also</span></span>

[<span data-ttu-id="0b25a-135">Определение наборов выделенных фрагментов</span><span class="sxs-lookup"><span data-stu-id="0b25a-135">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="0b25a-136">Элемент Name набора выбора (Format)</span><span class="sxs-lookup"><span data-stu-id="0b25a-136">Name Element of SelectionSet (Format)</span></span>](./name-element-for-selectionset-format.md)

[<span data-ttu-id="0b25a-137">Элемент SelectionSets (формат)</span><span class="sxs-lookup"><span data-stu-id="0b25a-137">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="0b25a-138">Элемент Types (Format)</span><span class="sxs-lookup"><span data-stu-id="0b25a-138">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="0b25a-139">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b25a-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
