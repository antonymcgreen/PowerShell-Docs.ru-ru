---
description: Описывает, как использовать Сплаттинг для передачи параметров в команды в PowerShell.
Locale: en-US
ms.date: 08/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_splatting?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Splatting
ms.openlocfilehash: e028f43828afd69d645591ab20795689cb115e12
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605301"
---
# <a name="about-splatting"></a><span data-ttu-id="10c29-103">О Сплаттинг</span><span class="sxs-lookup"><span data-stu-id="10c29-103">About Splatting</span></span>

## <a name="short-description"></a><span data-ttu-id="10c29-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="10c29-104">Short description</span></span>

<span data-ttu-id="10c29-105">Описывает, как использовать Сплаттинг для передачи параметров в команды в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="10c29-105">Describes how to use splatting to pass parameters to commands in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="10c29-106">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="10c29-106">Long description</span></span>

<span data-ttu-id="10c29-107">Сплаттинг — это метод передачи коллекции значений параметров в команду как единое целое.</span><span class="sxs-lookup"><span data-stu-id="10c29-107">Splatting is a method of passing a collection of parameter values to a command as a unit.</span></span> <span data-ttu-id="10c29-108">PowerShell связывает каждое значение в коллекции с параметром команды.</span><span class="sxs-lookup"><span data-stu-id="10c29-108">PowerShell associates each value in the collection with a command parameter.</span></span> <span data-ttu-id="10c29-109">Значения параметров сплаттед хранятся в именованных переменных Сплаттинг, которые выглядят как стандартные переменные, но начинаются с символа ( `@` ) вместо знака доллара ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="10c29-109">Splatted parameter values are stored in named splatting variables, which look like standard variables, but begin with an At symbol (`@`) instead of a dollar sign (`$`).</span></span> <span data-ttu-id="10c29-110">Символ at указывает PowerShell на передачу коллекции значений, а не одно значение.</span><span class="sxs-lookup"><span data-stu-id="10c29-110">The At symbol tells PowerShell that you are passing a collection of values, instead of a single value.</span></span>

<span data-ttu-id="10c29-111">Сплаттинг делает команды короче и проще в чтении.</span><span class="sxs-lookup"><span data-stu-id="10c29-111">Splatting makes your commands shorter and easier to read.</span></span> <span data-ttu-id="10c29-112">Можно повторно использовать значения сплаттинг в разных вызовах команд и использовать Сплаттинг для передачи значений параметров из `$PSBoundParameters` автоматической переменной в другие скрипты и функции.</span><span class="sxs-lookup"><span data-stu-id="10c29-112">You can reuse the splatting values in different command calls and use splatting to pass parameter values from the `$PSBoundParameters` automatic variable to other scripts and functions.</span></span>

<span data-ttu-id="10c29-113">Начиная с Windows PowerShell 3,0, можно также использовать Сплаттинг для представления всех параметров команды.</span><span class="sxs-lookup"><span data-stu-id="10c29-113">Beginning in Windows PowerShell 3.0, you can also use splatting to represent all parameters of a command.</span></span>

## <a name="syntax"></a><span data-ttu-id="10c29-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="10c29-114">Syntax</span></span>

```
<CommandName> <optional parameters> @<HashTable> <optional parameters>
<CommandName> <optional parameters> @<Array> <optional parameters>
```

<span data-ttu-id="10c29-115">Чтобы указать значения параметров для параметров позиционирования, в которых не требуются имена параметров, используйте синтаксис массива.</span><span class="sxs-lookup"><span data-stu-id="10c29-115">To provide parameter values for positional parameters, in which parameter names are not required, use the array syntax.</span></span> <span data-ttu-id="10c29-116">Чтобы указать пары имен и значений параметров, используйте синтаксис хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="10c29-116">To provide parameter name and value pairs, use the hash table syntax.</span></span> <span data-ttu-id="10c29-117">Значение сплаттед может находиться в любом месте в списке параметров.</span><span class="sxs-lookup"><span data-stu-id="10c29-117">The splatted value can appear anywhere in the parameter list.</span></span>

<span data-ttu-id="10c29-118">При Сплаттинг не нужно использовать хэш-таблицу или массив для передачи всех параметров.</span><span class="sxs-lookup"><span data-stu-id="10c29-118">When splatting, you do not need to use a hash table or an array to pass all parameters.</span></span> <span data-ttu-id="10c29-119">Некоторые параметры можно передать с помощью Сплаттинг и передать другим по положению или имени параметра.</span><span class="sxs-lookup"><span data-stu-id="10c29-119">You may pass some parameters by using splatting and pass others by position or by parameter name.</span></span> <span data-ttu-id="10c29-120">Кроме того, можно со звездочкой несколько объектов в одной команде, чтобы для каждого параметра не передавалось больше одного значения.</span><span class="sxs-lookup"><span data-stu-id="10c29-120">Also, you can splat multiple objects in a single command so you don't pass more than one value for each parameter.</span></span>

<span data-ttu-id="10c29-121">В PowerShell 7,1 можно переопределить параметр сплаттед, явно определив параметр в команде.</span><span class="sxs-lookup"><span data-stu-id="10c29-121">As of PowerShell 7.1, you can override a splatted parameter by explicitly defining a parameter in a command.</span></span>

## <a name="splatting-with-hash-tables"></a><span data-ttu-id="10c29-122">Сплаттинг с хэш-таблицами</span><span class="sxs-lookup"><span data-stu-id="10c29-122">Splatting with hash tables</span></span>

<span data-ttu-id="10c29-123">Используйте хэш-таблицу для со звездочкой пар имен и значений параметров.</span><span class="sxs-lookup"><span data-stu-id="10c29-123">Use a hash table to splat parameter name and value pairs.</span></span> <span data-ttu-id="10c29-124">Этот формат можно использовать для всех типов параметров, включая параметры позиционирования и переключателя.</span><span class="sxs-lookup"><span data-stu-id="10c29-124">You can use this format for all parameter types, including positional and switch parameters.</span></span>
<span data-ttu-id="10c29-125">Позиционированные параметры должны быть назначены по имени.</span><span class="sxs-lookup"><span data-stu-id="10c29-125">Positional parameters must be assigned by name.</span></span>

<span data-ttu-id="10c29-126">В следующих примерах сравниваются две `Copy-Item` команды, которые копируют файл Test.txt в файл Test2.txt в том же каталоге.</span><span class="sxs-lookup"><span data-stu-id="10c29-126">The following examples compare two `Copy-Item` commands that copy the Test.txt file to the Test2.txt file in the same directory.</span></span>

<span data-ttu-id="10c29-127">В первом примере используется традиционный формат, в котором включены имена параметров.</span><span class="sxs-lookup"><span data-stu-id="10c29-127">The first example uses the traditional format in which parameter names are included.</span></span>

```powershell
Copy-Item -Path "test.txt" -Destination "test2.txt" -WhatIf
```

<span data-ttu-id="10c29-128">Во втором примере используется хэш-таблица Сплаттинг.</span><span class="sxs-lookup"><span data-stu-id="10c29-128">The second example uses hash table splatting.</span></span> <span data-ttu-id="10c29-129">Первая команда создает хэш-таблицу пар "параметр-имя" и "параметр-значение" и сохраняет их в `$HashArguments` переменной.</span><span class="sxs-lookup"><span data-stu-id="10c29-129">The first command creates a hash table of parameter-name and parameter-value pairs and stores it in the `$HashArguments` variable.</span></span> <span data-ttu-id="10c29-130">Вторая команда использует `$HashArguments` переменную в команде с параметром Сплаттинг.</span><span class="sxs-lookup"><span data-stu-id="10c29-130">The second command uses the `$HashArguments` variable in a command with splatting.</span></span> <span data-ttu-id="10c29-131">Символ "at" ( `@HashArguments` ) заменяет знак доллара ( `$HashArguments` ) в команде.</span><span class="sxs-lookup"><span data-stu-id="10c29-131">The At symbol (`@HashArguments`) replaces the dollar sign (`$HashArguments`) in the command.</span></span>

<span data-ttu-id="10c29-132">Чтобы указать значение параметра **WhatIf** , используйте `$True` или `$False` .</span><span class="sxs-lookup"><span data-stu-id="10c29-132">To provide a value for the **WhatIf** switch parameter, use `$True` or `$False`.</span></span>

```powershell
$HashArguments = @{
  Path = "test.txt"
  Destination = "test2.txt"
  WhatIf = $true
}
Copy-Item @HashArguments
```

> [!NOTE]
> <span data-ttu-id="10c29-133">В первой команде символ at ( `@` ) указывает на хэш-таблицу, а не на значение сплаттед.</span><span class="sxs-lookup"><span data-stu-id="10c29-133">In the first command, the At symbol (`@`) indicates a hash table, not a splatted value.</span></span> <span data-ttu-id="10c29-134">Синтаксис для хэш-таблиц в PowerShell: `@{<name>=<value>; <name>=<value>; ...}`</span><span class="sxs-lookup"><span data-stu-id="10c29-134">The syntax for hash tables in PowerShell is: `@{<name>=<value>; <name>=<value>; ...}`</span></span>

## <a name="splatting-with-arrays"></a><span data-ttu-id="10c29-135">Сплаттинг с массивами</span><span class="sxs-lookup"><span data-stu-id="10c29-135">Splatting with arrays</span></span>

<span data-ttu-id="10c29-136">Используйте массив, чтобы со звездочкой значения для параметров позиционирования, не требующих указания имен параметров.</span><span class="sxs-lookup"><span data-stu-id="10c29-136">Use an array to splat values for positional parameters, which do not require parameter names.</span></span> <span data-ttu-id="10c29-137">Значения должны быть в порядке порядкового номера в массиве.</span><span class="sxs-lookup"><span data-stu-id="10c29-137">The values must be in position-number order in the array.</span></span>

<span data-ttu-id="10c29-138">В следующих примерах сравниваются две `Copy-Item` команды, которые копируют файл Test.txt в файл Test2.txt в том же каталоге.</span><span class="sxs-lookup"><span data-stu-id="10c29-138">The following examples compare two `Copy-Item` commands that copy the Test.txt file to the Test2.txt file in the same directory.</span></span>

<span data-ttu-id="10c29-139">В первом примере используется традиционный формат, в котором имена параметров опущены.</span><span class="sxs-lookup"><span data-stu-id="10c29-139">The first example uses the traditional format in which parameter names are omitted.</span></span> <span data-ttu-id="10c29-140">Значения параметров отображаются в порядке расположения в команде.</span><span class="sxs-lookup"><span data-stu-id="10c29-140">The parameter values appear in position order in the command.</span></span>

```powershell
Copy-Item "test.txt" "test2.txt" -WhatIf
```

<span data-ttu-id="10c29-141">Во втором примере используется массив Сплаттинг.</span><span class="sxs-lookup"><span data-stu-id="10c29-141">The second example uses array splatting.</span></span> <span data-ttu-id="10c29-142">Первая команда создает массив значений параметров и сохраняет их в `$ArrayArguments` переменной.</span><span class="sxs-lookup"><span data-stu-id="10c29-142">The first command creates an array of the parameter values and stores it in the `$ArrayArguments` variable.</span></span> <span data-ttu-id="10c29-143">Значения находятся в порядке расположения в массиве.</span><span class="sxs-lookup"><span data-stu-id="10c29-143">The values are in position order in the array.</span></span> <span data-ttu-id="10c29-144">Вторая команда использует `$ArrayArguments` переменную в команде в Сплаттинг.</span><span class="sxs-lookup"><span data-stu-id="10c29-144">The second command uses the `$ArrayArguments` variable in a command in splatting.</span></span> <span data-ttu-id="10c29-145">Символ "at" ( `@ArrayArguments` ) заменяет знак доллара ( `$ArrayArguments` ) в команде.</span><span class="sxs-lookup"><span data-stu-id="10c29-145">The At symbol (`@ArrayArguments`) replaces the dollar sign (`$ArrayArguments`) in the command.</span></span>

```powershell
$ArrayArguments = "test.txt", "test2.txt"
Copy-Item @ArrayArguments -WhatIf
```

### <a name="using-the-argumentlist-parameter"></a><span data-ttu-id="10c29-146">Использование параметра ArgumentList</span><span class="sxs-lookup"><span data-stu-id="10c29-146">Using the ArgumentList parameter</span></span>

<span data-ttu-id="10c29-147">Несколько командлетов имеют параметр **ArgumentList** , который используется для передачи значений параметров в блок сценария, выполняемый командлетом.</span><span class="sxs-lookup"><span data-stu-id="10c29-147">Several cmdlets have an **ArgumentList** parameter that is used to pass parameter values to a script block that is executed by the cmdlet.</span></span> <span data-ttu-id="10c29-148">Параметр **ArgumentList** принимает массив значений, передаваемых в блок скрипта.</span><span class="sxs-lookup"><span data-stu-id="10c29-148">The **ArgumentList** parameter takes an array of values that is passed to the script block.</span></span> <span data-ttu-id="10c29-149">PowerShell эффективно использует Array Сплаттинг для привязки значений к параметрам блока script.</span><span class="sxs-lookup"><span data-stu-id="10c29-149">PowerShell is effectively using array splatting to bind the values to the parameters of the script block.</span></span> <span data-ttu-id="10c29-150">Если при использовании **ArgumentList** необходимо передать массив как отдельный объект, привязанный к одному параметру, необходимо заключить массив в оболочку как единственный элемент другого массива.</span><span class="sxs-lookup"><span data-stu-id="10c29-150">When using **ArgumentList**, if you need to pass an array as a single object bound to a single parameter, you must wrap the array as the only element of another array.</span></span>

<span data-ttu-id="10c29-151">В следующем примере имеется блок скрипта, который принимает один параметр, который является массивом строк.</span><span class="sxs-lookup"><span data-stu-id="10c29-151">The following example has a script block that takes a single parameter that is an array of strings.</span></span>

```powershell
$array = 'Hello', 'World!'
Invoke-Command -ScriptBlock {
  param([string[]]$words) $words -join ' '
  } -ArgumentList $array
```
<!--
01234567890123456789012345678901234567890123456789012345678901234567890123456789
-->
<span data-ttu-id="10c29-152">В этом примере `$array` блоку Script передается только первый элемент в.</span><span class="sxs-lookup"><span data-stu-id="10c29-152">In this example, only the first item in `$array` is passed to the script block.</span></span>

```Output
Hello
```

```powershell
$array = 'Hello', 'World!'
Invoke-Command -ScriptBlock {
  param([string[]]$words) $words -join ' '
} -ArgumentList (,$array)
```

<span data-ttu-id="10c29-153">В этом примере `$array` переносится в массив, чтобы весь массив передавался в блок скрипта как один объект.</span><span class="sxs-lookup"><span data-stu-id="10c29-153">In this example, `$array` is wrapped in an array so that the entire array is passed to the script block as a single object.</span></span>

```Output
Hello World!
```

## <a name="examples"></a><span data-ttu-id="10c29-154">Примеры</span><span class="sxs-lookup"><span data-stu-id="10c29-154">Examples</span></span>

### <a name="example-1-reuse-splatted-parameters-in-different-commands"></a><span data-ttu-id="10c29-155">Пример 1. повторное использование параметров сплаттед в разных командах</span><span class="sxs-lookup"><span data-stu-id="10c29-155">Example 1: Reuse splatted parameters in different commands</span></span>

<span data-ttu-id="10c29-156">В этом примере показано, как повторно использовать значения сплаттед в различных командах.</span><span class="sxs-lookup"><span data-stu-id="10c29-156">This example shows how to reuse splatted values in different commands.</span></span> <span data-ttu-id="10c29-157">Команды в этом примере используют `Write-Host` командлет для записи сообщений в консоль главного приложения.</span><span class="sxs-lookup"><span data-stu-id="10c29-157">The commands in this example use the `Write-Host` cmdlet to write messages to the host program console.</span></span> <span data-ttu-id="10c29-158">Он использует Сплаттинг для указания цвета переднего плана и фона.</span><span class="sxs-lookup"><span data-stu-id="10c29-158">It uses splatting to specify the foreground and background colors.</span></span>

<span data-ttu-id="10c29-159">Чтобы изменить цвета всех команд, просто измените значение `$Colors` переменной.</span><span class="sxs-lookup"><span data-stu-id="10c29-159">To change the colors of all commands, just change the value of the `$Colors` variable.</span></span>

<span data-ttu-id="10c29-160">Первая команда создает хэш-таблицу с именами и значениями параметров и сохраняет хэш-таблицу в `$Colors` переменной.</span><span class="sxs-lookup"><span data-stu-id="10c29-160">The first command creates a hash table of parameter names and values and stores the hash table in the `$Colors` variable.</span></span>

```powershell
$Colors = @{ForegroundColor = "black"; BackgroundColor = "white"}
```

<span data-ttu-id="10c29-161">Вторая и третья команды используют `$Colors` переменную для сплаттинг в `Write-Host` команде.</span><span class="sxs-lookup"><span data-stu-id="10c29-161">The second and third commands use the `$Colors` variable for splatting in a `Write-Host` command.</span></span> <span data-ttu-id="10c29-162">Чтобы использовать `$Colors variable` , замените знак доллара ( `$Colors` ) на символ at ( `@Colors` ).</span><span class="sxs-lookup"><span data-stu-id="10c29-162">To use the `$Colors variable`, replace the dollar sign (`$Colors`) with an At symbol (`@Colors`).</span></span>

```powershell
#Write a message with the colors in $Colors
Write-Host "This is a test." @Colors

#Write second message with same colors. The position of splatted
#hash table does not matter.
Write-Host @Colors "This is another test."
```

### <a name="example-2-forward-parameters-using-psboundparameters"></a><span data-ttu-id="10c29-163">Пример 2. Пересылка параметров с помощью $PSBoundParameters</span><span class="sxs-lookup"><span data-stu-id="10c29-163">Example 2: Forward parameters using $PSBoundParameters</span></span>

<span data-ttu-id="10c29-164">В этом примере показано, как перенаправить свои параметры в другие команды с помощью Сплаттинг и `$PSBoundParameters` автоматической переменной.</span><span class="sxs-lookup"><span data-stu-id="10c29-164">This example shows how to forward their parameters to other commands by using splatting and the `$PSBoundParameters` automatic variable.</span></span>

<span data-ttu-id="10c29-165">`$PSBoundParameters`Автоматическая переменная — это объект словаря (System. Collections. Generic. Dictionary), содержащий все имена и значения параметров, которые используются при выполнении скрипта или функции.</span><span class="sxs-lookup"><span data-stu-id="10c29-165">The `$PSBoundParameters` automatic variable is a dictionary object (System.Collections.Generic.Dictionary) that contains all the parameter names and values that are used when a script or function is run.</span></span>

<span data-ttu-id="10c29-166">В следующем примере мы используем `$PSBoundParameters` переменную для пересылки значений параметров, переданных в скрипт или функцию, в функцию `Test2` `Test1` .</span><span class="sxs-lookup"><span data-stu-id="10c29-166">In the following example, we use the `$PSBoundParameters` variable to forward the parameters values passed to a script or function from `Test2` function to the `Test1` function.</span></span> <span data-ttu-id="10c29-167">Оба вызова `Test1` функции `Test2` используют Сплаттинг.</span><span class="sxs-lookup"><span data-stu-id="10c29-167">Both calls to the `Test1` function from `Test2` use splatting.</span></span>

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

### <a name="example-3-override-splatted-parameters-with-explicitly-defined-parameters"></a><span data-ttu-id="10c29-168">Пример 3. Переопределение параметров сплаттед с помощью явно определенных параметров</span><span class="sxs-lookup"><span data-stu-id="10c29-168">Example 3: Override splatted parameters with explicitly defined parameters</span></span>

<span data-ttu-id="10c29-169">В этом примере показано, как переопределить параметр сплаттед с помощью явно определенных параметров.</span><span class="sxs-lookup"><span data-stu-id="10c29-169">This example shows how to override a splatted parameter using explicitly defined parameters.</span></span> <span data-ttu-id="10c29-170">Это полезно, если вы не хотите создавать новую хэш-таблицу или изменить значение в хэш-таблице, которую вы используете для со звездочкой.</span><span class="sxs-lookup"><span data-stu-id="10c29-170">This is useful when you don't want to build a new hashtable or change a value in the hashtable you are using to splat.</span></span>

<span data-ttu-id="10c29-171">`$commonParams`Переменная хранит параметры для создания виртуальных машин в `East US` расположении.</span><span class="sxs-lookup"><span data-stu-id="10c29-171">The `$commonParams` variable stores the parameters to create virtual machines in the `East US` location.</span></span> <span data-ttu-id="10c29-172">`$allVms`Переменная представляет собой список виртуальных машин для создания.</span><span class="sxs-lookup"><span data-stu-id="10c29-172">The `$allVms` variable is a list of virtual machines to create.</span></span> <span data-ttu-id="10c29-173">Мы перебираем список и используем `$commonParams` , чтобы со звездочкой параметры для создания каждой виртуальной машины.</span><span class="sxs-lookup"><span data-stu-id="10c29-173">We loop through the list and use `$commonParams` to splat the parameters to create each virtual machine.</span></span> <span data-ttu-id="10c29-174">Однако мы хотим `myVM2` создать в регионе, отличном от региона других виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="10c29-174">However, we want `myVM2` to be created in a different region than the other virtual machines.</span></span> <span data-ttu-id="10c29-175">Вместо настройки `$commonParams` Hashtable можно явно определить параметр **Location** в, `New-AzVm` чтобы заменять значение `Location` ключа в `$commonParams` .</span><span class="sxs-lookup"><span data-stu-id="10c29-175">Instead of adjusting the `$commonParams` hashtable, you can explicitly define the **Location** parameter in `New-AzVm` to supersede the value of the `Location` key in `$commonParams`.</span></span>

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

## <a name="splatting-command-parameters"></a><span data-ttu-id="10c29-176">Параметры команды Сплаттинг</span><span class="sxs-lookup"><span data-stu-id="10c29-176">Splatting command parameters</span></span>

<span data-ttu-id="10c29-177">Сплаттинг можно использовать для представления параметров команды.</span><span class="sxs-lookup"><span data-stu-id="10c29-177">You can use splatting to represent the parameters of a command.</span></span> <span data-ttu-id="10c29-178">Этот метод полезен при создании прокси-функции, то есть функции, которая вызывает другую команду.</span><span class="sxs-lookup"><span data-stu-id="10c29-178">This technique is useful when you are creating a proxy function, that is, a function that calls another command.</span></span> <span data-ttu-id="10c29-179">Эта функция появилась в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="10c29-179">This feature is introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="10c29-180">Чтобы со звездочкой параметры команды, используйте `@Args` для представления параметров команды.</span><span class="sxs-lookup"><span data-stu-id="10c29-180">To splat the parameters of a command, use `@Args` to represent the command parameters.</span></span> <span data-ttu-id="10c29-181">Этот метод проще, чем перечислять параметры команды и работает без редакции, даже если параметры вызванной команды изменятся.</span><span class="sxs-lookup"><span data-stu-id="10c29-181">This technique is easier than enumerating command parameters and it works without revision even if the parameters of the called command change.</span></span>

<span data-ttu-id="10c29-182">Эта функция использует `$Args` автоматическую переменную, которая содержит все значения неназначенных параметров.</span><span class="sxs-lookup"><span data-stu-id="10c29-182">The feature uses the `$Args` automatic variable, which contains all unassigned parameter values.</span></span>

<span data-ttu-id="10c29-183">Например, следующая функция вызывает `Get-Process` командлет.</span><span class="sxs-lookup"><span data-stu-id="10c29-183">For example, the following function calls the `Get-Process` cmdlet.</span></span> <span data-ttu-id="10c29-184">В этой функции `@Args` представляет все параметры `Get-Process` командлета.</span><span class="sxs-lookup"><span data-stu-id="10c29-184">In this function, `@Args` represents all the parameters of the `Get-Process` cmdlet.</span></span>

```powershell
function Get-MyProcess { Get-Process @Args }
```

<span data-ttu-id="10c29-185">При использовании `Get-MyProcess` функции передаются все неназначенные параметры и значения параметров `@Args` , как показано в следующих командах.</span><span class="sxs-lookup"><span data-stu-id="10c29-185">When you use the `Get-MyProcess` function, all unassigned parameters and parameter values are passed to `@Args`, as shown in the following commands.</span></span>

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

<span data-ttu-id="10c29-186">Можно использовать `@Args` в функции, которая содержит явно объявленные параметры.</span><span class="sxs-lookup"><span data-stu-id="10c29-186">You can use `@Args` in a function that has explicitly declared parameters.</span></span> <span data-ttu-id="10c29-187">Его можно использовать несколько раз в функции, но все введенные параметры передаются всем экземплярам `@Args` , как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="10c29-187">You can use it more than once in a function, but all parameters that you enter are passed to all instances of `@Args`, as shown in the following example.</span></span>

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

## <a name="notes"></a><span data-ttu-id="10c29-188">Примечания</span><span class="sxs-lookup"><span data-stu-id="10c29-188">Notes</span></span>

<span data-ttu-id="10c29-189">Если вы сделаете функцию в расширенной функции с помощью атрибутов **CmdletBinding** или **Parameter** , `$args` Автоматическая переменная больше не будет доступна в функции.</span><span class="sxs-lookup"><span data-stu-id="10c29-189">If you make a function into an advanced function by using either the **CmdletBinding** or **Parameter** attributes, the `$args` automatic variable is no longer available in the function.</span></span> <span data-ttu-id="10c29-190">Для расширенных функций требуется явное определение параметра.</span><span class="sxs-lookup"><span data-stu-id="10c29-190">Advanced functions require explicit parameter definition.</span></span>

<span data-ttu-id="10c29-191">Настройка требуемого состояния PowerShell (DSC) не была разработана для использования Сплаттинг.</span><span class="sxs-lookup"><span data-stu-id="10c29-191">PowerShell Desired State Configuration (DSC) was not designed to use splatting.</span></span>
<span data-ttu-id="10c29-192">Сплаттинг нельзя использовать для передачи значений в ресурс DSC.</span><span class="sxs-lookup"><span data-stu-id="10c29-192">You cannot use splatting to pass values into a DSC resource.</span></span> <span data-ttu-id="10c29-193">Дополнительные сведения см. в статье Гаел Колас " [псевдо-СПЛАТТИНГ DSC Resources](https://gaelcolas.com/2017/11/05/pseudo-splatting-dsc-resources/).</span><span class="sxs-lookup"><span data-stu-id="10c29-193">For more information, see Gael Colas' article [Pseudo-Splatting DSC Resources](https://gaelcolas.com/2017/11/05/pseudo-splatting-dsc-resources/).</span></span>

## <a name="see-also"></a><span data-ttu-id="10c29-194">См. также</span><span class="sxs-lookup"><span data-stu-id="10c29-194">See also</span></span>

[<span data-ttu-id="10c29-195">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="10c29-195">about_Arrays</span></span>](about_Arrays.md)

[<span data-ttu-id="10c29-196">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="10c29-196">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="10c29-197">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="10c29-197">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="10c29-198">about_Parameters</span><span class="sxs-lookup"><span data-stu-id="10c29-198">about_Parameters</span></span>](about_Parameters.md)
