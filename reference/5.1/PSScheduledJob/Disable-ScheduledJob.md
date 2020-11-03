---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/disable-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-ScheduledJob
ms.openlocfilehash: a7ea520d7d0365fd0de8c9d0bb767981b68467c6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227402"
---
# <span data-ttu-id="b0946-103">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b0946-103">Disable-ScheduledJob</span></span>

## <span data-ttu-id="b0946-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b0946-104">SYNOPSIS</span></span>
<span data-ttu-id="b0946-105">Отключает запланированное задание.</span><span class="sxs-lookup"><span data-stu-id="b0946-105">Disables a scheduled job.</span></span>

## <span data-ttu-id="b0946-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b0946-106">SYNTAX</span></span>

### <span data-ttu-id="b0946-107">Определение (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="b0946-107">Definition (Default)</span></span>

```
Disable-ScheduledJob [-InputObject] <ScheduledJobDefinition> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="b0946-108">DefinitionId</span><span class="sxs-lookup"><span data-stu-id="b0946-108">DefinitionId</span></span>

```
Disable-ScheduledJob [-Id] <Int32> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b0946-109">DefinitionName</span><span class="sxs-lookup"><span data-stu-id="b0946-109">DefinitionName</span></span>

```
Disable-ScheduledJob [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b0946-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b0946-110">DESCRIPTION</span></span>
<span data-ttu-id="b0946-111">Командлет **Disable-ScheduledJob** временно отключает запланированные задания.</span><span class="sxs-lookup"><span data-stu-id="b0946-111">The **Disable-ScheduledJob** cmdlet temporarily disables scheduled jobs.</span></span>
<span data-ttu-id="b0946-112">При отключении сохраняются все свойства заданий и не отключаются триггеры задания, однако запрещается автоматический запуск запланированных заданий при их активации с помощью триггера.</span><span class="sxs-lookup"><span data-stu-id="b0946-112">Disabling preserves all job properties and does not disable the job triggers, but it prevents the scheduled jobs from starting automatically when triggered.</span></span>
<span data-ttu-id="b0946-113">Вы можете запустить отключенное запланированное задание с помощью командлета Start-Job или использовать отключенное запланированное задание в качестве шаблона.</span><span class="sxs-lookup"><span data-stu-id="b0946-113">You can start a disabled scheduled job by using the Start-Job cmdlet or use a disabled scheduled job as a template.</span></span>

<span data-ttu-id="b0946-114">Чтобы отключить запланированное задание, командлет **Disable-ScheduledJob** задает для свойства **Enabled** запланированного задания значение False ($false).</span><span class="sxs-lookup"><span data-stu-id="b0946-114">To disable a scheduled job, the **Disable-ScheduledJob** cmdlet sets the **Enabled** property of the scheduled job to False ($false).</span></span>
<span data-ttu-id="b0946-115">Чтобы повторно включить запланированное задание, используйте командлет Enable-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="b0946-115">To re-enable the scheduled job, use the Enable-ScheduledJob cmdlet.</span></span>

<span data-ttu-id="b0946-116">**Disable-ScheduledJob** является одной из коллекций командлетов планирования заданий в модуле **PSScheduledJob** , включенном в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0946-116">**Disable-ScheduledJob** is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="b0946-117">Дополнительные сведения о запланированных заданиях см. в разделах описания в модуле PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="b0946-117">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="b0946-118">Импортируйте модуль PSScheduledJob, а затем введите `Get-Help about_Scheduled*` или просмотрите статью about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="b0946-118">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="b0946-119">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="b0946-119">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="b0946-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="b0946-120">EXAMPLES</span></span>

### <span data-ttu-id="b0946-121">Пример 1. Отключение запланированного задания</span><span class="sxs-lookup"><span data-stu-id="b0946-121">Example 1: Disable a scheduled job</span></span>

```
PS C:\> Disable-ScheduledJob -ID 2 -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    False
```

<span data-ttu-id="b0946-122">Эта команда отключает запланированное задание с идентификатором 2 на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="b0946-122">This command disables the scheduled job with ID 2 on the local computer.</span></span>
<span data-ttu-id="b0946-123">В выходных данных приведены результаты выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="b0946-123">The output shows the effect of the command.</span></span>

### <span data-ttu-id="b0946-124">Пример 2. Отключение всех запланированных заданий</span><span class="sxs-lookup"><span data-stu-id="b0946-124">Example 2: Disable all scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob | Disable-ScheduledJob -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          ArchiveProje... {}              C:\Scripts\Archive-DxProjects.ps1        False
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    False
4          Test-HelpFiles  {1}             .\Test-HelpFiles.ps1                     False
5          TestJob         {1, 2}          .\Run-AllTests.ps1                       False
```

<span data-ttu-id="b0946-125">Эта команда отключает все запланированные задания на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="b0946-125">This command disables all scheduled jobs on the local computer.</span></span>
<span data-ttu-id="b0946-126">Он использует командлет Get-ScheduledJob, чтобы получить все запланированные задания и командлет **Disable-ScheduledJob** , чтобы отключить их.</span><span class="sxs-lookup"><span data-stu-id="b0946-126">It uses the Get-ScheduledJob cmdlet to get all scheduled job and the **Disable-ScheduledJob** cmdlet to disable them.</span></span>

<span data-ttu-id="b0946-127">Вы можете повторно включить запланированное задание с помощью командлета Enable-ScheduledJob и запустить отключенное запланированное задание с помощью командлета Start-Job.</span><span class="sxs-lookup"><span data-stu-id="b0946-127">You can re-enable scheduled job by using the Enable-ScheduledJob cmdlet and run a disabled scheduled job by using the Start-Job cmdlet.</span></span>

<span data-ttu-id="b0946-128">**Disable-ScheduledJob** не создает предупреждения или ошибки, если отключено запланированное задание, которое уже отключено, поэтому можно отключить все запланированные задания без условий.</span><span class="sxs-lookup"><span data-stu-id="b0946-128">**Disable-ScheduledJob** does not generate warnings or errors if you disable a scheduled job that is already disabled, so you can disable all scheduled jobs without conditions.</span></span>

### <span data-ttu-id="b0946-129">Пример 3. Отключение выбранных запланированных заданий</span><span class="sxs-lookup"><span data-stu-id="b0946-129">Example 3: Disable selected scheduled jobs</span></span>

```
PS C:\> Get-ScheduledJob | Where-Object {!$_.Credential} | Disable-ScheduledJob
```

<span data-ttu-id="b0946-130">Команда отключает запланированное задание, не имеющее учетных данных.</span><span class="sxs-lookup"><span data-stu-id="b0946-130">This command disables scheduled job do not include a credential.</span></span>
<span data-ttu-id="b0946-131">Задания без учетных данных запускаются с разрешения создавшего их пользователя.</span><span class="sxs-lookup"><span data-stu-id="b0946-131">Jobs without credentials run with the permission of the user who created them.</span></span>

<span data-ttu-id="b0946-132">Она использует командлет Get-ScheduledJob для получения всех запланированных заданий на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b0946-132">The command uses the Get-ScheduledJob cmdlet to get all scheduled jobs on the computer.</span></span>
<span data-ttu-id="b0946-133">Оператор конвейера отправляет запланированные задания в командлет Where-Object, который выбирает запланированные задания, не имеющие учетных данных.</span><span class="sxs-lookup"><span data-stu-id="b0946-133">A pipeline operator sends the scheduled jobs to the Where-Object cmdlet, which selects scheduled jobs that do not have credentials.</span></span>
<span data-ttu-id="b0946-134">Команда использует оператор not (!) и ссылается на свойство Credential запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="b0946-134">The command uses the not (!) operator and references the Credential property of the scheduled job.</span></span>
<span data-ttu-id="b0946-135">Другой конвейерный оператор запланированные задания в командлет **Disable-ScheduledJob** , который отключает их.</span><span class="sxs-lookup"><span data-stu-id="b0946-135">Another pipeline operator sends the selected scheduled jobs to the **Disable-ScheduledJob** cmdlet, which disables them.</span></span>

### <span data-ttu-id="b0946-136">Пример 4. отключение запланированных заданий на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="b0946-136">Example 4: Disable scheduled jobs on a remote computer</span></span>

```
PS C:\> Invoke-Command -ComputerName Srv01, Srv10 -ScriptBlock {Disable-ScheduledJob -Name TestJob}
```

<span data-ttu-id="b0946-137">Эта команда отключает запланированное задание TestJob на двух удаленных компьютерах — Srv01 и Srv10.</span><span class="sxs-lookup"><span data-stu-id="b0946-137">This command disables the TestJob scheduled job on two remote computers, Srv01 and Srv10.</span></span>

<span data-ttu-id="b0946-138">Команда использует командлет Invoke-Command для выполнения команды **Disable-ScheduledJob** на компьютерах SRV01 и Srv10.</span><span class="sxs-lookup"><span data-stu-id="b0946-138">The command uses the Invoke-Command cmdlet to run a **Disable-ScheduledJob** command on the Srv01 and Srv10 computers.</span></span>
<span data-ttu-id="b0946-139">Команда использует параметр *Name\*\*\*Disable-ScheduledJob*\* для выбора запланированного задания TestJob на каждом компьютере.</span><span class="sxs-lookup"><span data-stu-id="b0946-139">The command uses the *Name* parameter of **Disable-ScheduledJob** to select the TestJob scheduled job on each computer.</span></span>

### <span data-ttu-id="b0946-140">Пример 5. Отключение запланированного задания по его глобальному ИДЕНТИФИКАТОРу</span><span class="sxs-lookup"><span data-stu-id="b0946-140">Example 5: Disable a scheduled job by its global ID</span></span>

```
The first command demonstrates one way of finding the GlobalID of a scheduled job. The command uses the Get-ScheduledJob cmdlet to get the scheduled jobs on the computer. A pipeline operator (|) sends the scheduled jobs to the Format-Table cmdlet, which displays the Name, GlobalID, and Command properties of each job in a table.
PS C:\> Get-ScheduledJob | Format-Table -Property Name, GlobalID, Command -Autosize
Name             GlobalId                             Command
----             --------                             -------
ArchiveProjects1 a26a0b3d-b4e6-44d3-8b95-8706ef621f7c C:\Scripts\Archive-DxProjects.ps1
Inventory        3ac37e5d-84c0-4a8f-9661-7e88ebb8f914 \\Srv01\Scripts\Get-FullInventory.ps1
Backup-Scripts   4d0cc6be-c082-48d1-baec-1bd8278f3c81  Copy-Item C:\CurrentScripts\*.ps1 -Destination C:\BackupScripts
Test-HelpFiles   d77020ca-f20d-42be-86c8-fc64df97db90 .\Test-HelpFiles.ps1
Test-HelpFiles   2f1606d2-c6cf-4bef-8b1c-ae36a9cc9934 .\Test-DomainHelpFiles.ps1

The second command uses the  Get-ScheduledJob cmdlet to get the scheduled jobs on the computer. A pipeline operator (|) sends the scheduled jobs to the Where-Object cmdlet, which selects the scheduled job with the specified global ID. Another pipeline operator sends the job to the **Disable-ScheduledJob** cmdlet, which disables it.
PS C:\> Get-ScheduledJob | Where-Object {$_.GlobalID = d77020ca-f20d-42be-86c8-fc64df97db90} | Disable-ScheduledJob
```

<span data-ttu-id="b0946-141">В этих примерах показано, как отключить запланированное задание с помощью его глобального идентификатора.</span><span class="sxs-lookup"><span data-stu-id="b0946-141">This examples shows how to disable a scheduled job by using its global identifier.</span></span>
<span data-ttu-id="b0946-142">Значением свойства GlobalID запланированного задания является уникальный идентификатор (GUID).</span><span class="sxs-lookup"><span data-stu-id="b0946-142">The value of the GlobalID property of a scheduled job is a unique identifier (GUID).</span></span>
<span data-ttu-id="b0946-143">Используйте значение GlobalID, когда необходима точность, например при отключении запланированных заданий на нескольких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="b0946-143">Use the GlobalID value when precision is required, such as when you are disabling scheduled jobs on multiple computers.</span></span>

## <span data-ttu-id="b0946-144">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b0946-144">PARAMETERS</span></span>

### <span data-ttu-id="b0946-145">-Id</span><span class="sxs-lookup"><span data-stu-id="b0946-145">-Id</span></span>
<span data-ttu-id="b0946-146">Отключает запланированное задание с указанным идентификационным номером (идентификатором).</span><span class="sxs-lookup"><span data-stu-id="b0946-146">Disables the scheduled job with the specified identification number (ID).</span></span>
<span data-ttu-id="b0946-147">Введите идентификатор запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="b0946-147">Enter the ID of a scheduled job.</span></span>

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

### <span data-ttu-id="b0946-148">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b0946-148">-InputObject</span></span>
<span data-ttu-id="b0946-149">Задает отключаемое запланированное задание.</span><span class="sxs-lookup"><span data-stu-id="b0946-149">Specifies the scheduled job to be disabled.</span></span>
<span data-ttu-id="b0946-150">Введите переменную, содержащую объекты **ScheduledJobDefinition** , либо укажите команду или выражение, возвращающие объекты **ScheduledJobDefinition** , например команду ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="b0946-150">Enter a variable that contains  **ScheduledJobDefinition** objects or type a command or expression that gets **ScheduledJobDefinition** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="b0946-151">Можно также передать объект **ScheduledJobDefinition** в командлет **Disable-ScheduledJob** .</span><span class="sxs-lookup"><span data-stu-id="b0946-151">You can also pipe a **ScheduledJobDefinition** object to **Disable-ScheduledJob** .</span></span>

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

### <span data-ttu-id="b0946-152">-Name</span><span class="sxs-lookup"><span data-stu-id="b0946-152">-Name</span></span>
<span data-ttu-id="b0946-153">Отключает запланированные задания с указанными именами.</span><span class="sxs-lookup"><span data-stu-id="b0946-153">Disables the scheduled jobs with the specified names.</span></span>
<span data-ttu-id="b0946-154">Введите имя запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="b0946-154">Enter the name of a scheduled job.</span></span>
<span data-ttu-id="b0946-155">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b0946-155">Wildcards are supported.</span></span>

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

### <span data-ttu-id="b0946-156">-PassThru</span><span class="sxs-lookup"><span data-stu-id="b0946-156">-PassThru</span></span>
<span data-ttu-id="b0946-157">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="b0946-157">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="b0946-158">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="b0946-158">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="b0946-159">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b0946-159">-Confirm</span></span>
<span data-ttu-id="b0946-160">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="b0946-160">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b0946-161">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b0946-161">-WhatIf</span></span>
<span data-ttu-id="b0946-162">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="b0946-162">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="b0946-163">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="b0946-163">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b0946-164">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b0946-164">CommonParameters</span></span>
<span data-ttu-id="b0946-165">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b0946-165">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b0946-166">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b0946-166">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b0946-167">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b0946-167">INPUTS</span></span>

### <span data-ttu-id="b0946-168">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="b0946-168">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="b0946-169">Запланированное задание можно передать в **Disable-ScheduledJob** .</span><span class="sxs-lookup"><span data-stu-id="b0946-169">You can pipe a scheduled job to **Disable-ScheduledJob** .</span></span>

## <span data-ttu-id="b0946-170">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b0946-170">OUTPUTS</span></span>

### <span data-ttu-id="b0946-171">Нет или Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="b0946-171">None or Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="b0946-172">При использовании параметра **Passthru** командлет **Disable-ScheduledJob** возвращает запланированное задание, которое было отключено.</span><span class="sxs-lookup"><span data-stu-id="b0946-172">If you use the **Passthru** parameter, **Disable-ScheduledJob** returns the scheduled job that was disabled.</span></span>
<span data-ttu-id="b0946-173">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="b0946-173">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b0946-174">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b0946-174">NOTES</span></span>

* <span data-ttu-id="b0946-175">**Disable-ScheduledJob** не создает предупреждения или ошибки, если вы используете его для отключения запланированного задания, которое уже отключено.</span><span class="sxs-lookup"><span data-stu-id="b0946-175">**Disable-ScheduledJob** does not generate warnings or errors if you use it to disable a scheduled job that is already disabled.</span></span>

## <span data-ttu-id="b0946-176">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b0946-176">RELATED LINKS</span></span>

[<span data-ttu-id="b0946-177">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b0946-177">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="b0946-178">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b0946-178">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="b0946-179">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b0946-179">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="b0946-180">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b0946-180">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="b0946-181">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b0946-181">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="b0946-182">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b0946-182">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="b0946-183">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b0946-183">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="b0946-184">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="b0946-184">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="b0946-185">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b0946-185">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="b0946-186">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="b0946-186">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="b0946-187">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b0946-187">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="b0946-188">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b0946-188">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="b0946-189">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="b0946-189">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="b0946-190">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b0946-190">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="b0946-191">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="b0946-191">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="b0946-192">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="b0946-192">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
