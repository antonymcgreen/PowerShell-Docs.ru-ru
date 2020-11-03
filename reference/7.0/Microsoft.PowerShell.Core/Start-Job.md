---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/start-job?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Job
ms.openlocfilehash: 7875419bed68251628b072a35d6c220e75b78c24
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226901"
---
# <span data-ttu-id="8d4a9-103">Start-Job</span><span class="sxs-lookup"><span data-stu-id="8d4a9-103">Start-Job</span></span>

## <span data-ttu-id="8d4a9-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="8d4a9-104">SYNOPSIS</span></span>
<span data-ttu-id="8d4a9-105">Запускает фоновое задание PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-105">Starts a PowerShell background job.</span></span>

## <span data-ttu-id="8d4a9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8d4a9-106">SYNTAX</span></span>

### <span data-ttu-id="8d4a9-107">ComputerName (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8d4a9-107">ComputerName (Default)</span></span>

```
Start-Job [-Name <String>] [-ScriptBlock] <ScriptBlock> [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>]
 [-WorkingDirectory <String>] [-RunAs32] [-PSVersion <Version>] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="8d4a9-108">DefinitionName</span><span class="sxs-lookup"><span data-stu-id="8d4a9-108">DefinitionName</span></span>

```
Start-Job [-DefinitionName] <String> [[-DefinitionPath] <String>] [[-Type] <String>]
 [-WorkingDirectory <String>] [<CommonParameters>]
```

### <span data-ttu-id="8d4a9-109">филепаскомпутернаме</span><span class="sxs-lookup"><span data-stu-id="8d4a9-109">FilePathComputerName</span></span>

```
Start-Job [-Name <String>] [-Credential <PSCredential>] [-FilePath] <String>
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>]
 [-WorkingDirectory <String>] [-RunAs32] [-PSVersion <Version>] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="8d4a9-110">литералфилепаскомпутернаме</span><span class="sxs-lookup"><span data-stu-id="8d4a9-110">LiteralFilePathComputerName</span></span>

```
Start-Job [-Name <String>] [-Credential <PSCredential>] -LiteralPath <String>
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>]
 [-WorkingDirectory <String>] [-RunAs32] [-PSVersion <Version>] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

## <span data-ttu-id="8d4a9-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8d4a9-111">DESCRIPTION</span></span>

<span data-ttu-id="8d4a9-112">`Start-Job`Командлет запускает фоновое задание PowerShell на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-112">The `Start-Job` cmdlet starts a PowerShell background job on the local computer.</span></span>

<span data-ttu-id="8d4a9-113">Фоновое задание PowerShell выполняет команду без взаимодействия с текущим сеансом.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-113">A PowerShell background job runs a command without interacting with the current session.</span></span> <span data-ttu-id="8d4a9-114">При запуске фонового задания объект задания возвращается немедленно, даже если для завершения задания требуется дополнительное время.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-114">When you start a background job, a job object returns immediately, even if the job takes an extended time to finish.</span></span> <span data-ttu-id="8d4a9-115">Пока задание выполняется, можно продолжать работу с данным сеансом.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-115">You can continue to work in the session without interruption while the job runs.</span></span>

<span data-ttu-id="8d4a9-116">Объект задания содержит полезные сведения о задании, но не содержит результатов задания.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-116">The job object contains useful information about the job, but it doesn't contain the job results.</span></span>
<span data-ttu-id="8d4a9-117">По завершении задания используйте `Receive-Job` командлет для получения результатов задания.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-117">When the job finishes, use the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="8d4a9-118">Дополнительные сведения о фоновых заданиях см. в разделе [about_Jobs](./About/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="8d4a9-118">For more information about background jobs, see [about_Jobs](./About/about_Jobs.md).</span></span>

<span data-ttu-id="8d4a9-119">Чтобы запустить фоновое задание на удаленном компьютере, используйте параметр **AsJob** , доступный во многих командлетах, или используйте `Invoke-Command` командлет для выполнения `Start-Job` команды на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-119">To run a background job on a remote computer, use the **AsJob** parameter that is available on many cmdlets, or use the `Invoke-Command` cmdlet to run a `Start-Job` command on the remote computer.</span></span> <span data-ttu-id="8d4a9-120">Дополнительные сведения см. в разделе [about_Remote_Jobs](./About/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="8d4a9-120">For more information, see [about_Remote_Jobs](./About/about_Remote_Jobs.md).</span></span>

<span data-ttu-id="8d4a9-121">Начиная с версии PowerShell 3,0, `Start-Job` можно запускать экземпляры пользовательских типов заданий, например запланированные задания.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-121">Starting in PowerShell 3.0, `Start-Job` can start instances of custom job types, such as scheduled jobs.</span></span> <span data-ttu-id="8d4a9-122">Сведения об использовании `Start-Job` для запуска заданий с пользовательскими типами см. в справочных документах по функциям типа задания.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-122">For information about how to use `Start-Job` to start jobs with custom types, see the help documents for the job type feature.</span></span>

<span data-ttu-id="8d4a9-123">Начиная с PowerShell 6,0 можно запускать задания с помощью `&` фонового оператора амперсанд ().</span><span class="sxs-lookup"><span data-stu-id="8d4a9-123">Beginning in PowerShell 6.0, you can start jobs using the ampersand (`&`) background operator.</span></span> <span data-ttu-id="8d4a9-124">Функции фонового оператора похожи на `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="8d4a9-124">The functionality of the background operator is similar to `Start-Job`.</span></span> <span data-ttu-id="8d4a9-125">Оба метода запуска задания создают объект задания **псремотингжоб** .</span><span class="sxs-lookup"><span data-stu-id="8d4a9-125">Both methods to start a job create a **PSRemotingJob** job object.</span></span> <span data-ttu-id="8d4a9-126">Дополнительные сведения об использовании амперсанда ( `&` ) см. в разделе [about_Operators](./about/about_operators.md#background-operator-).</span><span class="sxs-lookup"><span data-stu-id="8d4a9-126">For more information about using the ampersand (`&`), see [about_Operators](./about/about_operators.md#background-operator-).</span></span>

<span data-ttu-id="8d4a9-127">В PowerShell 7 появился параметр **WorkingDirectory** , указывающий начальную рабочую папку фонового задания.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-127">PowerShell 7 introduced the **WorkingDirectory** parameter that specifies a background job's initial working directory.</span></span> <span data-ttu-id="8d4a9-128">Если параметр не указан, `Start-Job` по умолчанию используется текущий рабочий каталог вызывающей стороны, запустившего задание.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-128">If the parameter isn't specified, `Start-Job` defaults to the current working directory of the caller that started the job.</span></span>

> [!NOTE]
> <span data-ttu-id="8d4a9-129">Создание внепроцессного фонового задания с помощью `Start-Job` не поддерживается в сценарии, в котором PowerShell размещается в других приложениях, например в функциях Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-129">Creating an out-of-process background job with `Start-Job` is not supported in the scenario where PowerShell is being hosted in other applications, such as the PowerShell Azure Functions.</span></span>
>
> <span data-ttu-id="8d4a9-130">Это связано с тем, что `Start-Job` зависит от `pwsh` исполняемого файла, который должен быть доступен `$PSHOME` для запуска незавершенного фонового задания, но когда приложение размещает PowerShell, оно напрямую использует пакеты SDK NuGet для PowerShell и не будет `pwsh` доставлено.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-130">This is by design because `Start-Job` depends on the `pwsh` executable to be available under `$PSHOME` to start an out-of-process background job, but when an application is hosting PowerShell, it's directly using the PowerShell NuGet SDK packages and won't have `pwsh` shipped along.</span></span>
>
> <span data-ttu-id="8d4a9-131">Подстановка в этом сценарии осуществляется `Start-ThreadJob` из модуля **[среаджоб](https://www.powershellgallery.com/packages/ThreadJob)**.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-131">The substitute in that scenario is `Start-ThreadJob` from the module **[ThreadJob](https://www.powershellgallery.com/packages/ThreadJob)**.</span></span>

## <span data-ttu-id="8d4a9-132">Примеры</span><span class="sxs-lookup"><span data-stu-id="8d4a9-132">EXAMPLES</span></span>

### <span data-ttu-id="8d4a9-133">Пример 1. Запуск фонового задания</span><span class="sxs-lookup"><span data-stu-id="8d4a9-133">Example 1: Start a background job</span></span>

<span data-ttu-id="8d4a9-134">В этом примере запускается фоновое задание, выполняемое на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-134">This example starts a background job that runs on the local computer.</span></span>

```powershell
Start-Job -ScriptBlock { Get-Process -Name pwsh }
```

```Output
Id  Name   PSJobTypeName   State     HasMoreData   Location    Command
--  ----   -------------   -----     -----------   --------    -------
1   Job1   BackgroundJob   Running   True          localhost   Get-Process -Name pwsh
```

<span data-ttu-id="8d4a9-135">`Start-Job` использует параметр **ScriptBlock** для выполнения в `Get-Process` качестве фонового задания.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-135">`Start-Job` uses the **ScriptBlock** parameter to run `Get-Process` as a background job.</span></span> <span data-ttu-id="8d4a9-136">Параметр **Name** указывает на поиск процессов PowerShell `pwsh` .</span><span class="sxs-lookup"><span data-stu-id="8d4a9-136">The **Name** parameter specifies to find PowerShell processes, `pwsh`.</span></span> <span data-ttu-id="8d4a9-137">Отображаются сведения о задании, и PowerShell возвращается в командную строку, пока задание выполняется в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-137">The job information is displayed and PowerShell returns to a prompt while the job runs in the background.</span></span>

<span data-ttu-id="8d4a9-138">Чтобы просмотреть выходные данные задания, используйте `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-138">To view the job's output, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="8d4a9-139">Например, `Receive-Job -Id 1`.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-139">For example, `Receive-Job -Id 1`.</span></span>

### <span data-ttu-id="8d4a9-140">Пример 2. Использование оператора Background для запуска фонового задания</span><span class="sxs-lookup"><span data-stu-id="8d4a9-140">Example 2: Use the background operator to start a background job</span></span>

<span data-ttu-id="8d4a9-141">В этом примере оператор амперсанд ( `&` ) используется для запуска фонового задания на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-141">This example uses the ampersand (`&`) background operator to start a background job on the local computer.</span></span> <span data-ttu-id="8d4a9-142">Задание получает тот же результат, что и `Start-Job` в примере 1.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-142">The job gets the same result as `Start-Job` in Example 1.</span></span>

```powershell
Get-Process -Name pwsh &
```

```Output
Id    Name   PSJobTypeName   State       HasMoreData     Location      Command
--    ----   -------------   -----       -----------     --------      -------
5     Job5   BackgroundJob   Running     True            localhost     Microsoft.PowerShell.Man...
```

<span data-ttu-id="8d4a9-143">`Get-Process` использует параметр **Name** для указания процессов PowerShell `pwsh` .</span><span class="sxs-lookup"><span data-stu-id="8d4a9-143">`Get-Process` uses the **Name** parameter to specify PowerShell processes, `pwsh`.</span></span> <span data-ttu-id="8d4a9-144">Амперсанд ( `&` ) запускает команду в качестве фонового задания.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-144">The ampersand (`&`) runs the command as a background job.</span></span> <span data-ttu-id="8d4a9-145">Отображаются сведения о задании, и PowerShell возвращается в командную строку, пока задание выполняется в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-145">The job information is displayed and PowerShell returns to a prompt while the job runs in the background.</span></span>

<span data-ttu-id="8d4a9-146">Чтобы просмотреть выходные данные задания, используйте `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-146">To view the job's output, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="8d4a9-147">Например, `Receive-Job -Id 5`.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-147">For example, `Receive-Job -Id 5`.</span></span>

### <span data-ttu-id="8d4a9-148">Пример 3. Запуск задания с помощью Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="8d4a9-148">Example 3: Start a job using Invoke-Command</span></span>

<span data-ttu-id="8d4a9-149">В этом примере выполняется задание на нескольких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-149">This example runs a job on multiple computers.</span></span> <span data-ttu-id="8d4a9-150">Задание хранится в переменной и выполняется с помощью имени переменной в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-150">The job is stored in a variable and is executed by using the variable name on the PowerShell command line.</span></span>

```powershell
$jobWRM = Invoke-Command -ComputerName (Get-Content -Path C:\Servers.txt) -ScriptBlock {
   Get-Service -Name WinRM } -JobName WinRM -ThrottleLimit 16 -AsJob
```

<span data-ttu-id="8d4a9-151">Задание, которое использует, `Invoke-Command` создается и сохраняется в `$jobWRM` переменной.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-151">A job that uses `Invoke-Command` is created and stored in the `$jobWRM` variable.</span></span> <span data-ttu-id="8d4a9-152">`Invoke-Command` использует параметр **ComputerName** для указания компьютеров, на которых выполняется задание.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-152">`Invoke-Command` uses the **ComputerName** parameter to specify the computers where the job runs.</span></span> <span data-ttu-id="8d4a9-153">`Get-Content` Возвращает имена серверов из `C:\Servers.txt` файла.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-153">`Get-Content` gets the server names from the `C:\Servers.txt` file.</span></span>

<span data-ttu-id="8d4a9-154">Параметр **ScriptBlock** указывает команду, которая `Get-Service` Получает службу **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="8d4a9-154">The **ScriptBlock** parameter specifies a command that `Get-Service` gets the **WinRM** service.</span></span> <span data-ttu-id="8d4a9-155">Параметр **JobName** указывает понятное имя для задания, **WinRM**.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-155">The **JobName** parameter specifies a friendly name for the job, **WinRM**.</span></span> <span data-ttu-id="8d4a9-156">Параметр **ThrottleLimit** ограничивает количество одновременных команд до 16.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-156">The **ThrottleLimit** parameter limits the number of concurrent commands to 16.</span></span> <span data-ttu-id="8d4a9-157">Параметр **AsJob** запускает фоновое задание, которое выполняет команду на серверах.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-157">The **AsJob** parameter starts a background job that runs the command on the servers.</span></span>

### <span data-ttu-id="8d4a9-158">Пример 4. Получение сведений о задании</span><span class="sxs-lookup"><span data-stu-id="8d4a9-158">Example 4: Get job information</span></span>

<span data-ttu-id="8d4a9-159">Этот пример получает сведения о задании и отображает результаты завершенного задания, которое было запущено на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-159">This example gets information about a job and displays the results of a completed job that was run on the local computer.</span></span>

```powershell
$j = Start-Job -ScriptBlock { Get-WinEvent -Log System } -Credential Domain01\User01
$j | Select-Object -Property *
```

```Output
State         : Completed
HasMoreData   : True
StatusMessage :
Location      : localhost
Command       : Get-WinEvent -Log System
JobStateInfo  : Completed
Finished      : System.Threading.ManualResetEvent
InstanceId    : 27ce3fd9-40ed-488a-99e5-679cd91b9dd3
Id            : 18
Name          : Job18
ChildJobs     : {Job19}
PSBeginTime   : 8/8/2019 14:41:57
PSEndTime     : 8/8/2019 14:42:07
PSJobTypeName : BackgroundJob
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
Information   : {}
```

<span data-ttu-id="8d4a9-160">`Start-Job` использует параметр **ScriptBlock** для выполнения команды, указывающей `Get-WinEvent` на получение **системного** журнала.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-160">`Start-Job` uses the **ScriptBlock** parameter to run a command that specifies `Get-WinEvent` to get the **System** log.</span></span> <span data-ttu-id="8d4a9-161">Параметр **Credential** указывает учетную запись пользователя домена с разрешением на запуск задания на компьютере.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-161">The **Credential** parameter specifies a domain user account with permission to run the job on the computer.</span></span> <span data-ttu-id="8d4a9-162">Объект задания хранится в `$j` переменной.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-162">The job object is stored in the `$j` variable.</span></span>

<span data-ttu-id="8d4a9-163">Объект в `$j` переменной отправляется по конвейеру в `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="8d4a9-163">The object in the `$j` variable is sent down the pipeline to `Select-Object`.</span></span> <span data-ttu-id="8d4a9-164">Параметр **Property** задает звездочку ( `*` ) для вывода свойств объекта задания.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-164">The **Property** parameter specifies an asterisk (`*`) to display all the job object's properties.</span></span>

### <span data-ttu-id="8d4a9-165">Пример 5. Запуск скрипта как фонового задания</span><span class="sxs-lookup"><span data-stu-id="8d4a9-165">Example 5: Run a script as a background job</span></span>

<span data-ttu-id="8d4a9-166">В этом примере сценарий на локальном компьютере выполняется как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-166">In this example, a script on the local computer is run as a background job.</span></span>

```powershell
Start-Job -FilePath C:\Scripts\Sample.ps1
```

<span data-ttu-id="8d4a9-167">`Start-Job` использует параметр **FilePath** для указания файла скрипта, хранящегося на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-167">`Start-Job` uses the **FilePath** parameter to specify a script file that's stored on the local computer.</span></span>

### <span data-ttu-id="8d4a9-168">Пример 6. получение процесса с помощью фонового задания</span><span class="sxs-lookup"><span data-stu-id="8d4a9-168">Example 6: Get a process using a background job</span></span>

<span data-ttu-id="8d4a9-169">В этом примере для получения указанного процесса по имени используется фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-169">This example uses a background job to get a specified process by name.</span></span>

```powershell
Start-Job -Name PShellJob -ScriptBlock { Get-Process -Name PowerShell }
```

<span data-ttu-id="8d4a9-170">`Start-Job` использует параметр **Name** для указания понятного имени задания **пшеллжоб**.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-170">`Start-Job` uses the **Name** parameter to specify a friendly job name, **PShellJob**.</span></span> <span data-ttu-id="8d4a9-171">Параметр **ScriptBlock** указывает `Get-Process` на получение процессов с именем **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-171">The **ScriptBlock** parameter specifies `Get-Process` to get processes with the name **PowerShell**.</span></span>

### <span data-ttu-id="8d4a9-172">Пример 7. получение и сохранение данных с помощью фонового задания</span><span class="sxs-lookup"><span data-stu-id="8d4a9-172">Example 7: Collect and save data by using a background job</span></span>

<span data-ttu-id="8d4a9-173">В этом примере запускается задание, которое собирает большой объем данных о карте и сохраняет их в `.tif` файле.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-173">This example starts a job that collects a large amount of map data and then saves it in a `.tif` file.</span></span>

```powershell
Start-Job -Name GetMappingFiles -InitializationScript {Import-Module MapFunctions} -ScriptBlock {
   Get-Map -Name * | Set-Content -Path D:\Maps.tif }
```

<span data-ttu-id="8d4a9-174">`Start-Job` использует параметр **Name** для указания понятного имени задания **жетмаппингфилес**.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-174">`Start-Job` uses the **Name** parameter to specify a friendly job name, **GetMappingFiles**.</span></span> <span data-ttu-id="8d4a9-175">Параметр **инитиализатионскрипт** выполняет блок скрипта, который импортирует модуль **мапфунктионс** .</span><span class="sxs-lookup"><span data-stu-id="8d4a9-175">The **InitializationScript** parameter runs a script block that imports the **MapFunctions** module.</span></span> <span data-ttu-id="8d4a9-176">Параметр **ScriptBlock** выполняется `Get-Map` и `Set-Content` сохраняет данные в расположении, указанном параметром **path** .</span><span class="sxs-lookup"><span data-stu-id="8d4a9-176">The **ScriptBlock** parameter runs `Get-Map` and `Set-Content` saves the data in the location specified by the **Path** parameter.</span></span>

### <span data-ttu-id="8d4a9-177">Пример 8. передача входных данных в фоновое задание</span><span class="sxs-lookup"><span data-stu-id="8d4a9-177">Example 8: Pass input to a background job</span></span>

<span data-ttu-id="8d4a9-178">В этом примере `$input` Автоматическая переменная используется для обработки входного объекта.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-178">This example uses the `$input` automatic variable to process an input object.</span></span> <span data-ttu-id="8d4a9-179">Используйте `Receive-Job` для просмотра выходных данных задания.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-179">Use `Receive-Job` to view the job's output.</span></span>

```powershell
Start-Job -ScriptBlock { Get-Content $input } -InputObject "C:\Servers.txt"
Receive-Job -Name Job45 -Keep
```

```Output
Server01
Server02
Server03
Server04
```

<span data-ttu-id="8d4a9-180">`Start-Job` использует параметр **ScriptBlock** для выполнения `Get-Content` с `$input` автоматической переменной.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-180">`Start-Job` uses the **ScriptBlock** parameter to run `Get-Content` with the `$input` automatic variable.</span></span> <span data-ttu-id="8d4a9-181">`$input`Переменная получает объекты из параметра **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="8d4a9-181">The `$input` variable gets objects from the **InputObject** parameter.</span></span> <span data-ttu-id="8d4a9-182">`Receive-Job` использует параметр **Name** для указания задания и вывода результатов.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-182">`Receive-Job` uses the **Name** parameter to specify the job and outputs the results.</span></span> <span data-ttu-id="8d4a9-183">Параметр **сохранить** сохраняет выходные данные задания, чтобы их можно было снова просмотреть во время сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-183">The **Keep** parameter saves the job output so it can be viewed again during the PowerShell session.</span></span>

### <span data-ttu-id="8d4a9-184">Пример 9. Задание рабочего каталога для фонового задания</span><span class="sxs-lookup"><span data-stu-id="8d4a9-184">Example 9: Set the working directory for a background job</span></span>

<span data-ttu-id="8d4a9-185">**WorkingDirectory** позволяет указать альтернативный каталог для задания, из которого можно запускать скрипты или открывать файлы.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-185">The **WorkingDirectory** allows you to specify an alternate directory for a job from which you can run scripts or open files.</span></span> <span data-ttu-id="8d4a9-186">В этом примере фоновое задание указывает рабочий каталог, который отличается от текущего расположения каталога.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-186">In this example, the background job specifies a working directory that's different than the current directory location.</span></span>

```
PS C:\Test> Start-Job -WorkingDirectory C:\Test\Scripts { $PWD } | Receive-Job -AutoRemoveJob -Wait

Path
----
C:\Test\Scripts
```

<span data-ttu-id="8d4a9-187">Текущий рабочий каталог этого примера — `C:\Test` .</span><span class="sxs-lookup"><span data-stu-id="8d4a9-187">This example's current working directory is `C:\Test`.</span></span> <span data-ttu-id="8d4a9-188">`Start-Job` использует параметр **WorkingDirectory** для указания рабочего каталога задания.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-188">`Start-Job` uses the **WorkingDirectory** parameter to specify the job's working directory.</span></span> <span data-ttu-id="8d4a9-189">Параметр **ScriptBlock** используется `$PWD` для вывода рабочего каталога задания.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-189">The **ScriptBlock** parameter uses `$PWD` to display the job's working directory.</span></span> <span data-ttu-id="8d4a9-190">`Receive-Job` Отображает выходные данные фонового задания.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-190">`Receive-Job` displays the background job's output.</span></span>
<span data-ttu-id="8d4a9-191">**Ауторемовежоб** удаляет задание и **ждет** , пока не будут получены все результаты, заблокируя командную строку.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-191">**AutoRemoveJob** deletes the job and **Wait** suppresses the command prompt until all results are received.</span></span>

### <span data-ttu-id="8d4a9-192">Пример 10. Использование параметра ArgumentList для указания массива</span><span class="sxs-lookup"><span data-stu-id="8d4a9-192">Example 10: Use the ArgumentList parameter to specify an array</span></span>

<span data-ttu-id="8d4a9-193">В этом примере используется параметр **ArgumentList** для указания массива аргументов.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-193">This example uses the **ArgumentList** parameter to specify an array of arguments.</span></span> <span data-ttu-id="8d4a9-194">Массив представляет собой разделенный запятыми список имен процессов.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-194">The array is a comma-separated list of process names.</span></span>

```powershell
Start-Job -ScriptBlock { Get-Process -Name $args } -ArgumentList powershell, pwsh, notepad
```

```Output
Id     Name      PSJobTypeName   State       HasMoreData     Location     Command
--     ----      -------------   -----       -----------     --------     -------
1      Job1      BackgroundJob   Running     True            localhost    Get-Process -Name $args
```

<span data-ttu-id="8d4a9-195">`Start-Job`Командлет использует параметр **ScriptBlock** для выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-195">The `Start-Job` cmdlet uses the **ScriptBlock** parameter to run a command.</span></span> <span data-ttu-id="8d4a9-196">`Get-Process` Задает автоматическую переменную с помощью параметра **Name** `$args` .</span><span class="sxs-lookup"><span data-stu-id="8d4a9-196">`Get-Process` uses the **Name** parameter to specify the automatic variable `$args`.</span></span> <span data-ttu-id="8d4a9-197">Параметр **ArgumentList** передает массив имен процессов в `$args` .</span><span class="sxs-lookup"><span data-stu-id="8d4a9-197">The **ArgumentList** parameter passes the array of process names to `$args`.</span></span> <span data-ttu-id="8d4a9-198">Имена процессов PowerShell, pwsh и Notepad — это процессы, выполняемые на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-198">The process names powershell, pwsh, and notepad are processes running on the local computer.</span></span>

<span data-ttu-id="8d4a9-199">Чтобы просмотреть выходные данные задания, используйте `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-199">To view the job's output, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="8d4a9-200">Например, `Receive-Job -Id 1`.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-200">For example, `Receive-Job -Id 1`.</span></span>

### <span data-ttu-id="8d4a9-201">Пример 11. выполнение задания в Windows PowerShell 5,1</span><span class="sxs-lookup"><span data-stu-id="8d4a9-201">Example 11: Run job in a Windows PowerShell 5.1</span></span>

<span data-ttu-id="8d4a9-202">В этом примере для выполнения задания в сеансе Windows PowerShell 5,1 используется параметр **PSVersion** со значением **5,1** .</span><span class="sxs-lookup"><span data-stu-id="8d4a9-202">This example uses the **PSVersion** parameter with value **5.1** to run job in a Windows PowerShell 5.1 session.</span></span>

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Patch  PreReleaseLabel BuildLabel
-----  -----  -----  --------------- ----------
7      0      0      rc.1
```

```powershell
$job = Start-Job { $PSVersionTable.PSVersion } -PSVersion 5.1
Receive-Job $job
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      14393  3383
```

## <span data-ttu-id="8d4a9-203">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8d4a9-203">PARAMETERS</span></span>

### <span data-ttu-id="8d4a9-204">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="8d4a9-204">-ArgumentList</span></span>

<span data-ttu-id="8d4a9-205">Задает массив аргументов или значений параметров для скрипта, заданного параметром **FilePath** , или команды, указанной с помощью параметра **ScriptBlock** .</span><span class="sxs-lookup"><span data-stu-id="8d4a9-205">Specifies an array of arguments, or parameter values, for the script that is specified by the **FilePath** parameter or a command specified with the **ScriptBlock** parameter.</span></span>

<span data-ttu-id="8d4a9-206">Аргументы должны передаваться в **ArgumentList** как аргумент массива с одним измерением.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-206">Arguments must be passed to **ArgumentList** as single-dimension array argument.</span></span> <span data-ttu-id="8d4a9-207">Например, список с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-207">For example, a comma-separated list.</span></span> <span data-ttu-id="8d4a9-208">Дополнительные сведения о поведении **ArgumentList** см. в разделе [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="8d4a9-208">For more information about the behavior of **ArgumentList** , see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8d4a9-209">-Authentication</span><span class="sxs-lookup"><span data-stu-id="8d4a9-209">-Authentication</span></span>

<span data-ttu-id="8d4a9-210">Указывает механизм, используемый для проверки подлинности учетных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-210">Specifies the mechanism that is used to authenticate user credentials.</span></span>

<span data-ttu-id="8d4a9-211">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="8d4a9-211">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="8d4a9-212">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="8d4a9-212">Default</span></span>
- <span data-ttu-id="8d4a9-213">Базовый</span><span class="sxs-lookup"><span data-stu-id="8d4a9-213">Basic</span></span>
- <span data-ttu-id="8d4a9-214">CredSSP</span><span class="sxs-lookup"><span data-stu-id="8d4a9-214">Credssp</span></span>
- <span data-ttu-id="8d4a9-215">Digest (дайджест)</span><span class="sxs-lookup"><span data-stu-id="8d4a9-215">Digest</span></span>
- <span data-ttu-id="8d4a9-216">Kerberos</span><span class="sxs-lookup"><span data-stu-id="8d4a9-216">Kerberos</span></span>
- <span data-ttu-id="8d4a9-217">Согласование</span><span class="sxs-lookup"><span data-stu-id="8d4a9-217">Negotiate</span></span>
- <span data-ttu-id="8d4a9-218">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="8d4a9-218">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="8d4a9-219">Значение по умолчанию — Default.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-219">The default value is Default.</span></span>

<span data-ttu-id="8d4a9-220">Проверка подлинности CredSSP доступна только в Windows Vista, Windows Server 2008 и более поздних версиях операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-220">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="8d4a9-221">Дополнительные сведения о значениях этого параметра см. в разделе [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="8d4a9-221">For more information about the values of this parameter, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="8d4a9-222">Аутентификация CredSSP, в рамках которой учетные данные пользователя передаются на удаленный компьютер для проверки, предназначена для команд, требующих аутентификацию нескольких ресурсов, например для доступа к удаленной сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-222">Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="8d4a9-223">Этот механизм повышает риск безопасности удаленной операции.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-223">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="8d4a9-224">Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-224">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8d4a9-225">-Credential</span><span class="sxs-lookup"><span data-stu-id="8d4a9-225">-Credential</span></span>

<span data-ttu-id="8d4a9-226">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-226">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="8d4a9-227">Если параметр **Credential** не указан, команда использует учетные данные текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-227">If the **Credential** parameter isn't specified, the command uses the current user's credentials.</span></span>

<span data-ttu-id="8d4a9-228">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-228">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="8d4a9-229">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-229">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="8d4a9-230">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="8d4a9-230">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="8d4a9-231">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="8d4a9-231">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8d4a9-232">-DefinitionName</span><span class="sxs-lookup"><span data-stu-id="8d4a9-232">-DefinitionName</span></span>

<span data-ttu-id="8d4a9-233">Указывает имя определения задания, запускаемого этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-233">Specifies the definition name of the job that this cmdlet starts.</span></span> <span data-ttu-id="8d4a9-234">Используйте этот параметр для запуска заданий настраиваемых типов, имеющих имя определения, например запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-234">Use this parameter to start custom job types that have a definition name, such as scheduled jobs.</span></span>

<span data-ttu-id="8d4a9-235">При использовании `Start-Job` для запуска экземпляра запланированного задания задание запускается немедленно, независимо от триггеров задания или параметров задания.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-235">When you use `Start-Job` to start an instance of a scheduled job, the job starts immediately, regardless of job triggers or job options.</span></span> <span data-ttu-id="8d4a9-236">Результирующий экземпляр задания — это запланированное задание, но оно не сохраняется на диск, например запуск запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-236">The resulting job instance is a scheduled job, but it isn't saved to disk like triggered scheduled jobs.</span></span> <span data-ttu-id="8d4a9-237">Параметр **ArgumentList** аргумента нельзя использовать `Start-Job` для предоставления значений для параметров скриптов, выполняемых в запланированном задании.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-237">You can't use the **ArgumentList** parameter of `Start-Job` to provide values for parameters of scripts that run in a scheduled job.</span></span>

<span data-ttu-id="8d4a9-238">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-238">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="8d4a9-239">-DefinitionPath</span><span class="sxs-lookup"><span data-stu-id="8d4a9-239">-DefinitionPath</span></span>

<span data-ttu-id="8d4a9-240">Указывает путь определения задания, запускаемого этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-240">Specifies path of the definition for the job that this cmdlet starts.</span></span> <span data-ttu-id="8d4a9-241">Введите путь определения.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-241">Enter the definition path.</span></span> <span data-ttu-id="8d4a9-242">Объединение значений параметров **DefinitionPath** и **DefinitionName** является полным путем к определению задания.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-242">The concatenation of the values of the **DefinitionPath** and **DefinitionName** parameters is the fully qualified path of the job definition.</span></span> <span data-ttu-id="8d4a9-243">Используйте этот параметр для запуска заданий настраиваемых типов, которые имеют путь к определению, например запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-243">Use this parameter to start custom job types that have a definition path, such as scheduled jobs.</span></span>

<span data-ttu-id="8d4a9-244">Для запланированных заданий значение параметра **DefinitionPath** равно `$home\AppData\Local\Windows\PowerShell\ScheduledJob` .</span><span class="sxs-lookup"><span data-stu-id="8d4a9-244">For scheduled jobs, the value of the **DefinitionPath** parameter is `$home\AppData\Local\Windows\PowerShell\ScheduledJob`.</span></span>

<span data-ttu-id="8d4a9-245">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-245">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DefinitionName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8d4a9-246">-FilePath</span><span class="sxs-lookup"><span data-stu-id="8d4a9-246">-FilePath</span></span>

<span data-ttu-id="8d4a9-247">Указывает локальный скрипт, который `Start-Job` выполняется как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-247">Specifies a local script that `Start-Job` runs as a background job.</span></span> <span data-ttu-id="8d4a9-248">Введите путь и имя файла скрипта или используйте конвейер для отправки пути скрипта в `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="8d4a9-248">Enter the path and file name of the script or use the pipeline to send a script path to `Start-Job`.</span></span> <span data-ttu-id="8d4a9-249">Сценарий должен находиться на локальном компьютере или в папке, к которой может получить доступ локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-249">The script must be on the local computer or in a folder that the local computer can access.</span></span>

<span data-ttu-id="8d4a9-250">При использовании этого параметра PowerShell преобразует содержимое указанного файла скрипта в блок скрипта и запускает блок скрипта в качестве фонового задания.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-250">When you use this parameter, PowerShell converts the contents of the specified script file to a script block and runs the script block as a background job.</span></span>

```yaml
Type: System.String
Parameter Sets: FilePathComputerName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8d4a9-251">-Инитиализатионскрипт</span><span class="sxs-lookup"><span data-stu-id="8d4a9-251">-InitializationScript</span></span>

<span data-ttu-id="8d4a9-252">Указывает команды, выполняемые перед запуском задания.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-252">Specifies commands that run before the job starts.</span></span> <span data-ttu-id="8d4a9-253">Чтобы создать блок скрипта, заключите команды в фигурные скобки ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="8d4a9-253">To create a script block, enclose the commands in curly braces (`{}`).</span></span>

<span data-ttu-id="8d4a9-254">Используйте этот параметр для подготовки сеанса, в рамках которого выполняется задание.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-254">Use this parameter to prepare the session in which the job runs.</span></span> <span data-ttu-id="8d4a9-255">Например, его можно использовать для добавления в сеанс функций, оснасток и модулей.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-255">For example, you can use it to add functions, snap-ins, and modules to the session.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8d4a9-256">-InputObject</span><span class="sxs-lookup"><span data-stu-id="8d4a9-256">-InputObject</span></span>

<span data-ttu-id="8d4a9-257">Указывает входные данные команды.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-257">Specifies input to the command.</span></span> <span data-ttu-id="8d4a9-258">Введите переменную, содержащую объекты, либо введите команду или выражение для создания объектов.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-258">Enter a variable that contains the objects, or type a command or expression that generates the objects.</span></span>

<span data-ttu-id="8d4a9-259">В значении параметра **ScriptBlock** используйте `$input` автоматическую переменную для представления входных объектов.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-259">In the value of the **ScriptBlock** parameter, use the `$input` automatic variable to represent the input objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8d4a9-260">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="8d4a9-260">-LiteralPath</span></span>

<span data-ttu-id="8d4a9-261">Задает локальный скрипт, выполняемый этим командлетом в качестве фонового задания.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-261">Specifies a local script that this cmdlet runs as a background job.</span></span> <span data-ttu-id="8d4a9-262">Введите путь к скрипту на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-262">Enter the path of a script on the local computer.</span></span>

<span data-ttu-id="8d4a9-263">`Start-Job` использует значение параметра **LiteralPath** точно так же, как оно типизировано.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-263">`Start-Job` uses the value of the **LiteralPath** parameter exactly as it's typed.</span></span> <span data-ttu-id="8d4a9-264">Никакие символы не распознаются как подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-264">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="8d4a9-265">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-265">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="8d4a9-266">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-266">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralFilePathComputerName
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8d4a9-267">-Name</span><span class="sxs-lookup"><span data-stu-id="8d4a9-267">-Name</span></span>

<span data-ttu-id="8d4a9-268">Указывает понятное имя нового задания.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-268">Specifies a friendly name for the new job.</span></span> <span data-ttu-id="8d4a9-269">С помощью имени можно указать задание для других командлетов задания, например `Stop-Job` командлета.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-269">You can use the name to identify the job to other job cmdlets, such as the `Stop-Job` cmdlet.</span></span>

<span data-ttu-id="8d4a9-270">Понятное имя по умолчанию — `Job#` , где `#` — порядковый номер, увеличивающийся для каждого задания.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-270">The default friendly name is `Job#`, where `#` is an ordinal number that is incremented for each job.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8d4a9-271">-PSVersion</span><span class="sxs-lookup"><span data-stu-id="8d4a9-271">-PSVersion</span></span>

<span data-ttu-id="8d4a9-272">Указывает версию PowerShell для использования при выполнении задания.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-272">Specifies a version of PowerShell to use for running the job.</span></span>
<span data-ttu-id="8d4a9-273">Если значение **PSVersion** равно **5,1** , задание выполняется в сеансе Windows PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-273">When the value of **PSVersion** is **5.1** The job is run in a Windows PowerShell 5.1 session.</span></span>
<span data-ttu-id="8d4a9-274">Для любого другого значения задание выполняется с использованием текущей версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-274">For any other value, the job is run using the current version of PowerShell.</span></span>

<span data-ttu-id="8d4a9-275">Этот параметр был добавлен в PowerShell 7 и работает только в Windows.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-275">This parameter was added in PowerShell 7 and only works on Windows.</span></span>

```yaml
Type: System.Version
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8d4a9-276">-RunAs32</span><span class="sxs-lookup"><span data-stu-id="8d4a9-276">-RunAs32</span></span>

<span data-ttu-id="8d4a9-277">Начиная с PowerShell 7, параметр **RunAs32** не работает в 64-разрядной PowerShell ( `pwsh` ).</span><span class="sxs-lookup"><span data-stu-id="8d4a9-277">Beginning with PowerShell 7, the **RunAs32** parameter doesn't work on 64-bit PowerShell (`pwsh`).</span></span>
<span data-ttu-id="8d4a9-278">Если **RunAs32** указан в 64-разрядной версии PowerShell, `Start-Job` вызывается ошибка завершающего исключения.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-278">If **RunAs32** is specified in 64-bit PowerShell, `Start-Job` throws a terminating exception error.</span></span>
<span data-ttu-id="8d4a9-279">Чтобы запустить 32-разрядный процесс PowerShell ( `pwsh` ) с помощью **RunAs32** , необходимо установить 32-разрядную версию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-279">To start a 32-bit PowerShell (`pwsh`) process with **RunAs32** , you need to have the 32-bit PowerShell installed.</span></span>

<span data-ttu-id="8d4a9-280">В 32-разрядной версии PowerShell **RunAs32** принудительно запускает задание в 32-разрядном процессе даже в 64-разрядной операционной системе.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-280">In 32-bit PowerShell, **RunAs32** forces the job to run in a 32-bit process, even on a 64-bit operating system.</span></span>

<span data-ttu-id="8d4a9-281">В 64-разрядных версиях Windows 7 и Windows Server 2008 R2, если `Start-Job` команда содержит параметр **RunAs32** , нельзя использовать параметр **Credential** для указания учетных данных другого пользователя.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-281">On 64-bit versions of Windows 7 and Windows Server 2008 R2, when the `Start-Job` command includes the **RunAs32** parameter, you can't use the **Credential** parameter to specify the credentials of another user.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, FilePathComputerName, LiteralFilePathComputerName
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8d4a9-282">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="8d4a9-282">-ScriptBlock</span></span>

<span data-ttu-id="8d4a9-283">Указывает команды, которые нужно выполнить в фоновом задании.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-283">Specifies the commands to run in the background job.</span></span> <span data-ttu-id="8d4a9-284">Чтобы создать блок скрипта, заключите команды в фигурные скобки ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="8d4a9-284">To create a script block, enclose the commands in curly braces (`{}`).</span></span> <span data-ttu-id="8d4a9-285">Используйте `$input` автоматическую переменную для доступа к значению параметра **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="8d4a9-285">Use the `$input` automatic variable to access the value of the **InputObject** parameter.</span></span> <span data-ttu-id="8d4a9-286">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-286">This parameter is required.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ComputerName
Aliases: Command

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8d4a9-287">-Type</span><span class="sxs-lookup"><span data-stu-id="8d4a9-287">-Type</span></span>

<span data-ttu-id="8d4a9-288">Указывает пользовательский тип для заданий, запускаемых `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="8d4a9-288">Specifies the custom type for jobs started by `Start-Job`.</span></span> <span data-ttu-id="8d4a9-289">Введите имя настраиваемого типа задания, например PSScheduledJob для запланированных заданий или PSWorkflowJob для заданий рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-289">Enter a custom job type name, such as PSScheduledJob for scheduled jobs or PSWorkflowJob for workflows jobs.</span></span> <span data-ttu-id="8d4a9-290">Этот параметр не является допустимым для стандартных фоновых заданий.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-290">This parameter isn't valid for standard background jobs.</span></span>

<span data-ttu-id="8d4a9-291">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-291">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DefinitionName
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8d4a9-292">-WorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="8d4a9-292">-WorkingDirectory</span></span>

<span data-ttu-id="8d4a9-293">Указывает исходный рабочий каталог фонового задания.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-293">Specifies the initial working directory of the background job.</span></span> <span data-ttu-id="8d4a9-294">Если параметр не указан, задание выполняется из расположения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-294">If the parameter isn't specified, the job runs from the default location.</span></span> <span data-ttu-id="8d4a9-295">Расположение по умолчанию — это текущий рабочий каталог вызывающего объекта, запустившего задание.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-295">The default location is the current working directory of the caller that started the job.</span></span>

<span data-ttu-id="8d4a9-296">Этот параметр появился в PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-296">This parameter was introduced in PowerShell 7.</span></span>

```yaml
Type: System.String
Parameter Sets: All
Aliases:

Required: False
Position: Named
Default value: $HOME on Unix (macOS, Linux) and $HOME\Documents on Windows
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8d4a9-297">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="8d4a9-297">CommonParameters</span></span>

<span data-ttu-id="8d4a9-298">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-298">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8d4a9-299">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8d4a9-299">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8d4a9-300">Входные данные</span><span class="sxs-lookup"><span data-stu-id="8d4a9-300">INPUTS</span></span>

### <span data-ttu-id="8d4a9-301">System.String</span><span class="sxs-lookup"><span data-stu-id="8d4a9-301">System.String</span></span>

<span data-ttu-id="8d4a9-302">Конвейер можно использовать для отправки объекта со свойством **Name** в параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="8d4a9-302">You can use the pipeline to send an object with the **Name** property to the **Name** parameter.</span></span> <span data-ttu-id="8d4a9-303">Например, можно выполнить конвейер объекта **FileInfo** из `Get-ChildItem` в `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="8d4a9-303">For example, you can pipeline a **FileInfo** object from `Get-ChildItem` to `Start-Job`.</span></span>

## <span data-ttu-id="8d4a9-304">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="8d4a9-304">OUTPUTS</span></span>

### <span data-ttu-id="8d4a9-305">System. Management. Automation. Псремотингжоб</span><span class="sxs-lookup"><span data-stu-id="8d4a9-305">System.Management.Automation.PSRemotingJob</span></span>

<span data-ttu-id="8d4a9-306">`Start-Job` Возвращает объект **псремотингжоб** , представляющий запущенное задание.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-306">`Start-Job` returns a **PSRemotingJob** object that represents the job that it started.</span></span>

## <span data-ttu-id="8d4a9-307">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="8d4a9-307">NOTES</span></span>

<span data-ttu-id="8d4a9-308">Для запуска в фоновом режиме `Start-Job` выполняется в собственном сеансе в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-308">To run in the background, `Start-Job` runs in its own session in the current session.</span></span> <span data-ttu-id="8d4a9-309">При использовании `Invoke-Command` командлета для выполнения `Start-Job` команды в сеансе на удаленном компьютере `Start-Job` выполняется в сеансе удаленного сеанса.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-309">When you use the `Invoke-Command` cmdlet to run a `Start-Job` command in a session on a remote computer, `Start-Job` runs in a session in the remote session.</span></span>

## <span data-ttu-id="8d4a9-310">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="8d4a9-310">RELATED LINKS</span></span>

[<span data-ttu-id="8d4a9-311">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="8d4a9-311">about_Arrays</span></span>](./about/about_arrays.md)

[<span data-ttu-id="8d4a9-312">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="8d4a9-312">about_Automatic_Variables</span></span>](./about/about_automatic_variables.md)

[<span data-ttu-id="8d4a9-313">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="8d4a9-313">about_Jobs</span></span>](./About/about_Jobs.md)

[<span data-ttu-id="8d4a9-314">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="8d4a9-314">about_Job_Details</span></span>](./About/about_Job_Details.md)

[<span data-ttu-id="8d4a9-315">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="8d4a9-315">about_Remote_Jobs</span></span>](./About/about_Remote_Jobs.md)

[<span data-ttu-id="8d4a9-316">Get-Job.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-316">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="8d4a9-317">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="8d4a9-317">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="8d4a9-318">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-318">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="8d4a9-319">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="8d4a9-319">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="8d4a9-320">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="8d4a9-320">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="8d4a9-321">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="8d4a9-321">Wait-Job</span></span>](Wait-Job.md)
