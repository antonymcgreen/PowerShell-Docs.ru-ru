---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/01/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-timespan?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-TimeSpan
ms.openlocfilehash: 5808685a5560d1cbf91c6705b90643c35702b28a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603955"
---
# New-TimeSpan

## Краткий обзор
Создает объект TimeSpan.

## SYNTAX

### Дата (по умолчанию)

```
New-TimeSpan [[-Start] <DateTime>] [[-End] <DateTime>] [<CommonParameters>]
```

### время;

```
New-TimeSpan [-Days <Int32>] [-Hours <Int32>] [-Minutes <Int32>] [-Seconds <Int32>] [<CommonParameters>]
```

## DESCRIPTION

`New-TimeSpan`Командлет создает объект **TimeSpan** , представляющий интервал времени.
Объект **TimeSpan** можно использовать для добавления или вычитания времени из объектов **DateTime** .

Без параметров `New-TimeSpan` команда возвращает объект **TimeSpan** , представляющий интервал времени, равный нулю.

## Примеры

### Пример 1. Создание объекта TimeSpan на указанный период

Эта команда создает объект **TimeSpan** с длительностью в 1 час и 25 минут и сохраняет его в переменной с именем `$TimeSpan` . Он отображает представление объекта **TimeSpan** .

```powershell
$TimeSpan = New-TimeSpan -Hours 1 -Minutes 25
$TimeSpan
```

```Output
Days              : 0
Hours             : 1
Minutes           : 25
Seconds           : 0
Milliseconds      : 0
Ticks             : 51000000000
TotalDays         : 0.0590277777777778
TotalHours        : 1.41666666666667
TotalMinutes      : 85
TotalSeconds      : 5100
TotalMilliseconds : 5100000
```

### Пример 2. Создание объекта TimeSpan для интервала времени

В этом примере создается новый объект **TimeSpan** , представляющий интервал между временем выполнения команды и 1 января 2010.

Эта команда не требует параметра **Start** , так как значением по умолчанию для параметра **Start** является текущая дата и время.

```powershell
New-TimeSpan -End (Get-Date -Year 2010 -Month 1 -Day 1)
```

### Пример 3. Получение даты 90 дней с текущей даты

```powershell
$90days = New-TimeSpan -Days 90
(Get-Date) + $90days
```

Эти команды возвращают дату на 90 дней позднее текущей.

### Пример 4. Обнаружение TimeSpan с момента обновления файла

Эта команда указывает, сколько времени прошло с момента последнего обновления файла справки [about_remote](../Microsoft.PowerShell.Core/About/about_Remote.md) .
Этот формат команды можно использовать для любого файла или любого другого объекта, имеющего свойство **LastWriteTime** .

Эта команда работает, так как параметр **Start** параметра `New-TimeSpan` имеет псевдоним **LastWriteTime**. При передаче объекта, имеющего свойство **LastWriteTime** `New-TimeSpan` , в PowerShell использует значение свойства **LastWriteTime** в качестве значения параметра **Start** .

```powershell
Get-ChildItem $PSHOME\en-us\about_remote.help.txt | New-TimeSpan
```

```Output
Days              : 321
Hours             : 21
Minutes           : 59
Seconds           : 22
Milliseconds      : 312
Ticks             : 278135623127728
TotalDays         : 321.916230471907
TotalHours        : 7725.98953132578
TotalMinutes      : 463559.371879547
TotalSeconds      : 27813562.3127728
TotalMilliseconds : 27813562312.7728
```

## PARAMETERS

### -Days

Указывает дни в интервале времени.
Значение по умолчанию — 0.

```yaml
Type: System.Int32
Parameter Sets: Time
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -End

Задает конец интервала времени.
Значением по умолчанию являются текущие дата и время.

```yaml
Type: System.DateTime
Parameter Sets: Date
Aliases:

Required: False
Position: 1
Default value: Current date and time
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### – Часы

Указывает часы в интервале времени.
Значение по умолчанию равно нулю.

```yaml
Type: System.Int32
Parameter Sets: Time
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Минут

Указывает минуты в интервале времени.
Значение по умолчанию — 0.

```yaml
Type: System.Int32
Parameter Sets: Time
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Секунд

Задает длину интервала времени в секундах.
Значение по умолчанию — 0.

```yaml
Type: System.Int32
Parameter Sets: Time
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — Запуск

Задает начало периода времени.
Введите строку, представляющую дату и время, например "3/15/09", или объект **DateTime** , например, один из `Get-Date` команд. Значением по умолчанию являются текущие дата и время.

Можно использовать **Start** или его псевдоним **LastWriteTime**.
Псевдоним **LastWriteTime** позволяет передавать объекты, имеющие свойство **LastWriteTime** , например файлы в файловой системе `[System.Io.FileIO]` , в параметр **Start** объекта `New-TimeSpan` .

```yaml
Type: System.DateTime
Parameter Sets: Date
Aliases: LastWriteTime

Required: False
Position: 0
Default value: Current date and time
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### System.DateTime

Объект **DateTime** , представляющий время начала, можно передать в `New-TimeSpan` .

## Выходные данные

### System.TimeSpan

`New-TimeSpan` Возвращает объект, представляющий интервал времени.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Get-Дата](Get-Date.md)

[Set-Date](Set-Date.md)

