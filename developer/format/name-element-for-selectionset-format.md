---
title: Элемент Name для SelectionSet (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 914917f7-0efc-4d1f-88bd-de714bedd98f
caps.latest.revision: 15
ms.openlocfilehash: 29dbdbd335511e4ca2706a625541554825838f23
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065161"
---
# <a name="name-element-for-selectionset-format"></a><span data-ttu-id="73669-102">Элемент Name для элемента SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="73669-102">Name Element for SelectionSet (Format)</span></span>

<span data-ttu-id="73669-103">Указывает имя, используемое для ссылки на наборе выбора.</span><span class="sxs-lookup"><span data-stu-id="73669-103">Specifies the name used to reference the selection set.</span></span>

<span data-ttu-id="73669-104">Элемент конфигурации элемент (формат) элемент SelectionSets (формат) элемент SelectionSet (формат) имя из SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="73669-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Name Element of SelectionSet (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="73669-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="73669-105">Syntax</span></span>

```xml
<Name>Name of selection set</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="73669-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="73669-106">Attributes and Elements</span></span>

<span data-ttu-id="73669-107">В следующих разделах атрибуты, дочерние элементы и родительский элемент `Name` элемент.</span><span class="sxs-lookup"><span data-stu-id="73669-107">The following sections describe the attributes, child elements, and parent element of the `Name` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="73669-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="73669-108">Attributes</span></span>

<span data-ttu-id="73669-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="73669-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="73669-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="73669-110">Child Elements</span></span>

<span data-ttu-id="73669-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="73669-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="73669-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="73669-112">Parent Elements</span></span>

|<span data-ttu-id="73669-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="73669-113">Element</span></span>|<span data-ttu-id="73669-114">Описание</span><span class="sxs-lookup"><span data-stu-id="73669-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="73669-115">Элемент SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="73669-115">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="73669-116">Определяет один набор объектов .NET, которые можно ссылаться по имени набора.</span><span class="sxs-lookup"><span data-stu-id="73669-116">Defines a single set of .NET objects that can be referenced by the name of the set.</span></span>|

## <a name="text-value"></a><span data-ttu-id="73669-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="73669-117">Text Value</span></span>

<span data-ttu-id="73669-118">Укажите имя для ссылки на наборе выбора.</span><span class="sxs-lookup"><span data-stu-id="73669-118">Specify the name to reference the selection set.</span></span> <span data-ttu-id="73669-119">Нет никаких ограничений, о том, какие символы можно использовать.</span><span class="sxs-lookup"><span data-stu-id="73669-119">There are no restrictions as to what characters can be used.</span></span>

## <a name="remarks"></a><span data-ttu-id="73669-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="73669-120">Remarks</span></span>

<span data-ttu-id="73669-121">Имя, указанное здесь используется в `SelectionSetName` элемент.</span><span class="sxs-lookup"><span data-stu-id="73669-121">The name specified here is used in the `SelectionSetName` element.</span></span> <span data-ttu-id="73669-122">Набора, который может использоваться представлением, по определению представления (может иметь несколько определений представлений), или при указании условию выбора.</span><span class="sxs-lookup"><span data-stu-id="73669-122">The selection set that can be used by a view, by a definition of a view (views can have multiple definitions), or when specifying a selection condition.</span></span> <span data-ttu-id="73669-123">Дополнительные сведения о наборах выделения, см. в разделе [определение задает объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="73669-123">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="73669-124">Пример</span><span class="sxs-lookup"><span data-stu-id="73669-124">Example</span></span>

<span data-ttu-id="73669-125">В этом примере показано `SelectionSet` элемент, который определяет четыре типа .NET.</span><span class="sxs-lookup"><span data-stu-id="73669-125">This example shows a `SelectionSet` element that defines four .NET types.</span></span> <span data-ttu-id="73669-126">Имя набора выбора является «FileSystemTypes».</span><span class="sxs-lookup"><span data-stu-id="73669-126">The name of the selection set is "FileSystemTypes".</span></span>

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

## <a name="see-also"></a><span data-ttu-id="73669-127">См. также</span><span class="sxs-lookup"><span data-stu-id="73669-127">See Also</span></span>

[<span data-ttu-id="73669-128">Определение наборов Выбор</span><span class="sxs-lookup"><span data-stu-id="73669-128">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="73669-129">Элемент SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="73669-129">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="73669-130">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="73669-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
