---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/remove-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-JobTrigger
ms.openlocfilehash: adcd74361b1a045a57c7db2f15996f4ea53d6d5b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227370"
---
# <span data-ttu-id="e8caf-103">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="e8caf-103">Remove-JobTrigger</span></span>

## <span data-ttu-id="e8caf-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e8caf-104">SYNOPSIS</span></span>
<span data-ttu-id="e8caf-105">Удаление триггеров заданий из запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="e8caf-105">Delete job triggers from scheduled jobs.</span></span>

## <span data-ttu-id="e8caf-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e8caf-106">SYNTAX</span></span>

### <span data-ttu-id="e8caf-107">JobDefinition (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="e8caf-107">JobDefinition (Default)</span></span>

```
Remove-JobTrigger [-TriggerId <Int32[]>] [-InputObject] <ScheduledJobDefinition[]> [<CommonParameters>]
```

### <span data-ttu-id="e8caf-108">жобдефинитионид</span><span class="sxs-lookup"><span data-stu-id="e8caf-108">JobDefinitionId</span></span>

```
Remove-JobTrigger [-TriggerId <Int32[]>] [-Id] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="e8caf-109">жобдефинитионнаме</span><span class="sxs-lookup"><span data-stu-id="e8caf-109">JobDefinitionName</span></span>

```
Remove-JobTrigger [-TriggerId <Int32[]>] [-Name] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="e8caf-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e8caf-110">DESCRIPTION</span></span>
<span data-ttu-id="e8caf-111">Командлет **Remove-JobTrigger** удаляет Триггеры заданий из запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="e8caf-111">The **Remove-JobTrigger** cmdlet deletes job triggers from scheduled jobs.</span></span>

<span data-ttu-id="e8caf-112">Триггер задания определяет повторяющееся расписание или условия для запуска запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="e8caf-112">A job trigger defines a recurring schedule or conditions for starting a scheduled job.</span></span>
<span data-ttu-id="e8caf-113">Для управления триггерами заданий используйте командлеты New-JobTrigger, Add-JobTrigger, Set-JobTrigger и Set-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="e8caf-113">To manage job triggers, use the New-JobTrigger, Add-JobTrigger, Set-JobTrigger, and Set-ScheduledJob cmdlets.</span></span>

<span data-ttu-id="e8caf-114">Используйте параметры *Name* , *ID* , или *InputObject* командлета **Remove-JobTrigger** для идентификации запланированных заданий, из которых удаляются триггеры.</span><span class="sxs-lookup"><span data-stu-id="e8caf-114">Use the *Name* , *ID* , or *InputObject* parameters of **Remove-JobTrigger** to identify the scheduled jobs from which the triggers are removed.</span></span>
<span data-ttu-id="e8caf-115">Используйте параметр *TriggerID* , чтобы указать триггеры задания для удаления.</span><span class="sxs-lookup"><span data-stu-id="e8caf-115">Use the *TriggerID* parameter to identify the job triggers to delete.</span></span>
<span data-ttu-id="e8caf-116">По умолчанию **Remove-JobTrigger** удаляет все триггеры задания для запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="e8caf-116">By default, **Remove-JobTrigger** deletes all job triggers of a scheduled job.</span></span>

<span data-ttu-id="e8caf-117">**Remove-JobTrigger** — это одна из коллекций командлетов планирования заданий в модуле PSScheduledJob, который входит в состав Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e8caf-117">**Remove-JobTrigger** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="e8caf-118">Дополнительные сведения о запланированных заданиях см. в разделах описания в модуле PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="e8caf-118">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="e8caf-119">Импортируйте модуль PSScheduledJob, а затем введите `Get-Help about_Scheduled*` или просмотрите статью about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="e8caf-119">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="e8caf-120">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="e8caf-120">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="e8caf-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="e8caf-121">EXAMPLES</span></span>

### <span data-ttu-id="e8caf-122">Пример 1. Удаление всех триггеров заданий</span><span class="sxs-lookup"><span data-stu-id="e8caf-122">Example 1: Delete all job triggers</span></span>

```
PS C:\> Remove-JobTrigger -Name "Test*"
```

<span data-ttu-id="e8caf-123">Эта команда удаляет все триггеры заданий из запланированного задания, имена которых начинаются с Test.</span><span class="sxs-lookup"><span data-stu-id="e8caf-123">This command deletes all job triggers from scheduled job that have names that begin with Test.</span></span>

### <span data-ttu-id="e8caf-124">Пример 2. Удаление выбранных триггеров заданий</span><span class="sxs-lookup"><span data-stu-id="e8caf-124">Example 2: Delete selected job triggers</span></span>

```
PS C:\> Remove-JobTrigger -Name "BackupArchive" -TriggerID 3
```

<span data-ttu-id="e8caf-125">Эта команда удаляет только третий триггер (с идентификатором 3) из запланированного задания BackupArchive.</span><span class="sxs-lookup"><span data-stu-id="e8caf-125">This command deletes only the third trigger (ID = 3) from the BackupArchive scheduled job.</span></span>

### <span data-ttu-id="e8caf-126">Пример 3. Удаление триггеров заданий AtStartup из всех запланированных заданий</span><span class="sxs-lookup"><span data-stu-id="e8caf-126">Example 3: Delete AtStartup job triggers from all scheduled jobs</span></span>

```
PS C:\> function Delete-AtStartup
{
    Get-ScheduledJob | Get-JobTrigger | Where-Object {$_.Frequency -eq "AtStartup"} | ForEach-Object { Remove-JobTrigger -InputObject $_.JobDefinition -TriggerID $_.ID}
}
```

<span data-ttu-id="e8caf-127">Эта функция удаляет все триггеры задания AtStartup из всех заданий на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="e8caf-127">This function deletes all AtStartup job triggers from all jobs on the local computer.</span></span>
<span data-ttu-id="e8caf-128">Чтобы использовать функцию, запустите в сеансе функцию и введите `Delete-AtStartup` .</span><span class="sxs-lookup"><span data-stu-id="e8caf-128">To use the function, run the function in your session and then type `Delete-AtStartup`.</span></span>

<span data-ttu-id="e8caf-129">Функция Delete-AtStartup содержит одну команду.</span><span class="sxs-lookup"><span data-stu-id="e8caf-129">The Delete-AtStartup function contains a single command.</span></span>
<span data-ttu-id="e8caf-130">Команда использует командлет Get-ScheduledJob для получения запланированных заданий на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="e8caf-130">The command uses the Get-ScheduledJob cmdlet to get the scheduled jobs on the local computer.</span></span>
<span data-ttu-id="e8caf-131">Оператор конвейера (|) отправляет запланированные задания в командлет Get-JobTrigger, который получает все триггеры заданий из каждого из запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="e8caf-131">A pipeline operator (|) sends the scheduled jobs to the Get-JobTrigger cmdlet, which gets all of the job triggers from each of the scheduled jobs.</span></span>
<span data-ttu-id="e8caf-132">Конвейерный оператор отправляет триггеры задания в командлет Where-Object, который выбирает Триггеры заданий, где значение свойства Frequency триггера задания равно AtStartup.</span><span class="sxs-lookup"><span data-stu-id="e8caf-132">A pipeline operator sends the job triggers to the Where-Object cmdlet, which selects job triggers where the value of the Frequency property of the job trigger equals AtStartup.</span></span>

<span data-ttu-id="e8caf-133">Объекты **JobTrigger** имеют свойство **JobDefinition** , которое содержит запланированное задание, которое они активируют.</span><span class="sxs-lookup"><span data-stu-id="e8caf-133">**JobTrigger** objects have a **JobDefinition** property that contains the scheduled job that they trigger.</span></span>
<span data-ttu-id="e8caf-134">Остальная часть команды использует эту функцию.</span><span class="sxs-lookup"><span data-stu-id="e8caf-134">The remainder of the command uses that valuable feature.</span></span>

<span data-ttu-id="e8caf-135">Конвейерный оператор отправляет триггеры задания AtStartup в командлет ForEach-Object, который выполняет команду **Remove-JobTrigger** для каждого триггера AtStartup.</span><span class="sxs-lookup"><span data-stu-id="e8caf-135">A pipeline operator sends the AtStartup job triggers to the ForEach-Object cmdlet, which runs a **Remove-JobTrigger** command on each AtStartup trigger.</span></span>
<span data-ttu-id="e8caf-136">Значением параметра *InputObject* командлета **Remove-JobTrigger** является запланированное задание в свойстве JobDefinition триггера задания.</span><span class="sxs-lookup"><span data-stu-id="e8caf-136">The value of the *InputObject* parameter of **Remove-JobTrigger** is the scheduled job in the JobDefinition property of the job trigger.</span></span>
<span data-ttu-id="e8caf-137">Значением параметра *TriggerID* является идентификатор в свойстве ID триггера задания.</span><span class="sxs-lookup"><span data-stu-id="e8caf-137">The value of the *TriggerID* parameter is the identifier in the ID property of the job trigger.</span></span>

### <span data-ttu-id="e8caf-138">Пример 4. Удаление триггера задания из удаленного запланированного задания</span><span class="sxs-lookup"><span data-stu-id="e8caf-138">Example 4: Delete a job trigger from a remote scheduled job</span></span>

```
PS C:\> Invoke-Command -ComputerName "Server01" { Remove-JobTrigger -ID 38 -TriggerID 1 }
```

<span data-ttu-id="e8caf-139">Эта команда удаляет первый триггер задания из задания Inventory на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="e8caf-139">This command deletes the first job trigger from the Inventory job on the Server01 computer.</span></span>

<span data-ttu-id="e8caf-140">Команда использует командлет **Invoke-Command** для выполнения командлета **Remove-JobTrigger** на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="e8caf-140">The command uses the **Invoke-Command** cmdlet to run the **Remove-JobTrigger** cmdlet on the Server01 computer.</span></span>
<span data-ttu-id="e8caf-141">Командлет **Remove-JobTrigger** использует параметр *ID* для определения запланированного задания инвентаризации и параметр *TriggerID* для указания первого триггера.</span><span class="sxs-lookup"><span data-stu-id="e8caf-141">The **Remove-JobTrigger** cmdlet uses the *ID* parameter to identify the Inventory scheduled job and the *TriggerID* parameter to specify the first trigger.</span></span>
<span data-ttu-id="e8caf-142">Параметр *ID* особенно полезен, если несколько запланированных заданий имеют одинаковые или похожие имена.</span><span class="sxs-lookup"><span data-stu-id="e8caf-142">The *ID* parameter is especially useful when multiple scheduled jobs have the same or similar names.</span></span>

## <span data-ttu-id="e8caf-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e8caf-143">PARAMETERS</span></span>

### <span data-ttu-id="e8caf-144">-Id</span><span class="sxs-lookup"><span data-stu-id="e8caf-144">-Id</span></span>
<span data-ttu-id="e8caf-145">Задает идентификационные номера запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="e8caf-145">Specifies the identification numbers of the scheduled jobs.</span></span>
<span data-ttu-id="e8caf-146">**Remove-JobTrigger** удаляет триггеры задания из указанных запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="e8caf-146">**Remove-JobTrigger** deletes job triggers from the specified scheduled jobs.</span></span>

<span data-ttu-id="e8caf-147">Чтобы получить идентификационный номер запланированных заданий на локальном или удаленном компьютере, используйте командлет Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="e8caf-147">To get the identification number of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

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

### <span data-ttu-id="e8caf-148">-InputObject</span><span class="sxs-lookup"><span data-stu-id="e8caf-148">-InputObject</span></span>
<span data-ttu-id="e8caf-149">Указывает запланированные задания.</span><span class="sxs-lookup"><span data-stu-id="e8caf-149">Specifies the scheduled jobs.</span></span>
<span data-ttu-id="e8caf-150">Введите переменную, содержащую объекты **ScheduledJob** , или введите команду или выражение, которое получает объекты **ScheduledJob** , такие как команда Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="e8caf-150">Enter a variable that contains **ScheduledJob** objects or type a command or expression that gets **ScheduledJob** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="e8caf-151">Можно также передать объекты **ScheduledJob** в **Remove-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="e8caf-151">You can also pipe **ScheduledJob** objects to **Remove-JobTrigger** .</span></span>

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

### <span data-ttu-id="e8caf-152">-Name</span><span class="sxs-lookup"><span data-stu-id="e8caf-152">-Name</span></span>
<span data-ttu-id="e8caf-153">Задает имена запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="e8caf-153">Specifies the names of the scheduled jobs.</span></span>
<span data-ttu-id="e8caf-154">**Remove-JobTrigger** удаляет триггеры задания из указанных запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="e8caf-154">**Remove-JobTrigger** deletes the job triggers from the specified scheduled jobs.</span></span>
<span data-ttu-id="e8caf-155">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="e8caf-155">Wildcards are supported.</span></span>

<span data-ttu-id="e8caf-156">Чтобы получить имена запланированных заданий на локальном или удаленном компьютере, используйте командлет Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="e8caf-156">To get the names of scheduled jobs on the local computer or a remote computer, use the Get-ScheduledJob cmdlet.</span></span>

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

### <span data-ttu-id="e8caf-157">-TriggerId</span><span class="sxs-lookup"><span data-stu-id="e8caf-157">-TriggerId</span></span>
<span data-ttu-id="e8caf-158">Удаляет только указанные триггеры задания.</span><span class="sxs-lookup"><span data-stu-id="e8caf-158">Deletes only the specified job triggers.</span></span>
<span data-ttu-id="e8caf-159">По умолчанию **Remove-JobTrigger** удаляет все триггеры из запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="e8caf-159">By default, **Remove-JobTrigger** deletes all triggers from the scheduled jobs.</span></span>
<span data-ttu-id="e8caf-160">Используйте этот параметр, если запланированные задания имеют несколько триггеров задания.</span><span class="sxs-lookup"><span data-stu-id="e8caf-160">Use this parameter when the scheduled jobs have multiple job triggers.</span></span>

<span data-ttu-id="e8caf-161">Введите идентификаторы триггеров одного или нескольких запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="e8caf-161">Enter the trigger IDs of one or more job triggers of a scheduled job.</span></span>
<span data-ttu-id="e8caf-162">Если указано несколько запланированных заданий, **Remove-JobTrigger** удаляет триггер задания с указанным идентификатором из всех запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="e8caf-162">If you specify multiple scheduled jobs, **Remove-JobTrigger** deletes the job trigger with the specified ID from all scheduled jobs.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e8caf-163">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e8caf-163">CommonParameters</span></span>
<span data-ttu-id="e8caf-164">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e8caf-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e8caf-165">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e8caf-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e8caf-166">Входные данные</span><span class="sxs-lookup"><span data-stu-id="e8caf-166">INPUTS</span></span>

### <span data-ttu-id="e8caf-167">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="e8caf-167">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="e8caf-168">Можно передать запланированные задания в командлет **Remove-JobTrigger** .</span><span class="sxs-lookup"><span data-stu-id="e8caf-168">You can pipe scheduled jobs to the **Remove-JobTrigger** cmdlet.</span></span>

## <span data-ttu-id="e8caf-169">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="e8caf-169">OUTPUTS</span></span>

### <span data-ttu-id="e8caf-170">Нет</span><span class="sxs-lookup"><span data-stu-id="e8caf-170">None</span></span>
<span data-ttu-id="e8caf-171">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="e8caf-171">The cmdlet does not generate any output.</span></span>

## <span data-ttu-id="e8caf-172">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="e8caf-172">NOTES</span></span>

## <span data-ttu-id="e8caf-173">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="e8caf-173">RELATED LINKS</span></span>

[<span data-ttu-id="e8caf-174">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="e8caf-174">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="e8caf-175">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="e8caf-175">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="e8caf-176">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="e8caf-176">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="e8caf-177">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="e8caf-177">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="e8caf-178">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="e8caf-178">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="e8caf-179">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="e8caf-179">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="e8caf-180">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="e8caf-180">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="e8caf-181">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="e8caf-181">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="e8caf-182">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="e8caf-182">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="e8caf-183">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="e8caf-183">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="e8caf-184">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="e8caf-184">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="e8caf-185">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="e8caf-185">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="e8caf-186">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="e8caf-186">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="e8caf-187">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="e8caf-187">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="e8caf-188">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="e8caf-188">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="e8caf-189">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="e8caf-189">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
