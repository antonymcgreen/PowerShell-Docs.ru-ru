---
title: Типы элемента для SelectionSet (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4606fec0-ff31-4d36-af68-227405335ec3
caps.latest.revision: 15
ms.openlocfilehash: 0427367efa2c8a7e352d718706d1341a0c8e3621
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862380"
---
# <a name="types-element-for-selectionset-format"></a><span data-ttu-id="0e0ae-102">Элемент Types для элемента SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="0e0ae-102">Types Element for SelectionSet (Format)</span></span>

<span data-ttu-id="0e0ae-103">Определяет объекты .NET, заданных в выделении.</span><span class="sxs-lookup"><span data-stu-id="0e0ae-103">Defines the .NET objects that are in the selection set.</span></span>

<span data-ttu-id="0e0ae-104">SelectionSet элемент SelectionSets (формат) элемент (формат) для конфигурации элемента (формат) типы элемента (формат)</span><span class="sxs-lookup"><span data-stu-id="0e0ae-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Types Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0e0ae-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0e0ae-105">Syntax</span></span>

```xml
<Types>
  <TypeName>Nameof.NetType</TypeName>
</Types>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="0e0ae-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0e0ae-106">Attributes and Elements</span></span>

<span data-ttu-id="0e0ae-107">В следующих разделах атрибуты, дочерние элементы и родительский элемент `Types` элемент.</span><span class="sxs-lookup"><span data-stu-id="0e0ae-107">The following sections describe the attributes, child elements, and the parent element of the `Types` element.</span></span> <span data-ttu-id="0e0ae-108">Должен существовать по крайней мере один дочерний элемент, но не ограничено максимальное число дочерних элементов, которые могут быть добавлены.</span><span class="sxs-lookup"><span data-stu-id="0e0ae-108">There must be at least one child element, but there is no maximum limit to the number of child elements that can be added.</span></span>

### <a name="attributes"></a><span data-ttu-id="0e0ae-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0e0ae-109">Attributes</span></span>

<span data-ttu-id="0e0ae-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="0e0ae-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0e0ae-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0e0ae-111">Child Elements</span></span>

|<span data-ttu-id="0e0ae-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="0e0ae-112">Element</span></span>|<span data-ttu-id="0e0ae-113">Описание</span><span class="sxs-lookup"><span data-stu-id="0e0ae-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0e0ae-114">Элемент TypeName типов (формат)</span><span class="sxs-lookup"><span data-stu-id="0e0ae-114">TypeName Element of Types (Format)</span></span>](./typename-element-for-types-format.md)|<span data-ttu-id="0e0ae-115">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="0e0ae-115">Required element.</span></span><br /><br /> <span data-ttu-id="0e0ae-116">Указывает объект .NET, принадлежит к набору выбора.</span><span class="sxs-lookup"><span data-stu-id="0e0ae-116">Specifies the .NET object that belongs to the selection set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="0e0ae-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0e0ae-117">Parent Elements</span></span>

|<span data-ttu-id="0e0ae-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="0e0ae-118">Element</span></span>|<span data-ttu-id="0e0ae-119">Описание</span><span class="sxs-lookup"><span data-stu-id="0e0ae-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0e0ae-120">Элемент SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="0e0ae-120">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="0e0ae-121">Определяет набор объектов .NET, которые можно ссылаться по имени набора.</span><span class="sxs-lookup"><span data-stu-id="0e0ae-121">Defines a set of .NET objects that can be referenced by the name of the set.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0e0ae-122">Замечания</span><span class="sxs-lookup"><span data-stu-id="0e0ae-122">Remarks</span></span>

<span data-ttu-id="0e0ae-123">Объекты, определенные этим элементом входящие в состав набора, который может использоваться представлением, по определению представления (может иметь несколько определений представлений), или при указании условию выбора.</span><span class="sxs-lookup"><span data-stu-id="0e0ae-123">The objects defined by this element make up a selection set that can be used by a view, by a definition of a view (views can have multiple definitions), or when specifying a selection condition.</span></span>  <span data-ttu-id="0e0ae-124">Дополнительные сведения о наборах выделения, см. в разделе [определение задает объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="0e0ae-124">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="0e0ae-125">Пример</span><span class="sxs-lookup"><span data-stu-id="0e0ae-125">Example</span></span>

<span data-ttu-id="0e0ae-126">В этом примере показано `SelectionSet` элемент, который определяет четыре типа .NET.</span><span class="sxs-lookup"><span data-stu-id="0e0ae-126">This example shows a `SelectionSet` element that defines four .NET types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="0e0ae-127">См. также</span><span class="sxs-lookup"><span data-stu-id="0e0ae-127">See Also</span></span>

[<span data-ttu-id="0e0ae-128">Определение наборов объектов</span><span class="sxs-lookup"><span data-stu-id="0e0ae-128">Defining Sets of Objects</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="0e0ae-129">Элемент SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="0e0ae-129">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="0e0ae-130">Элемент TypeName типов (формат)</span><span class="sxs-lookup"><span data-stu-id="0e0ae-130">TypeName Element of Types (Format)</span></span>](./typename-element-for-types-format.md)

[<span data-ttu-id="0e0ae-131">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e0ae-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
