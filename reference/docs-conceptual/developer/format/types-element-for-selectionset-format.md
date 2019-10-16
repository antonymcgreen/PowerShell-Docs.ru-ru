---
title: Элемент Types для набора выбора (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4606fec0-ff31-4d36-af68-227405335ec3
caps.latest.revision: 15
ms.openlocfilehash: 0427367efa2c8a7e352d718706d1341a0c8e3621
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367963"
---
# <a name="types-element-for-selectionset-format"></a><span data-ttu-id="ca6f8-102">Элемент Types для элемента SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="ca6f8-102">Types Element for SelectionSet (Format)</span></span>

<span data-ttu-id="ca6f8-103">Определяет объекты .NET, которые находятся в наборе выбора.</span><span class="sxs-lookup"><span data-stu-id="ca6f8-103">Defines the .NET objects that are in the selection set.</span></span>

<span data-ttu-id="ca6f8-104">Элемент Configuration (Format) Селектионсетс элемент (Format) элемент набора выбора (Format) Types (формат) элемент (Format)</span><span class="sxs-lookup"><span data-stu-id="ca6f8-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Types Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ca6f8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca6f8-105">Syntax</span></span>

```xml
<Types>
  <TypeName>Nameof.NetType</TypeName>
</Types>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="ca6f8-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ca6f8-106">Attributes and Elements</span></span>

<span data-ttu-id="ca6f8-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `Types`.</span><span class="sxs-lookup"><span data-stu-id="ca6f8-107">The following sections describe the attributes, child elements, and the parent element of the `Types` element.</span></span> <span data-ttu-id="ca6f8-108">Должен существовать хотя бы один дочерний элемент, но максимальное количество дочерних элементов, которое можно добавить, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="ca6f8-108">There must be at least one child element, but there is no maximum limit to the number of child elements that can be added.</span></span>

### <a name="attributes"></a><span data-ttu-id="ca6f8-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ca6f8-109">Attributes</span></span>

<span data-ttu-id="ca6f8-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="ca6f8-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ca6f8-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ca6f8-111">Child Elements</span></span>

|<span data-ttu-id="ca6f8-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="ca6f8-112">Element</span></span>|<span data-ttu-id="ca6f8-113">Описание</span><span class="sxs-lookup"><span data-stu-id="ca6f8-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ca6f8-114">Элемент TypeName типов (Format)</span><span class="sxs-lookup"><span data-stu-id="ca6f8-114">TypeName Element of Types (Format)</span></span>](./typename-element-for-types-format.md)|<span data-ttu-id="ca6f8-115">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ca6f8-115">Required element.</span></span><br /><br /> <span data-ttu-id="ca6f8-116">Указывает объект .NET, который принадлежит набору выбора.</span><span class="sxs-lookup"><span data-stu-id="ca6f8-116">Specifies the .NET object that belongs to the selection set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ca6f8-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ca6f8-117">Parent Elements</span></span>

|<span data-ttu-id="ca6f8-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="ca6f8-118">Element</span></span>|<span data-ttu-id="ca6f8-119">Описание</span><span class="sxs-lookup"><span data-stu-id="ca6f8-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ca6f8-120">Элемент набора выбора (Format)</span><span class="sxs-lookup"><span data-stu-id="ca6f8-120">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="ca6f8-121">Определяет набор объектов .NET, на которые может ссылаться имя набора.</span><span class="sxs-lookup"><span data-stu-id="ca6f8-121">Defines a set of .NET objects that can be referenced by the name of the set.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ca6f8-122">Замечания</span><span class="sxs-lookup"><span data-stu-id="ca6f8-122">Remarks</span></span>

<span data-ttu-id="ca6f8-123">Объекты, определенные этим элементом, составляют набор выбора, который может использоваться представлением, определением представления (представления могут иметь несколько определений) или при указании условия выбора.</span><span class="sxs-lookup"><span data-stu-id="ca6f8-123">The objects defined by this element make up a selection set that can be used by a view, by a definition of a view (views can have multiple definitions), or when specifying a selection condition.</span></span>  <span data-ttu-id="ca6f8-124">Дополнительные сведения о наборах выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="ca6f8-124">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="ca6f8-125">Пример</span><span class="sxs-lookup"><span data-stu-id="ca6f8-125">Example</span></span>

<span data-ttu-id="ca6f8-126">В этом примере показан элемент `SelectionSet`, определяющий четыре типа .NET.</span><span class="sxs-lookup"><span data-stu-id="ca6f8-126">This example shows a `SelectionSet` element that defines four .NET types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="ca6f8-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="ca6f8-127">See Also</span></span>

[<span data-ttu-id="ca6f8-128">Определение наборов объектов</span><span class="sxs-lookup"><span data-stu-id="ca6f8-128">Defining Sets of Objects</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="ca6f8-129">Элемент набора выбора (Format)</span><span class="sxs-lookup"><span data-stu-id="ca6f8-129">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="ca6f8-130">Элемент TypeName типов (Format)</span><span class="sxs-lookup"><span data-stu-id="ca6f8-130">TypeName Element of Types (Format)</span></span>](./typename-element-for-types-format.md)

[<span data-ttu-id="ca6f8-131">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca6f8-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)