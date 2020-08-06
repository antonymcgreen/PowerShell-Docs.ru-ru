---
title: Определение наборов выбора | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 58c812b69f92c33304bf7fc7b2891cc2a0227918
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774309"
---
# <a name="defining-selection-sets"></a>Определение наборов выделенных фрагментов

При создании нескольких представлений и элементов управления можно определить наборы объектов, которые называются наборами выбора. Набор выбора позволяет определять объекты один раз без необходимости их многократного определения для каждого представления или элемента управления. Обычно наборы выбора используются при наличии набора связанных объектов .NET. Например, `FileSystem` файл форматирования (FileSystem.format.ps1XML) определяет набор типов файловой системы, используемых несколькими представлениями.

## <a name="where-selection-sets-are-defined-and-referenced"></a>Где определяются и указываются наборы выбора

Наборы выбора определяются как часть общих данных, которые могут использоваться всеми представлениями и элементами управления, определенными в файле форматирования. В следующем примере показано, как определить три набора выбора.

```xml
<Configuration>
  <SelectionSets>
    <SelectionSet>...</SelectionSet>
    <SelectionSet>...</SelectionSet>
    <SelectionSet>...</SelectionSet>
  </SelectionSets>
</Configuration>
```

Ссылаться на наборы выбора можно следующими способами.

- Каждое представление содержит `ViewSelectedBy` элемент, который определяет, какие объекты отображаются с помощью представления. `ViewSelectedBy`Элемент имеет `SelectionSetName` дочерний элемент, указывающий набор выбора, который используется всеми определениями представления. На количество наборов выбора, на которые можно ссылаться из представления, нет ограничений.

- В каждом определении представления или элемента управления `EntrySelectedBy` элемент определяет, какие объекты отображаются с помощью этого определения. Как правило, представление или элемент управления имеет только одно определение, поэтому объекты определяются `ViewSelectedBy` элементом. `EntrySelectedBy`Элемент определения содержит `SelectionSetName` дочерний элемент, указывающий набор выбора. При указании набора, выбранного для определения, нельзя указать какие-либо другие дочерние элементы `EntrySelectedBy` элемента.

- В каждом определении представления или элемента управления `SelectionCondition` элемент можно использовать для указания условия использования определения. `SelectionCondition`Элемент имеет `SelectionSetName` дочерний элемент, указывающий набор выбора, который запускает условие. Условие активируется при отображении любого из объектов, определенных в наборе выбора. Дополнительные сведения о настройке этих условий см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="selection-set-example"></a>Пример набора выбора

В следующем примере показан набор выбора, который берется непосредственно из `FileSystem` файла форматирования, предоставляемого Windows PowerShell. Дополнительные сведения о других файлах форматирования Windows PowerShell см. в разделе [файлы форматирования Windows PowerShell](./powershell-formatting-files.md).

```xml
<SelectionSets>
  <SelectionSet>
    <Name>FileSystemTypes</Name>
    <Types>
     <TypeName>System.IO.DirectoryInfo</TypeName>
     <TypeName>System.IO.FileInfo</TypeName>
     <TypeName>Deserialized.System.IO.DirectoryInfo</TypeName>
     <TypeName>Deserialized.System.IO.FileInfo</TypeName>
    </Types>
  </SelectionSet>
</SelectionSets>
```

В элементе табличного представления имеется ссылка на предыдущий набор элементов `ViewSelectedBy` .

```xml
<ViewDefinitions>
  <View>
    <Name>Files</Name>
    <ViewSelectedBy>
      <SelectionSetName>FileSystemTypes</SelectionSetName>
    </ViewSelectedBy>
    <TableControl>...</TableControl>
  </View>
</ViewDefinitions>

```

## <a name="xml-elements"></a>Элементы XML

 Количество наборов выбора, которые можно определить, не ограничено. Для создания набора выбора используются следующие XML-элементы.

- Элемент [селектионсетс](./selectionsets-element-format.md) определяет наборы объектов .NET, на которые ссылаются представления и элементы управления файла форматирования.

- Элемент [Selection](./selectionset-element-format.md) определяет один набор объектов .NET.

- Элемент [Name](./name-element-for-selectionset-format.md) указывает имя, используемое для ссылки на набор выбора.

- Элемент [types](./types-element-for-selectionset-format.md) указывает типы .NET объектов набора выбора. (В файлах форматирования объекты задаются типом .NET.)

 Для указания набора выбора используются следующие XML-элементы.

- Следующий элемент задает набор выбора, который будет использоваться во всех определениях представления:

  - [Элемент SelectionSetName для элемента ViewSelectedBy (формат)](./selectionsetname-element-for-viewselectedby-format.md)

  - [Элемент SelectionSetName для элемента EntrySelectedBy для элемента GroupBy (формат)](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

- Следующие элементы определяют набор выбора, используемый одним определением представления:

  - [Элемент SelectionSetName для элемента EntrySelectedBy для элемента ListControl (формат)](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

  - [Элемент SelectionSetName для элемента EntrySelectedBy для элемента TableControl (формат)](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

  - [Элемент SelectionSetName для элемента EntrySelectedBy для элемента WideControl (формат)](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

  - [Элемент SelectionSetName для элемента EntrySelectedBy для элемента CustomControl для элемента View (формат)](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

- Следующие элементы задают набор элементов, используемый в определениях типов Common и View Control:

  - [Элемент SelectionSetName для элемента EntrySelectedBy для элемента Controls для элемента View (формат)](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)

  - [Элемент SelectionSetName для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)](./selectionsetname-element-for-entryselectedby-for-controls-for-configuration-format.md)

- Следующие элементы определяют набор выбора, используемый при определении, какой объект следует развернуть:

  - [Элемент SelectionSetName для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

- Следующие элементы определяют набор элементов, используемый условиями выбора.

  - [Элемент SelectionSetName для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

  - [Элемент SelectionSetName для элемента SelectionCondition для элемента Controls для элемента View (формат)](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

  - [Элемент SelectionSetName для элемента SelectionCondition для элемента CustomControl для элемента View (формат)](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

  - [Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

  - [Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListEntry (формат)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)

  - [Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

  - [Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

  - [Элемент SelectionSetName для элемента SelectionCondition для элемента GroupBy (формат)](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)

## <a name="see-also"></a>См. также

[селектионсетс](./selectionsets-element-format.md)

[Набор выбора](./selectionset-element-format.md)

[Имя](./name-element-for-selectionset-format.md)

[Типы](./types-element-for-selectionset-format.md)

[Файлы форматирования PowerShell](./powershell-formatting-files.md)

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Создание файла форматирования и типов PowerShell](./writing-a-powershell-formatting-file.md)
