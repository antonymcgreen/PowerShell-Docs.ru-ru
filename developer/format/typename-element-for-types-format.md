---
title: Имя типа элемента для типов (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0595b99e-b438-4240-b47b-555cf0316f33
caps.latest.revision: 15
ms.openlocfilehash: 4f463ac6b70a00f628c5b93b112c5fa510ff3bfb
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853580"
---
# <a name="typename-element-for-types-format"></a><span data-ttu-id="6c830-102">Элемент TypeName для элемента Types (формат)</span><span class="sxs-lookup"><span data-stu-id="6c830-102">TypeName Element for Types (Format)</span></span>

<span data-ttu-id="6c830-103">Указывает тип объекта, который принадлежит к набору выбора .NET.</span><span class="sxs-lookup"><span data-stu-id="6c830-103">Specifies the .NET type of an object that belongs to the selection set.</span></span>

<span data-ttu-id="6c830-104">SelectionSet элемент SelectionSets (формат) элемент (формат) для конфигурации элемента (формат) типы элемента (формат) элемент TypeName типов (формат)</span><span class="sxs-lookup"><span data-stu-id="6c830-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Types Element (Format) TypeName Element of Types (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6c830-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c830-105">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6c830-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6c830-106">Attributes and Elements</span></span>

<span data-ttu-id="6c830-107">В следующих разделах атрибуты, дочерние элементы и родительский элемент `TypeName` элемент.</span><span class="sxs-lookup"><span data-stu-id="6c830-107">The following sections describe the attributes, child elements, and the parent element of the `TypeName` element.</span></span> <span data-ttu-id="6c830-108">По крайней мере один `TypeName` элемент должен быть включен в наборе выбора.</span><span class="sxs-lookup"><span data-stu-id="6c830-108">At least one `TypeName` element must be included in the selection set.</span></span>

### <a name="attributes"></a><span data-ttu-id="6c830-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6c830-109">Attributes</span></span>

<span data-ttu-id="6c830-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="6c830-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6c830-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6c830-111">Child Elements</span></span>

<span data-ttu-id="6c830-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="6c830-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6c830-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6c830-113">Parent Elements</span></span>

|<span data-ttu-id="6c830-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="6c830-114">Element</span></span>|<span data-ttu-id="6c830-115">Описание</span><span class="sxs-lookup"><span data-stu-id="6c830-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6c830-116">Типы элемента (формат)</span><span class="sxs-lookup"><span data-stu-id="6c830-116">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)|<span data-ttu-id="6c830-117">Определяет объекты .NET, заданных в выделении.</span><span class="sxs-lookup"><span data-stu-id="6c830-117">Defines the .NET objects that are in the selection set.</span></span>|

## <a name="text-value"></a><span data-ttu-id="6c830-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="6c830-118">Text Value</span></span>

<span data-ttu-id="6c830-119">Укажите полное имя типа .NET.</span><span class="sxs-lookup"><span data-stu-id="6c830-119">Specify the fully qualified name for the .NET type.</span></span>

## <a name="remarks"></a><span data-ttu-id="6c830-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="6c830-120">Remarks</span></span>

<span data-ttu-id="6c830-121">Выбор наборов можно использовать при наличии набора связанных объектов, которые вы хотите ссылаться, используя одно имя, таких как набор объектов, которые связаны через наследование.</span><span class="sxs-lookup"><span data-stu-id="6c830-121">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="6c830-122">При определении представления, можно указать набор объектов, используя имя выбора вместо перечисления всех объектов в каждом представлении.</span><span class="sxs-lookup"><span data-stu-id="6c830-122">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="6c830-123">Общие наборы выбора указываются по имени, при определении представлений для форматирования файла.</span><span class="sxs-lookup"><span data-stu-id="6c830-123">Common selection sets are specified by their name when defining the views of the formatting file.</span></span> <span data-ttu-id="6c830-124">В этих случаях `SelectionSetName` дочерний элемент элемента `ViewSelectedBy` элемент для представления задает набор.</span><span class="sxs-lookup"><span data-stu-id="6c830-124">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` element for the view specifies the set.</span></span> <span data-ttu-id="6c830-125">Тем не менее различные записи представления можно также указать набора, который применяется к только что операции представления.</span><span class="sxs-lookup"><span data-stu-id="6c830-125">However, different entries of a view can also specify a selection set that applies to only that entry of the view.</span></span> <span data-ttu-id="6c830-126">Дополнительные сведения о наборах выделения, см. в разделе [определение задает объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="6c830-126">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="6c830-127">Пример</span><span class="sxs-lookup"><span data-stu-id="6c830-127">Example</span></span>

<span data-ttu-id="6c830-128">В следующем примере показан `SelectionSet` элемент, который определяет четыре типа .NET.</span><span class="sxs-lookup"><span data-stu-id="6c830-128">The following example shows a `SelectionSet` element that defines four .NET types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="6c830-129">См. также</span><span class="sxs-lookup"><span data-stu-id="6c830-129">See Also</span></span>

[<span data-ttu-id="6c830-130">Определение наборов Выбор</span><span class="sxs-lookup"><span data-stu-id="6c830-130">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="6c830-131">Элемент SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="6c830-131">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="6c830-132">Элемент SelectionSets (формат)</span><span class="sxs-lookup"><span data-stu-id="6c830-132">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="6c830-133">Типы элемента (формат)</span><span class="sxs-lookup"><span data-stu-id="6c830-133">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="6c830-134">Написание Windows PowDefining из наборов ObjecterShell файла форматирования</span><span class="sxs-lookup"><span data-stu-id="6c830-134">Writing a Windows PowDefining Sets of ObjecterShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
