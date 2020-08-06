---
title: Элемент Селектионкондитион для Ентриселектедби элементов управления для представления (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 1c14b2638249bdbfe25f7a96e917d66ea10ed239
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787586"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-view-format"></a><span data-ttu-id="e77cb-102">Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="e77cb-102">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>

<span data-ttu-id="e77cb-103">Определяет условие, которое должно существовать для использования определения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e77cb-103">Defines a condition that must exist for the control definition to be used.</span></span> <span data-ttu-id="e77cb-104">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="e77cb-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="e77cb-105">Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет управляющий элемент (Format) элемент управления для элементов управления представления (Format) ошибка customcontrol для элементов управления элемента Кустоментриес представления (Format) для ошибка customcontrol для элементов управления для элемента Кустоментри представления (Format) Кустоментриес для элементов управления для представления (Format) Ентриселектедби элемента для Кустоментри для элементов управления для представления (Format) SelectionCondition в EntrySelectedBy для элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="e77cb-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e77cb-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e77cb-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e77cb-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e77cb-107">Attributes and Elements</span></span>

<span data-ttu-id="e77cb-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionCondition` элемента.</span><span class="sxs-lookup"><span data-stu-id="e77cb-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e77cb-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e77cb-109">Attributes</span></span>

<span data-ttu-id="e77cb-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e77cb-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e77cb-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e77cb-111">Child Elements</span></span>

|<span data-ttu-id="e77cb-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="e77cb-112">Element</span></span>|<span data-ttu-id="e77cb-113">Описание</span><span class="sxs-lookup"><span data-stu-id="e77cb-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e77cb-114">Элемент PropertyName для элемента SelectionCondition для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="e77cb-114">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="e77cb-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e77cb-115">Optional element.</span></span><br /><br /> <span data-ttu-id="e77cb-116">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="e77cb-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="e77cb-117">Элемент ScriptBlock для элемента SelectionCondition для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="e77cb-117">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="e77cb-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e77cb-118">Optional element.</span></span><br /><br /> <span data-ttu-id="e77cb-119">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="e77cb-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="e77cb-120">Элемент SelectionSetName для элемента SelectionCondition для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="e77cb-120">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="e77cb-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e77cb-121">Optional element.</span></span><br /><br /> <span data-ttu-id="e77cb-122">Указывает набор типов .NET, которые инициируют условие.</span><span class="sxs-lookup"><span data-stu-id="e77cb-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="e77cb-123">Элемент TypeName для элемента SelectionCondition для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="e77cb-123">TypeName Element for SelectionCondition for Controls for View (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="e77cb-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e77cb-124">Optional element.</span></span><br /><br /> <span data-ttu-id="e77cb-125">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="e77cb-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e77cb-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e77cb-126">Parent Elements</span></span>

|<span data-ttu-id="e77cb-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="e77cb-127">Element</span></span>|<span data-ttu-id="e77cb-128">Описание</span><span class="sxs-lookup"><span data-stu-id="e77cb-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e77cb-129">Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="e77cb-129">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="e77cb-130">Определяет типы .NET, которые используют это определение элемента управления или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="e77cb-130">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e77cb-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="e77cb-131">Remarks</span></span>

<span data-ttu-id="e77cb-132">При определении условия выбора применяются следующие требования.</span><span class="sxs-lookup"><span data-stu-id="e77cb-132">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="e77cb-133">Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.</span><span class="sxs-lookup"><span data-stu-id="e77cb-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="e77cb-134">Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.</span><span class="sxs-lookup"><span data-stu-id="e77cb-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="e77cb-135">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="e77cb-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e77cb-136">См. также</span><span class="sxs-lookup"><span data-stu-id="e77cb-136">See Also</span></span>

[<span data-ttu-id="e77cb-137">Элемент PropertyName для элемента SelectionCondition для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="e77cb-137">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="e77cb-138">Элемент ScriptBlock для элемента SelectionCondition для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="e77cb-138">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="e77cb-139">Элемент SelectionSetName для элемента SelectionCondition для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="e77cb-139">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="e77cb-140">Элемент TypeName для элемента SelectionCondition для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="e77cb-140">TypeName Element for SelectionCondition for Controls for View (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="e77cb-141">Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="e77cb-141">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="e77cb-142">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="e77cb-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
