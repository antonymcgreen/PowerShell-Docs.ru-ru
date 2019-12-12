---
title: Определение наборов выбора | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00dbb5ee-93d4-4914-a082-ef4d8b236b5c
caps.latest.revision: 16
ms.openlocfilehash: 596212f2e64401a751cf3dca0ee7d60b80912c00
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368853"
---
# <a name="defining-selection-sets"></a>Определение наборов выделенных фрагментов

При создании нескольких представлений и элементов управления можно определить наборы объектов, которые называются наборами выбора. Набор выбора позволяет определять объекты один раз без необходимости их многократного определения для каждого представления или элемента управления. Обычно наборы выбора используются при наличии набора связанных объектов .NET. Например, файл форматирования `FileSystem` (FileSystem. Format. ps1xml) определяет набор типов файловой системы, используемых несколькими представлениями.

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

- Каждое представление содержит элемент `ViewSelectedBy`, который определяет, какие объекты отображаются с помощью представления. Элемент `ViewSelectedBy` имеет `SelectionSetName` дочерний элемент, указывающий набор выбора, который используется всеми определениями представления. На количество наборов выбора, на которые можно ссылаться из представления, нет ограничений.

- В каждом определении представления или элемента управления элемент `EntrySelectedBy` определяет, какие объекты отображаются с помощью этого определения. Как правило, представление или элемент управления имеет только одно определение, поэтому объекты определяются элементом `ViewSelectedBy`. Элемент `EntrySelectedBy` определения содержит дочерний элемент `SelectionSetName`, указывающий набор выбора. При указании набора, выбранного для определения, нельзя указать какие-либо другие дочерние элементы элемента `EntrySelectedBy`.

- В каждом определении представления или элемента управления элемент `SelectionCondition` можно использовать для указания условия использования определения. Элемент `SelectionCondition` имеет `SelectionSetName` дочерний элемент, указывающий набор выбора, который запускает условие. Условие активируется при отображении любого из объектов, определенных в наборе выбора. Дополнительные сведения о настройке этих условий см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="selection-set-example"></a>Пример набора выбора

В следующем примере показан набор выбора, который берется непосредственно из файла форматирования `FileSystem`, предоставляемого Windows PowerShell. Дополнительные сведения о других файлах форматирования Windows PowerShell см. в разделе [файлы форматирования Windows PowerShell](./powershell-formatting-files.md).

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

В элементе `ViewSelectedBy` представления таблицы содержится ссылка на предыдущий набор элементов.

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

    - [Элемент Селектионсетнаме для Виевселектедби (Format)](./selectionsetname-element-for-viewselectedby-format.md)

    - [Элемент Селектионсетнаме для Ентриселектедби для GroupBy (Format)](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

- Следующие элементы определяют набор выбора, используемый одним определением представления:

    - [Элемент Селектионсетнаме для Ентриселектедби для ListControl (Format)](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

    - [Элемент Селектионсетнаме для Ентриселектедби для Таблеконтрол (Format)](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

    - [Элемент Селектионсетнаме для Ентриселектедби для Видеконтрол (Format)](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

    - [Элемент Селектионсетнаме для Ентриселектедби для ошибка customcontrol для представления (Format)](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

- Следующие элементы задают набор элементов, используемый в определениях типов Common и View Control:

    - [Элемент Селектионсетнаме для Ентриселектедби элементов управления для представления (формат)](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)

    - [Элемент Селектионсетнаме для Ентриселектедби для элементов управления конфигурации (Format)](./selectionsetname-element-for-entryselectedby-for-controls-for-configuration-format.md)

- Следующие элементы определяют набор выбора, используемый при определении, какой объект следует развернуть:

    - [Элемент Селектионсетнаме для Ентриселектедби для Енумерабликспансион (Format)](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

- Следующие элементы определяют набор элементов, используемый условиями выбора.

    - [Элемент Селектионсетнаме для Селектионкондитион для элементов управления конфигурации (Format)](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

    - [Элемент Селектионсетнаме для Селектионкондитион элементов управления для представления (формат)](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

    - [Элемент Селектионсетнаме для Селектионкондитион для ошибка customcontrol для представления (Format)](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

    - [Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

    - [Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Листентри (Format)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)

    - [Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Таблеконтрол (Format)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

    - [Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Видинтри (Format)](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

    - [Элемент Селектионсетнаме для Селектионкондитион для GroupBy (Format)](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)

## <a name="see-also"></a>См. также:

[селектионсетс](./selectionsets-element-format.md)

[Набор выбора](./selectionset-element-format.md)

[Name](./name-element-for-selectionset-format.md)

[Типы](./types-element-for-selectionset-format.md)

[Файлы форматирования PowerShell](./powershell-formatting-files.md)

[Определение условий для отображения данных](./defining-conditions-for-displaying-data.md)

[Создание файла форматирования и типов PowerShell](./writing-a-powershell-formatting-file.md)
