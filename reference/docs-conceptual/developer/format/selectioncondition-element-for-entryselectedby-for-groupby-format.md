---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)
description: Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)
ms.openlocfilehash: 14c293b6bc6d6accc201de35be9219349079801d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664746"
---
# <a name="selectioncondition-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="196a4-103">Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="196a4-103">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="196a4-104">Определяет условие, которое должно существовать для использования определения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="196a4-104">Defines a condition that must exist for a control definition to be used.</span></span> <span data-ttu-id="196a4-105">Этот элемент используется при определении того, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="196a4-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="196a4-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент GroupBy для элемента "View" (Format) ошибка customcontrol для элемента GroupBy (Format) Кустоментриес для ошибка customcontrol for GroupBy (формат) кустоментри для ошибка customcontrol for GroupBy (формат) ентриселектедби для кустоментри for GroupBy (Format) селектионкондитион для EntrySelectedBy for GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="196a4-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="196a4-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="196a4-107">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="196a4-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="196a4-108">Attributes and Elements</span></span>

<span data-ttu-id="196a4-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionCondition` элемента.</span><span class="sxs-lookup"><span data-stu-id="196a4-109">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="196a4-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="196a4-110">Attributes</span></span>

<span data-ttu-id="196a4-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="196a4-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="196a4-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="196a4-112">Child Elements</span></span>

|<span data-ttu-id="196a4-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="196a4-113">Element</span></span>|<span data-ttu-id="196a4-114">Описание</span><span class="sxs-lookup"><span data-stu-id="196a4-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="196a4-115">Элемент PropertyName для элемента SelectionCondition для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="196a4-115">PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="196a4-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="196a4-116">Optional element.</span></span><br /><br /> <span data-ttu-id="196a4-117">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="196a4-117">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="196a4-118">Элемент ScriptBlock для Селектионкондитион для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="196a4-118">ScriptBlock Element for SelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="196a4-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="196a4-119">Optional element.</span></span><br /><br /> <span data-ttu-id="196a4-120">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="196a4-120">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="196a4-121">Элемент SelectionSetName для элемента SelectionCondition для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="196a4-121">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="196a4-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="196a4-122">Optional element.</span></span><br /><br /> <span data-ttu-id="196a4-123">Указывает набор типов .NET, которые инициируют условие.</span><span class="sxs-lookup"><span data-stu-id="196a4-123">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="196a4-124">Элемент TypeName для Селектионкондитион для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="196a4-124">TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="196a4-125">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="196a4-125">Optional element.</span></span><br /><br /> <span data-ttu-id="196a4-126">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="196a4-126">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="196a4-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="196a4-127">Parent Elements</span></span>

|<span data-ttu-id="196a4-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="196a4-128">Element</span></span>|<span data-ttu-id="196a4-129">Описание</span><span class="sxs-lookup"><span data-stu-id="196a4-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="196a4-130">Элемент EntrySelectedBy для элемента CustomEntry для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="196a4-130">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="196a4-131">Определяет типы .NET, которые используют это определение элемента управления или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="196a4-131">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="196a4-132">Комментарии</span><span class="sxs-lookup"><span data-stu-id="196a4-132">Remarks</span></span>

<span data-ttu-id="196a4-133">При определении условия выбора применяются следующие требования.</span><span class="sxs-lookup"><span data-stu-id="196a4-133">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="196a4-134">Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.</span><span class="sxs-lookup"><span data-stu-id="196a4-134">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="196a4-135">Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.</span><span class="sxs-lookup"><span data-stu-id="196a4-135">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="196a4-136">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="196a4-136">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="196a4-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="196a4-137">See Also</span></span>

[<span data-ttu-id="196a4-138">Элемент PropertyName для элемента SelectionCondition для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="196a4-138">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="196a4-139">Элемент ScriptBlock для элемента SelectionCondition для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="196a4-139">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="196a4-140">Элемент Селектионсетнаме для Селектионкондитион пользовательского элемента управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="196a4-140">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="196a4-141">Элемент TypeName для Селектионкондитион для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="196a4-141">TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)

[<span data-ttu-id="196a4-142">Элемент EntrySelectedBy для элемента CustomEntry для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="196a4-142">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="196a4-143">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="196a4-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
