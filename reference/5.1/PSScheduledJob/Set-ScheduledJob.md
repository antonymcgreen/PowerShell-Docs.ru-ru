---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/set-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ScheduledJob
ms.openlocfilehash: 6144d9f19b86727bc09d07e94f4bcf158e3b7071
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94387912"
---
# <span data-ttu-id="244be-103">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="244be-103">Set-ScheduledJob</span></span>

## <span data-ttu-id="244be-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="244be-104">SYNOPSIS</span></span>
<span data-ttu-id="244be-105">Изменяет запланированные задания.</span><span class="sxs-lookup"><span data-stu-id="244be-105">Changes scheduled jobs.</span></span>

## <span data-ttu-id="244be-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="244be-106">SYNTAX</span></span>

### <span data-ttu-id="244be-107">ScriptBlock (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="244be-107">ScriptBlock (Default)</span></span>

```
Set-ScheduledJob [-Name <String>] [-ScriptBlock <ScriptBlock>] [-Trigger <ScheduledJobTrigger[]>]
 [-InitializationScript <ScriptBlock>] [-RunAs32] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-ScheduledJobOption <ScheduledJobOptions>]
 [-InputObject] <ScheduledJobDefinition> [-MaxResultCount <Int32>] [-PassThru] [-ArgumentList <Object[]>]
 [-RunNow] [-RunEvery <TimeSpan>] [<CommonParameters>]
```

### <span data-ttu-id="244be-108">FilePath</span><span class="sxs-lookup"><span data-stu-id="244be-108">FilePath</span></span>

```
Set-ScheduledJob [-Name <String>] [-FilePath <String>] [-Trigger <ScheduledJobTrigger[]>]
 [-InitializationScript <ScriptBlock>] [-RunAs32] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-ScheduledJobOption <ScheduledJobOptions>]
 [-InputObject] <ScheduledJobDefinition> [-MaxResultCount <Int32>] [-PassThru] [-ArgumentList <Object[]>]
 [-RunNow] [-RunEvery <TimeSpan>] [<CommonParameters>]
```

### <span data-ttu-id="244be-109">Выполнение</span><span class="sxs-lookup"><span data-stu-id="244be-109">Execution</span></span>

```
Set-ScheduledJob [-InputObject] <ScheduledJobDefinition> [-ClearExecutionHistory] [-PassThru]
 [<CommonParameters>]
```

## <span data-ttu-id="244be-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="244be-110">DESCRIPTION</span></span>
<span data-ttu-id="244be-111">Командлет **Set-ScheduledJob** изменяет свойства запланированных заданий, например, команды, которые выполняют задания, или учетные данные, необходимые для выполнения задания.</span><span class="sxs-lookup"><span data-stu-id="244be-111">The **Set-ScheduledJob** cmdlet changes the properties of scheduled jobs, such as the commands that the jobs run or the credentials required to run the job.</span></span>
<span data-ttu-id="244be-112">Его также можно использовать для очистки журнала выполнения запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="244be-112">You can also use it to clear the execution history of the scheduled job.</span></span>

<span data-ttu-id="244be-113">Чтобы использовать этот командлет, начните с использования командлета Get-ScheduledJob для получения запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="244be-113">To use this cmdlet, begin by using the Get-ScheduledJob cmdlet to get the scheduled job.</span></span>
<span data-ttu-id="244be-114">Затем передавайте по конвейеру запланированное задание в командлет **Set-ScheduledJob** или сохраните задание в переменной и используйте параметр *InputObject* , чтобы определить задание.</span><span class="sxs-lookup"><span data-stu-id="244be-114">Then, pipe the scheduled job to **Set-ScheduledJob** or save the job in a variable and use the *InputObject* parameter to identify the job.</span></span>
<span data-ttu-id="244be-115">Используйте остальные параметры **Set-ScheduledJob** для изменения свойств задания или очистки журнала выполнения.</span><span class="sxs-lookup"><span data-stu-id="244be-115">Use the remaining parameters of **Set-ScheduledJob** to change the job properties or clear the execution history.</span></span>

<span data-ttu-id="244be-116">Несмотря на то, что командлет **Set-ScheduledJob** можно использовать для изменения триггеров и параметров запланированного задания, команды Add-JobTrigger, Set-JobTrigger и Set-ScheduledJobOption предоставляют гораздо более простые способы выполнения этих задач.</span><span class="sxs-lookup"><span data-stu-id="244be-116">Although you can use **Set-ScheduledJob** to change the triggers and options of a scheduled job, the Add-JobTrigger, Set-JobTrigger, and Set-ScheduledJobOption cmdlets provide much easier ways to accomplish those tasks.</span></span>
<span data-ttu-id="244be-117">Чтобы создать новое запланированное задание, используйте командлет Register-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="244be-117">To create a new scheduled job, use the Register-ScheduledJob cmdlet.</span></span>

<span data-ttu-id="244be-118">Параметр *Trigger* командлета **Set-ScheduledJob** добавляет один или несколько триггеров задания, которые запускают задание.</span><span class="sxs-lookup"><span data-stu-id="244be-118">The *Trigger* parameter of **Set-ScheduledJob** adds one or more job triggers that start the job.</span></span>
<span data-ttu-id="244be-119">Параметр *Trigger* является необязательным, поэтому можно добавлять триггеры при создании запланированного задания, добавлять Триггеры заданий позже, добавлять параметр *RunNow* для немедленного запуска задания, использовать командлет Start-Job для немедленного запуска задания в любое время или сохранить неактивированное запланированное задание в качестве шаблона для других заданий.</span><span class="sxs-lookup"><span data-stu-id="244be-119">The *Trigger* parameter is optional, so you can add triggers when you create the scheduled job, add job triggers later, add the *RunNow* parameter to start the job immediately, use the Start-Job cmdlet to start the job immediately at any time, or save the untriggered scheduled job as a template for other jobs.</span></span>

<span data-ttu-id="244be-120">**Set-ScheduledJob** — это одна из коллекций командлетов планирования заданий в модуле PSScheduledJob, который входит в состав Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="244be-120">**Set-ScheduledJob** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="244be-121">Дополнительные сведения о запланированных заданиях см. в разделах описания в модуле PSScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="244be-121">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="244be-122">Импортируйте модуль PSScheduledJob, а затем введите `Get-Help about_Scheduled*` или просмотрите статью about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="244be-122">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="244be-123">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="244be-123">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="244be-124">Примеры</span><span class="sxs-lookup"><span data-stu-id="244be-124">EXAMPLES</span></span>

### <span data-ttu-id="244be-125">Пример 1. изменение скрипта, выполняемого заданием</span><span class="sxs-lookup"><span data-stu-id="244be-125">Example 1: Change the script that a job runs</span></span>

```
PS C:\> Get-ScheduledJob -Name "Inventory"
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          Inventory       {1}             C:\Scripts\Get-Inventory.ps1             True

The second command uses the Get-ScheduledJob cmdlet to get the Inventory scheduled job. A pipeline operator (|) sends the scheduled job to the **Set-ScheduledJob** cmdlet. The **Set-ScheduledJob** cmdlet uses the *Script* parameter to specify a new script, Get-FullInventory.ps1. The command uses the *Passthru* parameter to return the scheduled job after the change.
PS C:\> Get-ScheduledJob -Name "Inventory" | Set-ScheduledJob -FilePath "C:\Scripts\Get-FullInventory.ps1" -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          Inventory       {1}             C:\Scripts\Get-FullInventory.ps1         True
```

<span data-ttu-id="244be-126">В этом примере показано, как изменить сценарий, который выполняется в запланированном задании.</span><span class="sxs-lookup"><span data-stu-id="244be-126">This example shows how to change the script that is run in a scheduled job.</span></span>

<span data-ttu-id="244be-127">Первая команда использует командлет Get-ScheduledJob для получения запланированного задания инвентаризации.</span><span class="sxs-lookup"><span data-stu-id="244be-127">The first command uses the Get-ScheduledJob cmdlet to get the Inventory scheduled job.</span></span>
<span data-ttu-id="244be-128">Выходные данные показывают, что задание выполняет сценарий Get-Inventory.ps1.</span><span class="sxs-lookup"><span data-stu-id="244be-128">The output shows that the job runs the Get-Inventory.ps1 script.</span></span>

<span data-ttu-id="244be-129">Эта команда не является обязательной, она включена только для того, чтобы показать эффект изменения сценария.</span><span class="sxs-lookup"><span data-stu-id="244be-129">This command is not required; it is included only to show the effect of the script change.</span></span>

### <span data-ttu-id="244be-130">Пример 2. Удаление журнала выполнения запланированного задания</span><span class="sxs-lookup"><span data-stu-id="244be-130">Example 2: Delete the execution history of a scheduled job</span></span>

```
PS C:\> Get-ScheduledJob BackupArchive | Set-ScheduledJob -ClearExecutionHistory
```

<span data-ttu-id="244be-131">Эта команда удаляет текущий журнал выполнения и сохраненные результаты задания для запланированного задания BackupArchive.</span><span class="sxs-lookup"><span data-stu-id="244be-131">This command deletes the current execution history and saved job results for the BackupArchive scheduled job.</span></span>

<span data-ttu-id="244be-132">Команда использует командлет Get-ScheduledJob для получения запланированного задания запланированного backuparchive.</span><span class="sxs-lookup"><span data-stu-id="244be-132">The command uses the Get-ScheduledJob cmdlet to get the BackupArchive scheduled job.</span></span>
<span data-ttu-id="244be-133">Конвейерный оператор (|) отправляет задание в командлет **Set-ScheduledJob** , который изменяет его.</span><span class="sxs-lookup"><span data-stu-id="244be-133">A pipeline operator (|) sends the job to the **Set-ScheduledJob** cmdlet to change it.</span></span>
<span data-ttu-id="244be-134">Командлет **Set-ScheduledJob** использует параметр *клеарексекутионхистори* для удаления журнала выполнения и сохраненных результатов.</span><span class="sxs-lookup"><span data-stu-id="244be-134">The **Set-ScheduledJob** cmdlet uses the *ClearExecutionHistory* parameter to delete the execution history and saved results.</span></span>

<span data-ttu-id="244be-135">Дополнительные сведения о журнале выполнения и сохраненных результатах задания для запланированных заданий см. в описании about_Scheduled_Jobs.</span><span class="sxs-lookup"><span data-stu-id="244be-135">For more information about the execution history and saved job results of scheduled jobs, see about_Scheduled_Jobs.</span></span>

### <span data-ttu-id="244be-136">Пример 3. изменение запланированных заданий на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="244be-136">Example 3: Change scheduled jobs on a remote computer</span></span>

```
PS C:\> Invoke-Command -Computer "Server01, Server02" -ScriptBlock {Get-ScheduledJob | Set-ScheduledJob -InitializationScript \\SrvA\Scripts\SetForRun.ps1}
```

<span data-ttu-id="244be-137">Эта команда изменяет сценарий инициализации во всех запланированных заданиях на компьютерах Server01 и Server02.</span><span class="sxs-lookup"><span data-stu-id="244be-137">This command changes the initialization script in all scheduled jobs on the Server01 and Server02 computers.</span></span>

<span data-ttu-id="244be-138">Команда использует командлет Invoke-Command для выполнения команды на компьютерах Server01 и Server02.</span><span class="sxs-lookup"><span data-stu-id="244be-138">The command uses the Invoke-Command cmdlet to run a command on the Server01 and Server02 computers.</span></span>

<span data-ttu-id="244be-139">Удаленная команда начинается с Get-ScheduledJob команды, которая получает все запланированные задания на компьютере.</span><span class="sxs-lookup"><span data-stu-id="244be-139">The remote command begins with a Get-ScheduledJob command that gets all scheduled jobs on the computer.</span></span>
<span data-ttu-id="244be-140">Запланированные задания передаются в командлет **Set-ScheduledJob** , который изменяет скрипт инициализации на SetForRun.ps1.</span><span class="sxs-lookup"><span data-stu-id="244be-140">The scheduled jobs are piped to the **Set-ScheduledJob** cmdlet, which changes the initialization script to SetForRun.ps1.</span></span>

## <span data-ttu-id="244be-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="244be-141">PARAMETERS</span></span>

### <span data-ttu-id="244be-142">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="244be-142">-ArgumentList</span></span>
<span data-ttu-id="244be-143">Указывает значения для параметров сценария, который определяется параметром *FilePath* , или для команды, которая определяется параметром *ScriptBlock*.</span><span class="sxs-lookup"><span data-stu-id="244be-143">Specifies values for the parameters of the script that is specified by the *FilePath* parameter or for the command that is specified by the *ScriptBlock* parameter.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="244be-144">-Authentication</span><span class="sxs-lookup"><span data-stu-id="244be-144">-Authentication</span></span>
<span data-ttu-id="244be-145">Задает механизм, используемый при проверке подлинности учетных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="244be-145">Specifies the mechanism that is used to authenticate the user's credentials.</span></span>
<span data-ttu-id="244be-146">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="244be-146">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="244be-147">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="244be-147">Default</span></span>
- <span data-ttu-id="244be-148">Basic</span><span class="sxs-lookup"><span data-stu-id="244be-148">Basic</span></span>
- <span data-ttu-id="244be-149">CredSSP</span><span class="sxs-lookup"><span data-stu-id="244be-149">Credssp</span></span>
- <span data-ttu-id="244be-150">Digest (дайджест)</span><span class="sxs-lookup"><span data-stu-id="244be-150">Digest</span></span>
- <span data-ttu-id="244be-151">Kerberos</span><span class="sxs-lookup"><span data-stu-id="244be-151">Kerberos</span></span>
- <span data-ttu-id="244be-152">Согласование</span><span class="sxs-lookup"><span data-stu-id="244be-152">Negotiate</span></span>
- <span data-ttu-id="244be-153">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="244be-153">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="244be-154">Значение по умолчанию — Default.</span><span class="sxs-lookup"><span data-stu-id="244be-154">The default value is Default.</span></span> <span data-ttu-id="244be-155">Дополнительные сведения о значениях этого параметра см. в разделе [перечисление AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism) в пакете SDK для PowerShell.</span><span class="sxs-lookup"><span data-stu-id="244be-155">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism) in the PowerShell SDK.</span></span>

<span data-ttu-id="244be-156">Внимание! Аутентификация CredSSP, в рамках которой учетные данные пользователя передаются на удаленный компьютер для проверки, предназначена для команд, требующих аутентификацию нескольких ресурсов, например для доступа к удаленной сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="244be-156">Caution: Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span>
<span data-ttu-id="244be-157">Этот механизм повышает риск безопасности удаленной операции.</span><span class="sxs-lookup"><span data-stu-id="244be-157">This mechanism increases the security risk of the remote operation.</span></span>
<span data-ttu-id="244be-158">Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="244be-158">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ScriptBlock, FilePath
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="244be-159">-Клеарексекутионхистори</span><span class="sxs-lookup"><span data-stu-id="244be-159">-ClearExecutionHistory</span></span>
<span data-ttu-id="244be-160">Удаляет текущий журнал выполнения и сохраненные результаты запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="244be-160">Deletes the current execution history and the saved results of the scheduled job.</span></span>

<span data-ttu-id="244be-161">Журнал выполнения заданий и результаты задания сохраняются вместе с запланированным заданием в каталоге $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs на компьютере, где это задание создано.</span><span class="sxs-lookup"><span data-stu-id="244be-161">The job execution history and job results are saved with the scheduled job in the $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs directory on the computer on which the job is created.</span></span>
<span data-ttu-id="244be-162">Чтобы просмотреть журнал выполнения, используйте командлет Get-Job.</span><span class="sxs-lookup"><span data-stu-id="244be-162">To see the execution history, use the Get-Job cmdlet.</span></span>
<span data-ttu-id="244be-163">Чтобы получить результаты задания, используйте командлет Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="244be-163">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="244be-164">Этот параметр не влияет на события, которые планировщик записывает в журналы событий Windows, и не запрещает Windows PowerShell сохранять результаты заданий.</span><span class="sxs-lookup"><span data-stu-id="244be-164">This parameter does not affect the events that Task Scheduler writes to the Windows event logs and it does not stop Windows PowerShell from saving job results.</span></span>
<span data-ttu-id="244be-165">Чтобы управлять объемом сохраняемых результатов заданий, используйте параметр *MaxResultCount*.</span><span class="sxs-lookup"><span data-stu-id="244be-165">To manage the number of job results that are saved, use the *MaxResultCount* parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Execution
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="244be-166">-Credential</span><span class="sxs-lookup"><span data-stu-id="244be-166">-Credential</span></span>
<span data-ttu-id="244be-167">Указывает учетную запись пользователя, обладающую разрешением для выполнения запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="244be-167">Specifies a user account that has permission to run the scheduled job.</span></span>
<span data-ttu-id="244be-168">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="244be-168">The default is the current user.</span></span>

<span data-ttu-id="244be-169">Введите имя пользователя, например User01 или Domain01\User01, или введите объект **PSCredential** , например один из командлета Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="244be-169">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one from the Get-Credential cmdlet.</span></span>
<span data-ttu-id="244be-170">Если ввести только имя пользователя, появится приглашение ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="244be-170">If you enter only a user name, you will be prompted for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="244be-171">-FilePath</span><span class="sxs-lookup"><span data-stu-id="244be-171">-FilePath</span></span>
<span data-ttu-id="244be-172">Указывает сценарий, запускаемый запланированным заданием.</span><span class="sxs-lookup"><span data-stu-id="244be-172">Specifies a script that the scheduled job runs.</span></span>
<span data-ttu-id="244be-173">Введите путь к PS1-файлу на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="244be-173">Enter the path to a .ps1 file on the local computer.</span></span>
<span data-ttu-id="244be-174">Чтобы задать значения по умолчанию для параметров сценария, используйте параметр *ArgumentList*.</span><span class="sxs-lookup"><span data-stu-id="244be-174">To specify default values for the script parameters, use the *ArgumentList* parameter.</span></span>
<span data-ttu-id="244be-175">Каждое запланированное задание должно иметь либо значение *ScriptBlock* , либо значение *FilePath*.</span><span class="sxs-lookup"><span data-stu-id="244be-175">Every scheduled job must have either a *ScriptBlock* or *FilePath* value.</span></span>

```yaml
Type: System.String
Parameter Sets: FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="244be-176">-Инитиализатионскрипт</span><span class="sxs-lookup"><span data-stu-id="244be-176">-InitializationScript</span></span>
<span data-ttu-id="244be-177">Указывает полный путь к сценарию Windows PowerShell (PS1).</span><span class="sxs-lookup"><span data-stu-id="244be-177">Specifies the fully qualified path to a Windows PowerShell script (.ps1).</span></span>
<span data-ttu-id="244be-178">Сценарий инициализации выполняется в сеансе, который создается для фонового задания перед командами, которые задаются параметром *ScriptBlock* , или сценарием, который задается параметром *FilePath*.</span><span class="sxs-lookup"><span data-stu-id="244be-178">The initialization script runs in the session that is created for the background job before the commands that are specified by the *ScriptBlock* parameter or the script that is specified by the *FilePath* parameter.</span></span>
<span data-ttu-id="244be-179">Сценарий инициализации можно использовать для настройки сеанса, например, для добавления файлов, функций или псевдонимов, создания каталогов или проверки наличия необходимых компонентов.</span><span class="sxs-lookup"><span data-stu-id="244be-179">You can use the initialization script to configure the session, such as adding files, functions, or aliases, creating directories, or checking for prerequisites.</span></span>

<span data-ttu-id="244be-180">Чтобы задать сценарий, который выполняет команды основного задания, используйте параметр *FilePath*.</span><span class="sxs-lookup"><span data-stu-id="244be-180">To specify a script that runs the primary job commands, use the *FilePath* parameter.</span></span>

<span data-ttu-id="244be-181">Если скрипт инициализации создает ошибку, включая устранимую ошибку, текущий экземпляр запланированного задания не выполняется и его состояние — Failed.</span><span class="sxs-lookup"><span data-stu-id="244be-181">If the initialization script generates an error, including a non-terminating error, the current instance of the scheduled job does not run and its status is Failed.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="244be-182">-InputObject</span><span class="sxs-lookup"><span data-stu-id="244be-182">-InputObject</span></span>
<span data-ttu-id="244be-183">Задает изменяемое запланированное задание.</span><span class="sxs-lookup"><span data-stu-id="244be-183">Specifies the scheduled job to be changed.</span></span>
<span data-ttu-id="244be-184">Введите переменную, содержащую объекты **ScheduledJobDefinition** , или введите команду или выражение, которое получает объекты **ScheduledJobDefinition** , такие как команда Get-ScheduledJob.</span><span class="sxs-lookup"><span data-stu-id="244be-184">Enter a variable that contains **ScheduledJobDefinition** objects or type a command or expression that gets **ScheduledJobDefinition** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="244be-185">Можно также передать объект **ScheduledJobDefinition** в командлет **Set-ScheduledJob**.</span><span class="sxs-lookup"><span data-stu-id="244be-185">You can also pipe a **ScheduledJobDefinition** object to **Set-ScheduledJob**.</span></span>

<span data-ttu-id="244be-186">При указании нескольких запланированных заданий **Set-ScheduledJob** вносит одинаковые изменения во все задания.</span><span class="sxs-lookup"><span data-stu-id="244be-186">If you specify multiple scheduled jobs, **Set-ScheduledJob** makes the same changes to all jobs.</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="244be-187">-Максресулткаунт</span><span class="sxs-lookup"><span data-stu-id="244be-187">-MaxResultCount</span></span>
<span data-ttu-id="244be-188">Указывает, сколько записей результатов задания хранится для запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="244be-188">Specifies how many job result entries are maintained for the scheduled job.</span></span>
<span data-ttu-id="244be-189">Значение по умолчанию: 32.</span><span class="sxs-lookup"><span data-stu-id="244be-189">The default value is 32.</span></span>

<span data-ttu-id="244be-190">Windows PowerShell сохраняет журнал выполнения и результаты каждого активированного экземпляра запланированного задания на диске.</span><span class="sxs-lookup"><span data-stu-id="244be-190">Windows PowerShell saves the execution history and results of each triggered instance of the scheduled job on disk.</span></span>
<span data-ttu-id="244be-191">Значение этого параметра определяет количество результатов экземпляра задания, сохраняемых для данного запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="244be-191">The value of this parameter determines the number of job instance results that are saved for this scheduled job.</span></span>
<span data-ttu-id="244be-192">Когда число результатов экземпляра задания превышает это значение, Windows PowerShell удаляет результаты самого старого экземпляра задания, чтобы освободить место для результатов более нового экземпляра задания.</span><span class="sxs-lookup"><span data-stu-id="244be-192">When the number of job instance results exceeds this value, Windows PowerShell deletes the results of the oldest job instance to make room for the results of the newest job instance.</span></span>

<span data-ttu-id="244be-193">Журнал выполнения задания и результаты задания сохраняются в \\ \<JobName\> каталогах $Home \аппдата\локал\микрософт\виндовс\повершелл\счедуледжобс \аутпут \\ \<Timestamp\> на компьютере, где создается задание.</span><span class="sxs-lookup"><span data-stu-id="244be-193">The job execution history and job results are saved in the $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs\\\<JobName\>\Output\\\<Timestamp\> directories on the computer on which the job is created.</span></span>
<span data-ttu-id="244be-194">Чтобы просмотреть журнал выполнения, используйте командлет Get-Job.</span><span class="sxs-lookup"><span data-stu-id="244be-194">To see the execution history, use the Get-Job cmdlet.</span></span>
<span data-ttu-id="244be-195">Чтобы получить результаты задания, используйте командлет Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="244be-195">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="244be-196">Параметр *MaxResultCount* задает значение свойства ExecutionHistoryLength для запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="244be-196">The *MaxResultCount* parameter sets the value of the ExecutionHistoryLength property of the scheduled job.</span></span>

<span data-ttu-id="244be-197">Чтобы удалить текущие результаты задания и журнал выполнения, используйте параметр *ClearExecutionHistory*.</span><span class="sxs-lookup"><span data-stu-id="244be-197">To delete the current execution history and job results, use the *ClearExecutionHistory* parameter.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="244be-198">-Name</span><span class="sxs-lookup"><span data-stu-id="244be-198">-Name</span></span>
<span data-ttu-id="244be-199">Указывает новое имя для запланированного задания и его экземпляров.</span><span class="sxs-lookup"><span data-stu-id="244be-199">Specifies a new name for the scheduled job and instances of the scheduled job.</span></span>
<span data-ttu-id="244be-200">Это имя должно быть уникальным на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="244be-200">The name must be unique on the local computer.</span></span>

<span data-ttu-id="244be-201">Чтобы определить запланированное задание, которое необходимо изменить, используйте параметр *InputObject* или передайте запланированное задание по конвейеру из Get-ScheduledJob в командлет **Set-ScheduledJob**.</span><span class="sxs-lookup"><span data-stu-id="244be-201">To identify the scheduled job to be changed, use the *InputObject* parameter or pipe a scheduled job from Get-ScheduledJob to **Set-ScheduledJob**.</span></span>

<span data-ttu-id="244be-202">Этот параметр не изменяет имена экземпляров задания на диске.</span><span class="sxs-lookup"><span data-stu-id="244be-202">This parameter does not change the names of job instances on disk.</span></span>
<span data-ttu-id="244be-203">Он затрагивает только те экземпляры задания, которые запускаются после выполнения этой команды.</span><span class="sxs-lookup"><span data-stu-id="244be-203">It affects only job instances that are started after this command completes.</span></span>

```yaml
Type: System.String
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="244be-204">-PassThru</span><span class="sxs-lookup"><span data-stu-id="244be-204">-PassThru</span></span>
<span data-ttu-id="244be-205">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="244be-205">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="244be-206">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="244be-206">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="244be-207">-RunAs32</span><span class="sxs-lookup"><span data-stu-id="244be-207">-RunAs32</span></span>
<span data-ttu-id="244be-208">Запускает запланированное задание в 32-разрядном процессе.</span><span class="sxs-lookup"><span data-stu-id="244be-208">Runs the scheduled job in a 32-bit process.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="244be-209">-Руневери</span><span class="sxs-lookup"><span data-stu-id="244be-209">-RunEvery</span></span>

<span data-ttu-id="244be-210">Используется для указания периодичности выполнения задания.</span><span class="sxs-lookup"><span data-stu-id="244be-210">Used to specify how often to run the job.</span></span> <span data-ttu-id="244be-211">Например, этот параметр используется для запуска задания каждые 15 минут.</span><span class="sxs-lookup"><span data-stu-id="244be-211">For example, use this option to run a job every 15 minutes.</span></span>

```yaml
Type: System.TimeSpan
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="244be-212">-RunNow</span><span class="sxs-lookup"><span data-stu-id="244be-212">-RunNow</span></span>
<span data-ttu-id="244be-213">Запускает задание немедленно, как только выполняется командлет **Set-ScheduledJob** .</span><span class="sxs-lookup"><span data-stu-id="244be-213">Starts a job immediately, as soon as the **Set-ScheduledJob** cmdlet is run.</span></span>
<span data-ttu-id="244be-214">Этот параметр устраняет необходимость запуска планировщика заданий для выполнения сценария Windows PowerShell сразу после регистрации и не требует от пользователей создания триггера, который указывает начальную дату и время.</span><span class="sxs-lookup"><span data-stu-id="244be-214">This parameter eliminates the need to trigger Task Scheduler to run a Windows PowerShell script immediately after registration, and does not require users to create a trigger that specifies a starting date and time.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="244be-215">-Scheduledjoboptions</span><span class="sxs-lookup"><span data-stu-id="244be-215">-ScheduledJobOption</span></span>
<span data-ttu-id="244be-216">Задает параметры для запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="244be-216">Sets options for the scheduled job.</span></span>
<span data-ttu-id="244be-217">Введите объект **счедуледжобоптионс** , например, созданный с помощью командлета New-ScheduledJobOption, или значение хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="244be-217">Enter a **ScheduledJobOptions** object, such as one that you create by using the New-ScheduledJobOption cmdlet, or a hash table value.</span></span>

<span data-ttu-id="244be-218">Вы можете задать параметры для запланированного задания при регистрации запланированного задания или с помощью командлетов Set-ScheduledJobOption или **Set-ScheduledJob** , чтобы задать или изменить параметры.</span><span class="sxs-lookup"><span data-stu-id="244be-218">You can set options for a scheduled job when you register the scheduled job or use the Set-ScheduledJobOption or **Set-ScheduledJob** cmdlets to set or change options.</span></span>

<span data-ttu-id="244be-219">Многие параметры и их значения по умолчанию определяют, запускается ли запланированное задание и когда это происходит.</span><span class="sxs-lookup"><span data-stu-id="244be-219">Many of the options and their default values determine whether and when a scheduled job runs.</span></span>
<span data-ttu-id="244be-220">Обязательно просмотрите эти параметры перед планированием задания.</span><span class="sxs-lookup"><span data-stu-id="244be-220">Be sure to review these options before scheduling a job.</span></span>
<span data-ttu-id="244be-221">Описание параметров запланированного задания, включая значения по умолчанию, см. в разделе New-Scheduledjoboptions.</span><span class="sxs-lookup"><span data-stu-id="244be-221">For a description of the scheduled job options, including the default values, see New-ScheduledJobOption.</span></span>

<span data-ttu-id="244be-222">Чтобы отправить хэш-таблицу, используйте следующие ключи.</span><span class="sxs-lookup"><span data-stu-id="244be-222">To submit a hash table, use the following keys.</span></span>
<span data-ttu-id="244be-223">Ключи в следующей хэш-таблице ключи приведены со значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="244be-223">In the following hash table, the keys are shown with their default values.</span></span>

`@{# Power SettingsStartIfOnBattery=$False;StopIfGoingOnBattery=$True; WakeToRun=$False; # Idle SettingsStartIfNotIdle=$False; IdleDuration="00:10:00"; IdleTimeout="01:00:00"; StopIfGoingOffIdle=$True; RestartOnIdleResume=$False;# Security settingsShowInTaskScheduler=$TrueRunElevated=$False;# MiscRunWithoutNetwork=$False;DoNotAllowDemandStart=$False;MultipleInstancePolicy=IgnoreNew# Can be IgnoreNew, Parallel, Queue, StopExisting}`

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="244be-224">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="244be-224">-ScriptBlock</span></span>
<span data-ttu-id="244be-225">Указывает команды, выполняемые запланированным заданием.</span><span class="sxs-lookup"><span data-stu-id="244be-225">Specifies the commands that the scheduled job runs.</span></span>
<span data-ttu-id="244be-226">Чтобы создать блок скрипта, заключите команды в скобки ( { } ).</span><span class="sxs-lookup"><span data-stu-id="244be-226">Enclose the commands in braces ( { } ) to create a script block.</span></span>
<span data-ttu-id="244be-227">Чтобы задать значения по умолчанию для параметров команды, используйте параметр *ArgumentList*.</span><span class="sxs-lookup"><span data-stu-id="244be-227">To specify default values for command parameters, use the *ArgumentList* parameter.</span></span>

<span data-ttu-id="244be-228">Каждая команда Register-ScheduledJob должна использовать либо параметр *ScriptBlock* , либо параметр *FilePath*.</span><span class="sxs-lookup"><span data-stu-id="244be-228">Every Register-ScheduledJob command must use either the *ScriptBlock* or *FilePath* parameters.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="244be-229">-Триггер</span><span class="sxs-lookup"><span data-stu-id="244be-229">-Trigger</span></span>
<span data-ttu-id="244be-230">Задает триггеры для запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="244be-230">Specifies the triggers for the scheduled job.</span></span>
<span data-ttu-id="244be-231">Введите один или несколько объектов **ScheduledJobTrigger** , например объекты, возвращаемые командлетом New-JobTrigger, или хэш-таблицу ключей и значений триггера задания.</span><span class="sxs-lookup"><span data-stu-id="244be-231">Enter one or more **ScheduledJobTrigger** objects, such as the objects that the New-JobTrigger cmdlet returns, or a hash table of job trigger keys and values.</span></span>

<span data-ttu-id="244be-232">Триггер задания запускает запланированное задание автоматически при однократном или повторяющемся расписании или при возникновении события.</span><span class="sxs-lookup"><span data-stu-id="244be-232">A job trigger starts a scheduled job automatically on a one-time or recurring scheduled or when an event occurs.</span></span>

<span data-ttu-id="244be-233">Триггеры задания не являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="244be-233">Job triggers are optional.</span></span>
<span data-ttu-id="244be-234">Вы можете добавить триггер при создании запланированного задания, использовать командлеты Add-JobTrigger или **Set-ScheduledJob** , чтобы добавить триггеры позже, или использовать командлет Start-Job для немедленного запуска запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="244be-234">You can add a trigger when you create the scheduled job, use the Add-JobTrigger or **Set-ScheduledJob** cmdlets to add triggers later, or use the Start-Job cmdlet to start the scheduled job immediately.</span></span>
<span data-ttu-id="244be-235">Можно также создать и поддерживать запланированное задание, которое не имеет триггеров задания.</span><span class="sxs-lookup"><span data-stu-id="244be-235">You can also create and maintain a scheduled job that has no job triggers.</span></span>

<span data-ttu-id="244be-236">Чтобы отправить хэш-таблицу, используйте следующие ключи.</span><span class="sxs-lookup"><span data-stu-id="244be-236">To submit a hash table, use the following keys.</span></span>

<span data-ttu-id="244be-237">`@{Frequency="Once" (or Daily, Weekly, AtStartup, AtLogon);At="3am"` (или любая допустимая строка времени); `DaysOfWeek="Monday", "Wednesday"` (или любое сочетание названий дней); `Interval=2` (или любой допустимый интервал частоты); `RandomDelay="30minutes"` (или любая допустимая строка TimeSpan); `User="Domain1\User01"` (или любой допустимый пользователь; используется только со значением частоты AtLogon)</span><span class="sxs-lookup"><span data-stu-id="244be-237">`@{Frequency="Once" (or Daily, Weekly, AtStartup, AtLogon);At="3am"` (or any valid time string); `DaysOfWeek="Monday", "Wednesday"` (or any combination of day names); `Interval=2` (or any valid frequency interval); `RandomDelay="30minutes"` (or any valid timespan string); `User="Domain1\User01"` (or any valid user; used only with the AtLogon frequency value)</span></span>

<span data-ttu-id="244be-238">}</span><span class="sxs-lookup"><span data-stu-id="244be-238">}</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="244be-239">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="244be-239">CommonParameters</span></span>
<span data-ttu-id="244be-240">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="244be-240">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="244be-241">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="244be-241">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="244be-242">Входные данные</span><span class="sxs-lookup"><span data-stu-id="244be-242">INPUTS</span></span>

### <span data-ttu-id="244be-243">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="244be-243">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="244be-244">Можно передать запланированные задания в **Set-ScheduledJob**.</span><span class="sxs-lookup"><span data-stu-id="244be-244">You can pipe scheduled jobs to **Set-ScheduledJob**.</span></span>

## <span data-ttu-id="244be-245">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="244be-245">OUTPUTS</span></span>

### <span data-ttu-id="244be-246">Нет или Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="244be-246">None or Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="244be-247">При использовании параметра *Passthru* командлет **Set-ScheduledJob** возвращает запланированное задание, которое было изменено.</span><span class="sxs-lookup"><span data-stu-id="244be-247">If you use the *Passthru* parameter, **Set-ScheduledJob** returns the scheduled job that was changed.</span></span>
<span data-ttu-id="244be-248">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="244be-248">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="244be-249">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="244be-249">NOTES</span></span>

## <span data-ttu-id="244be-250">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="244be-250">RELATED LINKS</span></span>

[<span data-ttu-id="244be-251">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="244be-251">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="244be-252">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="244be-252">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="244be-253">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="244be-253">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="244be-254">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="244be-254">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="244be-255">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="244be-255">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="244be-256">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="244be-256">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="244be-257">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="244be-257">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="244be-258">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="244be-258">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="244be-259">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="244be-259">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="244be-260">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="244be-260">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="244be-261">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="244be-261">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="244be-262">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="244be-262">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="244be-263">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="244be-263">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="244be-264">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="244be-264">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="244be-265">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="244be-265">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="244be-266">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="244be-266">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
