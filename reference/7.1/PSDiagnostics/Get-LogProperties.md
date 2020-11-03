---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
Locale: en-US
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/get-logproperties?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LogProperties
ms.openlocfilehash: 5b95fe3bc643c9e12a3d216523c086d9b0cdf901
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226517"
---
# Get-LogProperties

## Краткий обзор
Извлекает свойства журнала событий Windows.

## SYNTAX

```
Get-LogProperties [-Name] <Object> [<CommonParameters>]
```

## DESCRIPTION

Этот командлет возвращает параметры конфигурации для журнала событий Windows. Этот командлет используется `Enable-PSTrace` `Disable-PSTrace` командлетами и.

## Примеры

### Пример 1. получение параметров конфигурации журнала событий Windows PowerShell

```powershell
Get-LogProperties 'Windows PowerShell'
```

```Output
Name       : Windows PowerShell
Enabled    : True
Type       : Admin
Retention  : False
AutoBackup : False
MaxLogSize : 15728640
```

## PARAMETERS

### -Name

Имя поставщика событий.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

## Выходные данные

### Microsoft. PowerShell. Diagnostics. Логдетаилс

Модуль **PSDiagnostics** добавляет класс **логдетаилс** в `Microsoft.PowerShell.Diagnostics` пространство имен.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Set-LogProperties](Set-LogProperties.md)

[Enable-PSTrace](Enable-PSTrace.md)

[Disable-PSTrace](Disable-PSTrace.md)

