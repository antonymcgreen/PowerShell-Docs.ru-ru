---
title: Все, что вы когда-либо хотели знать об инструкции switch
description: Инструкция switch в PowerShell обеспечивает возможности, которых нет в других языках.
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: c2e77aa5fb36d04fec1bc86f751291205120c729
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2020
ms.locfileid: "93355125"
---
# <a name="everything-you-ever-wanted-to-know-about-the-switch-statement"></a><span data-ttu-id="93ad2-103">Все, что вы когда-либо хотели знать об инструкции switch</span><span class="sxs-lookup"><span data-stu-id="93ad2-103">Everything you ever wanted to know about the switch statement</span></span>

<span data-ttu-id="93ad2-104">Как и многие другие языки, PowerShell содержит команды для управления потоком выполнения в скриптах.</span><span class="sxs-lookup"><span data-stu-id="93ad2-104">Like many other languages, PowerShell has commands for controlling the flow of execution within your scripts.</span></span> <span data-ttu-id="93ad2-105">Одна из них — инструкция [switch][], которая обеспечивает в PowerShell возможности, отсутствующие в других языках.</span><span class="sxs-lookup"><span data-stu-id="93ad2-105">One of those statements is the [switch][] statement and in PowerShell, it offers features that aren't found in other languages.</span></span> <span data-ttu-id="93ad2-106">Сегодня мы подробно рассмотрим работу с `switch` в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93ad2-106">Today, we take a deep dive into working with the PowerShell `switch`.</span></span>

> [!NOTE]
> <span data-ttu-id="93ad2-107">[Оригинал][] этой статьи впервые был опубликован в блоге автора [@KevinMarquette][].</span><span class="sxs-lookup"><span data-stu-id="93ad2-107">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="93ad2-108">Команда разработчиков PowerShell благодарит Кевина за то, что он поделился с нами этим материалом.</span><span class="sxs-lookup"><span data-stu-id="93ad2-108">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="93ad2-109">Читайте его блог — [PowerShellExplained.com][].</span><span class="sxs-lookup"><span data-stu-id="93ad2-109">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="the-if-statement"></a><span data-ttu-id="93ad2-110">Инструкция `if`</span><span class="sxs-lookup"><span data-stu-id="93ad2-110">The `if` statement</span></span>

<span data-ttu-id="93ad2-111">Одна из первых инструкций, которую вы изучите, — `if`.</span><span class="sxs-lookup"><span data-stu-id="93ad2-111">One of the first statements that you learn is the `if` statement.</span></span> <span data-ttu-id="93ad2-112">Она позволяет выполнять блок скрипта, если значение инструкции `$true`.</span><span class="sxs-lookup"><span data-stu-id="93ad2-112">It lets you execute a script block if a statement is `$true`.</span></span>

``` powershell
if ( Test-Path $Path )
{
    Remove-Item $Path
}
```

<span data-ttu-id="93ad2-113">Инструкции `elseif` и `else` позволяют использовать гораздо более сложную логику.</span><span class="sxs-lookup"><span data-stu-id="93ad2-113">You can have much more complicated logic by using `elseif` and `else` statements.</span></span> <span data-ttu-id="93ad2-114">Ниже приведен пример, в котором у меня есть числовое значение, обозначающее день недели, а я хочу получить имя в виде строки.</span><span class="sxs-lookup"><span data-stu-id="93ad2-114">Here is an example where I have a numeric value for day of the week and I want to get the name as a string.</span></span>

``` powershell
$day = 3

if ( $day -eq 0 ) { $result = 'Sunday'        }
elseif ( $day -eq 1 ) { $result = 'Monday'    }
elseif ( $day -eq 2 ) { $result = 'Tuesday'   }
elseif ( $day -eq 3 ) { $result = 'Wednesday' }
elseif ( $day -eq 4 ) { $result = 'Thursday'  }
elseif ( $day -eq 5 ) { $result = 'Friday'    }
elseif ( $day -eq 6 ) { $result = 'Saturday'  }

$result
```

```Output
Wednesday
```

<span data-ttu-id="93ad2-115">На самом деле это довольно типичная ситуация, и решить эту задачу можно множеством способов.</span><span class="sxs-lookup"><span data-stu-id="93ad2-115">It turns out that this is a common pattern and there are many ways to deal with this.</span></span> <span data-ttu-id="93ad2-116">В частности, с помощью инструкции `switch`.</span><span class="sxs-lookup"><span data-stu-id="93ad2-116">One of them is with a `switch`.</span></span>

## <a name="switch-statement"></a><span data-ttu-id="93ad2-117">Оператор switch</span><span class="sxs-lookup"><span data-stu-id="93ad2-117">Switch statement</span></span>

<span data-ttu-id="93ad2-118">Инструкция `switch` позволяет указать переменную и список возможных значений.</span><span class="sxs-lookup"><span data-stu-id="93ad2-118">The `switch` statement allows you to provide a variable and a list of possible values.</span></span> <span data-ttu-id="93ad2-119">Если значение соответствует переменной, выполняется ее блок ScriptBlock.</span><span class="sxs-lookup"><span data-stu-id="93ad2-119">If the value matches the variable, then its scriptblock is executed.</span></span>

``` powershell
$day = 3

switch ( $day )
{
    0 { $result = 'Sunday'    }
    1 { $result = 'Monday'    }
    2 { $result = 'Tuesday'   }
    3 { $result = 'Wednesday' }
    4 { $result = 'Thursday'  }
    5 { $result = 'Friday'    }
    6 { $result = 'Saturday'  }
}

$result
```

```Output
'Wednesday'
```

<span data-ttu-id="93ad2-120">В этом примере значение `$day` соответствует одному из числовых значений, поэтому `$result` присваивается правильное имя.</span><span class="sxs-lookup"><span data-stu-id="93ad2-120">For this example, the value of `$day` matches one of the numeric values, then the correct name is assigned to `$result`.</span></span> <span data-ttu-id="93ad2-121">В данном случае мы просто присваиваем значение переменной, но в таких блоках скриптов можно выполнять любые команды PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93ad2-121">We are only doing a variable assignment in this example, but any PowerShell can be executed in those script blocks.</span></span>

### <a name="assign-to-a-variable"></a><span data-ttu-id="93ad2-122">Присвоение значения переменной</span><span class="sxs-lookup"><span data-stu-id="93ad2-122">Assign to a variable</span></span>

<span data-ttu-id="93ad2-123">Этот последний пример можно написать иначе.</span><span class="sxs-lookup"><span data-stu-id="93ad2-123">We can write that last example in another way.</span></span>

``` powershell
$result = switch ( $day )
{
    0 { 'Sunday'    }
    1 { 'Monday'    }
    2 { 'Tuesday'   }
    3 { 'Wednesday' }
    4 { 'Thursday'  }
    5 { 'Friday'    }
    6 { 'Saturday'  }
}
```

<span data-ttu-id="93ad2-124">Поместим значение в конвейер PowerShell и присвоим его переменной `$result`.</span><span class="sxs-lookup"><span data-stu-id="93ad2-124">We are placing the value on the PowerShell pipeline and assigning it to the `$result`.</span></span> <span data-ttu-id="93ad2-125">Это же действие можно выполнить с помощью инструкций `if` и `foreach`.</span><span class="sxs-lookup"><span data-stu-id="93ad2-125">You can do this same thing with the `if` and `foreach` statements.</span></span>

### <a name="default"></a><span data-ttu-id="93ad2-126">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="93ad2-126">Default</span></span>

<span data-ttu-id="93ad2-127">Воспользовавшись ключевым словом `default`, можно определить, что должно произойти при отсутствии совпадения.</span><span class="sxs-lookup"><span data-stu-id="93ad2-127">We can use the `default` keyword to identify the what should happen if there is no match.</span></span>

``` powershell
$result = switch ( $day )
{
    0 { 'Sunday' }
    # ...
    6 { 'Saturday' }
    default { 'Unknown' }
}
```

<span data-ttu-id="93ad2-128">Здесь по умолчанию возвращается значение `Unknown`.</span><span class="sxs-lookup"><span data-stu-id="93ad2-128">Here we return the value `Unknown` in the default case.</span></span>

### <a name="strings"></a><span data-ttu-id="93ad2-129">строк</span><span class="sxs-lookup"><span data-stu-id="93ad2-129">Strings</span></span>

<span data-ttu-id="93ad2-130">Я в этих последних примерах сопоставлял числа, но вы также можете сопоставлять строки.</span><span class="sxs-lookup"><span data-stu-id="93ad2-130">I was matching numbers in those last examples, but you can also match strings.</span></span>

``` powershell
$item = 'Role'

switch ( $item )
{
    Component
    {
        'is a component'
    }
    Role
    {
        'is a role'
    }
    Location
    {
        'is a location'
    }
}
```

```Output
is a role
```

<span data-ttu-id="93ad2-131">Я решил не заключать здесь совпадения с `Component`, `Role` и `Location` в кавычки, подчеркнув тем самым тот факт, что они необязательны.</span><span class="sxs-lookup"><span data-stu-id="93ad2-131">I decided not to wrap the `Component`,`Role` and `Location` matches in quotes here to highlight that they're optional.</span></span> <span data-ttu-id="93ad2-132">В большинстве случаев `switch` обрабатывает их как строку.</span><span class="sxs-lookup"><span data-stu-id="93ad2-132">The `switch` treats those as a string in most cases.</span></span>

## <a name="arrays"></a><span data-ttu-id="93ad2-133">Массивы</span><span class="sxs-lookup"><span data-stu-id="93ad2-133">Arrays</span></span>

<span data-ttu-id="93ad2-134">Одна из замечательных особенностей PowerShell `switch` — особый способ обработки массивов.</span><span class="sxs-lookup"><span data-stu-id="93ad2-134">One of the cool features of the PowerShell `switch` is the way it handles arrays.</span></span> <span data-ttu-id="93ad2-135">Если передать инструкции `switch` массив, она обработает каждый элемент в этой коллекции.</span><span class="sxs-lookup"><span data-stu-id="93ad2-135">If you give a `switch` an array, it processes each element in that collection.</span></span>

``` powershell
$roles = @('WEB','Database')

switch ( $roles ) {
    'Database'   { 'Configure SQL' }
    'WEB'        { 'Configure IIS' }
    'FileServer' { 'Configure Share' }
}
```

```Output
Configure IIS
Configure SQL
```

<span data-ttu-id="93ad2-136">Если в массиве есть повторяющиеся элементы, они будут сопоставляться в соответствующем разделе несколько раз.</span><span class="sxs-lookup"><span data-stu-id="93ad2-136">If you have repeated items in your array, then they're matched multiple times by the appropriate section.</span></span>

### <a name="psitem"></a><span data-ttu-id="93ad2-137">PSItem</span><span class="sxs-lookup"><span data-stu-id="93ad2-137">PSItem</span></span>

<span data-ttu-id="93ad2-138">С помощью `$PSItem` или `$_` можно ссылаться на текущий обработанный элемент.</span><span class="sxs-lookup"><span data-stu-id="93ad2-138">You can use the `$PSItem` or `$_` to reference the current item that was processed.</span></span> <span data-ttu-id="93ad2-139">При выполнении простого сопоставления `$PSItem` — это сопоставляемое значение.</span><span class="sxs-lookup"><span data-stu-id="93ad2-139">When we do a simple match, `$PSItem` is the value that we are matching.</span></span> <span data-ttu-id="93ad2-140">В следующем разделе я покажу, как выполнить более сложные сопоставления с использованием этой переменной.</span><span class="sxs-lookup"><span data-stu-id="93ad2-140">I'll be performing some advanced matches in the next section where this variable is used.</span></span>

## <a name="parameters"></a><span data-ttu-id="93ad2-141">Параметры</span><span class="sxs-lookup"><span data-stu-id="93ad2-141">Parameters</span></span>

<span data-ttu-id="93ad2-142">Уникальная особенность инструкции `switch` в PowerShell заключается в наличии ряда [параметров-переключателей][], которые изменяют ее способ выполнения.</span><span class="sxs-lookup"><span data-stu-id="93ad2-142">A unique feature of the PowerShell `switch` is that it has a number of [switch parameters][] that change how it performs.</span></span>

### <a name="-casesensitive"></a><span data-ttu-id="93ad2-143">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="93ad2-143">-CaseSensitive</span></span>

<span data-ttu-id="93ad2-144">По умолчанию сопоставления выполняются без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="93ad2-144">The matches aren't case-sensitive by default.</span></span> <span data-ttu-id="93ad2-145">Если необходимо учитывать регистр, можно использовать параметр `-CaseSensitive`.</span><span class="sxs-lookup"><span data-stu-id="93ad2-145">If you need to be case-sensitive, you can use `-CaseSensitive`.</span></span> <span data-ttu-id="93ad2-146">Его можно использовать в сочетании с другими параметрами-переключателями.</span><span class="sxs-lookup"><span data-stu-id="93ad2-146">This can be used in combination with the other switch parameters.</span></span>

### <a name="-wildcard"></a><span data-ttu-id="93ad2-147">-Wildcard</span><span class="sxs-lookup"><span data-stu-id="93ad2-147">-Wildcard</span></span>

<span data-ttu-id="93ad2-148">Поддержку подстановочных знаков в switch можно включить с помощью параметра `-wildcard`.</span><span class="sxs-lookup"><span data-stu-id="93ad2-148">We can enable wildcard support with the `-wildcard` switch.</span></span> <span data-ttu-id="93ad2-149">При этом для каждого соответствия используется та же логика применения подстановочных знаков, что и у оператора `-like`.</span><span class="sxs-lookup"><span data-stu-id="93ad2-149">This uses the same wildcard logic as the `-like` operator to do each match.</span></span>

``` powershell
$Message = 'Warning, out of disk space'

switch -Wildcard ( $message )
{
    'Error*'
    {
        Write-Error -Message $Message
    }
    'Warning*'
    {
        Write-Warning -Message $Message
    }
    default
    {
        Write-Information $message
    }
}
```

```Output
WARNING: Warning, out of disk space
```

<span data-ttu-id="93ad2-150">В этом случае мы обрабатываем сообщение, а затем помещаем его в различные потоки на основе содержимого.</span><span class="sxs-lookup"><span data-stu-id="93ad2-150">Here we are processing a message and then outputting it on different streams based on the contents.</span></span>

### <a name="-regex"></a><span data-ttu-id="93ad2-151">-Regex</span><span class="sxs-lookup"><span data-stu-id="93ad2-151">-Regex</span></span>

<span data-ttu-id="93ad2-152">Инструкция switch поддерживает сопоставление не только с помощью подстановочных знаков, но и с использованием регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="93ad2-152">The switch statement supports regex matches just like it does wildcards.</span></span>

``` powershell
switch -Regex ( $message )
{
    '^Error'
    {
        Write-Error -Message $Message
    }
    '^Warning'
    {
        Write-Warning -Message $Message
    }
    default
    {
        Write-Information $message
    }
}
```

<span data-ttu-id="93ad2-153">Дополнительные примеры приведены в другой моей статье, где описывается [множество способов использования регулярных выражений][].</span><span class="sxs-lookup"><span data-stu-id="93ad2-153">I have more examples of using regex in another article I wrote: [The many ways to use regex][].</span></span>

### <a name="-file"></a><span data-ttu-id="93ad2-154">-File</span><span class="sxs-lookup"><span data-stu-id="93ad2-154">-File</span></span>

<span data-ttu-id="93ad2-155">Малоизвестная возможность инструкции switch заключается в том, что при использовании параметра `-File` она может обработать файл.</span><span class="sxs-lookup"><span data-stu-id="93ad2-155">A little known feature of the switch statement is that it can process a file with the `-File` parameter.</span></span> <span data-ttu-id="93ad2-156">Вместо того чтобы присваивать переменное выражение, используйте `-file` с путем к файлу.</span><span class="sxs-lookup"><span data-stu-id="93ad2-156">You use `-file` with a path to a file instead of giving it a variable expression.</span></span>

``` powershell
switch -Wildcard -File $path
{
    'Error*'
    {
        Write-Error -Message $PSItem
    }
    'Warning*'
    {
        Write-Warning -Message $PSItem
    }
    default
    {
        Write-Output $PSItem
    }
}
```

<span data-ttu-id="93ad2-157">Принцип действия будет таким же, как при обработке массива.</span><span class="sxs-lookup"><span data-stu-id="93ad2-157">It works just like processing an array.</span></span> <span data-ttu-id="93ad2-158">В этом примере я использую этот параметр для сопоставления вместе с подстановочными знаками и `$PSItem`.</span><span class="sxs-lookup"><span data-stu-id="93ad2-158">In this example, I combine it with wildcard matching and make use of the `$PSItem`.</span></span> <span data-ttu-id="93ad2-159">В результате выполняется обработка файла журнала и преобразование его в предупреждения и сообщения об ошибках в зависимости от совпадений, полученных на основе регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="93ad2-159">This would process a log file and convert it to warning and error messages depending on the regex matches.</span></span>

## <a name="advanced-details"></a><span data-ttu-id="93ad2-160">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="93ad2-160">Advanced details</span></span>

<span data-ttu-id="93ad2-161">Теперь, когда вы знаете обо всех этих документированных возможностях, мы можем использовать их в контексте более сложной обработки.</span><span class="sxs-lookup"><span data-stu-id="93ad2-161">Now that you're aware of all these documented features, we can use them in the context of more advanced processing.</span></span>

### <a name="expressions"></a><span data-ttu-id="93ad2-162">Выражения</span><span class="sxs-lookup"><span data-stu-id="93ad2-162">Expressions</span></span>

<span data-ttu-id="93ad2-163">Инструкцию `switch` можно применять не только к переменной, но и к выражению.</span><span class="sxs-lookup"><span data-stu-id="93ad2-163">The `switch` can be on an expression instead of a variable.</span></span>

``` powershell
switch ( ( Get-Service | Where status -eq 'running' ).name ) {...}
```

<span data-ttu-id="93ad2-164">Результат вычисления выражения и будет тем значением, которое используется для сопоставления.</span><span class="sxs-lookup"><span data-stu-id="93ad2-164">Whatever the expression evaluates to is the value used for the match.</span></span>

### <a name="multiple-matches"></a><span data-ttu-id="93ad2-165">Несколько совпадений</span><span class="sxs-lookup"><span data-stu-id="93ad2-165">Multiple matches</span></span>

<span data-ttu-id="93ad2-166">Возможно, вы уже догадались, что для сопоставления с помощью `switch` можно использовать несколько условий.</span><span class="sxs-lookup"><span data-stu-id="93ad2-166">You may have already picked up on this, but a `switch` can match to multiple conditions.</span></span> <span data-ttu-id="93ad2-167">Это особенно актуально при сопоставлении с использованием `-wildcard` или `-regex`.</span><span class="sxs-lookup"><span data-stu-id="93ad2-167">This is especially true when using `-wildcard` or `-regex` matches.</span></span> <span data-ttu-id="93ad2-168">Одно и то же условие можно добавить несколько раз, и все они будут активированы.</span><span class="sxs-lookup"><span data-stu-id="93ad2-168">You can add the same condition multiple times and all of them are triggered.</span></span>

``` powershell
switch ( 'Word' )
{
    'word' { 'lower case word match' }
    'Word' { 'mixed case word match' }
    'WORD' { 'upper case word match' }
}
```

```Output
lower case word match
mixed case word match
upper case word match
```

<span data-ttu-id="93ad2-169">Здесь сработают все три инструкции.</span><span class="sxs-lookup"><span data-stu-id="93ad2-169">All three of these statements are fired.</span></span> <span data-ttu-id="93ad2-170">Это свидетельствует о том, что проверяется каждое условие (по порядку).</span><span class="sxs-lookup"><span data-stu-id="93ad2-170">This shows that every condition is checked (in order).</span></span> <span data-ttu-id="93ad2-171">Это справедливо и для обработки массивов, где каждое условие проверяется для каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="93ad2-171">This holds true for processing arrays where each item checks each condition.</span></span>

### <a name="continue"></a><span data-ttu-id="93ad2-172">Continue</span><span class="sxs-lookup"><span data-stu-id="93ad2-172">Continue</span></span>

<span data-ttu-id="93ad2-173">Как правило, в таких случаях добавляют инструкцию `break`, но сначала давайте разберемся, как использовать `continue`.</span><span class="sxs-lookup"><span data-stu-id="93ad2-173">Normally, this is where I would introduce the `break` statement, but it's better that we learn how to use `continue` first.</span></span> <span data-ttu-id="93ad2-174">Как и в цикле `foreach`, `continue` переходит к следующему элементу в коллекции или выходит из `switch`, если элементов не осталось.</span><span class="sxs-lookup"><span data-stu-id="93ad2-174">Just like with a `foreach` loop, `continue` continues onto the next item in the collection or exits the `switch` if there are no more items.</span></span> <span data-ttu-id="93ad2-175">Мы можем переписать последний пример с использованием операторов continue, чтобы выполнялась только одна инструкция.</span><span class="sxs-lookup"><span data-stu-id="93ad2-175">We can rewrite that last example with continue statements so that only one statement executes.</span></span>

``` powershell
switch ( 'Word' )
{
    'word'
    {
        'lower case word match'
        continue
    }
    'Word'
    {
        'mixed case word match'
        continue
    }
    'WORD'
    {
        'upper case word match'
        continue
    }
}
```

```Output
lower case word match
```

<span data-ttu-id="93ad2-176">Вместо того чтобы сопоставлять все три элемента, сопоставляется только первый из них, после чего switch переходит к следующему значению.</span><span class="sxs-lookup"><span data-stu-id="93ad2-176">Instead of matching all three items, the first one is matched and the switch continues to the next value.</span></span> <span data-ttu-id="93ad2-177">Так как значений для обработки не осталось, выполнение switch завершается.</span><span class="sxs-lookup"><span data-stu-id="93ad2-177">Because there are no values left to process, the switch exits.</span></span> <span data-ttu-id="93ad2-178">В следующем примере показано, как подстановочный знак может сопоставляться с несколькими элементами.</span><span class="sxs-lookup"><span data-stu-id="93ad2-178">This next example is showing how a wildcard could match multiple items.</span></span>

``` powershell
switch -Wildcard -File $path
{
    '*Error*'
    {
        Write-Error -Message $PSItem
        continue
    }
    '*Warning*'
    {
        Write-Warning -Message $PSItem
        continue
    }
    default
    {
        Write-Output $PSItem
    }
}
```

<span data-ttu-id="93ad2-179">Так как строка во входном файле может содержать как слово `Error`, так и слово `Warning`, необходимо, чтобы инструкция выполнялась только для первого из них, а затем продолжалась обработка файла.</span><span class="sxs-lookup"><span data-stu-id="93ad2-179">Because a line in the input file could contain both the word `Error` and `Warning`, we only want the first one to execute and then continue processing the file.</span></span>

### <a name="break"></a><span data-ttu-id="93ad2-180">Break</span><span class="sxs-lookup"><span data-stu-id="93ad2-180">Break</span></span>

<span data-ttu-id="93ad2-181">Инструкция `break` выполняет выход из switch.</span><span class="sxs-lookup"><span data-stu-id="93ad2-181">A `break` statement exits the switch.</span></span> <span data-ttu-id="93ad2-182">Для отдельных значений ее поведение такое же, как у `continue`.</span><span class="sxs-lookup"><span data-stu-id="93ad2-182">This is the same behavior that `continue` presents for single values.</span></span> <span data-ttu-id="93ad2-183">Разница проявляется при обработке массива.</span><span class="sxs-lookup"><span data-stu-id="93ad2-183">The difference is shown when processing an array.</span></span> <span data-ttu-id="93ad2-184">`break` останавливает всю обработку в switch, а `continue` выполняет переход к следующему элементу.</span><span class="sxs-lookup"><span data-stu-id="93ad2-184">`break` stops all processing in the switch and `continue` moves onto the next item.</span></span>

``` powershell
$Messages = @(
    'Downloading update'
    'Ran into errors downloading file'
    'Error: out of disk space'
    'Sending email'
    '...'
)

switch -Wildcard ($Messages)
{
    'Error*'
    {
        Write-Error -Message $PSItem
        break
    }
    '*Error*'
    {
        Write-Warning -Message $PSItem
        continue
    }
    '*Warning*'
    {
        Write-Warning -Message $PSItem
        continue
    }
    default
    {
        Write-Output $PSItem
    }
}
```

```Output
Downloading update
WARNING: Ran into errors downloading file
write-error -message $PSItem : Error: out of disk space
+ CategoryInfo          : NotSpecified: (:) [Write-Error], WriteErrorException
+ FullyQualifiedErrorId : Microsoft.PowerShell.Commands.WriteErrorException
```

<span data-ttu-id="93ad2-185">В этом случае при совпадении с любой строкой, начинающейся с `Error`, выводится сообщение об ошибке и выполнение инструкции switch останавливается.</span><span class="sxs-lookup"><span data-stu-id="93ad2-185">In this case, if we hit any lines that start with `Error` then we get an error and the switch stops.</span></span>
<span data-ttu-id="93ad2-186">Вот что делает инструкция `break`.</span><span class="sxs-lookup"><span data-stu-id="93ad2-186">This is what that `break` statement is doing for us.</span></span> <span data-ttu-id="93ad2-187">Если слово `Error` найдено в середине, а не в начале строки, она записывается как предупреждение.</span><span class="sxs-lookup"><span data-stu-id="93ad2-187">If we find `Error` inside the string and not just at the beginning, we write it as a warning.</span></span> <span data-ttu-id="93ad2-188">Сделаем то же самое для `Warning`.</span><span class="sxs-lookup"><span data-stu-id="93ad2-188">We do the same thing for `Warning`.</span></span> <span data-ttu-id="93ad2-189">Строка может содержать как слово `Error`, так и слово `Warning`, но для обработки требуется только одно из них.</span><span class="sxs-lookup"><span data-stu-id="93ad2-189">It's possible that a line could have both the word `Error` and `Warning`, but we only need one to process.</span></span> <span data-ttu-id="93ad2-190">Этот то, что делает инструкция `continue`.</span><span class="sxs-lookup"><span data-stu-id="93ad2-190">This is what the `continue` statement is doing for us.</span></span>

### <a name="break-labels"></a><span data-ttu-id="93ad2-191">Метки прерывания</span><span class="sxs-lookup"><span data-stu-id="93ad2-191">Break labels</span></span>

<span data-ttu-id="93ad2-192">Инструкция `switch` поддерживает метки `break/continue` так же, как `foreach`.</span><span class="sxs-lookup"><span data-stu-id="93ad2-192">The `switch` statement supports `break/continue` labels just like `foreach`.</span></span>

``` powershell
:filelist foreach($path in $logs)
{
    :logFile switch -Wildcard -File $path
    {
        'Error*'
        {
            Write-Error -Message $PSItem
            break filelist
        }
        'Warning*'
        {
            Write-Error -Message $PSItem
            break logFile
        }
        default
        {
            Write-Output $PSItem
        }
    }
}
```

<span data-ttu-id="93ad2-193">Мне лично не нравится использовать метки разрыва, но я хочу обратить на них внимание, так как при первом знакомстве с ними могут возникнуть определенные сложности.</span><span class="sxs-lookup"><span data-stu-id="93ad2-193">I personally don't like the use of break labels but I wanted to point them out because they're confusing if you've never seen them before.</span></span> <span data-ttu-id="93ad2-194">При наличии нескольких вложенных инструкций `switch` или `foreach` может потребоваться прерывание на разных уровнях, а не только на самом внутреннем элементе.</span><span class="sxs-lookup"><span data-stu-id="93ad2-194">When you have multiple `switch` or `foreach` statements that are nested, you may want to break out of more than the inner most item.</span></span> <span data-ttu-id="93ad2-195">В `switch` можно поместить метку, которая и будет целевым объектом для `break`.</span><span class="sxs-lookup"><span data-stu-id="93ad2-195">You can place a label on a `switch` that can be the target of your `break`.</span></span>

### <a name="enum"></a><span data-ttu-id="93ad2-196">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="93ad2-196">Enum</span></span>

<span data-ttu-id="93ad2-197">В PowerShell 5.0 поддерживаются перечисления, которые можно использовать в switch.</span><span class="sxs-lookup"><span data-stu-id="93ad2-197">PowerShell 5.0 gave us enums and we can use them in a switch.</span></span>

``` powershell
enum Context {
    Component
    Role
    Location
}

$item = [Context]::Role

switch ( $item )
{
    Component
    {
        'is a component'
    }
    Role
    {
        'is a role'
    }
    Location
    {
        'is a location'
    }
}
```

```Output
is a role
```

<span data-ttu-id="93ad2-198">Если вы хотите хранить все данные как строго типизированные перечисления, их можно взять в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="93ad2-198">If you want to keep everything as strongly typed enums, then you can place them in parentheses.</span></span>

``` powershell
switch ($item )
{
    ([Context]::Component)
    {
        'is a component'
    }
    ([Context]::Role)
    {
        'is a role'
    }
    ([Context]::Location)
    {
        'is a location'
    }
}
```

<span data-ttu-id="93ad2-199">Здесь круглые скобки необходимы, чтобы инструкция switch не интерпретировала значение `[Context]::Location` как литеральную строку.</span><span class="sxs-lookup"><span data-stu-id="93ad2-199">The parentheses are needed here so that the switch doesn't treat the value `[Context]::Location` as a literal string.</span></span>

### <a name="scriptblock"></a><span data-ttu-id="93ad2-200">ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="93ad2-200">ScriptBlock</span></span>

<span data-ttu-id="93ad2-201">При необходимости для оценки соответствия можно использовать блок ScriptBlock.</span><span class="sxs-lookup"><span data-stu-id="93ad2-201">We can use a scriptblock to perform the evaluation for a match if needed.</span></span>

``` powershell
$age = 37

switch ( $age )
{
    {$PSItem -le 18}
    {
        'child'
    }
    {$PSItem -gt 18}
    {
        'adult'
    }
}
```

```Output
'adult'
```

<span data-ttu-id="93ad2-202">Такой подход повышает сложность и может затруднить чтение `switch`.</span><span class="sxs-lookup"><span data-stu-id="93ad2-202">This adds complexity and can make your `switch` hard to read.</span></span> <span data-ttu-id="93ad2-203">В большинстве случаев, когда требуется использовать что-то подобное, лучше воспользоваться инструкциями `if` и `elseif`.</span><span class="sxs-lookup"><span data-stu-id="93ad2-203">In most cases where you would use something like this it would be better to use `if` and `elseif` statements.</span></span> <span data-ttu-id="93ad2-204">Я бы воспользовался этим вариантом, если бы у меня уже была большая инструкция switch и мне нужно было, чтобы два элемента попали в один и тот же блок оценки.</span><span class="sxs-lookup"><span data-stu-id="93ad2-204">I would consider using this if I already had a large switch in place and I needed two items to hit the same evaluation block.</span></span>

<span data-ttu-id="93ad2-205">Мне кажется, что для улучшения читаемости блок ScriptBlock можно заключить в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="93ad2-205">One thing that I think helps with legibility is to place the scriptblock in parentheses.</span></span>

``` powershell
switch ( $age )
{
    ({$PSItem -le 18})
    {
        'child'
    }
    ({$PSItem -gt 18})
    {
        'adult'
    }
}
```

<span data-ttu-id="93ad2-206">Он будет выполняться таким же образом, но при этом визуальная разбивка станет удобнее для быстрого просмотра.</span><span class="sxs-lookup"><span data-stu-id="93ad2-206">It still executes the same way and gives a better visual break when quickly looking at it.</span></span>

### <a name="regex-matches"></a><span data-ttu-id="93ad2-207">Регулярное выражение $matches</span><span class="sxs-lookup"><span data-stu-id="93ad2-207">Regex $matches</span></span>

<span data-ttu-id="93ad2-208">Нам нужно вернуться к регулярному выражению, чтобы поработать над одним неочевидным аспектом.</span><span class="sxs-lookup"><span data-stu-id="93ad2-208">We need to revisit regex to touch on something that isn't immediately obvious.</span></span> <span data-ttu-id="93ad2-209">При использовании регулярного выражения заполняется переменная `$matches`.</span><span class="sxs-lookup"><span data-stu-id="93ad2-209">The use of regex populates the `$matches` variable.</span></span> <span data-ttu-id="93ad2-210">Использование переменной `$matches` подробно рассмотрено в статье о [Множество способов использования регулярных выражений][].</span><span class="sxs-lookup"><span data-stu-id="93ad2-210">I do go into the use of `$matches` more when I talk about [The many ways to use regex][].</span></span> <span data-ttu-id="93ad2-211">Здесь же приведен краткий пример, демонстрирующий ее в действии при использовании с именованными совпадениями.</span><span class="sxs-lookup"><span data-stu-id="93ad2-211">Here is a quick sample to show it in action with named matches.</span></span>

``` powershell
$message = 'my ssn is 123-23-3456 and credit card: 1234-5678-1234-5678'

switch -regex ($message)
{
    '(?<SSN>\d\d\d-\d\d-\d\d\d\d)'
    {
        Write-Warning "message contains a SSN: $($matches.SSN)"
    }
    '(?<CC>\d\d\d\d-\d\d\d\d-\d\d\d\d-\d\d\d\d)'
    {
        Write-Warning "message contains a credit card number: $($matches.CC)"
    }
    '(?<Phone>\d\d\d-\d\d\d-\d\d\d\d)'
    {
        Write-Warning "message contains a phone number: $($matches.Phone)"
    }
}
```

```Output
WARNING: message may contain a SSN: 123-23-3456
WARNING: message may contain a credit card number: 1234-5678-1234-5678
```

### <a name="null"></a><span data-ttu-id="93ad2-212">$null</span><span class="sxs-lookup"><span data-stu-id="93ad2-212">$null</span></span>

<span data-ttu-id="93ad2-213">Вы можете выполнить сопоставление со значением `$null`, которое не обязательно должно быть значением по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="93ad2-213">You can match a `$null` value that doesn't have to be the default.</span></span>

``` powershell
$value = $null

switch ( $value )
{
    $null
    {
        'Value is null'
    }
    default
    {
        'value is not null'
    }
}

```Output
Value is null
```

<span data-ttu-id="93ad2-214">То же касается пустой строки.</span><span class="sxs-lookup"><span data-stu-id="93ad2-214">Same goes for an empty string.</span></span>

``` powershell
switch ( '' )
{
    ''
    {
        'Value is empty'
    }
    default
    {
        'value is a empty string'
    }
}

```Output
Value is empty
```

### <a name="constant-expression"></a><span data-ttu-id="93ad2-215">Константное выражение</span><span class="sxs-lookup"><span data-stu-id="93ad2-215">Constant expression</span></span>

<span data-ttu-id="93ad2-216">Ли Дейли отмечает, что для вычисления элементов `[bool]` можно использовать константное выражение `$true`.</span><span class="sxs-lookup"><span data-stu-id="93ad2-216">Lee Dailey pointed out that we can use a constant `$true` expression to evaluate `[bool]` items.</span></span>
<span data-ttu-id="93ad2-217">Представьте, что у нас есть несколько логических проверок, которые необходимо выполнить.</span><span class="sxs-lookup"><span data-stu-id="93ad2-217">Imagine if we have several boolean checks that need to happen.</span></span>

``` powershell
$isVisible = $false
$isEnabled = $true
$isSecure = $true

switch ( $true )
{
    $isEnabled
    {
        'Do-Action'
    }
    $isVisible
    {
        'Show-Animation'
    }
    $isSecure
    {
        'Enable-AdminMenu'
    }
}
```

```Output
Do-Action
Enabled-AdminMenu
```

<span data-ttu-id="93ad2-218">Используя такой подход, можно непосредственно оценить состояние нескольких логических полей и выполнить над ними соответствующее действие.</span><span class="sxs-lookup"><span data-stu-id="93ad2-218">This is a clean way to evaluate and take action on the status of several boolean fields.</span></span> <span data-ttu-id="93ad2-219">Его преимущество в том, что одно совпадение может отражать состояние значения, которое еще не было оценено.</span><span class="sxs-lookup"><span data-stu-id="93ad2-219">The cool thing about this is that you can have one match flip the status of a value that hasn't been evaluated yet.</span></span>

``` powershell
$isVisible = $false
$isEnabled = $true
$isAdmin = $false

switch ( $true )
{
    $isEnabled
    {
        'Do-Action'
        $isVisible = $true
    }
    $isVisible
    {
        'Show-Animation'
    }
    $isAdmin
    {
        'Enable-AdminMenu'
    }
}
```

```Output
Do-Action
Show-Animation
```

<span data-ttu-id="93ad2-220">Поскольку в этом примере для `$isEnabled` задано значение `$true`, для `$isVisible` также должно быть задано значение `$true`.</span><span class="sxs-lookup"><span data-stu-id="93ad2-220">Setting `$isEnabled` to `$true` in this example makes sure that `$isVisible` is also set to `$true`.</span></span> <span data-ttu-id="93ad2-221">Тогда при вычислении переменной `$isVisible` будет вызываться ее ScriptBlock.</span><span class="sxs-lookup"><span data-stu-id="93ad2-221">Then when `$isVisible` gets evaluated, its scriptblock is invoked.</span></span> <span data-ttu-id="93ad2-222">Это не совсем интуитивный, но весьма остроумный способ применения этой возможности.</span><span class="sxs-lookup"><span data-stu-id="93ad2-222">This is a bit counter-intuitive but is a clever use of the mechanics.</span></span>

### <a name="switch-automatic-variable"></a><span data-ttu-id="93ad2-223">Автоматическая переменная $switch</span><span class="sxs-lookup"><span data-stu-id="93ad2-223">$switch automatic variable</span></span>

<span data-ttu-id="93ad2-224">Когда инструкция `switch` обрабатывает значения, она создает перечислитель и вызывает его `$switch`.</span><span class="sxs-lookup"><span data-stu-id="93ad2-224">When the `switch` is processing its values, it creates an enumerator and calls it `$switch`.</span></span> <span data-ttu-id="93ad2-225">Это автоматически созданная PowerShell переменная, с которой можно работать напрямую.</span><span class="sxs-lookup"><span data-stu-id="93ad2-225">This is an automatic variable created by PowerShell and you can manipulate it directly.</span></span>

```powershell
$a = 1, 2, 3, 4

switch($a) {
    1 { [void]$switch.MoveNext(); $switch.Current }
    3 { [void]$switch.MoveNext(); $switch.Current }
}
```

<span data-ttu-id="93ad2-226">Получаем такие результаты:</span><span class="sxs-lookup"><span data-stu-id="93ad2-226">This gives you the results of:</span></span>

```Output
2
4
```

<span data-ttu-id="93ad2-227">При переходе перечислителя к следующему элементу тот не обрабатывается с помощью `switch`, но к его значению можно получить доступ напрямую.</span><span class="sxs-lookup"><span data-stu-id="93ad2-227">By moving the enumerator forward, the next item doesn't get processed by the `switch` but you can access that value directly.</span></span> <span data-ttu-id="93ad2-228">Как по мне, это уж слишком.</span><span class="sxs-lookup"><span data-stu-id="93ad2-228">I would call it madness.</span></span>

## <a name="other-patterns"></a><span data-ttu-id="93ad2-229">Прочие ситуации</span><span class="sxs-lookup"><span data-stu-id="93ad2-229">Other patterns</span></span>

### <a name="hashtables"></a><span data-ttu-id="93ad2-230">хэш-таблицы;</span><span class="sxs-lookup"><span data-stu-id="93ad2-230">Hashtables</span></span>

<span data-ttu-id="93ad2-231">Одна из моих самых популярных публикаций посвящена [хэш-таблицам][].</span><span class="sxs-lookup"><span data-stu-id="93ad2-231">One of my most popular posts is the one I did on [hashtables][].</span></span> <span data-ttu-id="93ad2-232">Один из вариантов использования `hashtable` — таблица подстановки.</span><span class="sxs-lookup"><span data-stu-id="93ad2-232">One of the use cases for a `hashtable` is to be a lookup table.</span></span> <span data-ttu-id="93ad2-233">Это альтернативный подход для типичной ситуации, в которой зачастую применяется инструкция `switch`.</span><span class="sxs-lookup"><span data-stu-id="93ad2-233">That is an alternate approach to a common pattern that a `switch` statement is often addressing.</span></span>

``` powershell
$day = 3

$lookup = @{
    0 = 'Sunday'
    1 = 'Monday'
    2 = 'Tuesday'
    3 = 'Wednesday'
    4 = 'Thursday'
    5 = 'Friday'
    6 = 'Saturday'
}

$lookup[$day]
```

```Output
Wednesday
```

<span data-ttu-id="93ad2-234">Если я использую `switch` лишь для подстановки, я часто применяю `hashtable`.</span><span class="sxs-lookup"><span data-stu-id="93ad2-234">If I'm only using a `switch` as a lookup, I often use a `hashtable` instead.</span></span>

### <a name="enum"></a><span data-ttu-id="93ad2-235">Перечисление.</span><span class="sxs-lookup"><span data-stu-id="93ad2-235">Enum</span></span>

<span data-ttu-id="93ad2-236">В PowerShell 5.0 появилась функция `Enum`, и в данном случае можно использовать также ее.</span><span class="sxs-lookup"><span data-stu-id="93ad2-236">PowerShell 5.0 introduced the `Enum` and it's also an option in this case.</span></span>

``` powershell
$day = 3

enum DayOfTheWeek {
    Sunday
    Monday
    Tuesday
    Wednesday
    Thursday
    Friday
    Saturday
}

[DayOfTheWeek]$day
```

```Output
Wednesday
```

<span data-ttu-id="93ad2-237">Способов решения этой задачи очень много, так что на их обсуждение ушел бы целый день.</span><span class="sxs-lookup"><span data-stu-id="93ad2-237">We could go all day looking at different ways to solve this problem.</span></span> <span data-ttu-id="93ad2-238">Я же лишь хотел рассказать о том, что существуют различные варианты.</span><span class="sxs-lookup"><span data-stu-id="93ad2-238">I just wanted to make sure you knew you had options.</span></span>

## <a name="final-words"></a><span data-ttu-id="93ad2-239">Заключение</span><span class="sxs-lookup"><span data-stu-id="93ad2-239">Final words</span></span>

<span data-ttu-id="93ad2-240">Несмотря на свою кажущуюся простоту, инструкция switch зачастую предоставляет дополнительные возможности, о которых большинство даже и не подозревает.</span><span class="sxs-lookup"><span data-stu-id="93ad2-240">The switch statement is simple on the surface but it offers some advanced features that most people don't realize are available.</span></span> <span data-ttu-id="93ad2-241">Если использовать их все вместе, получится довольно эффективный инструмент.</span><span class="sxs-lookup"><span data-stu-id="93ad2-241">Stringing those features together makes this a powerful feature.</span></span> <span data-ttu-id="93ad2-242">Надеюсь, вы узнали что-то, о чем раньше и не подозревали.</span><span class="sxs-lookup"><span data-stu-id="93ad2-242">I hope you learned something that you had not realized before.</span></span>

<!-- link references -->
[Оригинал]: https://powershellexplained.com/2018-01-12-Powershell-switch-statement/
[original version]: https://powershellexplained.com/2018-01-12-Powershell-switch-statement/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[switch]: /powershell/module/microsoft.powershell.core/about/about_switch
[параметров-переключателей]: https://www.powershellmagazine.com/2013/12/20/using-powershell-switch-vs-boolean-parameters-in-sma-runbooks/
[switch parameters]: https://www.powershellmagazine.com/2013/12/20/using-powershell-switch-vs-boolean-parameters-in-sma-runbooks/
[Множество способов использования регулярных выражений]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression
[The many ways to use regex]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression
[хэш-таблицам]: everything-about-hashtable.md
[hashtables]: everything-about-hashtable.md
