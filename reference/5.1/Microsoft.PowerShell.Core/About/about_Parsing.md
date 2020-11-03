---
description: Описывает, как PowerShell выполняет синтаксический анализ команд.
keywords: powershell,командлет
Locale: en-US
ms.date: 09/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_parsing?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parsing
ms.openlocfilehash: d7b5af8c94ad6370c69773d2bc3796bace60ef7c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232345"
---
# <a name="about-parsing"></a><span data-ttu-id="bf15d-104">Сведения о синтаксическом анализе</span><span class="sxs-lookup"><span data-stu-id="bf15d-104">About Parsing</span></span>

## <a name="short-description"></a><span data-ttu-id="bf15d-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="bf15d-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="bf15d-106">Описывает, как PowerShell выполняет синтаксический анализ команд.</span><span class="sxs-lookup"><span data-stu-id="bf15d-106">Describes how PowerShell parses commands.</span></span>

## <a name="long-description"></a><span data-ttu-id="bf15d-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="bf15d-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="bf15d-108">При вводе команды в командной строке PowerShell разбивает текст команды на ряд сегментов, называемых _токенами_ , а затем определяет способ интерпретации каждого маркера.</span><span class="sxs-lookup"><span data-stu-id="bf15d-108">When you enter a command at the command prompt, PowerShell breaks the command text into a series of segments called _tokens_ and then determines how to interpret each token.</span></span>

<span data-ttu-id="bf15d-109">Например, если ввести:</span><span class="sxs-lookup"><span data-stu-id="bf15d-109">For example, if you type:</span></span>

```powershell
Write-Host book
```

<span data-ttu-id="bf15d-110">PowerShell разбивает команду на два токена, и `Write-Host` `book` и интерпретирует каждый маркер независимо друг от друга, используя один из двух основных режимов анализа: режим выражения и режим аргументов.</span><span class="sxs-lookup"><span data-stu-id="bf15d-110">PowerShell breaks the command into two tokens, `Write-Host` and `book`, and interprets each token independently using one of two major parsing modes: expression mode and argument mode.</span></span>

> [!NOTE]
> <span data-ttu-id="bf15d-111">Так как PowerShell анализирует ввод команды, он пытается разрешить имена команд в командлеты или собственные исполняемые файлы.</span><span class="sxs-lookup"><span data-stu-id="bf15d-111">As PowerShell parses command input it tries to resolve the command names to cmdlets or native executables.</span></span> <span data-ttu-id="bf15d-112">Если имя команды не имеет точного совпадения, PowerShell добавляется `Get-` к команде в качестве глагола по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bf15d-112">If a command name does not have an exact match, PowerShell prepends `Get-` to the command as a default verb.</span></span> <span data-ttu-id="bf15d-113">Например, PowerShell анализируется `Process` как `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="bf15d-113">For example, PowerShell parses `Process` as `Get-Process`.</span></span> <span data-ttu-id="bf15d-114">Не рекомендуется использовать эту функцию по следующим причинам.</span><span class="sxs-lookup"><span data-stu-id="bf15d-114">It's not recommended to use this feature for the following reasons:</span></span>
>
> - <span data-ttu-id="bf15d-115">Это неэффективно.</span><span class="sxs-lookup"><span data-stu-id="bf15d-115">It's inefficient.</span></span> <span data-ttu-id="bf15d-116">В результате PowerShell будет выполнять поиск несколько раз.</span><span class="sxs-lookup"><span data-stu-id="bf15d-116">This causes PowerShell to search multiple times.</span></span>
> - <span data-ttu-id="bf15d-117">Внешние программы с тем же именем разрешаются первыми, поэтому вы не можете выполнить предполагаемый командлет.</span><span class="sxs-lookup"><span data-stu-id="bf15d-117">External programs with the same name are resolved first, so you may not execute intended cmdlet.</span></span>
> - <span data-ttu-id="bf15d-118">`Get-Help` и `Get-Command` не распознают имена без команд.</span><span class="sxs-lookup"><span data-stu-id="bf15d-118">`Get-Help` and `Get-Command` don't recognize verb-less names.</span></span>

### <a name="expression-mode"></a><span data-ttu-id="bf15d-119">Режим выражения</span><span class="sxs-lookup"><span data-stu-id="bf15d-119">Expression mode</span></span>

<span data-ttu-id="bf15d-120">Режим выражения предназначен для объединения выражений, необходимых для обработки значений в языке сценариев.</span><span class="sxs-lookup"><span data-stu-id="bf15d-120">Expression mode is intended for combining expressions, required for value manipulation in a scripting language.</span></span> <span data-ttu-id="bf15d-121">Выражения — это представления значений в синтаксисе PowerShell, которые могут быть простыми или составными, например:</span><span class="sxs-lookup"><span data-stu-id="bf15d-121">Expressions are representations of values in PowerShell syntax, and can be simple or composite, for example:</span></span>

<span data-ttu-id="bf15d-122">Литеральные выражения — это прямые представления их значений.</span><span class="sxs-lookup"><span data-stu-id="bf15d-122">Literal expressions are direct representations of their values:</span></span>

```powershell
'hello', 32
```

<span data-ttu-id="bf15d-123">Переменные выражения содержат значение переменной, на которую они ссылаются:</span><span class="sxs-lookup"><span data-stu-id="bf15d-123">Variable expressions carry the value of the variable they reference:</span></span>

```powershell
$x, $script:path
```

<span data-ttu-id="bf15d-124">Операторы объединяют другие выражения для оценки:</span><span class="sxs-lookup"><span data-stu-id="bf15d-124">Operators combine other expressions for evaluation:</span></span>

```powershell
- 12, -not $Quiet, 3 + 7, $input.Length -gt 1
```

- <span data-ttu-id="bf15d-125">_Символьные строковые литералы_ должны содержаться в кавычках.</span><span class="sxs-lookup"><span data-stu-id="bf15d-125">_Character string literals_ must be contained in quotation marks.</span></span>
- <span data-ttu-id="bf15d-126">_Числа_ обрабатываются как числовые значения, а не как последовательность символов (за исключением экранирования).</span><span class="sxs-lookup"><span data-stu-id="bf15d-126">_Numbers_ are treated as numerical values rather than as a series of characters (unless escaped).</span></span>
- <span data-ttu-id="bf15d-127">_Операторы_ , включая унарные операторы, такие как `-` и `-not` , и бинарные операторы, такие как `+` и `-gt` , обрабатываются как операторы и применяют соответствующие операции к их аргументам (операндам).</span><span class="sxs-lookup"><span data-stu-id="bf15d-127">_Operators_ , including unary operators like `-` and `-not` and binary operators like `+` and `-gt`, are interpreted as operators and apply their respective operations on their arguments (operands).</span></span>
- <span data-ttu-id="bf15d-128">_Выражения атрибутов и преобразований_ анализируются как выражения и применяются к подчиненным выражениям, например `[int] '7'` .</span><span class="sxs-lookup"><span data-stu-id="bf15d-128">_Attribute and conversion expressions_ are parsed as expressions and applied to subordinate expressions, e.g. `[int] '7'`.</span></span>
- <span data-ttu-id="bf15d-129">_Ссылки на переменные_ оцениваются по их значениям, но _Сплаттинг_ (т. е. предварительно заполненные наборы параметров) запрещены и вызывают ошибку синтаксического анализатора.</span><span class="sxs-lookup"><span data-stu-id="bf15d-129">_Variable references_ are evaluated to their values but _splatting_ (i.e. pasting prefilled parameter sets) is forbidden and causes a parser error.</span></span>
- <span data-ttu-id="bf15d-130">Все остальное будет рассматриваться как вызываемая команда.</span><span class="sxs-lookup"><span data-stu-id="bf15d-130">Anything else will be treated as a command to be invoked.</span></span>

### <a name="argument-mode"></a><span data-ttu-id="bf15d-131">Режим аргументов</span><span class="sxs-lookup"><span data-stu-id="bf15d-131">Argument mode</span></span>

<span data-ttu-id="bf15d-132">При синтаксическом анализе PowerShell сначала выполняет интерпретацию входных данных как выражения.</span><span class="sxs-lookup"><span data-stu-id="bf15d-132">When parsing, PowerShell first looks to interpret input as an expression.</span></span> <span data-ttu-id="bf15d-133">Но при обнаружении вызова команды синтаксический анализ продолжится в режиме аргументов.</span><span class="sxs-lookup"><span data-stu-id="bf15d-133">But when a command invocation is encountered, parsing continues in argument mode.</span></span>

<span data-ttu-id="bf15d-134">Режим аргументов предназначен для синтаксического анализа аргументов и параметров команд в среде оболочки.</span><span class="sxs-lookup"><span data-stu-id="bf15d-134">Argument mode is designed for parsing arguments and parameters for commands in a shell environment.</span></span> <span data-ttu-id="bf15d-135">Все входные данные обрабатываются как расширяемая строка, если она не использует один из следующих синтаксисов:</span><span class="sxs-lookup"><span data-stu-id="bf15d-135">All input is treated as an expandable string unless it uses one of the following syntaxes:</span></span>

- <span data-ttu-id="bf15d-136">Знак доллара ( `$` ) начинает ссылку на переменную (только если за ней следует допустимое имя переменной, в противном случае оно интерпретируется как часть расширяемой строки).</span><span class="sxs-lookup"><span data-stu-id="bf15d-136">Dollar sign (`$`) begins a variable reference (only if it is followed by a valid variable name, otherwise it is interpreted as part of the expandable string).</span></span>
- <span data-ttu-id="bf15d-137">Кавычки ( `'` и `"` ) начало строковых значений</span><span class="sxs-lookup"><span data-stu-id="bf15d-137">Quotation marks (`'` and `"`) begin string values</span></span>
- <span data-ttu-id="bf15d-138">Круглые скобки ( `(` и `)` ) разграничения новые выражения.</span><span class="sxs-lookup"><span data-stu-id="bf15d-138">Parentheses (`(` and `)`) demarcate new expressions.</span></span>
- <span data-ttu-id="bf15d-139">Оператор части выражения ( `$(` ... `)` ) обозначает Embedded Expressions.</span><span class="sxs-lookup"><span data-stu-id="bf15d-139">Subexpression operator (`$(`…`)`) demarcates embedded expressions.</span></span>
- <span data-ttu-id="bf15d-140">В фигурные скобки ( `{` и `}` ) разграничения новые блоки скриптов.</span><span class="sxs-lookup"><span data-stu-id="bf15d-140">Braces (`{` and `}`) demarcate new script blocks.</span></span>
- <span data-ttu-id="bf15d-141">Начальная подпись at ( `@` ) начинает синтаксис выражений, таких как сплаттинг ( `@args` ), Arrays ( `@(1,2,3)` ) и hash Tables ( `@{a=1;b=2}` ).</span><span class="sxs-lookup"><span data-stu-id="bf15d-141">Initial at sign (`@`) begins expression syntaxes such as splatting (`@args`), arrays (`@(1,2,3)`) and hash tables (`@{a=1;b=2}`).</span></span>
- <span data-ttu-id="bf15d-142">Запятые ( `,` ) предоставляют списки, переданные в виде массивов, за исключением случаев, когда вызываемая команда является собственным приложением. в этом случае они рассматриваются как часть расширяемой строки.</span><span class="sxs-lookup"><span data-stu-id="bf15d-142">Commas (`,`) introduce lists passed as arrays, except when the command to be called is a native application, in which case they are interpreted as part of the expandable string.</span></span> <span data-ttu-id="bf15d-143">Начальные, последовательные или конечные запятые не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="bf15d-143">Initial, consecutive or trailing commas are not supported.</span></span>

<span data-ttu-id="bf15d-144">Значения внедренных выражений преобразуются в строки.</span><span class="sxs-lookup"><span data-stu-id="bf15d-144">Values of embedded expressions are converted to strings.</span></span>

<span data-ttu-id="bf15d-145">В следующей таблице приведены несколько примеров значений, обрабатываемых в режиме выражений и в режиме аргументов, а также вычисление этих значений.</span><span class="sxs-lookup"><span data-stu-id="bf15d-145">The following table provides several examples of values processed in expression mode and argument mode and the evaluation of those values.</span></span> <span data-ttu-id="bf15d-146">Предполагается, что значение переменной `a` равно `4` .</span><span class="sxs-lookup"><span data-stu-id="bf15d-146">We assume that the value of the variable `a` is `4`.</span></span>

|       <span data-ttu-id="bf15d-147">Пример</span><span class="sxs-lookup"><span data-stu-id="bf15d-147">Example</span></span>        |    <span data-ttu-id="bf15d-148">Режим</span><span class="sxs-lookup"><span data-stu-id="bf15d-148">Mode</span></span>    |      <span data-ttu-id="bf15d-149">Результат</span><span class="sxs-lookup"><span data-stu-id="bf15d-149">Result</span></span>       |
| -------------------- | ---------- | ----------------- |
| `2`                  | <span data-ttu-id="bf15d-150">Выражение</span><span class="sxs-lookup"><span data-stu-id="bf15d-150">Expression</span></span> | <span data-ttu-id="bf15d-151">2 (целое число)</span><span class="sxs-lookup"><span data-stu-id="bf15d-151">2 (integer)</span></span>       |
| `` `2``              | <span data-ttu-id="bf15d-152">Expression</span><span class="sxs-lookup"><span data-stu-id="bf15d-152">Expression</span></span> | <span data-ttu-id="bf15d-153">"2" (команда)</span><span class="sxs-lookup"><span data-stu-id="bf15d-153">"2" (command)</span></span>     |
| `echo 2`             | <span data-ttu-id="bf15d-154">Expression</span><span class="sxs-lookup"><span data-stu-id="bf15d-154">Expression</span></span> | <span data-ttu-id="bf15d-155">2 (целое число)</span><span class="sxs-lookup"><span data-stu-id="bf15d-155">2 (integer)</span></span>       |
| `2+2`                | <span data-ttu-id="bf15d-156">Expression</span><span class="sxs-lookup"><span data-stu-id="bf15d-156">Expression</span></span> | <span data-ttu-id="bf15d-157">4 (целое число)</span><span class="sxs-lookup"><span data-stu-id="bf15d-157">4 (integer)</span></span>       |
| `echo 2+2`           | <span data-ttu-id="bf15d-158">Аргумент</span><span class="sxs-lookup"><span data-stu-id="bf15d-158">Argument</span></span>   | <span data-ttu-id="bf15d-159">"2 + 2" (строка)</span><span class="sxs-lookup"><span data-stu-id="bf15d-159">"2+2" (string)</span></span>    |
| `echo(2+2)`          | <span data-ttu-id="bf15d-160">Expression</span><span class="sxs-lookup"><span data-stu-id="bf15d-160">Expression</span></span> | <span data-ttu-id="bf15d-161">4 (целое число)</span><span class="sxs-lookup"><span data-stu-id="bf15d-161">4 (integer)</span></span>       |
| `$a`                 | <span data-ttu-id="bf15d-162">Expression</span><span class="sxs-lookup"><span data-stu-id="bf15d-162">Expression</span></span> | <span data-ttu-id="bf15d-163">4 (целое число)</span><span class="sxs-lookup"><span data-stu-id="bf15d-163">4 (integer)</span></span>       |
| `echo $a`            | <span data-ttu-id="bf15d-164">Expression</span><span class="sxs-lookup"><span data-stu-id="bf15d-164">Expression</span></span> | <span data-ttu-id="bf15d-165">4 (целое число)</span><span class="sxs-lookup"><span data-stu-id="bf15d-165">4 (integer)</span></span>       |
| `$a+2`               | <span data-ttu-id="bf15d-166">Expression</span><span class="sxs-lookup"><span data-stu-id="bf15d-166">Expression</span></span> | <span data-ttu-id="bf15d-167">6 (целое число)</span><span class="sxs-lookup"><span data-stu-id="bf15d-167">6 (integer)</span></span>       |
| `echo $a+2`          | <span data-ttu-id="bf15d-168">Аргумент</span><span class="sxs-lookup"><span data-stu-id="bf15d-168">Argument</span></span>   | <span data-ttu-id="bf15d-169">4 + 2 (строка)</span><span class="sxs-lookup"><span data-stu-id="bf15d-169">4+2 (string)</span></span>      |
| `$-`                 | <span data-ttu-id="bf15d-170">Аргумент</span><span class="sxs-lookup"><span data-stu-id="bf15d-170">Argument</span></span>   | <span data-ttu-id="bf15d-171">"$-" (команда)</span><span class="sxs-lookup"><span data-stu-id="bf15d-171">"$-" (command)</span></span>    |
| `echo $-`            | <span data-ttu-id="bf15d-172">Аргумент</span><span class="sxs-lookup"><span data-stu-id="bf15d-172">Argument</span></span>   | <span data-ttu-id="bf15d-173">"$-" (строка)</span><span class="sxs-lookup"><span data-stu-id="bf15d-173">"$-" (string)</span></span>     |
| `a$a`                | <span data-ttu-id="bf15d-174">Expression</span><span class="sxs-lookup"><span data-stu-id="bf15d-174">Expression</span></span> | <span data-ttu-id="bf15d-175">"a $ a" (команда)</span><span class="sxs-lookup"><span data-stu-id="bf15d-175">"a$a" (command)</span></span>   |
| `echo a$a`           | <span data-ttu-id="bf15d-176">Аргумент</span><span class="sxs-lookup"><span data-stu-id="bf15d-176">Argument</span></span>   | <span data-ttu-id="bf15d-177">"A4" (строка)</span><span class="sxs-lookup"><span data-stu-id="bf15d-177">"a4" (string)</span></span>     |
| `a'$a'`              | <span data-ttu-id="bf15d-178">Expression</span><span class="sxs-lookup"><span data-stu-id="bf15d-178">Expression</span></span> | <span data-ttu-id="bf15d-179">"a $ a" (команда)</span><span class="sxs-lookup"><span data-stu-id="bf15d-179">"a$a" (command)</span></span>   |
| `echo a'$a'`         | <span data-ttu-id="bf15d-180">Аргумент</span><span class="sxs-lookup"><span data-stu-id="bf15d-180">Argument</span></span>   | <span data-ttu-id="bf15d-181">"a $ a" (строка)</span><span class="sxs-lookup"><span data-stu-id="bf15d-181">"a$a" (string)</span></span>    |
| `a"$a"`              | <span data-ttu-id="bf15d-182">Expression</span><span class="sxs-lookup"><span data-stu-id="bf15d-182">Expression</span></span> | <span data-ttu-id="bf15d-183">"a $ a" (команда)</span><span class="sxs-lookup"><span data-stu-id="bf15d-183">"a$a" (command)</span></span>   |
| `echo a"$a"`         | <span data-ttu-id="bf15d-184">Аргумент</span><span class="sxs-lookup"><span data-stu-id="bf15d-184">Argument</span></span>   | <span data-ttu-id="bf15d-185">"A4" (строка)</span><span class="sxs-lookup"><span data-stu-id="bf15d-185">"a4" (string)</span></span>     |
| `a$(2)`              | <span data-ttu-id="bf15d-186">Expression</span><span class="sxs-lookup"><span data-stu-id="bf15d-186">Expression</span></span> | <span data-ttu-id="bf15d-187">"a $ (2)" (команда)</span><span class="sxs-lookup"><span data-stu-id="bf15d-187">"a$(2)" (command)</span></span> |
| `echo a$(2)`         | <span data-ttu-id="bf15d-188">Аргумент</span><span class="sxs-lookup"><span data-stu-id="bf15d-188">Argument</span></span>   | <span data-ttu-id="bf15d-189">"a2" (строка)</span><span class="sxs-lookup"><span data-stu-id="bf15d-189">"a2" (string)</span></span>     |

<span data-ttu-id="bf15d-190">Каждый токен может интерпретироваться как некоторый тип объекта, например Boolean или String.</span><span class="sxs-lookup"><span data-stu-id="bf15d-190">Every token can be interpreted as some kind of object type, such as Boolean or string.</span></span> <span data-ttu-id="bf15d-191">PowerShell пытается определить тип объекта из выражения.</span><span class="sxs-lookup"><span data-stu-id="bf15d-191">PowerShell attempts to determine the object type from the expression.</span></span>
<span data-ttu-id="bf15d-192">Тип объекта зависит от типа параметра, который требуется команде, и от того, знает ли PowerShell, как преобразовать аргумент в правильный тип.</span><span class="sxs-lookup"><span data-stu-id="bf15d-192">The object type depends on the type of parameter a command expects and on whether PowerShell knows how to convert the argument to the correct type.</span></span> <span data-ttu-id="bf15d-193">В следующей таблице приведены несколько примеров типов, назначенных значениям, возвращаемым выражениями.</span><span class="sxs-lookup"><span data-stu-id="bf15d-193">The following table shows several examples of the types assigned to values returned by the expressions.</span></span>

|       <span data-ttu-id="bf15d-194">Пример</span><span class="sxs-lookup"><span data-stu-id="bf15d-194">Example</span></span>          |    <span data-ttu-id="bf15d-195">Режим</span><span class="sxs-lookup"><span data-stu-id="bf15d-195">Mode</span></span>    |     <span data-ttu-id="bf15d-196">Результат</span><span class="sxs-lookup"><span data-stu-id="bf15d-196">Result</span></span>      |
| ---------------------- | ---------- | --------------- |
| `Write-Output !1`      | <span data-ttu-id="bf15d-197">— аргумент</span><span class="sxs-lookup"><span data-stu-id="bf15d-197">argument</span></span>   | <span data-ttu-id="bf15d-198">"! 1" (строка)</span><span class="sxs-lookup"><span data-stu-id="bf15d-198">"!1" (string)</span></span>   |
| `Write-Output (!1)`    | <span data-ttu-id="bf15d-199">expression</span><span class="sxs-lookup"><span data-stu-id="bf15d-199">expression</span></span> | <span data-ttu-id="bf15d-200">False (логическое значение)</span><span class="sxs-lookup"><span data-stu-id="bf15d-200">False (Boolean)</span></span> |
| `Write-Output (2)`     | <span data-ttu-id="bf15d-201">expression</span><span class="sxs-lookup"><span data-stu-id="bf15d-201">expression</span></span> | <span data-ttu-id="bf15d-202">2 (целое число)</span><span class="sxs-lookup"><span data-stu-id="bf15d-202">2 (integer)</span></span>     |
| `Set-Variable AB A,B`  | <span data-ttu-id="bf15d-203">— аргумент</span><span class="sxs-lookup"><span data-stu-id="bf15d-203">argument</span></span>   | <span data-ttu-id="bf15d-204">"A", "B" (массив)</span><span class="sxs-lookup"><span data-stu-id="bf15d-204">'A','B' (array)</span></span> |
| `CMD /CECHO A,B`       | <span data-ttu-id="bf15d-205">— аргумент</span><span class="sxs-lookup"><span data-stu-id="bf15d-205">argument</span></span>   | <span data-ttu-id="bf15d-206">"A, B" (строка)</span><span class="sxs-lookup"><span data-stu-id="bf15d-206">'A,B' (string)</span></span>  |
| `CMD /CECHO $AB`       | <span data-ttu-id="bf15d-207">expression</span><span class="sxs-lookup"><span data-stu-id="bf15d-207">expression</span></span> | <span data-ttu-id="bf15d-208">"A", "B" (массив)</span><span class="sxs-lookup"><span data-stu-id="bf15d-208">'A','B' (array)</span></span> |
| `CMD /CECHO :$AB`      | <span data-ttu-id="bf15d-209">— аргумент</span><span class="sxs-lookup"><span data-stu-id="bf15d-209">argument</span></span>   | <span data-ttu-id="bf15d-210">": A B" (строка)</span><span class="sxs-lookup"><span data-stu-id="bf15d-210">':A B' (string)</span></span> |

<span data-ttu-id="bf15d-211">Символ "точка-анализ" ( `--%` ), представленный в powershell 3,0, направляет PowerShell для отключения от интерпретации входных данных как команд или выражений PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf15d-211">The stop-parsing symbol (`--%`), introduced in PowerShell 3.0, directs PowerShell to refrain from interpreting input as PowerShell commands or expressions.</span></span>

<span data-ttu-id="bf15d-212">При вызове исполняемой программы в PowerShell перед программными аргументами поместите символ "точка-анализ".</span><span class="sxs-lookup"><span data-stu-id="bf15d-212">When calling an executable program in PowerShell, place the stop-parsing symbol before the program arguments.</span></span> <span data-ttu-id="bf15d-213">Этот метод гораздо проще, чем использование escape-символов для предотвращения неточной интерпретации.</span><span class="sxs-lookup"><span data-stu-id="bf15d-213">This technique is much easier than using escape characters to prevent misinterpretation.</span></span>

<span data-ttu-id="bf15d-214">Когда обнаруживает символ "точка-анализ", PowerShell считает остальные символы в строке как литералы.</span><span class="sxs-lookup"><span data-stu-id="bf15d-214">When it encounters a stop-parsing symbol, PowerShell treats the remaining characters in the line as a literal.</span></span> <span data-ttu-id="bf15d-215">Единственной интерпретацией, которую он выполняет, является замена значений для переменных среды, использующих стандартную нотацию Windows, например `%USERPROFILE%` .</span><span class="sxs-lookup"><span data-stu-id="bf15d-215">The only interpretation it performs is to substitute values for environment variables that use standard Windows notation, such as `%USERPROFILE%`.</span></span>

<span data-ttu-id="bf15d-216">Символ "точка-анализ" действует только до следующей новой строки или символа конвейера.</span><span class="sxs-lookup"><span data-stu-id="bf15d-216">The stop-parsing symbol is effective only until the next newline or pipeline character.</span></span> <span data-ttu-id="bf15d-217">Нельзя использовать символ продолжения ( `` ` `` ), чтобы расширить его действие, или использовать разделитель команд ( `;` ) для завершения его воздействия.</span><span class="sxs-lookup"><span data-stu-id="bf15d-217">You cannot use a continuation character (`` ` ``) to extend its effect or use a command delimiter (`;`) to terminate its effect.</span></span>

<span data-ttu-id="bf15d-218">Например, следующая команда вызывает программу **icacls** .</span><span class="sxs-lookup"><span data-stu-id="bf15d-218">For example, the following command calls the **Icacls** program.</span></span>

```powershell
icacls X:\VMS /grant Dom\HVAdmin:(CI)(OI)F
```

<span data-ttu-id="bf15d-219">Чтобы выполнить эту команду в PowerShell 2,0, необходимо использовать escape-символы, чтобы запретить PowerShell правильно интерпретировать круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="bf15d-219">To run this command in PowerShell 2.0, you must use escape characters to prevent PowerShell from misinterpreting the parentheses.</span></span>

```powershell
icacls X:\VMS /grant Dom\HVAdmin:`(CI`)`(OI`)F
```

<span data-ttu-id="bf15d-220">Начиная с PowerShell 3,0 можно использовать символ "прерывать анализ".</span><span class="sxs-lookup"><span data-stu-id="bf15d-220">Beginning in PowerShell 3.0, you can use the stop-parsing symbol.</span></span>

```powershell
icacls X:\VMS --% /grant Dom\HVAdmin:(CI)(OI)F
```

<span data-ttu-id="bf15d-221">PowerShell отправляет следующую командную строку в программу **icacls** :</span><span class="sxs-lookup"><span data-stu-id="bf15d-221">PowerShell sends the following command string to the **Icacls** program:</span></span>

`X:\VMS /grant Dom\HVAdmin:(CI)(OI)F`

## <a name="see-also"></a><span data-ttu-id="bf15d-222">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="bf15d-222">SEE ALSO</span></span>

[<span data-ttu-id="bf15d-223">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="bf15d-223">about_Command_Syntax</span></span>](about_Command_Syntax.md)
