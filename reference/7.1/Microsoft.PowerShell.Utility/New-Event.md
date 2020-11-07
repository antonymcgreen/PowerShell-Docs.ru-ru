---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-event?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Event
ms.openlocfilehash: 0e7f263d309908a4a62187d3d1cc5ef08283e0c3
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94344411"
---
# New-Event

## Краткий обзор
Создает новое событие.

## SYNTAX

```
New-Event [-SourceIdentifier] <String> [[-Sender] <PSObject>] [[-EventArguments] <PSObject[]>]
 [[-MessageData] <PSObject>] [<CommonParameters>]
```

## DESCRIPTION

`New-Event`Командлет создает новое пользовательское событие.

Пользовательские события позволяют уведомлять пользователей об изменениях состояния программы, а также о любых других изменениях, которые может обнаружить программа, включая изменения условий работы оборудования или системы, состояния приложений, состояния диска, состояния сети или завершение фонового задания.

Пользовательские события автоматически добавляются в очередь событий в сеансе в момент их возникновения; настраивать подписку на эти события не нужно. Однако если вы хотите перенаправить событие в локальный сеанс или указать действие, отвечающее на событие, используйте `Register-EngineEvent` командлет для подписки на пользовательское событие.

При создании подписки на пользовательское событие в сеанс добавляется подписчик на событие. Если вы отменяете подписку на событие с помощью `Unregister-Event` командлета, подписчик на событие и пользовательское событие удаляются из сеанса. Если вы не подписаны на пользовательское событие, для удаления события необходимо изменить условия программы или закрыть сеанс PowerShell.

## Примеры

### Пример 1. Создание нового события в очереди событий

```
PS C:\> New-Event -SourceIdentifier Timer -Sender windows.timer -MessageData "Test"
```

Эта команда создает новое событие в очереди событий PowerShell. Для отправки события используется объект **Windows. Timer** .

### Пример 2. вызов события в ответ на другое событие

```
PS C:\> function Enable-ProcessCreationEvent
{
   $Query = New-Object System.Management.WqlEventQuery "__InstanceCreationEvent", (New-Object TimeSpan 0,0,1), "TargetInstance isa 'Win32_Process'"
   $ProcessWatcher = New-Object System.Management.ManagementEventWatcher $Query
   $Identifier = "WMI.ProcessCreated"
   Register-ObjectEvent $ProcessWatcher "EventArrived" -SupportEvent $Identifier -Action
   {
      [void] (New-Event -SourceID "PowerShell.ProcessCreated" -Sender $Args[0] -EventArguments $Args[1].SourceEventArgs.NewEvent.TargetInstance)
   }
}
```

Этот пример функции использует `New-Event` командлет для вызова события в ответ на другое событие. Команда использует `Register-ObjectEvent` командлет для подписки на событие инструментарий управления Windows (WMI) (WMI), возникающее при создании нового процесса. Команда использует параметр **Action** командлета для вызова `New-Event` командлета, который создает новое событие.

Так как события, которые `New-Event` вызываются, автоматически добавляются в очередь событий PowerShell, регистрация для этого события не требуется.

## PARAMETERS

### -Евентаргументс

Указывает объект, содержащий параметры события.

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
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
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — Отправитель

Указывает объект, который вызывает событие. По умолчанию используется подсистема PowerShell.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceIdentifier

Задает имя нового события. Этот параметр является обязательным и должен быть уникальным в сеансе.

Значение этого параметра отображается в свойстве **SourceIdentifier** событий.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

В этот командлет нельзя передать входные данные.

## Выходные данные

### System. Management. Automation. PSEventArgs

## ПРИМЕЧАНИЯ

На платформах Linux и macOS нет доступных источников событий.

Новое пользовательское событие, подписка на событие и очередь событий существуют только в текущем сеансе.
Если закрыть текущий сеанс, очередь событий удаляется, а подписка на событие отменяется.

## Связанные ссылки

[Get-Event](Get-Event.md)

[Register-EngineEvent](Register-EngineEvent.md)

[Register-ObjectEvent](Register-ObjectEvent.md)

[Remove-Event](Remove-Event.md)

[Unregister-Event](Unregister-Event.md)

[Wait-Event](Wait-Event.md)
