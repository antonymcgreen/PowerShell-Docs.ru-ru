---
external help file: PSDiagnostics-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-wsmantrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WSManTrace
ms.openlocfilehash: 08c9d61f210761e2ed7a3a5014812b2bd362201b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227433"
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

### Нет

## Выходные данные

### System.Object

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Трассировка событий](/windows/desktop/ETW/event-tracing-portal)

[Start-Trace](start-trace.md)

[Disable-WSManTrace](Disable-WSManTrace.md)
