---
title: Элемент EntrySelectedBy для ListEntry для ListControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f7a74e9-764d-46ce-ab8e-8b9314ce1659
caps.latest.revision: 12
ms.openlocfilehash: 442565d25f60ae8e04501f3f9ffba35d486fbc8a
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58054949"
---
# <a name="entryselectedby-element-for-listentry-for-listcontrol-format"></a><span data-ttu-id="416a9-102">Элемент EntrySelectedBy для элемента ListEntry для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="416a9-102">EntrySelectedBy Element for ListEntry for ListControl (Format)</span></span>

<span data-ttu-id="416a9-103">Определяет типы .NET, использующих это определение представления списка или условие, которое должен существовать для данного определения для использования.</span><span class="sxs-lookup"><span data-stu-id="416a9-103">Defines the .NET types that use this list view definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="416a9-104">В большинстве случаев требуется только одно определение представления списка.</span><span class="sxs-lookup"><span data-stu-id="416a9-104">In most cases only one definition is needed for a list view.</span></span> <span data-ttu-id="416a9-105">Тем не менее можно предоставить несколько определений для представления списка, если вы хотите использовать же представлении списка для отображения разных данных для различных объектов.</span><span class="sxs-lookup"><span data-stu-id="416a9-105">However, you can provide multiple definitions for the list view if you want to use the same list view to display different data for different objects.</span></span>

<span data-ttu-id="416a9-106">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемента ListControl (формат) ListEntries элемента конфигурации для элемента ListControl (формат) ListEntry ListEntry для EntrySelectedBy элемента ListControl (формат) ListEntry для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="416a9-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntry for ListControl (Format) EntrySelectedBy Element for ListEntry for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="416a9-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="416a9-107">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="416a9-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="416a9-108">Attributes and Elements</span></span>

<span data-ttu-id="416a9-109">В следующих разделах атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемент.</span><span class="sxs-lookup"><span data-stu-id="416a9-109">The following sections describe the attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="416a9-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="416a9-110">Attributes</span></span>

<span data-ttu-id="416a9-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="416a9-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="416a9-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="416a9-112">Child Elements</span></span>

|<span data-ttu-id="416a9-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="416a9-113">Element</span></span>|<span data-ttu-id="416a9-114">Описание</span><span class="sxs-lookup"><span data-stu-id="416a9-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="416a9-115">Элемент SelectionCondition для EntrySelectedBy для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="416a9-115">SelectionCondition Element for EntrySelectedBy for ListControl  (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="416a9-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="416a9-116">Optional element.</span></span><br /><br /> <span data-ttu-id="416a9-117">Определяет условие, которое должен существовать для данного определения представления списка для использования.</span><span class="sxs-lookup"><span data-stu-id="416a9-117">Defines the condition that must exist for this list view definition to be used.</span></span>|
|[<span data-ttu-id="416a9-118">Элемент SelectionSetName для EntrySelectedBy для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="416a9-118">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="416a9-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="416a9-119">Optional element.</span></span><br /><br /> <span data-ttu-id="416a9-120">Задает набор типов .NET, которые используют это определение представления списка.</span><span class="sxs-lookup"><span data-stu-id="416a9-120">Specifies a set of .NET types that use this list view definition.</span></span>|
|[<span data-ttu-id="416a9-121">TypeName-элемент для EntrySelectedBy для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="416a9-121">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>](./typename-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="416a9-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="416a9-122">Optional element.</span></span><br /><br /> <span data-ttu-id="416a9-123">Указывает тип .NET, который использует это определение представления списка.</span><span class="sxs-lookup"><span data-stu-id="416a9-123">Specifies a .NET type that uses this list view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="416a9-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="416a9-124">Parent Elements</span></span>

|<span data-ttu-id="416a9-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="416a9-125">Element</span></span>|<span data-ttu-id="416a9-126">Описание</span><span class="sxs-lookup"><span data-stu-id="416a9-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="416a9-127">Элемент ListEntry для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="416a9-127">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="416a9-128">Определяет способ отображения списка строк.</span><span class="sxs-lookup"><span data-stu-id="416a9-128">Defines how the rows of the list are displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="416a9-129">Замечания</span><span class="sxs-lookup"><span data-stu-id="416a9-129">Remarks</span></span>

<span data-ttu-id="416a9-130">Необходимо указать по крайней мере один тип, выбора или условию выбора определения представления списка.</span><span class="sxs-lookup"><span data-stu-id="416a9-130">You must specify at least one type, selection set, or selection condition for a list view definition.</span></span> <span data-ttu-id="416a9-131">Не ограничено максимальное число дочерних элементов, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="416a9-131">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="416a9-132">Выбор условия используются для определения условия, которое должен существовать для определения для использования, например, если объект имеет определенное свойство или значение конкретного свойства или скрипт принимает значение `true`.</span><span class="sxs-lookup"><span data-stu-id="416a9-132">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="416a9-133">Дополнительные сведения об условиях выделения, см. в разделе [определение условий при отображении данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="416a9-133">For more information about selection conditions, see [Defining Conditions for when Data is displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="416a9-134">Дополнительные сведения о компонентах представления списка, см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="416a9-134">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="416a9-135">Пример</span><span class="sxs-lookup"><span data-stu-id="416a9-135">Example</span></span>

<span data-ttu-id="416a9-136">В следующем примере показано, как для определения объектов для представления списка, используя их имя типа .NET.</span><span class="sxs-lookup"><span data-stu-id="416a9-136">The following example shows how to define the objects for a list view using their .NET type name.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>NameofDotNetType</TypeName>>
  </EntrySelectedBy>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="416a9-137">См. также</span><span class="sxs-lookup"><span data-stu-id="416a9-137">See Also</span></span>

[<span data-ttu-id="416a9-138">Элемент ListEntry для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="416a9-138">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="416a9-139">Элемент SelectionCondition для EntrySelectedBy для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="416a9-139">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="416a9-140">Элемент SelectionSetName для EntrySelectedBy для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="416a9-140">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="416a9-141">TypeName-элемент для EntrySelectedBy для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="416a9-141">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>](./typename-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="416a9-142">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="416a9-142">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="416a9-143">Определение условия при отображении данных</span><span class="sxs-lookup"><span data-stu-id="416a9-143">Defining Conditions for when Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="416a9-144">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="416a9-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
