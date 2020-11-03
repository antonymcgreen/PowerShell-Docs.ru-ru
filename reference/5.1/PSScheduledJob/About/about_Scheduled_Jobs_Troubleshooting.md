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
# <a name="about-scheduled-jobs-troubleshooting"></a><span data-ttu-id="bfb5a-104">Сведения об устранении неполадок запланированных заданий</span><span class="sxs-lookup"><span data-stu-id="bfb5a-104">About Scheduled Jobs Troubleshooting</span></span>

## <a name="short-description"></a><span data-ttu-id="bfb5a-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="bfb5a-105">Short description</span></span>

<span data-ttu-id="bfb5a-106">Способы устранения проблем с запланированными заданиями</span><span class="sxs-lookup"><span data-stu-id="bfb5a-106">Explains how to resolve problems with scheduled jobs</span></span>

## <a name="long-description"></a><span data-ttu-id="bfb5a-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="bfb5a-107">Long description</span></span>

<span data-ttu-id="bfb5a-108">В этом документе описываются некоторые проблемы, которые могут возникнуть при использовании функций запланированных заданий PowerShell, и предлагаются решения этих проблем.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-108">This document describes some of the problems that you might experience when using the scheduled job features of PowerShell and it suggests solutions to these problems.</span></span>

<span data-ttu-id="bfb5a-109">Перед использованием запланированных заданий PowerShell см. раздел [about_Scheduled_Jobs](about_Scheduled_Jobs.md) и связанные запланированные задания о разделах.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-109">Before using PowerShell scheduled jobs, see [about_Scheduled_Jobs](about_Scheduled_Jobs.md) and the related scheduled jobs about topics.</span></span>

<span data-ttu-id="bfb5a-110">Дополнительные сведения о командлетах, содержащихся в модуле **PSScheduledJob** , см. в разделе [PSScheduledJob](xref:PSScheduledJob).</span><span class="sxs-lookup"><span data-stu-id="bfb5a-110">For more information about the cmdlets contained in the **PSScheduledJob** module, see [PSScheduledJob](xref:PSScheduledJob).</span></span>

## <a name="cant-find-job-results"></a><span data-ttu-id="bfb5a-111">Не удается найти результаты задания</span><span class="sxs-lookup"><span data-stu-id="bfb5a-111">Can't find job results</span></span>

### <a name="basic-method-for-getting-job-results-in-powershell"></a><span data-ttu-id="bfb5a-112">Базовый метод получения результатов задания в PowerShell</span><span class="sxs-lookup"><span data-stu-id="bfb5a-112">Basic method for getting job results in PowerShell</span></span>

<span data-ttu-id="bfb5a-113">При выполнении запланированного задания создается экземпляр запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-113">When a scheduled job runs, it creates an instance of the scheduled job.</span></span> <span data-ttu-id="bfb5a-114">Для просмотра, управления и получения результатов экземпляров запланированных заданий используйте командлеты задания.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-114">To view, manage, and get the results of scheduled job instances, use the Job cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="bfb5a-115">Чтобы использовать командлеты задания для экземпляров запланированных заданий, необходимо импортировать модуль **PSScheduledJob** в сеанс.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-115">To use the Job cmdlets on instances of scheduled jobs, the **PSScheduledJob** module must be imported into the session.</span></span> <span data-ttu-id="bfb5a-116">Чтобы импортировать модуль **PSScheduledJob** , введите `Import-Module PSScheduledJob` или используйте любой командлет запланированного задания, например `Get-ScheduledJob` .</span><span class="sxs-lookup"><span data-stu-id="bfb5a-116">To import the **PSScheduledJob** module, type `Import-Module PSScheduledJob` or use any scheduled job cmdlet, such as `Get-ScheduledJob`.</span></span>

<span data-ttu-id="bfb5a-117">Чтобы получить список всех экземпляров запланированного задания, используйте `Get-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-117">To get a list of all instances of a scheduled job, use the `Get-Job` cmdlet.</span></span>

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

<span data-ttu-id="bfb5a-118">`Get-Job`Командлет отправляет объекты **процессжоб** вниз по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-118">The `Get-Job` cmdlet sends **ProcessJob** objects down the pipeline.</span></span> <span data-ttu-id="bfb5a-119">`Format-Table`Командлет отображает свойства **Name** , **ID** и **псбегинтиме** экземпляра запланированного задания в таблице.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-119">The `Format-Table` cmdlet displays the **Name** , **ID** , and **PSBeginTime** properties of a scheduled job instance in a table.</span></span>

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

<span data-ttu-id="bfb5a-120">Чтобы получить результаты экземпляра запланированного задания, используйте `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-120">To get the results of an instance of a scheduled job, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="bfb5a-121">Следующая команда возвращает результаты последнего экземпляра Процессжоб (ID = 50).</span><span class="sxs-lookup"><span data-stu-id="bfb5a-121">The following command gets the results of the newest instance of the ProcessJob (ID = 50).</span></span>

```powershell
Receive-Job -ID 50
```

### <a name="basic-method-for-finding-job-results-on-disk"></a><span data-ttu-id="bfb5a-122">Базовый метод поиска результатов задания на диске</span><span class="sxs-lookup"><span data-stu-id="bfb5a-122">Basic method for finding job results on disk</span></span>

<span data-ttu-id="bfb5a-123">Для управления запланированными заданиями используйте командлеты задания, такие как `Get-Job` и `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="bfb5a-123">To manage scheduled jobs, use the job cmdlets, such as `Get-Job` and `Receive-Job`.</span></span>

<span data-ttu-id="bfb5a-124">Если не `Get-Job` получает экземпляр задания или не `Receive-Job` получает результаты задания, можно выполнить поиск в файлах журнала выполнения задания на диске.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-124">If `Get-Job` does not get the job instance or `Receive-Job` does not get the job results, you can search the execution history files for the job on disk.</span></span>
<span data-ttu-id="bfb5a-125">Журнал выполнения содержит записи всех запущенных экземпляров задания.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-125">The execution history contains a record of all triggered job instances.</span></span>

<span data-ttu-id="bfb5a-126">Убедитесь, что в каталоге для запланированного задания существует каталог timestamp-Name, по следующему пути:</span><span class="sxs-lookup"><span data-stu-id="bfb5a-126">Verify that there is a timestamp-named directory in the directory for a scheduled job in the following path:</span></span>

`$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJob\<ScheduledJobName>\Output`

<span data-ttu-id="bfb5a-127">Пример:</span><span class="sxs-lookup"><span data-stu-id="bfb5a-127">For example:</span></span>

`C:\Users<UserName>\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJob\<ScheduledJobName>\Output`

<span data-ttu-id="bfb5a-128">Например, `Get-ChildItem` командлет возвращает историю выполнения на диске запланированного задания **процессжоб** .</span><span class="sxs-lookup"><span data-stu-id="bfb5a-128">For example, the `Get-ChildItem` cmdlet gets the on-disk execution history of the **ProcessJob** scheduled job.</span></span>

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

<span data-ttu-id="bfb5a-129">Каждый именованный каталог timestamp представляет экземпляр задания.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-129">Each timestamp-named directory represents a job instance.</span></span> <span data-ttu-id="bfb5a-130">Результаты каждого экземпляра задания сохраняются в файле **Results.xml** в каталоге timestamp-Name.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-130">The results of each job instance are saved in a **Results.xml** file in the timestamp-named directory.</span></span>

<span data-ttu-id="bfb5a-131">Например, следующая команда возвращает файлы **Results.xml** для каждого сохраненного экземпляра запланированного задания **процессжоб** .</span><span class="sxs-lookup"><span data-stu-id="bfb5a-131">For example, the following command gets the **Results.xml** files for every saved instance of the **ProcessJob** scheduled job.</span></span> <span data-ttu-id="bfb5a-132">Если файл **Results.xml** отсутствует, PowerShell не может вернуть или отобразить результаты задания.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-132">If the **Results.xml** file is missing, PowerShell cannot return or display the job results.</span></span>

```powershell
$Path = '$home\AppData\Local\Microsoft\Windows\PowerShell'
$Path += '\ScheduledJobs\ProcessJob\Output\*\Results.xml'
Get-ChildItem $Path
```

```Output
Directory: C:\Users\User01\Appdata\Local\Microsoft\Windows\PowerShell
               \ScheduledJobs\ProcessJob\Output
```

<span data-ttu-id="bfb5a-133">Командлет задания не может получить экземпляры запланированных заданий или их результаты, так как модуль **PSScheduledJob** не импортируется в сеанс.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-133">The job cmdlet might not be able to get scheduled job instances or their results because the **PSScheduledJob** module is not imported into the session.</span></span>

> [!NOTE]
> <span data-ttu-id="bfb5a-134">Перед использованием командлета задания в экземплярах запланированных заданий убедитесь, что модуль **PSScheduledJob** включен в сеанс.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-134">Before using a job cmdlet on scheduled job instances, verify that the **PSScheduledJob** module is included in the session.</span></span> <span data-ttu-id="bfb5a-135">Без модуля **PSScheduledJob** командлеты задания не могут получать экземпляры запланированных заданий или их результаты.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-135">Without the **PSScheduledJob** module, the job cmdlets cannot get scheduled job instances or their results.</span></span>

<span data-ttu-id="bfb5a-136">Чтобы импортировать модуль **PSScheduledJob** , выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-136">To import the **PSScheduledJob** module:</span></span>

```powershell
Import-Module PSScheduledJob
```

### <a name="receive-job-cmdlet-might-already-have-returned-the-results"></a><span data-ttu-id="bfb5a-137">Возможно, Receive-Job командлет уже вернул результаты.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-137">Receive-Job cmdlet might already have returned the results</span></span>

<span data-ttu-id="bfb5a-138">Если не `Receive-Job` возвращает результаты экземпляра задания, это может быть вызвано тем, что `Receive-Job` команда была запущена для этого экземпляра задания в текущем сеансе без параметра **сохранения** .</span><span class="sxs-lookup"><span data-stu-id="bfb5a-138">If `Receive-Job` does not return job instance results, it might be because a `Receive-Job` command has been run for that job instance in the current session without the **Keep** parameter.</span></span>

<span data-ttu-id="bfb5a-139">При использовании `Receive-Job` без параметра **сохранения** `Receive-Job` возвращает результаты задания и задает для свойства **хасморедата** экземпляра задания **значение false**.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-139">When you use `Receive-Job` without the **Keep** parameter, `Receive-Job` returns the job results and sets the job instance's **HasMoreData** property to **False**.</span></span> <span data-ttu-id="bfb5a-140">Значение **false** означает, что `Receive-Job` вернул результаты задания, а экземпляр больше не возвращает результаты.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-140">The **False** value means that `Receive-Job` returned the job's results and the instance has no more results to return.</span></span> <span data-ttu-id="bfb5a-141">Этот параметр подходит для стандартных фоновых заданий, но не для экземпляров запланированных заданий, которые сохраняются на диске.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-141">This setting is appropriate for standard background jobs, but not for instances of scheduled jobs, which are saved to disk.</span></span>

<span data-ttu-id="bfb5a-142">Чтобы снова получить результаты экземпляра задания, запустите новый сеанс PowerShell, введя команду `PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="bfb5a-142">To get the job instance results again, start a new PowerShell session by typing `PowerShell`.</span></span> <span data-ttu-id="bfb5a-143">Импортируйте модуль **PSScheduledJob** и повторите `Receive-Job` команду.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-143">Import the **PSScheduledJob** module, and try the `Receive-Job` command again.</span></span>

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

### <a name="using-keep-parameter-to-get-results-more-than-one-time-in-a-session"></a><span data-ttu-id="bfb5a-144">Использование параметра "удержать" для получения результатов более одного раза в сеансе</span><span class="sxs-lookup"><span data-stu-id="bfb5a-144">Using Keep parameter to get results more than one time in a session</span></span>

<span data-ttu-id="bfb5a-145">Чтобы получить результат экземпляра задания более одного раза в сеансе, используйте параметр **сохранения** `Receive-Job` командлета.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-145">To get the result of a job instance more than one time in a session, use the **Keep** parameter of the `Receive-Job` cmdlet.</span></span>

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

### <a name="the-scheduled-job-might-be-corrupted"></a><span data-ttu-id="bfb5a-146">Запланированное задание может быть повреждено</span><span class="sxs-lookup"><span data-stu-id="bfb5a-146">The scheduled job might be corrupted</span></span>

<span data-ttu-id="bfb5a-147">Если запланированное задание будет повреждено, PowerShell удалит поврежденное запланированное задание и его результаты.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-147">If a scheduled job becomes corrupted, PowerShell deletes the corrupted scheduled job and its results.</span></span> <span data-ttu-id="bfb5a-148">Невозможно восстановить результаты поврежденного запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-148">You cannot recover the results of a corrupted scheduled job.</span></span>

<span data-ttu-id="bfb5a-149">Чтобы определить, существует ли по-прежнему запланированное задание, используйте `Get-ScheduledJob` командлет.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-149">To determine if a scheduled job still exists, use the `Get-ScheduledJob` cmdlet.</span></span>

```powershell
Get-ScheduledJob
```

### <a name="the-number-of-results-might-have-exceeded-the-executionhistorylength"></a><span data-ttu-id="bfb5a-150">Возможно, число результатов превысило Ексекутионхисториленгс</span><span class="sxs-lookup"><span data-stu-id="bfb5a-150">The number of results might have exceeded the ExecutionHistoryLength</span></span>

<span data-ttu-id="bfb5a-151">Свойство **ексекутионхисториленгс** запланированного задания определяет, сколько экземпляров задания и их результаты сохраняются на диске.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-151">The **ExecutionHistoryLength** property of a scheduled job determines how many job instances, and their results, are saved to disk.</span></span> <span data-ttu-id="bfb5a-152">Значение по умолчанию: 32.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-152">The default value is 32.</span></span>
<span data-ttu-id="bfb5a-153">Когда количество экземпляров запланированного задания превышает это значение, PowerShell удаляет самый старый экземпляр задания, чтобы освободить место для каждого нового экземпляра задания.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-153">When the number of instances of a scheduled job exceeds this value, PowerShell deletes the oldest job instance to make room for each new job instance.</span></span>

<span data-ttu-id="bfb5a-154">Чтобы получить значение свойства **ексекутионхисториленгс** запланированного задания, используйте следующий формат команды:</span><span class="sxs-lookup"><span data-stu-id="bfb5a-154">To get the value of the **ExecutionHistoryLength** property of a scheduled job, use the following command format:</span></span>

```powershell
(Get-ScheduledJob <JobName>).ExecutionHistoryLength
```

<span data-ttu-id="bfb5a-155">Например, следующая команда возвращает значение свойства **ексекутионхисториленгс** запланированного задания **процессжоб** .</span><span class="sxs-lookup"><span data-stu-id="bfb5a-155">For example, the following command gets the value of the **ExecutionHistoryLength** property of the **ProcessJob** scheduled job.</span></span>

```powershell
(Get-ScheduledJob ProcessJob).ExecutionHistoryLength
```

<span data-ttu-id="bfb5a-156">Чтобы задать или изменить значение свойства **ексекутионхисториленгс** , используйте параметр **максресулткаунт** `Register-ScheduledJob` `Set-ScheduledJob` командлетов и.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-156">To set or change the value of the **ExecutionHistoryLength** property, use the **MaxResultCount** parameter of the `Register-ScheduledJob` and `Set-ScheduledJob` cmdlets.</span></span>

<span data-ttu-id="bfb5a-157">Следующая команда увеличивает значение свойства **ексекутионхисториленгс** на 50.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-157">The following command increases the value of the **ExecutionHistoryLength** property to 50.</span></span>

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -MaxResultCount 50
```

### <a name="the-job-instance-results-might-have-been-deleted"></a><span data-ttu-id="bfb5a-158">Возможно, результаты экземпляра задания были удалены.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-158">The job instance results might have been deleted</span></span>

<span data-ttu-id="bfb5a-159">Параметр **клеарексекутионхистори** `Set-ScheduledJob` командлета удаляет историю выполнения задания.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-159">The **ClearExecutionHistory** parameter of the `Set-ScheduledJob` cmdlet deletes the execution history of a job.</span></span> <span data-ttu-id="bfb5a-160">Эту функцию можно использовать для высвобождения места на диске или для удаления ненужных или уже использованных, проанализированных или сохраненных в другом расположениях.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-160">You can use this feature to free up disk space or delete results that are not needed, or already used, analyzed or saved in a different location.</span></span>

<span data-ttu-id="bfb5a-161">Чтобы удалить журнал выполнения запланированного задания, используйте параметр **клеарексекутионхистори** запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-161">To delete the execution history of a scheduled job, use the **ClearExecutionHistory** parameter of the scheduled job.</span></span>

<span data-ttu-id="bfb5a-162">Следующая команда удаляет журнал выполнения запланированного задания **процессжоб** .</span><span class="sxs-lookup"><span data-stu-id="bfb5a-162">The following command deletes the execution history of the **ProcessJob** scheduled job.</span></span>

```powershell
Get-ScheduledJob ProcessJob | Set-ScheduledJob -ClearExecutionHistory
```

<span data-ttu-id="bfb5a-163">Кроме того, `Remove-Job` командлет удаляет результаты задания.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-163">Also, the `Remove-Job` cmdlet deletes job results.</span></span> <span data-ttu-id="bfb5a-164">При использовании `Remove-Job` для удаления запланированного задания он удаляет все экземпляры задания на диске, включая журнал выполнения и все результаты задания.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-164">When you use `Remove-Job` to delete a scheduled job, it deletes all instances of the job on disk, including the execution history and all job results.</span></span>

### <a name="jobs-started-by-using-the-start-job-cmdlet-are-not-saved-to-disk"></a><span data-ttu-id="bfb5a-165">Задания, запущенные с помощью командлета Start-Job, не сохраняются на диске</span><span class="sxs-lookup"><span data-stu-id="bfb5a-165">Jobs started by using the Start-Job cmdlet are not saved to disk</span></span>

<span data-ttu-id="bfb5a-166">При использовании `Start-Job` для запуска запланированного задания вместо использования триггера задания `Start-Job` запускает стандартное фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-166">When you use `Start-Job` to start a scheduled job, instead of using a job trigger, `Start-Job` starts a standard background job.</span></span> <span data-ttu-id="bfb5a-167">Фоновое задание и его результаты не сохраняются в журнале выполнения задания на диске.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-167">The background job and its results are not stored in the execution history of the job on disk.</span></span>

<span data-ttu-id="bfb5a-168">С помощью `Get-Job` командлета можно получить задание и `Receive-Job` командлет для получения результатов задания, но результаты будут доступны только до тех пор, пока не будет использован параметр сохранения `Receive-Job` командлета.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-168">You can use the `Get-Job` cmdlet to get the job and the `Receive-Job` cmdlet to get the job results, but the results are available only until you receive them, unless you use the Keep parameter of the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="bfb5a-169">Кроме того, фоновые задания и их результаты относятся к конкретному сеансу. они существуют только в сеансе, в котором они созданы.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-169">Also, background jobs and their results are session-specific; they exist only in the session in which they are created.</span></span> <span data-ttu-id="bfb5a-170">Если вы удалите задание с помощью `Remove-Job` , закройте сеанс или закройте PowerShell, экземпляр задания и его результаты будут удалены.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-170">If you delete the job with `Remove-Job`, close the session or close PowerShell, the job instance and its results are deleted.</span></span>

## <a name="scheduled-job-doesnt-run"></a><span data-ttu-id="bfb5a-171">Запланированное задание не выполняется</span><span class="sxs-lookup"><span data-stu-id="bfb5a-171">Scheduled job doesn't run</span></span>

<span data-ttu-id="bfb5a-172">Запланированные задания не выполняются автоматически, если триггер задания или запланированное задание отключены.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-172">Scheduled jobs don't run automatically if the job triggers or the scheduled job are disabled.</span></span>

<span data-ttu-id="bfb5a-173">Используйте `Get-ScheduledJob` командлет для получения запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-173">Use the `Get-ScheduledJob` cmdlet to get the scheduled job.</span></span> <span data-ttu-id="bfb5a-174">Убедитесь, что для свойства **Enabled** запланированного задания задано значение **true**.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-174">Verify that the value of the **Enabled** property of the scheduled job is **True**.</span></span>

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

<span data-ttu-id="bfb5a-175">Используйте `Get-JobTrigger` командлет, чтобы получить триггеры задания для запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-175">Use the `Get-JobTrigger` cmdlet to get the job triggers of the scheduled job.</span></span>
<span data-ttu-id="bfb5a-176">Убедитесь, что для свойства **Enabled** триггера задания задано значение **true**.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-176">Verify that the value of the **Enabled** property of the job trigger is **True**.</span></span>

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

### <a name="scheduled-jobs-dont-run-automatically-if-job-triggers-are-invalid"></a><span data-ttu-id="bfb5a-177">Запланированные задания не выполняются автоматически, если триггеры заданий недопустимы</span><span class="sxs-lookup"><span data-stu-id="bfb5a-177">Scheduled jobs don't run automatically if job triggers are invalid</span></span>

<span data-ttu-id="bfb5a-178">Например, триггер задания может указывать дату в прошлом или дату, которая не возникает, например 5-й понедельник месяца.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-178">For example, a job trigger might specify a date in the past or a date that does not occur, such as the 5th Monday of the month.</span></span>

<span data-ttu-id="bfb5a-179">Запланированные задания не выполняются автоматически, если условия триггера задания или задания не выполнены.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-179">Scheduled jobs do not run automatically if the conditions of the job trigger or the job options are not satisfied.</span></span>

<span data-ttu-id="bfb5a-180">Например, запланированное задание, выполняемое только в том случае, если конкретный пользователь входит в систему, не будет работать, если он не вошел в систему или удаленно подключается.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-180">For example, a scheduled job that runs only when a particular user logs on to the computer will not run if that user does not log on or only connects remotely.</span></span>

<span data-ttu-id="bfb5a-181">Проверьте параметры запланированного задания и убедитесь, что они удовлетворены.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-181">Examine the options of the scheduled job and make sure that they are satisfied.</span></span>
<span data-ttu-id="bfb5a-182">Например, запланированное задание требует, чтобы компьютер был неактивен или для него требуется сетевое подключение, или он имеет длительное **идледуратион** или короткое значение **IdleTimeout** не может быть запущено.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-182">For example, a scheduled job that requires that the computer be idle or requires a network connection, or has a long **IdleDuration** or a brief **IdleTimeout** might never run.</span></span>

<span data-ttu-id="bfb5a-183">С помощью `Get-ScheduledJobOption` командлета проверьте параметры задания и их значения.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-183">Use the `Get-ScheduledJobOption` cmdlet to examine the job options and their values.</span></span>

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

<span data-ttu-id="bfb5a-184">Описание параметров запланированного задания см. в разделе [New-scheduledjoboptions](xref:PSScheduledJob.New-ScheduledJobOption).</span><span class="sxs-lookup"><span data-stu-id="bfb5a-184">For descriptions of the scheduled job options, see [New-ScheduledJobOption](xref:PSScheduledJob.New-ScheduledJobOption).</span></span>

### <a name="the-scheduled-job-instance-might-have-failed"></a><span data-ttu-id="bfb5a-185">Возможно, произошел сбой экземпляра запланированного задания</span><span class="sxs-lookup"><span data-stu-id="bfb5a-185">The scheduled job instance might have failed</span></span>

<span data-ttu-id="bfb5a-186">Если команда запланированного задания завершается сбоем, PowerShell немедленно сообщает о ней, выполнив сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-186">If a scheduled job command fails, PowerShell reports it immediately by generating an error message.</span></span> <span data-ttu-id="bfb5a-187">Однако если задание завершается сбоем, когда планировщик задач пытается запуститься, эта ошибка недоступна для PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-187">However, if the job fails when Task Scheduler tries to run it, the error is not available to PowerShell.</span></span>

<span data-ttu-id="bfb5a-188">Для обнаружения и исправления ошибок заданий используйте следующие методы.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-188">Use the following methods to detect and correct job failures:</span></span>

<span data-ttu-id="bfb5a-189">Проверьте журнал событий планировщик задач на наличие ошибок.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-189">Check the Task Scheduler event log for errors.</span></span> <span data-ttu-id="bfb5a-190">Чтобы проверить журнал, используйте Просмотр событий или команду PowerShell, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-190">To check the log, use Event Viewer or a PowerShell command such as the following:</span></span>

```powershell
Get-WinEvent -LogName Microsoft-Windows-TaskScheduler/Operational |
 Where {$_.Message -like "fail"}
```

<span data-ttu-id="bfb5a-191">Проверьте запись задания в планировщик задач.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-191">Check the job record in Task Scheduler.</span></span> <span data-ttu-id="bfb5a-192">Запланированные задания PowerShell хранятся в следующей запланированной папке задачи:</span><span class="sxs-lookup"><span data-stu-id="bfb5a-192">PowerShell scheduled jobs are stored in the following Task Scheduled folder:</span></span>

`Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs`

### <a name="the-scheduled-job-might-not-run-because-of-insufficient-permission"></a><span data-ttu-id="bfb5a-193">Запланированное задание может не запускаться из-за недостаточных разрешений</span><span class="sxs-lookup"><span data-stu-id="bfb5a-193">The scheduled job might not run because of insufficient permission</span></span>

<span data-ttu-id="bfb5a-194">Запланированные задания выполняются с разрешениями пользователя, создавшего задание, или разрешений пользователя, заданного параметром **Credential** в `Register-ScheduledJob` `Set-ScheduledJob` команде или.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-194">Scheduled jobs run with the permissions of the user who created the job or the permissions of the user who is specified by the **Credential** parameter in the `Register-ScheduledJob` or `Set-ScheduledJob` command.</span></span>

<span data-ttu-id="bfb5a-195">Если у этого пользователя нет разрешения на выполнение команд или сценариев, задание завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-195">If that user does not have permission to run the commands or scripts, the job fails.</span></span>

## <a name="cant-get-scheduled-job-or-scheduled-job-is-corrupted"></a><span data-ttu-id="bfb5a-196">Не удается получить расписание или запланированное задание, так как оно повреждено</span><span class="sxs-lookup"><span data-stu-id="bfb5a-196">Can't get scheduled job or scheduled job is corrupted</span></span>

<span data-ttu-id="bfb5a-197">В редких случаях запланированные задания могут быть повреждены или содержать внутренние противоречия, которые не могут быть разрешены.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-197">On rare occasions, scheduled jobs can become corrupted or contain internal contradictions that cannot be resolved.</span></span> <span data-ttu-id="bfb5a-198">Как правило, это происходит, когда XML-файлы для запланированного задания редактируются вручную, что приводит к неправильному XML.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-198">Typically, this happens when the XML files for the scheduled job are manually edited, resulting in invalid XML.</span></span>

<span data-ttu-id="bfb5a-199">При повреждении запланированного задания PowerShell пытается удалить запланированное задание, его историю выполнения и результаты с диска.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-199">When a scheduled job is corrupted, PowerShell attempts to delete the scheduled job, its execution history, and its results from disk.</span></span>

<span data-ttu-id="bfb5a-200">Если не удается удалить запланированное задание, при каждом запуске командлета будет выводится поврежденное сообщение об ошибке задания `Get-ScheduledJob` .</span><span class="sxs-lookup"><span data-stu-id="bfb5a-200">If it cannot remove the scheduled job, you will get a corrupted job error message each time you run the `Get-ScheduledJob` cmdlet.</span></span>

<span data-ttu-id="bfb5a-201">Чтобы удалить поврежденное запланированное задание, используйте один из следующих методов.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-201">To remove a corrupted scheduled job, use either one of the following methods:</span></span>

<span data-ttu-id="bfb5a-202">Удалите `<ScheduledJobName>` каталог для запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-202">Delete the `<ScheduledJobName>` directory for the scheduled job.</span></span> <span data-ttu-id="bfb5a-203">Не удаляйте каталог **ScheduledJob** .</span><span class="sxs-lookup"><span data-stu-id="bfb5a-203">Don't delete the **ScheduledJob** directory.</span></span>

<span data-ttu-id="bfb5a-204">Расположение каталога:</span><span class="sxs-lookup"><span data-stu-id="bfb5a-204">The directory's location:</span></span>

`$env:UserProfile\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs<ScheduledJobName>`

<span data-ttu-id="bfb5a-205">Пример:</span><span class="sxs-lookup"><span data-stu-id="bfb5a-205">For example:</span></span>

`C:\Users<UserName>\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs<ScheduledJobName>.`

<span data-ttu-id="bfb5a-206">Чтобы удалить запланированное задание, используйте планировщик задач.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-206">Use Task Scheduler to delete the scheduled job.</span></span> <span data-ttu-id="bfb5a-207">Запланированные задачи PowerShell отображаются в следующем планировщик задач пути:</span><span class="sxs-lookup"><span data-stu-id="bfb5a-207">PowerShell scheduled tasks appear in the following Task Scheduler path:</span></span>

`Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs<ScheduledJobName>`

## <a name="job-cmdlets-cant-consistently-find-scheduled-jobs"></a><span data-ttu-id="bfb5a-208">Командлеты задания не могут постоянно находить запланированные задания</span><span class="sxs-lookup"><span data-stu-id="bfb5a-208">Job cmdlets can't consistently find scheduled jobs</span></span>

<span data-ttu-id="bfb5a-209">Если модуль **PSScheduledJob** не находится в текущем сеансе, командлеты задания не могут получать запланированные задания, запускать их или получать результаты.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-209">When the **PSScheduledJob** module isn't in the current session, the job cmdlets cannot get scheduled jobs, start them, or get their results.</span></span>

<span data-ttu-id="bfb5a-210">Чтобы импортировать модуль **PSScheduledJob** , введите `Import-Module PSScheduledJob` или запустите или получите любой командлет в модуле, например `Get-ScheduledJob` командлет.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-210">To import the **PSScheduledJob** module, type `Import-Module PSScheduledJob` or run or get any cmdlet in the module, such as the `Get-ScheduledJob` cmdlet.</span></span>
<span data-ttu-id="bfb5a-211">Начиная с PowerShell 3,0 модули импортируются автоматически при получении или использовании любого командлета в модуле.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-211">Beginning in PowerShell 3.0, modules are imported automatically when you get or use any cmdlet in the module.</span></span>

<span data-ttu-id="bfb5a-212">Если модуль **PSScheduledJob** не находится в текущем сеансе, возможно, используется следующая последовательность команд.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-212">When the **PSScheduledJob** module isn't in the current session, the following command sequence is possible.</span></span>

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

<span data-ttu-id="bfb5a-213">Это происходит потому, что `Get-ScheduledJob` команда автоматически импортирует модуль **PSScheduledJob** , а затем выполняет команду.</span><span class="sxs-lookup"><span data-stu-id="bfb5a-213">This behavior occurs because the `Get-ScheduledJob` command automatically imports the **PSScheduledJob** module, and then runs the command.</span></span>

## <a name="see-also"></a><span data-ttu-id="bfb5a-214">См. также статью</span><span class="sxs-lookup"><span data-stu-id="bfb5a-214">See also</span></span>

[<span data-ttu-id="bfb5a-215">about_Scheduled_Jobs_Basics</span><span class="sxs-lookup"><span data-stu-id="bfb5a-215">about_Scheduled_Jobs_Basics</span></span>](about_Scheduled_Jobs_Basics.md)

[<span data-ttu-id="bfb5a-216">about_Scheduled_Jobs_Advanced</span><span class="sxs-lookup"><span data-stu-id="bfb5a-216">about_Scheduled_Jobs_Advanced</span></span>](about_Scheduled_Jobs_Advanced.md)

[<span data-ttu-id="bfb5a-217">about_Scheduled_Jobs</span><span class="sxs-lookup"><span data-stu-id="bfb5a-217">about_Scheduled_Jobs</span></span>](about_Scheduled_Jobs.md)

<span data-ttu-id="bfb5a-218">Командлеты модуля [PSScheduledJob](xref:PSScheduledJob)</span><span class="sxs-lookup"><span data-stu-id="bfb5a-218">[PSScheduledJob](xref:PSScheduledJob) module cmdlets</span></span>

[<span data-ttu-id="bfb5a-219">Планировщик заданий</span><span class="sxs-lookup"><span data-stu-id="bfb5a-219">Task Scheduler</span></span>](/windows/desktop/TaskSchd/task-scheduler-reference)
