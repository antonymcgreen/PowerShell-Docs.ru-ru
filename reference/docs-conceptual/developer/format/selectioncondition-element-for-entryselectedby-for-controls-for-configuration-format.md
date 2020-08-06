---
title: Элемент Селектионкондитион для Ентриселектедби для элементов управления конфигурации (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 748aa1aa0ba603a44334d9401e9e2c0e68f14e03
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783421"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format"></a><span data-ttu-id="2fd2b-102">Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="2fd2b-102">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

<span data-ttu-id="2fd2b-103">Определяет условие, которое должно существовать для использования определения общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="2fd2b-103">Defines a condition that must exist for a common control definition to be used.</span></span> <span data-ttu-id="2fd2b-104">Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="2fd2b-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="2fd2b-105">Элемент конфигурации (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления Configuration (Format) ошибка customcontrol для элемента Control (формат) Кустоментриес для ошибка customcontrol для элементов управления для элемента конфигурации (Format) Кустоментри для ошибка customcontrol для элементов управления для элемента конфигурации (Format) ентриселектедби для кустоментри для элементов управления конфигурации (Format) селектионкондитион для ентриселектедби для CustomEntry для конфигурации (Format).</span><span class="sxs-lookup"><span data-stu-id="2fd2b-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2fd2b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2fd2b-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2fd2b-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2fd2b-107">Attributes and Elements</span></span>

<span data-ttu-id="2fd2b-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionCondition` элемента.</span><span class="sxs-lookup"><span data-stu-id="2fd2b-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2fd2b-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2fd2b-109">Attributes</span></span>

<span data-ttu-id="2fd2b-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2fd2b-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2fd2b-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2fd2b-111">Child Elements</span></span>

|<span data-ttu-id="2fd2b-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="2fd2b-112">Element</span></span>|<span data-ttu-id="2fd2b-113">Описание</span><span class="sxs-lookup"><span data-stu-id="2fd2b-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2fd2b-114">Элемент PropertyName для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="2fd2b-114">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="2fd2b-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="2fd2b-115">Optional element.</span></span><br /><br /> <span data-ttu-id="2fd2b-116">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="2fd2b-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="2fd2b-117">Элемент ScriptBlock для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="2fd2b-117">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="2fd2b-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="2fd2b-118">Optional element.</span></span><br /><br /> <span data-ttu-id="2fd2b-119">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="2fd2b-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="2fd2b-120">Элемент SelectionSetName для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="2fd2b-120">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="2fd2b-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="2fd2b-121">Optional element.</span></span><br /><br /> <span data-ttu-id="2fd2b-122">Указывает набор типов .NET, которые инициируют условие.</span><span class="sxs-lookup"><span data-stu-id="2fd2b-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="2fd2b-123">Элемент TypeName для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="2fd2b-123">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="2fd2b-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="2fd2b-124">Optional element.</span></span><br /><br /> <span data-ttu-id="2fd2b-125">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="2fd2b-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2fd2b-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2fd2b-126">Parent Elements</span></span>

|<span data-ttu-id="2fd2b-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="2fd2b-127">Element</span></span>|<span data-ttu-id="2fd2b-128">Описание</span><span class="sxs-lookup"><span data-stu-id="2fd2b-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2fd2b-129">Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="2fd2b-129">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="2fd2b-130">Определяет типы .NET, которые используют эту запись определения общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="2fd2b-130">Defines the .NET types that use this entry of the common control definition.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2fd2b-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="2fd2b-131">Remarks</span></span>

<span data-ttu-id="2fd2b-132">При определении условия выбора необходимо следовать приведенным ниже рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="2fd2b-132">The following guidelines must be followed when defining a selection condition:</span></span>

- <span data-ttu-id="2fd2b-133">Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.</span><span class="sxs-lookup"><span data-stu-id="2fd2b-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="2fd2b-134">Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.</span><span class="sxs-lookup"><span data-stu-id="2fd2b-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="2fd2b-135">Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="2fd2b-135">For more information about how selection conditions can be used, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2fd2b-136">См. также</span><span class="sxs-lookup"><span data-stu-id="2fd2b-136">See Also</span></span>

[<span data-ttu-id="2fd2b-137">Элемент PropertyName для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="2fd2b-137">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="2fd2b-138">Элемент ScriptBlock для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="2fd2b-138">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="2fd2b-139">Элемент SelectionSetName для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="2fd2b-139">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="2fd2b-140">Элемент TypeName для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="2fd2b-140">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="2fd2b-141">Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="2fd2b-141">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="2fd2b-142">Создание файла форматирования и типов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2fd2b-142">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
