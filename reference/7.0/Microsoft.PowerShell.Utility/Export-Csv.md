---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-csv?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Csv
ms.openlocfilehash: bb2d077b3584d4501db00a927b83034d37dceaec
ms.sourcegitcommit: 560a9f3c3148acab4655e91e8b07745ab74d5d26
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2020
ms.locfileid: "96913365"
---
# Export-Csv

## Краткий обзор
Преобразует объекты в последовательность строк с разделителями-запятыми (CSV) и сохраняет строки в файл.

## SYNTAX

### Delimiter (по умолчанию)

```
Export-Csv -InputObject <PSObject> [[-Path] <String>] [-LiteralPath <String>] [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-Append] [[-Delimiter] <Char>] [-IncludeTypeInformation]
 [-NoTypeInformation] [-QuoteFields <String[]>] [-UseQuotes <QuoteKind>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### UseCulture

```
Export-Csv -InputObject <PSObject> [[-Path] <String>] [-LiteralPath <String>] [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-Append] [-UseCulture] [-IncludeTypeInformation] [-NoTypeInformation]
 [-QuoteFields <String[]>] [-UseQuotes <QuoteKind>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Export-CSV`Командлет создает CSV-файл объектов, которые вы отправляете. Каждый объект представляет собой строку, содержащую разделенный запятыми список значений свойств объекта. С помощью `Export-CSV` командлета можно создавать электронные таблицы и обмениваться данными с программами, которые принимают CSV-файлы в качестве входных.

Не форматируйте объекты перед их отправкой в `Export-CSV` командлет. Если `Export-CSV` получает отформатированные объекты, CSV-файл содержит свойства форматирования, а не свойства объекта. Чтобы экспортировать только выбранные свойства объекта, используйте `Select-Object` командлет.

## Примеры

### Пример 1. экспорт свойств процесса в CSV-файл

В этом примере выбираются объекты **Process** с конкретными свойствами, экспортируются объекты в CSV-файл.

```powershell
Get-Process -Name WmiPrvSE | Select-Object -Property BasePriority,Id,SessionId,WorkingSet |
  Export-Csv -Path .\WmiData.csv -NoTypeInformation
Import-Csv -Path .\WmiData.csv
```

```Output
BasePriority Id    SessionId WorkingSet
------------ --    --------- ----------
8            976   0         20267008
8            2292  0         36786176
8            3816  0         30351360
8            8604  0         15011840
8            10008 0         8830976
8            11764 0         14237696
8            54632 0         9502720
```

`Get-Process`Командлет возвращает объекты **процесса** . Параметр **Name** фильтрует выходные данные, чтобы включить только объекты процесса WmiPrvSE. Объекты процесса отправляются по конвейеру в `Select-Object` командлет. `Select-Object` использует параметр **Property** для выбора подмножества свойств объекта процесса. Объекты процесса отправляются по конвейеру в `Export-Csv` командлет. `Export-Csv` Преобразует объекты процесса в последовательность строк CSV. Параметр **path** указывает, что файл WmiData.csv сохраняется в текущем каталоге. Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6. `Import-Csv`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.

### Пример 2. экспорт процессов в файл с разделителями-запятыми

В этом примере **выполняется** получение объектов Process и экспорт объектов в CSV-файл.

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","511","2203597099008","35364864","21979136","30048", ...
```

`Get-Process`Командлет получает объекты **Process** . Объекты процесса отправляются по конвейеру в `Export-Csv` командлет. `Export-Csv` Преобразует объекты процесса в последовательность строк CSV.
Параметр **path** указывает, что файл Processes.csv сохраняется в текущем каталоге. Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6. `Get-Content`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.

### Пример 3. экспорт процессов в файл с разделителями-запятыми

В этом примере **выполняется** получение объектов Process и экспорт объектов в файл с разделителем в виде точки с запятой.

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -Delimiter ';' -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name";"SI";"Handles";"VM";"WS";"PM";"NPM";"Path";"Parent";"Company";"CPU";"FileVersion"; ...
"ApplicationFrameHost";"4";"509";"2203595321344";"34807808";"21770240";"29504"; ...
```

`Get-Process`Командлет получает объекты **Process** . Объекты процесса отправляются по конвейеру в `Export-Csv` командлет. `Export-Csv` Преобразует объекты процесса в последовательность строк CSV.
Параметр **path** указывает, что файл Processes.csv сохраняется в текущем каталоге. Параметр- **Разделитель** задает точку с запятой для разделения строковых значений. Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6. `Get-Content`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.

### Пример 4. экспорт процессов с использованием разделителя списка текущего языка и региональных параметров

В этом примере **выполняется** получение объектов Process и экспорт объектов в файл. Разделитель является разделителем списка текущего языка и региональных параметров.

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-Process | Export-Csv -Path .\Processes.csv -UseCulture -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","511","2203597099008","35364864","21979136","30048", ...
```

`Get-Culture`Командлет использует вложенные свойства **TextInfo** и **ListSeparator** и отображает текущий разделитель списка по умолчанию для текущего языка и региональных параметров. `Get-Process`Командлет получает объекты **Process** .
Объекты процесса отправляются по конвейеру в `Export-Csv` командлет. `Export-Csv` Преобразует объекты процесса в последовательность строк CSV. Параметр **path** указывает, что файл Processes.csv сохраняется в текущем каталоге. Параметр **UseCulture** использует разделитель списка по умолчанию текущего языка и региональных параметров в качестве разделителя. Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6. `Get-Content`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.

### Пример 5. экспорт процессов с информацией о типах

В этом примере объясняется, как включить данные заголовка **#TYPE** в CSV-файл. По умолчанию в версиях, предшествовавших версии PowerShell 6,0, используется заголовок **#TYPE** .

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -IncludeTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
#TYPE System.Diagnostics.Process
"Name","SI","Handles","VM","WS","PM","NPM","Path","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","507","2203595001856","35139584","20934656","29504", ...
```

`Get-Process`Командлет получает объекты **Process** . Объекты процесса отправляются по конвейеру в `Export-Csv` командлет. `Export-Csv` Преобразует объекты процесса в последовательность строк CSV.
Параметр **path** указывает, что файл Processes.csv сохраняется в текущем каталоге. **Инклудетипеинформатион** содержит заголовок **#TYPE** данных в выходных данных в формате CSV. `Get-Content`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.

### Пример 6. экспорт и добавление объектов в CSV-файл

В этом примере описывается, как экспортировать объекты в CSV-файл и использовать параметр **append** для добавления объектов в существующий файл.

```powershell
$AppService = (Get-Service -DisplayName *Application* | Select-Object -Property DisplayName, Status)
$AppService | Export-Csv -Path .\Services.Csv -NoTypeInformation
Get-Content -Path .\Services.Csv
$WinService = (Get-Service -DisplayName *Windows* | Select-Object -Property DisplayName, Status)
$WinService | Export-Csv -Path ./Services.csv -NoTypeInformation -Append
Get-Content -Path .\Services.Csv
```

```Output
"DisplayName","Status"
"Application Layer Gateway Service","Stopped"
"Application Identity","Running"
"Windows Audio Endpoint Builder","Running"
"Windows Audio","Running"
"Windows Event Log","Running"
```

`Get-Service`Командлет получает объекты службы. Параметр **DisplayName** возвращает службы, содержащие слово «приложение». Объекты службы отправляются по конвейеру в `Select-Object` командлет. `Select-Object` использует параметр **Property** для задания свойств **DisplayName** и **Status** . `$AppService`Переменная хранит объекты.

`$AppService`Объекты отправляются по конвейеру в `Export-Csv` командлет. `Export-Csv` Преобразует объекты службы в последовательность строк CSV. Параметр **path** указывает, что файл Services.csv сохраняется в текущем каталоге. Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6. `Get-Content`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.

`Get-Service` `Select-Object` Командлеты и повторяются для служб, содержащих слово Windows. `$WinService`Переменная хранит объекты службы. `Export-Csv`Командлет использует параметр **append** , чтобы указать, что `$WinService` объекты добавляются в существующий файл Services.csv. `Get-Content`Командлет повторяется для вывода обновленного файла, содержащего добавленные данные.

### Пример 7. командлет Format в конвейере создает непредвиденные результаты

В этом примере показано, почему важно не использовать командлет Format в конвейере. При получении непредвиденных выходных данных устраните неполадки синтаксиса конвейера.

```powershell
Get-Date | Select-Object -Property DateTime, Day, DayOfWeek, DayOfYear |
 Export-Csv -Path .\DateTime.csv -NoTypeInformation
Get-Content -Path .\DateTime.csv
```

```Output
"DateTime","Day","DayOfWeek","DayOfYear"
"Wednesday, January 2, 2019 14:59:34","2","Wednesday","2"
```

```powershell
Get-Date | Format-Table -Property DateTime, Day, DayOfWeek, DayOfYear |
 Export-Csv -Path .\FTDateTime.csv -NoTypeInformation
Get-Content -Path .\FTDateTime.csv
```

```Output
"ClassId2e4f51ef21dd47e99d3c952918aff9cd","pageHeaderEntry","pageFooterEntry","autosizeInfo", ...
"033ecb2bc07a4d43b5ef94ed5a35d280",,,,"Microsoft.PowerShell.Commands.Internal.Format. ...
"9e210fe47d09416682b841769c78b8a3",,,,,
"27c87ef9bbda4f709f6b4002fa4af63c",,,,,
"4ec4f0187cb04f4cb6973460dfe252df",,,,,
"cf522b78d86c486691226b40aa69e95c",,,,,
```

`Get-Date`Командлет возвращает объект **DateTime** . Объект отправляется по конвейеру в `Select-Object` командлет. `Select-Object` использует параметр **Property** для выбора подмножества свойств объекта. Объект отправляется по конвейеру в `Export-Csv` командлет. `Export-Csv` Преобразует объект в формат CSV. Параметр **path** указывает, что файл DateTime.csv сохраняется в текущем каталоге. Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6. `Get-Content`Командлет использует параметр **path** для вывода CSV-файла, расположенного в текущем каталоге.

При `Format-Table` использовании командлета в конвейере для выбора свойств получены непредвиденные результаты. `Format-Table` отправляет объекты формата таблицы по конвейеру в `Export-Csv` командлет, а не в объект **DateTime** . `Export-Csv` Преобразует объекты формата таблицы в последовательность строк CSV. `Get-Content`Командлет ОТОБРАЖАЕТ CSV-файл, содержащий объекты формата таблицы.

### Пример 8. Использование параметра Force для перезаписи файлов, которые доступны только для чтения

В этом примере создается пустой файл только для чтения, а для обновления файла используется параметр **Force** .

```powershell
New-Item -Path .\ReadOnly.csv -ItemType File
Set-ItemProperty -Path .\ReadOnly.csv -Name IsReadOnly -Value $true
Get-Process | Export-Csv -Path .\ReadOnly.csv -NoTypeInformation
```

```Output
Export-Csv : Access to the path 'C:\ReadOnly.csv' is denied.
At line:1 char:15
+ Get-Process | Export-Csv -Path .\ReadOnly.csv -NoTypeInformation
+               ~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : OpenError: (:) [Export-Csv], UnauthorizedAccessException
+ FullyQualifiedErrorId : FileOpenFailure,Microsoft.PowerShell.Commands.ExportCsvCommand
```

```powershell
Get-Process | Export-Csv -Path .\ReadOnly.csv -NoTypeInformation -Force
Get-Content -Path .\ReadOnly.csv
```

```Output
"Name";"SI";"Handles";"VM";"WS";"PM";"NPM";"Path";"Parent";"Company";"CPU";"FileVersion"; ...
"ApplicationFrameHost";"4";"509";"2203595321344";"34807808";"21770240";"29504"; ...
```

`New-Item`Командлет использует параметры **path** и **ItemType** для создания файла ReadOnly.csv в текущем каталоге. `Set-ItemProperty`Командлет использует параметры **Name** и **value** , чтобы изменить свойство **IsReadOnly** для файла на true. `Get-Process`Командлет получает объекты **Process** . Объекты процесса отправляются по конвейеру в `Export-Csv` командлет. `Export-Csv` Преобразует объекты процесса в последовательность строк CSV. Параметр **path** указывает, что файл ReadOnly.csv сохраняется в текущем каталоге. Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6. Выходные данные показывают, что файл не записан, так как доступ запрещен.

Параметр **Force** добавляется в командлет, `Export-Csv` чтобы принудительно выполнить запись экспорта в файл. `Get-Content`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.

### Пример 9. Использование параметра Force с Append

В этом примере показано, как использовать параметры **Force** и **append** . Если эти параметры объединены, несоответствующие свойства объекта могут быть записаны в CSV-файл.

```powershell
$Content = [PSCustomObject]@{Name = 'PowerShell Core'; Version = '6.0'}
$Content | Export-Csv -Path .\ParmFile.csv -NoTypeInformation
$AdditionalContent = [PSCustomObject]@{Name = 'Windows PowerShell'; Edition = 'Desktop'}
$AdditionalContent | Export-Csv -Path .\ParmFile.csv -NoTypeInformation -Append
```

```Output
Export-Csv : Cannot append CSV content to the following file: ParmFile.csv.
The appended object does not have a property that corresponds to the following column:
Version. To continue with mismatched properties, add the -Force parameter, and then retry
 the command.
At line:1 char:22
+ $AdditionalContent | Export-Csv -Path .\ParmFile.csv -NoTypeInformation -Append
+                      ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : InvalidData: (Version:String) [Export-Csv], InvalidOperationException
+ FullyQualifiedErrorId : CannotAppendCsvWithMismatchedPropertyNames,Microsoft.PowerShell. ...
```

```powershell
$AdditionalContent | Export-Csv -Path .\ParmFile.csv -NoTypeInformation -Append -Force
Import-Csv -Path .\ParmFile.csv
```

```Output
Name               Version
----               -------
PowerShell Core    6.0
Windows PowerShell
```

Выражение создает **PSCustomObject** с свойствами **Name** и **Version** . Значения хранятся в `$Content` переменной. `$Content`Переменная отправляется в командлет по конвейеру `Export-Csv` . `Export-Csv` использует параметр **path** и сохраняет файл ParmFile.csv в текущем каталоге. Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.

Другое выражение создает **PSCustomObject** с свойствами **Name** и **Edition** . Значения хранятся в `$AdditionalContent` переменной. `$AdditionalContent`Переменная отправляется в командлет по конвейеру `Export-Csv` . Параметр **append** используется для добавления данных в файл. Добавление завершается ошибкой из-за несоответствия имени свойства **версии** и **выпуска**.

`Export-Csv`Параметр **Force** командлета используется для принудительной записи экспорта в файл. Свойство **Edition** отбрасывается. `Import-Csv`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.

### Пример 10. экспорт в CSV с кавычками вокруг двух столбцов

В этом примере объект **DateTime** преобразуется в строку CSV.

```powershell
Get-Date | Export-Csv  -QuoteFields "DateTime","Date" -Path .\FTDateTime.csv
Get-Content -Path .\FTDateTime.csv
```

```Output
DisplayHint,"DateTime","Date",Day,DayOfWeek,DayOfYear,Hour,Kind,Millisecond,Minute,Month,Second,Ticks,TimeOfDay,Year
DateTime,"Thursday, August 22, 2019 11:27:34 AM","8/22/2019 12:00:00 AM",22,Thursday,234,11,Local,569,27,8,34,637020700545699784,11:27:34.5699784,2019
```

### Пример 11. экспорт в CSV с кавычками только при необходимости

В этом примере объект **DateTime** преобразуется в строку CSV.

```powershell
Get-Date | Export-Csv  -UseQuotes AsNeeded -Path .\FTDateTime.csv
Get-Content -Path .\FTDateTime.csv
```

```Output
DisplayHint,DateTime,Date,Day,DayOfWeek,DayOfYear,Hour,Kind,Millisecond,Minute,Month,Second,Ticks,TimeOfDay,Year
DateTime,"Thursday, August 22, 2019 11:31:00 AM",8/22/2019 12:00:00 AM,22,Thursday,234,11,Local,713,31,8,0,637020702607132640,11:31:00.7132640,2019
```

## PARAMETERS

### — Добавление

Используйте этот параметр, чтобы `Export-CSV` Добавить выходные данные CSV в конец указанного файла. Без этого параметра `Export-CSV` заменяет содержимое файла без предупреждения.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Delimiter

Указывает разделитель для значений свойств. Значение по умолчанию — запятая ( `,` ). Введите символ, например двоеточие ( `:` ). Чтобы указать точку с запятой ( `;` ), заключите ее в кавычки.

```yaml
Type: System.Char
Parameter Sets: Delimiter
Aliases:

Required: False
Position: 1
Default value: comma (,)
Accept pipeline input: False
Accept wildcard characters: False
```

### -Encoding

Указывает кодировку для экспортированного CSV-файла. Значение по умолчанию — `utf8NoBOM`.

Для этого параметра допустимы следующие значения:

- `ascii`: Использует кодировку для набора символов ASCII (7-разрядных).
- `bigendianunicode`: Кодируется в формате UTF-16 с обратным порядком байтов.
- `oem`: Использует кодировку по умолчанию для программ MS-DOS и консолей.
- `unicode`: Кодируется в формате UTF-16 с прямым порядком байтов.
- `utf7`: Кодируется в формате UTF-7.
- `utf8`: Кодируется в формате UTF-8.
- `utf8BOM`: Кодирует в формате UTF-8 с меткой порядка байтов (BOM)
- `utf8NoBOM`: Кодирует в формате UTF-8 без метки порядка байтов (BOM)
- `utf32`: Кодируется в формате UTF-32.

Начиная с PowerShell 6,2, параметр **кодировки** также разрешает числовые идентификаторы зарегистрированных кодовых страниц (например `-Encoding 1251` ,) или строковых имен зарегистрированных кодовых страниц (например `-Encoding "windows-1251"` ,). Дополнительные сведения см. в документации .NET по [кодированию. codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Этот параметр позволяет `Export-Csv` перезаписывать файлы с атрибутом " **только для чтения** ".

При объединении параметров **Force** и **append** объекты, содержащие несовпадающие свойства, могут быть записаны в CSV-файл. В файл записываются только те свойства, которые соответствуют. Несоответствующие свойства отбрасываются.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Инклудетипеинформатион

При использовании этого параметра первая строка выходных данных CSV содержит **#TYPE** , за которыми следует полное имя типа объекта. Например, **#TYPE System. Diagnostics. Process**.

Этот параметр появился в PowerShell 6,0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ITI

Required: False
Position: Named
Default value: #TYPE <Object>
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Указывает экспортируемые объекты в качестве строк CSV-файла. Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты. Также можно передать объекты в `Export-CSV` .

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -LiteralPath

Указывает путь к выходному CSV-файлу. В отличие от параметра **Path**, значение параметра **LiteralPath** используется в точности так, как вводится. Никакие символы не интерпретируются как знаки подстановки. Если путь содержит escape-символы, используйте одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath, LP

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoClobber

Используйте этот параметр, чтобы `Export-CSV` не перезаписать существующий файл. По умолчанию, если файл существует по указанному пути, `Export-CSV` перезаписывает файл без предупреждения.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoTypeInformation

Удаляет заголовок сведений о **#TYPE** из выходных данных. Этот параметр стал значением по умолчанию в PowerShell 6,0 и включен для обеспечения обратной совместимости.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NTI

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Обязательный параметр, указывающий расположение для сохранения выходного CSV-файла.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseCulture

Использует разделитель списка для текущего языка и региональных параметров в качестве разделителя элементов. Чтобы найти разделитель списка для языка и региональных параметров, используйте следующую команду: `(Get-Culture).TextInfo.ListSeparator` .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UseCulture
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Запрос подтверждения перед выполнением командлета.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Предотвращает обработку командлета или внесение изменений. Выходные данные показывают, что произойдет при запуске командлета.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Куотефиелдс

Задает имена столбцов, которые должны быть заключены в кавычки. При использовании этого параметра только указанные столбцы заключаются в кавычки. Этот параметр был добавлен в PowerShell 7,0.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: QF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Усекуотес

Указывает, когда в CSV-файлах используются кавычки. Возможны следующие значения:

- Никогда — не заключать никаких кавычек
- Всегда-цитировать все (поведение по умолчанию)
- AsNeeded — поля кавычек, содержащие символ-разделитель

Этот параметр был добавлен в PowerShell 7,0.

```yaml
Type: Microsoft.PowerShell.Commands.BaseCsvWritingCommand+QuoteKind
Parameter Sets: (All)
Aliases: UQ

Required: False
Position: Named
Default value: Always
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Management.Automation.PSObject

Любой объект с адаптером системы расширенного типа (ETS) можно передать в `Export-CSV` .

## Выходные данные

### System.String

Список CSV-файлов отправляется в файл, указанный в параметре Path.

## ПРИМЕЧАНИЯ

`Export-CSV`Командлет преобразует объекты, которые вы отправляете, в последовательность строк CSV и сохраняет их в указанном текстовом файле. Можно использовать `Export-CSV -IncludeTypeInformation` для сохранения объектов в CSV-файле, а затем использовать `Import-Csv` командлет для создания объектов из текста в CSV-файле.

В CSV-файле каждый объект представлен списком значений свойств объекта с разделителями-запятыми. Значения свойств преобразуются в строки с помощью метода **ToString ()** . Строки представлены именем значения свойства. `Export-CSV -IncludeTypeInformation` не экспортирует методы объекта.

Строки CSV выводятся следующим образом:

- Если используется **инклудетипеинформатион** , первая строка содержит заголовок **#TYPE** сведений, за которым следует полное имя типа объекта.
  Например, **#TYPE System. Diagnostics. Process**.
- Если **инклудетипеинформатион** не используется, первая строка включает заголовки столбцов. Заголовки содержат имена свойств первого объекта в виде списка с разделителями-запятыми.
- Остальные строки содержат разделенные запятыми списки значений свойств каждого объекта.

Начиная с PowerShell 6,0 поведение по умолчанию `Export-CSV` — не включать сведения о **#TYPE** в CSV-файл, а **NoTypeInformation** является подразумеваемым. **Инклудетипеинформатион** можно использовать для включения сведений о **#TYPE** и эмуляции поведения по умолчанию `Export-CSV` до PowerShell 6,0.

При отправке нескольких объектов в `Export-CSV` `Export-CSV` файл упорядочивается по свойствам первого отправленного объекта. Если остальные объекты не имеют одного из указанных свойств, значение этого свойства для объекта будет пустым, то есть представлено двумя идущими подряд запятыми. Если оставшиеся объекты содержат дополнительные свойства, их значения не включаются в файл.

Командлет можно использовать `Import-Csv` для повторного создания объектов из строк CSV в файлах. Полученные объекты являются версиями CSV-файлов исходных объектов, которые состоят из представлений строк значений свойств без методов.

`ConvertTo-Csv` `ConvertFrom-Csv` Командлеты и преобразуют объекты в строки CSV и из строк CSV. `Export-CSV` совпадает с `ConvertTo-CSV` , за исключением того, что строки CSV сохраняются в файле.

## Связанные ссылки

[ConvertFrom-Csv](ConvertFrom-Csv.md)

[ConvertTo-Csv](ConvertTo-Csv.md)

[Format-Table](Format-Table.md)

[Import-Csv](Import-Csv.md)

[Select-Object](Select-Object.md)
