---
description: Описание процедур создания запланированных заданий и управления ими.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/about/about_scheduled_jobs_basics?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scheduled_Jobs_Basics
ms.openlocfilehash: d957c3267959c13b705e79fb220da4048e27a435
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231629"
---
# <a name="about-scheduled-jobs-basics"></a>Общие сведения о запланированных заданиях

## <a name="short-description"></a>Краткое описание

Описание процедур создания запланированных заданий и управления ими.

## <a name="long-description"></a>Подробное описание

В этом документе показано, как выполнять базовые задачи по созданию запланированных заданий и управлению ими. Дополнительные сведения о более сложных задачах см. в разделе [about_Scheduled_Jobs_Advanced](about_Scheduled_Jobs_Advanced.md).

Дополнительные сведения о командлетах, содержащихся в модуле **PSScheduledJob** , см. в разделе [PSScheduledJob](xref:PSScheduledJob).

## <a name="how-to-create-a-scheduled-job"></a>Создание запланированного задания

Чтобы создать запланированное задание, используйте `Register-ScheduledJob` командлет. Командлету требуется имя, а также команды или скрипт, выполняемые заданием. Можно либо запустить задание немедленно, добавив параметр **RunNow** , либо создать триггер задания и задать параметры задания при создании задания или изменить существующее задание.

Чтобы создать задание, запускающее скрипт, используйте параметр **FilePath** , чтобы указать путь к файлу скрипта. Чтобы создать задание, запускающее команды, используйте параметр **ScriptBlock** .

`Register-ScheduledJob`Командлет создает **процессжоб** , который выполняет `Get-Process` команду. Это запланированное задание имеет параметры задания по умолчанию и не имеет триггера задания.

```powershell
Register-ScheduledJob -Name ProcessJob -ScriptBlock { Get-Process }
```

```Output
Id         Name            Triggers        Command       Enabled
--         ----            --------        -------       -------
8          ProcessJob      {}              Get-Process   True
```

## <a name="how-to-create-a-job-trigger"></a>Создание триггера задания

Триггеры заданий запускают запланированное задание автоматически. Триггером задания может быть однократное или повторяющееся расписание или событие, например, когда пользователь входит в систему или запускается Windows. Каждое задание может иметь ноль, один или несколько триггеров заданий.

Чтобы создать триггер задания, используйте `New-JobTrigger` командлет. Следующая команда создает триггер задания, который запускает задание каждый понедельник и четверг в 5:00 AM.
Команда сохраняет триггер задания в `$T` переменной.

```powershell
$T = New-JobTrigger -Weekly -DaysOfWeek "Monday", "Thursday" -At "5:00 AM"
```

Триггеры задания не являются обязательными. Вы можете запустить запланированное задание в любое время, добавив параметр **RunNow** в `Register-ScheduledJob` команду или используя `Start-Job` командлеты.

## <a name="how-to-add-a-job-trigger"></a>Добавление триггера задания

При добавлении триггера задания в запланированное задание триггер задания добавляется в XML-файл запланированного задания для запланированного задания и становится частью запланированного задания.

Вы можете добавить триггер задания в запланированное задание при создании запланированного задания или изменить существующее задание. Вы можете в любое время изменить триггер задания для запланированного задания.

PowerShell использует одни и те же Триггеры заданий, которые планировщик задач использует. Подробные сведения о триггерах заданий см. в разделе справки по командлету [New-JobTrigger](xref:PSScheduledJob.New-JobTrigger) .

В следующем примере Сплаттинг используется для создания `$JobParms` значений параметров, которые передаются в `Register-ScheduledJob` командлет. Дополнительные сведения см. в разделе [about_Splatting. md](../../Microsoft.PowerShell.Core/About/about_Splatting.md).
`Register-ScheduledJob`Использует `@JobParms` для создания запланированного задания. Для указания триггера задания в переменной используется параметр **Trigger** `$T` .

```powershell
$JobParms = @{
  Name = "ProcessJob"
  ScriptBlock = {Get-Command}
  Trigger = $T
}

Register-ScheduledJob @JobParms
```

Вы также можете добавить триггер задания в существующее запланированное задание в любое время. `Add-JobTrigger`Командлет добавляет триггер задания в `$T` переменную в запланированное задание **процессжоб** .

```powershell
Add-JobTrigger -Name ProcessJob -Trigger $T
```

В результате триггер задания запускает **процессжоб** автоматически каждый понедельник и четверг в 5:00 AM.

## <a name="how-to-get-a-job-trigger"></a>Как получить триггер задания

Чтобы получить триггер задания для запланированного задания, используйте `Get-JobTrigger` командлет. Используйте параметры **Name** , **ID** и **InputObject** , чтобы указать запланированное задание, а не триггер задания.

`Get-JobTrigger` Возвращает триггер задания **процессжоб**.

```powershell
Get-JobTrigger -Name ProcessJob
```

```Output
Id   Frequency       Time                   DaysOfWeek              Enabled
--   ---------       ----                   ----------              -------
1    Weekly          11/7/2011 5:00:00 AM   {Monday, Thursday}      True
```

## <a name="how-to-create-job-options"></a>Создание параметров задания

Параметры задания устанавливают условия для запуска и выполнения задания. Каждое задание имеет параметры задания по умолчанию, если они не были изменены. Поскольку параметры задания могут препятствовать запуску задания в запланированное время, важно понимать параметры задания и использовать их аккуратно.

PowerShell использует те же параметры задания, которые планировщик задач использует. Подробные сведения о параметрах задания см. в разделе справки [New-scheduledjoboptions](xref:PSScheduledJob.New-ScheduledJobOption).

Параметры задания хранятся в XML-файле запланированного задания. Вы можете задать параметры задания при создании запланированного задания или изменить их в любое время.

`New-ScheduledJobOption`Командлет создает параметр запланированного задания, в котором параметру запланированного задания **вакеторун** присвоено значение true. Параметр **вакеторун** запускает запланированное задание, даже если компьютер находится в спящем или спящем режиме в запланированное время запуска. Команда сохраняет параметры задания в `$O` переменной.

```powershell
$O = New-ScheduledJobOption -WakeToRun
```

## <a name="how-to-get-job-options"></a>Получение параметров задания

Чтобы получить параметры задания запланированного задания, используйте `Get-ScheduledJobOption` командлет. Используйте параметры **Name** , **ID** и **InputObject** , чтобы указать запланированное задание, а не параметры задания.

`Get-ScheduledJobOption` Возвращает параметры задания **процессжоб**.

```powershell
Get-ScheduledJobOption -Name ProcessJob
```

```Output
StartIfOnBatteries     : False
StopIfGoingOnBatteries : True
WakeToRun              : False
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

## <a name="how-to-change-job-options"></a>Изменение параметров задания

Можно изменить параметры задания запланированного задания при создании запланированного задания или изменении существующего задания.

Сплаттед `$JobParms` передаются в `Add-JobTrigger` командлет для создания задания процесса. Для указания параметров задания в переменной используется параметр **scheduledjoboptions** `$O` .

```powershell
$JobParms = @{
  Name = "ProcessJob"
  ScriptBlock = {Get-Process}
  ScheduledJobOption = $O
}

Add-JobTrigger @JobParms
```

Можно также изменить параметры задания на существующее запланированное задание в любое время.
Следующая команда использует командлет, `Set-ScheduledJobOption` чтобы изменить значение параметра **вакеторун** **процессжоб** scheduledJob на **true**.

`Set`Командлеты в модуле **PSScheduledJob** , такие как `Set-ScheduledJobOption` командлет, не имеют параметров **имени** или **идентификатора** . Параметр **InputObject** можно использовать для указания параметров запланированного задания или передачи по конвейеру запланированного задания из `Get-ScheduledJobOption` командлета в `Set-ScheduledJobOption` .

В этом примере используется `Get-ScheduledJob` командлет для получения процессжоб. Он использует `Get-ScheduledJobOption` командлет, чтобы получить параметры задания в **процессжоб** , и командлет, `Set-ScheduledJobOption` чтобы изменить параметр задания **вакеторун** в процессжоб на true.

```powershell
Get-ScheduledJob -Name ProcessJob | Get-ScheduledJobOption |
 Set-ScheduledJobOption -WakeToRun
```

## <a name="how-to-get-scheduled-job-instances"></a>Получение экземпляров запланированных заданий

При запуске запланированного задания PowerShell создает экземпляр задания, аналогичный стандартному фоновому заданию PowerShell. `Get-Job` `Stop-Job` Для управления экземплярами заданий можно использовать командлеты задания, такие как, и `Receive-Job` .

> [!NOTE]
> Чтобы использовать командлеты задания для экземпляров запланированных заданий, необходимо импортировать модуль **PSScheduledJob** в сеанс. Чтобы импортировать модуль **PSScheduledJob** , введите `Import-Module PSScheduledJob` или используйте любой командлет запланированного задания, например `Get-ScheduledJob` .

Чтобы получить все экземпляры запланированных заданий PowerShell и все активные стандартные задания, используйте `Get-Job` командлет. `Import-Module`Командлет импортирует модуль **PSScheduledJob** и `Get-Job` получает задания на локальном компьютере.

```powershell
Import-Module PSScheduledJob
Get-Job
```

`Get-Job` Возвращает экземпляры **процессжоб** на локальном компьютере.

```powershell
Get-Job -Name ProcessJob
```

```Output
Id     Name        PSJobTypeName  State    HasMoreData   Location   Command
--     ----        ------------   -----    -----------   --------   -------
45     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
46     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
47     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
48     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
49     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
50     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
51     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
```

Отображение по умолчанию не показывает время начала, которое обычно различает экземпляры одного и того же запланированного задания.

`Get-Job`Командлет отправляет объекты по конвейеру. `Format-Table`Командлет отображает свойства **Name** , **ID** и **BeginTime** запланированного задания.

```powershell
Get-Job ProcessJob | Format-Table -Property Name, ID, BeginTime
```

```Output
Name       Id BeginTime
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

## <a name="get-scheduled-job-results"></a>Получение результатов запланированного задания

Чтобы получить результаты экземпляра запланированного задания, используйте `Receive-Job` командлет.

> [!NOTE]
> Чтобы использовать командлеты задания для экземпляров запланированных заданий, необходимо импортировать модуль **PSScheduledJob** в сеанс. Чтобы импортировать модуль **PSScheduledJob** , введите `Import-Module PSScheduledJob` или используйте любой командлет запланированного задания, например `Get-ScheduledJob` .

В этом примере получаются результаты последнего экземпляра запланированного задания **процессжоб** (ид = 51).

```powershell
Import-Module PSScheduledJob
Receive-Job -ID 51 -Keep
```

Результаты запланированных заданий сохраняются на диске, поэтому параметр **сохранения** `Receive-Job` не требуется. Однако без параметра **сохранения** результаты запланированного задания можно получить только один раз в каждом сеансе PowerShell. Чтобы запустить новый сеанс PowerShell, введите `PowerShell` или откройте новое окно PowerShell.

## <a name="see-also"></a>См. также статью

[about_Scheduled_Jobs_Advanced](about_Scheduled_Jobs_Advanced.md)

[about_Scheduled_Jobs_Troubleshooting](about_Scheduled_Jobs_Troubleshooting.md)

[about_Scheduled_Jobs](about_Scheduled_Jobs.md)

[about_Splatting. md](../../Microsoft.PowerShell.Core/About/about_Splatting.md)

Командлеты модуля [PSScheduledJob](xref:PSScheduledJob)

[Планировщик заданий](/windows/desktop/TaskSchd/task-scheduler-reference)
