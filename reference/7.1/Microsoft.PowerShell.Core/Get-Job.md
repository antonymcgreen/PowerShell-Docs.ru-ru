---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-job?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Job.
ms.openlocfilehash: 167f56964bbdb675c2dd85e2803fdee2d308ee4f
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94389578"
---
# <span data-ttu-id="fdb53-103">Get-Job.</span><span class="sxs-lookup"><span data-stu-id="fdb53-103">Get-Job</span></span>

## <span data-ttu-id="fdb53-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="fdb53-104">SYNOPSIS</span></span>
<span data-ttu-id="fdb53-105">Возвращает фоновые задания PowerShell, выполняемые в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="fdb53-105">Gets PowerShell background jobs that are running in the current session.</span></span>

## <span data-ttu-id="fdb53-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fdb53-106">SYNTAX</span></span>

### <span data-ttu-id="fdb53-107">Сессионидпараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="fdb53-107">SessionIdParameterSet (Default)</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [[-Id] <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="fdb53-108">инстанцеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="fdb53-108">InstanceIdParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="fdb53-109">намепараметерсет</span><span class="sxs-lookup"><span data-stu-id="fdb53-109">NameParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="fdb53-110">статепараметерсет</span><span class="sxs-lookup"><span data-stu-id="fdb53-110">StateParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-State] <JobState> [<CommonParameters>]
```

### <span data-ttu-id="fdb53-111">коммандпараметерсет</span><span class="sxs-lookup"><span data-stu-id="fdb53-111">CommandParameterSet</span></span>

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Command <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="fdb53-112">филтерпараметерсет</span><span class="sxs-lookup"><span data-stu-id="fdb53-112">FilterParameterSet</span></span>

```
Get-Job [-Filter] <Hashtable> [<CommonParameters>]
```

## <span data-ttu-id="fdb53-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fdb53-113">DESCRIPTION</span></span>

<span data-ttu-id="fdb53-114">`Get-Job`Командлет возвращает объекты, представляющие фоновые задания, которые были запущены в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="fdb53-114">The `Get-Job` cmdlet gets objects that represent the background jobs that were started in the current session.</span></span> <span data-ttu-id="fdb53-115">Можно использовать `Get-Job` для получения заданий, запущенных с помощью `Start-Job` командлета, или с помощью параметра **AsJob** любого командлета.</span><span class="sxs-lookup"><span data-stu-id="fdb53-115">You can use `Get-Job` to get jobs that were started by using the `Start-Job` cmdlet, or by using the **AsJob** parameter of any cmdlet.</span></span>

<span data-ttu-id="fdb53-116">Без параметров `Get-Job` команда возвращает все задания в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="fdb53-116">Without parameters, a `Get-Job` command gets all jobs in the current session.</span></span> <span data-ttu-id="fdb53-117">`Get-Job`Для получения конкретных заданий можно использовать параметры.</span><span class="sxs-lookup"><span data-stu-id="fdb53-117">You can use the parameters of `Get-Job` to get particular jobs.</span></span>

<span data-ttu-id="fdb53-118">Объект задания, который `Get-Job` возвращает, содержит полезные сведения о задании, но не содержит результатов задания.</span><span class="sxs-lookup"><span data-stu-id="fdb53-118">The job object that `Get-Job` returns contains useful information about the job, but it does not contain the job results.</span></span> <span data-ttu-id="fdb53-119">Чтобы получить результаты, используйте `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="fdb53-119">To get the results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="fdb53-120">Фоновое задание Windows PowerShell — это команда, которая выполняется в фоновом режиме без взаимодействия с текущим сеансом.</span><span class="sxs-lookup"><span data-stu-id="fdb53-120">A Windows PowerShell background job is a command that runs in the background without interacting with the current session.</span></span> <span data-ttu-id="fdb53-121">Как правило, для выполнения сложной команды, которая занимает много времени, используется фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="fdb53-121">Typically, you use a background job to run a complex command that takes a long time to finish.</span></span> <span data-ttu-id="fdb53-122">Дополнительные сведения о фоновых заданиях в Windows PowerShell см. в разделе [about_Jobs](./about/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="fdb53-122">For more information about background jobs in Windows PowerShell, see [about_Jobs](./about/about_Jobs.md).</span></span>

<span data-ttu-id="fdb53-123">Начиная с Windows PowerShell 3,0, `Get-Job` командлет также получает пользовательские типы заданий, такие как задания рабочего процесса и экземпляры запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="fdb53-123">Beginning in Windows PowerShell 3.0, the `Get-Job` cmdlet also gets custom job types, such as workflow jobs and instances of scheduled jobs.</span></span> <span data-ttu-id="fdb53-124">Чтобы определить тип задания, используйте его свойство **PSJobTypeName**.</span><span class="sxs-lookup"><span data-stu-id="fdb53-124">To find the job type of a job, use the **PSJobTypeName** property of the job.</span></span>

<span data-ttu-id="fdb53-125">Чтобы разрешить `Get-Job` получение настраиваемого типа задания, импортируйте модуль, который поддерживает тип настраиваемого задания, в сеанс перед выполнением `Get-Job` команды либо с помощью `Import-Module` командлета, либо путем получения командлета в модуле.</span><span class="sxs-lookup"><span data-stu-id="fdb53-125">To enable `Get-Job` to get a custom job type, import the module that supports the custom job type into the session before you run a `Get-Job` command, either by using the `Import-Module` cmdlet or by using or getting a cmdlet in the module.</span></span> <span data-ttu-id="fdb53-126">Дополнительные сведения о определенных пользовательских типах заданий см. в разделе документации о данной функции.</span><span class="sxs-lookup"><span data-stu-id="fdb53-126">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="fdb53-127">Примеры</span><span class="sxs-lookup"><span data-stu-id="fdb53-127">EXAMPLES</span></span>

### <span data-ttu-id="fdb53-128">Пример 1. получение всех фоновых заданий, запущенных в текущем сеансе</span><span class="sxs-lookup"><span data-stu-id="fdb53-128">Example 1: Get all background jobs started in the current session</span></span>

<span data-ttu-id="fdb53-129">Эта команда возвращает все фоновые задания, запущенные в рамках текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="fdb53-129">This command gets all background jobs started in the current session.</span></span> <span data-ttu-id="fdb53-130">Сюда не включаются задания, созданные в рамках других сеансов, даже если они выполняются на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="fdb53-130">It does not include jobs created in other sessions, even if the jobs run on the local computer.</span></span>

```
PS C:\> Get-Job
```

### <span data-ttu-id="fdb53-131">Пример 2. завершение задания с помощью идентификатора экземпляра</span><span class="sxs-lookup"><span data-stu-id="fdb53-131">Example 2: Stop a job by using an instance ID</span></span>

<span data-ttu-id="fdb53-132">Эти команды показывают, как получить идентификатор экземпляра задания, а затем с его помощью остановить задание.</span><span class="sxs-lookup"><span data-stu-id="fdb53-132">These commands show how to get the instance ID of a job and then use it to stop a job.</span></span> <span data-ttu-id="fdb53-133">В отличие от имени задания, идентификатор экземпляра уникален.</span><span class="sxs-lookup"><span data-stu-id="fdb53-133">Unlike the name of a job, which is not unique, the instance ID is unique.</span></span>

<span data-ttu-id="fdb53-134">Первая команда использует `Get-Job` командлет для получения задания.</span><span class="sxs-lookup"><span data-stu-id="fdb53-134">The first command uses the `Get-Job` cmdlet to get a job.</span></span> <span data-ttu-id="fdb53-135">Для обнаружения задания используется параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="fdb53-135">It uses the **Name** parameter to identify the job.</span></span> <span data-ttu-id="fdb53-136">Команда сохраняет объект задания, который `Get-Job` возвращает значение в `$j` переменной.</span><span class="sxs-lookup"><span data-stu-id="fdb53-136">The command stores the job object that `Get-Job` returns in the `$j` variable.</span></span> <span data-ttu-id="fdb53-137">В этом примере имеется только одно задание с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="fdb53-137">In this example, there is only one job with the specified name.</span></span> <span data-ttu-id="fdb53-138">Вторая команда получает свойство **InstanceId** объекта в `$j` переменной и сохраняет его в `$ID` переменной.</span><span class="sxs-lookup"><span data-stu-id="fdb53-138">The second command gets the **InstanceId** property of the object in the `$j` variable and stores it in the `$ID` variable.</span></span> <span data-ttu-id="fdb53-139">Третья команда отображает значение `$ID` переменной.</span><span class="sxs-lookup"><span data-stu-id="fdb53-139">The third command displays the value of the `$ID` variable.</span></span> <span data-ttu-id="fdb53-140">Четвертая команда использует `Stop-Job` командлет для завершения задания.</span><span class="sxs-lookup"><span data-stu-id="fdb53-140">The fourth command uses `Stop-Job` cmdlet to stop the job.</span></span>
<span data-ttu-id="fdb53-141">Он использует параметр **InstanceId** для идентификации задания и переменной, `$ID` представляющей идентификатор экземпляра задания.</span><span class="sxs-lookup"><span data-stu-id="fdb53-141">It uses the **InstanceId** parameter to identify the job and `$ID` variable to represent the instance ID of the job.</span></span>

```
PS C:\> $j = Get-Job -Name Job1
PS C:\> $ID = $j.InstanceID
PS C:\> $ID

Guid
----
03c3232e-1d23-453b-a6f4-ed73c9e29d55

PS C:\> Stop-Job -InstanceId $ID
```

### <span data-ttu-id="fdb53-142">Пример 3. получение заданий, включающих определенную команду</span><span class="sxs-lookup"><span data-stu-id="fdb53-142">Example 3: Get jobs that include a specific command</span></span>

<span data-ttu-id="fdb53-143">Эта команда возвращает задания в системе, содержащие `Get-Process` команду.</span><span class="sxs-lookup"><span data-stu-id="fdb53-143">This command gets the jobs on the system that include a `Get-Process` command.</span></span> <span data-ttu-id="fdb53-144">Команда использует параметр **Command** аргумента `Get-Job` для ограничения числа извлекаемых заданий.</span><span class="sxs-lookup"><span data-stu-id="fdb53-144">The command uses the **Command** parameter of `Get-Job` to limit the jobs retrieved.</span></span> <span data-ttu-id="fdb53-145">Команда использует подстановочные знаки ( `*` ) для получения заданий, включающих `Get-Process` команду в любом месте командной строки.</span><span class="sxs-lookup"><span data-stu-id="fdb53-145">The command uses wildcard characters (`*`) to get jobs that include a `Get-Process` command anywhere in the command string.</span></span>

```
PS C:\> Get-Job -Command "*get-process*"
```

### <span data-ttu-id="fdb53-146">Пример 4. получение заданий, включающих определенную команду, с помощью конвейера</span><span class="sxs-lookup"><span data-stu-id="fdb53-146">Example 4: Get jobs that include a specific command by using the pipeline</span></span>

<span data-ttu-id="fdb53-147">Как и команда в предыдущем примере, эта команда возвращает задания в системе, которые включают `Get-Process` команду.</span><span class="sxs-lookup"><span data-stu-id="fdb53-147">Like the command in the previous example, this command gets the jobs on the system that include a `Get-Process` command.</span></span> <span data-ttu-id="fdb53-148">Команда использует оператор конвейера ( `|` ) для отправки строки в кавычки в `Get-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="fdb53-148">The command uses a pipeline operator (`|`) to send a string, in quotation marks, to the `Get-Job` cmdlet.</span></span> <span data-ttu-id="fdb53-149">Это равносильно предыдущей команде.</span><span class="sxs-lookup"><span data-stu-id="fdb53-149">It is the equivalent of the previous command.</span></span>

```
PS C:\> "*get-process*" | Get-Job
```

### <span data-ttu-id="fdb53-150">Пример 5. получение заданий, которые не были запущены</span><span class="sxs-lookup"><span data-stu-id="fdb53-150">Example 5: Get jobs that have not been started</span></span>

<span data-ttu-id="fdb53-151">Эта команда возвращает только те задания, которые созданы, но еще не запущены.</span><span class="sxs-lookup"><span data-stu-id="fdb53-151">This command gets only those jobs that have been created but have not yet been started.</span></span> <span data-ttu-id="fdb53-152">Сюда входят задания, запланированные к выполнению в будущем, и задания, выполнение которых еще не запланировано.</span><span class="sxs-lookup"><span data-stu-id="fdb53-152">This includes jobs that are scheduled to run in the future and those not yet scheduled.</span></span>

```
PS C:\> Get-Job -State NotStarted
```

### <span data-ttu-id="fdb53-153">Пример 6. получение заданий, которым не было назначено имя</span><span class="sxs-lookup"><span data-stu-id="fdb53-153">Example 6: Get jobs that have not been assigned a name</span></span>

<span data-ttu-id="fdb53-154">Эта команда возвращает все задания с именами заданий, которые начинаются с Job.</span><span class="sxs-lookup"><span data-stu-id="fdb53-154">This command gets all jobs that have job names that begin with job.</span></span> <span data-ttu-id="fdb53-155">Поскольку `job<number>` является именем задания по умолчанию, эта команда возвращает все задания, которым не назначено явное имя.</span><span class="sxs-lookup"><span data-stu-id="fdb53-155">Because `job<number>` is the default name for a job, this command gets all jobs that do not have an explicitly assigned name.</span></span>

```
PS C:\> Get-Job -Name Job*
```

### <span data-ttu-id="fdb53-156">Пример 7. Использование объекта задания для представления задания в команде</span><span class="sxs-lookup"><span data-stu-id="fdb53-156">Example 7: Use a job object to represent the job in a command</span></span>

<span data-ttu-id="fdb53-157">В этом примере показано, как использовать `Get-Job` для получения объекта задания, а затем показано, как использовать объект задания для представления задания в команде.</span><span class="sxs-lookup"><span data-stu-id="fdb53-157">This example shows how to use `Get-Job` to get a job object, and then it shows how to use the job object to represent the job in a command.</span></span>

<span data-ttu-id="fdb53-158">Первая команда использует `Start-Job` командлет для запуска фонового задания, запускающего `Get-Process` команду на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="fdb53-158">The first command uses the `Start-Job` cmdlet to start a background job that runs a `Get-Process` command on the local computer.</span></span> <span data-ttu-id="fdb53-159">Команда использует параметр **Name** параметра, `Start-Job` чтобы присвоить заданию понятное имя.</span><span class="sxs-lookup"><span data-stu-id="fdb53-159">The command uses the **Name** parameter of `Start-Job` to assign a friendly name to the job.</span></span> <span data-ttu-id="fdb53-160">Вторая команда использует `Get-Job` для получения задания.</span><span class="sxs-lookup"><span data-stu-id="fdb53-160">The second command uses `Get-Job` to get the job.</span></span> <span data-ttu-id="fdb53-161">Для обнаружения задания используется параметр **Name** объекта `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="fdb53-161">It uses the **Name** parameter of `Get-Job` to identify the job.</span></span> <span data-ttu-id="fdb53-162">Команда сохраняет результирующий объект задания в `$j` переменной.</span><span class="sxs-lookup"><span data-stu-id="fdb53-162">The command saves the resulting job object in the `$j` variable.</span></span> <span data-ttu-id="fdb53-163">Третья команда отображает значение объекта задания в `$j` переменной.</span><span class="sxs-lookup"><span data-stu-id="fdb53-163">The third command displays the value of the job object in the `$j` variable.</span></span> <span data-ttu-id="fdb53-164">Значение свойства **State** показывает, что задание завершено.</span><span class="sxs-lookup"><span data-stu-id="fdb53-164">The value of the **State** property shows that the job is completed.</span></span> <span data-ttu-id="fdb53-165">Значение свойства **HasMoreData** показывает, что есть результаты задания, которые еще не были получены.</span><span class="sxs-lookup"><span data-stu-id="fdb53-165">The value of the **HasMoreData** property shows that there are results available from the job that have not yet been retrieved.</span></span> <span data-ttu-id="fdb53-166">Четвертая команда использует `Receive-Job` командлет для получения результатов задания.</span><span class="sxs-lookup"><span data-stu-id="fdb53-166">The fourth command uses the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="fdb53-167">Он использует объект задания в `$j` переменной для представления задания.</span><span class="sxs-lookup"><span data-stu-id="fdb53-167">It uses the job object in the `$j` variable to represent the job.</span></span> <span data-ttu-id="fdb53-168">Можно также использовать оператор конвейера для отправки объекта задания в `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="fdb53-168">You can also use a pipeline operator to send a job object to `Receive-Job`.</span></span>

```
PS C:\> Start-Job -ScriptBlock {Get-Process} -Name MyJob
PS C:\> $j = Get-Job -Name MyJob
PS C:\> $j
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
6      MyJob           BackgroundJob   Completed     True            localhost            Get-Process

PS C:\> Receive-Job -Job $j
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    124       4    13572      12080    59            1140 audiodg
    783      16    11428      13636   100             548 CcmExec
     96       4     4252       3764    59            3856 ccmsetup
...
```


### <span data-ttu-id="fdb53-169">Пример 8. получение всех заданий, включая задания, запущенные другим методом</span><span class="sxs-lookup"><span data-stu-id="fdb53-169">Example 8: Get all jobs including jobs started by a different method</span></span>

<span data-ttu-id="fdb53-170">В этом примере показано, что `Get-Job` командлет может получить все задания, запущенные в текущем сеансе, даже если они были запущены с помощью различных методов.</span><span class="sxs-lookup"><span data-stu-id="fdb53-170">This example demonstrates that the `Get-Job` cmdlet can get all of the jobs that were started in the current session, even if they were started by using different methods.</span></span>

<span data-ttu-id="fdb53-171">Первая команда использует `Start-Job` командлет для запуска задания на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="fdb53-171">The first command uses the `Start-Job` cmdlet to start a job on the local computer.</span></span> <span data-ttu-id="fdb53-172">Вторая команда использует параметр **AsJob** `Invoke-Command` командлета для запуска задания на компьютере S1.</span><span class="sxs-lookup"><span data-stu-id="fdb53-172">The second command uses the **AsJob** parameter of the `Invoke-Command` cmdlet to start a job on the S1 computer.</span></span> <span data-ttu-id="fdb53-173">Хотя команды задания выполняются на удаленном компьютере, объект задания создается на локальном, поэтому вы можете управлять заданием с помощью локальных команд.</span><span class="sxs-lookup"><span data-stu-id="fdb53-173">Even though the commands in the job run on the remote computer, the job object is created on the local computer, so you use local commands to manage the job.</span></span> <span data-ttu-id="fdb53-174">Третья команда использует `Invoke-Command` командлет для выполнения `Start-Job` команды на компьютере S2.</span><span class="sxs-lookup"><span data-stu-id="fdb53-174">The third command uses the `Invoke-Command` cmdlet to run a `Start-Job` command on the S2 computer.</span></span> <span data-ttu-id="fdb53-175">При использовании этого метода объект задания создается на удаленном компьютере, поэтому для управления заданием используются удаленные команды.</span><span class="sxs-lookup"><span data-stu-id="fdb53-175">By using this method, the job object is created on the remote computer, so you use remote commands to manage the job.</span></span> <span data-ttu-id="fdb53-176">Четвертая команда использует `Get-Job` для получения заданий, хранящихся на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="fdb53-176">The fourth command uses `Get-Job` to get the jobs stored on the local computer.</span></span> <span data-ttu-id="fdb53-177">Свойство **псжобтипенаме** заданий, представленное в Windows PowerShell 3,0, показывает, что локальное задание, запущенное с помощью `Start-Job` командлета, является фоновым заданием и заданием, запущенным в удаленном сеансе с помощью `Invoke-Command` командлета, является удаленное задание.</span><span class="sxs-lookup"><span data-stu-id="fdb53-177">The **PSJobTypeName** property of jobs, introduced in Windows PowerShell 3.0, shows that the local job started by using the `Start-Job` cmdlet is a background job and the job started in a remote session by using the `Invoke-Command` cmdlet is a remote job.</span></span> <span data-ttu-id="fdb53-178">Пятая команда использует `Invoke-Command` для выполнения `Get-Job` команды на компьютере S2. В выходных данных примера показаны результаты выполнения `Get-Job` команды.</span><span class="sxs-lookup"><span data-stu-id="fdb53-178">The fifth command uses `Invoke-Command` to run a `Get-Job` command on the S2 computer.The sample output shows the results of the `Get-Job` command.</span></span> <span data-ttu-id="fdb53-179">На компьютере S2 задание отображается как локальное.</span><span class="sxs-lookup"><span data-stu-id="fdb53-179">On the S2 computer, the job appears to be a local job.</span></span> <span data-ttu-id="fdb53-180">Имя компьютера — localhost, а тип задания — фоновое задание. Дополнительные сведения о выполнении фоновых заданий на удаленных компьютерах см. в разделе [about_Remote_Jobs](./about/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="fdb53-180">The computer name is localhost and the job type is a background job.For more information about how to run background jobs on remote computers, see [about_Remote_Jobs](./about/about_Remote_Jobs.md).</span></span>

```
PS C:\> Start-Job -ScriptBlock {Get-EventLog System}
PS C:\> Invoke-Command -ComputerName S1 -ScriptBlock {Get-EventLog System} -AsJob
PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
PS C:\> Get-Job
Id     Name       PSJobTypeName   State         HasMoreData     Location        Command
--     ----       -------------   -----         -----------     --------        -------
1      Job1       BackgroundJob   Running       True            localhost       Get-EventLog System
2      Job2       RemoteJob       Running       True            S1              Get-EventLog System

PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Id    Name     PSJobTypeName  State      HasMoreData   Location   Command
--    ----     -------------  -----      -----------   -------    -------
4     Job4     BackgroundJob  Running    True          localhost  Get-Eventlog System
```

### <span data-ttu-id="fdb53-181">Пример 9. исследование невыполненного задания</span><span class="sxs-lookup"><span data-stu-id="fdb53-181">Example 9: Investigate a failed job</span></span>

<span data-ttu-id="fdb53-182">Эта команда показывает, как использовать объект задания, который `Get-Job` возвращает, чтобы выяснить причину сбоя задания.</span><span class="sxs-lookup"><span data-stu-id="fdb53-182">This command shows how to use the job object that `Get-Job` returns to investigate why a job failed.</span></span>
<span data-ttu-id="fdb53-183">Она также показывает, как получить дочерние задания каждого задания.</span><span class="sxs-lookup"><span data-stu-id="fdb53-183">It also shows how to get the child jobs of each job.</span></span>

<span data-ttu-id="fdb53-184">Первая команда использует `Start-Job` командлет для запуска задания на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="fdb53-184">The first command uses the `Start-Job` cmdlet to start a job on the local computer.</span></span> <span data-ttu-id="fdb53-185">Объект задания, который `Start-Job` возвращает значение, показывает, что задание завершилось ошибкой.</span><span class="sxs-lookup"><span data-stu-id="fdb53-185">The job object that `Start-Job` returns shows that the job failed.</span></span> <span data-ttu-id="fdb53-186">Значение свойства **State** не выполнено.</span><span class="sxs-lookup"><span data-stu-id="fdb53-186">The value of the **State** property is Failed.</span></span>

<span data-ttu-id="fdb53-187">Вторая команда использует `Get-Job` командлет для получения задания.</span><span class="sxs-lookup"><span data-stu-id="fdb53-187">The second command uses the `Get-Job` cmdlet to get the job.</span></span> <span data-ttu-id="fdb53-188">С помощью точечной нотации извлекается значение свойства **JobStateInfo** объекта.</span><span class="sxs-lookup"><span data-stu-id="fdb53-188">The command uses the dot method to get the value of the **JobStateInfo** property of the object.</span></span> <span data-ttu-id="fdb53-189">Он использует оператор конвейера для отправки объекта в свойство **JobStateInfo** в `Format-List` командлет, который форматирует все свойства объекта ( `*` ) в списке. Результат выполнения `Format-List` команды показывает, что значение свойства **Reason** задания пусто.</span><span class="sxs-lookup"><span data-stu-id="fdb53-189">It uses a pipeline operator to send the object in the **JobStateInfo** property to the `Format-List` cmdlet, which formats all of the properties of the object (`*`) in a list.The result of the `Format-List` command shows that the value of the **Reason** property of the job is blank.</span></span>

<span data-ttu-id="fdb53-190">Третья команда изучает дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="fdb53-190">The third command investigates more.</span></span> <span data-ttu-id="fdb53-191">Он использует `Get-Job` команду для получения задания, а затем использует оператор конвейера для отправки всего объекта задания в `Format-List` командлет, который отображает все свойства задания в списке. Отображение всех свойств в объекте задания показывает, что задание содержит дочернее задание с именем Job2.</span><span class="sxs-lookup"><span data-stu-id="fdb53-191">It uses a `Get-Job` command to get the job and then uses a pipeline operator to send the whole job object to the `Format-List` cmdlet, which displays all of the properties of the job in a list.The display of all properties in the job object shows that the job contains a child job named Job2.</span></span>

<span data-ttu-id="fdb53-192">Четвертая команда использует `Get-Job` для получения объекта задания, представляющего дочернее задание Job2.</span><span class="sxs-lookup"><span data-stu-id="fdb53-192">The fourth command uses `Get-Job` to get the job object that represents the Job2 child job.</span></span> <span data-ttu-id="fdb53-193">Это задание, в котором на самом деле выполнялась команда.</span><span class="sxs-lookup"><span data-stu-id="fdb53-193">This is the job in which the command actually ran.</span></span> <span data-ttu-id="fdb53-194">Он использует метод Dot для получения свойства **Reason** свойства **JobStateInfo** . Результат показывает, что задание завершилось сбоем из-за ошибки отказа в доступе.</span><span class="sxs-lookup"><span data-stu-id="fdb53-194">It uses the dot method to get the **Reason** property of the **JobStateInfo** property.The result shows that the job failed because of an Access Denied error.</span></span> <span data-ttu-id="fdb53-195">В этом случае пользователь забыл использовать параметр Запуск от имени администратора при запуске Windows PowerShell. Поскольку фоновые задания используют функции удаленного взаимодействия Windows PowerShell, компьютер должен быть настроен для запуска задания, даже если задание выполняется на локальном компьютере. Сведения о требованиях для удаленного взаимодействия в Windows PowerShell см. в разделе [about_Remote_Requirements](./about/about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdb53-195">In this case, the user forgot to use the Run as administrator option when starting Windows PowerShell.Because background jobs use the remoting features of Windows PowerShell, the computer must be configured for remoting to run a job, even when the job runs on the local computer.For information about requirements for remoting in Windows PowerShell, see [about_Remote_Requirements](./about/about_Remote_Requirements.md).</span></span> <span data-ttu-id="fdb53-196">Советы по устранению неполадок см. в разделе [about_Remote_Troubleshooting](./about/about_Remote_Troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="fdb53-196">For troubleshooting tips, see [about_Remote_Troubleshooting](./about/about_Remote_Troubleshooting.md).</span></span>

```
PS C:\> Start-Job -ScriptBlock {Get-Process}
Id     Name       PSJobTypeName   State       HasMoreData     Location             Command
--     ----       -------------   -----       -----------     --------             -------
1      Job1       BackgroundJob   Failed      False           localhost            Get-Process

PS C:\> (Get-Job).JobStateInfo | Format-List -Property *
State  : Failed
Reason :

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

PS C:\> (Get-Job -Name job2).JobStateInfo.Reason
Connecting to remote server using WSManCreateShellEx api failed. The async callback gave the
following error message: Access is denied.
```

### <span data-ttu-id="fdb53-197">Пример 10. получение отфильтрованных результатов</span><span class="sxs-lookup"><span data-stu-id="fdb53-197">Example 10: Get filtered results</span></span>

<span data-ttu-id="fdb53-198">В этом примере показано, как использовать параметр **Filter** для получения задания рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="fdb53-198">This example shows how to use the **Filter** parameter to get a workflow job.</span></span> <span data-ttu-id="fdb53-199">Параметр **Filter** , появившийся в Windows PowerShell 3.0, действует только применительно к заданиям настраиваемых типов, таким как задания рабочих процессов и запланированные задания.</span><span class="sxs-lookup"><span data-stu-id="fdb53-199">The **Filter** parameter, introduced in Windows PowerShell 3.0 is valid only on custom job types, such as workflow jobs and scheduled jobs.</span></span>

<span data-ttu-id="fdb53-200">Первая команда использует ключевое слово **рабочего процесса** для создания рабочего процесса вфпроцесс.</span><span class="sxs-lookup"><span data-stu-id="fdb53-200">The first command uses the **Workflow** keyword to create the WFProcess workflow.</span></span> <span data-ttu-id="fdb53-201">Вторая команда использует параметр **AsJob** рабочего процесса вфпроцесс для запуска рабочего процесса в качестве фонового задания.</span><span class="sxs-lookup"><span data-stu-id="fdb53-201">The second command uses the **AsJob** parameter of the WFProcess workflow to run the workflow as a background job.</span></span> <span data-ttu-id="fdb53-202">Параметр **JobName** рабочего процесса используется для указания имени задания, а параметр **PSPrivateMetadata** рабочего процесса — для указания настраиваемого идентификатора.</span><span class="sxs-lookup"><span data-stu-id="fdb53-202">It uses the **JobName** parameter of the workflow to specify a name for the job, and the **PSPrivateMetadata** parameter of the workflow to specify a custom ID.</span></span> <span data-ttu-id="fdb53-203">Третья команда использует параметр **Filter** объекта `Get-Job` для получения задания по пользовательскому идентификатору, указанному в параметре **псприватеметадата** .</span><span class="sxs-lookup"><span data-stu-id="fdb53-203">The third command uses the **Filter** parameter of `Get-Job` to get the job by custom ID that was specified in the **PSPrivateMetadata** parameter.</span></span>

```
PS C:\> Workflow WFProcess {Get-Process}
PS C:\> WFProcess -AsJob -JobName WFProcessJob -PSPrivateMetadata @{MyCustomId = 92107}
PS C:\> Get-Job -Filter @{MyCustomId = 92107}
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
1      WFProcessJob    Completed     True            localhost            WFProcess
```

### <span data-ttu-id="fdb53-204">Пример 11. Получение сведений о дочерних заданиях</span><span class="sxs-lookup"><span data-stu-id="fdb53-204">Example 11: Get information about child jobs</span></span>

<span data-ttu-id="fdb53-205">В этом примере показан результат использования параметров **инклудечилджоб** и **чилджобстате** `Get-Job` командлета.</span><span class="sxs-lookup"><span data-stu-id="fdb53-205">This example shows the effect of using the **IncludeChildJob** and **ChildJobState** parameters of the `Get-Job` cmdlet.</span></span>

<span data-ttu-id="fdb53-206">Первая команда возвращает задания в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="fdb53-206">The first command gets the jobs in the current session.</span></span> <span data-ttu-id="fdb53-207">Выходные данные включают в себя фоновое задание, удаленное задание и несколько экземпляров запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="fdb53-207">The output includes a background job, a remote job and several instances of a scheduled job.</span></span> <span data-ttu-id="fdb53-208">Удаленное задание Job4, по-видимому, завершилось сбоем.</span><span class="sxs-lookup"><span data-stu-id="fdb53-208">The remote job, Job4, appears to have failed.</span></span>
<span data-ttu-id="fdb53-209">Вторая команда использует параметр **инклудечилджоб** объекта `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="fdb53-209">The second command uses the **IncludeChildJob** parameter of `Get-Job`.</span></span> <span data-ttu-id="fdb53-210">Выходные данные добавляют дочерние задания всех заданий, имеющих дочерние задания. В этом случае измененные выходные данные показывают, что не удалось выполнить дочернее задание Job5 в Job4.</span><span class="sxs-lookup"><span data-stu-id="fdb53-210">The output adds the child jobs of all jobs that have child jobs.In this case, the revised output shows that only the Job5 child job of Job4 failed.</span></span> <span data-ttu-id="fdb53-211">Третья команда использует параметр **чилджобстате** со значением Failed. выходные данные включают все родительские задания и только дочерние задания, для которых произошел сбой.</span><span class="sxs-lookup"><span data-stu-id="fdb53-211">The third command uses the **ChildJobState** parameter with a value of Failed.The output includes all parent jobs and only the child jobs that failed.</span></span> <span data-ttu-id="fdb53-212">Пятая команда использует свойство **JobStateInfo** заданий и свойство **Reason** для выяснения причины сбоя Job5.</span><span class="sxs-lookup"><span data-stu-id="fdb53-212">The fifth command uses the **JobStateInfo** property of jobs and its **Reason** property to discover why Job5 failed.</span></span>

```
PS C:\> Get-Job
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost            .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02   .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

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

PS C:\> (Get-Job -Name Job5).JobStateInfo.Reason
Connecting to remote server Server01 failed with the following error message:
Access is denied.
```

<span data-ttu-id="fdb53-213">Дополнительные сведения см. в разделе справки [about_Remote_Troubleshooting](./about/about_Remote_Troubleshooting.md) .</span><span class="sxs-lookup"><span data-stu-id="fdb53-213">For more information, see the [about_Remote_Troubleshooting](./about/about_Remote_Troubleshooting.md) Help topic.</span></span>

## <span data-ttu-id="fdb53-214">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fdb53-214">PARAMETERS</span></span>

### <span data-ttu-id="fdb53-215">-After</span><span class="sxs-lookup"><span data-stu-id="fdb53-215">-After</span></span>

<span data-ttu-id="fdb53-216">Возвращает выполненные задания, которые завершились после указанных даты и времени.</span><span class="sxs-lookup"><span data-stu-id="fdb53-216">Gets completed jobs that ended after the specified date and time.</span></span> <span data-ttu-id="fdb53-217">Введите объект **DateTime** , например, возвращаемый `Get-Date` командлетом, или строку, которую можно преобразовать в объект **DateTime** , например `Dec 1, 2012 2:00 AM` или `11/06` .</span><span class="sxs-lookup"><span data-stu-id="fdb53-217">Enter a **DateTime** object, such as one returned by the `Get-Date` cmdlet or a string that can be converted to a **DateTime** object, such as `Dec 1, 2012 2:00 AM` or `11/06`.</span></span>

<span data-ttu-id="fdb53-218">Этот параметр применим только к заданиям настраиваемых типов, таким как задания рабочих процессов и запланированные задания, имеющим свойство **EndTime**.</span><span class="sxs-lookup"><span data-stu-id="fdb53-218">This parameter works only on custom job types, such as workflow jobs and scheduled jobs, that have an **EndTime** property.</span></span> <span data-ttu-id="fdb53-219">Он не работает со стандартными фоновыми заданиями, такими как созданные с помощью `Start-Job` командлета.</span><span class="sxs-lookup"><span data-stu-id="fdb53-219">It does not work on standard background jobs, such as those created by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="fdb53-220">Дополнительные сведения о поддержке данного параметра см. в разделе справки о соответствующем типе заданий.</span><span class="sxs-lookup"><span data-stu-id="fdb53-220">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="fdb53-221">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="fdb53-221">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="fdb53-222">— До</span><span class="sxs-lookup"><span data-stu-id="fdb53-222">-Before</span></span>

<span data-ttu-id="fdb53-223">Возвращает выполненные задания, которые завершились до указанных даты и времени.</span><span class="sxs-lookup"><span data-stu-id="fdb53-223">Gets completed jobs that ended before the specified date and time.</span></span> <span data-ttu-id="fdb53-224">Введите объект **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="fdb53-224">Enter a **DateTime** object.</span></span>

<span data-ttu-id="fdb53-225">Этот параметр применим только к заданиям настраиваемых типов, таким как задания рабочих процессов и запланированные задания, имеющим свойство **EndTime**.</span><span class="sxs-lookup"><span data-stu-id="fdb53-225">This parameter works only on custom job types, such as workflow jobs and scheduled jobs, that have an **EndTime** property.</span></span> <span data-ttu-id="fdb53-226">Он не работает со стандартными фоновыми заданиями, такими как созданные с помощью `Start-Job` командлета.</span><span class="sxs-lookup"><span data-stu-id="fdb53-226">It does not work on standard background jobs, such as those created by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="fdb53-227">Дополнительные сведения о поддержке данного параметра см. в разделе справки о соответствующем типе заданий.</span><span class="sxs-lookup"><span data-stu-id="fdb53-227">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="fdb53-228">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="fdb53-228">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="fdb53-229">-Чилджобстате</span><span class="sxs-lookup"><span data-stu-id="fdb53-229">-ChildJobState</span></span>

<span data-ttu-id="fdb53-230">Возвращает только те дочерние задания, которые находятся в указанном состоянии.</span><span class="sxs-lookup"><span data-stu-id="fdb53-230">Gets only the child jobs that have the specified state.</span></span> <span data-ttu-id="fdb53-231">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="fdb53-231">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="fdb53-232">NotStarted</span><span class="sxs-lookup"><span data-stu-id="fdb53-232">NotStarted</span></span>
- <span data-ttu-id="fdb53-233">Запущен</span><span class="sxs-lookup"><span data-stu-id="fdb53-233">Running</span></span>
- <span data-ttu-id="fdb53-234">Завершено</span><span class="sxs-lookup"><span data-stu-id="fdb53-234">Completed</span></span>
- <span data-ttu-id="fdb53-235">Ошибка</span><span class="sxs-lookup"><span data-stu-id="fdb53-235">Failed</span></span>
- <span data-ttu-id="fdb53-236">Остановлена</span><span class="sxs-lookup"><span data-stu-id="fdb53-236">Stopped</span></span>
- <span data-ttu-id="fdb53-237">Блокировано</span><span class="sxs-lookup"><span data-stu-id="fdb53-237">Blocked</span></span>
- <span data-ttu-id="fdb53-238">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="fdb53-238">Suspended</span></span>
- <span data-ttu-id="fdb53-239">Отключено</span><span class="sxs-lookup"><span data-stu-id="fdb53-239">Disconnected</span></span>
- <span data-ttu-id="fdb53-240">Приостановка</span><span class="sxs-lookup"><span data-stu-id="fdb53-240">Suspending</span></span>
- <span data-ttu-id="fdb53-241">Остановка</span><span class="sxs-lookup"><span data-stu-id="fdb53-241">Stopping</span></span>

<span data-ttu-id="fdb53-242">По умолчанию не `Get-Job` получает дочерних заданий.</span><span class="sxs-lookup"><span data-stu-id="fdb53-242">By default, `Get-Job` does not get child jobs.</span></span> <span data-ttu-id="fdb53-243">С помощью параметра **инклудечилджоб** `Get-Job` получает все дочерние задания.</span><span class="sxs-lookup"><span data-stu-id="fdb53-243">By using the **IncludeChildJob** parameter, `Get-Job` gets all child jobs.</span></span> <span data-ttu-id="fdb53-244">При использовании параметра **ChildJobState** параметр **IncludeChildJob** не действует.</span><span class="sxs-lookup"><span data-stu-id="fdb53-244">If you use the **ChildJobState** parameter, the **IncludeChildJob** parameter has no effect.</span></span>

<span data-ttu-id="fdb53-245">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="fdb53-245">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="fdb53-246">-Command</span><span class="sxs-lookup"><span data-stu-id="fdb53-246">-Command</span></span>

<span data-ttu-id="fdb53-247">Указывает массив команд в виде строк.</span><span class="sxs-lookup"><span data-stu-id="fdb53-247">Specifies an array of commands as strings.</span></span> <span data-ttu-id="fdb53-248">Этот командлет возвращает задания, включающие указанные команды.</span><span class="sxs-lookup"><span data-stu-id="fdb53-248">This cmdlet gets the jobs that include the specified commands.</span></span> <span data-ttu-id="fdb53-249">По умолчанию останавливаются все задания.</span><span class="sxs-lookup"><span data-stu-id="fdb53-249">The default is all jobs.</span></span> <span data-ttu-id="fdb53-250">Для указания шаблона команды можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="fdb53-250">You can use wildcard characters to specify a command pattern.</span></span>

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

### <span data-ttu-id="fdb53-251">-Filter</span><span class="sxs-lookup"><span data-stu-id="fdb53-251">-Filter</span></span>

<span data-ttu-id="fdb53-252">Указывает хэш-таблицу условий.</span><span class="sxs-lookup"><span data-stu-id="fdb53-252">Specifies a hash table of conditions.</span></span> <span data-ttu-id="fdb53-253">Этот командлет возвращает задания, которые отвечают всем условиям.</span><span class="sxs-lookup"><span data-stu-id="fdb53-253">This cmdlet gets jobs that satisfy all of the conditions.</span></span>
<span data-ttu-id="fdb53-254">Введите хэш-таблицу, где ключи являются свойствами заданий, а значения — значениями этих свойств.</span><span class="sxs-lookup"><span data-stu-id="fdb53-254">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="fdb53-255">Этот параметр работает только с пользовательскими типами заданий, такими как задания рабочих процессов и запланированные задания.</span><span class="sxs-lookup"><span data-stu-id="fdb53-255">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span> <span data-ttu-id="fdb53-256">Он не работает со стандартными фоновыми заданиями, такими как созданные с помощью `Start-Job` командлета.</span><span class="sxs-lookup"><span data-stu-id="fdb53-256">It does not work on standard background jobs, such as those created by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="fdb53-257">Дополнительные сведения о поддержке данного параметра см. в разделе справки о соответствующем типе заданий.</span><span class="sxs-lookup"><span data-stu-id="fdb53-257">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="fdb53-258">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="fdb53-258">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="fdb53-259">-Хасморедата</span><span class="sxs-lookup"><span data-stu-id="fdb53-259">-HasMoreData</span></span>

<span data-ttu-id="fdb53-260">Указывает, получает ли этот командлет только задания с указанным значением свойства **хасморедата** .</span><span class="sxs-lookup"><span data-stu-id="fdb53-260">Indicates whether this cmdlet gets only jobs that have the specified **HasMoreData** property value.</span></span>
<span data-ttu-id="fdb53-261">Свойство **HasMoreData** указывает, были ли все результаты задания получены в рамках текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="fdb53-261">The **HasMoreData** property indicates whether all job results have been received in the current session.</span></span> <span data-ttu-id="fdb53-262">Чтобы получить задания с дополнительными результатами, укажите значение `$True` .</span><span class="sxs-lookup"><span data-stu-id="fdb53-262">To get jobs that have more results, specify a value of `$True`.</span></span> <span data-ttu-id="fdb53-263">Чтобы получить задания, которые не имеют дополнительных результатов, укажите значение `$False` .</span><span class="sxs-lookup"><span data-stu-id="fdb53-263">To get jobs that do not have more results, specify a value of `$False`.</span></span>

<span data-ttu-id="fdb53-264">Чтобы получить результаты задания, используйте `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="fdb53-264">To get the results of a job, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="fdb53-265">При использовании `Receive-Job` командлета он удаляет из его хранилища, зависящего от сеанса, возвращаемые результаты.</span><span class="sxs-lookup"><span data-stu-id="fdb53-265">When you use the `Receive-Job` cmdlet, it deletes from its in-memory, session-specific storage the results that it returned.</span></span> <span data-ttu-id="fdb53-266">Когда он возвращает все результаты задания в текущем сеансе, он устанавливает для свойства **хасморедата** задания значение `$False` ), чтобы показать, что оно больше не содержит результатов для задания в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="fdb53-266">When it has returned all results of the job in the current session, it sets the value of the **HasMoreData** property of the job to `$False`) to indicate that it has no more results for the job in the current session.</span></span> <span data-ttu-id="fdb53-267">Используйте параметр **держитесь** параметра, `Receive-Job` чтобы предотвратить `Receive-Job` Удаление результатов и изменение значения свойства **хасморедата** .</span><span class="sxs-lookup"><span data-stu-id="fdb53-267">Use the **Keep** parameter of `Receive-Job` to prevent `Receive-Job` from deleting results and changing the value of the **HasMoreData** property.</span></span>
<span data-ttu-id="fdb53-268">Для получения дополнительных сведений введите `Get-Help Receive-Job`.</span><span class="sxs-lookup"><span data-stu-id="fdb53-268">For more information, type `Get-Help Receive-Job`.</span></span>

<span data-ttu-id="fdb53-269">Свойство **HasMoreData** относится к текущему сеансу.</span><span class="sxs-lookup"><span data-stu-id="fdb53-269">The **HasMoreData** property is specific to the current session.</span></span> <span data-ttu-id="fdb53-270">Если результаты для пользовательского типа задания сохраняются за пределами сеанса, например типа запланированного задания, который сохраняет результаты задания на диске, можно использовать `Receive-Job` командлет в другом сеансе для повторного получения результатов задания, даже если значение **хасморедата** равно `$False` .</span><span class="sxs-lookup"><span data-stu-id="fdb53-270">If results for a custom job type are saved outside of the session, such as the scheduled job type, which saves job results on disk, you can use the `Receive-Job` cmdlet in a different session to get the job results again, even if the value of **HasMoreData** is `$False`.</span></span> <span data-ttu-id="fdb53-271">Подробнее см. в разделах справки по настраиваемому типу задания.</span><span class="sxs-lookup"><span data-stu-id="fdb53-271">For more information, see the help topics for the custom job type.</span></span>

<span data-ttu-id="fdb53-272">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="fdb53-272">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="fdb53-273">-Id</span><span class="sxs-lookup"><span data-stu-id="fdb53-273">-Id</span></span>

<span data-ttu-id="fdb53-274">Указывает массив идентификаторов заданий, которые получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="fdb53-274">Specifies an array of IDs of jobs that this cmdlet gets.</span></span>

<span data-ttu-id="fdb53-275">Идентификатор — это целое число, которое однозначно определяет задание в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="fdb53-275">The ID is an integer that uniquely identifies the job in the current session.</span></span> <span data-ttu-id="fdb53-276">Проще запомнить и ввести, чем идентификатор экземпляра, но он уникален только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="fdb53-276">It is easier to remember and to type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="fdb53-277">Можно ввести один или несколько идентификаторов, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="fdb53-277">You can type one or more IDs separated by commas.</span></span> <span data-ttu-id="fdb53-278">Чтобы найти идентификатор задания, введите `Get-Job` без параметров.</span><span class="sxs-lookup"><span data-stu-id="fdb53-278">To find the ID of a job, type `Get-Job` without parameters.</span></span>

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

### <span data-ttu-id="fdb53-279">-Инклудечилджоб</span><span class="sxs-lookup"><span data-stu-id="fdb53-279">-IncludeChildJob</span></span>

<span data-ttu-id="fdb53-280">Указывает, что этот командлет возвращает дочерние задания в дополнение к родительским заданиям.</span><span class="sxs-lookup"><span data-stu-id="fdb53-280">Indicates that this cmdlet returns child jobs, in addition to parent jobs.</span></span>

<span data-ttu-id="fdb53-281">Этот параметр особенно полезен для изучения заданий рабочего процесса, для которых `Get-Job` возвращается родительское задание контейнера и сбои заданий, поскольку причина сбоя сохраняется в свойстве дочернего задания.</span><span class="sxs-lookup"><span data-stu-id="fdb53-281">This parameter is especially useful for investigating workflow jobs, for which `Get-Job` returns a container parent job, and job failures, because the reason for the failure is saved in a property of the child job.</span></span>

<span data-ttu-id="fdb53-282">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="fdb53-282">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="fdb53-283">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="fdb53-283">-InstanceId</span></span>

<span data-ttu-id="fdb53-284">Указывает массив идентификаторов экземпляров заданий, которые получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="fdb53-284">Specifies an array of instance IDs of jobs that this cmdlet gets.</span></span> <span data-ttu-id="fdb53-285">По умолчанию останавливаются все задания.</span><span class="sxs-lookup"><span data-stu-id="fdb53-285">The default is all jobs.</span></span>

<span data-ttu-id="fdb53-286">Идентификатор экземпляра — это GUID, который однозначно определяет задание на компьютере.</span><span class="sxs-lookup"><span data-stu-id="fdb53-286">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span> <span data-ttu-id="fdb53-287">Чтобы найти идентификатор экземпляра задания, используйте `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="fdb53-287">To find the instance ID of a job, use `Get-Job`.</span></span>

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

### <span data-ttu-id="fdb53-288">-Name</span><span class="sxs-lookup"><span data-stu-id="fdb53-288">-Name</span></span>

<span data-ttu-id="fdb53-289">Указывает массив понятных имен экземпляров заданий, которые получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="fdb53-289">Specifies an array of instance friendly names of jobs that this cmdlet gets.</span></span> <span data-ttu-id="fdb53-290">Введите имя задания или используйте подстановочные знаки для ввода шаблона имени задания.</span><span class="sxs-lookup"><span data-stu-id="fdb53-290">Enter a job name, or use wildcard characters to enter a job name pattern.</span></span> <span data-ttu-id="fdb53-291">По умолчанию `Get-Job` получает все задания в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="fdb53-291">By default, `Get-Job` gets all jobs in the current session.</span></span>

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

### <span data-ttu-id="fdb53-292">— Самый новый</span><span class="sxs-lookup"><span data-stu-id="fdb53-292">-Newest</span></span>

<span data-ttu-id="fdb53-293">Указывает число заданий для получения.</span><span class="sxs-lookup"><span data-stu-id="fdb53-293">Specifies a number of jobs to get.</span></span> <span data-ttu-id="fdb53-294">Этот командлет возвращает задания, которые были завершены недавно.</span><span class="sxs-lookup"><span data-stu-id="fdb53-294">This cmdlet gets the jobs that ended most recently.</span></span>

<span data-ttu-id="fdb53-295">Параметр **Newest** не сортирует задания по времени завершения.</span><span class="sxs-lookup"><span data-stu-id="fdb53-295">The **Newest** parameter does not sort or return the newest jobs in end-time order.</span></span> <span data-ttu-id="fdb53-296">Чтобы отсортировать выходные данные, используйте `Sort-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="fdb53-296">To sort the output, use the `Sort-Object` cmdlet.</span></span>

<span data-ttu-id="fdb53-297">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="fdb53-297">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="fdb53-298">-State</span><span class="sxs-lookup"><span data-stu-id="fdb53-298">-State</span></span>

<span data-ttu-id="fdb53-299">Указывает состояние задания.</span><span class="sxs-lookup"><span data-stu-id="fdb53-299">Specifies a job state.</span></span> <span data-ttu-id="fdb53-300">Этот командлет возвращает только задания в указанном состоянии.</span><span class="sxs-lookup"><span data-stu-id="fdb53-300">This cmdlet gets only jobs in the specified state.</span></span> <span data-ttu-id="fdb53-301">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="fdb53-301">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="fdb53-302">NotStarted</span><span class="sxs-lookup"><span data-stu-id="fdb53-302">NotStarted</span></span>
- <span data-ttu-id="fdb53-303">Запущен</span><span class="sxs-lookup"><span data-stu-id="fdb53-303">Running</span></span>
- <span data-ttu-id="fdb53-304">Завершено</span><span class="sxs-lookup"><span data-stu-id="fdb53-304">Completed</span></span>
- <span data-ttu-id="fdb53-305">Ошибка</span><span class="sxs-lookup"><span data-stu-id="fdb53-305">Failed</span></span>
- <span data-ttu-id="fdb53-306">Остановлена</span><span class="sxs-lookup"><span data-stu-id="fdb53-306">Stopped</span></span>
- <span data-ttu-id="fdb53-307">Блокировано</span><span class="sxs-lookup"><span data-stu-id="fdb53-307">Blocked</span></span>
- <span data-ttu-id="fdb53-308">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="fdb53-308">Suspended</span></span>
- <span data-ttu-id="fdb53-309">Отключено</span><span class="sxs-lookup"><span data-stu-id="fdb53-309">Disconnected</span></span>
- <span data-ttu-id="fdb53-310">Приостановка</span><span class="sxs-lookup"><span data-stu-id="fdb53-310">Suspending</span></span>
- <span data-ttu-id="fdb53-311">Остановка</span><span class="sxs-lookup"><span data-stu-id="fdb53-311">Stopping</span></span>

<span data-ttu-id="fdb53-312">По умолчанию `Get-Job` получает все задания в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="fdb53-312">By default, `Get-Job` gets all the jobs in the current session.</span></span>

<span data-ttu-id="fdb53-313">Дополнительные сведения о состояниях заданий см. в разделе [JobState enumeration](/dotnet/api/system.management.automation.jobstate).</span><span class="sxs-lookup"><span data-stu-id="fdb53-313">For more information about job states, see [JobState Enumeration](/dotnet/api/system.management.automation.jobstate).</span></span>

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

### <span data-ttu-id="fdb53-314">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="fdb53-314">CommonParameters</span></span>

<span data-ttu-id="fdb53-315">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fdb53-315">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fdb53-316">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fdb53-316">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fdb53-317">Входные данные</span><span class="sxs-lookup"><span data-stu-id="fdb53-317">INPUTS</span></span>

### <span data-ttu-id="fdb53-318">Нет</span><span class="sxs-lookup"><span data-stu-id="fdb53-318">None</span></span>

<span data-ttu-id="fdb53-319">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="fdb53-319">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="fdb53-320">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="fdb53-320">OUTPUTS</span></span>

### <span data-ttu-id="fdb53-321">System. Management. Automation. Ремотингжоб</span><span class="sxs-lookup"><span data-stu-id="fdb53-321">System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="fdb53-322">Этот командлет возвращает объекты, представляющие задания в сеансе.</span><span class="sxs-lookup"><span data-stu-id="fdb53-322">This cmdlet returns objects that represent the jobs in the session.</span></span>

## <span data-ttu-id="fdb53-323">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="fdb53-323">NOTES</span></span>

<span data-ttu-id="fdb53-324">Свойство **PSJobTypeName** задания указывает на его тип.</span><span class="sxs-lookup"><span data-stu-id="fdb53-324">The **PSJobTypeName** property of jobs indicates the job type of the job.</span></span> <span data-ttu-id="fdb53-325">Значение свойства определяется автором типа задания.</span><span class="sxs-lookup"><span data-stu-id="fdb53-325">The property value is determined by the job type author.</span></span> <span data-ttu-id="fdb53-326">Ниже приведен список распространенных типов заданий.</span><span class="sxs-lookup"><span data-stu-id="fdb53-326">The following list shows common job types.</span></span>

- <span data-ttu-id="fdb53-327">**Баккграунджоб**.</span><span class="sxs-lookup"><span data-stu-id="fdb53-327">**BackgroundJob**.</span></span> <span data-ttu-id="fdb53-328">Локальное задание запущено с помощью `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="fdb53-328">Local job started by using `Start-Job`.</span></span>
- <span data-ttu-id="fdb53-329">**Ремотежоб**.</span><span class="sxs-lookup"><span data-stu-id="fdb53-329">**RemoteJob**.</span></span> <span data-ttu-id="fdb53-330">Задание запущено в **PSSession** с помощью параметра **AsJob** `Invoke-Command` командлета.</span><span class="sxs-lookup"><span data-stu-id="fdb53-330">Job started in a **PSSession** by using the **AsJob** parameter of the `Invoke-Command` cmdlet.</span></span>
- <span data-ttu-id="fdb53-331">**Псворкфловжоб**.</span><span class="sxs-lookup"><span data-stu-id="fdb53-331">**PSWorkflowJob**.</span></span> <span data-ttu-id="fdb53-332">задание, запущенное с помощью общего параметра **AsJob** рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="fdb53-332">Job started by using the **AsJob** common parameter of workflows.</span></span>

## <span data-ttu-id="fdb53-333">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="fdb53-333">RELATED LINKS</span></span>

[<span data-ttu-id="fdb53-334">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="fdb53-334">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="fdb53-335">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="fdb53-335">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="fdb53-336">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="fdb53-336">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="fdb53-337">Start-Job</span><span class="sxs-lookup"><span data-stu-id="fdb53-337">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="fdb53-338">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="fdb53-338">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="fdb53-339">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="fdb53-339">Wait-Job</span></span>](Wait-Job.md)

[<span data-ttu-id="fdb53-340">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="fdb53-340">about_Jobs</span></span>](About/about_Jobs.md)

[<span data-ttu-id="fdb53-341">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="fdb53-341">about_Job_Details</span></span>](About/about_Job_Details.md)

[<span data-ttu-id="fdb53-342">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="fdb53-342">about_Remote_Jobs</span></span>](About/about_Remote_Jobs.md)
