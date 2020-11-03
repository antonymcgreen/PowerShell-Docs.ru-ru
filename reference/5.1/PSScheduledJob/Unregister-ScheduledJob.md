---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/unregister-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-ScheduledJob
ms.openlocfilehash: 0c0b55513bcfdcebdcd5d8a6f17968a4a45e2839
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227350"
---
# <span data-ttu-id="2b60f-103">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="2b60f-103">Unregister-ScheduledJob</span></span>

## <span data-ttu-id="2b60f-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="2b60f-104">SYNOPSIS</span></span>
<span data-ttu-id="2b60f-105">Удаляет запланированные задания на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="2b60f-105">Deletes scheduled jobs on the local computer.</span></span>

## <span data-ttu-id="2b60f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2b60f-106">SYNTAX</span></span>

### <span data-ttu-id="2b60f-107">Определение (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="2b60f-107">Definition (Default)</span></span>

```
Unregister-ScheduledJob [-InputObject] <ScheduledJobDefinition[]> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="2b60f-108">DefinitionId</span><span class="sxs-lookup"><span data-stu-id="2b60f-108">DefinitionId</span></span>

```
Unregister-ScheduledJob [-Id] <Int32[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2b60f-109">DefinitionName</span><span class="sxs-lookup"><span data-stu-id="2b60f-109">DefinitionName</span></span>

```
Unregister-ScheduledJob [-Name] <String[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="2b60f-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2b60f-110">DESCRIPTION</span></span>
<span data-ttu-id="2b60f-111">Командлет **Unregister-ScheduledJob** удаляет запланированные задания с локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="2b60f-111">The **Unregister-ScheduledJob** cmdlet deletes scheduled jobs from the local computer.</span></span>

<span data-ttu-id="2b60f-112">При удалении или отмене регистрации запланированного задания **Unregister-ScheduledJob** удаляет каталог для запланированного задания (в каталоге $Home \аппдата\локал\микрософт\виндовс\повершелл\счедуледжобс), который содержит XML-файл, определяющий запланированное задание, журнал выполнения задания и все результаты задания.</span><span class="sxs-lookup"><span data-stu-id="2b60f-112">When it deletes or unregisters a scheduled job, **Unregister-ScheduledJob** deletes the directory for the scheduled job (in the $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs directory), which contains the XML file that defines the scheduled job, the job execution history, and all job results.</span></span>
<span data-ttu-id="2b60f-113">Это действие также удаляет задание из планировщика заданий.</span><span class="sxs-lookup"><span data-stu-id="2b60f-113">This action also deletes the job from Task Scheduler.</span></span>

<span data-ttu-id="2b60f-114">**Unregister-ScheduledJob** удаляет только запланированные задания, созданные с помощью командлета Register-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="2b60f-114">**Unregister-ScheduledJob** deletes only the scheduled jobs that are created by using the Register-ScheduledJob cmdlet.</span></span>
<span data-ttu-id="2b60f-115">Он не удаляет запланированные задания, созданные в планировщике заданий.</span><span class="sxs-lookup"><span data-stu-id="2b60f-115">It does not delete scheduled jobs that are created in Task Scheduler.</span></span>

<span data-ttu-id="2b60f-116">Для удаления запланированных заданий по ИДЕНТИФИКАТОРу или имени можно использовать параметры командлета **Unregister-ScheduledJob** , а также передавать запланированные задания из Get-ScheduledJob в **Reregister-ScheduledJob** .</span><span class="sxs-lookup"><span data-stu-id="2b60f-116">You can use the parameters of **Unregister-ScheduledJob** to delete scheduled jobs by ID or name, or pipe scheduled jobs from Get-ScheduledJob to **Unregister-ScheduledJob** .</span></span>

<span data-ttu-id="2b60f-117">**Unregister-ScheduledJob** — это одна из коллекций командлетов планирования заданий в модуле PSScheduledJob, который входит в состав Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2b60f-117">**Unregister-ScheduledJob** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="2b60f-118">Дополнительные сведения о запланированных заданиях см. в разделах описания в модуле PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="2b60f-118">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="2b60f-119">Импортируйте модуль PSScheduledJob, а затем введите `Get-Help about_Scheduled*` или просмотрите статью about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="2b60f-119">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="2b60f-120">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="2b60f-120">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="2b60f-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="2b60f-121">EXAMPLES</span></span>

### <span data-ttu-id="2b60f-122">Пример 1. Удаление запланированного задания</span><span class="sxs-lookup"><span data-stu-id="2b60f-122">Example 1: Delete a scheduled job</span></span>

```
PS C:\> Unregister-ScheduledJob TestJob
```

<span data-ttu-id="2b60f-123">Эта команда удаляет запланированное задание TestJob на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="2b60f-123">This command deletes the TestJob scheduled job on the local computer.</span></span>

### <span data-ttu-id="2b60f-124">Пример 2. Удаление всех запланированных заданий</span><span class="sxs-lookup"><span data-stu-id="2b60f-124">Example 2: Delete all scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob | Unregister-ScheduledJob -Force
PS C:\> Unregister-ScheduledJob -Name "*" -Force
```

<span data-ttu-id="2b60f-125">В этом примере показаны две разные команды, которые удаляют все запланированные задания на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="2b60f-125">This example shows two different commands that delete all scheduled jobs on the local computer.</span></span>

<span data-ttu-id="2b60f-126">Первая команда использует командлет Get-ScheduledJob для получения всех запланированных заданий на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="2b60f-126">The first command uses the Get-ScheduledJob cmdlet to get all scheduled jobs on the local computer.</span></span>
<span data-ttu-id="2b60f-127">Конвейерный оператор (|) отправляет запланированные задания в командлет **Unregister-ScheduleJob** , который удаляет их.</span><span class="sxs-lookup"><span data-stu-id="2b60f-127">A pipeline operator (|) sends the scheduled jobs to **Unregister-ScheduleJob** , which deletes them.</span></span>

<span data-ttu-id="2b60f-128">Вторая команда использует параметр *Name* командлета **Unregister-ScheduledJob** со значением "все" (\*) для удаления всех запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="2b60f-128">The second command uses the *Name* parameter of **Unregister-ScheduledJob** with a value of all (\*) to delete all scheduled jobs.</span></span>

<span data-ttu-id="2b60f-129">Обе команды используют параметр *Force* , который удаляет запланированное задание, даже если выполняется его экземпляр.</span><span class="sxs-lookup"><span data-stu-id="2b60f-129">Both commands use the *Force* parameter, which deletes a scheduled job even if an instance of the job is running.</span></span>

### <span data-ttu-id="2b60f-130">Пример 3. Удаление запланированного задания на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="2b60f-130">Example 3: Delete a scheduled job on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName "Server01" { Unregister-ScheduledJob -Name "Test*"}
```

<span data-ttu-id="2b60f-131">Эта команда удаляет запланированные задания с именами, которые начинаются с Test на удаленном компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="2b60f-131">This command deletes scheduled jobs with names that begin with Test on the Server01 remote computer.</span></span>
<span data-ttu-id="2b60f-132">Команда использует командлет Invoke-Command для выполнения команды **Unregister-ScheduledJob** на компьютере Server02.</span><span class="sxs-lookup"><span data-stu-id="2b60f-132">The command uses the Invoke-Command cmdlet to run the **Unregister-ScheduledJob** command on the Server02 computer.</span></span>

## <span data-ttu-id="2b60f-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2b60f-133">PARAMETERS</span></span>

### <span data-ttu-id="2b60f-134">-Force</span><span class="sxs-lookup"><span data-stu-id="2b60f-134">-Force</span></span>
<span data-ttu-id="2b60f-135">Удаляет запланированное задание, даже если выполняется его экземпляр.</span><span class="sxs-lookup"><span data-stu-id="2b60f-135">Deletes the scheduled job even if an instance of the job is running.</span></span>
<span data-ttu-id="2b60f-136">По умолчанию **Unregister-ScheduledJob** не приводит к прекращению выполнения заданий.</span><span class="sxs-lookup"><span data-stu-id="2b60f-136">By default, **Unregister-ScheduledJob** does not interrupt running jobs.</span></span>

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

### <span data-ttu-id="2b60f-137">-Id</span><span class="sxs-lookup"><span data-stu-id="2b60f-137">-Id</span></span>
<span data-ttu-id="2b60f-138">Удаляет запланированные задания с указанными идентификационными номерами (идентификаторами).</span><span class="sxs-lookup"><span data-stu-id="2b60f-138">Deletes the scheduled jobs with the specified identification numbers (ID).</span></span>
<span data-ttu-id="2b60f-139">Введите идентификаторы запланированных заданий на компьютере.</span><span class="sxs-lookup"><span data-stu-id="2b60f-139">Enter the IDs of scheduled jobs on the computer.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: DefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2b60f-140">-InputObject</span><span class="sxs-lookup"><span data-stu-id="2b60f-140">-InputObject</span></span>
<span data-ttu-id="2b60f-141">Указывает запланированное задание.</span><span class="sxs-lookup"><span data-stu-id="2b60f-141">Specifies a scheduled job.</span></span>
<span data-ttu-id="2b60f-142">Введите переменную, содержащую объекты **ScheduledJob** , или введите команду или выражение, которое получает объекты **ScheduledJob** , такие как команда Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="2b60f-142">Enter a variable that contains **ScheduledJob** objects or type a command or expression that gets **ScheduledJob** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="2b60f-143">Вы также можете передать объекты **ScheduledJob** в командлет **Reregister-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="2b60f-143">You can also pipe **ScheduledJob** objects to **Unregister-JobTrigger** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition[]
Parameter Sets: Definition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="2b60f-144">-Name</span><span class="sxs-lookup"><span data-stu-id="2b60f-144">-Name</span></span>
<span data-ttu-id="2b60f-145">Удаляет запланированные задания с указанными именами.</span><span class="sxs-lookup"><span data-stu-id="2b60f-145">Deletes the scheduled jobs with the specified names.</span></span>
<span data-ttu-id="2b60f-146">Введите имена одного или нескольких запланированных заданий на компьютере.</span><span class="sxs-lookup"><span data-stu-id="2b60f-146">Enter the names of one or more scheduled jobs on the computer.</span></span>
<span data-ttu-id="2b60f-147">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="2b60f-147">Wildcards are supported.</span></span>

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

### <span data-ttu-id="2b60f-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2b60f-148">-Confirm</span></span>
<span data-ttu-id="2b60f-149">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="2b60f-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2b60f-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2b60f-150">-WhatIf</span></span>
<span data-ttu-id="2b60f-151">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="2b60f-151">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="2b60f-152">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="2b60f-152">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2b60f-153">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="2b60f-153">CommonParameters</span></span>
<span data-ttu-id="2b60f-154">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2b60f-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2b60f-155">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2b60f-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2b60f-156">Входные данные</span><span class="sxs-lookup"><span data-stu-id="2b60f-156">INPUTS</span></span>

### <span data-ttu-id="2b60f-157">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="2b60f-157">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="2b60f-158">Можно передать запланированные задания в Unregister-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="2b60f-158">You can pipe scheduled jobs to Unregister-ScheduledJob</span></span>

## <span data-ttu-id="2b60f-159">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="2b60f-159">OUTPUTS</span></span>

### <span data-ttu-id="2b60f-160">Нет</span><span class="sxs-lookup"><span data-stu-id="2b60f-160">None</span></span>
<span data-ttu-id="2b60f-161">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="2b60f-161">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="2b60f-162">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="2b60f-162">NOTES</span></span>

## <span data-ttu-id="2b60f-163">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="2b60f-163">RELATED LINKS</span></span>

[<span data-ttu-id="2b60f-164">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="2b60f-164">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="2b60f-165">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="2b60f-165">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="2b60f-166">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="2b60f-166">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="2b60f-167">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="2b60f-167">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="2b60f-168">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="2b60f-168">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="2b60f-169">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="2b60f-169">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="2b60f-170">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="2b60f-170">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="2b60f-171">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="2b60f-171">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="2b60f-172">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="2b60f-172">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="2b60f-173">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="2b60f-173">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="2b60f-174">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="2b60f-174">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="2b60f-175">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="2b60f-175">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="2b60f-176">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="2b60f-176">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="2b60f-177">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="2b60f-177">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="2b60f-178">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="2b60f-178">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="2b60f-179">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="2b60f-179">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
