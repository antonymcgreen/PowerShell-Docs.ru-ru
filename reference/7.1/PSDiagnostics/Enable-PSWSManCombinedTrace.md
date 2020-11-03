---
external help file: PSDiagnostics-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pswsmancombinedtrace?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSWSManCombinedTrace
ms.openlocfilehash: 0999c59ab2e27b066dc6afa0b21cce029a9419e1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226514"
---
# Enable-PSWSManCombinedTrace

## Краткий обзор
Запустите сеанс ведения журнала с включенными поставщиками WSMan и PowerShell.

## SYNTAX

```
Enable-PSWSManCombinedTrace [-DoNotOverwriteExistingTrace] [<CommonParameters>]
```

## DESCRIPTION

Этот командлет запускает сеанс ведения журнала со следующими включенными поставщиками PowerShell:

- Microsoft-Windows PowerShell
- Microsoft-Windows — WinRM

Сеанс называется "Пстраце".

Этот командлет использует `Start-Trace` командлет.

Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.

## Примеры

### Пример 1. Запуск Объединенного сеанса ведения журнала

```powershell
Enable-PSWSManCombinedTrace
```

## PARAMETERS

### -Донотовервритиксистингтраце

По умолчанию события записываются в "$pshome \Трацес\пстраце.ЕТЛ". При использовании этого параметра командлет создает уникальное имя файла: "$pshome \Трацес\ PSTrace_ {GUID}. ETL".

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

