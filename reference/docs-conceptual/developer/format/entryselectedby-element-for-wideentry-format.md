---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент EntrySelectedBy для элемента WideEntry (формат)
description: Элемент EntrySelectedBy для элемента WideEntry (формат)
ms.openlocfilehash: 246a1967300ab0551f376c4799deac275068308c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660238"
---
# <a name="entryselectedby-element-for-wideentry-format"></a><span data-ttu-id="a0433-103">Элемент EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="a0433-103">EntrySelectedBy Element for WideEntry (Format)</span></span>

<span data-ttu-id="a0433-104">Определяет типы .NET, которые используют это определение расширенного представления или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="a0433-104">Defines the .NET types that use this definition of the wide view or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="a0433-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="a0433-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a0433-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0433-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a0433-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a0433-107">Attributes and Elements</span></span>

<span data-ttu-id="a0433-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемента.</span><span class="sxs-lookup"><span data-stu-id="a0433-108">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a0433-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a0433-109">Attributes</span></span>

<span data-ttu-id="a0433-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a0433-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a0433-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a0433-111">Child Elements</span></span>

|<span data-ttu-id="a0433-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="a0433-112">Element</span></span>|<span data-ttu-id="a0433-113">Описание</span><span class="sxs-lookup"><span data-stu-id="a0433-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a0433-114">Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="a0433-114">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="a0433-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="a0433-115">Optional element.</span></span><br /><br /> <span data-ttu-id="a0433-116">Определяет условие, которое должно существовать для использования в этом расширенном определении представления.</span><span class="sxs-lookup"><span data-stu-id="a0433-116">Defines the condition that must exist for this wide view definition to be used.</span></span>|
|[<span data-ttu-id="a0433-117">Элемент Селектионсетнаме для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="a0433-117">SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="a0433-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="a0433-118">Optional element.</span></span><br /><br /> <span data-ttu-id="a0433-119">Указывает набор типов .NET, использующих это определение в масштабах представления.</span><span class="sxs-lookup"><span data-stu-id="a0433-119">Specifies a set of .NET types that use this wide view definition.</span></span>|
|[<span data-ttu-id="a0433-120">Элемент TypeName для элемента EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="a0433-120">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="a0433-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="a0433-121">Optional element.</span></span><br /><br /> <span data-ttu-id="a0433-122">Указывает тип .NET, использующий это определение в масштабе представления.</span><span class="sxs-lookup"><span data-stu-id="a0433-122">Specifies a .NET type that uses this wide view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a0433-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a0433-123">Parent Elements</span></span>

|<span data-ttu-id="a0433-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="a0433-124">Element</span></span>|<span data-ttu-id="a0433-125">Описание</span><span class="sxs-lookup"><span data-stu-id="a0433-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a0433-126">Элемент Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="a0433-126">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="a0433-127">Предоставляет определение расширенного представления.</span><span class="sxs-lookup"><span data-stu-id="a0433-127">Provides a definition of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a0433-128">Комментарии</span><span class="sxs-lookup"><span data-stu-id="a0433-128">Remarks</span></span>

<span data-ttu-id="a0433-129">Необходимо указать по крайней мере один тип, набор выбора или условие выбора для расширенного определения представления.</span><span class="sxs-lookup"><span data-stu-id="a0433-129">You must specify at least one type, selection set, or selection condition for a wide view definition.</span></span> <span data-ttu-id="a0433-130">Максимальное количество дочерних элементов, которое можно использовать, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="a0433-130">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="a0433-131">Условия выбора используются для определения условия, которое должно существовать для использования определения, например, если объект имеет определенное свойство или значение конкретного свойства или значения скрипта равно `true` .</span><span class="sxs-lookup"><span data-stu-id="a0433-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script value evaluates to `true`.</span></span> <span data-ttu-id="a0433-132">Дополнительные сведения об условиях выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="a0433-132">For more information about selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="a0433-133">Дополнительные сведения о других компонентах расширенного представления см. [в разделе Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="a0433-133">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a0433-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="a0433-134">See Also</span></span>

[<span data-ttu-id="a0433-135">Элемент Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="a0433-135">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="a0433-136">Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="a0433-136">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="a0433-137">Элемент Селектионсетнаме для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="a0433-137">SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="a0433-138">Элемент TypeName для элемента EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="a0433-138">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="a0433-139">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="a0433-139">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="a0433-140">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="a0433-140">Defining Conditions for Displaying Data</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="a0433-141">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0433-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
