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
# <a name="defining-conditions-for-displaying-data"></a>Определение условий для отображения данных

При определении данных, отображаемых представлением или элементом управления, можно указать условие, которое должно существовать для отображения данных. Условие может быть активировано конкретным свойством, или если значение скрипта или свойства равно `true` . При выполнении условия выбора используется определение представления или элемента управления.

## <a name="specifying-a-selection-condition-for-a-definition"></a>Указание условия выбора для определения

При создании определения для представления или элемента управления `EntrySelectedBy` элемент используется для указания объектов, которые будут использовать определение или какое условие должно существовать для использования определения. Условие задается `SelectionCondition` элементом.

В следующем примере условие выбора задается для определения табличного представления. В этом примере определение используется только при вычислении указанного скрипта `true` .

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

Количество условий выбора, которое можно указать для определения представления или элемента управления, не ограничено. Существуют следующие требования:

- Условие выбора должно указывать одно имя свойства или скрипт для активации условия, но не может одновременно указывать оба значения.

- Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.

## <a name="specifying-a-selection-condition-for-an-item"></a>Указание условия выбора для элемента

Можно также указать, когда элемент представления списка или элемента управления используется, включив `ItemSelectionCondition` элемент в определение элемента. В следующем примере условие выбора задается для элемента в представлении списка. В этом примере элемент используется только при вычислении скрипта `true` .

```xml
<ListItem>
  <ItemSelectionCondition>
    <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  </ItemSelectionCondition>
</ListItem>

```

Для элемента можно указать только одно условие выбора. И условие должно указывать одно имя свойства или скрипт для запуска условия, но не может одновременно указывать оба значения.

## <a name="xml-elements"></a>Элементы XML

 Для создания условия выбора используются следующие XML-элементы.

- Следующие элементы указывают условия выбора для определений представлений:

  - [Элемент SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

  - [Элемент SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

  - [Элемент SelectionCondition для элемента EntrySelectedBy для элемента WideControl (формат)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

  - [Элемент SelectionCondition для элемента EntrySelectedBy для элемента CustomControl (формат)](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

- Следующие элементы указывают условия выбора для типовых определений и определения элементов управления.

  - [Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

  - [Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента View (формат)](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

- Следующий элемент задает условие выбора для расширения объектов коллекции:

  - [Элемент SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

- Следующий элемент задает условие выбора для отображения новой группы данных:

  - [Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

- Следующий элемент задает условие выбора элемента для представления списка:

  - [Элемент ItemSelectionCondition для элемента ListItem для элемента ListControl (формат)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

- Следующие элементы определяют условие выбора элемента для элементов управления:

  - [Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента Controls для элемента Configuration (формат)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

  - [Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента Controls для элемента View (формат)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

  - [Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента CustomControl (формат)](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

## <a name="see-also"></a>См. также:

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
