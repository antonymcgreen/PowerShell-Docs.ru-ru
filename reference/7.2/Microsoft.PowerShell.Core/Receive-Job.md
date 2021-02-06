---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/receive-job?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Receive-Job.
ms.openlocfilehash: 3a11bdb27f3fe16b7b66e82821a3ffe8fa5f6cfa
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605550"
---
# <span data-ttu-id="54d75-102">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="54d75-102">Receive-Job</span></span>

## <span data-ttu-id="54d75-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="54d75-103">SYNOPSIS</span></span>
<span data-ttu-id="54d75-104">Возвращает результаты фоновых заданий PowerShell в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="54d75-104">Gets the results of the PowerShell background jobs in the current session.</span></span>

## <span data-ttu-id="54d75-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="54d75-105">SYNTAX</span></span>

### <span data-ttu-id="54d75-106">Расположение (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="54d75-106">Location (Default)</span></span>

```
Receive-Job [-Job] <Job[]> [[-Location] <String[]>] [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob]
 [-WriteEvents] [-WriteJobInResults] [<CommonParameters>]
```

### <span data-ttu-id="54d75-107">ИмяКомпьютера</span><span class="sxs-lookup"><span data-stu-id="54d75-107">ComputerName</span></span>

```
Receive-Job [-Job] <Job[]> [[-ComputerName] <String[]>] [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob]
 [-WriteEvents] [-WriteJobInResults] [<CommonParameters>]
```

### <span data-ttu-id="54d75-108">Сеанс</span><span class="sxs-lookup"><span data-stu-id="54d75-108">Session</span></span>

```
Receive-Job [-Job] <Job[]> [[-Session] <PSSession[]>] [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob]
 [-WriteEvents] [-WriteJobInResults] [<CommonParameters>]
```

### <span data-ttu-id="54d75-109">намепараметерсет</span><span class="sxs-lookup"><span data-stu-id="54d75-109">NameParameterSet</span></span>

```
Receive-Job [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob] [-WriteEvents] [-WriteJobInResults]
 [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="54d75-110">инстанцеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="54d75-110">InstanceIdParameterSet</span></span>

```
Receive-Job [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob] [-WriteEvents] [-WriteJobInResults]
 [-InstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="54d75-111">сессионидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="54d75-111">SessionIdParameterSet</span></span>

```
Receive-Job [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob] [-WriteEvents] [-WriteJobInResults]
 [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="54d75-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="54d75-112">DESCRIPTION</span></span>

<span data-ttu-id="54d75-113">`Receive-Job`Командлет получает результаты фоновых заданий PowerShell, таких как запущенные с помощью `Start-Job` командлета или параметра **AsJob** любого командлета.</span><span class="sxs-lookup"><span data-stu-id="54d75-113">The `Receive-Job` cmdlet gets the results of PowerShell background jobs, such as those started by using the `Start-Job` cmdlet or the **AsJob** parameter of any cmdlet.</span></span>
<span data-ttu-id="54d75-114">Можно получить результаты всех заданий или указать задания по имени, идентификатору, идентификатору экземпляра, имени компьютера, расположению или сеансу или путем отправки объекта задания.</span><span class="sxs-lookup"><span data-stu-id="54d75-114">You can get the results of all jobs or identify jobs by their name, ID, instance ID, computer name, location, or session, or by submitting a job object.</span></span>

<span data-ttu-id="54d75-115">При запуске фонового задания PowerShell задание запускается, но результаты не отображаются немедленно.</span><span class="sxs-lookup"><span data-stu-id="54d75-115">When you start a PowerShell background job, the job starts, but the results do not appear immediately.</span></span> <span data-ttu-id="54d75-116">Вместо этого команда возвращает объект, представляющий фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="54d75-116">Instead, the command returns an object that represents the background job.</span></span>
<span data-ttu-id="54d75-117">Объект задания содержит полезные сведения о задании, но не содержит результатов.</span><span class="sxs-lookup"><span data-stu-id="54d75-117">The job object contains useful information about the job, but it does not contain the results.</span></span>
<span data-ttu-id="54d75-118">Этот метод позволяет продолжить работу в сеансе во время выполнения задания.</span><span class="sxs-lookup"><span data-stu-id="54d75-118">This method lets you continue to work in the session while the job runs.</span></span>
<span data-ttu-id="54d75-119">Дополнительные сведения о фоновых заданиях в PowerShell см. в разделе [about_Jobs](./About/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="54d75-119">For more information about background jobs in PowerShell, see [about_Jobs](./About/about_Jobs.md).</span></span>

<span data-ttu-id="54d75-120">`Receive-Job`Командлет возвращает результаты, созданные в момент `Receive-Job` отправки команды.</span><span class="sxs-lookup"><span data-stu-id="54d75-120">The `Receive-Job` cmdlet gets the results that have been generated by the time that the `Receive-Job` command is submitted.</span></span>
<span data-ttu-id="54d75-121">Если результаты еще не завершены, можно выполнить дополнительные команды, `Receive-Job` чтобы получить оставшиеся результаты.</span><span class="sxs-lookup"><span data-stu-id="54d75-121">If the results are not yet complete, you can run additional `Receive-Job` commands to get the remaining results.</span></span>

<span data-ttu-id="54d75-122">По умолчанию результаты задания удаляются из системы при их получении, однако можно использовать параметр **Keep** для сохранения результатов, чтобы можно было получить их снова.</span><span class="sxs-lookup"><span data-stu-id="54d75-122">By default, job results are deleted from the system when you receive them, but you can use the **Keep** parameter to save the results so that you can receive them again.</span></span>
<span data-ttu-id="54d75-123">Чтобы удалить результаты задания, выполните `Receive-Job` команду еще раз без параметра **сохранения** , закройте сеанс или используйте `Remove-Job` командлет для удаления задания из сеанса.</span><span class="sxs-lookup"><span data-stu-id="54d75-123">To delete the job results, run the `Receive-Job` command again without the **Keep** parameter, close the session, or use the `Remove-Job` cmdlet to delete the job from the session.</span></span>

<span data-ttu-id="54d75-124">Начиная с Windows PowerShell 3,0, `Receive-Job` также получает результаты пользовательских типов заданий, таких как задания рабочего процесса и экземпляры запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="54d75-124">Starting in Windows PowerShell 3.0, `Receive-Job` also gets the results of custom job types, such as workflow jobs and instances of scheduled jobs.</span></span>
<span data-ttu-id="54d75-125">Чтобы обеспечить `Receive-Job` Получение результатов настраиваемого типа задания, импортируйте модуль, который поддерживает пользовательский тип задания, в сеанс перед выполнением `Receive-Job` команды либо с помощью `Import-Module` командлета, либо путем получения командлета в модуле.</span><span class="sxs-lookup"><span data-stu-id="54d75-125">To enable `Receive-Job` to get the results a custom job type, import the module that supports the custom job type into the session before it runs a `Receive-Job` command, either by using the `Import-Module` cmdlet or by using or getting a cmdlet in the module.</span></span>
<span data-ttu-id="54d75-126">Дополнительные сведения о определенных пользовательских типах заданий см. в разделе документации о данной функции.</span><span class="sxs-lookup"><span data-stu-id="54d75-126">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="54d75-127">Примеры</span><span class="sxs-lookup"><span data-stu-id="54d75-127">EXAMPLES</span></span>

### <span data-ttu-id="54d75-128">Пример 1. получение результатов для определенного задания</span><span class="sxs-lookup"><span data-stu-id="54d75-128">Example 1: Get results for a particular job</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Process}
Receive-Job -Job $job
```

<span data-ttu-id="54d75-129">Эти команды используют параметр **задания** `Receive-Job` для для получения результатов определенного задания.</span><span class="sxs-lookup"><span data-stu-id="54d75-129">These commands use the **Job** parameter of `Receive-Job` to get the results of a particular job.</span></span>

<span data-ttu-id="54d75-130">Первая команда запускает задание с параметром `Start-Job` и сохраняет объект задания в `$job` переменной.</span><span class="sxs-lookup"><span data-stu-id="54d75-130">The first command starts a job with `Start-Job` and stores the job object in the `$job` variable.</span></span>

<span data-ttu-id="54d75-131">Вторая команда использует `Receive-Job` командлет для получения результатов задания.</span><span class="sxs-lookup"><span data-stu-id="54d75-131">The second command uses the `Receive-Job` cmdlet to get the results of the job.</span></span>
<span data-ttu-id="54d75-132">Она использует параметр **Job** для указания задания.</span><span class="sxs-lookup"><span data-stu-id="54d75-132">It uses the **Job** parameter to specify the job.</span></span>

### <span data-ttu-id="54d75-133">Пример 2. Использование параметра "Держитесь"</span><span class="sxs-lookup"><span data-stu-id="54d75-133">Example 2: Use the Keep parameter</span></span>

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

```Output
Cannot find any service with service name 'fakeservice'.
    + CategoryInfo          : ObjectNotFound: (fakeservice:String) [Get-Service], ServiceCommandException
    + FullyQualifiedErrorId : NoServiceFoundForGivenName,Microsoft.PowerShell.Commands.GetServiceCommand
    + PSComputerName        : localhost

Status   Name               DisplayName
------   ----               -----------
Running  dhcp               DHCP Client
```

<span data-ttu-id="54d75-134">В этом примере задание сохраняется в `$job` переменной и передает задание в `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="54d75-134">This example stores a job in the `$job` variable, and pipes the job to the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="54d75-135">`-Keep`Параметр также используется, чтобы разрешить повторное извлечение всех агрегированных данных потока после первого представления.</span><span class="sxs-lookup"><span data-stu-id="54d75-135">The `-Keep` parameter is also used to allow all aggregated stream data to be retrieved again after first view.</span></span>

### <span data-ttu-id="54d75-136">Пример 3. получение результатов нескольких фоновых заданий</span><span class="sxs-lookup"><span data-stu-id="54d75-136">Example 3: Get results of several background jobs</span></span>

<span data-ttu-id="54d75-137">При использовании параметра **AsJob** `Invoke-Command` для запуска задания объект задания создается на локальном компьютере, даже если задание выполняется на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="54d75-137">When you use the **AsJob** parameter of `Invoke-Command` to start a job, the job object is created on the local computer, even though the job runs on the remote computers.</span></span>
<span data-ttu-id="54d75-138">Таким образом, для управления заданием можно использовать локальные команды.</span><span class="sxs-lookup"><span data-stu-id="54d75-138">As a result, you use local commands to manage the job.</span></span>

<span data-ttu-id="54d75-139">Кроме того, при использовании **AsJob** PowerShell возвращает один объект задания, содержащий дочернее задание для каждого запущенного задания.</span><span class="sxs-lookup"><span data-stu-id="54d75-139">Also, when you use **AsJob**, PowerShell returns one job object that contains a child job for each job that was started.</span></span> <span data-ttu-id="54d75-140">В этом случае объект задания содержит три дочерних задания (по одному для каждого задания на каждом удаленном компьютере).</span><span class="sxs-lookup"><span data-stu-id="54d75-140">In this case, the job object contains three child jobs, one for each job on each remote computer.</span></span>

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

### <span data-ttu-id="54d75-141">Пример 4. получение результатов фоновых заданий на нескольких удаленных компьютерах</span><span class="sxs-lookup"><span data-stu-id="54d75-141">Example 4: Get results of background jobs on multiple remote computers</span></span>

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

<span data-ttu-id="54d75-142">В этом примере показано, как получить результаты фоновых заданий, выполняющихся на трех удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="54d75-142">This example shows how to get the results of background jobs run on three remote computers.</span></span>
<span data-ttu-id="54d75-143">В отличие от предыдущего примера, использование `Invoke-Command` для выполнения `Start-Job` команды на самом деле запускает три независимых задания на каждом из трех компьютеров.</span><span class="sxs-lookup"><span data-stu-id="54d75-143">Unlike the previous example, using `Invoke-Command` to run the `Start-Job` command actually started three independent jobs on each of the three computers.</span></span> <span data-ttu-id="54d75-144">В результате команда вернула три объекта заданий, представляющие три задания, выполняемые локально на трех разных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="54d75-144">As a result, the command returned three job objects representing three jobs run locally on three different computers.</span></span>

> [!NOTE]
> <span data-ttu-id="54d75-145">В последней команде, поскольку `$j` является локальной переменной, блок скрипта использует модификатор области **using** для определения `$j` переменной.</span><span class="sxs-lookup"><span data-stu-id="54d75-145">In the last command, because `$j` is a local variable, the script block uses the **Using** scope modifier to identify the `$j` variable.</span></span> <span data-ttu-id="54d75-146">Дополнительные сведения об **использовании** модификатора SCOPE см. в разделе [about_Remote_Variables](./About/about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="54d75-146">For more information about the **Using** scope modifier, see [about_Remote_Variables](./About/about_Remote_Variables.md).</span></span>

### <span data-ttu-id="54d75-147">Пример 5. доступ к дочерним заданиям</span><span class="sxs-lookup"><span data-stu-id="54d75-147">Example 5: Access child jobs</span></span>

<span data-ttu-id="54d75-148">`-Keep`Параметр сохраняет состояние агрегированных потоков задания, чтобы его можно было снова просмотреть.</span><span class="sxs-lookup"><span data-stu-id="54d75-148">The `-Keep` parameter preserves the state of the aggregated streams of a job so that it can be viewed again.</span></span> <span data-ttu-id="54d75-149">Без этого параметра все агрегированные данные потока удаляются при получении задания.</span><span class="sxs-lookup"><span data-stu-id="54d75-149">Without this parameter all aggregated stream data is erased when the job is received.</span></span> <span data-ttu-id="54d75-150">Дополнительные сведения см. в разделе [about_Job_Details](About/about_Job_Details.md#child-jobs)</span><span class="sxs-lookup"><span data-stu-id="54d75-150">For more information, see [about_Job_Details](About/about_Job_Details.md#child-jobs)</span></span>

> [!NOTE]
> <span data-ttu-id="54d75-151">Агрегированные потоки включают потоки всех дочерних заданий.</span><span class="sxs-lookup"><span data-stu-id="54d75-151">The aggregated streams include the streams of all child jobs.</span></span> <span data-ttu-id="54d75-152">Вы по-прежнему можете обращаться к отдельным потокам данных через объект задания и дочерние объекты задания.</span><span class="sxs-lookup"><span data-stu-id="54d75-152">You can still reach the individual streams of data through the job object and child job objects.</span></span>

```powershell
Start-Job -Name TestJob -ScriptBlock {dir C:\, Z:\}
# Without the Keep parameter, aggregated child job data is displayed once.
# Then destroyed.
Receive-Job -Name TestJob
```

```Output
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

```Output

```

```powershell
# Using the object model, you can still retrieve child job data and streams.
$job = Get-Job -Name TestJob
$job.ChildJobs[0].Error
```

```Output
Cannot find drive. A drive with the name 'Z' does not exist.
    + CategoryInfo          : ObjectNotFound: (Z:String) [Get-ChildItem], DriveNotFoundException
    + FullyQualifiedErrorId : DriveNotFound,Microsoft.PowerShell.Commands.GetChildItemCommand
    + PSComputerName        : localhost
```

## <span data-ttu-id="54d75-153">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="54d75-153">PARAMETERS</span></span>

### <span data-ttu-id="54d75-154">-Ауторемовежоб</span><span class="sxs-lookup"><span data-stu-id="54d75-154">-AutoRemoveJob</span></span>

<span data-ttu-id="54d75-155">Указывает, что этот командлет удаляет задание после того, как оно возвращает результаты задания.</span><span class="sxs-lookup"><span data-stu-id="54d75-155">Indicates that this cmdlet deletes the job after it returns the job results.</span></span>
<span data-ttu-id="54d75-156">Если задание имеет больше результатов, оно по-прежнему удаляется, но `Receive-Job` отображает сообщение.</span><span class="sxs-lookup"><span data-stu-id="54d75-156">If the job has more results, the job is still deleted, but `Receive-Job` displays a message.</span></span>

<span data-ttu-id="54d75-157">Этот параметр работает только для настраиваемых типов заданий.</span><span class="sxs-lookup"><span data-stu-id="54d75-157">This parameter works only on custom job types.</span></span>
<span data-ttu-id="54d75-158">Он предназначен для экземпляров типов заданий, которые сохраняют задание или тип вне сеанса, например для экземпляров запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="54d75-158">It is designed for instances of job types that save the job or the type outside of the session, such as instances of scheduled jobs.</span></span>

<span data-ttu-id="54d75-159">Этот параметр нельзя использовать без параметра **Wait** .</span><span class="sxs-lookup"><span data-stu-id="54d75-159">This parameter cannot be used without the **Wait** parameter.</span></span>

<span data-ttu-id="54d75-160">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="54d75-160">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="54d75-161">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="54d75-161">-ComputerName</span></span>

<span data-ttu-id="54d75-162">Указывает массив имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="54d75-162">Specifies an array of names of computers.</span></span>

<span data-ttu-id="54d75-163">Этот параметр выбирает результаты задания, которые хранятся на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="54d75-163">This parameter selects from among the job results that are stored on the local computer.</span></span>
<span data-ttu-id="54d75-164">Он не получает данные для заданий, выполняемых на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="54d75-164">It does not get data for jobs run on remote computers.</span></span>
<span data-ttu-id="54d75-165">Чтобы получить результаты задания, хранящиеся на удаленных компьютерах, используйте `Invoke-Command` командлет для `Receive-Job` удаленного выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="54d75-165">To get job results that are stored on remote computers, use the `Invoke-Command` cmdlet to run a `Receive-Job` command remotely.</span></span>

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

### <span data-ttu-id="54d75-166">-Force</span><span class="sxs-lookup"><span data-stu-id="54d75-166">-Force</span></span>

<span data-ttu-id="54d75-167">Указывает, что этот командлет продолжает ожидать, если задания находятся в **приостановленном** или **отключенном** состоянии.</span><span class="sxs-lookup"><span data-stu-id="54d75-167">Indicates that this cmdlet continues waiting if jobs are in the **Suspended** or **Disconnected** state.</span></span> <span data-ttu-id="54d75-168">По умолчанию параметр **Wait** для `Receive-Job` Возвращает или прерывает ожидание, если задания находятся в одном из следующих состояний:</span><span class="sxs-lookup"><span data-stu-id="54d75-168">By default, the **Wait** parameter of `Receive-Job` returns, or terminates the wait, when jobs are in one of the following states:</span></span>

- <span data-ttu-id="54d75-169">Завершено</span><span class="sxs-lookup"><span data-stu-id="54d75-169">Completed</span></span>
- <span data-ttu-id="54d75-170">Ошибка</span><span class="sxs-lookup"><span data-stu-id="54d75-170">Failed</span></span>
- <span data-ttu-id="54d75-171">Остановлена</span><span class="sxs-lookup"><span data-stu-id="54d75-171">Stopped</span></span>
- <span data-ttu-id="54d75-172">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="54d75-172">Suspended</span></span>
- <span data-ttu-id="54d75-173">отключен.</span><span class="sxs-lookup"><span data-stu-id="54d75-173">Disconnected.</span></span>

<span data-ttu-id="54d75-174">Параметр **Force** допустим, только если в команде также используется параметр **Wait**.</span><span class="sxs-lookup"><span data-stu-id="54d75-174">The **Force** parameter is valid only when the **Wait** parameter is also used in the command.</span></span>

<span data-ttu-id="54d75-175">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="54d75-175">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="54d75-176">-Id</span><span class="sxs-lookup"><span data-stu-id="54d75-176">-Id</span></span>

<span data-ttu-id="54d75-177">Задает массив идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="54d75-177">Specifies an array of IDs.</span></span>
<span data-ttu-id="54d75-178">Этот командлет возвращает результаты заданий с указанными идентификаторами.</span><span class="sxs-lookup"><span data-stu-id="54d75-178">This cmdlet gets the results of jobs with the specified IDs.</span></span>

<span data-ttu-id="54d75-179">Идентификатор — это целое число, которое однозначно определяет задание в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="54d75-179">The ID is an integer that uniquely identifies the job in the current session.</span></span>
<span data-ttu-id="54d75-180">Проще запомнить и ввести, чем идентификатор экземпляра, но он уникален только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="54d75-180">It is easier to remember and type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="54d75-181">Можно ввести один или несколько идентификаторов, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="54d75-181">You can type one or more IDs separated by commas.</span></span>
<span data-ttu-id="54d75-182">Чтобы найти идентификатор задания, используйте `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="54d75-182">To find the ID of a job, use `Get-Job`.</span></span>

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

### <span data-ttu-id="54d75-183">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="54d75-183">-InstanceId</span></span>

<span data-ttu-id="54d75-184">Указывает массив идентификаторов экземпляров.</span><span class="sxs-lookup"><span data-stu-id="54d75-184">Specifies an array of instance IDs.</span></span>
<span data-ttu-id="54d75-185">Этот командлет возвращает результаты заданий с указанными идентификаторами экземпляров.</span><span class="sxs-lookup"><span data-stu-id="54d75-185">This cmdlet gets the results of jobs with the specified instance IDs.</span></span>

<span data-ttu-id="54d75-186">Идентификатор экземпляра — это GUID, который однозначно определяет задание на компьютере.</span><span class="sxs-lookup"><span data-stu-id="54d75-186">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span>
<span data-ttu-id="54d75-187">Чтобы найти идентификатор экземпляра задания, используйте `Get-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="54d75-187">To find the instance ID of a job, use the `Get-Job` cmdlet.</span></span>

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

### <span data-ttu-id="54d75-188">-Job</span><span class="sxs-lookup"><span data-stu-id="54d75-188">-Job</span></span>

<span data-ttu-id="54d75-189">Указывает задание, для которого получаются результаты.</span><span class="sxs-lookup"><span data-stu-id="54d75-189">Specifies the job for which results are being retrieved.</span></span>

<span data-ttu-id="54d75-190">Введите переменную, содержащую задание, или команду, которая получает задание.</span><span class="sxs-lookup"><span data-stu-id="54d75-190">Enter a variable that contains the job or a command that gets the job.</span></span>
<span data-ttu-id="54d75-191">Можно также передать объект задания в `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="54d75-191">You can also pipe a job object to `Receive-Job`.</span></span>

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

### <span data-ttu-id="54d75-192">-Держитесь</span><span class="sxs-lookup"><span data-stu-id="54d75-192">-Keep</span></span>

<span data-ttu-id="54d75-193">Указывает, что этот командлет сохраняет агрегированные потоковые данные в системе даже после их получения.</span><span class="sxs-lookup"><span data-stu-id="54d75-193">Indicates that this cmdlet saves the aggregated stream data in the system, even after you have received them.</span></span> <span data-ttu-id="54d75-194">По умолчанию агрегированные данные потока удаляются после просмотра с помощью `Receive-Job` .</span><span class="sxs-lookup"><span data-stu-id="54d75-194">By default, aggregated stream data is erased after viewed with `Receive-Job`.</span></span>

<span data-ttu-id="54d75-195">Закрытие сеанса или удаление задания с помощью `Remove-Job` командлета также приводит к удалению агрегированных данных потока.</span><span class="sxs-lookup"><span data-stu-id="54d75-195">Closing the session, or removing the job with the `Remove-Job` cmdlet also deletes aggregated stream data.</span></span>

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

### <span data-ttu-id="54d75-196">— Расположение</span><span class="sxs-lookup"><span data-stu-id="54d75-196">-Location</span></span>

<span data-ttu-id="54d75-197">Задает массив расположений.</span><span class="sxs-lookup"><span data-stu-id="54d75-197">Specifies an array of locations.</span></span>
<span data-ttu-id="54d75-198">Этот командлет возвращает только результаты заданий в указанных расположениях.</span><span class="sxs-lookup"><span data-stu-id="54d75-198">This cmdlet gets only the results of jobs in the specified locations.</span></span>

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

### <span data-ttu-id="54d75-199">-Name</span><span class="sxs-lookup"><span data-stu-id="54d75-199">-Name</span></span>

<span data-ttu-id="54d75-200">Указывает массив понятных имен.</span><span class="sxs-lookup"><span data-stu-id="54d75-200">Specifies an array of friendly names.</span></span>
<span data-ttu-id="54d75-201">Этот командлет возвращает результаты заданий с указанными именами.</span><span class="sxs-lookup"><span data-stu-id="54d75-201">This cmdlet gets the results of jobs that have the specified names.</span></span>
<span data-ttu-id="54d75-202">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="54d75-202">Wildcard characters are supported.</span></span>

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

### <span data-ttu-id="54d75-203">-Неповторение</span><span class="sxs-lookup"><span data-stu-id="54d75-203">-NoRecurse</span></span>

<span data-ttu-id="54d75-204">Указывает, что этот командлет получает результаты только из указанного задания.</span><span class="sxs-lookup"><span data-stu-id="54d75-204">Indicates that this cmdlet gets results only from the specified job.</span></span>
<span data-ttu-id="54d75-205">По умолчанию `Receive-Job` также получает результаты всех дочерних заданий указанного задания.</span><span class="sxs-lookup"><span data-stu-id="54d75-205">By default, `Receive-Job` also gets the results of all child jobs of the specified job.</span></span>

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

### <span data-ttu-id="54d75-206">-Session</span><span class="sxs-lookup"><span data-stu-id="54d75-206">-Session</span></span>

<span data-ttu-id="54d75-207">Указывает массив сеансов.</span><span class="sxs-lookup"><span data-stu-id="54d75-207">Specifies an array of sessions.</span></span>
<span data-ttu-id="54d75-208">Этот командлет возвращает результаты заданий, выполненных в указанном сеансе PowerShell (**PSSession**).</span><span class="sxs-lookup"><span data-stu-id="54d75-208">This cmdlet gets the results of jobs that were run in the specified PowerShell session (**PSSession**).</span></span>
<span data-ttu-id="54d75-209">Введите переменную, содержащую **PSSession** или команду, которая получает **PSSession**, например `Get-PSSession` команду.</span><span class="sxs-lookup"><span data-stu-id="54d75-209">Enter a variable that contains the **PSSession** or a command that gets the **PSSession**, such as a `Get-PSSession` command.</span></span>

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

### <span data-ttu-id="54d75-210">-Wait</span><span class="sxs-lookup"><span data-stu-id="54d75-210">-Wait</span></span>

<span data-ttu-id="54d75-211">Указывает, что этот командлет подавляет командную строку, пока не будут получены все результаты задания.</span><span class="sxs-lookup"><span data-stu-id="54d75-211">Indicates that this cmdlet suppresses the command prompt until all job results are received.</span></span>
<span data-ttu-id="54d75-212">По умолчанию `Receive-Job` немедленно возвращает доступные результаты.</span><span class="sxs-lookup"><span data-stu-id="54d75-212">By default, `Receive-Job` immediately returns the available results.</span></span>

<span data-ttu-id="54d75-213">По умолчанию параметр **Wait** ожидает, пока задание не перейдет в одно из следующих состояний:</span><span class="sxs-lookup"><span data-stu-id="54d75-213">By default, the **Wait** parameter waits until the job is in one of the following states:</span></span>

- <span data-ttu-id="54d75-214">Завершено</span><span class="sxs-lookup"><span data-stu-id="54d75-214">Completed</span></span>
- <span data-ttu-id="54d75-215">Ошибка</span><span class="sxs-lookup"><span data-stu-id="54d75-215">Failed</span></span>
- <span data-ttu-id="54d75-216">Остановлена</span><span class="sxs-lookup"><span data-stu-id="54d75-216">Stopped</span></span>
- <span data-ttu-id="54d75-217">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="54d75-217">Suspended</span></span>
- <span data-ttu-id="54d75-218">отключен.</span><span class="sxs-lookup"><span data-stu-id="54d75-218">Disconnected.</span></span>

<span data-ttu-id="54d75-219">Чтобы указать, что параметр **Wait** должен продолжать ожидание, если состояние задания — suspended или DISCONNECTED, используйте параметр **Force** вместе с параметром **Wait** .</span><span class="sxs-lookup"><span data-stu-id="54d75-219">To direct the **Wait** parameter to continue waiting if the job state is Suspended or Disconnected, use the **Force** parameter together with the **Wait** parameter.</span></span>

<span data-ttu-id="54d75-220">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="54d75-220">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="54d75-221">-Вритивентс</span><span class="sxs-lookup"><span data-stu-id="54d75-221">-WriteEvents</span></span>

<span data-ttu-id="54d75-222">Указывает, что этот командлет сообщает об изменениях в состоянии задания, пока он ожидает завершения задания.</span><span class="sxs-lookup"><span data-stu-id="54d75-222">Indicates that this cmdlet reports changes in the job state while it waits for the job to finish.</span></span>

<span data-ttu-id="54d75-223">Этот параметр допустим, только если параметр **Wait** используется в команде и опущен параметр **Keep**.</span><span class="sxs-lookup"><span data-stu-id="54d75-223">This parameter is valid only when the **Wait** parameter is used in the command and the **Keep** parameter is omitted.</span></span>

<span data-ttu-id="54d75-224">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="54d75-224">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="54d75-225">-Вритежобинресултс</span><span class="sxs-lookup"><span data-stu-id="54d75-225">-WriteJobInResults</span></span>

<span data-ttu-id="54d75-226">Указывает, что этот командлет возвращает объект задания, за которым следуют результаты.</span><span class="sxs-lookup"><span data-stu-id="54d75-226">Indicates that this cmdlet returns the job object followed by the results.</span></span>

<span data-ttu-id="54d75-227">Этот параметр допустим, только если параметр **Wait** используется в команде и опущен параметр **Keep**.</span><span class="sxs-lookup"><span data-stu-id="54d75-227">This parameter is valid only when the **Wait** parameter is used in the command and the **Keep** parameter is omitted.</span></span>

<span data-ttu-id="54d75-228">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="54d75-228">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="54d75-229">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="54d75-229">CommonParameters</span></span>

<span data-ttu-id="54d75-230">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="54d75-230">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="54d75-231">См. сведения в разделе [about_CommonParameters](./About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="54d75-231">For more information, see [about_CommonParameters](./About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="54d75-232">Входные данные</span><span class="sxs-lookup"><span data-stu-id="54d75-232">INPUTS</span></span>

### <span data-ttu-id="54d75-233">System. Management. Automation. job</span><span class="sxs-lookup"><span data-stu-id="54d75-233">System.Management.Automation.Job</span></span>

<span data-ttu-id="54d75-234">К этому командлету можно передать объекты заданий.</span><span class="sxs-lookup"><span data-stu-id="54d75-234">You can pipe job objects to this cmdlet.</span></span>

## <span data-ttu-id="54d75-235">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="54d75-235">OUTPUTS</span></span>

### <span data-ttu-id="54d75-236">PSObject</span><span class="sxs-lookup"><span data-stu-id="54d75-236">PSObject</span></span>

<span data-ttu-id="54d75-237">Этот командлет возвращает результаты выполнения команд в задании.</span><span class="sxs-lookup"><span data-stu-id="54d75-237">This cmdlet returns the results of the commands in the job.</span></span>

## <span data-ttu-id="54d75-238">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="54d75-238">NOTES</span></span>

## <span data-ttu-id="54d75-239">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="54d75-239">RELATED LINKS</span></span>

[<span data-ttu-id="54d75-240">Get-Job.</span><span class="sxs-lookup"><span data-stu-id="54d75-240">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="54d75-241">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="54d75-241">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="54d75-242">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="54d75-242">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="54d75-243">Start-Job</span><span class="sxs-lookup"><span data-stu-id="54d75-243">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="54d75-244">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="54d75-244">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="54d75-245">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="54d75-245">Wait-Job</span></span>](Wait-Job.md)

