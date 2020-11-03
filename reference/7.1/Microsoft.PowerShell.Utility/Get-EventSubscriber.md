---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-eventsubscriber?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-EventSubscriber
ms.openlocfilehash: e1ac039ce49141197c2e14b060118dd4c87f7003
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227210"
---
# Get-EventSubscriber

## Краткий обзор
Получает подписчики на событие в текущем сеансе.

## SYNTAX

### Бисаурце (по умолчанию)

```
Get-EventSubscriber [[-SourceIdentifier] <String>] [-Force] [<CommonParameters>]
```

### Метод byid

```
Get-EventSubscriber [-SubscriptionId] <Int32> [-Force] [<CommonParameters>]
```

## DESCRIPTION

Командлет **Get-EventSubscriber** получает подписчики на события в текущем сеансе.

При оформлении подписки на событие с помощью командлета регистрации событий в сеанс PowerShell добавляется подписчик событий, а события, на которые вы подписаны, добавляются в очередь событий каждый раз, когда они возникают.
Чтобы отменить подписку на событие, необходимо удалить подписчик с помощью командлета Unregister-Event.

## Примеры

### Пример 1. получение подписчика на событие для события таймера

```
PS C:\> $Timer = New-Object Timers.Timer
PS C:\> $Timer | Get-Member -Type Event
PS C:\> Register-ObjectEvent -InputObject $Timer -EventName Elapsed -SourceIdentifier Timer.Elapsed
PS C:\> Get-EventSubscriber
PS C:\> $Timer = New-Object Timers.Timer
PS C:\> $Timer | Get-Member -Type Event
TypeName: System.Timers.Timer
Name     MemberType Definition
----     ---------- ----------
Disposed Event      System.EventHandler Disposed(System.Object, System.EventArgs)
Elapsed  Event      System.Timers.ElapsedEventHandler Elapsed(System.Object, System.Timers.ElapsedEventArgs) PS C:\> Register-ObjectEvent -InputObject $Timer -EventName Elapsed -SourceIdentifier Timer.Elapsed
PS C:\> Get-EventSubscriber
SubscriptionId   : 4
SourceObject     : System.Timers.Timer
EventName        : Elapsed
SourceIdentifier : Timer.Elapsed
Action           :
HandlerDelegate  :
SupportEvent     : False
ForwardEvent     : False
```

В этом примере для получения подписчика на событие таймера используется команда **Get-EventSubscriber** .

Первая команда создает экземпляр объекта таймера с помощью командлета New-Object.
Новый объект Timer сохраняется в переменной $Timer.

Вторая команда отображает события, доступные для объектов таймера, с помощью командлета Get-Member.
Команда использует параметр типа командлета **Get-Member** со значением Event.

Третья команда регистрирует событие Elapsed объекта таймера с помощью командлета Register-ObjectEvent.

Четвертая команда использует командлет **Get-EventSubscriber** , чтобы получить подписчика на событие для события Elapsed.

### Пример 2. Использование динамического модуля в PSEventJob в свойстве Action подписчика событий

```
PS C:\> $Timer = New-Object Timers.Timer
PS C:\> $Timer.Interval = 500
PS C:\> Register-ObjectEvent -InputObject $Timer -EventName Elapsed -SourceIdentifier Timer.Random -Action { $Random = Get-Random -Min 0 -Max 100 }

Id  Name           State      HasMoreData  Location  Command
--  ----           -----      -----------  --------  -------
3   Timer.Random   NotStarted False                  $Random = Get-Random ...

PS C:\> $Timer.Enabled = $True
PS C:\> $Subscriber = Get-EventSubscriber -SourceIdentifier Timer.Random
PS C:\> ($Subscriber.action).gettype().fullname
System.Management.Automation.PSEventJob
PS C:\> $Subscriber.action | Format-List -Property *

State         : Running
Module        : __DynamicModule_6b5cbe82-d634-41d1-ae5e-ad7fe8d57fe0
StatusMessage :
HasMoreData   : True
Location      :
Command       : $random = Get-Random -Min 0 -Max 100
JobStateInfo  : Running
Finished      : System.Threading.ManualResetEvent
InstanceId    : 88944290-133d-4b44-8752-f901bd8012e2
Id            : 1
Name          : Timer.Random
ChildJobs     : {}
...

PS C:\> & $Subscriber.action.module {$Random}
96
PS C:\> & $Subscriber.action.module {$Random}
23
```

В этом примере показано, как использовать динамический модуль в объекте **PSEventJob** в свойстве Action подписчика событий.

Первая команда создает объект таймера с помощью командлета New-Object.
Вторая команда устанавливает интервал времени таймера равным 500 (миллисекундам).

Третья команда регистрирует событие Elapsed объекта таймера с помощью командлета Register-ObjectEvent.
Она содержит действие, обрабатывающее событие.
Когда интервал времени таймера истекает, появляется событие и выполняются команды, содержащиеся в действии.
В этом случае командлет Get-Random создает случайное число от 0 до 100 и сохраняет его в переменной $Random.
Идентификатор источника события — Timer.Random.

При использовании параметра *Action* в команде **Register-ObjectEvent** команда возвращает объект **PSEventJob** , представляющий действие.

Четвертая команда включает таймер.

Пятая команда использует командлет **Get-EventSubscriber** для получения подписчика на событие Timer. Random.
Объект подписчика событий сохраняется в переменной $Subscriber.

Шестая команда показывает, что свойство Action объекта подписчика событий содержит объект **PSEventJob** .
Фактически он содержит тот же объект **PSEventJob** , который возвращает команда **Register-ObjectEvent** .

Седьмая команда использует командлет Format-List для вывода всех свойств объекта **PSEventJob** в свойстве Action в списке.
Результат показывает, что объект **PSEventJob** имеет свойство Module, которое содержит динамический модуль скрипта, реализующий действие.

Остальные команды используют оператор Call (&) для вызова команды в модуле и вывода значения переменной $Random.
Оператор вызова можно использовать для вызова любой команды в модуле, включая команды, которые не экспортируются.
В этом случае команды показывают случайное число, создаваемое при появлении события Elapsed.

Дополнительные сведения о модулях см. в разделе [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).

## PARAMETERS

### -Force

Указывает, что этот командлет получает все подписчики на события, включая подписчики для событий, которые скрыты с помощью параметра *SupportEvent* Register-ObjectEvent, Register-WmiEvent и Register-EngineEvent.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceIdentifier

Указывает значение свойства **SourceIdentifier** , которое получает только подписчики на события.
По умолчанию **Get-EventSubscriber** получает все подписчики на события в сеансе.
Использовать подстановочные знаки запрещено.
Этот параметр чувствителен к регистру.

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

### -SubscriptionId

Указывает идентификатор подписки, который получает этот командлет.
По умолчанию **Get-EventSubscriber** получает все подписчики на события в сеансе.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

В этот командлет нельзя передать входные данные.

## Выходные данные

### System. Management. Automation. Псевентсубскрибер

Командлет **Get-EventSubscriber** возвращает объект, представляющий каждого подписчика на события.

## ПРИМЕЧАНИЯ

* Командлет New-Event, создающий пользовательское событие, не создает подписчик. Поэтому командлет **Get-EventSubscriber** не обнаружит объект подписчика для этих событий. Однако, если вы используете командлет Register-EngineEvent для подписки на пользовательское событие (чтобы перенаправить событие или указать действие), **Get-EventSubscriber** обнаружит подписчика, который вызывает **Register-EngineEvent** .

  События, подписки на события и очередь событий существуют только в текущем сеансе.
Если закрыть текущий сеанс, очередь событий удаляется, а подписка на событие отменяется.

*

## Связанные ссылки

[Get-Event](Get-Event.md)

[New-Event](New-Event.md)

[Register-EngineEvent](Register-EngineEvent.md)

[Register-ObjectEvent](Register-ObjectEvent.md)

[Remove-Event](Remove-Event.md)

[Unregister-Event](Unregister-Event.md)

[Wait-Event](Wait-Event.md)

