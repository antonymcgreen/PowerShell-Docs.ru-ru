---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-wsmantrace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WSManTrace
ms.openlocfilehash: a9d91eab94666186c13f8d5c928d83055f6dbefa
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601495"
---
# Enable-WSManTrace

## Краткий обзор
Запустите сеанс ведения журнала с включенными поставщиками WSMan.

## SYNTAX

```
Enable-WSManTrace [<CommonParameters>]
```

## DESCRIPTION
Этот командлет запускает сеанс ведения журнала с включенными поставщиками WSMan. Включены следующие поставщики событий:

- Пересылка событий
- ипмидрв
- ипмипрв
- WinRM
- винрскмд
- винрсексе
- винрсмгр
- всманпровхост

Сеанс называется "всмлог".

Этот командлет использует `Start-Trace` командлет.

Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.

## Примеры

### Пример 1. Запуск сеанса ведения журнала WSMan.

```powershell
Enable-WSManTrace
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

[Start-Trace](start-trace.md)

[Disable-WSManTrace](Disable-WSManTrace.md)

