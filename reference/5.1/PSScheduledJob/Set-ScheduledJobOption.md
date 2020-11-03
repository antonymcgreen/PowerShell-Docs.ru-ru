---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/set-scheduledjoboption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ScheduledJobOption
ms.openlocfilehash: 6647e9ba4e2ee49afa90dd382573d437d2deaee6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227353"
---
# <span data-ttu-id="28957-103">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="28957-103">Set-ScheduledJobOption</span></span>

## <span data-ttu-id="28957-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="28957-104">SYNOPSIS</span></span>
<span data-ttu-id="28957-105">Изменяет параметры задания для запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="28957-105">Changes the job options of a scheduled job.</span></span>

## <span data-ttu-id="28957-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="28957-106">SYNTAX</span></span>

```
Set-ScheduledJobOption [-InputObject] <ScheduledJobOptions> [-PassThru] [-RunElevated] [-HideInTaskScheduler]
 [-RestartOnIdleResume] [-MultipleInstancePolicy <TaskMultipleInstancePolicy>] [-DoNotAllowDemandStart]
 [-RequireNetwork] [-StopIfGoingOffIdle] [-WakeToRun] [-ContinueIfGoingOnBattery] [-StartIfOnBattery]
 [-IdleTimeout <TimeSpan>] [-IdleDuration <TimeSpan>] [-StartIfIdle] [<CommonParameters>]
```

## <span data-ttu-id="28957-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="28957-107">DESCRIPTION</span></span>
<span data-ttu-id="28957-108">Командлет **Set-ScheduledJobOptions** изменяет параметры задания для запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="28957-108">The **Set-ScheduledJobOptions** cmdlet changes the job options of scheduled jobs.</span></span>

<span data-ttu-id="28957-109">Чтобы изменить параметры запланированного задания, начните с использования командлета Get-ScheduledJobOption, чтобы получить параметры задания для запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="28957-109">To change the options of a scheduled job, begin by using the Get-ScheduledJobOption cmdlet to get the job options of a scheduled job.</span></span>
<span data-ttu-id="28957-110">Затем передайте параметры в **Set-ScheduledJobOption** или сохраните их  в переменной и используйте параметр *InputObject* командлета **Set-ScheduledJobOption** для идентификации параметров.</span><span class="sxs-lookup"><span data-stu-id="28957-110">Then, pipe the options to **Set-ScheduledJobOption** or save the options in a variable and use the *InputObject* parameter of **Set-ScheduledJobOption** cmdlet to identify the options.</span></span>
<span data-ttu-id="28957-111">Используйте остальные параметры **Set-ScheduledJobOption** для изменения параметров задания.</span><span class="sxs-lookup"><span data-stu-id="28957-111">Use the remaining parameters of **Set-ScheduledJobOption** to change the job options.</span></span>

<span data-ttu-id="28957-112">Чтобы включить параметр задания, используйте параметр, который задает соответствующий параметр.</span><span class="sxs-lookup"><span data-stu-id="28957-112">To turn on a job option, use the parameter that sets that option.</span></span>
<span data-ttu-id="28957-113">Чтобы отключить параметр, введите имя параметра, двоеточие (:) и $False.</span><span class="sxs-lookup"><span data-stu-id="28957-113">To turn off an option, type the parameter name, a colon (:), and $False.</span></span>
<span data-ttu-id="28957-114">Например, чтобы отключить параметр *RunElevated* , введите `-RunElevated:$False` .</span><span class="sxs-lookup"><span data-stu-id="28957-114">For example, to turn off the *RunElevated* option, type `-RunElevated:$False`.</span></span>

<span data-ttu-id="28957-115">Каждый объект параметров задания имеет свойство JobDefinition, содержащее запланированное задание, поэтому при изменении параметров задания связь с запланированным заданием сохраняется.</span><span class="sxs-lookup"><span data-stu-id="28957-115">Each job options object includes a JobDefinition property that contains the scheduled job, so the association with the scheduled job is retained when the job options are changed.</span></span>

<span data-ttu-id="28957-116">Параметры запланированного задания определяют, как задание выполняется в случае запуска планировщиком.</span><span class="sxs-lookup"><span data-stu-id="28957-116">The scheduled job options determine how the job runs when it is started by Task Scheduler.</span></span>
<span data-ttu-id="28957-117">Эти параметры не применяются при использовании командлета Start-Job для запуска запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="28957-117">These options to not apply when you use the Start-Job cmdlet to start a scheduled job.</span></span>

<span data-ttu-id="28957-118">**Set-scheduledjoboptions** — это одна из коллекций командлетов планирования заданий в модуле PSScheduledJob, который входит в состав Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28957-118">**Set-ScheduledJobOption** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="28957-119">Дополнительные сведения о запланированных заданиях см. в разделах описания в модуле PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="28957-119">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="28957-120">Импортируйте модуль PSScheduledJob, а затем введите `Get-Help about_Scheduled*` или просмотрите статью about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="28957-120">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="28957-121">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="28957-121">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="28957-122">Примеры</span><span class="sxs-lookup"><span data-stu-id="28957-122">EXAMPLES</span></span>

### <span data-ttu-id="28957-123">Пример 1. изменение параметров задания</span><span class="sxs-lookup"><span data-stu-id="28957-123">Example 1: Change job options</span></span>

```
PS C:\> Get-ScheduledJobOption -Name "DeployPackage"
StartIfOnBatteries     : False
StopIfGoingOnBatteries : True
WakeToRun              : False
StartIfNotIdle         : True
StopIfGoingOffIdle     : False
RestartOnIdleResume    : False
IdleDuration           : 00:10:00
IdleTimeout            : 01:00:00
ShowInTaskScheduler    : True
RunElevated            : False
RunWithoutNetwork      : False
DoNotAllowDemandStart  : False
MultipleInstancePolicy : IgnoreNew
JobDefinition          :

The second command uses the **Set-ScheduledJobOpton** cmdlet to change the job options so the values of the WakeToRun and RunWithoutNetwork properties are $True. The command uses the *Passthru* parameter to return the trigger after the change.
PS C:\> Get-ScheduledJobOption -Name "DeployPackage" | Set-ScheduledJobOption -WakeToRun -RequireNetwork:$False -Passthru
StartIfOnBatteries     : False
StopIfGoingOnBatteries : True
WakeToRun              : True
StartIfNotIdle         : True
StopIfGoingOffIdle     : False
RestartOnIdleResume    : False
IdleDuration           : 00:10:00
IdleTimeout            : 01:00:00
ShowInTaskScheduler    : True
RunElevated            : False
RunWithoutNetwork      : True
DoNotAllowDemandStart  : False
MultipleInstancePolicy : IgnoreNewJobDefinition          :
```

<span data-ttu-id="28957-124">В этом примере показано, как изменить параметры запланированного задания на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="28957-124">This example shows how to change the options of a scheduled job on the local computer.</span></span>

<span data-ttu-id="28957-125">Первая команда использует командлет Get-ScheduledJobOption для получения параметров задания запланированного задания DeployPackage.</span><span class="sxs-lookup"><span data-stu-id="28957-125">The first command uses the Get-ScheduledJobOption cmdlet to get the job options of the DeployPackage scheduled job.</span></span>
<span data-ttu-id="28957-126">Выходные данные показывают, что для свойств Вакеторун и RunElevated задано значение $False.</span><span class="sxs-lookup"><span data-stu-id="28957-126">The output shows that the WakeToRun and RunElevated properties are set to $False.</span></span>

<span data-ttu-id="28957-127">Эта команда не является обязательной, она включена только для того, чтобы показать эффект изменения параметров.</span><span class="sxs-lookup"><span data-stu-id="28957-127">This command is not required; it is included only to show the effect of the option change.</span></span>

### <span data-ttu-id="28957-128">Пример 2. изменение параметра для всех удаленных запланированных заданий</span><span class="sxs-lookup"><span data-stu-id="28957-128">Example 2: Change an option on all remote scheduled jobs</span></span>

```
PS C:\> Invoke-Command -Computer "Server01" -ScriptBlock {Get-ScheduledJob | Get-ScheduledJobOption | Set-ScheduledJobOption -IdleTimeout 2:00:00}
```

<span data-ttu-id="28957-129">Эта команда изменяет значение *IdleTimeout* с 1 часа (значение по умолчанию) на два часа для всех запланированных заданий на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="28957-129">This command changes the value of the *IdleTimeout* from one hour (the default value) to two hours on all scheduled jobs on the Server01 computer.</span></span>

<span data-ttu-id="28957-130">Команда использует командлет Invoke-Command для выполнения команды на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="28957-130">The command uses the Invoke-Command cmdlet to run a command on the Server01 computer.</span></span>

<span data-ttu-id="28957-131">Удаленная команда начинается с Get-ScheduledJob команды, которая получает все запланированные задания на компьютере.</span><span class="sxs-lookup"><span data-stu-id="28957-131">The remote command begins with a Get-ScheduledJob command that gets all scheduled jobs on the computer.</span></span>
<span data-ttu-id="28957-132">Запланированные задания передаются в командлет Get-ScheduledJobOption, который получает параметры задания для запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="28957-132">The scheduled jobs are piped to the Get-ScheduledJobOption cmdlet, which gets the job options of the scheduled jobs.</span></span>
<span data-ttu-id="28957-133">Каждый объект параметров задания имеет свойство JobDefinition, которое содержит запланированное задание, поэтому объект параметров остается связанным с запланированным заданием даже в случае его изменения.</span><span class="sxs-lookup"><span data-stu-id="28957-133">Each job options object contains a JobDefinition property that contains the scheduled job, so the options object remains associated with the scheduled job even when it is changed.</span></span>

<span data-ttu-id="28957-134">Триггеры заданий передаются в командлет **Set-scheduledjoboptions** , который изменяет значение параметра *IdleTimeout* на два часа (2:00:00).</span><span class="sxs-lookup"><span data-stu-id="28957-134">The job triggers are piped to the **Set-ScheduledJobOption** cmdlet, which changes the value of the *IdleTimeout* option to two hours (2:00:00).</span></span>

## <span data-ttu-id="28957-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="28957-135">PARAMETERS</span></span>

### <span data-ttu-id="28957-136">-Континуеифгоингонбаттери</span><span class="sxs-lookup"><span data-stu-id="28957-136">-ContinueIfGoingOnBattery</span></span>
<span data-ttu-id="28957-137">Не останавливайте запланированное задание, если компьютер переключается на питание от батареи (отключается от электросети) во время выполнения этого задания.</span><span class="sxs-lookup"><span data-stu-id="28957-137">Do not stop the scheduled job if the computer switches to battery power (disconnects from AC power) while the job is running.</span></span>
<span data-ttu-id="28957-138">По умолчанию запланированные задания останавливаются при отключении компьютера от электросети.</span><span class="sxs-lookup"><span data-stu-id="28957-138">By default, scheduled jobs stop when the computer disconnects from AC power.</span></span>

<span data-ttu-id="28957-139">Параметр *континуеифгоингонбаттери* задает для свойства стопифгоингонбаттериес запланированных заданий значение $true.</span><span class="sxs-lookup"><span data-stu-id="28957-139">The *ContinueIfGoingOnBattery* parameter sets the value of the StopIfGoingOnBatteries property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="28957-140">-Доноталловдемандстарт</span><span class="sxs-lookup"><span data-stu-id="28957-140">-DoNotAllowDemandStart</span></span>
<span data-ttu-id="28957-141">Запускайте задание только при его активации.</span><span class="sxs-lookup"><span data-stu-id="28957-141">Start the job only when it is triggered.</span></span>
<span data-ttu-id="28957-142">Пользователи не могут запускать задание вручную, например с помощью функции запуска компонентов в планировщике заданий.</span><span class="sxs-lookup"><span data-stu-id="28957-142">Users cannot start the job manually, such as by using the Run feature in Task Scheduler.</span></span>

<span data-ttu-id="28957-143">Этот параметр влияет только на планировщик.</span><span class="sxs-lookup"><span data-stu-id="28957-143">This parameter only affects Task Scheduler.</span></span>
<span data-ttu-id="28957-144">Он не запрещает пользователям использовать командлет Start-Job для запуска задания.</span><span class="sxs-lookup"><span data-stu-id="28957-144">It does not prevents users from using the Start-Job cmdlet to start the job.</span></span>

<span data-ttu-id="28957-145">Параметр *доноталловдемандстарт* задает для свойства доноталловдемандстарт запланированных заданий значение $true.</span><span class="sxs-lookup"><span data-stu-id="28957-145">The *DoNotAllowDemandStart* parameter sets the value of the DoNotAllowDemandStart property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="28957-146">-Хидеинтасксчедулер</span><span class="sxs-lookup"><span data-stu-id="28957-146">-HideInTaskScheduler</span></span>
<span data-ttu-id="28957-147">Не отображайте задание в планировщике заданий.</span><span class="sxs-lookup"><span data-stu-id="28957-147">Do not display the job in Task Scheduler.</span></span>
<span data-ttu-id="28957-148">Это значение затрагивает только компьютер, на котором выполняется задание.</span><span class="sxs-lookup"><span data-stu-id="28957-148">This value affects only the computer on which the job runs.</span></span>
<span data-ttu-id="28957-149">По умолчанию запланированные задачи отображаются в планировщике заданий.</span><span class="sxs-lookup"><span data-stu-id="28957-149">By default, scheduled tasks appear in Task Scheduler.</span></span>

<span data-ttu-id="28957-150">Даже если задача скрыта, пользователи могут отобразить задачу, выбрав параметр **Показать скрытые задачи** в планировщик задач.</span><span class="sxs-lookup"><span data-stu-id="28957-150">Even if a task is hidden, users can display the task by selecting the **Show hidden tasks** view option in Task Scheduler.</span></span>

<span data-ttu-id="28957-151">Параметр *хидеинтасксчедулер* задает для свойства шовинтасксчедулер запланированных заданий значение $false.</span><span class="sxs-lookup"><span data-stu-id="28957-151">The *HideInTaskScheduler* parameter sets the value of the ShowInTaskScheduler property of scheduled jobs to $False.</span></span>

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

### <span data-ttu-id="28957-152">-Идледуратион</span><span class="sxs-lookup"><span data-stu-id="28957-152">-IdleDuration</span></span>
<span data-ttu-id="28957-153">Указывает, как долго компьютер должен простаивать перед запуском задания.</span><span class="sxs-lookup"><span data-stu-id="28957-153">Specifies how long the computer must be idle before the job starts.</span></span>
<span data-ttu-id="28957-154">Значение по умолчанию — 10 минут.</span><span class="sxs-lookup"><span data-stu-id="28957-154">The default value is 10 minutes.</span></span>
<span data-ttu-id="28957-155">Если компьютер еще не простаивает заданное время на момент истечения периода *IdleTimeout* , запланированное задание не выполняется до следующего запланированного времени, если такое имеется.</span><span class="sxs-lookup"><span data-stu-id="28957-155">If the computer is not idle for the specified duration before the value of *IdleTimeout* expires, the scheduled job does not run until the next scheduled time, if any.</span></span>

<span data-ttu-id="28957-156">Введите объект TimeSpan, например созданный командлетом New-TimeSpan, или введите значение в \<hours\> \<minutes\> формате:: \<seconds\> Format, который автоматически преобразуется в объект **TimeSpan** .</span><span class="sxs-lookup"><span data-stu-id="28957-156">Enter a timespan object, such as one generated by the New-TimeSpan cmdlet, or enter a value in \<hours\>:\<minutes\>:\<seconds\> format that is automatically converted to a **TimeSpan** object.</span></span>

<span data-ttu-id="28957-157">Чтобы включить это значение, используйте параметр *StartIfIdle* .</span><span class="sxs-lookup"><span data-stu-id="28957-157">To enable this value, use the *StartIfIdle* parameter.</span></span>
<span data-ttu-id="28957-158">По умолчанию свойство Стартифнотидле запланированных заданий имеет значение $True и Windows PowerShell игнорирует значения *идледуратион* и *IdleTimeout* .</span><span class="sxs-lookup"><span data-stu-id="28957-158">By default, the StartIfNotIdle property of scheduled jobs is set to $True and Windows PowerShell ignores the *IdleDuration* and *IdleTimeout* values.</span></span>

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28957-159">-IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="28957-159">-IdleTimeout</span></span>
<span data-ttu-id="28957-160">Указывает, как долго компьютер должен простаивать перед запуском задания.</span><span class="sxs-lookup"><span data-stu-id="28957-160">Specifies how long the computer must be idle before the job starts.</span></span>
<span data-ttu-id="28957-161">Значение по умолчанию — 10 минут.</span><span class="sxs-lookup"><span data-stu-id="28957-161">The default value is 10 minutes.</span></span>
<span data-ttu-id="28957-162">Если компьютер еще не простаивает заданное время на момент истечения периода **IdleTimeout** , запланированное задание не выполняется до следующего запланированного времени, если такое имеется.</span><span class="sxs-lookup"><span data-stu-id="28957-162">If the computer is not idle for the specified duration before the value of **IdleTimeout** expires, the scheduled job does not run until the next scheduled time, if any.</span></span>

<span data-ttu-id="28957-163">Введите объект TimeSpan, например созданный командлетом New-TimeSpan, или введите значение в \<hours\> \<minutes\> формате:: \<seconds\> Format, который автоматически преобразуется в объект **TimeSpan** .</span><span class="sxs-lookup"><span data-stu-id="28957-163">Enter a timespan object, such as one generated by the New-TimeSpan cmdlet, or enter a value in \<hours\>:\<minutes\>:\<seconds\> format that is automatically converted to a **TimeSpan** object.</span></span>

<span data-ttu-id="28957-164">Чтобы включить это значение, используйте параметр *StartIfIdle* .</span><span class="sxs-lookup"><span data-stu-id="28957-164">To enable this value, use the *StartIfIdle* parameter.</span></span>
<span data-ttu-id="28957-165">По умолчанию свойство Стартифнотидле запланированных заданий имеет значение $True и Windows PowerShell игнорирует значения *идледуратион* и *IdleTimeout* .</span><span class="sxs-lookup"><span data-stu-id="28957-165">By default, the StartIfNotIdle property of scheduled jobs is set to $True and Windows PowerShell ignores the *IdleDuration* and *IdleTimeout* values.</span></span>

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28957-166">-InputObject</span><span class="sxs-lookup"><span data-stu-id="28957-166">-InputObject</span></span>
<span data-ttu-id="28957-167">Указывает параметры задания.</span><span class="sxs-lookup"><span data-stu-id="28957-167">Specifies the job options.</span></span>
<span data-ttu-id="28957-168">Введите переменную, содержащую объекты **счедуледжобоптионс** , или введите команду или выражение, которое получает объекты **счедуледжобоптионс** , такие как команда Get-ScheduledJobOption.</span><span class="sxs-lookup"><span data-stu-id="28957-168">Enter a variable that contains **ScheduledJobOptions** objects or type a command or expression that gets **ScheduledJobOptions** objects, such as a Get-ScheduledJobOption command.</span></span>
<span data-ttu-id="28957-169">Можно также передать объект **счедуледжобоптионс** в командлет **Set-scheduledjoboptions** .</span><span class="sxs-lookup"><span data-stu-id="28957-169">You can also pipe a **ScheduledJobOptions** object to **Set-ScheduledJobOption** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="28957-170">-Мултиплеинстанцеполици</span><span class="sxs-lookup"><span data-stu-id="28957-170">-MultipleInstancePolicy</span></span>
<span data-ttu-id="28957-171">Определяет, как система реагирует на запрос о запуске экземпляра запланированного задания во время выполнения другого экземпляра этого задания.</span><span class="sxs-lookup"><span data-stu-id="28957-171">Determines how the system responds to a request to start an instance of a scheduled job while another instance of the job is running.</span></span>
<span data-ttu-id="28957-172">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="28957-172">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="28957-173">Игноренев.</span><span class="sxs-lookup"><span data-stu-id="28957-173">IgnoreNew.</span></span>
<span data-ttu-id="28957-174">Новый экземпляр задания игнорируется.</span><span class="sxs-lookup"><span data-stu-id="28957-174">The new job instance is ignored.</span></span>
<span data-ttu-id="28957-175">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="28957-175">This is the default value.</span></span>
- <span data-ttu-id="28957-176">Параллельный.</span><span class="sxs-lookup"><span data-stu-id="28957-176">Parallel.</span></span>
<span data-ttu-id="28957-177">Новый экземпляр задания запускается немедленно.</span><span class="sxs-lookup"><span data-stu-id="28957-177">The new job instance starts immediately.</span></span>
- <span data-ttu-id="28957-178">Очередь.</span><span class="sxs-lookup"><span data-stu-id="28957-178">Queue.</span></span>
<span data-ttu-id="28957-179">Новый экземпляр задания запускается сразу после завершения текущего экземпляра.</span><span class="sxs-lookup"><span data-stu-id="28957-179">The new job instance starts as soon as the current instance completes.</span></span>
- <span data-ttu-id="28957-180">Стопексистинг.</span><span class="sxs-lookup"><span data-stu-id="28957-180">StopExisting.</span></span>
<span data-ttu-id="28957-181">Текущий экземпляр задания останавливается, и запускается новый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="28957-181">The current instance of the job stop and the new instance starts.</span></span>

<span data-ttu-id="28957-182">Чтобы запустить задание, должны быть выполнены все условия для расписания задания.</span><span class="sxs-lookup"><span data-stu-id="28957-182">To run the job, all conditions for the job schedule must be met.</span></span>
<span data-ttu-id="28957-183">Например, если условия, заданные параметрами *рекуиренетворк* , *идледуратион* и *IdleTimeout* , не удовлетворены, экземпляр задания не запускается, независимо от значения этого параметра.</span><span class="sxs-lookup"><span data-stu-id="28957-183">For example, if the conditions that are set by the *RequireNetwork* , *IdleDuration* , and *IdleTimeout* parameters are not satisfied, the job instance is not started, regardless of the value of this parameter.</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.TaskMultipleInstancePolicy
Parameter Sets: (All)
Aliases:
Accepted values: None, IgnoreNew, Parallel, Queue, StopExisting

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="28957-184">-PassThru</span><span class="sxs-lookup"><span data-stu-id="28957-184">-PassThru</span></span>
<span data-ttu-id="28957-185">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="28957-185">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="28957-186">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="28957-186">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="28957-187">-Рекуиренетворк</span><span class="sxs-lookup"><span data-stu-id="28957-187">-RequireNetwork</span></span>
<span data-ttu-id="28957-188">Запускает запланированное задание только при наличии доступных сетевых подключений.</span><span class="sxs-lookup"><span data-stu-id="28957-188">Runs the scheduled job only when network connections are available.</span></span>

<span data-ttu-id="28957-189">Если указать этот параметр и в запланированное время запуска задания сеть будет недоступна, задание не запускается до следующего запланированного времени запуска, если такое имеется.</span><span class="sxs-lookup"><span data-stu-id="28957-189">If you specify this parameter and the network is not available at the scheduled start time, the job does not run until the next scheduled start time, if any.</span></span>

<span data-ttu-id="28957-190">Параметр *рекуиренетворк* задает для свойства рунвисаутнетворк запланированных заданий значение $false.</span><span class="sxs-lookup"><span data-stu-id="28957-190">The *RequireNetwork* parameter sets the value of the RunWithoutNetwork property of scheduled jobs to $False.</span></span>

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

### <span data-ttu-id="28957-191">-Рестартонидлересуме</span><span class="sxs-lookup"><span data-stu-id="28957-191">-RestartOnIdleResume</span></span>
<span data-ttu-id="28957-192">Перезапускает запланированное задание, если компьютер переходит в состояние простоя.</span><span class="sxs-lookup"><span data-stu-id="28957-192">Restarts a scheduled job when the computer becomes idle.</span></span>
<span data-ttu-id="28957-193">Этот параметр работает с параметром *StopIfGoingOffIdle* , который приостанавливает выполнение запланированного задания, если компьютер становится активным (выходит из состояния простоя).</span><span class="sxs-lookup"><span data-stu-id="28957-193">This parameter works with the *StopIfGoingOffIdle* parameter, which suspends a running scheduled job if the computer becomes active (leaves the idle state).</span></span>

<span data-ttu-id="28957-194">Параметр *рестартонидлересуме* задает для свойства рестартонидлересуме запланированных заданий значение $true.</span><span class="sxs-lookup"><span data-stu-id="28957-194">The *RestartOnIdleResume* parameter sets the value of the RestartOnIdleResume property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="28957-195">-RunElevated</span><span class="sxs-lookup"><span data-stu-id="28957-195">-RunElevated</span></span>
<span data-ttu-id="28957-196">Запускает запланированное задание с правами члена группы администраторов на компьютере, где выполняется задание.</span><span class="sxs-lookup"><span data-stu-id="28957-196">Runs the scheduled job with the permissions of a member of the Administrators group on the computer on which the job runs.</span></span>

<span data-ttu-id="28957-197">Чтобы включить выполнение запланированного задания с разрешениями администратора, используйте параметр *Credential* параметра Register-ScheduledJob, чтобы предоставить явные учетные данные для задания.</span><span class="sxs-lookup"><span data-stu-id="28957-197">To enable a scheduled job to run with Administrator permissions, use the *Credential* parameter of Register-ScheduledJob to provide explicit credential for the job.</span></span>

<span data-ttu-id="28957-198">Параметр **RunElevated** задает значение true для свойства **RunElevated** запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="28957-198">The **RunElevated** parameter sets the value of the **RunElevated** property of scheduled jobs to True.</span></span>

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

### <span data-ttu-id="28957-199">-Стартифидле</span><span class="sxs-lookup"><span data-stu-id="28957-199">-StartIfIdle</span></span>
<span data-ttu-id="28957-200">Запускает запланированное задание, если до истечения времени, заданного параметром **IdleDuration** , компьютер уже простаивал на протяжении заданного параметром *IdleTimeout* периода.</span><span class="sxs-lookup"><span data-stu-id="28957-200">Starts the scheduled job if the computer has been idle for the time specified by the **IdleDuration** parameter before the time specified by the *IdleTimeout* parameter expires.</span></span>

<span data-ttu-id="28957-201">По умолчанию параметры *IdleDuration* и *IdleTimeout* игнорируются, и задание запускается в запланированное время, даже если компьютер занят.</span><span class="sxs-lookup"><span data-stu-id="28957-201">By default, the *IdleDuration* and *IdleTimeout* parameters are ignored and the job starts at the scheduled start time even if the computer is busy.</span></span>

<span data-ttu-id="28957-202">Если указать этот параметр и в запланированное время запуска задания компьютер будет занят (не будет простаивать), задание не запускается до следующего запланированного времени запуска, если такое имеется.</span><span class="sxs-lookup"><span data-stu-id="28957-202">If you specify this parameter and the computer is busy (not idle) at the scheduled start time, the job does not run until the next scheduled start time, if any.</span></span>

<span data-ttu-id="28957-203">Параметр *стартифидле* задает для свойства **стартифнотидле** запланированных заданий значение false.</span><span class="sxs-lookup"><span data-stu-id="28957-203">The *StartIfIdle* parameter sets the value of the **StartIfNotIdle** property of scheduled jobs to False.</span></span>

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

### <span data-ttu-id="28957-204">-Стартифонбаттери</span><span class="sxs-lookup"><span data-stu-id="28957-204">-StartIfOnBattery</span></span>
<span data-ttu-id="28957-205">Запускает запланированное задание, даже если в запланированное время запуска компьютер работает от батарей.</span><span class="sxs-lookup"><span data-stu-id="28957-205">Starts the scheduled job even if the computer is running on batteries at the scheduled start time.</span></span>
<span data-ttu-id="28957-206">Значение по умолчанию равно False.</span><span class="sxs-lookup"><span data-stu-id="28957-206">The default value is False.</span></span>

<span data-ttu-id="28957-207">Параметр *стартифонбаттери* задает для свойства **стартифонбаттериес** запланированных заданий значение $true.</span><span class="sxs-lookup"><span data-stu-id="28957-207">The *StartIfOnBattery* parameter sets the value of the **StartIfOnBatteries** property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="28957-208">-Стопифгоингоффидле</span><span class="sxs-lookup"><span data-stu-id="28957-208">-StopIfGoingOffIdle</span></span>
<span data-ttu-id="28957-209">Приостанавливает выполнение запланированного задания, если компьютер становится активным (выходит из режима простоя) во время выполнения задания.</span><span class="sxs-lookup"><span data-stu-id="28957-209">Suspends a running scheduled job if the computer becomes active (not idle) while the job is running.</span></span>

<span data-ttu-id="28957-210">По умолчанию запланированное задание, которое приостанавливается при выходе компьютера из режима простоя, возобновляется, когда компьютер снова становится неактивным.</span><span class="sxs-lookup"><span data-stu-id="28957-210">By default, a scheduled job that is suspended when the computer becomes active resumes when the computer becomes idle again.</span></span>
<span data-ttu-id="28957-211">Чтобы изменить это поведение по умолчанию, используйте параметр *RestartOnIdleResume* .</span><span class="sxs-lookup"><span data-stu-id="28957-211">To change this default behavior, use the *RestartOnIdleResume* parameter.</span></span>

<span data-ttu-id="28957-212">Параметр *стопифгоингоффидле* задает для свойства стопифгоингоффидле запланированных заданий значение $true.</span><span class="sxs-lookup"><span data-stu-id="28957-212">The *StopIfGoingOffIdle* parameter sets the value of the StopIfGoingOffIdle property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="28957-213">-Вакеторун</span><span class="sxs-lookup"><span data-stu-id="28957-213">-WakeToRun</span></span>
<span data-ttu-id="28957-214">Пробуждает компьютер из спящего состояния сна или гибернации в запланированное время запуска, чтобы он мог выполнить задание.</span><span class="sxs-lookup"><span data-stu-id="28957-214">Wakes the computer from a Hibernate or Sleep state at the scheduled start time so it can run the job.</span></span>
<span data-ttu-id="28957-215">По умолчанию если компьютер находится в режиме гибернации или сна в запланированное время запуска, задание не выполняется.</span><span class="sxs-lookup"><span data-stu-id="28957-215">By default, if the computer is in a Hibernate or Sleep state at the scheduled start time, the job does not run.</span></span>

<span data-ttu-id="28957-216">Параметр *вакеторун* задает для свойства вакеторун запланированных заданий значение $true.</span><span class="sxs-lookup"><span data-stu-id="28957-216">The *WakeToRun* parameter sets the value of the WakeToRun property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="28957-217">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="28957-217">CommonParameters</span></span>
<span data-ttu-id="28957-218">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="28957-218">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="28957-219">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="28957-219">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="28957-220">Входные данные</span><span class="sxs-lookup"><span data-stu-id="28957-220">INPUTS</span></span>

### <span data-ttu-id="28957-221">Microsoft. PowerShell. ScheduledJob. Счедуледжобоптионс</span><span class="sxs-lookup"><span data-stu-id="28957-221">Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions</span></span>
<span data-ttu-id="28957-222">Объект параметров запланированного задания можно передать в **Set-ScheduledJobOption** .</span><span class="sxs-lookup"><span data-stu-id="28957-222">You can pipe a scheduled job options object to **Set-ScheduledJobOption** .</span></span>

## <span data-ttu-id="28957-223">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="28957-223">OUTPUTS</span></span>

### <span data-ttu-id="28957-224">Нет или Microsoft. PowerShell. ScheduledJob. Счедуледжобоптионс</span><span class="sxs-lookup"><span data-stu-id="28957-224">None or Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions</span></span>
<span data-ttu-id="28957-225">При использовании параметра *Passthru* командлет **Set-ScheduledJobOption** возвращает параметры задания, которые были изменены.</span><span class="sxs-lookup"><span data-stu-id="28957-225">When you use the *Passthru* parameter, **Set-ScheduledJobOption** returns the job options that were changed.</span></span>
<span data-ttu-id="28957-226">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="28957-226">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="28957-227">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="28957-227">NOTES</span></span>

## <span data-ttu-id="28957-228">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="28957-228">RELATED LINKS</span></span>

[<span data-ttu-id="28957-229">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="28957-229">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="28957-230">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="28957-230">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="28957-231">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="28957-231">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="28957-232">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="28957-232">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="28957-233">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="28957-233">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="28957-234">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="28957-234">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="28957-235">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="28957-235">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="28957-236">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="28957-236">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="28957-237">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="28957-237">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="28957-238">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="28957-238">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="28957-239">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="28957-239">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="28957-240">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="28957-240">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="28957-241">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="28957-241">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="28957-242">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="28957-242">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="28957-243">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="28957-243">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="28957-244">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="28957-244">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
