---
title: Определение условий для отображения данных | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1e05821-6aec-437b-84a5-218a5727f88b
caps.latest.revision: 10
ms.openlocfilehash: 6036f30816e253b3f0c40c6b916279d0643acdb8
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692487"
---
# <a name="defining-conditions-for-displaying-data"></a><span data-ttu-id="5a3b5-102">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="5a3b5-102">Defining Conditions for Displaying Data</span></span>

<span data-ttu-id="5a3b5-103">При определении данных, отображаемых представлением или элементом управления, можно указать условие, которое должно существовать для отображения данных.</span><span class="sxs-lookup"><span data-stu-id="5a3b5-103">When defining what data is displayed by a view or a control, you can specify a condition that must exist for the data to be displayed.</span></span> <span data-ttu-id="5a3b5-104">Условие может быть активировано конкретным свойством, или если значение скрипта или свойства равно `true` .</span><span class="sxs-lookup"><span data-stu-id="5a3b5-104">The condition can be triggered by a specific property, or when a script or property value evaluates to `true`.</span></span> <span data-ttu-id="5a3b5-105">При выполнении условия выбора используется определение представления или элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5a3b5-105">When the selection condition is met, the definition of the view or control is used.</span></span>

## <a name="specifying-a-selection-condition-for-a-definition"></a><span data-ttu-id="5a3b5-106">Указание условия выбора для определения</span><span class="sxs-lookup"><span data-stu-id="5a3b5-106">Specifying a Selection Condition for a Definition</span></span>

<span data-ttu-id="5a3b5-107">При создании определения для представления или элемента управления `EntrySelectedBy` элемент используется для указания объектов, которые будут использовать определение или какое условие должно существовать для использования определения.</span><span class="sxs-lookup"><span data-stu-id="5a3b5-107">When creating a definition for a view or control, the `EntrySelectedBy` element is used to specify which objects will use the definition or what condition must exist for the definition to be used.</span></span> <span data-ttu-id="5a3b5-108">Условие задается `SelectionCondition` элементом.</span><span class="sxs-lookup"><span data-stu-id="5a3b5-108">The condition is specified by the `SelectionCondition` element.</span></span>

<span data-ttu-id="5a3b5-109">В следующем примере условие выбора задается для определения табличного представления.</span><span class="sxs-lookup"><span data-stu-id="5a3b5-109">In the following example, a selection condition is specified for a definition of a table view.</span></span> <span data-ttu-id="5a3b5-110">В этом примере определение используется только при вычислении указанного скрипта `true` .</span><span class="sxs-lookup"><span data-stu-id="5a3b5-110">In this example, the definition is used only when the specified script is evaluated to `true`.</span></span>

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

<span data-ttu-id="5a3b5-111">Количество условий выбора, которое можно указать для определения представления или элемента управления, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="5a3b5-111">There is no limit to the number of selection conditions that you can specify for a definition of a view or control.</span></span> <span data-ttu-id="5a3b5-112">Существуют следующие требования:</span><span class="sxs-lookup"><span data-stu-id="5a3b5-112">The only requirements are the following:</span></span>

- <span data-ttu-id="5a3b5-113">Условие выбора должно указывать одно имя свойства или скрипт для активации условия, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="5a3b5-113">The selection condition must specify one property name or script to trigger the condition, but cannot specify both.</span></span>

- <span data-ttu-id="5a3b5-114">Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.</span><span class="sxs-lookup"><span data-stu-id="5a3b5-114">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

## <a name="specifying-a-selection-condition-for-an-item"></a><span data-ttu-id="5a3b5-115">Указание условия выбора для элемента</span><span class="sxs-lookup"><span data-stu-id="5a3b5-115">Specifying a Selection Condition for an Item</span></span>

<span data-ttu-id="5a3b5-116">Можно также указать, когда элемент представления списка или элемента управления используется, включив `ItemSelectionCondition` элемент в определение элемента.</span><span class="sxs-lookup"><span data-stu-id="5a3b5-116">You can also specify when an item of a list view or control is used by including the `ItemSelectionCondition` element in the item definition.</span></span> <span data-ttu-id="5a3b5-117">В следующем примере условие выбора задается для элемента в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="5a3b5-117">In the following example, a selection condition is specified for an item of a list view.</span></span> <span data-ttu-id="5a3b5-118">В этом примере элемент используется только при вычислении скрипта `true` .</span><span class="sxs-lookup"><span data-stu-id="5a3b5-118">In this example, the item is used only when the script is evaluated to `true`.</span></span>

```xml
<ListItem>
  <ItemSelectionCondition>
    <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  </ItemSelectionCondition>
</ListItem>

```

<span data-ttu-id="5a3b5-119">Для элемента можно указать только одно условие выбора.</span><span class="sxs-lookup"><span data-stu-id="5a3b5-119">You can specify only one selection condition for an item.</span></span> <span data-ttu-id="5a3b5-120">И условие должно указывать одно имя свойства или скрипт для запуска условия, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="5a3b5-120">And the condition must specify one property name or script to trigger the condition, but cannot specify both.</span></span>

## <a name="xml-elements"></a><span data-ttu-id="5a3b5-121">Элементы XML</span><span class="sxs-lookup"><span data-stu-id="5a3b5-121">XML Elements</span></span>

 <span data-ttu-id="5a3b5-122">Для создания условия выбора используются следующие XML-элементы.</span><span class="sxs-lookup"><span data-stu-id="5a3b5-122">The following XML elements are used to create a selection condition.</span></span>

- <span data-ttu-id="5a3b5-123">Следующие элементы указывают условия выбора для определений представлений:</span><span class="sxs-lookup"><span data-stu-id="5a3b5-123">The following elements specify selection conditions for view definitions:</span></span>

  - [<span data-ttu-id="5a3b5-124">Элемент SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="5a3b5-124">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

  - [<span data-ttu-id="5a3b5-125">Элемент SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="5a3b5-125">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

  - [<span data-ttu-id="5a3b5-126">Элемент SelectionCondition для элемента EntrySelectedBy для элемента WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="5a3b5-126">SelectionCondition Element for EntrySelectedBy for WideControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

  - [<span data-ttu-id="5a3b5-127">Элемент SelectionCondition для элемента EntrySelectedBy для элемента CustomControl (формат)</span><span class="sxs-lookup"><span data-stu-id="5a3b5-127">SelectionCondition Element for EntrySelectedBy for CustomControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

- <span data-ttu-id="5a3b5-128">Следующие элементы указывают условия выбора для типовых определений и определения элементов управления.</span><span class="sxs-lookup"><span data-stu-id="5a3b5-128">The following elements specify selection conditions for common and view control definitions:</span></span>

  - [<span data-ttu-id="5a3b5-129">Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="5a3b5-129">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

  - [<span data-ttu-id="5a3b5-130">Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="5a3b5-130">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

- <span data-ttu-id="5a3b5-131">Следующий элемент задает условие выбора для расширения объектов коллекции:</span><span class="sxs-lookup"><span data-stu-id="5a3b5-131">The following element specifies the selection condition for expanding collection objects:</span></span>

  - [<span data-ttu-id="5a3b5-132">Элемент SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="5a3b5-132">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

- <span data-ttu-id="5a3b5-133">Следующий элемент задает условие выбора для отображения новой группы данных:</span><span class="sxs-lookup"><span data-stu-id="5a3b5-133">The following element specifies the selection condition for displaying a new group of data:</span></span>

  - [<span data-ttu-id="5a3b5-134">Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5a3b5-134">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

- <span data-ttu-id="5a3b5-135">Следующий элемент задает условие выбора элемента для представления списка:</span><span class="sxs-lookup"><span data-stu-id="5a3b5-135">The following element specifies an item selection condition for a list view:</span></span>

  - [<span data-ttu-id="5a3b5-136">Элемент ItemSelectionCondition для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="5a3b5-136">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

- <span data-ttu-id="5a3b5-137">Следующие элементы определяют условие выбора элемента для элементов управления:</span><span class="sxs-lookup"><span data-stu-id="5a3b5-137">The following elements specify an item selection condition for controls:</span></span>

  - [<span data-ttu-id="5a3b5-138">Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="5a3b5-138">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

  - [<span data-ttu-id="5a3b5-139">Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="5a3b5-139">ItemSelectionCondition Element for ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

  - [<span data-ttu-id="5a3b5-140">Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента CustomControl (формат)</span><span class="sxs-lookup"><span data-stu-id="5a3b5-140">ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

## <a name="see-also"></a><span data-ttu-id="5a3b5-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="5a3b5-141">See Also</span></span>

[<span data-ttu-id="5a3b5-142">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a3b5-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
