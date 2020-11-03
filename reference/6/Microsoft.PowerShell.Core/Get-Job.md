---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-job?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Job.
ms.openlocfilehash: d61f1efc613b7628585e5090b9fad8d90333a291
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228190"
---
# <span data-ttu-id="59229-103">Get-Job.</span><span class="sxs-lookup"><span data-stu-id="59229-103">Get-Job</span></span>

## <span data-ttu-id="59229-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="59229-104">SYNOPSIS</span></span>
<span data-ttu-id="59229-105">Возвращает фоновые задания PowerShell, выполняемые в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="59229-105">Gets PowerShell background jobs that are running in the current session.</span></span>

## <span data-ttu-id="59229-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="59229-106">SYNTAX</span></span>

### <span data-ttu-id="59229-107">Сессионидпараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="59229-107">SessionIdParameterSet (Default)</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [[-Id] <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="59229-108">инстанцеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="59229-108">InstanceIdParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="59229-109">намепараметерсет</span><span class="sxs-lookup"><span data-stu-id="59229-109">NameParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="59229-110">статепараметерсет</span><span class="sxs-lookup"><span data-stu-id="59229-110">StateParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-State] <JobState> [<CommonParameters>]
```

### <span data-ttu-id="59229-111">коммандпараметерсет</span><span class="sxs-lookup"><span data-stu-id="59229-111">CommandParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Command <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="59229-112">филтерпараметерсет</span><span class="sxs-lookup"><span data-stu-id="59229-112">FilterParameterSet</span></span>

```
Get-Job [-Filter] <Hashtable> [<CommonParameters>]
```

## <span data-ttu-id="59229-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="59229-113">DESCRIPTION</span></span>

<span data-ttu-id="59229-114">Командлет **Get-Job** возвращает объекты, которые представляют фоновые задания, запущенные в рамках текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="59229-114">The **Get-Job** cmdlet gets objects that represent the background jobs that were started in the current session.</span></span> <span data-ttu-id="59229-115">**Get-Job** можно использовать для получения заданий, запущенных с помощью командлета Start-Job, или с помощью параметра *AsJob* любого командлета.</span><span class="sxs-lookup"><span data-stu-id="59229-115">You can use **Get-Job** to get jobs that were started by using the Start-Job cmdlet, or by using the *AsJob* parameter of any cmdlet.</span></span>

<span data-ttu-id="59229-116">Без параметров команда **Get-Job** возвращает все задания в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="59229-116">Without parameters, a **Get-Job** command gets all jobs in the current session.</span></span>
<span data-ttu-id="59229-117">С помощью параметров командлета **Get-Job** можно получить определенные задания.</span><span class="sxs-lookup"><span data-stu-id="59229-117">You can use the parameters of **Get-Job** to get particular jobs.</span></span>

<span data-ttu-id="59229-118">Объект задания, возвращаемый командлетом **Get-Job** , содержит полезную информацию о задании, но не содержит результатов его выполнения.</span><span class="sxs-lookup"><span data-stu-id="59229-118">The job object that **Get-Job** returns contains useful information about the job, but it does not contain the job results.</span></span> <span data-ttu-id="59229-119">Чтобы получить результаты, используйте командлет Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="59229-119">To get the results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="59229-120">Фоновое задание PowerShell — это команда, которая выполняется в фоновом режиме без взаимодействия с текущим сеансом.</span><span class="sxs-lookup"><span data-stu-id="59229-120">A PowerShell background job is a command that runs in the background without interacting with the current session.</span></span> <span data-ttu-id="59229-121">Как правило, для выполнения сложной команды, которая занимает много времени, используется фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="59229-121">Typically, you use a background job to run a complex command that takes a long time to finish.</span></span> <span data-ttu-id="59229-122">Дополнительные сведения о фоновых заданиях в PowerShell см. в разделе about_Jobs.</span><span class="sxs-lookup"><span data-stu-id="59229-122">For more information about background jobs in PowerShell, see about_Jobs.</span></span>

<span data-ttu-id="59229-123">Начиная с выпуска Windows PowerShell 3.0 командлет **Get-Job** также возвращает задания настраиваемых типов, такие как задания рабочих процессов и экземпляры запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="59229-123">Beginning in Windows PowerShell 3.0, the **Get-Job** cmdlet also gets custom job types, such as workflow jobs and instances of scheduled jobs.</span></span> <span data-ttu-id="59229-124">Чтобы определить тип задания, используйте его свойство **PSJobTypeName** .</span><span class="sxs-lookup"><span data-stu-id="59229-124">To find the job type of a job, use the **PSJobTypeName** property of the job.</span></span>

<span data-ttu-id="59229-125">Чтобы включить командлет **Get-Job** для получения настраиваемого типа задания, импортируйте модуль, который поддерживает тип настраиваемого задания, в сеанс перед выполнением команды **get-job** с помощью Import-Moduleого или с помощью или получения командлета в модуле.</span><span class="sxs-lookup"><span data-stu-id="59229-125">To enable **Get-Job** to get a custom job type, import the module that supports the custom job type into the session before you run a **Get-Job** command, either by using the Import-Module cmdlet or by using or getting a cmdlet in the module.</span></span> <span data-ttu-id="59229-126">Дополнительные сведения о определенных пользовательских типах заданий см. в разделе документации о данной функции.</span><span class="sxs-lookup"><span data-stu-id="59229-126">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="59229-127">Примеры</span><span class="sxs-lookup"><span data-stu-id="59229-127">EXAMPLES</span></span>

### <span data-ttu-id="59229-128">Пример 1. получение всех фоновых заданий, запущенных в текущем сеансе</span><span class="sxs-lookup"><span data-stu-id="59229-128">Example 1: Get all background jobs started in the current session</span></span>

```powershell
Get-Job
```

<span data-ttu-id="59229-129">Эта команда возвращает все фоновые задания, запущенные в рамках текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="59229-129">This command gets all background jobs started in the current session.</span></span>
<span data-ttu-id="59229-130">Сюда не включаются задания, созданные в рамках других сеансов, даже если они выполняются на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="59229-130">It does not include jobs created in other sessions, even if the jobs run on the local computer.</span></span>

### <span data-ttu-id="59229-131">Пример 2. завершение задания с помощью идентификатора экземпляра</span><span class="sxs-lookup"><span data-stu-id="59229-131">Example 2: Stop a job by using an instance ID</span></span>

<span data-ttu-id="59229-132">Эти команды показывают, как получить идентификатор экземпляра задания, а затем с его помощью остановить задание.</span><span class="sxs-lookup"><span data-stu-id="59229-132">These commands show how to get the instance ID of a job and then use it to stop a job.</span></span>
<span data-ttu-id="59229-133">В отличие от имени задания, идентификатор экземпляра уникален.</span><span class="sxs-lookup"><span data-stu-id="59229-133">Unlike the name of a job, which is not unique, the instance ID is unique.</span></span>

```powershell
$j = Get-Job -Name Job1
$ID = $j.InstanceID
$ID
```

```Output
Guid
----
03c3232e-1d23-453b-a6f4-ed73c9e29d55
```

```powershell
Stop-Job -InstanceId $ID
```

<span data-ttu-id="59229-134">В первой команде используется командлет **Get-Job** для получения задания.</span><span class="sxs-lookup"><span data-stu-id="59229-134">The first command uses the **Get-Job** cmdlet to get a job.</span></span> <span data-ttu-id="59229-135">Для обнаружения задания используется параметр *Name* .</span><span class="sxs-lookup"><span data-stu-id="59229-135">It uses the *Name* parameter to identify the job.</span></span> <span data-ttu-id="59229-136">Объект задания, который возвращает командлет **Get-Job** , сохраняется в переменной $j.</span><span class="sxs-lookup"><span data-stu-id="59229-136">The command stores the job object that **Get-Job** returns in the $j variable.</span></span> <span data-ttu-id="59229-137">В этом примере имеется только одно задание с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="59229-137">In this example, there is only one job with the specified name.</span></span>

<span data-ttu-id="59229-138">Вторая команда возвращает свойство **InstanceId** объекта в переменной $j и сохраняет его в переменной $ID.</span><span class="sxs-lookup"><span data-stu-id="59229-138">The second command gets the **InstanceId** property of the object in the $j variable and stores it in the $ID variable.</span></span>

<span data-ttu-id="59229-139">Третья команда выводит значение переменной $ID.</span><span class="sxs-lookup"><span data-stu-id="59229-139">The third command displays the value of the $ID variable.</span></span>

<span data-ttu-id="59229-140">Четвертая команда использует командлет Stop-Job для завершения задания.</span><span class="sxs-lookup"><span data-stu-id="59229-140">The fourth command uses Stop-Job cmdlet to stop the job.</span></span> <span data-ttu-id="59229-141">Параметр *InstanceId* определяет задание, а переменная $ID содержит идентификатор экземпляра задания.</span><span class="sxs-lookup"><span data-stu-id="59229-141">It uses the *InstanceId* parameter to identify the job and $ID variable to represent the instance ID of the job.</span></span>

### <span data-ttu-id="59229-142">Пример 3. получение заданий, включающих определенную команду</span><span class="sxs-lookup"><span data-stu-id="59229-142">Example 3: Get jobs that include a specific command</span></span>

```powershell
Get-Job -Command "*get-process*"
```

<span data-ttu-id="59229-143">Эта команда возвращает задания в системе, которые содержат команду Get-Process.</span><span class="sxs-lookup"><span data-stu-id="59229-143">This command gets the jobs on the system that include a Get-Process command.</span></span> <span data-ttu-id="59229-144">В ней используется параметр *Command* командлета **Get-Job** для ограничения получаемых заданий.</span><span class="sxs-lookup"><span data-stu-id="59229-144">The command uses the *Command* parameter of **Get-Job** to limit the jobs retrieved.</span></span> <span data-ttu-id="59229-145">Команда использует подстановочные знаки (\*) для получения заданий, включающих команду **Get-Process** в любом месте командной строки.</span><span class="sxs-lookup"><span data-stu-id="59229-145">The command uses wildcard characters (\*) to get jobs that include a **Get-Process** command anywhere in the command string.</span></span>

### <span data-ttu-id="59229-146">Пример 4. получение заданий, включающих определенную команду, с помощью конвейера</span><span class="sxs-lookup"><span data-stu-id="59229-146">Example 4: Get jobs that include a specific command by using the pipeline</span></span>

```powershell
"*get-process*" | Get-Job
```

<span data-ttu-id="59229-147">Как и команда в предыдущем примере, эта команда возвращает задания в системе, которые включают команду **Get-Process** .</span><span class="sxs-lookup"><span data-stu-id="59229-147">Like the command in the previous example, this command gets the jobs on the system that include a **Get-Process** command.</span></span> <span data-ttu-id="59229-148">Команда использует оператор конвейера (|) для отправки строки в кавычках командлету **Get-Job** .</span><span class="sxs-lookup"><span data-stu-id="59229-148">The command uses a pipeline operator (|) to send a string, in quotation marks, to the **Get-Job** cmdlet.</span></span> <span data-ttu-id="59229-149">Это равносильно предыдущей команде.</span><span class="sxs-lookup"><span data-stu-id="59229-149">It is the equivalent of the previous command.</span></span>

### <span data-ttu-id="59229-150">Пример 5. получение заданий, которые не были запущены</span><span class="sxs-lookup"><span data-stu-id="59229-150">Example 5: Get jobs that have not been started</span></span>

```powershell
Get-Job -State NotStarted
```

<span data-ttu-id="59229-151">Эта команда возвращает только те задания, которые созданы, но еще не запущены.</span><span class="sxs-lookup"><span data-stu-id="59229-151">This command gets only those jobs that have been created but have not yet been started.</span></span>
<span data-ttu-id="59229-152">Сюда входят задания, запланированные к выполнению в будущем, и задания, выполнение которых еще не запланировано.</span><span class="sxs-lookup"><span data-stu-id="59229-152">This includes jobs that are scheduled to run in the future and those not yet scheduled.</span></span>

### <span data-ttu-id="59229-153">Пример 6. получение заданий, которым не было назначено имя</span><span class="sxs-lookup"><span data-stu-id="59229-153">Example 6: Get jobs that have not been assigned a name</span></span>

```powershell
Get-Job -Name Job*
```

<span data-ttu-id="59229-154">Эта команда возвращает все задания с именами заданий, которые начинаются с Job.</span><span class="sxs-lookup"><span data-stu-id="59229-154">This command gets all jobs that have job names that begin with job.</span></span>
<span data-ttu-id="59229-155">Так как задание \<number\> является именем задания по умолчанию, эта команда возвращает все задания, которым не назначено явное имя.</span><span class="sxs-lookup"><span data-stu-id="59229-155">Because job\<number\> is the default name for a job, this command gets all jobs that do not have an explicitly assigned name.</span></span>

### <span data-ttu-id="59229-156">Пример 7. Использование объекта задания для представления задания в команде</span><span class="sxs-lookup"><span data-stu-id="59229-156">Example 7: Use a job object to represent the job in a command</span></span>

<span data-ttu-id="59229-157">В этом примере показано, как использовать командлет **Get-Job** для получения объекта задания и как затем использовать этот объект для представления задания в команде.</span><span class="sxs-lookup"><span data-stu-id="59229-157">This example shows how to use **Get-Job** to get a job object, and then it shows how to use the job object to represent the job in a command.</span></span>

```powershell
Start-Job -ScriptBlock {Get-Process} -Name MyJob
$j = Get-Job -Name MyJob
$j
```

```Output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
6      MyJob           BackgroundJob   Completed     True            localhost            Get-Process
```

```powershell
Receive-Job -Job $j
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    124       4    13572      12080    59            1140 audiodg
    783      16    11428      13636   100             548 CcmExec
     96       4     4252       3764    59            3856 ccmsetup
...
```

<span data-ttu-id="59229-158">Первая команда использует командлет **Start-Job** для запуска фонового задания, запускающего команду **Get-Process** на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="59229-158">The first command uses the **Start-Job** cmdlet to start a background job that runs a **Get-Process** command on the local computer.</span></span> <span data-ttu-id="59229-159">С помощью параметра *Name* командлета **Start-Job** заданию присваивается понятное имя.</span><span class="sxs-lookup"><span data-stu-id="59229-159">The command uses the *Name* parameter of **Start-Job** to assign a friendly name to the job.</span></span>

<span data-ttu-id="59229-160">Во второй команде используется командлет Get-Job для получения задания.</span><span class="sxs-lookup"><span data-stu-id="59229-160">The second command uses Get-Job to get the job.</span></span> <span data-ttu-id="59229-161">Задание определяется с помощью параметра *Name* командлета **Get-Job** .</span><span class="sxs-lookup"><span data-stu-id="59229-161">It uses the *Name* parameter of **Get-Job** to identify the job.</span></span> <span data-ttu-id="59229-162">Полученный объект задания сохраняется в переменную $j.</span><span class="sxs-lookup"><span data-stu-id="59229-162">The command saves the resulting job object in the $j variable.</span></span>

<span data-ttu-id="59229-163">Третья команда выводит значение объекта задания в переменной $j.</span><span class="sxs-lookup"><span data-stu-id="59229-163">The third command displays the value of the job object in the $j variable.</span></span> <span data-ttu-id="59229-164">Значение свойства **State** показывает, что задание завершено.</span><span class="sxs-lookup"><span data-stu-id="59229-164">The value of the **State** property shows that the job is completed.</span></span> <span data-ttu-id="59229-165">Значение свойства **HasMoreData** показывает, что есть результаты задания, которые еще не были получены.</span><span class="sxs-lookup"><span data-stu-id="59229-165">The value of the **HasMoreData** property shows that there are results available from the job that have not yet been retrieved.</span></span>

<span data-ttu-id="59229-166">Четвертая команда использует командлет **Receive-Job** для получения результатов задания.</span><span class="sxs-lookup"><span data-stu-id="59229-166">The fourth command uses the **Receive-Job** cmdlet to get the results of the job.</span></span> <span data-ttu-id="59229-167">Объект задания в переменной $j представляет задание.</span><span class="sxs-lookup"><span data-stu-id="59229-167">It uses the job object in the $j variable to represent the job.</span></span> <span data-ttu-id="59229-168">Можно также использовать оператор конвейера для отправки объекта задания в **Receive-Job** .</span><span class="sxs-lookup"><span data-stu-id="59229-168">You can also use a pipeline operator to send a job object to **Receive-Job** .</span></span>

### <span data-ttu-id="59229-169">Пример 8. получение всех заданий, включая задания, запущенные другим методом</span><span class="sxs-lookup"><span data-stu-id="59229-169">Example 8: Get all jobs including jobs started by a different method</span></span>

<span data-ttu-id="59229-170">В этом примере показано, что командлет **Get-Job** может получить все задания, запущенные в текущем сеансе, даже если они были запущены с помощью различных методов.</span><span class="sxs-lookup"><span data-stu-id="59229-170">This example demonstrates that the **Get-Job** cmdlet can get all of the jobs that were started in the current session, even if they were started by using different methods.</span></span>

```powershell
Start-Job -ScriptBlock {Get-EventLog System}
Invoke-Command -ComputerName S1 -ScriptBlock {Get-EventLog System} -AsJob
Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Get-Job
```

```Output
Id     Name       PSJobTypeName   State         HasMoreData     Location        Command
--     ----       -------------   -----         -----------     --------        -------
1      Job1       BackgroundJob   Running       True            localhost       Get-EventLog System
2      Job2       RemoteJob       Running       True            S1              Get-EventLog System
```

```powershell
Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
```

```Output
Id    Name     PSJobTypeName  State      HasMoreData   Location   Command
--    ----     -------------  -----      -----------   -------    -------
4     Job4     BackgroundJob  Running    True          localhost  Get-Eventlog System
```

<span data-ttu-id="59229-171">Первая команда использует командлет **Start-Job** для запуска задания на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="59229-171">The first command uses the **Start-Job** cmdlet to start a job on the local computer.</span></span>

<span data-ttu-id="59229-172">Вторая команда использует параметр *AsJob* командлета **Invoke-Command** для запуска задания на компьютере S1.</span><span class="sxs-lookup"><span data-stu-id="59229-172">The second command uses the *AsJob* parameter of the **Invoke-Command** cmdlet to start a job on the S1 computer.</span></span> <span data-ttu-id="59229-173">Хотя команды задания выполняются на удаленном компьютере, объект задания создается на локальном, поэтому вы можете управлять заданием с помощью локальных команд.</span><span class="sxs-lookup"><span data-stu-id="59229-173">Even though the commands in the job run on the remote computer, the job object is created on the local computer, so you use local commands to manage the job.</span></span>

<span data-ttu-id="59229-174">В третьей команде используется командлет **Invoke-Command** для выполнения команды **Start-Job** на компьютере S2.</span><span class="sxs-lookup"><span data-stu-id="59229-174">The third command uses the **Invoke-Command** cmdlet to run a **Start-Job** command on the S2 computer.</span></span> <span data-ttu-id="59229-175">При использовании этого метода объект задания создается на удаленном компьютере, поэтому для управления заданием используются удаленные команды.</span><span class="sxs-lookup"><span data-stu-id="59229-175">By using this method, the job object is created on the remote computer, so you use remote commands to manage the job.</span></span>

<span data-ttu-id="59229-176">В четвертой команде используется командлет **Get-Job** для получения заданий, сохраненных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="59229-176">The fourth command uses **Get-Job** to get the jobs stored on the local computer.</span></span> <span data-ttu-id="59229-177">Свойство **псжобтипенаме** заданий, представленное в Windows PowerShell 3,0, показывает, что локальное задание, запущенное с помощью командлета **Start-Job** , является фоновым заданием и заданием, запущенным в удаленном сеансе с помощью командлета **Invoke-Command** , является удаленное задание.</span><span class="sxs-lookup"><span data-stu-id="59229-177">The **PSJobTypeName** property of jobs, introduced in Windows PowerShell 3.0, shows that the local job started by using the **Start-Job** cmdlet is a background job and the job started in a remote session by using the **Invoke-Command** cmdlet is a remote job.</span></span>

<span data-ttu-id="59229-178">Пятая команда использует **командлет Invoke-Command** для выполнения команды **Get-Job** на компьютере S2. В выходных данных примера показаны результаты выполнения команды Get-Job.</span><span class="sxs-lookup"><span data-stu-id="59229-178">The fifth command uses **Invoke-Command** to run a **Get-Job** command on the S2 computer.The sample output shows the results of the Get-Job command.</span></span> <span data-ttu-id="59229-179">На компьютере S2 задание отображается как локальное.</span><span class="sxs-lookup"><span data-stu-id="59229-179">On the S2 computer, the job appears to be a local job.</span></span> <span data-ttu-id="59229-180">Имя компьютера — localhost, а тип задания — фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="59229-180">The computer name is localhost and the job type is a background job.</span></span>

<span data-ttu-id="59229-181">Дополнительные сведения о выполнении фоновых заданий на удаленных компьютерах см. в разделе about_Remote_Jobs.</span><span class="sxs-lookup"><span data-stu-id="59229-181">For more information about how to run background jobs on remote computers, see about_Remote_Jobs.</span></span>

### <span data-ttu-id="59229-182">Пример 9. исследование невыполненного задания</span><span class="sxs-lookup"><span data-stu-id="59229-182">Example 9: Investigate a failed job</span></span>

```powershell
Start-Job -ScriptBlock {Get-Process}
```

```Output
Id     Name       PSJobTypeName   State       HasMoreData     Location             Command
--     ----       -------------   -----       -----------     --------             -------
1      Job1       BackgroundJob   Failed      False           localhost            Get-Process
```

```powershell
(Get-Job).JobStateInfo | Format-List -Property *
```

```Output
State  : Failed
Reason :
```

```powershell
Get-Job | Format-List -Property *
```

```Output
HasMoreData   : False
StatusMessage :
Location      : localhost
Command       : get-process
JobStateInfo  : Failed
Finished      : System.Threading.ManualReset
EventInstanceId    : fb792295-1318-4f5d-8ac8-8a89c5261507
Id            : 1
Name          : Job1
ChildJobs     : {Job2}
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
StateChanged  :
```

```powershell
(Get-Job -Name job2).JobStateInfo.Reason
```

```Output
Connecting to remote server using WSManCreateShellEx api failed. The async callback gave the following error message: Access is denied.

For information about requirements for remoting in PowerShell, see about_Remote_Requirements. For
troubleshooting tips, see about_Remote_Troubleshooting.
```

<span data-ttu-id="59229-183">Эта команда показывает, как использовать объект задания, возвращаемый командлетом **Get-Job** , чтобы выяснить причину сбоя задания.</span><span class="sxs-lookup"><span data-stu-id="59229-183">This command shows how to use the job object that **Get-Job** returns to investigate why a job failed.</span></span>
<span data-ttu-id="59229-184">Она также показывает, как получить дочерние задания каждого задания.</span><span class="sxs-lookup"><span data-stu-id="59229-184">It also shows how to get the child jobs of each job.</span></span>

<span data-ttu-id="59229-185">Первая команда использует командлет **Start-Job** для запуска задания на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="59229-185">The first command uses the **Start-Job** cmdlet to start a job on the local computer.</span></span> <span data-ttu-id="59229-186">Объект задания, который возвращает командлет **Start-Job** , показывает, что задание завершилось сбоем.</span><span class="sxs-lookup"><span data-stu-id="59229-186">The job object that **Start-Job** returns shows that the job failed.</span></span> <span data-ttu-id="59229-187">Значение свойства **State** не выполнено.</span><span class="sxs-lookup"><span data-stu-id="59229-187">The value of the **State** property is Failed.</span></span>

<span data-ttu-id="59229-188">Во второй команде используется командлет **Get-Job** для получения задания.</span><span class="sxs-lookup"><span data-stu-id="59229-188">The second command uses the **Get-Job** cmdlet to get the job.</span></span> <span data-ttu-id="59229-189">С помощью точечной нотации извлекается значение свойства **JobStateInfo** объекта.</span><span class="sxs-lookup"><span data-stu-id="59229-189">The command uses the dot method to get the value of the **JobStateInfo** property of the object.</span></span> <span data-ttu-id="59229-190">Он использует оператор конвейера для отправки объекта из свойства **JobStateInfo** в командлет Format-List, который форматирует все свойства объекта (\*) в списке. Результат выполнения команды **Format-List** показывает, что значение свойства **Reason** задания пусто.</span><span class="sxs-lookup"><span data-stu-id="59229-190">It uses a pipeline operator to send the object in the **JobStateInfo** property to the Format-List cmdlet, which formats all of the properties of the object (\*) in a list.The result of the **Format-List** command shows that the value of the **Reason** property of the job is blank.</span></span>

<span data-ttu-id="59229-191">Третья команда изучает дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="59229-191">The third command investigates more.</span></span> <span data-ttu-id="59229-192">Он использует команду **Get-Job** для получения задания, а затем использует оператор конвейера для отправки всего объекта задания в командлет **Format-List** , который отображает все свойства задания в списке. Отображение всех свойств в объекте задания показывает, что задание содержит дочернее задание с именем Job2.</span><span class="sxs-lookup"><span data-stu-id="59229-192">It uses a **Get-Job** command to get the job and then uses a pipeline operator to send the whole job object to the **Format-List** cmdlet, which displays all of the properties of the job in a list.The display of all properties in the job object shows that the job contains a child job named Job2.</span></span>

<span data-ttu-id="59229-193">В четвертой команде используется командлет **Get-Job** для получения объекта задания, который представляет дочернее задание Job2.</span><span class="sxs-lookup"><span data-stu-id="59229-193">The fourth command uses **Get-Job** to get the job object that represents the Job2 child job.</span></span> <span data-ttu-id="59229-194">Это задание, в котором на самом деле выполнялась команда.</span><span class="sxs-lookup"><span data-stu-id="59229-194">This is the job in which the command actually ran.</span></span> <span data-ttu-id="59229-195">Он использует метод Dot для получения свойства **Reason** свойства **JobStateInfo** . Результат показывает, что задание завершилось сбоем из-за ошибки отказа в доступе.</span><span class="sxs-lookup"><span data-stu-id="59229-195">It uses the dot method to get the **Reason** property of the **JobStateInfo** property.The result shows that the job failed because of an Access Denied error.</span></span> <span data-ttu-id="59229-196">В этом случае пользователь забыл использовать параметр Запуск от имени администратора при запуске PowerShell. Поскольку фоновые задания используют функции удаленного взаимодействия PowerShell, компьютер должен быть настроен для запуска задания, даже если задание выполняется на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="59229-196">In this case, the user forgot to use the Run as administrator option when starting PowerShell.Because background jobs use the remoting features of PowerShell, the computer must be configured for remoting to run a job, even when the job runs on the local computer.</span></span>

### <span data-ttu-id="59229-197">Пример 10. получение отфильтрованных результатов</span><span class="sxs-lookup"><span data-stu-id="59229-197">Example 10: Get filtered results</span></span>

<span data-ttu-id="59229-198">В этом примере показано, как использовать параметр *Filter* для получения задания рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="59229-198">This example shows how to use the *Filter* parameter to get a workflow job.</span></span>
<span data-ttu-id="59229-199">Параметр *Filter* , появившийся в Windows PowerShell 3.0, действует только применительно к заданиям настраиваемых типов, таким как задания рабочих процессов и запланированные задания.</span><span class="sxs-lookup"><span data-stu-id="59229-199">The *Filter* parameter, introduced in Windows PowerShell 3.0 is valid only on custom job types, such as workflow jobs and scheduled jobs.</span></span>

```powershell
Workflow WFProcess {Get-Process}
WFProcess -AsJob -JobName WFProcessJob -PSPrivateMetadata @{MyCustomId = 92107}
Get-Job -Filter @{MyCustomId = 92107}
```

```Output
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
1      WFProcessJob    Completed     True            localhost            WFProcess
```

<span data-ttu-id="59229-200">Первая команда использует ключевое слово **рабочего процесса** для создания рабочего процесса вфпроцесс.</span><span class="sxs-lookup"><span data-stu-id="59229-200">The first command uses the **Workflow** keyword to create the WFProcess workflow.</span></span>

<span data-ttu-id="59229-201">Вторая команда использует параметр *AsJob* рабочего процесса вфпроцесс для запуска рабочего процесса в качестве фонового задания.</span><span class="sxs-lookup"><span data-stu-id="59229-201">The second command uses the *AsJob* parameter of the WFProcess workflow to run the workflow as a background job.</span></span> <span data-ttu-id="59229-202">Параметр *JobName* рабочего процесса используется для указания имени задания, а параметр *PSPrivateMetadata* рабочего процесса — для указания настраиваемого идентификатора.</span><span class="sxs-lookup"><span data-stu-id="59229-202">It uses the *JobName* parameter of the workflow to specify a name for the job, and the *PSPrivateMetadata* parameter of the workflow to specify a custom ID.</span></span>

<span data-ttu-id="59229-203">В третьей команде используется параметр *Filter* командлета **Get-Job** для получения задания по настраиваемому идентификатору, который был указан в параметре *PSPrivateMetadata* .</span><span class="sxs-lookup"><span data-stu-id="59229-203">The third command uses the *Filter* parameter of **Get-Job** to get the job by custom ID that was specified in the *PSPrivateMetadata* parameter.</span></span>

### <span data-ttu-id="59229-204">Пример 11. Получение сведений о дочерних заданиях</span><span class="sxs-lookup"><span data-stu-id="59229-204">Example 11: Get information about child jobs</span></span>

<span data-ttu-id="59229-205">В этом примере показан результат использования параметров *IncludeChildJob* и *ChildJobState* командлета **Get-Job** .</span><span class="sxs-lookup"><span data-stu-id="59229-205">This example shows the effect of using the *IncludeChildJob* and *ChildJobState* parameters of the **Get-Job** cmdlet.</span></span>

```powershell
Get-Job
```

```Output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost            .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02   .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
```

```powershell
Get-Job -IncludeChildJob
```

```Output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost           .\Get-Archive.ps1
3      Job3                            Completed     True            localhost           .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02  .\Get-Archive.ps1
5      Job5                            Failed        False           Server01            .\Get-Archive.ps1
6      Job6                            Completed     True            Server02            .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
```

```powershell
Get-Job -Name Job4 -ChildJobState Failed
```

```Output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost           .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02  .\Get-Archive.ps1
5      Job5                            Failed        False           Server01            .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
```

```powershell
(Get-Job -Name Job5).JobStateInfo.Reason
```

```Output
Connecting to remote server Server01 failed with the following error message:
Access is denied.
For more information, see the about_Remote_Troubleshooting Help topic.
```

<span data-ttu-id="59229-206">Первая команда возвращает задания в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="59229-206">The first command gets the jobs in the current session.</span></span> <span data-ttu-id="59229-207">Выходные данные включают в себя фоновое задание, удаленное задание и несколько экземпляров запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="59229-207">The output includes a background job, a remote job and several instances of a scheduled job.</span></span> <span data-ttu-id="59229-208">Удаленное задание Job4, по-видимому, завершилось сбоем.</span><span class="sxs-lookup"><span data-stu-id="59229-208">The remote job, Job4, appears to have failed.</span></span>

<span data-ttu-id="59229-209">Во второй команде используется параметр *IncludeChildJob* командлета **Get-Job** .</span><span class="sxs-lookup"><span data-stu-id="59229-209">The second command uses the *IncludeChildJob* parameter of **Get-Job** .</span></span> <span data-ttu-id="59229-210">Выходные данные добавляют дочерние задания всех заданий, имеющих дочерние задания. В этом случае измененные выходные данные показывают, что не удалось выполнить дочернее задание Job5 в Job4.</span><span class="sxs-lookup"><span data-stu-id="59229-210">The output adds the child jobs of all jobs that have child jobs.In this case, the revised output shows that only the Job5 child job of Job4 failed.</span></span>

<span data-ttu-id="59229-211">Третья команда использует параметр *чилджобстате* со значением Failed. выходные данные включают все родительские задания и только дочерние задания, для которых произошел сбой.</span><span class="sxs-lookup"><span data-stu-id="59229-211">The third command uses the *ChildJobState* parameter with a value of Failed.The output includes all parent jobs and only the child jobs that failed.</span></span>

<span data-ttu-id="59229-212">Четвертая команда использует свойство **JobStateInfo** заданий и свойство **Reason** для выяснения причины сбоя Job5.</span><span class="sxs-lookup"><span data-stu-id="59229-212">The fourth command uses the **JobStateInfo** property of jobs and its **Reason** property to discover why Job5 failed.</span></span>

## <span data-ttu-id="59229-213">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="59229-213">PARAMETERS</span></span>

### <span data-ttu-id="59229-214">-After</span><span class="sxs-lookup"><span data-stu-id="59229-214">-After</span></span>

<span data-ttu-id="59229-215">Возвращает выполненные задания, которые завершились после указанных даты и времени.</span><span class="sxs-lookup"><span data-stu-id="59229-215">Gets completed jobs that ended after the specified date and time.</span></span> <span data-ttu-id="59229-216">Введите объект **DateTime** , например, возвращаемый командлетом Get-Date, или строку, которую можно преобразовать в объект **DateTime** , например `Dec 1, 2012 2:00 AM` или `11/06` .</span><span class="sxs-lookup"><span data-stu-id="59229-216">Enter a **DateTime** object, such as one returned by the Get-Date cmdlet or a string that can be converted to a **DateTime** object, such as `Dec 1, 2012 2:00 AM` or `11/06`.</span></span>

<span data-ttu-id="59229-217">Этот параметр применим только к заданиям настраиваемых типов, таким как задания рабочих процессов и запланированные задания, имеющим свойство **EndTime** .</span><span class="sxs-lookup"><span data-stu-id="59229-217">This parameter works only on custom job types, such as workflow jobs and scheduled jobs, that have an **EndTime** property.</span></span> <span data-ttu-id="59229-218">Он не работает со стандартными фоновыми заданиями, такими как созданные с помощью командлета **Start-Job** .</span><span class="sxs-lookup"><span data-stu-id="59229-218">It does not work on standard background jobs, such as those created by using the **Start-Job** cmdlet.</span></span> <span data-ttu-id="59229-219">Дополнительные сведения о поддержке данного параметра см. в разделе справки о соответствующем типе заданий.</span><span class="sxs-lookup"><span data-stu-id="59229-219">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="59229-220">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="59229-220">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59229-221">— До</span><span class="sxs-lookup"><span data-stu-id="59229-221">-Before</span></span>

<span data-ttu-id="59229-222">Возвращает выполненные задания, которые завершились до указанных даты и времени.</span><span class="sxs-lookup"><span data-stu-id="59229-222">Gets completed jobs that ended before the specified date and time.</span></span>
<span data-ttu-id="59229-223">Введите объект **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="59229-223">Enter a **DateTime** object.</span></span>

<span data-ttu-id="59229-224">Этот параметр применим только к заданиям настраиваемых типов, таким как задания рабочих процессов и запланированные задания, имеющим свойство **EndTime** .</span><span class="sxs-lookup"><span data-stu-id="59229-224">This parameter works only on custom job types, such as workflow jobs and scheduled jobs, that have an **EndTime** property.</span></span> <span data-ttu-id="59229-225">Он не работает со стандартными фоновыми заданиями, такими как созданные с помощью командлета **Start-Job** .</span><span class="sxs-lookup"><span data-stu-id="59229-225">It does not work on standard background jobs, such as those created by using the **Start-Job** cmdlet.</span></span> <span data-ttu-id="59229-226">Дополнительные сведения о поддержке данного параметра см. в разделе справки о соответствующем типе заданий.</span><span class="sxs-lookup"><span data-stu-id="59229-226">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="59229-227">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="59229-227">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59229-228">-Чилджобстате</span><span class="sxs-lookup"><span data-stu-id="59229-228">-ChildJobState</span></span>

<span data-ttu-id="59229-229">Возвращает только те дочерние задания, которые находятся в указанном состоянии.</span><span class="sxs-lookup"><span data-stu-id="59229-229">Gets only the child jobs that have the specified state.</span></span>
<span data-ttu-id="59229-230">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="59229-230">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="59229-231">NotStarted</span><span class="sxs-lookup"><span data-stu-id="59229-231">NotStarted</span></span>
- <span data-ttu-id="59229-232">Запущен</span><span class="sxs-lookup"><span data-stu-id="59229-232">Running</span></span>
- <span data-ttu-id="59229-233">Завершено</span><span class="sxs-lookup"><span data-stu-id="59229-233">Completed</span></span>
- <span data-ttu-id="59229-234">Ошибка</span><span class="sxs-lookup"><span data-stu-id="59229-234">Failed</span></span>
- <span data-ttu-id="59229-235">Остановлена</span><span class="sxs-lookup"><span data-stu-id="59229-235">Stopped</span></span>
- <span data-ttu-id="59229-236">Блокировано</span><span class="sxs-lookup"><span data-stu-id="59229-236">Blocked</span></span>
- <span data-ttu-id="59229-237">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="59229-237">Suspended</span></span>
- <span data-ttu-id="59229-238">Отключено</span><span class="sxs-lookup"><span data-stu-id="59229-238">Disconnected</span></span>
- <span data-ttu-id="59229-239">Приостановка</span><span class="sxs-lookup"><span data-stu-id="59229-239">Suspending</span></span>
- <span data-ttu-id="59229-240">Остановка</span><span class="sxs-lookup"><span data-stu-id="59229-240">Stopping</span></span>

<span data-ttu-id="59229-241">По умолчанию командлет **Get-Job** не возвращает дочерние задания.</span><span class="sxs-lookup"><span data-stu-id="59229-241">By default, **Get-Job** does not get child jobs.</span></span>
<span data-ttu-id="59229-242">С помощью параметра *инклудечилджоб* командлет **Get-Job** получает все дочерние задания.</span><span class="sxs-lookup"><span data-stu-id="59229-242">By using the *IncludeChildJob* parameter, **Get-Job** gets all child jobs.</span></span>
<span data-ttu-id="59229-243">При использовании параметра *ChildJobState* параметр *IncludeChildJob* не действует.</span><span class="sxs-lookup"><span data-stu-id="59229-243">If you use the *ChildJobState* parameter, the *IncludeChildJob* parameter has no effect.</span></span>

<span data-ttu-id="59229-244">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="59229-244">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59229-245">-Command</span><span class="sxs-lookup"><span data-stu-id="59229-245">-Command</span></span>

<span data-ttu-id="59229-246">Указывает массив команд в виде строк.</span><span class="sxs-lookup"><span data-stu-id="59229-246">Specifies an array of commands as strings.</span></span>
<span data-ttu-id="59229-247">Этот командлет возвращает задания, включающие указанные команды.</span><span class="sxs-lookup"><span data-stu-id="59229-247">This cmdlet gets the jobs that include the specified commands.</span></span>
<span data-ttu-id="59229-248">По умолчанию останавливаются все задания.</span><span class="sxs-lookup"><span data-stu-id="59229-248">The default is all jobs.</span></span>
<span data-ttu-id="59229-249">Для указания шаблона команды можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="59229-249">You can use wildcard characters to specify a command pattern.</span></span>

```yaml
Type: System.String[]
Parameter Sets: CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="59229-250">-Filter</span><span class="sxs-lookup"><span data-stu-id="59229-250">-Filter</span></span>

<span data-ttu-id="59229-251">Указывает хэш-таблицу условий.</span><span class="sxs-lookup"><span data-stu-id="59229-251">Specifies a hash table of conditions.</span></span>
<span data-ttu-id="59229-252">Этот командлет возвращает задания, которые отвечают всем условиям.</span><span class="sxs-lookup"><span data-stu-id="59229-252">This cmdlet gets jobs that satisfy all of the conditions.</span></span>
<span data-ttu-id="59229-253">Введите хэш-таблицу, где ключи являются свойствами заданий, а значения — значениями этих свойств.</span><span class="sxs-lookup"><span data-stu-id="59229-253">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="59229-254">Этот параметр работает только с пользовательскими типами заданий, такими как задания рабочих процессов и запланированные задания.</span><span class="sxs-lookup"><span data-stu-id="59229-254">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span>
<span data-ttu-id="59229-255">Он не работает со стандартными фоновыми заданиями, такими как созданные с помощью командлета **Start-Job** .</span><span class="sxs-lookup"><span data-stu-id="59229-255">It does not work on standard background jobs, such as those created by using the **Start-Job** cmdlet.</span></span>
<span data-ttu-id="59229-256">Дополнительные сведения о поддержке данного параметра см. в разделе справки о соответствующем типе заданий.</span><span class="sxs-lookup"><span data-stu-id="59229-256">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="59229-257">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="59229-257">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: FilterParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="59229-258">-Хасморедата</span><span class="sxs-lookup"><span data-stu-id="59229-258">-HasMoreData</span></span>

<span data-ttu-id="59229-259">Указывает, получает ли этот командлет только задания с указанным значением свойства **хасморедата** .</span><span class="sxs-lookup"><span data-stu-id="59229-259">Indicates whether this cmdlet gets only jobs that have the specified **HasMoreData** property value.</span></span>
<span data-ttu-id="59229-260">Свойство **HasMoreData** указывает, были ли все результаты задания получены в рамках текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="59229-260">The **HasMoreData** property indicates whether all job results have been received in the current session.</span></span>
<span data-ttu-id="59229-261">Чтобы получить задания с дополнительными результатами, укажите значение $True.</span><span class="sxs-lookup"><span data-stu-id="59229-261">To get jobs that have more results, specify a value of $True.</span></span>
<span data-ttu-id="59229-262">Чтобы получить задания, которые не имеют дополнительных результатов, укажите значение $False.</span><span class="sxs-lookup"><span data-stu-id="59229-262">To get jobs that do not have more results, specify a value of $False.</span></span>

<span data-ttu-id="59229-263">Чтобы получить результаты задания, используйте командлет Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="59229-263">To get the results of a job, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="59229-264">При использовании командлета **Receive-Job** он удаляет из его хранилища возвращаемые результаты.</span><span class="sxs-lookup"><span data-stu-id="59229-264">When you use the **Receive-Job** cmdlet, it deletes from its in-memory, session-specific storage the results that it returned.</span></span> <span data-ttu-id="59229-265">Когда он возвращает все результаты задания в текущем сеансе, он устанавливает для свойства **хасморедата** задания значение $false), чтобы указать, что он больше не имеет результатов для задания в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="59229-265">When it has returned all results of the job in the current session, it sets the value of the **HasMoreData** property of the job to $False) to indicate that it has no more results for the job in the current session.</span></span> <span data-ttu-id="59229-266">Чтобы запретить командлету *Receive-Job* удалять результаты и изменять значение свойства **HasMoreData** , используйте параметр **Keep** командлета **Receive-Job** .</span><span class="sxs-lookup"><span data-stu-id="59229-266">Use the *Keep* parameter of **Receive-Job** to prevent **Receive-Job** from deleting results and changing the value of the **HasMoreData** property.</span></span> <span data-ttu-id="59229-267">Для получения дополнительных сведений введите `Get-Help Receive-Job`.</span><span class="sxs-lookup"><span data-stu-id="59229-267">For more information, type `Get-Help Receive-Job`.</span></span>

<span data-ttu-id="59229-268">Свойство **HasMoreData** относится к текущему сеансу.</span><span class="sxs-lookup"><span data-stu-id="59229-268">The **HasMoreData** property is specific to the current session.</span></span> <span data-ttu-id="59229-269">Если результаты для пользовательского типа задания сохраняются за пределами сеанса, например тип запланированного задания, который сохраняет результаты задания на диске, можно использовать командлет **Receive-Job** в другом сеансе для повторного получения результатов задания, даже если значение **хасморедата** равно $false.</span><span class="sxs-lookup"><span data-stu-id="59229-269">If results for a custom job type are saved outside of the session, such as the scheduled job type, which saves job results on disk, you can use the **Receive-Job** cmdlet in a different session to get the job results again, even if the value of **HasMoreData** is $False.</span></span> <span data-ttu-id="59229-270">Подробнее см. в разделах справки по настраиваемому типу задания.</span><span class="sxs-lookup"><span data-stu-id="59229-270">For more information, see the help topics for the custom job type.</span></span>

<span data-ttu-id="59229-271">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="59229-271">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Boolean
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59229-272">-Id</span><span class="sxs-lookup"><span data-stu-id="59229-272">-Id</span></span>

<span data-ttu-id="59229-273">Указывает массив идентификаторов заданий, которые получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="59229-273">Specifies an array of IDs of jobs that this cmdlet gets.</span></span>

<span data-ttu-id="59229-274">Идентификатор — это целое число, которое однозначно определяет задание в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="59229-274">The ID is an integer that uniquely identifies the job in the current session.</span></span>
<span data-ttu-id="59229-275">Проще запомнить и ввести, чем идентификатор экземпляра, но он уникален только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="59229-275">It is easier to remember and to type than the instance ID, but it is unique only in the current session.</span></span>
<span data-ttu-id="59229-276">Можно ввести один или несколько идентификаторов, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="59229-276">You can type one or more IDs separated by commas.</span></span>
<span data-ttu-id="59229-277">Чтобы найти идентификатор задания, введите `Get-Job` без параметров.</span><span class="sxs-lookup"><span data-stu-id="59229-277">To find the ID of a job, type `Get-Job` without parameters.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="59229-278">-Инклудечилджоб</span><span class="sxs-lookup"><span data-stu-id="59229-278">-IncludeChildJob</span></span>

<span data-ttu-id="59229-279">Указывает, что этот командлет возвращает дочерние задания в дополнение к родительским заданиям.</span><span class="sxs-lookup"><span data-stu-id="59229-279">Indicates that this cmdlet returns child jobs, in addition to parent jobs.</span></span>

<span data-ttu-id="59229-280">Этот параметр особенно полезен для изучения заданий рабочего процесса, для которых командлет **Get-Job** Возвращает родительское задание контейнера, а также сбои заданий, так как причина сбоя сохраняется в свойстве дочернего задания.</span><span class="sxs-lookup"><span data-stu-id="59229-280">This parameter is especially useful for investigating workflow jobs, for which **Get-Job** returns a container parent job, and job failures, because the reason for the failure is saved in a property of the child job.</span></span>

<span data-ttu-id="59229-281">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="59229-281">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59229-282">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="59229-282">-InstanceId</span></span>

<span data-ttu-id="59229-283">Указывает массив идентификаторов экземпляров заданий, которые получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="59229-283">Specifies an array of instance IDs of jobs that this cmdlet gets.</span></span>
<span data-ttu-id="59229-284">По умолчанию останавливаются все задания.</span><span class="sxs-lookup"><span data-stu-id="59229-284">The default is all jobs.</span></span>

<span data-ttu-id="59229-285">Идентификатор экземпляра — это GUID, который однозначно определяет задание на компьютере.</span><span class="sxs-lookup"><span data-stu-id="59229-285">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span>
<span data-ttu-id="59229-286">Чтобы узнать идентификатор экземпляра задания, используйте командлет **Get-Job** .</span><span class="sxs-lookup"><span data-stu-id="59229-286">To find the instance ID of a job, use **Get-Job** .</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="59229-287">-Name</span><span class="sxs-lookup"><span data-stu-id="59229-287">-Name</span></span>

<span data-ttu-id="59229-288">Указывает массив понятных имен экземпляров заданий, которые получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="59229-288">Specifies an array of instance friendly names of jobs that this cmdlet gets.</span></span>
<span data-ttu-id="59229-289">Введите имя задания или используйте подстановочные знаки для ввода шаблона имени задания.</span><span class="sxs-lookup"><span data-stu-id="59229-289">Enter a job name, or use wildcard characters to enter a job name pattern.</span></span>
<span data-ttu-id="59229-290">По умолчанию командлет **Get-Job** возвращает все задания в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="59229-290">By default, **Get-Job** gets all jobs in the current session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="59229-291">— Самый новый</span><span class="sxs-lookup"><span data-stu-id="59229-291">-Newest</span></span>

<span data-ttu-id="59229-292">Указывает число заданий для получения.</span><span class="sxs-lookup"><span data-stu-id="59229-292">Specifies a number of jobs to get.</span></span>
<span data-ttu-id="59229-293">Этот командлет возвращает задания, которые были завершены недавно.</span><span class="sxs-lookup"><span data-stu-id="59229-293">This cmdlet gets the jobs that ended most recently.</span></span>

<span data-ttu-id="59229-294">Параметр *Newest* не сортирует задания по времени завершения.</span><span class="sxs-lookup"><span data-stu-id="59229-294">The *Newest* parameter does not sort or return the newest jobs in end-time order.</span></span>
<span data-ttu-id="59229-295">Чтобы отсортировать выходные данные, используйте командлет Sort-Object.</span><span class="sxs-lookup"><span data-stu-id="59229-295">To sort the output, use the Sort-Object cmdlet.</span></span>

<span data-ttu-id="59229-296">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="59229-296">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="59229-297">-State</span><span class="sxs-lookup"><span data-stu-id="59229-297">-State</span></span>

<span data-ttu-id="59229-298">Указывает состояние задания.</span><span class="sxs-lookup"><span data-stu-id="59229-298">Specifies a job state.</span></span>
<span data-ttu-id="59229-299">Этот командлет возвращает только задания в указанном состоянии.</span><span class="sxs-lookup"><span data-stu-id="59229-299">This cmdlet gets only jobs in the specified state.</span></span>
<span data-ttu-id="59229-300">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="59229-300">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="59229-301">NotStarted</span><span class="sxs-lookup"><span data-stu-id="59229-301">NotStarted</span></span>
- <span data-ttu-id="59229-302">Запущен</span><span class="sxs-lookup"><span data-stu-id="59229-302">Running</span></span>
- <span data-ttu-id="59229-303">Завершено</span><span class="sxs-lookup"><span data-stu-id="59229-303">Completed</span></span>
- <span data-ttu-id="59229-304">Ошибка</span><span class="sxs-lookup"><span data-stu-id="59229-304">Failed</span></span>
- <span data-ttu-id="59229-305">Остановлена</span><span class="sxs-lookup"><span data-stu-id="59229-305">Stopped</span></span>
- <span data-ttu-id="59229-306">Блокировано</span><span class="sxs-lookup"><span data-stu-id="59229-306">Blocked</span></span>
- <span data-ttu-id="59229-307">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="59229-307">Suspended</span></span>
- <span data-ttu-id="59229-308">Отключено</span><span class="sxs-lookup"><span data-stu-id="59229-308">Disconnected</span></span>
- <span data-ttu-id="59229-309">Приостановка</span><span class="sxs-lookup"><span data-stu-id="59229-309">Suspending</span></span>
- <span data-ttu-id="59229-310">Остановка</span><span class="sxs-lookup"><span data-stu-id="59229-310">Stopping</span></span>

<span data-ttu-id="59229-311">По умолчанию командлет **Get-Job** возвращает все задания в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="59229-311">By default, **Get-Job** gets all the jobs in the current session.</span></span>

<span data-ttu-id="59229-312">Дополнительные сведения о состояниях заданий см. в разделе [перечисление JobState](https://msdn.microsoft.com/library/system.management.automation.jobstate) в библиотеке MSDN.</span><span class="sxs-lookup"><span data-stu-id="59229-312">For more information about job states, see [JobState Enumeration](https://msdn.microsoft.com/library/system.management.automation.jobstate) in the MSDN library.</span></span>

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="59229-313">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="59229-313">CommonParameters</span></span>

<span data-ttu-id="59229-314">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="59229-314">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="59229-315">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="59229-315">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="59229-316">Входные данные</span><span class="sxs-lookup"><span data-stu-id="59229-316">INPUTS</span></span>

### <span data-ttu-id="59229-317">Нет</span><span class="sxs-lookup"><span data-stu-id="59229-317">None</span></span>

<span data-ttu-id="59229-318">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="59229-318">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="59229-319">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="59229-319">OUTPUTS</span></span>

### <span data-ttu-id="59229-320">System. Management. Automation. Ремотингжоб</span><span class="sxs-lookup"><span data-stu-id="59229-320">System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="59229-321">Этот командлет возвращает объекты, представляющие задания в сеансе.</span><span class="sxs-lookup"><span data-stu-id="59229-321">This cmdlet returns objects that represent the jobs in the session.</span></span>

## <span data-ttu-id="59229-322">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="59229-322">NOTES</span></span>

* <span data-ttu-id="59229-323">Свойство **PSJobTypeName** задания указывает на его тип.</span><span class="sxs-lookup"><span data-stu-id="59229-323">The **PSJobTypeName** property of jobs indicates the job type of the job.</span></span> <span data-ttu-id="59229-324">Значение свойства определяется автором типа задания.</span><span class="sxs-lookup"><span data-stu-id="59229-324">The property value is determined by the job type author.</span></span> <span data-ttu-id="59229-325">Ниже приведен список распространенных типов заданий.</span><span class="sxs-lookup"><span data-stu-id="59229-325">The following list shows common job types.</span></span>

  - <span data-ttu-id="59229-326">**Баккграунджоб** .</span><span class="sxs-lookup"><span data-stu-id="59229-326">**BackgroundJob** .</span></span>
<span data-ttu-id="59229-327">Локальное задание запущено с помощью команды **Start-Job** .</span><span class="sxs-lookup"><span data-stu-id="59229-327">Local job started by using **Start-Job** .</span></span>

  - <span data-ttu-id="59229-328">**Ремотежоб** .</span><span class="sxs-lookup"><span data-stu-id="59229-328">**RemoteJob** .</span></span>
<span data-ttu-id="59229-329">Задание запущено в **PSSession** с помощью параметра *AsJob* командлета Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="59229-329">Job started in a **PSSession** by using the *AsJob* parameter of the Invoke-Command cmdlet.</span></span>

## <span data-ttu-id="59229-330">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="59229-330">RELATED LINKS</span></span>

[<span data-ttu-id="59229-331">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="59229-331">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="59229-332">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="59229-332">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="59229-333">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="59229-333">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="59229-334">Start-Job</span><span class="sxs-lookup"><span data-stu-id="59229-334">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="59229-335">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="59229-335">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="59229-336">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="59229-336">Wait-Job</span></span>](Wait-Job.md)
