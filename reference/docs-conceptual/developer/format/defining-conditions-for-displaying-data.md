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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363903"
---
# <a name="defining-conditions-for-displaying-data"></a>Определение условий для отображения данных

При определении данных, отображаемых представлением или элементом управления, можно указать условие, которое должно существовать для отображения данных. Условие может быть активировано конкретным свойством, или если значение скрипта или свойства равно `true`. При выполнении условия выбора используется определение представления или элемента управления.

## <a name="specifying-a-selection-condition-for-a-definition"></a>Указание условия выбора для определения

При создании определения для представления или элемента управления элемент `EntrySelectedBy` используется для указания того, какие объекты будут использовать определение или какое условие должно существовать для использования определения. Условие задается элементом `SelectionCondition`.

В следующем примере условие выбора задается для определения табличного представления. В этом примере определение используется только в том случае, если указанный скрипт оценивается как `true`.

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

Можно также указать, когда элемент представления списка или элемента управления используется, включив элемент `ItemSelectionCondition` в определение элемента. В следующем примере условие выбора задается для элемента в представлении списка. В этом примере элемент используется только при вычислении скрипта в `true`.

```xml
<ListItem>
  <ItemSelectionCondition>
    <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  </ItemSelectionCondition>
</ListItem>

```

Для элемента можно указать только одно условие выбора. И условие должно указывать одно имя свойства или скрипт для запуска условия, но не может одновременно указывать оба значения.

## <a name="xml-elements"></a>XML-элементы

 Для создания условия выбора используются следующие XML-элементы.

- Следующие элементы указывают условия выбора для определений представлений:

    - [Элемент Селектионкондитион для Ентриселектедби для Таблеконтрол (Format)](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

    - [Элемент Селектионкондитион для Ентриселектедби для ListControl (Format)](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

    - [Элемент Селектионкондитион для Ентриселектедби для Видеконтрол (Format)](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

    - [Элемент Селектионкондитион для Ентриселектедби для ошибка customcontrol (Format)](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

- Следующие элементы указывают условия выбора для типовых определений и определения элементов управления.

    - [Элемент Селектионкондитион для Ентриселектедби для элементов управления конфигурации (Format)](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

    - [Элемент Селектионкондитион для Ентриселектедби элементов управления для представления (формат)](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

- Следующий элемент задает условие выбора для расширения объектов коллекции:

    - [Элемент Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format)](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

- Следующий элемент задает условие выбора для отображения новой группы данных:

    - [Элемент Селектионкондитион для Ентриселектедби для GroupBy (Format)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

- Следующий элемент задает условие выбора элемента для представления списка:

    - [Элемент Итемселектионкондитион для ListItem для ListControl (Format)](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

- Следующие элементы определяют условие выбора элемента для элементов управления:

    - [Элемент Итемселектионкондитион для ExpressionBinding для элементов управления конфигурации (Format)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

    - [Элемент Итемселектионкондитион для ExpressionBinding элементов управления для представления (формат)](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

    - [Элемент Итемселектионкондитион для ExpressionBinding для ошибка customcontrol (Format)](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

## <a name="see-also"></a>См. также:

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
