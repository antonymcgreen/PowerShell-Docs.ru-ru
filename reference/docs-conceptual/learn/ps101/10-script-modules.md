---
title: Модули скриптов
description: Модули скриптов — это простой способ упаковки скриптов и функций в многократно используемый инструмент.
ms.date: 06/02/2020
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: c557c071bc202a4216a77e7e5ae0bd73b4bc014b
ms.sourcegitcommit: df5e6f032ee2d4b556d50406832732d2f7dc2502
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2021
ms.locfileid: "99605517"
---
# <a name="chapter-10---script-modules"></a><span data-ttu-id="c9a77-103">Глава 10. Модули скриптов</span><span class="sxs-lookup"><span data-stu-id="c9a77-103">Chapter 10 - Script modules</span></span>

<span data-ttu-id="c9a77-104">Преобразование ваших однострочных элементов кода и скриптов в PowerShell в многократно используемые средства станет еще более важным процессом, если вы будете регулярно его выполнять.</span><span class="sxs-lookup"><span data-stu-id="c9a77-104">Turning your one-liners and scripts in PowerShell into reusable tools becomes even more important if it's something that you're going to use frequently.</span></span> <span data-ttu-id="c9a77-105">После упаковки функций в модуль скрипта они выглядят более профессионально, что облегчает их совместное использование.</span><span class="sxs-lookup"><span data-stu-id="c9a77-105">Packaging your functions in a script module makes them look and feel more professional and makes them easier to share.</span></span>

## <a name="dot-sourcing-functions"></a><span data-ttu-id="c9a77-106">Функции вызова с использованием точки</span><span class="sxs-lookup"><span data-stu-id="c9a77-106">Dot-Sourcing Functions</span></span>

<span data-ttu-id="c9a77-107">В предыдущей главе мы с вами не рассматривали функции вызова с использованием точки.</span><span class="sxs-lookup"><span data-stu-id="c9a77-107">Something that we didn't talk about in the previous chapter is dot-sourcing functions.</span></span> <span data-ttu-id="c9a77-108">Если функция в скрипте не является частью модуля, единственный способ загрузить его в память — вызвать файл `.PS1` с точкой, в котором он сохранен.</span><span class="sxs-lookup"><span data-stu-id="c9a77-108">When a function in a script isn't part of a module, the only way to load it into memory is to dot-source the `.PS1` file that it's saved in.</span></span>

<span data-ttu-id="c9a77-109">Следующая функция сохранена как `Get-MrPSVersion.ps1`.</span><span class="sxs-lookup"><span data-stu-id="c9a77-109">The following function has been saved as `Get-MrPSVersion.ps1`.</span></span>

```powershell
function Get-MrPSVersion {
    $PSVersionTable
}
```

<span data-ttu-id="c9a77-110">При запуске скрипта ничего не происходит.</span><span class="sxs-lookup"><span data-stu-id="c9a77-110">When you run the script, nothing happens.</span></span>

```powershell
.\Get-MrPSVersion.ps1
```

<span data-ttu-id="c9a77-111">Если вы попытаетесь вызвать эту функцию, появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="c9a77-111">If you try to call the function, it generates an error message.</span></span>

```powershell
Get-MrPSVersion
```

```Output
Get-MrPSVersion : The term 'Get-MrPSVersion' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or if a path
was included, verify that the path is correct and try again.
At line:1 char:1
+ Get-MrPSVersion
    + CategoryInfo          : ObjectNotFound: (Get-MrPSVersion:String) [], CommandNotFou
   ndException
    + FullyQualifiedErrorId : CommandNotFoundException

```

<span data-ttu-id="c9a77-112">Вы можете определить, загружаются ли функции в память, если проверите, есть ли они в PSDrive **Function**.</span><span class="sxs-lookup"><span data-stu-id="c9a77-112">You can determine if functions are loaded into memory by checking to see if they exist on the **Function** PSDrive.</span></span>

```powershell
Get-ChildItem -Path Function:\Get-MrPSVersion
```

```Output
Get-ChildItem : Cannot find path 'Get-MrPSVersion' because it does not exist.
At line:1 char:1
+ Get-ChildItem -Path Function:\Get-MrPSVersion
    + CategoryInfo          : ObjectNotFound: (Get-MrPSVersion:String) [Get-ChildItem],
   ItemNotFoundException
    + FullyQualifiedErrorId : PathNotFound,Microsoft.PowerShell.Commands.GetChildItemCommand
```

<span data-ttu-id="c9a77-113">Проблема с вызовом скрипта, содержащего функцию, состоит в том, что функции загружаются в область _Script_.</span><span class="sxs-lookup"><span data-stu-id="c9a77-113">The problem with calling the script that contains the function is that the functions are loaded in the _Script_ scope.</span></span> <span data-ttu-id="c9a77-114">После выполнения скрипта область удаляется и вместе с ней удаляется функция.</span><span class="sxs-lookup"><span data-stu-id="c9a77-114">When the script completes, that scope is removed and the function is removed with it.</span></span>

<span data-ttu-id="c9a77-115">Функция должна быть загружена в область _Global_.</span><span class="sxs-lookup"><span data-stu-id="c9a77-115">The function needs to be loaded into the _Global_ scope.</span></span> <span data-ttu-id="c9a77-116">Это можно сделать вызовом скрипта с точкой, который содержит эту функцию.</span><span class="sxs-lookup"><span data-stu-id="c9a77-116">That can be accomplished by dot-sourcing the script that contains the function.</span></span> <span data-ttu-id="c9a77-117">При этом можно использовать относительный путь.</span><span class="sxs-lookup"><span data-stu-id="c9a77-117">The relative path can be used.</span></span>

```powershell
. .\Get-MrPSVersion.ps1
```

<span data-ttu-id="c9a77-118">Кроме того, можно использовать полный путь.</span><span class="sxs-lookup"><span data-stu-id="c9a77-118">The fully qualified path can also be used.</span></span>

```powershell
. C:\Demo\Get-MrPSVersion.ps1
```

<span data-ttu-id="c9a77-119">Если часть пути хранится в переменной, ее можно объединить с оставшейся частью пути.</span><span class="sxs-lookup"><span data-stu-id="c9a77-119">If a portion of the path is stored in a variable, it can be combined with the remainder of the path.</span></span>
<span data-ttu-id="c9a77-120">Для объединения переменной вместе с оставшейся частью пути не нужно использовать объединение строк.</span><span class="sxs-lookup"><span data-stu-id="c9a77-120">There's no reason to use string concatenation to combine the variable together with the remainder of the path.</span></span>

```powershell
$Path = 'C:\'
. $Path\Get-MrPSVersion.ps1
```

<span data-ttu-id="c9a77-121">Теперь, когда я проверяю PSDrive **Function**, функция `Get-MrPSVersion` существует.</span><span class="sxs-lookup"><span data-stu-id="c9a77-121">Now when I check the **Function** PSDrive, the `Get-MrPSVersion` function exists.</span></span>

```powershell
Get-ChildItem -Path Function:\Get-MrPSVersion
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Function        Get-MrPSVersion
```

## <a name="script-modules"></a><span data-ttu-id="c9a77-122">Модули скриптов</span><span class="sxs-lookup"><span data-stu-id="c9a77-122">Script Modules</span></span>

<span data-ttu-id="c9a77-123">Модуль скрипта в PowerShell — это всего лишь файл, содержащий одну функцию или несколько, сохраненных в виде файла `.PSM1`, а не файла `.PS1`.</span><span class="sxs-lookup"><span data-stu-id="c9a77-123">A script module in PowerShell is simply a file containing one or more functions that's saved as a `.PSM1` file instead of a `.PS1` file.</span></span>

<span data-ttu-id="c9a77-124">Как создать модуль скрипта?</span><span class="sxs-lookup"><span data-stu-id="c9a77-124">How do you create a script module?</span></span> <span data-ttu-id="c9a77-125">Вероятно, вы думаете, что это можно сделать с помощью команды с именем вроде `New-Module`.</span><span class="sxs-lookup"><span data-stu-id="c9a77-125">You're probably guessing with a command named something like `New-Module`.</span></span> <span data-ttu-id="c9a77-126">Ваше предположение будет неверным.</span><span class="sxs-lookup"><span data-stu-id="c9a77-126">Your assumption would be wrong.</span></span> <span data-ttu-id="c9a77-127">Хотя в PowerShell есть команда с именем `New-Module`, она создает динамический модуль, а не модуль скрипта.</span><span class="sxs-lookup"><span data-stu-id="c9a77-127">While there is a command in PowerShell named `New-Module`, that command creates a dynamic module, not a script module.</span></span> <span data-ttu-id="c9a77-128">Обязательно ознакомьтесь со справкой для команды, даже если считаете, что нашли нужную команду.</span><span class="sxs-lookup"><span data-stu-id="c9a77-128">Always be sure to read the help for a command even when you think you've found the command you need.</span></span>

```powershell
help New-Module
```

```Output
NAME
    New-Module

SYNOPSIS
    Creates a new dynamic module that exists only in memory.

SYNTAX
    New-Module [-Name] <String> [-ScriptBlock] <ScriptBlock> [-ArgumentList <Object[]>]
    [-AsCustomObject] [-Cmdlet <String[]>] [-Function <String[]>] [-ReturnResult]
    [<CommonParameters>]

DESCRIPTION
    The New-Module cmdlet creates a dynamic module from a script block. The members of
    the dynamic module, such as functions and variables, are immediately available in
    the session and remain available until you close the session.

    Like static modules, by default, the cmdlets and functions in a dynamic module are
    exported and the variables and aliases are not. However, you can use the
    Export-ModuleMember cmdlet and the parameters of New-Module to override the defaults.

    You can also use the AsCustomObject parameter of New-Module to return the dynamic
    module as a custom object. The members of the modules, such as functions, are
    implemented as script methods of the custom object instead of being imported into
    the session.

    Dynamic modules exist only in memory, not on disk. Like all modules, the members of
    dynamic modules run in a private module scope that is a child of the global scope.
    Get-Module cannot get a dynamic module, but Get-Command can get the exported members.

    To make a dynamic module available to Get-Module , pipe a New-Module command to
    Import-Module, or pipe the module object that New-Module returns to Import-Module .
    This action adds the dynamic module to the Get-Module list, but it does not save the
    module to disk or make it persistent.

RELATED LINKS
    Online Version: http://go.microsoft.com/fwlink/?LinkId=821495
    Export-ModuleMember
    Get-Module
    Import-Module
    Remove-Module

REMARKS
    To see the examples, type: "get-help New-Module -examples".
    For more information, type: "get-help New-Module -detailed".
    For technical information, type: "get-help New-Module -full".
    For online help, type: "get-help New-Module -online"
```

<span data-ttu-id="c9a77-129">В предыдущей главе я говорил, что функции должны использовать утвержденные команды, иначе при импорте модуля будет появляться предупреждающее сообщение.</span><span class="sxs-lookup"><span data-stu-id="c9a77-129">In the previous chapter, I mentioned that functions should use approved verbs otherwise they'll generate a warning message when the module is imported.</span></span> <span data-ttu-id="c9a77-130">В следующем коде командлет `New-Module` используется для создания динамического модуля в памяти.</span><span class="sxs-lookup"><span data-stu-id="c9a77-130">The following code uses the `New-Module` cmdlet to create a dynamic module in memory.</span></span> <span data-ttu-id="c9a77-131">Этот модуль демонстрирует предупреждение о неутвержденной команде.</span><span class="sxs-lookup"><span data-stu-id="c9a77-131">This module demonstrates the unapproved verb warning.</span></span>

```powershell
New-Module -Name MyModule -ScriptBlock {

    function Return-MrOsVersion {
        Get-CimInstance -ClassName Win32_OperatingSystem |
        Select-Object -Property @{label='OperatingSystem';expression={$_.Caption}}
    }

    Export-ModuleMember -Function Return-MrOsVersion

} | Import-Module
```

```Output
WARNING: The names of some imported commands from the module 'MyModule' include
unapproved verbs that might make them less discoverable. To find the commands with
unapproved verbs, run the Import-Module command again with the Verbose parameter. For a
list of approved verbs, type Get-Verb.
```

<span data-ttu-id="c9a77-132">Хотя в предыдущем примере использовался командлет `New-Module`, эта команда используется только для повторной итерации, а не для создания модулей скрипта в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9a77-132">Just to reiterate, although the `New-Module` cmdlet was used in the previous example, that's not the command for creating script modules in PowerShell.</span></span>

<span data-ttu-id="c9a77-133">Сохраните следующие две функции в файле с именем `MyScriptModule.psm1`.</span><span class="sxs-lookup"><span data-stu-id="c9a77-133">Save the following two functions in a file named `MyScriptModule.psm1`.</span></span>

```powershell
function Get-MrPSVersion {
    $PSVersionTable
}

function Get-MrComputerName {
    $env:COMPUTERNAME
}
```

<span data-ttu-id="c9a77-134">Попробуйте вызвать одну из функций.</span><span class="sxs-lookup"><span data-stu-id="c9a77-134">Try to call one of the functions.</span></span>

```powershell
Get-MrComputerName
```

```Output
Get-MrComputerName : The term 'Get-MrComputerName' is not recognized as the name of a
cmdlet, function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
At line:1 char:1
+ Get-MrComputerName
    + CategoryInfo          : ObjectNotFound: (Get-MrComputerName:String) [], CommandNot
   FoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

<span data-ttu-id="c9a77-135">Появится сообщение об ошибке, в котором говорится, что функция не найдена.</span><span class="sxs-lookup"><span data-stu-id="c9a77-135">An error message is generated saying the function can't be found.</span></span> <span data-ttu-id="c9a77-136">Кроме того, вы можете проверить PSDrive **Function** так, как делали это раньше, и увидите, что ее там тоже нет.</span><span class="sxs-lookup"><span data-stu-id="c9a77-136">You could also check the **Function** PSDrive just like before and you'll find that it doesn't exist there either.</span></span>

<span data-ttu-id="c9a77-137">Вы можете импортировать файл вручную с помощью командлета `Import-Module`.</span><span class="sxs-lookup"><span data-stu-id="c9a77-137">You could manually import the file with the `Import-Module` cmdlet.</span></span>

```powershell
Import-Module C:\MyScriptModule.psm1
```

<span data-ttu-id="c9a77-138">Функция автозагрузки модулей появилась в PowerShell версии 3.</span><span class="sxs-lookup"><span data-stu-id="c9a77-138">The module autoloading feature was introduced in PowerShell version 3.</span></span> <span data-ttu-id="c9a77-139">Чтобы воспользоваться преимуществами автозагрузки модулей, необходимо сохранить модуль скрипта в папке с тем же базовым именем, что и файл `.PSM1`, и в расположении, указанном в `$env:PSModulePath`.</span><span class="sxs-lookup"><span data-stu-id="c9a77-139">To take advantage of module autoloading, a script module needs to be saved in a folder with the same base name as the `.PSM1` file and in a location specified in `$env:PSModulePath`.</span></span>

```powershell
$env:PSModulePath
```

```Output
C:\Users\mike-ladm\Documents\WindowsPowerShell\Modules;C:\Program Files\WindowsPowerShell\
Modules;C:\Windows\system32\WindowsPowerShell\v1.0\Modules;C:\Program Files (x86)\Microsof
t SQL Server\130\Tools\PowerShell\Modules\
```

<span data-ttu-id="c9a77-140">Полученные результаты будет нелегко прочитать.</span><span class="sxs-lookup"><span data-stu-id="c9a77-140">The results are difficult to read.</span></span> <span data-ttu-id="c9a77-141">Так как пути разделяются точкой с запятой, можно разбить результаты, чтобы вернуть каждый путь на отдельной строке.</span><span class="sxs-lookup"><span data-stu-id="c9a77-141">Since the paths are separated by a semicolon, you can split the results to return each path on a separate line.</span></span> <span data-ttu-id="c9a77-142">Так их легче будет прочитать.</span><span class="sxs-lookup"><span data-stu-id="c9a77-142">This makes them easier to read.</span></span>

```powershell
$env:PSModulePath -split ';'
```

```Output
C:\Users\mike-ladm\Documents\WindowsPowerShell\Modules
C:\Program Files\WindowsPowerShell\Modules
C:\Windows\system32\WindowsPowerShell\v1.0\Modules
C:\Program Files (x86)\Microsoft SQL Server\130\Tools\PowerShell\Modules\
```

<span data-ttu-id="c9a77-143">Первые три пути в списке стандартные.</span><span class="sxs-lookup"><span data-stu-id="c9a77-143">The first three paths in the list are the default.</span></span> <span data-ttu-id="c9a77-144">При установке SQL Server Management Studio был добавлен последний путь.</span><span class="sxs-lookup"><span data-stu-id="c9a77-144">When SQL Server Management Studio was installed, it added the last path.</span></span> <span data-ttu-id="c9a77-145">Для работы автозагрузки модулей файл `MyScriptModule.psm1` должен находиться в папке с именем `MyScriptModule` непосредственно в одном из этих путей.</span><span class="sxs-lookup"><span data-stu-id="c9a77-145">For module autoloading to work, the `MyScriptModule.psm1` file needs to be located in a folder named `MyScriptModule` directly inside one of those paths.</span></span>

<span data-ttu-id="c9a77-146">Не так быстро.</span><span class="sxs-lookup"><span data-stu-id="c9a77-146">Not so fast.</span></span> <span data-ttu-id="c9a77-147">У меня текущий путь пользователя не находится первым в списке.</span><span class="sxs-lookup"><span data-stu-id="c9a77-147">For me, my current user path isn't the first one in the list.</span></span> <span data-ttu-id="c9a77-148">Я почти никогда не использую этот путь, так как вхожу в систему Windows под учетной записью пользователя, отличной от той, которую я использую для запуска PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9a77-148">I almost never use that path since I log into Windows with a different user than the one I use to run PowerShell.</span></span> <span data-ttu-id="c9a77-149">Это означает, что этот путь находится не в моей обычной папке "Документы".</span><span class="sxs-lookup"><span data-stu-id="c9a77-149">That means it's not located in my normal Documents folder.</span></span>

<span data-ttu-id="c9a77-150">**AllUsers** — это второй путь.</span><span class="sxs-lookup"><span data-stu-id="c9a77-150">The second path is the **AllUsers** path.</span></span> <span data-ttu-id="c9a77-151">В этом месте я храню все свои модули.</span><span class="sxs-lookup"><span data-stu-id="c9a77-151">This is the location where I store all of my modules.</span></span>

<span data-ttu-id="c9a77-152">Третий путь находится под `C:\Windows\System32`.</span><span class="sxs-lookup"><span data-stu-id="c9a77-152">The third path is underneath `C:\Windows\System32`.</span></span> <span data-ttu-id="c9a77-153">Хранить модули в этом расположении должна только корпорация Майкрософт, так как оно находится в папке операционных систем.</span><span class="sxs-lookup"><span data-stu-id="c9a77-153">Only Microsoft should be storing modules in that location since it resides within the operating systems folder.</span></span>

<span data-ttu-id="c9a77-154">После того как файл `.PSM1` будет размещен в правильном пути, модуль будет автоматически загружаться при вызове одной из команд.</span><span class="sxs-lookup"><span data-stu-id="c9a77-154">Once the `.PSM1` file is located in the correct path, the module will load automatically when one of its commands is called.</span></span>

## <a name="module-manifests"></a><span data-ttu-id="c9a77-155">Манифесты модулей</span><span class="sxs-lookup"><span data-stu-id="c9a77-155">Module Manifests</span></span>

<span data-ttu-id="c9a77-156">Каждый модуль имеет манифест модуля.</span><span class="sxs-lookup"><span data-stu-id="c9a77-156">All modules should have a module manifest.</span></span> <span data-ttu-id="c9a77-157">Манифест модуля содержит метаданные о вашем модуле.</span><span class="sxs-lookup"><span data-stu-id="c9a77-157">A module manifest contains metadata about your module.</span></span>
<span data-ttu-id="c9a77-158">Расширение файла для файла манифеста модуля — `.PSD1`.</span><span class="sxs-lookup"><span data-stu-id="c9a77-158">The file extension for a module manifest file is `.PSD1`.</span></span> <span data-ttu-id="c9a77-159">Не все файлы с расширением `.PSD1` являются манифестами модулей.</span><span class="sxs-lookup"><span data-stu-id="c9a77-159">Not all files with a `.PSD1` extension are module manifests.</span></span> <span data-ttu-id="c9a77-160">Кроме того, их можно использовать для хранения части среды конфигурации DSC.</span><span class="sxs-lookup"><span data-stu-id="c9a77-160">They can also be used for things such as storing the environmental portion of a DSC configuration.</span></span> <span data-ttu-id="c9a77-161">`New-ModuleManifest` используется для создания манифеста модуля.</span><span class="sxs-lookup"><span data-stu-id="c9a77-161">`New-ModuleManifest` is used to create a module manifest.</span></span> <span data-ttu-id="c9a77-162">**Path** — единственное значение, которое необходимо указать.</span><span class="sxs-lookup"><span data-stu-id="c9a77-162">**Path** is the only value that's required.</span></span> <span data-ttu-id="c9a77-163">При этом модуль не будет работать, если не указан параметр **RootModule**.</span><span class="sxs-lookup"><span data-stu-id="c9a77-163">However, the module won't work if **RootModule** isn't specified.</span></span> <span data-ttu-id="c9a77-164">Лучше указать параметры **Author** и **Description** на тот случай, если вы решите передать модуль в репозиторий NuGet с помощью PowerShellGet, так как эти значения необходимо указать в приведенном сценарии.</span><span class="sxs-lookup"><span data-stu-id="c9a77-164">It's a good idea to specify **Author** and **Description** in case you decide to upload your module to a NuGet repository with PowerShellGet since those values are required in that scenario.</span></span>

<span data-ttu-id="c9a77-165">Версия модуля без манифеста — 0.0.</span><span class="sxs-lookup"><span data-stu-id="c9a77-165">The version of a module without a manifest is 0.0.</span></span> <span data-ttu-id="c9a77-166">Это явное доказательство того, что модуль не имеет манифеста.</span><span class="sxs-lookup"><span data-stu-id="c9a77-166">This is a dead giveaway that the module doesn't have a manifest.</span></span>

```powershell
Get-Module -Name MyScriptModule
```

```Output
ModuleType Version    Name                                ExportedCommands
---------- -------    ----                                ----------------
Script     0.0        myscriptmodule                      {Get-MrComputerName, Get-MrP...
```

<span data-ttu-id="c9a77-167">Манифест модуля можно создать с помощью всех рекомендуемых данных.</span><span class="sxs-lookup"><span data-stu-id="c9a77-167">The module manifest can be created with all of the recommended information.</span></span>

```powershell
New-ModuleManifest -Path $env:ProgramFiles\WindowsPowerShell\Modules\MyScriptModule\MyScriptModule.psd1 -RootModule MyScriptModule -Author 'Mike F Robbins' -Description 'MyScriptModule' -CompanyName 'mikefrobbins.com'
```

<span data-ttu-id="c9a77-168">Если во время первоначального создания манифеста модуля какие-либо данные отсутствуют, их можно добавить или обновить позже с помощью `Update-ModuleManifest`.</span><span class="sxs-lookup"><span data-stu-id="c9a77-168">If any of this information is missed during the initial creation of the module manifest, it can be added or updated later using `Update-ModuleManifest`.</span></span> <span data-ttu-id="c9a77-169">Не создавайте манифест повторно с помощью `New-ModuleManifest` после того, как он уже создан, так как в этом случае изменится идентификатор GUID.</span><span class="sxs-lookup"><span data-stu-id="c9a77-169">Don't recreate the manifest using `New-ModuleManifest` once it's already created because the GUID will change.</span></span>

## <a name="defining-public-and-private-functions"></a><span data-ttu-id="c9a77-170">Определение общих и частных функций</span><span class="sxs-lookup"><span data-stu-id="c9a77-170">Defining Public and Private Functions</span></span>

<span data-ttu-id="c9a77-171">Возможно, у вас есть вспомогательные функции, которые вы хотите сделать частными и доступными только для других функций в модуле.</span><span class="sxs-lookup"><span data-stu-id="c9a77-171">You may have helper functions that you may want to be private and only accessible by other functions within the module.</span></span> <span data-ttu-id="c9a77-172">Вспомогательные функции не предназначены для доступа пользователям вашего модуля.</span><span class="sxs-lookup"><span data-stu-id="c9a77-172">They are not intended to be accessible to users of your module.</span></span> <span data-ttu-id="c9a77-173">Это можно сделать двумя способами.</span><span class="sxs-lookup"><span data-stu-id="c9a77-173">There are a couple of different ways to accomplish this.</span></span>

<span data-ttu-id="c9a77-174">Если вы не следуете рекомендациям и у вас есть только файл `.PSM1`, единственный вариант для вас — использовать командлет `Export-ModuleMember`.</span><span class="sxs-lookup"><span data-stu-id="c9a77-174">If you're not following the best practices and only have a `.PSM1` file, then your only option is to use the `Export-ModuleMember` cmdlet.</span></span>

```powershell
function Get-MrPSVersion {
    $PSVersionTable
}

function Get-MrComputerName {
    $env:COMPUTERNAME
}

Export-ModuleMember -Function Get-MrPSVersion
```

<span data-ttu-id="c9a77-175">В предыдущем примере для пользователей модуля доступна только функция `Get-MrPSVersion`, при этом функция `Get-MrComputerName` доступна для других функций в самом модуле.</span><span class="sxs-lookup"><span data-stu-id="c9a77-175">In the previous example, only the `Get-MrPSVersion` function is available to the users of your module, but the `Get-MrComputerName` function is available to other functions within the module itself.</span></span>

```powershell
Get-Command -Module MyScriptModule

CommandType     Name                        Version    Source
-----------     ----                        -------    ------
Function        Get-MrPSVersion             1.0        MyScript...
```

<span data-ttu-id="c9a77-176">Если вы добавили в модуль манифест модуля (а это необходимо), советую указать отдельные функции, которые вам нужно экспортировать, в раздел **FunctionsToExport** манифеста модуля.</span><span class="sxs-lookup"><span data-stu-id="c9a77-176">If you've added a module manifest to your module (and you should), then I recommend specifying the individual functions you want to export in the **FunctionsToExport** section of the module manifest.</span></span>

```powershell
FunctionsToExport = 'Get-MrPSVersion'
```

<span data-ttu-id="c9a77-177">Нет необходимости использовать оба `Export-ModuleMember` в файле `.PSM1` и в разделе **FunctionsToExport** манифеста модуля.</span><span class="sxs-lookup"><span data-stu-id="c9a77-177">It's not necessary to use both `Export-ModuleMember` in the `.PSM1` file and the **FunctionsToExport** section of the module manifest.</span></span> <span data-ttu-id="c9a77-178">Достаточно использовать один из них.</span><span class="sxs-lookup"><span data-stu-id="c9a77-178">One or the other is sufficient.</span></span>

## <a name="summary"></a><span data-ttu-id="c9a77-179">Сводка</span><span class="sxs-lookup"><span data-stu-id="c9a77-179">Summary</span></span>

<span data-ttu-id="c9a77-180">В этой главе вы узнали, как преобразовать функции в модуль скрипта в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9a77-180">In this chapter you've learned how to turn your functions into a script module in PowerShell.</span></span> <span data-ttu-id="c9a77-181">Кроме того, вы рассмотрели некоторые рекомендации по созданию модулей скриптов, например создание манифеста модуля для модуля скрипта.</span><span class="sxs-lookup"><span data-stu-id="c9a77-181">You've also leaned some of the best practices for creating script modules such as creating a module manifest for your script module.</span></span>

## <a name="review"></a><span data-ttu-id="c9a77-182">Просмотр</span><span class="sxs-lookup"><span data-stu-id="c9a77-182">Review</span></span>

1. <span data-ttu-id="c9a77-183">Как создать модуль скрипта в PowerShell?</span><span class="sxs-lookup"><span data-stu-id="c9a77-183">How do you create a script module in PowerShell?</span></span>
1. <span data-ttu-id="c9a77-184">Почему для ваших функций важно использовать утвержденную команду?</span><span class="sxs-lookup"><span data-stu-id="c9a77-184">Why is it important for your functions to use an approved verb?</span></span>
1. <span data-ttu-id="c9a77-185">Как создать манифест модуля в PowerShell?</span><span class="sxs-lookup"><span data-stu-id="c9a77-185">How do you create a module manifest in PowerShell?</span></span>
1. <span data-ttu-id="c9a77-186">С помощью каких двух способов экспортируются только определенные функции из модуля?</span><span class="sxs-lookup"><span data-stu-id="c9a77-186">What are the two options for exporting only certain functions from your module?</span></span>
1. <span data-ttu-id="c9a77-187">Что требуется для автоматической загрузки модулей при вызове команды?</span><span class="sxs-lookup"><span data-stu-id="c9a77-187">What is required for your modules to load automatically when a command is called?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="c9a77-188">Рекомендуем прочесть</span><span class="sxs-lookup"><span data-stu-id="c9a77-188">Recommended Reading</span></span>

- <span data-ttu-id="c9a77-189">[Как создать модули скриптов PowerShell и манифесты модулей][]</span><span class="sxs-lookup"><span data-stu-id="c9a77-189">[How to Create PowerShell Script Modules and Module Manifests][]</span></span>
- <span data-ttu-id="c9a77-190">[about_Modules][]</span><span class="sxs-lookup"><span data-stu-id="c9a77-190">[about_Modules][]</span></span>
- <span data-ttu-id="c9a77-191">[New-ModuleManifest][]</span><span class="sxs-lookup"><span data-stu-id="c9a77-191">[New-ModuleManifest][]</span></span>
- <span data-ttu-id="c9a77-192">[Export-ModuleMember][]</span><span class="sxs-lookup"><span data-stu-id="c9a77-192">[Export-ModuleMember][]</span></span>

<!-- link references -->
[Как создать модули скриптов PowerShell и манифесты модулей]: https://mikefrobbins.com/2013/07/04/how-to-create-powershell-script-modules-and-module-manifests/
[How to Create PowerShell Script Modules and Module Manifests]: https://mikefrobbins.com/2013/07/04/how-to-create-powershell-script-modules-and-module-manifests/
[about_Modules]: /powershell/module/microsoft.powershell.core/about/about_modules
[New-ModuleManifest]: /powershell/module/microsoft.powershell.core/new-modulemanifest
[Export-ModuleMember]: /powershell/module/microsoft.powershell.core/export-modulemember
