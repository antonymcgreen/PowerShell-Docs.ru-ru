---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/suspend-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-Job
ms.openlocfilehash: 6ab50342e963832d89b3dfc4128a22fc16405926
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227026"
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
Командлет **Suspend-Job** приостанавливает задания рабочего процесса.
Приостановка означает временное прерывание или приостановку задания рабочего процесса.
Он позволяет пользователям, выполняющим рабочие процессы, приостанавливать их.
Он дополняет действие приостановки рабочего процесса https://go.microsoft.com/fwlink/?LinkId=267141 , которое является командой в рабочем процессе, которая приостанавливает рабочий процесс.

Командлет **Suspend-Job** применим только к заданиям рабочих процессов.
Он не работает для стандартных фоновых заданий, например для тех, которые запускаются с помощью командлета Start-Job.

Определить задание рабочего процесса можно по значению PSWorkflowJob свойства **PSJobTypeName** задания.
Чтобы определить, поддерживает ли определенное задание настраиваемого типа командлет **Suspend-Job** , см. разделы справки по этому типу.

Когда вы приостанавливаете задание рабочего процесса, оно выполняется до следующей контрольной точки, приостанавливается и немедленно возвращает объект задания рабочего процесса.
Чтобы дождаться завершения приостановки перед получением задания, используйте параметр *Wait* командлета **Suspend-Job** или Wait-Job.
При приостановке задания рабочего процесса значение свойства **State** для задания приостанавливается.

Правильность приостановки зависит от контрольных точек.
Текущее состояние задания, метаданные и выходные данные сохраняются в контрольной точке, поэтому задание рабочего процесса можно возобновить без потери состояния или данных.
Если у задания рабочего процесса нет контрольных точек, его нельзя приостановить правильно.
Чтобы добавить контрольные точки в выполняемый рабочий процесс, используйте общий параметр рабочего процесса *PSPersist*.
Можно использовать параметр *Force* , чтобы немедленно приостановить любое задание рабочего процесса и приостановить задание рабочего процесса, у которого нет контрольных точек, но это действие может привести к потере состояния и данных.

Перед использованием командлета задания для настраиваемого типа задания, например задания рабочего процесса ( **псворкфловжоб** ), импортируйте модуль, поддерживающий тип настраиваемого задания, с помощью командлета Import-Module или с помощью или командлета в модуле.

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. Приостановка задания рабочего процесса по имени

```
The first command creates the Get-SystemLog workflow. The workflow uses the CheckPoint-Workflow activity to define a checkpoint in the workflow.
#Sample WorkflowWorkflow Get-SystemLog
{
    $Events = Get-WinEvent -LogName System
    CheckPoint-Workflow
    InlineScript {\\Server01\Scripts\Analyze-SystemEvents.ps1 -Events $Events}
}

The second command uses the *AsJob* parameter that is common to all workflows to run the Get-SystemLog workflow as a background job. The command uses the *JobName* workflow common parameter to specify a friendly name for the workflow job.
PS C:\> Get-SystemLog -AsJob -JobName "Get-SystemLogJob"

The third command uses the **Get-Job** cmdlet to get the Get-SystemLogJob workflow job. The output shows that the value of the **PSJobTypeName** property is PSWorkflowJob.
PS C:\> Get-Job -Name Get-SystemLogJob
Id     Name              PSJobTypeName   State       HasMoreData     Location   Command
--     ----              -------------   -----       -----------     --------   -------
4      Get-SystemLogJob  PSWorkflowJob   Running     True            localhost   Get-SystemLog

The fourth command uses the **Suspend-Job** cmdlet to suspend the Get-SystemLogJob job. The job runs to the checkpoint and then suspends.
PS C:\> Suspend-Job -Name Get-SystemLogJob
Id     Name              PSJobTypeName   State       HasMoreData     Location   Command
--     ----              -------------   -----       -----------     --------   -------
4      Get-SystemLogJob  PSWorkflowJob   Suspended   True            localhost   Get-SystemLog
```

В этом примере показано, как приостановить задание рабочего процесса.

### Пример 2. Приостановка и возобновление задания рабочего процесса

```
The first command suspends the LogWorkflowJob job.The command returns immediately. The output shows that the workflow job is still running, even though it is being suspended.
PS C:\> Suspend-Job -Name LogWorkflowJob
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Running       True            localhost            LogWorkflow

The second command uses the **Get-Job** cmdlet to get the LogWorkflowJob job. The output shows that the workflow job suspended successfully.
PS C:\> Get-Job -Name LogWorkflowJob
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Suspended     True            localhost            LogWorkflow

The third command uses the **Get-Job** cmdlet to get the LogWorkflowJob job and the Resume-Job cmdlet to resume it. The output shows that the workflow job resumed successfully and is now running.
PS C:\> Get-Job -Name LogWorkflowJob | Resume-Job
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Running       True            localhost            LogWorkflow
```

В этом примере показано, как приостановить, а затем возобновить задание рабочего процесса.

### Пример 3. Приостановка задания рабочего процесса на удаленном компьютере

```
PS C:\> Invoke-Command -ComputerName Srv01 -Scriptblock {Suspend-Job -Filter @{CustomID="031589"}
```

Эта команда использует командлет Invoke-Command для приостановки задания рабочего процесса на удаленном компьютере SRV01.
Значение параметра *фильтра* — это хэш-таблица, которая указывает выбранное значение.
**CustomID**  — это метаданные задания ( **PSPrivateMetadata** ).

### Пример 4. Ожидание приостановки задания рабочего процесса

```
PS C:\> Suspend-Job VersionCheck -Wait
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
 5     VersionCheck  PSWorkflowJob      Suspended     True            localhost            LogWorkflow
```

Эта команда приостанавливает задание рабочего процесса VersionCheck.
В ней используется параметр *Wait* для указания того, что необходимо дождаться, когда задание рабочего процесса будет приостановлено.
Когда задание рабочего процесса выполняется до следующей контрольной точки и приостанавливается, команда завершается и возвращает объект задания.

### Пример 5. принудительное Приостановка задания рабочего процесса

```
PS C:\> Suspend-Job Maintenance -Force
```

Эта команда принудительно приостанавливает задание рабочего процесса Maintenance.
У задания обслуживания нет контрольных точек.
Она не может быть приостановлена правильно и может возобновиться неправильно.

## PARAMETERS

### -Filter
Указывает хэш-таблицу условий.
Этот командлет приостанавливает задания, которые отвечают всем условиям.
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
Мгновенно приостанавливает задание рабочего процесса.
Это действие может привести к потере состояния и данных.

По умолчанию командлет **Suspend-Job** позволяет заданию рабочего процесса выполняться до следующей контрольной точки, после чего приостанавливает его.
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

Идентификатор — это целое число, которое однозначно определяет задание в текущем сеансе.
Проще запомнить и ввести, чем идентификатор экземпляра, но он уникален только в текущем сеансе.
Можно ввести один или несколько идентификаторов, разделенных запятыми.
Чтобы найти идентификатор задания, используйте командлет Get-Job.

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
Указывает идентификаторы экземпляров заданий, приостанавливаемых этим командлетом.
По умолчанию останавливаются все задания.

Идентификатор экземпляра — это GUID, который однозначно определяет задание на компьютере.
Чтобы узнать идентификатор экземпляра задания, используйте командлет **Get-Job**.

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
Указывает задания рабочего процесса, которые останавливаются этим командлетом.
Введите переменную, которая содержит задания рабочих процессов, или команду, которая получает их.
Задания рабочих процессов можно также передавать в командлеты **Suspend-Job** по конвейеру.

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
Указывает понятные имена заданий, приостанавливаемых этим командлетом.
Введите одно или несколько имен заданий рабочих процессов.
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
Указывает состояние задания.
Этот командлет останавливает только задания в указанном состоянии.
Допустимые значения для этого параметра:

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

**Приостановка — задание** приостанавливает только задания рабочего процесса в состоянии **выполняется** .

Дополнительные сведения о состояниях заданий см. в разделе [перечисление JobState](https://msdn.microsoft.com/library/system.management.automation.jobstate) в библиотеке MSDN.

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
Указывает, что этот командлет подавляет командную строку, пока задание рабочего процесса не находится в приостановленном состоянии.
По умолчанию **приостановка-задание** возвращается немедленно, даже если задание рабочего процесса еще не находится в приостановленном состоянии.

Параметр *Wait* эквивалентен конвейеру команды **приостановки задания** к командлету **Wait-Job** .

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

### System. Management. Automation. job
К этому командлету можно передать все типы заданий.
Однако если **приостановить — задание** получает задание неподдерживаемого типа, то оно возвращает завершающую ошибку.

## Выходные данные

### System. Management. Automation. job
Этот командлет возвращает приостановленные задания.

## ПРИМЕЧАНИЯ

* Механизм и место сохранения приостановленного задания могут различаться в зависимости от его типа. Например, по умолчанию приостановленные задания рабочих процессов сохраняются в хранилище неструктурированных файлов, но также могут сохраняться в базе данных.
* При отправке задания рабочего процесса, которое не находится в состоянии выполняется, **приостановка — задание** выводит предупреждающее сообщение. Чтобы отключить это предупреждение, используйте общий параметр *WarningAction* со значением SilentlyContinue.

  Если задание не относится к типу, поддерживающему приостановку, **приостановка-задание** Возвращает завершающую ошибку.

* Чтобы найти приостановленные задания рабочего процесса, включая те, которые были приостановлены этим командлетом, используйте параметр *State* командлета **Get-Job** , чтобы получить задания рабочего процесса в приостановленном состоянии.
* Задания некоторых типов имеют параметры или свойства, которые не позволяют среде Windows PowerShell приостанавливать их. Если попытки приостановить задание завершились ошибкой, убедитесь, что параметры задания и свойства допускают приостановку.

## Связанные ссылки

[Get-Job.](Get-Job.md)

[Receive-Job.](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Resume-Job](Resume-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job.](Stop-Job.md)

[Suspend-Job](Suspend-Job.md)

[Wait-Job](Wait-Job.md)
