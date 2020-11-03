---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 07/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/register-wmievent?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-WmiEvent
ms.openlocfilehash: be29ce6376dea7686c0c063cc5528fbc7d840a9d
ms.sourcegitcommit: 41b072f0b6046d619b0e7f758982783fb648a3d5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/31/2020
ms.locfileid: "93230189"
---
# Register-WmiEvent

## Краткий обзор
Подписывается на событие WMI.

## SYNTAX

### Класс (по умолчанию)

```
Register-WmiEvent [-Namespace <String>] [-Credential <PSCredential>] [-ComputerName <String>] [-Class] <String>
 [-Timeout <Int64>] [[-SourceIdentifier] <String>] [[-Action] <ScriptBlock>] [-MessageData <PSObject>]
 [-SupportEvent] [-Forward] [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

### query

```
Register-WmiEvent [-Namespace <String>] [-Credential <PSCredential>] [-ComputerName <String>] [-Query] <String>
 [-Timeout <Int64>] [[-SourceIdentifier] <String>] [[-Action] <ScriptBlock>] [-MessageData <PSObject>]
 [-SupportEvent] [-Forward] [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

## DESCRIPTION

`Register-WmiEvent`Командлет подписывается на события инструментарий управления Windows (WMI) (WMI) на локальном компьютере или на удаленном компьютере.

При возникновении соответствующего события WMI оно добавляется в очередь событий в локальном сеансе, даже если событие инициировано на удаленном компьютере. Чтобы получить события в очереди событий, используйте `Get-Event` командлет.

Параметры функции можно использовать `Register-WmiEvent` для подписки на события на удаленных компьютерах, а также для указания значений свойств событий, которые могут помочь определить событие в очереди. Можно также использовать параметр **Action** , чтобы указать действия, выполняемые при возникновении подписанного события.

При подписке на событие к текущему сеансу добавляется подписчик события. Чтобы получить подписчиков событий в сеансе, используйте `Get-EventSubscriber` командлет. Чтобы отменить подписку, используйте `Unregister-Event` командлет, который удаляет подписчика событий из сеанса.

В Windows PowerShell 3.0 появились новые командлеты модели CIM, выполняющие те же задачи, что и командлеты инструментария WMI. Командлеты модели CIM соответствуют стандартам WS-Management (WSMan) и CIM, что позволяет им использовать те же способы управления компьютерами под управлением Windows и других операционных систем. Вместо использования `Register-WmiEvent` , рассмотрите возможность использования командлета [Register-Циминдикатионевент](../cimcmdlets/register-cimindicationevent.md) .

## Примеры

### Пример 1. Подписка на события, создаваемые с помощью класса

Эта команда подписывается на события, создаваемые классом **Win32_ProcessStartTrace** . Этот класс вызывает событие при запуске процесса.

```powershell
Register-WmiEvent -Class 'Win32_ProcessStartTrace' -SourceIdentifier "ProcessStarted"
```

### Пример 2. Подписка на события создания процесса

Эта команда использует запрос для подписки на события создания экземпляра Win32_process.

```powershell
$wmiParameters = @{
  Query = "select * from __instancecreationevent within 5 where targetinstance isa 'win32_process'"
  SourceIdentifier = "WMIProcess"
  MessageData = "Test 01"
  TimeOut = 500
}
Register-WmiEvent @wmiParameters
```

### Пример 3. Использование действия в ответ на событие

В этом примере показано, как использовать действие в ответ на событие. В этом случае при запуске процесса все `Start-Process` команды в текущем сеансе записываются в XML-файл.

```powershell
$action = { Get-History | where { $_.commandline -like "*start-process*" } | export-cliXml "commandHistory.clixml" }
Register-WmiEvent -Class 'Win32_ProcessStartTrace' -SourceIdentifier "ProcessStarted" -Action $action
```

```Output
Id    Name            State      HasMoreData   Location  Command
--    ----            -----      -----------   --------  -------
1     ProcessStarted  NotStarted False                   get-history | where {...
```

При использовании параметра **Action** `Register-WmiEvent` возвращает фоновое задание, представляющее действие события. **Job** `Get-Job` `Receive-Job` Для управления заданием события можно использовать командлеты задания, такие как и.

Дополнительные сведения см. в разделе about_Jobs.

### Пример 4. Регистрация для событий на удаленном компьютере

Этот пример регистрируется для событий на удаленном компьютере Server01.

```powershell
Register-WmiEvent -Class 'Win32_ProcessStartTrace' -SourceIdentifier "Start" -Computername Server01
Get-Event -SourceIdentifier "Start"
```

WMI возвращает события на локальный компьютер и сохраняет их в очередь событий в текущем сеансе. Чтобы получить события, выполните локальную `Get-Event` команду.

## PARAMETERS

### -Action

Задает команды, которые обрабатывают события. Команды в параметре **Action** выполняются при возникновении события вместо отправки события в очередь событий. Заключите команды в фигурные скобки ( `{}` ), чтобы создать блок скрипта.

Значение **Action** может включать `$Event` переменные,, `$EventSubscriber` `$Sender` , `$EventArgs` и `$Args` автоматически, которые предоставляют сведения о событии блоку сценария **действия** . Дополнительные сведения см. в разделе about_Automatic_Variables.

При указании действия `Register-WmiEvent` возвращает объект задания события, представляющий это действие. Для управления заданием события можно использовать командлеты, содержащие существительное **задания** (командлеты **задания** ).

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

### -Class

Указывает событие, на которое вы подписываетесь. Введите класс WMI, который создает событие. В каждой команде требуется указать **класс** или параметр **запроса** .

```yaml
Type: System.String
Parameter Sets: class
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Задает имя компьютера, на котором выполняется команда. По умолчанию это локальный компьютер.

Введите имя NetBIOS, IP-адрес или полное доменное имя компьютера. Чтобы указать локальный компьютер, введите имя компьютера, точку ( `.` ) или localhost.

Этот параметр не зависит от удаленного взаимодействия Windows PowerShell. Параметр **ComputerName** можно использовать, даже если компьютер не настроен для выполнения удаленных команд.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Указывает учетную запись пользователя с разрешением на выполнение этого действия. По умолчанию используется текущий пользователь.

Введите имя пользователя, например User01 или Domain01\User01, либо введите объект **PSCredential** , например, созданный `Get-Credential` командлетом. При вводе имени пользователя этот командлет запрашивает пароль.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Forward

Указывает, что этот командлет отправляет события по данной подписке в сеанс на локальном компьютере.
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

Указывает максимальное число триггеров.

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

Указывает дополнительные данные, которые будут связаны с подпиской на событие. Значение этого параметра отображается в свойстве **MessageData** всех событий, связанных с этой подпиской.

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

### -Namespace

Задает пространство имен класса WMI.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Query

Указывает запрос на языке запросов WMI, определяющий класс событий инструментария WMI, например `select * from __InstanceDeletionEvent`.

```yaml
Type: System.String
Parameter Sets: query
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceIdentifier

Указывает имя, выбранное для подписки. Выбранное имя должно быть уникальным в текущем сеансе. Значение по умолчанию — идентификатор GUID, который назначает Windows PowerShell.

Значение этого параметра отображается в значении свойства **SourceIdentifier** объекта подписчика, а также всех объектов событий, связанных с этой подпиской.

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

Указывает, что этот командлет скрывает подписку на событие. Этот параметр используется, если текущая подписка является частью более сложного механизма регистрации событий и не должна обнаруживаться независимым образом.

Чтобы просмотреть или отменить подписку, созданную с помощью параметра **SupportEvent** , укажите параметр **Force** `Get-EventSubscriber` `Unregister-Event` командлетов и.

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

### -Timeout

Указывает время ожидания выполнения команды в Windows PowerShell.

Значение по умолчанию — 0 (ноль) означает, что времени ожидания нет, из-за чего Windows PowerShell ожидает команды бессрочно.

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases: TimeoutMSec

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

Нельзя передать объекты в этот командлет с помощью конвейера.

## Выходные данные

### Нет

Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

Чтобы использовать этот командлет в Windows Vista или более поздней версии ОС Windows, запустите Windows PowerShell, используя параметр "Запуск от имени администратора".

События, подписки на события и очередь событий существуют только в текущем сеансе. Если закрыть текущий сеанс, очередь событий удаляется, а подписка на событие отменяется.

## Связанные ссылки
