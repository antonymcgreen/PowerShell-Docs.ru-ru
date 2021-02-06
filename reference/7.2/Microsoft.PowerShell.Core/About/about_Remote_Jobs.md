---
description: Описание выполнения заданий на удаленных компьютерах.
Locale: en-US
ms.date: 11/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_jobs?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Jobs
ms.openlocfilehash: 93e1d3aba1f4037cc3c5c18386488bf321fc2a64
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605033"
---
# <a name="about-remote-jobs"></a><span data-ttu-id="a8241-103">Об удаленных заданиях</span><span class="sxs-lookup"><span data-stu-id="a8241-103">About Remote Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="a8241-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="a8241-104">Short Description</span></span>
<span data-ttu-id="a8241-105">Описывает, как выполнять фоновые задания на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="a8241-105">Describes how to run background jobs on remote computers.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="a8241-106">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="a8241-106">Detailed Description</span></span>

<span data-ttu-id="a8241-107">PowerShell параллельно выполняет команды и скрипты с помощью заданий.</span><span class="sxs-lookup"><span data-stu-id="a8241-107">PowerShell concurrently runs commands and scripts through jobs.</span></span> <span data-ttu-id="a8241-108">Существует три типа заданий, предоставляемых PowerShell для поддержки параллелизма.</span><span class="sxs-lookup"><span data-stu-id="a8241-108">There are three jobs types provided by PowerShell to support concurrency.</span></span>

- <span data-ttu-id="a8241-109">`RemoteJob` — Команды и скрипты выполняются в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="a8241-109">`RemoteJob` - Commands and scripts run in a remote session.</span></span>
- <span data-ttu-id="a8241-110">`BackgroundJob` — Команды и скрипты выполняются в отдельном процессе на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a8241-110">`BackgroundJob` - Commands and scripts run in a separate process on the local machine.</span></span> <span data-ttu-id="a8241-111">См. дополнительные сведения о [заданиях](about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="a8241-111">For more information, see [about_Jobs](about_Jobs.md).</span></span>
- <span data-ttu-id="a8241-112">`PSTaskJob` или `ThreadJob` — команды и скрипты выполняются в отдельном потоке в том же процессе на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a8241-112">`PSTaskJob` or `ThreadJob` - Commands and scripts run in a separate thread within the same process on the local machine.</span></span> <span data-ttu-id="a8241-113">Дополнительные сведения см. в разделе [about_Thread_Jobs](/powershell/module/ThreadJob/about_Thread_Jobs).</span><span class="sxs-lookup"><span data-stu-id="a8241-113">For more information, see [about_Thread_Jobs](/powershell/module/ThreadJob/about_Thread_Jobs).</span></span>

<span data-ttu-id="a8241-114">Удаленное выполнение сценариев на отдельном компьютере или в отдельном процессе обеспечивает высокую изоляцию.</span><span class="sxs-lookup"><span data-stu-id="a8241-114">Running scripts remotely, on a separate machine or in a separate process, provide great isolation.</span></span> <span data-ttu-id="a8241-115">Любые ошибки, возникающие в удаленном задании, не влияют на другие выполняющиеся задания или родительский сеанс, запускающий задание.</span><span class="sxs-lookup"><span data-stu-id="a8241-115">Any errors that occur in the remote job do not affect other running jobs or the parent session that started the job.</span></span> <span data-ttu-id="a8241-116">Однако на уровне удаленного взаимодействия добавляются дополнительные издержки, в том числе сериализация объектов.</span><span class="sxs-lookup"><span data-stu-id="a8241-116">However, the remoting layer adds overhead, including object serialization.</span></span> <span data-ttu-id="a8241-117">Все объекты сериализуются и десериализуются, так как они передаются между родительским сеансом и удаленным сеансом (Job).</span><span class="sxs-lookup"><span data-stu-id="a8241-117">All objects are serialized and deserialized as they are passed between the parent session and the remote (job) session.</span></span> <span data-ttu-id="a8241-118">Сериализация больших сложных объектов данных может потреблять большие объемы ресурсов вычислений и памяти и передавать большие объемы данных по сети.</span><span class="sxs-lookup"><span data-stu-id="a8241-118">Serialization of large complex data objects can consume large amounts of compute and memory resources and transfer large amounts of data across the network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8241-119">Родительский сеанс, создавший задание, также отслеживает состояние задания и собирает данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="a8241-119">The parent session that created the job also monitors the job status and collects pipeline data.</span></span> <span data-ttu-id="a8241-120">Дочерний процесс задания завершается родительским процессом после того, как задание достигнет завершенного состояния.</span><span class="sxs-lookup"><span data-stu-id="a8241-120">The job child process is terminated by the parent process once the job reaches a finished state.</span></span> <span data-ttu-id="a8241-121">Если родительский сеанс завершается, все выполняющиеся дочерние задания завершаются вместе с их дочерними процессами.</span><span class="sxs-lookup"><span data-stu-id="a8241-121">If the parent session is terminated, all running child jobs are terminated along with their child processes.</span></span>

<span data-ttu-id="a8241-122">Существует два способа обойти эту ситуацию.</span><span class="sxs-lookup"><span data-stu-id="a8241-122">There are two ways work around this situation:</span></span>

1. <span data-ttu-id="a8241-123">Используйте `Invoke-Command` для создания заданий, выполняемых в отключенных сеансах.</span><span class="sxs-lookup"><span data-stu-id="a8241-123">Use `Invoke-Command` to create jobs that run in disconnected sessions.</span></span> <span data-ttu-id="a8241-124">См. раздел « [отсоединенные процессы](#how-to-run-as-a-detached-process) » этой статьи.</span><span class="sxs-lookup"><span data-stu-id="a8241-124">See the [detached processes](#how-to-run-as-a-detached-process) section of this article.</span></span>
1. <span data-ttu-id="a8241-125">Используйте `Start-Process` для создания нового процесса, а не задания.</span><span class="sxs-lookup"><span data-stu-id="a8241-125">Use `Start-Process` to create a new process rather than a job.</span></span> <span data-ttu-id="a8241-126">Дополнительные сведения см. в разделе [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).</span><span class="sxs-lookup"><span data-stu-id="a8241-126">For more information, see [Start-Process](xref:Microsoft.PowerShell.Management.Start-Process).</span></span>

## <a name="remote-jobs"></a><span data-ttu-id="a8241-127">Удаленные задания</span><span class="sxs-lookup"><span data-stu-id="a8241-127">Remote Jobs</span></span>

<span data-ttu-id="a8241-128">Задания можно запускать на удаленных компьютерах с помощью трех различных методов.</span><span class="sxs-lookup"><span data-stu-id="a8241-128">You can run jobs on remote computers by using three different methods.</span></span>

- <span data-ttu-id="a8241-129">Запуск интерактивного сеанса на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a8241-129">Start an interactive session on a remote computer.</span></span> <span data-ttu-id="a8241-130">Затем запустите задание в интерактивном сеансе.</span><span class="sxs-lookup"><span data-stu-id="a8241-130">Then start a job in the interactive session.</span></span> <span data-ttu-id="a8241-131">Процедуры совпадают с выполнением локального задания, хотя все действия выполняются на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a8241-131">The procedures are the same as running a local job, although all actions are performed on the remote computer.</span></span>

- <span data-ttu-id="a8241-132">Запуск задания на удаленном компьютере, который возвращает результаты на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="a8241-132">Run a job on a remote computer that returns its results to the local computer.</span></span> <span data-ttu-id="a8241-133">Используйте этот метод, если требуется получать результаты заданий и обслуживать их в центральном расположении на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a8241-133">Use this method when you want to collect the results of jobs and maintain them in a central location on the local computer.</span></span>

- <span data-ttu-id="a8241-134">Выполнение задания на удаленном компьютере, сохраняющем результаты на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a8241-134">Run a job on a remote computer that maintains its results on the remote computer.</span></span> <span data-ttu-id="a8241-135">Используйте этот метод, если данные задания более безопасно поддерживаются на исходном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a8241-135">Use this method when the job data is more securely maintained on the originating computer.</span></span>

### <a name="start-a-job-in-an-interactive-session"></a><span data-ttu-id="a8241-136">Запуск задания в интерактивном сеансе</span><span class="sxs-lookup"><span data-stu-id="a8241-136">Start a job in an interactive session</span></span>

<span data-ttu-id="a8241-137">Можно запустить интерактивный сеанс с удаленным компьютером, а затем запустить задание во время интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="a8241-137">You can start an interactive session with a remote computer and then start a job during the interactive session.</span></span> <span data-ttu-id="a8241-138">Дополнительные сведения о интерактивных сеансах см. в разделе about_Remote и см. в разделе `Enter-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="a8241-138">For more information about interactive sessions, see about_Remote, and see `Enter-PSSession`.</span></span>

<span data-ttu-id="a8241-139">Процедура запуска задания в интерактивном сеансе практически идентична процедуре запуска фонового задания на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a8241-139">The procedure for starting a job in an interactive session is almost identical to the procedure for starting a background job on the local computer.</span></span> <span data-ttu-id="a8241-140">Однако все операции выполняются на удаленном компьютере, а не на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a8241-140">However, all of the operations occur on the remote computer, not the local computer.</span></span>

1. <span data-ttu-id="a8241-141">Используйте `Enter-PSSession` командлет для запуска интерактивного сеанса с удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="a8241-141">Use the `Enter-PSSession` cmdlet to start an interactive session with a remote computer.</span></span> <span data-ttu-id="a8241-142">Параметр ComputerName параметра можно использовать `Enter-PSSession` для установки временного подключения к интерактивному сеансу.</span><span class="sxs-lookup"><span data-stu-id="a8241-142">You can use the ComputerName parameter of `Enter-PSSession` to establish a temporary connection for the interactive session.</span></span> <span data-ttu-id="a8241-143">Кроме того, можно использовать параметр Session для выполнения интерактивного сеанса в сеансе PowerShell (PSSession).</span><span class="sxs-lookup"><span data-stu-id="a8241-143">Or, you can use the Session parameter to run the interactive session in a PowerShell session (PSSession).</span></span>

   <span data-ttu-id="a8241-144">Следующая команда запускает интерактивный сеанс на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="a8241-144">The following command starts an interactive session on the Server01 computer.</span></span>

   ```powershell
   C:\PS> Enter-PSSession -computername Server01
   ```

   <span data-ttu-id="a8241-145">Командная строка изменится и отобразится, что теперь вы подключены к компьютеру Server01.</span><span class="sxs-lookup"><span data-stu-id="a8241-145">The command prompt changes to show that you are now connected to the Server01 computer.</span></span>

   ```
   Server01\C:>
   ```

1. <span data-ttu-id="a8241-146">Чтобы запустить удаленное задание в сеансе, используйте `Start-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="a8241-146">To start a remote job in the session, use the `Start-Job` cmdlet.</span></span> <span data-ttu-id="a8241-147">Следующая команда запускает удаленное задание, которое получает события в журнале событий Windows PowerShell на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="a8241-147">The following command runs a remote job that gets the events in the Windows PowerShell event log on the Server01 computer.</span></span> <span data-ttu-id="a8241-148">`Start-Job`Командлет возвращает объект, представляющий задание.</span><span class="sxs-lookup"><span data-stu-id="a8241-148">The `Start-Job` cmdlet returns an object that represents the job.</span></span>

   <span data-ttu-id="a8241-149">Эта команда сохраняет объект задания в `$job` переменной.</span><span class="sxs-lookup"><span data-stu-id="a8241-149">This command saves the job object in the `$job` variable.</span></span>

   ```powershell
   Server01\C:> $job = Start-Job -scriptblock {
     Get-Eventlog "Windows PowerShell"
   }
   ```

   <span data-ttu-id="a8241-150">Во время выполнения задания можно использовать интерактивный сеанс для выполнения других команд, включая другие задания.</span><span class="sxs-lookup"><span data-stu-id="a8241-150">While the job runs, you can use the interactive session to run other commands, including other jobs.</span></span> <span data-ttu-id="a8241-151">Однако интерактивный сеанс должен быть открыт до завершения задания.</span><span class="sxs-lookup"><span data-stu-id="a8241-151">However, you must keep the interactive session open until the job is completed.</span></span> <span data-ttu-id="a8241-152">Если завершить сеанс, задание будет прервано и результаты будут утеряны.</span><span class="sxs-lookup"><span data-stu-id="a8241-152">If you end the session, the job is interrupted, and the results are lost.</span></span>

1. <span data-ttu-id="a8241-153">Чтобы узнать, завершено ли задание, отобразите значение `$job` переменной или используйте `Get-Job` командлет для получения задания.</span><span class="sxs-lookup"><span data-stu-id="a8241-153">To find out if the job is complete, display the value of the `$job` variable, or use the `Get-Job` cmdlet to get the job.</span></span> <span data-ttu-id="a8241-154">Следующая команда использует `Get-Job` командлет для вывода задания.</span><span class="sxs-lookup"><span data-stu-id="a8241-154">The following command uses the `Get-Job` cmdlet to display the job.</span></span>

   ```powershell
   Server01\C:> Get-Job $job

   SessionId  Name  State      HasMoreData  Location   Command
   ---------  ----  -----      -----------  --------   -------
   1          Job1  Complete   True         localhost  Get-Eventlog "Windows...
   ```

   <span data-ttu-id="a8241-155">`Get-Job`Выходные данные показывают, что задание выполняется на компьютере "localhost", так как задание было запущено на том же компьютере (в данном случае Server01).</span><span class="sxs-lookup"><span data-stu-id="a8241-155">The `Get-Job` output shows that job is running on the "localhost" computer because the job was started on and is running on the same computer (in this case, Server01).</span></span>

1. <span data-ttu-id="a8241-156">Чтобы получить результаты задания, используйте `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="a8241-156">To get the results of the job, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="a8241-157">Результаты можно отобразить в интерактивном сеансе или сохранить в файл на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a8241-157">You can display the results in the interactive session or save them to a file on the remote computer.</span></span> <span data-ttu-id="a8241-158">Следующая команда возвращает результаты задания в переменной $job.</span><span class="sxs-lookup"><span data-stu-id="a8241-158">The following command gets the results of the job in the $job variable.</span></span> <span data-ttu-id="a8241-159">Команда использует оператор перенаправления ( `>` ) для сохранения результатов задания в файле PsLog.txt на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="a8241-159">The command uses the redirection operator (`>`) to save the results of the job in the PsLog.txt file on the Server01 computer.</span></span>

   ```powershell
   Server01\C:> Receive-Job $job > c:\logs\PsLog.txt
   ```

1. <span data-ttu-id="a8241-160">Чтобы завершить интерактивный сеанс, используйте `Exit-PSSession` командлет.</span><span class="sxs-lookup"><span data-stu-id="a8241-160">To end the interactive session, use the `Exit-PSSession` cmdlet.</span></span> <span data-ttu-id="a8241-161">Командная строка изменится, чтобы отобразить, что вы снова используете исходный сеанс на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a8241-161">The command prompt changes to show that you are back in the original session on the local computer.</span></span>

   ```powershell
   Server01\C:> Exit-PSSession
   C:\PS>
   ```

1. <span data-ttu-id="a8241-162">Чтобы просмотреть содержимое `PsLog.txt` файла на компьютере Server01 в любое время, запустите другой интерактивный сеанс или выполните удаленную команду.</span><span class="sxs-lookup"><span data-stu-id="a8241-162">To view the contents of the `PsLog.txt` file on the Server01 computer at any time, start another interactive session, or run a remote command.</span></span> <span data-ttu-id="a8241-163">Этот тип команды лучше выполнять в сеансе PSSession (постоянное подключение), если вы хотите использовать несколько команд для исследования и управления данными в `PsLog.txt` файле.</span><span class="sxs-lookup"><span data-stu-id="a8241-163">This type of command is best run in a PSSession (a persistent connection) in case you want to use several commands to investigate and manage the data in the `PsLog.txt` file.</span></span> <span data-ttu-id="a8241-164">Дополнительные сведения о PSSession см. в разделе [about_PSSessions](about_PSSessions.md).</span><span class="sxs-lookup"><span data-stu-id="a8241-164">For more information about PSSessions, see [about_PSSessions](about_PSSessions.md).</span></span>

   <span data-ttu-id="a8241-165">Следующие команды используют `New-PSSession` командлет для создания **сеанса PSSession** , подключенного к компьютеру Server01, и используют `Invoke-Command` командлет для выполнения `Get-Content` команды в PSSession для просмотра содержимого файла.</span><span class="sxs-lookup"><span data-stu-id="a8241-165">The following commands use the `New-PSSession` cmdlet to create a **PSSession** that is connected to the Server01 computer, and they use the `Invoke-Command` cmdlet to run a `Get-Content` command in the PSSession to view the contents of the file.</span></span>

   ```powershell
   $s = New-PSSession -computername Server01
   Invoke-Command -session $s -scriptblock {
     Get-Content c:\logs\pslog.txt}
   ```

### <a name="start-a-remote-job-that-returns-the-results-to-the-local-computer-asjob"></a><span data-ttu-id="a8241-166">Запуск удаленного задания, которое возвращает результаты на локальный компьютер (AsJob)</span><span class="sxs-lookup"><span data-stu-id="a8241-166">Start a remote job that returns the results to the local computer (AsJob)</span></span>

<span data-ttu-id="a8241-167">Чтобы запустить задание на удаленном компьютере, которое возвращает результаты команды на локальный компьютер, используйте параметр **AsJob** командлета, например `Invoke-Command` командлета.</span><span class="sxs-lookup"><span data-stu-id="a8241-167">To start a job on a remote computer that returns the command results to the local computer, use the **AsJob** parameter of a cmdlet such as the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="a8241-168">При использовании параметра **AsJob** объект задания на самом деле создается на локальном компьютере, даже если задание выполняется на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a8241-168">When you use the **AsJob** parameter, the job object is actually created on the local computer even though the job runs on the remote computer.</span></span> <span data-ttu-id="a8241-169">После завершения задания результаты возвращаются на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="a8241-169">When the job is completed, the results are returned to the local computer.</span></span>

<span data-ttu-id="a8241-170">Для управления любыми заданиями, созданными любым командлетом, можно использовать командлеты, содержащие существительное задания (командлеты задания).</span><span class="sxs-lookup"><span data-stu-id="a8241-170">You can use the cmdlets that contain the Job noun (the Job cmdlets) to manage any job created by any cmdlet.</span></span> <span data-ttu-id="a8241-171">Многие командлеты, имеющие параметры **AsJob** , не используют удаленное взаимодействие PowerShell, поэтому их можно использовать даже на компьютерах, которые не настроены на удаленное взаимодействие и которые не соответствуют требованиям к удаленному взаимодействию.</span><span class="sxs-lookup"><span data-stu-id="a8241-171">Many of the cmdlets that have **AsJob** parameters do not use PowerShell remoting, so you can use them even on computers that are not configured for remoting and that do not meet the requirements for remoting.</span></span>

1. <span data-ttu-id="a8241-172">Следующая команда использует параметр **AsJob** параметра `Invoke-Command` для запуска задания на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="a8241-172">The following command uses the **AsJob** parameter of `Invoke-Command` to start a job on the Server01 computer.</span></span> <span data-ttu-id="a8241-173">Задание выполняет `Get-Eventlog` команду, которая получает события в системном журнале.</span><span class="sxs-lookup"><span data-stu-id="a8241-173">The job runs a `Get-Eventlog` command that gets the events in the System log.</span></span> <span data-ttu-id="a8241-174">Вы можете использовать параметр JobName, чтобы назначить для задания отображаемое имя.</span><span class="sxs-lookup"><span data-stu-id="a8241-174">You can use the JobName parameter to assign a display name to the job.</span></span>

   ```powershell
   Invoke-Command -computername Server01 -scriptblock {
     Get-Eventlog system} -AsJob
   ```

   <span data-ttu-id="a8241-175">Результаты выполнения команды похожи на приведенный ниже образец выходных данных.</span><span class="sxs-lookup"><span data-stu-id="a8241-175">The results of the command resemble the following sample output.</span></span>

   ```Output
   SessionId   Name   State    HasMoreData   Location   Command
   ---------   ----   -----    -----------   --------   -------
   1           Job1   Running  True          Server01   Get-Eventlog system
   ```

   <span data-ttu-id="a8241-176">При использовании параметра **AsJob** `Invoke-Command` возвращает тот же тип объекта задания, который `Start-Job` возвращает.</span><span class="sxs-lookup"><span data-stu-id="a8241-176">When the **AsJob** parameter is used, `Invoke-Command` returns the same type of job object that `Start-Job` returns.</span></span> <span data-ttu-id="a8241-177">Вы можете сохранить объект задания в переменной или использовать `Get-Job` команду для получения задания.</span><span class="sxs-lookup"><span data-stu-id="a8241-177">You can save the job object in a variable, or you can use a `Get-Job` command to get the job.</span></span>

   <span data-ttu-id="a8241-178">Обратите внимание, что значение свойства Location показывает, что задание запущено на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="a8241-178">Note that the value of the Location property shows that the job ran on the Server01 computer.</span></span>

1. <span data-ttu-id="a8241-179">Для управления заданием, запущенным с помощью параметра **AsJob** `Invoke-Command` командлета, используйте командлеты задания.</span><span class="sxs-lookup"><span data-stu-id="a8241-179">To manage a job started by using the **AsJob** parameter of the `Invoke-Command` cmdlet, use the Job cmdlets.</span></span> <span data-ttu-id="a8241-180">Так как объект задания, представляющий удаленное задание, находится на локальном компьютере, выполнять удаленные команды для управления заданием не требуется.</span><span class="sxs-lookup"><span data-stu-id="a8241-180">Because the job object that represents the remote job is on the local computer, you do not need to run remote commands to manage the job.</span></span>

   <span data-ttu-id="a8241-181">Чтобы определить, завершено ли задание, используйте `Get-Job` команду.</span><span class="sxs-lookup"><span data-stu-id="a8241-181">To determine whether the job is complete, use a `Get-Job` command.</span></span> <span data-ttu-id="a8241-182">Следующая команда возвращает все задания, запущенные в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="a8241-182">The following command gets all of the jobs that were started in the current session.</span></span>

   ```powershell
   Get-Job
   ```

   <span data-ttu-id="a8241-183">Так как удаленное задание было запущено в текущем сеансе, локальная `Get-Job` команда получает задание.</span><span class="sxs-lookup"><span data-stu-id="a8241-183">Because the remote job was started in the current session, a local `Get-Job` command gets the job.</span></span> <span data-ttu-id="a8241-184">Свойство State объекта Job показывает, что команда выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="a8241-184">The State property of the job object shows that the command was completed successfully.</span></span>

   ```Output
   SessionId   Name   State      HasMoreData   Location   Command
   ---------   ----   -----      -----------   --------   -------
   1           Job1   Completed  True          Server01   Get-Eventlog system
   ```

1. <span data-ttu-id="a8241-185">Чтобы получить результаты задания, используйте `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="a8241-185">To get the results of the job, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="a8241-186">Так как результаты задания автоматически возвращаются на компьютер, где находится объект задания, результаты можно получить с помощью локальной `Receive-Job` команды.</span><span class="sxs-lookup"><span data-stu-id="a8241-186">Because the job results are automatically returned to the computer where the job object resides, you can get the results with a local `Receive-Job` command.</span></span>

   <span data-ttu-id="a8241-187">Следующая команда использует `Receive-Job` командлет для получения результатов задания.</span><span class="sxs-lookup"><span data-stu-id="a8241-187">The following command uses the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="a8241-188">Для идентификации задания используется идентификатор сеанса.</span><span class="sxs-lookup"><span data-stu-id="a8241-188">It uses the session ID to identify the job.</span></span> <span data-ttu-id="a8241-189">Эта команда сохраняет результаты задания в переменной $results.</span><span class="sxs-lookup"><span data-stu-id="a8241-189">This command saves the job results in the $results variable.</span></span> <span data-ttu-id="a8241-190">Можно также перенаправить результаты в файл.</span><span class="sxs-lookup"><span data-stu-id="a8241-190">You can also redirect the results to a file.</span></span>

   ```powershell
   $results = Receive-Job -id 1
   ```

### <a name="start-a-remote-job-that-keeps-the-results-on-the-remote-computer"></a><span data-ttu-id="a8241-191">Запуск удаленного задания, сохраняющего результаты на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="a8241-191">Start a remote job that keeps the results on the remote computer</span></span>

<span data-ttu-id="a8241-192">Чтобы запустить задание на удаленном компьютере, сохраняющем результаты команды на удаленном компьютере, используйте `Invoke-Command` командлет для выполнения `Start-Job` команды на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a8241-192">To start a job on a remote computer that keeps the command results on the remote computer, use the `Invoke-Command` cmdlet to run a `Start-Job` command on a remote computer.</span></span> <span data-ttu-id="a8241-193">Этот метод можно использовать для запуска заданий на нескольких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="a8241-193">You can use this method to run jobs on multiple computers.</span></span>

<span data-ttu-id="a8241-194">При `Start-Job` удаленном запуске команды на удаленном компьютере создается объект задания, и результаты задания сохраняются на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a8241-194">When you run a `Start-Job` command remotely, the job object is created on the remote computer, and the job results are maintained on the remote computer.</span></span>
<span data-ttu-id="a8241-195">С точки зрения задания все операции являются локальными.</span><span class="sxs-lookup"><span data-stu-id="a8241-195">From the perspective of the job, all operations are local.</span></span> <span data-ttu-id="a8241-196">Команды выполняются удаленно для управления локальным заданием на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a8241-196">You are just running commands remotely to manage a local job on the remote computer.</span></span>

1. <span data-ttu-id="a8241-197">Используйте `Invoke-Command` командлет для выполнения `Start-Job` команды на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a8241-197">Use the `Invoke-Command` cmdlet to run a `Start-Job` command on a remote computer.</span></span>

   <span data-ttu-id="a8241-198">Для этой команды требуется сеанс PSSession (постоянное подключение).</span><span class="sxs-lookup"><span data-stu-id="a8241-198">This command requires a PSSession (a persistent connection).</span></span> <span data-ttu-id="a8241-199">Если `Invoke-Command` для установления временного подключения используется параметр ComputerName, `Invoke-Command` выполнение команды считается полным при возвращении объекта задания.</span><span class="sxs-lookup"><span data-stu-id="a8241-199">If you use the ComputerName parameter of `Invoke-Command` to establish a temporary connection, the `Invoke-Command` command is considered to be complete when the job object is returned.</span></span> <span data-ttu-id="a8241-200">В результате этого временное подключение закрывается и задание отменяется.</span><span class="sxs-lookup"><span data-stu-id="a8241-200">As a result, the temporary connection is closed, and the job is canceled.</span></span>

   <span data-ttu-id="a8241-201">Следующая команда использует `New-PSSession` командлет для создания сеанса PSSession, подключенного к компьютеру Server01.</span><span class="sxs-lookup"><span data-stu-id="a8241-201">The following command uses the `New-PSSession` cmdlet to create a PSSession that is connected to the Server01 computer.</span></span> <span data-ttu-id="a8241-202">Команда сохраняет PSSession в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="a8241-202">The command saves the PSSession in the `$s` variable.</span></span>

   ```powershell
   $s = New-PSSession -computername Server01
   ```

   <span data-ttu-id="a8241-203">Следующая команда использует `Invoke-Command` командлет для выполнения `Start-Job` команды в PSSession.</span><span class="sxs-lookup"><span data-stu-id="a8241-203">The next command uses the `Invoke-Command` cmdlet to run a `Start-Job` command in the PSSession.</span></span> <span data-ttu-id="a8241-204">`Start-Job`Команда и `Get-Eventlog` команда заключаются в фигурные скобки.</span><span class="sxs-lookup"><span data-stu-id="a8241-204">The `Start-Job` command and the `Get-Eventlog` command are enclosed in braces.</span></span>

   ```powershell
   Invoke-Command -session $s -scriptblock {
     Start-Job -scriptblock {Get-Eventlog system}}
   ```

   <span data-ttu-id="a8241-205">Результаты похожи на приведенный ниже пример выходных данных.</span><span class="sxs-lookup"><span data-stu-id="a8241-205">The results resemble the following sample output.</span></span>

   ```Output
   Id       Name    State      HasMoreData     Location   Command
   --       ----    -----      -----------     --------   -------
   2        Job2    Running    True            Localhost  Get-Eventlog system
   ```

   <span data-ttu-id="a8241-206">При `Start-Job` удаленном запуске команды `Invoke-Command` возвращает тот же тип объекта задания, который `Start-Job` возвращает.</span><span class="sxs-lookup"><span data-stu-id="a8241-206">When you run a `Start-Job` command remotely, `Invoke-Command` returns the same type of job object that `Start-Job` returns.</span></span> <span data-ttu-id="a8241-207">Вы можете сохранить объект задания в переменной или использовать `Get-Job` команду для получения задания.</span><span class="sxs-lookup"><span data-stu-id="a8241-207">You can save the job object in a variable, or you can use a `Get-Job` command to get the job.</span></span>

   <span data-ttu-id="a8241-208">Обратите внимание, что значение свойства **Location** указывает на то, что задание было запущено на локальном компьютере, известном как localhost, даже если задание было запущено на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="a8241-208">Note that the value of the **Location** property shows that the job ran on the local computer, known as "LocalHost", even though the job ran on the Server01 computer.</span></span> <span data-ttu-id="a8241-209">Так как объект задания создается на компьютере Server01 и задание выполняется на том же компьютере, оно считается локальным фоновым заданием.</span><span class="sxs-lookup"><span data-stu-id="a8241-209">Because the job object is created on the Server01 computer and the job runs on the same computer, it is considered to be a local background job.</span></span>

1. <span data-ttu-id="a8241-210">Для управления удаленным заданием используйте командлеты **задания** .</span><span class="sxs-lookup"><span data-stu-id="a8241-210">To manage a remote job, use the **Job** cmdlets.</span></span> <span data-ttu-id="a8241-211">Так как объект задания находится на удаленном компьютере, необходимо выполнить удаленные команды, чтобы получать, прекращать, ожидать или получать результаты задания.</span><span class="sxs-lookup"><span data-stu-id="a8241-211">Because the job object is on the remote computer, you need to run remote commands to get, stop, wait for, or retrieve the job results.</span></span>

   <span data-ttu-id="a8241-212">Чтобы узнать, завершено ли задание, используйте `Invoke-Command` команду для выполнения `Get-Job` команды в сеансе PSSession, подключенном к компьютеру Server01.</span><span class="sxs-lookup"><span data-stu-id="a8241-212">To see if the job is complete, use an `Invoke-Command` command to run a `Get-Job` command in the PSSession that is connected to the Server01 computer.</span></span>

   ```powershell
   Invoke-Command -session $s -scriptblock {Get-Job}
   ```

   <span data-ttu-id="a8241-213">Команда возвращает объект задания.</span><span class="sxs-lookup"><span data-stu-id="a8241-213">The command returns a job object.</span></span> <span data-ttu-id="a8241-214">Свойство **State** объекта Job показывает, что команда выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="a8241-214">The **State** property of the job object shows that the command was completed successfully.</span></span>

   ```Output
   SessionId   Name  State      HasMoreData   Location   Command
   ---------   ----  -----      -----------   --------   -------
   2           Job2  Completed  True          LocalHost   Get-Eventlog system
   ```

1. <span data-ttu-id="a8241-215">Чтобы получить результаты задания, используйте `Invoke-Command` командлет для выполнения `Receive-Job` команды в сеансе PSSession, подключенном к компьютеру Server01.</span><span class="sxs-lookup"><span data-stu-id="a8241-215">To get the results of the job, use the `Invoke-Command` cmdlet to run a `Receive-Job` command in the PSSession that is connected to the Server01 computer.</span></span>

   <span data-ttu-id="a8241-216">Следующая команда использует `Receive-Job` командлет для получения результатов задания.</span><span class="sxs-lookup"><span data-stu-id="a8241-216">The following command uses the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="a8241-217">Для идентификации задания используется идентификатор сеанса.</span><span class="sxs-lookup"><span data-stu-id="a8241-217">It uses the session ID to identify the job.</span></span> <span data-ttu-id="a8241-218">Эта команда сохраняет результаты задания в `$results` переменной.</span><span class="sxs-lookup"><span data-stu-id="a8241-218">This command saves the job results in the `$results` variable.</span></span> <span data-ttu-id="a8241-219">`Receive-Job`Для сохранения результата в кэше заданий на удаленном компьютере используется параметр сохранения параметра.</span><span class="sxs-lookup"><span data-stu-id="a8241-219">It uses the Keep parameter of `Receive-Job` to keep the result in the job cache on the remote computer.</span></span>

   ```powershell
   $results = Invoke-Command -session $s -scriptblock {
     Receive-Job -SessionId 2 -Keep
   }
   ```

   <span data-ttu-id="a8241-220">Можно также перенаправить результаты в файл на локальном или удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a8241-220">You can also redirect the results to a file on the local or remote computer.</span></span>
   <span data-ttu-id="a8241-221">Следующая команда использует оператор перенаправления для сохранения результатов в файл на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="a8241-221">The following command uses a redirection operator to save the results in a file on the Server01 computer.</span></span>

   ```powershell
   Invoke-Command -session $s -command {
     Receive-Job -SessionId 2 > c:\logs\pslog.txt
   }
   ```

## <a name="how-to-run-as-a-detached-process"></a><span data-ttu-id="a8241-222">Запуск как отсоединенного процесса</span><span class="sxs-lookup"><span data-stu-id="a8241-222">How to run as a detached process</span></span>

<span data-ttu-id="a8241-223">Как упоминалось ранее, при завершении родительского сеанса все выполняющиеся дочерние задания завершаются вместе с их дочерними процессами.</span><span class="sxs-lookup"><span data-stu-id="a8241-223">As previously mentioned, when the parent session is terminated, all running child jobs are terminated along with their child processes.</span></span> <span data-ttu-id="a8241-224">Удаленное взаимодействие на локальном компьютере можно использовать для выполнения заданий, которые не подключены к текущему сеансу PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a8241-224">You can use remoting on the local machine to run jobs that are not attached to the current PowerShell session.</span></span>

<span data-ttu-id="a8241-225">Создайте новый сеанс PowerShell на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a8241-225">Create a new PowerShell session on the local machine.</span></span> <span data-ttu-id="a8241-226">Используется `Invoke-Command` для запуска задания в этом сеансе.</span><span class="sxs-lookup"><span data-stu-id="a8241-226">The use `Invoke-Command` to start a job in this session.</span></span> <span data-ttu-id="a8241-227">`Invoke-Command` позволяет отключить удаленный сеанс и завершить родительский сеанс.</span><span class="sxs-lookup"><span data-stu-id="a8241-227">`Invoke-Command` allows you to disconnect a remote session and terminate the parent session.</span></span> <span data-ttu-id="a8241-228">Позже можно будет запустить новый сеанс PowerShell и подключиться к ранее отключенному сеансу, чтобы возобновить наблюдение за заданием.</span><span class="sxs-lookup"><span data-stu-id="a8241-228">Later, you can start a new PowerShell session and connect to the previously disconnected session to resume monitoring the job.</span></span> <span data-ttu-id="a8241-229">Однако при завершении этого сеанса все данные, которые были возвращены в исходный сеанс PowerShell, теряются.</span><span class="sxs-lookup"><span data-stu-id="a8241-229">However, any data that was returned to the original PowerShell session is lost when that session is terminated.</span></span> <span data-ttu-id="a8241-230">При повторном подключении возвращаются только новые объекты данных, созданные после отключения.</span><span class="sxs-lookup"><span data-stu-id="a8241-230">Only new data objects generated after the disconnect are returned when re-connected.</span></span>

```powershell
# Create remote session on local machine
PS> $session = New-PSSession -cn localhost

# Start remote job
PS> $job = Invoke-Command -Session $session -ScriptBlock { 1..60 | % { sleep 1; "Output $_" } } -AsJob
PS> $job

Id     Name     PSJobTypeName   State         HasMoreData     Location      Command
--     ----     -------------   -----         -----------     --------      -------
1      Job1     RemoteJob       Running       True            localhost     1..60 | % { sleep 1; ...

# Disconnect the job session
PS> Disconnect-PSSession $session

Id Name         Transport ComputerName    ComputerType    State         ConfigurationName     Availability
-- ----         --------- ------------    ------------    -----         -----------------     ------------
1 Runspace1     WSMan     localhost       RemoteMachine   Disconnected  Microsoft.PowerShell          None

PS> $job

Id     Name     PSJobTypeName   State         HasMoreData     Location      Command
--     ----     -------------   -----         -----------     --------      -------
1      Job1     RemoteJob       Disconnected  True            localhost     1..60 | % { sleep 1;

# Reconnect the session to a new job object
PS> $jobNew = Receive-PSSession -Session $session -OutTarget Job
PS> $job | Wait-Job | Receive-Job
Output 9
Output 10
Output 11
...
```

<span data-ttu-id="a8241-231">В этом примере задания по-прежнему присоединяются к родительскому сеансу PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a8241-231">For this example, the jobs are still attached to a parent PowerShell session.</span></span>
<span data-ttu-id="a8241-232">Однако родительский сеанс не является исходным сеансом PowerShell, в котором выполнялся `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="a8241-232">However, the parent session is not the original PowerShell session where `Invoke-Command` was run.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8241-233">См. также</span><span class="sxs-lookup"><span data-stu-id="a8241-233">See also</span></span>

- [<span data-ttu-id="a8241-234">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="a8241-234">about_Jobs</span></span>](about_Jobs.md)
- [<span data-ttu-id="a8241-235">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="a8241-235">about_Job_Details</span></span>](about_Job_Details.md)
- [<span data-ttu-id="a8241-236">about_Remote</span><span class="sxs-lookup"><span data-stu-id="a8241-236">about_Remote</span></span>](about_Remote.md)
- [<span data-ttu-id="a8241-237">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="a8241-237">about_Remote_Variables</span></span>](about_Remote_Variables.md)
- [<span data-ttu-id="a8241-238">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="a8241-238">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)
- [<span data-ttu-id="a8241-239">Start-Job</span><span class="sxs-lookup"><span data-stu-id="a8241-239">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)
- [<span data-ttu-id="a8241-240">Get-Job.</span><span class="sxs-lookup"><span data-stu-id="a8241-240">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)
- [<span data-ttu-id="a8241-241">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="a8241-241">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)
- [<span data-ttu-id="a8241-242">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="a8241-242">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)
- [<span data-ttu-id="a8241-243">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="a8241-243">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)
- [<span data-ttu-id="a8241-244">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="a8241-244">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)
- [<span data-ttu-id="a8241-245">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="a8241-245">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)
- [<span data-ttu-id="a8241-246">Exit-PSSession;</span><span class="sxs-lookup"><span data-stu-id="a8241-246">Exit-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Exit-PSSession)
