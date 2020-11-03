---
description: Описывает, как PowerShell определяет, какую команду выполнить.
keywords: powershell,командлет
ms.date: 02/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_command_precedence?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Command_Precedence
ms.openlocfilehash: 19545a8e456d83e447873535746cdf4efccd80bb
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231038"
---
# <a name="about-command-precedence"></a><span data-ttu-id="afb0f-104">О приоритете команд</span><span class="sxs-lookup"><span data-stu-id="afb0f-104">About Command Precedence</span></span>

## <a name="short-description"></a><span data-ttu-id="afb0f-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="afb0f-105">Short description</span></span>
<span data-ttu-id="afb0f-106">Описывает, как PowerShell определяет, какую команду выполнить.</span><span class="sxs-lookup"><span data-stu-id="afb0f-106">Describes how PowerShell determines which command to run.</span></span>

## <a name="long-description"></a><span data-ttu-id="afb0f-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="afb0f-107">Long description</span></span>

<span data-ttu-id="afb0f-108">Очередность команд. описывает, как PowerShell определяет, какую команду запускать, если сеанс содержит несколько команд с одним и тем же именем.</span><span class="sxs-lookup"><span data-stu-id="afb0f-108">Command precedence describes how PowerShell determines which command to run when a session contains more than one command with the same name.</span></span> <span data-ttu-id="afb0f-109">Команды в сеансе могут быть скрыты или заменены командами с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="afb0f-109">Commands within a session can be hidden or replaced by commands with the same name.</span></span> <span data-ttu-id="afb0f-110">В этой статье показано, как выполнить скрытые команды и избежать конфликтов имен команд.</span><span class="sxs-lookup"><span data-stu-id="afb0f-110">This article shows you how to run hidden commands and how to avoid command-name conflicts.</span></span>

## <a name="command-precedence"></a><span data-ttu-id="afb0f-111">Очередность команд</span><span class="sxs-lookup"><span data-stu-id="afb0f-111">Command precedence</span></span>

<span data-ttu-id="afb0f-112">Если сеанс PowerShell содержит несколько команд с одинаковыми именами, то PowerShell определяет, какую команду выполнить, используя следующие правила.</span><span class="sxs-lookup"><span data-stu-id="afb0f-112">When a PowerShell session includes more than one command that has the same name, PowerShell determines which command to run by using the following rules.</span></span>

<span data-ttu-id="afb0f-113">Если указать путь к команде, PowerShell выполняет команду в расположении, указанном в пути.</span><span class="sxs-lookup"><span data-stu-id="afb0f-113">If you specify the path to a command, PowerShell runs the command at the location specified by the path.</span></span>

<span data-ttu-id="afb0f-114">Например, следующая команда запускает скрипт FindDocs.ps1 в каталоге C: \\ течдокс:</span><span class="sxs-lookup"><span data-stu-id="afb0f-114">For example, the following command runs the FindDocs.ps1 script in the "C:\\TechDocs" directory:</span></span>

```
C:\TechDocs\FindDocs.ps1
```

<span data-ttu-id="afb0f-115">В качестве функции безопасности PowerShell не выполняет исполняемые (собственные) команды, включая сценарии PowerShell, если команда не находится в пути, указанном в переменной среды PATH, `$env:path` или если не указан путь к файлу скрипта.</span><span class="sxs-lookup"><span data-stu-id="afb0f-115">As a security feature, PowerShell does not run executable (native) commands, including PowerShell scripts, unless the command is located in a path that is listed in the Path environment variable `$env:path` or unless you specify the path to the script file.</span></span>

<span data-ttu-id="afb0f-116">Чтобы выполнить скрипт, накоторый находится в текущем каталоге, укажите полный путь или введите точку, `.\` представляющую текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="afb0f-116">To run a script that is in the current directory, specify the full path, or type a dot `.\` to represent the current directory.</span></span>

<span data-ttu-id="afb0f-117">Например, чтобы запустить файл FindDocs.ps1 в текущем каталоге, введите:</span><span class="sxs-lookup"><span data-stu-id="afb0f-117">For example, to run the FindDocs.ps1 file in the current directory, type:</span></span>

```
.\FindDocs.ps1
```

### <a name="using-wildcards-in-execution"></a><span data-ttu-id="afb0f-118">Использование подстановочных знаков при выполнении</span><span class="sxs-lookup"><span data-stu-id="afb0f-118">Using wildcards in execution</span></span>

<span data-ttu-id="afb0f-119">При выполнении команды можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="afb0f-119">You may use wildcards in command execution.</span></span> <span data-ttu-id="afb0f-120">Использование подстановочных знаков также называется *глобализации*.</span><span class="sxs-lookup"><span data-stu-id="afb0f-120">Using wildcard characters is also known as *globbing*.</span></span>

<span data-ttu-id="afb0f-121">PowerShell выполняет файл с подстановочным знаком, перед совпадением литерала.</span><span class="sxs-lookup"><span data-stu-id="afb0f-121">PowerShell executes a file that has a wildcard match, before a literal match.</span></span>

<span data-ttu-id="afb0f-122">Например, рассмотрим каталог со следующими файлами:</span><span class="sxs-lookup"><span data-stu-id="afb0f-122">For example, consider a directory with the following files:</span></span>

```
Get-ChildItem C:\temp\test


    Directory: C:\temp\test


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        5/20/2019   2:29 PM             28 a.ps1
-a----        5/20/2019   2:29 PM             28 [a1].ps1
```

<span data-ttu-id="afb0f-123">Оба файла скрипта имеют одинаковое содержимое: `$MyInvocation.MyCommand.Path` .</span><span class="sxs-lookup"><span data-stu-id="afb0f-123">Both script files have the same content: `$MyInvocation.MyCommand.Path`.</span></span>
<span data-ttu-id="afb0f-124">Эта команда отображает имя вызываемого скрипта.</span><span class="sxs-lookup"><span data-stu-id="afb0f-124">This command displays the name of the script that is invoked.</span></span>

<span data-ttu-id="afb0f-125">При запуске `[a1].ps1` файл `a.ps1` выполняется, даже если он `[a1].ps1` совпадает с литералом.</span><span class="sxs-lookup"><span data-stu-id="afb0f-125">When you run `[a1].ps1`, the file `a.ps1` is executed even though the file `[a1].ps1` is a literal match.</span></span>

```powershell
C:\temp\test\[a1].ps1
```

```Output
C:\temp\test\a.ps1
```

<span data-ttu-id="afb0f-126">Теперь попробуем удалить `a.ps1` файл и попытаться запустить его снова.</span><span class="sxs-lookup"><span data-stu-id="afb0f-126">Now let's delete the `a.ps1` file and attempt to run it again.</span></span>

```powershell
Remove-Item C:\temp\test\a.ps1
C:\temp\test\[a1].ps1
```

```Output
C:\temp\test\[a1].ps1
```

<span data-ttu-id="afb0f-127">Из выходных данных, которые выполняются в данный момент, можно увидеть, что `[a1].ps1` литеральное совпадение является единственным файлом, соответствующим шаблону шаблона.</span><span class="sxs-lookup"><span data-stu-id="afb0f-127">You can see from the output that `[a1].ps1` runs this time because the literal match is the only file match for that wildcard pattern.</span></span>

<span data-ttu-id="afb0f-128">Дополнительные сведения об использовании подстановочных знаков в PowerShell см. в разделе [about_Wildcards](about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="afb0f-128">For more information about how PowerShell uses wildcards, see [about_Wildcards](about_Wildcards.md).</span></span>

> [!NOTE]
> <span data-ttu-id="afb0f-129">Чтобы ограничить поиск относительным путем, необходимо добавить перед именем скрипта `.\` путь.</span><span class="sxs-lookup"><span data-stu-id="afb0f-129">To limit the search to a relative path, you must prefix the script name with the `.\` path.</span></span> <span data-ttu-id="afb0f-130">Это ограничивает поиск команд файлами по этому относительному пути.</span><span class="sxs-lookup"><span data-stu-id="afb0f-130">This limits the search for commands to files in that relative path.</span></span> <span data-ttu-id="afb0f-131">Без этого префикса другой синтаксис PowerShell может конфликтовать, и существует несколько гарантий, что файл будет найден.</span><span class="sxs-lookup"><span data-stu-id="afb0f-131">Without this prefix, other PowerShell syntax may conflict and there are few guarantees that the file will be found.</span></span>

<span data-ttu-id="afb0f-132">Если путь не указан, PowerShell использует следующий порядок очередности при выполнении команд для всех элементов, загруженных в текущем сеансе:</span><span class="sxs-lookup"><span data-stu-id="afb0f-132">If you do not specify a path, PowerShell uses the following precedence order when it runs commands for all items loaded in the current session:</span></span>

  1. <span data-ttu-id="afb0f-133">Псевдоним</span><span class="sxs-lookup"><span data-stu-id="afb0f-133">Alias</span></span>
  2. <span data-ttu-id="afb0f-134">Компонент</span><span class="sxs-lookup"><span data-stu-id="afb0f-134">Function</span></span>
  3. <span data-ttu-id="afb0f-135">Командлет</span><span class="sxs-lookup"><span data-stu-id="afb0f-135">Cmdlet</span></span>
  4. <span data-ttu-id="afb0f-136">Внешние исполняемые файлы (программы и сценарии, не связанные с PowerShell)</span><span class="sxs-lookup"><span data-stu-id="afb0f-136">External executable files (programs and non-PowerShell scripts)</span></span>

<span data-ttu-id="afb0f-137">Поэтому, если ввести "Help", PowerShell сначала ищет псевдоним с именем `help` , затем функцию с именем `Help` и, наконец, командлет с именем `Help` .</span><span class="sxs-lookup"><span data-stu-id="afb0f-137">Therefore, if you type "help", PowerShell first looks for an alias named `help`, then a function named `Help`, and finally a cmdlet named `Help`.</span></span> <span data-ttu-id="afb0f-138">Он запускает первый `help` найденный элемент.</span><span class="sxs-lookup"><span data-stu-id="afb0f-138">It runs the first `help` item that it finds.</span></span>

<span data-ttu-id="afb0f-139">Например, если сеанс содержит командлет и функцию с именем, то `Get-Map` при вводе `Get-Map` PowerShell выполняет функцию.</span><span class="sxs-lookup"><span data-stu-id="afb0f-139">For example, if your session contains a cmdlet and a function, both named `Get-Map`, when you type `Get-Map`, PowerShell runs the function.</span></span>

> [!NOTE]
> <span data-ttu-id="afb0f-140">Это относится только к загруженным командам.</span><span class="sxs-lookup"><span data-stu-id="afb0f-140">This only applies to loaded commands.</span></span> <span data-ttu-id="afb0f-141">При наличии `build` исполняемого файла и псевдонима `build` для функции с именем `Invoke-Build` внутри модуля, который не был загружен в текущий сеанс, PowerShell запускает `build` исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="afb0f-141">If there is a `build` executable and an Alias `build` for a function with the name of `Invoke-Build` inside a module that is not loaded into the current session, PowerShell runs the `build` executable instead.</span></span> <span data-ttu-id="afb0f-142">Он не выполняет автоматическую загрузку модулей, если в данном случае обнаруживает внешний исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="afb0f-142">It does not auto-load modules if it finds the external executable in this case.</span></span> <span data-ttu-id="afb0f-143">Это происходит только в том случае, если не найдены внешние исполняемые файлы, которые вызываются псевдонимом, функцией или командлетом с заданным именем. Таким образом запускается автоматическая загрузка модуля.</span><span class="sxs-lookup"><span data-stu-id="afb0f-143">It is only when no external executable is found that an alias, function, or cmdlet with the given name is invoked, thereby triggering auto-loading of its module.</span></span>

<span data-ttu-id="afb0f-144">Если в сеансе содержатся элементы одного типа с одинаковым именем, PowerShell запускает новый элемент.</span><span class="sxs-lookup"><span data-stu-id="afb0f-144">When the session contains items of the same type that have the same name, PowerShell runs the newer item.</span></span>

<span data-ttu-id="afb0f-145">Например, при импорте другого `Get-Date` командлета из модуля при вводе `Get-Date` PowerShell выполняет импортированную версию по собственному каналу.</span><span class="sxs-lookup"><span data-stu-id="afb0f-145">For example, if you import another `Get-Date` cmdlet from a module, when you type `Get-Date`, PowerShell runs the imported version over the native one.</span></span>

## <a name="hidden-and-replaced-items"></a><span data-ttu-id="afb0f-146">Скрытые и замененные элементы</span><span class="sxs-lookup"><span data-stu-id="afb0f-146">Hidden and replaced items</span></span>

<span data-ttu-id="afb0f-147">В результате этих правил элементы могут быть заменены или скрыты элементами с одинаковыми именами.</span><span class="sxs-lookup"><span data-stu-id="afb0f-147">As a result of these rules, items can be replaced or hidden by items with the same name.</span></span>

<span data-ttu-id="afb0f-148">Элементы скрыты или затенены, если доступ к исходному элементу по-прежнему возможен, например, с помощью имени модуля или оснастки.</span><span class="sxs-lookup"><span data-stu-id="afb0f-148">Items are "hidden" or "shadowed" if you can still access the original item, such as by qualifying the item name with a module or snap-in name.</span></span>

<span data-ttu-id="afb0f-149">Например, при импорте функции, которая имеет то же имя, что и командлет в сеансе, этот командлет скрыт (но не заменяется), так как он был импортирован из оснастки или модуля.</span><span class="sxs-lookup"><span data-stu-id="afb0f-149">For example, if you import a function that has the same name as a cmdlet in the session, the cmdlet is hidden (but not replaced) because it was imported from a snap-in or module.</span></span>

<span data-ttu-id="afb0f-150">Элементы заменяются или перезаписываются, если доступ к исходному элементу больше невозможен.</span><span class="sxs-lookup"><span data-stu-id="afb0f-150">Items are "replaced" or "overwritten" if you can no longer access the original item.</span></span>

<span data-ttu-id="afb0f-151">Например, при импорте переменной, имя которой совпадает с именем переменной в сеансе, исходная переменная заменяется и становится недоступной.</span><span class="sxs-lookup"><span data-stu-id="afb0f-151">For example, if you import a variable that has the same name as a variable in the session, the original variable is replaced and is no longer accessible.</span></span>
<span data-ttu-id="afb0f-152">Нельзя определить переменную с именем модуля.</span><span class="sxs-lookup"><span data-stu-id="afb0f-152">You cannot qualify a variable with a module name.</span></span>

<span data-ttu-id="afb0f-153">Кроме того, если ввести функцию в командной строке и затем импортировать функцию с тем же именем, исходная функция будет заменена и больше недоступна.</span><span class="sxs-lookup"><span data-stu-id="afb0f-153">Also, if you type a function at the command line and then import a function with the same name, the original function is replaced and is no longer accessible.</span></span>

### <a name="finding-hidden-commands"></a><span data-ttu-id="afb0f-154">Поиск скрытых команд</span><span class="sxs-lookup"><span data-stu-id="afb0f-154">Finding hidden commands</span></span>

<span data-ttu-id="afb0f-155">Параметр **ALL** командлета [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command) получает все команды с указанным именем, даже если они скрыты или заменены.</span><span class="sxs-lookup"><span data-stu-id="afb0f-155">The **All** parameter of the [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command) cmdlet gets all commands with the specified name, even if they are hidden or replaced.</span></span> <span data-ttu-id="afb0f-156">Начиная с PowerShell 3,0, по умолчанию `Get-Command` получает только команды, которые выполняются при вводе имени команды.</span><span class="sxs-lookup"><span data-stu-id="afb0f-156">Beginning in PowerShell 3.0, by default, `Get-Command` gets only the commands that run when you type the command name.</span></span>

<span data-ttu-id="afb0f-157">В следующих примерах сеанс включает `Get-Date` функцию и командлет [Get-Date](xref:Microsoft.PowerShell.Utility.Get-Date) .</span><span class="sxs-lookup"><span data-stu-id="afb0f-157">In the following examples, the session includes a `Get-Date` function and a [Get-Date](xref:Microsoft.PowerShell.Utility.Get-Date) cmdlet.</span></span>

<span data-ttu-id="afb0f-158">Следующая команда возвращает `Get-Date` команду, которая выполняется при вводе `Get-Date` .</span><span class="sxs-lookup"><span data-stu-id="afb0f-158">The following command gets the `Get-Date` command that runs when you type `Get-Date`.</span></span>

```powershell
Get-Command Get-Date
```

```output
CommandType     Name                      ModuleName
-----------     ----                      ----------
Function        Get-Date
```

<span data-ttu-id="afb0f-159">Следующая команда использует параметр **ALL** для получения всех `Get-Date` команд.</span><span class="sxs-lookup"><span data-stu-id="afb0f-159">The following command uses the **All** parameter to get all `Get-Date` commands.</span></span>

```powershell
Get-Command Get-Date -All
```

```output
CommandType     Name                      ModuleName
-----------     ----                      ----------
Function        Get-Date
Cmdlet          Get-Date                  Microsoft.PowerShell.Utility
```

### <a name="running-hidden-commands"></a><span data-ttu-id="afb0f-160">Выполнение скрытых команд</span><span class="sxs-lookup"><span data-stu-id="afb0f-160">Running hidden commands</span></span>

<span data-ttu-id="afb0f-161">Вы можете выполнять определенные команды, указывая свойства элементов, которые отличают команду от других команд, которые могут иметь одно и то же имя.</span><span class="sxs-lookup"><span data-stu-id="afb0f-161">You can run particular commands by specifying item properties that distinguish the command from other commands that might have the same name.</span></span> <span data-ttu-id="afb0f-162">Этот метод можно использовать для выполнения любой команды, но он особенно полезен для выполнения скрытых команд.</span><span class="sxs-lookup"><span data-stu-id="afb0f-162">You can use this method to run any command, but it is especially useful for running hidden commands.</span></span>

#### <a name="qualified-names"></a><span data-ttu-id="afb0f-163">Полные имена</span><span class="sxs-lookup"><span data-stu-id="afb0f-163">Qualified names</span></span>

<span data-ttu-id="afb0f-164">Использование имени командлета с указанием модуля позволяет выполнять команды, скрытые элементом с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="afb0f-164">Using the module-qualified name of a cmdlet allows you to run commands hidden by an item with the same name.</span></span> <span data-ttu-id="afb0f-165">Например, можно выполнить `Get-Date` командлет, указав его имя модуля **Microsoft. PowerShell. Utility**.</span><span class="sxs-lookup"><span data-stu-id="afb0f-165">For example, you can run the `Get-Date` cmdlet by qualifying it with its module name **Microsoft.PowerShell.Utility**.</span></span>

<span data-ttu-id="afb0f-166">Используйте этот предпочтительный метод при написании сценариев, которые планируется распространить.</span><span class="sxs-lookup"><span data-stu-id="afb0f-166">Use this preferred method when writing scripts that you intend to distribute.</span></span> <span data-ttu-id="afb0f-167">Нельзя предсказать, какие команды могут присутствовать в сеансе, в котором выполняется скрипт.</span><span class="sxs-lookup"><span data-stu-id="afb0f-167">You cannot predict which commands might be present in the session in which the script runs.</span></span>

```powershell
New-Alias -Name "Get-Date" -Value "Get-ChildItem"
Microsoft.PowerShell.Utility\Get-Date
```

```output
Tuesday, September 4, 2018 8:17:25 AM
```

<span data-ttu-id="afb0f-168">Чтобы выполнить `New-Map` команду, добавленную `MapFunctions` модулем, используйте полное имя модуля:</span><span class="sxs-lookup"><span data-stu-id="afb0f-168">To run a `New-Map` command that was added by the `MapFunctions` module, use its module-qualified name:</span></span>

```powershell
MapFunctions\New-Map
```

<span data-ttu-id="afb0f-169">Чтобы найти модуль, из которого была импортирована команда, используйте свойство **ModuleName** команд.</span><span class="sxs-lookup"><span data-stu-id="afb0f-169">To find the module from which a command was imported, use the **ModuleName** property of commands.</span></span>

```
(Get-Command <command-name>).ModuleName
```

<span data-ttu-id="afb0f-170">Например, чтобы найти источник `Get-Date` командлета, введите:</span><span class="sxs-lookup"><span data-stu-id="afb0f-170">For example, to find the source of the `Get-Date` cmdlet, type:</span></span>

```powershell
(Get-Command Get-Date).ModuleName
```

```output
Microsoft.PowerShell.Utility
```

> [!NOTE]
> <span data-ttu-id="afb0f-171">Нельзя указывать переменные или псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="afb0f-171">You cannot qualify variables or aliases.</span></span>

#### <a name="call-operator"></a><span data-ttu-id="afb0f-172">Оператор Call</span><span class="sxs-lookup"><span data-stu-id="afb0f-172">Call operator</span></span>

<span data-ttu-id="afb0f-173">Можно также использовать `Call` оператор `&` для выполнения скрытых команд, объединив его с вызовом [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) (псевдоним — "Dir") `Get-Command` или [Get-Module](xref:Microsoft.PowerShell.Core.Get-Module).</span><span class="sxs-lookup"><span data-stu-id="afb0f-173">You can also use the `Call` operator `&` to run hidden commands by combining it with a call to [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) (the alias is "dir"), `Get-Command` or [Get-Module](xref:Microsoft.PowerShell.Core.Get-Module).</span></span>

<span data-ttu-id="afb0f-174">Оператор Call выполняет строки и блоки скриптов в дочерней области.</span><span class="sxs-lookup"><span data-stu-id="afb0f-174">The call operator executes strings and script blocks in a child scope.</span></span> <span data-ttu-id="afb0f-175">Дополнительные сведения см. в разделе [about_Operators](about_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="afb0f-175">For more information, see [about_Operators](about_Operators.md).</span></span>

<span data-ttu-id="afb0f-176">Например, если имеется функция с именем `Map` , которая скрыта псевдонимом с именем `Map` , используйте следующую команду для запуска функции.</span><span class="sxs-lookup"><span data-stu-id="afb0f-176">For example, if you have a function named `Map` that is hidden by an alias named `Map`, use the following command to run the function.</span></span>

```powershell
&(Get-Command -Name Map -CommandType Function)
```

<span data-ttu-id="afb0f-177">or</span><span class="sxs-lookup"><span data-stu-id="afb0f-177">or</span></span>

```powershell
&(dir Function:\map)
```

<span data-ttu-id="afb0f-178">Можно также сохранить скрытую команду в переменной, чтобы упростить ее выполнение.</span><span class="sxs-lookup"><span data-stu-id="afb0f-178">You can also save your hidden command in a variable to make it easier to run.</span></span>

<span data-ttu-id="afb0f-179">Например, следующая команда сохраняет `Map` функцию в `$myMap` переменной, а затем использует `Call` оператор для его запуска.</span><span class="sxs-lookup"><span data-stu-id="afb0f-179">For example, the following command saves the `Map` function in the `$myMap` variable and then uses the `Call` operator to run it.</span></span>

```powershell
$myMap = (Get-Command -Name map -CommandType function)
&($myMap)
```

### <a name="replaced-items"></a><span data-ttu-id="afb0f-180">Замененные элементы</span><span class="sxs-lookup"><span data-stu-id="afb0f-180">Replaced items</span></span>

<span data-ttu-id="afb0f-181">"Замененный" элемент — это тот, к которому вы больше не можете обращаться.</span><span class="sxs-lookup"><span data-stu-id="afb0f-181">A "replaced" item is one that you can no longer access.</span></span> <span data-ttu-id="afb0f-182">Вы можете заменить элементы, импортировав элементы с тем же именем из модуля или оснастки.</span><span class="sxs-lookup"><span data-stu-id="afb0f-182">You can replace items by importing items of the same name from a module or snap-in.</span></span>

<span data-ttu-id="afb0f-183">Например, если вы вводите `Get-Map` функцию в сеансе и импортируете функцию с именем `Get-Map` , она заменяет исходную функцию.</span><span class="sxs-lookup"><span data-stu-id="afb0f-183">For example, if you type a `Get-Map` function in your session, and you import a function called `Get-Map`, it replaces the original function.</span></span> <span data-ttu-id="afb0f-184">Его нельзя получить в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="afb0f-184">You cannot retrieve it in the current session.</span></span>

<span data-ttu-id="afb0f-185">Переменные и псевдонимы не могут быть скрыты, так как для их выполнения нельзя использовать оператор Call или полное имя.</span><span class="sxs-lookup"><span data-stu-id="afb0f-185">Variables and aliases cannot be hidden because you cannot use a call operator or a qualified name to run them.</span></span> <span data-ttu-id="afb0f-186">При импорте переменных и псевдонимов из модуля или оснастки они заменяют переменные в сеансе с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="afb0f-186">When you import variables and aliases from a module or snap-in, they replace variables in the session with the same name.</span></span>

### <a name="avoiding-name-conflicts"></a><span data-ttu-id="afb0f-187">Предотвращение конфликтов имен</span><span class="sxs-lookup"><span data-stu-id="afb0f-187">Avoiding name conflicts</span></span>

<span data-ttu-id="afb0f-188">Лучшим способом управления конфликтами имен команд является их предотвращение.</span><span class="sxs-lookup"><span data-stu-id="afb0f-188">The best way to manage command name conflicts is to prevent them.</span></span> <span data-ttu-id="afb0f-189">При именовании команд используйте уникальное имя.</span><span class="sxs-lookup"><span data-stu-id="afb0f-189">When you name your commands, use a unique name.</span></span> <span data-ttu-id="afb0f-190">Например, добавьте свои инициалы или аббревиатуру названия компании в существительные в командах.</span><span class="sxs-lookup"><span data-stu-id="afb0f-190">For example, add your initials or company name acronym to the nouns in your commands.</span></span>

<span data-ttu-id="afb0f-191">Кроме того, при импорте команд в сеанс из модуля PowerShell или из другого сеанса используйте параметр командлета `Prefix` [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module) или</span><span class="sxs-lookup"><span data-stu-id="afb0f-191">Also, when you import commands into your session from a PowerShell module or from another session, use the `Prefix` parameter of the [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module) or</span></span>

<span data-ttu-id="afb0f-192">Командлет [Import-PSSession](xref:Microsoft.PowerShell.Utility.Import-PSSession) для добавления префикса к существительным в именах команд.</span><span class="sxs-lookup"><span data-stu-id="afb0f-192">[Import-PSSession](xref:Microsoft.PowerShell.Utility.Import-PSSession) cmdlet to add a prefix to the nouns in the names of commands.</span></span>

<span data-ttu-id="afb0f-193">Например, следующая команда позволяет избежать конфликтов с `Get-Date` `Set-Date` командлетами и, которые поставляются с PowerShell при импорте `DateFunctions` модуля.</span><span class="sxs-lookup"><span data-stu-id="afb0f-193">For example, the following command avoids any conflict with the `Get-Date` and `Set-Date` cmdlets that come with PowerShell when you import the `DateFunctions` module.</span></span>

```powershell
Import-Module -Name DateFunctions -Prefix ZZ
```

<span data-ttu-id="afb0f-194">Дополнительные сведения см. в разделе `Import-Module` и `Import-PSSession` ниже.</span><span class="sxs-lookup"><span data-stu-id="afb0f-194">For more information, see `Import-Module` and `Import-PSSession` below.</span></span>

## <a name="see-also"></a><span data-ttu-id="afb0f-195">См. также статью</span><span class="sxs-lookup"><span data-stu-id="afb0f-195">See also</span></span>

- [<span data-ttu-id="afb0f-196">about_Path_Syntax</span><span class="sxs-lookup"><span data-stu-id="afb0f-196">about_Path_Syntax</span></span>](about_Path_Syntax.md)
- [<span data-ttu-id="afb0f-197">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="afb0f-197">about_Aliases</span></span>](about_Aliases.md)
- [<span data-ttu-id="afb0f-198">about_Functions</span><span class="sxs-lookup"><span data-stu-id="afb0f-198">about_Functions</span></span>](about_Functions.md)
- [<span data-ttu-id="afb0f-199">Alias-Provider</span><span class="sxs-lookup"><span data-stu-id="afb0f-199">Alias-Provider</span></span>](../../Microsoft.PowerShell.Core/About/about_Alias_Provider.md)
- [<span data-ttu-id="afb0f-200">Function-Provider</span><span class="sxs-lookup"><span data-stu-id="afb0f-200">Function-Provider</span></span>](../../Microsoft.PowerShell.Core/About/about_Function_Provider.md)
- [<span data-ttu-id="afb0f-201">Get-Command</span><span class="sxs-lookup"><span data-stu-id="afb0f-201">Get-Command</span></span>](xref:Microsoft.PowerShell.Core.Get-Command)
- [<span data-ttu-id="afb0f-202">Import-Module</span><span class="sxs-lookup"><span data-stu-id="afb0f-202">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)
- [<span data-ttu-id="afb0f-203">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="afb0f-203">Import-PSSession</span></span>](xref:Microsoft.PowerShell.Utility.Import-PSSession)
