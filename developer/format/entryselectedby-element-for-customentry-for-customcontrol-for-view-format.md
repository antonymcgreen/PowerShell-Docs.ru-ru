---
title: Элемент EntrySelectedBy для CustomEntry для пользовательский элемент управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7828b45b-eabf-4432-b127-131b4ef0c800
caps.latest.revision: 8
ms.openlocfilehash: e7176f9f6ef67116ea7c07a46797fb0ba84f915d
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859590"
---
# <a name="entryselectedby-element-for-customentry-for-customcontrol-for-view-format"></a><span data-ttu-id="ee9a4-102">Элемент EntrySelectedBy для элемента CustomEntry для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="ee9a4-102">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>

<span data-ttu-id="ee9a4-103">Определяет типы .NET, использующих этот пользовательскую запись или условие, которое должен существовать для данной записи для использования.</span><span class="sxs-lookup"><span data-stu-id="ee9a4-103">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>

<span data-ttu-id="ee9a4-104">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент пользовательский элемент управления (формат) CustomEntries элемент конфигурации для пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для EntrySelectedBy представление (формат) Элемент для CustomEntry для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="ee9a4-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ee9a4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ee9a4-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ee9a4-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ee9a4-106">Attributes and Elements</span></span>

<span data-ttu-id="ee9a4-107">Ниже описаны атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемент.</span><span class="sxs-lookup"><span data-stu-id="ee9a4-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ee9a4-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ee9a4-108">Attributes</span></span>

<span data-ttu-id="ee9a4-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="ee9a4-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ee9a4-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ee9a4-110">Child Elements</span></span>

|<span data-ttu-id="ee9a4-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="ee9a4-111">Element</span></span>|<span data-ttu-id="ee9a4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ee9a4-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ee9a4-113">Элемент SelectionCondition для EntrySelectedBy для CustomEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="ee9a4-113">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="ee9a4-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ee9a4-114">Optional element.</span></span><br /><br /> <span data-ttu-id="ee9a4-115">Определяет условие, которое должен существовать для данного определения для использования.</span><span class="sxs-lookup"><span data-stu-id="ee9a4-115">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="ee9a4-116">Элемент SelectionSetName для EntrySelectedBy для CustomEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="ee9a4-116">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)|<span data-ttu-id="ee9a4-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ee9a4-117">Optional element.</span></span><br /><br /> <span data-ttu-id="ee9a4-118">Задает набор типов .NET, которые используют это определение элемента управления представления.</span><span class="sxs-lookup"><span data-stu-id="ee9a4-118">Specifies a set of .NET types that use this definition of the control view.</span></span>|
|[<span data-ttu-id="ee9a4-119">TypeName-элемент для EntrySelectedBy для CustomEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="ee9a4-119">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="ee9a4-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ee9a4-120">Optional element.</span></span><br /><br /> <span data-ttu-id="ee9a4-121">Указывает тип .NET, который использует это определение элемента управления представления.</span><span class="sxs-lookup"><span data-stu-id="ee9a4-121">Specifies a .NET type that uses this definition of the control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ee9a4-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ee9a4-122">Parent Elements</span></span>

|<span data-ttu-id="ee9a4-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="ee9a4-123">Element</span></span>|<span data-ttu-id="ee9a4-124">Описание</span><span class="sxs-lookup"><span data-stu-id="ee9a4-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ee9a4-125">Элемент CustomEntry для CustomEntries для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="ee9a4-125">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="ee9a4-126">Определяет элементы управления, используемые определенными объектами .NET.</span><span class="sxs-lookup"><span data-stu-id="ee9a4-126">Defines the controls used by specific .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ee9a4-127">Замечания</span><span class="sxs-lookup"><span data-stu-id="ee9a4-127">Remarks</span></span>

<span data-ttu-id="ee9a4-128">Необходимо указать по крайней мере один тип, выбора или условию выбора для записи.</span><span class="sxs-lookup"><span data-stu-id="ee9a4-128">You must specify at least one type, selection set, or selection condition for an entry.</span></span> <span data-ttu-id="ee9a4-129">Не ограничено максимальное число дочерних элементов, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="ee9a4-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="ee9a4-130">Выбор условия используются для определения условия, которое должно существовать записи, которую необходимо использовать, например, если объект имеет определенное свойство или когда значения конкретного свойства или скрипта, результатом которого является `true`.</span><span class="sxs-lookup"><span data-stu-id="ee9a4-130">Selection conditions are used to define a condition that must exist for the entry to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="ee9a4-131">Дополнительные сведения об условиях выделения, см. в разделе [определение условий для, когда операция отчета или элемента используется](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="ee9a4-131">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="ee9a4-132">Дополнительные сведения о компонентах представления пользовательского элемента управления, см. в разделе [пользовательского элемента управления представления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="ee9a4-132">For more information about the components of a custom control view, see [Custom Control View](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ee9a4-133">См. также</span><span class="sxs-lookup"><span data-stu-id="ee9a4-133">See Also</span></span>

[<span data-ttu-id="ee9a4-134">Элемент SelectionCondition для EntrySelectedBy для CustomEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="ee9a4-134">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="ee9a4-135">Элемент SelectionSetName для EntrySelectedBy для CustomEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="ee9a4-135">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

[<span data-ttu-id="ee9a4-136">TypeName-элемент для EntrySelectedBy для CustomEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="ee9a4-136">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="ee9a4-137">Элемент CustomEntry для CustomEntries для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="ee9a4-137">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="ee9a4-138">Представление пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="ee9a4-138">Custom Control View</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="ee9a4-139">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee9a4-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
