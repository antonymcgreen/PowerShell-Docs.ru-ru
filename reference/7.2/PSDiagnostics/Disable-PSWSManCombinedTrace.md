---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pswsmancombinedtrace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSWSManCombinedTrace
ms.openlocfilehash: 690a8b050fd0e16033a585df210db340f41a83a3
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600668"
---
# Disable-PSWSManCombinedTrace

## Краткий обзор
Завершите сеанс ведения журнала, запущенный параметром enable-Псвсманкомбинедтраце.

## SYNTAX

```
Disable-PSWSManCombinedTrace [<CommonParameters>]
```

## DESCRIPTION

Этот командлет останавливает сеанс ведения журнала, запущенный `Enable-PSWSManCombinedTrace` .

Этот командлет использует `Stop-Trace` командлет.

Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.

## Примеры

### Пример 1. Отключение Объединенного сеанса ведения журнала

```powershell
Disable-PSWSManCombinedTrace
```

## PARAMETERS

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### None

## Выходные данные

### None

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Трассировка событий](/windows/desktop/ETW/event-tracing-portal)

[Stop-Trace](stop-trace.md)

[Enable-PSWSManCombinedTrace](Enable-PSWSManCombinedTrace.md)

