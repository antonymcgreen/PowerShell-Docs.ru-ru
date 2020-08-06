---
title: Элемент набора выбора (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: cf47229993458492c712d28e04913e75d1bde386
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783404"
---
# <a name="selectionset-element-format"></a><span data-ttu-id="aaf6c-102">Элемент SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="aaf6c-102">SelectionSet Element (Format)</span></span>

<span data-ttu-id="aaf6c-103">Определяет набор объектов .NET, на которые может ссылаться имя набора.</span><span class="sxs-lookup"><span data-stu-id="aaf6c-103">Defines a set of .NET objects that can be referenced by the name of the set.</span></span>

<span data-ttu-id="aaf6c-104">Элемент Configuration (Format) Селектионсетс элемент (Format) набор выбора (Format)</span><span class="sxs-lookup"><span data-stu-id="aaf6c-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="aaf6c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aaf6c-105">Syntax</span></span>

```xml
<SelectionSet>
  <Name>SelectionSetName</Name>
  <Types>...</Types>
</SelectionSet>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="aaf6c-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="aaf6c-106">Attributes and Elements</span></span>

<span data-ttu-id="aaf6c-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionSet` элемента.</span><span class="sxs-lookup"><span data-stu-id="aaf6c-107">The following sections describe the attributes, child elements, and the parent element of the `SelectionSet` element.</span></span> <span data-ttu-id="aaf6c-108">Каждый набор выбора должен иметь имя и должен указывать объекты .NET набора.</span><span class="sxs-lookup"><span data-stu-id="aaf6c-108">Each selection set must have a name, and it must specify the .NET objects of the set.</span></span>

### <a name="attributes"></a><span data-ttu-id="aaf6c-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="aaf6c-109">Attributes</span></span>

<span data-ttu-id="aaf6c-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="aaf6c-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="aaf6c-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="aaf6c-111">Child Elements</span></span>

|<span data-ttu-id="aaf6c-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="aaf6c-112">Element</span></span>|<span data-ttu-id="aaf6c-113">Описание</span><span class="sxs-lookup"><span data-stu-id="aaf6c-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="aaf6c-114">Элемент Name для элемента SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="aaf6c-114">Name Element for SelectionSet (Format)</span></span>](./name-element-for-selectionset-format.md)|<span data-ttu-id="aaf6c-115">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="aaf6c-115">Required element.</span></span><br /><br /> <span data-ttu-id="aaf6c-116">Задает имя, используемое для ссылки на набор выбора.</span><span class="sxs-lookup"><span data-stu-id="aaf6c-116">Specifies the name used to reference the selection set.</span></span>|
|[<span data-ttu-id="aaf6c-117">Элемент Types (Format)</span><span class="sxs-lookup"><span data-stu-id="aaf6c-117">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)|<span data-ttu-id="aaf6c-118">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="aaf6c-118">Required element.</span></span><br /><br /> <span data-ttu-id="aaf6c-119">Определяет объекты .NET, которые находятся в наборе выбора.</span><span class="sxs-lookup"><span data-stu-id="aaf6c-119">Defines the .NET objects that are in the selection set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="aaf6c-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="aaf6c-120">Parent Elements</span></span>

|<span data-ttu-id="aaf6c-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="aaf6c-121">Element</span></span>|<span data-ttu-id="aaf6c-122">Описание</span><span class="sxs-lookup"><span data-stu-id="aaf6c-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="aaf6c-123">Формат элемента Селектионсетс</span><span class="sxs-lookup"><span data-stu-id="aaf6c-123">SelectionSets Element Format</span></span>](./selectionsets-element-format.md)|<span data-ttu-id="aaf6c-124">Определяет общие наборы объектов .NET, которые могут использоваться всеми представлениями файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="aaf6c-124">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="aaf6c-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="aaf6c-125">Remarks</span></span>

<span data-ttu-id="aaf6c-126">Наборы выбора можно использовать при наличии набора связанных объектов, на которые необходимо создать ссылку, используя одно имя, например набор объектов, связанных через наследование.</span><span class="sxs-lookup"><span data-stu-id="aaf6c-126">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="aaf6c-127">При определении представлений можно указать набор объектов, используя имя набора вместо перечисления всех объектов в каждом представлении.</span><span class="sxs-lookup"><span data-stu-id="aaf6c-127">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="aaf6c-128">Стандартные наборы выбора задаются по имени при определении представлений файла форматирования или определений представлений.</span><span class="sxs-lookup"><span data-stu-id="aaf6c-128">Common selection sets are specified by their name when defining the views of the formatting file or the definitions of the views.</span></span> <span data-ttu-id="aaf6c-129">В таких случаях `SelectionSetName` дочерний элемент `ViewSelectedBy` `EntrySelectedBy` элементов и указывает используемый набор.</span><span class="sxs-lookup"><span data-stu-id="aaf6c-129">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` and `EntrySelectedBy` elements specifies the set to be used.</span></span> <span data-ttu-id="aaf6c-130">Дополнительные сведения о наборах выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="aaf6c-130">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="aaf6c-131">Пример</span><span class="sxs-lookup"><span data-stu-id="aaf6c-131">Example</span></span>

<span data-ttu-id="aaf6c-132">В следующем примере показан `SelectionSet` элемент, определяющий четыре типа .NET.</span><span class="sxs-lookup"><span data-stu-id="aaf6c-132">The following example shows a `SelectionSet` element that defines four .NET types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="aaf6c-133">См. также</span><span class="sxs-lookup"><span data-stu-id="aaf6c-133">See Also</span></span>

[<span data-ttu-id="aaf6c-134">Определение наборов выделенных фрагментов</span><span class="sxs-lookup"><span data-stu-id="aaf6c-134">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="aaf6c-135">Элемент Name набора выбора (Format)</span><span class="sxs-lookup"><span data-stu-id="aaf6c-135">Name Element of SelectionSet (Format)</span></span>](./name-element-for-selectionset-format.md)

[<span data-ttu-id="aaf6c-136">Элемент SelectionSets (формат)</span><span class="sxs-lookup"><span data-stu-id="aaf6c-136">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="aaf6c-137">Элемент Types (Format)</span><span class="sxs-lookup"><span data-stu-id="aaf6c-137">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="aaf6c-138">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="aaf6c-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
