---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/enable-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-JobTrigger
ms.openlocfilehash: d08b55f4ba78af69608ac74c097fc6851164093b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227386"
---
# <span data-ttu-id="71116-103">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="71116-103">Enable-JobTrigger</span></span>

## <span data-ttu-id="71116-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="71116-104">SYNOPSIS</span></span>
<span data-ttu-id="71116-105">Включает триггеры задания для запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="71116-105">Enables the job triggers of scheduled jobs.</span></span>

## <span data-ttu-id="71116-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="71116-106">SYNTAX</span></span>

```
Enable-JobTrigger [-InputObject] <ScheduledJobTrigger[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="71116-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="71116-107">DESCRIPTION</span></span>
<span data-ttu-id="71116-108">Командлет **Enable-JobTrigger** повторно включает отключенные триггеры запланированных заданий, например те, которые были отключены с помощью командлета Disable-JobTrigger.</span><span class="sxs-lookup"><span data-stu-id="71116-108">The **Enable-JobTrigger** cmdlet re-enables job triggers of scheduled jobs, such as those that were disabled by using the Disable-JobTrigger cmdlet.</span></span>
<span data-ttu-id="71116-109">Включенные и повторно включенные триггеры заданий могут запускать запланированные задания сразу же, не требуя перезагрузки Windows или Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71116-109">Enabled and re-enabled job triggers can start scheduled jobs immediately; there is no need to restart Windows or Windows PowerShell.</span></span>

<span data-ttu-id="71116-110">Чтобы использовать этот командлет, воспользуйтесь командлетом Get-JobTrigger для получения триггеров заданий.</span><span class="sxs-lookup"><span data-stu-id="71116-110">To use this cmdlet, use the  Get-JobTrigger cmdlet to get the job triggers.</span></span>
<span data-ttu-id="71116-111">Затем передайте триггеры заданий в командлет **Enable-JobTrigger** или используйте его параметр *InputObject* .</span><span class="sxs-lookup"><span data-stu-id="71116-111">Then pipe the job triggers to **Enable-JobTrigger** or use its *InputObject* parameter.</span></span>

<span data-ttu-id="71116-112">Чтобы включить триггер задания, командлет **Enable-JobTrigger** задает для свойства Enabled триггера задания значение $true.</span><span class="sxs-lookup"><span data-stu-id="71116-112">To enable a job trigger, the **Enable-JobTrigger** cmdlet sets the Enabled property of the job trigger to $True.</span></span>

<span data-ttu-id="71116-113">**Enabled-ScheduledJob** входит в коллекцию командлетов планирования заданий в модуле **PSScheduledJob** в составе Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71116-113">**Enable-ScheduledJob** is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="71116-114">Дополнительные сведения о запланированных заданиях см. в разделах описания в модуле PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="71116-114">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="71116-115">Импортируйте модуль PSScheduledJob, а затем введите `Get-Help about_Scheduled*` или просмотрите статью about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="71116-115">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="71116-116">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="71116-116">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="71116-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="71116-117">EXAMPLES</span></span>

### <span data-ttu-id="71116-118">Пример 1. Включение триггера задания</span><span class="sxs-lookup"><span data-stu-id="71116-118">Example 1: Enable a job trigger</span></span>

```
PS C:\> Get-JobTrigger -Name Backup-Archives -TriggerID 1 | Enable-JobTrigger
```

<span data-ttu-id="71116-119">Эта команда включает первый триггер (с идентификатором 1) запланированного задания Backup-Archives на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="71116-119">This command enables the first trigger (ID=1) of the Backup-Archives scheduled job on the local computer.</span></span>

<span data-ttu-id="71116-120">Команда использует командлет Get-JobTrigger для получения триггера задания.</span><span class="sxs-lookup"><span data-stu-id="71116-120">The command uses the Get-JobTrigger cmdlet to get the job trigger.</span></span>
<span data-ttu-id="71116-121">Конвейерный оператор отправляет триггер задания в командлет **Enable-JobTrigger** , который включает его.</span><span class="sxs-lookup"><span data-stu-id="71116-121">A pipeline operator sends the job trigger to the **Enable-JobTrigger** cmdlet, which enables it.</span></span>

### <span data-ttu-id="71116-122">Пример 2. Включение всех триггеров заданий</span><span class="sxs-lookup"><span data-stu-id="71116-122">Example 2: Enable all job triggers</span></span>

```
PS C:\> Get-ScheduledJob | Get-JobTrigger | Enable-JobTrigger
```

<span data-ttu-id="71116-123">Она использует командлет Get-ScheduledJob для получения запланированных заданий на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="71116-123">The command uses the Get-ScheduledJob cmdlet to get  the scheduled jobs on the local computer.</span></span>
<span data-ttu-id="71116-124">Конвейерный оператор (|) отправляет запланированные задания в командлет Get-JobTrigger, который получает все триггеры для каждого из запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="71116-124">A pipeline operator (|) sends the scheduled jobs to the Get-JobTrigger cmdlet, which gets all job triggers of the scheduled jobs.</span></span>
<span data-ttu-id="71116-125">Другой конвейерный оператор отправляет триггеры заданий в командлет **Enable-JobTrigger** , который включает их.</span><span class="sxs-lookup"><span data-stu-id="71116-125">Another pipeline operator sends the job triggers to the **Enable-JobTrigger** cmdlet, which enables them.</span></span>

### <span data-ttu-id="71116-126">Пример 3. Включение триггера задания запланированного задания на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="71116-126">Example 3: Enable the job trigger of a scheduled job on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Server01 {Get-JobTrigger -Name DeployPackage | Where-Object {$_.Frequency -eq "AtLogon"} | Enable-JobTrigger}
```

<span data-ttu-id="71116-127">Эта команда повторно включает триггеры заданий AtLogon для запланированного задания DeployPackage на удаленном компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="71116-127">This command re-enables the AtLogon job triggers on the DeployPackage scheduled job on the Server01 remote computer.</span></span>

<span data-ttu-id="71116-128">Команда использует командлет Invoke-Command для выполнения команд на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="71116-128">The command uses the Invoke-Command cmdlet to run the commands on the Server01 computer.</span></span>
<span data-ttu-id="71116-129">Удаленная команда использует командлет Get-JobTrigger, чтобы получить триггеры для запланированного задания DeployPackage.</span><span class="sxs-lookup"><span data-stu-id="71116-129">The remote command uses the Get-JobTrigger cmdlet to get the job triggers of the DeployPackage scheduled job.</span></span>
<span data-ttu-id="71116-130">Конвейерный оператор отправляет триггеры заданий в командлет Where-Object, который возвращает только триггеры заданий AtLogon.</span><span class="sxs-lookup"><span data-stu-id="71116-130">A pipeline operator sends the job triggers to the Where-Object cmdlet which returns only AtLogon job triggers.</span></span>
<span data-ttu-id="71116-131">Конвейерный оператор отправляет триггеры задания AtLogon в командлет **Enable-JobTrigger** , который включает их.</span><span class="sxs-lookup"><span data-stu-id="71116-131">A pipeline operator sends the AtLogon job triggers to the **Enable-JobTrigger** cmdlet, which enables them.</span></span>

### <span data-ttu-id="71116-132">Пример 4. Отображение отключенных триггеров заданий</span><span class="sxs-lookup"><span data-stu-id="71116-132">Example 4: Display disabled job triggers</span></span>

```
PS C:\> Get-ScheduledJob | Get-JobTrigger | where {!$_.Enabled} | Format-Table Id, Frequency, At, DaysOfWeek, Enabled, @{Label="JobName";Expression={$_.JobDefinition.Name}}
Id Frequency At                     DaysOfWeek Enabled JobName
-- --------- --                     ---------- ------- -------
 1    Weekly 9/28/2011 3:00:00 AM   {Monday}   False   Backup-Archive
 2    Daily  9/29/2011 1:00:00 AM              False   Backup-Archive
 1    Weekly 10/20/2011 11:00:00 PM {Friday}   False   Inventory
 1    Weekly 11/2/2011 2:00:00 PM   {Monday}   False   Inventory
```

<span data-ttu-id="71116-133">Эта команда отображает все отключенные триггеры всех запланированных заданий в таблице.</span><span class="sxs-lookup"><span data-stu-id="71116-133">This command displays all disabled job triggers of all scheduled jobs in a table.</span></span>
<span data-ttu-id="71116-134">Данную команду можно использовать для поиска триггеров заданий, которые может потребоваться включить.</span><span class="sxs-lookup"><span data-stu-id="71116-134">You can use a command like this one to discover job triggers that might need to be enabled.</span></span>

<span data-ttu-id="71116-135">Команда использует командлет Get-ScheduledJob для получения запланированных заданий на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="71116-135">The command uses the Get-ScheduledJob cmdlet to get the scheduled jobs on the local computer.</span></span>
<span data-ttu-id="71116-136">Конвейерный оператор (|) отправляет запланированные задания в командлет Get-JobTrigger, который получает все триггеры для каждого из запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="71116-136">A pipeline operator (|) sends the scheduled jobs to the Get-JobTrigger cmdlet, which gets all job triggers of the scheduled jobs.</span></span>
<span data-ttu-id="71116-137">Другой конвейерный оператор отправляет триггеры заданий в командлет Where-Object, который возвращает только отключенные триггеры заданий, то есть тех, где значение свойства Enabled триггера задания отличается (!) от true.</span><span class="sxs-lookup"><span data-stu-id="71116-137">Another pipeline operator sends the job triggers to the Where-Object cmdlet, which returns only job triggers that are disabled, that is, where the value of the Enabled property of the job trigger is not (!) true.</span></span>

<span data-ttu-id="71116-138">Другой конвейерный оператор отправляет отключенные триггеры заданий в командлет Format-Table, который отображает выбранные свойства триггеров заданий в таблице.</span><span class="sxs-lookup"><span data-stu-id="71116-138">Another pipeline operator sends the disabled job triggers to the Format-Table cmdlet, which displays the selected properties of the job triggers in a table.</span></span>
<span data-ttu-id="71116-139">В набор свойств входит новое свойство JobName, которое отображает имя запланированного задания в свойстве JobDefinition триггера задания.</span><span class="sxs-lookup"><span data-stu-id="71116-139">The properties include a new JobName property that displays the name of the scheduled job in the JobDefinition property of the job trigger.</span></span>

## <span data-ttu-id="71116-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="71116-140">PARAMETERS</span></span>

### <span data-ttu-id="71116-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="71116-141">-InputObject</span></span>
<span data-ttu-id="71116-142">Указывает триггер задания для включения.</span><span class="sxs-lookup"><span data-stu-id="71116-142">Specifies the job trigger to enable.</span></span>
<span data-ttu-id="71116-143">Введите переменную, содержащую объекты **ScheduledJobTrigger** , или введите команду или выражение, которое получает объекты **ScheduledJobTrigger** , такие как команда Get-JobTrigger.</span><span class="sxs-lookup"><span data-stu-id="71116-143">Enter a variable that contains **ScheduledJobTrigger** objects or type a command or expression that gets **ScheduledJobTrigger** objects, such as a Get-JobTrigger command.</span></span>
<span data-ttu-id="71116-144">Можно также передать по конвейеру объект **ScheduledJobTrigger** в командлет **Enable-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="71116-144">You can also pipe a **ScheduledJobTrigger** object to **Enable-JobTrigger** .</span></span>

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

### <span data-ttu-id="71116-145">-PassThru</span><span class="sxs-lookup"><span data-stu-id="71116-145">-PassThru</span></span>
<span data-ttu-id="71116-146">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="71116-146">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="71116-147">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="71116-147">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="71116-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="71116-148">-Confirm</span></span>
<span data-ttu-id="71116-149">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="71116-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="71116-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="71116-150">-WhatIf</span></span>
<span data-ttu-id="71116-151">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="71116-151">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="71116-152">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="71116-152">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="71116-153">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="71116-153">CommonParameters</span></span>
<span data-ttu-id="71116-154">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="71116-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="71116-155">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="71116-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="71116-156">Входные данные</span><span class="sxs-lookup"><span data-stu-id="71116-156">INPUTS</span></span>

### <span data-ttu-id="71116-157">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span><span class="sxs-lookup"><span data-stu-id="71116-157">Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger</span></span>
<span data-ttu-id="71116-158">Можно передать триггеры заданий в **Enable-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="71116-158">You can pipe job triggers to **Enable-JobTrigger** .</span></span>

## <span data-ttu-id="71116-159">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="71116-159">OUTPUTS</span></span>

### <span data-ttu-id="71116-160">Нет</span><span class="sxs-lookup"><span data-stu-id="71116-160">None</span></span>
<span data-ttu-id="71116-161">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="71116-161">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="71116-162">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="71116-162">NOTES</span></span>

* <span data-ttu-id="71116-163">**Enable-JobTrigger** не выдает предупреждения или ошибки при включении триггера задания, который уже включен.</span><span class="sxs-lookup"><span data-stu-id="71116-163">**Enable-JobTrigger** does not generate errors or warnings if you enable a job trigger that is already enabled.</span></span>

## <span data-ttu-id="71116-164">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="71116-164">RELATED LINKS</span></span>

[<span data-ttu-id="71116-165">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="71116-165">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="71116-166">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="71116-166">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="71116-167">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="71116-167">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="71116-168">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="71116-168">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="71116-169">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="71116-169">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="71116-170">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="71116-170">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="71116-171">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="71116-171">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="71116-172">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="71116-172">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="71116-173">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="71116-173">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="71116-174">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="71116-174">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="71116-175">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="71116-175">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="71116-176">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="71116-176">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="71116-177">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="71116-177">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="71116-178">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="71116-178">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="71116-179">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="71116-179">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="71116-180">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="71116-180">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
