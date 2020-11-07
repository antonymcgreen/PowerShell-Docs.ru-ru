---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-event?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Event
ms.openlocfilehash: 101732472611943a52c54e6517f42f523b513cfa
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347658"
---
# Remove-Event

## Краткий обзор
Удаляет события из очереди событий.

## SYNTAX

### Бисаурце (по умолчанию)

```
Remove-Event [-SourceIdentifier] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### бидентифиер

```
Remove-Event [-EventIdentifier] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Remove-Event`Командлет удаляет события из очереди событий в текущем сеансе.

Этот командлет удаляет только те события, которые в данный момент находятся в очереди. Чтобы отменить регистрацию событий или отказаться от подписки, используйте `Unregister-Event` командлет.

## Примеры

### Пример 1. Удаление события по идентификатору источника

```
PS C:\> Remove-Event -SourceIdentifier "ProcessStarted"
```

Эта команда удаляет события с идентификатором источника процесса, запущенным из очереди событий.

### Пример 2. Удаление события по идентификатору события

```
PS C:\> Remove-Event -EventIdentifier 30
```

Эта команда удаляет из очереди событий событие с идентификатором 30.

### Пример 3. Удаление всех событий

```
PS C:\> Get-Event | Remove-Event
```

Эта команда удаляет все события из очереди событий.

## PARAMETERS

### -EventIdentifier

Указывает идентификатор события, для которого удаляется командлет. В каждой команде требуется параметр **EventIdentifier** или **SourceIdentifier** .

```yaml
Type: System.Int32
Parameter Sets: ByIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceIdentifier

Указывает идентификатор источника, из которого этот командлет удаляет события. Использовать подстановочные знаки запрещено. В каждой команде требуется параметр **EventIdentifier** или **SourceIdentifier** .

```yaml
Type: System.String
Parameter Sets: BySource
Aliases:

Required: True
Position: 0
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

### System. Management. Automation. PSEventArgs

Можно передать события из `Get-Event` в `Remove-Event` .

## Выходные данные

### Нет

Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

На платформах Linux и macOS нет доступных источников событий.

События, подписки на события и очередь событий существуют только в текущем сеансе. Если закрыть текущий сеанс, очередь событий удаляется, а подписка на событие отменяется.

## Связанные ссылки

[Get-Event](Get-Event.md)

[New-Event](New-Event.md)

[Register-EngineEvent](Register-EngineEvent.md)

[Register-ObjectEvent](Register-ObjectEvent.md)

[Remove-Event](Remove-Event.md)

[Unregister-Event](Unregister-Event.md)

[Wait-Event](Wait-Event.md)
