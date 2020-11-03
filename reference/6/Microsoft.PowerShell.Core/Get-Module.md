---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-module?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Module
ms.openlocfilehash: b3444b0670794b9cc65329cbaabc7e26dd131f64
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228726"
---
# <span data-ttu-id="06d21-103">Get-Module</span><span class="sxs-lookup"><span data-stu-id="06d21-103">Get-Module</span></span>

## <span data-ttu-id="06d21-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="06d21-104">SYNOPSIS</span></span>
<span data-ttu-id="06d21-105">Возвращает модули, которые были или могут быть импортированы в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="06d21-105">Gets the modules that have been imported or that can be imported into the current session.</span></span>

## <span data-ttu-id="06d21-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="06d21-106">SYNTAX</span></span>

### <span data-ttu-id="06d21-107">Загружено (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="06d21-107">Loaded (Default)</span></span>

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-All] [<CommonParameters>]
```

### <span data-ttu-id="06d21-108">Доступно</span><span class="sxs-lookup"><span data-stu-id="06d21-108">Available</span></span>

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-All] [-ListAvailable]
 [-PSEdition <String>] [-SkipEditionCheck] [-Refresh] [<CommonParameters>]
```

### <span data-ttu-id="06d21-109">PsSession</span><span class="sxs-lookup"><span data-stu-id="06d21-109">PsSession</span></span>

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-ListAvailable]
 [-PSEdition <String>] [-SkipEditionCheck] [-Refresh] -PSSession <PSSession> [<CommonParameters>]
```

### <span data-ttu-id="06d21-110">CimSession</span><span class="sxs-lookup"><span data-stu-id="06d21-110">CimSession</span></span>

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-ListAvailable]
 [-SkipEditionCheck] [-Refresh] -CimSession <CimSession> [-CimResourceUri <Uri>] [-CimNamespace <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="06d21-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="06d21-111">DESCRIPTION</span></span>

<span data-ttu-id="06d21-112">`Get-Module`Командлет возвращает модули PowerShell, которые были импортированы или могут быть импортированы, в сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06d21-112">The `Get-Module` cmdlet gets the PowerShell modules that have been imported, or that can be imported, into a PowerShell session.</span></span>
<span data-ttu-id="06d21-113">Объект модуля, который `Get-Module` возвращает, содержит ценные сведения о модуле.</span><span class="sxs-lookup"><span data-stu-id="06d21-113">The module object that `Get-Module` returns contains valuable information about the module.</span></span>
<span data-ttu-id="06d21-114">Можно также передать объекты модуля в другие командлеты, такие как `Import-Module` `Remove-Module` командлеты и.</span><span class="sxs-lookup"><span data-stu-id="06d21-114">You can also pipe the module objects to other cmdlets, such as the `Import-Module` and `Remove-Module` cmdlets.</span></span>

<span data-ttu-id="06d21-115">Без параметров `Get-Module` возвращает модули, которые были импортированы в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="06d21-115">Without parameters, `Get-Module` gets modules that have been imported into the current session.</span></span>
<span data-ttu-id="06d21-116">Чтобы получить все установленные модули, укажите параметр **ListAvailable** .</span><span class="sxs-lookup"><span data-stu-id="06d21-116">To get all installed modules, specify the **ListAvailable** parameter.</span></span>

<span data-ttu-id="06d21-117">`Get-Module` Возвращает модули, но не импортирует их.</span><span class="sxs-lookup"><span data-stu-id="06d21-117">`Get-Module` gets modules, but it does not import them.</span></span>
<span data-ttu-id="06d21-118">Начиная с Windows PowerShell 3,0 модули автоматически импортируются при использовании команды в модуле, но `Get-Module` команда не запускает автоматический импорт.</span><span class="sxs-lookup"><span data-stu-id="06d21-118">Starting in Windows PowerShell 3.0, modules are automatically imported when you use a command in the module, but a `Get-Module` command does not trigger an automatic import.</span></span>
<span data-ttu-id="06d21-119">Вы также можете импортировать модули в сеанс с помощью `Import-Module` командлета.</span><span class="sxs-lookup"><span data-stu-id="06d21-119">You can also import the modules into your session by using the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="06d21-120">Начиная с Windows PowerShell 3,0, вы можете получить и импортировать модули из удаленных сеансов в локальный сеанс.</span><span class="sxs-lookup"><span data-stu-id="06d21-120">Starting in Windows PowerShell 3.0, you can get and then, import modules from remote sessions into the local session.</span></span>
<span data-ttu-id="06d21-121">Эта стратегия использует функцию неявного удаленного взаимодействия PowerShell и эквивалентна использованию `Import-PSSession` командлета.</span><span class="sxs-lookup"><span data-stu-id="06d21-121">This strategy uses the Implicit Remoting feature of PowerShell and is equivalent to using the `Import-PSSession` cmdlet.</span></span>
<span data-ttu-id="06d21-122">При использовании команд в модулях, импортированных из другого сеанса, команды выполняются неявно в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="06d21-122">When you use commands in modules imported from another session, the commands run implicitly in the remote session.</span></span> <span data-ttu-id="06d21-123">Эта функция позволяет управлять удаленным компьютером из локального сеанса.</span><span class="sxs-lookup"><span data-stu-id="06d21-123">This feature lets you manage the remote computer from the local session.</span></span>

<span data-ttu-id="06d21-124">Кроме того, начиная с Windows PowerShell 3,0 можно использовать `Get-Module` и `Import-Module` для получения и импорта модулей модель CIM (CIM), в которых командлеты определяются в файлах XML определения командлетов (CDXML).</span><span class="sxs-lookup"><span data-stu-id="06d21-124">Also, starting in Windows PowerShell 3.0, you can use `Get-Module` and `Import-Module` to get and import Common Information Model (CIM) modules, in which the cmdlets are defined in Cmdlet Definition XML (CDXML) files.</span></span>
<span data-ttu-id="06d21-125">Эта функция позволяет использовать командлеты, реализованные в неуправляемых сборках кода, таких как написанные на C++.</span><span class="sxs-lookup"><span data-stu-id="06d21-125">This feature lets you use cmdlets that are implemented in non-managed code assemblies, such as those written in C++.</span></span>

<span data-ttu-id="06d21-126">С помощью этих новых функций `Get-Module` `Import-Module` командлеты и становятся основными средствами для управления разнородными предприятиями, включающими компьютеры под управлением операционной системы Windows и компьютеры под управлением других операционных систем.</span><span class="sxs-lookup"><span data-stu-id="06d21-126">With these new features, the `Get-Module` and `Import-Module` cmdlets become primary tools for managing heterogeneous enterprises that include computers that run the Windows operating system and computers that run other operating systems.</span></span>

<span data-ttu-id="06d21-127">Для управления удаленными компьютерами под управлением операционной системы Windows с включенным PowerShell и удаленным взаимодействием PowerShell создайте **сеанс PSSession** на удаленном компьютере, а затем используйте параметр **PSSession** , `Get-Module` чтобы получить модули PowerShell в **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="06d21-127">To manage remote computers that run the Windows operating system that have PowerShell and PowerShell remoting enabled, create a **PSSession** on the remote computer and then use the **PSSession** parameter of `Get-Module` to get the PowerShell modules in the **PSSession** .</span></span>
<span data-ttu-id="06d21-128">При импорте модулей и последующем использовании импортированных команд в текущем сеансе команды выполняются неявно в **сеансе PSSession** на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="06d21-128">When you import the modules, and then use the imported commands in the current session, the commands run implicitly in the **PSSession** on the remote computer.</span></span>
<span data-ttu-id="06d21-129">С помощью этой стратегии можно управлять удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="06d21-129">You can use this strategy to manage the remote computer.</span></span>

<span data-ttu-id="06d21-130">Аналогичную стратегию можно использовать для управления компьютерами, на которых не включено удаленное взаимодействие PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06d21-130">You can use a similar strategy to manage computers that do not have PowerShell remoting enabled.</span></span>
<span data-ttu-id="06d21-131">К ним относятся компьютеры, на которых не установлена операционная система Windows, а также компьютеры с PowerShell, для которых не включено удаленное взаимодействие PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06d21-131">These include computers that are not running the Windows operating system, and computers that have PowerShell but do not have PowerShell remoting enabled.</span></span>

<span data-ttu-id="06d21-132">Начните с создания сеанса CIM на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="06d21-132">Start by creating a CIM session on the remote computer.</span></span>
<span data-ttu-id="06d21-133">Сеанс CIM — это подключение к инструментарий управления Windows (WMI) (WMI) на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="06d21-133">A CIM session is a connection to Windows Management Instrumentation (WMI) on the remote computer.</span></span>
<span data-ttu-id="06d21-134">Затем используйте параметр **CIMSession** параметра, `Get-Module` чтобы получить модули CIM из сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="06d21-134">Then use the **CIMSession** parameter of `Get-Module` to get CIM modules from the CIM session.</span></span>
<span data-ttu-id="06d21-135">При импорте модуля CIM с помощью `Import-Module` командлета и последующем выполнении импортированных команд команды выполняются неявно на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="06d21-135">When you import a CIM module by using the `Import-Module` cmdlet and then run the imported commands, the commands run implicitly on the remote computer.</span></span>
<span data-ttu-id="06d21-136">С помощью этой стратегии, предполагающей использование инструментария WMI и модели CIM, можно управлять удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="06d21-136">You can use this WMI and CIM strategy to manage the remote computer.</span></span>

## <span data-ttu-id="06d21-137">Примеры</span><span class="sxs-lookup"><span data-stu-id="06d21-137">EXAMPLES</span></span>

### <span data-ttu-id="06d21-138">Пример 1. получение модулей, импортированных в текущий сеанс</span><span class="sxs-lookup"><span data-stu-id="06d21-138">Example 1: Get modules imported into the current session</span></span>

```powershell
Get-Module
```

<span data-ttu-id="06d21-139">Эта команда возвращает модули, которые были импортированы в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="06d21-139">This command gets modules that have been imported into the current session.</span></span>

### <span data-ttu-id="06d21-140">Пример 2. Получение установленных модулей и доступных модулей</span><span class="sxs-lookup"><span data-stu-id="06d21-140">Example 2: Get installed modules and available modules</span></span>

```powershell
Get-Module -ListAvailable
```

<span data-ttu-id="06d21-141">Эта команда возвращает модули, которые установлены на компьютере и могут быть импортированы в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="06d21-141">This command gets the modules that are installed on the computer and can be imported into the current session.</span></span>

<span data-ttu-id="06d21-142">`Get-Module` ищет доступные модули по пути, указанному в переменной среды **$env:P смодулепас** .</span><span class="sxs-lookup"><span data-stu-id="06d21-142">`Get-Module` looks for available modules in the path specified by the **$env:PSModulePath** environment variable.</span></span>
<span data-ttu-id="06d21-143">Подробнее о переменной среды **PSModulePath** , см. в разделах [about_Modules](About/about_Modules.md) и [about_Environment_Variables](About/about_Environment_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="06d21-143">For more information about **PSModulePath** , see [about_Modules](About/about_Modules.md) and [about_Environment_Variables](About/about_Environment_Variables.md).</span></span>

### <span data-ttu-id="06d21-144">Пример 3. получение всех экспортированных файлов</span><span class="sxs-lookup"><span data-stu-id="06d21-144">Example 3: Get all exported files</span></span>

```powershell
Get-Module -ListAvailable -All
```

<span data-ttu-id="06d21-145">Эта команда возвращает все экспортированные файлы для всех доступных модулей.</span><span class="sxs-lookup"><span data-stu-id="06d21-145">This command gets all of the exported files for all available modules.</span></span>

### <span data-ttu-id="06d21-146">Пример 4. Получение модуля по его полному имени</span><span class="sxs-lookup"><span data-stu-id="06d21-146">Example 4: Get a module by its fully qualified name</span></span>

```powershell
$FullyQualifedName = @{ModuleName="Microsoft.PowerShell.Management";ModuleVersion="3.1.0.0"}
  Get-Module -FullyQualifiedName $FullyQualifedName | Format-Table -Property Name,Version
```

```Output
Name                             Version
----                             -------
Microsoft.PowerShell.Management  3.1.0.0
```

<span data-ttu-id="06d21-147">Эта команда получает модуль **Microsoft. PowerShell. Management** , указывая полное имя модуля с помощью параметра **FullyQualifiedName** .</span><span class="sxs-lookup"><span data-stu-id="06d21-147">This command gets the **Microsoft.PowerShell.Management** module by specifying the fully qualified name of the module by using the **FullyQualifiedName** parameter.</span></span>
<span data-ttu-id="06d21-148">Затем команда передает результаты в `Format-Table` командлет, чтобы отформатировать результаты в виде таблицы с **именами** и **версиями** в качестве заголовков столбцов.</span><span class="sxs-lookup"><span data-stu-id="06d21-148">The command then pipes the results into the `Format-Table` cmdlet to format the results as a table with **Name** and **Version** as the column headings.</span></span>

### <span data-ttu-id="06d21-149">Пример 5. получение свойств модуля</span><span class="sxs-lookup"><span data-stu-id="06d21-149">Example 5: Get properties of a module</span></span>

```powershell
Get-Module | Get-Member -MemberType Property | Format-Table Name
```

```Output
Name
----
AccessMode
Author
ClrVersion
CompanyName
Copyright
Definition
Description
DotNetFrameworkVersion
ExportedAliases
ExportedCmdlets
ExportedCommands
ExportedFormatFiles
ExportedFunctions
ExportedTypeFiles
ExportedVariables
ExportedWorkflows
FileList
Guid
HelpInfoUri
LogPipelineExecutionDetails
ModuleBase
ModuleList
ModuleType
Name
NestedModules
OnRemove
Path
PowerShellHostName
PowerShellHostVersion
PowerShellVersion
PrivateData
ProcessorArchitecture
RequiredAssemblies
RequiredModules
RootModule
Scripts
SessionState
Version
```

<span data-ttu-id="06d21-150">Эта команда возвращает свойства объекта **PSModuleInfo** , который `Get-Module` возвращает.</span><span class="sxs-lookup"><span data-stu-id="06d21-150">This command gets the properties of the **PSModuleInfo** object that `Get-Module` returns.</span></span>
<span data-ttu-id="06d21-151">Для каждого файла модуля имеется один объект.</span><span class="sxs-lookup"><span data-stu-id="06d21-151">There is one object for each module file.</span></span>

<span data-ttu-id="06d21-152">С помощью свойств можно форматировать и фильтровать объекты модулей.</span><span class="sxs-lookup"><span data-stu-id="06d21-152">You can use the properties to format and filter the module objects.</span></span>
<span data-ttu-id="06d21-153">Дополнительные сведения о свойствах см. в разделе [Свойства PSModuleInfo](/dotnet/api/system.management.automation.psmoduleinfo).</span><span class="sxs-lookup"><span data-stu-id="06d21-153">For more information about the properties, see [PSModuleInfo Properties](/dotnet/api/system.management.automation.psmoduleinfo).</span></span>

<span data-ttu-id="06d21-154">Выходные данные включают новые свойства, такие как **Author** и **CompanyName** , которые появились в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="06d21-154">The output includes the new properties, such as **Author** and **CompanyName** , that were introduced in Windows PowerShell 3.0.</span></span>

### <span data-ttu-id="06d21-155">Пример 6. Группировка всех модулей по имени</span><span class="sxs-lookup"><span data-stu-id="06d21-155">Example 6: Group all modules by name</span></span>

```powershell
Get-Module -ListAvailable -All | Format-Table -Property Name, Moduletype, Path -Groupby Name
```

```Output
Name: AppLocker

Name      ModuleType Path
----      ---------- ----
AppLocker   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\AppLocker\AppLocker.psd1


   Name: Appx

Name ModuleType Path
---- ---------- ----
Appx   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Appx\en-US\Appx.psd1
Appx   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Appx\Appx.psd1
Appx     Script C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Appx\Appx.psm1


   Name: BestPractices

Name          ModuleType Path
----          ---------- ----
BestPractices   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\BestPractices\BestPractices.psd1


   Name: BitsTransfer

Name         ModuleType Path
----         ---------- ----
BitsTransfer   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\BitsTransfer\BitsTransfer.psd1
```

<span data-ttu-id="06d21-156">Эта команда возвращает все файлы модулей, импортированные и доступные, а затем группирует их по имени модуля.</span><span class="sxs-lookup"><span data-stu-id="06d21-156">This command gets all module files, both imported and available, and then groups them by module name.</span></span> <span data-ttu-id="06d21-157">Это позволяет увидеть, какие файлы модулей экспортирует каждый сценарий.</span><span class="sxs-lookup"><span data-stu-id="06d21-157">This lets you see the module files that each script is exporting.</span></span>

### <span data-ttu-id="06d21-158">Пример 7. Отображение содержимого манифеста модуля</span><span class="sxs-lookup"><span data-stu-id="06d21-158">Example 7: Display the contents of a module manifest</span></span>

<span data-ttu-id="06d21-159">Эти команды отображают содержимое манифеста модуля для модуля **BitsTransfer** PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06d21-159">These commands display the contents of the module manifest for the PowerShell **BitsTransfer** module.</span></span>

<span data-ttu-id="06d21-160">Модули не обязательно должны иметь файлы манифеста.</span><span class="sxs-lookup"><span data-stu-id="06d21-160">Modules are not required to have manifest files.</span></span>
<span data-ttu-id="06d21-161">Если у них есть файл манифеста, файл манифеста требуется только для включения номера версии.</span><span class="sxs-lookup"><span data-stu-id="06d21-161">When they do have a manifest file, the manifest file is required only to include a version number.</span></span>
<span data-ttu-id="06d21-162">Однако файлы манифестов часто предоставляют полезную информацию о модуле, его требованиях и содержимом.</span><span class="sxs-lookup"><span data-stu-id="06d21-162">However, manifest files often provide useful information about a module, its requirements, and its contents.</span></span>

```powershell
# First command
$m = Get-Module -list -Name BitsTransfer

# Second command
Get-Content $m.Path
```

```Output
@ {
    GUID               = "{8FA5064B-8479-4c5c-86EA-0D311FE48875}"
    Author             = "Microsoft Corporation"
    CompanyName        = "Microsoft Corporation"
    Copyright          = "Microsoft Corporation. All rights reserved."
    ModuleVersion      = "1.0.0.0"
    Description        = "Windows PowerShell File Transfer Module"
    PowerShellVersion  = "2.0"
    CLRVersion         = "2.0"
    NestedModules      = "Microsoft.BackgroundIntelligentTransfer.Management"
    FormatsToProcess   = "FileTransfer.Format.ps1xml"
    RequiredAssemblies = Join-Path $psScriptRoot "Microsoft.BackgroundIntelligentTransfer.Management.Interop.dll"
}
```

<span data-ttu-id="06d21-163">Первая команда возвращает объект PSModuleInfo, который представляет модуль BitsTransfer.</span><span class="sxs-lookup"><span data-stu-id="06d21-163">The first command gets the PSModuleInfo object that represents BitsTransfer module.</span></span> <span data-ttu-id="06d21-164">Объект сохраняется в `$m` переменной.</span><span class="sxs-lookup"><span data-stu-id="06d21-164">It saves the object in the `$m` variable.</span></span>

<span data-ttu-id="06d21-165">Вторая команда использует `Get-Content` командлет для получения содержимого файла манифеста по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="06d21-165">The second command uses the `Get-Content` cmdlet to get the content of the manifest file in the specified path.</span></span> <span data-ttu-id="06d21-166">В ней используется нотация с точками для получения пути к файлу манифеста, который хранится в свойстве Path объекта.</span><span class="sxs-lookup"><span data-stu-id="06d21-166">It uses dot notation to get the path to the manifest file, which is stored in the Path property of the object.</span></span> <span data-ttu-id="06d21-167">В выходных данных показано содержимое манифеста модуля.</span><span class="sxs-lookup"><span data-stu-id="06d21-167">The output shows the contents of the module manifest.</span></span>

### <span data-ttu-id="06d21-168">Пример 8. Вывод списка файлов в каталоге Module</span><span class="sxs-lookup"><span data-stu-id="06d21-168">Example 8: List files in module directory</span></span>

```powershell
dir (Get-Module -ListAvailable FileTransfer).ModuleBase
```

```Output
Directory: C:\Windows\system32\WindowsPowerShell\v1.0\Modules\FileTransfer
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----        12/16/2008  12:36 PM            en-US
-a---        11/19/2008  11:30 PM      16184 FileTransfer.Format.ps1xml
-a---        11/20/2008  11:30 PM       1044 FileTransfer.psd1
-a---        12/16/2008  12:20 AM     108544 Microsoft.BackgroundIntelligentTransfer.Management.Interop.dll
```

<span data-ttu-id="06d21-169">Эта команда выводит список файлов в каталоге модуля.</span><span class="sxs-lookup"><span data-stu-id="06d21-169">This command lists the files in the directory of the module.</span></span>
<span data-ttu-id="06d21-170">Это еще один способ определить, что входит в модуль, перед его импортом.</span><span class="sxs-lookup"><span data-stu-id="06d21-170">This is another way to determine what is in a module before you import it.</span></span>
<span data-ttu-id="06d21-171">Некоторые модули могут иметь файлы справки или файлы ReadMe, в которых описывается модуль.</span><span class="sxs-lookup"><span data-stu-id="06d21-171">Some modules might have help files or ReadMe files that describe the module.</span></span>

### <span data-ttu-id="06d21-172">Пример 9. получение модулей, установленных на компьютере</span><span class="sxs-lookup"><span data-stu-id="06d21-172">Example 9: Get modules installed on a computer</span></span>

```powershell
$s = New-PSSession -ComputerName Server01

Get-Module -PSSession $s -ListAvailable
```

<span data-ttu-id="06d21-173">Эти команды возвращают модули, которые установлены на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="06d21-173">These commands get the modules that are installed on the Server01 computer.</span></span>

<span data-ttu-id="06d21-174">Первая команда использует `New-PSSession` командлет для создания **сеанса PSSession** на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="06d21-174">The first command uses the `New-PSSession` cmdlet to create a **PSSession** on the Server01 computer.</span></span> <span data-ttu-id="06d21-175">Команда сохраняет **PSSession** в переменной $s.</span><span class="sxs-lookup"><span data-stu-id="06d21-175">The command saves the **PSSession** in the $s variable.</span></span>

<span data-ttu-id="06d21-176">Вторая команда использует параметры **PSSession** и **ListAvailable** `Get-Module` для получения модулей в **PSSession** в переменной $s.</span><span class="sxs-lookup"><span data-stu-id="06d21-176">The second command uses the **PSSession** and **ListAvailable** parameters of `Get-Module` to get the modules in the **PSSession** in the $s variable.</span></span>

<span data-ttu-id="06d21-177">При передаче модулей из других сеансов в `Import-Module` командлет `Import-Module` импортирует модуль в текущий сеанс с помощью функции неявного удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="06d21-177">If you pipe modules from other sessions to the `Import-Module` cmdlet, `Import-Module` imports the module into the current session by using the implicit remoting feature.</span></span>
<span data-ttu-id="06d21-178">Это эквивалентно использованию `Import-PSSession` командлета.</span><span class="sxs-lookup"><span data-stu-id="06d21-178">This is equivalent to using the `Import-PSSession` cmdlet.</span></span>
<span data-ttu-id="06d21-179">Вы можете использовать командлеты из модуля в рамках текущего сеанса, но команды, использующие эти командлеты, на самом деле выполняются в рамках удаленного сеанса.</span><span class="sxs-lookup"><span data-stu-id="06d21-179">You can use the cmdlets from the module in the current session, but commands that use these cmdlets actually run the remote session.</span></span>
<span data-ttu-id="06d21-180">Дополнительные сведения см. в разделах [`Import-Module`](Import-Module.md) и [`Import-PSSession`](../Microsoft.PowerShell.Utility/Import-PSSession.md).</span><span class="sxs-lookup"><span data-stu-id="06d21-180">For more information, see [`Import-Module`](Import-Module.md) and [`Import-PSSession`](../Microsoft.PowerShell.Utility/Import-PSSession.md).</span></span>

### <span data-ttu-id="06d21-181">Пример 10. Управление компьютером, на котором не выполняется операционная система Windows</span><span class="sxs-lookup"><span data-stu-id="06d21-181">Example 10: Manage a computer that does not run the Windows operating system</span></span>

<span data-ttu-id="06d21-182">Команды в этом примере позволяют управлять системами хранения на удаленном компьютере, на котором не установлена операционная система Windows.</span><span class="sxs-lookup"><span data-stu-id="06d21-182">The commands in this example enable you to manage the storage systems of a remote computer that is not running the Windows operating system.</span></span>
<span data-ttu-id="06d21-183">Поскольку администратор в этом примере установил поставщик WMI модуля обнаружения на на компьютере, команды CIM могут использовать значения по умолчанию, которые предназначены для поставщика.</span><span class="sxs-lookup"><span data-stu-id="06d21-183">In this example, because the administrator of the computer has installed the Module Discovery WMI provider, the CIM commands can use the default values, which are designed for the provider.</span></span>

```powershell
$cs = New-CimSession -ComputerName RSDGF03
Get-Module -CimSession $cs -Name Storage | Import-Module
Get-Command Get-Disk
```

```Output
CommandType     Name                  ModuleName
-----------     ----                  ----------
Function        Get-Disk              Storage
```

```powershell
Get-Disk
```

```Output
Number Friendly Name              OperationalStatus          Total Size Partition Style
------ -------------              -----------------          ---------- ---------------
0      Virtual HD ATA Device      Online                          40 GB MBR
```

<span data-ttu-id="06d21-184">Первая команда использует `New-CimSession` командлет для создания сеанса на удаленном компьютере RSDGF03.</span><span class="sxs-lookup"><span data-stu-id="06d21-184">The first command uses the `New-CimSession` cmdlet to create a session on the RSDGF03 remote computer.</span></span> <span data-ttu-id="06d21-185">Сеанс подключается к инструментарию WMI на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="06d21-185">The session connects to WMI on the remote computer.</span></span> <span data-ttu-id="06d21-186">Команда сохраняет сеанс CIM в `$cs` переменной.</span><span class="sxs-lookup"><span data-stu-id="06d21-186">The command saves the CIM session in the `$cs` variable.</span></span>

<span data-ttu-id="06d21-187">Вторая команда использует сеанс CIM в `$cs` переменной для выполнения `Get-Module` команды на компьютере RSDGF03.</span><span class="sxs-lookup"><span data-stu-id="06d21-187">The second command uses the CIM session in the `$cs` variable to run a `Get-Module` command on the RSDGF03 computer.</span></span> <span data-ttu-id="06d21-188">С помощью параметра Name указывается модуль хранения.</span><span class="sxs-lookup"><span data-stu-id="06d21-188">The command uses the Name parameter to specify the Storage module.</span></span> <span data-ttu-id="06d21-189">Команда использует оператор конвейера (|) для отправки модуля хранения в `Import-Module` командлет, который импортирует его в локальный сеанс.</span><span class="sxs-lookup"><span data-stu-id="06d21-189">The command uses a pipeline operator (|) to send the Storage module to the `Import-Module` cmdlet, which imports it into the local session.</span></span>

<span data-ttu-id="06d21-190">Третья команда выполняет `Get-Command` командлет для `Get-Disk` команды в модуле Storage.</span><span class="sxs-lookup"><span data-stu-id="06d21-190">The third command runs the `Get-Command` cmdlet on the `Get-Disk` command in the Storage module.</span></span>
<span data-ttu-id="06d21-191">При импорте модуля CIM в локальный сеанс PowerShell преобразует файлы CDXML, представляющие модуль CIM, в скрипты PowerShell, которые отображаются как функции в локальном сеансе.</span><span class="sxs-lookup"><span data-stu-id="06d21-191">When you import a CIM module into the local session, PowerShell converts the CDXML files that represent the CIM module into PowerShell scripts, which appear as functions in the local session.</span></span>

<span data-ttu-id="06d21-192">Четвертая команда выполняет `Get-Disk` команду.</span><span class="sxs-lookup"><span data-stu-id="06d21-192">The fourth command runs the `Get-Disk` command.</span></span> <span data-ttu-id="06d21-193">Хотя команда вводится в рамках текущего сеанса, она выполняется неявно на удаленном компьютере, с которого она была импортирована.</span><span class="sxs-lookup"><span data-stu-id="06d21-193">Although the command is typed in the local session, it runs implicitly on the remote computer from which it was imported.</span></span> <span data-ttu-id="06d21-194">Команда получает объекты с удаленного компьютера и возвращает их в локальный сеанс.</span><span class="sxs-lookup"><span data-stu-id="06d21-194">The command gets objects from the remote computer and returns them to the local session.</span></span>

## <span data-ttu-id="06d21-195">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="06d21-195">PARAMETERS</span></span>

### <span data-ttu-id="06d21-196">-All</span><span class="sxs-lookup"><span data-stu-id="06d21-196">-All</span></span>

<span data-ttu-id="06d21-197">Указывает, что этот командлет получает все модули в каждой папке модуля, включая вложенные модули, файлы манифеста (PSD1), файлы модуля скрипта (. PSM1) и двоичные файлы (DLL).</span><span class="sxs-lookup"><span data-stu-id="06d21-197">Indicates that this cmdlet gets all modules in each module folder, including nested modules, manifest (.psd1) files, script module (.psm1) files, and binary module (.dll) files.</span></span>
<span data-ttu-id="06d21-198">Без этого параметра `Get-Module` получает только модуль по умолчанию в каждой папке модуля.</span><span class="sxs-lookup"><span data-stu-id="06d21-198">Without this parameter, `Get-Module` gets only the default module in each module folder.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Loaded, Available
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="06d21-199">-Цимнамеспаце</span><span class="sxs-lookup"><span data-stu-id="06d21-199">-CimNamespace</span></span>

<span data-ttu-id="06d21-200">Задает пространство имен для альтернативного поставщика CIM, предоставляющего модули CIM.</span><span class="sxs-lookup"><span data-stu-id="06d21-200">Specifies the namespace of an alternate CIM provider that exposes CIM modules.</span></span>
<span data-ttu-id="06d21-201">Значение по умолчанию — пространство имен поставщика модуля обнаружения WMI.</span><span class="sxs-lookup"><span data-stu-id="06d21-201">The default value is the namespace of the Module Discovery WMI provider.</span></span>

<span data-ttu-id="06d21-202">Этот параметр используется для получения модулей CIM с компьютеров и устройств, на которых не установлена операционная система Windows.</span><span class="sxs-lookup"><span data-stu-id="06d21-202">Use this parameter to get CIM modules from computers and devices that are not running the Windows operating system.</span></span>

<span data-ttu-id="06d21-203">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="06d21-203">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="06d21-204">-Цимресаурцеури</span><span class="sxs-lookup"><span data-stu-id="06d21-204">-CimResourceUri</span></span>

<span data-ttu-id="06d21-205">Задает альтернативное расположение для модулей CIM.</span><span class="sxs-lookup"><span data-stu-id="06d21-205">Specifies an alternate location for CIM modules.</span></span>
<span data-ttu-id="06d21-206">Значение по умолчанию — URI ресурса поставщика модуля обнаружения WMI на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="06d21-206">The default value is the resource URI of the Module Discovery WMI provider on the remote computer.</span></span>

<span data-ttu-id="06d21-207">Этот параметр используется для получения модулей CIM с компьютеров и устройств, на которых не установлена операционная система Windows.</span><span class="sxs-lookup"><span data-stu-id="06d21-207">Use this parameter to get CIM modules from computers and devices that are not running the Windows operating system.</span></span>

<span data-ttu-id="06d21-208">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="06d21-208">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Uri
Parameter Sets: CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="06d21-209">-CimSession</span><span class="sxs-lookup"><span data-stu-id="06d21-209">-CimSession</span></span>

<span data-ttu-id="06d21-210">Указывает сеанс CIM на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="06d21-210">Specifies a CIM session on the remote computer.</span></span>
<span data-ttu-id="06d21-211">Введите переменную, которая содержит сеанс CIM, или команду, которая получает сеанс CIM, например команду [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) .</span><span class="sxs-lookup"><span data-stu-id="06d21-211">Enter a variable that contains the CIM session or a command that gets the CIM session, such as a [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) command.</span></span>

<span data-ttu-id="06d21-212">`Get-Module` использует соединение с сеансом CIM для получения модулей с удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="06d21-212">`Get-Module` uses the CIM session connection to get modules from the remote computer.</span></span>
<span data-ttu-id="06d21-213">При импорте модуля с помощью `Import-Module` командлета и использовании команд из импортированного модуля в текущем сеансе команды фактически выполняются на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="06d21-213">When you import the module by using the `Import-Module` cmdlet and use the commands from the imported module in the current session, the commands actually run on the remote computer.</span></span>

<span data-ttu-id="06d21-214">Этот параметр можно использовать для получения модулей с компьютеров и устройств, не работающих под управлением операционной системы Windows, а также для компьютеров с PowerShell, на которых не включено удаленное взаимодействие PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06d21-214">You can use this parameter to get modules from computers and devices that are not running the Windows operating system, and computers that have PowerShell, but do not have PowerShell remoting enabled.</span></span>

<span data-ttu-id="06d21-215">Параметр **CimSession** возвращает все модули из сеанса **CIMSession** .</span><span class="sxs-lookup"><span data-stu-id="06d21-215">The **CimSession** parameter gets all modules in the **CIMSession** .</span></span>
<span data-ttu-id="06d21-216">Однако вы можете импортировать только модули CIM и CDXML.</span><span class="sxs-lookup"><span data-stu-id="06d21-216">However, you can import only CIM-based and Cmdlet Definition XML (CDXML)-based modules.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession
Parameter Sets: CimSession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="06d21-217">-FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="06d21-217">-FullyQualifiedName</span></span>

<span data-ttu-id="06d21-218">Указывает имена модулей в форме объектов **ModuleSpecification** .</span><span class="sxs-lookup"><span data-stu-id="06d21-218">Specifies names of modules in the form of **ModuleSpecification** objects.</span></span>
<span data-ttu-id="06d21-219">Эти объекты описаны в разделе "Примечания" [конструктора ModuleSpecification (Hashtable)](https://msdn.microsoft.com/library/jj136290) в библиотеке MSDN.</span><span class="sxs-lookup"><span data-stu-id="06d21-219">These objects are described in the Remarks section of [ModuleSpecification Constructor (Hashtable)](https://msdn.microsoft.com/library/jj136290) in the MSDN library.</span></span>
<span data-ttu-id="06d21-220">Например, параметр **FullyQualifiedName** принимает имя модуля, указанное в следующих форматах:</span><span class="sxs-lookup"><span data-stu-id="06d21-220">For example, the **FullyQualifiedName** parameter accepts a module name that is specified in the following formats:</span></span>

- <span data-ttu-id="06d21-221">@ {ModuleName = "ModuleName"; ", ИД =" version_number "}</span><span class="sxs-lookup"><span data-stu-id="06d21-221">@{ModuleName = "modulename"; ModuleVersion = "version_number"}</span></span>
- <span data-ttu-id="06d21-222">@ {ModuleName = "ModuleName"; "ИД" = "version_number"; GUID = "GUID"}</span><span class="sxs-lookup"><span data-stu-id="06d21-222">@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}</span></span>

<span data-ttu-id="06d21-223">Параметры **ModuleName** и **ModuleVersion** обязательны, а **Guid**  — нет.</span><span class="sxs-lookup"><span data-stu-id="06d21-223">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span>

<span data-ttu-id="06d21-224">Нельзя указать параметр **FullyQualifiedName** в той же команде, что и параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="06d21-224">You cannot specify the **FullyQualifiedName** parameter in the same command as a **Name** parameter.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="06d21-225">-ListAvailable</span><span class="sxs-lookup"><span data-stu-id="06d21-225">-ListAvailable</span></span>

<span data-ttu-id="06d21-226">Указывает, что этот командлет получает все установленные модули.</span><span class="sxs-lookup"><span data-stu-id="06d21-226">Indicates that this cmdlet gets all installed modules.</span></span>
<span data-ttu-id="06d21-227">`Get-Module` Возвращает модули в путях, указанных в переменной среды **PSModulePath** .</span><span class="sxs-lookup"><span data-stu-id="06d21-227">`Get-Module` gets modules in paths listed in the **PSModulePath** environment variable.</span></span>
<span data-ttu-id="06d21-228">Без этого параметра `Get-Module` получает только те модули, которые указаны в переменной среды **PSModulePath** и загружены в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="06d21-228">Without this parameter, `Get-Module` gets only the modules that are both listed in the **PSModulePath** environment variable, and that are loaded in the current session.</span></span>
<span data-ttu-id="06d21-229">Параметр **ListAvailable** не возвращает информацию о модулях, которые не найдены в переменной среды **PSModulePath** , даже если они загружены в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="06d21-229">**ListAvailable** does not return information about modules that are not found in the **PSModulePath** environment variable, even if those modules are loaded in the current session.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Available, PsSession, CimSession
Aliases:

Required: True (Available), False (PsSession, CimSession)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="06d21-230">-Name</span><span class="sxs-lookup"><span data-stu-id="06d21-230">-Name</span></span>

<span data-ttu-id="06d21-231">Указывает имена или шаблоны имен модулей, которые получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="06d21-231">Specifies names or name patterns of modules that this cmdlet gets.</span></span>
<span data-ttu-id="06d21-232">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="06d21-232">Wildcard characters are permitted.</span></span>
<span data-ttu-id="06d21-233">Можно также передать имена в `Get-Module` .</span><span class="sxs-lookup"><span data-stu-id="06d21-233">You can also pipe the names to `Get-Module`.</span></span>
<span data-ttu-id="06d21-234">Нельзя указать параметр **FullyQualifiedName** в той же команде, что и параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="06d21-234">You cannot specify the **FullyQualifiedName** parameter in the same command as a **Name** parameter.</span></span>

<span data-ttu-id="06d21-235">**Имя** не может принимать GUID модуля в качестве значения.</span><span class="sxs-lookup"><span data-stu-id="06d21-235">**Name** cannot accept a module GUID as a value.</span></span>
<span data-ttu-id="06d21-236">Чтобы вернуть модули, указав идентификатор GUID, используйте вместо него **FullyQualifiedName** .</span><span class="sxs-lookup"><span data-stu-id="06d21-236">To return modules by specifying a GUID, use **FullyQualifiedName** instead.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="06d21-237">-PSSession</span><span class="sxs-lookup"><span data-stu-id="06d21-237">-PSSession</span></span>

<span data-ttu-id="06d21-238">Возвращает модули из указанного управляемого пользователем сеанса PowerShell ( **PSSession** ).</span><span class="sxs-lookup"><span data-stu-id="06d21-238">Gets the modules in the specified user-managed PowerShell session ( **PSSession** ).</span></span>
<span data-ttu-id="06d21-239">Введите переменную, которая содержит сеанс, команду, которая получает сеанс, например `Get-PSSession` команду, или команду, которая создает сеанс, например `New-PSSession` команду.</span><span class="sxs-lookup"><span data-stu-id="06d21-239">Enter a variable that contains the session, a command that gets the session, such as a `Get-PSSession` command, or a command that creates the session, such as a `New-PSSession` command.</span></span>

<span data-ttu-id="06d21-240">Если сеанс подключен к удаленному компьютеру, необходимо указать параметр **ListAvailable** .</span><span class="sxs-lookup"><span data-stu-id="06d21-240">When the session is connected to a remote computer, you must specify the **ListAvailable** parameter.</span></span>

<span data-ttu-id="06d21-241">`Get-Module`Команда, использующая параметр **PSSession** , эквивалентна использованию `Invoke-Command` командлета для выполнения `Get-Module -ListAvailable` команды в **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="06d21-241">A `Get-Module` command that uses the **PSSession** parameter is equivalent to using the `Invoke-Command` cmdlet to run a `Get-Module -ListAvailable` command in a **PSSession** .</span></span>

<span data-ttu-id="06d21-242">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="06d21-242">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: PsSession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="06d21-243">-Refresh</span><span class="sxs-lookup"><span data-stu-id="06d21-243">-Refresh</span></span>

<span data-ttu-id="06d21-244">Указывает, что этот командлет обновляет кэш установленных команд.</span><span class="sxs-lookup"><span data-stu-id="06d21-244">Indicates that this cmdlet refreshes the cache of installed commands.</span></span>
<span data-ttu-id="06d21-245">Кэш команд создается при запуске сеанса.</span><span class="sxs-lookup"><span data-stu-id="06d21-245">The command cache is created when the session starts.</span></span>
<span data-ttu-id="06d21-246">Он позволяет `Get-Command` командлету получать команды из модулей, которые не импортируются в сеанс.</span><span class="sxs-lookup"><span data-stu-id="06d21-246">It enables the `Get-Command` cmdlet to get commands from modules that are not imported into the session.</span></span>

<span data-ttu-id="06d21-247">Этот параметр предназначен для сценариев разработки и тестирования, в которых содержимое модулей меняется с момента начала сеанса.</span><span class="sxs-lookup"><span data-stu-id="06d21-247">This parameter is designed for development and testing scenarios in which the contents of modules have changed since the session started.</span></span>

<span data-ttu-id="06d21-248">При указании параметра **Refresh** в команде необходимо указать **ListAvailable** .</span><span class="sxs-lookup"><span data-stu-id="06d21-248">When you specify the **Refresh** parameter in a command, you must specify **ListAvailable** .</span></span>

<span data-ttu-id="06d21-249">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="06d21-249">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Available, PsSession, CimSession
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="06d21-250">-PSEdition</span><span class="sxs-lookup"><span data-stu-id="06d21-250">-PSEdition</span></span>

<span data-ttu-id="06d21-251">Возвращает модули, поддерживающие указанный выпуск PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06d21-251">Gets the modules that support specified edition of PowerShell.</span></span>

<span data-ttu-id="06d21-252">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="06d21-252">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="06d21-253">Классические приложения</span><span class="sxs-lookup"><span data-stu-id="06d21-253">Desktop</span></span>
- <span data-ttu-id="06d21-254">Основные сведения</span><span class="sxs-lookup"><span data-stu-id="06d21-254">Core</span></span>

<span data-ttu-id="06d21-255">Командлет Get-Module проверяет свойство **CompatiblePSEditions** объекта **PSModuleInfo** на указанное значение и возвращает только те модули, для которых он задан.</span><span class="sxs-lookup"><span data-stu-id="06d21-255">The Get-Module cmdlet checks **CompatiblePSEditions** property of **PSModuleInfo** object for the specified value and returns only those modules that have it set.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="06d21-256">**Настольный выпуск:** Сборка на основе .NET Framework применяется к Windows PowerShell 5,1 и ниже в большинстве выпусков Windows.</span><span class="sxs-lookup"><span data-stu-id="06d21-256">**Desktop Edition:** Built on .NET Framework, applies to Windows PowerShell 5.1 and below on most Windows editions.</span></span>
> - <span data-ttu-id="06d21-257">**Выпуск Core:** Основано на .NET Core, применяется к PowerShell Core 6,0 и более поздним версиям, а также к некоторым выпускам Windows PowerShell 5,1, созданным для Windows IoT и Windows Server.</span><span class="sxs-lookup"><span data-stu-id="06d21-257">**Core Edition:** Built on .NET Core, applies to PowerShell Core 6.0 and above, as well as some editions of Windows PowerShell 5.1 built for Windows IoT and Windows Nanoserver.</span></span> <span data-ttu-id="06d21-258">> выпуск текущего сеанса PowerShell можно найти с помощью `$PSEdition` переменной.</span><span class="sxs-lookup"><span data-stu-id="06d21-258">> The edition of the current PowerShell session can be found with the `$PSEdition` variable.</span></span>

```yaml
Type: System.String
Parameter Sets: Available, PsSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="06d21-259">-Скипедитиончекк</span><span class="sxs-lookup"><span data-stu-id="06d21-259">-SkipEditionCheck</span></span>

<span data-ttu-id="06d21-260">Пропускает проверку `CompatiblePSEditions` поля.</span><span class="sxs-lookup"><span data-stu-id="06d21-260">Skips the check of the `CompatiblePSEditions` field.</span></span>

<span data-ttu-id="06d21-261">По умолчанию Get-Module будет опускать модули в `%windir%\System32\WindowsPowerShell\v1.0\Modules` каталоге, не указанные `Core` в `CompatiblePSEditions` поле.</span><span class="sxs-lookup"><span data-stu-id="06d21-261">By default, Get-Module will omit modules in the `%windir%\System32\WindowsPowerShell\v1.0\Modules` directory that do not specify `Core` in the `CompatiblePSEditions` field.</span></span>
<span data-ttu-id="06d21-262">Если этот параметр задан, то модули без `Core` будут включены, поэтому будут возвращены модули в пути модуля Windows PowerShell, несовместимые с PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="06d21-262">When this switch is set, modules without `Core` will be included, so that modules under the Windows PowerShell module path that are incompatible with PowerShell Core will be returned.</span></span>

<span data-ttu-id="06d21-263">В macOS и Linux этот параметр не выполняет никаких действий.</span><span class="sxs-lookup"><span data-stu-id="06d21-263">On macOS and Linux, this parameter does nothing.</span></span>

<span data-ttu-id="06d21-264">Дополнительные сведения см. в разделе [about_PowerShell_Editions](About/about_PowerShell_Editions.md) .</span><span class="sxs-lookup"><span data-stu-id="06d21-264">See [about_PowerShell_Editions](About/about_PowerShell_Editions.md) for more information.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Available, PsSession, CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="06d21-265">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="06d21-265">CommonParameters</span></span>

<span data-ttu-id="06d21-266">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="06d21-266">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="06d21-267">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="06d21-267">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="06d21-268">Входные данные</span><span class="sxs-lookup"><span data-stu-id="06d21-268">INPUTS</span></span>

### <span data-ttu-id="06d21-269">System.String</span><span class="sxs-lookup"><span data-stu-id="06d21-269">System.String</span></span>

<span data-ttu-id="06d21-270">В этот командлет можно передать имена модулей.</span><span class="sxs-lookup"><span data-stu-id="06d21-270">You can pipe module names to this cmdlet.</span></span>

## <span data-ttu-id="06d21-271">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="06d21-271">OUTPUTS</span></span>

### <span data-ttu-id="06d21-272">System.Management.Automation.PSModuleInfo</span><span class="sxs-lookup"><span data-stu-id="06d21-272">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="06d21-273">Этот командлет возвращает объекты, представляющие модули.</span><span class="sxs-lookup"><span data-stu-id="06d21-273">This cmdlet returns objects that represent modules.</span></span>
<span data-ttu-id="06d21-274">При указании параметра **ListAvailable** `Get-Module` возвращает объект **модулеинфограупинг** , который является типом объекта **PSModuleInfo** , который имеет те же свойства и методы.</span><span class="sxs-lookup"><span data-stu-id="06d21-274">When you specify the **ListAvailable** parameter, `Get-Module` returns a **ModuleInfoGrouping** object, which is a type of **PSModuleInfo** object that has the same properties and methods.</span></span>

## <span data-ttu-id="06d21-275">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="06d21-275">NOTES</span></span>

- <span data-ttu-id="06d21-276">Начиная с Windows PowerShell 3,0, основные команды, входящие в PowerShell, упаковываются в модули.</span><span class="sxs-lookup"><span data-stu-id="06d21-276">Beginning in Windows PowerShell 3.0, the core commands that are included in PowerShell are packaged in modules.</span></span> <span data-ttu-id="06d21-277">Исключением является **Microsoft. PowerShell. Core** — оснастка ( **PSSnapin** ).</span><span class="sxs-lookup"><span data-stu-id="06d21-277">The exception is **Microsoft.PowerShell.Core** , which is a snap-in ( **PSSnapin** ).</span></span> <span data-ttu-id="06d21-278">По умолчанию в сеанс добавляется только оснастка **Microsoft.PowerShell.Core** .</span><span class="sxs-lookup"><span data-stu-id="06d21-278">By default, only the **Microsoft.PowerShell.Core** snap-in is added to the session.</span></span>
<span data-ttu-id="06d21-279">Модули импортируются автоматически при первом использовании `Import-Module` . для их импорта можно использовать командлет.</span><span class="sxs-lookup"><span data-stu-id="06d21-279">Modules are imported automatically on first use and you can use the `Import-Module` cmdlet to import them.</span></span>
- <span data-ttu-id="06d21-280">Начиная с Windows PowerShell 3,0, основные команды, устанавливаемые с помощью PowerShell, упаковываются в модули.</span><span class="sxs-lookup"><span data-stu-id="06d21-280">Starting in Windows PowerShell 3.0, the core commands that are installed with PowerShell are packaged in modules.</span></span> <span data-ttu-id="06d21-281">В Windows PowerShell 2,0 и в ведущих программах, которые создают сеансы предыдущих версий в более поздних версиях PowerShell, основные команды упаковываются в оснастки ( **PSSnapin** ).</span><span class="sxs-lookup"><span data-stu-id="06d21-281">In Windows PowerShell 2.0, and in host programs that create older-style sessions in later versions of PowerShell, the core commands are packaged in snap-ins ( **PSSnapins** ).</span></span> <span data-ttu-id="06d21-282">Исключением является **Microsoft. PowerShell. Core** , который всегда является оснасткой.</span><span class="sxs-lookup"><span data-stu-id="06d21-282">The exception is **Microsoft.PowerShell.Core** , which is always a snap-in.</span></span> <span data-ttu-id="06d21-283">Кроме того, удаленные сеансы, такие как запущенные `New-PSSession` командлетом, являются сеансами предыдущих версий, включающими основные оснастки.</span><span class="sxs-lookup"><span data-stu-id="06d21-283">Also, remote sessions, such as those started by the `New-PSSession` cmdlet, are older-style sessions that include core snap-ins.</span></span>

  <span data-ttu-id="06d21-284">Дополнительные сведения о методе **CreateDefault2** , который создает сеансы более новых версий с основными модулями, см. в разделе [метод CREATEDEFAULT2](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2) в библиотеке MSDN.</span><span class="sxs-lookup"><span data-stu-id="06d21-284">For information about the **CreateDefault2** method that creates newer-style sessions with core modules, see [CreateDefault2 Method](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2) in the MSDN library.</span></span>

- <span data-ttu-id="06d21-285">`Get-Module` только возвращает модули в расположениях, которые хранятся в значении переменной среды **PSModulePath** ($env:P смодулепас).</span><span class="sxs-lookup"><span data-stu-id="06d21-285">`Get-Module` only gets modules in locations that are stored in the value of the **PSModulePath** environment variable ($env:PSModulePath).</span></span> <span data-ttu-id="06d21-286">Параметр **path** `Import-Module` командлета можно использовать для импорта модулей в других местах, однако `Get-Module` для их получения нельзя использовать командлет.</span><span class="sxs-lookup"><span data-stu-id="06d21-286">You can use the **Path** parameter of the `Import-Module` cmdlet to import modules in other locations, but you cannot use the `Get-Module` cmdlet to get them.</span></span>
- <span data-ttu-id="06d21-287">Кроме того, начиная с PowerShell 3,0 в объект, который возвращает, были добавлены новые свойства, `Get-Module` которые упрощают изучение модулей даже перед их импортом.</span><span class="sxs-lookup"><span data-stu-id="06d21-287">Also, starting in PowerShell 3.0, new properties have been added to the object that `Get-Module` returns that make it easier to learn about modules even before they are imported.</span></span> <span data-ttu-id="06d21-288">Все свойства заполняются перед импортом.</span><span class="sxs-lookup"><span data-stu-id="06d21-288">All properties are populated before importing.</span></span> <span data-ttu-id="06d21-289">К ним относятся свойства **ExportedCommands** , **експортедкмдлетс** и **експортедфунктионс** , в которых перечислены команды, экспортируемые модулем.</span><span class="sxs-lookup"><span data-stu-id="06d21-289">These include the **ExportedCommands** , **ExportedCmdlets** and **ExportedFunctions** properties that list the commands that the module exports.</span></span>
- <span data-ttu-id="06d21-290">Параметр **ListAvailable** возвращает только модули с правильным форматом, то есть папки, содержащие по крайней мере один файл, базовое имя которого совпадает с именем папки модуля.</span><span class="sxs-lookup"><span data-stu-id="06d21-290">The **ListAvailable** parameter gets only well-formed modules, that is, folders that contain at least one file whose base name is the same as the name of the module folder.</span></span> <span data-ttu-id="06d21-291">Базовое имя — это имя без расширения имени файла.</span><span class="sxs-lookup"><span data-stu-id="06d21-291">The base name is the name without the file name extension.</span></span> <span data-ttu-id="06d21-292">Папки, содержащие файлы с разными именами, считаются контейнерами, но не модулями.</span><span class="sxs-lookup"><span data-stu-id="06d21-292">Folders that contain files that have different names are considered to be containers, but not modules.</span></span>

  <span data-ttu-id="06d21-293">Для получения модулей, которые реализуются в виде DLL-файлов, но не заключаются в папку модуля, укажите оба параметра: **ListAvailable** и **ALL** .</span><span class="sxs-lookup"><span data-stu-id="06d21-293">To get modules that are implemented as .dll files, but are not enclosed in a module folder, specify both the **ListAvailable** and **All** parameters.</span></span>

- <span data-ttu-id="06d21-294">Для использования функции сеанса CIM на удаленном компьютере должен быть установлен компонент удаленного взаимодействия WS-Management и инструментарий управления Windows (WMI), который представляет собой реализацию стандарта CIM корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="06d21-294">To use the CIM session feature, the remote computer must have WS-Management remoting and Windows Management Instrumentation (WMI), which is the Microsoft implementation of the Common Information Model (CIM) standard.</span></span> <span data-ttu-id="06d21-295">На компьютере должен быть также поставщик WMI обнаружения модулей или другой поставщик WMI с теми же основными возможностями.</span><span class="sxs-lookup"><span data-stu-id="06d21-295">The computer must also have the Module Discovery WMI provider or an alternate WMI provider that has the same basic features.</span></span>

  <span data-ttu-id="06d21-296">Можно использовать сеанс CIM на компьютерах, на которых не установлена операционная система Windows и на компьютерах Windows с PowerShell, но удаленное взаимодействие PowerShell не включено.</span><span class="sxs-lookup"><span data-stu-id="06d21-296">You can use the CIM session feature on computers that are not running the Windows operating system and on Windows computers that have PowerShell, but do not have PowerShell remoting enabled.</span></span>

  <span data-ttu-id="06d21-297">Можно также использовать параметры CIM для получения модулей CIM с компьютеров, на которых включено удаленное взаимодействие PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06d21-297">You can also use the CIM parameters to get CIM modules from computers that have PowerShell remoting enabled.</span></span> <span data-ttu-id="06d21-298">Сюда входит локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="06d21-298">This includes the local computer.</span></span>
<span data-ttu-id="06d21-299">При создании сеанса CIM на локальном компьютере для создания сеанса в PowerShell используется DCOM, а не WMI.</span><span class="sxs-lookup"><span data-stu-id="06d21-299">When you create a CIM session on the local computer, PowerShell uses DCOM, instead of WMI, to create the session.</span></span>

## <span data-ttu-id="06d21-300">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="06d21-300">RELATED LINKS</span></span>

[<span data-ttu-id="06d21-301">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="06d21-301">Get-CimSession</span></span>](../CimCmdlets/Get-CimSession.md)

[<span data-ttu-id="06d21-302">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="06d21-302">New-CimSession</span></span>](../CimCmdlets/New-CimSession.md)

[<span data-ttu-id="06d21-303">about_Modules</span><span class="sxs-lookup"><span data-stu-id="06d21-303">about_Modules</span></span>](About/about_Modules.md)

[<span data-ttu-id="06d21-304">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="06d21-304">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="06d21-305">Import-Module</span><span class="sxs-lookup"><span data-stu-id="06d21-305">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="06d21-306">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="06d21-306">Import-PSSession</span></span>](../Microsoft.PowerShell.Utility/Import-PSSession.md)

[<span data-ttu-id="06d21-307">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="06d21-307">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="06d21-308">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="06d21-308">Remove-Module</span></span>](Remove-Module.md)

[<span data-ttu-id="06d21-309">about_PowerShell_Editions</span><span class="sxs-lookup"><span data-stu-id="06d21-309">about_PowerShell_Editions</span></span>](About/about_PowerShell_Editions.md)
