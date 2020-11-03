---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-event?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Event
ms.openlocfilehash: ce14e6038473e6c53b62b310c288e23f6a7597e2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229361"
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

Командлет **New-Event** создает новое пользовательское событие.

Пользовательские события позволяют уведомлять пользователей об изменениях состояния программы, а также о любых других изменениях, которые может обнаружить программа, включая изменения условий работы оборудования или системы, состояния приложений, состояния диска, состояния сети или завершение фонового задания.

Пользовательские события автоматически добавляются в очередь событий в сеансе в момент их возникновения; настраивать подписку на эти события не нужно.
Однако если требуется перенаправить событие в локальный сеанс или настроить реакцию на событие, необходимо подписаться на соответствующее пользовательское событие с помощью командлета Register-EngineEvent.

При создании подписки на пользовательское событие в сеанс добавляется подписчик на событие.
Если отменить подписку на событие с помощью командлета Unregister-Event, подписчик на событие и само пользовательское событие будут удалены из сеанса.
Если вы не подписаны на пользовательское событие, для удаления события необходимо изменить условия программы или закрыть сеанс PowerShell.

## Примеры

### Пример 1. Создание нового события в очереди событий

```
PS C:\> New-Event -SourceIdentifier Timer -Sender windows.timer -MessageData "Test"
```

Эта команда создает новое событие в очереди событий PowerShell.
Для отправки события используется объект **Windows. Timer** .

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

Этот пример функции использует командлет **New-Event** для вызова события в ответ на другое событие.
С помощью командлета Register-ObjectEvent команда создает подписку на событие инструментария управления Windows (WMI), возникающее при создании нового процесса.
Команда использует параметр *Action* командлета для вызова командлета **New-Event** , который создает новое событие.

Так как события, создаваемые **событием New** , автоматически добавляются в очередь событий PowerShell, регистрация для этого события не требуется.

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

Указывает дополнительные данные, связанные с событием.
Значение этого параметра отображается в свойстве **MessageData** объекта события.

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

Указывает объект, который вызывает событие.
По умолчанию используется подсистема PowerShell.

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

Задает имя нового события.
Этот параметр является обязательным и должен быть уникальным в сеансе.

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

Новое пользовательское событие, подписка на событие и очередь событий существуют только в текущем сеансе. Если закрыть текущий сеанс, очередь событий удаляется, а подписка на событие отменяется.

## Связанные ссылки

[Get-Event](Get-Event.md)

[Register-EngineEvent](Register-EngineEvent.md)

[Register-ObjectEvent](Register-ObjectEvent.md)

[Remove-Event](Remove-Event.md)

[Unregister-Event](Unregister-Event.md)

[Wait-Event](Wait-Event.md)

