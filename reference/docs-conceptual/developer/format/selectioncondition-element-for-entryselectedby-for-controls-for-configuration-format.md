---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)
description: Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)
ms.openlocfilehash: ce00cdf868a3075875043aeb59f2cb8a17d049a9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645783"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format"></a><span data-ttu-id="28d6f-103">Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="28d6f-103">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

<span data-ttu-id="28d6f-104">Определяет условие, которое должно существовать для использования определения общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="28d6f-104">Defines a condition that must exist for a common control definition to be used.</span></span> <span data-ttu-id="28d6f-105">Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="28d6f-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="28d6f-106">Элемент конфигурации (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления Configuration (Format) ошибка customcontrol для элемента Control (формат) Кустоментриес для ошибка customcontrol для элементов управления для элемента конфигурации (Format) Кустоментри для ошибка customcontrol для элементов управления для элемента конфигурации (Format) ентриселектедби для кустоментри для элементов управления конфигурации (Format) селектионкондитион для ентриселектедби для CustomEntry для конфигурации (Format).</span><span class="sxs-lookup"><span data-stu-id="28d6f-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="28d6f-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="28d6f-107">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="28d6f-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="28d6f-108">Attributes and Elements</span></span>

<span data-ttu-id="28d6f-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionCondition` элемента.</span><span class="sxs-lookup"><span data-stu-id="28d6f-109">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="28d6f-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="28d6f-110">Attributes</span></span>

<span data-ttu-id="28d6f-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="28d6f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="28d6f-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="28d6f-112">Child Elements</span></span>

|<span data-ttu-id="28d6f-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="28d6f-113">Element</span></span>|<span data-ttu-id="28d6f-114">Описание</span><span class="sxs-lookup"><span data-stu-id="28d6f-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="28d6f-115">Элемент PropertyName для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="28d6f-115">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="28d6f-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="28d6f-116">Optional element.</span></span><br /><br /> <span data-ttu-id="28d6f-117">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="28d6f-117">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="28d6f-118">Элемент ScriptBlock для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="28d6f-118">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="28d6f-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="28d6f-119">Optional element.</span></span><br /><br /> <span data-ttu-id="28d6f-120">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="28d6f-120">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="28d6f-121">Элемент SelectionSetName для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="28d6f-121">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="28d6f-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="28d6f-122">Optional element.</span></span><br /><br /> <span data-ttu-id="28d6f-123">Указывает набор типов .NET, которые инициируют условие.</span><span class="sxs-lookup"><span data-stu-id="28d6f-123">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="28d6f-124">Элемент TypeName для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="28d6f-124">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="28d6f-125">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="28d6f-125">Optional element.</span></span><br /><br /> <span data-ttu-id="28d6f-126">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="28d6f-126">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="28d6f-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="28d6f-127">Parent Elements</span></span>

|<span data-ttu-id="28d6f-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="28d6f-128">Element</span></span>|<span data-ttu-id="28d6f-129">Описание</span><span class="sxs-lookup"><span data-stu-id="28d6f-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="28d6f-130">Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="28d6f-130">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="28d6f-131">Определяет типы .NET, которые используют эту запись определения общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="28d6f-131">Defines the .NET types that use this entry of the common control definition.</span></span>|

## <a name="remarks"></a><span data-ttu-id="28d6f-132">Комментарии</span><span class="sxs-lookup"><span data-stu-id="28d6f-132">Remarks</span></span>

<span data-ttu-id="28d6f-133">При определении условия выбора необходимо следовать приведенным ниже рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="28d6f-133">The following guidelines must be followed when defining a selection condition:</span></span>

- <span data-ttu-id="28d6f-134">Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.</span><span class="sxs-lookup"><span data-stu-id="28d6f-134">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="28d6f-135">Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.</span><span class="sxs-lookup"><span data-stu-id="28d6f-135">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="28d6f-136">Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="28d6f-136">For more information about how selection conditions can be used, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="28d6f-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="28d6f-137">See Also</span></span>

[<span data-ttu-id="28d6f-138">Элемент PropertyName для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="28d6f-138">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="28d6f-139">Элемент ScriptBlock для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="28d6f-139">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="28d6f-140">Элемент SelectionSetName для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="28d6f-140">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="28d6f-141">Элемент TypeName для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="28d6f-141">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="28d6f-142">Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="28d6f-142">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="28d6f-143">Создание файла форматирования и типов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="28d6f-143">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
