---
title: Элемент Селектионкондитион для Ентриселектедби элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2623407e-fa10-4d27-a804-204f6d50ef22
caps.latest.revision: 6
ms.openlocfilehash: ea15e647a9dd7a7064718a0c536c4a3178d62d95
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362053"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-view-format"></a><span data-ttu-id="f9c3e-102">Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="f9c3e-102">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>

<span data-ttu-id="f9c3e-103">Определяет условие, которое должно существовать для использования определения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f9c3e-103">Defines a condition that must exist for the control definition to be used.</span></span> <span data-ttu-id="f9c3e-104">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="f9c3e-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="f9c3e-105">Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет управляющий элемент (Format) элемент управления для элементов управления представления (Format) ошибка customcontrol для элементов управления элемента Кустоментриес представления (Format) для Ошибка customcontrol для элементов управления для представления (Format) Кустоментри для Кустоментриес для элементов управления для представления (Format) Ентриселектедби элемента для Кустоментри для элементов управления для представления (формат) Селектионкондитион для элементов управления для представления ( Формат</span><span class="sxs-lookup"><span data-stu-id="f9c3e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f9c3e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f9c3e-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f9c3e-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f9c3e-107">Attributes and Elements</span></span>

<span data-ttu-id="f9c3e-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `SelectionCondition`.</span><span class="sxs-lookup"><span data-stu-id="f9c3e-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f9c3e-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f9c3e-109">Attributes</span></span>

<span data-ttu-id="f9c3e-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="f9c3e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f9c3e-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f9c3e-111">Child Elements</span></span>

|<span data-ttu-id="f9c3e-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="f9c3e-112">Element</span></span>|<span data-ttu-id="f9c3e-113">Описание</span><span class="sxs-lookup"><span data-stu-id="f9c3e-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f9c3e-114">Элемент PropertyName для Селектионкондитион элементов управления для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="f9c3e-114">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="f9c3e-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f9c3e-115">Optional element.</span></span><br /><br /> <span data-ttu-id="f9c3e-116">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="f9c3e-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="f9c3e-117">Элемент ScriptBlock для Селектионкондитион элементов управления для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="f9c3e-117">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="f9c3e-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f9c3e-118">Optional element.</span></span><br /><br /> <span data-ttu-id="f9c3e-119">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="f9c3e-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="f9c3e-120">Элемент Селектионсетнаме для Селектионкондитион элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f9c3e-120">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="f9c3e-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f9c3e-121">Optional element.</span></span><br /><br /> <span data-ttu-id="f9c3e-122">Указывает набор типов .NET, которые инициируют условие.</span><span class="sxs-lookup"><span data-stu-id="f9c3e-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="f9c3e-123">Элемент TypeName для Селектионкондитион элементов управления для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="f9c3e-123">TypeName Element for SelectionCondition for Controls for View (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="f9c3e-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f9c3e-124">Optional element.</span></span><br /><br /> <span data-ttu-id="f9c3e-125">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="f9c3e-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f9c3e-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f9c3e-126">Parent Elements</span></span>

|<span data-ttu-id="f9c3e-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="f9c3e-127">Element</span></span>|<span data-ttu-id="f9c3e-128">Описание</span><span class="sxs-lookup"><span data-stu-id="f9c3e-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f9c3e-129">Элемент Ентриселектедби для Кустоментри элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f9c3e-129">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="f9c3e-130">Определяет типы .NET, которые используют это определение элемента управления или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="f9c3e-130">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f9c3e-131">Замечания</span><span class="sxs-lookup"><span data-stu-id="f9c3e-131">Remarks</span></span>

<span data-ttu-id="f9c3e-132">При определении условия выбора применяются следующие требования.</span><span class="sxs-lookup"><span data-stu-id="f9c3e-132">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="f9c3e-133">Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.</span><span class="sxs-lookup"><span data-stu-id="f9c3e-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="f9c3e-134">Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.</span><span class="sxs-lookup"><span data-stu-id="f9c3e-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="f9c3e-135">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="f9c3e-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f9c3e-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="f9c3e-136">See Also</span></span>

[<span data-ttu-id="f9c3e-137">Элемент PropertyName для Селектионкондитион элементов управления для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="f9c3e-137">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="f9c3e-138">Элемент ScriptBlock для Селектионкондитион элементов управления для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="f9c3e-138">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="f9c3e-139">Элемент Селектионсетнаме для Селектионкондитион элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f9c3e-139">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="f9c3e-140">Элемент TypeName для Селектионкондитион элементов управления для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="f9c3e-140">TypeName Element for SelectionCondition for Controls for View (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="f9c3e-141">Элемент Ентриселектедби для Кустоментри элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f9c3e-141">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="f9c3e-142">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9c3e-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
