---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pstrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSTrace
ms.openlocfilehash: 9abc91086d42ec7b813695e241820947f7fb0acc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227437"
---
# Enable-PSTrace

## Краткий обзор
Включает журналы поставщика событий Microsoft-Windows-PowerShell.

## SYNTAX

```
Enable-PSTrace [-Force] [-AnalyticOnly]
```

## DESCRIPTION

Этот командлет включает операционные и аналитические журналы событий поставщика событий Microsoft-Windows-PowerShell.

Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.

## Примеры

### Пример 1. Включение журнала аналитических событий для PowerShell

В следующем примере включается только журнал аналитических событий поставщика Microsoft-Windows-PowerShell.

```powershell
Enable-PSTrace -AnalyticOnly
```

## PARAMETERS

### -Аналитиконли

При использовании этого параметра командлет включает журнал аналитических событий поставщика Microsoft-Windows-PowerShell. Журнал рабочих событий не изменяется.

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

### -Force

Используется для принудительного изменения без запроса.

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

## Входные данные

### Нет

## Выходные данные

### System.Object

## ПРИМЕЧАНИЯ

Этот командлет использует `Get-LogProperties` `Set-LogProperties` командлеты и.

Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.

## Связанные ссылки

[Get-LogProperties](Get-LogProperties.md)

[Set-LogProperties](Set-LogProperties.md)

[Disable-PSTrace](Disable-PSTrace.md)
