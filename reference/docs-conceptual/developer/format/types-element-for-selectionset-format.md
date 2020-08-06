---
title: Элемент Types для набора выбора (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 9978daefb3e97ab131774ca4dff633dde6b4dfbf
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772524"
---
# <a name="types-element-for-selectionset-format"></a><span data-ttu-id="b69ba-102">Элемент Types для элемента SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="b69ba-102">Types Element for SelectionSet (Format)</span></span>

<span data-ttu-id="b69ba-103">Определяет объекты .NET, которые находятся в наборе выбора.</span><span class="sxs-lookup"><span data-stu-id="b69ba-103">Defines the .NET objects that are in the selection set.</span></span>

<span data-ttu-id="b69ba-104">Элемент Configuration (Format) Селектионсетс элемент (Format) элемент набора выбора (Format) Types (формат) элемент (Format)</span><span class="sxs-lookup"><span data-stu-id="b69ba-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Types Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b69ba-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b69ba-105">Syntax</span></span>

```xml
<Types>
  <TypeName>Nameof.NetType</TypeName>
</Types>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="b69ba-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b69ba-106">Attributes and Elements</span></span>

<span data-ttu-id="b69ba-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Types` элемента.</span><span class="sxs-lookup"><span data-stu-id="b69ba-107">The following sections describe the attributes, child elements, and the parent element of the `Types` element.</span></span> <span data-ttu-id="b69ba-108">Должен существовать хотя бы один дочерний элемент, но максимальное количество дочерних элементов, которое можно добавить, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="b69ba-108">There must be at least one child element, but there is no maximum limit to the number of child elements that can be added.</span></span>

### <a name="attributes"></a><span data-ttu-id="b69ba-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b69ba-109">Attributes</span></span>

<span data-ttu-id="b69ba-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b69ba-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b69ba-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b69ba-111">Child Elements</span></span>

|<span data-ttu-id="b69ba-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="b69ba-112">Element</span></span>|<span data-ttu-id="b69ba-113">Описание</span><span class="sxs-lookup"><span data-stu-id="b69ba-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b69ba-114">Элемент TypeName типов (Format)</span><span class="sxs-lookup"><span data-stu-id="b69ba-114">TypeName Element of Types (Format)</span></span>](./typename-element-for-types-format.md)|<span data-ttu-id="b69ba-115">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="b69ba-115">Required element.</span></span><br /><br /> <span data-ttu-id="b69ba-116">Указывает объект .NET, который принадлежит набору выбора.</span><span class="sxs-lookup"><span data-stu-id="b69ba-116">Specifies the .NET object that belongs to the selection set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b69ba-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b69ba-117">Parent Elements</span></span>

|<span data-ttu-id="b69ba-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="b69ba-118">Element</span></span>|<span data-ttu-id="b69ba-119">Описание</span><span class="sxs-lookup"><span data-stu-id="b69ba-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b69ba-120">Элемент SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="b69ba-120">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="b69ba-121">Определяет набор объектов .NET, на которые может ссылаться имя набора.</span><span class="sxs-lookup"><span data-stu-id="b69ba-121">Defines a set of .NET objects that can be referenced by the name of the set.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b69ba-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="b69ba-122">Remarks</span></span>

<span data-ttu-id="b69ba-123">Объекты, определенные этим элементом, составляют набор выбора, который может использоваться представлением, определением представления (представления могут иметь несколько определений) или при указании условия выбора.</span><span class="sxs-lookup"><span data-stu-id="b69ba-123">The objects defined by this element make up a selection set that can be used by a view, by a definition of a view (views can have multiple definitions), or when specifying a selection condition.</span></span>  <span data-ttu-id="b69ba-124">Дополнительные сведения о наборах выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="b69ba-124">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="b69ba-125">Пример</span><span class="sxs-lookup"><span data-stu-id="b69ba-125">Example</span></span>

<span data-ttu-id="b69ba-126">В этом примере показан `SelectionSet` элемент, определяющий четыре типа .NET.</span><span class="sxs-lookup"><span data-stu-id="b69ba-126">This example shows a `SelectionSet` element that defines four .NET types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b69ba-127">См. также</span><span class="sxs-lookup"><span data-stu-id="b69ba-127">See Also</span></span>

[<span data-ttu-id="b69ba-128">Определение наборов объектов</span><span class="sxs-lookup"><span data-stu-id="b69ba-128">Defining Sets of Objects</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="b69ba-129">Элемент SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="b69ba-129">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="b69ba-130">Элемент TypeName типов (Format)</span><span class="sxs-lookup"><span data-stu-id="b69ba-130">TypeName Element of Types (Format)</span></span>](./typename-element-for-types-format.md)

[<span data-ttu-id="b69ba-131">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="b69ba-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
