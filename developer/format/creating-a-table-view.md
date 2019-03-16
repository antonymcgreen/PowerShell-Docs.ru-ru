---
title: Создание представления таблицы | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1f405afb-70b5-4fe0-9986-bc07401d93fd
caps.latest.revision: 23
ms.openlocfilehash: 862f942facafff6cea66c4f8f1040772c6a62ec3
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58057371"
---
# <a name="creating-a-table-view"></a>Создание представления таблицы

В табличное представление отображает данные в один или несколько столбцов. Каждая строка таблицы представляет объект .NET, и каждый столбец таблицы представляет свойства объекта или значение скрипта. Можно определить представление таблицы, которое отображает все свойства объекта или подмножество свойств объекта.

## <a name="a-table-view-display"></a>Отображение представления таблиц

В следующем примере показано, как Windows PowerShell отображает [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) объект, возвращаемый [Get-Service](/powershell/module/microsoft.powershell.management/get-service) командлета. Для этого объекта, Windows PowerShell определенные отображаются: представление таблицы `Status` свойство, `Name` свойство (это свойство является псевдонимом свойства для `ServiceName` свойства) и `DisplayName` свойство. Каждая строка таблицы представляет объект, возвращаемый командлетом.

```output
Status   Name               DisplayName
------   ----               -----------
Stopped  AJRouter           AllJoyn Router Service
Stopped  ALG                Application Layer Gateway Service
Stopped  AppIDSvc           Application Identity
Running  Appinfo            Application Information
```

## <a name="defining-the-table-view"></a>Определение представления таблицы

Следующий код XML показывает схему представления таблицы для отображения [System.Serviceprocess.Servicecontroller? Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController) объекта. Укажите каждое свойство, которое будет отображаться в табличном представлении.

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>
    <TableHeaders>
      <TableColumnHeader>
        <Width>8</Width>
      </TableColumnHeader>
      <TableColumnHeader>
        <Width>18</Width>
      </TableColumnHeader>
      <TableColumnHeader>
        <Width>38</Width>
      </TableColumnHeader>
    </TableHeaders>
    <TableRowEntries>
      <TableRowEntry>
        <TableColumnItems>
          <TableColumnItem>
           <PropertyName>Status</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>Name</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>DisplayName</PropertyName>
          </TableColumnItem>
        </TableColumnItems>
      </TableRowEntry>
    </TableRowEntries>
  </TableControl>
</View>
```

Следующие элементы XML используются для определения представления списка:

- [Представление](./view-element-format.md) элемент является родительским для элемента представления таблицы. (Это же родительского элемента для списка, ширину и пользовательский элемент управления представления).

- [Имя](./name-element-for-view-format.md) элемент задает имя представления. Этот элемент является обязательным для всех представлений.

- [ViewSelectedBy](./viewselectedby-element-format.md) элемент определяет объекты, используемые представления. Этот элемент является обязательным.

- [GroupBy](./groupby-element-for-view-format.md) (не показано в следующем примере) определяет при отображении группу объектов. Новая группа запускается при каждом изменении значения определенных свойств или скрипта. Этот элемент является необязательным.

- [Элементов управления](./controls-element-for-view-format.md) (не показано в следующем примере) определяет пользовательские элементы управления, которые определены в представлении таблицы. Элементы управления позволяют для указания способа отображения данных. Этот элемент является необязательным. Представления можно определить свои собственные пользовательские элементы управления, или он может использовать стандартные элементы управления, которые могут использоваться с любого представления в файле форматирования. Дополнительные сведения о пользовательских элементах управления см. в разделе [Создание пользовательских элементов управления](./creating-custom-controls.md).

- [HideTableHeaders](./hidetableheaders-element-format.md) элемент (не показано в этом примере) указывает, что в таблице не отображается все названия в верхней части таблицы. Этот элемент является необязательным.

- [TableControl](./tablecontrol-element-format.md) элемент, который определяет сведения о заголовке и строки таблицы. Как и с другими представлениями, табличном представлении можно отобразить значения свойств объекта или значения, создаваемые скрипты.

## <a name="defining-column-headers"></a>Определение заголовков столбцов

1. [TableHeaders](./tableheaders-element-format.md) элемент и его дочерние элементы определяют, отображаемые в верхней части таблицы.

2. [TableColumnHeader](./tablecolumnheader-element-format.md) элемент определяет, что отображается в верхней части столбца таблицы. Эти элементы указываются в том порядке, что отображаются заголовки.

   Неограниченное количество этих элементом, который можно использовать, но число [TableColumnHeader](./tablecolumnheader-element-format.md) элементов в представлении таблицы должно быть равно количество [TableRowEntry](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md) элементы, которые можно использовать.

3. [Метка](./label-element-for-tablecolumnheader-for-tablecontrol-format.md) элемент указывает текст, который будет отображаться. Этот элемент является необязательным.

4. [Ширины](./width-element-for-tablecolumnheader-for-tablecontrol-format.md) элемент задает ширину (в символах) столбца. Этот элемент является необязательным.

5. [Выравнивание](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md) элемент указывает способ отображения метки. Метка может быть выровнены по левому краю, по правому краю; или по центру. Этот элемент является необязательным.

## <a name="defining-the-table-rows"></a>Определение строк таблицы

Представления таблиц можно указать одно или несколько определений, которые указывают, какие данные отображаются в строках таблицы с помощью дочерних элементов элемента [TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md) элемент. Обратите внимание, что можно указать несколько определений для строки таблицы, что заголовки строк остается тем же, независимо от того, какие определения строки используется. Как правило таблица будет содержать только одно определение.

В следующем примере, представление будет содержать одно определение, которое отображает значения нескольких свойств [System.Diagnostics.Process? Displayproperty = Fullname](/dotnet/api/System.Diagnostics.Process) объекта. Представление таблицы можно отобразить значение свойства или значение сценария (не показано в примере) в строках.

```xml
<TableRowEntries>
      <TableRowEntry>
        <TableColumnItems>
          <TableColumnItem>
           <PropertyName>Status</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>Name</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>DisplayName</PropertyName>
          </TableColumnItem>
        </TableColumnItems>
      </TableRowEntry>
    </TableRowEntries>

```

Следующие элементы XML может использоваться для предоставления определения для строки:

- [TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md) элемент и его дочерние элементы определяют, отображаемые в строках таблицы.

- [TableRowEntry](./listentry-element-for-listcontrol-format.md) элемент предоставляет определение строки. По крайней мере один [TableRowEntry](./listentry-element-for-listcontrol-format.md) требуется; тем не менее, не ограничено максимальное количество элементов, которые могут быть добавлены. В большинстве случаев представление будет иметь только одно определение.

- [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) элемент определяет объекты, которые отображаются по специфическим определением. Этот элемент является необязательным и требуется только в том случае, при определении нескольких [TableRowEntry](./listentry-element-for-listcontrol-format.md) элементы, отображающие разные объекты.

- [Wrap](./wrap-element-for-tablerowentry-for-tablecontrol-format.md) элемент указывает, что текст, который превышает ширину столбца отображается на следующей строке. По умолчанию текст, не уместившийся по ширине столбца, усекается.

- [TableColumnItems](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md) элемент определяет свойства или скрипты, значения которых отображаются в строке.

- [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) элемент определяет свойства или скрипта, значение которого отображается в столбце строки. Объект [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) элемент является обязательным для каждого столбца, строки. Первая запись отображается в первом столбце, вторая запись второго столбца и т. д.

- [PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) определяет свойство, значение которого отображается в строке. Необходимо указать свойство или сценария, но нельзя указать одновременно.

- [ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) элемент указывает сценарий, значение которого отображается в строке. Необходимо указать сценарий или свойство, но нельзя указать одновременно.

- [FormatString](./label-element-for-listitem-for-listcontrol-format.md) элемент задает шаблон формата, который определяет способ отображения значения свойства или скрипт. Этот элемент является необязательным.

- [Выравнивание](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md) элемент указывает, как отображается значение свойства или скрипт. Значение может быть выровнены по левому краю, по правому краю; или по центру. Этот элемент является необязательным.

## <a name="defining-the-objects-that-use-the-table-view"></a>Определение объектов, используйте представление таблицы

Существует два способа определить, какие объекты .NET используйте представление таблицы. Можно использовать [ViewSelectedBy](./viewselectedby-element-format.md) можно использовать для определения объектов, которые могут отображаться все определения представления, или [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) элемент, чтобы определить, какие объекты будут отображаться по Определение конкретного представления. В большинстве случаев представление имеет только одно определение, поэтому обычно определяются объекты [ViewSelectedBy](./viewselectedby-element-format.md) элемент.

В следующем примере показано, как для определения объектов для отображения в представлении таблицы с помощью [ViewSelectedBy](./viewselectedby-element-format.md) и [TypeName](./typename-element-for-viewselectedby-format.md) элементов. Нет ограничений на число [TypeName](./typename-element-for-viewselectedby-format.md) элементов можно указать, что их порядок не имеет значения.

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>
```

Чтобы указать объекты, которые используются в представлении таблицы можно использовать следующие элементы XML:

- [ViewSelectedBy](./viewselectedby-element-format.md) элемент определяет объекты, отображаемые в представлении списка.

- [TypeName](./typename-element-for-viewselectedby-format.md) элемент указывает объект .NET, которое отображается в представлении. Полное имя типа .NET является обязательным. Необходимо указать по крайней мере один тип или выбора для представления, но есть не максимального количества элементов, которые могут быть указаны.

В следующем примере используется [ViewSelectedBy](./viewselectedby-element-format.md) и [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) элементов. Используйте наборы выделения, где, что у вас есть набор связанных объектов, которые отображаются в нескольких представлениях, например при определении представления списка и представление таблицы для те же объекты. Дополнительные сведения о том, как создать набор выбора см. в разделе [определение наборы выделения](./defining-selection-sets.md).

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>
```

Чтобы указать объекты, которые используются в представлении списка можно использовать следующие элементы XML:

- [ViewSelectedBy](./viewselectedby-element-format.md) элемент определяет объекты, отображаемые в представлении списка.

- [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) элемент указывает набор объектов, которые могут отображаться в представлении. Необходимо указать по крайней мере одного набора или тип для представления, но есть не максимального количества элементов, которые могут быть указаны.

В следующем примере показано, как для определения объектов, отображаемых командлетом точное определение таблицы представления, используя [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) элемент. С помощью этого элемента, можно указать имя типа .NET объект набора выбора объектов и выбора условие, которое указывает, когда используется определение. Дополнительные сведения о том, как для создания выделения условий см. в разделе [определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

> [!NOTE]
> При создании нескольких определений представления таблицы нельзя указать другой столбец заголовков. Можно указать только сведения, отображаемые в строках таблицы, например, какие объекты отображаются.

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</TableRowEntry>
```

Чтобы указать объекты, которые используются с конкретным определением в представлении списка можно использовать следующие элементы XML:

- [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) элемент определяет, какие объекты отображаются с помощью определения.

- [TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md) элемент указывает объект .NET, которое отображается с помощью определения. При использовании этого элемента, требуется полное имя типа .NET. Необходимо указать по крайней мере один тип, выбора или условию выбора для определения, но есть не максимального количества элементов, которые могут быть указаны.

- [SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) (не показано) указывает набор объектов, которые могут отображаться в соответствии с этим определением. Необходимо указать по крайней мере один тип, выбора или условию выбора для определения, но есть не максимального количества элементов, которые могут быть указаны.

- [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) элемент (не показано) определяет условие, которое должен существовать для данного определения для использования. Необходимо указать по крайней мере один тип, выбора или условию выбора для определения, но есть не максимального количества элементов, которые могут быть указаны. Дополнительные сведения об определении условий выборки см. в разделе [определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="using-format-strings"></a>С помощью строки формата

Строки форматирования можно добавить в представление, чтобы более детально определить способ отображения данных. Приведенный ниже показано, как определить строку форматирования для значения `StartTime` свойство.

```xml
<TableColumnItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</TableColumnItem>
```

Следующие элементы XML может использоваться для указания шаблона формата:

- [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) элемент определяет свойства или скрипта, значение которого отображается в столбце строки. Объект [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) элемент является обязательным для каждого столбца, строки. Первая запись отображается в первом столбце, вторая запись второго столбца и т. д.

- [PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) определяет свойство, значение которого отображается в строке. Необходимо указать свойство или сценария, но нельзя указать одновременно.

- [FormatString](./label-element-for-listitem-for-listcontrol-format.md) элемент задает шаблон формата, который определяет способ отображения значения свойства или скрипт.

В следующем примере `ToString` метод вызывается для форматирования значения переменной скрипта. Скрипты можно вызвать любой метод объекта. Таким образом Если объект имеет метод, такой как `ToString`, с параметрами форматирования, скрипт можно вызвать этот метод для форматирования значения выходных данных сценария.

```xml
<ListItem>
  <ScriptBlock>
    [String]::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</ListItem>
```

Следующий XML-элемент может использоваться для вызова метода `ToString` метод:

- [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) элемент определяет свойства или скрипта, значение которого отображается в столбце строки. Объект [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) элемент является обязательным для каждого столбца, строки. Первая запись отображается в первом столбце, вторая запись второго столбца и т. д.

- [ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) элемент указывает сценарий, значение которого отображается в строке. Необходимо указать сценарий или свойство, но нельзя указать одновременно.

## <a name="see-also"></a>См. также

[Запись файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
