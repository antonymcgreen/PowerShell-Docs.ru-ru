---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента View (формат)
description: Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента View (формат)
ms.openlocfilehash: 29b0574a95d81962fb3f72a526f89273baeea647
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660271"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-view-format"></a><span data-ttu-id="d8582-103">Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="d8582-103">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>

<span data-ttu-id="d8582-104">Определяет типы .NET, которые используют это определение элемента управления или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="d8582-104">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="d8582-105">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="d8582-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="d8582-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет элементом управления "элемент (Format)" для элементов управления для элемента управления "View" (Format) ошибка customcontrol для элемента Control для элементов управления для элемента "View" (формат) Кустоментриес для ошибка customcontrol для элементов управления для представления (Format) кустоментри для кустоментриес для элементов управления представления (формат).</span><span class="sxs-lookup"><span data-stu-id="d8582-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d8582-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d8582-107">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d8582-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d8582-108">Attributes and Elements</span></span>

<span data-ttu-id="d8582-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемента.</span><span class="sxs-lookup"><span data-stu-id="d8582-109">The following sections describe attributes, child elements, and parent element of the `EntrySelectedBy` element.</span></span> <span data-ttu-id="d8582-110">Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения.</span><span class="sxs-lookup"><span data-stu-id="d8582-110">You must specify at least one type, selection set, or selection condition for a definition.</span></span> <span data-ttu-id="d8582-111">Максимальное количество дочерних элементов, которое можно использовать, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="d8582-111">There is no maximum limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="d8582-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d8582-112">Attributes</span></span>

<span data-ttu-id="d8582-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d8582-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d8582-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d8582-114">Child Elements</span></span>

|<span data-ttu-id="d8582-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="d8582-115">Element</span></span>|<span data-ttu-id="d8582-116">Описание</span><span class="sxs-lookup"><span data-stu-id="d8582-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d8582-117">Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="d8582-117">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="d8582-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d8582-118">Optional element.</span></span><br /><br /> <span data-ttu-id="d8582-119">Определяет условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="d8582-119">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="d8582-120">Элемент SelectionSetName для элемента EntrySelectedBy для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="d8582-120">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="d8582-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d8582-121">Optional element.</span></span><br /><br /> <span data-ttu-id="d8582-122">Задает набор типов .NET, использующих это определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d8582-122">Specifies a set of .NET types that use this definition of the control.</span></span>|
|[<span data-ttu-id="d8582-123">Элемент TypeName для элемента EntrySelectedBy для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="d8582-123">TypeName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./typename-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="d8582-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d8582-124">Optional element.</span></span><br /><br /> <span data-ttu-id="d8582-125">Указывает тип .NET, который использует это определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d8582-125">Specifies a .NET type that uses this definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d8582-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d8582-126">Parent Elements</span></span>

|<span data-ttu-id="d8582-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="d8582-127">Element</span></span>|<span data-ttu-id="d8582-128">Описание</span><span class="sxs-lookup"><span data-stu-id="d8582-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d8582-129">Элемент CustomEntry для элемента CustomEntries для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="d8582-129">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="d8582-130">Предоставляет определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d8582-130">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d8582-131">Комментарии</span><span class="sxs-lookup"><span data-stu-id="d8582-131">Remarks</span></span>

<span data-ttu-id="d8582-132">Условия выбора используются для определения условия, которое должно существовать для использования определения, например, если у объекта есть определенное свойство или если определенное значение или скрипт свойства не равны `true` .</span><span class="sxs-lookup"><span data-stu-id="d8582-132">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="d8582-133">Дополнительные сведения об условиях выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="d8582-133">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d8582-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="d8582-134">See Also</span></span>

[<span data-ttu-id="d8582-135">Элемент CustomEntry для элемента CustomEntries для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="d8582-135">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="d8582-136">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8582-136">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
