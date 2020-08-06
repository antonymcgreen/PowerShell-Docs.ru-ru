---
title: Элемент Селектионсетнаме для Селектионкондитион элементов управления для представления (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 0feb23f860487952344680f75ee674e9e0e6dcc6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787535"
---
# <a name="selectionsetname-element-for-selectioncondition-for-controls-for-view-format"></a><span data-ttu-id="b7204-102">Элемент SelectionSetName для элемента SelectionCondition для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="b7204-102">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="b7204-103">Указывает набор типов .NET, которые активируют условие.</span><span class="sxs-lookup"><span data-stu-id="b7204-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="b7204-104">При наличии любого из типов в этом наборе условие выполняется, и объект отображается с помощью этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b7204-104">When any of the types in this set are present, the condition is met and the object is displayed using this control.</span></span> <span data-ttu-id="b7204-105">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="b7204-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="b7204-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет элементом управления "элемент (Format)" для элементов управления для элемента "View" (Format) ошибка customcontrol для элемента управления, для которого элемент Control элемента (Format) Кустоментри элемент для Кустоментриес для элементов управления элемента Ентриселектедби представления (Format) для Кустоментри для элементов управления для элемента "View" (формат) SelectionCondition для EntrySelectedBy для элементов управления представления (Format) SelectionSetName для SelectionCondition для элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="b7204-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format) SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b7204-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b7204-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b7204-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b7204-108">Attributes and Elements</span></span>

<span data-ttu-id="b7204-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемента.</span><span class="sxs-lookup"><span data-stu-id="b7204-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b7204-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b7204-110">Attributes</span></span>

<span data-ttu-id="b7204-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b7204-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b7204-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b7204-112">Child Elements</span></span>

<span data-ttu-id="b7204-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b7204-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b7204-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b7204-114">Parent Elements</span></span>

|<span data-ttu-id="b7204-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="b7204-115">Element</span></span>|<span data-ttu-id="b7204-116">Описание</span><span class="sxs-lookup"><span data-stu-id="b7204-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b7204-117">Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="b7204-117">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="b7204-118">Определяет условие, которое должно существовать для использования определения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b7204-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b7204-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="b7204-119">Text Value</span></span>

<span data-ttu-id="b7204-120">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="b7204-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="b7204-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="b7204-121">Remarks</span></span>

<span data-ttu-id="b7204-122">Наборы выбора — это распространенные группы объектов .NET, которые могут использоваться любым представлением, определяемым файлом форматирования.</span><span class="sxs-lookup"><span data-stu-id="b7204-122">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="b7204-123">Дополнительные сведения о создании и ссылке на наборы выбора см. в разделе [Определение наборов выбора](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="b7204-123">For more information about creating and referencing selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="b7204-124">Условие выбора может указывать набор выбора или тип .NET, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="b7204-124">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="b7204-125">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="b7204-125">For more information about how to use selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b7204-126">См. также</span><span class="sxs-lookup"><span data-stu-id="b7204-126">See Also</span></span>

[<span data-ttu-id="b7204-127">Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="b7204-127">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[<span data-ttu-id="b7204-128">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="b7204-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="b7204-129">Определение наборов выделенных фрагментов</span><span class="sxs-lookup"><span data-stu-id="b7204-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="b7204-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7204-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
