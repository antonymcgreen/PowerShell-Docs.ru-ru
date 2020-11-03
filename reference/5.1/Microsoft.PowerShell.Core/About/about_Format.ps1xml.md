---
description: '`Format.ps1xml`Файлы в PowerShell определяют отображение объектов по умолчанию в консоли PowerShell. Можно создать собственные файлы, `Format.ps1xml` чтобы изменить отображение объектов или определить отображение по умолчанию для новых типов объектов, создаваемых в PowerShell.'
keywords: powershell,командлет
Locale: en-US
ms.date: 11/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_format.ps1xml?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Format.ps1xml
ms.openlocfilehash: be88007d23ab98b9c2f707b77f9c43578ba9887b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232045"
---
# <a name="about-formatps1xml"></a>Сведения о Format.ps1XML

## <a name="short-description"></a>Краткое описание

`Format.ps1xml`Файлы в PowerShell определяют отображение объектов по умолчанию в консоли PowerShell. Можно создать собственные файлы, `Format.ps1xml` чтобы изменить отображение объектов или определить отображение по умолчанию для новых типов объектов, создаваемых в PowerShell.

## <a name="long-description"></a>Подробное описание

`Format.ps1xml`Файлы в PowerShell определяют отображение объектов по умолчанию в PowerShell. Можно создать собственные файлы, `Format.ps1xml` чтобы изменить отображение объектов или определить отображение по умолчанию для новых типов объектов, создаваемых в PowerShell.

Когда в PowerShell отображается объект, он использует данные в структурированных файлах форматирования для определения отображения объекта по умолчанию. Данные в файлах форматирования определяют, отображается ли объект в таблице или в списке, и определяет, какие свойства отображаются по умолчанию.

Форматирование влияет только на отображение. Он не влияет на то, какие свойства объекта передаются по конвейеру или каким способом они передаются. `Format.ps1xml` файлы нельзя использовать для настройки формата выходных данных для хэш-таблиц.

PowerShell включает семь файлов форматирования. Эти файлы находятся в каталоге установки ( `$PSHOME` ). Каждый файл определяет отображение группы объектов Microsoft .NET Framework:

1. `Certificate.Format.ps1xml`

   Объекты в хранилище сертификатов, такие как сертификаты X. 509 и хранилища сертификатов.

1. `DotNetTypes.Format.ps1xml`

   Другие типы .NET Framework, например объекты CultureInfo, FileVersionInfo и EventLogEntry.

1. `FileSystem.Format.ps1xml`

   Объекты файловой системы, такие как файлы и каталоги.

1. `Help.Format.ps1xml`

   Представления справки, такие как подробные и полные представления, параметры и примеры.

1. `PowerShellCore.Format.ps1xml`

   Объекты, создаваемые командлетами PowerShell Core, например `Get-Member` и `Get-History` .

1. `PowerShellTrace.Format.ps1xml`

   Объекты трассировки, такие как созданные `Trace-Command` командлетом.

1. `Registry.Format.ps1xml`

   Объекты реестра, такие как ключи и записи.

Файл форматирования может определять четыре различных представления каждого объекта:

- Таблица
- Список
- Широкий
- Другой

Например, когда выходные данные `Get-ChildItem` команды передаются в `Format-List` команду, `Format-List` использует представление в `FileSystem.Format.ps1xml` файле для определения способа отображения объектов файла и папки в виде списка.

Если файл форматирования содержит более одного представления объекта, PowerShell применяет первое найденное представление.

В `Format.ps1xml` файле представление определяется набором XML-тегов, описывающих имя представления, тип объекта, к которому он может быть применен, заголовки столбцов и свойства, отображаемые в тексте представления. Формат в `Format.ps1xml` файлах применяется непосредственно перед тем, как данные представлены пользователю.

## <a name="creating-new-formatps1xml-files"></a>Создание новых Format.ps1XML-файлов

`.ps1xml`Файлы, устанавливаемые с помощью PowerShell, имеют цифровую подпись, чтобы предотвратить незаконное изменение, так как форматирование может включать блоки сценариев. Чтобы изменить формат отображения существующего представления объектов или добавить представления для новых объектов, создайте собственные `Format.ps1xml` файлы, а затем добавьте их в сеанс PowerShell.

Чтобы создать новый файл, скопируйте существующий `Format.ps1xml` файл. Новый файл может иметь любое имя, но он должен иметь `.ps1xml` расширение имени файла. Новый файл можно поместить в любой каталог, доступный для PowerShell, но при этом полезно поместить файлы в каталог установки PowerShell ( `$PSHOME` ) или в подкаталог каталога установки.

Чтобы изменить форматирование текущего представления, найдите представление в файле форматирования, а затем используйте теги для изменения представления. Чтобы создать представление для нового типа объекта, создайте новое представление или используйте существующее представление в качестве модели. Теги описаны в следующем разделе. Затем можно удалить все остальные представления в файле, чтобы изменения были очевидны для любого, который просматривает файл.

После сохранения изменений используйте `Update-FormatData` командлет, чтобы добавить новый файл в сеанс PowerShell. Если необходимо, чтобы представление было иметь приоритет над представлением, определенным во встроенных файлах, используйте параметр **препендпас** .
`Update-FormatData` влияет только на текущий сеанс. Чтобы внести изменения во все будущие сеансы, добавьте `Update-FormatData` команду в профиль PowerShell.

### <a name="example-adding-calendar-data-to-culture-objects"></a>Пример. Добавление данных календаря в объекты языка и региональных параметров

В этом примере показано, как изменить форматирование объектов языка и региональных параметров **System. Globalization. CultureInfo** , созданных `Get-Culture` командлетом в текущем сеансе PowerShell. Команды в примере добавляют свойство **Calendar** в представление таблицы по умолчанию, отображающее объекты языка и региональных параметров.

Первым шагом является поиск `Format.ps1xml` файла, содержащего текущее представление объектов языка и региональных параметров. Следующая `Select-String` команда находит файл:

```powershell
$Parms = @{
  Path = "$PSHOME\*Format.ps1xml"
  Pattern = "System.Globalization.CultureInfo"
}

Select-String @Parms
```

```Output
C:\Windows\System32\WindowsPowerShell\v1.0\DotNetTypes.format.ps1xml:113:
     <Name>System.Globalization.CultureInfo</Name>
C:\Windows\System32\WindowsPowerShell\v1.0\DotNetTypes.format.ps1xml:115:
<TypeName>System.Globalization.CultureInfo</TypeName>
```

Эта команда показывает, что определение находится в `DotNetTypes.Format.ps1xml` файле.

Следующая команда копирует содержимое файла в новый файл, `MyDotNetTypes.Format.ps1xml` .

```powershell
Copy-Item $PSHome\DotNetTypes.format.ps1xml MyDotNetTypes.Format.ps1xml
```

Откройте `MyDotNetTypes.Format.ps1xml` файл в любом XML-или текстовом редакторе, например Visual Studio Code. Найдите раздел объект **System. Globalization. CultureInfo** . Следующий XML-код определяет представления объекта **CultureInfo** . Объект имеет только представление **таблеконтрол** .

```xml
<View>
  <Name>System.Globalization.CultureInfo</Name>
  <ViewSelectedBy>
    <TypeName>Deserialized.System.Globalization.CultureInfo</TypeName>
    <TypeName>System.Globalization.CultureInfo</TypeName>
  </ViewSelectedBy>
  <TableControl>
    <TableHeaders>
      <TableColumnHeader>
        <Width>16</Width>
      </TableColumnHeader>
      <TableColumnHeader>
        <Width>16</Width>
      </TableColumnHeader>
    </TableHeaders>
    <TableRowEntries>
      <TableRowEntry>
        <TableColumnItems>
          <TableColumnItem>
            <PropertyName>LCID</PropertyName>
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

Удалите оставшуюся часть файла, за исключением открывающих `<?xml>` тегов, и, а `<Configuration>` `<ViewDefinitions>` также закрывающих `<ViewDefinitions>` `<Configuration>` тегов и. Если имеется цифровая подпись, удалите ее из пользовательского `Format.ps1xml` файла.

`MyDotNetTypes.Format.ps1xml`Теперь файл должен выглядеть, как в следующем примере:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Configuration>
<ViewDefinitions>
<View>
  <Name>System.Globalization.CultureInfo</Name>
  <ViewSelectedBy>
    <TypeName>Deserialized.System.Globalization.CultureInfo</TypeName>
    <TypeName>System.Globalization.CultureInfo</TypeName>
  </ViewSelectedBy>
  <TableControl>
    <TableHeaders>
      <TableColumnHeader>
        <Width>16</Width>
      </TableColumnHeader>
      <TableColumnHeader>
        <Width>16</Width>
      </TableColumnHeader>
      <TableColumnHeader/>
    </TableHeaders>
    <TableRowEntries>
      <TableRowEntry>
        <TableColumnItems>
          <TableColumnItem>
            <PropertyName>LCID</PropertyName>
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
</ViewDefinitions>
</Configuration>
```

Создайте новый столбец для свойства **Calendar** , добавив новый набор `<TableColumnHeader>` тегов. Значение свойства **Calendar** может быть длинным, поэтому укажите в качестве значения 45 символов `<Width>` .

```xml
<TableHeaders>
  <TableColumnHeader>
    <Width>16</Width>
  </TableColumnHeader>
  <TableColumnHeader>
    <Width>16</Width>
  </TableColumnHeader>
  <TableColumnHeader>
    <Width>45</Width>
  </TableColumnHeader>
  <TableColumnHeader/>
</TableHeaders>
```

Добавьте новый элемент столбца для **Calendar** в строки таблицы с помощью `<TableColumnItem>` `<PropertyName` тегов и.

```xml
<TableRowEntries>
  <TableRowEntry>
    <TableColumnItems>
      <TableColumnItem>
        <PropertyName>LCID</PropertyName>
      </TableColumnItem>
      <TableColumnItem>
        <PropertyName>Name</PropertyName>
      </TableColumnItem>
      <TableColumnItem>
        <PropertyName>Calendar</PropertyName>
      </TableColumnItem>
      <TableColumnItem>
        <PropertyName>DisplayName</PropertyName>
      </TableColumnItem>
    </TableColumnItems>
  </TableRowEntry>
</TableRowEntries>
```

Сохраните файл и закройте его. Используйте `Update-FormatData` , чтобы добавить новый файл форматирования в текущий сеанс PowerShell.

В этом примере используется параметр **препендпас** для размещения нового файла в порядке приоритета, отличном от исходного файла. Дополнительные сведения см. в разделе [Update-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData).

```powershell
Update-FormatData -PrependPath $PSHOME\MyDotNetTypes.Format.ps1xml
```

Чтобы проверить изменение, введите `Get-Culture` и проверьте выходные данные, включающие в себя свойство **Calendar** .

```powershell
Get-Culture
```

```Output
LCID Name  Calendar                               DisplayName
---- ----  --------                               -----------
1033 en-US System.Globalization.GregorianCalendar English (United States)
```

## <a name="the-xml-in-formatps1xml-files"></a>XML-файлы в Format.ps1XML-файлах

Полное определение схемы можно найти в файле [format. xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Format.xsd) в репозитории исходного кода PowerShell на сайте GitHub.

Раздел **виевдефинитионс** каждого `Format.ps1xml` файла содержит `<View>` теги, определяющие каждое представление. Типичный `<View>` тег содержит следующие Теги:

- `<Name>` Определяет имя представления.
- `<ViewSelectedBy>` Указывает тип или типы объектов, к которым применяется представление.
- `<GroupBy>` Указывает, как элементы представления будут объединены в группы.
- `<TableControl>`, `<ListControl>` , `<WideControl>` и `<CustomControl>` содержат теги, которые определяют, как будет отображаться каждый элемент.

### <a name="viewselectedby-tag"></a>Тег Виевселектедби

`<ViewSelectedBy>`Тег может содержать `<TypeName>` тег для каждого типа объектов, к которому применяется представление. Или может содержать `<SelectionSetName>` тег, который ссылается на набор выбора, определенный в других местах с помощью `<SelectionSet>` тега.

### <a name="groupby-tag"></a>Тег GroupBy

`<GroupBy>`Тег содержит `<PropertyName>` тег, указывающий свойство объекта, по которому группируются элементы. Он также содержит `<Label>` тег, указывающий строку, которая будет использоваться в качестве метки для каждой группы `<CustomControlName>` , или тег, который ссылается на пользовательский элемент управления, определенный в любом расположении с помощью `<Control>` тега. `<Control>`Тег содержит `<Name>` тег и `<CustomControl>` тег.

### <a name="tablecontroltag"></a>таблеконтролтаг

`<TableControl>`Тег обычно содержит `<TableHeaders>` теги и `<TableRowEntries>` , определяющие форматирование головок и строк таблицы. `<TableHeaders>`Тег обычно содержит `<TableColumnHeader>` теги, которые содержат `<Label>` теги, `<Width>` и `<Alignment>` . `<TableRowEntries>`Тег содержит `<TableRowEntry>` теги для каждой строки в таблице. `<TableRowEntry>`Тег содержит `<TableColumnItems>` тег, который содержит `<TableColumnItem>` тег для каждого столбца в строке. Как правило, `<TableColumnItem>` тег содержит либо `<PropertyName>` тег, определяющий свойство объекта, которое должно отображаться в определенном расположении, либо `<ScriptBlock>` тег, содержащий код скрипта, который вычисляет результат, отображаемый в расположении.

> [!NOTE]
> Блоки сценариев также можно использовать в других местах, где вычисленные результаты могут быть полезными.

`<TableColumnItem>`Тег также может содержать `<FormatString>` тег, указывающий, как будут отображаться свойство или вычисляемые результаты.

### <a name="listcontrol-tag"></a>Тег ListControl

`<ListControl>`Тег обычно содержит `<ListEntries>` тег. `<ListEntries>`Тег содержит `<ListEntry>` тег. `<ListEntry>`Тег содержит `<ListItems>` тег. `<ListItems>`Тег содержит `<ListItem>` теги, которые содержат `<PropertyName>` теги. `<PropertyName>`Теги указывают свойство объекта, которое должно отображаться в указанном месте списка. Если выбор представления определен с помощью набора элементов, `<ListControl>` `<ListEntry>` теги и также могут содержать `<EntrySelectedBy>` тег, содержащий один или несколько `<TypeName>` тегов. Эти `<TypeName>` теги указывают тип объекта, который должен `<ListControl>` отображаться в теге.

### <a name="widecontrol-tag"></a>Тег Видеконтрол

`<WideControl>`Тег обычно содержит `<WideEntries>` тег. `<WideEntries>`Тег содержит один или несколько `<WideEntry>` тегов. `<WideEntry>`Тег обычно содержит `<PropertyName>` тег, указывающий свойство, которое должно отображаться в указанном месте представления. `<PropertyName>`Тег может содержать `<FormatString>` тег, указывающий, как должно отображаться свойство.

### <a name="customcontrol-tag"></a>Тег ошибка customcontrol

`<CustomControl>`Тег позволяет использовать блок скрипта для определения формата. `<CustomControl>`Тег обычно содержит `<CustomEntries>` тег, который содержит несколько `<CustomEntry>` тегов. Каждый `<CustomEntry>` тег содержит `<CustomItem>` тег, который может содержать различные теги, которые задают содержимое и форматирование указанного расположения в представлении, включая `<Text>` `<Indentation>` теги,, `<ExpressionBinding>` и `<NewLine>` .

## <a name="default-displays-in-typesps1xml"></a>Отображение по умолчанию в Types.ps1XML

По умолчанию отображаются некоторые базовые типы объектов, определенные в `Types.ps1xml` файле в `$PSHOME` каталоге. Узлы имеют имя **псстандардмемберс** , а подузлы используют один из следующих тегов:

- `<DefaultDisplayProperty>`
- `<DefaultDisplayPropertySet>`
- `<DefaultKeyPropertySet>`

Дополнительные сведения см. в разделе [about_Types.ps1XML](about_Types.ps1xml.md).

## <a name="tracing-formatps1xml-file-use"></a>Использование трассировки Format.ps1XML-файла

Чтобы обнаружить ошибки при загрузке или применении `Format.ps1xml` файлов, используйте `Trace-Command` командлет с любым из следующих компонентов формата в качестве значения параметра **Name** :

- форматфилелоадинг
- форматвиевбиндинг

Дополнительные сведения см. в разделе [Trace-Command](xref:Microsoft.PowerShell.Utility.Trace-Command) и [Get-TraceSource](xref:Microsoft.PowerShell.Utility.Get-TraceSource).

## <a name="signing-a-formatps1xml-file"></a>Подписывание Format.ps1XML-файла

Для защиты пользователей `Format.ps1xml` файла подпишите его с помощью цифровой подписи. Дополнительные сведения см. в разделе [about_Signing](about_Signing.md).

## <a name="sample-xml-for-a-format-table-custom-view"></a>Образец XML-кода для Format-Table пользовательского представления

В следующем примере создается `Format-Table` пользовательское представление для объектов **System. IO. DirectoryInfo** и **System. IO. FileInfo** , созданных `Get-ChildItem` . Пользовательское представление называется **мигЦивиев** и добавляет столбец **CreationTime** в таблицу.

Пользовательское представление создается из измененной версии `FileSystem.Format.ps1xml` файла, хранящегося в в `$PSHOME` PowerShell 5,1.

После сохранения пользовательского `.ps1xml` файла используйте `Update-FormatData` для включения представления в сеанс PowerShell. В этом примере пользовательское представление должно использовать формат таблицы, в противном случае — `Format-Table` сбой.

Используйте `Format-Table` с параметром **View** , чтобы указать имя пользовательского представления и отформатировать выходные данные таблицы. Пример выполнения команды см. в разделе [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).

```powershell
$Parms = @{
  Path = "$PSHOME\*Format.ps1xml"
  Pattern = "System.IO.DirectoryInfo"
}
Select-String @Parms
Copy-Item $PSHome\FileSystem.format.ps1xml .\MyFileSystem.Format.ps1xml
Update-FormatData -PrependPath $PSHOME\Format\MyFileSystem.Format.ps1xml
```

> [!NOTE]
> Чтобы вписать образец XML в ограничения по ширине строк, необходимо сжать некоторые отступы и использовать разрывы строк в коде.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Configuration>
    <SelectionSets>
        <SelectionSet>
            <Name>FileSystemTypes</Name>
            <Types>
                <TypeName>System.IO.DirectoryInfo</TypeName>
                <TypeName>System.IO.FileInfo</TypeName>
            </Types>
        </SelectionSet>
    </SelectionSets>
<Controls>
<Control>
<Name>FileSystemTypes-GroupingFormat</Name>
<CustomControl>
 <CustomEntries>
  <CustomEntry>
    <CustomItem>
    <Frame>
    <LeftIndent>4</LeftIndent>
    <CustomItem>
    <Text AssemblyName="System.Management.Automation"
    BaseName="FileSystemProviderStrings"
    ResourceId="DirectoryDisplayGrouping"/>
    <ExpressionBinding>
     <ScriptBlock>
      $_.PSParentPath.Replace("Microsoft.PowerShell.Core\FileSystem::", "")
     </ScriptBlock>
    </ExpressionBinding>
    <NewLine/>
    </CustomItem>
    </Frame>
    </CustomItem>
    </CustomEntry>
 </CustomEntries>
</CustomControl>
</Control>
</Controls>
<ViewDefinitions>
    <View>
    <Name>mygciview</Name>
    <ViewSelectedBy>
        <SelectionSetName>FileSystemTypes</SelectionSetName>
    </ViewSelectedBy>
    <GroupBy>
      <PropertyName>PSParentPath</PropertyName>
      <CustomControlName>FileSystemTypes-GroupingFormat</CustomControlName>
    </GroupBy>
        <TableControl>
            <TableHeaders>
                <TableColumnHeader>
                    <Label>Mode</Label>
                    <Width>7</Width>
                    <Alignment>left</Alignment>
                </TableColumnHeader>
                <TableColumnHeader>
                    <Label>LastWriteTime</Label>
                    <Width>25</Width>
                    <Alignment>right</Alignment>
                </TableColumnHeader>
                <TableColumnHeader>
                    <Label>CreationTime</Label>
                    <Width>25</Width>
                    <Alignment>right</Alignment>
                </TableColumnHeader>
                <TableColumnHeader>
                    <Label>Length</Label>
                    <Width>14</Width>
                    <Alignment>right</Alignment>
                </TableColumnHeader>
                <TableColumnHeader/>
            </TableHeaders>
            <TableRowEntries>
                <TableRowEntry>
                    <Wrap/>
                    <TableColumnItems>
                        <TableColumnItem>
                            <PropertyName>Mode</PropertyName>
                        </TableColumnItem>
                        <TableColumnItem>
                            <ScriptBlock>
                                [String]::Format("{0,10}  {1,8}",
                                    $_.LastWriteTime.ToString("d"),
                                    $_.LastWriteTime.ToString("t"))
                            </ScriptBlock>
                        </TableColumnItem>
                        <TableColumnItem>
                            <ScriptBlock>
                                [String]::Format("{0,10}  {1,8}",
                                    $_.CreationTime.ToString("d"),
                                    $_.LastWriteTime.ToString("t"))
                            </ScriptBlock>
                        </TableColumnItem>
                        <TableColumnItem>
                        <PropertyName>Length</PropertyName>
                        </TableColumnItem>
                        <TableColumnItem>
                            <PropertyName>Name</PropertyName>
                        </TableColumnItem>
                    </TableColumnItems>
                </TableRowEntry>
            </TableRowEntries>
        </TableControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

## <a name="see-also"></a>См. также статью

[Export-FormatData](xref:Microsoft.PowerShell.Utility.Export-FormatData)

[Get-FormatData;](xref:Microsoft.PowerShell.Utility.Get-FormatData)

[Get-TraceSource](xref:Microsoft.PowerShell.Utility.Get-TraceSource)

[Ссылка на схему формата XML](/powershell/scripting/developer/format/format-schema-xml-reference)

[Trace-Command](xref:Microsoft.PowerShell.Utility.Trace-Command)

[Update-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData)

[Написание файла форматирования PowerShell](/powershell/scripting/developer/format/writing-a-powershell-formatting-file)
