---
title: Все, что нужно знать о $null
description: В PowerShell состояние $null часто кажется простым, но оно имеет много нюансов. Давайте подробно рассмотрим $null и выясним, что означает неожиданное получение значения NULL.
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: e0553a5e17450d8044f548792649369e99903850
ms.sourcegitcommit: ed4a895d672334c7b02fb7ef6e950dbc2ba4a197
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2020
ms.locfileid: "84149477"
---
# <a name="everything-you-wanted-to-know-about-null"></a><span data-ttu-id="345ec-104">Все, что нужно знать о $null</span><span class="sxs-lookup"><span data-stu-id="345ec-104">Everything you wanted to know about $null</span></span>

<span data-ttu-id="345ec-105">В PowerShell состояние `$null` часто кажется простым, но оно имеет много нюансов.</span><span class="sxs-lookup"><span data-stu-id="345ec-105">The PowerShell `$null` often appears to be simple but it has a lot of nuances.</span></span> <span data-ttu-id="345ec-106">Давайте подробно рассмотрим `$null` и выясним, что означает неожиданное получение значения `$null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-106">Let's take a close look at `$null` so you know what happens when you unexpectedly run into a `$null` value.</span></span>

> [!NOTE]
> <span data-ttu-id="345ec-107">[Оригинал статьи][] этой статьи впервые был опубликован в блоге автора [@KevinMarquette][].</span><span class="sxs-lookup"><span data-stu-id="345ec-107">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="345ec-108">Команда разработчиков PowerShell благодарит Кевина за то, что он поделился с нами этим материалом.</span><span class="sxs-lookup"><span data-stu-id="345ec-108">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="345ec-109">Читайте его блог — [PowerShellExplained.com][].</span><span class="sxs-lookup"><span data-stu-id="345ec-109">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="what-is-null"></a><span data-ttu-id="345ec-110">Что означает NULL</span><span class="sxs-lookup"><span data-stu-id="345ec-110">What is NULL?</span></span>

<span data-ttu-id="345ec-111">Значение NULL можно считать неизвестным или пустым значением.</span><span class="sxs-lookup"><span data-stu-id="345ec-111">You can think of NULL as an unknown or empty value.</span></span> <span data-ttu-id="345ec-112">Переменная имеет значение NULL, пока ей не присвоено значение или объект.</span><span class="sxs-lookup"><span data-stu-id="345ec-112">A variable is NULL until you assign a value or an object to it.</span></span> <span data-ttu-id="345ec-113">Это важный момент, так как некоторые команды требуют значения и возвращают ошибку, если значением является NULL.</span><span class="sxs-lookup"><span data-stu-id="345ec-113">This can be important because there are some commands that require a value and generate errors if the value is NULL.</span></span>

### <a name="powershell-null"></a><span data-ttu-id="345ec-114">$null в PowerShell</span><span class="sxs-lookup"><span data-stu-id="345ec-114">PowerShell $null</span></span>

<span data-ttu-id="345ec-115">`$null` — это автоматическая переменная в PowerShell, используемая для представления значения NULL.</span><span class="sxs-lookup"><span data-stu-id="345ec-115">`$null` is an automatic variable in PowerShell used to represent NULL.</span></span> <span data-ttu-id="345ec-116">Ее можно назначать переменным и использовать в сравнениях, а также в качестве заполнителя для значения NULL в коллекции.</span><span class="sxs-lookup"><span data-stu-id="345ec-116">You can assign it to variables, use it in comparisons and use it as a place holder for NULL in a collection.</span></span>

<span data-ttu-id="345ec-117">В PowerShell `$null` считается объектом со значением NULL,</span><span class="sxs-lookup"><span data-stu-id="345ec-117">PowerShell treats `$null` as an object with a value of NULL.</span></span> <span data-ttu-id="345ec-118">что отличается от трактовки этого понятия в других языках.</span><span class="sxs-lookup"><span data-stu-id="345ec-118">This is different than what you may expect if you come from another language.</span></span>

## <a name="examples-of-null"></a><span data-ttu-id="345ec-119">Примеры использования $null</span><span class="sxs-lookup"><span data-stu-id="345ec-119">Examples of $null</span></span>

<span data-ttu-id="345ec-120">Всякий раз, когда вы пытаетесь использовать переменную, которая не была инициализирована, ее значением будет `$null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-120">Anytime you try to use a variable that you have not initialized, the value is `$null`.</span></span> <span data-ttu-id="345ec-121">Это одна из самых распространенных причин, по которой значения `$null` появляются в коде.</span><span class="sxs-lookup"><span data-stu-id="345ec-121">This is one of the most common ways that `$null` values sneak into your code.</span></span>

```powershell
PS> $null -eq $undefinedVariable
True
```

<span data-ttu-id="345ec-122">Если вы неправильно указали имя переменной, PowerShell не распознает ее и присвоит ей значение `$null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-122">If you happen to mistype a variable name then PowerShell sees it as a different variable and the value is `$null`.</span></span>

<span data-ttu-id="345ec-123">Значения `$null` также появляются при выполнении команд, которые не выдают результатов.</span><span class="sxs-lookup"><span data-stu-id="345ec-123">The other way you find `$null` values is when they come from other commands that don't give you any results.</span></span>

```powershell
PS> function Get-Nothing {}
PS> $value = Get-Nothing
PS> $null -eq $value
True
```

## <a name="impact-of-null"></a><span data-ttu-id="345ec-124">Интерпретация $null</span><span class="sxs-lookup"><span data-stu-id="345ec-124">Impact of $null</span></span>

<span data-ttu-id="345ec-125">Значения `$null` обрабатываются в коде по-разному, в зависимости от того, где они находятся.</span><span class="sxs-lookup"><span data-stu-id="345ec-125">`$null` values impact your code differently depending on where they show up.</span></span>

### <a name="in-strings"></a><span data-ttu-id="345ec-126">В строках</span><span class="sxs-lookup"><span data-stu-id="345ec-126">In strings</span></span>

<span data-ttu-id="345ec-127">Если в строке используется `$null`, то это пустое значение (или пустая строка).</span><span class="sxs-lookup"><span data-stu-id="345ec-127">If you use `$null` in a string, then it's a blank value (or empty string).</span></span>

```powershell
PS> $value = $null
PS> Write-Output "The value is $value"
The value is
```

<span data-ttu-id="345ec-128">Это одна из причин, по которой я предпочитаю заключать переменные в скобки при их использовании в сообщениях журнала.</span><span class="sxs-lookup"><span data-stu-id="345ec-128">This is one of the reasons that I like to place brackets around variables when using them in log messages.</span></span> <span data-ttu-id="345ec-129">Если значение находится в конце строки, это также помогает обнаружить границы значений переменных.</span><span class="sxs-lookup"><span data-stu-id="345ec-129">It's even more important to identify the edges of your variable values when the value is at the end of the string.</span></span>

```powershell
PS> $value = $null
PS> Write-Output "The value is [$value]"
The value is []
```

<span data-ttu-id="345ec-130">Так можно легко обнаружить пустые строки и значения `$null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-130">This makes empty strings and `$null` values easy to spot.</span></span>

### <a name="in-numeric-equation"></a><span data-ttu-id="345ec-131">В числовом уравнении</span><span class="sxs-lookup"><span data-stu-id="345ec-131">In numeric equation</span></span>

<span data-ttu-id="345ec-132">Когда значение `$null` используется в числовом уравнении, результаты будут недействительными, если не будет возвращена ошибка.</span><span class="sxs-lookup"><span data-stu-id="345ec-132">When a `$null` value is used in a numeric equation then your results are invalid if they don't give an error.</span></span> <span data-ttu-id="345ec-133">Иногда `$null` значит `0`, но в других случаях полученный результат будет приравнен к `$null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-133">Sometimes the `$null` evaluates to `0` and other times it makes the whole result `$null`.</span></span>
<span data-ttu-id="345ec-134">Ниже приведен пример с умножением, результатом которого может быть как 0, так и `$null` в зависимости от порядка значений.</span><span class="sxs-lookup"><span data-stu-id="345ec-134">Here is an example with multiplication that gives 0 or `$null` depending on the order of the values.</span></span>

```powershell
PS> $null * 5
PS> $null -eq ( $null * 5 )
True

PS> 5 * $null
0
PS> $null -eq ( 5 * $null )
False
```

### <a name="in-place-of-a-collection"></a><span data-ttu-id="345ec-135">Вместо коллекции</span><span class="sxs-lookup"><span data-stu-id="345ec-135">In place of a collection</span></span>

<span data-ttu-id="345ec-136">Коллекция позволяет использовать индекс для доступа к значениям.</span><span class="sxs-lookup"><span data-stu-id="345ec-136">A collection allow you use an index to access values.</span></span> <span data-ttu-id="345ec-137">При попытке индексировать в коллекцию, которая фактически является `null`, вы получите ошибку `Cannot index into a null array`.</span><span class="sxs-lookup"><span data-stu-id="345ec-137">If you try to index into a collection that is actually `null`, you get this error: `Cannot index into a null array`.</span></span>

```powershell
PS> $value = $null
PS> $value[10]
Cannot index into a null array.
At line:1 char:1
+ $value[10]
+ ~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [], RuntimeException
    + FullyQualifiedErrorId : NullArray
```

<span data-ttu-id="345ec-138">Если у вас есть коллекция, но вы пытаетесь получить доступ к элементу, который отсутствует в коллекции, вы получите результат `$null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-138">If you have a collection but try to access an element that is not in the collection, you get a `$null` result.</span></span>

```powershell
$array = @( 'one','two','three' )
$null -eq $array[100]
True
```

### <a name="in-place-of-an-object"></a><span data-ttu-id="345ec-139">Вместо объекта</span><span class="sxs-lookup"><span data-stu-id="345ec-139">In place of an object</span></span>

<span data-ttu-id="345ec-140">При попытке доступа к свойству или подсвойству объекта, у которого нет указанного свойства, вы получите значение `$null`, как и в случае доступа к неопределенной переменной.</span><span class="sxs-lookup"><span data-stu-id="345ec-140">If you try to access a property or sub property of an object that doesn't have the specified property, you get a `$null` value like you would for an undefined variable.</span></span> <span data-ttu-id="345ec-141">При этом не имеет значения, является ли переменная `$null` или фактическим объектом.</span><span class="sxs-lookup"><span data-stu-id="345ec-141">It doesn't matter if the variable is `$null` or an actual object in this case.</span></span>

```powershell
PS> $null -eq $undefined.some.fake.property
True

PS> $date = Get-Date
PS> $null -eq $date.some.fake.property
True
```

### <a name="method-on-a-null-valued-expression"></a><span data-ttu-id="345ec-142">Метод в выражении со значением NULL</span><span class="sxs-lookup"><span data-stu-id="345ec-142">Method on a null-valued expression</span></span>

<span data-ttu-id="345ec-143">Вызов метода для объекта `$null` вызывает исключение `RuntimeException`.</span><span class="sxs-lookup"><span data-stu-id="345ec-143">Calling a method on a `$null` object throws a `RuntimeException`.</span></span>

```powershell
PS> $value = $null
PS> $value.toString()
You cannot call a method on a null-valued expression.
At line:1 char:1
+ $value.tostring()
+ ~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [], RuntimeException
    + FullyQualifiedErrorId : InvokeMethodOnNull
```

<span data-ttu-id="345ec-144">Когда я получаю сообщение `You cannot call a method on a null-valued expression`, первое, что я ищу, — это места, где я вызываю метод для переменной без предварительной проверки на соответствие `$null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-144">Whenever I see the phrase `You cannot call a method on a null-valued expression` then the first thing I look for are places where I am calling a method on a variable without first checking it for `$null`.</span></span>

## <a name="checking-for-null"></a><span data-ttu-id="345ec-145">Проверка на соответствие $null</span><span class="sxs-lookup"><span data-stu-id="345ec-145">Checking for $null</span></span>

<span data-ttu-id="345ec-146">Вы могли заметить, что при проверке на `$null` я всегда указываю `$null` слева в своих примерах.</span><span class="sxs-lookup"><span data-stu-id="345ec-146">You may have noticed that I always place the `$null` on the left when checking for `$null` in my examples.</span></span> <span data-ttu-id="345ec-147">Это сделано специально, как и рекомендуется в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="345ec-147">This is intentional and accepted as a PowerShell best practice.</span></span> <span data-ttu-id="345ec-148">Возможны ситуации, когда размещение $null справа не дает ожидаемого результата.</span><span class="sxs-lookup"><span data-stu-id="345ec-148">There are some scenarios where placing it on the right doesn't give you the expected result.</span></span>

<span data-ttu-id="345ec-149">Взгляните на следующий пример и постарайтесь предсказать результаты:</span><span class="sxs-lookup"><span data-stu-id="345ec-149">Look at this next example and try to predict the results:</span></span>

```powershell
if ( $value -eq $null )
{
    'The array is $null'
}
if ( $value -ne $null )
{
    'The array is not $null'
}
```

<span data-ttu-id="345ec-150">Если я не определяю `$value`, результатом первого условия будет `$true`, а мы получим сообщение `The array is $null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-150">If I do not define `$value`, the first one evaluates to `$true` and our message is `The array is $null`.</span></span> <span data-ttu-id="345ec-151">Ловушка заключается в том, что можно создать `$value`, допускающее, чтобы оба условия были `$false`.</span><span class="sxs-lookup"><span data-stu-id="345ec-151">The trap here is that it's possible to create a `$value` that allows both of them to be `$false`</span></span>

```powershell
$value = @( $null )
```

<span data-ttu-id="345ec-152">В данном случае `$value` является массивом, содержащим `$null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-152">In this case, the `$value` is an array that contains a `$null`.</span></span> <span data-ttu-id="345ec-153">`-eq` проверяет каждое значение в массиве и возвращает совпадающее значение `$null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-153">The `-eq` checks every value in the array and returns the `$null` that is matched.</span></span> <span data-ttu-id="345ec-154">Результатом этого будет `$false`.</span><span class="sxs-lookup"><span data-stu-id="345ec-154">This evaluates to `$false`.</span></span> <span data-ttu-id="345ec-155">`-ne` возвращает все, что не соответствует `$null`, и в этом случае не имеет результата (результатом также будет `$false`).</span><span class="sxs-lookup"><span data-stu-id="345ec-155">The `-ne` returns everything that doesn't match `$null` and in this case there are no results (This also evaluates to `$false`).</span></span> <span data-ttu-id="345ec-156">Ни одно из условий не является `$true`, тогда как кажется, что одно из них должно быть таким.</span><span class="sxs-lookup"><span data-stu-id="345ec-156">Neither one is `$true` even though it looks like one of them should be.</span></span>

<span data-ttu-id="345ec-157">Мы можем не только создать значение, допускающее, чтобы оба условия были `$false`, но и такое, когда оба из них станут `$true`.</span><span class="sxs-lookup"><span data-stu-id="345ec-157">Not only can we create a value that makes both of them evaluate to `$false`, it's possible to create a value where they both evaluate to `$true`.</span></span> <span data-ttu-id="345ec-158">Матиас Йессен (Mathias Jessen, @IISResetMe) опубликовал [Хорошая статья][] на эту тему.</span><span class="sxs-lookup"><span data-stu-id="345ec-158">Mathias Jessen (@IISResetMe) has a [good post][] that dives into that scenario.</span></span>

### <a name="psscriptanalyzer-and-vscode"></a><span data-ttu-id="345ec-159">PSScriptAnalyzer и VSCode</span><span class="sxs-lookup"><span data-stu-id="345ec-159">PSScriptAnalyzer and VSCode</span></span>

<span data-ttu-id="345ec-160">Модуль [PSScriptAnalyzer][] имеет правило для проверки таких коллизий, называющееся `PSPossibleIncorrectComparisonWithNull`.</span><span class="sxs-lookup"><span data-stu-id="345ec-160">The [PSScriptAnalyzer][] module has a rule that checks for this issue called `PSPossibleIncorrectComparisonWithNull`.</span></span>

```powershell
PS> Invoke-ScriptAnalyzer ./myscript.ps1

RuleName                              Message
--------                              -------
PSPossibleIncorrectComparisonWithNull $null should be on the left side of equality comparisons.
```

<span data-ttu-id="345ec-161">Поскольку VS Code также использует правила PSScriptAnalyser, в редакторе такие фрагменты кода выделяются и считаются проблемой.</span><span class="sxs-lookup"><span data-stu-id="345ec-161">Because VS Code uses the PSScriptAnalyser rules too, it also highlights or identifies this as a problem in your script.</span></span>

### <a name="simple-if-check"></a><span data-ttu-id="345ec-162">Простая проверка if</span><span class="sxs-lookup"><span data-stu-id="345ec-162">Simple if check</span></span>

<span data-ttu-id="345ec-163">Проверку на несоответствие значению $null обычно выполняют с помощью простой инструкции `if()` без сравнения.</span><span class="sxs-lookup"><span data-stu-id="345ec-163">A common way that people check for a non-$null value is to use a simple `if()` statement without the comparison.</span></span>

```powershell
if ( $value )
{
    Do-Something
}
```

<span data-ttu-id="345ec-164">Если значение равно `$null`, то результатом будет `$false`.</span><span class="sxs-lookup"><span data-stu-id="345ec-164">If the value is `$null`, this evaluates to `$false`.</span></span> <span data-ttu-id="345ec-165">Это выглядит просто, но только на первый взгляд.</span><span class="sxs-lookup"><span data-stu-id="345ec-165">This is easy to read, but be careful that it's looking for exactly what you're expecting it to look for.</span></span> <span data-ttu-id="345ec-166">Я понимаю эту строку кода как:</span><span class="sxs-lookup"><span data-stu-id="345ec-166">I read that line of code as:</span></span>

> <span data-ttu-id="345ec-167">Если `$value` имеет значение.</span><span class="sxs-lookup"><span data-stu-id="345ec-167">If `$value` has a value.</span></span>

<span data-ttu-id="345ec-168">Но это еще не все.</span><span class="sxs-lookup"><span data-stu-id="345ec-168">But that's not the whole story.</span></span> <span data-ttu-id="345ec-169">На самом деле строка значит следующее:</span><span class="sxs-lookup"><span data-stu-id="345ec-169">That line is actually saying:</span></span>

> <span data-ttu-id="345ec-170">Если `$value` не имеет значение `$null`, `0`, `$false` или `empty string`.</span><span class="sxs-lookup"><span data-stu-id="345ec-170">If `$value` is not `$null` or `0` or `$false` or an `empty string`</span></span>

<span data-ttu-id="345ec-171">Ниже приведен более полный пример этой инструкции.</span><span class="sxs-lookup"><span data-stu-id="345ec-171">Here is a more complete sample of that statement.</span></span>

```powershell
if ( $null -ne $value -and
        $value -ne 0 -and
        $value -ne '' -and
        $value -ne $false )
{
    Do-Something
}
```

<span data-ttu-id="345ec-172">Вполне допустимо использовать базовую проверку `if`, помня не только о значении переменной, но и о том, что другие значения считаются `$false`.</span><span class="sxs-lookup"><span data-stu-id="345ec-172">It's perfectly OK to use a basic `if` check as long as you remember those other values count as `$false` and not just that a variable has a value.</span></span>

<span data-ttu-id="345ec-173">Несколько дней назад я столкнулся с этой проблемой при рефакторинге кода.</span><span class="sxs-lookup"><span data-stu-id="345ec-173">I ran into this issue when refactoring some code a few days ago.</span></span> <span data-ttu-id="345ec-174">В нем присутствовала базовая проверка такого типа.</span><span class="sxs-lookup"><span data-stu-id="345ec-174">It had a basic property check like this.</span></span>

```powershell
if ( $object.property )
{
    $object.property = $value
}
```

<span data-ttu-id="345ec-175">Мне было нужно присвоить значение свойству объекта только в том случае, если он существует.</span><span class="sxs-lookup"><span data-stu-id="345ec-175">I wanted to assign a value to the object property only if it existed.</span></span> <span data-ttu-id="345ec-176">В большинстве случаев первоначальному объекту было присвоено значение, для которого возвращался результат `$true` при выполнении `if`.</span><span class="sxs-lookup"><span data-stu-id="345ec-176">In most cases, the original object had a value that would evaluate to `$true` in the `if` statement.</span></span> <span data-ttu-id="345ec-177">Но я столкнулся с проблемой, когда значение иногда не устанавливалось.</span><span class="sxs-lookup"><span data-stu-id="345ec-177">But I ran into an issue where the value was occasionally not getting set.</span></span> <span data-ttu-id="345ec-178">Я начал отладку и обнаружил, что у объекта есть свойство, но это пустое строковое значение.</span><span class="sxs-lookup"><span data-stu-id="345ec-178">I debugged the code and found that the object had the property but it was a blank string value.</span></span> <span data-ttu-id="345ec-179">Это вообще не позволяло ему обновляться в соответствии с предыдущей логикой.</span><span class="sxs-lookup"><span data-stu-id="345ec-179">This prevented it from ever getting updated with the previous logic.</span></span> <span data-ttu-id="345ec-180">Поэтому я добавил необходимую проверку на соответствие `$null`, и все заработало.</span><span class="sxs-lookup"><span data-stu-id="345ec-180">So I added a proper `$null` check and everything worked.</span></span>

```powershell
if ( $null -ne $object.property )
{
    $object.property = $value
}
```

<span data-ttu-id="345ec-181">Такие мелкие ошибки трудно обнаружить, что научило меня специально проверять значения на соответствие `$null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-181">It's little bugs like these that are hard to spot and make me aggressively check values for `$null`.</span></span>

## <a name="nullcount"></a><span data-ttu-id="345ec-182">$null.Count</span><span class="sxs-lookup"><span data-stu-id="345ec-182">$null.Count</span></span>

<span data-ttu-id="345ec-183">Если вы попытаетесь получить доступ к свойству по значению `$null`, это свойство также будет `$null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-183">If you try to access a property on a `$null` value, that the property is also `$null`.</span></span> <span data-ttu-id="345ec-184">Свойство `count` является исключением из этого правила.</span><span class="sxs-lookup"><span data-stu-id="345ec-184">The `count` property is the exception to this rule.</span></span>

```powershell
PS> $value = $null
PS> $value.count
0
```

<span data-ttu-id="345ec-185">Если у вас есть значение `$null`, то `count` равняется `0`.</span><span class="sxs-lookup"><span data-stu-id="345ec-185">When you have a `$null` value, then the `count` is `0`.</span></span> <span data-ttu-id="345ec-186">Это специальное свойство добавляется PowerShell.</span><span class="sxs-lookup"><span data-stu-id="345ec-186">This special property is added by PowerShell.</span></span>

### <a name="pscustomobject-count"></a><span data-ttu-id="345ec-187">[PSCustomObject] Count</span><span class="sxs-lookup"><span data-stu-id="345ec-187">[PSCustomObject] Count</span></span>

<span data-ttu-id="345ec-188">Почти у всех объектов в PowerShell есть свойство Count.</span><span class="sxs-lookup"><span data-stu-id="345ec-188">Almost all objects in PowerShell have that count property.</span></span> <span data-ttu-id="345ec-189">Одним из примечательных исключений является `[PSCustomObject]` в Windows PowerShell 5.1 (что было исправлено в PowerShell 6.0).</span><span class="sxs-lookup"><span data-stu-id="345ec-189">One important exception is the `[PSCustomObject]` in Windows PowerShell 5.1 (This is fixed in PowerShell 6.0).</span></span> <span data-ttu-id="345ec-190">У него нет свойства Count, поэтому при попытке его использования вы получаете значение `$null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-190">It doesn't have a count property so you get a `$null` value if you try to use it.</span></span> <span data-ttu-id="345ec-191">Я вспомнил это к тому, чтобы вы не пытались использовать `.Count` вместо проверки `$null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-191">I call this out here so that you don't try to use `.Count` instead of a `$null` check.</span></span>

<span data-ttu-id="345ec-192">Выполнение этого примера в Windows PowerShell 5.1 и PowerShell 6.0 дает разные результаты.</span><span class="sxs-lookup"><span data-stu-id="345ec-192">Running this example on Windows PowerShell 5.1 and PowerShell 6.0 gives you different results.</span></span>

```powershell
$value = [PSCustomObject]@{Name='MyObject'}
if ( $value.count -eq 1 )
{
    "We have a value"
}
```

## <a name="empty-null"></a><span data-ttu-id="345ec-193">Пустое значение NULL</span><span class="sxs-lookup"><span data-stu-id="345ec-193">Empty null</span></span>

<span data-ttu-id="345ec-194">Существует один особый тип `$null`, который отличается от остальных.</span><span class="sxs-lookup"><span data-stu-id="345ec-194">There is one special type of `$null` that acts differently than the others.</span></span> <span data-ttu-id="345ec-195">Я буду называть его пустым значением `$null`, тогда как фактически это [System.Management.Automation.Internal.AutomationNull][].</span><span class="sxs-lookup"><span data-stu-id="345ec-195">I am going to call it the empty `$null` but it's really a [System.Management.Automation.Internal.AutomationNull][].</span></span> <span data-ttu-id="345ec-196">Такое пустое значение `$null` вы получаете в результате выполнения функции или блока скрипта, которые не возвращают ничего (возвращают void).</span><span class="sxs-lookup"><span data-stu-id="345ec-196">This empty `$null` is the one you get as the result of a function or script block that returns nothing (a void result).</span></span>

```powershell
PS> function Get-Nothing {}
PS> $nothing = Get-Nothing
PS> $null -eq $nothing
True
```

<span data-ttu-id="345ec-197">Если сравнить его с `$null`, вы получите значение `$null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-197">If you compare it with `$null`, you get a `$null` value.</span></span> <span data-ttu-id="345ec-198">При использовании в вычислении, где требуется значение, его значение всегда будет `$null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-198">When used in an evaluation where a value is required, the value is always `$null`.</span></span> <span data-ttu-id="345ec-199">Но если поместить его в массив, он будет считаться пустым массивом.</span><span class="sxs-lookup"><span data-stu-id="345ec-199">But if you place it inside an array, it's treated the same as an empty array.</span></span>

```powershell
PS> $containempty = @( @() )
PS> $containnothing = @($nothing)
PS> $containnull = @($null)

PS> $containempty.count
0
PS> $containnothing.count
0
PS> $containnull.count
1
```

<span data-ttu-id="345ec-200">Можно создать массив с одним значением `$null`, при этом его свойство `count` будет равно `1`.</span><span class="sxs-lookup"><span data-stu-id="345ec-200">You can have an array that contains one `$null` value and its `count` is `1`.</span></span> <span data-ttu-id="345ec-201">Но если поместить пустой результат в массив, он не будет считаться элементом,</span><span class="sxs-lookup"><span data-stu-id="345ec-201">But if you place an empty result inside an array then it's not counted as an item.</span></span> <span data-ttu-id="345ec-202">а Count будет иметь значение `0`.</span><span class="sxs-lookup"><span data-stu-id="345ec-202">The count is `0`.</span></span>

<span data-ttu-id="345ec-203">Если пустое значение `$null` вы обрабатываете как коллекцию, она будет считаться пустой.</span><span class="sxs-lookup"><span data-stu-id="345ec-203">If you treat the empty `$null` like a collection, then it's empty.</span></span>

### <a name="pipeline"></a><span data-ttu-id="345ec-204">Pipeline</span><span class="sxs-lookup"><span data-stu-id="345ec-204">Pipeline</span></span>

<span data-ttu-id="345ec-205">Различия особенно заметны при работе с конвейером.</span><span class="sxs-lookup"><span data-stu-id="345ec-205">The primary place you see the difference is when using the pipeline.</span></span> <span data-ttu-id="345ec-206">Вы можете передать в него значение `$null`, но не пустое значение `$null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-206">You can pipe a `$null` value but not an empty `$null` value.</span></span>

```powershell
PS> $null | ForEach-Object{ Write-Output 'NULL Value' }
'NULL Value'
PS> $nothing | ForEach-Object{ Write-Output 'No Value' }
```

<span data-ttu-id="345ec-207">В зависимости от кода следует учитывать `$null` в логике.</span><span class="sxs-lookup"><span data-stu-id="345ec-207">Depending on your code, you should account for the `$null` in your logic.</span></span>

<span data-ttu-id="345ec-208">В любом случае сначала выполните проверку на соответствие `$null`:</span><span class="sxs-lookup"><span data-stu-id="345ec-208">Either check for `$null` first</span></span>

- <span data-ttu-id="345ec-209">В конвейере отфильтруйте значение NULL(`... | Where {$null -ne $_} | ...`).</span><span class="sxs-lookup"><span data-stu-id="345ec-209">Filter out null on the pipeline (`... | Where {$null -ne $_} | ...`)</span></span>
- <span data-ttu-id="345ec-210">Задайте его обработку с помощью функции конвейера.</span><span class="sxs-lookup"><span data-stu-id="345ec-210">Handle it in the pipeline function</span></span>

## <a name="foreach"></a><span data-ttu-id="345ec-211">foreach</span><span class="sxs-lookup"><span data-stu-id="345ec-211">foreach</span></span>

<span data-ttu-id="345ec-212">Одна из моих любимых возможностей метода `foreach` — это то, что он не выполняет перечисление по коллекции `$null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-212">One of my favorite features of `foreach` is that it doesn't enumerate over a `$null` collection.</span></span>

```powershell
foreach ( $node in $null )
{
    #skipped
}
```

<span data-ttu-id="345ec-213">Это избавляет от необходимости проверять коллекцию на соответствие `$null` перед ее перечислением.</span><span class="sxs-lookup"><span data-stu-id="345ec-213">This saves me from having to `$null` check the collection before I enumerate it.</span></span> <span data-ttu-id="345ec-214">Если у вас есть коллекция со значениями `$null`, объект `$node` также может иметь значение `$null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-214">If you have a collection of `$null` values, the `$node` can still be `$null`.</span></span>

<span data-ttu-id="345ec-215">Оператор foreach начал так работать с версии PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="345ec-215">The foreach started working this way with PowerShell 3.0.</span></span> <span data-ttu-id="345ec-216">Если у вас предыдущая версия, такой режим работы в ней не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="345ec-216">If you happen to be on an older version, then this is not the case.</span></span> <span data-ttu-id="345ec-217">Это одно из важных отличий, которое необходимо учитывать при обратном портировании кода для совместимости с версией 2.0.</span><span class="sxs-lookup"><span data-stu-id="345ec-217">This is one of the important changes to be aware of when back-porting code for 2.0 compatibility.</span></span>

## <a name="value-types"></a><span data-ttu-id="345ec-218">Типы значений</span><span class="sxs-lookup"><span data-stu-id="345ec-218">Value types</span></span>

<span data-ttu-id="345ec-219">Технически только ссылочные типы могут принимать значение `$null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-219">Technically, only reference types can be `$null`.</span></span> <span data-ttu-id="345ec-220">Но благодаря стараниям разработчиков PowerShell мы можем указывать любой тип для переменных.</span><span class="sxs-lookup"><span data-stu-id="345ec-220">But PowerShell is very generous and allows for variables to be any type.</span></span> <span data-ttu-id="345ec-221">Если вы решили строго типизировать значения, задать `$null` не получится.</span><span class="sxs-lookup"><span data-stu-id="345ec-221">If you decide to strongly type a value type, it cannot be `$null`.</span></span>
<span data-ttu-id="345ec-222">PowerShell преобразует `$null` в значение по умолчанию для многих типов.</span><span class="sxs-lookup"><span data-stu-id="345ec-222">PowerShell converts `$null` to a default value for many types.</span></span>

```powershell
PS> [int]$number = $null
PS> $number
0

PS> [bool]$boolean = $null
PS> $boolean
False

PS> [string]$string = $null
PS> $string -eq ''
True
```

<span data-ttu-id="345ec-223">У некоторых типов не предусмотрено значение для преобразования из `$null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-223">There are some types that do not have a valid conversion from `$null`.</span></span> <span data-ttu-id="345ec-224">Такие типы при обработке вызывают ошибку `Cannot convert null to type`.</span><span class="sxs-lookup"><span data-stu-id="345ec-224">These types generate a `Cannot convert null to type` error.</span></span>

```powershell
PS> [datetime]$date = $null
Cannot convert null to type "System.DateTime".
At line:1 char:1
+ [datetime]$date = $null
+ ~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : MetadataError: (:) [], ArgumentTransformationMetadataException
    + FullyQualifiedErrorId : RuntimeException
```

### <a name="function-parameters"></a><span data-ttu-id="345ec-225">Параметры функции</span><span class="sxs-lookup"><span data-stu-id="345ec-225">Function parameters</span></span>

<span data-ttu-id="345ec-226">Общепринято использовать строго типизированные значения в параметрах функций.</span><span class="sxs-lookup"><span data-stu-id="345ec-226">Using a strongly typed values in function parameters is very common.</span></span> <span data-ttu-id="345ec-227">Обычно мы стараемся определять типы параметров, даже если не собираемся определять типы других переменных в скриптах.</span><span class="sxs-lookup"><span data-stu-id="345ec-227">We generally learn to define the types of our parameters even if we tend not to define the types of other variables in our scripts.</span></span> <span data-ttu-id="345ec-228">Возможно, вы сами строго типизировали переменные в функциях, даже не осознавая этого.</span><span class="sxs-lookup"><span data-stu-id="345ec-228">You may already have some strongly typed variables in your functions and not even realize it.</span></span>

```powershell
function Do-Something
{
    param(
        [String] $Value
    )
}
```

<span data-ttu-id="345ec-229">Как только вы задаете тип параметра `string`, его значение не может быть `$null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-229">As soon as you set the type of the parameter as a `string`, the value can never be `$null`.</span></span> <span data-ttu-id="345ec-230">Обычно принято выполнять проверку на соответствие `$null`, чтобы выяснить, предоставил ли пользователь значение.</span><span class="sxs-lookup"><span data-stu-id="345ec-230">It's common to check if a value is `$null` to see if the user provided a value or not.</span></span>

```powershell
if ( $null -ne $Value ){...}
```

<span data-ttu-id="345ec-231">Если значение не указано, `$Value` является пустой строкой `''`.</span><span class="sxs-lookup"><span data-stu-id="345ec-231">`$Value` is an empty string `''` when no value is provided.</span></span> <span data-ttu-id="345ec-232">Вместо этого используйте автоматическую переменную `$PSBoundParameters.Value`.</span><span class="sxs-lookup"><span data-stu-id="345ec-232">Use the automatic variable `$PSBoundParameters.Value` instead.</span></span>

```powershell
if ( $null -ne $PSBoundParameters.Value ){...}
```

<span data-ttu-id="345ec-233">`$PSBoundParameters` содержит только параметры, указанные при вызове функции.</span><span class="sxs-lookup"><span data-stu-id="345ec-233">`$PSBoundParameters` only contains the parameters that were specified when the function was called.</span></span>
<span data-ttu-id="345ec-234">Для проверки свойства можно также использовать метод `ContainsKey`.</span><span class="sxs-lookup"><span data-stu-id="345ec-234">You can also use the `ContainsKey` method to check for the property.</span></span>

```powershell
if ( $PSBoundParameters.ContainsKey('Value') ){...}
```

### <a name="isnotnullorempty"></a><span data-ttu-id="345ec-235">IsNotNullOrEmpty</span><span class="sxs-lookup"><span data-stu-id="345ec-235">IsNotNullOrEmpty</span></span>

<span data-ttu-id="345ec-236">Если значение является строкой, можно использовать статическую строковую функцию для проверки того, является ли значение `$null` или пустой строкой одновременно.</span><span class="sxs-lookup"><span data-stu-id="345ec-236">If the value is a string, you can use a static string function to check if the value is `$null` or an empty string at the same time.</span></span>

```powershell
if ( -not [string]::IsNullOrEmpty( $value ) ){...}
```

<span data-ttu-id="345ec-237">Я часто так делаю, когда знаю, что тип значения должен быть строкой.</span><span class="sxs-lookup"><span data-stu-id="345ec-237">I find myself using this often when I know the value type should be a string.</span></span>

## <a name="when-i-null-check"></a><span data-ttu-id="345ec-238">Когда я выполняю проверку на соответствие $null</span><span class="sxs-lookup"><span data-stu-id="345ec-238">When I $null check</span></span>

<span data-ttu-id="345ec-239">Когда я пишу код, то стараюсь предусмотреть все варианты.</span><span class="sxs-lookup"><span data-stu-id="345ec-239">I am a defensive scripter.</span></span> <span data-ttu-id="345ec-240">Вызывая функцию и присваивая ее переменной, я проверяю ее на соответствие `$null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-240">Anytime I call a function and assign it to a variable, I check it for `$null`.</span></span>

```powershell
$userList = Get-ADUser kevmar
if ($null -ne $userList){...}
```

<span data-ttu-id="345ec-241">Я предпочитаю использовать `if` или `foreach`, а не `try/catch`.</span><span class="sxs-lookup"><span data-stu-id="345ec-241">I much prefer using `if` or `foreach` over using `try/catch`.</span></span> <span data-ttu-id="345ec-242">Не поймите мене неправильно, я часто пользуюсь `try/catch`.</span><span class="sxs-lookup"><span data-stu-id="345ec-242">Don't get me wrong, I still use `try/catch` a lot.</span></span> <span data-ttu-id="345ec-243">Но если я могу задать проверку на состояния ошибки или пустой набор результатов, я могу обеспечить обработку реальных исключений.</span><span class="sxs-lookup"><span data-stu-id="345ec-243">But if I can test for an error condition or an empty set of results, I can allow my exception handling be for true exceptions.</span></span>

<span data-ttu-id="345ec-244">Я стараюсь проверять на соответствие `$null` перед индексацией в значение или вызовом методов для объекта.</span><span class="sxs-lookup"><span data-stu-id="345ec-244">I also tend to check for `$null` before I index into a value or call methods on an object.</span></span> <span data-ttu-id="345ec-245">Оба этих действия не срабатывают для объектов `$null`, поэтому сначала нужно их проверить.</span><span class="sxs-lookup"><span data-stu-id="345ec-245">These two actions fail for a `$null` object so I find it important to validate them first.</span></span> <span data-ttu-id="345ec-246">Эти сценарии уже рассматривались ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="345ec-246">I already covered those scenarios earlier in this post.</span></span>

### <a name="no-results-scenario"></a><span data-ttu-id="345ec-247">Сценарий без результатов</span><span class="sxs-lookup"><span data-stu-id="345ec-247">No results scenario</span></span>

<span data-ttu-id="345ec-248">Важно помнить, что разные функции и команды по-разному обрабатывают сценарий без результатов.</span><span class="sxs-lookup"><span data-stu-id="345ec-248">It's important to know that different functions and commands handle the no results scenario differently.</span></span> <span data-ttu-id="345ec-249">Многие команды PowerShell возвращают пустое значение `$null` и ошибку в потоке ошибок,</span><span class="sxs-lookup"><span data-stu-id="345ec-249">Many PowerShell commands return the empty `$null` and an error in the error stream.</span></span> <span data-ttu-id="345ec-250">тогда как другие вызывают исключения или предоставляют объект состояния.</span><span class="sxs-lookup"><span data-stu-id="345ec-250">But others throw exceptions or give you a status object.</span></span> <span data-ttu-id="345ec-251">Вам нужно выяснить, как используемые вами команды работают со сценариями без результатов и сценариями ошибок.</span><span class="sxs-lookup"><span data-stu-id="345ec-251">It's still up to you to know how the commands you use deal with the no results and error scenarios.</span></span>

## <a name="initializing-to-null"></a><span data-ttu-id="345ec-252">Инициализация значения $null</span><span class="sxs-lookup"><span data-stu-id="345ec-252">Initializing to $null</span></span>

<span data-ttu-id="345ec-253">У меня выработалась привычка инициализировать все переменные перед их использованием.</span><span class="sxs-lookup"><span data-stu-id="345ec-253">One habit that I have picked up is initializing all my variables before I use them.</span></span> <span data-ttu-id="345ec-254">В других языках это обязательно.</span><span class="sxs-lookup"><span data-stu-id="345ec-254">You are required to do this in other languages.</span></span> <span data-ttu-id="345ec-255">В начале функции или цикла foreach я определяю все используемые значения.</span><span class="sxs-lookup"><span data-stu-id="345ec-255">At the top of my function or as I enter a foreach loop, I define all the values that I'm using.</span></span>

<span data-ttu-id="345ec-256">Вот сценарий, который я советую вам внимательно изучить.</span><span class="sxs-lookup"><span data-stu-id="345ec-256">Here is a scenario that I want you to take a close look at.</span></span> <span data-ttu-id="345ec-257">Это пример ошибки, которую я однажды выявлял.</span><span class="sxs-lookup"><span data-stu-id="345ec-257">It's an example of a bug I had to chase down before.</span></span>

```powershell
function Do-Something
{
    foreach ( $node in 1..6 )
    {
        try
        {
            $result = Get-Something -ID $node
        }
        catch
        {
            Write-Verbose "[$result] not valid"
        }

        if ( $null -ne $result )
        {
            Update-Something $result
        }
    }
}
```

<span data-ttu-id="345ec-258">Здесь предполагается, что `Get-Something` возвращает либо результат, либо пустое значение `$null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-258">The expectation here is that `Get-Something` returns either a result or an empty `$null`.</span></span> <span data-ttu-id="345ec-259">Если возникает ошибка, она регистрируется в журнале.</span><span class="sxs-lookup"><span data-stu-id="345ec-259">If there is an error, we log it.</span></span> <span data-ttu-id="345ec-260">Перед ее обработкой мы проводим проверку, чтобы убедиться в том, что получен допустимый результат.</span><span class="sxs-lookup"><span data-stu-id="345ec-260">Then we check to make sure we got a valid result before processing it.</span></span>

<span data-ttu-id="345ec-261">Ошибка в этом коде возникает, когда `Get-Something` создает исключение и не присваивает `$result` значение.</span><span class="sxs-lookup"><span data-stu-id="345ec-261">The bug hiding in this code is when `Get-Something` throws an exception and doesn't assign a value to `$result`.</span></span> <span data-ttu-id="345ec-262">Выполнение кода завершается ошибкой до назначения, поэтому переменной `$result` даже не присваивается значение `$null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-262">It fails before the assignment so we don't even assign `$null` to the `$result` variable.</span></span> <span data-ttu-id="345ec-263">Переменная `$result` сохраняет допустимое значение `$result` из предыдущих итераций.</span><span class="sxs-lookup"><span data-stu-id="345ec-263">`$result` still contains the previous valid `$result` from other iterations.</span></span>
<span data-ttu-id="345ec-264">В этом примере `Update-Something` выполняется несколько раз с одним и тем же объектом.</span><span class="sxs-lookup"><span data-stu-id="345ec-264">`Update-Something` to execute multiple times on the same object in this example.</span></span>

<span data-ttu-id="345ec-265">Устранить проблему мне удалось после того, как я задал `$null` для `$result` прямо в цикле foreach.</span><span class="sxs-lookup"><span data-stu-id="345ec-265">I set `$result` to `$null` right inside the foreach loop before I use it to mitigate this issue.</span></span>

```powershell
foreach ( $node in 1..6 )
{
    $result = $null
    try
    {
        ...
```

### <a name="scope-issues"></a><span data-ttu-id="345ec-266">Проблемы с областью действия</span><span class="sxs-lookup"><span data-stu-id="345ec-266">Scope issues</span></span>

<span data-ttu-id="345ec-267">Это также помогает устранить проблемы, связанные с областью действия функции.</span><span class="sxs-lookup"><span data-stu-id="345ec-267">This also helps mitigate scoping issues.</span></span> <span data-ttu-id="345ec-268">В следующем примере мы будем последовательно задавать значения `$result` в цикле.</span><span class="sxs-lookup"><span data-stu-id="345ec-268">In that example, we assign values to `$result` over and over in a loop.</span></span> <span data-ttu-id="345ec-269">Поскольку PowerShell позволяет значениям переменных, находящимся за пределами функции, попадать в область действия текущей функции, их инициализация в функции снижает вероятность ошибок, которые могут возникать в таких ситуациях.</span><span class="sxs-lookup"><span data-stu-id="345ec-269">But because PowerShell allows variable values from outside the function to bleed into the scope of the current function, initializing them inside your function mitigates bugs that can be introduced that way.</span></span>

<span data-ttu-id="345ec-270">Неинициализированная переменная в функции не имеет значения `$null`, если ей присвоено значение в родительской области.</span><span class="sxs-lookup"><span data-stu-id="345ec-270">An uninitialized variable in your function is not `$null` if it's set to a value in a parent scope.</span></span>
<span data-ttu-id="345ec-271">Родительской областью может быть другая функция, которая вызывает эту функцию и использует такие же имена переменных.</span><span class="sxs-lookup"><span data-stu-id="345ec-271">The parent scope could be another function that calls your function and uses the same variable names.</span></span>

<span data-ttu-id="345ec-272">Если взять тот же пример `Do-something` и удалить из него цикл, то код будет таким:</span><span class="sxs-lookup"><span data-stu-id="345ec-272">If I take that same `Do-something` example and remove the loop, I would end up with something that looks like this example:</span></span>

```powershell
function Invoke-Something
{
    $result = 'ParentScope'
    Do-Something
}

function Do-Something
{
    try
    {
        $result = Get-Something -ID $node
    }
    catch
    {
        Write-Verbose "[$result] not valid"
    }

    if ( $null -ne $result )
    {
        Update-Something $result
    }
}
```

<span data-ttu-id="345ec-273">Если вызов `Get-Something` возвращает исключение, тогда проверка на соответствие `$null` найдет `$result` в `Invoke-Something`.</span><span class="sxs-lookup"><span data-stu-id="345ec-273">If the call to `Get-Something` throws an exception, then my `$null` check finds the `$result` from `Invoke-Something`.</span></span> <span data-ttu-id="345ec-274">Инициализация значения внутри функции устраняет эту ошибку.</span><span class="sxs-lookup"><span data-stu-id="345ec-274">Initializing the value inside your function mitigates this issue.</span></span>

<span data-ttu-id="345ec-275">Именовать переменные сложно, и разработчики часто используют одинаковые имена переменных в разных функциях.</span><span class="sxs-lookup"><span data-stu-id="345ec-275">Naming variables is hard and it's common for an author to use the same variable names in multiple functions.</span></span> <span data-ttu-id="345ec-276">Например, я постоянно использую `$node`,`$result` и `$data`.</span><span class="sxs-lookup"><span data-stu-id="345ec-276">I know I use `$node`,`$result`,`$data` all the time.</span></span> <span data-ttu-id="345ec-277">Из-за этого значения из других областей могут легко появиться в тех местах, где их не должно быть.</span><span class="sxs-lookup"><span data-stu-id="345ec-277">So it would be very easy for values from different scopes to show up in places where they should not be.</span></span>

## <a name="redirect-output-to-null"></a><span data-ttu-id="345ec-278">Перенаправление вывода в $null</span><span class="sxs-lookup"><span data-stu-id="345ec-278">Redirect output to $null</span></span>

<span data-ttu-id="345ec-279">Все вышесказанное касалось значений `$null`, но тема не будет раскрыта, если не объяснить, как перенаправлять выходные данные в `$null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-279">I have been talking about `$null` values for this entire article but the topic is not complete if I didn't mention redirecting output to `$null`.</span></span> <span data-ttu-id="345ec-280">Бывают команды, выходные данные или объекты которых нужно опустить.</span><span class="sxs-lookup"><span data-stu-id="345ec-280">There are times when you have commands that output information or objects that you want to suppress.</span></span> <span data-ttu-id="345ec-281">Это можно сделать, перенаправив выходные данные в `$null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-281">Redirecting output to `$null` does that.</span></span>

### <a name="out-null"></a><span data-ttu-id="345ec-282">Out-Null</span><span class="sxs-lookup"><span data-stu-id="345ec-282">Out-Null</span></span>

<span data-ttu-id="345ec-283">Команда Out-Null — это встроенный способ перенаправления данных конвейера в `$null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-283">The Out-Null command is the built-in way to redirect pipeline data to `$null`.</span></span>

```powershell
New-Item -Type Directory -Path $path | Out-Null
```

### <a name="assign-to-null"></a><span data-ttu-id="345ec-284">Назначение в $null</span><span class="sxs-lookup"><span data-stu-id="345ec-284">Assign to $null</span></span>

<span data-ttu-id="345ec-285">Результатам команды можно назначить значение `$null`, что будет аналогично использованию `Out-Null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-285">You can assign the results of a command to `$null` for the same effect as using `Out-Null`.</span></span>

```powershell
$null = New-Item -Type Directory -Path $path
```

<span data-ttu-id="345ec-286">Поскольку `$null` является постоянным значением, перезаписать его нельзя.</span><span class="sxs-lookup"><span data-stu-id="345ec-286">Because `$null` is a constant value, you can never overwrite it.</span></span> <span data-ttu-id="345ec-287">Мне не нравится такая реализация в коде, но этот способ часто работает быстрее, чем `Out-Null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-287">I don't like the way it looks in my code but it often performs faster than `Out-Null`.</span></span>

### <a name="redirect-to-null"></a><span data-ttu-id="345ec-288">Перенаправление в $null</span><span class="sxs-lookup"><span data-stu-id="345ec-288">Redirect to $null</span></span>

<span data-ttu-id="345ec-289">Можно также использовать оператор перенаправления для отправки выходных данных в `$null`.</span><span class="sxs-lookup"><span data-stu-id="345ec-289">You can also use the redirection operator to send output to `$null`.</span></span>

```powershell
New-Item -Type Directory -Path $path > $null
```

<span data-ttu-id="345ec-290">Если вы работаете с исполняемыми файлами командной строки, которые выводят данные в различные потоки,</span><span class="sxs-lookup"><span data-stu-id="345ec-290">If you're dealing with command-line executables that output on the different streams.</span></span> <span data-ttu-id="345ec-291">вы можете перенаправить все выходные потоки в `$null` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="345ec-291">You can redirect all output streams to `$null` like this:</span></span>

```powershell
git status *> $null
```

## <a name="summary"></a><span data-ttu-id="345ec-292">Сводка</span><span class="sxs-lookup"><span data-stu-id="345ec-292">Summary</span></span>

<span data-ttu-id="345ec-293">Здесь я много рассказал о $null, но статья получилась несколько отрывочной.</span><span class="sxs-lookup"><span data-stu-id="345ec-293">I covered a lot of ground on this one and I know this article is more fragmented than most of my deep dives.</span></span> <span data-ttu-id="345ec-294">Все потому, что значения `$null` могут встречаться повсюду в PowerShell, и их трактовка будет обусловлена конкретным местом.</span><span class="sxs-lookup"><span data-stu-id="345ec-294">That is because `$null` values can pop up in many different places in PowerShell and all the nuances are specific to where you find it.</span></span> <span data-ttu-id="345ec-295">Надеюсь, теперь вы лучше разобрались с `$null` и непонятными ситуациями, где это состояние может повстречаться.</span><span class="sxs-lookup"><span data-stu-id="345ec-295">I hope you walk away from this with a better understanding of `$null` and an awareness of the more obscure scenarios you may run into.</span></span>

<!-- link references -->
[Оригинал статьи]: https://powershellexplained.com/2018-12-23-Powershell-null-everything-you-wanted-to-know/
[original version]: https://powershellexplained.com/2018-12-23-Powershell-null-everything-you-wanted-to-know/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[Хорошая статья]: https://blog.iisreset.me/schrodingers-argumentlist
[good post]: https://blog.iisreset.me/schrodingers-argumentlist
[PSScriptAnalyzer]: https://www.powershellgallery.com/packages/PSScriptAnalyzer
[System.Management.Automation.Internal.AutomationNull]: /dotnet/api/system.management.automation.internal.automationnull
