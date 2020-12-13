---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент SelectionSetName для элемента SelectionCondition для элемента CustomControl для элемента View (формат)
description: Элемент SelectionSetName для элемента SelectionCondition для элемента CustomControl для элемента View (формат)
ms.openlocfilehash: 839032048739e529057d7066fb3bc6aa2fbc5037
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651615"
---
# <a name="selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="ba2ec-103">Элемент SelectionSetName для элемента SelectionCondition для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="ba2ec-103">SelectionSetName Element for SelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="ba2ec-104">Указывает набор типов .NET, которые активируют условие.</span><span class="sxs-lookup"><span data-stu-id="ba2ec-104">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="ba2ec-105">При наличии любого из типов в этом наборе условие выполняется, и объект отображается с помощью этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ba2ec-105">When any of the types in this set are present, the condition is met and the object is displayed using this control.</span></span> <span data-ttu-id="ba2ec-106">Этот элемент используется при определении пользовательского представления элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ba2ec-106">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="ba2ec-107">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ошибка customcontrol элемент (Format) Кустоментриес для ошибка customcontrol в элементе кустоментри для представления кустоментриес для ентриселектедби для представления (формат).</span><span class="sxs-lookup"><span data-stu-id="ba2ec-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ba2ec-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba2ec-108">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ba2ec-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ba2ec-109">Attributes and Elements</span></span>

<span data-ttu-id="ba2ec-110">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемента.</span><span class="sxs-lookup"><span data-stu-id="ba2ec-110">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ba2ec-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ba2ec-111">Attributes</span></span>

<span data-ttu-id="ba2ec-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ba2ec-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ba2ec-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ba2ec-113">Child Elements</span></span>

<span data-ttu-id="ba2ec-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ba2ec-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ba2ec-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ba2ec-115">Parent Elements</span></span>

|<span data-ttu-id="ba2ec-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="ba2ec-116">Element</span></span>|<span data-ttu-id="ba2ec-117">Описание</span><span class="sxs-lookup"><span data-stu-id="ba2ec-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ba2ec-118">Элемент Селектионкондитион для Ентриселектедби для ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="ba2ec-118">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="ba2ec-119">Определяет условие, которое должно существовать для использования определения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ba2ec-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ba2ec-120">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="ba2ec-120">Text Value</span></span>

<span data-ttu-id="ba2ec-121">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="ba2ec-121">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="ba2ec-122">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ba2ec-122">Remarks</span></span>

<span data-ttu-id="ba2ec-123">Наборы выбора — это распространенные группы объектов .NET, которые могут использоваться любым представлением, определяемым файлом форматирования.</span><span class="sxs-lookup"><span data-stu-id="ba2ec-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="ba2ec-124">Дополнительные сведения о создании и ссылке на наборы выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="ba2ec-124">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="ba2ec-125">Условие выбора может указывать набор выбора или тип .NET, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="ba2ec-125">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="ba2ec-126">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="ba2ec-126">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ba2ec-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="ba2ec-127">See Also</span></span>

[<span data-ttu-id="ba2ec-128">Элемент Селектионкондитион для Ентриселектедби для ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="ba2ec-128">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="ba2ec-129">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="ba2ec-129">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="ba2ec-130">Определение наборов выделенных фрагментов</span><span class="sxs-lookup"><span data-stu-id="ba2ec-130">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="ba2ec-131">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="ba2ec-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
