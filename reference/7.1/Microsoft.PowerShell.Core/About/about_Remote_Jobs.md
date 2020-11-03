---
description: Описывает, как выполнять фоновые задания на удаленных компьютерах.
keywords: powershell,командлет
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_jobs?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Jobs
ms.openlocfilehash: fb2270ea5c0acdcf2c506e687787d22c73e2cb2c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232109"
---
# <a name="about-remote-jobs"></a><span data-ttu-id="05080-104">Об удаленных заданиях</span><span class="sxs-lookup"><span data-stu-id="05080-104">About Remote Jobs</span></span>

## <a name="short-description"></a><span data-ttu-id="05080-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="05080-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="05080-106">Описывает, как выполнять фоновые задания на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="05080-106">Describes how to run background jobs on remote computers.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="05080-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="05080-107">DETAILED DESCRIPTION</span></span>

<span data-ttu-id="05080-108">Фоновое задание — это команда, которая выполняется асинхронно без взаимодействия с текущим сеансом.</span><span class="sxs-lookup"><span data-stu-id="05080-108">A background job is a command that runs asynchronously without interacting with the current session.</span></span> <span data-ttu-id="05080-109">Командная строка немедленно возвращается, и вы можете продолжать использовать сеанс во время выполнения задания.</span><span class="sxs-lookup"><span data-stu-id="05080-109">The command prompt returns immediately, and you can continue to use the session while the job runs.</span></span>

<span data-ttu-id="05080-110">По умолчанию фоновые задания выполняются на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="05080-110">By default, background jobs run on the local computer.</span></span> <span data-ttu-id="05080-111">Однако для выполнения фоновых заданий на удаленных компьютерах можно использовать несколько разных процедур.</span><span class="sxs-lookup"><span data-stu-id="05080-111">However, you can use several different procedures to run background jobs on remote computers.</span></span>

<span data-ttu-id="05080-112">В этом разделе объясняется, как запустить фоновое задание на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="05080-112">This topic explains how to run a background job on a remote computer.</span></span> <span data-ttu-id="05080-113">Дополнительные сведения о выполнении фоновых заданий на локальном компьютере см. в разделе [about_Jobs](about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="05080-113">For information about how to run background jobs on a local computer, see [about_Jobs](about_Jobs.md).</span></span> <span data-ttu-id="05080-114">Дополнительные сведения о фоновых заданиях см. в разделе [about_Job_Details](about_Job_Details.md).</span><span class="sxs-lookup"><span data-stu-id="05080-114">For more information about background jobs, see [about_Job_Details](about_Job_Details.md).</span></span>

## <a name="remote-background-jobs"></a><span data-ttu-id="05080-115">УДАЛЕННЫЕ ФОНОВЫЕ ЗАДАНИЯ</span><span class="sxs-lookup"><span data-stu-id="05080-115">REMOTE BACKGROUND JOBS</span></span>

<span data-ttu-id="05080-116">Фоновые задания можно выполнять на удаленных компьютерах с помощью трех различных методов.</span><span class="sxs-lookup"><span data-stu-id="05080-116">You can run background jobs on remote computers by using three different methods.</span></span>

- <span data-ttu-id="05080-117">Запустите интерактивный сеанс с удаленным компьютером и запустите задание в интерактивном сеансе.</span><span class="sxs-lookup"><span data-stu-id="05080-117">Start an interactive session with a remote computer, and start a job in the interactive session.</span></span> <span data-ttu-id="05080-118">Процедуры совпадают с выполнением локального задания, хотя все действия выполняются на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="05080-118">The procedures are the same as running a local job, although all actions are performed on the remote computer.</span></span>

- <span data-ttu-id="05080-119">Запуск фонового задания на удаленном компьютере, который возвращает результаты на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="05080-119">Run a background job on a remote computer that returns its results to the local computer.</span></span> <span data-ttu-id="05080-120">Используйте этот метод, если требуется получать результаты фоновых заданий и обслуживать их в центральном расположении на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="05080-120">Use this method when you want to collect the results of background jobs and maintain them in a central location on the local computer.</span></span>

- <span data-ttu-id="05080-121">Выполнение фонового задания на удаленном компьютере, в котором хранятся результаты на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="05080-121">Run a background job on a remote computer that maintains its results on the remote computer.</span></span> <span data-ttu-id="05080-122">Используйте этот метод, если данные задания более безопасно поддерживаются на исходном компьютере.</span><span class="sxs-lookup"><span data-stu-id="05080-122">Use this method when the job data is more securely maintained on the originating computer.</span></span>

### <a name="start-a-background-job-in-an-interactive-session"></a><span data-ttu-id="05080-123">ЗАПУСК ФОНОВОГО ЗАДАНИЯ В ИНТЕРАКТИВНОМ СЕАНСЕ</span><span class="sxs-lookup"><span data-stu-id="05080-123">START A BACKGROUND JOB IN AN INTERACTIVE SESSION</span></span>

<span data-ttu-id="05080-124">Можно запустить интерактивный сеанс с удаленным компьютером, а затем запустить фоновое задание во время интерактивного сеанса.</span><span class="sxs-lookup"><span data-stu-id="05080-124">You can start an interactive session with a remote computer and then start a background job during the interactive session.</span></span> <span data-ttu-id="05080-125">Дополнительные сведения о интерактивных сеансах см. в разделе about_Remote и см. в разделе Ввод-PSSession.</span><span class="sxs-lookup"><span data-stu-id="05080-125">For more information about interactive sessions, see about_Remote, and see Enter-PSSession.</span></span>

<span data-ttu-id="05080-126">Процедура запуска фонового задания в интерактивном сеансе практически идентична процедуре запуска фонового задания на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="05080-126">The procedure for starting a background job in an interactive session is almost identical to the procedure for starting a background job on the local computer.</span></span> <span data-ttu-id="05080-127">Однако все операции выполняются на удаленном компьютере, а не на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="05080-127">However, all of the operations occur on the remote computer, not the local computer.</span></span>

#### <a name="step-1-enter-pssession"></a><span data-ttu-id="05080-128">ШАГ 1. ВВОД-PSSESSION</span><span class="sxs-lookup"><span data-stu-id="05080-128">STEP 1: ENTER-PSSESSION</span></span>

<span data-ttu-id="05080-129">Используйте командлет Enter-PSSession для запуска интерактивного сеанса с удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="05080-129">Use the Enter-PSSession cmdlet to start an interactive session with a remote computer.</span></span> <span data-ttu-id="05080-130">Чтобы установить временное подключение для интерактивного сеанса, можно использовать параметр ComputerName из Enter-PSSession.</span><span class="sxs-lookup"><span data-stu-id="05080-130">You can use the ComputerName parameter of Enter-PSSession to establish a temporary connection for the interactive session.</span></span> <span data-ttu-id="05080-131">Кроме того, можно использовать параметр Session для выполнения интерактивного сеанса в сеансе PowerShell (PSSession).</span><span class="sxs-lookup"><span data-stu-id="05080-131">Or, you can use the Session parameter to run the interactive session in a PowerShell session (PSSession).</span></span>

<span data-ttu-id="05080-132">Следующая команда запускает интерактивный сеанс на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="05080-132">The following command starts an interactive session on the Server01 computer.</span></span>

```powershell
C:\PS> Enter-PSSession -computername Server01
```

<span data-ttu-id="05080-133">Командная строка изменится и отобразится, что теперь вы подключены к компьютеру Server01.</span><span class="sxs-lookup"><span data-stu-id="05080-133">The command prompt changes to show that you are now connected to the Server01 computer.</span></span>

```
Server01\C:>
```

#### <a name="step-2-start-job"></a><span data-ttu-id="05080-134">ШАГ 2. ЗАПУСК — ЗАДАНИЕ</span><span class="sxs-lookup"><span data-stu-id="05080-134">STEP 2: START-JOB</span></span>

<span data-ttu-id="05080-135">Чтобы запустить фоновое задание в сеансе, используйте командлет Start-Job.</span><span class="sxs-lookup"><span data-stu-id="05080-135">To start a background job in the session, use the Start-Job cmdlet.</span></span>

<span data-ttu-id="05080-136">Следующая команда запускает фоновое задание, которое получает события в журнале событий Windows PowerShell на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="05080-136">The following command runs a background job that gets the events in the Windows PowerShell event log on the Server01 computer.</span></span> <span data-ttu-id="05080-137">Командлет Start-Job возвращает объект, представляющий задание.</span><span class="sxs-lookup"><span data-stu-id="05080-137">The Start-Job cmdlet returns an object that represents the job.</span></span>

<span data-ttu-id="05080-138">Эта команда сохраняет объект задания в \$ переменной задания.</span><span class="sxs-lookup"><span data-stu-id="05080-138">This command saves the job object in the \$job variable.</span></span>

```powershell
Server01\C:> $job = start-job -scriptblock {
  get-eventlog "Windows PowerShell"
}
```

<span data-ttu-id="05080-139">Во время выполнения задания можно использовать интерактивный сеанс для выполнения других команд, включая другие фоновые задания.</span><span class="sxs-lookup"><span data-stu-id="05080-139">While the job runs, you can use the interactive session to run other commands, including other background jobs.</span></span> <span data-ttu-id="05080-140">Однако интерактивный сеанс должен быть открыт до завершения задания.</span><span class="sxs-lookup"><span data-stu-id="05080-140">However, you must keep the interactive session open until the job is completed.</span></span> <span data-ttu-id="05080-141">Если завершить сеанс, задание будет прервано и результаты будут утеряны.</span><span class="sxs-lookup"><span data-stu-id="05080-141">If you end the session, the job is interrupted, and the results are lost.</span></span>

#### <a name="step-3-get-job"></a><span data-ttu-id="05080-142">ШАГ 3. ПОЛУЧЕНИЕ И ЗАДАНИЕ</span><span class="sxs-lookup"><span data-stu-id="05080-142">STEP 3: GET-JOB</span></span>

<span data-ttu-id="05080-143">Чтобы узнать, завершено ли задание, отобразите значение \$ переменной задания или используйте командлет Get-Job для получения задания.</span><span class="sxs-lookup"><span data-stu-id="05080-143">To find out if the job is complete, display the value of the \$job variable, or use the Get-Job cmdlet to get the job.</span></span> <span data-ttu-id="05080-144">Следующая команда использует командлет Get-Job для вывода задания.</span><span class="sxs-lookup"><span data-stu-id="05080-144">The following command uses the Get-Job cmdlet to display the job.</span></span>

```powershell
Server01\C:> get-job $job

SessionId  Name  State      HasMoreData  Location   Command
---------  ----  -----      -----------  --------   -------
1          Job1  Complete   True         localhost  get-eventlog "Windows...
```

<span data-ttu-id="05080-145">В выходных данных Get-Job показано, что задание выполняется на компьютере "localhost", так как задание было запущено на том же компьютере (в данном случае Server01).</span><span class="sxs-lookup"><span data-stu-id="05080-145">The Get-Job output shows that job is running on the "localhost" computer because the job was started on and is running on the same computer (in this case, Server01).</span></span>

#### <a name="step-4-receive-job"></a><span data-ttu-id="05080-146">ШАГ 4. ПОЛУЧЕНИЕ-ЗАДАНИЕ</span><span class="sxs-lookup"><span data-stu-id="05080-146">STEP 4: RECEIVE-JOB</span></span>

<span data-ttu-id="05080-147">Чтобы получить результаты задания, используйте командлет Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="05080-147">To get the results of the job, use the Receive-Job cmdlet.</span></span> <span data-ttu-id="05080-148">Результаты можно отобразить в интерактивном сеансе или сохранить в файл на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="05080-148">You can display the results in the interactive session or save them to a file on the remote computer.</span></span> <span data-ttu-id="05080-149">Следующая команда возвращает результаты задания в переменной $job.</span><span class="sxs-lookup"><span data-stu-id="05080-149">The following command gets the results of the job in the $job variable.</span></span> <span data-ttu-id="05080-150">Команда использует оператор перенаправления (>) для сохранения результатов задания в файле PsLog.txt на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="05080-150">The command uses the redirection operator (>) to save the results of the job in the PsLog.txt file on the Server01 computer.</span></span>

```powershell
Server01\C:> receive-job $job > c:\logs\PsLog.txt
```

#### <a name="step-5-exit-pssession"></a><span data-ttu-id="05080-151">ШАГ 5. EXIT-PSSESSION</span><span class="sxs-lookup"><span data-stu-id="05080-151">STEP 5: EXIT-PSSESSION</span></span>

<span data-ttu-id="05080-152">Чтобы завершить интерактивный сеанс, используйте командлет Exit-PSSession.</span><span class="sxs-lookup"><span data-stu-id="05080-152">To end the interactive session, use the Exit-PSSession cmdlet.</span></span> <span data-ttu-id="05080-153">Командная строка изменится, чтобы отобразить, что вы снова используете исходный сеанс на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="05080-153">The command prompt changes to show that you are back in the original session on the local computer.</span></span>

```powershell
Server01\C:> Exit-PSSession
C:\PS>
```

#### <a name="step-6-invoke-command-get-content"></a><span data-ttu-id="05080-154">ШАГ 6. ВЫЗОВ КОМАНДЫ: GET-CONTENT</span><span class="sxs-lookup"><span data-stu-id="05080-154">STEP 6: INVOKE-COMMAND: GET-CONTENT</span></span>

<span data-ttu-id="05080-155">Чтобы просмотреть содержимое файла PsLog.txt на компьютере Server01 в любое время, запустите другой интерактивный сеанс или выполните удаленную команду.</span><span class="sxs-lookup"><span data-stu-id="05080-155">To view the contents of the PsLog.txt file on the Server01 computer at any time, start another interactive session, or run a remote command.</span></span> <span data-ttu-id="05080-156">Этот тип команды лучше выполнять в PSSession (постоянное подключение) на случай, если требуется использовать несколько команд для исследования и управления данными в файле PsLog.txt.</span><span class="sxs-lookup"><span data-stu-id="05080-156">This type of command is best run in a PSSession (a persistent connection) in case you want to use several commands to investigate and manage the data in the PsLog.txt file.</span></span> <span data-ttu-id="05080-157">Дополнительные сведения о PSSession см. в разделе about_PSSessions.</span><span class="sxs-lookup"><span data-stu-id="05080-157">For more information about PSSessions, see about_PSSessions.</span></span>

<span data-ttu-id="05080-158">Следующие команды используют командлет New-PSSession для создания сеанса PSSession, подключенного к компьютеру Server01, и используют командлет Invoke-Command для выполнения команды Get-Content в сеансе PSSession для просмотра содержимого файла.</span><span class="sxs-lookup"><span data-stu-id="05080-158">The following commands use the New-PSSession cmdlet to create a PSSession that is connected to the Server01 computer, and they use the Invoke-Command cmdlet to run a Get-Content command in the PSSession to view the contents of the file.</span></span>

```powershell
$s = new-pssession -computername Server01
invoke-command -session $s -scriptblock {
  get-content c:\logs\pslog.txt}
```

### <a name="start-a-remote-job-that-returns-the-results-to-the-local-computer-asjob"></a><span data-ttu-id="05080-159">Запуск удаленного задания, которое ВОЗВРАЩАЕТ результаты на локальный компьютер ( \( ASJOB)\)</span><span class="sxs-lookup"><span data-stu-id="05080-159">START A REMOTE JOB THAT RETURNS THE RESULTS TO THE LOCAL COMPUTER \(ASJOB\)</span></span>

<span data-ttu-id="05080-160">Чтобы запустить фоновое задание на удаленном компьютере, которое возвращает результаты команды на локальный компьютер, используйте параметр AsJob командлета, например командлет Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="05080-160">To start a background job on a remote computer that returns the command results to the local computer, use the AsJob parameter of a cmdlet such as the Invoke-Command cmdlet.</span></span>

<span data-ttu-id="05080-161">При использовании параметра AsJob объект задания на самом деле создается на локальном компьютере, даже если задание выполняется на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="05080-161">When you use the AsJob parameter, the job object is actually created on the local computer even though the job runs on the remote computer.</span></span> <span data-ttu-id="05080-162">После завершения задания результаты возвращаются на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="05080-162">When the job is completed, the results are returned to the local computer.</span></span>

<span data-ttu-id="05080-163">Для управления любыми заданиями, созданными любым командлетом, можно использовать командлеты, содержащие существительное задания (командлеты задания).</span><span class="sxs-lookup"><span data-stu-id="05080-163">You can use the cmdlets that contain the Job noun (the Job cmdlets) to manage any job created by any cmdlet.</span></span> <span data-ttu-id="05080-164">Многие командлеты, имеющие параметры AsJob, не используют удаленное взаимодействие PowerShell, поэтому их можно использовать даже на компьютерах, которые не настроены на удаленное взаимодействие и которые не соответствуют требованиям к удаленному взаимодействию.</span><span class="sxs-lookup"><span data-stu-id="05080-164">Many of the cmdlets that have AsJob parameters do not use PowerShell remoting, so you can use them even on computers that are not configured for remoting and that do not meet the requirements for remoting.</span></span>

#### <a name="step-1-invoke-command--asjob"></a><span data-ttu-id="05080-165">ШАГ 1. INVOKE-COMMAND-ASJOB</span><span class="sxs-lookup"><span data-stu-id="05080-165">STEP 1: INVOKE-COMMAND -ASJOB</span></span>

<span data-ttu-id="05080-166">Следующая команда использует параметр AsJob Invoke-Command для запуска фонового задания на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="05080-166">The following command uses the AsJob parameter of Invoke-Command to start a background job on the Server01 computer.</span></span> <span data-ttu-id="05080-167">Задание выполняет команду Get-Eventlog, которая получает события в журнале системы.</span><span class="sxs-lookup"><span data-stu-id="05080-167">The job runs a Get-Eventlog command that gets the events in the System log.</span></span> <span data-ttu-id="05080-168">Вы можете использовать параметр JobName, чтобы назначить для задания отображаемое имя.</span><span class="sxs-lookup"><span data-stu-id="05080-168">You can use the JobName parameter to assign a display name to the job.</span></span>

```powershell
invoke-command -computername Server01 -scriptblock {
  get-eventlog system} -asjob
```

<span data-ttu-id="05080-169">Результаты выполнения команды похожи на приведенный ниже образец выходных данных.</span><span class="sxs-lookup"><span data-stu-id="05080-169">The results of the command resemble the following sample output.</span></span>

```Output
SessionId   Name   State    HasMoreData   Location   Command
---------   ----   -----    -----------   --------   -------
1           Job1   Running  True          Server01   get-eventlog system
```

<span data-ttu-id="05080-170">При использовании параметра AsJob Invoke-Command возвращает тот же тип объекта задания, который Start-Job возвращает.</span><span class="sxs-lookup"><span data-stu-id="05080-170">When the AsJob parameter is used, Invoke-Command returns the same type of job object that Start-Job returns.</span></span> <span data-ttu-id="05080-171">Вы можете сохранить объект задания в переменной или воспользоваться командой Get-Job для получения задания.</span><span class="sxs-lookup"><span data-stu-id="05080-171">You can save the job object in a variable, or you can use a Get-Job command to get the job.</span></span>

<span data-ttu-id="05080-172">Обратите внимание, что значение свойства Location показывает, что задание запущено на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="05080-172">Note that the value of the Location property shows that the job ran on the Server01 computer.</span></span>

#### <a name="step-2-get-job"></a><span data-ttu-id="05080-173">ШАГ 2. ПОЛУЧЕНИЕ-ЗАДАНИЕ</span><span class="sxs-lookup"><span data-stu-id="05080-173">STEP 2: GET-JOB</span></span>

<span data-ttu-id="05080-174">Для управления заданием, запущенным с помощью параметра AsJob командлета Invoke-Command, используйте командлеты задания.</span><span class="sxs-lookup"><span data-stu-id="05080-174">To manage a job started by using the AsJob parameter of the Invoke-Command cmdlet, use the Job cmdlets.</span></span> <span data-ttu-id="05080-175">Так как объект задания, представляющий удаленное задание, находится на локальном компьютере, выполнять удаленные команды для управления заданием не требуется.</span><span class="sxs-lookup"><span data-stu-id="05080-175">Because the job object that represents the remote job is on the local computer, you do not need to run remote commands to manage the job.</span></span>

<span data-ttu-id="05080-176">Чтобы определить, завершено ли задание, используйте команду Get-Job.</span><span class="sxs-lookup"><span data-stu-id="05080-176">To determine whether the job is complete, use a Get-Job command.</span></span> <span data-ttu-id="05080-177">Следующая команда возвращает все задания, запущенные в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="05080-177">The following command gets all of the jobs that were started in the current session.</span></span>

```powershell
get-job
```

<span data-ttu-id="05080-178">Так как удаленное задание было запущено в текущем сеансе, локальная команда Get-Job получает задание.</span><span class="sxs-lookup"><span data-stu-id="05080-178">Because the remote job was started in the current session, a local Get-Job command gets the job.</span></span> <span data-ttu-id="05080-179">Свойство State объекта Job показывает, что команда выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="05080-179">The State property of the job object shows that the command was completed successfully.</span></span>

```Output
SessionId   Name   State      HasMoreData   Location   Command
---------   ----   -----      -----------   --------   -------
1           Job1   Completed  True          Server01   get-eventlog system
```

#### <a name="step-3-receive-job"></a><span data-ttu-id="05080-180">ШАГ 3. ПОЛУЧЕНИЕ-ЗАДАНИЕ</span><span class="sxs-lookup"><span data-stu-id="05080-180">STEP 3: RECEIVE-JOB</span></span>

<span data-ttu-id="05080-181">Чтобы получить результаты задания, используйте командлет Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="05080-181">To get the results of the job, use the Receive-Job cmdlet.</span></span> <span data-ttu-id="05080-182">Так как результаты задания автоматически возвращаются на компьютер, где находится объект задания, результаты можно получить с помощью локальной команды Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="05080-182">Because the job results are automatically returned to the computer where the job object resides, you can get the results with a local Receive-Job command.</span></span>

<span data-ttu-id="05080-183">Следующая команда использует командлет Receive-Job для получения результатов задания.</span><span class="sxs-lookup"><span data-stu-id="05080-183">The following command uses the Receive-Job cmdlet to get the results of the job.</span></span> <span data-ttu-id="05080-184">Для идентификации задания используется идентификатор сеанса.</span><span class="sxs-lookup"><span data-stu-id="05080-184">It uses the session ID to identify the job.</span></span> <span data-ttu-id="05080-185">Эта команда сохраняет результаты задания в переменной $results.</span><span class="sxs-lookup"><span data-stu-id="05080-185">This command saves the job results in the $results variable.</span></span> <span data-ttu-id="05080-186">Можно также перенаправить результаты в файл.</span><span class="sxs-lookup"><span data-stu-id="05080-186">You can also redirect the results to a file.</span></span>

```powershell
$results = receive-job -id 1
```

### <a name="start-a-remote-job-that-keeps-the-results-on-the-remote-computer"></a><span data-ttu-id="05080-187">ЗАПУСК УДАЛЕННОГО ЗАДАНИЯ, СОХРАНЯЮЩЕГО РЕЗУЛЬТАТЫ НА УДАЛЕННОМ КОМПЬЮТЕРЕ</span><span class="sxs-lookup"><span data-stu-id="05080-187">START A REMOTE JOB THAT KEEPS THE RESULTS ON THE REMOTE COMPUTER</span></span>

<span data-ttu-id="05080-188">Чтобы запустить фоновое задание на удаленном компьютере, сохраняющем результаты команды на удаленном компьютере, используйте командлет Invoke-Command, чтобы выполнить команду Start-Job на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="05080-188">To start a background job on a remote computer that keeps the command results on the remote computer, use the Invoke-Command cmdlet to run a Start-Job command on a remote computer.</span></span> <span data-ttu-id="05080-189">Этот метод можно использовать для выполнения фоновых заданий на нескольких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="05080-189">You can use this method to run background jobs on multiple computers.</span></span>

<span data-ttu-id="05080-190">При удаленном запуске команды Start-Job на удаленном компьютере создается объект задания, а результаты задания сохраняются на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="05080-190">When you run a Start-Job command remotely, the job object is created on the remote computer, and the job results are maintained on the remote computer.</span></span>
<span data-ttu-id="05080-191">С точки зрения задания все операции являются локальными.</span><span class="sxs-lookup"><span data-stu-id="05080-191">From the perspective of the job, all operations are local.</span></span> <span data-ttu-id="05080-192">Команды выполняются удаленно для управления локальным заданием на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="05080-192">You are just running commands remotely to manage a local job on the remote computer.</span></span>

#### <a name="step-1-invoke-command-start-job"></a><span data-ttu-id="05080-193">ШАГ 1. ЗАПУСК-КОМАНДА START — ЗАДАНИЕ</span><span class="sxs-lookup"><span data-stu-id="05080-193">STEP 1: INVOKE-COMMAND START-JOB</span></span>

<span data-ttu-id="05080-194">Используйте командлет Invoke-Command, чтобы выполнить команду Start-Job на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="05080-194">Use the Invoke-Command cmdlet to run a Start-Job command on a remote computer.</span></span>

<span data-ttu-id="05080-195">Для этой команды требуется сеанс PSSession (постоянное подключение).</span><span class="sxs-lookup"><span data-stu-id="05080-195">This command requires a PSSession (a persistent connection).</span></span> <span data-ttu-id="05080-196">Если для установления временного подключения используется параметр ComputerName Invoke-Command, то Invoke-Command команда считается завершенной при возвращении объекта задания.</span><span class="sxs-lookup"><span data-stu-id="05080-196">If you use the ComputerName parameter of Invoke-Command to establish a temporary connection, the Invoke-Command command is considered to be complete when the job object is returned.</span></span> <span data-ttu-id="05080-197">В результате этого временное подключение закрывается и задание отменяется.</span><span class="sxs-lookup"><span data-stu-id="05080-197">As a result, the temporary connection is closed, and the job is canceled.</span></span>

<span data-ttu-id="05080-198">Следующая команда использует командлет New-PSSession для создания сеанса PSSession, подключенного к компьютеру Server01.</span><span class="sxs-lookup"><span data-stu-id="05080-198">The following command uses the New-PSSession cmdlet to create a PSSession that is connected to the Server01 computer.</span></span> <span data-ttu-id="05080-199">Команда сохраняет PSSession в \$ переменной s.</span><span class="sxs-lookup"><span data-stu-id="05080-199">The command saves the PSSession in the \$s variable.</span></span>

```powershell
$s = new-pssession -computername Server01
```

<span data-ttu-id="05080-200">Следующая команда использует командлет Invoke-Command для выполнения команды Start-Job в сеансе PSSession.</span><span class="sxs-lookup"><span data-stu-id="05080-200">The next command uses the Invoke-Command cmdlet to run a Start-Job command in the PSSession.</span></span> <span data-ttu-id="05080-201">Команда Start-Job и команда Get-Eventlog заключаются в фигурные скобки.</span><span class="sxs-lookup"><span data-stu-id="05080-201">The Start-Job command and the Get-Eventlog command are enclosed in braces.</span></span>

```powershell
invoke-command -session $s -scriptblock {
  start-job -scriptblock {get-eventlog system}}
```

<span data-ttu-id="05080-202">Результаты похожи на приведенный ниже пример выходных данных.</span><span class="sxs-lookup"><span data-stu-id="05080-202">The results resemble the following sample output.</span></span>

```Output
Id       Name    State      HasMoreData     Location   Command
--       ----    -----      -----------     --------   -------
2        Job2    Running    True            Localhost  get-eventlog system
```

<span data-ttu-id="05080-203">При удаленном запуске команды Start-Job Invoke-Command возвращает тот же тип объекта задания, который Start-Job возвращает.</span><span class="sxs-lookup"><span data-stu-id="05080-203">When you run a Start-Job command remotely, Invoke-Command returns the same type of job object that Start-Job returns.</span></span> <span data-ttu-id="05080-204">Вы можете сохранить объект задания в переменной или воспользоваться командой Get-Job для получения задания.</span><span class="sxs-lookup"><span data-stu-id="05080-204">You can save the job object in a variable, or you can use a Get-Job command to get the job.</span></span>

<span data-ttu-id="05080-205">Обратите внимание, что значение свойства Location указывает на то, что задание было запущено на локальном компьютере, известном как LocalHost, даже если задание было запущено на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="05080-205">Note that the value of the Location property shows that the job ran on the local computer, known as "LocalHost", even though the job ran on the Server01 computer.</span></span> <span data-ttu-id="05080-206">Так как объект задания создается на компьютере Server01 и задание выполняется на том же компьютере, оно считается локальным фоновым заданием.</span><span class="sxs-lookup"><span data-stu-id="05080-206">Because the job object is created on the Server01 computer and the job runs on the same computer, it is considered to be a local background job.</span></span>

#### <a name="step-2-invoke-command-get-job"></a><span data-ttu-id="05080-207">ШАГ 2. КОМАНДЛЕТ INVOKE-COMMAND GET-JOB</span><span class="sxs-lookup"><span data-stu-id="05080-207">STEP 2: INVOKE-COMMAND GET-JOB</span></span>

<span data-ttu-id="05080-208">Для управления удаленным фоновым заданием используйте командлеты задания.</span><span class="sxs-lookup"><span data-stu-id="05080-208">To manage a remote background job, use the Job cmdlets.</span></span> <span data-ttu-id="05080-209">Так как объект задания находится на удаленном компьютере, необходимо выполнить удаленные команды, чтобы получать, прекращать, ожидать или получать результаты задания.</span><span class="sxs-lookup"><span data-stu-id="05080-209">Because the job object is on the remote computer, you need to run remote commands to get, stop, wait for, or retrieve the job results.</span></span>

<span data-ttu-id="05080-210">Чтобы узнать, завершено ли задание, используйте команду Invoke-Command, чтобы выполнить команду Get-Job в сеансе PSSession, подключенном к компьютеру Server01.</span><span class="sxs-lookup"><span data-stu-id="05080-210">To see if the job is complete, use an Invoke-Command command to run a Get-Job command in the PSSession that is connected to the Server01 computer.</span></span>

```powershell
invoke-command -session $s -scriptblock {get-job}
```

<span data-ttu-id="05080-211">Команда возвращает объект задания.</span><span class="sxs-lookup"><span data-stu-id="05080-211">The command returns a job object.</span></span> <span data-ttu-id="05080-212">Свойство State объекта Job показывает, что команда выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="05080-212">The State property of the job object shows that the command was completed successfully.</span></span>

```Output
SessionId   Name  State      HasMoreData   Location   Command
---------   ----  -----      -----------   --------   -------
2           Job2  Completed  True          LocalHost   get-eventlog system
```

#### <a name="step-3-invoke-command-receive-job"></a><span data-ttu-id="05080-213">ШАГ 3. ПОЛУЧЕНИЕ ВЫЗОВА КОМАНДЫ ДЛЯ ЗАДАНИЯ</span><span class="sxs-lookup"><span data-stu-id="05080-213">STEP 3: INVOKE-COMMAND RECEIVE-JOB</span></span>

<span data-ttu-id="05080-214">Чтобы получить результаты задания, используйте командлет Invoke-Command, чтобы выполнить команду Receive-Job в сеансе PSSession, подключенном к компьютеру Server01.</span><span class="sxs-lookup"><span data-stu-id="05080-214">To get the results of the job, use the Invoke-Command cmdlet to run a Receive-Job command in the PSSession that is connected to the Server01 computer.</span></span>

<span data-ttu-id="05080-215">Следующая команда использует командлет Receive-Job для получения результатов задания.</span><span class="sxs-lookup"><span data-stu-id="05080-215">The following command uses the Receive-Job cmdlet to get the results of the job.</span></span> <span data-ttu-id="05080-216">Для идентификации задания используется идентификатор сеанса.</span><span class="sxs-lookup"><span data-stu-id="05080-216">It uses the session ID to identify the job.</span></span> <span data-ttu-id="05080-217">Эта команда сохраняет результаты задания в \$ переменной results.</span><span class="sxs-lookup"><span data-stu-id="05080-217">This command saves the job results in the \$results variable.</span></span> <span data-ttu-id="05080-218">Для сохранения результатов в кэше заданий на удаленном компьютере используется параметр сохранения Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="05080-218">It uses the Keep parameter of Receive-Job to keep the result in the job cache on the remote computer.</span></span>

```powershell
$results = invoke-command -session $s -scriptblock {
  receive-job -sessionid 2 -keep}
```

<span data-ttu-id="05080-219">Можно также перенаправить результаты в файл на локальном или удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="05080-219">You can also redirect the results to a file on the local or remote computer.</span></span>
<span data-ttu-id="05080-220">Следующая команда использует оператор перенаправления для сохранения результатов в файл на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="05080-220">The following command uses a redirection operator to save the results in a file on the Server01 computer.</span></span>

```powershell
invoke-command -session $s -command {
  receive-job -sessionid 2 > c:\logs\pslog.txt}
```

## <a name="see-also"></a><span data-ttu-id="05080-221">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="05080-221">SEE ALSO</span></span>

[<span data-ttu-id="05080-222">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="05080-222">about_Jobs</span></span>](about_Jobs.md)

[<span data-ttu-id="05080-223">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="05080-223">about_Job_Details</span></span>](about_Job_Details.md)

[<span data-ttu-id="05080-224">about_Remote</span><span class="sxs-lookup"><span data-stu-id="05080-224">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="05080-225">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="05080-225">about_Remote_Variables</span></span>](about_Remote_Variables.md)

[<span data-ttu-id="05080-226">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="05080-226">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="05080-227">Start-Job</span><span class="sxs-lookup"><span data-stu-id="05080-227">Start-Job</span></span>](xref:Microsoft.PowerShell.Core.Start-Job)

[<span data-ttu-id="05080-228">Get-Job.</span><span class="sxs-lookup"><span data-stu-id="05080-228">Get-Job</span></span>](xref:Microsoft.PowerShell.Core.Get-Job)

[<span data-ttu-id="05080-229">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="05080-229">Wait-Job</span></span>](xref:Microsoft.PowerShell.Core.Wait-Job)

[<span data-ttu-id="05080-230">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="05080-230">Stop-Job</span></span>](xref:Microsoft.PowerShell.Core.Stop-Job)

[<span data-ttu-id="05080-231">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="05080-231">Remove-Job</span></span>](xref:Microsoft.PowerShell.Core.Remove-Job)

[<span data-ttu-id="05080-232">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="05080-232">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

[<span data-ttu-id="05080-233">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="05080-233">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="05080-234">Exit-PSSession;</span><span class="sxs-lookup"><span data-stu-id="05080-234">Exit-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Exit-PSSession)

