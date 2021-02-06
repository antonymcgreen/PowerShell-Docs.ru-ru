---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-json?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Json
ms.openlocfilehash: 525b123d48b0f88ca3eef85a3f95cc303a981ca3
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605054"
---
# ConvertFrom-Json

## Краткий обзор
Преобразует строку в формате JSON в пользовательский объект или хэш-таблицу.

## SYNTAX

```
ConvertFrom-Json [-InputObject] <String> [-AsHashtable] [-Depth <Int32>] [-NoEnumerate] [<CommonParameters>]
```

## DESCRIPTION

`ConvertFrom-Json`Командлет преобразует строку в формате нотация объектов JavaScript (JSON) в пользовательский объект **PSCustomObject** , имеющий свойство для каждого поля в строке JSON. Формат JSON обычно используется на веб-сайтах для текстового представления объектов. Стандарт JSON не запрещает использование, которое запрещено **PSCustomObject**. Например, если строка JSON содержит дублирующиеся ключи, этот командлет использует только последний ключ. См. Другие примеры ниже.

Чтобы создать строку JSON из любого объекта, используйте `ConvertTo-Json` командлет.

Этот командлет появился в PowerShell 3,0.

> [!NOTE]
> Начиная с PowerShell 6, этот командлет поддерживает JSON с комментариями. Принятые комментарии запускаются с двумя косыми чертами ( `//` ). Комментарий не будет представлен в данных и может быть записан в файл без повреждения данных или вызова ошибки, как это делалось в PowerShell 5,1.

## Примеры

### Пример 1. преобразование объекта DateTime в объект JSON

Эта команда использует `ConvertTo-Json` `ConvertFrom-Json` командлеты и для преобразования объекта **DateTime** из `Get-Date` командлета в объект JSON и затем в **PSCustomObject**.

```powershell
Get-Date | Select-Object -Property * | ConvertTo-Json | ConvertFrom-Json
```

```Output
DisplayHint : 2
DateTime    : Friday, January 13, 2012 8:06:31 PM
Date        : 1/13/2012 8:00:00 AM
Day         : 13
DayOfWeek   : 5
DayOfYear   : 13
Hour        : 20
Kind        : 2
Millisecond : 400
Minute      : 6
Month       : 1
Second      : 31
Ticks       : 634620819914009002
TimeOfDay   : @{Ticks=723914009002; Days=0; Hours=20; Milliseconds=400; Minutes=6; Seconds=31; TotalDays=0.83786343634490734; TotalHours=20.108722472277776; TotalMilliseconds=72391400.900200009; TotalMinutes=1206.5233483366667;TotalSeconds=72391.4009002}
Year        : 2012
```

В примере используется `Select-Object` командлет для получения всех свойств объекта **DateTime** . Он использует `ConvertTo-Json` командлет для преобразования объекта **DateTime** в строку, отформатированную в виде объекта JSON, и `ConvertFrom-Json` командлет для преобразования строки в формате JSON в объект **PSCustomObject** .

### Пример 2. Получение строк JSON из веб-службы и их преобразование в объекты PowerShell

Эта команда использует `Invoke-WebRequest` командлет для получения строк JSON из веб-службы, а затем использует `ConvertFrom-Json` командлет для преобразования содержимого JSON в объекты, которыми можно управлять в PowerShell.

```powershell
# Ensures that Invoke-WebRequest uses TLS 1.2
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
$j = Invoke-WebRequest 'https://api.github.com/repos/PowerShell/PowerShell/issues' | ConvertFrom-Json
```

Можно также использовать `Invoke-RestMethod` командлет, который автоматически преобразует содержимое JSON в объекты.

### Пример 3. Преобразование строки JSON в пользовательский объект

В этом примере показано, как использовать `ConvertFrom-Json` командлет для преобразования JSON-файла в пользовательский объект PowerShell.

```powershell
Get-Content JsonFile.JSON | ConvertFrom-Json
```

Команда использует командлет Get-Content для получения строк в JSON-файле. Затем он использует оператор конвейера для отправки строки с разделителями в `ConvertFrom-Json` командлет, который преобразует его в пользовательский объект.

### Пример 4. Преобразование строки JSON в хэш-таблицу

Эта команда показывает пример, в котором `-AsHashtable` коммутатор может преодолеть ограничения команды.

```powershell
'{ "key":"value1", "Key":"value2" }' | ConvertFrom-Json -AsHashtable
```

Строка JSON содержит две пары "ключ — значение" с ключами, которые отличаются только регистром. Без параметра команда вызовет ошибку.

### Пример 5. цикл обработки одного массива элементов

Эта команда показывает пример, в котором `-NoEnumerate` параметр используется для приема-передачи массива JSON с одним элементом.

```powershell
Write-Output "With -NoEnumerate: $('[1]' | ConvertFrom-Json -NoEnumerate | ConvertTo-Json -Compress)"
Write-Output "Without -NoEnumerate: $('[1]' | ConvertFrom-Json | ConvertTo-Json -Compress)"
```

```Output
With -NoEnumerate: [1]
Without -NoEnumerate: 1
```

Строка JSON содержит массив с одним элементом. Без параметра преобразование JSON в PSObject, а затем преобразование его обратно с помощью `ConvertTo-Json` команды приводит к одному целому числу.

## PARAMETERS

### -AsHashtable

Преобразует JSON в объект хэш-таблицы. Этот параметр появился в PowerShell 6,0. Существует несколько сценариев, в которых можно преодолеть некоторые ограничения `ConvertFrom-Json` командлета.

- Если в JSON содержится список с ключами, отличающимися только регистром. Без параметра эти ключи будут рассматриваться как идентичные ключи, поэтому будет использоваться только последний из них.
- Если в JSON содержится ключ, являющийся пустой строкой. Без параметра командлет выдаст ошибку, так как не разрешает это `PSCustomObject` , но хэш-таблица делает это. В качестве примера использования может возникнуть ситуация, когда это `project.lock.json` файлы.
- Хэш-таблицы могут обрабатываться быстрее для определенных структур данных.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Depth

Возвращает или задает максимальную глубину, которой может обладать входные данные JSON. По умолчанию это 1024.

Этот параметр появился в PowerShell 6,2.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Указывает строки JSON, которые нужно преобразовать в объекты JSON. Введите переменную, содержащую строку, либо введите команду или выражение для получения строки. Можно также передать строку в `ConvertFrom-Json` .

Параметр **InputObject** обязателен, но его значением может быть пустая строка. Если входной объект является пустой строкой, `ConvertFrom-Json` не создает никаких выходных данных. Значение **InputObject** не может быть `$null` .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Не перечислять

Указывает, что выходные данные не перечисляются.

Установка этого параметра приводит к тому, что массивы отправляются в виде одного объекта вместо отправки каждого элемента отдельно. Это гарантирует, что JSON можно будет обрабатывать с помощью `ConvertTo-Json` .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

Строку JSON можно передать в `ConvertFrom-Json` .

## Выходные данные

### PSCustomObject

### System.Collections.Hashtable

## ПРИМЕЧАНИЯ

Этот командлет реализуется с помощью [Newtonsoft JSON.NET](https://www.newtonsoft.com/json).

Начиная с PowerShell 6, `ConvertTo-Json` пытается преобразовать строки, отформатированные как метки времени, в значения **типа DateTime** . Преобразованное значение является `[datetime]` экземпляром с `Kind` набором свойств следующим образом:

- `Unspecified`значение, если во входной строке нет сведений о часовом поясе.
- `Utc`значение, если сведения о часовом поясе являются конечными `Z` .
- `Local`значение, если сведения о часовом поясе заданы в качестве _смещения_ в конце UTC, например `+02:00` . Смещение правильно преобразуется в настроенный часовой пояс вызывающего объекта. Форматирование выхода по умолчанию не указывает на исходное смещение часового пояса.

## Связанные ссылки

[Введение в нотация объектов JavaScript (JSON) в JavaScript и .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))

[ConvertTo-Json](ConvertTo-Json.md)

[Invoke-WebRequest](Invoke-WebRequest.md)

[Invoke-RestMethod](Invoke-RestMethod.md)
