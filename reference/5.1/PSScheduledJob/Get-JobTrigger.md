---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/get-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-JobTrigger
ms.openlocfilehash: 7a75a5a7e6875ed88fd31ea0f385c19f1991f8d7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227385"
---
# <span data-ttu-id="a1195-103">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="a1195-103">Get-JobTrigger</span></span>

## <span data-ttu-id="a1195-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a1195-104">SYNOPSIS</span></span>
<span data-ttu-id="a1195-105">Получает триггеры задания для запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="a1195-105">Gets the job triggers of scheduled jobs.</span></span>

## <span data-ttu-id="a1195-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a1195-106">SYNTAX</span></span>

### <span data-ttu-id="a1195-107">JobDefinition (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="a1195-107">JobDefinition (Default)</span></span>

```
Get-JobTrigger [[-TriggerId] <Int32[]>] [-InputObject] <ScheduledJobDefinition> [<CommonParameters>]
```

### <span data-ttu-id="a1195-108">жобдефинитионид</span><span class="sxs-lookup"><span data-stu-id="a1195-108">JobDefinitionId</span></span>

```
Get-JobTrigger [[-TriggerId] <Int32[]>] [-Id] <Int32> [<CommonParameters>]
```

### <span data-ttu-id="a1195-109">жобдефинитионнаме</span><span class="sxs-lookup"><span data-stu-id="a1195-109">JobDefinitionName</span></span>

```
Get-JobTrigger [[-TriggerId] <Int32[]>] [-Name] <String> [<CommonParameters>]
```

## <span data-ttu-id="a1195-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a1195-110">DESCRIPTION</span></span>
<span data-ttu-id="a1195-111">Командлет **Get-JobTrigger** получает триггеры задания для запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="a1195-111">The **Get-JobTrigger** cmdlet gets the job triggers of scheduled jobs.</span></span>
<span data-ttu-id="a1195-112">Эта команда используется для проверки триггеров задания или их передачи в другие командлеты.</span><span class="sxs-lookup"><span data-stu-id="a1195-112">You can use this command to examine the job triggers or to pipe the job triggers to other cmdlets.</span></span>

<span data-ttu-id="a1195-113">Триггер задания определяет повторяющееся расписание или условия для запуска запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="a1195-113">A job trigger defines a recurring schedule or conditions for starting a scheduled job.</span></span>
<span data-ttu-id="a1195-114">Триггеры задания не сохраняются на диск независимо; они являются частью запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="a1195-114">Job triggers are not saved to disk independently; they are part of a scheduled job.</span></span>
<span data-ttu-id="a1195-115">Чтобы получить триггер задания, укажите запланированное задание, запускаемое триггером.</span><span class="sxs-lookup"><span data-stu-id="a1195-115">To get a job trigger, specify the scheduled job that the trigger starts.</span></span>

<span data-ttu-id="a1195-116">Используйте параметры командлета **Get-JobTrigger** , чтобы определить запланированные задания.</span><span class="sxs-lookup"><span data-stu-id="a1195-116">Use the parameters of the **Get-JobTrigger** cmdlet to identify the scheduled jobs.</span></span>
<span data-ttu-id="a1195-117">Запланированные задания можно определить по их именам или идентификационным номерам либо путем ввода или передачи объектов **ScheduledJob** , например, возвращаемых командлетом Get-ScheduledJob, в **Get-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="a1195-117">You can identify the scheduled jobs by their names or identification numbers, or by entering or piping **ScheduledJob** objects, such as those that are returned by the Get-ScheduledJob cmdlet, to **Get-JobTrigger** .</span></span>

<span data-ttu-id="a1195-118">**Get-JobTrigger** — это одна из коллекций командлетов планирования заданий в модуле PSScheduledJob, который входит в состав Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a1195-118">**Get-JobTrigger** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="a1195-119">Дополнительные сведения о запланированных заданиях см. в разделах описания в модуле PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="a1195-119">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="a1195-120">Импортируйте модуль PSScheduledJob, а затем введите `Get-Help about_Scheduled*` или просмотрите статью about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="a1195-120">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="a1195-121">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a1195-121">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="a1195-122">Примеры</span><span class="sxs-lookup"><span data-stu-id="a1195-122">EXAMPLES</span></span>

### <span data-ttu-id="a1195-123">Пример 1. получение триггера задания по имени запланированного задания</span><span class="sxs-lookup"><span data-stu-id="a1195-123">Example 1: Get a job trigger by scheduled job name</span></span>

```
PS C:\> Get-JobTrigger -Name "BackupJob"
```

<span data-ttu-id="a1195-124">Команда использует параметр *Name* командлета **Get-JobTrigger** , чтобы получить триггеры задания для запланированного задания баккупжоб.</span><span class="sxs-lookup"><span data-stu-id="a1195-124">The command uses the *Name* parameter of **Get-JobTrigger** to get the job triggers of the BackupJob scheduled job.</span></span>

### <span data-ttu-id="a1195-125">Пример 2. получение триггера задания по ИДЕНТИФИКАТОРу</span><span class="sxs-lookup"><span data-stu-id="a1195-125">Example 2: Get a job trigger by ID</span></span>

```
The first command uses the Get-ScheduledJob cmdlet to display the scheduled jobs on the local computer. The display includes the IDs of the scheduled jobs.
PS C:\> Get-ScheduledJob
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          ArchiveProjects {1}             \\Server\Share\Archive-Projects.ps1      True
2          Backup          {1,2}           \\Server\Share\Run-Backup.ps1            True
3          Test-HelpFiles  {1}             \\Server\Share\Test-HelpFiles.ps1        True
4          TestJob         {}              \\Server\Share\Run-AllTests.ps1          True

The second command uses the **Get-JobTrigger** cmdlet to get the job trigger for the Test-HelpFiles job (ID = 3)
PS C:\> Get-JobTrigger -ID 3
```

<span data-ttu-id="a1195-126">В примере используется параметр *ID* командлета **Get-JobTrigger** , чтобы получить триггеры задания для запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="a1195-126">The example uses the *ID* parameter of **Get-JobTrigger** to get the job triggers of a scheduled job.</span></span>

### <span data-ttu-id="a1195-127">Пример 3. получение триггеров задания путем передачи задания по конвейеру</span><span class="sxs-lookup"><span data-stu-id="a1195-127">Example 3: Get job triggers by piping a job</span></span>

```
PS C:\> Get-ScheduledJob -Name *Backup*, *Archive* | Get-JobTrigger
```

<span data-ttu-id="a1195-128">Эта команда возвращает Триггеры заданий для всех заданий, имеющих резервную копию или Архив в именах.</span><span class="sxs-lookup"><span data-stu-id="a1195-128">This command gets the job triggers of all jobs that have Backup or Archive in their names.</span></span>

### <span data-ttu-id="a1195-129">Пример 4. получение триггера задания на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="a1195-129">Example 4: Get the job trigger of a job on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Server01 { Get-ScheduledJob Backup | Get-JobTrigger -TriggerID 2 }
```

<span data-ttu-id="a1195-130">Эта команда возвращает один из двух триггеров задания для запланированного задания на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a1195-130">This command gets one of the two job triggers of a scheduled job on a remote computer.</span></span>

<span data-ttu-id="a1195-131">Команда использует командлет Invoke-Command для выполнения команды на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="a1195-131">The command uses the Invoke-Command cmdlet to run a command on the Server01 computer.</span></span>
<span data-ttu-id="a1195-132">Он использует командлет Get-ScheduledJob, чтобы получить запланированное задание резервного копирования, которое оно передает в командлет **Get-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="a1195-132">It uses the Get-ScheduledJob cmdlet to get the Backup scheduled job, which it pipes to the **Get-JobTrigger** cmdlet.</span></span>
<span data-ttu-id="a1195-133">Для получения только второго триггера используется параметр *TriggerID* .</span><span class="sxs-lookup"><span data-stu-id="a1195-133">It uses the *TriggerID* parameter to get only the second trigger.</span></span>

### <span data-ttu-id="a1195-134">Пример 5. получение всех триггеров заданий</span><span class="sxs-lookup"><span data-stu-id="a1195-134">Example 5: Get all job triggers</span></span>

```
PS C:\> Get-ScheduledJob | Get-JobTrigger | Format-Table -Property ID, Frequency, At, DaysOfWeek, Enabled, @{Label="ScheduledJob";Expression={$_.JobDefinition.Name}} -AutoSize
Id Frequency At                    DaysOfWeek Enabled ScheduledJob
-- --------- --                    ---------- ------- ------------
1    Weekly  9/28/2011 3:00:00 AM  {Monday}   True    Backup
1    Daily   9/27/2011 11:00:00 PM            True    Test-HelpFiles
```

<span data-ttu-id="a1195-135">Эта команда возвращает все триггеры задания для всех запланированных заданий на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a1195-135">This command gets all job triggers of all scheduled jobs on the local computer.</span></span>

<span data-ttu-id="a1195-136">Команда использует Get-ScheduledJob для получения запланированных заданий на локальном компьютере и передает их в **Get-JobTrigger** , который получает триггер задания для каждого запланированного задания (если оно есть).</span><span class="sxs-lookup"><span data-stu-id="a1195-136">The command uses the Get-ScheduledJob to get the scheduled jobs on the local computer and pipes them to **Get-JobTrigger** , which gets the job trigger of each scheduled job (if any).</span></span>

<span data-ttu-id="a1195-137">Чтобы добавить имя запланированного задания к отображению триггера задания, команда использует функцию вычисленное свойство командлета Format-Table.</span><span class="sxs-lookup"><span data-stu-id="a1195-137">To add the name of the scheduled job to the job trigger display, the command uses the calculated property feature of the Format-Table cmdlet.</span></span>
<span data-ttu-id="a1195-138">В дополнение к свойствам триггера задания, отображаемым по умолчанию, команда создает новое свойство ScheduledJob, которое отображает имя запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="a1195-138">In addition to the job trigger properties that are displayed by default, the command creates a new ScheduledJob property that displays the name of the scheduled job.</span></span>

### <span data-ttu-id="a1195-139">Пример 6. получение свойства триггера задания для запланированного задания</span><span class="sxs-lookup"><span data-stu-id="a1195-139">Example 6: Get the job trigger property of a scheduled job</span></span>

```
The command uses the Get-ScheduledJob cmdlet to get the Test-HelpFiles scheduled job. Then it uses the dot method (.) to get the JobTriggers property of the Test-HelpFiles scheduled job.
PS C:\> (Get-ScheduledJob Test-HelpFiles).JobTriggers

The second command uses the Get-ScheduledJob cmdlet to get all scheduled jobs on the local computer. It uses the ForEach-Object cmdlet to get the value of the JobTrigger property of each scheduled job.
PS C:\> Get-ScheduledJob | foreach {$_.JobTriggers}
```

<span data-ttu-id="a1195-140">Триггеры задания для запланированного задания хранятся в свойстве JobTriggers задания.</span><span class="sxs-lookup"><span data-stu-id="a1195-140">The job triggers of a scheduled job are stored in the JobTriggers property of the job.</span></span>
<span data-ttu-id="a1195-141">В этом примере показаны альтернативные варианты использования командлета **Get-JobTrigger** для получения триггеров заданий.</span><span class="sxs-lookup"><span data-stu-id="a1195-141">This example shows alternatives to using the **Get-JobTrigger** cmdlet to get job triggers.</span></span>
<span data-ttu-id="a1195-142">Результаты аналогичны использованию командлета **Get-JobTrigger** , и эти методы являются взаимозаменяемыми.</span><span class="sxs-lookup"><span data-stu-id="a1195-142">The results are identical to using the **Get-JobTrigger** cmdlet and the techniques can be used interchangeably.</span></span>

### <span data-ttu-id="a1195-143">Пример 7. сравнение триггеров заданий</span><span class="sxs-lookup"><span data-stu-id="a1195-143">Example 7: Compare job triggers</span></span>

```
The first command gets the job trigger of the ArchiveProjects scheduled job. The command pipes the job trigger to the Tee-Object cmdlet, which saves the job trigger in the $T1 variable and displays it at the command line.
PS C:\> Get-ScheduledJob -Name ArchiveProjects | Get-JobTrigger | Tee-Object -Variable T1
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
0          Daily           9/26/2011 3:00:00 AM                           True

The second command gets the job trigger of the Test-HelpFiles scheduled job. The command pipes the job trigger to the Tee-Object cmdlet, which saves the job trigger in the $T2 variable and displays it at the command line.
PS C:\> Get-ScheduledJob -Name "Test-HelpFiles" | Get-JobTrigger | Tee-Object -Variable T2
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
0          Daily           9/26/2011 3:00:00 AM                           True

The third command compares the job triggers in the $t1 and $t2 variables. It uses the Get-Member cmdlet to get the properties of the job trigger in the $t1 variable. It pipes the properties to the ForEach-Object cmdlet, which compares each property to the properties of the job trigger in the $t2 variable by name. The command then pipes the differing properties to the Format-List cmdlet, which displays them in a list.The output indicates that, although the job triggers appear to be the same, the HelpFiles job trigger includes a random delay of three (3) minutes.
PS C:\> $T1 | Get-Member -Type Property | ForEach-Object { Compare-Object $T1 $T2 -Property $_.Name}
RandomDelay                                                 SideIndicator
-----------                                                 -------------
00:00:00                                                    =>
00:03:00                                                    <=
```

<span data-ttu-id="a1195-144">В этом примере показано, как сравнить триггеры задания двух запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="a1195-144">This example shows how to compare the job triggers of two scheduled jobs.</span></span>

## <span data-ttu-id="a1195-145">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a1195-145">PARAMETERS</span></span>

### <span data-ttu-id="a1195-146">-Id</span><span class="sxs-lookup"><span data-stu-id="a1195-146">-Id</span></span>
<span data-ttu-id="a1195-147">Задает идентификационный номер запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="a1195-147">Specifies the identification number of a scheduled job.</span></span>
<span data-ttu-id="a1195-148">**Get-JobTrigger** получает триггер указанного запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="a1195-148">**Get-JobTrigger** gets the job trigger of the specified scheduled job.</span></span>

<span data-ttu-id="a1195-149">Чтобы получить идентификационный номер запланированных заданий на локальном или удаленном компьютере, используйте командлет Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="a1195-149">To get the identification number of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

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

### <span data-ttu-id="a1195-150">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a1195-150">-InputObject</span></span>
<span data-ttu-id="a1195-151">Указывает запланированное задание.</span><span class="sxs-lookup"><span data-stu-id="a1195-151">Specifies a scheduled job.</span></span>
<span data-ttu-id="a1195-152">Введите переменную, содержащую объекты  **ScheduledJob** , или введите команду или выражение, которое получает объекты **ScheduledJob** , такие как команда Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="a1195-152">Enter a variable that contains  **ScheduledJob** objects or type a command or expression that gets **ScheduledJob** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="a1195-153">Вы также можете передать объекты **ScheduledJob** в командлет **Get-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="a1195-153">You can also pipe **ScheduledJob** objects to **Get-JobTrigger** .</span></span>

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

### <span data-ttu-id="a1195-154">-Name</span><span class="sxs-lookup"><span data-stu-id="a1195-154">-Name</span></span>
<span data-ttu-id="a1195-155">Указывает имя запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="a1195-155">Specifies the name of a scheduled job.</span></span>
<span data-ttu-id="a1195-156">**Get-JobTrigger** получает триггер указанного запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="a1195-156">**Get-JobTrigger** gets the job trigger of the specified scheduled job.</span></span>
<span data-ttu-id="a1195-157">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="a1195-157">Wildcards are supported.</span></span>

<span data-ttu-id="a1195-158">Чтобы получить имена запланированных заданий на локальном или удаленном компьютере, используйте командлет Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="a1195-158">To get the names of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a1195-159">-TriggerId</span><span class="sxs-lookup"><span data-stu-id="a1195-159">-TriggerId</span></span>
<span data-ttu-id="a1195-160">Возвращает указанные триггеры задания.</span><span class="sxs-lookup"><span data-stu-id="a1195-160">Gets the specified job triggers.</span></span>
<span data-ttu-id="a1195-161">Введите идентификаторы триггеров одного или нескольких запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="a1195-161">Enter the trigger IDs of one or more job triggers of a scheduled job.</span></span>
<span data-ttu-id="a1195-162">Используйте этот параметр, если запланированное задание, заданное параметрами *Name* , *ID* или *InputObject* , имеет несколько триггеров задания.</span><span class="sxs-lookup"><span data-stu-id="a1195-162">Use this parameter when the scheduled job that is specified by the *Name* , *ID* , or *InputObject* parameters has multiple job triggers.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a1195-163">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a1195-163">CommonParameters</span></span>
<span data-ttu-id="a1195-164">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a1195-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a1195-165">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a1195-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a1195-166">Входные данные</span><span class="sxs-lookup"><span data-stu-id="a1195-166">INPUTS</span></span>

### <span data-ttu-id="a1195-167">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="a1195-167">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="a1195-168">Вы можете передать запланированное задание из Get-ScheduledJob в командлет **Get-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="a1195-168">You can pipe a scheduled job from Get-ScheduledJob to **Get-JobTrigger** .</span></span>

## <span data-ttu-id="a1195-169">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a1195-169">OUTPUTS</span></span>

### <span data-ttu-id="a1195-170">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span><span class="sxs-lookup"><span data-stu-id="a1195-170">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span></span>

## <span data-ttu-id="a1195-171">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="a1195-171">NOTES</span></span>

## <span data-ttu-id="a1195-172">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a1195-172">RELATED LINKS</span></span>

[<span data-ttu-id="a1195-173">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="a1195-173">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="a1195-174">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="a1195-174">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="a1195-175">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="a1195-175">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="a1195-176">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="a1195-176">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="a1195-177">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="a1195-177">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="a1195-178">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="a1195-178">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="a1195-179">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="a1195-179">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="a1195-180">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="a1195-180">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="a1195-181">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="a1195-181">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="a1195-182">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="a1195-182">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="a1195-183">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="a1195-183">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="a1195-184">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="a1195-184">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="a1195-185">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="a1195-185">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="a1195-186">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="a1195-186">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="a1195-187">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="a1195-187">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="a1195-188">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="a1195-188">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
