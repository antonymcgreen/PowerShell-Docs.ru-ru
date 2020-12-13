---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент SelectionCondition для элемента EntrySelectedBy для элемента WideControl (формат)
description: Элемент SelectionCondition для элемента EntrySelectedBy для элемента WideControl (формат)
ms.openlocfilehash: 8c51ca72edc6ad174dc289c61a8987e8f9495d19
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655110"
---
# <a name="selectioncondition-element-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="2294c-103">Элемент SelectionCondition для элемента EntrySelectedBy для элемента WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="2294c-103">SelectionCondition Element for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="2294c-104">Определяет условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="2294c-104">Defines the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="2294c-105">Количество условий выбора, которое можно указать для определения расширенной записи, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="2294c-105">There is no limit to the number of selection conditions that can be specified for a wide entry definition.</span></span>

<span data-ttu-id="2294c-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Ентриселектедби для видинтри (Format) Селектионкондитион для EntrySelectedBy в WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="2294c-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2294c-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2294c-107">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2294c-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2294c-108">Attributes and Elements</span></span>

<span data-ttu-id="2294c-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionCondition` элемента.</span><span class="sxs-lookup"><span data-stu-id="2294c-109">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span> <span data-ttu-id="2294c-110">Необходимо указать один `PropertyName` `ScriptBlock` элемент или.</span><span class="sxs-lookup"><span data-stu-id="2294c-110">You must specify a single `PropertyName` or `ScriptBlock` element.</span></span> <span data-ttu-id="2294c-111">`SelectionSetName`Элементы и `TypeName` являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="2294c-111">The `SelectionSetName` and `TypeName` elements are optional.</span></span> <span data-ttu-id="2294c-112">Можно указать один из этих элементов.</span><span class="sxs-lookup"><span data-stu-id="2294c-112">You can specify one of either element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2294c-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2294c-113">Attributes</span></span>

<span data-ttu-id="2294c-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2294c-114">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2294c-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2294c-115">Child Elements</span></span>

|<span data-ttu-id="2294c-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="2294c-116">Element</span></span>|<span data-ttu-id="2294c-117">Описание</span><span class="sxs-lookup"><span data-stu-id="2294c-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2294c-118">Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="2294c-118">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="2294c-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="2294c-119">Optional element.</span></span><br /><br /> <span data-ttu-id="2294c-120">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="2294c-120">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="2294c-121">Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="2294c-121">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="2294c-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="2294c-122">Optional element.</span></span><br /><br /> <span data-ttu-id="2294c-123">Указывает блок скрипта, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="2294c-123">Specifies the script block that triggers the condition.</span></span>|
|[<span data-ttu-id="2294c-124">Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="2294c-124">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="2294c-125">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="2294c-125">Optional element.</span></span><br /><br /> <span data-ttu-id="2294c-126">Указывает набор типов .NET, которые инициируют условие.</span><span class="sxs-lookup"><span data-stu-id="2294c-126">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="2294c-127">Элемент TypeName для Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="2294c-127">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="2294c-128">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="2294c-128">Optional element.</span></span><br /><br /> <span data-ttu-id="2294c-129">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="2294c-129">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2294c-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2294c-130">Parent Elements</span></span>

|<span data-ttu-id="2294c-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="2294c-131">Element</span></span>|<span data-ttu-id="2294c-132">Описание</span><span class="sxs-lookup"><span data-stu-id="2294c-132">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2294c-133">Элемент EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="2294c-133">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="2294c-134">Определяет типы .NET, которые используют эту расширенную запись или условие, которое должно существовать для использования этой записи.</span><span class="sxs-lookup"><span data-stu-id="2294c-134">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2294c-135">Комментарии</span><span class="sxs-lookup"><span data-stu-id="2294c-135">Remarks</span></span>

<span data-ttu-id="2294c-136">Для каждой широкой записи должно быть определено по крайней мере одно имя типа, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="2294c-136">Each wide entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="2294c-137">При определении условия выбора применяются следующие требования.</span><span class="sxs-lookup"><span data-stu-id="2294c-137">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="2294c-138">Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.</span><span class="sxs-lookup"><span data-stu-id="2294c-138">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="2294c-139">Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.</span><span class="sxs-lookup"><span data-stu-id="2294c-139">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="2294c-140">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="2294c-140">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="2294c-141">Дополнительные сведения о других компонентах расширенного представления см. [в разделе Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="2294c-141">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2294c-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="2294c-142">See Also</span></span>

[<span data-ttu-id="2294c-143">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="2294c-143">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="2294c-144">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="2294c-144">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="2294c-145">Элемент EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="2294c-145">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="2294c-146">Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="2294c-146">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="2294c-147">Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="2294c-147">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="2294c-148">Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="2294c-148">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="2294c-149">Элемент TypeName для Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="2294c-149">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="2294c-150">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="2294c-150">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
