---
external help file: Microsoft.PowerShell.ScheduledJob.dll-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/add-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-JobTrigger
ms.openlocfilehash: 6066b8f91c99830fefb09a8bea13fac6ddf958e9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227413"
---
# <span data-ttu-id="f7864-103">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f7864-103">Add-JobTrigger</span></span>

## <span data-ttu-id="f7864-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="f7864-104">SYNOPSIS</span></span>
<span data-ttu-id="f7864-105">Добавляет триггеры задания в запланированные задания.</span><span class="sxs-lookup"><span data-stu-id="f7864-105">Adds job triggers to scheduled jobs.</span></span>

## <span data-ttu-id="f7864-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f7864-106">SYNTAX</span></span>

### <span data-ttu-id="f7864-107">JobDefinition (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="f7864-107">JobDefinition (Default)</span></span>

```
Add-JobTrigger [-Trigger] <ScheduledJobTrigger[]> [-InputObject] <ScheduledJobDefinition[]>
 [<CommonParameters>]
```

### <span data-ttu-id="f7864-108">жобдефинитионид</span><span class="sxs-lookup"><span data-stu-id="f7864-108">JobDefinitionId</span></span>

```
Add-JobTrigger [-Trigger] <ScheduledJobTrigger[]> [-Id] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="f7864-109">жобдефинитионнаме</span><span class="sxs-lookup"><span data-stu-id="f7864-109">JobDefinitionName</span></span>

```
Add-JobTrigger [-Trigger] <ScheduledJobTrigger[]> [-Name] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="f7864-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f7864-110">DESCRIPTION</span></span>
<span data-ttu-id="f7864-111">Командлет **Add-JobTrigger** добавляет триггеры задания в запланированные задания.</span><span class="sxs-lookup"><span data-stu-id="f7864-111">The **Add-JobTrigger** cmdlet adds job triggers to scheduled jobs.</span></span>
<span data-ttu-id="f7864-112">Его можно использовать для добавления нескольких триггеров в несколько запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="f7864-112">You can use it to add multiple triggers to multiple scheduled jobs.</span></span>

<span data-ttu-id="f7864-113">Триггер задания запускает запланированное задание в однократном или повторяющемся расписании или при возникновении события.</span><span class="sxs-lookup"><span data-stu-id="f7864-113">A job trigger starts a scheduled job on a one-time or recurring schedule or when an event occurs.</span></span>

<span data-ttu-id="f7864-114">Используйте параметр *Trigger* командлета **Add-JobTrigger** , чтобы указать триггеры заданий для добавления.</span><span class="sxs-lookup"><span data-stu-id="f7864-114">Use the *Trigger* parameter of **Add-JobTrigger** to identify the job triggers to add.</span></span>
<span data-ttu-id="f7864-115">Используйте параметры *Name* , *ID* или *InputObject* командлета **Add-JobTrigger** , чтобы указать запланированное задание, в которое добавляются триггеры.</span><span class="sxs-lookup"><span data-stu-id="f7864-115">Use the *Name* , *ID* , or *InputObject* parameters of **Add-JobTrigger** to identify the scheduled job to which the triggers are added.</span></span>

<span data-ttu-id="f7864-116">Чтобы создать триггеры задания для значения параметра *Trigger* , используйте командлет New-JobTrigger или хэш-таблицу, чтобы указать триггер задания.</span><span class="sxs-lookup"><span data-stu-id="f7864-116">To create job triggers for the value of the *Trigger* parameter, use the New-JobTrigger cmdlet or use a hash table to specify the job trigger.</span></span>

<span data-ttu-id="f7864-117">**Add-JobTrigger** — это одна из коллекций командлетов планирования заданий в модуле **PSScheduledJob** , который входит в состав Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f7864-117">**Add-JobTrigger** is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="f7864-118">Дополнительные сведения о запланированных заданиях см. в разделах описания в модуле PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="f7864-118">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="f7864-119">Импортируйте модуль PSScheduledJob, а затем введите `Get-Help about_Scheduled*` или просмотрите статью about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="f7864-119">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="f7864-120">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="f7864-120">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="f7864-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="f7864-121">EXAMPLES</span></span>

### <span data-ttu-id="f7864-122">Пример 1. добавление триггера задания в запланированное задание</span><span class="sxs-lookup"><span data-stu-id="f7864-122">Example 1: Add a job trigger to a scheduled job</span></span>

```
PS C:\> $Daily = New-JobTrigger -Daily -At 3AMPS
PS C:\> Add-JobTrigger -Trigger $Daily -Name "TestJob"
```

<span data-ttu-id="f7864-123">Эти команды добавляют триггер задания Daily в запланированное задание TestJob.</span><span class="sxs-lookup"><span data-stu-id="f7864-123">These commands add the Daily job trigger to the TestJob scheduled job.</span></span>

<span data-ttu-id="f7864-124">Первая команда использует командлет New-JobTrigger для создания триггера задания, запускающего запланированное задание каждый день в 3:00 утра.</span><span class="sxs-lookup"><span data-stu-id="f7864-124">The first command uses the New-JobTrigger cmdlet to create a job trigger that starts a scheduled job every day at 3:00 a.m.</span></span>
<span data-ttu-id="f7864-125">Команда сохраняет триггер задания в переменной $Daily.</span><span class="sxs-lookup"><span data-stu-id="f7864-125">The command saves the job trigger in the $Daily variable.</span></span>

<span data-ttu-id="f7864-126">Вторая команда использует командлет **Add-JobTrigger** , чтобы добавить триггер задания в переменной $Startup в запланированное задание TestJob.</span><span class="sxs-lookup"><span data-stu-id="f7864-126">The second command uses the **Add-JobTrigger** cmdlet to add the job trigger in the $Startup variable to the TestJob scheduled job.</span></span>

### <span data-ttu-id="f7864-127">Пример 2. добавление триггера задания в несколько запланированных заданий</span><span class="sxs-lookup"><span data-stu-id="f7864-127">Example 2: Add a job trigger to several scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob | Add-JobTrigger -Trigger (New-JobTrigger -AtStartup)
```

<span data-ttu-id="f7864-128">Эта команда добавляет триггер задания AtStartup во все запланированные задания на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="f7864-128">This command adds an AtStartup job trigger to all scheduled jobs on the local computer.</span></span>
<span data-ttu-id="f7864-129">Для получения всех запланированных заданий на компьютере используется Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="f7864-129">It uses the Get-ScheduledJob to get all of the scheduled jobs on the computer.</span></span>
<span data-ttu-id="f7864-130">Она использует конвейерный оператор (|) для отправки заданий в командлет **Add-JobTrigger** , который добавляет триггер задания для каждого из запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="f7864-130">It uses a pipeline operator (|) to send the jobs to the **Add-JobTrigger** cmdlet, which adds the job trigger to each of the scheduled jobs.</span></span>
<span data-ttu-id="f7864-131">Значением параметра *Trigger* является New-JobTrigger команда, создающая триггер задания AtStartup.</span><span class="sxs-lookup"><span data-stu-id="f7864-131">The value of the *Trigger* parameter is a New-JobTrigger command that creates the AtStartup job trigger.</span></span>

### <span data-ttu-id="f7864-132">Пример 3. копирование триггера задания</span><span class="sxs-lookup"><span data-stu-id="f7864-132">Example 3: Copy a job trigger</span></span>

```
PS C:\> $T = Get-JobTrigger -Name "BackupArchives"
PS C:\> Add-JobTrigger -Name "TestBackup,BackupLogs" -Trigger $T
```

<span data-ttu-id="f7864-133">Эти команды копируют триггер задания из запланированного задания BackupArchives и добавляют его в запланированные задания TestBackup и BackupLogs.</span><span class="sxs-lookup"><span data-stu-id="f7864-133">These commands copy the job trigger from the BackupArchives scheduled job and add it to the TestBackup and BackupLogs scheduled jobs.</span></span>

<span data-ttu-id="f7864-134">Первая команда использует командлет Get-JobTrigger для получения триггера задания запланированного задания запланированного.</span><span class="sxs-lookup"><span data-stu-id="f7864-134">The first command uses the Get-JobTrigger cmdlet to get the job trigger of the BackupArchives scheduled job.</span></span>
<span data-ttu-id="f7864-135">Команда сохраняет триггер в переменной $t.</span><span class="sxs-lookup"><span data-stu-id="f7864-135">The command saves the trigger in the $t variable.</span></span>

<span data-ttu-id="f7864-136">Вторая команда использует командлет **Add-JobTrigger** , чтобы добавить триггер задания в переменной $t в запланированные задания TestBackup и BackupLogs.</span><span class="sxs-lookup"><span data-stu-id="f7864-136">The second command uses the **Add-JobTrigger** cmdlet to add the job trigger in $t to the TestBackup and BackupLogs scheduled jobs.</span></span>

## <span data-ttu-id="f7864-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f7864-137">PARAMETERS</span></span>

### <span data-ttu-id="f7864-138">-Id</span><span class="sxs-lookup"><span data-stu-id="f7864-138">-Id</span></span>
<span data-ttu-id="f7864-139">Задает идентификационные номера запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="f7864-139">Specifies the identification numbers of the scheduled jobs.</span></span>
<span data-ttu-id="f7864-140">**Add-JobTrigger** добавляет триггер задания для указанных запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="f7864-140">**Add-JobTrigger** adds the job trigger to the specified scheduled jobs.</span></span>

<span data-ttu-id="f7864-141">Чтобы получить идентификационный номер запланированных заданий на локальном или удаленном компьютере, используйте командлет Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="f7864-141">To get the identification number of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: JobDefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f7864-142">-InputObject</span><span class="sxs-lookup"><span data-stu-id="f7864-142">-InputObject</span></span>
<span data-ttu-id="f7864-143">Указывает запланированные задания.</span><span class="sxs-lookup"><span data-stu-id="f7864-143">Specifies the scheduled jobs.</span></span>
<span data-ttu-id="f7864-144">Введите переменную, содержащую объекты **ScheduledJob** , или введите команду или выражение, которое получает объекты **ScheduledJob** , такие как команда Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="f7864-144">Enter a variable that contains **ScheduledJob** objects or type a command or expression that gets **ScheduledJob** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="f7864-145">Вы также можете передать объекты **ScheduledJob** в командлет **Add-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="f7864-145">You can also pipe **ScheduledJob** objects to **Add-JobTrigger** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition[]
Parameter Sets: JobDefinition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f7864-146">-Name</span><span class="sxs-lookup"><span data-stu-id="f7864-146">-Name</span></span>
<span data-ttu-id="f7864-147">Задает имена запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="f7864-147">Specifies the names of the scheduled jobs.</span></span>
<span data-ttu-id="f7864-148">**Add-JobTrigger** добавляет триггеры задания для указанных запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="f7864-148">**Add-JobTrigger** adds the job triggers to the specified scheduled jobs.</span></span>
<span data-ttu-id="f7864-149">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="f7864-149">Wildcards are supported.</span></span>

<span data-ttu-id="f7864-150">Чтобы получить имена запланированных заданий на локальном или удаленном компьютере, используйте командлет Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="f7864-150">To get the names of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f7864-151">-Триггер</span><span class="sxs-lookup"><span data-stu-id="f7864-151">-Trigger</span></span>
<span data-ttu-id="f7864-152">Указывает триггеры задания для добавления.</span><span class="sxs-lookup"><span data-stu-id="f7864-152">Specifies the job triggers to add.</span></span>
<span data-ttu-id="f7864-153">Введите хэш-таблицу, которая указывает триггеры задания или переменную, содержащую объекты **ScheduledJobTrigger** , либо введите команду или выражение, которое получает объекты **ScheduledJobTrigger** , например команду Get-JobTrigger.</span><span class="sxs-lookup"><span data-stu-id="f7864-153">Enter a hash table that specifies job triggers or a variable that contains **ScheduledJobTrigger** objects, or type a command or expression that gets **ScheduledJobTrigger** objects, such as a Get-JobTrigger command.</span></span>
<span data-ttu-id="f7864-154">Вы также можете передать объекты **ScheduledJobTrigger** в командлет **Add-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="f7864-154">You can also pipe **ScheduledJobTrigger** objects to **Add-JobTrigger** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f7864-155">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="f7864-155">CommonParameters</span></span>
<span data-ttu-id="f7864-156">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f7864-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f7864-157">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f7864-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f7864-158">Входные данные</span><span class="sxs-lookup"><span data-stu-id="f7864-158">INPUTS</span></span>

### <span data-ttu-id="f7864-159">Microsoft. PowerShell. ScheduledJob. ScheduledJobTrigger, Microsoft. PowerShell. ScheduledJob. ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="f7864-159">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger, Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="f7864-160">Можно передать триггеры задания или запланированные задания в **Add-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="f7864-160">You can pipe job triggers or scheduled jobs to **Add-JobTrigger** .</span></span>

## <span data-ttu-id="f7864-161">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="f7864-161">OUTPUTS</span></span>

### <span data-ttu-id="f7864-162">Нет</span><span class="sxs-lookup"><span data-stu-id="f7864-162">None</span></span>
<span data-ttu-id="f7864-163">Этот командлет не возвращает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="f7864-163">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="f7864-164">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="f7864-164">NOTES</span></span>

## <span data-ttu-id="f7864-165">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="f7864-165">RELATED LINKS</span></span>

[<span data-ttu-id="f7864-166">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f7864-166">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="f7864-167">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f7864-167">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="f7864-168">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f7864-168">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="f7864-169">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f7864-169">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="f7864-170">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f7864-170">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="f7864-171">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f7864-171">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="f7864-172">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f7864-172">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="f7864-173">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="f7864-173">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="f7864-174">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f7864-174">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="f7864-175">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="f7864-175">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="f7864-176">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f7864-176">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="f7864-177">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f7864-177">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="f7864-178">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="f7864-178">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="f7864-179">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f7864-179">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="f7864-180">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="f7864-180">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="f7864-181">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="f7864-181">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
