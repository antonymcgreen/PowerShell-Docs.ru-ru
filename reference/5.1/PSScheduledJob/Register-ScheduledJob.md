---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/register-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-ScheduledJob
ms.openlocfilehash: 89887474142490a71d372577576fb0059b4ff12e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227373"
---
# <span data-ttu-id="cd988-103">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="cd988-103">Register-ScheduledJob</span></span>

## <span data-ttu-id="cd988-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="cd988-104">SYNOPSIS</span></span>
<span data-ttu-id="cd988-105">Создает запланированное задание.</span><span class="sxs-lookup"><span data-stu-id="cd988-105">Creates a scheduled job.</span></span>

## <span data-ttu-id="cd988-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cd988-106">SYNTAX</span></span>

### <span data-ttu-id="cd988-107">ScriptBlock (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="cd988-107">ScriptBlock (Default)</span></span>

```
Register-ScheduledJob [-ScriptBlock] <ScriptBlock> [-Name] <String>
 [-Trigger <ScheduledJobTrigger[]>] [-InitializationScript <ScriptBlock>] [-RunAs32]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-ScheduledJobOption <ScheduledJobOptions>] [-ArgumentList <Object[]>] [-MaxResultCount <Int32>]
 [-RunNow] [-RunEvery <TimeSpan>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cd988-108">FilePath</span><span class="sxs-lookup"><span data-stu-id="cd988-108">FilePath</span></span>

```
Register-ScheduledJob [-FilePath] <String> [-Name] <String> [-Trigger <ScheduledJobTrigger[]>]
 [-InitializationScript <ScriptBlock>] [-RunAs32] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-ScheduledJobOption <ScheduledJobOptions>]
 [-ArgumentList <Object[]>] [-MaxResultCount <Int32>] [-RunNow] [-RunEvery <TimeSpan>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="cd988-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cd988-109">DESCRIPTION</span></span>

<span data-ttu-id="cd988-110">`Register-ScheduledJob`Командлет создает запланированные задания на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cd988-110">The `Register-ScheduledJob` cmdlet creates scheduled jobs on the local computer.</span></span>

<span data-ttu-id="cd988-111">Запланированное задание — это фоновое задание Windows PowerShell, которое можно запустить автоматически при однократном или повторяющемся расписании.</span><span class="sxs-lookup"><span data-stu-id="cd988-111">A scheduled job is a Windows PowerShell background job that can be started automatically on a one-time or recurring schedule.</span></span> <span data-ttu-id="cd988-112">Запланированные задания хранятся на диске и регистрируются в планировщик задач.</span><span class="sxs-lookup"><span data-stu-id="cd988-112">Scheduled jobs are stored on disk and registered in Task Scheduler.</span></span>
<span data-ttu-id="cd988-113">Заданиями можно управлять в планировщик задач или с помощью командлетов запланированных заданий в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cd988-113">The jobs can be managed in Task Scheduler or by using the Scheduled Job cmdlets in Windows PowerShell.</span></span>

<span data-ttu-id="cd988-114">При запуске запланированного задания создается экземпляр запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="cd988-114">When a scheduled job starts, it creates an instance of the scheduled job.</span></span> <span data-ttu-id="cd988-115">Экземпляры запланированного задания идентичны фоновым заданиям Windows PowerShell, за исключением того, что результаты сохраняются на диске.</span><span class="sxs-lookup"><span data-stu-id="cd988-115">Scheduled job instances are identical to Windows PowerShell background jobs, except that the results are saved on disk.</span></span> <span data-ttu-id="cd988-116">Используйте командлеты задания, такие как `Start-Job` , `Get-Job` и, `Receive-Job` чтобы запустить, просмотреть и получить результаты экземпляров задания.</span><span class="sxs-lookup"><span data-stu-id="cd988-116">Use the Job cmdlets, such as `Start-Job`, `Get-Job`, and `Receive-Job` to start, view, and get the results of the job instances.</span></span>

<span data-ttu-id="cd988-117">Используйте `Register-ScheduledJob` для создания нового запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="cd988-117">Use `Register-ScheduledJob` to create a new scheduled job.</span></span> <span data-ttu-id="cd988-118">Чтобы указать команды, выполняемые запланированным заданием, используйте параметр **ScriptBlock** .</span><span class="sxs-lookup"><span data-stu-id="cd988-118">To specify the commands that the scheduled job runs, use the **ScriptBlock** parameter.</span></span> <span data-ttu-id="cd988-119">Чтобы указать скрипт, выполняемый заданием, используйте параметр **FilePath** .</span><span class="sxs-lookup"><span data-stu-id="cd988-119">To specify a script that the job runs, use the **FilePath** parameter.</span></span>

<span data-ttu-id="cd988-120">Windows PowerShell — запланированные задания используют те же Триггеры заданий и параметры задания, которые планировщик задач используют для запланированных задач.</span><span class="sxs-lookup"><span data-stu-id="cd988-120">Windows PowerShell-scheduled jobs use the same job triggers and job options that Task Scheduler uses for scheduled tasks.</span></span>

<span data-ttu-id="cd988-121">Параметр **триггера** `Register-ScheduledJob` добавляет один или несколько триггеров задания, которые запускают задание.</span><span class="sxs-lookup"><span data-stu-id="cd988-121">The **Trigger** parameter of `Register-ScheduledJob` adds one or more job triggers that start the job.</span></span> <span data-ttu-id="cd988-122">Параметр **Trigger** является необязательным, поэтому можно добавлять триггеры при создании запланированного задания, добавлять Триггеры заданий позже, добавлять параметр **RunNow** для немедленного запуска задания, использовать `Start-Job` командлет для немедленного запуска задания в любое время или сохранить неактивированное запланированное задание в качестве шаблона для других заданий.</span><span class="sxs-lookup"><span data-stu-id="cd988-122">The **Trigger** parameter is optional, so you can add triggers when you create the scheduled job, add job triggers later, add the **RunNow** parameter to start the job immediately, use the `Start-Job` cmdlet to start the job immediately at any time, or save the untriggered scheduled job as a template for other jobs.</span></span>

<span data-ttu-id="cd988-123">Параметр **Options** позволяет настраивать параметры для запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="cd988-123">The **Options** parameter lets you customize the options settings for the scheduled job.</span></span> <span data-ttu-id="cd988-124">Параметр **Options** является необязательным, поэтому можно задать параметры задания при создании запланированного задания или изменить их в любое время.</span><span class="sxs-lookup"><span data-stu-id="cd988-124">The **Options** parameter is optional, so you can set job options when you create the scheduled job or change them at any time.</span></span> <span data-ttu-id="cd988-125">Поскольку значения параметров задания могут запрещать выполнение запланированного задания, проверьте параметры задания и внимательно настройте их.</span><span class="sxs-lookup"><span data-stu-id="cd988-125">Because job option settings can prevent the scheduled job from running, review the job options and set them carefully.</span></span>

<span data-ttu-id="cd988-126">`Register-ScheduledJob` является одной из коллекций командлетов планирования заданий в модуле **PSScheduledJob** , который входит в состав Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cd988-126">`Register-ScheduledJob` is one of a collection of job scheduling cmdlets in the **PSScheduledJob** module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="cd988-127">Дополнительные сведения о запланированных заданиях см. в разделе о статьях в модуле **PSScheduledJob** .</span><span class="sxs-lookup"><span data-stu-id="cd988-127">For more information about Scheduled Jobs, see the About articles in the **PSScheduledJob** module.</span></span>
<span data-ttu-id="cd988-128">Импортируйте модуль **PSScheduledJob** и введите: `Get-Help about_Scheduled*` или см. [about_Scheduled_Jobs](./about/about_scheduled_jobs.md).</span><span class="sxs-lookup"><span data-stu-id="cd988-128">Import the **PSScheduledJob** module and then type: `Get-Help about_Scheduled*` or see [about_Scheduled_Jobs](./about/about_scheduled_jobs.md).</span></span>

<span data-ttu-id="cd988-129">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="cd988-129">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="cd988-130">Примеры</span><span class="sxs-lookup"><span data-stu-id="cd988-130">EXAMPLES</span></span>

### <span data-ttu-id="cd988-131">Пример 1. Создание запланированного задания</span><span class="sxs-lookup"><span data-stu-id="cd988-131">Example 1: Create a scheduled job</span></span>

<span data-ttu-id="cd988-132">В этом примере создается запланированное задание на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cd988-132">This example creates a scheduled job on the local computer.</span></span>

```powershell
Register-ScheduledJob -Name "Archive-Scripts" -ScriptBlock {
  Get-ChildItem $home\*.ps1 -Recurse |
    Copy-Item -Destination "\\Server\Share\PSScriptArchive"
}
```

<span data-ttu-id="cd988-133">`Register-ScheduledJob` использует параметр **Name** для создания запланированного задания **Archive-Scripts** .</span><span class="sxs-lookup"><span data-stu-id="cd988-133">`Register-ScheduledJob` uses the **Name** parameter to create the **Archive-Scripts** scheduled job.</span></span>
<span data-ttu-id="cd988-134">Запускается параметр **ScriptBlock** `Get-ChildItem` , который рекурсивно ищет `$home` файлы в каталоге `.ps1` .</span><span class="sxs-lookup"><span data-stu-id="cd988-134">The **ScriptBlock** parameter runs `Get-ChildItem` that searches the `$home` directory recursively for `.ps1` files.</span></span> <span data-ttu-id="cd988-135">`Copy-Item`Командлет копирует файлы в каталог, указанный параметром **Destination** .</span><span class="sxs-lookup"><span data-stu-id="cd988-135">The `Copy-Item` cmdlet copies the files to a directory specified by the **Destination** parameter.</span></span>

<span data-ttu-id="cd988-136">Так как запланированное задание не содержит триггер, оно не запускается автоматически.</span><span class="sxs-lookup"><span data-stu-id="cd988-136">Because the scheduled job doesn't contain a trigger, it's not started automatically.</span></span> <span data-ttu-id="cd988-137">Можно добавить триггеры заданий с помощью `Add-JobTrigger` `Start-Job` командлета, чтобы запустить задание по требованию, или использовать запланированное задание в качестве шаблона для других запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="cd988-137">You can add job triggers with `Add-JobTrigger`, use the `Start-Job` cmdlet to start the job on demand, or use the scheduled job as a template for other scheduled jobs.</span></span>

### <span data-ttu-id="cd988-138">Пример 2. Создание запланированного задания с триггерами и настраиваемыми параметрами</span><span class="sxs-lookup"><span data-stu-id="cd988-138">Example 2: Create a scheduled job with triggers and custom options</span></span>

<span data-ttu-id="cd988-139">В этом примере показано, как создать запланированное задание, имеющее триггер задания и пользовательские параметры задания.</span><span class="sxs-lookup"><span data-stu-id="cd988-139">This example shows how to create a scheduled job that has a job trigger and custom job options.</span></span>

```powershell
$O = New-ScheduledJobOption -WakeToRun -StartIfIdle -MultipleInstancePolicy Queue
$T = New-JobTrigger -Weekly -At "9:00 PM" -DaysOfWeek Monday -WeeksInterval 2
$path = "\\Srv01\Scripts\UpdateVersion.ps1"
Register-ScheduledJob -Name "UpdateVersion" -FilePath $path -ScheduledJobOption $O -Trigger $T
```

<span data-ttu-id="cd988-140">`$O`Переменная хранит объект параметра задания, `New-ScheduledJobOption` созданный командлетом.</span><span class="sxs-lookup"><span data-stu-id="cd988-140">The `$O` variable stores the job option object that the `New-ScheduledJobOption` cmdlet created.</span></span> <span data-ttu-id="cd988-141">Эти параметры запускают запланированное задание, даже если компьютер не находится в режиме простоя, пробуждает компьютер для запуска задания, если это необходимо, и позволяет выполнять несколько экземпляров задания в ряде.</span><span class="sxs-lookup"><span data-stu-id="cd988-141">The options start the scheduled job even if the computer isn't idle, wakes the computer to run the job, if necessary, and allows multiple instances of the job to run in a series.</span></span>

<span data-ttu-id="cd988-142">`$T`Переменная сохраняет результат `New-JobTrigger` командлета для создания триггера задания, который запускает задание каждый второй понедельник в 9:00 PM.</span><span class="sxs-lookup"><span data-stu-id="cd988-142">The `$T` variable stores the result from the `New-JobTrigger` cmdlet to create job trigger that starts a job every other Monday at 9:00 PM.</span></span>

<span data-ttu-id="cd988-143">`$path`Переменная хранит путь к `UpdateVersion.ps1` файлу скрипта.</span><span class="sxs-lookup"><span data-stu-id="cd988-143">The `$path` variable stores the path to the `UpdateVersion.ps1` script file.</span></span>

<span data-ttu-id="cd988-144">`Register-ScheduledJob` использует параметр **Name** для создания запланированного задания **упдатеверсион** .</span><span class="sxs-lookup"><span data-stu-id="cd988-144">`Register-ScheduledJob` uses the **Name** paramter to create the **UpdateVersion** scheduled job.</span></span>
<span data-ttu-id="cd988-145">Параметр **FilePath** используется `$path` для указания скрипта, выполняемого заданием.</span><span class="sxs-lookup"><span data-stu-id="cd988-145">The **FilePath** parameter uses `$path` to specify the script that the job runs.</span></span> <span data-ttu-id="cd988-146">Параметр **scheduledjoboptions** использует параметры задания, хранящиеся в `$O` .</span><span class="sxs-lookup"><span data-stu-id="cd988-146">The **ScheduledJobOption** parameter uses the job options stored in `$O`.</span></span> <span data-ttu-id="cd988-147">Параметр **Trigger** использует Триггеры заданий, хранимые в `$T` .</span><span class="sxs-lookup"><span data-stu-id="cd988-147">The **Trigger** parameter uses the job triggers stored in `$T`.</span></span>

### <span data-ttu-id="cd988-148">Пример 3. Использование хэш-таблиц для задания параметров триггера и запланированного задания</span><span class="sxs-lookup"><span data-stu-id="cd988-148">Example 3: Use hash tables to specify a trigger and scheduled job options</span></span>

<span data-ttu-id="cd988-149">Этот пример действует так же, как и команда в примере 2.</span><span class="sxs-lookup"><span data-stu-id="cd988-149">This example has the same effect as the command in Example 2.</span></span> <span data-ttu-id="cd988-150">Он создает запланированное задание, используя хэш-таблицы для указания значений параметров **Trigger** и **scheduledjoboptions** .</span><span class="sxs-lookup"><span data-stu-id="cd988-150">It creates a scheduled job, using hash tables to specify the values of the **Trigger** and **ScheduledJobOption** parameters.</span></span> <span data-ttu-id="cd988-151">`$O`Переменные и, `$T` определенные в примере 2, заменяются хэш-таблицами.</span><span class="sxs-lookup"><span data-stu-id="cd988-151">The `$O` and `$T`variables defined in Example 2 are replaced with hash tables.</span></span>

```powershell
$T = @{
  Frequency="Weekly"
  At="9:00PM"
  DaysOfWeek="Monday"
  Interval=2
}
$O = @{
  WakeToRun=$true
  StartIfNotIdle=$false
  MultipleInstancePolicy="Queue"
}
Register-ScheduledJob -Trigger $T -ScheduledJobOption $O -Name UpdateVersion -FilePath "\\Srv01\Scripts\Update-Version.ps1"
```

### <span data-ttu-id="cd988-152">Пример 4. создание запланированных заданий на удаленных компьютерах</span><span class="sxs-lookup"><span data-stu-id="cd988-152">Example 4: Create scheduled jobs on remote computers</span></span>

<span data-ttu-id="cd988-153">В этом примере запланированное задание **енергидата** создается на нескольких удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="cd988-153">In this example, the **EnergyData** scheduled job is created on multiple remote computers.</span></span> <span data-ttu-id="cd988-154">Запланированное задание запускает сценарий, собирающий необработанные данные и сохраняющий их в запущенном журнале на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cd988-154">The scheduled job runs a script that gathers raw data and saves it in a running log on the remote computer.</span></span>

```powershell
$Cred = Get-Credential
$O = New-ScheduledJobOption -WakeToRun -StartIfIdle -MultipleInstancePolicy Queue
$T = New-JobTrigger -Weekly -At "9:00 PM" -DaysOfWeek Monday -WeeksInterval 2
Invoke-Command -ComputerName (Get-Content Servers.txt) -Credential $Cred -ScriptBlock {
  $params = @{
      Name = "Get-EnergyData"
      FilePath = "\\Srv01\Scripts\Get-EnergyData.ps1"
      ScheduledJobOption = $using:O
      Trigger = $using:T
  }
  Register-ScheduledJob @params
}
```

<span data-ttu-id="cd988-155">`$Cred`Переменная сохраняет учетные данные в объекте **PSCredential** для пользователя с разрешениями на создание запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="cd988-155">The `$Cred` variable stores credentials in a **PSCredential** object for a user with permissions to create scheduled jobs.</span></span> <span data-ttu-id="cd988-156">`$O`Переменная хранит параметры задания, созданные с помощью `New-ScheduledJobOption` .</span><span class="sxs-lookup"><span data-stu-id="cd988-156">The `$O` variable stores the job options created with `New-ScheduledJobOption`.</span></span> <span data-ttu-id="cd988-157">`$T`Переменная хранит Триггеры заданий, созданные с помощью `New-JobTrigger` .</span><span class="sxs-lookup"><span data-stu-id="cd988-157">The `$T` variable stores the job triggers created with `New-JobTrigger`.</span></span>

<span data-ttu-id="cd988-158">`Invoke-Command`Командлет использует параметр **ComputerName** для получения списка имен серверов из `Servers.txt` файла.</span><span class="sxs-lookup"><span data-stu-id="cd988-158">The `Invoke-Command` cmdlet uses the **ComputerName** parameter to get a list of server names from the `Servers.txt` file.</span></span> <span data-ttu-id="cd988-159">Параметр **Credential** получает объект учетных данных, хранящийся в `$Cred` .</span><span class="sxs-lookup"><span data-stu-id="cd988-159">The **Credential** parameter gets the credential object stored in `$Cred`.</span></span>
<span data-ttu-id="cd988-160">Параметр **ScriptBlock** выполняет `Register-ScheduledJob` команду на компьютерах в `Servers.txt` файле.</span><span class="sxs-lookup"><span data-stu-id="cd988-160">The **ScriptBlock** parameter runs a `Register-ScheduledJob` command on the computers in the `Servers.txt` file.</span></span>

<span data-ttu-id="cd988-161">Параметры для определяются `Register-ScheduledJob` параметром `$params` .</span><span class="sxs-lookup"><span data-stu-id="cd988-161">The parameters for `Register-ScheduledJob` are defined by `$params`.</span></span> <span data-ttu-id="cd988-162">Параметры **Name** указывают, что задание называется **Get-енергидата** на каждом удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cd988-162">The **Name** parameters specifies the job is named **Get-EnergyData** on each remote computer.</span></span> <span data-ttu-id="cd988-163">**FilePath** задает расположение `EnergyData.ps1` скрипта.</span><span class="sxs-lookup"><span data-stu-id="cd988-163">**FilePath** provides the location of the `EnergyData.ps1` script.</span></span> <span data-ttu-id="cd988-164">Сценарий находится на файловом сервере, доступном всем участвующим компьютерам. Задание выполняется по расписанию, заданному триггерами заданий в `$T` , а также в параметрах задания в `$O` .</span><span class="sxs-lookup"><span data-stu-id="cd988-164">The script is located on a file server that is available to all participating computers.The job runs on the schedule specified by the job triggers in `$T` and the job options in `$O`.</span></span>

<span data-ttu-id="cd988-165">`Register-ScheduledJob @params`Команда создает запланированное задание с параметрами из блока script.</span><span class="sxs-lookup"><span data-stu-id="cd988-165">The `Register-ScheduledJob @params` command creates the scheduled job with the parameters from the script block.</span></span>

### <span data-ttu-id="cd988-166">Пример 5. Создание запланированного задания, запускающего сценарий на удаленных компьютерах</span><span class="sxs-lookup"><span data-stu-id="cd988-166">Example 5: Create a scheduled job that runs a script on remote computers</span></span>

<span data-ttu-id="cd988-167">В этом примере создается запланированное задание **коллектенергидата** на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cd988-167">This example creates the **CollectEnergyData** scheduled job on the local computer.</span></span> <span data-ttu-id="cd988-168">Задание выполняется на нескольких удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="cd988-168">The job runs on multiple remote computers.</span></span>

```powershell
$Admin = Get-Credential
$T = New-JobTrigger -Weekly -At "9:00 PM" -DaysOfWeek Monday -WeeksInterval 2
Register-ScheduledJob -Name "CollectEnergyData" -Trigger $T -MaxResultCount 99 -ScriptBlock {
  $params = @{
    AsJob = $true
    ComputerName = (Get-Content Servers.txt)
    FilePath = '\\Srv01\Scripts\Get-EnergyData.ps1'
    Credential = $using:Admin
    Authentication = 'CredSSP'
  }
  Invoke-Command @params
}
```

<span data-ttu-id="cd988-169">`$Admin`Переменная хранит учетные данные пользователя с разрешениями на выполнение команд в объекте **PSCredential** .</span><span class="sxs-lookup"><span data-stu-id="cd988-169">The `$Admin` variable stores credentials for a user with permissions to run the commands in a **PSCredential** object.</span></span> <span data-ttu-id="cd988-170">`$T`Переменная хранит Триггеры заданий, созданные с помощью `New-JobTrigger` .</span><span class="sxs-lookup"><span data-stu-id="cd988-170">The `$T` variable stores the job triggers created with `New-JobTrigger`.</span></span>

<span data-ttu-id="cd988-171">`Register-ScheduledJob`Командлет использует параметр **Name** для создания запланированного задания **коллектенергидата** на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cd988-171">The `Register-ScheduledJob` cmdlet uses the **Name** parameter to create the **CollectEnergyData** scheduled job on the local computer.</span></span> <span data-ttu-id="cd988-172">Параметр **Trigger** указывает триггеры задания в `$T` , а параметр **максресулткаунт** увеличивает число сохраненных результатов до 99.</span><span class="sxs-lookup"><span data-stu-id="cd988-172">The **Trigger** parameter specifies the job triggers in `$T` and the **MaxResultCount** parameter increases the number of saved results to 99.</span></span>

<span data-ttu-id="cd988-173">Параметр **ScriptBlock** определяет `Invoke-Command` параметры с помощью `$params` .</span><span class="sxs-lookup"><span data-stu-id="cd988-173">The **ScriptBlock** parameter defines the `Invoke-Command` parameters with `$params`.</span></span> <span data-ttu-id="cd988-174">Параметр **AsJob** создает объект фонового задания на локальном компьютере, даже если `Energydata.ps1` сценарий выполняется на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="cd988-174">The **AsJob** parameter creates the background job object on the local computer, even though the `Energydata.ps1` script runs on the remote computers.</span></span> <span data-ttu-id="cd988-175">Параметр **ComputerName** возвращает список имен серверов из `Servers.txt` файла.</span><span class="sxs-lookup"><span data-stu-id="cd988-175">The **ComputerName** parameter gets a list of server names from the `Servers.txt` file.</span></span> <span data-ttu-id="cd988-176">Параметр **Credential** указывает учетную запись пользователя, имеющую разрешение на выполнение скриптов на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="cd988-176">The **Credential** parameter specifies a user account that has permission to run scripts on the remote computers.</span></span> <span data-ttu-id="cd988-177">И параметр **authentication** задает значение **CredSSP** , разрешающее делегированные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="cd988-177">And, the **Authentication** parameter specifies a value of **CredSSP** to allow delegated credentials.</span></span>

<span data-ttu-id="cd988-178">`Invoke-Command @params`Запускает команду с параметрами из блока скрипта.</span><span class="sxs-lookup"><span data-stu-id="cd988-178">The `Invoke-Command @params` runs the command with the parameters from the script block.</span></span>

## <span data-ttu-id="cd988-179">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cd988-179">PARAMETERS</span></span>

### <span data-ttu-id="cd988-180">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="cd988-180">-ArgumentList</span></span>

<span data-ttu-id="cd988-181">Указывает значения для параметров сценария, который определяется параметром **FilePath** , или для команды, которая определяется параметром **ScriptBlock** .</span><span class="sxs-lookup"><span data-stu-id="cd988-181">Specifies values for the parameters of the script that is specified by the **FilePath** parameter or for the command that is specified by the **ScriptBlock** parameter.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cd988-182">-Authentication</span><span class="sxs-lookup"><span data-stu-id="cd988-182">-Authentication</span></span>

<span data-ttu-id="cd988-183">Задает механизм, используемый при проверке подлинности учетных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="cd988-183">Specifies the mechanism that is used to authenticate the user's credentials.</span></span> <span data-ttu-id="cd988-184">Значение по умолчанию — Default.</span><span class="sxs-lookup"><span data-stu-id="cd988-184">The default value is Default.</span></span>

<span data-ttu-id="cd988-185">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="cd988-185">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="cd988-186">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="cd988-186">Default</span></span>
- <span data-ttu-id="cd988-187">Базовый</span><span class="sxs-lookup"><span data-stu-id="cd988-187">Basic</span></span>
- <span data-ttu-id="cd988-188">CredSSP</span><span class="sxs-lookup"><span data-stu-id="cd988-188">Credssp</span></span>
- <span data-ttu-id="cd988-189">Digest (дайджест)</span><span class="sxs-lookup"><span data-stu-id="cd988-189">Digest</span></span>
- <span data-ttu-id="cd988-190">Kerberos</span><span class="sxs-lookup"><span data-stu-id="cd988-190">Kerberos</span></span>
- <span data-ttu-id="cd988-191">Согласование</span><span class="sxs-lookup"><span data-stu-id="cd988-191">Negotiate</span></span>
- <span data-ttu-id="cd988-192">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="cd988-192">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="cd988-193">Дополнительные сведения о значениях этого параметра см. в разделе [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="cd988-193">For more information about the values of this parameter, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="cd988-194">Проверка подлинности CredSSP, при применении которой учетные данные пользователя передаются на удаленный компьютер, предназначена для команд, требующих проверки подлинности для нескольких ресурсов, например для доступа к удаленной сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="cd988-194">Credential Security Service Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="cd988-195">Этот механизм повышает риск безопасности удаленной операции.</span><span class="sxs-lookup"><span data-stu-id="cd988-195">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="cd988-196">Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="cd988-196">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cd988-197">-Confirm</span><span class="sxs-lookup"><span data-stu-id="cd988-197">-Confirm</span></span>

<span data-ttu-id="cd988-198">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="cd988-198">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="cd988-199">-Credential</span><span class="sxs-lookup"><span data-stu-id="cd988-199">-Credential</span></span>

<span data-ttu-id="cd988-200">Указывает учетную запись пользователя, обладающую разрешением для выполнения запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="cd988-200">Specifies a user account that has permission to run the scheduled job.</span></span> <span data-ttu-id="cd988-201">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="cd988-201">The default is the current user.</span></span>

<span data-ttu-id="cd988-202">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , например один из `Get-Credential` командлетов.</span><span class="sxs-lookup"><span data-stu-id="cd988-202">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object, such as one from the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="cd988-203">Если ввести только имя пользователя, появится запрос на ввод пароля.</span><span class="sxs-lookup"><span data-stu-id="cd988-203">If you enter only a user name, you're prompted for a password.</span></span>

<span data-ttu-id="cd988-204">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="cd988-204">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="cd988-205">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="cd988-205">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cd988-206">-FilePath</span><span class="sxs-lookup"><span data-stu-id="cd988-206">-FilePath</span></span>

<span data-ttu-id="cd988-207">Указывает сценарий, запускаемый запланированным заданием.</span><span class="sxs-lookup"><span data-stu-id="cd988-207">Specifies a script that the scheduled job runs.</span></span> <span data-ttu-id="cd988-208">Введите путь к `.ps1` файлу на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cd988-208">Enter the path to a `.ps1` file on the local computer.</span></span> <span data-ttu-id="cd988-209">Чтобы задать значения по умолчанию для параметров сценария, используйте параметр **ArgumentList** .</span><span class="sxs-lookup"><span data-stu-id="cd988-209">To specify default values for the script parameters, use the **ArgumentList** parameter.</span></span>
<span data-ttu-id="cd988-210">Каждая `Register-ScheduledJob` команда должна использовать либо параметры **ScriptBlock** , либо **FilePath** .</span><span class="sxs-lookup"><span data-stu-id="cd988-210">Every `Register-ScheduledJob` command must use either the **ScriptBlock** or **FilePath** parameters.</span></span>

```yaml
Type: System.String
Parameter Sets: FilePath
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cd988-211">-Инитиализатионскрипт</span><span class="sxs-lookup"><span data-stu-id="cd988-211">-InitializationScript</span></span>

<span data-ttu-id="cd988-212">Указывает полный путь к сценарию Windows PowerShell ( `.ps1` ).</span><span class="sxs-lookup"><span data-stu-id="cd988-212">Specifies the fully qualified path to a Windows PowerShell script (`.ps1`).</span></span> <span data-ttu-id="cd988-213">Сценарий инициализации выполняется в сеансе, который создается для фонового задания перед командами, которые задаются параметром **ScriptBlock** , или сценарием, который задается параметром **FilePath** .</span><span class="sxs-lookup"><span data-stu-id="cd988-213">The initialization script runs in the session that is created for the background job before the commands that are specified by the **ScriptBlock** parameter or the script that is specified by the **FilePath** parameter.</span></span> <span data-ttu-id="cd988-214">Сценарий инициализации можно использовать для настройки сеанса, например, для добавления файлов, функций или псевдонимов, создания каталогов или проверки наличия необходимых компонентов.</span><span class="sxs-lookup"><span data-stu-id="cd988-214">You can use the initialization script to configure the session, such as adding files, functions, or aliases, creating directories, or checking for prerequisites.</span></span>

<span data-ttu-id="cd988-215">Чтобы задать сценарий, который выполняет команды основного задания, используйте параметр **FilePath** .</span><span class="sxs-lookup"><span data-stu-id="cd988-215">To specify a script that runs the primary job commands, use the **FilePath** parameter.</span></span>

<span data-ttu-id="cd988-216">Если скрипт инициализации создает ошибку, даже устранимую ошибку, текущий экземпляр запланированного задания не выполняется и его состояние — **Failed** .</span><span class="sxs-lookup"><span data-stu-id="cd988-216">If the initialization script generates an error, even a non-terminating error, the current instance of the scheduled job doesn't run and its status is **Failed** .</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cd988-217">-Максресулткаунт</span><span class="sxs-lookup"><span data-stu-id="cd988-217">-MaxResultCount</span></span>

<span data-ttu-id="cd988-218">Указывает, сколько записей результатов задания хранится для запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="cd988-218">Specifies how many job result entries are maintained for the scheduled job.</span></span> <span data-ttu-id="cd988-219">Значение по умолчанию: 32.</span><span class="sxs-lookup"><span data-stu-id="cd988-219">The default value is 32.</span></span>

<span data-ttu-id="cd988-220">Windows PowerShell сохраняет журнал выполнения и результаты каждого активированного экземпляра запланированного задания на диске.</span><span class="sxs-lookup"><span data-stu-id="cd988-220">Windows PowerShell saves the execution history and results of each triggered instance of the scheduled job on disk.</span></span> <span data-ttu-id="cd988-221">Значение этого параметра определяет количество результатов экземпляра задания, сохраняемых для данного запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="cd988-221">The value of this parameter determines the number of job instance results that are saved for this scheduled job.</span></span> <span data-ttu-id="cd988-222">Когда число результатов экземпляра задания превышает это значение, Windows PowerShell удаляет результаты самого старого экземпляра задания, чтобы освободить место для результатов более нового экземпляра задания.</span><span class="sxs-lookup"><span data-stu-id="cd988-222">When the number of job instance results exceeds this value, Windows PowerShell deletes the results of the oldest job instance to make room for the results of the newest job instance.</span></span>

<span data-ttu-id="cd988-223">Журнал выполнения задания и результаты задания сохраняются в `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs\<JobName>\Output\<Timestamp>`</span><span class="sxs-lookup"><span data-stu-id="cd988-223">The job execution history and job results are saved in the `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs\<JobName>\Output\<Timestamp>`</span></span>
<span data-ttu-id="cd988-224">каталоги на компьютере, на котором создается задание.</span><span class="sxs-lookup"><span data-stu-id="cd988-224">directories on the computer on which the job is created.</span></span> <span data-ttu-id="cd988-225">Чтобы просмотреть журнал выполнения, используйте `Get-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="cd988-225">To see the execution history, use the `Get-Job` cmdlet.</span></span> <span data-ttu-id="cd988-226">Чтобы получить результаты задания, используйте `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="cd988-226">To get the job results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="cd988-227">Параметр **MaxResultCount** задает значение свойства ExecutionHistoryLength для запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="cd988-227">The **MaxResultCount** parameter sets the value of the ExecutionHistoryLength property of the scheduled job.</span></span>

<span data-ttu-id="cd988-228">Чтобы удалить текущий журнал выполнения и результаты задания, используйте параметр **клеарексекутионхистори** `Set-ScheduledJob` командлета.</span><span class="sxs-lookup"><span data-stu-id="cd988-228">To delete the current execution history and job results, use the **ClearExecutionHistory** parameter of the `Set-ScheduledJob` cmdlet.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cd988-229">-Name</span><span class="sxs-lookup"><span data-stu-id="cd988-229">-Name</span></span>

<span data-ttu-id="cd988-230">Задает имя для запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="cd988-230">Specifies a name for the scheduled job.</span></span> <span data-ttu-id="cd988-231">Данное имя также используется для всех запущенных экземпляров этого запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="cd988-231">The name is also used for all started instances of the scheduled job.</span></span> <span data-ttu-id="cd988-232">Это имя должно быть уникальным на компьютере.</span><span class="sxs-lookup"><span data-stu-id="cd988-232">The name must be unique on the computer.</span></span> <span data-ttu-id="cd988-233">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="cd988-233">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cd988-234">-RunAs32</span><span class="sxs-lookup"><span data-stu-id="cd988-234">-RunAs32</span></span>

<span data-ttu-id="cd988-235">Запускает запланированное задание в 32-разрядном процессе.</span><span class="sxs-lookup"><span data-stu-id="cd988-235">Runs the scheduled job in a 32-bit process.</span></span>

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

### <span data-ttu-id="cd988-236">-Руневери</span><span class="sxs-lookup"><span data-stu-id="cd988-236">-RunEvery</span></span>

<span data-ttu-id="cd988-237">Используется для указания периодичности выполнения задания.</span><span class="sxs-lookup"><span data-stu-id="cd988-237">Used to specify how often to run the job.</span></span> <span data-ttu-id="cd988-238">Например, этот параметр используется для запуска задания каждые 15 минут.</span><span class="sxs-lookup"><span data-stu-id="cd988-238">For example, use this option to run a job every 15 minutes.</span></span>

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

### <span data-ttu-id="cd988-239">-RunNow</span><span class="sxs-lookup"><span data-stu-id="cd988-239">-RunNow</span></span>

<span data-ttu-id="cd988-240">Запускает задание немедленно, как только `Register-ScheduledJob` запускается командлет.</span><span class="sxs-lookup"><span data-stu-id="cd988-240">Starts a job immediately, as soon as the `Register-ScheduledJob` cmdlet is run.</span></span> <span data-ttu-id="cd988-241">Этот параметр устраняет необходимость в активации планировщик задач для запуска сценария Windows PowerShell сразу после регистрации и не требует от пользователей создания триггера, указывающего дату и время начала.</span><span class="sxs-lookup"><span data-stu-id="cd988-241">This parameter eliminates the need to trigger Task Scheduler to run a Windows PowerShell script immediately after registration, and doesn't require users to create a trigger that specifies a starting date and time.</span></span>

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

### <span data-ttu-id="cd988-242">-Scheduledjoboptions</span><span class="sxs-lookup"><span data-stu-id="cd988-242">-ScheduledJobOption</span></span>

<span data-ttu-id="cd988-243">Задает параметры для запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="cd988-243">Sets options for the scheduled job.</span></span> <span data-ttu-id="cd988-244">Введите объект **счедуледжобоптионс** , например, созданный с помощью `New-ScheduledJobOption` командлета, или значение хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="cd988-244">Enter a **ScheduledJobOptions** object, such as one that you create by using the `New-ScheduledJobOption` cmdlet, or a hash table value.</span></span>

<span data-ttu-id="cd988-245">Параметры запланированного задания можно задать при регистрации задания по расписанию или с помощью `Set-ScheduledJobOption` `Set-ScheduledJob` командлетов или для изменения параметров.</span><span class="sxs-lookup"><span data-stu-id="cd988-245">You can set options for a scheduled job when you register the schedule job or use the `Set-ScheduledJobOption` or `Set-ScheduledJob` cmdlets to change the options.</span></span>

<span data-ttu-id="cd988-246">Многие параметры и их значения по умолчанию определяют, запускается ли запланированное задание и когда это происходит.</span><span class="sxs-lookup"><span data-stu-id="cd988-246">Many of the options and their default values determine whether and when a scheduled job runs.</span></span> <span data-ttu-id="cd988-247">Обязательно просмотрите эти параметры перед планированием задания.</span><span class="sxs-lookup"><span data-stu-id="cd988-247">Be sure to review these options before scheduling a job.</span></span> <span data-ttu-id="cd988-248">Описание параметров запланированного задания, включая значения по умолчанию, см. в разделе `New-ScheduledJobOption` .</span><span class="sxs-lookup"><span data-stu-id="cd988-248">For a description of the scheduled job options, including the default values, see `New-ScheduledJobOption`.</span></span>

<span data-ttu-id="cd988-249">Чтобы отправить хэш-таблицу, используйте следующие ключи.</span><span class="sxs-lookup"><span data-stu-id="cd988-249">To submit a hash table, use the following keys.</span></span> <span data-ttu-id="cd988-250">Ключи в следующей хэш-таблице ключи приведены со значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cd988-250">In the following hash table, the keys are shown with their default values.</span></span>

`@{StartIfOnBattery=$False; StopIfGoingOnBattery=$True; WakeToRun=$False; StartIfNotIdle=$False; IdleDuration="00:10:00"; IdleTimeout="01:00:00"; StopIfGoingOffIdle=$True; RestartOnIdleResume=$False; ShowInTaskScheduler=$True; RunElevated=$False; RunWithoutNetwork=$False; DoNotAllowDemandStart=$False; MultipleInstancePolicy="IgnoreNew"}`

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cd988-251">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="cd988-251">-ScriptBlock</span></span>

<span data-ttu-id="cd988-252">Указывает команды, выполняемые запланированным заданием.</span><span class="sxs-lookup"><span data-stu-id="cd988-252">Specifies the commands that the scheduled job runs.</span></span> <span data-ttu-id="cd988-253">Чтобы создать блок скрипта, заключите команды в фигурные скобки ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="cd988-253">Enclose the commands in curly braces (`{}`) to create a script block.</span></span> <span data-ttu-id="cd988-254">Чтобы задать значения по умолчанию для параметров команды, используйте параметр **ArgumentList** .</span><span class="sxs-lookup"><span data-stu-id="cd988-254">To specify default values for command parameters, use the **ArgumentList** parameter.</span></span>

<span data-ttu-id="cd988-255">Каждая `Register-ScheduledJob` команда должна использовать либо параметры **ScriptBlock** , либо **FilePath** .</span><span class="sxs-lookup"><span data-stu-id="cd988-255">Every `Register-ScheduledJob` command must use either the **ScriptBlock** or **FilePath** parameters.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cd988-256">-Триггер</span><span class="sxs-lookup"><span data-stu-id="cd988-256">-Trigger</span></span>

<span data-ttu-id="cd988-257">Задает триггеры для запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="cd988-257">Specifies the triggers for the scheduled job.</span></span> <span data-ttu-id="cd988-258">Введите один или несколько объектов **ScheduledJobTrigger** , например объекты, `New-JobTrigger` возвращаемые командлетом, или хэш-таблицу ключей и значений триггера задания.</span><span class="sxs-lookup"><span data-stu-id="cd988-258">Enter one or more **ScheduledJobTrigger** objects, such as the objects that the `New-JobTrigger` cmdlet returns, or a hash table of job trigger keys and values.</span></span>

<span data-ttu-id="cd988-259">Триггер задания запускает задание по расписанию.</span><span class="sxs-lookup"><span data-stu-id="cd988-259">A job trigger starts the schedule job.</span></span> <span data-ttu-id="cd988-260">Триггер может указывать однократное или регулярное расписание или событие, например вход пользователя в систему или запуск Windows.</span><span class="sxs-lookup"><span data-stu-id="cd988-260">The trigger can specify a one-time or recurring scheduled or an event, such as when a user logs on or Windows starts.</span></span>

<span data-ttu-id="cd988-261">Параметр **Trigger** не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="cd988-261">The **Trigger** parameter is optional.</span></span> <span data-ttu-id="cd988-262">Вы можете добавить триггер при создании запланированного задания, использовать `Add-JobTrigger` `Set-JobTrigger` командлеты, или, `Set-ScheduledJob` чтобы добавить или изменить триггеры заданий позже, или использовать `Start-Job` командлет для немедленного запуска запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="cd988-262">You can add a trigger when you create the scheduled job, use the `Add-JobTrigger`, `Set-JobTrigger`, or `Set-ScheduledJob` cmdlets to add or change job triggers later, or use the `Start-Job` cmdlet to start the scheduled job immediately.</span></span> <span data-ttu-id="cd988-263">Можно также создать и поддерживать запланированное задание без триггера, используемое в качестве шаблона.</span><span class="sxs-lookup"><span data-stu-id="cd988-263">You can also create and maintain a scheduled job without a trigger that is used as a template.</span></span>

<span data-ttu-id="cd988-264">Чтобы отправить хэш-таблицу, используйте следующие ключи:</span><span class="sxs-lookup"><span data-stu-id="cd988-264">To submit a hash table, use the following keys:</span></span>

- <span data-ttu-id="cd988-265">**Частота** : ежедневно, еженедельно, AtStartup, AtLogon</span><span class="sxs-lookup"><span data-stu-id="cd988-265">**Frequency** : Daily, Weekly, AtStartup, AtLogon</span></span>
- <span data-ttu-id="cd988-266">**At** : любая допустимая строка времени</span><span class="sxs-lookup"><span data-stu-id="cd988-266">**At** : Any valid time string</span></span>
- <span data-ttu-id="cd988-267">**DaysOfWeek** — любое сочетание названий дней</span><span class="sxs-lookup"><span data-stu-id="cd988-267">**DaysOfWeek** - Any combination of day names</span></span>
- <span data-ttu-id="cd988-268">**Interval** — любой допустимый интервал частоты</span><span class="sxs-lookup"><span data-stu-id="cd988-268">**Interval** - Any valid frequency interval</span></span>
- <span data-ttu-id="cd988-269">**Рандомделай** : любая допустимая строка TimeSpan</span><span class="sxs-lookup"><span data-stu-id="cd988-269">**RandomDelay** : Any valid timespan string</span></span>
- <span data-ttu-id="cd988-270">**Пользователь** : любой допустимый пользователь.</span><span class="sxs-lookup"><span data-stu-id="cd988-270">**User** : Any valid user.</span></span> <span data-ttu-id="cd988-271">Используется только с значением частоты AtLogon</span><span class="sxs-lookup"><span data-stu-id="cd988-271">Used only with the AtLogon frequency value</span></span>

<span data-ttu-id="cd988-272">Пример:</span><span class="sxs-lookup"><span data-stu-id="cd988-272">For example:</span></span>

`@{Frequency="Once"; At="3am"; DaysOfWeek="Monday", "Wednesday"; Interval=2; RandomDelay="30minutes"; User="Domain1\User01"}`

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cd988-273">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="cd988-273">-WhatIf</span></span>

<span data-ttu-id="cd988-274">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="cd988-274">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="cd988-275">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="cd988-275">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="cd988-276">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="cd988-276">CommonParameters</span></span>

<span data-ttu-id="cd988-277">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="cd988-277">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cd988-278">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="cd988-278">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cd988-279">Входные данные</span><span class="sxs-lookup"><span data-stu-id="cd988-279">INPUTS</span></span>

### <span data-ttu-id="cd988-280">Нет</span><span class="sxs-lookup"><span data-stu-id="cd988-280">None</span></span>

<span data-ttu-id="cd988-281">Вы не можете отправить входные данные по конвейеру в этот командлет.</span><span class="sxs-lookup"><span data-stu-id="cd988-281">You can't send input down the pipeline to this cmdlet.</span></span>

## <span data-ttu-id="cd988-282">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="cd988-282">OUTPUTS</span></span>

### <span data-ttu-id="cd988-283">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span><span class="sxs-lookup"><span data-stu-id="cd988-283">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>

## <span data-ttu-id="cd988-284">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="cd988-284">NOTES</span></span>

<span data-ttu-id="cd988-285">Каждое запланированное задание сохраняется в подкаталоге `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` каталога на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cd988-285">Each scheduled job is saved in a subdirectory of the `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` directory on the local computer.</span></span>
<span data-ttu-id="cd988-286">Подкаталог имеет имя для запланированного задания и содержит XML-файл для запланированного задания и записи его журнала выполнения.</span><span class="sxs-lookup"><span data-stu-id="cd988-286">The subdirectory is named for the scheduled job and contains an XML file for the scheduled job and records of its execution history.</span></span> <span data-ttu-id="cd988-287">Дополнительные сведения о запланированных заданиях на диске см. в разделе [about_Scheduled_Jobs_Advanced](./about/about_scheduled_jobs_advanced.md).</span><span class="sxs-lookup"><span data-stu-id="cd988-287">For more information about scheduled jobs on disk, see [about_Scheduled_Jobs_Advanced](./about/about_scheduled_jobs_advanced.md).</span></span>

<span data-ttu-id="cd988-288">Запланированные задания, создаваемые в Windows PowerShell, отображаются в планировщик задач в `Library\Microsoft\Windows\PowerShell\ScheduledJobs` папке планировщик задач.</span><span class="sxs-lookup"><span data-stu-id="cd988-288">Scheduled jobs that you create in Windows PowerShell appear in Task Scheduler in the Task Scheduler `Library\Microsoft\Windows\PowerShell\ScheduledJobs` folder.</span></span> <span data-ttu-id="cd988-289">Планировщик заданий можно использовать для просмотра и изменения запланированного задания.</span><span class="sxs-lookup"><span data-stu-id="cd988-289">You can use Task Scheduler to view and edit the scheduled job.</span></span>

<span data-ttu-id="cd988-290">Для управления запланированными заданиями, созданными с помощью командлетов запланированных заданий, можно использовать планировщик задач, средство командной строки **schtasks.exe** и командлеты планировщик задач.</span><span class="sxs-lookup"><span data-stu-id="cd988-290">You can use Task Scheduler, the **schtasks.exe** command-line tool, and the Task Scheduler cmdlets to manage scheduled jobs that you create with the Scheduled Job cmdlets.</span></span> <span data-ttu-id="cd988-291">Однако нельзя использовать командлеты запланированных заданий для управления задачами, созданными в планировщик задач.</span><span class="sxs-lookup"><span data-stu-id="cd988-291">However, you can't use the Scheduled Job cmdlets to manage tasks that you create in Task Scheduler.</span></span>

<span data-ttu-id="cd988-292">При сбое команды запланированного задания Windows PowerShell возвращает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="cd988-292">If a scheduled job command fails, Windows PowerShell returns an error message.</span></span> <span data-ttu-id="cd988-293">Однако если задание завершается сбоем, когда планировщик задач пытается его запустить, то эта ошибка недоступна для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cd988-293">However, if the job fails when Task Scheduler tries to run it, the error isn't available to Windows PowerShell.</span></span>

<span data-ttu-id="cd988-294">Если запланированное задание не выполняется, используйте следующие методы, чтобы найти причину:</span><span class="sxs-lookup"><span data-stu-id="cd988-294">If a scheduled job doesn't run, use the following methods to find the reason:</span></span>

- <span data-ttu-id="cd988-295">Убедитесь, что триггер задания задан правильно.</span><span class="sxs-lookup"><span data-stu-id="cd988-295">Verify that the job trigger is set properly.</span></span>
  - <span data-ttu-id="cd988-296">Убедитесь, что условия, заданные в параметрах задания, удовлетворены.</span><span class="sxs-lookup"><span data-stu-id="cd988-296">Verify that the conditions set in the job options are satisfied.</span></span>
- <span data-ttu-id="cd988-297">Убедитесь, что учетная запись пользователя, под которой выполняется задание, имеет разрешение на выполнение команд или скриптов в задании.</span><span class="sxs-lookup"><span data-stu-id="cd988-297">Verify that the user account under which the job runs has permission to run the commands or scripts in the job.</span></span>
- <span data-ttu-id="cd988-298">Проверьте журнал планировщик задач на наличие ошибок.</span><span class="sxs-lookup"><span data-stu-id="cd988-298">Check the Task Scheduler history for errors.</span></span>
- <span data-ttu-id="cd988-299">Проверьте журнал событий планировщик задач на наличие ошибок.</span><span class="sxs-lookup"><span data-stu-id="cd988-299">Check the Task Scheduler event log for errors.</span></span>

<span data-ttu-id="cd988-300">Дополнительные сведения см. в разделе [about_Scheduled_Jobs_Troubleshooting](./about/about_scheduled_jobs_troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="cd988-300">For more information, see [about_Scheduled_Jobs_Troubleshooting](./about/about_scheduled_jobs_troubleshooting.md).</span></span>

## <span data-ttu-id="cd988-301">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="cd988-301">RELATED LINKS</span></span>

[<span data-ttu-id="cd988-302">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="cd988-302">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="cd988-303">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="cd988-303">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="cd988-304">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="cd988-304">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="cd988-305">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="cd988-305">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="cd988-306">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="cd988-306">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="cd988-307">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="cd988-307">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="cd988-308">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="cd988-308">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="cd988-309">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="cd988-309">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="cd988-310">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="cd988-310">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="cd988-311">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="cd988-311">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="cd988-312">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="cd988-312">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="cd988-313">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="cd988-313">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="cd988-314">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="cd988-314">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="cd988-315">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="cd988-315">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="cd988-316">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="cd988-316">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="cd988-317">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="cd988-317">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
