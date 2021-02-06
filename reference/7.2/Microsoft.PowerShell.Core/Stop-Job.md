---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/stop-job?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Job.
ms.openlocfilehash: 479c099d2d5daf1cc50c5c645be053ff4ae02bdc
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605058"
---
# <span data-ttu-id="5225f-102">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="5225f-102">Stop-Job</span></span>

## <span data-ttu-id="5225f-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="5225f-103">SYNOPSIS</span></span>
<span data-ttu-id="5225f-104">Останавливает фоновое задание PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5225f-104">Stops a PowerShell background job.</span></span>

## <span data-ttu-id="5225f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5225f-105">SYNTAX</span></span>

### <span data-ttu-id="5225f-106">Сессионидпараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="5225f-106">SessionIdParameterSet (Default)</span></span>

```
Stop-Job [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5225f-107">жобпараметерсет</span><span class="sxs-lookup"><span data-stu-id="5225f-107">JobParameterSet</span></span>

```
Stop-Job [-Job] <Job[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5225f-108">намепараметерсет</span><span class="sxs-lookup"><span data-stu-id="5225f-108">NameParameterSet</span></span>

```
Stop-Job [-PassThru] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5225f-109">инстанцеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="5225f-109">InstanceIdParameterSet</span></span>

```
Stop-Job [-PassThru] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5225f-110">статепараметерсет</span><span class="sxs-lookup"><span data-stu-id="5225f-110">StateParameterSet</span></span>

```
Stop-Job [-PassThru] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="5225f-111">филтерпараметерсет</span><span class="sxs-lookup"><span data-stu-id="5225f-111">FilterParameterSet</span></span>

```
Stop-Job [-PassThru] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="5225f-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5225f-112">DESCRIPTION</span></span>

<span data-ttu-id="5225f-113">`Stop-Job`Командлет останавливает выполняемые фоновые задания PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5225f-113">The `Stop-Job` cmdlet stops PowerShell background jobs that are in progress.</span></span> <span data-ttu-id="5225f-114">С помощью этого командлета можно прерывать все задания или прекращать выполнение выбранных заданий по имени, ИДЕНТИФИКАТОРу, ИДЕНТИФИКАТОРу экземпляра или состоянию, передавая объект задания в `Stop-Job` .</span><span class="sxs-lookup"><span data-stu-id="5225f-114">You can use this cmdlet to stop all jobs or stop selected jobs based on their name, ID, instance ID, or state, or by passing a job object to `Stop-Job`.</span></span>

<span data-ttu-id="5225f-115">Можно использовать `Stop-Job` для завершения фоновых заданий, например тех, которые были запущены с помощью `Start-Job` командлета или параметра **AsJob** любого командлета.</span><span class="sxs-lookup"><span data-stu-id="5225f-115">You can use `Stop-Job` to stop background jobs, such as those that were started by using the `Start-Job` cmdlet or the **AsJob** parameter of any cmdlet.</span></span> <span data-ttu-id="5225f-116">При прекращении фонового задания PowerShell завершает все задачи, ожидающие в этой очереди заданий, а затем завершает задание.</span><span class="sxs-lookup"><span data-stu-id="5225f-116">When you stop a background job, PowerShell completes all tasks that are pending in that job queue and then ends the job.</span></span> <span data-ttu-id="5225f-117">Новые задания не добавляются в очередь после отправки этой команды.</span><span class="sxs-lookup"><span data-stu-id="5225f-117">No new tasks are added to the queue after this command is submitted.</span></span>

<span data-ttu-id="5225f-118">Этот командлет не удаляет фоновые задания.</span><span class="sxs-lookup"><span data-stu-id="5225f-118">This cmdlet does not delete background jobs.</span></span> <span data-ttu-id="5225f-119">Чтобы удалить задание, используйте `Remove-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="5225f-119">To delete a job, use the `Remove-Job` cmdlet.</span></span>

<span data-ttu-id="5225f-120">Начиная с Windows PowerShell 3,0, `Stop-Job` также останавливаются пользовательские типы заданий, такие как задания рабочего процесса и экземпляры запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="5225f-120">Starting in Windows PowerShell 3.0, `Stop-Job` also stops custom job types, such as workflow jobs and instances of scheduled jobs.</span></span> <span data-ttu-id="5225f-121">Чтобы включить функцию `Stop-Job` для отмены задания с настраиваемым типом задания, импортируйте модуль, который поддерживает тип настраиваемого задания, в сеанс перед выполнением `Stop-Job` команды либо с помощью `Import-Module` командлета, либо с помощью или получения командлета в модуле.</span><span class="sxs-lookup"><span data-stu-id="5225f-121">To enable `Stop-Job` to stop a job with custom job type, import the module that supports the custom job type into the session before you run a `Stop-Job` command, either by using the `Import-Module` cmdlet or by using or getting a cmdlet in the module.</span></span> <span data-ttu-id="5225f-122">Дополнительные сведения о определенных пользовательских типах заданий см. в разделе документации о данной функции.</span><span class="sxs-lookup"><span data-stu-id="5225f-122">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="5225f-123">Примеры</span><span class="sxs-lookup"><span data-stu-id="5225f-123">EXAMPLES</span></span>

### <span data-ttu-id="5225f-124">Пример 1. Отмена задания на удаленном компьютере с помощью Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="5225f-124">Example 1: Stop a job on a remote computer by using Invoke-Command</span></span>

```powershell
$s = New-PSSession -ComputerName Server01 -Credential Domain01\Admin02
$j = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Invoke-Command -Session $s -ScriptBlock { Stop-job -Job $Using:j }
```

<span data-ttu-id="5225f-125">В этом примере показано, как использовать `Stop-Job` командлет для завершения задания, выполняемого на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5225f-125">This example shows how to use the `Stop-Job` cmdlet to stop a job that is running on a remote computer.</span></span>

<span data-ttu-id="5225f-126">Так как задание было запущено с помощью `Invoke-Command` командлета для `Start-Job` удаленного выполнения команды, объект задания хранится на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5225f-126">Because the job was started by using the `Invoke-Command` cmdlet to run a `Start-Job` command remotely, the job object is stored on the remote computer.</span></span> <span data-ttu-id="5225f-127">`Invoke-Command`Для удаленного выполнения команды необходимо использовать другую команду `Stop-Job` .</span><span class="sxs-lookup"><span data-stu-id="5225f-127">You must use another `Invoke-Command` command to run a `Stop-Job` command remotely.</span></span> <span data-ttu-id="5225f-128">Дополнительные сведения об удаленных фоновых заданиях см. в разделе about_Remote_Jobs.</span><span class="sxs-lookup"><span data-stu-id="5225f-128">For more information about remote background jobs, see about_Remote_Jobs.</span></span>

<span data-ttu-id="5225f-129">Первая команда создает сеанс PowerShell (**PSSession**) на компьютере Server01, а затем сохраняет объект сеанса в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="5225f-129">The first command creates a PowerShell session (**PSSession**) on the Server01 computer, and then stores the session object in the `$s` variable.</span></span> <span data-ttu-id="5225f-130">Команда использует учетные данные администратора домена.</span><span class="sxs-lookup"><span data-stu-id="5225f-130">The command uses the credentials of a domain administrator.</span></span>

<span data-ttu-id="5225f-131">Вторая команда использует `Invoke-Command` командлет для выполнения `Start-Job` команды в сеансе.</span><span class="sxs-lookup"><span data-stu-id="5225f-131">The second command uses the `Invoke-Command` cmdlet to run a `Start-Job` command in the session.</span></span> <span data-ttu-id="5225f-132">Команда в задании получает все события в системном журнале событий.</span><span class="sxs-lookup"><span data-stu-id="5225f-132">The command in the job gets all of the events in the System event log.</span></span> <span data-ttu-id="5225f-133">Результирующий объект задания хранится в `$j` переменной.</span><span class="sxs-lookup"><span data-stu-id="5225f-133">The resulting job object is stored in the `$j` variable.</span></span>

<span data-ttu-id="5225f-134">Третья команда останавливает задание.</span><span class="sxs-lookup"><span data-stu-id="5225f-134">The third command stops the job.</span></span> <span data-ttu-id="5225f-135">Он использует `Invoke-Command` командлет для выполнения `Stop-Job` команды в **сеансе PSSession** на Server01.</span><span class="sxs-lookup"><span data-stu-id="5225f-135">It uses the `Invoke-Command` cmdlet to run a `Stop-Job` command in the **PSSession** on Server01.</span></span> <span data-ttu-id="5225f-136">Поскольку объекты задания хранятся в среде `$j` , которая является переменной на локальном компьютере, команда использует модификатор области using для определения `$j` в качестве локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="5225f-136">Because the job objects are stored in `$j`, which is a variable on the local computer, the command uses the Using scope modifier to identify `$j` as a local variable.</span></span>
<span data-ttu-id="5225f-137">Дополнительные сведения об использовании модификатора SCOPE см. в разделе [about_Remote_Variables](about/about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="5225f-137">For more information about the Using scope modifier, see [about_Remote_Variables](about/about_Remote_Variables.md).</span></span>

<span data-ttu-id="5225f-138">По завершении выполнения команды задание останавливается, а **сеанс PSSession** `$s` доступен для использования.</span><span class="sxs-lookup"><span data-stu-id="5225f-138">When the command finishes, the job is stopped and the **PSSession** in `$s` is available for use.</span></span>

### <span data-ttu-id="5225f-139">Пример 2. завершение фонового задания</span><span class="sxs-lookup"><span data-stu-id="5225f-139">Example 2: Stop a background job</span></span>

```powershell
Stop-Job -Name "Job1"
```

<span data-ttu-id="5225f-140">Эта команда останавливает фоновое задание Job1.</span><span class="sxs-lookup"><span data-stu-id="5225f-140">This command stops the Job1 background job.</span></span>

### <span data-ttu-id="5225f-141">Пример 3. завершение нескольких фоновых заданий</span><span class="sxs-lookup"><span data-stu-id="5225f-141">Example 3: Stop several background jobs</span></span>

```powershell
Stop-Job -Id 1, 3, 4
```

<span data-ttu-id="5225f-142">Эта команда останавливает три задания.</span><span class="sxs-lookup"><span data-stu-id="5225f-142">This command stops three jobs.</span></span>
<span data-ttu-id="5225f-143">Она определяет их по идентификаторам.</span><span class="sxs-lookup"><span data-stu-id="5225f-143">It identifies them by their IDs.</span></span>

### <span data-ttu-id="5225f-144">Пример 4. завершение всех фоновых заданий</span><span class="sxs-lookup"><span data-stu-id="5225f-144">Example 4: Stop all background jobs</span></span>

```powershell
Get-Job | Stop-Job
```

<span data-ttu-id="5225f-145">Эта команда останавливает все фоновые задания в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="5225f-145">This command stops all of the background jobs in the current session.</span></span>

### <span data-ttu-id="5225f-146">Пример 5. завершение всех заблокированных фоновых заданий</span><span class="sxs-lookup"><span data-stu-id="5225f-146">Example 5: Stop all blocked background jobs</span></span>

```powershell
Stop-Job -State Blocked
```

<span data-ttu-id="5225f-147">Эта команда останавливает все задания, которые заблокированы.</span><span class="sxs-lookup"><span data-stu-id="5225f-147">This command stops all the jobs that are blocked.</span></span>

### <span data-ttu-id="5225f-148">Пример 6. завершение задания с помощью идентификатора экземпляра</span><span class="sxs-lookup"><span data-stu-id="5225f-148">Example 6: Stop a job by using an instance ID</span></span>

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

<span data-ttu-id="5225f-149">Эти команды позволяют остановить задание, указав идентификатор экземпляра.</span><span class="sxs-lookup"><span data-stu-id="5225f-149">These commands show how to stop a job based on its instance ID.</span></span>

<span data-ttu-id="5225f-150">Первая команда использует `Get-Job` командлет для получения заданий в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="5225f-150">The first command uses the `Get-Job` cmdlet to get the jobs in the current session.</span></span> <span data-ttu-id="5225f-151">Команда использует оператор конвейера ( `|` ) для отправки заданий в `Format-Table` команду, которая отображает таблицу с указанными свойствами каждого задания.</span><span class="sxs-lookup"><span data-stu-id="5225f-151">The command uses a pipeline operator (`|`) to send the jobs to a `Format-Table` command, which displays a table of the specified properties of each job.</span></span> <span data-ttu-id="5225f-152">Таблица содержит идентификатор экземпляра каждого задания.</span><span class="sxs-lookup"><span data-stu-id="5225f-152">The table includes the Instance ID of each job.</span></span> <span data-ttu-id="5225f-153">Для отображения состояния задания используется вычисляемое свойство.</span><span class="sxs-lookup"><span data-stu-id="5225f-153">It uses a calculated property to display the job state.</span></span>

<span data-ttu-id="5225f-154">Вторая команда использует `Stop-Job` команду с параметром **InstanceId** для завершения выбранного задания.</span><span class="sxs-lookup"><span data-stu-id="5225f-154">The second command uses a `Stop-Job` command that has the **InstanceID** parameter to stop a selected job.</span></span>

### <span data-ttu-id="5225f-155">Пример 7. завершение задания на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="5225f-155">Example 7: Stop a job on a remote computer</span></span>

```powershell
$j = Invoke-Command -ComputerName Server01 -ScriptBlock {Get-EventLog System} -AsJob
$j | Stop-Job -PassThru
```

```Output
Id    Name    State      HasMoreData     Location         Command
--    ----    ----       -----------     --------         -------
5     Job5    Stopped    True            user01-tablet    get-eventlog system
```

<span data-ttu-id="5225f-156">В этом примере показано, как использовать `Stop-Job` командлет для завершения задания, выполняемого на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5225f-156">This example shows how to use the `Stop-Job` cmdlet to stop a job that is running on a remote computer.</span></span>

<span data-ttu-id="5225f-157">Так как задание было запущено с помощью параметра **AsJob** `Invoke-Command` командлета, объект задания находится на локальном компьютере, даже если задание выполняется на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5225f-157">Because the job was started by using the **AsJob** parameter of the `Invoke-Command` cmdlet, the job object is located on the local computer, even though the job runs on the remote computer.</span></span> <span data-ttu-id="5225f-158">Таким образом, для завершения задания можно использовать локальную `Stop-Job` команду.</span><span class="sxs-lookup"><span data-stu-id="5225f-158">Therefore, you can use a local `Stop-Job` command to stop the job.</span></span>

<span data-ttu-id="5225f-159">Первая команда использует `Invoke-Command` командлет для запуска фонового задания на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="5225f-159">The first command uses the `Invoke-Command` cmdlet to start a background job on the Server01 computer.</span></span> <span data-ttu-id="5225f-160">Параметр **AsJob** применяется для выполнения удаленной команды в качестве фонового задания.</span><span class="sxs-lookup"><span data-stu-id="5225f-160">The command uses the **AsJob** parameter to run the remote command as a background job.</span></span>

<span data-ttu-id="5225f-161">Эта команда возвращает объект задания, который является тем же объектом задания, который `Start-Job` возвращает командлет.</span><span class="sxs-lookup"><span data-stu-id="5225f-161">This command returns a job object, which is the same job object that the `Start-Job` cmdlet returns.</span></span>
<span data-ttu-id="5225f-162">Команда сохраняет объект задания в `$j` переменной.</span><span class="sxs-lookup"><span data-stu-id="5225f-162">The command saves the job object in the `$j` variable.</span></span>

<span data-ttu-id="5225f-163">Вторая команда использует оператор конвейера для отправки задания в `$j` переменной в `Stop-Job` .</span><span class="sxs-lookup"><span data-stu-id="5225f-163">The second command uses a pipeline operator to send the job in the `$j` variable to `Stop-Job`.</span></span> <span data-ttu-id="5225f-164">Команда использует параметр **PassThru** для направления `Stop-Job` возврата объекта задания.</span><span class="sxs-lookup"><span data-stu-id="5225f-164">The command uses the **PassThru** parameter to direct `Stop-Job` to return a job object.</span></span> <span data-ttu-id="5225f-165">Отобразится объект задания, подтверждающий, что состояние задания остановлено.</span><span class="sxs-lookup"><span data-stu-id="5225f-165">The job object display confirms that the state of the job is Stopped.</span></span>

<span data-ttu-id="5225f-166">Дополнительные сведения об удаленных фоновых заданиях см. в разделе about_Remote_Jobs.</span><span class="sxs-lookup"><span data-stu-id="5225f-166">For more information about remote background jobs, see about_Remote_Jobs.</span></span>

## <span data-ttu-id="5225f-167">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5225f-167">PARAMETERS</span></span>

### <span data-ttu-id="5225f-168">-Filter</span><span class="sxs-lookup"><span data-stu-id="5225f-168">-Filter</span></span>

<span data-ttu-id="5225f-169">Указывает хэш-таблицу условий.</span><span class="sxs-lookup"><span data-stu-id="5225f-169">Specifies a hash table of conditions.</span></span> <span data-ttu-id="5225f-170">Этот командлет останавливает задания, которые отвечают всем условиям.</span><span class="sxs-lookup"><span data-stu-id="5225f-170">This cmdlet stops jobs that satisfy all of the conditions.</span></span>
<span data-ttu-id="5225f-171">Введите хэш-таблицу, где ключи являются свойствами заданий, а значения — значениями этих свойств.</span><span class="sxs-lookup"><span data-stu-id="5225f-171">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="5225f-172">Этот параметр работает только с пользовательскими типами заданий, такими как задания рабочих процессов и запланированные задания.</span><span class="sxs-lookup"><span data-stu-id="5225f-172">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span> <span data-ttu-id="5225f-173">Он не работает со стандартными фоновыми заданиями, такими как созданные с помощью `Start-Job` командлета.</span><span class="sxs-lookup"><span data-stu-id="5225f-173">It does not work on standard background jobs, such as those created by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="5225f-174">Дополнительные сведения о поддержке данного параметра см. в разделе справки о соответствующем типе заданий.</span><span class="sxs-lookup"><span data-stu-id="5225f-174">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="5225f-175">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5225f-175">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5225f-176">-Id</span><span class="sxs-lookup"><span data-stu-id="5225f-176">-Id</span></span>

<span data-ttu-id="5225f-177">Указывает идентификаторы заданий, которые останавливаются этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="5225f-177">Specifies the IDs of jobs that this cmdlet stops.</span></span> <span data-ttu-id="5225f-178">По умолчанию останавливаются все задания в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="5225f-178">The default is all jobs in the current session.</span></span>

<span data-ttu-id="5225f-179">Идентификатор — это целое число, которое однозначно определяет задание в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="5225f-179">The ID is an integer that uniquely identifies the job in the current session.</span></span> <span data-ttu-id="5225f-180">Проще запомнить и ввести, чем идентификатор экземпляра, но он уникален только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="5225f-180">It is easier to remember and type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="5225f-181">Можно ввести один или несколько идентификаторов, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="5225f-181">You can type one or more IDs, separated by commas.</span></span> <span data-ttu-id="5225f-182">Чтобы найти идентификатор задания, введите `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="5225f-182">To find the ID of a job, type `Get-Job`.</span></span>

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

### <span data-ttu-id="5225f-183">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="5225f-183">-InstanceId</span></span>

<span data-ttu-id="5225f-184">Указывает идентификаторы экземпляров заданий, которые останавливает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="5225f-184">Specifies the instance IDs of jobs that this cmdlet stops.</span></span> <span data-ttu-id="5225f-185">По умолчанию останавливаются все задания.</span><span class="sxs-lookup"><span data-stu-id="5225f-185">The default is all jobs.</span></span>

<span data-ttu-id="5225f-186">Идентификатор экземпляра — это GUID, который однозначно определяет задание на компьютере.</span><span class="sxs-lookup"><span data-stu-id="5225f-186">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span> <span data-ttu-id="5225f-187">Чтобы найти идентификатор экземпляра задания, используйте `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="5225f-187">To find the instance ID of a job, use `Get-Job`.</span></span>

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

### <span data-ttu-id="5225f-188">-Job</span><span class="sxs-lookup"><span data-stu-id="5225f-188">-Job</span></span>

<span data-ttu-id="5225f-189">Указывает задания, которые останавливаются этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="5225f-189">Specifies the jobs that this cmdlet stops.</span></span> <span data-ttu-id="5225f-190">Введите переменную, содержащую задания, либо команду, которая их возвращают.</span><span class="sxs-lookup"><span data-stu-id="5225f-190">Enter a variable that contains the jobs or a command that gets the jobs.</span></span> <span data-ttu-id="5225f-191">Можно также использовать оператор конвейера для отправки заданий в `Stop-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="5225f-191">You can also use a pipeline operator to submit jobs to the `Stop-Job` cmdlet.</span></span> <span data-ttu-id="5225f-192">По умолчанию `Stop-Job` удаляет все задания, запущенные в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="5225f-192">By default, `Stop-Job` deletes all jobs that were started in the current session.</span></span>

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

### <span data-ttu-id="5225f-193">-Name</span><span class="sxs-lookup"><span data-stu-id="5225f-193">-Name</span></span>

<span data-ttu-id="5225f-194">Указывает понятные имена заданий, которые остановит этот командлет.</span><span class="sxs-lookup"><span data-stu-id="5225f-194">Specifies friendly names of jobs that this cmdlet stops.</span></span> <span data-ttu-id="5225f-195">Введите имена заданий в списке с разделителями запятыми или используйте подстановочные знаки (\*) для ввода шаблона имени задания.</span><span class="sxs-lookup"><span data-stu-id="5225f-195">Enter the job names in a comma-separated list or use wildcard characters (\*) to enter a job name pattern.</span></span> <span data-ttu-id="5225f-196">По умолчанию `Stop-Job` останавливает все задания, созданные в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="5225f-196">By default, `Stop-Job` stops all jobs created in the current session.</span></span>

<span data-ttu-id="5225f-197">Так как понятное имя не обязательно должно быть уникальным, используйте параметры **WhatIf** и **Confirm** при остановке заданий по имени.</span><span class="sxs-lookup"><span data-stu-id="5225f-197">Because the friendly name is not guaranteed to be unique, use the **WhatIf** and **Confirm** parameters when stopping jobs by name.</span></span>

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

### <span data-ttu-id="5225f-198">-PassThru</span><span class="sxs-lookup"><span data-stu-id="5225f-198">-PassThru</span></span>

<span data-ttu-id="5225f-199">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="5225f-199">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="5225f-200">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="5225f-200">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="5225f-201">-State</span><span class="sxs-lookup"><span data-stu-id="5225f-201">-State</span></span>

<span data-ttu-id="5225f-202">Указывает состояние задания.</span><span class="sxs-lookup"><span data-stu-id="5225f-202">Specifies a job state.</span></span> <span data-ttu-id="5225f-203">Этот командлет останавливает только задания в указанном состоянии.</span><span class="sxs-lookup"><span data-stu-id="5225f-203">This cmdlet stops only jobs in the specified state.</span></span> <span data-ttu-id="5225f-204">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="5225f-204">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="5225f-205">NotStarted</span><span class="sxs-lookup"><span data-stu-id="5225f-205">NotStarted</span></span>
- <span data-ttu-id="5225f-206">Запущен</span><span class="sxs-lookup"><span data-stu-id="5225f-206">Running</span></span>
- <span data-ttu-id="5225f-207">Завершено</span><span class="sxs-lookup"><span data-stu-id="5225f-207">Completed</span></span>
- <span data-ttu-id="5225f-208">Ошибка</span><span class="sxs-lookup"><span data-stu-id="5225f-208">Failed</span></span>
- <span data-ttu-id="5225f-209">Остановлена</span><span class="sxs-lookup"><span data-stu-id="5225f-209">Stopped</span></span>
- <span data-ttu-id="5225f-210">Блокировано</span><span class="sxs-lookup"><span data-stu-id="5225f-210">Blocked</span></span>
- <span data-ttu-id="5225f-211">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="5225f-211">Suspended</span></span>
- <span data-ttu-id="5225f-212">Отключено</span><span class="sxs-lookup"><span data-stu-id="5225f-212">Disconnected</span></span>
- <span data-ttu-id="5225f-213">Приостановка</span><span class="sxs-lookup"><span data-stu-id="5225f-213">Suspending</span></span>
- <span data-ttu-id="5225f-214">Остановка</span><span class="sxs-lookup"><span data-stu-id="5225f-214">Stopping</span></span>

<span data-ttu-id="5225f-215">Дополнительные сведения о состояниях заданий см. в разделе [JobState enumeration](/dotnet/api/system.management.automation.jobstate).</span><span class="sxs-lookup"><span data-stu-id="5225f-215">For more information about job states, see [JobState Enumeration](/dotnet/api/system.management.automation.jobstate).</span></span>

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

### <span data-ttu-id="5225f-216">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5225f-216">-Confirm</span></span>

<span data-ttu-id="5225f-217">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="5225f-217">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="5225f-218">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5225f-218">-WhatIf</span></span>

<span data-ttu-id="5225f-219">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="5225f-219">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="5225f-220">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="5225f-220">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="5225f-221">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="5225f-221">CommonParameters</span></span>

<span data-ttu-id="5225f-222">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5225f-222">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5225f-223">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5225f-223">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5225f-224">Входные данные</span><span class="sxs-lookup"><span data-stu-id="5225f-224">INPUTS</span></span>

### <span data-ttu-id="5225f-225">System. Management. Automation. Ремотингжоб</span><span class="sxs-lookup"><span data-stu-id="5225f-225">System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="5225f-226">Объект задания можно передать в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="5225f-226">You can pipe a job object to this cmdlet.</span></span>

## <span data-ttu-id="5225f-227">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="5225f-227">OUTPUTS</span></span>

### <span data-ttu-id="5225f-228">Нет, System. Management. Automation. Псремотингжоб</span><span class="sxs-lookup"><span data-stu-id="5225f-228">None, System.Management.Automation.PSRemotingJob</span></span>

<span data-ttu-id="5225f-229">Этот командлет возвращает объект задания, если указан параметр **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="5225f-229">This cmdlet returns a job object, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="5225f-230">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="5225f-230">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="5225f-231">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="5225f-231">NOTES</span></span>

## <span data-ttu-id="5225f-232">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="5225f-232">RELATED LINKS</span></span>

[<span data-ttu-id="5225f-233">Get-Job.</span><span class="sxs-lookup"><span data-stu-id="5225f-233">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="5225f-234">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="5225f-234">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="5225f-235">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="5225f-235">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="5225f-236">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="5225f-236">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="5225f-237">Start-Job</span><span class="sxs-lookup"><span data-stu-id="5225f-237">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="5225f-238">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="5225f-238">Wait-Job</span></span>](Wait-Job.md)

[<span data-ttu-id="5225f-239">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="5225f-239">about_Job_Details</span></span>](About/about_Job_Details.md)

[<span data-ttu-id="5225f-240">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="5225f-240">about_Remote_Jobs</span></span>](About/about_Remote_Jobs.md)

[<span data-ttu-id="5225f-241">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="5225f-241">about_Remote_Variables</span></span>](About/about_Remote_Variables.md)

[<span data-ttu-id="5225f-242">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="5225f-242">about_Jobs</span></span>](About/about_Jobs.md)

[<span data-ttu-id="5225f-243">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="5225f-243">about_Scopes</span></span>](About/about_scopes.md)
