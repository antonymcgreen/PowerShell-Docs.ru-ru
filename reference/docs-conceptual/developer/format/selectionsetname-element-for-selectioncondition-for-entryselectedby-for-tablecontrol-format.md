---
title: Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Таблеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17ae4d6b-dc95-4a1d-8e32-31ff084a951f
caps.latest.revision: 10
ms.openlocfilehash: edb163f2b0b5129bd741677dce882888d9bbfd89
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361923"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="22c62-102">Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="22c62-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="22c62-103">Указывает набор типов .NET, которые активируют условие.</span><span class="sxs-lookup"><span data-stu-id="22c62-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="22c62-104">При наличии любого из типов в этом наборе условие выполняется, и объект отображается с помощью этого определения табличного представления.</span><span class="sxs-lookup"><span data-stu-id="22c62-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this definition of the table view.</span></span>

<span data-ttu-id="22c62-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Ентриселектедби для Таблеровентри (Format) Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format) Селектионсетнаме элемента для Селектионкондитион для EntrySelectedBy в TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="22c62-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="22c62-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22c62-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="22c62-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="22c62-107">Attributes and Elements</span></span>

<span data-ttu-id="22c62-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `SelectionSetName`.</span><span class="sxs-lookup"><span data-stu-id="22c62-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="22c62-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="22c62-109">Attributes</span></span>

<span data-ttu-id="22c62-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="22c62-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="22c62-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="22c62-111">Child Elements</span></span>

<span data-ttu-id="22c62-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="22c62-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="22c62-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="22c62-113">Parent Elements</span></span>

|<span data-ttu-id="22c62-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="22c62-114">Element</span></span>|<span data-ttu-id="22c62-115">Описание</span><span class="sxs-lookup"><span data-stu-id="22c62-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="22c62-116">Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="22c62-116">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="22c62-117">Определяет условие, которое должно существовать для использования в этом определении табличного представления.</span><span class="sxs-lookup"><span data-stu-id="22c62-117">Defines the condition that must exist to use for this definition of the table view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="22c62-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="22c62-118">Text Value</span></span>

<span data-ttu-id="22c62-119">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="22c62-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="22c62-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="22c62-120">Remarks</span></span>

<span data-ttu-id="22c62-121">Условие выбора может указывать набор выбора или тип .NET, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="22c62-121">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="22c62-122">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="22c62-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="22c62-123">Наборы выбора — это распространенные группы объектов .NET, которые могут использоваться любым представлением, определяемым файлом форматирования.</span><span class="sxs-lookup"><span data-stu-id="22c62-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="22c62-124">Дополнительные сведения о создании и ссылке на наборы выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="22c62-124">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="22c62-125">Дополнительные сведения о других компонентах расширенного представления см. [в разделе Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="22c62-125">For more information about other components of a wide view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="22c62-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="22c62-126">See Also</span></span>

[<span data-ttu-id="22c62-127">Создание табличного представления</span><span class="sxs-lookup"><span data-stu-id="22c62-127">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="22c62-128">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="22c62-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="22c62-129">Элемент TypeName для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="22c62-129">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="22c62-130">Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="22c62-130">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="22c62-131">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="22c62-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
