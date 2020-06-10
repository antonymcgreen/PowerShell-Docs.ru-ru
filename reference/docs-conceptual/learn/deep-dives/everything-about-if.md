---
title: Все, что вы хотели знать об операторе IF
description: Как и многие другие языки, PowerShell содержит операторы для условного исполнения кода в сценариях.
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 6ffb70af694e80430d31991045b9fadc1a2cc3f0
ms.sourcegitcommit: ed4a895d672334c7b02fb7ef6e950dbc2ba4a197
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2020
ms.locfileid: "84149527"
---
# <a name="everything-you-wanted-to-know-about-the-if-statement"></a><span data-ttu-id="09842-103">Все, что вы хотели знать об операторе IF</span><span class="sxs-lookup"><span data-stu-id="09842-103">Everything you wanted to know about the IF statement</span></span>

<span data-ttu-id="09842-104">Как и многие другие языки, PowerShell содержит операторы для условного исполнения кода в сценариях.</span><span class="sxs-lookup"><span data-stu-id="09842-104">Like many other languages, PowerShell has statements for conditionally executing code in your scripts.</span></span> <span data-ttu-id="09842-105">Одним из таких операторов является оператор [if][].</span><span class="sxs-lookup"><span data-stu-id="09842-105">One of those statements is the [if][] statement.</span></span> <span data-ttu-id="09842-106">Сегодня мы более подробно поговорим об одной из важнейших команд в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09842-106">Today we will take a deep dive into one of the most fundamental commands in PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="09842-107">[Оригинал][] этой статьи впервые был опубликован в блоге автора [@KevinMarquette][].</span><span class="sxs-lookup"><span data-stu-id="09842-107">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="09842-108">Группа разработчиков PowerShell благодарит Кевина за то, что он поделился с нами этими материалами.</span><span class="sxs-lookup"><span data-stu-id="09842-108">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="09842-109">Ознакомьтесь с его блогом на веб-сайте [PowerShellExplained.com][].</span><span class="sxs-lookup"><span data-stu-id="09842-109">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="conditional-execution"></a><span data-ttu-id="09842-110">Условное выполнение</span><span class="sxs-lookup"><span data-stu-id="09842-110">Conditional execution</span></span>

<span data-ttu-id="09842-111">В сценариях часто требуется принимать решения и применять различные логики в зависимости от этих решений.</span><span class="sxs-lookup"><span data-stu-id="09842-111">Your scripts often need to make decisions and perform different logic based on those decisions.</span></span>
<span data-ttu-id="09842-112">Именно это имеется в виду под условным выполнением.</span><span class="sxs-lookup"><span data-stu-id="09842-112">This is what I mean by conditional execution.</span></span> <span data-ttu-id="09842-113">У вас есть один оператор или значение для вычисления, а затем вы выполняете другой раздел кода на основе этого вычисления.</span><span class="sxs-lookup"><span data-stu-id="09842-113">You have one statement or value to evaluate, then execute a different section of code based on that evaluation.</span></span> <span data-ttu-id="09842-114">Именно это и делает оператор `if`.</span><span class="sxs-lookup"><span data-stu-id="09842-114">This is exactly what the `if` statement does.</span></span>

## <a name="the-if-statement"></a><span data-ttu-id="09842-115">Оператор if</span><span class="sxs-lookup"><span data-stu-id="09842-115">The if statement</span></span>

<span data-ttu-id="09842-116">Ниже приведен простой пример оператора `if`.</span><span class="sxs-lookup"><span data-stu-id="09842-116">Here is a basic example of the `if` statement:</span></span>

```powershell
$condition = $true
if ( $condition )
{
    Write-Output "The condition was true"
}
```

<span data-ttu-id="09842-117">Первое, что делает оператор `if`, — вычисляет выражение в круглых скобках.</span><span class="sxs-lookup"><span data-stu-id="09842-117">The first thing the `if` statement does is evaluate the expression in parentheses.</span></span> <span data-ttu-id="09842-118">Если он имеет значение `$true`, то он выполняет `scriptblock` в фигурных скобках.</span><span class="sxs-lookup"><span data-stu-id="09842-118">If it evaluates to `$true`, then it executes the `scriptblock` in the braces.</span></span> <span data-ttu-id="09842-119">Если значение равнялось `$false`, то этот блок сценария был бы пропущен.</span><span class="sxs-lookup"><span data-stu-id="09842-119">If the value was `$false`, then it would skip over that scriptblock.</span></span>

<span data-ttu-id="09842-120">В предыдущем примере оператор `if` только что вычислил переменную `$condition`.</span><span class="sxs-lookup"><span data-stu-id="09842-120">In the previous example, the `if` statement was just evaluating the `$condition` variable.</span></span> <span data-ttu-id="09842-121">Он был равен `$true` и выполнил бы команду `Write-Output` в блоке сценария.</span><span class="sxs-lookup"><span data-stu-id="09842-121">It was `$true` and would have executed the `Write-Output` command inside the scriptblock.</span></span>

<span data-ttu-id="09842-122">В некоторых языках можно поместить одну строку кода после оператора `if`, чтобы выполнить ее.</span><span class="sxs-lookup"><span data-stu-id="09842-122">In some languages, you can place a single line of code after the `if` statement and it gets executed.</span></span> <span data-ttu-id="09842-123">В PowerShell все не так.</span><span class="sxs-lookup"><span data-stu-id="09842-123">That isn't the case in PowerShell.</span></span> <span data-ttu-id="09842-124">Чтобы все работало правильно, необходимо указать полный `scriptblock` с фигурными скобками.</span><span class="sxs-lookup"><span data-stu-id="09842-124">You must provide a full `scriptblock` with braces for it to work correctly.</span></span>

## <a name="comparison-operators"></a><span data-ttu-id="09842-125">Операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="09842-125">Comparison operators</span></span>

<span data-ttu-id="09842-126">Оператор `if` чаще всего используется для сравнения двух элементов.</span><span class="sxs-lookup"><span data-stu-id="09842-126">The most common use of the `if` statement for is comparing two items with each other.</span></span> <span data-ttu-id="09842-127">PowerShell предлагает специальные операторы для различных сценариев сравнения.</span><span class="sxs-lookup"><span data-stu-id="09842-127">PowerShell has special operators for different comparison scenarios.</span></span> <span data-ttu-id="09842-128">При использовании оператора сравнения значение в левой части сравнивается со значением в правой части.</span><span class="sxs-lookup"><span data-stu-id="09842-128">When you use a comparison operator, the value on the left-hand side is compared to the value on the right-hand side.</span></span>

### <a name="-eq-for-equality"></a><span data-ttu-id="09842-129">-eq для "равно"</span><span class="sxs-lookup"><span data-stu-id="09842-129">-eq for equality</span></span>

<span data-ttu-id="09842-130">`-eq` проверяет равенство двух значений, чтобы убедиться в том, что они равны друг другу.</span><span class="sxs-lookup"><span data-stu-id="09842-130">The `-eq` does an equality check between two values to make sure they're equal to each other.</span></span>

```powershell
$value = Get-MysteryValue
if ( 5 -eq $value )
{
    # do something
}
```

<span data-ttu-id="09842-131">В этом примере я беру известное значение `5` и сравниваю его с моим `$value`, чтобы понять, совпадают ли они.</span><span class="sxs-lookup"><span data-stu-id="09842-131">In this example, I'm taking a known value of `5` and comparing it to my `$value` to see if they match.</span></span>

<span data-ttu-id="09842-132">Один из возможных вариантов использования — проверка состояния значения до того, как выполнено действие с ним.</span><span class="sxs-lookup"><span data-stu-id="09842-132">One possible use case is to check the status of a value before you take an action on it.</span></span> <span data-ttu-id="09842-133">Можно получить службу и убедиться в том, что до вызова `Restart-Service` она имела состояние running.</span><span class="sxs-lookup"><span data-stu-id="09842-133">You could get a service and check that the status was running before you called `Restart-Service` on it.</span></span>

<span data-ttu-id="09842-134">В других языках, таких как C#, обычно используется `==` для проверки на равенство (например, `5 == $value`), но в PowerShell это невозможно.</span><span class="sxs-lookup"><span data-stu-id="09842-134">It's common in other languages like C# to use `==` for equality (ex: `5 == $value`) but that doesn't work with PowerShell.</span></span> <span data-ttu-id="09842-135">Еще одна распространенная ошибка, которую делают пользователи, — использование знака равенства (например, `5 = $value`), который зарезервирован для присвоения значений переменным.</span><span class="sxs-lookup"><span data-stu-id="09842-135">Another common mistake that people make is to use the equals sign (ex: `5 = $value`) that is reserved for assigning values to variables.</span></span> <span data-ttu-id="09842-136">Если поместить известное значение слева, вероятность ошибки повышается.</span><span class="sxs-lookup"><span data-stu-id="09842-136">By placing your known value on the left, it makes that mistaken more awkward to make.</span></span>

<span data-ttu-id="09842-137">Для этого оператора (как и для других) доступно несколько вариантов.</span><span class="sxs-lookup"><span data-stu-id="09842-137">This operator (and others) has a few variations.</span></span>

- <span data-ttu-id="09842-138">`-eq` без учета регистра, равенство</span><span class="sxs-lookup"><span data-stu-id="09842-138">`-eq` case-insensitive equality</span></span>
- <span data-ttu-id="09842-139">`-ieq` без учета регистра, равенство</span><span class="sxs-lookup"><span data-stu-id="09842-139">`-ieq` case-insensitive equality</span></span>
- <span data-ttu-id="09842-140">`-ceq` с учетом регистра, равенство</span><span class="sxs-lookup"><span data-stu-id="09842-140">`-ceq` case-sensitive equality</span></span>

### <a name="-ne-not-equal"></a><span data-ttu-id="09842-141">-ne "не равно"</span><span class="sxs-lookup"><span data-stu-id="09842-141">-ne not equal</span></span>

<span data-ttu-id="09842-142">Для многих операторов предусмотрен связанный оператор, который выполняет проверку на противоположный результат.</span><span class="sxs-lookup"><span data-stu-id="09842-142">Many operators have a related operator that is checking for the opposite result.</span></span> <span data-ttu-id="09842-143">`-ne` проверяет, чтобы значения не были равны друг другу.</span><span class="sxs-lookup"><span data-stu-id="09842-143">`-ne` verifies that the values don't equal each other.</span></span>

```powershell
if ( 5 -ne $value )
{
    # do something
}
```

<span data-ttu-id="09842-144">Этот параметр позволяет убедиться в том, что действие выполняется только в том случае, если значение не равно `5`.</span><span class="sxs-lookup"><span data-stu-id="09842-144">Use this to make sure that the action only executes if the value isn't `5`.</span></span> <span data-ttu-id="09842-145">В качестве одного из полезных примеров его использования можно проверить, имеет ли служба состояние running до того, как пытаться запустить ее.</span><span class="sxs-lookup"><span data-stu-id="09842-145">A good use-cases where would be to check if a service was in the running state before you try to start it.</span></span>

<span data-ttu-id="09842-146">**Варианты:**</span><span class="sxs-lookup"><span data-stu-id="09842-146">**Variations:**</span></span>

- <span data-ttu-id="09842-147">`-ne` без учета регистра, не равно</span><span class="sxs-lookup"><span data-stu-id="09842-147">`-ne` case-insensitive not equal</span></span>
- <span data-ttu-id="09842-148">`-ine` без учета регистра, не равно</span><span class="sxs-lookup"><span data-stu-id="09842-148">`-ine` case-insensitive not equal</span></span>
- <span data-ttu-id="09842-149">`-cne` с учетом регистра, не равно</span><span class="sxs-lookup"><span data-stu-id="09842-149">`-cne` case-sensitive not equal</span></span>

<span data-ttu-id="09842-150">Это инвертированные варианты `-eq`.</span><span class="sxs-lookup"><span data-stu-id="09842-150">These are inverse variations of `-eq`.</span></span> <span data-ttu-id="09842-151">Эти типы будут сгруппированы при перечислении вариантов для других операторов.</span><span class="sxs-lookup"><span data-stu-id="09842-151">I'll group these types together when I list variations for other operators.</span></span>

### <a name="-gt--ge--lt--le-for-greater-than-or-less-than"></a><span data-ttu-id="09842-152">-gt -ge -lt -le для "больше, чем" или "меньше, чем"</span><span class="sxs-lookup"><span data-stu-id="09842-152">-gt -ge -lt -le for greater than or less than</span></span>

<span data-ttu-id="09842-153">Эти операторы позволяют убедиться в том, что значение больше или меньше другого значения.</span><span class="sxs-lookup"><span data-stu-id="09842-153">These operators are used when checking to see if a value is larger or smaller than another value.</span></span>
<span data-ttu-id="09842-154">`-gt -ge -lt -le` означают GreaterThan, GreaterThanOrEqual, LessThan и LessThanOrEqual.</span><span class="sxs-lookup"><span data-stu-id="09842-154">The `-gt -ge -lt -le` stand for GreaterThan, GreaterThanOrEqual, LessThan, and LessThanOrEqual.</span></span>

```powershell
if ( $value -gt 5 )
{
    # do something
}
```

<span data-ttu-id="09842-155">**Варианты:**</span><span class="sxs-lookup"><span data-stu-id="09842-155">**Variations:**</span></span>

- <span data-ttu-id="09842-156">`-gt` "больше, чем"</span><span class="sxs-lookup"><span data-stu-id="09842-156">`-gt` greater than</span></span>
- <span data-ttu-id="09842-157">`-igt` "больше, чем", без учета регистра</span><span class="sxs-lookup"><span data-stu-id="09842-157">`-igt` greater than, case-insensitive</span></span>
- <span data-ttu-id="09842-158">`-cgt` "больше, чем", с учетом регистра</span><span class="sxs-lookup"><span data-stu-id="09842-158">`-cgt` greater than, case-sensitive</span></span>
- <span data-ttu-id="09842-159">`-ge` "больше, чем" или "равно"</span><span class="sxs-lookup"><span data-stu-id="09842-159">`-ge` greater than or equal</span></span>
- <span data-ttu-id="09842-160">`-ige` "больше, чем" или "равно", без учета регистра</span><span class="sxs-lookup"><span data-stu-id="09842-160">`-ige` greater than or equal, case-insensitive</span></span>
- <span data-ttu-id="09842-161">`-cge` "больше, чем" или "равно", с учетом регистра</span><span class="sxs-lookup"><span data-stu-id="09842-161">`-cge` greater than or equal, case-sensitive</span></span>
- <span data-ttu-id="09842-162">`-lt` "меньше, чем"</span><span class="sxs-lookup"><span data-stu-id="09842-162">`-lt` less than</span></span>
- <span data-ttu-id="09842-163">`-ilt` "меньше, чем", без учета регистра</span><span class="sxs-lookup"><span data-stu-id="09842-163">`-ilt` less than, case-insensitive</span></span>
- <span data-ttu-id="09842-164">`-clt` "меньше, чем", с учетом регистра</span><span class="sxs-lookup"><span data-stu-id="09842-164">`-clt` less than, case-sensitive</span></span>
- <span data-ttu-id="09842-165">`-le` "меньше, чем" или "равно"</span><span class="sxs-lookup"><span data-stu-id="09842-165">`-le` less than or equal</span></span>
- <span data-ttu-id="09842-166">`-ile` "меньше, чем" или "равно", без учета регистра</span><span class="sxs-lookup"><span data-stu-id="09842-166">`-ile` less than or equal, case-insensitive</span></span>
- <span data-ttu-id="09842-167">`-cle` "меньше, чем" или "равно", с учетом регистра</span><span class="sxs-lookup"><span data-stu-id="09842-167">`-cle` less than or equal, case-sensitive</span></span>

<span data-ttu-id="09842-168">Я не знаю, зачем для этих операторов использовать параметры с учетом регистра или без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="09842-168">I don't know why you would use case-sensitive and insensitive options for these operators.</span></span>

### <a name="-like-wildcard-matches"></a><span data-ttu-id="09842-169">Сопоставление с использованием подстановочного знака -like</span><span class="sxs-lookup"><span data-stu-id="09842-169">-like wildcard matches</span></span>

<span data-ttu-id="09842-170">PowerShell использует собственный синтаксис сопоставления шаблонов на основе подстановочных знаков, и его можно сочетать с оператором `-like`.</span><span class="sxs-lookup"><span data-stu-id="09842-170">PowerShell has its own wildcard-based pattern matching syntax and you can use it with the `-like` operator.</span></span> <span data-ttu-id="09842-171">Шаблоны с подстановочными знаками довольно просты.</span><span class="sxs-lookup"><span data-stu-id="09842-171">These wildcard patterns are fairly basic.</span></span>

- <span data-ttu-id="09842-172">`?` сопоставляет любой отдельный символ</span><span class="sxs-lookup"><span data-stu-id="09842-172">`?` matches any single character</span></span>
- <span data-ttu-id="09842-173">`*` сопоставляет любое число символов</span><span class="sxs-lookup"><span data-stu-id="09842-173">`*` matches any number of characters</span></span>

```powershell
$value = 'S-ATX-SQL01'
if ( $value -like 'S-*-SQL??')
{
    # do something
}
```

<span data-ttu-id="09842-174">Важно отметить, что шаблон сопоставляет всю строку.</span><span class="sxs-lookup"><span data-stu-id="09842-174">It's important to point out that the pattern matches the whole string.</span></span> <span data-ttu-id="09842-175">Если необходимо сопоставить данные в середине строки, поместите `*` на обоих концах строки.</span><span class="sxs-lookup"><span data-stu-id="09842-175">If you need to match something in the middle of the string, you need to place the `*` on both ends of the string.</span></span>

```powershell
$value = 'S-ATX-SQL02'
if ( $value -like '*SQL*')
{
    # do something
}
```

<span data-ttu-id="09842-176">**Варианты:**</span><span class="sxs-lookup"><span data-stu-id="09842-176">**Variations:**</span></span>

- <span data-ttu-id="09842-177">`-like` без учета регистра, подстановочный знак</span><span class="sxs-lookup"><span data-stu-id="09842-177">`-like` case-insensitive wildcard</span></span>
- <span data-ttu-id="09842-178">`-ilike` без учета регистра, подстановочный знак</span><span class="sxs-lookup"><span data-stu-id="09842-178">`-ilike` case-insensitive wildcard</span></span>
- <span data-ttu-id="09842-179">`-clike` с учетом регистра, подстановочный знак</span><span class="sxs-lookup"><span data-stu-id="09842-179">`-clike` case-sensitive wildcard</span></span>
- <span data-ttu-id="09842-180">`-notlike` без учета регистра, подстановочный знак, не сопоставлен</span><span class="sxs-lookup"><span data-stu-id="09842-180">`-notlike` case-insensitive wildcard not matched</span></span>
- <span data-ttu-id="09842-181">`-inotlike` без учета регистра, подстановочный знак, не сопоставлен</span><span class="sxs-lookup"><span data-stu-id="09842-181">`-inotlike` case-insensitive wildcard not matched</span></span>
- <span data-ttu-id="09842-182">`-cnotlike` с учетом регистра, подстановочный знак, не сопоставлен</span><span class="sxs-lookup"><span data-stu-id="09842-182">`-cnotlike` case-sensitive wildcard not matched</span></span>

### <a name="-match-regular-expression"></a><span data-ttu-id="09842-183">Регулярное выражение -match</span><span class="sxs-lookup"><span data-stu-id="09842-183">-match regular expression</span></span>

<span data-ttu-id="09842-184">Оператор `-match` позволяет проверить строку на соответствие регулярному выражению.</span><span class="sxs-lookup"><span data-stu-id="09842-184">The `-match` operator allows you to check a string for a regular-expression-based match.</span></span> <span data-ttu-id="09842-185">Используйте этот параметр, если шаблоны с подстановочными знаками не обеспечивают достаточной гибкости.</span><span class="sxs-lookup"><span data-stu-id="09842-185">Use this when the wildcard patterns aren't flexible enough for you.</span></span>

```powershell
$value = 'S-ATX-SQL01'
if ( $value -match 'S-\w\w\w-SQL\d\d')
{
    # do something
}
```

<span data-ttu-id="09842-186">Шаблон регулярного выражения по умолчанию соответствует данным в любом месте строки.</span><span class="sxs-lookup"><span data-stu-id="09842-186">A regex pattern matches anywhere in the string by default.</span></span> <span data-ttu-id="09842-187">Поэтому можно указать подстроку, которую необходимо сопоставить следующим образом:</span><span class="sxs-lookup"><span data-stu-id="09842-187">So you can specify a substring that you want matched like this:</span></span>

```powershell
$value = 'S-ATX-SQL01'
if ( $value -match 'SQL')
{
    # do something
}
```

<span data-ttu-id="09842-188">Регулярные выражения представляют собой сложный язык сами по себе и достойны изучения.</span><span class="sxs-lookup"><span data-stu-id="09842-188">Regex is a complex language of its own and worth looking into.</span></span> <span data-ttu-id="09842-189">Я подробнее расскажу о `-match` и [множестве способов использования регулярных выражений][] в другой статье.</span><span class="sxs-lookup"><span data-stu-id="09842-189">I talk more about `-match` and [the many ways to use regex][] in another article.</span></span>

<span data-ttu-id="09842-190">**Варианты:**</span><span class="sxs-lookup"><span data-stu-id="09842-190">**Variations:**</span></span>

- <span data-ttu-id="09842-191">`-match` без учета регистра, регулярное выражение</span><span class="sxs-lookup"><span data-stu-id="09842-191">`-match` case-insensitive regex</span></span>
- <span data-ttu-id="09842-192">`-imatch` без учета регистра, регулярное выражение</span><span class="sxs-lookup"><span data-stu-id="09842-192">`-imatch` case-insensitive regex</span></span>
- <span data-ttu-id="09842-193">`-cmatch` с учетом регистра, регулярное выражение</span><span class="sxs-lookup"><span data-stu-id="09842-193">`-cmatch` case-sensitive regex</span></span>
- <span data-ttu-id="09842-194">`-notmatch` без учета регистра, регулярное выражение, не сопоставлено</span><span class="sxs-lookup"><span data-stu-id="09842-194">`-notmatch` case-insensitive regex not matched</span></span>
- <span data-ttu-id="09842-195">`-inotmatch` без учета регистра, регулярное выражение, не сопоставлено</span><span class="sxs-lookup"><span data-stu-id="09842-195">`-inotmatch` case-insensitive regex not matched</span></span>
- <span data-ttu-id="09842-196">`-cnotmatch` с учетом регистра, регулярное выражение, не сопоставлено</span><span class="sxs-lookup"><span data-stu-id="09842-196">`-cnotmatch` case-sensitive regex not matched</span></span>

### <a name="-is-of-type"></a><span data-ttu-id="09842-197">-is относится к типу</span><span class="sxs-lookup"><span data-stu-id="09842-197">-is of type</span></span>

<span data-ttu-id="09842-198">Тип значения можно проверить с помощью оператора `-is`.</span><span class="sxs-lookup"><span data-stu-id="09842-198">You can check a value's type with the `-is` operator.</span></span>

```powershell
if ( $value -is [string] )
{
    # do something
}
```

<span data-ttu-id="09842-199">Эту возможность можно использовать, если вы работаете с классами или принимаете различные объекты по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="09842-199">You may use this if you're working with classes or accepting various objects over the pipeline.</span></span> <span data-ttu-id="09842-200">В качестве входных данных может быть задана служба или имя службы.</span><span class="sxs-lookup"><span data-stu-id="09842-200">You could have either a service or a service name as your input.</span></span> <span data-ttu-id="09842-201">Затем проверьте, есть ли у вас служба, и получите службу, используя только ее имя.</span><span class="sxs-lookup"><span data-stu-id="09842-201">Then check to see if you have a service and fetch the service if you only have the name.</span></span>

```powershell
if ( $Service -isnot [System.ServiceProcess.ServiceController] )
{
    $Service = Get-Service -Name $Service
}
```

<span data-ttu-id="09842-202">**Варианты:**</span><span class="sxs-lookup"><span data-stu-id="09842-202">**Variations:**</span></span>

- <span data-ttu-id="09842-203">`-is` относится к типу</span><span class="sxs-lookup"><span data-stu-id="09842-203">`-is` of type</span></span>
- <span data-ttu-id="09842-204">`-isnot` не относится к типу</span><span class="sxs-lookup"><span data-stu-id="09842-204">`-isnot` not of type</span></span>

## <a name="collection-operators"></a><span data-ttu-id="09842-205">Операторы коллекции</span><span class="sxs-lookup"><span data-stu-id="09842-205">Collection operators</span></span>

<span data-ttu-id="09842-206">При использовании предыдущих операторов с одним значением результатом является `$true` или `$false`.</span><span class="sxs-lookup"><span data-stu-id="09842-206">When you use the previous operators with a single value, the result is `$true` or `$false`.</span></span> <span data-ttu-id="09842-207">При работе с коллекцией обработка выполняется несколько другим способом.</span><span class="sxs-lookup"><span data-stu-id="09842-207">This is handled slightly differently when working with a collection.</span></span> <span data-ttu-id="09842-208">Каждый элемент в коллекции вычисляется, и оператор возвращает каждое значение, результатом которого является `$true`.</span><span class="sxs-lookup"><span data-stu-id="09842-208">Each item in the collection gets evaluated and the operator returns every value that evaluates to `$true`.</span></span>

```powershell
PS> 1,2,3,4 -eq 3
3
```

<span data-ttu-id="09842-209">Эта операция по-прежнему работает корректно в операторе `if`.</span><span class="sxs-lookup"><span data-stu-id="09842-209">This still works correctly in a `if` statement.</span></span> <span data-ttu-id="09842-210">Поэтому оператор возвращает значение, и тогда вся инструкция равна `$true`.</span><span class="sxs-lookup"><span data-stu-id="09842-210">So a value is returned by your operator, then the whole statement is `$true`.</span></span>

```powershell
$array = 1..6
if ( $array -gt 3 )
{
    # do something
}
```

<span data-ttu-id="09842-211">Здесь есть одна небольшая скрытая трудность, на которую нужно обратить внимание. При использовании оператора `-ne` таким образом легко по ошибке просмотреть логику в обратном направлении.</span><span class="sxs-lookup"><span data-stu-id="09842-211">There's one small trap hiding in the details here that I need to point out. When using the `-ne` operator this way, it's easy to mistakenly look at the logic backwards.</span></span> <span data-ttu-id="09842-212">Использование `-ne` с коллекцией возвращает `$true`, если какой-либо элемент в коллекции не совпадает с имеющимся значением.</span><span class="sxs-lookup"><span data-stu-id="09842-212">Using `-ne` with a collection returns `$true` if any item in the collection doesn't match your value.</span></span>

```powershell
PS> 1,2,3 -ne 4
1
2
3
```

<span data-ttu-id="09842-213">Это может показаться разумным, но у нас есть операторы `-contains` и `-in`, которые более эффективно справятся с этой задачей.</span><span class="sxs-lookup"><span data-stu-id="09842-213">This may look like a clever trick, but we have operators `-contains` and `-in` that handle this more efficiently.</span></span> <span data-ttu-id="09842-214">При этом `-notcontains` выполняет то, что от него ожидается.</span><span class="sxs-lookup"><span data-stu-id="09842-214">And `-notcontains` does what you expect.</span></span>

### <a name="-contains"></a><span data-ttu-id="09842-215">-contains</span><span class="sxs-lookup"><span data-stu-id="09842-215">-contains</span></span>

<span data-ttu-id="09842-216">Оператор `-contains` проверяет коллекцию на наличие вашего значения.</span><span class="sxs-lookup"><span data-stu-id="09842-216">The `-contains` operator checks the collection for your value.</span></span> <span data-ttu-id="09842-217">После обнаружения совпадения возвращается значение `$true`.</span><span class="sxs-lookup"><span data-stu-id="09842-217">As soon as it finds a match, it returns `$true`.</span></span>

```powershell
$array = 1..6
if ( $array -contains 3 )
{
    # do something
}
```

<span data-ttu-id="09842-218">Это самый удобный способ узнать, содержит ли коллекция ваше значение.</span><span class="sxs-lookup"><span data-stu-id="09842-218">This is the preferred way to see if a collection contains your value.</span></span> <span data-ttu-id="09842-219">При использовании `Where-Object` (или `-eq`) каждый раз выполняется обход всего списка, и работа значительно замедляется.</span><span class="sxs-lookup"><span data-stu-id="09842-219">Using `Where-Object` (or `-eq`) walks the entire list every time and is significantly slower.</span></span>

<span data-ttu-id="09842-220">**Варианты:**</span><span class="sxs-lookup"><span data-stu-id="09842-220">**Variations:**</span></span>

- <span data-ttu-id="09842-221">`-contains` без учета регистра, совпадение</span><span class="sxs-lookup"><span data-stu-id="09842-221">`-contains` case-insensitive match</span></span>
- <span data-ttu-id="09842-222">`-icontains` без учета регистра, совпадение</span><span class="sxs-lookup"><span data-stu-id="09842-222">`-icontains` case-insensitive match</span></span>
- <span data-ttu-id="09842-223">`-ccontains` с учетом регистра, совпадение</span><span class="sxs-lookup"><span data-stu-id="09842-223">`-ccontains` case-sensitive match</span></span>
- <span data-ttu-id="09842-224">`-notcontains` без учета регистра, не сопоставлено</span><span class="sxs-lookup"><span data-stu-id="09842-224">`-notcontains` case-insensitive not matched</span></span>
- <span data-ttu-id="09842-225">`-inotcontains` без учета регистра, не сопоставлено</span><span class="sxs-lookup"><span data-stu-id="09842-225">`-inotcontains` case-insensitive not matched</span></span>
- <span data-ttu-id="09842-226">`-cnotcontains` с учетом регистра, не сопоставлено</span><span class="sxs-lookup"><span data-stu-id="09842-226">`-cnotcontains` case-sensitive not matched</span></span>

### <a name="-in"></a><span data-ttu-id="09842-227">-in</span><span class="sxs-lookup"><span data-stu-id="09842-227">-in</span></span>

<span data-ttu-id="09842-228">Оператор `-in` похож на оператор `-contains` за исключением того, что коллекция находится в правой части.</span><span class="sxs-lookup"><span data-stu-id="09842-228">The `-in` operator is just like the `-contains` operator except the collection is on the right-hand side.</span></span>

```powershell
$array = 1..6
if ( 3 -in $array )
{
    # do something
}
```

<span data-ttu-id="09842-229">**Варианты:**</span><span class="sxs-lookup"><span data-stu-id="09842-229">**Variations:**</span></span>

- <span data-ttu-id="09842-230">`-in` без учета регистра, совпадение</span><span class="sxs-lookup"><span data-stu-id="09842-230">`-in` case-insensitive match</span></span>
- <span data-ttu-id="09842-231">`-iin` без учета регистра, совпадение</span><span class="sxs-lookup"><span data-stu-id="09842-231">`-iin` case-insensitive match</span></span>
- <span data-ttu-id="09842-232">`-cin` с учетом регистра, совпадение</span><span class="sxs-lookup"><span data-stu-id="09842-232">`-cin` case-sensitive match</span></span>
- <span data-ttu-id="09842-233">`-notin` без учета регистра, не сопоставлено</span><span class="sxs-lookup"><span data-stu-id="09842-233">`-notin` case-insensitive not matched</span></span>
- <span data-ttu-id="09842-234">`-inotin` без учета регистра, не сопоставлено</span><span class="sxs-lookup"><span data-stu-id="09842-234">`-inotin` case-insensitive not matched</span></span>
- <span data-ttu-id="09842-235">`-cnotin` с учетом регистра, не сопоставлено</span><span class="sxs-lookup"><span data-stu-id="09842-235">`-cnotin` case-sensitive not matched</span></span>

## <a name="logical-operators"></a><span data-ttu-id="09842-236">Логические операторы</span><span class="sxs-lookup"><span data-stu-id="09842-236">Logical operators</span></span>

<span data-ttu-id="09842-237">Логические операторы используются для инверсии или объединения других выражений.</span><span class="sxs-lookup"><span data-stu-id="09842-237">Logical operators are used to invert or combine other expressions.</span></span>

### <a name="-not"></a><span data-ttu-id="09842-238">-not</span><span class="sxs-lookup"><span data-stu-id="09842-238">-not</span></span>

<span data-ttu-id="09842-239">Оператор `-not` инвертирует выражение из `$false` в `$true` или из `$true` в `$false`.</span><span class="sxs-lookup"><span data-stu-id="09842-239">The `-not` operator flips an expression from `$false` to `$true` or from `$true` to `$false`.</span></span> <span data-ttu-id="09842-240">Ниже приведен пример, в котором требуется выполнить действие, когда `Test-Path` равно `$false`.</span><span class="sxs-lookup"><span data-stu-id="09842-240">Here is an example where we want to perform an action when `Test-Path` is `$false`.</span></span>

```powershell
if ( -not ( Test-Path -Path $path ) )
```

<span data-ttu-id="09842-241">Большинство операторов, о которых мы говорили, используют вариант, в котором использование оператора `-not` не требуется.</span><span class="sxs-lookup"><span data-stu-id="09842-241">Most of the operators we talked about do have a variation where you do not need to use the `-not` operator.</span></span> <span data-ttu-id="09842-242">Однако в отдельных случаях это все-таки полезно.</span><span class="sxs-lookup"><span data-stu-id="09842-242">But there are still times it is useful.</span></span>

### <a name="-operator"></a><span data-ttu-id="09842-243">!</span><span class="sxs-lookup"><span data-stu-id="09842-243">!</span></span> <span data-ttu-id="09842-244">оператор</span><span class="sxs-lookup"><span data-stu-id="09842-244">operator</span></span>

<span data-ttu-id="09842-245">Можно использовать `!` как псевдоним для `-not`.</span><span class="sxs-lookup"><span data-stu-id="09842-245">You can use `!` as an alias for `-not`.</span></span>

```powershell
if ( -not $value ){}
if ( !$value ){}
```

<span data-ttu-id="09842-246">Как можно заметить, `!` чаще используется теми пользователями, которые переходят на PowerShell с других языков, таких как C#.</span><span class="sxs-lookup"><span data-stu-id="09842-246">You may see `!` used more by people that come from another languages like C#.</span></span> <span data-ttu-id="09842-247">Я предпочитаю печатать этот оператор, потому что мне его трудно увидеть при быстром просмотре сценариев.</span><span class="sxs-lookup"><span data-stu-id="09842-247">I prefer to type it out because I find it hard to see when quickly looking at my scripts.</span></span>

### <a name="-and"></a><span data-ttu-id="09842-248">-and</span><span class="sxs-lookup"><span data-stu-id="09842-248">-and</span></span>

<span data-ttu-id="09842-249">Выражения можно объединять с помощью оператора `-and`.</span><span class="sxs-lookup"><span data-stu-id="09842-249">You can combine expressions with the `-and` operator.</span></span> <span data-ttu-id="09842-250">В этом случае обе стороны должны быть равны `$true`, чтобы все выражение было равно `$true`.</span><span class="sxs-lookup"><span data-stu-id="09842-250">When you do that, both sides need to be `$true` for the whole expression to be `$true`.</span></span>

```powershell
if ( ($age -gt 13) -and ($age -lt 55) )
```

<span data-ttu-id="09842-251">В этом примере `$age` должно быть равно 13 или более для левой части и менее 55 для правой части.</span><span class="sxs-lookup"><span data-stu-id="09842-251">In that example, `$age` must be 13 or older for the left side and less than 55 for the right side.</span></span> <span data-ttu-id="09842-252">Я добавил дополнительные круглые скобки, чтобы выделить эти данные в примере, но это необязательно, если выражение простое.</span><span class="sxs-lookup"><span data-stu-id="09842-252">I added extra parentheses to make it clearer in that example but they're optional as long as the expression is simple.</span></span> <span data-ttu-id="09842-253">Вот пример без дополнительных скобок.</span><span class="sxs-lookup"><span data-stu-id="09842-253">Here is the same example without them.</span></span>

```powershell
if ( $age -gt 13 -and $age -lt 55 )
```

<span data-ttu-id="09842-254">Вычисления выполняются слева направо.</span><span class="sxs-lookup"><span data-stu-id="09842-254">Evaluation happens from left to right.</span></span> <span data-ttu-id="09842-255">Если первый элемент принимает значение `$false`, он преждевременно завершает работу и правильное сравнение не выполняется.</span><span class="sxs-lookup"><span data-stu-id="09842-255">If the first item evaluates to `$false`, it exits early and doesn't perform the right comparison.</span></span> <span data-ttu-id="09842-256">Это удобно, если перед использованием значения необходимо убедиться в том, что оно существует.</span><span class="sxs-lookup"><span data-stu-id="09842-256">This is handy when you need to make sure a value exists before you use it.</span></span> <span data-ttu-id="09842-257">Например, `Test-Path` выдает ошибку, если присвоить ему путь `$null`.</span><span class="sxs-lookup"><span data-stu-id="09842-257">For example, `Test-Path` throws an error if you give it a `$null` path.</span></span>

```powershell
if ( $null -ne $path -and (Test-Path -Path $path) )
```

### <a name="-or"></a><span data-ttu-id="09842-258">-or</span><span class="sxs-lookup"><span data-stu-id="09842-258">-or</span></span>

<span data-ttu-id="09842-259">`-or` позволяет указать два выражения и возвращает значение `$true`, если одно из них равно `$true`.</span><span class="sxs-lookup"><span data-stu-id="09842-259">The `-or` allows for you to specify two expressions and returns `$true` if either one of them is `$true`.</span></span>

```powershell
if ( $age -le 13 -or $age -ge 55 )
```

<span data-ttu-id="09842-260">Как и в случае с оператором `-and`, вычисление выполняется слева направо.</span><span class="sxs-lookup"><span data-stu-id="09842-260">Just like with the `-and` operator, the evaluation happens from left to right.</span></span> <span data-ttu-id="09842-261">Однако если первая часть равна `$true`, то весь оператор равен `$true` и не обрабатывает оставшуюся часть выражения.</span><span class="sxs-lookup"><span data-stu-id="09842-261">Except that if the first part is `$true`, then the whole statement is `$true` and it doesn't process the rest of the expression.</span></span>

<span data-ttu-id="09842-262">Обратите также внимание на то, как работает синтаксис для этих операторов.</span><span class="sxs-lookup"><span data-stu-id="09842-262">Also make note of how the syntax works for these operators.</span></span> <span data-ttu-id="09842-263">Потребуется два отдельных выражения.</span><span class="sxs-lookup"><span data-stu-id="09842-263">You need two separate expressions.</span></span> <span data-ttu-id="09842-264">Я видел, что пользователи пытаются сделать что-то похожее на `$value -eq 5 -or 6`, не понимая, в чем их ошибка.</span><span class="sxs-lookup"><span data-stu-id="09842-264">I have seen users try to do something like this `$value -eq 5 -or 6` without realizing their mistake.</span></span>

### <a name="-xor-exclusive-or"></a><span data-ttu-id="09842-265">-xor (исключающее ИЛИ)</span><span class="sxs-lookup"><span data-stu-id="09842-265">-xor exclusive or</span></span>

<span data-ttu-id="09842-266">Это немного необычный оператор.</span><span class="sxs-lookup"><span data-stu-id="09842-266">This one is a little unusual.</span></span> <span data-ttu-id="09842-267">`-xor` позволяет принимать равным `$true` только одно выражение.</span><span class="sxs-lookup"><span data-stu-id="09842-267">`-xor` allows only one expression to evaluate to `$true`.</span></span> <span data-ttu-id="09842-268">Таким образом, если оба элемента равны `$false` или `$true`, все выражение равно `$false`.</span><span class="sxs-lookup"><span data-stu-id="09842-268">So if both items are `$false` or both items are `$true`, then the whole expression is `$false`.</span></span> <span data-ttu-id="09842-269">Еще один вариант — выражение равно `$true` только в том случае, если результаты выражения отличаются.</span><span class="sxs-lookup"><span data-stu-id="09842-269">Another way to look at this is the expression is only `$true` when the results of the expression are different.</span></span>

<span data-ttu-id="09842-270">Вряд ли кто-то станет вообще использовать этот логический оператор, и я даже не могу придумать хороший пример, зачем я сам стал бы это делать.</span><span class="sxs-lookup"><span data-stu-id="09842-270">It's rare that anyone would ever use this logical operator and I can't think up a good example as to why I would ever use it.</span></span>

## <a name="bitwise-operators"></a><span data-ttu-id="09842-271">Побитовые операторы</span><span class="sxs-lookup"><span data-stu-id="09842-271">Bitwise operators</span></span>

<span data-ttu-id="09842-272">Побитовые операторы выполняют вычисления с битами в значениях и создают новое результирующее значение.</span><span class="sxs-lookup"><span data-stu-id="09842-272">Bitwise operators perform calculations on the bits within the values and produce a new value as the result.</span></span> <span data-ttu-id="09842-273">Обучение работе с [побитовыми операторами][] не рассматривается в этой статье, однако здесь приведен их перечень.</span><span class="sxs-lookup"><span data-stu-id="09842-273">Teaching [bitwise operators][] is beyond the scope of this article, but here is the list the them.</span></span>

- <span data-ttu-id="09842-274">`-band` двоичное И</span><span class="sxs-lookup"><span data-stu-id="09842-274">`-band` binary AND</span></span>
- <span data-ttu-id="09842-275">`-bor` двоичное ИЛИ</span><span class="sxs-lookup"><span data-stu-id="09842-275">`-bor` binary OR</span></span>
- <span data-ttu-id="09842-276">`-bxor` двоичное исключающее ИЛИ</span><span class="sxs-lookup"><span data-stu-id="09842-276">`-bxor` binary exclusive OR</span></span>
- <span data-ttu-id="09842-277">`-bnot` двоичное НЕ</span><span class="sxs-lookup"><span data-stu-id="09842-277">`-bnot` binary NOT</span></span>
- <span data-ttu-id="09842-278">`-shl` сдвиг влево</span><span class="sxs-lookup"><span data-stu-id="09842-278">`-shl` shift left</span></span>
- <span data-ttu-id="09842-279">`-shr` сдвиг вправо</span><span class="sxs-lookup"><span data-stu-id="09842-279">`-shr` shift right</span></span>

## <a name="powershell-expressions"></a><span data-ttu-id="09842-280">Выражения PowerShell</span><span class="sxs-lookup"><span data-stu-id="09842-280">PowerShell expressions</span></span>

<span data-ttu-id="09842-281">В операторе условия можно использовать обычные функции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09842-281">We can use normal PowerShell inside the condition statement.</span></span>

```powershell
if ( Test-Path -Path $Path )
```

<span data-ttu-id="09842-282">При выполнении `Test-Path` возвращает `$true` или `$false`.</span><span class="sxs-lookup"><span data-stu-id="09842-282">`Test-Path` returns `$true` or `$false` when it executes.</span></span> <span data-ttu-id="09842-283">Это также относится к командам, которые возвращают другие значения.</span><span class="sxs-lookup"><span data-stu-id="09842-283">This also applies to commands that return other values.</span></span>

```powershell
if ( Get-Process Notepad* )
```

<span data-ttu-id="09842-284">Оператор принимает значение `$true`, если есть возвращаемый процесс, или `$false`, если такой процесс отсутствует.</span><span class="sxs-lookup"><span data-stu-id="09842-284">It evaluates to `$true` if there's a returned process and `$false` if there'sn'thing.</span></span> <span data-ttu-id="09842-285">Вполне допустимо использовать выражения конвейера или другие операторы PowerShell:</span><span class="sxs-lookup"><span data-stu-id="09842-285">It's perfectly valid to use pipeline expressions or other PowerShell statements like this:</span></span>

```powershell
if ( Get-Process | Where Name -eq Notepad )
```

<span data-ttu-id="09842-286">Эти выражения можно объединять друг с другом с помощью операторов `-and` и `-or`, однако, возможно, потребуется использование круглых скобок, чтобы разбить выражения на части.</span><span class="sxs-lookup"><span data-stu-id="09842-286">These expressions can be combined with each other with the `-and` and `-or` operators, but you may have to use parenthesis to break them into subexpressions.</span></span>

```powershell
if ( (Get-Process) -and (Get-Service) )
```

### <a name="checking-for-null"></a><span data-ttu-id="09842-287">Проверка на наличие значения $null</span><span class="sxs-lookup"><span data-stu-id="09842-287">Checking for $null</span></span>

<span data-ttu-id="09842-288">Отсутствие результата или значение `$null` вычисляется как `$false` в операторе `if`.</span><span class="sxs-lookup"><span data-stu-id="09842-288">Having a no result or a `$null` value evaluates to `$false` in the `if` statement.</span></span> <span data-ttu-id="09842-289">Если выполняется специальная проверка на наличие `$null`, рекомендуется размещать `$null` в левой части.</span><span class="sxs-lookup"><span data-stu-id="09842-289">When checking specifically for `$null`, it's a best practice to place the `$null` on the left-hand side.</span></span>

```powershell
if ( $null -eq $value )
```

<span data-ttu-id="09842-290">При работе со значениями `$null` в PowerShell существует много нюансов.</span><span class="sxs-lookup"><span data-stu-id="09842-290">There are quite a few nuances when dealing with `$null` values in PowerShell.</span></span> <span data-ttu-id="09842-291">Если вы хотите узнать об этом больше, ознакомьтесь с моей статьей обо [всем, что необходимо знать о $null][].</span><span class="sxs-lookup"><span data-stu-id="09842-291">If you're interested in diving deeper, I have an article about [everything you wanted to know about $null][].</span></span>

### <a name="variable-assignment"></a><span data-ttu-id="09842-292">Присвоение значения переменной</span><span class="sxs-lookup"><span data-stu-id="09842-292">Variable assignment</span></span>

<span data-ttu-id="09842-293">Я чуть не забыл добавить этот раздел, хорошо, что [Прасун Карунан В.][] мне об этом напомнил.</span><span class="sxs-lookup"><span data-stu-id="09842-293">I almost forgot to add this one until [Prasoon Karunan V][] reminded me of it.</span></span>

```powershell
if ($process=Get-Process notepad -ErrorAction ignore) {$process} else {$false}
```

<span data-ttu-id="09842-294">Обычно присвоенное переменной значение не передается в конвейер или в консоль.</span><span class="sxs-lookup"><span data-stu-id="09842-294">Normally when you assign a value to a variable, the value isn't passed onto the pipeline or console.</span></span> <span data-ttu-id="09842-295">При присвоении переменной в части выражения оно передается в конвейер.</span><span class="sxs-lookup"><span data-stu-id="09842-295">When you do a variable assignment in a sub expression, it does get passed on to the pipeline.</span></span>

```powershell
PS> $first = 1
PS> ($second = 2)
2
```

<span data-ttu-id="09842-296">Заметили, что присвоение `$first` не создает выходные данные, а присвоение `$second` — создает?</span><span class="sxs-lookup"><span data-stu-id="09842-296">See how the `$first` assignment has no output and the `$second` assignment does?</span></span> <span data-ttu-id="09842-297">Когда присвоение происходит в операторе `if`, оно выполняется точно так же, как присвоение `$second` выше.</span><span class="sxs-lookup"><span data-stu-id="09842-297">When an assignment is done in an `if` statement, it executes just like the `$second` assignment above.</span></span> <span data-ttu-id="09842-298">Далее приведен понятный пример возможного использования.</span><span class="sxs-lookup"><span data-stu-id="09842-298">Here is a clean example on how you could use it:</span></span>

```powershell
if ( $process = Get-Process Notepad* )
{
    $process | Stop-Process
}
```

<span data-ttu-id="09842-299">Если для `$process` присваивается значение, то работа оператора `$true` и `$process` прекращается.</span><span class="sxs-lookup"><span data-stu-id="09842-299">If `$process` gets assigned a value, then the statement is `$true` and `$process` gets stopped.</span></span>

<span data-ttu-id="09842-300">Убедитесь в том, что вы не путаете его с `-eq`, так как это не проверка на равенство.</span><span class="sxs-lookup"><span data-stu-id="09842-300">Make sure you don't confuse this with `-eq` because this isn't an equality check.</span></span> <span data-ttu-id="09842-301">Это малоизвестная функция, и большинство пользователей даже не представляют, что она так работает.</span><span class="sxs-lookup"><span data-stu-id="09842-301">This is a more obscure feature that most people don't realize works this way.</span></span>

## <a name="alternate-execution-path"></a><span data-ttu-id="09842-302">Альтернативный путь выполнения</span><span class="sxs-lookup"><span data-stu-id="09842-302">Alternate execution path</span></span>

<span data-ttu-id="09842-303">Оператор `if` позволяет указать действие не только, когда оператор равен `$true`, но и когда он равен `$false`.</span><span class="sxs-lookup"><span data-stu-id="09842-303">The `if` statement allows you to specify an action for not only when the statement is `$true`, but also for when it's `$false`.</span></span> <span data-ttu-id="09842-304">Именно здесь используется оператор `else`.</span><span class="sxs-lookup"><span data-stu-id="09842-304">This is where the `else` statement comes into play.</span></span>

### <a name="else"></a><span data-ttu-id="09842-305">else</span><span class="sxs-lookup"><span data-stu-id="09842-305">else</span></span>

<span data-ttu-id="09842-306">При использовании оператора `else` он всегда является последней частью оператора `if`.</span><span class="sxs-lookup"><span data-stu-id="09842-306">The `else` statement is always the last part of the `if` statement when used.</span></span>

```powershell
if ( Test-Path -Path $Path -PathType Leaf )
{
    Move-Item -Path $Path -Destination $archivePath
}
else
{
    Write-Warning "$path doesn't exist or isn't a file."
}
```

<span data-ttu-id="09842-307">В этом примере мы проверяем `$path`, чтобы убедиться в том, что это файл.</span><span class="sxs-lookup"><span data-stu-id="09842-307">In this example, we check the `$path` to make sure it's a file.</span></span> <span data-ttu-id="09842-308">Если мы найдем файл, мы его переместим.</span><span class="sxs-lookup"><span data-stu-id="09842-308">If we find the file, we move it.</span></span> <span data-ttu-id="09842-309">В противном случае мы создаем предупреждение.</span><span class="sxs-lookup"><span data-stu-id="09842-309">If not, we write a warning.</span></span> <span data-ttu-id="09842-310">Этот тип логики ветвления весьма распространен.</span><span class="sxs-lookup"><span data-stu-id="09842-310">This type of branching logic is very common.</span></span>

### <a name="nested-if"></a><span data-ttu-id="09842-311">Вложенное IF</span><span class="sxs-lookup"><span data-stu-id="09842-311">Nested if</span></span>

<span data-ttu-id="09842-312">Операторы `if` и `else` принимают блок сценария, поэтому мы можем поместить в них любую команду PowerShell, в том числе еще один оператор `if`.</span><span class="sxs-lookup"><span data-stu-id="09842-312">The `if` and `else` statements take a script block, so we can place any PowerShell command inside them, including another `if` statement.</span></span> <span data-ttu-id="09842-313">Это позволяет использовать гораздо более сложную логику.</span><span class="sxs-lookup"><span data-stu-id="09842-313">This allows you to make use of much more complicated logic.</span></span>

```powershell
if ( Test-Path -Path $Path -PathType Leaf )
{
    Move-Item -Path $Path -Destination $archivePath
}
else
{
    if ( Test-Path -Path $Path )
    {
        Write-Warning "A file was required but a directory was found instead."
    }
    else
    {
        Write-Warning "$path could not be found."
    }
}
```

<span data-ttu-id="09842-314">В этом примере мы сначала тестируем удачный путь, а затем используем его на практике.</span><span class="sxs-lookup"><span data-stu-id="09842-314">In this example, we test the happy path first and then take action on it.</span></span> <span data-ttu-id="09842-315">Если это не удалось сделать, выполняется еще одна проверка, чтобы указать более подробные сведения для пользователя.</span><span class="sxs-lookup"><span data-stu-id="09842-315">If that fails, we do another check and to provide more detailed information to the user.</span></span>

### <a name="elseif"></a><span data-ttu-id="09842-316">elseif</span><span class="sxs-lookup"><span data-stu-id="09842-316">elseif</span></span>

<span data-ttu-id="09842-317">Мы не ограничиваемся одной условной проверкой.</span><span class="sxs-lookup"><span data-stu-id="09842-317">We aren't limited to just a single conditional check.</span></span> <span data-ttu-id="09842-318">Можно объединять операторы `if` и `else` в цепочку, а не вкладывать их с помощью оператора `elseif`.</span><span class="sxs-lookup"><span data-stu-id="09842-318">We can chain `if` and `else` statements together instead of nesting them by using the `elseif` statement.</span></span>

```powershell
if ( Test-Path -Path $Path -PathType Leaf )
{
    Move-Item -Path $Path -Destination $archivePath
}
elseif ( Test-Path -Path $Path )
{
    Write-Warning "A file was required but a directory was found instead."
}
else
{
    Write-Warning "$path could not be found."
}
```

<span data-ttu-id="09842-319">Они выполняются в направлении сверху вниз.</span><span class="sxs-lookup"><span data-stu-id="09842-319">The execution happens from the top to the bottom.</span></span> <span data-ttu-id="09842-320">Верхний оператор `if` вычисляется в первую очередь.</span><span class="sxs-lookup"><span data-stu-id="09842-320">The top `if` statement is evaluated first.</span></span> <span data-ttu-id="09842-321">Если это `$false`, вычисление выполняется для следующего оператора `elseif` или `else` в списке.</span><span class="sxs-lookup"><span data-stu-id="09842-321">If that is `$false`, then it moves down to the next `elseif` or `else` in the list.</span></span> <span data-ttu-id="09842-322">Последний оператор `else` является действием по умолчанию, которое выполняется, если ни одно другое действие не возвращает `$true`.</span><span class="sxs-lookup"><span data-stu-id="09842-322">That last `else` is the default action to take if none of the others return `$true`.</span></span>

### <a name="switch"></a><span data-ttu-id="09842-323">Параметр</span><span class="sxs-lookup"><span data-stu-id="09842-323">switch</span></span>

<span data-ttu-id="09842-324">На этом этапе я должен рассказать об операторе `switch`.</span><span class="sxs-lookup"><span data-stu-id="09842-324">At this point, I need to mention the `switch` statement.</span></span> <span data-ttu-id="09842-325">Он предоставляет альтернативный синтаксис для выполнения нескольких сравнений со значением.</span><span class="sxs-lookup"><span data-stu-id="09842-325">It provides an alternate syntax for doing multiple comparisons with a value.</span></span> <span data-ttu-id="09842-326">С помощью `switch` указывается выражение, а полученный результат сравнивается с несколькими различными значениями.</span><span class="sxs-lookup"><span data-stu-id="09842-326">With the `switch`, you specify an expression and that result gets compared with several different values.</span></span> <span data-ttu-id="09842-327">Если одно из этих значений совпадает, выполняется соответствующий блок кода.</span><span class="sxs-lookup"><span data-stu-id="09842-327">If one of those values match, the matching code block is executed.</span></span> <span data-ttu-id="09842-328">Взгляните на этот пример:</span><span class="sxs-lookup"><span data-stu-id="09842-328">Take a look at this example:</span></span>

```powershell
$itemType = 'Role'
switch ( $itemType )
{
    'Component'
    {
        'is a component'
    }
    'Role'
    {
        'is a role'
    }
    'Location'
    {
        'is a location'
    }
}
```

<span data-ttu-id="09842-329">Существует три возможных значения, которые могут совпадать с `$itemType`.</span><span class="sxs-lookup"><span data-stu-id="09842-329">There three possible values that can match the `$itemType`.</span></span> <span data-ttu-id="09842-330">В этом случае оно совпадает с `Role`.</span><span class="sxs-lookup"><span data-stu-id="09842-330">In this case, it matches with `Role`.</span></span> <span data-ttu-id="09842-331">Я использовал этот простой пример, просто чтобы продемонстрировать работу оператора `switch`.</span><span class="sxs-lookup"><span data-stu-id="09842-331">I used a simple example just to give you some exposure to the `switch` operator.</span></span> <span data-ttu-id="09842-332">В другой статье я подробно описываю [все, что вы хотите знать об операторе switch][].</span><span class="sxs-lookup"><span data-stu-id="09842-332">I talk more about [everything you ever wanted to know about the switch statement][] in another article.</span></span>

## <a name="pipeline"></a><span data-ttu-id="09842-333">Pipeline</span><span class="sxs-lookup"><span data-stu-id="09842-333">Pipeline</span></span>

<span data-ttu-id="09842-334">Конвейер — уникальная и важная функция PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09842-334">The pipeline is a unique and important feature of PowerShell.</span></span> <span data-ttu-id="09842-335">Любое значение, которое не подавляется и не присваивается переменной, помещается в конвейер.</span><span class="sxs-lookup"><span data-stu-id="09842-335">Any value that isn't suppressed or assigned to a variable gets placed in the pipeline.</span></span> <span data-ttu-id="09842-336">`if` позволяет нам воспользоваться преимуществами конвейера таким способом, который не всегда очевиден.</span><span class="sxs-lookup"><span data-stu-id="09842-336">The `if` provides us a way to take advantage of the pipeline in a way that isn't always obvious.</span></span>

```powershell
$discount = if ( $age -ge 55 )
{
    Get-SeniorDiscount
}
elseif ( $age -le 13 )
{
    Get-ChildDiscount
}
else
{
    0.00
}
```

<span data-ttu-id="09842-337">Каждый блок сценария помещает в конвейер результаты выполнения команд или значение.</span><span class="sxs-lookup"><span data-stu-id="09842-337">Each script block is placing the results the commands or the value into the pipeline.</span></span> <span data-ttu-id="09842-338">Затем мы присваиваем результат оператора if переменной `$discount`.</span><span class="sxs-lookup"><span data-stu-id="09842-338">Then we assign the result of the if statement to the `$discount` variable.</span></span> <span data-ttu-id="09842-339">В этом примере можно так же легко присвоить эти значения переменной `$discount` непосредственно в каждом блоке ScriptBlock.</span><span class="sxs-lookup"><span data-stu-id="09842-339">That example could have just as easily assigned those values to the `$discount` variable directly in each scriptblock.</span></span> <span data-ttu-id="09842-340">Не сказал бы, что я часто использую эту возможность для оператора `if`, однако у меня есть пример недавнего использования.</span><span class="sxs-lookup"><span data-stu-id="09842-340">I can't say that I use this with the `if` statement often, but I do have an example where I used this recently.</span></span>

### <a name="array-inline"></a><span data-ttu-id="09842-341">Массив в строке</span><span class="sxs-lookup"><span data-stu-id="09842-341">Array inline</span></span>

<span data-ttu-id="09842-342">У меня есть функция с именем [Invoke-SnowSql][], которая запускает исполняемый файл с несколькими аргументами командной строки.</span><span class="sxs-lookup"><span data-stu-id="09842-342">I have a function called [Invoke-SnowSql][] that launches an executable with several command-line arguments.</span></span> <span data-ttu-id="09842-343">Вот фрагмент этой функции, где я создаю массив аргументов.</span><span class="sxs-lookup"><span data-stu-id="09842-343">Here is a clip from that function where I build the array of arguments.</span></span>

```powershell
$snowSqlParam = @(
    '--accountname', $Endpoint
    '--username', $Credential.UserName
    '--option', 'exit_on_error=true'
    '--option', 'output_format=csv'
    '--option', 'friendly=false'
    '--option', 'timing=false'
    if ($Debug)
    {
        '--option', 'log_level=DEBUG'
    }
    if ($Path)
    {
        '--filename', $Path
    }
    else
    {
        '--query', $singleLineQuery
    }
)
```

<span data-ttu-id="09842-344">Переменные `$Debug` и `$Path` являются параметрами функции, которые указываются конечным пользователем.</span><span class="sxs-lookup"><span data-stu-id="09842-344">The `$Debug` and `$Path` variables are parameters on the function that are provided by the end user.</span></span>
<span data-ttu-id="09842-345">Я вычисляю их в строке при инициализации массива.</span><span class="sxs-lookup"><span data-stu-id="09842-345">I evaluate them inline inside the initialization of my array.</span></span> <span data-ttu-id="09842-346">Если `$Debug` имеет значение true, эти значения помещаются в нужной точке в `$snowSqlParam`.</span><span class="sxs-lookup"><span data-stu-id="09842-346">If `$Debug` is true, then those values fall into the `$snowSqlParam` in the correct place.</span></span> <span data-ttu-id="09842-347">То же самое верно для переменной `$Path`.</span><span class="sxs-lookup"><span data-stu-id="09842-347">Same holds true for the `$Path` variable.</span></span>

## <a name="simplify-complex-operations"></a><span data-ttu-id="09842-348">Упрощение сложных операций</span><span class="sxs-lookup"><span data-stu-id="09842-348">Simplify complex operations</span></span>

<span data-ttu-id="09842-349">Вы неизбежно столкнетесь с такой ситуацией, когда необходимо проверить множество сравнений и для просмотра оператора if придется долго прокручивать экран вправо.</span><span class="sxs-lookup"><span data-stu-id="09842-349">It's inevitable that you run into a situation that has way too many comparisons to check and your if statement scrolls way off the right side of the screen.</span></span>

```powershell
$user = Get-ADUser -Identity $UserName
if ( $null -ne $user -and $user.Department -eq 'Finance' -and $user.Title -match 'Senior' -and $user.HomeDrive -notlike '\\server\*' )
{
    # Do Something
}
```

<span data-ttu-id="09842-350">Они могут быть трудночитаемыми, и из-за этого возможны ошибки.</span><span class="sxs-lookup"><span data-stu-id="09842-350">They can be hard to read and that make you more prone to make mistakes.</span></span> <span data-ttu-id="09842-351">Эту проблему можно решить несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="09842-351">There are a few things we can do about that.</span></span>

### <a name="line-continuation"></a><span data-ttu-id="09842-352">Продолжение строки</span><span class="sxs-lookup"><span data-stu-id="09842-352">Line continuation</span></span>

<span data-ttu-id="09842-353">В PowerShell есть ряд операторов, которые позволяют переносить команды на следующую строку.</span><span class="sxs-lookup"><span data-stu-id="09842-353">There some operators in PowerShell that let you wrap you command to the next line.</span></span> <span data-ttu-id="09842-354">Логические операторы `-and` и `-or` полезны, если нужно разбить выражение на несколько строк.</span><span class="sxs-lookup"><span data-stu-id="09842-354">The logical operators `-and` and `-or` are good operators to use if you want to break your expression into multiple lines.</span></span>

```powershell
if ($null -ne $user -and
    $user.Department -eq 'Finance' -and
    $user.Title -match 'Senior' -and
    $user.HomeDrive -notlike '\\server\*'
)
{
    # Do Something
}
```

<span data-ttu-id="09842-355">Там выполняется еще много действий, но размещение каждого фрагмента в отдельной строке в корне меняет дело.</span><span class="sxs-lookup"><span data-stu-id="09842-355">There's still a lot going on there, but placing each piece on its own line makes a big difference.</span></span>
<span data-ttu-id="09842-356">Я обычно использую эту функцию, если у меня более двух сравнений или мне приходится прокручивать экран вправо, чтобы прочитать любую часть логики.</span><span class="sxs-lookup"><span data-stu-id="09842-356">I generally use this when I get more than two comparisons or if I have to scroll to the right to read any of the logic.</span></span>

### <a name="pre-calculating-results"></a><span data-ttu-id="09842-357">Предварительное вычисление результатов</span><span class="sxs-lookup"><span data-stu-id="09842-357">Pre-calculating results</span></span>

<span data-ttu-id="09842-358">Мы можем взять эту инструкцию из оператора if и просто проверить результат.</span><span class="sxs-lookup"><span data-stu-id="09842-358">We can take that statement out of the if statement and only check the result.</span></span>

```powershell
$needsSecureHomeDrive = $null -ne $user -and
    $user.Department -eq 'Finance' -and
    $user.Title -match 'Senior' -and
    $user.HomeDrive -notlike '\\server\*'

if ( $needsSecureHomeDrive )
{
    # Do Something
}
```

<span data-ttu-id="09842-359">Это гораздо более понятно, чем в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="09842-359">This just feels much cleaner than the previous example.</span></span> <span data-ttu-id="09842-360">У вас также есть возможность использовать имя переменной, которое разъясняет, что именно вы проверяете.</span><span class="sxs-lookup"><span data-stu-id="09842-360">You also are given an opportunity to use a variable name that explains what it's that you're really checking.</span></span> <span data-ttu-id="09842-361">Это также пример самодокументируемого кода, в котором сохраняются несущественные комментарии.</span><span class="sxs-lookup"><span data-stu-id="09842-361">This is also and example of self-documenting code that saves unnecessary comments.</span></span>

### <a name="multiple-if-statements"></a><span data-ttu-id="09842-362">Несколько операторов if</span><span class="sxs-lookup"><span data-stu-id="09842-362">Multiple if statements</span></span>

<span data-ttu-id="09842-363">Можно разбить этот фрагмент на несколько операторов и проверить их по одному.</span><span class="sxs-lookup"><span data-stu-id="09842-363">We can break this up into multiple statements and check them one at a time.</span></span> <span data-ttu-id="09842-364">В этом случае для объединения результатов используется флаг или переменная отслеживания.</span><span class="sxs-lookup"><span data-stu-id="09842-364">In this case, we use a flag or a tracking variable to combine the results.</span></span>

```powershell

$skipUser = $false

if( $null -eq $user )
{
    $skipUser = $true
}

if( $user.Department -ne 'Finance' )
{
    Write-Verbose "isn't in Finance department"
    $skipUser = $true
}

if( $user.Title -match 'Senior' )
{
    Write-Verbose "Doesn't have Senior title"
    $skipUser = $true
}

if( $user.HomeDrive -like '\\server\*' )
{
    Write-Verbose "Home drive already configured"
    $skipUser = $true
}

if ( -not $skipUser )
{
    # do something
}
```

<span data-ttu-id="09842-365">Мне нужно было инвертировать логику, чтобы логика флагов работала корректно.</span><span class="sxs-lookup"><span data-stu-id="09842-365">I did have to invert the logic to make the flag logic work correctly.</span></span> <span data-ttu-id="09842-366">Каждое вычисление представляет собой отдельный оператор `if`.</span><span class="sxs-lookup"><span data-stu-id="09842-366">Each evaluation is an individual `if` statement.</span></span> <span data-ttu-id="09842-367">Преимущество такого подхода заключается в том, что при отладке вы сможете точно определить, что делает эта логика.</span><span class="sxs-lookup"><span data-stu-id="09842-367">The advantage of this is that when you're debugging, you can tell exactly what the logic is doing.</span></span> <span data-ttu-id="09842-368">В то же время мне удалось обеспечить гораздо более высокий уровень детализации.</span><span class="sxs-lookup"><span data-stu-id="09842-368">I was able to add much better verbosity at the same time.</span></span>

<span data-ttu-id="09842-369">Очевидным недостатком является то, что приходится писать гораздо больше кода.</span><span class="sxs-lookup"><span data-stu-id="09842-369">The obvious downside is that it's so much more code to write.</span></span> <span data-ttu-id="09842-370">Код более сложен для просмотра, так как он занимает одну строку логики и разворачивает ее в 25 или более строк.</span><span class="sxs-lookup"><span data-stu-id="09842-370">The code is more complex to look at as it takes a single line of logic and explodes it into 25 or more lines.</span></span>

### <a name="using-functions"></a><span data-ttu-id="09842-371">Использование функций</span><span class="sxs-lookup"><span data-stu-id="09842-371">Using functions</span></span>

<span data-ttu-id="09842-372">Кроме того, можно переместить всю логику проверки в функцию.</span><span class="sxs-lookup"><span data-stu-id="09842-372">We can also move all that validation logic into a function.</span></span> <span data-ttu-id="09842-373">Посмотрите, насколько простым и понятным это выглядит.</span><span class="sxs-lookup"><span data-stu-id="09842-373">Look at how clean this looks at a glance.</span></span>

```powershell
if ( Test-SecureDriveConfiguration -ADUser $user )
{
    # do something
}
```

<span data-ttu-id="09842-374">Вам по-прежнему необходимо создать функцию для выполнения проверки, однако благодаря этому с кодом будет гораздо проще работать.</span><span class="sxs-lookup"><span data-stu-id="09842-374">You still have to create the function to do the validation, but it makes this code much easier to work with.</span></span> <span data-ttu-id="09842-375">Это упрощает тестирование кода.</span><span class="sxs-lookup"><span data-stu-id="09842-375">It makes this code easier to test.</span></span> <span data-ttu-id="09842-376">В тестах можно имитировать вызов `Test-ADDriveConfiguration`, и для этой функции потребуется всего два теста.</span><span class="sxs-lookup"><span data-stu-id="09842-376">In your tests, you can mock the call to `Test-ADDriveConfiguration` and you only need two tests for this function.</span></span> <span data-ttu-id="09842-377">В одном из них она возвращает `$true`, а во втором — `$false`.</span><span class="sxs-lookup"><span data-stu-id="09842-377">One where it returns `$true` and one where it returns `$false`.</span></span> <span data-ttu-id="09842-378">Тестировать другую функцию проще, потому что она совсем небольшая.</span><span class="sxs-lookup"><span data-stu-id="09842-378">Testing the other function is simpler because it's so small.</span></span>

<span data-ttu-id="09842-379">Текстовая область этой функции по-прежнему может состоять всего из одной строки, как это было в самом начале, или может быть расчлененной логикой, которую мы использовали в последнем разделе.</span><span class="sxs-lookup"><span data-stu-id="09842-379">The body of that function could still be that one-liner we started with or the exploded logic that we used in the last section.</span></span> <span data-ttu-id="09842-380">Это эффективно в рамках обоих сценариев и позволяет легко изменить данную реализацию позднее.</span><span class="sxs-lookup"><span data-stu-id="09842-380">This works well for both scenarios and allows you to easily change that implementation later.</span></span>

## <a name="error-handling"></a><span data-ttu-id="09842-381">Обработка ошибок</span><span class="sxs-lookup"><span data-stu-id="09842-381">Error handling</span></span>

<span data-ttu-id="09842-382">Одной из основных целей использования оператора `if` является проверка наличия условий возникновения ошибок, прежде чем они появятся.</span><span class="sxs-lookup"><span data-stu-id="09842-382">One important use of the `if` statement is to check for error conditions before you run into errors.</span></span> <span data-ttu-id="09842-383">Например, вы можете проверить, существует ли папка, до того, как попытаетесь ее создать.</span><span class="sxs-lookup"><span data-stu-id="09842-383">A good example is to check if a folder already exists before you try to create it.</span></span>

```powershell
if ( -not (Test-Path -Path $folder) )
{
    New-Item -Type Directory -Path $folder
}
```

<span data-ttu-id="09842-384">Я люблю говорить: если вы ожидаете, что возникнет исключение, значит, на самом деле это не исключение.</span><span class="sxs-lookup"><span data-stu-id="09842-384">I like to say that if you expect an exception to happen, then it's not really an exception.</span></span> <span data-ttu-id="09842-385">Таким образом, лучше при любом удобном случае проверять свои значения и условия.</span><span class="sxs-lookup"><span data-stu-id="09842-385">So check your values and validate your conditions where you can.</span></span>

<span data-ttu-id="09842-386">Более подробно о фактической обработке исключений см. в моей статье, где рассматривается [все, что вы хотели знать об исключениях][].</span><span class="sxs-lookup"><span data-stu-id="09842-386">If you want to dive a little more into actual exception handling, I have an article on [everything you ever wanted to know about exceptions][].</span></span>

## <a name="final-words"></a><span data-ttu-id="09842-387">Заключение</span><span class="sxs-lookup"><span data-stu-id="09842-387">Final words</span></span>

<span data-ttu-id="09842-388">Оператор `if` очень простой, но именно он является основополагающим компонентом PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09842-388">The `if` statement is such a simple statement but is a fundamental piece of PowerShell.</span></span> <span data-ttu-id="09842-389">Вы будете очень часто его использовать практически в каждом созданном вами сценарии.</span><span class="sxs-lookup"><span data-stu-id="09842-389">You will find yourself using this multiple times in almost every script you write.</span></span> <span data-ttu-id="09842-390">Надеюсь, теперь вы лучше понимаете его работу, чем раньше.</span><span class="sxs-lookup"><span data-stu-id="09842-390">I hope you have a better understanding than you had before.</span></span>

<!-- link references -->
[Оригинал]: https://powershellexplained.com/2019-08-11-PowerShell-if-then-else-equals-operator/
[original version]: https://powershellexplained.com/2019-08-11-PowerShell-if-then-else-equals-operator/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[if]: /powershell/module/microsoft.powershell.core/about/about_if (если);
[побитовыми операторами]: https://powershellexplained.com/powershell/module/microsoft.powershell.core/about/about_arithmetic_operators#bitwise-operators
[bitwise operators]: https://powershellexplained.com/powershell/module/microsoft.powershell.core/about/about_arithmetic_operators#bitwise-operators
[множестве способов использования регулярных выражений]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression/
[the many ways to use regex]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression/
[все, что вы хотели знать об исключениях]: everything-about-exceptions.md
[everything you ever wanted to know about exceptions]: everything-about-exceptions.md
[всем, что необходимо знать о $null]: everything-about-null.md
[everything you wanted to know about $null]: everything-about-null.md
[Прасун Карунан В.]: https://twitter.com/prasoonkarunan
[Prasoon Karunan V]: https://twitter.com/prasoonkarunan
[все, что вы хотите знать об операторе switch]: everything-about-switch.md
[everything you ever wanted to know about the switch statement]: everything-about-switch.md
[Invoke-SnowSql]: https://github.com/loanDepot/SnowSQL/blob/a3731b52e4ab4ecb503fb81e2d8cb131e8f90410/SnowSQL/public/Invoke-SnowSql.ps1#L90
