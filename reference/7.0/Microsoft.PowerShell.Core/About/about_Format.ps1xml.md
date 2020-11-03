---
description: Начиная с PowerShell 6, представления по умолчанию для объектов определяются в исходном коде PowerShell.  Можно создать собственные файлы, `Format.ps1xml` чтобы изменить отображение объектов или определить отображение по умолчанию для новых типов объектов, создаваемых в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 11/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_format.ps1xml?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Format.ps1xml
ms.openlocfilehash: ea7a5262be912750b2a4ff6ce72060b31ccdfb8a
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231821"
---
# <a name="about-formatps1xml"></a>Сведения о Format.ps1XML

## <a name="short-description"></a>Краткое описание

Начиная с PowerShell 6, представления по умолчанию для объектов определяются в исходном коде PowerShell.

Можно создать собственные файлы, `Format.ps1xml` чтобы изменить отображение объектов или определить отображение по умолчанию для новых типов объектов, создаваемых в PowerShell.

## <a name="long-description"></a>Подробное описание

Начиная с PowerShell 6, представления по умолчанию определяются в исходном коде PowerShell. `Format.ps1xml`Файлы из powershell 5,1 и более ранних версий не существуют в PowerShell 6 и более поздних версиях.

Исходный код PowerShell определяет отображение объектов по умолчанию в консоли PowerShell. Можно создать собственные файлы, `Format.ps1xml` чтобы изменить отображение объектов или определить отображение по умолчанию для новых типов объектов, создаваемых в PowerShell.

Когда в PowerShell отображается объект, он использует данные в структурированных файлах форматирования для определения отображения объекта по умолчанию. Данные в файлах форматирования определяют, отображается ли объект в таблице или в списке, и определяет, какие свойства отображаются по умолчанию.

Форматирование влияет только на отображение. Он не влияет на то, какие свойства объекта передаются по конвейеру или каким способом они передаются. `Format.ps1xml` файлы нельзя использовать для настройки формата выходных данных для хэш-таблиц.

`.ps1xml`Файл форматирования может определять четыре различных представления каждого объекта:

- Таблица
- Список
- Широкий
- Другой

Например, когда выходные данные `Get-ChildItem` команды передаются в `Format-List` команду, `Format-List` использует представление списка, определенное в исходном коде, для определения способа отображения объектов файлов и папок в виде списка.

Если файл форматирования содержит более одного представления объекта, PowerShell применяет первое найденное представление.

В пользовательском `Format.ps1xml` файле представление определяется набором XML-тегов, описывающих имя представления, тип объекта, к которому он может быть применен, заголовки столбцов и свойства, отображаемые в тексте представления. Формат в `Format.ps1xml` файлах применяется непосредственно перед тем, как данные представлены пользователю.

## <a name="creating-new-formatps1xml-files"></a>Создание новых Format.ps1XML-файлов

Чтобы изменить формат отображения существующего представления объектов или добавить представления для новых объектов, создайте собственные `Format.ps1xml` файлы, а затем добавьте их в сеанс PowerShell.

Чтобы создать `Format.ps1xml` файл для определения пользовательского представления, используйте командлеты [Get-FormatData](xref:Microsoft.PowerShell.Utility.Get-FormatData) и [Export-FormatData](xref:Microsoft.PowerShell.Utility.Export-FormatData) . Для редактирования файла используйте текстовый редактор. Файл можно сохранить в любой каталог, к которому может получить доступ PowerShell, например в подкаталог `$HOME` .

Чтобы изменить форматирование текущего представления, найдите представление в файле форматирования, а затем используйте теги для изменения представления. Чтобы создать представление для нового типа объекта, создайте новое представление или используйте существующее представление в качестве модели. Теги описаны в следующем разделе. Затем можно удалить все остальные представления в файле, чтобы изменения были очевидны для любого, который просматривает файл.

После сохранения изменений используйте [Update-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData) , чтобы добавить новый файл в сеанс PowerShell. Если необходимо, чтобы представление было иметь приоритет над представлением, определенным во встроенных файлах, используйте параметр **препендпас** . `Update-FormatData` влияет только на текущий сеанс. Чтобы внести изменения во все будущие сеансы, добавьте `Update-FormatData` команду в профиль PowerShell.

### <a name="example-add-calendar-data-to-culture-objects"></a>Пример. Добавление данных календаря в объекты языка и региональных параметров

В этом примере показано, как изменить форматирование объектов языка и региональных параметров **System. Globalization. CultureInfo** , созданных `Get-Culture` командлетом в текущем сеансе PowerShell. Команды в примере добавляют свойство **Calendar** в представление таблицы по умолчанию, отображающее объекты языка и региональных параметров.

Чтобы начать, получите данные форматирования из файла исходного кода и создайте `Format.ps1xml` файл, содержащий текущее представление объектов языка и региональных параметров.

```powershell
Get-FormatData -TypeName System.Globalization.CultureInfo |
  Export-FormatData -Path $HOME\Format\CultureInfo.Format.ps1xml
```

Откройте `CultureInfo.Format.ps1xml` файл в любом XML-или текстовом редакторе, например Visual Studio Code. Следующий XML-код определяет представления объекта **CultureInfo** .

`CultureInfo.Format.ps1xml`Файл должен выглядеть, как в следующем примере:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Configuration>
  <ViewDefinitions>
    <View>
      <Name>System.Globalization.CultureInfo</Name>
      <ViewSelectedBy>
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
          <TableColumnHeader />
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
Update-FormatData -PrependPath $HOME\Format\CultureInfo.Format.ps1xml
```

Чтобы проверить изменение, введите `Get-Culture` и проверьте выходные данные, включающие в себя свойство **Calendar** .

```powershell
Get-Culture
```

```Output
LCID  Name   Calendar                                DisplayName
----  ----   --------                                -----------
1033  en-US  System.Globalization.GregorianCalendar  English (United States)
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

## <a name="tracing-formatps1xml-file-use"></a>Использование трассировки Format.ps1XML-файла

Чтобы обнаружить ошибки при загрузке или применении `Format.ps1xml` файлов, используйте `Trace-Command` командлет с любым из следующих компонентов формата в качестве значения параметра **Name** :

- форматфилелоадинг
- форматвиевбиндинг

Дополнительные сведения см. в разделе [Trace-Command](xref:Microsoft.PowerShell.Utility.Trace-Command) и [Get-TraceSource](xref:Microsoft.PowerShell.Utility.Get-TraceSource).

## <a name="signing-a-formatps1xml-file"></a>Подписывание Format.ps1XML-файла

Для защиты пользователей `Format.ps1xml` файла подпишите его с помощью цифровой подписи. Дополнительные сведения см. в разделе [about_Signing](about_Signing.md).

## <a name="sample-xml-for-a-format-table-custom-view"></a>Образец XML-кода для Format-Table пользовательского представления

Следующий образец XML-кода создает `Format-Table` пользовательское представление для объектов **System. IO. DirectoryInfo** и **System. IO. FileInfo** , созданных `Get-ChildItem` . Пользовательское представление называется **мигЦивиев** и добавляет столбец **CreationTime** в таблицу.

Чтобы создать пользовательское представление, используйте `Get-FormatData` `Export-FormatData` командлеты и для создания `.ps1xml` файла. Затем измените файл, `.ps1xml` чтобы создать код для пользовательского представления. `.ps1xml`Файл может храниться в любом каталоге, к которому может получить доступ PowerShell. Например, подкаталог `$HOME` .

После `.ps1xml` создания файла используйте `Update-FormatData` командлет, чтобы включить представление в текущий сеанс PowerShell. Также можно добавить команду Update в профиль PowerShell, если требуется представление, доступное во всех сеансах PowerShell.

В этом примере пользовательское представление должно использовать формат таблицы, в противном случае — `Format-Table` сбой.

Используйте `Format-Table` с параметром **View** , чтобы указать имя пользовательского представления, **мигЦивиев** и отформатировать выходные данные таблицы с помощью столбца **CreationTime** . Пример выполнения команды см. в разделе [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).

> [!NOTE]
> Хотя можно получить XML-код форматирования из исходного кода для создания пользовательского представления, для получения желаемого результата может потребоваться дополнительная разработка.

В следующей `Get-FormatData` команде есть альтернатива параметру **PowerShellVersion** , чтобы гарантировать возврат всех сведений о локальном форматировании. Используйте `-PowerShellVersion $PSVersionTable.PSVersion` вместо конкретной версии PowerShell.

```powershell
Get-FormatData -PowerShellVersion 5.1 -TypeName System.IO.DirectoryInfo |
   Export-FormatData -Path ./Mygciview.Format.ps1xml
Update-FormatData -AppendPath ./Mygciview.Format.ps1xml
```

```xml
<?xml version="1.0" encoding="utf-8"?>
<Configuration>
  <ViewDefinitions>
    <View>
      <Name>mygciview</Name>
      <ViewSelectedBy>
        <TypeName>System.IO.DirectoryInfo</TypeName>
        <TypeName>System.IO.FileInfo</TypeName>
      </ViewSelectedBy>
      <GroupBy>
        <PropertyName>PSParentPath</PropertyName>
      </GroupBy>
      <TableControl>
        <TableHeaders>
          <TableColumnHeader>
            <Label>Mode</Label>
            <Width>7</Width>
            <Alignment>Left</Alignment>
          </TableColumnHeader>
          <TableColumnHeader>
            <Label>LastWriteTime</Label>
            <Width>26</Width>
            <Alignment>Right</Alignment>
          </TableColumnHeader>
          <TableColumnHeader>
            <Label>CreationTime</Label>
            <Width>26</Width>
            <Alignment>Right</Alignment>
          </TableColumnHeader>
          <TableColumnHeader>
            <Label>Length</Label>
            <Width>14</Width>
            <Alignment>Right</Alignment>
          </TableColumnHeader>
          <TableColumnHeader>
            <Label>Name</Label>
            <Alignment>Left</Alignment>
          </TableColumnHeader>
        </TableHeaders>
        <TableRowEntries>
          <TableRowEntry>
            <Wrap />
            <TableColumnItems>
              <TableColumnItem>
                <PropertyName>ModeWithoutHardLink</PropertyName>
              </TableColumnItem>
              <TableColumnItem>
                <PropertyName>LastWriteTime</PropertyName>
              </TableColumnItem>
              <TableColumnItem>
                <PropertyName>CreationTime</PropertyName>
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
