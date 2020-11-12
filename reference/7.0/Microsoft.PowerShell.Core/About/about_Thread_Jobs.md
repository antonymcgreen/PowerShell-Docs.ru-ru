---
description: Предоставляет сведения о заданиях, основанных на потоках PowerShell. Задание потока — это тип фонового задания, выполняющего команду или выражение в отдельном потоке в рамках текущего процесса сеанса.
keywords: powershell,командлет
Locale: en-US
ms.date: 11/11/2020
online version: 1.0.0
schema: 2.0.0
title: about_Thread_Jobs
ms.openlocfilehash: ba6251a195d3efdebd427b3f705386336b069211
ms.sourcegitcommit: aac365f7813756e16b59322832a904e703e0465b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2020
ms.locfileid: "94524643"
---
# <a name="about-thread-jobs"></a><span data-ttu-id="627be-105">О заданиях потоков</span><span class="sxs-lookup"><span data-stu-id="627be-105">About Thread Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="627be-106">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="627be-106">Short description</span></span>

<span data-ttu-id="627be-107">Предоставляет сведения о заданиях, основанных на потоках PowerShell.</span><span class="sxs-lookup"><span data-stu-id="627be-107">Provides information about PowerShell thread-based jobs.</span></span> <span data-ttu-id="627be-108">Задание потока — это тип фонового задания, выполняющего команду или выражение в отдельном потоке в рамках текущего процесса сеанса.</span><span class="sxs-lookup"><span data-stu-id="627be-108">A thread job is a type of background job that runs a command or expression in a separate thread within the current session process.</span></span>

## <a name="long-description"></a><span data-ttu-id="627be-109">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="627be-109">Long description</span></span>

<span data-ttu-id="627be-110">PowerShell параллельно выполняет команды и скрипты с помощью заданий.</span><span class="sxs-lookup"><span data-stu-id="627be-110">PowerShell concurrently runs commands and scripts through jobs.</span></span> <span data-ttu-id="627be-111">Существует три типа заданий, предоставляемых PowerShell для поддержки параллелизма.</span><span class="sxs-lookup"><span data-stu-id="627be-111">There are three jobs types provided by PowerShell to support concurrency.</span></span>

- <span data-ttu-id="627be-112">`RemoteJob` — Команды и скрипты выполняются в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="627be-112">`RemoteJob` - Commands and scripts run in a remote session.</span></span> <span data-ttu-id="627be-113">Дополнительные сведения см. в разделе [about_Remote_Jobs](about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="627be-113">For information, see [about_Remote_Jobs](about_Remote_Jobs.md).</span></span>
- <span data-ttu-id="627be-114">`BackgroundJob` — Команды и скрипты выполняются в отдельном процессе на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="627be-114">`BackgroundJob` - Commands and scripts run in a separate process on the local machine.</span></span> <span data-ttu-id="627be-115">См. дополнительные сведения о [заданиях](about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="627be-115">For more information, see [about_Jobs](about_Jobs.md).</span></span>
- <span data-ttu-id="627be-116">`PSTaskJob` или `ThreadJob` — команды и скрипты выполняются в отдельном потоке в том же процессе на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="627be-116">`PSTaskJob` or `ThreadJob` - Commands and scripts run in a separate thread within the same process on the local machine.</span></span>

<span data-ttu-id="627be-117">Задания на основе потоков не так надежны, как удаленные и фоновые задания, так как они выполняются в одном и том же процессе в разных потоках.</span><span class="sxs-lookup"><span data-stu-id="627be-117">Thread-based jobs are not as robust as remote and background jobs, because they run in the same process on different threads.</span></span> <span data-ttu-id="627be-118">Если в одном задании есть критическая ошибка, которая приводит к сбою процесса, то все остальные задания в этом процессе завершаются.</span><span class="sxs-lookup"><span data-stu-id="627be-118">If one job has a critical error that crashes the process, then all other jobs in the process are terminated.</span></span>

<span data-ttu-id="627be-119">Однако задания на основе потоков нуждаются в меньшей нагрузке.</span><span class="sxs-lookup"><span data-stu-id="627be-119">However, thread-based jobs require less overhead.</span></span> <span data-ttu-id="627be-120">Они не используют удаленный уровень или сериализацию.</span><span class="sxs-lookup"><span data-stu-id="627be-120">They don't use the remoting layer or serialization.</span></span> <span data-ttu-id="627be-121">Результирующие объекты возвращаются в виде ссылок на активные объекты в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="627be-121">The result objects are returned as references to live objects in the current session.</span></span> <span data-ttu-id="627be-122">Без такой нагрузки задания на основе потоков выполняются быстрее и используют меньше ресурсов, чем другие типы заданий.</span><span class="sxs-lookup"><span data-stu-id="627be-122">Without this overhead, thread-based jobs run faster and use fewer resources than the other job types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="627be-123">Родительский сеанс, создавший задание, также отслеживает состояние задания и собирает данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="627be-123">The parent session that created the job also monitors the job status and collects pipeline data.</span></span> <span data-ttu-id="627be-124">Дочерний процесс задания завершается родительским процессом после того, как задание достигнет завершенного состояния.</span><span class="sxs-lookup"><span data-stu-id="627be-124">The job child process is terminated by the parent process once the job reaches a finished state.</span></span> <span data-ttu-id="627be-125">Если родительский сеанс завершается, все выполняющиеся дочерние задания завершаются вместе с их дочерними процессами.</span><span class="sxs-lookup"><span data-stu-id="627be-125">If the parent session is terminated, all running child jobs are terminated along with their child processes.</span></span>

<span data-ttu-id="627be-126">Существует два способа обойти эту ситуацию.</span><span class="sxs-lookup"><span data-stu-id="627be-126">There are two ways work around this situation:</span></span>

1. <span data-ttu-id="627be-127">Используйте `Invoke-Command` для создания заданий, выполняемых в отключенных сеансах.</span><span class="sxs-lookup"><span data-stu-id="627be-127">Use `Invoke-Command` to create jobs that run in disconnected sessions.</span></span> <span data-ttu-id="627be-128">Дополнительные сведения см. в разделе [about_Remote_Jobs](about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="627be-128">For more information, see [about_Remote_Jobs](about_Remote_Jobs.md).</span></span>
1. <span data-ttu-id="627be-129">Используйте `Start-Process` для создания нового процесса, а не задания.</span><span class="sxs-lookup"><span data-stu-id="627be-129">Use `Start-Process` to create a new process rather than a job.</span></span> <span data-ttu-id="627be-130">Дополнительные сведения см. в разделе [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).</span><span class="sxs-lookup"><span data-stu-id="627be-130">For more information, see [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).</span></span>

## <a name="how-to-start-and-manage-thread-based-jobs"></a><span data-ttu-id="627be-131">Запуск и управление заданиями на основе потоков</span><span class="sxs-lookup"><span data-stu-id="627be-131">How to start and manage thread-based jobs</span></span>

<span data-ttu-id="627be-132">Запускать задания на основе потоков можно двумя способами:</span><span class="sxs-lookup"><span data-stu-id="627be-132">There are two ways to start thread-based jobs:</span></span>

- <span data-ttu-id="627be-133">`Start-ThreadJob`— из модуля **среаджоб**</span><span class="sxs-lookup"><span data-stu-id="627be-133">`Start-ThreadJob` - from the **ThreadJob** module</span></span>
- <span data-ttu-id="627be-134">`ForEach-Object -Parallel -AsJob` — компонент Parallel был добавлен в PowerShell 7,0</span><span class="sxs-lookup"><span data-stu-id="627be-134">`ForEach-Object -Parallel -AsJob` - the parallel feature was added in PowerShell 7.0</span></span>

<span data-ttu-id="627be-135">Используйте те же командлеты **задания** , которые описаны в [about_Jobs](about_Jobs.md) для управления заданиями на основе потоков.</span><span class="sxs-lookup"><span data-stu-id="627be-135">Use the same **Job** cmdlets described in [about_Jobs](about_Jobs.md) to manage thread-based jobs.</span></span>

### <a name="using-start-threadjob"></a><span data-ttu-id="627be-136">Использование `Start-ThreadJob`</span><span class="sxs-lookup"><span data-stu-id="627be-136">Using `Start-ThreadJob`</span></span>

<span data-ttu-id="627be-137">Модуль **среаджоб** , который впервые поставлялся с PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="627be-137">The **ThreadJob** module first shipped with PowerShell 6.</span></span> <span data-ttu-id="627be-138">Его также можно установить из коллекция PowerShell для Windows PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="627be-138">It can also be installed from the PowerShell Gallery for Windows PowerShell 5.1.</span></span>

<span data-ttu-id="627be-139">Чтобы запустить задание потока на локальном компьютере, используйте `Start-ThreadJob` командлет с командой или сценарием, заключенными в фигурные скобки ( `{ }` ).</span><span class="sxs-lookup"><span data-stu-id="627be-139">To start a thread job on the local computer, use the `Start-ThreadJob` cmdlet with a command or script enclosed in curly braces (`{ }`).</span></span>

<span data-ttu-id="627be-140">В следующем примере запускается задание потока, выполняющее `Get-Process` команду на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="627be-140">The following example starts a thread job that runs a `Get-Process` command on the local computer.</span></span>

```powershell
Start-ThreadJob -ScriptBlock { Get-Process }
```

<span data-ttu-id="627be-141">`Start-ThreadJob`Команда возвращает `ThreadJob` объект, представляющий выполняемое задание.</span><span class="sxs-lookup"><span data-stu-id="627be-141">The `Start-ThreadJob` command returns a `ThreadJob` object that represents the running job.</span></span> <span data-ttu-id="627be-142">Объект задания содержит полезные сведения о задании, включая текущее состояние выполнения.</span><span class="sxs-lookup"><span data-stu-id="627be-142">The job object contains useful information about the job including its current running status.</span></span> <span data-ttu-id="627be-143">Он собирает результаты выполнения задания по мере формирования результатов.</span><span class="sxs-lookup"><span data-stu-id="627be-143">It collects the results of the job as the results are being generated.</span></span>

### <a name="using-foreach-object--parallel--asjob"></a><span data-ttu-id="627be-144">Использование `ForEach-Object -Parallel -AsJob`</span><span class="sxs-lookup"><span data-stu-id="627be-144">Using `ForEach-Object -Parallel -AsJob`</span></span>

<span data-ttu-id="627be-145">В PowerShell 7,0 добавлен новый набор параметров в `ForEach-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="627be-145">PowerShell 7.0 added a new parameter set to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="627be-146">Новые параметры позволяют запускать блоки сценариев в параллельных потоках как задания PowerShell.</span><span class="sxs-lookup"><span data-stu-id="627be-146">The new parameters allow you to run script blocks in parallel threads as PowerShell jobs.</span></span>

<span data-ttu-id="627be-147">Вы можете передать данные в `ForEach-Object -Parallel` .</span><span class="sxs-lookup"><span data-stu-id="627be-147">You can pipe data to `ForEach-Object -Parallel`.</span></span> <span data-ttu-id="627be-148">Данные передаются в блок скрипта, который выполняется параллельно.</span><span class="sxs-lookup"><span data-stu-id="627be-148">The data is passed to the script block that is run in parallel.</span></span> <span data-ttu-id="627be-149">`-AsJob`Параметр создает объекты заданий для каждого из параллельных потоков.</span><span class="sxs-lookup"><span data-stu-id="627be-149">The `-AsJob` parameter creates jobs objects for each of the parallel threads.</span></span>

<span data-ttu-id="627be-150">Следующая команда запускает задание, которое содержит дочерние задания для каждого входного значения, переданного команде.</span><span class="sxs-lookup"><span data-stu-id="627be-150">The following command starts a job that contains child jobs for each input value piped to the command.</span></span> <span data-ttu-id="627be-151">Каждое дочернее задание выполняет `Write-Output` команду с входным значением, переданным в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="627be-151">Each child job runs the `Write-Output` command with a piped input value as the argument.</span></span>

```powershell
1..5 | ForEach-Object -Parallel { Write-Output $_ } -AsJob
```

<span data-ttu-id="627be-152">`ForEach-Object -Parallel`Команда возвращает `PSTaskJob` объект, содержащий дочерние задания для каждого входного значения перенаправленного.</span><span class="sxs-lookup"><span data-stu-id="627be-152">The `ForEach-Object -Parallel` command returns a `PSTaskJob` object that contains child jobs for each piped input value.</span></span> <span data-ttu-id="627be-153">Объект задания содержит полезные сведения о состоянии выполнения дочерних заданий.</span><span class="sxs-lookup"><span data-stu-id="627be-153">The job object contains useful information about the child jobs running status.</span></span> <span data-ttu-id="627be-154">Он собирает результаты дочерних заданий по мере формирования результатов.</span><span class="sxs-lookup"><span data-stu-id="627be-154">It collects the results of the child jobs as the results are being generated.</span></span>

## <a name="how-to-wait-for-a-job-to-complete-and-retrieve-job-results"></a><span data-ttu-id="627be-155">Как дождаться завершения задания и получить результаты задания</span><span class="sxs-lookup"><span data-stu-id="627be-155">How to wait for a job to complete and retrieve job results</span></span>

<span data-ttu-id="627be-156">Вы можете использовать командлеты задания PowerShell, такие как `Wait-Job` и, `Receive-Job` чтобы дождаться завершения задания, а затем вернуть все результаты, созданные заданием.</span><span class="sxs-lookup"><span data-stu-id="627be-156">You can use PowerShell job cmdlets, such as `Wait-Job` and `Receive-Job` to wait for a job to complete and then return all results generated by the job.</span></span>

<span data-ttu-id="627be-157">Следующая команда запускает задание потока, которое выполняет `Get-Process` команду, затем ожидает завершения команды и возвращает все результаты данных, созданные командой.</span><span class="sxs-lookup"><span data-stu-id="627be-157">The following command starts a thread job that runs a `Get-Process` command, then waits for the command to complete, and finally returns all data results generated by the command.</span></span>

```powershell
Start-ThreadJob -ScriptBlock { Get-Process } | Wait-Job | Receive-Job
```

<span data-ttu-id="627be-158">Следующая команда запускает задание, которое выполняет `Write-Output` команду для каждого входного значения, а затем ожидает завершения всех дочерних заданий и возвращает все результаты данных, созданные дочерними заданиями.</span><span class="sxs-lookup"><span data-stu-id="627be-158">The following command starts a job that runs a `Write-Output` command for each piped input, then waits for all child jobs to complete, and finally returns all data results generated by the child jobs.</span></span>

```powershell
1..5 | ForEach-Object -Parallel { Write-Output $_ } -AsJob | Wait-Job | Receive-Job
```

<span data-ttu-id="627be-159">`Receive-Job`Командлет возвращает результаты дочерних заданий.</span><span class="sxs-lookup"><span data-stu-id="627be-159">The `Receive-Job` cmdlet returns the results of the child jobs.</span></span>

```powershell
1
3
2
4
5
```

<span data-ttu-id="627be-160">Так как каждое дочернее задание выполняется параллельно, порядок созданных результатов не гарантируется.</span><span class="sxs-lookup"><span data-stu-id="627be-160">Because each child job runs parallel, the order of the generated results is not guaranteed.</span></span>

## <a name="thread-job-performance"></a><span data-ttu-id="627be-161">Производительность задания потока</span><span class="sxs-lookup"><span data-stu-id="627be-161">Thread job performance</span></span>

<span data-ttu-id="627be-162">Задания потоков выполняются быстрее и легче, чем другие типы заданий.</span><span class="sxs-lookup"><span data-stu-id="627be-162">Thread jobs are faster and lighter weight than other types of jobs.</span></span> <span data-ttu-id="627be-163">Но они по-прежнему имеют накладные расходы, которые могут быть большими по сравнению с работой, выполняемой заданием.</span><span class="sxs-lookup"><span data-stu-id="627be-163">But they still have overhead that can be large when compared to work the job is doing.</span></span>

<span data-ttu-id="627be-164">PowerShell запускает команды и скрипты в сеансе.</span><span class="sxs-lookup"><span data-stu-id="627be-164">PowerShell runs commands and script in a session.</span></span> <span data-ttu-id="627be-165">Только одна команда или сценарий может выполняться одновременно в сеансе.</span><span class="sxs-lookup"><span data-stu-id="627be-165">Only one command or script can run at a time in a session.</span></span> <span data-ttu-id="627be-166">Поэтому при выполнении нескольких заданий каждое задание выполняется в отдельном сеансе.</span><span class="sxs-lookup"><span data-stu-id="627be-166">So when running multiple jobs, each job runs in a separate session.</span></span> <span data-ttu-id="627be-167">Каждый сеанс влияет на накладные расходы.</span><span class="sxs-lookup"><span data-stu-id="627be-167">Each session contributes to the overhead.</span></span>

<span data-ttu-id="627be-168">Задания потоков обеспечивают наилучшую производительность, когда работа, выполняемая ими, превышает издержки сеанса, используемого для выполнения задания.</span><span class="sxs-lookup"><span data-stu-id="627be-168">Thread jobs provide the best performance when the work they perform is greater than the overhead of the session used to run the job.</span></span> <span data-ttu-id="627be-169">Существует два варианта соответствия этого критерия.</span><span class="sxs-lookup"><span data-stu-id="627be-169">There are two cases for that meet this criteria.</span></span>

- <span data-ttu-id="627be-170">Работа — это большое количество вычислительных ресурсов. выполнение скрипта для нескольких заданий потоков может использовать преимущества нескольких процессорных ядер и ускорить работу.</span><span class="sxs-lookup"><span data-stu-id="627be-170">Work is compute intensive - Running a script on multiple thread jobs can take advantage of multiple processor cores and complete faster.</span></span>

- <span data-ttu-id="627be-171">Работа состоит из значительного ожидающего сценария, который тратит время на ожидание результатов ввода-вывода или удаленного вызова.</span><span class="sxs-lookup"><span data-stu-id="627be-171">Work consists of significant waiting - A script that spends time waiting for I/O or remote call results.</span></span> <span data-ttu-id="627be-172">Параллельное выполнение обычно завершается быстрее, чем при последовательном выполнении.</span><span class="sxs-lookup"><span data-stu-id="627be-172">Running in parallel usually completes quicker than if run sequentially.</span></span>

```powershell
(Measure-Command {
    1..1000 | ForEach { Start-ThreadJob { Write-Output "Hello $using:_" } } | Receive-Job -Wait
}).TotalMilliseconds
36860.8226

(Measure-Command {
    1..1000 | ForEach-Object { "Hello: $_" }
}).TotalMilliseconds
7.1975
```

<span data-ttu-id="627be-173">В первом примере показан цикл foreach, который создает задания потоков 1000, чтобы выполнить простую запись в строку.</span><span class="sxs-lookup"><span data-stu-id="627be-173">The first example above shows a foreach loop that creates 1000 thread jobs to do a simple string write.</span></span> <span data-ttu-id="627be-174">Из-за накладных расходов на задание выполнение займет более 36 секунд.</span><span class="sxs-lookup"><span data-stu-id="627be-174">Due to job overhead, it takes over 36 seconds to complete.</span></span>

<span data-ttu-id="627be-175">Во втором примере командлет запускается `ForEach` для выполнения тех же операций 1000.</span><span class="sxs-lookup"><span data-stu-id="627be-175">The second example runs the `ForEach` cmdlet to do the same 1000 operations.</span></span>
<span data-ttu-id="627be-176">На этот раз `ForEach-Object` выполняется последовательно в одном потоке без дополнительных издержек заданий.</span><span class="sxs-lookup"><span data-stu-id="627be-176">This time, `ForEach-Object` runs sequentially, on a single thread, without any job overhead.</span></span> <span data-ttu-id="627be-177">Она завершается всего за 7 миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="627be-177">It completes in a mere 7 milliseconds.</span></span>

<span data-ttu-id="627be-178">В следующем примере собираются до 5000 записей для 10 отдельных системных журналов.</span><span class="sxs-lookup"><span data-stu-id="627be-178">In the following example, up to 5000 entries are collected for 10 separate system logs.</span></span> <span data-ttu-id="627be-179">Поскольку сценарий включает чтение нескольких журналов, имеет смысл выполнять операции параллельно.</span><span class="sxs-lookup"><span data-stu-id="627be-179">Since the script involves reading a number of logs, it makes sense to do the operations in parallel.</span></span>

```powershell
$logNames.count
10

Measure-Command {
    $logs = $logNames | ForEach-Object {
        Get-WinEvent -LogName $_ -MaxEvents 5000 2>$null
    }
}

TotalMilliseconds : 252398.4321 (4 minutes 12 seconds)
$logs.Count
50000
```

<span data-ttu-id="627be-180">Скрипт завершается в половину времени, когда задания выполняются параллельно.</span><span class="sxs-lookup"><span data-stu-id="627be-180">The script completes in half the time when the jobs are run in parallel.</span></span>

```powershell
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

## <a name="thread-jobs-and-variables"></a><span data-ttu-id="627be-181">Задания и переменные потоков</span><span class="sxs-lookup"><span data-stu-id="627be-181">Thread jobs and variables</span></span>

<span data-ttu-id="627be-182">Существует несколько способов передачи значений в задания на основе потоков.</span><span class="sxs-lookup"><span data-stu-id="627be-182">There are multiple ways to pass values into the thread-based jobs.</span></span>

<span data-ttu-id="627be-183">`Start-ThreadJob` может принимать переменные, передаваемые в командлет, переданные в блок скрипта через `$using` ключевое слово или передаваемые через параметр **ArgumentList** .</span><span class="sxs-lookup"><span data-stu-id="627be-183">`Start-ThreadJob` can accept variables that are piped to the cmdlet, passed in to the script block via the `$using` keyword, or passed in via the **ArgumentList** parameter.</span></span>

```powershell
$msg = "Hello"

$msg | Start-ThreadJob { $input | Write-Output } | Wait-Job | Receive-Job

Start-ThreadJob { Write-Output $using:msg } | Wait-Job | Receive-Job

Start-ThreadJob { param ([string] $message) Write-Output $message } -ArgumentList @($msg) |
  Wait-Job | Receive-Job
```

<span data-ttu-id="627be-184">`ForEach-Object -Parallel` принимает переданные переменные и переменные, передаваемые непосредственно в блок скрипта с помощью `$using` ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="627be-184">`ForEach-Object -Parallel` accepts piped in variables, and variables passed directly to the script block via the `$using` keyword.</span></span>

```powershell
$msg = "Hello"

$msg | ForEach-Object -Parallel { Write-Output $_ } -AsJob | Wait-Job | Receive-Job

1..1 | ForEach-Object -Parallel { Write-Output $using:msg } -AsJob | Wait-Job | Receive-Job
```

<span data-ttu-id="627be-185">Так как задания потоков выполняются в одном процессе, любой ссылочный тип переменной, переданный в задание, должен обрабатываться аккуратно.</span><span class="sxs-lookup"><span data-stu-id="627be-185">Since thread jobs run in the same process, any variable reference type passed into the job has to be treated carefully.</span></span> <span data-ttu-id="627be-186">Если он не является потокобезопасным объектом, ему никогда не следует присваивать значение, а метод и свойства никогда не должны вызываться для него.</span><span class="sxs-lookup"><span data-stu-id="627be-186">If it is not a thread safe object, then it should never be assigned to, and method and properties should never be invoked on it.</span></span>

<span data-ttu-id="627be-187">В следующем примере потокобезопасный объект .NET передается `ConcurrentDictionary` во все дочерние задания для получения объектов процессов с уникальными именами.</span><span class="sxs-lookup"><span data-stu-id="627be-187">The following example passes a thread-safe .NET `ConcurrentDictionary` object to all child jobs to collect uniquely named process objects.</span></span> <span data-ttu-id="627be-188">Поскольку это потокобезопасный объект, его можно безопасно использовать во время параллельного выполнения заданий в процессе.</span><span class="sxs-lookup"><span data-stu-id="627be-188">Since it is a thread safe object, it can be safely used while the jobs run concurrently in the process.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="627be-189">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="627be-189">See also</span></span>

- [<span data-ttu-id="627be-190">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="627be-190">about_Remote_Jobs</span></span>](about_Remote_Jobs.md)
- [<span data-ttu-id="627be-191">about_Thread_Jobs</span><span class="sxs-lookup"><span data-stu-id="627be-191">about_Thread_Jobs</span></span>](about_Thread_Jobs.md)
- [<span data-ttu-id="627be-192">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="627be-192">about_Job_Details</span></span>](about_Job_Details.md)
- [<span data-ttu-id="627be-193">about_Remote</span><span class="sxs-lookup"><span data-stu-id="627be-193">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="627be-194">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="627be-194">about_PSSessions</span></span>](about_PSSessions.md)
- [<span data-ttu-id="627be-195">Start-Job</span><span class="sxs-lookup"><span data-stu-id="627be-195">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="627be-196">Get-Job.</span><span class="sxs-lookup"><span data-stu-id="627be-196">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="627be-197">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="627be-197">Receive-Job</span></span>](xref:Microsoft.PowerShell.Core.Receive-Job)
- [<span data-ttu-id="627be-198">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="627be-198">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="627be-199">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="627be-199">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="627be-200">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="627be-200">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
