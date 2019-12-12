---
title: Элемент Селектионсетс (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebbac73a-1c99-4388-9f47-703cd024dc6d
caps.latest.revision: 18
ms.openlocfilehash: a9356635d60d5f8c5d4dec4ec8b7d0aea2b037dd
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361873"
---
# <a name="selectionsets-element-format"></a><span data-ttu-id="18405-102">Элемент SelectionSets (формат)</span><span class="sxs-lookup"><span data-stu-id="18405-102">SelectionSets Element (Format)</span></span>

<span data-ttu-id="18405-103">Определяет общие наборы объектов .NET, которые могут использоваться всеми представлениями файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="18405-103">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span> <span data-ttu-id="18405-104">Представления и элементы управления файла форматирования могут ссылаться на полный набор объектов, используя только имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="18405-104">The views and controls of the formatting file can reference the complete set of objects by using only the name of the selection set.</span></span>

<span data-ttu-id="18405-105">Формат элемента Селектионсетс элемента конфигурации</span><span class="sxs-lookup"><span data-stu-id="18405-105">Configuration Element SelectionSets Element Format</span></span>

## <a name="syntax"></a><span data-ttu-id="18405-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18405-106">Syntax</span></span>

```xml
<SelectionSets>
  <SelectionSet>...</SelectionSet>
</SelectionSets>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="18405-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="18405-107">Attributes and Elements</span></span>

<span data-ttu-id="18405-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `SelectionSets`.</span><span class="sxs-lookup"><span data-stu-id="18405-108">The following sections describe the attributes, child elements, and parent element of the `SelectionSets` element.</span></span> <span data-ttu-id="18405-109">Каждый дочерний элемент определяет набор объектов, на которые может ссылаться имя набора.</span><span class="sxs-lookup"><span data-stu-id="18405-109">Each child element defines a set of objects that can be referenced by the name of the set.</span></span> <span data-ttu-id="18405-110">Порядок дочерних элементов не важен.</span><span class="sxs-lookup"><span data-stu-id="18405-110">The order of the child elements is not significant.</span></span>

### <a name="attributes"></a><span data-ttu-id="18405-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="18405-111">Attributes</span></span>

<span data-ttu-id="18405-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="18405-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="18405-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="18405-113">Child Elements</span></span>

|<span data-ttu-id="18405-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="18405-114">Element</span></span>|<span data-ttu-id="18405-115">Описание</span><span class="sxs-lookup"><span data-stu-id="18405-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="18405-116">Элемент набора выбора (Format)</span><span class="sxs-lookup"><span data-stu-id="18405-116">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)|<span data-ttu-id="18405-117">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="18405-117">Required element.</span></span><br /><br /> <span data-ttu-id="18405-118">Определяет один набор объектов .NET, на который может ссылаться имя набора.</span><span class="sxs-lookup"><span data-stu-id="18405-118">Defines a single set of .NET objects that can be referenced by the name of the set.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="18405-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="18405-119">Parent Elements</span></span>

|<span data-ttu-id="18405-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="18405-120">Element</span></span>|<span data-ttu-id="18405-121">Описание</span><span class="sxs-lookup"><span data-stu-id="18405-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="18405-122">Элемент Configuration</span><span class="sxs-lookup"><span data-stu-id="18405-122">Configuration Element</span></span>](./configuration-element-format.md)|<span data-ttu-id="18405-123">Представляет элемент верхнего уровня файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="18405-123">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="18405-124">Замечания</span><span class="sxs-lookup"><span data-stu-id="18405-124">Remarks</span></span>

<span data-ttu-id="18405-125">Наборы выбора можно использовать при наличии набора связанных объектов, на которые необходимо создать ссылку, используя одно имя, например набор объектов, связанных через наследование.</span><span class="sxs-lookup"><span data-stu-id="18405-125">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="18405-126">При определении представлений можно указать набор объектов, используя имя набора вместо перечисления всех объектов в каждом представлении.</span><span class="sxs-lookup"><span data-stu-id="18405-126">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="18405-127">Стандартные наборы выбора задаются по имени при определении представлений файла форматирования или определений представлений.</span><span class="sxs-lookup"><span data-stu-id="18405-127">Common selection sets are specified by their name when defining the views of the formatting file or the definitions of the views.</span></span> <span data-ttu-id="18405-128">В таких случаях `SelectionSetName` дочерний элемент элементов `ViewSelectedBy` и `EntrySelectedBy` задает используемый набор.</span><span class="sxs-lookup"><span data-stu-id="18405-128">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` and `EntrySelectedBy` elements specifies the set to be used.</span></span> <span data-ttu-id="18405-129">Дополнительные сведения о наборах выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="18405-129">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="18405-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="18405-130">See Also</span></span>

[<span data-ttu-id="18405-131">Элемент Configuration</span><span class="sxs-lookup"><span data-stu-id="18405-131">Configuration Element</span></span>](./configuration-element-format.md)

[<span data-ttu-id="18405-132">Определение наборов выбора</span><span class="sxs-lookup"><span data-stu-id="18405-132">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="18405-133">Элемент набора выбора (Format)</span><span class="sxs-lookup"><span data-stu-id="18405-133">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="18405-134">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="18405-134">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
