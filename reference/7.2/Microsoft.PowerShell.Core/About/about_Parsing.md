---
description: Описывает, как PowerShell выполняет синтаксический анализ команд.
Locale: en-US
ms.date: 09/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_parsing?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parsing
ms.openlocfilehash: a5ce30b2ad9aff7dd8b54e7a62937013a61cd278
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605074"
---
# <a name="about-parsing"></a><span data-ttu-id="4024a-103">Сведения о синтаксическом анализе</span><span class="sxs-lookup"><span data-stu-id="4024a-103">About Parsing</span></span>

## <a name="short-description"></a><span data-ttu-id="4024a-104">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="4024a-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="4024a-105">Описывает, как PowerShell выполняет синтаксический анализ команд.</span><span class="sxs-lookup"><span data-stu-id="4024a-105">Describes how PowerShell parses commands.</span></span>

## <a name="long-description"></a><span data-ttu-id="4024a-106">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="4024a-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="4024a-107">При вводе команды в командной строке PowerShell разбивает текст команды на ряд сегментов, называемых _токенами_ , а затем определяет способ интерпретации каждого маркера.</span><span class="sxs-lookup"><span data-stu-id="4024a-107">When you enter a command at the command prompt, PowerShell breaks the command text into a series of segments called _tokens_ and then determines how to interpret each token.</span></span>

<span data-ttu-id="4024a-108">Например, если ввести:</span><span class="sxs-lookup"><span data-stu-id="4024a-108">For example, if you type:</span></span>

```powershell
Write-Host book
```

<span data-ttu-id="4024a-109">PowerShell разбивает команду на два токена, и `Write-Host` `book` и интерпретирует каждый маркер независимо друг от друга, используя один из двух основных режимов анализа: режим выражения и режим аргументов.</span><span class="sxs-lookup"><span data-stu-id="4024a-109">PowerShell breaks the command into two tokens, `Write-Host` and `book`, and interprets each token independently using one of two major parsing modes: expression mode and argument mode.</span></span>

> [!NOTE]
> <span data-ttu-id="4024a-110">Так как PowerShell анализирует ввод команды, он пытается разрешить имена команд в командлеты или собственные исполняемые файлы.</span><span class="sxs-lookup"><span data-stu-id="4024a-110">As PowerShell parses command input it tries to resolve the command names to cmdlets or native executables.</span></span> <span data-ttu-id="4024a-111">Если имя команды не имеет точного совпадения, PowerShell добавляется `Get-` к команде в качестве глагола по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4024a-111">If a command name does not have an exact match, PowerShell prepends `Get-` to the command as a default verb.</span></span> <span data-ttu-id="4024a-112">Например, PowerShell анализируется `Process` как `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="4024a-112">For example, PowerShell parses `Process` as `Get-Process`.</span></span> <span data-ttu-id="4024a-113">Не рекомендуется использовать эту функцию по следующим причинам.</span><span class="sxs-lookup"><span data-stu-id="4024a-113">It's not recommended to use this feature for the following reasons:</span></span>
>
> - <span data-ttu-id="4024a-114">Это неэффективно.</span><span class="sxs-lookup"><span data-stu-id="4024a-114">It's inefficient.</span></span> <span data-ttu-id="4024a-115">В результате PowerShell будет выполнять поиск несколько раз.</span><span class="sxs-lookup"><span data-stu-id="4024a-115">This causes PowerShell to search multiple times.</span></span>
> - <span data-ttu-id="4024a-116">Внешние программы с тем же именем разрешаются первыми, поэтому вы не можете выполнить предполагаемый командлет.</span><span class="sxs-lookup"><span data-stu-id="4024a-116">External programs with the same name are resolved first, so you may not execute intended cmdlet.</span></span>
> - <span data-ttu-id="4024a-117">`Get-Help` и `Get-Command` не распознают имена без команд.</span><span class="sxs-lookup"><span data-stu-id="4024a-117">`Get-Help` and `Get-Command` don't recognize verb-less names.</span></span>

### <a name="expression-mode"></a><span data-ttu-id="4024a-118">Режим выражения</span><span class="sxs-lookup"><span data-stu-id="4024a-118">Expression mode</span></span>

<span data-ttu-id="4024a-119">Режим выражения предназначен для объединения выражений, необходимых для обработки значений в языке сценариев.</span><span class="sxs-lookup"><span data-stu-id="4024a-119">Expression mode is intended for combining expressions, required for value manipulation in a scripting language.</span></span> <span data-ttu-id="4024a-120">Выражения — это представления значений в синтаксисе PowerShell, которые могут быть простыми или составными, например:</span><span class="sxs-lookup"><span data-stu-id="4024a-120">Expressions are representations of values in PowerShell syntax, and can be simple or composite, for example:</span></span>

<span data-ttu-id="4024a-121">Литеральные выражения — это прямые представления их значений.</span><span class="sxs-lookup"><span data-stu-id="4024a-121">Literal expressions are direct representations of their values:</span></span> 

```powershell
'hello', 32
```

<span data-ttu-id="4024a-122">Переменные выражения содержат значение переменной, на которую они ссылаются:</span><span class="sxs-lookup"><span data-stu-id="4024a-122">Variable expressions carry the value of the variable they reference:</span></span> 

```powershell
$x, $script:path
```
<span data-ttu-id="4024a-123">Операторы объединяют другие выражения для оценки:</span><span class="sxs-lookup"><span data-stu-id="4024a-123">Operators combine other expressions for evaluation:</span></span> 

```powershell
- 12, -not $Quiet, 3 + 7, $input.Length -gt 1
```

- <span data-ttu-id="4024a-124">_Символьные строковые литералы_ должны содержаться в кавычках.</span><span class="sxs-lookup"><span data-stu-id="4024a-124">_Character string literals_ must be contained in quotation marks.</span></span>
- <span data-ttu-id="4024a-125">_Числа_ обрабатываются как числовые значения, а не как последовательность символов (за исключением экранирования).</span><span class="sxs-lookup"><span data-stu-id="4024a-125">_Numbers_ are treated as numerical values rather than as a series of characters (unless escaped).</span></span>
- <span data-ttu-id="4024a-126">_Операторы_, включая унарные операторы, такие как `-` и `-not` , и бинарные операторы, такие как `+` и `-gt` , обрабатываются как операторы и применяют соответствующие операции к их аргументам (операндам).</span><span class="sxs-lookup"><span data-stu-id="4024a-126">_Operators_, including unary operators like `-` and `-not` and binary operators like `+` and `-gt`, are interpreted as operators and apply their respective operations on their arguments (operands).</span></span>
- <span data-ttu-id="4024a-127">_Выражения атрибутов и преобразований_ анализируются как выражения и применяются к подчиненным выражениям, например `[int] '7'` .</span><span class="sxs-lookup"><span data-stu-id="4024a-127">_Attribute and conversion expressions_ are parsed as expressions and applied to subordinate expressions, e.g. `[int] '7'`.</span></span>
- <span data-ttu-id="4024a-128">_Ссылки на переменные_ оцениваются по их значениям, но _Сплаттинг_ (т. е. предварительно заполненные наборы параметров) запрещены и вызывают ошибку синтаксического анализатора.</span><span class="sxs-lookup"><span data-stu-id="4024a-128">_Variable references_ are evaluated to their values but _splatting_ (i.e. pasting prefilled parameter sets) is forbidden and causes a parser error.</span></span>
- <span data-ttu-id="4024a-129">Все остальное будет рассматриваться как вызываемая команда.</span><span class="sxs-lookup"><span data-stu-id="4024a-129">Anything else will be treated as a command to be invoked.</span></span>

### <a name="argument-mode"></a><span data-ttu-id="4024a-130">Режим аргументов</span><span class="sxs-lookup"><span data-stu-id="4024a-130">Argument mode</span></span>

<span data-ttu-id="4024a-131">При синтаксическом анализе PowerShell сначала выполняет интерпретацию входных данных как выражения.</span><span class="sxs-lookup"><span data-stu-id="4024a-131">When parsing, PowerShell first looks to interpret input as an expression.</span></span> <span data-ttu-id="4024a-132">Но при обнаружении вызова команды синтаксический анализ продолжится в режиме аргументов.</span><span class="sxs-lookup"><span data-stu-id="4024a-132">But when a command invocation is encountered, parsing continues in argument mode.</span></span>

<span data-ttu-id="4024a-133">Режим аргументов предназначен для синтаксического анализа аргументов и параметров команд в среде оболочки.</span><span class="sxs-lookup"><span data-stu-id="4024a-133">Argument mode is designed for parsing arguments and parameters for commands in a shell environment.</span></span> <span data-ttu-id="4024a-134">Все входные данные обрабатываются как расширяемая строка, если она не использует один из следующих синтаксисов:</span><span class="sxs-lookup"><span data-stu-id="4024a-134">All input is treated as an expandable string unless it uses one of the following syntaxes:</span></span>

- <span data-ttu-id="4024a-135">Знак доллара ( `$` ) начинает ссылку на переменную (только если за ней следует допустимое имя переменной, в противном случае оно интерпретируется как часть расширяемой строки).</span><span class="sxs-lookup"><span data-stu-id="4024a-135">Dollar sign (`$`) begins a variable reference (only if it is followed by a valid variable name, otherwise it is interpreted as part of the expandable string).</span></span>
- <span data-ttu-id="4024a-136">Кавычки ( `'` и `"` ) начало строковых значений</span><span class="sxs-lookup"><span data-stu-id="4024a-136">Quotation marks (`'` and `"`) begin string values</span></span>
- <span data-ttu-id="4024a-137">Круглые скобки ( `(` и `)` ) разграничения новые выражения.</span><span class="sxs-lookup"><span data-stu-id="4024a-137">Parentheses (`(` and `)`) demarcate new expressions.</span></span>
- <span data-ttu-id="4024a-138">Оператор части выражения ( `$(` ... `)` ) обозначает Embedded Expressions.</span><span class="sxs-lookup"><span data-stu-id="4024a-138">Subexpression operator (`$(`…`)`) demarcates embedded expressions.</span></span>
- <span data-ttu-id="4024a-139">В фигурные скобки ( `{` и `}` ) разграничения новые блоки скриптов.</span><span class="sxs-lookup"><span data-stu-id="4024a-139">Braces (`{` and `}`) demarcate new script blocks.</span></span>
- <span data-ttu-id="4024a-140">Начальная подпись at ( `@` ) начинает синтаксис выражений, таких как сплаттинг ( `@args` ), Arrays ( `@(1,2,3)` ) и hash Tables ( `@{a=1;b=2}` ).</span><span class="sxs-lookup"><span data-stu-id="4024a-140">Initial at sign (`@`) begins expression syntaxes such as splatting (`@args`), arrays (`@(1,2,3)`) and hash tables (`@{a=1;b=2}`).</span></span>
- <span data-ttu-id="4024a-141">Запятые ( `,` ) предоставляют списки, переданные в виде массивов, за исключением случаев, когда вызываемая команда является собственным приложением. в этом случае они рассматриваются как часть расширяемой строки.</span><span class="sxs-lookup"><span data-stu-id="4024a-141">Commas (`,`) introduce lists passed as arrays, except when the command to be called is a native application, in which case they are interpreted as part of the expandable string.</span></span> <span data-ttu-id="4024a-142">Начальные, последовательные или конечные запятые не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="4024a-142">Initial, consecutive or trailing commas are not supported.</span></span>

<!--
01234567890123456789012345678901234567890123456789012345678901234567890123456789
-->
<span data-ttu-id="4024a-143">Значения внедренных выражений преобразуются в строки.</span><span class="sxs-lookup"><span data-stu-id="4024a-143">Values of embedded expressions are converted to strings.</span></span>

<span data-ttu-id="4024a-144">В следующей таблице приведены несколько примеров значений, обрабатываемых в режиме выражений и в режиме аргументов, а также вычисление этих значений.</span><span class="sxs-lookup"><span data-stu-id="4024a-144">The following table provides several examples of values processed in expression mode and argument mode and the evaluation of those values.</span></span> <span data-ttu-id="4024a-145">Предполагается, что значение переменной `a` равно `4` .</span><span class="sxs-lookup"><span data-stu-id="4024a-145">We assume that the value of the variable `a` is `4`.</span></span>

|       <span data-ttu-id="4024a-146">Пример</span><span class="sxs-lookup"><span data-stu-id="4024a-146">Example</span></span>        |    <span data-ttu-id="4024a-147">Режим</span><span class="sxs-lookup"><span data-stu-id="4024a-147">Mode</span></span>    |      <span data-ttu-id="4024a-148">Результат</span><span class="sxs-lookup"><span data-stu-id="4024a-148">Result</span></span>       |
| -------------------- | ---------- | ----------------- |
| `2`                  | <span data-ttu-id="4024a-149">Выражение</span><span class="sxs-lookup"><span data-stu-id="4024a-149">Expression</span></span> | <span data-ttu-id="4024a-150">2 (целое число)</span><span class="sxs-lookup"><span data-stu-id="4024a-150">2 (integer)</span></span>       |
| `` `2``              | <span data-ttu-id="4024a-151">Expression</span><span class="sxs-lookup"><span data-stu-id="4024a-151">Expression</span></span> | <span data-ttu-id="4024a-152">"2" (команда)</span><span class="sxs-lookup"><span data-stu-id="4024a-152">"2" (command)</span></span>     |
| `echo 2`             | <span data-ttu-id="4024a-153">Expression</span><span class="sxs-lookup"><span data-stu-id="4024a-153">Expression</span></span> | <span data-ttu-id="4024a-154">2 (целое число)</span><span class="sxs-lookup"><span data-stu-id="4024a-154">2 (integer)</span></span>       |
| `2+2`                | <span data-ttu-id="4024a-155">Expression</span><span class="sxs-lookup"><span data-stu-id="4024a-155">Expression</span></span> | <span data-ttu-id="4024a-156">4 (целое число)</span><span class="sxs-lookup"><span data-stu-id="4024a-156">4 (integer)</span></span>       |
| `echo 2+2`           | <span data-ttu-id="4024a-157">Аргумент</span><span class="sxs-lookup"><span data-stu-id="4024a-157">Argument</span></span>   | <span data-ttu-id="4024a-158">"2 + 2" (строка)</span><span class="sxs-lookup"><span data-stu-id="4024a-158">"2+2" (string)</span></span>    |
| `echo(2+2)`          | <span data-ttu-id="4024a-159">Expression</span><span class="sxs-lookup"><span data-stu-id="4024a-159">Expression</span></span> | <span data-ttu-id="4024a-160">4 (целое число)</span><span class="sxs-lookup"><span data-stu-id="4024a-160">4 (integer)</span></span>       |
| `$a`                 | <span data-ttu-id="4024a-161">Expression</span><span class="sxs-lookup"><span data-stu-id="4024a-161">Expression</span></span> | <span data-ttu-id="4024a-162">4 (целое число)</span><span class="sxs-lookup"><span data-stu-id="4024a-162">4 (integer)</span></span>       |
| `echo $a`            | <span data-ttu-id="4024a-163">Expression</span><span class="sxs-lookup"><span data-stu-id="4024a-163">Expression</span></span> | <span data-ttu-id="4024a-164">4 (целое число)</span><span class="sxs-lookup"><span data-stu-id="4024a-164">4 (integer)</span></span>       |
| `$a+2`               | <span data-ttu-id="4024a-165">Expression</span><span class="sxs-lookup"><span data-stu-id="4024a-165">Expression</span></span> | <span data-ttu-id="4024a-166">6 (целое число)</span><span class="sxs-lookup"><span data-stu-id="4024a-166">6 (integer)</span></span>       |
| `echo $a+2`          | <span data-ttu-id="4024a-167">Аргумент</span><span class="sxs-lookup"><span data-stu-id="4024a-167">Argument</span></span>   | <span data-ttu-id="4024a-168">4 + 2 (строка)</span><span class="sxs-lookup"><span data-stu-id="4024a-168">4+2 (string)</span></span>      |
| `$-`                 | <span data-ttu-id="4024a-169">Аргумент</span><span class="sxs-lookup"><span data-stu-id="4024a-169">Argument</span></span>   | <span data-ttu-id="4024a-170">"$-" (команда)</span><span class="sxs-lookup"><span data-stu-id="4024a-170">"$-" (command)</span></span>    |
| `echo $-`            | <span data-ttu-id="4024a-171">Аргумент</span><span class="sxs-lookup"><span data-stu-id="4024a-171">Argument</span></span>   | <span data-ttu-id="4024a-172">"$-" (строка)</span><span class="sxs-lookup"><span data-stu-id="4024a-172">"$-" (string)</span></span>     |
| `a$a`                | <span data-ttu-id="4024a-173">Expression</span><span class="sxs-lookup"><span data-stu-id="4024a-173">Expression</span></span> | <span data-ttu-id="4024a-174">"a $ a" (команда)</span><span class="sxs-lookup"><span data-stu-id="4024a-174">"a$a" (command)</span></span>   |
| `echo a$a`           | <span data-ttu-id="4024a-175">Аргумент</span><span class="sxs-lookup"><span data-stu-id="4024a-175">Argument</span></span>   | <span data-ttu-id="4024a-176">"A4" (строка)</span><span class="sxs-lookup"><span data-stu-id="4024a-176">"a4" (string)</span></span>     |
| `a'$a'`              | <span data-ttu-id="4024a-177">Expression</span><span class="sxs-lookup"><span data-stu-id="4024a-177">Expression</span></span> | <span data-ttu-id="4024a-178">"a $ a" (команда)</span><span class="sxs-lookup"><span data-stu-id="4024a-178">"a$a" (command)</span></span>   |
| `echo a'$a'`         | <span data-ttu-id="4024a-179">Аргумент</span><span class="sxs-lookup"><span data-stu-id="4024a-179">Argument</span></span>   | <span data-ttu-id="4024a-180">"a $ a" (строка)</span><span class="sxs-lookup"><span data-stu-id="4024a-180">"a$a" (string)</span></span>    |
| `a"$a"`              | <span data-ttu-id="4024a-181">Expression</span><span class="sxs-lookup"><span data-stu-id="4024a-181">Expression</span></span> | <span data-ttu-id="4024a-182">"a $ a" (команда)</span><span class="sxs-lookup"><span data-stu-id="4024a-182">"a$a" (command)</span></span>   |
| `echo a"$a"`         | <span data-ttu-id="4024a-183">Аргумент</span><span class="sxs-lookup"><span data-stu-id="4024a-183">Argument</span></span>   | <span data-ttu-id="4024a-184">"A4" (строка)</span><span class="sxs-lookup"><span data-stu-id="4024a-184">"a4" (string)</span></span>     |
| `a$(2)`              | <span data-ttu-id="4024a-185">Expression</span><span class="sxs-lookup"><span data-stu-id="4024a-185">Expression</span></span> | <span data-ttu-id="4024a-186">"a $ (2)" (команда)</span><span class="sxs-lookup"><span data-stu-id="4024a-186">"a$(2)" (command)</span></span> |
| `echo a$(2)`         | <span data-ttu-id="4024a-187">Аргумент</span><span class="sxs-lookup"><span data-stu-id="4024a-187">Argument</span></span>   | <span data-ttu-id="4024a-188">"a2" (строка)</span><span class="sxs-lookup"><span data-stu-id="4024a-188">"a2" (string)</span></span>     |

<span data-ttu-id="4024a-189">Каждый токен может интерпретироваться как некоторый тип объекта, например Boolean или String.</span><span class="sxs-lookup"><span data-stu-id="4024a-189">Every token can be interpreted as some kind of object type, such as Boolean or string.</span></span> <span data-ttu-id="4024a-190">PowerShell пытается определить тип объекта из выражения.</span><span class="sxs-lookup"><span data-stu-id="4024a-190">PowerShell attempts to determine the object type from the expression.</span></span>
<span data-ttu-id="4024a-191">Тип объекта зависит от типа параметра, который требуется команде, и от того, знает ли PowerShell, как преобразовать аргумент в правильный тип.</span><span class="sxs-lookup"><span data-stu-id="4024a-191">The object type depends on the type of parameter a command expects and on whether PowerShell knows how to convert the argument to the correct type.</span></span> <span data-ttu-id="4024a-192">В следующей таблице приведены несколько примеров типов, назначенных значениям, возвращаемым выражениями.</span><span class="sxs-lookup"><span data-stu-id="4024a-192">The following table shows several examples of the types assigned to values returned by the expressions.</span></span>

|       <span data-ttu-id="4024a-193">Пример</span><span class="sxs-lookup"><span data-stu-id="4024a-193">Example</span></span>          |    <span data-ttu-id="4024a-194">Режим</span><span class="sxs-lookup"><span data-stu-id="4024a-194">Mode</span></span>    |     <span data-ttu-id="4024a-195">Результат</span><span class="sxs-lookup"><span data-stu-id="4024a-195">Result</span></span>      |
| ---------------------- | ---------- | --------------- |
| `Write-Output !1`      | <span data-ttu-id="4024a-196">— аргумент</span><span class="sxs-lookup"><span data-stu-id="4024a-196">argument</span></span>   | <span data-ttu-id="4024a-197">"! 1" (строка)</span><span class="sxs-lookup"><span data-stu-id="4024a-197">"!1" (string)</span></span>   |
| `Write-Output (!1)`    | <span data-ttu-id="4024a-198">expression</span><span class="sxs-lookup"><span data-stu-id="4024a-198">expression</span></span> | <span data-ttu-id="4024a-199">False (логическое значение)</span><span class="sxs-lookup"><span data-stu-id="4024a-199">False (Boolean)</span></span> |
| `Write-Output (2)`     | <span data-ttu-id="4024a-200">expression</span><span class="sxs-lookup"><span data-stu-id="4024a-200">expression</span></span> | <span data-ttu-id="4024a-201">2 (целое число)</span><span class="sxs-lookup"><span data-stu-id="4024a-201">2 (integer)</span></span>     |
| `Set-Variable AB A,B`  | <span data-ttu-id="4024a-202">— аргумент</span><span class="sxs-lookup"><span data-stu-id="4024a-202">argument</span></span>   | <span data-ttu-id="4024a-203">"A", "B" (массив)</span><span class="sxs-lookup"><span data-stu-id="4024a-203">'A','B' (array)</span></span> |
| `CMD /CECHO A,B`       | <span data-ttu-id="4024a-204">— аргумент</span><span class="sxs-lookup"><span data-stu-id="4024a-204">argument</span></span>   | <span data-ttu-id="4024a-205">"A, B" (строка)</span><span class="sxs-lookup"><span data-stu-id="4024a-205">'A,B' (string)</span></span>  |
| `CMD /CECHO $AB`       | <span data-ttu-id="4024a-206">expression</span><span class="sxs-lookup"><span data-stu-id="4024a-206">expression</span></span> | <span data-ttu-id="4024a-207">"A", "B" (массив)</span><span class="sxs-lookup"><span data-stu-id="4024a-207">'A','B' (array)</span></span> |
| `CMD /CECHO :$AB`      | <span data-ttu-id="4024a-208">— аргумент</span><span class="sxs-lookup"><span data-stu-id="4024a-208">argument</span></span>   | <span data-ttu-id="4024a-209">": A B" (строка)</span><span class="sxs-lookup"><span data-stu-id="4024a-209">':A B' (string)</span></span> |

<span data-ttu-id="4024a-210">Символ "точка-анализ" ( `--%` ), представленный в powershell 3,0, направляет PowerShell для отключения от интерпретации входных данных как команд или выражений PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4024a-210">The stop-parsing symbol (`--%`), introduced in PowerShell 3.0, directs PowerShell to refrain from interpreting input as PowerShell commands or expressions.</span></span>

<span data-ttu-id="4024a-211">При вызове исполняемой программы в PowerShell перед программными аргументами поместите символ "точка-анализ".</span><span class="sxs-lookup"><span data-stu-id="4024a-211">When calling an executable program in PowerShell, place the stop-parsing symbol before the program arguments.</span></span> <span data-ttu-id="4024a-212">Этот метод гораздо проще, чем использование escape-символов для предотвращения неточной интерпретации.</span><span class="sxs-lookup"><span data-stu-id="4024a-212">This technique is much easier than using escape characters to prevent misinterpretation.</span></span>

<span data-ttu-id="4024a-213">Когда обнаруживает символ "точка-анализ", PowerShell считает остальные символы в строке как литералы.</span><span class="sxs-lookup"><span data-stu-id="4024a-213">When it encounters a stop-parsing symbol, PowerShell treats the remaining characters in the line as a literal.</span></span> <span data-ttu-id="4024a-214">Единственной интерпретацией, которую он выполняет, является замена значений для переменных среды, использующих стандартную нотацию Windows, например `%USERPROFILE%` .</span><span class="sxs-lookup"><span data-stu-id="4024a-214">The only interpretation it performs is to substitute values for environment variables that use standard Windows notation, such as `%USERPROFILE%`.</span></span>

<span data-ttu-id="4024a-215">Символ "точка-анализ" действует только до следующей новой строки или символа конвейера.</span><span class="sxs-lookup"><span data-stu-id="4024a-215">The stop-parsing symbol is effective only until the next newline or pipeline character.</span></span> <span data-ttu-id="4024a-216">Нельзя использовать символ продолжения ( `` ` `` ), чтобы расширить его действие, или использовать разделитель команд ( `;` ) для завершения его воздействия.</span><span class="sxs-lookup"><span data-stu-id="4024a-216">You cannot use a continuation character (`` ` ``) to extend its effect or use a command delimiter (`;`) to terminate its effect.</span></span>

<span data-ttu-id="4024a-217">Например, следующая команда вызывает программу **icacls** .</span><span class="sxs-lookup"><span data-stu-id="4024a-217">For example, the following command calls the **Icacls** program.</span></span>

```powershell
icacls X:\VMS /grant Dom\HVAdmin:(CI)(OI)F
```

<span data-ttu-id="4024a-218">Чтобы выполнить эту команду в PowerShell 2,0, необходимо использовать escape-символы, чтобы запретить PowerShell правильно интерпретировать круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="4024a-218">To run this command in PowerShell 2.0, you must use escape characters to prevent PowerShell from misinterpreting the parentheses.</span></span>

```powershell
icacls X:\VMS /grant Dom\HVAdmin:`(CI`)`(OI`)F
```

<span data-ttu-id="4024a-219">Начиная с PowerShell 3,0 можно использовать символ "прерывать анализ".</span><span class="sxs-lookup"><span data-stu-id="4024a-219">Beginning in PowerShell 3.0, you can use the stop-parsing symbol.</span></span>

```powershell
icacls X:\VMS --% /grant Dom\HVAdmin:(CI)(OI)F
```

<span data-ttu-id="4024a-220">PowerShell отправляет следующую командную строку в программу **icacls** :</span><span class="sxs-lookup"><span data-stu-id="4024a-220">PowerShell sends the following command string to the **Icacls** program:</span></span>

`X:\VMS /grant Dom\HVAdmin:(CI)(OI)F`

> [!NOTE]
> <span data-ttu-id="4024a-221">Символ для отмены синтаксического анализа предназначен только для платформ Windows.</span><span class="sxs-lookup"><span data-stu-id="4024a-221">The stop-parsing symbol only intended for use on Windows platforms.</span></span>

## <a name="see-also"></a><span data-ttu-id="4024a-222">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="4024a-222">SEE ALSO</span></span>

[<span data-ttu-id="4024a-223">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="4024a-223">about_Command_Syntax</span></span>](about_Command_Syntax.md)
