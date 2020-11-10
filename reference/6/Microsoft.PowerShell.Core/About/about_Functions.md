---
description: Описание создания и использования функций в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 2/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions
ms.openlocfilehash: 944cb3fc77406cfbf288655d2740bad6ddcceee4
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94387640"
---
# <a name="about-functions"></a><span data-ttu-id="e9da4-104">О функциях</span><span class="sxs-lookup"><span data-stu-id="e9da4-104">About Functions</span></span>

## <a name="short-description"></a><span data-ttu-id="e9da4-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="e9da4-105">Short description</span></span>

<span data-ttu-id="e9da4-106">Описание создания и использования функций в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e9da4-106">Describes how to create and use functions in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="e9da4-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="e9da4-107">Long description</span></span>

<span data-ttu-id="e9da4-108">Функция — это список операторов PowerShell с назначенным именем.</span><span class="sxs-lookup"><span data-stu-id="e9da4-108">A function is a list of PowerShell statements that has a name that you assign.</span></span> <span data-ttu-id="e9da4-109">При запуске функции необходимо ввести имя функции.</span><span class="sxs-lookup"><span data-stu-id="e9da4-109">When you run a function, you type the function name.</span></span> <span data-ttu-id="e9da4-110">Инструкции в списке выполняются так, как если бы вы вводили их в командной строке.</span><span class="sxs-lookup"><span data-stu-id="e9da4-110">The statements in the list run as if you had typed them at the command prompt.</span></span>

<span data-ttu-id="e9da4-111">Функции могут быть простыми:</span><span class="sxs-lookup"><span data-stu-id="e9da4-111">Functions can be as simple as:</span></span>

```powershell
function Get-PowerShellProcess { Get-Process PowerShell }
```

<span data-ttu-id="e9da4-112">Функция также может быть сложной в качестве командлета или программы приложения.</span><span class="sxs-lookup"><span data-stu-id="e9da4-112">A function can also be as complex as a cmdlet or an application program.</span></span>

<span data-ttu-id="e9da4-113">Как и командлеты, функции могут иметь параметры.</span><span class="sxs-lookup"><span data-stu-id="e9da4-113">Like cmdlets, functions can have parameters.</span></span> <span data-ttu-id="e9da4-114">Параметры могут быть именованными, позиционированными, переключателями или динамическими параметрами.</span><span class="sxs-lookup"><span data-stu-id="e9da4-114">The parameters can be named, positional, switch, or dynamic parameters.</span></span> <span data-ttu-id="e9da4-115">Параметры функции можно считывать из командной строки или из конвейера.</span><span class="sxs-lookup"><span data-stu-id="e9da4-115">Function parameters can be read from the command line or from the pipeline.</span></span>

<span data-ttu-id="e9da4-116">Функции могут возвращать значения, которые могут быть отображены, назначены переменным или переданы другим функциям или командлетам.</span><span class="sxs-lookup"><span data-stu-id="e9da4-116">Functions can return values that can be displayed, assigned to variables, or passed to other functions or cmdlets.</span></span> <span data-ttu-id="e9da4-117">Также можно указать возвращаемое значение с помощью `return` ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="e9da4-117">You can also specify a return value using the `return` keyword.</span></span> <span data-ttu-id="e9da4-118">`return`Ключевое слово не влияет или не подавляет другие выходные данные, возвращаемые функцией.</span><span class="sxs-lookup"><span data-stu-id="e9da4-118">The `return` keyword does not affect or suppress other output returned from your function.</span></span> <span data-ttu-id="e9da4-119">Однако `return` ключевое слово завершает функцию в этой строке.</span><span class="sxs-lookup"><span data-stu-id="e9da4-119">However, the `return` keyword exits the function at that line.</span></span> <span data-ttu-id="e9da4-120">Дополнительные сведения см. в разделе [about_Return](about_Return.md).</span><span class="sxs-lookup"><span data-stu-id="e9da4-120">For more information, see [about_Return](about_Return.md).</span></span>

<span data-ttu-id="e9da4-121">Список операторов функции может содержать различные типы списков операторов с ключевыми словами `Begin` , `Process` и `End` .</span><span class="sxs-lookup"><span data-stu-id="e9da4-121">The function's statement list can contain different types of statement lists with the keywords `Begin`, `Process`, and `End`.</span></span> <span data-ttu-id="e9da4-122">Эти списки инструкций обработают входные данные из конвейера по-разному.</span><span class="sxs-lookup"><span data-stu-id="e9da4-122">These statement lists handle input from the pipeline differently.</span></span>

<span data-ttu-id="e9da4-123">Фильтр — это специальный тип функции, который использует `Filter` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="e9da4-123">A filter is a special kind of function that uses the `Filter` keyword.</span></span>

<span data-ttu-id="e9da4-124">Функции также могут действовать как командлеты.</span><span class="sxs-lookup"><span data-stu-id="e9da4-124">Functions can also act like cmdlets.</span></span> <span data-ttu-id="e9da4-125">Можно создать функцию, которая работает так же, как командлет, без использования `C#` программирования.</span><span class="sxs-lookup"><span data-stu-id="e9da4-125">You can create a function that works just like a cmdlet without using `C#` programming.</span></span> <span data-ttu-id="e9da4-126">Дополнительные сведения см. в разделе [about_Functions_Advanced](about_Functions_Advanced.md).</span><span class="sxs-lookup"><span data-stu-id="e9da4-126">For more information, see [about_Functions_Advanced](about_Functions_Advanced.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="e9da4-127">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e9da4-127">Syntax</span></span>

<span data-ttu-id="e9da4-128">Ниже приведен синтаксис функции.</span><span class="sxs-lookup"><span data-stu-id="e9da4-128">The following is the syntax for a function:</span></span>

```
function [<scope:>]<name> [([type]$parameter1[,[type]$parameter2])]
{
  param([type]$parameter1 [,[type]$parameter2])
  dynamicparam {<statement list>}
  begin {<statement list>}
  process {<statement list>}
  end {<statement list>}
}
```

<span data-ttu-id="e9da4-129">Функция включает следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="e9da4-129">A function includes the following items:</span></span>

- <span data-ttu-id="e9da4-130">`Function`Ключевое слово</span><span class="sxs-lookup"><span data-stu-id="e9da4-130">A `Function` keyword</span></span>
- <span data-ttu-id="e9da4-131">Область (необязательно)</span><span class="sxs-lookup"><span data-stu-id="e9da4-131">A scope (optional)</span></span>
- <span data-ttu-id="e9da4-132">Выбранное имя</span><span class="sxs-lookup"><span data-stu-id="e9da4-132">A name that you select</span></span>
- <span data-ttu-id="e9da4-133">Любое количество именованных параметров (необязательно)</span><span class="sxs-lookup"><span data-stu-id="e9da4-133">Any number of named parameters (optional)</span></span>
- <span data-ttu-id="e9da4-134">Одна или несколько команд PowerShell, заключенных в фигурные скобки `{}`</span><span class="sxs-lookup"><span data-stu-id="e9da4-134">One or more PowerShell commands enclosed in braces `{}`</span></span>

<span data-ttu-id="e9da4-135">Дополнительные сведения о `Dynamicparam` ключевом слове и динамических параметрах в функциях см. в разделе [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="e9da4-135">For more information about the `Dynamicparam` keyword and dynamic parameters in functions, see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

## <a name="simple-functions"></a><span data-ttu-id="e9da4-136">Простые функции</span><span class="sxs-lookup"><span data-stu-id="e9da4-136">Simple Functions</span></span>

<span data-ttu-id="e9da4-137">Функции не обязательно должны быть очень сложными.</span><span class="sxs-lookup"><span data-stu-id="e9da4-137">Functions do not have to be complicated to be useful.</span></span> <span data-ttu-id="e9da4-138">Простейшие функции имеют следующий формат:</span><span class="sxs-lookup"><span data-stu-id="e9da4-138">The simplest functions have the following format:</span></span>

```
function <function-name> {statements}
```

<span data-ttu-id="e9da4-139">Например, следующая функция запускает PowerShell с параметром Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="e9da4-139">For example, the following function starts PowerShell with the Run as Administrator option.</span></span>

```powershell
function Start-PSAdmin {Start-Process PowerShell -Verb RunAs}
```

<span data-ttu-id="e9da4-140">Чтобы использовать функцию, введите: `Start-PSAdmin`</span><span class="sxs-lookup"><span data-stu-id="e9da4-140">To use the function, type: `Start-PSAdmin`</span></span>

<span data-ttu-id="e9da4-141">Чтобы добавить операторы в функцию, введите каждую инструкцию в отдельной строке или используйте точку с запятой `;` для разделения инструкций.</span><span class="sxs-lookup"><span data-stu-id="e9da4-141">To add statements to the function, type each statement on a separate line, or use a semi-colon `;` to separate the statements.</span></span>

<span data-ttu-id="e9da4-142">Например, следующая функция находит все `.jpg` файлы в каталогах текущего пользователя, которые были изменены после начальной даты.</span><span class="sxs-lookup"><span data-stu-id="e9da4-142">For example, the following function finds all `.jpg` files in the current user's directories that were changed after the start date.</span></span>

```powershell
function Get-NewPix
{
  $start = Get-Date -Month 1 -Day 1 -Year 2010
  $allpix = Get-ChildItem -Path $env:UserProfile\*.jpg -Recurse
  $allpix | Where-Object {$_.LastWriteTime -gt $Start}
}
```

<span data-ttu-id="e9da4-143">Вы можете создать панель элементов с полезными небольшими функциями.</span><span class="sxs-lookup"><span data-stu-id="e9da4-143">You can create a toolbox of useful small functions.</span></span> <span data-ttu-id="e9da4-144">Добавьте эти функции в профиль PowerShell, как описано в [about_Profiles](about_Profiles.md) и далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="e9da4-144">Add these functions to your PowerShell profile, as described in [about_Profiles](about_Profiles.md) and later in this topic.</span></span>

## <a name="function-names"></a><span data-ttu-id="e9da4-145">Имена функций</span><span class="sxs-lookup"><span data-stu-id="e9da4-145">Function Names</span></span>

<span data-ttu-id="e9da4-146">Функции можно назначить любое имя, но функции, к которым вы предоставили доступ другим, должны соответствовать правилам именования, установленным для всех команд PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e9da4-146">You can assign any name to a function, but functions that you share with others should follow the naming rules that have been established for all PowerShell commands.</span></span>

<span data-ttu-id="e9da4-147">Имена функций должны состоять из пары существительных глаголов, в которых команда определяет действие, выполняемое функцией, а существительное определяет элемент, на котором командлет выполняет свое действие.</span><span class="sxs-lookup"><span data-stu-id="e9da4-147">Functions names should consist of a verb-noun pair in which the verb identifies the action that the function performs and the noun identifies the item on which the cmdlet performs its action.</span></span>

<span data-ttu-id="e9da4-148">Функции должны использовать стандартные команды, которые были утверждены для всех команд PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e9da4-148">Functions should use the standard verbs that have been approved for all PowerShell commands.</span></span> <span data-ttu-id="e9da4-149">Эти команды помогают нам упростить, согласовать и легко понимать имена команд.</span><span class="sxs-lookup"><span data-stu-id="e9da4-149">These verbs help us to keep our command names simple, consistent, and easy for users to understand.</span></span>

<span data-ttu-id="e9da4-150">Дополнительные сведения о стандартных командах PowerShell см. в разделе [утвержденные команды](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands) в документация Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e9da4-150">For more information about the standard PowerShell verbs, see [Approved Verbs](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands) in the Microsoft Docs.</span></span>

## <a name="functions-with-parameters"></a><span data-ttu-id="e9da4-151">Функции с параметрами</span><span class="sxs-lookup"><span data-stu-id="e9da4-151">Functions with Parameters</span></span>

<span data-ttu-id="e9da4-152">Параметры можно использовать с функциями, в том числе с именованными параметрами, параметрами, параметрами и динамическими параметрами.</span><span class="sxs-lookup"><span data-stu-id="e9da4-152">You can use parameters with functions, including named parameters, positional parameters, switch parameters, and dynamic parameters.</span></span> <span data-ttu-id="e9da4-153">Дополнительные сведения о динамических параметрах в функциях см. в разделе [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="e9da4-153">For more information about dynamic parameters in functions, see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

### <a name="named-parameters"></a><span data-ttu-id="e9da4-154">именованных параметров</span><span class="sxs-lookup"><span data-stu-id="e9da4-154">Named Parameters</span></span>

<span data-ttu-id="e9da4-155">Можно определить любое количество именованных параметров.</span><span class="sxs-lookup"><span data-stu-id="e9da4-155">You can define any number of named parameters.</span></span> <span data-ttu-id="e9da4-156">Можно включить значение по умолчанию для именованных параметров, как описано далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="e9da4-156">You can include a default value for named parameters, as described later in this topic.</span></span>

<span data-ttu-id="e9da4-157">Параметры внутри фигурных скобок можно определить с помощью `Param` ключевого слова, как показано в следующем примере синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="e9da4-157">You can define parameters inside the braces using the `Param` keyword, as shown in the following sample syntax:</span></span>

```
function <name> {
  param ([type]$parameter1[,[type]$parameter2])
  <statement list>
}
```

<span data-ttu-id="e9da4-158">Можно также определить параметры за пределами фигурных скобок без `Param` ключевого слова, как показано в следующем примере синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="e9da4-158">You can also define parameters outside the braces without the `Param` keyword, as shown in the following sample syntax:</span></span>

```powershell
function <name> [([type]$parameter1[,[type]$parameter2])] {
  <statement list>
}
```

<span data-ttu-id="e9da4-159">Ниже приведен пример альтернативного синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="e9da4-159">Below is an example of this alternative syntax.</span></span>

```powershell
Function Add-Numbers($one, $two) {
    $one + $two
}
```

<span data-ttu-id="e9da4-160">Хотя первый метод является предпочтительным, разница между этими двумя методами отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e9da4-160">While the first method is preferred, there is no difference between these two methods.</span></span>

<span data-ttu-id="e9da4-161">При запуске функции значение, указываемое для параметра, присваивается переменной, содержащей имя параметра.</span><span class="sxs-lookup"><span data-stu-id="e9da4-161">When you run the function, the value you supply for a parameter is assigned to a variable that contains the parameter name.</span></span> <span data-ttu-id="e9da4-162">Значение этой переменной может использоваться в функции.</span><span class="sxs-lookup"><span data-stu-id="e9da4-162">The value of that variable can be used in the function.</span></span>

<span data-ttu-id="e9da4-163">В следующем примере показана функция с именем `Get-SmallFiles` .</span><span class="sxs-lookup"><span data-stu-id="e9da4-163">The following example is a function called `Get-SmallFiles`.</span></span> <span data-ttu-id="e9da4-164">Эта функция имеет `$Size` параметр.</span><span class="sxs-lookup"><span data-stu-id="e9da4-164">This function has a `$Size` parameter.</span></span> <span data-ttu-id="e9da4-165">Функция отображает все файлы, размер которых меньше значения `$Size` параметра, и исключает каталоги.</span><span class="sxs-lookup"><span data-stu-id="e9da4-165">The function displays all the files that are smaller than the value of the `$Size` parameter, and it excludes directories:</span></span>

```powershell
function Get-SmallFiles {
  Param($Size)
  Get-ChildItem $HOME | Where-Object {
    $_.Length -lt $Size -and !$_.PSIsContainer
  }
}
```

<span data-ttu-id="e9da4-166">В функции можно использовать `$Size` переменную, которая является именем, определенным для параметра.</span><span class="sxs-lookup"><span data-stu-id="e9da4-166">In the function, you can use the `$Size` variable, which is the name defined for the parameter.</span></span>

<span data-ttu-id="e9da4-167">Чтобы использовать эту функцию, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e9da4-167">To use this function, type the following command:</span></span>

```powershell
Get-SmallFiles -Size 50
```

<span data-ttu-id="e9da4-168">Можно также ввести значение для именованного параметра без имени параметра.</span><span class="sxs-lookup"><span data-stu-id="e9da4-168">You can also enter a value for a named parameter without the parameter name.</span></span>
<span data-ttu-id="e9da4-169">Например, следующая команда дает тот же результат, что и команда, которая присваивает имя параметру **size** :</span><span class="sxs-lookup"><span data-stu-id="e9da4-169">For example, the following command gives the same result as a command that names the **Size** parameter:</span></span>

```powershell
Get-SmallFiles 50
```

<span data-ttu-id="e9da4-170">Чтобы определить значение по умолчанию для параметра, введите знак равенства и значение после имени параметра, как показано в следующем варианте `Get-SmallFiles` примера:</span><span class="sxs-lookup"><span data-stu-id="e9da4-170">To define a default value for a parameter, type an equal sign and the value after the parameter name, as shown in the following variation of the `Get-SmallFiles` example:</span></span>

```powershell
function Get-SmallFiles ($Size = 100) {
  Get-ChildItem $HOME | Where-Object {
    $_.Length -lt $Size -and !$_.PSIsContainer
  }
}
```

<span data-ttu-id="e9da4-171">Если ввести `Get-SmallFiles` без значения, функция присваивает 100 значение `$size` .</span><span class="sxs-lookup"><span data-stu-id="e9da4-171">If you type `Get-SmallFiles` without a value, the function assigns 100 to `$size`.</span></span> <span data-ttu-id="e9da4-172">Если указать значение, то функция использует это значение.</span><span class="sxs-lookup"><span data-stu-id="e9da4-172">If you provide a value, the function uses that value.</span></span>

<span data-ttu-id="e9da4-173">При необходимости можно указать краткую строку справки, описывающую значение параметра по умолчанию, добавив атрибут **псдефаултвалуе** в описание параметра и указав свойство **Help** объекта **псдефаултвалуе**.</span><span class="sxs-lookup"><span data-stu-id="e9da4-173">Optionally, you can provide a brief help string that describes the default value of your parameter, by adding the **PSDefaultValue** attribute to the description of your parameter, and specifying the **Help** property of **PSDefaultValue**.</span></span> <span data-ttu-id="e9da4-174">Чтобы предоставить строку справки, описывающую значение по умолчанию (100) параметра **size** в `Get-SmallFiles` функции, добавьте атрибут **псдефаултвалуе** , как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="e9da4-174">To provide a help string that describes the default value (100) of the **Size** parameter in the `Get-SmallFiles` function, add the **PSDefaultValue** attribute as shown in the following example.</span></span>

```powershell
function Get-SmallFiles {
  param (
      [PSDefaultValue(Help = '100')]
      $Size = 100
  )
}
```

<span data-ttu-id="e9da4-175">Дополнительные сведения о классе атрибута **псдефаултвалуе** см. в разделе [псдефаултвалуе Attribute Members](/dotnet/api/system.management.automation.psdefaultvalueattribute).</span><span class="sxs-lookup"><span data-stu-id="e9da4-175">For more information about the **PSDefaultValue** attribute class, see [PSDefaultValue Attribute Members](/dotnet/api/system.management.automation.psdefaultvalueattribute).</span></span>

### <a name="positional-parameters"></a><span data-ttu-id="e9da4-176">Параметры позиционирования</span><span class="sxs-lookup"><span data-stu-id="e9da4-176">Positional Parameters</span></span>

<span data-ttu-id="e9da4-177">Параметр с заданной позицией — это параметр без имени параметра.</span><span class="sxs-lookup"><span data-stu-id="e9da4-177">A positional parameter is a parameter without a parameter name.</span></span> <span data-ttu-id="e9da4-178">PowerShell использует порядок значений параметра, чтобы связать каждое значение параметра с параметром в функции.</span><span class="sxs-lookup"><span data-stu-id="e9da4-178">PowerShell uses the parameter value order to associate each parameter value with a parameter in the function.</span></span>

<span data-ttu-id="e9da4-179">При использовании позиционированных параметров введите одно или несколько значений после имени функции.</span><span class="sxs-lookup"><span data-stu-id="e9da4-179">When you use positional parameters, type one or more values after the function name.</span></span> <span data-ttu-id="e9da4-180">Значения позиционированных параметров присваиваются `$args` переменной массива.</span><span class="sxs-lookup"><span data-stu-id="e9da4-180">Positional parameter values are assigned to the `$args` array variable.</span></span>
<span data-ttu-id="e9da4-181">Значение, следующее за именем функции, присваивается первой положению в `$args` массиве, `$args[0]` .</span><span class="sxs-lookup"><span data-stu-id="e9da4-181">The value that follows the function name is assigned to the first position in the `$args` array, `$args[0]`.</span></span>

<span data-ttu-id="e9da4-182">Следующая `Get-Extension` функция добавляет `.txt` расширение имени файла к указанному имени файла:</span><span class="sxs-lookup"><span data-stu-id="e9da4-182">The following `Get-Extension` function adds the `.txt` file name extension to a file name that you supply:</span></span>

```powershell
function Get-Extension {
  $name = $args[0] + ".txt"
  $name
}
```

```powershell
Get-Extension myTextFile
```

```Output
myTextFile.txt
```

### <a name="switch-parameters"></a><span data-ttu-id="e9da4-183">Параметры переключателя</span><span class="sxs-lookup"><span data-stu-id="e9da4-183">Switch Parameters</span></span>

<span data-ttu-id="e9da4-184">Переключатель — это параметр, который не требует значения.</span><span class="sxs-lookup"><span data-stu-id="e9da4-184">A switch is a parameter that does not require a value.</span></span> <span data-ttu-id="e9da4-185">Вместо этого введите имя функции, за которым следует имя параметра переключателя.</span><span class="sxs-lookup"><span data-stu-id="e9da4-185">Instead, you type the function name followed by the name of the switch parameter.</span></span>

<span data-ttu-id="e9da4-186">Чтобы определить параметр переключателя, укажите тип `[switch]` перед именем параметра, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e9da4-186">To define a switch parameter, specify the type `[switch]` before the parameter name, as shown in the following example:</span></span>

```powershell
function Switch-Item {
  param ([switch]$on)
  if ($on) { "Switch on" }
  else { "Switch off" }
}
```

<span data-ttu-id="e9da4-187">При вводе `On` параметра Switch после имени функции функция отображает параметр on.</span><span class="sxs-lookup"><span data-stu-id="e9da4-187">When you type the `On` switch parameter after the function name, the function displays "Switch on".</span></span> <span data-ttu-id="e9da4-188">Без параметра Switch отображается значение "Отключить выключение".</span><span class="sxs-lookup"><span data-stu-id="e9da4-188">Without the switch parameter, it displays "Switch off".</span></span>

```powershell
Switch-Item -on
```

```Output
Switch on
```

```powershell
Switch-Item
```

```Output
Switch off
```

<span data-ttu-id="e9da4-189">При выполнении функции можно также присвоить **логическое** значение параметру, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e9da4-189">You can also assign a **Boolean** value to a switch when you run the function, as shown in the following example:</span></span>

```powershell
Switch-Item -on:$true
```

```Output
Switch on
```

```powershell
Switch-Item -on:$false
```

```Output
Switch off
```

## <a name="using-splatting-to-represent-command-parameters"></a><span data-ttu-id="e9da4-190">Использование Сплаттинг для представления параметров команды</span><span class="sxs-lookup"><span data-stu-id="e9da4-190">Using Splatting to Represent Command Parameters</span></span>

<span data-ttu-id="e9da4-191">Сплаттинг можно использовать для представления параметров команды.</span><span class="sxs-lookup"><span data-stu-id="e9da4-191">You can use splatting to represent the parameters of a command.</span></span> <span data-ttu-id="e9da4-192">Эта функция появилась в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="e9da4-192">This feature is introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="e9da4-193">Используйте этот метод в функциях, вызывающих команды в сеансе.</span><span class="sxs-lookup"><span data-stu-id="e9da4-193">Use this technique in functions that call commands in the session.</span></span> <span data-ttu-id="e9da4-194">Вам не нужно объявлять или перечислять параметры команды или изменять функцию при изменении параметров команды.</span><span class="sxs-lookup"><span data-stu-id="e9da4-194">You do not need to declare or enumerate the command parameters, or change the function when command parameters change.</span></span>

<span data-ttu-id="e9da4-195">Следующий пример функции вызывает `Get-Command` командлет.</span><span class="sxs-lookup"><span data-stu-id="e9da4-195">The following sample function calls the `Get-Command` cmdlet.</span></span> <span data-ttu-id="e9da4-196">Команда использует `@Args` для представления параметров `Get-Command` .</span><span class="sxs-lookup"><span data-stu-id="e9da4-196">The command uses `@Args` to represent the parameters of `Get-Command`.</span></span>

```powershell
function Get-MyCommand { Get-Command @Args }
```

<span data-ttu-id="e9da4-197">`Get-Command`При вызове функции можно использовать все параметры `Get-MyCommand` .</span><span class="sxs-lookup"><span data-stu-id="e9da4-197">You can use all of the parameters of `Get-Command` when you call the `Get-MyCommand` function.</span></span> <span data-ttu-id="e9da4-198">Параметры и значения параметров передаются в команду с помощью команды `@Args` .</span><span class="sxs-lookup"><span data-stu-id="e9da4-198">The parameters and parameter values are passed to the command using `@Args`.</span></span>

```powershell
Get-MyCommand -Name Get-ChildItem
```

```Output
CommandType     Name                ModuleName
-----------     ----                ----------
Cmdlet          Get-ChildItem       Microsoft.PowerShell.Management
```

<span data-ttu-id="e9da4-199">Эта `@Args` функция использует `$Args` Автоматический параметр, представляющий необъявленные параметры и значения командлета из оставшихся аргументов.</span><span class="sxs-lookup"><span data-stu-id="e9da4-199">The `@Args` feature uses the `$Args` automatic parameter, which represents undeclared cmdlet parameters and values from remaining arguments.</span></span>

<span data-ttu-id="e9da4-200">Дополнительные сведения о Сплаттинг см. в разделе [about_Splatting](about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="e9da4-200">For more information about splatting, see [about_Splatting](about_Splatting.md).</span></span>

## <a name="piping-objects-to-functions"></a><span data-ttu-id="e9da4-201">Передача объектов в функции</span><span class="sxs-lookup"><span data-stu-id="e9da4-201">Piping Objects to Functions</span></span>

<span data-ttu-id="e9da4-202">Любая функция может принимать входные данные из конвейера.</span><span class="sxs-lookup"><span data-stu-id="e9da4-202">Any function can take input from the pipeline.</span></span> <span data-ttu-id="e9da4-203">Можно контролировать, как функция обрабатывает входные данные из конвейера с помощью `Begin` `Process` `End` ключевых слов, и.</span><span class="sxs-lookup"><span data-stu-id="e9da4-203">You can control how a function processes input from the pipeline using `Begin`, `Process`, and `End` keywords.</span></span> <span data-ttu-id="e9da4-204">В следующем образце синтаксиса показаны три ключевых слова:</span><span class="sxs-lookup"><span data-stu-id="e9da4-204">The following sample syntax shows the three keywords:</span></span>

```
function <name> {
  begin {<statement list>}
  process {<statement list>}
  end {<statement list>}
}
```

<span data-ttu-id="e9da4-205">`Begin`Список инструкций выполняется только один раз в начале функции.</span><span class="sxs-lookup"><span data-stu-id="e9da4-205">The `Begin` statement list runs one time only, at the beginning of the function.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e9da4-206">Если функция определяет `Begin` блок, то `Process` `End` весь код должен находиться внутри этих блоков.</span><span class="sxs-lookup"><span data-stu-id="e9da4-206">If your function defines a `Begin`, `Process` or `End` block, all of your code must reside inside those blocks.</span></span> <span data-ttu-id="e9da4-207">Код не будет располагаться за пределами блоков, если определены *какие либо* блоки.</span><span class="sxs-lookup"><span data-stu-id="e9da4-207">No code will be recognized outside the blocks if *any* of the blocks are defined.</span></span>

<span data-ttu-id="e9da4-208">`Process`Список инструкций выполняется один раз для каждого объекта в конвейере.</span><span class="sxs-lookup"><span data-stu-id="e9da4-208">The `Process` statement list runs one time for each object in the pipeline.</span></span>
<span data-ttu-id="e9da4-209">Во время `Process` выполнения блока каждый объект конвейера назначается `$_` автоматической переменной, по одному объекту конвейера за раз.</span><span class="sxs-lookup"><span data-stu-id="e9da4-209">While the `Process` block is running, each pipeline object is assigned to the `$_` automatic variable, one pipeline object at a time.</span></span>

<span data-ttu-id="e9da4-210">После того как функция получит все объекты в конвейере, `End` список инструкций будет выполняться один раз.</span><span class="sxs-lookup"><span data-stu-id="e9da4-210">After the function receives all the objects in the pipeline, the `End` statement list runs one time.</span></span> <span data-ttu-id="e9da4-211">Если не `Begin` `Process` `End` используются ключевые слова, или, все инструкции рассматриваются как `End` список инструкций.</span><span class="sxs-lookup"><span data-stu-id="e9da4-211">If no `Begin`, `Process`, or `End` keywords are used, all the statements are treated like an `End` statement list.</span></span>

<span data-ttu-id="e9da4-212">Следующая функция использует `Process` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="e9da4-212">The following function uses the `Process` keyword.</span></span> <span data-ttu-id="e9da4-213">Функция отображает примеры из конвейера:</span><span class="sxs-lookup"><span data-stu-id="e9da4-213">The function displays examples from the pipeline:</span></span>

```powershell
function Get-Pipeline
{
  process {"The value is: $_"}
}
```

<span data-ttu-id="e9da4-214">Чтобы продемонстрировать эту функцию, введите список чисел, разделенных запятыми, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e9da4-214">To demonstrate this function, enter an list of numbers separated by commas, as shown in the following example:</span></span>

```powershell
1,2,4 | Get-Pipeline
```

```Output
The value is: 1
The value is: 2
The value is: 4
```

<span data-ttu-id="e9da4-215">При использовании функции в конвейере объекты, переданный функции, назначаются `$input` автоматической переменной.</span><span class="sxs-lookup"><span data-stu-id="e9da4-215">When you use a function in a pipeline, the objects piped to the function are assigned to the `$input` automatic variable.</span></span> <span data-ttu-id="e9da4-216">Функция выполняет инструкции с `Begin` ключевым словом перед тем, как все объекты поступают из конвейера.</span><span class="sxs-lookup"><span data-stu-id="e9da4-216">The function runs statements with the `Begin` keyword before any objects come from the pipeline.</span></span> <span data-ttu-id="e9da4-217">Функция выполняет инструкции с `End` ключевым словом после того, как все объекты были получены из конвейера.</span><span class="sxs-lookup"><span data-stu-id="e9da4-217">The function runs statements with the `End` keyword after all the objects have been received from the pipeline.</span></span>

<span data-ttu-id="e9da4-218">В следующем примере показана `$input` Автоматическая переменная с `Begin` `End` ключевыми словами и.</span><span class="sxs-lookup"><span data-stu-id="e9da4-218">The following example shows the `$input` automatic variable with `Begin` and `End` keywords.</span></span>

```powershell
function Get-PipelineBeginEnd
{
  begin {"Begin: The input is $input"}
  end {"End:   The input is $input" }
}
```

<span data-ttu-id="e9da4-219">Если эта функция выполняется с помощью конвейера, отображаются следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="e9da4-219">If this function is run by using the pipeline, it displays the following results:</span></span>

```powershell
1,2,4 | Get-PipelineBeginEnd
```

```Output
Begin: The input is
End:   The input is 1 2 4
```

<span data-ttu-id="e9da4-220">При `Begin` выполнении инструкции функция не имеет входных данных из конвейера.</span><span class="sxs-lookup"><span data-stu-id="e9da4-220">When the `Begin` statement runs, the function does not have the input from the pipeline.</span></span> <span data-ttu-id="e9da4-221">`End`Инструкция выполняется после того, как функция применяет значения.</span><span class="sxs-lookup"><span data-stu-id="e9da4-221">The `End` statement runs after the function has the values.</span></span>

<span data-ttu-id="e9da4-222">Если у функции есть `Process` ключевое слово, каждый объект в удаляется `$input` из `$input` и присваивается `$_` .</span><span class="sxs-lookup"><span data-stu-id="e9da4-222">If the function has a `Process` keyword, each object in `$input` is removed from `$input` and assigned to `$_`.</span></span> <span data-ttu-id="e9da4-223">В следующем примере содержится `Process` список операторов:</span><span class="sxs-lookup"><span data-stu-id="e9da4-223">The following example has a `Process` statement list:</span></span>

```powershell
function Get-PipelineInput
{
  process {"Processing:  $_ " }
  end {"End:   The input is: $input" }
}
```

<span data-ttu-id="e9da4-224">В этом примере каждый объект, передаваемый функции, отправляется в `Process` список инструкций.</span><span class="sxs-lookup"><span data-stu-id="e9da4-224">In this example, each object that is piped to the function is sent to the `Process` statement list.</span></span> <span data-ttu-id="e9da4-225">`Process`Инструкции выполняются для каждого объекта, по одному объекту за раз.</span><span class="sxs-lookup"><span data-stu-id="e9da4-225">The `Process` statements run on each object, one object at a time.</span></span> <span data-ttu-id="e9da4-226">`$input`Автоматическая переменная пуста, если функция достигает `End` ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="e9da4-226">The `$input` automatic variable is empty when the function reaches the `End` keyword.</span></span>

```powershell
1,2,4 | Get-PipelineInput
```

```Output
Processing:  1
Processing:  2
Processing:  4
End:   The input is:
```

<span data-ttu-id="e9da4-227">Дополнительные сведения см. [в разделе Использование перечислителей](about_Automatic_Variables.md#using-enumerators) .</span><span class="sxs-lookup"><span data-stu-id="e9da4-227">For more information, see [Using Enumerators](about_Automatic_Variables.md#using-enumerators)</span></span>

## <a name="filters"></a><span data-ttu-id="e9da4-228">Фильтры</span><span class="sxs-lookup"><span data-stu-id="e9da4-228">Filters</span></span>

<span data-ttu-id="e9da4-229">Фильтр — это тип функции, которая выполняется для каждого объекта в конвейере.</span><span class="sxs-lookup"><span data-stu-id="e9da4-229">A filter is a type of function that runs on each object in the pipeline.</span></span> <span data-ttu-id="e9da4-230">Фильтр напоминает функцию со всеми ее операторами в `Process` блоке.</span><span class="sxs-lookup"><span data-stu-id="e9da4-230">A filter resembles a function with all its statements in a `Process` block.</span></span>

<span data-ttu-id="e9da4-231">Синтаксис фильтра выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e9da4-231">The syntax of a filter is as follows:</span></span>

```
filter [<scope:>]<name> {<statement list>}
```

<span data-ttu-id="e9da4-232">Следующий фильтр принимает записи журнала из конвейера, а затем отображает всю запись или только часть сообщения в записи:</span><span class="sxs-lookup"><span data-stu-id="e9da4-232">The following filter takes log entries from the pipeline and then displays either the whole entry or only the message portion of the entry:</span></span>

```powershell
filter Get-ErrorLog ([switch]$message)
{
  if ($message) { Out-Host -InputObject $_.Message }
  else { $_ }
}
```

## <a name="function-scope"></a><span data-ttu-id="e9da4-233">Область действия функции</span><span class="sxs-lookup"><span data-stu-id="e9da4-233">Function Scope</span></span>

<span data-ttu-id="e9da4-234">Функция существует в области, в которой она была создана.</span><span class="sxs-lookup"><span data-stu-id="e9da4-234">A function exists in the scope in which it was created.</span></span>

<span data-ttu-id="e9da4-235">Если функция является частью скрипта, функция доступна для инструкций внутри этого скрипта.</span><span class="sxs-lookup"><span data-stu-id="e9da4-235">If a function is part of a script, the function is available to statements within that script.</span></span> <span data-ttu-id="e9da4-236">По умолчанию функция в скрипте недоступна в командной строке.</span><span class="sxs-lookup"><span data-stu-id="e9da4-236">By default, a function in a script is not available at the command prompt.</span></span>

<span data-ttu-id="e9da4-237">Можно указать область функции.</span><span class="sxs-lookup"><span data-stu-id="e9da4-237">You can specify the scope of a function.</span></span> <span data-ttu-id="e9da4-238">Например, функция добавляется в глобальную область в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e9da4-238">For example, the function is added to the global scope in the following example:</span></span>

```powershell
function global:Get-DependentSvs {
  Get-Service | Where-Object {$_.DependentServices}
}
```

<span data-ttu-id="e9da4-239">Если функция находится в глобальной области, ее можно использовать в скриптах, функциях и в командной строке.</span><span class="sxs-lookup"><span data-stu-id="e9da4-239">When a function is in the global scope, you can use the function in scripts, in functions, and at the command line.</span></span>

<span data-ttu-id="e9da4-240">Обычно функции создают область.</span><span class="sxs-lookup"><span data-stu-id="e9da4-240">Functions normally create a scope.</span></span> <span data-ttu-id="e9da4-241">Элементы, созданные в функции, такие как переменные, существуют только в области видимости функции.</span><span class="sxs-lookup"><span data-stu-id="e9da4-241">The items created in a function, such as variables, exist only in the function scope.</span></span>

<span data-ttu-id="e9da4-242">Дополнительные сведения об области действия в PowerShell см. в разделе [about_Scopes](about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="e9da4-242">For more information about scope in PowerShell, see [about_Scopes](about_Scopes.md).</span></span>

## <a name="finding-and-managing-functions-using-the-function-drive"></a><span data-ttu-id="e9da4-243">Поиск функций и управление ими с помощью диска Function:</span><span class="sxs-lookup"><span data-stu-id="e9da4-243">Finding and Managing Functions Using the Function: Drive</span></span>

<span data-ttu-id="e9da4-244">Все функции и фильтры в PowerShell автоматически сохраняются на `Function:` диске.</span><span class="sxs-lookup"><span data-stu-id="e9da4-244">All the functions and filters in PowerShell are automatically stored in the `Function:` drive.</span></span> <span data-ttu-id="e9da4-245">Этот диск предоставляется поставщиком **функций** PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e9da4-245">This drive is exposed by the PowerShell **Function** provider.</span></span>

<span data-ttu-id="e9da4-246">При обращении к `Function:` диску введите двоеточие после **функции** , как при обращении к `C` диску или на `D` диске компьютера.</span><span class="sxs-lookup"><span data-stu-id="e9da4-246">When referring to the `Function:` drive, type a colon after **Function** , just as you would do when referencing the `C` or `D` drive of a computer.</span></span>

<span data-ttu-id="e9da4-247">Следующая команда отображает все функции в текущем сеансе PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e9da4-247">The following command displays all the functions in the current session of PowerShell:</span></span>

```powershell
Get-ChildItem function:
```

<span data-ttu-id="e9da4-248">Команды в функции хранятся в виде блока скрипта в свойстве определения функции.</span><span class="sxs-lookup"><span data-stu-id="e9da4-248">The commands in the function are stored as a script block in the definition property of the function.</span></span> <span data-ttu-id="e9da4-249">Например, чтобы отобразить команды в функции справки, поставляемой с PowerShell, введите:</span><span class="sxs-lookup"><span data-stu-id="e9da4-249">For example, to display the commands in the Help function that comes with PowerShell, type:</span></span>

```powershell
(Get-ChildItem function:help).Definition
```

<span data-ttu-id="e9da4-250">Можно также использовать следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="e9da4-250">You can also use the following syntax.</span></span>

```powershell
$function:help
```

<span data-ttu-id="e9da4-251">Дополнительные сведения о `Function:` диске см. в разделе справки по поставщику **функций** .</span><span class="sxs-lookup"><span data-stu-id="e9da4-251">For more information about the `Function:` drive, see the help topic for the **Function** provider.</span></span> <span data-ttu-id="e9da4-252">Введите `Get-Help Function`.</span><span class="sxs-lookup"><span data-stu-id="e9da4-252">Type `Get-Help Function`.</span></span>

## <a name="reusing-functions-in-new-sessions"></a><span data-ttu-id="e9da4-253">Повторное использование функций в новых сеансах</span><span class="sxs-lookup"><span data-stu-id="e9da4-253">Reusing Functions in New Sessions</span></span>

<span data-ttu-id="e9da4-254">При вводе функции в командной строке PowerShell функция станет частью текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="e9da4-254">When you type a function at the PowerShell command prompt, the function becomes part of the current session.</span></span> <span data-ttu-id="e9da4-255">Он доступен до завершения сеанса.</span><span class="sxs-lookup"><span data-stu-id="e9da4-255">It is available until the session ends.</span></span>

<span data-ttu-id="e9da4-256">Чтобы использовать функцию во всех сеансах PowerShell, добавьте функцию в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e9da4-256">To use your function in all PowerShell sessions, add the function to your PowerShell profile.</span></span> <span data-ttu-id="e9da4-257">Дополнительные сведения о профилях см. в разделе [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="e9da4-257">For more information about profiles, see [about_Profiles](about_Profiles.md).</span></span>

<span data-ttu-id="e9da4-258">Можно также сохранить функцию в файле сценария PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e9da4-258">You can also save your function in a PowerShell script file.</span></span> <span data-ttu-id="e9da4-259">Введите функцию в текстовом файле, а затем сохраните файл с `.ps1` расширением имени файла.</span><span class="sxs-lookup"><span data-stu-id="e9da4-259">Type your function in a text file, and then save the file with the `.ps1` file name extension.</span></span>

## <a name="writing-help-for-functions"></a><span data-ttu-id="e9da4-260">Написание справки для функций</span><span class="sxs-lookup"><span data-stu-id="e9da4-260">Writing Help for Functions</span></span>

<span data-ttu-id="e9da4-261">`Get-Help`Командлет возвращает справку по функциям, а также к командлетам, поставщикам и скриптам.</span><span class="sxs-lookup"><span data-stu-id="e9da4-261">The `Get-Help` cmdlet gets help for functions, as well as for cmdlets, providers, and scripts.</span></span> <span data-ttu-id="e9da4-262">Чтобы получить справку по функции, введите, `Get-Help` за которым следует имя функции.</span><span class="sxs-lookup"><span data-stu-id="e9da4-262">To get help for a function, type `Get-Help` followed by the function name.</span></span>

<span data-ttu-id="e9da4-263">Например, чтобы получить справку по `Get-MyDisks` функции, введите:</span><span class="sxs-lookup"><span data-stu-id="e9da4-263">For example, to get help for the `Get-MyDisks` function, type:</span></span>

```powershell
Get-Help Get-MyDisks
```

<span data-ttu-id="e9da4-264">Вы можете написать справку для функции с помощью любого из двух следующих методов:</span><span class="sxs-lookup"><span data-stu-id="e9da4-264">You can write help for a function by using either of the two following methods:</span></span>

- <span data-ttu-id="e9da4-265">Comment-Based справки по функциям</span><span class="sxs-lookup"><span data-stu-id="e9da4-265">Comment-Based Help for Functions</span></span>

  <span data-ttu-id="e9da4-266">Создайте раздел справки, используя специальные ключевые слова в комментариях.</span><span class="sxs-lookup"><span data-stu-id="e9da4-266">Create a help topic by using special keywords in the comments.</span></span> <span data-ttu-id="e9da4-267">Чтобы создать справку на основе комментариев для функции, комментарии должны располагаться в начале или в конце тела функции или в строках, предшествующих ключевому слову Function.</span><span class="sxs-lookup"><span data-stu-id="e9da4-267">To create comment-based help for a function, the comments must be placed at the beginning or end of the function body or on the lines preceding the function keyword.</span></span> <span data-ttu-id="e9da4-268">Дополнительные сведения о справке на основе комментариев см. в разделе [about_Comment_Based_Help](about_Comment_Based_Help.md).</span><span class="sxs-lookup"><span data-stu-id="e9da4-268">For more information about comment-based help, see [about_Comment_Based_Help](about_Comment_Based_Help.md).</span></span>

- <span data-ttu-id="e9da4-269">XML-Based справки по функциям</span><span class="sxs-lookup"><span data-stu-id="e9da4-269">XML-Based Help for Functions</span></span>

  <span data-ttu-id="e9da4-270">Создайте раздел справки на основе XML, например тип, который обычно создается для командлетов.</span><span class="sxs-lookup"><span data-stu-id="e9da4-270">Create an XML-based help topic, such as the type that is typically created for cmdlets.</span></span> <span data-ttu-id="e9da4-271">При локализации разделов справки на несколько языков требуется справка на основе XML.</span><span class="sxs-lookup"><span data-stu-id="e9da4-271">XML-based help is required if you are localizing help topics into multiple languages.</span></span>

  <span data-ttu-id="e9da4-272">Чтобы связать функцию с разделом справки на основе XML, используйте `.ExternalHelp` ключевое слово справки на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="e9da4-272">To associate the function with the XML-based help topic, use the `.ExternalHelp` comment-based help keyword.</span></span> <span data-ttu-id="e9da4-273">Без этого ключевого слова `Get-Help` не удается найти раздел справки по функциям и вызовы для `Get-Help` функции, возвращающие только автоматически созданную справку.</span><span class="sxs-lookup"><span data-stu-id="e9da4-273">Without this keyword, `Get-Help` cannot find the function help topic and calls to `Get-Help` for the function return only auto-generated help.</span></span>

  <span data-ttu-id="e9da4-274">Дополнительные сведения о `ExternalHelp` ключевом слове см. в разделе [about_Comment_Based_Help](about_Comment_Based_Help.md).</span><span class="sxs-lookup"><span data-stu-id="e9da4-274">For more information about the `ExternalHelp` keyword, see [about_Comment_Based_Help](about_Comment_Based_Help.md).</span></span> <span data-ttu-id="e9da4-275">Дополнительные сведения о справке на основе XML см. [в разделе как написать справку по командлетам](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).</span><span class="sxs-lookup"><span data-stu-id="e9da4-275">For more information about XML-based help, see [How to Write Cmdlet Help](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).</span></span>

## <a name="see-also"></a><span data-ttu-id="e9da4-276">См. также</span><span class="sxs-lookup"><span data-stu-id="e9da4-276">See also</span></span>

[<span data-ttu-id="e9da4-277">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="e9da4-277">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="e9da4-278">about_Comment_Based_Help</span><span class="sxs-lookup"><span data-stu-id="e9da4-278">about_Comment_Based_Help</span></span>](about_Comment_Based_Help.md)

[<span data-ttu-id="e9da4-279">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="e9da4-279">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="e9da4-280">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="e9da4-280">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="e9da4-281">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="e9da4-281">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="e9da4-282">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="e9da4-282">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="e9da4-283">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="e9da4-283">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)

[<span data-ttu-id="e9da4-284">about_Parameters</span><span class="sxs-lookup"><span data-stu-id="e9da4-284">about_Parameters</span></span>](about_Parameters.md)

[<span data-ttu-id="e9da4-285">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="e9da4-285">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="e9da4-286">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="e9da4-286">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="e9da4-287">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="e9da4-287">about_Script_Blocks</span></span>](about_Script_Blocks.md)

[<span data-ttu-id="e9da4-288">about_Function_provider</span><span class="sxs-lookup"><span data-stu-id="e9da4-288">about_Function_provider</span></span>](about_Function_provider.md)
