---
title: Элемент EntrySelectedBy для EnumerableExpansion (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3af6aff8-4c2d-4f08-9bb1-e1f3ed3e583e
caps.latest.revision: 11
ms.openlocfilehash: 6a371bdbb85d07730c32931a4a79ee40856ce298
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855590"
---
# <a name="entryselectedby-element-for-enumerableexpansion-format"></a><span data-ttu-id="5a561-102">Элемент EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="5a561-102">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="5a561-103">Определяет типы .NET, которые используют это определение или условие, которое должен существовать для данного определения для использования.</span><span class="sxs-lookup"><span data-stu-id="5a561-103">Defines the .NET types that use this definition or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="5a561-104">Элемент (формат) элемент DefaultSettings (формат) элемент EnumerableExpansions (формат) элемент EnumerableExpansion (формат) EntrySelectedBy элемент конфигурации для EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="5a561-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5a561-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5a561-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5a561-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5a561-106">Attributes and Elements</span></span>

<span data-ttu-id="5a561-107">Ниже описаны атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемент.</span><span class="sxs-lookup"><span data-stu-id="5a561-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5a561-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5a561-108">Attributes</span></span>

<span data-ttu-id="5a561-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="5a561-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5a561-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5a561-110">Child Elements</span></span>

|<span data-ttu-id="5a561-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="5a561-111">Element</span></span>|<span data-ttu-id="5a561-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5a561-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5a561-113">Элемент SelectionCondition для EntrySelectedBy для EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="5a561-113">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="5a561-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="5a561-114">Optional element.</span></span><br /><br /> <span data-ttu-id="5a561-115">Определяет условие, которое должно существовать разверните коллекцию объектов данного определения.</span><span class="sxs-lookup"><span data-stu-id="5a561-115">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|
|[<span data-ttu-id="5a561-116">Элемент SelectionSetName для EntrySelectedBy для EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="5a561-116">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="5a561-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="5a561-117">Optional element.</span></span><br /><br /> <span data-ttu-id="5a561-118">Задает набор типов .NET, которые используют это определение разворачиваются как коллекции объектов.</span><span class="sxs-lookup"><span data-stu-id="5a561-118">Specifies a set of .NET types that use this definition of how collection objects are expanded.</span></span>|
|[<span data-ttu-id="5a561-119">TypeName-элемент для EntrySelectedBy для EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="5a561-119">TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="5a561-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="5a561-120">Optional element.</span></span><br /><br /> <span data-ttu-id="5a561-121">Указывает тип .NET, который использует это определение разворачиваются как коллекции объектов.</span><span class="sxs-lookup"><span data-stu-id="5a561-121">Specifies a .NET type that uses this definition of how collection objects are expanded.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5a561-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5a561-122">Parent Elements</span></span>

|<span data-ttu-id="5a561-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="5a561-123">Element</span></span>|<span data-ttu-id="5a561-124">Описание</span><span class="sxs-lookup"><span data-stu-id="5a561-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5a561-125">Элемент EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="5a561-125">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="5a561-126">Определяет, как определенные коллекции .NET, объекты развертываются в том случае, когда они отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="5a561-126">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5a561-127">Замечания</span><span class="sxs-lookup"><span data-stu-id="5a561-127">Remarks</span></span>

<span data-ttu-id="5a561-128">Необходимо указать по крайней мере один тип, выбора или условию выбора для определения записи.</span><span class="sxs-lookup"><span data-stu-id="5a561-128">You must specify at least one type, selection set, or selection condition for a definition entry.</span></span> <span data-ttu-id="5a561-129">Не ограничено максимальное число дочерних элементов, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="5a561-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="5a561-130">Выбор условия используются для определения условия, которое должен существовать для определения для использования, например, если объект имеет определенное свойство или значение конкретного свойства или скрипт принимает значение `true`.</span><span class="sxs-lookup"><span data-stu-id="5a561-130">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="5a561-131">Дополнительные сведения об условиях выделения, см. в разделе [определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="5a561-131">For more information about selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5a561-132">См. также</span><span class="sxs-lookup"><span data-stu-id="5a561-132">See Also</span></span>

[<span data-ttu-id="5a561-133">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="5a561-133">Defining Conditions for Displaying Data</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="5a561-134">Элемент EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="5a561-134">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)

[<span data-ttu-id="5a561-135">Элемент SelectionCondition для EntrySelectedBy для EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="5a561-135">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="5a561-136">Элемент SelectionSetName для EntrySelectedBy для EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="5a561-136">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="5a561-137">TypeName-элемент для EntrySelectedBy для EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="5a561-137">TypeName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="5a561-138">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a561-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
