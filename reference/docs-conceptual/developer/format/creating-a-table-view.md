---
ms.date: 09/13/2016
ms.topic: reference
title: Создание представления таблицы
description: Создание представления таблицы
ms.openlocfilehash: 035d42f7968a9e8babec692a7a5873e24b36cd97
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660290"
---
# <a name="creating-a-table-view"></a>Создание представления таблицы

Табличное представление отображает данные в одном или нескольких столбцах. Каждая строка в таблице представляет объект .NET, а каждый столбец таблицы представляет свойство объекта или значение скрипта. Можно определить табличное представление, в котором отображаются все свойства объекта или подмножество свойств объекта.

## <a name="a-table-view-display"></a>Отображение табличного представления

В следующем примере показано, как Windows PowerShell отображает объект [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) , возвращаемый командлетом [Get-Service](/powershell/module/microsoft.powershell.management/get-service) . Для этого объекта в Windows PowerShell определено табличное представление, в котором отображается `Status` свойство, `Name` свойство (это свойство является свойством псевдонима для `ServiceName` Свойства) и `DisplayName` свойство. Каждая строка в таблице представляет объект, возвращаемый командлетом.

```output
Status   Name               DisplayName
------   ----               -----------
Stopped  AJRouter           AllJoyn Router Service
Stopped  ALG                Application Layer Gateway Service
Stopped  AppIDSvc           Application Identity
Running  Appinfo            Application Information
```

## <a name="defining-the-table-view"></a>Определение табличного представления

В следующем коде XML показана схема табличного представления для отображения [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) , объект. Необходимо указать каждое свойство, которое должно отображаться в представлении таблицы.

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

Для определения представления списка используются следующие XML-элементы:

- Элемент [View](./view-element-format.md) является родительским элементом табличного представления. (Это тот же родительский элемент для представлений list, Wide и Custom Control.)

- Элемент [Name](./name-element-for-view-format.md) указывает имя представления. Этот элемент является обязательным для всех представлений.

- Элемент [виевселектедби](./viewselectedby-element-format.md) определяет объекты, которые используют представление. Этот элемент является обязательным.

- Элемент [GroupBy](./groupby-element-for-view-format.md) (не показан в этом примере) определяет, когда отображается новая группа объектов. Новая группа запускается каждый раз при изменении значения определенного свойства или сценария. Этот элемент является необязательным.

- Элемент [Controls](./controls-element-for-view-format.md) (не показан в этом примере) определяет пользовательские элементы управления, определенные табличным представлением. Элементы управления позволяют дополнительно указать способ отображения данных. Этот элемент является необязательным. Представление может определять собственные пользовательские элементы управления или использовать стандартные элементы управления, которые могут использоваться любыми представлениями в файле форматирования. Дополнительные сведения о пользовательских элементах управления см. в разделе [Создание пользовательских элементов управления](./creating-custom-controls.md).

- Элемент [хидетаблехеадерс](./hidetableheaders-element-format.md) (не показан в этом примере) указывает, что в таблице не будут отображаться метки в верхней части таблицы. Этот элемент является необязательным.

- Элемент [таблеконтрол](./tablecontrol-element-format.md) , определяющий заголовок и сведения о строках таблицы. Как и в других представлениях, табличное представление может отображать значения свойств объектов или значений, создаваемых скриптами.

## <a name="defining-column-headers"></a>Определение заголовков столбцов

1. Элемент [таблехеадерс](./tableheaders-element-format.md) и его дочерние элементы определяют, что отображается в верхней части таблицы.

2. Элемент [таблеколумнхеадер](./tablecolumnheader-element-format.md) определяет, что отображается в верхней части столбца таблицы. Укажите эти элементы в том порядке, в котором должны отображаться заголовки.

   Число элементов в представлении таблицы, которое можно использовать, не ограничено, но число [таблеколумнхеадер](./tablecolumnheader-element-format.md) в таблице должно равняться числу используемых элементов [таблеровентри](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md) .

3. Элемент [Label](./label-element-for-tablecolumnheader-for-tablecontrol-format.md) указывает отображаемый текст. Этот элемент является необязательным.

4. Элемент [Width](./width-element-for-tablecolumnheader-for-tablecontrol-format.md) задает ширину столбца (в символах). Этот элемент является необязательным.

5. Элемент [alignment](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md) определяет способ отображения метки. Метка может быть выровнена слева, справа или по центру. Этот элемент является необязательным.

## <a name="defining-the-table-rows"></a>Определение строк таблицы

Табличные представления могут содержать одно или несколько определений, которые определяют, какие данные отображаются в строках таблицы с помощью дочерних элементов элемента [таблеровентриес](./tablerowentries-element-for-tablecontrol-format.md) . Обратите внимание, что можно указать несколько определений для строк таблицы, но заголовки строк остаются неизменными независимо от того, какое определение строки используется. Как правило, таблица будет иметь только одно определение.

В следующем примере представление предоставляет одно определение, в котором отображаются значения нескольких свойств [System. Diagnostics. Process? DisplayProperty = FullName](/dotnet/api/System.Diagnostics.Process) , объект. Табличное представление может отображать значение свойства или значение скрипта (не показано в примере) в его строках.

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

Для определения строки можно использовать следующие XML-элементы:

- Элемент [таблеровентриес](./tablerowentries-element-for-tablecontrol-format.md) и его дочерние элементы определяют, что отображается в строках таблицы.

- Элемент [таблеровентри](./listentry-element-for-listcontrol-format.md) предоставляет определение строки. Требуется по крайней мере один [таблеровентри](./listentry-element-for-listcontrol-format.md) ; Однако максимальное количество элементов, которые можно добавить, не ограничено. В большинстве случаев представление будет иметь только одно определение.

- Элемент [ентриселектедби](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) указывает объекты, отображаемые конкретным определением. Этот элемент является необязательным и необходим только при определении нескольких элементов [таблеровентри](./listentry-element-for-listcontrol-format.md) , отображающих разные объекты.

- Элемент [Wrap](./wrap-element-for-tablerowentry-for-tablecontrol-format.md) указывает, что текст, превышающий ширину столбца, отображается на следующей строке. По умолчанию текст, не уместившийся по ширине столбца, усекается.

- Элемент [таблеколумнитемс](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md) определяет свойства или скрипты, значения которых отображаются в строке.

- Элемент [таблеколумнитем](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) определяет свойство или скрипт, значение которого отображается в столбце строки. Для каждого столбца строки требуется элемент [таблеколумнитем](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) . Первая запись отображается в первом столбце, второй элемент во втором столбце и т. д.

- Элемент [PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) указывает свойство, значение которого отображается в строке. Необходимо указать либо свойство, либо скрипт, но нельзя указать и то, и другое.

- Элемент [ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) указывает скрипт, значение которого отображается в строке. Необходимо указать либо скрипт, либо свойство, но нельзя указать и то, и другое.

- Элемент [FormatString](./label-element-for-listitem-for-listcontrol-format.md) задает шаблон формата, определяющий способ отображения значения свойства или скрипта. Этот элемент является необязательным.

- Элемент [alignment](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md) определяет, как отображается значение свойства или скрипта. Значение может быть выровнено слева, справа или по центру. Этот элемент является необязательным.

## <a name="defining-the-objects-that-use-the-table-view"></a>Определение объектов, использующих табличное представление

Существует два способа определения объектов .NET, использующих табличное представление. Элемент [виевселектедби](./viewselectedby-element-format.md) можно использовать для определения объектов, которые могут отображаться всеми определениями представления, или можно использовать элемент [ентриселектедби](./entryselectedby-element-for-listentry-for-listcontrol-format.md) для определения объектов, отображаемых определенным определением представления. В большинстве случаев представление имеет только одно определение, поэтому объекты обычно определяются элементом [виевселектедби](./viewselectedby-element-format.md) .

В следующем примере показано, как определить объекты, отображаемые табличным представлением с помощью элементов [виевселектедби](./viewselectedby-element-format.md) и [TypeName](./typename-element-for-viewselectedby-format.md) . Количество элементов [TypeName](./typename-element-for-viewselectedby-format.md) , которые можно указать, не ограничено, и их порядок не важен.

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>
```

Для указания объектов, используемых табличным представлением, можно использовать следующие XML-элементы:

- Элемент [виевселектедби](./viewselectedby-element-format.md) определяет, какие объекты отображаются в представлении списка.

- Элемент [TypeName](./typename-element-for-viewselectedby-format.md) задает объект .NET, отображаемый представлением. Требуется полное имя типа .NET. Необходимо указать по крайней мере один тип или набор элементов для представления, но максимальное количество заданных объектов не предусмотрено.

В следующем примере используются элементы [виевселектедби](./viewselectedby-element-format.md) и [селектионсетнаме](./selectionsetname-element-for-viewselectedby-format.md) . Используйте наборы выбора, в которых имеется связанный набор объектов, отображаемых с помощью нескольких представлений, например при определении представления списка и табличного представления для тех же объектов. Дополнительные сведения о создании набора выбора см. в разделе [Определение наборов выбора](./defining-selection-sets.md).

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>
```

Для указания объектов, используемых представлением списка, можно использовать следующие XML-элементы:

- Элемент [виевселектедби](./viewselectedby-element-format.md) определяет, какие объекты отображаются в представлении списка.

- Элемент [селектионсетнаме](./selectionsetname-element-for-viewselectedby-format.md) указывает набор объектов, которые могут быть отображены представлением. Необходимо указать хотя бы один набор выбора или тип для представления, но максимальное количество элементов, которое можно указать, не существует.

В следующем примере показано, как определить объекты, отображаемые определенным определением табличного представления с помощью элемента [ентриселектедби](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) . С помощью этого элемента можно указать имя типа .NET объекта, набор элементов выбора объектов или условие выбора, которое указывает, когда используется определение. Дополнительные сведения о создании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

> [!NOTE]
> При создании нескольких определений табличного представления нельзя указывать разные заголовки столбцов. Можно указать только то, что отображается в строках таблицы, например, какие объекты отображаются.

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</TableRowEntry>
```

Следующие XML-элементы можно использовать для указания объектов, которые используются в определенном определении представления списка:

- Элемент [ентриселектедби](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) определяет, какие объекты отображаются в определении.

- Элемент [TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md) указывает объект .NET, который отображается в определении. При использовании этого элемента требуется полное имя типа .NET. Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения, но максимальное число элементов, которое можно указать, не предусмотрено.

- Элемент [селектионсетнаме](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) (не показан) задает набор объектов, которые могут отображаться в этом определении. Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения, но максимальное число элементов, которое можно указать, не предусмотрено.

- Элемент [селектионкондитион](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) (не показано) указывает условие, которое должно существовать, чтобы использовать это определение. Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения, но максимальное число элементов, которое можно указать, не предусмотрено. Дополнительные сведения об определении условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).

## <a name="using-format-strings"></a>Использование строк формата

Строки форматирования можно добавить в представление, чтобы дополнительно определить способ отображения данных. В следующем примере показано, как определить строку форматирования для значения `StartTime` Свойства.

```xml
<TableColumnItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</TableColumnItem>
```

Для указания шаблона формата можно использовать следующие XML-элементы:

- Элемент [таблеколумнитем](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) определяет свойство или скрипт, значение которого отображается в столбце строки. Для каждого столбца строки требуется элемент [таблеколумнитем](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) . Первая запись отображается в первом столбце, второй элемент во втором столбце и т. д.

- Элемент [PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) указывает свойство, значение которого отображается в строке. Необходимо указать либо свойство, либо скрипт, но нельзя указать и то, и другое.

- Элемент [FormatString](./label-element-for-listitem-for-listcontrol-format.md) задает шаблон формата, определяющий способ отображения значения свойства или скрипта.

В следующем примере `ToString` метод вызывается для форматирования значения скрипта. Скрипты могут вызывать любой метод объекта. Таким образом, если у объекта есть метод, такой как `ToString` , имеющий параметры форматирования, скрипт может вызвать этот метод для форматирования выходного значения скрипта.

```xml
<ListItem>
  <ScriptBlock>
    [String]::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</ListItem>
```

Для вызова метода можно использовать следующий XML-элемент `ToString` :

- Элемент [таблеколумнитем](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) определяет свойство или скрипт, значение которого отображается в столбце строки. Для каждого столбца строки требуется элемент [таблеколумнитем](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) . Первая запись отображается в первом столбце, второй элемент во втором столбце и т. д.

- Элемент [ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) указывает скрипт, значение которого отображается в строке. Необходимо указать либо скрипт, либо свойство, но нельзя указать и то, и другое.

## <a name="see-also"></a>См. также:

[Написание файла форматирования PowerShell](./writing-a-powershell-formatting-file.md)
