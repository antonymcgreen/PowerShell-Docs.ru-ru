---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/stop-job?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Job.
ms.openlocfilehash: 56dc7462e2625768db8b52370d3b7d38c8defafe
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94387266"
---
# <span data-ttu-id="cc65d-103">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="cc65d-103">Stop-Job</span></span>

## <span data-ttu-id="cc65d-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="cc65d-104">SYNOPSIS</span></span>
<span data-ttu-id="cc65d-105">Останавливает фоновое задание PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc65d-105">Stops a PowerShell background job.</span></span>

## <span data-ttu-id="cc65d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cc65d-106">SYNTAX</span></span>

### <span data-ttu-id="cc65d-107">Сессионидпараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="cc65d-107">SessionIdParameterSet (Default)</span></span>

```
Stop-Job [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cc65d-108">жобпараметерсет</span><span class="sxs-lookup"><span data-stu-id="cc65d-108">JobParameterSet</span></span>

```
Stop-Job [-Job] <Job[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cc65d-109">намепараметерсет</span><span class="sxs-lookup"><span data-stu-id="cc65d-109">NameParameterSet</span></span>

```
Stop-Job [-PassThru] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cc65d-110">инстанцеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="cc65d-110">InstanceIdParameterSet</span></span>

```
Stop-Job [-PassThru] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cc65d-111">статепараметерсет</span><span class="sxs-lookup"><span data-stu-id="cc65d-111">StateParameterSet</span></span>

```
Stop-Job [-PassThru] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cc65d-112">филтерпараметерсет</span><span class="sxs-lookup"><span data-stu-id="cc65d-112">FilterParameterSet</span></span>

```
Stop-Job [-PassThru] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="cc65d-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cc65d-113">DESCRIPTION</span></span>

<span data-ttu-id="cc65d-114">`Stop-Job`Командлет останавливает выполняемые фоновые задания PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc65d-114">The `Stop-Job` cmdlet stops PowerShell background jobs that are in progress.</span></span> <span data-ttu-id="cc65d-115">С помощью этого командлета можно прерывать все задания или прекращать выполнение выбранных заданий по имени, ИДЕНТИФИКАТОРу, ИДЕНТИФИКАТОРу экземпляра или состоянию, передавая объект задания в `Stop-Job` .</span><span class="sxs-lookup"><span data-stu-id="cc65d-115">You can use this cmdlet to stop all jobs or stop selected jobs based on their name, ID, instance ID, or state, or by passing a job object to `Stop-Job`.</span></span>

<span data-ttu-id="cc65d-116">Можно использовать `Stop-Job` для завершения фоновых заданий, например тех, которые были запущены с помощью `Start-Job` командлета или параметра **AsJob** любого командлета.</span><span class="sxs-lookup"><span data-stu-id="cc65d-116">You can use `Stop-Job` to stop background jobs, such as those that were started by using the `Start-Job` cmdlet or the **AsJob** parameter of any cmdlet.</span></span> <span data-ttu-id="cc65d-117">При прекращении фонового задания PowerShell завершает все задачи, ожидающие в этой очереди заданий, а затем завершает задание.</span><span class="sxs-lookup"><span data-stu-id="cc65d-117">When you stop a background job, PowerShell completes all tasks that are pending in that job queue and then ends the job.</span></span> <span data-ttu-id="cc65d-118">Новые задания не добавляются в очередь после отправки этой команды.</span><span class="sxs-lookup"><span data-stu-id="cc65d-118">No new tasks are added to the queue after this command is submitted.</span></span>

<span data-ttu-id="cc65d-119">Этот командлет не удаляет фоновые задания.</span><span class="sxs-lookup"><span data-stu-id="cc65d-119">This cmdlet does not delete background jobs.</span></span> <span data-ttu-id="cc65d-120">Чтобы удалить задание, используйте `Remove-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="cc65d-120">To delete a job, use the `Remove-Job` cmdlet.</span></span>

<span data-ttu-id="cc65d-121">Начиная с Windows PowerShell 3,0, `Stop-Job` также останавливаются пользовательские типы заданий, такие как задания рабочего процесса и экземпляры запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="cc65d-121">Starting in Windows PowerShell 3.0, `Stop-Job` also stops custom job types, such as workflow jobs and instances of scheduled jobs.</span></span> <span data-ttu-id="cc65d-122">Чтобы включить функцию `Stop-Job` для отмены задания с настраиваемым типом задания, импортируйте модуль, который поддерживает тип настраиваемого задания, в сеанс перед выполнением `Stop-Job` команды либо с помощью `Import-Module` командлета, либо с помощью или получения командлета в модуле.</span><span class="sxs-lookup"><span data-stu-id="cc65d-122">To enable `Stop-Job` to stop a job with custom job type, import the module that supports the custom job type into the session before you run a `Stop-Job` command, either by using the `Import-Module` cmdlet or by using or getting a cmdlet in the module.</span></span> <span data-ttu-id="cc65d-123">Дополнительные сведения о определенных пользовательских типах заданий см. в разделе документации о данной функции.</span><span class="sxs-lookup"><span data-stu-id="cc65d-123">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="cc65d-124">Примеры</span><span class="sxs-lookup"><span data-stu-id="cc65d-124">EXAMPLES</span></span>

### <span data-ttu-id="cc65d-125">Пример 1. Отмена задания на удаленном компьютере с помощью Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="cc65d-125">Example 1: Stop a job on a remote computer by using Invoke-Command</span></span>

```powershell
$s = New-PSSession -ComputerName Server01 -Credential Domain01\Admin02
$j = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Invoke-Command -Session $s -ScriptBlock { Stop-job -Job $Using:j }
```

<span data-ttu-id="cc65d-126">В этом примере показано, как использовать `Stop-Job` командлет для завершения задания, выполняемого на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cc65d-126">This example shows how to use the `Stop-Job` cmdlet to stop a job that is running on a remote computer.</span></span>

<span data-ttu-id="cc65d-127">Так как задание было запущено с помощью `Invoke-Command` командлета для `Start-Job` удаленного выполнения команды, объект задания хранится на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cc65d-127">Because the job was started by using the `Invoke-Command` cmdlet to run a `Start-Job` command remotely, the job object is stored on the remote computer.</span></span> <span data-ttu-id="cc65d-128">`Invoke-Command`Для удаленного выполнения команды необходимо использовать другую команду `Stop-Job` .</span><span class="sxs-lookup"><span data-stu-id="cc65d-128">You must use another `Invoke-Command` command to run a `Stop-Job` command remotely.</span></span> <span data-ttu-id="cc65d-129">Дополнительные сведения об удаленных фоновых заданиях см. в разделе about_Remote_Jobs.</span><span class="sxs-lookup"><span data-stu-id="cc65d-129">For more information about remote background jobs, see about_Remote_Jobs.</span></span>

<span data-ttu-id="cc65d-130">Первая команда создает сеанс PowerShell ( **PSSession** ) на компьютере Server01, а затем сохраняет объект сеанса в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="cc65d-130">The first command creates a PowerShell session ( **PSSession** ) on the Server01 computer, and then stores the session object in the `$s` variable.</span></span> <span data-ttu-id="cc65d-131">Команда использует учетные данные администратора домена.</span><span class="sxs-lookup"><span data-stu-id="cc65d-131">The command uses the credentials of a domain administrator.</span></span>

<span data-ttu-id="cc65d-132">Вторая команда использует `Invoke-Command` командлет для выполнения `Start-Job` команды в сеансе.</span><span class="sxs-lookup"><span data-stu-id="cc65d-132">The second command uses the `Invoke-Command` cmdlet to run a `Start-Job` command in the session.</span></span> <span data-ttu-id="cc65d-133">Команда в задании получает все события в системном журнале событий.</span><span class="sxs-lookup"><span data-stu-id="cc65d-133">The command in the job gets all of the events in the System event log.</span></span> <span data-ttu-id="cc65d-134">Результирующий объект задания хранится в `$j` переменной.</span><span class="sxs-lookup"><span data-stu-id="cc65d-134">The resulting job object is stored in the `$j` variable.</span></span>

<span data-ttu-id="cc65d-135">Третья команда останавливает задание.</span><span class="sxs-lookup"><span data-stu-id="cc65d-135">The third command stops the job.</span></span> <span data-ttu-id="cc65d-136">Он использует `Invoke-Command` командлет для выполнения `Stop-Job` команды в **сеансе PSSession** на Server01.</span><span class="sxs-lookup"><span data-stu-id="cc65d-136">It uses the `Invoke-Command` cmdlet to run a `Stop-Job` command in the **PSSession** on Server01.</span></span> <span data-ttu-id="cc65d-137">Поскольку объекты задания хранятся в среде `$j` , которая является переменной на локальном компьютере, команда использует модификатор области using для определения `$j` в качестве локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="cc65d-137">Because the job objects are stored in `$j`, which is a variable on the local computer, the command uses the Using scope modifier to identify `$j` as a local variable.</span></span>
<span data-ttu-id="cc65d-138">Дополнительные сведения об использовании модификатора SCOPE см. в разделе [about_Remote_Variables](about/about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="cc65d-138">For more information about the Using scope modifier, see [about_Remote_Variables](about/about_Remote_Variables.md).</span></span>

<span data-ttu-id="cc65d-139">По завершении выполнения команды задание останавливается, а **сеанс PSSession** `$s` доступен для использования.</span><span class="sxs-lookup"><span data-stu-id="cc65d-139">When the command finishes, the job is stopped and the **PSSession** in `$s` is available for use.</span></span>

### <span data-ttu-id="cc65d-140">Пример 2. завершение фонового задания</span><span class="sxs-lookup"><span data-stu-id="cc65d-140">Example 2: Stop a background job</span></span>

```powershell
Stop-Job -Name "Job1"
```

<span data-ttu-id="cc65d-141">Эта команда останавливает фоновое задание Job1.</span><span class="sxs-lookup"><span data-stu-id="cc65d-141">This command stops the Job1 background job.</span></span>

### <span data-ttu-id="cc65d-142">Пример 3. завершение нескольких фоновых заданий</span><span class="sxs-lookup"><span data-stu-id="cc65d-142">Example 3: Stop several background jobs</span></span>

```powershell
Stop-Job -Id 1, 3, 4
```

<span data-ttu-id="cc65d-143">Эта команда останавливает три задания.</span><span class="sxs-lookup"><span data-stu-id="cc65d-143">This command stops three jobs.</span></span>
<span data-ttu-id="cc65d-144">Она определяет их по идентификаторам.</span><span class="sxs-lookup"><span data-stu-id="cc65d-144">It identifies them by their IDs.</span></span>

### <span data-ttu-id="cc65d-145">Пример 4. завершение всех фоновых заданий</span><span class="sxs-lookup"><span data-stu-id="cc65d-145">Example 4: Stop all background jobs</span></span>

```powershell
Get-Job | Stop-Job
```

<span data-ttu-id="cc65d-146">Эта команда останавливает все фоновые задания в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="cc65d-146">This command stops all of the background jobs in the current session.</span></span>

### <span data-ttu-id="cc65d-147">Пример 5. завершение всех заблокированных фоновых заданий</span><span class="sxs-lookup"><span data-stu-id="cc65d-147">Example 5: Stop all blocked background jobs</span></span>

```powershell
Stop-Job -State Blocked
```

<span data-ttu-id="cc65d-148">Эта команда останавливает все задания, которые заблокированы.</span><span class="sxs-lookup"><span data-stu-id="cc65d-148">This command stops all the jobs that are blocked.</span></span>

### <span data-ttu-id="cc65d-149">Пример 6. завершение задания с помощью идентификатора экземпляра</span><span class="sxs-lookup"><span data-stu-id="cc65d-149">Example 6: Stop a job by using an instance ID</span></span>

```powershell
Get-Job | Format-Table ID, Name, Command, @{Label="State";Expression={$_.JobStateInfo.State}},
InstanceID -Auto
```

```Output
Id Name Command                 State  InstanceId
-- ---- -------                 -----  ----------
1 Job1 start-service schedule Running 05abb67a-2932-4bd5-b331-c0254b8d9146
3 Job3 start-service schedule Running c03cbd45-19f3-4558-ba94-ebe41b68ad03
5 Job5 get-service s*         Blocked e3bbfed1-9c53-401a-a2c3-a8db34336adf
```

```powershell
Stop-Job -InstanceId e3bbfed1-9c53-401a-a2c3-a8db34336adf
```

<span data-ttu-id="cc65d-150">Эти команды позволяют остановить задание, указав идентификатор экземпляра.</span><span class="sxs-lookup"><span data-stu-id="cc65d-150">These commands show how to stop a job based on its instance ID.</span></span>

<span data-ttu-id="cc65d-151">Первая команда использует `Get-Job` командлет для получения заданий в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="cc65d-151">The first command uses the `Get-Job` cmdlet to get the jobs in the current session.</span></span> <span data-ttu-id="cc65d-152">Команда использует оператор конвейера ( `|` ) для отправки заданий в `Format-Table` команду, которая отображает таблицу с указанными свойствами каждого задания.</span><span class="sxs-lookup"><span data-stu-id="cc65d-152">The command uses a pipeline operator (`|`) to send the jobs to a `Format-Table` command, which displays a table of the specified properties of each job.</span></span> <span data-ttu-id="cc65d-153">Таблица содержит идентификатор экземпляра каждого задания.</span><span class="sxs-lookup"><span data-stu-id="cc65d-153">The table includes the Instance ID of each job.</span></span> <span data-ttu-id="cc65d-154">Для отображения состояния задания используется вычисляемое свойство.</span><span class="sxs-lookup"><span data-stu-id="cc65d-154">It uses a calculated property to display the job state.</span></span>

<span data-ttu-id="cc65d-155">Вторая команда использует `Stop-Job` команду с параметром **InstanceId** для завершения выбранного задания.</span><span class="sxs-lookup"><span data-stu-id="cc65d-155">The second command uses a `Stop-Job` command that has the **InstanceID** parameter to stop a selected job.</span></span>

### <span data-ttu-id="cc65d-156">Пример 7. завершение задания на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="cc65d-156">Example 7: Stop a job on a remote computer</span></span>

```powershell
$j = Invoke-Command -ComputerName Server01 -ScriptBlock {Get-EventLog System} -AsJob
$j | Stop-Job -PassThru
```

```Output
Id    Name    State      HasMoreData     Location         Command
--    ----    ----       -----------     --------         -------
5     Job5    Stopped    True            user01-tablet    get-eventlog system
```

<span data-ttu-id="cc65d-157">В этом примере показано, как использовать `Stop-Job` командлет для завершения задания, выполняемого на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cc65d-157">This example shows how to use the `Stop-Job` cmdlet to stop a job that is running on a remote computer.</span></span>

<span data-ttu-id="cc65d-158">Так как задание было запущено с помощью параметра **AsJob** `Invoke-Command` командлета, объект задания находится на локальном компьютере, даже если задание выполняется на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cc65d-158">Because the job was started by using the **AsJob** parameter of the `Invoke-Command` cmdlet, the job object is located on the local computer, even though the job runs on the remote computer.</span></span> <span data-ttu-id="cc65d-159">Таким образом, для завершения задания можно использовать локальную `Stop-Job` команду.</span><span class="sxs-lookup"><span data-stu-id="cc65d-159">Therefore, you can use a local `Stop-Job` command to stop the job.</span></span>

<span data-ttu-id="cc65d-160">Первая команда использует `Invoke-Command` командлет для запуска фонового задания на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="cc65d-160">The first command uses the `Invoke-Command` cmdlet to start a background job on the Server01 computer.</span></span> <span data-ttu-id="cc65d-161">Параметр **AsJob** применяется для выполнения удаленной команды в качестве фонового задания.</span><span class="sxs-lookup"><span data-stu-id="cc65d-161">The command uses the **AsJob** parameter to run the remote command as a background job.</span></span>

<span data-ttu-id="cc65d-162">Эта команда возвращает объект задания, который является тем же объектом задания, который `Start-Job` возвращает командлет.</span><span class="sxs-lookup"><span data-stu-id="cc65d-162">This command returns a job object, which is the same job object that the `Start-Job` cmdlet returns.</span></span>
<span data-ttu-id="cc65d-163">Команда сохраняет объект задания в `$j` переменной.</span><span class="sxs-lookup"><span data-stu-id="cc65d-163">The command saves the job object in the `$j` variable.</span></span>

<span data-ttu-id="cc65d-164">Вторая команда использует оператор конвейера для отправки задания в `$j` переменной в `Stop-Job` .</span><span class="sxs-lookup"><span data-stu-id="cc65d-164">The second command uses a pipeline operator to send the job in the `$j` variable to `Stop-Job`.</span></span> <span data-ttu-id="cc65d-165">Команда использует параметр **PassThru** для направления `Stop-Job` возврата объекта задания.</span><span class="sxs-lookup"><span data-stu-id="cc65d-165">The command uses the **PassThru** parameter to direct `Stop-Job` to return a job object.</span></span> <span data-ttu-id="cc65d-166">Отобразится объект задания, подтверждающий, что состояние задания остановлено.</span><span class="sxs-lookup"><span data-stu-id="cc65d-166">The job object display confirms that the state of the job is Stopped.</span></span>

<span data-ttu-id="cc65d-167">Дополнительные сведения об удаленных фоновых заданиях см. в разделе about_Remote_Jobs.</span><span class="sxs-lookup"><span data-stu-id="cc65d-167">For more information about remote background jobs, see about_Remote_Jobs.</span></span>

## <span data-ttu-id="cc65d-168">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cc65d-168">PARAMETERS</span></span>

### <span data-ttu-id="cc65d-169">-Filter</span><span class="sxs-lookup"><span data-stu-id="cc65d-169">-Filter</span></span>

<span data-ttu-id="cc65d-170">Указывает хэш-таблицу условий.</span><span class="sxs-lookup"><span data-stu-id="cc65d-170">Specifies a hash table of conditions.</span></span> <span data-ttu-id="cc65d-171">Этот командлет останавливает задания, которые отвечают всем условиям.</span><span class="sxs-lookup"><span data-stu-id="cc65d-171">This cmdlet stops jobs that satisfy all of the conditions.</span></span>
<span data-ttu-id="cc65d-172">Введите хэш-таблицу, где ключи являются свойствами заданий, а значения — значениями этих свойств.</span><span class="sxs-lookup"><span data-stu-id="cc65d-172">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="cc65d-173">Этот параметр работает только с пользовательскими типами заданий, такими как задания рабочих процессов и запланированные задания.</span><span class="sxs-lookup"><span data-stu-id="cc65d-173">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span> <span data-ttu-id="cc65d-174">Он не работает со стандартными фоновыми заданиями, такими как созданные с помощью `Start-Job` командлета.</span><span class="sxs-lookup"><span data-stu-id="cc65d-174">It does not work on standard background jobs, such as those created by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="cc65d-175">Дополнительные сведения о поддержке данного параметра см. в разделе справки о соответствующем типе заданий.</span><span class="sxs-lookup"><span data-stu-id="cc65d-175">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="cc65d-176">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="cc65d-176">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="cc65d-177">-Id</span><span class="sxs-lookup"><span data-stu-id="cc65d-177">-Id</span></span>

<span data-ttu-id="cc65d-178">Указывает идентификаторы заданий, которые останавливаются этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="cc65d-178">Specifies the IDs of jobs that this cmdlet stops.</span></span> <span data-ttu-id="cc65d-179">По умолчанию останавливаются все задания в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="cc65d-179">The default is all jobs in the current session.</span></span>

<span data-ttu-id="cc65d-180">Идентификатор — это целое число, которое однозначно определяет задание в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="cc65d-180">The ID is an integer that uniquely identifies the job in the current session.</span></span> <span data-ttu-id="cc65d-181">Проще запомнить и ввести, чем идентификатор экземпляра, но он уникален только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="cc65d-181">It is easier to remember and type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="cc65d-182">Можно ввести один или несколько идентификаторов, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="cc65d-182">You can type one or more IDs, separated by commas.</span></span> <span data-ttu-id="cc65d-183">Чтобы найти идентификатор задания, введите `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="cc65d-183">To find the ID of a job, type `Get-Job`.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cc65d-184">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="cc65d-184">-InstanceId</span></span>

<span data-ttu-id="cc65d-185">Указывает идентификаторы экземпляров заданий, которые останавливает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="cc65d-185">Specifies the instance IDs of jobs that this cmdlet stops.</span></span> <span data-ttu-id="cc65d-186">По умолчанию останавливаются все задания.</span><span class="sxs-lookup"><span data-stu-id="cc65d-186">The default is all jobs.</span></span>

<span data-ttu-id="cc65d-187">Идентификатор экземпляра — это GUID, который однозначно определяет задание на компьютере.</span><span class="sxs-lookup"><span data-stu-id="cc65d-187">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span> <span data-ttu-id="cc65d-188">Чтобы найти идентификатор экземпляра задания, используйте `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="cc65d-188">To find the instance ID of a job, use `Get-Job`.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cc65d-189">-Job</span><span class="sxs-lookup"><span data-stu-id="cc65d-189">-Job</span></span>

<span data-ttu-id="cc65d-190">Указывает задания, которые останавливаются этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="cc65d-190">Specifies the jobs that this cmdlet stops.</span></span> <span data-ttu-id="cc65d-191">Введите переменную, содержащую задания, либо команду, которая их возвращают.</span><span class="sxs-lookup"><span data-stu-id="cc65d-191">Enter a variable that contains the jobs or a command that gets the jobs.</span></span> <span data-ttu-id="cc65d-192">Можно также использовать оператор конвейера для отправки заданий в `Stop-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="cc65d-192">You can also use a pipeline operator to submit jobs to the `Stop-Job` cmdlet.</span></span> <span data-ttu-id="cc65d-193">По умолчанию `Stop-Job` удаляет все задания, запущенные в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="cc65d-193">By default, `Stop-Job` deletes all jobs that were started in the current session.</span></span>

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="cc65d-194">-Name</span><span class="sxs-lookup"><span data-stu-id="cc65d-194">-Name</span></span>

<span data-ttu-id="cc65d-195">Указывает понятные имена заданий, которые остановит этот командлет.</span><span class="sxs-lookup"><span data-stu-id="cc65d-195">Specifies friendly names of jobs that this cmdlet stops.</span></span> <span data-ttu-id="cc65d-196">Введите имена заданий в списке с разделителями запятыми или используйте подстановочные знаки (\*) для ввода шаблона имени задания.</span><span class="sxs-lookup"><span data-stu-id="cc65d-196">Enter the job names in a comma-separated list or use wildcard characters (\*) to enter a job name pattern.</span></span> <span data-ttu-id="cc65d-197">По умолчанию `Stop-Job` останавливает все задания, созданные в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="cc65d-197">By default, `Stop-Job` stops all jobs created in the current session.</span></span>

<span data-ttu-id="cc65d-198">Так как понятное имя не обязательно должно быть уникальным, используйте параметры **WhatIf** и **Confirm** при остановке заданий по имени.</span><span class="sxs-lookup"><span data-stu-id="cc65d-198">Because the friendly name is not guaranteed to be unique, use the **WhatIf** and **Confirm** parameters when stopping jobs by name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="cc65d-199">-PassThru</span><span class="sxs-lookup"><span data-stu-id="cc65d-199">-PassThru</span></span>

<span data-ttu-id="cc65d-200">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="cc65d-200">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="cc65d-201">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="cc65d-201">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="cc65d-202">-State</span><span class="sxs-lookup"><span data-stu-id="cc65d-202">-State</span></span>

<span data-ttu-id="cc65d-203">Указывает состояние задания.</span><span class="sxs-lookup"><span data-stu-id="cc65d-203">Specifies a job state.</span></span> <span data-ttu-id="cc65d-204">Этот командлет останавливает только задания в указанном состоянии.</span><span class="sxs-lookup"><span data-stu-id="cc65d-204">This cmdlet stops only jobs in the specified state.</span></span> <span data-ttu-id="cc65d-205">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="cc65d-205">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="cc65d-206">NotStarted</span><span class="sxs-lookup"><span data-stu-id="cc65d-206">NotStarted</span></span>
- <span data-ttu-id="cc65d-207">Запущен</span><span class="sxs-lookup"><span data-stu-id="cc65d-207">Running</span></span>
- <span data-ttu-id="cc65d-208">Завершено</span><span class="sxs-lookup"><span data-stu-id="cc65d-208">Completed</span></span>
- <span data-ttu-id="cc65d-209">Ошибка</span><span class="sxs-lookup"><span data-stu-id="cc65d-209">Failed</span></span>
- <span data-ttu-id="cc65d-210">Остановлена</span><span class="sxs-lookup"><span data-stu-id="cc65d-210">Stopped</span></span>
- <span data-ttu-id="cc65d-211">Блокировано</span><span class="sxs-lookup"><span data-stu-id="cc65d-211">Blocked</span></span>
- <span data-ttu-id="cc65d-212">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="cc65d-212">Suspended</span></span>
- <span data-ttu-id="cc65d-213">Отключено</span><span class="sxs-lookup"><span data-stu-id="cc65d-213">Disconnected</span></span>
- <span data-ttu-id="cc65d-214">Приостановка</span><span class="sxs-lookup"><span data-stu-id="cc65d-214">Suspending</span></span>
- <span data-ttu-id="cc65d-215">Остановка</span><span class="sxs-lookup"><span data-stu-id="cc65d-215">Stopping</span></span>

<span data-ttu-id="cc65d-216">Дополнительные сведения о состояниях заданий см. в разделе [JobState enumeration](/dotnet/api/system.management.automation.jobstate).</span><span class="sxs-lookup"><span data-stu-id="cc65d-216">For more information about job states, see [JobState Enumeration](/dotnet/api/system.management.automation.jobstate).</span></span>

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cc65d-217">-Confirm</span><span class="sxs-lookup"><span data-stu-id="cc65d-217">-Confirm</span></span>

<span data-ttu-id="cc65d-218">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="cc65d-218">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cc65d-219">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="cc65d-219">-WhatIf</span></span>

<span data-ttu-id="cc65d-220">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="cc65d-220">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="cc65d-221">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="cc65d-221">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cc65d-222">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="cc65d-222">CommonParameters</span></span>

<span data-ttu-id="cc65d-223">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="cc65d-223">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cc65d-224">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="cc65d-224">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cc65d-225">Входные данные</span><span class="sxs-lookup"><span data-stu-id="cc65d-225">INPUTS</span></span>

### <span data-ttu-id="cc65d-226">System. Management. Automation. Ремотингжоб</span><span class="sxs-lookup"><span data-stu-id="cc65d-226">System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="cc65d-227">Объект задания можно передать в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="cc65d-227">You can pipe a job object to this cmdlet.</span></span>

## <span data-ttu-id="cc65d-228">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="cc65d-228">OUTPUTS</span></span>

### <span data-ttu-id="cc65d-229">Нет, System. Management. Automation. Псремотингжоб</span><span class="sxs-lookup"><span data-stu-id="cc65d-229">None, System.Management.Automation.PSRemotingJob</span></span>

<span data-ttu-id="cc65d-230">Этот командлет возвращает объект задания, если указан параметр **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="cc65d-230">This cmdlet returns a job object, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="cc65d-231">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="cc65d-231">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="cc65d-232">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="cc65d-232">NOTES</span></span>

## <span data-ttu-id="cc65d-233">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="cc65d-233">RELATED LINKS</span></span>

[<span data-ttu-id="cc65d-234">Get-Job.</span><span class="sxs-lookup"><span data-stu-id="cc65d-234">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="cc65d-235">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="cc65d-235">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="cc65d-236">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="cc65d-236">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="cc65d-237">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="cc65d-237">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="cc65d-238">Start-Job</span><span class="sxs-lookup"><span data-stu-id="cc65d-238">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="cc65d-239">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="cc65d-239">Wait-Job</span></span>](Wait-Job.md)

[<span data-ttu-id="cc65d-240">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="cc65d-240">about_Job_Details</span></span>](About/about_Job_Details.md)

[<span data-ttu-id="cc65d-241">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="cc65d-241">about_Remote_Jobs</span></span>](About/about_Remote_Jobs.md)

[<span data-ttu-id="cc65d-242">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="cc65d-242">about_Remote_Variables</span></span>](About/about_Remote_Variables.md)

[<span data-ttu-id="cc65d-243">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="cc65d-243">about_Jobs</span></span>](About/about_Jobs.md)

[<span data-ttu-id="cc65d-244">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="cc65d-244">about_Scopes</span></span>](About/about_scopes.md)
