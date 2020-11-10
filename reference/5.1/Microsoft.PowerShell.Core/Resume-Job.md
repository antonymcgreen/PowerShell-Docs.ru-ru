---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/resume-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-Job
ms.openlocfilehash: 6d08d9053e100cb53d37a6e4931d118f90c35a6a
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388541"
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

`Resume-Job`Командлет возобновляет приостановленное задание рабочего процесса, например с помощью `Suspend-Job` командлета или действия [about_Suspend-Workflow](../PSWorkflow/about/about_Suspend-Workflow.md) . При возобновлении задания рабочего процесса обработчик заданий перестраивает состояние, метаданные и выходные данные из сохраненных ресурсов, таких как контрольные точки. Задание перезапускается без потери состояния или данных.
Состояние задания меняется с **Suspended** на **Running**.

Используйте параметры, `Resume-Job` чтобы выбрать задания по имени, идентификатору, идентификатору экземпляра или передать по каналу объект задания, например, возвращаемый `Get-Job` командлетом, в `Resume-Job` . Для выбора задания, которое нужно возобновить, можно также использовать фильтр свойств.

По умолчанию `Resume-Job` возвращает значение немедленно, несмотря на то, что все задания могут быть еще не возобновлены. Чтобы заблокировать вывод командной строки до тех пор, пока все указанные задания не будут возобновлены, используйте параметр **Wait**.

`Resume-Job`Командлет работает только с пользовательскими типами заданий, такими как задания рабочего процесса. Он не работает для стандартных фоновых заданий, например для тех, которые запускаются с помощью `Start-Job` командлета. При отправке задания неподдерживаемого типа `Resume-Job` создает завершающую ошибку и прекращает выполнение.

Определить задание рабочего процесса можно по значению **PSWorkflowJob** свойства **PSJobTypeName** задания. Чтобы определить, поддерживает ли конкретный тип настраиваемого задания `Resume-Job` командлет, см. разделы справки для типа настраиваемого задания.

Перед использованием командлета задания для настраиваемого типа задания Импортируйте модуль, поддерживающий тип настраиваемого задания, с помощью `Import-Module` командлета или путем получения или использования командлета в модуле.

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. возобновление задания по ИДЕНТИФИКАТОРу

Команды в этом примере проверяют, является ли задание приостановленным заданием рабочего процесса, а затем возобновляют его. Первая команда использует `Get-Job` командлет для получения задания. В выходных данных видно, что задания является приостановленным заданием рабочего процесса. Вторая команда использует параметр **ID** `Resume-Job` командлета, чтобы возобновить задание с **идентификатором** 4.

```
PS C:\> Get-Job EventJob
Id     Name            PSJobTypeName   State         HasMoreData     Location   Command
--     ----            -------------   -----         -----------     --------   -------
4      EventJob        PSWorkflowJob   Suspended     True            Server01   \\Script\Share\Event.ps1

PS C:\> Resume-Job -Id 4
```

### Пример 2. возобновление задания по имени

В этой команде используется параметр **Name** для возобновления нескольких заданий рабочих процессов на локальном компьютере.

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest*
```

### Пример 3. Использование значений настраиваемых свойств

В этой команде с помощью значения настраиваемого свойства определяется задание рабочего процесса, которое нужно возобновить. В ней используется параметр **Filter** для указания задания рабочего процесса по значению свойства **CustomID**. В ней также используется параметр **State** для проверки того, приостановлено ли задание рабочего процесса, перед попыткой его возобновления.

```
PS C:\> Resume-Job -Filter @{CustomID="T091291"} -State Suspended
```

### Пример 4. возобновление всех приостановленных заданий на удаленном компьютере

Эта команда возобновляет все приостановленные задания на удаленном компьютере Srv01.

```
PS C:\> Invoke-Command -ComputerName Srv01 -ScriptBlock {Get-Job -State Suspended | Resume-Job}
```

Команда использует `Invoke-Command` командлет для выполнения команды на компьютере SRV01. Удаленная команда использует параметр **State** `Get-Job` командлета, чтобы получить все приостановленные задания на компьютере. Оператор конвейера ( `|` ) отправляет приостановленные задания в `Resume-Job` командлет, который возобновляет их.

### Пример 5. Ожидание возобновления заданий

Эта команда использует параметр **Wait** для направления `Resume-Job` возврата только после возобновления всех указанных заданий. Параметр **Wait** особенно полезен в сценариях, в которых предполагается, что задания должны быть возобновлены, прежде чем выполнение сценария будет продолжено.

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest* -Wait
```

### Пример 6. Возобновление рабочего процесса, который приостанавливает работу

В этом примере кода показано `Suspend-Workflow` действие в рабочем процессе.

`Test-Suspend`Рабочий процесс на компьютере Server01. При запуске рабочего процесса Рабочий процесс запускает `Get-Date` действие и сохраняет результат в `$a` переменной. Затем выполняется `Suspend-Workflow` действие. В ответ принимается контрольная точка, приостанавливается рабочий процесс и возвращается объект задания рабочего процесса. `Suspend-Workflow` Возвращает объект задания рабочего процесса, даже если рабочий процесс не выполняется явным образом как задание.

`Resume-Job` возобновляет `Test-Suspend` Рабочий процесс в Job8. В ней используется параметр **Wait** для блокирования вывода командной строки до тех пор, пока задание не будет возобновлено.

`Receive-Job`Командлет возвращает результаты `Test-Suspend` рабочего процесса. Последняя команда в рабочем процессе возвращает объект **TimeSpan** , представляющий истекшее время между текущей датой и временем и датой и временем, которые были сохранены в `$a` переменной до приостановки рабочего процесса.

```
#SampleWorkflow
Workflow Test-Suspend
{
    $a = Get-Date
    Suspend-Workflow
    (Get-Date)- $a
}

PS C:\> Test-Suspend -PSComputerName Server01
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
8      Job8            PSWorkflowJob   Suspended     True            Server01             Test-Suspend

PS C:\> Resume-Job -Name "Job8" -Wait
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
8      Job8            PSWorkflowJob   Running       True            Server01             Test-Suspend

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

`Resume-Job`Командлет позволяет возобновить задание рабочего процесса, которое было приостановлено с помощью `Suspend-Workflow` действия. Это действие приостанавливает рабочий процесс из самого процесса. Оно допустимо только в рабочих процессах.

Дополнительные сведения о `Suspend-Workflow` см. в разделе about_Suspend-Workflow] (.. /Псворкфлов/абаут/about_Suspend-Workflow. md).

## PARAMETERS

### -Filter

Указывает хэш-таблицу условий. Этот командлет возобновляет задания, которые соответствуют всем условиям в хэш-таблице. Введите хэш-таблицу, где ключи являются свойствами заданий, а значения — значениями этих свойств.

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

Идентификатор — это целое число, которое однозначно определяет задание в текущем сеансе. Проще запомнить и ввести, чем идентификатор экземпляра, но он уникален только в текущем сеансе. Можно ввести один или несколько идентификаторов, разделенных запятыми. Чтобы найти идентификатор задания, выполните команду `Get-Job` .

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

Указывает массив идентификаторов экземпляров заданий, которые возобновляет этот командлет. По умолчанию останавливаются все задания.

Идентификатор экземпляра — это GUID, который однозначно определяет задание на компьютере. Чтобы найти идентификатор экземпляра задания, выполните команду `Get-Job` .

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

Указывает задания, которые нужно возобновить. Введите переменную, содержащую задания, либо команду, которая их возвращают. Можно также передать задания по конвейеру в `Resume-Job` командлет.

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

Указывает массив понятных имен заданий, которые возобновляет этот командлет. Введите одно или несколько имен заданий.
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

Указывает состояние заданий для возобновления. Допустимые значения для этого параметра:

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

Указывает, что этот командлет подавляет командную строку до тех пор, пока не будут перезапущены все результаты задания. По умолчанию этот командлет немедленно возвращает доступные результаты.

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

К этому командлету можно передать все типы заданий. Если `Resume-Job` получает задание неподдерживаемого типа, оно возвращает завершающую ошибку.

## Выходные данные

### Нет, System. Management. Automation. job

Этот командлет возвращает задания, которые он пытается возобновить, если используется параметр **PassThru** .
В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

- `Resume-Job` может возобновлять только приостановленные задания. При отправке задания в другом состоянии `Resume-Job` выполняет операцию возобновления задания, но выдает предупреждение о том, что задание не может быть возобновлено. Чтобы отключить это предупреждение, используйте общий параметр **WarningAction** со значением SilentlyContinue.
- Если задание не относится к типу, который поддерживает возобновление, например задание рабочего процесса ( **псворкфловжоб** ), `Resume-Job` Возвращает завершающую ошибку.
- Механизм и место сохранения приостановленного задания могут различаться в зависимости от его типа. Например, по умолчанию приостановленные задания рабочих процессов сохраняются в хранилище неструктурированных файлов, но также могут сохраняться в базе данных SQL.
- При возобновлении задания его состояние меняется с **Suspended** на **Running**. Чтобы найти выполняемые задания, включая те, которые были возобновлены с помощью этого командлета, используйте параметр **State** `Get-Job` командлета для получения заданий в состоянии **выполняется** .
- Задания некоторых типов имеют параметры или свойства, которые не позволяют среде Windows PowerShell приостанавливать их.
  Если попытки приостановить задание завершились ошибкой, убедитесь, что параметры задания и свойства допускают приостановку.

## Связанные ссылки

[Get-Job.](Get-Job.md)

[Receive-Job.](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job.](Stop-Job.md)

[Suspend-Job](Suspend-Job.md)

[Wait-Job](Wait-Job.md)
