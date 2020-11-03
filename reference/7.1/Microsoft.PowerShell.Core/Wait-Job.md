---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/wait-job?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Job
ms.openlocfilehash: b69688891df70c396d19911624c58ae7733183d0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226997"
---
# <span data-ttu-id="cef47-103">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="cef47-103">Wait-Job</span></span>

## <span data-ttu-id="cef47-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="cef47-104">SYNOPSIS</span></span>
<span data-ttu-id="cef47-105">Подавляет командную строку до завершения выполнения одного или всех фоновых заданий PowerShell, выполняемых в этом сеансе.</span><span class="sxs-lookup"><span data-stu-id="cef47-105">Suppresses the command prompt until one or all of the PowerShell background jobs running in the session are completed.</span></span>

## <span data-ttu-id="cef47-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cef47-106">SYNTAX</span></span>

### <span data-ttu-id="cef47-107">Сессионидпараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="cef47-107">SessionIdParameterSet (Default)</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Id] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="cef47-108">жобпараметерсет</span><span class="sxs-lookup"><span data-stu-id="cef47-108">JobParameterSet</span></span>

```
Wait-Job [-Job] <Job[]> [-Any] [-Timeout <Int32>] [-Force] [<CommonParameters>]
```

### <span data-ttu-id="cef47-109">намепараметерсет</span><span class="sxs-lookup"><span data-stu-id="cef47-109">NameParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="cef47-110">инстанцеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="cef47-110">InstanceIdParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="cef47-111">статепараметерсет</span><span class="sxs-lookup"><span data-stu-id="cef47-111">StateParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-State] <JobState> [<CommonParameters>]
```

### <span data-ttu-id="cef47-112">филтерпараметерсет</span><span class="sxs-lookup"><span data-stu-id="cef47-112">FilterParameterSet</span></span>

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Filter] <Hashtable> [<CommonParameters>]
```

## <span data-ttu-id="cef47-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cef47-113">DESCRIPTION</span></span>

<span data-ttu-id="cef47-114">Командлет **Wait-Job** ожидает завершения фоновых заданий PowerShell, прежде чем отобразит командную строку.</span><span class="sxs-lookup"><span data-stu-id="cef47-114">The **Wait-Job** cmdlet waits for PowerShell background jobs to finish before it displays the command prompt.</span></span>
<span data-ttu-id="cef47-115">При этом можно командлет может ожидать завершения одного или всех фоновых заданий либо ограничиваться максимальным временем ожидания.</span><span class="sxs-lookup"><span data-stu-id="cef47-115">You can wait until any background job is complete, or until all background jobs are complete, and you can set a maximum wait time for the job.</span></span>

<span data-ttu-id="cef47-116">После выполнения содержащихся в задании команд **Wait-Job** отображает командную строку и возвращает объект задания, который можно передать по конвейеру в другую команду.</span><span class="sxs-lookup"><span data-stu-id="cef47-116">When the commands in the job are complete, **Wait-Job** displays the command prompt and returns a job object so that you can pipe it to another command.</span></span>

<span data-ttu-id="cef47-117">Командлет **Wait-Job** можно использовать для ожидания фоновых заданий, например тех, которые были запущены с помощью Start-Jobого командлета или параметра *AsJob* командлета Invoke-Command.</span><span class="sxs-lookup"><span data-stu-id="cef47-117">You can use **Wait-Job** cmdlet to wait for background jobs, such as those that were started by using the Start-Job cmdlet or the *AsJob* parameter of the Invoke-Command cmdlet.</span></span>
<span data-ttu-id="cef47-118">Дополнительные сведения о фоновых заданиях PowerShell см. в разделе about_Jobs.</span><span class="sxs-lookup"><span data-stu-id="cef47-118">For more information about PowerShell background jobs, see about_Jobs.</span></span>

<span data-ttu-id="cef47-119">Начиная с Windows PowerShell 3,0, командлет **Wait-Job** также ждет выполнения пользовательских типов заданий, таких как задания рабочего процесса и экземпляры запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="cef47-119">Starting in Windows PowerShell 3.0, the **Wait-Job** cmdlet also waits for custom job types, such as workflow jobs and instances of scheduled jobs.</span></span>
<span data-ttu-id="cef47-120">Чтобы разрешить ожидание **задания** ожидания заданий определенного типа, импортируйте модуль, который поддерживает тип настраиваемого задания, в сеанс перед запуском командлета Get-Job с помощью командлета Import-Module или с помощью или получения командлета в модуле.</span><span class="sxs-lookup"><span data-stu-id="cef47-120">To enable **Wait-Job** to wait for jobs of a particular type, import the module that supports the custom job type into the session before you run the Get-Job cmdlet, either by using the Import-Module cmdlet or by using or getting a cmdlet in the module.</span></span>
<span data-ttu-id="cef47-121">Дополнительные сведения о определенных пользовательских типах заданий см. в разделе документации о данной функции.</span><span class="sxs-lookup"><span data-stu-id="cef47-121">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="cef47-122">Примеры</span><span class="sxs-lookup"><span data-stu-id="cef47-122">EXAMPLES</span></span>

### <span data-ttu-id="cef47-123">Пример 1. Ожидание всех заданий</span><span class="sxs-lookup"><span data-stu-id="cef47-123">Example 1: Wait for all jobs</span></span>

```powershell
Get-Job | Wait-Job
```

<span data-ttu-id="cef47-124">Эта команда ожидает завершения всех фоновых заданий, выполняемых в сеансе.</span><span class="sxs-lookup"><span data-stu-id="cef47-124">This command waits for all of the background jobs running in the session to finish.</span></span>

### <span data-ttu-id="cef47-125">Пример 2. Ожидание запуска заданий на удаленных компьютерах с помощью Start-Job</span><span class="sxs-lookup"><span data-stu-id="cef47-125">Example 2: Wait for jobs started on remote computers by using Start-Job</span></span>

```powershell
$s = New-PSSession Server01, Server02, Server03
Invoke-Command -Session $s -ScriptBlock {Start-Job -Name Date1 -ScriptBlock {Get-Date}}
$done = Invoke-Command -Session $s -Command {Wait-Job -Name Date1}
$done.Count
```

```Output
3
```

<span data-ttu-id="cef47-126">В этом примере показано, как использовать командлет **Wait-Job** с заданиями, запущенными на удаленных компьютерах с помощью командлета **Start-Job** .</span><span class="sxs-lookup"><span data-stu-id="cef47-126">This example shows how to use the **Wait-Job** cmdlet with jobs started on remote computers by using the **Start-Job** cmdlet.</span></span>
<span data-ttu-id="cef47-127">Команды **Start-Job** и **Wait-Job** отправляются на удаленный компьютер с помощью командлета **Invoke-Command** .</span><span class="sxs-lookup"><span data-stu-id="cef47-127">Both **Start-Job** and **Wait-Job** commands are submitted to the remote computer by using the **Invoke-Command** cmdlet.</span></span>

<span data-ttu-id="cef47-128">В этом примере используется **Ожидание задания** , чтобы определить, завершена ли команда Get-Date, выполняемая как фоновое задание на трех разных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="cef47-128">This example uses **Wait-Job** to determine whether a Get-Date command running as a background job on three different computers is finished.</span></span>

<span data-ttu-id="cef47-129">Первая команда создает сеанс PowerShell ( **PSSession** ) на каждом из трех удаленных компьютеров и сохраняет их в переменной $s.</span><span class="sxs-lookup"><span data-stu-id="cef47-129">The first command creates a PowerShell session ( **PSSession** ) on each of the three remote computers and stores them in the $s variable.</span></span>

<span data-ttu-id="cef47-130">Вторая команда использует **Invoke-Command** для запуска **запуска задания** в каждом из трех сеансов в $s.</span><span class="sxs-lookup"><span data-stu-id="cef47-130">The second command uses **Invoke-Command** to run **Start-Job** in each of the three sessions in $s.</span></span>
<span data-ttu-id="cef47-131">Все задания имеют имя Date1.</span><span class="sxs-lookup"><span data-stu-id="cef47-131">All of the jobs are named Date1.</span></span>

<span data-ttu-id="cef47-132">Третья команда использует **командлет Invoke-Command** для выполнения **Wait-Job**.</span><span class="sxs-lookup"><span data-stu-id="cef47-132">The third command uses **Invoke-Command** to run **Wait-Job**.</span></span>
<span data-ttu-id="cef47-133">Эта команда ожидает завершения заданий Date1 на каждом компьютере.</span><span class="sxs-lookup"><span data-stu-id="cef47-133">This command waits for the Date1 jobs on each computer to finish.</span></span>
<span data-ttu-id="cef47-134">Полученная коллекция (массив) объектов заданий сохраняется в переменную $done.</span><span class="sxs-lookup"><span data-stu-id="cef47-134">It stores the resulting collection (array) of job objects in the $done variable.</span></span>

<span data-ttu-id="cef47-135">Четвертая команда использует свойство **Count** массива объектов задания в переменной $done, чтобы определить, сколько заданий завершено.</span><span class="sxs-lookup"><span data-stu-id="cef47-135">The fourth command uses the **Count** property of the array of job objects in the $done variable to determine how many of the jobs are finished.</span></span>

### <span data-ttu-id="cef47-136">Пример 3. Определение времени завершения первого фонового задания</span><span class="sxs-lookup"><span data-stu-id="cef47-136">Example 3: Determine when the first background job finishes</span></span>

```powershell
$s = New-PSSession (Get-Content Machines.txt)
$c = 'Get-EventLog -LogName System | where {$_.EntryType -eq "error" --and $_.Source -eq "LSASRV"} | Out-File Errors.txt'
Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {$Using:c}
Invoke-Command -Session $s -ScriptBlock {Wait-Job -Any}
```

<span data-ttu-id="cef47-137">В этом примере используется *параметр* **Wait-Job** для определения времени выполнения первого из многих фоновых заданий, выполняемых в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="cef47-137">This example uses the *Any* parameter of **Wait-Job** to determine when the first of many background jobs running in the current session are completed.</span></span>
<span data-ttu-id="cef47-138">В нем также показано, как использовать командлет **Wait-Job** для ожидания завершения удаленных заданий.</span><span class="sxs-lookup"><span data-stu-id="cef47-138">It also shows how to use the **Wait-Job** cmdlet to wait for remote jobs to finish.</span></span>

<span data-ttu-id="cef47-139">Первая команда создает **сеанс PSSession** на каждом из компьютеров, перечисленных в файле Machines.txt, и сохраняет объекты **PSSession** в переменной $s.</span><span class="sxs-lookup"><span data-stu-id="cef47-139">The first command creates a **PSSession** on each of the computers listed in the Machines.txt file and stores the **PSSession** objects in the $s variable.</span></span>
<span data-ttu-id="cef47-140">Команда использует командлет Get-Content для получения содержимого файла.</span><span class="sxs-lookup"><span data-stu-id="cef47-140">The command uses the Get-Content cmdlet to get the contents of the file.</span></span>
<span data-ttu-id="cef47-141">Команда **Get-Content** заключается в круглые скобки, чтобы убедиться, что она выполняется перед командой New-PSSession.</span><span class="sxs-lookup"><span data-stu-id="cef47-141">The **Get-Content** command is enclosed in parentheses to make sure that it runs before the New-PSSession command.</span></span>

<span data-ttu-id="cef47-142">Вторая команда сохраняет командную строку **Get-EventLog** в кавычках в переменной $c.</span><span class="sxs-lookup"><span data-stu-id="cef47-142">The second command stores a **Get-EventLog** command string, in quotation marks, in the $c variable.</span></span>

<span data-ttu-id="cef47-143">Третья команда использует командлет Invoke-Command для запуска **запуска задания** в каждом из сеансов в $s.</span><span class="sxs-lookup"><span data-stu-id="cef47-143">The third command uses Invoke-Command cmdlet to run **Start-Job** in each of the sessions in $s.</span></span>
<span data-ttu-id="cef47-144">Команда **Start-Job** запускает фоновое задание, которое выполняет команду **Get-EventLog** в переменной $c.</span><span class="sxs-lookup"><span data-stu-id="cef47-144">The **Start-Job** command starts a background job that runs the **Get-EventLog** command in the $c variable.</span></span>

<span data-ttu-id="cef47-145">Поскольку переменная $c является локальной, в команде используется модификатор области **Using**.</span><span class="sxs-lookup"><span data-stu-id="cef47-145">The command uses the **Using** scope modifier to indicate that the $c variable was defined on the local computer.</span></span>
<span data-ttu-id="cef47-146">Модификатор области **Using** был введен в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="cef47-146">The **Using** scope modifier is introduced in Windows PowerShell 3.0.</span></span>
<span data-ttu-id="cef47-147">Дополнительные сведения об **использовании** модификатора SCOPE см. в разделе [about_Remote_Variables](about/about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="cef47-147">For more information about the **Using** scope modifier, see [about_Remote_Variables](about/about_Remote_Variables.md).</span></span>

<span data-ttu-id="cef47-148">Четвертая команда использует **командлет Invoke-Command** для выполнения команды **Wait-Job** в сеансах.</span><span class="sxs-lookup"><span data-stu-id="cef47-148">The fourth command uses **Invoke-Command** to run a **Wait-Job** command in the sessions.</span></span>
<span data-ttu-id="cef47-149">Он использует параметр *ANY* для ожидания завершения первого задания на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="cef47-149">It uses the *Any* parameter to wait until the first job on the remote computers is completed.</span></span>

### <span data-ttu-id="cef47-150">Пример 4. Задание времени ожидания для заданий на удаленных компьютерах</span><span class="sxs-lookup"><span data-stu-id="cef47-150">Example 4: Set a wait time for jobs on remote computers</span></span>

```powershell
$s = New-PSSession Server01, Server02, Server03
$jobs = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {Get-Date}}
$done = Invoke-Command -Session $s -ScriptBlock {Wait-Job -Timeout 30}
```

<span data-ttu-id="cef47-151">В этом примере показано, как использовать параметр *timeout* командлета **Wait-Job** , чтобы задать максимальное время ожидания для заданий, выполняемых на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="cef47-151">This example shows how to use the *Timeout* parameter of **Wait-Job** to set a maximum wait time for the jobs running on remote computers.</span></span>

<span data-ttu-id="cef47-152">Первая команда создает **сеанс PSSession** на каждом из трех удаленных компьютеров (Server01, Server02 и Server03), а затем сохраняет объекты **PSSession** в переменной $s.</span><span class="sxs-lookup"><span data-stu-id="cef47-152">The first command creates a **PSSession** on each of three remote computers (Server01, Server02, and Server03), and then stores the **PSSession** objects in the $s variable.</span></span>

<span data-ttu-id="cef47-153">Вторая команда использует **Invoke-Command** для запуска **запуска задания** в каждом из объектов **PSSession** в $s.</span><span class="sxs-lookup"><span data-stu-id="cef47-153">The second command uses **Invoke-Command** to run **Start-Job** in each of the **PSSession** objects in $s.</span></span>
<span data-ttu-id="cef47-154">Он сохраняет результирующие объекты задания в переменной $jobs.</span><span class="sxs-lookup"><span data-stu-id="cef47-154">It stores the resulting job objects in the $jobs variable.</span></span>

<span data-ttu-id="cef47-155">Третья команда использует **командлет Invoke-Command** для выполнения **Wait-Job** в каждом из сеансов в $s.</span><span class="sxs-lookup"><span data-stu-id="cef47-155">The third command uses **Invoke-Command** to run **Wait-Job** in each of the sessions in $s.</span></span>
<span data-ttu-id="cef47-156">Команда **Wait-Job** определяет, выполнены ли все команды в течение 30 секунд.</span><span class="sxs-lookup"><span data-stu-id="cef47-156">The **Wait-Job** command determines whether all of the commands have completed within 30 seconds.</span></span>
<span data-ttu-id="cef47-157">Он использует параметр *timeout* со значением 30 для установки максимального времени ожидания, а затем сохраняет результаты выполнения команды в переменной $done.</span><span class="sxs-lookup"><span data-stu-id="cef47-157">It uses the *Timeout* parameter with a value of 30 to establish the maximum wait time, and then stores the results of the command in the $done variable.</span></span>

<span data-ttu-id="cef47-158">В данном случае по истечении 30 секунд была завершена только команда на компьютере Server02.</span><span class="sxs-lookup"><span data-stu-id="cef47-158">In this case, after 30 seconds, only the command on the Server02 computer has completed.</span></span>
<span data-ttu-id="cef47-159">**Wait-Job** завершает ожидание, отображает командную строку и возвращает объект, представляющий завершенное задание.</span><span class="sxs-lookup"><span data-stu-id="cef47-159">**Wait-Job** ends the wait, displays the command prompt, and returns the object that represents the job that was completed.</span></span>

<span data-ttu-id="cef47-160">Переменная $done содержит объект задания, представляющий задание, которое выполнялось на компьютере Server02.</span><span class="sxs-lookup"><span data-stu-id="cef47-160">The $done variable contains a job object that represents the job that ran on Server02.</span></span>

### <span data-ttu-id="cef47-161">Пример 5. Ожидание завершения одного из нескольких заданий</span><span class="sxs-lookup"><span data-stu-id="cef47-161">Example 5: Wait until one of several jobs finishes</span></span>

```powershell
Wait-Job -id 1,2,5 -Any
```

<span data-ttu-id="cef47-162">Эта команда определяет три задания по их идентификаторам и ожидает завершения одного из них.</span><span class="sxs-lookup"><span data-stu-id="cef47-162">This command identifies three jobs by their IDs and waits until any one of them are completed.</span></span>
<span data-ttu-id="cef47-163">Командная строка возвращает время завершения первого задания.</span><span class="sxs-lookup"><span data-stu-id="cef47-163">The command prompt returns when the first job finishes.</span></span>

### <span data-ttu-id="cef47-164">Пример 6. Ожидание периода, а затем разрешение на продолжение работы в фоновом режиме</span><span class="sxs-lookup"><span data-stu-id="cef47-164">Example 6: Wait for a period, then allow job to continue in background</span></span>

```powershell
Wait-Job -Name "DailyLog" -Timeout 120
```

<span data-ttu-id="cef47-165">Эта команда ожидает завершения задания Даилилог в течение 120 с (две минуты).</span><span class="sxs-lookup"><span data-stu-id="cef47-165">This command waits 120 seconds (two minutes) for the DailyLog job to finish.</span></span>
<span data-ttu-id="cef47-166">Если задание не завершается в течение следующих двух минут, Командная строка все равно возвращается, и задание продолжит выполняться в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="cef47-166">If the job does not finish in the next two minutes, the command prompt returns anyway, and the job continues to run in the background.</span></span>

### <span data-ttu-id="cef47-167">Пример 7. Ожидание задания по имени</span><span class="sxs-lookup"><span data-stu-id="cef47-167">Example 7: Wait for a job by name</span></span>

```powershell
Wait-Job -Name "Job3"
```

<span data-ttu-id="cef47-168">Эта команда использует имя задания для указания задания, которое требуется подождать.</span><span class="sxs-lookup"><span data-stu-id="cef47-168">This command uses the job name to identify the job for which to wait.</span></span>

### <span data-ttu-id="cef47-169">Пример 8. Ожидание запуска заданий на локальном компьютере с Start-Job</span><span class="sxs-lookup"><span data-stu-id="cef47-169">Example 8: Wait for jobs on local computer started with Start-Job</span></span>

```powershell
$j = Start-Job -ScriptBlock {Get-ChildItem *.ps1| where {$_lastwritetime -gt ((Get-Date) - (New-TimeSpan -Days 7))}}
$j | Wait-Job
```

<span data-ttu-id="cef47-170">В этом примере показано, как использовать командлет **Wait-Job** с заданиями, запущенными на локальном компьютере с помощью команды **Start-Job**.</span><span class="sxs-lookup"><span data-stu-id="cef47-170">This example shows how to use the **Wait-Job** cmdlet with jobs started on the local computer by using **Start-Job**.</span></span>

<span data-ttu-id="cef47-171">Эти команды запускают задание, которое получает файлы скриптов PowerShell, которые были добавлены или обновлены за последнюю неделю.</span><span class="sxs-lookup"><span data-stu-id="cef47-171">These commands start a job that gets the PowerShell script files that were added or updated in the last week.</span></span>

<span data-ttu-id="cef47-172">Первая команда использует **Запуск-задание** для запуска фонового задания на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cef47-172">The first command uses **Start-Job** to start a background job on the local computer.</span></span>
<span data-ttu-id="cef47-173">Задание выполняет Get-ChildItem команду, которая получает все файлы с расширением PS1, которые были добавлены или обновлены за последнюю неделю.</span><span class="sxs-lookup"><span data-stu-id="cef47-173">The job runs a Get-ChildItem command that gets all of the files that have a .ps1 file name extension that were added or updated in the last week.</span></span>

<span data-ttu-id="cef47-174">Третья команда использует **Wait-Job** для ожидания завершения задания.</span><span class="sxs-lookup"><span data-stu-id="cef47-174">The third command uses **Wait-Job** to wait until the job is completed.</span></span>
<span data-ttu-id="cef47-175">После завершения задания команда отображает объект задания, содержащий сведения о задании.</span><span class="sxs-lookup"><span data-stu-id="cef47-175">When the job finishes, the command displays the job object, which contains information about the job.</span></span>

### <span data-ttu-id="cef47-176">Пример 9. Ожидание запуска заданий на удаленных компьютерах с помощью Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="cef47-176">Example 9: Wait for jobs started on remote computers by using Invoke-Command</span></span>

```powershell
$s = New-PSSession Server01, Server02, Server03
$j = Invoke-Command -Session $s -ScriptBlock {Get-Process} -AsJob
$j | Wait-Job
```

<span data-ttu-id="cef47-177">В этом примере показано, как использовать **Wait-Job** с заданиями, запущенными на удаленных компьютерах, с помощью параметра *AsJob* **командлета Invoke-Command**.</span><span class="sxs-lookup"><span data-stu-id="cef47-177">This example shows how to use **Wait-Job** with jobs started on remote computers by using the *AsJob* parameter of **Invoke-Command**.</span></span>
<span data-ttu-id="cef47-178">При использовании *AsJob* задание создается на локальном компьютере, а результаты автоматически возвращаются на локальный компьютер, даже если задание выполняется на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="cef47-178">When using *AsJob* , the job is created on the local computer and the results are automatically returned to the local computer, even though the job runs on the remote computers.</span></span>

<span data-ttu-id="cef47-179">В этом примере используется **Ожидание задания** , чтобы определить, завершена ли команда **Get-Process** , выполняемая в сеансах на трех удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="cef47-179">This example uses **Wait-Job** to determine whether a **Get-Process** command running in the sessions on three remote computers is completed.</span></span>

<span data-ttu-id="cef47-180">Первая команда создает объекты **PSSession** на трех компьютерах и сохраняет их в переменной $s.</span><span class="sxs-lookup"><span data-stu-id="cef47-180">The first command creates **PSSession** objects on three computers and stores them in the $s variable.</span></span>

<span data-ttu-id="cef47-181">Вторая команда использует **командлет Invoke-Command** для запуска **Get-Process** в каждом из трех сеансов в $s.</span><span class="sxs-lookup"><span data-stu-id="cef47-181">The second command uses **Invoke-Command** to run **Get-Process** in each of the three sessions in $s.</span></span>
<span data-ttu-id="cef47-182">Команда использует параметр *AsJob* для асинхронного выполнения команды в качестве фонового задания.</span><span class="sxs-lookup"><span data-stu-id="cef47-182">The command uses the *AsJob* parameter to run the command asynchronously as a background job.</span></span>
<span data-ttu-id="cef47-183">Команда возвращает объект задания, как и задания, запущенные с помощью **Start-Job** , а объект задания хранится в переменной $j.</span><span class="sxs-lookup"><span data-stu-id="cef47-183">The command returns a job object, just like the jobs started by using **Start-Job** , and the job object is stored in the $j variable.</span></span>

<span data-ttu-id="cef47-184">Третья команда использует конвейерный оператор (|) для отправки объекта задания в $j в командлет **Wait-Job** .</span><span class="sxs-lookup"><span data-stu-id="cef47-184">The third command uses a pipeline operator (|) to send the job object in $j to the **Wait-Job** cmdlet.</span></span>
<span data-ttu-id="cef47-185">В этом случае команда **Invoke-Command** не требуется, так как задание находится на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cef47-185">An **Invoke-Command** command is not required in this case, because the job resides on the local computer.</span></span>

### <span data-ttu-id="cef47-186">Пример 10. Ожидание задания с ИДЕНТИФИКАТОРом</span><span class="sxs-lookup"><span data-stu-id="cef47-186">Example 10: Wait for a job that has an ID</span></span>

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

<span data-ttu-id="cef47-187">Эта команда ожидает завершения задания с идентификатором 1.</span><span class="sxs-lookup"><span data-stu-id="cef47-187">This command waits for the job with an ID value of 1.</span></span>

## <span data-ttu-id="cef47-188">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cef47-188">PARAMETERS</span></span>

### <span data-ttu-id="cef47-189">-Any</span><span class="sxs-lookup"><span data-stu-id="cef47-189">-Any</span></span>

<span data-ttu-id="cef47-190">Указывает, что этот командлет отображает командную строку и возвращает объект задания при завершении любого задания.</span><span class="sxs-lookup"><span data-stu-id="cef47-190">Indicates that this cmdlet displays the command prompt, and returns the job object, when any job finishes.</span></span>
<span data-ttu-id="cef47-191">По умолчанию **Wait-Job** ожидает завершения всех указанных заданий до того, как отобразится запрос.</span><span class="sxs-lookup"><span data-stu-id="cef47-191">By default, **Wait-Job** waits until all of the specified jobs are complete before it displays the prompt.</span></span>

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

### <span data-ttu-id="cef47-192">-Filter</span><span class="sxs-lookup"><span data-stu-id="cef47-192">-Filter</span></span>

<span data-ttu-id="cef47-193">Указывает хэш-таблицу условий.</span><span class="sxs-lookup"><span data-stu-id="cef47-193">Specifies a hash table of conditions.</span></span>
<span data-ttu-id="cef47-194">Этот командлет ожидает задания, которые отвечают всем условиям в хэш-таблице.</span><span class="sxs-lookup"><span data-stu-id="cef47-194">This cmdlet waits for jobs that satisfy all of the conditions in the hash table.</span></span>
<span data-ttu-id="cef47-195">Введите хэш-таблицу, где ключи являются свойствами заданий, а значения — значениями этих свойств.</span><span class="sxs-lookup"><span data-stu-id="cef47-195">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="cef47-196">Этот параметр работает только с пользовательскими типами заданий, такими как задания рабочих процессов и запланированные задания.</span><span class="sxs-lookup"><span data-stu-id="cef47-196">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span>
<span data-ttu-id="cef47-197">Он не работает со стандартными фоновыми заданиями, такими как созданные с помощью командлета **Start-Job** .</span><span class="sxs-lookup"><span data-stu-id="cef47-197">It does not work on standard background jobs, such as those created by using the **Start-Job** cmdlet.</span></span>
<span data-ttu-id="cef47-198">Дополнительные сведения о поддержке данного параметра см. в разделе справки о соответствующем типе заданий.</span><span class="sxs-lookup"><span data-stu-id="cef47-198">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="cef47-199">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="cef47-199">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="cef47-200">-Force</span><span class="sxs-lookup"><span data-stu-id="cef47-200">-Force</span></span>

<span data-ttu-id="cef47-201">Указывает, что этот командлет продолжает ожидать задания в приостановленном или отключенном состоянии.</span><span class="sxs-lookup"><span data-stu-id="cef47-201">Indicates that this cmdlet continues to wait for jobs in the Suspended or Disconnected state.</span></span>
<span data-ttu-id="cef47-202">По умолчанию **Wait-Job** Возвращает или завершает ожидание, если задания находятся в одном из следующих состояний:</span><span class="sxs-lookup"><span data-stu-id="cef47-202">By default, **Wait-Job** returns, or ends  the wait, when jobs are in one of the following states:</span></span>

- <span data-ttu-id="cef47-203">Завершено</span><span class="sxs-lookup"><span data-stu-id="cef47-203">Completed</span></span>
- <span data-ttu-id="cef47-204">Ошибка</span><span class="sxs-lookup"><span data-stu-id="cef47-204">Failed</span></span>
- <span data-ttu-id="cef47-205">Остановлена</span><span class="sxs-lookup"><span data-stu-id="cef47-205">Stopped</span></span>
- <span data-ttu-id="cef47-206">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="cef47-206">Suspended</span></span>
- <span data-ttu-id="cef47-207">Отключено</span><span class="sxs-lookup"><span data-stu-id="cef47-207">Disconnected</span></span>

<span data-ttu-id="cef47-208">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="cef47-208">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="cef47-209">-Id</span><span class="sxs-lookup"><span data-stu-id="cef47-209">-Id</span></span>

<span data-ttu-id="cef47-210">Указывает массив идентификаторов заданий, для которых этот командлет ожидает выполнения.</span><span class="sxs-lookup"><span data-stu-id="cef47-210">Specifies an array of IDs of jobs for which this cmdlet waits.</span></span>

<span data-ttu-id="cef47-211">Идентификатор — это целое число, которое однозначно определяет задание в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="cef47-211">The ID is an integer that uniquely identifies the job in the current session.</span></span>
<span data-ttu-id="cef47-212">Проще запомнить и ввести, чем идентификатор экземпляра, но он уникален только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="cef47-212">It is easier to remember and type than the instance ID, but it is unique only in the current session.</span></span>
<span data-ttu-id="cef47-213">Можно ввести один или несколько идентификаторов, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="cef47-213">You can type one or more IDs, separated by commas.</span></span>
<span data-ttu-id="cef47-214">Чтобы найти идентификатор задания, введите `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="cef47-214">To find the ID of a job, type `Get-Job`.</span></span>

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

### <span data-ttu-id="cef47-215">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="cef47-215">-InstanceId</span></span>

<span data-ttu-id="cef47-216">Указывает массив идентификаторов экземпляров заданий, для которых этот командлет ожидает выполнения.</span><span class="sxs-lookup"><span data-stu-id="cef47-216">Specifies an array of instance IDs of jobs for which this cmdlet waits.</span></span>
<span data-ttu-id="cef47-217">По умолчанию останавливаются все задания.</span><span class="sxs-lookup"><span data-stu-id="cef47-217">The default is all jobs.</span></span>

<span data-ttu-id="cef47-218">Идентификатор экземпляра — это GUID, который однозначно определяет задание на компьютере.</span><span class="sxs-lookup"><span data-stu-id="cef47-218">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span>
<span data-ttu-id="cef47-219">Чтобы узнать идентификатор экземпляра задания, используйте командлет **Get-Job**.</span><span class="sxs-lookup"><span data-stu-id="cef47-219">To find the instance ID of a job, use **Get-Job**.</span></span>

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

### <span data-ttu-id="cef47-220">-Job</span><span class="sxs-lookup"><span data-stu-id="cef47-220">-Job</span></span>

<span data-ttu-id="cef47-221">Указывает задания, для которых этот командлет ожидает.</span><span class="sxs-lookup"><span data-stu-id="cef47-221">Specifies the jobs for which this cmdlet waits.</span></span>
<span data-ttu-id="cef47-222">Введите переменную, содержащую объекты заданий, либо команду, которая их возвращают.</span><span class="sxs-lookup"><span data-stu-id="cef47-222">Enter a variable that contains the job objects or a command that gets the job objects.</span></span>
<span data-ttu-id="cef47-223">Можно также использовать оператор конвейера для отправки объектов задания в командлет **Wait-Job** .</span><span class="sxs-lookup"><span data-stu-id="cef47-223">You can also use a pipeline operator to send job objects to the **Wait-Job** cmdlet.</span></span>
<span data-ttu-id="cef47-224">По умолчанию **Wait-Job** ожидает все задания, созданные в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="cef47-224">By default, **Wait-Job** waits for all jobs created in the current session.</span></span>

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

### <span data-ttu-id="cef47-225">-Name</span><span class="sxs-lookup"><span data-stu-id="cef47-225">-Name</span></span>

<span data-ttu-id="cef47-226">Указывает понятные имена заданий, для которых этот командлет ожидает выполнения.</span><span class="sxs-lookup"><span data-stu-id="cef47-226">Specifies friendly names of jobs for which this cmdlet waits.</span></span>

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

### <span data-ttu-id="cef47-227">-State</span><span class="sxs-lookup"><span data-stu-id="cef47-227">-State</span></span>

<span data-ttu-id="cef47-228">Указывает состояние задания.</span><span class="sxs-lookup"><span data-stu-id="cef47-228">Specifies a job state.</span></span>
<span data-ttu-id="cef47-229">Этот командлет ожидает только задания в указанном состоянии.</span><span class="sxs-lookup"><span data-stu-id="cef47-229">This cmdlet waits only for jobs in the specified state.</span></span>
<span data-ttu-id="cef47-230">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="cef47-230">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="cef47-231">NotStarted</span><span class="sxs-lookup"><span data-stu-id="cef47-231">NotStarted</span></span>
- <span data-ttu-id="cef47-232">Запущен</span><span class="sxs-lookup"><span data-stu-id="cef47-232">Running</span></span>
- <span data-ttu-id="cef47-233">Завершено</span><span class="sxs-lookup"><span data-stu-id="cef47-233">Completed</span></span>
- <span data-ttu-id="cef47-234">Ошибка</span><span class="sxs-lookup"><span data-stu-id="cef47-234">Failed</span></span>
- <span data-ttu-id="cef47-235">Остановлена</span><span class="sxs-lookup"><span data-stu-id="cef47-235">Stopped</span></span>
- <span data-ttu-id="cef47-236">Блокировано</span><span class="sxs-lookup"><span data-stu-id="cef47-236">Blocked</span></span>
- <span data-ttu-id="cef47-237">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="cef47-237">Suspended</span></span>
- <span data-ttu-id="cef47-238">Отключено</span><span class="sxs-lookup"><span data-stu-id="cef47-238">Disconnected</span></span>
- <span data-ttu-id="cef47-239">Приостановка</span><span class="sxs-lookup"><span data-stu-id="cef47-239">Suspending</span></span>
- <span data-ttu-id="cef47-240">Остановка</span><span class="sxs-lookup"><span data-stu-id="cef47-240">Stopping</span></span>

<span data-ttu-id="cef47-241">Дополнительные сведения о состояниях заданий см. в разделе [перечисление JobState](https://msdn.microsoft.com/library/system.management.automation.jobstate) в библиотеке MSDN.</span><span class="sxs-lookup"><span data-stu-id="cef47-241">For more information about job states, see [JobState Enumeration](https://msdn.microsoft.com/library/system.management.automation.jobstate) in the MSDN library.</span></span>

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

### <span data-ttu-id="cef47-242">-Timeout</span><span class="sxs-lookup"><span data-stu-id="cef47-242">-Timeout</span></span>

<span data-ttu-id="cef47-243">Задает максимальное время ожидания для каждого фонового задания в секундах.</span><span class="sxs-lookup"><span data-stu-id="cef47-243">Specifies the maximum wait time for each background job, in seconds.</span></span>
<span data-ttu-id="cef47-244">Значение по умолчанию – 1 указывает, что командлет ожидает завершения задания.</span><span class="sxs-lookup"><span data-stu-id="cef47-244">The default value, -1, indicates that the cmdlet waits until the job finishes.</span></span>
<span data-ttu-id="cef47-245">Отсчет времени начинается при отправке команды **Wait-Job** , а не команды **Start-Job** .</span><span class="sxs-lookup"><span data-stu-id="cef47-245">The timing starts when you submit the **Wait-Job** command, not the **Start-Job** command.</span></span>

<span data-ttu-id="cef47-246">Если указанное время истекло, ожидание прекращается, а окно командной строки становится активным, даже если задание все еще выполняется.</span><span class="sxs-lookup"><span data-stu-id="cef47-246">If this time is exceeded, the wait ends and the command prompt returns, even if the job is still running.</span></span>
<span data-ttu-id="cef47-247">Команда не отображает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="cef47-247">The command does not display any error message.</span></span>

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

### <span data-ttu-id="cef47-248">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="cef47-248">CommonParameters</span></span>

<span data-ttu-id="cef47-249">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="cef47-249">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cef47-250">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="cef47-250">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cef47-251">Входные данные</span><span class="sxs-lookup"><span data-stu-id="cef47-251">INPUTS</span></span>

### <span data-ttu-id="cef47-252">System. Management. Automation. Ремотингжоб</span><span class="sxs-lookup"><span data-stu-id="cef47-252">System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="cef47-253">Объект задания можно передать в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="cef47-253">You can pipe a job object to this cmdlet.</span></span>

## <span data-ttu-id="cef47-254">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="cef47-254">OUTPUTS</span></span>

### <span data-ttu-id="cef47-255">System. Management. Automation. Псремотингжоб</span><span class="sxs-lookup"><span data-stu-id="cef47-255">System.Management.Automation.PSRemotingJob</span></span>

<span data-ttu-id="cef47-256">Этот командлет возвращает объекты задания, представляющие завершенные задания.</span><span class="sxs-lookup"><span data-stu-id="cef47-256">This cmdlet returns job objects that represent the completed jobs.</span></span>
<span data-ttu-id="cef47-257">Если ожидание заканчивается из-за превышения значения параметра *timeout* , то **Wait-Job** не возвращает никаких объектов.</span><span class="sxs-lookup"><span data-stu-id="cef47-257">If the wait ends because the value of the *Timeout* parameter is exceeded, **Wait-Job** does not return any objects.</span></span>

## <span data-ttu-id="cef47-258">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="cef47-258">NOTES</span></span>

* <span data-ttu-id="cef47-259">По умолчанию **Wait-Job** Возвращает или завершает ожидание, если задания находятся в одном из следующих состояний:</span><span class="sxs-lookup"><span data-stu-id="cef47-259">By default, **Wait-Job** returns, or ends the wait, when jobs are in one of the following states:</span></span>

- <span data-ttu-id="cef47-260">Завершено</span><span class="sxs-lookup"><span data-stu-id="cef47-260">Completed</span></span>
- <span data-ttu-id="cef47-261">Ошибка</span><span class="sxs-lookup"><span data-stu-id="cef47-261">Failed</span></span>
- <span data-ttu-id="cef47-262">Остановлена</span><span class="sxs-lookup"><span data-stu-id="cef47-262">Stopped</span></span>
- <span data-ttu-id="cef47-263">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="cef47-263">Suspended</span></span>
- <span data-ttu-id="cef47-264">Отключено **от прямого ожидания — задание** для продолжения ожидания приостановленных и отключенных заданий, используйте параметр *Force* .</span><span class="sxs-lookup"><span data-stu-id="cef47-264">Disconnected To direct **Wait-Job** to continue to wait for Suspended and Disconnected jobs, use the *Force* parameter.</span></span>

## <span data-ttu-id="cef47-265">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="cef47-265">RELATED LINKS</span></span>

[<span data-ttu-id="cef47-266">Get-Job.</span><span class="sxs-lookup"><span data-stu-id="cef47-266">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="cef47-267">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="cef47-267">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="cef47-268">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="cef47-268">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="cef47-269">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="cef47-269">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="cef47-270">Start-Job</span><span class="sxs-lookup"><span data-stu-id="cef47-270">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="cef47-271">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="cef47-271">Stop-Job</span></span>](Stop-Job.md)

