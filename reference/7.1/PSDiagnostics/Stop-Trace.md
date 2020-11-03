---
external help file: PSDiagnostics-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/stop-trace?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Trace
ms.openlocfilehash: 7331c7ca1ece02757859e75eefddd5a662353beb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226509"
---
# Stop-Trace

## Краткий обзор
Останавливает сеанс ведения журнала трассировки событий.

## SYNTAX

```
Stop-Trace [-SessionName] <Object> [-ETS] [<CommonParameters>]
```

## DESCRIPTION

Этот командлет останавливает сеанс ведения журнала трассировки событий Windows.

Этот командлет используется следующими командлетами:

- `Disable-PSWSManCombinedTrace`
- `Disable-WSManTrace`

Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.

## Примеры

### Пример 1. Завершение сеанса ведения журнала трассировки WSMan

```powershell
Stop-Trace -SessionName 'wsmlog'
```

## PARAMETERS

### -ETS
Отправка команд в сеансы трассировки событий напрямую без сохранения или планирования.

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

### -SessionName
Имя останавливаемого сеанса трассировки событий.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

## Выходные данные

### Нет

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Трассировка событий](/windows/desktop/ETW/event-tracing-portal)

[Start-Trace](start-trace.md)

[Disable-PSWSManCombinedTrace](Disable-PSWSManCombinedTrace.md)

[Disable-WSManTrace](Disable-WSManTrace.md)

[Enable-PSWSManCombinedTrace](Enable-PSWSManCombinedTrace.md)

[Enable-WSManTrace](Enable-WSManTrace.md)

