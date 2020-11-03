---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/resume-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-Job
ms.openlocfilehash: 85cbfad2a4866bf18e69fb99afb8698e233c4c80
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227053"
---
# <span data-ttu-id="99072-103">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="99072-103">Resume-Job</span></span>

## <span data-ttu-id="99072-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="99072-104">SYNOPSIS</span></span>
<span data-ttu-id="99072-105">Перезапускает приостановленное задание.</span><span class="sxs-lookup"><span data-stu-id="99072-105">Restarts a suspended job.</span></span>

## <span data-ttu-id="99072-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="99072-106">SYNTAX</span></span>

### <span data-ttu-id="99072-107">Сессионидпараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="99072-107">SessionIdParameterSet (Default)</span></span>

```
Resume-Job [-Wait] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="99072-108">жобпараметерсет</span><span class="sxs-lookup"><span data-stu-id="99072-108">JobParameterSet</span></span>

```
Resume-Job [-Job] <Job[]> [-Wait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="99072-109">намепараметерсет</span><span class="sxs-lookup"><span data-stu-id="99072-109">NameParameterSet</span></span>

```
Resume-Job [-Wait] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="99072-110">инстанцеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="99072-110">InstanceIdParameterSet</span></span>

```
Resume-Job [-Wait] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="99072-111">статепараметерсет</span><span class="sxs-lookup"><span data-stu-id="99072-111">StateParameterSet</span></span>

```
Resume-Job [-Wait] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="99072-112">филтерпараметерсет</span><span class="sxs-lookup"><span data-stu-id="99072-112">FilterParameterSet</span></span>

```
Resume-Job [-Wait] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="99072-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="99072-113">DESCRIPTION</span></span>
<span data-ttu-id="99072-114">Командлет **Resume-Job** возобновляет приостановленное задание рабочего процесса, например с помощью командлета Suspend-Job или действия About_Suspend-Workflow.</span><span class="sxs-lookup"><span data-stu-id="99072-114">The **Resume-Job** cmdlet resumes a workflow job that was suspended, such as by using the Suspend-Job cmdlet or the about_Suspend-Workflow activity.</span></span>
<span data-ttu-id="99072-115">При возобновлении задания рабочего процесса обработчик заданий перестраивает состояние, метаданные и выходные данные из сохраненных ресурсов, таких как контрольные точки.</span><span class="sxs-lookup"><span data-stu-id="99072-115">When a workflow job resumes, the job engine reconstructs the state, metadata, and output from saved resources, such as checkpoints.</span></span>
<span data-ttu-id="99072-116">Задание перезапускается без потери состояния или данных.</span><span class="sxs-lookup"><span data-stu-id="99072-116">The job is restarted without any loss of state or data.</span></span>
<span data-ttu-id="99072-117">Состояние задания меняется с **Suspended** на **Running**.</span><span class="sxs-lookup"><span data-stu-id="99072-117">The job state is changed from **Suspended** to **Running**.</span></span>

<span data-ttu-id="99072-118">Используйте параметры **возобновления задания** , чтобы выбрать задания по имени, идентификатору, идентификатору экземпляра или передать по каналу объект задания, например, возвращаемый командлетом Get-Job, для **возобновления** работы.</span><span class="sxs-lookup"><span data-stu-id="99072-118">Use the parameters of **Resume-Job** to select jobs by name, ID, instance ID or pipe a job object, such as one returned by the Get-Job cmdlet, to **Resume-Job**.</span></span>
<span data-ttu-id="99072-119">Для выбора задания, которое нужно возобновить, можно также использовать фильтр свойств.</span><span class="sxs-lookup"><span data-stu-id="99072-119">You can also use a property filter to select a job to be resumed.</span></span>

<span data-ttu-id="99072-120">По умолчанию командлет **Resume-Job** возвращает результат немедленно, даже если возобновлены еще не все задания.</span><span class="sxs-lookup"><span data-stu-id="99072-120">By default, **Resume-Job** returns immediately, even though all jobs might not yet be resumed.</span></span>
<span data-ttu-id="99072-121">Чтобы заблокировать вывод командной строки до тех пор, пока все указанные задания не будут возобновлены, используйте параметр *Wait*.</span><span class="sxs-lookup"><span data-stu-id="99072-121">To suppress the command prompt until all specified jobs are resumed, use the *Wait* parameter.</span></span>

<span data-ttu-id="99072-122">Командлет **Resume-Job** применим только к заданиям настраиваемых типов, например заданиям рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="99072-122">The **Resume-Job** cmdlet works only on custom job types, such as workflow jobs.</span></span>
<span data-ttu-id="99072-123">Он не работает для стандартных фоновых заданий, например для тех, которые запускаются с помощью командлета Start-Job.</span><span class="sxs-lookup"><span data-stu-id="99072-123">It does not work on standard background jobs, such as those that are started by using the Start-Job cmdlet.</span></span>
<span data-ttu-id="99072-124">При передаче задания неподдерживаемого типа командлет **Resume-Job** создает неустранимую ошибку и его выполнение останавливается.</span><span class="sxs-lookup"><span data-stu-id="99072-124">If you submit a job of an unsupported type, **Resume-Job** generates a terminating error and stops running.</span></span>

<span data-ttu-id="99072-125">Определить задание рабочего процесса можно по значению **PSWorkflowJob** свойства **PSJobTypeName** задания.</span><span class="sxs-lookup"><span data-stu-id="99072-125">To identify a workflow job, look for a value of **PSWorkflowJob** in the **PSJobTypeName** property of the job.</span></span>
<span data-ttu-id="99072-126">Чтобы определить, поддерживает ли конкретный тип настраиваемого задания командлет **Resume-Job** , см. разделы справки для типа настраиваемого задания.</span><span class="sxs-lookup"><span data-stu-id="99072-126">To determine whether a particular custom job type supports the **Resume-Job** cmdlet, see the help topics for the custom job type.</span></span>

<span data-ttu-id="99072-127">Перед использованием командлета задания для настраиваемого типа задания Импортируйте модуль, поддерживающий тип настраиваемого задания, с помощью командлета Import-Module или путем получения или использования командлета в модуле.</span><span class="sxs-lookup"><span data-stu-id="99072-127">Before using a Job cmdlet on a custom job type, import the module that supports the custom job type, either by using the Import-Module cmdlet or getting or using a cmdlet in the module.</span></span>

<span data-ttu-id="99072-128">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="99072-128">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="99072-129">Примеры</span><span class="sxs-lookup"><span data-stu-id="99072-129">EXAMPLES</span></span>

### <span data-ttu-id="99072-130">Пример 1. возобновление задания по ИДЕНТИФИКАТОРу</span><span class="sxs-lookup"><span data-stu-id="99072-130">Example 1: Resume a job by ID</span></span>

```
The first command uses the **Get-Job** cmdlet to get the job. The output shows that the job is a suspended workflow job.
PS C:\> Get-Job EventJob
Id     Name            PSJobTypeName   State         HasMoreData     Location   Command
--     ----            -------------   -----         -----------     --------   -------
4      EventJob        PSWorkflowJob   Suspended     True            Server01   \\Script\Share\Event.ps1

The second command uses the *Id* parameter of the **Resume-Job** cmdlet to resume the job with an *Id* value of 4.
PS C:\> Resume-Job -Id 4
```

<span data-ttu-id="99072-131">Команды в этом примере проверяют, является ли задание приостановленным заданием рабочего процесса, а затем возобновляют его.</span><span class="sxs-lookup"><span data-stu-id="99072-131">The commands in this example verify that the job is a suspended workflow job and then resume the job.</span></span>

### <span data-ttu-id="99072-132">Пример 2. возобновление задания по имени</span><span class="sxs-lookup"><span data-stu-id="99072-132">Example 2: Resume a job by name</span></span>

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest*
```

<span data-ttu-id="99072-133">В этой команде используется параметр *Name* для возобновления нескольких заданий рабочих процессов на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="99072-133">This command uses the *Name* parameter to resume several workflow jobs on the local computer.</span></span>

### <span data-ttu-id="99072-134">Пример 3. Использование значений настраиваемых свойств</span><span class="sxs-lookup"><span data-stu-id="99072-134">Example 3: Use custom property values</span></span>

```
PS C:\> Resume-Job -Filter @{CustomID="T091291"} -State Suspended
```

<span data-ttu-id="99072-135">В этой команде с помощью значения настраиваемого свойства определяется задание рабочего процесса, которое нужно возобновить.</span><span class="sxs-lookup"><span data-stu-id="99072-135">This command uses the value of a custom property to identify the workflow job to resume.</span></span>
<span data-ttu-id="99072-136">В ней используется параметр *Filter* для указания задания рабочего процесса по значению свойства **CustomID**.</span><span class="sxs-lookup"><span data-stu-id="99072-136">It uses the *Filter* parameter to identify the workflow job by its **CustomID** property.</span></span>
<span data-ttu-id="99072-137">В ней также используется параметр *State* для проверки того, приостановлено ли задание рабочего процесса, перед попыткой его возобновления.</span><span class="sxs-lookup"><span data-stu-id="99072-137">It also uses the *State* parameter to verify that the workflow job is suspended, before it tries to resume it.</span></span>

### <span data-ttu-id="99072-138">Пример 4. возобновление всех приостановленных заданий на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="99072-138">Example 4: Resume all suspended jobs on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Srv01 -ScriptBlock {Get-Job -State Suspended | Resume-Job}
```

<span data-ttu-id="99072-139">Эта команда возобновляет все приостановленные задания на удаленном компьютере Srv01.</span><span class="sxs-lookup"><span data-stu-id="99072-139">This command resumes all suspended jobs on the Srv01 remote computer.</span></span>

<span data-ttu-id="99072-140">Команда использует командлет Invoke-Command для выполнения команды на компьютере SRV01.</span><span class="sxs-lookup"><span data-stu-id="99072-140">The command uses the Invoke-Command cmdlet to run a command on the Srv01 computer.</span></span>
<span data-ttu-id="99072-141">Удаленная команда использует параметр *State* командлета **Get-Job** , чтобы получить все приостановленные задания на компьютере.</span><span class="sxs-lookup"><span data-stu-id="99072-141">The remote command uses the *State* parameter of the **Get-Job** cmdlet to get all suspended jobs on the computer.</span></span>
<span data-ttu-id="99072-142">С помощью оператора конвейера (|) приостановленные задания передаются в командлет **Resume-Job** , который возобновляет их.</span><span class="sxs-lookup"><span data-stu-id="99072-142">A pipeline operator (|) sends the suspended jobs to the **Resume-Job** cmdlet, which resumes them.</span></span>

### <span data-ttu-id="99072-143">Пример 5. Ожидание возобновления заданий</span><span class="sxs-lookup"><span data-stu-id="99072-143">Example 5: Wait for jobs to resume</span></span>

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest* -Wait
```

<span data-ttu-id="99072-144">Эта команда использует параметр *Wait* для прямого **возобновления задания** , чтобы оно возвращалось только после возобновления всех указанных заданий.</span><span class="sxs-lookup"><span data-stu-id="99072-144">This command uses the *Wait* parameter to direct **Resume-Job** to return only after all specified jobs are resumed.</span></span>
<span data-ttu-id="99072-145">Параметр *Wait* особенно полезен в сценариях, в которых предполагается, что задания должны быть возобновлены, прежде чем выполнение сценария будет продолжено.</span><span class="sxs-lookup"><span data-stu-id="99072-145">The *Wait* parameter is especially useful in scripts that assume that jobs are resumed before the script continues.</span></span>

### <span data-ttu-id="99072-146">Пример 6. Возобновление рабочего процесса, который приостанавливает работу</span><span class="sxs-lookup"><span data-stu-id="99072-146">Example 6: Resume a workflow that suspends itself</span></span>

```
This code sample shows the **Suspend-Workflow** activity in a workflow.
#SampleWorkflow
Workflow Test-Suspend
{
    $a = Get-Date
    Suspend-Workflow
    (Get-Date)- $a
}

The following command runs the Test-Suspend workflow on the Server01 computer.When you run the workflow, the workflow runs the Get-Date activity and stores the result in the $a variable. Then it runs the Suspend-Workflow activity. In response, it takes a checkpoint, suspends the workflow, and returns a workflow job object.  Suspend-Workflow returns a workflow job object even if the workflow is not explicitly run as a job.
PS C:\> Test-Suspend -PSComputerName Server01
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
8      Job8            PSWorkflowJob   Suspended     True            Server01             Test-Suspend

The following command resumes the Test-Suspend workflow in Job8. It uses the *Wait* parameter to hold the command prompt until the job is resumed.
PS C:\> Resume-Job -Name "Job8" -Wait
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command

--     ----            -------------   -----         -----------     --------             -------

8      Job8            PSWorkflowJob   Running       True            Server01             Test-Suspend

This command uses the **Receive-Job** cmdlet to get the results of the Test-Suspend workflow. The final command in the workflow returns a **TimeSpan** object that represents the elapsed time between the current date and time and the date and time that was saved in the $a variable before the workflow was suspended.
PS C:\> Receive-Job -Name Job8
        Days              : 0
        Hours             : 0
        Minutes           : 0
        Seconds           : 19
        Milliseconds      : 823
        Ticks             : 198230041
        TotalDays         : 0.000229432917824074
        TotalHours        : 0.00550639002777778
        TotalMinutes      : 0.330383401666667
        TotalSeconds      : 19.8230041
        TotalMilliseconds : 19823.0041
        PSComputerName    : Server01
```

<span data-ttu-id="99072-147">Командлет **Resume-Job** позволяет возобновить задание рабочего процесса, которое было приостановлено с помощью действия **приостановки рабочего процесса** .</span><span class="sxs-lookup"><span data-stu-id="99072-147">The **Resume-Job** cmdlet lets you resume a workflow job that was suspend by using the **Suspend-Workflow** activity.</span></span>
<span data-ttu-id="99072-148">Это действие приостанавливает рабочий процесс из самого процесса.</span><span class="sxs-lookup"><span data-stu-id="99072-148">This activity suspends a workflow from within a workflow.</span></span>
<span data-ttu-id="99072-149">Оно допустимо только в рабочих процессах.</span><span class="sxs-lookup"><span data-stu-id="99072-149">It is valid only in workflows.</span></span>

<span data-ttu-id="99072-150">Сведения о действии Suspend-Workflow см. в разделе about_Suspend-Workflow.</span><span class="sxs-lookup"><span data-stu-id="99072-150">For information about the Suspend-Workflow, see about_Suspend-Workflow.</span></span>

## <span data-ttu-id="99072-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="99072-151">PARAMETERS</span></span>

### <span data-ttu-id="99072-152">-Filter</span><span class="sxs-lookup"><span data-stu-id="99072-152">-Filter</span></span>
<span data-ttu-id="99072-153">Указывает хэш-таблицу условий.</span><span class="sxs-lookup"><span data-stu-id="99072-153">Specifies a hash table of conditions.</span></span>
<span data-ttu-id="99072-154">Этот командлет возобновляет задания, которые соответствуют всем условиям в хэш-таблице.</span><span class="sxs-lookup"><span data-stu-id="99072-154">This cmdlet resumes jobs that satisfy all of the conditions in the hash table.</span></span>
<span data-ttu-id="99072-155">Введите хэш-таблицу, где ключи являются свойствами заданий, а значения — значениями этих свойств.</span><span class="sxs-lookup"><span data-stu-id="99072-155">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

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

### <span data-ttu-id="99072-156">-Id</span><span class="sxs-lookup"><span data-stu-id="99072-156">-Id</span></span>
<span data-ttu-id="99072-157">Указывает массив идентификаторов для заданий, которые возобновляет этот командлет.</span><span class="sxs-lookup"><span data-stu-id="99072-157">Specifies an array of IDs for jobs that this cmdlet resumes.</span></span>

<span data-ttu-id="99072-158">Идентификатор — это целое число, которое однозначно определяет задание в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="99072-158">The ID is an integer that uniquely identifies the job in the current session.</span></span>
<span data-ttu-id="99072-159">Проще запомнить и ввести, чем идентификатор экземпляра, но он уникален только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="99072-159">It is easier to remember and to type than the instance ID, but it is unique only in the current session.</span></span>
<span data-ttu-id="99072-160">Можно ввести один или несколько идентификаторов, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="99072-160">You can type one or more IDs, separated by commas.</span></span>
<span data-ttu-id="99072-161">Чтобы найти идентификатор задания, выполните команду **Get-Job**.</span><span class="sxs-lookup"><span data-stu-id="99072-161">To find the ID of a job, run **Get-Job**.</span></span>

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

### <span data-ttu-id="99072-162">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="99072-162">-InstanceId</span></span>
<span data-ttu-id="99072-163">Указывает массив идентификаторов экземпляров заданий, которые возобновляет этот командлет.</span><span class="sxs-lookup"><span data-stu-id="99072-163">Specifies an array of instance IDs of jobs that this cmdlet resumes.</span></span>
<span data-ttu-id="99072-164">По умолчанию останавливаются все задания.</span><span class="sxs-lookup"><span data-stu-id="99072-164">The default is all jobs.</span></span>

<span data-ttu-id="99072-165">Идентификатор экземпляра — это GUID, который однозначно определяет задание на компьютере.</span><span class="sxs-lookup"><span data-stu-id="99072-165">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span>
<span data-ttu-id="99072-166">Чтобы найти идентификатор экземпляра задания, выполните команду **Get-Job**.</span><span class="sxs-lookup"><span data-stu-id="99072-166">To find the instance ID of a job, run **Get-Job**.</span></span>

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

### <span data-ttu-id="99072-167">-Job</span><span class="sxs-lookup"><span data-stu-id="99072-167">-Job</span></span>
<span data-ttu-id="99072-168">Указывает задания, которые нужно возобновить.</span><span class="sxs-lookup"><span data-stu-id="99072-168">Specifies the jobs to be resumed.</span></span>
<span data-ttu-id="99072-169">Введите переменную, содержащую задания, либо команду, которая их возвращают.</span><span class="sxs-lookup"><span data-stu-id="99072-169">Enter a variable that contains the jobs or a command that gets the jobs.</span></span>
<span data-ttu-id="99072-170">Задания можно также передавать в командлет **Resume-Job** по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="99072-170">You can also pipe jobs to the **Resume-Job** cmdlet.</span></span>

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

### <span data-ttu-id="99072-171">-Name</span><span class="sxs-lookup"><span data-stu-id="99072-171">-Name</span></span>
<span data-ttu-id="99072-172">Указывает массив понятных имен заданий, которые возобновляет этот командлет.</span><span class="sxs-lookup"><span data-stu-id="99072-172">Specifies an array of friendly names of jobs that this cmdlet resumes.</span></span>
<span data-ttu-id="99072-173">Введите одно или несколько имен заданий.</span><span class="sxs-lookup"><span data-stu-id="99072-173">Enter one or more job names.</span></span>
<span data-ttu-id="99072-174">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="99072-174">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="99072-175">-State</span><span class="sxs-lookup"><span data-stu-id="99072-175">-State</span></span>
<span data-ttu-id="99072-176">Указывает состояние заданий для возобновления.</span><span class="sxs-lookup"><span data-stu-id="99072-176">Specifies the state of jobs to resume.</span></span>
<span data-ttu-id="99072-177">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="99072-177">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="99072-178">NotStarted</span><span class="sxs-lookup"><span data-stu-id="99072-178">NotStarted</span></span>
- <span data-ttu-id="99072-179">Запущен</span><span class="sxs-lookup"><span data-stu-id="99072-179">Running</span></span>
- <span data-ttu-id="99072-180">Завершено</span><span class="sxs-lookup"><span data-stu-id="99072-180">Completed</span></span>
- <span data-ttu-id="99072-181">Ошибка</span><span class="sxs-lookup"><span data-stu-id="99072-181">Failed</span></span>
- <span data-ttu-id="99072-182">Остановлена</span><span class="sxs-lookup"><span data-stu-id="99072-182">Stopped</span></span>
- <span data-ttu-id="99072-183">Блокировано</span><span class="sxs-lookup"><span data-stu-id="99072-183">Blocked</span></span>
- <span data-ttu-id="99072-184">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="99072-184">Suspended</span></span>
- <span data-ttu-id="99072-185">Отключено</span><span class="sxs-lookup"><span data-stu-id="99072-185">Disconnected</span></span>
- <span data-ttu-id="99072-186">Приостановка</span><span class="sxs-lookup"><span data-stu-id="99072-186">Suspending</span></span>
- <span data-ttu-id="99072-187">Остановка</span><span class="sxs-lookup"><span data-stu-id="99072-187">Stopping</span></span>

<span data-ttu-id="99072-188">Этот командлет возобновляет только задания в **приостановленном** состоянии.</span><span class="sxs-lookup"><span data-stu-id="99072-188">This cmdlet resumes only jobs in the **Suspended** state.</span></span>

<span data-ttu-id="99072-189">Дополнительные сведения о состояниях заданий см. в разделе [перечисление JobState](https://msdn.microsoft.com/library/system.management.automation.jobstate) в библиотеке MSDN.</span><span class="sxs-lookup"><span data-stu-id="99072-189">For more information about job states, see [JobState Enumeration](https://msdn.microsoft.com/library/system.management.automation.jobstate) in the MSDN library.</span></span>

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

### <span data-ttu-id="99072-190">-Wait</span><span class="sxs-lookup"><span data-stu-id="99072-190">-Wait</span></span>
<span data-ttu-id="99072-191">Указывает, что этот командлет подавляет командную строку до тех пор, пока не будут перезапущены все результаты задания.</span><span class="sxs-lookup"><span data-stu-id="99072-191">Indicates that this cmdlet suppresses the command prompt until all job results are restarted.</span></span>
<span data-ttu-id="99072-192">По умолчанию этот командлет немедленно возвращает доступные результаты.</span><span class="sxs-lookup"><span data-stu-id="99072-192">By default, this cmdlet immediately returns the available results.</span></span>

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

### <span data-ttu-id="99072-193">-Confirm</span><span class="sxs-lookup"><span data-stu-id="99072-193">-Confirm</span></span>
<span data-ttu-id="99072-194">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="99072-194">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="99072-195">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="99072-195">-WhatIf</span></span>
<span data-ttu-id="99072-196">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="99072-196">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="99072-197">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="99072-197">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="99072-198">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="99072-198">CommonParameters</span></span>
<span data-ttu-id="99072-199">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="99072-199">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="99072-200">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="99072-200">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="99072-201">Входные данные</span><span class="sxs-lookup"><span data-stu-id="99072-201">INPUTS</span></span>

### <span data-ttu-id="99072-202">System. Management. Automation. job</span><span class="sxs-lookup"><span data-stu-id="99072-202">System.Management.Automation.Job</span></span>
<span data-ttu-id="99072-203">К этому командлету можно передать все типы заданий.</span><span class="sxs-lookup"><span data-stu-id="99072-203">You can pipe all types of jobs to this cmdlet.</span></span>
<span data-ttu-id="99072-204">Если **Resume-Job** получает задание неподдерживаемого типа, то оно возвращает завершающую ошибку.</span><span class="sxs-lookup"><span data-stu-id="99072-204">If **Resume-Job** gets a job of an unsupported type, it returns a terminating error.</span></span>

## <span data-ttu-id="99072-205">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="99072-205">OUTPUTS</span></span>

### <span data-ttu-id="99072-206">Нет, System. Management. Automation. job</span><span class="sxs-lookup"><span data-stu-id="99072-206">None, System.Management.Automation.Job</span></span>
<span data-ttu-id="99072-207">Этот командлет возвращает задания, которые он пытается возобновить, если используется параметр *PassThru* .</span><span class="sxs-lookup"><span data-stu-id="99072-207">This cmdlet returns the jobs that it tries to resume, if you use the *PassThru* parameter.</span></span>
<span data-ttu-id="99072-208">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="99072-208">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="99072-209">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="99072-209">NOTES</span></span>

* <span data-ttu-id="99072-210">**Resume — задание** может возобновлять только приостановленные задания.</span><span class="sxs-lookup"><span data-stu-id="99072-210">**Resume-Job** can only resume jobs that are suspended.</span></span> <span data-ttu-id="99072-211">При передаче задания, имеющего другое состояние, командлет **Resume-Job** выполняет операцию возобновления задания, но выводит предупреждение о том, что задание не удалось возобновить.</span><span class="sxs-lookup"><span data-stu-id="99072-211">If you submit a job in a different state, **Resume-Job** runs the resume operation on the job, but generates a warning to notify you that the job could not be resumed.</span></span> <span data-ttu-id="99072-212">Чтобы отключить это предупреждение, используйте общий параметр *WarningAction* со значением SilentlyContinue.</span><span class="sxs-lookup"><span data-stu-id="99072-212">To suppress the warning, use the *WarningAction* common parameter with a value of SilentlyContinue.</span></span>
* <span data-ttu-id="99072-213">Если задание не относится к типу, который поддерживает возобновление, например задание рабочего процесса ( **псворкфловжоб** ), **возобновление** работы возвращает неустранимую ошибку.</span><span class="sxs-lookup"><span data-stu-id="99072-213">If a job is not of a type that supports resuming, such as a workflow job ( **PSWorkflowJob** ), **Resume-Job** returns a terminating error.</span></span>
* <span data-ttu-id="99072-214">Механизм и место сохранения приостановленного задания могут различаться в зависимости от его типа.</span><span class="sxs-lookup"><span data-stu-id="99072-214">The mechanism and location for saving a suspended job might vary depending on the job type.</span></span> <span data-ttu-id="99072-215">Например, по умолчанию приостановленные задания рабочих процессов сохраняются в хранилище неструктурированных файлов, но также могут сохраняться в базе данных SQL.</span><span class="sxs-lookup"><span data-stu-id="99072-215">For example, suspended workflow jobs are saved in a flat file store by default, but can also be saved in a SQL database.</span></span>
* <span data-ttu-id="99072-216">При возобновлении задания его состояние меняется с **Suspended** на **Running**.</span><span class="sxs-lookup"><span data-stu-id="99072-216">When you resume a job, the job state changes from **Suspended** to **Running**.</span></span> <span data-ttu-id="99072-217">Чтобы найти выполняемые задания, включая те, которые были возобновлены с помощью этого командлета, используйте параметр *State* командлета **Get-Job** , чтобы получить задания в состоянии **выполнения** .</span><span class="sxs-lookup"><span data-stu-id="99072-217">To find the jobs that are running, including those that were resumed by this cmdlet, use the *State* parameter of the **Get-Job** cmdlet to get jobs in the **Running** state.</span></span>
* <span data-ttu-id="99072-218">Задания некоторых типов имеют параметры или свойства, которые не позволяют среде Windows PowerShell приостанавливать их.</span><span class="sxs-lookup"><span data-stu-id="99072-218">Some job types have options or properties that prevent Windows PowerShell from suspending the job.</span></span> <span data-ttu-id="99072-219">Если попытки приостановить задание завершились ошибкой, убедитесь, что параметры задания и свойства допускают приостановку.</span><span class="sxs-lookup"><span data-stu-id="99072-219">If attempts to suspend the job fail, verify that the job options and properties allow for suspending.</span></span>

## <span data-ttu-id="99072-220">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="99072-220">RELATED LINKS</span></span>

[<span data-ttu-id="99072-221">Get-Job.</span><span class="sxs-lookup"><span data-stu-id="99072-221">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="99072-222">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="99072-222">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="99072-223">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="99072-223">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="99072-224">Start-Job</span><span class="sxs-lookup"><span data-stu-id="99072-224">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="99072-225">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="99072-225">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="99072-226">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="99072-226">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="99072-227">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="99072-227">Wait-Job</span></span>](Wait-Job.md)
