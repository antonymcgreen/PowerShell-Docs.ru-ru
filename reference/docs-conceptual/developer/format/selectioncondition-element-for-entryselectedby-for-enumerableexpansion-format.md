---
title: Элемент Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8c012115-9241-4851-9015-841eb508faf3
caps.latest.revision: 10
ms.openlocfilehash: d6adf2fa62384d671fd6a07dd185a941daa44cec
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362013"
---
# <a name="selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="e9928-102">Элемент SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="e9928-102">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="e9928-103">Определяет условие, которое должно существовать для расширения объектов коллекции этого определения.</span><span class="sxs-lookup"><span data-stu-id="e9928-103">Defines the condition that must exist to expand the collection objects of this definition.</span></span>

<span data-ttu-id="e9928-104">Элемент конфигурации (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс элемент (Format) Енумерабликспансион элемент (Format) Ентриселектедби элемент для енумерабликспансион (Format) SelectionCondition для EntrySelectedBy Енумерабликспансион (формат)</span><span class="sxs-lookup"><span data-stu-id="e9928-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e9928-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e9928-105">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e9928-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e9928-106">Attributes and Elements</span></span>

<span data-ttu-id="e9928-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `SelectionCondition`.</span><span class="sxs-lookup"><span data-stu-id="e9928-107">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span> <span data-ttu-id="e9928-108">Необходимо указать один элемент `PropertyName` или `ScriptBlock`.</span><span class="sxs-lookup"><span data-stu-id="e9928-108">You must specify a single `PropertyName` or `ScriptBlock` element.</span></span> <span data-ttu-id="e9928-109">Элементы `SelectionSetName` и `TypeName` необязательны.</span><span class="sxs-lookup"><span data-stu-id="e9928-109">The `SelectionSetName` and `TypeName` elements are optional.</span></span> <span data-ttu-id="e9928-110">Можно указать один из этих элементов.</span><span class="sxs-lookup"><span data-stu-id="e9928-110">You can specify one of either element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e9928-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e9928-111">Attributes</span></span>

<span data-ttu-id="e9928-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="e9928-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e9928-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e9928-113">Child Elements</span></span>

|<span data-ttu-id="e9928-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="e9928-114">Element</span></span>|<span data-ttu-id="e9928-115">Описание</span><span class="sxs-lookup"><span data-stu-id="e9928-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e9928-116">Элемент PropertyName для Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format)</span><span class="sxs-lookup"><span data-stu-id="e9928-116">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="e9928-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e9928-117">Optional element.</span></span><br /><br /> <span data-ttu-id="e9928-118">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="e9928-118">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="e9928-119">Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format)</span><span class="sxs-lookup"><span data-stu-id="e9928-119">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="e9928-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e9928-120">Optional element.</span></span><br /><br /> <span data-ttu-id="e9928-121">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="e9928-121">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="e9928-122">Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format)</span><span class="sxs-lookup"><span data-stu-id="e9928-122">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="e9928-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e9928-123">Optional element.</span></span><br /><br /> <span data-ttu-id="e9928-124">Указывает набор типов .NET, которые инициируют условие.</span><span class="sxs-lookup"><span data-stu-id="e9928-124">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="e9928-125">Элемент TypeName для Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format)</span><span class="sxs-lookup"><span data-stu-id="e9928-125">TypeName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="e9928-126">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e9928-126">Optional element.</span></span><br /><br /> <span data-ttu-id="e9928-127">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="e9928-127">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e9928-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e9928-128">Parent Elements</span></span>

|<span data-ttu-id="e9928-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="e9928-129">Element</span></span>|<span data-ttu-id="e9928-130">Описание</span><span class="sxs-lookup"><span data-stu-id="e9928-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e9928-131">Элемент Ентриселектедби для Енумерабликспансион (Format)</span><span class="sxs-lookup"><span data-stu-id="e9928-131">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="e9928-132">Определяет, какие объекты коллекции .NET разворачиваются этим определением.</span><span class="sxs-lookup"><span data-stu-id="e9928-132">Defines which .NET collection objects are expanded by this definition.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e9928-133">Замечания</span><span class="sxs-lookup"><span data-stu-id="e9928-133">Remarks</span></span>

<span data-ttu-id="e9928-134">Каждое определение должно иметь по крайней мере одно определенное имя типа, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="e9928-134">Each definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="e9928-135">При определении условия выбора применяются следующие требования.</span><span class="sxs-lookup"><span data-stu-id="e9928-135">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="e9928-136">Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.</span><span class="sxs-lookup"><span data-stu-id="e9928-136">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="e9928-137">Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.</span><span class="sxs-lookup"><span data-stu-id="e9928-137">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="e9928-138">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для воспроизведения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="e9928-138">For more information about how to use selection conditions, see [Defining Conditions for Diplaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="e9928-139">Дополнительные сведения о других компонентах расширенного представления см. в разделе [широкие представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="e9928-139">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e9928-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="e9928-140">See Also</span></span>

[<span data-ttu-id="e9928-141">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="e9928-141">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="e9928-142">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="e9928-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
