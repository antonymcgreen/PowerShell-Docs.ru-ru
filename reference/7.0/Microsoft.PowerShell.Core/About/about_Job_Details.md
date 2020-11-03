---
description: Предоставляет сведения о фоновых заданиях на локальных и удаленных компьютерах.
keywords: powershell,командлет
Locale: en-US
ms.date: 10/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_job_details?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Job_Details
ms.openlocfilehash: 0d85cd242c8e79281fa8be153b0e140660f16c1a
ms.sourcegitcommit: 108686b166672cc08817c637dd93eb1ad830511d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "93232982"
---
# <a name="about-job-details"></a><span data-ttu-id="3b31f-104">Сведения о задании</span><span class="sxs-lookup"><span data-stu-id="3b31f-104">About Job Details</span></span>

## <a name="short-description"></a><span data-ttu-id="3b31f-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="3b31f-105">Short description</span></span>
<span data-ttu-id="3b31f-106">Предоставляет сведения о фоновых заданиях на локальных и удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="3b31f-106">Provides details about background jobs on local and remote computers.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="3b31f-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="3b31f-107">Detailed description</span></span>

<span data-ttu-id="3b31f-108">В этом разделе объясняется понятие фонового задания и предоставляются технические сведения о работе фоновых заданий в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3b31f-108">This topic explains the concept of a background job and provides technical information about how background jobs work in PowerShell.</span></span>

<span data-ttu-id="3b31f-109">Этот раздел является дополнением к разделам [about_Jobs](about_Jobs.md), [about_Thread_Jobs](about_Thread_Jobs.md)и [about_Remote_Jobs](about_Remote_Jobs.md) .</span><span class="sxs-lookup"><span data-stu-id="3b31f-109">This topic is a supplement to the [about_Jobs](about_Jobs.md), [about_Thread_Jobs](about_Thread_Jobs.md), and [about_Remote_Jobs](about_Remote_Jobs.md) topics.</span></span>

### <a name="about-background-jobs"></a><span data-ttu-id="3b31f-110">О фоновых заданиях</span><span class="sxs-lookup"><span data-stu-id="3b31f-110">About background jobs</span></span>

<span data-ttu-id="3b31f-111">Фоновое задание выполняет команду или выражение асинхронно.</span><span class="sxs-lookup"><span data-stu-id="3b31f-111">A background job runs a command or expression asynchronously.</span></span> <span data-ttu-id="3b31f-112">Он может выполнять командлет, функцию, сценарий или любую другую задачу на основе команды.</span><span class="sxs-lookup"><span data-stu-id="3b31f-112">It might run a cmdlet, a function, a script, or any other command-based task.</span></span> <span data-ttu-id="3b31f-113">Она предназначена для выполнения команд, которые выполняются в течение продолжительного периода времени, но их можно использовать для выполнения любой команды в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="3b31f-113">It is designed to run commands that take an extended period of time, but you can use it to run any command in the background.</span></span>

<span data-ttu-id="3b31f-114">При выполнении синхронной команды Командная строка PowerShell подавляется до завершения команды.</span><span class="sxs-lookup"><span data-stu-id="3b31f-114">When a synchronous command runs, the PowerShell command prompt is suppressed until the command is complete.</span></span> <span data-ttu-id="3b31f-115">Но фоновое задание не подавляет командную строку PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3b31f-115">But a background job does not suppress the PowerShell prompt.</span></span> <span data-ttu-id="3b31f-116">Команда для запуска фонового задания возвращает объект задания.</span><span class="sxs-lookup"><span data-stu-id="3b31f-116">A command to start a background job returns a job object.</span></span>
<span data-ttu-id="3b31f-117">Запрос возвращается немедленно, чтобы можно было работать с другими задачами во время выполнения фонового задания.</span><span class="sxs-lookup"><span data-stu-id="3b31f-117">The prompt returns immediately so you can work on other tasks while the background job runs.</span></span>

<span data-ttu-id="3b31f-118">Однако при запуске фонового задания результаты не получаются немедленно, даже если задание выполняется очень быстро.</span><span class="sxs-lookup"><span data-stu-id="3b31f-118">However, when you start a background job, you do not get the results immediately even if the job runs very quickly.</span></span> <span data-ttu-id="3b31f-119">Возвращаемый объект задания содержит полезные сведения о задании, но не содержит результатов задания.</span><span class="sxs-lookup"><span data-stu-id="3b31f-119">The job object that is returned contains useful information about the job, but it does not contain the job results.</span></span> <span data-ttu-id="3b31f-120">Для получения результатов задания необходимо выполнить отдельную команду.</span><span class="sxs-lookup"><span data-stu-id="3b31f-120">You must run a separate command to get the job results.</span></span> <span data-ttu-id="3b31f-121">Можно также выполнить команды для завершения задания, ожидания завершения задания и удаления задания.</span><span class="sxs-lookup"><span data-stu-id="3b31f-121">You can also run commands to stop the job, to wait for the job to be completed, and to delete the job.</span></span>

<span data-ttu-id="3b31f-122">Чтобы сделать время фонового задания независимым от других команд, каждое фоновое задание выполняется в отдельном сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3b31f-122">To make the timing of a background job independent of other commands, each background job runs in its own PowerShell session.</span></span> <span data-ttu-id="3b31f-123">Однако это временное подключение, которое создается только для запуска задания и затем уничтожается, либо может быть постоянным **сеансом PSSession** , который можно использовать для выполнения нескольких связанных заданий или команд.</span><span class="sxs-lookup"><span data-stu-id="3b31f-123">However, this can be a temporary connection that is created only to run the job and is then destroyed, or it can be a persistent **PSSession** that you can use to run several related jobs or commands.</span></span>

### <a name="using-the-job-cmdlets"></a><span data-ttu-id="3b31f-124">Использование командлетов заданий</span><span class="sxs-lookup"><span data-stu-id="3b31f-124">Using the job cmdlets</span></span>

<span data-ttu-id="3b31f-125">Используйте `Start-Job` команду для запуска фонового задания на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b31f-125">Use a `Start-Job` command to start a background job on a local computer.</span></span>
<span data-ttu-id="3b31f-126">`Start-Job` Возвращает объект задания.</span><span class="sxs-lookup"><span data-stu-id="3b31f-126">`Start-Job` returns a job object.</span></span> <span data-ttu-id="3b31f-127">Кроме того, можно получить объекты, представляющие задания, запущенные на локальном компьютере с помощью `Get-Job` командлета.</span><span class="sxs-lookup"><span data-stu-id="3b31f-127">You can also get objects representing the jobs that were started on the local computer using the `Get-Job` cmdlet.</span></span>

<span data-ttu-id="3b31f-128">Чтобы получить результаты задания, используйте `Receive-Job` команду.</span><span class="sxs-lookup"><span data-stu-id="3b31f-128">To get the job results, use a `Receive-Job` command.</span></span> <span data-ttu-id="3b31f-129">Если задание не завершено, `Receive-Job` возвращает частичные результаты.</span><span class="sxs-lookup"><span data-stu-id="3b31f-129">If the job is not complete, `Receive-Job` returns partial results.</span></span> <span data-ttu-id="3b31f-130">Можно также использовать `Wait-Job` командлет для подавления командной строки до завершения одного или всех заданий, запущенных в сеансе.</span><span class="sxs-lookup"><span data-stu-id="3b31f-130">You can also use the `Wait-Job` cmdlet to suppress the command prompt until one or all of the jobs that were started in the session are complete.</span></span>

<span data-ttu-id="3b31f-131">Чтобы прерывать фоновое задание, используйте `Stop-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="3b31f-131">To stop a background job, use the `Stop-Job` cmdlet.</span></span> <span data-ttu-id="3b31f-132">Чтобы удалить задание, используйте `Remove-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="3b31f-132">To delete a job, use the `Remove-Job` cmdlet.</span></span>

<span data-ttu-id="3b31f-133">Дополнительные сведения о работе командлетов см. в разделе справки по каждому командлету и см. [about_Jobs](about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="3b31f-133">For more information about how the cmdlets work, see the Help topic for each cmdlet, and see [about_Jobs](about_Jobs.md).</span></span>

### <a name="starting-background-jobs-on-remote-computers"></a><span data-ttu-id="3b31f-134">Запуск фоновых заданий на удаленных компьютерах</span><span class="sxs-lookup"><span data-stu-id="3b31f-134">Starting background jobs on remote computers</span></span>

<span data-ttu-id="3b31f-135">Вы можете создавать фоновые задания и управлять ими на локальном или удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b31f-135">You can create and manage background jobs on a local or remote computer.</span></span> <span data-ttu-id="3b31f-136">Чтобы запустить фоновое задание удаленно, используйте параметр **AsJob** командлета `Invoke-Command` , например, или используйте `Invoke-Command` командлет для `Start-Job` удаленного выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="3b31f-136">To run a background job remotely, use the **AsJob** parameter of a cmdlet such as `Invoke-Command`, or use the `Invoke-Command` cmdlet to run a `Start-Job` command remotely.</span></span> <span data-ttu-id="3b31f-137">Фоновое задание также можно запустить в интерактивном сеансе.</span><span class="sxs-lookup"><span data-stu-id="3b31f-137">You can also start a background job in an interactive session.</span></span>

<span data-ttu-id="3b31f-138">Дополнительные сведения об удаленных фоновых заданиях см. в разделе [about_Remote_Jobs](about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="3b31f-138">For more information about remote background jobs, see [about_Remote_Jobs](about_Remote_Jobs.md).</span></span>

### <a name="child-jobs"></a><span data-ttu-id="3b31f-139">Дочерние задания</span><span class="sxs-lookup"><span data-stu-id="3b31f-139">Child jobs</span></span>

<span data-ttu-id="3b31f-140">Каждое фоновое задание состоит из родительского задания и одного или нескольких дочерних заданий.</span><span class="sxs-lookup"><span data-stu-id="3b31f-140">Each background job consists of a parent job and one or more child jobs.</span></span> <span data-ttu-id="3b31f-141">В заданиях, запущенных с помощью `Start-Job` или с параметром **AsJob** `Invoke-Command` , родительским заданием является руководитель.</span><span class="sxs-lookup"><span data-stu-id="3b31f-141">In jobs started using `Start-Job` or the **AsJob** parameter of `Invoke-Command`, the parent job is an executive.</span></span> <span data-ttu-id="3b31f-142">Он не выполняет никаких команд и не возвращает никаких результатов.</span><span class="sxs-lookup"><span data-stu-id="3b31f-142">It does not run any commands or return any results.</span></span> <span data-ttu-id="3b31f-143">Команды фактически выполняются дочерними заданиями.</span><span class="sxs-lookup"><span data-stu-id="3b31f-143">The commands are actually run by the child jobs.</span></span> <span data-ttu-id="3b31f-144">Задания, запущенные с помощью других командлетов, могут работать по-разному.</span><span class="sxs-lookup"><span data-stu-id="3b31f-144">Jobs started using other cmdlets might work differently.</span></span>

<span data-ttu-id="3b31f-145">Дочерние задания хранятся в свойстве **чилджобс** родительского объекта Job.</span><span class="sxs-lookup"><span data-stu-id="3b31f-145">The child jobs are stored in the **ChildJobs** property of the parent job object.</span></span> <span data-ttu-id="3b31f-146">Свойство **чилджобс** может содержать один или несколько дочерних объектов задания.</span><span class="sxs-lookup"><span data-stu-id="3b31f-146">The **ChildJobs** property can contain one or many child job objects.</span></span>
<span data-ttu-id="3b31f-147">Дочерние объекты задания имеют **имя** , **идентификатор** и **InstanceId** , отличающиеся от родительского задания, что позволяет управлять родительскими и дочерними заданиями по отдельности или как единое целое.</span><span class="sxs-lookup"><span data-stu-id="3b31f-147">The child job objects have a **Name** , **ID** , and **InstanceId** that differ from the parent job so that you can manage the parent and child jobs individually or as a unit.</span></span>

<span data-ttu-id="3b31f-148">Чтобы получить родительские и дочерние задания задания, используйте параметр **инклудечилджобс** `Get-Job` командлета.</span><span class="sxs-lookup"><span data-stu-id="3b31f-148">To get the parent and child jobs of a job, use the **IncludeChildJobs** parameter of the `Get-Job` cmdlet.</span></span> <span data-ttu-id="3b31f-149">Параметр **инклудечилджоб** появился в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="3b31f-149">The **IncludeChildJob** parameter was introduced in Windows PowerShell 3.0.</span></span>

```powershell
PS> Get-Job -IncludeChildJob

Id Name   PSJobTypeName State      HasMoreData   Location    Command
-- ----   ------------- -----      -----------   --------    -------
1  Job1   RemoteJob     Failed     True          localhost   Get-Process
2  Job2                 Completed  True          Server01    Get-Process
3  Job3                 Failed     False         localhost   Get-Process
```

<span data-ttu-id="3b31f-150">Чтобы получить родительское задание и только дочерние задания с определенным значением **состояния** , используйте параметр **чилджобстате** `Get-Job` командлета.</span><span class="sxs-lookup"><span data-stu-id="3b31f-150">To get the parent job and only the child jobs with a particular **State** value, use the **ChildJobState** parameter of the `Get-Job` cmdlet.</span></span> <span data-ttu-id="3b31f-151">Параметр **чилджобстате** появился в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="3b31f-151">The **ChildJobState** parameter was introduced in Windows PowerShell 3.0.</span></span>

```powershell
PS> Get-Job -ChildJobState Failed

Id Name   PSJobTypeName State      HasMoreData   Location    Command
-- ----   ------------- -----      -----------   --------    -------
1  Job1   RemoteJob     Failed     True          localhost   Get-Process
3  Job3                 Failed     False         localhost   Get-Process
```

<span data-ttu-id="3b31f-152">Чтобы получить дочерние задания во всех версиях PowerShell, используйте свойство **чилджоб** родительского задания.</span><span class="sxs-lookup"><span data-stu-id="3b31f-152">To get the child jobs of a job on all versions of PowerShell, use the **ChildJob** property of the parent job.</span></span>

```powershell
PS> (Get-Job Job1).ChildJobs

Id Name   PSJobTypeName State      HasMoreData   Location    Command
-- ----   ------------- -----      -----------   --------    -------
2  Job2                 Completed  True          Server01    Get-Process
3  Job3                 Failed     False         localhost   Get-Process
```

<span data-ttu-id="3b31f-153">Можно также использовать `Get-Job` команду в дочернем задании, как показано в следующей команде:</span><span class="sxs-lookup"><span data-stu-id="3b31f-153">You can also use a `Get-Job` command on the child job, as shown in the following command:</span></span>

```powershell
PS> Get-Job Job3

Id Name   PSJobTypeName State      HasMoreData   Location    Command
-- ----   ------------- -----      -----------   --------    -------
3  Job3                 Failed     False         localhost   Get-Process
```

<span data-ttu-id="3b31f-154">Настройка дочернего задания зависит от команды, используемой для запуска задания.</span><span class="sxs-lookup"><span data-stu-id="3b31f-154">The configuration of the child job depends on the command that you use to start the job.</span></span>

- <span data-ttu-id="3b31f-155">При использовании `Start-Job` для запуска задания на локальном компьютере задание состоит из родительского задания и дочернего задания, выполняющего команду.</span><span class="sxs-lookup"><span data-stu-id="3b31f-155">When you use `Start-Job` to start a job on a local computer, the job consists of an executive parent job and a child job that runs the command.</span></span>

- <span data-ttu-id="3b31f-156">При использовании параметра **AsJob** `Invoke-Command` в для запуска задания на одном или нескольких компьютерах задание состоит из родительского задания и дочернего задания для каждого задания, выполняемого на каждом компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b31f-156">When you use the **AsJob** parameter of `Invoke-Command` to start a job on one or more computers, the job consists of an executive parent job and a child job for each job run on each computer.</span></span>

- <span data-ttu-id="3b31f-157">При использовании `Invoke-Command` для выполнения `Start-Job` команды на одном или нескольких удаленных компьютерах результат совпадает с локальной командой, выполняемой на каждом удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b31f-157">When you use `Invoke-Command` to run a `Start-Job` command on one or more remote computers, the result is the same as a local command run on each remote computer.</span></span> <span data-ttu-id="3b31f-158">Команда возвращает объект задания для каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="3b31f-158">The command returns a job object for each computer.</span></span> <span data-ttu-id="3b31f-159">Объект задания состоит из родительского задания руководителя и одного дочернего задания, которое выполняет команду.</span><span class="sxs-lookup"><span data-stu-id="3b31f-159">The job object consists of an executive parent job and one child job that runs the command.</span></span>

<span data-ttu-id="3b31f-160">Родительское задание представляет все дочерние задания.</span><span class="sxs-lookup"><span data-stu-id="3b31f-160">The parent job represents all of the child jobs.</span></span> <span data-ttu-id="3b31f-161">При управлении родительским заданием также управляются связанные с ним дочерние задания.</span><span class="sxs-lookup"><span data-stu-id="3b31f-161">When you manage a parent job, you also manage the associated child jobs.</span></span> <span data-ttu-id="3b31f-162">Например, если остановить родительское задание, все дочерние задания будут остановлены.</span><span class="sxs-lookup"><span data-stu-id="3b31f-162">For example, if you stop a parent job, all child jobs are stopped.</span></span> <span data-ttu-id="3b31f-163">Если вы получаете результаты родительского задания, вы получаете результаты всех дочерних заданий.</span><span class="sxs-lookup"><span data-stu-id="3b31f-163">If you get the results of a parent job, you get the results of all child jobs.</span></span>

<span data-ttu-id="3b31f-164">Однако вы также можете управлять дочерними заданиями по отдельности.</span><span class="sxs-lookup"><span data-stu-id="3b31f-164">However, you can also manage child jobs individually.</span></span> <span data-ttu-id="3b31f-165">Это наиболее полезно, если нужно исследовать проблему с заданием или получить результаты только одного из нескольких дочерних заданий, запущенных с помощью параметра **AsJob** `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="3b31f-165">This is most useful when you want to investigate a problem with a job or get the results of only one of a number of child jobs started using the **AsJob** parameter of `Invoke-Command`.</span></span>

<span data-ttu-id="3b31f-166">Следующая команда использует параметр **AsJob** параметра `Invoke-Command` для запуска фоновых заданий на локальном компьютере и на двух удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="3b31f-166">The following command uses the **AsJob** parameter of `Invoke-Command` to start background jobs on the local computer and two remote computers.</span></span> <span data-ttu-id="3b31f-167">Команда сохраняет задание в `$j` переменной.</span><span class="sxs-lookup"><span data-stu-id="3b31f-167">The command saves the job in the `$j` variable.</span></span>

```powershell
PS> $j = Invoke-Command -ComputerName localhost, Server01, Server02 `
-Command {Get-Date} -AsJob
```

<span data-ttu-id="3b31f-168">При отображении свойств Name и **чилджоб** задания в `$j` отображается, что команда вернула объект задания с тремя дочерними заданиями, по одному для каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="3b31f-168">When you display the Name and **ChildJob** properties of the job in `$j`, it shows that the command returned a job object with three child jobs, one for each computer.</span></span>

```powershell
PS> $j | Format-List Name, ChildJobs

Name      : Job3
ChildJobs : {Job4, Job5, Job6}
```

<span data-ttu-id="3b31f-169">При отображении родительского задания показывается, что задание завершилось ошибкой.</span><span class="sxs-lookup"><span data-stu-id="3b31f-169">When you display the parent job, it shows that the job failed.</span></span>

```powershell
PS> $j

Id Name   PSJobTypeName State      HasMoreData   Location
-- ----   ------------- -----      -----------   --------
3  Job3   RemotingJob   Failed     False         localhost,Server...
```

<span data-ttu-id="3b31f-170">Но при выполнении `Get-Job` команды, которая получает дочерние задания, выходные данные показывают, что не удалось выполнить только одно дочернее задание.</span><span class="sxs-lookup"><span data-stu-id="3b31f-170">But when you run a `Get-Job` command that gets the child jobs, the output shows that only one child job failed.</span></span>

```powershell
PS> Get-Job -IncludeChildJobs

Id  Name   PSJobTypeName State      HasMoreData   Location    Command
--  ----   ------------- -----      -----------   --------    -------
3   Job3   RemotingJob   Failed     False         localhost,Server...
4   Job4                 Completed  True          localhost   Get-Date
5   Job5                 Failed     False         Server01    Get-Date
6   Job6                 Completed  True          Server02    Get-Date
```

<span data-ttu-id="3b31f-171">Чтобы получить результаты всех дочерних заданий, используйте `Receive-Job` командлет, чтобы получить результаты родительского задания.</span><span class="sxs-lookup"><span data-stu-id="3b31f-171">To get the results of all child jobs, use the `Receive-Job` cmdlet to get the results of the parent job.</span></span> <span data-ttu-id="3b31f-172">Но вы также можете получить результаты конкретного дочернего задания, как показано в следующей команде.</span><span class="sxs-lookup"><span data-stu-id="3b31f-172">But you can also get the results of a particular child job, as shown in the following command.</span></span>

```powershell
PS> Receive-Job -Name Job6 -Keep | Format-Table ComputerName,
>> DateTime -AutoSize
ComputerName DateTime
------------ --------
Server02     Thursday, March 13, 2008 4:16:03 PM
```

<span data-ttu-id="3b31f-173">Функция дочерних заданий в фоновых заданиях PowerShell обеспечивает более полный контроль над выполняемыми заданиями.</span><span class="sxs-lookup"><span data-stu-id="3b31f-173">The child jobs feature of PowerShell background jobs gives you more control over the jobs that you run.</span></span>

### <a name="job-types"></a><span data-ttu-id="3b31f-174">Типы заданий</span><span class="sxs-lookup"><span data-stu-id="3b31f-174">Job types</span></span>

<span data-ttu-id="3b31f-175">PowerShell поддерживает различные типы заданий для различных задач.</span><span class="sxs-lookup"><span data-stu-id="3b31f-175">PowerShell supports different types of jobs for different tasks.</span></span> <span data-ttu-id="3b31f-176">Начиная с Windows PowerShell 3,0, разработчики могут создавать "адаптеры источников заданий", которые добавляют новые типы заданий в PowerShell и включают в модули исходные адаптеры заданий.</span><span class="sxs-lookup"><span data-stu-id="3b31f-176">Beginning in Windows PowerShell 3.0, developers can write "job source adapters" that add new job types to PowerShell and include the job source adapters in modules.</span></span>
<span data-ttu-id="3b31f-177">При импорте модуля можно использовать новый тип задания в своем сеансе.</span><span class="sxs-lookup"><span data-stu-id="3b31f-177">When you import the module, you can use the new job type in your session.</span></span>

<span data-ttu-id="3b31f-178">Например, модуль PSScheduledJob добавляет запланированные задания, а модуль PSWorkflow добавляет задания рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="3b31f-178">For example, the PSScheduledJob module adds scheduled jobs and the PSWorkflow module adds workflow jobs.</span></span>

<span data-ttu-id="3b31f-179">Типы пользовательских заданий могут значительно отличаться от стандартных фоновых заданий PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3b31f-179">Custom jobs types might differ significantly from standard PowerShell background jobs.</span></span> <span data-ttu-id="3b31f-180">Например, запланированные задания сохраняются на диске; они не существуют только в определенном сеансе.</span><span class="sxs-lookup"><span data-stu-id="3b31f-180">For example, scheduled jobs are saved on disk; they do not exist only in a particular session.</span></span> <span data-ttu-id="3b31f-181">Задания рабочего процесса могут быть приостановлены и возобновлены.</span><span class="sxs-lookup"><span data-stu-id="3b31f-181">Workflow jobs can be suspended and resumed.</span></span>

<span data-ttu-id="3b31f-182">Командлеты, используемые для управления пользовательскими заданиями, зависят от типа задания.</span><span class="sxs-lookup"><span data-stu-id="3b31f-182">The cmdlets that you use to manage custom jobs depend on the job type.</span></span> <span data-ttu-id="3b31f-183">Для некоторых из них используются стандартные командлеты задания, такие как `Get-Job` и `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="3b31f-183">For some, you use the standard job cmdlets, such as `Get-Job` and `Start-Job`.</span></span> <span data-ttu-id="3b31f-184">Другие поставляются с специализированными командлетами, которые управляют только определенным типом задания.</span><span class="sxs-lookup"><span data-stu-id="3b31f-184">Others come with specialized cmdlets that manage only a particular type of job.</span></span> <span data-ttu-id="3b31f-185">Подробные сведения о типах настраиваемых заданий см. в разделах справки о типе задания.</span><span class="sxs-lookup"><span data-stu-id="3b31f-185">For detailed information about custom job types, see the help topics about the job type.</span></span>

<span data-ttu-id="3b31f-186">Чтобы найти тип задания, используйте `Get-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="3b31f-186">To find the job type of a job, use the `Get-Job` cmdlet.</span></span> <span data-ttu-id="3b31f-187">`Get-Job` Возвращает различные объекты задания для различных типов заданий.</span><span class="sxs-lookup"><span data-stu-id="3b31f-187">`Get-Job` returns different job objects for different types of jobs.</span></span> <span data-ttu-id="3b31f-188">Значение свойства **псжобтипенаме** объектов задания, которое `Get-Job` возвращает, указывает тип задания.</span><span class="sxs-lookup"><span data-stu-id="3b31f-188">The value of the **PSJobTypeName** property of the job objects that `Get-Job` returns indicates the job type.</span></span>

<span data-ttu-id="3b31f-189">В следующей таблице перечислены типы заданий, которые входят в состав PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3b31f-189">The following table lists the job types that come with PowerShell.</span></span>

|    <span data-ttu-id="3b31f-190">Тип задания</span><span class="sxs-lookup"><span data-stu-id="3b31f-190">Job Type</span></span>    |                       <span data-ttu-id="3b31f-191">Описание</span><span class="sxs-lookup"><span data-stu-id="3b31f-191">Description</span></span>                        |
| -------------- | -------------------------------------------------------- |
| <span data-ttu-id="3b31f-192">баккграунджоб</span><span class="sxs-lookup"><span data-stu-id="3b31f-192">BackgroundJob</span></span>  | <span data-ttu-id="3b31f-193">Запущено с помощью `Start-Job` командлета.</span><span class="sxs-lookup"><span data-stu-id="3b31f-193">Started using the `Start-Job` cmdlet.</span></span>                    |
| <span data-ttu-id="3b31f-194">ремотежоб</span><span class="sxs-lookup"><span data-stu-id="3b31f-194">RemoteJob</span></span>      | <span data-ttu-id="3b31f-195">Запущено использование параметра **AsJob**</span><span class="sxs-lookup"><span data-stu-id="3b31f-195">Started using the **AsJob** parameter of the</span></span>             |
|                | <span data-ttu-id="3b31f-196">`Invoke-Command`.</span><span class="sxs-lookup"><span data-stu-id="3b31f-196">`Invoke-Command` cmdlet.</span></span>                                 |
| <span data-ttu-id="3b31f-197">псворкфловжоб</span><span class="sxs-lookup"><span data-stu-id="3b31f-197">PSWorkflowJob</span></span>  | <span data-ttu-id="3b31f-198">Запущено использование параметра **AsJob** рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="3b31f-198">Started using the **AsJob** parameter of a workflow.</span></span>     |
| <span data-ttu-id="3b31f-199">PSScheduledJob</span><span class="sxs-lookup"><span data-stu-id="3b31f-199">PSScheduledJob</span></span> | <span data-ttu-id="3b31f-200">Экземпляр запланированного задания, запущенный триггером задания.</span><span class="sxs-lookup"><span data-stu-id="3b31f-200">An instance of a scheduled job started by a job trigger.</span></span> |
| <span data-ttu-id="3b31f-201">Цимжоб</span><span class="sxs-lookup"><span data-stu-id="3b31f-201">CIMJob</span></span>         | <span data-ttu-id="3b31f-202">Запущено использование параметра **AsJob** командлета из</span><span class="sxs-lookup"><span data-stu-id="3b31f-202">Started using the **AsJob** parameter of a cmdlet from a</span></span> |
|                | <span data-ttu-id="3b31f-203">Модуль CDXML.</span><span class="sxs-lookup"><span data-stu-id="3b31f-203">CDXML module.</span></span>                                            |
| <span data-ttu-id="3b31f-204">вмижоб</span><span class="sxs-lookup"><span data-stu-id="3b31f-204">WMIJob</span></span>         | <span data-ttu-id="3b31f-205">Запущено использование параметра **AsJob** командлета из</span><span class="sxs-lookup"><span data-stu-id="3b31f-205">Started using the **AsJob** parameter of a cmdlet from a</span></span> |
|                | <span data-ttu-id="3b31f-206">Модуль WMI.</span><span class="sxs-lookup"><span data-stu-id="3b31f-206">WMI module.</span></span>                                              |
| <span data-ttu-id="3b31f-207">PSEventJob</span><span class="sxs-lookup"><span data-stu-id="3b31f-207">PSEventJob</span></span>     | <span data-ttu-id="3b31f-208">Создано с использованием `Register-ObjectEvent` и указанием</span><span class="sxs-lookup"><span data-stu-id="3b31f-208">Created using`Register-ObjectEvent` and specifying an</span></span>    |
|                | <span data-ttu-id="3b31f-209">действие с параметром **Action** .</span><span class="sxs-lookup"><span data-stu-id="3b31f-209">action with the **Action** parameter.</span></span>                    |

<span data-ttu-id="3b31f-210">Примечание. перед использованием `Get-Job` командлета для получения заданий определенного типа убедитесь, что модуль, добавляющий тип задания, импортируется в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="3b31f-210">NOTE: Before using the `Get-Job` cmdlet to get jobs of a particular type, verify that the module that adds the job type is imported into the current session.</span></span>
<span data-ttu-id="3b31f-211">В противном случае не `Get-Job` получает задания этого типа.</span><span class="sxs-lookup"><span data-stu-id="3b31f-211">Otherwise, `Get-Job` does not get jobs of that type.</span></span>

## <a name="examples"></a><span data-ttu-id="3b31f-212">Примеры</span><span class="sxs-lookup"><span data-stu-id="3b31f-212">Examples</span></span>

<span data-ttu-id="3b31f-213">Следующие команды создают локальное фоновое задание, удаленное фоновое задание, задание рабочего процесса и запланированное задание.</span><span class="sxs-lookup"><span data-stu-id="3b31f-213">The following commands create a local background job, a remote background job, a workflow job, and a scheduled job.</span></span> <span data-ttu-id="3b31f-214">Затем он использует `Get-Job` командлет для получения заданий.</span><span class="sxs-lookup"><span data-stu-id="3b31f-214">Then, it uses the `Get-Job` cmdlet to get the jobs.</span></span> <span data-ttu-id="3b31f-215">`Get-Job` не получает запланированное задание, но возвращает все запущенные экземпляры запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="3b31f-215">`Get-Job` does not get the scheduled job, but it gets any started instances of the scheduled job.</span></span>

<span data-ttu-id="3b31f-216">Запуск фонового задания на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b31f-216">Start a background job on the local computer.</span></span>

```powershell
PS> Start-Job -Name LocalData {Get-Process}

Id Name        PSJobTypeName   State   HasMoreData   Location   Command
-- ----        -------------   -----   -----------   --------   -------
2  LocalData   BackgroundJob   Running        True   localhost  Get-Process
```

<span data-ttu-id="3b31f-217">Запуск фонового задания, выполняемого на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b31f-217">Start a background job that runs on a remote computer.</span></span>

```powershell
PS> Invoke-Command -ComputerName Server01 {Get-Process} `
-AsJob -JobName RemoteData

Id  Name        PSJobTypeName  State   HasMoreData   Location   Command
--  ----        -------------  -----   -----------   --------   -------
2   RemoteData  RemoteJob      Running        True   Server01   Get-Process
```

<span data-ttu-id="3b31f-218">Создание запланированного задания</span><span class="sxs-lookup"><span data-stu-id="3b31f-218">Create a scheduled job</span></span>

```powershell
PS>  Register-ScheduledJob -Name ScheduledJob -ScriptBlock `
 {Get-Process} -Trigger (New-JobTrigger -Once -At "3 PM")

Id         Name            JobTriggers     Command       Enabled
--         ----            -----------     -------       -------
1          ScheduledJob    1               Get-Process   True
```

<span data-ttu-id="3b31f-219">Создайте рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="3b31f-219">Create a workflow.</span></span>

```powershell
PS> workflow Test-Workflow {Get-Process}
```

<span data-ttu-id="3b31f-220">Запустите рабочий процесс как задание.</span><span class="sxs-lookup"><span data-stu-id="3b31f-220">Run the workflow as a job.</span></span>

```powershell

PS> Test-Workflow -AsJob -JobName TestWFJob

Id  Name       PSJobTypeName   State   HasMoreData   Location   Command
--  ----       -------------   -----   -----------   --------   -------
2   TestWFJob  PSWorkflowJob   NotStarted     True   localhost  Get-Process
```

<span data-ttu-id="3b31f-221">Получение заданий.</span><span class="sxs-lookup"><span data-stu-id="3b31f-221">Get the jobs.</span></span> <span data-ttu-id="3b31f-222">Команда не получает `Get-Job` запланированные задания, но получает экземпляры запущенного запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="3b31f-222">The `Get-Job` command does not get scheduled jobs, but it gets instances of the scheduled job that are started.</span></span>

```powershell
PS> Get-Job

Id  Name         PSJobTypeName  State     HasMoreData  Location  Command
--  ----         -------------  -----     -----------  --------  -------
2   LocalData    BackgroundJob  Completed True         localhost Get-Process
4   RemoteData   RemoteJob      Completed True         Server01  Get-Process
6   TestWFJob    PSWorkflowJob  Completed True         localhost WorkflowJob
8   ScheduledJob PSScheduledJob Completed True         localhost Get-Process
```

<span data-ttu-id="3b31f-223">Чтобы получить запланированные задания, используйте `Get-ScheduledJob` командлет.</span><span class="sxs-lookup"><span data-stu-id="3b31f-223">To get scheduled jobs, use the `Get-ScheduledJob` cmdlet.</span></span>

```powershell
PS> Get-ScheduledJob

Id         Name            JobTriggers     Command       Enabled
--         ----            -----------     -------       -------
1          ScheduledJob    1               Get-Process   True
```

## <a name="see-also"></a><span data-ttu-id="3b31f-224">См. также статью</span><span class="sxs-lookup"><span data-stu-id="3b31f-224">See also</span></span>

- [<span data-ttu-id="3b31f-225">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="3b31f-225">about_Jobs</span></span>](about_Jobs.md)
- [<span data-ttu-id="3b31f-226">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="3b31f-226">about_Remote_Jobs</span></span>](about_Remote_Jobs.md)
- [<span data-ttu-id="3b31f-227">about_Thread_Jobs</span><span class="sxs-lookup"><span data-stu-id="3b31f-227">about_Thread_Jobs</span></span>](about_Thread_Jobs.md)
- [<span data-ttu-id="3b31f-228">about_Remote</span><span class="sxs-lookup"><span data-stu-id="3b31f-228">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="3b31f-229">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="3b31f-229">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)
- [<span data-ttu-id="3b31f-230">Start-Job</span><span class="sxs-lookup"><span data-stu-id="3b31f-230">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="3b31f-231">Get-Job.</span><span class="sxs-lookup"><span data-stu-id="3b31f-231">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="3b31f-232">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="3b31f-232">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="3b31f-233">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="3b31f-233">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="3b31f-234">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="3b31f-234">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
- [<span data-ttu-id="3b31f-235">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="3b31f-235">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)
- [<span data-ttu-id="3b31f-236">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="3b31f-236">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)
- [<span data-ttu-id="3b31f-237">Exit-PSSession;</span><span class="sxs-lookup"><span data-stu-id="3b31f-237">Exit-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Exit-PSSession)
