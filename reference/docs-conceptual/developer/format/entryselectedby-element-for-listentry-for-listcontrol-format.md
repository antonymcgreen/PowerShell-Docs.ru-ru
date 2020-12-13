---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент EntrySelectedBy для элемента ListEntry для элемента ListControl (формат)
description: Элемент EntrySelectedBy для элемента ListEntry для элемента ListControl (формат)
ms.openlocfilehash: 1981c8fae65f494504d6cdd9f59337d555350b07
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652292"
---
# <a name="entryselectedby-element-for-listentry-for-listcontrol-format"></a><span data-ttu-id="4c17c-103">Элемент EntrySelectedBy для элемента ListEntry для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="4c17c-103">EntrySelectedBy Element for ListEntry for ListControl (Format)</span></span>

<span data-ttu-id="4c17c-104">Определяет типы .NET, которые используют это определение представления списка или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="4c17c-104">Defines the .NET types that use this list view definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="4c17c-105">В большинстве случаев для представления списка требуется только одно определение.</span><span class="sxs-lookup"><span data-stu-id="4c17c-105">In most cases only one definition is needed for a list view.</span></span> <span data-ttu-id="4c17c-106">Однако можно указать несколько определений для представления списка, если вы хотите использовать одно и то же представление списка для отображения различных данных для разных объектов.</span><span class="sxs-lookup"><span data-stu-id="4c17c-106">However, you can provide multiple definitions for the list view if you want to use the same list view to display different data for different objects.</span></span>

<span data-ttu-id="4c17c-107">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент ListControl (Format) элемент Листентриес для ListControl (Format) Листентри для листентри для ListControl (Format) Ентриселектедби для листентри в ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="4c17c-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntry for ListControl (Format) EntrySelectedBy Element for ListEntry for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4c17c-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4c17c-108">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4c17c-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4c17c-109">Attributes and Elements</span></span>

<span data-ttu-id="4c17c-110">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемента.</span><span class="sxs-lookup"><span data-stu-id="4c17c-110">The following sections describe the attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4c17c-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4c17c-111">Attributes</span></span>

<span data-ttu-id="4c17c-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4c17c-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4c17c-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4c17c-113">Child Elements</span></span>

|<span data-ttu-id="4c17c-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="4c17c-114">Element</span></span>|<span data-ttu-id="4c17c-115">Описание</span><span class="sxs-lookup"><span data-stu-id="4c17c-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4c17c-116">Элемент Селектионкондитион для Ентриселектедби для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="4c17c-116">SelectionCondition Element for EntrySelectedBy for ListControl  (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="4c17c-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4c17c-117">Optional element.</span></span><br /><br /> <span data-ttu-id="4c17c-118">Определяет условие, которое должно существовать, чтобы использовать это определение представления списка.</span><span class="sxs-lookup"><span data-stu-id="4c17c-118">Defines the condition that must exist for this list view definition to be used.</span></span>|
|[<span data-ttu-id="4c17c-119">Элемент SelectionSetName для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="4c17c-119">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="4c17c-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4c17c-120">Optional element.</span></span><br /><br /> <span data-ttu-id="4c17c-121">Задает набор типов .NET, использующих это определение представления списка.</span><span class="sxs-lookup"><span data-stu-id="4c17c-121">Specifies a set of .NET types that use this list view definition.</span></span>|
|[<span data-ttu-id="4c17c-122">Элемент TypeName для элемента EntrySelectedBy для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="4c17c-122">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>](./typename-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="4c17c-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4c17c-123">Optional element.</span></span><br /><br /> <span data-ttu-id="4c17c-124">Указывает тип .NET, использующий это определение представления списка.</span><span class="sxs-lookup"><span data-stu-id="4c17c-124">Specifies a .NET type that uses this list view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4c17c-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4c17c-125">Parent Elements</span></span>

|<span data-ttu-id="4c17c-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="4c17c-126">Element</span></span>|<span data-ttu-id="4c17c-127">Описание</span><span class="sxs-lookup"><span data-stu-id="4c17c-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4c17c-128">Элемент ListEntry для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="4c17c-128">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="4c17c-129">Определяет, как отображаются строки списка.</span><span class="sxs-lookup"><span data-stu-id="4c17c-129">Defines how the rows of the list are displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4c17c-130">Комментарии</span><span class="sxs-lookup"><span data-stu-id="4c17c-130">Remarks</span></span>

<span data-ttu-id="4c17c-131">Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения представления списка.</span><span class="sxs-lookup"><span data-stu-id="4c17c-131">You must specify at least one type, selection set, or selection condition for a list view definition.</span></span> <span data-ttu-id="4c17c-132">Максимальное количество дочерних элементов, которое можно использовать, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="4c17c-132">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="4c17c-133">Условия выбора используются для определения условия, которое должно существовать, чтобы использовать определение, например, если объект имеет определенное свойство или значение конкретного свойства или скрипта равно `true` .</span><span class="sxs-lookup"><span data-stu-id="4c17c-133">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="4c17c-134">Дополнительные сведения об условиях выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="4c17c-134">For more information about selection conditions, see [Defining Conditions for when Data is displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="4c17c-135">Дополнительные сведения о компонентах представления списка см. [в разделе Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="4c17c-135">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="4c17c-136">Пример</span><span class="sxs-lookup"><span data-stu-id="4c17c-136">Example</span></span>

<span data-ttu-id="4c17c-137">В следующем примере показано, как определить объекты для представления списка с помощью имени типа .NET.</span><span class="sxs-lookup"><span data-stu-id="4c17c-137">The following example shows how to define the objects for a list view using their .NET type name.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>NameofDotNetType</TypeName>>
  </EntrySelectedBy>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="4c17c-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="4c17c-138">See Also</span></span>

[<span data-ttu-id="4c17c-139">Элемент ListEntry для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="4c17c-139">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="4c17c-140">Элемент SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="4c17c-140">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="4c17c-141">Элемент SelectionSetName для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="4c17c-141">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="4c17c-142">Элемент TypeName для элемента EntrySelectedBy для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="4c17c-142">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>](./typename-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="4c17c-143">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="4c17c-143">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="4c17c-144">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="4c17c-144">Defining Conditions for when Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="4c17c-145">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c17c-145">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
