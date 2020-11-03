---
description: Способы устранения проблем с запланированными заданиями
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/about/about_scheduled_jobs_troubleshooting?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scheduled_Jobs_Troubleshooting
ms.openlocfilehash: 924205edb9d44724cfef201d84baa304ecde67ad
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231625"
---
# <a name="about-scheduled-jobs-troubleshooting"></a>Сведения об устранении неполадок запланированных заданий

## <a name="short-description"></a>Краткое описание

Способы устранения проблем с запланированными заданиями

## <a name="long-description"></a>Подробное описание

В этом документе описываются некоторые проблемы, которые могут возникнуть при использовании функций запланированных заданий PowerShell, и предлагаются решения этих проблем.

Перед использованием запланированных заданий PowerShell см. раздел [about_Scheduled_Jobs](about_Scheduled_Jobs.md) и связанные запланированные задания о разделах.

Дополнительные сведения о командлетах, содержащихся в модуле **PSScheduledJob** , см. в разделе [PSScheduledJob](xref:PSScheduledJob).

## <a name="cant-find-job-results"></a>Не удается найти результаты задания

### <a name="basic-method-for-getting-job-results-in-powershell"></a>Базовый метод получения результатов задания в PowerShell

При выполнении запланированного задания создается экземпляр запланированного задания. Для просмотра, управления и получения результатов экземпляров запланированных заданий используйте командлеты задания.

> [!NOTE]
> Чтобы использовать командлеты задания для экземпляров запланированных заданий, необходимо импортировать модуль **PSScheduledJob** в сеанс. Чтобы импортировать модуль **PSScheduledJob** , введите `Import-Module PSScheduledJob` или используйте любой командлет запланированного задания, например `Get-ScheduledJob` .

Чтобы получить список всех экземпляров запланированного задания, используйте `Get-Job` командлет.

```powershell
Import-Module PSScheduledJob
Get-Job ProcessJob
```

```Output
Id     Name         PSJobTypeName   State         HasMoreData     Location
--     ----         -------------   -----         -----------     --------
43     ProcessJob   PSScheduledJob  Completed     False           localhost
44     ProcessJob   PSScheduledJob  Completed     False           localhost
45     ProcessJob   PSScheduledJob  Completed     False           localhost
46     ProcessJob   PSScheduledJob  Completed     False           localhost
47     ProcessJob   PSScheduledJob  Completed     False           localhost
48     ProcessJob   PSScheduledJob  Completed     False           localhost
49     ProcessJob   PSScheduledJob  Completed     False           localhost
50     ProcessJob   PSScheduledJob  Completed     False           localhost
```

`Get-Job`Командлет отправляет объекты **процессжоб** вниз по конвейеру. `Format-Table`Командлет отображает свойства **Name** , **ID** и **псбегинтиме** экземпляра запланированного задания в таблице.

```powershell
Get-Job ProcessJob | Format-Table -Property Name, ID, PSBeginTime -Auto
```

```Output
Name       Id PSBeginTime
----       -- ---------
ProcessJob 43 11/2/2011 3:00:02 AM
ProcessJob 44 11/3/2011 3:00:02 AM
ProcessJob 45 11/4/2011 3:00:02 AM
ProcessJob 46 11/5/2011 3:00:02 AM
ProcessJob 47 11/6/2011 3:00:02 AM
ProcessJob 48 11/7/2011 12:00:01 AM
ProcessJob 49 11/7/2011 3:00:02 AM
ProcessJob 50 11/8/2011 3:00:02 AM
```

Чтобы получить результаты экземпляра запланированного задания, используйте `Receive-Job` командлет. Следующая команда возвращает результаты последнего экземпляра Процессжоб (ID = 50).

```powershell
Receive-Job -ID 50
```

### <a name="basic-method-for-finding-job-results-on-disk"></a>Базовый метод поиска результатов задания на диске

Для управления запланированными заданиями используйте командлеты задания, такие как `Get-Job` и `Receive-Job` .

Если не `Get-Job` получает экземпляр задания или не `Receive-Job` получает результаты задания, можно выполнить поиск в файлах журнала выполнения задания на диске.
Журнал выполнения содержит записи всех запущенных экземпляров задания.

Убедитесь, что в каталоге для запланированного задания существует каталог timestamp-Name, по следующему пути:

`$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJob\<ScheduledJobName>\Output`

Пример:

`C:\Users<UserName>\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJob\<ScheduledJobName>\Output`

Например, `Get-ChildItem` командлет возвращает историю выполнения на диске запланированного задания **процессжоб** .

```powershell
$Path = '$home\AppData\Local\Microsoft\Windows\PowerShell'
$Path += '\ScheduledJobs\ProcessJob\Output'
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\AppData\Local\Microsoft\Windows\PowerShell
               \ScheduledJobs\ProcessJob\Output

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         11/2/2011   3:00 AM            20111102-030002-260
d----         11/3/2011   3:00 AM            20111103-030002-277
d----         11/4/2011   3:00 AM            20111104-030002-209
d----         11/5/2011   3:00 AM            20111105-030002-251
d----         11/6/2011   3:00 AM            20111106-030002-174
d----         11/7/2011  12:00 AM            20111107-000001-914
d----         11/7/2011   3:00 AM            20111107-030002-376
```

Каждый именованный каталог timestamp представляет экземпляр задания. Результаты каждого экземпляра задания сохраняются в файле **Results.xml** в каталоге timestamp-Name.

Например, следующая команда возвращает файлы **Results.xml** для каждого сохраненного экземпляра запланированного задания **процессжоб** . Если файл **Results.xml** отсутствует, PowerShell не может вернуть или отобразить результаты задания.

```powershell
$Path = '$home\AppData\Local\Microsoft\Windows\PowerShell'
$Path += '\ScheduledJobs\ProcessJob\Output\*\Results.xml'
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\Appdata\Local\Microsoft\Windows\PowerShell
               \ScheduledJobs\ProcessJob\Output
```

Командлет задания не может получить экземпляры запланированных заданий или их результаты, так как модуль **PSScheduledJob** не импортируется в сеанс.

> [!NOTE]
> Перед использованием командлета задания в экземплярах запланированных заданий убедитесь, что модуль **PSScheduledJob** включен в сеанс. Без модуля **PSScheduledJob** командлеты задания не могут получать экземпляры запланированных заданий или их результаты.

Чтобы импортировать модуль **PSScheduledJob** , выполните следующие действия.

```powershell
Import-Module PSScheduledJob
```

### <a name="receive-job-cmdlet-might-already-have-returned-the-results"></a>Возможно, Receive-Job командлет уже вернул результаты.

Если не `Receive-Job` возвращает результаты экземпляра задания, это может быть вызвано тем, что `Receive-Job` команда была запущена для этого экземпляра задания в текущем сеансе без параметра **сохранения** .

При использовании `Receive-Job` без параметра **сохранения** `Receive-Job` возвращает результаты задания и задает для свойства **хасморедата** экземпляра задания **значение false**. Значение **false** означает, что `Receive-Job` вернул результаты задания, а экземпляр больше не возвращает результаты. Этот параметр подходит для стандартных фоновых заданий, но не для экземпляров запланированных заданий, которые сохраняются на диске.

Чтобы снова получить результаты экземпляра задания, запустите новый сеанс PowerShell, введя команду `PowerShell` . Импортируйте модуль **PSScheduledJob** и повторите `Receive-Job` команду.

```powershell
Receive-Job -ID 50
```

```Output
#No results
```

```powershell
PowerShell.exe
```

```Output
Windows PowerShell
Copyright (C) 2012 Microsoft Corporation. All rights reserved.
```

```powershell
Import-Module PSScheduledJob
Receive-Job -ID 50
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id  ProcessName
-------  ------    -----      ----- -----   ------     --  -----------
1213         33    12348      21676    88    25.71   1608  CcmExec
29            4     1168       2920    43     0.02    748  conhost
46            6     2208       4612    45     0.03   1640  conhost
```

### <a name="using-keep-parameter-to-get-results-more-than-one-time-in-a-session"></a>Использование параметра "удержать" для получения результатов более одного раза в сеансе

Чтобы получить результат экземпляра задания более одного раза в сеансе, используйте параметр **сохранения** `Receive-Job` командлета.

```powershell
Import-Module PSScheduledJob
Receive-Job -ID 50 -Keep
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id  ProcessName
-------  ------    -----      ----- -----   ------     --  -----------
1213         33    12348      21676    88    25.71   1608  CcmExec
29            4     1168       2920    43     0.02    748  conhost
46            6     2208       4612    45     0.03   1640  conhost
```

```powershell
Receive-Job -ID 50 -Keep
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id  ProcessName
-------  ------    -----      ----- -----   ------     --  -----------
1213         33    12348      21676    88    25.71   1608  CcmExec
29            4     1168       2920    43     0.02    748  conhost
46            6     2208       4612    45     0.03   1640  conhost
```

### <a name="the-scheduled-job-might-be-corrupted"></a>Запланированное задание может быть повреждено

Если запланированное задание будет повреждено, PowerShell удалит поврежденное запланированное задание и его результаты. Невозможно восстановить результаты поврежденного запланированного задания.

Чтобы определить, существует ли по-прежнему запланированное задание, используйте `Get-ScheduledJob` командлет.

```powershell
Get-ScheduledJob
```

### <a name="the-number-of-results-might-have-exceeded-the-executionhistorylength"></a>Возможно, число результатов превысило Ексекутионхисториленгс

Свойство **ексекутионхисториленгс** запланированного задания определяет, сколько экземпляров задания и их результаты сохраняются на диске. Значение по умолчанию: 32.
Когда количество экземпляров запланированного задания превышает это значение, PowerShell удаляет самый старый экземпляр задания, чтобы освободить место для каждого нового экземпляра задания.

Чтобы получить значение свойства **ексекутионхисториленгс** запланированного задания, используйте следующий формат команды:

```powershell
(Get-ScheduledJob <JobName>).ExecutionHistoryLength
```

Например, следующая команда возвращает значение свойства **ексекутионхисториленгс** запланированного задания **процессжоб** .

```powershell
(Get-ScheduledJob ProcessJob).ExecutionHistoryLength
```

Чтобы задать или изменить значение свойства **ексекутионхисториленгс** , используйте параметр **максресулткаунт** `Register-ScheduledJob` `Set-ScheduledJob` командлетов и.

Следующая команда увеличивает значение свойства **ексекутионхисториленгс** на 50.

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -MaxResultCount 50
```

### <a name="the-job-instance-results-might-have-been-deleted"></a>Возможно, результаты экземпляра задания были удалены.

Параметр **клеарексекутионхистори** `Set-ScheduledJob` командлета удаляет историю выполнения задания. Эту функцию можно использовать для высвобождения места на диске или для удаления ненужных или уже использованных, проанализированных или сохраненных в другом расположениях.

Чтобы удалить журнал выполнения запланированного задания, используйте параметр **клеарексекутионхистори** запланированного задания.

Следующая команда удаляет журнал выполнения запланированного задания **процессжоб** .

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -ClearExecutionHistory
```

Кроме того, `Remove-Job` командлет удаляет результаты задания. При использовании `Remove-Job` для удаления запланированного задания он удаляет все экземпляры задания на диске, включая журнал выполнения и все результаты задания.

### <a name="jobs-started-by-using-the-start-job-cmdlet-are-not-saved-to-disk"></a>Задания, запущенные с помощью командлета Start-Job, не сохраняются на диске

При использовании `Start-Job` для запуска запланированного задания вместо использования триггера задания `Start-Job` запускает стандартное фоновое задание. Фоновое задание и его результаты не сохраняются в журнале выполнения задания на диске.

С помощью `Get-Job` командлета можно получить задание и `Receive-Job` командлет для получения результатов задания, но результаты будут доступны только до тех пор, пока не будет использован параметр сохранения `Receive-Job` командлета.

Кроме того, фоновые задания и их результаты относятся к конкретному сеансу. они существуют только в сеансе, в котором они созданы. Если вы удалите задание с помощью `Remove-Job` , закройте сеанс или закройте PowerShell, экземпляр задания и его результаты будут удалены.

## <a name="scheduled-job-doesnt-run"></a>Запланированное задание не выполняется

Запланированные задания не выполняются автоматически, если триггер задания или запланированное задание отключены.

Используйте `Get-ScheduledJob` командлет для получения запланированного задания. Убедитесь, что для свойства **Enabled** запланированного задания задано значение **true**.

```powershell
Get-ScheduledJob ProcessJob
```

```Output
Id         Name            Triggers        Command         Enabled
--         ----            --------        -------         -------
4          ProcessJob      {1, 2}          Get-Process     True
```

```powershell
(Get-ScheduledJob ProcessJob).Enabled
```

```Output
True
```

Используйте `Get-JobTrigger` командлет, чтобы получить триггеры задания для запланированного задания.
Убедитесь, что для свойства **Enabled** триггера задания задано значение **true**.

```powershell
Get-ScheduledJob ProcessJob | Get-JobTrigger
```

```Output
Id      Frequency    Time                   DaysOfWeek            Enabled
--      ---------    ----                   ----------            -------
1       Weekly       11/7/2011 5:00:00 AM   {Monday, Thursday}    True
2       Daily        11/7/2011 3:00:00 PM                         True
```

```powershell
Get-ScheduledJob ProcessJob|Get-JobTrigger|Format-Table ID, Enabled -Auto
```

```Output
Id Enabled
-- -------
1    True
2    True
```

### <a name="scheduled-jobs-dont-run-automatically-if-job-triggers-are-invalid"></a>Запланированные задания не выполняются автоматически, если триггеры заданий недопустимы

Например, триггер задания может указывать дату в прошлом или дату, которая не возникает, например 5-й понедельник месяца.

Запланированные задания не выполняются автоматически, если условия триггера задания или задания не выполнены.

Например, запланированное задание, выполняемое только в том случае, если конкретный пользователь входит в систему, не будет работать, если он не вошел в систему или удаленно подключается.

Проверьте параметры запланированного задания и убедитесь, что они удовлетворены.
Например, запланированное задание требует, чтобы компьютер был неактивен или для него требуется сетевое подключение, или он имеет длительное **идледуратион** или короткое значение **IdleTimeout** не может быть запущено.

С помощью `Get-ScheduledJobOption` командлета проверьте параметры задания и их значения.

```powershell
Get-ScheduledJob -Name ProcessJob
```

```Output
StartIfOnBatteries     : False
StopIfGoingOnBatteries : True
WakeToRun              : True
StartIfNotIdle         : True
StopIfGoingOffIdle     : False
RestartOnIdleResume    : False
IdleDuration           : 00:10:00
IdleTimeout            : 01:00:00
ShowInTaskScheduler    : True
RunElevated            : False
RunWithoutNetwork      : True
DoNotAllowDemandStart  : False
MultipleInstancePolicy : IgnoreNew
JobDefinition          : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

Описание параметров запланированного задания см. в разделе [New-scheduledjoboptions](xref:PSScheduledJob.New-ScheduledJobOption).

### <a name="the-scheduled-job-instance-might-have-failed"></a>Возможно, произошел сбой экземпляра запланированного задания

Если команда запланированного задания завершается сбоем, PowerShell немедленно сообщает о ней, выполнив сообщение об ошибке. Однако если задание завершается сбоем, когда планировщик задач пытается запуститься, эта ошибка недоступна для PowerShell.

Для обнаружения и исправления ошибок заданий используйте следующие методы.

Проверьте журнал событий планировщик задач на наличие ошибок. Чтобы проверить журнал, используйте Просмотр событий или команду PowerShell, как показано ниже.

```powershell
Get-WinEvent -LogName Microsoft-Windows-TaskScheduler/Operational |
 Where {$_.Message -like "fail"}
```

Проверьте запись задания в планировщик задач. Запланированные задания PowerShell хранятся в следующей запланированной папке задачи:

`Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs`

### <a name="the-scheduled-job-might-not-run-because-of-insufficient-permission"></a>Запланированное задание может не запускаться из-за недостаточных разрешений

Запланированные задания выполняются с разрешениями пользователя, создавшего задание, или разрешений пользователя, заданного параметром **Credential** в `Register-ScheduledJob` `Set-ScheduledJob` команде или.

Если у этого пользователя нет разрешения на выполнение команд или сценариев, задание завершается ошибкой.

## <a name="cant-get-scheduled-job-or-scheduled-job-is-corrupted"></a>Не удается получить расписание или запланированное задание, так как оно повреждено

В редких случаях запланированные задания могут быть повреждены или содержать внутренние противоречия, которые не могут быть разрешены. Как правило, это происходит, когда XML-файлы для запланированного задания редактируются вручную, что приводит к неправильному XML.

При повреждении запланированного задания PowerShell пытается удалить запланированное задание, его историю выполнения и результаты с диска.

Если не удается удалить запланированное задание, при каждом запуске командлета будет выводится поврежденное сообщение об ошибке задания `Get-ScheduledJob` .

Чтобы удалить поврежденное запланированное задание, используйте один из следующих методов.

Удалите `<ScheduledJobName>` каталог для запланированного задания. Не удаляйте каталог **ScheduledJob** .

Расположение каталога:

`$env:UserProfile\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs<ScheduledJobName>`

Пример:

`C:\Users<UserName>\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs<ScheduledJobName>.`

Чтобы удалить запланированное задание, используйте планировщик задач. Запланированные задачи PowerShell отображаются в следующем планировщик задач пути:

`Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs<ScheduledJobName>`

## <a name="job-cmdlets-cant-consistently-find-scheduled-jobs"></a>Командлеты задания не могут постоянно находить запланированные задания

Если модуль **PSScheduledJob** не находится в текущем сеансе, командлеты задания не могут получать запланированные задания, запускать их или получать результаты.

Чтобы импортировать модуль **PSScheduledJob** , введите `Import-Module PSScheduledJob` или запустите или получите любой командлет в модуле, например `Get-ScheduledJob` командлет.
Начиная с PowerShell 3,0 модули импортируются автоматически при получении или использовании любого командлета в модуле.

Если модуль **PSScheduledJob** не находится в текущем сеансе, возможно, используется следующая последовательность команд.

```powershell
Get-Job ProcessJob
```

```Output
Get-Job : The command cannot find the job because the job name
ProcessJob was not found.
Verify the value of the Name parameter, and then try the command again.
+ CategoryInfo          : ObjectNotFound: (ProcessJob:String) [Get-Job],
PSArgumentException
+ FullyQualifiedErrorId : JobWithSpecifiedNameNotFound,Microsoft.PowerShell.
Commands.GetJobCommand
```

```powershell
Get-Job
Get-ScheduledJob ProcessJob
```

```Output
Id         Name            Triggers        Command      Enabled
--         ----            --------        -------      -------
4          ProcessJob      {1}             Get-Process  True
```

```powershell
Get-Job ProcessJob
```

```Output
Id     Name         PSJobTypeName   State       HasMoreData     Location
--     ----         -------------   -----       -----------     --------
43     ProcessJob   PSScheduledJob  Completed   True            localhost
44     ProcessJob   PSScheduledJob  Completed   True            localhost
45     ProcessJob   PSScheduledJob  Completed   True            localhost
46     ProcessJob   PSScheduledJob  Completed   True            localhost
47     ProcessJob   PSScheduledJob  Completed   True            localhost
48     ProcessJob   PSScheduledJob  Completed   True            localhost
49     ProcessJob   PSScheduledJob  Completed   True            localhost
50     ProcessJob   PSScheduledJob  Completed   True            localhost
```

Это происходит потому, что `Get-ScheduledJob` команда автоматически импортирует модуль **PSScheduledJob** , а затем выполняет команду.

## <a name="see-also"></a>См. также статью

[about_Scheduled_Jobs_Basics](about_Scheduled_Jobs_Basics.md)

[about_Scheduled_Jobs_Advanced](about_Scheduled_Jobs_Advanced.md)

[about_Scheduled_Jobs](about_Scheduled_Jobs.md)

Командлеты модуля [PSScheduledJob](xref:PSScheduledJob)

[Планировщик заданий](/windows/desktop/TaskSchd/task-scheduler-reference)
