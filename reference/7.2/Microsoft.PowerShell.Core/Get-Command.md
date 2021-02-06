---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/20/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-command?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Command;
ms.openlocfilehash: 1d54082ee313c0e8d4ee7911f89da150aeba9d55
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602286"
---
# <span data-ttu-id="b2dce-102">Get-Command;</span><span class="sxs-lookup"><span data-stu-id="b2dce-102">Get-Command</span></span>

## <span data-ttu-id="b2dce-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b2dce-103">SYNOPSIS</span></span>
<span data-ttu-id="b2dce-104">Получает все команды.</span><span class="sxs-lookup"><span data-stu-id="b2dce-104">Gets all commands.</span></span>

## <span data-ttu-id="b2dce-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b2dce-105">SYNTAX</span></span>

### <span data-ttu-id="b2dce-106">CmdletSet (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="b2dce-106">CmdletSet (Default)</span></span>

```
Get-Command [-Verb <String[]>] [-Noun <String[]>] [-Module <String[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [-TotalCount <Int32>] [-Syntax] [-ShowCommandInfo]
 [[-ArgumentList] <Object[]>] [-All] [-ListImported] [-ParameterName <String[]>]
 [-ParameterType <PSTypeName[]>] [<CommonParameters>]
```

### <span data-ttu-id="b2dce-107">AllCommandSet</span><span class="sxs-lookup"><span data-stu-id="b2dce-107">AllCommandSet</span></span>

```
Get-Command [[-Name] <String[]>] [-Module <String[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [-CommandType <CommandTypes>] [-TotalCount <Int32>]
 [-Syntax] [-ShowCommandInfo] [[-ArgumentList] <Object[]>] [-All] [-ListImported]
 [-ParameterName <String[]>] [-ParameterType <PSTypeName[]>] [-UseFuzzyMatching]
 [-UseAbbreviationExpansion] [<CommonParameters>]
```

## <span data-ttu-id="b2dce-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b2dce-108">DESCRIPTION</span></span>

<span data-ttu-id="b2dce-109">`Get-Command`Командлет получает все команды, установленные на компьютере, включая командлеты, псевдонимы, функции, фильтры, сценарии и приложения.</span><span class="sxs-lookup"><span data-stu-id="b2dce-109">The `Get-Command` cmdlet gets all commands that are installed on the computer, including cmdlets, aliases, functions, filters, scripts, and applications.</span></span> <span data-ttu-id="b2dce-110">`Get-Command` Получает команды из модулей и команд PowerShell, импортированных из других сеансов.</span><span class="sxs-lookup"><span data-stu-id="b2dce-110">`Get-Command` gets the commands from PowerShell modules and commands that were imported from other sessions.</span></span> <span data-ttu-id="b2dce-111">Чтобы получить только те команды, которые были импортированы в текущий сеанс, используйте параметр **ListImported**.</span><span class="sxs-lookup"><span data-stu-id="b2dce-111">To get only commands that have been imported into the current session, use the **ListImported** parameter.</span></span>

<span data-ttu-id="b2dce-112">Без параметров `Get-Command` получает все командлеты, функции и псевдонимы, установленные на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b2dce-112">Without parameters, `Get-Command` gets all of the cmdlets, functions, and aliases installed on the computer.</span></span> <span data-ttu-id="b2dce-113">`Get-Command *` Возвращает все типы команд, включая все файлы, не относящиеся к PowerShell, в переменной среды PATH ( `$env:Path` ), которая отображается в типе команды приложения.</span><span class="sxs-lookup"><span data-stu-id="b2dce-113">`Get-Command *` gets all types of commands, including all of the non-PowerShell files in the Path environment variable (`$env:Path`), which it lists in the Application command type.</span></span>

<span data-ttu-id="b2dce-114">`Get-Command` При этом используется точное имя команды без подстановочных знаков, автоматически импортируется модуль, содержащий команду, чтобы можно было использовать команду немедленно.</span><span class="sxs-lookup"><span data-stu-id="b2dce-114">`Get-Command` that uses the exact name of the command, without wildcard characters, automatically imports the module that contains the command so that you can use the command immediately.</span></span> <span data-ttu-id="b2dce-115">Чтобы включить, отключить и настроить автоматический импорт модулей, используйте `$PSModuleAutoLoadingPreference` переменную предпочтение.</span><span class="sxs-lookup"><span data-stu-id="b2dce-115">To enable, disable, and configure automatic importing of modules, use the `$PSModuleAutoLoadingPreference` preference variable.</span></span> <span data-ttu-id="b2dce-116">Дополнительные сведения см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="b2dce-116">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="b2dce-117">`Get-Command` Получает данные непосредственно из кода команды, в отличие от `Get-Help` , который получает сведения из разделов справки.</span><span class="sxs-lookup"><span data-stu-id="b2dce-117">`Get-Command` gets its data directly from the command code, unlike `Get-Help`, which gets its information from help topics.</span></span>

<span data-ttu-id="b2dce-118">Начиная с Windows PowerShell 5,0, `Get-Command` по умолчанию в результатах командлета отображается столбец **версии** .</span><span class="sxs-lookup"><span data-stu-id="b2dce-118">Starting in Windows PowerShell 5.0, results of the `Get-Command` cmdlet display a **Version** column by default.</span></span> <span data-ttu-id="b2dce-119">В класс **CommandInfo** было добавлено новое свойство **Version** .</span><span class="sxs-lookup"><span data-stu-id="b2dce-119">A new **Version** property has been added to the **CommandInfo** class.</span></span>

## <span data-ttu-id="b2dce-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="b2dce-120">EXAMPLES</span></span>

### <span data-ttu-id="b2dce-121">Пример 1. получение командлетов, функций и псевдонимов</span><span class="sxs-lookup"><span data-stu-id="b2dce-121">Example 1: Get cmdlets, functions, and aliases</span></span>

<span data-ttu-id="b2dce-122">Эта команда возвращает командлеты, функции и псевдонимы PowerShell, установленные на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b2dce-122">This command gets the PowerShell cmdlets, functions, and aliases that are installed on the computer.</span></span>

```powershell
Get-Command
```

### <span data-ttu-id="b2dce-123">Пример 2. получение команд в текущем сеансе</span><span class="sxs-lookup"><span data-stu-id="b2dce-123">Example 2: Get commands in the current session</span></span>

<span data-ttu-id="b2dce-124">Эта команда использует параметр **ListImported**, чтобы получить только команды в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="b2dce-124">This command uses the **ListImported** parameter to get only the commands in the current session.</span></span>

```powershell
Get-Command -ListImported
```

### <span data-ttu-id="b2dce-125">Пример 3. получение командлетов и их отображение по порядку</span><span class="sxs-lookup"><span data-stu-id="b2dce-125">Example 3: Get cmdlets and display them in order</span></span>

<span data-ttu-id="b2dce-126">Эта команда получает все командлеты, сортирует их в алфавитном порядке по существительным в имени командлета, а затем отображает их в группах на базе существительных.</span><span class="sxs-lookup"><span data-stu-id="b2dce-126">This command gets all of the cmdlets, sorts them alphabetically by the noun in the cmdlet name, and then displays them in noun-based groups.</span></span> <span data-ttu-id="b2dce-127">Это помогает найти командлеты для задачи.</span><span class="sxs-lookup"><span data-stu-id="b2dce-127">This display can help you find the cmdlets for a task.</span></span>

```powershell
Get-Command -Type Cmdlet | Sort-Object -Property Noun | Format-Table -GroupBy Noun
```

### <span data-ttu-id="b2dce-128">Пример 4. получение команд в модуле</span><span class="sxs-lookup"><span data-stu-id="b2dce-128">Example 4: Get commands in a module</span></span>

<span data-ttu-id="b2dce-129">Эта команда использует параметр **module** для получения команд в модулях Microsoft. PowerShell. Security и Microsoft. PowerShell. Utility.</span><span class="sxs-lookup"><span data-stu-id="b2dce-129">This command uses the **Module** parameter to get the commands in the Microsoft.PowerShell.Security and Microsoft.PowerShell.Utility modules.</span></span>

```powershell
Get-Command -Module Microsoft.PowerShell.Security, Microsoft.PowerShell.Utility
```

### <span data-ttu-id="b2dce-130">Пример 5. Получение сведений о командлете</span><span class="sxs-lookup"><span data-stu-id="b2dce-130">Example 5: Get information about a cmdlet</span></span>

<span data-ttu-id="b2dce-131">Эта команда возвращает сведения о `Get-AppLockerPolicy` командлете.</span><span class="sxs-lookup"><span data-stu-id="b2dce-131">This command gets information about the `Get-AppLockerPolicy` cmdlet.</span></span> <span data-ttu-id="b2dce-132">Она также импортирует модуль **AppLocker**, который добавляет все команды в модуле **AppLocker** в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="b2dce-132">It also imports the **AppLocker** module, which adds all of the commands in the **AppLocker** module to the current session.</span></span>

```powershell
Get-Command Get-AppLockerPolicy
```

<span data-ttu-id="b2dce-133">Если модуль импортируется автоматически, результат аналогичен результату при использовании командлета Import-Module.</span><span class="sxs-lookup"><span data-stu-id="b2dce-133">When a module is imported automatically, the effect is the same as using the Import-Module cmdlet.</span></span>
<span data-ttu-id="b2dce-134">Модуль может добавить команды, типы и файлы форматирования, а также запустить скрипты в сеансе.</span><span class="sxs-lookup"><span data-stu-id="b2dce-134">The module can add commands, types and formatting files, and run scripts in the session.</span></span> <span data-ttu-id="b2dce-135">Чтобы включить, отключить и настроить автоматический импорт модулей, используйте `$PSModuleAutoLoadingPreference` переменную предпочтение.</span><span class="sxs-lookup"><span data-stu-id="b2dce-135">To enable, disable, and configuration automatic importing of modules, use the `$PSModuleAutoLoadingPreference` preference variable.</span></span> <span data-ttu-id="b2dce-136">Дополнительные сведения см. в разделе [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="b2dce-136">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

### <span data-ttu-id="b2dce-137">Пример 6. получение синтаксиса командлета</span><span class="sxs-lookup"><span data-stu-id="b2dce-137">Example 6: Get the syntax of a cmdlet</span></span>

<span data-ttu-id="b2dce-138">Эта команда использует параметры **ArgumentList** и **синтаксиса** для получения синтаксиса `Get-ChildItem` командлета, когда он используется на диске CERT:.</span><span class="sxs-lookup"><span data-stu-id="b2dce-138">This command uses the **ArgumentList** and **Syntax** parameters to get the syntax of the `Get-ChildItem` cmdlet when it is used in the Cert: drive.</span></span> <span data-ttu-id="b2dce-139">Диск CERT: — это диск PowerShell, который поставщик сертификатов добавляет в сеанс.</span><span class="sxs-lookup"><span data-stu-id="b2dce-139">The Cert: drive is a PowerShell drive that the Certificate Provider adds to the session.</span></span>

```powershell
Get-Command  -Name Get-Childitem -Args Cert: -Syntax
```

<span data-ttu-id="b2dce-140">При сравнении синтаксиса, отображаемого в выходных данных, с синтаксисом, который отображается при пропуске параметра **args** (**ArgumentList**), вы увидите, что **поставщик сертификатов** добавляет динамический параметр **CodeSigningCert** в `Get-ChildItem` командлет.</span><span class="sxs-lookup"><span data-stu-id="b2dce-140">When you compare the syntax displayed in the output with the syntax that is displayed when you omit the **Args** (**ArgumentList**) parameter, you'll see that the **Certificate provider** adds a dynamic parameter, **CodeSigningCert**, to the `Get-ChildItem` cmdlet.</span></span>

<span data-ttu-id="b2dce-141">Дополнительные сведения о поставщике сертификатов см. в разделе [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span><span class="sxs-lookup"><span data-stu-id="b2dce-141">For more information about the Certificate provider, see [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span></span>

### <span data-ttu-id="b2dce-142">Пример 7. получение динамических параметров</span><span class="sxs-lookup"><span data-stu-id="b2dce-142">Example 7: Get dynamic parameters</span></span>

<span data-ttu-id="b2dce-143">Команда в примере использует `Get-DynamicParameters` функцию для получения динамических параметров, которые поставщик сертификатов добавляет к `Get-ChildItem` командлету при его использовании на диске CERT:.</span><span class="sxs-lookup"><span data-stu-id="b2dce-143">The command in the example uses the `Get-DynamicParameters` function to get the dynamic parameters that the Certificate provider adds to the `Get-ChildItem` cmdlet when it is used in the Cert: drive.</span></span>

```powershell
function Get-DynamicParameters
{
    param ($Cmdlet, $PSDrive)
    (Get-Command -Name $Cmdlet -ArgumentList $PSDrive).ParameterSets | ForEach-Object {$_.Parameters} | Where-Object { $_.IsDynamic } | Select-Object -Property Name -Unique
}
Get-DynamicParameters -Cmdlet Get-ChildItem -PSDrive Cert:
```

```Output
Name
----
CodeSigningCert
```

<span data-ttu-id="b2dce-144">`Get-DynamicParameters`Функция в этом примере получает динамические параметры командлета.</span><span class="sxs-lookup"><span data-stu-id="b2dce-144">The `Get-DynamicParameters` function in this example gets the dynamic parameters of a cmdlet.</span></span> <span data-ttu-id="b2dce-145">Это альтернативный метод, использованный в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="b2dce-145">This is an alternative to the method used in the previous example.</span></span> <span data-ttu-id="b2dce-146">Динамический параметр можно добавить в командлет с помощью другого командлета или поставщика.</span><span class="sxs-lookup"><span data-stu-id="b2dce-146">Dynamic parameter can be added to a cmdlet by another cmdlet or a provider.</span></span>

### <span data-ttu-id="b2dce-147">Пример 8. получение всех команд всех типов</span><span class="sxs-lookup"><span data-stu-id="b2dce-147">Example 8: Get all commands of all types</span></span>

<span data-ttu-id="b2dce-148">Эта команда возвращает все команды всех типов на локальном компьютере, включая исполняемые файлы, в пути переменной среды **path** ( `$env:path` ).</span><span class="sxs-lookup"><span data-stu-id="b2dce-148">This command gets all commands of all types on the local computer, including executable files in the paths of the **Path** environment variable (`$env:path`).</span></span>

```powershell
Get-Command *
```

<span data-ttu-id="b2dce-149">Она возвращает для каждого файла объект **ApplicationInfo** (System.Management.Automation.ApplicationInfo), а не объект **FileInfo** (System.IO.FileInfo).</span><span class="sxs-lookup"><span data-stu-id="b2dce-149">It returns an **ApplicationInfo** object (System.Management.Automation.ApplicationInfo) for each file, not a **FileInfo** object (System.IO.FileInfo).</span></span>

### <span data-ttu-id="b2dce-150">Пример 9. получение командлетов с помощью имени и типа параметра</span><span class="sxs-lookup"><span data-stu-id="b2dce-150">Example 9: Get cmdlets by using a parameter name and type</span></span>

<span data-ttu-id="b2dce-151">Эта команда получает командлеты с параметром, имя которого включает проверку подлинности и тип **AuthenticationMechanism**.</span><span class="sxs-lookup"><span data-stu-id="b2dce-151">This command gets cmdlets that have a parameter whose name includes Auth and whose type is **AuthenticationMechanism**.</span></span>

```powershell
Get-Command -ParameterName *Auth* -ParameterType AuthenticationMechanism
```

<span data-ttu-id="b2dce-152">Для поиска командлетов, которые позволяют указать метод, использующийся для проверки подлинности пользователя, можно использовать команду подобным образом.</span><span class="sxs-lookup"><span data-stu-id="b2dce-152">You can use a command like this one to find cmdlets that let you specify the method that is used to authenticate the user.</span></span>

<span data-ttu-id="b2dce-153">Параметр **ParameterType** разделяет параметры, которые получают значение **AuthenticationMechanism** от тех параметров, которые получают параметр **AuthenticationLevel**, даже если они имеют одинаковые имена.</span><span class="sxs-lookup"><span data-stu-id="b2dce-153">The **ParameterType** parameter distinguishes parameters that take an **AuthenticationMechanism** value from those that take an **AuthenticationLevel** parameter, even when they have similar names.</span></span>

### <span data-ttu-id="b2dce-154">Пример 10. получение псевдонима</span><span class="sxs-lookup"><span data-stu-id="b2dce-154">Example 10: Get an alias</span></span>

<span data-ttu-id="b2dce-155">В этом примере показано, как использовать `Get-Command` командлет с псевдонимом.</span><span class="sxs-lookup"><span data-stu-id="b2dce-155">This example shows how to use the `Get-Command` cmdlet with an alias.</span></span>

```powershell
Get-Command Name dir
```

```Output
CommandType     Name                                               ModuleName
-----------     ----                                               ----------
Alias           dir -> Get-ChildItem
```

<span data-ttu-id="b2dce-156">Хотя он обычно используется в командлетах и функциях, `Get-Command` также получает скрипты, функции, псевдонимы и исполняемые файлы.</span><span class="sxs-lookup"><span data-stu-id="b2dce-156">Although it is typically used on cmdlets and functions, `Get-Command` also gets scripts, functions, aliases, and executable files.</span></span>

<span data-ttu-id="b2dce-157">В выходных данных команды показано специальное представление значения свойства **Name** для псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="b2dce-157">The output of the command shows the special view of the **Name** property value for aliases.</span></span> <span data-ttu-id="b2dce-158">В представлении показан псевдоним и полное имя команды.</span><span class="sxs-lookup"><span data-stu-id="b2dce-158">The view shows the alias and the full command name.</span></span>

### <span data-ttu-id="b2dce-159">Пример 11. получение синтаксиса из псевдонима</span><span class="sxs-lookup"><span data-stu-id="b2dce-159">Example 11: Get Syntax from an alias</span></span>

<span data-ttu-id="b2dce-160">В этом примере показано, как получить синтаксис вместе со стандартным именем псевдонима.</span><span class="sxs-lookup"><span data-stu-id="b2dce-160">This example shows how to get the syntax along with the standard name of an alias.</span></span>

<span data-ttu-id="b2dce-161">Выходные данные команды показывают псевдоним со стандартным именем, за которым следует синтаксис.</span><span class="sxs-lookup"><span data-stu-id="b2dce-161">The output of the command shows the labeled alias with the standard name, followed by the syntax.</span></span>

```powershell
Get-Command -Name dir -Syntax
```

```Output
dir (alias) -> Get-ChildItem

dir [[-Path] <string[]>] [[-Filter] <string>] [-Include <string[]>] [-Exclude <string[]>] [-Recurse] [-Depth <uint>] [-Force] [-Name] [-Attributes <FlagsExpression[FileAttributes]>] [-FollowSymlink] [-Directory] [-File] [-Hidden] [-ReadOnly] [-System] [<CommonParameters>]

dir [[-Filter] <string>] -LiteralPath <string[]> [-Include <string[]>] [-Exclude <string[]>] [-Recurse] [-Depth <uint>] [-Force] [-Name] [-Attributes <FlagsExpression[FileAttributes]>] [-FollowSymlink] [-Directory] [-File] [-Hidden] [-ReadOnly] [-System] [<CommonParameters>]
```

### <span data-ttu-id="b2dce-162">Пример 12. получение всех экземпляров команды Notepad</span><span class="sxs-lookup"><span data-stu-id="b2dce-162">Example 12: Get all instances of the Notepad command</span></span>

<span data-ttu-id="b2dce-163">В этом примере используется параметр **ALL** `Get-Command` командлета для отображения всех экземпляров `Notepad` команды на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="b2dce-163">This example uses the **All** parameter of the `Get-Command` cmdlet to show all instances of the `Notepad` command on the local computer.</span></span>

```powershell
Get-Command Notepad -All | Format-Table CommandType, Name, Definition
```

```Output
CommandType     Name           Definition
-----------     ----           ----------
Application     notepad.exe    C:\WINDOWS\system32\notepad.exe
Application     NOTEPAD.EXE    C:\WINDOWS\NOTEPAD.EXE
```

<span data-ttu-id="b2dce-164">Параметр **All** полезен, если в сеансе есть больше одной команды с одинаковым именем.</span><span class="sxs-lookup"><span data-stu-id="b2dce-164">The **All** parameter is useful when there is more than one command with the same name in the session.</span></span>

<span data-ttu-id="b2dce-165">Начиная с Windows PowerShell 3,0, по умолчанию, когда сеанс включает несколько команд с одинаковым именем, `Get-Command` получает только команду, которая выполняется при вводе имени команды.</span><span class="sxs-lookup"><span data-stu-id="b2dce-165">Beginning in Windows PowerShell 3.0, by default, when the session includes multiple commands with the same name, `Get-Command` gets only the command that runs when you type the command name.</span></span> <span data-ttu-id="b2dce-166">При использовании параметра **ALL** `Get-Command` получает все команды с указанным именем и возвращает их в порядке очередности выполнения.</span><span class="sxs-lookup"><span data-stu-id="b2dce-166">With the **All** parameter, `Get-Command` gets all commands with the specified name and returns them in execution precedence order.</span></span> <span data-ttu-id="b2dce-167">Чтобы запустить команду, которая не является первой в списке, введите полный путь к команде.</span><span class="sxs-lookup"><span data-stu-id="b2dce-167">To run a command other than the first one in the list, type the fully qualified path to the command.</span></span>

<span data-ttu-id="b2dce-168">Дополнительные сведения о приоритете команд см. в разделе [about_Command_Precedence](About/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="b2dce-168">For more information about command precedence, see [about_Command_Precedence](About/about_Command_Precedence.md).</span></span>

### <span data-ttu-id="b2dce-169">Пример 13. Получение имени модуля, содержащего командлет</span><span class="sxs-lookup"><span data-stu-id="b2dce-169">Example 13: Get the name of a module that contains a cmdlet</span></span>

<span data-ttu-id="b2dce-170">Эта команда возвращает имя модуля, в котором `Get-Date` был создан командлет.</span><span class="sxs-lookup"><span data-stu-id="b2dce-170">This command gets the name of the module in which the `Get-Date` cmdlet originated.</span></span>
<span data-ttu-id="b2dce-171">Команда использует свойство **ModuleName** всех команд.</span><span class="sxs-lookup"><span data-stu-id="b2dce-171">The command uses the **ModuleName** property of all commands.</span></span>

```powershell
(Get-Command Get-Date).ModuleName
```

```Output
Microsoft.PowerShell.Utility
```

<span data-ttu-id="b2dce-172">Этот формат команды работает с командами в модулях PowerShell, даже если они не импортированы в сеанс.</span><span class="sxs-lookup"><span data-stu-id="b2dce-172">This command format works on commands in PowerShell modules, even if they are not imported into the session.</span></span>

### <span data-ttu-id="b2dce-173">Пример 14. получение командлетов и функций с типом выходных данных</span><span class="sxs-lookup"><span data-stu-id="b2dce-173">Example 14: Get cmdlets and functions that have an output type</span></span>

```powershell
Get-Command -Type Cmdlet | Where-Object OutputType | Format-List -Property Name, OutputType
```

<span data-ttu-id="b2dce-174">Эта команда получает командлеты и функции, содержащие тип выходных данных и тип возвращаемых объектов.</span><span class="sxs-lookup"><span data-stu-id="b2dce-174">This command gets the cmdlets and functions that have an output type and the type of objects that they return.</span></span>

<span data-ttu-id="b2dce-175">Первая часть команды получает все командлеты.</span><span class="sxs-lookup"><span data-stu-id="b2dce-175">The first part of the command gets all cmdlets.</span></span> <span data-ttu-id="b2dce-176">Оператор конвейера ( `|` ) отправляет командлеты `Where-Object` командлету, который выбирает только те, в которых заполнено свойство **OutputType** .</span><span class="sxs-lookup"><span data-stu-id="b2dce-176">A pipeline operator (`|`) sends the cmdlets to the `Where-Object` cmdlet, which selects only the ones in which the **OutputType** property is populated.</span></span> <span data-ttu-id="b2dce-177">Другой конвейерный оператор отправляет выбранные объекты командлета в `Format-List` командлет, который отображает имя и тип выходных данных каждого командлета в списке.</span><span class="sxs-lookup"><span data-stu-id="b2dce-177">Another pipeline operator sends the selected cmdlet objects to the `Format-List` cmdlet, which displays the name and output type of each cmdlet in a list.</span></span>

<span data-ttu-id="b2dce-178">Свойство **OutputType** объекта **CommandInfo** имеет значение, отличное от NULL, только если код командлета определяет для командлета атрибут **OutputType**.</span><span class="sxs-lookup"><span data-stu-id="b2dce-178">The **OutputType** property of a **CommandInfo** object has a non-null value only when the cmdlet code defines the **OutputType** attribute for the cmdlet.</span></span>

### <span data-ttu-id="b2dce-179">Пример 15. получение командлетов, которые принимают в качестве входных данных конкретный тип объекта</span><span class="sxs-lookup"><span data-stu-id="b2dce-179">Example 15: Get cmdlets that take a specific object type as input</span></span>

```powershell
Get-Command -ParameterType (((Get-NetAdapter)[0]).PSTypeNames)
```

```Output
CommandType     Name                                               ModuleName
-----------     ----                                               ----------
Function        Disable-NetAdapter                                 NetAdapter
Function        Enable-NetAdapter                                  NetAdapter
Function        Rename-NetAdapter                                  NetAdapter
Function        Restart-NetAdapter                                 NetAdapter
Function        Set-NetAdapter                                     NetAdapter
```

<span data-ttu-id="b2dce-180">Эта команда находит командлеты, которые получают объекты сетевого адаптера в качестве выходных данных.</span><span class="sxs-lookup"><span data-stu-id="b2dce-180">This command finds cmdlets that take net adapter objects as input.</span></span> <span data-ttu-id="b2dce-181">Этот формат команды можно использовать для поиска командлетов, которые принимают тип объектов, возвращаемый любой командой.</span><span class="sxs-lookup"><span data-stu-id="b2dce-181">You can use this command format to find the cmdlets that accept the type of objects that any command returns.</span></span>

<span data-ttu-id="b2dce-182">Команда использует внутреннее свойство **PSTypeNames** всех объектов, которые получают типы, описывающие объект.</span><span class="sxs-lookup"><span data-stu-id="b2dce-182">The command uses the **PSTypeNames** intrinsic property of all objects, which gets the types that describe the object.</span></span> <span data-ttu-id="b2dce-183">Чтобы получить свойство сетевого адаптера **PSTypeNames**, а не свойство коллекции сетевых адаптеров **PSTypeNames**, команда использует нотацию массива, чтобы получить первый сетевой адаптер, который возвращает командлет.</span><span class="sxs-lookup"><span data-stu-id="b2dce-183">To get the **PSTypeNames** property of a net adapter, and not the **PSTypeNames** property of a collection of net adapters, the command uses array notation to get the first net adapter that the cmdlet returns.</span></span>

### <span data-ttu-id="b2dce-184">Пример 16. получение команд с помощью нечеткого соответствия</span><span class="sxs-lookup"><span data-stu-id="b2dce-184">Example 16: Get commands using a fuzzy match</span></span>

<span data-ttu-id="b2dce-185">В этом примере имя команды намеренно имеет опечатку "Get-коммнд".</span><span class="sxs-lookup"><span data-stu-id="b2dce-185">In this example, the name of the command deliberately has a typo as 'get-commnd'.</span></span>
<span data-ttu-id="b2dce-186">С помощью `-UseFuzzyMatching` параметра командлет определил, что в системе с наиболее подходящей соответствием `Get-Command` следуют другие машинные команды, которые были аналогичными.</span><span class="sxs-lookup"><span data-stu-id="b2dce-186">Using the `-UseFuzzyMatching` switch, the cmdlet determined that the best match was `Get-Command` followed by other native commands on the system that were a similar match.</span></span>

```powershell
Get-Command get-commnd -UseFuzzyMatching
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Get-Command                                        6.2.0.0    Microsoft.PowerShell.Core
Application     getconf                                            0.0.0.0    /usr/bin/getconf
Application     command                                            0.0.0.0    /usr/bin/command
```

## <span data-ttu-id="b2dce-187">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b2dce-187">PARAMETERS</span></span>

### <span data-ttu-id="b2dce-188">-All</span><span class="sxs-lookup"><span data-stu-id="b2dce-188">-All</span></span>

<span data-ttu-id="b2dce-189">Указывает, что этот командлет получает все команды, включая команды того же типа с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="b2dce-189">Indicates that this cmdlet gets all commands, including commands of the same type that have the same name.</span></span> <span data-ttu-id="b2dce-190">По умолчанию `Get-Command` получает только команды, которые выполняются при вводе имени команды.</span><span class="sxs-lookup"><span data-stu-id="b2dce-190">By default, `Get-Command` gets only the commands that run when you type the command name.</span></span>

<span data-ttu-id="b2dce-191">Дополнительные сведения о методе, используемом PowerShell для выбора команды, которая будет выполняться, если несколько команд имеют одинаковые имена, см. в разделе [about_Command_Precedence](About/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="b2dce-191">For more information about the method that PowerShell uses to select the command to run when multiple commands have the same name, see [about_Command_Precedence](About/about_Command_Precedence.md).</span></span>
<span data-ttu-id="b2dce-192">Сведения об именах команд с указанием модуля и выполнении команд, которые не выполняются по умолчанию из-за конфликта имен, см. в разделе [about_Modules](About/about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="b2dce-192">For information about module-qualified command names and running commands that do not run by default because of a name conflict, see [about_Modules](About/about_Modules.md).</span></span>

<span data-ttu-id="b2dce-193">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="b2dce-193">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="b2dce-194">В Windows PowerShell 2,0 `Get-Command` по умолчанию получает все команды.</span><span class="sxs-lookup"><span data-stu-id="b2dce-194">In Windows PowerShell 2.0, `Get-Command` gets all commands by default.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b2dce-195">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="b2dce-195">-ArgumentList</span></span>

<span data-ttu-id="b2dce-196">Задает массив аргументов.</span><span class="sxs-lookup"><span data-stu-id="b2dce-196">Specifies an array of arguments.</span></span> <span data-ttu-id="b2dce-197">Этот командлет получает сведения о командлете или функции при их использовании с указанными параметрами ("arguments").</span><span class="sxs-lookup"><span data-stu-id="b2dce-197">This cmdlet gets information about a cmdlet or function when it is used with the specified parameters ("arguments").</span></span> <span data-ttu-id="b2dce-198">Псевдоним для **ArgumentList** — **Args**.</span><span class="sxs-lookup"><span data-stu-id="b2dce-198">The alias for **ArgumentList** is **Args**.</span></span>

<span data-ttu-id="b2dce-199">Чтобы обнаружить динамические параметры, доступные только при использовании некоторых других параметров, задайте для параметра **ArgumentList** значение, которое вызывает динамические параметры.</span><span class="sxs-lookup"><span data-stu-id="b2dce-199">To detect dynamic parameters that are available only when certain other parameters are used, set the value of **ArgumentList** to the parameters that trigger the dynamic parameters.</span></span>

<span data-ttu-id="b2dce-200">Чтобы определить динамические параметры, которые поставщик добавляет к командлету, присвойте параметру **ArgumentList** путь на диске поставщика, например WSMan:, HKLM: или CERT:.</span><span class="sxs-lookup"><span data-stu-id="b2dce-200">To detect the dynamic parameters that a provider adds to a cmdlet, set the value of the **ArgumentList** parameter to a path in the provider drive, such as WSMan:, HKLM:, or Cert:.</span></span> <span data-ttu-id="b2dce-201">Если команда является командлетом поставщика PowerShell, введите в каждой команде только один путь.</span><span class="sxs-lookup"><span data-stu-id="b2dce-201">When the command is a PowerShell provider cmdlet, enter only one path in each command.</span></span> <span data-ttu-id="b2dce-202">Командлеты поставщика возвращают только динамические параметры для первого пути в значении **ArgumentList**.</span><span class="sxs-lookup"><span data-stu-id="b2dce-202">The provider cmdlets return only the dynamic parameters for the first path the value of **ArgumentList**.</span></span> <span data-ttu-id="b2dce-203">Дополнительные сведения о командлетах поставщика см. в разделе [about_Providers](About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="b2dce-203">For information about the provider cmdlets, see [about_Providers](About/about_Providers.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b2dce-204">-CommandType</span><span class="sxs-lookup"><span data-stu-id="b2dce-204">-CommandType</span></span>

<span data-ttu-id="b2dce-205">Указывает типы команд, которые получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="b2dce-205">Specifies the types of commands that this cmdlet gets.</span></span> <span data-ttu-id="b2dce-206">Введите один или несколько типов команд.</span><span class="sxs-lookup"><span data-stu-id="b2dce-206">Enter one or more command types.</span></span> <span data-ttu-id="b2dce-207">Используйте параметр **CommandType** или его псевдоним **Type**.</span><span class="sxs-lookup"><span data-stu-id="b2dce-207">Use **CommandType** or its alias, **Type**.</span></span> <span data-ttu-id="b2dce-208">По умолчанию `Get-Command` получает все командлеты, функции и псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="b2dce-208">By default, `Get-Command` gets all cmdlets, functions, and aliases.</span></span>

<span data-ttu-id="b2dce-209">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="b2dce-209">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="b2dce-210">Псевдоним.</span><span class="sxs-lookup"><span data-stu-id="b2dce-210">Alias.</span></span> <span data-ttu-id="b2dce-211">Возвращает псевдонимы всех команд PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b2dce-211">Gets the aliases of all PowerShell commands.</span></span> <span data-ttu-id="b2dce-212">Дополнительные сведения см. в разделе [about_Aliases](About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="b2dce-212">For more information, see [about_Aliases](About/about_Aliases.md).</span></span>
- <span data-ttu-id="b2dce-213">Все.</span><span class="sxs-lookup"><span data-stu-id="b2dce-213">All.</span></span> <span data-ttu-id="b2dce-214">Получает все типы команд.</span><span class="sxs-lookup"><span data-stu-id="b2dce-214">Gets all command types.</span></span> <span data-ttu-id="b2dce-215">Значение этого параметра эквивалентно значению `Get-Command *` .</span><span class="sxs-lookup"><span data-stu-id="b2dce-215">This parameter value is the equivalent of `Get-Command *`.</span></span>
- <span data-ttu-id="b2dce-216">приложение.</span><span class="sxs-lookup"><span data-stu-id="b2dce-216">Application.</span></span> <span data-ttu-id="b2dce-217">Возвращает файлы, не относящиеся к PowerShell, в путях, указанных в переменной среды **path** ($env:p ь), включая txt, exe и DLL-файлы.</span><span class="sxs-lookup"><span data-stu-id="b2dce-217">Gets non-PowerShell files in paths listed in the **Path** environment variable ($env:path), including .txt, .exe, and .dll files.</span></span> <span data-ttu-id="b2dce-218">Дополнительные сведения о переменной среды **Path** см. в разделе about_Environment_Variables.</span><span class="sxs-lookup"><span data-stu-id="b2dce-218">For more information about the **Path** environment variable, see about_Environment_Variables.</span></span>
- <span data-ttu-id="b2dce-219">Командлет.</span><span class="sxs-lookup"><span data-stu-id="b2dce-219">Cmdlet.</span></span> <span data-ttu-id="b2dce-220">Получает все командлеты.</span><span class="sxs-lookup"><span data-stu-id="b2dce-220">Gets all cmdlets.</span></span>
- <span data-ttu-id="b2dce-221">Екстерналскрипт.</span><span class="sxs-lookup"><span data-stu-id="b2dce-221">ExternalScript.</span></span> <span data-ttu-id="b2dce-222">Получает все PS1-файлы в путях, указанных в переменной среды **Path** ($env:path).</span><span class="sxs-lookup"><span data-stu-id="b2dce-222">Gets all .ps1 files in the paths listed in the **Path** environment variable ($env:path).</span></span>
- <span data-ttu-id="b2dce-223">Фильтр и функция.</span><span class="sxs-lookup"><span data-stu-id="b2dce-223">Filter and Function.</span></span> <span data-ttu-id="b2dce-224">Возвращает все расширенные и простые функции и фильтры PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b2dce-224">Gets all PowerShell advanced and simple functions and filters.</span></span>
- <span data-ttu-id="b2dce-225">Скрипт.</span><span class="sxs-lookup"><span data-stu-id="b2dce-225">Script.</span></span> <span data-ttu-id="b2dce-226">Получает все блоки скриптов.</span><span class="sxs-lookup"><span data-stu-id="b2dce-226">Gets all script blocks.</span></span> <span data-ttu-id="b2dce-227">Чтобы получить скрипты PowerShell (PS1-файлы), используйте значение Екстерналскрипт.</span><span class="sxs-lookup"><span data-stu-id="b2dce-227">To get PowerShell scripts (.ps1 files), use the ExternalScript value.</span></span>

```yaml
Type: System.Management.Automation.CommandTypes
Parameter Sets: AllCommandSet
Aliases: Type
Accepted values: Alias, Function, Filter, Cmdlet, ExternalScript, Application, Script, Workflow, Configuration, All

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b2dce-228">-FullyQualifiedModule</span><span class="sxs-lookup"><span data-stu-id="b2dce-228">-FullyQualifiedModule</span></span>

<span data-ttu-id="b2dce-229">Указывает модули с именами, указанными в форме объектов **ModuleSpecification** , описанной в разделе **"Примечания"** [конструктора ModuleSpecification (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span><span class="sxs-lookup"><span data-stu-id="b2dce-229">Specifies modules with names that are specified in the form of **ModuleSpecification** objects, described in the **Remarks** section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>
<span data-ttu-id="b2dce-230">Например, параметр **FullyQualifiedModule** принимает имя модуля, указанное в одном из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="b2dce-230">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in one of the following formats:</span></span>

- `@{ModuleName = "modulename"; ModuleVersion = "version_number"}`
- `@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

<span data-ttu-id="b2dce-231">Параметры **ModuleName** и **ModuleVersion** обязательны, а **Guid** — нет.</span><span class="sxs-lookup"><span data-stu-id="b2dce-231">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span>

<span data-ttu-id="b2dce-232">Нельзя указать параметр **FullyQualifiedModule** в той же команде, что и параметр **module** .</span><span class="sxs-lookup"><span data-stu-id="b2dce-232">You cannot specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span> <span data-ttu-id="b2dce-233">Два параметра являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="b2dce-233">The two parameters are mutually exclusive.</span></span>

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

### <span data-ttu-id="b2dce-234">-ListImported</span><span class="sxs-lookup"><span data-stu-id="b2dce-234">-ListImported</span></span>

<span data-ttu-id="b2dce-235">Указывает, что этот командлет получает только команды в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="b2dce-235">Indicates that this cmdlet gets only commands in the current session.</span></span>

<span data-ttu-id="b2dce-236">Начиная с PowerShell 3,0, по умолчанию `Get-Command` получает все установленные команды, включая, но не ограниченные, команды в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="b2dce-236">Starting in PowerShell 3.0, by default, `Get-Command` gets all installed commands, including, but not limited to, the commands in the current session.</span></span> <span data-ttu-id="b2dce-237">В PowerShell 2,0 он возвращает только команды в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="b2dce-237">In PowerShell 2.0, it gets only commands in the current session.</span></span>

<span data-ttu-id="b2dce-238">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="b2dce-238">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b2dce-239">-Module</span><span class="sxs-lookup"><span data-stu-id="b2dce-239">-Module</span></span>

<span data-ttu-id="b2dce-240">Указывает массив модулей.</span><span class="sxs-lookup"><span data-stu-id="b2dce-240">Specifies an array of modules.</span></span> <span data-ttu-id="b2dce-241">Этот командлет получает команды, поступившие из указанных модулей.</span><span class="sxs-lookup"><span data-stu-id="b2dce-241">This cmdlet gets the commands that came from the specified modules.</span></span>
<span data-ttu-id="b2dce-242">Введите имена модулей или объектов модуля.</span><span class="sxs-lookup"><span data-stu-id="b2dce-242">Enter the names of modules or module objects.</span></span>

<span data-ttu-id="b2dce-243">Этот параметр принимает строковые значения, но значение этого параметра также может быть объектом **PSModuleInfo** , таким как объекты, `Get-Module` `Import-PSSession` возвращаемые командлетами и.</span><span class="sxs-lookup"><span data-stu-id="b2dce-243">This parameter takes string values, but the value of this parameter can also be a **PSModuleInfo** object, such as the objects that the `Get-Module` and `Import-PSSession` cmdlets return.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSSnapin

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="b2dce-244">-Name</span><span class="sxs-lookup"><span data-stu-id="b2dce-244">-Name</span></span>

<span data-ttu-id="b2dce-245">Задает массив имен.</span><span class="sxs-lookup"><span data-stu-id="b2dce-245">Specifies an array of names.</span></span> <span data-ttu-id="b2dce-246">Этот командлет возвращает только команды с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="b2dce-246">This cmdlet gets only commands that have the specified name.</span></span> <span data-ttu-id="b2dce-247">Введите имя или шаблон имени.</span><span class="sxs-lookup"><span data-stu-id="b2dce-247">Enter a name or name pattern.</span></span> <span data-ttu-id="b2dce-248">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b2dce-248">Wildcard characters are permitted.</span></span>

<span data-ttu-id="b2dce-249">Чтобы получить команды с одинаковым именем, используйте параметр **All**.</span><span class="sxs-lookup"><span data-stu-id="b2dce-249">To get commands that have the same name, use the **All** parameter.</span></span> <span data-ttu-id="b2dce-250">Если две команды имеют одинаковое имя, по умолчанию `Get-Command` получает команду, которая выполняется при вводе имени команды.</span><span class="sxs-lookup"><span data-stu-id="b2dce-250">When two commands have the same name, by default, `Get-Command` gets the command that runs when you type the command name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: AllCommandSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="b2dce-251">-Noun</span><span class="sxs-lookup"><span data-stu-id="b2dce-251">-Noun</span></span>

<span data-ttu-id="b2dce-252">Указывает массив существительных команд.</span><span class="sxs-lookup"><span data-stu-id="b2dce-252">Specifies an array of command nouns.</span></span> <span data-ttu-id="b2dce-253">Этот командлет возвращает команды, которые включают командлеты, функции и псевдонимы, имена которых содержат указанное существительное.</span><span class="sxs-lookup"><span data-stu-id="b2dce-253">This cmdlet gets commands, which include cmdlets, functions, and aliases, that have names that include the specified noun.</span></span> <span data-ttu-id="b2dce-254">Введите одно или несколько существительных или шаблонов существительных.</span><span class="sxs-lookup"><span data-stu-id="b2dce-254">Enter one or more nouns or noun patterns.</span></span> <span data-ttu-id="b2dce-255">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b2dce-255">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: CmdletSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="b2dce-256">-ParameterName</span><span class="sxs-lookup"><span data-stu-id="b2dce-256">-ParameterName</span></span>

<span data-ttu-id="b2dce-257">Указывает массив имен параметров.</span><span class="sxs-lookup"><span data-stu-id="b2dce-257">Specifies an array of parameter names.</span></span> <span data-ttu-id="b2dce-258">Этот командлет возвращает команды в сеансе с указанными параметрами.</span><span class="sxs-lookup"><span data-stu-id="b2dce-258">This cmdlet gets commands in the session that have the specified parameters.</span></span> <span data-ttu-id="b2dce-259">Введите имена параметров или псевдонимы параметров.</span><span class="sxs-lookup"><span data-stu-id="b2dce-259">Enter parameter names or parameter aliases.</span></span> <span data-ttu-id="b2dce-260">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b2dce-260">Wildcard characters are supported.</span></span>

<span data-ttu-id="b2dce-261">Параметры **ParameterName** и **ParameterType** ищут только команды в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="b2dce-261">The **ParameterName** and **ParameterType** parameters search only commands in the current session.</span></span>

<span data-ttu-id="b2dce-262">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="b2dce-262">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="b2dce-263">-ParameterType</span><span class="sxs-lookup"><span data-stu-id="b2dce-263">-ParameterType</span></span>

<span data-ttu-id="b2dce-264">Указывает массив имен параметров.</span><span class="sxs-lookup"><span data-stu-id="b2dce-264">Specifies an array of parameter names.</span></span> <span data-ttu-id="b2dce-265">Этот командлет возвращает команды в сеансе, которые имеют параметры указанного типа.</span><span class="sxs-lookup"><span data-stu-id="b2dce-265">This cmdlet gets commands in the session that have parameters of the specified type.</span></span> <span data-ttu-id="b2dce-266">Введите полное имя или частичное имя типа параметра.</span><span class="sxs-lookup"><span data-stu-id="b2dce-266">Enter the full name or partial name of a parameter type.</span></span> <span data-ttu-id="b2dce-267">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b2dce-267">Wildcard characters are supported.</span></span>

<span data-ttu-id="b2dce-268">Параметры **ParameterName** и **ParameterType** ищут только команды в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="b2dce-268">The **ParameterName** and **ParameterType** parameters search only commands in the current session.</span></span>

<span data-ttu-id="b2dce-269">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="b2dce-269">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSTypeName[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="b2dce-270">-ShowCommandInfo</span><span class="sxs-lookup"><span data-stu-id="b2dce-270">-ShowCommandInfo</span></span>

<span data-ttu-id="b2dce-271">Указывает, что этот командлет отображает сведения о команде.</span><span class="sxs-lookup"><span data-stu-id="b2dce-271">Indicates that this cmdlet displays command information.</span></span>

<span data-ttu-id="b2dce-272">Этот параметр появился в Windows PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="b2dce-272">This parameter was introduced in Windows PowerShell 5.0.</span></span>

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

### <span data-ttu-id="b2dce-273">-Syntax</span><span class="sxs-lookup"><span data-stu-id="b2dce-273">-Syntax</span></span>

<span data-ttu-id="b2dce-274">Указывает, что этот командлет получает только следующие указанные данные о команде:</span><span class="sxs-lookup"><span data-stu-id="b2dce-274">Indicates that this cmdlet gets only the following specified data about the command:</span></span>

- <span data-ttu-id="b2dce-275">Псевдоним.</span><span class="sxs-lookup"><span data-stu-id="b2dce-275">Aliases.</span></span> <span data-ttu-id="b2dce-276">Возвращает стандартное имя и синтаксис.</span><span class="sxs-lookup"><span data-stu-id="b2dce-276">Gets the standard name and syntax.</span></span>
- <span data-ttu-id="b2dce-277">Образующих.</span><span class="sxs-lookup"><span data-stu-id="b2dce-277">Cmdlets.</span></span> <span data-ttu-id="b2dce-278">Возвращает синтаксис.</span><span class="sxs-lookup"><span data-stu-id="b2dce-278">Gets the syntax.</span></span>
- <span data-ttu-id="b2dce-279">Функции и фильтры.</span><span class="sxs-lookup"><span data-stu-id="b2dce-279">Functions and filters.</span></span> <span data-ttu-id="b2dce-280">Возвращает определение функции.</span><span class="sxs-lookup"><span data-stu-id="b2dce-280">Gets the function definition.</span></span>
- <span data-ttu-id="b2dce-281">Скрипты и приложения или файлы.</span><span class="sxs-lookup"><span data-stu-id="b2dce-281">Scripts and applications or files.</span></span> <span data-ttu-id="b2dce-282">Возвращает путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="b2dce-282">Gets the path and filename.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b2dce-283">-TotalCount</span><span class="sxs-lookup"><span data-stu-id="b2dce-283">-TotalCount</span></span>

<span data-ttu-id="b2dce-284">Указывает количество команд для получения.</span><span class="sxs-lookup"><span data-stu-id="b2dce-284">Specifies the number of commands to get.</span></span> <span data-ttu-id="b2dce-285">Этот параметр можно использовать, чтобы ограничить выходные данные команды.</span><span class="sxs-lookup"><span data-stu-id="b2dce-285">You can use this parameter to limit the output of a command.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b2dce-286">-Усеаббревиатионекспансион</span><span class="sxs-lookup"><span data-stu-id="b2dce-286">-UseAbbreviationExpansion</span></span>

<span data-ttu-id="b2dce-287">Указывает использование сопоставления символов в команде для поиска символов в верхнем регистре в команде.</span><span class="sxs-lookup"><span data-stu-id="b2dce-287">Indicates using matching of the characters in the command to find with uppercase characters in a command.</span></span> <span data-ttu-id="b2dce-288">Например, `i-psdf` будет соответствовать, `Import-PowerShellDataFile` как каждый из искомых символов соответствует символу верхнего регистра в результате.</span><span class="sxs-lookup"><span data-stu-id="b2dce-288">For example, `i-psdf` would match `Import-PowerShellDataFile` as each of the characters to find matches an uppercase character in the result.</span></span> <span data-ttu-id="b2dce-289">При использовании такого типа соответствия любые подстановочные знаки не будут иметь соответствий.</span><span class="sxs-lookup"><span data-stu-id="b2dce-289">When using this type of match, any wildcards will result in no matches.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AllCommandSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b2dce-290">-Усефуззиматчинг</span><span class="sxs-lookup"><span data-stu-id="b2dce-290">-UseFuzzyMatching</span></span>

<span data-ttu-id="b2dce-291">Указывает использование алгоритма нечеткого сопоставления при поиске команд.</span><span class="sxs-lookup"><span data-stu-id="b2dce-291">Indicates using a fuzzy matching algorithm when finding commands.</span></span> <span data-ttu-id="b2dce-292">Порядок выходных данных находится в порядке приближения к наиболее вероятным совпадениям.</span><span class="sxs-lookup"><span data-stu-id="b2dce-292">The order of the output is from closest match to least likely match.</span></span> <span data-ttu-id="b2dce-293">Подстановочные знаки не следует использовать с нечетким соответствием, так как они будут пытаться сопоставлять команды, которые могут содержать эти подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b2dce-293">Wildcards should not be used with fuzzy matching as it will attempt to match commands that may contain those wildcard characters.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AllCommandSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b2dce-294">-Verb</span><span class="sxs-lookup"><span data-stu-id="b2dce-294">-Verb</span></span>

<span data-ttu-id="b2dce-295">Задает массив команд.</span><span class="sxs-lookup"><span data-stu-id="b2dce-295">Specifies an array of command verbs.</span></span> <span data-ttu-id="b2dce-296">Этот командлет возвращает команды, которые включают командлеты, функции и псевдонимы, имеющие имена, включающие указанную команду.</span><span class="sxs-lookup"><span data-stu-id="b2dce-296">This cmdlet gets commands, which include cmdlets, functions, and aliases, that have names that include the specified verb.</span></span> <span data-ttu-id="b2dce-297">Введите один или несколько глаголов или шаблонов глаголов.</span><span class="sxs-lookup"><span data-stu-id="b2dce-297">Enter one or more verbs or verb patterns.</span></span> <span data-ttu-id="b2dce-298">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b2dce-298">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: CmdletSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="b2dce-299">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b2dce-299">CommonParameters</span></span>

<span data-ttu-id="b2dce-300">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b2dce-300">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b2dce-301">См. сведения в разделе [about_CommonParameters](About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="b2dce-301">For more information, see [about_CommonParameters](About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="b2dce-302">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b2dce-302">INPUTS</span></span>

### <span data-ttu-id="b2dce-303">System.String</span><span class="sxs-lookup"><span data-stu-id="b2dce-303">System.String</span></span>

<span data-ttu-id="b2dce-304">В этот командлет можно передать имена команд по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="b2dce-304">You can pipe command names to this cmdlet.</span></span>

## <span data-ttu-id="b2dce-305">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b2dce-305">OUTPUTS</span></span>

### <span data-ttu-id="b2dce-306">System.Management.Automation.CommandInfo</span><span class="sxs-lookup"><span data-stu-id="b2dce-306">System.Management.Automation.CommandInfo</span></span>

<span data-ttu-id="b2dce-307">Этот командлет возвращает объекты, производные от класса **CommandInfo** .</span><span class="sxs-lookup"><span data-stu-id="b2dce-307">This cmdlet returns objects derived from the **CommandInfo** class.</span></span> <span data-ttu-id="b2dce-308">Тип возвращаемого объекта зависит от типа команды, которая `Get-Command` получает.</span><span class="sxs-lookup"><span data-stu-id="b2dce-308">The type of object that is returned depends on the type of command that `Get-Command` gets.</span></span>

### <span data-ttu-id="b2dce-309">System.Management.Automation.AliasInfo</span><span class="sxs-lookup"><span data-stu-id="b2dce-309">System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="b2dce-310">Представляет псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="b2dce-310">Represents aliases.</span></span>

### <span data-ttu-id="b2dce-311">System.Management.Automation.ApplicationInfo</span><span class="sxs-lookup"><span data-stu-id="b2dce-311">System.Management.Automation.ApplicationInfo</span></span>

<span data-ttu-id="b2dce-312">Представляет приложения и файлы.</span><span class="sxs-lookup"><span data-stu-id="b2dce-312">Represents applications and files.</span></span>

### <span data-ttu-id="b2dce-313">System.Management.Automation.CmdletInfo</span><span class="sxs-lookup"><span data-stu-id="b2dce-313">System.Management.Automation.CmdletInfo</span></span>

<span data-ttu-id="b2dce-314">Представляет командлеты.</span><span class="sxs-lookup"><span data-stu-id="b2dce-314">Represents cmdlets.</span></span>

### <span data-ttu-id="b2dce-315">System.Management.Automation.FunctionInfo</span><span class="sxs-lookup"><span data-stu-id="b2dce-315">System.Management.Automation.FunctionInfo</span></span>

<span data-ttu-id="b2dce-316">Представляет функции и фильтры.</span><span class="sxs-lookup"><span data-stu-id="b2dce-316">Represents functions and filters.</span></span>

## <span data-ttu-id="b2dce-317">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b2dce-317">NOTES</span></span>

* <span data-ttu-id="b2dce-318">Если в сеансе доступно более одной команды с одним и тем же именем, `Get-Command` Возвращает команду, которая выполняется при вводе имени команды.</span><span class="sxs-lookup"><span data-stu-id="b2dce-318">When more than one command that has the same name is available to the session, `Get-Command` returns the command that runs when you type the command name.</span></span> <span data-ttu-id="b2dce-319">Для получения команд с одинаковыми именами, перечисленными в списке порядок выполнения, используйте параметр **ALL** .</span><span class="sxs-lookup"><span data-stu-id="b2dce-319">To get commands that have the same name, listed in run order, use the **All** parameter.</span></span> <span data-ttu-id="b2dce-320">Дополнительные сведения см. в разделе [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="b2dce-320">For more information, see [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md).</span></span>
* <span data-ttu-id="b2dce-321">При автоматическом импорте модуля этот результат будет таким же, как и при использовании `Import-Module` командлета.</span><span class="sxs-lookup"><span data-stu-id="b2dce-321">When a module is imported automatically, the effect is the same as using the `Import-Module` cmdlet.</span></span> <span data-ttu-id="b2dce-322">Модуль может добавить команды, типы и файлы форматирования, а также запустить скрипты в сеансе.</span><span class="sxs-lookup"><span data-stu-id="b2dce-322">The module can add commands, types and formatting files, and run scripts in the session.</span></span>
  <span data-ttu-id="b2dce-323">Чтобы включить, отключить и настроить автоматический импорт модулей, используйте `$PSModuleAutoLoadingPreference` переменную предпочтение.</span><span class="sxs-lookup"><span data-stu-id="b2dce-323">To enable, disable, and configuration automatic importing of modules, use the `$PSModuleAutoLoadingPreference` preference variable.</span></span> <span data-ttu-id="b2dce-324">Дополнительные сведения см. в разделе [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="b2dce-324">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

## <span data-ttu-id="b2dce-325">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b2dce-325">RELATED LINKS</span></span>

[<span data-ttu-id="b2dce-326">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="b2dce-326">Export-PSSession</span></span>](../Microsoft.PowerShell.Utility/Export-PSSession.md)

[<span data-ttu-id="b2dce-327">Get-Help</span><span class="sxs-lookup"><span data-stu-id="b2dce-327">Get-Help</span></span>](Get-Help.md)

[<span data-ttu-id="b2dce-328">Get-Member</span><span class="sxs-lookup"><span data-stu-id="b2dce-328">Get-Member</span></span>](../Microsoft.PowerShell.Utility/Get-Member.md)

[<span data-ttu-id="b2dce-329">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="b2dce-329">Get-PSDrive</span></span>](../Microsoft.PowerShell.Management/Get-PSDrive.md)

[<span data-ttu-id="b2dce-330">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="b2dce-330">Import-PSSession</span></span>](../Microsoft.PowerShell.Utility/Import-PSSession.md)

[<span data-ttu-id="b2dce-331">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="b2dce-331">about_Command_Precedence</span></span>](About/about_Command_Precedence.md)

