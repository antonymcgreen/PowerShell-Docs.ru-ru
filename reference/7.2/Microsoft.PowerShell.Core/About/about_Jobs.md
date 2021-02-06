---
description: Содержит сведения о том, как фоновые задания PowerShell выполняют команду или выражение в фоновом режиме без взаимодействия с текущим сеансом.
Locale: en-US
ms.date: 11/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_jobs?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Jobs
ms.openlocfilehash: 862fbf54b927bb70c68e4b3cc43c564f178f9db5
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599375"
---
# <a name="about-jobs"></a><span data-ttu-id="f9d51-103">О заданиях</span><span class="sxs-lookup"><span data-stu-id="f9d51-103">About Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="f9d51-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="f9d51-104">Short description</span></span>
<span data-ttu-id="f9d51-105">Содержит сведения о том, как фоновые задания PowerShell выполняют команду или выражение в фоновом режиме без взаимодействия с текущим сеансом.</span><span class="sxs-lookup"><span data-stu-id="f9d51-105">Provides information about how PowerShell background jobs run a command or expression in the background without interacting with the current session.</span></span>

## <a name="long-description"></a><span data-ttu-id="f9d51-106">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="f9d51-106">Long description</span></span>

<span data-ttu-id="f9d51-107">PowerShell параллельно выполняет команды и скрипты с помощью заданий.</span><span class="sxs-lookup"><span data-stu-id="f9d51-107">PowerShell concurrently runs commands and scripts through jobs.</span></span> <span data-ttu-id="f9d51-108">Существует три типа заданий, предоставляемых PowerShell для поддержки параллелизма.</span><span class="sxs-lookup"><span data-stu-id="f9d51-108">There are three jobs types provided by PowerShell to support concurrency.</span></span>

- <span data-ttu-id="f9d51-109">`RemoteJob` — Команды и сценарии выполняются в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="f9d51-109">`RemoteJob` - Commands and scripts run on a remote session.</span></span> <span data-ttu-id="f9d51-110">Дополнительные сведения см. в разделе [about_Remote_Jobs](about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="f9d51-110">For information, see [about_Remote_Jobs](about_Remote_Jobs.md).</span></span>
- <span data-ttu-id="f9d51-111">`BackgroundJob` — Команды и скрипты выполняются в отдельном процессе на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="f9d51-111">`BackgroundJob` - Commands and scripts run in a separate process on the local machine.</span></span>
- <span data-ttu-id="f9d51-112">`PSTaskJob` или `ThreadJob` — команды и скрипты выполняются в отдельном потоке в том же процессе на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="f9d51-112">`PSTaskJob` or `ThreadJob` - Commands and scripts run in a separate thread within the same process on the local machine.</span></span> <span data-ttu-id="f9d51-113">Дополнительные сведения см. в разделе [about_Thread_Jobs](/powershell/module/ThreadJob/about_Thread_Jobs).</span><span class="sxs-lookup"><span data-stu-id="f9d51-113">For more information, see [about_Thread_Jobs](/powershell/module/ThreadJob/about_Thread_Jobs).</span></span>

<span data-ttu-id="f9d51-114">Удаленное выполнение сценариев на отдельном компьютере или в отдельном процессе обеспечивает высокую изоляцию.</span><span class="sxs-lookup"><span data-stu-id="f9d51-114">Running scripts remotely, on a separate machine or in a separate process, provides great isolation.</span></span> <span data-ttu-id="f9d51-115">Любые ошибки, возникающие в удаленном задании, не влияют на другие выполняющиеся задания или родительский сеанс, запускающий задание.</span><span class="sxs-lookup"><span data-stu-id="f9d51-115">Any errors that occur in the remote job do not affect other running jobs or the parent session that started the job.</span></span> <span data-ttu-id="f9d51-116">Однако на уровне удаленного взаимодействия добавляются дополнительные издержки, в том числе сериализация объектов.</span><span class="sxs-lookup"><span data-stu-id="f9d51-116">However, the remoting layer adds overhead, including object serialization.</span></span> <span data-ttu-id="f9d51-117">Все объекты сериализуются и десериализуются, так как они передаются между родительским сеансом и удаленным сеансом (Job).</span><span class="sxs-lookup"><span data-stu-id="f9d51-117">All objects are serialized and deserialized as they are passed between the parent session and the remote (job) session.</span></span> <span data-ttu-id="f9d51-118">Сериализация больших сложных объектов данных может потреблять большие объемы ресурсов вычислений и памяти и передавать большие объемы данных по сети.</span><span class="sxs-lookup"><span data-stu-id="f9d51-118">Serialization of large complex data objects can consume large amounts of compute and memory resources and transfer large amounts of data across the network.</span></span>

<span data-ttu-id="f9d51-119">Задания на основе потоков не так надежны, как удаленные и фоновые задания, так как они выполняются в одном и том же процессе в разных потоках.</span><span class="sxs-lookup"><span data-stu-id="f9d51-119">Thread-based jobs are not as robust as remote and background jobs, because they run in the same process on different threads.</span></span> <span data-ttu-id="f9d51-120">Если в одном задании есть критическая ошибка, которая приводит к сбою процесса, то все остальные задания в этом процессе завершаются.</span><span class="sxs-lookup"><span data-stu-id="f9d51-120">If one job has a critical error that crashes the process, then all other jobs in the process are terminated.</span></span>

<span data-ttu-id="f9d51-121">Однако задания на основе потоков нуждаются в меньшей нагрузке.</span><span class="sxs-lookup"><span data-stu-id="f9d51-121">However, thread-based jobs require less overhead.</span></span> <span data-ttu-id="f9d51-122">Они не используют удаленный уровень или сериализацию.</span><span class="sxs-lookup"><span data-stu-id="f9d51-122">They don't use the remoting layer or serialization.</span></span> <span data-ttu-id="f9d51-123">Результирующие объекты возвращаются в виде ссылок на активные объекты в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="f9d51-123">The result objects are returned as references to live objects in the current session.</span></span> <span data-ttu-id="f9d51-124">Без такой нагрузки задания на основе потоков выполняются быстрее и используют меньше ресурсов, чем другие типы заданий.</span><span class="sxs-lookup"><span data-stu-id="f9d51-124">Without this overhead, thread-based jobs run faster and use fewer resources than the other job types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9d51-125">Родительский сеанс, создавший задание, также отслеживает состояние задания и собирает данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="f9d51-125">The parent session that created the job also monitors the job status and collects pipeline data.</span></span> <span data-ttu-id="f9d51-126">Дочерний процесс задания завершается родительским процессом после того, как задание достигнет завершенного состояния.</span><span class="sxs-lookup"><span data-stu-id="f9d51-126">The job child process is terminated by the parent process once the job reaches a finished state.</span></span> <span data-ttu-id="f9d51-127">Если родительский сеанс завершается, все выполняющиеся дочерние задания завершаются вместе с их дочерними процессами.</span><span class="sxs-lookup"><span data-stu-id="f9d51-127">If the parent session is terminated, all running child jobs are terminated along with their child processes.</span></span>

<span data-ttu-id="f9d51-128">Существует два способа обойти эту ситуацию.</span><span class="sxs-lookup"><span data-stu-id="f9d51-128">There are two ways work around this situation:</span></span>

1. <span data-ttu-id="f9d51-129">Используйте `Invoke-Command` для создания заданий, выполняемых в отключенных сеансах.</span><span class="sxs-lookup"><span data-stu-id="f9d51-129">Use `Invoke-Command` to create jobs that run in disconnected sessions.</span></span> <span data-ttu-id="f9d51-130">Дополнительные сведения см. в разделе [about_Remote_Jobs](about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="f9d51-130">For more information, see [about_Remote_Jobs](about_Remote_Jobs.md).</span></span>
1. <span data-ttu-id="f9d51-131">Используйте `Start-Process` для создания нового процесса, а не задания.</span><span class="sxs-lookup"><span data-stu-id="f9d51-131">Use `Start-Process` to create a new process rather than a job.</span></span> <span data-ttu-id="f9d51-132">Дополнительные сведения см. в разделе [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).</span><span class="sxs-lookup"><span data-stu-id="f9d51-132">For more information, see [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).</span></span>

## <a name="the-job-cmdlets"></a><span data-ttu-id="f9d51-133">Командлеты задания</span><span class="sxs-lookup"><span data-stu-id="f9d51-133">The job cmdlets</span></span>

|<span data-ttu-id="f9d51-134">Командлет</span><span class="sxs-lookup"><span data-stu-id="f9d51-134">Cmdlet</span></span>          |<span data-ttu-id="f9d51-135">Описание</span><span class="sxs-lookup"><span data-stu-id="f9d51-135">Description</span></span>                                            |
|----------------|-------------------------------------------------------|
|`Start-Job`     |<span data-ttu-id="f9d51-136">Запускает фоновое задание на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="f9d51-136">Starts a background job on a local computer.</span></span>           |
|`Get-Job`       |<span data-ttu-id="f9d51-137">Возвращает фоновые задания, запущенные в</span><span class="sxs-lookup"><span data-stu-id="f9d51-137">Gets the background jobs that were started in the</span></span>      |
|                |<span data-ttu-id="f9d51-138">текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="f9d51-138">current session.</span></span>                                       |
|`Receive-Job`   |<span data-ttu-id="f9d51-139">Возвращает результаты фоновых заданий.</span><span class="sxs-lookup"><span data-stu-id="f9d51-139">Gets the results of background jobs.</span></span>                   |
|`Stop-Job`      |<span data-ttu-id="f9d51-140">Останавливает фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="f9d51-140">Stops a background job.</span></span>                                |
|`Wait-Job`      |<span data-ttu-id="f9d51-141">Подавляет командную строку до тех пор, пока одно или все задания не будут</span><span class="sxs-lookup"><span data-stu-id="f9d51-141">Suppresses the command prompt until one or all jobs are</span></span>|
|                |<span data-ttu-id="f9d51-142">завершения.</span><span class="sxs-lookup"><span data-stu-id="f9d51-142">complete.</span></span>                                              |
|`Remove-Job`    |<span data-ttu-id="f9d51-143">Удаляет фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="f9d51-143">Deletes a background job.</span></span>                              |
|`Invoke-Command`|<span data-ttu-id="f9d51-144">Параметр **AsJob** создает фоновое задание на</span><span class="sxs-lookup"><span data-stu-id="f9d51-144">The **AsJob** parameter creates a background job on a</span></span>  |
|                |<span data-ttu-id="f9d51-145">удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="f9d51-145">remote computer.</span></span> <span data-ttu-id="f9d51-146">Можно использовать `Invoke-Command` для запуска</span><span class="sxs-lookup"><span data-stu-id="f9d51-146">You can use `Invoke-Command` to run</span></span>   |
|                |<span data-ttu-id="f9d51-147">Любая команда задания удаленно, включая `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="f9d51-147">any job command remotely, including `Start-Job`.</span></span>       |

## <a name="how-to-start-a-job-on-the-local-computer"></a><span data-ttu-id="f9d51-148">Запуск задания на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="f9d51-148">How to start a job on the local computer</span></span>

<span data-ttu-id="f9d51-149">Чтобы запустить фоновое задание на локальном компьютере, используйте `Start-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="f9d51-149">To start a background job on the local computer, use the `Start-Job` cmdlet.</span></span>

<span data-ttu-id="f9d51-150">Чтобы написать `Start-Job` команду, заключите команду, которая выполняется заданием, в фигурные скобки ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="f9d51-150">To write a `Start-Job` command, enclose the command that the job runs in curly braces (`{}`).</span></span> <span data-ttu-id="f9d51-151">Используйте параметр **ScriptBlock** для указания команды.</span><span class="sxs-lookup"><span data-stu-id="f9d51-151">Use the **ScriptBlock** parameter to specify the command.</span></span>

<span data-ttu-id="f9d51-152">Следующая команда запускает фоновое задание, которое выполняет `Get-Process` команду на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="f9d51-152">The following command starts a background job that runs a `Get-Process` command on the local computer.</span></span>

```powershell
Start-Job -ScriptBlock {Get-Process}
```

<span data-ttu-id="f9d51-153">Когда вы запускаете фоновое задание, Командная строка возвращается немедленно, даже если выполнение задания занимает длительное время.</span><span class="sxs-lookup"><span data-stu-id="f9d51-153">When you start a background job, the command prompt returns immediately, even if the job takes an extended time to complete.</span></span> <span data-ttu-id="f9d51-154">Пока задание выполняется, можно продолжать работу с данным сеансом.</span><span class="sxs-lookup"><span data-stu-id="f9d51-154">You can continue to work in the session without interruption while the job runs.</span></span>

<span data-ttu-id="f9d51-155">`Start-Job`Команда возвращает объект, представляющий задание.</span><span class="sxs-lookup"><span data-stu-id="f9d51-155">The `Start-Job` command returns an object that represents the job.</span></span> <span data-ttu-id="f9d51-156">Объект задания содержит полезную информацию о задании, но не содержит результатов его выполнения.</span><span class="sxs-lookup"><span data-stu-id="f9d51-156">The job object contains useful information about the job, but it does not contain the job results.</span></span>

<span data-ttu-id="f9d51-157">Вы можете сохранить объект задания в переменной, а затем использовать его вместе с другими командлетами **задания** для управления фоновыми заданиями.</span><span class="sxs-lookup"><span data-stu-id="f9d51-157">You can save the job object in a variable and then use it with the other **Job** cmdlets to manage the background job.</span></span> <span data-ttu-id="f9d51-158">Следующая команда запускает объект задания и сохраняет результирующий объект задания в `$job` переменной.</span><span class="sxs-lookup"><span data-stu-id="f9d51-158">The following command starts a job object and saves the resulting job object in the `$job` variable.</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Process}
```

<span data-ttu-id="f9d51-159">Начиная с версии PowerShell 6,0 можно использовать оператор Background ( `&` ) в конце конвейера для запуска фонового задания.</span><span class="sxs-lookup"><span data-stu-id="f9d51-159">Beginning in PowerShell 6.0, you can use the background operator (`&`) at the end of a pipeline to start a background job.</span></span> <span data-ttu-id="f9d51-160">Дополнительные сведения см. в разделе [оператор Background](about_Operators.md#background-operator-).</span><span class="sxs-lookup"><span data-stu-id="f9d51-160">For more information, see [background operator](about_Operators.md#background-operator-).</span></span>

<span data-ttu-id="f9d51-161">Использование оператора Background функционально эквивалентно использованию `Start-Job` командлета в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="f9d51-161">Using the background operator is functionally equivalent to using the `Start-Job` cmdlet in the previous example.</span></span>

```powershell
$job = Get-Process &
```

## <a name="getting-job-objects"></a><span data-ttu-id="f9d51-162">Получение объектов заданий</span><span class="sxs-lookup"><span data-stu-id="f9d51-162">Getting job objects</span></span>

<span data-ttu-id="f9d51-163">`Get-Job`Командлет возвращает объекты, представляющие фоновые задания, которые были запущены в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="f9d51-163">The `Get-Job` cmdlet returns objects that represent the background jobs that were started in the current session.</span></span> <span data-ttu-id="f9d51-164">Без параметров `Get-Job` возвращает все задания, запущенные в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="f9d51-164">Without parameters, `Get-Job` returns all of the jobs that were started in the current session.</span></span>

```powershell
Get-Job
```

<span data-ttu-id="f9d51-165">Объект задания содержит состояние задания, которое указывает, завершено ли задание.</span><span class="sxs-lookup"><span data-stu-id="f9d51-165">The job object contains the state of the job, which indicates whether the job has finished.</span></span> <span data-ttu-id="f9d51-166">Завершенное задание имеет состояние " **завершено** " или " **сбой**".</span><span class="sxs-lookup"><span data-stu-id="f9d51-166">A finished job has a state of **Complete** or **Failed**.</span></span> <span data-ttu-id="f9d51-167">Задание также может быть **заблокировано** или **заработано**.</span><span class="sxs-lookup"><span data-stu-id="f9d51-167">A job might also be **Blocked** or **Running**.</span></span>

```Output
Id  Name  PSJobTypeName State      HasMoreData  Location   Command
--  ----  ------------- -----      -----------  --------   -------
1   Job1  BackgroundJob Complete   True         localhost  Get-Process
```

<span data-ttu-id="f9d51-168">Вы можете сохранить объект задания в переменной и использовать его для представления задания в более поздней команде.</span><span class="sxs-lookup"><span data-stu-id="f9d51-168">You can save the job object in a variable and use it to represent the job in a later command.</span></span> <span data-ttu-id="f9d51-169">Следующая команда возвращает задание с ИДЕНТИФИКАТОРом 1 и сохраняет его в `$job` переменной.</span><span class="sxs-lookup"><span data-stu-id="f9d51-169">The following command gets the job with ID 1 and saves it in the `$job` variable.</span></span>

```powershell
$job = Get-Job -Id 1
```

## <a name="getting-the-results-of-a-job"></a><span data-ttu-id="f9d51-170">Получение результатов задания</span><span class="sxs-lookup"><span data-stu-id="f9d51-170">Getting the results of a job</span></span>

<span data-ttu-id="f9d51-171">При выполнении фонового задания результаты не отображаются немедленно.</span><span class="sxs-lookup"><span data-stu-id="f9d51-171">When you run a background job, the results do not appear immediately.</span></span> <span data-ttu-id="f9d51-172">Чтобы получить результаты фонового задания, используйте `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="f9d51-172">To get the results of a background job, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="f9d51-173">В следующем примере `Receive-Job` командлет получает результаты задания с помощью объекта задания в `$job` переменной.</span><span class="sxs-lookup"><span data-stu-id="f9d51-173">The following example, the `Receive-Job` cmdlet gets the results of the job using job object in the `$job` variable.</span></span>

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

<span data-ttu-id="f9d51-174">Результаты задания можно сохранить в переменной.</span><span class="sxs-lookup"><span data-stu-id="f9d51-174">You can save the results of a job in a variable.</span></span> <span data-ttu-id="f9d51-175">Следующая команда сохраняет результаты задания в `$job` переменной в `$results` переменной.</span><span class="sxs-lookup"><span data-stu-id="f9d51-175">The following command saves the results of the job in the `$job` variable to the `$results` variable.</span></span>

```powershell
$results = Receive-Job -Job $job
```

### <a name="getting-and-keeping-partial-job-results"></a><span data-ttu-id="f9d51-176">Получение и хранение результатов частичной работы</span><span class="sxs-lookup"><span data-stu-id="f9d51-176">Getting and keeping partial job results</span></span>

<span data-ttu-id="f9d51-177">`Receive-Job`Командлет возвращает результаты фонового задания.</span><span class="sxs-lookup"><span data-stu-id="f9d51-177">The `Receive-Job` cmdlet gets the results of a background job.</span></span> <span data-ttu-id="f9d51-178">Если задание завершено, `Receive-Job` получает результаты всех заданий.</span><span class="sxs-lookup"><span data-stu-id="f9d51-178">If the job is complete, `Receive-Job` gets all job results.</span></span> <span data-ttu-id="f9d51-179">Если задание по-прежнему выполняется, `Receive-Job` получает результаты, которые были созданы до сих пор.</span><span class="sxs-lookup"><span data-stu-id="f9d51-179">If the job is still running, `Receive-Job` gets the results that have been generated thus far.</span></span> <span data-ttu-id="f9d51-180">`Receive-Job`Чтобы получить оставшиеся результаты, можно выполнить команды еще раз.</span><span class="sxs-lookup"><span data-stu-id="f9d51-180">You can run `Receive-Job` commands again to get the remaining results.</span></span>

<span data-ttu-id="f9d51-181">По умолчанию `Receive-Job` удаляет результаты из кэша, в котором хранятся результаты задания.</span><span class="sxs-lookup"><span data-stu-id="f9d51-181">By default, `Receive-Job` deletes the results from the cache where job results are stored.</span></span> <span data-ttu-id="f9d51-182">При `Receive-Job` повторном запуске вы получаете только новые результаты, поступившие после первого запуска.</span><span class="sxs-lookup"><span data-stu-id="f9d51-182">When you run `Receive-Job` again, you get only the new results that arrived after the first run.</span></span>

<span data-ttu-id="f9d51-183">Следующие команды показывают результаты `Receive-Job` выполнения команд до завершения задания.</span><span class="sxs-lookup"><span data-stu-id="f9d51-183">The following commands show the results of `Receive-Job` commands run before the job is complete.</span></span>

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

<span data-ttu-id="f9d51-184">Используйте параметр **держитесь** , чтобы предотвратить `Receive-Job` Удаление возвращаемых результатов задания.</span><span class="sxs-lookup"><span data-stu-id="f9d51-184">Use the **Keep** parameter to prevent `Receive-Job` from deleting the job results that are returned.</span></span> <span data-ttu-id="f9d51-185">Приведенные ниже команды демонстрируют последствия использования параметра **сохранения** для задания, которое еще не завершено.</span><span class="sxs-lookup"><span data-stu-id="f9d51-185">The following commands show the effect of using the **Keep** parameter on a job that is not yet complete.</span></span>

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

### <a name="waiting-for-the-results"></a><span data-ttu-id="f9d51-186">Ожидание результатов</span><span class="sxs-lookup"><span data-stu-id="f9d51-186">Waiting for the results</span></span>

<span data-ttu-id="f9d51-187">При выполнении команды, выполнение которой занимает много времени, можно использовать свойства объекта задания, чтобы определить, когда задание завершено.</span><span class="sxs-lookup"><span data-stu-id="f9d51-187">If you run a command that takes a long time to complete, you can use the properties of the job object to determine when the job is complete.</span></span> <span data-ttu-id="f9d51-188">Следующая команда использует `Get-Job` объект для получения всех фоновых заданий в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="f9d51-188">The following command uses the `Get-Job` object to get all of the background jobs in the current session.</span></span>

```powershell
Get-Job
```

<span data-ttu-id="f9d51-189">Результаты отображаются в таблице.</span><span class="sxs-lookup"><span data-stu-id="f9d51-189">The results appear in a table.</span></span> <span data-ttu-id="f9d51-190">Состояние задания отображается в столбце **состояние** .</span><span class="sxs-lookup"><span data-stu-id="f9d51-190">The status of the job appears in the **State** column.</span></span>

```Output
Id Name  PSJobTypeName State    HasMoreData Location  Command
-- ----  ------------- -----    ----------- --------  -------
1  Job1  BackgroundJob Complete True        localhost Get-Process
2  Job2  BackgroundJob Running  True        localhost Get-EventLog -Log ...
3  Job3  BackgroundJob Complete True        localhost dir -Path C:\* -Re...
```

<span data-ttu-id="f9d51-191">В этом случае свойство **State** показывает, что задание 2 все еще выполняется.</span><span class="sxs-lookup"><span data-stu-id="f9d51-191">In this case, the **State** property reveals that Job 2 is still running.</span></span> <span data-ttu-id="f9d51-192">Если вы использовали `Receive-Job` командлет для получения результатов задания прямо сейчас, результаты будут неполными.</span><span class="sxs-lookup"><span data-stu-id="f9d51-192">If you were to use the `Receive-Job` cmdlet to get the job results now, the results would be incomplete.</span></span> <span data-ttu-id="f9d51-193">Можно `Receive-Job` многократно использовать командлет для получения всех результатов.</span><span class="sxs-lookup"><span data-stu-id="f9d51-193">You can use the `Receive-Job` cmdlet repeatedly to get all of the results.</span></span> <span data-ttu-id="f9d51-194">Чтобы определить, когда задание завершено, используйте свойство **State** .</span><span class="sxs-lookup"><span data-stu-id="f9d51-194">Use the **State** property to determine when the job is complete.</span></span>

<span data-ttu-id="f9d51-195">Можно также использовать параметр **Wait** `Receive-Job` командлета.</span><span class="sxs-lookup"><span data-stu-id="f9d51-195">You can also use the **Wait** parameter of the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="f9d51-196">При использовании этого параметра командлет не возвращает командную строку, пока задание не будет завершено и все результаты будут доступны.</span><span class="sxs-lookup"><span data-stu-id="f9d51-196">When use use this parameter, the cmdlet does not return the command prompt until the job is completed and all results are available.</span></span>

<span data-ttu-id="f9d51-197">Можно также использовать `Wait-Job` командлет для ожидания любого или всех результатов задания.</span><span class="sxs-lookup"><span data-stu-id="f9d51-197">You can also use the `Wait-Job` cmdlet to wait for any or all of the results of the job.</span></span> <span data-ttu-id="f9d51-198">`Wait-Job` позволяет ожидать одно или несколько конкретных заданий или всех заданий.</span><span class="sxs-lookup"><span data-stu-id="f9d51-198">`Wait-Job` lets you wait for one or more specific job or for all jobs.</span></span>
<span data-ttu-id="f9d51-199">Следующая команда использует `Wait-Job` командлет для ожидания задания с **идентификатором** .</span><span class="sxs-lookup"><span data-stu-id="f9d51-199">The following command uses the `Wait-Job` cmdlet to wait for a job with **ID**</span></span>
10.

```powershell
Wait-Job -ID 10
```

<span data-ttu-id="f9d51-200">В результате Командная строка PowerShell подавляется до завершения задания.</span><span class="sxs-lookup"><span data-stu-id="f9d51-200">As a result, the PowerShell prompt is suppressed until the job is completed.</span></span>

<span data-ttu-id="f9d51-201">Можно также дождаться заранее определенного периода времени.</span><span class="sxs-lookup"><span data-stu-id="f9d51-201">You can also wait for a predetermined period of time.</span></span> <span data-ttu-id="f9d51-202">Эта команда использует параметр **timeout** , чтобы ограничить время ожидания 120 секунд.</span><span class="sxs-lookup"><span data-stu-id="f9d51-202">This command uses the **Timeout** parameter to limit the wait to 120 seconds.</span></span> <span data-ttu-id="f9d51-203">По истечении этого времени Командная строка возвращает значение, но задание продолжит выполняться в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="f9d51-203">When the time expires, the command prompt returns, but the job continues to run in the background.</span></span>

```powershell
Wait-Job -ID 10 -Timeout 120
```

## <a name="stopping-a-job"></a><span data-ttu-id="f9d51-204">Остановка задания</span><span class="sxs-lookup"><span data-stu-id="f9d51-204">Stopping a job</span></span>

<span data-ttu-id="f9d51-205">Чтобы прерывать фоновое задание, используйте `Stop-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="f9d51-205">To stop a background job, use the `Stop-Job` cmdlet.</span></span> <span data-ttu-id="f9d51-206">Следующая команда запускает задание для получения каждой записи в журнале системных событий.</span><span class="sxs-lookup"><span data-stu-id="f9d51-206">The following command starts a job to get every entry in the System event log.</span></span> <span data-ttu-id="f9d51-207">Объект задания сохраняется в `$job` переменной.</span><span class="sxs-lookup"><span data-stu-id="f9d51-207">It saves the job object in the `$job` variable.</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-EventLog -Log System}
```

<span data-ttu-id="f9d51-208">Следующая команда останавливает задание.</span><span class="sxs-lookup"><span data-stu-id="f9d51-208">The following command stops the job.</span></span> <span data-ttu-id="f9d51-209">Он использует оператор конвейера ( `|` ) для отправки задания в переменной в `$job` `Stop-Job` .</span><span class="sxs-lookup"><span data-stu-id="f9d51-209">It uses a pipeline operator (`|`) to send the job in the `$job` variable to `Stop-Job`.</span></span>

```powershell
$job | Stop-Job
```

## <a name="deleting-a-job"></a><span data-ttu-id="f9d51-210">Удаление задания</span><span class="sxs-lookup"><span data-stu-id="f9d51-210">Deleting a job</span></span>

<span data-ttu-id="f9d51-211">Чтобы удалить фоновое задание, используйте `Remove-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="f9d51-211">To delete a background job, use the `Remove-Job` cmdlet.</span></span> <span data-ttu-id="f9d51-212">Следующая команда удаляет задание в `$job` переменной.</span><span class="sxs-lookup"><span data-stu-id="f9d51-212">The following command deletes the job in the `$job` variable.</span></span>

```powershell
Remove-Job -Job $job
```

## <a name="investigating-a-failed-job"></a><span data-ttu-id="f9d51-213">Исследование невыполненного задания</span><span class="sxs-lookup"><span data-stu-id="f9d51-213">Investigating a failed job</span></span>

<span data-ttu-id="f9d51-214">Задания могут завершаться сбоем по многим причинам.</span><span class="sxs-lookup"><span data-stu-id="f9d51-214">Jobs can fail for many reasons.</span></span> <span data-ttu-id="f9d51-215">Объект задания содержит свойство **Reason** , содержащее сведения о причине сбоя.</span><span class="sxs-lookup"><span data-stu-id="f9d51-215">the job object contains a **Reason** property that contains information about the cause of the failure.</span></span>

<span data-ttu-id="f9d51-216">В следующем примере запускается задание без требуемых учетных данных.</span><span class="sxs-lookup"><span data-stu-id="f9d51-216">The following example starts a job without the required credentials.</span></span>

```powershell
$job = Start-Job -ScriptBlock {New-Item -Path HKLM:\Software\MyCompany}
Get-Job $job

Id Name  PSJobTypeName State  HasMoreData  Location  Command
-- ----  ------------- -----  -----------  --------  -------
1  Job1  BackgroundJob Failed False        localhost New-Item -Path HKLM:...
```

<span data-ttu-id="f9d51-217">Проверьте свойство **Reason** , чтобы найти ошибку, вызвавшую сбой задания.</span><span class="sxs-lookup"><span data-stu-id="f9d51-217">Inspect the **Reason** property to find the error that caused the job to fail.</span></span>

```powershell
$job.ChildJobs[0].JobStateInfo.Reason
```

<span data-ttu-id="f9d51-218">В этом случае задание завершилось сбоем, так как удаленный компьютер требует явных учетных данных для выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="f9d51-218">In this case, the job failed because the remote computer required explicit credentials to run the command.</span></span> <span data-ttu-id="f9d51-219">Свойство **Reason** содержит следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="f9d51-219">The **Reason** property contains the following message:</span></span>

> <span data-ttu-id="f9d51-220">Сбой подключения к удаленному серверу со следующим сообщением об ошибке: "отказано в доступе".</span><span class="sxs-lookup"><span data-stu-id="f9d51-220">Connecting to remote server failed with the following error message: "Access is denied".</span></span>

## <a name="see-also"></a><span data-ttu-id="f9d51-221">См. также</span><span class="sxs-lookup"><span data-stu-id="f9d51-221">See also</span></span>

- [<span data-ttu-id="f9d51-222">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="f9d51-222">about_Remote_Jobs</span></span>](about_Remote_Jobs.md)
- [<span data-ttu-id="f9d51-223">about_Thread_Jobs</span><span class="sxs-lookup"><span data-stu-id="f9d51-223">about_Thread_Jobs</span></span>](about_Thread_Jobs.md)
- [<span data-ttu-id="f9d51-224">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="f9d51-224">about_Job_Details</span></span>](about_Job_Details.md)
- [<span data-ttu-id="f9d51-225">about_Remote</span><span class="sxs-lookup"><span data-stu-id="f9d51-225">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="f9d51-226">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="f9d51-226">about_PSSessions</span></span>](about_PSSessions.md)
- [<span data-ttu-id="f9d51-227">Start-Job</span><span class="sxs-lookup"><span data-stu-id="f9d51-227">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="f9d51-228">Get-Job.</span><span class="sxs-lookup"><span data-stu-id="f9d51-228">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="f9d51-229">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="f9d51-229">Receive-Job</span></span>](xref:Microsoft.PowerShell.Core.Receive-Job)
- [<span data-ttu-id="f9d51-230">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="f9d51-230">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="f9d51-231">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="f9d51-231">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="f9d51-232">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="f9d51-232">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
- [<span data-ttu-id="f9d51-233">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="f9d51-233">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)
