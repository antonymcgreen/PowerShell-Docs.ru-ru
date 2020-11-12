---
description: Содержит сведения о том, как фоновые задания PowerShell выполняют команду или выражение в фоновом режиме без взаимодействия с текущим сеансом.
keywords: powershell,командлет
Locale: en-US
ms.date: 11/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_jobs?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Jobs
ms.openlocfilehash: 6ddb54bac62e7bc11a045874700acb3982a0093b
ms.sourcegitcommit: aac365f7813756e16b59322832a904e703e0465b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2020
ms.locfileid: "94524489"
---
# <a name="about-jobs"></a><span data-ttu-id="e69a5-104">О заданиях</span><span class="sxs-lookup"><span data-stu-id="e69a5-104">About Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="e69a5-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="e69a5-105">Short description</span></span>
<span data-ttu-id="e69a5-106">Содержит сведения о том, как фоновые задания PowerShell выполняют команду или выражение в фоновом режиме без взаимодействия с текущим сеансом.</span><span class="sxs-lookup"><span data-stu-id="e69a5-106">Provides information about how PowerShell background jobs run a command or expression in the background without interacting with the current session.</span></span>

## <a name="long-description"></a><span data-ttu-id="e69a5-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="e69a5-107">Long description</span></span>

<span data-ttu-id="e69a5-108">PowerShell параллельно выполняет команды и скрипты с помощью заданий.</span><span class="sxs-lookup"><span data-stu-id="e69a5-108">PowerShell concurrently runs commands and scripts through jobs.</span></span> <span data-ttu-id="e69a5-109">Существует три типа заданий, предоставляемых PowerShell для поддержки параллелизма.</span><span class="sxs-lookup"><span data-stu-id="e69a5-109">There are three jobs types provided by PowerShell to support concurrency.</span></span>

- <span data-ttu-id="e69a5-110">`RemoteJob` — Команды и сценарии выполняются в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="e69a5-110">`RemoteJob` - Commands and scripts run on a remote session.</span></span> <span data-ttu-id="e69a5-111">Дополнительные сведения см. в разделе [about_Remote_Jobs](about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="e69a5-111">For information, see [about_Remote_Jobs](about_Remote_Jobs.md).</span></span>
- <span data-ttu-id="e69a5-112">`BackgroundJob` — Команды и скрипты выполняются в отдельном процессе на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="e69a5-112">`BackgroundJob` - Commands and scripts run in a separate process on the local machine.</span></span>
- <span data-ttu-id="e69a5-113">`PSTaskJob` или `ThreadJob` — команды и скрипты выполняются в отдельном потоке в том же процессе на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="e69a5-113">`PSTaskJob` or `ThreadJob` - Commands and scripts run in a separate thread within the same process on the local machine.</span></span> <span data-ttu-id="e69a5-114">Дополнительные сведения см. в разделе [about_Thread_Jobs](/powershell/module/ThreadJob/about_Thread_Jobs).</span><span class="sxs-lookup"><span data-stu-id="e69a5-114">For more information, see [about_Thread_Jobs](/powershell/module/ThreadJob/about_Thread_Jobs).</span></span>

<span data-ttu-id="e69a5-115">Удаленное выполнение сценариев на отдельном компьютере или в отдельном процессе обеспечивает высокую изоляцию.</span><span class="sxs-lookup"><span data-stu-id="e69a5-115">Running scripts remotely, on a separate machine or in a separate process, provides great isolation.</span></span> <span data-ttu-id="e69a5-116">Любые ошибки, возникающие в удаленном задании, не влияют на другие выполняющиеся задания или родительский сеанс, запускающий задание.</span><span class="sxs-lookup"><span data-stu-id="e69a5-116">Any errors that occur in the remote job do not affect other running jobs or the parent session that started the job.</span></span> <span data-ttu-id="e69a5-117">Однако на уровне удаленного взаимодействия добавляются дополнительные издержки, в том числе сериализация объектов.</span><span class="sxs-lookup"><span data-stu-id="e69a5-117">However, the remoting layer adds overhead, including object serialization.</span></span> <span data-ttu-id="e69a5-118">Все объекты сериализуются и десериализуются, так как они передаются между родительским сеансом и удаленным сеансом (Job).</span><span class="sxs-lookup"><span data-stu-id="e69a5-118">All objects are serialized and deserialized as they are passed between the parent session and the remote (job) session.</span></span> <span data-ttu-id="e69a5-119">Сериализация больших сложных объектов данных может потреблять большие объемы ресурсов вычислений и памяти и передавать большие объемы данных по сети.</span><span class="sxs-lookup"><span data-stu-id="e69a5-119">Serialization of large complex data objects can consume large amounts of compute and memory resources and transfer large amounts of data across the network.</span></span>

<span data-ttu-id="e69a5-120">Задания на основе потоков не так надежны, как удаленные и фоновые задания, так как они выполняются в одном и том же процессе в разных потоках.</span><span class="sxs-lookup"><span data-stu-id="e69a5-120">Thread-based jobs are not as robust as remote and background jobs, because they run in the same process on different threads.</span></span> <span data-ttu-id="e69a5-121">Если в одном задании есть критическая ошибка, которая приводит к сбою процесса, то все остальные задания в этом процессе завершаются.</span><span class="sxs-lookup"><span data-stu-id="e69a5-121">If one job has a critical error that crashes the process, then all other jobs in the process are terminated.</span></span>

<span data-ttu-id="e69a5-122">Однако задания на основе потоков нуждаются в меньшей нагрузке.</span><span class="sxs-lookup"><span data-stu-id="e69a5-122">However, thread-based jobs require less overhead.</span></span> <span data-ttu-id="e69a5-123">Они не используют удаленный уровень или сериализацию.</span><span class="sxs-lookup"><span data-stu-id="e69a5-123">They don't use the remoting layer or serialization.</span></span> <span data-ttu-id="e69a5-124">Результирующие объекты возвращаются в виде ссылок на активные объекты в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="e69a5-124">The result objects are returned as references to live objects in the current session.</span></span> <span data-ttu-id="e69a5-125">Без такой нагрузки задания на основе потоков выполняются быстрее и используют меньше ресурсов, чем другие типы заданий.</span><span class="sxs-lookup"><span data-stu-id="e69a5-125">Without this overhead, thread-based jobs run faster and use fewer resources than the other job types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e69a5-126">Родительский сеанс, создавший задание, также отслеживает состояние задания и собирает данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="e69a5-126">The parent session that created the job also monitors the job status and collects pipeline data.</span></span> <span data-ttu-id="e69a5-127">Дочерний процесс задания завершается родительским процессом после того, как задание достигнет завершенного состояния.</span><span class="sxs-lookup"><span data-stu-id="e69a5-127">The job child process is terminated by the parent process once the job reaches a finished state.</span></span> <span data-ttu-id="e69a5-128">Если родительский сеанс завершается, все выполняющиеся дочерние задания завершаются вместе с их дочерними процессами.</span><span class="sxs-lookup"><span data-stu-id="e69a5-128">If the parent session is terminated, all running child jobs are terminated along with their child processes.</span></span>

<span data-ttu-id="e69a5-129">Существует два способа обойти это ограничение:</span><span class="sxs-lookup"><span data-stu-id="e69a5-129">There are two ways work around this limitation:</span></span>

1. <span data-ttu-id="e69a5-130">Используйте `Invoke-Command` для создания заданий, выполняемых в отключенных сеансах.</span><span class="sxs-lookup"><span data-stu-id="e69a5-130">Use `Invoke-Command` to create jobs that run in disconnected sessions.</span></span> <span data-ttu-id="e69a5-131">Дополнительные сведения см. в разделе [about_Remote_Jobs](about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="e69a5-131">For more information, see [about_Remote_Jobs](about_Remote_Jobs.md).</span></span>
1. <span data-ttu-id="e69a5-132">Используйте `Start-Process` для создания нового процесса, а не задания.</span><span class="sxs-lookup"><span data-stu-id="e69a5-132">Use `Start-Process` to create a new process rather than a job.</span></span> <span data-ttu-id="e69a5-133">Дополнительные сведения см. в разделе [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).</span><span class="sxs-lookup"><span data-stu-id="e69a5-133">For more information, see [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).</span></span>

## <a name="the-job-cmdlets"></a><span data-ttu-id="e69a5-134">Командлеты задания</span><span class="sxs-lookup"><span data-stu-id="e69a5-134">The job cmdlets</span></span>

|<span data-ttu-id="e69a5-135">Командлет</span><span class="sxs-lookup"><span data-stu-id="e69a5-135">Cmdlet</span></span>          |<span data-ttu-id="e69a5-136">Описание</span><span class="sxs-lookup"><span data-stu-id="e69a5-136">Description</span></span>                                            |
|----------------|-------------------------------------------------------|
|`Start-Job`     |<span data-ttu-id="e69a5-137">Запускает фоновое задание на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="e69a5-137">Starts a background job on a local computer.</span></span>           |
|`Get-Job`       |<span data-ttu-id="e69a5-138">Возвращает фоновые задания, запущенные в</span><span class="sxs-lookup"><span data-stu-id="e69a5-138">Gets the background jobs that were started in the</span></span>      |
|                |<span data-ttu-id="e69a5-139">текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="e69a5-139">current session.</span></span>                                       |
|`Receive-Job`   |<span data-ttu-id="e69a5-140">Возвращает результаты фоновых заданий.</span><span class="sxs-lookup"><span data-stu-id="e69a5-140">Gets the results of background jobs.</span></span>                   |
|`Stop-Job`      |<span data-ttu-id="e69a5-141">Останавливает фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="e69a5-141">Stops a background job.</span></span>                                |
|`Wait-Job`      |<span data-ttu-id="e69a5-142">Подавляет командную строку до тех пор, пока одно или все задания не будут</span><span class="sxs-lookup"><span data-stu-id="e69a5-142">Suppresses the command prompt until one or all jobs are</span></span>|
|                |<span data-ttu-id="e69a5-143">завершения.</span><span class="sxs-lookup"><span data-stu-id="e69a5-143">complete.</span></span>                                              |
|`Remove-Job`    |<span data-ttu-id="e69a5-144">Удаляет фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="e69a5-144">Deletes a background job.</span></span>                              |
|`Invoke-Command`|<span data-ttu-id="e69a5-145">Параметр **AsJob** создает фоновое задание на</span><span class="sxs-lookup"><span data-stu-id="e69a5-145">The **AsJob** parameter creates a background job on a</span></span>  |
|                |<span data-ttu-id="e69a5-146">удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="e69a5-146">remote computer.</span></span> <span data-ttu-id="e69a5-147">Можно использовать `Invoke-Command` для запуска</span><span class="sxs-lookup"><span data-stu-id="e69a5-147">You can use `Invoke-Command` to run</span></span>   |
|                |<span data-ttu-id="e69a5-148">Любая команда задания удаленно, включая `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="e69a5-148">any job command remotely, including `Start-Job`.</span></span>       |

## <a name="how-to-start-a-job-on-the-local-computer"></a><span data-ttu-id="e69a5-149">Запуск задания на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="e69a5-149">How to start a job on the local computer</span></span>

<span data-ttu-id="e69a5-150">Чтобы запустить фоновое задание на локальном компьютере, используйте `Start-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="e69a5-150">To start a background job on the local computer, use the `Start-Job` cmdlet.</span></span>

<span data-ttu-id="e69a5-151">Чтобы написать `Start-Job` команду, заключите команду, которая выполняется заданием, в фигурные скобки ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="e69a5-151">To write a `Start-Job` command, enclose the command that the job runs in curly braces (`{}`).</span></span> <span data-ttu-id="e69a5-152">Используйте параметр **ScriptBlock** для указания команды.</span><span class="sxs-lookup"><span data-stu-id="e69a5-152">Use the **ScriptBlock** parameter to specify the command.</span></span>

<span data-ttu-id="e69a5-153">Следующая команда запускает фоновое задание, которое выполняет `Get-Process` команду на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="e69a5-153">The following command starts a background job that runs a `Get-Process` command on the local computer.</span></span>

```powershell
Start-Job -ScriptBlock {Get-Process}
```

<span data-ttu-id="e69a5-154">Когда вы запускаете фоновое задание, Командная строка возвращается немедленно, даже если выполнение задания занимает длительное время.</span><span class="sxs-lookup"><span data-stu-id="e69a5-154">When you start a background job, the command prompt returns immediately, even if the job takes an extended time to complete.</span></span> <span data-ttu-id="e69a5-155">Пока задание выполняется, можно продолжать работу с данным сеансом.</span><span class="sxs-lookup"><span data-stu-id="e69a5-155">You can continue to work in the session without interruption while the job runs.</span></span>

<span data-ttu-id="e69a5-156">`Start-Job`Команда возвращает объект, представляющий задание.</span><span class="sxs-lookup"><span data-stu-id="e69a5-156">The `Start-Job` command returns an object that represents the job.</span></span> <span data-ttu-id="e69a5-157">Объект задания содержит полезную информацию о задании, но не содержит результатов его выполнения.</span><span class="sxs-lookup"><span data-stu-id="e69a5-157">The job object contains useful information about the job, but it does not contain the job results.</span></span>

<span data-ttu-id="e69a5-158">Вы можете сохранить объект задания в переменной, а затем использовать его вместе с другими командлетами **задания** для управления фоновыми заданиями.</span><span class="sxs-lookup"><span data-stu-id="e69a5-158">You can save the job object in a variable and then use it with the other **Job** cmdlets to manage the background job.</span></span> <span data-ttu-id="e69a5-159">Следующая команда запускает объект задания и сохраняет результирующий объект задания в `$job` переменной.</span><span class="sxs-lookup"><span data-stu-id="e69a5-159">The following command starts a job object and saves the resulting job object in the `$job` variable.</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Process}
```

<span data-ttu-id="e69a5-160">Начиная с версии PowerShell 6,0 можно использовать оператор Background ( `&` ) в конце конвейера для запуска фонового задания.</span><span class="sxs-lookup"><span data-stu-id="e69a5-160">Beginning in PowerShell 6.0, you can use the background operator (`&`) at the end of a pipeline to start a background job.</span></span> <span data-ttu-id="e69a5-161">Дополнительные сведения см. в разделе [оператор Background](about_Operators.md#background-operator-).</span><span class="sxs-lookup"><span data-stu-id="e69a5-161">For more information, see [background operator](about_Operators.md#background-operator-).</span></span>

<span data-ttu-id="e69a5-162">Использование оператора Background функционально эквивалентно использованию `Start-Job` командлета в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="e69a5-162">Using the background operator is functionally equivalent to using the `Start-Job` cmdlet in the previous example.</span></span>

```powershell
$job = Get-Process &
```

## <a name="getting-job-objects"></a><span data-ttu-id="e69a5-163">Получение объектов заданий</span><span class="sxs-lookup"><span data-stu-id="e69a5-163">Getting job objects</span></span>

<span data-ttu-id="e69a5-164">`Get-Job`Командлет возвращает объекты, представляющие фоновые задания, которые были запущены в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="e69a5-164">The `Get-Job` cmdlet returns objects that represent the background jobs that were started in the current session.</span></span> <span data-ttu-id="e69a5-165">Без параметров `Get-Job` возвращает все задания, запущенные в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="e69a5-165">Without parameters, `Get-Job` returns all of the jobs that were started in the current session.</span></span>

```powershell
Get-Job
```

<span data-ttu-id="e69a5-166">Объект задания содержит состояние задания, которое указывает, завершено ли задание.</span><span class="sxs-lookup"><span data-stu-id="e69a5-166">The job object contains the state of the job, which indicates whether the job has finished.</span></span> <span data-ttu-id="e69a5-167">Завершенное задание имеет состояние " **завершено** " или " **сбой** ".</span><span class="sxs-lookup"><span data-stu-id="e69a5-167">A finished job has a state of **Complete** or **Failed**.</span></span> <span data-ttu-id="e69a5-168">Задание также может быть **заблокировано** или **заработано**.</span><span class="sxs-lookup"><span data-stu-id="e69a5-168">A job might also be **Blocked** or **Running**.</span></span>

```Output
Id  Name  PSJobTypeName State      HasMoreData  Location   Command
--  ----  ------------- -----      -----------  --------   -------
1   Job1  BackgroundJob Complete   True         localhost  Get-Process
```

<span data-ttu-id="e69a5-169">Вы можете сохранить объект задания в переменной и использовать его для представления задания в более поздней команде.</span><span class="sxs-lookup"><span data-stu-id="e69a5-169">You can save the job object in a variable and use it to represent the job in a later command.</span></span> <span data-ttu-id="e69a5-170">Следующая команда возвращает задание с ИДЕНТИФИКАТОРом 1 и сохраняет его в `$job` переменной.</span><span class="sxs-lookup"><span data-stu-id="e69a5-170">The following command gets the job with ID 1 and saves it in the `$job` variable.</span></span>

```powershell
$job = Get-Job -Id 1
```

## <a name="getting-the-results-of-a-job"></a><span data-ttu-id="e69a5-171">Получение результатов задания</span><span class="sxs-lookup"><span data-stu-id="e69a5-171">Getting the results of a job</span></span>

<span data-ttu-id="e69a5-172">При выполнении фонового задания результаты не отображаются немедленно.</span><span class="sxs-lookup"><span data-stu-id="e69a5-172">When you run a background job, the results do not appear immediately.</span></span> <span data-ttu-id="e69a5-173">Чтобы получить результаты фонового задания, используйте `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="e69a5-173">To get the results of a background job, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="e69a5-174">В следующем примере `Receive-Job` командлет получает результаты задания с помощью объекта задания в `$job` переменной.</span><span class="sxs-lookup"><span data-stu-id="e69a5-174">The following example, the `Receive-Job` cmdlet gets the results of the job using job object in the `$job` variable.</span></span>

```powershell
Receive-Job -Job $job
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)    Id ProcessName
-------  ------    -----      ----- -----   ------    -- -----------
    103       4    11328       9692    56           1176 audiodg
    804      14    12228      14108   100   101.74  1740 CcmExec
    668       7     2672       6168   104    32.26   488 csrss
...
```

<span data-ttu-id="e69a5-175">Результаты задания можно сохранить в переменной.</span><span class="sxs-lookup"><span data-stu-id="e69a5-175">You can save the results of a job in a variable.</span></span> <span data-ttu-id="e69a5-176">Следующая команда сохраняет результаты задания в `$job` переменной в `$results` переменной.</span><span class="sxs-lookup"><span data-stu-id="e69a5-176">The following command saves the results of the job in the `$job` variable to the `$results` variable.</span></span>

```powershell
$results = Receive-Job -Job $job
```

### <a name="getting-and-keeping-partial-job-results"></a><span data-ttu-id="e69a5-177">Получение и хранение результатов частичной работы</span><span class="sxs-lookup"><span data-stu-id="e69a5-177">Getting and keeping partial job results</span></span>

<span data-ttu-id="e69a5-178">`Receive-Job`Командлет возвращает результаты фонового задания.</span><span class="sxs-lookup"><span data-stu-id="e69a5-178">The `Receive-Job` cmdlet gets the results of a background job.</span></span> <span data-ttu-id="e69a5-179">Если задание завершено, `Receive-Job` получает результаты всех заданий.</span><span class="sxs-lookup"><span data-stu-id="e69a5-179">If the job is complete, `Receive-Job` gets all job results.</span></span> <span data-ttu-id="e69a5-180">Если задание по-прежнему выполняется, `Receive-Job` получает результаты, которые были созданы до сих пор.</span><span class="sxs-lookup"><span data-stu-id="e69a5-180">If the job is still running, `Receive-Job` gets the results that have been generated thus far.</span></span> <span data-ttu-id="e69a5-181">`Receive-Job`Чтобы получить оставшиеся результаты, можно выполнить команды еще раз.</span><span class="sxs-lookup"><span data-stu-id="e69a5-181">You can run `Receive-Job` commands again to get the remaining results.</span></span>

<span data-ttu-id="e69a5-182">По умолчанию `Receive-Job` удаляет результаты из кэша, в котором хранятся результаты задания.</span><span class="sxs-lookup"><span data-stu-id="e69a5-182">By default, `Receive-Job` deletes the results from the cache where job results are stored.</span></span> <span data-ttu-id="e69a5-183">При `Receive-Job` повторном запуске вы получаете только новые результаты, поступившие после первого запуска.</span><span class="sxs-lookup"><span data-stu-id="e69a5-183">When you run `Receive-Job` again, you get only the new results that arrived after the first run.</span></span>

<span data-ttu-id="e69a5-184">Следующие команды показывают результаты `Receive-Job` выполнения команд до завершения задания.</span><span class="sxs-lookup"><span data-stu-id="e69a5-184">The following commands show the results of `Receive-Job` commands run before the job is complete.</span></span>

```powershell
C:\PS> Receive-Job -Job $job

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    103       4    11328       9692    56            1176 audiodg
    804      14    12228      14108   100   101.74   1740 CcmExec

C:\PS> Receive-Job -Job $job

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    68       3     2632        664    29     0.36   1388 ccmsetup
   749      22    21468      19940   203   122.13   3644 communicator
   905       7     2980       2628    34   197.97    424 csrss
  1121      25    28408      32940   174   430.14   3048 explorer
```

<span data-ttu-id="e69a5-185">Используйте параметр **держитесь** , чтобы предотвратить `Receive-Job` Удаление возвращаемых результатов задания.</span><span class="sxs-lookup"><span data-stu-id="e69a5-185">Use the **Keep** parameter to prevent `Receive-Job` from deleting the job results that are returned.</span></span> <span data-ttu-id="e69a5-186">Приведенные ниже команды демонстрируют последствия использования параметра **сохранения** для задания, которое еще не завершено.</span><span class="sxs-lookup"><span data-stu-id="e69a5-186">The following commands show the effect of using the **Keep** parameter on a job that is not yet complete.</span></span>

```powershell
C:\PS> Receive-Job -Job $job -Keep

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    103       4    11328       9692    56            1176 audiodg
    804      14    12228      14108   100   101.74   1740 CcmExec

C:\PS> Receive-Job -Job $job -Keep

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    103       4    11328       9692    56            1176 audiodg
    804      14    12228      14108   100   101.74   1740 CcmExec
     68       3     2632        664    29     0.36   1388 ccmsetup
    749      22    21468      19940   203   122.13   3644 communicator
    905       7     2980       2628    34   197.97    424 csrss
   1121      25    28408      32940   174   430.14   3048 explorer
```

### <a name="waiting-for-the-results"></a><span data-ttu-id="e69a5-187">Ожидание результатов</span><span class="sxs-lookup"><span data-stu-id="e69a5-187">Waiting for the results</span></span>

<span data-ttu-id="e69a5-188">При выполнении команды, выполнение которой занимает много времени, можно использовать свойства объекта задания, чтобы определить, когда задание завершено.</span><span class="sxs-lookup"><span data-stu-id="e69a5-188">If you run a command that takes a long time to complete, you can use the properties of the job object to determine when the job is complete.</span></span> <span data-ttu-id="e69a5-189">Следующая команда использует `Get-Job` объект для получения всех фоновых заданий в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="e69a5-189">The following command uses the `Get-Job` object to get all of the background jobs in the current session.</span></span>

```powershell
Get-Job
```

<span data-ttu-id="e69a5-190">Результаты отображаются в таблице.</span><span class="sxs-lookup"><span data-stu-id="e69a5-190">The results appear in a table.</span></span> <span data-ttu-id="e69a5-191">Состояние задания отображается в столбце **состояние** .</span><span class="sxs-lookup"><span data-stu-id="e69a5-191">The status of the job appears in the **State** column.</span></span>

```Output
Id Name  PSJobTypeName State    HasMoreData Location  Command
-- ----  ------------- -----    ----------- --------  -------
1  Job1  BackgroundJob Complete True        localhost Get-Process
2  Job2  BackgroundJob Running  True        localhost Get-EventLog -Log ...
3  Job3  BackgroundJob Complete True        localhost dir -Path C:\* -Re...
```

<span data-ttu-id="e69a5-192">В этом случае свойство **State** показывает, что задание 2 все еще выполняется.</span><span class="sxs-lookup"><span data-stu-id="e69a5-192">In this case, the **State** property reveals that Job 2 is still running.</span></span> <span data-ttu-id="e69a5-193">Если вы использовали `Receive-Job` командлет для получения результатов задания прямо сейчас, результаты будут неполными.</span><span class="sxs-lookup"><span data-stu-id="e69a5-193">If you were to use the `Receive-Job` cmdlet to get the job results now, the results would be incomplete.</span></span> <span data-ttu-id="e69a5-194">Можно `Receive-Job` многократно использовать командлет для получения всех результатов.</span><span class="sxs-lookup"><span data-stu-id="e69a5-194">You can use the `Receive-Job` cmdlet repeatedly to get all of the results.</span></span> <span data-ttu-id="e69a5-195">Чтобы определить, когда задание завершено, используйте свойство **State** .</span><span class="sxs-lookup"><span data-stu-id="e69a5-195">Use the **State** property to determine when the job is complete.</span></span>

<span data-ttu-id="e69a5-196">Можно также использовать параметр **Wait** `Receive-Job` командлета.</span><span class="sxs-lookup"><span data-stu-id="e69a5-196">You can also use the **Wait** parameter of the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="e69a5-197">При использовании этого параметра командлет не возвращает командную строку, пока задание не будет завершено и все результаты будут доступны.</span><span class="sxs-lookup"><span data-stu-id="e69a5-197">When use use this parameter, the cmdlet does not return the command prompt until the job is completed and all results are available.</span></span>

<span data-ttu-id="e69a5-198">Можно также использовать `Wait-Job` командлет для ожидания любого или всех результатов задания.</span><span class="sxs-lookup"><span data-stu-id="e69a5-198">You can also use the `Wait-Job` cmdlet to wait for any or all of the results of the job.</span></span> <span data-ttu-id="e69a5-199">`Wait-Job` позволяет ожидать одно или несколько конкретных заданий или всех заданий.</span><span class="sxs-lookup"><span data-stu-id="e69a5-199">`Wait-Job` lets you wait for one or more specific job or for all jobs.</span></span>
<span data-ttu-id="e69a5-200">Следующая команда использует `Wait-Job` командлет для ожидания задания с **идентификатором** .</span><span class="sxs-lookup"><span data-stu-id="e69a5-200">The following command uses the `Wait-Job` cmdlet to wait for a job with **ID**</span></span>
10.

```powershell
Wait-Job -ID 10
```

<span data-ttu-id="e69a5-201">В результате Командная строка PowerShell подавляется до завершения задания.</span><span class="sxs-lookup"><span data-stu-id="e69a5-201">As a result, the PowerShell prompt is suppressed until the job is completed.</span></span>

<span data-ttu-id="e69a5-202">Можно также дождаться заранее определенного периода времени.</span><span class="sxs-lookup"><span data-stu-id="e69a5-202">You can also wait for a predetermined period of time.</span></span> <span data-ttu-id="e69a5-203">Эта команда использует параметр **timeout** , чтобы ограничить время ожидания 120 секунд.</span><span class="sxs-lookup"><span data-stu-id="e69a5-203">This command uses the **Timeout** parameter to limit the wait to 120 seconds.</span></span> <span data-ttu-id="e69a5-204">По истечении этого времени Командная строка возвращает значение, но задание продолжит выполняться в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="e69a5-204">When the time expires, the command prompt returns, but the job continues to run in the background.</span></span>

```powershell
Wait-Job -ID 10 -Timeout 120
```

## <a name="stopping-a-job"></a><span data-ttu-id="e69a5-205">Остановка задания</span><span class="sxs-lookup"><span data-stu-id="e69a5-205">Stopping a job</span></span>

<span data-ttu-id="e69a5-206">Чтобы прерывать фоновое задание, используйте `Stop-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="e69a5-206">To stop a background job, use the `Stop-Job` cmdlet.</span></span> <span data-ttu-id="e69a5-207">Следующая команда запускает задание для получения каждой записи в журнале системных событий.</span><span class="sxs-lookup"><span data-stu-id="e69a5-207">The following command starts a job to get every entry in the System event log.</span></span> <span data-ttu-id="e69a5-208">Объект задания сохраняется в `$job` переменной.</span><span class="sxs-lookup"><span data-stu-id="e69a5-208">It saves the job object in the `$job` variable.</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-EventLog -Log System}
```

<span data-ttu-id="e69a5-209">Следующая команда останавливает задание.</span><span class="sxs-lookup"><span data-stu-id="e69a5-209">The following command stops the job.</span></span> <span data-ttu-id="e69a5-210">Он использует оператор конвейера ( `|` ) для отправки задания в переменной в `$job` `Stop-Job` .</span><span class="sxs-lookup"><span data-stu-id="e69a5-210">It uses a pipeline operator (`|`) to send the job in the `$job` variable to `Stop-Job`.</span></span>

```powershell
$job | Stop-Job
```

## <a name="deleting-a-job"></a><span data-ttu-id="e69a5-211">Удаление задания</span><span class="sxs-lookup"><span data-stu-id="e69a5-211">Deleting a job</span></span>

<span data-ttu-id="e69a5-212">Чтобы удалить фоновое задание, используйте `Remove-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="e69a5-212">To delete a background job, use the `Remove-Job` cmdlet.</span></span> <span data-ttu-id="e69a5-213">Следующая команда удаляет задание в `$job` переменной.</span><span class="sxs-lookup"><span data-stu-id="e69a5-213">The following command deletes the job in the `$job` variable.</span></span>

```powershell
Remove-Job -Job $job
```

## <a name="investigating-a-failed-job"></a><span data-ttu-id="e69a5-214">Исследование невыполненного задания</span><span class="sxs-lookup"><span data-stu-id="e69a5-214">Investigating a failed job</span></span>

<span data-ttu-id="e69a5-215">Задания могут завершаться сбоем по многим причинам.</span><span class="sxs-lookup"><span data-stu-id="e69a5-215">Jobs can fail for many reasons.</span></span> <span data-ttu-id="e69a5-216">Объект задания содержит свойство **Reason** , содержащее сведения о причине сбоя.</span><span class="sxs-lookup"><span data-stu-id="e69a5-216">the job object contains a **Reason** property that contains information about the cause of the failure.</span></span>

<span data-ttu-id="e69a5-217">В следующем примере запускается задание без требуемых учетных данных.</span><span class="sxs-lookup"><span data-stu-id="e69a5-217">The following example starts a job without the required credentials.</span></span>

```powershell
$job = Start-Job -ScriptBlock {New-Item -Path HKLM:\Software\MyCompany}
Get-Job $job

Id Name  PSJobTypeName State  HasMoreData  Location  Command
-- ----  ------------- -----  -----------  --------  -------
1  Job1  BackgroundJob Failed False        localhost New-Item -Path HKLM:...
```

<span data-ttu-id="e69a5-218">Проверьте свойство **Reason** , чтобы найти ошибку, вызвавшую сбой задания.</span><span class="sxs-lookup"><span data-stu-id="e69a5-218">Inspect the **Reason** property to find the error that caused the job to fail.</span></span>

```powershell
$job.ChildJobs[0].JobStateInfo.Reason
```

<span data-ttu-id="e69a5-219">В этом случае задание завершилось сбоем, так как удаленный компьютер требует явных учетных данных для выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="e69a5-219">In this case, the job failed because the remote computer required explicit credentials to run the command.</span></span> <span data-ttu-id="e69a5-220">Свойство **Reason** содержит следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="e69a5-220">The **Reason** property contains the following message:</span></span>

> <span data-ttu-id="e69a5-221">Сбой подключения к удаленному серверу со следующим сообщением об ошибке: "отказано в доступе".</span><span class="sxs-lookup"><span data-stu-id="e69a5-221">Connecting to remote server failed with the following error message: "Access is denied".</span></span>

## <a name="see-also"></a><span data-ttu-id="e69a5-222">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e69a5-222">See also</span></span>

- [<span data-ttu-id="e69a5-223">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="e69a5-223">about_Remote_Jobs</span></span>](about_Remote_Jobs.md)
- [<span data-ttu-id="e69a5-224">about_Thread_Jobs</span><span class="sxs-lookup"><span data-stu-id="e69a5-224">about_Thread_Jobs</span></span>](about_Thread_Jobs.md)
- [<span data-ttu-id="e69a5-225">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="e69a5-225">about_Job_Details</span></span>](about_Job_Details.md)
- [<span data-ttu-id="e69a5-226">about_Remote</span><span class="sxs-lookup"><span data-stu-id="e69a5-226">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="e69a5-227">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="e69a5-227">about_PSSessions</span></span>](about_PSSessions.md)
- [<span data-ttu-id="e69a5-228">Start-Job</span><span class="sxs-lookup"><span data-stu-id="e69a5-228">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="e69a5-229">Get-Job.</span><span class="sxs-lookup"><span data-stu-id="e69a5-229">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="e69a5-230">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="e69a5-230">Receive-Job</span></span>](xref:Microsoft.PowerShell.Core.Receive-Job)
- [<span data-ttu-id="e69a5-231">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="e69a5-231">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="e69a5-232">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="e69a5-232">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="e69a5-233">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="e69a5-233">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
- [<span data-ttu-id="e69a5-234">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="e69a5-234">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)
