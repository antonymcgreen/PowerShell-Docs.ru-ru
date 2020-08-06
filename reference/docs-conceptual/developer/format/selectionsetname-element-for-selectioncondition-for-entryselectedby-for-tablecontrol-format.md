---
title: Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Таблеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: db751c40b22db52985bc7cd9f8f4296a64a523f0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787467"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="92c7f-102">Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="92c7f-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="92c7f-103">Указывает набор типов .NET, которые активируют условие.</span><span class="sxs-lookup"><span data-stu-id="92c7f-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="92c7f-104">При наличии любого из типов в этом наборе условие выполняется, и объект отображается с помощью этого определения табличного представления.</span><span class="sxs-lookup"><span data-stu-id="92c7f-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this definition of the table view.</span></span>

<span data-ttu-id="92c7f-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Ентриселектедби для таблеровентри (Format) SelectionCondition для EntrySelectedBy для TableRowEntry в SelectionSetName для SelectionCondition (формат)</span><span class="sxs-lookup"><span data-stu-id="92c7f-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="92c7f-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="92c7f-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="92c7f-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="92c7f-107">Attributes and Elements</span></span>

<span data-ttu-id="92c7f-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемента.</span><span class="sxs-lookup"><span data-stu-id="92c7f-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="92c7f-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="92c7f-109">Attributes</span></span>

<span data-ttu-id="92c7f-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="92c7f-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="92c7f-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="92c7f-111">Child Elements</span></span>

<span data-ttu-id="92c7f-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="92c7f-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="92c7f-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="92c7f-113">Parent Elements</span></span>

|<span data-ttu-id="92c7f-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="92c7f-114">Element</span></span>|<span data-ttu-id="92c7f-115">Описание</span><span class="sxs-lookup"><span data-stu-id="92c7f-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="92c7f-116">Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="92c7f-116">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="92c7f-117">Определяет условие, которое должно существовать для использования в этом определении табличного представления.</span><span class="sxs-lookup"><span data-stu-id="92c7f-117">Defines the condition that must exist to use for this definition of the table view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="92c7f-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="92c7f-118">Text Value</span></span>

<span data-ttu-id="92c7f-119">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="92c7f-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="92c7f-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="92c7f-120">Remarks</span></span>

<span data-ttu-id="92c7f-121">Условие выбора может указывать набор выбора или тип .NET, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="92c7f-121">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="92c7f-122">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="92c7f-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="92c7f-123">Наборы выбора — это распространенные группы объектов .NET, которые могут использоваться любым представлением, определяемым файлом форматирования.</span><span class="sxs-lookup"><span data-stu-id="92c7f-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="92c7f-124">Дополнительные сведения о создании и ссылке на наборы выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="92c7f-124">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="92c7f-125">Дополнительные сведения о других компонентах расширенного представления см. [в разделе Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="92c7f-125">For more information about other components of a wide view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="92c7f-126">См. также</span><span class="sxs-lookup"><span data-stu-id="92c7f-126">See Also</span></span>

[<span data-ttu-id="92c7f-127">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="92c7f-127">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="92c7f-128">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="92c7f-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="92c7f-129">Элемент TypeName для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="92c7f-129">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="92c7f-130">Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="92c7f-130">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="92c7f-131">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="92c7f-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
