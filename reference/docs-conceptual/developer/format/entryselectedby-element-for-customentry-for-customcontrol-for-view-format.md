---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент EntrySelectedBy для элемента CustomEntry для элемента CustomControl для элемента View (формат)
description: Элемент EntrySelectedBy для элемента CustomEntry для элемента CustomControl для элемента View (формат)
ms.openlocfilehash: 4821f22560f35034f90d018e5a109004f331441f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655343"
---
# <a name="entryselectedby-element-for-customentry-for-customcontrol-for-view-format"></a><span data-ttu-id="bcc57-103">Элемент EntrySelectedBy для элемента CustomEntry для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="bcc57-103">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>

<span data-ttu-id="bcc57-104">Определяет типы .NET, которые используют эту настраиваемую запись, или условие, которое должно существовать для использования этой записи.</span><span class="sxs-lookup"><span data-stu-id="bcc57-104">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>

<span data-ttu-id="bcc57-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ошибка customcontrol элемент (Format) Кустоментриес для ошибка customcontrol в элементе кустоментри для представления кустоментриес для ентриселектедби для представления (формат).</span><span class="sxs-lookup"><span data-stu-id="bcc57-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bcc57-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bcc57-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bcc57-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bcc57-107">Attributes and Elements</span></span>

<span data-ttu-id="bcc57-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемента.</span><span class="sxs-lookup"><span data-stu-id="bcc57-108">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bcc57-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bcc57-109">Attributes</span></span>

<span data-ttu-id="bcc57-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="bcc57-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bcc57-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bcc57-111">Child Elements</span></span>

|<span data-ttu-id="bcc57-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="bcc57-112">Element</span></span>|<span data-ttu-id="bcc57-113">Описание</span><span class="sxs-lookup"><span data-stu-id="bcc57-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bcc57-114">Элемент Селектионкондитион для Ентриселектедби для Кустоментри (Format)</span><span class="sxs-lookup"><span data-stu-id="bcc57-114">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="bcc57-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="bcc57-115">Optional element.</span></span><br /><br /> <span data-ttu-id="bcc57-116">Определяет условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="bcc57-116">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="bcc57-117">Элемент Селектионсетнаме для Ентриселектедби для Кустоментри (Format)</span><span class="sxs-lookup"><span data-stu-id="bcc57-117">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)|<span data-ttu-id="bcc57-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="bcc57-118">Optional element.</span></span><br /><br /> <span data-ttu-id="bcc57-119">Задает набор типов .NET, использующих это определение представления элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bcc57-119">Specifies a set of .NET types that use this definition of the control view.</span></span>|
|[<span data-ttu-id="bcc57-120">Элемент TypeName для Ентриселектедби для Кустоментри (Format)</span><span class="sxs-lookup"><span data-stu-id="bcc57-120">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="bcc57-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="bcc57-121">Optional element.</span></span><br /><br /> <span data-ttu-id="bcc57-122">Указывает тип .NET, использующий это определение представления элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bcc57-122">Specifies a .NET type that uses this definition of the control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="bcc57-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bcc57-123">Parent Elements</span></span>

|<span data-ttu-id="bcc57-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="bcc57-124">Element</span></span>|<span data-ttu-id="bcc57-125">Описание</span><span class="sxs-lookup"><span data-stu-id="bcc57-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bcc57-126">Элемент Кустоментри для Кустоментриес для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="bcc57-126">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="bcc57-127">Определяет элементы управления, используемые конкретными объектами .NET.</span><span class="sxs-lookup"><span data-stu-id="bcc57-127">Defines the controls used by specific .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bcc57-128">Комментарии</span><span class="sxs-lookup"><span data-stu-id="bcc57-128">Remarks</span></span>

<span data-ttu-id="bcc57-129">Необходимо указать по крайней мере один тип, набор выбора или условие выбора для записи.</span><span class="sxs-lookup"><span data-stu-id="bcc57-129">You must specify at least one type, selection set, or selection condition for an entry.</span></span> <span data-ttu-id="bcc57-130">Максимальное количество дочерних элементов, которое можно использовать, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="bcc57-130">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="bcc57-131">Условия выбора используются для определения условия, которое должно существовать для использования записи, например, если у объекта есть определенное свойство или если определенное значение или скрипт свойства равны `true` .</span><span class="sxs-lookup"><span data-stu-id="bcc57-131">Selection conditions are used to define a condition that must exist for the entry to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="bcc57-132">Дополнительные сведения об условиях выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="bcc57-132">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="bcc57-133">Дополнительные сведения о компонентах представления пользовательского элемента управления см. в разделе [представление пользовательского элемента управления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="bcc57-133">For more information about the components of a custom control view, see [Custom Control View](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bcc57-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="bcc57-134">See Also</span></span>

[<span data-ttu-id="bcc57-135">Элемент Селектионкондитион для Ентриселектедби для Кустоментри (Format)</span><span class="sxs-lookup"><span data-stu-id="bcc57-135">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="bcc57-136">Элемент Селектионсетнаме для Ентриселектедби для Кустоментри (Format)</span><span class="sxs-lookup"><span data-stu-id="bcc57-136">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

[<span data-ttu-id="bcc57-137">Элемент TypeName для Ентриселектедби для Кустоментри (Format)</span><span class="sxs-lookup"><span data-stu-id="bcc57-137">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="bcc57-138">Элемент Кустоментри для Кустоментриес для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="bcc57-138">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="bcc57-139">Представление пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="bcc57-139">Custom Control View</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="bcc57-140">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="bcc57-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
