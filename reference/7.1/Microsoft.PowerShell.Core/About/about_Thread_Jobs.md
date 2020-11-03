---
description: Предоставляет сведения о заданиях, основанных на потоках PowerShell. Задание потока — это тип фонового задания, выполняющего команду или выражение в отдельном потоке в рамках текущего процесса сеанса.
keywords: powershell,командлет
Locale: en-US
ms.date: 10/16/2020
online version: 1.0.0
schema: 2.0.0
title: about_Thread_Jobs
ms.openlocfilehash: d3f7c2754a2e54bc1b6f9fb95d1cf6ce2fed5b9b
ms.sourcegitcommit: 108686b166672cc08817c637dd93eb1ad830511d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "93232961"
---
# <a name="about-thread-jobs"></a><span data-ttu-id="56363-105">О заданиях потоков</span><span class="sxs-lookup"><span data-stu-id="56363-105">About Thread Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="56363-106">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="56363-106">Short description</span></span>

<span data-ttu-id="56363-107">Предоставляет сведения о заданиях, основанных на потоках PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56363-107">Provides information about PowerShell thread-based jobs.</span></span> <span data-ttu-id="56363-108">Задание потока — это тип фонового задания, выполняющего команду или выражение в отдельном потоке в рамках текущего процесса сеанса.</span><span class="sxs-lookup"><span data-stu-id="56363-108">A thread job is a type of background job that runs a command or expression in a separate thread within the current session process.</span></span>

## <a name="long-description"></a><span data-ttu-id="56363-109">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="56363-109">Long description</span></span>

<span data-ttu-id="56363-110">В этой статье объясняется, как выполнять задания потоков в PowerShell на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="56363-110">This article explains how to run thread jobs in PowerShell on a local computer.</span></span>
<span data-ttu-id="56363-111">Сведения о выполнении фоновых заданий на локальном компьютере см. в разделе [about_Jobs](about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="56363-111">For information about running background jobs on a local computer, see [about_Jobs](about_Jobs.md).</span></span>

<span data-ttu-id="56363-112">Можно запустить задание потока одним из двух способов.</span><span class="sxs-lookup"><span data-stu-id="56363-112">You can start a thread job in one of two ways.</span></span>

<span data-ttu-id="56363-113">Первый способ — с помощью `Start-ThreadJob` командлета.</span><span class="sxs-lookup"><span data-stu-id="56363-113">The first way is with the `Start-ThreadJob` cmdlet.</span></span> <span data-ttu-id="56363-114">Этот командлет доступен в модуле **среаджоб** , который поставляется с PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56363-114">This cmdlet is available in the **ThreadJob** module that ships with PowerShell.</span></span> <span data-ttu-id="56363-115">`Start-ThreadJob` Возвращает один объект задания, который инкапсулирует выполняющуюся команду или скрипт, и может использоваться со всеми командлетами задания PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56363-115">`Start-ThreadJob` returns a single job object that encapsulates the running command or script, and can be used with all PowerShell job manipulating cmdlets.</span></span>

<span data-ttu-id="56363-116">Второй способ заключается в использовании `ForEach-Object` командлета с `-Parallel` аргументом блока скрипта Parameter вместе с `-AsJob` параметром Parameter.</span><span class="sxs-lookup"><span data-stu-id="56363-116">The second way is with the `ForEach-Object` cmdlet, with the `-Parallel` parameter script block argument along with the `-AsJob` parameter switch.</span></span> <span data-ttu-id="56363-117">Этот командлет возвращает единичный (родительский) объект задания, который содержит дочернее задание для каждого входа, переданного в командлет.</span><span class="sxs-lookup"><span data-stu-id="56363-117">This cmdlet returns a single (parent) job object that contains a child job for each input piped to the cmdlet.</span></span> <span data-ttu-id="56363-118">Каждое дочернее задание запускает сценарий в отдельном потоке с `-ThrottleLimit` ограничением () для того, сколько дочерних заданий выполняется в определенный момент времени.</span><span class="sxs-lookup"><span data-stu-id="56363-118">Each child job runs script in a separate thread with a (`-ThrottleLimit`) limit to how many child jobs run at a given time.</span></span>

## <a name="the-job-cmdlets"></a><span data-ttu-id="56363-119">КОМАНДЛЕТЫ ЗАДАНИЯ</span><span class="sxs-lookup"><span data-stu-id="56363-119">THE JOB CMDLETS</span></span>

|<span data-ttu-id="56363-120">Командлет</span><span class="sxs-lookup"><span data-stu-id="56363-120">Cmdlet</span></span>           |<span data-ttu-id="56363-121">Описание</span><span class="sxs-lookup"><span data-stu-id="56363-121">Description</span></span>                                            |
|-----------------|-------------------------------------------------------|
|`Start-ThreadJob`|<span data-ttu-id="56363-122">Запускает задание потока на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="56363-122">Starts a thread job on a local computer.</span></span>               |
|`ForEach-Object` |<span data-ttu-id="56363-123">Запускает задания потока для каждого входного объекта, когда</span><span class="sxs-lookup"><span data-stu-id="56363-123">Starts thread jobs for each piped input object, when</span></span>   |
|                 |<span data-ttu-id="56363-124">используются с параметрами-Parallel и-AsJob.</span><span class="sxs-lookup"><span data-stu-id="56363-124">used with -Parallel and -AsJob parameters.</span></span>             |
|`Get-Job`        |<span data-ttu-id="56363-125">Возвращает задания, запущенные в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="56363-125">Gets the jobs that were started in the current session.</span></span>|
|`Receive-Job`    |<span data-ttu-id="56363-126">Возвращает результаты заданий.</span><span class="sxs-lookup"><span data-stu-id="56363-126">Gets the results of jobs.</span></span>                              |
|`Stop-Job`       |<span data-ttu-id="56363-127">Останавливает выполняющееся задание.</span><span class="sxs-lookup"><span data-stu-id="56363-127">Stops a running job.</span></span>                                   |
|`Wait-Job`       |<span data-ttu-id="56363-128">Подавляет командную строку до тех пор, пока одно или все задания не будут</span><span class="sxs-lookup"><span data-stu-id="56363-128">Suppresses the command prompt until one or all jobs are</span></span>|
|                 |<span data-ttu-id="56363-129">завершения.</span><span class="sxs-lookup"><span data-stu-id="56363-129">complete.</span></span>                                              |
|`Remove-Job`     |<span data-ttu-id="56363-130">Удаляет задание.</span><span class="sxs-lookup"><span data-stu-id="56363-130">Deletes a job.</span></span>                                         |

## <a name="how-to-start-a-thread-job-on-the-local-computer"></a><span data-ttu-id="56363-131">Запуск задания потока на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="56363-131">How to start a thread job on the local computer</span></span>

<span data-ttu-id="56363-132">Чтобы запустить задание потока на локальном компьютере, используйте `Start-ThreadJob` командлет.</span><span class="sxs-lookup"><span data-stu-id="56363-132">To start a thread job on the local computer, use the `Start-ThreadJob` cmdlet.</span></span>

<span data-ttu-id="56363-133">Чтобы написать `Start-ThreadJob` команду, заключите команду или скрипт, выполняемые заданием, в фигурные скобки ( `{ }` ).</span><span class="sxs-lookup"><span data-stu-id="56363-133">To write a `Start-ThreadJob` command, enclose the command or script the job runs in curly braces (`{ }`).</span></span>

<span data-ttu-id="56363-134">Следующая команда запускает задание потока, которое выполняет `Get-Process` команду на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="56363-134">The following command starts a thread job that runs a `Get-Process` command on the local computer.</span></span>

```powershell
Start-ThreadJob -ScriptBlock { Get-Process }
```

<span data-ttu-id="56363-135">`Start-ThreadJob`Команда возвращает `ThreadJob` объект, представляющий выполняемое задание.</span><span class="sxs-lookup"><span data-stu-id="56363-135">The `Start-ThreadJob` command returns a `ThreadJob` object that represents the running job.</span></span> <span data-ttu-id="56363-136">Объект задания содержит полезные сведения о задании, включая текущее состояние выполнения.</span><span class="sxs-lookup"><span data-stu-id="56363-136">The job object contains useful information about the job including its current running status.</span></span> <span data-ttu-id="56363-137">Он собирает результаты выполнения задания по мере формирования результатов.</span><span class="sxs-lookup"><span data-stu-id="56363-137">It collects the results of the job as the results are being generated.</span></span>

<span data-ttu-id="56363-138">Чтобы записать `ForEach-Object -Parallel` команду, передать данные в команду и заключить команду или скрипт, выполняемые заданием, в фигурные скобки ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="56363-138">To write a `ForEach-Object -Parallel` command, pipe data to the command and enclose the command or script the job runs in curly braces(`{}`).</span></span> <span data-ttu-id="56363-139">Используйте `-AsJob` параметр параметра, чтобы возвращался объект задания.</span><span class="sxs-lookup"><span data-stu-id="56363-139">Use the `-AsJob` parameter switch so that a job object is returned.</span></span>

<span data-ttu-id="56363-140">Следующая команда запускает задание, которое содержит дочерние задания для каждого входного значения, переданного команде.</span><span class="sxs-lookup"><span data-stu-id="56363-140">The following command starts a job that contains child jobs for each input value piped to the command.</span></span> <span data-ttu-id="56363-141">Каждое дочернее задание выполняет `Write-Output` команду с входным значением, переданным в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="56363-141">Each child job runs the `Write-Output` command with a piped input value as the argument.</span></span>

```powershell
1..5 | ForEach-Object -Parallel { Write-Output $_ } -AsJob
```

<span data-ttu-id="56363-142">`ForEach-Object -Parallel`Команда возвращает `PSTaskJob` объект, содержащий дочерние задания для каждого входного значения перенаправленного.</span><span class="sxs-lookup"><span data-stu-id="56363-142">The `ForEach-Object -Parallel` command returns a `PSTaskJob` object that contains child jobs for each piped input value.</span></span> <span data-ttu-id="56363-143">Объект задания содержит полезные сведения о состоянии выполнения дочерних заданий.</span><span class="sxs-lookup"><span data-stu-id="56363-143">The job object contains useful information about the child jobs running status.</span></span> <span data-ttu-id="56363-144">Он собирает результаты дочерних заданий по мере формирования результатов.</span><span class="sxs-lookup"><span data-stu-id="56363-144">It collects the results of the child jobs as the results are being generated.</span></span>

## <a name="how-to-wait-for-a-job-to-complete-and-retrieve-job-results"></a><span data-ttu-id="56363-145">Как дождаться завершения задания и получить результаты задания</span><span class="sxs-lookup"><span data-stu-id="56363-145">How to wait for a job to complete and retrieve job results</span></span>

<span data-ttu-id="56363-146">Вы можете использовать командлеты задания PowerShell, такие как `Wait-Job` и, `Receive-Job` чтобы дождаться завершения задания, а затем вернуть все результаты, созданные заданием.</span><span class="sxs-lookup"><span data-stu-id="56363-146">You can use PowerShell job cmdlets, such as `Wait-Job` and `Receive-Job` to wait for a job to complete and then return all results generated by the job.</span></span>

<span data-ttu-id="56363-147">Следующая команда запускает задание потока, которое выполняет `Get-Process` команду, затем ожидает завершения команды и возвращает все результаты данных, созданные командой.</span><span class="sxs-lookup"><span data-stu-id="56363-147">The following command starts a thread job that runs a `Get-Process` command, then waits for the command to complete, and finally returns all data results generated by the command.</span></span>

```powershell
Start-ThreadJob -ScriptBlock { Get-Process } | Wait-Job | Receive-Job
```

<span data-ttu-id="56363-148">Следующая команда запускает задание, которое выполняет `Write-Output` команду для каждого входного значения, а затем ожидает завершения всех дочерних заданий и возвращает все результаты данных, созданные дочерними заданиями.</span><span class="sxs-lookup"><span data-stu-id="56363-148">The following command starts a job that runs a `Write-Output` command for each piped input, then waits for all child jobs to complete, and finally returns all data results generated by the child jobs.</span></span>

```powershell
1..5 | ForEach-Object -Parallel { Write-Output $_ } -AsJob | Wait-Job | Receive-Job
```

<span data-ttu-id="56363-149">`Receive-Job`Командлет возвращает результаты дочерних заданий.</span><span class="sxs-lookup"><span data-stu-id="56363-149">The `Receive-Job` cmdlet returns the results of the child jobs.</span></span>

```powershell
1
3
2
4
5
```

<span data-ttu-id="56363-150">Так как каждое дочернее задание выполняется параллельно, порядок созданных результатов не гарантируется.</span><span class="sxs-lookup"><span data-stu-id="56363-150">Because each child job runs parallel, the order of the generated results is not guaranteed.</span></span>

## <a name="powershell-concurrency-and-jobs"></a><span data-ttu-id="56363-151">Параллелизм и задания PowerShell</span><span class="sxs-lookup"><span data-stu-id="56363-151">PowerShell concurrency and jobs</span></span>

<span data-ttu-id="56363-152">PowerShell параллельно выполняет команды и скрипты с помощью заданий.</span><span class="sxs-lookup"><span data-stu-id="56363-152">PowerShell concurrently runs commands and script through jobs.</span></span> <span data-ttu-id="56363-153">Существует три решения на основе заданий, предоставляемые PowerShell для поддержки параллелизма.</span><span class="sxs-lookup"><span data-stu-id="56363-153">There are three jobs-based solutions provided by PowerShell to support concurrency.</span></span>

|<span data-ttu-id="56363-154">Задание</span><span class="sxs-lookup"><span data-stu-id="56363-154">Job</span></span>            |<span data-ttu-id="56363-155">Описание</span><span class="sxs-lookup"><span data-stu-id="56363-155">Description</span></span>                                                  |
|---------------|-------------------------------------------------------------|
|`RemoteJob`    |<span data-ttu-id="56363-156">Команда и сценарий выполняются на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="56363-156">Command and script run on a remote computer.</span></span>                 |
|`BackgroundJob`|<span data-ttu-id="56363-157">Команда и сценарий выполняются в отдельном процессе в локальной системе</span><span class="sxs-lookup"><span data-stu-id="56363-157">Command and script run in a separate process on the local</span></span>    |
|               |<span data-ttu-id="56363-158">машине.</span><span class="sxs-lookup"><span data-stu-id="56363-158">machine.</span></span>                                                     |
|`ThreadJob`    |<span data-ttu-id="56363-159">Команда и сценарий выполняются в отдельном потоке в том же</span><span class="sxs-lookup"><span data-stu-id="56363-159">Command and script run in a separate thread within the same</span></span>  |
|               |<span data-ttu-id="56363-160">процесс на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="56363-160">process on the local machine.</span></span>                                |

<span data-ttu-id="56363-161">Каждый тип задания имеет свои преимущества и недостатки.</span><span class="sxs-lookup"><span data-stu-id="56363-161">Each type of job has benefits and drawbacks.</span></span> <span data-ttu-id="56363-162">Удаленное выполнение сценария на отдельном компьютере или в отдельном процессе имеет большую изоляцию.</span><span class="sxs-lookup"><span data-stu-id="56363-162">Running script remotely on a separate machine or in a separate process has great isolation.</span></span> <span data-ttu-id="56363-163">Любые ошибки не влияют на другие выполняющиеся задания или на клиент, запустивший задание.</span><span class="sxs-lookup"><span data-stu-id="56363-163">Any errors won't affect other running jobs or the client that started the job.</span></span> <span data-ttu-id="56363-164">Но на уровне удаленного взаимодействия добавляются дополнительные издержки, включая сериализацию объектов.</span><span class="sxs-lookup"><span data-stu-id="56363-164">But the remoting layer adds overhead, including object serialization.</span></span> <span data-ttu-id="56363-165">Все объекты, передаваемые в удаленный сеанс и из него, должны быть сериализованы и десериализованы при передаче между клиентом и целевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="56363-165">All objects passed to and from the remote session must be serialized and then deserialized as it passes between the client and the target session.</span></span> <span data-ttu-id="56363-166">Операция сериализации может использовать много ресурсов вычислений и памяти для больших сложных объектов данных.</span><span class="sxs-lookup"><span data-stu-id="56363-166">The serialization operation can use many compute and memory resources for large complex data objects.</span></span>

## <a name="powershell-thread-based-jobs"></a><span data-ttu-id="56363-167">Задания на основе потока PowerShell</span><span class="sxs-lookup"><span data-stu-id="56363-167">PowerShell thread based jobs</span></span>

<span data-ttu-id="56363-168">Задания на основе потоков не так надежны, как удаленные и фоновые задания, так как они выполняются в одном и том же процессе в разных потоках.</span><span class="sxs-lookup"><span data-stu-id="56363-168">Thread based jobs are not as robust as Remote and Background jobs, because they run in the same process on different threads.</span></span> <span data-ttu-id="56363-169">Если в одном задании есть критическая ошибка, которая приводит к сбою процесса, то все остальные задания в процессе также завершатся ошибкой.</span><span class="sxs-lookup"><span data-stu-id="56363-169">If one job has a critical error that crashes the process, then all other jobs in the process will also fail.</span></span>

<span data-ttu-id="56363-170">Однако задания на основе потоков значительно меньше издержек.</span><span class="sxs-lookup"><span data-stu-id="56363-170">However, thread-based jobs have much less overhead.</span></span> <span data-ttu-id="56363-171">Им не нужно использовать удаленный уровень или сериализацию.</span><span class="sxs-lookup"><span data-stu-id="56363-171">They don't need to use the remoting layer or serialization.</span></span> <span data-ttu-id="56363-172">В результате задания на основе потоков выполняются гораздо быстрее и используют гораздо меньшие ресурсы, чем другие типы заданий.</span><span class="sxs-lookup"><span data-stu-id="56363-172">The result is that thread-based jobs tend to run much faster and use far less resources than the other job types.</span></span>

## <a name="thread-job-performance"></a><span data-ttu-id="56363-173">Производительность задания потока</span><span class="sxs-lookup"><span data-stu-id="56363-173">Thread job performance</span></span>

<span data-ttu-id="56363-174">Задания потоков выполняются быстрее и легче, чем другие типы заданий.</span><span class="sxs-lookup"><span data-stu-id="56363-174">Thread jobs are faster and lighter weight than other types of jobs.</span></span> <span data-ttu-id="56363-175">Но они по-прежнему имеют накладные расходы, которые могут быть большими по сравнению с работой, выполняемой заданием.</span><span class="sxs-lookup"><span data-stu-id="56363-175">But they still have overhead that can be large when compared to work the job is doing.</span></span>

<span data-ttu-id="56363-176">PowerShell запускает команды и скрипты в сеансе.</span><span class="sxs-lookup"><span data-stu-id="56363-176">PowerShell runs commands and script in a session.</span></span> <span data-ttu-id="56363-177">Только одна команда или сценарий может выполняться одновременно в сеансе.</span><span class="sxs-lookup"><span data-stu-id="56363-177">Only one command or script can run at a time in a session.</span></span> <span data-ttu-id="56363-178">Поэтому при выполнении нескольких заданий каждое задание выполняется в отдельном сеансе.</span><span class="sxs-lookup"><span data-stu-id="56363-178">So when running multiple jobs, each job runs in a separate session.</span></span> <span data-ttu-id="56363-179">Каждый сеанс влияет на накладные расходы.</span><span class="sxs-lookup"><span data-stu-id="56363-179">Each session contributes to the overhead.</span></span>

<span data-ttu-id="56363-180">Задания потоков обеспечивают наилучшую производительность, когда работа, выполняемая ими, превышает издержки сеанса, используемого для выполнения задания.</span><span class="sxs-lookup"><span data-stu-id="56363-180">Thread jobs provide the best performance when the work they perform is greater than the overhead of the session used to run the job.</span></span> <span data-ttu-id="56363-181">Существует два варианта соответствия этого критерия.</span><span class="sxs-lookup"><span data-stu-id="56363-181">There are two cases for that meet this criteria.</span></span>

- <span data-ttu-id="56363-182">Работа — это большое количество вычислительных ресурсов. выполнение скрипта для нескольких заданий потоков может использовать преимущества нескольких процессорных ядер и ускорить работу.</span><span class="sxs-lookup"><span data-stu-id="56363-182">Work is compute intensive - Running a script on multiple thread jobs can take advantage of multiple processor cores and complete faster.</span></span>

- <span data-ttu-id="56363-183">Работа состоит из значительного ожидающего сценария, который тратит время на ожидание результатов ввода-вывода или удаленного вызова.</span><span class="sxs-lookup"><span data-stu-id="56363-183">Work consists of significant waiting - A script that spends time waiting for I/O or remote call results.</span></span> <span data-ttu-id="56363-184">Параллельное выполнение обычно завершается быстрее, чем при последовательном выполнении.</span><span class="sxs-lookup"><span data-stu-id="56363-184">Running in parallel usually completes quicker than if run sequentially.</span></span>

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

<span data-ttu-id="56363-185">В первом примере показан цикл foreach, который создает задания потоков 1000, чтобы выполнить простую запись в строку.</span><span class="sxs-lookup"><span data-stu-id="56363-185">The first example above shows a foreach loop that creates 1000 thread jobs to do a simple string write.</span></span> <span data-ttu-id="56363-186">Из-за накладных расходов на задание выполнение займет более 33 секунд.</span><span class="sxs-lookup"><span data-stu-id="56363-186">Due to job overhead, it takes over 33 seconds to complete.</span></span>

<span data-ttu-id="56363-187">Во втором примере командлет выполняется `ForEach` для выполнения тех же операций 1000, и каждая строка записи выполняется последовательно без дополнительных издержек заданий.</span><span class="sxs-lookup"><span data-stu-id="56363-187">The second example runs the `ForEach` cmdlet to do the same 1000 operations and each string write is executed sequentially without any job overhead.</span></span> <span data-ttu-id="56363-188">Она завершается всего за 25 миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="56363-188">It completes in a mere 25 milliseconds.</span></span>

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

<span data-ttu-id="56363-189">В приведенном выше примере собираются до 5000 записей для 10 отдельных системных журналов.</span><span class="sxs-lookup"><span data-stu-id="56363-189">In the above example, up to 5000 entries are collected for 10 separate system logs.</span></span> <span data-ttu-id="56363-190">Поскольку сценарий включает чтение нескольких журналов, имеет смысл выполнять операции параллельно.</span><span class="sxs-lookup"><span data-stu-id="56363-190">Since the script involves reading a number of logs, it makes sense to do the operations in parallel.</span></span> <span data-ttu-id="56363-191">И выполнение задания выполняется в два раза быстрее, как если бы сценарий выполнялся последовательно.</span><span class="sxs-lookup"><span data-stu-id="56363-191">And the job completes over twice as fast as when the script is run sequentially.</span></span>

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

## <a name="thread-jobs-and-variables"></a><span data-ttu-id="56363-192">Задания и переменные потоков</span><span class="sxs-lookup"><span data-stu-id="56363-192">Thread jobs and variables</span></span>

<span data-ttu-id="56363-193">Переменные передаются в задания потоков различными способами.</span><span class="sxs-lookup"><span data-stu-id="56363-193">Variables are passed into thread jobs in various ways.</span></span>

<span data-ttu-id="56363-194">`Start-ThreadJob` может принимать переменные, передаваемые в командлет, переданные в блок скрипта через `$using` ключевое слово или передаваемые через параметр **ArgumentList** .</span><span class="sxs-lookup"><span data-stu-id="56363-194">`Start-ThreadJob` can accept variables that are piped to the cmdlet, passed in to the script block via the `$using` keyword, or passed in via the **ArgumentList** parameter.</span></span>

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

<span data-ttu-id="56363-195">Так как задания потоков выполняются в одном процессе, любой ссылочный тип переменной, переданный в задание, должен обрабатываться аккуратно.</span><span class="sxs-lookup"><span data-stu-id="56363-195">Since thread jobs run in the same process, any variable reference type passed into the job has to be treated carefully.</span></span> <span data-ttu-id="56363-196">Если он не является потокобезопасным объектом, ему никогда не следует присваивать значение, а метод и свойства никогда не должны вызываться для него.</span><span class="sxs-lookup"><span data-stu-id="56363-196">If it is not a thread safe object, then it should never be assigned to, and method and properties should never be invoked on it.</span></span>

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

<span data-ttu-id="56363-197">В приведенном выше примере объект dotNet, являющийся потокобезопасным, передается `ConcurrentDictionary` всем дочерним заданиям для получения объектов процессов с уникальными именами.</span><span class="sxs-lookup"><span data-stu-id="56363-197">The above example passes a thread safe dotNet `ConcurrentDictionary` object to all child jobs to collect uniquely named process objects.</span></span> <span data-ttu-id="56363-198">Поскольку это потокобезопасный объект, его можно безопасно использовать во время параллельного выполнения заданий в процессе.</span><span class="sxs-lookup"><span data-stu-id="56363-198">Since it is a thread safe object, it can be safely used while the jobs run concurrently in the process.</span></span>

## <a name="see-also"></a><span data-ttu-id="56363-199">См. также статью</span><span class="sxs-lookup"><span data-stu-id="56363-199">See also</span></span>

- [<span data-ttu-id="56363-200">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="56363-200">about_Remote_Jobs</span></span>](about_Remote_Jobs.md)
- [<span data-ttu-id="56363-201">about_Thread_Jobs</span><span class="sxs-lookup"><span data-stu-id="56363-201">about_Thread_Jobs</span></span>](about_Thread_Jobs.md)
- [<span data-ttu-id="56363-202">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="56363-202">about_Job_Details</span></span>](about_Job_Details.md)
- [<span data-ttu-id="56363-203">about_Remote</span><span class="sxs-lookup"><span data-stu-id="56363-203">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="56363-204">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="56363-204">about_PSSessions</span></span>](about_PSSessions.md)
- [<span data-ttu-id="56363-205">Start-Job</span><span class="sxs-lookup"><span data-stu-id="56363-205">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="56363-206">Get-Job.</span><span class="sxs-lookup"><span data-stu-id="56363-206">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="56363-207">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="56363-207">Receive-Job</span></span>](xref:Microsoft.PowerShell.Core.Receive-Job)
- [<span data-ttu-id="56363-208">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="56363-208">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="56363-209">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="56363-209">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="56363-210">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="56363-210">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
