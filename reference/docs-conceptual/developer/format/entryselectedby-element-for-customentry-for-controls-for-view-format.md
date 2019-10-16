---
title: Элемент Ентриселектедби для Кустоментри элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3d80a7d-3797-4c46-ae74-ae5cda79b24f
caps.latest.revision: 8
ms.openlocfilehash: efb20c3f2077547e6eb3cb28240512b444f9c481
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363893"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-view-format"></a><span data-ttu-id="a689b-102">Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="a689b-102">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>

<span data-ttu-id="a689b-103">Определяет типы .NET, которые используют это определение элемента управления или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="a689b-103">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="a689b-104">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="a689b-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="a689b-105">Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет управляющий элемент (Format) элемент управления для элементов управления представления (Format) ошибка customcontrol для элементов управления элемента Кустоментриес представления (Format) для Ошибка customcontrol для элементов управления для элемента Кустоментри представления (Format) для Кустоментриес для элементов управления для представления (Format) Ентриселектедби для Кустоментри для элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="a689b-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a689b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a689b-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a689b-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a689b-107">Attributes and Elements</span></span>

<span data-ttu-id="a689b-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `EntrySelectedBy`.</span><span class="sxs-lookup"><span data-stu-id="a689b-108">The following sections describe attributes, child elements, and parent element of the `EntrySelectedBy` element.</span></span> <span data-ttu-id="a689b-109">Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения.</span><span class="sxs-lookup"><span data-stu-id="a689b-109">You must specify at least one type, selection set, or selection condition for a definition.</span></span> <span data-ttu-id="a689b-110">Максимальное количество дочерних элементов, которое можно использовать, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="a689b-110">There is no maximum limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="a689b-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a689b-111">Attributes</span></span>

<span data-ttu-id="a689b-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="a689b-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a689b-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a689b-113">Child Elements</span></span>

|<span data-ttu-id="a689b-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="a689b-114">Element</span></span>|<span data-ttu-id="a689b-115">Описание</span><span class="sxs-lookup"><span data-stu-id="a689b-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a689b-116">Элемент Селектионкондитион для Ентриселектедби элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="a689b-116">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="a689b-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="a689b-117">Optional element.</span></span><br /><br /> <span data-ttu-id="a689b-118">Определяет условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="a689b-118">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="a689b-119">Элемент Селектионсетнаме для Ентриселектедби элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="a689b-119">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="a689b-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="a689b-120">Optional element.</span></span><br /><br /> <span data-ttu-id="a689b-121">Задает набор типов .NET, использующих это определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a689b-121">Specifies a set of .NET types that use this definition of the control.</span></span>|
|[<span data-ttu-id="a689b-122">Элемент TypeName для Ентриселектедби элементов управления для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="a689b-122">TypeName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./typename-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="a689b-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="a689b-123">Optional element.</span></span><br /><br /> <span data-ttu-id="a689b-124">Указывает тип .NET, который использует это определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a689b-124">Specifies a .NET type that uses this definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a689b-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a689b-125">Parent Elements</span></span>

|<span data-ttu-id="a689b-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="a689b-126">Element</span></span>|<span data-ttu-id="a689b-127">Описание</span><span class="sxs-lookup"><span data-stu-id="a689b-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a689b-128">Элемент Кустоментри для Кустоментриес элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="a689b-128">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="a689b-129">Предоставляет определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a689b-129">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a689b-130">Замечания</span><span class="sxs-lookup"><span data-stu-id="a689b-130">Remarks</span></span>

<span data-ttu-id="a689b-131">Условия выбора используются для определения условия, которое должно существовать для использования определения, например, если у объекта есть определенное свойство или если определенное значение или скрипт свойства имеют `true`.</span><span class="sxs-lookup"><span data-stu-id="a689b-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="a689b-132">Дополнительные сведения об условиях выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="a689b-132">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a689b-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="a689b-133">See Also</span></span>

[<span data-ttu-id="a689b-134">Элемент Кустоментри для Кустоментриес элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="a689b-134">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="a689b-135">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="a689b-135">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
