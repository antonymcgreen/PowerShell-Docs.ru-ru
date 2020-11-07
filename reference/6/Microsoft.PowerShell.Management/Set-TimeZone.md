---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/18/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-timezone?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-TimeZone
ms.openlocfilehash: 3738ac6202fa7a46c9a742e48edaeb1b82b5d749
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345125"
---
# Set-TimeZone

## Краткий обзор
Устанавливает часовой пояс системы в указанный часовой пояс.

## SYNTAX

### Имя (по умолчанию)

```
Set-TimeZone [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Идентификатор

```
Set-TimeZone -Id <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject

```
Set-TimeZone [-InputObject] <TimeZoneInfo> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Set-TimeZone`Командлет устанавливает часовой пояс системы в указанный часовой пояс.

## Примеры

### Пример 1. Задание часового пояса по идентификатору

В этом примере задается часовой пояс на локальном компьютере в русском языке (зима).

```powershell
Set-TimeZone -Id "Russian Standard Time" -PassThru
```

```Output
Id                         : Russian Standard Time
DisplayName                : (UTC+03:00) Moscow, St. Petersburg
StandardName               : Russia TZ 2 Standard Time
DaylightName               : Russia TZ 2 Daylight Time
BaseUtcOffset              : 03:00:00
SupportsDaylightSavingTime : True
```

### Пример 2. Настройка часового пояса по имени

В этом примере задается часовой пояс на локальном компьютере в русском языке (зима).

```powershell
Set-TimeZone -Name "Russia TZ 2 Standard Time"
```

Как было показано в предыдущем примере, **идентификатор** и **имя** часового пояса не всегда совпадают.
Параметр **Name** должен соответствовать свойствам **StandardName** или **дайлигхтнаме** объекта **TimeZoneInfo** .

## PARAMETERS

### -Id

Указывает идентификатор часового пояса, который задается этим командлетом. Полный список идентификаторов часовых поясов можно получить, выполнив следующую команду: `Get-TimeZone -ListAvailable` .

```yaml
Type: System.String
Parameter Sets: Id
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject

Указывает объект **TimeZoneInfo** для использования в качестве входных данных.

```yaml
Type: System.TimeZoneInfo
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Указывает имя часового пояса, который устанавливает этот командлет. Полный список имен часовых поясов можно получить, выполнив следующую команду: `Get-TimeZone -ListAvailable` .

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Возвращает объект, представляющий элемент, с которым вы работаете. По умолчанию этот командлет не создает выходные данные.

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

### -Confirm

Запрос подтверждения перед выполнением командлета.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Показывает, что произойдет при запуске командлета. Командлет не выполняется.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System. String, System. TimeZoneInfo, System. String

## Выходные данные

## ПРИМЕЧАНИЯ

Этот командлет доступен только на платформах Windows.

## Связанные ссылки

[Get-TimeZone](Get-TimeZone.md)
