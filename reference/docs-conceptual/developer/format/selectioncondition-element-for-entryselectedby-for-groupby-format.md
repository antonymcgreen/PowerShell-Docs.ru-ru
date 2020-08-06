---
title: Элемент Селектионкондитион для Ентриселектедби для GroupBy (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 0930d8076c314c12cac6cdfa2b33716b7efeb6a9
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772847"
---
# <a name="selectioncondition-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="10168-102">Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="10168-102">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="10168-103">Определяет условие, которое должно существовать для использования определения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="10168-103">Defines a condition that must exist for a control definition to be used.</span></span> <span data-ttu-id="10168-104">Этот элемент используется при определении того, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="10168-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="10168-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент GroupBy для элемента "View" (Format) ошибка customcontrol для элемента GroupBy (Format) Кустоментриес для ошибка customcontrol for GroupBy (формат) кустоментри для ошибка customcontrol for GroupBy (формат) ентриселектедби для кустоментри for GroupBy (Format) селектионкондитион для EntrySelectedBy for GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="10168-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="10168-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="10168-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="10168-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="10168-107">Attributes and Elements</span></span>

<span data-ttu-id="10168-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionCondition` элемента.</span><span class="sxs-lookup"><span data-stu-id="10168-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="10168-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="10168-109">Attributes</span></span>

<span data-ttu-id="10168-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="10168-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="10168-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="10168-111">Child Elements</span></span>

|<span data-ttu-id="10168-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="10168-112">Element</span></span>|<span data-ttu-id="10168-113">Описание</span><span class="sxs-lookup"><span data-stu-id="10168-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="10168-114">Элемент PropertyName для элемента SelectionCondition для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="10168-114">PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="10168-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="10168-115">Optional element.</span></span><br /><br /> <span data-ttu-id="10168-116">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="10168-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="10168-117">Элемент ScriptBlock для Селектионкондитион для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="10168-117">ScriptBlock Element for SelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="10168-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="10168-118">Optional element.</span></span><br /><br /> <span data-ttu-id="10168-119">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="10168-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="10168-120">Элемент SelectionSetName для элемента SelectionCondition для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="10168-120">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="10168-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="10168-121">Optional element.</span></span><br /><br /> <span data-ttu-id="10168-122">Указывает набор типов .NET, которые инициируют условие.</span><span class="sxs-lookup"><span data-stu-id="10168-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="10168-123">Элемент TypeName для Селектионкондитион для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="10168-123">TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="10168-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="10168-124">Optional element.</span></span><br /><br /> <span data-ttu-id="10168-125">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="10168-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="10168-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="10168-126">Parent Elements</span></span>

|<span data-ttu-id="10168-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="10168-127">Element</span></span>|<span data-ttu-id="10168-128">Описание</span><span class="sxs-lookup"><span data-stu-id="10168-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="10168-129">Элемент EntrySelectedBy для элемента CustomEntry для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="10168-129">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="10168-130">Определяет типы .NET, которые используют это определение элемента управления или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="10168-130">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="10168-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="10168-131">Remarks</span></span>

<span data-ttu-id="10168-132">При определении условия выбора применяются следующие требования.</span><span class="sxs-lookup"><span data-stu-id="10168-132">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="10168-133">Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.</span><span class="sxs-lookup"><span data-stu-id="10168-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="10168-134">Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.</span><span class="sxs-lookup"><span data-stu-id="10168-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="10168-135">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="10168-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="10168-136">См. также</span><span class="sxs-lookup"><span data-stu-id="10168-136">See Also</span></span>

[<span data-ttu-id="10168-137">Элемент PropertyName для элемента SelectionCondition для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="10168-137">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="10168-138">Элемент ScriptBlock для элемента SelectionCondition для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="10168-138">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="10168-139">Элемент Селектионсетнаме для Селектионкондитион пользовательского элемента управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="10168-139">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="10168-140">Элемент TypeName для Селектионкондитион для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="10168-140">TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)

[<span data-ttu-id="10168-141">Элемент EntrySelectedBy для элемента CustomEntry для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="10168-141">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="10168-142">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="10168-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
