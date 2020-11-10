---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/suspend-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-Job
ms.openlocfilehash: 9b18782fae77fa0776aa2cfaa39b74a2292099d9
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388473"
---
# <span data-ttu-id="1278b-103">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="1278b-103">Suspend-Job</span></span>

## <span data-ttu-id="1278b-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="1278b-104">SYNOPSIS</span></span>
<span data-ttu-id="1278b-105">Временно останавливает задания рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="1278b-105">Temporarily stops workflow jobs.</span></span>

## <span data-ttu-id="1278b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1278b-106">SYNTAX</span></span>

### <span data-ttu-id="1278b-107">Сессионидпараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="1278b-107">SessionIdParameterSet (Default)</span></span>

```
Suspend-Job [-Force] [-Wait] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1278b-108">жобпараметерсет</span><span class="sxs-lookup"><span data-stu-id="1278b-108">JobParameterSet</span></span>

```
Suspend-Job [-Job] <Job[]> [-Force] [-Wait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1278b-109">намепараметерсет</span><span class="sxs-lookup"><span data-stu-id="1278b-109">NameParameterSet</span></span>

```
Suspend-Job [-Force] [-Wait] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1278b-110">инстанцеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="1278b-110">InstanceIdParameterSet</span></span>

```
Suspend-Job [-Force] [-Wait] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1278b-111">филтерпараметерсет</span><span class="sxs-lookup"><span data-stu-id="1278b-111">FilterParameterSet</span></span>

```
Suspend-Job [-Force] [-Wait] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1278b-112">статепараметерсет</span><span class="sxs-lookup"><span data-stu-id="1278b-112">StateParameterSet</span></span>

```
Suspend-Job [-Force] [-Wait] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="1278b-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1278b-113">DESCRIPTION</span></span>

<span data-ttu-id="1278b-114">`Suspend-Job`Командлет приостанавливает задания рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1278b-114">The `Suspend-Job` cmdlet suspends workflow jobs.</span></span> <span data-ttu-id="1278b-115">Приостановка означает временное прерывание или приостановку задания рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1278b-115">Suspend means to temporarily interrupt or pause a workflow job.</span></span> <span data-ttu-id="1278b-116">Он позволяет пользователям, выполняющим рабочие процессы, приостанавливать их.</span><span class="sxs-lookup"><span data-stu-id="1278b-116">This cmdlet allows users who are running workflows to suspend the workflow.</span></span> <span data-ttu-id="1278b-117">Он дополняет действие приостановки рабочего процесса https://go.microsoft.com/fwlink/?LinkId=267141 , которое является командой в рабочем процессе, которая приостанавливает рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="1278b-117">It complements the Suspend-Workflowhttps://go.microsoft.com/fwlink/?LinkId=267141 activity, which is a command in the workflow that suspends the workflow.</span></span>

<span data-ttu-id="1278b-118">`Suspend-Job`Командлет работает только с заданиями рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1278b-118">The `Suspend-Job` cmdlet works only on workflow jobs.</span></span> <span data-ttu-id="1278b-119">Он не работает для стандартных фоновых заданий, например для тех, которые запускаются с помощью `Start-Job` командлета.</span><span class="sxs-lookup"><span data-stu-id="1278b-119">It does not work on standard background jobs, such as those that are started by using the `Start-Job` cmdlet.</span></span>

<span data-ttu-id="1278b-120">Определить задание рабочего процесса можно по значению PSWorkflowJob свойства **PSJobTypeName** задания.</span><span class="sxs-lookup"><span data-stu-id="1278b-120">To identify a workflow job, look for a value of PSWorkflowJob in the **PSJobTypeName** property of the job.</span></span> <span data-ttu-id="1278b-121">Чтобы определить, поддерживает ли конкретный тип настраиваемого задания `Suspend-Job` командлет, см. разделы справки для типа настраиваемого задания.</span><span class="sxs-lookup"><span data-stu-id="1278b-121">To determine whether a particular custom job type supports the `Suspend-Job` cmdlet, see the help topics for the custom job type.</span></span>

<span data-ttu-id="1278b-122">Когда вы приостанавливаете задание рабочего процесса, оно выполняется до следующей контрольной точки, приостанавливается и немедленно возвращает объект задания рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1278b-122">When you suspend a workflow job, the workflow job runs to the next checkpoint, suspends, and immediately returns a workflow job object.</span></span> <span data-ttu-id="1278b-123">Чтобы дождаться завершения приостановки перед получением задания, используйте параметр **Wait** `Suspend-Job` `Wait-Job` командлета или.</span><span class="sxs-lookup"><span data-stu-id="1278b-123">To wait for the suspension to complete before getting the job, use the **Wait** parameter of `Suspend-Job` or the `Wait-Job` cmdlet.</span></span> <span data-ttu-id="1278b-124">При приостановке задания рабочего процесса значение свойства **State** для задания приостанавливается.</span><span class="sxs-lookup"><span data-stu-id="1278b-124">When the workflow job is suspended, the value of the **State** property of the job is Suspended.</span></span>

<span data-ttu-id="1278b-125">Правильность приостановки зависит от контрольных точек.</span><span class="sxs-lookup"><span data-stu-id="1278b-125">Suspending correctly relies on checkpoints.</span></span> <span data-ttu-id="1278b-126">Текущее состояние задания, метаданные и выходные данные сохраняются в контрольной точке, поэтому задание рабочего процесса можно возобновить без потери состояния или данных.</span><span class="sxs-lookup"><span data-stu-id="1278b-126">The current job state, metadata, and output are saved in the checkpoint so the workflow job can be resumed without loss of state or data.</span></span> <span data-ttu-id="1278b-127">Если у задания рабочего процесса нет контрольных точек, его нельзя приостановить правильно.</span><span class="sxs-lookup"><span data-stu-id="1278b-127">If the workflow job does not have checkpoints, it cannot be suspended correctly.</span></span> <span data-ttu-id="1278b-128">Чтобы добавить контрольные точки в выполняемый рабочий процесс, используйте общий параметр рабочего процесса **PSPersist**.</span><span class="sxs-lookup"><span data-stu-id="1278b-128">To add checkpoints to a workflow that you are running, use the **PSPersist** workflow common parameter.</span></span> <span data-ttu-id="1278b-129">Можно использовать параметр **Force** , чтобы немедленно приостановить любое задание рабочего процесса и приостановить задание рабочего процесса, у которого нет контрольных точек, но это действие может привести к потере состояния и данных.</span><span class="sxs-lookup"><span data-stu-id="1278b-129">You can use the **Force** parameter to suspend any workflow job immediately and to suspend a workflow job that does not have checkpoints, but the action could cause loss of state and data.</span></span>

<span data-ttu-id="1278b-130">Перед использованием командлета задания для настраиваемого типа задания, например задания рабочего процесса ( **псворкфловжоб** ), импортируйте модуль, поддерживающий тип настраиваемого задания, с помощью `Import-Module` командлета или с помощью командлета в модуле.</span><span class="sxs-lookup"><span data-stu-id="1278b-130">Before you use a Job cmdlet on a custom job type, such as a workflow job ( **PSWorkflowJob** ) import the module that supports the custom job type, either by using the `Import-Module` cmdlet or using or using a cmdlet in the module.</span></span>

<span data-ttu-id="1278b-131">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="1278b-131">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="1278b-132">Примеры</span><span class="sxs-lookup"><span data-stu-id="1278b-132">EXAMPLES</span></span>

### <span data-ttu-id="1278b-133">Пример 1. Приостановка задания рабочего процесса по имени</span><span class="sxs-lookup"><span data-stu-id="1278b-133">Example 1: Suspend a workflow job by name</span></span>

<span data-ttu-id="1278b-134">В этом примере показано, как приостановить задание рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1278b-134">This example shows how to suspend a workflow job.</span></span>

<span data-ttu-id="1278b-135">Первая команда создает `Get-SystemLog` Рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="1278b-135">The first command creates the `Get-SystemLog` workflow.</span></span> <span data-ttu-id="1278b-136">Рабочий процесс использует `CheckPoint-Workflow` действие для определения контрольной точки в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="1278b-136">The workflow uses the `CheckPoint-Workflow` activity to define a checkpoint in the workflow.</span></span>

<span data-ttu-id="1278b-137">Вторая команда использует параметр **AsJob** , который является общим для всех рабочих процессов для запуска `Get-SystemLog` рабочего процесса в качестве фонового задания.</span><span class="sxs-lookup"><span data-stu-id="1278b-137">The second command uses the **AsJob** parameter that is common to all workflows to run the `Get-SystemLog` workflow as a background job.</span></span> <span data-ttu-id="1278b-138">В команде используется общий параметр рабочих процессов **JobName** для указания понятного имени задания рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1278b-138">The command uses the **JobName** workflow common parameter to specify a friendly name for the workflow job.</span></span>

<span data-ttu-id="1278b-139">Третья команда использует `Get-Job` командлет для получения `Get-SystemLogJob` задания рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1278b-139">The third command uses the `Get-Job` cmdlet to get the `Get-SystemLogJob` workflow job.</span></span> <span data-ttu-id="1278b-140">В выходных данных показано, что значение свойства **псжобтипенаме** равно псворкфловжоб.</span><span class="sxs-lookup"><span data-stu-id="1278b-140">The output shows that the value of the **PSJobTypeName** property is PSWorkflowJob.</span></span>

<span data-ttu-id="1278b-141">Четвертая команда использует `Suspend-Job` командлет для приостановки `Get-SystemLogJob` задания.</span><span class="sxs-lookup"><span data-stu-id="1278b-141">The fourth command uses the `Suspend-Job` cmdlet to suspend the `Get-SystemLogJob` job.</span></span> <span data-ttu-id="1278b-142">Задание выполняется до контрольной точки, а затем приостанавливается.</span><span class="sxs-lookup"><span data-stu-id="1278b-142">The job runs to the checkpoint and then suspends.</span></span>

```
#Sample WorkflowWorkflow Get-SystemLog
{
    $Events = Get-WinEvent -LogName System
    CheckPoint-Workflow
    InlineScript {\\Server01\Scripts\Analyze-SystemEvents.ps1 -Events $Events}
}

PS C:\> Get-SystemLog -AsJob -JobName "Get-SystemLogJob"

PS C:\> Get-Job -Name Get-SystemLogJob
Id     Name              PSJobTypeName   State       HasMoreData     Location   Command
--     ----              -------------   -----       -----------     --------   -------
4      Get-SystemLogJob  PSWorkflowJob   Running     True            localhost   Get-SystemLog

PS C:\> Suspend-Job -Name Get-SystemLogJob
Id     Name              PSJobTypeName   State       HasMoreData     Location   Command
--     ----              -------------   -----       -----------     --------   -------
4      Get-SystemLogJob  PSWorkflowJob   Suspended   True            localhost   Get-SystemLog
```


### <span data-ttu-id="1278b-143">Пример 2. Приостановка и возобновление задания рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="1278b-143">Example 2: Suspend and resume a workflow job</span></span>

<span data-ttu-id="1278b-144">В этом примере показано, как приостановить, а затем возобновить задание рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1278b-144">This example shows how to suspend and resume a workflow job.</span></span>

<span data-ttu-id="1278b-145">Первая команда приостанавливает задание Логворкфловжоб. Команда возвращает значение немедленно.</span><span class="sxs-lookup"><span data-stu-id="1278b-145">The first command suspends the LogWorkflowJob job.The command returns immediately.</span></span> <span data-ttu-id="1278b-146">Выходные данные показывают, что задание рабочего процесса все еще выполняется, даже если оно приостановлено.</span><span class="sxs-lookup"><span data-stu-id="1278b-146">The output shows that the workflow job is still running, even though it is being suspended.</span></span>

<span data-ttu-id="1278b-147">Вторая команда использует `Get-Job` командлет для получения задания логворкфловжоб.</span><span class="sxs-lookup"><span data-stu-id="1278b-147">The second command uses the `Get-Job` cmdlet to get the LogWorkflowJob job.</span></span> <span data-ttu-id="1278b-148">В выходных данных видно, что задание рабочего процесса успешно приостановлено.</span><span class="sxs-lookup"><span data-stu-id="1278b-148">The output shows that the workflow job suspended successfully.</span></span>

<span data-ttu-id="1278b-149">Третья команда использует командлет, `Get-Job` чтобы получить задание логворкфловжоб и `Resume-Job` командлет для его возобновления.</span><span class="sxs-lookup"><span data-stu-id="1278b-149">The third command uses the `Get-Job` cmdlet to get the LogWorkflowJob job and the `Resume-Job` cmdlet to resume it.</span></span> <span data-ttu-id="1278b-150">В выходных данных видно, что задание рабочего процесса успешно возобновлено и в данный момент выполняется.</span><span class="sxs-lookup"><span data-stu-id="1278b-150">The output shows that the workflow job resumed successfully and is now running.</span></span>

```
PS C:\> Suspend-Job -Name LogWorkflowJob
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Running       True            localhost            LogWorkflow

PS C:\> Get-Job -Name LogWorkflowJob
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Suspended     True            localhost            LogWorkflow

PS C:\> Get-Job -Name LogWorkflowJob | Resume-Job
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Running       True            localhost            LogWorkflow
```


### <span data-ttu-id="1278b-151">Пример 3. Приостановка задания рабочего процесса на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="1278b-151">Example 3: Suspend a workflow job on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Srv01 -Scriptblock {Suspend-Job -Filter @{CustomID="031589"}
```

<span data-ttu-id="1278b-152">Эта команда использует `Invoke-Command` командлет для приостановки задания рабочего процесса на удаленном компьютере SRV01.</span><span class="sxs-lookup"><span data-stu-id="1278b-152">This command uses the `Invoke-Command` cmdlet to suspend a workflow job on the Srv01 remote computer.</span></span> <span data-ttu-id="1278b-153">Значение параметра **фильтра** — это хэш-таблица, которая указывает выбранное значение.</span><span class="sxs-lookup"><span data-stu-id="1278b-153">The value of the **Filter** parameter is a hash table that specifies a CustomID value.</span></span>
<span data-ttu-id="1278b-154">**CustomID**  — это метаданные задания ( **PSPrivateMetadata** ).</span><span class="sxs-lookup"><span data-stu-id="1278b-154">This **CustomID** is job metadata ( **PSPrivateMetadata** ).</span></span>

### <span data-ttu-id="1278b-155">Пример 4. Ожидание приостановки задания рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="1278b-155">Example 4: Wait for the workflow job to suspend</span></span>

```
PS C:\> Suspend-Job VersionCheck -Wait
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
 5     VersionCheck  PSWorkflowJob      Suspended     True            localhost            LogWorkflow
```

<span data-ttu-id="1278b-156">Эта команда приостанавливает задание рабочего процесса VersionCheck.</span><span class="sxs-lookup"><span data-stu-id="1278b-156">This command suspends the VersionCheck workflow job.</span></span> <span data-ttu-id="1278b-157">В ней используется параметр **Wait** для указания того, что необходимо дождаться, когда задание рабочего процесса будет приостановлено.</span><span class="sxs-lookup"><span data-stu-id="1278b-157">The command uses the **Wait** parameter to wait until the workflow job is suspended.</span></span> <span data-ttu-id="1278b-158">Когда задание рабочего процесса выполняется до следующей контрольной точки и приостанавливается, команда завершается и возвращает объект задания.</span><span class="sxs-lookup"><span data-stu-id="1278b-158">When the workflow job runs to the next checkpoint and is suspended, the command finishes and returns the job object.</span></span>

### <span data-ttu-id="1278b-159">Пример 5. принудительное Приостановка задания рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="1278b-159">Example 5: Force a workflow job to suspend</span></span>

```
PS C:\> Suspend-Job Maintenance -Force
```

<span data-ttu-id="1278b-160">Эта команда принудительно приостанавливает задание рабочего процесса Maintenance.</span><span class="sxs-lookup"><span data-stu-id="1278b-160">This command suspends the Maintenance workflow job forcibly.</span></span> <span data-ttu-id="1278b-161">У задания обслуживания нет контрольных точек.</span><span class="sxs-lookup"><span data-stu-id="1278b-161">The Maintenance job does not have checkpoints.</span></span> <span data-ttu-id="1278b-162">Она не может быть приостановлена правильно и может возобновиться неправильно.</span><span class="sxs-lookup"><span data-stu-id="1278b-162">It cannot be suspended correctly and might not resume correctly.</span></span>

## <span data-ttu-id="1278b-163">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1278b-163">PARAMETERS</span></span>

### <span data-ttu-id="1278b-164">-Filter</span><span class="sxs-lookup"><span data-stu-id="1278b-164">-Filter</span></span>

<span data-ttu-id="1278b-165">Указывает хэш-таблицу условий.</span><span class="sxs-lookup"><span data-stu-id="1278b-165">Specifies a hash table of conditions.</span></span> <span data-ttu-id="1278b-166">Этот командлет приостанавливает задания, которые отвечают всем условиям.</span><span class="sxs-lookup"><span data-stu-id="1278b-166">This cmdlet suspends jobs that satisfy all of the conditions.</span></span>
<span data-ttu-id="1278b-167">Введите хэш-таблицу, где ключи являются свойствами заданий, а значения — значениями этих свойств.</span><span class="sxs-lookup"><span data-stu-id="1278b-167">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

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

### <span data-ttu-id="1278b-168">-Force</span><span class="sxs-lookup"><span data-stu-id="1278b-168">-Force</span></span>

<span data-ttu-id="1278b-169">Мгновенно приостанавливает задание рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1278b-169">Suspends the workflow job immediately.</span></span> <span data-ttu-id="1278b-170">Это действие может привести к потере состояния и данных.</span><span class="sxs-lookup"><span data-stu-id="1278b-170">This action could cause a loss of state and data.</span></span>

<span data-ttu-id="1278b-171">По умолчанию `Suspend-Job` разрешает выполнение задания рабочего процесса до следующей контрольной точки, а затем приостанавливает ее.</span><span class="sxs-lookup"><span data-stu-id="1278b-171">By default, `Suspend-Job` lets the workflow job run until the next checkpoint and then suspends it.</span></span>
<span data-ttu-id="1278b-172">С помощью этого параметра можно также приостанавливать задания рабочих процессов, у которых нет контрольных точек.</span><span class="sxs-lookup"><span data-stu-id="1278b-172">You can also use this parameter to suspend workflow jobs that do not have checkpoints.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: F

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1278b-173">-Id</span><span class="sxs-lookup"><span data-stu-id="1278b-173">-Id</span></span>

<span data-ttu-id="1278b-174">Указывает идентификаторы заданий, приостанавливаемых этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="1278b-174">Specifies the IDs of jobs that this cmdlet suspends.</span></span>

<span data-ttu-id="1278b-175">Идентификатор — это целое число, которое однозначно определяет задание в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="1278b-175">The ID is an integer that uniquely identifies the job in the current session.</span></span> <span data-ttu-id="1278b-176">Проще запомнить и ввести, чем идентификатор экземпляра, но он уникален только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="1278b-176">It is easier to remember and to type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="1278b-177">Можно ввести один или несколько идентификаторов, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="1278b-177">You can type one or more IDs, separated by commas.</span></span> <span data-ttu-id="1278b-178">Чтобы найти идентификатор задания, используйте `Get-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="1278b-178">To find the ID of a job, use the `Get-Job` cmdlet.</span></span>

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

### <span data-ttu-id="1278b-179">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="1278b-179">-InstanceId</span></span>

<span data-ttu-id="1278b-180">Указывает идентификаторы экземпляров заданий, приостанавливаемых этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="1278b-180">Specifies the instance IDs of jobs that this cmdlet suspends.</span></span> <span data-ttu-id="1278b-181">По умолчанию останавливаются все задания.</span><span class="sxs-lookup"><span data-stu-id="1278b-181">The default is all jobs.</span></span>

<span data-ttu-id="1278b-182">Идентификатор экземпляра — это GUID, который однозначно определяет задание на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1278b-182">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span> <span data-ttu-id="1278b-183">Чтобы найти идентификатор экземпляра задания, используйте `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="1278b-183">To find the instance ID of a job, use `Get-Job`.</span></span>

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

### <span data-ttu-id="1278b-184">-Job</span><span class="sxs-lookup"><span data-stu-id="1278b-184">-Job</span></span>

<span data-ttu-id="1278b-185">Указывает задания рабочего процесса, которые останавливаются этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="1278b-185">Specifies the workflow jobs that this cmdlet stops.</span></span> <span data-ttu-id="1278b-186">Введите переменную, которая содержит задания рабочих процессов, или команду, которая получает их.</span><span class="sxs-lookup"><span data-stu-id="1278b-186">Enter a variable that contains the workflow jobs or a command that gets the workflow jobs.</span></span> <span data-ttu-id="1278b-187">Вы также можете передать задания рабочего процесса в `Suspend-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="1278b-187">You can also pipe workflow jobs to the `Suspend-Job` cmdlet.</span></span>

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

### <span data-ttu-id="1278b-188">-Name</span><span class="sxs-lookup"><span data-stu-id="1278b-188">-Name</span></span>

<span data-ttu-id="1278b-189">Указывает понятные имена заданий, приостанавливаемых этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="1278b-189">Specifies friendly names of jobs that this cmdlet suspends.</span></span> <span data-ttu-id="1278b-190">Введите одно или несколько имен заданий рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="1278b-190">Enter one or more workflow job names.</span></span>
<span data-ttu-id="1278b-191">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="1278b-191">Wildcard characters are supported.</span></span>

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

### <span data-ttu-id="1278b-192">-State</span><span class="sxs-lookup"><span data-stu-id="1278b-192">-State</span></span>

<span data-ttu-id="1278b-193">Указывает состояние задания.</span><span class="sxs-lookup"><span data-stu-id="1278b-193">Specifies a job state.</span></span> <span data-ttu-id="1278b-194">Этот командлет останавливает только задания в указанном состоянии.</span><span class="sxs-lookup"><span data-stu-id="1278b-194">This cmdlet stops only jobs in the specified state.</span></span> <span data-ttu-id="1278b-195">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="1278b-195">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="1278b-196">NotStarted</span><span class="sxs-lookup"><span data-stu-id="1278b-196">NotStarted</span></span>
- <span data-ttu-id="1278b-197">Запущен</span><span class="sxs-lookup"><span data-stu-id="1278b-197">Running</span></span>
- <span data-ttu-id="1278b-198">Завершено</span><span class="sxs-lookup"><span data-stu-id="1278b-198">Completed</span></span>
- <span data-ttu-id="1278b-199">Ошибка</span><span class="sxs-lookup"><span data-stu-id="1278b-199">Failed</span></span>
- <span data-ttu-id="1278b-200">Остановлена</span><span class="sxs-lookup"><span data-stu-id="1278b-200">Stopped</span></span>
- <span data-ttu-id="1278b-201">Блокировано</span><span class="sxs-lookup"><span data-stu-id="1278b-201">Blocked</span></span>
- <span data-ttu-id="1278b-202">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="1278b-202">Suspended</span></span>
- <span data-ttu-id="1278b-203">Отключено</span><span class="sxs-lookup"><span data-stu-id="1278b-203">Disconnected</span></span>
- <span data-ttu-id="1278b-204">Приостановка</span><span class="sxs-lookup"><span data-stu-id="1278b-204">Suspending</span></span>
- <span data-ttu-id="1278b-205">Остановка</span><span class="sxs-lookup"><span data-stu-id="1278b-205">Stopping</span></span>

<span data-ttu-id="1278b-206">`Suspend-Job` приостанавливает только задания рабочего процесса в состоянии **выполнения** .</span><span class="sxs-lookup"><span data-stu-id="1278b-206">`Suspend-Job` suspends only workflow jobs in the **Running** state.</span></span>

<span data-ttu-id="1278b-207">Дополнительные сведения о состояниях заданий см. в разделе [JobState enumeration](/dotnet/api/system.management.automation.jobstate).</span><span class="sxs-lookup"><span data-stu-id="1278b-207">For more information about job states, see [JobState Enumeration](/dotnet/api/system.management.automation.jobstate).</span></span>

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

### <span data-ttu-id="1278b-208">-Wait</span><span class="sxs-lookup"><span data-stu-id="1278b-208">-Wait</span></span>

<span data-ttu-id="1278b-209">Указывает, что этот командлет подавляет командную строку, пока задание рабочего процесса не находится в приостановленном состоянии.</span><span class="sxs-lookup"><span data-stu-id="1278b-209">Indicates that this cmdlet suppresses the command prompt until the workflow job is in the suspended state.</span></span> <span data-ttu-id="1278b-210">По умолчанию `Suspend-Job` возвращает значение немедленно, даже если задание рабочего процесса еще не находится в приостановленном состоянии.</span><span class="sxs-lookup"><span data-stu-id="1278b-210">By default, `Suspend-Job` returns immediately, even if the workflow job is not yet in the suspended state.</span></span>

<span data-ttu-id="1278b-211">Параметр **Wait** эквивалентен конвейеру команды в `Suspend-Job` `Wait-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="1278b-211">The **Wait** parameter is equivalent to piping a `Suspend-Job` command to the `Wait-Job` cmdlet.</span></span>

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

### <span data-ttu-id="1278b-212">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1278b-212">-Confirm</span></span>

<span data-ttu-id="1278b-213">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="1278b-213">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="1278b-214">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1278b-214">-WhatIf</span></span>

<span data-ttu-id="1278b-215">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="1278b-215">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="1278b-216">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="1278b-216">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="1278b-217">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="1278b-217">CommonParameters</span></span>

<span data-ttu-id="1278b-218">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1278b-218">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1278b-219">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1278b-219">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1278b-220">Входные данные</span><span class="sxs-lookup"><span data-stu-id="1278b-220">INPUTS</span></span>

### <span data-ttu-id="1278b-221">System. Management. Automation. job</span><span class="sxs-lookup"><span data-stu-id="1278b-221">System.Management.Automation.Job</span></span>

<span data-ttu-id="1278b-222">К этому командлету можно передать все типы заданий.</span><span class="sxs-lookup"><span data-stu-id="1278b-222">You can pipe all types of jobs to this cmdlet.</span></span> <span data-ttu-id="1278b-223">Однако если `Suspend-Job` получает задание неподдерживаемого типа, оно возвращает завершающую ошибку.</span><span class="sxs-lookup"><span data-stu-id="1278b-223">However, if `Suspend-Job` gets a job of an unsupported type, it returns a terminating error.</span></span>

## <span data-ttu-id="1278b-224">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1278b-224">OUTPUTS</span></span>

### <span data-ttu-id="1278b-225">System. Management. Automation. job</span><span class="sxs-lookup"><span data-stu-id="1278b-225">System.Management.Automation.Job</span></span>
<span data-ttu-id="1278b-226">Этот командлет возвращает приостановленные задания.</span><span class="sxs-lookup"><span data-stu-id="1278b-226">This cmdlet returns the jobs that it suspended.</span></span>

## <span data-ttu-id="1278b-227">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="1278b-227">NOTES</span></span>

- <span data-ttu-id="1278b-228">Механизм и место сохранения приостановленного задания могут различаться в зависимости от его типа.</span><span class="sxs-lookup"><span data-stu-id="1278b-228">The mechanism and location for saving a suspended job might vary depending on the job type.</span></span> <span data-ttu-id="1278b-229">Например, по умолчанию приостановленные задания рабочих процессов сохраняются в хранилище неструктурированных файлов, но также могут сохраняться в базе данных.</span><span class="sxs-lookup"><span data-stu-id="1278b-229">For example, suspended workflow jobs are saved in a flat file store by default, but can also be saved in a database.</span></span>
- <span data-ttu-id="1278b-230">При отправке задания рабочего процесса, которое не находится в состоянии выполняется, `Suspend-Job` выводится предупреждающее сообщение.</span><span class="sxs-lookup"><span data-stu-id="1278b-230">If you submit a workflow job that is not in the Running state, `Suspend-Job` displays a warning message.</span></span> <span data-ttu-id="1278b-231">Чтобы отключить это предупреждение, используйте общий параметр **WarningAction** со значением SilentlyContinue.</span><span class="sxs-lookup"><span data-stu-id="1278b-231">To suppress the warning, use the **WarningAction** common parameter with a value of SilentlyContinue.</span></span>

  <span data-ttu-id="1278b-232">Если задание не относится к типу, поддерживающему приостановку, функция `Suspend-Job` Возвращает завершающую ошибку.</span><span class="sxs-lookup"><span data-stu-id="1278b-232">If a job is not of a type that supports suspending, `Suspend-Job` returns a terminating error.</span></span>

- <span data-ttu-id="1278b-233">Чтобы найти приостановленные задания рабочего процесса, включая те, которые были приостановлены этим командлетом, используйте параметр **State** `Get-Job` командлета для получения заданий рабочего процесса в приостановленном состоянии.</span><span class="sxs-lookup"><span data-stu-id="1278b-233">To find the workflow jobs that are suspended, including those that were suspended by this cmdlet, use the **State** parameter of the `Get-Job` cmdlet to get workflow jobs in the Suspended state.</span></span>
- <span data-ttu-id="1278b-234">Задания некоторых типов имеют параметры или свойства, которые не позволяют среде Windows PowerShell приостанавливать их.</span><span class="sxs-lookup"><span data-stu-id="1278b-234">Some job types have options or properties that prevent Windows PowerShell from suspending the job.</span></span>
  <span data-ttu-id="1278b-235">Если попытки приостановить задание завершились ошибкой, убедитесь, что параметры задания и свойства допускают приостановку.</span><span class="sxs-lookup"><span data-stu-id="1278b-235">If attempts to suspend the job fail, verify that the job options and properties allow for suspending.</span></span>

## <span data-ttu-id="1278b-236">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="1278b-236">RELATED LINKS</span></span>

[<span data-ttu-id="1278b-237">Get-Job.</span><span class="sxs-lookup"><span data-stu-id="1278b-237">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="1278b-238">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="1278b-238">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="1278b-239">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="1278b-239">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="1278b-240">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="1278b-240">Resume-Job</span></span>](Resume-Job.md)

[<span data-ttu-id="1278b-241">Start-Job</span><span class="sxs-lookup"><span data-stu-id="1278b-241">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="1278b-242">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="1278b-242">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="1278b-243">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="1278b-243">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="1278b-244">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="1278b-244">Wait-Job</span></span>](Wait-Job.md)
