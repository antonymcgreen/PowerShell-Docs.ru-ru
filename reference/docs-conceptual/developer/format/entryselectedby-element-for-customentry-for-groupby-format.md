---
title: Элемент Ентриселектедби для Кустоментри для GroupBy (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a317d482-73cc-4c98-a002-1357fa879cd7
caps.latest.revision: 7
ms.openlocfilehash: cf1a80e845c38d97d71f26eba63c38a550958b79
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363863"
---
# <a name="entryselectedby-element-for-customentry-for-groupby-format"></a><span data-ttu-id="02e9a-102">Элемент EntrySelectedBy для элемента CustomEntry для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="02e9a-102">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>

<span data-ttu-id="02e9a-103">Определяет типы .NET, которые используют это определение элемента управления или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="02e9a-103">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="02e9a-104">Этот элемент используется при определении того, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="02e9a-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="02e9a-105">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (формат) элемент GroupBy для элемента Ошибка customcontrol представления (Format) для элемента Кустоментриес (Format) для ошибка customcontrol для элемента GroupBy (Format) Кустоментри для Ошибка customcontrol для элемента Ентриселектедби GroupBy (Format) для Кустоментри для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="02e9a-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="02e9a-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="02e9a-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="02e9a-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="02e9a-107">Attributes and Elements</span></span>

<span data-ttu-id="02e9a-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `EntrySelectedBy`.</span><span class="sxs-lookup"><span data-stu-id="02e9a-108">The following sections describe attributes, child elements, and parent element of the `EntrySelectedBy` element.</span></span> <span data-ttu-id="02e9a-109">Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения.</span><span class="sxs-lookup"><span data-stu-id="02e9a-109">You must specify at least one type, selection set, or selection condition for a definition.</span></span> <span data-ttu-id="02e9a-110">Максимальное количество дочерних элементов, которое можно использовать, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="02e9a-110">There is no maximum limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="02e9a-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="02e9a-111">Attributes</span></span>

<span data-ttu-id="02e9a-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="02e9a-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="02e9a-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="02e9a-113">Child Elements</span></span>

|<span data-ttu-id="02e9a-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="02e9a-114">Element</span></span>|<span data-ttu-id="02e9a-115">Описание</span><span class="sxs-lookup"><span data-stu-id="02e9a-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="02e9a-116">Элемент Селектионкондитион для Ентриселектедби для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="02e9a-116">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="02e9a-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="02e9a-117">Optional element.</span></span><br /><br /> <span data-ttu-id="02e9a-118">Определяет условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="02e9a-118">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="02e9a-119">Элемент Селектионсетнаме для Ентриселектедби для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="02e9a-119">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="02e9a-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="02e9a-120">Optional element.</span></span><br /><br /> <span data-ttu-id="02e9a-121">Задает набор типов .NET, использующих это определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="02e9a-121">Specifies a set of .NET types that use this definition of the control.</span></span>|
|[<span data-ttu-id="02e9a-122">Элемент TypeName для Ентриселектедби для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="02e9a-122">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./typename-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="02e9a-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="02e9a-123">Optional element.</span></span><br /><br /> <span data-ttu-id="02e9a-124">Указывает тип .NET, который использует это определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="02e9a-124">Specifies a .NET type that uses this definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="02e9a-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="02e9a-125">Parent Elements</span></span>

|<span data-ttu-id="02e9a-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="02e9a-126">Element</span></span>|<span data-ttu-id="02e9a-127">Описание</span><span class="sxs-lookup"><span data-stu-id="02e9a-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="02e9a-128">Элемент Кустоментри для ошибка customcontrol для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="02e9a-128">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="02e9a-129">Предоставляет определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="02e9a-129">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="02e9a-130">Замечания</span><span class="sxs-lookup"><span data-stu-id="02e9a-130">Remarks</span></span>

<span data-ttu-id="02e9a-131">Условия выбора используются для определения условия, которое должно существовать для использования определения, например, если у объекта есть определенное свойство или если определенное значение или скрипт свойства имеют `true`.</span><span class="sxs-lookup"><span data-stu-id="02e9a-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="02e9a-132">Дополнительные сведения об условиях выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="02e9a-132">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="02e9a-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="02e9a-133">See Also</span></span>

[<span data-ttu-id="02e9a-134">Элемент Селектионкондитион для Ентриселектедби для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="02e9a-134">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="02e9a-135">Элемент Селектионсетнаме для Ентриселектедби для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="02e9a-135">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="02e9a-136">Элемент TypeName для Ентриселектедби для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="02e9a-136">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./typename-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="02e9a-137">Элемент Кустоментри для Кустоментриес элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="02e9a-137">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="02e9a-138">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="02e9a-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
