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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066198"
---
# <a name="entryselectedby-element-for-listentry-for-listcontrol-format"></a><span data-ttu-id="09c47-102">Элемент EntrySelectedBy для элемента ListEntry для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="09c47-102">EntrySelectedBy Element for ListEntry for ListControl (Format)</span></span>

<span data-ttu-id="09c47-103">Определяет типы .NET, использующих это определение представления списка или условие, которое должен существовать для данного определения для использования.</span><span class="sxs-lookup"><span data-stu-id="09c47-103">Defines the .NET types that use this list view definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="09c47-104">В большинстве случаев требуется только одно определение представления списка.</span><span class="sxs-lookup"><span data-stu-id="09c47-104">In most cases only one definition is needed for a list view.</span></span> <span data-ttu-id="09c47-105">Тем не менее можно предоставить несколько определений для представления списка, если вы хотите использовать же представлении списка для отображения разных данных для различных объектов.</span><span class="sxs-lookup"><span data-stu-id="09c47-105">However, you can provide multiple definitions for the list view if you want to use the same list view to display different data for different objects.</span></span>

<span data-ttu-id="09c47-106">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемента ListControl (формат) ListEntries элемента конфигурации для элемента ListControl (формат) ListEntry ListEntry для EntrySelectedBy элемента ListControl (формат) ListEntry для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="09c47-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntry for ListControl (Format) EntrySelectedBy Element for ListEntry for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="09c47-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="09c47-107">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="09c47-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="09c47-108">Attributes and Elements</span></span>

<span data-ttu-id="09c47-109">В следующих разделах атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемент.</span><span class="sxs-lookup"><span data-stu-id="09c47-109">The following sections describe the attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="09c47-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="09c47-110">Attributes</span></span>

<span data-ttu-id="09c47-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="09c47-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="09c47-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="09c47-112">Child Elements</span></span>

|<span data-ttu-id="09c47-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="09c47-113">Element</span></span>|<span data-ttu-id="09c47-114">Описание</span><span class="sxs-lookup"><span data-stu-id="09c47-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="09c47-115">Элемент SelectionCondition для EntrySelectedBy для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="09c47-115">SelectionCondition Element for EntrySelectedBy for ListControl  (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="09c47-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="09c47-116">Optional element.</span></span><br /><br /> <span data-ttu-id="09c47-117">Определяет условие, которое должен существовать для данного определения представления списка для использования.</span><span class="sxs-lookup"><span data-stu-id="09c47-117">Defines the condition that must exist for this list view definition to be used.</span></span>|
|[<span data-ttu-id="09c47-118">Элемент SelectionSetName для EntrySelectedBy для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="09c47-118">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="09c47-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="09c47-119">Optional element.</span></span><br /><br /> <span data-ttu-id="09c47-120">Задает набор типов .NET, которые используют это определение представления списка.</span><span class="sxs-lookup"><span data-stu-id="09c47-120">Specifies a set of .NET types that use this list view definition.</span></span>|
|[<span data-ttu-id="09c47-121">TypeName-элемент для EntrySelectedBy для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="09c47-121">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>](./typename-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="09c47-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="09c47-122">Optional element.</span></span><br /><br /> <span data-ttu-id="09c47-123">Указывает тип .NET, который использует это определение представления списка.</span><span class="sxs-lookup"><span data-stu-id="09c47-123">Specifies a .NET type that uses this list view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="09c47-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="09c47-124">Parent Elements</span></span>

|<span data-ttu-id="09c47-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="09c47-125">Element</span></span>|<span data-ttu-id="09c47-126">Описание</span><span class="sxs-lookup"><span data-stu-id="09c47-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="09c47-127">Элемент ListEntry для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="09c47-127">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="09c47-128">Определяет способ отображения списка строк.</span><span class="sxs-lookup"><span data-stu-id="09c47-128">Defines how the rows of the list are displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="09c47-129">Замечания</span><span class="sxs-lookup"><span data-stu-id="09c47-129">Remarks</span></span>

<span data-ttu-id="09c47-130">Необходимо указать по крайней мере один тип, выбора или условию выбора определения представления списка.</span><span class="sxs-lookup"><span data-stu-id="09c47-130">You must specify at least one type, selection set, or selection condition for a list view definition.</span></span> <span data-ttu-id="09c47-131">Не ограничено максимальное число дочерних элементов, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="09c47-131">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="09c47-132">Выбор условия используются для определения условия, которое должен существовать для определения для использования, например, если объект имеет определенное свойство или значение конкретного свойства или скрипт принимает значение `true`.</span><span class="sxs-lookup"><span data-stu-id="09c47-132">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="09c47-133">Дополнительные сведения об условиях выделения, см. в разделе [определение условий при отображении данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="09c47-133">For more information about selection conditions, see [Defining Conditions for when Data is displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="09c47-134">Дополнительные сведения о компонентах представления списка, см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="09c47-134">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="09c47-135">Пример</span><span class="sxs-lookup"><span data-stu-id="09c47-135">Example</span></span>

<span data-ttu-id="09c47-136">В следующем примере показано, как для определения объектов для представления списка, используя их имя типа .NET.</span><span class="sxs-lookup"><span data-stu-id="09c47-136">The following example shows how to define the objects for a list view using their .NET type name.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>NameofDotNetType</TypeName>>
  </EntrySelectedBy>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="09c47-137">См. также</span><span class="sxs-lookup"><span data-stu-id="09c47-137">See Also</span></span>

[<span data-ttu-id="09c47-138">Элемент ListEntry для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="09c47-138">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="09c47-139">Элемент SelectionCondition для EntrySelectedBy для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="09c47-139">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="09c47-140">Элемент SelectionSetName для EntrySelectedBy для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="09c47-140">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="09c47-141">TypeName-элемент для EntrySelectedBy для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="09c47-141">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>](./typename-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="09c47-142">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="09c47-142">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="09c47-143">Определение условия при отображении данных</span><span class="sxs-lookup"><span data-stu-id="09c47-143">Defining Conditions for when Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="09c47-144">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="09c47-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
