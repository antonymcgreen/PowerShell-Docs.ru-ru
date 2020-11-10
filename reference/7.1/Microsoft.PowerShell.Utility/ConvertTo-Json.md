---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-json?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Json
ms.openlocfilehash: acfeae4025b3a32d2a04307609597cf30332d708
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94389459"
---
# ConvertTo-Json

## Краткий обзор
Преобразует объект в строку в формате JSON.

## SYNTAX

```
ConvertTo-Json [-InputObject] <Object> [-Depth <Int32>] [-Compress]
[-EnumsAsStrings] [-AsArray] [-EscapeHandling <StringEscapeHandling>]
[<CommonParameters>]
```

## DESCRIPTION

`ConvertTo-Json`Командлет преобразует любой объект .NET в строку в формате нотация объектов JavaScript (JSON). Свойства преобразуются в имена полей, значения полей преобразуются в значения свойств, а методы удаляются.

Затем можно использовать `ConvertFrom-Json` командлет для преобразования строки в формате JSON в объект JSON, который легко управляется в PowerShell.

Многие веб-сайты используют нотацию JSON вместо XML для сериализации данных для взаимодействия между серверами и веб-приложениями.

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1

```powershell
(Get-UICulture).Calendar | ConvertTo-Json
```

```Output
{
  "MinSupportedDateTime": "0001-01-01T00:00:00",
  "MaxSupportedDateTime": "9999-12-31T23:59:59.9999999",
  "AlgorithmType": 1,
  "CalendarType": 1,
  "Eras": [
    1
  ],
  "TwoDigitYearMax": 2029,
  "IsReadOnly": true
}
```

Эта команда использует `ConvertTo-Json` командлет для преобразования объекта GregorianCalendar в строку в формате JSON.

### Пример 2

```powershell
Get-Date | ConvertTo-Json; Get-Date | ConvertTo-Json -AsArray
```

```Output
{
  "value": "2018-10-12T23:07:18.8450248-05:00",
  "DisplayHint": 2,
  "DateTime": "October 12, 2018 11:07:18 PM"
}
[
  {
    "value": "2018-10-12T23:07:18.8480668-05:00",
    "DisplayHint": 2,
    "DateTime": "October 12, 2018 11:07:18 PM"
  }
]
```

В этом примере показаны выходные данные `ConvertTo-Json` командлета с параметром **асаррай** и без него. Можно увидеть, что вторая часть выходных данных заключена в скобки массива.

### Пример 3

```powershell
@{Account="User01";Domain="Domain01";Admin="True"} | ConvertTo-Json -Compress
```

```Output
{"Domain":"Domain01","Account":"User01","Admin":"True"}
```

Эта команда показывает результат применения параметра **сжатия** `ConvertTo-Json` . Сжатие влияет только на внешний вид строки, но не на ее действительность.

### Пример 4

```powershell
Get-Date | Select-Object -Property * | ConvertTo-Json
```

```Output
{
  "DisplayHint": 2,
  "DateTime": "October 12, 2018 10:55:32 PM",
  "Date": "2018-10-12T00:00:00-05:00",
  "Day": 12,
  "DayOfWeek": 5,
  "DayOfYear": 285,
  "Hour": 22,
  "Kind": 2,
  "Millisecond": 639,
  "Minute": 55,
  "Month": 10,
  "Second": 32,
  "Ticks": 636749817326397744,
  "TimeOfDay": {
    "Ticks": 825326397744,
    "Days": 0,
    "Hours": 22,
    "Milliseconds": 639,
    "Minutes": 55,
    "Seconds": 32,
    "TotalDays": 0.95523888627777775,
    "TotalHours": 22.925733270666665,
    "TotalMilliseconds": 82532639.774400011,
    "TotalMinutes": 1375.54399624,
    "TotalSeconds": 82532.6397744
  },
  "Year": 2018
}
```

В этом примере `ConvertTo-Json` командлет используется для преобразования объекта **System. DateTime** из `Get-Date` командлета в строку в формате JSON. Команда использует `Select-Object` командлет для получения всех ( `*` ) свойств объекта **DateTime** . В выходных данных отображается строка JSON, которая `ConvertTo-Json` возвращает.

### Пример 5

```powershell
Get-Date | Select-Object -Property * | ConvertTo-Json | ConvertFrom-Json
```

```Output
DisplayHint : 2
DateTime    : October 12, 2018 10:55:52 PM
Date        : 2018-10-12 12:00:00 AM
Day         : 12
DayOfWeek   : 5
DayOfYear   : 285
Hour        : 22
Kind        : 2
Millisecond : 768
Minute      : 55
Month       : 10
Second      : 52
Ticks       : 636749817527683372
TimeOfDay   : @{Ticks=825527683372; Days=0; Hours=22; Milliseconds=768; Minutes=55; Seconds=52;
              TotalDays=0.95547185575463; TotalHours=22.9313245381111; TotalMilliseconds=82552768.3372;
              TotalMinutes=1375.87947228667; TotalSeconds=82552.7683372}
Year        : 2018
```

В этом примере показано, как использовать `ConvertTo-Json` `ConvertFrom-Json` командлеты и для преобразования объекта в строку JSON и объект JSON.

## PARAMETERS

### -Асаррай

Выводит объект в скобках массива, даже если входные данные являются одним объектом.

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

### -Сжимать

Исключает пробелы и отступы в выходной строке.

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

### -Depth

Указывает, сколько уровней вложенных объектов включается в JSON-представление. Значение по умолчанию — 2.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 2
Accept pipeline input: False
Accept wildcard characters: False
```

### -Енумсасстрингс

Предоставляет альтернативный параметр сериализации, который преобразует все перечисления в их строковое представление.

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

### -Ескапехандлинг

Определяет, как определенные символы экранированы в результирующем выходных данных JSON. По умолчанию escape-последовательности обрабатываются только управляющие символы (например, символ новой строки).

Допустимы следующие значения:

- Управляющие символы по умолчанию преобразуются в escape-последовательность.
- ЕскапенонасЦии — все символы, отличные от ASCII, и управляющие знаки преобразуются в escape-последовательность.
- Ескапехтмл-HTML ( `<` , `>` , `&` , `'` , `"` ) и управляющие символы экранированы.

Этот параметр появился в PowerShell 6,2.

```yaml
Type: Newtonsoft.Json.StringEscapeHandling
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Задает объекты для преобразования в формат JSON. Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты. Также можно передать объект в `ConvertTo-Json` .

Параметр **InputObject** является обязательным, но его значение может быть равно null ( `$null` ) или пустой строке.
Если входной объект имеет значение `$null` , не `ConvertTo-Json` создает никаких выходных данных. Если входной объект является пустой строкой, `ConvertTo-Json` возвращает пустую строку.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### System.Object

Любой объект можно передать по конвейеру в `ConvertTo-Json` .

## Выходные данные

### System.String

## ПРИМЕЧАНИЯ

`ConvertTo-Json`Командлет реализуется с помощью [Newtonsoft JSON.NET](https://www.newtonsoft.com/json).

## Связанные ссылки

[Введение в нотация объектов JavaScript (JSON) в JavaScript и .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))

[ConvertFrom-Json](ConvertFrom-Json.md)

[Get-Content](../Microsoft.PowerShell.Management/Get-Content.md)

[Get-UICulture](Get-UICulture.md)

[Invoke-WebRequest](Invoke-WebRequest.md)

[Invoke-RestMethod](Invoke-RestMethod.md)

[NewtonSoft.Js. стринжескапехандлинг](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm)
