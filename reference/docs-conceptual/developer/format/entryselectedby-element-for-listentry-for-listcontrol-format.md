---
title: Элемент Ентриселектедби для Листентри для ListControl (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: d6ab1c08dd353da74d1a7d27c569d2fa86e083c3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774122"
---
# <a name="entryselectedby-element-for-listentry-for-listcontrol-format"></a><span data-ttu-id="5cb69-102">Элемент EntrySelectedBy для элемента ListEntry для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="5cb69-102">EntrySelectedBy Element for ListEntry for ListControl (Format)</span></span>

<span data-ttu-id="5cb69-103">Определяет типы .NET, которые используют это определение представления списка или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="5cb69-103">Defines the .NET types that use this list view definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="5cb69-104">В большинстве случаев для представления списка требуется только одно определение.</span><span class="sxs-lookup"><span data-stu-id="5cb69-104">In most cases only one definition is needed for a list view.</span></span> <span data-ttu-id="5cb69-105">Однако можно указать несколько определений для представления списка, если вы хотите использовать одно и то же представление списка для отображения различных данных для разных объектов.</span><span class="sxs-lookup"><span data-stu-id="5cb69-105">However, you can provide multiple definitions for the list view if you want to use the same list view to display different data for different objects.</span></span>

<span data-ttu-id="5cb69-106">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент ListControl (Format) элемент Листентриес для ListControl (Format) Листентри для листентри для ListControl (Format) Ентриселектедби для листентри в ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="5cb69-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntry for ListControl (Format) EntrySelectedBy Element for ListEntry for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5cb69-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5cb69-107">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5cb69-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5cb69-108">Attributes and Elements</span></span>

<span data-ttu-id="5cb69-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемента.</span><span class="sxs-lookup"><span data-stu-id="5cb69-109">The following sections describe the attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5cb69-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5cb69-110">Attributes</span></span>

<span data-ttu-id="5cb69-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5cb69-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5cb69-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5cb69-112">Child Elements</span></span>

|<span data-ttu-id="5cb69-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="5cb69-113">Element</span></span>|<span data-ttu-id="5cb69-114">Описание</span><span class="sxs-lookup"><span data-stu-id="5cb69-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5cb69-115">Элемент Селектионкондитион для Ентриселектедби для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="5cb69-115">SelectionCondition Element for EntrySelectedBy for ListControl  (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="5cb69-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="5cb69-116">Optional element.</span></span><br /><br /> <span data-ttu-id="5cb69-117">Определяет условие, которое должно существовать, чтобы использовать это определение представления списка.</span><span class="sxs-lookup"><span data-stu-id="5cb69-117">Defines the condition that must exist for this list view definition to be used.</span></span>|
|[<span data-ttu-id="5cb69-118">Элемент SelectionSetName для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="5cb69-118">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="5cb69-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="5cb69-119">Optional element.</span></span><br /><br /> <span data-ttu-id="5cb69-120">Задает набор типов .NET, использующих это определение представления списка.</span><span class="sxs-lookup"><span data-stu-id="5cb69-120">Specifies a set of .NET types that use this list view definition.</span></span>|
|[<span data-ttu-id="5cb69-121">Элемент TypeName для элемента EntrySelectedBy для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="5cb69-121">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>](./typename-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="5cb69-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="5cb69-122">Optional element.</span></span><br /><br /> <span data-ttu-id="5cb69-123">Указывает тип .NET, использующий это определение представления списка.</span><span class="sxs-lookup"><span data-stu-id="5cb69-123">Specifies a .NET type that uses this list view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5cb69-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5cb69-124">Parent Elements</span></span>

|<span data-ttu-id="5cb69-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="5cb69-125">Element</span></span>|<span data-ttu-id="5cb69-126">Описание</span><span class="sxs-lookup"><span data-stu-id="5cb69-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5cb69-127">Элемент ListEntry для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="5cb69-127">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="5cb69-128">Определяет, как отображаются строки списка.</span><span class="sxs-lookup"><span data-stu-id="5cb69-128">Defines how the rows of the list are displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5cb69-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="5cb69-129">Remarks</span></span>

<span data-ttu-id="5cb69-130">Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения представления списка.</span><span class="sxs-lookup"><span data-stu-id="5cb69-130">You must specify at least one type, selection set, or selection condition for a list view definition.</span></span> <span data-ttu-id="5cb69-131">Максимальное количество дочерних элементов, которое можно использовать, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="5cb69-131">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="5cb69-132">Условия выбора используются для определения условия, которое должно существовать, чтобы использовать определение, например, если объект имеет определенное свойство или значение конкретного свойства или скрипта равно `true` .</span><span class="sxs-lookup"><span data-stu-id="5cb69-132">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="5cb69-133">Дополнительные сведения об условиях выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="5cb69-133">For more information about selection conditions, see [Defining Conditions for when Data is displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="5cb69-134">Дополнительные сведения о компонентах представления списка см. [в разделе Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="5cb69-134">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="5cb69-135">Пример</span><span class="sxs-lookup"><span data-stu-id="5cb69-135">Example</span></span>

<span data-ttu-id="5cb69-136">В следующем примере показано, как определить объекты для представления списка с помощью имени типа .NET.</span><span class="sxs-lookup"><span data-stu-id="5cb69-136">The following example shows how to define the objects for a list view using their .NET type name.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>NameofDotNetType</TypeName>>
  </EntrySelectedBy>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="5cb69-137">См. также</span><span class="sxs-lookup"><span data-stu-id="5cb69-137">See Also</span></span>

[<span data-ttu-id="5cb69-138">Элемент ListEntry для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="5cb69-138">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="5cb69-139">Элемент SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="5cb69-139">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="5cb69-140">Элемент SelectionSetName для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="5cb69-140">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="5cb69-141">Элемент TypeName для элемента EntrySelectedBy для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="5cb69-141">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>](./typename-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="5cb69-142">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="5cb69-142">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="5cb69-143">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="5cb69-143">Defining Conditions for when Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="5cb69-144">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="5cb69-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
