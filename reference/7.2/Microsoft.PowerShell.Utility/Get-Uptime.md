---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-uptime?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Uptime
ms.openlocfilehash: 0b71d59175ed56e7aad6a24035d1eff5503e4d88
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602276"
---
# Get-Uptime

## Краткий обзор
Получение **временного интервала** с момента последней загрузки.

## SYNTAX

### TimeSpan (по умолчанию)

```
Get-Uptime [<CommonParameters>]
```

### Шедших

```
Get-Uptime [-Since] [<CommonParameters>]
```

## DESCRIPTION

Этот командлет возвращает время, прошедшее с момента последней загрузки операционной системы.

`Get-Uptime`Командлет был представлен в PowerShell 6,0.

## Примеры

### Пример 1. Отображение времени с момента последней загрузки

```powershell
Get-Uptime
```

```Output
Days              : 9
Hours             : 0
Minutes           : 9
Seconds           : 45
Milliseconds      : 0
Ticks             : 7781850000000
TotalDays         : 9.00677083333333
TotalHours        : 216.1625
TotalMinutes      : 12969.75
TotalSeconds      : 778185
TotalMilliseconds : 778185000
```

### Пример 2. Отображение времени последней загрузки

```powershell
Get-Uptime -Since
```

```Output
Tuesday, June 18, 2019 2:34:56 PM
```

## PARAMETERS

### — С

Вызов командлета для возврата объекта **DateTime** , представляющего время последней загрузки операционной системы.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Since
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

### None

## Выходные данные

### System.TimeSpan

Это возвращаемый тип по умолчанию, если параметры не используются.

### System.DateTime

Этот тип возвращается при использовании параметра **с** .

> [!NOTE]
> Если параметр быстрого запуска Windows включен, Windows не обновляет значение, хранящееся в **LastBootUpTime**. Чтобы отключить быстрый запуск, выполните следующую команду: `Powercfg -h off` .
>
> Дополнительные сведения о быстром запуске Windows см. в разделе [различия быстрого запуска от пробуждения из спящего режима](/windows-hardware/drivers/kernel/distinguishing-fast-startup-from-wake-from-hibernation).

## ПРИМЕЧАНИЯ

В Windows возвращаемое значение совпадает со свойством **LastBootUpTime** класса **Win32_OperatingSystem** в WMI.

## Связанные ссылки

[Win32_OperatingSystem](/windows/win32/cimwin32prov/win32-operatingsystem#properties)

