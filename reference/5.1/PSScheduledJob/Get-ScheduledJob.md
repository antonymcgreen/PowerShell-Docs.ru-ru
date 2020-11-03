---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/get-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ScheduledJob
ms.openlocfilehash: 40224432c208ee45efc20f556312fa250e9bb7a6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227382"
---
# <span data-ttu-id="9176d-103">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="9176d-103">Get-ScheduledJob</span></span>

## <span data-ttu-id="9176d-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="9176d-104">SYNOPSIS</span></span>
<span data-ttu-id="9176d-105">Получает запланированные задания на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="9176d-105">Gets scheduled jobs on the local computer.</span></span>

## <span data-ttu-id="9176d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9176d-106">SYNTAX</span></span>

### <span data-ttu-id="9176d-107">DefinitionId (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="9176d-107">DefinitionId (Default)</span></span>

```
Get-ScheduledJob [[-Id] <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="9176d-108">DefinitionName</span><span class="sxs-lookup"><span data-stu-id="9176d-108">DefinitionName</span></span>

```
Get-ScheduledJob [-Name] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="9176d-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9176d-109">DESCRIPTION</span></span>
<span data-ttu-id="9176d-110">Командлет **Get-ScheduledJob** возвращает запланированные задания на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="9176d-110">The **Get-ScheduledJob** cmdlet gets scheduled jobs on the local computer.</span></span>
<span data-ttu-id="9176d-111">**Get-ScheduledJob** возвращает только запланированные задания, созданные текущим пользователем с помощью командлета Register-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="9176d-111">**Get-ScheduledJob** gets only scheduled jobs that are created by the current user using the Register-ScheduledJob cmdlet.</span></span>

<span data-ttu-id="9176d-112">Хотя задания, созданные с помощью командлета **Register-ScheduledJob** , отображаются в планировщике заданий, **Get-ScheduledJob** возвращает только запланированные задания.</span><span class="sxs-lookup"><span data-stu-id="9176d-112">Although jobs that are created by using the **Register-ScheduledJob** cmdlet appear in Task Scheduler, **Get-ScheduledJob** gets only scheduled jobs.</span></span>
<span data-ttu-id="9176d-113">Он не возвращает запланированные задачи, созданные в планировщике.</span><span class="sxs-lookup"><span data-stu-id="9176d-113">It does not get scheduled tasks created in Task Scheduler.</span></span>

<span data-ttu-id="9176d-114">Без параметров **Get-ScheduledJob** возвращает все запланированные задания на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9176d-114">Without parameters, **Get-ScheduledJob** gets all scheduled jobs on the computer.</span></span>
<span data-ttu-id="9176d-115">Можно использовать параметры командлета **Get-ScheduledJob** для получения запланированных заданий по идентификатору или имени и проверять их или передавать в другие командлеты.</span><span class="sxs-lookup"><span data-stu-id="9176d-115">You can use the parameters of **Get-ScheduledJob** to get scheduled jobs by ID or name and examine them or pipe them to other cmdlets.</span></span>

<span data-ttu-id="9176d-116">**Get-ScheduledJob** — это одна из коллекций командлетов планирования заданий в модуле **PSScheduledJob** , который входит в состав Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9176d-116">**Get-ScheduledJob** is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="9176d-117">Дополнительные сведения о запланированных заданиях см. в разделах описания в модуле PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="9176d-117">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="9176d-118">Импортируйте модуль PSScheduledJob, а затем введите `Get-Help about_Scheduled*` или просмотрите статью about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="9176d-118">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="9176d-119">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="9176d-119">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="9176d-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="9176d-120">EXAMPLES</span></span>

### <span data-ttu-id="9176d-121">Пример 1. получение всех запланированных заданий</span><span class="sxs-lookup"><span data-stu-id="9176d-121">Example 1: Get all scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob
```

<span data-ttu-id="9176d-122">Эта команда возвращает все запланированные задания на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="9176d-122">This command gets all scheduled jobs on the local computer.</span></span>

### <span data-ttu-id="9176d-123">Пример 2. Получение запланированных заданий по имени</span><span class="sxs-lookup"><span data-stu-id="9176d-123">Example 2: Get scheduled jobs by name</span></span>

```
PS C:\> Get-ScheduledJob -Name *Backup*, *Archive*
```

<span data-ttu-id="9176d-124">Эта команда возвращает все запланированные задания на компьютере, имена которых содержат резервную копию или Архив.</span><span class="sxs-lookup"><span data-stu-id="9176d-124">This command gets all scheduled jobs on the computer that have names that include Backup or Archive.</span></span>
<span data-ttu-id="9176d-125">Формат этой команды позволяет искать определенные задания.</span><span class="sxs-lookup"><span data-stu-id="9176d-125">This command format lets you search for particular jobs.</span></span>

### <span data-ttu-id="9176d-126">Пример 3. Получение запланированных заданий на удаленных компьютерах</span><span class="sxs-lookup"><span data-stu-id="9176d-126">Example 3: Get scheduled jobs on remote computers</span></span>

```
PS C:\> Invoke-Command -ComputerName (Get-Content Servers.txt) {Get-ScheduledJob}
```

<span data-ttu-id="9176d-127">Эта команда возвращает все запланированные задания на компьютерах, которые указаны в файле Servers.txt.</span><span class="sxs-lookup"><span data-stu-id="9176d-127">This command gets all scheduled jobs on the computers that are listed in the Servers.txt file.</span></span>
<span data-ttu-id="9176d-128">Команда использует командлет Invoke-Command для выполнения команды **Get-ScheduleJob** на каждом компьютере.</span><span class="sxs-lookup"><span data-stu-id="9176d-128">The command uses the Invoke-Command cmdlet to run a **Get-ScheduleJob** command on each computer.</span></span>

### <span data-ttu-id="9176d-129">Пример 4. Передача запланированных заданий по конвейеру другим командлетам</span><span class="sxs-lookup"><span data-stu-id="9176d-129">Example 4: Pipe scheduled jobs to other cmdlets</span></span>

```
PS C:\> Get-ScheduledJob DailyBackup, WeeklyBackup | Get-JobTrigger
```

<span data-ttu-id="9176d-130">Эта команда получает триггеры задания для запланированных заданий DailyBackup и WeeklyBackup.</span><span class="sxs-lookup"><span data-stu-id="9176d-130">This command gets the job triggers of the DailyBackup and WeeklyBackup scheduled jobs.</span></span>
<span data-ttu-id="9176d-131">Он использует командлет **Get-ScheduledJob** для получения запланированных заданий и командлет Get-JobTrigger для получения триггеров заданий запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="9176d-131">It uses the **Get-ScheduledJob** cmdlet to get the scheduled jobs and the Get-JobTrigger cmdlet to get the job triggers of the scheduled jobs.</span></span>

## <span data-ttu-id="9176d-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9176d-132">PARAMETERS</span></span>

### <span data-ttu-id="9176d-133">-Id</span><span class="sxs-lookup"><span data-stu-id="9176d-133">-Id</span></span>
<span data-ttu-id="9176d-134">Возвращает только запланированные задания с указанным идентификационным номером (идентификатором).</span><span class="sxs-lookup"><span data-stu-id="9176d-134">Gets only the scheduled jobs with the specified identification number (ID).</span></span>
<span data-ttu-id="9176d-135">Введите один или несколько идентификаторов запланированных заданий на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9176d-135">Enter one or more IDs of scheduled jobs on the computer.</span></span>
<span data-ttu-id="9176d-136">По умолчанию **Get-ScheduledJob** возвращает все запланированные задания на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9176d-136">By default, **Get-ScheduledJob** gets all scheduled jobs on the computer.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: DefinitionId
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9176d-137">-Name</span><span class="sxs-lookup"><span data-stu-id="9176d-137">-Name</span></span>
<span data-ttu-id="9176d-138">Возвращает только запланированные задания с указанными именами.</span><span class="sxs-lookup"><span data-stu-id="9176d-138">Gets only the scheduled jobs with the specified names.</span></span>
<span data-ttu-id="9176d-139">Введите одно или несколько имен запланированных заданий на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9176d-139">Enter one or more names of scheduled jobs on the computer.</span></span>
<span data-ttu-id="9176d-140">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="9176d-140">Wildcards are supported.</span></span>
<span data-ttu-id="9176d-141">По умолчанию **Get-ScheduledJob** возвращает все запланированные задания на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9176d-141">By default, **Get-ScheduledJob** gets all scheduled jobs on the computer.</span></span>

```yaml
Type: System.String[]
Parameter Sets: DefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9176d-142">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="9176d-142">CommonParameters</span></span>
<span data-ttu-id="9176d-143">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9176d-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9176d-144">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9176d-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9176d-145">Входные данные</span><span class="sxs-lookup"><span data-stu-id="9176d-145">INPUTS</span></span>

### <span data-ttu-id="9176d-146">Нет</span><span class="sxs-lookup"><span data-stu-id="9176d-146">None</span></span>
<span data-ttu-id="9176d-147">Нельзя передать входные данные в командлет **Get-ScheduledJob** с помощью конвейера.</span><span class="sxs-lookup"><span data-stu-id="9176d-147">You cannot pipe input to **Get-ScheduledJob** .</span></span>

## <span data-ttu-id="9176d-148">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="9176d-148">OUTPUTS</span></span>

### <span data-ttu-id="9176d-149">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="9176d-149">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>

## <span data-ttu-id="9176d-150">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="9176d-150">NOTES</span></span>

* <span data-ttu-id="9176d-151">Каждое запланированное задание сохраняется в подкаталоге каталога $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="9176d-151">Each scheduled job is saved in a subdirectory of the $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs directory on the local computer.</span></span> <span data-ttu-id="9176d-152">Этот подкаталог назван по имени запланированного задания и содержит XML-файл для этого задания и записи его журнала выполнения.</span><span class="sxs-lookup"><span data-stu-id="9176d-152">The subdirectory is named for the scheduled job and contains the XML file for the scheduled job and records of its execution history.</span></span> <span data-ttu-id="9176d-153">Дополнительные сведения о запланированных заданиях на диске см. в описании about_Scheduled_Jobs_Advanced.</span><span class="sxs-lookup"><span data-stu-id="9176d-153">For more information about scheduled jobs on disk, see about_Scheduled_Jobs_Advanced.</span></span>
* <span data-ttu-id="9176d-154">Запланированные задания, созданные в Windows PowerShell, отображаются в планировщике заданий в папке "Библиотека планировщика заданий\Microsoft\Windows\PowerShell\ScheduledJobs".</span><span class="sxs-lookup"><span data-stu-id="9176d-154">Scheduled jobs that you create in Windows PowerShell appear in Task Scheduler in the Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs folder.</span></span> <span data-ttu-id="9176d-155">Планировщик заданий можно использовать для просмотра и изменения запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="9176d-155">You can use Task Scheduler to view and edit the scheduled job.</span></span>
* <span data-ttu-id="9176d-156">Планировщик заданий, средство командной строки SchTasks.exe и командлеты планировщика заданий можно использовать для управления запланированными заданиями, созданные с помощью командлетов запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="9176d-156">You can use Task Scheduler, the SchTasks.exe command-line tool, and the Task Scheduler cmdlets to manage scheduled jobs that you create with the Scheduled Job cmdlets.</span></span> <span data-ttu-id="9176d-157">Однако нельзя использовать командлеты запланированных заданий для управления задачами, созданными в планировщике заданий.</span><span class="sxs-lookup"><span data-stu-id="9176d-157">However, you cannot use the Scheduled Job cmdlets to manage tasks that you create in Task Scheduler.</span></span>

## <span data-ttu-id="9176d-158">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="9176d-158">RELATED LINKS</span></span>

[<span data-ttu-id="9176d-159">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="9176d-159">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="9176d-160">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="9176d-160">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="9176d-161">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="9176d-161">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="9176d-162">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="9176d-162">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="9176d-163">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="9176d-163">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="9176d-164">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="9176d-164">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="9176d-165">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="9176d-165">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="9176d-166">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="9176d-166">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="9176d-167">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="9176d-167">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="9176d-168">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="9176d-168">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="9176d-169">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="9176d-169">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="9176d-170">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="9176d-170">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="9176d-171">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="9176d-171">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="9176d-172">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="9176d-172">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="9176d-173">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="9176d-173">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="9176d-174">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="9176d-174">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
