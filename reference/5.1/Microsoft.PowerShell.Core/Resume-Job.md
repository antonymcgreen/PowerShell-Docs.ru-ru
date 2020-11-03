---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/resume-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-Job
ms.openlocfilehash: 85cbfad2a4866bf18e69fb99afb8698e233c4c80
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227053"
---
# Resume-Job

## Краткий обзор
Перезапускает приостановленное задание.

## SYNTAX

### Сессионидпараметерсет (по умолчанию)

```
Resume-Job [-Wait] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### жобпараметерсет

```
Resume-Job [-Job] <Job[]> [-Wait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### намепараметерсет

```
Resume-Job [-Wait] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### инстанцеидпараметерсет

```
Resume-Job [-Wait] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### статепараметерсет

```
Resume-Job [-Wait] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### филтерпараметерсет

```
Resume-Job [-Wait] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Resume-Job** возобновляет приостановленное задание рабочего процесса, например с помощью командлета Suspend-Job или действия About_Suspend-Workflow.
При возобновлении задания рабочего процесса обработчик заданий перестраивает состояние, метаданные и выходные данные из сохраненных ресурсов, таких как контрольные точки.
Задание перезапускается без потери состояния или данных.
Состояние задания меняется с **Suspended** на **Running**.

Используйте параметры **возобновления задания** , чтобы выбрать задания по имени, идентификатору, идентификатору экземпляра или передать по каналу объект задания, например, возвращаемый командлетом Get-Job, для **возобновления** работы.
Для выбора задания, которое нужно возобновить, можно также использовать фильтр свойств.

По умолчанию командлет **Resume-Job** возвращает результат немедленно, даже если возобновлены еще не все задания.
Чтобы заблокировать вывод командной строки до тех пор, пока все указанные задания не будут возобновлены, используйте параметр *Wait*.

Командлет **Resume-Job** применим только к заданиям настраиваемых типов, например заданиям рабочих процессов.
Он не работает для стандартных фоновых заданий, например для тех, которые запускаются с помощью командлета Start-Job.
При передаче задания неподдерживаемого типа командлет **Resume-Job** создает неустранимую ошибку и его выполнение останавливается.

Определить задание рабочего процесса можно по значению **PSWorkflowJob** свойства **PSJobTypeName** задания.
Чтобы определить, поддерживает ли конкретный тип настраиваемого задания командлет **Resume-Job** , см. разделы справки для типа настраиваемого задания.

Перед использованием командлета задания для настраиваемого типа задания Импортируйте модуль, поддерживающий тип настраиваемого задания, с помощью командлета Import-Module или путем получения или использования командлета в модуле.

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. возобновление задания по ИДЕНТИФИКАТОРу

```
The first command uses the **Get-Job** cmdlet to get the job. The output shows that the job is a suspended workflow job.
PS C:\> Get-Job EventJob
Id     Name            PSJobTypeName   State         HasMoreData     Location   Command
--     ----            -------------   -----         -----------     --------   -------
4      EventJob        PSWorkflowJob   Suspended     True            Server01   \\Script\Share\Event.ps1

The second command uses the *Id* parameter of the **Resume-Job** cmdlet to resume the job with an *Id* value of 4.
PS C:\> Resume-Job -Id 4
```

Команды в этом примере проверяют, является ли задание приостановленным заданием рабочего процесса, а затем возобновляют его.

### Пример 2. возобновление задания по имени

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest*
```

В этой команде используется параметр *Name* для возобновления нескольких заданий рабочих процессов на локальном компьютере.

### Пример 3. Использование значений настраиваемых свойств

```
PS C:\> Resume-Job -Filter @{CustomID="T091291"} -State Suspended
```

В этой команде с помощью значения настраиваемого свойства определяется задание рабочего процесса, которое нужно возобновить.
В ней используется параметр *Filter* для указания задания рабочего процесса по значению свойства **CustomID**.
В ней также используется параметр *State* для проверки того, приостановлено ли задание рабочего процесса, перед попыткой его возобновления.

### Пример 4. возобновление всех приостановленных заданий на удаленном компьютере

```
PS C:\> Invoke-Command -ComputerName Srv01 -ScriptBlock {Get-Job -State Suspended | Resume-Job}
```

Эта команда возобновляет все приостановленные задания на удаленном компьютере Srv01.

Команда использует командлет Invoke-Command для выполнения команды на компьютере SRV01.
Удаленная команда использует параметр *State* командлета **Get-Job** , чтобы получить все приостановленные задания на компьютере.
С помощью оператора конвейера (|) приостановленные задания передаются в командлет **Resume-Job** , который возобновляет их.

### Пример 5. Ожидание возобновления заданий

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest* -Wait
```

Эта команда использует параметр *Wait* для прямого **возобновления задания** , чтобы оно возвращалось только после возобновления всех указанных заданий.
Параметр *Wait* особенно полезен в сценариях, в которых предполагается, что задания должны быть возобновлены, прежде чем выполнение сценария будет продолжено.

### Пример 6. Возобновление рабочего процесса, который приостанавливает работу

```
This code sample shows the **Suspend-Workflow** activity in a workflow.
#SampleWorkflow
Workflow Test-Suspend
{
    $a = Get-Date
    Suspend-Workflow
    (Get-Date)- $a
}

The following command runs the Test-Suspend workflow on the Server01 computer.When you run the workflow, the workflow runs the Get-Date activity and stores the result in the $a variable. Then it runs the Suspend-Workflow activity. In response, it takes a checkpoint, suspends the workflow, and returns a workflow job object.  Suspend-Workflow returns a workflow job object even if the workflow is not explicitly run as a job.
PS C:\> Test-Suspend -PSComputerName Server01
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
8      Job8            PSWorkflowJob   Suspended     True            Server01             Test-Suspend

The following command resumes the Test-Suspend workflow in Job8. It uses the *Wait* parameter to hold the command prompt until the job is resumed.
PS C:\> Resume-Job -Name "Job8" -Wait
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command

--     ----            -------------   -----         -----------     --------             -------

8      Job8            PSWorkflowJob   Running       True            Server01             Test-Suspend

This command uses the **Receive-Job** cmdlet to get the results of the Test-Suspend workflow. The final command in the workflow returns a **TimeSpan** object that represents the elapsed time between the current date and time and the date and time that was saved in the $a variable before the workflow was suspended.
PS C:\> Receive-Job -Name Job8
        Days              : 0
        Hours             : 0
        Minutes           : 0
        Seconds           : 19
        Milliseconds      : 823
        Ticks             : 198230041
        TotalDays         : 0.000229432917824074
        TotalHours        : 0.00550639002777778
        TotalMinutes      : 0.330383401666667
        TotalSeconds      : 19.8230041
        TotalMilliseconds : 19823.0041
        PSComputerName    : Server01
```

Командлет **Resume-Job** позволяет возобновить задание рабочего процесса, которое было приостановлено с помощью действия **приостановки рабочего процесса** .
Это действие приостанавливает рабочий процесс из самого процесса.
Оно допустимо только в рабочих процессах.

Сведения о действии Suspend-Workflow см. в разделе about_Suspend-Workflow.

## PARAMETERS

### -Filter
Указывает хэш-таблицу условий.
Этот командлет возобновляет задания, которые соответствуют всем условиям в хэш-таблице.
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

### -Id
Указывает массив идентификаторов для заданий, которые возобновляет этот командлет.

Идентификатор — это целое число, которое однозначно определяет задание в текущем сеансе.
Проще запомнить и ввести, чем идентификатор экземпляра, но он уникален только в текущем сеансе.
Можно ввести один или несколько идентификаторов, разделенных запятыми.
Чтобы найти идентификатор задания, выполните команду **Get-Job**.

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
Указывает массив идентификаторов экземпляров заданий, которые возобновляет этот командлет.
По умолчанию останавливаются все задания.

Идентификатор экземпляра — это GUID, который однозначно определяет задание на компьютере.
Чтобы найти идентификатор экземпляра задания, выполните команду **Get-Job**.

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
Указывает задания, которые нужно возобновить.
Введите переменную, содержащую задания, либо команду, которая их возвращают.
Задания можно также передавать в командлет **Resume-Job** по конвейеру.

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
Указывает массив понятных имен заданий, которые возобновляет этот командлет.
Введите одно или несколько имен заданий.
Можно использовать подстановочные знаки.

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
Указывает состояние заданий для возобновления.
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

Этот командлет возобновляет только задания в **приостановленном** состоянии.

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
Указывает, что этот командлет подавляет командную строку до тех пор, пока не будут перезапущены все результаты задания.
По умолчанию этот командлет немедленно возвращает доступные результаты.

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
Если **Resume-Job** получает задание неподдерживаемого типа, то оно возвращает завершающую ошибку.

## Выходные данные

### Нет, System. Management. Automation. job
Этот командлет возвращает задания, которые он пытается возобновить, если используется параметр *PassThru* .
В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

* **Resume — задание** может возобновлять только приостановленные задания. При передаче задания, имеющего другое состояние, командлет **Resume-Job** выполняет операцию возобновления задания, но выводит предупреждение о том, что задание не удалось возобновить. Чтобы отключить это предупреждение, используйте общий параметр *WarningAction* со значением SilentlyContinue.
* Если задание не относится к типу, который поддерживает возобновление, например задание рабочего процесса ( **псворкфловжоб** ), **возобновление** работы возвращает неустранимую ошибку.
* Механизм и место сохранения приостановленного задания могут различаться в зависимости от его типа. Например, по умолчанию приостановленные задания рабочих процессов сохраняются в хранилище неструктурированных файлов, но также могут сохраняться в базе данных SQL.
* При возобновлении задания его состояние меняется с **Suspended** на **Running**. Чтобы найти выполняемые задания, включая те, которые были возобновлены с помощью этого командлета, используйте параметр *State* командлета **Get-Job** , чтобы получить задания в состоянии **выполнения** .
* Задания некоторых типов имеют параметры или свойства, которые не позволяют среде Windows PowerShell приостанавливать их. Если попытки приостановить задание завершились ошибкой, убедитесь, что параметры задания и свойства допускают приостановку.

## Связанные ссылки

[Get-Job.](Get-Job.md)

[Receive-Job.](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job.](Stop-Job.md)

[Suspend-Job](Suspend-Job.md)

[Wait-Job](Wait-Job.md)
