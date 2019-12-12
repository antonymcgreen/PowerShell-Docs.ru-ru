---
title: Элемент Селектионкондитион для Ентриселектедби для элементов управления конфигурации (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f23ef405-0f1e-4607-b3f4-4017b7ead106
caps.latest.revision: 7
ms.openlocfilehash: a5098da55d0a63272a121b973cb05e26dc47e3e1
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368453"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format"></a><span data-ttu-id="35f55-102">Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="35f55-102">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

<span data-ttu-id="35f55-103">Определяет условие, которое должно существовать для использования определения общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="35f55-103">Defines a condition that must exist for a common control definition to be used.</span></span> <span data-ttu-id="35f55-104">Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="35f55-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="35f55-105">Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control (формат) Кустоментриес для ошибка customcontrol для элементов управления для Элемент конфигурации (Format) Кустоментри для ошибка customcontrol элементов управления для элемента конфигурации (Format) Ентриселектедби для Кустоментри элементов управления для элемента конфигурации (Format) Селектионкондитион для Ентриселектедби для Кустоментри для Конфигурация (формат)</span><span class="sxs-lookup"><span data-stu-id="35f55-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="35f55-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="35f55-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="35f55-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="35f55-107">Attributes and Elements</span></span>

<span data-ttu-id="35f55-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `SelectionCondition`.</span><span class="sxs-lookup"><span data-stu-id="35f55-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="35f55-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="35f55-109">Attributes</span></span>

<span data-ttu-id="35f55-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="35f55-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="35f55-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="35f55-111">Child Elements</span></span>

|<span data-ttu-id="35f55-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="35f55-112">Element</span></span>|<span data-ttu-id="35f55-113">Описание</span><span class="sxs-lookup"><span data-stu-id="35f55-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="35f55-114">Элемент PropertyName для Селектионкондитион элементов управления в конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="35f55-114">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="35f55-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="35f55-115">Optional element.</span></span><br /><br /> <span data-ttu-id="35f55-116">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="35f55-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="35f55-117">Элемент ScriptBlock для Селектионкондитион элементов управления в конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="35f55-117">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="35f55-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="35f55-118">Optional element.</span></span><br /><br /> <span data-ttu-id="35f55-119">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="35f55-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="35f55-120">Элемент Селектионсетнаме для Селектионкондитион для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="35f55-120">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="35f55-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="35f55-121">Optional element.</span></span><br /><br /> <span data-ttu-id="35f55-122">Указывает набор типов .NET, которые инициируют условие.</span><span class="sxs-lookup"><span data-stu-id="35f55-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="35f55-123">Элемент TypeName для Селектионкондитион для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="35f55-123">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="35f55-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="35f55-124">Optional element.</span></span><br /><br /> <span data-ttu-id="35f55-125">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="35f55-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="35f55-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="35f55-126">Parent Elements</span></span>

|<span data-ttu-id="35f55-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="35f55-127">Element</span></span>|<span data-ttu-id="35f55-128">Описание</span><span class="sxs-lookup"><span data-stu-id="35f55-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="35f55-129">Элемент Ентриселектедби для Кустоментри для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="35f55-129">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="35f55-130">Определяет типы .NET, которые используют эту запись определения общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="35f55-130">Defines the .NET types that use this entry of the common control definition.</span></span>|

## <a name="remarks"></a><span data-ttu-id="35f55-131">Замечания</span><span class="sxs-lookup"><span data-stu-id="35f55-131">Remarks</span></span>

<span data-ttu-id="35f55-132">При определении условия выбора необходимо следовать приведенным ниже рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="35f55-132">The following guidelines must be followed when defining a selection condition:</span></span>

- <span data-ttu-id="35f55-133">Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.</span><span class="sxs-lookup"><span data-stu-id="35f55-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="35f55-134">Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.</span><span class="sxs-lookup"><span data-stu-id="35f55-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="35f55-135">Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="35f55-135">For more information about how selection conditions can be used, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="35f55-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="35f55-136">See Also</span></span>

[<span data-ttu-id="35f55-137">Элемент PropertyName для Селектионкондитион элементов управления в конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="35f55-137">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="35f55-138">Элемент ScriptBlock для Селектионкондитион элементов управления в конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="35f55-138">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="35f55-139">Элемент Селектионсетнаме для Селектионкондитион для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="35f55-139">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="35f55-140">Элемент TypeName для Селектионкондитион для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="35f55-140">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="35f55-141">Элемент Ентриселектедби для Кустоментри для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="35f55-141">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="35f55-142">Создание файла форматирования и типов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="35f55-142">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
