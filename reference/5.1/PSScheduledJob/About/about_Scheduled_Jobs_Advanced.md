---
description: Дополнительные разделы о запланированных заданиях, включая описание структуры файлов, лежащей в основе запланированных заданий.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/about/about_scheduled_jobs_advanced?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scheduled_Jobs_Advanced
ms.openlocfilehash: 7b09a72e8ad7e68641c73d2f7e59065dbf8f889b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231633"
---
# <a name="about-scheduled-jobs-advanced"></a>О дополнительных запланированных заданиях

## <a name="short-description"></a>Краткое описание

Дополнительные разделы о запланированных заданиях, включая описание структуры файлов, лежащей в основе запланированных заданий.

## <a name="long-description"></a>Подробное описание

Дополнительные сведения о командлетах, содержащихся в модуле **PSScheduledJob** , см. в разделе [PSScheduledJob](xref:PSScheduledJob).

## <a name="scheduled-job-directories-and-files"></a>Каталоги и файлы запланированных заданий

Запланированные задания PowerShell — это как задания PowerShell, так и задачи планировщик задач.
Каждое запланированное задание регистрируется в планировщик задач и сохраняется на диске в формате XML сериализации Microsoft .NET Framework.

При создании запланированного задания PowerShell создает каталог для запланированного задания в `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` каталоге на локальном компьютере. Имя каталога совпадает с именем задания.

Ниже приведен пример каталога **ScheduledJobs** .

```powershell
Get-ChildItem $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs
```

```Output
Directory: C:\Users\User01\AppData\Local
               \Microsoft\Windows\PowerShell\ScheduledJobs

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         9/29/2011  10:03 AM            ArchiveProjects
d----         9/30/2011   1:18 PM            Inventory
d----        10/20/2011   9:15 AM            Backup-Scripts
d----         11/7/2011  10:40 AM            ProcessJob
d----         11/2/2011  10:25 AM            SecureJob
d----         9/27/2011   1:29 PM            Test-HelpFiles
d----         9/26/2011   4:22 PM            DeployPackage
```

Каждое запланированное задание имеет свой собственный каталог. Каталог содержит XML-файл запланированного задания и **выходной** подкаталог.

```powershell
$Path = "$home\AppData\Local\Microsoft\Windows\PowerShell"
$Path += "\ScheduledJobs\ProcessJob"
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\AppData\Local\Microsoft\Windows\PowerShell
               \ScheduledJobs\ProcessJob

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----         11/1/2011   3:00 PM            Output
-a---         11/1/2011   3:43 PM       7281 ScheduledJobDefinition.xml
```

**Выходной** каталог для запланированного задания содержит журнал выполнения.
Каждый раз, когда триггер задания запускает запланированное задание, PowerShell создает в выходном каталоге каталог с меткой времени. Каталог меток времени содержит результаты задания в файле **Results.xml** и состояние задания в **Status.xmlном** файле.

Следующая команда показывает каталоги журнала выполнения для запланированного задания **процессжоб** .

```powershell
$Path = "$home\AppData\Local\Microsoft"
$Path += "\Windows\PowerShell\ScheduledJobs\ProcessJob\Output"
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\AppData\Local\Microsoft
               \Windows\PowerShell\ScheduledJobs\ProcessJob\Output

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

```powershell
$Path = "$home\AppData\Local\Microsoft\Windows\PowerShell\"
$Path += "ScheduledJobs\ProcessJob\Output\20111102-030002-260"
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\AppData\Local\Microsoft\Windows\PowerShell
               \ScheduledJobs\ProcessJob\Output\20111102-030002-260

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---         11/2/2011   3:00 AM     581106 Results.xml
-a---         11/2/2011   3:00 AM       9451 Status.xml
```

Вы можете открывать и изучать **ScheduledJobDefinition.xml** , **Results.xml** и **Status.xml** файлы или использовать `Select-XML` командлет для анализа файлов.

> [!WARNING]
> Не изменяйте XML-файлы. Если любой XML-файл содержит недопустимый XML-код, PowerShell удаляет запланированное задание и его историю выполнения, включая результаты задания.

## <a name="start-a-scheduled-job-immediately"></a>Немедленное запуск запланированного задания

Вы можете немедленно запустить запланированное задание одним из двух способов:

- Выполните `Start-Job` командлет, чтобы запустить любое запланированное задание.
- Добавьте в команду параметр **RunNow** , `Register-ScheduledJob` чтобы запустить задание сразу же после выполнения команды.

Задания, запускаемые с помощью `Start-Job` командлета, являются стандартными фоновыми заданиями PowerShell, а не экземплярами запланированного задания. Как и все фоновые задания, эти задания запускаются немедленно, они не подчиняются параметрам задания или не зависят от триггеров заданий. Выходные данные задания не сохраняются в **выходном** каталоге каталога запланированных заданий.

Следующая команда использует параметр **DefinitionName** `Start-Job` командлета для запуска запланированного задания процессжоб.

```powershell
Start-Job -DefinitionName ProcessJob
```

Для управления заданием и получения результатов задания используйте командлеты задания. Дополнительные сведения о командлетах заданий см. в разделе [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md).

> [!NOTE]
> Чтобы использовать командлеты задания для экземпляров запланированных заданий, необходимо импортировать модуль **PSScheduledJob** в сеанс. Чтобы импортировать модуль **PSScheduledJob** , введите `Import-Module PSScheduledJob` или используйте любой командлет запланированного задания, например `Get-ScheduledJob` .

## <a name="rename-a-scheduled-job"></a>Переименование запланированного задания

Чтобы переименовать запланированное задание, используйте параметр name `Set-ScheduledJob` командлета. При переименовании запланированного задания PowerShell изменяет имя запланированного задания и каталог запланированных заданий. Однако они не изменяют имена уже выполненных экземпляров запланированного задания.

## <a name="get-start-and-end-times"></a>Получение времени начала и окончания

Чтобы получить даты и время начала и окончания работы экземпляров заданий, используйте свойства **псбегинтиме** и **псендтиме** объекта ScheduledJob, который `Get-Job` возвращает для запланированных заданий.

В следующем примере используется параметр **Property** `Format-Table` командлета для вывода свойств **псбегинтиме** и **псендтиме** каждого экземпляра задания в таблице. Вычисляемое свойство с именем **Label** отображает время, прошедшее с момента выполнения каждого экземпляра задания.

```powershell
Get-job -Name UpdateHelpJob | 
  Format-Table -Property ID, PSBeginTime, PSEndTime,
@{Label="Elapsed Time";Expression={$.PsEndTime - $.PSBeginTime}}
```

```Output
Id   PSBeginTime             PSEndTime                Elapsed Time
--   -----------             ---------                ------------
 2   11/3/2011 3:00:01 AM    11/3/2011 3:00:39 AM     00:00:38.0053854
 3   11/4/2011 3:00:02 AM    11/4/2011 3:01:01 AM     00:00:59.1188475
 4   11/5/2011 3:00:02 AM    11/5/2011 3:00:50 AM     00:00:48.3692034
 5   11/6/2011 3:00:01 AM    11/6/2011 3:00:54 AM     00:00:52.8013036
 6   11/7/2011 3:00:01 AM    11/7/2011 3:00:38 AM     00:00:37.1930350
 7   11/8/2011 3:00:01 AM    11/8/2011 3:00:57 AM     00:00:56.2570556
 8   11/9/2011 3:00:03 AM    11/9/2011 3:00:55 AM     00:00:51.8142222
 9   11/10/2011 3:00:02 AM   11/10/2011 3:00:42 AM    00:00:40.7195954
```

## <a name="manage-execution-history"></a>Управление журналом выполнения

Можно определить количество результатов экземпляра задания, сохраняемых для каждого запланированного задания, а также удалить журнал выполнения и результаты сохраненных заданий для всех запланированных заданий.

Свойство **ексекутионхисториленгс** запланированного задания определяет, сколько результатов экземпляра задания сохраняется для запланированного задания. Если число сохраненных результатов превышает значение свойства **ексекутионхисториленгс** , PowerShell удаляет результаты самого старого экземпляра, чтобы освободить место для результатов последнего экземпляра.

По умолчанию PowerShell сохраняет журнал выполнения и результаты для 32 экземпляров каждого запланированного задания. Чтобы изменить это значение, используйте параметры **максресулткаунт** `Register-ScheduledJob` `Set-ScheduledJob` командлетов или.

Чтобы удалить журнал выполнения и все результаты для запланированного задания, используйте параметр **клеарексекутионхистори** `Set-ScheduledJob` командлета. Удаление этого журнала выполнения не мешает PowerShell сохранять результаты новых экземпляров запланированного задания.

В следующем примере Сплаттинг используется для создания `$JobParms` значений параметров, которые передаются в `Register-ScheduledJob` командлет. Дополнительные сведения см. в разделе [about_Splatting. md](../../Microsoft.PowerShell.Core/About/about_Splatting.md).
`Register-ScheduledJob`Использует `@JobParms` для создания запланированного задания. Команда использует параметр **максресулткаунт** со значением 12, чтобы сохранить только 12 самых последних экземпляров задания запланированного задания.

```powershell
$JobParms = @{
  Name = "ProcessJob"
  ScriptBlock = {Get-Process}
  MaxResultCount = "12"
}

Register-ScheduledJob @JobParms
```

Следующая команда использует параметр **максресулткаунт** `Set-ScheduledJob` командлета для увеличения числа сохраненных результатов экземпляра до
15.

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -MaxResultCount 15
```

Следующая команда удаляет журнал выполнения и текущие сохраненные результаты запланированного задания **процессжоб** .

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -ClearExecutionHistory
```

Следующая команда возвращает значения свойств Name и **ексекутионхисториленгс** всех запланированных заданий на компьютере и отображает их в таблице.

```powershell
Get-ScheduledJob | 
  Format-Table -Property Name, ExecutionHistoryLength -AutoSize
```

## <a name="see-also"></a>См. также статью

[about_Scheduled_Jobs_Basics](about_Scheduled_Jobs_Basics.md)

[about_Scheduled_Jobs_Troubleshooting](about_Scheduled_Jobs_Troubleshooting.md)

[about_Scheduled_Jobs](about_Scheduled_Jobs.md)

[about_Splatting. md](../../Microsoft.PowerShell.Core/About/about_Splatting.md)

Командлеты модуля [PSScheduledJob](xref:PSScheduledJob)

[Планировщик заданий](/windows/desktop/TaskSchd/task-scheduler-reference)
