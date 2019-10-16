---
title: Элемент Селектионкондитион для Ентриселектедби для GroupBy (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6dc2093a-dc54-42c4-ada3-c8d089ba1e8e
caps.latest.revision: 6
ms.openlocfilehash: a6738a7c4c934b2d6a16695a711f7c6c80afdd2d
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368433"
---
# <a name="selectioncondition-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="b16dd-102">Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="b16dd-102">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="b16dd-103">Определяет условие, которое должно существовать для использования определения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b16dd-103">Defines a condition that must exist for a control definition to be used.</span></span> <span data-ttu-id="b16dd-104">Этот элемент используется при определении того, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="b16dd-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="b16dd-105">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (формат) элемент GroupBy для элемента Ошибка customcontrol представления (Format) для элемента Кустоментриес (Format) для ошибка customcontrol для элемента GroupBy (Format) Кустоментри для Ошибка customcontrol для элемента Ентриселектедби GroupBy для Кустоментри для GroupBy (Format) Селектионкондитион элемента для Ентриселектедби для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="b16dd-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b16dd-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b16dd-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b16dd-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b16dd-107">Attributes and Elements</span></span>

<span data-ttu-id="b16dd-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `SelectionCondition`.</span><span class="sxs-lookup"><span data-stu-id="b16dd-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b16dd-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b16dd-109">Attributes</span></span>

<span data-ttu-id="b16dd-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="b16dd-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b16dd-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b16dd-111">Child Elements</span></span>

|<span data-ttu-id="b16dd-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="b16dd-112">Element</span></span>|<span data-ttu-id="b16dd-113">Описание</span><span class="sxs-lookup"><span data-stu-id="b16dd-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b16dd-114">Элемент PropertyName для Селектионкондитион для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="b16dd-114">PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="b16dd-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="b16dd-115">Optional element.</span></span><br /><br /> <span data-ttu-id="b16dd-116">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="b16dd-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="b16dd-117">Элемент ScriptBlock для Селектионкондитион для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="b16dd-117">ScriptBlock Element for SelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="b16dd-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="b16dd-118">Optional element.</span></span><br /><br /> <span data-ttu-id="b16dd-119">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="b16dd-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="b16dd-120">Элемент Селектионсетнаме для Селектионкондитион для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="b16dd-120">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="b16dd-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="b16dd-121">Optional element.</span></span><br /><br /> <span data-ttu-id="b16dd-122">Указывает набор типов .NET, которые инициируют условие.</span><span class="sxs-lookup"><span data-stu-id="b16dd-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="b16dd-123">Элемент TypeName для Селектионкондитион для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="b16dd-123">TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="b16dd-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="b16dd-124">Optional element.</span></span><br /><br /> <span data-ttu-id="b16dd-125">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="b16dd-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b16dd-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b16dd-126">Parent Elements</span></span>

|<span data-ttu-id="b16dd-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="b16dd-127">Element</span></span>|<span data-ttu-id="b16dd-128">Описание</span><span class="sxs-lookup"><span data-stu-id="b16dd-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b16dd-129">Элемент Ентриселектедби для Кустоментри для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="b16dd-129">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="b16dd-130">Определяет типы .NET, которые используют это определение элемента управления или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="b16dd-130">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b16dd-131">Замечания</span><span class="sxs-lookup"><span data-stu-id="b16dd-131">Remarks</span></span>

<span data-ttu-id="b16dd-132">При определении условия выбора применяются следующие требования.</span><span class="sxs-lookup"><span data-stu-id="b16dd-132">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="b16dd-133">Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.</span><span class="sxs-lookup"><span data-stu-id="b16dd-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="b16dd-134">Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.</span><span class="sxs-lookup"><span data-stu-id="b16dd-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="b16dd-135">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="b16dd-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b16dd-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="b16dd-136">See Also</span></span>

[<span data-ttu-id="b16dd-137">Элемент PropertyName для Селектионкондитион для ошибка customcontrol в представлении (формат)</span><span class="sxs-lookup"><span data-stu-id="b16dd-137">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="b16dd-138">Элемент ScriptBlock для Селектионкондитион для ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="b16dd-138">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="b16dd-139">Элемент Селектионсетнаме для Селектионкондитион пользовательского элемента управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="b16dd-139">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="b16dd-140">Элемент TypeName для Селектионкондитион для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="b16dd-140">TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)

[<span data-ttu-id="b16dd-141">Элемент Ентриселектедби для Кустоментри для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="b16dd-141">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="b16dd-142">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="b16dd-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
