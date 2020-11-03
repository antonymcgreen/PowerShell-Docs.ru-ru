---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 4/30/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-date?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Date
ms.openlocfilehash: 1c2a029a20b80826f74662a2b68d4a5f32276b00
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226574"
---
# Set-Date

## Краткий обзор
Меняет системное время компьютера на указанное.

## SYNTAX

### Дата (по умолчанию)

```
Set-Date [-Date] <DateTime> [-DisplayHint <DisplayHintType>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Adjust

```
Set-Date [-Adjust] <TimeSpan> [-DisplayHint <DisplayHintType>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Set-Date`Командлет изменяет системную дату и время на компьютере на указанную дату и время.
Можно указать новую дату и (или) время, введя строку или передав объект **DateTime** или **TimeSpan** в `Set-Date` . Чтобы указать новую дату или время, используйте параметр **Date** .
Чтобы задать интервал изменения, используйте параметр **корректировки** .

## Примеры

### Пример 1. Добавление трех дней к системной дате

Эта команда добавляет к текущей системной дате три дня.
На время она не влияет.
Команда использует параметр **Date** для указания даты.

`Get-Date`Командлет возвращает текущую дату в виде объекта **DateTime** . Метод **AddDays** объекта **DateTime** добавляет указанное число дней (3) к текущему объекту **DateTime** .

```powershell
Set-Date -Date (Get-Date).AddDays(3)
```

### Пример 2. Настройка системных часов назад через 10 минут

В этом примере текущее системное время устанавливается на 10 минут.

Параметр " **изменить** " позволяет указать интервал изменения (не более десяти минут) в стандартном формате времени для языкового стандарта.

Параметр **дисплайхинт** указывает PowerShell отображать только время, но не влияет на объект **DateTime** , `Set-Date` возвращающий значение.

```powershell
Set-Date -Adjust -0:10:0 -DisplayHint Time
```

### Пример 3. Установка значения переменной даты и времени

Эти команды изменяют системную дату и время на локальном компьютере на дату и время, сохраненные в переменной `$T` . Первая команда получает дату и сохраняет ее в `$T` .

Вторая команда использует параметр **Date** для передачи объекта **DateTime** в `$T` `Set-Date` командлет.

```powershell
$T = Get-Date
Set-Date -Date $T
```

### Пример 4. Добавление в системные часы 90 минут

Эти команды переводят системное время на локальном компьютере на 90 минут вперед.

Первая команда использует `New-TimeSpan` командлет для создания объекта **TimeSpan** с интервалом в 90 минут и сохраняет его в `$90mins` переменной.

Вторая команда использует параметр **корректировки** `Set-Date` для для настройки даты по значению объекта **TimeSpan** в `$90mins` переменной.

```powershell
$90mins = New-TimeSpan -Minutes 90
Set-Date -Adjust $90mins
```

## PARAMETERS

### — Настройка

Задает значение, которое этот командлет добавляет или вычитает из текущей даты и времени.
можно ввести корректировку в стандартном формате даты и времени для языкового стандарта или использовать параметр " **изменить** " для передачи объекта **TimeSpan** из `New-TimeSpan` в `Set-Date` .

```yaml
Type: System.TimeSpan
Parameter Sets: Adjust
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Date

Устанавливает указанные значения даты и времени.
Можно ввести новую дату в кратком формате даты, а время — в стандартном формате времени для используемого языкового стандарта. Или можно передать объект **DateTime** из `Get-Date` .

Если указать дату, но не время, `Set-Date` то изменяет время на полночь на указанную дату. Если указано только время, дата не изменяется.

```yaml
Type: System.DateTime
Parameter Sets: Date
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -DisplayHint

Указывает, какие элементы даты и времени отображаются. Допустимые значения для этого параметра:

- дата.
  Отображает только дату.
- Время.
  Отображает только время.
- DateTime.
  Отображает дату и время.

Этот параметр влияет только на отображаемые значения
Он не влияет на объект **DateTime** , который `Get-Date` получает.

```yaml
Type: Microsoft.PowerShell.Commands.DisplayHintType
Parameter Sets: (All)
Aliases:
Accepted values: Date, Time, DateTime

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

Показывает, что произойдет при запуске командлета.
Командлет не выполняется.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### System.DateTime

Дату можно передать в `Set-Date` .

## Выходные данные

### System.DateTime

`Set-Date` Возвращает объект, представляющий заданную дату.

## ПРИМЕЧАНИЯ

- Используйте этот командлет с осторожностью при изменении даты и времени на компьютере. Из-за изменения даты или времени компьютер может не получать системные события и обновления, которые запускаются в определенный день или момент времени. Используйте параметры **WhatIf** и **Confirm** , чтобы избежать ошибок.
- Вы можете использовать стандартные методы .NET с объектами **DateTime** и **TimeSpan** , которые используются с `Set-Date` , например **AddDays** , **аддмонсс** и **фромфилетиме**. Дополнительные сведения см. в разделе [методы DateTime](/dotnet/api/system.datetime) и

  [Методы TimeSpan](/dotnet/api/system.timespan) в библиотеке MSDN.

## Связанные ссылки

[Get-Дата](Get-Date.md)

[New-TimeSpan](New-TimeSpan.md)

