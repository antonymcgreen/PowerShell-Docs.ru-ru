---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-json?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Json
ms.openlocfilehash: f2159a2de3432aec14fb395b93ed476f349616a8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227737"
---
# ConvertFrom-Json

## Краткий обзор
Преобразует строку в формате JSON в пользовательский объект.

## SYNTAX

```
ConvertFrom-Json [-InputObject] <String> [<CommonParameters>]
```

## DESCRIPTION

`ConvertFrom-Json`Командлет преобразует строку в формате нотация объектов JavaScript (JSON) в пользовательский объект **PSCustomObject** , имеющий свойство для каждого поля в строке JSON. Формат JSON обычно используется на веб-сайтах для текстового представления объектов. Стандарт JSON не запрещает использование, которое запрещено **PSCustomObject** . Например, если строка JSON содержит дублирующиеся ключи, этот командлет использует только последний ключ. См. Другие примеры ниже.

Чтобы создать строку JSON из любого объекта, используйте `ConvertTo-Json` командлет.

Этот командлет появился в PowerShell 3,0.

> [!NOTE]
> Этот командлет не поддерживает JSON с комментариями.

## Примеры

### Пример 1. преобразование объекта DateTime в объект JSON

Эта команда использует `ConvertTo-Json` `ConvertFrom-Json` командлеты и для преобразования объекта **DateTime** из `Get-Date` командлета в объект JSON и затем в **PSCustomObject** .

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

## PARAMETERS

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

Строку JSON можно передать в `ConvertFrom-Json` .

## Выходные данные

### PSCustomObject

## ПРИМЕЧАНИЯ

`ConvertFrom-Json`Командлет реализуется с помощью [класса JavaScriptSerializer](/dotnet/api/system.web.script.serialization.javascriptserializer).

## Связанные ссылки

[Введение в нотация объектов JavaScript (JSON) в JavaScript и .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))

[ConvertTo-Json](ConvertTo-Json.md)

[Invoke-WebRequest](Invoke-WebRequest.md)

[Invoke-RestMethod](Invoke-RestMethod.md)
