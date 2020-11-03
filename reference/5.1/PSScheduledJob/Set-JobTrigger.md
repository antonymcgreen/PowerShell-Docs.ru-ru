---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/set-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-JobTrigger
ms.openlocfilehash: 8d1b12b67ccf695e1c4b948e6eeecf292c588af4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227365"
---
# <span data-ttu-id="5840b-103">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="5840b-103">Set-JobTrigger</span></span>

## <span data-ttu-id="5840b-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="5840b-104">SYNOPSIS</span></span>
<span data-ttu-id="5840b-105">Изменяет триггер задания для запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="5840b-105">Changes the job trigger of a scheduled job.</span></span>

## <span data-ttu-id="5840b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5840b-106">SYNTAX</span></span>

```
Set-JobTrigger [-InputObject] <ScheduledJobTrigger[]> [-DaysInterval <Int32>] [-WeeksInterval <Int32>]
 [-RandomDelay <TimeSpan>] [-At <DateTime>] [-User <String>] [-DaysOfWeek <DayOfWeek[]>] [-AtStartup]
 [-AtLogOn] [-Once] [-RepetitionInterval <TimeSpan>] [-RepetitionDuration <TimeSpan>] [-RepeatIndefinitely]
 [-Daily] [-Weekly] [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="5840b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5840b-107">DESCRIPTION</span></span>
<span data-ttu-id="5840b-108">Командлет **Set-JobTrigger** изменяет свойства триггеров задания для запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="5840b-108">The **Set-JobTrigger** cmdlet changes the properties of the job triggers of scheduled jobs.</span></span>
<span data-ttu-id="5840b-109">Его можно использовать для изменения времени или частоты, с которой запускаются задания, а также для перехода от расписаний на основе времени к расписаниям, где активация осуществляется при загрузке системы или входе в нее.</span><span class="sxs-lookup"><span data-stu-id="5840b-109">You can use it to change the time or frequency at which the jobs start or to change from a time-based schedules to schedules that are triggered by a logon or startup.</span></span>

<span data-ttu-id="5840b-110">Триггер задания определяет повторяющееся расписание или условия для запуска запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="5840b-110">A job trigger defines a recurring schedule or conditions for starting a scheduled job.</span></span>
<span data-ttu-id="5840b-111">Хотя триггеры задания не сохраняются на диске, можно изменить триггеры задания для сохраненных на диск запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="5840b-111">Although job triggers are not saved to disk, you can change the job triggers of scheduled jobs, which are saved to disk.</span></span>

<span data-ttu-id="5840b-112">Чтобы изменить триггер задания для запланированного задания, начните с использования командлета Get-JobTrigger, чтобы получить триггер задания для запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="5840b-112">To change a job trigger of a scheduled job, begin by using the Get-JobTrigger cmdlet to get the job trigger of a scheduled job.</span></span>
<span data-ttu-id="5840b-113">Затем передайте триггер в **Set-JobTrigger** или сохраните его в переменной и используйте параметр *InputObject* командлета **Set-JobTrigger** для идентификации триггера.</span><span class="sxs-lookup"><span data-stu-id="5840b-113">Then, pipe the trigger to **Set-JobTrigger** or save the trigger in a variable and use the *InputObject* parameter of **Set-JobTrigger** cmdlet to identify the trigger.</span></span>
<span data-ttu-id="5840b-114">Используйте остальные параметры **Set-JobTrigger** для изменения триггера задания.</span><span class="sxs-lookup"><span data-stu-id="5840b-114">Use the remaining parameters of **Set-JobTrigger** to change the job trigger.</span></span>

<span data-ttu-id="5840b-115">При изменении типа триггера задания, например при изменении триггера задания с ежедневного или еженедельного триггера на триггер *AtLogon* , исходные свойства триггера удаляются.</span><span class="sxs-lookup"><span data-stu-id="5840b-115">When you change the type of a job trigger, such as changing a job trigger from a daily or weekly trigger to an *AtLogon* trigger, the original trigger properties are deleted.</span></span>
<span data-ttu-id="5840b-116">Однако при изменении значений триггера, но не его типа, например, при изменении дней еженедельного триггера, изменяются только задаваемые свойства.</span><span class="sxs-lookup"><span data-stu-id="5840b-116">However, if you change the values of the trigger, but not its type, such as changing the days in a weekly trigger, only the properties that you specify are changed.</span></span>
<span data-ttu-id="5840b-117">Все остальные свойства исходного триггера задания сохраняются.</span><span class="sxs-lookup"><span data-stu-id="5840b-117">All other properties of the original job trigger are retained.</span></span>

<span data-ttu-id="5840b-118">**Set-JobTrigger** — это одна из коллекций командлетов планирования заданий в модуле PSScheduledJob, который входит в состав Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5840b-118">**Set-JobTrigger** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="5840b-119">Дополнительные сведения о запланированных заданиях см. в разделах описания в модуле PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="5840b-119">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="5840b-120">Импортируйте модуль PSScheduledJob и введите: `Get-Help about_Scheduled*`  или см. about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="5840b-120">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*`  or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="5840b-121">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5840b-121">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="5840b-122">Примеры</span><span class="sxs-lookup"><span data-stu-id="5840b-122">EXAMPLES</span></span>

### <span data-ttu-id="5840b-123">Пример 1. изменение дней в триггере задания</span><span class="sxs-lookup"><span data-stu-id="5840b-123">Example 1: Change the days in a job trigger</span></span>

```
PS C:\> Get-JobTrigger -Name "DeployPackage"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Weekly          9/29/2011 12:00:00 AM  {Wednesday, Saturday}   True

The second command uses the Get-JobTrigger cmdlet to get the job trigger of the DeployPackage scheduled job. A pipeline operator (|) sends the trigger to the **Set-JobTrigger** cmdlet, which changes the job trigger so that it starts the DeployPackage job on Wednesdays and Sundays. The command uses the *Passthru* parameter to return the trigger after the change.
PS C:\> Get-JobTrigger -Name "DeployPackage" | Set-JobTrigger -DaysOfWeek "Wednesday", "Sunday" -Passthru
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Weekly          9/29/2011 12:00:00 AM  {Wednesday, Sunday}     True
```

<span data-ttu-id="5840b-124">В этом примере показано, как изменить дни в еженедельном триггере задания.</span><span class="sxs-lookup"><span data-stu-id="5840b-124">This example shows how to change the days in a weekly job trigger.</span></span>

<span data-ttu-id="5840b-125">Первая команда использует командлет Get-JobTrigger для получения триггера задания запланированного задания DeployPackage.</span><span class="sxs-lookup"><span data-stu-id="5840b-125">The first command uses the Get-JobTrigger cmdlet to get the job trigger of the DeployPackage scheduled job.</span></span>
<span data-ttu-id="5840b-126">Выходные данные показывают, что триггер запускает задание в полночь по средам и субботам.</span><span class="sxs-lookup"><span data-stu-id="5840b-126">The output shows that the trigger starts the job at midnight on Wednesdays and Saturdays.</span></span>

<span data-ttu-id="5840b-127">Эта команда не является обязательной, она включена только для того, чтобы показать эффект изменения триггера.</span><span class="sxs-lookup"><span data-stu-id="5840b-127">This command is not required; it is included only to show the effect of the trigger change.</span></span>

### <span data-ttu-id="5840b-128">Пример 2. изменение типа триггера задания</span><span class="sxs-lookup"><span data-stu-id="5840b-128">Example 2: Change the job trigger type</span></span>

```
PS C:\> Get-JobTrigger -Name "Inventory"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Daily           9/27/2011 11:00:00 PM                          True
2          AtStartup                                                      True

The second command uses the **Get-JobTrigger** cmdlet to get the *AtStartup* job trigger of the Inventory job. The command uses the *TriggerID* parameter to identify the job trigger. A pipeline operator (|) sends the job trigger to the **Set-JobTrigger** cmdlet, which changes it to a weekly job trigger that runs every four weeks on Monday at midnight. The command uses the *Passthru* parameter to return the trigger after the change.
PS C:\> Get-JobTrigger -Name "Inventory" -TriggerID 2 | Set-JobTrigger -Weekly -WeeksInterval 4 -DaysOfWeek Monday -At "12:00 AM"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Daily           9/27/2011 11:00:00 PM                          True
2          Weekly          10/31/2011 12:00:00 AM {Monday}                True
```

<span data-ttu-id="5840b-129">В этом примере показано, как изменить тип триггера задания, который запускает задание.</span><span class="sxs-lookup"><span data-stu-id="5840b-129">This example shows how to change the type of job trigger that starts a job.</span></span>
<span data-ttu-id="5840b-130">Команды в этом примере заменяют триггер задания AtStartup еженедельным триггером.</span><span class="sxs-lookup"><span data-stu-id="5840b-130">The commands in this example replace an AtStartup job trigger with a weekly trigger.</span></span>

<span data-ttu-id="5840b-131">Первая команда использует командлет Get-JobTrigger, чтобы получить триггер задания для запланированного задания инвентаризации.</span><span class="sxs-lookup"><span data-stu-id="5840b-131">The first command uses the Get-JobTrigger cmdlet to get the job trigger of the Inventory scheduled job.</span></span>
<span data-ttu-id="5840b-132">Выходные данные показывают, что задание имеет два триггера: ежедневный триггер и триггер *AtStartup* .</span><span class="sxs-lookup"><span data-stu-id="5840b-132">The output shows that the job has two triggers a daily trigger and an *AtStartup* trigger.</span></span>

<span data-ttu-id="5840b-133">Эта команда не является обязательной, она включена только для того, чтобы показать эффект изменения триггера.</span><span class="sxs-lookup"><span data-stu-id="5840b-133">This command is not required; it is included only to show the effect of the trigger change.</span></span>

### <span data-ttu-id="5840b-134">Пример 3. изменение пользователя для триггера удаленного задания</span><span class="sxs-lookup"><span data-stu-id="5840b-134">Example 3: Change the user on a remote job trigger</span></span>

```
PS C:\> Invoke-Command -ComputerName "Server01" -ScriptBlock {Get-ScheduledJob | Get-JobTrigger | Where-Object {$_.User} | Set-JobTrigger -User "Domain01/Admin02"}
```

<span data-ttu-id="5840b-135">Эта команда изменяет пользователя во всех триггерах заданий *AtLogon* запланированных заданий на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="5840b-135">This command changes the user in all *AtLogon* job triggers of scheduled jobs on the Server01 computer.</span></span>

<span data-ttu-id="5840b-136">Команда использует командлет Invoke-Command для выполнения команды на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="5840b-136">The command uses the Invoke-Command cmdlet to run a command on the Server01 computer.</span></span>

<span data-ttu-id="5840b-137">Удаленная команда начинается с Get-ScheduledJob команды, которая получает все запланированные задания на компьютере.</span><span class="sxs-lookup"><span data-stu-id="5840b-137">The remote command begins with a Get-ScheduledJob command that gets all scheduled jobs on the computer.</span></span>
<span data-ttu-id="5840b-138">Запланированные задания передаются в командлет Get-JobTrigger, который получает Триггеры заданий запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="5840b-138">The scheduled jobs are piped to the Get-JobTrigger cmdlet, which gets the job triggers of the scheduled jobs.</span></span>
<span data-ttu-id="5840b-139">Каждый триггер задания имеет свойство JobDefinition, которое содержит запланированное задание, поэтому триггер остается связанным с запланированным заданием даже в случае его изменения.</span><span class="sxs-lookup"><span data-stu-id="5840b-139">Each job trigger contains a JobDefinition property that contains the scheduled job, so the trigger remains associated with the scheduled job even when it is changed.</span></span>

<span data-ttu-id="5840b-140">Триггеры задания передаются в командлет Where-Object, который получает Триггеры заданий, имеющие свойство User.</span><span class="sxs-lookup"><span data-stu-id="5840b-140">The job triggers are piped to the Where-Object cmdlet, which gets job triggers that have the User property.</span></span>
<span data-ttu-id="5840b-141">Выбранные триггеры задания передаются в командлет **Set-JobTrigger** , который изменяет пользователя на Domain01\Admin02.</span><span class="sxs-lookup"><span data-stu-id="5840b-141">The selected job triggers are piped to the **Set-JobTrigger** cmdlet, which changes the user to Domain01\Admin02.</span></span>

### <span data-ttu-id="5840b-142">Пример 4. изменение одного из множества триггеров заданий</span><span class="sxs-lookup"><span data-stu-id="5840b-142">Example 4: Change one of many job triggers</span></span>

```
PS C:\> Get-JobTrigger -Name "SecurityCheck"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Daily           4/24/2013 3:00:00 AM                           True
2          Weekly          4/24/2013 4:00:00 PM   {Sunday}                True
3          Once            4/24/2013 4:00:00 PM                           True

The second command uses the **TriggerID** parameter of the **Get-JobTrigger** cmdlet to get the *Once* trigger of the SecurityCheck scheduled job. The command pipes the trigger to the Format-List cmdlet, which displays all of the properties of the *Once* job trigger.The output shows that the trigger starts the job once every hour (RepetitionInterval = 1 hour) for one day (RepetitionDuration = 1 day).
PS C:\> Get-JobTrigger -Name "SecurityCheck" -TriggerID 3 | Format-List -Property *
At                 : 4/24/2012 4:00:00 PM
DaysOfWeek         :
Interval           : 1
Frequency          : Once
RandomDelay        : 00:00:00
RepetitionInterval : 01:00:00
RepetitionDuration : 1.00:00:00
User               :
Id                 : 3
Enabled            : True
JobDefinition      : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition

The third command changes the repetition interval of the job trigger from one hour to 90 minutes. The command does not return any output.
PS C:\> Get-JobTrigger -Name "SecurityCheck" -TriggerId 3 | Set-JobTrigger -RepetitionInterval (New-TimeSpan -Minutes 90)

The fourth command displays the effect of the change.The output shows that the trigger starts the job once every 90 minutes (RepetitionInterval = 1 hour, 30 minutes) for one day (RepetitionDuration = 1 day).
PS C:\> Get-JobTrigger -Name "SecurityCheck" -TriggerID 3 | Format-List -Property *
At                 : 4/24/2012 4:00:00 PM
DaysOfWeek         :
Interval           : 1
Frequency          : Once
RandomDelay        : 00:00:00
RepetitionInterval : 01:30:00
RepetitionDuration : 1.00:00:00
User               :
Id                 : 3
Enabled            : True
JobDefinition      : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

<span data-ttu-id="5840b-143">Команды в этом примере изменяют интервал повторения триггера задания *Once* для запланированного задания SecurityCheck с 60 минут на 90 минут.</span><span class="sxs-lookup"><span data-stu-id="5840b-143">The commands in this example changes the repetition interval of the *Once* job trigger of SecurityCheck scheduled job from every 60 minutes to every 90 minutes.</span></span>
<span data-ttu-id="5840b-144">Запланированное задание Секуритичекк имеет три триггера заданий, поэтому команды используют параметр *TriggerId* командлета Get-JobTrigger для обнаружения изменяемого триггера задания.</span><span class="sxs-lookup"><span data-stu-id="5840b-144">The SecurityCheck scheduled job has three job triggers, so the commands use the *TriggerId* parameter of the Get-JobTrigger cmdlet to identify the job trigger that is being changed.</span></span>

<span data-ttu-id="5840b-145">Первая команда использует командлет **Get-JobTrigger** для получения всех триггеров запланированного задания SecurityCheck.</span><span class="sxs-lookup"><span data-stu-id="5840b-145">The first command uses the **Get-JobTrigger** cmdlet to get all job triggers of the SecurityCheck scheduled job.</span></span>
<span data-ttu-id="5840b-146">Выходные данные, содержащие идентификаторы триггеров задания, показывают, что триггер задания *Once* имеет идентификатор 3.</span><span class="sxs-lookup"><span data-stu-id="5840b-146">The output, which displays the IDs of the job triggers, reveals that the *Once* job trigger has an ID of 3.</span></span>

## <span data-ttu-id="5840b-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5840b-147">PARAMETERS</span></span>

### <span data-ttu-id="5840b-148">-At</span><span class="sxs-lookup"><span data-stu-id="5840b-148">-At</span></span>
<span data-ttu-id="5840b-149">Запускает задание в указанный день и указанное время.</span><span class="sxs-lookup"><span data-stu-id="5840b-149">Starts the job at the specified date and time.</span></span>
<span data-ttu-id="5840b-150">Введите объект **DateTime** , например, возвращаемый командлетом Get-Date, или строку, которую можно преобразовать в время, например "19 апреля, 2012 15:00", "12/31/2013 9:00 PM" или "03:00".</span><span class="sxs-lookup"><span data-stu-id="5840b-150">Enter a **DateTime** object, such as one that the Get-Date cmdlet returns, or a string that can be converted to a time, such as "April 19, 2012 15:00", "12/31/2013 9:00 PM", or "3am".</span></span>

<span data-ttu-id="5840b-151">Если не указать элемент объекта **DateTime** , например секунды, этот элемент триггера задания не изменится.</span><span class="sxs-lookup"><span data-stu-id="5840b-151">If you don't specify an element of the **DateTime** object, such as seconds, that element of the job trigger is not changed.</span></span>
<span data-ttu-id="5840b-152">Если исходный триггер задания не включал в себя объект **DateTime** и вы не пропускаете элемент, триггер задания создается с соответствующим элементом из текущих даты и времени.</span><span class="sxs-lookup"><span data-stu-id="5840b-152">If the original job trigger didn't include a **DateTime** object and you omit an element, the job trigger is created with the corresponding element from the current date and time.</span></span>

<span data-ttu-id="5840b-153">При использовании параметра *Once* задайте в качестве значения параметра *At* определенную дату и определенное время.</span><span class="sxs-lookup"><span data-stu-id="5840b-153">When using the *Once* parameter, set the value of the *At* parameter to a particular date and time.</span></span>
<span data-ttu-id="5840b-154">Поскольку по умолчанию дата в объекте **DateTime** является текущей, при указании момента времени до текущего времени без явной даты триггер задания создается для времени в прошлом.</span><span class="sxs-lookup"><span data-stu-id="5840b-154">Because the default date in a **DateTime** object is the current date, setting a time before the current time without an explicit date results in a job trigger for a time in the past.</span></span>

<span data-ttu-id="5840b-155">Объекты **DateTime** и строки, которые преобразуются в объекты **DateTime** , автоматически настраиваются для совместимости с форматами даты и времени, выбранными для локального компьютера в области и языка на панели управления.</span><span class="sxs-lookup"><span data-stu-id="5840b-155">**DateTime** objects, and strings that are converted to **DateTime** objects, are automatically adjusted to be compatible with the date and time formats selected for the local computer in Region and Language in Control Panel.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5840b-156">-AtLogOn</span><span class="sxs-lookup"><span data-stu-id="5840b-156">-AtLogOn</span></span>
<span data-ttu-id="5840b-157">Запускает запланированное задание при входе указанных пользователей на компьютер.</span><span class="sxs-lookup"><span data-stu-id="5840b-157">Starts the scheduled job when the specified users log on to the computer.</span></span>
<span data-ttu-id="5840b-158">Чтобы указать пользователя, используйте параметр *User* .</span><span class="sxs-lookup"><span data-stu-id="5840b-158">To specify a user, use the *User* parameter.</span></span>

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

### <span data-ttu-id="5840b-159">-AtStartup</span><span class="sxs-lookup"><span data-stu-id="5840b-159">-AtStartup</span></span>
<span data-ttu-id="5840b-160">Запускает запланированное задание при запуске Windows.</span><span class="sxs-lookup"><span data-stu-id="5840b-160">Starts the scheduled job when Windows starts.</span></span>

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

### <span data-ttu-id="5840b-161">— Ежедневно</span><span class="sxs-lookup"><span data-stu-id="5840b-161">-Daily</span></span>
<span data-ttu-id="5840b-162">Указывает регулярное ежедневное расписание задания.</span><span class="sxs-lookup"><span data-stu-id="5840b-162">Specifies a recurring daily job schedule.</span></span>
<span data-ttu-id="5840b-163">Используйте другие параметры из набора *ежедневных* параметров, чтобы указать сведения о расписании.</span><span class="sxs-lookup"><span data-stu-id="5840b-163">Use the other parameters in the *Daily* parameter set to specify the schedule details.</span></span>

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

### <span data-ttu-id="5840b-164">-Дайсинтервал</span><span class="sxs-lookup"><span data-stu-id="5840b-164">-DaysInterval</span></span>
<span data-ttu-id="5840b-165">Указывает количество дней между выполнениями для ежедневного расписания.</span><span class="sxs-lookup"><span data-stu-id="5840b-165">Specifies the number of days between occurrences on a daily schedule.</span></span>
<span data-ttu-id="5840b-166">Например, при значении 3 запланированное задание запускается в следующие дни: 1, 4, 7 и т. д.</span><span class="sxs-lookup"><span data-stu-id="5840b-166">For example, a value of 3 starts the scheduled job on days 1, 4, 7 and so on.</span></span>
<span data-ttu-id="5840b-167">Значение по умолчанию — 1.</span><span class="sxs-lookup"><span data-stu-id="5840b-167">The default value is 1.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5840b-168">-DaysOfWeek</span><span class="sxs-lookup"><span data-stu-id="5840b-168">-DaysOfWeek</span></span>
<span data-ttu-id="5840b-169">Указывает дни недели, по которым выполняется запланированное задание.</span><span class="sxs-lookup"><span data-stu-id="5840b-169">Specifies the days of the week on which a weekly scheduled job runs.</span></span>
<span data-ttu-id="5840b-170">Введите названия дней, например понедельник, четверг, целые числа 0-6, где 0 означает воскресенье, или звездочку ( \* ), представляющую каждый день.</span><span class="sxs-lookup"><span data-stu-id="5840b-170">Enter day names, such as Monday, Thursday, integers 0-6, where 0 represents Sunday, or an asterisk (\*) to represent every day.</span></span>
<span data-ttu-id="5840b-171">Этот параметр необходим в наборе параметров Weekly.</span><span class="sxs-lookup"><span data-stu-id="5840b-171">This parameter is required in the Weekly parameter set.</span></span>

<span data-ttu-id="5840b-172">Названия дней преобразуются в их целочисленные значения в триггере задания.</span><span class="sxs-lookup"><span data-stu-id="5840b-172">Day names are converted to their integer values in the job trigger.</span></span>
<span data-ttu-id="5840b-173">В команде заключайте название каждого дня в отдельные кавычки, например Monday, Tuesday.</span><span class="sxs-lookup"><span data-stu-id="5840b-173">When you enclose day names in quotation marks in a command, enclose each day name in separate quotation marks, such as "Monday", "Tuesday".</span></span>
<span data-ttu-id="5840b-174">Если заключить несколько названий дней в одну пару одинарных кавычек, соответствующие целые значения суммируются.</span><span class="sxs-lookup"><span data-stu-id="5840b-174">If you enclose multiple day names in a single quotation mark pair, the corresponding integer values are summed.</span></span>
<span data-ttu-id="5840b-175">Например, Monday, Tuesday (1, 2) дает значение Wednesday (3).</span><span class="sxs-lookup"><span data-stu-id="5840b-175">For example, "Monday, Tuesday" (1, 2) results in a value of "Wednesday" (3).</span></span>

```yaml
Type: System.DayOfWeek[]
Parameter Sets: (All)
Aliases:
Accepted values: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5840b-176">-InputObject</span><span class="sxs-lookup"><span data-stu-id="5840b-176">-InputObject</span></span>
<span data-ttu-id="5840b-177">Указывает триггеры задания.</span><span class="sxs-lookup"><span data-stu-id="5840b-177">Specifies the job triggers.</span></span>
<span data-ttu-id="5840b-178">Введите переменную, содержащую объекты **ScheduledJobTrigger** , или введите команду или выражение, которое получает объекты **ScheduledJobTrigger** , такие как команда Get-JobTrigger.</span><span class="sxs-lookup"><span data-stu-id="5840b-178">Enter a variable that contains **ScheduledJobTrigger** objects or type a command or expression that gets **ScheduledJobTrigger** objects, such as a Get-JobTrigger command.</span></span>
<span data-ttu-id="5840b-179">Можно также передать объект **ScheduledJobTrigger** в командлет **Set-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="5840b-179">You can also pipe a **ScheduledJobTrigger** object to **Set-JobTrigger** .</span></span>

<span data-ttu-id="5840b-180">При указании нескольких триггеров заданий **Set-JobTrigger** вносит одинаковые изменения во все триггеры задания.</span><span class="sxs-lookup"><span data-stu-id="5840b-180">If you specify multiple job triggers, **Set-JobTrigger** makes the same changes to all job triggers.</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="5840b-181">-Один раз</span><span class="sxs-lookup"><span data-stu-id="5840b-181">-Once</span></span>
<span data-ttu-id="5840b-182">Задает разовое (неповторяющееся) расписание.</span><span class="sxs-lookup"><span data-stu-id="5840b-182">Specifies a non-recurring (one time) schedule.</span></span>

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

### <span data-ttu-id="5840b-183">-PassThru</span><span class="sxs-lookup"><span data-stu-id="5840b-183">-PassThru</span></span>
<span data-ttu-id="5840b-184">Возвращает изменившиеся триггеры задания.</span><span class="sxs-lookup"><span data-stu-id="5840b-184">Returns the job triggers that changed.</span></span>
<span data-ttu-id="5840b-185">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="5840b-185">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="5840b-186">-Рандомделай</span><span class="sxs-lookup"><span data-stu-id="5840b-186">-RandomDelay</span></span>
<span data-ttu-id="5840b-187">Включает случайную задержку, которая начинается в запланированное время начала, и задает максимальное значение этой задержки.</span><span class="sxs-lookup"><span data-stu-id="5840b-187">Enables a random delay that begins at the scheduled start time, and sets the maximum delay value.</span></span>
<span data-ttu-id="5840b-188">Длительность задержки задается для каждого запуска псевдослучайным образом и лежит в диапазоне от нуля до значения этого параметра.</span><span class="sxs-lookup"><span data-stu-id="5840b-188">The length of the delay is set pseudo-randomly for each start and varies from no delay to the time specified by the value of this parameter.</span></span>
<span data-ttu-id="5840b-189">Нулевое значение по умолчанию (00:00:00) отключает случайную задержку.</span><span class="sxs-lookup"><span data-stu-id="5840b-189">The default value, zero (00:00:00), disables the random delay.</span></span>

<span data-ttu-id="5840b-190">Введите объект TimeSpan, например возвращаемый командлетом New-TimeSpan, или введите значение в \<hours\> \<minutes\> формате:: \<seconds\> Format, которое автоматически преобразуется в объект TimeSpan.</span><span class="sxs-lookup"><span data-stu-id="5840b-190">Enter a timespan object, such as one returned by the New-TimeSpan cmdlet, or enter a value in \<hours\>:\<minutes\>:\<seconds\> format, which is automatically converted to a timespan object.</span></span>

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

### <span data-ttu-id="5840b-191">-RepeatIndefinitely</span><span class="sxs-lookup"><span data-stu-id="5840b-191">-RepeatIndefinitely</span></span>
<span data-ttu-id="5840b-192">Этот параметр, который доступен, начиная с Windows PowerShell 4.0, устраняет необходимость в указании значения **TimeSpan.MaxValue** параметра *RepetitionDuration* для выполнения задания по расписанию в течение неопределенного времени.</span><span class="sxs-lookup"><span data-stu-id="5840b-192">This parameter, available starting in Windows PowerShell 4.0, eliminates the necessity of specifying a **TimeSpan.MaxValue** value for the *RepetitionDuration* parameter to run a scheduled job repeatedly, for an indefinite period.</span></span>

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

### <span data-ttu-id="5840b-193">-RepetitionDuration</span><span class="sxs-lookup"><span data-stu-id="5840b-193">-RepetitionDuration</span></span>
<span data-ttu-id="5840b-194">Повторяет задание до истечения заданного времени.</span><span class="sxs-lookup"><span data-stu-id="5840b-194">Repeats the job until the specified time expires.</span></span>
<span data-ttu-id="5840b-195">Частота повторения определяется значением параметра *RepetitionInterval* .</span><span class="sxs-lookup"><span data-stu-id="5840b-195">The repetition frequency is determined by the value of the *RepetitionInterval* parameter.</span></span>
<span data-ttu-id="5840b-196">Например, если значение **RepetitionInterval** составляет 5 минут, а значение *RepetitionDuration* составляет 2 часа, задание запускается каждые пять минут в течение двух часов.</span><span class="sxs-lookup"><span data-stu-id="5840b-196">For example, if the value of **RepetitionInterval** is 5 minutes and the value of *RepetitionDuration* is 2 hours, the job is triggered every five minutes for two hours.</span></span>

<span data-ttu-id="5840b-197">Введите объект TimeSpan, например, возвращаемый командлетом New-TimeSpan, или строку, которую можно преобразовать в объект TimeSpan, например "1:05:30".</span><span class="sxs-lookup"><span data-stu-id="5840b-197">Enter a timespan object, such as one that the New-TimeSpan cmdlet returns or a string that can be converted to a timespan object, such as "1:05:30".</span></span>

<span data-ttu-id="5840b-198">Для бессрочного выполнения задания добавьте вместо этого параметр *RepeatIndefinitely* .</span><span class="sxs-lookup"><span data-stu-id="5840b-198">To run a job indefinitely, add the *RepeatIndefinitely* parameter instead.</span></span>

<span data-ttu-id="5840b-199">Чтобы остановить задание до истечения срока повторения триггера задания, задайте для **RepetitionDuration** нулевое значение (0).</span><span class="sxs-lookup"><span data-stu-id="5840b-199">To stop a job before the job trigger repetition duration expires, set the **RepetitionDuration** value to zero (0).</span></span>

<span data-ttu-id="5840b-200">Чтобы изменить длительность повторения или интервал повторения триггера задания *Once* , команда должна содержать оба параметра **RepetitionInterval** и **RepetitionDuration** .</span><span class="sxs-lookup"><span data-stu-id="5840b-200">To change the repetition duration or repetition interval of a *Once* job trigger, the command must include both the **RepetitionInterval** and **RepetitionDuration** parameters.</span></span>
<span data-ttu-id="5840b-201">Чтобы изменить длительность повторения или интервалы повторения других типов триггеров задания, команда должна содержать параметры *Once* , *At* , *RepetitionInterval* и *RepetitionDuration* .</span><span class="sxs-lookup"><span data-stu-id="5840b-201">To change the repetition duration or repetition intervals of other types of job triggers, the command must include the *Once* , *At* , *RepetitionInterval* and *RepetitionDuration* parameters.</span></span>

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

### <span data-ttu-id="5840b-202">-Репетитионинтервал</span><span class="sxs-lookup"><span data-stu-id="5840b-202">-RepetitionInterval</span></span>
<span data-ttu-id="5840b-203">Повторяет задание с определенным интервалом.</span><span class="sxs-lookup"><span data-stu-id="5840b-203">Repeats the job at the specified time interval.</span></span>
<span data-ttu-id="5840b-204">Например, если значение этого параметра равно 2 часам, задание активируется каждые два часа.</span><span class="sxs-lookup"><span data-stu-id="5840b-204">For example, if the value of this parameter is 2 hours, the job is triggered every two hours.</span></span>
<span data-ttu-id="5840b-205">При использовании нулевого значения по умолчанию задание не запускается повторно.</span><span class="sxs-lookup"><span data-stu-id="5840b-205">The default value, 0, does not repeat the job.</span></span>

<span data-ttu-id="5840b-206">Введите объект TimeSpan, например, возвращаемый командлетом New-TimeSpan, или строку, которую можно преобразовать в объект TimeSpan, например "1:05:30".</span><span class="sxs-lookup"><span data-stu-id="5840b-206">Enter a timespan object, such as one that the New-TimeSpan cmdlet returns or a string that can be converted to a timespan object, such as "1:05:30".</span></span>

<span data-ttu-id="5840b-207">Чтобы изменить длительность повторения или интервал повторения триггера задания **Once** , команда должна содержать оба параметра **RepetitionInterval** и **RepetitionDuration** .</span><span class="sxs-lookup"><span data-stu-id="5840b-207">To change the repetition duration or repetition interval of a **Once** job trigger, the command must include both the **RepetitionInterval** and **RepetitionDuration** parameters.</span></span>
<span data-ttu-id="5840b-208">Чтобы изменить длительность повторения или интервалы повторения других типов триггеров задания, команда должна содержать параметры **Once** , **At** , **RepetitionInterval** и **RepetitionDuration** .</span><span class="sxs-lookup"><span data-stu-id="5840b-208">To change the repetition duration or repetition intervals of other types of job triggers, the command must include the **Once** , **At** , **RepetitionInterval** and **RepetitionDuration** parameters.</span></span>

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

### <span data-ttu-id="5840b-209">-User</span><span class="sxs-lookup"><span data-stu-id="5840b-209">-User</span></span>
<span data-ttu-id="5840b-210">Указывает пользователей, которые активируют запуск *AtLogon* запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="5840b-210">Specifies the users who trigger an *AtLogon* start of a scheduled job.</span></span>
<span data-ttu-id="5840b-211">Введите имя пользователя в \<UserName\> \<Domain\Username\> формате или введите звездочку ( \* ) для представления всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="5840b-211">Enter the name of a user in \<UserName\> or \<Domain\Username\> format or enter an asterisk (\*) to represent all users.</span></span>
<span data-ttu-id="5840b-212">По умолчанию заданы все пользователи.</span><span class="sxs-lookup"><span data-stu-id="5840b-212">The default value is all users.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5840b-213">— Еженедельно</span><span class="sxs-lookup"><span data-stu-id="5840b-213">-Weekly</span></span>
<span data-ttu-id="5840b-214">Указывает регулярное еженедельное расписание задания.</span><span class="sxs-lookup"><span data-stu-id="5840b-214">Specifies a recurring weekly job schedule.</span></span>
<span data-ttu-id="5840b-215">Используйте другие параметры из набора *еженедельных* параметров, чтобы указать сведения о расписании.</span><span class="sxs-lookup"><span data-stu-id="5840b-215">Use the other parameters in the *Weekly* parameter set to specify the schedule details.</span></span>

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

### <span data-ttu-id="5840b-216">-Виксинтервал</span><span class="sxs-lookup"><span data-stu-id="5840b-216">-WeeksInterval</span></span>
<span data-ttu-id="5840b-217">Указывает количество недель между выполнениями для еженедельного расписания.</span><span class="sxs-lookup"><span data-stu-id="5840b-217">Specifies the number of weeks between occurrences on a weekly job schedule.</span></span>
<span data-ttu-id="5840b-218">Например, при значении 3 запланированное задание запускается в следующие недели: 1, 4, 7 и т. д.</span><span class="sxs-lookup"><span data-stu-id="5840b-218">For example, a value of 3 starts the scheduled job on weeks 1, 4, 7 and so on.</span></span>
<span data-ttu-id="5840b-219">Значение по умолчанию — 1.</span><span class="sxs-lookup"><span data-stu-id="5840b-219">The default value is 1.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5840b-220">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="5840b-220">CommonParameters</span></span>
<span data-ttu-id="5840b-221">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5840b-221">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5840b-222">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5840b-222">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5840b-223">Входные данные</span><span class="sxs-lookup"><span data-stu-id="5840b-223">INPUTS</span></span>

### <span data-ttu-id="5840b-224">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span><span class="sxs-lookup"><span data-stu-id="5840b-224">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span></span>
<span data-ttu-id="5840b-225">Можно передать несколько триггеров задания в командлет **Set-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="5840b-225">You can pipe multiple job triggers to **Set-JobTrigger** .</span></span>

## <span data-ttu-id="5840b-226">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="5840b-226">OUTPUTS</span></span>

### <span data-ttu-id="5840b-227">Нет или Microsoft. PowerShell. ScheduledJob. ScheduledJobTrigger</span><span class="sxs-lookup"><span data-stu-id="5840b-227">None or Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span></span>
<span data-ttu-id="5840b-228">При использовании параметра *Passthru* командлет **Set-JobTrigger** возвращает триггеры задания, которые были изменены.</span><span class="sxs-lookup"><span data-stu-id="5840b-228">When you use the *Passthru* parameter, **Set-JobTrigger** returns the job triggers that were changed.</span></span>
<span data-ttu-id="5840b-229">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="5840b-229">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="5840b-230">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="5840b-230">NOTES</span></span>

* <span data-ttu-id="5840b-231">Триггеры задания имеют свойство JobDefintion, которое связывает их с запланированным заданием.</span><span class="sxs-lookup"><span data-stu-id="5840b-231">Job triggers have a JobDefintion property that associates them with the scheduled job.</span></span> <span data-ttu-id="5840b-232">При изменении триггера запланированного заданий изменяется и это задание.</span><span class="sxs-lookup"><span data-stu-id="5840b-232">When you change the job trigger of a scheduled job, the job is changed.</span></span> <span data-ttu-id="5840b-233">Для применения измененного триггера к запланированному заданию не нужно использовать команду Set-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="5840b-233">You do not need to use a Set-ScheduledJob command to apply the changed trigger to the scheduled job.</span></span>

## <span data-ttu-id="5840b-234">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="5840b-234">RELATED LINKS</span></span>

[<span data-ttu-id="5840b-235">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="5840b-235">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="5840b-236">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="5840b-236">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="5840b-237">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="5840b-237">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="5840b-238">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="5840b-238">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="5840b-239">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="5840b-239">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="5840b-240">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="5840b-240">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="5840b-241">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="5840b-241">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="5840b-242">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="5840b-242">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="5840b-243">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="5840b-243">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="5840b-244">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="5840b-244">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="5840b-245">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="5840b-245">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="5840b-246">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="5840b-246">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="5840b-247">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="5840b-247">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="5840b-248">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="5840b-248">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="5840b-249">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="5840b-249">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="5840b-250">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="5840b-250">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
