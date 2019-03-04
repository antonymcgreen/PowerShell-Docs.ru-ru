---
title: Элемент EntrySelectedBy для WideEntry (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e0c98933-b7a5-4205-b811-06c0b0bf8988
caps.latest.revision: 9
ms.openlocfilehash: 54c7c261a23075721cd7bce75e530150dc0e0212
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854980"
---
# <a name="entryselectedby-element-for-wideentry-format"></a><span data-ttu-id="15cff-102">Элемент EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="15cff-102">EntrySelectedBy Element for WideEntry (Format)</span></span>

<span data-ttu-id="15cff-103">Определяет типы .NET, использовать это определение широкое представление или условие, которое должен существовать для данного определения для использования.</span><span class="sxs-lookup"><span data-stu-id="15cff-103">Defines the .NET types that use this definition of the wide view or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="15cff-104">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент WideControl (формат) элемент WideEntries (формат) элемент WideEntry (формат) EntrySelectedBy элемент конфигурации для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="15cff-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="15cff-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="15cff-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="15cff-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="15cff-106">Attributes and Elements</span></span>

<span data-ttu-id="15cff-107">Ниже описаны атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемент.</span><span class="sxs-lookup"><span data-stu-id="15cff-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="15cff-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="15cff-108">Attributes</span></span>

<span data-ttu-id="15cff-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="15cff-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="15cff-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="15cff-110">Child Elements</span></span>

|<span data-ttu-id="15cff-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="15cff-111">Element</span></span>|<span data-ttu-id="15cff-112">Описание</span><span class="sxs-lookup"><span data-stu-id="15cff-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="15cff-113">Элемент SelectionCondition для EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="15cff-113">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="15cff-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="15cff-114">Optional element.</span></span><br /><br /> <span data-ttu-id="15cff-115">Определяет условие, которое должен существовать для данного определения широкое представление для использования.</span><span class="sxs-lookup"><span data-stu-id="15cff-115">Defines the condition that must exist for this wide view definition to be used.</span></span>|
|[<span data-ttu-id="15cff-116">Элемент SelectionSetName для EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="15cff-116">SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="15cff-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="15cff-117">Optional element.</span></span><br /><br /> <span data-ttu-id="15cff-118">Задает набор типов .NET, которые используют это определение широкое представление.</span><span class="sxs-lookup"><span data-stu-id="15cff-118">Specifies a set of .NET types that use this wide view definition.</span></span>|
|[<span data-ttu-id="15cff-119">TypeName-элемент для EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="15cff-119">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="15cff-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="15cff-120">Optional element.</span></span><br /><br /> <span data-ttu-id="15cff-121">Указывает тип .NET, который использует это определение широкое представление.</span><span class="sxs-lookup"><span data-stu-id="15cff-121">Specifies a .NET type that uses this wide view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="15cff-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="15cff-122">Parent Elements</span></span>

|<span data-ttu-id="15cff-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="15cff-123">Element</span></span>|<span data-ttu-id="15cff-124">Описание</span><span class="sxs-lookup"><span data-stu-id="15cff-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="15cff-125">Элемент WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="15cff-125">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="15cff-126">Предоставляет определение широкое представление.</span><span class="sxs-lookup"><span data-stu-id="15cff-126">Provides a definition of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="15cff-127">Замечания</span><span class="sxs-lookup"><span data-stu-id="15cff-127">Remarks</span></span>

<span data-ttu-id="15cff-128">Необходимо указать по крайней мере один тип, выбора или условию выбора для определения широкое представление.</span><span class="sxs-lookup"><span data-stu-id="15cff-128">You must specify at least one type, selection set, or selection condition for a wide view definition.</span></span> <span data-ttu-id="15cff-129">Не ограничено максимальное число дочерних элементов, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="15cff-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="15cff-130">Выбор условия используются для определения условия, которое должен существовать для определения для использования, например, если объект имеет определенное свойство или значение конкретного свойства или значение сценарий принимает значение `true`.</span><span class="sxs-lookup"><span data-stu-id="15cff-130">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script value evaluates to `true`.</span></span> <span data-ttu-id="15cff-131">Дополнительные сведения об условиях выделения, см. в разделе [определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="15cff-131">For more information about selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="15cff-132">Дополнительные сведения о других компонентах широкое представление, см. в разделе [Создание широкое представление](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="15cff-132">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="15cff-133">См. также</span><span class="sxs-lookup"><span data-stu-id="15cff-133">See Also</span></span>

[<span data-ttu-id="15cff-134">Элемент WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="15cff-134">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="15cff-135">Элемент SelectionCondition для EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="15cff-135">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="15cff-136">Элемент SelectionSetName для EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="15cff-136">SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="15cff-137">TypeName-элемент для EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="15cff-137">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="15cff-138">Создание широкое представление</span><span class="sxs-lookup"><span data-stu-id="15cff-138">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="15cff-139">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="15cff-139">Defining Conditions for Displaying Data</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="15cff-140">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="15cff-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
