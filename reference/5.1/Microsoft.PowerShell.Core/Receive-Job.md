---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/receive-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Receive-Job.
ms.openlocfilehash: 7b872c2a28943ee3d2b9ab27459ddb87722cc954
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227085"
---
# <span data-ttu-id="8d1d3-103">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-103">Receive-Job</span></span>

## <span data-ttu-id="8d1d3-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="8d1d3-104">SYNOPSIS</span></span>
<span data-ttu-id="8d1d3-105">Возвращает результаты фоновых заданий PowerShell в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-105">Gets the results of the PowerShell background jobs in the current session.</span></span>

## <span data-ttu-id="8d1d3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8d1d3-106">SYNTAX</span></span>

### <span data-ttu-id="8d1d3-107">Расположение (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8d1d3-107">Location (Default)</span></span>

```
Receive-Job [-Job] <Job[]> [[-Location] <String[]>] [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob]
 [-WriteEvents] [-WriteJobInResults] [<CommonParameters>]
```

### <span data-ttu-id="8d1d3-108">Сеанс</span><span class="sxs-lookup"><span data-stu-id="8d1d3-108">Session</span></span>

```
Receive-Job [-Job] <Job[]> [[-Session] <PSSession[]>] [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob]
 [-WriteEvents] [-WriteJobInResults] [<CommonParameters>]
```

### <span data-ttu-id="8d1d3-109">ИмяКомпьютера</span><span class="sxs-lookup"><span data-stu-id="8d1d3-109">ComputerName</span></span>

```
Receive-Job [-Job] <Job[]> [[-ComputerName] <String[]>] [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob]
 [-WriteEvents] [-WriteJobInResults] [<CommonParameters>]
```

### <span data-ttu-id="8d1d3-110">намепараметерсет</span><span class="sxs-lookup"><span data-stu-id="8d1d3-110">NameParameterSet</span></span>

```
Receive-Job [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob] [-WriteEvents] [-WriteJobInResults]
 [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="8d1d3-111">инстанцеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="8d1d3-111">InstanceIdParameterSet</span></span>

```
Receive-Job [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob] [-WriteEvents] [-WriteJobInResults]
 [-InstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="8d1d3-112">сессионидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="8d1d3-112">SessionIdParameterSet</span></span>

```
Receive-Job [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob] [-WriteEvents] [-WriteJobInResults]
 [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="8d1d3-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8d1d3-113">DESCRIPTION</span></span>

<span data-ttu-id="8d1d3-114">`Receive-Job`Командлет получает результаты фоновых заданий PowerShell, таких как запущенные с помощью `Start-Job` командлета или параметра **AsJob** любого командлета.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-114">The `Receive-Job` cmdlet gets the results of PowerShell background jobs, such as those started by using the `Start-Job` cmdlet or the **AsJob** parameter of any cmdlet.</span></span>
<span data-ttu-id="8d1d3-115">Можно получить результаты всех заданий или указать задания по имени, идентификатору, идентификатору экземпляра, имени компьютера, расположению или сеансу или путем отправки объекта задания.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-115">You can get the results of all jobs or identify jobs by their name, ID, instance ID, computer name, location, or session, or by submitting a job object.</span></span>

<span data-ttu-id="8d1d3-116">При запуске фонового задания PowerShell задание запускается, но результаты не отображаются немедленно.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-116">When you start a PowerShell background job, the job starts, but the results do not appear immediately.</span></span> <span data-ttu-id="8d1d3-117">Вместо этого команда возвращает объект, представляющий фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-117">Instead, the command returns an object that represents the background job.</span></span>
<span data-ttu-id="8d1d3-118">Объект задания содержит полезные сведения о задании, но не содержит результатов.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-118">The job object contains useful information about the job, but it does not contain the results.</span></span>
<span data-ttu-id="8d1d3-119">Этот метод позволяет продолжить работу в сеансе во время выполнения задания.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-119">This method lets you continue to work in the session while the job runs.</span></span>
<span data-ttu-id="8d1d3-120">Дополнительные сведения о фоновых заданиях в PowerShell см. в разделе [about_Jobs](./About/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="8d1d3-120">For more information about background jobs in PowerShell, see [about_Jobs](./About/about_Jobs.md).</span></span>

<span data-ttu-id="8d1d3-121">`Receive-Job`Командлет возвращает результаты, созданные в момент `Receive-Job` отправки команды.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-121">The `Receive-Job` cmdlet gets the results that have been generated by the time that the `Receive-Job` command is submitted.</span></span>
<span data-ttu-id="8d1d3-122">Если результаты еще не завершены, можно выполнить дополнительные команды, `Receive-Job` чтобы получить оставшиеся результаты.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-122">If the results are not yet complete, you can run additional `Receive-Job` commands to get the remaining results.</span></span>

<span data-ttu-id="8d1d3-123">По умолчанию результаты задания удаляются из системы при их получении, однако можно использовать параметр **Keep** для сохранения результатов, чтобы можно было получить их снова.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-123">By default, job results are deleted from the system when you receive them, but you can use the **Keep** parameter to save the results so that you can receive them again.</span></span>
<span data-ttu-id="8d1d3-124">Чтобы удалить результаты задания, выполните `Receive-Job` команду еще раз без параметра **сохранения** , закройте сеанс или используйте `Remove-Job` командлет для удаления задания из сеанса.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-124">To delete the job results, run the `Receive-Job` command again without the **Keep** parameter, close the session, or use the `Remove-Job` cmdlet to delete the job from the session.</span></span>

<span data-ttu-id="8d1d3-125">Начиная с Windows PowerShell 3,0, `Receive-Job` также получает результаты пользовательских типов заданий, таких как задания рабочего процесса и экземпляры запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-125">Starting in Windows PowerShell 3.0, `Receive-Job` also gets the results of custom job types, such as workflow jobs and instances of scheduled jobs.</span></span>
<span data-ttu-id="8d1d3-126">Чтобы обеспечить `Receive-Job` Получение результатов настраиваемого типа задания, импортируйте модуль, который поддерживает пользовательский тип задания, в сеанс перед выполнением `Receive-Job` команды либо с помощью `Import-Module` командлета, либо путем получения командлета в модуле.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-126">To enable `Receive-Job` to get the results a custom job type, import the module that supports the custom job type into the session before it runs a `Receive-Job` command, either by using the `Import-Module` cmdlet or by using or getting a cmdlet in the module.</span></span>
<span data-ttu-id="8d1d3-127">Дополнительные сведения о определенных пользовательских типах заданий см. в разделе документации о данной функции.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-127">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="8d1d3-128">Примеры</span><span class="sxs-lookup"><span data-stu-id="8d1d3-128">EXAMPLES</span></span>

### <span data-ttu-id="8d1d3-129">Пример 1. получение результатов для определенного задания</span><span class="sxs-lookup"><span data-stu-id="8d1d3-129">Example 1: Get results for a particular job</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Process}
Receive-Job -Job $job
```

<span data-ttu-id="8d1d3-130">Эти команды используют параметр **задания** `Receive-Job` для для получения результатов определенного задания.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-130">These commands use the **Job** parameter of `Receive-Job` to get the results of a particular job.</span></span>

<span data-ttu-id="8d1d3-131">Первая команда запускает задание с параметром `Start-Job` и сохраняет объект задания в `$job` переменной.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-131">The first command starts a job with `Start-Job` and stores the job object in the `$job` variable.</span></span>

<span data-ttu-id="8d1d3-132">Вторая команда использует `Receive-Job` командлет для получения результатов задания.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-132">The second command uses the `Receive-Job` cmdlet to get the results of the job.</span></span>
<span data-ttu-id="8d1d3-133">Она использует параметр **Job** для указания задания.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-133">It uses the **Job** parameter to specify the job.</span></span>

### <span data-ttu-id="8d1d3-134">Пример 2. Использование параметра "Держитесь"</span><span class="sxs-lookup"><span data-stu-id="8d1d3-134">Example 2: Use the Keep parameter</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Service dhcp, fakeservice}
$job | Receive-Job -Keep
```

```Output
Cannot find any service with service name 'fakeservice'.
    + CategoryInfo          : ObjectNotFound: (fakeservice:String) [Get-Service], ServiceCommandException
    + FullyQualifiedErrorId : NoServiceFoundForGivenName,Microsoft.PowerShell.Commands.GetServiceCommand
    + PSComputerName        : localhost

Status   Name               DisplayName
------   ----               -----------
Running  dhcp               DHCP Client
```

```powershell
$job | Receive-Job -Keep
```

```output
Cannot find any service with service name 'fakeservice'.
    + CategoryInfo          : ObjectNotFound: (fakeservice:String) [Get-Service], ServiceCommandException
    + FullyQualifiedErrorId : NoServiceFoundForGivenName,Microsoft.PowerShell.Commands.GetServiceCommand
    + PSComputerName        : localhost

Status   Name               DisplayName
------   ----               -----------
Running  dhcp               DHCP Client
```

<span data-ttu-id="8d1d3-135">В этом примере задание сохраняется в `$job` переменной и передает задание в `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-135">This example stores a job in the `$job` variable, and pipes the job to the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="8d1d3-136">`-Keep`Параметр также используется, чтобы разрешить повторное извлечение всех агрегированных данных потока после первого представления.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-136">The `-Keep` parameter is also used to allow all aggregated stream data to be retrieved again after first view.</span></span>

### <span data-ttu-id="8d1d3-137">Пример 3. получение результатов нескольких фоновых заданий</span><span class="sxs-lookup"><span data-stu-id="8d1d3-137">Example 3: Get results of several background jobs</span></span>

<span data-ttu-id="8d1d3-138">При использовании параметра **AsJob** `Invoke-Command` для запуска задания объект задания создается на локальном компьютере, даже если задание выполняется на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-138">When you use the **AsJob** parameter of `Invoke-Command` to start a job, the job object is created on the local computer, even though the job runs on the remote computers.</span></span>
<span data-ttu-id="8d1d3-139">Таким образом, для управления заданием можно использовать локальные команды.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-139">As a result, you use local commands to manage the job.</span></span>

<span data-ttu-id="8d1d3-140">Кроме того, при использовании **AsJob** PowerShell возвращает один объект задания, содержащий дочернее задание для каждого запущенного задания.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-140">Also, when you use **AsJob** , PowerShell returns one job object that contains a child job for each job that was started.</span></span> <span data-ttu-id="8d1d3-141">В этом случае объект задания содержит три дочерних задания (по одному для каждого задания на каждом удаленном компьютере).</span><span class="sxs-lookup"><span data-stu-id="8d1d3-141">In this case, the job object contains three child jobs, one for each job on each remote computer.</span></span>

```powershell
# Use the Invoke-Command cmdlet with the -AsJob parameter to start a background job that runs a Get-Service command on three remote computers.
# Store the resulting job object in the $j variable
$j = Invoke-Command -ComputerName Server01, Server02, Server03 -ScriptBlock {Get-Service} -AsJob
# Display the value of the **ChildJobs** property of the job object in $j.
# The display shows that the command created three child jobs, one for the job on each remote computer.
# You could also use the -IncludeChildJobs parameter of the Get-Job cmdlet.
$j.ChildJobs
```

```Output
Id   Name     State      HasMoreData   Location       Command
--   ----     -----      -----------   --------       -------
2    Job2     Completed  True          Server01       Get-Service
3    Job3     Completed  True          Server02       Get-Service
4    Job4     Completed  True          Server03       Get-Service
```

```powershell
# Use the Receive-Job cmdlet to get the results of just the Job3 child job that ran on the Server02 computer.
# Use the *Keep* parameter to allow you to view the aggregated stream data more than once.
Receive-Job -Name Job3 -Keep
```

```Output
Status  Name        DisplayName                        PSComputerName
------  ----------- -----------                        --------------
Running AeLookupSvc Application Experience             Server02
Stopped ALG         Application Layer Gateway Service  Server02
Running Appinfo     Application Information            Server02
Running AppMgmt     Application Management             Server02
```

### <span data-ttu-id="8d1d3-142">Пример 4. получение результатов фоновых заданий на нескольких удаленных компьютерах</span><span class="sxs-lookup"><span data-stu-id="8d1d3-142">Example 4: Get results of background jobs on multiple remote computers</span></span>

```powershell
# Use the New-PSSession cmdlet to create three user-managed PSSessions on three servers, and save the sessions in the $s variable.
$s = New-PSSession -ComputerName Server01, Server02, Server03
# Use Invoke-Command run a Start-Job command in each of the PSSessions in the $s variable.
# The job outputs the ComputerName of each server.
# Save the job objects in the $j variable.
$j = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {$env:COMPUTERNAME}}
# To confirm that these job objects are from the remote machines, run Get-Job to show no local jobs running.
Get-Job
```

```Output

```

```powershell
# Display the three job objects in $j.
# Note that the Localhost location is not the local computer, but instead localhost as it relates to the job on each Server.
$j
```

```Output
Id   Name     State      HasMoreData   Location   Command
--   ----     -----      -----------   --------   -------
1    Job1     Completed  True          Localhost  $env:COMPUTERNAME
2    Job2     Completed  True          Localhost  $env:COMPUTERNAME
3    Job3     Completed  True          Localhost  $env:COMPUTERNAME
```

```powershell
# Use Invoke-Command to run a Receive-Job command in each of the sessions in the $s variable and save the results in the $Results variable.
# The Receive-Job command must be run in each session because the jobs were run locally on each server.
$results = Invoke-Command -Session $s -ScriptBlock {Receive-Job -Job $Using:j}
```

```Output
Server01
Server02
Server03
```

<span data-ttu-id="8d1d3-143">В этом примере показано, как получить результаты фоновых заданий, выполняющихся на трех удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-143">This example shows how to get the results of background jobs run on three remote computers.</span></span>
<span data-ttu-id="8d1d3-144">В отличие от предыдущего примера, использование `Invoke-Command` для выполнения `Start-Job` команды на самом деле запускает три независимых задания на каждом из трех компьютеров.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-144">Unlike the previous example, using `Invoke-Command` to run the `Start-Job` command actually started three independent jobs on each of the three computers.</span></span> <span data-ttu-id="8d1d3-145">В результате команда вернула три объекта заданий, представляющие три задания, выполняемые локально на трех разных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-145">As a result, the command returned three job objects representing three jobs run locally on three different computers.</span></span>

> [!NOTE]
> <span data-ttu-id="8d1d3-146">В последней команде, поскольку `$j` является локальной переменной, блок скрипта использует модификатор области **using** для определения `$j` переменной.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-146">In the last command, because `$j` is a local variable, the script block uses the **Using** scope modifier to identify the `$j` variable.</span></span> <span data-ttu-id="8d1d3-147">Дополнительные сведения об **использовании** модификатора SCOPE см. в разделе [about_Remote_Variables](./About/about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="8d1d3-147">For more information about the **Using** scope modifier, see [about_Remote_Variables](./About/about_Remote_Variables.md).</span></span>

### <span data-ttu-id="8d1d3-148">Пример 5. доступ к дочерним заданиям</span><span class="sxs-lookup"><span data-stu-id="8d1d3-148">Example 5: Access child jobs</span></span>

<span data-ttu-id="8d1d3-149">`-Keep`Параметр сохраняет состояние агрегированных потоков задания, чтобы его можно было снова просмотреть.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-149">The `-Keep` parameter preserves the state of the aggregated streams of a job so that it can be viewed again.</span></span> <span data-ttu-id="8d1d3-150">Без этого параметра все агрегированные данные потока удаляются при получении задания.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-150">Without this parameter all aggregated stream data is erased when the job is received.</span></span> <span data-ttu-id="8d1d3-151">Дополнительные сведения см. в разделе [about_Job_Details](About/about_Job_Details.md#child-jobs)</span><span class="sxs-lookup"><span data-stu-id="8d1d3-151">For more information, see [about_Job_Details](About/about_Job_Details.md#child-jobs)</span></span>

> [!NOTE]
> <span data-ttu-id="8d1d3-152">Агрегированные потоки включают потоки всех дочерних заданий.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-152">The aggregated streams include the streams of all child jobs.</span></span> <span data-ttu-id="8d1d3-153">Вы по-прежнему можете обращаться к отдельным потокам данных через объект задания и дочерние объекты задания.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-153">You can still reach the individual streams of data through the job object and child job objects.</span></span>

```powershell
Start-Job -Name TestJob -ScriptBlock {dir C:\, Z:\}
# Without the Keep parameter, aggregated child job data is displayed once.
# Then destroyed.
Receive-Job -Name TestJob
```

```output
    Directory: C:\

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-r---        1/24/2019   7:11 AM                Program Files
d-r---        2/13/2019   8:32 AM                Program Files (x86)
d-r---        10/3/2018  11:47 AM                Users
d-----         2/7/2019   1:52 AM                Windows
Cannot find drive. A drive with the name 'Z' does not exist.
    + CategoryInfo          : ObjectNotFound: (Z:String) [Get-ChildItem], DriveNotFoundException
    + FullyQualifiedErrorId : DriveNotFound,Microsoft.PowerShell.Commands.GetChildItemCommand
    + PSComputerName        : localhost
```

```powershell
# It would seem that the child job data is gone.
Receive-Job -Name TestJob
```

```output

```

```powershell
# Using the object model, you can still retrieve child job data and streams.
$job = Get-Job -Name TestJob
$job.ChildJobs[0].Error
```

```output
Cannot find drive. A drive with the name 'Z' does not exist.
    + CategoryInfo          : ObjectNotFound: (Z:String) [Get-ChildItem], DriveNotFoundException
    + FullyQualifiedErrorId : DriveNotFound,Microsoft.PowerShell.Commands.GetChildItemCommand
    + PSComputerName        : localhost
```

## <span data-ttu-id="8d1d3-154">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8d1d3-154">PARAMETERS</span></span>

### <span data-ttu-id="8d1d3-155">-Ауторемовежоб</span><span class="sxs-lookup"><span data-stu-id="8d1d3-155">-AutoRemoveJob</span></span>

<span data-ttu-id="8d1d3-156">Указывает, что этот командлет удаляет задание после того, как оно возвращает результаты задания.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-156">Indicates that this cmdlet deletes the job after it returns the job results.</span></span>
<span data-ttu-id="8d1d3-157">Если задание имеет больше результатов, оно по-прежнему удаляется, но `Receive-Job` отображает сообщение.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-157">If the job has more results, the job is still deleted, but `Receive-Job` displays a message.</span></span>

<span data-ttu-id="8d1d3-158">Этот параметр работает только для настраиваемых типов заданий.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-158">This parameter works only on custom job types.</span></span>
<span data-ttu-id="8d1d3-159">Он предназначен для экземпляров типов заданий, которые сохраняют задание или тип вне сеанса, например для экземпляров запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-159">It is designed for instances of job types that save the job or the type outside of the session, such as instances of scheduled jobs.</span></span>

<span data-ttu-id="8d1d3-160">Этот параметр нельзя использовать без параметра **Wait** .</span><span class="sxs-lookup"><span data-stu-id="8d1d3-160">This parameter cannot be used without the **Wait** parameter.</span></span>

<span data-ttu-id="8d1d3-161">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-161">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8d1d3-162">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="8d1d3-162">-ComputerName</span></span>

<span data-ttu-id="8d1d3-163">Указывает массив имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-163">Specifies an array of names of computers.</span></span>

<span data-ttu-id="8d1d3-164">Этот параметр выбирает результаты задания, которые хранятся на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-164">This parameter selects from among the job results that are stored on the local computer.</span></span>
<span data-ttu-id="8d1d3-165">Он не получает данные для заданий, выполняемых на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-165">It does not get data for jobs run on remote computers.</span></span>
<span data-ttu-id="8d1d3-166">Чтобы получить результаты задания, хранящиеся на удаленных компьютерах, используйте `Invoke-Command` командлет для `Receive-Job` удаленного выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-166">To get job results that are stored on remote computers, use the `Invoke-Command` cmdlet to run a `Receive-Job` command remotely.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerName
Aliases: Cn

Required: False
Position: 1
Default value: All computers available
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="8d1d3-167">-Force</span><span class="sxs-lookup"><span data-stu-id="8d1d3-167">-Force</span></span>

<span data-ttu-id="8d1d3-168">Указывает, что этот командлет продолжает ожидать, если задания находятся в **приостановленном** или **отключенном** состоянии.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-168">Indicates that this cmdlet continues waiting if jobs are in the **Suspended** or **Disconnected** state.</span></span> <span data-ttu-id="8d1d3-169">По умолчанию параметр **Wait** для `Receive-Job` Возвращает или прерывает ожидание, если задания находятся в одном из следующих состояний:</span><span class="sxs-lookup"><span data-stu-id="8d1d3-169">By default, the **Wait** parameter of `Receive-Job` returns, or terminates the wait, when jobs are in one of the following states:</span></span>

- <span data-ttu-id="8d1d3-170">Завершено</span><span class="sxs-lookup"><span data-stu-id="8d1d3-170">Completed</span></span>
- <span data-ttu-id="8d1d3-171">Ошибка</span><span class="sxs-lookup"><span data-stu-id="8d1d3-171">Failed</span></span>
- <span data-ttu-id="8d1d3-172">Остановлена</span><span class="sxs-lookup"><span data-stu-id="8d1d3-172">Stopped</span></span>
- <span data-ttu-id="8d1d3-173">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="8d1d3-173">Suspended</span></span>
- <span data-ttu-id="8d1d3-174">отключен.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-174">Disconnected.</span></span>

<span data-ttu-id="8d1d3-175">Параметр **Force** допустим, только если в команде также используется параметр **Wait**.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-175">The **Force** parameter is valid only when the **Wait** parameter is also used in the command.</span></span>

<span data-ttu-id="8d1d3-176">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-176">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8d1d3-177">-Id</span><span class="sxs-lookup"><span data-stu-id="8d1d3-177">-Id</span></span>

<span data-ttu-id="8d1d3-178">Задает массив идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-178">Specifies an array of IDs.</span></span>
<span data-ttu-id="8d1d3-179">Этот командлет возвращает результаты заданий с указанными идентификаторами.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-179">This cmdlet gets the results of jobs with the specified IDs.</span></span>

<span data-ttu-id="8d1d3-180">Идентификатор — это целое число, которое однозначно определяет задание в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-180">The ID is an integer that uniquely identifies the job in the current session.</span></span>
<span data-ttu-id="8d1d3-181">Проще запомнить и ввести, чем идентификатор экземпляра, но он уникален только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-181">It is easier to remember and type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="8d1d3-182">Можно ввести один или несколько идентификаторов, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-182">You can type one or more IDs separated by commas.</span></span>
<span data-ttu-id="8d1d3-183">Чтобы найти идентификатор задания, используйте `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="8d1d3-183">To find the ID of a job, use `Get-Job`.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8d1d3-184">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="8d1d3-184">-InstanceId</span></span>

<span data-ttu-id="8d1d3-185">Указывает массив идентификаторов экземпляров.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-185">Specifies an array of instance IDs.</span></span>
<span data-ttu-id="8d1d3-186">Этот командлет возвращает результаты заданий с указанными идентификаторами экземпляров.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-186">This cmdlet gets the results of jobs with the specified instance IDs.</span></span>

<span data-ttu-id="8d1d3-187">Идентификатор экземпляра — это GUID, который однозначно определяет задание на компьютере.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-187">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span>
<span data-ttu-id="8d1d3-188">Чтобы найти идентификатор экземпляра задания, используйте `Get-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-188">To find the instance ID of a job, use the `Get-Job` cmdlet.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: All instances
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8d1d3-189">-Job</span><span class="sxs-lookup"><span data-stu-id="8d1d3-189">-Job</span></span>

<span data-ttu-id="8d1d3-190">Указывает задание, для которого получаются результаты.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-190">Specifies the job for which results are being retrieved.</span></span>

<span data-ttu-id="8d1d3-191">Введите переменную, содержащую задание, или команду, которая получает задание.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-191">Enter a variable that contains the job or a command that gets the job.</span></span>
<span data-ttu-id="8d1d3-192">Можно также передать объект задания в `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="8d1d3-192">You can also pipe a job object to `Receive-Job`.</span></span>

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: Location, Session, ComputerName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8d1d3-193">-Держитесь</span><span class="sxs-lookup"><span data-stu-id="8d1d3-193">-Keep</span></span>

<span data-ttu-id="8d1d3-194">Указывает, что этот командлет сохраняет агрегированные потоковые данные в системе даже после их получения.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-194">Indicates that this cmdlet saves the aggregated stream data in the system, even after you have received them.</span></span> <span data-ttu-id="8d1d3-195">По умолчанию агрегированные данные потока удаляются после просмотра с помощью `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="8d1d3-195">By default, aggregated stream data is erased after viewed with `Receive-Job`.</span></span>

<span data-ttu-id="8d1d3-196">Закрытие сеанса или удаление задания с помощью `Remove-Job` командлета также приводит к удалению агрегированных данных потока.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-196">Closing the session, or removing the job with the `Remove-Job` cmdlet also deletes aggregated stream data.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8d1d3-197">— Расположение</span><span class="sxs-lookup"><span data-stu-id="8d1d3-197">-Location</span></span>

<span data-ttu-id="8d1d3-198">Задает массив расположений.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-198">Specifies an array of locations.</span></span>
<span data-ttu-id="8d1d3-199">Этот командлет возвращает только результаты заданий в указанных расположениях.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-199">This cmdlet gets only the results of jobs in the specified locations.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Location
Aliases:

Required: False
Position: 1
Default value: All locations
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8d1d3-200">-Name</span><span class="sxs-lookup"><span data-stu-id="8d1d3-200">-Name</span></span>

<span data-ttu-id="8d1d3-201">Указывает массив понятных имен.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-201">Specifies an array of friendly names.</span></span>
<span data-ttu-id="8d1d3-202">Этот командлет возвращает результаты заданий с указанными именами.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-202">This cmdlet gets the results of jobs that have the specified names.</span></span>
<span data-ttu-id="8d1d3-203">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-203">Wildcard characters are supported.</span></span>

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

### <span data-ttu-id="8d1d3-204">-Неповторение</span><span class="sxs-lookup"><span data-stu-id="8d1d3-204">-NoRecurse</span></span>

<span data-ttu-id="8d1d3-205">Указывает, что этот командлет получает результаты только из указанного задания.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-205">Indicates that this cmdlet gets results only from the specified job.</span></span>
<span data-ttu-id="8d1d3-206">По умолчанию `Receive-Job` также получает результаты всех дочерних заданий указанного задания.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-206">By default, `Receive-Job` also gets the results of all child jobs of the specified job.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8d1d3-207">-Session</span><span class="sxs-lookup"><span data-stu-id="8d1d3-207">-Session</span></span>

<span data-ttu-id="8d1d3-208">Указывает массив сеансов.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-208">Specifies an array of sessions.</span></span>
<span data-ttu-id="8d1d3-209">Этот командлет возвращает результаты заданий, выполненных в указанном сеансе PowerShell ( **PSSession** ).</span><span class="sxs-lookup"><span data-stu-id="8d1d3-209">This cmdlet gets the results of jobs that were run in the specified PowerShell session ( **PSSession** ).</span></span>
<span data-ttu-id="8d1d3-210">Введите переменную, содержащую **PSSession** или команду, которая получает **PSSession** , например `Get-PSSession` команду.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-210">Enter a variable that contains the **PSSession** or a command that gets the **PSSession** , such as a `Get-PSSession` command.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: False
Position: 1
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8d1d3-211">-Wait</span><span class="sxs-lookup"><span data-stu-id="8d1d3-211">-Wait</span></span>

<span data-ttu-id="8d1d3-212">Указывает, что этот командлет подавляет командную строку, пока не будут получены все результаты задания.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-212">Indicates that this cmdlet suppresses the command prompt until all job results are received.</span></span>
<span data-ttu-id="8d1d3-213">По умолчанию `Receive-Job` немедленно возвращает доступные результаты.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-213">By default, `Receive-Job` immediately returns the available results.</span></span>

<span data-ttu-id="8d1d3-214">По умолчанию параметр **Wait** ожидает, пока задание не перейдет в одно из следующих состояний:</span><span class="sxs-lookup"><span data-stu-id="8d1d3-214">By default, the **Wait** parameter waits until the job is in one of the following states:</span></span>

- <span data-ttu-id="8d1d3-215">Завершено</span><span class="sxs-lookup"><span data-stu-id="8d1d3-215">Completed</span></span>
- <span data-ttu-id="8d1d3-216">Ошибка</span><span class="sxs-lookup"><span data-stu-id="8d1d3-216">Failed</span></span>
- <span data-ttu-id="8d1d3-217">Остановлена</span><span class="sxs-lookup"><span data-stu-id="8d1d3-217">Stopped</span></span>
- <span data-ttu-id="8d1d3-218">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="8d1d3-218">Suspended</span></span>
- <span data-ttu-id="8d1d3-219">отключен.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-219">Disconnected.</span></span>

<span data-ttu-id="8d1d3-220">Чтобы указать, что параметр **Wait** должен продолжать ожидание, если состояние задания — suspended или DISCONNECTED, используйте параметр **Force** вместе с параметром **Wait** .</span><span class="sxs-lookup"><span data-stu-id="8d1d3-220">To direct the **Wait** parameter to continue waiting if the job state is Suspended or Disconnected, use the **Force** parameter together with the **Wait** parameter.</span></span>

<span data-ttu-id="8d1d3-221">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-221">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8d1d3-222">-Вритивентс</span><span class="sxs-lookup"><span data-stu-id="8d1d3-222">-WriteEvents</span></span>

<span data-ttu-id="8d1d3-223">Указывает, что этот командлет сообщает об изменениях в состоянии задания, пока он ожидает завершения задания.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-223">Indicates that this cmdlet reports changes in the job state while it waits for the job to finish.</span></span>

<span data-ttu-id="8d1d3-224">Этот параметр допустим, только если параметр **Wait** используется в команде и опущен параметр **Keep**.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-224">This parameter is valid only when the **Wait** parameter is used in the command and the **Keep** parameter is omitted.</span></span>

<span data-ttu-id="8d1d3-225">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-225">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8d1d3-226">-Вритежобинресултс</span><span class="sxs-lookup"><span data-stu-id="8d1d3-226">-WriteJobInResults</span></span>

<span data-ttu-id="8d1d3-227">Указывает, что этот командлет возвращает объект задания, за которым следуют результаты.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-227">Indicates that this cmdlet returns the job object followed by the results.</span></span>

<span data-ttu-id="8d1d3-228">Этот параметр допустим, только если параметр **Wait** используется в команде и опущен параметр **Keep**.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-228">This parameter is valid only when the **Wait** parameter is used in the command and the **Keep** parameter is omitted.</span></span>

<span data-ttu-id="8d1d3-229">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-229">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8d1d3-230">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="8d1d3-230">CommonParameters</span></span>

<span data-ttu-id="8d1d3-231">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-231">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8d1d3-232">См. сведения в разделе [about_CommonParameters](./About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="8d1d3-232">For more information, see [about_CommonParameters](./About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="8d1d3-233">Входные данные</span><span class="sxs-lookup"><span data-stu-id="8d1d3-233">INPUTS</span></span>

### <span data-ttu-id="8d1d3-234">System. Management. Automation. job</span><span class="sxs-lookup"><span data-stu-id="8d1d3-234">System.Management.Automation.Job</span></span>

<span data-ttu-id="8d1d3-235">К этому командлету можно передать объекты заданий.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-235">You can pipe job objects to this cmdlet.</span></span>

## <span data-ttu-id="8d1d3-236">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="8d1d3-236">OUTPUTS</span></span>

### <span data-ttu-id="8d1d3-237">PSObject</span><span class="sxs-lookup"><span data-stu-id="8d1d3-237">PSObject</span></span>

<span data-ttu-id="8d1d3-238">Этот командлет возвращает результаты выполнения команд в задании.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-238">This cmdlet returns the results of the commands in the job.</span></span>

## <span data-ttu-id="8d1d3-239">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="8d1d3-239">NOTES</span></span>

## <span data-ttu-id="8d1d3-240">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="8d1d3-240">RELATED LINKS</span></span>

[<span data-ttu-id="8d1d3-241">Get-Job.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-241">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="8d1d3-242">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="8d1d3-242">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="8d1d3-243">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="8d1d3-243">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="8d1d3-244">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="8d1d3-244">Resume-Job</span></span>](Resume-Job.md)

[<span data-ttu-id="8d1d3-245">Start-Job</span><span class="sxs-lookup"><span data-stu-id="8d1d3-245">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="8d1d3-246">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="8d1d3-246">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="8d1d3-247">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="8d1d3-247">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="8d1d3-248">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="8d1d3-248">Wait-Job</span></span>](Wait-Job.md)
