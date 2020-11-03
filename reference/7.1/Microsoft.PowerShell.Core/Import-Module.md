---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/import-module?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Module
ms.openlocfilehash: 70453f50e727f89012a3e2077557bff7a81ff000
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229506"
---
# <span data-ttu-id="5f57b-103">Import-Module</span><span class="sxs-lookup"><span data-stu-id="5f57b-103">Import-Module</span></span>

## <span data-ttu-id="5f57b-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="5f57b-104">SYNOPSIS</span></span>
<span data-ttu-id="5f57b-105">Добавляет модули в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="5f57b-105">Adds modules to the current session.</span></span>

## <span data-ttu-id="5f57b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5f57b-106">SYNTAX</span></span>

### <span data-ttu-id="5f57b-107">Имя (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="5f57b-107">Name (Default)</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Name] <String[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-SkipEditionCheck]
 [-PassThru] [-AsCustomObject] [-MinimumVersion <Version>] [-MaximumVersion <String>]
 [-RequiredVersion <Version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>]  [<CommonParameters>]
```

### <span data-ttu-id="5f57b-108">PSSession</span><span class="sxs-lookup"><span data-stu-id="5f57b-108">PSSession</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Name] <String[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-SkipEditionCheck]
 [-PassThru] [-AsCustomObject] [-MinimumVersion <Version>] [-MaximumVersion <String>]
 [-RequiredVersion <Version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] -PSSession <PSSession>  [<CommonParameters>]
```

### <span data-ttu-id="5f57b-109">CimSession</span><span class="sxs-lookup"><span data-stu-id="5f57b-109">CimSession</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Name] <String[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-SkipEditionCheck]
 [-PassThru] [-AsCustomObject] [-MinimumVersion <Version>] [-MaximumVersion <String>]
 [-RequiredVersion <Version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] -CimSession <CimSession> [-CimResourceUri <Uri>] [-CimNamespace <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="5f57b-110">усевиндовсповершелл</span><span class="sxs-lookup"><span data-stu-id="5f57b-110">UseWindowsPowerShell</span></span>

```
Import-Module [-Name] <string[]> -UseWindowsPowerShell [-Global] [-Prefix <string>]
 [-Function <string[]>] [-Cmdlet <string[]>] [-Variable <string[]>] [-Alias <string[]>]
 [-Force] [-PassThru] [-AsCustomObject] [-MinimumVersion <version>] [-MaximumVersion <string>]
 [-RequiredVersion <version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <string>] [<CommonParameters>]
```

### <span data-ttu-id="5f57b-111">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="5f57b-111">FullyQualifiedName</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-FullyQualifiedName] <ModuleSpecification[]>
 [-Function <String[]>] [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force]
 [-SkipEditionCheck] [-PassThru] [-AsCustomObject] [-ArgumentList <Object[]>] [-DisableNameChecking]
 [-NoClobber] [-Scope <String>]  [<CommonParameters>]
```

### <span data-ttu-id="5f57b-112">фулликуалифиеднамеандпссессион</span><span class="sxs-lookup"><span data-stu-id="5f57b-112">FullyQualifiedNameAndPSSession</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-FullyQualifiedName] <ModuleSpecification[]>
 [-Function <String[]>] [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force]
 [-SkipEditionCheck] [-PassThru] [-AsCustomObject] [-ArgumentList <Object[]>] [-DisableNameChecking]
 [-NoClobber] [-Scope <String>] -PSSession <PSSession>  [<CommonParameters>]
```

### <span data-ttu-id="5f57b-113">фулликуалифиеднамеандусевиндовсповершелл</span><span class="sxs-lookup"><span data-stu-id="5f57b-113">FullyQualifiedNameAndUseWindowsPowerShell</span></span>

```
Import-Module [-FullyQualifiedName] <ModuleSpecification[]> -UseWindowsPowerShell [-Global]
 [-Prefix <string>] [-Function <string[]>] [-Cmdlet <string[]>] [-Variable <string[]>]
 [-Alias <string[]>] [-Force] [-PassThru] [-AsCustomObject] [-ArgumentList <Object[]>]
 [-DisableNameChecking] [-NoClobber] [-Scope <string>] [<CommonParameters>]
```

### <span data-ttu-id="5f57b-114">Сборка</span><span class="sxs-lookup"><span data-stu-id="5f57b-114">Assembly</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Assembly] <Assembly[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-SkipEditionCheck]
 [-PassThru] [-AsCustomObject] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>]  [<CommonParameters>]
```

### <span data-ttu-id="5f57b-115">ModuleInfo</span><span class="sxs-lookup"><span data-stu-id="5f57b-115">ModuleInfo</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Function <String[]>] [-Cmdlet <String[]>]
 [-Variable <String[]>] [-Alias <String[]>] [-Force] [-SkipEditionCheck] [-PassThru]
 [-AsCustomObject] [-ModuleInfo] <PSModuleInfo[]> [-ArgumentList <Object[]>] [-DisableNameChecking]
 [-NoClobber] [-Scope <String>]  [<CommonParameters>]
```

## <span data-ttu-id="5f57b-116">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5f57b-116">DESCRIPTION</span></span>

<span data-ttu-id="5f57b-117">`Import-Module`Командлет добавляет один или несколько модулей в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="5f57b-117">The `Import-Module` cmdlet adds one or more modules to the current session.</span></span> <span data-ttu-id="5f57b-118">Начиная с PowerShell 3,0, установленные модули автоматически импортируются в сеанс при использовании каких либо команд или поставщиков в модуле.</span><span class="sxs-lookup"><span data-stu-id="5f57b-118">Starting in PowerShell 3.0, installed modules are automatically imported to the session when you use any commands or providers in the module.</span></span> <span data-ttu-id="5f57b-119">Однако вы по-прежнему можете использовать `Import-Module` команду для импорта модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-119">However, you can still use the `Import-Module` command to import a module.</span></span>
<span data-ttu-id="5f57b-120">Вы можете отключить автоматическое импортирование модулей с помощью `$PSModuleAutoloadingPreference` переменной предпочтений.</span><span class="sxs-lookup"><span data-stu-id="5f57b-120">You can disable automatic module importing using the `$PSModuleAutoloadingPreference` preference variable.</span></span> <span data-ttu-id="5f57b-121">Дополнительные сведения о `$PSModuleAutoloadingPreference` переменной см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="5f57b-121">For more information about the `$PSModuleAutoloadingPreference` variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="5f57b-122">Модуль — это пакет, содержащий элементы, которые можно использовать в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f57b-122">A module is a package that contains members that can be used in PowerShell.</span></span> <span data-ttu-id="5f57b-123">Члены включают командлеты, поставщики, скрипты, функции, переменные и другие средства и файлы.</span><span class="sxs-lookup"><span data-stu-id="5f57b-123">Members include cmdlets, providers, scripts, functions, variables, and other tools and files.</span></span> <span data-ttu-id="5f57b-124">После импорта модуля вы можете использовать его элементы в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="5f57b-124">After a module is imported, you can use the module members in your session.</span></span> <span data-ttu-id="5f57b-125">Дополнительные сведения о модулях см. в разделе [about_Modules](About/about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="5f57b-125">For more information about modules, see [about_Modules](About/about_Modules.md).</span></span>

<span data-ttu-id="5f57b-126">По умолчанию `Import-Module` импортирует все элементы, экспортируемые модулем, но можно использовать параметры **псевдонима** , **функции** , **командлета** и **переменной** , чтобы ограничить импортируемые элементы.</span><span class="sxs-lookup"><span data-stu-id="5f57b-126">By default, `Import-Module` imports all members that the module exports, but you can use the **Alias** , **Function** , **Cmdlet** , and **Variable** parameters to restrict which members are imported.</span></span> <span data-ttu-id="5f57b-127">Параметр **NoClobber** предотвращает `Import-Module` Импорт элементов, имеющих те же имена, что и члены в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="5f57b-127">The **NoClobber** parameter prevents `Import-Module` from importing members that have the same names as members in the current session.</span></span>

<span data-ttu-id="5f57b-128">`Import-Module` импортирует модуль только в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="5f57b-128">`Import-Module` imports a module only into the current session.</span></span> <span data-ttu-id="5f57b-129">Чтобы импортировать модуль в каждый новый сеанс, добавьте `Import-Module` команду в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f57b-129">To import the module into every new session, add an `Import-Module` command to your PowerShell profile.</span></span> <span data-ttu-id="5f57b-130">Дополнительные сведения о профилях см. в разделе [about_Profiles](About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="5f57b-130">For more information about profiles, see [about_Profiles](About/about_Profiles.md).</span></span>

<span data-ttu-id="5f57b-131">Вы можете управлять удаленными компьютерами Windows, на которых удаленное взаимодействие PowerShell включено, создав **сеанс PSSession** на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5f57b-131">You can manage remote Windows computers that have PowerShell remoting enabled by creating a **PSSession** on the remote computer.</span></span> <span data-ttu-id="5f57b-132">Затем используйте параметр **PSSession** параметра, `Import-Module` чтобы импортировать модули, установленные на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5f57b-132">Then use the **PSSession** parameter of `Import-Module` to import the modules that are installed on the remote computer.</span></span> <span data-ttu-id="5f57b-133">Теперь можно использовать импортированные команды в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="5f57b-133">You can now use the imported commands in the current session.</span></span> <span data-ttu-id="5f57b-134">Команды выполняются неявным образом на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5f57b-134">The commands implicitly run on the remote computer.</span></span>

<span data-ttu-id="5f57b-135">Начиная с Windows PowerShell 3,0, можно использовать `Import-Module` для импорта модулей модель CIM (CIM), в которых командлеты определяются в файлах XML определения командлетов (CDXML).</span><span class="sxs-lookup"><span data-stu-id="5f57b-135">Starting in Windows PowerShell 3.0, you can use `Import-Module` to import Common Information Model (CIM) modules, in which the cmdlets are defined in Cmdlet Definition XML (CDXML) files.</span></span> <span data-ttu-id="5f57b-136">Эта возможность позволяет использовать командлеты, которые реализованы в сборках неуправляемого кода, например на языке C++.</span><span class="sxs-lookup"><span data-stu-id="5f57b-136">This feature allows you to use cmdlets that are implemented in non-managed code assemblies, such as those written in C++.</span></span>

<span data-ttu-id="5f57b-137">Для удаленных компьютеров, на которых не включено удаленное взаимодействие PowerShell, включая компьютеры, на которых не установлена операционная система Windows, можно **CIMSession** использовать параметр CIMSession `Import-Module` в для импорта модулей CIM с удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="5f57b-137">For remote computers that don't have PowerShell remoting enabled, including computers that aren't running the Windows operating system, you can use the **CIMSession** parameter of `Import-Module` to import CIM modules from the remote computer.</span></span> <span data-ttu-id="5f57b-138">Импортированные команды выполняются неявно на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5f57b-138">The imported commands run implicitly on the remote computer.</span></span> <span data-ttu-id="5f57b-139">**CIMSession** — это подключение к инструментарий управления Windows (WMI) (WMI) на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5f57b-139">A **CIMSession** is a connection to Windows Management Instrumentation (WMI) on the remote computer.</span></span>

## <span data-ttu-id="5f57b-140">Примеры</span><span class="sxs-lookup"><span data-stu-id="5f57b-140">EXAMPLES</span></span>

### <span data-ttu-id="5f57b-141">Пример 1. Импорт членов модуля в текущий сеанс</span><span class="sxs-lookup"><span data-stu-id="5f57b-141">Example 1: Import the members of a module into the current session</span></span>

<span data-ttu-id="5f57b-142">В этом примере выполняется импорт элементов модуля **PSDiagnostics** в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="5f57b-142">This example imports the members of the **PSDiagnostics** module into the current session.</span></span>

```powershell
Import-Module -Name PSDiagnostics
```

### <span data-ttu-id="5f57b-143">Пример 2. импорт всех модулей, указанных в пути к модулю</span><span class="sxs-lookup"><span data-stu-id="5f57b-143">Example 2: Import all modules specified by the module path</span></span>

<span data-ttu-id="5f57b-144">В этом примере выполняется импорт всех доступных модулей по пути, указанному в `$env:PSModulePath` переменной среды, в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="5f57b-144">This example imports all available modules in the path specified by the `$env:PSModulePath` environment variable into the current session.</span></span>

```powershell
Get-Module -ListAvailable | Import-Module
```

### <span data-ttu-id="5f57b-145">Пример 3. Импорт элементов нескольких модулей в текущий сеанс</span><span class="sxs-lookup"><span data-stu-id="5f57b-145">Example 3: Import the members of several modules into the current session</span></span>

<span data-ttu-id="5f57b-146">В этом примере выполняется импорт элементов модулей **PSDiagnostics** и **DISM** в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="5f57b-146">This example imports the members of the **PSDiagnostics** and **Dism** modules into the current session.</span></span>

```powershell
$m = Get-Module -ListAvailable PSDiagnostics, Dism
Import-Module -ModuleInfo $m
```

<span data-ttu-id="5f57b-147">`Get-Module`Командлет получает модули **PSDiagnostics** и **DISM** и сохраняет объекты в `$m` переменной.</span><span class="sxs-lookup"><span data-stu-id="5f57b-147">The `Get-Module` cmdlet gets the **PSDiagnostics** and **Dism** modules and saves the objects in the `$m` variable.</span></span> <span data-ttu-id="5f57b-148">Параметр **ListAvailable** является обязательным при получении модулей, которые еще не импортированы в сеанс.</span><span class="sxs-lookup"><span data-stu-id="5f57b-148">The **ListAvailable** parameter is required when you're getting modules that aren't yet imported into the session.</span></span>

<span data-ttu-id="5f57b-149">Параметр **ModuleInfo** класса `Import-Module` используется для импорта модулей в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="5f57b-149">The **ModuleInfo** parameter of `Import-Module` is used to import the modules into the current session.</span></span>

### <span data-ttu-id="5f57b-150">Пример 4. импорт всех модулей, указанных путем</span><span class="sxs-lookup"><span data-stu-id="5f57b-150">Example 4: Import all modules specified by a path</span></span>

<span data-ttu-id="5f57b-151">В этом примере используется явный путь для указания импортируемого модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-151">This example uses an explicit path to identify the module to import.</span></span>

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

<span data-ttu-id="5f57b-152">Использование параметра **verbose** приводит `Import-Module` к отчету о ходе выполнения при загрузке модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-152">Using the **Verbose** parameter causes `Import-Module` to report progress as it loads the module.</span></span>
<span data-ttu-id="5f57b-153">Без параметра **verbose** , **PassThru** или **AsCustomObject** не `Import-Module` создает никаких выходных данных при импорте модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-153">Without the **Verbose** , **PassThru** , or **AsCustomObject** parameter, `Import-Module` does not generate any output when it imports a module.</span></span>

### <span data-ttu-id="5f57b-154">Пример 5. Ограничение элементов модуля, импортированных в сеанс</span><span class="sxs-lookup"><span data-stu-id="5f57b-154">Example 5: Restrict module members imported into a session</span></span>

<span data-ttu-id="5f57b-155">В этом примере показано, как ограничить список членов модуля, импортируемых в сеанс, и результат выполнения этой команды в сеансе.</span><span class="sxs-lookup"><span data-stu-id="5f57b-155">This example shows how to restrict which module members are imported into the session and the effect of this command on the session.</span></span> <span data-ttu-id="5f57b-156">Параметр **функции** ограничивает элементы, импортируемые из модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-156">The **Function** parameter limits the members that are imported from the module.</span></span> <span data-ttu-id="5f57b-157">Можно также использовать параметры **псевдонима** , **переменной** и **командлета** для ограничения других членов, импортируемых модулем.</span><span class="sxs-lookup"><span data-stu-id="5f57b-157">You can also use the **Alias** , **Variable** , and **Cmdlet** parameters to restrict other members that a module imports.</span></span>

<span data-ttu-id="5f57b-158">`Get-Module`Командлет возвращает объект, представляющий модуль **PSDiagnostics** .</span><span class="sxs-lookup"><span data-stu-id="5f57b-158">The `Get-Module` cmdlet gets the object that represents the **PSDiagnostics** module.</span></span> <span data-ttu-id="5f57b-159">Свойство **експортедкмдлетс** перечисляет все командлеты, экспортируемые модулем, даже если они не были импортированы.</span><span class="sxs-lookup"><span data-stu-id="5f57b-159">The **ExportedCmdlets** property lists all the cmdlets that the module exports, even though they were not all imported.</span></span>

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

<span data-ttu-id="5f57b-160">С помощью параметра **module** `Get-Command` командлета отображаются команды, импортированные из модуля **PSDiagnostics** .</span><span class="sxs-lookup"><span data-stu-id="5f57b-160">Using the **Module** parameter of the `Get-Command` cmdlet shows the commands that were imported from the **PSDiagnostics** module.</span></span> <span data-ttu-id="5f57b-161">Результаты подтверждают, что `Disable-PSTrace` `Enable-PSTrace` импортированы только командлеты и.</span><span class="sxs-lookup"><span data-stu-id="5f57b-161">The results confirm that only the `Disable-PSTrace` and `Enable-PSTrace` cmdlets were imported.</span></span>

### <span data-ttu-id="5f57b-162">Пример 6. Импорт элементов модуля и Добавление префикса</span><span class="sxs-lookup"><span data-stu-id="5f57b-162">Example 6: Import the members of a module and add a prefix</span></span>

<span data-ttu-id="5f57b-163">Этот пример импортирует модуль **PSDiagnostics** в текущий сеанс, добавляет префикс к именам членов, а затем отображает имена элементов с префиксом.</span><span class="sxs-lookup"><span data-stu-id="5f57b-163">This example imports the **PSDiagnostics** module into the current session, adds a prefix to the member names, and then displays the prefixed member names.</span></span> <span data-ttu-id="5f57b-164">Параметр **prefix** параметра `Import-Module` добавляет префикс **x** ко всем элементам, импортированным из модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-164">The **Prefix** parameter of `Import-Module` adds the **x** prefix to all members that are imported from the module.</span></span> <span data-ttu-id="5f57b-165">Префикс применяется только к элементам в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="5f57b-165">The prefix applies only to the members in the current session.</span></span> <span data-ttu-id="5f57b-166">Он не изменяет сам модуль.</span><span class="sxs-lookup"><span data-stu-id="5f57b-166">It does not change the module.</span></span> <span data-ttu-id="5f57b-167">Параметр **PassThru** возвращает объект Module, представляющий импортированный модуль.</span><span class="sxs-lookup"><span data-stu-id="5f57b-167">The **PassThru** parameter returns a module object that represents the imported module.</span></span>

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

<span data-ttu-id="5f57b-168">`Get-Command` Возвращает элементы, которые были импортированы из модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-168">`Get-Command` gets the members that have been imported from the module.</span></span> <span data-ttu-id="5f57b-169">Выходные данные показывают, что к элементам модуля был правильно добавлен префикс.</span><span class="sxs-lookup"><span data-stu-id="5f57b-169">The output shows that the module members were correctly prefixed.</span></span>

### <span data-ttu-id="5f57b-170">Пример 7. получение и использование пользовательского объекта</span><span class="sxs-lookup"><span data-stu-id="5f57b-170">Example 7: Get and use a custom object</span></span>

<span data-ttu-id="5f57b-171">В этом примере показано, как получить и использовать пользовательский объект, возвращаемый **Import-Module** .</span><span class="sxs-lookup"><span data-stu-id="5f57b-171">This example demonstrates how to get and use the custom object returned by **Import-Module** .</span></span>

<span data-ttu-id="5f57b-172">Настраиваемые объекты содержат синтетические элементы, представляющие каждый из элементов импортированного модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-172">Custom objects include synthetic members that represent each of the imported module members.</span></span> <span data-ttu-id="5f57b-173">Например, командлеты и функции в модуле преобразуются в методы скрипта пользовательского объекта.</span><span class="sxs-lookup"><span data-stu-id="5f57b-173">For example, the cmdlets and functions in a module are converted to script methods of the custom object.</span></span>

<span data-ttu-id="5f57b-174">Пользовательские объекты полезны в сценариях.</span><span class="sxs-lookup"><span data-stu-id="5f57b-174">Custom objects are useful in scripting.</span></span> <span data-ttu-id="5f57b-175">Они также полезны, если имена нескольких импортированных объектов совпадают.</span><span class="sxs-lookup"><span data-stu-id="5f57b-175">They are also useful when several imported objects have the same names.</span></span> <span data-ttu-id="5f57b-176">Использование метода скрипта объекта равнозначно указанию полного имени импортированного элемента, включая имя модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-176">Using the script method of an object is equivalent to specifying the fully qualified name of an imported member, including its module name.</span></span>

<span data-ttu-id="5f57b-177">Параметр **AsCustomObject** можно использовать только при импорте модуля скрипта.</span><span class="sxs-lookup"><span data-stu-id="5f57b-177">The **AsCustomObject** parameter can be used only when importing a script module.</span></span> <span data-ttu-id="5f57b-178">Используйте `Get-Module` , чтобы определить, какой из доступных модулей является модулем скрипта.</span><span class="sxs-lookup"><span data-stu-id="5f57b-178">Use `Get-Module` to determine which of the available modules is a script module.</span></span>

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

<span data-ttu-id="5f57b-179">Модуль « **Показ-календарь** » импортируется с помощью параметра **AsCustomObject** для запроса пользовательского объекта, а параметр **PassThru** — для возврата объекта.</span><span class="sxs-lookup"><span data-stu-id="5f57b-179">The **Show-Calendar** script module is imported using the **AsCustomObject** parameter to request a custom object and the **PassThru** parameter to return the object.</span></span> <span data-ttu-id="5f57b-180">Полученный пользовательский объект сохраняется в `$a` переменной.</span><span class="sxs-lookup"><span data-stu-id="5f57b-180">The resulting custom object is saved in the `$a` variable.</span></span>

<span data-ttu-id="5f57b-181">`$a`Переменная передается в `Get-Member` командлет для отображения свойств и методов сохраненного объекта.</span><span class="sxs-lookup"><span data-stu-id="5f57b-181">The `$a` variable is piped to the `Get-Member` cmdlet to show the properties and methods of the saved object.</span></span> <span data-ttu-id="5f57b-182">В выходных данных показан метод сценария " **Показать-календарь** ".</span><span class="sxs-lookup"><span data-stu-id="5f57b-182">The output shows a **Show-Calendar** script method.</span></span>

<span data-ttu-id="5f57b-183">Чтобы вызвать метод сценария **представления-Calendar** , имя метода должно быть заключено в кавычки, так как имя включает дефис.</span><span class="sxs-lookup"><span data-stu-id="5f57b-183">To call the **Show-Calendar** script method, the method name must be enclosed in quotation marks because the name includes a hyphen.</span></span>

### <span data-ttu-id="5f57b-184">Пример 8. повторное импорт модуля в тот же сеанс</span><span class="sxs-lookup"><span data-stu-id="5f57b-184">Example 8: Reimport a module into the same session</span></span>

<span data-ttu-id="5f57b-185">В этом примере показано, как использовать параметр **Force** при повторном `Import-Module` импорте модуля в тот же сеанс.</span><span class="sxs-lookup"><span data-stu-id="5f57b-185">This example shows how to use the **Force** parameter of `Import-Module` when you're reimporting a module into the same session.</span></span> <span data-ttu-id="5f57b-186">Параметр **Force** удаляет загруженный модуль и затем импортирует его снова.</span><span class="sxs-lookup"><span data-stu-id="5f57b-186">The **Force** parameter removes the loaded module and then imports it again.</span></span>

```powershell
Import-Module PSDiagnostics
Import-Module PSDiagnostics -Force -Prefix PS
```

<span data-ttu-id="5f57b-187">Первая команда импортирует модуль **PSDiagnostics** .</span><span class="sxs-lookup"><span data-stu-id="5f57b-187">The first command imports the **PSDiagnostics** module.</span></span> <span data-ttu-id="5f57b-188">Вторая команда импортирует модуль, на этот раз с помощью параметра **Prefix** .</span><span class="sxs-lookup"><span data-stu-id="5f57b-188">The second command imports the module again, this time using the **Prefix** parameter.</span></span>

<span data-ttu-id="5f57b-189">Без параметра **Force** сеанс будет содержать две копии каждого командлета **PSDiagnostics** , один из которых имеет стандартное имя и имя с префиксом.</span><span class="sxs-lookup"><span data-stu-id="5f57b-189">Without the **Force** parameter, the session would include two copies of each **PSDiagnostics** cmdlet, one with the standard name and one with the prefixed name.</span></span>

### <span data-ttu-id="5f57b-190">Пример 9. выполнение команд, скрытых с помощью импортированных команд</span><span class="sxs-lookup"><span data-stu-id="5f57b-190">Example 9: Run commands that have been hidden by imported commands</span></span>

<span data-ttu-id="5f57b-191">В этом примере показано, как выполнить команды, которые были скрыты импортированными командами.</span><span class="sxs-lookup"><span data-stu-id="5f57b-191">This example shows how to run commands that have been hidden by imported commands.</span></span> <span data-ttu-id="5f57b-192">Модуль **тестмодуле** включает функцию с именем `Get-Date` , которая возвращает год и день года.</span><span class="sxs-lookup"><span data-stu-id="5f57b-192">The **TestModule** module includes a function named `Get-Date` that returns the year and day of the year.</span></span>

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

<span data-ttu-id="5f57b-193">Первый `Get-Date` командлет возвращает объект **DateTime** с текущей датой.</span><span class="sxs-lookup"><span data-stu-id="5f57b-193">The first `Get-Date` cmdlet returns a **DateTime** object with the current date.</span></span> <span data-ttu-id="5f57b-194">После импорта модуля **тестмодуле** `Get-Date` возвращает год и день года.</span><span class="sxs-lookup"><span data-stu-id="5f57b-194">After importing the **TestModule** module, `Get-Date` returns the year and day of the year.</span></span>

<span data-ttu-id="5f57b-195">Используя параметр **ALL** параметра, вы `Get-Command` увидите все `Get-Date` команды в сеансе.</span><span class="sxs-lookup"><span data-stu-id="5f57b-195">Using the **All** parameter of `Get-Command` show all the `Get-Date` commands in the session.</span></span> <span data-ttu-id="5f57b-196">Результаты показывают, что `Get-Date` в сеансе есть две команды: функция из модуля **тестмодуле** и командлет из модуля **Microsoft. PowerShell. Utility** .</span><span class="sxs-lookup"><span data-stu-id="5f57b-196">The results show that there are two `Get-Date` commands in the session, a function from the **TestModule** module and a cmdlet from the **Microsoft.PowerShell.Utility** module.</span></span>

<span data-ttu-id="5f57b-197">Поскольку функции имеют приоритет над командлетами, `Get-Date` вместо командлета выполняется функция из модуля **тестмодуле** `Get-Date` .</span><span class="sxs-lookup"><span data-stu-id="5f57b-197">Because functions take precedence over cmdlets, the `Get-Date` function from the **TestModule** module runs, instead of the `Get-Date` cmdlet.</span></span> <span data-ttu-id="5f57b-198">Чтобы запустить исходную версию `Get-Date` , необходимо уточнить имя команды с помощью имени модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-198">To run the original version of `Get-Date`, you must qualify the command name with the module name.</span></span>

<span data-ttu-id="5f57b-199">Дополнительные сведения о приоритетах команд в PowerShell см. в разделе [about_Command_Precedence](about/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="5f57b-199">For more information about command precedence in PowerShell, see [about_Command_Precedence](about/about_Command_Precedence.md).</span></span>

### <span data-ttu-id="5f57b-200">Пример 10. Импорт минимальной версии модуля</span><span class="sxs-lookup"><span data-stu-id="5f57b-200">Example 10: Import a minimum version of a module</span></span>

<span data-ttu-id="5f57b-201">В этом примере импортируется модуль **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="5f57b-201">This example imports the **PowerShellGet** module.</span></span> <span data-ttu-id="5f57b-202">Параметр **MinimumVersion** `Import-Module` в используется для импорта только 2.0.0 версии или выше модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-202">It uses the **MinimumVersion** parameter of `Import-Module` to import only version 2.0.0 or greater of the module.</span></span>

```powershell
Import-Module -Name PowerShellGet -MinimumVersion 2.0.0
```

<span data-ttu-id="5f57b-203">Можно также использовать параметр **RequiredVersion** для импорта определенной версии модуля или использовать параметры **модуля** и **версии** `#Requires` ключевого слова, чтобы требовать определенную версию модуля в скрипте.</span><span class="sxs-lookup"><span data-stu-id="5f57b-203">You can also use the **RequiredVersion** parameter to import a particular version of a module, or use the **Module** and **Version** parameters of the `#Requires` keyword to require a particular version of a module in a script.</span></span>

### <span data-ttu-id="5f57b-204">Пример 11. Импорт с использованием полного имени</span><span class="sxs-lookup"><span data-stu-id="5f57b-204">Example 11: Import using a fully qualified name</span></span>

<span data-ttu-id="5f57b-205">В этом примере выполняется импорт определенной версии модуля с помощью FullyQualifiedName.</span><span class="sxs-lookup"><span data-stu-id="5f57b-205">This example imports a specific version of a module using the FullyQualifiedName.</span></span>

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

### <span data-ttu-id="5f57b-206">Пример 12. Импорт с использованием полного пути</span><span class="sxs-lookup"><span data-stu-id="5f57b-206">Example 12: Import using a fully qualified path</span></span>

<span data-ttu-id="5f57b-207">В этом примере выполняется импорт определенной версии модуля с использованием полного пути.</span><span class="sxs-lookup"><span data-stu-id="5f57b-207">This example imports a specific version of a module using the fully qualified path.</span></span>

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

### <span data-ttu-id="5f57b-208">Пример 13. импорт модуля с удаленного компьютера</span><span class="sxs-lookup"><span data-stu-id="5f57b-208">Example 13: Import a module from a remote computer</span></span>

<span data-ttu-id="5f57b-209">В этом примере показано, как использовать `Import-Module` командлет для импорта модуля с удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="5f57b-209">This example shows how to use the `Import-Module` cmdlet to import a module from a remote computer.</span></span>
<span data-ttu-id="5f57b-210">Эта команда использует функцию неявного удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f57b-210">This command uses the Implicit Remoting feature of PowerShell.</span></span>

<span data-ttu-id="5f57b-211">При импорте модулей из другого сеанса можно применять командлеты в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="5f57b-211">When you import modules from another session, you can use the cmdlets in the current session.</span></span>
<span data-ttu-id="5f57b-212">Однако команды, использующие командлеты, выполняются в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="5f57b-212">However, commands that use the cmdlets run in the remote session.</span></span>

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

<span data-ttu-id="5f57b-213">`New-PSSession` создает удаленный сеанс ( **PSSession** ) на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="5f57b-213">`New-PSSession` creates a remote session ( **PSSession** ) to the Server01 computer.</span></span> <span data-ttu-id="5f57b-214">**Сеанс PSSession** сохраняется в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="5f57b-214">The **PSSession** is saved in the `$s` variable.</span></span>

<span data-ttu-id="5f57b-215">Запуск `Get-Module` с параметром **PSSession** показывает, что модуль **NetSecurity** установлен и доступен на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5f57b-215">Running `Get-Module` with the **PSSession** parameter shows that the **NetSecurity** module is installed and available on the remote computer.</span></span> <span data-ttu-id="5f57b-216">Эта команда эквивалентна использованию `Invoke-Command` командлета для выполнения `Get-Module` команды в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="5f57b-216">This command is equivalent to using the `Invoke-Command` cmdlet to run `Get-Module` command in the remote session.</span></span> <span data-ttu-id="5f57b-217">Например: (`Invoke-Command $s {Get-Module -ListAvailable -Name NetSecurity`</span><span class="sxs-lookup"><span data-stu-id="5f57b-217">For example: (`Invoke-Command $s {Get-Module -ListAvailable -Name NetSecurity`</span></span>

<span data-ttu-id="5f57b-218">`Import-Module`При выполнении с параметром **PSSession** импортирует модуль **NetSecurity** с удаленного компьютера в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="5f57b-218">Running `Import-Module` with the **PSSession** parameter imports the **NetSecurity** module from the remote computer into the current session.</span></span> <span data-ttu-id="5f57b-219">`Get-Command`Командлет используется для получения команд, начинающихся с **Get** и включая **брандмауэр** из модуля **NetSecurity** .</span><span class="sxs-lookup"><span data-stu-id="5f57b-219">The `Get-Command` cmdlet is used to get commands that begin with **Get** and include **Firewall** from the **NetSecurity** module.</span></span> <span data-ttu-id="5f57b-220">Выходные данные подтверждают, что модуль и его командлеты были импортированы в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="5f57b-220">The output confirms that the module and its cmdlets were imported into the current session.</span></span>

<span data-ttu-id="5f57b-221">Затем `Get-NetFirewallRule` командлет получает служба удаленного управления Windows правила брандмауэра на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="5f57b-221">Next, the `Get-NetFirewallRule` cmdlet gets Windows Remote Management firewall rules on the Server01 computer.</span></span> <span data-ttu-id="5f57b-222">Это эквивалентно использованию `Invoke-Command` командлета для запуска `Get-NetFirewallRule` в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="5f57b-222">This is equivalent to using the `Invoke-Command` cmdlet to run `Get-NetFirewallRule` on the remote session.</span></span>

### <span data-ttu-id="5f57b-223">Пример 14. Управление хранилищем на удаленном компьютере без операционной системы Windows</span><span class="sxs-lookup"><span data-stu-id="5f57b-223">Example 14: Manage storage on a remote computer without the Windows operating system</span></span>

<span data-ttu-id="5f57b-224">В этом примере администратор компьютера установил поставщик WMI для обнаружения модуля, который позволяет использовать команды CIM, предназначенные для поставщика.</span><span class="sxs-lookup"><span data-stu-id="5f57b-224">In this example, the administrator of the computer has installed the Module Discovery WMI provider, which allows you to use CIM commands that are designed for the provider.</span></span>

<span data-ttu-id="5f57b-225">`New-CimSession`Командлет создает сеанс на удаленном компьютере с именем RSDGF03.</span><span class="sxs-lookup"><span data-stu-id="5f57b-225">The `New-CimSession` cmdlet creates a session on the remote computer named RSDGF03.</span></span> <span data-ttu-id="5f57b-226">Сеанс подключается к службе WMI на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5f57b-226">The session connects to the WMI service on the remote computer.</span></span> <span data-ttu-id="5f57b-227">Сеанс CIM сохраняется в `$cs` переменной.</span><span class="sxs-lookup"><span data-stu-id="5f57b-227">The CIM session is saved in the `$cs` variable.</span></span>
<span data-ttu-id="5f57b-228">`Import-Module` использует **CimSession** в `$cs` для импорта модуля CIM **хранилища** с компьютера RSDGF03.</span><span class="sxs-lookup"><span data-stu-id="5f57b-228">`Import-Module` uses the **CimSession** in `$cs` to import the **Storage** CIM module from the RSDGF03 computer.</span></span>

<span data-ttu-id="5f57b-229">`Get-Command`Командлет отображает `Get-Disk` команду в модуле **Storage** .</span><span class="sxs-lookup"><span data-stu-id="5f57b-229">The `Get-Command` cmdlet shows the `Get-Disk` command in the **Storage** module.</span></span> <span data-ttu-id="5f57b-230">При импорте модуля CIM в локальный сеанс PowerShell преобразует файлы CDXML для каждой команды в скрипты PowerShell, которые отображаются как функции в локальном сеансе.</span><span class="sxs-lookup"><span data-stu-id="5f57b-230">When you import a CIM module into the local session, PowerShell converts the CDXML files for each command into PowerShell scripts, which appear as functions in the local session.</span></span>

<span data-ttu-id="5f57b-231">Хотя он `Get-Disk` вводится в локальный сеанс, командлет выполняется неявно на удаленном компьютере, с которого он был импортирован.</span><span class="sxs-lookup"><span data-stu-id="5f57b-231">Although `Get-Disk` is typed in the local session, the cmdlet implicitly runs on the remote computer from which it was imported.</span></span> <span data-ttu-id="5f57b-232">Команда возвращает объекты с удаленного компьютера в локальный сеанс.</span><span class="sxs-lookup"><span data-stu-id="5f57b-232">The command returns objects from the remote computer to the local session.</span></span>

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

## <span data-ttu-id="5f57b-233">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5f57b-233">PARAMETERS</span></span>

### <span data-ttu-id="5f57b-234">-Alias</span><span class="sxs-lookup"><span data-stu-id="5f57b-234">-Alias</span></span>

<span data-ttu-id="5f57b-235">Задает псевдонимы, которые этот командлет импортирует из модуля в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="5f57b-235">Specifies the aliases that this cmdlet imports from the module into the current session.</span></span> <span data-ttu-id="5f57b-236">Введите разделенный запятыми список псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="5f57b-236">Enter a comma-separated list of aliases.</span></span> <span data-ttu-id="5f57b-237">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="5f57b-237">Wildcard characters are permitted.</span></span>

<span data-ttu-id="5f57b-238">Некоторые модули автоматически экспортируют выбранные псевдонимы в сеанс при импорте модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-238">Some modules automatically export selected aliases into your session when you import the module.</span></span>
<span data-ttu-id="5f57b-239">Этот параметр позволяет выбрать один из экспортированных псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="5f57b-239">This parameter lets you select from among the exported aliases.</span></span>

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

### <span data-ttu-id="5f57b-240">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="5f57b-240">-ArgumentList</span></span>

<span data-ttu-id="5f57b-241">Указывает массив аргументов или значений параметров, которые передаются в модуль скрипта во время выполнения `Import-Module` команды.</span><span class="sxs-lookup"><span data-stu-id="5f57b-241">Specifies an array of arguments, or parameter values, that are passed to a script module during the `Import-Module` command.</span></span> <span data-ttu-id="5f57b-242">Этот параметр допустим только при импорте модуля скрипта.</span><span class="sxs-lookup"><span data-stu-id="5f57b-242">This parameter is valid only when you're importing a script module.</span></span>

<span data-ttu-id="5f57b-243">Можно также ссылаться на параметр **ArgumentList** по его псевдониму **args** .</span><span class="sxs-lookup"><span data-stu-id="5f57b-243">You can also refer to the **ArgumentList** parameter by its alias, **args** .</span></span> <span data-ttu-id="5f57b-244">Дополнительные сведения о поведении **ArgumentList** см. в разделе [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="5f57b-244">For more information about the behavior of **ArgumentList** , see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

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

### <span data-ttu-id="5f57b-245">-AsCustomObject</span><span class="sxs-lookup"><span data-stu-id="5f57b-245">-AsCustomObject</span></span>

<span data-ttu-id="5f57b-246">Указывает, что этот командлет возвращает пользовательский объект с элементами, представляющими импортированные элементы модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-246">Indicates that this cmdlet returns a custom object with members that represent the imported module members.</span></span> <span data-ttu-id="5f57b-247">Этот параметр допустим только для модулей скриптов.</span><span class="sxs-lookup"><span data-stu-id="5f57b-247">This parameter is valid only for script modules.</span></span>

<span data-ttu-id="5f57b-248">При использовании параметра **AsCustomObject** `Import-Module` импортирует элементы модуля в сеанс, а затем возвращает объект **PSCustomObject** вместо объекта **PSModuleInfo** .</span><span class="sxs-lookup"><span data-stu-id="5f57b-248">When you use the **AsCustomObject** parameter, `Import-Module` imports the module members into the session and then returns a **PSCustomObject** object instead of a **PSModuleInfo** object.</span></span> <span data-ttu-id="5f57b-249">Пользовательский объект можно сохранить в переменную и использовать точку для вызова элементов.</span><span class="sxs-lookup"><span data-stu-id="5f57b-249">You can save the custom object in a variable and use dot notation to invoke the members.</span></span>

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

### <span data-ttu-id="5f57b-250">-Assembly</span><span class="sxs-lookup"><span data-stu-id="5f57b-250">-Assembly</span></span>

<span data-ttu-id="5f57b-251">Задает массив объектов Assembly.</span><span class="sxs-lookup"><span data-stu-id="5f57b-251">Specifies an array of assembly objects.</span></span> <span data-ttu-id="5f57b-252">Этот командлет импортирует командлеты и поставщики, реализованные в указанных объектах сборки.</span><span class="sxs-lookup"><span data-stu-id="5f57b-252">This cmdlet imports the cmdlets and providers implemented in the specified assembly objects.</span></span> <span data-ttu-id="5f57b-253">Введите переменную, которая содержит объекты сборки, или команду, которая создает объекты сборки.</span><span class="sxs-lookup"><span data-stu-id="5f57b-253">Enter a variable that contains assembly objects or a command that creates assembly objects.</span></span> <span data-ttu-id="5f57b-254">Также можно передать объект сборки в `Import-Module` .</span><span class="sxs-lookup"><span data-stu-id="5f57b-254">You can also pipe an assembly object to `Import-Module`.</span></span>

<span data-ttu-id="5f57b-255">При использовании этого параметра импортируются только командлеты и поставщики, реализованные в указанных сборках.</span><span class="sxs-lookup"><span data-stu-id="5f57b-255">When you use this parameter, only the cmdlets and providers implemented by the specified assemblies are imported.</span></span> <span data-ttu-id="5f57b-256">Если модуль содержит другие файлы, они не импортируются и могут отсутствовать важные члены модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-256">If the module contains other files, they aren't imported, and you might be missing important members of the module.</span></span> <span data-ttu-id="5f57b-257">Этот параметр используется для отладки и тестирования модуля, а также при указании его использования автором модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-257">Use this parameter for debugging and testing the module, or when you're instructed to use it by the module author.</span></span>

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

### <span data-ttu-id="5f57b-258">-Цимнамеспаце</span><span class="sxs-lookup"><span data-stu-id="5f57b-258">-CimNamespace</span></span>

<span data-ttu-id="5f57b-259">Задает пространство имен для альтернативного поставщика CIM, предоставляющего модули CIM.</span><span class="sxs-lookup"><span data-stu-id="5f57b-259">Specifies the namespace of an alternate CIM provider that exposes CIM modules.</span></span> <span data-ttu-id="5f57b-260">Значение по умолчанию — пространство имен поставщика модуля обнаружения WMI.</span><span class="sxs-lookup"><span data-stu-id="5f57b-260">The default value is the namespace of the Module Discovery WMI provider.</span></span>

<span data-ttu-id="5f57b-261">Этот параметр используется для импорта модулей CIM с компьютеров и устройств, которые не работают под управлением операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="5f57b-261">Use this parameter to import CIM modules from computers and devices that aren't running a Windows operating system.</span></span>

<span data-ttu-id="5f57b-262">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5f57b-262">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5f57b-263">-Цимресаурцеури</span><span class="sxs-lookup"><span data-stu-id="5f57b-263">-CimResourceUri</span></span>

<span data-ttu-id="5f57b-264">Задает альтернативное расположение для модулей CIM.</span><span class="sxs-lookup"><span data-stu-id="5f57b-264">Specifies an alternate location for CIM modules.</span></span> <span data-ttu-id="5f57b-265">Значение по умолчанию — URI ресурса поставщика модуля обнаружения WMI на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5f57b-265">The default value is the resource URI of the Module Discovery WMI provider on the remote computer.</span></span>

<span data-ttu-id="5f57b-266">Этот параметр используется для импорта модулей CIM с компьютеров и устройств, которые не работают под управлением операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="5f57b-266">Use this parameter to import CIM modules from computers and devices that aren't running a Windows operating system.</span></span>

<span data-ttu-id="5f57b-267">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5f57b-267">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5f57b-268">-CimSession</span><span class="sxs-lookup"><span data-stu-id="5f57b-268">-CimSession</span></span>

<span data-ttu-id="5f57b-269">Указывает сеанс CIM на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5f57b-269">Specifies a CIM session on the remote computer.</span></span> <span data-ttu-id="5f57b-270">Введите переменную, которая содержит сеанс CIM, или команду, которая получает сеанс CIM, например команду [Get-CimSession](../CimCmdlets/Get-CimSession.md) .</span><span class="sxs-lookup"><span data-stu-id="5f57b-270">Enter a variable that contains the CIM session or a command that gets the CIM session, such as a [Get-CimSession](../CimCmdlets/Get-CimSession.md) command.</span></span>

<span data-ttu-id="5f57b-271">`Import-Module` использует соединение с сеансом CIM для импорта модулей с удаленного компьютера в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="5f57b-271">`Import-Module` uses the CIM session connection to import modules from the remote computer into the current session.</span></span> <span data-ttu-id="5f57b-272">При использовании команд из импортированного модуля в текущем сеансе команды выполняются на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5f57b-272">When you use the commands from the imported module in the current session, the commands run on the remote computer.</span></span>

<span data-ttu-id="5f57b-273">Этот параметр можно использовать для импорта модулей с компьютеров и устройств, которые не работают под управлением операционной системы Windows, и компьютеров Windows с PowerShell, но не поддерживают удаленное взаимодействие PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f57b-273">You can use this parameter to import modules from computers and devices that aren't running the Windows operating system, and Windows computers that have PowerShell, but don't have PowerShell remoting enabled.</span></span>

<span data-ttu-id="5f57b-274">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5f57b-274">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5f57b-275">Командлет</span><span class="sxs-lookup"><span data-stu-id="5f57b-275">-Cmdlet</span></span>

<span data-ttu-id="5f57b-276">Указывает массив командлетов, которые этот командлет импортирует из модуля в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="5f57b-276">Specifies an array of cmdlets that this cmdlet imports from the module into the current session.</span></span>
<span data-ttu-id="5f57b-277">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="5f57b-277">Wildcard characters are permitted.</span></span>

<span data-ttu-id="5f57b-278">Некоторые модули автоматически экспортируют выбранные командлеты в сеанс при импорте модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-278">Some modules automatically export selected cmdlets into your session when you import the module.</span></span>
<span data-ttu-id="5f57b-279">Этот параметр позволяет выбрать один из экспортированных командлетов.</span><span class="sxs-lookup"><span data-stu-id="5f57b-279">This parameter lets you select from among the exported cmdlets.</span></span>

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

### <span data-ttu-id="5f57b-280">-DisableNameChecking</span><span class="sxs-lookup"><span data-stu-id="5f57b-280">-DisableNameChecking</span></span>

<span data-ttu-id="5f57b-281">Указывает, что этот командлет подавляет сообщение, выдающее предупреждение при импорте командлета или функции, имя которой включает неутвержденную команду или запрещенный символ.</span><span class="sxs-lookup"><span data-stu-id="5f57b-281">Indicates that this cmdlet suppresses the message that warns you when you import a cmdlet or function whose name includes an unapproved verb or a prohibited character.</span></span>

<span data-ttu-id="5f57b-282">По умолчанию, когда импортируемый модуль экспортирует командлеты или функции с неодобренными командами в именах, PowerShell выводит следующее предупреждающее сообщение:</span><span class="sxs-lookup"><span data-stu-id="5f57b-282">By default, when a module that you import exports cmdlets or functions that have unapproved verbs in their names, PowerShell displays the following warning message:</span></span>

> <span data-ttu-id="5f57b-283">ПРЕДУПРЕЖДЕНИЕ. Некоторые импортированные имена команд включают неутвержденные команды, которые могут сделать их менее обнаруживаемыми.</span><span class="sxs-lookup"><span data-stu-id="5f57b-283">WARNING: Some imported command names include unapproved verbs which might make them less discoverable.</span></span> <span data-ttu-id="5f57b-284">Чтобы получить подробные сведения, используйте параметр Verbose, или введите Get-Verb, чтобы просмотреть список утвержденных команд.</span><span class="sxs-lookup"><span data-stu-id="5f57b-284">Use the Verbose parameter for more detail or type Get-Verb to see the list of approved verbs.</span></span>

<span data-ttu-id="5f57b-285">Это сообщение является всего лишь предупреждением.</span><span class="sxs-lookup"><span data-stu-id="5f57b-285">This message is only a warning.</span></span> <span data-ttu-id="5f57b-286">Импорт осуществляется для всего модуля, включая недопустимые команды.</span><span class="sxs-lookup"><span data-stu-id="5f57b-286">The complete module is still imported, including the non-conforming commands.</span></span> <span data-ttu-id="5f57b-287">Хотя это сообщение отображается для пользователей модуля, проблема с именованием должна быть устранена автором модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-287">Although the message is displayed to module users, the naming problem should be fixed by the module author.</span></span>

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

### <span data-ttu-id="5f57b-288">-Force</span><span class="sxs-lookup"><span data-stu-id="5f57b-288">-Force</span></span>

<span data-ttu-id="5f57b-289">Этот параметр приводит к тому, что модуль загружается или перегружается поверх текущего.</span><span class="sxs-lookup"><span data-stu-id="5f57b-289">This parameter causes a module to be loaded, or reloaded, over top of the current one.</span></span>

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

### <span data-ttu-id="5f57b-290">-FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="5f57b-290">-FullyQualifiedName</span></span>

<span data-ttu-id="5f57b-291">Указывает полное имя модуля в виде хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="5f57b-291">Specifies the fully qualified name of the module as a hash table.</span></span> <span data-ttu-id="5f57b-292">Значение может быть сочетанием строк и хэш-таблиц.</span><span class="sxs-lookup"><span data-stu-id="5f57b-292">The value can be a combination of strings and hash tables.</span></span> <span data-ttu-id="5f57b-293">Хэш-таблица содержит следующие ключи.</span><span class="sxs-lookup"><span data-stu-id="5f57b-293">The hash table has the following keys.</span></span>

- <span data-ttu-id="5f57b-294">`ModuleName` - **Обязательное требование** Указывает имя модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-294">`ModuleName` - **Required** Specifies the module name.</span></span>
- <span data-ttu-id="5f57b-295">`GUID` - **Необязательно** Указывает идентификатор GUID модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-295">`GUID` - **Optional** Specifies the GUID of the module.</span></span>
- <span data-ttu-id="5f57b-296">**Также необходимо** указать один из трех указанных ниже ключей.</span><span class="sxs-lookup"><span data-stu-id="5f57b-296">It's also **Required** to specify one of the three below keys.</span></span> <span data-ttu-id="5f57b-297">Эти ключи нельзя использовать совместно.</span><span class="sxs-lookup"><span data-stu-id="5f57b-297">These keys can't be used together.</span></span>
  - <span data-ttu-id="5f57b-298">`ModuleVersion` — Указывает минимальную допустимую версию модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-298">`ModuleVersion` - Specifies a minimum acceptable version of the module.</span></span>
  - <span data-ttu-id="5f57b-299">`RequiredVersion` — Указывает точную, требуемую версию модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-299">`RequiredVersion` - Specifies an exact, required version of the module.</span></span>
  - <span data-ttu-id="5f57b-300">`MaximumVersion` — Указывает максимально допустимую версию модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-300">`MaximumVersion` - Specifies the maximum acceptable version of the module.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: FullyQualifiedName, FullyQualifiedNameAndPSSession, FullyQualifiedNameAndWinCompat
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="5f57b-301">-Function</span><span class="sxs-lookup"><span data-stu-id="5f57b-301">-Function</span></span>

<span data-ttu-id="5f57b-302">Указывает массив функций, которые этот командлет импортирует из модуля в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="5f57b-302">Specifies an array of functions that this cmdlet imports from the module into the current session.</span></span>
<span data-ttu-id="5f57b-303">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="5f57b-303">Wildcard characters are permitted.</span></span> <span data-ttu-id="5f57b-304">Некоторые модули автоматически экспортируют выбранные функции в сеанс при импорте модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-304">Some modules automatically export selected functions into your session when you import the module.</span></span> <span data-ttu-id="5f57b-305">Этот параметр позволяет выбрать один из экспортированных функций.</span><span class="sxs-lookup"><span data-stu-id="5f57b-305">This parameter lets you select from among the exported functions.</span></span>

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

### <span data-ttu-id="5f57b-306">-Global</span><span class="sxs-lookup"><span data-stu-id="5f57b-306">-Global</span></span>

<span data-ttu-id="5f57b-307">Указывает, что этот командлет импортирует модули в глобальное состояние сеанса, чтобы они были доступны для всех команд в сеансе.</span><span class="sxs-lookup"><span data-stu-id="5f57b-307">Indicates that this cmdlet imports modules into the global session state so they are available to all commands in the session.</span></span>

<span data-ttu-id="5f57b-308">По умолчанию при `Import-Module` вызове командлета из командной строки, файла скрипта или сценария ScriptBlock все команды импортируются в глобальное состояние сеанса.</span><span class="sxs-lookup"><span data-stu-id="5f57b-308">By default, when `Import-Module` cmdlet is called from the command prompt, script file, or scriptblock, all the commands are imported into the global session state.</span></span>

<span data-ttu-id="5f57b-309">При вызове из другого модуля `Import-Module` командлет импортирует команды в модуль, включая команды из вложенных модулей, в состояние сеанса вызывающего модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-309">When invoked from another module, `Import-Module` cmdlet imports the commands in a module, including commands from nested modules, into the calling module's session state.</span></span>

> [!TIP]
> <span data-ttu-id="5f57b-310">Следует избегать вызова `Import-Module` из модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-310">You should avoid calling `Import-Module` from within a module.</span></span> <span data-ttu-id="5f57b-311">Вместо этого следует объявить целевой модуль как вложенный модуль в манифесте родительского модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-311">Instead, declare the target module as a nested module in the parent module's manifest.</span></span> <span data-ttu-id="5f57b-312">Объявление вложенных модулей повышает возможность обнаружения зависимостей.</span><span class="sxs-lookup"><span data-stu-id="5f57b-312">Declaring nested modules improves the discoverability of dependencies.</span></span>

<span data-ttu-id="5f57b-313">Параметр **Global** аналогичен параметру **Scope** со значением **Global** .</span><span class="sxs-lookup"><span data-stu-id="5f57b-313">The **Global** parameter is equivalent to the **Scope** parameter with a value of **Global** .</span></span>

<span data-ttu-id="5f57b-314">Чтобы ограничить команды, экспортируемые модулем, используйте `Export-ModuleMember` команду в модуле script.</span><span class="sxs-lookup"><span data-stu-id="5f57b-314">To restrict the commands that a module exports, use an `Export-ModuleMember` command in the script module.</span></span>

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

### <span data-ttu-id="5f57b-315">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="5f57b-315">-MaximumVersion</span></span>

<span data-ttu-id="5f57b-316">Указывает максимальную версию.</span><span class="sxs-lookup"><span data-stu-id="5f57b-316">Specifies a maximum version.</span></span> <span data-ttu-id="5f57b-317">Этот командлет импортирует только версию модуля, которая меньше или равна указанному значению.</span><span class="sxs-lookup"><span data-stu-id="5f57b-317">This cmdlet imports only a version of the module that is less than or equal to the specified value.</span></span> <span data-ttu-id="5f57b-318">Если версия не соответствует требованиям, функция `Import-Module` возвращает ошибку.</span><span class="sxs-lookup"><span data-stu-id="5f57b-318">If no version qualifies, `Import-Module` returns an error.</span></span>

```yaml
Type: System.String
Parameter Sets: Name, PSSession, CimSession, WinCompat
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5f57b-319">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="5f57b-319">-MinimumVersion</span></span>

<span data-ttu-id="5f57b-320">Указывает минимальную версию.</span><span class="sxs-lookup"><span data-stu-id="5f57b-320">Specifies a minimum version.</span></span> <span data-ttu-id="5f57b-321">Этот командлет импортирует только версию модуля, которая больше или равна указанному значению.</span><span class="sxs-lookup"><span data-stu-id="5f57b-321">This cmdlet imports only a version of the module that is greater than or equal to the specified value.</span></span> <span data-ttu-id="5f57b-322">Используйте имя параметра **MinimumVersion** или его псевдоним, **Version** .</span><span class="sxs-lookup"><span data-stu-id="5f57b-322">Use the **MinimumVersion** parameter name or its alias, **Version** .</span></span> <span data-ttu-id="5f57b-323">Если версия не соответствует требованиям, `Import-Module` выдает ошибку.</span><span class="sxs-lookup"><span data-stu-id="5f57b-323">If no version qualifies, `Import-Module` generates an error.</span></span>

<span data-ttu-id="5f57b-324">Чтобы указать точную версию, используйте параметр **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="5f57b-324">To specify an exact version, use the **RequiredVersion** parameter.</span></span> <span data-ttu-id="5f57b-325">Можно также использовать параметры **модуля** и **версии** ключевого слова **#Requires** , чтобы требовать определенную версию модуля в скрипте.</span><span class="sxs-lookup"><span data-stu-id="5f57b-325">You can also use the **Module** and **Version** parameters of the **#Requires** keyword to require a specific version of a module in a script.</span></span>

<span data-ttu-id="5f57b-326">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5f57b-326">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Version
Parameter Sets: Name, PSSession, CimSession, WinCompat
Aliases: Version

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5f57b-327">-ModuleInfo</span><span class="sxs-lookup"><span data-stu-id="5f57b-327">-ModuleInfo</span></span>

<span data-ttu-id="5f57b-328">Указывает массив объектов модуля для импорта.</span><span class="sxs-lookup"><span data-stu-id="5f57b-328">Specifies an array of module objects to import.</span></span> <span data-ttu-id="5f57b-329">Введите переменную, содержащую объекты модуля, или команду, которая получает объекты модуля, например следующую команду: `Get-Module -ListAvailable` .</span><span class="sxs-lookup"><span data-stu-id="5f57b-329">Enter a variable that contains the module objects, or a command that gets the module objects, such as the following command: `Get-Module -ListAvailable`.</span></span> <span data-ttu-id="5f57b-330">Также можно передать объекты модуля в `Import-Module` .</span><span class="sxs-lookup"><span data-stu-id="5f57b-330">You can also pipe module objects to `Import-Module`.</span></span>

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

### <span data-ttu-id="5f57b-331">-Name</span><span class="sxs-lookup"><span data-stu-id="5f57b-331">-Name</span></span>

<span data-ttu-id="5f57b-332">Задает имена модулей для импорта.</span><span class="sxs-lookup"><span data-stu-id="5f57b-332">Specifies the names of the modules to import.</span></span> <span data-ttu-id="5f57b-333">Введите имя модуля или имя файла в модуле, например `.psd1` файл,, `.psm1` `.dll` или `.ps1` .</span><span class="sxs-lookup"><span data-stu-id="5f57b-333">Enter the name of the module or the name of a file in the module, such as a `.psd1`, `.psm1`, `.dll`, or `.ps1` file.</span></span> <span data-ttu-id="5f57b-334">Пути к файлам являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="5f57b-334">File paths are optional.</span></span> <span data-ttu-id="5f57b-335">Подстановочные знаки не допускаются.</span><span class="sxs-lookup"><span data-stu-id="5f57b-335">Wildcard characters aren't permitted.</span></span> <span data-ttu-id="5f57b-336">Можно также передать имена модулей и имен файлов в `Import-Module` .</span><span class="sxs-lookup"><span data-stu-id="5f57b-336">You can also pipe module names and filenames to `Import-Module`.</span></span>

<span data-ttu-id="5f57b-337">Если опустить путь, `Import-Module` ищет модуль в путях, сохраненных в `$env:PSModulePath` переменной среды.</span><span class="sxs-lookup"><span data-stu-id="5f57b-337">If you omit a path, `Import-Module` looks for the module in the paths saved in the `$env:PSModulePath` environment variable.</span></span>

<span data-ttu-id="5f57b-338">По возможности указывайте только имя модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-338">Specify only the module name whenever possible.</span></span> <span data-ttu-id="5f57b-339">Если указать имя файла, импортируются только элементы, реализованные в этом файле.</span><span class="sxs-lookup"><span data-stu-id="5f57b-339">When you specify a file name, only the members that are implemented in that file are imported.</span></span> <span data-ttu-id="5f57b-340">Если модуль содержит другие файлы, они не импортируются и могут отсутствовать важные члены модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-340">If the module contains other files, they aren't imported, and you might be missing important members of the module.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name, PSSession, CimSession, WinCompat
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="5f57b-341">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="5f57b-341">-NoClobber</span></span>

<span data-ttu-id="5f57b-342">Предотвращает импорт команд, имеющих те же имена, что и существующие команды в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="5f57b-342">Prevents importing commands that have the same names as existing commands in the current session.</span></span> <span data-ttu-id="5f57b-343">По умолчанию `Import-Module` импортирует все команды экспортированного модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-343">By default, `Import-Module` imports all exported module commands.</span></span>

<span data-ttu-id="5f57b-344">Команды с одинаковыми именами могут скрывать или заменять команды в сеансе.</span><span class="sxs-lookup"><span data-stu-id="5f57b-344">Commands that have the same names can hide or replace commands in the session.</span></span> <span data-ttu-id="5f57b-345">Чтобы избежать конфликта имен команд в сеансе, используйте параметр **Prefix** или **NoClobber** .</span><span class="sxs-lookup"><span data-stu-id="5f57b-345">To avoid command name conflicts in a session, use the **Prefix** or **NoClobber** parameters.</span></span> <span data-ttu-id="5f57b-346">Дополнительные сведения о конфликтах имен и приоритете команд см. в разделе "Конфликты модулей и имен" в статьях [about_Modules](about/about_Modules.md) и [about_Command_Precedence](about/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="5f57b-346">For more information about name conflicts and command precedence, see "Modules and Name Conflicts" in [about_Modules](about/about_Modules.md) and [about_Command_Precedence](about/about_Command_Precedence.md).</span></span>

<span data-ttu-id="5f57b-347">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5f57b-347">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5f57b-348">-PassThru</span><span class="sxs-lookup"><span data-stu-id="5f57b-348">-PassThru</span></span>

<span data-ttu-id="5f57b-349">Возвращает объект, представляющий элемент, с которым выполняется работа.</span><span class="sxs-lookup"><span data-stu-id="5f57b-349">Returns an object representing the item with which you're working.</span></span> <span data-ttu-id="5f57b-350">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="5f57b-350">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="5f57b-351">— Префикс</span><span class="sxs-lookup"><span data-stu-id="5f57b-351">-Prefix</span></span>

<span data-ttu-id="5f57b-352">Задает префикс, который добавляется этим командлетом к существительным в именах импортированных элементов модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-352">Specifies a prefix that this cmdlet adds to the nouns in the names of imported module members.</span></span>

<span data-ttu-id="5f57b-353">Используйте этот параметр, чтобы избежать конфликтов имен, которые могут возникать, когда имена элементов совпадают с именами элементов в сеансе.</span><span class="sxs-lookup"><span data-stu-id="5f57b-353">Use this parameter to avoid name conflicts that might occur when different members in the session have the same name.</span></span> <span data-ttu-id="5f57b-354">Этот параметр не изменяет модуль и не влияет на файлы, импортируемые модулем для его собственного использования.</span><span class="sxs-lookup"><span data-stu-id="5f57b-354">This parameter does not change the module, and it does not affect files that the module imports for its own use.</span></span> <span data-ttu-id="5f57b-355">Они называются вложенными модулями.</span><span class="sxs-lookup"><span data-stu-id="5f57b-355">These are known as nested modules.</span></span> <span data-ttu-id="5f57b-356">Этот командлет влияет только на имена элементов в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="5f57b-356">This cmdlet affects only the names of members in the current session.</span></span>

<span data-ttu-id="5f57b-357">Например, если указать префикс UTC, а затем импортировать `Get-Date` командлет, то этот командлет будет известен в сеансе как `Get-UTCDate` , и он не будет путать с исходным `Get-Date` командлетом.</span><span class="sxs-lookup"><span data-stu-id="5f57b-357">For example, if you specify the prefix UTC and then import a `Get-Date` cmdlet, the cmdlet is known in the session as `Get-UTCDate`, and it is not confused with the original `Get-Date` cmdlet.</span></span>

<span data-ttu-id="5f57b-358">Значение этого параметра имеет приоритет над свойством **DefaultCommandPrefix** модуля, который определяет префикс по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5f57b-358">The value of this parameter takes precedence over the **DefaultCommandPrefix** property of the module, which specifies the default prefix.</span></span>

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

### <span data-ttu-id="5f57b-359">-PSSession</span><span class="sxs-lookup"><span data-stu-id="5f57b-359">-PSSession</span></span>

<span data-ttu-id="5f57b-360">Указывает управляемый пользователем сеанс PowerShell ( **PSSession** ), из которого этот командлет импортирует модули в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="5f57b-360">Specifies a PowerShell user-managed session ( **PSSession** ) from which this cmdlet imports modules into the current session.</span></span> <span data-ttu-id="5f57b-361">Введите переменную, содержащую **сеанс PSSession** или команду, которая получает **PSSession** , например `Get-PSSession` команду.</span><span class="sxs-lookup"><span data-stu-id="5f57b-361">Enter a variable that contains a **PSSession** or a command that gets a **PSSession** , such as a `Get-PSSession` command.</span></span>

<span data-ttu-id="5f57b-362">При импорте модуля из другого сеанса в текущий сеанс командлеты из модуля в текущем сеансе можно использовать, как и командлеты из локального модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-362">When you import a module from a different session into the current session, you can use the cmdlets from the module in the current session, just as you would use cmdlets from a local module.</span></span> <span data-ttu-id="5f57b-363">Команды, использующие удаленные командлеты, выполняются в удаленном сеансе, но сведения об удаленном взаимодействии управляются в фоновом режиме с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f57b-363">Commands that use the remote cmdlets run in the remote session, but the remoting details are managed in the background by PowerShell.</span></span>

<span data-ttu-id="5f57b-364">Этот параметр использует функцию неявного удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f57b-364">This parameter uses the Implicit Remoting feature of PowerShell.</span></span> <span data-ttu-id="5f57b-365">Он эквивалентен использованию `Import-PSSession` командлета для импорта определенных модулей из сеанса.</span><span class="sxs-lookup"><span data-stu-id="5f57b-365">It is equivalent to using the `Import-PSSession` cmdlet to import particular modules from a session.</span></span>

<span data-ttu-id="5f57b-366">`Import-Module` невозможно импортировать модули PowerShell Core из другого сеанса.</span><span class="sxs-lookup"><span data-stu-id="5f57b-366">`Import-Module` cannot import PowerShell Core modules from another session.</span></span> <span data-ttu-id="5f57b-367">Имена модулей PowerShell Core начинаются с Microsoft. PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f57b-367">The PowerShell Core modules have names that begin with Microsoft.PowerShell.</span></span>

<span data-ttu-id="5f57b-368">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5f57b-368">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5f57b-369">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="5f57b-369">-RequiredVersion</span></span>

<span data-ttu-id="5f57b-370">Указывает версию модуля, который импортирует этот командлет.</span><span class="sxs-lookup"><span data-stu-id="5f57b-370">Specifies a version of the module that this cmdlet imports.</span></span> <span data-ttu-id="5f57b-371">Если версия не установлена, `Import-Module` создает ошибку.</span><span class="sxs-lookup"><span data-stu-id="5f57b-371">If the version is not installed, `Import-Module` generates an error.</span></span>

<span data-ttu-id="5f57b-372">По умолчанию `Import-Module` импортирует модуль без проверки номера версии.</span><span class="sxs-lookup"><span data-stu-id="5f57b-372">By default, `Import-Module` imports the module without checking the version number.</span></span>

<span data-ttu-id="5f57b-373">Чтобы указать минимальную версию, используйте параметр **MinimumVersion** .</span><span class="sxs-lookup"><span data-stu-id="5f57b-373">To specify a minimum version, use the **MinimumVersion** parameter.</span></span> <span data-ttu-id="5f57b-374">Можно также использовать параметры **модуля** и **версии** ключевого слова **#Requires** , чтобы требовать определенную версию модуля в скрипте.</span><span class="sxs-lookup"><span data-stu-id="5f57b-374">You can also use the **Module** and **Version** parameters of the **#Requires** keyword to require a specific version of a module in a script.</span></span>

<span data-ttu-id="5f57b-375">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5f57b-375">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="5f57b-376">Сценарии, использующие **RequiredVersion** для импорта модулей, входящих в состав существующих выпусков операционной системы Windows, не выполняются автоматически в будущих выпусках операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="5f57b-376">Scripts that use **RequiredVersion** to import modules that are included with existing releases of the Windows operating system don't automatically run in future releases of the Windows operating system.</span></span> <span data-ttu-id="5f57b-377">Это обусловлено тем, что номера версий модулей PowerShell в будущих выпусках операционной системы Windows выше, чем номера версий модулей в существующих выпусках операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="5f57b-377">This is because PowerShell module version numbers in future releases of the Windows operating system are higher than module version numbers in existing releases of the Windows operating system.</span></span>

```yaml
Type: System.Version
Parameter Sets: Name, PSSession, CimSession, WinCompat
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5f57b-378">-Scope</span><span class="sxs-lookup"><span data-stu-id="5f57b-378">-Scope</span></span>

<span data-ttu-id="5f57b-379">Указывает область, в которой этот командлет импортирует модуль.</span><span class="sxs-lookup"><span data-stu-id="5f57b-379">Specifies a scope into which this cmdlet imports the module.</span></span>

<span data-ttu-id="5f57b-380">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="5f57b-380">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="5f57b-381">**Глобальный** .</span><span class="sxs-lookup"><span data-stu-id="5f57b-381">**Global** .</span></span> <span data-ttu-id="5f57b-382">доступно для всех команд в сеансе.</span><span class="sxs-lookup"><span data-stu-id="5f57b-382">Available to all commands in the session.</span></span> <span data-ttu-id="5f57b-383">Эквивалентно параметру **Global** .</span><span class="sxs-lookup"><span data-stu-id="5f57b-383">Equivalent to the **Global** parameter.</span></span>
- <span data-ttu-id="5f57b-384">**Локальный** .</span><span class="sxs-lookup"><span data-stu-id="5f57b-384">**Local** .</span></span> <span data-ttu-id="5f57b-385">доступно только в текущей области.</span><span class="sxs-lookup"><span data-stu-id="5f57b-385">Available only in the current scope.</span></span>

<span data-ttu-id="5f57b-386">По умолчанию при `Import-Module` вызове командлета из командной строки, файла скрипта или сценария ScriptBlock все команды импортируются в глобальное состояние сеанса.</span><span class="sxs-lookup"><span data-stu-id="5f57b-386">By default, when `Import-Module` cmdlet is called from the command prompt, script file, or scriptblock, all the commands are imported into the global session state.</span></span> <span data-ttu-id="5f57b-387">Можно использовать параметр **-Scope** со значением **Local** для импорта содержимого модуля в область скрипта или ScriptBlock.</span><span class="sxs-lookup"><span data-stu-id="5f57b-387">You can use the **-Scope** parameter with the value of **Local** to import module content into the script or scriptblock scope.</span></span>

<span data-ttu-id="5f57b-388">При вызове из другого модуля `Import-Module` командлет импортирует команды в модуль, включая команды из вложенных модулей, в состояние сеанса вызывающего.</span><span class="sxs-lookup"><span data-stu-id="5f57b-388">When invoked from another module, `Import-Module` cmdlet imports the commands in a module, including commands from nested modules, into the caller's session state.</span></span> <span data-ttu-id="5f57b-389">Указание `-Scope Global` или `-Global` указывает, что этот командлет импортирует модули в глобальное состояние сеанса, поэтому они доступны для всех команд в сеансе.</span><span class="sxs-lookup"><span data-stu-id="5f57b-389">Specifying `-Scope Global` or `-Global` indicates that this cmdlet imports modules into the global session state so they are available to all commands in the session.</span></span>

<span data-ttu-id="5f57b-390">**Глобальный** параметр эквивалентен параметру **Scope** со значением Global.</span><span class="sxs-lookup"><span data-stu-id="5f57b-390">The **Global** parameter is equivalent to the **Scope** parameter with a value of Global.</span></span>

<span data-ttu-id="5f57b-391">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="5f57b-391">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5f57b-392">-Variable</span><span class="sxs-lookup"><span data-stu-id="5f57b-392">-Variable</span></span>

<span data-ttu-id="5f57b-393">Указывает массив переменных, которые этот командлет импортирует из модуля в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="5f57b-393">Specifies an array of variables that this cmdlet imports from the module into the current session.</span></span>
<span data-ttu-id="5f57b-394">Введите список переменных.</span><span class="sxs-lookup"><span data-stu-id="5f57b-394">Enter a list of variables.</span></span> <span data-ttu-id="5f57b-395">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="5f57b-395">Wildcard characters are permitted.</span></span>

<span data-ttu-id="5f57b-396">Некоторые модули автоматически экспортируют выбранные переменные в сеанс при импорте модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-396">Some modules automatically export selected variables into your session when you import the module.</span></span>
<span data-ttu-id="5f57b-397">Этот параметр позволяет выбрать один из экспортированных переменных.</span><span class="sxs-lookup"><span data-stu-id="5f57b-397">This parameter lets you select from among the exported variables.</span></span>

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

### <span data-ttu-id="5f57b-398">-Скипедитиончекк</span><span class="sxs-lookup"><span data-stu-id="5f57b-398">-SkipEditionCheck</span></span>

<span data-ttu-id="5f57b-399">Пропускает проверку на `CompatiblePSEditions` поле.</span><span class="sxs-lookup"><span data-stu-id="5f57b-399">Skips the check on the `CompatiblePSEditions` field.</span></span>

<span data-ttu-id="5f57b-400">Позволяет загрузить модуль из `"$($env:windir)\System32\WindowsPowerShell\v1.0\Modules"` каталога модуля в PowerShell Core, если этот модуль не указан `Core` в `CompatiblePSEditions` поле манифеста.</span><span class="sxs-lookup"><span data-stu-id="5f57b-400">Allows loading a module from the `"$($env:windir)\System32\WindowsPowerShell\v1.0\Modules"` module directory into PowerShell Core when that module does not specify `Core` in the `CompatiblePSEditions` manifest field.</span></span>

<span data-ttu-id="5f57b-401">При импорте модуля из другого пути этот параметр не выполняет никаких действий, так как проверка не выполняется.</span><span class="sxs-lookup"><span data-stu-id="5f57b-401">When importing a module from another path, this switch does nothing, since the check is not performed.</span></span> <span data-ttu-id="5f57b-402">В Linux и macOS этот параметр не выполняет никаких действий.</span><span class="sxs-lookup"><span data-stu-id="5f57b-402">On Linux and macOS, this switch does nothing.</span></span>

<span data-ttu-id="5f57b-403">Дополнительные сведения см. в разделе [about_PowerShell_Editions](About/about_PowerShell_Editions.md).</span><span class="sxs-lookup"><span data-stu-id="5f57b-403">For more information, see [about_PowerShell_Editions](About/about_PowerShell_Editions.md).</span></span>

> [!WARNING]
> <span data-ttu-id="5f57b-404">`Import-Module -SkipEditionCheck` по-прежнему может не импортировать модуль.</span><span class="sxs-lookup"><span data-stu-id="5f57b-404">`Import-Module -SkipEditionCheck` is still likely to fail to import a module.</span></span> <span data-ttu-id="5f57b-405">Даже если он завершится успешно, при попытке использовать несовместимый API вызов команды из модуля может завершиться ошибкой.</span><span class="sxs-lookup"><span data-stu-id="5f57b-405">Even if it does succeed, invoking a command from the module may later fail when it tries to use an incompatible API.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Name, PSSession, CimSession, FullyQualifiedName, FullyQualifiedNameAndPSSession, Assembly, ModuleInfo
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5f57b-406">-Усевиндовсповершелл</span><span class="sxs-lookup"><span data-stu-id="5f57b-406">-UseWindowsPowerShell</span></span>

<span data-ttu-id="5f57b-407">Загружает модуль с помощью функции совместимости Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f57b-407">Loads module using Windows PowerShell Compatibility functionality.</span></span> <span data-ttu-id="5f57b-408">Дополнительные сведения см. в разделе [about_Windows_PowerShell_Compatibility](About/about_Windows_PowerShell_Compatibility.md) .</span><span class="sxs-lookup"><span data-stu-id="5f57b-408">See [about_Windows_PowerShell_Compatibility](About/about_Windows_PowerShell_Compatibility.md) for more information.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WinCompat, FullyQualifiedNameAndWinCompat
Aliases: UseWinPS

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5f57b-409">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="5f57b-409">CommonParameters</span></span>

<span data-ttu-id="5f57b-410">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5f57b-410">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5f57b-411">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5f57b-411">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5f57b-412">Входные данные</span><span class="sxs-lookup"><span data-stu-id="5f57b-412">INPUTS</span></span>

### <span data-ttu-id="5f57b-413">System. String, System. Management. Automation. PSModuleInfo, System. Reflection. Assembly</span><span class="sxs-lookup"><span data-stu-id="5f57b-413">System.String, System.Management.Automation.PSModuleInfo, System.Reflection.Assembly</span></span>

<span data-ttu-id="5f57b-414">В этот командлет можно передать имя модуля, объект модуля или объект сборки.</span><span class="sxs-lookup"><span data-stu-id="5f57b-414">You can pipe a module name, module object, or assembly object to this cmdlet.</span></span>

## <span data-ttu-id="5f57b-415">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="5f57b-415">OUTPUTS</span></span>

### <span data-ttu-id="5f57b-416">None, System. Management. Automation. PSModuleInfo или System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="5f57b-416">None, System.Management.Automation.PSModuleInfo, or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="5f57b-417">По умолчанию не `Import-Module` создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="5f57b-417">By default, `Import-Module` does not generate any output.</span></span> <span data-ttu-id="5f57b-418">Если указан параметр **PassThru** , командлет создает объект **System. Management. Automation. PSModuleInfo** , представляющий модуль.</span><span class="sxs-lookup"><span data-stu-id="5f57b-418">If you specify the **PassThru** parameter, the cmdlet generates a **System.Management.Automation.PSModuleInfo** object that represents the module.</span></span> <span data-ttu-id="5f57b-419">При указании параметра **AsCustomObject** создается объект **PSCustomObject** .</span><span class="sxs-lookup"><span data-stu-id="5f57b-419">If you specify the **AsCustomObject** parameter, it generates a **PSCustomObject** object.</span></span>

## <span data-ttu-id="5f57b-420">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="5f57b-420">NOTES</span></span>

- <span data-ttu-id="5f57b-421">Перед импортом модуля необходимо установить модуль на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5f57b-421">Before you can import a module, the module must be installed on the local computer.</span></span> <span data-ttu-id="5f57b-422">То есть каталог модуля должен быть скопирован в каталог, доступный локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="5f57b-422">That is, the module directory must be copied to a directory that is accessible to your local computer.</span></span> <span data-ttu-id="5f57b-423">Дополнительные сведения см. в разделе [about_Modules](About/about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="5f57b-423">For more information, see [about_Modules](About/about_Modules.md).</span></span>

  <span data-ttu-id="5f57b-424">Для импорта модулей, установленных на удаленных компьютерах, можно также использовать параметры **PSSession** и **CIMSession** .</span><span class="sxs-lookup"><span data-stu-id="5f57b-424">You can also use the **PSSession** and **CIMSession** parameters to import modules that are installed on remote computers.</span></span> <span data-ttu-id="5f57b-425">Однако команды, использующие командлеты в этих модулях, выполняются в удаленном сеансе на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5f57b-425">However, commands that use the cmdlets in these modules run in the remote session on the remote computer.</span></span>

- <span data-ttu-id="5f57b-426">Если в сеансе импортируются элементы с одинаковым именем и типом, то в PowerShell по умолчанию используется элемент, импортированный последним.</span><span class="sxs-lookup"><span data-stu-id="5f57b-426">If you import members with the same name and the same type into your session, PowerShell uses the member imported last by default.</span></span> <span data-ttu-id="5f57b-427">Переменные и псевдонимы заменяются, и исходные значения недоступны.</span><span class="sxs-lookup"><span data-stu-id="5f57b-427">Variables and aliases are replaced, and the originals aren't accessible.</span></span> <span data-ttu-id="5f57b-428">Функции, командлеты и поставщики просто затенены новыми элементами.</span><span class="sxs-lookup"><span data-stu-id="5f57b-428">Functions, cmdlets, and providers are merely shadowed by the new members.</span></span> <span data-ttu-id="5f57b-429">Доступ к ним можно получить, добавив в имя команды имя своей оснастки, модуля или пути к функции.</span><span class="sxs-lookup"><span data-stu-id="5f57b-429">They can be accessed by qualifying the command name with the name of its snap-in, module, or function path.</span></span>

- <span data-ttu-id="5f57b-430">Чтобы обновить данные форматирования для команд, импортированных из модуля, используйте `Update-FormatData` командлет.</span><span class="sxs-lookup"><span data-stu-id="5f57b-430">To update the formatting data for commands that have been imported from a module, use the `Update-FormatData` cmdlet.</span></span> <span data-ttu-id="5f57b-431">`Update-FormatData` также обновляет данные форматирования для команд в сеансе, импортированных из модулей.</span><span class="sxs-lookup"><span data-stu-id="5f57b-431">`Update-FormatData` also updates the formatting data for commands in the session that were imported from modules.</span></span> <span data-ttu-id="5f57b-432">При изменении файла форматирования для модуля можно выполнить `Update-FormatData` команду, чтобы обновить данные форматирования для импортированных команд.</span><span class="sxs-lookup"><span data-stu-id="5f57b-432">If the formatting file for a module changes, you can run an `Update-FormatData` command to update the formatting data for imported commands.</span></span> <span data-ttu-id="5f57b-433">Импортировать модуль повторно не требуется.</span><span class="sxs-lookup"><span data-stu-id="5f57b-433">You don't need to import the module again.</span></span>

- <span data-ttu-id="5f57b-434">Начиная с Windows PowerShell 3,0, основные команды, устанавливаемые с помощью PowerShell, упаковываются в модули.</span><span class="sxs-lookup"><span data-stu-id="5f57b-434">Starting in Windows PowerShell 3.0, the core commands that are installed with PowerShell are packaged in modules.</span></span> <span data-ttu-id="5f57b-435">В Windows PowerShell 2,0 и в ведущих программах, которые создают сеансы предыдущих версий в более поздних версиях PowerShell, основные команды упаковываются в оснастки ( **PSSnapin** ).</span><span class="sxs-lookup"><span data-stu-id="5f57b-435">In Windows PowerShell 2.0, and in host programs that create older-style sessions in later versions of PowerShell, the core commands are packaged in snap-ins ( **PSSnapins** ).</span></span> <span data-ttu-id="5f57b-436">Исключением является **Microsoft. PowerShell. Core** , который всегда является оснасткой.</span><span class="sxs-lookup"><span data-stu-id="5f57b-436">The exception is **Microsoft.PowerShell.Core** , which is always a snap-in.</span></span> <span data-ttu-id="5f57b-437">Кроме того, удаленные сеансы, такие как запущенные `New-PSSession` командлетом, являются сеансами предыдущих версий, включающими основные оснастки.</span><span class="sxs-lookup"><span data-stu-id="5f57b-437">Also, remote sessions, such as those started by the `New-PSSession` cmdlet, are older-style sessions that include core snap-ins.</span></span>

  <span data-ttu-id="5f57b-438">Дополнительные сведения о методе **CreateDefault2** , который создает сеансы нового стиля с основными модулями, см. в описании [метода CreateDefault2](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2).</span><span class="sxs-lookup"><span data-stu-id="5f57b-438">For information about the **CreateDefault2** method that creates newer-style sessions with core modules, see the [CreateDefault2 Method](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2).</span></span>

- <span data-ttu-id="5f57b-439">`Import-Module` невозможно импортировать модули PowerShell Core из другого сеанса.</span><span class="sxs-lookup"><span data-stu-id="5f57b-439">`Import-Module` cannot import PowerShell Core modules from another session.</span></span> <span data-ttu-id="5f57b-440">Имена модулей PowerShell Core начинаются с `Microsoft.PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="5f57b-440">The PowerShell Core modules have names that begin with `Microsoft.PowerShell`.</span></span>

- <span data-ttu-id="5f57b-441">В Windows PowerShell 2,0 некоторые значения свойств объекта Module, такие как значения свойств **експортедкмдлетс** и **NestedModules** , не были заполнены до тех пор, пока модуль не будет импортирован и не был доступен в объекте Module, возвращаемом параметром **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="5f57b-441">In Windows PowerShell 2.0, some of the property values of the module object, such as the **ExportedCmdlets** and **NestedModules** property values, were not populated until the module was imported and were not available on the module object that the **PassThru** parameter returns.</span></span> <span data-ttu-id="5f57b-442">В Windows PowerShell 3,0 все значения свойств модуля заполняются.</span><span class="sxs-lookup"><span data-stu-id="5f57b-442">In Windows PowerShell 3.0, all module property values are populated.</span></span>

- <span data-ttu-id="5f57b-443">При попытке импортировать модуль, содержащий сборки в смешанном режиме, которые несовместимы с Windows PowerShell 3,0, `Import-Module` возвращает сообщение об ошибке следующего вида.</span><span class="sxs-lookup"><span data-stu-id="5f57b-443">If you attempt to import a module that contains mixed-mode assemblies that aren't compatible with Windows PowerShell 3.0, `Import-Module` returns an error message like the following one.</span></span>

  > <span data-ttu-id="5f57b-444">Import-Module: сборка смешанного режима построена на базе версии "v 2.0.50727" среды выполнения и не может быть загружена в среду выполнения 4,0 без дополнительных сведений о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5f57b-444">Import-Module : Mixed mode assembly is built against version 'v2.0.50727' of the runtime and cannot be loaded in the 4.0 runtime without additional configuration information.</span></span>

  <span data-ttu-id="5f57b-445">Эта ошибка возникает, когда модуль, разработанный для Windows PowerShell 2,0, содержит по крайней мере одну сборку смешанного модуля, то есть сборку, включающую как управляемый, так и неуправляемый код, например C++ и C#.</span><span class="sxs-lookup"><span data-stu-id="5f57b-445">This error occurs when a module that is designed for Windows PowerShell 2.0 contains at least one mixed-module assembly, that is, an assembly that includes both managed and non-managed code, such as C++ and C#.</span></span>

  <span data-ttu-id="5f57b-446">Чтобы импортировать модуль, содержащий сборки в смешанном режиме, запустите Windows PowerShell 2,0 с помощью следующей команды и повторите `Import-Module` команду.</span><span class="sxs-lookup"><span data-stu-id="5f57b-446">To import a module that contains mixed-mode assemblies, start Windows PowerShell 2.0 by using the following command, and then try the `Import-Module` command again.</span></span>

  `PowerShell.exe -Version 2.0`

- <span data-ttu-id="5f57b-447">Для использования функции сеанса CIM на удаленном компьютере должен быть установлен компонент удаленного взаимодействия WS-Management и инструментарий управления Windows (WMI), который представляет собой реализацию стандарта CIM корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5f57b-447">To use the CIM session feature, the remote computer must have WS-Management remoting and Windows Management Instrumentation (WMI), which is the Microsoft implementation of the Common Information Model (CIM) standard.</span></span> <span data-ttu-id="5f57b-448">На компьютере также должен быть поставщик WMI модуля обнаружения или альтернативный поставщик CIM с теми же основными функциями.</span><span class="sxs-lookup"><span data-stu-id="5f57b-448">The computer must also have the Module Discovery WMI provider or an alternate CIM provider that has the same basic features.</span></span>

  <span data-ttu-id="5f57b-449">Можно использовать сеанс CIM на компьютерах, которые не работают под управлением операционной системы Windows и на компьютерах Windows с PowerShell, но не поддерживают удаленное взаимодействие PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f57b-449">You can use the CIM session feature on computers that aren't running a Windows operating system and on Windows computers that have PowerShell, but don't have PowerShell remoting enabled.</span></span>

  <span data-ttu-id="5f57b-450">Можно также использовать параметры CIM для получения модулей CIM с компьютеров, на которых включено удаленное взаимодействие PowerShell, включая локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="5f57b-450">You can also use the CIM parameters to get CIM modules from computers that have PowerShell remoting enabled, including the local computer.</span></span> <span data-ttu-id="5f57b-451">При создании сеанса CIM на локальном компьютере для создания сеанса в PowerShell используется DCOM, а не WMI.</span><span class="sxs-lookup"><span data-stu-id="5f57b-451">When you create a CIM session on the local computer, PowerShell uses DCOM, instead of WMI, to create the session.</span></span>

- <span data-ttu-id="5f57b-452">По умолчанию `Import-Module` импортирует модули в глобальной области, даже если они вызываются из области видимости потомков.</span><span class="sxs-lookup"><span data-stu-id="5f57b-452">By default, `Import-Module` imports modules in the global scope even when called from a descendant scope.</span></span> <span data-ttu-id="5f57b-453">Область верхнего уровня и все области видимости потомков имеют доступ к экспортированным элементам модуля.</span><span class="sxs-lookup"><span data-stu-id="5f57b-453">The top-level scope and all descendant scopes have access to the module's exported elements.</span></span>

  <span data-ttu-id="5f57b-454">В области видимости потомков `-Scope Local` ограничивает импорт в эту область и все ее дочерние области.</span><span class="sxs-lookup"><span data-stu-id="5f57b-454">In a descendant scope, `-Scope Local` limits the import to that scope and all its descendant scopes.</span></span> <span data-ttu-id="5f57b-455">В родительских областях не отображаются импортированные элементы.</span><span class="sxs-lookup"><span data-stu-id="5f57b-455">Parent scopes then do not see the imported members.</span></span>

  > [!NOTE]
  > <span data-ttu-id="5f57b-456">`Get-Module` показывает все модули, загруженные в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="5f57b-456">`Get-Module` shows all modules loaded in the current session.</span></span> <span data-ttu-id="5f57b-457">Сюда входят модули, загруженные локально в области видимости потомков.</span><span class="sxs-lookup"><span data-stu-id="5f57b-457">This includes modules loaded locally in a descendant scope.</span></span> <span data-ttu-id="5f57b-458">Используйте `Get-Command -Module modulename` , чтобы узнать, какие элементы загружаются в текущей области.</span><span class="sxs-lookup"><span data-stu-id="5f57b-458">Use `Get-Command -Module modulename` to see which members are loaded in the current scope.</span></span>

  <span data-ttu-id="5f57b-459">Если модуль содержит определения классов и перечислений, используйте `using module` в начале скрипта.</span><span class="sxs-lookup"><span data-stu-id="5f57b-459">If the module includes class and enum definitions, use `using module` at the beginning of your script.</span></span> <span data-ttu-id="5f57b-460">При этом импортируются скрипты, включая определения класса и перечисления.</span><span class="sxs-lookup"><span data-stu-id="5f57b-460">This import the scripts, including the class and enum definitions.</span></span> <span data-ttu-id="5f57b-461">Дополнительные сведения см. в разделе [about_Using](About/about_Using.md).</span><span class="sxs-lookup"><span data-stu-id="5f57b-461">For more information, see [about_Using](About/about_Using.md).</span></span>

## <span data-ttu-id="5f57b-462">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="5f57b-462">RELATED LINKS</span></span>

[<span data-ttu-id="5f57b-463">Export-ModuleMember</span><span class="sxs-lookup"><span data-stu-id="5f57b-463">Export-ModuleMember</span></span>](Export-ModuleMember.md)

[<span data-ttu-id="5f57b-464">Get-Module</span><span class="sxs-lookup"><span data-stu-id="5f57b-464">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="5f57b-465">New-Module</span><span class="sxs-lookup"><span data-stu-id="5f57b-465">New-Module</span></span>](New-Module.md)

[<span data-ttu-id="5f57b-466">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="5f57b-466">Remove-Module</span></span>](Remove-Module.md)

[<span data-ttu-id="5f57b-467">about_PowerShell_Editions</span><span class="sxs-lookup"><span data-stu-id="5f57b-467">about_PowerShell_Editions</span></span>](About/about_PowerShell_Editions.md)

