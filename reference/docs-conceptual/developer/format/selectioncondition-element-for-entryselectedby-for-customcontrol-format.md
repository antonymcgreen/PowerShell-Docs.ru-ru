---
title: Элемент Селектионкондитион для Ентриселектедби для ошибка customcontrol (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 231e9c6d-09ec-4e68-80ee-0c8f7fe1b9f5
caps.latest.revision: 7
ms.openlocfilehash: 49e2c0cf09dfa55b535effcd431e980daf12fac3
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368443"
---
# <a name="selectioncondition-element-for-entryselectedby-for-customcontrol-format"></a><span data-ttu-id="6c770-102">Элемент SelectionCondition для элемента EntrySelectedBy для элемента CustomControl (формат)</span><span class="sxs-lookup"><span data-stu-id="6c770-102">SelectionCondition Element for EntrySelectedBy for CustomControl (Format)</span></span>

<span data-ttu-id="6c770-103">Определяет условие, которое должно существовать для использования определения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6c770-103">Defines a condition that must exist for a control definition to be used.</span></span> <span data-ttu-id="6c770-104">Этот элемент используется при определении пользовательского представления элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6c770-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="6c770-105">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) представление элемента Ошибка customcontrol для элемента представления (Format) Кустоментриес для ошибка customcontrol для элемента View (Format) Кустоментри для Кустоментриес для ошибка customcontrol View ( Формат). элемент Кустомитем для Кустоментри для ошибка customcontrol для представления (Format) Ентриселектедби для Кустоментри для ошибка customcontrol for View (Format) Селектионкондитион для ентриселектедби для ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="6c770-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) EntrySelectedBy Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6c770-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c770-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6c770-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6c770-107">Attributes and Elements</span></span>

<span data-ttu-id="6c770-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `SelectionCondition`.</span><span class="sxs-lookup"><span data-stu-id="6c770-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6c770-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6c770-109">Attributes</span></span>

<span data-ttu-id="6c770-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="6c770-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6c770-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6c770-111">Child Elements</span></span>

|<span data-ttu-id="6c770-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="6c770-112">Element</span></span>|<span data-ttu-id="6c770-113">Описание</span><span class="sxs-lookup"><span data-stu-id="6c770-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6c770-114">Элемент PropertyName для Селектионкондитион для ошибка customcontrol в представлении (формат)</span><span class="sxs-lookup"><span data-stu-id="6c770-114">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="6c770-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="6c770-115">Optional element.</span></span><br /><br /> <span data-ttu-id="6c770-116">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="6c770-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="6c770-117">Элемент ScriptBlock для Селектионкондитион для ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="6c770-117">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="6c770-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="6c770-118">Optional element.</span></span><br /><br /> <span data-ttu-id="6c770-119">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="6c770-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="6c770-120">Элемент Селектионсетнаме для Селектионкондитион пользовательского элемента управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="6c770-120">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="6c770-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="6c770-121">Optional element.</span></span><br /><br /> <span data-ttu-id="6c770-122">Указывает набор типов .NET, которые инициируют условие.</span><span class="sxs-lookup"><span data-stu-id="6c770-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="6c770-123">Элемент TypeName для Селектионкондитион для ошибка customcontrol для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="6c770-123">TypeName Element for SelectionCondition for CustomControl for View  (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="6c770-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="6c770-124">Optional element.</span></span><br /><br /> <span data-ttu-id="6c770-125">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="6c770-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="6c770-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6c770-126">Parent Elements</span></span>

|<span data-ttu-id="6c770-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="6c770-127">Element</span></span>|<span data-ttu-id="6c770-128">Описание</span><span class="sxs-lookup"><span data-stu-id="6c770-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6c770-129">Элемент Ентриселектедби для Кустоментри для ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="6c770-129">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="6c770-130">Определяет типы .NET, которые используют это определение элемента управления или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="6c770-130">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6c770-131">Замечания</span><span class="sxs-lookup"><span data-stu-id="6c770-131">Remarks</span></span>

<span data-ttu-id="6c770-132">При определении условия выбора применяются следующие требования.</span><span class="sxs-lookup"><span data-stu-id="6c770-132">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="6c770-133">Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.</span><span class="sxs-lookup"><span data-stu-id="6c770-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="6c770-134">Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.</span><span class="sxs-lookup"><span data-stu-id="6c770-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="6c770-135">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="6c770-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6c770-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="6c770-136">See Also</span></span>

[<span data-ttu-id="6c770-137">Элемент PropertyName для Селектионкондитион для ошибка customcontrol в представлении (формат)</span><span class="sxs-lookup"><span data-stu-id="6c770-137">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="6c770-138">Элемент ScriptBlock для Селектионкондитион для ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="6c770-138">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="6c770-139">Элемент Селектионсетнаме для Селектионкондитион пользовательского элемента управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="6c770-139">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="6c770-140">Элемент TypeName для Селектионкондитион для ошибка customcontrol для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="6c770-140">TypeName Element for SelectionCondition for CustomControl for View  (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="6c770-141">Элемент Ентриселектедби для Кустоментри для ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="6c770-141">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="6c770-142">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="6c770-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
