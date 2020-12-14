---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableRowEntry (формат)
description: Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableRowEntry (формат)
ms.openlocfilehash: dcb59fc438ae217870566f09204fb16b8f031614
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665793"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format"></a><span data-ttu-id="8e1d4-103">Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="8e1d4-103">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

<span data-ttu-id="8e1d4-104">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="8e1d4-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="8e1d4-105">Если это свойство имеется или если оно имеет значение `true` , условие выполняется и используется запись таблицы.</span><span class="sxs-lookup"><span data-stu-id="8e1d4-105">When this property is present or when it evaluates to `true`, the condition is met, and the table entry is used.</span></span>

<span data-ttu-id="8e1d4-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Ентриселектедби для таблеровентри (Format) SelectionCondition для EntrySelectedBy в TableRowEntry для SelectionCondition в EntrySelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="8e1d4-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8e1d4-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8e1d4-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8e1d4-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8e1d4-108">Attributes and Elements</span></span>

<span data-ttu-id="8e1d4-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.</span><span class="sxs-lookup"><span data-stu-id="8e1d4-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8e1d4-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8e1d4-110">Attributes</span></span>

<span data-ttu-id="8e1d4-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8e1d4-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8e1d4-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8e1d4-112">Child Elements</span></span>

<span data-ttu-id="8e1d4-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8e1d4-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8e1d4-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8e1d4-114">Parent Elements</span></span>

|<span data-ttu-id="8e1d4-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="8e1d4-115">Element</span></span>|<span data-ttu-id="8e1d4-116">Описание</span><span class="sxs-lookup"><span data-stu-id="8e1d4-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8e1d4-117">Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="8e1d4-117">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="8e1d4-118">Определяет условие, которое должно существовать для использования этой записи таблицы.</span><span class="sxs-lookup"><span data-stu-id="8e1d4-118">Defines the condition that must exist for this table entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="8e1d4-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="8e1d4-119">Text Value</span></span>

<span data-ttu-id="8e1d4-120">Укажите имя свойства .NET.</span><span class="sxs-lookup"><span data-stu-id="8e1d4-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="8e1d4-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="8e1d4-121">Remarks</span></span>

<span data-ttu-id="8e1d4-122">Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="8e1d4-122">The selection condition must specify at least one property name or a script block, but cannot specify both.</span></span> <span data-ttu-id="8e1d4-123">Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="8e1d4-123">For more information about how selection conditions can be used, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="8e1d4-124">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="8e1d4-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8e1d4-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="8e1d4-125">See Also</span></span>

[<span data-ttu-id="8e1d4-126">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="8e1d4-126">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="8e1d4-127">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="8e1d4-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="8e1d4-128">Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="8e1d4-128">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="8e1d4-129">Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="8e1d4-129">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="8e1d4-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e1d4-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
