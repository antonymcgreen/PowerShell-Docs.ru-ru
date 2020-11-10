---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/suspend-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-Job
ms.openlocfilehash: 9b18782fae77fa0776aa2cfaa39b74a2292099d9
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388473"
---
# Suspend-Job

## Краткий обзор
Временно останавливает задания рабочих процессов.

## SYNTAX

### Сессионидпараметерсет (по умолчанию)

```
Suspend-Job [-Force] [-Wait] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### жобпараметерсет

```
Suspend-Job [-Job] <Job[]> [-Force] [-Wait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### намепараметерсет

```
Suspend-Job [-Force] [-Wait] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### инстанцеидпараметерсет

```
Suspend-Job [-Force] [-Wait] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### филтерпараметерсет

```
Suspend-Job [-Force] [-Wait] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### статепараметерсет

```
Suspend-Job [-Force] [-Wait] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Suspend-Job`Командлет приостанавливает задания рабочего процесса. Приостановка означает временное прерывание или приостановку задания рабочего процесса. Он позволяет пользователям, выполняющим рабочие процессы, приостанавливать их. Он дополняет действие приостановки рабочего процесса https://go.microsoft.com/fwlink/?LinkId=267141 , которое является командой в рабочем процессе, которая приостанавливает рабочий процесс.

`Suspend-Job`Командлет работает только с заданиями рабочего процесса. Он не работает для стандартных фоновых заданий, например для тех, которые запускаются с помощью `Start-Job` командлета.

Определить задание рабочего процесса можно по значению PSWorkflowJob свойства **PSJobTypeName** задания. Чтобы определить, поддерживает ли конкретный тип настраиваемого задания `Suspend-Job` командлет, см. разделы справки для типа настраиваемого задания.

Когда вы приостанавливаете задание рабочего процесса, оно выполняется до следующей контрольной точки, приостанавливается и немедленно возвращает объект задания рабочего процесса. Чтобы дождаться завершения приостановки перед получением задания, используйте параметр **Wait** `Suspend-Job` `Wait-Job` командлета или. При приостановке задания рабочего процесса значение свойства **State** для задания приостанавливается.

Правильность приостановки зависит от контрольных точек. Текущее состояние задания, метаданные и выходные данные сохраняются в контрольной точке, поэтому задание рабочего процесса можно возобновить без потери состояния или данных. Если у задания рабочего процесса нет контрольных точек, его нельзя приостановить правильно. Чтобы добавить контрольные точки в выполняемый рабочий процесс, используйте общий параметр рабочего процесса **PSPersist**. Можно использовать параметр **Force** , чтобы немедленно приостановить любое задание рабочего процесса и приостановить задание рабочего процесса, у которого нет контрольных точек, но это действие может привести к потере состояния и данных.

Перед использованием командлета задания для настраиваемого типа задания, например задания рабочего процесса ( **псворкфловжоб** ), импортируйте модуль, поддерживающий тип настраиваемого задания, с помощью `Import-Module` командлета или с помощью командлета в модуле.

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. Приостановка задания рабочего процесса по имени

В этом примере показано, как приостановить задание рабочего процесса.

Первая команда создает `Get-SystemLog` Рабочий процесс. Рабочий процесс использует `CheckPoint-Workflow` действие для определения контрольной точки в рабочем процессе.

Вторая команда использует параметр **AsJob** , который является общим для всех рабочих процессов для запуска `Get-SystemLog` рабочего процесса в качестве фонового задания. В команде используется общий параметр рабочих процессов **JobName** для указания понятного имени задания рабочего процесса.

Третья команда использует `Get-Job` командлет для получения `Get-SystemLogJob` задания рабочего процесса. В выходных данных показано, что значение свойства **псжобтипенаме** равно псворкфловжоб.

Четвертая команда использует `Suspend-Job` командлет для приостановки `Get-SystemLogJob` задания. Задание выполняется до контрольной точки, а затем приостанавливается.

```
#Sample WorkflowWorkflow Get-SystemLog
{
    $Events = Get-WinEvent -LogName System
    CheckPoint-Workflow
    InlineScript {\\Server01\Scripts\Analyze-SystemEvents.ps1 -Events $Events}
}

PS C:\> Get-SystemLog -AsJob -JobName "Get-SystemLogJob"

PS C:\> Get-Job -Name Get-SystemLogJob
Id     Name              PSJobTypeName   State       HasMoreData     Location   Command
--     ----              -------------   -----       -----------     --------   -------
4      Get-SystemLogJob  PSWorkflowJob   Running     True            localhost   Get-SystemLog

PS C:\> Suspend-Job -Name Get-SystemLogJob
Id     Name              PSJobTypeName   State       HasMoreData     Location   Command
--     ----              -------------   -----       -----------     --------   -------
4      Get-SystemLogJob  PSWorkflowJob   Suspended   True            localhost   Get-SystemLog
```


### Пример 2. Приостановка и возобновление задания рабочего процесса

В этом примере показано, как приостановить, а затем возобновить задание рабочего процесса.

Первая команда приостанавливает задание Логворкфловжоб. Команда возвращает значение немедленно. Выходные данные показывают, что задание рабочего процесса все еще выполняется, даже если оно приостановлено.

Вторая команда использует `Get-Job` командлет для получения задания логворкфловжоб. В выходных данных видно, что задание рабочего процесса успешно приостановлено.

Третья команда использует командлет, `Get-Job` чтобы получить задание логворкфловжоб и `Resume-Job` командлет для его возобновления. В выходных данных видно, что задание рабочего процесса успешно возобновлено и в данный момент выполняется.

```
PS C:\> Suspend-Job -Name LogWorkflowJob
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Running       True            localhost            LogWorkflow

PS C:\> Get-Job -Name LogWorkflowJob
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Suspended     True            localhost            LogWorkflow

PS C:\> Get-Job -Name LogWorkflowJob | Resume-Job
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Running       True            localhost            LogWorkflow
```


### Пример 3. Приостановка задания рабочего процесса на удаленном компьютере

```
PS C:\> Invoke-Command -ComputerName Srv01 -Scriptblock {Suspend-Job -Filter @{CustomID="031589"}
```

Эта команда использует `Invoke-Command` командлет для приостановки задания рабочего процесса на удаленном компьютере SRV01. Значение параметра **фильтра** — это хэш-таблица, которая указывает выбранное значение.
**CustomID**  — это метаданные задания ( **PSPrivateMetadata** ).

### Пример 4. Ожидание приостановки задания рабочего процесса

```
PS C:\> Suspend-Job VersionCheck -Wait
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
 5     VersionCheck  PSWorkflowJob      Suspended     True            localhost            LogWorkflow
```

Эта команда приостанавливает задание рабочего процесса VersionCheck. В ней используется параметр **Wait** для указания того, что необходимо дождаться, когда задание рабочего процесса будет приостановлено. Когда задание рабочего процесса выполняется до следующей контрольной точки и приостанавливается, команда завершается и возвращает объект задания.

### Пример 5. принудительное Приостановка задания рабочего процесса

```
PS C:\> Suspend-Job Maintenance -Force
```

Эта команда принудительно приостанавливает задание рабочего процесса Maintenance. У задания обслуживания нет контрольных точек. Она не может быть приостановлена правильно и может возобновиться неправильно.

## PARAMETERS

### -Filter

Указывает хэш-таблицу условий. Этот командлет приостанавливает задания, которые отвечают всем условиям.
Введите хэш-таблицу, где ключи являются свойствами заданий, а значения — значениями этих свойств.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: FilterParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force

Мгновенно приостанавливает задание рабочего процесса. Это действие может привести к потере состояния и данных.

По умолчанию `Suspend-Job` разрешает выполнение задания рабочего процесса до следующей контрольной точки, а затем приостанавливает ее.
С помощью этого параметра можно также приостанавливать задания рабочих процессов, у которых нет контрольных точек.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: F

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Указывает идентификаторы заданий, приостанавливаемых этим командлетом.

Идентификатор — это целое число, которое однозначно определяет задание в текущем сеансе. Проще запомнить и ввести, чем идентификатор экземпляра, но он уникален только в текущем сеансе. Можно ввести один или несколько идентификаторов, разделенных запятыми. Чтобы найти идентификатор задания, используйте `Get-Job` командлет.

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId

Указывает идентификаторы экземпляров заданий, приостанавливаемых этим командлетом. По умолчанию останавливаются все задания.

Идентификатор экземпляра — это GUID, который однозначно определяет задание на компьютере. Чтобы найти идентификатор экземпляра задания, используйте `Get-Job` .

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Job

Указывает задания рабочего процесса, которые останавливаются этим командлетом. Введите переменную, которая содержит задания рабочих процессов, или команду, которая получает их. Вы также можете передать задания рабочего процесса в `Suspend-Job` командлет.

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name

Указывает понятные имена заданий, приостанавливаемых этим командлетом. Введите одно или несколько имен заданий рабочих процессов.
Поддерживаются подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -State

Указывает состояние задания. Этот командлет останавливает только задания в указанном состоянии. Допустимые значения для этого параметра:

- NotStarted
- Запущен
- Завершено
- Ошибка
- Остановлена
- Блокировано
- Приостановлена
- Отключено
- Приостановка
- Остановка

`Suspend-Job` приостанавливает только задания рабочего процесса в состоянии **выполнения** .

Дополнительные сведения о состояниях заданий см. в разделе [JobState enumeration](/dotnet/api/system.management.automation.jobstate).

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Wait

Указывает, что этот командлет подавляет командную строку, пока задание рабочего процесса не находится в приостановленном состоянии. По умолчанию `Suspend-Job` возвращает значение немедленно, даже если задание рабочего процесса еще не находится в приостановленном состоянии.

Параметр **Wait** эквивалентен конвейеру команды в `Suspend-Job` `Wait-Job` командлет.

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

### System. Management. Automation. job

К этому командлету можно передать все типы заданий. Однако если `Suspend-Job` получает задание неподдерживаемого типа, оно возвращает завершающую ошибку.

## Выходные данные

### System. Management. Automation. job
Этот командлет возвращает приостановленные задания.

## ПРИМЕЧАНИЯ

- Механизм и место сохранения приостановленного задания могут различаться в зависимости от его типа. Например, по умолчанию приостановленные задания рабочих процессов сохраняются в хранилище неструктурированных файлов, но также могут сохраняться в базе данных.
- При отправке задания рабочего процесса, которое не находится в состоянии выполняется, `Suspend-Job` выводится предупреждающее сообщение. Чтобы отключить это предупреждение, используйте общий параметр **WarningAction** со значением SilentlyContinue.

  Если задание не относится к типу, поддерживающему приостановку, функция `Suspend-Job` Возвращает завершающую ошибку.

- Чтобы найти приостановленные задания рабочего процесса, включая те, которые были приостановлены этим командлетом, используйте параметр **State** `Get-Job` командлета для получения заданий рабочего процесса в приостановленном состоянии.
- Задания некоторых типов имеют параметры или свойства, которые не позволяют среде Windows PowerShell приостанавливать их.
  Если попытки приостановить задание завершились ошибкой, убедитесь, что параметры задания и свойства допускают приостановку.

## Связанные ссылки

[Get-Job.](Get-Job.md)

[Receive-Job.](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Resume-Job](Resume-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job.](Stop-Job.md)

[Suspend-Job](Suspend-Job.md)

[Wait-Job](Wait-Job.md)
