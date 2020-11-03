---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-event?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Event
ms.openlocfilehash: f9f4edca0fce4633daeac9ac11a3ccfb09feb98a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227661"
---
# Get-Event

## Краткий обзор
Получает события из очереди событий.

## SYNTAX

### Бисаурце (по умолчанию)

```
Get-Event [[-SourceIdentifier] <String>] [<CommonParameters>]
```

### Метод byid

```
Get-Event [-EventIdentifier] <Int32> [<CommonParameters>]
```

## DESCRIPTION
Командлет **Get-Event** Возвращает события в очереди событий Windows PowerShell для текущего сеанса.
Чтобы указать события, можно получить все события или использовать параметр *EventIdentifier* или *SourceIdentifier* .

Каждое возникающее событие добавляется в очередь событий.
Очередь событий включает события, на получение которых зарегистрирован пользователь, события, созданные с помощью командлета New-Event, а также события, возникающие при выходе из Windows PowerShell.
Для получения событий можно использовать **Get-Event** или Wait-Event.

Данный командлет не получает события из журналов средства просмотра событий.
Для получения этих событий используются командлеты Get-WinEvent и Get-EventLog.

## Примеры

### Пример 1. получение всех событий

```
PS C:\> Get-Event
```

Эта команда получает все события из очереди событий.

### Пример 2. получение событий по идентификатору источника

```
PS C:\> Get-Event -SourceIdentifier "PowerShell.ProcessCreated"
```

Эта команда возвращает события, в которых значение свойства SourceIdentifier — PowerShell. Процесскреатед.

### Пример 3. Получение события на основе времени его создания

```
PS C:\> $Events = Get-Event
PS C:\> $Events[0] | Format-List -Property *
ComputerName     :
RunspaceId       : c2153740-256d-46c0-a57c-b805917d1b7b
EventIdentifier  : 1
Sender           : System.Management.ManagementEventWatcher
SourceEventArgs  : System.Management.EventArrivedEventArgs
SourceArgs       : {System.Management.ManagementEventWatcher, System.Management.EventArrivedEventArgs}
SourceIdentifier : ProcessStarted
TimeGenerated    : 11/13/2008 12:09:32 PM
MessageData      : PS C:\> Get-Event | Where {$_.TimeGenerated -ge "11/13/2008 12:15:00 PM"}
ComputerName     :
RunspaceId       : c2153740-256d-46c0-a57c-b8059325d1a0
EventIdentifier  : 1
Sender           : System.Management.ManagementEventWatcher
SourceEventArgs  : System.Management.EventArrivedEventArgs
SourceArgs       : {System.Management.ManagementEventWatcher, System.Management.EventArrivedEventArgs}
SourceIdentifier : ProcessStarted
TimeGenerated    : 11/13/2008 12:15:00 PM
MessageData      :
```

В этом примере показано, как получать события с помощью свойств, отличных от SourceIdentifier.

Первая команда получает все события в очереди событий и сохраняет их в переменной $Events.

Вторая команда использует нотацию массива для получения первого события (0-index) в массиве в переменной $Events.
С помощью конвейерного оператора (|) команда отправляет событие в команду Format-List, которая отображает все свойства события в списке.
Это позволяет проверить свойства объекта события.

Третья команда показывает, как использовать командлет Where-Object для получения события в зависимости от времени его создания.

### Пример 4. Получение события по его идентификатору

```
PS C:\> Get-Event -EventIdentifier 2
```

Эта команда получает событие с идентификатором 2.

## PARAMETERS

### -EventIdentifier
Указывает идентификаторы событий, для которых этот командлет получает события.

```yaml
Type: System.Int32
Parameter Sets: ById
Aliases: Id

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceIdentifier
Указывает идентификаторы источников, для которых этот командлет получает события.
По умолчанию командлет получает все события в очереди.
Использовать подстановочные знаки запрещено.

```yaml
Type: System.String
Parameter Sets: BySource
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет
В этот командлет нельзя передать входные данные.

## Выходные данные

### System. Management. Automation. PSEventArgs
**Get-Event** возвращает объект **PSEventArgs** для каждого события.
Чтобы просмотреть описание этого объекта, введите `Get-Help Get-Event -Full` и просмотрите раздел "Примечания" в разделе справки.

## ПРИМЕЧАНИЯ

* События, подписки на события и очередь событий существуют только в текущем сеансе. Если закрыть текущий сеанс, очередь событий удаляется, а подписка на событие отменяется.

  Командлет **Get-Event** возвращает объект **PSEventArgs** ( **System. Management. Automation. PSEventArgs** ) со следующими свойствами:

  - ComputerName.
имя компьютера, на котором произошло событие.
Значение этого свойства заполняется только в том случае, если событие передается с удаленного компьютера.

  - Рунспацеид.
GUID, однозначно идентифицирующий сеанс, в ходе которого произошло событие.
Значение этого свойства заполняется только в том случае, если событие передается с удаленного компьютера.

  - EventIdentifier.
целое число (Int32), однозначно идентифицирующее уведомление о событии в текущем сеансе.

  - Отправителя.
объект, создавший событие.
В значении параметра *Action* $sender автоматическая переменная содержит объект sender.

  - Саурцеевентаргс.
первый параметр, который наследуется от EventArgs (если существует).
Например, в событии с истекшим таймером, в котором сигнатура имеет форму отправитель объекта, Timers. ElapsedEventArgs e, свойство Саурцеевентаргс будет содержать таймеры. ElapsedEventArgs.
В значении параметра *Action* $EventArgs автоматическая переменная содержит это значение.

  - Саурцеаргс.
все параметры сигнатуры исходного события.
Для стандартной сигнатуры события $Args \[ 0 \] соответствует отправителю, а $args \[ 1 \] — саурцеевентаргс.
В значении параметра *Action* $args автоматическая переменная содержит это значение.

  - SourceIdentifier.
cтрока, идентифицирующая подписку на событие.
В значении параметра *Action* свойство SourceIdentifier автоматической переменной $Event содержит это значение.

  - TimeGenerated.
Объект **DateTime** , представляющий время создания события.
В значении параметра *Action* свойство timegenerated автоматической переменной $Event содержит это значение.

  --MessageData.
данные, связанные с подпиской на событие.
Пользователи указывают эти данные при регистрации события.
В значении параметра *Action* свойство MessageData автоматической переменной $Event содержит это значение.

*

## Связанные ссылки

[New-Event](New-Event.md)

[Register-EngineEvent](Register-EngineEvent.md)

[Register-ObjectEvent](Register-ObjectEvent.md)

[Remove-Event](Remove-Event.md)

[Unregister-Event](Unregister-Event.md)

[Wait-Event](Wait-Event.md)
