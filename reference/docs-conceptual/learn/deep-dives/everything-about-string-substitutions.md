---
title: Все, что вы хотели знать о подстановке переменных в строках
description: Существует множество способов использования переменных в строках для создания форматированного текста.
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 786526fb98dbf1b3ec7c5c6c985ac95b85a96259
ms.sourcegitcommit: 4bb44f183dcbfa8dced57f075812e02d3b45fd70
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2020
ms.locfileid: "86301324"
---
# <a name="everything-you-wanted-to-know-about-variable-substitution-in-strings"></a><span data-ttu-id="d2ea7-103">Все, что вы хотели знать о подстановке переменных в строках</span><span class="sxs-lookup"><span data-stu-id="d2ea7-103">Everything you wanted to know about variable substitution in strings</span></span>

<span data-ttu-id="d2ea7-104">Переменные в строках можно использовать множеством способов.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-104">There are many ways to use variables in strings.</span></span> <span data-ttu-id="d2ea7-105">Я называю это подстановкой переменных, но подразумеваю все ситуации, когда необходимо отформатировать строку с учетом значений переменных.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-105">I'm calling this variable substitution but I'm referring to any time you want to format a string to include values from variables.</span></span> <span data-ttu-id="d2ea7-106">Мне часто приходится объяснять этот момент новичкам, изучающим создание скриптов.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-106">This is something that I often find myself explaining to new scripters.</span></span>

> [!NOTE]
> <span data-ttu-id="d2ea7-107">[Оригинал][] этой статьи впервые был опубликован в блоге автора [@KevinMarquette][].</span><span class="sxs-lookup"><span data-stu-id="d2ea7-107">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="d2ea7-108">Команда разработчиков PowerShell благодарит Кевина за то, что он поделился с нами этим материалом.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-108">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="d2ea7-109">Читайте его блог — [PowerShellExplained.com][].</span><span class="sxs-lookup"><span data-stu-id="d2ea7-109">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="concatenation"></a><span data-ttu-id="d2ea7-110">Объединение</span><span class="sxs-lookup"><span data-stu-id="d2ea7-110">Concatenation</span></span>

<span data-ttu-id="d2ea7-111">Первый класс методов можно называть объединением.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-111">The first class of methods can be referred to as concatenation.</span></span> <span data-ttu-id="d2ea7-112">По сути, они принимают несколько строк и объединяют их друг с другом.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-112">It's basically taking several strings and joining them together.</span></span> <span data-ttu-id="d2ea7-113">Объединение уже довольно давно используется для создания форматированных строк.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-113">There's a long history of using concatenation to build formatted strings.</span></span>

```powershell
$name = 'Kevin Marquette'
$message = 'Hello, ' + $name
```

<span data-ttu-id="d2ea7-114">Объединение отлично подходит для ситуаций, когда необходимо добавить всего несколько значений.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-114">Concatenation works out OK when there are only a few values to add.</span></span> <span data-ttu-id="d2ea7-115">Однако зачастую применять его довольно сложно.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-115">But this can get complicated quickly.</span></span>

```powershell
$first = 'Kevin'
$last = 'Marquette'
```

```powershell
$message = 'Hello, ' + $first + ' ' + $last + '.'
```

<span data-ttu-id="d2ea7-116">Этот простой пример читать уже труднее.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-116">This simple example is already getting harder to read.</span></span>

## <a name="variable-substitution"></a><span data-ttu-id="d2ea7-117">Подстановка переменных</span><span class="sxs-lookup"><span data-stu-id="d2ea7-117">Variable substitution</span></span>

<span data-ttu-id="d2ea7-118">В PowerShell есть более простой вариант.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-118">PowerShell has another option that is easier.</span></span> <span data-ttu-id="d2ea7-119">Переменные можно задавать непосредственно в строках.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-119">You can specify your variables directly in the strings.</span></span>

```powershell
$message = "Hello, $first $last."
```

<span data-ttu-id="d2ea7-120">Многое зависит от типа кавычек, в которые заключена строка.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-120">The type of quotes you use around the string makes a difference.</span></span> <span data-ttu-id="d2ea7-121">Строка, заключенная в двойные кавычки, допускает подстановку, а строка с одинарными кавычками — нет.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-121">A double quoted string allows the substitution but a single quoted string doesn't.</span></span> <span data-ttu-id="d2ea7-122">Вы можете выбрать подходящий вариант в зависимости от ситуации.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-122">There are times you want one or the other so you have an option.</span></span>

## <a name="command-substitution"></a><span data-ttu-id="d2ea7-123">Подстановка команд</span><span class="sxs-lookup"><span data-stu-id="d2ea7-123">Command substitution</span></span>

<span data-ttu-id="d2ea7-124">Если вы пытаетесь получить значения свойств в строку, ситуация немного усложняется.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-124">Things get a little tricky when you start trying to get the values of properties into a string.</span></span> <span data-ttu-id="d2ea7-125">Многие новички испытывают с этим проблемы.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-125">This is where many new people get tripped up.</span></span> <span data-ttu-id="d2ea7-126">Позвольте мне сначала показать, что, по их мнению, должно сработать (по идее, все выглядит логично).</span><span class="sxs-lookup"><span data-stu-id="d2ea7-126">First let me show you what they think should work (and at face value almost looks like it should).</span></span>

```powershell
$directory = Get-Item 'c:\windows'
$message = "Time: $directory.CreationTime"
```

<span data-ttu-id="d2ea7-127">Казалось бы, вы должны получить `CreationTime` из `$directory`, но вместо этого вы получаете в качестве значения `Time: c:\windows.CreationTime`.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-127">You would be expecting to get the `CreationTime` off of the `$directory`, but instead you get this `Time: c:\windows.CreationTime` as your value.</span></span> <span data-ttu-id="d2ea7-128">Причина в том, что подстановка такого типа распознает только базовую переменную.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-128">The reason is that this type of substitution only sees the base variable.</span></span> <span data-ttu-id="d2ea7-129">Она интерпретирует точку как часть строки, поэтому не сопоставляет значение на более глубоких уровнях.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-129">It considers the period as part of the string so it stops resolving the value any deeper.</span></span>

<span data-ttu-id="d2ea7-130">Выходит так, что при помещении в строку этот объект предоставляет строку в качестве значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-130">It just so happens that this object gives a string as a default value when placed into a string.</span></span>
<span data-ttu-id="d2ea7-131">Некоторые объекты вместо этого предоставляют имя типа, например `System.Collections.Hashtable`.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-131">Some objects give you the type name instead like `System.Collections.Hashtable`.</span></span> <span data-ttu-id="d2ea7-132">Это то, на что нужно обратить внимание.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-132">Just something to watch for.</span></span>

<span data-ttu-id="d2ea7-133">PowerShell позволяет выполнять команды внутри строки с помощью специального синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-133">PowerShell allows you to do command execution inside the string with a special syntax.</span></span> <span data-ttu-id="d2ea7-134">Это позволяет получить свойства этих объектов и выполнить любую другую команду для получения значения.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-134">This allows us to get the properties of these objects and run any other command to get a value.</span></span>

```powershell
$message = "Time: $($directory.CreationTime)"
```

<span data-ttu-id="d2ea7-135">Этот подход отлично подходит для определенных ситуаций, но в некоторых случаях может оказаться таким же неудобным, как объединение при наличии нескольких переменных.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-135">This works great for some situations but it can get just as crazy as concatenation if you have just a few variables.</span></span>

### <a name="command-execution"></a><span data-ttu-id="d2ea7-136">Выполнение команды</span><span class="sxs-lookup"><span data-stu-id="d2ea7-136">Command execution</span></span>

<span data-ttu-id="d2ea7-137">Команды можно выполнять внутри строки.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-137">You can run commands inside a string.</span></span> <span data-ttu-id="d2ea7-138">Хотя так можно делать, мне это не нравится.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-138">Even though I have this option, I don't like it.</span></span> <span data-ttu-id="d2ea7-139">Код быстро становится перегруженным, и его трудно отлаживать.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-139">It gets cluttered quickly and hard to debug.</span></span> <span data-ttu-id="d2ea7-140">Я либо использую команду и сохраняю ее результат в переменную, либо использую строку форматирования.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-140">I either run the command and save to a variable or use a format string.</span></span>

```powershell
$message = "Date: $(Get-Date)"
```

## <a name="format-string"></a><span data-ttu-id="d2ea7-141">Строка форматирования</span><span class="sxs-lookup"><span data-stu-id="d2ea7-141">Format string</span></span>

<span data-ttu-id="d2ea7-142">.NET позволяет отформатировать строки, с которыми довольно легко работать.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-142">.NET has a way to format strings that I find fairly easy to work with.</span></span> <span data-ttu-id="d2ea7-143">Сначала позвольте продемонстрировать статический метод, после чего я покажу, как сделать то же самое с помощью ярлыка PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-143">First let me show you the static method for it before I show you the PowerShell shortcut to do the same thing.</span></span>

```powershell
# .NET string format string
[string]::Format('Hello, {0} {1}.',$first,$last)

# PowerShell format string
'Hello, {0} {1}.' -f $first, $last
```

<span data-ttu-id="d2ea7-144">В этом случае строка анализируется на наличие токенов `{0}` и `{1}`, а затем этот номер используется для выбора среди предоставленных значений.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-144">What is happening here is that the string is parsed for the tokens `{0}` and `{1}`, then it uses that number to pick from the values provided.</span></span> <span data-ttu-id="d2ea7-145">Если вы хотите повторить одно значение в строке, можно повторно использовать его номер.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-145">If you want to repeat one value some place in the string, you can reuse that values number.</span></span>

<span data-ttu-id="d2ea7-146">При таком подходе чем сложнее строка, тем больше значений будет получено.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-146">The more complicated the string gets, the more value you get out of this approach.</span></span>

### <a name="format-values-as-arrays"></a><span data-ttu-id="d2ea7-147">Форматирование значений в виде массивов</span><span class="sxs-lookup"><span data-stu-id="d2ea7-147">Format values as arrays</span></span>

<span data-ttu-id="d2ea7-148">Если строка форматирования слишком длинная, можно сначала поместить значения в массив.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-148">If your format line gets too long, you can place your values into an array first.</span></span>

```powershell
$values = @(
    "Kevin"
    "Marquette"
)
'Hello, {0} {1}.' -f $values
```

<span data-ttu-id="d2ea7-149">Это не сплаттинг, поскольку я передаю весь массив, но идея аналогична.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-149">This is not splatting because I'm passing the whole array in, but the idea is similar.</span></span>

## <a name="advanced-formatting"></a><span data-ttu-id="d2ea7-150">Расширенное форматирование</span><span class="sxs-lookup"><span data-stu-id="d2ea7-150">Advanced formatting</span></span>

<span data-ttu-id="d2ea7-151">Я намеренно использовал для вызова .NET, так как для этой платформы уже хорошо [задокументировано][] множество вариантов форматирования.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-151">I intentionally called these out as coming from .NET because there are lots of formatting options already well [documented][] on it.</span></span> <span data-ttu-id="d2ea7-152">Для различных типов данных предусмотрены встроенные возможности форматирования.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-152">There are built in ways to format various data types.</span></span>

```powershell
"{0:yyyyMMdd}" -f (Get-Date)
"Population {0:N0}" -f  8175133
```

<span data-ttu-id="d2ea7-153">Рассматривать я их не буду, лишь упомяну, что это очень эффективный механизм форматирования, который вы можете использовать при необходимости.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-153">I'm not going to go into them but I just wanted to let you know that this is a very powerful formatting engine if you need it.</span></span>

## <a name="joining-strings"></a><span data-ttu-id="d2ea7-154">Объединение строк</span><span class="sxs-lookup"><span data-stu-id="d2ea7-154">Joining strings</span></span>

<span data-ttu-id="d2ea7-155">Иногда требуется сцепить список значений вместе.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-155">Sometimes you actually do want to concatenate a list of values together.</span></span> <span data-ttu-id="d2ea7-156">Это можно сделать с помощью оператора `-join`.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-156">There's a `-join` operator that can do that for you.</span></span> <span data-ttu-id="d2ea7-157">Он даже позволяет указать символ для объединения строк.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-157">It even lets you specify a character to join between the strings.</span></span>

```powershell
$servers = @(
    'server1'
    'server2'
    'server3'
)

$servers  -join ','
```

<span data-ttu-id="d2ea7-158">Если с помощью `-join` необходимо объединить несколько строк без разделителя, необходимо указать пустую строку `''`.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-158">If you want to `-join` some strings without a separator, you need to specify an empty string `''`.</span></span>
<span data-ttu-id="d2ea7-159">Но если нужно сделать только это, существует более быстрый вариант.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-159">But if that is all you need, there's a faster option.</span></span>

```powershell
[string]::Concat('server1','server2','server3')
[string]::Concat($servers)
```

<span data-ttu-id="d2ea7-160">Также стоит отметить, что с помощью оператора `-split` строки можно разделить.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-160">It's also worth pointing out that you can also `-split` strings too.</span></span>

## <a name="join-path"></a><span data-ttu-id="d2ea7-161">Join-Path</span><span class="sxs-lookup"><span data-stu-id="d2ea7-161">Join-Path</span></span>

<span data-ttu-id="d2ea7-162">Этот командлет часто бывает неудобен, но он отлично подходит для создания пути к файлу.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-162">This is often overlooked but a great cmdlet for building a file path.</span></span>

```powershell
$folder = 'Temp'
Join-Path -Path 'c:\windows' -ChildPath $folder
```

<span data-ttu-id="d2ea7-163">Самое замечательное в нем то, что он правильно обрабатывает обратные косые черты, когда собирает значение воедино.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-163">The great thing about this is it works out the backslashes correctly when it puts the values together.</span></span> <span data-ttu-id="d2ea7-164">Это особенно важно, если вы принимаете значения от пользователей или файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-164">This is especially important if you are taking values from users or config files.</span></span>

<span data-ttu-id="d2ea7-165">Он также прекрасно работает с `Split-Path` и `Test-Path`.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-165">This also goes well with `Split-Path` and `Test-Path`.</span></span> <span data-ttu-id="d2ea7-166">Я также рассказываю о нем в публикации о [чтении и сохранении в файлы][].</span><span class="sxs-lookup"><span data-stu-id="d2ea7-166">I also cover these in my post about [reading and saving to files][].</span></span>

## <a name="strings-are-arrays"></a><span data-ttu-id="d2ea7-167">Строки как массивы</span><span class="sxs-lookup"><span data-stu-id="d2ea7-167">Strings are arrays</span></span>

<span data-ttu-id="d2ea7-168">Прежде чем продолжить, я должен упомянуть о добавлении строк.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-168">I do need to mention adding strings here before I go on.</span></span> <span data-ttu-id="d2ea7-169">Помните, что строка представляет собой обычный массив символов.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-169">Remember that a string is just an array of characters.</span></span> <span data-ttu-id="d2ea7-170">При добавлении нескольких строк в одну каждый раз создается новый массив.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-170">When you add multiple strings together, a new array is created each time.</span></span>

<span data-ttu-id="d2ea7-171">Взгляните на этот пример.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-171">Look at this example:</span></span>

```powershell
$message = "Numbers: "
foreach($number in 1..10000)
{
    $message += " $number"
}
```

<span data-ttu-id="d2ea7-172">Он выглядит очень простым, но на самом деле при каждом добавлении строки в `$message` создается полностью новая строка.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-172">It looks very basic but what you don't see is that each time a string is added to `$message` that a whole new string is created.</span></span> <span data-ttu-id="d2ea7-173">Для этого выделяется память, в нее копируются данные, а старая строка удаляется.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-173">Memory gets allocated, data gets copied and the old one is discarded.</span></span>
<span data-ttu-id="d2ea7-174">Ничего особенного, если такая операция выполняется лишь несколько раз, но в случае цикла, подобного этому, это может быть проблемой.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-174">Not a big deal when it's only done a few times, but a loop like this would really expose the issue.</span></span>

### <a name="stringbuilder"></a><span data-ttu-id="d2ea7-175">StringBuilder</span><span class="sxs-lookup"><span data-stu-id="d2ea7-175">StringBuilder</span></span>

<span data-ttu-id="d2ea7-176">Класс StringBuilder также очень часто используется для создания больших строк из множества строк меньшего размера.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-176">StringBuilder is also very popular for building large strings from lots of smaller strings.</span></span> <span data-ttu-id="d2ea7-177">Его популярность связана с тем, что он просто собирает все добавленные в него строки, а затем сцепляет их в конце при извлечении значения.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-177">The reason why is because it just collects all the strings you add to it and only concatenates all of them at the end when you retrieve the value.</span></span>

```powershell
$stringBuilder = New-Object -TypeName "System.Text.StringBuilder"

[void]$stringBuilder.Append("Numbers: ")
foreach($number in 1..10000)
{
    [void]$stringBuilder.Append(" $number")
}
$message = $stringBuilder.ToString()
```

<span data-ttu-id="d2ea7-178">Опять же, именно поэтому я использую .NET.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-178">Again, this is something that I'm reaching out to .NET for.</span></span> <span data-ttu-id="d2ea7-179">Пользуюсь я им нечасто, но знать о его существовании будет не лишним.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-179">I don't use it often anymore but it's good to know it's there.</span></span>

## <a name="delineation-with-braces"></a><span data-ttu-id="d2ea7-180">Разграничение с помощью фигурных скобок</span><span class="sxs-lookup"><span data-stu-id="d2ea7-180">Delineation with braces</span></span>

<span data-ttu-id="d2ea7-181">Этот метод используется для объединения суффикса с другими данными в строке.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-181">This is used for suffix concatenation within the string.</span></span> <span data-ttu-id="d2ea7-182">Иногда у переменной отсутствует четкая граница слова.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-182">Sometimes your variable doesn't have a clean word boundary.</span></span>

```powershell
$test = "Bet"
$tester = "Better"
Write-Host "$test $tester ${test}ter"
```

<span data-ttu-id="d2ea7-183">Благодарю [/u/real_parbold][] за эту идею.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-183">Thank you [/u/real_parbold][] for that one.</span></span>

<span data-ttu-id="d2ea7-184">Вот альтернатива данному подходу.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-184">Here is an alternate to this approach:</span></span>

```powershell
Write-Host "$test $tester $($test)ter"
Write-Host "{0} {1} {0}ter" -f $test, $tester
```

<span data-ttu-id="d2ea7-185">Лично я использую для этого строку форматирования, но знать о такой возможности будет не лишним на тот случай, если вам она где-то встретится.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-185">I personally use format string for this, but this is good to know incase you see it in the wild.</span></span>

## <a name="find-and-replace-tokens"></a><span data-ttu-id="d2ea7-186">Токены для поиска и замены</span><span class="sxs-lookup"><span data-stu-id="d2ea7-186">Find and replace tokens</span></span>

<span data-ttu-id="d2ea7-187">Хотя большая часть этих функций призвана снизить потребность в развертывании собственного решения, их можно применять и в тех случаях, когда необходимо заменить строки в больших файлах шаблонов.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-187">While most of these features limit your need to roll your own solution, there are times where you may have large template files where you want to replace strings inside.</span></span>

<span data-ttu-id="d2ea7-188">Предположим, что вы извлекли шаблон из файла, который содержит большой объем текста.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-188">Let us assume you pulled in a template from a file that has a lot of text.</span></span>

```powershell
$letter = Get-Content -Path TemplateLetter.txt -RAW
$letter = $letter -replace '#FULL_NAME#', 'Kevin Marquette'
```

<span data-ttu-id="d2ea7-189">У вас может быть много токенов для замены.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-189">You may have lots of tokens to replace.</span></span> <span data-ttu-id="d2ea7-190">Хитрость заключается в том, чтобы использовать особый токен, который легко найти и заменить.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-190">The trick is to use a very distinct token that is easy to find and replace.</span></span> <span data-ttu-id="d2ea7-191">Я обычно использую специальный символ на обоих концах, чтобы его было проще отличить.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-191">I tend to use a special character at both ends to help distinguish it.</span></span>

<span data-ttu-id="d2ea7-192">Недавно я обнаружил новый подход для решения этой задачи.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-192">I recently found a new way to approach this.</span></span> <span data-ttu-id="d2ea7-193">Так как это довольно распространенная схема, я не стану вдаваться в дальнейшие подробности в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-193">I decided to leave this section in here because this is a pattern that is commonly used.</span></span>

### <a name="replace-multiple-tokens"></a><span data-ttu-id="d2ea7-194">Замена нескольких токенов</span><span class="sxs-lookup"><span data-stu-id="d2ea7-194">Replace multiple tokens</span></span>

<span data-ttu-id="d2ea7-195">Если у меня есть список токенов, которые нужно заменить, я использую более универсальный подход.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-195">When I have a list of tokens that I need to replace, I take a more generic approach.</span></span> <span data-ttu-id="d2ea7-196">Я помещаю их в хэш-таблицу и перебираю их методом итерации, чтобы выполнить замену.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-196">I would place them in a hashtable and iterate over them to do the replace.</span></span>

```powershell
$tokenList = @{
    Full_Name = 'Kevin Marquette'
    Location = 'Orange County'
    State = 'CA'
}

$letter = Get-Content -Path TemplateLetter.txt -RAW
foreach( $token in $tokenList.GetEnumerator() )
{
    $pattern = '#{0}#' -f $token.key
    $letter = $letter -replace $pattern, $token.Value
}
```

<span data-ttu-id="d2ea7-197">При необходимости эти токены можно загрузить из файла JSON или CSV.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-197">Those tokens could be loaded from JSON or CSV if needed.</span></span>

### <a name="executioncontext-expandstring"></a><span data-ttu-id="d2ea7-198">Метод ExpandString класса ExecutionContext</span><span class="sxs-lookup"><span data-stu-id="d2ea7-198">ExecutionContext ExpandString</span></span>

<span data-ttu-id="d2ea7-199">Существует отличный способ, который заключается в том, чтобы определить строку подстановки с помощью одинарных кавычек, а затем развернуть переменные.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-199">There's a clever way to define a substitution string with single quotes and expand the variables later.</span></span> <span data-ttu-id="d2ea7-200">Взгляните на этот пример.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-200">Look at this example:</span></span>

```powershell
$message = 'Hello, $Name!'
$name = 'Kevin Marquette'
$string = $ExecutionContext.InvokeCommand.ExpandString($message)
```

<span data-ttu-id="d2ea7-201">При вызове `.InvokeCommand.ExpandString` в текущем контексте выполнения для подстановки используются переменные в текущей области.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-201">The call to `.InvokeCommand.ExpandString` on the current execution context uses the variables in the current scope for substitution.</span></span> <span data-ttu-id="d2ea7-202">Ключевым моментом здесь является то, что `$message` можно определить заранее, когда переменные еще даже не существуют.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-202">The key thing here is that the `$message` can be defined very early before the variables even exist.</span></span>

<span data-ttu-id="d2ea7-203">Немного дополнив этот код, можно обеспечить повторное выполнение этой замены для различных значений.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-203">If we expand on that just a little bit, we can perform this substitution over and over wih different values.</span></span>

```powershell
$message = 'Hello, $Name!'
$nameList = 'Mark Kraus','Kevin Marquette','Lee Dailey'
foreach($name in $nameList){
    $ExecutionContext.InvokeCommand.ExpandString($message)
}
```

<span data-ttu-id="d2ea7-204">Развивая эту идею, можно импортировать большой шаблон электронной почты из текстового файла.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-204">To keep going on this idea; you could be importing a large email template from a text file to do this.</span></span> <span data-ttu-id="d2ea7-205">Я благодарю [Марк Краус][] за это [предложение][].</span><span class="sxs-lookup"><span data-stu-id="d2ea7-205">I have to thank [Mark Kraus][] for this [suggestion][].</span></span>

## <a name="whatever-works-the-best-for-you"></a><span data-ttu-id="d2ea7-206">Оптимальный вариант для конкретной ситуации</span><span class="sxs-lookup"><span data-stu-id="d2ea7-206">Whatever works the best for you</span></span>

<span data-ttu-id="d2ea7-207">Мне нравится подход со строками форматирования.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-207">I'm a fan of the format string approach.</span></span> <span data-ttu-id="d2ea7-208">Я применяю его для более сложных строк или при наличии нескольких переменных.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-208">I definitely do this with the more complicated strings or if there are multiple variables.</span></span> <span data-ttu-id="d2ea7-209">Но для коротких строк подойдет любой из описанных методов.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-209">On anything that is very short, I may use any one of these.</span></span>

## <a name="anything-else"></a><span data-ttu-id="d2ea7-210">Другие возможности</span><span class="sxs-lookup"><span data-stu-id="d2ea7-210">Anything else?</span></span>

<span data-ttu-id="d2ea7-211">Я лишь вкратце затронул эту тему.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-211">I covered a lot of ground on this one.</span></span> <span data-ttu-id="d2ea7-212">Я надеюсь, что вы сможете двигаться дальше, узнав для себя что-то новое.</span><span class="sxs-lookup"><span data-stu-id="d2ea7-212">My hope is that you walk away learning something new.</span></span>

<!-- link references -->
[Оригинал]: https://powershellexplained.com/2017-01-13-powershell-variable-substitution-in-strings/
[original version]: https://powershellexplained.com/2017-01-13-powershell-variable-substitution-in-strings/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[Марк Краус]: https://get-powershellblog.blogspot.com/
[Mark Kraus]: https://get-powershellblog.blogspot.com/
[предложение]: https://www.reddit.com/r/PowerShell/comments/5npf8h/kevmar_everything_you_wanted_to_know_about/dcdfia5/
[suggestion]: https://www.reddit.com/r/PowerShell/comments/5npf8h/kevmar_everything_you_wanted_to_know_about/dcdfia5/
[/u/real_parbold]: https://www.reddit.com/r/PowerShell/comments/5npf8h/kevmar_everything_you_wanted_to_know_about/dcdfm6p/
[чтении и сохранении в файлы]: https://powershellexplained.com/2017-03-18-Powershell-reading-and-saving-data-to-files/
[reading and saving to files]: https://powershellexplained.com/2017-03-18-Powershell-reading-and-saving-data-to-files/
[задокументировано]: /dotnet/api/system.string.format#overloads
[documented]: /dotnet/api/system.string.format#overloads
