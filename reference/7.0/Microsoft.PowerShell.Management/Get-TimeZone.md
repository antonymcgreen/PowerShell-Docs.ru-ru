---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-timezone?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TimeZone
ms.openlocfilehash: 44740fff5b8cef989d4c6391379741d1882f4734
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345618"
---
# Get-TimeZone

## Краткий обзор
Возвращает текущий часовой пояс или список доступных часовых поясов.

## SYNTAX

### Имя (по умолчанию)

```
Get-TimeZone [[-Name] <String[]>] [<CommonParameters>]
```

### Идентификатор

```
Get-TimeZone -Id <String[]> [<CommonParameters>]
```

### ListAvailable

```
Get-TimeZone [-ListAvailable] [<CommonParameters>]
```

## DESCRIPTION

Командлет **Get-TimeZone** получает текущий часовой пояс или список доступных часовых поясов.

## Примеры

### Пример 1. Получение текущего часового пояса

```
PS C:\> Get-TimeZone
Pacific Standard Time
```

Эта команда возвращает текущий часовой пояс.

### Пример 2. получение часовых поясов, соответствующих указанной строке

```
PS C:\> Get-TimeZone -Name "*pac*"
Pacific Standard Time (Mexico)

(UTC-08:00) Pacific Time (US &amp; Canada)

Pacific Standard Time

SA Pacific Standard Time

Pacific SA Standard Time

West Pacific Standard Time

Central Pacific Standard Time
```

Эта команда возвращает все часовые пояса, соответствующие указанному подстановочному знаку.

### Пример 3. получение всех доступных часовых поясов

```
PS C:\> Get-TimeZone -ListAvailable
```

Эта команда возвращает все доступные часовые пояса.

## PARAMETERS

### -Id

Указывает в виде массива строк идентификатор или идентификаторы часовых поясов, которые получает этот командлет.

```yaml
Type: System.String[]
Parameter Sets: Id
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ListAvailable

Указывает, что этот командлет получает все доступные часовые пояса.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ListAvailable
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Указывает в виде массива строк имя или имена часовых поясов, которые получает этот командлет.

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String[]

## Выходные данные

### System. TimeZoneInfo []

## ПРИМЕЧАНИЯ

Этот командлет доступен только на платформах Windows.

## Связанные ссылки

[Set-TimeZone](Set-TimeZone.md)
