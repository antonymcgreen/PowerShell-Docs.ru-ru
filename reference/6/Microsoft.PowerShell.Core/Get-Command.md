---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 12/14/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-command?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Command;
ms.openlocfilehash: 5e76a15e8f2dcacc7f973cbc46d057bb92c3ad41
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229282"
---
# <span data-ttu-id="a6b30-103">Get-Command;</span><span class="sxs-lookup"><span data-stu-id="a6b30-103">Get-Command</span></span>

## <span data-ttu-id="a6b30-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a6b30-104">SYNOPSIS</span></span>
<span data-ttu-id="a6b30-105">Получает все команды.</span><span class="sxs-lookup"><span data-stu-id="a6b30-105">Gets all commands.</span></span>

## <span data-ttu-id="a6b30-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a6b30-106">SYNTAX</span></span>

### <span data-ttu-id="a6b30-107">CmdletSet (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="a6b30-107">CmdletSet (Default)</span></span>

```
Get-Command [-Verb <String[]>] [-Noun <String[]>] [-Module <String[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [-TotalCount <Int32>] [-Syntax] [-ShowCommandInfo]
 [[-ArgumentList] <Object[]>] [-All] [-ListImported] [-ParameterName <String[]>]
 [-ParameterType <PSTypeName[]>] [<CommonParameters>]
```

### <span data-ttu-id="a6b30-108">AllCommandSet</span><span class="sxs-lookup"><span data-stu-id="a6b30-108">AllCommandSet</span></span>

```
Get-Command [[-Name] <String[]>] [-Module <String[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [-CommandType <CommandTypes>] [-TotalCount <Int32>]
 [-Syntax] [-ShowCommandInfo] [[-ArgumentList] <Object[]>] [-All] [-ListImported]
 [-ParameterName <String[]>] [-ParameterType <PSTypeName[]>] [-UseFuzzyMatching]
 [<CommonParameters>]
```

## <span data-ttu-id="a6b30-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a6b30-109">DESCRIPTION</span></span>

<span data-ttu-id="a6b30-110">`Get-Command`Командлет получает все команды, установленные на компьютере, включая командлеты, псевдонимы, функции, фильтры, сценарии и приложения.</span><span class="sxs-lookup"><span data-stu-id="a6b30-110">The `Get-Command` cmdlet gets all commands that are installed on the computer, including cmdlets, aliases, functions, filters, scripts, and applications.</span></span> <span data-ttu-id="a6b30-111">`Get-Command` Получает команды из модулей и команд PowerShell, импортированных из других сеансов.</span><span class="sxs-lookup"><span data-stu-id="a6b30-111">`Get-Command` gets the commands from PowerShell modules and commands that were imported from other sessions.</span></span> <span data-ttu-id="a6b30-112">Чтобы получить только те команды, которые были импортированы в текущий сеанс, используйте параметр **ListImported**.</span><span class="sxs-lookup"><span data-stu-id="a6b30-112">To get only commands that have been imported into the current session, use the **ListImported** parameter.</span></span>

<span data-ttu-id="a6b30-113">Без параметров `Get-Command` получает все командлеты, функции и псевдонимы, установленные на компьютере.</span><span class="sxs-lookup"><span data-stu-id="a6b30-113">Without parameters, `Get-Command` gets all of the cmdlets, functions, and aliases installed on the computer.</span></span> <span data-ttu-id="a6b30-114">`Get-Command *` Возвращает все типы команд, включая все файлы, не относящиеся к PowerShell, в переменной среды PATH ( `$env:Path` ), которая отображается в типе команды приложения.</span><span class="sxs-lookup"><span data-stu-id="a6b30-114">`Get-Command *` gets all types of commands, including all of the non-PowerShell files in the Path environment variable (`$env:Path`), which it lists in the Application command type.</span></span>

<span data-ttu-id="a6b30-115">`Get-Command` При этом используется точное имя команды без подстановочных знаков, автоматически импортируется модуль, содержащий команду, чтобы можно было использовать команду немедленно.</span><span class="sxs-lookup"><span data-stu-id="a6b30-115">`Get-Command` that uses the exact name of the command, without wildcard characters, automatically imports the module that contains the command so that you can use the command immediately.</span></span> <span data-ttu-id="a6b30-116">Чтобы включить, отключить и настроить автоматический импорт модулей, используйте `$PSModuleAutoLoadingPreference` переменную предпочтение.</span><span class="sxs-lookup"><span data-stu-id="a6b30-116">To enable, disable, and configure automatic importing of modules, use the `$PSModuleAutoLoadingPreference` preference variable.</span></span> <span data-ttu-id="a6b30-117">Дополнительные сведения см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="a6b30-117">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="a6b30-118">`Get-Command` Получает данные непосредственно из кода команды, в отличие от `Get-Help` , который получает сведения из разделов справки.</span><span class="sxs-lookup"><span data-stu-id="a6b30-118">`Get-Command` gets its data directly from the command code, unlike `Get-Help`, which gets its information from help topics.</span></span>

<span data-ttu-id="a6b30-119">Начиная с Windows PowerShell 5,0, `Get-Command` по умолчанию в результатах командлета отображается столбец **версии** .</span><span class="sxs-lookup"><span data-stu-id="a6b30-119">Starting in Windows PowerShell 5.0, results of the `Get-Command` cmdlet display a **Version** column by default.</span></span> <span data-ttu-id="a6b30-120">В класс **CommandInfo** было добавлено новое свойство **Version** .</span><span class="sxs-lookup"><span data-stu-id="a6b30-120">A new **Version** property has been added to the **CommandInfo** class.</span></span>

## <span data-ttu-id="a6b30-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="a6b30-121">EXAMPLES</span></span>

### <span data-ttu-id="a6b30-122">Пример 1. получение командлетов, функций и псевдонимов</span><span class="sxs-lookup"><span data-stu-id="a6b30-122">Example 1: Get cmdlets, functions, and aliases</span></span>

<span data-ttu-id="a6b30-123">Эта команда возвращает командлеты, функции и псевдонимы PowerShell, установленные на компьютере.</span><span class="sxs-lookup"><span data-stu-id="a6b30-123">This command gets the PowerShell cmdlets, functions, and aliases that are installed on the computer.</span></span>

```powershell
Get-Command
```

### <span data-ttu-id="a6b30-124">Пример 2. получение команд в текущем сеансе</span><span class="sxs-lookup"><span data-stu-id="a6b30-124">Example 2: Get commands in the current session</span></span>

<span data-ttu-id="a6b30-125">Эта команда использует параметр **ListImported** , чтобы получить только команды в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="a6b30-125">This command uses the **ListImported** parameter to get only the commands in the current session.</span></span>

```powershell
Get-Command -ListImported
```

### <span data-ttu-id="a6b30-126">Пример 3. получение командлетов и их отображение по порядку</span><span class="sxs-lookup"><span data-stu-id="a6b30-126">Example 3: Get cmdlets and display them in order</span></span>

<span data-ttu-id="a6b30-127">Эта команда получает все командлеты, сортирует их в алфавитном порядке по существительным в имени командлета, а затем отображает их в группах на базе существительных.</span><span class="sxs-lookup"><span data-stu-id="a6b30-127">This command gets all of the cmdlets, sorts them alphabetically by the noun in the cmdlet name, and then displays them in noun-based groups.</span></span> <span data-ttu-id="a6b30-128">Это помогает найти командлеты для задачи.</span><span class="sxs-lookup"><span data-stu-id="a6b30-128">This display can help you find the cmdlets for a task.</span></span>

```powershell
Get-Command -Type Cmdlet | Sort-Object -Property Noun | Format-Table -GroupBy Noun
```

### <span data-ttu-id="a6b30-129">Пример 4. получение команд в модуле</span><span class="sxs-lookup"><span data-stu-id="a6b30-129">Example 4: Get commands in a module</span></span>

<span data-ttu-id="a6b30-130">Эта команда использует параметр **module** для получения команд в модулях Microsoft. PowerShell. Security и Microsoft. PowerShell. Utility.</span><span class="sxs-lookup"><span data-stu-id="a6b30-130">This command uses the **Module** parameter to get the commands in the Microsoft.PowerShell.Security and Microsoft.PowerShell.Utility modules.</span></span>

```powershell
Get-Command -Module Microsoft.PowerShell.Security, Microsoft.PowerShell.Utility
```

### <span data-ttu-id="a6b30-131">Пример 5. Получение сведений о командлете</span><span class="sxs-lookup"><span data-stu-id="a6b30-131">Example 5: Get information about a cmdlet</span></span>

<span data-ttu-id="a6b30-132">Эта команда возвращает сведения о `Get-AppLockerPolicy` командлете.</span><span class="sxs-lookup"><span data-stu-id="a6b30-132">This command gets information about the `Get-AppLockerPolicy` cmdlet.</span></span> <span data-ttu-id="a6b30-133">Она также импортирует модуль **AppLocker** , который добавляет все команды в модуле **AppLocker** в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="a6b30-133">It also imports the **AppLocker** module, which adds all of the commands in the **AppLocker** module to the current session.</span></span>

```powershell
Get-Command Get-AppLockerPolicy
```

<span data-ttu-id="a6b30-134">Если модуль импортируется автоматически, результат аналогичен результату при использовании командлета Import-Module.</span><span class="sxs-lookup"><span data-stu-id="a6b30-134">When a module is imported automatically, the effect is the same as using the Import-Module cmdlet.</span></span>
<span data-ttu-id="a6b30-135">Модуль может добавить команды, типы и файлы форматирования, а также запустить скрипты в сеансе.</span><span class="sxs-lookup"><span data-stu-id="a6b30-135">The module can add commands, types and formatting files, and run scripts in the session.</span></span> <span data-ttu-id="a6b30-136">Чтобы включить, отключить и настроить автоматический импорт модулей, используйте `$PSModuleAutoLoadingPreference` переменную предпочтение.</span><span class="sxs-lookup"><span data-stu-id="a6b30-136">To enable, disable, and configuration automatic importing of modules, use the `$PSModuleAutoLoadingPreference` preference variable.</span></span> <span data-ttu-id="a6b30-137">Дополнительные сведения см. в разделе [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="a6b30-137">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

### <span data-ttu-id="a6b30-138">Пример 6. получение синтаксиса командлета</span><span class="sxs-lookup"><span data-stu-id="a6b30-138">Example 6: Get the syntax of a cmdlet</span></span>

<span data-ttu-id="a6b30-139">Эта команда использует параметры **ArgumentList** и **синтаксиса** для получения синтаксиса `Get-ChildItem` командлета, когда он используется на диске CERT:.</span><span class="sxs-lookup"><span data-stu-id="a6b30-139">This command uses the **ArgumentList** and **Syntax** parameters to get the syntax of the `Get-ChildItem` cmdlet when it is used in the Cert: drive.</span></span> <span data-ttu-id="a6b30-140">Диск CERT: — это диск PowerShell, который поставщик сертификатов добавляет в сеанс.</span><span class="sxs-lookup"><span data-stu-id="a6b30-140">The Cert: drive is a PowerShell drive that the Certificate Provider adds to the session.</span></span>

```powershell
Get-Command Get-Childitem -Args Cert: -Syntax
```

<span data-ttu-id="a6b30-141">При сравнении синтаксиса, отображаемого в выходных данных, с синтаксисом, который отображается при пропуске параметра **args** ( **ArgumentList** ), вы увидите, что **поставщик сертификатов** добавляет динамический параметр **CodeSigningCert** в `Get-ChildItem` командлет.</span><span class="sxs-lookup"><span data-stu-id="a6b30-141">When you compare the syntax displayed in the output with the syntax that is displayed when you omit the **Args** ( **ArgumentList** ) parameter, you'll see that the **Certificate provider** adds a dynamic parameter, **CodeSigningCert** , to the `Get-ChildItem` cmdlet.</span></span>

<span data-ttu-id="a6b30-142">Дополнительные сведения о поставщике сертификатов см. в разделе [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span><span class="sxs-lookup"><span data-stu-id="a6b30-142">For more information about the Certificate provider, see [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span></span>

### <span data-ttu-id="a6b30-143">Пример 7. получение динамических параметров</span><span class="sxs-lookup"><span data-stu-id="a6b30-143">Example 7: Get dynamic parameters</span></span>

<span data-ttu-id="a6b30-144">Команда в примере использует `Get-DynamicParameters` функцию для получения динамических параметров, которые поставщик сертификатов добавляет к `Get-ChildItem` командлету при его использовании на диске CERT:.</span><span class="sxs-lookup"><span data-stu-id="a6b30-144">The command in the example uses the `Get-DynamicParameters` function to get the dynamic parameters that the Certificate provider adds to the `Get-ChildItem` cmdlet when it is used in the Cert: drive.</span></span>

```powershell
function Get-DynamicParameters
{
    param ($Cmdlet, $PSDrive)
    (Get-Command $Cmdlet -ArgumentList $PSDrive).ParameterSets | ForEach-Object {$_.Parameters} | Where-Object { $_.IsDynamic } | Select-Object -Property Name -Unique
}
Get-DynamicParameters -Cmdlet Get-ChildItem -PSDrive Cert:
```

```Output
Name
----
CodeSigningCert
```

<span data-ttu-id="a6b30-145">`Get-DynamicParameters`Функция в этом примере получает динамические параметры командлета.</span><span class="sxs-lookup"><span data-stu-id="a6b30-145">The `Get-DynamicParameters` function in this example gets the dynamic parameters of a cmdlet.</span></span> <span data-ttu-id="a6b30-146">Это альтернативный метод, использованный в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="a6b30-146">This is an alternative to the method used in the previous example.</span></span> <span data-ttu-id="a6b30-147">Динамический параметр можно добавить в командлет с помощью другого командлета или поставщика.</span><span class="sxs-lookup"><span data-stu-id="a6b30-147">Dynamic parameter can be added to a cmdlet by another cmdlet or a provider.</span></span>

### <span data-ttu-id="a6b30-148">Пример 8. получение всех команд всех типов</span><span class="sxs-lookup"><span data-stu-id="a6b30-148">Example 8: Get all commands of all types</span></span>

<span data-ttu-id="a6b30-149">Эта команда возвращает все команды всех типов на локальном компьютере, включая исполняемые файлы, в пути переменной среды **path** ( `$env:path` ).</span><span class="sxs-lookup"><span data-stu-id="a6b30-149">This command gets all commands of all types on the local computer, including executable files in the paths of the **Path** environment variable (`$env:path`).</span></span>

```powershell
Get-Command *
```

<span data-ttu-id="a6b30-150">Она возвращает для каждого файла объект **ApplicationInfo** (System.Management.Automation.ApplicationInfo), а не объект **FileInfo** (System.IO.FileInfo).</span><span class="sxs-lookup"><span data-stu-id="a6b30-150">It returns an **ApplicationInfo** object (System.Management.Automation.ApplicationInfo) for each file, not a **FileInfo** object (System.IO.FileInfo).</span></span>

### <span data-ttu-id="a6b30-151">Пример 9. получение командлетов с помощью имени и типа параметра</span><span class="sxs-lookup"><span data-stu-id="a6b30-151">Example 9: Get cmdlets by using a parameter name and type</span></span>

<span data-ttu-id="a6b30-152">Эта команда получает командлеты с параметром, имя которого включает проверку подлинности и тип **AuthenticationMechanism**.</span><span class="sxs-lookup"><span data-stu-id="a6b30-152">This command gets cmdlets that have a parameter whose name includes Auth and whose type is **AuthenticationMechanism**.</span></span>

```powershell
Get-Command -ParameterName *Auth* -ParameterType AuthenticationMechanism
```

<span data-ttu-id="a6b30-153">Для поиска командлетов, которые позволяют указать метод, использующийся для проверки подлинности пользователя, можно использовать команду подобным образом.</span><span class="sxs-lookup"><span data-stu-id="a6b30-153">You can use a command like this one to find cmdlets that let you specify the method that is used to authenticate the user.</span></span>

<span data-ttu-id="a6b30-154">Параметр **ParameterType** разделяет параметры, которые получают значение **AuthenticationMechanism** от тех параметров, которые получают параметр **AuthenticationLevel** , даже если они имеют одинаковые имена.</span><span class="sxs-lookup"><span data-stu-id="a6b30-154">The **ParameterType** parameter distinguishes parameters that take an **AuthenticationMechanism** value from those that take an **AuthenticationLevel** parameter, even when they have similar names.</span></span>

### <span data-ttu-id="a6b30-155">Пример 10. получение псевдонима</span><span class="sxs-lookup"><span data-stu-id="a6b30-155">Example 10: Get an alias</span></span>

<span data-ttu-id="a6b30-156">В этом примере показано, как использовать `Get-Command` командлет с псевдонимом.</span><span class="sxs-lookup"><span data-stu-id="a6b30-156">This example shows how to use the `Get-Command` cmdlet with an alias.</span></span>

```powershell
Get-Command dir
```

```Output
CommandType     Name                                               ModuleName
-----------     ----                                               ----------
Alias           dir -> Get-ChildItem
```

<span data-ttu-id="a6b30-157">Хотя он обычно используется в командлетах и функциях, `Get-Command` также получает скрипты, функции, псевдонимы и исполняемые файлы.</span><span class="sxs-lookup"><span data-stu-id="a6b30-157">Although it is typically used on cmdlets and functions, `Get-Command` also gets scripts, functions, aliases, and executable files.</span></span>

<span data-ttu-id="a6b30-158">В выходных данных команды показано специальное представление значения свойства **Name** для псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="a6b30-158">The output of the command shows the special view of the **Name** property value for aliases.</span></span> <span data-ttu-id="a6b30-159">В представлении показан псевдоним и полное имя команды.</span><span class="sxs-lookup"><span data-stu-id="a6b30-159">The view shows the alias and the full command name.</span></span>

### <span data-ttu-id="a6b30-160">Пример 11. получение всех экземпляров команды Notepad</span><span class="sxs-lookup"><span data-stu-id="a6b30-160">Example 11: Get all instances of the Notepad command</span></span>

<span data-ttu-id="a6b30-161">В этом примере используется параметр **ALL** `Get-Command` командлета для отображения всех экземпляров команды «Notepad» на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a6b30-161">This example uses the **All** parameter of the `Get-Command` cmdlet to show all instances of the "Notepad" command on the local computer.</span></span>

```powershell
Get-Command Notepad -All | Format-Table CommandType, Name, Definition
```

```Output
CommandType     Name           Definition
-----------     ----           ----------
Application     notepad.exe    C:\WINDOWS\system32\notepad.exe
Application     NOTEPAD.EXE    C:\WINDOWS\NOTEPAD.EXE
```

<span data-ttu-id="a6b30-162">Параметр **All** полезен, если в сеансе есть больше одной команды с одинаковым именем.</span><span class="sxs-lookup"><span data-stu-id="a6b30-162">The **All** parameter is useful when there is more than one command with the same name in the session.</span></span>

<span data-ttu-id="a6b30-163">Начиная с Windows PowerShell 3,0, по умолчанию, когда сеанс включает несколько команд с одинаковым именем, `Get-Command` получает только команду, которая выполняется при вводе имени команды.</span><span class="sxs-lookup"><span data-stu-id="a6b30-163">Beginning in Windows PowerShell 3.0, by default, when the session includes multiple commands with the same name, `Get-Command` gets only the command that runs when you type the command name.</span></span> <span data-ttu-id="a6b30-164">При использовании параметра **ALL** `Get-Command` получает все команды с указанным именем и возвращает их в порядке очередности выполнения.</span><span class="sxs-lookup"><span data-stu-id="a6b30-164">With the **All** parameter, `Get-Command` gets all commands with the specified name and returns them in execution precedence order.</span></span> <span data-ttu-id="a6b30-165">Чтобы запустить команду, которая не является первой в списке, введите полный путь к команде.</span><span class="sxs-lookup"><span data-stu-id="a6b30-165">To run a command other than the first one in the list, type the fully qualified path to the command.</span></span>

<span data-ttu-id="a6b30-166">Дополнительные сведения о приоритете команд см. в разделе [about_Command_Precedence](About/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="a6b30-166">For more information about command precedence, see [about_Command_Precedence](About/about_Command_Precedence.md).</span></span>

### <span data-ttu-id="a6b30-167">Пример 12. Получение имени модуля, содержащего командлет</span><span class="sxs-lookup"><span data-stu-id="a6b30-167">Example 12: Get the name of a module that contains a cmdlet</span></span>

<span data-ttu-id="a6b30-168">Эта команда возвращает имя модуля, в котором `Get-Date` был создан командлет.</span><span class="sxs-lookup"><span data-stu-id="a6b30-168">This command gets the name of the module in which the `Get-Date` cmdlet originated.</span></span>
<span data-ttu-id="a6b30-169">Команда использует свойство **ModuleName** всех команд.</span><span class="sxs-lookup"><span data-stu-id="a6b30-169">The command uses the **ModuleName** property of all commands.</span></span>

```powershell
(Get-Command Get-Date).ModuleName
```

```Output
Microsoft.PowerShell.Utility
```

<span data-ttu-id="a6b30-170">Этот формат команды работает с командами в модулях PowerShell, даже если они не импортированы в сеанс.</span><span class="sxs-lookup"><span data-stu-id="a6b30-170">This command format works on commands in PowerShell modules, even if they are not imported into the session.</span></span>

### <span data-ttu-id="a6b30-171">Пример 13. получение командлетов и функций с типом выходных данных</span><span class="sxs-lookup"><span data-stu-id="a6b30-171">Example 13: Get cmdlets and functions that have an output type</span></span>

```powershell
Get-Command -Type Cmdlet | Where-Object OutputType | Format-List -Property Name, OutputType
```

<span data-ttu-id="a6b30-172">Эта команда получает командлеты и функции, содержащие тип выходных данных и тип возвращаемых объектов.</span><span class="sxs-lookup"><span data-stu-id="a6b30-172">This command gets the cmdlets and functions that have an output type and the type of objects that they return.</span></span>

<span data-ttu-id="a6b30-173">Первая часть команды получает все командлеты.</span><span class="sxs-lookup"><span data-stu-id="a6b30-173">The first part of the command gets all cmdlets.</span></span>
<span data-ttu-id="a6b30-174">Оператор конвейера (|) отправляет командлеты `Where-Object` командлету, который выбирает только те, в которых заполнено свойство **OutputType** .</span><span class="sxs-lookup"><span data-stu-id="a6b30-174">A pipeline operator (|) sends the cmdlets to the `Where-Object` cmdlet, which selects only the ones in which the **OutputType** property is populated.</span></span>
<span data-ttu-id="a6b30-175">Другой конвейерный оператор отправляет выбранные объекты командлета в `Format-List` командлет, который отображает имя и тип выходных данных каждого командлета в списке.</span><span class="sxs-lookup"><span data-stu-id="a6b30-175">Another pipeline operator sends the selected cmdlet objects to the `Format-List` cmdlet, which displays the name and output type of each cmdlet in a list.</span></span>

<span data-ttu-id="a6b30-176">Свойство **OutputType** объекта **CommandInfo** имеет значение, отличное от NULL, только если код командлета определяет для командлета атрибут **OutputType**.</span><span class="sxs-lookup"><span data-stu-id="a6b30-176">The **OutputType** property of a **CommandInfo** object has a non-null value only when the cmdlet code defines the **OutputType** attribute for the cmdlet.</span></span>

### <span data-ttu-id="a6b30-177">Пример 14. получение командлетов, которые принимают в качестве входных данных конкретный тип объекта</span><span class="sxs-lookup"><span data-stu-id="a6b30-177">Example 14: Get cmdlets that take a specific object type as input</span></span>

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

<span data-ttu-id="a6b30-178">Эта команда находит командлеты, которые получают объекты сетевого адаптера в качестве выходных данных.</span><span class="sxs-lookup"><span data-stu-id="a6b30-178">This command finds cmdlets that take net adapter objects as input.</span></span> <span data-ttu-id="a6b30-179">Этот формат команды можно использовать для поиска командлетов, которые принимают тип объектов, возвращаемый любой командой.</span><span class="sxs-lookup"><span data-stu-id="a6b30-179">You can use this command format to find the cmdlets that accept the type of objects that any command returns.</span></span>

<span data-ttu-id="a6b30-180">Команда использует внутреннее свойство **PSTypeNames** всех объектов, которые получают типы, описывающие объект.</span><span class="sxs-lookup"><span data-stu-id="a6b30-180">The command uses the **PSTypeNames** intrinsic property of all objects, which gets the types that describe the object.</span></span> <span data-ttu-id="a6b30-181">Чтобы получить свойство сетевого адаптера **PSTypeNames** , а не свойство коллекции сетевых адаптеров **PSTypeNames** , команда использует нотацию массива, чтобы получить первый сетевой адаптер, который возвращает командлет.</span><span class="sxs-lookup"><span data-stu-id="a6b30-181">To get the **PSTypeNames** property of a net adapter, and not the **PSTypeNames** property of a collection of net adapters, the command uses array notation to get the first net adapter that the cmdlet returns.</span></span>

### <span data-ttu-id="a6b30-182">Пример 15. получение команд с помощью нечеткого соответствия</span><span class="sxs-lookup"><span data-stu-id="a6b30-182">Example 15: Get commands using a fuzzy match</span></span>

<span data-ttu-id="a6b30-183">В этом примере имя команды намеренно имеет опечатку "Get-коммнд".</span><span class="sxs-lookup"><span data-stu-id="a6b30-183">In this example, the name of the command deliberately has a typo as 'get-commnd'.</span></span>
<span data-ttu-id="a6b30-184">С помощью `-UseFuzzyMatching` параметра командлет определил, что в системе с наиболее подходящей соответствием `Get-Command` следуют другие машинные команды, которые были аналогичными.</span><span class="sxs-lookup"><span data-stu-id="a6b30-184">Using the `-UseFuzzyMatching` switch, the cmdlet determined that the best match was `Get-Command` followed by other native commands on the system that were a similar match.</span></span>

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

## <span data-ttu-id="a6b30-185">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a6b30-185">PARAMETERS</span></span>

### <span data-ttu-id="a6b30-186">-All</span><span class="sxs-lookup"><span data-stu-id="a6b30-186">-All</span></span>

<span data-ttu-id="a6b30-187">Указывает, что этот командлет получает все команды, включая команды того же типа с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="a6b30-187">Indicates that this cmdlet gets all commands, including commands of the same type that have the same name.</span></span> <span data-ttu-id="a6b30-188">По умолчанию `Get-Command` получает только команды, которые выполняются при вводе имени команды.</span><span class="sxs-lookup"><span data-stu-id="a6b30-188">By default, `Get-Command` gets only the commands that run when you type the command name.</span></span>

<span data-ttu-id="a6b30-189">Дополнительные сведения о методе, используемом PowerShell для выбора команды, которая будет выполняться, если несколько команд имеют одинаковые имена, см. в разделе [about_Command_Precedence](About/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="a6b30-189">For more information about the method that PowerShell uses to select the command to run when multiple commands have the same name, see [about_Command_Precedence](About/about_Command_Precedence.md).</span></span>
<span data-ttu-id="a6b30-190">Сведения об именах команд с указанием модуля и выполнении команд, которые не выполняются по умолчанию из-за конфликта имен, см. в разделе [about_Modules](About/about_Modules.md).</span><span class="sxs-lookup"><span data-stu-id="a6b30-190">For information about module-qualified command names and running commands that do not run by default because of a name conflict, see [about_Modules](About/about_Modules.md).</span></span>

<span data-ttu-id="a6b30-191">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a6b30-191">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="a6b30-192">В Windows PowerShell 2,0 `Get-Command` по умолчанию получает все команды.</span><span class="sxs-lookup"><span data-stu-id="a6b30-192">In Windows PowerShell 2.0, `Get-Command` gets all commands by default.</span></span>

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

### <span data-ttu-id="a6b30-193">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="a6b30-193">-ArgumentList</span></span>

<span data-ttu-id="a6b30-194">Задает массив аргументов.</span><span class="sxs-lookup"><span data-stu-id="a6b30-194">Specifies an array of arguments.</span></span> <span data-ttu-id="a6b30-195">Этот командлет получает сведения о командлете или функции при их использовании с указанными параметрами ("arguments").</span><span class="sxs-lookup"><span data-stu-id="a6b30-195">This cmdlet gets information about a cmdlet or function when it is used with the specified parameters ("arguments").</span></span> <span data-ttu-id="a6b30-196">Псевдоним для **ArgumentList** — **Args**.</span><span class="sxs-lookup"><span data-stu-id="a6b30-196">The alias for **ArgumentList** is **Args**.</span></span>

<span data-ttu-id="a6b30-197">Чтобы обнаружить динамические параметры, доступные только при использовании некоторых других параметров, задайте для параметра **ArgumentList** значение, которое вызывает динамические параметры.</span><span class="sxs-lookup"><span data-stu-id="a6b30-197">To detect dynamic parameters that are available only when certain other parameters are used, set the value of **ArgumentList** to the parameters that trigger the dynamic parameters.</span></span>

<span data-ttu-id="a6b30-198">Чтобы определить динамические параметры, которые поставщик добавляет к командлету, присвойте параметру **ArgumentList** путь на диске поставщика, например WSMan:, HKLM: или CERT:.</span><span class="sxs-lookup"><span data-stu-id="a6b30-198">To detect the dynamic parameters that a provider adds to a cmdlet, set the value of the **ArgumentList** parameter to a path in the provider drive, such as WSMan:, HKLM:, or Cert:.</span></span> <span data-ttu-id="a6b30-199">Если команда является командлетом поставщика PowerShell, введите в каждой команде только один путь.</span><span class="sxs-lookup"><span data-stu-id="a6b30-199">When the command is a PowerShell provider cmdlet, enter only one path in each command.</span></span> <span data-ttu-id="a6b30-200">Командлеты поставщика возвращают только динамические параметры для первого пути в значении **ArgumentList**.</span><span class="sxs-lookup"><span data-stu-id="a6b30-200">The provider cmdlets return only the dynamic parameters for the first path the value of **ArgumentList**.</span></span> <span data-ttu-id="a6b30-201">Дополнительные сведения о командлетах поставщика см. в разделе [about_Providers](About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="a6b30-201">For information about the provider cmdlets, see [about_Providers](About/about_Providers.md).</span></span>

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

### <span data-ttu-id="a6b30-202">-CommandType</span><span class="sxs-lookup"><span data-stu-id="a6b30-202">-CommandType</span></span>

<span data-ttu-id="a6b30-203">Указывает типы команд, которые получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="a6b30-203">Specifies the types of commands that this cmdlet gets.</span></span> <span data-ttu-id="a6b30-204">Введите один или несколько типов команд.</span><span class="sxs-lookup"><span data-stu-id="a6b30-204">Enter one or more command types.</span></span> <span data-ttu-id="a6b30-205">Используйте параметр **CommandType** или его псевдоним **Type**.</span><span class="sxs-lookup"><span data-stu-id="a6b30-205">Use **CommandType** or its alias, **Type**.</span></span> <span data-ttu-id="a6b30-206">По умолчанию `Get-Command` получает все командлеты, функции и псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="a6b30-206">By default, `Get-Command` gets all cmdlets, functions, and aliases.</span></span>

<span data-ttu-id="a6b30-207">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="a6b30-207">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="a6b30-208">Псевдоним.</span><span class="sxs-lookup"><span data-stu-id="a6b30-208">Alias.</span></span> <span data-ttu-id="a6b30-209">Возвращает псевдонимы всех команд PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6b30-209">Gets the aliases of all PowerShell commands.</span></span> <span data-ttu-id="a6b30-210">Дополнительные сведения см. в разделе [about_Aliases](About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="a6b30-210">For more information, see [about_Aliases](About/about_Aliases.md).</span></span>
- <span data-ttu-id="a6b30-211">Все.</span><span class="sxs-lookup"><span data-stu-id="a6b30-211">All.</span></span> <span data-ttu-id="a6b30-212">Получает все типы команд.</span><span class="sxs-lookup"><span data-stu-id="a6b30-212">Gets all command types.</span></span> <span data-ttu-id="a6b30-213">Значение этого параметра эквивалентно значению `Get-Command *` .</span><span class="sxs-lookup"><span data-stu-id="a6b30-213">This parameter value is the equivalent of `Get-Command *`.</span></span>
- <span data-ttu-id="a6b30-214">приложение.</span><span class="sxs-lookup"><span data-stu-id="a6b30-214">Application.</span></span> <span data-ttu-id="a6b30-215">Возвращает файлы, не относящиеся к PowerShell, в путях, указанных в переменной среды **path** ($env:p ь), включая txt, exe и DLL-файлы.</span><span class="sxs-lookup"><span data-stu-id="a6b30-215">Gets non-PowerShell files in paths listed in the **Path** environment variable ($env:path), including .txt, .exe, and .dll files.</span></span> <span data-ttu-id="a6b30-216">Дополнительные сведения о переменной среды **Path** см. в разделе about_Environment_Variables.</span><span class="sxs-lookup"><span data-stu-id="a6b30-216">For more information about the **Path** environment variable, see about_Environment_Variables.</span></span>
- <span data-ttu-id="a6b30-217">Командлет.</span><span class="sxs-lookup"><span data-stu-id="a6b30-217">Cmdlet.</span></span> <span data-ttu-id="a6b30-218">Получает все командлеты.</span><span class="sxs-lookup"><span data-stu-id="a6b30-218">Gets all cmdlets.</span></span>
- <span data-ttu-id="a6b30-219">Екстерналскрипт.</span><span class="sxs-lookup"><span data-stu-id="a6b30-219">ExternalScript.</span></span> <span data-ttu-id="a6b30-220">Получает все PS1-файлы в путях, указанных в переменной среды **Path** ($env:path).</span><span class="sxs-lookup"><span data-stu-id="a6b30-220">Gets all .ps1 files in the paths listed in the **Path** environment variable ($env:path).</span></span>
- <span data-ttu-id="a6b30-221">Фильтр и функция.</span><span class="sxs-lookup"><span data-stu-id="a6b30-221">Filter and Function.</span></span> <span data-ttu-id="a6b30-222">Возвращает все расширенные и простые функции и фильтры PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6b30-222">Gets all PowerShell advanced and simple functions and filters.</span></span>
- <span data-ttu-id="a6b30-223">Скрипт.</span><span class="sxs-lookup"><span data-stu-id="a6b30-223">Script.</span></span> <span data-ttu-id="a6b30-224">Получает все блоки скриптов.</span><span class="sxs-lookup"><span data-stu-id="a6b30-224">Gets all script blocks.</span></span> <span data-ttu-id="a6b30-225">Чтобы получить скрипты PowerShell (PS1-файлы), используйте значение Екстерналскрипт.</span><span class="sxs-lookup"><span data-stu-id="a6b30-225">To get PowerShell scripts (.ps1 files), use the ExternalScript value.</span></span>

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

### <span data-ttu-id="a6b30-226">-FullyQualifiedModule</span><span class="sxs-lookup"><span data-stu-id="a6b30-226">-FullyQualifiedModule</span></span>

<span data-ttu-id="a6b30-227">Указывает модули с именами, указанными в форме объектов **ModuleSpecification** , описанной в разделе **"Примечания"** [конструктора ModuleSpecification (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span><span class="sxs-lookup"><span data-stu-id="a6b30-227">Specifies modules with names that are specified in the form of **ModuleSpecification** objects, described in the **Remarks** section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>
<span data-ttu-id="a6b30-228">Например, параметр **FullyQualifiedModule** принимает имя модуля, указанное в одном из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="a6b30-228">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in one of the following formats:</span></span>

- `@{ModuleName = "modulename"; ModuleVersion = "version_number"}`
- `@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

<span data-ttu-id="a6b30-229">Параметры **ModuleName** и **ModuleVersion** обязательны, а **Guid**  — нет.</span><span class="sxs-lookup"><span data-stu-id="a6b30-229">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span>

<span data-ttu-id="a6b30-230">Нельзя указать параметр **FullyQualifiedModule** в той же команде, что и параметр **module** .</span><span class="sxs-lookup"><span data-stu-id="a6b30-230">You cannot specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span> <span data-ttu-id="a6b30-231">Два параметра являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="a6b30-231">The two parameters are mutually exclusive.</span></span>

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

### <span data-ttu-id="a6b30-232">-ListImported</span><span class="sxs-lookup"><span data-stu-id="a6b30-232">-ListImported</span></span>

<span data-ttu-id="a6b30-233">Указывает, что этот командлет получает только команды в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="a6b30-233">Indicates that this cmdlet gets only commands in the current session.</span></span>

<span data-ttu-id="a6b30-234">Начиная с PowerShell 3,0, по умолчанию `Get-Command` получает все установленные команды, включая, но не ограниченные, команды в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="a6b30-234">Starting in PowerShell 3.0, by default, `Get-Command` gets all installed commands, including, but not limited to, the commands in the current session.</span></span> <span data-ttu-id="a6b30-235">В PowerShell 2,0 он возвращает только команды в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="a6b30-235">In PowerShell 2.0, it gets only commands in the current session.</span></span>

<span data-ttu-id="a6b30-236">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a6b30-236">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a6b30-237">-Module</span><span class="sxs-lookup"><span data-stu-id="a6b30-237">-Module</span></span>

<span data-ttu-id="a6b30-238">Указывает массив модулей.</span><span class="sxs-lookup"><span data-stu-id="a6b30-238">Specifies an array of modules.</span></span> <span data-ttu-id="a6b30-239">Этот командлет получает команды, поступившие из указанных модулей.</span><span class="sxs-lookup"><span data-stu-id="a6b30-239">This cmdlet gets the commands that came from the specified modules.</span></span>
<span data-ttu-id="a6b30-240">Введите имена модулей или объектов модуля.</span><span class="sxs-lookup"><span data-stu-id="a6b30-240">Enter the names of modules or module objects.</span></span>

<span data-ttu-id="a6b30-241">Этот параметр принимает строковые значения, но значение этого параметра также может быть объектом **PSModuleInfo** , таким как объекты, `Get-Module` `Import-PSSession` возвращаемые командлетами и.</span><span class="sxs-lookup"><span data-stu-id="a6b30-241">This parameter takes string values, but the value of this parameter can also be a **PSModuleInfo** object, such as the objects that the `Get-Module` and `Import-PSSession` cmdlets return.</span></span>

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

### <span data-ttu-id="a6b30-242">-Name</span><span class="sxs-lookup"><span data-stu-id="a6b30-242">-Name</span></span>

<span data-ttu-id="a6b30-243">Задает массив имен.</span><span class="sxs-lookup"><span data-stu-id="a6b30-243">Specifies an array of names.</span></span> <span data-ttu-id="a6b30-244">Этот командлет возвращает только команды с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="a6b30-244">This cmdlet gets only commands that have the specified name.</span></span> <span data-ttu-id="a6b30-245">Введите имя или шаблон имени.</span><span class="sxs-lookup"><span data-stu-id="a6b30-245">Enter a name or name pattern.</span></span> <span data-ttu-id="a6b30-246">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="a6b30-246">Wildcard characters are permitted.</span></span>

<span data-ttu-id="a6b30-247">Чтобы получить команды с одинаковым именем, используйте параметр **All**.</span><span class="sxs-lookup"><span data-stu-id="a6b30-247">To get commands that have the same name, use the **All** parameter.</span></span> <span data-ttu-id="a6b30-248">Если две команды имеют одинаковое имя, по умолчанию `Get-Command` получает команду, которая выполняется при вводе имени команды.</span><span class="sxs-lookup"><span data-stu-id="a6b30-248">When two commands have the same name, by default, `Get-Command` gets the command that runs when you type the command name.</span></span>

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

### <span data-ttu-id="a6b30-249">-Noun</span><span class="sxs-lookup"><span data-stu-id="a6b30-249">-Noun</span></span>

<span data-ttu-id="a6b30-250">Указывает массив существительных команд.</span><span class="sxs-lookup"><span data-stu-id="a6b30-250">Specifies an array of command nouns.</span></span> <span data-ttu-id="a6b30-251">Этот командлет возвращает команды, которые включают командлеты, функции и псевдонимы, имена которых содержат указанное существительное.</span><span class="sxs-lookup"><span data-stu-id="a6b30-251">This cmdlet gets commands, which include cmdlets, functions, and aliases, that have names that include the specified noun.</span></span> <span data-ttu-id="a6b30-252">Введите одно или несколько существительных или шаблонов существительных.</span><span class="sxs-lookup"><span data-stu-id="a6b30-252">Enter one or more nouns or noun patterns.</span></span> <span data-ttu-id="a6b30-253">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="a6b30-253">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="a6b30-254">-ParameterName</span><span class="sxs-lookup"><span data-stu-id="a6b30-254">-ParameterName</span></span>

<span data-ttu-id="a6b30-255">Указывает массив имен параметров.</span><span class="sxs-lookup"><span data-stu-id="a6b30-255">Specifies an array of parameter names.</span></span> <span data-ttu-id="a6b30-256">Этот командлет возвращает команды в сеансе с указанными параметрами.</span><span class="sxs-lookup"><span data-stu-id="a6b30-256">This cmdlet gets commands in the session that have the specified parameters.</span></span> <span data-ttu-id="a6b30-257">Введите имена параметров или псевдонимы параметров.</span><span class="sxs-lookup"><span data-stu-id="a6b30-257">Enter parameter names or parameter aliases.</span></span> <span data-ttu-id="a6b30-258">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="a6b30-258">Wildcard characters are supported.</span></span>

<span data-ttu-id="a6b30-259">Параметры **ParameterName** и **ParameterType** ищут только команды в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="a6b30-259">The **ParameterName** and **ParameterType** parameters search only commands in the current session.</span></span>

<span data-ttu-id="a6b30-260">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a6b30-260">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a6b30-261">-ParameterType</span><span class="sxs-lookup"><span data-stu-id="a6b30-261">-ParameterType</span></span>

<span data-ttu-id="a6b30-262">Указывает массив имен параметров.</span><span class="sxs-lookup"><span data-stu-id="a6b30-262">Specifies an array of parameter names.</span></span> <span data-ttu-id="a6b30-263">Этот командлет возвращает команды в сеансе, которые имеют параметры указанного типа.</span><span class="sxs-lookup"><span data-stu-id="a6b30-263">This cmdlet gets commands in the session that have parameters of the specified type.</span></span> <span data-ttu-id="a6b30-264">Введите полное имя или частичное имя типа параметра.</span><span class="sxs-lookup"><span data-stu-id="a6b30-264">Enter the full name or partial name of a parameter type.</span></span> <span data-ttu-id="a6b30-265">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="a6b30-265">Wildcard characters are supported.</span></span>

<span data-ttu-id="a6b30-266">Параметры **ParameterName** и **ParameterType** ищут только команды в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="a6b30-266">The **ParameterName** and **ParameterType** parameters search only commands in the current session.</span></span>

<span data-ttu-id="a6b30-267">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a6b30-267">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="a6b30-268">-ShowCommandInfo</span><span class="sxs-lookup"><span data-stu-id="a6b30-268">-ShowCommandInfo</span></span>

<span data-ttu-id="a6b30-269">Указывает, что этот командлет отображает сведения о команде.</span><span class="sxs-lookup"><span data-stu-id="a6b30-269">Indicates that this cmdlet displays command information.</span></span>

<span data-ttu-id="a6b30-270">Этот параметр появился в Windows PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="a6b30-270">This parameter was introduced in Windows PowerShell 5.0.</span></span>

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

### <span data-ttu-id="a6b30-271">-Syntax</span><span class="sxs-lookup"><span data-stu-id="a6b30-271">-Syntax</span></span>

<span data-ttu-id="a6b30-272">Указывает, что этот командлет получает только следующие указанные данные о команде:</span><span class="sxs-lookup"><span data-stu-id="a6b30-272">Indicates that this cmdlet gets only the following specified data about the command:</span></span>

- <span data-ttu-id="a6b30-273">Псевдоним.</span><span class="sxs-lookup"><span data-stu-id="a6b30-273">Aliases.</span></span> <span data-ttu-id="a6b30-274">Возвращает стандартное имя.</span><span class="sxs-lookup"><span data-stu-id="a6b30-274">Gets the standard name.</span></span>
- <span data-ttu-id="a6b30-275">Образующих.</span><span class="sxs-lookup"><span data-stu-id="a6b30-275">Cmdlets.</span></span> <span data-ttu-id="a6b30-276">Возвращает синтаксис.</span><span class="sxs-lookup"><span data-stu-id="a6b30-276">Gets the syntax.</span></span>
- <span data-ttu-id="a6b30-277">Функции и фильтры.</span><span class="sxs-lookup"><span data-stu-id="a6b30-277">Functions and filters.</span></span> <span data-ttu-id="a6b30-278">Возвращает определение функции.</span><span class="sxs-lookup"><span data-stu-id="a6b30-278">Gets the function definition.</span></span>
- <span data-ttu-id="a6b30-279">Скрипты и приложения или файлы.</span><span class="sxs-lookup"><span data-stu-id="a6b30-279">Scripts and applications or files.</span></span> <span data-ttu-id="a6b30-280">Возвращает путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="a6b30-280">Gets the path and filename.</span></span>

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

### <span data-ttu-id="a6b30-281">-TotalCount</span><span class="sxs-lookup"><span data-stu-id="a6b30-281">-TotalCount</span></span>

<span data-ttu-id="a6b30-282">Указывает количество команд для получения.</span><span class="sxs-lookup"><span data-stu-id="a6b30-282">Specifies the number of commands to get.</span></span> <span data-ttu-id="a6b30-283">Этот параметр можно использовать, чтобы ограничить выходные данные команды.</span><span class="sxs-lookup"><span data-stu-id="a6b30-283">You can use this parameter to limit the output of a command.</span></span>

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

### <span data-ttu-id="a6b30-284">-Усефуззиматчинг</span><span class="sxs-lookup"><span data-stu-id="a6b30-284">-UseFuzzyMatching</span></span>

<span data-ttu-id="a6b30-285">Указывает использование алгоритма нечеткого сопоставления при поиске команд.</span><span class="sxs-lookup"><span data-stu-id="a6b30-285">Indicates using a fuzzy matching algorithm when finding commands.</span></span> <span data-ttu-id="a6b30-286">Порядок выходных данных находится в порядке приближения к наиболее вероятным совпадениям.</span><span class="sxs-lookup"><span data-stu-id="a6b30-286">The order of the output is from closest match to least likely match.</span></span> <span data-ttu-id="a6b30-287">Подстановочные знаки не следует использовать с нечетким соответствием, так как они будут пытаться сопоставлять команды, которые могут содержать эти подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="a6b30-287">Wildcards should not be used with fuzzy matching as it will attempt to match commands that may contain those wildcard characters.</span></span>

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

### <span data-ttu-id="a6b30-288">-Verb</span><span class="sxs-lookup"><span data-stu-id="a6b30-288">-Verb</span></span>

<span data-ttu-id="a6b30-289">Задает массив команд.</span><span class="sxs-lookup"><span data-stu-id="a6b30-289">Specifies an array of command verbs.</span></span> <span data-ttu-id="a6b30-290">Этот командлет возвращает команды, которые включают командлеты, функции и псевдонимы, имеющие имена, включающие указанную команду.</span><span class="sxs-lookup"><span data-stu-id="a6b30-290">This cmdlet gets commands, which include cmdlets, functions, and aliases, that have names that include the specified verb.</span></span> <span data-ttu-id="a6b30-291">Введите один или несколько глаголов или шаблонов глаголов.</span><span class="sxs-lookup"><span data-stu-id="a6b30-291">Enter one or more verbs or verb patterns.</span></span> <span data-ttu-id="a6b30-292">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="a6b30-292">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="a6b30-293">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a6b30-293">CommonParameters</span></span>

<span data-ttu-id="a6b30-294">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a6b30-294">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a6b30-295">См. сведения в разделе [about_CommonParameters](About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="a6b30-295">For more information, see [about_CommonParameters](About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="a6b30-296">Входные данные</span><span class="sxs-lookup"><span data-stu-id="a6b30-296">INPUTS</span></span>

### <span data-ttu-id="a6b30-297">System.String</span><span class="sxs-lookup"><span data-stu-id="a6b30-297">System.String</span></span>

<span data-ttu-id="a6b30-298">В этот командлет можно передать имена команд по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="a6b30-298">You can pipe command names to this cmdlet.</span></span>

## <span data-ttu-id="a6b30-299">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a6b30-299">OUTPUTS</span></span>

### <span data-ttu-id="a6b30-300">System.Management.Automation.CommandInfo</span><span class="sxs-lookup"><span data-stu-id="a6b30-300">System.Management.Automation.CommandInfo</span></span>

<span data-ttu-id="a6b30-301">Этот командлет возвращает объекты, производные от класса **CommandInfo** .</span><span class="sxs-lookup"><span data-stu-id="a6b30-301">This cmdlet returns objects derived from the **CommandInfo** class.</span></span> <span data-ttu-id="a6b30-302">Тип возвращаемого объекта зависит от типа команды, которая `Get-Command` получает.</span><span class="sxs-lookup"><span data-stu-id="a6b30-302">The type of object that is returned depends on the type of command that `Get-Command` gets.</span></span>

### <span data-ttu-id="a6b30-303">System.Management.Automation.AliasInfo</span><span class="sxs-lookup"><span data-stu-id="a6b30-303">System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="a6b30-304">Представляет псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="a6b30-304">Represents aliases.</span></span>

### <span data-ttu-id="a6b30-305">System.Management.Automation.ApplicationInfo</span><span class="sxs-lookup"><span data-stu-id="a6b30-305">System.Management.Automation.ApplicationInfo</span></span>

<span data-ttu-id="a6b30-306">Представляет приложения и файлы.</span><span class="sxs-lookup"><span data-stu-id="a6b30-306">Represents applications and files.</span></span>

### <span data-ttu-id="a6b30-307">System.Management.Automation.CmdletInfo</span><span class="sxs-lookup"><span data-stu-id="a6b30-307">System.Management.Automation.CmdletInfo</span></span>

<span data-ttu-id="a6b30-308">Представляет командлеты.</span><span class="sxs-lookup"><span data-stu-id="a6b30-308">Represents cmdlets.</span></span>

### <span data-ttu-id="a6b30-309">System.Management.Automation.FunctionInfo</span><span class="sxs-lookup"><span data-stu-id="a6b30-309">System.Management.Automation.FunctionInfo</span></span>

<span data-ttu-id="a6b30-310">Представляет функции и фильтры.</span><span class="sxs-lookup"><span data-stu-id="a6b30-310">Represents functions and filters.</span></span>

## <span data-ttu-id="a6b30-311">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="a6b30-311">NOTES</span></span>

* <span data-ttu-id="a6b30-312">Если в сеансе доступно более одной команды с одним и тем же именем, `Get-Command` Возвращает команду, которая выполняется при вводе имени команды.</span><span class="sxs-lookup"><span data-stu-id="a6b30-312">When more than one command that has the same name is available to the session, `Get-Command` returns the command that runs when you type the command name.</span></span> <span data-ttu-id="a6b30-313">Для получения команд с одинаковыми именами, перечисленными в списке порядок выполнения, используйте параметр **ALL** .</span><span class="sxs-lookup"><span data-stu-id="a6b30-313">To get commands that have the same name, listed in run order, use the **All** parameter.</span></span> <span data-ttu-id="a6b30-314">Дополнительные сведения см. в разделе [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md).</span><span class="sxs-lookup"><span data-stu-id="a6b30-314">For more information, see [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md).</span></span>
* <span data-ttu-id="a6b30-315">При автоматическом импорте модуля этот результат будет таким же, как и при использовании `Import-Module` командлета.</span><span class="sxs-lookup"><span data-stu-id="a6b30-315">When a module is imported automatically, the effect is the same as using the `Import-Module` cmdlet.</span></span> <span data-ttu-id="a6b30-316">Модуль может добавить команды, типы и файлы форматирования, а также запустить скрипты в сеансе.</span><span class="sxs-lookup"><span data-stu-id="a6b30-316">The module can add commands, types and formatting files, and run scripts in the session.</span></span>
  <span data-ttu-id="a6b30-317">Чтобы включить, отключить и настроить автоматический импорт модулей, используйте `$PSModuleAutoLoadingPreference` переменную предпочтение.</span><span class="sxs-lookup"><span data-stu-id="a6b30-317">To enable, disable, and configuration automatic importing of modules, use the `$PSModuleAutoLoadingPreference` preference variable.</span></span> <span data-ttu-id="a6b30-318">Дополнительные сведения см. в разделе [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="a6b30-318">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

## <span data-ttu-id="a6b30-319">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a6b30-319">RELATED LINKS</span></span>

[<span data-ttu-id="a6b30-320">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="a6b30-320">Export-PSSession</span></span>](../Microsoft.PowerShell.Utility/Export-PSSession.md)

[<span data-ttu-id="a6b30-321">Get-Help</span><span class="sxs-lookup"><span data-stu-id="a6b30-321">Get-Help</span></span>](Get-Help.md)

[<span data-ttu-id="a6b30-322">Get-Member</span><span class="sxs-lookup"><span data-stu-id="a6b30-322">Get-Member</span></span>](../Microsoft.PowerShell.Utility/Get-Member.md)

[<span data-ttu-id="a6b30-323">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="a6b30-323">Get-PSDrive</span></span>](../Microsoft.PowerShell.Management/Get-PSDrive.md)

[<span data-ttu-id="a6b30-324">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="a6b30-324">Import-PSSession</span></span>](../Microsoft.PowerShell.Utility/Import-PSSession.md)

[<span data-ttu-id="a6b30-325">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="a6b30-325">about_Command_Precedence</span></span>](About/about_Command_Precedence.md)
