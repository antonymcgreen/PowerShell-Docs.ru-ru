---
title: Элемент набора выбора (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 848e7acd-d578-4fd1-a575-c0c3b9b5e68a
caps.latest.revision: 17
ms.openlocfilehash: c809aa6c3a40d16cfd2fd99065a846d265ec0f61
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368383"
---
# <a name="selectionset-element-format"></a><span data-ttu-id="602e4-102">Элемент SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="602e4-102">SelectionSet Element (Format)</span></span>

<span data-ttu-id="602e4-103">Определяет набор объектов .NET, на которые может ссылаться имя набора.</span><span class="sxs-lookup"><span data-stu-id="602e4-103">Defines a set of .NET objects that can be referenced by the name of the set.</span></span>

<span data-ttu-id="602e4-104">Элемент Configuration (Format) Селектионсетс элемент (Format) набор выбора (Format)</span><span class="sxs-lookup"><span data-stu-id="602e4-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="602e4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="602e4-105">Syntax</span></span>

```xml
<SelectionSet>
  <Name>SelectionSetName</Name>
  <Types>...</Types>
</SelectionSet>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="602e4-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="602e4-106">Attributes and Elements</span></span>

<span data-ttu-id="602e4-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `SelectionSet`.</span><span class="sxs-lookup"><span data-stu-id="602e4-107">The following sections describe the attributes, child elements, and the parent element of the `SelectionSet` element.</span></span> <span data-ttu-id="602e4-108">Каждый набор выбора должен иметь имя и должен указывать объекты .NET набора.</span><span class="sxs-lookup"><span data-stu-id="602e4-108">Each selection set must have a name, and it must specify the .NET objects of the set.</span></span>

### <a name="attributes"></a><span data-ttu-id="602e4-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="602e4-109">Attributes</span></span>

<span data-ttu-id="602e4-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="602e4-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="602e4-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="602e4-111">Child Elements</span></span>

|<span data-ttu-id="602e4-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="602e4-112">Element</span></span>|<span data-ttu-id="602e4-113">Описание</span><span class="sxs-lookup"><span data-stu-id="602e4-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="602e4-114">Элемент Name для набора выбора (Format)</span><span class="sxs-lookup"><span data-stu-id="602e4-114">Name Element for SelectionSet (Format)</span></span>](./name-element-for-selectionset-format.md)|<span data-ttu-id="602e4-115">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="602e4-115">Required element.</span></span><br /><br /> <span data-ttu-id="602e4-116">Задает имя, используемое для ссылки на набор выбора.</span><span class="sxs-lookup"><span data-stu-id="602e4-116">Specifies the name used to reference the selection set.</span></span>|
|[<span data-ttu-id="602e4-117">Элемент Types (Format)</span><span class="sxs-lookup"><span data-stu-id="602e4-117">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)|<span data-ttu-id="602e4-118">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="602e4-118">Required element.</span></span><br /><br /> <span data-ttu-id="602e4-119">Определяет объекты .NET, которые находятся в наборе выбора.</span><span class="sxs-lookup"><span data-stu-id="602e4-119">Defines the .NET objects that are in the selection set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="602e4-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="602e4-120">Parent Elements</span></span>

|<span data-ttu-id="602e4-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="602e4-121">Element</span></span>|<span data-ttu-id="602e4-122">Описание</span><span class="sxs-lookup"><span data-stu-id="602e4-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="602e4-123">Формат элемента Селектионсетс</span><span class="sxs-lookup"><span data-stu-id="602e4-123">SelectionSets Element Format</span></span>](./selectionsets-element-format.md)|<span data-ttu-id="602e4-124">Определяет общие наборы объектов .NET, которые могут использоваться всеми представлениями файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="602e4-124">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="602e4-125">Замечания</span><span class="sxs-lookup"><span data-stu-id="602e4-125">Remarks</span></span>

<span data-ttu-id="602e4-126">Наборы выбора можно использовать при наличии набора связанных объектов, на которые необходимо создать ссылку, используя одно имя, например набор объектов, связанных через наследование.</span><span class="sxs-lookup"><span data-stu-id="602e4-126">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="602e4-127">При определении представлений можно указать набор объектов, используя имя набора вместо перечисления всех объектов в каждом представлении.</span><span class="sxs-lookup"><span data-stu-id="602e4-127">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="602e4-128">Стандартные наборы выбора задаются по имени при определении представлений файла форматирования или определений представлений.</span><span class="sxs-lookup"><span data-stu-id="602e4-128">Common selection sets are specified by their name when defining the views of the formatting file or the definitions of the views.</span></span> <span data-ttu-id="602e4-129">В этих случаях дочерний элемент `SelectionSetName` для элементов `ViewSelectedBy` и `EntrySelectedBy` указывает используемый набор.</span><span class="sxs-lookup"><span data-stu-id="602e4-129">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` and `EntrySelectedBy` elements specifies the set to be used.</span></span> <span data-ttu-id="602e4-130">Дополнительные сведения о наборах выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="602e4-130">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="602e4-131">Пример</span><span class="sxs-lookup"><span data-stu-id="602e4-131">Example</span></span>

<span data-ttu-id="602e4-132">В следующем примере показан элемент `SelectionSet`, определяющий четыре типа .NET.</span><span class="sxs-lookup"><span data-stu-id="602e4-132">The following example shows a `SelectionSet` element that defines four .NET types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="602e4-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="602e4-133">See Also</span></span>

[<span data-ttu-id="602e4-134">Определение наборов выбора</span><span class="sxs-lookup"><span data-stu-id="602e4-134">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="602e4-135">Элемент Name набора выбора (Format)</span><span class="sxs-lookup"><span data-stu-id="602e4-135">Name Element of SelectionSet (Format)</span></span>](./name-element-for-selectionset-format.md)

[<span data-ttu-id="602e4-136">Элемент Селектионсетс (Format)</span><span class="sxs-lookup"><span data-stu-id="602e4-136">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="602e4-137">Элемент Types (Format)</span><span class="sxs-lookup"><span data-stu-id="602e4-137">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="602e4-138">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="602e4-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
