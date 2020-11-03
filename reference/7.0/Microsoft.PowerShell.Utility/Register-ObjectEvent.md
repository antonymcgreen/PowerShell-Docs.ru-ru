---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/register-objectevent?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-ObjectEvent
ms.openlocfilehash: a6ed76164dbc2773393211ad8474becb499986a3
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225814"
---
# Register-ObjectEvent

## Краткий обзор
Подписывается на события, создаваемые объектом Microsoft .NET Framework.

## SYNTAX

```
Register-ObjectEvent [-InputObject] <PSObject> [-EventName] <String> [[-SourceIdentifier] <String>]
 [[-Action] <ScriptBlock>] [-MessageData <PSObject>] [-SupportEvent] [-Forward] [-MaxTriggerCount <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION

`Register-ObjectEvent`Командлет подписывается на события, созданные объектами .NET на локальном компьютере или на удаленном компьютере.

При возникновении события, для которого создана подписка, это событие добавляется в очередь событий сеанса. Чтобы получить события в очереди событий, используйте `Get-Event` командлет.

С помощью параметров функции можно `Register-ObjectEvent` указать значения свойств событий, которые могут помочь определить событие в очереди. Можно также использовать параметр **Action** , чтобы указать действия, выполняемые при возникновении подписанного события, и параметр **Forward** для отправки удаленных событий в очередь событий в локальном сеансе.

При подписке на событие к текущему сеансу добавляется подписчик события. Чтобы получить подписчиков событий в сеансе, используйте `Get-EventSubscriber` командлет. Чтобы отменить подписку, используйте `Unregister-Event` командлет, который удаляет подписчика событий из сеанса.

## Примеры

### Пример 1. Подписка на события при запуске нового процесса

В этом примере показано, как подписаться на события, созданные при запуске нового процесса.

Команда использует объект **ManagementEventWatcher** для получения событий **EventArrived** . Объект запроса указывает, что события являются событиями создания экземпляра для класса **Win32_Process** .

```powershell
$queryParameters = '__InstanceCreationEvent', (New-Object TimeSpan 0,0,1),
    "TargetInstance isa 'Win32_Process'"
$Query = New-Object System.Management.WqlEventQuery -ArgumentList $queryParameters
$ProcessWatcher = New-Object System.Management.ManagementEventWatcher $Query
Register-ObjectEvent -InputObject $ProcessWatcher -EventName "EventArrived"
```

### Пример 2. Указание действия для реагирования на событие

При указании действия возникающие события не добавляются в очередь событий. Вместо этого на событие реагирует действие. В этом примере при возникновении события создания экземпляра, указывающего на запуск нового процесса, возникает новое событие **процесскреатед** .

```powershell
$queryParameters = '__InstanceCreationEvent', (New-Object TimeSpan 0,0,1),
    "TargetInstance isa 'Win32_Process'"
$Query = New-Object System.Management.WqlEventQuery -ArgumentList $queryParameters
$ProcessWatcher = New-Object System.Management.ManagementEventWatcher $query
$newEventArgs = @{
    SourceIdentifier = 'PowerShell.ProcessCreated'
    Sender = $Sender
    EventArguments = $EventArgs.NewEvent.TargetInstance
}
$Action = { New-Event @newEventArgs }
Register-ObjectEvent -InputObject $ProcessWatcher -EventName "EventArrived" -Action $Action
```

```Output
Id   Name               PSJobTypeName   State       HasMoreData   Location   Command
--   ----               -------------   -----       -----------   --------   -------
 5   3db2d67a-efff-...                 NotStarted   False                    New-Event @newEventArgs
```

Действие использует `$Sender` и `$EventArgs` Автоматические переменные, заполняемые только для действий события.

`Register-ObjectEvent`Команда возвращает объект задания, представляющий действие, которое выполняется как фоновое задание. `Get-Job` `Receive-Job` Для управления фоновыми заданиями можно использовать командлеты задания, такие как и. См. дополнительные сведения о [заданиях](../Microsoft.PowerShell.Core/About/about_Jobs.md).

### Пример 3. Подписка на события объекта на удаленных компьютерах

В этом примере показано, как подписаться на события объектов на удаленных компьютерах. В этом примере используется `Enable-ProcessCreationEvent` функция, определенная в `ProcessCreationEvent.ps1` файле скрипта. Этот сценарий доступен для всех компьютеров в этом примере.

```powershell
# ProcessCreationEvent.ps1
function  Enable-ProcessCreationEvent {
    $queryParameters = "__InstanceCreationEvent", (New-Object TimeSpan 0,0,1),
        "TargetInstance isa 'Win32_Process'"
    $Query = New-Object System.Management.WqlEventQuery -ArgumentList $queryParameters

    $objectEventArgs = @{
        Input = New-Object System.Management.ManagementEventWatcher $Query
        EventName = 'EventArrived'
        SourceIdentifier = 'WMI.ProcessCreated'
        MessageData = 'Test'
        Forward = $True
    }
    Register-ObjectEvent @objectEventArgs
}

$S = New-PSSession -ComputerName "Server01, Server02"
Invoke-Command -Session $S -FilePath ProcessCreationEvent.ps1
Invoke-Command -Session $S { Enable-ProcessCreationEvent }
```

Сначала мы создадим **PSSession** на двух удаленных компьютерах и сохраняем их в `$S` переменной. Затем `Invoke-Command` командлет запускает `ProcessCreationEvent.ps1` сценарий в каждом из PSSession в `$S` . Это действие создает `Enable-ProcessCreationEvent` функцию в удаленных сеансах.
Наконец, мы выполняем `Enable-ProcessCreationEvent` функцию в удаленных сеансах.

 Функция включает `Register-ObjectEvent` команду, которая подписывается на события создания экземпляра объекта **Win32_Process** через объект **ManagementEventWatcher** и его событие **EventArrived** .

### Пример 4. Использование динамического модуля в объекте PSEventJob

В этом примере показано, как использовать динамический модуль в объекте **PSEventJob** , который создается при включении **действия** в регистрацию событий. Сначала мы креатеанд и включили объект Timer, а затем установите интервал таймера равным 500 (МС). `Register-ObjectEvent`Командлет регистрирует событие **Elapsed** объекта Timer. Объект **PSEventJob** сохраняется в `$Job` переменной и также доступен в свойстве **Action** подписчика на событие. Дополнительные сведения см. в разделе [Get-EventSubscriber](Get-EventSubscriber.md).

По истечении интервала таймера возникает событие, и выполняется действие. В этом случае `Get-Random` командлет создает случайное число от 0 до 100 и сохраняет его в `$Random` переменной.

```powershell
$Timer = New-Object Timers.Timer
$Timer.Interval = 500
$Timer.Enabled = $True
$objectEventArgs = @{
    InputObject = $Timer
    EventName = 'Elapsed'
    SourceIdentifier = 'Timer.Random'
    Action = {$Random = Get-Random -Min 0 -Max 100}
}
$Job = Register-ObjectEvent @objectEventArgs
$Job | Format-List -Property *
& $Job.module {$Random}
& $Job.module {$Random}
```

```Output
State         : Running
Module        : __DynamicModule_53113769-31f2-42dc-830b-8749325e28d6
StatusMessage :
HasMoreData   : True
Location      :
Command       : $Random = Get-Random -Min 0 -Max 100
JobStateInfo  : Running
Finished      : System.Threading.ManualResetEvent
InstanceId    : 47b5ec9f-bfe3-4605-860a-4674e5d44ca8
Id            : 7
Name          : Timer.Random
ChildJobs     : {}
PSBeginTime   : 6/27/2019 10:19:06 AM
PSEndTime     :
PSJobTypeName :
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
Information   : {}
60
47
```

**PSEventJob** имеет свойство **module** , которое содержит динамический модуль скрипта, реализующий действие. С помощью оператора Call ( `&` ) мы вызываем команду в модуле, чтобы отобразить значение `$Random` переменной.

Дополнительные сведения о модулях см. в разделе [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).

## PARAMETERS

### -Action

Указывает команды для обработки события. При возникновении события команды в разделе **Action** не отправляют его в очередь. а выполняют. Чтобы создать блок скрипта, заключите команды в скобки ( { } ).

Значение параметра **Action** может включать `$Event` переменные,, `$EventSubscriber` `$Sender` , `$EventArgs` и `$Args` автоматические. Эти переменные предоставляют сведения о событии в блок сценария **действия** . Дополнительные сведения см. в разделе [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).

При указании действия `Register-ObjectEvent` возвращает объект задания события, представляющий это действие. Командлеты группы Job позволяют управлять заданием событий.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: 101
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EventName

Указывает событие, на которое вы подписываетесь.

Значение этого параметра должно быть именем события, которое предоставляет объект .NET. Например, класс **ManagementEventWatcher** содержит события с именами **EventArrived** и **Stopped** . Чтобы найти имя события, используйте `Get-Member` командлет.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Forward

Указывает, что командлет отправляет события для этой подписки в удаленный сеанс. Этот параметр используется при регистрации событий, полученных на удаленном компьютере или в удаленном сеансе.

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

### -InputObject

Указывает объект .NET, который создает события. Введите переменную, содержащую объект, или наберите команду или выражение, которые получают объект.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxTriggerCount

Указывает максимальное число запусков события.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MessageData

Указывает дополнительные данные, которые будут связаны с подпиской на событие. Значение этого параметра отображается в свойстве MessageData всех событий, связанных с этой подпиской.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceIdentifier

Указывает имя, выбранное для подписки. Выбранное имя должно быть уникальным в текущем сеансе. Значение по умолчанию — это идентификатор GUID, который назначается PowerShell.

Значение этого параметра отображается в значении свойства **SourceIdentifier** объекта подписчика и всех объектов событий, связанных с этой подпиской.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 100
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SupportEvent

Указывает, что командлет скрывает подписку на события. Используйте этот параметр, если текущая подписка является частью более сложного механизма регистрации событий и не должна обнаруживаться отдельно.

Чтобы просмотреть или отменить подписку, созданную с помощью параметра **SupportEvent** , используйте параметр **Force** `Get-EventSubscriber` `Unregister-Event` командлетов и.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

Вы не можете передать объекты в `Register-ObjectEvent` .

## Выходные данные

### None или System. Management. Automation. PSEventJob

При использовании параметра **Action** `Register-ObjectEvent` возвращает объект **System. Management. Automation. PSEventJob** . В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

События, подписки на события и очередь событий существуют только в текущем сеансе. Если закрыть текущий сеанс, очередь событий удаляется, а подписка на событие отменяется.

## Связанные ссылки

[Get-Event](Get-Event.md)

[New-Event](New-Event.md)

[Register-EngineEvent](Register-EngineEvent.md)

[Remove-Event](Remove-Event.md)

[Unregister-Event](Unregister-Event.md)

[Wait-Event](Wait-Event.md)
