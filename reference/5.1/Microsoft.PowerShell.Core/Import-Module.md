---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/import-module?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Module
ms.openlocfilehash: 6b87074f6053189b20b5cc0983f978324420c99b
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2020
ms.locfileid: "96564396"
---
# <span data-ttu-id="ce404-102">Import-Module</span><span class="sxs-lookup"><span data-stu-id="ce404-102">Import-Module</span></span>

## <span data-ttu-id="ce404-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ce404-103">SYNOPSIS</span></span>
<span data-ttu-id="ce404-104">Добавляет модули в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="ce404-104">Adds modules to the current session.</span></span>

## <span data-ttu-id="ce404-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ce404-105">SYNTAX</span></span>

### <span data-ttu-id="ce404-106">Имя (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="ce404-106">Name (Default)</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Name] <String[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-PassThru]
 [-AsCustomObject] [-MinimumVersion <Version>] [-MaximumVersion <String>]
 [-RequiredVersion <Version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] [<CommonParameters>]
```

### <span data-ttu-id="ce404-107">PSSession</span><span class="sxs-lookup"><span data-stu-id="ce404-107">PSSession</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Name] <String[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-PassThru]
 [-AsCustomObject] [-MinimumVersion <Version>] [-MaximumVersion <String>]
 [-RequiredVersion <Version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] -PSSession <PSSession> [<CommonParameters>]
```

### <span data-ttu-id="ce404-108">CimSession</span><span class="sxs-lookup"><span data-stu-id="ce404-108">CimSession</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Name] <String[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-PassThru]
 [-AsCustomObject] [-MinimumVersion <Version>] [-MaximumVersion <String>]
 [-RequiredVersion <Version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] -CimSession <CimSession> [-CimResourceUri <Uri>] [-CimNamespace <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="ce404-109">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="ce404-109">FullyQualifiedName</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-FullyQualifiedName] <ModuleSpecification[]>
 [-Function <String[]>] [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force]
 [-PassThru] [-AsCustomObject] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] [<CommonParameters>]
```

### <span data-ttu-id="ce404-110">фулликуалифиеднамеандпссессион</span><span class="sxs-lookup"><span data-stu-id="ce404-110">FullyQualifiedNameAndPSSession</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-FullyQualifiedName] <ModuleSpecification[]>
 [-Function <String[]>] [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force]
 [-PassThru] [-AsCustomObject] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] -PSSession <PSSession> [<CommonParameters>]
```

### <span data-ttu-id="ce404-111">Сборка</span><span class="sxs-lookup"><span data-stu-id="ce404-111">Assembly</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Assembly] <Assembly[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-PassThru]
 [-AsCustomObject] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber] [-Scope <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="ce404-112">ModuleInfo</span><span class="sxs-lookup"><span data-stu-id="ce404-112">ModuleInfo</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Function <String[]>] [-Cmdlet <String[]>]
 [-Variable <String[]>] [-Alias <String[]>] [-Force] [-PassThru] [-AsCustomObject]
 [-ModuleInfo] <PSModuleInfo[]> [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] [<CommonParameters>]
```

## <span data-ttu-id="ce404-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ce404-113">DESCRIPTION</span></span>

<span data-ttu-id="ce404-114">`Import-Module`Командлет добавляет один или несколько модулей в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="ce404-114">The `Import-Module` cmdlet adds one or more modules to the current session.</span></span> <span data-ttu-id="ce404-115">Начиная с PowerShell 3,0, установленные модули автоматически импортируются в сеанс при использовании каких либо команд или поставщиков в модуле.</span><span class="sxs-lookup"><span data-stu-id="ce404-115">Starting in PowerShell 3.0, installed modules are automatically imported to the session when you use any commands or providers in the module.</span></span> <span data-ttu-id="ce404-116">Однако вы по-прежнему можете использовать `Import-Module` команду для импорта модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-116">However, you can still use the `Import-Module` command to import a module.</span></span>
<span data-ttu-id="ce404-117">Вы можете отключить автоматическое импортирование модулей с помощью `$PSModuleAutoloadingPreference` переменной предпочтений.</span><span class="sxs-lookup"><span data-stu-id="ce404-117">You can disable automatic module importing using the `$PSModuleAutoloadingPreference` preference variable.</span></span> <span data-ttu-id="ce404-118">Дополнительные сведения о `$PSModuleAutoloadingPreference` переменной см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="ce404-118">For more information about the `$PSModuleAutoloadingPreference` variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="ce404-119">Модуль — это пакет, содержащий элементы, которые можно использовать в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ce404-119">A module is a package that contains members that can be used in PowerShell.</span></span> <span data-ttu-id="ce404-120">Члены включают командлеты, поставщики, скрипты, функции, переменные и другие средства и файлы.</span><span class="sxs-lookup"><span data-stu-id="ce404-120">Members include cmdlets, providers, scripts, functions, variables, and other tools and files.</span></span> <span data-ttu-id="ce404-121">После импорта модуля вы можете использовать его элементы в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="ce404-121">After a module is imported, you can use the module members in your session.</span></span> <span data-ttu-id="ce404-122">Дополнительные сведения о модулях см. в разделе [about_Modules](About/about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="ce404-122">For more information about modules, see [about_Modules](About/about_Modules.md).</span></span>

<span data-ttu-id="ce404-123">По умолчанию `Import-Module` импортирует все элементы, экспортируемые модулем, но можно использовать параметры **псевдонима**, **функции**, **командлета** и **переменной** , чтобы ограничить импортируемые элементы.</span><span class="sxs-lookup"><span data-stu-id="ce404-123">By default, `Import-Module` imports all members that the module exports, but you can use the **Alias**, **Function**, **Cmdlet**, and **Variable** parameters to restrict which members are imported.</span></span> <span data-ttu-id="ce404-124">Параметр **NoClobber** предотвращает `Import-Module` Импорт элементов, имеющих те же имена, что и члены в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="ce404-124">The **NoClobber** parameter prevents `Import-Module` from importing members that have the same names as members in the current session.</span></span>

<span data-ttu-id="ce404-125">`Import-Module` импортирует модуль только в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="ce404-125">`Import-Module` imports a module only into the current session.</span></span> <span data-ttu-id="ce404-126">Чтобы импортировать модуль в каждый новый сеанс, добавьте `Import-Module` команду в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ce404-126">To import the module into every new session, add an `Import-Module` command to your PowerShell profile.</span></span> <span data-ttu-id="ce404-127">Дополнительные сведения о профилях см. в разделе [about_Profiles](About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ce404-127">For more information about profiles, see [about_Profiles](About/about_Profiles.md).</span></span>

<span data-ttu-id="ce404-128">Вы можете управлять удаленными компьютерами Windows, на которых удаленное взаимодействие PowerShell включено, создав **сеанс PSSession** на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ce404-128">You can manage remote Windows computers that have PowerShell remoting enabled by creating a **PSSession** on the remote computer.</span></span> <span data-ttu-id="ce404-129">Затем используйте параметр **PSSession** параметра, `Import-Module` чтобы импортировать модули, установленные на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ce404-129">Then use the **PSSession** parameter of `Import-Module` to import the modules that are installed on the remote computer.</span></span> <span data-ttu-id="ce404-130">При использовании импортированных команд в текущем сеансе команды выполняются неявным образом на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ce404-130">When you use the imported commands in the current session the commands implicitly run on the remote computer.</span></span>

<span data-ttu-id="ce404-131">Начиная с Windows PowerShell 3,0, можно использовать `Import-Module` для импорта модулей модель CIM (CIM).</span><span class="sxs-lookup"><span data-stu-id="ce404-131">Starting in Windows PowerShell 3.0, you can use `Import-Module` to import Common Information Model (CIM) modules.</span></span> <span data-ttu-id="ce404-132">Модули CIM определяют командлеты в файлах XML определения командлетов (CDXML).</span><span class="sxs-lookup"><span data-stu-id="ce404-132">CIM modules define cmdlets in Cmdlet Definition XML (CDXML) files.</span></span> <span data-ttu-id="ce404-133">Эта функция позволяет использовать командлеты, реализованные в неуправляемых сборках кода, таких как написанные на C++.</span><span class="sxs-lookup"><span data-stu-id="ce404-133">This feature lets you use cmdlets that are implemented in non-managed code assemblies, such as those written in C++.</span></span>

<span data-ttu-id="ce404-134">Для удаленных компьютеров, на которых не включено удаленное взаимодействие PowerShell, включая компьютеры, на которых не установлена операционная система Windows, можно  использовать параметр CIMSession `Import-Module` в для импорта модулей CIM с удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="ce404-134">For remote computers that don't have PowerShell remoting enabled, including computers that aren't running the Windows operating system, you can use the **CIMSession** parameter of `Import-Module` to import CIM modules from the remote computer.</span></span> <span data-ttu-id="ce404-135">Импортированные команды выполняются неявно на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ce404-135">The imported commands run implicitly on the remote computer.</span></span> <span data-ttu-id="ce404-136">**CIMSession** — это подключение к инструментарий управления Windows (WMI) (WMI) на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ce404-136">A **CIMSession** is a connection to Windows Management Instrumentation (WMI) on the remote computer.</span></span>

## <span data-ttu-id="ce404-137">Примеры</span><span class="sxs-lookup"><span data-stu-id="ce404-137">EXAMPLES</span></span>

### <span data-ttu-id="ce404-138">Пример 1. Импорт членов модуля в текущий сеанс</span><span class="sxs-lookup"><span data-stu-id="ce404-138">Example 1: Import the members of a module into the current session</span></span>

<span data-ttu-id="ce404-139">В этом примере выполняется импорт элементов модуля **PSDiagnostics** в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="ce404-139">This example imports the members of the **PSDiagnostics** module into the current session.</span></span>

```powershell
Import-Module -Name PSDiagnostics
```

### <span data-ttu-id="ce404-140">Пример 2. импорт всех модулей, указанных в пути к модулю</span><span class="sxs-lookup"><span data-stu-id="ce404-140">Example 2: Import all modules specified by the module path</span></span>

<span data-ttu-id="ce404-141">В этом примере выполняется импорт всех доступных модулей по пути, указанному в `$env:PSModulePath` переменной среды, в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="ce404-141">This example imports all available modules in the path specified by the `$env:PSModulePath` environment variable into the current session.</span></span>

```powershell
Get-Module -ListAvailable | Import-Module
```

### <span data-ttu-id="ce404-142">Пример 3. Импорт элементов нескольких модулей в текущий сеанс</span><span class="sxs-lookup"><span data-stu-id="ce404-142">Example 3: Import the members of several modules into the current session</span></span>

<span data-ttu-id="ce404-143">В этом примере выполняется импорт элементов модулей **PSDiagnostics** и **DISM** в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="ce404-143">This example imports the members of the **PSDiagnostics** and **Dism** modules into the current session.</span></span>

```powershell
$m = Get-Module -ListAvailable PSDiagnostics, Dism
Import-Module -ModuleInfo $m
```

<span data-ttu-id="ce404-144">`Get-Module`Командлет получает модули **PSDiagnostics** и **DISM** и сохраняет объекты в `$m` переменной.</span><span class="sxs-lookup"><span data-stu-id="ce404-144">The `Get-Module` cmdlet gets the **PSDiagnostics** and **Dism** modules and saves the objects in the `$m` variable.</span></span> <span data-ttu-id="ce404-145">Параметр **ListAvailable** является обязательным при получении модулей, которые еще не импортированы в сеанс.</span><span class="sxs-lookup"><span data-stu-id="ce404-145">The **ListAvailable** parameter is required when you're getting modules that aren't yet imported into the session.</span></span>

<span data-ttu-id="ce404-146">Параметр **ModuleInfo** класса `Import-Module` используется для импорта модулей в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="ce404-146">The **ModuleInfo** parameter of `Import-Module` is used to import the modules into the current session.</span></span>

### <span data-ttu-id="ce404-147">Пример 4. импорт всех модулей, указанных путем</span><span class="sxs-lookup"><span data-stu-id="ce404-147">Example 4: Import all modules specified by a path</span></span>

<span data-ttu-id="ce404-148">В этом примере используется явный путь для указания импортируемого модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-148">This example uses an explicit path to identify the module to import.</span></span>

```powershell
Import-Module -Name c:\ps-test\modules\test -Verbose
```

```Output
VERBOSE: Loading module from path 'C:\ps-test\modules\Test\Test.psm1'.
VERBOSE: Exporting function 'my-parm'.
VERBOSE: Exporting function 'Get-Parameter'.
VERBOSE: Exporting function 'Get-Specification'.
VERBOSE: Exporting function 'Get-SpecDetails'.
```

<span data-ttu-id="ce404-149">Использование параметра **verbose** приводит `Import-Module` к отчету о ходе выполнения при загрузке модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-149">Using the **Verbose** parameter causes `Import-Module` to report progress as it loads the module.</span></span>
<span data-ttu-id="ce404-150">Без параметра **verbose**, **PassThru** или **AsCustomObject** не `Import-Module` создает никаких выходных данных при импорте модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-150">Without the **Verbose**, **PassThru**, or **AsCustomObject** parameter, `Import-Module` does not generate any output when it imports a module.</span></span>

### <span data-ttu-id="ce404-151">Пример 5. Ограничение элементов модуля, импортированных в сеанс</span><span class="sxs-lookup"><span data-stu-id="ce404-151">Example 5: Restrict module members imported into a session</span></span>

<span data-ttu-id="ce404-152">В этом примере показано, как ограничить список членов модуля, импортируемых в сеанс, и результат выполнения этой команды в сеансе.</span><span class="sxs-lookup"><span data-stu-id="ce404-152">This example shows how to restrict which module members are imported into the session and the effect of this command on the session.</span></span> <span data-ttu-id="ce404-153">Параметр **функции** ограничивает элементы, импортируемые из модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-153">The **Function** parameter limits the members that are imported from the module.</span></span> <span data-ttu-id="ce404-154">Можно также использовать параметры **псевдонима**, **переменной** и **командлета** для ограничения других членов, импортируемых модулем.</span><span class="sxs-lookup"><span data-stu-id="ce404-154">You can also use the **Alias**, **Variable**, and **Cmdlet** parameters to restrict other members that a module imports.</span></span>

<span data-ttu-id="ce404-155">`Get-Module`Командлет возвращает объект, представляющий модуль **PSDiagnostics** .</span><span class="sxs-lookup"><span data-stu-id="ce404-155">The `Get-Module` cmdlet gets the object that represents the **PSDiagnostics** module.</span></span> <span data-ttu-id="ce404-156">Свойство **експортедкмдлетс** перечисляет все командлеты, экспортируемые модулем, даже если они не были импортированы.</span><span class="sxs-lookup"><span data-stu-id="ce404-156">The **ExportedCmdlets** property lists all the cmdlets that the module exports, even though they were not all imported.</span></span>

```powershell
Import-Module PSDiagnostics -Function Disable-PSTrace, Enable-PSTrace
(Get-Module PSDiagnostics).ExportedCommands
```

```Output
Key                          Value
---                          -----
Disable-PSTrace              Disable-PSTrace
Disable-PSWSManCombinedTrace Disable-PSWSManCombinedTrace
Disable-WSManTrace           Disable-WSManTrace
Enable-PSTrace               Enable-PSTrace
Enable-PSWSManCombinedTrace  Enable-PSWSManCombinedTrace
Enable-WSManTrace            Enable-WSManTrace
Get-LogProperties            Get-LogProperties
Set-LogProperties            Set-LogProperties
Start-Trace                  Start-Trace
Stop-Trace                   Stop-Trace
```

```powershell
Get-Command -Module PSDiagnostics
```

```Output
CommandType     Name                 Version    Source
-----------     ----                 -------    ------
Function        Disable-PSTrace      6.1.0.0    PSDiagnostics
Function        Enable-PSTrace       6.1.0.0    PSDiagnostics
```

<span data-ttu-id="ce404-157">С помощью параметра **module** `Get-Command` командлета отображаются команды, импортированные из модуля **PSDiagnostics** .</span><span class="sxs-lookup"><span data-stu-id="ce404-157">Using the **Module** parameter of the `Get-Command` cmdlet shows the commands that were imported from the **PSDiagnostics** module.</span></span> <span data-ttu-id="ce404-158">Результаты подтверждают, что `Disable-PSTrace` `Enable-PSTrace` импортированы только командлеты и.</span><span class="sxs-lookup"><span data-stu-id="ce404-158">The results confirm that only the `Disable-PSTrace` and `Enable-PSTrace` cmdlets were imported.</span></span>

### <span data-ttu-id="ce404-159">Пример 6. Импорт элементов модуля и Добавление префикса</span><span class="sxs-lookup"><span data-stu-id="ce404-159">Example 6: Import the members of a module and add a prefix</span></span>

<span data-ttu-id="ce404-160">Этот пример импортирует модуль **PSDiagnostics** в текущий сеанс, добавляет префикс к именам членов, а затем отображает имена элементов с префиксом.</span><span class="sxs-lookup"><span data-stu-id="ce404-160">This example imports the **PSDiagnostics** module into the current session, adds a prefix to the member names, and then displays the prefixed member names.</span></span> <span data-ttu-id="ce404-161">Параметр **prefix** параметра `Import-Module` добавляет префикс **x** ко всем элементам, импортированным из модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-161">The **Prefix** parameter of `Import-Module` adds the **x** prefix to all members that are imported from the module.</span></span> <span data-ttu-id="ce404-162">Префикс применяется только к элементам в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="ce404-162">The prefix applies only to the members in the current session.</span></span> <span data-ttu-id="ce404-163">Он не изменяет сам модуль.</span><span class="sxs-lookup"><span data-stu-id="ce404-163">It does not change the module.</span></span> <span data-ttu-id="ce404-164">Параметр **PassThru** возвращает объект Module, представляющий импортированный модуль.</span><span class="sxs-lookup"><span data-stu-id="ce404-164">The **PassThru** parameter returns a module object that represents the imported module.</span></span>

```powershell
Import-Module PSDiagnostics -Prefix x -PassThru
```

```Output
ModuleType Version    Name               ExportedCommands
---------- -------    ----               ----------------
Script     6.1.0.0    PSDiagnostics      {Disable-xPSTrace, Disable-xPSWSManCombinedTrace, Disable-xW...
```

```powershell
Get-Command -Module PSDiagnostics
```

```Output
CommandType     Name                                   Version    Source
-----------     ----                                   -------    ------
Function        Disable-xPSTrace                       6.1.0.0    PSDiagnostics
Function        Disable-xPSWSManCombinedTrace          6.1.0.0    PSDiagnostics
Function        Disable-xWSManTrace                    6.1.0.0    PSDiagnostics
Function        Enable-xPSTrace                        6.1.0.0    PSDiagnostics
Function        Enable-xPSWSManCombinedTrace           6.1.0.0    PSDiagnostics
Function        Enable-xWSManTrace                     6.1.0.0    PSDiagnostics
Function        Get-xLogProperties                     6.1.0.0    PSDiagnostics
Function        Set-xLogProperties                     6.1.0.0    PSDiagnostics
Function        Start-xTrace                           6.1.0.0    PSDiagnostics
Function        Stop-xTrace                            6.1.0.0    PSDiagnostics
```

<span data-ttu-id="ce404-165">`Get-Command` Возвращает элементы, которые были импортированы из модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-165">`Get-Command` gets the members that have been imported from the module.</span></span> <span data-ttu-id="ce404-166">Выходные данные показывают, что к элементам модуля был правильно добавлен префикс.</span><span class="sxs-lookup"><span data-stu-id="ce404-166">The output shows that the module members were correctly prefixed.</span></span>

### <span data-ttu-id="ce404-167">Пример 7. получение и использование пользовательского объекта</span><span class="sxs-lookup"><span data-stu-id="ce404-167">Example 7: Get and use a custom object</span></span>

<span data-ttu-id="ce404-168">В этом примере показано, как получить и использовать пользовательский объект, возвращаемый методом `Import-Module` .</span><span class="sxs-lookup"><span data-stu-id="ce404-168">This example demonstrates how to get and use the custom object returned by `Import-Module`.</span></span>

<span data-ttu-id="ce404-169">Настраиваемые объекты содержат синтетические элементы, представляющие каждый из элементов импортированного модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-169">Custom objects include synthetic members that represent each of the imported module members.</span></span> <span data-ttu-id="ce404-170">Например, командлеты и функции в модуле преобразуются в методы скрипта пользовательского объекта.</span><span class="sxs-lookup"><span data-stu-id="ce404-170">For example, the cmdlets and functions in a module are converted to script methods of the custom object.</span></span>

<span data-ttu-id="ce404-171">Пользовательские объекты полезны в сценариях.</span><span class="sxs-lookup"><span data-stu-id="ce404-171">Custom objects are useful in scripting.</span></span> <span data-ttu-id="ce404-172">Они также полезны, если имена нескольких импортированных объектов совпадают.</span><span class="sxs-lookup"><span data-stu-id="ce404-172">They are also useful when several imported objects have the same names.</span></span> <span data-ttu-id="ce404-173">Использование метода скрипта объекта равнозначно указанию полного имени импортированного элемента, включая имя модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-173">Using the script method of an object is equivalent to specifying the fully qualified name of an imported member, including its module name.</span></span>

<span data-ttu-id="ce404-174">Параметр **AsCustomObject** можно использовать только при импорте модуля скрипта.</span><span class="sxs-lookup"><span data-stu-id="ce404-174">The **AsCustomObject** parameter can be used only when importing a script module.</span></span> <span data-ttu-id="ce404-175">Используйте `Get-Module` , чтобы определить, какой из доступных модулей является модулем скрипта.</span><span class="sxs-lookup"><span data-stu-id="ce404-175">Use `Get-Module` to determine which of the available modules is a script module.</span></span>

```powershell
Get-Module -List | Format-Table -Property Name, ModuleType -AutoSize
```

```Output
Name          ModuleType
----          ----------
Show-Calendar     Script
BitsTransfer    Manifest
PSDiagnostics   Manifest
TestCmdlets       Script
...
```

```powershell
$a = Import-Module -Name Show-Calendar -AsCustomObject -Passthru
$a | Get-Member
```

```Output
    TypeName: System.Management.Automation.PSCustomObject
Name          MemberType   Definition
----          ----------   ----------
Equals        Method       bool Equals(System.Object obj)
GetHashCode   Method       int GetHashCode()
GetType       Method       type GetType()
ToString      Method       string ToString()
Show-Calendar ScriptMethod System.Object Show-Calendar();
```

```powershell
$a."Show-Calendar"()
```

<span data-ttu-id="ce404-176">`Show-Calendar`Модуль скрипта импортируется с помощью параметра **AsCustomObject** для запроса пользовательского объекта, а параметр **PassThru** — для возврата объекта.</span><span class="sxs-lookup"><span data-stu-id="ce404-176">The `Show-Calendar` script module is imported using the **AsCustomObject** parameter to request a custom object and the **PassThru** parameter to return the object.</span></span> <span data-ttu-id="ce404-177">Полученный пользовательский объект сохраняется в `$a` переменной.</span><span class="sxs-lookup"><span data-stu-id="ce404-177">The resulting custom object is saved in the `$a` variable.</span></span>

<span data-ttu-id="ce404-178">`$a`Переменная передается в `Get-Member` командлет для отображения свойств и методов сохраненного объекта.</span><span class="sxs-lookup"><span data-stu-id="ce404-178">The `$a` variable is piped to the `Get-Member` cmdlet to show the properties and methods of the saved object.</span></span> <span data-ttu-id="ce404-179">В выходных данных показан `Show-Calendar` метод скрипта.</span><span class="sxs-lookup"><span data-stu-id="ce404-179">The output shows a `Show-Calendar` script method.</span></span>

<span data-ttu-id="ce404-180">Чтобы вызвать `Show-Calendar` метод скрипта, имя метода должно быть заключено в кавычки, так как имя включает дефис.</span><span class="sxs-lookup"><span data-stu-id="ce404-180">To call the `Show-Calendar` script method, the method name must be enclosed in quotation marks because the name includes a hyphen.</span></span>

### <span data-ttu-id="ce404-181">Пример 8. повторное импорт модуля в тот же сеанс</span><span class="sxs-lookup"><span data-stu-id="ce404-181">Example 8: Reimport a module into the same session</span></span>

<span data-ttu-id="ce404-182">В этом примере показано, как использовать параметр **Force** при повторном `Import-Module` импорте модуля в тот же сеанс.</span><span class="sxs-lookup"><span data-stu-id="ce404-182">This example shows how to use the **Force** parameter of `Import-Module` when you're reimporting a module into the same session.</span></span> <span data-ttu-id="ce404-183">Параметр **Force** удаляет загруженный модуль и затем импортирует его снова.</span><span class="sxs-lookup"><span data-stu-id="ce404-183">The **Force** parameter removes the loaded module and then imports it again.</span></span>

```powershell
Import-Module PSDiagnostics
Import-Module PSDiagnostics -Force -Prefix PS
```

<span data-ttu-id="ce404-184">Первая команда импортирует модуль **PSDiagnostics** .</span><span class="sxs-lookup"><span data-stu-id="ce404-184">The first command imports the **PSDiagnostics** module.</span></span> <span data-ttu-id="ce404-185">Вторая команда импортирует модуль, на этот раз с помощью параметра **Prefix**.</span><span class="sxs-lookup"><span data-stu-id="ce404-185">The second command imports the module again, this time using the **Prefix** parameter.</span></span>

<span data-ttu-id="ce404-186">Без параметра **Force** сеанс будет содержать две копии каждого командлета **PSDiagnostics** , один из которых имеет стандартное имя и имя с префиксом.</span><span class="sxs-lookup"><span data-stu-id="ce404-186">Without the **Force** parameter, the session would include two copies of each **PSDiagnostics** cmdlet, one with the standard name and one with the prefixed name.</span></span>

### <span data-ttu-id="ce404-187">Пример 9. выполнение команд, скрытых с помощью импортированных команд</span><span class="sxs-lookup"><span data-stu-id="ce404-187">Example 9: Run commands that have been hidden by imported commands</span></span>

<span data-ttu-id="ce404-188">В этом примере показано, как выполнить команды, которые были скрыты импортированными командами.</span><span class="sxs-lookup"><span data-stu-id="ce404-188">This example shows how to run commands that have been hidden by imported commands.</span></span> <span data-ttu-id="ce404-189">Модуль **тестмодуле** включает функцию с именем `Get-Date` , которая возвращает год и день года.</span><span class="sxs-lookup"><span data-stu-id="ce404-189">The **TestModule** module includes a function named `Get-Date` that returns the year and day of the year.</span></span>

```powershell
Get-Date
```

```Output
Thursday, August 15, 2019 2:26:12 PM
```

```powershell
Import-Module TestModule
Get-Date
```

```Output
19227
```

```powershell
Get-Command Get-Date -All | Format-Table -Property CommandType, Name, ModuleName -AutoSize
```

```Output
CommandType     Name         ModuleName
-----------     ----         ----------
Function        Get-Date     TestModule
Cmdlet          Get-Date     Microsoft.PowerShell.Utility
```

```powershell
Microsoft.PowerShell.Utility\Get-Date
```

```Output
Thursday, August 15, 2019 2:28:31 PM
```

<span data-ttu-id="ce404-190">Первый `Get-Date` командлет возвращает объект **DateTime** с текущей датой.</span><span class="sxs-lookup"><span data-stu-id="ce404-190">The first `Get-Date` cmdlet returns a **DateTime** object with the current date.</span></span> <span data-ttu-id="ce404-191">После импорта модуля **тестмодуле** `Get-Date` возвращает год и день года.</span><span class="sxs-lookup"><span data-stu-id="ce404-191">After importing the **TestModule** module, `Get-Date` returns the year and day of the year.</span></span>

<span data-ttu-id="ce404-192">Используя параметр **ALL** параметра, вы `Get-Command` увидите все `Get-Date` команды в сеансе.</span><span class="sxs-lookup"><span data-stu-id="ce404-192">Using the **All** parameter of `Get-Command` show all the `Get-Date` commands in the session.</span></span> <span data-ttu-id="ce404-193">Результаты показывают, что `Get-Date` в сеансе есть две команды: функция из модуля **тестмодуле** и командлет из модуля **Microsoft. PowerShell. Utility** .</span><span class="sxs-lookup"><span data-stu-id="ce404-193">The results show that there are two `Get-Date` commands in the session, a function from the **TestModule** module and a cmdlet from the **Microsoft.PowerShell.Utility** module.</span></span>

<span data-ttu-id="ce404-194">Поскольку функции имеют приоритет над командлетами, `Get-Date` вместо командлета выполняется функция из модуля **тестмодуле** `Get-Date` .</span><span class="sxs-lookup"><span data-stu-id="ce404-194">Because functions take precedence over cmdlets, the `Get-Date` function from the **TestModule** module runs, instead of the `Get-Date` cmdlet.</span></span> <span data-ttu-id="ce404-195">Чтобы запустить исходную версию `Get-Date` , необходимо уточнить имя команды с помощью имени модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-195">To run the original version of `Get-Date`, you must qualify the command name with the module name.</span></span>

<span data-ttu-id="ce404-196">Дополнительные сведения о приоритетах команд в PowerShell см. в разделе [about_Command_Precedence](about/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="ce404-196">For more information about command precedence in PowerShell, see [about_Command_Precedence](about/about_Command_Precedence.md).</span></span>

### <span data-ttu-id="ce404-197">Пример 10. Импорт минимальной версии модуля</span><span class="sxs-lookup"><span data-stu-id="ce404-197">Example 10: Import a minimum version of a module</span></span>

<span data-ttu-id="ce404-198">В этом примере импортируется модуль **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="ce404-198">This example imports the **PowerShellGet** module.</span></span> <span data-ttu-id="ce404-199">Параметр **MinimumVersion** `Import-Module` в используется для импорта только 2.0.0 версии или выше модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-199">It uses the **MinimumVersion** parameter of `Import-Module` to import only version 2.0.0 or greater of the module.</span></span>

```powershell
Import-Module -Name PowerShellGet -MinimumVersion 2.0.0
```

<span data-ttu-id="ce404-200">Можно также использовать параметр **RequiredVersion** для импорта определенной версии модуля или использовать параметры **модуля** и **версии** `#Requires` ключевого слова, чтобы требовать определенную версию модуля в скрипте.</span><span class="sxs-lookup"><span data-stu-id="ce404-200">You can also use the **RequiredVersion** parameter to import a particular version of a module, or use the **Module** and **Version** parameters of the `#Requires` keyword to require a particular version of a module in a script.</span></span>

### <span data-ttu-id="ce404-201">Пример 11. Импорт с использованием полного имени</span><span class="sxs-lookup"><span data-stu-id="ce404-201">Example 11: Import using a fully qualified name</span></span>

<span data-ttu-id="ce404-202">В этом примере выполняется импорт определенной версии модуля с помощью FullyQualifiedName.</span><span class="sxs-lookup"><span data-stu-id="ce404-202">This example imports a specific version of a module using the FullyQualifiedName.</span></span>

```powershell
PS> Get-Module -ListAvailable PowerShellGet | Select-Object Name, Version

Name          Version
----          -------
PowerShellGet 2.2.1
PowerShellGet 2.1.3
PowerShellGet 2.1.2
PowerShellGet 1.0.0.1

PS> Import-Module -FullyQualifiedName @{ModuleName = 'PowerShellGet'; ModuleVersion = '2.1.3' }
```

### <span data-ttu-id="ce404-203">Пример 12. Импорт с использованием полного пути</span><span class="sxs-lookup"><span data-stu-id="ce404-203">Example 12: Import using a fully qualified path</span></span>

<span data-ttu-id="ce404-204">В этом примере выполняется импорт определенной версии модуля с использованием полного пути.</span><span class="sxs-lookup"><span data-stu-id="ce404-204">This example imports a specific version of a module using the fully qualified path.</span></span>

```powershell
PS> Get-Module -ListAvailable PowerShellGet | Select-Object Path

Path
----
C:\Program Files\PowerShell\Modules\PowerShellGet\2.2.1\PowerShellGet.psd1
C:\program files\powershell\6\Modules\PowerShellGet\PowerShellGet.psd1
C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\2.1.2\PowerShellGet.psd1
C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PowerShellGet.psd1

PS> Import-Module -Name 'C:\Program Files\PowerShell\Modules\PowerShellGet\2.2.1\PowerShellGet.psd1'
```

### <span data-ttu-id="ce404-205">Пример 13. импорт модуля с удаленного компьютера</span><span class="sxs-lookup"><span data-stu-id="ce404-205">Example 13: Import a module from a remote computer</span></span>

<span data-ttu-id="ce404-206">В этом примере показано, как использовать `Import-Module` командлет для импорта модуля с удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="ce404-206">This example shows how to use the `Import-Module` cmdlet to import a module from a remote computer.</span></span>
<span data-ttu-id="ce404-207">Эта команда использует функцию неявного удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ce404-207">This command uses the Implicit Remoting feature of PowerShell.</span></span>

<span data-ttu-id="ce404-208">При импорте модулей из другого сеанса можно применять командлеты в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="ce404-208">When you import modules from another session, you can use the cmdlets in the current session.</span></span>
<span data-ttu-id="ce404-209">Однако команды, использующие командлеты, выполняются в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="ce404-209">However, commands that use the cmdlets run in the remote session.</span></span>

```powershell
$s = New-PSSession -ComputerName Server01
Get-Module -PSSession $s -ListAvailable -Name NetSecurity
```

```Output
ModuleType Name             ExportedCommands
---------- ----             ----------------
Manifest   NetSecurity      {New-NetIPsecAuthProposal, New-NetIPsecMainModeCryptoProposal, New-Ne...
```

```powershell
Import-Module -PSSession $s -Name NetSecurity
Get-Command -Module NetSecurity -Name Get-*Firewall*
```

```Output
CommandType     Name                                               ModuleName
-----------     ----                                               ----------
Function        Get-NetFirewallAddressFilter                       NetSecurity
Function        Get-NetFirewallApplicationFilter                   NetSecurity
Function        Get-NetFirewallInterfaceFilter                     NetSecurity
Function        Get-NetFirewallInterfaceTypeFilter                 NetSecurity
Function        Get-NetFirewallPortFilter                          NetSecurity
Function        Get-NetFirewallProfile                             NetSecurity
Function        Get-NetFirewallRule                                NetSecurity
Function        Get-NetFirewallSecurityFilter                      NetSecurity
Function        Get-NetFirewallServiceFilter                       NetSecurity
Function        Get-NetFirewallSetting                             NetSecurity
```

```powershell
Get-NetFirewallRule -DisplayName "Windows Remote Management*" |
  Format-Table -Property DisplayName, Name -AutoSize
```

```Output
DisplayName                                              Name
-----------                                              ----
Windows Remote Management (HTTP-In)                      WINRM-HTTP-In-TCP
Windows Remote Management (HTTP-In)                      WINRM-HTTP-In-TCP-PUBLIC
Windows Remote Management - Compatibility Mode (HTTP-In) WINRM-HTTP-Compat-In-TCP
```

<span data-ttu-id="ce404-210">`New-PSSession` создает удаленный сеанс (**PSSession**) на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="ce404-210">`New-PSSession` creates a remote session (**PSSession**) to the Server01 computer.</span></span> <span data-ttu-id="ce404-211">**Сеанс PSSession** сохраняется в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="ce404-211">The **PSSession** is saved in the `$s` variable.</span></span>

<span data-ttu-id="ce404-212">Запуск `Get-Module` с параметром **PSSession** показывает, что модуль **NetSecurity** установлен и доступен на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ce404-212">Running `Get-Module` with the **PSSession** parameter shows that the **NetSecurity** module is installed and available on the remote computer.</span></span> <span data-ttu-id="ce404-213">Эта команда эквивалентна использованию `Invoke-Command` командлета для выполнения `Get-Module` команды в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="ce404-213">This command is equivalent to using the `Invoke-Command` cmdlet to run `Get-Module` command in the remote session.</span></span> <span data-ttu-id="ce404-214">Например: (`Invoke-Command $s {Get-Module -ListAvailable -Name NetSecurity`</span><span class="sxs-lookup"><span data-stu-id="ce404-214">For example: (`Invoke-Command $s {Get-Module -ListAvailable -Name NetSecurity`</span></span>

<span data-ttu-id="ce404-215">`Import-Module`При выполнении с параметром **PSSession** импортирует модуль **NetSecurity** с удаленного компьютера в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="ce404-215">Running `Import-Module` with the **PSSession** parameter imports the **NetSecurity** module from the remote computer into the current session.</span></span> <span data-ttu-id="ce404-216">`Get-Command`Командлет используется для получения команд, начинающихся с **Get** и включая **брандмауэр** из модуля **NetSecurity** .</span><span class="sxs-lookup"><span data-stu-id="ce404-216">The `Get-Command` cmdlet is used to get commands that begin with **Get** and include **Firewall** from the **NetSecurity** module.</span></span> <span data-ttu-id="ce404-217">Выходные данные подтверждают, что модуль и его командлеты были импортированы в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="ce404-217">The output confirms that the module and its cmdlets were imported into the current session.</span></span>

<span data-ttu-id="ce404-218">Затем `Get-NetFirewallRule` командлет получает служба удаленного управления Windows правила брандмауэра на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="ce404-218">Next, the `Get-NetFirewallRule` cmdlet gets Windows Remote Management firewall rules on the Server01 computer.</span></span> <span data-ttu-id="ce404-219">Это эквивалентно использованию `Invoke-Command` командлета для запуска `Get-NetFirewallRule` в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="ce404-219">This is equivalent to using the `Invoke-Command` cmdlet to run `Get-NetFirewallRule` on the remote session.</span></span>

### <span data-ttu-id="ce404-220">Пример 14. Управление хранилищем на удаленном компьютере без операционной системы Windows</span><span class="sxs-lookup"><span data-stu-id="ce404-220">Example 14: Manage storage on a remote computer without the Windows operating system</span></span>

<span data-ttu-id="ce404-221">В этом примере администратор компьютера установил поставщик WMI для обнаружения модуля, который позволяет использовать команды CIM, предназначенные для поставщика.</span><span class="sxs-lookup"><span data-stu-id="ce404-221">In this example, the administrator of the computer has installed the Module Discovery WMI provider, which allows you to use CIM commands that are designed for the provider.</span></span>

<span data-ttu-id="ce404-222">`New-CimSession`Командлет создает сеанс на удаленном компьютере с именем RSDGF03.</span><span class="sxs-lookup"><span data-stu-id="ce404-222">The `New-CimSession` cmdlet creates a session on the remote computer named RSDGF03.</span></span> <span data-ttu-id="ce404-223">Сеанс подключается к службе WMI на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ce404-223">The session connects to the WMI service on the remote computer.</span></span> <span data-ttu-id="ce404-224">Сеанс CIM сохраняется в `$cs` переменной.</span><span class="sxs-lookup"><span data-stu-id="ce404-224">The CIM session is saved in the `$cs` variable.</span></span>
<span data-ttu-id="ce404-225">`Import-Module` использует **CimSession** в `$cs` для импорта модуля CIM **хранилища** с компьютера RSDGF03.</span><span class="sxs-lookup"><span data-stu-id="ce404-225">`Import-Module` uses the **CimSession** in `$cs` to import the **Storage** CIM module from the RSDGF03 computer.</span></span>

<span data-ttu-id="ce404-226">`Get-Command`Командлет отображает `Get-Disk` команду в модуле **Storage** .</span><span class="sxs-lookup"><span data-stu-id="ce404-226">The `Get-Command` cmdlet shows the `Get-Disk` command in the **Storage** module.</span></span> <span data-ttu-id="ce404-227">При импорте модуля CIM в локальный сеанс PowerShell преобразует файлы CDXML для каждой команды в скрипты PowerShell, которые отображаются как функции в локальном сеансе.</span><span class="sxs-lookup"><span data-stu-id="ce404-227">When you import a CIM module into the local session, PowerShell converts the CDXML files for each command into PowerShell scripts, which appear as functions in the local session.</span></span>

<span data-ttu-id="ce404-228">Хотя он `Get-Disk` вводится в локальный сеанс, командлет выполняется неявно на удаленном компьютере, с которого он был импортирован.</span><span class="sxs-lookup"><span data-stu-id="ce404-228">Although `Get-Disk` is typed in the local session, the cmdlet implicitly runs on the remote computer from which it was imported.</span></span> <span data-ttu-id="ce404-229">Команда возвращает объекты с удаленного компьютера в локальный сеанс.</span><span class="sxs-lookup"><span data-stu-id="ce404-229">The command returns objects from the remote computer to the local session.</span></span>

```powershell
$cs = New-CimSession -ComputerName RSDGF03
Import-Module -CimSession $cs -Name Storage
# Importing a CIM module, converts the CDXML files for each command into PowerShell scripts.
# These appear as functions in the local session.
Get-Command Get-Disk
```

```Output
CommandType     Name                  ModuleName
-----------     ----                  ----------
Function        Get-Disk              Storage
```

```powershell
# Use implicit remoting to query disks on the remote computer from which the module was imported.
Get-Disk
```

```Output
Number Friendly Name           OperationalStatus  Total Size Partition Style
------ -------------           -----------------  ---------- ---------------
0      Virtual HD ATA Device   Online                  40 GB MBR
```

## <span data-ttu-id="ce404-230">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ce404-230">PARAMETERS</span></span>

### <span data-ttu-id="ce404-231">-Alias</span><span class="sxs-lookup"><span data-stu-id="ce404-231">-Alias</span></span>

<span data-ttu-id="ce404-232">Задает псевдонимы, которые этот командлет импортирует из модуля в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="ce404-232">Specifies the aliases that this cmdlet imports from the module into the current session.</span></span> <span data-ttu-id="ce404-233">Введите разделенный запятыми список псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="ce404-233">Enter a comma-separated list of aliases.</span></span> <span data-ttu-id="ce404-234">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="ce404-234">Wildcard characters are permitted.</span></span>

<span data-ttu-id="ce404-235">Некоторые модули автоматически экспортируют выбранные псевдонимы в сеанс при импорте модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-235">Some modules automatically export selected aliases into your session when you import the module.</span></span>
<span data-ttu-id="ce404-236">Этот параметр позволяет выбрать один из экспортированных псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="ce404-236">This parameter lets you select from among the exported aliases.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="ce404-237">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="ce404-237">-ArgumentList</span></span>

<span data-ttu-id="ce404-238">Указывает массив аргументов или значений параметров, которые передаются в модуль скрипта во время выполнения `Import-Module` команды.</span><span class="sxs-lookup"><span data-stu-id="ce404-238">Specifies an array of arguments, or parameter values, that are passed to a script module during the `Import-Module` command.</span></span> <span data-ttu-id="ce404-239">Этот параметр допустим только при импорте модуля скрипта.</span><span class="sxs-lookup"><span data-stu-id="ce404-239">This parameter is valid only when you're importing a script module.</span></span>

<span data-ttu-id="ce404-240">Можно также ссылаться на параметр **ArgumentList** по его псевдониму **args**.</span><span class="sxs-lookup"><span data-stu-id="ce404-240">You can also refer to the **ArgumentList** parameter by its alias, **args**.</span></span> <span data-ttu-id="ce404-241">Дополнительные сведения о поведении **ArgumentList** см. в разделе [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="ce404-241">For more information about the behavior of **ArgumentList**, see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce404-242">-AsCustomObject</span><span class="sxs-lookup"><span data-stu-id="ce404-242">-AsCustomObject</span></span>

<span data-ttu-id="ce404-243">Указывает, что этот командлет возвращает пользовательский объект с элементами, представляющими импортированные элементы модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-243">Indicates that this cmdlet returns a custom object with members that represent the imported module members.</span></span> <span data-ttu-id="ce404-244">Этот параметр допустим только для модулей скриптов.</span><span class="sxs-lookup"><span data-stu-id="ce404-244">This parameter is valid only for script modules.</span></span>

<span data-ttu-id="ce404-245">При использовании параметра **AsCustomObject** `Import-Module` импортирует элементы модуля в сеанс, а затем возвращает объект **PSCustomObject** вместо объекта **PSModuleInfo** .</span><span class="sxs-lookup"><span data-stu-id="ce404-245">When you use the **AsCustomObject** parameter, `Import-Module` imports the module members into the session and then returns a **PSCustomObject** object instead of a **PSModuleInfo** object.</span></span> <span data-ttu-id="ce404-246">Пользовательский объект можно сохранить в переменную и использовать точку для вызова элементов.</span><span class="sxs-lookup"><span data-stu-id="ce404-246">You can save the custom object in a variable and use dot notation to invoke the members.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce404-247">-Assembly</span><span class="sxs-lookup"><span data-stu-id="ce404-247">-Assembly</span></span>

<span data-ttu-id="ce404-248">Задает массив объектов Assembly.</span><span class="sxs-lookup"><span data-stu-id="ce404-248">Specifies an array of assembly objects.</span></span> <span data-ttu-id="ce404-249">Этот командлет импортирует командлеты и поставщики, реализованные в указанных объектах сборки.</span><span class="sxs-lookup"><span data-stu-id="ce404-249">This cmdlet imports the cmdlets and providers implemented in the specified assembly objects.</span></span> <span data-ttu-id="ce404-250">Введите переменную, которая содержит объекты сборки, или команду, которая создает объекты сборки.</span><span class="sxs-lookup"><span data-stu-id="ce404-250">Enter a variable that contains assembly objects or a command that creates assembly objects.</span></span> <span data-ttu-id="ce404-251">Также можно передать объект сборки в `Import-Module` .</span><span class="sxs-lookup"><span data-stu-id="ce404-251">You can also pipe an assembly object to `Import-Module`.</span></span>

<span data-ttu-id="ce404-252">При использовании этого параметра импортируются только командлеты и поставщики, реализованные в указанных сборках.</span><span class="sxs-lookup"><span data-stu-id="ce404-252">When you use this parameter, only the cmdlets and providers implemented by the specified assemblies are imported.</span></span> <span data-ttu-id="ce404-253">Если модуль содержит другие файлы, они не импортируются и могут отсутствовать важные члены модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-253">If the module contains other files, they aren't imported, and you might be missing important members of the module.</span></span> <span data-ttu-id="ce404-254">Этот параметр используется для отладки и тестирования модуля, а также при указании его использования автором модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-254">Use this parameter for debugging and testing the module, or when you're instructed to use it by the module author.</span></span>

```yaml
Type: System.Reflection.Assembly[]
Parameter Sets: Assembly
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ce404-255">-Цимнамеспаце</span><span class="sxs-lookup"><span data-stu-id="ce404-255">-CimNamespace</span></span>

<span data-ttu-id="ce404-256">Задает пространство имен для альтернативного поставщика CIM, предоставляющего модули CIM.</span><span class="sxs-lookup"><span data-stu-id="ce404-256">Specifies the namespace of an alternate CIM provider that exposes CIM modules.</span></span> <span data-ttu-id="ce404-257">Значение по умолчанию — пространство имен поставщика модуля обнаружения WMI.</span><span class="sxs-lookup"><span data-stu-id="ce404-257">The default value is the namespace of the Module Discovery WMI provider.</span></span>

<span data-ttu-id="ce404-258">Этот параметр используется для импорта модулей CIM с компьютеров и устройств, которые не работают под управлением операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="ce404-258">Use this parameter to import CIM modules from computers and devices that aren't running a Windows operating system.</span></span>

<span data-ttu-id="ce404-259">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="ce404-259">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="ce404-260">-Цимресаурцеури</span><span class="sxs-lookup"><span data-stu-id="ce404-260">-CimResourceUri</span></span>

<span data-ttu-id="ce404-261">Задает альтернативное расположение для модулей CIM.</span><span class="sxs-lookup"><span data-stu-id="ce404-261">Specifies an alternate location for CIM modules.</span></span> <span data-ttu-id="ce404-262">Значение по умолчанию — URI ресурса поставщика модуля обнаружения WMI на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ce404-262">The default value is the resource URI of the Module Discovery WMI provider on the remote computer.</span></span>

<span data-ttu-id="ce404-263">Этот параметр используется для импорта модулей CIM с компьютеров и устройств, которые не работают под управлением операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="ce404-263">Use this parameter to import CIM modules from computers and devices that aren't running a Windows operating system.</span></span>

<span data-ttu-id="ce404-264">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="ce404-264">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="ce404-265">-CimSession</span><span class="sxs-lookup"><span data-stu-id="ce404-265">-CimSession</span></span>

<span data-ttu-id="ce404-266">Указывает сеанс CIM на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ce404-266">Specifies a CIM session on the remote computer.</span></span> <span data-ttu-id="ce404-267">Введите переменную, которая содержит сеанс CIM, или команду, которая получает сеанс CIM, например команду [Get-CimSession](../CimCmdlets/Get-CimSession.md) .</span><span class="sxs-lookup"><span data-stu-id="ce404-267">Enter a variable that contains the CIM session or a command that gets the CIM session, such as a [Get-CimSession](../CimCmdlets/Get-CimSession.md) command.</span></span>

<span data-ttu-id="ce404-268">`Import-Module` использует соединение с сеансом CIM для импорта модулей с удаленного компьютера в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="ce404-268">`Import-Module` uses the CIM session connection to import modules from the remote computer into the current session.</span></span> <span data-ttu-id="ce404-269">При использовании команд из импортированного модуля в текущем сеансе команды выполняются на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ce404-269">When you use the commands from the imported module in the current session, the commands run on the remote computer.</span></span>

<span data-ttu-id="ce404-270">Этот параметр можно использовать для импорта модулей с компьютеров и устройств, которые не работают под управлением операционной системы Windows, и компьютеров Windows с PowerShell, но не поддерживают удаленное взаимодействие PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ce404-270">You can use this parameter to import modules from computers and devices that aren't running the Windows operating system, and Windows computers that have PowerShell, but don't have PowerShell remoting enabled.</span></span>

<span data-ttu-id="ce404-271">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="ce404-271">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="ce404-272">Командлет</span><span class="sxs-lookup"><span data-stu-id="ce404-272">-Cmdlet</span></span>

<span data-ttu-id="ce404-273">Указывает массив командлетов, которые этот командлет импортирует из модуля в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="ce404-273">Specifies an array of cmdlets that this cmdlet imports from the module into the current session.</span></span>
<span data-ttu-id="ce404-274">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="ce404-274">Wildcard characters are permitted.</span></span>

<span data-ttu-id="ce404-275">Некоторые модули автоматически экспортируют выбранные командлеты в сеанс при импорте модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-275">Some modules automatically export selected cmdlets into your session when you import the module.</span></span>
<span data-ttu-id="ce404-276">Этот параметр позволяет выбрать один из экспортированных командлетов.</span><span class="sxs-lookup"><span data-stu-id="ce404-276">This parameter lets you select from among the exported cmdlets.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="ce404-277">-DisableNameChecking</span><span class="sxs-lookup"><span data-stu-id="ce404-277">-DisableNameChecking</span></span>

<span data-ttu-id="ce404-278">Указывает, что этот командлет подавляет сообщение, выдающее предупреждение при импорте командлета или функции, имя которой включает неутвержденную команду или запрещенный символ.</span><span class="sxs-lookup"><span data-stu-id="ce404-278">Indicates that this cmdlet suppresses the message that warns you when you import a cmdlet or function whose name includes an unapproved verb or a prohibited character.</span></span>

<span data-ttu-id="ce404-279">По умолчанию, когда импортируемый модуль экспортирует командлеты или функции с неодобренными командами в именах, PowerShell выводит следующее предупреждающее сообщение:</span><span class="sxs-lookup"><span data-stu-id="ce404-279">By default, when a module that you import exports cmdlets or functions that have unapproved verbs in their names, PowerShell displays the following warning message:</span></span>

> <span data-ttu-id="ce404-280">ПРЕДУПРЕЖДЕНИЕ. Некоторые импортированные имена команд включают неутвержденные команды, которые могут сделать их менее обнаруживаемыми.</span><span class="sxs-lookup"><span data-stu-id="ce404-280">WARNING: Some imported command names include unapproved verbs which might make them less discoverable.</span></span> <span data-ttu-id="ce404-281">Чтобы получить подробные сведения, используйте параметр Verbose, или введите Get-Verb, чтобы просмотреть список утвержденных команд.</span><span class="sxs-lookup"><span data-stu-id="ce404-281">Use the Verbose parameter for more detail or type Get-Verb to see the list of approved verbs.</span></span>

<span data-ttu-id="ce404-282">Это сообщение является всего лишь предупреждением.</span><span class="sxs-lookup"><span data-stu-id="ce404-282">This message is only a warning.</span></span> <span data-ttu-id="ce404-283">Импорт осуществляется для всего модуля, включая недопустимые команды.</span><span class="sxs-lookup"><span data-stu-id="ce404-283">The complete module is still imported, including the non-conforming commands.</span></span> <span data-ttu-id="ce404-284">Хотя это сообщение отображается для пользователей модуля, проблема с именованием должна быть устранена автором модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-284">Although the message is displayed to module users, the naming problem should be fixed by the module author.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce404-285">-Force</span><span class="sxs-lookup"><span data-stu-id="ce404-285">-Force</span></span>

<span data-ttu-id="ce404-286">Этот параметр приводит к тому, что модуль загружается или перегружается поверх текущего.</span><span class="sxs-lookup"><span data-stu-id="ce404-286">This parameter causes a module to be loaded, or reloaded, over top of the current one.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce404-287">-FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="ce404-287">-FullyQualifiedName</span></span>

<span data-ttu-id="ce404-288">Указывает полное имя модуля в виде хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="ce404-288">Specifies the fully qualified name of the module as a hash table.</span></span> <span data-ttu-id="ce404-289">Значение может быть сочетанием строк и хэш-таблиц.</span><span class="sxs-lookup"><span data-stu-id="ce404-289">The value can be a combination of strings and hash tables.</span></span> <span data-ttu-id="ce404-290">Хэш-таблица содержит следующие ключи.</span><span class="sxs-lookup"><span data-stu-id="ce404-290">The hash table has the following keys.</span></span>

- <span data-ttu-id="ce404-291">`ModuleName` - **Обязательное требование** Указывает имя модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-291">`ModuleName` - **Required** Specifies the module name.</span></span>
- <span data-ttu-id="ce404-292">`GUID` - **Необязательно** Указывает идентификатор GUID модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-292">`GUID` - **Optional** Specifies the GUID of the module.</span></span>
- <span data-ttu-id="ce404-293">**Также необходимо** указать один из трех указанных ниже ключей.</span><span class="sxs-lookup"><span data-stu-id="ce404-293">It's also **Required** to specify one of the three below keys.</span></span> <span data-ttu-id="ce404-294">Эти ключи нельзя использовать совместно.</span><span class="sxs-lookup"><span data-stu-id="ce404-294">These keys can't be used together.</span></span>
  - <span data-ttu-id="ce404-295">`ModuleVersion` — Указывает минимальную допустимую версию модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-295">`ModuleVersion` - Specifies a minimum acceptable version of the module.</span></span>
  - <span data-ttu-id="ce404-296">`RequiredVersion` — Указывает точную, требуемую версию модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-296">`RequiredVersion` - Specifies an exact, required version of the module.</span></span>
  - <span data-ttu-id="ce404-297">`MaximumVersion` — Указывает максимально допустимую версию модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-297">`MaximumVersion` - Specifies the maximum acceptable version of the module.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: FullyQualifiedName, FullyQualifiedNameAndPSSession
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ce404-298">-Function</span><span class="sxs-lookup"><span data-stu-id="ce404-298">-Function</span></span>

<span data-ttu-id="ce404-299">Указывает массив функций, которые этот командлет импортирует из модуля в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="ce404-299">Specifies an array of functions that this cmdlet imports from the module into the current session.</span></span>
<span data-ttu-id="ce404-300">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="ce404-300">Wildcard characters are permitted.</span></span> <span data-ttu-id="ce404-301">Некоторые модули автоматически экспортируют выбранные функции в сеанс при импорте модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-301">Some modules automatically export selected functions into your session when you import the module.</span></span> <span data-ttu-id="ce404-302">Этот параметр позволяет выбрать один из экспортированных функций.</span><span class="sxs-lookup"><span data-stu-id="ce404-302">This parameter lets you select from among the exported functions.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="ce404-303">-Global</span><span class="sxs-lookup"><span data-stu-id="ce404-303">-Global</span></span>

<span data-ttu-id="ce404-304">Указывает, что этот командлет импортирует модули в глобальное состояние сеанса, чтобы они были доступны для всех команд в сеансе.</span><span class="sxs-lookup"><span data-stu-id="ce404-304">Indicates that this cmdlet imports modules into the global session state so they are available to all commands in the session.</span></span>

<span data-ttu-id="ce404-305">По умолчанию при `Import-Module` вызове командлета из командной строки, файла скрипта или сценария ScriptBlock все команды импортируются в глобальное состояние сеанса.</span><span class="sxs-lookup"><span data-stu-id="ce404-305">By default, when `Import-Module` cmdlet is called from the command prompt, script file, or scriptblock, all the commands are imported into the global session state.</span></span>

<span data-ttu-id="ce404-306">При вызове из другого модуля `Import-Module` командлет импортирует команды в модуль, включая команды из вложенных модулей, в состояние сеанса вызывающего модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-306">When invoked from another module, `Import-Module` cmdlet imports the commands in a module, including commands from nested modules, into the calling module's session state.</span></span>

> [!TIP]
> <span data-ttu-id="ce404-307">Следует избегать вызова `Import-Module` из модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-307">You should avoid calling `Import-Module` from within a module.</span></span> <span data-ttu-id="ce404-308">Вместо этого следует объявить целевой модуль как вложенный модуль в манифесте родительского модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-308">Instead, declare the target module as a nested module in the parent module's manifest.</span></span> <span data-ttu-id="ce404-309">Объявление вложенных модулей повышает возможность обнаружения зависимостей.</span><span class="sxs-lookup"><span data-stu-id="ce404-309">Declaring nested modules improves the discoverability of dependencies.</span></span>

<span data-ttu-id="ce404-310">Параметр **Global** аналогичен параметру **Scope** со значением **Global**.</span><span class="sxs-lookup"><span data-stu-id="ce404-310">The **Global** parameter is equivalent to the **Scope** parameter with a value of **Global**.</span></span>

<span data-ttu-id="ce404-311">Чтобы ограничить команды, экспортируемые модулем, используйте `Export-ModuleMember` команду в модуле script.</span><span class="sxs-lookup"><span data-stu-id="ce404-311">To restrict the commands that a module exports, use an `Export-ModuleMember` command in the script module.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce404-312">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="ce404-312">-MaximumVersion</span></span>

<span data-ttu-id="ce404-313">Указывает максимальную версию.</span><span class="sxs-lookup"><span data-stu-id="ce404-313">Specifies a maximum version.</span></span> <span data-ttu-id="ce404-314">Этот командлет импортирует только версию модуля, которая меньше или равна указанному значению.</span><span class="sxs-lookup"><span data-stu-id="ce404-314">This cmdlet imports only a version of the module that is less than or equal to the specified value.</span></span> <span data-ttu-id="ce404-315">Если версия не соответствует требованиям, функция `Import-Module` возвращает ошибку.</span><span class="sxs-lookup"><span data-stu-id="ce404-315">If no version qualifies, `Import-Module` returns an error.</span></span>

```yaml
Type: System.String
Parameter Sets: Name, PSSession, CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce404-316">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="ce404-316">-MinimumVersion</span></span>

<span data-ttu-id="ce404-317">Указывает минимальную версию.</span><span class="sxs-lookup"><span data-stu-id="ce404-317">Specifies a minimum version.</span></span> <span data-ttu-id="ce404-318">Этот командлет импортирует только версию модуля, которая больше или равна указанному значению.</span><span class="sxs-lookup"><span data-stu-id="ce404-318">This cmdlet imports only a version of the module that is greater than or equal to the specified value.</span></span> <span data-ttu-id="ce404-319">Используйте имя параметра **MinimumVersion** или его псевдоним, **Version**.</span><span class="sxs-lookup"><span data-stu-id="ce404-319">Use the **MinimumVersion** parameter name or its alias, **Version**.</span></span> <span data-ttu-id="ce404-320">Если версия не соответствует требованиям, `Import-Module` выдает ошибку.</span><span class="sxs-lookup"><span data-stu-id="ce404-320">If no version qualifies, `Import-Module` generates an error.</span></span>

<span data-ttu-id="ce404-321">Чтобы указать точную версию, используйте параметр **RequiredVersion**.</span><span class="sxs-lookup"><span data-stu-id="ce404-321">To specify an exact version, use the **RequiredVersion** parameter.</span></span> <span data-ttu-id="ce404-322">Можно также использовать параметры **модуля** и **версии** ключевого слова **#Requires** , чтобы требовать определенную версию модуля в скрипте.</span><span class="sxs-lookup"><span data-stu-id="ce404-322">You can also use the **Module** and **Version** parameters of the **#Requires** keyword to require a specific version of a module in a script.</span></span>

<span data-ttu-id="ce404-323">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="ce404-323">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Version
Parameter Sets: Name, PSSession, CimSession
Aliases: Version

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce404-324">-ModuleInfo</span><span class="sxs-lookup"><span data-stu-id="ce404-324">-ModuleInfo</span></span>

<span data-ttu-id="ce404-325">Указывает массив объектов модуля для импорта.</span><span class="sxs-lookup"><span data-stu-id="ce404-325">Specifies an array of module objects to import.</span></span> <span data-ttu-id="ce404-326">Введите переменную, содержащую объекты модуля, или команду, которая получает объекты модуля, например следующую команду: `Get-Module -ListAvailable` .</span><span class="sxs-lookup"><span data-stu-id="ce404-326">Enter a variable that contains the module objects, or a command that gets the module objects, such as the following command: `Get-Module -ListAvailable`.</span></span> <span data-ttu-id="ce404-327">Также можно передать объекты модуля в `Import-Module` .</span><span class="sxs-lookup"><span data-stu-id="ce404-327">You can also pipe module objects to `Import-Module`.</span></span>

```yaml
Type: System.Management.Automation.PSModuleInfo[]
Parameter Sets: ModuleInfo
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ce404-328">-Name</span><span class="sxs-lookup"><span data-stu-id="ce404-328">-Name</span></span>

<span data-ttu-id="ce404-329">Задает имена модулей для импорта.</span><span class="sxs-lookup"><span data-stu-id="ce404-329">Specifies the names of the modules to import.</span></span> <span data-ttu-id="ce404-330">Введите имя модуля или имя файла в модуле, например `.psd1` файл,, `.psm1` `.dll` или `.ps1` .</span><span class="sxs-lookup"><span data-stu-id="ce404-330">Enter the name of the module or the name of a file in the module, such as a `.psd1`, `.psm1`, `.dll`, or `.ps1` file.</span></span> <span data-ttu-id="ce404-331">Пути к файлам являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="ce404-331">File paths are optional.</span></span> <span data-ttu-id="ce404-332">Подстановочные знаки не допускаются.</span><span class="sxs-lookup"><span data-stu-id="ce404-332">Wildcard characters aren't permitted.</span></span> <span data-ttu-id="ce404-333">Можно также передать имена модулей и имен файлов в `Import-Module` .</span><span class="sxs-lookup"><span data-stu-id="ce404-333">You can also pipe module names and filenames to `Import-Module`.</span></span>

<span data-ttu-id="ce404-334">Если опустить путь, `Import-Module` ищет модуль в путях, сохраненных в `$env:PSModulePath` переменной среды.</span><span class="sxs-lookup"><span data-stu-id="ce404-334">If you omit a path, `Import-Module` looks for the module in the paths saved in the `$env:PSModulePath` environment variable.</span></span>

<span data-ttu-id="ce404-335">По возможности указывайте только имя модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-335">Specify only the module name whenever possible.</span></span> <span data-ttu-id="ce404-336">Если указать имя файла, импортируются только элементы, реализованные в этом файле.</span><span class="sxs-lookup"><span data-stu-id="ce404-336">When you specify a file name, only the members that are implemented in that file are imported.</span></span> <span data-ttu-id="ce404-337">Если модуль содержит другие файлы, они не импортируются и могут отсутствовать важные члены модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-337">If the module contains other files, they aren't imported, and you might be missing important members of the module.</span></span>

> [!NOTE]
> <span data-ttu-id="ce404-338">Хотя файл скрипта () можно импортировать `.ps1` как модуль, файлы скриптов обычно не структурированы как файл модулей скрипта ( `.psm1` ).</span><span class="sxs-lookup"><span data-stu-id="ce404-338">While it is possible to import a script (`.ps1`) file as a module, script files are usually not structured like script modules file (`.psm1`) file.</span></span> <span data-ttu-id="ce404-339">Импорт файла скрипта не гарантирует, что он будет использоваться в качестве модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-339">Importing a script file does not guarantee that it is usable as a module.</span></span> <span data-ttu-id="ce404-340">Дополнительные сведения см. в разделе [about_Modules](about/about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="ce404-340">For more information, see [about_Modules](about/about_Modules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name, PSSession, CimSession
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="ce404-341">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="ce404-341">-NoClobber</span></span>

<span data-ttu-id="ce404-342">Предотвращает импорт команд, имеющих те же имена, что и существующие команды в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="ce404-342">Prevents importing commands that have the same names as existing commands in the current session.</span></span> <span data-ttu-id="ce404-343">По умолчанию `Import-Module` импортирует все команды экспортированного модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-343">By default, `Import-Module` imports all exported module commands.</span></span>

<span data-ttu-id="ce404-344">Команды с одинаковыми именами могут скрывать или заменять команды в сеансе.</span><span class="sxs-lookup"><span data-stu-id="ce404-344">Commands that have the same names can hide or replace commands in the session.</span></span> <span data-ttu-id="ce404-345">Чтобы избежать конфликта имен команд в сеансе, используйте параметр **Prefix** или **NoClobber**.</span><span class="sxs-lookup"><span data-stu-id="ce404-345">To avoid command name conflicts in a session, use the **Prefix** or **NoClobber** parameters.</span></span> <span data-ttu-id="ce404-346">Дополнительные сведения о конфликтах имен и приоритете команд см. в разделе "Конфликты модулей и имен" в статьях [about_Modules](about/about_Modules.md) и [about_Command_Precedence](about/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="ce404-346">For more information about name conflicts and command precedence, see "Modules and Name Conflicts" in [about_Modules](about/about_Modules.md) and [about_Command_Precedence](about/about_Command_Precedence.md).</span></span>

<span data-ttu-id="ce404-347">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="ce404-347">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce404-348">-PassThru</span><span class="sxs-lookup"><span data-stu-id="ce404-348">-PassThru</span></span>

<span data-ttu-id="ce404-349">Возвращает объект, представляющий элемент, с которым выполняется работа.</span><span class="sxs-lookup"><span data-stu-id="ce404-349">Returns an object representing the item with which you're working.</span></span> <span data-ttu-id="ce404-350">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="ce404-350">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce404-351">— Префикс</span><span class="sxs-lookup"><span data-stu-id="ce404-351">-Prefix</span></span>

<span data-ttu-id="ce404-352">Задает префикс, который добавляется этим командлетом к существительным в именах импортированных элементов модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-352">Specifies a prefix that this cmdlet adds to the nouns in the names of imported module members.</span></span>

<span data-ttu-id="ce404-353">Используйте этот параметр, чтобы избежать конфликтов имен, которые могут возникать, когда имена элементов совпадают с именами элементов в сеансе.</span><span class="sxs-lookup"><span data-stu-id="ce404-353">Use this parameter to avoid name conflicts that might occur when different members in the session have the same name.</span></span> <span data-ttu-id="ce404-354">Этот параметр не изменяет модуль и не влияет на файлы, импортируемые модулем для его собственного использования.</span><span class="sxs-lookup"><span data-stu-id="ce404-354">This parameter does not change the module, and it does not affect files that the module imports for its own use.</span></span> <span data-ttu-id="ce404-355">Они называются вложенными модулями.</span><span class="sxs-lookup"><span data-stu-id="ce404-355">These are known as nested modules.</span></span> <span data-ttu-id="ce404-356">Этот командлет влияет только на имена элементов в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="ce404-356">This cmdlet affects only the names of members in the current session.</span></span>

<span data-ttu-id="ce404-357">Например, если указать префикс UTC, а затем импортировать `Get-Date` командлет, то этот командлет будет известен в сеансе как `Get-UTCDate` , и он не будет путать с исходным `Get-Date` командлетом.</span><span class="sxs-lookup"><span data-stu-id="ce404-357">For example, if you specify the prefix UTC and then import a `Get-Date` cmdlet, the cmdlet is known in the session as `Get-UTCDate`, and it is not confused with the original `Get-Date` cmdlet.</span></span>

<span data-ttu-id="ce404-358">Значение этого параметра имеет приоритет над свойством **DefaultCommandPrefix** модуля, который определяет префикс по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ce404-358">The value of this parameter takes precedence over the **DefaultCommandPrefix** property of the module, which specifies the default prefix.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce404-359">-PSSession</span><span class="sxs-lookup"><span data-stu-id="ce404-359">-PSSession</span></span>

<span data-ttu-id="ce404-360">Указывает управляемый пользователем сеанс PowerShell (**PSSession**), из которого этот командлет импортирует модули в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="ce404-360">Specifies a PowerShell user-managed session (**PSSession**) from which this cmdlet imports modules into the current session.</span></span> <span data-ttu-id="ce404-361">Введите переменную, содержащую **сеанс PSSession** или команду, которая получает **PSSession**, например `Get-PSSession` команду.</span><span class="sxs-lookup"><span data-stu-id="ce404-361">Enter a variable that contains a **PSSession** or a command that gets a **PSSession**, such as a `Get-PSSession` command.</span></span>

<span data-ttu-id="ce404-362">При импорте модуля из другого сеанса в текущий сеанс командлеты из модуля в текущем сеансе можно использовать, как и командлеты из локального модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-362">When you import a module from a different session into the current session, you can use the cmdlets from the module in the current session, just as you would use cmdlets from a local module.</span></span> <span data-ttu-id="ce404-363">Команды, использующие удаленные командлеты, выполняются в удаленном сеансе, но сведения об удаленном взаимодействии управляются в фоновом режиме с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ce404-363">Commands that use the remote cmdlets run in the remote session, but the remoting details are managed in the background by PowerShell.</span></span>

<span data-ttu-id="ce404-364">Этот параметр использует функцию неявного удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ce404-364">This parameter uses the Implicit Remoting feature of PowerShell.</span></span> <span data-ttu-id="ce404-365">Он эквивалентен использованию `Import-PSSession` командлета для импорта определенных модулей из сеанса.</span><span class="sxs-lookup"><span data-stu-id="ce404-365">It is equivalent to using the `Import-PSSession` cmdlet to import particular modules from a session.</span></span>

<span data-ttu-id="ce404-366">`Import-Module` невозможно импортировать модули PowerShell Core из другого сеанса.</span><span class="sxs-lookup"><span data-stu-id="ce404-366">`Import-Module` cannot import PowerShell Core modules from another session.</span></span> <span data-ttu-id="ce404-367">Имена модулей PowerShell Core начинаются с Microsoft. PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ce404-367">The PowerShell Core modules have names that begin with Microsoft.PowerShell.</span></span>

<span data-ttu-id="ce404-368">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="ce404-368">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: PSSession, FullyQualifiedNameAndPSSession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce404-369">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="ce404-369">-RequiredVersion</span></span>

<span data-ttu-id="ce404-370">Указывает версию модуля, который импортирует этот командлет.</span><span class="sxs-lookup"><span data-stu-id="ce404-370">Specifies a version of the module that this cmdlet imports.</span></span> <span data-ttu-id="ce404-371">Если версия не установлена, `Import-Module` создает ошибку.</span><span class="sxs-lookup"><span data-stu-id="ce404-371">If the version is not installed, `Import-Module` generates an error.</span></span>

<span data-ttu-id="ce404-372">По умолчанию `Import-Module` импортирует модуль без проверки номера версии.</span><span class="sxs-lookup"><span data-stu-id="ce404-372">By default, `Import-Module` imports the module without checking the version number.</span></span>

<span data-ttu-id="ce404-373">Чтобы указать минимальную версию, используйте параметр **MinimumVersion**.</span><span class="sxs-lookup"><span data-stu-id="ce404-373">To specify a minimum version, use the **MinimumVersion** parameter.</span></span> <span data-ttu-id="ce404-374">Можно также использовать параметры **модуля** и **версии** ключевого слова **#Requires** , чтобы требовать определенную версию модуля в скрипте.</span><span class="sxs-lookup"><span data-stu-id="ce404-374">You can also use the **Module** and **Version** parameters of the **#Requires** keyword to require a specific version of a module in a script.</span></span>

<span data-ttu-id="ce404-375">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="ce404-375">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="ce404-376">Сценарии, использующие **RequiredVersion** для импорта модулей, входящих в состав существующих выпусков операционной системы Windows, не выполняются автоматически в будущих выпусках операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="ce404-376">Scripts that use **RequiredVersion** to import modules that are included with existing releases of the Windows operating system don't automatically run in future releases of the Windows operating system.</span></span> <span data-ttu-id="ce404-377">Это обусловлено тем, что номера версий модулей PowerShell в будущих выпусках операционной системы Windows выше, чем номера версий модулей в существующих выпусках операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="ce404-377">This is because PowerShell module version numbers in future releases of the Windows operating system are higher than module version numbers in existing releases of the Windows operating system.</span></span>

```yaml
Type: System.Version
Parameter Sets: Name, PSSession, CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce404-378">-Scope</span><span class="sxs-lookup"><span data-stu-id="ce404-378">-Scope</span></span>

<span data-ttu-id="ce404-379">Указывает область, в которой этот командлет импортирует модуль.</span><span class="sxs-lookup"><span data-stu-id="ce404-379">Specifies a scope into which this cmdlet imports the module.</span></span>

<span data-ttu-id="ce404-380">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="ce404-380">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="ce404-381">**Глобальный**.</span><span class="sxs-lookup"><span data-stu-id="ce404-381">**Global**.</span></span> <span data-ttu-id="ce404-382">доступно для всех команд в сеансе.</span><span class="sxs-lookup"><span data-stu-id="ce404-382">Available to all commands in the session.</span></span> <span data-ttu-id="ce404-383">Эквивалентно параметру **Global**.</span><span class="sxs-lookup"><span data-stu-id="ce404-383">Equivalent to the **Global** parameter.</span></span>
- <span data-ttu-id="ce404-384">**Локальный**.</span><span class="sxs-lookup"><span data-stu-id="ce404-384">**Local**.</span></span> <span data-ttu-id="ce404-385">доступно только в текущей области.</span><span class="sxs-lookup"><span data-stu-id="ce404-385">Available only in the current scope.</span></span>

<span data-ttu-id="ce404-386">По умолчанию при `Import-Module` вызове командлета из командной строки, файла скрипта или сценария ScriptBlock все команды импортируются в глобальное состояние сеанса.</span><span class="sxs-lookup"><span data-stu-id="ce404-386">By default, when `Import-Module` cmdlet is called from the command prompt, script file, or scriptblock, all the commands are imported into the global session state.</span></span> <span data-ttu-id="ce404-387">С помощью параметра можно `-Scope Local` импортировать содержимое модуля в область скрипта или ScriptBlock.</span><span class="sxs-lookup"><span data-stu-id="ce404-387">You can use the `-Scope Local` parameter to import module content into the script or scriptblock scope.</span></span>

<span data-ttu-id="ce404-388">При вызове из другого модуля `Import-Module` командлет импортирует команды в модуль, включая команды из вложенных модулей, в состояние сеанса вызывающего.</span><span class="sxs-lookup"><span data-stu-id="ce404-388">When invoked from another module, `Import-Module` cmdlet imports the commands in a module, including commands from nested modules, into the caller's session state.</span></span> <span data-ttu-id="ce404-389">Указание `-Scope Global` или `-Global` указывает, что этот командлет импортирует модули в глобальное состояние сеанса, поэтому они доступны для всех команд в сеансе.</span><span class="sxs-lookup"><span data-stu-id="ce404-389">Specifying `-Scope Global` or `-Global` indicates that this cmdlet imports modules into the global session state so they are available to all commands in the session.</span></span>

<span data-ttu-id="ce404-390">Параметр **Global** аналогичен параметру **Scope** со значением **Global**.</span><span class="sxs-lookup"><span data-stu-id="ce404-390">The **Global** parameter is equivalent to the **Scope** parameter with a value of **Global**.</span></span>

<span data-ttu-id="ce404-391">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="ce404-391">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Local, Global

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce404-392">-Variable</span><span class="sxs-lookup"><span data-stu-id="ce404-392">-Variable</span></span>

<span data-ttu-id="ce404-393">Указывает массив переменных, которые этот командлет импортирует из модуля в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="ce404-393">Specifies an array of variables that this cmdlet imports from the module into the current session.</span></span>
<span data-ttu-id="ce404-394">Введите список переменных.</span><span class="sxs-lookup"><span data-stu-id="ce404-394">Enter a list of variables.</span></span> <span data-ttu-id="ce404-395">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="ce404-395">Wildcard characters are permitted.</span></span>

<span data-ttu-id="ce404-396">Некоторые модули автоматически экспортируют выбранные переменные в сеанс при импорте модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-396">Some modules automatically export selected variables into your session when you import the module.</span></span>
<span data-ttu-id="ce404-397">Этот параметр позволяет выбрать один из экспортированных переменных.</span><span class="sxs-lookup"><span data-stu-id="ce404-397">This parameter lets you select from among the exported variables.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="ce404-398">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="ce404-398">CommonParameters</span></span>
<span data-ttu-id="ce404-399">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ce404-399">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ce404-400">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ce404-400">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ce404-401">Входные данные</span><span class="sxs-lookup"><span data-stu-id="ce404-401">INPUTS</span></span>

### <span data-ttu-id="ce404-402">System. String, System. Management. Automation. PSModuleInfo, System. Reflection. Assembly</span><span class="sxs-lookup"><span data-stu-id="ce404-402">System.String, System.Management.Automation.PSModuleInfo, System.Reflection.Assembly</span></span>

<span data-ttu-id="ce404-403">В этот командлет можно передать имя модуля, объект модуля или объект сборки.</span><span class="sxs-lookup"><span data-stu-id="ce404-403">You can pipe a module name, module object, or assembly object to this cmdlet.</span></span>

## <span data-ttu-id="ce404-404">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="ce404-404">OUTPUTS</span></span>

### <span data-ttu-id="ce404-405">None, System. Management. Automation. PSModuleInfo или System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="ce404-405">None, System.Management.Automation.PSModuleInfo, or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="ce404-406">По умолчанию не `Import-Module` создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="ce404-406">By default, `Import-Module` does not generate any output.</span></span> <span data-ttu-id="ce404-407">Если указан параметр **PassThru** , командлет создает объект **System. Management. Automation. PSModuleInfo** , представляющий модуль.</span><span class="sxs-lookup"><span data-stu-id="ce404-407">If you specify the **PassThru** parameter, the cmdlet generates a **System.Management.Automation.PSModuleInfo** object that represents the module.</span></span> <span data-ttu-id="ce404-408">При указании параметра **AsCustomObject** создается объект **PSCustomObject** .</span><span class="sxs-lookup"><span data-stu-id="ce404-408">If you specify the **AsCustomObject** parameter, it generates a **PSCustomObject** object.</span></span>

## <span data-ttu-id="ce404-409">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="ce404-409">NOTES</span></span>

- <span data-ttu-id="ce404-410">Перед импортом модуля необходимо установить модуль на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ce404-410">Before you can import a module, the module must be installed on the local computer.</span></span> <span data-ttu-id="ce404-411">То есть каталог модуля должен быть скопирован в каталог, доступный локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="ce404-411">That is, the module directory must be copied to a directory that is accessible to your local computer.</span></span> <span data-ttu-id="ce404-412">Дополнительные сведения см. в разделе [about_Modules](About/about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="ce404-412">For more information, see [about_Modules](About/about_Modules.md).</span></span>

  <span data-ttu-id="ce404-413">Для импорта модулей, установленных на удаленных компьютерах, можно также использовать параметры **PSSession** и **CIMSession**.</span><span class="sxs-lookup"><span data-stu-id="ce404-413">You can also use the **PSSession** and **CIMSession** parameters to import modules that are installed on remote computers.</span></span> <span data-ttu-id="ce404-414">Однако команды, использующие командлеты в этих модулях, выполняются в удаленном сеансе на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ce404-414">However, commands that use the cmdlets in these modules run in the remote session on the remote computer.</span></span>

- <span data-ttu-id="ce404-415">Если в сеансе импортируются элементы с одинаковым именем и типом, то в PowerShell по умолчанию используется элемент, импортированный последним.</span><span class="sxs-lookup"><span data-stu-id="ce404-415">If you import members with the same name and the same type into your session, PowerShell uses the member imported last by default.</span></span> <span data-ttu-id="ce404-416">Переменные и псевдонимы заменяются, и исходные значения недоступны.</span><span class="sxs-lookup"><span data-stu-id="ce404-416">Variables and aliases are replaced, and the originals aren't accessible.</span></span> <span data-ttu-id="ce404-417">Функции, командлеты и поставщики просто затенены новыми элементами.</span><span class="sxs-lookup"><span data-stu-id="ce404-417">Functions, cmdlets, and providers are merely shadowed by the new members.</span></span> <span data-ttu-id="ce404-418">Доступ к ним можно получить, добавив в имя команды имя своей оснастки, модуля или пути к функции.</span><span class="sxs-lookup"><span data-stu-id="ce404-418">They can be accessed by qualifying the command name with the name of its snap-in, module, or function path.</span></span>

- <span data-ttu-id="ce404-419">Чтобы обновить данные форматирования для команд, импортированных из модуля, используйте `Update-FormatData` командлет.</span><span class="sxs-lookup"><span data-stu-id="ce404-419">To update the formatting data for commands that have been imported from a module, use the `Update-FormatData` cmdlet.</span></span> <span data-ttu-id="ce404-420">`Update-FormatData` также обновляет данные форматирования для команд в сеансе, импортированных из модулей.</span><span class="sxs-lookup"><span data-stu-id="ce404-420">`Update-FormatData` also updates the formatting data for commands in the session that were imported from modules.</span></span> <span data-ttu-id="ce404-421">При изменении файла форматирования для модуля можно выполнить `Update-FormatData` команду, чтобы обновить данные форматирования для импортированных команд.</span><span class="sxs-lookup"><span data-stu-id="ce404-421">If the formatting file for a module changes, you can run an `Update-FormatData` command to update the formatting data for imported commands.</span></span> <span data-ttu-id="ce404-422">Импортировать модуль повторно не требуется.</span><span class="sxs-lookup"><span data-stu-id="ce404-422">You don't need to import the module again.</span></span>

- <span data-ttu-id="ce404-423">Начиная с Windows PowerShell 3,0, основные команды, устанавливаемые с помощью PowerShell, упаковываются в модули.</span><span class="sxs-lookup"><span data-stu-id="ce404-423">Starting in Windows PowerShell 3.0, the core commands that are installed with PowerShell are packaged in modules.</span></span> <span data-ttu-id="ce404-424">В Windows PowerShell 2,0 и в ведущих программах, которые создают сеансы предыдущих версий в более поздних версиях PowerShell, основные команды упаковываются в оснастки (**PSSnapin**).</span><span class="sxs-lookup"><span data-stu-id="ce404-424">In Windows PowerShell 2.0, and in host programs that create older-style sessions in later versions of PowerShell, the core commands are packaged in snap-ins (**PSSnapins**).</span></span> <span data-ttu-id="ce404-425">Исключением является **Microsoft. PowerShell. Core**, который всегда является оснасткой.</span><span class="sxs-lookup"><span data-stu-id="ce404-425">The exception is **Microsoft.PowerShell.Core**, which is always a snap-in.</span></span> <span data-ttu-id="ce404-426">Кроме того, удаленные сеансы, такие как запущенные `New-PSSession` командлетом, являются сеансами предыдущих версий, включающими основные оснастки.</span><span class="sxs-lookup"><span data-stu-id="ce404-426">Also, remote sessions, such as those started by the `New-PSSession` cmdlet, are older-style sessions that include core snap-ins.</span></span>

  <span data-ttu-id="ce404-427">Дополнительные сведения о методе **CreateDefault2** , который создает сеансы нового стиля с основными модулями, см. в описании [метода CreateDefault2](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2).</span><span class="sxs-lookup"><span data-stu-id="ce404-427">For information about the **CreateDefault2** method that creates newer-style sessions with core modules, see the [CreateDefault2 Method](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2).</span></span>

- <span data-ttu-id="ce404-428">В Windows PowerShell 2,0 некоторые значения свойств объекта Module, такие как значения свойств **експортедкмдлетс** и **NestedModules** , не были заполнены до импорта модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-428">In Windows PowerShell 2.0, some of the property values of the module object, such as the **ExportedCmdlets** and **NestedModules** property values, were not populated until the module was imported.</span></span>

- <span data-ttu-id="ce404-429">При попытке импортировать модуль, содержащий сборки в смешанном режиме, несовместимые с Windows PowerShell 3.0 +, `Import-Module` возвращает сообщение об ошибке следующего вида.</span><span class="sxs-lookup"><span data-stu-id="ce404-429">If you attempt to import a module that contains mixed-mode assemblies that aren't compatible with Windows PowerShell 3.0+, `Import-Module` returns an error message like the following one.</span></span>

  > <span data-ttu-id="ce404-430">Import-Module: сборка смешанного режима построена на базе версии "v 2.0.50727" среды выполнения и не может быть загружена в среду выполнения 4,0 без дополнительных сведений о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ce404-430">Import-Module : Mixed mode assembly is built against version 'v2.0.50727' of the runtime and cannot be loaded in the 4.0 runtime without additional configuration information.</span></span>

  <span data-ttu-id="ce404-431">Эта ошибка возникает, когда модуль, разработанный для Windows PowerShell 2,0, содержит по крайней мере одну сборку смешанного модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-431">This error occurs when a module that is designed for Windows PowerShell 2.0 contains at least one mixed-module assembly.</span></span> <span data-ttu-id="ce404-432">Сборка смешанного модуля, включающая как управляемый, так и неуправляемый код, например C++ и C#.</span><span class="sxs-lookup"><span data-stu-id="ce404-432">A mixed-module assembly that includes both managed and non-managed code, such as C++ and C#.</span></span>

  <span data-ttu-id="ce404-433">Чтобы импортировать модуль, содержащий сборки в смешанном режиме, запустите Windows PowerShell 2,0 с помощью следующей команды и повторите `Import-Module` команду.</span><span class="sxs-lookup"><span data-stu-id="ce404-433">To import a module that contains mixed-mode assemblies, start Windows PowerShell 2.0 by using the following command, and then try the `Import-Module` command again.</span></span>

  `PowerShell.exe -Version 2.0`

- <span data-ttu-id="ce404-434">Для использования функции сеанса CIM на удаленном компьютере должен быть установлен компонент удаленного взаимодействия WS-Management и инструментарий управления Windows (WMI), который представляет собой реализацию стандарта CIM корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ce404-434">To use the CIM session feature, the remote computer must have WS-Management remoting and Windows Management Instrumentation (WMI), which is the Microsoft implementation of the Common Information Model (CIM) standard.</span></span> <span data-ttu-id="ce404-435">На компьютере также должен быть поставщик WMI модуля обнаружения или альтернативный поставщик CIM с теми же основными функциями.</span><span class="sxs-lookup"><span data-stu-id="ce404-435">The computer must also have the Module Discovery WMI provider or an alternate CIM provider that has the same basic features.</span></span>

  <span data-ttu-id="ce404-436">Можно использовать сеанс CIM на компьютерах, которые не работают под управлением операционной системы Windows и на компьютерах Windows с PowerShell, но не поддерживают удаленное взаимодействие PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ce404-436">You can use the CIM session feature on computers that aren't running a Windows operating system and on Windows computers that have PowerShell, but don't have PowerShell remoting enabled.</span></span>

  <span data-ttu-id="ce404-437">Можно также использовать параметры CIM для получения модулей CIM с компьютеров, на которых включено удаленное взаимодействие PowerShell, включая локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="ce404-437">You can also use the CIM parameters to get CIM modules from computers that have PowerShell remoting enabled, including the local computer.</span></span> <span data-ttu-id="ce404-438">При создании сеанса CIM на локальном компьютере для создания сеанса в PowerShell используется DCOM, а не WMI.</span><span class="sxs-lookup"><span data-stu-id="ce404-438">When you create a CIM session on the local computer, PowerShell uses DCOM, instead of WMI, to create the session.</span></span>

- <span data-ttu-id="ce404-439">По умолчанию `Import-Module` импортирует модули в глобальной области, даже если они вызываются из области видимости потомков.</span><span class="sxs-lookup"><span data-stu-id="ce404-439">By default, `Import-Module` imports modules in the global scope even when called from a descendant scope.</span></span> <span data-ttu-id="ce404-440">Область верхнего уровня и все области видимости потомков имеют доступ к экспортированным элементам модуля.</span><span class="sxs-lookup"><span data-stu-id="ce404-440">The top-level scope and all descendant scopes have access to the module's exported elements.</span></span>

  <span data-ttu-id="ce404-441">В области видимости потомков `-Scope Local` ограничивает импорт в эту область и все ее дочерние области.</span><span class="sxs-lookup"><span data-stu-id="ce404-441">In a descendant scope, `-Scope Local` limits the import to that scope and all its descendant scopes.</span></span> <span data-ttu-id="ce404-442">В родительских областях не отображаются импортированные элементы.</span><span class="sxs-lookup"><span data-stu-id="ce404-442">Parent scopes then do not see the imported members.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ce404-443">`Get-Module` показывает все модули, загруженные в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="ce404-443">`Get-Module` shows all modules loaded in the current session.</span></span> <span data-ttu-id="ce404-444">Сюда входят модули, загруженные локально в области видимости потомков.</span><span class="sxs-lookup"><span data-stu-id="ce404-444">This includes modules loaded locally in a descendant scope.</span></span> <span data-ttu-id="ce404-445">Используйте `Get-Command -Module modulename` , чтобы узнать, какие элементы загружаются в текущей области.</span><span class="sxs-lookup"><span data-stu-id="ce404-445">Use `Get-Command -Module modulename` to see which members are loaded in the current scope.</span></span>

  <span data-ttu-id="ce404-446">`Import-Module` не загружает определения классов и перечислений в модуле.</span><span class="sxs-lookup"><span data-stu-id="ce404-446">`Import-Module` does not load class and enum definitions in the module.</span></span> <span data-ttu-id="ce404-447">Используйте `using module` оператор в начале скрипта.</span><span class="sxs-lookup"><span data-stu-id="ce404-447">Use the `using module` statement at the beginning of your script.</span></span> <span data-ttu-id="ce404-448">Это позволит импортировать модуль, включая определения класса и перечисления.</span><span class="sxs-lookup"><span data-stu-id="ce404-448">This imports the module, including the class and enum definitions.</span></span> <span data-ttu-id="ce404-449">Дополнительные сведения см. в разделе [about_Using](About/about_Using.md).</span><span class="sxs-lookup"><span data-stu-id="ce404-449">For more information, see [about_Using](About/about_Using.md).</span></span>

## <span data-ttu-id="ce404-450">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ce404-450">RELATED LINKS</span></span>

[<span data-ttu-id="ce404-451">about_Modules</span><span class="sxs-lookup"><span data-stu-id="ce404-451">about_Modules</span></span>](about/about_Modules.md)

[<span data-ttu-id="ce404-452">Export-ModuleMember</span><span class="sxs-lookup"><span data-stu-id="ce404-452">Export-ModuleMember</span></span>](Export-ModuleMember.md)

[<span data-ttu-id="ce404-453">Get-Module</span><span class="sxs-lookup"><span data-stu-id="ce404-453">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="ce404-454">New-Module</span><span class="sxs-lookup"><span data-stu-id="ce404-454">New-Module</span></span>](New-Module.md)

[<span data-ttu-id="ce404-455">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="ce404-455">Remove-Module</span></span>](Remove-Module.md)
