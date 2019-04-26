---
title: Элемент SelectionSet (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 848e7acd-d578-4fd1-a575-c0c3b9b5e68a
caps.latest.revision: 17
ms.openlocfilehash: c809aa6c3a40d16cfd2fd99065a846d265ec0f61
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62076316"
---
# <a name="selectionset-element-format"></a><span data-ttu-id="7a1de-102">Элемент SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="7a1de-102">SelectionSet Element (Format)</span></span>

<span data-ttu-id="7a1de-103">Определяет набор объектов .NET, которые можно ссылаться по имени набора.</span><span class="sxs-lookup"><span data-stu-id="7a1de-103">Defines a set of .NET objects that can be referenced by the name of the set.</span></span>

<span data-ttu-id="7a1de-104">SelectionSet элемент SelectionSets (формат) элемент (формат) для конфигурации элемента (формат)</span><span class="sxs-lookup"><span data-stu-id="7a1de-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7a1de-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7a1de-105">Syntax</span></span>

```xml
<SelectionSet>
  <Name>SelectionSetName</Name>
  <Types>...</Types>
</SelectionSet>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7a1de-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7a1de-106">Attributes and Elements</span></span>

<span data-ttu-id="7a1de-107">В следующих разделах атрибуты, дочерние элементы и родительский элемент `SelectionSet` элемент.</span><span class="sxs-lookup"><span data-stu-id="7a1de-107">The following sections describe the attributes, child elements, and the parent element of the `SelectionSet` element.</span></span> <span data-ttu-id="7a1de-108">Каждого набора должны иметь имена, и он должен указать объекты .NET из набора.</span><span class="sxs-lookup"><span data-stu-id="7a1de-108">Each selection set must have a name, and it must specify the .NET objects of the set.</span></span>

### <a name="attributes"></a><span data-ttu-id="7a1de-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7a1de-109">Attributes</span></span>

<span data-ttu-id="7a1de-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="7a1de-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7a1de-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7a1de-111">Child Elements</span></span>

|<span data-ttu-id="7a1de-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="7a1de-112">Element</span></span>|<span data-ttu-id="7a1de-113">Описание</span><span class="sxs-lookup"><span data-stu-id="7a1de-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7a1de-114">Элемент Name описания SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="7a1de-114">Name Element for SelectionSet (Format)</span></span>](./name-element-for-selectionset-format.md)|<span data-ttu-id="7a1de-115">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="7a1de-115">Required element.</span></span><br /><br /> <span data-ttu-id="7a1de-116">Указывает имя, используемое для ссылки на наборе выбора.</span><span class="sxs-lookup"><span data-stu-id="7a1de-116">Specifies the name used to reference the selection set.</span></span>|
|[<span data-ttu-id="7a1de-117">Типы элемента (формат)</span><span class="sxs-lookup"><span data-stu-id="7a1de-117">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)|<span data-ttu-id="7a1de-118">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="7a1de-118">Required element.</span></span><br /><br /> <span data-ttu-id="7a1de-119">Определяет объекты .NET, заданных в выделении.</span><span class="sxs-lookup"><span data-stu-id="7a1de-119">Defines the .NET objects that are in the selection set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="7a1de-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7a1de-120">Parent Elements</span></span>

|<span data-ttu-id="7a1de-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="7a1de-121">Element</span></span>|<span data-ttu-id="7a1de-122">Описание</span><span class="sxs-lookup"><span data-stu-id="7a1de-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7a1de-123">Формат SelectionSets элемент</span><span class="sxs-lookup"><span data-stu-id="7a1de-123">SelectionSets Element Format</span></span>](./selectionsets-element-format.md)|<span data-ttu-id="7a1de-124">Определяет общие наборы объектов .NET, которые могут использоваться все представления файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="7a1de-124">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7a1de-125">Замечания</span><span class="sxs-lookup"><span data-stu-id="7a1de-125">Remarks</span></span>

<span data-ttu-id="7a1de-126">Выбор наборов можно использовать при наличии набора связанных объектов, которые вы хотите ссылаться, используя одно имя, таких как набор объектов, которые связаны через наследование.</span><span class="sxs-lookup"><span data-stu-id="7a1de-126">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="7a1de-127">При определении представления, можно указать набор объектов, используя имя выбора вместо перечисления всех объектов в каждом представлении.</span><span class="sxs-lookup"><span data-stu-id="7a1de-127">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="7a1de-128">Общие наборы выбора указываются по имени, при определении представлений для форматирования файла или определения представления.</span><span class="sxs-lookup"><span data-stu-id="7a1de-128">Common selection sets are specified by their name when defining the views of the formatting file or the definitions of the views.</span></span> <span data-ttu-id="7a1de-129">В этих случаях `SelectionSetName` дочерний элемент элемента `ViewSelectedBy` и `EntrySelectedBy` элементов указывает набор, который требуется использовать.</span><span class="sxs-lookup"><span data-stu-id="7a1de-129">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` and `EntrySelectedBy` elements specifies the set to be used.</span></span> <span data-ttu-id="7a1de-130">Дополнительные сведения о наборах выделения, см. в разделе [определение задает объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="7a1de-130">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="7a1de-131">Пример</span><span class="sxs-lookup"><span data-stu-id="7a1de-131">Example</span></span>

<span data-ttu-id="7a1de-132">В следующем примере показан `SelectionSet` элемент, который определяет четыре типа .NET.</span><span class="sxs-lookup"><span data-stu-id="7a1de-132">The following example shows a `SelectionSet` element that defines four .NET types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="7a1de-133">См. также</span><span class="sxs-lookup"><span data-stu-id="7a1de-133">See Also</span></span>

[<span data-ttu-id="7a1de-134">Определение наборов Выбор</span><span class="sxs-lookup"><span data-stu-id="7a1de-134">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="7a1de-135">Элемент Name из SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="7a1de-135">Name Element of SelectionSet (Format)</span></span>](./name-element-for-selectionset-format.md)

[<span data-ttu-id="7a1de-136">Элемент SelectionSets (формат)</span><span class="sxs-lookup"><span data-stu-id="7a1de-136">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="7a1de-137">Типы элемента (формат)</span><span class="sxs-lookup"><span data-stu-id="7a1de-137">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="7a1de-138">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="7a1de-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
