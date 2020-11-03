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
# <a name="about-scheduled-jobs-basics"></a><span data-ttu-id="d8fa6-104">Общие сведения о запланированных заданиях</span><span class="sxs-lookup"><span data-stu-id="d8fa6-104">About Scheduled Jobs Basics</span></span>

## <a name="short-description"></a><span data-ttu-id="d8fa6-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="d8fa6-105">Short description</span></span>

<span data-ttu-id="d8fa6-106">Описание процедур создания запланированных заданий и управления ими.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-106">Explains how to create and manage scheduled jobs.</span></span>

## <a name="long-description"></a><span data-ttu-id="d8fa6-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="d8fa6-107">Long description</span></span>

<span data-ttu-id="d8fa6-108">В этом документе показано, как выполнять базовые задачи по созданию запланированных заданий и управлению ими.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-108">This document shows how to perform basic tasks of creating and managing scheduled jobs.</span></span> <span data-ttu-id="d8fa6-109">Дополнительные сведения о более сложных задачах см. в разделе [about_Scheduled_Jobs_Advanced](about_Scheduled_Jobs_Advanced.md).</span><span class="sxs-lookup"><span data-stu-id="d8fa6-109">For information about more advanced tasks, see [about_Scheduled_Jobs_Advanced](about_Scheduled_Jobs_Advanced.md).</span></span>

<span data-ttu-id="d8fa6-110">Дополнительные сведения о командлетах, содержащихся в модуле **PSScheduledJob** , см. в разделе [PSScheduledJob](xref:PSScheduledJob).</span><span class="sxs-lookup"><span data-stu-id="d8fa6-110">For more information about the cmdlets contained in the **PSScheduledJob** module, see [PSScheduledJob](xref:PSScheduledJob).</span></span>

## <a name="how-to-create-a-scheduled-job"></a><span data-ttu-id="d8fa6-111">Создание запланированного задания</span><span class="sxs-lookup"><span data-stu-id="d8fa6-111">How to create a scheduled job</span></span>

<span data-ttu-id="d8fa6-112">Чтобы создать запланированное задание, используйте `Register-ScheduledJob` командлет.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-112">To create a scheduled job, use the `Register-ScheduledJob` cmdlet.</span></span> <span data-ttu-id="d8fa6-113">Командлету требуется имя, а также команды или скрипт, выполняемые заданием.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-113">The cmdlet requires a name and the commands or script that the job runs.</span></span> <span data-ttu-id="d8fa6-114">Можно либо запустить задание немедленно, добавив параметр **RunNow** , либо создать триггер задания и задать параметры задания при создании задания или изменить существующее задание.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-114">You can either run the job immediately by adding the **RunNow** parameter, or create a job trigger and set job options when you create the job, or edit an existing job.</span></span>

<span data-ttu-id="d8fa6-115">Чтобы создать задание, запускающее скрипт, используйте параметр **FilePath** , чтобы указать путь к файлу скрипта.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-115">To create a job that runs a script, use the **FilePath** parameter to specify the path to the script file.</span></span> <span data-ttu-id="d8fa6-116">Чтобы создать задание, запускающее команды, используйте параметр **ScriptBlock** .</span><span class="sxs-lookup"><span data-stu-id="d8fa6-116">To create a job that runs commands, use the **ScriptBlock** parameter.</span></span>

<span data-ttu-id="d8fa6-117">`Register-ScheduledJob`Командлет создает **процессжоб** , который выполняет `Get-Process` команду.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-117">The `Register-ScheduledJob` cmdlet creates the **ProcessJob** , which runs a `Get-Process` command.</span></span> <span data-ttu-id="d8fa6-118">Это запланированное задание имеет параметры задания по умолчанию и не имеет триггера задания.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-118">This scheduled job has the default job options and no job trigger.</span></span>

```powershell
Register-ScheduledJob -Name ProcessJob -ScriptBlock { Get-Process }
```

```Output
Id         Name            Triggers        Command       Enabled
--         ----            --------        -------       -------
8          ProcessJob      {}              Get-Process   True
```

## <a name="how-to-create-a-job-trigger"></a><span data-ttu-id="d8fa6-119">Создание триггера задания</span><span class="sxs-lookup"><span data-stu-id="d8fa6-119">How to create a job trigger</span></span>

<span data-ttu-id="d8fa6-120">Триггеры заданий запускают запланированное задание автоматически.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-120">Job triggers start a scheduled job automatically.</span></span> <span data-ttu-id="d8fa6-121">Триггером задания может быть однократное или повторяющееся расписание или событие, например, когда пользователь входит в систему или запускается Windows.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-121">A job trigger can be one-time or recurring schedule or an event, such as when a user logs on or Windows starts.</span></span> <span data-ttu-id="d8fa6-122">Каждое задание может иметь ноль, один или несколько триггеров заданий.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-122">Each job can have zero, one, or multiple job triggers.</span></span>

<span data-ttu-id="d8fa6-123">Чтобы создать триггер задания, используйте `New-JobTrigger` командлет.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-123">To create a job trigger, use the `New-JobTrigger` cmdlet.</span></span> <span data-ttu-id="d8fa6-124">Следующая команда создает триггер задания, который запускает задание каждый понедельник и четверг в 5:00 AM.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-124">The following command creates a job trigger that starts a job every Monday and Thursday at 5:00 AM.</span></span>
<span data-ttu-id="d8fa6-125">Команда сохраняет триггер задания в `$T` переменной.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-125">The command saves the job trigger in the `$T` variable.</span></span>

```powershell
$T = New-JobTrigger -Weekly -DaysOfWeek "Monday", "Thursday" -At "5:00 AM"
```

<span data-ttu-id="d8fa6-126">Триггеры задания не являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-126">Job triggers are optional.</span></span> <span data-ttu-id="d8fa6-127">Вы можете запустить запланированное задание в любое время, добавив параметр **RunNow** в `Register-ScheduledJob` команду или используя `Start-Job` командлеты.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-127">You can start a scheduled job at any time by adding the **RunNow** parameter to your `Register-ScheduledJob` command, or by using the `Start-Job` cmdlets.</span></span>

## <a name="how-to-add-a-job-trigger"></a><span data-ttu-id="d8fa6-128">Добавление триггера задания</span><span class="sxs-lookup"><span data-stu-id="d8fa6-128">How to add a job trigger</span></span>

<span data-ttu-id="d8fa6-129">При добавлении триггера задания в запланированное задание триггер задания добавляется в XML-файл запланированного задания для запланированного задания и становится частью запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-129">When you add a job trigger to a scheduled job, the job trigger is added to the scheduled job XML file for the scheduled job and becomes part of the scheduled job.</span></span>

<span data-ttu-id="d8fa6-130">Вы можете добавить триггер задания в запланированное задание при создании запланированного задания или изменить существующее задание.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-130">You can add a job trigger to a scheduled job when you create the scheduled job, or edit an existing job.</span></span> <span data-ttu-id="d8fa6-131">Вы можете в любое время изменить триггер задания для запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-131">You can change the job trigger of a scheduled job at any time.</span></span>

<span data-ttu-id="d8fa6-132">PowerShell использует одни и те же Триггеры заданий, которые планировщик задач использует.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-132">PowerShell uses some of the same job triggers that Task Scheduler uses.</span></span> <span data-ttu-id="d8fa6-133">Подробные сведения о триггерах заданий см. в разделе справки по командлету [New-JobTrigger](xref:PSScheduledJob.New-JobTrigger) .</span><span class="sxs-lookup"><span data-stu-id="d8fa6-133">For detailed information about job triggers, see the help topic for the [New-JobTrigger](xref:PSScheduledJob.New-JobTrigger) cmdlet.</span></span>

<span data-ttu-id="d8fa6-134">В следующем примере Сплаттинг используется для создания `$JobParms` значений параметров, которые передаются в `Register-ScheduledJob` командлет.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-134">The following example uses splatting to create `$JobParms` which are parameter values that are passed to the `Register-ScheduledJob` cmdlet.</span></span> <span data-ttu-id="d8fa6-135">Дополнительные сведения см. в разделе [about_Splatting. md](../../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="d8fa6-135">For more information, see [about_Splatting.md](../../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>
<span data-ttu-id="d8fa6-136">`Register-ScheduledJob`Использует `@JobParms` для создания запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-136">The `Register-ScheduledJob` uses `@JobParms` to create a scheduled job.</span></span> <span data-ttu-id="d8fa6-137">Для указания триггера задания в переменной используется параметр **Trigger** `$T` .</span><span class="sxs-lookup"><span data-stu-id="d8fa6-137">It uses the **Trigger** parameter to specify the job trigger in the `$T` variable.</span></span>

```powershell
$JobParms = @{
  Name = "ProcessJob"
  ScriptBlock = {Get-Command}
  Trigger = $T
}

Register-ScheduledJob @JobParms
```

<span data-ttu-id="d8fa6-138">Вы также можете добавить триггер задания в существующее запланированное задание в любое время.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-138">You can also add a job trigger to an existing scheduled job at any time.</span></span> <span data-ttu-id="d8fa6-139">`Add-JobTrigger`Командлет добавляет триггер задания в `$T` переменную в запланированное задание **процессжоб** .</span><span class="sxs-lookup"><span data-stu-id="d8fa6-139">The `Add-JobTrigger` cmdlet adds the job trigger in the `$T` variable to the **ProcessJob** scheduled job.</span></span>

```powershell
Add-JobTrigger -Name ProcessJob -Trigger $T
```

<span data-ttu-id="d8fa6-140">В результате триггер задания запускает **процессжоб** автоматически каждый понедельник и четверг в 5:00 AM.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-140">As a result, the job trigger starts the **ProcessJob** automatically every Monday and Thursday at 5:00 AM.</span></span>

## <a name="how-to-get-a-job-trigger"></a><span data-ttu-id="d8fa6-141">Как получить триггер задания</span><span class="sxs-lookup"><span data-stu-id="d8fa6-141">How to get a job trigger</span></span>

<span data-ttu-id="d8fa6-142">Чтобы получить триггер задания для запланированного задания, используйте `Get-JobTrigger` командлет.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-142">To get the job trigger of a scheduled job, use the `Get-JobTrigger` cmdlet.</span></span> <span data-ttu-id="d8fa6-143">Используйте параметры **Name** , **ID** и **InputObject** , чтобы указать запланированное задание, а не триггер задания.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-143">Use the **Name** , **ID** , and **InputObject** parameters to specify the scheduled job, not the job trigger.</span></span>

<span data-ttu-id="d8fa6-144">`Get-JobTrigger` Возвращает триггер задания **процессжоб**.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-144">`Get-JobTrigger` gets the job trigger of the **ProcessJob**.</span></span>

```powershell
Get-JobTrigger -Name ProcessJob
```

```Output
Id   Frequency       Time                   DaysOfWeek              Enabled
--   ---------       ----                   ----------              -------
1    Weekly          11/7/2011 5:00:00 AM   {Monday, Thursday}      True
```

## <a name="how-to-create-job-options"></a><span data-ttu-id="d8fa6-145">Создание параметров задания</span><span class="sxs-lookup"><span data-stu-id="d8fa6-145">How to create job options</span></span>

<span data-ttu-id="d8fa6-146">Параметры задания устанавливают условия для запуска и выполнения задания.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-146">Job options establish conditions for starting and running the job.</span></span> <span data-ttu-id="d8fa6-147">Каждое задание имеет параметры задания по умолчанию, если они не были изменены.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-147">Every job has the default job options unless you change them.</span></span> <span data-ttu-id="d8fa6-148">Поскольку параметры задания могут препятствовать запуску задания в запланированное время, важно понимать параметры задания и использовать их аккуратно.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-148">Because job options can prevent a job from running at the scheduled time, it is important to understand the job options and use them carefully.</span></span>

<span data-ttu-id="d8fa6-149">PowerShell использует те же параметры задания, которые планировщик задач использует.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-149">PowerShell uses the same job options that Task Scheduler uses.</span></span> <span data-ttu-id="d8fa6-150">Подробные сведения о параметрах задания см. в разделе справки [New-scheduledjoboptions](xref:PSScheduledJob.New-ScheduledJobOption).</span><span class="sxs-lookup"><span data-stu-id="d8fa6-150">For detailed information about the job options, see the help topic for [New-ScheduledJobOption](xref:PSScheduledJob.New-ScheduledJobOption).</span></span>

<span data-ttu-id="d8fa6-151">Параметры задания хранятся в XML-файле запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-151">Job options are stored in the scheduled job XML file.</span></span> <span data-ttu-id="d8fa6-152">Вы можете задать параметры задания при создании запланированного задания или изменить их в любое время.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-152">You can set job options when you create a scheduled job or change them at any time.</span></span>

<span data-ttu-id="d8fa6-153">`New-ScheduledJobOption`Командлет создает параметр запланированного задания, в котором параметру запланированного задания **вакеторун** присвоено значение true.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-153">The `New-ScheduledJobOption` cmdlet creates a scheduled job option in which the **WakeToRun** scheduled job option is set to True.</span></span> <span data-ttu-id="d8fa6-154">Параметр **вакеторун** запускает запланированное задание, даже если компьютер находится в спящем или спящем режиме в запланированное время запуска.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-154">The **WakeToRun** option runs the scheduled job even if the computer is in the Sleep or Hibernate state at the scheduled start time.</span></span> <span data-ttu-id="d8fa6-155">Команда сохраняет параметры задания в `$O` переменной.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-155">The command saves the job options in the `$O` variable.</span></span>

```powershell
$O = New-ScheduledJobOption -WakeToRun
```

## <a name="how-to-get-job-options"></a><span data-ttu-id="d8fa6-156">Получение параметров задания</span><span class="sxs-lookup"><span data-stu-id="d8fa6-156">How to get job options</span></span>

<span data-ttu-id="d8fa6-157">Чтобы получить параметры задания запланированного задания, используйте `Get-ScheduledJobOption` командлет.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-157">To get the job options of a scheduled job, use the `Get-ScheduledJobOption` cmdlet.</span></span> <span data-ttu-id="d8fa6-158">Используйте параметры **Name** , **ID** и **InputObject** , чтобы указать запланированное задание, а не параметры задания.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-158">Use the **Name** , **ID** , and **InputObject** parameters to specify the scheduled job, not the job options.</span></span>

<span data-ttu-id="d8fa6-159">`Get-ScheduledJobOption` Возвращает параметры задания **процессжоб**.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-159">`Get-ScheduledJobOption` gets the job options of the **ProcessJob**.</span></span>

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

## <a name="how-to-change-job-options"></a><span data-ttu-id="d8fa6-160">Изменение параметров задания</span><span class="sxs-lookup"><span data-stu-id="d8fa6-160">How to change job options</span></span>

<span data-ttu-id="d8fa6-161">Можно изменить параметры задания запланированного задания при создании запланированного задания или изменении существующего задания.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-161">You can change the job options of a scheduled job when you create a scheduled job or edit an existing job.</span></span>

<span data-ttu-id="d8fa6-162">Сплаттед `$JobParms` передаются в `Add-JobTrigger` командлет для создания задания процесса.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-162">The splatted `$JobParms` are passed to the `Add-JobTrigger` cmdlet to create the process job.</span></span> <span data-ttu-id="d8fa6-163">Для указания параметров задания в переменной используется параметр **scheduledjoboptions** `$O` .</span><span class="sxs-lookup"><span data-stu-id="d8fa6-163">It uses the **ScheduledJobOption** parameter to specify the job options in the `$O` variable.</span></span>

```powershell
$JobParms = @{
  Name = "ProcessJob"
  ScriptBlock = {Get-Process}
  ScheduledJobOption = $O
}

Add-JobTrigger @JobParms
```

<span data-ttu-id="d8fa6-164">Можно также изменить параметры задания на существующее запланированное задание в любое время.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-164">You can also change the job options to an existing scheduled job at any time.</span></span>
<span data-ttu-id="d8fa6-165">Следующая команда использует командлет, `Set-ScheduledJobOption` чтобы изменить значение параметра **вакеторун** **процессжоб** scheduledJob на **true**.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-165">The following command uses the `Set-ScheduledJobOption` cmdlet to change the value of the **WakeToRun** option of the **ProcessJob** scheduledJob to **True**.</span></span>

<span data-ttu-id="d8fa6-166">`Set`Командлеты в модуле **PSScheduledJob** , такие как `Set-ScheduledJobOption` командлет, не имеют параметров **имени** или **идентификатора** .</span><span class="sxs-lookup"><span data-stu-id="d8fa6-166">The `Set` cmdlets in the **PSScheduledJob** module, such as the `Set-ScheduledJobOption` cmdlet, don't have **Name** or **ID** parameters.</span></span> <span data-ttu-id="d8fa6-167">Параметр **InputObject** можно использовать для указания параметров запланированного задания или передачи по конвейеру запланированного задания из `Get-ScheduledJobOption` командлета в `Set-ScheduledJobOption` .</span><span class="sxs-lookup"><span data-stu-id="d8fa6-167">You can use the **InputObject** parameter to specify the scheduled job options or pipe a scheduled job from `Get-ScheduledJobOption` cmdlet to `Set-ScheduledJobOption`.</span></span>

<span data-ttu-id="d8fa6-168">В этом примере используется `Get-ScheduledJob` командлет для получения процессжоб.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-168">This example uses the `Get-ScheduledJob` cmdlet to get the ProcessJob.</span></span> <span data-ttu-id="d8fa6-169">Он использует `Get-ScheduledJobOption` командлет, чтобы получить параметры задания в **процессжоб** , и командлет, `Set-ScheduledJobOption` чтобы изменить параметр задания **вакеторун** в процессжоб на true.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-169">It uses the `Get-ScheduledJobOption` cmdlet to get the job options in the **ProcessJob** and the `Set-ScheduledJobOption` cmdlet to change the **WakeToRun** job option in the ProcessJob to True.</span></span>

```powershell
Get-ScheduledJob -Name ProcessJob | Get-ScheduledJobOption |
 Set-ScheduledJobOption -WakeToRun
```

## <a name="how-to-get-scheduled-job-instances"></a><span data-ttu-id="d8fa6-170">Получение экземпляров запланированных заданий</span><span class="sxs-lookup"><span data-stu-id="d8fa6-170">How to get scheduled job instances</span></span>

<span data-ttu-id="d8fa6-171">При запуске запланированного задания PowerShell создает экземпляр задания, аналогичный стандартному фоновому заданию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-171">When a scheduled job is started, PowerShell creates a job instance that is similar to a standard PowerShell background job.</span></span> <span data-ttu-id="d8fa6-172">`Get-Job` `Stop-Job` Для управления экземплярами заданий можно использовать командлеты задания, такие как, и `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="d8fa6-172">You can use the job cmdlets, such as `Get-Job`, `Stop-Job` and `Receive-Job` to manage the job instances.</span></span>

> [!NOTE]
> <span data-ttu-id="d8fa6-173">Чтобы использовать командлеты задания для экземпляров запланированных заданий, необходимо импортировать модуль **PSScheduledJob** в сеанс.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-173">To use the job cmdlets on instances of scheduled jobs, the **PSScheduledJob** module must be imported into the session.</span></span> <span data-ttu-id="d8fa6-174">Чтобы импортировать модуль **PSScheduledJob** , введите `Import-Module PSScheduledJob` или используйте любой командлет запланированного задания, например `Get-ScheduledJob` .</span><span class="sxs-lookup"><span data-stu-id="d8fa6-174">To import the **PSScheduledJob** module, type `Import-Module PSScheduledJob` or use any scheduled job cmdlet, such as `Get-ScheduledJob`.</span></span>

<span data-ttu-id="d8fa6-175">Чтобы получить все экземпляры запланированных заданий PowerShell и все активные стандартные задания, используйте `Get-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-175">To get all instances of PowerShell scheduled jobs, and all active standard jobs, use the `Get-Job` cmdlet.</span></span> <span data-ttu-id="d8fa6-176">`Import-Module`Командлет импортирует модуль **PSScheduledJob** и `Get-Job` получает задания на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-176">The `Import-Module` cmdlet imports the **PSScheduledJob** module and `Get-Job` gets the jobs on the local computer.</span></span>

```powershell
Import-Module PSScheduledJob
Get-Job
```

<span data-ttu-id="d8fa6-177">`Get-Job` Возвращает экземпляры **процессжоб** на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-177">`Get-Job` gets instances of **ProcessJob** on the local computer.</span></span>

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

<span data-ttu-id="d8fa6-178">Отображение по умолчанию не показывает время начала, которое обычно различает экземпляры одного и того же запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-178">The default display does not show the start time, which typically distinguishes instances of the same scheduled job.</span></span>

<span data-ttu-id="d8fa6-179">`Get-Job`Командлет отправляет объекты по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-179">The `Get-Job` cmdlet sends objects down the pipeline.</span></span> <span data-ttu-id="d8fa6-180">`Format-Table`Командлет отображает свойства **Name** , **ID** и **BeginTime** запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-180">The `Format-Table` cmdlet displays the **Name** , **ID** , and **BeginTime** properties of the scheduled job.</span></span>

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

## <a name="get-scheduled-job-results"></a><span data-ttu-id="d8fa6-181">Получение результатов запланированного задания</span><span class="sxs-lookup"><span data-stu-id="d8fa6-181">Get scheduled job results</span></span>

<span data-ttu-id="d8fa6-182">Чтобы получить результаты экземпляра запланированного задания, используйте `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-182">To get the results of an instance of a scheduled job, use the `Receive-Job` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="d8fa6-183">Чтобы использовать командлеты задания для экземпляров запланированных заданий, необходимо импортировать модуль **PSScheduledJob** в сеанс.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-183">To use the Job cmdlets on instances of scheduled jobs, the **PSScheduledJob** module must be imported into the session.</span></span> <span data-ttu-id="d8fa6-184">Чтобы импортировать модуль **PSScheduledJob** , введите `Import-Module PSScheduledJob` или используйте любой командлет запланированного задания, например `Get-ScheduledJob` .</span><span class="sxs-lookup"><span data-stu-id="d8fa6-184">To import the **PSScheduledJob** module, type `Import-Module PSScheduledJob` or use any scheduled job cmdlet, such as `Get-ScheduledJob`.</span></span>

<span data-ttu-id="d8fa6-185">В этом примере получаются результаты последнего экземпляра запланированного задания **процессжоб** (ид = 51).</span><span class="sxs-lookup"><span data-stu-id="d8fa6-185">This examples gets the results of the newest instance of the **ProcessJob** scheduled job (ID = 51).</span></span>

```powershell
Import-Module PSScheduledJob
Receive-Job -ID 51 -Keep
```

<span data-ttu-id="d8fa6-186">Результаты запланированных заданий сохраняются на диске, поэтому параметр **сохранения** `Receive-Job` не требуется.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-186">The results of scheduled jobs are saved on disk, so the **Keep** parameter of `Receive-Job` is not required.</span></span> <span data-ttu-id="d8fa6-187">Однако без параметра **сохранения** результаты запланированного задания можно получить только один раз в каждом сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-187">However, without the **Keep** parameter, you can get the results of a scheduled job only once in each PowerShell session.</span></span> <span data-ttu-id="d8fa6-188">Чтобы запустить новый сеанс PowerShell, введите `PowerShell` или откройте новое окно PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8fa6-188">To start a new PowerShell session, type `PowerShell` or open a new PowerShell window.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8fa6-189">См. также статью</span><span class="sxs-lookup"><span data-stu-id="d8fa6-189">See also</span></span>

[<span data-ttu-id="d8fa6-190">about_Scheduled_Jobs_Advanced</span><span class="sxs-lookup"><span data-stu-id="d8fa6-190">about_Scheduled_Jobs_Advanced</span></span>](about_Scheduled_Jobs_Advanced.md)

[<span data-ttu-id="d8fa6-191">about_Scheduled_Jobs_Troubleshooting</span><span class="sxs-lookup"><span data-stu-id="d8fa6-191">about_Scheduled_Jobs_Troubleshooting</span></span>](about_Scheduled_Jobs_Troubleshooting.md)

[<span data-ttu-id="d8fa6-192">about_Scheduled_Jobs</span><span class="sxs-lookup"><span data-stu-id="d8fa6-192">about_Scheduled_Jobs</span></span>](about_Scheduled_Jobs.md)

[<span data-ttu-id="d8fa6-193">about_Splatting. md</span><span class="sxs-lookup"><span data-stu-id="d8fa6-193">about_Splatting.md</span></span>](../../Microsoft.PowerShell.Core/About/about_Splatting.md)

<span data-ttu-id="d8fa6-194">Командлеты модуля [PSScheduledJob](xref:PSScheduledJob)</span><span class="sxs-lookup"><span data-stu-id="d8fa6-194">[PSScheduledJob](xref:PSScheduledJob) module cmdlets</span></span>

[<span data-ttu-id="d8fa6-195">Планировщик заданий</span><span class="sxs-lookup"><span data-stu-id="d8fa6-195">Task Scheduler</span></span>](/windows/desktop/TaskSchd/task-scheduler-reference)
