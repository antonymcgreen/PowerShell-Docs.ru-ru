---
external help file: Microsoft.PowerShell.ConsoleHost.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Host
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.host/stop-transcript?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Transcript
ms.openlocfilehash: 16b41711e98276fee37d56f77f57e7372daa4cf3
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605284"
---
# Stop-Transcript

## Краткий обзор
Останавливает запись.

## SYNTAX

```
Stop-Transcript [<CommonParameters>]
```

## DESCRIPTION

`Stop-Transcript`Командлет останавливает запись, которая была запущена `Start-Transcript` командлетом.
Кроме того, можно завершить сеанс, чтобы прекратить запись разговора.

## Примеры

### Пример 1. завершение всех записей

```powershell
Stop-Transcript
```

Эта команда останавливает все записи.

## PARAMETERS

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### None

В этот командлет нельзя передать входные данные.

## Выходные данные

### System.String

Этот командлет возвращает строку, содержащую сообщение о состоянии и путь к выходному файлу.

## ПРИМЕЧАНИЯ

* Если запись разговора не была запущена, команда завершается ошибкой.

*

## Связанные ссылки

[Start-Transcript](Start-Transcript.md)

