---
title: Элемент Ентриселектедби для Кустоментри для ошибка customcontrol для представления (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7828b45b-eabf-4432-b127-131b4ef0c800
caps.latest.revision: 8
ms.openlocfilehash: e7176f9f6ef67116ea7c07a46797fb0ba84f915d
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368783"
---
# <a name="entryselectedby-element-for-customentry-for-customcontrol-for-view-format"></a><span data-ttu-id="89409-102">Элемент EntrySelectedBy для элемента CustomEntry для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="89409-102">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>

<span data-ttu-id="89409-103">Определяет типы .NET, которые используют эту настраиваемую запись, или условие, которое должно существовать для использования этой записи.</span><span class="sxs-lookup"><span data-stu-id="89409-103">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>

<span data-ttu-id="89409-104">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ошибка customcontrol элемент (Format) Кустоментриес для ошибка customcontrol для элемента представления (Format) Кустоментри для Кустоментриес для представления (Format) Ентриселектедби Элемент для Кустоментри представления (Format)</span><span class="sxs-lookup"><span data-stu-id="89409-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="89409-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89409-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="89409-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="89409-106">Attributes and Elements</span></span>

<span data-ttu-id="89409-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `EntrySelectedBy`.</span><span class="sxs-lookup"><span data-stu-id="89409-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="89409-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="89409-108">Attributes</span></span>

<span data-ttu-id="89409-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="89409-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="89409-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="89409-110">Child Elements</span></span>

|<span data-ttu-id="89409-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="89409-111">Element</span></span>|<span data-ttu-id="89409-112">Описание</span><span class="sxs-lookup"><span data-stu-id="89409-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="89409-113">Элемент Селектионкондитион для Ентриселектедби для Кустоментри (Format)</span><span class="sxs-lookup"><span data-stu-id="89409-113">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="89409-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="89409-114">Optional element.</span></span><br /><br /> <span data-ttu-id="89409-115">Определяет условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="89409-115">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="89409-116">Элемент Селектионсетнаме для Ентриселектедби для Кустоментри (Format)</span><span class="sxs-lookup"><span data-stu-id="89409-116">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)|<span data-ttu-id="89409-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="89409-117">Optional element.</span></span><br /><br /> <span data-ttu-id="89409-118">Задает набор типов .NET, использующих это определение представления элемента управления.</span><span class="sxs-lookup"><span data-stu-id="89409-118">Specifies a set of .NET types that use this definition of the control view.</span></span>|
|[<span data-ttu-id="89409-119">Элемент TypeName для Ентриселектедби для Кустоментри (Format)</span><span class="sxs-lookup"><span data-stu-id="89409-119">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="89409-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="89409-120">Optional element.</span></span><br /><br /> <span data-ttu-id="89409-121">Указывает тип .NET, использующий это определение представления элемента управления.</span><span class="sxs-lookup"><span data-stu-id="89409-121">Specifies a .NET type that uses this definition of the control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="89409-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="89409-122">Parent Elements</span></span>

|<span data-ttu-id="89409-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="89409-123">Element</span></span>|<span data-ttu-id="89409-124">Описание</span><span class="sxs-lookup"><span data-stu-id="89409-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="89409-125">Элемент Кустоментри для Кустоментриес для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="89409-125">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="89409-126">Определяет элементы управления, используемые конкретными объектами .NET.</span><span class="sxs-lookup"><span data-stu-id="89409-126">Defines the controls used by specific .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="89409-127">Замечания</span><span class="sxs-lookup"><span data-stu-id="89409-127">Remarks</span></span>

<span data-ttu-id="89409-128">Необходимо указать по крайней мере один тип, набор выбора или условие выбора для записи.</span><span class="sxs-lookup"><span data-stu-id="89409-128">You must specify at least one type, selection set, or selection condition for an entry.</span></span> <span data-ttu-id="89409-129">Максимальное количество дочерних элементов, которое можно использовать, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="89409-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="89409-130">Условия выбора используются для определения условия, которое должно существовать для использования записи, например, если у объекта есть определенное свойство или если определенное значение или скрипт свойства имеют `true`.</span><span class="sxs-lookup"><span data-stu-id="89409-130">Selection conditions are used to define a condition that must exist for the entry to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="89409-131">Дополнительные сведения об условиях выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="89409-131">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="89409-132">Дополнительные сведения о компонентах представления пользовательского элемента управления см. в разделе [представление пользовательского элемента управления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="89409-132">For more information about the components of a custom control view, see [Custom Control View](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="89409-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="89409-133">See Also</span></span>

[<span data-ttu-id="89409-134">Элемент Селектионкондитион для Ентриселектедби для Кустоментри (Format)</span><span class="sxs-lookup"><span data-stu-id="89409-134">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="89409-135">Элемент Селектионсетнаме для Ентриселектедби для Кустоментри (Format)</span><span class="sxs-lookup"><span data-stu-id="89409-135">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

[<span data-ttu-id="89409-136">Элемент TypeName для Ентриселектедби для Кустоментри (Format)</span><span class="sxs-lookup"><span data-stu-id="89409-136">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="89409-137">Элемент Кустоментри для Кустоментриес для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="89409-137">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="89409-138">Представление пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="89409-138">Custom Control View</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="89409-139">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="89409-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
