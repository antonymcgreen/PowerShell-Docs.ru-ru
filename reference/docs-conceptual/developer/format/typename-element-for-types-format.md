---
title: Элемент TypeName для типов (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 40fad73c66124d6c3b0d969b4268713a492c963a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772541"
---
# <a name="typename-element-for-types-format"></a><span data-ttu-id="90fc4-102">Элемент TypeName для элемента Types (формат)</span><span class="sxs-lookup"><span data-stu-id="90fc4-102">TypeName Element for Types (Format)</span></span>

<span data-ttu-id="90fc4-103">Указывает тип .NET объекта, который принадлежит к набору выбора.</span><span class="sxs-lookup"><span data-stu-id="90fc4-103">Specifies the .NET type of an object that belongs to the selection set.</span></span>

<span data-ttu-id="90fc4-104">Элемент Configuration (Format) Селектионсетс элемент (Format) элемент набора выбора (Format) Types элемент (Format) имя_типа Types (Format)</span><span class="sxs-lookup"><span data-stu-id="90fc4-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Types Element (Format) TypeName Element of Types (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="90fc4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="90fc4-105">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="90fc4-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="90fc4-106">Attributes and Elements</span></span>

<span data-ttu-id="90fc4-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TypeName` элемента.</span><span class="sxs-lookup"><span data-stu-id="90fc4-107">The following sections describe the attributes, child elements, and the parent element of the `TypeName` element.</span></span> <span data-ttu-id="90fc4-108">`TypeName`В набор выбора необходимо добавить хотя бы один элемент.</span><span class="sxs-lookup"><span data-stu-id="90fc4-108">At least one `TypeName` element must be included in the selection set.</span></span>

### <a name="attributes"></a><span data-ttu-id="90fc4-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="90fc4-109">Attributes</span></span>

<span data-ttu-id="90fc4-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="90fc4-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="90fc4-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="90fc4-111">Child Elements</span></span>

<span data-ttu-id="90fc4-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="90fc4-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="90fc4-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="90fc4-113">Parent Elements</span></span>

|<span data-ttu-id="90fc4-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="90fc4-114">Element</span></span>|<span data-ttu-id="90fc4-115">Описание</span><span class="sxs-lookup"><span data-stu-id="90fc4-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="90fc4-116">Элемент Types (Format)</span><span class="sxs-lookup"><span data-stu-id="90fc4-116">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)|<span data-ttu-id="90fc4-117">Определяет объекты .NET, которые находятся в наборе выбора.</span><span class="sxs-lookup"><span data-stu-id="90fc4-117">Defines the .NET objects that are in the selection set.</span></span>|

## <a name="text-value"></a><span data-ttu-id="90fc4-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="90fc4-118">Text Value</span></span>

<span data-ttu-id="90fc4-119">Укажите полное имя для типа .NET.</span><span class="sxs-lookup"><span data-stu-id="90fc4-119">Specify the fully qualified name for the .NET type.</span></span>

## <a name="remarks"></a><span data-ttu-id="90fc4-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="90fc4-120">Remarks</span></span>

<span data-ttu-id="90fc4-121">Наборы выбора можно использовать при наличии набора связанных объектов, на которые необходимо создать ссылку, используя одно имя, например набор объектов, связанных через наследование.</span><span class="sxs-lookup"><span data-stu-id="90fc4-121">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="90fc4-122">При определении представлений можно указать набор объектов, используя имя набора вместо перечисления всех объектов в каждом представлении.</span><span class="sxs-lookup"><span data-stu-id="90fc4-122">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="90fc4-123">Стандартные наборы выбора задаются по имени при определении представлений файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="90fc4-123">Common selection sets are specified by their name when defining the views of the formatting file.</span></span> <span data-ttu-id="90fc4-124">В таких случаях `SelectionSetName` дочерний элемент `ViewSelectedBy` элемента для представления задает набор.</span><span class="sxs-lookup"><span data-stu-id="90fc4-124">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` element for the view specifies the set.</span></span> <span data-ttu-id="90fc4-125">Однако в разных записях представления также можно указать набор выбора, который применяется только к этой записи представления.</span><span class="sxs-lookup"><span data-stu-id="90fc4-125">However, different entries of a view can also specify a selection set that applies to only that entry of the view.</span></span> <span data-ttu-id="90fc4-126">Дополнительные сведения о наборах выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="90fc4-126">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="90fc4-127">Пример</span><span class="sxs-lookup"><span data-stu-id="90fc4-127">Example</span></span>

<span data-ttu-id="90fc4-128">В следующем примере показан `SelectionSet` элемент, определяющий четыре типа .NET.</span><span class="sxs-lookup"><span data-stu-id="90fc4-128">The following example shows a `SelectionSet` element that defines four .NET types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="90fc4-129">См. также</span><span class="sxs-lookup"><span data-stu-id="90fc4-129">See Also</span></span>

[<span data-ttu-id="90fc4-130">Определение наборов выделенных фрагментов</span><span class="sxs-lookup"><span data-stu-id="90fc4-130">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="90fc4-131">Элемент SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="90fc4-131">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="90fc4-132">Элемент SelectionSets (формат)</span><span class="sxs-lookup"><span data-stu-id="90fc4-132">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="90fc4-133">Элемент Types (Format)</span><span class="sxs-lookup"><span data-stu-id="90fc4-133">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="90fc4-134">Написание файла форматирования Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="90fc4-134">Writing a Windows PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
