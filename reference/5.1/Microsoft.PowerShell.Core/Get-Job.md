---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Job.
ms.openlocfilehash: 0b9c76ca1e26adaa244473366c2eabdaaa28452c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226681"
---
# <span data-ttu-id="bc06f-103">Get-Job.</span><span class="sxs-lookup"><span data-stu-id="bc06f-103">Get-Job</span></span>

## <span data-ttu-id="bc06f-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="bc06f-104">SYNOPSIS</span></span>
<span data-ttu-id="bc06f-105">Возвращает фоновые задания PowerShell, выполняемые в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="bc06f-105">Gets PowerShell background jobs that are running in the current session.</span></span>

## <span data-ttu-id="bc06f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bc06f-106">SYNTAX</span></span>

### <span data-ttu-id="bc06f-107">Сессионидпараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="bc06f-107">SessionIdParameterSet (Default)</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [[-Id] <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="bc06f-108">коммандпараметерсет</span><span class="sxs-lookup"><span data-stu-id="bc06f-108">CommandParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Command <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="bc06f-109">инстанцеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="bc06f-109">InstanceIdParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="bc06f-110">намепараметерсет</span><span class="sxs-lookup"><span data-stu-id="bc06f-110">NameParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="bc06f-111">статепараметерсет</span><span class="sxs-lookup"><span data-stu-id="bc06f-111">StateParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-State] <JobState> [<CommonParameters>]
```

### <span data-ttu-id="bc06f-112">филтерпараметерсет</span><span class="sxs-lookup"><span data-stu-id="bc06f-112">FilterParameterSet</span></span>

```
Get-Job [-Filter] <Hashtable> [<CommonParameters>]
```

## <span data-ttu-id="bc06f-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bc06f-113">DESCRIPTION</span></span>

<span data-ttu-id="bc06f-114">Командлет **Get-Job** возвращает объекты, которые представляют фоновые задания, запущенные в рамках текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="bc06f-114">The **Get-Job** cmdlet gets objects that represent the background jobs that were started in the current session.</span></span>
<span data-ttu-id="bc06f-115">**Get-Job** можно использовать для получения заданий, запущенных с помощью командлета Start-Job, или с помощью параметра *AsJob* любого командлета.</span><span class="sxs-lookup"><span data-stu-id="bc06f-115">You can use **Get-Job** to get jobs that were started by using the Start-Job cmdlet, or by using the *AsJob* parameter of any cmdlet.</span></span>

<span data-ttu-id="bc06f-116">Без параметров команда **Get-Job** возвращает все задания в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="bc06f-116">Without parameters, a **Get-Job** command gets all jobs in the current session.</span></span>
<span data-ttu-id="bc06f-117">С помощью параметров командлета **Get-Job** можно получить определенные задания.</span><span class="sxs-lookup"><span data-stu-id="bc06f-117">You can use the parameters of **Get-Job** to get particular jobs.</span></span>

<span data-ttu-id="bc06f-118">Объект задания, возвращаемый командлетом **Get-Job** , содержит полезную информацию о задании, но не содержит результатов его выполнения.</span><span class="sxs-lookup"><span data-stu-id="bc06f-118">The job object that **Get-Job** returns contains useful information about the job, but it does not contain the job results.</span></span>
<span data-ttu-id="bc06f-119">Чтобы получить результаты, используйте командлет Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="bc06f-119">To get the results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="bc06f-120">Фоновое задание Windows PowerShell — это команда, которая выполняется в фоновом режиме без взаимодействия с текущим сеансом.</span><span class="sxs-lookup"><span data-stu-id="bc06f-120">A Windows PowerShell background job is a command that runs in the background without interacting with the current session.</span></span>
<span data-ttu-id="bc06f-121">Как правило, для выполнения сложной команды, которая занимает много времени, используется фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="bc06f-121">Typically, you use a background job to run a complex command that takes a long time to finish.</span></span>
<span data-ttu-id="bc06f-122">Дополнительные сведения о фоновых заданиях в Windows PowerShell см. в разделе about_Jobs.</span><span class="sxs-lookup"><span data-stu-id="bc06f-122">For more information about background jobs in Windows PowerShell, see about_Jobs.</span></span>

<span data-ttu-id="bc06f-123">Начиная с выпуска Windows PowerShell 3.0 командлет **Get-Job** также возвращает задания настраиваемых типов, такие как задания рабочих процессов и экземпляры запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="bc06f-123">Beginning in Windows PowerShell 3.0, the **Get-Job** cmdlet also gets custom job types, such as workflow jobs and instances of scheduled jobs.</span></span>
<span data-ttu-id="bc06f-124">Чтобы определить тип задания, используйте его свойство **PSJobTypeName**.</span><span class="sxs-lookup"><span data-stu-id="bc06f-124">To find the job type of a job, use the **PSJobTypeName** property of the job.</span></span>

<span data-ttu-id="bc06f-125">Чтобы включить командлет **Get-Job** для получения настраиваемого типа задания, импортируйте модуль, который поддерживает тип настраиваемого задания, в сеанс перед выполнением команды **get-job** с помощью Import-Moduleого или с помощью или получения командлета в модуле.</span><span class="sxs-lookup"><span data-stu-id="bc06f-125">To enable **Get-Job** to get a custom job type, import the module that supports the custom job type into the session before you run a **Get-Job** command, either by using the Import-Module cmdlet or by using or getting a cmdlet in the module.</span></span>
<span data-ttu-id="bc06f-126">Дополнительные сведения о определенных пользовательских типах заданий см. в разделе документации о данной функции.</span><span class="sxs-lookup"><span data-stu-id="bc06f-126">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="bc06f-127">Примеры</span><span class="sxs-lookup"><span data-stu-id="bc06f-127">EXAMPLES</span></span>

### <span data-ttu-id="bc06f-128">Пример 1. получение всех фоновых заданий, запущенных в текущем сеансе</span><span class="sxs-lookup"><span data-stu-id="bc06f-128">Example 1: Get all background jobs started in the current session</span></span>

```
PS C:\> Get-Job
```

<span data-ttu-id="bc06f-129">Эта команда возвращает все фоновые задания, запущенные в рамках текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="bc06f-129">This command gets all background jobs started in the current session.</span></span>
<span data-ttu-id="bc06f-130">Сюда не включаются задания, созданные в рамках других сеансов, даже если они выполняются на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="bc06f-130">It does not include jobs created in other sessions, even if the jobs run on the local computer.</span></span>

### <span data-ttu-id="bc06f-131">Пример 2. завершение задания с помощью идентификатора экземпляра</span><span class="sxs-lookup"><span data-stu-id="bc06f-131">Example 2: Stop a job by using an instance ID</span></span>

```
The first command uses the **Get-Job** cmdlet to get a job. It uses the *Name* parameter to identify the job. The command stores the job object that **Get-Job** returns in the $j variable. In this example, there is only one job with the specified name.
PS C:\> $j = Get-Job -Name Job1

The second command gets the **InstanceId** property of the object in the $j variable and stores it in the $ID variable.
PS C:\> $ID = $j.InstanceID

The third command displays the value of the $ID variable.
PS C:\> $ID

Guid
----
03c3232e-1d23-453b-a6f4-ed73c9e29d55

The fourth command uses Stop-Job cmdlet to stop the job. It uses the *InstanceId* parameter to identify the job and $ID variable to represent the instance ID of the job.
PS C:\> Stop-Job -InstanceId $ID
```

<span data-ttu-id="bc06f-132">Эти команды показывают, как получить идентификатор экземпляра задания, а затем с его помощью остановить задание.</span><span class="sxs-lookup"><span data-stu-id="bc06f-132">These commands show how to get the instance ID of a job and then use it to stop a job.</span></span>
<span data-ttu-id="bc06f-133">В отличие от имени задания, идентификатор экземпляра уникален.</span><span class="sxs-lookup"><span data-stu-id="bc06f-133">Unlike the name of a job, which is not unique, the instance ID is unique.</span></span>

### <span data-ttu-id="bc06f-134">Пример 3. получение заданий, включающих определенную команду</span><span class="sxs-lookup"><span data-stu-id="bc06f-134">Example 3: Get jobs that include a specific command</span></span>

```
PS C:\> Get-Job -Command "*get-process*"
```

<span data-ttu-id="bc06f-135">Эта команда возвращает задания в системе, которые содержат команду Get-Process.</span><span class="sxs-lookup"><span data-stu-id="bc06f-135">This command gets the jobs on the system that include a Get-Process command.</span></span>
<span data-ttu-id="bc06f-136">В ней используется параметр *Command* командлета **Get-Job** для ограничения получаемых заданий.</span><span class="sxs-lookup"><span data-stu-id="bc06f-136">The command uses the *Command* parameter of **Get-Job** to limit the jobs retrieved.</span></span>
<span data-ttu-id="bc06f-137">Команда использует подстановочные знаки (\*) для получения заданий, включающих команду **Get-Process** в любом месте командной строки.</span><span class="sxs-lookup"><span data-stu-id="bc06f-137">The command uses wildcard characters (\*) to get jobs that include a **Get-Process** command anywhere in the command string.</span></span>

### <span data-ttu-id="bc06f-138">Пример 4. получение заданий, включающих определенную команду, с помощью конвейера</span><span class="sxs-lookup"><span data-stu-id="bc06f-138">Example 4: Get jobs that include a specific command by using the pipeline</span></span>

```
PS C:\> "*get-process*" | Get-Job
```

<span data-ttu-id="bc06f-139">Как и команда в предыдущем примере, эта команда возвращает задания в системе, которые включают команду **Get-Process** .</span><span class="sxs-lookup"><span data-stu-id="bc06f-139">Like the command in the previous example, this command gets the jobs on the system that include a **Get-Process** command.</span></span>
<span data-ttu-id="bc06f-140">Команда использует оператор конвейера (|) для отправки строки в кавычках командлету **Get-Job** .</span><span class="sxs-lookup"><span data-stu-id="bc06f-140">The command uses a pipeline operator (|) to send a string, in quotation marks, to the **Get-Job** cmdlet.</span></span>
<span data-ttu-id="bc06f-141">Это равносильно предыдущей команде.</span><span class="sxs-lookup"><span data-stu-id="bc06f-141">It is the equivalent of the previous command.</span></span>

### <span data-ttu-id="bc06f-142">Пример 5. получение заданий, которые не были запущены</span><span class="sxs-lookup"><span data-stu-id="bc06f-142">Example 5: Get jobs that have not been started</span></span>

```
PS C:\> Get-Job -State NotStarted
```

<span data-ttu-id="bc06f-143">Эта команда возвращает только те задания, которые созданы, но еще не запущены.</span><span class="sxs-lookup"><span data-stu-id="bc06f-143">This command gets only those jobs that have been created but have not yet been started.</span></span>
<span data-ttu-id="bc06f-144">Сюда входят задания, запланированные к выполнению в будущем, и задания, выполнение которых еще не запланировано.</span><span class="sxs-lookup"><span data-stu-id="bc06f-144">This includes jobs that are scheduled to run in the future and those not yet scheduled.</span></span>

### <span data-ttu-id="bc06f-145">Пример 6. получение заданий, которым не было назначено имя</span><span class="sxs-lookup"><span data-stu-id="bc06f-145">Example 6: Get jobs that have not been assigned a name</span></span>

```
PS C:\> Get-Job -Name Job*
```

<span data-ttu-id="bc06f-146">Эта команда возвращает все задания с именами заданий, которые начинаются с Job.</span><span class="sxs-lookup"><span data-stu-id="bc06f-146">This command gets all jobs that have job names that begin with job.</span></span>
<span data-ttu-id="bc06f-147">Так как задание \<number\> является именем задания по умолчанию, эта команда возвращает все задания, которым не назначено явное имя.</span><span class="sxs-lookup"><span data-stu-id="bc06f-147">Because job\<number\> is the default name for a job, this command gets all jobs that do not have an explicitly assigned name.</span></span>

### <span data-ttu-id="bc06f-148">Пример 7. Использование объекта задания для представления задания в команде</span><span class="sxs-lookup"><span data-stu-id="bc06f-148">Example 7: Use a job object to represent the job in a command</span></span>

```
The first command uses the **Start-Job** cmdlet to start a background job that runs a **Get-Process** command on the local computer. The command uses the *Name* parameter of **Start-Job** to assign a friendly name to the job.
PS C:\> Start-Job -ScriptBlock {Get-Process} -Name MyJob

The second command uses Get-Job to get the job. It uses the *Name* parameter of **Get-Job** to identify the job. The command saves the resulting job object in the $j variable.
PS C:\> $j = Get-Job -Name MyJob

The third command displays the value of the job object in the $j variable. The value of the **State** property shows that the job is completed. The value of the **HasMoreData** property shows that there are results available from the job that have not yet been retrieved.
PS C:\> $j
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
6      MyJob           BackgroundJob   Completed     True            localhost            Get-Process

The fourth command uses the **Receive-Job** cmdlet to get the results of the job. It uses the job object in the $j variable to represent the job. You can also use a pipeline operator to send a job object to **Receive-Job**.
PS C:\> Receive-Job -Job $j
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    124       4    13572      12080    59            1140 audiodg
    783      16    11428      13636   100             548 CcmExec
     96       4     4252       3764    59            3856 ccmsetup
...
```

<span data-ttu-id="bc06f-149">В этом примере показано, как использовать командлет **Get-Job** для получения объекта задания и как затем использовать этот объект для представления задания в команде.</span><span class="sxs-lookup"><span data-stu-id="bc06f-149">This example shows how to use **Get-Job** to get a job object, and then it shows how to use the job object to represent the job in a command.</span></span>

### <span data-ttu-id="bc06f-150">Пример 8. получение всех заданий, включая задания, запущенные другим методом</span><span class="sxs-lookup"><span data-stu-id="bc06f-150">Example 8: Get all jobs including jobs started by a different method</span></span>

```
The first command uses the **Start-Job** cmdlet to start a job on the local computer.
PS C:\> Start-Job -ScriptBlock {Get-EventLog System}

The second command uses the *AsJob* parameter of the **Invoke-Command** cmdlet to start a job on the S1 computer. Even though the commands in the job run on the remote computer, the job object is created on the local computer, so you use local commands to manage the job.
PS C:\> Invoke-Command -ComputerName S1 -ScriptBlock {Get-EventLog System} -AsJob

The third command uses the **Invoke-Command** cmdlet to run a **Start-Job** command on the S2 computer. By using this method, the job object is created on the remote computer, so you use remote commands to manage the job.
PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}

The fourth command uses **Get-Job** to get the jobs stored on the local computer. The **PSJobTypeName** property of jobs, introduced in Windows PowerShell 3.0, shows that the local job started by using the **Start-Job** cmdlet is a background job and the job started in a remote session by using the **Invoke-Command** cmdlet is a remote job.
PS C:\> Get-Job
Id     Name       PSJobTypeName   State         HasMoreData     Location        Command
--     ----       -------------   -----         -----------     --------        -------
1      Job1       BackgroundJob   Running       True            localhost       Get-EventLog System
2      Job2       RemoteJob       Running       True            S1              Get-EventLog System

The fifth command uses **Invoke-Command** to run a **Get-Job** command on the S2 computer.The sample output shows the results of the Get-Job command. On the S2 computer, the job appears to be a local job. The computer name is localhost and the job type is a background job.For more information about how to run background jobs on remote computers, see about_Remote_Jobs.
PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Id    Name     PSJobTypeName  State      HasMoreData   Location   Command
--    ----     -------------  -----      -----------   -------    -------
4     Job4     BackgroundJob  Running    True          localhost  Get-Eventlog System
```

<span data-ttu-id="bc06f-151">В этом примере показано, что командлет **Get-Job** может получить все задания, запущенные в текущем сеансе, даже если они были запущены с помощью различных методов.</span><span class="sxs-lookup"><span data-stu-id="bc06f-151">This example demonstrates that the **Get-Job** cmdlet can get all of the jobs that were started in the current session, even if they were started by using different methods.</span></span>

### <span data-ttu-id="bc06f-152">Пример 9. исследование невыполненного задания</span><span class="sxs-lookup"><span data-stu-id="bc06f-152">Example 9: Investigate a failed job</span></span>

```
The first command uses the **Start-Job** cmdlet to start a job on the local computer. The job object that **Start-Job** returns shows that the job failed. The value of the **State** property is Failed.
PS C:\> Start-Job -ScriptBlock {Get-Process}
Id     Name       PSJobTypeName   State       HasMoreData     Location             Command
--     ----       -------------   -----       -----------     --------             -------
1      Job1       BackgroundJob   Failed      False           localhost            Get-Process

The second command uses the **Get-Job** cmdlet to get the job. The command uses the dot method to get the value of the **JobStateInfo** property of the object. It uses a pipeline operator to send the object in the **JobStateInfo** property to the Format-List cmdlet, which formats all of the properties of the object (*) in a list.The result of the **Format-List** command shows that the value of the **Reason** property of the job is blank.
PS C:\> (Get-Job).JobStateInfo | Format-List -Property *
State  : Failed
Reason :

The third command investigates more. It uses a **Get-Job** command to get the job and then uses a pipeline operator to send the whole job object to the **Format-List** cmdlet, which displays all of the properties of the job in a list.The display of all properties in the job object shows that the job contains a child job named Job2.
PS C:\> Get-Job | Format-List -Property *
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

The fourth command uses **Get-Job** to get the job object that represents the Job2 child job. This is the job in which the command actually ran. It uses the dot method to get the **Reason** property of the **JobStateInfo** property.The result shows that the job failed because of an Access Denied error. In this case, the user forgot to use the Run as administrator option when starting Windows PowerShell.Because background jobs use the remoting features of Windows PowerShell, the computer must be configured for remoting to run a job, even when the job runs on the local computer.For information about requirements for remoting in Windows PowerShell, see about_Remote_Requirements. For troubleshooting tips, see about_Remote_Troubleshooting.
PS C:\> (Get-Job -Name job2).JobStateInfo.Reason
Connecting to remote server using WSManCreateShellEx api failed. The async callback gave the following error message: Access is denied.
```

<span data-ttu-id="bc06f-153">Эта команда показывает, как использовать объект задания, возвращаемый командлетом **Get-Job** , чтобы выяснить причину сбоя задания.</span><span class="sxs-lookup"><span data-stu-id="bc06f-153">This command shows how to use the job object that **Get-Job** returns to investigate why a job failed.</span></span>
<span data-ttu-id="bc06f-154">Она также показывает, как получить дочерние задания каждого задания.</span><span class="sxs-lookup"><span data-stu-id="bc06f-154">It also shows how to get the child jobs of each job.</span></span>

### <span data-ttu-id="bc06f-155">Пример 10. получение отфильтрованных результатов</span><span class="sxs-lookup"><span data-stu-id="bc06f-155">Example 10: Get filtered results</span></span>

```
The first command uses the **Workflow** keyword to create the WFProcess workflow.
PS C:\> Workflow WFProcess {Get-Process}

The second command uses the *AsJob* parameter of the WFProcess workflow to run the workflow as a background job. It uses the *JobName* parameter of the workflow to specify a name for the job, and the *PSPrivateMetadata* parameter of the workflow to specify a custom ID.
PS C:\> WFProcess -AsJob -JobName WFProcessJob -PSPrivateMetadata @{MyCustomId = 92107}

The third command uses the *Filter* parameter of **Get-Job** to get the job by custom ID that was specified in the *PSPrivateMetadata* parameter.
PS C:\> Get-Job -Filter @{MyCustomId = 92107}
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
1      WFProcessJob    Completed     True            localhost            WFProcess
```

<span data-ttu-id="bc06f-156">В этом примере показано, как использовать параметр *Filter* для получения задания рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="bc06f-156">This example shows how to use the *Filter* parameter to get a workflow job.</span></span>
<span data-ttu-id="bc06f-157">Параметр *Filter* , появившийся в Windows PowerShell 3.0, действует только применительно к заданиям настраиваемых типов, таким как задания рабочих процессов и запланированные задания.</span><span class="sxs-lookup"><span data-stu-id="bc06f-157">The *Filter* parameter, introduced in Windows PowerShell 3.0 is valid only on custom job types, such as workflow jobs and scheduled jobs.</span></span>

### <span data-ttu-id="bc06f-158">Пример 11. Получение сведений о дочерних заданиях</span><span class="sxs-lookup"><span data-stu-id="bc06f-158">Example 11: Get information about child jobs</span></span>

```
The first command gets the jobs in the current session. The output includes a background job, a remote job and several instances of a scheduled job. The remote job, Job4, appears to have failed.
PS C:\> Get-Job
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost            .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02   .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

The second command uses the *IncludeChildJob* parameter of **Get-Job**. The output adds the child jobs of all jobs that have child jobs.In this case, the revised output shows that only the Job5 child job of Job4 failed.
PS C:\> Get-Job -IncludeChildJob
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

The third command uses the *ChildJobState* parameter with a value of Failed.The output includes all parent jobs and only the child jobs that failed.
PS C:\> Get-Job -Name Job4 -ChildJobState Failed
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost           .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02  .\Get-Archive.ps1
5      Job5                            Failed        False           Server01            .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

The fifth command uses the **JobStateInfo** property of jobs and its **Reason** property to discover why Job5 failed.
PS C:\> (Get-Job -Name Job5).JobStateInfo.Reason
Connecting to remote server Server01 failed with the following error message:
Access is denied.
For more information, see the about_Remote_Troubleshooting Help topic.
```

<span data-ttu-id="bc06f-159">В этом примере показан результат использования параметров *IncludeChildJob* и *ChildJobState* командлета **Get-Job**.</span><span class="sxs-lookup"><span data-stu-id="bc06f-159">This example shows the effect of using the *IncludeChildJob* and *ChildJobState* parameters of the **Get-Job** cmdlet.</span></span>

## <span data-ttu-id="bc06f-160">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bc06f-160">PARAMETERS</span></span>

### <span data-ttu-id="bc06f-161">-After</span><span class="sxs-lookup"><span data-stu-id="bc06f-161">-After</span></span>

<span data-ttu-id="bc06f-162">Возвращает выполненные задания, которые завершились после указанных даты и времени.</span><span class="sxs-lookup"><span data-stu-id="bc06f-162">Gets completed jobs that ended after the specified date and time.</span></span>
<span data-ttu-id="bc06f-163">Введите объект **DateTime** , например, возвращаемый командлетом Get-Date, или строку, которую можно преобразовать в объект **DateTime** , например `Dec 1, 2012 2:00 AM` или `11/06` .</span><span class="sxs-lookup"><span data-stu-id="bc06f-163">Enter a **DateTime** object, such as one returned by the Get-Date cmdlet or a string that can be converted to a **DateTime** object, such as `Dec 1, 2012 2:00 AM` or `11/06`.</span></span>

<span data-ttu-id="bc06f-164">Этот параметр применим только к заданиям настраиваемых типов, таким как задания рабочих процессов и запланированные задания, имеющим свойство **EndTime**.</span><span class="sxs-lookup"><span data-stu-id="bc06f-164">This parameter works only on custom job types, such as workflow jobs and scheduled jobs, that have an **EndTime** property.</span></span>
<span data-ttu-id="bc06f-165">Он не работает со стандартными фоновыми заданиями, такими как созданные с помощью командлета **Start-Job** .</span><span class="sxs-lookup"><span data-stu-id="bc06f-165">It does not work on standard background jobs, such as those created by using the **Start-Job** cmdlet.</span></span>
<span data-ttu-id="bc06f-166">Дополнительные сведения о поддержке данного параметра см. в разделе справки о соответствующем типе заданий.</span><span class="sxs-lookup"><span data-stu-id="bc06f-166">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="bc06f-167">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="bc06f-167">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bc06f-168">— До</span><span class="sxs-lookup"><span data-stu-id="bc06f-168">-Before</span></span>

<span data-ttu-id="bc06f-169">Возвращает выполненные задания, которые завершились до указанных даты и времени.</span><span class="sxs-lookup"><span data-stu-id="bc06f-169">Gets completed jobs that ended before the specified date and time.</span></span>
<span data-ttu-id="bc06f-170">Введите объект **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="bc06f-170">Enter a **DateTime** object.</span></span>

<span data-ttu-id="bc06f-171">Этот параметр применим только к заданиям настраиваемых типов, таким как задания рабочих процессов и запланированные задания, имеющим свойство **EndTime**.</span><span class="sxs-lookup"><span data-stu-id="bc06f-171">This parameter works only on custom job types, such as workflow jobs and scheduled jobs, that have an **EndTime** property.</span></span>
<span data-ttu-id="bc06f-172">Он не работает со стандартными фоновыми заданиями, такими как созданные с помощью командлета **Start-Job** .</span><span class="sxs-lookup"><span data-stu-id="bc06f-172">It does not work on standard background jobs, such as those created by using the **Start-Job** cmdlet.</span></span>
<span data-ttu-id="bc06f-173">Дополнительные сведения о поддержке данного параметра см. в разделе справки о соответствующем типе заданий.</span><span class="sxs-lookup"><span data-stu-id="bc06f-173">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="bc06f-174">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="bc06f-174">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bc06f-175">-Чилджобстате</span><span class="sxs-lookup"><span data-stu-id="bc06f-175">-ChildJobState</span></span>

<span data-ttu-id="bc06f-176">Возвращает только те дочерние задания, которые находятся в указанном состоянии.</span><span class="sxs-lookup"><span data-stu-id="bc06f-176">Gets only the child jobs that have the specified state.</span></span>
<span data-ttu-id="bc06f-177">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="bc06f-177">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="bc06f-178">NotStarted</span><span class="sxs-lookup"><span data-stu-id="bc06f-178">NotStarted</span></span>
- <span data-ttu-id="bc06f-179">Запущен</span><span class="sxs-lookup"><span data-stu-id="bc06f-179">Running</span></span>
- <span data-ttu-id="bc06f-180">Завершено</span><span class="sxs-lookup"><span data-stu-id="bc06f-180">Completed</span></span>
- <span data-ttu-id="bc06f-181">Ошибка</span><span class="sxs-lookup"><span data-stu-id="bc06f-181">Failed</span></span>
- <span data-ttu-id="bc06f-182">Остановлена</span><span class="sxs-lookup"><span data-stu-id="bc06f-182">Stopped</span></span>
- <span data-ttu-id="bc06f-183">Блокировано</span><span class="sxs-lookup"><span data-stu-id="bc06f-183">Blocked</span></span>
- <span data-ttu-id="bc06f-184">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="bc06f-184">Suspended</span></span>
- <span data-ttu-id="bc06f-185">Отключено</span><span class="sxs-lookup"><span data-stu-id="bc06f-185">Disconnected</span></span>
- <span data-ttu-id="bc06f-186">Приостановка</span><span class="sxs-lookup"><span data-stu-id="bc06f-186">Suspending</span></span>
- <span data-ttu-id="bc06f-187">Остановка</span><span class="sxs-lookup"><span data-stu-id="bc06f-187">Stopping</span></span>

<span data-ttu-id="bc06f-188">По умолчанию командлет **Get-Job** не возвращает дочерние задания.</span><span class="sxs-lookup"><span data-stu-id="bc06f-188">By default, **Get-Job** does not get child jobs.</span></span>
<span data-ttu-id="bc06f-189">С помощью параметра *инклудечилджоб* командлет **Get-Job** получает все дочерние задания.</span><span class="sxs-lookup"><span data-stu-id="bc06f-189">By using the *IncludeChildJob* parameter, **Get-Job** gets all child jobs.</span></span>
<span data-ttu-id="bc06f-190">При использовании параметра *ChildJobState* параметр *IncludeChildJob* не действует.</span><span class="sxs-lookup"><span data-stu-id="bc06f-190">If you use the *ChildJobState* parameter, the *IncludeChildJob* parameter has no effect.</span></span>

<span data-ttu-id="bc06f-191">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="bc06f-191">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bc06f-192">-Command</span><span class="sxs-lookup"><span data-stu-id="bc06f-192">-Command</span></span>

<span data-ttu-id="bc06f-193">Указывает массив команд в виде строк.</span><span class="sxs-lookup"><span data-stu-id="bc06f-193">Specifies an array of commands as strings.</span></span>
<span data-ttu-id="bc06f-194">Этот командлет возвращает задания, включающие указанные команды.</span><span class="sxs-lookup"><span data-stu-id="bc06f-194">This cmdlet gets the jobs that include the specified commands.</span></span>
<span data-ttu-id="bc06f-195">По умолчанию останавливаются все задания.</span><span class="sxs-lookup"><span data-stu-id="bc06f-195">The default is all jobs.</span></span>
<span data-ttu-id="bc06f-196">Для указания шаблона команды можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="bc06f-196">You can use wildcard characters to specify a command pattern.</span></span>

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

### <span data-ttu-id="bc06f-197">-Filter</span><span class="sxs-lookup"><span data-stu-id="bc06f-197">-Filter</span></span>

<span data-ttu-id="bc06f-198">Указывает хэш-таблицу условий.</span><span class="sxs-lookup"><span data-stu-id="bc06f-198">Specifies a hash table of conditions.</span></span>
<span data-ttu-id="bc06f-199">Этот командлет возвращает задания, которые отвечают всем условиям.</span><span class="sxs-lookup"><span data-stu-id="bc06f-199">This cmdlet gets jobs that satisfy all of the conditions.</span></span>
<span data-ttu-id="bc06f-200">Введите хэш-таблицу, где ключи являются свойствами заданий, а значения — значениями этих свойств.</span><span class="sxs-lookup"><span data-stu-id="bc06f-200">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="bc06f-201">Этот параметр работает только с пользовательскими типами заданий, такими как задания рабочих процессов и запланированные задания.</span><span class="sxs-lookup"><span data-stu-id="bc06f-201">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span>
<span data-ttu-id="bc06f-202">Он не работает со стандартными фоновыми заданиями, такими как созданные с помощью командлета **Start-Job** .</span><span class="sxs-lookup"><span data-stu-id="bc06f-202">It does not work on standard background jobs, such as those created by using the **Start-Job** cmdlet.</span></span>
<span data-ttu-id="bc06f-203">Дополнительные сведения о поддержке данного параметра см. в разделе справки о соответствующем типе заданий.</span><span class="sxs-lookup"><span data-stu-id="bc06f-203">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="bc06f-204">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="bc06f-204">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="bc06f-205">-Хасморедата</span><span class="sxs-lookup"><span data-stu-id="bc06f-205">-HasMoreData</span></span>

<span data-ttu-id="bc06f-206">Указывает, получает ли этот командлет только задания с указанным значением свойства **хасморедата** .</span><span class="sxs-lookup"><span data-stu-id="bc06f-206">Indicates whether this cmdlet gets only jobs that have the specified **HasMoreData** property value.</span></span>
<span data-ttu-id="bc06f-207">Свойство **HasMoreData** указывает, были ли все результаты задания получены в рамках текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="bc06f-207">The **HasMoreData** property indicates whether all job results have been received in the current session.</span></span>
<span data-ttu-id="bc06f-208">Чтобы получить задания с дополнительными результатами, укажите значение $True.</span><span class="sxs-lookup"><span data-stu-id="bc06f-208">To get jobs that have more results, specify a value of $True.</span></span>
<span data-ttu-id="bc06f-209">Чтобы получить задания, которые не имеют дополнительных результатов, укажите значение $False.</span><span class="sxs-lookup"><span data-stu-id="bc06f-209">To get jobs that do not have more results, specify a value of $False.</span></span>

<span data-ttu-id="bc06f-210">Чтобы получить результаты задания, используйте командлет Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="bc06f-210">To get the results of a job, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="bc06f-211">При использовании командлета **Receive-Job** он удаляет из его хранилища возвращаемые результаты.</span><span class="sxs-lookup"><span data-stu-id="bc06f-211">When you use the **Receive-Job** cmdlet, it deletes from its in-memory, session-specific storage the results that it returned.</span></span>
<span data-ttu-id="bc06f-212">Когда он возвращает все результаты задания в текущем сеансе, он устанавливает для свойства **хасморедата** задания значение $false), чтобы указать, что он больше не имеет результатов для задания в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="bc06f-212">When it has returned all results of the job in the current session, it sets the value of the **HasMoreData** property of the job to $False) to indicate that it has no more results for the job in the current session.</span></span>
<span data-ttu-id="bc06f-213">Чтобы запретить командлету *Receive-Job* удалять результаты и изменять значение свойства **HasMoreData** , используйте параметр **Keep** командлета **Receive-Job**.</span><span class="sxs-lookup"><span data-stu-id="bc06f-213">Use the *Keep* parameter of **Receive-Job** to prevent **Receive-Job** from deleting results and changing the value of the **HasMoreData** property.</span></span>
<span data-ttu-id="bc06f-214">Для получения дополнительных сведений введите `Get-Help Receive-Job`.</span><span class="sxs-lookup"><span data-stu-id="bc06f-214">For more information, type `Get-Help Receive-Job`.</span></span>

<span data-ttu-id="bc06f-215">Свойство **HasMoreData** относится к текущему сеансу.</span><span class="sxs-lookup"><span data-stu-id="bc06f-215">The **HasMoreData** property is specific to the current session.</span></span>
<span data-ttu-id="bc06f-216">Если результаты для пользовательского типа задания сохраняются за пределами сеанса, например тип запланированного задания, который сохраняет результаты задания на диске, можно использовать командлет **Receive-Job** в другом сеансе для повторного получения результатов задания, даже если значение **хасморедата** равно $false.</span><span class="sxs-lookup"><span data-stu-id="bc06f-216">If results for a custom job type are saved outside of the session, such as the scheduled job type, which saves job results on disk, you can use the **Receive-Job** cmdlet in a different session to get the job results again, even if the value of **HasMoreData** is $False.</span></span>
<span data-ttu-id="bc06f-217">Подробнее см. в разделах справки по настраиваемому типу задания.</span><span class="sxs-lookup"><span data-stu-id="bc06f-217">For more information, see the help topics for the custom job type.</span></span>

<span data-ttu-id="bc06f-218">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="bc06f-218">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Boolean
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bc06f-219">-Id</span><span class="sxs-lookup"><span data-stu-id="bc06f-219">-Id</span></span>

<span data-ttu-id="bc06f-220">Указывает массив идентификаторов заданий, которые получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="bc06f-220">Specifies an array of IDs of jobs that this cmdlet gets.</span></span>

<span data-ttu-id="bc06f-221">Идентификатор — это целое число, которое однозначно определяет задание в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="bc06f-221">The ID is an integer that uniquely identifies the job in the current session.</span></span>
<span data-ttu-id="bc06f-222">Проще запомнить и ввести, чем идентификатор экземпляра, но он уникален только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="bc06f-222">It is easier to remember and to type than the instance ID, but it is unique only in the current session.</span></span>
<span data-ttu-id="bc06f-223">Можно ввести один или несколько идентификаторов, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="bc06f-223">You can type one or more IDs separated by commas.</span></span>
<span data-ttu-id="bc06f-224">Чтобы найти идентификатор задания, введите `Get-Job` без параметров.</span><span class="sxs-lookup"><span data-stu-id="bc06f-224">To find the ID of a job, type `Get-Job` without parameters.</span></span>

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

### <span data-ttu-id="bc06f-225">-Инклудечилджоб</span><span class="sxs-lookup"><span data-stu-id="bc06f-225">-IncludeChildJob</span></span>

<span data-ttu-id="bc06f-226">Указывает, что этот командлет возвращает дочерние задания в дополнение к родительским заданиям.</span><span class="sxs-lookup"><span data-stu-id="bc06f-226">Indicates that this cmdlet returns child jobs, in addition to parent jobs.</span></span>

<span data-ttu-id="bc06f-227">Этот параметр особенно полезен для изучения заданий рабочего процесса, для которых командлет **Get-Job** Возвращает родительское задание контейнера, а также сбои заданий, так как причина сбоя сохраняется в свойстве дочернего задания.</span><span class="sxs-lookup"><span data-stu-id="bc06f-227">This parameter is especially useful for investigating workflow jobs, for which **Get-Job** returns a container parent job, and job failures, because the reason for the failure is saved in a property of the child job.</span></span>

<span data-ttu-id="bc06f-228">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="bc06f-228">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bc06f-229">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="bc06f-229">-InstanceId</span></span>

<span data-ttu-id="bc06f-230">Указывает массив идентификаторов экземпляров заданий, которые получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="bc06f-230">Specifies an array of instance IDs of jobs that this cmdlet gets.</span></span>
<span data-ttu-id="bc06f-231">По умолчанию останавливаются все задания.</span><span class="sxs-lookup"><span data-stu-id="bc06f-231">The default is all jobs.</span></span>

<span data-ttu-id="bc06f-232">Идентификатор экземпляра — это GUID, который однозначно определяет задание на компьютере.</span><span class="sxs-lookup"><span data-stu-id="bc06f-232">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span>
<span data-ttu-id="bc06f-233">Чтобы узнать идентификатор экземпляра задания, используйте командлет **Get-Job**.</span><span class="sxs-lookup"><span data-stu-id="bc06f-233">To find the instance ID of a job, use **Get-Job**.</span></span>

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

### <span data-ttu-id="bc06f-234">-Name</span><span class="sxs-lookup"><span data-stu-id="bc06f-234">-Name</span></span>

<span data-ttu-id="bc06f-235">Указывает массив понятных имен экземпляров заданий, которые получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="bc06f-235">Specifies an array of instance friendly names of jobs that this cmdlet gets.</span></span>
<span data-ttu-id="bc06f-236">Введите имя задания или используйте подстановочные знаки для ввода шаблона имени задания.</span><span class="sxs-lookup"><span data-stu-id="bc06f-236">Enter a job name, or use wildcard characters to enter a job name pattern.</span></span>
<span data-ttu-id="bc06f-237">По умолчанию командлет **Get-Job** возвращает все задания в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="bc06f-237">By default, **Get-Job** gets all jobs in the current session.</span></span>

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

### <span data-ttu-id="bc06f-238">— Самый новый</span><span class="sxs-lookup"><span data-stu-id="bc06f-238">-Newest</span></span>

<span data-ttu-id="bc06f-239">Указывает число заданий для получения.</span><span class="sxs-lookup"><span data-stu-id="bc06f-239">Specifies a number of jobs to get.</span></span>
<span data-ttu-id="bc06f-240">Этот командлет возвращает задания, которые были завершены недавно.</span><span class="sxs-lookup"><span data-stu-id="bc06f-240">This cmdlet gets the jobs that ended most recently.</span></span>

<span data-ttu-id="bc06f-241">Параметр *Newest* не сортирует задания по времени завершения.</span><span class="sxs-lookup"><span data-stu-id="bc06f-241">The *Newest* parameter does not sort or return the newest jobs in end-time order.</span></span>
<span data-ttu-id="bc06f-242">Чтобы отсортировать выходные данные, используйте командлет Sort-Object.</span><span class="sxs-lookup"><span data-stu-id="bc06f-242">To sort the output, use the Sort-Object cmdlet.</span></span>

<span data-ttu-id="bc06f-243">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="bc06f-243">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bc06f-244">-State</span><span class="sxs-lookup"><span data-stu-id="bc06f-244">-State</span></span>

<span data-ttu-id="bc06f-245">Указывает состояние задания.</span><span class="sxs-lookup"><span data-stu-id="bc06f-245">Specifies a job state.</span></span>
<span data-ttu-id="bc06f-246">Этот командлет возвращает только задания в указанном состоянии.</span><span class="sxs-lookup"><span data-stu-id="bc06f-246">This cmdlet gets only jobs in the specified state.</span></span>
<span data-ttu-id="bc06f-247">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="bc06f-247">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="bc06f-248">NotStarted</span><span class="sxs-lookup"><span data-stu-id="bc06f-248">NotStarted</span></span>
- <span data-ttu-id="bc06f-249">Запущен</span><span class="sxs-lookup"><span data-stu-id="bc06f-249">Running</span></span>
- <span data-ttu-id="bc06f-250">Завершено</span><span class="sxs-lookup"><span data-stu-id="bc06f-250">Completed</span></span>
- <span data-ttu-id="bc06f-251">Ошибка</span><span class="sxs-lookup"><span data-stu-id="bc06f-251">Failed</span></span>
- <span data-ttu-id="bc06f-252">Остановлена</span><span class="sxs-lookup"><span data-stu-id="bc06f-252">Stopped</span></span>
- <span data-ttu-id="bc06f-253">Блокировано</span><span class="sxs-lookup"><span data-stu-id="bc06f-253">Blocked</span></span>
- <span data-ttu-id="bc06f-254">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="bc06f-254">Suspended</span></span>
- <span data-ttu-id="bc06f-255">Отключено</span><span class="sxs-lookup"><span data-stu-id="bc06f-255">Disconnected</span></span>
- <span data-ttu-id="bc06f-256">Приостановка</span><span class="sxs-lookup"><span data-stu-id="bc06f-256">Suspending</span></span>
- <span data-ttu-id="bc06f-257">Остановка</span><span class="sxs-lookup"><span data-stu-id="bc06f-257">Stopping</span></span>

<span data-ttu-id="bc06f-258">По умолчанию командлет **Get-Job** возвращает все задания в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="bc06f-258">By default, **Get-Job** gets all the jobs in the current session.</span></span>

<span data-ttu-id="bc06f-259">Дополнительные сведения о состояниях заданий см. в разделе [перечисление JobState](https://msdn.microsoft.com/library/system.management.automation.jobstate) в библиотеке MSDN.</span><span class="sxs-lookup"><span data-stu-id="bc06f-259">For more information about job states, see [JobState Enumeration](https://msdn.microsoft.com/library/system.management.automation.jobstate) in the MSDN library.</span></span>

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

### <span data-ttu-id="bc06f-260">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="bc06f-260">CommonParameters</span></span>

<span data-ttu-id="bc06f-261">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bc06f-261">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bc06f-262">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bc06f-262">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bc06f-263">Входные данные</span><span class="sxs-lookup"><span data-stu-id="bc06f-263">INPUTS</span></span>

### <span data-ttu-id="bc06f-264">Нет</span><span class="sxs-lookup"><span data-stu-id="bc06f-264">None</span></span>

<span data-ttu-id="bc06f-265">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="bc06f-265">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="bc06f-266">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="bc06f-266">OUTPUTS</span></span>

### <span data-ttu-id="bc06f-267">System. Management. Automation. Ремотингжоб</span><span class="sxs-lookup"><span data-stu-id="bc06f-267">System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="bc06f-268">Этот командлет возвращает объекты, представляющие задания в сеансе.</span><span class="sxs-lookup"><span data-stu-id="bc06f-268">This cmdlet returns objects that represent the jobs in the session.</span></span>

## <span data-ttu-id="bc06f-269">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="bc06f-269">NOTES</span></span>

* <span data-ttu-id="bc06f-270">Свойство **PSJobTypeName** задания указывает на его тип.</span><span class="sxs-lookup"><span data-stu-id="bc06f-270">The **PSJobTypeName** property of jobs indicates the job type of the job.</span></span> <span data-ttu-id="bc06f-271">Значение свойства определяется автором типа задания.</span><span class="sxs-lookup"><span data-stu-id="bc06f-271">The property value is determined by the job type author.</span></span> <span data-ttu-id="bc06f-272">Ниже приведен список распространенных типов заданий.</span><span class="sxs-lookup"><span data-stu-id="bc06f-272">The following list shows common job types.</span></span>

  - <span data-ttu-id="bc06f-273">**Баккграунджоб**.</span><span class="sxs-lookup"><span data-stu-id="bc06f-273">**BackgroundJob**.</span></span>
<span data-ttu-id="bc06f-274">Локальное задание запущено с помощью команды **Start-Job**.</span><span class="sxs-lookup"><span data-stu-id="bc06f-274">Local job started by using **Start-Job**.</span></span>

  - <span data-ttu-id="bc06f-275">**Ремотежоб**.</span><span class="sxs-lookup"><span data-stu-id="bc06f-275">**RemoteJob**.</span></span>
<span data-ttu-id="bc06f-276">Задание запущено в **PSSession** с помощью параметра *AsJob* командлета Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="bc06f-276">Job started in a **PSSession** by using the *AsJob* parameter of the Invoke-Command cmdlet.</span></span>

  - <span data-ttu-id="bc06f-277">**Псворкфловжоб**.</span><span class="sxs-lookup"><span data-stu-id="bc06f-277">**PSWorkflowJob**.</span></span>
<span data-ttu-id="bc06f-278">задание, запущенное с помощью общего параметра *AsJob* рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="bc06f-278">Job started by using the *AsJob* common parameter of workflows.</span></span>

## <span data-ttu-id="bc06f-279">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="bc06f-279">RELATED LINKS</span></span>

[<span data-ttu-id="bc06f-280">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="bc06f-280">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="bc06f-281">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="bc06f-281">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="bc06f-282">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="bc06f-282">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="bc06f-283">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="bc06f-283">Resume-Job</span></span>](Resume-Job.md)

[<span data-ttu-id="bc06f-284">Start-Job</span><span class="sxs-lookup"><span data-stu-id="bc06f-284">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="bc06f-285">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="bc06f-285">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="bc06f-286">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="bc06f-286">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="bc06f-287">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="bc06f-287">Wait-Job</span></span>](Wait-Job.md)

[<span data-ttu-id="bc06f-288">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="bc06f-288">about_Jobs</span></span>](About/about_Jobs.md)

[<span data-ttu-id="bc06f-289">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="bc06f-289">about_Job_Details</span></span>](About/about_Job_Details.md)

[<span data-ttu-id="bc06f-290">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="bc06f-290">about_Remote_Jobs</span></span>](About/about_Remote_Jobs.md)

[<span data-ttu-id="bc06f-291">about_Scheduled_Jobs</span><span class="sxs-lookup"><span data-stu-id="bc06f-291">about_Scheduled_Jobs</span></span>](../PSScheduledJob/About/about_Scheduled_Jobs.md)
