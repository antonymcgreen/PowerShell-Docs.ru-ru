---
description: Описание создания и использования функций в PowerShell.
Locale: en-US
ms.date: 02/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions
ms.openlocfilehash: d51c4d0bbf728bb23b4a5452d5192a262b722758
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602873"
---
# <a name="about-functions"></a><span data-ttu-id="60bff-103">О функциях</span><span class="sxs-lookup"><span data-stu-id="60bff-103">About Functions</span></span>

## <a name="short-description"></a><span data-ttu-id="60bff-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="60bff-104">Short description</span></span>

<span data-ttu-id="60bff-105">Описание создания и использования функций в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="60bff-105">Describes how to create and use functions in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="60bff-106">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="60bff-106">Long description</span></span>

<span data-ttu-id="60bff-107">Функция — это список операторов PowerShell с назначенным именем.</span><span class="sxs-lookup"><span data-stu-id="60bff-107">A function is a list of PowerShell statements that has a name that you assign.</span></span> <span data-ttu-id="60bff-108">При запуске функции необходимо ввести имя функции.</span><span class="sxs-lookup"><span data-stu-id="60bff-108">When you run a function, you type the function name.</span></span> <span data-ttu-id="60bff-109">Инструкции в списке выполняются так, как если бы вы вводили их в командной строке.</span><span class="sxs-lookup"><span data-stu-id="60bff-109">The statements in the list run as if you had typed them at the command prompt.</span></span>

<span data-ttu-id="60bff-110">Функции могут быть простыми:</span><span class="sxs-lookup"><span data-stu-id="60bff-110">Functions can be as simple as:</span></span>

```powershell
function Get-PowerShellProcess { Get-Process PowerShell }
```

<span data-ttu-id="60bff-111">Функция также может быть сложной в качестве командлета или программы приложения.</span><span class="sxs-lookup"><span data-stu-id="60bff-111">A function can also be as complex as a cmdlet or an application program.</span></span>

<span data-ttu-id="60bff-112">Как и командлеты, функции могут иметь параметры.</span><span class="sxs-lookup"><span data-stu-id="60bff-112">Like cmdlets, functions can have parameters.</span></span> <span data-ttu-id="60bff-113">Параметры могут быть именованными, позиционированными, переключателями или динамическими параметрами.</span><span class="sxs-lookup"><span data-stu-id="60bff-113">The parameters can be named, positional, switch, or dynamic parameters.</span></span> <span data-ttu-id="60bff-114">Параметры функции можно считывать из командной строки или из конвейера.</span><span class="sxs-lookup"><span data-stu-id="60bff-114">Function parameters can be read from the command line or from the pipeline.</span></span>

<span data-ttu-id="60bff-115">Функции могут возвращать значения, которые могут быть отображены, назначены переменным или переданы другим функциям или командлетам.</span><span class="sxs-lookup"><span data-stu-id="60bff-115">Functions can return values that can be displayed, assigned to variables, or passed to other functions or cmdlets.</span></span> <span data-ttu-id="60bff-116">Также можно указать возвращаемое значение с помощью `return` ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="60bff-116">You can also specify a return value using the `return` keyword.</span></span> <span data-ttu-id="60bff-117">`return`Ключевое слово не влияет или не подавляет другие выходные данные, возвращаемые функцией.</span><span class="sxs-lookup"><span data-stu-id="60bff-117">The `return` keyword does not affect or suppress other output returned from your function.</span></span> <span data-ttu-id="60bff-118">Однако `return` ключевое слово завершает функцию в этой строке.</span><span class="sxs-lookup"><span data-stu-id="60bff-118">However, the `return` keyword exits the function at that line.</span></span> <span data-ttu-id="60bff-119">Дополнительные сведения см. в разделе [about_Return](about_Return.md).</span><span class="sxs-lookup"><span data-stu-id="60bff-119">For more information, see [about_Return](about_Return.md).</span></span>

<span data-ttu-id="60bff-120">Список операторов функции может содержать различные типы списков операторов с ключевыми словами `Begin` , `Process` и `End` .</span><span class="sxs-lookup"><span data-stu-id="60bff-120">The function's statement list can contain different types of statement lists with the keywords `Begin`, `Process`, and `End`.</span></span> <span data-ttu-id="60bff-121">Эти списки инструкций обработают входные данные из конвейера по-разному.</span><span class="sxs-lookup"><span data-stu-id="60bff-121">These statement lists handle input from the pipeline differently.</span></span>

<span data-ttu-id="60bff-122">Фильтр — это специальный тип функции, который использует `Filter` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="60bff-122">A filter is a special kind of function that uses the `Filter` keyword.</span></span>

<span data-ttu-id="60bff-123">Функции также могут действовать как командлеты.</span><span class="sxs-lookup"><span data-stu-id="60bff-123">Functions can also act like cmdlets.</span></span> <span data-ttu-id="60bff-124">Можно создать функцию, которая работает так же, как командлет, без использования `C#` программирования.</span><span class="sxs-lookup"><span data-stu-id="60bff-124">You can create a function that works just like a cmdlet without using `C#` programming.</span></span> <span data-ttu-id="60bff-125">Дополнительные сведения см. в разделе [about_Functions_Advanced](about_Functions_Advanced.md).</span><span class="sxs-lookup"><span data-stu-id="60bff-125">For more information, see [about_Functions_Advanced](about_Functions_Advanced.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="60bff-126">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="60bff-126">Syntax</span></span>

<span data-ttu-id="60bff-127">Ниже приведен синтаксис функции.</span><span class="sxs-lookup"><span data-stu-id="60bff-127">The following is the syntax for a function:</span></span>

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

<span data-ttu-id="60bff-128">Функция включает следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="60bff-128">A function includes the following items:</span></span>

- <span data-ttu-id="60bff-129">`Function`Ключевое слово</span><span class="sxs-lookup"><span data-stu-id="60bff-129">A `Function` keyword</span></span>
- <span data-ttu-id="60bff-130">Область (необязательно)</span><span class="sxs-lookup"><span data-stu-id="60bff-130">A scope (optional)</span></span>
- <span data-ttu-id="60bff-131">Выбранное имя</span><span class="sxs-lookup"><span data-stu-id="60bff-131">A name that you select</span></span>
- <span data-ttu-id="60bff-132">Любое количество именованных параметров (необязательно)</span><span class="sxs-lookup"><span data-stu-id="60bff-132">Any number of named parameters (optional)</span></span>
- <span data-ttu-id="60bff-133">Одна или несколько команд PowerShell, заключенных в фигурные скобки `{}`</span><span class="sxs-lookup"><span data-stu-id="60bff-133">One or more PowerShell commands enclosed in braces `{}`</span></span>

<span data-ttu-id="60bff-134">Дополнительные сведения о `Dynamicparam` ключевом слове и динамических параметрах в функциях см. в разделе [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="60bff-134">For more information about the `Dynamicparam` keyword and dynamic parameters in functions, see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

## <a name="simple-functions"></a><span data-ttu-id="60bff-135">Простые функции</span><span class="sxs-lookup"><span data-stu-id="60bff-135">Simple Functions</span></span>

<span data-ttu-id="60bff-136">Функции не обязательно должны быть очень сложными.</span><span class="sxs-lookup"><span data-stu-id="60bff-136">Functions do not have to be complicated to be useful.</span></span> <span data-ttu-id="60bff-137">Простейшие функции имеют следующий формат:</span><span class="sxs-lookup"><span data-stu-id="60bff-137">The simplest functions have the following format:</span></span>

```
function <function-name> {statements}
```

<span data-ttu-id="60bff-138">Например, следующая функция запускает PowerShell с параметром Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="60bff-138">For example, the following function starts PowerShell with the Run as Administrator option.</span></span>

```powershell
function Start-PSAdmin {Start-Process PowerShell -Verb RunAs}
```

<span data-ttu-id="60bff-139">Чтобы использовать функцию, введите: `Start-PSAdmin`</span><span class="sxs-lookup"><span data-stu-id="60bff-139">To use the function, type: `Start-PSAdmin`</span></span>

<span data-ttu-id="60bff-140">Чтобы добавить операторы в функцию, введите каждую инструкцию в отдельной строке или используйте точку с запятой `;` для разделения инструкций.</span><span class="sxs-lookup"><span data-stu-id="60bff-140">To add statements to the function, type each statement on a separate line, or use a semi-colon `;` to separate the statements.</span></span>

<span data-ttu-id="60bff-141">Например, следующая функция находит все `.jpg` файлы в каталогах текущего пользователя, которые были изменены после начальной даты.</span><span class="sxs-lookup"><span data-stu-id="60bff-141">For example, the following function finds all `.jpg` files in the current user's directories that were changed after the start date.</span></span>

```powershell
function Get-NewPix
{
  $start = Get-Date -Month 1 -Day 1 -Year 2010
  $allpix = Get-ChildItem -Path $env:UserProfile\*.jpg -Recurse
  $allpix | Where-Object {$_.LastWriteTime -gt $Start}
}
```

<span data-ttu-id="60bff-142">Вы можете создать панель элементов с полезными небольшими функциями.</span><span class="sxs-lookup"><span data-stu-id="60bff-142">You can create a toolbox of useful small functions.</span></span> <span data-ttu-id="60bff-143">Добавьте эти функции в профиль PowerShell, как описано в [about_Profiles](about_Profiles.md) и далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="60bff-143">Add these functions to your PowerShell profile, as described in [about_Profiles](about_Profiles.md) and later in this topic.</span></span>

## <a name="function-names"></a><span data-ttu-id="60bff-144">Имена функций</span><span class="sxs-lookup"><span data-stu-id="60bff-144">Function Names</span></span>

<span data-ttu-id="60bff-145">Функции можно назначить любое имя, но функции, к которым вы предоставили доступ другим, должны соответствовать правилам именования, установленным для всех команд PowerShell.</span><span class="sxs-lookup"><span data-stu-id="60bff-145">You can assign any name to a function, but functions that you share with others should follow the naming rules that have been established for all PowerShell commands.</span></span>

<span data-ttu-id="60bff-146">Имена функций должны состоять из пары существительных глаголов, в которых команда определяет действие, выполняемое функцией, а существительное определяет элемент, на котором командлет выполняет свое действие.</span><span class="sxs-lookup"><span data-stu-id="60bff-146">Functions names should consist of a verb-noun pair in which the verb identifies the action that the function performs and the noun identifies the item on which the cmdlet performs its action.</span></span>

<span data-ttu-id="60bff-147">Функции должны использовать стандартные команды, которые были утверждены для всех команд PowerShell.</span><span class="sxs-lookup"><span data-stu-id="60bff-147">Functions should use the standard verbs that have been approved for all PowerShell commands.</span></span> <span data-ttu-id="60bff-148">Эти команды помогают нам упростить, согласовать и легко понимать имена команд.</span><span class="sxs-lookup"><span data-stu-id="60bff-148">These verbs help us to keep our command names simple, consistent, and easy for users to understand.</span></span>

<span data-ttu-id="60bff-149">Дополнительные сведения о стандартных командах PowerShell см. в разделе [утвержденные команды](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands) в документация Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="60bff-149">For more information about the standard PowerShell verbs, see [Approved Verbs](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands) in the Microsoft Docs.</span></span>

## <a name="functions-with-parameters"></a><span data-ttu-id="60bff-150">Функции с параметрами</span><span class="sxs-lookup"><span data-stu-id="60bff-150">Functions with Parameters</span></span>

<span data-ttu-id="60bff-151">Параметры можно использовать с функциями, в том числе с именованными параметрами, параметрами, параметрами и динамическими параметрами.</span><span class="sxs-lookup"><span data-stu-id="60bff-151">You can use parameters with functions, including named parameters, positional parameters, switch parameters, and dynamic parameters.</span></span> <span data-ttu-id="60bff-152">Дополнительные сведения о динамических параметрах в функциях см. в разделе [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="60bff-152">For more information about dynamic parameters in functions, see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

### <a name="named-parameters"></a><span data-ttu-id="60bff-153">именованных параметров</span><span class="sxs-lookup"><span data-stu-id="60bff-153">Named Parameters</span></span>

<span data-ttu-id="60bff-154">Можно определить любое количество именованных параметров.</span><span class="sxs-lookup"><span data-stu-id="60bff-154">You can define any number of named parameters.</span></span> <span data-ttu-id="60bff-155">Можно включить значение по умолчанию для именованных параметров, как описано далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="60bff-155">You can include a default value for named parameters, as described later in this topic.</span></span>

<span data-ttu-id="60bff-156">Параметры внутри фигурных скобок можно определить с помощью `Param` ключевого слова, как показано в следующем примере синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="60bff-156">You can define parameters inside the braces using the `Param` keyword, as shown in the following sample syntax:</span></span>

```
function <name> {
  param ([type]$parameter1[,[type]$parameter2])
  <statement list>
}
```

<span data-ttu-id="60bff-157">Можно также определить параметры за пределами фигурных скобок без `Param` ключевого слова, как показано в следующем примере синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="60bff-157">You can also define parameters outside the braces without the `Param` keyword, as shown in the following sample syntax:</span></span>

```powershell
function <name> [([type]$parameter1[,[type]$parameter2])] {
  <statement list>
}
```

<span data-ttu-id="60bff-158">Ниже приведен пример альтернативного синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="60bff-158">Below is an example of this alternative syntax.</span></span>

```powershell
Function Add-Numbers($one, $two) {
    $one + $two
}
```

<span data-ttu-id="60bff-159">Хотя первый метод является предпочтительным, разница между этими двумя методами отсутствует.</span><span class="sxs-lookup"><span data-stu-id="60bff-159">While the first method is preferred, there is no difference between these two methods.</span></span>

<span data-ttu-id="60bff-160">При запуске функции значение, указываемое для параметра, присваивается переменной, содержащей имя параметра.</span><span class="sxs-lookup"><span data-stu-id="60bff-160">When you run the function, the value you supply for a parameter is assigned to a variable that contains the parameter name.</span></span> <span data-ttu-id="60bff-161">Значение этой переменной может использоваться в функции.</span><span class="sxs-lookup"><span data-stu-id="60bff-161">The value of that variable can be used in the function.</span></span>

<span data-ttu-id="60bff-162">В следующем примере показана функция с именем `Get-SmallFiles` .</span><span class="sxs-lookup"><span data-stu-id="60bff-162">The following example is a function called `Get-SmallFiles`.</span></span> <span data-ttu-id="60bff-163">Эта функция имеет `$Size` параметр.</span><span class="sxs-lookup"><span data-stu-id="60bff-163">This function has a `$Size` parameter.</span></span> <span data-ttu-id="60bff-164">Функция отображает все файлы, размер которых меньше значения `$Size` параметра, и исключает каталоги.</span><span class="sxs-lookup"><span data-stu-id="60bff-164">The function displays all the files that are smaller than the value of the `$Size` parameter, and it excludes directories:</span></span>

```powershell
function Get-SmallFiles {
  Param($Size)
  Get-ChildItem $HOME | Where-Object {
    $_.Length -lt $Size -and !$_.PSIsContainer
  }
}
```

<span data-ttu-id="60bff-165">В функции можно использовать `$Size` переменную, которая является именем, определенным для параметра.</span><span class="sxs-lookup"><span data-stu-id="60bff-165">In the function, you can use the `$Size` variable, which is the name defined for the parameter.</span></span>

<span data-ttu-id="60bff-166">Чтобы использовать эту функцию, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="60bff-166">To use this function, type the following command:</span></span>

```powershell
Get-SmallFiles -Size 50
```

<span data-ttu-id="60bff-167">Можно также ввести значение для именованного параметра без имени параметра.</span><span class="sxs-lookup"><span data-stu-id="60bff-167">You can also enter a value for a named parameter without the parameter name.</span></span>
<span data-ttu-id="60bff-168">Например, следующая команда дает тот же результат, что и команда, которая присваивает имя параметру **size** :</span><span class="sxs-lookup"><span data-stu-id="60bff-168">For example, the following command gives the same result as a command that names the **Size** parameter:</span></span>

```powershell
Get-SmallFiles 50
```

<span data-ttu-id="60bff-169">Чтобы определить значение по умолчанию для параметра, введите знак равенства и значение после имени параметра, как показано в следующем варианте `Get-SmallFiles` примера:</span><span class="sxs-lookup"><span data-stu-id="60bff-169">To define a default value for a parameter, type an equal sign and the value after the parameter name, as shown in the following variation of the `Get-SmallFiles` example:</span></span>

```powershell
function Get-SmallFiles ($Size = 100) {
  Get-ChildItem $HOME | Where-Object {
    $_.Length -lt $Size -and !$_.PSIsContainer
  }
}
```

<span data-ttu-id="60bff-170">Если ввести `Get-SmallFiles` без значения, функция присваивает 100 значение `$size` .</span><span class="sxs-lookup"><span data-stu-id="60bff-170">If you type `Get-SmallFiles` without a value, the function assigns 100 to `$size`.</span></span> <span data-ttu-id="60bff-171">Если указать значение, то функция использует это значение.</span><span class="sxs-lookup"><span data-stu-id="60bff-171">If you provide a value, the function uses that value.</span></span>

<span data-ttu-id="60bff-172">При необходимости можно указать краткую строку справки, описывающую значение параметра по умолчанию, добавив атрибут **псдефаултвалуе** в описание параметра и указав свойство **Help** объекта **псдефаултвалуе**.</span><span class="sxs-lookup"><span data-stu-id="60bff-172">Optionally, you can provide a brief help string that describes the default value of your parameter, by adding the **PSDefaultValue** attribute to the description of your parameter, and specifying the **Help** property of **PSDefaultValue**.</span></span> <span data-ttu-id="60bff-173">Чтобы предоставить строку справки, описывающую значение по умолчанию (100) параметра **size** в `Get-SmallFiles` функции, добавьте атрибут **псдефаултвалуе** , как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="60bff-173">To provide a help string that describes the default value (100) of the **Size** parameter in the `Get-SmallFiles` function, add the **PSDefaultValue** attribute as shown in the following example.</span></span>

```powershell
function Get-SmallFiles {
  param (
      [PSDefaultValue(Help = '100')]
      $Size = 100
  )
}
```

<span data-ttu-id="60bff-174">Дополнительные сведения о классе атрибута **псдефаултвалуе** см. в разделе [псдефаултвалуе Attribute Members](/dotnet/api/system.management.automation.psdefaultvalueattribute).</span><span class="sxs-lookup"><span data-stu-id="60bff-174">For more information about the **PSDefaultValue** attribute class, see [PSDefaultValue Attribute Members](/dotnet/api/system.management.automation.psdefaultvalueattribute).</span></span>

### <a name="positional-parameters"></a><span data-ttu-id="60bff-175">Параметры позиционирования</span><span class="sxs-lookup"><span data-stu-id="60bff-175">Positional Parameters</span></span>

<span data-ttu-id="60bff-176">Параметр с заданной позицией — это параметр без имени параметра.</span><span class="sxs-lookup"><span data-stu-id="60bff-176">A positional parameter is a parameter without a parameter name.</span></span> <span data-ttu-id="60bff-177">PowerShell использует порядок значений параметра, чтобы связать каждое значение параметра с параметром в функции.</span><span class="sxs-lookup"><span data-stu-id="60bff-177">PowerShell uses the parameter value order to associate each parameter value with a parameter in the function.</span></span>

<span data-ttu-id="60bff-178">При использовании позиционированных параметров введите одно или несколько значений после имени функции.</span><span class="sxs-lookup"><span data-stu-id="60bff-178">When you use positional parameters, type one or more values after the function name.</span></span> <span data-ttu-id="60bff-179">Значения позиционированных параметров присваиваются `$args` переменной массива.</span><span class="sxs-lookup"><span data-stu-id="60bff-179">Positional parameter values are assigned to the `$args` array variable.</span></span>
<span data-ttu-id="60bff-180">Значение, следующее за именем функции, присваивается первой положению в `$args` массиве, `$args[0]` .</span><span class="sxs-lookup"><span data-stu-id="60bff-180">The value that follows the function name is assigned to the first position in the `$args` array, `$args[0]`.</span></span>

<span data-ttu-id="60bff-181">Следующая `Get-Extension` функция добавляет `.txt` расширение имени файла к указанному имени файла:</span><span class="sxs-lookup"><span data-stu-id="60bff-181">The following `Get-Extension` function adds the `.txt` file name extension to a file name that you supply:</span></span>

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

### <a name="switch-parameters"></a><span data-ttu-id="60bff-182">Параметры переключателя</span><span class="sxs-lookup"><span data-stu-id="60bff-182">Switch Parameters</span></span>

<span data-ttu-id="60bff-183">Переключатель — это параметр, который не требует значения.</span><span class="sxs-lookup"><span data-stu-id="60bff-183">A switch is a parameter that does not require a value.</span></span> <span data-ttu-id="60bff-184">Вместо этого введите имя функции, за которым следует имя параметра переключателя.</span><span class="sxs-lookup"><span data-stu-id="60bff-184">Instead, you type the function name followed by the name of the switch parameter.</span></span>

<span data-ttu-id="60bff-185">Чтобы определить параметр переключателя, укажите тип `[switch]` перед именем параметра, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="60bff-185">To define a switch parameter, specify the type `[switch]` before the parameter name, as shown in the following example:</span></span>

```powershell
function Switch-Item {
  param ([switch]$on)
  if ($on) { "Switch on" }
  else { "Switch off" }
}
```

<span data-ttu-id="60bff-186">При вводе `On` параметра Switch после имени функции функция отображает параметр on.</span><span class="sxs-lookup"><span data-stu-id="60bff-186">When you type the `On` switch parameter after the function name, the function displays "Switch on".</span></span> <span data-ttu-id="60bff-187">Без параметра Switch отображается значение "Отключить выключение".</span><span class="sxs-lookup"><span data-stu-id="60bff-187">Without the switch parameter, it displays "Switch off".</span></span>

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

<span data-ttu-id="60bff-188">При выполнении функции можно также присвоить **логическое** значение параметру, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="60bff-188">You can also assign a **Boolean** value to a switch when you run the function, as shown in the following example:</span></span>

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

## <a name="using-splatting-to-represent-command-parameters"></a><span data-ttu-id="60bff-189">Использование Сплаттинг для представления параметров команды</span><span class="sxs-lookup"><span data-stu-id="60bff-189">Using Splatting to Represent Command Parameters</span></span>

<span data-ttu-id="60bff-190">Сплаттинг можно использовать для представления параметров команды.</span><span class="sxs-lookup"><span data-stu-id="60bff-190">You can use splatting to represent the parameters of a command.</span></span> <span data-ttu-id="60bff-191">Эта функция появилась в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="60bff-191">This feature is introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="60bff-192">Используйте этот метод в функциях, вызывающих команды в сеансе.</span><span class="sxs-lookup"><span data-stu-id="60bff-192">Use this technique in functions that call commands in the session.</span></span> <span data-ttu-id="60bff-193">Вам не нужно объявлять или перечислять параметры команды или изменять функцию при изменении параметров команды.</span><span class="sxs-lookup"><span data-stu-id="60bff-193">You do not need to declare or enumerate the command parameters, or change the function when command parameters change.</span></span>

<span data-ttu-id="60bff-194">Следующий пример функции вызывает `Get-Command` командлет.</span><span class="sxs-lookup"><span data-stu-id="60bff-194">The following sample function calls the `Get-Command` cmdlet.</span></span> <span data-ttu-id="60bff-195">Команда использует `@Args` для представления параметров `Get-Command` .</span><span class="sxs-lookup"><span data-stu-id="60bff-195">The command uses `@Args` to represent the parameters of `Get-Command`.</span></span>

```powershell
function Get-MyCommand { Get-Command @Args }
```

<span data-ttu-id="60bff-196">`Get-Command`При вызове функции можно использовать все параметры `Get-MyCommand` .</span><span class="sxs-lookup"><span data-stu-id="60bff-196">You can use all of the parameters of `Get-Command` when you call the `Get-MyCommand` function.</span></span> <span data-ttu-id="60bff-197">Параметры и значения параметров передаются в команду с помощью команды `@Args` .</span><span class="sxs-lookup"><span data-stu-id="60bff-197">The parameters and parameter values are passed to the command using `@Args`.</span></span>

```powershell
Get-MyCommand -Name Get-ChildItem
```

```Output
CommandType     Name                ModuleName
-----------     ----                ----------
Cmdlet          Get-ChildItem       Microsoft.PowerShell.Management
```

<span data-ttu-id="60bff-198">Эта `@Args` функция использует `$Args` Автоматический параметр, представляющий необъявленные параметры и значения командлета из оставшихся аргументов.</span><span class="sxs-lookup"><span data-stu-id="60bff-198">The `@Args` feature uses the `$Args` automatic parameter, which represents undeclared cmdlet parameters and values from remaining arguments.</span></span>

<span data-ttu-id="60bff-199">Дополнительные сведения о Сплаттинг см. в разделе [about_Splatting](about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="60bff-199">For more information about splatting, see [about_Splatting](about_Splatting.md).</span></span>

## <a name="piping-objects-to-functions"></a><span data-ttu-id="60bff-200">Передача объектов в функции</span><span class="sxs-lookup"><span data-stu-id="60bff-200">Piping Objects to Functions</span></span>

<span data-ttu-id="60bff-201">Любая функция может принимать входные данные из конвейера.</span><span class="sxs-lookup"><span data-stu-id="60bff-201">Any function can take input from the pipeline.</span></span> <span data-ttu-id="60bff-202">Можно контролировать, как функция обрабатывает входные данные из конвейера с помощью `Begin` `Process` `End` ключевых слов, и.</span><span class="sxs-lookup"><span data-stu-id="60bff-202">You can control how a function processes input from the pipeline using `Begin`, `Process`, and `End` keywords.</span></span> <span data-ttu-id="60bff-203">В следующем образце синтаксиса показаны три ключевых слова:</span><span class="sxs-lookup"><span data-stu-id="60bff-203">The following sample syntax shows the three keywords:</span></span>

```
function <name> {
  begin {<statement list>}
  process {<statement list>}
  end {<statement list>}
}
```

<span data-ttu-id="60bff-204">`Begin`Список инструкций выполняется только один раз в начале функции.</span><span class="sxs-lookup"><span data-stu-id="60bff-204">The `Begin` statement list runs one time only, at the beginning of the function.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="60bff-205">Если функция определяет `Begin` блок, то `Process` `End` весь код должен находиться внутри этих блоков.</span><span class="sxs-lookup"><span data-stu-id="60bff-205">If your function defines a `Begin`, `Process` or `End` block, all of your code must reside inside those blocks.</span></span> <span data-ttu-id="60bff-206">Код не будет располагаться за пределами блоков, если определены *какие либо* блоки.</span><span class="sxs-lookup"><span data-stu-id="60bff-206">No code will be recognized outside the blocks if *any* of the blocks are defined.</span></span>

<span data-ttu-id="60bff-207">`Process`Список инструкций выполняется один раз для каждого объекта в конвейере.</span><span class="sxs-lookup"><span data-stu-id="60bff-207">The `Process` statement list runs one time for each object in the pipeline.</span></span>
<span data-ttu-id="60bff-208">Во время `Process` выполнения блока каждый объект конвейера назначается `$_` автоматической переменной, по одному объекту конвейера за раз.</span><span class="sxs-lookup"><span data-stu-id="60bff-208">While the `Process` block is running, each pipeline object is assigned to the `$_` automatic variable, one pipeline object at a time.</span></span>

<span data-ttu-id="60bff-209">После того как функция получит все объекты в конвейере, `End` список инструкций будет выполняться один раз.</span><span class="sxs-lookup"><span data-stu-id="60bff-209">After the function receives all the objects in the pipeline, the `End` statement list runs one time.</span></span> <span data-ttu-id="60bff-210">Если не `Begin` `Process` `End` используются ключевые слова, или, все инструкции рассматриваются как `End` список инструкций.</span><span class="sxs-lookup"><span data-stu-id="60bff-210">If no `Begin`, `Process`, or `End` keywords are used, all the statements are treated like an `End` statement list.</span></span>

<span data-ttu-id="60bff-211">Следующая функция использует `Process` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="60bff-211">The following function uses the `Process` keyword.</span></span> <span data-ttu-id="60bff-212">Функция отображает примеры из конвейера:</span><span class="sxs-lookup"><span data-stu-id="60bff-212">The function displays examples from the pipeline:</span></span>

```powershell
function Get-Pipeline
{
  process {"The value is: $_"}
}
```

<span data-ttu-id="60bff-213">Чтобы продемонстрировать эту функцию, введите список чисел, разделенных запятыми, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="60bff-213">To demonstrate this function, enter an list of numbers separated by commas, as shown in the following example:</span></span>

```powershell
1,2,4 | Get-Pipeline
```

```Output
The value is: 1
The value is: 2
The value is: 4
```

<span data-ttu-id="60bff-214">При использовании функции в конвейере объекты, переданный функции, назначаются `$input` автоматической переменной.</span><span class="sxs-lookup"><span data-stu-id="60bff-214">When you use a function in a pipeline, the objects piped to the function are assigned to the `$input` automatic variable.</span></span> <span data-ttu-id="60bff-215">Функция выполняет инструкции с `Begin` ключевым словом перед тем, как все объекты поступают из конвейера.</span><span class="sxs-lookup"><span data-stu-id="60bff-215">The function runs statements with the `Begin` keyword before any objects come from the pipeline.</span></span> <span data-ttu-id="60bff-216">Функция выполняет инструкции с `End` ключевым словом после того, как все объекты были получены из конвейера.</span><span class="sxs-lookup"><span data-stu-id="60bff-216">The function runs statements with the `End` keyword after all the objects have been received from the pipeline.</span></span>

<span data-ttu-id="60bff-217">В следующем примере показана `$input` Автоматическая переменная с `Begin` `End` ключевыми словами и.</span><span class="sxs-lookup"><span data-stu-id="60bff-217">The following example shows the `$input` automatic variable with `Begin` and `End` keywords.</span></span>

```powershell
function Get-PipelineBeginEnd
{
  begin {"Begin: The input is $input"}
  end {"End:   The input is $input" }
}
```

<span data-ttu-id="60bff-218">Если эта функция выполняется с помощью конвейера, отображаются следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="60bff-218">If this function is run by using the pipeline, it displays the following results:</span></span>

```powershell
1,2,4 | Get-PipelineBeginEnd
```

```Output
Begin: The input is
End:   The input is 1 2 4
```

<span data-ttu-id="60bff-219">При `Begin` выполнении инструкции функция не имеет входных данных из конвейера.</span><span class="sxs-lookup"><span data-stu-id="60bff-219">When the `Begin` statement runs, the function does not have the input from the pipeline.</span></span> <span data-ttu-id="60bff-220">`End`Инструкция выполняется после того, как функция применяет значения.</span><span class="sxs-lookup"><span data-stu-id="60bff-220">The `End` statement runs after the function has the values.</span></span>

<span data-ttu-id="60bff-221">Если у функции есть `Process` ключевое слово, каждый объект в удаляется `$input` из `$input` и присваивается `$_` .</span><span class="sxs-lookup"><span data-stu-id="60bff-221">If the function has a `Process` keyword, each object in `$input` is removed from `$input` and assigned to `$_`.</span></span> <span data-ttu-id="60bff-222">В следующем примере содержится `Process` список операторов:</span><span class="sxs-lookup"><span data-stu-id="60bff-222">The following example has a `Process` statement list:</span></span>

```powershell
function Get-PipelineInput
{
  process {"Processing:  $_ " }
  end {"End:   The input is: $input" }
}
```

<span data-ttu-id="60bff-223">В этом примере каждый объект, передаваемый функции, отправляется в `Process` список инструкций.</span><span class="sxs-lookup"><span data-stu-id="60bff-223">In this example, each object that is piped to the function is sent to the `Process` statement list.</span></span> <span data-ttu-id="60bff-224">`Process`Инструкции выполняются для каждого объекта, по одному объекту за раз.</span><span class="sxs-lookup"><span data-stu-id="60bff-224">The `Process` statements run on each object, one object at a time.</span></span> <span data-ttu-id="60bff-225">`$input`Автоматическая переменная пуста, если функция достигает `End` ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="60bff-225">The `$input` automatic variable is empty when the function reaches the `End` keyword.</span></span>

```powershell
1,2,4 | Get-PipelineInput
```

```Output
Processing:  1
Processing:  2
Processing:  4
End:   The input is:
```

<span data-ttu-id="60bff-226">Дополнительные сведения см. [в разделе Использование перечислителей](about_Automatic_Variables.md#using-enumerators) .</span><span class="sxs-lookup"><span data-stu-id="60bff-226">For more information, see [Using Enumerators](about_Automatic_Variables.md#using-enumerators)</span></span>

## <a name="filters"></a><span data-ttu-id="60bff-227">Фильтры</span><span class="sxs-lookup"><span data-stu-id="60bff-227">Filters</span></span>

<span data-ttu-id="60bff-228">Фильтр — это тип функции, которая выполняется для каждого объекта в конвейере.</span><span class="sxs-lookup"><span data-stu-id="60bff-228">A filter is a type of function that runs on each object in the pipeline.</span></span> <span data-ttu-id="60bff-229">Фильтр напоминает функцию со всеми ее операторами в `Process` блоке.</span><span class="sxs-lookup"><span data-stu-id="60bff-229">A filter resembles a function with all its statements in a `Process` block.</span></span>

<span data-ttu-id="60bff-230">Синтаксис фильтра выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="60bff-230">The syntax of a filter is as follows:</span></span>

```
filter [<scope:>]<name> {<statement list>}
```

<span data-ttu-id="60bff-231">Следующий фильтр принимает записи журнала из конвейера, а затем отображает всю запись или только часть сообщения в записи:</span><span class="sxs-lookup"><span data-stu-id="60bff-231">The following filter takes log entries from the pipeline and then displays either the whole entry or only the message portion of the entry:</span></span>

```powershell
filter Get-ErrorLog ([switch]$message)
{
  if ($message) { Out-Host -InputObject $_.Message }
  else { $_ }
}
```

## <a name="function-scope"></a><span data-ttu-id="60bff-232">Область действия функции</span><span class="sxs-lookup"><span data-stu-id="60bff-232">Function Scope</span></span>

<span data-ttu-id="60bff-233">Функция существует в области, в которой она была создана.</span><span class="sxs-lookup"><span data-stu-id="60bff-233">A function exists in the scope in which it was created.</span></span>

<span data-ttu-id="60bff-234">Если функция является частью скрипта, функция доступна для инструкций внутри этого скрипта.</span><span class="sxs-lookup"><span data-stu-id="60bff-234">If a function is part of a script, the function is available to statements within that script.</span></span> <span data-ttu-id="60bff-235">По умолчанию функция в скрипте недоступна в командной строке.</span><span class="sxs-lookup"><span data-stu-id="60bff-235">By default, a function in a script is not available at the command prompt.</span></span>

<span data-ttu-id="60bff-236">Можно указать область функции.</span><span class="sxs-lookup"><span data-stu-id="60bff-236">You can specify the scope of a function.</span></span> <span data-ttu-id="60bff-237">Например, функция добавляется в глобальную область в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="60bff-237">For example, the function is added to the global scope in the following example:</span></span>

```powershell
function global:Get-DependentSvs {
  Get-Service | Where-Object {$_.DependentServices}
}
```

<span data-ttu-id="60bff-238">Если функция находится в глобальной области, ее можно использовать в скриптах, функциях и в командной строке.</span><span class="sxs-lookup"><span data-stu-id="60bff-238">When a function is in the global scope, you can use the function in scripts, in functions, and at the command line.</span></span>

<span data-ttu-id="60bff-239">Обычно функции создают область.</span><span class="sxs-lookup"><span data-stu-id="60bff-239">Functions normally create a scope.</span></span> <span data-ttu-id="60bff-240">Элементы, созданные в функции, такие как переменные, существуют только в области видимости функции.</span><span class="sxs-lookup"><span data-stu-id="60bff-240">The items created in a function, such as variables, exist only in the function scope.</span></span>

<span data-ttu-id="60bff-241">Дополнительные сведения об области действия в PowerShell см. в разделе [about_Scopes](about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="60bff-241">For more information about scope in PowerShell, see [about_Scopes](about_Scopes.md).</span></span>

## <a name="finding-and-managing-functions-using-the-function-drive"></a><span data-ttu-id="60bff-242">Поиск функций и управление ими с помощью диска Function:</span><span class="sxs-lookup"><span data-stu-id="60bff-242">Finding and Managing Functions Using the Function: Drive</span></span>

<span data-ttu-id="60bff-243">Все функции и фильтры в PowerShell автоматически сохраняются на `Function:` диске.</span><span class="sxs-lookup"><span data-stu-id="60bff-243">All the functions and filters in PowerShell are automatically stored in the `Function:` drive.</span></span> <span data-ttu-id="60bff-244">Этот диск предоставляется поставщиком **функций** PowerShell.</span><span class="sxs-lookup"><span data-stu-id="60bff-244">This drive is exposed by the PowerShell **Function** provider.</span></span>

<span data-ttu-id="60bff-245">При обращении к `Function:` диску введите двоеточие после **функции**, как при обращении к `C` диску или на `D` диске компьютера.</span><span class="sxs-lookup"><span data-stu-id="60bff-245">When referring to the `Function:` drive, type a colon after **Function**, just as you would do when referencing the `C` or `D` drive of a computer.</span></span>

<span data-ttu-id="60bff-246">Следующая команда отображает все функции в текущем сеансе PowerShell:</span><span class="sxs-lookup"><span data-stu-id="60bff-246">The following command displays all the functions in the current session of PowerShell:</span></span>

```powershell
Get-ChildItem function:
```

<span data-ttu-id="60bff-247">Команды в функции хранятся в виде блока скрипта в свойстве определения функции.</span><span class="sxs-lookup"><span data-stu-id="60bff-247">The commands in the function are stored as a script block in the definition property of the function.</span></span> <span data-ttu-id="60bff-248">Например, чтобы отобразить команды в функции справки, поставляемой с PowerShell, введите:</span><span class="sxs-lookup"><span data-stu-id="60bff-248">For example, to display the commands in the Help function that comes with PowerShell, type:</span></span>

```powershell
(Get-ChildItem function:help).Definition
```

<span data-ttu-id="60bff-249">Можно также использовать следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="60bff-249">You can also use the following syntax.</span></span>

```powershell
$function:help
```

<span data-ttu-id="60bff-250">Дополнительные сведения о `Function:` диске см. в разделе справки по поставщику **функций** .</span><span class="sxs-lookup"><span data-stu-id="60bff-250">For more information about the `Function:` drive, see the help topic for the **Function** provider.</span></span> <span data-ttu-id="60bff-251">Введите `Get-Help Function`.</span><span class="sxs-lookup"><span data-stu-id="60bff-251">Type `Get-Help Function`.</span></span>

## <a name="reusing-functions-in-new-sessions"></a><span data-ttu-id="60bff-252">Повторное использование функций в новых сеансах</span><span class="sxs-lookup"><span data-stu-id="60bff-252">Reusing Functions in New Sessions</span></span>

<span data-ttu-id="60bff-253">При вводе функции в командной строке PowerShell функция станет частью текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="60bff-253">When you type a function at the PowerShell command prompt, the function becomes part of the current session.</span></span> <span data-ttu-id="60bff-254">Он доступен до завершения сеанса.</span><span class="sxs-lookup"><span data-stu-id="60bff-254">It is available until the session ends.</span></span>

<span data-ttu-id="60bff-255">Чтобы использовать функцию во всех сеансах PowerShell, добавьте функцию в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="60bff-255">To use your function in all PowerShell sessions, add the function to your PowerShell profile.</span></span> <span data-ttu-id="60bff-256">Дополнительные сведения о профилях см. в разделе [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="60bff-256">For more information about profiles, see [about_Profiles](about_Profiles.md).</span></span>

<span data-ttu-id="60bff-257">Можно также сохранить функцию в файле сценария PowerShell.</span><span class="sxs-lookup"><span data-stu-id="60bff-257">You can also save your function in a PowerShell script file.</span></span> <span data-ttu-id="60bff-258">Введите функцию в текстовом файле, а затем сохраните файл с `.ps1` расширением имени файла.</span><span class="sxs-lookup"><span data-stu-id="60bff-258">Type your function in a text file, and then save the file with the `.ps1` file name extension.</span></span>

## <a name="writing-help-for-functions"></a><span data-ttu-id="60bff-259">Написание справки для функций</span><span class="sxs-lookup"><span data-stu-id="60bff-259">Writing Help for Functions</span></span>

<span data-ttu-id="60bff-260">`Get-Help`Командлет возвращает справку по функциям, а также к командлетам, поставщикам и скриптам.</span><span class="sxs-lookup"><span data-stu-id="60bff-260">The `Get-Help` cmdlet gets help for functions, as well as for cmdlets, providers, and scripts.</span></span> <span data-ttu-id="60bff-261">Чтобы получить справку по функции, введите, `Get-Help` за которым следует имя функции.</span><span class="sxs-lookup"><span data-stu-id="60bff-261">To get help for a function, type `Get-Help` followed by the function name.</span></span>

<span data-ttu-id="60bff-262">Например, чтобы получить справку по `Get-MyDisks` функции, введите:</span><span class="sxs-lookup"><span data-stu-id="60bff-262">For example, to get help for the `Get-MyDisks` function, type:</span></span>

```powershell
Get-Help Get-MyDisks
```

<span data-ttu-id="60bff-263">Вы можете написать справку для функции с помощью любого из двух следующих методов:</span><span class="sxs-lookup"><span data-stu-id="60bff-263">You can write help for a function by using either of the two following methods:</span></span>

- <span data-ttu-id="60bff-264">Comment-Based справки по функциям</span><span class="sxs-lookup"><span data-stu-id="60bff-264">Comment-Based Help for Functions</span></span>

  <span data-ttu-id="60bff-265">Создайте раздел справки, используя специальные ключевые слова в комментариях.</span><span class="sxs-lookup"><span data-stu-id="60bff-265">Create a help topic by using special keywords in the comments.</span></span> <span data-ttu-id="60bff-266">Чтобы создать справку на основе комментариев для функции, комментарии должны располагаться в начале или в конце тела функции или в строках, предшествующих ключевому слову Function.</span><span class="sxs-lookup"><span data-stu-id="60bff-266">To create comment-based help for a function, the comments must be placed at the beginning or end of the function body or on the lines preceding the function keyword.</span></span> <span data-ttu-id="60bff-267">Дополнительные сведения о справке на основе комментариев см. в разделе [about_Comment_Based_Help](about_Comment_Based_Help.md).</span><span class="sxs-lookup"><span data-stu-id="60bff-267">For more information about comment-based help, see [about_Comment_Based_Help](about_Comment_Based_Help.md).</span></span>

- <span data-ttu-id="60bff-268">XML-Based справки по функциям</span><span class="sxs-lookup"><span data-stu-id="60bff-268">XML-Based Help for Functions</span></span>

  <span data-ttu-id="60bff-269">Создайте раздел справки на основе XML, например тип, который обычно создается для командлетов.</span><span class="sxs-lookup"><span data-stu-id="60bff-269">Create an XML-based help topic, such as the type that is typically created for cmdlets.</span></span> <span data-ttu-id="60bff-270">При локализации разделов справки на несколько языков требуется справка на основе XML.</span><span class="sxs-lookup"><span data-stu-id="60bff-270">XML-based help is required if you are localizing help topics into multiple languages.</span></span>

  <span data-ttu-id="60bff-271">Чтобы связать функцию с разделом справки на основе XML, используйте `.ExternalHelp` ключевое слово справки на основе комментариев.</span><span class="sxs-lookup"><span data-stu-id="60bff-271">To associate the function with the XML-based help topic, use the `.ExternalHelp` comment-based help keyword.</span></span> <span data-ttu-id="60bff-272">Без этого ключевого слова `Get-Help` не удается найти раздел справки по функциям и вызовы для `Get-Help` функции, возвращающие только автоматически созданную справку.</span><span class="sxs-lookup"><span data-stu-id="60bff-272">Without this keyword, `Get-Help` cannot find the function help topic and calls to `Get-Help` for the function return only auto-generated help.</span></span>

  <span data-ttu-id="60bff-273">Дополнительные сведения о `ExternalHelp` ключевом слове см. в разделе [about_Comment_Based_Help](about_Comment_Based_Help.md).</span><span class="sxs-lookup"><span data-stu-id="60bff-273">For more information about the `ExternalHelp` keyword, see [about_Comment_Based_Help](about_Comment_Based_Help.md).</span></span> <span data-ttu-id="60bff-274">Дополнительные сведения о справке на основе XML см. [в разделе как написать справку по командлетам](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).</span><span class="sxs-lookup"><span data-stu-id="60bff-274">For more information about XML-based help, see [How to Write Cmdlet Help](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).</span></span>

## <a name="see-also"></a><span data-ttu-id="60bff-275">См. также</span><span class="sxs-lookup"><span data-stu-id="60bff-275">See also</span></span>

[<span data-ttu-id="60bff-276">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="60bff-276">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="60bff-277">about_Comment_Based_Help</span><span class="sxs-lookup"><span data-stu-id="60bff-277">about_Comment_Based_Help</span></span>](about_Comment_Based_Help.md)

[<span data-ttu-id="60bff-278">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="60bff-278">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="60bff-279">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="60bff-279">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="60bff-280">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="60bff-280">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="60bff-281">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="60bff-281">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="60bff-282">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="60bff-282">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)

[<span data-ttu-id="60bff-283">about_Parameters</span><span class="sxs-lookup"><span data-stu-id="60bff-283">about_Parameters</span></span>](about_Parameters.md)

[<span data-ttu-id="60bff-284">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="60bff-284">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="60bff-285">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="60bff-285">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="60bff-286">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="60bff-286">about_Script_Blocks</span></span>](about_Script_Blocks.md)

[<span data-ttu-id="60bff-287">about_Function_provider</span><span class="sxs-lookup"><span data-stu-id="60bff-287">about_Function_provider</span></span>](about_Function_provider.md)
