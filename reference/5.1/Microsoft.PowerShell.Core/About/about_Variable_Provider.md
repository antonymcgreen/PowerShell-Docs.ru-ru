---
description: Переменная
keywords: powershell,командлет
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variable_provider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Variable Provider
ms.openlocfilehash: ff3d457e8d057329544cf1265720fc041a804973
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232277"
---
# <a name="variable-provider"></a><span data-ttu-id="49297-104">Поставщик переменных</span><span class="sxs-lookup"><span data-stu-id="49297-104">Variable provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="49297-105">Имя поставщика</span><span class="sxs-lookup"><span data-stu-id="49297-105">Provider name</span></span>

<span data-ttu-id="49297-106">Переменная</span><span class="sxs-lookup"><span data-stu-id="49297-106">Variable</span></span>

## <a name="drives"></a><span data-ttu-id="49297-107">Диски</span><span class="sxs-lookup"><span data-stu-id="49297-107">Drives</span></span>

`Variable:`

## <a name="capabilities"></a><span data-ttu-id="49297-108">Характеристики</span><span class="sxs-lookup"><span data-stu-id="49297-108">Capabilities</span></span>

<span data-ttu-id="49297-109">**ShouldProcess**</span><span class="sxs-lookup"><span data-stu-id="49297-109">**ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="49297-110">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="49297-110">Short description</span></span>

<span data-ttu-id="49297-111">Предоставляет доступ к переменным PowerShell и их значениям.</span><span class="sxs-lookup"><span data-stu-id="49297-111">Provides access to the PowerShell variables and to their values.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="49297-112">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="49297-112">Detailed description</span></span>

<span data-ttu-id="49297-113">Поставщик **переменных** PowerShell позволяет получать, добавлять, изменять, очищать и удалять переменные PowerShell в текущей консоли.</span><span class="sxs-lookup"><span data-stu-id="49297-113">The PowerShell **Variable** provider lets you get, add, change, clear, and delete PowerShell variables in the current console.</span></span>

<span data-ttu-id="49297-114">Поставщик **переменных** PowerShell поддерживает переменные, создаваемые PowerShell, включая автоматические переменные, переменные предпочтений и создаваемые переменные.</span><span class="sxs-lookup"><span data-stu-id="49297-114">The PowerShell **Variable** provider supports the variables that PowerShell creates, including the automatic variables, the preference variables, and the variables that you create.</span></span>

<span data-ttu-id="49297-115">**Переменная** Drive является плоским пространством имен, которое содержит только объекты переменных.</span><span class="sxs-lookup"><span data-stu-id="49297-115">The **Variable** drive is a flat namespace that contains only the variable objects.</span></span> <span data-ttu-id="49297-116">Переменные не имеют дочерних переменных.</span><span class="sxs-lookup"><span data-stu-id="49297-116">The variables have no child items.</span></span>

<span data-ttu-id="49297-117">Поставщик **переменных** поддерживает следующие командлеты, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="49297-117">The **Variable** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="49297-118">Get-Location</span><span class="sxs-lookup"><span data-stu-id="49297-118">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="49297-119">Set-Location</span><span class="sxs-lookup"><span data-stu-id="49297-119">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="49297-120">Get-Item</span><span class="sxs-lookup"><span data-stu-id="49297-120">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="49297-121">New-Item</span><span class="sxs-lookup"><span data-stu-id="49297-121">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="49297-122">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="49297-122">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="49297-123">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="49297-123">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)

<span data-ttu-id="49297-124">PowerShell также включает набор командлетов, предназначенных специально для просмотра и изменения переменных.</span><span class="sxs-lookup"><span data-stu-id="49297-124">PowerShell also includes a set of cmdlets designed especially to view and to change variables.</span></span> <span data-ttu-id="49297-125">При использовании командлетов **переменных** не нужно указывать `Variable:` диск в имени.</span><span class="sxs-lookup"><span data-stu-id="49297-125">When you use **Variable** cmdlets, you do not need to specify the `Variable:` drive in the name.</span></span> <span data-ttu-id="49297-126">В этой статье не рассматривается работа с командлетами **переменных** .</span><span class="sxs-lookup"><span data-stu-id="49297-126">This article does not cover working with **Variable** cmdlets.</span></span>

- [<span data-ttu-id="49297-127">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="49297-127">Get-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Get-Variable)
- [<span data-ttu-id="49297-128">New-Variable</span><span class="sxs-lookup"><span data-stu-id="49297-128">New-Variable</span></span>](xref:Microsoft.PowerShell.Utility.New-Variable)
- [<span data-ttu-id="49297-129">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="49297-129">Set-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Set-Variable)
- [<span data-ttu-id="49297-130">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="49297-130">Remove-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Remove-Variable)
- [<span data-ttu-id="49297-131">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="49297-131">Clear-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Clear-Variable)

> [!NOTE]
> <span data-ttu-id="49297-132">Средство синтаксического анализа выражений PowerShell также можно использовать для создания, просмотра и изменения значений переменных без использования командлетов.</span><span class="sxs-lookup"><span data-stu-id="49297-132">You can also use the PowerShell expression parser to create, view, and change the values of variables without using the cmdlets.</span></span> <span data-ttu-id="49297-133">При работе с переменными напрямую используйте знак доллара ( `$` ), чтобы определить имя как переменную и оператор присваивания ( `=` ) для установки и изменения его значения.</span><span class="sxs-lookup"><span data-stu-id="49297-133">When working with variables directly, use a dollar sign (`$`) to identify the name as a variable and the assignment operator (`=`)to establish and change its value.</span></span> <span data-ttu-id="49297-134">Например, `$p = Get-Process` создает `p` переменную и сохраняет результаты `Get-Process` команды в ней.</span><span class="sxs-lookup"><span data-stu-id="49297-134">For example, `$p = Get-Process` creates the `p` variable and stores the results of a `Get-Process` command in it.</span></span>

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="49297-135">Типы, предоставляемые этим поставщиком</span><span class="sxs-lookup"><span data-stu-id="49297-135">Types exposed by this provider</span></span>

<span data-ttu-id="49297-136">Переменные могут быть одного из нескольких разных типов.</span><span class="sxs-lookup"><span data-stu-id="49297-136">Variables can be one of several different types.</span></span> <span data-ttu-id="49297-137">Большинство переменных будут экземплярами `PSVariable` класса.</span><span class="sxs-lookup"><span data-stu-id="49297-137">Most variables will be instances of the `PSVariable` class.</span></span> <span data-ttu-id="49297-138">Ниже перечислены другие переменные и их типы.</span><span class="sxs-lookup"><span data-stu-id="49297-138">Other variables and their types are listed below.</span></span>

- <span data-ttu-id="49297-139">`?`Переменная является экземпляром `QuestionMarkVariable` класса.</span><span class="sxs-lookup"><span data-stu-id="49297-139">The `?` variable is an instance of the `QuestionMarkVariable` class.</span></span>
- <span data-ttu-id="49297-140">`null`Переменная является экземпляром `NullVariable` класса.</span><span class="sxs-lookup"><span data-stu-id="49297-140">The `null` variable is an instance of the `NullVariable` class.</span></span>
- <span data-ttu-id="49297-141">Переменные максимального числа — это экземпляры `SessionStateCapacityVariable` класса.</span><span class="sxs-lookup"><span data-stu-id="49297-141">The maximum count variables are instances of the `SessionStateCapacityVariable` class.</span></span>
- <span data-ttu-id="49297-142">`LocalVariable` экземпляры содержат сведения о текущем выполнении, например:</span><span class="sxs-lookup"><span data-stu-id="49297-142">`LocalVariable` instances contain information about current execution, such as:</span></span>
  - `MyInvocation`
  - `PSCommandPath`
  - `PSScriptRoot`
  - `PSBoundParameters`
  - `args`
  - `input`

## <a name="navigating-the-variable-drives"></a><span data-ttu-id="49297-143">Навигация по переменным дискам</span><span class="sxs-lookup"><span data-stu-id="49297-143">Navigating the Variable drives</span></span>

<span data-ttu-id="49297-144">Поставщик **переменных** предоставляет хранилище данных на `Variable:` диске.</span><span class="sxs-lookup"><span data-stu-id="49297-144">The **Variable** provider exposes its data store in the `Variable:` drive.</span></span> <span data-ttu-id="49297-145">Для работы с переменными можно изменить расположение на `Variable:` диск ( `Set-Location Variable:` ) или работать с любого другого диска PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49297-145">To work with variables, you can change your location to the `Variable:` drive (`Set-Location Variable:`), or you can work from any other PowerShell drive.</span></span> <span data-ttu-id="49297-146">Чтобы сослаться на переменную из другого расположения, используйте имя диска ( `Variable:` ) в пути.</span><span class="sxs-lookup"><span data-stu-id="49297-146">To reference a variable from another location, use the drive name (`Variable:`) in the path.</span></span>

```powershell
Set-Location Variable:
```

<span data-ttu-id="49297-147">Чтобы вернуться к диску файловой системы, введите имя диска.</span><span class="sxs-lookup"><span data-stu-id="49297-147">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="49297-148">Например, введите:</span><span class="sxs-lookup"><span data-stu-id="49297-148">For example, type:</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="49297-149">Вы также можете работать с поставщиком **переменных** с любого другого диска PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49297-149">You can also work with the **Variable** provider from any other PowerShell drive.</span></span> <span data-ttu-id="49297-150">Чтобы сослаться на переменную из другого расположения, используйте имя диска `Variable:` в пути.</span><span class="sxs-lookup"><span data-stu-id="49297-150">To reference an variable from another location, use the drive name `Variable:` in the path.</span></span>

> [!NOTE]
> <span data-ttu-id="49297-151">PowerShell использует Псевдонимы для предоставления привычного способа работы с путями поставщика.</span><span class="sxs-lookup"><span data-stu-id="49297-151">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="49297-152">Команды, такие как `dir` и `ls` , теперь являются псевдонимами для [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` являются псевдонимом для [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span><span class="sxs-lookup"><span data-stu-id="49297-152">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span> <span data-ttu-id="49297-153">и `pwd` — это псевдоним для [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span><span class="sxs-lookup"><span data-stu-id="49297-153">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

## <a name="displaying-the-value-of-variables"></a><span data-ttu-id="49297-154">Отображение значения переменных</span><span class="sxs-lookup"><span data-stu-id="49297-154">Displaying the value of variables</span></span>

### <a name="get-all-variables-in-the-current-session"></a><span data-ttu-id="49297-155">Получение всех переменных в текущем сеансе</span><span class="sxs-lookup"><span data-stu-id="49297-155">Get all variables in the current session</span></span>

<span data-ttu-id="49297-156">Эта команда возвращает список всех переменных и их значений в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="49297-156">This command gets the list of all the variables and their values in the current session.</span></span> <span data-ttu-id="49297-157">Эту команду можно использовать на любом диске PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49297-157">You can use this command from any PowerShell drive.</span></span>

```powershell
Get-ChildItem -Path Variable:
```

### <a name="get-a-variable-using-its-provider-path"></a><span data-ttu-id="49297-158">Получение переменной с помощью пути к поставщику</span><span class="sxs-lookup"><span data-stu-id="49297-158">Get a variable using its provider path</span></span>

<span data-ttu-id="49297-159">Эта команда извлекает значение переменных, используя путь к поставщику с префиксом доллара ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="49297-159">This command retrieves a variables value using its provider path prefixed by the dollar sign (`$`).</span></span> <span data-ttu-id="49297-160">Это действует так же, как и префикс имени переменной с символом доллара ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="49297-160">This has the same effect as prefixing the variables name with the dollar sign (`$`).</span></span>

```powershell
$variable:home
```

### <a name="get-variables-using-wildcards"></a><span data-ttu-id="49297-161">Получение переменных с помощью подстановочных знаков</span><span class="sxs-lookup"><span data-stu-id="49297-161">Get variables using wildcards</span></span>

<span data-ttu-id="49297-162">Эта команда возвращает переменные с именами, которые начинаются на "max".</span><span class="sxs-lookup"><span data-stu-id="49297-162">This command gets the variables with names that begin with "max".</span></span> <span data-ttu-id="49297-163">Эту команду можно использовать на любом диске PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49297-163">You can use this command from any PowerShell drive.</span></span>

```powershell
Get-ChildItem -Path Variable:max*
```

### <a name="get-the-value-of-the--variable"></a><span data-ttu-id="49297-164">Получить значение?</span><span class="sxs-lookup"><span data-stu-id="49297-164">Get the value of the ?</span></span> <span data-ttu-id="49297-165">Переменная</span><span class="sxs-lookup"><span data-stu-id="49297-165">variable</span></span>

<span data-ttu-id="49297-166">Эта команда использует `-LiteralPath` параметр командлета [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) для получения значения `?` переменной в пределах `Variable:` диска.</span><span class="sxs-lookup"><span data-stu-id="49297-166">This command uses the `-LiteralPath` parameter of [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) to get the value of the `?` variable from within the `Variable:` drive.</span></span> <span data-ttu-id="49297-167">`?`Является подстановочным знаком в путях, но не `Get-ChildItem` пытается разрешить подстановочные знаки в значениях `-LiteralPath` параметра.</span><span class="sxs-lookup"><span data-stu-id="49297-167">The `?` is a wildcard in paths, but `Get-ChildItem` does not attempt to resolve any wildcards in the values of the `-LiteralPath` parameter.</span></span>

```powershell
Get-ChildItem -Literalpath ?
```

### <a name="get-readonly-and-constant-variables"></a><span data-ttu-id="49297-168">Получить переменные только для чтения и константы</span><span class="sxs-lookup"><span data-stu-id="49297-168">Get ReadOnly and Constant variables</span></span>

<span data-ttu-id="49297-169">Эта команда возвращает переменные, которые имеют значения `ReadOnly` или `Constant` для своего свойства **Options** .</span><span class="sxs-lookup"><span data-stu-id="49297-169">This command gets the variables that have the values of `ReadOnly` or `Constant` for their **Options** property.</span></span>

```powershell
Get-ChildItem -Path Variable: | Where-Object {
   $_.options -Match "Constant" `
   -or $_.options -Match "ReadOnly"
 } | Format-List -Property name, value, options
```

## <a name="creating-variables"></a><span data-ttu-id="49297-170">Создание переменных</span><span class="sxs-lookup"><span data-stu-id="49297-170">Creating variables</span></span>

### <a name="create-a-new-variable"></a><span data-ttu-id="49297-171">Создание новой переменной</span><span class="sxs-lookup"><span data-stu-id="49297-171">Create a new variable</span></span>

<span data-ttu-id="49297-172">Эта команда создает `services` переменную и сохраняет результаты `Get-Service` команды в ней.</span><span class="sxs-lookup"><span data-stu-id="49297-172">This command creates the `services` variable and stores the results of a `Get-Service` command in it.</span></span> <span data-ttu-id="49297-173">Так как текущее расположение находится в `Variable:` диске, значением `-Path` параметра является точка ( `.` ), которая представляет текущее расположение.</span><span class="sxs-lookup"><span data-stu-id="49297-173">Because the current location is in the `Variable:` drive, the value of the `-Path` parameter is a dot (`.`), which represents the current location.</span></span>

<span data-ttu-id="49297-174">Круглые скобки вокруг `Get-Service` команды гарантируют, что команда выполняется перед созданием переменной.</span><span class="sxs-lookup"><span data-stu-id="49297-174">The parentheses around the `Get-Service` command ensure that the command is executed before the variable is created.</span></span> <span data-ttu-id="49297-175">Если круглые скобки отсутствуют, значением новой переменной станет строка "Get-Service".</span><span class="sxs-lookup"><span data-stu-id="49297-175">Without the parentheses, the value of the new variable is a "Get-Service" string.</span></span>

```powershell
New-Item -Path . -Name services -Value (Get-Service)
```

### <a name="create-a-variable-using-an-absolute-path"></a><span data-ttu-id="49297-176">Создание переменной с помощью абсолютного пути</span><span class="sxs-lookup"><span data-stu-id="49297-176">Create a variable using an absolute path</span></span>

<span data-ttu-id="49297-177">Эта команда создает `services` переменную и сохраняет результат `Get-Service` команды в ней.</span><span class="sxs-lookup"><span data-stu-id="49297-177">This command creates a `services` variable and stores the result of a `Get-Service` command in it.</span></span>

```powershell
New-Item -Path Variable:services -Value Get-Service
```

 <span data-ttu-id="49297-178">Чтобы создать переменную без значения, опустите оператор присваивания.</span><span class="sxs-lookup"><span data-stu-id="49297-178">To create a variable without a value, omit the assignment operator.</span></span>

## <a name="changing-variables"></a><span data-ttu-id="49297-179">Изменение переменных</span><span class="sxs-lookup"><span data-stu-id="49297-179">Changing variables</span></span>

### <a name="rename-a-variable"></a><span data-ttu-id="49297-180">Переименование переменной</span><span class="sxs-lookup"><span data-stu-id="49297-180">Rename a variable</span></span>

<span data-ttu-id="49297-181">Эта команда использует `Rename-Item` командлет, чтобы изменить имя `a` переменной на `processes` .</span><span class="sxs-lookup"><span data-stu-id="49297-181">This command uses the `Rename-Item` cmdlet to change the name of the `a` variable to `processes`.</span></span>

```powershell
Rename-Item -Path Variable:a -NewName processes
```

### <a name="change-the-value-of-a-variable"></a><span data-ttu-id="49297-182">Изменение значения переменной</span><span class="sxs-lookup"><span data-stu-id="49297-182">Change the value of a variable</span></span>

<span data-ttu-id="49297-183">Эта команда использует `Set-Item` командлет, чтобы изменить значение `ErrorActionPreference` переменной на "останавливаться".</span><span class="sxs-lookup"><span data-stu-id="49297-183">This command uses the `Set-Item` cmdlet to change the value of the `ErrorActionPreference` variable to "Stop".</span></span>

```powershell
Set-Item -Path Variable:ErrorActionPreference -Value Stop
```

## <a name="copy-a-variable"></a><span data-ttu-id="49297-184">Копирование переменной</span><span class="sxs-lookup"><span data-stu-id="49297-184">Copy a variable</span></span>

<span data-ttu-id="49297-185">Эта команда использует `Copy-Item` командлет, чтобы скопировать `processes` переменную в `old_processes` .</span><span class="sxs-lookup"><span data-stu-id="49297-185">This command uses the `Copy-Item` cmdlet to copy the `processes` variable to `old_processes`.</span></span> <span data-ttu-id="49297-186">При этом создается новая переменная с именем `old_processes` , имеющая то же значение, что и `processes` переменная.</span><span class="sxs-lookup"><span data-stu-id="49297-186">This creates a new variable named `old_processes` that has the same value as the `processes` variable.</span></span>

```powershell
Copy-Item -Path Variable:processes -Destination Variable:old_processes
```

## <a name="delete-a-variable"></a><span data-ttu-id="49297-187">Удаление переменной</span><span class="sxs-lookup"><span data-stu-id="49297-187">Delete a variable</span></span>

<span data-ttu-id="49297-188">Эта команда удаляет `serv` переменную из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="49297-188">This command deletes the `serv` variable from the current session.</span></span> <span data-ttu-id="49297-189">Эту команду можно использовать на любом диске PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49297-189">You can use this command in any PowerShell drive.</span></span>

```powershell
Remove-Variable -Path Variable:serv
```

### <a name="delete-variables-using-the--force-parameter"></a><span data-ttu-id="49297-190">Удаление переменных с помощью параметра-Force</span><span class="sxs-lookup"><span data-stu-id="49297-190">Delete variables using the -Force parameter</span></span>

<span data-ttu-id="49297-191">Эта команда удаляет все переменные из текущего сеанса, за исключением переменных, у которых свойство **Options** имеет значение `Constant` .</span><span class="sxs-lookup"><span data-stu-id="49297-191">This command deletes all variables from the current session except for the variables whose **Options** property has a value of `Constant`.</span></span> <span data-ttu-id="49297-192">Без `-Force` параметра команда не удаляет переменные, у которых свойство **Options** имеет значение `ReadOnly` .</span><span class="sxs-lookup"><span data-stu-id="49297-192">Without the `-Force` parameter, the command does not delete variables whose **Options** property has a value of `ReadOnly`.</span></span>

```powershell
Remove-Item Variable:* -Force
```

## <a name="setting-the-value-of-a-variable-to-null"></a><span data-ttu-id="49297-193">Присвоение переменной значения NULL</span><span class="sxs-lookup"><span data-stu-id="49297-193">Setting the value of a variable to NULL</span></span>

<span data-ttu-id="49297-194">Эта команда использует `Clear-Item` командлет, чтобы изменить значение `processes` переменной на null.</span><span class="sxs-lookup"><span data-stu-id="49297-194">This command uses the `Clear-Item` cmdlet to change the value of the `processes` variable to NULL.</span></span>

```powershell
Clear-Item -Path Variable:processes
```

## <a name="using-the-pipeline"></a><span data-ttu-id="49297-195">Использование конвейера</span><span class="sxs-lookup"><span data-stu-id="49297-195">Using the pipeline</span></span>

<span data-ttu-id="49297-196">Командлеты поставщика принимают входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="49297-196">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="49297-197">Вы можете использовать конвейер для упрощения задачи, отправив данные поставщика из одного командлета другому командлету поставщика.</span><span class="sxs-lookup"><span data-stu-id="49297-197">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="49297-198">Дополнительные сведения об использовании конвейера с командлетами поставщика см. в справочнике по командлетам, приведенным в этой статье.</span><span class="sxs-lookup"><span data-stu-id="49297-198">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="49297-199">Получение справки</span><span class="sxs-lookup"><span data-stu-id="49297-199">Getting help</span></span>

<span data-ttu-id="49297-200">Начиная с Windows PowerShell 3.0, стали доступны настраиваемые разделы справки по командлетам поставщика, в которых объясняется поведение этих командлетов на диске файловой системы.</span><span class="sxs-lookup"><span data-stu-id="49297-200">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="49297-201">Чтобы получить разделы справки, настроенные для диска файловой системы, выполните команду [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) на диске файловой системы или используйте параметр командлета `-Path` [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) , чтобы указать диск файловой системы.</span><span class="sxs-lookup"><span data-stu-id="49297-201">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path variable:
```

## <a name="see-also"></a><span data-ttu-id="49297-202">См. также статью</span><span class="sxs-lookup"><span data-stu-id="49297-202">See also</span></span>

[<span data-ttu-id="49297-203">about_Variables</span><span class="sxs-lookup"><span data-stu-id="49297-203">about_Variables</span></span>](../About/about_Variables.md)

[<span data-ttu-id="49297-204">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="49297-204">about_Automatic_Variables</span></span>](../About/about_Automatic_Variables.md)

[<span data-ttu-id="49297-205">about_Providers</span><span class="sxs-lookup"><span data-stu-id="49297-205">about_Providers</span></span>](../About/about_Providers.md)
