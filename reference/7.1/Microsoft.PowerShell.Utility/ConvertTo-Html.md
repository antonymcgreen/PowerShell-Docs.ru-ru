---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-html?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Html
ms.openlocfilehash: 27a1d2994dee46b9e5bfd54132ff4a665330c2b4
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2020
ms.locfileid: "93230373"
---
# ConvertTo-Html

## Краткий обзор
Преобразует объекты .NET в код HTML, который может отображаться в веб-браузере.

## SYNTAX

### Страница (по умолчанию)

```
ConvertTo-Html [-InputObject <PSObject>] [[-Property] <Object[]>] [[-Body] <String[]>]
 [[-Head] <String[]>] [[-Title] <String>] [-As <String>] [-CssUri <Uri>] [-PostContent <String[]>]
 [-PreContent <String[]>] [-Meta <Hashtable>] [-Charset <String>] [-Transitional]
 [<CommonParameters>]
```

### Fragment

```
ConvertTo-Html [-InputObject <PSObject>] [[-Property] <Object[]>] [-As <String>] [-Fragment]
 [-PostContent <String[]>] [-PreContent <String[]>] [<CommonParameters>]
```

## DESCRIPTION

`ConvertTo-Html`Командлет преобразует объекты .NET в формат HTML, который может отображаться в веб-браузере. Этот командлет можно использовать для отображения выходных данных команды на веб-странице.

С помощью параметров можно `ConvertTo-Html` выбрать свойства объекта, указать формат таблицы или списка, указать заголовок HTML-страницы, добавить текст до и после объекта, а также вернуть только фрагмент таблицы или списка, а не определенную страницу DTD.

При отправке нескольких объектов в `ConvertTo-Html` PowerShell создает таблицу (или список) на основе свойств первого отправленного объекта. Если у оставшихся объектов нет одного из указанных свойств, значением свойства этого объекта является пустая ячейка. Если оставшиеся объекты содержат дополнительные свойства, их значения не включаются в файл.

## Примеры

### Пример 1. Создание веб-страницы для вывода даты

```powershell
ConvertTo-Html -InputObject (Get-Date)
```

Эта команда создает HTML-страницу, на которой отображаются свойства текущей даты. Он использует параметр **InputObject** для отправки результатов `Get-Date` команды в `ConvertTo-Html` командлет.

### Пример 2. Создание веб-страницы для вывода псевдонимов PowerShell

```powershell
Get-Alias | ConvertTo-Html | Out-File aliases.htm
Invoke-Item aliases.htm
```

Эта команда создает HTML-страницу, в которой перечислены псевдонимы PowerShell в текущей консоли.

Команда использует `Get-Alias` командлет для получения псевдонимов. Он использует оператор конвейера ( `|` ) для отправки псевдонимов в `ConvertTo-Html` командлет, который создает HTML-страницу. Команда также использует `Out-File` командлет для отправки HTML-кода в `aliases.htm` файл.

### Пример 3. Создание веб-страницы для вывода событий PowerShell

```powershell
`Get-EventLog` -LogName "Windows PowerShell" | ConvertTo-Html | Out-File pslog.htm
```

Эта команда создает HTML-страницу `pslog.htm` с именем, которая отображает события в журнале событий Windows PowerShell на локальном компьютере.

Он использует `Get-EventLog` командлет для получения событий в журнале Windows PowerShell, а затем использует оператор конвейера ( `|` ) для отправки событий в `ConvertTo-Html` командлет. Команда также использует `Out-File` командлет для отправки HTML-кода в `pslog.htm` файл.

Команда также использует `Out-File` командлет для отправки HTML-кода в `pslog.htm` файл.

### Пример 4. Создание веб-страницы для показа процессов

```powershell
Get-Process |
  ConvertTo-Html -Property Name, Path, Company -Title "Process Information" |
    Out-File proc.htm
Invoke-Item proc.htm
```

Эти команды создают и открывают HTML-страницу, содержащую имя, путь и компанию для процессов на локальном компьютере.

Первая команда использует `Get-Process` командлет для получения объектов, представляющих процессы, запущенные на компьютере. Команда использует оператор конвейера ( `|` ) для отправки объектов процесса в `ConvertTo-Html` командлет.

Команда использует параметр **Property** для выбора трех свойств объектов процесса, которые должны быть добавлены в таблицу. Команда использует параметр **Title** для указания заголовка HTML-страницы. Команда также использует `Out-File` командлет для отправки полученного HTML-кода в файл с именем Proc.htm.

Вторая команда использует `Invoke-Item` командлет для открытия в `Proc.htm` браузере по умолчанию.

### Пример 5. Создание веб-страницы для вывода объектов службы

```powershell
Get-Service | ConvertTo-Html -CssUri "test.css"
```

```Output
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"  "https://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
<html>
<head>
<title>HTML TABLE</title>
<link rel="stylesheet" type="text/css" href="test.css" />
...
```

Эта команда создает HTML-страницу объектов службы, `Get-Service` возвращаемых командлетом. Команда использует параметр **кссури** для указания каскадной таблицы стилей для HTML-страницы.

Параметр **кссури** добавляет дополнительный `<link rel="stylesheet" type="text/css" href="test.css">` тег в результирующий HTML-код. Атрибут HREF в теге содержит имя таблицы стилей.

### Пример 6. Создание веб-страницы для вывода объектов службы

```powershell
Get-Service | ConvertTo-Html -As LIST | Out-File services.htm
```

Эта команда создает HTML-страницу объектов службы, `Get-Service` возвращаемых командлетом. Команда использует параметр **as** для задания формата списка. Командлет `Out-File` отправляет полученный HTML-код в `Services.htm` файл.

### Пример 7. Создание веб-таблицы для текущей даты

```powershell
Get-Date | ConvertTo-Html -Fragment
```

```Output
<table>
<colgroup>...</colgroup>
<tr><th>DisplayHint</th><th>DateTime</th><th>Date</th><th>Day</th><th>DayOfWeek</th><th>DayOfYear</th><th>Hour</th>
<th>Kind</th><th>Millisecond</th><th>Minute</th><th>Month</th><th>Second</th><th>Ticks</th><th>TimeOfDay</th><th>Year</th></tr>
<tr><td>DateTime</td><td>Monday, May 05, 2008 10:40:04 AM</td><td>5/5/2008 12:00:00 AM</td><td>5</td><td>Monday</td>
<td>126</td><td>10</td><td>Local</td><td>123</td><td>40</td><td>5</td><td>4</td><td>633455808041237213</td><td>10:40:04.12
37213</td><td>2008</td></tr>
</table>
```

Эта команда использует `ConvertTo-Html` для создания HTML-таблицы текущей даты. Команда использует `Get-Date` командлет для получения текущей даты. Для отправки результатов в командлет используется оператор конвейера (|) `ConvertTo-Html` .

`ConvertTo-Html`Команда включает параметр **Fragment** , который ограничивает выходные данные HTML-таблицей. В результате другие элементы HTML-страницы, например теги `<HEAD>` и `<BODY>`, пропускаются.

### Пример 8. Создание веб-страницы для вывода событий PowerShell

```powershell
Get-EventLog -Log "Windows PowerShell" | ConvertTo-Html -Property id, level, task
```

Эта команда использует `Get-EventLog` командлет для получения событий из журнала событий Windows PowerShell.

Он использует оператор конвейера ( `|` ) для отправки событий в `ConvertTo-Html` командлет, который преобразует события в формат HTML.

`ConvertTo-Html`Команда использует параметр **Property** для выбора только свойств **ID** , **Level** и **Task** события.

### Пример 9. Создание веб-страницы для показа указанных служб

```powershell
$htmlParams = @{
  Title = "Windows Services: Server01"
  Body = Get-Date
  PreContent = "<P>Generated by Corporate IT</P>"
  PostContent = "For details, contact Corporate IT."
}
Get-Service A* |
  ConvertTo-Html @htmlParams |
    Out-File Services.htm
Invoke-Item Services.htm
```

Эта команда создает и открывает веб-страницу, в которой отображаются службы на компьютере, начинающиеся с. Для настройки выходных данных в нем используются параметры **Title** , **Body** , for **Content** и My **Content** `ConvertTo-Html` .

Первая часть команды использует `Get-Service` командлет для получения служб на компьютере, который начинается с. Команда использует оператор конвейера ( `|` ) для отправки результатов в `ConvertTo-Html` командлет. Команда также использует `Out-File` командлет для отправки выходных данных в файл Services.htm.

Точка с запятой ( `;` ) завершает первую команду и запускает вторую команду, которая использует `Invoke-Item` командлет для открытия `Services.htm` файла в браузере по умолчанию.

### Пример 10. Задание свойств meta и charset HTML

```powershell
Get-Service | ConvertTo-HTML -Meta @{
  refresh=10
  author="Author's Name"
  keywords="PowerShell, HTML, ConvertTo-HTML"
} -Charset "UTF-8"
```

Эта команда создает HTML для веб-страницы с тегами meta для обновления, создания и ключевых слов.
Кодировка для страницы равна UTF-8

### Пример 11. Настройка переходного формата HTML в формат XHTML

```powershell
Get-Service | ConvertTo-HTML -Transitional
```

Эта команда устанавливает DOCTYPE возвращаемого HTML-кода в XHTML Transitional DTD

## PARAMETERS

### — Как

Определяет, форматируется ли объект как таблица или список. Допустимые значения: **Table** и **List** . Значение по умолчанию — **Table** .

**Табличное** значение создает таблицу HTML, похожую на формат таблицы PowerShell. В строке заголовка отображаются имена свойств. Каждая строка таблицы представляет объект и отображает значения объекта для каждого свойства.

Значение **списка** создает таблицу HTML с двумя столбцами для каждого объекта, который напоминает формат списка PowerShell. В первом столбце отображается имя свойства. Во втором столбце отображается значение свойства.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Table, List

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Body

Задает текст, добавляемый после открывающего тега `<BODY>`. По умолчанию текст в этой позиции отсутствует.

```yaml
Type: System.String[]
Parameter Sets: Page
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Charset

Задает текст, добавляемый в открывающий `<charset>` тег. По умолчанию текст в этой позиции отсутствует.

Этот параметр появился в PowerShell 6,0.

```yaml
Type: System.String
Parameter Sets: Page
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Кссури

Указывает идентификатор URI таблицы каскадных стилей (CSS), применяемый к HTML-файлу. Этот URI включается в ссылку таблицы стилей в выходных данных.

```yaml
Type: System.Uri
Parameter Sets: Page
Aliases: cu, uri

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Fragment

Создает только HTML-таблицу. Теги HTML, HEAD, TITLE и BODY пропускаются.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Fragment
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Head

Задает содержимое тега `<HEAD>`. Значение по умолчанию — `<title\>HTML TABLE</title>`. При использовании параметра **head** параметр **Title** игнорируется.

```yaml
Type: System.String[]
Parameter Sets: Page
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Указывает объекты, которые должны быть представлены в формате HTML. Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.

Если этот параметр используется для отправки нескольких объектов, таких как все службы на компьютере, `ConvertTo-Html` создает таблицу, отображающую свойства коллекции или массива объектов. Чтобы создать таблицу отдельных объектов, используйте оператор конвейера, чтобы передать объекты в `ConvertTo-Html` .

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Meta

Задает текст, добавляемый в открывающий `<meta>` тег. По умолчанию текст в этой позиции отсутствует.

Этот параметр появился в PowerShell 6,0.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: Page
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Содержимое

Задает текст, добавляемый после закрывающего тега `</TABLE>`. По умолчанию текст в этой позиции отсутствует.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — Предварительное содержимое

Задает текст, добавляемый перед открывающим тегом `<TABLE>`. По умолчанию текст в этой позиции отсутствует.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Property

Включает указанные свойства объектов в HTML. Значением параметра **Property** может быть новое вычисляемое свойство. Вычисляемое свойство может быть блоком скрипта или хэш-таблицей. Допустимые пары "ключ-значение":

- Имя (или метка) — `<string>` (добавляется в PowerShell 6. x)
- Выражение — `<string>` или `<script block>`
- FormatString `<string>`
- Ширина- `<int32>` -должен быть больше `0`
- Alignment — значение может быть `Left` , `Center` или `Right`

Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Title

Указывает заголовок HTML-файл, т. е. текст, расположенный между тегами `<TITLE>`.

```yaml
Type: System.String
Parameter Sets: Page
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — Переход

Изменяет тип **DOCTYPE** на **XHTML transitioned DTD** , по умолчанию **DOCTYPE** — **XHTML** .

Этот параметр появился в PowerShell 6,0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Page
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Management.Automation.PSObject

Любой объект .NET можно передать в конвейер `ConvertTo-Html` .

## Выходные данные

### System. String или System.Xml.Xmlдокумент

`ConvertTo-Html` Возвращает ряд строк, составляющих допустимый HTML-код.

## ПРИМЕЧАНИЯ

Чтобы использовать этот командлет, необходимо передать один или несколько объектов в командлет или использовать параметр **InputObject** для указания объекта. Если входные данные состоят из нескольких объектов, выходные данные этих двух методов отличаются.

- При передаче нескольких объектов в командлет PowerShell посылает объекты в командлет по одному за раз. В результате `ConvertTo-Html` создается таблица, в которой отображаются отдельные объекты. Например, если передать процессы на компьютере в `ConvertTo-Html` , в результирующей таблице отобразятся все процессы.

- При использовании параметра **InputObject** для отправки нескольких объектов `ConvertTo-Html` получает эти объекты как коллекцию или как массив. В результате создается таблица, отображающая массива и его свойства, а не элементы в массиве. Например, при использовании **InputObject** для отправки процессов на компьютер в `ConvertTo-Html` результирующая таблица отображает массив объектов и его свойства.

  Чтобы обеспечить соответствие стандарту XHTML-DTD, тег DOCTYPE изменяется соответствующим образом:

   `<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"   "https://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd"\>`

## Связанные ссылки

[about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[ConvertTo-Csv](ConvertTo-Csv.md)

[ConvertTo-Json](ConvertTo-Json.md)

[ConvertTo-Xml](ConvertTo-Xml.md)

[Export-Clixml](Export-Clixml.md)

[Import-Clixml](Import-Clixml.md)
