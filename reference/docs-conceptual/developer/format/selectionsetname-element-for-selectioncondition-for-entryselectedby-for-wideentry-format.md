---
title: Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Видинтри (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a13a429c-a31b-4e29-828c-c0c0917b5415
caps.latest.revision: 11
ms.openlocfilehash: baea89e4b259611dfa45b6bcf94fa0bf2df6b9de
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368413"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="0f61e-102">Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="0f61e-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="0f61e-103">Указывает набор типов .NET, которые активируют условие.</span><span class="sxs-lookup"><span data-stu-id="0f61e-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="0f61e-104">При наличии любого из типов в этом наборе условие выполняется, и объект отображается с помощью этого определения расширенного представления.</span><span class="sxs-lookup"><span data-stu-id="0f61e-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this definition of the wide view.</span></span>

<span data-ttu-id="0f61e-105">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Ентриселектедби для Видинтри (Format) Селектионкондитион элемент для Ентриселектедби для Видинтри (Format) Селектионсетнаме для Селектионкондитион для Ентриселектедби в Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="0f61e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0f61e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f61e-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0f61e-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0f61e-107">Attributes and Elements</span></span>

<span data-ttu-id="0f61e-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `SelectionSetName`.</span><span class="sxs-lookup"><span data-stu-id="0f61e-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0f61e-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0f61e-109">Attributes</span></span>

<span data-ttu-id="0f61e-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="0f61e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0f61e-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0f61e-111">Child Elements</span></span>

<span data-ttu-id="0f61e-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="0f61e-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0f61e-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0f61e-113">Parent Elements</span></span>

|<span data-ttu-id="0f61e-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="0f61e-114">Element</span></span>|<span data-ttu-id="0f61e-115">Описание</span><span class="sxs-lookup"><span data-stu-id="0f61e-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0f61e-116">Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="0f61e-116">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="0f61e-117">Определяет условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="0f61e-117">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="0f61e-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="0f61e-118">Text Value</span></span>

<span data-ttu-id="0f61e-119">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="0f61e-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="0f61e-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="0f61e-120">Remarks</span></span>

<span data-ttu-id="0f61e-121">Условие выбора может указывать набор выбора или тип .NET, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="0f61e-121">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="0f61e-122">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="0f61e-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="0f61e-123">Наборы выбора — это распространенные группы объектов .NET, которые могут использоваться любым представлением, определяемым файлом форматирования.</span><span class="sxs-lookup"><span data-stu-id="0f61e-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="0f61e-124">Дополнительные сведения о создании и ссылке на наборы выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="0f61e-124">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="0f61e-125">Дополнительные сведения о других компонентах расширенного представления см. [в разделе Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="0f61e-125">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0f61e-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="0f61e-126">See Also</span></span>

[<span data-ttu-id="0f61e-127">Создание расширенного представления</span><span class="sxs-lookup"><span data-stu-id="0f61e-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="0f61e-128">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="0f61e-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="0f61e-129">Определение наборов выбора</span><span class="sxs-lookup"><span data-stu-id="0f61e-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="0f61e-130">Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="0f61e-130">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="0f61e-131">Элемент TypeName для Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="0f61e-131">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="0f61e-132">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f61e-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
