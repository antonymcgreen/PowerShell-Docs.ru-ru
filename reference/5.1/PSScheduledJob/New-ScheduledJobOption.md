---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/new-scheduledjoboption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ScheduledJobOption
ms.openlocfilehash: 35ada8d5aaa6a6c1fdc74a089308aefe13598b10
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227374"
---
# <span data-ttu-id="4c4ff-103">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="4c4ff-103">New-ScheduledJobOption</span></span>

## <span data-ttu-id="4c4ff-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4c4ff-104">SYNOPSIS</span></span>
<span data-ttu-id="4c4ff-105">Создает объект, содержащий дополнительные параметры для запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-105">Creates an object that contains advanced options for a scheduled job.</span></span>

## <span data-ttu-id="4c4ff-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4c4ff-106">SYNTAX</span></span>

```
New-ScheduledJobOption [-RunElevated] [-HideInTaskScheduler] [-RestartOnIdleResume]
 [-MultipleInstancePolicy <TaskMultipleInstancePolicy>] [-DoNotAllowDemandStart] [-RequireNetwork]
 [-StopIfGoingOffIdle] [-WakeToRun] [-ContinueIfGoingOnBattery] [-StartIfOnBattery] [-IdleTimeout <TimeSpan>]
 [-IdleDuration <TimeSpan>] [-StartIfIdle] [<CommonParameters>]
```

## <span data-ttu-id="4c4ff-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4c4ff-107">DESCRIPTION</span></span>
<span data-ttu-id="4c4ff-108">Командлет **New-ScheduledJobOption** создает объект, содержащий дополнительные параметры для запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-108">The **New-ScheduledJobOption** cmdlet creates an object that contains advanced options for a scheduled job.</span></span>

<span data-ttu-id="4c4ff-109">Можно использовать объект **ScheduledJobOptions** , возвращаемый **New-ScheduledJobOption** , чтобы задать параметры задания для нового или существующего запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-109">You can use the **ScheduledJobOptions** object that **New-ScheduledJobOption** returns to set job options for a new or existing scheduled job.</span></span>
<span data-ttu-id="4c4ff-110">Кроме того, можно задать параметры задания с помощью командлета Get-ScheduledJobOption, чтобы получить параметры задания существующего запланированного задания или использовать значение хэш-таблицы для представления параметров задания.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-110">Alternatively, you can set job options by using the Get-ScheduledJobOption cmdlet to get the job options of an existing scheduled job or by using a hash table value to represent the job options.</span></span>

<span data-ttu-id="4c4ff-111">Без параметров командлет **New-scheduledjoboptions** создает объект, который содержит значения по умолчанию для всех параметров.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-111">Without parameters, **New-ScheduledJobOption** generates an object that contains the default values for all of the options.</span></span>
<span data-ttu-id="4c4ff-112">Поскольку все свойства, кроме свойства JobDefinition, доступны для изменения, вы можете использовать итоговый объект в качестве шаблона и создавать стандартные объекты параметров для своей организации.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-112">Because all of the properties except for the JobDefinition property can be edited, you can use the resulting object as a template, and create standard option objects for your enterprise.</span></span>

<span data-ttu-id="4c4ff-113">При создании запланированных заданий и настройки их параметров проверьте значения по умолчанию для всех параметров запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-113">When creating scheduled jobs and setting scheduled job options, review the default values of all scheduled job options.</span></span>
<span data-ttu-id="4c4ff-114">Запланированные задания запускаются только в том случае, если соблюдены все условия их выполнения.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-114">Scheduled jobs run only when all conditions set for their execution are satisfied.</span></span>

<span data-ttu-id="4c4ff-115">**New-scheduledjoboptions** — это одна из коллекций командлетов планирования заданий в модуле PSScheduledJob, который входит в состав Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-115">**New-ScheduledJobOption** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="4c4ff-116">Дополнительные сведения о запланированных заданиях см. в разделах описания в модуле PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-116">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="4c4ff-117">Импортируйте модуль PSScheduledJob, а затем введите `Get-Help about_Scheduled*` или просмотрите статью about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-117">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="4c4ff-118">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-118">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="4c4ff-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="4c4ff-119">EXAMPLES</span></span>

### <span data-ttu-id="4c4ff-120">Пример 1. Создание объекта параметра запланированного задания со значениями по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4c4ff-120">Example 1: Create a scheduled job option object with default values</span></span>

```
PS C:\> New-ScheduledJobOption
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
RunWithoutNetwork      : True
DoNotAllowDemandStart  : False
MultipleInstancePolicy : Ignore
NewJobDefinition       :
```

<span data-ttu-id="4c4ff-121">Эта команда создает объект параметров запланированного задания со всеми значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-121">This command creates a scheduled job option object that has all of the default values.</span></span>

### <span data-ttu-id="4c4ff-122">Пример 2. Создание объекта параметра запланированного задания с пользовательскими значениями</span><span class="sxs-lookup"><span data-stu-id="4c4ff-122">Example 2: Create a scheduled job option object with custom values</span></span>

```
PS C:\> New-ScheduledJobOption -RequireNetwork -StartIfOnBattery
StartIfOnBatteries     : True
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
MultipleInstancePolicy : Ignore
NewJobDefinition       :
```

<span data-ttu-id="4c4ff-123">Следующая команда создает объект запланированного задания, который требует наличия сети и запускает запланированное задание, даже если компьютер не подключен к электросети.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-123">The following command creates a scheduled job object that requires the network and runs the scheduled job even if the computer is not connected to AC power.</span></span>

<span data-ttu-id="4c4ff-124">Выходные данные показывают, что параметр *рекуиренетворк* изменил значение свойства рунвисаутнетворк на $false, а параметр *стартифонбаттери* изменил значение свойства стартифонбаттериес на $true.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-124">The output shows that the *RequireNetwork* parameter changed the value of the RunWithoutNetwork property to $False and the *StartIfOnBattery* parameter changed the value of the StartIfOnBatteries property to $True.</span></span>

### <span data-ttu-id="4c4ff-125">Пример 3. Задание параметров для нового запланированного задания</span><span class="sxs-lookup"><span data-stu-id="4c4ff-125">Example 3: Set options for a new scheduled job</span></span>

```
The first command creates a **ScheduledJobOptions** object with the *RunElevated* parameter. It saves the object in the $RunAsAdmin variable.
PS C:\> $RunAsAdmin = New-ScheduledJobOption -RunElevated

The second command uses the Register-ScheduledJob cmdlet to create a new scheduled job. The value of the *ScheduledJobOption* parameter is the option object in the value of the $RunAsAdmin variable.
PS C:\> Register-ScheduledJob -Name Backup -FilePath D:\Scripts\Backup.ps1 -Trigger $Mondays -ScheduledJobOption $RunAsAdmin

The third command uses the Get-ScheduledJobOption cmdlet to get the job options of the Backup scheduled job.The cmdlet output shows that the RunElevated property is set to $True and the JobDefinition property of the job option object is now populated with the scheduled job object for the Backup scheduled job.
PS C:\> Get-ScheduledJobOption -Name Backup
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
MultipleInstancePolicy : IgnoreNew
JobDefinition          : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

<span data-ttu-id="4c4ff-126">В этом примере показано, как использовать объект **ScheduledJobOptions** , возвращаемый **New-ScheduledJobOption** , чтобы задать параметры для нового запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-126">This example shows how to use the **ScheduledJobOptions** object that **New-ScheduledJobOption** returns to set the options for a new scheduled job.</span></span>

### <span data-ttu-id="4c4ff-127">Пример 4. Сортировка свойств объекта параметра запланированного задания</span><span class="sxs-lookup"><span data-stu-id="4c4ff-127">Example 4: Sort the properties of a scheduled job option object</span></span>

```
PS C:\> $Options = New-ScheduledJobOption -WakeToRun
PS C:\> $Options.PSObject.Properties | Sort-Object -Property Name | Format-Table -Property Name, Value -Autosize
Name                       Value
----                       -----
DoNotAllowDemandStart      False
IdleDuration            00:10:00
IdleTimeout             01:00:00
JobDefinition
MultipleInstancePolicy IgnoreNew
RestartOnIdleResume        False
RunElevated                False
RunWithoutNetwork           True
ShowInTaskScheduler         True
StartIfNotIdle              True
StartIfOnBatteries         False
StopIfGoingOffIdle         False
StopIfGoingOnBatteries      True
WakeToRun                   True
```

<span data-ttu-id="4c4ff-128">В этом примере показано, как сортировать свойства объекта **ScheduledJobOptions** в алфавитном порядке для облегчения процесса чтения.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-128">This example shows how to sort the properties of a **ScheduledJobOptions** object in alphabetical order for easy reading.</span></span>

<span data-ttu-id="4c4ff-129">Первая команда использует командлет **New-ScheduledJobOption** для создания объекта **ScheduledJobOptions** .</span><span class="sxs-lookup"><span data-stu-id="4c4ff-129">The first command uses the **New-ScheduledJobOption** cmdlet to create a **ScheduledJobOptions** object.</span></span>
<span data-ttu-id="4c4ff-130">Команда использует параметр *WakeToRun* и сохраняет полученный объект в переменной $Options.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-130">The command uses the *WakeToRun* parameter and saves the resulting object in the $Options variable.</span></span>

<span data-ttu-id="4c4ff-131">Чтобы получить свойства $Options в виде объектов, во второй команде используется свойство **PSObject** всех объектов Windows PowerShell и его свойство Properties.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-131">To get the properties of $Options as objects, the second command uses the **PSObject** property of all Windows PowerShell objects and its Properties property.</span></span>
<span data-ttu-id="4c4ff-132">Затем команда передает объекты свойств в командлет Sort-Object, который сортирует свойства в алфавитном порядке по имени, а затем в командлет Format-Table, в котором отображаются имена и значения свойств в таблице.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-132">The command then pipes the property objects to the Sort-Object cmdlet, which sorts the properties in alphabetical order by name, and then to the Format-Table cmdlet, which displays the names and values of the properties in a table.</span></span>

<span data-ttu-id="4c4ff-133">Этот формат значительно упрощает поиск свойства Вакеторун объекта **счедуледжобоптионс** в $Options и проверку того, что его значение изменилось с $False на $true.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-133">This format makes it much easier to find the WakeToRun property of the **ScheduledJobOptions** object in $Options and to verify that its value was changed from $False to $True.</span></span>

## <span data-ttu-id="4c4ff-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4c4ff-134">PARAMETERS</span></span>

### <span data-ttu-id="4c4ff-135">-Континуеифгоингонбаттери</span><span class="sxs-lookup"><span data-stu-id="4c4ff-135">-ContinueIfGoingOnBattery</span></span>
<span data-ttu-id="4c4ff-136">Не останавливайте запланированное задание, если компьютер переключается на питание от батареи (отключается от электросети) во время выполнения этого задания.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-136">Do not stop the scheduled job if the computer switches to battery power (disconnects from AC power) while the job is running.</span></span>
<span data-ttu-id="4c4ff-137">По умолчанию запланированные задания останавливаются при отключении компьютера от электросети.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-137">By default, scheduled jobs stop when the computer disconnects from AC power.</span></span>

<span data-ttu-id="4c4ff-138">Параметр *континуеифгоингонбаттери* задает для свойства стопифгоингонбаттериес запланированных заданий значение $true.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-138">The *ContinueIfGoingOnBattery* parameter sets the value of the StopIfGoingOnBatteries property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="4c4ff-139">-Доноталловдемандстарт</span><span class="sxs-lookup"><span data-stu-id="4c4ff-139">-DoNotAllowDemandStart</span></span>
<span data-ttu-id="4c4ff-140">Запускайте задание только при его активации.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-140">Start the job only when it is triggered.</span></span>
<span data-ttu-id="4c4ff-141">Пользователи не могут запускать задание вручную, например с помощью функции запуска компонентов в планировщике заданий.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-141">Users cannot start the job manually, such as by using the Run feature in Task Scheduler.</span></span>

<span data-ttu-id="4c4ff-142">Этот параметр влияет только на планировщик.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-142">This parameter only affects Task Scheduler.</span></span>
<span data-ttu-id="4c4ff-143">Он не запрещает пользователям использовать командлет Start-Job для запуска задания.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-143">It does not prevents users from using the Start-Job cmdlet to start the job.</span></span>

<span data-ttu-id="4c4ff-144">Параметр *доноталловдемандстарт* задает для свойства доноталловдемандстарт запланированных заданий значение $true.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-144">The *DoNotAllowDemandStart* parameter sets the value of the DoNotAllowDemandStart property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="4c4ff-145">-Хидеинтасксчедулер</span><span class="sxs-lookup"><span data-stu-id="4c4ff-145">-HideInTaskScheduler</span></span>
<span data-ttu-id="4c4ff-146">Не отображайте задание в планировщике заданий.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-146">Do not display the job in Task Scheduler.</span></span>
<span data-ttu-id="4c4ff-147">Это значение затрагивает только компьютер, на котором выполняется задание.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-147">This value affects only the computer on which the job runs.</span></span>
<span data-ttu-id="4c4ff-148">По умолчанию запланированные задачи отображаются в планировщике заданий.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-148">By default, scheduled tasks appear in Task Scheduler.</span></span>

<span data-ttu-id="4c4ff-149">Даже если задача скрыта, пользователи могут отобразить задачу, выбрав параметр Показать скрытые задачи в планировщик задач.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-149">Even if a task is hidden, users can display the task by selecting the Show hidden tasks view option in Task Scheduler.</span></span>

<span data-ttu-id="4c4ff-150">Параметр *хидеинтасксчедулер* задает для свойства шовинтасксчедулер запланированных заданий значение $false.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-150">The *HideInTaskScheduler* parameter sets the value of the ShowInTaskScheduler property of scheduled jobs to $False.</span></span>

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

### <span data-ttu-id="4c4ff-151">-Идледуратион</span><span class="sxs-lookup"><span data-stu-id="4c4ff-151">-IdleDuration</span></span>
<span data-ttu-id="4c4ff-152">Указывает, как долго компьютер должен простаивать перед запуском задания.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-152">Specifies how long the computer must be idle before the job starts.</span></span>
<span data-ttu-id="4c4ff-153">Значение по умолчанию — 10 минут.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-153">The default value is 10 minutes.</span></span>
<span data-ttu-id="4c4ff-154">Если компьютер еще не простаивает заданное время на момент истечения периода *IdleTimeout* , запланированное задание не выполняется до следующего запланированного времени, если такое имеется.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-154">If the computer is not idle for the specified duration before the value of *IdleTimeout* expires, the scheduled job does not run until the next scheduled time, if any.</span></span>

<span data-ttu-id="4c4ff-155">Введите объект **TimeSpan** , например созданный командлетом New-TimeSpan, или введите значение в \<hours\> \<minutes\> формате:: \<seconds\> Format, который автоматически преобразуется в объект **TimeSpan** .</span><span class="sxs-lookup"><span data-stu-id="4c4ff-155">Enter a **TimeSpan** object, such as one generated by the New-TimeSpan cmdlet, or enter a value in \<hours\>:\<minutes\>:\<seconds\> format  that is automatically converted to a **TimeSpan** object.</span></span>

<span data-ttu-id="4c4ff-156">Чтобы включить это значение, используйте параметр *StartIfIdle* .</span><span class="sxs-lookup"><span data-stu-id="4c4ff-156">To enable this value, use the *StartIfIdle* parameter.</span></span>
<span data-ttu-id="4c4ff-157">По умолчанию свойство Стартифнотидле запланированных заданий имеет значение $True и Windows PowerShell игнорирует значения *идледуратион* и *IdleTimeout* .</span><span class="sxs-lookup"><span data-stu-id="4c4ff-157">By default, the StartIfNotIdle property of scheduled jobs is set to $True and Windows PowerShell ignores the *IdleDuration* and *IdleTimeout* values.</span></span>

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

### <span data-ttu-id="4c4ff-158">-IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="4c4ff-158">-IdleTimeout</span></span>
<span data-ttu-id="4c4ff-159">Указывает, как долго запланированное задание ожидает нахождения компьютера в неактивном состоянии.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-159">Specifies how long the scheduled job waits for the computer to be idle.</span></span>
<span data-ttu-id="4c4ff-160">Если при истечении этого времени ожидания компьютер бездействует меньше периода времени, определяемого параметром *IdleDuration* , задание не выполняется до следующего запланированного времени, если оно имеется.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-160">If this timeout expires before the computer remains idle for the time period that is specified by the *IdleDuration* parameter, the job does not run until the next scheduled time, if any.</span></span>
<span data-ttu-id="4c4ff-161">Значение по умолчанию — один час.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-161">The default value is one hour.</span></span>

<span data-ttu-id="4c4ff-162">Введите объект **TimeSpan** , например созданный командлетом New-TimeSpan, или введите значение в \<hours\> \<minutes\> формате:: \<seconds\> Format, который автоматически преобразуется в объект **TimeSpan** .</span><span class="sxs-lookup"><span data-stu-id="4c4ff-162">Enter a **TimeSpan** object, such as one generated by the New-TimeSpan cmdlet, or enter a value in \<hours\>:\<minutes\>:\<seconds\> format that is automatically converted to a **TimeSpan** object.</span></span>

<span data-ttu-id="4c4ff-163">Чтобы включить это значение, используйте параметр *StartIfIdle* .</span><span class="sxs-lookup"><span data-stu-id="4c4ff-163">To enable this value, use the *StartIfIdle* parameter.</span></span>
<span data-ttu-id="4c4ff-164">По умолчанию свойство Стартифнотидле запланированных заданий имеет значение $True и Windows PowerShell игнорирует значения *идледуратион* и *IdleTimeout* .</span><span class="sxs-lookup"><span data-stu-id="4c4ff-164">By default, the StartIfNotIdle property of scheduled jobs is set to $True and Windows PowerShell ignores the *IdleDuration* and *IdleTimeout* values.</span></span>

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

### <span data-ttu-id="4c4ff-165">-Мултиплеинстанцеполици</span><span class="sxs-lookup"><span data-stu-id="4c4ff-165">-MultipleInstancePolicy</span></span>
<span data-ttu-id="4c4ff-166">Определяет, как система реагирует на запрос о запуске экземпляра запланированного задания во время выполнения другого экземпляра этого задания.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-166">Determines how the system responds to a request to start an instance of a scheduled job while another instance of the job is running.</span></span>
<span data-ttu-id="4c4ff-167">Значение по умолчанию — Игноренев.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-167">The default value is IgnoreNew.</span></span>
<span data-ttu-id="4c4ff-168">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="4c4ff-168">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="4c4ff-169">Игноренев.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-169">IgnoreNew.</span></span>
<span data-ttu-id="4c4ff-170">Новый экземпляр задания игнорируется.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-170">The new job instance is ignored.</span></span>
- <span data-ttu-id="4c4ff-171">Параллельный.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-171">Parallel.</span></span>
<span data-ttu-id="4c4ff-172">Новый экземпляр задания запускается немедленно.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-172">The new job instance starts immediately.</span></span>
- <span data-ttu-id="4c4ff-173">Очередь.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-173">Queue.</span></span>
<span data-ttu-id="4c4ff-174">Новый экземпляр задания запускается сразу после завершения текущего экземпляра.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-174">The new job instance starts as soon as the current instance completes.</span></span>
- <span data-ttu-id="4c4ff-175">Стопексистинг.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-175">StopExisting.</span></span>
<span data-ttu-id="4c4ff-176">Текущий экземпляр задания останавливается и запускается новый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-176">The current instance of the job stops and the new instance starts.</span></span>

<span data-ttu-id="4c4ff-177">Чтобы запустить задание, должны быть выполнены все условия для расписания задания.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-177">To run the job, all conditions for the job schedule must be met.</span></span>
<span data-ttu-id="4c4ff-178">Например, если условия, заданные параметрами *рекуиренетворк* , *идледуратион* и *IdleTimeout* , не удовлетворены, экземпляр задания не запускается, независимо от значения этого параметра.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-178">For example, if the conditions that are set by the *RequireNetwork* , *IdleDuration* , and *IdleTimeout* parameters are not satisfied, the job instance is not started, regardless of the value of this parameter.</span></span>

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

### <span data-ttu-id="4c4ff-179">-Рекуиренетворк</span><span class="sxs-lookup"><span data-stu-id="4c4ff-179">-RequireNetwork</span></span>
<span data-ttu-id="4c4ff-180">Запускает запланированное задание только при наличии доступных сетевых подключений.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-180">Runs the scheduled job only when network connections are available.</span></span>

<span data-ttu-id="4c4ff-181">Если указать этот параметр и в запланированное время запуска задания сеть будет недоступна, задание не запускается до следующего запланированного времени запуска, если такое имеется.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-181">If you specify this parameter and the network is not available at the scheduled start time, the job does not run until the next scheduled start time, if any.</span></span>

<span data-ttu-id="4c4ff-182">Параметр *рекуиренетворк* задает для свойства рунвисаутнетворк запланированных заданий значение $false.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-182">The *RequireNetwork* parameter sets the value of the RunWithoutNetwork property of scheduled jobs to $False.</span></span>

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

### <span data-ttu-id="4c4ff-183">-Рестартонидлересуме</span><span class="sxs-lookup"><span data-stu-id="4c4ff-183">-RestartOnIdleResume</span></span>
<span data-ttu-id="4c4ff-184">Перезапускает запланированное задание, если компьютер переходит в состояние простоя.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-184">Restarts a scheduled job when the computer becomes idle.</span></span>
<span data-ttu-id="4c4ff-185">Этот параметр работает с параметром *StopIfGoingOffIdle* , который приостанавливает выполнение запланированного задания, если компьютер становится активным (выходит из состояния простоя).</span><span class="sxs-lookup"><span data-stu-id="4c4ff-185">This parameter works with the *StopIfGoingOffIdle* parameter, which suspends a running scheduled job if the computer becomes active (leaves the idle state).</span></span>

<span data-ttu-id="4c4ff-186">Параметр *рестартонидлересуме* задает для свойства рестартонидлересуме запланированных заданий значение $true.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-186">The *RestartOnIdleResume* parameter sets the value of the RestartOnIdleResume property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="4c4ff-187">-RunElevated</span><span class="sxs-lookup"><span data-stu-id="4c4ff-187">-RunElevated</span></span>
<span data-ttu-id="4c4ff-188">Запускает запланированное задание с правами члена группы администраторов на компьютере, где выполняется задание.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-188">Runs the scheduled job with the permissions of a member of the Administrators group on the computer on which the job runs.</span></span>

<span data-ttu-id="4c4ff-189">Чтобы включить выполнение запланированного задания с разрешениями администратора, используйте параметр *Credential* параметра Register-ScheduledJob, чтобы предоставить явные учетные данные для задания.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-189">To enable a scheduled job to run with Administrator permissions, use the *Credential* parameter of Register-ScheduledJob to provide explicit credential for the job.</span></span>

<span data-ttu-id="4c4ff-190">Параметр *RunElevated* задает для свойства RunElevated запланированных заданий значение $true.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-190">The *RunElevated* parameter sets the value of the RunElevated property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="4c4ff-191">-Стартифидле</span><span class="sxs-lookup"><span data-stu-id="4c4ff-191">-StartIfIdle</span></span>
<span data-ttu-id="4c4ff-192">Запускает запланированное задание, если до истечения времени, заданного параметром *IdleDuration* , компьютер уже простаивал на протяжении заданного параметром *IdleTimeout* периода.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-192">Starts the scheduled job if the computer has been idle for the time specified by the *IdleDuration* parameter before the time specified by the *IdleTimeout* parameter expires.</span></span>

<span data-ttu-id="4c4ff-193">По умолчанию параметры *IdleDuration* и *IdleTimeout* игнорируются, и задание запускается в запланированное время, даже если компьютер занят.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-193">By default, the *IdleDuration* and *IdleTimeout* parameters are ignored and the job starts at the scheduled start time even if the computer is busy.</span></span>

<span data-ttu-id="4c4ff-194">Если указать этот параметр и в запланированное время запуска задания компьютер будет занят (не будет простаивать), задание не запускается до следующего запланированного времени запуска, если такое имеется.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-194">If you specify this parameter and the computer is busy (not idle) at the scheduled start time, the job does not run until the next scheduled start time, if any.</span></span>

<span data-ttu-id="4c4ff-195">Параметр *стартифидле* задает для свойства стартифнотидле запланированных заданий значение $false.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-195">The *StartIfIdle* parameter sets the value of the StartIfNotIdle property of scheduled jobs to $False.</span></span>

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

### <span data-ttu-id="4c4ff-196">-Стартифонбаттери</span><span class="sxs-lookup"><span data-stu-id="4c4ff-196">-StartIfOnBattery</span></span>
<span data-ttu-id="4c4ff-197">Запускает запланированное задание, даже если в запланированное время запуска компьютер работает от батарей.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-197">Starts the scheduled job even if the computer is running on batteries at the scheduled start time.</span></span>
<span data-ttu-id="4c4ff-198">Значение по умолчанию — $False.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-198">The default value is $False.</span></span>

<span data-ttu-id="4c4ff-199">Параметр *стартифонбаттери* задает для свойства стартифонбаттериес запланированных заданий значение $true.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-199">The *StartIfOnBattery* parameter sets the value of the StartIfOnBatteries property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="4c4ff-200">-Стопифгоингоффидле</span><span class="sxs-lookup"><span data-stu-id="4c4ff-200">-StopIfGoingOffIdle</span></span>
<span data-ttu-id="4c4ff-201">Приостанавливает выполнение запланированного задания, если компьютер становится активным (выходит из режима простоя) во время выполнения задания.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-201">Suspends a running scheduled job if the computer becomes active (not idle) while the job is running.</span></span>

<span data-ttu-id="4c4ff-202">По умолчанию запланированное задание, которое приостанавливается при выходе компьютера из режима простоя, возобновляется, когда компьютер снова становится неактивным.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-202">By default, a scheduled job that is suspended when the computer becomes active resumes when the computer becomes idle again.</span></span>
<span data-ttu-id="4c4ff-203">Чтобы изменить это поведение по умолчанию, используйте параметр *RestartOnIdleResume* .</span><span class="sxs-lookup"><span data-stu-id="4c4ff-203">To change this default behavior, use the *RestartOnIdleResume* parameter.</span></span>

<span data-ttu-id="4c4ff-204">Параметр *стопифгоингоффидле* задает для свойства стопифгоингоффидле запланированных заданий значение $true.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-204">The *StopIfGoingOffIdle* parameter sets the value of the StopIfGoingOffIdle property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="4c4ff-205">-Вакеторун</span><span class="sxs-lookup"><span data-stu-id="4c4ff-205">-WakeToRun</span></span>
<span data-ttu-id="4c4ff-206">Пробуждает компьютер из спящего состояния сна или гибернации в запланированное время запуска, чтобы он мог выполнить задание.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-206">Wakes the computer from a Hibernate or Sleep state at the scheduled start time so it can run the job.</span></span>
<span data-ttu-id="4c4ff-207">По умолчанию если компьютер находится в режиме гибернации или сна в запланированное время запуска, задание не выполняется.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-207">By default, if the computer is in a Hibernate or Sleep state at the scheduled start time, the job does not run.</span></span>

<span data-ttu-id="4c4ff-208">Параметр *вакеторун* задает для свойства вакеторун запланированных заданий значение $true.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-208">The *WakeToRun* parameter sets the value of the WakeToRun property of scheduled jobs to $True.</span></span>

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

### <span data-ttu-id="4c4ff-209">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="4c4ff-209">CommonParameters</span></span>
<span data-ttu-id="4c4ff-210">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-210">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4c4ff-211">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4c4ff-211">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4c4ff-212">Входные данные</span><span class="sxs-lookup"><span data-stu-id="4c4ff-212">INPUTS</span></span>

### <span data-ttu-id="4c4ff-213">Нет</span><span class="sxs-lookup"><span data-stu-id="4c4ff-213">None</span></span>
<span data-ttu-id="4c4ff-214">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-214">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="4c4ff-215">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="4c4ff-215">OUTPUTS</span></span>

### <span data-ttu-id="4c4ff-216">Microsoft. PowerShell. ScheduledJob. Счедуледжобоптионс</span><span class="sxs-lookup"><span data-stu-id="4c4ff-216">Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions</span></span>

## <span data-ttu-id="4c4ff-217">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="4c4ff-217">NOTES</span></span>

* <span data-ttu-id="4c4ff-218">Вы можете использовать объект **счедуледжобоптионс** , который создается командлетом **New-scheduledjoboptions** в качестве значения параметра *scheduledjoboptions* для Register-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="4c4ff-218">You can use the **ScheduledJobOptions** object that **New-ScheduledJobOption** creates as the value of the *ScheduledJobOption* parameter of the Register-ScheduledJob cmdlet.</span></span> <span data-ttu-id="4c4ff-219">Однако параметр *scheduledjoboptions* также может принимать значение хэш-таблицы, определяющее свойства объекта **счедуледжобоптионс** и их значения, такие как:</span><span class="sxs-lookup"><span data-stu-id="4c4ff-219">However, the *ScheduledJobOption* parameter can also take a hash table value that specifies the properties of the **ScheduledJobOptions** object and their values, such as:</span></span>

  `@{ShowInTaskScheduler=$False; RunElevated=$True; IdleDuration="00:05"}`

## <span data-ttu-id="4c4ff-220">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="4c4ff-220">RELATED LINKS</span></span>

[<span data-ttu-id="4c4ff-221">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="4c4ff-221">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="4c4ff-222">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="4c4ff-222">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="4c4ff-223">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="4c4ff-223">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="4c4ff-224">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="4c4ff-224">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="4c4ff-225">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="4c4ff-225">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="4c4ff-226">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="4c4ff-226">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="4c4ff-227">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="4c4ff-227">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="4c4ff-228">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="4c4ff-228">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="4c4ff-229">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="4c4ff-229">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="4c4ff-230">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="4c4ff-230">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="4c4ff-231">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="4c4ff-231">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="4c4ff-232">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="4c4ff-232">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="4c4ff-233">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="4c4ff-233">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="4c4ff-234">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="4c4ff-234">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="4c4ff-235">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="4c4ff-235">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="4c4ff-236">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="4c4ff-236">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
