---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/new-winevent?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WinEvent
ms.openlocfilehash: 8e64c3e3a782fadf1669f1310d1615f3a014ccee
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225666"
---
# New-WinEvent

## Краткий обзор
Создает новое событие Windows для указанного поставщика событий.

## SYNTAX

```
New-WinEvent [-ProviderName] <String> [-Id] <Int32> [-Version <Byte>] [[-Payload] <Object[]>]
 [<CommonParameters>]
```

## DESCRIPTION

Командлет **New-WinEvent** создает событие "Трассировка событий Windows (ETW)" для поставщика событий.
С помощью этого командлета можно добавлять события в каналы ETW из PowerShell.

## Примеры

### Пример 1

```powershell
PS C:\> New-WinEvent -ProviderName Microsoft-Windows-PowerShell -Id 45090 -Payload @("Workflow", "Running")
```

В этой команде командлет **New-WinEvent** используется для создания события 45090 для поставщика Microsoft-Windows-PowerShell.

## PARAMETERS

### -Id

Указывает идентификатор события, зарегистрированный посредством манифеста инструментария.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Полезные данные

Указывает сообщение события. Когда событие записывается в журнал событий, полезные данные сохраняются в свойстве **Message** объекта события.

Если указанные полезные данные не соответствуют полезной нагрузке в определении события, PowerShell выдает предупреждение, но команда по-прежнему выполняется.

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProviderName

Указывает поставщика событий, который записывает событие в журнал событий, например Microsoft-Windows-PowerShell. Поставщик событий ETW — это логическая сущность, которая записывает события в сеансы ETW.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Version

Указывает номер версии события. Введите номер события. PowerShell преобразует число в требуемый тип Byte.

Этот параметр позволяет указать событие, если определены разные версии одного и того же события.

```yaml
Type: System.Byte
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

Этот командлет не принимает входные данные по конвейеру.

## Выходные данные

### Нет

Этот командлет не создает никаких выходных данных.

## ПРИМЕЧАНИЯ

* После того как поставщик записывает данные в журнал событий, можно использовать командлет Get-WinEvent, чтобы получить событие из журнала.

## Связанные ссылки

[Get-WinEvent](Get-WinEvent.md)
