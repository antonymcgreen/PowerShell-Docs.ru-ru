---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент EntrySelectedBy для элемента EnumerableExpansion (формат)
description: Элемент EntrySelectedBy для элемента EnumerableExpansion (формат)
ms.openlocfilehash: 8b2fff2d0b14d0622d0be2c5af3a95194c733a73
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652330"
---
# <a name="entryselectedby-element-for-enumerableexpansion-format"></a><span data-ttu-id="a017d-103">Элемент EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="a017d-103">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="a017d-104">Определяет типы .NET, которые используют это определение, или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="a017d-104">Defines the .NET types that use this definition or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="a017d-105">Элемент конфигурации (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс элемент (Format) Енумерабликспансион элемент (Format) Ентриселектедби для Енумерабликспансион (Format)</span><span class="sxs-lookup"><span data-stu-id="a017d-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a017d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a017d-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a017d-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a017d-107">Attributes and Elements</span></span>

<span data-ttu-id="a017d-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемента.</span><span class="sxs-lookup"><span data-stu-id="a017d-108">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a017d-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a017d-109">Attributes</span></span>

<span data-ttu-id="a017d-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a017d-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a017d-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a017d-111">Child Elements</span></span>

|<span data-ttu-id="a017d-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="a017d-112">Element</span></span>|<span data-ttu-id="a017d-113">Описание</span><span class="sxs-lookup"><span data-stu-id="a017d-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a017d-114">Элемент SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="a017d-114">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="a017d-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="a017d-115">Optional element.</span></span><br /><br /> <span data-ttu-id="a017d-116">Определяет условие, которое должно существовать для расширения объектов коллекции этого определения.</span><span class="sxs-lookup"><span data-stu-id="a017d-116">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|
|[<span data-ttu-id="a017d-117">Элемент SelectionSetName для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="a017d-117">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="a017d-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="a017d-118">Optional element.</span></span><br /><br /> <span data-ttu-id="a017d-119">Задает набор типов .NET, использующих это определение того, как разворачиваются объекты коллекции.</span><span class="sxs-lookup"><span data-stu-id="a017d-119">Specifies a set of .NET types that use this definition of how collection objects are expanded.</span></span>|
|[<span data-ttu-id="a017d-120">Элемент TypeName для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="a017d-120">TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="a017d-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="a017d-121">Optional element.</span></span><br /><br /> <span data-ttu-id="a017d-122">Указывает тип .NET, использующий это определение того, как разворачиваются объекты коллекции.</span><span class="sxs-lookup"><span data-stu-id="a017d-122">Specifies a .NET type that uses this definition of how collection objects are expanded.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a017d-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a017d-123">Parent Elements</span></span>

|<span data-ttu-id="a017d-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="a017d-124">Element</span></span>|<span data-ttu-id="a017d-125">Описание</span><span class="sxs-lookup"><span data-stu-id="a017d-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a017d-126">Элемент EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="a017d-126">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="a017d-127">Определяет, каким способом развертываются определенные объекты коллекции .NET, когда они отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="a017d-127">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a017d-128">Комментарии</span><span class="sxs-lookup"><span data-stu-id="a017d-128">Remarks</span></span>

<span data-ttu-id="a017d-129">Необходимо указать по крайней мере один тип, набор выбора или условие выбора для записи определения.</span><span class="sxs-lookup"><span data-stu-id="a017d-129">You must specify at least one type, selection set, or selection condition for a definition entry.</span></span> <span data-ttu-id="a017d-130">Максимальное количество дочерних элементов, которое можно использовать, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="a017d-130">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="a017d-131">Условия выбора используются для определения условия, которое должно существовать, чтобы использовать определение, например, если объект имеет определенное свойство или значение конкретного свойства или скрипта равно `true` .</span><span class="sxs-lookup"><span data-stu-id="a017d-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="a017d-132">Дополнительные сведения об условиях выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="a017d-132">For more information about selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a017d-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="a017d-133">See Also</span></span>

[<span data-ttu-id="a017d-134">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="a017d-134">Defining Conditions for Displaying Data</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="a017d-135">Элемент EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="a017d-135">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)

[<span data-ttu-id="a017d-136">Элемент SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="a017d-136">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="a017d-137">Элемент SelectionSetName для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="a017d-137">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="a017d-138">Элемент TypeName для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="a017d-138">TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="a017d-139">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="a017d-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
