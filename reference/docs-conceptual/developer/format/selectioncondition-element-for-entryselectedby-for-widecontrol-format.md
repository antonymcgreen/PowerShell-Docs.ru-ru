---
title: Элемент Селектионкондитион для Ентриселектедби для Видеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 4115ad1ee8729ea4fc16bc19698018d2f4ed9be1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772711"
---
# <a name="selectioncondition-element-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="becb5-102">Элемент SelectionCondition для элемента EntrySelectedBy для элемента WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="becb5-102">SelectionCondition Element for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="becb5-103">Определяет условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="becb5-103">Defines the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="becb5-104">Количество условий выбора, которое можно указать для определения расширенной записи, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="becb5-104">There is no limit to the number of selection conditions that can be specified for a wide entry definition.</span></span>

<span data-ttu-id="becb5-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Ентриселектедби для видинтри (Format) Селектионкондитион для EntrySelectedBy в WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="becb5-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="becb5-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="becb5-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="becb5-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="becb5-107">Attributes and Elements</span></span>

<span data-ttu-id="becb5-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionCondition` элемента.</span><span class="sxs-lookup"><span data-stu-id="becb5-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span> <span data-ttu-id="becb5-109">Необходимо указать один `PropertyName` `ScriptBlock` элемент или.</span><span class="sxs-lookup"><span data-stu-id="becb5-109">You must specify a single `PropertyName` or `ScriptBlock` element.</span></span> <span data-ttu-id="becb5-110">`SelectionSetName`Элементы и `TypeName` являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="becb5-110">The `SelectionSetName` and `TypeName` elements are optional.</span></span> <span data-ttu-id="becb5-111">Можно указать один из этих элементов.</span><span class="sxs-lookup"><span data-stu-id="becb5-111">You can specify one of either element.</span></span>

### <a name="attributes"></a><span data-ttu-id="becb5-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="becb5-112">Attributes</span></span>

<span data-ttu-id="becb5-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="becb5-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="becb5-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="becb5-114">Child Elements</span></span>

|<span data-ttu-id="becb5-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="becb5-115">Element</span></span>|<span data-ttu-id="becb5-116">Описание</span><span class="sxs-lookup"><span data-stu-id="becb5-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="becb5-117">Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="becb5-117">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="becb5-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="becb5-118">Optional element.</span></span><br /><br /> <span data-ttu-id="becb5-119">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="becb5-119">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="becb5-120">Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="becb5-120">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="becb5-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="becb5-121">Optional element.</span></span><br /><br /> <span data-ttu-id="becb5-122">Указывает блок скрипта, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="becb5-122">Specifies the script block that triggers the condition.</span></span>|
|[<span data-ttu-id="becb5-123">Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="becb5-123">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="becb5-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="becb5-124">Optional element.</span></span><br /><br /> <span data-ttu-id="becb5-125">Указывает набор типов .NET, которые инициируют условие.</span><span class="sxs-lookup"><span data-stu-id="becb5-125">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="becb5-126">Элемент TypeName для Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="becb5-126">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="becb5-127">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="becb5-127">Optional element.</span></span><br /><br /> <span data-ttu-id="becb5-128">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="becb5-128">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="becb5-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="becb5-129">Parent Elements</span></span>

|<span data-ttu-id="becb5-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="becb5-130">Element</span></span>|<span data-ttu-id="becb5-131">Описание</span><span class="sxs-lookup"><span data-stu-id="becb5-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="becb5-132">Элемент EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="becb5-132">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="becb5-133">Определяет типы .NET, которые используют эту расширенную запись или условие, которое должно существовать для использования этой записи.</span><span class="sxs-lookup"><span data-stu-id="becb5-133">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="becb5-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="becb5-134">Remarks</span></span>

<span data-ttu-id="becb5-135">Для каждой широкой записи должно быть определено по крайней мере одно имя типа, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="becb5-135">Each wide entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="becb5-136">При определении условия выбора применяются следующие требования.</span><span class="sxs-lookup"><span data-stu-id="becb5-136">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="becb5-137">Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.</span><span class="sxs-lookup"><span data-stu-id="becb5-137">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="becb5-138">Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.</span><span class="sxs-lookup"><span data-stu-id="becb5-138">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="becb5-139">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="becb5-139">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="becb5-140">Дополнительные сведения о других компонентах расширенного представления см. [в разделе Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="becb5-140">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="becb5-141">См. также</span><span class="sxs-lookup"><span data-stu-id="becb5-141">See Also</span></span>

[<span data-ttu-id="becb5-142">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="becb5-142">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="becb5-143">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="becb5-143">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="becb5-144">Элемент EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="becb5-144">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="becb5-145">Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="becb5-145">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="becb5-146">Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="becb5-146">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="becb5-147">Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="becb5-147">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="becb5-148">Элемент TypeName для Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="becb5-148">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="becb5-149">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="becb5-149">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
