---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pstrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSTrace
ms.openlocfilehash: fc58e0bcfdd0b4ee7c7ee383b44f7d7f428c34c0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227446"
---
# Disable-PSTrace

## Краткий обзор
Отключает журналы поставщика событий Microsoft-Windows-PowerShell.

## SYNTAX

```
Disable-PSTrace [-AnalyticOnly] [<CommonParameters>]
```

## DESCRIPTION

Этот командлет отключает операционные и аналитические журналы событий поставщика событий Microsoft-Windows-PowerShell.

Этот командлет необходимо запустить из сеанса PowerShell с повышенными привилегиями.

## Примеры

### Пример 1. Отключение журнала аналитических событий для PowerShell

В следующем примере отключается только журнал аналитических событий поставщика Microsoft-Windows-PowerShell.

```powershell
Disable-PSTrace -AnalyticOnly
```

## PARAMETERS

### -Аналитиконли

При использовании этого параметра командлет отключает журнал аналитических событий поставщика Microsoft-Windows-PowerShell. Журнал рабочих событий не изменяется.

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

[Enable-PSTrace](Enable-PSTrace.md)
