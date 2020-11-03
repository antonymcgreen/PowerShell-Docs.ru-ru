---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/disable-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-JobTrigger
ms.openlocfilehash: 236e6b7e6e450bd1f3f868f889a19cf796890127
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227410"
---
# <span data-ttu-id="697dd-103">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="697dd-103">Disable-JobTrigger</span></span>

## <span data-ttu-id="697dd-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="697dd-104">SYNOPSIS</span></span>
<span data-ttu-id="697dd-105">Отключает триггеры задания для запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="697dd-105">Disables the job triggers of scheduled jobs.</span></span>

## <span data-ttu-id="697dd-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="697dd-106">SYNTAX</span></span>

```
Disable-JobTrigger [-InputObject] <ScheduledJobTrigger[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="697dd-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="697dd-107">DESCRIPTION</span></span>
<span data-ttu-id="697dd-108">Командлет **Disable-JobTrigger** временно отключает триггеры задания для запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="697dd-108">The **Disable-JobTrigger** cmdlet temporarily disables the job triggers of scheduled jobs.</span></span>
<span data-ttu-id="697dd-109">При отключении сохраняются все свойства триггера задания, однако запрещается запуск запланированного задания триггером задания.</span><span class="sxs-lookup"><span data-stu-id="697dd-109">Disabling preserves all job trigger properties, but it prevents the job trigger from starting the scheduled job.</span></span>

<span data-ttu-id="697dd-110">Чтобы использовать этот командлет, используйте командлет Get-JobTrigger, чтобы получить триггеры задания.</span><span class="sxs-lookup"><span data-stu-id="697dd-110">To use this cmdlet, use the Get-JobTrigger cmdlet to get the job triggers.</span></span>
<span data-ttu-id="697dd-111">Затем передайте триггеры задания в командлет **Disable-JobTrigger** или используйте его параметр *InputObject* .</span><span class="sxs-lookup"><span data-stu-id="697dd-111">Then pipe the job triggers to **Disable-JobTrigger** or use its *InputObject* parameter.</span></span>

<span data-ttu-id="697dd-112">Чтобы отключить триггер задания, командлет **Disable-JobTrigger** задает для свойства Enabled триггера задания значение $false.</span><span class="sxs-lookup"><span data-stu-id="697dd-112">To disable a job trigger, the **Disable-JobTrigger** cmdlet sets the Enabled property of the job trigger to $False.</span></span>
<span data-ttu-id="697dd-113">Чтобы повторно включить триггер задания, используйте командлет Enable-JobTrigger, который задает для свойства **Enabled** триггера задания значение $true.</span><span class="sxs-lookup"><span data-stu-id="697dd-113">To re-enable the job trigger, use the Enable-JobTrigger cmdlet, which sets the **Enabled** property of the job trigger to $True.</span></span>
<span data-ttu-id="697dd-114">Отключение триггера задания не приводит к отключению запланированного задания, как это делается командлетом Disable-ScheduledJob, но если отключить все триггеры заданий, то результат будет таким же, как и при отключении запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="697dd-114">Disabling a job trigger does not disable the scheduled job, such as is done by the Disable-ScheduledJob cmdlet, but if you disable all job triggers, the effect is the same as disabling the scheduled job.</span></span>

<span data-ttu-id="697dd-115">При отключении запланированного задания или отключении всех триггеров заданий по расписанию можно запустить задание с помощью командлета Start-Job или использовать отключенное запланированное задание в качестве шаблона.</span><span class="sxs-lookup"><span data-stu-id="697dd-115">If you disable a scheduled job or disable all job triggers of a scheduled job, you can still start the job by using the Start-Job cmdlet or use the disabled scheduled job as a template.</span></span>

<span data-ttu-id="697dd-116">**Disable-ScheduledJob** является одной из коллекций командлетов планирования заданий в модуле **PSScheduledJob** , включенном в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="697dd-116">**Disable-ScheduledJob** is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="697dd-117">Дополнительные сведения о запланированных заданиях см. в разделах описания в модуле PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="697dd-117">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="697dd-118">Импортируйте модуль PSScheduledJob, а затем введите `Get-Help about_Scheduled*` или просмотрите статью about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="697dd-118">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="697dd-119">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="697dd-119">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="697dd-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="697dd-120">EXAMPLES</span></span>

### <span data-ttu-id="697dd-121">Пример 1. Отключение триггера задания</span><span class="sxs-lookup"><span data-stu-id="697dd-121">Example 1: Disable a job trigger</span></span>

```
PS C:\> Get-JobTrigger -Name "Backup-Archives" -TriggerID 1 | Disable-JobTrigger
```

<span data-ttu-id="697dd-122">Эта команда отключает первый триггер (с идентификатором 1) запланированного задания Backup-Archives на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="697dd-122">This command disables the first trigger (ID=1) of the Backup-Archives scheduled job on the local computer.</span></span>

<span data-ttu-id="697dd-123">Команда использует командлет Get-JobTrigger для получения триггера задания.</span><span class="sxs-lookup"><span data-stu-id="697dd-123">The command uses the Get-JobTrigger cmdlet to get the job trigger.</span></span>
<span data-ttu-id="697dd-124">Конвейерный оператор отправляет триггер задания в командлет **Disable-JobTrigger** , который отключает его.</span><span class="sxs-lookup"><span data-stu-id="697dd-124">A pipeline operator sends the job trigger to the **Disable-JobTrigger** cmdlet, which disables it.</span></span>

### <span data-ttu-id="697dd-125">Пример 2. Отключение всех триггеров заданий</span><span class="sxs-lookup"><span data-stu-id="697dd-125">Example 2: Disable all job triggers</span></span>

```
The first command uses the Get-ScheduledJob cmdlet to get the Backup-Archives and Inventory scheduled jobs. A pipeline operator (|) sends the scheduled jobs to the Get-JobTrigger cmdlet, which gets all job triggers of the scheduled jobs. Another pipeline operator sends the job triggers to the **Disable-JobTrigger** cmdlet, which disables them.The first command uses the **Get-ScheduledJob** cmdlet to get the jobs, because its *Name* parameter takes multiple names.
PS C:\> Get-ScheduledJob -Name "Backup-Archives,Inventory" | Get-JobTrigger | Disable-JobTrigger

The second command displays the results. The command repeats the **Get-ScheduledJob** and **Get-JobTrigger** command. A pipeline operator sends the job triggers to the Format-Table cmdlet, which displays the job triggers in a table. The **Format-Table** command adds a JobName property that displays the value of the Name property of the scheduled job in the JobDefinition property of the job trigger object.
PS C:\> Get-ScheduledJob -Name "Backup-Archives,Inventory" | Get-JobTrigger | Format-Table -Property ID, Frequency, At, DaysOfWeek, Enabled, @{Label="JobName";Expression={$_.JobDefinition.Name}} -AutoSize
Id Frequency At                     DaysOfWeek Enabled JobName
-- --------- --                     ---------- ------- -------
1  Weekly    9/28/2011 3:00:00 AM   {Monday}   False   Backup-Archive
2  Daily     9/29/2011 1:00:00 AM              False   Backup-Archive
1  Weekly    10/20/2011 11:00:00 PM {Friday}   False   Inventory
1  Weekly    11/2/2011 2:00:00 PM   {Monday}   False   Inventory
```

<span data-ttu-id="697dd-126">Эти команды отключают все триггеры задания для двух запланированных заданий и отображают результаты.</span><span class="sxs-lookup"><span data-stu-id="697dd-126">These commands disable all job triggers on two scheduled jobs and display the results.</span></span>

### <span data-ttu-id="697dd-127">Пример 3. Отключение триггера задания запланированного задания на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="697dd-127">Example 3: Disable job trigger of a scheduled job on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Server01 {Get-JobTrigger -Name DeployPackage | Where-Object {$_.Frequency -eq "Daily"} | Disable-JobTrigger}
```

<span data-ttu-id="697dd-128">Эта команда отключает триггеры задания Daily для запланированного задания DeployPackage на удаленном компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="697dd-128">This command disables the daily job triggers on the DeployPackage scheduled job on the Server01 remote computer.</span></span>

<span data-ttu-id="697dd-129">Команда использует командлет Invoke-Command для выполнения команд на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="697dd-129">The command uses the Invoke-Command cmdlet to run the commands on the Server01 computer.</span></span>
<span data-ttu-id="697dd-130">Удаленная команда использует командлет Get-JobTrigger, чтобы получить триггеры для запланированного задания DeployPackage.</span><span class="sxs-lookup"><span data-stu-id="697dd-130">The remote command uses the Get-JobTrigger cmdlet to get the job triggers of the DeployPackage scheduled job.</span></span>
<span data-ttu-id="697dd-131">Конвейерный оператор отправляет триггеры задания в командлет Where-Object, который возвращает только ежедневные Триггеры заданий.</span><span class="sxs-lookup"><span data-stu-id="697dd-131">A pipeline operator sends the job triggers to the Where-Object cmdlet, which returns only daily job triggers.</span></span>
<span data-ttu-id="697dd-132">Оператор конвейера отправляет триггеры ежедневного задания в командлет **Disable-JobTrigger** , который отключает их.</span><span class="sxs-lookup"><span data-stu-id="697dd-132">A pipeline operator sends the daily job triggers to the **Disable-JobTrigger** cmdlet, which disables them.</span></span>

## <span data-ttu-id="697dd-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="697dd-133">PARAMETERS</span></span>

### <span data-ttu-id="697dd-134">-InputObject</span><span class="sxs-lookup"><span data-stu-id="697dd-134">-InputObject</span></span>
<span data-ttu-id="697dd-135">Задает отключаемый триггер задания.</span><span class="sxs-lookup"><span data-stu-id="697dd-135">Specifies the job trigger to be disabled.</span></span>
<span data-ttu-id="697dd-136">Введите переменную, содержащую объекты  **ScheduledJobTrigger** , или введите команду или выражение, которое получает объекты **ScheduledJobTrigger** , такие как команда Get-JobTrigger.</span><span class="sxs-lookup"><span data-stu-id="697dd-136">Enter a variable that contains  **ScheduledJobTrigger** objects or type a command or expression that gets **ScheduledJobTrigger** objects, such as a Get-JobTrigger command.</span></span>
<span data-ttu-id="697dd-137">Можно также передать объект **ScheduledJobTrigger** в командлет **Disable-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="697dd-137">You can also pipe a **ScheduledJobTrigger** object to **Disable-JobTrigger** .</span></span>

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

### <span data-ttu-id="697dd-138">-PassThru</span><span class="sxs-lookup"><span data-stu-id="697dd-138">-PassThru</span></span>
<span data-ttu-id="697dd-139">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="697dd-139">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="697dd-140">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="697dd-140">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="697dd-141">-Confirm</span><span class="sxs-lookup"><span data-stu-id="697dd-141">-Confirm</span></span>
<span data-ttu-id="697dd-142">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="697dd-142">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="697dd-143">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="697dd-143">-WhatIf</span></span>
<span data-ttu-id="697dd-144">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="697dd-144">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="697dd-145">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="697dd-145">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="697dd-146">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="697dd-146">CommonParameters</span></span>
<span data-ttu-id="697dd-147">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="697dd-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="697dd-148">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="697dd-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="697dd-149">Входные данные</span><span class="sxs-lookup"><span data-stu-id="697dd-149">INPUTS</span></span>

### <span data-ttu-id="697dd-150">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span><span class="sxs-lookup"><span data-stu-id="697dd-150">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span></span>
<span data-ttu-id="697dd-151">Можно передать триггеры задания в **Disable-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="697dd-151">You can pipe job triggers to **Disable-JobTrigger** .</span></span>

## <span data-ttu-id="697dd-152">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="697dd-152">OUTPUTS</span></span>

### <span data-ttu-id="697dd-153">Нет</span><span class="sxs-lookup"><span data-stu-id="697dd-153">None</span></span>
<span data-ttu-id="697dd-154">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="697dd-154">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="697dd-155">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="697dd-155">NOTES</span></span>

* <span data-ttu-id="697dd-156">**Disable-JobTrigger** не создает ошибок или предупреждений, если отключен триггер задания, который уже отключен.</span><span class="sxs-lookup"><span data-stu-id="697dd-156">**Disable-JobTrigger** does not generate errors or warnings if you disable a job trigger that is already disabled.</span></span>

## <span data-ttu-id="697dd-157">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="697dd-157">RELATED LINKS</span></span>

[<span data-ttu-id="697dd-158">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="697dd-158">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="697dd-159">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="697dd-159">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="697dd-160">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="697dd-160">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="697dd-161">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="697dd-161">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="697dd-162">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="697dd-162">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="697dd-163">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="697dd-163">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="697dd-164">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="697dd-164">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="697dd-165">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="697dd-165">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="697dd-166">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="697dd-166">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="697dd-167">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="697dd-167">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="697dd-168">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="697dd-168">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="697dd-169">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="697dd-169">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="697dd-170">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="697dd-170">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="697dd-171">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="697dd-171">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="697dd-172">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="697dd-172">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="697dd-173">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="697dd-173">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
