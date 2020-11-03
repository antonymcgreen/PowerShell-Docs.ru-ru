---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/suspend-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-Job
ms.openlocfilehash: 6ab50342e963832d89b3dfc4128a22fc16405926
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227026"
---
# <span data-ttu-id="9ac20-103">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="9ac20-103">Suspend-Job</span></span>

## <span data-ttu-id="9ac20-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="9ac20-104">SYNOPSIS</span></span>
<span data-ttu-id="9ac20-105">Временно останавливает задания рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="9ac20-105">Temporarily stops workflow jobs.</span></span>

## <span data-ttu-id="9ac20-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9ac20-106">SYNTAX</span></span>

### <span data-ttu-id="9ac20-107">Сессионидпараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="9ac20-107">SessionIdParameterSet (Default)</span></span>

```
Suspend-Job [-Force] [-Wait] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9ac20-108">жобпараметерсет</span><span class="sxs-lookup"><span data-stu-id="9ac20-108">JobParameterSet</span></span>

```
Suspend-Job [-Job] <Job[]> [-Force] [-Wait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9ac20-109">намепараметерсет</span><span class="sxs-lookup"><span data-stu-id="9ac20-109">NameParameterSet</span></span>

```
Suspend-Job [-Force] [-Wait] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9ac20-110">инстанцеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="9ac20-110">InstanceIdParameterSet</span></span>

```
Suspend-Job [-Force] [-Wait] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9ac20-111">филтерпараметерсет</span><span class="sxs-lookup"><span data-stu-id="9ac20-111">FilterParameterSet</span></span>

```
Suspend-Job [-Force] [-Wait] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9ac20-112">статепараметерсет</span><span class="sxs-lookup"><span data-stu-id="9ac20-112">StateParameterSet</span></span>

```
Suspend-Job [-Force] [-Wait] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9ac20-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9ac20-113">DESCRIPTION</span></span>
<span data-ttu-id="9ac20-114">Командлет **Suspend-Job** приостанавливает задания рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="9ac20-114">The **Suspend-Job** cmdlet suspends workflow jobs.</span></span>
<span data-ttu-id="9ac20-115">Приостановка означает временное прерывание или приостановку задания рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="9ac20-115">Suspend means to temporarily interrupt or pause a workflow job.</span></span>
<span data-ttu-id="9ac20-116">Он позволяет пользователям, выполняющим рабочие процессы, приостанавливать их.</span><span class="sxs-lookup"><span data-stu-id="9ac20-116">This cmdlet allows users who are running workflows to suspend the workflow.</span></span>
<span data-ttu-id="9ac20-117">Он дополняет действие приостановки рабочего процесса https://go.microsoft.com/fwlink/?LinkId=267141 , которое является командой в рабочем процессе, которая приостанавливает рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="9ac20-117">It complements the Suspend-Workflowhttps://go.microsoft.com/fwlink/?LinkId=267141 activity, which is a command in the workflow that suspends the workflow.</span></span>

<span data-ttu-id="9ac20-118">Командлет **Suspend-Job** применим только к заданиям рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="9ac20-118">The **Suspend-Job** cmdlet works only on workflow jobs.</span></span>
<span data-ttu-id="9ac20-119">Он не работает для стандартных фоновых заданий, например для тех, которые запускаются с помощью командлета Start-Job.</span><span class="sxs-lookup"><span data-stu-id="9ac20-119">It does not work on standard background jobs, such as those that are started by using the Start-Job cmdlet.</span></span>

<span data-ttu-id="9ac20-120">Определить задание рабочего процесса можно по значению PSWorkflowJob свойства **PSJobTypeName** задания.</span><span class="sxs-lookup"><span data-stu-id="9ac20-120">To identify a workflow job, look for a value of PSWorkflowJob in the **PSJobTypeName** property of the job.</span></span>
<span data-ttu-id="9ac20-121">Чтобы определить, поддерживает ли определенное задание настраиваемого типа командлет **Suspend-Job** , см. разделы справки по этому типу.</span><span class="sxs-lookup"><span data-stu-id="9ac20-121">To determine whether a particular custom job type supports the **Suspend-Job** cmdlet, see the help topics for the custom job type.</span></span>

<span data-ttu-id="9ac20-122">Когда вы приостанавливаете задание рабочего процесса, оно выполняется до следующей контрольной точки, приостанавливается и немедленно возвращает объект задания рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="9ac20-122">When you suspend a workflow job, the workflow job runs to the next checkpoint, suspends, and immediately returns a workflow job object.</span></span>
<span data-ttu-id="9ac20-123">Чтобы дождаться завершения приостановки перед получением задания, используйте параметр *Wait* командлета **Suspend-Job** или Wait-Job.</span><span class="sxs-lookup"><span data-stu-id="9ac20-123">To wait for the suspension to complete before getting the job, use the *Wait* parameter of **Suspend-Job** or the Wait-Job cmdlet.</span></span>
<span data-ttu-id="9ac20-124">При приостановке задания рабочего процесса значение свойства **State** для задания приостанавливается.</span><span class="sxs-lookup"><span data-stu-id="9ac20-124">When the workflow job is suspended, the value of the **State** property of the job is Suspended.</span></span>

<span data-ttu-id="9ac20-125">Правильность приостановки зависит от контрольных точек.</span><span class="sxs-lookup"><span data-stu-id="9ac20-125">Suspending correctly relies on checkpoints.</span></span>
<span data-ttu-id="9ac20-126">Текущее состояние задания, метаданные и выходные данные сохраняются в контрольной точке, поэтому задание рабочего процесса можно возобновить без потери состояния или данных.</span><span class="sxs-lookup"><span data-stu-id="9ac20-126">The current job state, metadata, and output are saved in the checkpoint so the workflow job can be resumed without loss of state or data.</span></span>
<span data-ttu-id="9ac20-127">Если у задания рабочего процесса нет контрольных точек, его нельзя приостановить правильно.</span><span class="sxs-lookup"><span data-stu-id="9ac20-127">If the workflow job does not have checkpoints, it cannot be suspended correctly.</span></span>
<span data-ttu-id="9ac20-128">Чтобы добавить контрольные точки в выполняемый рабочий процесс, используйте общий параметр рабочего процесса *PSPersist*.</span><span class="sxs-lookup"><span data-stu-id="9ac20-128">To add checkpoints to a workflow that you are running, use the *PSPersist* workflow common parameter.</span></span>
<span data-ttu-id="9ac20-129">Можно использовать параметр *Force* , чтобы немедленно приостановить любое задание рабочего процесса и приостановить задание рабочего процесса, у которого нет контрольных точек, но это действие может привести к потере состояния и данных.</span><span class="sxs-lookup"><span data-stu-id="9ac20-129">You can use the *Force* parameter to suspend any workflow job immediately and to suspend a workflow job that does not have checkpoints, but the action could cause loss of state and data.</span></span>

<span data-ttu-id="9ac20-130">Перед использованием командлета задания для настраиваемого типа задания, например задания рабочего процесса ( **псворкфловжоб** ), импортируйте модуль, поддерживающий тип настраиваемого задания, с помощью командлета Import-Module или с помощью или командлета в модуле.</span><span class="sxs-lookup"><span data-stu-id="9ac20-130">Before you use a Job cmdlet on a custom job type, such as a workflow job ( **PSWorkflowJob** ) import the module that supports the custom job type, either by using the Import-Module cmdlet or using or using a cmdlet in the module.</span></span>

<span data-ttu-id="9ac20-131">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="9ac20-131">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="9ac20-132">Примеры</span><span class="sxs-lookup"><span data-stu-id="9ac20-132">EXAMPLES</span></span>

### <span data-ttu-id="9ac20-133">Пример 1. Приостановка задания рабочего процесса по имени</span><span class="sxs-lookup"><span data-stu-id="9ac20-133">Example 1: Suspend a workflow job by name</span></span>

```
The first command creates the Get-SystemLog workflow. The workflow uses the CheckPoint-Workflow activity to define a checkpoint in the workflow.
#Sample WorkflowWorkflow Get-SystemLog
{
    $Events = Get-WinEvent -LogName System
    CheckPoint-Workflow
    InlineScript {\\Server01\Scripts\Analyze-SystemEvents.ps1 -Events $Events}
}

The second command uses the *AsJob* parameter that is common to all workflows to run the Get-SystemLog workflow as a background job. The command uses the *JobName* workflow common parameter to specify a friendly name for the workflow job.
PS C:\> Get-SystemLog -AsJob -JobName "Get-SystemLogJob"

The third command uses the **Get-Job** cmdlet to get the Get-SystemLogJob workflow job. The output shows that the value of the **PSJobTypeName** property is PSWorkflowJob.
PS C:\> Get-Job -Name Get-SystemLogJob
Id     Name              PSJobTypeName   State       HasMoreData     Location   Command
--     ----              -------------   -----       -----------     --------   -------
4      Get-SystemLogJob  PSWorkflowJob   Running     True            localhost   Get-SystemLog

The fourth command uses the **Suspend-Job** cmdlet to suspend the Get-SystemLogJob job. The job runs to the checkpoint and then suspends.
PS C:\> Suspend-Job -Name Get-SystemLogJob
Id     Name              PSJobTypeName   State       HasMoreData     Location   Command
--     ----              -------------   -----       -----------     --------   -------
4      Get-SystemLogJob  PSWorkflowJob   Suspended   True            localhost   Get-SystemLog
```

<span data-ttu-id="9ac20-134">В этом примере показано, как приостановить задание рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="9ac20-134">This example shows how to suspend a workflow job.</span></span>

### <span data-ttu-id="9ac20-135">Пример 2. Приостановка и возобновление задания рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="9ac20-135">Example 2: Suspend and resume a workflow job</span></span>

```
The first command suspends the LogWorkflowJob job.The command returns immediately. The output shows that the workflow job is still running, even though it is being suspended.
PS C:\> Suspend-Job -Name LogWorkflowJob
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Running       True            localhost            LogWorkflow

The second command uses the **Get-Job** cmdlet to get the LogWorkflowJob job. The output shows that the workflow job suspended successfully.
PS C:\> Get-Job -Name LogWorkflowJob
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Suspended     True            localhost            LogWorkflow

The third command uses the **Get-Job** cmdlet to get the LogWorkflowJob job and the Resume-Job cmdlet to resume it. The output shows that the workflow job resumed successfully and is now running.
PS C:\> Get-Job -Name LogWorkflowJob | Resume-Job
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Running       True            localhost            LogWorkflow
```

<span data-ttu-id="9ac20-136">В этом примере показано, как приостановить, а затем возобновить задание рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="9ac20-136">This example shows how to suspend and resume a workflow job.</span></span>

### <span data-ttu-id="9ac20-137">Пример 3. Приостановка задания рабочего процесса на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="9ac20-137">Example 3: Suspend a workflow job on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Srv01 -Scriptblock {Suspend-Job -Filter @{CustomID="031589"}
```

<span data-ttu-id="9ac20-138">Эта команда использует командлет Invoke-Command для приостановки задания рабочего процесса на удаленном компьютере SRV01.</span><span class="sxs-lookup"><span data-stu-id="9ac20-138">This command uses the Invoke-Command cmdlet to suspend a workflow job on the Srv01 remote computer.</span></span>
<span data-ttu-id="9ac20-139">Значение параметра *фильтра* — это хэш-таблица, которая указывает выбранное значение.</span><span class="sxs-lookup"><span data-stu-id="9ac20-139">The value of the *Filter* parameter is a hash table that specifies a CustomID value.</span></span>
<span data-ttu-id="9ac20-140">**CustomID**  — это метаданные задания ( **PSPrivateMetadata** ).</span><span class="sxs-lookup"><span data-stu-id="9ac20-140">This **CustomID** is job metadata ( **PSPrivateMetadata** ).</span></span>

### <span data-ttu-id="9ac20-141">Пример 4. Ожидание приостановки задания рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="9ac20-141">Example 4: Wait for the workflow job to suspend</span></span>

```
PS C:\> Suspend-Job VersionCheck -Wait
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
 5     VersionCheck  PSWorkflowJob      Suspended     True            localhost            LogWorkflow
```

<span data-ttu-id="9ac20-142">Эта команда приостанавливает задание рабочего процесса VersionCheck.</span><span class="sxs-lookup"><span data-stu-id="9ac20-142">This command suspends the VersionCheck workflow job.</span></span>
<span data-ttu-id="9ac20-143">В ней используется параметр *Wait* для указания того, что необходимо дождаться, когда задание рабочего процесса будет приостановлено.</span><span class="sxs-lookup"><span data-stu-id="9ac20-143">The command uses the *Wait* parameter to wait until the workflow job is suspended.</span></span>
<span data-ttu-id="9ac20-144">Когда задание рабочего процесса выполняется до следующей контрольной точки и приостанавливается, команда завершается и возвращает объект задания.</span><span class="sxs-lookup"><span data-stu-id="9ac20-144">When the workflow job runs to the next checkpoint and is suspended, the command finishes and returns the job object.</span></span>

### <span data-ttu-id="9ac20-145">Пример 5. принудительное Приостановка задания рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="9ac20-145">Example 5: Force a workflow job to suspend</span></span>

```
PS C:\> Suspend-Job Maintenance -Force
```

<span data-ttu-id="9ac20-146">Эта команда принудительно приостанавливает задание рабочего процесса Maintenance.</span><span class="sxs-lookup"><span data-stu-id="9ac20-146">This command suspends the Maintenance workflow job forcibly.</span></span>
<span data-ttu-id="9ac20-147">У задания обслуживания нет контрольных точек.</span><span class="sxs-lookup"><span data-stu-id="9ac20-147">The Maintenance job does not have checkpoints.</span></span>
<span data-ttu-id="9ac20-148">Она не может быть приостановлена правильно и может возобновиться неправильно.</span><span class="sxs-lookup"><span data-stu-id="9ac20-148">It cannot be suspended correctly and might not resume correctly.</span></span>

## <span data-ttu-id="9ac20-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9ac20-149">PARAMETERS</span></span>

### <span data-ttu-id="9ac20-150">-Filter</span><span class="sxs-lookup"><span data-stu-id="9ac20-150">-Filter</span></span>
<span data-ttu-id="9ac20-151">Указывает хэш-таблицу условий.</span><span class="sxs-lookup"><span data-stu-id="9ac20-151">Specifies a hash table of conditions.</span></span>
<span data-ttu-id="9ac20-152">Этот командлет приостанавливает задания, которые отвечают всем условиям.</span><span class="sxs-lookup"><span data-stu-id="9ac20-152">This cmdlet suspends jobs that satisfy all of the conditions.</span></span>
<span data-ttu-id="9ac20-153">Введите хэш-таблицу, где ключи являются свойствами заданий, а значения — значениями этих свойств.</span><span class="sxs-lookup"><span data-stu-id="9ac20-153">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

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

### <span data-ttu-id="9ac20-154">-Force</span><span class="sxs-lookup"><span data-stu-id="9ac20-154">-Force</span></span>
<span data-ttu-id="9ac20-155">Мгновенно приостанавливает задание рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="9ac20-155">Suspends the workflow job immediately.</span></span>
<span data-ttu-id="9ac20-156">Это действие может привести к потере состояния и данных.</span><span class="sxs-lookup"><span data-stu-id="9ac20-156">This action could cause a loss of state and data.</span></span>

<span data-ttu-id="9ac20-157">По умолчанию командлет **Suspend-Job** позволяет заданию рабочего процесса выполняться до следующей контрольной точки, после чего приостанавливает его.</span><span class="sxs-lookup"><span data-stu-id="9ac20-157">By default, **Suspend-Job** lets the workflow job run until the next checkpoint and then suspends it.</span></span>
<span data-ttu-id="9ac20-158">С помощью этого параметра можно также приостанавливать задания рабочих процессов, у которых нет контрольных точек.</span><span class="sxs-lookup"><span data-stu-id="9ac20-158">You can also use this parameter to suspend workflow jobs that do not have checkpoints.</span></span>

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

### <span data-ttu-id="9ac20-159">-Id</span><span class="sxs-lookup"><span data-stu-id="9ac20-159">-Id</span></span>
<span data-ttu-id="9ac20-160">Указывает идентификаторы заданий, приостанавливаемых этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="9ac20-160">Specifies the IDs of jobs that this cmdlet suspends.</span></span>

<span data-ttu-id="9ac20-161">Идентификатор — это целое число, которое однозначно определяет задание в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="9ac20-161">The ID is an integer that uniquely identifies the job in the current session.</span></span>
<span data-ttu-id="9ac20-162">Проще запомнить и ввести, чем идентификатор экземпляра, но он уникален только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="9ac20-162">It is easier to remember and to type than the instance ID, but it is unique only in the current session.</span></span>
<span data-ttu-id="9ac20-163">Можно ввести один или несколько идентификаторов, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="9ac20-163">You can type one or more IDs, separated by commas.</span></span>
<span data-ttu-id="9ac20-164">Чтобы найти идентификатор задания, используйте командлет Get-Job.</span><span class="sxs-lookup"><span data-stu-id="9ac20-164">To find the ID of a job, use the Get-Job cmdlet.</span></span>

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

### <span data-ttu-id="9ac20-165">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="9ac20-165">-InstanceId</span></span>
<span data-ttu-id="9ac20-166">Указывает идентификаторы экземпляров заданий, приостанавливаемых этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="9ac20-166">Specifies the instance IDs of jobs that this cmdlet suspends.</span></span>
<span data-ttu-id="9ac20-167">По умолчанию останавливаются все задания.</span><span class="sxs-lookup"><span data-stu-id="9ac20-167">The default is all jobs.</span></span>

<span data-ttu-id="9ac20-168">Идентификатор экземпляра — это GUID, который однозначно определяет задание на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9ac20-168">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span>
<span data-ttu-id="9ac20-169">Чтобы узнать идентификатор экземпляра задания, используйте командлет **Get-Job**.</span><span class="sxs-lookup"><span data-stu-id="9ac20-169">To find the instance ID of a job, use **Get-Job**.</span></span>

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

### <span data-ttu-id="9ac20-170">-Job</span><span class="sxs-lookup"><span data-stu-id="9ac20-170">-Job</span></span>
<span data-ttu-id="9ac20-171">Указывает задания рабочего процесса, которые останавливаются этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="9ac20-171">Specifies the workflow jobs that this cmdlet stops.</span></span>
<span data-ttu-id="9ac20-172">Введите переменную, которая содержит задания рабочих процессов, или команду, которая получает их.</span><span class="sxs-lookup"><span data-stu-id="9ac20-172">Enter a variable that contains the workflow jobs or a command that gets the workflow jobs.</span></span>
<span data-ttu-id="9ac20-173">Задания рабочих процессов можно также передавать в командлеты **Suspend-Job** по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="9ac20-173">You can also pipe workflow jobs to the **Suspend-Job** cmdlet.</span></span>

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

### <span data-ttu-id="9ac20-174">-Name</span><span class="sxs-lookup"><span data-stu-id="9ac20-174">-Name</span></span>
<span data-ttu-id="9ac20-175">Указывает понятные имена заданий, приостанавливаемых этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="9ac20-175">Specifies friendly names of jobs that this cmdlet suspends.</span></span>
<span data-ttu-id="9ac20-176">Введите одно или несколько имен заданий рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="9ac20-176">Enter one or more workflow job names.</span></span>
<span data-ttu-id="9ac20-177">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="9ac20-177">Wildcard characters are supported.</span></span>

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

### <span data-ttu-id="9ac20-178">-State</span><span class="sxs-lookup"><span data-stu-id="9ac20-178">-State</span></span>
<span data-ttu-id="9ac20-179">Указывает состояние задания.</span><span class="sxs-lookup"><span data-stu-id="9ac20-179">Specifies a job state.</span></span>
<span data-ttu-id="9ac20-180">Этот командлет останавливает только задания в указанном состоянии.</span><span class="sxs-lookup"><span data-stu-id="9ac20-180">This cmdlet stops only jobs in the specified state.</span></span>
<span data-ttu-id="9ac20-181">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="9ac20-181">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="9ac20-182">NotStarted</span><span class="sxs-lookup"><span data-stu-id="9ac20-182">NotStarted</span></span>
- <span data-ttu-id="9ac20-183">Запущен</span><span class="sxs-lookup"><span data-stu-id="9ac20-183">Running</span></span>
- <span data-ttu-id="9ac20-184">Завершено</span><span class="sxs-lookup"><span data-stu-id="9ac20-184">Completed</span></span>
- <span data-ttu-id="9ac20-185">Ошибка</span><span class="sxs-lookup"><span data-stu-id="9ac20-185">Failed</span></span>
- <span data-ttu-id="9ac20-186">Остановлена</span><span class="sxs-lookup"><span data-stu-id="9ac20-186">Stopped</span></span>
- <span data-ttu-id="9ac20-187">Блокировано</span><span class="sxs-lookup"><span data-stu-id="9ac20-187">Blocked</span></span>
- <span data-ttu-id="9ac20-188">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="9ac20-188">Suspended</span></span>
- <span data-ttu-id="9ac20-189">Отключено</span><span class="sxs-lookup"><span data-stu-id="9ac20-189">Disconnected</span></span>
- <span data-ttu-id="9ac20-190">Приостановка</span><span class="sxs-lookup"><span data-stu-id="9ac20-190">Suspending</span></span>
- <span data-ttu-id="9ac20-191">Остановка</span><span class="sxs-lookup"><span data-stu-id="9ac20-191">Stopping</span></span>

<span data-ttu-id="9ac20-192">**Приостановка — задание** приостанавливает только задания рабочего процесса в состоянии **выполняется** .</span><span class="sxs-lookup"><span data-stu-id="9ac20-192">**Suspend-Job** suspends only workflow jobs in the **Running** state.</span></span>

<span data-ttu-id="9ac20-193">Дополнительные сведения о состояниях заданий см. в разделе [перечисление JobState](https://msdn.microsoft.com/library/system.management.automation.jobstate) в библиотеке MSDN.</span><span class="sxs-lookup"><span data-stu-id="9ac20-193">For more information about job states, see [JobState Enumeration](https://msdn.microsoft.com/library/system.management.automation.jobstate) in the MSDN library.</span></span>

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

### <span data-ttu-id="9ac20-194">-Wait</span><span class="sxs-lookup"><span data-stu-id="9ac20-194">-Wait</span></span>
<span data-ttu-id="9ac20-195">Указывает, что этот командлет подавляет командную строку, пока задание рабочего процесса не находится в приостановленном состоянии.</span><span class="sxs-lookup"><span data-stu-id="9ac20-195">Indicates that this cmdlet suppresses the command prompt until the workflow job is in the suspended state.</span></span>
<span data-ttu-id="9ac20-196">По умолчанию **приостановка-задание** возвращается немедленно, даже если задание рабочего процесса еще не находится в приостановленном состоянии.</span><span class="sxs-lookup"><span data-stu-id="9ac20-196">By default, **Suspend-Job** returns immediately, even if the workflow job is not yet in the suspended state.</span></span>

<span data-ttu-id="9ac20-197">Параметр *Wait* эквивалентен конвейеру команды **приостановки задания** к командлету **Wait-Job** .</span><span class="sxs-lookup"><span data-stu-id="9ac20-197">The *Wait* parameter is equivalent to piping a **Suspend-Job** command to the **Wait-Job** cmdlet.</span></span>

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

### <span data-ttu-id="9ac20-198">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9ac20-198">-Confirm</span></span>
<span data-ttu-id="9ac20-199">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="9ac20-199">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="9ac20-200">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9ac20-200">-WhatIf</span></span>
<span data-ttu-id="9ac20-201">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="9ac20-201">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="9ac20-202">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="9ac20-202">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="9ac20-203">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="9ac20-203">CommonParameters</span></span>
<span data-ttu-id="9ac20-204">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9ac20-204">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9ac20-205">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9ac20-205">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9ac20-206">Входные данные</span><span class="sxs-lookup"><span data-stu-id="9ac20-206">INPUTS</span></span>

### <span data-ttu-id="9ac20-207">System. Management. Automation. job</span><span class="sxs-lookup"><span data-stu-id="9ac20-207">System.Management.Automation.Job</span></span>
<span data-ttu-id="9ac20-208">К этому командлету можно передать все типы заданий.</span><span class="sxs-lookup"><span data-stu-id="9ac20-208">You can pipe all types of jobs to this cmdlet.</span></span>
<span data-ttu-id="9ac20-209">Однако если **приостановить — задание** получает задание неподдерживаемого типа, то оно возвращает завершающую ошибку.</span><span class="sxs-lookup"><span data-stu-id="9ac20-209">However, if **Suspend-Job** gets a job of an unsupported type, it returns a terminating error.</span></span>

## <span data-ttu-id="9ac20-210">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="9ac20-210">OUTPUTS</span></span>

### <span data-ttu-id="9ac20-211">System. Management. Automation. job</span><span class="sxs-lookup"><span data-stu-id="9ac20-211">System.Management.Automation.Job</span></span>
<span data-ttu-id="9ac20-212">Этот командлет возвращает приостановленные задания.</span><span class="sxs-lookup"><span data-stu-id="9ac20-212">This cmdlet returns the jobs that it suspended.</span></span>

## <span data-ttu-id="9ac20-213">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="9ac20-213">NOTES</span></span>

* <span data-ttu-id="9ac20-214">Механизм и место сохранения приостановленного задания могут различаться в зависимости от его типа.</span><span class="sxs-lookup"><span data-stu-id="9ac20-214">The mechanism and location for saving a suspended job might vary depending on the job type.</span></span> <span data-ttu-id="9ac20-215">Например, по умолчанию приостановленные задания рабочих процессов сохраняются в хранилище неструктурированных файлов, но также могут сохраняться в базе данных.</span><span class="sxs-lookup"><span data-stu-id="9ac20-215">For example, suspended workflow jobs are saved in a flat file store by default, but can also be saved in a database.</span></span>
* <span data-ttu-id="9ac20-216">При отправке задания рабочего процесса, которое не находится в состоянии выполняется, **приостановка — задание** выводит предупреждающее сообщение.</span><span class="sxs-lookup"><span data-stu-id="9ac20-216">If you submit a workflow job that is not in the Running state, **Suspend-Job** displays a warning message.</span></span> <span data-ttu-id="9ac20-217">Чтобы отключить это предупреждение, используйте общий параметр *WarningAction* со значением SilentlyContinue.</span><span class="sxs-lookup"><span data-stu-id="9ac20-217">To suppress the warning, use the *WarningAction* common parameter with a value of SilentlyContinue.</span></span>

  <span data-ttu-id="9ac20-218">Если задание не относится к типу, поддерживающему приостановку, **приостановка-задание** Возвращает завершающую ошибку.</span><span class="sxs-lookup"><span data-stu-id="9ac20-218">If a job is not of a type that supports suspending, **Suspend-Job** returns a terminating error.</span></span>

* <span data-ttu-id="9ac20-219">Чтобы найти приостановленные задания рабочего процесса, включая те, которые были приостановлены этим командлетом, используйте параметр *State* командлета **Get-Job** , чтобы получить задания рабочего процесса в приостановленном состоянии.</span><span class="sxs-lookup"><span data-stu-id="9ac20-219">To find the workflow jobs that are suspended, including those that were suspended by this cmdlet, use the *State* parameter of the **Get-Job** cmdlet to get workflow jobs in the Suspended state.</span></span>
* <span data-ttu-id="9ac20-220">Задания некоторых типов имеют параметры или свойства, которые не позволяют среде Windows PowerShell приостанавливать их.</span><span class="sxs-lookup"><span data-stu-id="9ac20-220">Some job types have options or properties that prevent Windows PowerShell from suspending the job.</span></span> <span data-ttu-id="9ac20-221">Если попытки приостановить задание завершились ошибкой, убедитесь, что параметры задания и свойства допускают приостановку.</span><span class="sxs-lookup"><span data-stu-id="9ac20-221">If attempts to suspend the job fail, verify that the job options and properties allow for suspending.</span></span>

## <span data-ttu-id="9ac20-222">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="9ac20-222">RELATED LINKS</span></span>

[<span data-ttu-id="9ac20-223">Get-Job.</span><span class="sxs-lookup"><span data-stu-id="9ac20-223">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="9ac20-224">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="9ac20-224">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="9ac20-225">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="9ac20-225">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="9ac20-226">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="9ac20-226">Resume-Job</span></span>](Resume-Job.md)

[<span data-ttu-id="9ac20-227">Start-Job</span><span class="sxs-lookup"><span data-stu-id="9ac20-227">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="9ac20-228">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="9ac20-228">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="9ac20-229">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="9ac20-229">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="9ac20-230">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="9ac20-230">Wait-Job</span></span>](Wait-Job.md)
