---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 02/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/register-engineevent?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-EngineEvent
ms.openlocfilehash: 64d927907f995613d3e2260e5476b406949bc1aa
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599405"
---
# Register-EngineEvent

## Краткий обзор
Подписывается на события, созданные подсистемой PowerShell и `New-Event` командлетом.

## SYNTAX

```
Register-EngineEvent [-SourceIdentifier] <String> [[-Action] <ScriptBlock>] [-MessageData <PSObject>]
 [-SupportEvent] [-Forward] [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

## DESCRIPTION

`Register-EngineEvent`Командлет подписывается на события, созданные подсистемой PowerShell и `New-Event` командлетом. Для задания события используйте параметр **SourceIdentifier**.

С помощью этого командлета можно подписываться на события обработчика **выхода** и события, создаваемые `New-Event` командлетом. Эти события автоматически добавляются в очередь событий сеанса без оформления подписки. Однако создание подписки позволяет перенаправлять события, задавать действия для реагирования на них, а также отменять подписку.

При возникновении события, для которого создана подписка, это событие добавляется в очередь событий сеанса. Чтобы получить события в очереди событий, используйте `Get-Event` командлет.

При оформлении подписки на событие в сеанс добавляется подписчик событий. Чтобы получить подписчиков событий в сеансе, используйте `Get-EventSubscriber` командлет. Чтобы отменить подписку, используйте `Unregister-Event` командлет, который удаляет подписчика событий из сеанса.

## Примеры

### Пример 1. регистрация события обработчика PowerShell на удаленных компьютерах

В этом примере регистрируется событие обработчика PowerShell на двух удаленных компьютерах.

```powershell
$S = New-PSSession -ComputerName "Server01, Server02"
Invoke-Command -Session $S {
Register-EngineEvent -SourceIdentifier ([System.Management.Automation.PsEngineEvent]::Exiting) -Forward
}
```

`New-PSSession` создает управляемый пользователем сеанс (PSSession) на каждом из удаленных компьютеров. `Invoke-Command` Командлет выполняет `Register-EngineEvent` команду в удаленных сеансах.
`Register-EngineEvent` использует параметр **SourceIdentifier** для обнаружения события. Параметр **Forward** сообщает обработчику о необходимости пересылки событий из удаленного сеанса в локальный сеанс.

### Пример 2. выполнение указанного действия при возникновении события Exit

В этом примере показано, как запустить, `Register-EngineEvent` чтобы выполнить определенное действие при возникновении события **PowerShell. Exit** .

```powershell
Register-EngineEvent -SourceIdentifier PowerShell.Exiting -SupportEvent -Action {
    Get-History | Export-Clixml $Home\history.clixml
}
```

Для скрытия подписки на события добавляется параметр **SupportEvent** . Когда PowerShell завершает работу, в этом случае в журнал команд из сеанса выхода экспортируется XML-файл в `$Home` каталоге пользователя.

### Пример 3. Создание и подписка на определяемое пользователем событие

В этом примере создается подписка на события из источника **мевентсаурце**. Это произвольный источник, который мы будем использовать для отслеживания хода выполнения задания. `Register-EngineEvent` используется для создания подписки. Блок скрипта для параметра **Action** записывает данные события в текстовый файл.

```powershell
Register-EngineEvent -SourceIdentifier MyEventSource -Action {
    "Event: {0}" -f $event.messagedata | Out-File c:\temp\MyEvents.txt -Append
}

Start-Job -Name TestJob -ScriptBlock {
    While ($True) {
        Register-EngineEvent -SourceIdentifier MyEventSource -Forward
        Start-Sleep -seconds 2
        "Doing some work..."
        New-Event -SourceIdentifier MyEventSource -Message ("{0} -  Work done..." -f (Get-Date))
    }
}
Start-Sleep -seconds 4
Get-EventSubscriber
Get-Job
```

```Output
SubscriptionId   : 12
SourceObject     :
EventName        :
SourceIdentifier : MyEventSource
Action           : System.Management.Automation.PSEventJob
HandlerDelegate  :
SupportEvent     : False
ForwardEvent     : False

Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
18     MyEventSource                   Running       True                                 …
19     TestJob         BackgroundJob   Running       True            localhost            …
```

`Register-EngineEvent` создан ИД задания 18. `Start-Job` создан код задания 19. В примере #4 удаляется подписка на события и задания, а затем проверяется файл журнала.

### Пример 4. Отмена регистрации событий и очистка заданий

Это продолжение примера 3. В этом примере мы дожидаться 10 секунд, чтобы разрешить несколько событий. Затем отменяется регистрация подписки на события.

```powershell
PS> Start-Sleep -seconds 10
PS> Get-EventSubscriber | Unregister-Event
PS> Get-Job

Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
18     MyEventSource                   Stopped       False                                …
19     TestJob         BackgroundJob   Running       True            localhost            …

PS> Stop-Job -Id 19
PS> Get-Job | Remove-Job
PS> Get-Content C:\temp\MyEvents.txt
Event: 2/18/2020 2:36:19 PM -  Work done...
Event: 2/18/2020 2:36:21 PM -  Work done...
Event: 2/18/2020 2:36:23 PM -  Work done...
Event: 2/18/2020 2:36:25 PM -  Work done...
Event: 2/18/2020 2:36:27 PM -  Work done...
Event: 2/18/2020 2:36:29 PM -  Work done...
Event: 2/18/2020 2:36:31 PM -  Work done...
```

`Unregister-Event`Командлет останавливает задание, связанное с подпиской на событие (ИД задания 18). Задание с идентификатором 19 все еще выполняется и создает новые события. Мы используем командлеты **задания** , чтобы отменить задание и удалить ненужные объекты задания. `Get-Content` Отображает содержимое файла журнала.

## PARAMETERS

### -Action

Указывает команды для обработки событий. При возникновении события команды в разделе **Action** не отправляют его в очередь. а выполняют. Чтобы создать блок скрипта, заключите команды в скобки ( { } ).

Значение параметра **Action** может включать `$Event` переменные,, `$EventSubscriber` `$Sender` , `$EventArgs` и `$Args` автоматически, которые предоставляют сведения о событии в блок сценария **действия** . Дополнительные сведения см. в разделе [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).

При указании действия `Register-EngineEvent` возвращает объект задания события, представляющий это действие. Командлеты группы Job позволяют управлять заданием событий.

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

### -Forward

Указывает, что командлет отправляет события для этой подписки в сеанс на локальном компьютере.
Этот параметр используется при регистрации событий, полученных на удаленном компьютере или в удаленном сеансе.

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

### -MaxTriggerCount

Указывает максимальное количество выполнений действия для подписки на события.

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

Указывает дополнительные данные, связанные с событием. Значение этого параметра отображается в свойстве **MessageData** объекта события.

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

Указывает идентификатор источника события, для которого создается подписка. Идентификатор источника должен быть уникальным в пределах текущего сеанса Это обязательный параметр.

Значение этого параметра отображается в значении свойства **SourceIdentifier** объекта подписчика, а также всех объектов событий, связанных с этой подпиской.

Значение зависит от источника события. Это может быть произвольное значение, которое вы создали для использования с `New-Event` командлетом. Обработчик PowerShell поддерживает значения **EngineEvent** **PowerShell. Exit** и **PowerShell. OnIdle**.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 100
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SupportEvent

Указывает, что командлет скрывает подписку на события. Добавьте этот параметр, если текущая подписка является частью более сложного механизма регистрации событий и не должна обнаруживаться отдельно.

Чтобы просмотреть или отменить подписку, созданную с помощью параметра **SupportEvent** , добавьте параметр **Force** в `Get-EventSubscriber` `Unregister-Event` командлеты или.

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

### None

Вы не можете передать входные данные в `Register-EngineEvent` .

## Выходные данные

### None или System. Management. Automation. PSEventJob

При использовании параметра **Action** `Register-EngineEvent` возвращает объект **System. Management. Automation. PSEventJob** . В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

На платформах Linux и macOS нет доступных источников событий.

События, подписки на события и очередь событий существуют только в текущем сеансе. Если закрыть текущий сеанс, очередь событий удаляется, а подписка на событие отменяется.

## Связанные ссылки

[Get-Event](Get-Event.md)

[New-Event](New-Event.md)

[Register-ObjectEvent](Register-ObjectEvent.md)

[Remove-Event](Remove-Event.md)

[Unregister-Event](Unregister-Event.md)

[Wait-Event](Wait-Event.md)
