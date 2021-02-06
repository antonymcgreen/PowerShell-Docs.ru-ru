---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-job?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Job
ms.openlocfilehash: 52613dae3ba73227818c6c0dec40183ba20ce2a3
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600018"
---
# <span data-ttu-id="0f8a9-102">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="0f8a9-102">Remove-Job</span></span>

## <span data-ttu-id="0f8a9-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0f8a9-103">SYNOPSIS</span></span>
<span data-ttu-id="0f8a9-104">Удаляет фоновое задание PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-104">Deletes a PowerShell background job.</span></span>

## <span data-ttu-id="0f8a9-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0f8a9-105">SYNTAX</span></span>

### <span data-ttu-id="0f8a9-106">Сессионидпараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="0f8a9-106">SessionIdParameterSet (Default)</span></span>

```
Remove-Job [-Force] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0f8a9-107">жобпараметерсет</span><span class="sxs-lookup"><span data-stu-id="0f8a9-107">JobParameterSet</span></span>

```
Remove-Job [-Job] <Job[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0f8a9-108">намепараметерсет</span><span class="sxs-lookup"><span data-stu-id="0f8a9-108">NameParameterSet</span></span>

```
Remove-Job [-Force] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0f8a9-109">инстанцеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="0f8a9-109">InstanceIdParameterSet</span></span>

```
Remove-Job [-Force] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0f8a9-110">филтерпараметерсет</span><span class="sxs-lookup"><span data-stu-id="0f8a9-110">FilterParameterSet</span></span>

```
Remove-Job [-Force] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0f8a9-111">статепараметерсет</span><span class="sxs-lookup"><span data-stu-id="0f8a9-111">StateParameterSet</span></span>

```
Remove-Job [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0f8a9-112">коммандпараметерсет</span><span class="sxs-lookup"><span data-stu-id="0f8a9-112">CommandParameterSet</span></span>

```
Remove-Job [-Command <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0f8a9-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0f8a9-113">DESCRIPTION</span></span>

<span data-ttu-id="0f8a9-114">`Remove-Job`Командлет удаляет фоновые задания PowerShell, которые были запущены `Start-Job` командлетом или командлетами `Invoke-Command` , например, поддерживают параметр **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="0f8a9-114">The `Remove-Job` cmdlet deletes PowerShell background jobs that were started by the `Start-Job` cmdlet or by cmdlets such as `Invoke-Command` that support the **AsJob** parameter.</span></span>

<span data-ttu-id="0f8a9-115">Можно использовать `Remove-Job` для удаления всех заданий или удаления выбранных заданий.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-115">You can use `Remove-Job` to delete all jobs or delete selected jobs.</span></span> <span data-ttu-id="0f8a9-116">Задания идентифицируются по **имени**, **ИДЕНТИФИКАТОРу**, **идентификатору экземпляра**, **команде** или **состоянию**.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-116">The jobs are identified by their **Name**, **ID**, **Instance ID**, **Command**, or **State**.</span></span> <span data-ttu-id="0f8a9-117">Или же объект задания может быть отправлен в конвейер в `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="0f8a9-117">Or, a job object can be sent down the pipeline to `Remove-Job`.</span></span> <span data-ttu-id="0f8a9-118">Без параметров и значений параметров не оказывает никакого `Remove-Job` влияния.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-118">Without parameters or parameter values, `Remove-Job` has no effect.</span></span>

<span data-ttu-id="0f8a9-119">Поскольку PowerShell 3,0, `Remove-Job` может удалять пользовательские типы заданий, такие как запланированные задания и задания рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-119">Since PowerShell 3.0, `Remove-Job` can delete custom job types, such as scheduled jobs and workflow jobs.</span></span> <span data-ttu-id="0f8a9-120">Например, `Remove-Job` удаляет запланированное задание, все экземпляры запланированного задания на диске и результаты всех запущенных экземпляров заданий.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-120">For example, `Remove-Job` deletes the scheduled job, all instances of the scheduled job on disk, and the results of all triggered job instances.</span></span>

<span data-ttu-id="0f8a9-121">При попытке удалить выполняющееся задание `Remove-Job` завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-121">If you try to delete a running job, `Remove-Job` fails.</span></span> <span data-ttu-id="0f8a9-122">Используйте `Stop-Job` командлет для завершения выполняющегося задания.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-122">Use the `Stop-Job` cmdlet to stop a running job.</span></span> <span data-ttu-id="0f8a9-123">Или используйте `Remove-Job` с параметром **Force** для удаления выполняющегося задания.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-123">Or, use `Remove-Job` with the **Force** parameter to delete a running job.</span></span>

<span data-ttu-id="0f8a9-124">Задания остаются в глобальном кэше заданий до тех пор, пока не будет удалено фоновое задание или не будет закрыт сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-124">Jobs remain in the global job cache until you delete the background job or close the PowerShell session.</span></span>

## <span data-ttu-id="0f8a9-125">Примеры</span><span class="sxs-lookup"><span data-stu-id="0f8a9-125">EXAMPLES</span></span>

### <span data-ttu-id="0f8a9-126">Пример 1. Удаление задания с использованием его имени</span><span class="sxs-lookup"><span data-stu-id="0f8a9-126">Example 1: Delete a job by using its name</span></span>

<span data-ttu-id="0f8a9-127">В этом примере используется переменная и конвейер для удаления задания по имени.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-127">This example uses a variable and the pipeline to delete a job by name.</span></span>

```powershell
$batch = Get-Job -Name BatchJob
$batch | Remove-Job
```

<span data-ttu-id="0f8a9-128">`Get-Job` использует параметр **Name** для указания задания **батчжоб**.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-128">`Get-Job` uses the **Name** parameter to specify the job, **BatchJob**.</span></span> <span data-ttu-id="0f8a9-129">Объект задания хранится в `$batch` переменной.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-129">The job object is stored in the `$batch` variable.</span></span> <span data-ttu-id="0f8a9-130">Объект в отправляется в `$batch` конвейер в `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="0f8a9-130">The object in `$batch` is sent down the pipeline to `Remove-Job`.</span></span>

<span data-ttu-id="0f8a9-131">Альтернативой является использование параметра **задания** , например `Remove-Job -Job $batch` .</span><span class="sxs-lookup"><span data-stu-id="0f8a9-131">An alternative is to use the **Job** parameter, such as `Remove-Job -Job $batch`.</span></span>

### <span data-ttu-id="0f8a9-132">Пример 2. Удаление всех заданий в сеансе</span><span class="sxs-lookup"><span data-stu-id="0f8a9-132">Example 2: Delete all jobs in a session</span></span>

<span data-ttu-id="0f8a9-133">В этом примере удаляются все задания в текущем сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-133">In this example, all the jobs in the current PowerShell session are deleted.</span></span>

```powershell
Get-job | Remove-Job
```

<span data-ttu-id="0f8a9-134">`Get-Job` Возвращает все задания в текущем сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-134">`Get-Job` gets all the jobs in the current PowerShell session.</span></span> <span data-ttu-id="0f8a9-135">Объекты задания отправляются по конвейеру в `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="0f8a9-135">The job objects are sent down the pipeline to `Remove-Job`.</span></span>

### <span data-ttu-id="0f8a9-136">Пример 3. Удаление заданий NotStarted</span><span class="sxs-lookup"><span data-stu-id="0f8a9-136">Example 3: Delete NotStarted jobs</span></span>

<span data-ttu-id="0f8a9-137">В этом примере удаляются все задания из текущего сеанса PowerShell, который еще не запущен.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-137">This example deletes all jobs from the current PowerShell session that haven't started.</span></span>

```powershell
Remove-Job -State NotStarted
```

<span data-ttu-id="0f8a9-138">`Remove-Job` Задает состояние задания с помощью параметра **State** .</span><span class="sxs-lookup"><span data-stu-id="0f8a9-138">`Remove-Job` uses the **State** parameter to specify the job status.</span></span>

### <span data-ttu-id="0f8a9-139">Пример 4. Удаление заданий с помощью понятного имени</span><span class="sxs-lookup"><span data-stu-id="0f8a9-139">Example 4: Delete jobs by using a friendly name</span></span>

<span data-ttu-id="0f8a9-140">В этом примере удаляются все задания из текущего сеанса с понятными именами, заканчивающимися на \* Batch \* \*, включая выполняемые задания.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-140">This example deletes all jobs from the current session with friendly names that end with \*batch\*\*, including jobs that are running.</span></span>

```powershell
Remove-Job -Name *batch -Force
```

<span data-ttu-id="0f8a9-141">`Remove-Job` использует параметр **Name** для указания шаблона имени задания.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-141">`Remove-Job` uses the **Name** parameter to specify a job name pattern.</span></span> <span data-ttu-id="0f8a9-142">Шаблон содержит `*` подстановочный знак звездочки () для поиска всех имен заданий, заканчивающихся **пакетной** службой.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-142">The pattern includes the asterisk (`*`) wildcard to find all job names that end with **batch**.</span></span> <span data-ttu-id="0f8a9-143">Параметр **Force** удаляет задания, выполняющие.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-143">The **Force** parameter deletes jobs that running.</span></span>

### <span data-ttu-id="0f8a9-144">Пример 5. Удаление задания, созданного с помощью Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="0f8a9-144">Example 5: Delete a job that was created by Invoke-Command</span></span>

<span data-ttu-id="0f8a9-145">В этом примере удаляется задание, запущенное на удаленном компьютере с `Invoke-Command` параметром **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="0f8a9-145">This example removes a job that was started on a remote computer using `Invoke-Command` with the **AsJob** parameter.</span></span>

<span data-ttu-id="0f8a9-146">Так как в примере используется параметр **AsJob** , объект задания создается на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-146">Because the example uses the **AsJob** parameter, the job object is created on the local computer.</span></span>
<span data-ttu-id="0f8a9-147">Но задание выполняется на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-147">But, the job runs on a remote computer.</span></span> <span data-ttu-id="0f8a9-148">Таким образом, для управления заданием можно использовать локальные команды.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-148">As a result, you use local commands to manage the job.</span></span>

```powershell
$job = Invoke-Command -ComputerName Server01 -ScriptBlock {Get-Process} -AsJob
$job | Remove-Job
```

<span data-ttu-id="0f8a9-149">`Invoke-Command` запускает задание на компьютере **Server01** .</span><span class="sxs-lookup"><span data-stu-id="0f8a9-149">`Invoke-Command` runs a job on the **Server01** computer.</span></span> <span data-ttu-id="0f8a9-150">Параметр **AsJob** запускает **ScriptBlock** как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-150">The **AsJob** parameter runs the **ScriptBlock** as a background job.</span></span> <span data-ttu-id="0f8a9-151">Объект задания хранится в `$job` переменной.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-151">The job object is stored in the `$job` variable.</span></span> <span data-ttu-id="0f8a9-152">`$job`Объект переменной отправляется по конвейеру в `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="0f8a9-152">The `$job` variable object is sent down the pipeline to `Remove-Job`.</span></span>

### <span data-ttu-id="0f8a9-153">Пример 6. Удаление задания, созданного с помощью Invoke-Command и Start-Job</span><span class="sxs-lookup"><span data-stu-id="0f8a9-153">Example 6: Delete a job that was created by Invoke-Command and Start-Job</span></span>

<span data-ttu-id="0f8a9-154">В этом примере показано, как удалить задание на удаленном компьютере, запущенном с помощью команды `Invoke-Command` для запуска `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="0f8a9-154">This example shows how to remove a job on a remote computer that was started by using `Invoke-Command` to run `Start-Job`.</span></span> <span data-ttu-id="0f8a9-155">Объект задания создается на удаленном компьютере, а для управления заданием используются удаленные команды.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-155">The job object is created on the remote computer and remote commands are used to manage the job.</span></span> <span data-ttu-id="0f8a9-156">При выполнении удаленной команды требуется постоянное подключение `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="0f8a9-156">A persistent connection is required when running a remote `Start-Job` command.</span></span>

```powershell
$S = New-PSSession -ComputerName Server01
Invoke-Command -Session $S -ScriptBlock {Start-Job -ScriptBlock {Get-Process} -Name MyJob}
Invoke-Command -Session $S -ScriptBlock {Remove-Job -Name MyJob}
```

<span data-ttu-id="0f8a9-157">`New-PSSession`создает на компьютере **Server01** **сеанс PSSession**, постоянное подключение.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-157">`New-PSSession` creates a **PSSession**, a persistent connection, to the **Server01** computer.</span></span> <span data-ttu-id="0f8a9-158">Соединение сохраняется в `$S` переменной.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-158">The connection is saved in the `$S` variable.</span></span>

<span data-ttu-id="0f8a9-159">`Invoke-Command` подключается к сеансу, сохраненному в `$S` .</span><span class="sxs-lookup"><span data-stu-id="0f8a9-159">`Invoke-Command` connects to the session saved in `$S`.</span></span> <span data-ttu-id="0f8a9-160">Блок **ScriptBlock** использует `Start-Job` для запуска удаленного задания.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-160">The **ScriptBlock** uses `Start-Job` to start a remote job.</span></span> <span data-ttu-id="0f8a9-161">Задание выполняет `Get-Process` команду и использует параметр **Name** для указания понятного имени задания **MyJob**.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-161">The job runs a `Get-Process` command and uses the **Name** parameter to specify a friendly job name, **MyJob**.</span></span>

<span data-ttu-id="0f8a9-162">`Invoke-Command` использует `$S` сеанс и выполняется `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="0f8a9-162">`Invoke-Command` uses the `$S` session and runs `Remove-Job`.</span></span> <span data-ttu-id="0f8a9-163">Параметр **Name** указывает, что задание с именем **MyJob** будет удалено.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-163">The **Name** parameter specifies that the job named **MyJob** is deleted.</span></span>

### <span data-ttu-id="0f8a9-164">Пример 7. Удаление задания с помощью InstanceId</span><span class="sxs-lookup"><span data-stu-id="0f8a9-164">Example 7: Delete a job by using its InstanceId</span></span>

<span data-ttu-id="0f8a9-165">В этом примере удаляется задание, основанное на его **InstanceId**.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-165">This example removes a job based on its **InstanceId**.</span></span>

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

<span data-ttu-id="0f8a9-166">`Start-Job` Запускает фоновое задание, а объект задания сохраняется в `$job` переменной.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-166">`Start-Job` starts a background job and the job object is saved in the `$job` variable.</span></span>

<span data-ttu-id="0f8a9-167">Объект в отправляется в `$job` конвейер в `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="0f8a9-167">The object in `$job` is sent down the pipeline to `Format-List`.</span></span> <span data-ttu-id="0f8a9-168">Параметр **Property** использует звездочку ( `*` ), чтобы указать, что все свойства объекта отображаются в списке.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-168">The **Property** parameter uses an asterisk (`*`) to specify that all the object's properties are displayed in a list.</span></span>

<span data-ttu-id="0f8a9-169">`Remove-Job` задает удаляемое задание с помощью параметра **InstanceId** .</span><span class="sxs-lookup"><span data-stu-id="0f8a9-169">`Remove-Job` uses the **InstanceId** parameter to specify the job to delete.</span></span>

## <span data-ttu-id="0f8a9-170">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0f8a9-170">PARAMETERS</span></span>

### <span data-ttu-id="0f8a9-171">-Command</span><span class="sxs-lookup"><span data-stu-id="0f8a9-171">-Command</span></span>

<span data-ttu-id="0f8a9-172">Удаляет задания, в команды которых входят указанные слова.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-172">Deletes jobs that include the specified words in the command.</span></span> <span data-ttu-id="0f8a9-173">Можно ввести разделенный запятыми массив.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-173">You can enter a comma-separated array.</span></span>

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

### <span data-ttu-id="0f8a9-174">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0f8a9-174">-Confirm</span></span>

<span data-ttu-id="0f8a9-175">Запрашивает подтверждение перед `Remove-Job` запуском.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-175">Prompts you for confirmation before `Remove-Job` is run.</span></span>

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

### <span data-ttu-id="0f8a9-176">-Filter</span><span class="sxs-lookup"><span data-stu-id="0f8a9-176">-Filter</span></span>

<span data-ttu-id="0f8a9-177">Удаляет задания, которые соответствуют всем условиям, установленным в связанной хэш-таблице.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-177">Deletes jobs that satisfy all the conditions established in the associated hash table.</span></span> <span data-ttu-id="0f8a9-178">Введите хэш-таблицу, где ключи являются свойствами заданий, а значения — значениями этих свойств.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-178">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="0f8a9-179">Этот параметр работает только с пользовательскими типами заданий, такими как задания рабочих процессов и запланированные задания.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-179">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span> <span data-ttu-id="0f8a9-180">Он не работает со стандартными фоновыми заданиями, такими как созданные с помощью `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="0f8a9-180">It doesn't work on standard background jobs, such as those created by using the `Start-Job`.</span></span>

<span data-ttu-id="0f8a9-181">Этот параметр впервые появился в PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-181">This parameter is introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="0f8a9-182">-Force</span><span class="sxs-lookup"><span data-stu-id="0f8a9-182">-Force</span></span>

<span data-ttu-id="0f8a9-183">Удаляет задание, даже если состояние задания — **работает**.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-183">Deletes a job even if the job's state is **Running**.</span></span> <span data-ttu-id="0f8a9-184">Если параметр **Force** не указан, то `Remove-Job` не удаляет выполняющиеся задания.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-184">If the **Force** parameter isn't specified, `Remove-Job` doesn't delete running jobs.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SessionIdParameterSet, JobParameterSet, InstanceIdParameterSet, NameParameterSet, FilterParameterSet
Aliases: F

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f8a9-185">-Id</span><span class="sxs-lookup"><span data-stu-id="0f8a9-185">-Id</span></span>

<span data-ttu-id="0f8a9-186">Удаляет фоновые задания с указанным **идентификатором**. Можно ввести разделенный запятыми массив.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-186">Deletes background jobs with the specified **Id**. You can enter a comma-separated array.</span></span> <span data-ttu-id="0f8a9-187">**Идентификатор** задания — это уникальное целое число, определяющее задание в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-187">The job's **Id** is a unique integer that identifies a job within the current session.</span></span>

<span data-ttu-id="0f8a9-188">Чтобы найти **идентификатор** задания, используйте `Get-Job` параметр без параметров.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-188">To find a job's **Id**, use `Get-Job` without parameters.</span></span>

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

### <span data-ttu-id="0f8a9-189">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="0f8a9-189">-InstanceId</span></span>

<span data-ttu-id="0f8a9-190">Удаляет задания с указанным **InstanceId**.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-190">Deletes jobs with the specified **InstanceId**.</span></span> <span data-ttu-id="0f8a9-191">Можно ввести разделенный запятыми массив.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-191">You can enter a comma-separated array.</span></span> <span data-ttu-id="0f8a9-192">**InstanceId** — это уникальный идентификатор GUID, определяющий задание.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-192">An **InstanceId** is a unique GUID that identifies a job.</span></span>

<span data-ttu-id="0f8a9-193">Чтобы найти **InstanceId** задания, используйте `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="0f8a9-193">To find a job's **InstanceId**, use `Get-Job`.</span></span>

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

### <span data-ttu-id="0f8a9-194">-Job</span><span class="sxs-lookup"><span data-stu-id="0f8a9-194">-Job</span></span>

<span data-ttu-id="0f8a9-195">Указывает задания, которые требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-195">Specifies the jobs to be deleted.</span></span> <span data-ttu-id="0f8a9-196">Введите переменную, содержащую задания, либо команду, которая их возвращают.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-196">Enter a variable that contains the jobs or a command that gets the jobs.</span></span> <span data-ttu-id="0f8a9-197">Можно ввести разделенный запятыми массив.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-197">You can enter a comma-separated array.</span></span>

<span data-ttu-id="0f8a9-198">Объекты задания можно отправить по конвейеру в `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="0f8a9-198">You can send job objects down the pipeline to `Remove-Job`.</span></span>

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

### <span data-ttu-id="0f8a9-199">-Name</span><span class="sxs-lookup"><span data-stu-id="0f8a9-199">-Name</span></span>

<span data-ttu-id="0f8a9-200">Удаляет только задания с указанным понятным именем.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-200">Only deletes jobs with the specified friendly name.</span></span> <span data-ttu-id="0f8a9-201">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-201">Wildcards are permitted.</span></span> <span data-ttu-id="0f8a9-202">Можно ввести разделенный запятыми массив.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-202">You can enter a comma-separated array.</span></span>

<span data-ttu-id="0f8a9-203">Понятные имена для заданий не обязательно должны быть уникальными даже в рамках сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-203">Friendly names for jobs aren't guaranteed to be unique, even within a PowerShell session.</span></span> <span data-ttu-id="0f8a9-204">Используйте параметры **WhatIf** и **Confirm** при удалении файлов по имени.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-204">Use the **WhatIf** and **Confirm** parameters when you delete files by name.</span></span>

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

### <span data-ttu-id="0f8a9-205">-State</span><span class="sxs-lookup"><span data-stu-id="0f8a9-205">-State</span></span>

<span data-ttu-id="0f8a9-206">Удаляет только задания с указанным состоянием.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-206">Only deletes jobs with the specified state.</span></span> <span data-ttu-id="0f8a9-207">Чтобы удалить задания с состоянием **работает**, используйте параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="0f8a9-207">To delete jobs with a state of **Running**, use the **Force** parameter.</span></span>

<span data-ttu-id="0f8a9-208">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="0f8a9-208">Accepted values:</span></span>

- <span data-ttu-id="0f8a9-209">AtBreakpoint</span><span class="sxs-lookup"><span data-stu-id="0f8a9-209">AtBreakpoint</span></span>
- <span data-ttu-id="0f8a9-210">Блокировано</span><span class="sxs-lookup"><span data-stu-id="0f8a9-210">Blocked</span></span>
- <span data-ttu-id="0f8a9-211">Завершено</span><span class="sxs-lookup"><span data-stu-id="0f8a9-211">Completed</span></span>
- <span data-ttu-id="0f8a9-212">Отключено</span><span class="sxs-lookup"><span data-stu-id="0f8a9-212">Disconnected</span></span>
- <span data-ttu-id="0f8a9-213">Failed</span><span class="sxs-lookup"><span data-stu-id="0f8a9-213">Failed</span></span>
- <span data-ttu-id="0f8a9-214">NotStarted</span><span class="sxs-lookup"><span data-stu-id="0f8a9-214">NotStarted</span></span>
- <span data-ttu-id="0f8a9-215">Запущен</span><span class="sxs-lookup"><span data-stu-id="0f8a9-215">Running</span></span>
- <span data-ttu-id="0f8a9-216">Остановлена</span><span class="sxs-lookup"><span data-stu-id="0f8a9-216">Stopped</span></span>
- <span data-ttu-id="0f8a9-217">Остановка</span><span class="sxs-lookup"><span data-stu-id="0f8a9-217">Stopping</span></span>
- <span data-ttu-id="0f8a9-218">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="0f8a9-218">Suspended</span></span>
- <span data-ttu-id="0f8a9-219">Приостановка</span><span class="sxs-lookup"><span data-stu-id="0f8a9-219">Suspending</span></span>

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

### <span data-ttu-id="0f8a9-220">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0f8a9-220">-WhatIf</span></span>

<span data-ttu-id="0f8a9-221">Показывает, что произойдет при `Remove-Job` запуске.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-221">Shows what would happen if `Remove-Job` runs.</span></span> <span data-ttu-id="0f8a9-222">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-222">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="0f8a9-223">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="0f8a9-223">CommonParameters</span></span>

<span data-ttu-id="0f8a9-224">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-224">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0f8a9-225">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0f8a9-225">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0f8a9-226">Входные данные</span><span class="sxs-lookup"><span data-stu-id="0f8a9-226">INPUTS</span></span>

### <span data-ttu-id="0f8a9-227">System. Management. Automation. job</span><span class="sxs-lookup"><span data-stu-id="0f8a9-227">System.Management.Automation.Job</span></span>

<span data-ttu-id="0f8a9-228">Объект задания можно отправить по конвейеру в `Remove-Job` .</span><span class="sxs-lookup"><span data-stu-id="0f8a9-228">You can send a job object down the pipeline to `Remove-Job`.</span></span>

## <span data-ttu-id="0f8a9-229">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="0f8a9-229">OUTPUTS</span></span>

### <span data-ttu-id="0f8a9-230">None</span><span class="sxs-lookup"><span data-stu-id="0f8a9-230">None</span></span>

<span data-ttu-id="0f8a9-231">`Remove-Job` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-231">`Remove-Job` doesn't generate any output.</span></span>

## <span data-ttu-id="0f8a9-232">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="0f8a9-232">NOTES</span></span>

<span data-ttu-id="0f8a9-233">Задание PowerShell создает новый процесс.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-233">A PowerShell job creates a new process.</span></span> <span data-ttu-id="0f8a9-234">После завершения задания процесс завершается.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-234">When the job completes, the process exits.</span></span> <span data-ttu-id="0f8a9-235">При `Remove-Job` запуске состояние задания удаляется.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-235">When `Remove-Job` is run, the job's state is removed.</span></span>

<span data-ttu-id="0f8a9-236">Если задание останавливается до завершения и его процесс не завершается, процесс принудительно завершается.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-236">If a job stops before completion and its process hasn't exited, the process is forcibly terminated.</span></span>

## <span data-ttu-id="0f8a9-237">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="0f8a9-237">RELATED LINKS</span></span>

[<span data-ttu-id="0f8a9-238">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="0f8a9-238">about_Jobs</span></span>](./About/about_Jobs.md)

[<span data-ttu-id="0f8a9-239">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="0f8a9-239">about_Job_Details</span></span>](./About/about_Job_Details.md)

[<span data-ttu-id="0f8a9-240">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="0f8a9-240">about_Remote_Jobs</span></span>](./About/about_Remote_Jobs.md)

[<span data-ttu-id="0f8a9-241">Get-Job.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-241">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="0f8a9-242">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="0f8a9-242">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="0f8a9-243">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-243">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="0f8a9-244">Start-Job</span><span class="sxs-lookup"><span data-stu-id="0f8a9-244">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="0f8a9-245">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="0f8a9-245">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="0f8a9-246">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="0f8a9-246">Wait-Job</span></span>](Wait-Job.md)

