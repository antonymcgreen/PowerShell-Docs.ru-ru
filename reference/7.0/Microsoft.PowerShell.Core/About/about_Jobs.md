---
description: Содержит сведения о том, как фоновые задания PowerShell выполняют команду или выражение в фоновом режиме без взаимодействия с текущим сеансом.
keywords: powershell,командлет
Locale: en-US
ms.date: 10/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_jobs?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Jobs
ms.openlocfilehash: 838e142fe39260b759e9a44c6d69b80d3c5b293e
ms.sourcegitcommit: 108686b166672cc08817c637dd93eb1ad830511d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "93232981"
---
# <a name="about-jobs"></a><span data-ttu-id="1cd3a-104">О заданиях</span><span class="sxs-lookup"><span data-stu-id="1cd3a-104">About Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="1cd3a-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="1cd3a-105">Short description</span></span>
<span data-ttu-id="1cd3a-106">Содержит сведения о том, как фоновые задания PowerShell выполняют команду или выражение в фоновом режиме без взаимодействия с текущим сеансом.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-106">Provides information about how PowerShell background jobs run a command or expression in the background without interacting with the current session.</span></span>

## <a name="long-description"></a><span data-ttu-id="1cd3a-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="1cd3a-107">Long description</span></span>

<span data-ttu-id="1cd3a-108">PowerShell параллельно выполняет команды и скрипты с помощью заданий.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-108">PowerShell concurrently runs commands and script through jobs.</span></span> <span data-ttu-id="1cd3a-109">Существует три решения на основе заданий, предоставляемые PowerShell для поддержки параллелизма.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-109">There are three jobs-based solutions provided by PowerShell to support concurrency.</span></span>

|<span data-ttu-id="1cd3a-110">Задание</span><span class="sxs-lookup"><span data-stu-id="1cd3a-110">Job</span></span>            |<span data-ttu-id="1cd3a-111">Описание</span><span class="sxs-lookup"><span data-stu-id="1cd3a-111">Description</span></span>                                                  |
|---------------|-------------------------------------------------------------|
|`RemoteJob`    |<span data-ttu-id="1cd3a-112">Команда и сценарий выполняются на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-112">Command and script run on a remote computer.</span></span>                 |
|`BackgroundJob`|<span data-ttu-id="1cd3a-113">Команда и сценарий выполняются в отдельном процессе в локальной системе</span><span class="sxs-lookup"><span data-stu-id="1cd3a-113">Command and script run in a separate process on the local</span></span>    |
|               |<span data-ttu-id="1cd3a-114">машине.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-114">machine.</span></span>                                                     |
|`ThreadJob`    |<span data-ttu-id="1cd3a-115">Команда и сценарий выполняются в отдельном потоке в том же</span><span class="sxs-lookup"><span data-stu-id="1cd3a-115">Command and script run in a separate thread within the same</span></span>  |
|               |<span data-ttu-id="1cd3a-116">процесс на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-116">process on the local machine.</span></span>                                |

<span data-ttu-id="1cd3a-117">Каждый тип задания имеет свои преимущества и недостатки.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-117">Each type of job has benefits and drawbacks.</span></span> <span data-ttu-id="1cd3a-118">Удаленное выполнение сценария на отдельном компьютере или в отдельном процессе имеет большую изоляцию.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-118">Running script remotely on a separate machine or in a separate process has great isolation.</span></span> <span data-ttu-id="1cd3a-119">Любые ошибки не влияют на другие выполняющиеся задания или на клиент, запустивший задание.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-119">Any errors won't affect other running jobs or the client that started the job.</span></span> <span data-ttu-id="1cd3a-120">Но на уровне удаленного взаимодействия добавляются дополнительные издержки, включая сериализацию объектов.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-120">But the remoting layer adds overhead, including object serialization.</span></span> <span data-ttu-id="1cd3a-121">Все объекты, передаваемые в удаленный сеанс и из него, должны быть сериализованы и десериализованы при передаче между клиентом и целевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-121">All objects passed to and from the remote session must be serialized and then deserialized as it passes between the client and the target session.</span></span> <span data-ttu-id="1cd3a-122">Операция сериализации может использовать много ресурсов вычислений и памяти для больших сложных объектов данных.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-122">The serialization operation can use many compute and memory resources for large complex data objects.</span></span>

<span data-ttu-id="1cd3a-123">В этом разделе объясняется, как выполнять фоновые задания в PowerShell на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-123">This topic explains how to run background jobs in PowerShell on a local computer.</span></span> <span data-ttu-id="1cd3a-124">Сведения о выполнении фоновых заданий на удаленных компьютерах см. в разделе [about_Remote_Jobs](about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="1cd3a-124">For information about running background jobs on remote computers, see [about_Remote_Jobs](about_Remote_Jobs.md).</span></span> <span data-ttu-id="1cd3a-125">Дополнительные сведения о заданиях потоков см. в разделе [about_Thread_Jobs](about_Thread_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="1cd3a-125">For more information about thread jobs, see [about_Thread_Jobs](about_Thread_Jobs.md).</span></span>

<span data-ttu-id="1cd3a-126">Когда вы запускаете фоновое задание, Командная строка возвращается немедленно, даже если выполнение задания занимает длительное время.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-126">When you start a background job, the command prompt returns immediately, even if the job takes an extended time to complete.</span></span> <span data-ttu-id="1cd3a-127">Пока задание выполняется, можно продолжать работу с данным сеансом.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-127">You can continue to work in the session without interruption while the job runs.</span></span>

## <a name="the-job-cmdlets"></a><span data-ttu-id="1cd3a-128">Командлеты задания</span><span class="sxs-lookup"><span data-stu-id="1cd3a-128">The job cmdlets</span></span>

|<span data-ttu-id="1cd3a-129">Командлет</span><span class="sxs-lookup"><span data-stu-id="1cd3a-129">Cmdlet</span></span>          |<span data-ttu-id="1cd3a-130">Описание</span><span class="sxs-lookup"><span data-stu-id="1cd3a-130">Description</span></span>                                            |
|----------------|-------------------------------------------------------|
|`Start-Job`     |<span data-ttu-id="1cd3a-131">Запускает фоновое задание на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-131">Starts a background job on a local computer.</span></span>           |
|`Get-Job`       |<span data-ttu-id="1cd3a-132">Возвращает фоновые задания, запущенные в</span><span class="sxs-lookup"><span data-stu-id="1cd3a-132">Gets the background jobs that were started in the</span></span>      |
|                |<span data-ttu-id="1cd3a-133">текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-133">current session.</span></span>                                       |
|`Receive-Job`   |<span data-ttu-id="1cd3a-134">Возвращает результаты фоновых заданий.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-134">Gets the results of background jobs.</span></span>                   |
|`Stop-Job`      |<span data-ttu-id="1cd3a-135">Останавливает фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-135">Stops a background job.</span></span>                                |
|`Wait-Job`      |<span data-ttu-id="1cd3a-136">Подавляет командную строку до тех пор, пока одно или все задания не будут</span><span class="sxs-lookup"><span data-stu-id="1cd3a-136">Suppresses the command prompt until one or all jobs are</span></span>|
|                |<span data-ttu-id="1cd3a-137">завершения.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-137">complete.</span></span>                                              |
|`Remove-Job`    |<span data-ttu-id="1cd3a-138">Удаляет фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-138">Deletes a background job.</span></span>                              |
|`Invoke-Command`|<span data-ttu-id="1cd3a-139">Параметр **AsJob** создает фоновое задание на</span><span class="sxs-lookup"><span data-stu-id="1cd3a-139">The **AsJob** parameter creates a background job on a</span></span>  |
|                |<span data-ttu-id="1cd3a-140">удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-140">remote computer.</span></span> <span data-ttu-id="1cd3a-141">Можно использовать `Invoke-Command` для запуска</span><span class="sxs-lookup"><span data-stu-id="1cd3a-141">You can use `Invoke-Command` to run</span></span>   |
|                |<span data-ttu-id="1cd3a-142">Любая команда задания удаленно, включая `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="1cd3a-142">any job command remotely, including `Start-Job`.</span></span>       |

## <a name="how-to-start-a-job-on-the-local-computer"></a><span data-ttu-id="1cd3a-143">Запуск задания на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="1cd3a-143">How to start a job on the local computer</span></span>

<span data-ttu-id="1cd3a-144">Чтобы запустить фоновое задание на локальном компьютере, используйте `Start-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-144">To start a background job on the local computer, use the `Start-Job` cmdlet.</span></span>

<span data-ttu-id="1cd3a-145">Чтобы написать `Start-Job` команду, заключите команду, которая выполняется заданием, в фигурные скобки ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="1cd3a-145">To write a `Start-Job` command, enclose the command that the job runs in curly braces (`{}`).</span></span> <span data-ttu-id="1cd3a-146">Используйте параметр **ScriptBlock** для указания команды.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-146">Use the **ScriptBlock** parameter to specify the command.</span></span>

<span data-ttu-id="1cd3a-147">Следующая команда запускает фоновое задание, которое выполняет `Get-Process` команду на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-147">The following command starts a background job that runs a `Get-Process` command on the local computer.</span></span>

```powershell
Start-Job -ScriptBlock {Get-Process}
```

<span data-ttu-id="1cd3a-148">`Start-Job`Команда возвращает объект, представляющий задание.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-148">The `Start-Job` command returns an object that represents the job.</span></span> <span data-ttu-id="1cd3a-149">Объект задания содержит полезную информацию о задании, но не содержит результатов его выполнения.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-149">The job object contains useful information about the job, but it does not contain the job results.</span></span>

<span data-ttu-id="1cd3a-150">Сохраните объект задания в переменной, а затем используйте его вместе с другими командлетами задания для управления фоновыми заданиями.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-150">Save the job object in a variable, and then use it with the other Job cmdlets to manage the background job.</span></span> <span data-ttu-id="1cd3a-151">Следующая команда запускает объект задания и сохраняет результирующий объект задания в `$job` переменной.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-151">The following command starts a job object and saves the resulting job object in the `$job` variable.</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Process}
```

<span data-ttu-id="1cd3a-152">Начиная с PowerShell 6,0 можно использовать амерсанд ( `&` ) в конце конвейера для запуска фонового задания.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-152">Beginning in PowerShell 6.0, you can use an amersand (`&`) at the end of a pipeline to start a background job.</span></span> <span data-ttu-id="1cd3a-153">Следующая команда функционально эквивалентна команде выше.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-153">The following command is functionally equivalent to the command above.</span></span>

```powershell
$job = Get-Process &
```

<span data-ttu-id="1cd3a-154">Амперсанд ( `&` ) называется оператором фона.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-154">The ampersand (`&`) is called the background operator.</span></span> <span data-ttu-id="1cd3a-155">Дополнительные сведения см. в разделе [оператор Background](about_Operators.md#background-operator-).</span><span class="sxs-lookup"><span data-stu-id="1cd3a-155">For more information, see [background operator](about_Operators.md#background-operator-).</span></span>

<span data-ttu-id="1cd3a-156">Можно также использовать `Get-Job` командлет для получения объектов, представляющих задания, запущенные в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-156">You can also use the `Get-Job` cmdlet to get objects that represent the jobs started in the current session.</span></span> <span data-ttu-id="1cd3a-157">`Get-Job` возвращает тот же объект задания, который `Start-Job` возвращает.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-157">`Get-Job` returns the same job object that `Start-Job` returns.</span></span>

## <a name="getting-job-objects"></a><span data-ttu-id="1cd3a-158">Получение объектов заданий</span><span class="sxs-lookup"><span data-stu-id="1cd3a-158">Getting job objects</span></span>

<span data-ttu-id="1cd3a-159">Чтобы получить объект, который представляет фоновые задания, запущенные в текущем сеансе, используйте `Get-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-159">To get object that represent the background jobs that were started in the current session, use the `Get-Job` cmdlet.</span></span> <span data-ttu-id="1cd3a-160">Без параметров `Get-Job` возвращает все задания, запущенные в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-160">Without parameters, `Get-Job` returns all of the jobs that were started in the current session.</span></span>

<span data-ttu-id="1cd3a-161">Например, следующая команда возвращает задания в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-161">For example, the following command gets the jobs in the current session.</span></span>

```powershell
PS C:> Get-Job

Id  Name  PSJobTypeName State      HasMoreData  Location   Command
--  ----  ------------- -----      -----------  --------   -------
1   Job1  BackgroundJob Running    True         localhost  Get-Process
```

<span data-ttu-id="1cd3a-162">Можно также сохранить объект задания в переменной и использовать его для представления задания в более поздней команде.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-162">You can also save the job object in a variable and use it to represent the job in a later command.</span></span> <span data-ttu-id="1cd3a-163">Следующая команда возвращает задание с ИДЕНТИФИКАТОРом 1 и сохраняет его в `$job` переменной.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-163">The following command gets the job with ID 1 and saves it in the `$job` variable.</span></span>

```powershell
$job = Get-Job -Id 1
```

<span data-ttu-id="1cd3a-164">Объект задания содержит состояние задания, которое указывает, завершено ли задание.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-164">The job object contains the state of the job, which indicates whether the job has finished.</span></span> <span data-ttu-id="1cd3a-165">Завершенное задание имеет состояние " **завершено** " или " **сбой** ".</span><span class="sxs-lookup"><span data-stu-id="1cd3a-165">A finished job has a state of **Complete** or **Failed** .</span></span> <span data-ttu-id="1cd3a-166">Задание также может быть **заблокировано** или **заработано** .</span><span class="sxs-lookup"><span data-stu-id="1cd3a-166">A job might also be **blocked** or **running** .</span></span>

```powershell
Get-Job

Id  Name  PSJobTypeName State      HasMoreData  Location   Command
--  ----  ------------- -----      -----------  --------   -------
1   Job1  BackgroundJob Complete   True         localhost  Get-Process
```

## <a name="getting-the-results-of-a-job"></a><span data-ttu-id="1cd3a-167">Получение результатов задания</span><span class="sxs-lookup"><span data-stu-id="1cd3a-167">Getting the results of a job</span></span>

<span data-ttu-id="1cd3a-168">При выполнении фонового задания результаты не отображаются немедленно.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-168">When you run a background job, the results do not appear immediately.</span></span> <span data-ttu-id="1cd3a-169">Вместо этого `Start-Job` командлет возвращает объект задания, который представляет задание, но не содержит результаты.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-169">Instead, the `Start-Job` cmdlet returns a job object that represents the job, but it does not contain the results.</span></span> <span data-ttu-id="1cd3a-170">Чтобы получить результаты фонового задания, используйте `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-170">To get the results of a background job, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="1cd3a-171">Следующая команда использует `Receive-Job` командлет для получения результатов задания.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-171">The following command uses the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="1cd3a-172">Для обнаружения задания используется объект задания, сохраненный в `$job` переменной.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-172">It uses a job object saved in the `$job` variable to identify the job.</span></span>

```powershell
Receive-Job -Job $job
```

<span data-ttu-id="1cd3a-173">`Receive-Job`Командлет возвращает результаты задания.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-173">The `Receive-Job` cmdlet returns the results of the job.</span></span>

```
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)    Id ProcessName
-------  ------    -----      ----- -----   ------    -- -----------
    103       4    11328       9692    56           1176 audiodg
    804      14    12228      14108   100   101.74  1740 CcmExec
    668       7     2672       6168   104    32.26   488 csrss
# ...
```

<span data-ttu-id="1cd3a-174">Результаты задания также можно сохранить в переменной.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-174">You can also save the results of a job in a variable.</span></span> <span data-ttu-id="1cd3a-175">Следующая команда сохраняет результаты задания в `$job` переменной в `$results` переменной.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-175">The following command saves the results of the job in the `$job` variable to the `$results` variable.</span></span>

```powershell
$results = Receive-Job -Job $job
```

<span data-ttu-id="1cd3a-176">Кроме того, результаты задания можно сохранить в файле с помощью оператора перенаправления ( `>` ) или `Out-File` командлета.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-176">And, you can save the results of the job in a file by using the redirection operator (`>`) or the `Out-File` cmdlet.</span></span> <span data-ttu-id="1cd3a-177">Следующая команда использует оператор перенаправления для сохранения результатов задания в `$job` переменной в `Results.txt` файле.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-177">The following command uses the redirection operator to save the results of the job in the `$job` variable in the `Results.txt` file.</span></span>

```powershell
Receive-Job -Job $job > results.txt
```

## <a name="getting-and-keeping-partial-job-results"></a><span data-ttu-id="1cd3a-178">Получение и хранение результатов частичной работы</span><span class="sxs-lookup"><span data-stu-id="1cd3a-178">Getting and keeping partial job results</span></span>

<span data-ttu-id="1cd3a-179">`Receive-Job`Командлет возвращает результаты фонового задания.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-179">The `Receive-Job` cmdlet gets the results of a background job.</span></span> <span data-ttu-id="1cd3a-180">Если задание завершено, `Receive-Job` получает результаты всех заданий.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-180">If the job is complete, `Receive-Job` gets all job results.</span></span> <span data-ttu-id="1cd3a-181">Если задание по-прежнему выполняется, `Receive-Job` получает результаты, которые были созданы до сих пор.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-181">If the job is still running, `Receive-Job` gets the results that have been generated thus far.</span></span> <span data-ttu-id="1cd3a-182">`Receive-Job`Чтобы получить оставшиеся результаты, можно выполнить команды еще раз.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-182">You can run `Receive-Job` commands again to get the remaining results.</span></span>

<span data-ttu-id="1cd3a-183">Если `Receive-Job` возвращает результаты, по умолчанию он удаляет результаты из кэша, в котором хранятся результаты задания.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-183">When `Receive-Job` returns results, by default, it deletes those results from the cache where job results are stored.</span></span> <span data-ttu-id="1cd3a-184">Если выполнить другую `Receive-Job` команду, вы получите только те результаты, которые еще не были получены.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-184">If you run another `Receive-Job` command, you get only the results that are not yet received.</span></span>

<span data-ttu-id="1cd3a-185">Следующие команды показывают результаты `Receive-Job` выполнения команд до завершения задания.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-185">The following commands show the results of `Receive-Job` commands run before the job is complete.</span></span>

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

<span data-ttu-id="1cd3a-186">Чтобы предотвратить `Receive-Job` Удаление возвращаемых результатов задания, используйте параметр **держитесь** .</span><span class="sxs-lookup"><span data-stu-id="1cd3a-186">To prevent `Receive-Job` from deleting the job results that it has returned, use the **Keep** parameter.</span></span> <span data-ttu-id="1cd3a-187">В результате `Receive-Job` возвращает все результаты, которые были созданы до этого времени.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-187">As a result, `Receive-Job` returns all of the results that have been generated until that time.</span></span>

<span data-ttu-id="1cd3a-188">Приведенные ниже команды демонстрируют последствия использования параметра **сохранения** для задания, которое еще не завершено.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-188">The following commands show the effect of using the **Keep** parameter on a job that is not yet complete.</span></span>

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

## <a name="waiting-for-the-results"></a><span data-ttu-id="1cd3a-189">Ожидание результатов</span><span class="sxs-lookup"><span data-stu-id="1cd3a-189">Waiting for the results</span></span>

<span data-ttu-id="1cd3a-190">При выполнении команды, выполнение которой занимает много времени, можно использовать свойства объекта задания, чтобы определить, когда задание завершено.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-190">If you run a command that takes a long time to complete, you can use the properties of the job object to determine when the job is complete.</span></span> <span data-ttu-id="1cd3a-191">Следующая команда использует `Get-Job` объект для получения всех фоновых заданий в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-191">The following command uses the `Get-Job` object to get all of the background jobs in the current session.</span></span>

```powershell
Get-Job
```

<span data-ttu-id="1cd3a-192">Результаты отображаются в таблице.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-192">The results appear in a table.</span></span> <span data-ttu-id="1cd3a-193">Состояние задания отображается в столбце **состояние** .</span><span class="sxs-lookup"><span data-stu-id="1cd3a-193">The status of the job appears in the **State** column.</span></span>

```
Id Name  PSJobTypeName State    HasMoreData Location  Command
-- ----  ------------- -----    ----------- --------  -------
1  Job1  BackgroundJob Complete True        localhost Get-Process
2  Job2  BackgroundJob Running  True        localhost Get-EventLog -Log ...
3  Job3  BackgroundJob Complete True        localhost dir -Path C:\* -Re...
```

<span data-ttu-id="1cd3a-194">В этом случае свойство State показывает, что задание 2 все еще выполняется.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-194">In this case, the State property reveals that Job 2 is still running.</span></span> <span data-ttu-id="1cd3a-195">Если вы использовали `Receive-Job` командлет для получения результатов задания прямо сейчас, результаты будут неполными.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-195">If you were to use the `Receive-Job` cmdlet to get the job results now, the results would be incomplete.</span></span> <span data-ttu-id="1cd3a-196">Можно `Receive-Job` многократно использовать командлет для получения всех результатов.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-196">You can use the `Receive-Job` cmdlet repeatedly to get all of the results.</span></span> <span data-ttu-id="1cd3a-197">По умолчанию при каждом использовании вы получаете только те результаты, которые еще не были получены, но можно использовать параметр **сохранения** `Receive-Job` командлета для сохранения результатов, даже если они уже были получены.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-197">By default, each time you use it, you get only the results that were not already received, but you can use the **Keep** parameter of the `Receive-Job` cmdlet to retain the results, even though they were already received.</span></span>

<span data-ttu-id="1cd3a-198">Можно записать частичные результаты в файл, а затем добавить новые результаты по мере их поступления или же подождать и проверить состояние задания позже.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-198">You can write the partial results to a file and then append newer results as they arrive or you can wait and check the state of the job later.</span></span>

<span data-ttu-id="1cd3a-199">Можно использовать параметр **Wait** `Receive-Job` командлета, который не возвращает командную строку, пока задание не будет завершено и все результаты будут доступны.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-199">You can use the **Wait** parameter of the `Receive-Job` cmdlet, which does not return the command prompt until the job is complete and all results are available.</span></span>

<span data-ttu-id="1cd3a-200">Можно также использовать `Wait-Job` командлет для ожидания любого или всех результатов задания.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-200">You can also use the `Wait-Job` cmdlet to wait for any or all of the results of the job.</span></span> <span data-ttu-id="1cd3a-201">`Wait-Job` позволяет ожидать определенного задания, для всех заданий или для выполнения всех заданий.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-201">`Wait-Job` lets you wait for a particular job, for all jobs, or for any of the jobs to be completed.</span></span>

<span data-ttu-id="1cd3a-202">Следующая команда использует `Wait-Job` командлет для ожидания задания с **идентификатором** .</span><span class="sxs-lookup"><span data-stu-id="1cd3a-202">The following command uses the `Wait-Job` cmdlet to wait for a job with **ID**</span></span>
10.

```powershell
Wait-Job -ID 10
```

<span data-ttu-id="1cd3a-203">В результате Командная строка PowerShell подавляется до завершения задания.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-203">As a result, the PowerShell prompt is suppressed until the job is completed.</span></span>

<span data-ttu-id="1cd3a-204">Можно также дождаться заранее определенного периода времени.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-204">You can also wait for a predetermined period of time.</span></span> <span data-ttu-id="1cd3a-205">Эта команда использует параметр **timeout** , чтобы ограничить время ожидания 120 секунд.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-205">This command uses the **Timeout** parameter to limit the wait to 120 seconds.</span></span> <span data-ttu-id="1cd3a-206">По истечении этого времени Командная строка возвращает значение, но задание продолжит выполняться в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-206">When the time expires, the command prompt returns, but the job continues to run in the background.</span></span>

```powershell
Wait-Job -ID 10 -Timeout 120
```

## <a name="stopping-a-job"></a><span data-ttu-id="1cd3a-207">Остановка задания</span><span class="sxs-lookup"><span data-stu-id="1cd3a-207">Stopping a job</span></span>

<span data-ttu-id="1cd3a-208">Чтобы прерывать фоновое задание, используйте `Stop-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-208">To stop a background job, use the `Stop-Job` cmdlet.</span></span> <span data-ttu-id="1cd3a-209">Следующая команда запускает задание для получения каждой записи в журнале системных событий.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-209">The following command starts a job to get every entry in the System event log.</span></span> <span data-ttu-id="1cd3a-210">Объект задания сохраняется в `$job` переменной.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-210">It saves the job object in the `$job` variable.</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-EventLog -Log System}
```

<span data-ttu-id="1cd3a-211">Следующая команда останавливает задание.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-211">The following command stops the job.</span></span> <span data-ttu-id="1cd3a-212">Он использует оператор конвейера ( `|` ) для отправки задания в переменной в `$job` `Stop-Job` .</span><span class="sxs-lookup"><span data-stu-id="1cd3a-212">It uses a pipeline operator (`|`) to send the job in the `$job` variable to `Stop-Job`.</span></span>

```powershell
$job | Stop-Job
```

## <a name="deleting-a-job"></a><span data-ttu-id="1cd3a-213">Удаление задания</span><span class="sxs-lookup"><span data-stu-id="1cd3a-213">Deleting a job</span></span>

<span data-ttu-id="1cd3a-214">Чтобы удалить фоновое задание, используйте `Remove-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-214">To delete a background job, use the `Remove-Job` cmdlet.</span></span> <span data-ttu-id="1cd3a-215">Следующая команда удаляет задание в `$job` переменной.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-215">The following command deletes the job in the `$job` variable.</span></span>

```powershell
Remove-Job -Job $job
```

## <a name="investigating-a-failed-job"></a><span data-ttu-id="1cd3a-216">Исследование невыполненного задания</span><span class="sxs-lookup"><span data-stu-id="1cd3a-216">Investigating a failed job</span></span>

<span data-ttu-id="1cd3a-217">Чтобы узнать, почему не удалось выполнить задание, используйте свойство **Reason** объекта Job.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-217">To find out why a job failed, use the **Reason** property of the job object.</span></span>

<span data-ttu-id="1cd3a-218">Следующая команда запускает задание без требуемых учетных данных.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-218">The following command starts a job without the required credentials.</span></span> <span data-ttu-id="1cd3a-219">Объект задания сохраняется в `$job` переменной.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-219">It saves the job object in the `$job` variable.</span></span>

```powershell
$job = Start-Job -ScriptBlock {New-Item -Path HKLM:\Software\MyCompany}

Id Name  PSJobTypeName State  HasMoreData  Location  Command
-- ----  ------------- -----  -----------  --------  -------
1  Job1  BackgroundJob Failed False        localhost New-Item -Path HKLM:...
```

<span data-ttu-id="1cd3a-220">Следующая команда использует свойство Reason для поиска ошибки, вызвавшей сбой задания.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-220">The following command uses the Reason property to find the error that caused the job to fail.</span></span>

```powershell
$job.ChildJobs[0].JobStateInfo.Reason
```

<span data-ttu-id="1cd3a-221">В этом случае задание завершилось сбоем, так как удаленный компьютер требует явных учетных данных для выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-221">In this case, the job failed because the remote computer required explicit credentials to run the command.</span></span> <span data-ttu-id="1cd3a-222">Значение свойства **Reason** :</span><span class="sxs-lookup"><span data-stu-id="1cd3a-222">The value of the **Reason** property is:</span></span>

<span data-ttu-id="1cd3a-223">Сбой подключения к удаленному серверу со следующим сообщением об ошибке: "отказано в доступе".</span><span class="sxs-lookup"><span data-stu-id="1cd3a-223">Connecting to remote server failed with the following error message: "Access is denied".</span></span>

## <a name="see-also"></a><span data-ttu-id="1cd3a-224">См. также статью</span><span class="sxs-lookup"><span data-stu-id="1cd3a-224">See also</span></span>

- [<span data-ttu-id="1cd3a-225">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="1cd3a-225">about_Remote_Jobs</span></span>](about_Remote_Jobs.md)
- [<span data-ttu-id="1cd3a-226">about_Thread_Jobs</span><span class="sxs-lookup"><span data-stu-id="1cd3a-226">about_Thread_Jobs</span></span>](about_Thread_Jobs.md)
- [<span data-ttu-id="1cd3a-227">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="1cd3a-227">about_Job_Details</span></span>](about_Job_Details.md)
- [<span data-ttu-id="1cd3a-228">about_Remote</span><span class="sxs-lookup"><span data-stu-id="1cd3a-228">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="1cd3a-229">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="1cd3a-229">about_PSSessions</span></span>](about_PSSessions.md)
- [<span data-ttu-id="1cd3a-230">Start-Job</span><span class="sxs-lookup"><span data-stu-id="1cd3a-230">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="1cd3a-231">Get-Job.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-231">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="1cd3a-232">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-232">Receive-Job</span></span>](xref:Microsoft.PowerShell.Core.Receive-Job)
- [<span data-ttu-id="1cd3a-233">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="1cd3a-233">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="1cd3a-234">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="1cd3a-234">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="1cd3a-235">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="1cd3a-235">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
- [<span data-ttu-id="1cd3a-236">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="1cd3a-236">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)