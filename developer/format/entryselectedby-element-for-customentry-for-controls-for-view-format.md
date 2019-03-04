---
title: Элемент EntrySelectedBy для CustomEntry для элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3d80a7d-3797-4c46-ae74-ae5cda79b24f
caps.latest.revision: 8
ms.openlocfilehash: efb20c3f2077547e6eb3cb28240512b444f9c481
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859540"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-view-format"></a><span data-ttu-id="a7077-102">Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="a7077-102">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>

<span data-ttu-id="a7077-103">Определяет типы .NET, которые используют это определение элемента управления или условие, которое должен существовать для данного определения для использования.</span><span class="sxs-lookup"><span data-stu-id="a7077-103">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="a7077-104">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="a7077-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="a7077-105">Конфигурации элемента (формат) элемент ViewDefinitions (формат) представление элемента (формат) элементы управления элемента (формат) элемент управления для элементов управления для элемента представления (формат) пользовательский элемент управления для элемента управления для элементов управления для элемента CustomEntries представления (формат) для Пользовательский элемент управления для элементов управления для элемента представления (формат) CustomEntry для CustomEntries для элементов управления для элемента представления (формат) EntrySelectedBy для CustomEntry для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="a7077-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a7077-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a7077-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a7077-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a7077-107">Attributes and Elements</span></span>

<span data-ttu-id="a7077-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `EntrySelectedBy` элемент.</span><span class="sxs-lookup"><span data-stu-id="a7077-108">The following sections describe attributes, child elements, and parent element of the `EntrySelectedBy` element.</span></span> <span data-ttu-id="a7077-109">Необходимо указать по крайней мере один тип, выбора или условию выбора для определения.</span><span class="sxs-lookup"><span data-stu-id="a7077-109">You must specify at least one type, selection set, or selection condition for a definition.</span></span> <span data-ttu-id="a7077-110">Не ограничено максимальное число дочерних элементов, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="a7077-110">There is no maximum limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="a7077-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a7077-111">Attributes</span></span>

<span data-ttu-id="a7077-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="a7077-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a7077-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a7077-113">Child Elements</span></span>

|<span data-ttu-id="a7077-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="a7077-114">Element</span></span>|<span data-ttu-id="a7077-115">Описание</span><span class="sxs-lookup"><span data-stu-id="a7077-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a7077-116">Элемент SelectionCondition для EntrySelectedBy для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="a7077-116">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="a7077-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="a7077-117">Optional element.</span></span><br /><br /> <span data-ttu-id="a7077-118">Определяет условие, которое должен существовать для данного определения для использования.</span><span class="sxs-lookup"><span data-stu-id="a7077-118">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="a7077-119">Элемент SelectionSetName для EntrySelectedBy для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="a7077-119">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="a7077-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="a7077-120">Optional element.</span></span><br /><br /> <span data-ttu-id="a7077-121">Задает набор типов .NET, которые используют это определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a7077-121">Specifies a set of .NET types that use this definition of the control.</span></span>|
|[<span data-ttu-id="a7077-122">TypeName-элемент для EntrySelectedBy для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="a7077-122">TypeName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./typename-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="a7077-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="a7077-123">Optional element.</span></span><br /><br /> <span data-ttu-id="a7077-124">Указывает тип .NET, который использует это определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a7077-124">Specifies a .NET type that uses this definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a7077-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a7077-125">Parent Elements</span></span>

|<span data-ttu-id="a7077-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="a7077-126">Element</span></span>|<span data-ttu-id="a7077-127">Описание</span><span class="sxs-lookup"><span data-stu-id="a7077-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a7077-128">Элемент CustomEntry для CustomEntries для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="a7077-128">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="a7077-129">Предоставляет определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a7077-129">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a7077-130">Замечания</span><span class="sxs-lookup"><span data-stu-id="a7077-130">Remarks</span></span>

<span data-ttu-id="a7077-131">Выбор условия используются для определения условия, которое должен существовать для определения используемого, например если объект имеет определенное свойство или когда значения конкретного свойства или скрипта, результатом которого является `true`.</span><span class="sxs-lookup"><span data-stu-id="a7077-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="a7077-132">Дополнительные сведения об условиях выделения, см. в разделе [определение условий для, когда операция отчета или элемента используется](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="a7077-132">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a7077-133">См. также</span><span class="sxs-lookup"><span data-stu-id="a7077-133">See Also</span></span>

[<span data-ttu-id="a7077-134">Элемент CustomEntry для CustomEntries для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="a7077-134">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="a7077-135">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="a7077-135">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
