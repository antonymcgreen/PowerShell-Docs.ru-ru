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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066334"
---
# <a name="defining-conditions-for-displaying-data"></a>Определение условий для отображения данных

При определении того, какие данные отображаются в представлении или элемент управления, можно указать условие, которое должен существовать для отображения данных. Условие может запускаться по определенному свойству или сценарий, или значение свойства, результатом которого является `true`. При выполнении условия выбора, используется определение представления или элемента управления.

## <a name="specifying-a-selection-condition-for-a-definition"></a>Указывается условие выбора для определения

При создании определения представления или управлять тем, `EntrySelectedBy` элемент используется для указания объектов, которые будет использовать определение или какие-либо условие должно существовать для определения для использования. Условие задается `SelectionCondition` элемент.

В следующем примере условие выбора указано определение таблицы представления. В этом примере определение используется только в том случае, когда указанный скрипт вычисляется для `true`.

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

Не ограничено количество условий выборки, которые можно указать для определения представления или элемента управления. Ниже перечислены только требования.

- Условию выбора необходимо указать одно имя свойства или сценарии, чтобы запустить условие, но нельзя указать одновременно.

- Условию выбора можно указать любое число типов .NET или выбора задает, но нельзя указать одновременно.

## <a name="specifying-a-selection-condition-for-an-item"></a>Указывается условие выбора для элемента

Можно также указать, когда используется элемент представления списка или элемента управления, включая `ItemSelectionCondition` элемент в определении элемента. В следующем примере условие выбора указывается для элемента представления списка. В этом примере используется элемент только в том случае, если скрипт выполняется для `true`.

```xml
<ListItem>
  <ItemSelectionCondition>
    <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  </ItemSelectionCondition>
</ListItem>

```

Можно указать условие выбрать только один вариант для элемента. И условие, необходимо указать одно имя свойства или сценарии, чтобы запустить условие, но нельзя указать одновременно.

## <a name="xml-elements"></a>XML-элементов

 Следующие элементы XML используются для создания условия выбора.

- Следующие элементы задать условия выбора для определения представлений:

    - [Элемент SelectionCondition для EntrySelectedBy для TableControl (формат)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

    - [Элемент SelectionCondition для EntrySelectedBy для ListControl (формат)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

    - [Элемент SelectionCondition для EntrySelectedBy для WideControl (формат)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

    - [Элемент SelectionCondition для EntrySelectedBy для пользовательский элемент управления (формат)](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

- Выберите следующие элементы условия для часто используемых и представление управления определениями:

    - [Элемент SelectionCondition для EntrySelectedBy для элементов управления для конфигурации (формат)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

    - [Элемент SelectionCondition для EntrySelectedBy для элементов управления для представления (формат)](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

- Следующий элемент указывает условия выбора для динамически-расширяемых объектов коллекции:

    - [Элемент SelectionCondition для EntrySelectedBy для EnumerableExpansion (формат)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

- Следующий элемент указывает условия выбора для отображения новой группы данных:

    - [Элемент SelectionCondition для EntrySelectedBy для GroupBy (формат)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

- Следующий элемент указывает условие выбора элемента представления списка:

    - [Элемент ItemSelectionCondition для ListItem для ListControl (формат)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

- Следующие элементы указать условие выбора элементов для элементов управления:

    - [Элемент ItemSelectionCondition для ExpressionBinding для элементов управления для конфигурации (формат)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

    - [Элемент ItemSelectionCondition для ExpressionBinding для элементов управления для представления (формат)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

    - [Элемент ItemSelectionCondition для ExpressionBinding для пользовательский элемент управления (формат)](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

## <a name="see-also"></a>См. также

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
