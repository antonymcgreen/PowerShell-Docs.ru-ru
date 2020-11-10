---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/resume-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-Job
ms.openlocfilehash: 6d08d9053e100cb53d37a6e4931d118f90c35a6a
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388541"
---
# <span data-ttu-id="a91ef-103">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="a91ef-103">Resume-Job</span></span>

## <span data-ttu-id="a91ef-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a91ef-104">SYNOPSIS</span></span>
<span data-ttu-id="a91ef-105">Перезапускает приостановленное задание.</span><span class="sxs-lookup"><span data-stu-id="a91ef-105">Restarts a suspended job.</span></span>

## <span data-ttu-id="a91ef-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a91ef-106">SYNTAX</span></span>

### <span data-ttu-id="a91ef-107">Сессионидпараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="a91ef-107">SessionIdParameterSet (Default)</span></span>

```
Resume-Job [-Wait] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a91ef-108">жобпараметерсет</span><span class="sxs-lookup"><span data-stu-id="a91ef-108">JobParameterSet</span></span>

```
Resume-Job [-Job] <Job[]> [-Wait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a91ef-109">намепараметерсет</span><span class="sxs-lookup"><span data-stu-id="a91ef-109">NameParameterSet</span></span>

```
Resume-Job [-Wait] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a91ef-110">инстанцеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="a91ef-110">InstanceIdParameterSet</span></span>

```
Resume-Job [-Wait] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a91ef-111">статепараметерсет</span><span class="sxs-lookup"><span data-stu-id="a91ef-111">StateParameterSet</span></span>

```
Resume-Job [-Wait] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a91ef-112">филтерпараметерсет</span><span class="sxs-lookup"><span data-stu-id="a91ef-112">FilterParameterSet</span></span>

```
Resume-Job [-Wait] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a91ef-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a91ef-113">DESCRIPTION</span></span>

<span data-ttu-id="a91ef-114">`Resume-Job`Командлет возобновляет приостановленное задание рабочего процесса, например с помощью `Suspend-Job` командлета или действия [about_Suspend-Workflow](../PSWorkflow/about/about_Suspend-Workflow.md) .</span><span class="sxs-lookup"><span data-stu-id="a91ef-114">The `Resume-Job` cmdlet resumes a workflow job that was suspended, such as by using the `Suspend-Job` cmdlet or the [about_Suspend-Workflow](../PSWorkflow/about/about_Suspend-Workflow.md) activity.</span></span> <span data-ttu-id="a91ef-115">При возобновлении задания рабочего процесса обработчик заданий перестраивает состояние, метаданные и выходные данные из сохраненных ресурсов, таких как контрольные точки.</span><span class="sxs-lookup"><span data-stu-id="a91ef-115">When a workflow job resumes, the job engine reconstructs the state, metadata, and output from saved resources, such as checkpoints.</span></span> <span data-ttu-id="a91ef-116">Задание перезапускается без потери состояния или данных.</span><span class="sxs-lookup"><span data-stu-id="a91ef-116">The job is restarted without any loss of state or data.</span></span>
<span data-ttu-id="a91ef-117">Состояние задания меняется с **Suspended** на **Running**.</span><span class="sxs-lookup"><span data-stu-id="a91ef-117">The job state is changed from **Suspended** to **Running**.</span></span>

<span data-ttu-id="a91ef-118">Используйте параметры, `Resume-Job` чтобы выбрать задания по имени, идентификатору, идентификатору экземпляра или передать по каналу объект задания, например, возвращаемый `Get-Job` командлетом, в `Resume-Job` .</span><span class="sxs-lookup"><span data-stu-id="a91ef-118">Use the parameters of `Resume-Job` to select jobs by name, ID, instance ID or pipe a job object, such as one returned by the `Get-Job` cmdlet, to `Resume-Job`.</span></span> <span data-ttu-id="a91ef-119">Для выбора задания, которое нужно возобновить, можно также использовать фильтр свойств.</span><span class="sxs-lookup"><span data-stu-id="a91ef-119">You can also use a property filter to select a job to be resumed.</span></span>

<span data-ttu-id="a91ef-120">По умолчанию `Resume-Job` возвращает значение немедленно, несмотря на то, что все задания могут быть еще не возобновлены.</span><span class="sxs-lookup"><span data-stu-id="a91ef-120">By default, `Resume-Job` returns immediately, even though all jobs might not yet be resumed.</span></span> <span data-ttu-id="a91ef-121">Чтобы заблокировать вывод командной строки до тех пор, пока все указанные задания не будут возобновлены, используйте параметр **Wait**.</span><span class="sxs-lookup"><span data-stu-id="a91ef-121">To suppress the command prompt until all specified jobs are resumed, use the **Wait** parameter.</span></span>

<span data-ttu-id="a91ef-122">`Resume-Job`Командлет работает только с пользовательскими типами заданий, такими как задания рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="a91ef-122">The `Resume-Job` cmdlet works only on custom job types, such as workflow jobs.</span></span> <span data-ttu-id="a91ef-123">Он не работает для стандартных фоновых заданий, например для тех, которые запускаются с помощью `Start-Job` командлета.</span><span class="sxs-lookup"><span data-stu-id="a91ef-123">It does not work on standard background jobs, such as those that are started by using the `Start-Job` cmdlet.</span></span> <span data-ttu-id="a91ef-124">При отправке задания неподдерживаемого типа `Resume-Job` создает завершающую ошибку и прекращает выполнение.</span><span class="sxs-lookup"><span data-stu-id="a91ef-124">If you submit a job of an unsupported type, `Resume-Job` generates a terminating error and stops running.</span></span>

<span data-ttu-id="a91ef-125">Определить задание рабочего процесса можно по значению **PSWorkflowJob** свойства **PSJobTypeName** задания.</span><span class="sxs-lookup"><span data-stu-id="a91ef-125">To identify a workflow job, look for a value of **PSWorkflowJob** in the **PSJobTypeName** property of the job.</span></span> <span data-ttu-id="a91ef-126">Чтобы определить, поддерживает ли конкретный тип настраиваемого задания `Resume-Job` командлет, см. разделы справки для типа настраиваемого задания.</span><span class="sxs-lookup"><span data-stu-id="a91ef-126">To determine whether a particular custom job type supports the `Resume-Job` cmdlet, see the help topics for the custom job type.</span></span>

<span data-ttu-id="a91ef-127">Перед использованием командлета задания для настраиваемого типа задания Импортируйте модуль, поддерживающий тип настраиваемого задания, с помощью `Import-Module` командлета или путем получения или использования командлета в модуле.</span><span class="sxs-lookup"><span data-stu-id="a91ef-127">Before using a Job cmdlet on a custom job type, import the module that supports the custom job type, either by using the `Import-Module` cmdlet or getting or using a cmdlet in the module.</span></span>

<span data-ttu-id="a91ef-128">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a91ef-128">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="a91ef-129">Примеры</span><span class="sxs-lookup"><span data-stu-id="a91ef-129">EXAMPLES</span></span>

### <span data-ttu-id="a91ef-130">Пример 1. возобновление задания по ИДЕНТИФИКАТОРу</span><span class="sxs-lookup"><span data-stu-id="a91ef-130">Example 1: Resume a job by ID</span></span>

<span data-ttu-id="a91ef-131">Команды в этом примере проверяют, является ли задание приостановленным заданием рабочего процесса, а затем возобновляют его.</span><span class="sxs-lookup"><span data-stu-id="a91ef-131">The commands in this example verify that the job is a suspended workflow job and then resume the job.</span></span> <span data-ttu-id="a91ef-132">Первая команда использует `Get-Job` командлет для получения задания.</span><span class="sxs-lookup"><span data-stu-id="a91ef-132">The first command uses the `Get-Job` cmdlet to get the job.</span></span> <span data-ttu-id="a91ef-133">В выходных данных видно, что задания является приостановленным заданием рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="a91ef-133">The output shows that the job is a suspended workflow job.</span></span> <span data-ttu-id="a91ef-134">Вторая команда использует параметр **ID** `Resume-Job` командлета, чтобы возобновить задание с **идентификатором** 4.</span><span class="sxs-lookup"><span data-stu-id="a91ef-134">The second command uses the **Id** parameter of the `Resume-Job` cmdlet to resume the job with an **Id** value of 4.</span></span>

```
PS C:\> Get-Job EventJob
Id     Name            PSJobTypeName   State         HasMoreData     Location   Command
--     ----            -------------   -----         -----------     --------   -------
4      EventJob        PSWorkflowJob   Suspended     True            Server01   \\Script\Share\Event.ps1

PS C:\> Resume-Job -Id 4
```

### <span data-ttu-id="a91ef-135">Пример 2. возобновление задания по имени</span><span class="sxs-lookup"><span data-stu-id="a91ef-135">Example 2: Resume a job by name</span></span>

<span data-ttu-id="a91ef-136">В этой команде используется параметр **Name** для возобновления нескольких заданий рабочих процессов на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a91ef-136">This command uses the **Name** parameter to resume several workflow jobs on the local computer.</span></span>

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest*
```

### <span data-ttu-id="a91ef-137">Пример 3. Использование значений настраиваемых свойств</span><span class="sxs-lookup"><span data-stu-id="a91ef-137">Example 3: Use custom property values</span></span>

<span data-ttu-id="a91ef-138">В этой команде с помощью значения настраиваемого свойства определяется задание рабочего процесса, которое нужно возобновить.</span><span class="sxs-lookup"><span data-stu-id="a91ef-138">This command uses the value of a custom property to identify the workflow job to resume.</span></span> <span data-ttu-id="a91ef-139">В ней используется параметр **Filter** для указания задания рабочего процесса по значению свойства **CustomID**.</span><span class="sxs-lookup"><span data-stu-id="a91ef-139">It uses the **Filter** parameter to identify the workflow job by its **CustomID** property.</span></span> <span data-ttu-id="a91ef-140">В ней также используется параметр **State** для проверки того, приостановлено ли задание рабочего процесса, перед попыткой его возобновления.</span><span class="sxs-lookup"><span data-stu-id="a91ef-140">It also uses the **State** parameter to verify that the workflow job is suspended, before it tries to resume it.</span></span>

```
PS C:\> Resume-Job -Filter @{CustomID="T091291"} -State Suspended
```

### <span data-ttu-id="a91ef-141">Пример 4. возобновление всех приостановленных заданий на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="a91ef-141">Example 4: Resume all suspended jobs on a remote computer</span></span>

<span data-ttu-id="a91ef-142">Эта команда возобновляет все приостановленные задания на удаленном компьютере Srv01.</span><span class="sxs-lookup"><span data-stu-id="a91ef-142">This command resumes all suspended jobs on the Srv01 remote computer.</span></span>

```
PS C:\> Invoke-Command -ComputerName Srv01 -ScriptBlock {Get-Job -State Suspended | Resume-Job}
```

<span data-ttu-id="a91ef-143">Команда использует `Invoke-Command` командлет для выполнения команды на компьютере SRV01.</span><span class="sxs-lookup"><span data-stu-id="a91ef-143">The command uses the `Invoke-Command` cmdlet to run a command on the Srv01 computer.</span></span> <span data-ttu-id="a91ef-144">Удаленная команда использует параметр **State** `Get-Job` командлета, чтобы получить все приостановленные задания на компьютере.</span><span class="sxs-lookup"><span data-stu-id="a91ef-144">The remote command uses the **State** parameter of the `Get-Job` cmdlet to get all suspended jobs on the computer.</span></span> <span data-ttu-id="a91ef-145">Оператор конвейера ( `|` ) отправляет приостановленные задания в `Resume-Job` командлет, который возобновляет их.</span><span class="sxs-lookup"><span data-stu-id="a91ef-145">A pipeline operator (`|`) sends the suspended jobs to the `Resume-Job` cmdlet, which resumes them.</span></span>

### <span data-ttu-id="a91ef-146">Пример 5. Ожидание возобновления заданий</span><span class="sxs-lookup"><span data-stu-id="a91ef-146">Example 5: Wait for jobs to resume</span></span>

<span data-ttu-id="a91ef-147">Эта команда использует параметр **Wait** для направления `Resume-Job` возврата только после возобновления всех указанных заданий.</span><span class="sxs-lookup"><span data-stu-id="a91ef-147">This command uses the **Wait** parameter to direct `Resume-Job` to return only after all specified jobs are resumed.</span></span> <span data-ttu-id="a91ef-148">Параметр **Wait** особенно полезен в сценариях, в которых предполагается, что задания должны быть возобновлены, прежде чем выполнение сценария будет продолжено.</span><span class="sxs-lookup"><span data-stu-id="a91ef-148">The **Wait** parameter is especially useful in scripts that assume that jobs are resumed before the script continues.</span></span>

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest* -Wait
```

### <span data-ttu-id="a91ef-149">Пример 6. Возобновление рабочего процесса, который приостанавливает работу</span><span class="sxs-lookup"><span data-stu-id="a91ef-149">Example 6: Resume a workflow that suspends itself</span></span>

<span data-ttu-id="a91ef-150">В этом примере кода показано `Suspend-Workflow` действие в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="a91ef-150">This code sample shows the `Suspend-Workflow` activity in a workflow.</span></span>

<span data-ttu-id="a91ef-151">`Test-Suspend`Рабочий процесс на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="a91ef-151">The `Test-Suspend` workflow on the Server01 computer.</span></span> <span data-ttu-id="a91ef-152">При запуске рабочего процесса Рабочий процесс запускает `Get-Date` действие и сохраняет результат в `$a` переменной.</span><span class="sxs-lookup"><span data-stu-id="a91ef-152">When you run the workflow, the workflow runs the `Get-Date` activity and stores the result in the `$a` variable.</span></span> <span data-ttu-id="a91ef-153">Затем выполняется `Suspend-Workflow` действие.</span><span class="sxs-lookup"><span data-stu-id="a91ef-153">Then it runs the `Suspend-Workflow` activity.</span></span> <span data-ttu-id="a91ef-154">В ответ принимается контрольная точка, приостанавливается рабочий процесс и возвращается объект задания рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="a91ef-154">In response, it takes a checkpoint, suspends the workflow, and returns a workflow job object.</span></span> <span data-ttu-id="a91ef-155">`Suspend-Workflow` Возвращает объект задания рабочего процесса, даже если рабочий процесс не выполняется явным образом как задание.</span><span class="sxs-lookup"><span data-stu-id="a91ef-155">`Suspend-Workflow` returns a workflow job object even if the workflow is not explicitly run as a job.</span></span>

<span data-ttu-id="a91ef-156">`Resume-Job` возобновляет `Test-Suspend` Рабочий процесс в Job8.</span><span class="sxs-lookup"><span data-stu-id="a91ef-156">`Resume-Job` resumes the `Test-Suspend` workflow in Job8.</span></span> <span data-ttu-id="a91ef-157">В ней используется параметр **Wait** для блокирования вывода командной строки до тех пор, пока задание не будет возобновлено.</span><span class="sxs-lookup"><span data-stu-id="a91ef-157">It uses the **Wait** parameter to hold the command prompt until the job is resumed.</span></span>

<span data-ttu-id="a91ef-158">`Receive-Job`Командлет возвращает результаты `Test-Suspend` рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="a91ef-158">The `Receive-Job` cmdlet gets the results of the `Test-Suspend` workflow.</span></span> <span data-ttu-id="a91ef-159">Последняя команда в рабочем процессе возвращает объект **TimeSpan** , представляющий истекшее время между текущей датой и временем и датой и временем, которые были сохранены в `$a` переменной до приостановки рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="a91ef-159">The final command in the workflow returns a **TimeSpan** object that represents the elapsed time between the current date and time and the date and time that was saved in the `$a` variable before the workflow was suspended.</span></span>

```
#SampleWorkflow
Workflow Test-Suspend
{
    $a = Get-Date
    Suspend-Workflow
    (Get-Date)- $a
}

PS C:\> Test-Suspend -PSComputerName Server01
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
8      Job8            PSWorkflowJob   Suspended     True            Server01             Test-Suspend

PS C:\> Resume-Job -Name "Job8" -Wait
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
8      Job8            PSWorkflowJob   Running       True            Server01             Test-Suspend

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

<span data-ttu-id="a91ef-160">`Resume-Job`Командлет позволяет возобновить задание рабочего процесса, которое было приостановлено с помощью `Suspend-Workflow` действия.</span><span class="sxs-lookup"><span data-stu-id="a91ef-160">The `Resume-Job` cmdlet lets you resume a workflow job that was suspend by using the `Suspend-Workflow` activity.</span></span> <span data-ttu-id="a91ef-161">Это действие приостанавливает рабочий процесс из самого процесса.</span><span class="sxs-lookup"><span data-stu-id="a91ef-161">This activity suspends a workflow from within a workflow.</span></span> <span data-ttu-id="a91ef-162">Оно допустимо только в рабочих процессах.</span><span class="sxs-lookup"><span data-stu-id="a91ef-162">It is valid only in workflows.</span></span>

<span data-ttu-id="a91ef-163">Дополнительные сведения о `Suspend-Workflow` см. в разделе about_Suspend-Workflow] (.. /Псворкфлов/абаут/about_Suspend-Workflow. md).</span><span class="sxs-lookup"><span data-stu-id="a91ef-163">For information about the `Suspend-Workflow`, see about_Suspend-Workflow](../PSWorkflow/about/about_Suspend-Workflow.md).</span></span>

## <span data-ttu-id="a91ef-164">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a91ef-164">PARAMETERS</span></span>

### <span data-ttu-id="a91ef-165">-Filter</span><span class="sxs-lookup"><span data-stu-id="a91ef-165">-Filter</span></span>

<span data-ttu-id="a91ef-166">Указывает хэш-таблицу условий.</span><span class="sxs-lookup"><span data-stu-id="a91ef-166">Specifies a hash table of conditions.</span></span> <span data-ttu-id="a91ef-167">Этот командлет возобновляет задания, которые соответствуют всем условиям в хэш-таблице.</span><span class="sxs-lookup"><span data-stu-id="a91ef-167">This cmdlet resumes jobs that satisfy all of the conditions in the hash table.</span></span> <span data-ttu-id="a91ef-168">Введите хэш-таблицу, где ключи являются свойствами заданий, а значения — значениями этих свойств.</span><span class="sxs-lookup"><span data-stu-id="a91ef-168">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

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

### <span data-ttu-id="a91ef-169">-Id</span><span class="sxs-lookup"><span data-stu-id="a91ef-169">-Id</span></span>

<span data-ttu-id="a91ef-170">Указывает массив идентификаторов для заданий, которые возобновляет этот командлет.</span><span class="sxs-lookup"><span data-stu-id="a91ef-170">Specifies an array of IDs for jobs that this cmdlet resumes.</span></span>

<span data-ttu-id="a91ef-171">Идентификатор — это целое число, которое однозначно определяет задание в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="a91ef-171">The ID is an integer that uniquely identifies the job in the current session.</span></span> <span data-ttu-id="a91ef-172">Проще запомнить и ввести, чем идентификатор экземпляра, но он уникален только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="a91ef-172">It is easier to remember and to type than the instance ID, but it is unique only in the current session.</span></span> <span data-ttu-id="a91ef-173">Можно ввести один или несколько идентификаторов, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="a91ef-173">You can type one or more IDs, separated by commas.</span></span> <span data-ttu-id="a91ef-174">Чтобы найти идентификатор задания, выполните команду `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="a91ef-174">To find the ID of a job, run `Get-Job`.</span></span>

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

### <span data-ttu-id="a91ef-175">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="a91ef-175">-InstanceId</span></span>

<span data-ttu-id="a91ef-176">Указывает массив идентификаторов экземпляров заданий, которые возобновляет этот командлет.</span><span class="sxs-lookup"><span data-stu-id="a91ef-176">Specifies an array of instance IDs of jobs that this cmdlet resumes.</span></span> <span data-ttu-id="a91ef-177">По умолчанию останавливаются все задания.</span><span class="sxs-lookup"><span data-stu-id="a91ef-177">The default is all jobs.</span></span>

<span data-ttu-id="a91ef-178">Идентификатор экземпляра — это GUID, который однозначно определяет задание на компьютере.</span><span class="sxs-lookup"><span data-stu-id="a91ef-178">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span> <span data-ttu-id="a91ef-179">Чтобы найти идентификатор экземпляра задания, выполните команду `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="a91ef-179">To find the instance ID of a job, run `Get-Job`.</span></span>

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

### <span data-ttu-id="a91ef-180">-Job</span><span class="sxs-lookup"><span data-stu-id="a91ef-180">-Job</span></span>

<span data-ttu-id="a91ef-181">Указывает задания, которые нужно возобновить.</span><span class="sxs-lookup"><span data-stu-id="a91ef-181">Specifies the jobs to be resumed.</span></span> <span data-ttu-id="a91ef-182">Введите переменную, содержащую задания, либо команду, которая их возвращают.</span><span class="sxs-lookup"><span data-stu-id="a91ef-182">Enter a variable that contains the jobs or a command that gets the jobs.</span></span> <span data-ttu-id="a91ef-183">Можно также передать задания по конвейеру в `Resume-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="a91ef-183">You can also pipe jobs to the `Resume-Job` cmdlet.</span></span>

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

### <span data-ttu-id="a91ef-184">-Name</span><span class="sxs-lookup"><span data-stu-id="a91ef-184">-Name</span></span>

<span data-ttu-id="a91ef-185">Указывает массив понятных имен заданий, которые возобновляет этот командлет.</span><span class="sxs-lookup"><span data-stu-id="a91ef-185">Specifies an array of friendly names of jobs that this cmdlet resumes.</span></span> <span data-ttu-id="a91ef-186">Введите одно или несколько имен заданий.</span><span class="sxs-lookup"><span data-stu-id="a91ef-186">Enter one or more job names.</span></span>
<span data-ttu-id="a91ef-187">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="a91ef-187">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="a91ef-188">-State</span><span class="sxs-lookup"><span data-stu-id="a91ef-188">-State</span></span>

<span data-ttu-id="a91ef-189">Указывает состояние заданий для возобновления.</span><span class="sxs-lookup"><span data-stu-id="a91ef-189">Specifies the state of jobs to resume.</span></span> <span data-ttu-id="a91ef-190">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="a91ef-190">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="a91ef-191">NotStarted</span><span class="sxs-lookup"><span data-stu-id="a91ef-191">NotStarted</span></span>
- <span data-ttu-id="a91ef-192">Запущен</span><span class="sxs-lookup"><span data-stu-id="a91ef-192">Running</span></span>
- <span data-ttu-id="a91ef-193">Завершено</span><span class="sxs-lookup"><span data-stu-id="a91ef-193">Completed</span></span>
- <span data-ttu-id="a91ef-194">Ошибка</span><span class="sxs-lookup"><span data-stu-id="a91ef-194">Failed</span></span>
- <span data-ttu-id="a91ef-195">Остановлена</span><span class="sxs-lookup"><span data-stu-id="a91ef-195">Stopped</span></span>
- <span data-ttu-id="a91ef-196">Блокировано</span><span class="sxs-lookup"><span data-stu-id="a91ef-196">Blocked</span></span>
- <span data-ttu-id="a91ef-197">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="a91ef-197">Suspended</span></span>
- <span data-ttu-id="a91ef-198">Отключено</span><span class="sxs-lookup"><span data-stu-id="a91ef-198">Disconnected</span></span>
- <span data-ttu-id="a91ef-199">Приостановка</span><span class="sxs-lookup"><span data-stu-id="a91ef-199">Suspending</span></span>
- <span data-ttu-id="a91ef-200">Остановка</span><span class="sxs-lookup"><span data-stu-id="a91ef-200">Stopping</span></span>

<span data-ttu-id="a91ef-201">Этот командлет возобновляет только задания в **приостановленном** состоянии.</span><span class="sxs-lookup"><span data-stu-id="a91ef-201">This cmdlet resumes only jobs in the **Suspended** state.</span></span>

<span data-ttu-id="a91ef-202">Дополнительные сведения о состояниях заданий см. в разделе [JobState enumeration](/dotnet/api/system.management.automation.jobstate).</span><span class="sxs-lookup"><span data-stu-id="a91ef-202">For more information about job states, see [JobState Enumeration](/dotnet/api/system.management.automation.jobstate).</span></span>

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

### <span data-ttu-id="a91ef-203">-Wait</span><span class="sxs-lookup"><span data-stu-id="a91ef-203">-Wait</span></span>

<span data-ttu-id="a91ef-204">Указывает, что этот командлет подавляет командную строку до тех пор, пока не будут перезапущены все результаты задания.</span><span class="sxs-lookup"><span data-stu-id="a91ef-204">Indicates that this cmdlet suppresses the command prompt until all job results are restarted.</span></span> <span data-ttu-id="a91ef-205">По умолчанию этот командлет немедленно возвращает доступные результаты.</span><span class="sxs-lookup"><span data-stu-id="a91ef-205">By default, this cmdlet immediately returns the available results.</span></span>

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

### <span data-ttu-id="a91ef-206">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a91ef-206">-Confirm</span></span>

<span data-ttu-id="a91ef-207">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="a91ef-207">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a91ef-208">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a91ef-208">-WhatIf</span></span>

<span data-ttu-id="a91ef-209">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="a91ef-209">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="a91ef-210">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="a91ef-210">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a91ef-211">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a91ef-211">CommonParameters</span></span>

<span data-ttu-id="a91ef-212">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a91ef-212">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a91ef-213">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a91ef-213">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a91ef-214">Входные данные</span><span class="sxs-lookup"><span data-stu-id="a91ef-214">INPUTS</span></span>

### <span data-ttu-id="a91ef-215">System. Management. Automation. job</span><span class="sxs-lookup"><span data-stu-id="a91ef-215">System.Management.Automation.Job</span></span>

<span data-ttu-id="a91ef-216">К этому командлету можно передать все типы заданий.</span><span class="sxs-lookup"><span data-stu-id="a91ef-216">You can pipe all types of jobs to this cmdlet.</span></span> <span data-ttu-id="a91ef-217">Если `Resume-Job` получает задание неподдерживаемого типа, оно возвращает завершающую ошибку.</span><span class="sxs-lookup"><span data-stu-id="a91ef-217">If `Resume-Job` gets a job of an unsupported type, it returns a terminating error.</span></span>

## <span data-ttu-id="a91ef-218">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a91ef-218">OUTPUTS</span></span>

### <span data-ttu-id="a91ef-219">Нет, System. Management. Automation. job</span><span class="sxs-lookup"><span data-stu-id="a91ef-219">None, System.Management.Automation.Job</span></span>

<span data-ttu-id="a91ef-220">Этот командлет возвращает задания, которые он пытается возобновить, если используется параметр **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="a91ef-220">This cmdlet returns the jobs that it tries to resume, if you use the **PassThru** parameter.</span></span>
<span data-ttu-id="a91ef-221">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="a91ef-221">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="a91ef-222">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="a91ef-222">NOTES</span></span>

- <span data-ttu-id="a91ef-223">`Resume-Job` может возобновлять только приостановленные задания.</span><span class="sxs-lookup"><span data-stu-id="a91ef-223">`Resume-Job` can only resume jobs that are suspended.</span></span> <span data-ttu-id="a91ef-224">При отправке задания в другом состоянии `Resume-Job` выполняет операцию возобновления задания, но выдает предупреждение о том, что задание не может быть возобновлено.</span><span class="sxs-lookup"><span data-stu-id="a91ef-224">If you submit a job in a different state, `Resume-Job` runs the resume operation on the job, but generates a warning to notify you that the job could not be resumed.</span></span> <span data-ttu-id="a91ef-225">Чтобы отключить это предупреждение, используйте общий параметр **WarningAction** со значением SilentlyContinue.</span><span class="sxs-lookup"><span data-stu-id="a91ef-225">To suppress the warning, use the **WarningAction** common parameter with a value of SilentlyContinue.</span></span>
- <span data-ttu-id="a91ef-226">Если задание не относится к типу, который поддерживает возобновление, например задание рабочего процесса ( **псворкфловжоб** ), `Resume-Job` Возвращает завершающую ошибку.</span><span class="sxs-lookup"><span data-stu-id="a91ef-226">If a job is not of a type that supports resuming, such as a workflow job ( **PSWorkflowJob** ), `Resume-Job` returns a terminating error.</span></span>
- <span data-ttu-id="a91ef-227">Механизм и место сохранения приостановленного задания могут различаться в зависимости от его типа.</span><span class="sxs-lookup"><span data-stu-id="a91ef-227">The mechanism and location for saving a suspended job might vary depending on the job type.</span></span> <span data-ttu-id="a91ef-228">Например, по умолчанию приостановленные задания рабочих процессов сохраняются в хранилище неструктурированных файлов, но также могут сохраняться в базе данных SQL.</span><span class="sxs-lookup"><span data-stu-id="a91ef-228">For example, suspended workflow jobs are saved in a flat file store by default, but can also be saved in a SQL database.</span></span>
- <span data-ttu-id="a91ef-229">При возобновлении задания его состояние меняется с **Suspended** на **Running**.</span><span class="sxs-lookup"><span data-stu-id="a91ef-229">When you resume a job, the job state changes from **Suspended** to **Running**.</span></span> <span data-ttu-id="a91ef-230">Чтобы найти выполняемые задания, включая те, которые были возобновлены с помощью этого командлета, используйте параметр **State** `Get-Job` командлета для получения заданий в состоянии **выполняется** .</span><span class="sxs-lookup"><span data-stu-id="a91ef-230">To find the jobs that are running, including those that were resumed by this cmdlet, use the **State** parameter of the `Get-Job` cmdlet to get jobs in the **Running** state.</span></span>
- <span data-ttu-id="a91ef-231">Задания некоторых типов имеют параметры или свойства, которые не позволяют среде Windows PowerShell приостанавливать их.</span><span class="sxs-lookup"><span data-stu-id="a91ef-231">Some job types have options or properties that prevent Windows PowerShell from suspending the job.</span></span>
  <span data-ttu-id="a91ef-232">Если попытки приостановить задание завершились ошибкой, убедитесь, что параметры задания и свойства допускают приостановку.</span><span class="sxs-lookup"><span data-stu-id="a91ef-232">If attempts to suspend the job fail, verify that the job options and properties allow for suspending.</span></span>

## <span data-ttu-id="a91ef-233">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a91ef-233">RELATED LINKS</span></span>

[<span data-ttu-id="a91ef-234">Get-Job.</span><span class="sxs-lookup"><span data-stu-id="a91ef-234">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="a91ef-235">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="a91ef-235">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="a91ef-236">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="a91ef-236">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="a91ef-237">Start-Job</span><span class="sxs-lookup"><span data-stu-id="a91ef-237">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="a91ef-238">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="a91ef-238">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="a91ef-239">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="a91ef-239">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="a91ef-240">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="a91ef-240">Wait-Job</span></span>](Wait-Job.md)
