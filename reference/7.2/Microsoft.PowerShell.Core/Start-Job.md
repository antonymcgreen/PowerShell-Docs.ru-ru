---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/start-job?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Job
ms.openlocfilehash: 491292253578f287940490bad198698fc4b87e37
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600185"
---
# <span data-ttu-id="76935-102">Start-Job</span><span class="sxs-lookup"><span data-stu-id="76935-102">Start-Job</span></span>

## <span data-ttu-id="76935-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="76935-103">SYNOPSIS</span></span>
<span data-ttu-id="76935-104">Запускает фоновое задание PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76935-104">Starts a PowerShell background job.</span></span>

## <span data-ttu-id="76935-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="76935-105">SYNTAX</span></span>

### <span data-ttu-id="76935-106">ComputerName (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="76935-106">ComputerName (Default)</span></span>

```
Start-Job [-Name <String>] [-ScriptBlock] <ScriptBlock> [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>]
 [-WorkingDirectory <String>] [-RunAs32] [-PSVersion <Version>] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="76935-107">DefinitionName</span><span class="sxs-lookup"><span data-stu-id="76935-107">DefinitionName</span></span>

```
Start-Job [-DefinitionName] <String> [[-DefinitionPath] <String>] [[-Type] <String>]
 [-WorkingDirectory <String>] [<CommonParameters>]
```

### <span data-ttu-id="76935-108">филепаскомпутернаме</span><span class="sxs-lookup"><span data-stu-id="76935-108">FilePathComputerName</span></span>

```
Start-Job [-Name <String>] [-Credential <PSCredential>] [-FilePath] <String>
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>]
 [-WorkingDirectory <String>] [-RunAs32] [-PSVersion <Version>] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="76935-109">литералфилепаскомпутернаме</span><span class="sxs-lookup"><span data-stu-id="76935-109">LiteralFilePathComputerName</span></span>

```
Start-Job [-Name <String>] [-Credential <PSCredential>] -LiteralPath <String>
 [-Authentication <AuthenticationMechanism>] [[-InitializationScript] <ScriptBlock>]
 [-WorkingDirectory <String>] [-RunAs32] [-PSVersion <Version>] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

## <span data-ttu-id="76935-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="76935-110">DESCRIPTION</span></span>

<span data-ttu-id="76935-111">`Start-Job`Командлет запускает фоновое задание PowerShell на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="76935-111">The `Start-Job` cmdlet starts a PowerShell background job on the local computer.</span></span>

<span data-ttu-id="76935-112">Фоновое задание PowerShell выполняет команду без взаимодействия с текущим сеансом.</span><span class="sxs-lookup"><span data-stu-id="76935-112">A PowerShell background job runs a command without interacting with the current session.</span></span> <span data-ttu-id="76935-113">При запуске фонового задания объект задания возвращается немедленно, даже если для завершения задания требуется дополнительное время.</span><span class="sxs-lookup"><span data-stu-id="76935-113">When you start a background job, a job object returns immediately, even if the job takes an extended time to finish.</span></span> <span data-ttu-id="76935-114">Пока задание выполняется, можно продолжать работу с данным сеансом.</span><span class="sxs-lookup"><span data-stu-id="76935-114">You can continue to work in the session without interruption while the job runs.</span></span>

<span data-ttu-id="76935-115">Объект задания содержит полезные сведения о задании, но не содержит результатов задания.</span><span class="sxs-lookup"><span data-stu-id="76935-115">The job object contains useful information about the job, but it doesn't contain the job results.</span></span>
<span data-ttu-id="76935-116">По завершении задания используйте `Receive-Job` командлет для получения результатов задания.</span><span class="sxs-lookup"><span data-stu-id="76935-116">When the job finishes, use the `Receive-Job` cmdlet to get the results of the job.</span></span> <span data-ttu-id="76935-117">Дополнительные сведения о фоновых заданиях см. в разделе [about_Jobs](./About/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="76935-117">For more information about background jobs, see [about_Jobs](./About/about_Jobs.md).</span></span>

<span data-ttu-id="76935-118">Чтобы запустить фоновое задание на удаленном компьютере, используйте параметр **AsJob** , доступный во многих командлетах, или используйте `Invoke-Command` командлет для выполнения `Start-Job` команды на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="76935-118">To run a background job on a remote computer, use the **AsJob** parameter that is available on many cmdlets, or use the `Invoke-Command` cmdlet to run a `Start-Job` command on the remote computer.</span></span> <span data-ttu-id="76935-119">Дополнительные сведения см. в разделе [about_Remote_Jobs](./About/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="76935-119">For more information, see [about_Remote_Jobs](./About/about_Remote_Jobs.md).</span></span>

<span data-ttu-id="76935-120">Начиная с версии PowerShell 3,0, `Start-Job` можно запускать экземпляры пользовательских типов заданий, например запланированные задания.</span><span class="sxs-lookup"><span data-stu-id="76935-120">Starting in PowerShell 3.0, `Start-Job` can start instances of custom job types, such as scheduled jobs.</span></span> <span data-ttu-id="76935-121">Сведения об использовании `Start-Job` для запуска заданий с пользовательскими типами см. в справочных документах по функциям типа задания.</span><span class="sxs-lookup"><span data-stu-id="76935-121">For information about how to use `Start-Job` to start jobs with custom types, see the help documents for the job type feature.</span></span>

<span data-ttu-id="76935-122">Начиная с PowerShell 6,0 можно запускать задания с помощью `&` фонового оператора амперсанд ().</span><span class="sxs-lookup"><span data-stu-id="76935-122">Beginning in PowerShell 6.0, you can start jobs using the ampersand (`&`) background operator.</span></span> <span data-ttu-id="76935-123">Функции фонового оператора похожи на `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="76935-123">The functionality of the background operator is similar to `Start-Job`.</span></span> <span data-ttu-id="76935-124">Оба метода запуска задания создают объект задания **псремотингжоб** .</span><span class="sxs-lookup"><span data-stu-id="76935-124">Both methods to start a job create a **PSRemotingJob** job object.</span></span> <span data-ttu-id="76935-125">Дополнительные сведения об использовании амперсанда ( `&` ) см. в разделе [about_Operators](./about/about_operators.md#background-operator-).</span><span class="sxs-lookup"><span data-stu-id="76935-125">For more information about using the ampersand (`&`), see [about_Operators](./about/about_operators.md#background-operator-).</span></span>

<span data-ttu-id="76935-126">В PowerShell 7 появился параметр **WorkingDirectory** , указывающий начальную рабочую папку фонового задания.</span><span class="sxs-lookup"><span data-stu-id="76935-126">PowerShell 7 introduced the **WorkingDirectory** parameter that specifies a background job's initial working directory.</span></span> <span data-ttu-id="76935-127">Если параметр не указан, `Start-Job` по умолчанию используется текущий рабочий каталог вызывающей стороны, запустившего задание.</span><span class="sxs-lookup"><span data-stu-id="76935-127">If the parameter isn't specified, `Start-Job` defaults to the current working directory of the caller that started the job.</span></span>

> [!NOTE]
> <span data-ttu-id="76935-128">Создание внепроцессного фонового задания с помощью `Start-Job` не поддерживается в сценарии, в котором PowerShell размещается в других приложениях, например в функциях Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76935-128">Creating an out-of-process background job with `Start-Job` is not supported in the scenario where PowerShell is being hosted in other applications, such as the PowerShell Azure Functions.</span></span>
>
> <span data-ttu-id="76935-129">Это связано с тем, что `Start-Job` зависит от `pwsh` исполняемого файла, который должен быть доступен `$PSHOME` для запуска незавершенного фонового задания, но когда приложение размещает PowerShell, оно напрямую использует пакеты SDK NuGet для PowerShell и не будет `pwsh` доставлено.</span><span class="sxs-lookup"><span data-stu-id="76935-129">This is by design because `Start-Job` depends on the `pwsh` executable to be available under `$PSHOME` to start an out-of-process background job, but when an application is hosting PowerShell, it's directly using the PowerShell NuGet SDK packages and won't have `pwsh` shipped along.</span></span>
>
> <span data-ttu-id="76935-130">Подстановка в этом сценарии осуществляется `Start-ThreadJob` из модуля **[среаджоб](https://www.powershellgallery.com/packages/ThreadJob)**.</span><span class="sxs-lookup"><span data-stu-id="76935-130">The substitute in that scenario is `Start-ThreadJob` from the module **[ThreadJob](https://www.powershellgallery.com/packages/ThreadJob)**.</span></span>

## <span data-ttu-id="76935-131">Примеры</span><span class="sxs-lookup"><span data-stu-id="76935-131">EXAMPLES</span></span>

### <span data-ttu-id="76935-132">Пример 1. Запуск фонового задания</span><span class="sxs-lookup"><span data-stu-id="76935-132">Example 1: Start a background job</span></span>

<span data-ttu-id="76935-133">В этом примере запускается фоновое задание, выполняемое на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="76935-133">This example starts a background job that runs on the local computer.</span></span>

```powershell
Start-Job -ScriptBlock { Get-Process -Name pwsh }
```

```Output
Id  Name   PSJobTypeName   State     HasMoreData   Location    Command
--  ----   -------------   -----     -----------   --------    -------
1   Job1   BackgroundJob   Running   True          localhost   Get-Process -Name pwsh
```

<span data-ttu-id="76935-134">`Start-Job` использует параметр **ScriptBlock** для выполнения в `Get-Process` качестве фонового задания.</span><span class="sxs-lookup"><span data-stu-id="76935-134">`Start-Job` uses the **ScriptBlock** parameter to run `Get-Process` as a background job.</span></span> <span data-ttu-id="76935-135">Параметр **Name** указывает на поиск процессов PowerShell `pwsh` .</span><span class="sxs-lookup"><span data-stu-id="76935-135">The **Name** parameter specifies to find PowerShell processes, `pwsh`.</span></span> <span data-ttu-id="76935-136">Отображаются сведения о задании, и PowerShell возвращается в командную строку, пока задание выполняется в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="76935-136">The job information is displayed and PowerShell returns to a prompt while the job runs in the background.</span></span>

<span data-ttu-id="76935-137">Чтобы просмотреть выходные данные задания, используйте `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="76935-137">To view the job's output, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="76935-138">Пример: `Receive-Job -Id 1`.</span><span class="sxs-lookup"><span data-stu-id="76935-138">For example, `Receive-Job -Id 1`.</span></span>

### <span data-ttu-id="76935-139">Пример 2. Использование оператора Background для запуска фонового задания</span><span class="sxs-lookup"><span data-stu-id="76935-139">Example 2: Use the background operator to start a background job</span></span>

<span data-ttu-id="76935-140">В этом примере оператор амперсанд ( `&` ) используется для запуска фонового задания на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="76935-140">This example uses the ampersand (`&`) background operator to start a background job on the local computer.</span></span> <span data-ttu-id="76935-141">Задание получает тот же результат, что и `Start-Job` в примере 1.</span><span class="sxs-lookup"><span data-stu-id="76935-141">The job gets the same result as `Start-Job` in Example 1.</span></span>

```powershell
Get-Process -Name pwsh &
```

```Output
Id    Name   PSJobTypeName   State       HasMoreData     Location      Command
--    ----   -------------   -----       -----------     --------      -------
5     Job5   BackgroundJob   Running     True            localhost     Microsoft.PowerShell.Man...
```

<span data-ttu-id="76935-142">`Get-Process` использует параметр **Name** для указания процессов PowerShell `pwsh` .</span><span class="sxs-lookup"><span data-stu-id="76935-142">`Get-Process` uses the **Name** parameter to specify PowerShell processes, `pwsh`.</span></span> <span data-ttu-id="76935-143">Амперсанд ( `&` ) запускает команду в качестве фонового задания.</span><span class="sxs-lookup"><span data-stu-id="76935-143">The ampersand (`&`) runs the command as a background job.</span></span> <span data-ttu-id="76935-144">Отображаются сведения о задании, и PowerShell возвращается в командную строку, пока задание выполняется в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="76935-144">The job information is displayed and PowerShell returns to a prompt while the job runs in the background.</span></span>

<span data-ttu-id="76935-145">Чтобы просмотреть выходные данные задания, используйте `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="76935-145">To view the job's output, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="76935-146">Пример: `Receive-Job -Id 5`.</span><span class="sxs-lookup"><span data-stu-id="76935-146">For example, `Receive-Job -Id 5`.</span></span>

### <span data-ttu-id="76935-147">Пример 3. Запуск задания с помощью Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="76935-147">Example 3: Start a job using Invoke-Command</span></span>

<span data-ttu-id="76935-148">В этом примере выполняется задание на нескольких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="76935-148">This example runs a job on multiple computers.</span></span> <span data-ttu-id="76935-149">Задание хранится в переменной и выполняется с помощью имени переменной в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76935-149">The job is stored in a variable and is executed by using the variable name on the PowerShell command line.</span></span>

```powershell
$jobWRM = Invoke-Command -ComputerName (Get-Content -Path C:\Servers.txt) -ScriptBlock {
   Get-Service -Name WinRM } -JobName WinRM -ThrottleLimit 16 -AsJob
```

<span data-ttu-id="76935-150">Задание, которое использует, `Invoke-Command` создается и сохраняется в `$jobWRM` переменной.</span><span class="sxs-lookup"><span data-stu-id="76935-150">A job that uses `Invoke-Command` is created and stored in the `$jobWRM` variable.</span></span> <span data-ttu-id="76935-151">`Invoke-Command` использует параметр **ComputerName** для указания компьютеров, на которых выполняется задание.</span><span class="sxs-lookup"><span data-stu-id="76935-151">`Invoke-Command` uses the **ComputerName** parameter to specify the computers where the job runs.</span></span> <span data-ttu-id="76935-152">`Get-Content` Возвращает имена серверов из `C:\Servers.txt` файла.</span><span class="sxs-lookup"><span data-stu-id="76935-152">`Get-Content` gets the server names from the `C:\Servers.txt` file.</span></span>

<span data-ttu-id="76935-153">Параметр **ScriptBlock** указывает команду, которая `Get-Service` Получает службу **WinRM** .</span><span class="sxs-lookup"><span data-stu-id="76935-153">The **ScriptBlock** parameter specifies a command that `Get-Service` gets the **WinRM** service.</span></span> <span data-ttu-id="76935-154">Параметр **JobName** указывает понятное имя для задания, **WinRM**.</span><span class="sxs-lookup"><span data-stu-id="76935-154">The **JobName** parameter specifies a friendly name for the job, **WinRM**.</span></span> <span data-ttu-id="76935-155">Параметр **ThrottleLimit** ограничивает количество одновременных команд до 16.</span><span class="sxs-lookup"><span data-stu-id="76935-155">The **ThrottleLimit** parameter limits the number of concurrent commands to 16.</span></span> <span data-ttu-id="76935-156">Параметр **AsJob** запускает фоновое задание, которое выполняет команду на серверах.</span><span class="sxs-lookup"><span data-stu-id="76935-156">The **AsJob** parameter starts a background job that runs the command on the servers.</span></span>

### <span data-ttu-id="76935-157">Пример 4. Получение сведений о задании</span><span class="sxs-lookup"><span data-stu-id="76935-157">Example 4: Get job information</span></span>

<span data-ttu-id="76935-158">Этот пример получает сведения о задании и отображает результаты завершенного задания, которое было запущено на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="76935-158">This example gets information about a job and displays the results of a completed job that was run on the local computer.</span></span>

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

<span data-ttu-id="76935-159">`Start-Job` использует параметр **ScriptBlock** для выполнения команды, указывающей `Get-WinEvent` на получение **системного** журнала.</span><span class="sxs-lookup"><span data-stu-id="76935-159">`Start-Job` uses the **ScriptBlock** parameter to run a command that specifies `Get-WinEvent` to get the **System** log.</span></span> <span data-ttu-id="76935-160">Параметр **Credential** указывает учетную запись пользователя домена с разрешением на запуск задания на компьютере.</span><span class="sxs-lookup"><span data-stu-id="76935-160">The **Credential** parameter specifies a domain user account with permission to run the job on the computer.</span></span> <span data-ttu-id="76935-161">Объект задания хранится в `$j` переменной.</span><span class="sxs-lookup"><span data-stu-id="76935-161">The job object is stored in the `$j` variable.</span></span>

<span data-ttu-id="76935-162">Объект в `$j` переменной отправляется по конвейеру в `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="76935-162">The object in the `$j` variable is sent down the pipeline to `Select-Object`.</span></span> <span data-ttu-id="76935-163">Параметр **Property** задает звездочку ( `*` ) для вывода свойств объекта задания.</span><span class="sxs-lookup"><span data-stu-id="76935-163">The **Property** parameter specifies an asterisk (`*`) to display all the job object's properties.</span></span>

### <span data-ttu-id="76935-164">Пример 5. Запуск скрипта как фонового задания</span><span class="sxs-lookup"><span data-stu-id="76935-164">Example 5: Run a script as a background job</span></span>

<span data-ttu-id="76935-165">В этом примере сценарий на локальном компьютере выполняется как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="76935-165">In this example, a script on the local computer is run as a background job.</span></span>

```powershell
Start-Job -FilePath C:\Scripts\Sample.ps1
```

<span data-ttu-id="76935-166">`Start-Job` использует параметр **FilePath** для указания файла скрипта, хранящегося на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="76935-166">`Start-Job` uses the **FilePath** parameter to specify a script file that's stored on the local computer.</span></span>

### <span data-ttu-id="76935-167">Пример 6. получение процесса с помощью фонового задания</span><span class="sxs-lookup"><span data-stu-id="76935-167">Example 6: Get a process using a background job</span></span>

<span data-ttu-id="76935-168">В этом примере для получения указанного процесса по имени используется фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="76935-168">This example uses a background job to get a specified process by name.</span></span>

```powershell
Start-Job -Name PShellJob -ScriptBlock { Get-Process -Name PowerShell }
```

<span data-ttu-id="76935-169">`Start-Job` использует параметр **Name** для указания понятного имени задания **пшеллжоб**.</span><span class="sxs-lookup"><span data-stu-id="76935-169">`Start-Job` uses the **Name** parameter to specify a friendly job name, **PShellJob**.</span></span> <span data-ttu-id="76935-170">Параметр **ScriptBlock** указывает `Get-Process` на получение процессов с именем **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="76935-170">The **ScriptBlock** parameter specifies `Get-Process` to get processes with the name **PowerShell**.</span></span>

### <span data-ttu-id="76935-171">Пример 7. получение и сохранение данных с помощью фонового задания</span><span class="sxs-lookup"><span data-stu-id="76935-171">Example 7: Collect and save data by using a background job</span></span>

<span data-ttu-id="76935-172">В этом примере запускается задание, которое собирает большой объем данных о карте и сохраняет их в `.tif` файле.</span><span class="sxs-lookup"><span data-stu-id="76935-172">This example starts a job that collects a large amount of map data and then saves it in a `.tif` file.</span></span>

```powershell
Start-Job -Name GetMappingFiles -InitializationScript {Import-Module MapFunctions} -ScriptBlock {
   Get-Map -Name * | Set-Content -Path D:\Maps.tif }
```

<span data-ttu-id="76935-173">`Start-Job` использует параметр **Name** для указания понятного имени задания **жетмаппингфилес**.</span><span class="sxs-lookup"><span data-stu-id="76935-173">`Start-Job` uses the **Name** parameter to specify a friendly job name, **GetMappingFiles**.</span></span> <span data-ttu-id="76935-174">Параметр **инитиализатионскрипт** выполняет блок скрипта, который импортирует модуль **мапфунктионс** .</span><span class="sxs-lookup"><span data-stu-id="76935-174">The **InitializationScript** parameter runs a script block that imports the **MapFunctions** module.</span></span> <span data-ttu-id="76935-175">Параметр **ScriptBlock** выполняется `Get-Map` и `Set-Content` сохраняет данные в расположении, указанном параметром **path** .</span><span class="sxs-lookup"><span data-stu-id="76935-175">The **ScriptBlock** parameter runs `Get-Map` and `Set-Content` saves the data in the location specified by the **Path** parameter.</span></span>

### <span data-ttu-id="76935-176">Пример 8. передача входных данных в фоновое задание</span><span class="sxs-lookup"><span data-stu-id="76935-176">Example 8: Pass input to a background job</span></span>

<span data-ttu-id="76935-177">В этом примере `$input` Автоматическая переменная используется для обработки входного объекта.</span><span class="sxs-lookup"><span data-stu-id="76935-177">This example uses the `$input` automatic variable to process an input object.</span></span> <span data-ttu-id="76935-178">Используйте `Receive-Job` для просмотра выходных данных задания.</span><span class="sxs-lookup"><span data-stu-id="76935-178">Use `Receive-Job` to view the job's output.</span></span>

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

<span data-ttu-id="76935-179">`Start-Job` использует параметр **ScriptBlock** для выполнения `Get-Content` с `$input` автоматической переменной.</span><span class="sxs-lookup"><span data-stu-id="76935-179">`Start-Job` uses the **ScriptBlock** parameter to run `Get-Content` with the `$input` automatic variable.</span></span> <span data-ttu-id="76935-180">`$input`Переменная получает объекты из параметра **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="76935-180">The `$input` variable gets objects from the **InputObject** parameter.</span></span> <span data-ttu-id="76935-181">`Receive-Job` использует параметр **Name** для указания задания и вывода результатов.</span><span class="sxs-lookup"><span data-stu-id="76935-181">`Receive-Job` uses the **Name** parameter to specify the job and outputs the results.</span></span> <span data-ttu-id="76935-182">Параметр **сохранить** сохраняет выходные данные задания, чтобы их можно было снова просмотреть во время сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76935-182">The **Keep** parameter saves the job output so it can be viewed again during the PowerShell session.</span></span>

### <span data-ttu-id="76935-183">Пример 9. Задание рабочего каталога для фонового задания</span><span class="sxs-lookup"><span data-stu-id="76935-183">Example 9: Set the working directory for a background job</span></span>

<span data-ttu-id="76935-184">**WorkingDirectory** позволяет указать альтернативный каталог для задания, из которого можно запускать скрипты или открывать файлы.</span><span class="sxs-lookup"><span data-stu-id="76935-184">The **WorkingDirectory** allows you to specify an alternate directory for a job from which you can run scripts or open files.</span></span> <span data-ttu-id="76935-185">В этом примере фоновое задание указывает рабочий каталог, который отличается от текущего расположения каталога.</span><span class="sxs-lookup"><span data-stu-id="76935-185">In this example, the background job specifies a working directory that's different than the current directory location.</span></span>

```
PS C:\Test> Start-Job -WorkingDirectory C:\Test\Scripts { $PWD } | Receive-Job -AutoRemoveJob -Wait

Path
----
C:\Test\Scripts
```

<span data-ttu-id="76935-186">Текущий рабочий каталог этого примера — `C:\Test` .</span><span class="sxs-lookup"><span data-stu-id="76935-186">This example's current working directory is `C:\Test`.</span></span> <span data-ttu-id="76935-187">`Start-Job` использует параметр **WorkingDirectory** для указания рабочего каталога задания.</span><span class="sxs-lookup"><span data-stu-id="76935-187">`Start-Job` uses the **WorkingDirectory** parameter to specify the job's working directory.</span></span> <span data-ttu-id="76935-188">Параметр **ScriptBlock** используется `$PWD` для вывода рабочего каталога задания.</span><span class="sxs-lookup"><span data-stu-id="76935-188">The **ScriptBlock** parameter uses `$PWD` to display the job's working directory.</span></span> <span data-ttu-id="76935-189">`Receive-Job` Отображает выходные данные фонового задания.</span><span class="sxs-lookup"><span data-stu-id="76935-189">`Receive-Job` displays the background job's output.</span></span>
<span data-ttu-id="76935-190">**Ауторемовежоб** удаляет задание и **ждет** , пока не будут получены все результаты, заблокируя командную строку.</span><span class="sxs-lookup"><span data-stu-id="76935-190">**AutoRemoveJob** deletes the job and **Wait** suppresses the command prompt until all results are received.</span></span>

### <span data-ttu-id="76935-191">Пример 10. Использование параметра ArgumentList для указания массива</span><span class="sxs-lookup"><span data-stu-id="76935-191">Example 10: Use the ArgumentList parameter to specify an array</span></span>

<span data-ttu-id="76935-192">В этом примере используется параметр **ArgumentList** для указания массива аргументов.</span><span class="sxs-lookup"><span data-stu-id="76935-192">This example uses the **ArgumentList** parameter to specify an array of arguments.</span></span> <span data-ttu-id="76935-193">Массив представляет собой разделенный запятыми список имен процессов.</span><span class="sxs-lookup"><span data-stu-id="76935-193">The array is a comma-separated list of process names.</span></span>

```powershell
Start-Job -ScriptBlock { Get-Process -Name $args } -ArgumentList powershell, pwsh, notepad
```

```Output
Id     Name      PSJobTypeName   State       HasMoreData     Location     Command
--     ----      -------------   -----       -----------     --------     -------
1      Job1      BackgroundJob   Running     True            localhost    Get-Process -Name $args
```

<span data-ttu-id="76935-194">`Start-Job`Командлет использует параметр **ScriptBlock** для выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="76935-194">The `Start-Job` cmdlet uses the **ScriptBlock** parameter to run a command.</span></span> <span data-ttu-id="76935-195">`Get-Process` Задает автоматическую переменную с помощью параметра **Name** `$args` .</span><span class="sxs-lookup"><span data-stu-id="76935-195">`Get-Process` uses the **Name** parameter to specify the automatic variable `$args`.</span></span> <span data-ttu-id="76935-196">Параметр **ArgumentList** передает массив имен процессов в `$args` .</span><span class="sxs-lookup"><span data-stu-id="76935-196">The **ArgumentList** parameter passes the array of process names to `$args`.</span></span> <span data-ttu-id="76935-197">Имена процессов PowerShell, pwsh и Notepad — это процессы, выполняемые на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="76935-197">The process names powershell, pwsh, and notepad are processes running on the local computer.</span></span>

<span data-ttu-id="76935-198">Чтобы просмотреть выходные данные задания, используйте `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="76935-198">To view the job's output, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="76935-199">Пример: `Receive-Job -Id 1`.</span><span class="sxs-lookup"><span data-stu-id="76935-199">For example, `Receive-Job -Id 1`.</span></span>

### <span data-ttu-id="76935-200">Пример 11. выполнение задания в Windows PowerShell 5,1</span><span class="sxs-lookup"><span data-stu-id="76935-200">Example 11: Run job in a Windows PowerShell 5.1</span></span>

<span data-ttu-id="76935-201">В этом примере для выполнения задания в сеансе Windows PowerShell 5,1 используется параметр **PSVersion** со значением **5,1** .</span><span class="sxs-lookup"><span data-stu-id="76935-201">This example uses the **PSVersion** parameter with value **5.1** to run job in a Windows PowerShell 5.1 session.</span></span>

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

## <span data-ttu-id="76935-202">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="76935-202">PARAMETERS</span></span>

### <span data-ttu-id="76935-203">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="76935-203">-ArgumentList</span></span>

<span data-ttu-id="76935-204">Задает массив аргументов или значений параметров для скрипта, заданного параметром **FilePath** , или команды, указанной с помощью параметра **ScriptBlock** .</span><span class="sxs-lookup"><span data-stu-id="76935-204">Specifies an array of arguments, or parameter values, for the script that is specified by the **FilePath** parameter or a command specified with the **ScriptBlock** parameter.</span></span>

<span data-ttu-id="76935-205">Аргументы должны передаваться в **ArgumentList** как аргумент массива с одним измерением.</span><span class="sxs-lookup"><span data-stu-id="76935-205">Arguments must be passed to **ArgumentList** as single-dimension array argument.</span></span> <span data-ttu-id="76935-206">Например, список с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="76935-206">For example, a comma-separated list.</span></span> <span data-ttu-id="76935-207">Дополнительные сведения о поведении **ArgumentList** см. в разделе [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="76935-207">For more information about the behavior of **ArgumentList**, see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

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

### <span data-ttu-id="76935-208">-Authentication</span><span class="sxs-lookup"><span data-stu-id="76935-208">-Authentication</span></span>

<span data-ttu-id="76935-209">Указывает механизм, используемый для проверки подлинности учетных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="76935-209">Specifies the mechanism that is used to authenticate user credentials.</span></span>

<span data-ttu-id="76935-210">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="76935-210">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="76935-211">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="76935-211">Default</span></span>
- <span data-ttu-id="76935-212">Basic</span><span class="sxs-lookup"><span data-stu-id="76935-212">Basic</span></span>
- <span data-ttu-id="76935-213">CredSSP</span><span class="sxs-lookup"><span data-stu-id="76935-213">Credssp</span></span>
- <span data-ttu-id="76935-214">Digest (дайджест)</span><span class="sxs-lookup"><span data-stu-id="76935-214">Digest</span></span>
- <span data-ttu-id="76935-215">Kerberos</span><span class="sxs-lookup"><span data-stu-id="76935-215">Kerberos</span></span>
- <span data-ttu-id="76935-216">Согласование</span><span class="sxs-lookup"><span data-stu-id="76935-216">Negotiate</span></span>
- <span data-ttu-id="76935-217">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="76935-217">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="76935-218">Значение по умолчанию — Default.</span><span class="sxs-lookup"><span data-stu-id="76935-218">The default value is Default.</span></span>

<span data-ttu-id="76935-219">Проверка подлинности CredSSP доступна только в Windows Vista, Windows Server 2008 и более поздних версиях операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="76935-219">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="76935-220">Дополнительные сведения о значениях этого параметра см. в разделе [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="76935-220">For more information about the values of this parameter, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="76935-221">Аутентификация CredSSP, в рамках которой учетные данные пользователя передаются на удаленный компьютер для проверки, предназначена для команд, требующих аутентификацию нескольких ресурсов, например для доступа к удаленной сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="76935-221">Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="76935-222">Этот механизм повышает риск безопасности удаленной операции.</span><span class="sxs-lookup"><span data-stu-id="76935-222">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="76935-223">Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="76935-223">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

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

### <span data-ttu-id="76935-224">-Credential</span><span class="sxs-lookup"><span data-stu-id="76935-224">-Credential</span></span>

<span data-ttu-id="76935-225">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="76935-225">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="76935-226">Если параметр **Credential** не указан, команда использует учетные данные текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="76935-226">If the **Credential** parameter isn't specified, the command uses the current user's credentials.</span></span>

<span data-ttu-id="76935-227">Введите имя пользователя, например **User01** или **Domain01\User01**, либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="76935-227">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="76935-228">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="76935-228">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="76935-229">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="76935-229">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="76935-230">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="76935-230">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="76935-231">-DefinitionName</span><span class="sxs-lookup"><span data-stu-id="76935-231">-DefinitionName</span></span>

<span data-ttu-id="76935-232">Указывает имя определения задания, запускаемого этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="76935-232">Specifies the definition name of the job that this cmdlet starts.</span></span> <span data-ttu-id="76935-233">Используйте этот параметр для запуска заданий настраиваемых типов, имеющих имя определения, например запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="76935-233">Use this parameter to start custom job types that have a definition name, such as scheduled jobs.</span></span>

<span data-ttu-id="76935-234">При использовании `Start-Job` для запуска экземпляра запланированного задания задание запускается немедленно, независимо от триггеров задания или параметров задания.</span><span class="sxs-lookup"><span data-stu-id="76935-234">When you use `Start-Job` to start an instance of a scheduled job, the job starts immediately, regardless of job triggers or job options.</span></span> <span data-ttu-id="76935-235">Результирующий экземпляр задания — это запланированное задание, но оно не сохраняется на диск, например запуск запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="76935-235">The resulting job instance is a scheduled job, but it isn't saved to disk like triggered scheduled jobs.</span></span> <span data-ttu-id="76935-236">Параметр **ArgumentList** аргумента нельзя использовать `Start-Job` для предоставления значений для параметров скриптов, выполняемых в запланированном задании.</span><span class="sxs-lookup"><span data-stu-id="76935-236">You can't use the **ArgumentList** parameter of `Start-Job` to provide values for parameters of scripts that run in a scheduled job.</span></span>

<span data-ttu-id="76935-237">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="76935-237">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="76935-238">-DefinitionPath</span><span class="sxs-lookup"><span data-stu-id="76935-238">-DefinitionPath</span></span>

<span data-ttu-id="76935-239">Указывает путь определения задания, запускаемого этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="76935-239">Specifies path of the definition for the job that this cmdlet starts.</span></span> <span data-ttu-id="76935-240">Введите путь определения.</span><span class="sxs-lookup"><span data-stu-id="76935-240">Enter the definition path.</span></span> <span data-ttu-id="76935-241">Объединение значений параметров **DefinitionPath** и **DefinitionName** является полным путем к определению задания.</span><span class="sxs-lookup"><span data-stu-id="76935-241">The concatenation of the values of the **DefinitionPath** and **DefinitionName** parameters is the fully qualified path of the job definition.</span></span> <span data-ttu-id="76935-242">Используйте этот параметр для запуска заданий настраиваемых типов, которые имеют путь к определению, например запланированных заданий.</span><span class="sxs-lookup"><span data-stu-id="76935-242">Use this parameter to start custom job types that have a definition path, such as scheduled jobs.</span></span>

<span data-ttu-id="76935-243">Для запланированных заданий значение параметра **DefinitionPath** равно `$home\AppData\Local\Windows\PowerShell\ScheduledJob` .</span><span class="sxs-lookup"><span data-stu-id="76935-243">For scheduled jobs, the value of the **DefinitionPath** parameter is `$home\AppData\Local\Windows\PowerShell\ScheduledJob`.</span></span>

<span data-ttu-id="76935-244">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="76935-244">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="76935-245">-FilePath</span><span class="sxs-lookup"><span data-stu-id="76935-245">-FilePath</span></span>

<span data-ttu-id="76935-246">Указывает локальный скрипт, который `Start-Job` выполняется как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="76935-246">Specifies a local script that `Start-Job` runs as a background job.</span></span> <span data-ttu-id="76935-247">Введите путь и имя файла скрипта или используйте конвейер для отправки пути скрипта в `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="76935-247">Enter the path and file name of the script or use the pipeline to send a script path to `Start-Job`.</span></span> <span data-ttu-id="76935-248">Сценарий должен находиться на локальном компьютере или в папке, к которой может получить доступ локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="76935-248">The script must be on the local computer or in a folder that the local computer can access.</span></span>

<span data-ttu-id="76935-249">При использовании этого параметра PowerShell преобразует содержимое указанного файла скрипта в блок скрипта и запускает блок скрипта в качестве фонового задания.</span><span class="sxs-lookup"><span data-stu-id="76935-249">When you use this parameter, PowerShell converts the contents of the specified script file to a script block and runs the script block as a background job.</span></span>

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

### <span data-ttu-id="76935-250">-Инитиализатионскрипт</span><span class="sxs-lookup"><span data-stu-id="76935-250">-InitializationScript</span></span>

<span data-ttu-id="76935-251">Указывает команды, выполняемые перед запуском задания.</span><span class="sxs-lookup"><span data-stu-id="76935-251">Specifies commands that run before the job starts.</span></span> <span data-ttu-id="76935-252">Чтобы создать блок скрипта, заключите команды в фигурные скобки ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="76935-252">To create a script block, enclose the commands in curly braces (`{}`).</span></span>

<span data-ttu-id="76935-253">Используйте этот параметр для подготовки сеанса, в рамках которого выполняется задание.</span><span class="sxs-lookup"><span data-stu-id="76935-253">Use this parameter to prepare the session in which the job runs.</span></span> <span data-ttu-id="76935-254">Например, его можно использовать для добавления в сеанс функций, оснасток и модулей.</span><span class="sxs-lookup"><span data-stu-id="76935-254">For example, you can use it to add functions, snap-ins, and modules to the session.</span></span>

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

### <span data-ttu-id="76935-255">-InputObject</span><span class="sxs-lookup"><span data-stu-id="76935-255">-InputObject</span></span>

<span data-ttu-id="76935-256">Указывает входные данные команды.</span><span class="sxs-lookup"><span data-stu-id="76935-256">Specifies input to the command.</span></span> <span data-ttu-id="76935-257">Введите переменную, содержащую объекты, либо введите команду или выражение для создания объектов.</span><span class="sxs-lookup"><span data-stu-id="76935-257">Enter a variable that contains the objects, or type a command or expression that generates the objects.</span></span>

<span data-ttu-id="76935-258">В значении параметра **ScriptBlock** используйте `$input` автоматическую переменную для представления входных объектов.</span><span class="sxs-lookup"><span data-stu-id="76935-258">In the value of the **ScriptBlock** parameter, use the `$input` automatic variable to represent the input objects.</span></span>

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

### <span data-ttu-id="76935-259">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="76935-259">-LiteralPath</span></span>

<span data-ttu-id="76935-260">Задает локальный скрипт, выполняемый этим командлетом в качестве фонового задания.</span><span class="sxs-lookup"><span data-stu-id="76935-260">Specifies a local script that this cmdlet runs as a background job.</span></span> <span data-ttu-id="76935-261">Введите путь к скрипту на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="76935-261">Enter the path of a script on the local computer.</span></span>

<span data-ttu-id="76935-262">`Start-Job` использует значение параметра **LiteralPath** точно так же, как оно типизировано.</span><span class="sxs-lookup"><span data-stu-id="76935-262">`Start-Job` uses the value of the **LiteralPath** parameter exactly as it's typed.</span></span> <span data-ttu-id="76935-263">Никакие символы не распознаются как подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="76935-263">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="76935-264">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="76935-264">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="76935-265">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="76935-265">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="76935-266">-Name</span><span class="sxs-lookup"><span data-stu-id="76935-266">-Name</span></span>

<span data-ttu-id="76935-267">Указывает понятное имя нового задания.</span><span class="sxs-lookup"><span data-stu-id="76935-267">Specifies a friendly name for the new job.</span></span> <span data-ttu-id="76935-268">С помощью имени можно указать задание для других командлетов задания, например `Stop-Job` командлета.</span><span class="sxs-lookup"><span data-stu-id="76935-268">You can use the name to identify the job to other job cmdlets, such as the `Stop-Job` cmdlet.</span></span>

<span data-ttu-id="76935-269">Понятное имя по умолчанию — `Job#` , где `#` — порядковый номер, увеличивающийся для каждого задания.</span><span class="sxs-lookup"><span data-stu-id="76935-269">The default friendly name is `Job#`, where `#` is an ordinal number that is incremented for each job.</span></span>

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

### <span data-ttu-id="76935-270">-PSVersion</span><span class="sxs-lookup"><span data-stu-id="76935-270">-PSVersion</span></span>

<span data-ttu-id="76935-271">Указывает версию PowerShell для использования при выполнении задания.</span><span class="sxs-lookup"><span data-stu-id="76935-271">Specifies a version of PowerShell to use for running the job.</span></span>
<span data-ttu-id="76935-272">Если значение **PSVersion** равно **5,1** , задание выполняется в сеансе Windows PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="76935-272">When the value of **PSVersion** is **5.1** The job is run in a Windows PowerShell 5.1 session.</span></span>
<span data-ttu-id="76935-273">Для любого другого значения задание выполняется с использованием текущей версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76935-273">For any other value, the job is run using the current version of PowerShell.</span></span>

<span data-ttu-id="76935-274">Этот параметр был добавлен в PowerShell 7 и работает только в Windows.</span><span class="sxs-lookup"><span data-stu-id="76935-274">This parameter was added in PowerShell 7 and only works on Windows.</span></span>

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

### <span data-ttu-id="76935-275">-RunAs32</span><span class="sxs-lookup"><span data-stu-id="76935-275">-RunAs32</span></span>

<span data-ttu-id="76935-276">Начиная с PowerShell 7, параметр **RunAs32** не работает в 64-разрядной PowerShell ( `pwsh` ).</span><span class="sxs-lookup"><span data-stu-id="76935-276">Beginning with PowerShell 7, the **RunAs32** parameter doesn't work on 64-bit PowerShell (`pwsh`).</span></span>
<span data-ttu-id="76935-277">Если **RunAs32** указан в 64-разрядной версии PowerShell, `Start-Job` вызывается ошибка завершающего исключения.</span><span class="sxs-lookup"><span data-stu-id="76935-277">If **RunAs32** is specified in 64-bit PowerShell, `Start-Job` throws a terminating exception error.</span></span>
<span data-ttu-id="76935-278">Чтобы запустить 32-разрядный процесс PowerShell ( `pwsh` ) с помощью **RunAs32**, необходимо установить 32-разрядную версию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76935-278">To start a 32-bit PowerShell (`pwsh`) process with **RunAs32**, you need to have the 32-bit PowerShell installed.</span></span>

<span data-ttu-id="76935-279">В 32-разрядной версии PowerShell **RunAs32** принудительно запускает задание в 32-разрядном процессе даже в 64-разрядной операционной системе.</span><span class="sxs-lookup"><span data-stu-id="76935-279">In 32-bit PowerShell, **RunAs32** forces the job to run in a 32-bit process, even on a 64-bit operating system.</span></span>

<span data-ttu-id="76935-280">В 64-разрядных версиях Windows 7 и Windows Server 2008 R2, если `Start-Job` команда содержит параметр **RunAs32** , нельзя использовать параметр **Credential** для указания учетных данных другого пользователя.</span><span class="sxs-lookup"><span data-stu-id="76935-280">On 64-bit versions of Windows 7 and Windows Server 2008 R2, when the `Start-Job` command includes the **RunAs32** parameter, you can't use the **Credential** parameter to specify the credentials of another user.</span></span>

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

### <span data-ttu-id="76935-281">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="76935-281">-ScriptBlock</span></span>

<span data-ttu-id="76935-282">Указывает команды, которые нужно выполнить в фоновом задании.</span><span class="sxs-lookup"><span data-stu-id="76935-282">Specifies the commands to run in the background job.</span></span> <span data-ttu-id="76935-283">Чтобы создать блок скрипта, заключите команды в фигурные скобки ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="76935-283">To create a script block, enclose the commands in curly braces (`{}`).</span></span> <span data-ttu-id="76935-284">Используйте `$input` автоматическую переменную для доступа к значению параметра **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="76935-284">Use the `$input` automatic variable to access the value of the **InputObject** parameter.</span></span> <span data-ttu-id="76935-285">Это обязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="76935-285">This parameter is required.</span></span>

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

### <span data-ttu-id="76935-286">-Type</span><span class="sxs-lookup"><span data-stu-id="76935-286">-Type</span></span>

<span data-ttu-id="76935-287">Указывает пользовательский тип для заданий, запускаемых `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="76935-287">Specifies the custom type for jobs started by `Start-Job`.</span></span> <span data-ttu-id="76935-288">Введите имя настраиваемого типа задания, например PSScheduledJob для запланированных заданий или PSWorkflowJob для заданий рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="76935-288">Enter a custom job type name, such as PSScheduledJob for scheduled jobs or PSWorkflowJob for workflows jobs.</span></span> <span data-ttu-id="76935-289">Этот параметр не является допустимым для стандартных фоновых заданий.</span><span class="sxs-lookup"><span data-stu-id="76935-289">This parameter isn't valid for standard background jobs.</span></span>

<span data-ttu-id="76935-290">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="76935-290">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="76935-291">-WorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="76935-291">-WorkingDirectory</span></span>

<span data-ttu-id="76935-292">Указывает исходный рабочий каталог фонового задания.</span><span class="sxs-lookup"><span data-stu-id="76935-292">Specifies the initial working directory of the background job.</span></span> <span data-ttu-id="76935-293">Если параметр не указан, задание выполняется из расположения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="76935-293">If the parameter isn't specified, the job runs from the default location.</span></span> <span data-ttu-id="76935-294">Расположение по умолчанию — это текущий рабочий каталог вызывающего объекта, запустившего задание.</span><span class="sxs-lookup"><span data-stu-id="76935-294">The default location is the current working directory of the caller that started the job.</span></span>

<span data-ttu-id="76935-295">Этот параметр появился в PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="76935-295">This parameter was introduced in PowerShell 7.</span></span>

 ```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $HOME on Unix (macOS, Linux) and $HOME\Documents on Windows
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="76935-296">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="76935-296">CommonParameters</span></span>

<span data-ttu-id="76935-297">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="76935-297">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="76935-298">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="76935-298">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="76935-299">Входные данные</span><span class="sxs-lookup"><span data-stu-id="76935-299">INPUTS</span></span>

### <span data-ttu-id="76935-300">System.String</span><span class="sxs-lookup"><span data-stu-id="76935-300">System.String</span></span>

<span data-ttu-id="76935-301">Конвейер можно использовать для отправки объекта со свойством **Name** в параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="76935-301">You can use the pipeline to send an object with the **Name** property to the **Name** parameter.</span></span> <span data-ttu-id="76935-302">Например, можно выполнить конвейер объекта **FileInfo** из `Get-ChildItem` в `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="76935-302">For example, you can pipeline a **FileInfo** object from `Get-ChildItem` to `Start-Job`.</span></span>

## <span data-ttu-id="76935-303">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="76935-303">OUTPUTS</span></span>

### <span data-ttu-id="76935-304">System. Management. Automation. Псремотингжоб</span><span class="sxs-lookup"><span data-stu-id="76935-304">System.Management.Automation.PSRemotingJob</span></span>

<span data-ttu-id="76935-305">`Start-Job` Возвращает объект **псремотингжоб** , представляющий запущенное задание.</span><span class="sxs-lookup"><span data-stu-id="76935-305">`Start-Job` returns a **PSRemotingJob** object that represents the job that it started.</span></span>

## <span data-ttu-id="76935-306">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="76935-306">NOTES</span></span>

<span data-ttu-id="76935-307">Для запуска в фоновом режиме `Start-Job` выполняется в собственном сеансе в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="76935-307">To run in the background, `Start-Job` runs in its own session in the current session.</span></span> <span data-ttu-id="76935-308">При использовании `Invoke-Command` командлета для выполнения `Start-Job` команды в сеансе на удаленном компьютере `Start-Job` выполняется в сеансе удаленного сеанса.</span><span class="sxs-lookup"><span data-stu-id="76935-308">When you use the `Invoke-Command` cmdlet to run a `Start-Job` command in a session on a remote computer, `Start-Job` runs in a session in the remote session.</span></span>

## <span data-ttu-id="76935-309">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="76935-309">RELATED LINKS</span></span>

[<span data-ttu-id="76935-310">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="76935-310">about_Arrays</span></span>](./about/about_arrays.md)

[<span data-ttu-id="76935-311">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="76935-311">about_Automatic_Variables</span></span>](./about/about_automatic_variables.md)

[<span data-ttu-id="76935-312">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="76935-312">about_Jobs</span></span>](./About/about_Jobs.md)

[<span data-ttu-id="76935-313">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="76935-313">about_Job_Details</span></span>](./About/about_Job_Details.md)

[<span data-ttu-id="76935-314">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="76935-314">about_Remote_Jobs</span></span>](./About/about_Remote_Jobs.md)

[<span data-ttu-id="76935-315">Get-Job.</span><span class="sxs-lookup"><span data-stu-id="76935-315">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="76935-316">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="76935-316">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="76935-317">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="76935-317">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="76935-318">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="76935-318">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="76935-319">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="76935-319">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="76935-320">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="76935-320">Wait-Job</span></span>](Wait-Job.md)
