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
# <a name="about-scheduled-jobs-advanced"></a><span data-ttu-id="23e33-104">О дополнительных запланированных заданиях</span><span class="sxs-lookup"><span data-stu-id="23e33-104">About Scheduled Jobs Advanced</span></span>

## <a name="short-description"></a><span data-ttu-id="23e33-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="23e33-105">Short description</span></span>

<span data-ttu-id="23e33-106">Дополнительные разделы о запланированных заданиях, включая описание структуры файлов, лежащей в основе запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="23e33-106">Explains advanced scheduled job topics, including the file structure that underlies scheduled jobs.</span></span>

## <a name="long-description"></a><span data-ttu-id="23e33-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="23e33-107">Long description</span></span>

<span data-ttu-id="23e33-108">Дополнительные сведения о командлетах, содержащихся в модуле **PSScheduledJob** , см. в разделе [PSScheduledJob](xref:PSScheduledJob).</span><span class="sxs-lookup"><span data-stu-id="23e33-108">For more information about the cmdlets contained in the **PSScheduledJob** module, see [PSScheduledJob](xref:PSScheduledJob).</span></span>

## <a name="scheduled-job-directories-and-files"></a><span data-ttu-id="23e33-109">Каталоги и файлы запланированных заданий</span><span class="sxs-lookup"><span data-stu-id="23e33-109">Scheduled job directories and files</span></span>

<span data-ttu-id="23e33-110">Запланированные задания PowerShell — это как задания PowerShell, так и задачи планировщик задач.</span><span class="sxs-lookup"><span data-stu-id="23e33-110">PowerShell scheduled jobs are both PowerShell jobs and Task Scheduler tasks.</span></span>
<span data-ttu-id="23e33-111">Каждое запланированное задание регистрируется в планировщик задач и сохраняется на диске в формате XML сериализации Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="23e33-111">Each scheduled job is registered in Task Scheduler and saved on disk in Microsoft .NET Framework Serialization XML format.</span></span>

<span data-ttu-id="23e33-112">При создании запланированного задания PowerShell создает каталог для запланированного задания в `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` каталоге на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="23e33-112">When you create a scheduled job, PowerShell creates a directory for the scheduled job in the `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` directory on the local computer.</span></span> <span data-ttu-id="23e33-113">Имя каталога совпадает с именем задания.</span><span class="sxs-lookup"><span data-stu-id="23e33-113">The directory name is the same as the job name.</span></span>

<span data-ttu-id="23e33-114">Ниже приведен пример каталога **ScheduledJobs** .</span><span class="sxs-lookup"><span data-stu-id="23e33-114">The following is a sample **ScheduledJobs** directory.</span></span>

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

<span data-ttu-id="23e33-115">Каждое запланированное задание имеет свой собственный каталог.</span><span class="sxs-lookup"><span data-stu-id="23e33-115">Each scheduled job has its own directory.</span></span> <span data-ttu-id="23e33-116">Каталог содержит XML-файл запланированного задания и **выходной** подкаталог.</span><span class="sxs-lookup"><span data-stu-id="23e33-116">The directory contains the scheduled job XML file and an **Output** subdirectory.</span></span>

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

<span data-ttu-id="23e33-117">**Выходной** каталог для запланированного задания содержит журнал выполнения.</span><span class="sxs-lookup"><span data-stu-id="23e33-117">The **Output** directory for a scheduled job contains its execution history.</span></span>
<span data-ttu-id="23e33-118">Каждый раз, когда триггер задания запускает запланированное задание, PowerShell создает в выходном каталоге каталог с меткой времени.</span><span class="sxs-lookup"><span data-stu-id="23e33-118">Each time a job trigger starts a scheduled job, PowerShell creates a timestamp-named directory in the output directory.</span></span> <span data-ttu-id="23e33-119">Каталог меток времени содержит результаты задания в файле **Results.xml** и состояние задания в **Status.xmlном** файле.</span><span class="sxs-lookup"><span data-stu-id="23e33-119">The timestamp directory contains the results of the job in a **Results.xml** file and the job status in a **Status.xml** file.</span></span>

<span data-ttu-id="23e33-120">Следующая команда показывает каталоги журнала выполнения для запланированного задания **процессжоб** .</span><span class="sxs-lookup"><span data-stu-id="23e33-120">The following command shows the execution history directories for the **ProcessJob** scheduled job.</span></span>

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

<span data-ttu-id="23e33-121">Вы можете открывать и изучать **ScheduledJobDefinition.xml** , **Results.xml** и **Status.xml** файлы или использовать `Select-XML` командлет для анализа файлов.</span><span class="sxs-lookup"><span data-stu-id="23e33-121">You can open and examine the **ScheduledJobDefinition.xml** , **Results.xml** and **Status.xml** files or use the `Select-XML` cmdlet to parse the files.</span></span>

> [!WARNING]
> <span data-ttu-id="23e33-122">Не изменяйте XML-файлы.</span><span class="sxs-lookup"><span data-stu-id="23e33-122">Do not edit the XML files.</span></span> <span data-ttu-id="23e33-123">Если любой XML-файл содержит недопустимый XML-код, PowerShell удаляет запланированное задание и его историю выполнения, включая результаты задания.</span><span class="sxs-lookup"><span data-stu-id="23e33-123">If any XML file contains invalid XML, PowerShell deletes the scheduled job and its execution history, including job results.</span></span>

## <a name="start-a-scheduled-job-immediately"></a><span data-ttu-id="23e33-124">Немедленное запуск запланированного задания</span><span class="sxs-lookup"><span data-stu-id="23e33-124">Start a scheduled job immediately</span></span>

<span data-ttu-id="23e33-125">Вы можете немедленно запустить запланированное задание одним из двух способов:</span><span class="sxs-lookup"><span data-stu-id="23e33-125">You can start a scheduled job immediately in one of two ways:</span></span>

- <span data-ttu-id="23e33-126">Выполните `Start-Job` командлет, чтобы запустить любое запланированное задание.</span><span class="sxs-lookup"><span data-stu-id="23e33-126">Run the `Start-Job` cmdlet to start any scheduled job.</span></span>
- <span data-ttu-id="23e33-127">Добавьте в команду параметр **RunNow** , `Register-ScheduledJob` чтобы запустить задание сразу же после выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="23e33-127">Add the **RunNow** parameter to your `Register-ScheduledJob` command to start the job as soon as the command is run.</span></span>

<span data-ttu-id="23e33-128">Задания, запускаемые с помощью `Start-Job` командлета, являются стандартными фоновыми заданиями PowerShell, а не экземплярами запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="23e33-128">Jobs that are started by using the `Start-Job` cmdlet are standard PowerShell background jobs, not instances of the scheduled job.</span></span> <span data-ttu-id="23e33-129">Как и все фоновые задания, эти задания запускаются немедленно, они не подчиняются параметрам задания или не зависят от триггеров заданий.</span><span class="sxs-lookup"><span data-stu-id="23e33-129">Like all background jobs, these jobs start immediately, they aren't subject to job options or affected by job triggers.</span></span> <span data-ttu-id="23e33-130">Выходные данные задания не сохраняются в **выходном** каталоге каталога запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="23e33-130">The job output isn't saved in the **Output** directory of the scheduled job directory.</span></span>

<span data-ttu-id="23e33-131">Следующая команда использует параметр **DefinitionName** `Start-Job` командлета для запуска запланированного задания процессжоб.</span><span class="sxs-lookup"><span data-stu-id="23e33-131">The following command uses the **DefinitionName** parameter of the `Start-Job` cmdlet to start the ProcessJob scheduled job.</span></span>

```powershell
Start-Job -DefinitionName ProcessJob
```

<span data-ttu-id="23e33-132">Для управления заданием и получения результатов задания используйте командлеты задания.</span><span class="sxs-lookup"><span data-stu-id="23e33-132">To manage the job and get the job results, use the job cmdlets.</span></span> <span data-ttu-id="23e33-133">Дополнительные сведения о командлетах заданий см. в разделе [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="23e33-133">For more information about the job cmdlets, see [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md).</span></span>

> [!NOTE]
> <span data-ttu-id="23e33-134">Чтобы использовать командлеты задания для экземпляров запланированных заданий, необходимо импортировать модуль **PSScheduledJob** в сеанс.</span><span class="sxs-lookup"><span data-stu-id="23e33-134">To use the Job cmdlets on instances of scheduled jobs, the **PSScheduledJob** module must be imported into the session.</span></span> <span data-ttu-id="23e33-135">Чтобы импортировать модуль **PSScheduledJob** , введите `Import-Module PSScheduledJob` или используйте любой командлет запланированного задания, например `Get-ScheduledJob` .</span><span class="sxs-lookup"><span data-stu-id="23e33-135">To import the **PSScheduledJob** module, type `Import-Module PSScheduledJob` or use any scheduled job cmdlet, such as `Get-ScheduledJob`.</span></span>

## <a name="rename-a-scheduled-job"></a><span data-ttu-id="23e33-136">Переименование запланированного задания</span><span class="sxs-lookup"><span data-stu-id="23e33-136">Rename a scheduled job</span></span>

<span data-ttu-id="23e33-137">Чтобы переименовать запланированное задание, используйте параметр name `Set-ScheduledJob` командлета.</span><span class="sxs-lookup"><span data-stu-id="23e33-137">To rename a scheduled job, use the Name parameter of the `Set-ScheduledJob` cmdlet.</span></span> <span data-ttu-id="23e33-138">При переименовании запланированного задания PowerShell изменяет имя запланированного задания и каталог запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="23e33-138">When you rename a scheduled job, PowerShell changes the name of the scheduled job and the scheduled job directory.</span></span> <span data-ttu-id="23e33-139">Однако они не изменяют имена уже выполненных экземпляров запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="23e33-139">However, it doesn't change the names of instances of the scheduled job that have already run.</span></span>

## <a name="get-start-and-end-times"></a><span data-ttu-id="23e33-140">Получение времени начала и окончания</span><span class="sxs-lookup"><span data-stu-id="23e33-140">Get start and end times</span></span>

<span data-ttu-id="23e33-141">Чтобы получить даты и время начала и окончания работы экземпляров заданий, используйте свойства **псбегинтиме** и **псендтиме** объекта ScheduledJob, который `Get-Job` возвращает для запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="23e33-141">To get the dates and times that job instances started and ended, use the **PSBeginTime** and **PSEndTime** properties of the ScheduledJob object that `Get-Job` returns for scheduled jobs.</span></span>

<span data-ttu-id="23e33-142">В следующем примере используется параметр **Property** `Format-Table` командлета для вывода свойств **псбегинтиме** и **псендтиме** каждого экземпляра задания в таблице.</span><span class="sxs-lookup"><span data-stu-id="23e33-142">The following example uses the **Property** parameter of the `Format-Table` cmdlet to display the **PSBeginTime** and **PSEndTime** properties of each job instance in a table.</span></span> <span data-ttu-id="23e33-143">Вычисляемое свойство с именем **Label** отображает время, прошедшее с момента выполнения каждого экземпляра задания.</span><span class="sxs-lookup"><span data-stu-id="23e33-143">A calculated property named **Label** displays the elapsed time of each job instance.</span></span>

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

## <a name="manage-execution-history"></a><span data-ttu-id="23e33-144">Управление журналом выполнения</span><span class="sxs-lookup"><span data-stu-id="23e33-144">Manage execution history</span></span>

<span data-ttu-id="23e33-145">Можно определить количество результатов экземпляра задания, сохраняемых для каждого запланированного задания, а также удалить журнал выполнения и результаты сохраненных заданий для всех запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="23e33-145">You can determine the number of job instance results that are saved for each scheduled job and delete the execution history and saved job results of any scheduled job.</span></span>

<span data-ttu-id="23e33-146">Свойство **ексекутионхисториленгс** запланированного задания определяет, сколько результатов экземпляра задания сохраняется для запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="23e33-146">The **ExecutionHistoryLength** property of a scheduled job determines how many job instance results are saved for the scheduled job.</span></span> <span data-ttu-id="23e33-147">Если число сохраненных результатов превышает значение свойства **ексекутионхисториленгс** , PowerShell удаляет результаты самого старого экземпляра, чтобы освободить место для результатов последнего экземпляра.</span><span class="sxs-lookup"><span data-stu-id="23e33-147">When the number of saved results exceeds the value of the **ExecutionHistoryLength** property, PowerShell deletes the results of the oldest instance to make room for the results of the newest instance.</span></span>

<span data-ttu-id="23e33-148">По умолчанию PowerShell сохраняет журнал выполнения и результаты для 32 экземпляров каждого запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="23e33-148">By default, PowerShell saves the execution history and results of 32 instances of each scheduled job.</span></span> <span data-ttu-id="23e33-149">Чтобы изменить это значение, используйте параметры **максресулткаунт** `Register-ScheduledJob` `Set-ScheduledJob` командлетов или.</span><span class="sxs-lookup"><span data-stu-id="23e33-149">To change that value, use the **MaxResultCount** parameters of the `Register-ScheduledJob` or `Set-ScheduledJob` cmdlets.</span></span>

<span data-ttu-id="23e33-150">Чтобы удалить журнал выполнения и все результаты для запланированного задания, используйте параметр **клеарексекутионхистори** `Set-ScheduledJob` командлета.</span><span class="sxs-lookup"><span data-stu-id="23e33-150">To delete the execution history and all results for a scheduled job, use the **ClearExecutionHistory** parameter of the `Set-ScheduledJob` cmdlet.</span></span> <span data-ttu-id="23e33-151">Удаление этого журнала выполнения не мешает PowerShell сохранять результаты новых экземпляров запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="23e33-151">Deleting this execution history does not prevent PowerShell from saving the results of new instances of the scheduled job.</span></span>

<span data-ttu-id="23e33-152">В следующем примере Сплаттинг используется для создания `$JobParms` значений параметров, которые передаются в `Register-ScheduledJob` командлет.</span><span class="sxs-lookup"><span data-stu-id="23e33-152">The following example uses splatting to create `$JobParms` which are parameter values that are passed to the `Register-ScheduledJob` cmdlet.</span></span> <span data-ttu-id="23e33-153">Дополнительные сведения см. в разделе [about_Splatting. md](../../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="23e33-153">For more information, see [about_Splatting.md](../../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>
<span data-ttu-id="23e33-154">`Register-ScheduledJob`Использует `@JobParms` для создания запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="23e33-154">The `Register-ScheduledJob` uses `@JobParms` to create a scheduled job.</span></span> <span data-ttu-id="23e33-155">Команда использует параметр **максресулткаунт** со значением 12, чтобы сохранить только 12 самых последних экземпляров задания запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="23e33-155">The command uses the **MaxResultCount** parameter with a value of 12 to save only the 12 newest job instance results of the scheduled job.</span></span>

```powershell
$JobParms = @{
  Name = "ProcessJob"
  ScriptBlock = {Get-Process}
  MaxResultCount = "12"
}

Register-ScheduledJob @JobParms
```

<span data-ttu-id="23e33-156">Следующая команда использует параметр **максресулткаунт** `Set-ScheduledJob` командлета для увеличения числа сохраненных результатов экземпляра до</span><span class="sxs-lookup"><span data-stu-id="23e33-156">The following command uses the **MaxResultCount** parameter of the `Set-ScheduledJob` cmdlet to increase the number of saved instance results to</span></span>
15.

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -MaxResultCount 15
```

<span data-ttu-id="23e33-157">Следующая команда удаляет журнал выполнения и текущие сохраненные результаты запланированного задания **процессжоб** .</span><span class="sxs-lookup"><span data-stu-id="23e33-157">The following command deletes the execution history and the current saved results of the **ProcessJob** scheduled job.</span></span>

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -ClearExecutionHistory
```

<span data-ttu-id="23e33-158">Следующая команда возвращает значения свойств Name и **ексекутионхисториленгс** всех запланированных заданий на компьютере и отображает их в таблице.</span><span class="sxs-lookup"><span data-stu-id="23e33-158">The following command gets the values of the name and **ExecutionHistoryLength** properties of all scheduled jobs on the computer and displays them in a table.</span></span>

```powershell
Get-ScheduledJob | 
  Format-Table -Property Name, ExecutionHistoryLength -AutoSize
```

## <a name="see-also"></a><span data-ttu-id="23e33-159">См. также статью</span><span class="sxs-lookup"><span data-stu-id="23e33-159">See also</span></span>

[<span data-ttu-id="23e33-160">about_Scheduled_Jobs_Basics</span><span class="sxs-lookup"><span data-stu-id="23e33-160">about_Scheduled_Jobs_Basics</span></span>](about_Scheduled_Jobs_Basics.md)

[<span data-ttu-id="23e33-161">about_Scheduled_Jobs_Troubleshooting</span><span class="sxs-lookup"><span data-stu-id="23e33-161">about_Scheduled_Jobs_Troubleshooting</span></span>](about_Scheduled_Jobs_Troubleshooting.md)

[<span data-ttu-id="23e33-162">about_Scheduled_Jobs</span><span class="sxs-lookup"><span data-stu-id="23e33-162">about_Scheduled_Jobs</span></span>](about_Scheduled_Jobs.md)

[<span data-ttu-id="23e33-163">about_Splatting. md</span><span class="sxs-lookup"><span data-stu-id="23e33-163">about_Splatting.md</span></span>](../../Microsoft.PowerShell.Core/About/about_Splatting.md)

<span data-ttu-id="23e33-164">Командлеты модуля [PSScheduledJob](xref:PSScheduledJob)</span><span class="sxs-lookup"><span data-stu-id="23e33-164">[PSScheduledJob](xref:PSScheduledJob) module cmdlets</span></span>

[<span data-ttu-id="23e33-165">Планировщик заданий</span><span class="sxs-lookup"><span data-stu-id="23e33-165">Task Scheduler</span></span>](/windows/desktop/TaskSchd/task-scheduler-reference)
