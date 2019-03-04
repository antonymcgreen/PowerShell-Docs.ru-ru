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
ms.openlocfilehash: 8a5b84b6a461e9fc340a5981578d95ca2ac6b9f7
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855650"
---
# <a name="defining-conditions-for-displaying-data"></a><span data-ttu-id="fbcca-102">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="fbcca-102">Defining Conditions for Displaying Data</span></span>

<span data-ttu-id="fbcca-103">При определении того, какие данные отображаются в представлении или элемент управления, можно указать условие, которое должен существовать для отображения данных.</span><span class="sxs-lookup"><span data-stu-id="fbcca-103">When defining what data is displayed by a view or a control, you can specify a condition that must exist for the data to be displayed.</span></span> <span data-ttu-id="fbcca-104">Условие может запускаться по определенному свойству или сценарий, или значение свойства, результатом которого является `true`.</span><span class="sxs-lookup"><span data-stu-id="fbcca-104">The condition can be triggered by a specific property, or when a script or property value evaluates to `true`.</span></span> <span data-ttu-id="fbcca-105">При выполнении условия выбора, используется определение представления или элемента управления.</span><span class="sxs-lookup"><span data-stu-id="fbcca-105">When the selection condition is met, the definition of the view or control is used.</span></span>

## <a name="specifying-a-selection-condition-for-a-definition"></a><span data-ttu-id="fbcca-106">Указывается условие выбора для определения</span><span class="sxs-lookup"><span data-stu-id="fbcca-106">Specifying a Selection Condition for a Definition</span></span>

<span data-ttu-id="fbcca-107">При создании определения представления или управлять тем, `EntrySelectedBy` элемент используется для указания объектов, которые будет использовать определение или какие-либо условие должно существовать для определения для использования.</span><span class="sxs-lookup"><span data-stu-id="fbcca-107">When creating a definition for a view or control, the `EntrySelectedBy` element is used to specify which objects will use the definition or what condition must exist for the definition to be used.</span></span> <span data-ttu-id="fbcca-108">Условие задается `SelectionCondition` элемент.</span><span class="sxs-lookup"><span data-stu-id="fbcca-108">The condition is specified by the `SelectionCondition` element.</span></span>

<span data-ttu-id="fbcca-109">В следующем примере условие выбора указано определение таблицы представления.</span><span class="sxs-lookup"><span data-stu-id="fbcca-109">In the following example, a selection condition is specified for a definition of a table view.</span></span> <span data-ttu-id="fbcca-110">В этом примере определение используется только в том случае, когда указанный скрипт вычисляется для `true`.</span><span class="sxs-lookup"><span data-stu-id="fbcca-110">In this example, the definition is used only when the specified script is evaluated to `true`.</span></span>

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

<span data-ttu-id="fbcca-111">Не ограничено количество условий выборки, которые можно указать для определения представления или элемента управления.</span><span class="sxs-lookup"><span data-stu-id="fbcca-111">There is no limit to the number of selection conditions that you can specify for a definition of a view or control.</span></span> <span data-ttu-id="fbcca-112">Ниже перечислены только требования.</span><span class="sxs-lookup"><span data-stu-id="fbcca-112">The only requirements are the following:</span></span>

- <span data-ttu-id="fbcca-113">Условию выбора необходимо указать одно имя свойства или сценарии, чтобы запустить условие, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="fbcca-113">The selection condition must specify one property name or script to trigger the condition, but cannot specify both.</span></span>

- <span data-ttu-id="fbcca-114">Условию выбора можно указать любое число типов .NET или выбора задает, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="fbcca-114">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

## <a name="specifying-a-selection-condition-for-an-item"></a><span data-ttu-id="fbcca-115">Указывается условие выбора для элемента</span><span class="sxs-lookup"><span data-stu-id="fbcca-115">Specifying a Selection Condition for an Item</span></span>

<span data-ttu-id="fbcca-116">Можно также указать, когда используется элемент представления списка или элемента управления, включая `ItemSelectionCondition` элемент в определении элемента.</span><span class="sxs-lookup"><span data-stu-id="fbcca-116">You can also specify when an item of a list view or control is used by including the `ItemSelectionCondition` element in the item definition.</span></span> <span data-ttu-id="fbcca-117">В следующем примере условие выбора указывается для элемента представления списка.</span><span class="sxs-lookup"><span data-stu-id="fbcca-117">In the following example, a selection condition is specified for an item of a list view.</span></span> <span data-ttu-id="fbcca-118">В этом примере используется элемент только в том случае, если скрипт выполняется для `true`.</span><span class="sxs-lookup"><span data-stu-id="fbcca-118">In this example, the item is used only when the script is evaluated to `true`.</span></span>

```xml
<ListItem>
  <ItemSelectionCondition>
    <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  </ItemSelectionCondition>
</ListItem>

```

<span data-ttu-id="fbcca-119">Можно указать условие выбрать только один вариант для элемента.</span><span class="sxs-lookup"><span data-stu-id="fbcca-119">You can specify only one selection condition for an item.</span></span> <span data-ttu-id="fbcca-120">И условие, необходимо указать одно имя свойства или сценарии, чтобы запустить условие, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="fbcca-120">And the condition must specify one property name or script to trigger the condition, but cannot specify both.</span></span>

## <a name="xml-elements"></a><span data-ttu-id="fbcca-121">XML-элементов</span><span class="sxs-lookup"><span data-stu-id="fbcca-121">XML Elements</span></span>

 <span data-ttu-id="fbcca-122">Следующие элементы XML используются для создания условия выбора.</span><span class="sxs-lookup"><span data-stu-id="fbcca-122">The following XML elements are used to create a selection condition.</span></span>

- <span data-ttu-id="fbcca-123">Следующие элементы задать условия выбора для определения представлений:</span><span class="sxs-lookup"><span data-stu-id="fbcca-123">The following elements specify selection conditions for view definitions:</span></span>

    - [<span data-ttu-id="fbcca-124">Элемент SelectionCondition для EntrySelectedBy для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="fbcca-124">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

    - [<span data-ttu-id="fbcca-125">Элемент SelectionCondition для EntrySelectedBy для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="fbcca-125">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

    - [<span data-ttu-id="fbcca-126">Элемент SelectionCondition для EntrySelectedBy для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="fbcca-126">SelectionCondition Element for EntrySelectedBy for WideControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

    - [<span data-ttu-id="fbcca-127">Элемент SelectionCondition для EntrySelectedBy для пользовательский элемент управления (формат)</span><span class="sxs-lookup"><span data-stu-id="fbcca-127">SelectionCondition Element for EntrySelectedBy for CustomControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

- <span data-ttu-id="fbcca-128">Выберите следующие элементы условия для часто используемых и представление управления определениями:</span><span class="sxs-lookup"><span data-stu-id="fbcca-128">The following elements specify selection conditions for common and view control definitions:</span></span>

    - [<span data-ttu-id="fbcca-129">Элемент SelectionCondition для EntrySelectedBy для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="fbcca-129">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

    - [<span data-ttu-id="fbcca-130">Элемент SelectionCondition для EntrySelectedBy для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="fbcca-130">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

- <span data-ttu-id="fbcca-131">Следующий элемент указывает условия выбора для динамически-расширяемых объектов коллекции:</span><span class="sxs-lookup"><span data-stu-id="fbcca-131">The following element specifies the selection condition for expanding collection objects:</span></span>

    - [<span data-ttu-id="fbcca-132">Элемент SelectionCondition для EntrySelectedBy для EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="fbcca-132">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

- <span data-ttu-id="fbcca-133">Следующий элемент указывает условия выбора для отображения новой группы данных:</span><span class="sxs-lookup"><span data-stu-id="fbcca-133">The following element specifies the selection condition for displaying a new group of data:</span></span>

    - [<span data-ttu-id="fbcca-134">Элемент SelectionCondition для EntrySelectedBy для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="fbcca-134">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

- <span data-ttu-id="fbcca-135">Следующий элемент указывает условие выбора элемента представления списка:</span><span class="sxs-lookup"><span data-stu-id="fbcca-135">The following element specifies an item selection condition for a list view:</span></span>

    - [<span data-ttu-id="fbcca-136">Элемент ItemSelectionCondition для ListItem для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="fbcca-136">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

- <span data-ttu-id="fbcca-137">Следующие элементы указать условие выбора элементов для элементов управления:</span><span class="sxs-lookup"><span data-stu-id="fbcca-137">The following elements specify an item selection condition for controls:</span></span>

    - [<span data-ttu-id="fbcca-138">Элемент ItemSelectionCondition для ExpressionBinding для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="fbcca-138">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

    - [<span data-ttu-id="fbcca-139">Элемент ItemSelectionCondition для ExpressionBinding для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="fbcca-139">ItemSelectionCondition Element for ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

    - [<span data-ttu-id="fbcca-140">Элемент ItemSelectionCondition для ExpressionBinding для пользовательский элемент управления (формат)</span><span class="sxs-lookup"><span data-stu-id="fbcca-140">ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

## <a name="see-also"></a><span data-ttu-id="fbcca-141">См. также</span><span class="sxs-lookup"><span data-stu-id="fbcca-141">See Also</span></span>

[<span data-ttu-id="fbcca-142">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="fbcca-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
