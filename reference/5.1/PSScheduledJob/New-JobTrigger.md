---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/new-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-JobTrigger
ms.openlocfilehash: de49ab937c6f3a8187f5aecd6aafc81425b8cd00
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227377"
---
# <span data-ttu-id="af71e-103">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="af71e-103">New-JobTrigger</span></span>

## <span data-ttu-id="af71e-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="af71e-104">SYNOPSIS</span></span>
<span data-ttu-id="af71e-105">Создает триггер задания для запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="af71e-105">Creates a job trigger for a scheduled job.</span></span>

## <span data-ttu-id="af71e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="af71e-106">SYNTAX</span></span>

### <span data-ttu-id="af71e-107">Однократно (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="af71e-107">Once (Default)</span></span>

```
New-JobTrigger [-RandomDelay <TimeSpan>] -At <DateTime> [-Once] [-RepetitionInterval <TimeSpan>]
 [-RepetitionDuration <TimeSpan>] [-RepeatIndefinitely] [<CommonParameters>]
```

### <span data-ttu-id="af71e-108">Ежедневно</span><span class="sxs-lookup"><span data-stu-id="af71e-108">Daily</span></span>

```
New-JobTrigger [-DaysInterval <Int32>] [-RandomDelay <TimeSpan>] -At <DateTime> [-Daily] [<CommonParameters>]
```

### <span data-ttu-id="af71e-109">Weekly (Еженедельно);</span><span class="sxs-lookup"><span data-stu-id="af71e-109">Weekly</span></span>

```
New-JobTrigger [-WeeksInterval <Int32>] [-RandomDelay <TimeSpan>] -At <DateTime> -DaysOfWeek <DayOfWeek[]>
 [-Weekly] [<CommonParameters>]
```

### <span data-ttu-id="af71e-110">AtStartup</span><span class="sxs-lookup"><span data-stu-id="af71e-110">AtStartup</span></span>

```
New-JobTrigger [-RandomDelay <TimeSpan>] [-AtStartup] [<CommonParameters>]
```

### <span data-ttu-id="af71e-111">AtLogon</span><span class="sxs-lookup"><span data-stu-id="af71e-111">AtLogon</span></span>

```
New-JobTrigger [-RandomDelay <TimeSpan>] [-User <String>] [-AtLogOn] [<CommonParameters>]
```

## <span data-ttu-id="af71e-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="af71e-112">DESCRIPTION</span></span>
<span data-ttu-id="af71e-113">Командлет **New-JobTrigger** создает триггер задания, который запускает запланированное задание при однократном или повторяющемся расписании или при возникновении события.</span><span class="sxs-lookup"><span data-stu-id="af71e-113">The **New-JobTrigger** cmdlet creates a job trigger that starts a scheduled job on a one-time or recurring schedule, or when an event occurs.</span></span>

<span data-ttu-id="af71e-114">Можно использовать объект **ScheduledJobTrigger** , возвращаемый **New-JobTrigger** , чтобы задать триггер задания для нового или существующего запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="af71e-114">You can use the **ScheduledJobTrigger** object that **New-JobTrigger** returns to set a job trigger for a new or existing scheduled job.</span></span>
<span data-ttu-id="af71e-115">Можно также создать триггер задания с помощью командлета Get-JobTrigger, чтобы получить триггер задания для существующего запланированного задания или использовать значение хэш-таблицы для представления триггера задания.</span><span class="sxs-lookup"><span data-stu-id="af71e-115">You can also create a job trigger by using the Get-JobTrigger cmdlet to get the job trigger of an existing scheduled job, or by using a hash table value to represent a job trigger.</span></span>

<span data-ttu-id="af71e-116">При создании триггера задания проверьте значения по умолчанию для параметров, заданных в командлете New-ScheduledJobOption.</span><span class="sxs-lookup"><span data-stu-id="af71e-116">When creating a job trigger, review the default values of the options specified by the New-ScheduledJobOption cmdlet.</span></span>
<span data-ttu-id="af71e-117">Эти свойства, у которых допустимые значения и значения по умолчанию совпадают с соответствующими параметрами в **Task Scheduler** , влияют на график и периодичность запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="af71e-117">These options, which have the same valid and default values as the corresponding options in **Task Scheduler** , affect the scheduling and timing of scheduled jobs.</span></span>

<span data-ttu-id="af71e-118">**New-JobTrigger** — это одна из коллекций командлетов планирования заданий в модуле PSScheduledJob, который входит в состав Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af71e-118">**New-JobTrigger** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="af71e-119">Дополнительные сведения о запланированных заданиях см. в разделах описания в модуле PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="af71e-119">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="af71e-120">Импортируйте модуль PSScheduledJob, а затем введите `Get-Help about_Scheduled*` или просмотрите статью about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="af71e-120">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="af71e-121">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="af71e-121">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="af71e-122">Примеры</span><span class="sxs-lookup"><span data-stu-id="af71e-122">EXAMPLES</span></span>

### <span data-ttu-id="af71e-123">Пример 1. однократное расписание</span><span class="sxs-lookup"><span data-stu-id="af71e-123">Example 1: Once Schedule</span></span>

```
PS C:\> New-JobTrigger -Once -At "1/20/2012 3:00 AM"
```

<span data-ttu-id="af71e-124">Эта команда использует командлет **New-JobTrigger** , чтобы создать триггер задания, который запускает запланированное задание только один раз.</span><span class="sxs-lookup"><span data-stu-id="af71e-124">This command uses the **New-JobTrigger** cmdlet to create a job trigger that starts a scheduled job only one time.</span></span>
<span data-ttu-id="af71e-125">Значение параметра *At* представляет собой строку, которую Windows PowerShell преобразует в объект **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="af71e-125">The value of the *At* parameter is a string that Windows PowerShell converts into a **DateTime** object.</span></span>
<span data-ttu-id="af71e-126">Значение параметра *At* включает в себя не только время, но и дату в явном виде.</span><span class="sxs-lookup"><span data-stu-id="af71e-126">The *At* parameter value includes an explicit date, not just a time.</span></span>
<span data-ttu-id="af71e-127">Если дата была пропущена, триггер создается с текущей датой и временем 3:00, что с большой вероятностью относится ко времени в прошлом.</span><span class="sxs-lookup"><span data-stu-id="af71e-127">If the date were omitted, the trigger would be created with the current date and 3:00 AM time, which is likely to represent a time in the past.</span></span>

### <span data-ttu-id="af71e-128">Пример 2. ежедневное расписание</span><span class="sxs-lookup"><span data-stu-id="af71e-128">Example 2: Daily Schedule</span></span>

```
PS C:\> New-JobTrigger -Daily -At "4:15 AM" -DaysInterval 3
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
0          Daily           9/21/2012 4:15:00 AM                           True
```

<span data-ttu-id="af71e-129">Эта команда создает триггер задания, который запускает запланированное задание каждые 3 дня в 4:15.</span><span class="sxs-lookup"><span data-stu-id="af71e-129">This command creates a job trigger that starts a scheduled job every 3 days at 4:15 a.m.</span></span>

<span data-ttu-id="af71e-130">Поскольку значение параметра *At* не включает в себя дату, в качестве значения даты в объекте **DateTime** используется текущая дата.</span><span class="sxs-lookup"><span data-stu-id="af71e-130">Because the value of the *At* parameter does not include a date, the current date is used as the date value in the **DateTime** object.</span></span>
<span data-ttu-id="af71e-131">Если дата и время относятся к прошлому, запланированное задание запускается в следующий допустимый момент, который на 3 дня позднее значения параметра *At* .</span><span class="sxs-lookup"><span data-stu-id="af71e-131">If the date and time is in the past, the scheduled job is started at the next occurrence, which is 3 days later from the *At* parameter value.</span></span>

### <span data-ttu-id="af71e-132">Пример 3. еженедельное расписание</span><span class="sxs-lookup"><span data-stu-id="af71e-132">Example 3: Weekly Schedule</span></span>

```
PS C:\> New-JobTrigger -Weekly -DaysOfWeek Monday, Wednesday, Friday -At "23:00" -WeeksInterval 4
Id Frequency Time                  DaysOfWeek                  Enabled
-- --------- ----                  ----------                  -------
0  Weekly    9/21/2012 11:00:00 PM {Monday, Wednesday, Friday} True
```

<span data-ttu-id="af71e-133">Эта команда создает триггер задания, который запускает запланированное задание каждые 4 недели в понедельник, среду и пятницу в 23:00.</span><span class="sxs-lookup"><span data-stu-id="af71e-133">This command creates a job trigger that starts a scheduled job every 4 weeks on Monday, Wednesday, and Friday at 2300 hours (11:00 PM).</span></span>

<span data-ttu-id="af71e-134">Можно также ввести значение параметра *DaysOfWeek* в целых числах, например `-DaysOfWeek 1, 5` .</span><span class="sxs-lookup"><span data-stu-id="af71e-134">You can also enter the *DaysOfWeek* parameter value in integers, such as `-DaysOfWeek 1, 5`.</span></span>

### <span data-ttu-id="af71e-135">Пример 4. расписание входа</span><span class="sxs-lookup"><span data-stu-id="af71e-135">Example 4: Logon Schedule</span></span>

```
PS C:\> New-JobTrigger -AtLogOn -User Domain01\Admin01
```

<span data-ttu-id="af71e-136">Эта команда создает триггер задания, который запускает запланированное задание каждый раз, когда администратор домена выполняет вход в систему на компьютере.</span><span class="sxs-lookup"><span data-stu-id="af71e-136">This command creates a job trigger that starts a scheduled job whenever the domain administrator logs onto the computer.</span></span>

### <span data-ttu-id="af71e-137">Пример 5. использование случайной задержки</span><span class="sxs-lookup"><span data-stu-id="af71e-137">Example 5: Using a Random Delay</span></span>

```
PS C:\> New-JobTrigger -Daily -At 1:00 -RandomDelay 00:20:00
```

<span data-ttu-id="af71e-138">Эта команда создает триггер задания, который запускает запланированное задание каждый день в 1:00.</span><span class="sxs-lookup"><span data-stu-id="af71e-138">This command creates a job trigger that starts a scheduled job every day at 1:00 in the morning.</span></span>
<span data-ttu-id="af71e-139">Команда использует параметр *RandomDelay* для указания максимальной задержки (до 20 минут).</span><span class="sxs-lookup"><span data-stu-id="af71e-139">The command uses the *RandomDelay* parameter to set the maximum delay to 20 minutes.</span></span>
<span data-ttu-id="af71e-140">В результате задание выполняется ежедневно в интервале с 1:00 до 1:20, изменяющемся псевдослучайным образом.</span><span class="sxs-lookup"><span data-stu-id="af71e-140">As a result, the job runs every day between 1:00 AM and 1:20 AM, with the interval varying pseudo-randomly.</span></span>

<span data-ttu-id="af71e-141">Случайную задержку можно использовать для выборки, балансировки нагрузки и других административных задач.</span><span class="sxs-lookup"><span data-stu-id="af71e-141">You can use a random delay for sampling, load balancing, and other administrative tasks.</span></span>
<span data-ttu-id="af71e-142">При задании значения задержки изучите действующие и значения по умолчанию для командлета New-ScheduledJobOption и согласуйте задержку с настройками параметров.</span><span class="sxs-lookup"><span data-stu-id="af71e-142">When setting the delay value, review the effective and default values of the New-ScheduledJobOption cmdlet and coordinate the delay with the option settings.</span></span>

### <span data-ttu-id="af71e-143">Пример 6. Создание триггера задания для нового запланированного задания</span><span class="sxs-lookup"><span data-stu-id="af71e-143">Example 6: Create a Job Trigger for a New Scheduled Job</span></span>

```
The first command uses the **New-JobTrigger** cmdlet to create a job trigger that starts a job every Monday, Wednesday, and Friday at 12:01 AM. The command saves the job trigger in the $T variable.
PS C:\> $T = New-JobTrigger -Weekly -DaysOfWeek 1,3,5 -At 12:01AM


The second command uses the Register-ScheduledJob cmdlet to create a scheduled job that starts a job every Monday, Wednesday, and Friday at 12:01 AM. The value of the *Trigger* parameter is the trigger that is stored in the $T variable.
PS C:\> Register-ScheduledJob -Name Test-HelpFiles -FilePath C:\Scripts\Test-HelpFiles.ps1 -Trigger $T
```

<span data-ttu-id="af71e-144">Эти команды используют триггер задания для создания нового запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="af71e-144">These commands use a job trigger to create a new scheduled job.</span></span>

### <span data-ttu-id="af71e-145">Пример 7. добавление триггера задания в запланированное задание</span><span class="sxs-lookup"><span data-stu-id="af71e-145">Example 7: Add a Job Trigger to a Scheduled Job</span></span>

```
PS C:\> Add-JobTrigger -Name SynchronizeApps -Trigger (New-JobTrigger -Daily -At 3:10AM)
```

<span data-ttu-id="af71e-146">В этом примере показано, как добавить триггер задания в существующее запланированное задания.</span><span class="sxs-lookup"><span data-stu-id="af71e-146">This example shows how to add a job trigger to an existing scheduled job.</span></span>
<span data-ttu-id="af71e-147">Для любого запланированного задания можно добавить несколько триггеров задания.</span><span class="sxs-lookup"><span data-stu-id="af71e-147">You can add multiple job triggers to any scheduled job.</span></span>

<span data-ttu-id="af71e-148">Команда использует командлет Add-JobTrigger, чтобы добавить триггер задания в запланированное задание Синчронизеаппс.</span><span class="sxs-lookup"><span data-stu-id="af71e-148">The command uses the Add-JobTrigger cmdlet to add the job trigger to the SynchronizeApps scheduled job.</span></span>
<span data-ttu-id="af71e-149">Значением параметра *Trigger* является команда **New-JobTrigger** , которая запускает задание каждый день в 3:10.</span><span class="sxs-lookup"><span data-stu-id="af71e-149">The value of the *Trigger* parameter is a **New-JobTrigger** command that runs the job every day at 3:10 AM.</span></span>

<span data-ttu-id="af71e-150">После завершения выполнения команды SynchronizeApps становится запланированным заданием, которое запускается во время, заданное триггером задания.</span><span class="sxs-lookup"><span data-stu-id="af71e-150">When the command completes, SynchronizeApps is a scheduled job that runs at the times specified by the job trigger.</span></span>

### <span data-ttu-id="af71e-151">Пример 8. Создание повторяющегося триггера задания</span><span class="sxs-lookup"><span data-stu-id="af71e-151">Example 8: Create a repeating job trigger</span></span>

```
PS C:\> New-JobTrigger -Once -At "09/12/2013 1:00:00" -RepetitionInterval (New-TimeSpan -Hours 1) -RepetitionDuration (New-Timespan -Hours 48)
```

<span data-ttu-id="af71e-152">Эта команда создает триггер задания, который запускает задание каждые 60 минут в течение 48 часов, начиная с 12 сентября 2013 в 1:00 AM.</span><span class="sxs-lookup"><span data-stu-id="af71e-152">This command creates a job trigger that runs a job every 60 minutes for 48 hours beginning on September 12, 2013 at 1:00 AM.</span></span>

### <span data-ttu-id="af71e-153">Пример 9. Завершение повторяющегося триггера задания</span><span class="sxs-lookup"><span data-stu-id="af71e-153">Example 9: Stop a repeating job trigger</span></span>

```
PS C:\> Get-JobTrigger -Name SecurityCheck | Set-JobTrigger -RepetitionInterval 0:00 -RepetitionDuration 0:00
```

<span data-ttu-id="af71e-154">Эта команда принудительно останавливает задание SecurityCheck, которое активируется для запуска каждые 60 минут до истечения срока действия триггера задания.</span><span class="sxs-lookup"><span data-stu-id="af71e-154">This command forcibly stops the SecurityCheck job, which is triggered to run every 60 minutes until its job trigger expires.</span></span>

<span data-ttu-id="af71e-155">Чтобы предотвратить повторение задания, команда использует Get-JobTrigger для получения триггера задания задания Секуритичекк и командлета Set-JobTrigger, чтобы изменить интервал повтора и длительность повтора для триггера задания на ноль (0).</span><span class="sxs-lookup"><span data-stu-id="af71e-155">To prevent the job from repeating, the command uses the Get-JobTrigger to get the job trigger of the SecurityCheck job and the Set-JobTrigger cmdlet to change the repetition interval and repetition duration of the job trigger to zero (0).</span></span>

### <span data-ttu-id="af71e-156">Пример 10. Создание триггера ежечасного задания</span><span class="sxs-lookup"><span data-stu-id="af71e-156">Example 10: Create an hourly job trigger</span></span>

```
PS C:\> New-JobTrigger -Once -At "9/21/2012 0am" -RepetitionInterval (New-TimeSpan -Hour 12) -RepetitionDuration ([TimeSpan]::MaxValue)
```

<span data-ttu-id="af71e-157">Следующая команда создает триггер задания, который запускает запланированное задание каждые 12 часов в течение неопределенного периода времени.</span><span class="sxs-lookup"><span data-stu-id="af71e-157">The following command creates a job trigger that runs a scheduled job once every 12 hours for an indefinite period of time.</span></span>
<span data-ttu-id="af71e-158">Расписание начинается завтра (9/21/2012) в полночь (0:00).</span><span class="sxs-lookup"><span data-stu-id="af71e-158">The schedule begins tomorrow (9/21/2012) at midnight (0:00 AM).</span></span>

## <span data-ttu-id="af71e-159">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="af71e-159">PARAMETERS</span></span>

### <span data-ttu-id="af71e-160">-At</span><span class="sxs-lookup"><span data-stu-id="af71e-160">-At</span></span>
<span data-ttu-id="af71e-161">Запускает задание в указанный день и указанное время.</span><span class="sxs-lookup"><span data-stu-id="af71e-161">Starts the job at the specified date and time.</span></span>
<span data-ttu-id="af71e-162">Введите объект **DateTime** , например, возвращаемый командлетом Get-Date, или строку, которую можно преобразовать в дату и время, например "19 апреля, 2012 15:00", "12/31" или "03:00".</span><span class="sxs-lookup"><span data-stu-id="af71e-162">Enter a **DateTime** object, such as one that the Get-Date cmdlet returns, or a string that can be converted to a date and time, such as "April 19, 2012 15:00", "12/31", or "3am".</span></span>
<span data-ttu-id="af71e-163">Если не указать элемент даты, например год, дата в триггере имеет соответствующий элемент с учетом текущей даты.</span><span class="sxs-lookup"><span data-stu-id="af71e-163">If you don't specify an element of the date, such as the year, the date in the trigger has the corresponding element from the current date.</span></span>

<span data-ttu-id="af71e-164">При использовании параметра *Once* задайте в качестве значения параметра *At* дату и время в будущем.</span><span class="sxs-lookup"><span data-stu-id="af71e-164">When using the *Once* parameter, set the value of the *At* parameter to a future date and time.</span></span>
<span data-ttu-id="af71e-165">Поскольку по умолчанию дата в объекте **DateTime** является текущей, при указании момента времени до текущего времени без явной даты триггер задания создается для времени в прошлом.</span><span class="sxs-lookup"><span data-stu-id="af71e-165">Because the default date in a **DateTime** object is the current date, if you specify a time before the current time without an explicit date, the job trigger is created for a time in the past.</span></span>

<span data-ttu-id="af71e-166">Объекты **DateTime** и строки, которые преобразуются в объекты **DateTime** , автоматически настраиваются для совместимости с форматами даты и времени, выбранными для локального компьютера в области и языка на панели управления.</span><span class="sxs-lookup"><span data-stu-id="af71e-166">**DateTime** objects, and strings that are converted to **DateTime** objects, are automatically adjusted to be compatible with the date and time formats selected for the local computer in Region and Language in Control Panel.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: Once, Daily, Weekly
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af71e-167">-AtLogOn</span><span class="sxs-lookup"><span data-stu-id="af71e-167">-AtLogOn</span></span>
<span data-ttu-id="af71e-168">Запускает запланированное задание при входе указанных пользователей на компьютер.</span><span class="sxs-lookup"><span data-stu-id="af71e-168">Starts the scheduled job when the specified users log on to the computer.</span></span>
<span data-ttu-id="af71e-169">Чтобы указать пользователя, используйте параметр *User* .</span><span class="sxs-lookup"><span data-stu-id="af71e-169">To specify a user, use the *User* parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AtLogon
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af71e-170">-AtStartup</span><span class="sxs-lookup"><span data-stu-id="af71e-170">-AtStartup</span></span>
<span data-ttu-id="af71e-171">Запускает запланированное задание при запуске Windows.</span><span class="sxs-lookup"><span data-stu-id="af71e-171">Starts the scheduled job when Windows starts.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AtStartup
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af71e-172">— Ежедневно</span><span class="sxs-lookup"><span data-stu-id="af71e-172">-Daily</span></span>
<span data-ttu-id="af71e-173">Указывает регулярное ежедневное расписание задания.</span><span class="sxs-lookup"><span data-stu-id="af71e-173">Specifies a recurring daily job schedule.</span></span>
<span data-ttu-id="af71e-174">Используйте другие параметры из набора *ежедневных* параметров, чтобы указать сведения о расписании.</span><span class="sxs-lookup"><span data-stu-id="af71e-174">Use the other parameters in the *Daily* parameter set to specify the schedule details.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Daily
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af71e-175">-Дайсинтервал</span><span class="sxs-lookup"><span data-stu-id="af71e-175">-DaysInterval</span></span>
<span data-ttu-id="af71e-176">Указывает количество дней между выполнениями для ежедневного расписания.</span><span class="sxs-lookup"><span data-stu-id="af71e-176">Specifies the number of days between occurrences on a daily schedule.</span></span>
<span data-ttu-id="af71e-177">Например, при значении 3 запланированное задание запускается в следующие дни: 1, 4, 7 и т. д.</span><span class="sxs-lookup"><span data-stu-id="af71e-177">For example, a value of 3 starts the scheduled job on days 1, 4, 7 and so on.</span></span>
<span data-ttu-id="af71e-178">Значение по умолчанию — 1.</span><span class="sxs-lookup"><span data-stu-id="af71e-178">The default value is 1.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Daily
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af71e-179">-DaysOfWeek</span><span class="sxs-lookup"><span data-stu-id="af71e-179">-DaysOfWeek</span></span>
<span data-ttu-id="af71e-180">Указывает дни недели, по которым выполняется запланированное задание.</span><span class="sxs-lookup"><span data-stu-id="af71e-180">Specifies the days of the week on which a weekly scheduled job runs.</span></span>
<span data-ttu-id="af71e-181">Введите названия дней, например Monday, или целые числа от 0 до 6, где 0 — воскресенье.</span><span class="sxs-lookup"><span data-stu-id="af71e-181">Enter day names, such as "Monday" or integers 0-6, where 0 represents Sunday.</span></span>
<span data-ttu-id="af71e-182">Этот параметр необходим в наборе параметров Weekly.</span><span class="sxs-lookup"><span data-stu-id="af71e-182">This parameter is required in the Weekly parameter set.</span></span>

<span data-ttu-id="af71e-183">Названия дней преобразуются в их целочисленные значения в триггере задания.</span><span class="sxs-lookup"><span data-stu-id="af71e-183">Day names are converted to their integer values in the job trigger.</span></span>
<span data-ttu-id="af71e-184">В команде заключайте название каждого дня в отдельные кавычки, например Monday, Tuesday.</span><span class="sxs-lookup"><span data-stu-id="af71e-184">When you enclose day names in quotation marks in a command, enclose each day name in separate quotation marks, such as "Monday", "Tuesday".</span></span>
<span data-ttu-id="af71e-185">Если заключить несколько названий дней в одну пару одинарных кавычек, соответствующие целые значения суммируются.</span><span class="sxs-lookup"><span data-stu-id="af71e-185">If you enclose multiple day names in a single quotation mark pair, the corresponding integer values are summed.</span></span>
<span data-ttu-id="af71e-186">Например, Monday, Tuesday (1, 2) дает значение Wednesday (3).</span><span class="sxs-lookup"><span data-stu-id="af71e-186">For example, "Monday, Tuesday" (1, 2) results in a value of "Wednesday" (3).</span></span>

```yaml
Type: System.DayOfWeek[]
Parameter Sets: Weekly
Aliases:
Accepted values: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af71e-187">-Один раз</span><span class="sxs-lookup"><span data-stu-id="af71e-187">-Once</span></span>
<span data-ttu-id="af71e-188">Задает разовое (неповторяющееся) или пользовательское расписание.</span><span class="sxs-lookup"><span data-stu-id="af71e-188">Specifies a non-recurring (one time) or custom repeating schedule.</span></span>
<span data-ttu-id="af71e-189">Чтобы создать повторяющееся расписание, используйте параметр *Once* с параметрами *RepetitionDuration* и *RepetitionInterval* .</span><span class="sxs-lookup"><span data-stu-id="af71e-189">To create a repeating schedule, use the *Once* parameter with the *RepetitionDuration* and *RepetitionInterval* parameters.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Once
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af71e-190">-Рандомделай</span><span class="sxs-lookup"><span data-stu-id="af71e-190">-RandomDelay</span></span>
<span data-ttu-id="af71e-191">Включает случайную задержку, которая начинается в запланированное время начала, и задает максимальное значение этой задержки.</span><span class="sxs-lookup"><span data-stu-id="af71e-191">Enables a random delay that begins at the scheduled start time, and sets the maximum delay value.</span></span>
<span data-ttu-id="af71e-192">Длительность задержки задается для каждого запуска псевдослучайным образом и лежит в диапазоне от нуля до значения этого параметра.</span><span class="sxs-lookup"><span data-stu-id="af71e-192">The length of the delay is set pseudo-randomly for each start and varies from no delay to the time specified by the value of this parameter.</span></span>
<span data-ttu-id="af71e-193">Нулевое значение по умолчанию (00:00:00) отключает случайную задержку.</span><span class="sxs-lookup"><span data-stu-id="af71e-193">The default value, zero (00:00:00), disables the random delay.</span></span>

<span data-ttu-id="af71e-194">Введите объект TimeSpan, например возвращаемый командлетом New-TimeSpan, или введите значение в \<hours\> \<minutes\> формате:: \<seconds\> Format, которое автоматически преобразуется в объект **TimeSpan** .</span><span class="sxs-lookup"><span data-stu-id="af71e-194">Enter a timespan object, such as one returned by the New-TimeSpan cmdlet, or enter a value in \<hours\>:\<minutes\>:\<seconds\> format, which is automatically converted to a **TimeSpan** object.</span></span>

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

### <span data-ttu-id="af71e-195">-RepeatIndefinitely</span><span class="sxs-lookup"><span data-stu-id="af71e-195">-RepeatIndefinitely</span></span>
<span data-ttu-id="af71e-196">Этот параметр, который доступен, начиная с Windows PowerShell 4.0, устраняет необходимость в указании значения **TimeSpan.MaxValue** параметра *RepetitionDuration* для выполнения задания по расписанию в течение неопределенного времени.</span><span class="sxs-lookup"><span data-stu-id="af71e-196">This parameter, available starting in Windows PowerShell 4.0, eliminates the necessity of specifying a **TimeSpan.MaxValue** value for the *RepetitionDuration* parameter to run a scheduled job repeatedly, for an indefinite period.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af71e-197">-RepetitionDuration</span><span class="sxs-lookup"><span data-stu-id="af71e-197">-RepetitionDuration</span></span>
<span data-ttu-id="af71e-198">Повторяет задание до истечения заданного времени.</span><span class="sxs-lookup"><span data-stu-id="af71e-198">Repeats the job until the specified time expires.</span></span>
<span data-ttu-id="af71e-199">Частота повторения определяется значением параметра *RepetitionInterval* .</span><span class="sxs-lookup"><span data-stu-id="af71e-199">The repetition frequency is determined by the value of the *RepetitionInterval* parameter.</span></span>
<span data-ttu-id="af71e-200">Например, если значение **RepetitionInterval** составляет 5 минут, а значение **RepetitionDuration** составляет 2 часа, задание запускается каждые пять минут в течение двух часов.</span><span class="sxs-lookup"><span data-stu-id="af71e-200">For example, if the value of **RepetitionInterval** is 5 minutes and the value of **RepetitionDuration** is 2 hours, the job is triggered every five minutes for two hours.</span></span>

<span data-ttu-id="af71e-201">Введите объект TimeSpan, например, возвращаемый командлетом New-TimeSpan, или строку, которую можно преобразовать в объект TimeSpan, например "1:05:30".</span><span class="sxs-lookup"><span data-stu-id="af71e-201">Enter a timespan object, such as one that the New-TimeSpan cmdlet returns or a string that can be converted to a timespan object, such as "1:05:30".</span></span>

<span data-ttu-id="af71e-202">Для бессрочного выполнения задания добавьте вместо этого параметр *RepeatIndefinitely* .</span><span class="sxs-lookup"><span data-stu-id="af71e-202">To run a job indefinitely, add the *RepeatIndefinitely* parameter instead.</span></span>

<span data-ttu-id="af71e-203">Чтобы прерывать задание до истечения срока действия триггера задания, используйте командлет Set-JobTrigger, чтобы установить значение *RepetitionDuration* равным нулю (0).</span><span class="sxs-lookup"><span data-stu-id="af71e-203">To stop a job before the job trigger repetition duration expires, use the Set-JobTrigger cmdlet to set the *RepetitionDuration* value to zero (0).</span></span>

<span data-ttu-id="af71e-204">Этот параметр активен, только если в команде также используются параметры *Once* , *At* и *RepetitionInterval* .</span><span class="sxs-lookup"><span data-stu-id="af71e-204">This parameter is valid only when the *Once* , *At* and *RepetitionInterval* parameters are used in the command.</span></span>

```yaml
Type: System.TimeSpan
Parameter Sets: Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af71e-205">-Репетитионинтервал</span><span class="sxs-lookup"><span data-stu-id="af71e-205">-RepetitionInterval</span></span>
<span data-ttu-id="af71e-206">Повторяет задание с определенным интервалом.</span><span class="sxs-lookup"><span data-stu-id="af71e-206">Repeats the job at the specified time interval.</span></span>
<span data-ttu-id="af71e-207">Например, если значение этого параметра равно 2 часам, задание активируется каждые два часа.</span><span class="sxs-lookup"><span data-stu-id="af71e-207">For example, if the value of this parameter is 2 hours, the job is triggered every two hours.</span></span>
<span data-ttu-id="af71e-208">При использовании нулевого значения по умолчанию задание не запускается повторно.</span><span class="sxs-lookup"><span data-stu-id="af71e-208">The default value, 0, does not repeat the job.</span></span>

<span data-ttu-id="af71e-209">Введите объект TimeSpan, например, возвращаемый командлетом New-TimeSpan, или строку, которую можно преобразовать в объект TimeSpan, например "1:05:30".</span><span class="sxs-lookup"><span data-stu-id="af71e-209">Enter a timespan object, such as one that the New-TimeSpan cmdlet returns or a string that can be converted to a timespan object, such as "1:05:30".</span></span>

<span data-ttu-id="af71e-210">Этот параметр активен, только если в команде также используются параметры *Once* , *At* и *RepetitionDuration* .</span><span class="sxs-lookup"><span data-stu-id="af71e-210">This parameter is valid only when the *Once* , *At* , and *RepetitionDuration* parameters are used in the command.</span></span>

```yaml
Type: System.TimeSpan
Parameter Sets: Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af71e-211">-User</span><span class="sxs-lookup"><span data-stu-id="af71e-211">-User</span></span>
<span data-ttu-id="af71e-212">Указывает пользователей, которые активируют запуск *AtLogon* запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="af71e-212">Specifies the users who trigger an *AtLogon* start of a scheduled job.</span></span>
<span data-ttu-id="af71e-213">Введите имя пользователя в \<UserName\> \<Domain\Username\> формате или введите звездочку ( \* ) для представления всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="af71e-213">Enter the name of a user in \<UserName\> or \<Domain\Username\> format or enter an asterisk (\*) to represent all users.</span></span>
<span data-ttu-id="af71e-214">По умолчанию заданы все пользователи.</span><span class="sxs-lookup"><span data-stu-id="af71e-214">The default value is all users.</span></span>

```yaml
Type: System.String
Parameter Sets: AtLogon
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af71e-215">— Еженедельно</span><span class="sxs-lookup"><span data-stu-id="af71e-215">-Weekly</span></span>
<span data-ttu-id="af71e-216">Указывает регулярное еженедельное расписание задания.</span><span class="sxs-lookup"><span data-stu-id="af71e-216">Specifies a recurring weekly job schedule.</span></span>
<span data-ttu-id="af71e-217">Используйте другие параметры в наборе параметров Weekly, чтобы указать сведения о расписании.</span><span class="sxs-lookup"><span data-stu-id="af71e-217">Use the other parameters in the Weekly parameter set to specify the schedule details.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Weekly
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af71e-218">-Виксинтервал</span><span class="sxs-lookup"><span data-stu-id="af71e-218">-WeeksInterval</span></span>
<span data-ttu-id="af71e-219">Указывает количество недель между выполнениями для еженедельного расписания.</span><span class="sxs-lookup"><span data-stu-id="af71e-219">Specifies the number of weeks between occurrences on a weekly job schedule.</span></span>
<span data-ttu-id="af71e-220">Например, при значении 3 запланированное задание запускается в следующие недели: 1, 4, 7 и т. д.</span><span class="sxs-lookup"><span data-stu-id="af71e-220">For example, a value of 3 starts the scheduled job on weeks 1, 4, 7 and so on.</span></span>
<span data-ttu-id="af71e-221">Значение по умолчанию — 1.</span><span class="sxs-lookup"><span data-stu-id="af71e-221">The default value is 1.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Weekly
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af71e-222">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="af71e-222">CommonParameters</span></span>
<span data-ttu-id="af71e-223">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="af71e-223">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="af71e-224">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="af71e-224">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="af71e-225">Входные данные</span><span class="sxs-lookup"><span data-stu-id="af71e-225">INPUTS</span></span>

### <span data-ttu-id="af71e-226">Нет</span><span class="sxs-lookup"><span data-stu-id="af71e-226">None</span></span>
<span data-ttu-id="af71e-227">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="af71e-227">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="af71e-228">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="af71e-228">OUTPUTS</span></span>

### <span data-ttu-id="af71e-229">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span><span class="sxs-lookup"><span data-stu-id="af71e-229">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span></span>

## <span data-ttu-id="af71e-230">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="af71e-230">NOTES</span></span>

* <span data-ttu-id="af71e-231">Триггеры задания не сохраняются на диск.</span><span class="sxs-lookup"><span data-stu-id="af71e-231">Job triggers are not saved to disk.</span></span> <span data-ttu-id="af71e-232">Однако запланированные задания сохраняются на диск, и вы можете использовать Get-JobTrigger, чтобы получить триггер задания для любого запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="af71e-232">However, scheduled jobs are saved to disk, and you can use the Get-JobTrigger to get the job trigger of any scheduled job.</span></span>
* <span data-ttu-id="af71e-233">**New-JobTrigger** не препятствует созданию триггера задания, который не будет выполнять запланированное задание, например одноразовый триггер для даты в прошлом.</span><span class="sxs-lookup"><span data-stu-id="af71e-233">**New-JobTrigger** does not prevent you from creating a job trigger that will not run a scheduled job, such as one-time trigger for a date in the past.</span></span>
* <span data-ttu-id="af71e-234">Командлет Register-ScheduledJob принимает объект ScheduledJobTrigger, например, возвращаемый командлетами **New-JobTrigger** или Get-JobTrigger, или хэш-таблицу со значениями триггера.</span><span class="sxs-lookup"><span data-stu-id="af71e-234">The Register-ScheduledJob cmdlet accepts a ScheduledJobTrigger object, such as one returned by the **New-JobTrigger** or Get-JobTrigger cmdlets, or a hash table with trigger values.</span></span>

  <span data-ttu-id="af71e-235">Чтобы отправить хэш-таблицу, используйте следующие ключи.</span><span class="sxs-lookup"><span data-stu-id="af71e-235">To submit a hash table, use the following keys.</span></span>

  <span data-ttu-id="af71e-236">`@{Frequency="Once" (or Daily, Weekly, AtStartup, AtLogon);At="3am"` (или любая допустимая строка времени); `DaysOfWeek="Monday", "Wednesday"` (или любое сочетание названий дней); `Interval=2` (или любой допустимый интервал частоты); `RandomDelay="30minutes"` (или любая допустимая строка TimeSpan); `User="Domain1\User01` (или любой допустимый пользователь; используется только со значением частоты *AtLogon* )}</span><span class="sxs-lookup"><span data-stu-id="af71e-236">`@{Frequency="Once" (or Daily, Weekly, AtStartup, AtLogon);At="3am"` (or any valid time string); `DaysOfWeek="Monday", "Wednesday"` (or any combination of day names); `Interval=2` (or any valid frequency interval); `RandomDelay="30minutes"` (or any valid timespan string); `User="Domain1\User01` (or any valid user; used only with the *AtLogon* frequency value) }</span></span>

## <span data-ttu-id="af71e-237">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="af71e-237">RELATED LINKS</span></span>

[<span data-ttu-id="af71e-238">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="af71e-238">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="af71e-239">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="af71e-239">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="af71e-240">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="af71e-240">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="af71e-241">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="af71e-241">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="af71e-242">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="af71e-242">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="af71e-243">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="af71e-243">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="af71e-244">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="af71e-244">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="af71e-245">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="af71e-245">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="af71e-246">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="af71e-246">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="af71e-247">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="af71e-247">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="af71e-248">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="af71e-248">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="af71e-249">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="af71e-249">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="af71e-250">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="af71e-250">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="af71e-251">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="af71e-251">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="af71e-252">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="af71e-252">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="af71e-253">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="af71e-253">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
