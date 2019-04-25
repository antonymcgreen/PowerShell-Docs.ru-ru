---
title: Определение наборов Выбор | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00dbb5ee-93d4-4914-a082-ef4d8b236b5c
caps.latest.revision: 16
ms.openlocfilehash: 596212f2e64401a751cf3dca0ee7d60b80912c00
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066317"
---
# <a name="defining-selection-sets"></a>Определение наборов выделенных фрагментов

При создании нескольких представлений и элементов управления, можно определить наборы объектов, которые указаны как наборы выделения. Выбора позволяет определить один раз объекты без необходимости определять их несколько раз для каждого представления или элемента управления. Как правило выбор наборов используются при наличии набора связанных объектов .NET. Например `FileSystem` файл форматирования (FileSystem.format.ps1xml) определяет набор выбора типов файлов системы, использующие несколько представлений.

## <a name="where-selection-sets-are-defined-and-referenced"></a>Где находятся наборы выделения, определенные и указывает на

Выбор наборов определить как часть общих данных, который может использоваться для всех представлений и элементов управления, определенных в файле форматирования. В следующем примере показано, как определяются три набора выбора.

```xml
<Configuration>
  <SelectionSets>
    <SelectionSet>...</SelectionSet>
    <SelectionSet>...</SelectionSet>
    <SelectionSet>...</SelectionSet>
  </SelectionSets>
</Configuration>
```

Вы можете ссылаться на выбор задает одним из следующих способов:

- Каждое представление имеет `ViewSelectedBy` элемент, который определяет, какие объекты отображаются с помощью представления. `ViewSelectedBy` Элемент имеет `SelectionSetName` дочерний элемент, который указывает выбранный набор, все определения использования представления. Нет никаких ограничений на число наборов выбора, которые можно создать ссылку из представления.

- В каждое определение представления или элемента управления `EntrySelectedBy` элемент определяет, какие объекты отображаются с помощью этого определения. Обычно в представлении или элемент управления имеет только одно определение, определяются объекты `ViewSelectedBy` элемент. `EntrySelectedBy` Элемент определения имеет `SelectionSetName` дочерний элемент, указывающий набор выделения. Если указать значение для определения выделения, нельзя задавать любые другие дочерние элементы `EntrySelectedBy` элемент.

- В каждое определение представления или элемента управления `SelectionCondition` элемент может использоваться для указания условия для использования определение. `SelectionCondition` Элемент имеет `SelectionSetName` дочерний элемент, который указывает выбранный набор, который активирует условие. Условие активируется в том случае, когда отображается ни одно из объектов, определенных в наборе выбора. Дополнительные сведения о настройке этих условий см. в разделе [определение условий при отображении данных](./defining-conditions-for-displaying-data.md).

## <a name="selection-set-example"></a>Пример выбора набора

В следующем примере показано набор выделения берется непосредственно из `FileSystem` форматирования файлов, предоставляемые Windows PowerShell. Дополнительные сведения о других Windows PowerShell, в файлов форматирования см. в разделе [файлы форматирования Windows PowerShell](./powershell-formatting-files.md).

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

Предыдущий набор выбора указывается в `ViewSelectedBy` элемент представления таблицы.

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

## <a name="xml-elements"></a>XML-элементов

 Нет ограничений на число наборов выбора, которые можно определить. Следующие элементы XML используются для создания набора выбора.

- [SelectionSets](./selectionsets-element-format.md) элемент определяет набор объектов .NET, на которые ссылается представления и элементы управления форматирования файла.

- [SelectionSet](./selectionset-element-format.md) элемент определяет один набор объектов .NET.

- [Имя](./name-element-for-selectionset-format.md) элемент указывает имя, которое используется для ссылки на наборе выбора.

- [Типы](./types-element-for-selectionset-format.md) элемент задает типы .NET объектов набора выбора. (Внутри файлов форматирования, объекты указываются по типу .NET.)

 Следующие элементы XML используются для указания выбора.

- Следующий элемент указывает выбора, настроенный для использования в все определения представления:

    - [Элемент SelectionSetName для ViewSelectedBy (формат)](./selectionsetname-element-for-viewselectedby-format.md)

    - [Элемент SelectionSetName для EntrySelectedBy для GroupBy (формат)](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

- Следующие элементы указать набор выделения, используемый по определению одно представление:

    - [Элемент SelectionSetName для EntrySelectedBy для ListControl (формат)](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

    - [Элемент SelectionSetName для EntrySelectedBy для TableControl (формат)](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

    - [Элемент SelectionSetName для EntrySelectedBy для WideControl (формат)](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

    - [Элемент SelectionSetName для EntrySelectedBy для пользовательский элемент управления для представления (формат)](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

- Следующие элементы указать набор выделения, используемый общего определения элемента управления:

    - [Элемент SelectionSetName для EntrySelectedBy для элементов управления для представления (формат)](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)

    - [Элемент SelectionSetName для EntrySelectedBy для элементов управления для конфигурации (формат)](./selectionsetname-element-for-entryselectedby-for-controls-for-configuration-format.md)

- Следующие элементы укажите набора, используемые при определении какого объекта, чтобы развернуть:

    - [Элемент SelectionSetName для EntrySelectedBy для EnumerableExpansion (формат)](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

- Следующие элементы укажите набор выбора используемых условий выборки.

    - [Элемент SelectionSetName для SelectionCondition для элементов управления для конфигурации (формат)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

    - [Элемент SelectionSetName для SelectionCondition для элементов управления для представления (формат)](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

    - [Элемент SelectionSetName для SelectionCondition для пользовательский элемент управления для представления (формат)](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

    - [Элемент SelectionSetName для SelectionCondition для EntrySelectedBy для EnumerableExpansion (формат)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

    - [Элемент SelectionSetName для SelectionCondition для EntrySelectedBy для ListEntry (формат)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)

    - [Элемент SelectionSetName для SelectionCondition для EntrySelectedBy для TableControl (формат)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

    - [Элемент SelectionSetName для SelectionCondition для EntrySelectedBy для WideEntry (формат)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

    - [Элемент SelectionSetName для SelectionCondition для GroupBy (формат)](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)

## <a name="see-also"></a>См. также

[SelectionSets](./selectionsets-element-format.md)

[SelectionSet](./selectionset-element-format.md)

[Name](./name-element-for-selectionset-format.md)

[Типы](./types-element-for-selectionset-format.md)

[Файлы форматирования PowerShell](./powershell-formatting-files.md)

[Определение условия при отображении данных](./defining-conditions-for-displaying-data.md)

[Написание форматирование PowerShell и типы файлов](./writing-a-powershell-formatting-file.md)
