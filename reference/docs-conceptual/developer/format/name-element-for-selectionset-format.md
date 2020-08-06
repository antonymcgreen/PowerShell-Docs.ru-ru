---
title: Элемент Name для набора выбора (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 1fc33eeb87a6912ed6793629ab1969cd65b5f0c5
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773306"
---
# <a name="name-element-for-selectionset-format"></a><span data-ttu-id="c340e-102">Элемент Name для элемента SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="c340e-102">Name Element for SelectionSet (Format)</span></span>

<span data-ttu-id="c340e-103">Задает имя, используемое для ссылки на набор выбора.</span><span class="sxs-lookup"><span data-stu-id="c340e-103">Specifies the name used to reference the selection set.</span></span>

<span data-ttu-id="c340e-104">Элемент Configuration (Format) Селектионсетс элемент (Format) элемент набора выбора (формат) имя элемента набора выбора (Format)</span><span class="sxs-lookup"><span data-stu-id="c340e-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Name Element of SelectionSet (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c340e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c340e-105">Syntax</span></span>

```xml
<Name>Name of selection set</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c340e-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c340e-106">Attributes and Elements</span></span>

<span data-ttu-id="c340e-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Name` элемента.</span><span class="sxs-lookup"><span data-stu-id="c340e-107">The following sections describe the attributes, child elements, and parent element of the `Name` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c340e-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c340e-108">Attributes</span></span>

<span data-ttu-id="c340e-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c340e-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c340e-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c340e-110">Child Elements</span></span>

<span data-ttu-id="c340e-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c340e-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c340e-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c340e-112">Parent Elements</span></span>

|<span data-ttu-id="c340e-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="c340e-113">Element</span></span>|<span data-ttu-id="c340e-114">Описание</span><span class="sxs-lookup"><span data-stu-id="c340e-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c340e-115">Элемент SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="c340e-115">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="c340e-116">Определяет один набор объектов .NET, на который может ссылаться имя набора.</span><span class="sxs-lookup"><span data-stu-id="c340e-116">Defines a single set of .NET objects that can be referenced by the name of the set.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c340e-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="c340e-117">Text Value</span></span>

<span data-ttu-id="c340e-118">Укажите имя для ссылки на набор выбора.</span><span class="sxs-lookup"><span data-stu-id="c340e-118">Specify the name to reference the selection set.</span></span> <span data-ttu-id="c340e-119">Никаких ограничений на то, какие символы можно использовать, не существует.</span><span class="sxs-lookup"><span data-stu-id="c340e-119">There are no restrictions as to what characters can be used.</span></span>

## <a name="remarks"></a><span data-ttu-id="c340e-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="c340e-120">Remarks</span></span>

<span data-ttu-id="c340e-121">Указанное здесь имя используется в `SelectionSetName` элементе.</span><span class="sxs-lookup"><span data-stu-id="c340e-121">The name specified here is used in the `SelectionSetName` element.</span></span> <span data-ttu-id="c340e-122">Набор выбора, который может использоваться представлением, определением представления (представления могут иметь несколько определений) или при указании условия выбора.</span><span class="sxs-lookup"><span data-stu-id="c340e-122">The selection set that can be used by a view, by a definition of a view (views can have multiple definitions), or when specifying a selection condition.</span></span> <span data-ttu-id="c340e-123">Дополнительные сведения о наборах выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="c340e-123">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="c340e-124">Пример</span><span class="sxs-lookup"><span data-stu-id="c340e-124">Example</span></span>

<span data-ttu-id="c340e-125">В этом примере показан `SelectionSet` элемент, определяющий четыре типа .NET.</span><span class="sxs-lookup"><span data-stu-id="c340e-125">This example shows a `SelectionSet` element that defines four .NET types.</span></span> <span data-ttu-id="c340e-126">Имя набора выбора — "Филесистемтипес".</span><span class="sxs-lookup"><span data-stu-id="c340e-126">The name of the selection set is "FileSystemTypes".</span></span>

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

## <a name="see-also"></a><span data-ttu-id="c340e-127">См. также</span><span class="sxs-lookup"><span data-stu-id="c340e-127">See Also</span></span>

[<span data-ttu-id="c340e-128">Определение наборов выделенных фрагментов</span><span class="sxs-lookup"><span data-stu-id="c340e-128">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="c340e-129">Элемент SelectionSet (формат)</span><span class="sxs-lookup"><span data-stu-id="c340e-129">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="c340e-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="c340e-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
