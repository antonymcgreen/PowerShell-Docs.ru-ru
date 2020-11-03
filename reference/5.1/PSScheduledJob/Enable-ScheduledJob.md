---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/enable-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-ScheduledJob
ms.openlocfilehash: 757402a348a6b694d2f2aee53053a1b7615dbb53
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227389"
---
# <span data-ttu-id="94642-103">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="94642-103">Enable-ScheduledJob</span></span>

## <span data-ttu-id="94642-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="94642-104">SYNOPSIS</span></span>
<span data-ttu-id="94642-105">Включает запланированное задание.</span><span class="sxs-lookup"><span data-stu-id="94642-105">Enables a scheduled job.</span></span>

## <span data-ttu-id="94642-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="94642-106">SYNTAX</span></span>

### <span data-ttu-id="94642-107">Определение (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="94642-107">Definition (Default)</span></span>

```
Enable-ScheduledJob [-InputObject] <ScheduledJobDefinition> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="94642-108">DefinitionId</span><span class="sxs-lookup"><span data-stu-id="94642-108">DefinitionId</span></span>

```
Enable-ScheduledJob [-Id] <Int32> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="94642-109">DefinitionName</span><span class="sxs-lookup"><span data-stu-id="94642-109">DefinitionName</span></span>

```
Enable-ScheduledJob [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="94642-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="94642-110">DESCRIPTION</span></span>
<span data-ttu-id="94642-111">Командлет **Enable-ScheduledJob** повторно включает отключенные запланированные задания, например те, которые отключены с помощью командлета Disable-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="94642-111">The **Enable-ScheduledJob** cmdlet re-enables scheduled jobs that are disabled, such as those that are disabled by using the Disable-ScheduledJob cmdlet.</span></span>
<span data-ttu-id="94642-112">Включенные задания запускаются автоматически при активации триггера.</span><span class="sxs-lookup"><span data-stu-id="94642-112">Enabled jobs run automatically when triggered.</span></span>

<span data-ttu-id="94642-113">Чтобы включить запланированное задание, командлет **Enable-ScheduledJob** задает для свойства Enabled запланированного задания значение $true.</span><span class="sxs-lookup"><span data-stu-id="94642-113">To enable a scheduled job, the **Enable-ScheduledJob** cmdlet sets the Enabled property of the scheduled job to $True.</span></span>

<span data-ttu-id="94642-114">**Enabled-ScheduledJob** входит в коллекцию командлетов планирования заданий в модуле **PSScheduledJob** в составе Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="94642-114">**Enabled-ScheduledJob** is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="94642-115">Дополнительные сведения о запланированных заданиях см. в разделах описания в модуле PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="94642-115">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="94642-116">Импортируйте модуль PSScheduledJob, а затем введите `Get-Help about_Scheduled*` или просмотрите статью about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="94642-116">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="94642-117">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="94642-117">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="94642-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="94642-118">EXAMPLES</span></span>

### <span data-ttu-id="94642-119">Пример 1. Включение запланированного задания</span><span class="sxs-lookup"><span data-stu-id="94642-119">Example 1: Enable a scheduled job</span></span>

```
PS C:\> Enable-ScheduledJob -ID 2 -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    True
```

<span data-ttu-id="94642-120">Эта команда включает запланированное задание с идентификатором 2 на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="94642-120">This command enables the scheduled job with ID 2 on the local computer.</span></span>
<span data-ttu-id="94642-121">В выходных данных приведены результаты выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="94642-121">The output shows the effect of the command.</span></span>

### <span data-ttu-id="94642-122">Пример 2. Включение всех запланированных заданий</span><span class="sxs-lookup"><span data-stu-id="94642-122">Example 2: Enable all scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob | Enable-ScheduledJob -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          ArchiveProje... {}              C:\Scripts\Archive-DxProjects.ps1        True
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    True
4          Test-HelpFiles  {1}             .\Test-HelpFiles.ps1                     True
5          TestJob         {1, 2}          .\Run-AllTests.ps1                       True
```

<span data-ttu-id="94642-123">Эта команда включает все запланированные задания на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="94642-123">This command enables all scheduled jobs on the local computer.</span></span>
<span data-ttu-id="94642-124">Она использует командлет Get-ScheduledJob для получения всех запланированных заданий и командлет **Enable-ScheduledJob** для их включения.</span><span class="sxs-lookup"><span data-stu-id="94642-124">It uses the Get-ScheduledJob cmdlet to get all scheduled job and the **Enable-ScheduledJob** cmdlet to enable them.</span></span>

<span data-ttu-id="94642-125">**Enable-ScheduledJob** не выдает предупреждения или ошибки при включении запланированного задания, которое уже включено, поэтому вы можете включить все запланированные задания без условий.</span><span class="sxs-lookup"><span data-stu-id="94642-125">**Enable-ScheduledJob** does not generate warnings or errors if you enable a scheduled job that is already enabled, so you can enable all scheduled jobs without conditions.</span></span>

### <span data-ttu-id="94642-126">Пример 3. Включение выбранных запланированных заданий</span><span class="sxs-lookup"><span data-stu-id="94642-126">Example 3: Enable selected scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption | Where-Object {$_.RunWithoutNetwork} | ForEach-Object {Enable-ScheduledJob -InputObject $_.JobDefinition}
```

<span data-ttu-id="94642-127">Эта команда включает запланированные задания, которые не требуют подключения к сети.</span><span class="sxs-lookup"><span data-stu-id="94642-127">This command enables scheduled jobs that do not require a network connection.</span></span>

<span data-ttu-id="94642-128">Она использует командлет Get-ScheduledJob для получения всех запланированных заданий на компьютере.</span><span class="sxs-lookup"><span data-stu-id="94642-128">The command uses the Get-ScheduledJob cmdlet to get all scheduled jobs on the computer.</span></span>
<span data-ttu-id="94642-129">Конвейерный оператор отправляет запланированные задания в командлет Get-ScheduledJobOptions, который получает параметры задания для каждого из этих запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="94642-129">A pipeline operator sends the scheduled jobs to the Get-ScheduledJobOption cmdlet, which gets the job options of each scheduled job.</span></span>
<span data-ttu-id="94642-130">Каждый объект параметров задания имеет свойство JobDefinition, которое содержит связанное запланированное задание.</span><span class="sxs-lookup"><span data-stu-id="94642-130">Each job options object has a JobDefinition property that contains the associated scheduled job.</span></span>
<span data-ttu-id="94642-131">Свойство JobDefinition используется для выполнения данной команды.</span><span class="sxs-lookup"><span data-stu-id="94642-131">The JobDefinition property is used to complete the command.</span></span>

<span data-ttu-id="94642-132">Команда использует оператор конвейера (|) для отправки параметров задания в командлет Where-Object, который выбирает объекты параметров запланированного задания, в которых свойство **рунвисаутнетворк** имеет значение True ($true).</span><span class="sxs-lookup"><span data-stu-id="94642-132">The command uses a pipeline operator (|) to send the job options to the Where-Object cmdlet, which selects scheduled job option objects in which the **RunWithoutNetwork** property has a value of True ($true).</span></span>
<span data-ttu-id="94642-133">Другой конвейерный оператор отправляет выбранные объекты параметров запланированного задания в командлет ForEach-Object, который выполняет команду **Enable-ScheduledJob** с запланированным заданием в значении свойства JobDefinition каждого объекта параметров задания.</span><span class="sxs-lookup"><span data-stu-id="94642-133">Another pipeline operator sends the selected scheduled job options objects to the ForEach-Object cmdlet which runs an **Enable-ScheduledJob** command on the scheduled job in the value of the JobDefinition property of each job options object.</span></span>

### <span data-ttu-id="94642-134">Пример 4. Включение запланированных заданий на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="94642-134">Example 4: Enable scheduled jobs on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName "Srv01,Srv10" -ScriptBlock {Enable-ScheduledJob -Name "Inventory"}
```

<span data-ttu-id="94642-135">Эта команда включает запланированные задания, которые имеют слово test в именах, на двух удаленных компьютерах — Srv01 и Srv10.</span><span class="sxs-lookup"><span data-stu-id="94642-135">This command enables scheduled jobs that have "test" in their names on two remote computers, Srv01 and Srv10.</span></span>

<span data-ttu-id="94642-136">Она использует командлет Invoke-Command для выполнения команды **Enable-ScheduledJob** на компьютерах Srv01 и Srv10.</span><span class="sxs-lookup"><span data-stu-id="94642-136">The command uses the Invoke-Command cmdlet to run an **Enable-ScheduledJob** command on the Srv01 and Srv10 computers.</span></span>
<span data-ttu-id="94642-137">Команда использует параметр *Name\*\*\*Enable-ScheduledJob*\* для включения запланированного задания инвентаризации на каждом компьютере.</span><span class="sxs-lookup"><span data-stu-id="94642-137">The command uses the *Name* parameter of **Enable-ScheduledJob** to enable the Inventory scheduled job on each computer.</span></span>

## <span data-ttu-id="94642-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="94642-138">PARAMETERS</span></span>

### <span data-ttu-id="94642-139">-Id</span><span class="sxs-lookup"><span data-stu-id="94642-139">-Id</span></span>
<span data-ttu-id="94642-140">Включает запланированное задание с указанным идентификационным номером (идентификатором).</span><span class="sxs-lookup"><span data-stu-id="94642-140">Enables the scheduled job with the specified identification number (ID).</span></span>
<span data-ttu-id="94642-141">Введите идентификатор запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="94642-141">Enter the ID of a scheduled job.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="94642-142">-InputObject</span><span class="sxs-lookup"><span data-stu-id="94642-142">-InputObject</span></span>
<span data-ttu-id="94642-143">Указывает запланированное задание, которое необходимо включить.</span><span class="sxs-lookup"><span data-stu-id="94642-143">Specifies the scheduled job to enable.</span></span>
<span data-ttu-id="94642-144">Введите переменную, содержащую объекты **ScheduledJobDefinition** , или введите команду или выражение, которое получает объекты **ScheduledJobDefinition** , такие как команда Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="94642-144">Enter a variable that contains **ScheduledJobDefinition** objects or type a command or expression that gets **ScheduledJobDefinition** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="94642-145">Вы также можете передать по конвейеру объект **ScheduledJobDefinition** в командлет **Enable-ScheduledJob** .</span><span class="sxs-lookup"><span data-stu-id="94642-145">You can also pipe a **ScheduledJobDefinition** object to **Enable-ScheduledJob** .</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: Definition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="94642-146">-Name</span><span class="sxs-lookup"><span data-stu-id="94642-146">-Name</span></span>
<span data-ttu-id="94642-147">Включает запланированные задания с указанными именами.</span><span class="sxs-lookup"><span data-stu-id="94642-147">Enables the scheduled jobs with the specified names.</span></span>
<span data-ttu-id="94642-148">Введите имя запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="94642-148">Enter the name of a scheduled job.</span></span>
<span data-ttu-id="94642-149">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="94642-149">Wildcards are supported.</span></span>

```yaml
Type: System.String
Parameter Sets: DefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="94642-150">-PassThru</span><span class="sxs-lookup"><span data-stu-id="94642-150">-PassThru</span></span>
<span data-ttu-id="94642-151">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="94642-151">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="94642-152">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="94642-152">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="94642-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="94642-153">-Confirm</span></span>
<span data-ttu-id="94642-154">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="94642-154">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="94642-155">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="94642-155">-WhatIf</span></span>
<span data-ttu-id="94642-156">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="94642-156">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="94642-157">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="94642-157">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="94642-158">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="94642-158">CommonParameters</span></span>
<span data-ttu-id="94642-159">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="94642-159">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="94642-160">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="94642-160">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="94642-161">Входные данные</span><span class="sxs-lookup"><span data-stu-id="94642-161">INPUTS</span></span>

### <span data-ttu-id="94642-162">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="94642-162">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="94642-163">Запланированное задание можно передать по конвейеру в **Enable-ScheduledJob** .</span><span class="sxs-lookup"><span data-stu-id="94642-163">You can pipe a scheduled job to **Enable-ScheduledJob** .</span></span>

## <span data-ttu-id="94642-164">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="94642-164">OUTPUTS</span></span>

### <span data-ttu-id="94642-165">Нет или Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="94642-165">None or Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="94642-166">При использовании параметра **Passthru** командлет **Enable-ScheduledJob** возвращает запланированное задание, которое было включено.</span><span class="sxs-lookup"><span data-stu-id="94642-166">If you use the **Passthru** parameter, **Enable-ScheduledJob** returns the scheduled job that was enabled.</span></span>
<span data-ttu-id="94642-167">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="94642-167">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="94642-168">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="94642-168">NOTES</span></span>

* <span data-ttu-id="94642-169">**Enable-ScheduledJob** не выдает предупреждения или ошибки, если используется для включения запланированного задания, которое уже включено.</span><span class="sxs-lookup"><span data-stu-id="94642-169">**Enable-ScheduledJob** does not generate warnings or errors if you use it to enable a scheduled job that is already enabled.</span></span>

## <span data-ttu-id="94642-170">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="94642-170">RELATED LINKS</span></span>

[<span data-ttu-id="94642-171">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="94642-171">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="94642-172">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="94642-172">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="94642-173">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="94642-173">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="94642-174">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="94642-174">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="94642-175">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="94642-175">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="94642-176">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="94642-176">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="94642-177">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="94642-177">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="94642-178">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="94642-178">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="94642-179">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="94642-179">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="94642-180">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="94642-180">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="94642-181">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="94642-181">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="94642-182">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="94642-182">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="94642-183">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="94642-183">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="94642-184">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="94642-184">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="94642-185">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="94642-185">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="94642-186">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="94642-186">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
