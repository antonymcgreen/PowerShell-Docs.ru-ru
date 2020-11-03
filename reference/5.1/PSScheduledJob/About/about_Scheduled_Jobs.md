---
description: Описывает запланированные задания и объясняет, как использовать запланированные задания и управлять ими в PowerShell и в планировщик задач.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/about/about_scheduled_jobs?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scheduled_Jobs
ms.openlocfilehash: 4d4e86957a584bb4deb47cadcd8588c1236455ac
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231634"
---
# <a name="about-scheduled-jobs"></a><span data-ttu-id="3e499-104">О запланированных заданиях</span><span class="sxs-lookup"><span data-stu-id="3e499-104">About Scheduled Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="3e499-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="3e499-105">Short description</span></span>

<span data-ttu-id="3e499-106">Описывает запланированные задания и объясняет, как использовать запланированные задания и управлять ими в PowerShell и в планировщик задач.</span><span class="sxs-lookup"><span data-stu-id="3e499-106">Describes scheduled jobs and explains how to use and manage scheduled jobs in PowerShell and in Task Scheduler.</span></span>

## <a name="long-description"></a><span data-ttu-id="3e499-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="3e499-107">Long description</span></span>

<span data-ttu-id="3e499-108">Запланированные задания PowerShell — это полезная гибрид фоновых заданий PowerShell и планировщик задач задач.</span><span class="sxs-lookup"><span data-stu-id="3e499-108">PowerShell scheduled jobs are a useful hybrid of PowerShell background jobs and Task Scheduler tasks.</span></span>

<span data-ttu-id="3e499-109">Как и фоновые задания PowerShell, запланированные задания выполняются асинхронно в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="3e499-109">Like PowerShell background jobs, scheduled jobs run asynchronously in the background.</span></span> <span data-ttu-id="3e499-110">Экземпляры выполняемых запланированных заданий можно управлять с помощью командлетов задания, таких как,, `Start-Job` `Get-Job` `Stop-Job` и `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="3e499-110">Instances of scheduled jobs that have run can be managed by using the job cmdlets, such as `Start-Job`, `Get-Job`, `Stop-Job`, and `Receive-Job`.</span></span>

<span data-ttu-id="3e499-111">Как и планировщик задач задачи, запланированные задания сохраняются на диск.</span><span class="sxs-lookup"><span data-stu-id="3e499-111">Like Task Scheduler tasks, scheduled jobs are saved to disk.</span></span> <span data-ttu-id="3e499-112">Вы можете просматривать задания и управлять ими в планировщик задач, включать и отключать их по мере необходимости, запускать их или использовать в качестве шаблонов, устанавливать однократные или повторяющиеся расписания для запуска заданий или задавать условия, при которых задания запускаются.</span><span class="sxs-lookup"><span data-stu-id="3e499-112">You can view and manage the jobs in Task Scheduler, enable and disable them as needed, run them or use them as templates, establish a one-time or recurring schedules for starting the jobs, or set conditions under which the jobs start.</span></span>

<span data-ttu-id="3e499-113">Кроме того, результаты выполнения экземпляров запланированных заданий сохраняются на диске в удобном для использования формате, предоставляя выполнение журнала выходных данных задания.</span><span class="sxs-lookup"><span data-stu-id="3e499-113">In addition, the results of scheduled job instances are saved to disk in an easily accessible format, providing a running log of job output.</span></span> <span data-ttu-id="3e499-114">Запланированные задания поставляются с настроенным набором командлетов для управления ими.</span><span class="sxs-lookup"><span data-stu-id="3e499-114">Scheduled jobs come with a customized set of cmdlets for managing them.</span></span> <span data-ttu-id="3e499-115">Командлеты позволяют создавать, изменять, управлять, отключать и повторно включать запланированные задания, триггеры заданий и параметры задания.</span><span class="sxs-lookup"><span data-stu-id="3e499-115">The cmdlets let you create, edit, manage, disable, and re-enable scheduled jobs, job triggers and job options.</span></span>

<span data-ttu-id="3e499-116">Этот всеобъемлющий и гибкий набор средств делает запланированные задания ключевым компонентом многих профессиональных ИТ-решений PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e499-116">This comprehensive and flexible set of tools make scheduled jobs an essential component of many professional PowerShell IT solutions.</span></span>

<span data-ttu-id="3e499-117">Командлеты запланированных заданий входят в модуль **PSScheduledJob** , который устанавливается вместе с PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e499-117">The scheduled job cmdlets are included in the **PSScheduledJob** module that is installed with PowerShell.</span></span> <span data-ttu-id="3e499-118">Этот модуль появился в PowerShell 3,0 и работает в PowerShell 3,0 и более поздних версиях PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e499-118">This module was introduced in PowerShell 3.0 and works in PowerShell 3.0 and later versions of PowerShell.</span></span> <span data-ttu-id="3e499-119">Дополнительные сведения о командлетах, содержащихся в модуле **PSScheduledJob** , см. в разделе [PSScheduledJob](xref:PSScheduledJob).</span><span class="sxs-lookup"><span data-stu-id="3e499-119">For more information about the cmdlets contained in the **PSScheduledJob** module, see [PSScheduledJob](xref:PSScheduledJob).</span></span>

<span data-ttu-id="3e499-120">Дополнительные сведения о фоновых заданиях PowerShell см. в разделе [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="3e499-120">For more information about PowerShell background jobs, see [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md).</span></span>

<span data-ttu-id="3e499-121">Дополнительные сведения о планировщик задач см. в разделе [планировщик задач](/windows/desktop/TaskSchd/task-scheduler-reference).</span><span class="sxs-lookup"><span data-stu-id="3e499-121">For more information about Task Scheduler, see [Task Scheduler](/windows/desktop/TaskSchd/task-scheduler-reference).</span></span>

> [!NOTE]
> <span data-ttu-id="3e499-122">Вы можете просматривать запланированные задания PowerShell и управлять ими в планировщик задач.</span><span class="sxs-lookup"><span data-stu-id="3e499-122">You can view and manage PowerShell scheduled jobs in Task Scheduler.</span></span> <span data-ttu-id="3e499-123">Задания PowerShell и командлеты запланированных заданий работают только с запланированными заданиями, созданными в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e499-123">The PowerShell jobs and scheduled job cmdlets work only on scheduled jobs that are created in PowerShell.</span></span>

## <a name="quick-start"></a><span data-ttu-id="3e499-124">Быстрый запуск</span><span class="sxs-lookup"><span data-stu-id="3e499-124">Quick start</span></span>

<span data-ttu-id="3e499-125">В этом примере создается запланированное задание, которое запускается каждый день в 3:00 AM и запускается `Get-Process` командлет.</span><span class="sxs-lookup"><span data-stu-id="3e499-125">This example creates a scheduled job that starts every day at 3:00 AM and runs the `Get-Process` cmdlet.</span></span> <span data-ttu-id="3e499-126">Задание запускается, даже если компьютер работает от батарей.</span><span class="sxs-lookup"><span data-stu-id="3e499-126">The job starts even if the computer is running on batteries.</span></span>

```powershell
$trigger = New-JobTrigger -Daily -At 3AM
$options = New-ScheduledJobOption -StartIfOnBattery
Register-ScheduledJob -Name ProcessJob -ScriptBlock {Get-Process} `
-Trigger $trigger -ScheduledJobOption $options
```

<span data-ttu-id="3e499-127">`Get-ScheduledJob`Командлет возвращает запланированные задания на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3e499-127">The `Get-ScheduledJob` cmdlet gets the scheduled jobs on the local computer.</span></span>

```powershell
Get-ScheduledJob
```

```Output
Id         Name            Triggers        Command            Enabled
--         ----            --------        -------            -------
7          ProcessJob      {1}             Get-Process        True
```

<span data-ttu-id="3e499-128">`Get-JobTrigger` Возвращает триггеры задания **процессжоб** .</span><span class="sxs-lookup"><span data-stu-id="3e499-128">`Get-JobTrigger` gets the job triggers of **ProcessJob** .</span></span> <span data-ttu-id="3e499-129">Входные параметры задают запланированное задание, а не триггер, так как триггеры сохраняются в запланированном задании.</span><span class="sxs-lookup"><span data-stu-id="3e499-129">The input parameters specify the scheduled job, not the trigger, because triggers are saved in a scheduled job.</span></span>

```powershell
Get-JobTrigger -Name ProcessJob
```

```Output
Id         Frequency       Time                   DaysOfWeek        Enabled
--         ---------       ----                   ----------        -------
1          Daily           11/5/2011 3:00:00 AM                     True
```

<span data-ttu-id="3e499-130">В этом примере используется параметр **континуеифгоингонбаттери** `Set-ScheduledJob` командлета, чтобы изменить свойство **Стопифгоингонбаттериес** объекта **процессжоб** на **false** .</span><span class="sxs-lookup"><span data-stu-id="3e499-130">This example uses the **ContinueIfGoingOnBattery** parameter of the `Set-ScheduledJob` cmdlet to change the **StopIfGoingOnBatteries** property of **ProcessJob** to **False** .</span></span>

```powershell
Get-ScheduledJob -Name ProcessJob | Set-ScheduledJobOption `
-ContinueIfGoingOnBattery -Passthru
```

```Output
StartIfOnBatteries     : True
StopIfGoingOnBatteries : False
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

<span data-ttu-id="3e499-131">`Get-ScheduledJob`Командлет возвращает запланированное задание **процессжоб** .</span><span class="sxs-lookup"><span data-stu-id="3e499-131">The `Get-ScheduledJob` cmdlet gets the **ProcessJob** scheduled job.</span></span>

```powershell
Get-ScheduledJob ProcessJob
```

```Output
Id         Name            Triggers        Command        Enabled
--         ----            --------        -------        -------
7          ProcessJob      {1}             Get-Process    True
```

<span data-ttu-id="3e499-132">`Get-Job`Командлет возвращает все экземпляры запланированного задания **процессжоб** , которые были запущены на данный момент.</span><span class="sxs-lookup"><span data-stu-id="3e499-132">The `Get-Job` cmdlet gets all instances of the **ProcessJob** scheduled job that have run thus far.</span></span> <span data-ttu-id="3e499-133">`Get-Job`Командлет получает запланированные задания только при импорте модуля **PSScheduledJob** в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="3e499-133">The `Get-Job` cmdlet gets scheduled jobs only when the **PSScheduledJob** module is imported into the current session.</span></span>

> [!TIP]
> <span data-ttu-id="3e499-134">Обратите внимание, что командлеты запланированных заданий используются для управления запланированными заданиями, но для управления экземплярами запланированных заданий используются командлеты задания.</span><span class="sxs-lookup"><span data-stu-id="3e499-134">Notice that you use the scheduled job cmdlets to manage scheduled jobs, but you use the job cmdlets to manage instances of scheduled jobs.</span></span>

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

<span data-ttu-id="3e499-135">`Receive-Job`Командлет возвращает результаты последнего экземпляра запланированного задания **ПРОЦЕССЖОБ** (ИД = 51).</span><span class="sxs-lookup"><span data-stu-id="3e499-135">The `Receive-Job` cmdlet gets the results of the most recent instance of the **ProcessJob** scheduled job (ID = 51).</span></span>

```powershell
Receive-Job -ID 51
```

<span data-ttu-id="3e499-136">Несмотря на то `Receive-Job` , что команда не включала параметр **сохранения** , результаты задания сохраняются на диске, пока вы не удалите их или не превышено максимальное число результатов.</span><span class="sxs-lookup"><span data-stu-id="3e499-136">Even though the `Receive-Job` command did not include the **Keep** parameter, the results of the job are saved on disk until you delete them or the maximum number of results are exceeded.</span></span>

<span data-ttu-id="3e499-137">Результаты задания больше не доступны в этом сеансе, но если вы запускаете новый сеанс или открываете новое окно PowerShell, результаты задания снова становятся доступными.</span><span class="sxs-lookup"><span data-stu-id="3e499-137">The job results are no longer available in this session, but if you start a new session or open a new PowerShell window, the results of the job are available again.</span></span>

<span data-ttu-id="3e499-138">Следующая команда использует параметр **DefinitionName** `Start-Job` командлета для запуска запланированного задания **процессжоб** .</span><span class="sxs-lookup"><span data-stu-id="3e499-138">The following command uses the **DefinitionName** parameter of the `Start-Job` cmdlet to start the **ProcessJob** scheduled job.</span></span>

<span data-ttu-id="3e499-139">Задания, запускаемые с помощью `Start-Job` командлета, являются стандартными фоновыми заданиями PowerShell, а не экземплярами запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="3e499-139">Jobs that are started by using the `Start-Job` cmdlet are standard PowerShell background jobs, not instances of the scheduled job.</span></span> <span data-ttu-id="3e499-140">Как и все фоновые задания, эти задания запускаются немедленно, они не подчиняются параметрам задания или не зависят от триггеров заданий, а их выходные данные не сохраняются в выходном каталоге каталога запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="3e499-140">Like all background jobs, these jobs start immediately, they aren't subject to job options or affected by job triggers, and their output is not saved in the output directory of the scheduled job directory.</span></span>

```powershell
Start-Job -DefinitionName ProcessJob
```

<span data-ttu-id="3e499-141">`Unregister-ScheduledJob`Командлет удаляет запланированное задание **процессжоб** и все сохраненные результаты его экземпляров.</span><span class="sxs-lookup"><span data-stu-id="3e499-141">The `Unregister-ScheduledJob` cmdlet deletes the **ProcessJob** scheduled job and all saved results of its job instances.</span></span>

```powershell
Unregister-ScheduledJob ProcessJob
```

## <a name="scheduled-jobs-concepts"></a><span data-ttu-id="3e499-142">Основные понятия запланированных заданий</span><span class="sxs-lookup"><span data-stu-id="3e499-142">Scheduled jobs concepts</span></span>

<span data-ttu-id="3e499-143">Запланированное задание запускает команды или скрипт.</span><span class="sxs-lookup"><span data-stu-id="3e499-143">A scheduled job runs commands or a script.</span></span> <span data-ttu-id="3e499-144">Запланированное задание может включать триггеры заданий, запускающие задания и параметры задания, которые задают условия для выполнения задания.</span><span class="sxs-lookup"><span data-stu-id="3e499-144">A scheduled job can include job triggers that start the job and job options that set conditions for running the job.</span></span>

<span data-ttu-id="3e499-145">Триггер задания автоматически запускает запланированное задание.</span><span class="sxs-lookup"><span data-stu-id="3e499-145">A job trigger starts a scheduled job automatically.</span></span> <span data-ttu-id="3e499-146">Триггер задания может включать разовое или повторяющееся расписание или указывать событие, например, когда пользователь входит в систему или запускается Windows.</span><span class="sxs-lookup"><span data-stu-id="3e499-146">A job trigger can include a one-time or recurring schedule or specify an event, such as when a user logs on or Windows starts.</span></span> <span data-ttu-id="3e499-147">Запланированное задание может иметь один или несколько триггеров заданий, а также создавать, добавлять, включать, отключать и получать Триггеры заданий.</span><span class="sxs-lookup"><span data-stu-id="3e499-147">A scheduled job can have one or more job triggers, and you can create, add, enable, disable, and get job triggers.</span></span>

<span data-ttu-id="3e499-148">Триггеры задания не являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="3e499-148">Job triggers are optional.</span></span> <span data-ttu-id="3e499-149">Запланированные задания можно запускать немедленно с помощью `Start-Job cmdlet` или путем добавления параметра **RunNow** в `Register-ScheduledJob` команду.</span><span class="sxs-lookup"><span data-stu-id="3e499-149">You can start scheduled jobs immediately by using the `Start-Job cmdlet`, or by adding the **RunNow** parameter to your `Register-ScheduledJob` command.</span></span>

<span data-ttu-id="3e499-150">Параметры задания задают условия для выполнения запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="3e499-150">Job options set the conditions for running a scheduled job.</span></span> <span data-ttu-id="3e499-151">У каждого запланированного задания есть один объект параметров задания.</span><span class="sxs-lookup"><span data-stu-id="3e499-151">Every scheduled job has one job options object.</span></span> <span data-ttu-id="3e499-152">Вы можете создавать и изменять объекты параметров задания, а также добавлять их в одно или несколько запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="3e499-152">You can create and edit job options objects and add them to one or more scheduled jobs.</span></span>

<span data-ttu-id="3e499-153">При каждом запуске запланированного задания создается экземпляр задания.</span><span class="sxs-lookup"><span data-stu-id="3e499-153">Each time a scheduled job starts, a job instance is created.</span></span> <span data-ttu-id="3e499-154">Используйте командлеты задания PowerShell для просмотра экземпляра задания и управления им.</span><span class="sxs-lookup"><span data-stu-id="3e499-154">Use the PowerShell job cmdlets to view and manage the job instance.</span></span>

<span data-ttu-id="3e499-155">Запланированные задания сохраняются на диске и используют команду командлета, `Register` вместо `New` .</span><span class="sxs-lookup"><span data-stu-id="3e499-155">Scheduled jobs are saved to disk and use the cmdlet verb, `Register`, instead of `New`.</span></span> <span data-ttu-id="3e499-156">XML-файлы находятся на локальном компьютере в каталоге `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` .</span><span class="sxs-lookup"><span data-stu-id="3e499-156">The XML files are located on the local computer in the directory `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs`.</span></span>

<span data-ttu-id="3e499-157">PowerShell создает каталог для каждого запланированного задания и сохраняет команды задания, триггеры заданий, параметры задания и результаты задания в каталоге запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="3e499-157">PowerShell creates a directory for each scheduled job and saves the job commands, job triggers, job options and job results in the scheduled job directory.</span></span> <span data-ttu-id="3e499-158">Триггеры задания и параметры задания не сохраняются на диск независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="3e499-158">Job triggers and job options aren't saved to disk independently.</span></span>
<span data-ttu-id="3e499-159">Они сохраняются в XML-коде запланированного задания для каждого запланированного задания, с которым они связаны.</span><span class="sxs-lookup"><span data-stu-id="3e499-159">They are saved in the scheduled job XML of each scheduled job with which they are associated.</span></span>

<span data-ttu-id="3e499-160">Запланированные задания, триггеры заданий и параметры задания отображаются в PowerShell как объекты.</span><span class="sxs-lookup"><span data-stu-id="3e499-160">Scheduled jobs, job triggers, and job options appear in PowerShell as objects.</span></span>
<span data-ttu-id="3e499-161">Объекты взаимосвязаны, что упрощает их обнаружение и использование в командах и скриптах.</span><span class="sxs-lookup"><span data-stu-id="3e499-161">The objects are interlinked, which makes them easy to discover and use in commands and scripts.</span></span>

<span data-ttu-id="3e499-162">Запланированные задания отображаются как объекты **ScheduledJobDefinition** .</span><span class="sxs-lookup"><span data-stu-id="3e499-162">Scheduled jobs appear as **ScheduledJobDefinition** objects.</span></span> <span data-ttu-id="3e499-163">Объект **ScheduledJobDefinition** имеет свойство **жобтригжерс** , которое содержит триггеры заданий запланированного задания и свойство **Options** , которое содержит параметры задания.</span><span class="sxs-lookup"><span data-stu-id="3e499-163">The **ScheduledJobDefinition** object has a **JobTriggers** property that contains the job triggers of the scheduled job and an **Options** property that contains the job options.</span></span> <span data-ttu-id="3e499-164">Объекты **счедуледжобтригжерс** и **счедуледжобоптионс** , которые представляют триггеры задания и параметры задания соответственно, имеют свойство **JobDefinition** , содержащее запланированное задание, с которым они связаны.</span><span class="sxs-lookup"><span data-stu-id="3e499-164">The **ScheduledJobTriggers** and **ScheduledJobOptions** objects that represent job triggers and job options, respectively, each have a **JobDefinition** property that contains the scheduled job with which they are associated.</span></span> <span data-ttu-id="3e499-165">Это рекурсивное межсоединение позволяет легко найти триггеры и параметры запланированного задания, а также найти, создать скрипт и отобразить запланированное задание, связанное с любым триггером задания или параметром задания.</span><span class="sxs-lookup"><span data-stu-id="3e499-165">This recursive interconnection makes it easy to find the triggers and options of a scheduled job and to find, script, and display the scheduled job to which any job trigger or job option is associated.</span></span>

## <a name="see-also"></a><span data-ttu-id="3e499-166">См. также статью</span><span class="sxs-lookup"><span data-stu-id="3e499-166">See also</span></span>

[<span data-ttu-id="3e499-167">about_Scheduled_Jobs_Basics</span><span class="sxs-lookup"><span data-stu-id="3e499-167">about_Scheduled_Jobs_Basics</span></span>](about_Scheduled_Jobs_Basics.md)

[<span data-ttu-id="3e499-168">about_Scheduled_Jobs_Advanced</span><span class="sxs-lookup"><span data-stu-id="3e499-168">about_Scheduled_Jobs_Advanced</span></span>](about_Scheduled_Jobs_Advanced.md)

[<span data-ttu-id="3e499-169">about_Scheduled_Jobs_Troubleshooting</span><span class="sxs-lookup"><span data-stu-id="3e499-169">about_Scheduled_Jobs_Troubleshooting</span></span>](about_Scheduled_Jobs_Troubleshooting.md)

<span data-ttu-id="3e499-170">Командлеты модуля [PSScheduledJob](xref:PSScheduledJob)</span><span class="sxs-lookup"><span data-stu-id="3e499-170">[PSScheduledJob](xref:PSScheduledJob) module cmdlets</span></span>

[<span data-ttu-id="3e499-171">Планировщик заданий</span><span class="sxs-lookup"><span data-stu-id="3e499-171">Task Scheduler</span></span>](/windows/desktop/TaskSchd/task-scheduler-reference)
