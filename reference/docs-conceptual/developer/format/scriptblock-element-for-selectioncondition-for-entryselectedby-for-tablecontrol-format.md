---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)
description: Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)
ms.openlocfilehash: a984bda6b8fba3a5cb9485576ffd847f0d366d3e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659882"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="b3159-103">Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="b3159-103">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="b3159-104">Указывает блок скрипта, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="b3159-104">Specifies the script block that triggers the condition.</span></span> <span data-ttu-id="b3159-105">При вычислении этого скрипта `true` выполняется условие, и используется запись в таблице.</span><span class="sxs-lookup"><span data-stu-id="b3159-105">When this script is evaluated to `true`, the condition is met, and the table entry is used.</span></span>

<span data-ttu-id="b3159-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Ентриселектедби для Таблеровентри (Format) SelectionCondition для EntrySelectedBy в TableRowEntry для SelectionCondition в EntrySelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="b3159-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b3159-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3159-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b3159-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b3159-108">Attributes and Elements</span></span>

<span data-ttu-id="b3159-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемента.</span><span class="sxs-lookup"><span data-stu-id="b3159-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b3159-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b3159-110">Attributes</span></span>

<span data-ttu-id="b3159-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b3159-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b3159-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b3159-112">Child Elements</span></span>

<span data-ttu-id="b3159-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b3159-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b3159-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b3159-114">Parent Elements</span></span>

|<span data-ttu-id="b3159-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="b3159-115">Element</span></span>|<span data-ttu-id="b3159-116">Описание</span><span class="sxs-lookup"><span data-stu-id="b3159-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b3159-117">Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="b3159-117">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="b3159-118">Определяет условие, которое должно существовать для использования этой записи таблицы.</span><span class="sxs-lookup"><span data-stu-id="b3159-118">Defines the condition that must exist for this table entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b3159-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="b3159-119">Text Value</span></span>

<span data-ttu-id="b3159-120">Укажите оцениваемый скрипт.</span><span class="sxs-lookup"><span data-stu-id="b3159-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="b3159-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="b3159-121">Remarks</span></span>

<span data-ttu-id="b3159-122">Условие выбора должно указывать по крайней мере один блок скрипта или имя свойства, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="b3159-122">The selection condition must specify at least one script block or property name, but cannot specify both.</span></span> <span data-ttu-id="b3159-123">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="b3159-123">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="b3159-124">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="b3159-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b3159-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="b3159-125">See Also</span></span>

[<span data-ttu-id="b3159-126">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="b3159-126">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="b3159-127">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="b3159-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="b3159-128">Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="b3159-128">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[<span data-ttu-id="b3159-129">Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="b3159-129">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="b3159-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3159-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
