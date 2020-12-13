---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент Name для элемента SelectionSet (формат)
description: Элемент Name для элемента SelectionSet (формат)
ms.openlocfilehash: 98c13be6ea352055231fbdb3a60f0eb508f661b8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666470"
---
# <a name="name-element-for-selectionset-format"></a><span data-ttu-id="68464-103">Элемент Name для элемента SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="68464-103">Name Element for SelectionSet (Format)</span></span>

<span data-ttu-id="68464-104">Задает имя, используемое для ссылки на набор выбора.</span><span class="sxs-lookup"><span data-stu-id="68464-104">Specifies the name used to reference the selection set.</span></span>

<span data-ttu-id="68464-105">Элемент Configuration (Format) Селектионсетс элемент (Format) элемент набора выбора (формат) имя элемента набора выбора (Format)</span><span class="sxs-lookup"><span data-stu-id="68464-105">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Name Element of SelectionSet (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="68464-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="68464-106">Syntax</span></span>

```xml
<Name>Name of selection set</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="68464-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="68464-107">Attributes and Elements</span></span>

<span data-ttu-id="68464-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Name` элемента.</span><span class="sxs-lookup"><span data-stu-id="68464-108">The following sections describe the attributes, child elements, and parent element of the `Name` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="68464-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="68464-109">Attributes</span></span>

<span data-ttu-id="68464-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="68464-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="68464-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="68464-111">Child Elements</span></span>

<span data-ttu-id="68464-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="68464-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="68464-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="68464-113">Parent Elements</span></span>

|<span data-ttu-id="68464-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="68464-114">Element</span></span>|<span data-ttu-id="68464-115">Описание</span><span class="sxs-lookup"><span data-stu-id="68464-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="68464-116">Элемент SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="68464-116">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="68464-117">Определяет один набор объектов .NET, на который может ссылаться имя набора.</span><span class="sxs-lookup"><span data-stu-id="68464-117">Defines a single set of .NET objects that can be referenced by the name of the set.</span></span>|

## <a name="text-value"></a><span data-ttu-id="68464-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="68464-118">Text Value</span></span>

<span data-ttu-id="68464-119">Укажите имя для ссылки на набор выбора.</span><span class="sxs-lookup"><span data-stu-id="68464-119">Specify the name to reference the selection set.</span></span> <span data-ttu-id="68464-120">Никаких ограничений на то, какие символы можно использовать, не существует.</span><span class="sxs-lookup"><span data-stu-id="68464-120">There are no restrictions as to what characters can be used.</span></span>

## <a name="remarks"></a><span data-ttu-id="68464-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="68464-121">Remarks</span></span>

<span data-ttu-id="68464-122">Указанное здесь имя используется в `SelectionSetName` элементе.</span><span class="sxs-lookup"><span data-stu-id="68464-122">The name specified here is used in the `SelectionSetName` element.</span></span> <span data-ttu-id="68464-123">Набор выбора, который может использоваться представлением, определением представления (представления могут иметь несколько определений) или при указании условия выбора.</span><span class="sxs-lookup"><span data-stu-id="68464-123">The selection set that can be used by a view, by a definition of a view (views can have multiple definitions), or when specifying a selection condition.</span></span> <span data-ttu-id="68464-124">Дополнительные сведения о наборах выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="68464-124">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="68464-125">Пример</span><span class="sxs-lookup"><span data-stu-id="68464-125">Example</span></span>

<span data-ttu-id="68464-126">В этом примере показан `SelectionSet` элемент, определяющий четыре типа .NET.</span><span class="sxs-lookup"><span data-stu-id="68464-126">This example shows a `SelectionSet` element that defines four .NET types.</span></span> <span data-ttu-id="68464-127">Имя набора выбора — "Филесистемтипес".</span><span class="sxs-lookup"><span data-stu-id="68464-127">The name of the selection set is "FileSystemTypes".</span></span>

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

## <a name="see-also"></a><span data-ttu-id="68464-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="68464-128">See Also</span></span>

[<span data-ttu-id="68464-129">Определение наборов выделенных фрагментов</span><span class="sxs-lookup"><span data-stu-id="68464-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="68464-130">Элемент SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="68464-130">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="68464-131">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="68464-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
