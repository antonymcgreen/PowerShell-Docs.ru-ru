---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент TypeName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)
description: Элемент TypeName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)
ms.openlocfilehash: 66e90ab33775cf35d5e98e45266996d2d1a622d7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659630"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="2a0fc-103">Элемент TypeName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="2a0fc-103">TypeName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="2a0fc-104">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="2a0fc-104">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="2a0fc-105">При наличии этого типа условие выполняется, и используется строка таблицы.</span><span class="sxs-lookup"><span data-stu-id="2a0fc-105">When this type is present, the condition is met, and the table row is used.</span></span>

<span data-ttu-id="2a0fc-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Ентриселектедби для таблеровентри (Format) SelectionCondition для EntrySelectedBy в TableRowEntry для SelectionCondition (Format).</span><span class="sxs-lookup"><span data-stu-id="2a0fc-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2a0fc-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a0fc-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2a0fc-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2a0fc-108">Attributes and Elements</span></span>

<span data-ttu-id="2a0fc-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TypeName` элемента.</span><span class="sxs-lookup"><span data-stu-id="2a0fc-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2a0fc-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2a0fc-110">Attributes</span></span>

<span data-ttu-id="2a0fc-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2a0fc-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2a0fc-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2a0fc-112">Child Elements</span></span>

<span data-ttu-id="2a0fc-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2a0fc-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2a0fc-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2a0fc-114">Parent Elements</span></span>

|<span data-ttu-id="2a0fc-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="2a0fc-115">Element</span></span>|<span data-ttu-id="2a0fc-116">Описание</span><span class="sxs-lookup"><span data-stu-id="2a0fc-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2a0fc-117">Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="2a0fc-117">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="2a0fc-118">Определяет условие, которое должно существовать для использования этой строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="2a0fc-118">Defines the condition that must exist for this table row to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2a0fc-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="2a0fc-119">Text Value</span></span>

<span data-ttu-id="2a0fc-120">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="2a0fc-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2a0fc-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="2a0fc-121">Remarks</span></span>

<span data-ttu-id="2a0fc-122">Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.</span><span class="sxs-lookup"><span data-stu-id="2a0fc-122">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span> <span data-ttu-id="2a0fc-123">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="2a0fc-123">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="2a0fc-124">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="2a0fc-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2a0fc-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="2a0fc-125">See Also</span></span>

[<span data-ttu-id="2a0fc-126">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="2a0fc-126">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="2a0fc-127">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="2a0fc-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="2a0fc-128">Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="2a0fc-128">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="2a0fc-129">Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="2a0fc-129">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="2a0fc-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="2a0fc-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
