---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 1/7/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-csv?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Csv
ms.openlocfilehash: e4cc40e7a9a5fdcd12b6a787607e4979ddbb3273
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228617"
---
# ConvertTo-Csv

## Краткий обзор
Преобразует объекты .NET в последовательность строк значений, разделенных символами (CSV).

## SYNTAX

### Разделитель

```
ConvertTo-Csv [-InputObject] <PSObject> [[-Delimiter] <Char>] [-IncludeTypeInformation]
 [-NoTypeInformation] [-QuoteFields <String[]>] [-UseQuotes <QuoteKind>] [<CommonParameters>]
```

### UseCulture

```
ConvertTo-Csv [-InputObject] <PSObject> [-UseCulture] [-IncludeTypeInformation] [-NoTypeInformation]
 [-QuoteFields <String[]>] [-UseQuotes <QuoteKind>] [<CommonParameters>]
```

## DESCRIPTION

`ConvertTo-CSV`Командлет возвращает ряд строк с разделителями-запятыми (CSV), представляющих отправляемые объекты. Затем можно использовать `ConvertFrom-Csv` командлет для повторного создания объектов из строк CSV. Объекты, преобразованные из CSV, являются строковыми значениями исходных объектов, которые содержат значения свойств и не имеют методов.

`Export-Csv`Для преобразования объектов в строки CSV можно использовать командлет. `Export-CSV` аналогичен `ConvertTo-CSV` , за исключением того, что строки CSV сохраняются в файл.

`ConvertTo-CSV`Командлет имеет параметры для указания разделителя, отличного от запятой, или использовать текущий язык и региональные параметры в качестве разделителя.

## Примеры

### Пример 1. преобразование объекта в CSV-файл

В этом примере объект **процесса** преобразуется в строку CSV.

```powershell
Get-Process -Name pwsh | ConvertTo-Csv -NoTypeInformation
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"pwsh","8","950","2204001161216","100925440","59686912","67104", ...
```

`Get-Process`Командлет получает объект **процесса** и использует параметр **Name** для указания процесса PowerShell. Объект процесса отправляется в командлет по конвейеру `ConvertTo-CSV` . `ConvertTo-CSV`Командлет преобразует объект в строки CSV. Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.

### Пример 2. преобразование объекта DateTime в CSV-файл

В этом примере объект **DateTime** преобразуется в строку CSV.

```powershell
$Date = Get-Date
ConvertTo-Csv -InputObject $Date -Delimiter ';' -NoTypeInformation
```

```Output
"DisplayHint";"DateTime";"Date";"Day";"DayOfWeek";"DayOfYear";"Hour";"Kind";"Millisecond";"Minute";"Month";"Second";"Ticks";"TimeOfDay";"Year"
"DateTime";"Friday, January 4, 2019 14:40:51";"1/4/2019 00:00:00";"4";"Friday";"4";"14";"Local";"711";"40";"1";"51";"636822096517114991";"14:40:51.7114991";"2019"
```

`Get-Date`Командлет возвращает объект **DateTime** и сохраняет его в `$Date` переменной. `ConvertTo-Csv`Командлет преобразует объект **DateTime** в строки. Параметр **InputObject** использует объект **DateTime** , хранящийся в `$Date` переменной. Параметр- **Разделитель** задает точку с запятой для разделения строковых значений. Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.

### Пример 3. преобразование журнала событий PowerShell в CSV-файл

В этом примере журнал событий Windows для PowerShell преобразуется в последовательность строк CSV.

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-WinEvent -LogName 'PowerShellCore/Operational' | ConvertTo-Csv -UseCulture -NoTypeInformation
```

```Output
,
"Message","Id","Version","Qualifiers","Level","Task","Opcode","Keywords","RecordId", ...
"Error Message = System error""4100","1",,"3","106","19","0","31716","PowerShellCore", ...
```

`Get-Culture`Командлет использует вложенные свойства **TextInfo** и **ListSeparator** и отображает текущий разделитель списка по умолчанию для текущего языка и региональных параметров. `Get-WinEvent`Командлет получает объекты журнала событий и использует параметр " **/l** " для указания имени файла журнала. Объекты журнала событий отправляются по конвейеру в `ConvertTo-Csv` командлет. `ConvertTo-Csv`Командлет преобразует объекты журнала событий в последовательность строк CSV. Параметр **UseCulture** использует разделитель списка по умолчанию текущего языка и региональных параметров в качестве разделителя. Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.

### Пример 4. преобразование в CSV с кавычками вокруг двух столбцов

В этом примере объект **DateTime** преобразуется в строку CSV.

```powershell
Get-Date | ConvertTo-Csv -QuoteFields "DateTime","Date"
```

```Output
DisplayHint,"DateTime","Date",Day,DayOfWeek,DayOfYear,Hour,Kind,Millisecond,Minute,Month,Second,Ticks,TimeOfDay,Year
DateTime,"Thursday, August 22, 2019 11:27:34 AM","8/22/2019 12:00:00 AM",22,Thursday,234,11,Local,569,27,8,34,637020700545699784,11:27:34.5699784,2019
```

### Пример 4. преобразование в CSV с кавычками только при необходимости

В этом примере объект **DateTime** преобразуется в строку CSV.

```powershell
Get-Date | ConvertTo-Csv -UseQuotes AsNeeded
```

```Output
DisplayHint,DateTime,Date,Day,DayOfWeek,DayOfYear,Hour,Kind,Millisecond,Minute,Month,Second,Ticks,TimeOfDay,Year
DateTime,"Thursday, August 22, 2019 11:31:00 AM",8/22/2019 12:00:00 AM,22,Thursday,234,11,Local,713,31,8,0,637020702607132640,11:31:00.7132640,2019
```

## PARAMETERS

### -Delimiter

Задает разделитель значений свойств в строках CSV. Значение по умолчанию — запятая ( `,` ). Введите символ, например двоеточие ( `:` ). Чтобы указать точку с запятой ( `;` ), заключите ее в одинарные кавычки.

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

### -Инклудетипеинформатион

При использовании этого параметра первая строка выходных данных содержит **#TYPE** , за которыми следует полное имя типа объекта. Например, **#TYPE System. Diagnostics. Process** .

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

Указывает объекты, которые преобразуются в строки CSV. Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты. Также можно передать объекты в `ConvertTo-CSV` .

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### -Куотефиелдс

Задает имена столбцов, которые должны быть заключены в кавычки. При использовании этого параметра только указанные столбцы заключаются в кавычки.

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

Любой объект, имеющий адаптер расширенной системы типов (ETS), можно передать в `ConvertTo-CSV` .

## Выходные данные

### System.String

Выходные данные в формате CSV возвращаются в виде коллекции строк.

## ПРИМЕЧАНИЯ

В формате CSV каждый объект представлен как разделенный запятыми список значений свойств. Значения свойств преобразуются в строки с помощью метода **ToString ()** объекта. Строки представлены именем значения свойства. `ConvertTo-CSV` не экспортирует методы объекта.

Строки CSV выводятся следующим образом:

- Если используется **инклудетипеинформатион** , первая строка состоит из **#TYPE** , за которой следует полное имя типа объекта. Например, **#TYPE System. Diagnostics. Process** .
- Если **инклудетипеинформатион** не используется, первая строка включает заголовки столбцов. Заголовки содержат имена свойств первого объекта в виде списка с разделителями-запятыми.
- Остальные строки содержат разделенные запятыми списки значений свойств каждого объекта.

Начиная с PowerShell 6,0 поведение по умолчанию `ConvertTo-CSV` — не включать сведения о **#TYPE** в CSV-файл, а **NoTypeInformation** является подразумеваемым. **Инклудетипеинформатион** можно использовать для включения сведений о **#TYPE** и эмуляции поведения по умолчанию `ConvertTo-CSV` до PowerShell 6,0.

При отправке нескольких объектов в `ConvertTo-CSV` `ConvertTo-CSV` упорядочивает строки на основе свойств первого отправленного объекта. Если остальные объекты не имеют одного из указанных свойств, значение свойства этого объекта равно null, как представлено двумя последовательными запятыми. Если у остальных объектов есть дополнительные свойства, их значения игнорируются.

## Связанные ссылки

[ConvertFrom-Csv](ConvertFrom-Csv.md)

[Export-Csv](Export-Csv.md)

[Import-Csv](Import-Csv.md)

