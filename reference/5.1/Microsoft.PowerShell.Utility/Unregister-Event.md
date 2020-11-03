---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unregister-event?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-Event
ms.openlocfilehash: f1f42c1e8831896feac398228e45fc0890136fff
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227482"
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
Командлет **Unregister-Event** отменяет подписку на событие, созданную с помощью командлета Register-EngineEvent, Register-ObjectEvent или Register-WmiEvent.

При отмене подписки на событие подписчик удаляется из сеанса, а события, на которые была оформлена подписка, больше не добавляются в очередь событий.
При отмене подписки на событие, созданное с помощью командлета New-Event, новое событие также удаляется из сеанса.

**Отмена регистрации — событие** не удаляет события из очереди событий.
Чтобы удалить события, используйте командлет Remove-Event.

## Примеры

### Пример 1. Отмена подписки на событие по идентификатору источника

```
PS C:\> Unregister-Event -SourceIdentifier "ProcessStarted"
```

Эта команда отменяет подписку на событие, имеющую идентификатор источника ProcessStarted.

Чтобы определить идентификатор источника события, используйте командлет Get-Event.
Чтобы найти идентификатор источника подписки на события, используйте командлет **Get-EventSubscriber** .

### Пример 2. Отмена подписки на событие по идентификатору подписки

```
PS C:\> Unregister-Event -SubscriptionId 2
```

Эта команда отменяет подписку на событие с идентификатором подписки 2.

Чтобы найти идентификатор подписки для подписки на события, используйте командлет **Get-EventSubscriber** .

### Пример 3. Отмена всех подписок на события

```
PS C:\> Get-EventSubscriber -Force | Unregister-Event -Force
```

Эта команда отменяет все подписки на события в рамках сеанса.

Команда использует командлет **Get-EventSubscriber** для получения всех объектов подписчиков событий в сеансе, включая подписчики, скрытые с помощью параметра *SupportEvent* командлетов регистрации событий.

Он использует оператор конвейера (|) для отправки объектов подписчика для **отмены регистрации — события** , которое удаляет их из сеанса.
Для выполнения задачи параметр *Force* также требуется при **отмене регистрации-события** .

## PARAMETERS

### -Force
Отменяет все подписки на события, включая подписки, которые были скрыты с помощью параметра *SupportEvent* **Register-ObjectEvent** , **Register-WmiEvent** и **Register-EngineEvent** .

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

Параметр *SourceIdentifier* или *SubscriptionId* должен включаться в каждую команду.

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

Параметр *SourceIdentifier* или *SubscriptionId* должен включаться в каждую команду.

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
Показывает, что произойдет при запуске командлета.
Командлет не выполняется.

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
Выходные данные можно передать из Get-EventSubscriber в командлет **Unregister-Event** .

## Выходные данные

### Нет
Этот командлет не возвращает никакие выходные данные.

## ПРИМЕЧАНИЯ

* События, подписки на события и очередь событий существуют только в текущем сеансе. Если закрыть текущий сеанс, очередь событий удаляется, а подписка на событие отменяется.

  **Отмена регистрации — событие** не может удалять события, созданные с помощью командлета New-Event, если только вы не подписаны на событие с помощью командлета **Register-EngineEvent** .
Чтобы удалить из сеанса настраиваемое событие, используйте программный способ или закройте сеанс.

*

## Связанные ссылки

[Get-Event](Get-Event.md)

[Get-EventSubscriber](Get-EventSubscriber.md)

[New-Event](New-Event.md)

[Register-EngineEvent](Register-EngineEvent.md)

[Register-ObjectEvent](Register-ObjectEvent.md)

[Remove-Event](Remove-Event.md)

[Unregister-Event](Unregister-Event.md)

[Wait-Event](Wait-Event.md)
