---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 01/28/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/wait-job?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Job
ms.openlocfilehash: 0afa3b0a86b3c2c318b8bbf6c969639825370cd7
ms.sourcegitcommit: 81558c2adb9d109946a027e5b96e4d24b3b13747
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99098668"
---
# <span data-ttu-id="a7753-103">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="a7753-103">Wait-Job</span></span>

## <span data-ttu-id="a7753-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a7753-104">SYNOPSIS</span></span>
<span data-ttu-id="a7753-105">Ожидает, пока один или все выполняемые в сеансе задания PowerShell находятся в состоянии завершения.</span><span class="sxs-lookup"><span data-stu-id="a7753-105">Waits until one or all of the PowerShell jobs running in the session are in a terminating state.</span></span>

## <span data-ttu-id="a7753-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a7753-106">SYNTAX</span></span>

### <span data-ttu-id="a7753-107">Сессионидпараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="a7753-107">SessionIdParameterSet (Default)</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Id] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="a7753-108">жобпараметерсет</span><span class="sxs-lookup"><span data-stu-id="a7753-108">JobParameterSet</span></span>

```
Wait-Job [-Job] <Job[]> [-Any] [-Timeout <Int32>] [-Force] [<CommonParameters>]
```

### <span data-ttu-id="a7753-109">намепараметерсет</span><span class="sxs-lookup"><span data-stu-id="a7753-109">NameParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="a7753-110">инстанцеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="a7753-110">InstanceIdParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="a7753-111">статепараметерсет</span><span class="sxs-lookup"><span data-stu-id="a7753-111">StateParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-State] <JobState> [<CommonParameters>]
```

### <span data-ttu-id="a7753-112">филтерпараметерсет</span><span class="sxs-lookup"><span data-stu-id="a7753-112">FilterParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Filter] <Hashtable> [<CommonParameters>]
```

## <span data-ttu-id="a7753-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a7753-113">DESCRIPTION</span></span>

<span data-ttu-id="a7753-114">`Wait-Job`Командлет ожидает, пока задание находится в состоянии завершения, прежде чем продолжить выполнение.</span><span class="sxs-lookup"><span data-stu-id="a7753-114">The `Wait-Job` cmdlet waits for a job to be in a terminating state before continuing execution.</span></span>
<span data-ttu-id="a7753-115">Завершающие состояния:</span><span class="sxs-lookup"><span data-stu-id="a7753-115">The terminating states are:</span></span>

- <span data-ttu-id="a7753-116">Завершено</span><span class="sxs-lookup"><span data-stu-id="a7753-116">Completed</span></span>
- <span data-ttu-id="a7753-117">Ошибка</span><span class="sxs-lookup"><span data-stu-id="a7753-117">Failed</span></span>
- <span data-ttu-id="a7753-118">Остановлена</span><span class="sxs-lookup"><span data-stu-id="a7753-118">Stopped</span></span>
- <span data-ttu-id="a7753-119">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="a7753-119">Suspended</span></span>
- <span data-ttu-id="a7753-120">Отключено</span><span class="sxs-lookup"><span data-stu-id="a7753-120">Disconnected</span></span>

<span data-ttu-id="a7753-121">Можно подождать, пока заданное задание или все задания находятся в состоянии завершения.</span><span class="sxs-lookup"><span data-stu-id="a7753-121">You can wait until a specified job, or all jobs are in a terminating state.</span></span> <span data-ttu-id="a7753-122">Можно также задать максимальное время ожидания для задания с помощью параметра **timeout** или использовать параметр **Force** для ожидания задания в `Suspended` `Disconnected` состоянии или.</span><span class="sxs-lookup"><span data-stu-id="a7753-122">You can also set a maximum wait time for the job using the **Timeout** parameter, or use the **Force** parameter to wait for a job in the `Suspended` or `Disconnected` states.</span></span>

<span data-ttu-id="a7753-123">После завершения выполнения команд в задании `Wait-Job` возвращает объект задания и продолжение выполнения.</span><span class="sxs-lookup"><span data-stu-id="a7753-123">When the commands in the job are complete, `Wait-Job` returns a job object and continues execution.</span></span>

<span data-ttu-id="a7753-124">Командлет можно использовать `Wait-Job` для ожидания запуска заданий с помощью `Start-Job` командлета или параметра **AsJob** `Invoke-Command` командлета.</span><span class="sxs-lookup"><span data-stu-id="a7753-124">You can use the `Wait-Job` cmdlet to wait for jobs started by using the `Start-Job` cmdlet or the **AsJob** parameter of the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="a7753-125">Дополнительные сведения см. в разделе [about_Jobs](./about/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="a7753-125">For more information about jobs, see [about_Jobs](./about/about_Jobs.md).</span></span>

<span data-ttu-id="a7753-126">Начиная с Windows PowerShell 3,0, `Wait-Job` командлет также ждет выполнения пользовательских типов заданий, таких как задания рабочего процесса и экземпляры запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="a7753-126">Starting in Windows PowerShell 3.0, the `Wait-Job` cmdlet also waits for custom job types, such as workflow jobs and instances of scheduled jobs.</span></span> <span data-ttu-id="a7753-127">Чтобы разрешить `Wait-Job` Ожидание заданий определенного типа, импортируйте модуль, который поддерживает тип настраиваемого задания, в сеанс перед выполнением `Get-Job` командлета либо с помощью командлета, либо `Import-Module` путем получения командлета в модуле.</span><span class="sxs-lookup"><span data-stu-id="a7753-127">To enable `Wait-Job` to wait for jobs of a particular type, import the module that supports the custom job type into the session before you run the `Get-Job` cmdlet, either by using the `Import-Module` cmdlet or by using or getting a cmdlet in the module.</span></span> <span data-ttu-id="a7753-128">Дополнительные сведения о определенных пользовательских типах заданий см. в разделе документации о данной функции.</span><span class="sxs-lookup"><span data-stu-id="a7753-128">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="a7753-129">Примеры</span><span class="sxs-lookup"><span data-stu-id="a7753-129">EXAMPLES</span></span>

### <span data-ttu-id="a7753-130">Пример 1. Ожидание всех заданий</span><span class="sxs-lookup"><span data-stu-id="a7753-130">Example 1: Wait for all jobs</span></span>

```powershell
Get-Job | Wait-Job
```

<span data-ttu-id="a7753-131">Эта команда ожидает завершения всех заданий, выполняемых в сеансе.</span><span class="sxs-lookup"><span data-stu-id="a7753-131">This command waits for all of the jobs running in the session to finish.</span></span>

### <span data-ttu-id="a7753-132">Пример 2. Ожидание запуска заданий на удаленных компьютерах с помощью Start-Job</span><span class="sxs-lookup"><span data-stu-id="a7753-132">Example 2: Wait for jobs started on remote computers by using Start-Job</span></span>

```powershell
$s = New-PSSession Server01, Server02, Server03
Invoke-Command -Session $s -ScriptBlock {Start-Job -Name Date1 -ScriptBlock {Get-Date}}
$done = Invoke-Command -Session $s -Command {Wait-Job -Name Date1}
$done.Count
```

```Output
3
```

<span data-ttu-id="a7753-133">В этом примере показано, как использовать `Wait-Job` командлет с заданиями, запущенными на удаленных компьютерах с помощью `Start-Job` командлета.</span><span class="sxs-lookup"><span data-stu-id="a7753-133">This example shows how to use the `Wait-Job` cmdlet with jobs started on remote computers by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="a7753-134">Обе `Start-Job` `Wait-Job` команды и передаются на удаленный компьютер с помощью `Invoke-Command` командлета.</span><span class="sxs-lookup"><span data-stu-id="a7753-134">Both `Start-Job` and `Wait-Job` commands are submitted to the remote computer by using the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="a7753-135">В этом примере используется `Wait-Job` , чтобы определить, `Get-Date` завершена ли команда, выполняемая в качестве задания на трех разных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="a7753-135">This example uses `Wait-Job` to determine whether a `Get-Date` command running as a job on three different computers is finished.</span></span>

<span data-ttu-id="a7753-136">Первая команда создает сеанс Windows PowerShell (**PSSession**) на каждом из трех удаленных компьютеров и сохраняет их в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="a7753-136">The first command creates a Windows PowerShell session (**PSSession**) on each of the three remote computers and stores them in the `$s` variable.</span></span>

<span data-ttu-id="a7753-137">Вторая команда использует `Invoke-Command` для выполнения `Start-Job` в каждом из трех сеансов в `$s` .</span><span class="sxs-lookup"><span data-stu-id="a7753-137">The second command uses `Invoke-Command` to run `Start-Job` in each of the three sessions in `$s`.</span></span>
<span data-ttu-id="a7753-138">Все задания имеют имя Date1.</span><span class="sxs-lookup"><span data-stu-id="a7753-138">All of the jobs are named Date1.</span></span>

<span data-ttu-id="a7753-139">Третья команда использует `Invoke-Command` для запуска `Wait-Job` .</span><span class="sxs-lookup"><span data-stu-id="a7753-139">The third command uses `Invoke-Command` to run `Wait-Job`.</span></span> <span data-ttu-id="a7753-140">Эта команда ожидает `Date1` завершения заданий на каждом компьютере.</span><span class="sxs-lookup"><span data-stu-id="a7753-140">This command waits for the `Date1` jobs on each computer to finish.</span></span> <span data-ttu-id="a7753-141">В нем сохраняется результирующая коллекция (**Array**) объектов **Job** в `$done` переменной.</span><span class="sxs-lookup"><span data-stu-id="a7753-141">It stores the resulting collection (**array**) of **job** objects in the `$done` variable.</span></span>

<span data-ttu-id="a7753-142">Четвертая команда использует свойство **Count** массива объектов задания в `$done` переменной, чтобы определить, сколько заданий завершено.</span><span class="sxs-lookup"><span data-stu-id="a7753-142">The fourth command uses the **Count** property of the array of job objects in the `$done` variable to determine how many of the jobs are finished.</span></span>

### <span data-ttu-id="a7753-143">Пример 3. Определение времени завершения первого задания</span><span class="sxs-lookup"><span data-stu-id="a7753-143">Example 3: Determine when the first job finishes</span></span>

```powershell
$s = New-PSSession (Get-Content Machines.txt)
$c = 'Get-EventLog -LogName System | where {$_.EntryType -eq "error" --and $_.Source -eq "LSASRV"} | Out-File Errors.txt'
Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {$Using:c}
Invoke-Command -Session $s -ScriptBlock {Wait-Job -Any}
```

<span data-ttu-id="a7753-144">В этом примере используется параметр **ANY** , `Wait-Job` чтобы определить, когда первое из многих заданий, выполняемых в текущем сеансе, находится в состоянии завершения.</span><span class="sxs-lookup"><span data-stu-id="a7753-144">This example uses the **Any** parameter of `Wait-Job` to determine when the first of many jobs running in the current session are in a terminating state.</span></span> <span data-ttu-id="a7753-145">В нем также показано, как использовать `Wait-Job` командлет для ожидания завершения удаленных заданий.</span><span class="sxs-lookup"><span data-stu-id="a7753-145">It also shows how to use the `Wait-Job` cmdlet to wait for remote jobs to finish.</span></span>

<span data-ttu-id="a7753-146">Первая команда создает **сеанс PSSession** на каждом из компьютеров, перечисленных в файле Machines.txt, и сохраняет объекты **PSSession** в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="a7753-146">The first command creates a **PSSession** on each of the computers listed in the Machines.txt file and stores the **PSSession** objects in the `$s` variable.</span></span> <span data-ttu-id="a7753-147">Команда использует `Get-Content` командлет для получения содержимого файла.</span><span class="sxs-lookup"><span data-stu-id="a7753-147">The command uses the `Get-Content` cmdlet to get the contents of the file.</span></span> <span data-ttu-id="a7753-148">`Get-Content`Команда заключается в круглые скобки, чтобы убедиться, что она выполняется перед `New-PSSession` командой.</span><span class="sxs-lookup"><span data-stu-id="a7753-148">The `Get-Content` command is enclosed in parentheses to make sure that it runs before the `New-PSSession` command.</span></span>

<span data-ttu-id="a7753-149">Вторая команда сохраняет `Get-EventLog` командную строку в кавычках в `$c` переменной.</span><span class="sxs-lookup"><span data-stu-id="a7753-149">The second command stores a `Get-EventLog` command string, in quotation marks, in the `$c` variable.</span></span>

<span data-ttu-id="a7753-150">Третья команда использует `Invoke-Command` командлет для выполнения `Start-Job` в каждом сеансе в `$s` .</span><span class="sxs-lookup"><span data-stu-id="a7753-150">The third command uses `Invoke-Command` cmdlet to run `Start-Job` in each of the sessions in `$s`.</span></span>
<span data-ttu-id="a7753-151">`Start-Job`Команда запускает задание, которое выполняет `Get-EventLog` команду в `$c` переменной.</span><span class="sxs-lookup"><span data-stu-id="a7753-151">The `Start-Job` command starts a job that runs the `Get-EventLog` command in the `$c` variable.</span></span>

<span data-ttu-id="a7753-152">Команда использует модификатор области **using** , чтобы указать, что `$c` переменная была определена на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a7753-152">The command uses the **Using** scope modifier to indicate that the `$c` variable was defined on the local computer.</span></span> <span data-ttu-id="a7753-153">Модификатор области **Using** был введен в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a7753-153">The **Using** scope modifier is introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="a7753-154">Дополнительные сведения об **использовании** модификатора SCOPE см. в разделе [about_Remote_Variables](./about/about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="a7753-154">For more information about the **Using** scope modifier, see [about_Remote_Variables](./about/about_Remote_Variables.md).</span></span>

<span data-ttu-id="a7753-155">Четвертая команда использует `Invoke-Command` для выполнения `Wait-Job` команды в сеансах.</span><span class="sxs-lookup"><span data-stu-id="a7753-155">The fourth command uses `Invoke-Command` to run a `Wait-Job` command in the sessions.</span></span> <span data-ttu-id="a7753-156">Он использует параметр **ANY** для ожидания завершения первого задания на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="a7753-156">It uses the **Any** parameter to wait until the first job on the remote computers is terminating state.</span></span>

### <span data-ttu-id="a7753-157">Пример 4. Задание времени ожидания для заданий на удаленных компьютерах</span><span class="sxs-lookup"><span data-stu-id="a7753-157">Example 4: Set a wait time for jobs on remote computers</span></span>

```powershell
PS> $s = New-PSSession Server01, Server02, Server03
PS> $jobs = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {Get-Date}}
PS> $done = Invoke-Command -Session $s -ScriptBlock {Wait-Job -Timeout 30}
PS>
```

<span data-ttu-id="a7753-158">В этом примере показано, как использовать параметр **timeout** в, `Wait-Job` чтобы задать максимальное время ожидания для заданий, выполняемых на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="a7753-158">This example shows how to use the **Timeout** parameter of `Wait-Job` to set a maximum wait time for the jobs running on remote computers.</span></span>

<span data-ttu-id="a7753-159">Первая команда создает **сеанс PSSession** на каждом из трех удаленных компьютеров (Server01, Server02 и Server03), а затем сохраняет объекты **PSSession** в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="a7753-159">The first command creates a **PSSession** on each of three remote computers (Server01, Server02, and Server03), and then stores the **PSSession** objects in the `$s` variable.</span></span>

<span data-ttu-id="a7753-160">Вторая команда использует `Invoke-Command` для выполнения `Start-Job` в каждом из объектов **PSSession** в `$s` .</span><span class="sxs-lookup"><span data-stu-id="a7753-160">The second command uses `Invoke-Command` to run `Start-Job` in each of the **PSSession** objects in `$s`.</span></span> <span data-ttu-id="a7753-161">Он сохраняет результирующие объекты задания в `$jobs` переменной.</span><span class="sxs-lookup"><span data-stu-id="a7753-161">It stores the resulting job objects in the `$jobs` variable.</span></span>

<span data-ttu-id="a7753-162">Третья команда использует `Invoke-Command` для выполнения `Wait-Job` в каждом сеансе в `$s` .</span><span class="sxs-lookup"><span data-stu-id="a7753-162">The third command uses `Invoke-Command` to run `Wait-Job` in each of the sessions in `$s`.</span></span> <span data-ttu-id="a7753-163">`Wait-Job`Команда определяет, выполнены ли все команды в течение 30 секунд.</span><span class="sxs-lookup"><span data-stu-id="a7753-163">The `Wait-Job` command determines whether all of the commands have completed within 30 seconds.</span></span> <span data-ttu-id="a7753-164">Он использует параметр **timeout** со значением 30 для установки максимального времени ожидания, а затем сохраняет результаты выполнения команды в `$done` переменной.</span><span class="sxs-lookup"><span data-stu-id="a7753-164">It uses the **Timeout** parameter with a value of 30 to establish the maximum wait time, and then stores the results of the command in the `$done` variable.</span></span>

<span data-ttu-id="a7753-165">В данном случае по истечении 30 секунд была завершена только команда на компьютере Server02.</span><span class="sxs-lookup"><span data-stu-id="a7753-165">In this case, after 30 seconds, only the command on the Server02 computer has completed.</span></span> <span data-ttu-id="a7753-166">`Wait-Job` завершает ожидание, возвращает объект, представляющий завершенное задание, и отображает командную строку.</span><span class="sxs-lookup"><span data-stu-id="a7753-166">`Wait-Job` ends the wait, returns the object that represents the job that was completed, and displays the command prompt.</span></span>

<span data-ttu-id="a7753-167">`$done`Переменная содержит объект задания, который представляет задание, которое выполнялось в Server02.</span><span class="sxs-lookup"><span data-stu-id="a7753-167">The `$done` variable contains a job object that represents the job that ran on Server02.</span></span>

### <span data-ttu-id="a7753-168">Пример 5. Ожидание завершения одного из нескольких заданий</span><span class="sxs-lookup"><span data-stu-id="a7753-168">Example 5: Wait until one of several jobs finishes</span></span>

```powershell
Wait-Job -id 1,2,5 -Any
```

<span data-ttu-id="a7753-169">Эта команда определяет три задания по их идентификаторам и ожидает до тех пор, пока они не будут находиться в состоянии завершения.</span><span class="sxs-lookup"><span data-stu-id="a7753-169">This command identifies three jobs by their IDs and waits until any one of them are in a terminating state.</span></span> <span data-ttu-id="a7753-170">Выполнение продолжится после завершения первого задания.</span><span class="sxs-lookup"><span data-stu-id="a7753-170">Execution continues when the first job finishes.</span></span>

### <span data-ttu-id="a7753-171">Пример 6. Ожидание периода, а затем разрешение на продолжение работы в фоновом режиме</span><span class="sxs-lookup"><span data-stu-id="a7753-171">Example 6: Wait for a period, then allow job to continue in background</span></span>

```powershell
Wait-Job -Name "DailyLog" -Timeout 120
```

<span data-ttu-id="a7753-172">Эта команда ожидает завершения задания Даилилог в течение 120 с (две минуты).</span><span class="sxs-lookup"><span data-stu-id="a7753-172">This command waits 120 seconds (two minutes) for the DailyLog job to finish.</span></span> <span data-ttu-id="a7753-173">Если задание не закончится в течение следующих двух минут, выполнение продолжится, и задание продолжит выполняться в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="a7753-173">If the job does not finish in the next two minutes, execution continues, and the job continues to run in the background.</span></span>

### <span data-ttu-id="a7753-174">Пример 7. Ожидание задания по имени</span><span class="sxs-lookup"><span data-stu-id="a7753-174">Example 7: Wait for a job by name</span></span>

```powershell
Wait-Job -Name "Job3"
```

<span data-ttu-id="a7753-175">Эта команда использует имя задания для указания задания, которое требуется подождать.</span><span class="sxs-lookup"><span data-stu-id="a7753-175">This command uses the job name to identify the job for which to wait.</span></span>

### <span data-ttu-id="a7753-176">Пример 8. Ожидание запуска заданий на локальном компьютере с Start-Job</span><span class="sxs-lookup"><span data-stu-id="a7753-176">Example 8: Wait for jobs on local computer started with Start-Job</span></span>

```powershell
$j = Start-Job -ScriptBlock {Get-ChildItem *.ps1| where {$_.lastwritetime -gt ((Get-Date) - (New-TimeSpan -Days 7))}}
$j | Wait-Job
```

<span data-ttu-id="a7753-177">В этом примере показано, как использовать `Wait-Job` командлет с заданиями, запущенными на локальном компьютере с помощью `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="a7753-177">This example shows how to use the `Wait-Job` cmdlet with jobs started on the local computer by using `Start-Job`.</span></span>

<span data-ttu-id="a7753-178">Эти команды запускают задание, которое получает список файлов скриптов Windows PowerShell, добавленных или измененных в течение последней недели.</span><span class="sxs-lookup"><span data-stu-id="a7753-178">These commands start a job that gets the Windows PowerShell script files that were added or updated in the last week.</span></span>

<span data-ttu-id="a7753-179">Первая команда использует `Start-Job` для запуска задания на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a7753-179">The first command uses `Start-Job` to start a job on the local computer.</span></span> <span data-ttu-id="a7753-180">Задание выполняет `Get-ChildItem` команду, которая получает все файлы с расширением PS1, которые были добавлены или обновлены за последнюю неделю.</span><span class="sxs-lookup"><span data-stu-id="a7753-180">The job runs a `Get-ChildItem` command that gets all of the files that have a .ps1 file name extension that were added or updated in the last week.</span></span>

<span data-ttu-id="a7753-181">Третья команда использует `Wait-Job` , чтобы подождать, пока задание находится в состоянии завершения.</span><span class="sxs-lookup"><span data-stu-id="a7753-181">The third command uses `Wait-Job` to wait until the job is in a terminating state.</span></span> <span data-ttu-id="a7753-182">После завершения задания команда отображает объект задания, содержащий сведения о задании.</span><span class="sxs-lookup"><span data-stu-id="a7753-182">When the job finishes, the command displays the job object, which contains information about the job.</span></span>

### <span data-ttu-id="a7753-183">Пример 9. Ожидание запуска заданий на удаленных компьютерах с помощью Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="a7753-183">Example 9: Wait for jobs started on remote computers by using Invoke-Command</span></span>

```powershell
$s = New-PSSession Server01, Server02, Server03
$j = Invoke-Command -Session $s -ScriptBlock {Get-Process} -AsJob
$j | Wait-Job
```

<span data-ttu-id="a7753-184">В этом примере показано, как использовать `Wait-Job` с заданиями, запущенными на удаленных компьютерах, с помощью параметра **AsJob** в `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="a7753-184">This example shows how to use `Wait-Job` with jobs started on remote computers by using the **AsJob** parameter of `Invoke-Command`.</span></span> <span data-ttu-id="a7753-185">При использовании **AsJob** задание создается на локальном компьютере, а результаты автоматически возвращаются на локальный компьютер, даже если задание выполняется на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="a7753-185">When using **AsJob**, the job is created on the local computer and the results are automatically returned to the local computer, even though the job runs on the remote computers.</span></span>

<span data-ttu-id="a7753-186">В этом примере используется `Wait-Job` для определения того, `Get-Process` находится ли команда, выполняемая в сеансах на трех удаленных компьютерах, в состоянии завершения.</span><span class="sxs-lookup"><span data-stu-id="a7753-186">This example uses `Wait-Job` to determine whether a `Get-Process` command running in the sessions on three remote computers is in a terminating state.</span></span>

<span data-ttu-id="a7753-187">Первая команда создает объекты **PSSession** на трех компьютерах и сохраняет их в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="a7753-187">The first command creates **PSSession** objects on three computers and stores them in the `$s` variable.</span></span>

<span data-ttu-id="a7753-188">Вторая команда использует `Invoke-Command` для выполнения `Get-Process` в каждом из трех сеансов в `$s` .</span><span class="sxs-lookup"><span data-stu-id="a7753-188">The second command uses `Invoke-Command` to run `Get-Process` in each of the three sessions in `$s`.</span></span>
<span data-ttu-id="a7753-189">Команда использует параметр **AsJob** для асинхронного выполнения команды в качестве задания.</span><span class="sxs-lookup"><span data-stu-id="a7753-189">The command uses the **AsJob** parameter to run the command asynchronously as a job.</span></span> <span data-ttu-id="a7753-190">Команда возвращает объект задания, как и задания, запущенные с помощью `Start-Job` , а объект задания хранится в `$j` переменной.</span><span class="sxs-lookup"><span data-stu-id="a7753-190">The command returns a job object, just like the jobs started by using `Start-Job`, and the job object is stored in the `$j` variable.</span></span>

<span data-ttu-id="a7753-191">Третья команда использует конвейерный оператор ( `|` ) для отправки объекта задания в `$j` `Wait-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="a7753-191">The third command uses a pipeline operator (`|`) to send the job object in `$j` to the `Wait-Job` cmdlet.</span></span> <span data-ttu-id="a7753-192">`Invoke-Command`В этом случае команда не требуется, так как задание находится на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a7753-192">An `Invoke-Command` command is not required in this case, because the job resides on the local computer.</span></span>

### <span data-ttu-id="a7753-193">Пример 10. Ожидание задания с ИДЕНТИФИКАТОРом</span><span class="sxs-lookup"><span data-stu-id="a7753-193">Example 10: Wait for a job that has an ID</span></span>

```powershell
Get-Job
```

```Output
Id   Name     State      HasMoreData     Location             Command
--   ----     -----      -----------     --------             -------
1    Job1     Completed  True            localhost,Server01.. get-service
4    Job4     Completed  True            localhost            dir | where
```

```powershell
Wait-Job -Id 1
```

<span data-ttu-id="a7753-194">Эта команда ожидает завершения задания с идентификатором 1.</span><span class="sxs-lookup"><span data-stu-id="a7753-194">This command waits for the job with an ID value of 1.</span></span>

## <span data-ttu-id="a7753-195">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a7753-195">PARAMETERS</span></span>

### <span data-ttu-id="a7753-196">-Any</span><span class="sxs-lookup"><span data-stu-id="a7753-196">-Any</span></span>

<span data-ttu-id="a7753-197">Указывает, что этот командлет возвращает объект задания и возобновляет выполнение по завершении любого задания.</span><span class="sxs-lookup"><span data-stu-id="a7753-197">Indicates that this cmdlet returns the job object and continues execution when any job finishes.</span></span> <span data-ttu-id="a7753-198">По умолчанию `Wait-Job` ожидает завершения всех указанных заданий перед отображением запроса.</span><span class="sxs-lookup"><span data-stu-id="a7753-198">By default, `Wait-Job` waits until all of the specified jobs are complete before it displays the prompt.</span></span>

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

### <span data-ttu-id="a7753-199">-Filter</span><span class="sxs-lookup"><span data-stu-id="a7753-199">-Filter</span></span>

<span data-ttu-id="a7753-200">Указывает хэш-таблицу условий.</span><span class="sxs-lookup"><span data-stu-id="a7753-200">Specifies a hash table of conditions.</span></span> <span data-ttu-id="a7753-201">Этот командлет ожидает задания, которые отвечают всем условиям в хэш-таблице.</span><span class="sxs-lookup"><span data-stu-id="a7753-201">This cmdlet waits for jobs that satisfy all of the conditions in the hash table.</span></span> <span data-ttu-id="a7753-202">Введите хэш-таблицу, где ключи являются свойствами заданий, а значения — значениями этих свойств.</span><span class="sxs-lookup"><span data-stu-id="a7753-202">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="a7753-203">Этот параметр работает только с пользовательскими типами заданий, такими как задания рабочих процессов и запланированные задания.</span><span class="sxs-lookup"><span data-stu-id="a7753-203">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span> <span data-ttu-id="a7753-204">Он не работает со стандартными заданиями, такими как созданные с помощью `Start-Job` командлета.</span><span class="sxs-lookup"><span data-stu-id="a7753-204">It does not work on standard jobs, such as those created by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="a7753-205">Дополнительные сведения о поддержке данного параметра см. в разделе справки о соответствующем типе заданий.</span><span class="sxs-lookup"><span data-stu-id="a7753-205">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="a7753-206">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a7753-206">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a7753-207">-Force</span><span class="sxs-lookup"><span data-stu-id="a7753-207">-Force</span></span>

<span data-ttu-id="a7753-208">Указывает, что этот командлет продолжает ожидать задания в приостановленном или отключенном состоянии.</span><span class="sxs-lookup"><span data-stu-id="a7753-208">Indicates that this cmdlet continues to wait for jobs in the Suspended or Disconnected state.</span></span> <span data-ttu-id="a7753-209">По умолчанию `Wait-Job` Возвращает или завершает ожидание, если задания находятся в одном из следующих состояний:</span><span class="sxs-lookup"><span data-stu-id="a7753-209">By default, `Wait-Job` returns, or ends the wait, when jobs are in one of the following states:</span></span>

- <span data-ttu-id="a7753-210">Завершено</span><span class="sxs-lookup"><span data-stu-id="a7753-210">Completed</span></span>
- <span data-ttu-id="a7753-211">Ошибка</span><span class="sxs-lookup"><span data-stu-id="a7753-211">Failed</span></span>
- <span data-ttu-id="a7753-212">Остановлена</span><span class="sxs-lookup"><span data-stu-id="a7753-212">Stopped</span></span>
- <span data-ttu-id="a7753-213">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="a7753-213">Suspended</span></span>
- <span data-ttu-id="a7753-214">Отключено</span><span class="sxs-lookup"><span data-stu-id="a7753-214">Disconnected</span></span>

<span data-ttu-id="a7753-215">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a7753-215">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a7753-216">-Id</span><span class="sxs-lookup"><span data-stu-id="a7753-216">-Id</span></span>

<span data-ttu-id="a7753-217">Указывает массив идентификаторов заданий, для которых этот командлет ожидает выполнения.</span><span class="sxs-lookup"><span data-stu-id="a7753-217">Specifies an array of IDs of jobs for which this cmdlet waits.</span></span>

<span data-ttu-id="a7753-218">Идентификатор — это целое число, которое однозначно определяет задание в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="a7753-218">The ID is an integer that uniquely identifies the job in the current session.</span></span> <span data-ttu-id="a7753-219">Проще запомнить и ввести, чем идентификатор экземпляра, но он уникален только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="a7753-219">It is easier to remember and type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="a7753-220">Можно ввести один или несколько идентификаторов, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="a7753-220">You can type one or more IDs, separated by commas.</span></span> <span data-ttu-id="a7753-221">Чтобы найти идентификатор задания, введите `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="a7753-221">To find the ID of a job, type `Get-Job`.</span></span>

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

### <span data-ttu-id="a7753-222">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="a7753-222">-InstanceId</span></span>

<span data-ttu-id="a7753-223">Указывает массив идентификаторов экземпляров заданий, для которых этот командлет ожидает выполнения.</span><span class="sxs-lookup"><span data-stu-id="a7753-223">Specifies an array of instance IDs of jobs for which this cmdlet waits.</span></span> <span data-ttu-id="a7753-224">По умолчанию останавливаются все задания.</span><span class="sxs-lookup"><span data-stu-id="a7753-224">The default is all jobs.</span></span>

<span data-ttu-id="a7753-225">Идентификатор экземпляра — это GUID, который однозначно определяет задание на компьютере.</span><span class="sxs-lookup"><span data-stu-id="a7753-225">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span> <span data-ttu-id="a7753-226">Чтобы найти идентификатор экземпляра задания, используйте `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="a7753-226">To find the instance ID of a job, use `Get-Job`.</span></span>

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

### <span data-ttu-id="a7753-227">-Job</span><span class="sxs-lookup"><span data-stu-id="a7753-227">-Job</span></span>

<span data-ttu-id="a7753-228">Указывает задания, для которых этот командлет ожидает.</span><span class="sxs-lookup"><span data-stu-id="a7753-228">Specifies the jobs for which this cmdlet waits.</span></span> <span data-ttu-id="a7753-229">Введите переменную, содержащую объекты заданий, либо команду, которая их возвращают.</span><span class="sxs-lookup"><span data-stu-id="a7753-229">Enter a variable that contains the job objects or a command that gets the job objects.</span></span> <span data-ttu-id="a7753-230">Для отправки объектов заданий в командлет можно также использовать оператор конвейера `Wait-Job` .</span><span class="sxs-lookup"><span data-stu-id="a7753-230">You can also use a pipeline operator to send job objects to the `Wait-Job` cmdlet.</span></span> <span data-ttu-id="a7753-231">По умолчанию `Wait-Job` ожидает всех заданий, созданных в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="a7753-231">By default, `Wait-Job` waits for all jobs created in the current session.</span></span>

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a7753-232">-Name</span><span class="sxs-lookup"><span data-stu-id="a7753-232">-Name</span></span>

<span data-ttu-id="a7753-233">Указывает понятные имена заданий, для которых этот командлет ожидает выполнения.</span><span class="sxs-lookup"><span data-stu-id="a7753-233">Specifies friendly names of jobs for which this cmdlet waits.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a7753-234">-State</span><span class="sxs-lookup"><span data-stu-id="a7753-234">-State</span></span>

<span data-ttu-id="a7753-235">Указывает состояние задания.</span><span class="sxs-lookup"><span data-stu-id="a7753-235">Specifies a job state.</span></span> <span data-ttu-id="a7753-236">Этот командлет ожидает только задания в указанном состоянии.</span><span class="sxs-lookup"><span data-stu-id="a7753-236">This cmdlet waits only for jobs in the specified state.</span></span> <span data-ttu-id="a7753-237">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="a7753-237">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="a7753-238">NotStarted</span><span class="sxs-lookup"><span data-stu-id="a7753-238">NotStarted</span></span>
- <span data-ttu-id="a7753-239">Запущен</span><span class="sxs-lookup"><span data-stu-id="a7753-239">Running</span></span>
- <span data-ttu-id="a7753-240">Завершено</span><span class="sxs-lookup"><span data-stu-id="a7753-240">Completed</span></span>
- <span data-ttu-id="a7753-241">Ошибка</span><span class="sxs-lookup"><span data-stu-id="a7753-241">Failed</span></span>
- <span data-ttu-id="a7753-242">Остановлена</span><span class="sxs-lookup"><span data-stu-id="a7753-242">Stopped</span></span>
- <span data-ttu-id="a7753-243">Блокировано</span><span class="sxs-lookup"><span data-stu-id="a7753-243">Blocked</span></span>
- <span data-ttu-id="a7753-244">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="a7753-244">Suspended</span></span>
- <span data-ttu-id="a7753-245">Отключено</span><span class="sxs-lookup"><span data-stu-id="a7753-245">Disconnected</span></span>
- <span data-ttu-id="a7753-246">Приостановка</span><span class="sxs-lookup"><span data-stu-id="a7753-246">Suspending</span></span>
- <span data-ttu-id="a7753-247">Остановка</span><span class="sxs-lookup"><span data-stu-id="a7753-247">Stopping</span></span>

<span data-ttu-id="a7753-248">Дополнительные сведения о состояниях заданий см. в разделе [JobState enumeration](/dotnet/api/system.management.automation.jobstate).</span><span class="sxs-lookup"><span data-stu-id="a7753-248">For more information about job states, see [JobState Enumeration](/dotnet/api/system.management.automation.jobstate).</span></span>

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

### <span data-ttu-id="a7753-249">-Timeout</span><span class="sxs-lookup"><span data-stu-id="a7753-249">-Timeout</span></span>

<span data-ttu-id="a7753-250">Задает максимальное время ожидания для каждого задания в секундах.</span><span class="sxs-lookup"><span data-stu-id="a7753-250">Specifies the maximum wait time for each job, in seconds.</span></span> <span data-ttu-id="a7753-251">Значение по умолчанию – 1 указывает, что командлет ожидает завершения задания.</span><span class="sxs-lookup"><span data-stu-id="a7753-251">The default value, -1, indicates that the cmdlet waits until the job finishes.</span></span> <span data-ttu-id="a7753-252">Время начинается при отправке `Wait-Job` команды, а не `Start-Job` команды.</span><span class="sxs-lookup"><span data-stu-id="a7753-252">The timing starts when you submit the `Wait-Job` command, not the `Start-Job` command.</span></span>

<span data-ttu-id="a7753-253">Если это время превышено, ожидание завершается и выполнение продолжается, даже если задание все еще выполняется.</span><span class="sxs-lookup"><span data-stu-id="a7753-253">If this time is exceeded, the wait ends and execution continues, even if the job is still running.</span></span>
<span data-ttu-id="a7753-254">Команда не отображает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="a7753-254">The command does not display any error message.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a7753-255">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a7753-255">CommonParameters</span></span>

<span data-ttu-id="a7753-256">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a7753-256">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a7753-257">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a7753-257">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a7753-258">Входные данные</span><span class="sxs-lookup"><span data-stu-id="a7753-258">INPUTS</span></span>

### <span data-ttu-id="a7753-259">System. Management. Automation. Ремотингжоб</span><span class="sxs-lookup"><span data-stu-id="a7753-259">System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="a7753-260">Объект задания можно передать в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="a7753-260">You can pipe a job object to this cmdlet.</span></span>

## <span data-ttu-id="a7753-261">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a7753-261">OUTPUTS</span></span>

### <span data-ttu-id="a7753-262">System. Management. Automation. Псремотингжоб</span><span class="sxs-lookup"><span data-stu-id="a7753-262">System.Management.Automation.PSRemotingJob</span></span>

<span data-ttu-id="a7753-263">Этот командлет возвращает объекты задания, представляющие задания в состоянии завершения.</span><span class="sxs-lookup"><span data-stu-id="a7753-263">This cmdlet returns job objects that represent the jobs in a terminating state.</span></span> <span data-ttu-id="a7753-264">Если ожидание заканчивается из-за превышения значения параметра **timeout** , не `Wait-Job` возвращает никаких объектов.</span><span class="sxs-lookup"><span data-stu-id="a7753-264">If the wait ends because the value of the **Timeout** parameter is exceeded, `Wait-Job` does not return any objects.</span></span>

## <span data-ttu-id="a7753-265">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="a7753-265">NOTES</span></span>

<span data-ttu-id="a7753-266">По умолчанию `Wait-Job` Возвращает или завершает ожидание, если задания находятся в одном из следующих состояний:</span><span class="sxs-lookup"><span data-stu-id="a7753-266">By default, `Wait-Job` returns, or ends the wait, when jobs are in one of the following states:</span></span>

- <span data-ttu-id="a7753-267">Завершено</span><span class="sxs-lookup"><span data-stu-id="a7753-267">Completed</span></span>
- <span data-ttu-id="a7753-268">Ошибка</span><span class="sxs-lookup"><span data-stu-id="a7753-268">Failed</span></span>
- <span data-ttu-id="a7753-269">Остановлена</span><span class="sxs-lookup"><span data-stu-id="a7753-269">Stopped</span></span>
- <span data-ttu-id="a7753-270">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="a7753-270">Suspended</span></span>
- <span data-ttu-id="a7753-271">Отключено. чтобы `Wait-Job` продолжить ожидание приостановленных и отключенных заданий, используйте параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="a7753-271">Disconnected To direct `Wait-Job` to continue to wait for Suspended and Disconnected jobs, use the **Force** parameter.</span></span>

## <span data-ttu-id="a7753-272">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a7753-272">RELATED LINKS</span></span>

[<span data-ttu-id="a7753-273">Get-Job.</span><span class="sxs-lookup"><span data-stu-id="a7753-273">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="a7753-274">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="a7753-274">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="a7753-275">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="a7753-275">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="a7753-276">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="a7753-276">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="a7753-277">Start-Job</span><span class="sxs-lookup"><span data-stu-id="a7753-277">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="a7753-278">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="a7753-278">Stop-Job</span></span>](Stop-Job.md)
