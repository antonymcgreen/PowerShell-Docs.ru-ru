---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-job?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Job
ms.openlocfilehash: 52db5da9057023ce9a687e1d11b0534afaabdad9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226898"
---
# <span data-ttu-id="bf46a-103">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="bf46a-103">Remove-Job</span></span>

## <span data-ttu-id="bf46a-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="bf46a-104">SYNOPSIS</span></span>
<span data-ttu-id="bf46a-105">Удаляет фоновое задание PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf46a-105">Deletes a PowerShell background job.</span></span>

## <span data-ttu-id="bf46a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bf46a-106">SYNTAX</span></span>

### <span data-ttu-id="bf46a-107">Сессионидпараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="bf46a-107">SessionIdParameterSet (Default)</span></span>

```
Remove-Job [-Force] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="bf46a-108">жобпараметерсет</span><span class="sxs-lookup"><span data-stu-id="bf46a-108">JobParameterSet</span></span>

```
Remove-Job [-Job] <Job[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="bf46a-109">намепараметерсет</span><span class="sxs-lookup"><span data-stu-id="bf46a-109">NameParameterSet</span></span>

```
Remove-Job [-Force] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="bf46a-110">инстанцеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="bf46a-110">InstanceIdParameterSet</span></span>

```
Remove-Job [-Force] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="bf46a-111">филтерпараметерсет</span><span class="sxs-lookup"><span data-stu-id="bf46a-111">FilterParameterSet</span></span>

```
Remove-Job [-Force] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="bf46a-112">статепараметерсет</span><span class="sxs-lookup"><span data-stu-id="bf46a-112">StateParameterSet</span></span>

```
Remove-Job [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="bf46a-113">коммандпараметерсет</span><span class="sxs-lookup"><span data-stu-id="bf46a-113">CommandParameterSet</span></span>

```
Remove-Job [-Command <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="bf46a-114">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bf46a-114">DESCRIPTION</span></span>

<span data-ttu-id="bf46a-115">`Remove-Job`Командлет удаляет фоновые задания PowerShell, которые были запущены `Start-Job` командлетом или командлетами `Invoke-Command` , например, поддерживают параметр **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="bf46a-115">The `Remove-Job` cmdlet deletes PowerShell background jobs that were started by the `Start-Job` cmdlet or by cmdlets such as `Invoke-Command` that support the **AsJob** parameter.</span></span>

<span data-ttu-id="bf46a-116">Можно использовать `Remove-Job` для удаления всех заданий или удаления выбранных заданий.</span><span class="sxs-lookup"><span data-stu-id="bf46a-116">You can use `Remove-Job` to delete all jobs or delete selected jobs.</span></span> <span data-ttu-id="bf46a-117">Задания идентифицируются по **имени** , **ИДЕНТИФИКАТОРу** , **идентификатору экземпляра** , **команде** или **состоянию**.</span><span class="sxs-lookup"><span data-stu-id="bf46a-117">The jobs are identified by their **Name** , **ID** , **Instance ID** , **Command** , or **State**.</span></span> <span data-ttu-id="bf46a-118">Или же объект задания может быть отправлен в конвейер в `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="bf46a-118">Or, a job object can be sent down the pipeline to `Remove-Job`.</span></span> <span data-ttu-id="bf46a-119">Без параметров и значений параметров не оказывает никакого `Remove-Job` влияния.</span><span class="sxs-lookup"><span data-stu-id="bf46a-119">Without parameters or parameter values, `Remove-Job` has no effect.</span></span>

<span data-ttu-id="bf46a-120">Поскольку PowerShell 3,0, `Remove-Job` может удалять пользовательские типы заданий, такие как запланированные задания и задания рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="bf46a-120">Since PowerShell 3.0, `Remove-Job` can delete custom job types, such as scheduled jobs and workflow jobs.</span></span> <span data-ttu-id="bf46a-121">Например, `Remove-Job` удаляет запланированное задание, все экземпляры запланированного задания на диске и результаты всех запущенных экземпляров заданий.</span><span class="sxs-lookup"><span data-stu-id="bf46a-121">For example, `Remove-Job` deletes the scheduled job, all instances of the scheduled job on disk, and the results of all triggered job instances.</span></span>

<span data-ttu-id="bf46a-122">При попытке удалить выполняющееся задание `Remove-Job` завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="bf46a-122">If you try to delete a running job, `Remove-Job` fails.</span></span> <span data-ttu-id="bf46a-123">Используйте `Stop-Job` командлет для завершения выполняющегося задания.</span><span class="sxs-lookup"><span data-stu-id="bf46a-123">Use the `Stop-Job` cmdlet to stop a running job.</span></span> <span data-ttu-id="bf46a-124">Или используйте `Remove-Job` с параметром **Force** для удаления выполняющегося задания.</span><span class="sxs-lookup"><span data-stu-id="bf46a-124">Or, use `Remove-Job` with the **Force** parameter to delete a running job.</span></span>

<span data-ttu-id="bf46a-125">Задания остаются в глобальном кэше заданий до тех пор, пока не будет удалено фоновое задание или не будет закрыт сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf46a-125">Jobs remain in the global job cache until you delete the background job or close the PowerShell session.</span></span>

## <span data-ttu-id="bf46a-126">Примеры</span><span class="sxs-lookup"><span data-stu-id="bf46a-126">EXAMPLES</span></span>

### <span data-ttu-id="bf46a-127">Пример 1. Удаление задания с использованием его имени</span><span class="sxs-lookup"><span data-stu-id="bf46a-127">Example 1: Delete a job by using its name</span></span>

<span data-ttu-id="bf46a-128">В этом примере используется переменная и конвейер для удаления задания по имени.</span><span class="sxs-lookup"><span data-stu-id="bf46a-128">This example uses a variable and the pipeline to delete a job by name.</span></span>

```powershell
$batch = Get-Job -Name BatchJob
$batch | Remove-Job
```

<span data-ttu-id="bf46a-129">`Get-Job` использует параметр **Name** для указания задания **батчжоб**.</span><span class="sxs-lookup"><span data-stu-id="bf46a-129">`Get-Job` uses the **Name** parameter to specify the job, **BatchJob**.</span></span> <span data-ttu-id="bf46a-130">Объект задания хранится в `$batch` переменной.</span><span class="sxs-lookup"><span data-stu-id="bf46a-130">The job object is stored in the `$batch` variable.</span></span> <span data-ttu-id="bf46a-131">Объект в отправляется в `$batch` конвейер в `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="bf46a-131">The object in `$batch` is sent down the pipeline to `Remove-Job`.</span></span>

<span data-ttu-id="bf46a-132">Альтернативой является использование параметра **задания** , например `Remove-Job -Job $batch` .</span><span class="sxs-lookup"><span data-stu-id="bf46a-132">An alternative is to use the **Job** parameter, such as `Remove-Job -Job $batch`.</span></span>

### <span data-ttu-id="bf46a-133">Пример 2. Удаление всех заданий в сеансе</span><span class="sxs-lookup"><span data-stu-id="bf46a-133">Example 2: Delete all jobs in a session</span></span>

<span data-ttu-id="bf46a-134">В этом примере удаляются все задания в текущем сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf46a-134">In this example, all the jobs in the current PowerShell session are deleted.</span></span>

```powershell
Get-job | Remove-Job
```

<span data-ttu-id="bf46a-135">`Get-Job` Возвращает все задания в текущем сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf46a-135">`Get-Job` gets all the jobs in the current PowerShell session.</span></span> <span data-ttu-id="bf46a-136">Объекты задания отправляются по конвейеру в `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="bf46a-136">The job objects are sent down the pipeline to `Remove-Job`.</span></span>

### <span data-ttu-id="bf46a-137">Пример 3. Удаление заданий NotStarted</span><span class="sxs-lookup"><span data-stu-id="bf46a-137">Example 3: Delete NotStarted jobs</span></span>

<span data-ttu-id="bf46a-138">В этом примере удаляются все задания из текущего сеанса PowerShell, который еще не запущен.</span><span class="sxs-lookup"><span data-stu-id="bf46a-138">This example deletes all jobs from the current PowerShell session that haven't started.</span></span>

```powershell
Remove-Job -State NotStarted
```

<span data-ttu-id="bf46a-139">`Remove-Job` Задает состояние задания с помощью параметра **State** .</span><span class="sxs-lookup"><span data-stu-id="bf46a-139">`Remove-Job` uses the **State** parameter to specify the job status.</span></span>

### <span data-ttu-id="bf46a-140">Пример 4. Удаление заданий с помощью понятного имени</span><span class="sxs-lookup"><span data-stu-id="bf46a-140">Example 4: Delete jobs by using a friendly name</span></span>

<span data-ttu-id="bf46a-141">В этом примере удаляются все задания из текущего сеанса с понятными именами, заканчивающимися на \* Batch \* \*, включая выполняемые задания.</span><span class="sxs-lookup"><span data-stu-id="bf46a-141">This example deletes all jobs from the current session with friendly names that end with \*batch\*\*, including jobs that are running.</span></span>

```powershell
Remove-Job -Name *batch -Force
```

<span data-ttu-id="bf46a-142">`Remove-Job` использует параметр **Name** для указания шаблона имени задания.</span><span class="sxs-lookup"><span data-stu-id="bf46a-142">`Remove-Job` uses the **Name** parameter to specify a job name pattern.</span></span> <span data-ttu-id="bf46a-143">Шаблон содержит `*` подстановочный знак звездочки () для поиска всех имен заданий, заканчивающихся **пакетной** службой.</span><span class="sxs-lookup"><span data-stu-id="bf46a-143">The pattern includes the asterisk (`*`) wildcard to find all job names that end with **batch**.</span></span> <span data-ttu-id="bf46a-144">Параметр **Force** удаляет задания, выполняющие.</span><span class="sxs-lookup"><span data-stu-id="bf46a-144">The **Force** parameter deletes jobs that running.</span></span>

### <span data-ttu-id="bf46a-145">Пример 5. Удаление задания, созданного с помощью Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="bf46a-145">Example 5: Delete a job that was created by Invoke-Command</span></span>

<span data-ttu-id="bf46a-146">В этом примере удаляется задание, запущенное на удаленном компьютере с `Invoke-Command` параметром **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="bf46a-146">This example removes a job that was started on a remote computer using `Invoke-Command` with the **AsJob** parameter.</span></span>

<span data-ttu-id="bf46a-147">Так как в примере используется параметр **AsJob** , объект задания создается на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="bf46a-147">Because the example uses the **AsJob** parameter, the job object is created on the local computer.</span></span>
<span data-ttu-id="bf46a-148">Но задание выполняется на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="bf46a-148">But, the job runs on a remote computer.</span></span> <span data-ttu-id="bf46a-149">Таким образом, для управления заданием можно использовать локальные команды.</span><span class="sxs-lookup"><span data-stu-id="bf46a-149">As a result, you use local commands to manage the job.</span></span>

```powershell
$job = Invoke-Command -ComputerName Server01 -ScriptBlock {Get-Process} -AsJob
$job | Remove-Job
```

<span data-ttu-id="bf46a-150">`Invoke-Command` запускает задание на компьютере **Server01** .</span><span class="sxs-lookup"><span data-stu-id="bf46a-150">`Invoke-Command` runs a job on the **Server01** computer.</span></span> <span data-ttu-id="bf46a-151">Параметр **AsJob** запускает **ScriptBlock** как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="bf46a-151">The **AsJob** parameter runs the **ScriptBlock** as a background job.</span></span> <span data-ttu-id="bf46a-152">Объект задания хранится в `$job` переменной.</span><span class="sxs-lookup"><span data-stu-id="bf46a-152">The job object is stored in the `$job` variable.</span></span> <span data-ttu-id="bf46a-153">`$job`Объект переменной отправляется по конвейеру в `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="bf46a-153">The `$job` variable object is sent down the pipeline to `Remove-Job`.</span></span>

### <span data-ttu-id="bf46a-154">Пример 6. Удаление задания, созданного с помощью Invoke-Command и Start-Job</span><span class="sxs-lookup"><span data-stu-id="bf46a-154">Example 6: Delete a job that was created by Invoke-Command and Start-Job</span></span>

<span data-ttu-id="bf46a-155">В этом примере показано, как удалить задание на удаленном компьютере, запущенном с помощью команды `Invoke-Command` для запуска `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="bf46a-155">This example shows how to remove a job on a remote computer that was started by using `Invoke-Command` to run `Start-Job`.</span></span> <span data-ttu-id="bf46a-156">Объект задания создается на удаленном компьютере, а для управления заданием используются удаленные команды.</span><span class="sxs-lookup"><span data-stu-id="bf46a-156">The job object is created on the remote computer and remote commands are used to manage the job.</span></span> <span data-ttu-id="bf46a-157">При выполнении удаленной команды требуется постоянное подключение `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="bf46a-157">A persistent connection is required when running a remote `Start-Job` command.</span></span>

```powershell
$S = New-PSSession -ComputerName Server01
Invoke-Command -Session $S -ScriptBlock {Start-Job -ScriptBlock {Get-Process} -Name MyJob}
Invoke-Command -Session $S -ScriptBlock {Remove-Job -Name MyJob}
```

<span data-ttu-id="bf46a-158">`New-PSSession`создает на компьютере **Server01** **сеанс PSSession** , постоянное подключение.</span><span class="sxs-lookup"><span data-stu-id="bf46a-158">`New-PSSession` creates a **PSSession** , a persistent connection, to the **Server01** computer.</span></span> <span data-ttu-id="bf46a-159">Соединение сохраняется в `$S` переменной.</span><span class="sxs-lookup"><span data-stu-id="bf46a-159">The connection is saved in the `$S` variable.</span></span>

<span data-ttu-id="bf46a-160">`Invoke-Command` подключается к сеансу, сохраненному в `$S` .</span><span class="sxs-lookup"><span data-stu-id="bf46a-160">`Invoke-Command` connects to the session saved in `$S`.</span></span> <span data-ttu-id="bf46a-161">Блок **ScriptBlock** использует `Start-Job` для запуска удаленного задания.</span><span class="sxs-lookup"><span data-stu-id="bf46a-161">The **ScriptBlock** uses `Start-Job` to start a remote job.</span></span> <span data-ttu-id="bf46a-162">Задание выполняет `Get-Process` команду и использует параметр **Name** для указания понятного имени задания **MyJob**.</span><span class="sxs-lookup"><span data-stu-id="bf46a-162">The job runs a `Get-Process` command and uses the **Name** parameter to specify a friendly job name, **MyJob**.</span></span>

<span data-ttu-id="bf46a-163">`Invoke-Command` использует `$S` сеанс и выполняется `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="bf46a-163">`Invoke-Command` uses the `$S` session and runs `Remove-Job`.</span></span> <span data-ttu-id="bf46a-164">Параметр **Name** указывает, что задание с именем **MyJob** будет удалено.</span><span class="sxs-lookup"><span data-stu-id="bf46a-164">The **Name** parameter specifies that the job named **MyJob** is deleted.</span></span>

### <span data-ttu-id="bf46a-165">Пример 7. Удаление задания с помощью InstanceId</span><span class="sxs-lookup"><span data-stu-id="bf46a-165">Example 7: Delete a job by using its InstanceId</span></span>

<span data-ttu-id="bf46a-166">В этом примере удаляется задание, основанное на его **InstanceId**.</span><span class="sxs-lookup"><span data-stu-id="bf46a-166">This example removes a job based on its **InstanceId**.</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Process PowerShell}
$job | Format-List -Property *
Remove-Job -InstanceId ad02b942-8007-4407-87f3-d23e71955872
```

```Output
State         : Completed
HasMoreData   : True
StatusMessage :
Location      : localhost
Command       : Get-Process PowerShell
JobStateInfo  : Completed
Finished      : System.Threading.ManualResetEvent
InstanceId    : ad02b942-8007-4407-87f3-d23e71955872
Id            : 3
Name          : Job3
ChildJobs     : {Job4}
PSBeginTime   : 7/26/2019 11:36:56
PSEndTime     : 7/26/2019 11:36:57
PSJobTypeName : BackgroundJob
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
Information   : {}
```

<span data-ttu-id="bf46a-167">`Start-Job` Запускает фоновое задание, а объект задания сохраняется в `$job` переменной.</span><span class="sxs-lookup"><span data-stu-id="bf46a-167">`Start-Job` starts a background job and the job object is saved in the `$job` variable.</span></span>

<span data-ttu-id="bf46a-168">Объект в отправляется в `$job` конвейер в `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="bf46a-168">The object in `$job` is sent down the pipeline to `Format-List`.</span></span> <span data-ttu-id="bf46a-169">Параметр **Property** использует звездочку ( `*` ), чтобы указать, что все свойства объекта отображаются в списке.</span><span class="sxs-lookup"><span data-stu-id="bf46a-169">The **Property** parameter uses an asterisk (`*`) to specify that all the object's properties are displayed in a list.</span></span>

<span data-ttu-id="bf46a-170">`Remove-Job` задает удаляемое задание с помощью параметра **InstanceId** .</span><span class="sxs-lookup"><span data-stu-id="bf46a-170">`Remove-Job` uses the **InstanceId** parameter to specify the job to delete.</span></span>

## <span data-ttu-id="bf46a-171">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bf46a-171">PARAMETERS</span></span>

### <span data-ttu-id="bf46a-172">-Command</span><span class="sxs-lookup"><span data-stu-id="bf46a-172">-Command</span></span>

<span data-ttu-id="bf46a-173">Удаляет задания, в команды которых входят указанные слова.</span><span class="sxs-lookup"><span data-stu-id="bf46a-173">Deletes jobs that include the specified words in the command.</span></span> <span data-ttu-id="bf46a-174">Можно ввести разделенный запятыми массив.</span><span class="sxs-lookup"><span data-stu-id="bf46a-174">You can enter a comma-separated array.</span></span>

```yaml
Type: System.String[]
Parameter Sets: CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="bf46a-175">-Confirm</span><span class="sxs-lookup"><span data-stu-id="bf46a-175">-Confirm</span></span>

<span data-ttu-id="bf46a-176">Запрашивает подтверждение перед `Remove-Job` запуском.</span><span class="sxs-lookup"><span data-stu-id="bf46a-176">Prompts you for confirmation before `Remove-Job` is run.</span></span>

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

### <span data-ttu-id="bf46a-177">-Filter</span><span class="sxs-lookup"><span data-stu-id="bf46a-177">-Filter</span></span>

<span data-ttu-id="bf46a-178">Удаляет задания, которые соответствуют всем условиям, установленным в связанной хэш-таблице.</span><span class="sxs-lookup"><span data-stu-id="bf46a-178">Deletes jobs that satisfy all the conditions established in the associated hash table.</span></span> <span data-ttu-id="bf46a-179">Введите хэш-таблицу, где ключи являются свойствами заданий, а значения — значениями этих свойств.</span><span class="sxs-lookup"><span data-stu-id="bf46a-179">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="bf46a-180">Этот параметр работает только с пользовательскими типами заданий, такими как задания рабочих процессов и запланированные задания.</span><span class="sxs-lookup"><span data-stu-id="bf46a-180">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span> <span data-ttu-id="bf46a-181">Он не работает со стандартными фоновыми заданиями, такими как созданные с помощью `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="bf46a-181">It doesn't work on standard background jobs, such as those created by using the `Start-Job`.</span></span>

<span data-ttu-id="bf46a-182">Этот параметр впервые появился в PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="bf46a-182">This parameter is introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="bf46a-183">-Force</span><span class="sxs-lookup"><span data-stu-id="bf46a-183">-Force</span></span>

<span data-ttu-id="bf46a-184">Удаляет задание, даже если состояние задания — **работает**.</span><span class="sxs-lookup"><span data-stu-id="bf46a-184">Deletes a job even if the job's state is **Running**.</span></span> <span data-ttu-id="bf46a-185">Если параметр **Force** не указан, то `Remove-Job` не удаляет выполняющиеся задания.</span><span class="sxs-lookup"><span data-stu-id="bf46a-185">If the **Force** parameter isn't specified, `Remove-Job` doesn't delete running jobs.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SessionIdParameterSet, JobParameterSet, NameParameterSet, InstanceIdParameterSet, FilterParameterSet
Aliases: F

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bf46a-186">-Id</span><span class="sxs-lookup"><span data-stu-id="bf46a-186">-Id</span></span>

<span data-ttu-id="bf46a-187">Удаляет фоновые задания с указанным **идентификатором**. Можно ввести разделенный запятыми массив.</span><span class="sxs-lookup"><span data-stu-id="bf46a-187">Deletes background jobs with the specified **Id**. You can enter a comma-separated array.</span></span> <span data-ttu-id="bf46a-188">**Идентификатор** задания — это уникальное целое число, определяющее задание в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="bf46a-188">The job's **Id** is a unique integer that identifies a job within the current session.</span></span>

<span data-ttu-id="bf46a-189">Чтобы найти **идентификатор** задания, используйте `Get-Job` параметр без параметров.</span><span class="sxs-lookup"><span data-stu-id="bf46a-189">To find a job's **Id** , use `Get-Job` without parameters.</span></span>

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

### <span data-ttu-id="bf46a-190">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="bf46a-190">-InstanceId</span></span>

<span data-ttu-id="bf46a-191">Удаляет задания с указанным **InstanceId**.</span><span class="sxs-lookup"><span data-stu-id="bf46a-191">Deletes jobs with the specified **InstanceId**.</span></span> <span data-ttu-id="bf46a-192">Можно ввести разделенный запятыми массив.</span><span class="sxs-lookup"><span data-stu-id="bf46a-192">You can enter a comma-separated array.</span></span> <span data-ttu-id="bf46a-193">**InstanceId** — это уникальный идентификатор GUID, определяющий задание.</span><span class="sxs-lookup"><span data-stu-id="bf46a-193">An **InstanceId** is a unique GUID that identifies a job.</span></span>

<span data-ttu-id="bf46a-194">Чтобы найти **InstanceId** задания, используйте `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="bf46a-194">To find a job's **InstanceId** , use `Get-Job`.</span></span>

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

### <span data-ttu-id="bf46a-195">-Job</span><span class="sxs-lookup"><span data-stu-id="bf46a-195">-Job</span></span>

<span data-ttu-id="bf46a-196">Указывает задания, которые требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="bf46a-196">Specifies the jobs to be deleted.</span></span> <span data-ttu-id="bf46a-197">Введите переменную, содержащую задания, либо команду, которая их возвращают.</span><span class="sxs-lookup"><span data-stu-id="bf46a-197">Enter a variable that contains the jobs or a command that gets the jobs.</span></span> <span data-ttu-id="bf46a-198">Можно ввести разделенный запятыми массив.</span><span class="sxs-lookup"><span data-stu-id="bf46a-198">You can enter a comma-separated array.</span></span>

<span data-ttu-id="bf46a-199">Объекты задания можно отправить по конвейеру в `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="bf46a-199">You can send job objects down the pipeline to `Remove-Job`.</span></span>

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

### <span data-ttu-id="bf46a-200">-Name</span><span class="sxs-lookup"><span data-stu-id="bf46a-200">-Name</span></span>

<span data-ttu-id="bf46a-201">Удаляет только задания с указанным понятным именем.</span><span class="sxs-lookup"><span data-stu-id="bf46a-201">Only deletes jobs with the specified friendly name.</span></span> <span data-ttu-id="bf46a-202">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="bf46a-202">Wildcards are permitted.</span></span> <span data-ttu-id="bf46a-203">Можно ввести разделенный запятыми массив.</span><span class="sxs-lookup"><span data-stu-id="bf46a-203">You can enter a comma-separated array.</span></span>

<span data-ttu-id="bf46a-204">Понятные имена для заданий не обязательно должны быть уникальными даже в рамках сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf46a-204">Friendly names for jobs aren't guaranteed to be unique, even within a PowerShell session.</span></span> <span data-ttu-id="bf46a-205">Используйте параметры **WhatIf** и **Confirm** при удалении файлов по имени.</span><span class="sxs-lookup"><span data-stu-id="bf46a-205">Use the **WhatIf** and **Confirm** parameters when you delete files by name.</span></span>

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

### <span data-ttu-id="bf46a-206">-State</span><span class="sxs-lookup"><span data-stu-id="bf46a-206">-State</span></span>

<span data-ttu-id="bf46a-207">Удаляет только задания с указанным состоянием.</span><span class="sxs-lookup"><span data-stu-id="bf46a-207">Only deletes jobs with the specified state.</span></span> <span data-ttu-id="bf46a-208">Чтобы удалить задания с состоянием **работает** , используйте параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="bf46a-208">To delete jobs with a state of **Running** , use the **Force** parameter.</span></span>

<span data-ttu-id="bf46a-209">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="bf46a-209">Accepted values:</span></span>

- <span data-ttu-id="bf46a-210">AtBreakpoint</span><span class="sxs-lookup"><span data-stu-id="bf46a-210">AtBreakpoint</span></span>
- <span data-ttu-id="bf46a-211">Блокировано</span><span class="sxs-lookup"><span data-stu-id="bf46a-211">Blocked</span></span>
- <span data-ttu-id="bf46a-212">Завершено</span><span class="sxs-lookup"><span data-stu-id="bf46a-212">Completed</span></span>
- <span data-ttu-id="bf46a-213">Отключено</span><span class="sxs-lookup"><span data-stu-id="bf46a-213">Disconnected</span></span>
- <span data-ttu-id="bf46a-214">Сбой</span><span class="sxs-lookup"><span data-stu-id="bf46a-214">Failed</span></span>
- <span data-ttu-id="bf46a-215">NotStarted</span><span class="sxs-lookup"><span data-stu-id="bf46a-215">NotStarted</span></span>
- <span data-ttu-id="bf46a-216">Запущен</span><span class="sxs-lookup"><span data-stu-id="bf46a-216">Running</span></span>
- <span data-ttu-id="bf46a-217">Остановлена</span><span class="sxs-lookup"><span data-stu-id="bf46a-217">Stopped</span></span>
- <span data-ttu-id="bf46a-218">Остановка</span><span class="sxs-lookup"><span data-stu-id="bf46a-218">Stopping</span></span>
- <span data-ttu-id="bf46a-219">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="bf46a-219">Suspended</span></span>
- <span data-ttu-id="bf46a-220">Приостановка</span><span class="sxs-lookup"><span data-stu-id="bf46a-220">Suspending</span></span>

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: AtBreakpoint, Blocked, Completed, Disconnected, Failed, NotStarted, Running, Stopped, Stopping, Suspended, Suspending

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="bf46a-221">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="bf46a-221">-WhatIf</span></span>

<span data-ttu-id="bf46a-222">Показывает, что произойдет при `Remove-Job` запуске.</span><span class="sxs-lookup"><span data-stu-id="bf46a-222">Shows what would happen if `Remove-Job` runs.</span></span> <span data-ttu-id="bf46a-223">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="bf46a-223">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="bf46a-224">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="bf46a-224">CommonParameters</span></span>

<span data-ttu-id="bf46a-225">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bf46a-225">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bf46a-226">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bf46a-226">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bf46a-227">Входные данные</span><span class="sxs-lookup"><span data-stu-id="bf46a-227">INPUTS</span></span>

### <span data-ttu-id="bf46a-228">System. Management. Automation. job</span><span class="sxs-lookup"><span data-stu-id="bf46a-228">System.Management.Automation.Job</span></span>

<span data-ttu-id="bf46a-229">Объект задания можно отправить по конвейеру в `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="bf46a-229">You can send a job object down the pipeline to `Remove-Job`.</span></span>

## <span data-ttu-id="bf46a-230">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="bf46a-230">OUTPUTS</span></span>

### <span data-ttu-id="bf46a-231">Нет</span><span class="sxs-lookup"><span data-stu-id="bf46a-231">None</span></span>

<span data-ttu-id="bf46a-232">`Remove-Job` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="bf46a-232">`Remove-Job` doesn't generate any output.</span></span>

## <span data-ttu-id="bf46a-233">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="bf46a-233">NOTES</span></span>

<span data-ttu-id="bf46a-234">Задание PowerShell создает новый процесс.</span><span class="sxs-lookup"><span data-stu-id="bf46a-234">A PowerShell job creates a new process.</span></span> <span data-ttu-id="bf46a-235">После завершения задания процесс завершается.</span><span class="sxs-lookup"><span data-stu-id="bf46a-235">When the job completes, the process exits.</span></span> <span data-ttu-id="bf46a-236">При `Remove-Job` запуске состояние задания удаляется.</span><span class="sxs-lookup"><span data-stu-id="bf46a-236">When `Remove-Job` is run, the job's state is removed.</span></span>

<span data-ttu-id="bf46a-237">Если задание останавливается до завершения и его процесс не завершается, процесс принудительно завершается.</span><span class="sxs-lookup"><span data-stu-id="bf46a-237">If a job stops before completion and its process hasn't exited, the process is forcibly terminated.</span></span>

## <span data-ttu-id="bf46a-238">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="bf46a-238">RELATED LINKS</span></span>

[<span data-ttu-id="bf46a-239">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="bf46a-239">about_Jobs</span></span>](./About/about_Jobs.md)

[<span data-ttu-id="bf46a-240">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="bf46a-240">about_Job_Details</span></span>](./About/about_Job_Details.md)

[<span data-ttu-id="bf46a-241">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="bf46a-241">about_Remote_Jobs</span></span>](./About/about_Remote_Jobs.md)

[<span data-ttu-id="bf46a-242">Get-Job.</span><span class="sxs-lookup"><span data-stu-id="bf46a-242">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="bf46a-243">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="bf46a-243">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="bf46a-244">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="bf46a-244">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="bf46a-245">Start-Job</span><span class="sxs-lookup"><span data-stu-id="bf46a-245">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="bf46a-246">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="bf46a-246">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="bf46a-247">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="bf46a-247">Wait-Job</span></span>](Wait-Job.md)
