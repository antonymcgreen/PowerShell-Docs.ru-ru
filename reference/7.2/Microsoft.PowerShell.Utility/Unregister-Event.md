---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unregister-event?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-Event
ms.openlocfilehash: 863dbba4c106f1f57c9396823692620bb358b646
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605280"
---
# Unregister-Event

## Краткий обзор
Отменяет подписку на событие.

## SYNTAX

### Бисаурце (по умолчанию)

```
Unregister-Event [-SourceIdentifier] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Метод byid

```
Unregister-Event [-SubscriptionId] <Int32> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Unregister-Event`Командлет отменяет подписку на событие, созданную с помощью `Register-EngineEvent` `Register-ObjectEvent` `Register-WmiEvent` командлета, или.

При отмене подписки на событие подписчик удаляется из сеанса, а события, на которые была оформлена подписка, больше не добавляются в очередь событий. При отмене подписки на событие, созданное с помощью `New-Event` командлета, новое событие также удаляется из сеанса.

`Unregister-Event` не удаляет события из очереди событий. Чтобы удалить события, используйте `Remove-Event` командлет.

## Примеры

### Пример 1. Отмена подписки на событие по идентификатору источника

```
PS C:\> Unregister-Event -SourceIdentifier "ProcessStarted"
```

Эта команда отменяет подписку на событие, имеющую идентификатор источника ProcessStarted.

Чтобы найти идентификатор источника события, используйте `Get-Event` командлет. Чтобы найти идентификатор источника подписки на события, используйте `Get-EventSubscriber` командлет.

### Пример 2. Отмена подписки на событие по идентификатору подписки

```
PS C:\> Unregister-Event -SubscriptionId 2
```

Эта команда отменяет подписку на событие с идентификатором подписки 2.

Чтобы найти идентификатор подписки подписки на события, используйте `Get-EventSubscriber` командлет.

### Пример 3. Отмена всех подписок на события

```
PS C:\> Get-EventSubscriber -Force | Unregister-Event -Force
```

Эта команда отменяет все подписки на события в рамках сеанса.

Команда использует `Get-EventSubscriber` командлет для получения всех объектов подписчиков событий в сеансе, включая подписчики, скрытые с помощью параметра **SupportEvent** командлетов регистрации событий.

Он использует оператор конвейера ( `|` ) для отправки объектов подписчика `Unregister-Event` , который удаляет их из сеанса. Для выполнения задачи параметр **Force** также требуется для `Unregister-Event` .

## PARAMETERS

### -Force

Отменяет все подписки на события, включая подписки, которые были скрыты с помощью параметра **SupportEvent** `Register-ObjectEvent` , `Register-WmiEvent` и `Register-EngineEvent` .

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

### -SourceIdentifier

Указывает идентификатор источника, который этот командлет отменяет подписки на события.

Параметр **SourceIdentifier** или **SubscriptionId** должен включаться в каждую команду.

```yaml
Type: System.String
Parameter Sets: BySource
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubscriptionId

Указывает идентификатор исходного идентификатора, по которому этот командлет отменяет подписки на события.

Параметр **SourceIdentifier** или **SubscriptionId** должен включаться в каждую команду.

```yaml
Type: System.Int32
Parameter Sets: ById
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### System. Management. Automation. Псевентсубскрибер

Выходные данные можно передать в `Get-EventSubscriber` `Unregister-Event` .

## Выходные данные

### None

Этот командлет не возвращает никакие выходные данные.

## ПРИМЕЧАНИЯ

На платформах Linux и macOS нет доступных источников событий.

События, подписки на события и очередь событий существуют только в текущем сеансе. Если закрыть текущий сеанс, очередь событий удаляется, а подписка на событие отменяется.

`Unregister-Event` невозможно удалить события, созданные с помощью `New-Event` командлета, если только вы не подписаны на событие с помощью `Register-EngineEvent` командлета. Чтобы удалить из сеанса настраиваемое событие, используйте программный способ или закройте сеанс.

## Связанные ссылки

[Get-Event](Get-Event.md)

[Get-EventSubscriber](Get-EventSubscriber.md)

[New-Event](New-Event.md)

[Register-EngineEvent](Register-EngineEvent.md)

[Register-ObjectEvent](Register-ObjectEvent.md)

[Remove-Event](Remove-Event.md)

[Unregister-Event](Unregister-Event.md)

[Wait-Event](Wait-Event.md)
