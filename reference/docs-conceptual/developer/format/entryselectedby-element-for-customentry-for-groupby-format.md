---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент EntrySelectedBy для элемента CustomEntry для элемента GroupBy (формат)
description: Элемент EntrySelectedBy для элемента CustomEntry для элемента GroupBy (формат)
ms.openlocfilehash: 5af4abe081ca268699d281a1b586a584107b9a83
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652351"
---
# <a name="entryselectedby-element-for-customentry-for-groupby-format"></a><span data-ttu-id="397c6-103">Элемент EntrySelectedBy для элемента CustomEntry для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="397c6-103">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>

<span data-ttu-id="397c6-104">Определяет типы .NET, которые используют это определение элемента управления или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="397c6-104">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="397c6-105">Этот элемент используется при определении того, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="397c6-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="397c6-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент GroupBy для элемента представления (Format) ошибка customcontrol для элемента GroupBy (Format) Кустоментриес для ошибка customcontrol for GroupBy (формат) кустоментри элемент для ошибка customcontrol for GroupBy (формат) ентриселектедби для кустоментри for GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="397c6-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="397c6-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="397c6-107">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="397c6-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="397c6-108">Attributes and Elements</span></span>

<span data-ttu-id="397c6-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемента.</span><span class="sxs-lookup"><span data-stu-id="397c6-109">The following sections describe attributes, child elements, and parent element of the `EntrySelectedBy` element.</span></span> <span data-ttu-id="397c6-110">Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения.</span><span class="sxs-lookup"><span data-stu-id="397c6-110">You must specify at least one type, selection set, or selection condition for a definition.</span></span> <span data-ttu-id="397c6-111">Максимальное количество дочерних элементов, которое можно использовать, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="397c6-111">There is no maximum limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="397c6-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="397c6-112">Attributes</span></span>

<span data-ttu-id="397c6-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="397c6-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="397c6-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="397c6-114">Child Elements</span></span>

|<span data-ttu-id="397c6-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="397c6-115">Element</span></span>|<span data-ttu-id="397c6-116">Описание</span><span class="sxs-lookup"><span data-stu-id="397c6-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="397c6-117">Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="397c6-117">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="397c6-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="397c6-118">Optional element.</span></span><br /><br /> <span data-ttu-id="397c6-119">Определяет условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="397c6-119">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="397c6-120">Элемент SelectionSetName для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="397c6-120">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="397c6-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="397c6-121">Optional element.</span></span><br /><br /> <span data-ttu-id="397c6-122">Задает набор типов .NET, использующих это определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="397c6-122">Specifies a set of .NET types that use this definition of the control.</span></span>|
|[<span data-ttu-id="397c6-123">Элемент TypeName для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="397c6-123">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./typename-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="397c6-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="397c6-124">Optional element.</span></span><br /><br /> <span data-ttu-id="397c6-125">Указывает тип .NET, который использует это определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="397c6-125">Specifies a .NET type that uses this definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="397c6-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="397c6-126">Parent Elements</span></span>

|<span data-ttu-id="397c6-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="397c6-127">Element</span></span>|<span data-ttu-id="397c6-128">Описание</span><span class="sxs-lookup"><span data-stu-id="397c6-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="397c6-129">Элемент CustomEntry для элемента CustomControl для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="397c6-129">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="397c6-130">Предоставляет определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="397c6-130">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="397c6-131">Комментарии</span><span class="sxs-lookup"><span data-stu-id="397c6-131">Remarks</span></span>

<span data-ttu-id="397c6-132">Условия выбора используются для определения условия, которое должно существовать для использования определения, например, если у объекта есть определенное свойство или если определенное значение или скрипт свойства не равны `true` .</span><span class="sxs-lookup"><span data-stu-id="397c6-132">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="397c6-133">Дополнительные сведения об условиях выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="397c6-133">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="397c6-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="397c6-134">See Also</span></span>

[<span data-ttu-id="397c6-135">Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="397c6-135">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="397c6-136">Элемент SelectionSetName для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="397c6-136">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="397c6-137">Элемент TypeName для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="397c6-137">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./typename-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="397c6-138">Элемент CustomEntry для элемента CustomEntries для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="397c6-138">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="397c6-139">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="397c6-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
