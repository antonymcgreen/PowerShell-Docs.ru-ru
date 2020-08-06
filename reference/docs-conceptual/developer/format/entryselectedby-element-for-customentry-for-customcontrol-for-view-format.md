---
title: Элемент Ентриселектедби для Кустоментри для ошибка customcontrol для представления (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 4d4900cefb0d499397fc9dff7e037ce0a541f72f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783693"
---
# <a name="entryselectedby-element-for-customentry-for-customcontrol-for-view-format"></a><span data-ttu-id="bbf04-102">Элемент EntrySelectedBy для элемента CustomEntry для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="bbf04-102">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>

<span data-ttu-id="bbf04-103">Определяет типы .NET, которые используют эту настраиваемую запись, или условие, которое должно существовать для использования этой записи.</span><span class="sxs-lookup"><span data-stu-id="bbf04-103">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>

<span data-ttu-id="bbf04-104">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ошибка customcontrol элемент (Format) Кустоментриес для ошибка customcontrol в элементе кустоментри для представления кустоментриес для ентриселектедби для представления (формат).</span><span class="sxs-lookup"><span data-stu-id="bbf04-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bbf04-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bbf04-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bbf04-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bbf04-106">Attributes and Elements</span></span>

<span data-ttu-id="bbf04-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемента.</span><span class="sxs-lookup"><span data-stu-id="bbf04-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bbf04-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bbf04-108">Attributes</span></span>

<span data-ttu-id="bbf04-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="bbf04-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bbf04-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bbf04-110">Child Elements</span></span>

|<span data-ttu-id="bbf04-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="bbf04-111">Element</span></span>|<span data-ttu-id="bbf04-112">Описание</span><span class="sxs-lookup"><span data-stu-id="bbf04-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bbf04-113">Элемент Селектионкондитион для Ентриселектедби для Кустоментри (Format)</span><span class="sxs-lookup"><span data-stu-id="bbf04-113">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="bbf04-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="bbf04-114">Optional element.</span></span><br /><br /> <span data-ttu-id="bbf04-115">Определяет условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="bbf04-115">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="bbf04-116">Элемент Селектионсетнаме для Ентриселектедби для Кустоментри (Format)</span><span class="sxs-lookup"><span data-stu-id="bbf04-116">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)|<span data-ttu-id="bbf04-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="bbf04-117">Optional element.</span></span><br /><br /> <span data-ttu-id="bbf04-118">Задает набор типов .NET, использующих это определение представления элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bbf04-118">Specifies a set of .NET types that use this definition of the control view.</span></span>|
|[<span data-ttu-id="bbf04-119">Элемент TypeName для Ентриселектедби для Кустоментри (Format)</span><span class="sxs-lookup"><span data-stu-id="bbf04-119">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="bbf04-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="bbf04-120">Optional element.</span></span><br /><br /> <span data-ttu-id="bbf04-121">Указывает тип .NET, использующий это определение представления элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bbf04-121">Specifies a .NET type that uses this definition of the control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="bbf04-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bbf04-122">Parent Elements</span></span>

|<span data-ttu-id="bbf04-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="bbf04-123">Element</span></span>|<span data-ttu-id="bbf04-124">Описание</span><span class="sxs-lookup"><span data-stu-id="bbf04-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bbf04-125">Элемент Кустоментри для Кустоментриес для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="bbf04-125">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="bbf04-126">Определяет элементы управления, используемые конкретными объектами .NET.</span><span class="sxs-lookup"><span data-stu-id="bbf04-126">Defines the controls used by specific .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bbf04-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="bbf04-127">Remarks</span></span>

<span data-ttu-id="bbf04-128">Необходимо указать по крайней мере один тип, набор выбора или условие выбора для записи.</span><span class="sxs-lookup"><span data-stu-id="bbf04-128">You must specify at least one type, selection set, or selection condition for an entry.</span></span> <span data-ttu-id="bbf04-129">Максимальное количество дочерних элементов, которое можно использовать, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="bbf04-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="bbf04-130">Условия выбора используются для определения условия, которое должно существовать для использования записи, например, если у объекта есть определенное свойство или если определенное значение или скрипт свойства равны `true` .</span><span class="sxs-lookup"><span data-stu-id="bbf04-130">Selection conditions are used to define a condition that must exist for the entry to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="bbf04-131">Дополнительные сведения об условиях выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="bbf04-131">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="bbf04-132">Дополнительные сведения о компонентах представления пользовательского элемента управления см. в разделе [представление пользовательского элемента управления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="bbf04-132">For more information about the components of a custom control view, see [Custom Control View](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bbf04-133">См. также</span><span class="sxs-lookup"><span data-stu-id="bbf04-133">See Also</span></span>

[<span data-ttu-id="bbf04-134">Элемент Селектионкондитион для Ентриселектедби для Кустоментри (Format)</span><span class="sxs-lookup"><span data-stu-id="bbf04-134">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="bbf04-135">Элемент Селектионсетнаме для Ентриселектедби для Кустоментри (Format)</span><span class="sxs-lookup"><span data-stu-id="bbf04-135">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

[<span data-ttu-id="bbf04-136">Элемент TypeName для Ентриселектедби для Кустоментри (Format)</span><span class="sxs-lookup"><span data-stu-id="bbf04-136">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="bbf04-137">Элемент Кустоментри для Кустоментриес для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="bbf04-137">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="bbf04-138">Представление пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="bbf04-138">Custom Control View</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="bbf04-139">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbf04-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
