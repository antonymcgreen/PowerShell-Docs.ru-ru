---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-module?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Module
ms.openlocfilehash: 1f06d1e7114a84ea89097167b188ded605f81aa0
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2020
ms.locfileid: "96564543"
---
# <span data-ttu-id="f5b17-102">Get-Module</span><span class="sxs-lookup"><span data-stu-id="f5b17-102">Get-Module</span></span>

## <span data-ttu-id="f5b17-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="f5b17-103">SYNOPSIS</span></span>
<span data-ttu-id="f5b17-104">Выводит список модулей, импортированных в текущем сеансе или импортируемых из PSModulePath.</span><span class="sxs-lookup"><span data-stu-id="f5b17-104">List the modules imported in the current session or that can be imported from the PSModulePath.</span></span>

## <span data-ttu-id="f5b17-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f5b17-105">SYNTAX</span></span>

### <span data-ttu-id="f5b17-106">Загружено (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="f5b17-106">Loaded (Default)</span></span>

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-All] [<CommonParameters>]
```

### <span data-ttu-id="f5b17-107">Доступно</span><span class="sxs-lookup"><span data-stu-id="f5b17-107">Available</span></span>

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-All] [-ListAvailable]
 [-PSEdition <String>] [-SkipEditionCheck] [-Refresh] [<CommonParameters>]
```

### <span data-ttu-id="f5b17-108">PsSession</span><span class="sxs-lookup"><span data-stu-id="f5b17-108">PsSession</span></span>

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-ListAvailable]
 [-PSEdition <String>] [-SkipEditionCheck] [-Refresh] -PSSession <PSSession> [<CommonParameters>]
```

### <span data-ttu-id="f5b17-109">CimSession</span><span class="sxs-lookup"><span data-stu-id="f5b17-109">CimSession</span></span>

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-ListAvailable]
 [-SkipEditionCheck] [-Refresh] -CimSession <CimSession> [-CimResourceUri <Uri>] [-CimNamespace <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="f5b17-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f5b17-110">DESCRIPTION</span></span>

<span data-ttu-id="f5b17-111">`Get-Module`Командлет перечисляет модули PowerShell, которые были импортированы или могут быть импортированы, в сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f5b17-111">The `Get-Module` cmdlet lists the PowerShell modules that have been imported, or that can be imported, into a PowerShell session.</span></span> <span data-ttu-id="f5b17-112">Без параметров `Get-Module` возвращает модули, которые были импортированы в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="f5b17-112">Without parameters, `Get-Module` gets modules that have been imported into the current session.</span></span> <span data-ttu-id="f5b17-113">Параметр **ListAvailable** используется для перечисления модулей, доступных для импорта из путей, указанных в переменной среды PSModulePath ( `$env:PSModulePath` ).</span><span class="sxs-lookup"><span data-stu-id="f5b17-113">The **ListAvailable** parameter is used to list the modules that are available to be imported from the paths specified in the PSModulePath environment variable (`$env:PSModulePath`).</span></span>

<span data-ttu-id="f5b17-114">Объект модуля, который `Get-Module` возвращает, содержит ценные сведения о модуле.</span><span class="sxs-lookup"><span data-stu-id="f5b17-114">The module object that `Get-Module` returns contains valuable information about the module.</span></span> <span data-ttu-id="f5b17-115">Можно также передать объекты модуля в другие командлеты, такие как `Import-Module` `Remove-Module` командлеты и.</span><span class="sxs-lookup"><span data-stu-id="f5b17-115">You can also pipe the module objects to other cmdlets, such as the `Import-Module` and `Remove-Module` cmdlets.</span></span>

<span data-ttu-id="f5b17-116">`Get-Module` Выводит список модулей, но не импортирует их.</span><span class="sxs-lookup"><span data-stu-id="f5b17-116">`Get-Module` lists modules, but it does not import them.</span></span> <span data-ttu-id="f5b17-117">Начиная с Windows PowerShell 3,0 модули автоматически импортируются при использовании команды в модуле, но `Get-Module` команда не запускает автоматический импорт.</span><span class="sxs-lookup"><span data-stu-id="f5b17-117">Starting in Windows PowerShell 3.0, modules are automatically imported when you use a command in the module, but a `Get-Module` command does not trigger an automatic import.</span></span> <span data-ttu-id="f5b17-118">Вы также можете импортировать модули в сеанс с помощью `Import-Module` командлета.</span><span class="sxs-lookup"><span data-stu-id="f5b17-118">You can also import the modules into your session using the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="f5b17-119">Начиная с Windows PowerShell 3,0, вы можете получить и импортировать модули из удаленных сеансов в локальный сеанс.</span><span class="sxs-lookup"><span data-stu-id="f5b17-119">Starting in Windows PowerShell 3.0, you can get and then, import modules from remote sessions into the local session.</span></span> <span data-ttu-id="f5b17-120">Эта стратегия использует функцию неявного удаленного взаимодействия PowerShell и эквивалентна использованию `Import-PSSession` командлета.</span><span class="sxs-lookup"><span data-stu-id="f5b17-120">This strategy uses the Implicit Remoting feature of PowerShell and is equivalent to using the `Import-PSSession` cmdlet.</span></span> <span data-ttu-id="f5b17-121">При использовании команд в модулях, импортированных из другого сеанса, команды выполняются неявно в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="f5b17-121">When you use commands in modules imported from another session, the commands run implicitly in the remote session.</span></span> <span data-ttu-id="f5b17-122">Эта функция позволяет управлять удаленным компьютером из локального сеанса.</span><span class="sxs-lookup"><span data-stu-id="f5b17-122">This feature lets you manage the remote computer from the local session.</span></span>

<span data-ttu-id="f5b17-123">Кроме того, начиная с Windows PowerShell 3,0, вы можете использовать `Get-Module` и `Import-Module` для получения и импорта модулей модель CIM (CIM).</span><span class="sxs-lookup"><span data-stu-id="f5b17-123">Also, starting in Windows PowerShell 3.0, you can use `Get-Module` and `Import-Module` to get and import Common Information Model (CIM) modules.</span></span> <span data-ttu-id="f5b17-124">Модули CIM определяют командлеты в файлах XML определения командлетов (CDXML).</span><span class="sxs-lookup"><span data-stu-id="f5b17-124">CIM modules define cmdlets in Cmdlet Definition XML (CDXML) files.</span></span> <span data-ttu-id="f5b17-125">Эта функция позволяет использовать командлеты, реализованные в неуправляемых сборках кода, таких как написанные на C++.</span><span class="sxs-lookup"><span data-stu-id="f5b17-125">This feature lets you use cmdlets that are implemented in non-managed code assemblies, such as those written in C++.</span></span>

<span data-ttu-id="f5b17-126">Неявное удаленное взаимодействие можно использовать для управления удаленными компьютерами, на которых включено удаленное взаимодействие PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f5b17-126">Implicit remoting can be used to manage remote computers that have PowerShell remoting enabled.</span></span>
<span data-ttu-id="f5b17-127">Создайте сеанс **PSSession** на удаленном компьютере, а затем используйте параметр **PSSession** , `Get-Module` чтобы получить модули PowerShell в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="f5b17-127">Create a **PSSession** on the remote computer and then use the **PSSession** parameter of `Get-Module` to get the PowerShell modules in the remote session.</span></span> <span data-ttu-id="f5b17-128">При импорте модуля из удаленного сеанса импортированные команды выполняются в сеансе на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="f5b17-128">When you import a module from the remote session the imported commands run in the session on the remote computer.</span></span>

<span data-ttu-id="f5b17-129">Аналогичную стратегию можно использовать для управления компьютерами, на которых не включено удаленное взаимодействие PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f5b17-129">You can use a similar strategy to manage computers that do not have PowerShell remoting enabled.</span></span>
<span data-ttu-id="f5b17-130">К ним относятся компьютеры, на которых не установлена операционная система Windows, а также компьютеры с PowerShell, для которых не включено удаленное взаимодействие PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f5b17-130">These include computers that are not running the Windows operating system, and computers that have PowerShell but do not have PowerShell remoting enabled.</span></span>

<span data-ttu-id="f5b17-131">Начните с создания сеанса CIM на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="f5b17-131">Start by creating a CIM session on the remote computer.</span></span> <span data-ttu-id="f5b17-132">Сеанс CIM — это подключение к инструментарий управления Windows (WMI) (WMI) на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="f5b17-132">A CIM session is a connection to Windows Management Instrumentation (WMI) on the remote computer.</span></span> <span data-ttu-id="f5b17-133">Затем используйте параметр **CIMSession** параметра, `Get-Module` чтобы получить модули CIM из сеанса CIM.</span><span class="sxs-lookup"><span data-stu-id="f5b17-133">Then use the **CIMSession** parameter of `Get-Module` to get CIM modules from the CIM session.</span></span> <span data-ttu-id="f5b17-134">При импорте модуля CIM с помощью `Import-Module` командлета и последующем выполнении импортированных команд команды выполняются неявно на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="f5b17-134">When you import a CIM module by using the `Import-Module` cmdlet and then run the imported commands, the commands run implicitly on the remote computer.</span></span> <span data-ttu-id="f5b17-135">С помощью этой стратегии, предполагающей использование инструментария WMI и модели CIM, можно управлять удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="f5b17-135">You can use this WMI and CIM strategy to manage the remote computer.</span></span>

## <span data-ttu-id="f5b17-136">Примеры</span><span class="sxs-lookup"><span data-stu-id="f5b17-136">EXAMPLES</span></span>

### <span data-ttu-id="f5b17-137">Пример 1. получение модулей, импортированных в текущий сеанс</span><span class="sxs-lookup"><span data-stu-id="f5b17-137">Example 1: Get modules imported into the current session</span></span>

```powershell
Get-Module
```

<span data-ttu-id="f5b17-138">Эта команда возвращает модули, которые были импортированы в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="f5b17-138">This command gets modules that have been imported into the current session.</span></span>

### <span data-ttu-id="f5b17-139">Пример 2. Получение установленных модулей и доступных модулей</span><span class="sxs-lookup"><span data-stu-id="f5b17-139">Example 2: Get installed modules and available modules</span></span>

```powershell
Get-Module -ListAvailable
```

<span data-ttu-id="f5b17-140">Эта команда возвращает модули, которые установлены на компьютере и могут быть импортированы в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="f5b17-140">This command gets the modules that are installed on the computer and can be imported into the current session.</span></span>

<span data-ttu-id="f5b17-141">`Get-Module` ищет доступные модули по пути, указанному в переменной среды **$env:P смодулепас** .</span><span class="sxs-lookup"><span data-stu-id="f5b17-141">`Get-Module` looks for available modules in the path specified by the **$env:PSModulePath** environment variable.</span></span> <span data-ttu-id="f5b17-142">Подробнее о переменной среды **PSModulePath**, см. в разделах [about_Modules](About/about_Modules.md) и [about_Environment_Variables](About/about_Environment_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="f5b17-142">For more information about **PSModulePath**, see [about_Modules](About/about_Modules.md) and [about_Environment_Variables](About/about_Environment_Variables.md).</span></span>

### <span data-ttu-id="f5b17-143">Пример 3. получение всех экспортированных файлов</span><span class="sxs-lookup"><span data-stu-id="f5b17-143">Example 3: Get all exported files</span></span>

```powershell
Get-Module -ListAvailable -All
```

<span data-ttu-id="f5b17-144">Эта команда возвращает все экспортированные файлы для всех доступных модулей.</span><span class="sxs-lookup"><span data-stu-id="f5b17-144">This command gets all of the exported files for all available modules.</span></span>

### <span data-ttu-id="f5b17-145">Пример 4. Получение модуля по его полному имени</span><span class="sxs-lookup"><span data-stu-id="f5b17-145">Example 4: Get a module by its fully qualified name</span></span>

```powershell
$FullyQualifedName = @{ModuleName="Microsoft.PowerShell.Management";ModuleVersion="3.1.0.0"}
Get-Module -FullyQualifiedName $FullyQualifedName | Format-Table -Property Name,Version
```

```Output
Name                             Version
----                             -------
Microsoft.PowerShell.Management  3.1.0.0
```

<span data-ttu-id="f5b17-146">Эта команда получает модуль **Microsoft. PowerShell. Management** , указывая полное имя модуля с помощью параметра **FullyQualifiedName** .</span><span class="sxs-lookup"><span data-stu-id="f5b17-146">This command gets the **Microsoft.PowerShell.Management** module by specifying the fully qualified name of the module by using the **FullyQualifiedName** parameter.</span></span> <span data-ttu-id="f5b17-147">Затем команда передает результаты в `Format-Table` командлет, чтобы отформатировать результаты в виде таблицы с **именами** и **версиями** в качестве заголовков столбцов.</span><span class="sxs-lookup"><span data-stu-id="f5b17-147">The command then pipes the results into the `Format-Table` cmdlet to format the results as a table with **Name** and **Version** as the column headings.</span></span>

### <span data-ttu-id="f5b17-148">Пример 5. получение свойств модуля</span><span class="sxs-lookup"><span data-stu-id="f5b17-148">Example 5: Get properties of a module</span></span>

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

<span data-ttu-id="f5b17-149">Эта команда возвращает свойства объекта **PSModuleInfo** , который `Get-Module` возвращает.</span><span class="sxs-lookup"><span data-stu-id="f5b17-149">This command gets the properties of the **PSModuleInfo** object that `Get-Module` returns.</span></span> <span data-ttu-id="f5b17-150">Для каждого файла модуля имеется один объект.</span><span class="sxs-lookup"><span data-stu-id="f5b17-150">There is one object for each module file.</span></span>

<span data-ttu-id="f5b17-151">С помощью свойств можно форматировать и фильтровать объекты модулей.</span><span class="sxs-lookup"><span data-stu-id="f5b17-151">You can use the properties to format and filter the module objects.</span></span> <span data-ttu-id="f5b17-152">Дополнительные сведения о свойствах см. в разделе [Свойства PSModuleInfo](/dotnet/api/system.management.automation.psmoduleinfo).</span><span class="sxs-lookup"><span data-stu-id="f5b17-152">For more information about the properties, see [PSModuleInfo Properties](/dotnet/api/system.management.automation.psmoduleinfo).</span></span>

<span data-ttu-id="f5b17-153">Выходные данные включают новые свойства, такие как **Author** и **CompanyName**, которые появились в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="f5b17-153">The output includes the new properties, such as **Author** and **CompanyName**, that were introduced in Windows PowerShell 3.0.</span></span>

### <span data-ttu-id="f5b17-154">Пример 6. Группировка всех модулей по имени</span><span class="sxs-lookup"><span data-stu-id="f5b17-154">Example 6: Group all modules by name</span></span>

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

<span data-ttu-id="f5b17-155">Эта команда возвращает все файлы модулей, импортированные и доступные, а затем группирует их по имени модуля.</span><span class="sxs-lookup"><span data-stu-id="f5b17-155">This command gets all module files, both imported and available, and then groups them by module name.</span></span> <span data-ttu-id="f5b17-156">Это позволяет увидеть, какие файлы модулей экспортирует каждый сценарий.</span><span class="sxs-lookup"><span data-stu-id="f5b17-156">This lets you see the module files that each script is exporting.</span></span>

### <span data-ttu-id="f5b17-157">Пример 7. Отображение содержимого манифеста модуля</span><span class="sxs-lookup"><span data-stu-id="f5b17-157">Example 7: Display the contents of a module manifest</span></span>

<span data-ttu-id="f5b17-158">Эти команды отображают содержимое манифеста модуля для модуля **BitsTransfer** Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f5b17-158">These commands display the contents of the module manifest for the Windows PowerShell **BitsTransfer** module.</span></span>

<span data-ttu-id="f5b17-159">Модули не обязательно должны иметь файлы манифеста.</span><span class="sxs-lookup"><span data-stu-id="f5b17-159">Modules are not required to have manifest files.</span></span> <span data-ttu-id="f5b17-160">Если у них есть файл манифеста, файл манифеста требуется только для включения номера версии.</span><span class="sxs-lookup"><span data-stu-id="f5b17-160">When they do have a manifest file, the manifest file is required only to include a version number.</span></span> <span data-ttu-id="f5b17-161">Однако файлы манифестов часто предоставляют полезную информацию о модуле, его требованиях и содержимом.</span><span class="sxs-lookup"><span data-stu-id="f5b17-161">However, manifest files often provide useful information about a module, its requirements, and its contents.</span></span>

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

<span data-ttu-id="f5b17-162">Первая команда возвращает объект PSModuleInfo, который представляет модуль BitsTransfer.</span><span class="sxs-lookup"><span data-stu-id="f5b17-162">The first command gets the PSModuleInfo object that represents BitsTransfer module.</span></span> <span data-ttu-id="f5b17-163">Объект сохраняется в `$m` переменной.</span><span class="sxs-lookup"><span data-stu-id="f5b17-163">It saves the object in the `$m` variable.</span></span>

<span data-ttu-id="f5b17-164">Вторая команда использует `Get-Content` командлет для получения содержимого файла манифеста по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="f5b17-164">The second command uses the `Get-Content` cmdlet to get the content of the manifest file in the specified path.</span></span> <span data-ttu-id="f5b17-165">В ней используется нотация с точками для получения пути к файлу манифеста, который хранится в свойстве Path объекта.</span><span class="sxs-lookup"><span data-stu-id="f5b17-165">It uses dot notation to get the path to the manifest file, which is stored in the Path property of the object.</span></span> <span data-ttu-id="f5b17-166">В выходных данных показано содержимое манифеста модуля.</span><span class="sxs-lookup"><span data-stu-id="f5b17-166">The output shows the contents of the module manifest.</span></span>

### <span data-ttu-id="f5b17-167">Пример 8. Вывод списка файлов в каталоге Module</span><span class="sxs-lookup"><span data-stu-id="f5b17-167">Example 8: List files in module directory</span></span>

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

<span data-ttu-id="f5b17-168">Эта команда выводит список файлов в каталоге модуля.</span><span class="sxs-lookup"><span data-stu-id="f5b17-168">This command lists the files in the directory of the module.</span></span> <span data-ttu-id="f5b17-169">Это еще один способ определить, что входит в модуль, перед его импортом.</span><span class="sxs-lookup"><span data-stu-id="f5b17-169">This is another way to determine what is in a module before you import it.</span></span> <span data-ttu-id="f5b17-170">Некоторые модули могут иметь файлы справки или файлы ReadMe, в которых описывается модуль.</span><span class="sxs-lookup"><span data-stu-id="f5b17-170">Some modules might have help files or ReadMe files that describe the module.</span></span>

### <span data-ttu-id="f5b17-171">Пример 9. получение модулей, установленных на компьютере</span><span class="sxs-lookup"><span data-stu-id="f5b17-171">Example 9: Get modules installed on a computer</span></span>

```powershell
$s = New-PSSession -ComputerName Server01

Get-Module -PSSession $s -ListAvailable
```

<span data-ttu-id="f5b17-172">Эти команды возвращают модули, которые установлены на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="f5b17-172">These commands get the modules that are installed on the Server01 computer.</span></span>

<span data-ttu-id="f5b17-173">Первая команда использует `New-PSSession` командлет для создания **сеанса PSSession** на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="f5b17-173">The first command uses the `New-PSSession` cmdlet to create a **PSSession** on the Server01 computer.</span></span> <span data-ttu-id="f5b17-174">Команда сохраняет **PSSession** в переменной $s.</span><span class="sxs-lookup"><span data-stu-id="f5b17-174">The command saves the **PSSession** in the $s variable.</span></span>

<span data-ttu-id="f5b17-175">Вторая команда использует параметры **PSSession** и **ListAvailable** `Get-Module` для получения модулей в **PSSession** в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="f5b17-175">The second command uses the **PSSession** and **ListAvailable** parameters of `Get-Module` to get the modules in the **PSSession** in the `$s` variable.</span></span>

<span data-ttu-id="f5b17-176">При передаче модулей из других сеансов в `Import-Module` командлет `Import-Module` импортирует модуль в текущий сеанс с помощью функции неявного удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="f5b17-176">If you pipe modules from other sessions to the `Import-Module` cmdlet, `Import-Module` imports the module into the current session by using the implicit remoting feature.</span></span> <span data-ttu-id="f5b17-177">Это эквивалентно использованию `Import-PSSession` командлета.</span><span class="sxs-lookup"><span data-stu-id="f5b17-177">This is equivalent to using the `Import-PSSession` cmdlet.</span></span> <span data-ttu-id="f5b17-178">Вы можете использовать командлеты из модуля в рамках текущего сеанса, но команды, использующие эти командлеты, на самом деле выполняются в рамках удаленного сеанса.</span><span class="sxs-lookup"><span data-stu-id="f5b17-178">You can use the cmdlets from the module in the current session, but commands that use these cmdlets actually run the remote session.</span></span> <span data-ttu-id="f5b17-179">Дополнительные сведения см. в разделах [`Import-Module`](Import-Module.md) и [`Import-PSSession`](../Microsoft.PowerShell.Utility/Import-PSSession.md).</span><span class="sxs-lookup"><span data-stu-id="f5b17-179">For more information, see [`Import-Module`](Import-Module.md) and [`Import-PSSession`](../Microsoft.PowerShell.Utility/Import-PSSession.md).</span></span>

### <span data-ttu-id="f5b17-180">Пример 10. Управление компьютером, на котором не выполняется операционная система Windows</span><span class="sxs-lookup"><span data-stu-id="f5b17-180">Example 10: Manage a computer that does not run the Windows operating system</span></span>

<span data-ttu-id="f5b17-181">Команды в этом примере позволяют управлять системами хранения на удаленном компьютере, на котором не установлена операционная система Windows.</span><span class="sxs-lookup"><span data-stu-id="f5b17-181">The commands in this example enable you to manage the storage systems of a remote computer that is not running the Windows operating system.</span></span>
<span data-ttu-id="f5b17-182">Поскольку администратор в этом примере установил поставщик WMI модуля обнаружения на на компьютере, команды CIM могут использовать значения по умолчанию, которые предназначены для поставщика.</span><span class="sxs-lookup"><span data-stu-id="f5b17-182">In this example, because the administrator of the computer has installed the Module Discovery WMI provider, the CIM commands can use the default values, which are designed for the provider.</span></span>

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

<span data-ttu-id="f5b17-183">Первая команда использует `New-CimSession` командлет для создания сеанса на удаленном компьютере RSDGF03.</span><span class="sxs-lookup"><span data-stu-id="f5b17-183">The first command uses the `New-CimSession` cmdlet to create a session on the RSDGF03 remote computer.</span></span> <span data-ttu-id="f5b17-184">Сеанс подключается к инструментарию WMI на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="f5b17-184">The session connects to WMI on the remote computer.</span></span> <span data-ttu-id="f5b17-185">Команда сохраняет сеанс CIM в `$cs` переменной.</span><span class="sxs-lookup"><span data-stu-id="f5b17-185">The command saves the CIM session in the `$cs` variable.</span></span>

<span data-ttu-id="f5b17-186">Вторая команда использует сеанс CIM в `$cs` переменной для выполнения `Get-Module` команды на компьютере RSDGF03.</span><span class="sxs-lookup"><span data-stu-id="f5b17-186">The second command uses the CIM session in the `$cs` variable to run a `Get-Module` command on the RSDGF03 computer.</span></span> <span data-ttu-id="f5b17-187">С помощью параметра Name указывается модуль хранения.</span><span class="sxs-lookup"><span data-stu-id="f5b17-187">The command uses the Name parameter to specify the Storage module.</span></span> <span data-ttu-id="f5b17-188">Команда использует оператор конвейера (|) для отправки модуля хранения в `Import-Module` командлет, который импортирует его в локальный сеанс.</span><span class="sxs-lookup"><span data-stu-id="f5b17-188">The command uses a pipeline operator (|) to send the Storage module to the `Import-Module` cmdlet, which imports it into the local session.</span></span>

<span data-ttu-id="f5b17-189">Третья команда выполняет `Get-Command` командлет для `Get-Disk` команды в модуле Storage.</span><span class="sxs-lookup"><span data-stu-id="f5b17-189">The third command runs the `Get-Command` cmdlet on the `Get-Disk` command in the Storage module.</span></span>
<span data-ttu-id="f5b17-190">При импорте модуля CIM в локальный сеанс PowerShell преобразует файлы CDXML, представляющие модуль CIM, в скрипты PowerShell, которые отображаются как функции в локальном сеансе.</span><span class="sxs-lookup"><span data-stu-id="f5b17-190">When you import a CIM module into the local session, PowerShell converts the CDXML files that represent the CIM module into PowerShell scripts, which appear as functions in the local session.</span></span>

<span data-ttu-id="f5b17-191">Четвертая команда выполняет `Get-Disk` команду.</span><span class="sxs-lookup"><span data-stu-id="f5b17-191">The fourth command runs the `Get-Disk` command.</span></span> <span data-ttu-id="f5b17-192">Хотя команда вводится в рамках текущего сеанса, она выполняется неявно на удаленном компьютере, с которого она была импортирована.</span><span class="sxs-lookup"><span data-stu-id="f5b17-192">Although the command is typed in the local session, it runs implicitly on the remote computer from which it was imported.</span></span> <span data-ttu-id="f5b17-193">Команда получает объекты с удаленного компьютера и возвращает их в локальный сеанс.</span><span class="sxs-lookup"><span data-stu-id="f5b17-193">The command gets objects from the remote computer and returns them to the local session.</span></span>

## <span data-ttu-id="f5b17-194">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f5b17-194">PARAMETERS</span></span>

### <span data-ttu-id="f5b17-195">-All</span><span class="sxs-lookup"><span data-stu-id="f5b17-195">-All</span></span>

<span data-ttu-id="f5b17-196">Указывает, что этот командлет получает все модули в каждой папке модуля, включая вложенные модули, файлы манифеста (PSD1), файлы модуля скрипта (. PSM1) и двоичные файлы (DLL).</span><span class="sxs-lookup"><span data-stu-id="f5b17-196">Indicates that this cmdlet gets all modules in each module folder, including nested modules, manifest (.psd1) files, script module (.psm1) files, and binary module (.dll) files.</span></span> <span data-ttu-id="f5b17-197">Без этого параметра `Get-Module` получает только модуль по умолчанию в каждой папке модуля.</span><span class="sxs-lookup"><span data-stu-id="f5b17-197">Without this parameter, `Get-Module` gets only the default module in each module folder.</span></span>

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

### <span data-ttu-id="f5b17-198">-Цимнамеспаце</span><span class="sxs-lookup"><span data-stu-id="f5b17-198">-CimNamespace</span></span>

<span data-ttu-id="f5b17-199">Задает пространство имен для альтернативного поставщика CIM, предоставляющего модули CIM.</span><span class="sxs-lookup"><span data-stu-id="f5b17-199">Specifies the namespace of an alternate CIM provider that exposes CIM modules.</span></span> <span data-ttu-id="f5b17-200">Значение по умолчанию — пространство имен поставщика модуля обнаружения WMI.</span><span class="sxs-lookup"><span data-stu-id="f5b17-200">The default value is the namespace of the Module Discovery WMI provider.</span></span>

<span data-ttu-id="f5b17-201">Этот параметр используется для получения модулей CIM с компьютеров и устройств, на которых не установлена операционная система Windows.</span><span class="sxs-lookup"><span data-stu-id="f5b17-201">Use this parameter to get CIM modules from computers and devices that are not running the Windows operating system.</span></span>

<span data-ttu-id="f5b17-202">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="f5b17-202">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="f5b17-203">-Цимресаурцеури</span><span class="sxs-lookup"><span data-stu-id="f5b17-203">-CimResourceUri</span></span>

<span data-ttu-id="f5b17-204">Задает альтернативное расположение для модулей CIM.</span><span class="sxs-lookup"><span data-stu-id="f5b17-204">Specifies an alternate location for CIM modules.</span></span> <span data-ttu-id="f5b17-205">Значение по умолчанию — URI ресурса поставщика модуля обнаружения WMI на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="f5b17-205">The default value is the resource URI of the Module Discovery WMI provider on the remote computer.</span></span>

<span data-ttu-id="f5b17-206">Этот параметр используется для получения модулей CIM с компьютеров и устройств, на которых не установлена операционная система Windows.</span><span class="sxs-lookup"><span data-stu-id="f5b17-206">Use this parameter to get CIM modules from computers and devices that are not running the Windows operating system.</span></span>

<span data-ttu-id="f5b17-207">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="f5b17-207">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="f5b17-208">-CimSession</span><span class="sxs-lookup"><span data-stu-id="f5b17-208">-CimSession</span></span>

<span data-ttu-id="f5b17-209">Указывает сеанс CIM на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="f5b17-209">Specifies a CIM session on the remote computer.</span></span> <span data-ttu-id="f5b17-210">Введите переменную, которая содержит сеанс CIM, или команду, которая получает сеанс CIM, например команду [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) .</span><span class="sxs-lookup"><span data-stu-id="f5b17-210">Enter a variable that contains the CIM session or a command that gets the CIM session, such as a [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) command.</span></span>

<span data-ttu-id="f5b17-211">`Get-Module` использует соединение с сеансом CIM для получения модулей с удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="f5b17-211">`Get-Module` uses the CIM session connection to get modules from the remote computer.</span></span> <span data-ttu-id="f5b17-212">При импорте модуля с помощью `Import-Module` командлета и использовании команд из импортированного модуля в текущем сеансе команды фактически выполняются на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="f5b17-212">When you import the module by using the `Import-Module` cmdlet and use the commands from the imported module in the current session, the commands actually run on the remote computer.</span></span>

<span data-ttu-id="f5b17-213">Этот параметр можно использовать для получения модулей с компьютеров и устройств, не работающих под управлением операционной системы Windows, а также для компьютеров с PowerShell, на которых не включено удаленное взаимодействие PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f5b17-213">You can use this parameter to get modules from computers and devices that are not running the Windows operating system, and computers that have PowerShell, but do not have PowerShell remoting enabled.</span></span>

<span data-ttu-id="f5b17-214">Параметр **CimSession** возвращает все модули из сеанса **CIMSession**.</span><span class="sxs-lookup"><span data-stu-id="f5b17-214">The **CimSession** parameter gets all modules in the **CIMSession**.</span></span> <span data-ttu-id="f5b17-215">Однако вы можете импортировать только модули CIM и CDXML.</span><span class="sxs-lookup"><span data-stu-id="f5b17-215">However, you can import only CIM-based and Cmdlet Definition XML (CDXML)-based modules.</span></span>

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

### <span data-ttu-id="f5b17-216">-FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="f5b17-216">-FullyQualifiedName</span></span>

<span data-ttu-id="f5b17-217">Указывает модули с именами, указанными в форме объектов **ModuleSpecification** .</span><span class="sxs-lookup"><span data-stu-id="f5b17-217">Specifies modules with names that are specified in the form of **ModuleSpecification** objects.</span></span> <span data-ttu-id="f5b17-218">См. раздел "Примечания" [конструктора ModuleSpecification (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span><span class="sxs-lookup"><span data-stu-id="f5b17-218">See the Remarks section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>

<span data-ttu-id="f5b17-219">Например, параметр **FullyQualifiedModule** принимает имя модуля, указанное в одном из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="f5b17-219">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in either of these formats:</span></span>

- `@{ModuleName = "modulename"; ModuleVersion = "version_number"}`
- `@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

<span data-ttu-id="f5b17-220">Параметры **ModuleName** и **ModuleVersion** обязательны, а **Guid** — нет.</span><span class="sxs-lookup"><span data-stu-id="f5b17-220">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span> <span data-ttu-id="f5b17-221">Нельзя указать параметр **FullyQualifiedModule** в той же команде, что и параметр **module** .</span><span class="sxs-lookup"><span data-stu-id="f5b17-221">You cannot specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span> <span data-ttu-id="f5b17-222">два параметра являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="f5b17-222">the two parameters are mutually exclusive.</span></span>

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

### <span data-ttu-id="f5b17-223">-ListAvailable</span><span class="sxs-lookup"><span data-stu-id="f5b17-223">-ListAvailable</span></span>

<span data-ttu-id="f5b17-224">Указывает, что этот командлет получает все установленные модули.</span><span class="sxs-lookup"><span data-stu-id="f5b17-224">Indicates that this cmdlet gets all installed modules.</span></span> <span data-ttu-id="f5b17-225">`Get-Module` Возвращает модули в путях, указанных в переменной среды **PSModulePath** .</span><span class="sxs-lookup"><span data-stu-id="f5b17-225">`Get-Module` gets modules in paths listed in the **PSModulePath** environment variable.</span></span> <span data-ttu-id="f5b17-226">Без этого параметра `Get-Module` получает только те модули, которые указаны в переменной среды **PSModulePath** и загружены в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="f5b17-226">Without this parameter, `Get-Module` gets only the modules that are both listed in the **PSModulePath** environment variable, and that are loaded in the current session.</span></span> <span data-ttu-id="f5b17-227">Параметр **ListAvailable** не возвращает информацию о модулях, которые не найдены в переменной среды **PSModulePath**, даже если они загружены в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="f5b17-227">**ListAvailable** does not return information about modules that are not found in the **PSModulePath** environment variable, even if those modules are loaded in the current session.</span></span>

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

### <span data-ttu-id="f5b17-228">-Name</span><span class="sxs-lookup"><span data-stu-id="f5b17-228">-Name</span></span>

<span data-ttu-id="f5b17-229">Указывает имена или шаблоны имен модулей, которые получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="f5b17-229">Specifies names or name patterns of modules that this cmdlet gets.</span></span> <span data-ttu-id="f5b17-230">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="f5b17-230">Wildcard characters are permitted.</span></span> <span data-ttu-id="f5b17-231">Можно также передать имена в `Get-Module` .</span><span class="sxs-lookup"><span data-stu-id="f5b17-231">You can also pipe the names to `Get-Module`.</span></span> <span data-ttu-id="f5b17-232">Нельзя указать параметр **FullyQualifiedName** в той же команде, что и параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="f5b17-232">You cannot specify the **FullyQualifiedName** parameter in the same command as a **Name** parameter.</span></span>

<span data-ttu-id="f5b17-233">**Имя** не может принимать GUID модуля в качестве значения.</span><span class="sxs-lookup"><span data-stu-id="f5b17-233">**Name** cannot accept a module GUID as a value.</span></span>
<span data-ttu-id="f5b17-234">Чтобы вернуть модули, указав идентификатор GUID, используйте вместо него **FullyQualifiedName** .</span><span class="sxs-lookup"><span data-stu-id="f5b17-234">To return modules by specifying a GUID, use **FullyQualifiedName** instead.</span></span>

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

### <span data-ttu-id="f5b17-235">-PSEdition</span><span class="sxs-lookup"><span data-stu-id="f5b17-235">-PSEdition</span></span>

<span data-ttu-id="f5b17-236">Возвращает модули, поддерживающие указанный выпуск PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f5b17-236">Gets the modules that support specified edition of PowerShell.</span></span>

<span data-ttu-id="f5b17-237">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="f5b17-237">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f5b17-238">Рабочий стол</span><span class="sxs-lookup"><span data-stu-id="f5b17-238">Desktop</span></span>
- <span data-ttu-id="f5b17-239">Основные сведения</span><span class="sxs-lookup"><span data-stu-id="f5b17-239">Core</span></span>

<span data-ttu-id="f5b17-240">Командлет Get-Module проверяет свойство **CompatiblePSEditions** объекта **PSModuleInfo** на указанное значение и возвращает только те модули, для которых он задан.</span><span class="sxs-lookup"><span data-stu-id="f5b17-240">The Get-Module cmdlet checks **CompatiblePSEditions** property of **PSModuleInfo** object for the specified value and returns only those modules that have it set.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="f5b17-241">**Выпуск Desktop:** создан на базе платформы .NET Framework и обеспечивает совместимость со сценариями и модулями, предназначенными для версий PowerShell в полноценных выпусках Windows, таких как Server Core и Windows Desktop.</span><span class="sxs-lookup"><span data-stu-id="f5b17-241">**Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.</span></span>
> - <span data-ttu-id="f5b17-242">**Выпуск Core Edition:** построен на основе .NET Core и обеспечивает совместимость со скриптами и модулями, которые предназначены для версий PowerShell, выполняющихся в выпусках Windows с ограниченными возможностями, таких как Nano Server и Windows IoT.</span><span class="sxs-lookup"><span data-stu-id="f5b17-242">**Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.</span></span>

```yaml
Type: System.String
Parameter Sets: PsSession, Available
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f5b17-243">-PSSession</span><span class="sxs-lookup"><span data-stu-id="f5b17-243">-PSSession</span></span>

<span data-ttu-id="f5b17-244">Возвращает модули из указанного управляемого пользователем сеанса PowerShell (**PSSession**).</span><span class="sxs-lookup"><span data-stu-id="f5b17-244">Gets the modules in the specified user-managed PowerShell session (**PSSession**).</span></span> <span data-ttu-id="f5b17-245">Введите переменную, которая содержит сеанс, команду, которая получает сеанс, например `Get-PSSession` команду, или команду, которая создает сеанс, например `New-PSSession` команду.</span><span class="sxs-lookup"><span data-stu-id="f5b17-245">Enter a variable that contains the session, a command that gets the session, such as a `Get-PSSession` command, or a command that creates the session, such as a `New-PSSession` command.</span></span>

<span data-ttu-id="f5b17-246">Если сеанс подключен к удаленному компьютеру, необходимо указать параметр **ListAvailable** .</span><span class="sxs-lookup"><span data-stu-id="f5b17-246">When the session is connected to a remote computer, you must specify the **ListAvailable** parameter.</span></span>

<span data-ttu-id="f5b17-247">`Get-Module`Команда, использующая параметр **PSSession** , эквивалентна использованию `Invoke-Command` командлета для выполнения `Get-Module -ListAvailable` команды в **PSSession**.</span><span class="sxs-lookup"><span data-stu-id="f5b17-247">A `Get-Module` command that uses the **PSSession** parameter is equivalent to using the `Invoke-Command` cmdlet to run a `Get-Module -ListAvailable` command in a **PSSession**.</span></span>

<span data-ttu-id="f5b17-248">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="f5b17-248">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="f5b17-249">-Refresh</span><span class="sxs-lookup"><span data-stu-id="f5b17-249">-Refresh</span></span>

<span data-ttu-id="f5b17-250">Указывает, что этот командлет обновляет кэш установленных команд.</span><span class="sxs-lookup"><span data-stu-id="f5b17-250">Indicates that this cmdlet refreshes the cache of installed commands.</span></span> <span data-ttu-id="f5b17-251">Кэш команд создается при запуске сеанса.</span><span class="sxs-lookup"><span data-stu-id="f5b17-251">The command cache is created when the session starts.</span></span> <span data-ttu-id="f5b17-252">Он позволяет `Get-Command` командлету получать команды из модулей, которые не импортируются в сеанс.</span><span class="sxs-lookup"><span data-stu-id="f5b17-252">It enables the `Get-Command` cmdlet to get commands from modules that are not imported into the session.</span></span>

<span data-ttu-id="f5b17-253">Этот параметр предназначен для сценариев разработки и тестирования, в которых содержимое модулей меняется с момента начала сеанса.</span><span class="sxs-lookup"><span data-stu-id="f5b17-253">This parameter is designed for development and testing scenarios in which the contents of modules have changed since the session started.</span></span>

<span data-ttu-id="f5b17-254">При указании параметра **Refresh** в команде необходимо указать **ListAvailable**.</span><span class="sxs-lookup"><span data-stu-id="f5b17-254">When you specify the **Refresh** parameter in a command, you must specify **ListAvailable**.</span></span>

<span data-ttu-id="f5b17-255">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="f5b17-255">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="f5b17-256">-Скипедитиончекк</span><span class="sxs-lookup"><span data-stu-id="f5b17-256">-SkipEditionCheck</span></span>

<span data-ttu-id="f5b17-257">Пропускает проверку `CompatiblePSEditions` поля.</span><span class="sxs-lookup"><span data-stu-id="f5b17-257">Skips the check of the `CompatiblePSEditions` field.</span></span>

<span data-ttu-id="f5b17-258">По умолчанию Get-Module будет опускать модули в `%windir%\System32\WindowsPowerShell\v1.0\Modules` каталоге, не указанные `Core` в `CompatiblePSEditions` поле.</span><span class="sxs-lookup"><span data-stu-id="f5b17-258">By default, Get-Module will omit modules in the `%windir%\System32\WindowsPowerShell\v1.0\Modules` directory that do not specify `Core` in the `CompatiblePSEditions` field.</span></span> <span data-ttu-id="f5b17-259">Если этот параметр задан, то модули без `Core` будут включены, поэтому будут возвращены модули в пути модуля Windows PowerShell, несовместимые с PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="f5b17-259">When this switch is set, modules without `Core` will be included, so that modules under the Windows PowerShell module path that are incompatible with PowerShell Core will be returned.</span></span>

<span data-ttu-id="f5b17-260">В macOS и Linux этот параметр не выполняет никаких действий.</span><span class="sxs-lookup"><span data-stu-id="f5b17-260">On macOS and Linux, this parameter does nothing.</span></span>

<span data-ttu-id="f5b17-261">Дополнительные сведения см. в разделе [about_PowerShell_Editions](About/about_PowerShell_Editions.md) .</span><span class="sxs-lookup"><span data-stu-id="f5b17-261">See [about_PowerShell_Editions](About/about_PowerShell_Editions.md) for more information.</span></span>

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

### <span data-ttu-id="f5b17-262">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="f5b17-262">CommonParameters</span></span>

<span data-ttu-id="f5b17-263">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f5b17-263">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f5b17-264">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f5b17-264">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f5b17-265">Входные данные</span><span class="sxs-lookup"><span data-stu-id="f5b17-265">INPUTS</span></span>

### <span data-ttu-id="f5b17-266">System.String</span><span class="sxs-lookup"><span data-stu-id="f5b17-266">System.String</span></span>

<span data-ttu-id="f5b17-267">В этот командлет можно передать имена модулей.</span><span class="sxs-lookup"><span data-stu-id="f5b17-267">You can pipe module names to this cmdlet.</span></span>

## <span data-ttu-id="f5b17-268">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="f5b17-268">OUTPUTS</span></span>

### <span data-ttu-id="f5b17-269">System.Management.Automation.PSModuleInfo</span><span class="sxs-lookup"><span data-stu-id="f5b17-269">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="f5b17-270">Этот командлет возвращает объекты, представляющие модули.</span><span class="sxs-lookup"><span data-stu-id="f5b17-270">This cmdlet returns objects that represent modules.</span></span>
<span data-ttu-id="f5b17-271">При указании параметра **ListAvailable** `Get-Module` возвращает объект **модулеинфограупинг** , который является типом объекта **PSModuleInfo** , который имеет те же свойства и методы.</span><span class="sxs-lookup"><span data-stu-id="f5b17-271">When you specify the **ListAvailable** parameter, `Get-Module` returns a **ModuleInfoGrouping** object, which is a type of **PSModuleInfo** object that has the same properties and methods.</span></span>

## <span data-ttu-id="f5b17-272">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="f5b17-272">NOTES</span></span>

- <span data-ttu-id="f5b17-273">Начиная с Windows PowerShell 3,0, основные команды, входящие в PowerShell, упаковываются в модули.</span><span class="sxs-lookup"><span data-stu-id="f5b17-273">Beginning in Windows PowerShell 3.0, the core commands that are included in PowerShell are packaged in modules.</span></span> <span data-ttu-id="f5b17-274">Исключением является **Microsoft. PowerShell. Core**— оснастка (**PSSnapin**).</span><span class="sxs-lookup"><span data-stu-id="f5b17-274">The exception is **Microsoft.PowerShell.Core**, which is a snap-in (**PSSnapin**).</span></span> <span data-ttu-id="f5b17-275">По умолчанию в сеанс добавляется только оснастка **Microsoft.PowerShell.Core**.</span><span class="sxs-lookup"><span data-stu-id="f5b17-275">By default, only the **Microsoft.PowerShell.Core** snap-in is added to the session.</span></span> <span data-ttu-id="f5b17-276">Модули импортируются автоматически при первом использовании `Import-Module` . для их импорта можно использовать командлет.</span><span class="sxs-lookup"><span data-stu-id="f5b17-276">Modules are imported automatically on first use and you can use the `Import-Module` cmdlet to import them.</span></span>

- <span data-ttu-id="f5b17-277">В Windows PowerShell 2,0 и в ведущих программах, которые создают сеансы предыдущих версий в более поздних версиях PowerShell, основные команды упаковываются в оснастки (**PSSnapin**).</span><span class="sxs-lookup"><span data-stu-id="f5b17-277">In Windows PowerShell 2.0, and in host programs that create older-style sessions in later versions of PowerShell, the core commands are packaged in snap-ins (**PSSnapins**).</span></span> <span data-ttu-id="f5b17-278">Исключением является **Microsoft. PowerShell. Core**, который всегда является оснасткой.</span><span class="sxs-lookup"><span data-stu-id="f5b17-278">The exception is **Microsoft.PowerShell.Core**, which is always a snap-in.</span></span> <span data-ttu-id="f5b17-279">Кроме того, удаленные сеансы, такие как запущенные `New-PSSession` командлетом, являются сеансами предыдущих версий, включающими основные оснастки.</span><span class="sxs-lookup"><span data-stu-id="f5b17-279">Also, remote sessions, such as those started by the `New-PSSession` cmdlet, are older-style sessions that include core snap-ins.</span></span>

  <span data-ttu-id="f5b17-280">Дополнительные сведения о методе **CreateDefault2** , который создает сеансы нового стиля с основными модулями, см. в разделе [метод CreateDefault2](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2).</span><span class="sxs-lookup"><span data-stu-id="f5b17-280">For information about the **CreateDefault2** method that creates newer-style sessions with core modules, see [CreateDefault2 Method](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2).</span></span>

- <span data-ttu-id="f5b17-281">`Get-Module` только возвращает модули в расположениях, которые хранятся в значении переменной среды **PSModulePath** ($env:P смодулепас).</span><span class="sxs-lookup"><span data-stu-id="f5b17-281">`Get-Module` only gets modules in locations that are stored in the value of the **PSModulePath** environment variable ($env:PSModulePath).</span></span> <span data-ttu-id="f5b17-282">`Import-Module`Командлет может импортировать модули в других местах, но `Get-Module` для их получения нельзя использовать командлет.</span><span class="sxs-lookup"><span data-stu-id="f5b17-282">The `Import-Module` cmdlet can import modules in other locations, but you cannot use the `Get-Module` cmdlet to get them.</span></span>

- <span data-ttu-id="f5b17-283">Кроме того, начиная с PowerShell 3,0 в объект, который возвращает, были добавлены новые свойства, `Get-Module` которые упрощают изучение модулей даже перед их импортом.</span><span class="sxs-lookup"><span data-stu-id="f5b17-283">Also, starting in PowerShell 3.0, new properties have been added to the object that `Get-Module` returns that make it easier to learn about modules even before they are imported.</span></span> <span data-ttu-id="f5b17-284">Все свойства заполняются перед импортом.</span><span class="sxs-lookup"><span data-stu-id="f5b17-284">All properties are populated before importing.</span></span> <span data-ttu-id="f5b17-285">К ним относятся свойства **ExportedCommands**, **експортедкмдлетс** и **експортедфунктионс** , в которых перечислены команды, экспортируемые модулем.</span><span class="sxs-lookup"><span data-stu-id="f5b17-285">These include the **ExportedCommands**, **ExportedCmdlets** and **ExportedFunctions** properties that list the commands that the module exports.</span></span>

- <span data-ttu-id="f5b17-286">Параметр **ListAvailable** возвращает только модули с правильным форматом, то есть папки, содержащие по крайней мере один файл, базовое имя которого совпадает с именем папки модуля.</span><span class="sxs-lookup"><span data-stu-id="f5b17-286">The **ListAvailable** parameter gets only well-formed modules, that is, folders that contain at least one file whose base name is the same as the name of the module folder.</span></span> <span data-ttu-id="f5b17-287">Базовое имя — это имя без расширения имени файла.</span><span class="sxs-lookup"><span data-stu-id="f5b17-287">The base name is the name without the file name extension.</span></span> <span data-ttu-id="f5b17-288">Папки, содержащие файлы с разными именами, считаются контейнерами, но не модулями.</span><span class="sxs-lookup"><span data-stu-id="f5b17-288">Folders that contain files that have different names are considered to be containers, but not modules.</span></span>

  <span data-ttu-id="f5b17-289">Для получения модулей, которые реализуются в виде DLL-файлов, но не заключаются в папку модуля, укажите оба параметра: **ListAvailable** и **ALL** .</span><span class="sxs-lookup"><span data-stu-id="f5b17-289">To get modules that are implemented as DLL files, but are not enclosed in a module folder, specify both the **ListAvailable** and **All** parameters.</span></span>

- <span data-ttu-id="f5b17-290">Для использования функции сеанса CIM на удаленном компьютере должен быть установлен компонент удаленного взаимодействия WS-Management и инструментарий управления Windows (WMI), который представляет собой реализацию стандарта CIM корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f5b17-290">To use the CIM session feature, the remote computer must have WS-Management remoting and Windows Management Instrumentation (WMI), which is the Microsoft implementation of the Common Information Model (CIM) standard.</span></span> <span data-ttu-id="f5b17-291">На компьютере должен быть также поставщик WMI обнаружения модулей или другой поставщик WMI с теми же основными возможностями.</span><span class="sxs-lookup"><span data-stu-id="f5b17-291">The computer must also have the Module Discovery WMI provider or an alternate WMI provider that has the same basic features.</span></span>

  <span data-ttu-id="f5b17-292">Можно использовать сеанс CIM на компьютерах, на которых не установлена операционная система Windows и на компьютерах Windows с PowerShell, но удаленное взаимодействие PowerShell не включено.</span><span class="sxs-lookup"><span data-stu-id="f5b17-292">You can use the CIM session feature on computers that are not running the Windows operating system and on Windows computers that have PowerShell, but do not have PowerShell remoting enabled.</span></span>

  <span data-ttu-id="f5b17-293">Можно также использовать параметры CIM для получения модулей CIM с компьютеров, на которых включено удаленное взаимодействие PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f5b17-293">You can also use the CIM parameters to get CIM modules from computers that have PowerShell remoting enabled.</span></span> <span data-ttu-id="f5b17-294">Сюда входит локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="f5b17-294">This includes the local computer.</span></span> <span data-ttu-id="f5b17-295">При создании сеанса CIM на локальном компьютере для создания сеанса в PowerShell используется DCOM, а не WMI.</span><span class="sxs-lookup"><span data-stu-id="f5b17-295">When you create a CIM session on the local computer, PowerShell uses DCOM, instead of WMI, to create the session.</span></span>

## <span data-ttu-id="f5b17-296">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="f5b17-296">RELATED LINKS</span></span>

[<span data-ttu-id="f5b17-297">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="f5b17-297">Get-CimSession</span></span>](../CimCmdlets/Get-CimSession.md)

[<span data-ttu-id="f5b17-298">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="f5b17-298">New-CimSession</span></span>](../CimCmdlets/New-CimSession.md)

[<span data-ttu-id="f5b17-299">about_Modules</span><span class="sxs-lookup"><span data-stu-id="f5b17-299">about_Modules</span></span>](About/about_Modules.md)

[<span data-ttu-id="f5b17-300">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="f5b17-300">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="f5b17-301">Import-Module</span><span class="sxs-lookup"><span data-stu-id="f5b17-301">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="f5b17-302">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="f5b17-302">Import-PSSession</span></span>](../Microsoft.PowerShell.Utility/Import-PSSession.md)

[<span data-ttu-id="f5b17-303">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="f5b17-303">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="f5b17-304">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="f5b17-304">Remove-Module</span></span>](Remove-Module.md)

[<span data-ttu-id="f5b17-305">about_PowerShell_Editions</span><span class="sxs-lookup"><span data-stu-id="f5b17-305">about_PowerShell_Editions</span></span>](About/about_PowerShell_Editions.md)
