---
description: Описывает, как использовать Сплаттинг для передачи параметров в команды в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 08/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_splatting?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Splatting
ms.openlocfilehash: a64cbbe5edd40bf4fc7f9b7347421988d225e666
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231657"
---
# <a name="about-splatting"></a><span data-ttu-id="22d91-104">О Сплаттинг</span><span class="sxs-lookup"><span data-stu-id="22d91-104">About Splatting</span></span>

## <a name="short-description"></a><span data-ttu-id="22d91-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="22d91-105">Short description</span></span>

<span data-ttu-id="22d91-106">Описывает, как использовать Сплаттинг для передачи параметров в команды в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22d91-106">Describes how to use splatting to pass parameters to commands in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="22d91-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="22d91-107">Long description</span></span>

<span data-ttu-id="22d91-108">Сплаттинг — это метод передачи коллекции значений параметров в команду как единое целое.</span><span class="sxs-lookup"><span data-stu-id="22d91-108">Splatting is a method of passing a collection of parameter values to a command as a unit.</span></span> <span data-ttu-id="22d91-109">PowerShell связывает каждое значение в коллекции с параметром команды.</span><span class="sxs-lookup"><span data-stu-id="22d91-109">PowerShell associates each value in the collection with a command parameter.</span></span> <span data-ttu-id="22d91-110">Значения параметров сплаттед хранятся в именованных переменных Сплаттинг, которые выглядят как стандартные переменные, но начинаются с символа ( `@` ) вместо знака доллара ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="22d91-110">Splatted parameter values are stored in named splatting variables, which look like standard variables, but begin with an At symbol (`@`) instead of a dollar sign (`$`).</span></span> <span data-ttu-id="22d91-111">Символ at указывает PowerShell на передачу коллекции значений, а не одно значение.</span><span class="sxs-lookup"><span data-stu-id="22d91-111">The At symbol tells PowerShell that you are passing a collection of values, instead of a single value.</span></span>

<span data-ttu-id="22d91-112">Сплаттинг делает команды короче и проще в чтении.</span><span class="sxs-lookup"><span data-stu-id="22d91-112">Splatting makes your commands shorter and easier to read.</span></span> <span data-ttu-id="22d91-113">Можно повторно использовать значения сплаттинг в разных вызовах команд и использовать Сплаттинг для передачи значений параметров из `$PSBoundParameters` автоматической переменной в другие скрипты и функции.</span><span class="sxs-lookup"><span data-stu-id="22d91-113">You can reuse the splatting values in different command calls and use splatting to pass parameter values from the `$PSBoundParameters` automatic variable to other scripts and functions.</span></span>

<span data-ttu-id="22d91-114">Начиная с Windows PowerShell 3,0, можно также использовать Сплаттинг для представления всех параметров команды.</span><span class="sxs-lookup"><span data-stu-id="22d91-114">Beginning in Windows PowerShell 3.0, you can also use splatting to represent all parameters of a command.</span></span>

## <a name="syntax"></a><span data-ttu-id="22d91-115">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22d91-115">Syntax</span></span>

```
<CommandName> <optional parameters> @<HashTable> <optional parameters>
<CommandName> <optional parameters> @<Array> <optional parameters>
```

<span data-ttu-id="22d91-116">Чтобы указать значения параметров для параметров позиционирования, в которых не требуются имена параметров, используйте синтаксис массива.</span><span class="sxs-lookup"><span data-stu-id="22d91-116">To provide parameter values for positional parameters, in which parameter names are not required, use the array syntax.</span></span> <span data-ttu-id="22d91-117">Чтобы указать пары имен и значений параметров, используйте синтаксис хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="22d91-117">To provide parameter name and value pairs, use the hash table syntax.</span></span> <span data-ttu-id="22d91-118">Значение сплаттед может находиться в любом месте в списке параметров.</span><span class="sxs-lookup"><span data-stu-id="22d91-118">The splatted value can appear anywhere in the parameter list.</span></span>

<span data-ttu-id="22d91-119">При Сплаттинг не нужно использовать хэш-таблицу или массив для передачи всех параметров.</span><span class="sxs-lookup"><span data-stu-id="22d91-119">When splatting, you do not need to use a hash table or an array to pass all parameters.</span></span> <span data-ttu-id="22d91-120">Некоторые параметры можно передать с помощью Сплаттинг и передать другим по положению или имени параметра.</span><span class="sxs-lookup"><span data-stu-id="22d91-120">You may pass some parameters by using splatting and pass others by position or by parameter name.</span></span> <span data-ttu-id="22d91-121">Кроме того, можно со звездочкой несколько объектов в одной команде, чтобы для каждого параметра не передавалось больше одного значения.</span><span class="sxs-lookup"><span data-stu-id="22d91-121">Also, you can splat multiple objects in a single command so you don't pass more than one value for each parameter.</span></span>

<span data-ttu-id="22d91-122">В PowerShell 7,1 можно переопределить параметр сплаттед, явно определив параметр в команде.</span><span class="sxs-lookup"><span data-stu-id="22d91-122">As of PowerShell 7.1, you can override a splatted parameter by explicitly defining a parameter in a command.</span></span>

## <a name="splatting-with-hash-tables"></a><span data-ttu-id="22d91-123">Сплаттинг с хэш-таблицами</span><span class="sxs-lookup"><span data-stu-id="22d91-123">Splatting with hash tables</span></span>

<span data-ttu-id="22d91-124">Используйте хэш-таблицу для со звездочкой пар имен и значений параметров.</span><span class="sxs-lookup"><span data-stu-id="22d91-124">Use a hash table to splat parameter name and value pairs.</span></span> <span data-ttu-id="22d91-125">Этот формат можно использовать для всех типов параметров, включая параметры позиционирования и переключателя.</span><span class="sxs-lookup"><span data-stu-id="22d91-125">You can use this format for all parameter types, including positional and switch parameters.</span></span>
<span data-ttu-id="22d91-126">Позиционированные параметры должны быть назначены по имени.</span><span class="sxs-lookup"><span data-stu-id="22d91-126">Positional parameters must be assigned by name.</span></span>

<span data-ttu-id="22d91-127">В следующих примерах сравниваются две `Copy-Item` команды, которые копируют файл Test.txt в файл Test2.txt в том же каталоге.</span><span class="sxs-lookup"><span data-stu-id="22d91-127">The following examples compare two `Copy-Item` commands that copy the Test.txt file to the Test2.txt file in the same directory.</span></span>

<span data-ttu-id="22d91-128">В первом примере используется традиционный формат, в котором включены имена параметров.</span><span class="sxs-lookup"><span data-stu-id="22d91-128">The first example uses the traditional format in which parameter names are included.</span></span>

```powershell
Copy-Item -Path "test.txt" -Destination "test2.txt" -WhatIf
```

<span data-ttu-id="22d91-129">Во втором примере используется хэш-таблица Сплаттинг.</span><span class="sxs-lookup"><span data-stu-id="22d91-129">The second example uses hash table splatting.</span></span> <span data-ttu-id="22d91-130">Первая команда создает хэш-таблицу пар "параметр-имя" и "параметр-значение" и сохраняет их в `$HashArguments` переменной.</span><span class="sxs-lookup"><span data-stu-id="22d91-130">The first command creates a hash table of parameter-name and parameter-value pairs and stores it in the `$HashArguments` variable.</span></span> <span data-ttu-id="22d91-131">Вторая команда использует `$HashArguments` переменную в команде с параметром Сплаттинг.</span><span class="sxs-lookup"><span data-stu-id="22d91-131">The second command uses the `$HashArguments` variable in a command with splatting.</span></span> <span data-ttu-id="22d91-132">Символ "at" ( `@HashArguments` ) заменяет знак доллара ( `$HashArguments` ) в команде.</span><span class="sxs-lookup"><span data-stu-id="22d91-132">The At symbol (`@HashArguments`) replaces the dollar sign (`$HashArguments`) in the command.</span></span>

<span data-ttu-id="22d91-133">Чтобы указать значение параметра **WhatIf** , используйте `$True` или `$False` .</span><span class="sxs-lookup"><span data-stu-id="22d91-133">To provide a value for the **WhatIf** switch parameter, use `$True` or `$False`.</span></span>

```powershell
$HashArguments = @{
  Path = "test.txt"
  Destination = "test2.txt"
  WhatIf = $true
}
Copy-Item @HashArguments
```

> [!NOTE]
> <span data-ttu-id="22d91-134">В первой команде символ at ( `@` ) указывает на хэш-таблицу, а не на значение сплаттед.</span><span class="sxs-lookup"><span data-stu-id="22d91-134">In the first command, the At symbol (`@`) indicates a hash table, not a splatted value.</span></span> <span data-ttu-id="22d91-135">Синтаксис для хэш-таблиц в PowerShell: `@{<name>=<value>; <name>=<value>; ...}`</span><span class="sxs-lookup"><span data-stu-id="22d91-135">The syntax for hash tables in PowerShell is: `@{<name>=<value>; <name>=<value>; ...}`</span></span>

## <a name="splatting-with-arrays"></a><span data-ttu-id="22d91-136">Сплаттинг с массивами</span><span class="sxs-lookup"><span data-stu-id="22d91-136">Splatting with arrays</span></span>

<span data-ttu-id="22d91-137">Используйте массив, чтобы со звездочкой значения для параметров позиционирования, не требующих указания имен параметров.</span><span class="sxs-lookup"><span data-stu-id="22d91-137">Use an array to splat values for positional parameters, which do not require parameter names.</span></span> <span data-ttu-id="22d91-138">Значения должны быть в порядке порядкового номера в массиве.</span><span class="sxs-lookup"><span data-stu-id="22d91-138">The values must be in position-number order in the array.</span></span>

<span data-ttu-id="22d91-139">В следующих примерах сравниваются две `Copy-Item` команды, которые копируют файл Test.txt в файл Test2.txt в том же каталоге.</span><span class="sxs-lookup"><span data-stu-id="22d91-139">The following examples compare two `Copy-Item` commands that copy the Test.txt file to the Test2.txt file in the same directory.</span></span>

<span data-ttu-id="22d91-140">В первом примере используется традиционный формат, в котором имена параметров опущены.</span><span class="sxs-lookup"><span data-stu-id="22d91-140">The first example uses the traditional format in which parameter names are omitted.</span></span> <span data-ttu-id="22d91-141">Значения параметров отображаются в порядке расположения в команде.</span><span class="sxs-lookup"><span data-stu-id="22d91-141">The parameter values appear in position order in the command.</span></span>

```powershell
Copy-Item "test.txt" "test2.txt" -WhatIf
```

<span data-ttu-id="22d91-142">Во втором примере используется массив Сплаттинг.</span><span class="sxs-lookup"><span data-stu-id="22d91-142">The second example uses array splatting.</span></span> <span data-ttu-id="22d91-143">Первая команда создает массив значений параметров и сохраняет их в `$ArrayArguments` переменной.</span><span class="sxs-lookup"><span data-stu-id="22d91-143">The first command creates an array of the parameter values and stores it in the `$ArrayArguments` variable.</span></span> <span data-ttu-id="22d91-144">Значения находятся в порядке расположения в массиве.</span><span class="sxs-lookup"><span data-stu-id="22d91-144">The values are in position order in the array.</span></span> <span data-ttu-id="22d91-145">Вторая команда использует `$ArrayArguments` переменную в команде в Сплаттинг.</span><span class="sxs-lookup"><span data-stu-id="22d91-145">The second command uses the `$ArrayArguments` variable in a command in splatting.</span></span> <span data-ttu-id="22d91-146">Символ "at" ( `@ArrayArguments` ) заменяет знак доллара ( `$ArrayArguments` ) в команде.</span><span class="sxs-lookup"><span data-stu-id="22d91-146">The At symbol (`@ArrayArguments`) replaces the dollar sign (`$ArrayArguments`) in the command.</span></span>

```powershell
$ArrayArguments = "test.txt", "test2.txt"
Copy-Item @ArrayArguments -WhatIf
```

### <a name="using-the-argumentlist-parameter"></a><span data-ttu-id="22d91-147">Использование параметра ArgumentList</span><span class="sxs-lookup"><span data-stu-id="22d91-147">Using the ArgumentList parameter</span></span>

<span data-ttu-id="22d91-148">Несколько командлетов имеют параметр **ArgumentList** , который используется для передачи значений параметров в блок сценария, выполняемый командлетом.</span><span class="sxs-lookup"><span data-stu-id="22d91-148">Several cmdlets have an **ArgumentList** parameter that is used to pass parameter values to a script block that is executed by the cmdlet.</span></span> <span data-ttu-id="22d91-149">Параметр **ArgumentList** принимает массив значений, передаваемых в блок скрипта.</span><span class="sxs-lookup"><span data-stu-id="22d91-149">The **ArgumentList** parameter takes an array of values that is passed to the script block.</span></span> <span data-ttu-id="22d91-150">PowerShell эффективно использует Array Сплаттинг для привязки значений к параметрам блока script.</span><span class="sxs-lookup"><span data-stu-id="22d91-150">PowerShell is effectively using array splatting to bind the values to the parameters of the script block.</span></span> <span data-ttu-id="22d91-151">Если при использовании **ArgumentList** необходимо передать массив как отдельный объект, привязанный к одному параметру, необходимо заключить массив в оболочку как единственный элемент другого массива.</span><span class="sxs-lookup"><span data-stu-id="22d91-151">When using **ArgumentList** , if you need to pass an array as a single object bound to a single parameter, you must wrap the array as the only element of another array.</span></span>

<span data-ttu-id="22d91-152">В следующем примере имеется блок скрипта, который принимает один параметр, который является массивом строк.</span><span class="sxs-lookup"><span data-stu-id="22d91-152">The following example has a script block that takes a single parameter that is an array of strings.</span></span>

```powershell
$array = 'Hello', 'World!'
Invoke-Command -ScriptBlock {
  param([string[]]$words) $words -join ' '
  } -ArgumentList $array
```
<!--
01234567890123456789012345678901234567890123456789012345678901234567890123456789
-->
<span data-ttu-id="22d91-153">В этом примере `$array` блоку Script передается только первый элемент в.</span><span class="sxs-lookup"><span data-stu-id="22d91-153">In this example, only the first item in `$array` is passed to the script block.</span></span>

```Output
Hello
```

```powershell
$array = 'Hello', 'World!'
Invoke-Command -ScriptBlock {
  param([string[]]$words) $words -join ' '
} -ArgumentList (,$array)
```

<span data-ttu-id="22d91-154">В этом примере `$array` переносится в массив, чтобы весь массив передавался в блок скрипта как один объект.</span><span class="sxs-lookup"><span data-stu-id="22d91-154">In this example, `$array` is wrapped in an array so that the entire array is passed to the script block as a single object.</span></span>

```Output
Hello World!
```

## <a name="examples"></a><span data-ttu-id="22d91-155">Примеры</span><span class="sxs-lookup"><span data-stu-id="22d91-155">Examples</span></span>

### <a name="example-1-reuse-splatted-parameters-in-different-commands"></a><span data-ttu-id="22d91-156">Пример 1. повторное использование параметров сплаттед в разных командах</span><span class="sxs-lookup"><span data-stu-id="22d91-156">Example 1: Reuse splatted parameters in different commands</span></span>

<span data-ttu-id="22d91-157">В этом примере показано, как повторно использовать значения сплаттед в различных командах.</span><span class="sxs-lookup"><span data-stu-id="22d91-157">This example shows how to reuse splatted values in different commands.</span></span> <span data-ttu-id="22d91-158">Команды в этом примере используют `Write-Host` командлет для записи сообщений в консоль главного приложения.</span><span class="sxs-lookup"><span data-stu-id="22d91-158">The commands in this example use the `Write-Host` cmdlet to write messages to the host program console.</span></span> <span data-ttu-id="22d91-159">Он использует Сплаттинг для указания цвета переднего плана и фона.</span><span class="sxs-lookup"><span data-stu-id="22d91-159">It uses splatting to specify the foreground and background colors.</span></span>

<span data-ttu-id="22d91-160">Чтобы изменить цвета всех команд, просто измените значение `$Colors` переменной.</span><span class="sxs-lookup"><span data-stu-id="22d91-160">To change the colors of all commands, just change the value of the `$Colors` variable.</span></span>

<span data-ttu-id="22d91-161">Первая команда создает хэш-таблицу с именами и значениями параметров и сохраняет хэш-таблицу в `$Colors` переменной.</span><span class="sxs-lookup"><span data-stu-id="22d91-161">The first command creates a hash table of parameter names and values and stores the hash table in the `$Colors` variable.</span></span>

```powershell
$Colors = @{ForegroundColor = "black"; BackgroundColor = "white"}
```

<span data-ttu-id="22d91-162">Вторая и третья команды используют `$Colors` переменную для сплаттинг в `Write-Host` команде.</span><span class="sxs-lookup"><span data-stu-id="22d91-162">The second and third commands use the `$Colors` variable for splatting in a `Write-Host` command.</span></span> <span data-ttu-id="22d91-163">Чтобы использовать `$Colors variable` , замените знак доллара ( `$Colors` ) на символ at ( `@Colors` ).</span><span class="sxs-lookup"><span data-stu-id="22d91-163">To use the `$Colors variable`, replace the dollar sign (`$Colors`) with an At symbol (`@Colors`).</span></span>

```powershell
#Write a message with the colors in $Colors
Write-Host "This is a test." @Colors

#Write second message with same colors. The position of splatted
#hash table does not matter.
Write-Host @Colors "This is another test."
```

### <a name="example-2-forward-parameters-using-psboundparameters"></a><span data-ttu-id="22d91-164">Пример 2. Пересылка параметров с помощью $PSBoundParameters</span><span class="sxs-lookup"><span data-stu-id="22d91-164">Example 2: Forward parameters using $PSBoundParameters</span></span>

<span data-ttu-id="22d91-165">В этом примере показано, как перенаправить свои параметры в другие команды с помощью Сплаттинг и `$PSBoundParameters` автоматической переменной.</span><span class="sxs-lookup"><span data-stu-id="22d91-165">This example shows how to forward their parameters to other commands by using splatting and the `$PSBoundParameters` automatic variable.</span></span>

<span data-ttu-id="22d91-166">`$PSBoundParameters`Автоматическая переменная — это объект словаря (System. Collections. Generic. Dictionary), содержащий все имена и значения параметров, которые используются при выполнении скрипта или функции.</span><span class="sxs-lookup"><span data-stu-id="22d91-166">The `$PSBoundParameters` automatic variable is a dictionary object (System.Collections.Generic.Dictionary) that contains all the parameter names and values that are used when a script or function is run.</span></span>

<span data-ttu-id="22d91-167">В следующем примере мы используем `$PSBoundParameters` переменную для пересылки значений параметров, переданных в скрипт или функцию, в функцию `Test2` `Test1` .</span><span class="sxs-lookup"><span data-stu-id="22d91-167">In the following example, we use the `$PSBoundParameters` variable to forward the parameters values passed to a script or function from `Test2` function to the `Test1` function.</span></span> <span data-ttu-id="22d91-168">Оба вызова `Test1` функции `Test2` используют Сплаттинг.</span><span class="sxs-lookup"><span data-stu-id="22d91-168">Both calls to the `Test1` function from `Test2` use splatting.</span></span>

```powershell
function Test1
{
    param($a, $b, $c)

    $a
    $b
    $c
}

function Test2
{
    param($a, $b, $c)

    #Call the Test1 function with $a, $b, and $c.
    Test1 @PsBoundParameters

    #Call the Test1 function with $b and $c, but not with $a
    $LimitedParameters = $PSBoundParameters
    $LimitedParameters.Remove("a") | Out-Null
    Test1 @LimitedParameters
}
```

```Output
Test2 -a 1 -b 2 -c 3
1
2
3
2
3
```

### <a name="example-3-override-splatted-parameters-with-explicitly-defined-parameters"></a><span data-ttu-id="22d91-169">Пример 3. Переопределение параметров сплаттед с помощью явно определенных параметров</span><span class="sxs-lookup"><span data-stu-id="22d91-169">Example 3: Override splatted parameters with explicitly defined parameters</span></span>

<span data-ttu-id="22d91-170">В этом примере показано, как переопределить параметр сплаттед с помощью явно определенных параметров.</span><span class="sxs-lookup"><span data-stu-id="22d91-170">This example shows how to override a splatted parameter using explicitly defined parameters.</span></span> <span data-ttu-id="22d91-171">Это полезно, если вы не хотите создавать новую хэш-таблицу или изменить значение в хэш-таблице, которую вы используете для со звездочкой.</span><span class="sxs-lookup"><span data-stu-id="22d91-171">This is useful when you don't want to build a new hashtable or change a value in the hashtable you are using to splat.</span></span>

<span data-ttu-id="22d91-172">`$commonParams`Переменная хранит параметры для создания виртуальных машин в `East US` расположении.</span><span class="sxs-lookup"><span data-stu-id="22d91-172">The `$commonParams` variable stores the parameters to create virtual machines in the `East US` location.</span></span> <span data-ttu-id="22d91-173">`$allVms`Переменная представляет собой список виртуальных машин для создания.</span><span class="sxs-lookup"><span data-stu-id="22d91-173">The `$allVms` variable is a list of virtual machines to create.</span></span> <span data-ttu-id="22d91-174">Мы перебираем список и используем `$commonParams` , чтобы со звездочкой параметры для создания каждой виртуальной машины.</span><span class="sxs-lookup"><span data-stu-id="22d91-174">We loop through the list and use `$commonParams` to splat the parameters to create each virtual machine.</span></span> <span data-ttu-id="22d91-175">Однако мы хотим `myVM2` создать в регионе, отличном от региона других виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="22d91-175">However, we want `myVM2` to be created in a different region than the other virtual machines.</span></span> <span data-ttu-id="22d91-176">Вместо настройки `$commonParams` Hashtable можно явно определить параметр **Location** в, `New-AzVm` чтобы заменять значение `Location` ключа в `$commonParams` .</span><span class="sxs-lookup"><span data-stu-id="22d91-176">Instead of adjusting the `$commonParams` hashtable, you can explicitly define the **Location** parameter in `New-AzVm` to supersede the value of the `Location` key in `$commonParams`.</span></span>

```powershell
$commonParams = @{
    ResourceGroupName = "myResourceGroup"
    Location = "East US"
    VirtualNetworkName = "myVnet"
    SubnetName = "mySubnet"
    SecurityGroupName = "myNetworkSecurityGroup"
    PublicIpAddressName = "myPublicIpAddress"
}

$allVms = @('myVM1','myVM2','myVM3',)

foreach ($vm in $allVms)
{
    if ($vm -eq 'myVM2')
    {
        New-AzVm @commonParams -Name $vm -Location "West US"
    }
    else
    {
        New-AzVm @commonParams -Name $vm
    }
}
```

## <a name="splatting-command-parameters"></a><span data-ttu-id="22d91-177">Параметры команды Сплаттинг</span><span class="sxs-lookup"><span data-stu-id="22d91-177">Splatting command parameters</span></span>

<span data-ttu-id="22d91-178">Сплаттинг можно использовать для представления параметров команды.</span><span class="sxs-lookup"><span data-stu-id="22d91-178">You can use splatting to represent the parameters of a command.</span></span> <span data-ttu-id="22d91-179">Этот метод полезен при создании прокси-функции, то есть функции, которая вызывает другую команду.</span><span class="sxs-lookup"><span data-stu-id="22d91-179">This technique is useful when you are creating a proxy function, that is, a function that calls another command.</span></span> <span data-ttu-id="22d91-180">Эта функция появилась в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="22d91-180">This feature is introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="22d91-181">Чтобы со звездочкой параметры команды, используйте `@Args` для представления параметров команды.</span><span class="sxs-lookup"><span data-stu-id="22d91-181">To splat the parameters of a command, use `@Args` to represent the command parameters.</span></span> <span data-ttu-id="22d91-182">Этот метод проще, чем перечислять параметры команды и работает без редакции, даже если параметры вызванной команды изменятся.</span><span class="sxs-lookup"><span data-stu-id="22d91-182">This technique is easier than enumerating command parameters and it works without revision even if the parameters of the called command change.</span></span>

<span data-ttu-id="22d91-183">Эта функция использует `$Args` автоматическую переменную, которая содержит все значения неназначенных параметров.</span><span class="sxs-lookup"><span data-stu-id="22d91-183">The feature uses the `$Args` automatic variable, which contains all unassigned parameter values.</span></span>

<span data-ttu-id="22d91-184">Например, следующая функция вызывает `Get-Process` командлет.</span><span class="sxs-lookup"><span data-stu-id="22d91-184">For example, the following function calls the `Get-Process` cmdlet.</span></span> <span data-ttu-id="22d91-185">В этой функции `@Args` представляет все параметры `Get-Process` командлета.</span><span class="sxs-lookup"><span data-stu-id="22d91-185">In this function, `@Args` represents all the parameters of the `Get-Process` cmdlet.</span></span>

```powershell
function Get-MyProcess { Get-Process @Args }
```

<span data-ttu-id="22d91-186">При использовании `Get-MyProcess` функции передаются все неназначенные параметры и значения параметров `@Args` , как показано в следующих командах.</span><span class="sxs-lookup"><span data-stu-id="22d91-186">When you use the `Get-MyProcess` function, all unassigned parameters and parameter values are passed to `@Args`, as shown in the following commands.</span></span>

```powershell
Get-MyProcess -Name PowerShell
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    463      46   225484     237196   719    15.86   3228 powershell
```

```powershell
Get-MyProcess -Name PowerShell_Ise -FileVersionInfo
```

```Output
ProductVersion   FileVersion      FileName
--------------   -----------      --------
6.2.9200.16384   6.2.9200.1638... C:\Windows\system32\WindowsPowerShell\...
```

<span data-ttu-id="22d91-187">Можно использовать `@Args` в функции, которая содержит явно объявленные параметры.</span><span class="sxs-lookup"><span data-stu-id="22d91-187">You can use `@Args` in a function that has explicitly declared parameters.</span></span> <span data-ttu-id="22d91-188">Его можно использовать несколько раз в функции, но все введенные параметры передаются всем экземплярам `@Args` , как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="22d91-188">You can use it more than once in a function, but all parameters that you enter are passed to all instances of `@Args`, as shown in the following example.</span></span>

```powershell
function Get-MyCommand
{
    Param ([switch]$P, [switch]$C)
    if ($P) { Get-Process @Args }
    if ($C) { Get-Command @Args }
}

Get-MyCommand -P -C -Name PowerShell
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
408      28    75568      83176   620     1.33   1692 powershell

Path               : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.e
Extension          : .exe
Definition         : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.e
Visibility         : Public
OutputType         : {System.String}
Name               : powershell.exe
CommandType        : Application
ModuleName         :
Module             :
RemotingCapability : PowerShell
Parameters         :
ParameterSets      :
HelpUri            :
FileVersionInfo    : File:             C:\Windows\System32\WindowsPowerShell
                     \v1.0\powershell.exe
                     InternalName:     POWERSHELL
                     OriginalFilename: PowerShell.EXE.MUI
                     FileVersion:      10.0.14393.0 (rs1_release.160715-1616
                     FileDescription:  Windows PowerShell
                     Product:          Microsoft Windows Operating System
                     ProductVersion:   10.0.14393.0
                     Debug:            False
                     Patched:          False
                     PreRelease:       False
                     PrivateBuild:     False
                     SpecialBuild:     False
                     Language:         English (United States)
```

## <a name="notes"></a><span data-ttu-id="22d91-189">Примечания</span><span class="sxs-lookup"><span data-stu-id="22d91-189">Notes</span></span>

<span data-ttu-id="22d91-190">Если вы сделаете функцию в расширенной функции с помощью атрибутов **CmdletBinding** или **Parameter** , `$args` Автоматическая переменная больше не будет доступна в функции.</span><span class="sxs-lookup"><span data-stu-id="22d91-190">If you make a function into an advanced function by using either the **CmdletBinding** or **Parameter** attributes, the `$args` automatic variable is no longer available in the function.</span></span> <span data-ttu-id="22d91-191">Для расширенных функций требуется явное определение параметра.</span><span class="sxs-lookup"><span data-stu-id="22d91-191">Advanced functions require explicit parameter definition.</span></span>

<span data-ttu-id="22d91-192">Настройка требуемого состояния PowerShell (DSC) не была разработана для использования Сплаттинг.</span><span class="sxs-lookup"><span data-stu-id="22d91-192">PowerShell Desired State Configuration (DSC) was not designed to use splatting.</span></span>
<span data-ttu-id="22d91-193">Сплаттинг нельзя использовать для передачи значений в ресурс DSC.</span><span class="sxs-lookup"><span data-stu-id="22d91-193">You cannot use splatting to pass values into a DSC resource.</span></span> <span data-ttu-id="22d91-194">Дополнительные сведения см. в статье Гаел Колас " [псевдо-СПЛАТТИНГ DSC Resources](https://gaelcolas.com/2017/11/05/pseudo-splatting-dsc-resources/).</span><span class="sxs-lookup"><span data-stu-id="22d91-194">For more information, see Gael Colas' article [Pseudo-Splatting DSC Resources](https://gaelcolas.com/2017/11/05/pseudo-splatting-dsc-resources/).</span></span>

## <a name="see-also"></a><span data-ttu-id="22d91-195">См. также статью</span><span class="sxs-lookup"><span data-stu-id="22d91-195">See also</span></span>

[<span data-ttu-id="22d91-196">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="22d91-196">about_Arrays</span></span>](about_Arrays.md)

[<span data-ttu-id="22d91-197">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="22d91-197">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="22d91-198">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="22d91-198">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="22d91-199">about_Parameters</span><span class="sxs-lookup"><span data-stu-id="22d91-199">about_Parameters</span></span>](about_Parameters.md)