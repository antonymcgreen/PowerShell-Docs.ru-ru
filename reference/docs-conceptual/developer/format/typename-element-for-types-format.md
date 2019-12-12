---
title: Элемент TypeName для типов (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0595b99e-b438-4240-b47b-555cf0316f33
caps.latest.revision: 15
ms.openlocfilehash: bd5baa03c2050b2c3bbe1d7697c253d923175d39
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368033"
---
# <a name="typename-element-for-types-format"></a><span data-ttu-id="7f8aa-102">Элемент TypeName для элемента Types (формат)</span><span class="sxs-lookup"><span data-stu-id="7f8aa-102">TypeName Element for Types (Format)</span></span>

<span data-ttu-id="7f8aa-103">Указывает тип .NET объекта, который принадлежит к набору выбора.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-103">Specifies the .NET type of an object that belongs to the selection set.</span></span>

<span data-ttu-id="7f8aa-104">Элемент Configuration (Format) Селектионсетс элемент (Format) элемент набора выбора (Format) Types элемент (Format) имя_типа Types (Format)</span><span class="sxs-lookup"><span data-stu-id="7f8aa-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Types Element (Format) TypeName Element of Types (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7f8aa-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7f8aa-105">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7f8aa-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7f8aa-106">Attributes and Elements</span></span>

<span data-ttu-id="7f8aa-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `TypeName`.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-107">The following sections describe the attributes, child elements, and the parent element of the `TypeName` element.</span></span> <span data-ttu-id="7f8aa-108">В набор выбора необходимо добавить по крайней мере один элемент `TypeName`.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-108">At least one `TypeName` element must be included in the selection set.</span></span>

### <a name="attributes"></a><span data-ttu-id="7f8aa-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7f8aa-109">Attributes</span></span>

<span data-ttu-id="7f8aa-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7f8aa-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7f8aa-111">Child Elements</span></span>

<span data-ttu-id="7f8aa-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7f8aa-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7f8aa-113">Parent Elements</span></span>

|<span data-ttu-id="7f8aa-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="7f8aa-114">Element</span></span>|<span data-ttu-id="7f8aa-115">Описание</span><span class="sxs-lookup"><span data-stu-id="7f8aa-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7f8aa-116">Элемент Types (Format)</span><span class="sxs-lookup"><span data-stu-id="7f8aa-116">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)|<span data-ttu-id="7f8aa-117">Определяет объекты .NET, которые находятся в наборе выбора.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-117">Defines the .NET objects that are in the selection set.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7f8aa-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="7f8aa-118">Text Value</span></span>

<span data-ttu-id="7f8aa-119">Укажите полное имя для типа .NET.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-119">Specify the fully qualified name for the .NET type.</span></span>

## <a name="remarks"></a><span data-ttu-id="7f8aa-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="7f8aa-120">Remarks</span></span>

<span data-ttu-id="7f8aa-121">Наборы выбора можно использовать при наличии набора связанных объектов, на которые необходимо создать ссылку, используя одно имя, например набор объектов, связанных через наследование.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-121">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="7f8aa-122">При определении представлений можно указать набор объектов, используя имя набора вместо перечисления всех объектов в каждом представлении.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-122">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="7f8aa-123">Стандартные наборы выбора задаются по имени при определении представлений файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-123">Common selection sets are specified by their name when defining the views of the formatting file.</span></span> <span data-ttu-id="7f8aa-124">В таких случаях `SelectionSetName` дочерний элемент элемента `ViewSelectedBy` для представления задает набор.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-124">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` element for the view specifies the set.</span></span> <span data-ttu-id="7f8aa-125">Однако в разных записях представления также можно указать набор выбора, который применяется только к этой записи представления.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-125">However, different entries of a view can also specify a selection set that applies to only that entry of the view.</span></span> <span data-ttu-id="7f8aa-126">Дополнительные сведения о наборах выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="7f8aa-126">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="7f8aa-127">Пример</span><span class="sxs-lookup"><span data-stu-id="7f8aa-127">Example</span></span>

<span data-ttu-id="7f8aa-128">В следующем примере показан элемент `SelectionSet`, определяющий четыре типа .NET.</span><span class="sxs-lookup"><span data-stu-id="7f8aa-128">The following example shows a `SelectionSet` element that defines four .NET types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="7f8aa-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="7f8aa-129">See Also</span></span>

[<span data-ttu-id="7f8aa-130">Определение наборов выбора</span><span class="sxs-lookup"><span data-stu-id="7f8aa-130">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="7f8aa-131">Элемент набора выбора (Format)</span><span class="sxs-lookup"><span data-stu-id="7f8aa-131">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="7f8aa-132">Элемент Селектионсетс (Format)</span><span class="sxs-lookup"><span data-stu-id="7f8aa-132">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="7f8aa-133">Элемент Types (Format)</span><span class="sxs-lookup"><span data-stu-id="7f8aa-133">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="7f8aa-134">Запись файла форматирования Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7f8aa-134">Writing a Windows PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
