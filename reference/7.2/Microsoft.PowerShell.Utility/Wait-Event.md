---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/wait-event?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Event
ms.openlocfilehash: caf2a1c80848d3140e7ad46fdf54dbe71886c633
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603103"
---
# Wait-Event

## Краткий обзор
Ожидает определенное событие, прежде чем продолжить выполнение.

## SYNTAX

```
Wait-Event [[-SourceIdentifier] <String>] [-Timeout <Int32>] [<CommonParameters>]
```

## DESCRIPTION

`Wait-Event`Командлет приостанавливает выполнение скрипта или функции до тех пор, пока не будет вызвано определенное событие. Выполнение возобновляется после обнаружении события. Чтобы отменить ожидание, нажмите клавиши <kbd>CTRL</kbd> + <kbd>C</kbd>.

Эта функция представляет альтернативу опросу события. Он также позволяет определить ответ на событие двумя разными способами:

- Использование параметра **Action** подписки на события
- ожидание возврата события и ответ с действием

## Примеры

### Пример 1. ожидание следующего события

В этом примере ожидает следующего вызванного события.

```powershell
Wait-Event
```

### Пример 2. ожидание события с указанным идентификатором источника

Этот пример ожидает следующего вызванного события и имеет идентификатор источника ProcessStarted.

```powershell
Wait-Event -SourceIdentifier "ProcessStarted"
```

### Пример 3. ожидание события Elapsed Timer

В этом примере используется `Wait-Event` командлет для ожидания события таймера в таймере, установленном в течение 2000 миллисекунд.

```powershell
$Timer = New-Object Timers.Timer
$objectEventArgs = @{
    InputObject = $Timer
    EventName = 'Elapsed'
    SourceIdentifier = 'Timer.Elapsed'
}
Register-ObjectEvent @objectEventArgs
$Timer.Interval = 2000
$Timer.Autoreset = $False
$Timer.Enabled = $True
Wait-Event Timer.Elapsed
```

```Output
ComputerName     :
RunspaceId       : bb560b14-ff43-48d4-b801-5adc31bbc6fb
EventIdentifier  : 1
Sender           : System.Timers.Timer
SourceEventArgs  : System.Timers.ElapsedEventArgs
SourceArgs       : {System.Timers.Timer, System.Timers.ElapsedEventArgs}
SourceIdentifier : Timer.Elapsed
TimeGenerated    : 4/23/2020 2:30:37 PM
MessageData      :
```

### Пример 4. ожидание события после указанного времени ожидания

В этом примере ожидается задержка до 90 секунд для следующего вызванного события и имеющего идентификатор источника **ProcessStarted**. Если указанное время истекает, ожидание завершается.

```powershell
Wait-Event -SourceIdentifier "ProcessStarted" -Timeout 90
```

## PARAMETERS

### -SourceIdentifier

Указывает идентификатор источника, который этот командлет ожидает события.
По умолчанию `Wait-Event` ожидает любого события.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Timeout

Указывает максимальное время в секундах, которое ожидает наступления `Wait-Event` события. Значение по умолчанию, -1, обозначает неопределенное время ожидания. Время начинается с момента отправки `Wait-Event` команды.

Если указанное время ожидания превышено, ожидание прекращается и возвращается командная строка, даже если событие не возникло. Сообщение об ошибке не отображается.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutSec

Required: False
Position: Named
Default value: -1
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

## Выходные данные

### System. Management. Automation. PSEventArgs

## ПРИМЕЧАНИЯ

События, подписки на события и очередь событий существуют только в текущем сеансе. Если закрыть текущий сеанс, очередь событий удаляется, а подписка на событие отменяется.

## Связанные ссылки

[Get-Event](Get-Event.md)

[Get-EventSubscriber](Get-EventSubscriber.md)

[New-Event](New-Event.md)

[Register-EngineEvent](Register-EngineEvent.md)

[Register-ObjectEvent](Register-ObjectEvent.md)

[Remove-Event](Remove-Event.md)

[Unregister-Event](Unregister-Event.md)

[Wait-Event](Wait-Event.md)

