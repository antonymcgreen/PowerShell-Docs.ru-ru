---
description: Предоставляет сведения о заданиях, основанных на потоках PowerShell. Задание потока — это тип фонового задания, выполняющего команду или выражение в отдельном потоке в рамках текущего процесса сеанса.
keywords: powershell,командлет
Locale: en-US
ms.date: 10/16/2020
online version: 1.0.0
schema: 2.0.0
title: about_Thread_Jobs
ms.openlocfilehash: 973d0ddf18b63cd7462817cf68f7c5d7466f4724
ms.sourcegitcommit: 108686b166672cc08817c637dd93eb1ad830511d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "93232986"
---
# <a name="about-thread-jobs"></a><span data-ttu-id="01e15-105">О заданиях потоков</span><span class="sxs-lookup"><span data-stu-id="01e15-105">About Thread Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="01e15-106">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="01e15-106">Short description</span></span>

<span data-ttu-id="01e15-107">Предоставляет сведения о заданиях, основанных на потоках PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01e15-107">Provides information about PowerShell thread-based jobs.</span></span> <span data-ttu-id="01e15-108">Задание потока — это тип фонового задания, выполняющего команду или выражение в отдельном потоке в рамках текущего процесса сеанса.</span><span class="sxs-lookup"><span data-stu-id="01e15-108">A thread job is a type of background job that runs a command or expression in a separate thread within the current session process.</span></span>

## <a name="long-description"></a><span data-ttu-id="01e15-109">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="01e15-109">Long description</span></span>

<span data-ttu-id="01e15-110">В этой статье объясняется, как выполнять задания потоков в PowerShell на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="01e15-110">This article explains how to run thread jobs in PowerShell on a local computer.</span></span>
<span data-ttu-id="01e15-111">Сведения о выполнении фоновых заданий на локальном компьютере см. в разделе [about_Jobs](about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="01e15-111">For information about running background jobs on a local computer, see [about_Jobs](about_Jobs.md).</span></span>

<span data-ttu-id="01e15-112">Запустите задание потока с помощью `Start-ThreadJob` командлета.</span><span class="sxs-lookup"><span data-stu-id="01e15-112">Start a thread job by using the `Start-ThreadJob` cmdlet.</span></span> <span data-ttu-id="01e15-113">Этот командлет доступен в модуле **среаджоб** , который поставляется с PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01e15-113">This cmdlet is available in the **ThreadJob** module that ships with PowerShell.</span></span>
<span data-ttu-id="01e15-114">`Start-ThreadJob` Возвращает один объект задания, который инкапсулирует выполняющуюся команду или скрипт, и может использоваться со всеми командлетами задания PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01e15-114">`Start-ThreadJob` returns a single job object that encapsulates the running command or script, and can be used with all PowerShell job manipulating cmdlets.</span></span>

## <a name="the-job-cmdlets"></a><span data-ttu-id="01e15-115">Командлеты задания</span><span class="sxs-lookup"><span data-stu-id="01e15-115">The job cmdlets</span></span>

|<span data-ttu-id="01e15-116">Командлет</span><span class="sxs-lookup"><span data-stu-id="01e15-116">Cmdlet</span></span>           |<span data-ttu-id="01e15-117">Описание</span><span class="sxs-lookup"><span data-stu-id="01e15-117">Description</span></span>                                            |
|-----------------|-------------------------------------------------------|
|`Start-ThreadJob`|<span data-ttu-id="01e15-118">Запускает задание потока на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="01e15-118">Starts a thread job on a local computer.</span></span>               |
|`Get-Job`        |<span data-ttu-id="01e15-119">Возвращает задания, запущенные в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="01e15-119">Gets the jobs that were started in the current session.</span></span>|
|`Receive-Job`    |<span data-ttu-id="01e15-120">Возвращает результаты заданий.</span><span class="sxs-lookup"><span data-stu-id="01e15-120">Gets the results of jobs.</span></span>                              |
|`Stop-Job`       |<span data-ttu-id="01e15-121">Останавливает выполняющееся задание.</span><span class="sxs-lookup"><span data-stu-id="01e15-121">Stops a running job.</span></span>                                   |
|`Wait-Job`       |<span data-ttu-id="01e15-122">Подавляет командную строку до тех пор, пока одно или все задания не будут</span><span class="sxs-lookup"><span data-stu-id="01e15-122">Suppresses the command prompt until one or all jobs are</span></span>|
|                 |<span data-ttu-id="01e15-123">завершения.</span><span class="sxs-lookup"><span data-stu-id="01e15-123">complete.</span></span>                                              |
|`Remove-Job`     |<span data-ttu-id="01e15-124">Удаляет задание.</span><span class="sxs-lookup"><span data-stu-id="01e15-124">Deletes a job.</span></span>                                         |

## <a name="how-to-start-a-thread-job-on-the-local-computer"></a><span data-ttu-id="01e15-125">Запуск задания потока на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="01e15-125">How to start a thread job on the local computer</span></span>

<span data-ttu-id="01e15-126">Чтобы запустить задание потока на локальном компьютере, используйте `Start-ThreadJob` командлет.</span><span class="sxs-lookup"><span data-stu-id="01e15-126">To start a thread job on the local computer, use the `Start-ThreadJob` cmdlet.</span></span>

<span data-ttu-id="01e15-127">Чтобы написать `Start-ThreadJob` команду, заключите команду или скрипт, выполняемые заданием, в фигурные скобки ( `{ }` ).</span><span class="sxs-lookup"><span data-stu-id="01e15-127">To write a `Start-ThreadJob` command, enclose the command or script the job runs in curly braces (`{ }`).</span></span>

<span data-ttu-id="01e15-128">Следующая команда запускает задание потока, которое выполняет `Get-Process` команду на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="01e15-128">The following command starts a thread job that runs a `Get-Process` command on the local computer.</span></span>

```powershell
Start-ThreadJob -ScriptBlock { Get-Process }
```

<span data-ttu-id="01e15-129">`Start-ThreadJob`Команда возвращает `ThreadJob` объект, представляющий выполняемое задание.</span><span class="sxs-lookup"><span data-stu-id="01e15-129">The `Start-ThreadJob` command returns a `ThreadJob` object that represents the running job.</span></span> <span data-ttu-id="01e15-130">Объект задания содержит полезные сведения о задании, включая текущее состояние выполнения.</span><span class="sxs-lookup"><span data-stu-id="01e15-130">The job object contains useful information about the job including its current running status.</span></span> <span data-ttu-id="01e15-131">Он собирает результаты выполнения задания по мере формирования результатов.</span><span class="sxs-lookup"><span data-stu-id="01e15-131">It collects the results of the job as the results are being generated.</span></span>

<span data-ttu-id="01e15-132">Чтобы записать `ForEach-Object -Parallel` команду, передать данные в команду и заключить команду или скрипт, выполняемые заданием, в фигурные скобки ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="01e15-132">To write a `ForEach-Object -Parallel` command, pipe data to the command and enclose the command or script the job runs in curly braces(`{}`).</span></span> <span data-ttu-id="01e15-133">Используйте `-AsJob` параметр параметра, чтобы возвращался объект задания.</span><span class="sxs-lookup"><span data-stu-id="01e15-133">Use the `-AsJob` parameter switch so that a job object is returned.</span></span>

<span data-ttu-id="01e15-134">Следующая команда запускает задание, которое содержит дочерние задания для каждого входного значения, переданного команде.</span><span class="sxs-lookup"><span data-stu-id="01e15-134">The following command starts a job that contains child jobs for each input value piped to the command.</span></span> <span data-ttu-id="01e15-135">Каждое дочернее задание выполняет `Write-Output` команду с входным значением, переданным в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="01e15-135">Each child job runs the `Write-Output` command with a piped input value as the argument.</span></span>

```powershell
1..5 | ForEach-Object -Parallel { Write-Output $_ } -AsJob
```

<span data-ttu-id="01e15-136">`ForEach-Object -Parallel`Команда возвращает `PSTaskJob` объект, содержащий дочерние задания для каждого входного значения перенаправленного.</span><span class="sxs-lookup"><span data-stu-id="01e15-136">The `ForEach-Object -Parallel` command returns a `PSTaskJob` object that contains child jobs for each piped input value.</span></span> <span data-ttu-id="01e15-137">Объект задания содержит полезные сведения о состоянии выполнения дочерних заданий.</span><span class="sxs-lookup"><span data-stu-id="01e15-137">The job object contains useful information about the child jobs running status.</span></span> <span data-ttu-id="01e15-138">Он собирает результаты дочерних заданий по мере формирования результатов.</span><span class="sxs-lookup"><span data-stu-id="01e15-138">It collects the results of the child jobs as the results are being generated.</span></span>

## <a name="how-to-wait-for-a-job-to-complete-and-retrieve-job-results"></a><span data-ttu-id="01e15-139">Как дождаться завершения задания и получить результаты задания</span><span class="sxs-lookup"><span data-stu-id="01e15-139">How to wait for a job to complete and retrieve job results</span></span>

<span data-ttu-id="01e15-140">Вы можете использовать командлеты задания PowerShell, такие как `Wait-Job` и, `Receive-Job` чтобы дождаться завершения задания, а затем вернуть все результаты, созданные заданием.</span><span class="sxs-lookup"><span data-stu-id="01e15-140">You can use PowerShell job cmdlets, such as `Wait-Job` and `Receive-Job` to wait for a job to complete and then return all results generated by the job.</span></span>

<span data-ttu-id="01e15-141">Следующая команда запускает задание потока, которое выполняет `Get-Process` команду, затем ожидает завершения команды и возвращает все результаты данных, созданные командой.</span><span class="sxs-lookup"><span data-stu-id="01e15-141">The following command starts a thread job that runs a `Get-Process` command, then waits for the command to complete, and finally returns all data results generated by the command.</span></span>

```powershell
Start-ThreadJob -ScriptBlock { Get-Process } | Wait-Job | Receive-Job
```

<span data-ttu-id="01e15-142">Следующая команда запускает задание, которое выполняет `Write-Output` команду для каждого входного значения, а затем ожидает завершения всех дочерних заданий и возвращает все результаты данных, созданные дочерними заданиями.</span><span class="sxs-lookup"><span data-stu-id="01e15-142">The following command starts a job that runs a `Write-Output` command for each piped input, then waits for all child jobs to complete, and finally returns all data results generated by the child jobs.</span></span>

```powershell
1..5 | ForEach-Object -Parallel { Write-Output $_ } -AsJob | Wait-Job | Receive-Job
```

<span data-ttu-id="01e15-143">`Receive-Job`Командлет возвращает результаты дочерних заданий.</span><span class="sxs-lookup"><span data-stu-id="01e15-143">The `Receive-Job` cmdlet returns the results of the child jobs.</span></span>

```powershell
1
3
2
4
5
```

<span data-ttu-id="01e15-144">Так как каждое дочернее задание выполняется параллельно, порядок созданных результатов не гарантируется.</span><span class="sxs-lookup"><span data-stu-id="01e15-144">Because each child job runs parallel, the order of the generated results is not guaranteed.</span></span>

## <a name="powershell-concurrency-and-jobs"></a><span data-ttu-id="01e15-145">Параллелизм и задания PowerShell</span><span class="sxs-lookup"><span data-stu-id="01e15-145">PowerShell concurrency and jobs</span></span>

<span data-ttu-id="01e15-146">PowerShell параллельно выполняет команды и скрипты с помощью заданий.</span><span class="sxs-lookup"><span data-stu-id="01e15-146">PowerShell concurrently runs commands and script through jobs.</span></span> <span data-ttu-id="01e15-147">Существует три решения на основе заданий, предоставляемые PowerShell для поддержки параллелизма.</span><span class="sxs-lookup"><span data-stu-id="01e15-147">There are three jobs-based solutions provided by PowerShell to support concurrency.</span></span>

|<span data-ttu-id="01e15-148">Задание</span><span class="sxs-lookup"><span data-stu-id="01e15-148">Job</span></span>            |<span data-ttu-id="01e15-149">Описание</span><span class="sxs-lookup"><span data-stu-id="01e15-149">Description</span></span>                                                  |
|---------------|-------------------------------------------------------------|
|`RemoteJob`    |<span data-ttu-id="01e15-150">Команда и сценарий выполняются на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="01e15-150">Command and script run on a remote computer.</span></span>                 |
|`BackgroundJob`|<span data-ttu-id="01e15-151">Команда и сценарий выполняются в отдельном процессе в локальной системе</span><span class="sxs-lookup"><span data-stu-id="01e15-151">Command and script run in a separate process on the local</span></span>    |
|               |<span data-ttu-id="01e15-152">машине.</span><span class="sxs-lookup"><span data-stu-id="01e15-152">machine.</span></span>                                                     |
|`ThreadJob`    |<span data-ttu-id="01e15-153">Команда и сценарий выполняются в отдельном потоке в том же</span><span class="sxs-lookup"><span data-stu-id="01e15-153">Command and script run in a separate thread within the same</span></span>  |
|               |<span data-ttu-id="01e15-154">процесс на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="01e15-154">process on the local machine.</span></span>                                |

<span data-ttu-id="01e15-155">Каждый тип задания имеет свои преимущества и недостатки.</span><span class="sxs-lookup"><span data-stu-id="01e15-155">Each type of job has benefits and drawbacks.</span></span> <span data-ttu-id="01e15-156">Удаленное выполнение сценария на отдельном компьютере или в отдельном процессе имеет большую изоляцию.</span><span class="sxs-lookup"><span data-stu-id="01e15-156">Running script remotely on a separate machine or in a separate process has great isolation.</span></span> <span data-ttu-id="01e15-157">Любые ошибки не влияют на другие выполняющиеся задания или на клиент, запустивший задание.</span><span class="sxs-lookup"><span data-stu-id="01e15-157">Any errors won't affect other running jobs or the client that started the job.</span></span> <span data-ttu-id="01e15-158">Но на уровне удаленного взаимодействия добавляются дополнительные издержки, включая сериализацию объектов.</span><span class="sxs-lookup"><span data-stu-id="01e15-158">But the remoting layer adds overhead, including object serialization.</span></span> <span data-ttu-id="01e15-159">Все объекты, передаваемые в удаленный сеанс и из него, должны быть сериализованы и десериализованы при передаче между клиентом и целевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="01e15-159">All objects passed to and from the remote session must be serialized and then deserialized as it passes between the client and the target session.</span></span> <span data-ttu-id="01e15-160">Операция сериализации может использовать много ресурсов вычислений и памяти для больших сложных объектов данных.</span><span class="sxs-lookup"><span data-stu-id="01e15-160">The serialization operation can use many compute and memory resources for large complex data objects.</span></span>

## <a name="powershell-thread-based-jobs"></a><span data-ttu-id="01e15-161">Задания на основе потока PowerShell</span><span class="sxs-lookup"><span data-stu-id="01e15-161">PowerShell thread based jobs</span></span>

<span data-ttu-id="01e15-162">Задания на основе потоков не так надежны, как удаленные и фоновые задания, так как они выполняются в одном и том же процессе в разных потоках.</span><span class="sxs-lookup"><span data-stu-id="01e15-162">Thread based jobs are not as robust as Remote and Background jobs, because they run in the same process on different threads.</span></span> <span data-ttu-id="01e15-163">Если в одном задании есть критическая ошибка, которая приводит к сбою процесса, то все остальные задания в процессе также завершатся ошибкой.</span><span class="sxs-lookup"><span data-stu-id="01e15-163">If one job has a critical error that crashes the process, then all other jobs in the process will also fail.</span></span>

<span data-ttu-id="01e15-164">Однако задания на основе потоков значительно меньше издержек.</span><span class="sxs-lookup"><span data-stu-id="01e15-164">However, thread-based jobs have much less overhead.</span></span> <span data-ttu-id="01e15-165">Им не нужно использовать удаленный уровень или сериализацию.</span><span class="sxs-lookup"><span data-stu-id="01e15-165">They don't need to use the remoting layer or serialization.</span></span> <span data-ttu-id="01e15-166">В результате задания на основе потоков выполняются гораздо быстрее и используют гораздо меньшие ресурсы, чем другие типы заданий.</span><span class="sxs-lookup"><span data-stu-id="01e15-166">The result is that thread-based jobs tend to run much faster and use far less resources than the other job types.</span></span>

## <a name="thread-job-performance"></a><span data-ttu-id="01e15-167">Производительность задания потока</span><span class="sxs-lookup"><span data-stu-id="01e15-167">Thread job performance</span></span>

<span data-ttu-id="01e15-168">Задания потоков выполняются быстрее и легче, чем другие типы заданий.</span><span class="sxs-lookup"><span data-stu-id="01e15-168">Thread jobs are faster and lighter weight than other types of jobs.</span></span> <span data-ttu-id="01e15-169">Но они по-прежнему имеют накладные расходы, которые могут быть большими по сравнению с работой, выполняемой заданием.</span><span class="sxs-lookup"><span data-stu-id="01e15-169">But they still have overhead that can be large when compared to work the job is doing.</span></span>

<span data-ttu-id="01e15-170">PowerShell запускает команды и скрипты в сеансе.</span><span class="sxs-lookup"><span data-stu-id="01e15-170">PowerShell runs commands and script in a session.</span></span> <span data-ttu-id="01e15-171">Только одна команда или сценарий может выполняться одновременно в сеансе.</span><span class="sxs-lookup"><span data-stu-id="01e15-171">Only one command or script can run at a time in a session.</span></span> <span data-ttu-id="01e15-172">Поэтому при выполнении нескольких заданий каждое задание выполняется в отдельном сеансе.</span><span class="sxs-lookup"><span data-stu-id="01e15-172">So when running multiple jobs, each job runs in a separate session.</span></span> <span data-ttu-id="01e15-173">Каждый сеанс влияет на накладные расходы.</span><span class="sxs-lookup"><span data-stu-id="01e15-173">Each session contributes to the overhead.</span></span>

<span data-ttu-id="01e15-174">Задания потоков обеспечивают наилучшую производительность, когда работа, выполняемая ими, превышает издержки сеанса, используемого для выполнения задания.</span><span class="sxs-lookup"><span data-stu-id="01e15-174">Thread jobs provide the best performance when the work they perform is greater than the overhead of the session used to run the job.</span></span> <span data-ttu-id="01e15-175">Существует два варианта соответствия этого критерия.</span><span class="sxs-lookup"><span data-stu-id="01e15-175">There are two cases for that meet this criteria.</span></span>

- <span data-ttu-id="01e15-176">Работа — это большое количество вычислительных ресурсов. выполнение скрипта для нескольких заданий потоков может использовать преимущества нескольких процессорных ядер и ускорить работу.</span><span class="sxs-lookup"><span data-stu-id="01e15-176">Work is compute intensive - Running a script on multiple thread jobs can take advantage of multiple processor cores and complete faster.</span></span>

- <span data-ttu-id="01e15-177">Работа состоит из значительного ожидающего сценария, который тратит время на ожидание результатов ввода-вывода или удаленного вызова.</span><span class="sxs-lookup"><span data-stu-id="01e15-177">Work consists of significant waiting - A script that spends time waiting for I/O or remote call results.</span></span> <span data-ttu-id="01e15-178">Параллельное выполнение обычно завершается быстрее, чем при последовательном выполнении.</span><span class="sxs-lookup"><span data-stu-id="01e15-178">Running in parallel usually completes quicker than if run sequentially.</span></span>

```powershell
(Measure-Command {
    1..1000 | ForEach { Start-ThreadJob { Write-Output "Hello $using:_" } } | Receive-Job -Wait
}).TotalMilliseconds
10457.962


(Measure-Command {
    1..1000 | ForEach-Object { "Hello: $_" }
}).TotalMilliseconds
24.9277
```

<span data-ttu-id="01e15-179">В первом примере показан цикл foreach, который создает задания потоков 1000, чтобы выполнить простую запись в строку.</span><span class="sxs-lookup"><span data-stu-id="01e15-179">The first example above shows a foreach loop that creates 1000 thread jobs to do a simple string write.</span></span> <span data-ttu-id="01e15-180">Из-за накладных расходов на задание выполнение займет более 33 секунд.</span><span class="sxs-lookup"><span data-stu-id="01e15-180">Due to job overhead, it takes over 33 seconds to complete.</span></span>

<span data-ttu-id="01e15-181">Во втором примере командлет выполняется `ForEach` для выполнения тех же операций 1000, и каждая строка записи выполняется последовательно без дополнительных издержек заданий.</span><span class="sxs-lookup"><span data-stu-id="01e15-181">The second example runs the `ForEach` cmdlet to do the same 1000 operations and each string write is executed sequentially without any job overhead.</span></span> <span data-ttu-id="01e15-182">Она завершается всего за 25 миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="01e15-182">It completes in a mere 25 milliseconds.</span></span>

```powershell
$logNames.count
10

Measure-Command {
    $logs = $logNames | ForEach {
        Start-ThreadJob {
            Get-WinEvent -LogName $using:_ -MaxEvents 5000 2>$null
        } -ThrottleLimit 10
    } | Wait-Job | Receive-Job
}

TotalMilliseconds : 115994.3 (1 minute 56 seconds)
$logs.Count
50000
```

<span data-ttu-id="01e15-183">В приведенном выше примере собираются до 5000 записей для 10 отдельных системных журналов.</span><span class="sxs-lookup"><span data-stu-id="01e15-183">In the above example, up to 5000 entries are collected for 10 separate system logs.</span></span> <span data-ttu-id="01e15-184">Поскольку сценарий включает чтение нескольких журналов, имеет смысл выполнять операции параллельно.</span><span class="sxs-lookup"><span data-stu-id="01e15-184">Since the script involves reading a number of logs, it makes sense to do the operations in parallel.</span></span> <span data-ttu-id="01e15-185">И выполнение задания выполняется в два раза быстрее, как если бы сценарий выполнялся последовательно.</span><span class="sxs-lookup"><span data-stu-id="01e15-185">And the job completes over twice as fast as when the script is run sequentially.</span></span>

```powershell
Measure-Command {
    $logs = $logNames | ForEach-Object {
        Get-WinEvent -LogName $_ -MaxEvents 5000 2>$null
    }
}

TotalMilliseconds : 252398.4321 (4 minutes 12 seconds)
$logs.Count
50000
```

## <a name="thread-jobs-and-variables"></a><span data-ttu-id="01e15-186">Задания и переменные потоков</span><span class="sxs-lookup"><span data-stu-id="01e15-186">Thread jobs and variables</span></span>

<span data-ttu-id="01e15-187">Переменные передаются в задания потоков различными способами.</span><span class="sxs-lookup"><span data-stu-id="01e15-187">Variables are passed into thread jobs in various ways.</span></span>

<span data-ttu-id="01e15-188">`Start-ThreadJob` может принимать переменные, передаваемые в командлет, переданные в блок скрипта через `$using` ключевое слово или передаваемые через параметр **ArgumentList** .</span><span class="sxs-lookup"><span data-stu-id="01e15-188">`Start-ThreadJob` can accept variables that are piped to the cmdlet, passed in to the script block via the `$using` keyword, or passed in via the **ArgumentList** parameter.</span></span>

```powershell
$msg = "Hello"

$msg | Start-ThreadJob { $input | Write-Output } | Wait-Job | Receive-Job

Start-ThreadJob { Write-Output $using:msg } | Wait-Job | Receive-Job

Start-ThreadJob { param ([string] $message) Write-Output $message } -ArgumentList @($msg) |
  Wait-Job | Receive-Job

`ForEach-Object -Parallel` accepts piped in variables, and variables passed
directly to the script block via the `$using` keyword.

```powershell
$msg = "Hello"

$msg | ForEach-Object -Parallel { Write-Output $_ } -AsJob | Wait-Job | Receive-Job

1..1 | ForEach-Object -Parallel { Write-Output $using:msg } -AsJob | Wait-Job | Receive-Job
```

<span data-ttu-id="01e15-189">Так как задания потоков выполняются в одном процессе, любой ссылочный тип переменной, переданный в задание, должен обрабатываться аккуратно.</span><span class="sxs-lookup"><span data-stu-id="01e15-189">Since thread jobs run in the same process, any variable reference type passed into the job has to be treated carefully.</span></span> <span data-ttu-id="01e15-190">Если он не является потокобезопасным объектом, ему никогда не следует присваивать значение, а метод и свойства никогда не должны вызываться для него.</span><span class="sxs-lookup"><span data-stu-id="01e15-190">If it is not a thread safe object, then it should never be assigned to, and method and properties should never be invoked on it.</span></span>

```powershell
$threadSafeDictionary = [System.Collections.Concurrent.ConcurrentDictionary[string,object]]::new()
$jobs = Get-Process | ForEach {
    Start-ThreadJob {
        $proc = $using:_
        $dict = $using:threadSafeDictionary
        $dict.TryAdd($proc.ProcessName, $proc)
    }
}
$jobs | Wait-Job | Receive-Job

$threadSafeDictionary.Count
96

$threadSafeDictionary["pwsh"]

NPM(K)  PM(M)   WS(M) CPU(s)    Id SI ProcessName
------  -----   ----- ------    -- -- -----------
  112  108.25  124.43  69.75 16272  1 pwsh
```

<span data-ttu-id="01e15-191">В приведенном выше примере объект dotNet, являющийся потокобезопасным, передается `ConcurrentDictionary` всем дочерним заданиям для получения объектов процессов с уникальными именами.</span><span class="sxs-lookup"><span data-stu-id="01e15-191">The above example passes a thread safe dotNet `ConcurrentDictionary` object to all child jobs to collect uniquely named process objects.</span></span> <span data-ttu-id="01e15-192">Поскольку это потокобезопасный объект, его можно безопасно использовать во время параллельного выполнения заданий в процессе.</span><span class="sxs-lookup"><span data-stu-id="01e15-192">Since it is a thread safe object, it can be safely used while the jobs run concurrently in the process.</span></span>

## <a name="see-also"></a><span data-ttu-id="01e15-193">См. также статью</span><span class="sxs-lookup"><span data-stu-id="01e15-193">See also</span></span>

- [<span data-ttu-id="01e15-194">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="01e15-194">about_Remote_Jobs</span></span>](about_Remote_Jobs.md)
- [<span data-ttu-id="01e15-195">about_Thread_Jobs</span><span class="sxs-lookup"><span data-stu-id="01e15-195">about_Thread_Jobs</span></span>](about_Thread_Jobs.md)
- [<span data-ttu-id="01e15-196">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="01e15-196">about_Job_Details</span></span>](about_Job_Details.md)
- [<span data-ttu-id="01e15-197">about_Remote</span><span class="sxs-lookup"><span data-stu-id="01e15-197">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="01e15-198">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="01e15-198">about_PSSessions</span></span>](about_PSSessions.md)
- [<span data-ttu-id="01e15-199">Start-Job</span><span class="sxs-lookup"><span data-stu-id="01e15-199">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="01e15-200">Get-Job.</span><span class="sxs-lookup"><span data-stu-id="01e15-200">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="01e15-201">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="01e15-201">Receive-Job</span></span>](xref:Microsoft.PowerShell.Core.Receive-Job)
- [<span data-ttu-id="01e15-202">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="01e15-202">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="01e15-203">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="01e15-203">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="01e15-204">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="01e15-204">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
