---
ms.date: 09/13/2016
ms.topic: reference
title: Определение условий для отображения данных
description: Определение условий для отображения данных
ms.openlocfilehash: 9a8b7a618da8c64de978c13b527435a2d7793677
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660322"
---
# <a name="defining-conditions-for-displaying-data"></a><span data-ttu-id="c73a3-103">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="c73a3-103">Defining Conditions for Displaying Data</span></span>

<span data-ttu-id="c73a3-104">При определении данных, отображаемых представлением или элементом управления, можно указать условие, которое должно существовать для отображения данных.</span><span class="sxs-lookup"><span data-stu-id="c73a3-104">When defining what data is displayed by a view or a control, you can specify a condition that must exist for the data to be displayed.</span></span> <span data-ttu-id="c73a3-105">Условие может быть активировано конкретным свойством, или если значение скрипта или свойства равно `true` .</span><span class="sxs-lookup"><span data-stu-id="c73a3-105">The condition can be triggered by a specific property, or when a script or property value evaluates to `true`.</span></span> <span data-ttu-id="c73a3-106">При выполнении условия выбора используется определение представления или элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c73a3-106">When the selection condition is met, the definition of the view or control is used.</span></span>

## <a name="specifying-a-selection-condition-for-a-definition"></a><span data-ttu-id="c73a3-107">Указание условия выбора для определения</span><span class="sxs-lookup"><span data-stu-id="c73a3-107">Specifying a Selection Condition for a Definition</span></span>

<span data-ttu-id="c73a3-108">При создании определения для представления или элемента управления `EntrySelectedBy` элемент используется для указания объектов, которые будут использовать определение или какое условие должно существовать для использования определения.</span><span class="sxs-lookup"><span data-stu-id="c73a3-108">When creating a definition for a view or control, the `EntrySelectedBy` element is used to specify which objects will use the definition or what condition must exist for the definition to be used.</span></span> <span data-ttu-id="c73a3-109">Условие задается `SelectionCondition` элементом.</span><span class="sxs-lookup"><span data-stu-id="c73a3-109">The condition is specified by the `SelectionCondition` element.</span></span>

<span data-ttu-id="c73a3-110">В следующем примере условие выбора задается для определения табличного представления.</span><span class="sxs-lookup"><span data-stu-id="c73a3-110">In the following example, a selection condition is specified for a definition of a table view.</span></span> <span data-ttu-id="c73a3-111">В этом примере определение используется только при вычислении указанного скрипта `true` .</span><span class="sxs-lookup"><span data-stu-id="c73a3-111">In this example, the definition is used only when the specified script is evaluated to `true`.</span></span>

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <SelectionCondition>
      <ScriptBlock>ScriptToEvaluate</ScriptBlock>
    </SelectionCondition>
  </EntrySelectedBy>
  <TableColumnItems>
  </TableColumnItems>
</TableRowEntry>

```

<span data-ttu-id="c73a3-112">Количество условий выбора, которое можно указать для определения представления или элемента управления, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="c73a3-112">There is no limit to the number of selection conditions that you can specify for a definition of a view or control.</span></span> <span data-ttu-id="c73a3-113">Существуют следующие требования:</span><span class="sxs-lookup"><span data-stu-id="c73a3-113">The only requirements are the following:</span></span>

- <span data-ttu-id="c73a3-114">Условие выбора должно указывать одно имя свойства или скрипт для активации условия, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="c73a3-114">The selection condition must specify one property name or script to trigger the condition, but cannot specify both.</span></span>

- <span data-ttu-id="c73a3-115">Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.</span><span class="sxs-lookup"><span data-stu-id="c73a3-115">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

## <a name="specifying-a-selection-condition-for-an-item"></a><span data-ttu-id="c73a3-116">Указание условия выбора для элемента</span><span class="sxs-lookup"><span data-stu-id="c73a3-116">Specifying a Selection Condition for an Item</span></span>

<span data-ttu-id="c73a3-117">Можно также указать, когда элемент представления списка или элемента управления используется, включив `ItemSelectionCondition` элемент в определение элемента.</span><span class="sxs-lookup"><span data-stu-id="c73a3-117">You can also specify when an item of a list view or control is used by including the `ItemSelectionCondition` element in the item definition.</span></span> <span data-ttu-id="c73a3-118">В следующем примере условие выбора задается для элемента в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="c73a3-118">In the following example, a selection condition is specified for an item of a list view.</span></span> <span data-ttu-id="c73a3-119">В этом примере элемент используется только при вычислении скрипта `true` .</span><span class="sxs-lookup"><span data-stu-id="c73a3-119">In this example, the item is used only when the script is evaluated to `true`.</span></span>

```xml
<ListItem>
  <ItemSelectionCondition>
    <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  </ItemSelectionCondition>
</ListItem>

```

<span data-ttu-id="c73a3-120">Для элемента можно указать только одно условие выбора.</span><span class="sxs-lookup"><span data-stu-id="c73a3-120">You can specify only one selection condition for an item.</span></span> <span data-ttu-id="c73a3-121">И условие должно указывать одно имя свойства или скрипт для запуска условия, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="c73a3-121">And the condition must specify one property name or script to trigger the condition, but cannot specify both.</span></span>

## <a name="xml-elements"></a><span data-ttu-id="c73a3-122">Элементы XML</span><span class="sxs-lookup"><span data-stu-id="c73a3-122">XML Elements</span></span>

 <span data-ttu-id="c73a3-123">Для создания условия выбора используются следующие XML-элементы.</span><span class="sxs-lookup"><span data-stu-id="c73a3-123">The following XML elements are used to create a selection condition.</span></span>

- <span data-ttu-id="c73a3-124">Следующие элементы указывают условия выбора для определений представлений:</span><span class="sxs-lookup"><span data-stu-id="c73a3-124">The following elements specify selection conditions for view definitions:</span></span>

  - [<span data-ttu-id="c73a3-125">Элемент SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="c73a3-125">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

  - [<span data-ttu-id="c73a3-126">Элемент SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="c73a3-126">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

  - [<span data-ttu-id="c73a3-127">Элемент SelectionCondition для элемента EntrySelectedBy для элемента WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="c73a3-127">SelectionCondition Element for EntrySelectedBy for WideControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

  - [<span data-ttu-id="c73a3-128">Элемент SelectionCondition для элемента EntrySelectedBy для элемента CustomControl (формат)</span><span class="sxs-lookup"><span data-stu-id="c73a3-128">SelectionCondition Element for EntrySelectedBy for CustomControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

- <span data-ttu-id="c73a3-129">Следующие элементы указывают условия выбора для типовых определений и определения элементов управления.</span><span class="sxs-lookup"><span data-stu-id="c73a3-129">The following elements specify selection conditions for common and view control definitions:</span></span>

  - [<span data-ttu-id="c73a3-130">Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="c73a3-130">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

  - [<span data-ttu-id="c73a3-131">Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="c73a3-131">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

- <span data-ttu-id="c73a3-132">Следующий элемент задает условие выбора для расширения объектов коллекции:</span><span class="sxs-lookup"><span data-stu-id="c73a3-132">The following element specifies the selection condition for expanding collection objects:</span></span>

  - [<span data-ttu-id="c73a3-133">Элемент SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="c73a3-133">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

- <span data-ttu-id="c73a3-134">Следующий элемент задает условие выбора для отображения новой группы данных:</span><span class="sxs-lookup"><span data-stu-id="c73a3-134">The following element specifies the selection condition for displaying a new group of data:</span></span>

  - [<span data-ttu-id="c73a3-135">Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="c73a3-135">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

- <span data-ttu-id="c73a3-136">Следующий элемент задает условие выбора элемента для представления списка:</span><span class="sxs-lookup"><span data-stu-id="c73a3-136">The following element specifies an item selection condition for a list view:</span></span>

  - [<span data-ttu-id="c73a3-137">Элемент ItemSelectionCondition для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="c73a3-137">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

- <span data-ttu-id="c73a3-138">Следующие элементы определяют условие выбора элемента для элементов управления:</span><span class="sxs-lookup"><span data-stu-id="c73a3-138">The following elements specify an item selection condition for controls:</span></span>

  - [<span data-ttu-id="c73a3-139">Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="c73a3-139">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

  - [<span data-ttu-id="c73a3-140">Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="c73a3-140">ItemSelectionCondition Element for ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

  - [<span data-ttu-id="c73a3-141">Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента CustomControl (формат)</span><span class="sxs-lookup"><span data-stu-id="c73a3-141">ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

## <a name="see-also"></a><span data-ttu-id="c73a3-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="c73a3-142">See Also</span></span>

[<span data-ttu-id="c73a3-143">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="c73a3-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
