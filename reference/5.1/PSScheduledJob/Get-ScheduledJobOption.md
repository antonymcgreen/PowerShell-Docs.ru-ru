---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/get-scheduledjoboption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ScheduledJobOption
ms.openlocfilehash: 5c317be9add0898137aceed6c39032f3e271bac1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227378"
---
# <span data-ttu-id="dc3d4-103">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="dc3d4-103">Get-ScheduledJobOption</span></span>

## <span data-ttu-id="dc3d4-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="dc3d4-104">SYNOPSIS</span></span>
<span data-ttu-id="dc3d4-105">Получает параметры задания для запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-105">Gets the job options of scheduled jobs.</span></span>

## <span data-ttu-id="dc3d4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dc3d4-106">SYNTAX</span></span>

### <span data-ttu-id="dc3d4-107">JobDefinition (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="dc3d4-107">JobDefinition (Default)</span></span>

```
Get-ScheduledJobOption [-InputObject] <ScheduledJobDefinition> [<CommonParameters>]
```

### <span data-ttu-id="dc3d4-108">жобдефинитионид</span><span class="sxs-lookup"><span data-stu-id="dc3d4-108">JobDefinitionId</span></span>

```
Get-ScheduledJobOption [-Id] <Int32> [<CommonParameters>]
```

### <span data-ttu-id="dc3d4-109">жобдефинитионнаме</span><span class="sxs-lookup"><span data-stu-id="dc3d4-109">JobDefinitionName</span></span>

```
Get-ScheduledJobOption [-Name] <String> [<CommonParameters>]
```

## <span data-ttu-id="dc3d4-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="dc3d4-110">DESCRIPTION</span></span>
<span data-ttu-id="dc3d4-111">Командлет **Get-scheduledjoboptions** Возвращает параметры задания для запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-111">The **Get-ScheduledJobOption** cmdlet gets the job options of scheduled jobs.</span></span>
<span data-ttu-id="dc3d4-112">Эта команда используется для проверки параметров задания или их передачи в другие командлеты.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-112">You can use this command to examine the job options or to pipe the job options to other cmdlets.</span></span>

<span data-ttu-id="dc3d4-113">Параметры задания не сохраняются на диск независимо; они являются частью запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-113">Job options are not saved to disk independently; they are part of a scheduled job.</span></span>
<span data-ttu-id="dc3d4-114">Чтобы получить параметры запланированного задания, укажите это запланированное задание.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-114">To get the job options of a scheduled job, specify the scheduled job.</span></span>

<span data-ttu-id="dc3d4-115">Используйте параметры командлета **Get-ScheduledJobOption** , чтобы определить запланированное задание.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-115">Use the parameters of the **Get-ScheduledJobOption** cmdlet to identify the scheduled job.</span></span>
<span data-ttu-id="dc3d4-116">Запланированные задания можно определить по их именам или идентификационным номерам либо путем ввода или передачи объектов **ScheduledJob** , например, возвращаемых командлетом Get-ScheduledJob, в **Get-scheduledjoboptions** .</span><span class="sxs-lookup"><span data-stu-id="dc3d4-116">You can identify scheduled jobs by their names or identification numbers, or by entering or piping **ScheduledJob** objects, such as those that are returned by the Get-ScheduledJob cmdlet, to **Get-ScheduledJobOption** .</span></span>

<span data-ttu-id="dc3d4-117">**Get-scheduledjoboptions** — это одна из коллекций командлетов планирования заданий в модуле PSScheduledJob, который входит в состав Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-117">**Get-ScheduledJobOption** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="dc3d4-118">Дополнительные сведения о запланированных заданиях см. в разделах описания в модуле PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-118">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="dc3d4-119">Импортируйте модуль PSScheduledJob, а затем введите `Get-Help about_Scheduled*` или просмотрите статью about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-119">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="dc3d4-120">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-120">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="dc3d4-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="dc3d4-121">EXAMPLES</span></span>

### <span data-ttu-id="dc3d4-122">Пример 1. получение параметров задания</span><span class="sxs-lookup"><span data-stu-id="dc3d4-122">Example 1: Get job options</span></span>

```
PS C:\> Get-ScheduledJobOption -Name "*Backup*"
StartIfOnBatteries     : False

StopIfGoingOnBatteries : True

WakeToRun              : False

StartIfNotIdle         : True

StopIfGoingOffIdle     : False

RestartOnIdleResume    : False

IdleDuration           : 00:10:00

IdleTimeout            : 01:00:00

ShowInTaskScheduler    : True

RunElevated            : True

RunWithoutNetwork      : True

DoNotAllowDemandStart  : False

MultipleInstancePolicy : Ignore

NewJobDefinition       : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

<span data-ttu-id="dc3d4-123">Эта команда возвращает параметры задания для запланированных заданий, в именах которых есть резервная копия.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-123">This command gets the job options of scheduled jobs that have BackUp in their names.</span></span>
<span data-ttu-id="dc3d4-124">В результатах показан возвращенный **Get-ScheduledJobOption** объект параметров задания.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-124">The results show the job options object that **Get-ScheduledJobOption** returned.</span></span>

### <span data-ttu-id="dc3d4-125">Пример 2. получение всех параметров задания</span><span class="sxs-lookup"><span data-stu-id="dc3d4-125">Example 2: Get all job options</span></span>

```
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption
```

<span data-ttu-id="dc3d4-126">Эта команда возвращает параметры задания для всех запланированных заданий на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-126">This command gets the job options of all scheduled jobs on the local computer.</span></span>

<span data-ttu-id="dc3d4-127">Он использует командлет Get-ScheduledJob для получения запланированных заданий на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-127">It uses the Get-ScheduledJob cmdlet to get the scheduled jobs on the local computer.</span></span>
<span data-ttu-id="dc3d4-128">Оператор конвейера (|) отправляет запланированные задания в командлет **Get-scheduledjoboptions** , который получает параметры задания для каждого запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-128">A pipeline operator (|) sends the scheduled jobs to the **Get-ScheduledJobOption** cmdlet, which gets the job options of each scheduled job.</span></span>

### <span data-ttu-id="dc3d4-129">Пример 3. Получение выбранных параметров задания</span><span class="sxs-lookup"><span data-stu-id="dc3d4-129">Example 3: Get selected job options</span></span>

```
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption | Where {$_.RunElevated -and !$_.WaketoRun}
StartIfOnBatteries     : False

StopIfGoingOnBatteries : True

WakeToRun              : True

StartIfNotIdle         : True

StopIfGoingOffIdle     : False

RestartOnIdleResume    : False

IdleDuration           : 00:10:00

IdleTimeout            : 01:00:00

ShowInTaskScheduler    : True

RunElevated            : True

RunWithoutNetwork      : True

DoNotAllowDemandStart  : False

MultipleInstancePolicy : Ignore

NewJobDefinition       : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition

The second command shows how to find to which scheduled job the job options belong. This command uses a pipeline operator (|) to send the selected job options to the ForEach-Object cmdlet, which gets the JobDefinition property of each options object. The JobDefinition property contains the originating job object. The results show that the selected options came from the DeployPkg scheduled job.
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption | Where {$_.RunElevated -and !$_.WaketoRun} | ForEach-Object {$_.JobDefinition}
Id         Name            Triggers        Command                                  Enabled

--         ----            --------        -------                                  -------

2          DeployPkg         {1, 2}        DeployPackage.ps1                        True
```

<span data-ttu-id="dc3d4-130">В этом примере показано, как найти объект параметров задания с определенными значениями.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-130">This example shows how to find job options object with particular values.</span></span>

<span data-ttu-id="dc3d4-131">Первая команда получает параметры задания, в которых свойство RunElevated имеет значение $True а свойство Рунвисаутнетворк имеет значение $False.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-131">The first command gets job options in which the RunElevated property has a value of $True and the RunWithoutNetwork property has a value of $False.</span></span>
<span data-ttu-id="dc3d4-132">В выходных данных отображается выбранный объект **жобоптионс** .</span><span class="sxs-lookup"><span data-stu-id="dc3d4-132">The output shows the **JobOptions** object that was selected.</span></span>

### <span data-ttu-id="dc3d4-133">Пример 4. Использование параметров задания для создания нового задания</span><span class="sxs-lookup"><span data-stu-id="dc3d4-133">Example 4: Use job options to create a new job</span></span>

```
PS C:\> $Opts = Get-ScheduledJobOption -Name "BackupTestLogs"
PS C:\> Register-ScheduledJob -Name "Archive-Scripts" -FilePath "\\Srv01\Scripts\ArchiveScripts.ps1" -ScheduledJobOption $Opts
```

<span data-ttu-id="dc3d4-134">В этом примере показано, как использовать параметры задания, которые Get-ScheduledJobOption получаются в новом запланированном задании.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-134">This example shows how to use the job options that Get-ScheduledJobOption gets in a new scheduled job.</span></span>

<span data-ttu-id="dc3d4-135">Первая команда использует **Get-scheduledjoboptions** для получения параметров заданий запланированного задания баккуптестлогс.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-135">The first command uses **Get-ScheduledJobOption** to get the jobs options of the BackupTestLogs scheduled job.</span></span>
<span data-ttu-id="dc3d4-136">Команда сохраняет эти параметры в переменной $Opts.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-136">The command saves the options in the $Opts variable.</span></span>

<span data-ttu-id="dc3d4-137">Вторая команда использует командлет Register-ScheduledJob для создания нового запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-137">The second command uses Register-ScheduledJob cmdlet to create a new scheduled job.</span></span>
<span data-ttu-id="dc3d4-138">Значение параметра *ScheduledJobOption* представляет собой объект параметров в переменной $Opts.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-138">The value of the *ScheduledJobOption* parameter is the options object in the $Opts variable.</span></span>

### <span data-ttu-id="dc3d4-139">Пример 5. получение параметров задания с удаленного компьютера</span><span class="sxs-lookup"><span data-stu-id="dc3d4-139">Example 5: Get job options from a remote computer</span></span>

```
PS C:\> $O = Invoke-Command -ComputerName "Srv01" -ScriptBlock {Get-ScheduledJob -Name "DataDemon" }
```

<span data-ttu-id="dc3d4-140">Эта команда использует командлет Invoke-Command для получения параметров запланированного задания задания Датадемон на компьютере SRV01.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-140">This command uses the Invoke-Command cmdlet to get the scheduled job options of the DataDemon job on the Srv01 computer.</span></span>
<span data-ttu-id="dc3d4-141">Команда сохраняет параметры в переменной $O.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-141">The command saves the options in the $O variable.</span></span>

## <span data-ttu-id="dc3d4-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dc3d4-142">PARAMETERS</span></span>

### <span data-ttu-id="dc3d4-143">-Id</span><span class="sxs-lookup"><span data-stu-id="dc3d4-143">-Id</span></span>
<span data-ttu-id="dc3d4-144">Задает идентификационный номер запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-144">Specifies the identification number of a scheduled job.</span></span>
<span data-ttu-id="dc3d4-145">**Get-ScheduledJobOption** получает параметры указанного запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-145">**Get-ScheduledJobOption** gets the job options of the specified scheduled job.</span></span>

<span data-ttu-id="dc3d4-146">Чтобы получить идентификационные номера запланированных заданий на локальном или удаленном компьютере, используйте командлет Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-146">To get the identification numbers of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

```yaml
Type: System.Int32
Parameter Sets: JobDefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dc3d4-147">-InputObject</span><span class="sxs-lookup"><span data-stu-id="dc3d4-147">-InputObject</span></span>
<span data-ttu-id="dc3d4-148">Указывает запланированное задание.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-148">Specifies a scheduled job.</span></span>
<span data-ttu-id="dc3d4-149">Введите переменную, содержащую объект **ScheduledJob** , или введите команду или выражение, которое получает объект **ScheduledJob** , например команду Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-149">Enter a variable that contains a **ScheduledJob** object or type a command or expression that gets a **ScheduledJob** object, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="dc3d4-150">Можно также передать объект **ScheduledJob** в **Get-ScheduledJobOption** .</span><span class="sxs-lookup"><span data-stu-id="dc3d4-150">You can also pipe a **ScheduledJob** object to **Get-ScheduledJobOption** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: JobDefinition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="dc3d4-151">-Name</span><span class="sxs-lookup"><span data-stu-id="dc3d4-151">-Name</span></span>
<span data-ttu-id="dc3d4-152">Задает имена запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-152">Specifies the names of scheduled jobs.</span></span>
<span data-ttu-id="dc3d4-153">**Get-ScheduledJobOption** получает параметры указанного запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-153">**Get-ScheduledJobOption** gets the job options of the specified scheduled job.</span></span>
<span data-ttu-id="dc3d4-154">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-154">Wildcards are supported.</span></span>

<span data-ttu-id="dc3d4-155">Чтобы получить имена запланированных заданий на локальном или удаленном компьютере, используйте командлет Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-155">To get the names of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="dc3d4-156">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="dc3d4-156">CommonParameters</span></span>
<span data-ttu-id="dc3d4-157">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="dc3d4-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dc3d4-158">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="dc3d4-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="dc3d4-159">Входные данные</span><span class="sxs-lookup"><span data-stu-id="dc3d4-159">INPUTS</span></span>

### <span data-ttu-id="dc3d4-160">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="dc3d4-160">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="dc3d4-161">Вы можете передать запланированное задание из Get-ScheduledJob в командлет **Get-scheduledjoboptions** .</span><span class="sxs-lookup"><span data-stu-id="dc3d4-161">You can pipe a scheduled job from Get-ScheduledJob to **Get-ScheduledJobOption** .</span></span>

## <span data-ttu-id="dc3d4-162">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="dc3d4-162">OUTPUTS</span></span>

### <span data-ttu-id="dc3d4-163">Microsoft. PowerShell. ScheduledJob. Счедуледжобоптионс</span><span class="sxs-lookup"><span data-stu-id="dc3d4-163">Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions</span></span>

## <span data-ttu-id="dc3d4-164">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="dc3d4-164">NOTES</span></span>

## <span data-ttu-id="dc3d4-165">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="dc3d4-165">RELATED LINKS</span></span>

[<span data-ttu-id="dc3d4-166">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="dc3d4-166">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="dc3d4-167">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="dc3d4-167">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="dc3d4-168">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="dc3d4-168">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="dc3d4-169">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="dc3d4-169">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="dc3d4-170">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="dc3d4-170">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="dc3d4-171">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="dc3d4-171">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="dc3d4-172">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="dc3d4-172">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="dc3d4-173">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="dc3d4-173">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="dc3d4-174">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="dc3d4-174">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="dc3d4-175">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="dc3d4-175">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="dc3d4-176">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="dc3d4-176">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="dc3d4-177">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="dc3d4-177">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="dc3d4-178">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="dc3d4-178">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="dc3d4-179">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="dc3d4-179">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="dc3d4-180">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="dc3d4-180">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="dc3d4-181">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="dc3d4-181">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
