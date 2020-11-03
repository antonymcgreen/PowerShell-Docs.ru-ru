---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/start-job?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Job
ms.openlocfilehash: 69cebe735e413b226bd40539df075bf3a49bce95
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229246"
---
# <span data-ttu-id="487cf-103">Start-Job</span><span class="sxs-lookup"><span data-stu-id="487cf-103">Start-Job</span></span>

## <span data-ttu-id="487cf-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="487cf-104">SYNOPSIS</span></span>
<span data-ttu-id="487cf-105">Запускает фоновое задание PowerShell.</span><span class="sxs-lookup"><span data-stu-id="487cf-105">Starts a PowerShell background job.</span></span>

## <span data-ttu-id="487cf-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="487cf-106">SYNTAX</span></span>

### <span data-ttu-id="487cf-107">ComputerName (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="487cf-107">ComputerName (Default)</span></span>

```
Start-Job [-Name <String>] [-ScriptBlock] <ScriptBlock> [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>] [-RunAs32]
 [-PSVersion <Version>] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="487cf-108">DefinitionName</span><span class="sxs-lookup"><span data-stu-id="487cf-108">DefinitionName</span></span>

```
Start-Job [-DefinitionName] <String> [[-DefinitionPath] <String>] [[-Type] <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="487cf-109">литералфилепаскомпутернаме</span><span class="sxs-lookup"><span data-stu-id="487cf-109">LiteralFilePathComputerName</span></span>

```
Start-Job [-Name <String>] [-Credential <PSCredential>] -LiteralPath <String>
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>] [-RunAs32]
 [-PSVersion <Version>] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="487cf-110">филепаскомпутернаме</span><span class="sxs-lookup"><span data-stu-id="487cf-110">FilePathComputerName</span></span>

```
Start-Job [-Name <String>] [-Credential <PSCredential>] [-FilePath] <String>
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>] [-RunAs32]
 [-PSVersion <Version>] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

## <span data-ttu-id="487cf-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="487cf-111">DESCRIPTION</span></span>

<span data-ttu-id="487cf-112">`Start-Job`Командлет запускает фоновое задание PowerShell на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="487cf-112">The `Start-Job` cmdlet starts a PowerShell background job on the local computer.</span></span>

<span data-ttu-id="487cf-113">Фоновое задание PowerShell выполняет команду без взаимодействия с текущим сеансом.</span><span class="sxs-lookup"><span data-stu-id="487cf-113">A PowerShell background job runs a command without interacting with the current session.</span></span> <span data-ttu-id="487cf-114">При запуске фонового задания объект задания возвращается немедленно, даже если для завершения задания требуется дополнительное время.</span><span class="sxs-lookup"><span data-stu-id="487cf-114">When you start a background job, a job object returns immediately, even if the job takes an extended time to finish.</span></span> <span data-ttu-id="487cf-115">Пока задание выполняется, можно продолжать работу с данным сеансом.</span><span class="sxs-lookup"><span data-stu-id="487cf-115">You can continue to work in the session without interruption while the job runs.</span></span>

<span data-ttu-id="487cf-116">Объект задания содержит полезные сведения о задании, но не содержит результатов задания.</span><span class="sxs-lookup"><span data-stu-id="487cf-116">The job object contains useful information about the job, but it doesn't contain the job results.</span></span>
<span data-ttu-id="487cf-117">По завершении задания используйте `Receive-Job` командлет для получения результатов задания.</span><span class="sxs-lookup"><span data-stu-id="487cf-117">When the job finishes, use the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="487cf-118">Дополнительные сведения о фоновых заданиях см. в разделе [about_Jobs](./About/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="487cf-118">For more information about background jobs, see [about_Jobs](./About/about_Jobs.md).</span></span>

<span data-ttu-id="487cf-119">Чтобы запустить фоновое задание на удаленном компьютере, используйте параметр **AsJob** , доступный во многих командлетах, или используйте `Invoke-Command` командлет для выполнения `Start-Job` команды на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="487cf-119">To run a background job on a remote computer, use the **AsJob** parameter that is available on many cmdlets, or use the `Invoke-Command` cmdlet to run a `Start-Job` command on the remote computer.</span></span> <span data-ttu-id="487cf-120">Дополнительные сведения см. в разделе [about_Remote_Jobs](./About/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="487cf-120">For more information, see [about_Remote_Jobs](./About/about_Remote_Jobs.md).</span></span>

<span data-ttu-id="487cf-121">Начиная с версии PowerShell 3,0, `Start-Job` можно запускать экземпляры пользовательских типов заданий, например запланированные задания.</span><span class="sxs-lookup"><span data-stu-id="487cf-121">Starting in PowerShell 3.0, `Start-Job` can start instances of custom job types, such as scheduled jobs.</span></span> <span data-ttu-id="487cf-122">Сведения об использовании `Start-Job` для запуска заданий с пользовательскими типами см. в справочных документах по функциям типа задания.</span><span class="sxs-lookup"><span data-stu-id="487cf-122">For information about how to use `Start-Job` to start jobs with custom types, see the help documents for the job type feature.</span></span>

<span data-ttu-id="487cf-123">Начиная с PowerShell 6,0 можно запускать задания с помощью `&` фонового оператора амперсанд ().</span><span class="sxs-lookup"><span data-stu-id="487cf-123">Beginning in PowerShell 6.0, you can start jobs using the ampersand (`&`) background operator.</span></span> <span data-ttu-id="487cf-124">Функции фонового оператора похожи на `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="487cf-124">The functionality of the background operator is similar to `Start-Job`.</span></span> <span data-ttu-id="487cf-125">Оба метода запуска задания создают объект задания **псремотингжоб** .</span><span class="sxs-lookup"><span data-stu-id="487cf-125">Both methods to start a job create a **PSRemotingJob** job object.</span></span> <span data-ttu-id="487cf-126">Дополнительные сведения об использовании амперсанда ( `&` ) см. в разделе [about_Operators](./about/about_operators.md#background-operator-).</span><span class="sxs-lookup"><span data-stu-id="487cf-126">For more information about using the ampersand (`&`), see [about_Operators](./about/about_operators.md#background-operator-).</span></span>

<span data-ttu-id="487cf-127">Рабочий каталог по умолчанию для заданий является жестко закодированным.</span><span class="sxs-lookup"><span data-stu-id="487cf-127">The default working directory for jobs is hardcoded.</span></span> <span data-ttu-id="487cf-128">По умолчанию Windows имеет значение `$HOME\Documents` , а в Linux или macOS значение по умолчанию — `$HOME` .</span><span class="sxs-lookup"><span data-stu-id="487cf-128">The Windows default is `$HOME\Documents` and on Linux or macOS the default is `$HOME`.</span></span> <span data-ttu-id="487cf-129">Код скрипта, выполняемый в фоновом задании, должен управлять рабочим каталогом по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="487cf-129">The script code running in the background job needs to manage the working directory as needed.</span></span>

> [!NOTE]
> <span data-ttu-id="487cf-130">Создание внепроцессного фонового задания с помощью `Start-Job` не поддерживается в сценарии, в котором PowerShell размещается в других приложениях, например в функциях Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="487cf-130">Creating an out-of-process background job with `Start-Job` is not supported in the scenario where PowerShell is being hosted in other applications, such as the PowerShell Azure Functions.</span></span>
>
> <span data-ttu-id="487cf-131">Это связано с тем, что `Start-Job` зависит от `pwsh` исполняемого файла, который должен быть доступен `$PSHOME` для запуска незавершенного фонового задания, но когда приложение размещает PowerShell, оно напрямую использует пакеты SDK NuGet для PowerShell и не будет `pwsh` доставлено.</span><span class="sxs-lookup"><span data-stu-id="487cf-131">This is by design because `Start-Job` depends on the `pwsh` executable to be available under `$PSHOME` to start an out-of-process background job, but when an application is hosting PowerShell, it's directly using the PowerShell NuGet SDK packages and won't have `pwsh` shipped along.</span></span>
>
> <span data-ttu-id="487cf-132">Подстановка в этом сценарии осуществляется `Start-ThreadJob` из модуля **[среаджоб](https://www.powershellgallery.com/packages/ThreadJob)**.</span><span class="sxs-lookup"><span data-stu-id="487cf-132">The substitute in that scenario is `Start-ThreadJob` from the module **[ThreadJob](https://www.powershellgallery.com/packages/ThreadJob)**.</span></span>

## <span data-ttu-id="487cf-133">Примеры</span><span class="sxs-lookup"><span data-stu-id="487cf-133">EXAMPLES</span></span>

### <span data-ttu-id="487cf-134">Пример 1. Запуск фонового задания</span><span class="sxs-lookup"><span data-stu-id="487cf-134">Example 1: Start a background job</span></span>

<span data-ttu-id="487cf-135">В этом примере запускается фоновое задание, выполняемое на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="487cf-135">This example starts a background job that runs on the local computer.</span></span>

```powershell
Start-Job -ScriptBlock { Get-Process -Name pwsh }
```

```Output
Id  Name   PSJobTypeName   State     HasMoreData   Location    Command
--  ----   -------------   -----     -----------   --------    -------
1   Job1   BackgroundJob   Running   True          localhost   Get-Process -Name pwsh
```

<span data-ttu-id="487cf-136">`Start-Job` использует параметр **ScriptBlock** для выполнения в `Get-Process` качестве фонового задания.</span><span class="sxs-lookup"><span data-stu-id="487cf-136">`Start-Job` uses the **ScriptBlock** parameter to run `Get-Process` as a background job.</span></span> <span data-ttu-id="487cf-137">Параметр **Name** указывает на поиск процессов PowerShell `pwsh` .</span><span class="sxs-lookup"><span data-stu-id="487cf-137">The **Name** parameter specifies to find PowerShell processes, `pwsh`.</span></span> <span data-ttu-id="487cf-138">Отображаются сведения о задании, и PowerShell возвращается в командную строку, пока задание выполняется в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="487cf-138">The job information is displayed and PowerShell returns to a prompt while the job runs in the background.</span></span>

<span data-ttu-id="487cf-139">Чтобы просмотреть выходные данные задания, используйте `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="487cf-139">To view the job's output, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="487cf-140">Например, `Receive-Job -Id 1`.</span><span class="sxs-lookup"><span data-stu-id="487cf-140">For example, `Receive-Job -Id 1`.</span></span>

### <span data-ttu-id="487cf-141">Пример 2. Использование оператора Background для запуска фонового задания</span><span class="sxs-lookup"><span data-stu-id="487cf-141">Example 2: Use the background operator to start a background job</span></span>

<span data-ttu-id="487cf-142">В этом примере оператор амперсанд ( `&` ) используется для запуска фонового задания на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="487cf-142">This example uses the ampersand (`&`) background operator to start a background job on the local computer.</span></span> <span data-ttu-id="487cf-143">Задание получает тот же результат, что и `Start-Job` в примере 1.</span><span class="sxs-lookup"><span data-stu-id="487cf-143">The job gets the same result as `Start-Job` in Example 1.</span></span>

```powershell
Get-Process -Name pwsh &
```

```Output
Id    Name   PSJobTypeName   State       HasMoreData     Location      Command
--    ----   -------------   -----       -----------     --------      -------
5     Job5   BackgroundJob   Running     True            localhost     Microsoft.PowerShell.Man...
```

<span data-ttu-id="487cf-144">`Get-Process` использует параметр **Name** для указания процессов PowerShell `pwsh` .</span><span class="sxs-lookup"><span data-stu-id="487cf-144">`Get-Process` uses the **Name** parameter to specify PowerShell processes, `pwsh`.</span></span> <span data-ttu-id="487cf-145">Амперсанд ( `&` ) запускает команду в качестве фонового задания.</span><span class="sxs-lookup"><span data-stu-id="487cf-145">The ampersand (`&`) runs the command as a background job.</span></span> <span data-ttu-id="487cf-146">Отображаются сведения о задании, и PowerShell возвращается в командную строку, пока задание выполняется в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="487cf-146">The job information is displayed and PowerShell returns to a prompt while the job runs in the background.</span></span>

<span data-ttu-id="487cf-147">Чтобы просмотреть выходные данные задания, используйте `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="487cf-147">To view the job's output, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="487cf-148">Например, `Receive-Job -Id 5`.</span><span class="sxs-lookup"><span data-stu-id="487cf-148">For example, `Receive-Job -Id 5`.</span></span>

### <span data-ttu-id="487cf-149">Пример 3. Запуск задания с помощью Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="487cf-149">Example 3: Start a job using Invoke-Command</span></span>

<span data-ttu-id="487cf-150">В этом примере выполняется задание на нескольких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="487cf-150">This example runs a job on multiple computers.</span></span> <span data-ttu-id="487cf-151">Задание хранится в переменной и выполняется с помощью имени переменной в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="487cf-151">The job is stored in a variable and is executed by using the variable name on the PowerShell command line.</span></span>

```powershell
$jobWRM = Invoke-Command -ComputerName (Get-Content -Path C:\Servers.txt) -ScriptBlock {
   Get-Service -Name WinRM } -JobName WinRM -ThrottleLimit 16 -AsJob
```

<span data-ttu-id="487cf-152">Задание, которое использует, `Invoke-Command` создается и сохраняется в `$jobWRM` переменной.</span><span class="sxs-lookup"><span data-stu-id="487cf-152">A job that uses `Invoke-Command` is created and stored in the `$jobWRM` variable.</span></span> <span data-ttu-id="487cf-153">`Invoke-Command` использует параметр **ComputerName** для указания компьютеров, на которых выполняется задание.</span><span class="sxs-lookup"><span data-stu-id="487cf-153">`Invoke-Command` uses the **ComputerName** parameter to specify the computers where the job runs.</span></span> <span data-ttu-id="487cf-154">`Get-Content` Возвращает имена серверов из `C:\Servers.txt` файла.</span><span class="sxs-lookup"><span data-stu-id="487cf-154">`Get-Content` gets the server names from the `C:\Servers.txt` file.</span></span>

<span data-ttu-id="487cf-155">Параметр **ScriptBlock** указывает команду, которая `Get-Service` Получает службу **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="487cf-155">The **ScriptBlock** parameter specifies a command that `Get-Service` gets the **WinRM** service.</span></span> <span data-ttu-id="487cf-156">Параметр **JobName** указывает понятное имя для задания, **WinRM**.</span><span class="sxs-lookup"><span data-stu-id="487cf-156">The **JobName** parameter specifies a friendly name for the job, **WinRM**.</span></span> <span data-ttu-id="487cf-157">Параметр **ThrottleLimit** ограничивает количество одновременных команд до 16.</span><span class="sxs-lookup"><span data-stu-id="487cf-157">The **ThrottleLimit** parameter limits the number of concurrent commands to 16.</span></span> <span data-ttu-id="487cf-158">Параметр **AsJob** запускает фоновое задание, которое выполняет команду на серверах.</span><span class="sxs-lookup"><span data-stu-id="487cf-158">The **AsJob** parameter starts a background job that runs the command on the servers.</span></span>

### <span data-ttu-id="487cf-159">Пример 4. Получение сведений о задании</span><span class="sxs-lookup"><span data-stu-id="487cf-159">Example 4: Get job information</span></span>

<span data-ttu-id="487cf-160">Этот пример получает сведения о задании и отображает результаты завершенного задания, которое было запущено на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="487cf-160">This example gets information about a job and displays the results of a completed job that was run on the local computer.</span></span>

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

<span data-ttu-id="487cf-161">`Start-Job` использует параметр **ScriptBlock** для выполнения команды, указывающей `Get-WinEvent` на получение **системного** журнала.</span><span class="sxs-lookup"><span data-stu-id="487cf-161">`Start-Job` uses the **ScriptBlock** parameter to run a command that specifies `Get-WinEvent` to get the **System** log.</span></span> <span data-ttu-id="487cf-162">Параметр **Credential** указывает учетную запись пользователя домена с разрешением на запуск задания на компьютере.</span><span class="sxs-lookup"><span data-stu-id="487cf-162">The **Credential** parameter specifies a domain user account with permission to run the job on the computer.</span></span> <span data-ttu-id="487cf-163">Объект задания хранится в `$j` переменной.</span><span class="sxs-lookup"><span data-stu-id="487cf-163">The job object is stored in the `$j` variable.</span></span>

<span data-ttu-id="487cf-164">Объект в `$j` переменной отправляется по конвейеру в `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="487cf-164">The object in the `$j` variable is sent down the pipeline to `Select-Object`.</span></span> <span data-ttu-id="487cf-165">Параметр **Property** задает звездочку ( `*` ) для вывода свойств объекта задания.</span><span class="sxs-lookup"><span data-stu-id="487cf-165">The **Property** parameter specifies an asterisk (`*`) to display all the job object's properties.</span></span>

### <span data-ttu-id="487cf-166">Пример 5. Запуск скрипта как фонового задания</span><span class="sxs-lookup"><span data-stu-id="487cf-166">Example 5: Run a script as a background job</span></span>

<span data-ttu-id="487cf-167">В этом примере сценарий на локальном компьютере выполняется как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="487cf-167">In this example, a script on the local computer is run as a background job.</span></span>

```powershell
Start-Job -FilePath C:\Scripts\Sample.ps1
```

<span data-ttu-id="487cf-168">`Start-Job` использует параметр **FilePath** для указания файла скрипта, хранящегося на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="487cf-168">`Start-Job` uses the **FilePath** parameter to specify a script file that's stored on the local computer.</span></span>

### <span data-ttu-id="487cf-169">Пример 6. получение процесса с помощью фонового задания</span><span class="sxs-lookup"><span data-stu-id="487cf-169">Example 6: Get a process using a background job</span></span>

<span data-ttu-id="487cf-170">В этом примере для получения указанного процесса по имени используется фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="487cf-170">This example uses a background job to get a specified process by name.</span></span>

```powershell
Start-Job -Name PShellJob -ScriptBlock { Get-Process -Name PowerShell }
```

<span data-ttu-id="487cf-171">`Start-Job` использует параметр **Name** для указания понятного имени задания **пшеллжоб**.</span><span class="sxs-lookup"><span data-stu-id="487cf-171">`Start-Job` uses the **Name** parameter to specify a friendly job name, **PShellJob**.</span></span> <span data-ttu-id="487cf-172">Параметр **ScriptBlock** указывает `Get-Process` на получение процессов с именем **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="487cf-172">The **ScriptBlock** parameter specifies `Get-Process` to get processes with the name **PowerShell**.</span></span>

### <span data-ttu-id="487cf-173">Пример 7. получение и сохранение данных с помощью фонового задания</span><span class="sxs-lookup"><span data-stu-id="487cf-173">Example 7: Collect and save data by using a background job</span></span>

<span data-ttu-id="487cf-174">В этом примере запускается задание, которое собирает большой объем данных о карте и сохраняет их в `.tif` файле.</span><span class="sxs-lookup"><span data-stu-id="487cf-174">This example starts a job that collects a large amount of map data and then saves it in a `.tif` file.</span></span>

```powershell
Start-Job -Name GetMappingFiles -InitializationScript {Import-Module MapFunctions} -ScriptBlock {
   Get-Map -Name * | Set-Content -Path D:\Maps.tif } -RunAs32
```

<span data-ttu-id="487cf-175">`Start-Job` использует параметр **Name** для указания понятного имени задания **жетмаппингфилес**.</span><span class="sxs-lookup"><span data-stu-id="487cf-175">`Start-Job` uses the **Name** parameter to specify a friendly job name, **GetMappingFiles**.</span></span> <span data-ttu-id="487cf-176">Параметр **инитиализатионскрипт** выполняет блок скрипта, который импортирует модуль **мапфунктионс** .</span><span class="sxs-lookup"><span data-stu-id="487cf-176">The **InitializationScript** parameter runs a script block that imports the **MapFunctions** module.</span></span> <span data-ttu-id="487cf-177">Параметр **ScriptBlock** выполняется `Get-Map` и `Set-Content` сохраняет данные в расположении, указанном параметром **path** .</span><span class="sxs-lookup"><span data-stu-id="487cf-177">The **ScriptBlock** parameter runs `Get-Map` and `Set-Content` saves the data in the location specified by the **Path** parameter.</span></span> <span data-ttu-id="487cf-178">Параметр **RunAs32** запускает процесс как 32-разрядный, даже в 64-разрядной операционной системе.</span><span class="sxs-lookup"><span data-stu-id="487cf-178">The **RunAs32** parameter runs the process as 32-bit, even on a 64-bit operating system.</span></span>

### <span data-ttu-id="487cf-179">Пример 8. передача входных данных в фоновое задание</span><span class="sxs-lookup"><span data-stu-id="487cf-179">Example 8: Pass input to a background job</span></span>

<span data-ttu-id="487cf-180">В этом примере `$input` Автоматическая переменная используется для обработки входного объекта.</span><span class="sxs-lookup"><span data-stu-id="487cf-180">This example uses the `$input` automatic variable to process an input object.</span></span> <span data-ttu-id="487cf-181">Используйте `Receive-Job` для просмотра выходных данных задания.</span><span class="sxs-lookup"><span data-stu-id="487cf-181">Use `Receive-Job` to view the job's output.</span></span>

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

<span data-ttu-id="487cf-182">`Start-Job` использует параметр **ScriptBlock** для выполнения `Get-Content` с `$input` автоматической переменной.</span><span class="sxs-lookup"><span data-stu-id="487cf-182">`Start-Job` uses the **ScriptBlock** parameter to run `Get-Content` with the `$input` automatic variable.</span></span> <span data-ttu-id="487cf-183">`$input`Переменная получает объекты из параметра **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="487cf-183">The `$input` variable gets objects from the **InputObject** parameter.</span></span> <span data-ttu-id="487cf-184">`Receive-Job` использует параметр **Name** для указания задания и вывода результатов.</span><span class="sxs-lookup"><span data-stu-id="487cf-184">`Receive-Job` uses the **Name** parameter to specify the job and outputs the results.</span></span> <span data-ttu-id="487cf-185">Параметр **сохранить** сохраняет выходные данные задания, чтобы их можно было снова просмотреть во время сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="487cf-185">The **Keep** parameter saves the job output so it can be viewed again during the PowerShell session.</span></span>

### <span data-ttu-id="487cf-186">Пример 9. Использование параметра ArgumentList для указания массива</span><span class="sxs-lookup"><span data-stu-id="487cf-186">Example 9: Use the ArgumentList parameter to specify an array</span></span>

<span data-ttu-id="487cf-187">В этом примере используется параметр **ArgumentList** для указания массива аргументов.</span><span class="sxs-lookup"><span data-stu-id="487cf-187">This example uses the **ArgumentList** parameter to specify an array of arguments.</span></span> <span data-ttu-id="487cf-188">Массив представляет собой разделенный запятыми список имен процессов.</span><span class="sxs-lookup"><span data-stu-id="487cf-188">The array is a comma-separated list of process names.</span></span>

```powershell
Start-Job -ScriptBlock { Get-Process -Name $args } -ArgumentList powershell, pwsh, notepad
```

```Output
Id     Name      PSJobTypeName   State       HasMoreData     Location     Command
--     ----      -------------   -----       -----------     --------     -------
1      Job1      BackgroundJob   Running     True            localhost    Get-Process -Name $args
```

<span data-ttu-id="487cf-189">`Start-Job`Командлет использует параметр **ScriptBlock** для выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="487cf-189">The `Start-Job` cmdlet uses the **ScriptBlock** parameter to run a command.</span></span> <span data-ttu-id="487cf-190">`Get-Process` Задает автоматическую переменную с помощью параметра **Name** `$args` .</span><span class="sxs-lookup"><span data-stu-id="487cf-190">`Get-Process` uses the **Name** parameter to specify the automatic variable `$args`.</span></span> <span data-ttu-id="487cf-191">Параметр **ArgumentList** передает массив имен процессов в `$args` .</span><span class="sxs-lookup"><span data-stu-id="487cf-191">The **ArgumentList** parameter passes the array of process names to `$args`.</span></span> <span data-ttu-id="487cf-192">Имена процессов PowerShell, pwsh и Notepad — это процессы, выполняемые на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="487cf-192">The process names powershell, pwsh, and notepad are processes running on the local computer.</span></span>

<span data-ttu-id="487cf-193">Чтобы просмотреть выходные данные задания, используйте `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="487cf-193">To view the job's output, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="487cf-194">Например, `Receive-Job -Id 1`.</span><span class="sxs-lookup"><span data-stu-id="487cf-194">For example, `Receive-Job -Id 1`.</span></span>

## <span data-ttu-id="487cf-195">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="487cf-195">PARAMETERS</span></span>

### <span data-ttu-id="487cf-196">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="487cf-196">-ArgumentList</span></span>

<span data-ttu-id="487cf-197">Задает массив аргументов или значений параметров для скрипта, заданного параметром **FilePath** , или команды, указанной с помощью параметра **ScriptBlock** .</span><span class="sxs-lookup"><span data-stu-id="487cf-197">Specifies an array of arguments, or parameter values, for the script that is specified by the **FilePath** parameter or a command specified with the **ScriptBlock** parameter.</span></span>

<span data-ttu-id="487cf-198">Аргументы должны передаваться в **ArgumentList** как аргумент массива с одним измерением.</span><span class="sxs-lookup"><span data-stu-id="487cf-198">Arguments must be passed to **ArgumentList** as single-dimension array argument.</span></span> <span data-ttu-id="487cf-199">Например, список с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="487cf-199">For example, a comma-separated list.</span></span> <span data-ttu-id="487cf-200">Дополнительные сведения о поведении **ArgumentList** см. в разделе [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="487cf-200">For more information about the behavior of **ArgumentList** , see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

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

### <span data-ttu-id="487cf-201">-Authentication</span><span class="sxs-lookup"><span data-stu-id="487cf-201">-Authentication</span></span>

<span data-ttu-id="487cf-202">Указывает механизм, используемый для проверки подлинности учетных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="487cf-202">Specifies the mechanism that is used to authenticate user credentials.</span></span>

<span data-ttu-id="487cf-203">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="487cf-203">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="487cf-204">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="487cf-204">Default</span></span>
- <span data-ttu-id="487cf-205">Базовый</span><span class="sxs-lookup"><span data-stu-id="487cf-205">Basic</span></span>
- <span data-ttu-id="487cf-206">CredSSP</span><span class="sxs-lookup"><span data-stu-id="487cf-206">Credssp</span></span>
- <span data-ttu-id="487cf-207">Digest (дайджест)</span><span class="sxs-lookup"><span data-stu-id="487cf-207">Digest</span></span>
- <span data-ttu-id="487cf-208">Kerberos</span><span class="sxs-lookup"><span data-stu-id="487cf-208">Kerberos</span></span>
- <span data-ttu-id="487cf-209">Согласование</span><span class="sxs-lookup"><span data-stu-id="487cf-209">Negotiate</span></span>
- <span data-ttu-id="487cf-210">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="487cf-210">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="487cf-211">Значение по умолчанию — Default.</span><span class="sxs-lookup"><span data-stu-id="487cf-211">The default value is Default.</span></span>

<span data-ttu-id="487cf-212">Проверка подлинности CredSSP доступна только в Windows Vista, Windows Server 2008 и более поздних версиях операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="487cf-212">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="487cf-213">Дополнительные сведения о значениях этого параметра см. в разделе [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="487cf-213">For more information about the values of this parameter, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="487cf-214">Аутентификация CredSSP, в рамках которой учетные данные пользователя передаются на удаленный компьютер для проверки, предназначена для команд, требующих аутентификацию нескольких ресурсов, например для доступа к удаленной сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="487cf-214">Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="487cf-215">Этот механизм повышает риск безопасности удаленной операции.</span><span class="sxs-lookup"><span data-stu-id="487cf-215">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="487cf-216">Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="487cf-216">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

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

### <span data-ttu-id="487cf-217">-Credential</span><span class="sxs-lookup"><span data-stu-id="487cf-217">-Credential</span></span>

<span data-ttu-id="487cf-218">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="487cf-218">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="487cf-219">Если параметр **Credential** не указан, команда использует учетные данные текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="487cf-219">If the **Credential** parameter isn't specified, the command uses the current user's credentials.</span></span>

<span data-ttu-id="487cf-220">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="487cf-220">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="487cf-221">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="487cf-221">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="487cf-222">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="487cf-222">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="487cf-223">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="487cf-223">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="487cf-224">-DefinitionName</span><span class="sxs-lookup"><span data-stu-id="487cf-224">-DefinitionName</span></span>

<span data-ttu-id="487cf-225">Указывает имя определения задания, запускаемого этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="487cf-225">Specifies the definition name of the job that this cmdlet starts.</span></span> <span data-ttu-id="487cf-226">Используйте этот параметр для запуска заданий настраиваемых типов, имеющих имя определения, например запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="487cf-226">Use this parameter to start custom job types that have a definition name, such as scheduled jobs.</span></span>

<span data-ttu-id="487cf-227">При использовании `Start-Job` для запуска экземпляра запланированного задания задание запускается немедленно, независимо от триггеров задания или параметров задания.</span><span class="sxs-lookup"><span data-stu-id="487cf-227">When you use `Start-Job` to start an instance of a scheduled job, the job starts immediately, regardless of job triggers or job options.</span></span> <span data-ttu-id="487cf-228">Результирующий экземпляр задания — это запланированное задание, но оно не сохраняется на диск, например запуск запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="487cf-228">The resulting job instance is a scheduled job, but it isn't saved to disk like triggered scheduled jobs.</span></span> <span data-ttu-id="487cf-229">Параметр **ArgumentList** аргумента нельзя использовать `Start-Job` для предоставления значений для параметров скриптов, выполняемых в запланированном задании.</span><span class="sxs-lookup"><span data-stu-id="487cf-229">You can't use the **ArgumentList** parameter of `Start-Job` to provide values for parameters of scripts that run in a scheduled job.</span></span>

<span data-ttu-id="487cf-230">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="487cf-230">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="487cf-231">-DefinitionPath</span><span class="sxs-lookup"><span data-stu-id="487cf-231">-DefinitionPath</span></span>

<span data-ttu-id="487cf-232">Указывает путь определения задания, запускаемого этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="487cf-232">Specifies path of the definition for the job that this cmdlet starts.</span></span> <span data-ttu-id="487cf-233">Введите путь определения.</span><span class="sxs-lookup"><span data-stu-id="487cf-233">Enter the definition path.</span></span> <span data-ttu-id="487cf-234">Объединение значений параметров **DefinitionPath** и **DefinitionName** является полным путем к определению задания.</span><span class="sxs-lookup"><span data-stu-id="487cf-234">The concatenation of the values of the **DefinitionPath** and **DefinitionName** parameters is the fully qualified path of the job definition.</span></span> <span data-ttu-id="487cf-235">Используйте этот параметр для запуска заданий настраиваемых типов, которые имеют путь к определению, например запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="487cf-235">Use this parameter to start custom job types that have a definition path, such as scheduled jobs.</span></span>

<span data-ttu-id="487cf-236">Для запланированных заданий значение параметра **DefinitionPath** равно `$home\AppData\Local\Windows\PowerShell\ScheduledJob` .</span><span class="sxs-lookup"><span data-stu-id="487cf-236">For scheduled jobs, the value of the **DefinitionPath** parameter is `$home\AppData\Local\Windows\PowerShell\ScheduledJob`.</span></span>

<span data-ttu-id="487cf-237">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="487cf-237">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="487cf-238">-FilePath</span><span class="sxs-lookup"><span data-stu-id="487cf-238">-FilePath</span></span>

<span data-ttu-id="487cf-239">Указывает локальный скрипт, который `Start-Job` выполняется как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="487cf-239">Specifies a local script that `Start-Job` runs as a background job.</span></span> <span data-ttu-id="487cf-240">Введите путь и имя файла скрипта или используйте конвейер для отправки пути скрипта в `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="487cf-240">Enter the path and file name of the script or use the pipeline to send a script path to `Start-Job`.</span></span> <span data-ttu-id="487cf-241">Сценарий должен находиться на локальном компьютере или в папке, к которой может получить доступ локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="487cf-241">The script must be on the local computer or in a folder that the local computer can access.</span></span>

<span data-ttu-id="487cf-242">При использовании этого параметра PowerShell преобразует содержимое указанного файла скрипта в блок скрипта и запускает блок скрипта в качестве фонового задания.</span><span class="sxs-lookup"><span data-stu-id="487cf-242">When you use this parameter, PowerShell converts the contents of the specified script file to a script block and runs the script block as a background job.</span></span>

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

### <span data-ttu-id="487cf-243">-Инитиализатионскрипт</span><span class="sxs-lookup"><span data-stu-id="487cf-243">-InitializationScript</span></span>

<span data-ttu-id="487cf-244">Указывает команды, выполняемые перед запуском задания.</span><span class="sxs-lookup"><span data-stu-id="487cf-244">Specifies commands that run before the job starts.</span></span> <span data-ttu-id="487cf-245">Чтобы создать блок скрипта, заключите команды в фигурные скобки ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="487cf-245">To create a script block, enclose the commands in curly braces (`{}`).</span></span>

<span data-ttu-id="487cf-246">Используйте этот параметр для подготовки сеанса, в рамках которого выполняется задание.</span><span class="sxs-lookup"><span data-stu-id="487cf-246">Use this parameter to prepare the session in which the job runs.</span></span> <span data-ttu-id="487cf-247">Например, его можно использовать для добавления в сеанс функций, оснасток и модулей.</span><span class="sxs-lookup"><span data-stu-id="487cf-247">For example, you can use it to add functions, snap-ins, and modules to the session.</span></span>

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

### <span data-ttu-id="487cf-248">-InputObject</span><span class="sxs-lookup"><span data-stu-id="487cf-248">-InputObject</span></span>

<span data-ttu-id="487cf-249">Указывает входные данные команды.</span><span class="sxs-lookup"><span data-stu-id="487cf-249">Specifies input to the command.</span></span> <span data-ttu-id="487cf-250">Введите переменную, содержащую объекты, либо введите команду или выражение для создания объектов.</span><span class="sxs-lookup"><span data-stu-id="487cf-250">Enter a variable that contains the objects, or type a command or expression that generates the objects.</span></span>

<span data-ttu-id="487cf-251">В значении параметра **ScriptBlock** используйте `$input` автоматическую переменную для представления входных объектов.</span><span class="sxs-lookup"><span data-stu-id="487cf-251">In the value of the **ScriptBlock** parameter, use the `$input` automatic variable to represent the input objects.</span></span>

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

### <span data-ttu-id="487cf-252">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="487cf-252">-LiteralPath</span></span>

<span data-ttu-id="487cf-253">Задает локальный скрипт, выполняемый этим командлетом в качестве фонового задания.</span><span class="sxs-lookup"><span data-stu-id="487cf-253">Specifies a local script that this cmdlet runs as a background job.</span></span> <span data-ttu-id="487cf-254">Введите путь к скрипту на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="487cf-254">Enter the path of a script on the local computer.</span></span>

<span data-ttu-id="487cf-255">`Start-Job` использует значение параметра **LiteralPath** точно так же, как оно типизировано.</span><span class="sxs-lookup"><span data-stu-id="487cf-255">`Start-Job` uses the value of the **LiteralPath** parameter exactly as it's typed.</span></span> <span data-ttu-id="487cf-256">Никакие символы не распознаются как подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="487cf-256">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="487cf-257">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="487cf-257">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="487cf-258">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="487cf-258">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="487cf-259">-Name</span><span class="sxs-lookup"><span data-stu-id="487cf-259">-Name</span></span>

<span data-ttu-id="487cf-260">Указывает понятное имя нового задания.</span><span class="sxs-lookup"><span data-stu-id="487cf-260">Specifies a friendly name for the new job.</span></span> <span data-ttu-id="487cf-261">С помощью имени можно указать задание для других командлетов задания, например `Stop-Job` командлета.</span><span class="sxs-lookup"><span data-stu-id="487cf-261">You can use the name to identify the job to other job cmdlets, such as the `Stop-Job` cmdlet.</span></span>

<span data-ttu-id="487cf-262">Понятное имя по умолчанию — `Job#` , где `#` — порядковый номер, увеличивающийся для каждого задания.</span><span class="sxs-lookup"><span data-stu-id="487cf-262">The default friendly name is `Job#`, where `#` is an ordinal number that is incremented for each job.</span></span>

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

### <span data-ttu-id="487cf-263">-PSVersion</span><span class="sxs-lookup"><span data-stu-id="487cf-263">-PSVersion</span></span>

<span data-ttu-id="487cf-264">Указывает версию.</span><span class="sxs-lookup"><span data-stu-id="487cf-264">Specifies a version.</span></span> <span data-ttu-id="487cf-265">`Start-Job` запускает задание с версией PowerShell.</span><span class="sxs-lookup"><span data-stu-id="487cf-265">`Start-Job` runs the job with the version of PowerShell.</span></span> <span data-ttu-id="487cf-266">Допустимые значения для этого параметра: `2.0` и `3.0` .</span><span class="sxs-lookup"><span data-stu-id="487cf-266">The acceptable values for this parameter are: `2.0` and `3.0`.</span></span>

<span data-ttu-id="487cf-267">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="487cf-267">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="487cf-268">-RunAs32</span><span class="sxs-lookup"><span data-stu-id="487cf-268">-RunAs32</span></span>

<span data-ttu-id="487cf-269">Указывает, что `Start-Job` запускает задание в 32-разрядном процессе.</span><span class="sxs-lookup"><span data-stu-id="487cf-269">Indicates that `Start-Job` runs the job in a 32-bit process.</span></span> <span data-ttu-id="487cf-270">**RunAs32** принудительно запускает задание в 32-разрядном процессе даже в 64-разрядной операционной системе.</span><span class="sxs-lookup"><span data-stu-id="487cf-270">**RunAs32** forces the job to run in a 32-bit process, even on a 64-bit operating system.</span></span>

<span data-ttu-id="487cf-271">В 64-разрядных версиях Windows 7 и Windows Server 2008 R2, если `Start-Job` команда содержит параметр **RunAs32** , нельзя использовать параметр **Credential** для указания учетных данных другого пользователя.</span><span class="sxs-lookup"><span data-stu-id="487cf-271">On 64-bit versions of Windows 7 and Windows Server 2008 R2, when the `Start-Job` command includes the **RunAs32** parameter, you can't use the **Credential** parameter to specify the credentials of another user.</span></span>

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

### <span data-ttu-id="487cf-272">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="487cf-272">-ScriptBlock</span></span>

<span data-ttu-id="487cf-273">Указывает команды, которые нужно выполнить в фоновом задании.</span><span class="sxs-lookup"><span data-stu-id="487cf-273">Specifies the commands to run in the background job.</span></span> <span data-ttu-id="487cf-274">Чтобы создать блок скрипта, заключите команды в фигурные скобки ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="487cf-274">To create a script block, enclose the commands in curly braces (`{}`).</span></span> <span data-ttu-id="487cf-275">Используйте `$input` автоматическую переменную для доступа к значению параметра **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="487cf-275">Use the `$input` automatic variable to access the value of the **InputObject** parameter.</span></span> <span data-ttu-id="487cf-276">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="487cf-276">This parameter is required.</span></span>

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

### <span data-ttu-id="487cf-277">-Type</span><span class="sxs-lookup"><span data-stu-id="487cf-277">-Type</span></span>

<span data-ttu-id="487cf-278">Указывает пользовательский тип для заданий, запускаемых `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="487cf-278">Specifies the custom type for jobs started by `Start-Job`.</span></span> <span data-ttu-id="487cf-279">Введите имя настраиваемого типа задания, например PSScheduledJob для запланированных заданий или PSWorkflowJob для заданий рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="487cf-279">Enter a custom job type name, such as PSScheduledJob for scheduled jobs or PSWorkflowJob for workflows jobs.</span></span> <span data-ttu-id="487cf-280">Этот параметр не является допустимым для стандартных фоновых заданий.</span><span class="sxs-lookup"><span data-stu-id="487cf-280">This parameter isn't valid for standard background jobs.</span></span>

<span data-ttu-id="487cf-281">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="487cf-281">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="487cf-282">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="487cf-282">CommonParameters</span></span>

<span data-ttu-id="487cf-283">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="487cf-283">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="487cf-284">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="487cf-284">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="487cf-285">Входные данные</span><span class="sxs-lookup"><span data-stu-id="487cf-285">INPUTS</span></span>

### <span data-ttu-id="487cf-286">System.String</span><span class="sxs-lookup"><span data-stu-id="487cf-286">System.String</span></span>

<span data-ttu-id="487cf-287">Конвейер можно использовать для отправки объекта со свойством **Name** в параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="487cf-287">You can use the pipeline to send an object with the **Name** property to the **Name** parameter.</span></span> <span data-ttu-id="487cf-288">Например, можно выполнить конвейер объекта **FileInfo** из `Get-ChildItem` в `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="487cf-288">For example, you can pipeline a **FileInfo** object from `Get-ChildItem` to `Start-Job`.</span></span>

## <span data-ttu-id="487cf-289">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="487cf-289">OUTPUTS</span></span>

### <span data-ttu-id="487cf-290">System. Management. Automation. Псремотингжоб</span><span class="sxs-lookup"><span data-stu-id="487cf-290">System.Management.Automation.PSRemotingJob</span></span>

<span data-ttu-id="487cf-291">`Start-Job` Возвращает объект **псремотингжоб** , представляющий запущенное задание.</span><span class="sxs-lookup"><span data-stu-id="487cf-291">`Start-Job` returns a **PSRemotingJob** object that represents the job that it started.</span></span>

## <span data-ttu-id="487cf-292">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="487cf-292">NOTES</span></span>

<span data-ttu-id="487cf-293">Для запуска в фоновом режиме `Start-Job` выполняется в собственном сеансе в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="487cf-293">To run in the background, `Start-Job` runs in its own session in the current session.</span></span> <span data-ttu-id="487cf-294">При использовании `Invoke-Command` командлета для выполнения `Start-Job` команды в сеансе на удаленном компьютере `Start-Job` выполняется в сеансе удаленного сеанса.</span><span class="sxs-lookup"><span data-stu-id="487cf-294">When you use the `Invoke-Command` cmdlet to run a `Start-Job` command in a session on a remote computer, `Start-Job` runs in a session in the remote session.</span></span>

## <span data-ttu-id="487cf-295">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="487cf-295">RELATED LINKS</span></span>

[<span data-ttu-id="487cf-296">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="487cf-296">about_Arrays</span></span>](./about/about_arrays.md)

[<span data-ttu-id="487cf-297">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="487cf-297">about_Automatic_Variables</span></span>](./about/about_automatic_variables.md)

[<span data-ttu-id="487cf-298">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="487cf-298">about_Jobs</span></span>](./About/about_Jobs.md)

[<span data-ttu-id="487cf-299">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="487cf-299">about_Job_Details</span></span>](./About/about_Job_Details.md)

[<span data-ttu-id="487cf-300">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="487cf-300">about_Remote_Jobs</span></span>](./About/about_Remote_Jobs.md)

[<span data-ttu-id="487cf-301">Get-Job.</span><span class="sxs-lookup"><span data-stu-id="487cf-301">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="487cf-302">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="487cf-302">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="487cf-303">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="487cf-303">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="487cf-304">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="487cf-304">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="487cf-305">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="487cf-305">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="487cf-306">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="487cf-306">Wait-Job</span></span>](Wait-Job.md)
