---
description: Описывает операторы, которые сравнивают значения в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comparison_Operators
ms.openlocfilehash: b6076e20ad3ecbe9f2def157bb20bdb3bee5b7ad
ms.sourcegitcommit: c9e56ec489522c706b8d6b8733f3f015d6d7e893
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "93232930"
---
# <a name="about-comparison-operators"></a><span data-ttu-id="90eec-104">Сведения об операторах сравнения</span><span class="sxs-lookup"><span data-stu-id="90eec-104">About Comparison Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="90eec-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="90eec-105">Short description</span></span>
<span data-ttu-id="90eec-106">Описывает операторы, которые сравнивают значения в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90eec-106">Describes the operators that compare values in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="90eec-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="90eec-107">Long description</span></span>

<span data-ttu-id="90eec-108">Операторы сравнения позволяют задавать условия для сравнения значений и поиска значений, соответствующих указанным шаблонам.</span><span class="sxs-lookup"><span data-stu-id="90eec-108">Comparison operators let you specify conditions for comparing values and finding values that match specified patterns.</span></span> <span data-ttu-id="90eec-109">Чтобы использовать оператор сравнения, укажите значения, которые необходимо сравнить с оператором, разделяющим эти значения.</span><span class="sxs-lookup"><span data-stu-id="90eec-109">To use a comparison operator, specify the values that you want to compare together with an operator that separates these values.</span></span>

<span data-ttu-id="90eec-110">PowerShell содержит следующие операторы сравнения:</span><span class="sxs-lookup"><span data-stu-id="90eec-110">PowerShell includes the following comparison operators:</span></span>

| <span data-ttu-id="90eec-111">Тип</span><span class="sxs-lookup"><span data-stu-id="90eec-111">Type</span></span>        | <span data-ttu-id="90eec-112">Операторы</span><span class="sxs-lookup"><span data-stu-id="90eec-112">Operators</span></span>    | <span data-ttu-id="90eec-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="90eec-113">Description</span></span>                                 |
| ----------- | ------------ | --------------------------------------------|
| <span data-ttu-id="90eec-114">Равенство</span><span class="sxs-lookup"><span data-stu-id="90eec-114">Equality</span></span>    | <span data-ttu-id="90eec-115">-eq</span><span class="sxs-lookup"><span data-stu-id="90eec-115">-eq</span></span>          | <span data-ttu-id="90eec-116">равно</span><span class="sxs-lookup"><span data-stu-id="90eec-116">equals</span></span>                                      |
|             | <span data-ttu-id="90eec-117">-ne</span><span class="sxs-lookup"><span data-stu-id="90eec-117">-ne</span></span>          | <span data-ttu-id="90eec-118">не равно</span><span class="sxs-lookup"><span data-stu-id="90eec-118">not equals</span></span>                                  |
|             | <span data-ttu-id="90eec-119">-gt</span><span class="sxs-lookup"><span data-stu-id="90eec-119">-gt</span></span>          | <span data-ttu-id="90eec-120">больше чем</span><span class="sxs-lookup"><span data-stu-id="90eec-120">greater than</span></span>                                |
|             | <span data-ttu-id="90eec-121">-ge</span><span class="sxs-lookup"><span data-stu-id="90eec-121">-ge</span></span>          | <span data-ttu-id="90eec-122">больше или равно</span><span class="sxs-lookup"><span data-stu-id="90eec-122">greater than or equal</span></span>                       |
|             | <span data-ttu-id="90eec-123">-lt</span><span class="sxs-lookup"><span data-stu-id="90eec-123">-lt</span></span>          | <span data-ttu-id="90eec-124">меньше чем</span><span class="sxs-lookup"><span data-stu-id="90eec-124">less than</span></span>                                   |
|             | <span data-ttu-id="90eec-125">-le</span><span class="sxs-lookup"><span data-stu-id="90eec-125">-le</span></span>          | <span data-ttu-id="90eec-126">меньше или равно</span><span class="sxs-lookup"><span data-stu-id="90eec-126">less than or equal</span></span>                          |
|             |              |                                             |
| <span data-ttu-id="90eec-127">Matching</span><span class="sxs-lookup"><span data-stu-id="90eec-127">Matching</span></span>    | <span data-ttu-id="90eec-128">-like</span><span class="sxs-lookup"><span data-stu-id="90eec-128">-like</span></span>        | <span data-ttu-id="90eec-129">Возвращает значение true, если строка соответствует подстановочному знаку</span><span class="sxs-lookup"><span data-stu-id="90eec-129">Returns true when string matches wildcard</span></span>   |
|             |              | <span data-ttu-id="90eec-130">pattern</span><span class="sxs-lookup"><span data-stu-id="90eec-130">pattern</span></span>                                     |
|             | <span data-ttu-id="90eec-131">-notlike</span><span class="sxs-lookup"><span data-stu-id="90eec-131">-notlike</span></span>     | <span data-ttu-id="90eec-132">Возвращает значение true, если строка не соответствует</span><span class="sxs-lookup"><span data-stu-id="90eec-132">Returns true when string does not match</span></span>     |
|             |              | <span data-ttu-id="90eec-133">Шаблон подстановочного знака</span><span class="sxs-lookup"><span data-stu-id="90eec-133">wildcard pattern</span></span>                            |
|             | <span data-ttu-id="90eec-134">-match</span><span class="sxs-lookup"><span data-stu-id="90eec-134">-match</span></span>       | <span data-ttu-id="90eec-135">Возвращает значение true, если строка соответствует регулярному выражению</span><span class="sxs-lookup"><span data-stu-id="90eec-135">Returns true when string matches regex</span></span>      |
|             |              | <span data-ttu-id="90eec-136">пакет $matches содержит совпадающие строки</span><span class="sxs-lookup"><span data-stu-id="90eec-136">pattern; $matches contains matching strings</span></span> |
|             | <span data-ttu-id="90eec-137">-notmatch</span><span class="sxs-lookup"><span data-stu-id="90eec-137">-notmatch</span></span>    | <span data-ttu-id="90eec-138">Возвращает значение true, если строка не соответствует</span><span class="sxs-lookup"><span data-stu-id="90eec-138">Returns true when string does not match</span></span>     |
|             |              | <span data-ttu-id="90eec-139">шаблон регулярного выражения; $matches содержит сопоставление</span><span class="sxs-lookup"><span data-stu-id="90eec-139">regex pattern; $matches contains matching</span></span>   |
|             |              | <span data-ttu-id="90eec-140">строки;</span><span class="sxs-lookup"><span data-stu-id="90eec-140">strings</span></span>                                     |
|             |              |                                             |
| <span data-ttu-id="90eec-141">Containment</span><span class="sxs-lookup"><span data-stu-id="90eec-141">Containment</span></span> | <span data-ttu-id="90eec-142">-contains</span><span class="sxs-lookup"><span data-stu-id="90eec-142">-contains</span></span>    | <span data-ttu-id="90eec-143">Возвращает значение true, если содержалось ссылочное значение</span><span class="sxs-lookup"><span data-stu-id="90eec-143">Returns true when reference value contained</span></span> |
|             |              | <span data-ttu-id="90eec-144">в коллекции</span><span class="sxs-lookup"><span data-stu-id="90eec-144">in a collection</span></span>                             |
|             | <span data-ttu-id="90eec-145">-notcontains</span><span class="sxs-lookup"><span data-stu-id="90eec-145">-notcontains</span></span> | <span data-ttu-id="90eec-146">Возвращает значение true, если значение ссылки не</span><span class="sxs-lookup"><span data-stu-id="90eec-146">Returns true when reference value not</span></span>       |
|             |              | <span data-ttu-id="90eec-147">содержится в коллекции</span><span class="sxs-lookup"><span data-stu-id="90eec-147">contained in a collection</span></span>                   |
|             | <span data-ttu-id="90eec-148">-in</span><span class="sxs-lookup"><span data-stu-id="90eec-148">-in</span></span>          | <span data-ttu-id="90eec-149">Возвращает значение true, если значение теста содержится в элементе</span><span class="sxs-lookup"><span data-stu-id="90eec-149">Returns true when test value contained in a</span></span> |
|             |              | <span data-ttu-id="90eec-150">коллекция</span><span class="sxs-lookup"><span data-stu-id="90eec-150">collection</span></span>                                  |
|             | <span data-ttu-id="90eec-151">-notin</span><span class="sxs-lookup"><span data-stu-id="90eec-151">-notin</span></span>       | <span data-ttu-id="90eec-152">Возвращает значение true, если тестовое значение не содержится</span><span class="sxs-lookup"><span data-stu-id="90eec-152">Returns true when test value not contained</span></span>  |
|             |              | <span data-ttu-id="90eec-153">в коллекции</span><span class="sxs-lookup"><span data-stu-id="90eec-153">in a collection</span></span>                             |
|             |              |                                             |
| <span data-ttu-id="90eec-154">Замена</span><span class="sxs-lookup"><span data-stu-id="90eec-154">Replacement</span></span> | <span data-ttu-id="90eec-155">-Replace</span><span class="sxs-lookup"><span data-stu-id="90eec-155">-replace</span></span>     | <span data-ttu-id="90eec-156">Заменяет шаблон строки</span><span class="sxs-lookup"><span data-stu-id="90eec-156">Replaces a string pattern</span></span>                   |
|             |              |                                             |
| <span data-ttu-id="90eec-157">Тип</span><span class="sxs-lookup"><span data-stu-id="90eec-157">Type</span></span>        | <span data-ttu-id="90eec-158">— имеет</span><span class="sxs-lookup"><span data-stu-id="90eec-158">-is</span></span>          | <span data-ttu-id="90eec-159">Возвращает значение true, если оба объекта одинаковы</span><span class="sxs-lookup"><span data-stu-id="90eec-159">Returns true if both object are the same</span></span>    |
|             |              | <span data-ttu-id="90eec-160">тип</span><span class="sxs-lookup"><span data-stu-id="90eec-160">type</span></span>                                        |
|             | <span data-ttu-id="90eec-161">-IsNot</span><span class="sxs-lookup"><span data-stu-id="90eec-161">-isnot</span></span>       | <span data-ttu-id="90eec-162">Возвращает значение true, если объекты не совпадают</span><span class="sxs-lookup"><span data-stu-id="90eec-162">Returns true if the objects are not the same</span></span>|
|             |              | <span data-ttu-id="90eec-163">тип</span><span class="sxs-lookup"><span data-stu-id="90eec-163">type</span></span>                                        |

<span data-ttu-id="90eec-164">По умолчанию все операторы сравнения не учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="90eec-164">By default, all comparison operators are case-insensitive.</span></span> <span data-ttu-id="90eec-165">Чтобы выполнить оператор сравнения с учетом регистра, перед именем оператора введите `c` .</span><span class="sxs-lookup"><span data-stu-id="90eec-165">To make a comparison operator case-sensitive, precede the operator name with a `c`.</span></span> <span data-ttu-id="90eec-166">Например, версия с учетом регистра `-eq` — `-ceq` .</span><span class="sxs-lookup"><span data-stu-id="90eec-166">For example, the case-sensitive version of `-eq` is `-ceq`.</span></span> <span data-ttu-id="90eec-167">Чтобы явно сделать регистр без учета регистра, перед оператором следует использовать `i` .</span><span class="sxs-lookup"><span data-stu-id="90eec-167">To make the case-insensitivity explicit, precede the operator with an `i`.</span></span> <span data-ttu-id="90eec-168">Например, явная версия без учета регистра `-eq` — `-ieq` .</span><span class="sxs-lookup"><span data-stu-id="90eec-168">For example, the explicitly case-insensitive version of `-eq` is `-ieq`.</span></span>

<span data-ttu-id="90eec-169">Если входные данные оператора являются скалярным значением, операторы сравнения возвращают логическое значение.</span><span class="sxs-lookup"><span data-stu-id="90eec-169">When the input to an operator is a scalar value, comparison operators return a Boolean value.</span></span> <span data-ttu-id="90eec-170">Если входные данные представляют собой коллекцию значений, то операторы сравнения возвращают все совпадающие значения.</span><span class="sxs-lookup"><span data-stu-id="90eec-170">When the input is a collection of values, the comparison operators return any matching values.</span></span> <span data-ttu-id="90eec-171">Если в коллекции нет совпадений, операторы сравнения возвращают пустой массив.</span><span class="sxs-lookup"><span data-stu-id="90eec-171">If there are no matches in a collection, comparison operators return an empty array.</span></span>

```powershell
PS> (1, 2 -eq 3).GetType().FullName
System.Object[]
```

<span data-ttu-id="90eec-172">Исключениями являются операторы включения, операторы in и операторы типа, которые всегда возвращают **логическое** значение.</span><span class="sxs-lookup"><span data-stu-id="90eec-172">The exceptions are the containment operators, the In operators, and the type operators, which always return a **Boolean** value.</span></span>

> [!NOTE]
> <span data-ttu-id="90eec-173">Если необходимо сравнить значение с `$null` , необходимо разместить `$null` в левой части сравнения.</span><span class="sxs-lookup"><span data-stu-id="90eec-173">If you need to compare a value to `$null` you should put `$null` on the left-hand side of the comparison.</span></span> <span data-ttu-id="90eec-174">При сравнении `$null` с **объектом []** результат равен **false** , поскольку объект сравнения является массивом.</span><span class="sxs-lookup"><span data-stu-id="90eec-174">When you compare `$null` to an **Object[]** the result is **False** because the comparison object is an array.</span></span> <span data-ttu-id="90eec-175">При сравнении массива со `$null` значением сравнения отфильтровывает все значения, `$null` хранящиеся в массиве.</span><span class="sxs-lookup"><span data-stu-id="90eec-175">When you compare an array to `$null`, the comparison filters out any `$null` values stored in the array.</span></span> <span data-ttu-id="90eec-176">Пример:</span><span class="sxs-lookup"><span data-stu-id="90eec-176">For example:</span></span>
>
> ```powershell
> PS> $null -ne $null, "hello"
> True
> PS> $null, "hello" -ne $null
> hello
> ```

### <a name="equality-operators"></a><span data-ttu-id="90eec-177">Операторы равенства</span><span class="sxs-lookup"><span data-stu-id="90eec-177">Equality Operators</span></span>

<span data-ttu-id="90eec-178">Операторы равенства ( `-eq` , `-ne` ) возвращают значение true или совпадения, если одно или несколько входных значений идентичны заданному шаблону.</span><span class="sxs-lookup"><span data-stu-id="90eec-178">The equality operators (`-eq`, `-ne`) return a value of TRUE or the matches when one or more of the input values is identical to the specified pattern.</span></span> <span data-ttu-id="90eec-179">Весь шаблон должен соответствовать всему значению.</span><span class="sxs-lookup"><span data-stu-id="90eec-179">The entire pattern must match an entire value.</span></span>

<span data-ttu-id="90eec-180">Пример</span><span class="sxs-lookup"><span data-stu-id="90eec-180">Example:</span></span>

#### <a name="-eq"></a><span data-ttu-id="90eec-181">-eq</span><span class="sxs-lookup"><span data-stu-id="90eec-181">-eq</span></span>

<span data-ttu-id="90eec-182">Описание: равно.</span><span class="sxs-lookup"><span data-stu-id="90eec-182">Description: Equal to.</span></span> <span data-ttu-id="90eec-183">Содержит идентичное значение.</span><span class="sxs-lookup"><span data-stu-id="90eec-183">Includes an identical value.</span></span>

<span data-ttu-id="90eec-184">Пример</span><span class="sxs-lookup"><span data-stu-id="90eec-184">Example:</span></span>

```powershell
PS> 2 -eq 2
True

PS> 2 -eq 3
False

PS> 1,2,3 -eq 2
2
PS> "abc" -eq "abc"
True

PS> "abc" -eq "abc", "def"
False

PS> "abc", "def" -eq "abc"
abc
```

#### <a name="-ne"></a><span data-ttu-id="90eec-185">-ne</span><span class="sxs-lookup"><span data-stu-id="90eec-185">-ne</span></span>

<span data-ttu-id="90eec-186">Описание: не равно.</span><span class="sxs-lookup"><span data-stu-id="90eec-186">Description: Not equal to.</span></span> <span data-ttu-id="90eec-187">Содержит другое значение.</span><span class="sxs-lookup"><span data-stu-id="90eec-187">Includes a different value.</span></span>

<span data-ttu-id="90eec-188">Пример</span><span class="sxs-lookup"><span data-stu-id="90eec-188">Example:</span></span>

```powershell
PS> "abc" -ne "def"
True

PS> "abc" -ne "abc"
False

PS> "abc" -ne "abc", "def"
True

PS> "abc", "def" -ne "abc"
def
```

#### <a name="-gt"></a><span data-ttu-id="90eec-189">-gt</span><span class="sxs-lookup"><span data-stu-id="90eec-189">-gt</span></span>

<span data-ttu-id="90eec-190">Описание: "больше чем".</span><span class="sxs-lookup"><span data-stu-id="90eec-190">Description: Greater-than.</span></span>

<span data-ttu-id="90eec-191">Пример</span><span class="sxs-lookup"><span data-stu-id="90eec-191">Example:</span></span>

```powershell
PS> 8 -gt 6
True

PS> 7, 8, 9 -gt 8
9
```

> [!NOTE]
> <span data-ttu-id="90eec-192">Это не следует путать с `>` оператором "больше" во многих других языках программирования.</span><span class="sxs-lookup"><span data-stu-id="90eec-192">This should not to be confused with `>`, the greater-than operator in many other programming languages.</span></span> <span data-ttu-id="90eec-193">В PowerShell `>` используется для перенаправления.</span><span class="sxs-lookup"><span data-stu-id="90eec-193">In PowerShell, `>` is used for redirection.</span></span> <span data-ttu-id="90eec-194">Дополнительные сведения см. в разделе [About_redirection](about_Redirection.md#potential-confusion-with-comparison-operators).</span><span class="sxs-lookup"><span data-stu-id="90eec-194">For more information, see [About_redirection](about_Redirection.md#potential-confusion-with-comparison-operators).</span></span>

#### <a name="-ge"></a><span data-ttu-id="90eec-195">-ge</span><span class="sxs-lookup"><span data-stu-id="90eec-195">-ge</span></span>

<span data-ttu-id="90eec-196">Описание: больше или равно.</span><span class="sxs-lookup"><span data-stu-id="90eec-196">Description: Greater-than or equal to.</span></span>

<span data-ttu-id="90eec-197">Пример</span><span class="sxs-lookup"><span data-stu-id="90eec-197">Example:</span></span>

```powershell
PS> 8 -ge 8
True

PS> 7, 8, 9 -ge 8
8
9
```

#### <a name="-lt"></a><span data-ttu-id="90eec-198">-lt</span><span class="sxs-lookup"><span data-stu-id="90eec-198">-lt</span></span>

<span data-ttu-id="90eec-199">Описание: "меньше чем".</span><span class="sxs-lookup"><span data-stu-id="90eec-199">Description: Less-than.</span></span>

<span data-ttu-id="90eec-200">Пример</span><span class="sxs-lookup"><span data-stu-id="90eec-200">Example:</span></span>

```powershell

PS> 8 -lt 6
False

PS> 7, 8, 9 -lt 8
7
```

#### <a name="-le"></a><span data-ttu-id="90eec-201">-le</span><span class="sxs-lookup"><span data-stu-id="90eec-201">-le</span></span>

<span data-ttu-id="90eec-202">Описание: меньше или равно.</span><span class="sxs-lookup"><span data-stu-id="90eec-202">Description: Less-than or equal to.</span></span>

<span data-ttu-id="90eec-203">Пример</span><span class="sxs-lookup"><span data-stu-id="90eec-203">Example:</span></span>

```powershell
PS> 6 -le 8
True

PS> 7, 8, 9 -le 8
7
8
```

### <a name="matching-operators"></a><span data-ttu-id="90eec-204">Соответствующие операторы</span><span class="sxs-lookup"><span data-stu-id="90eec-204">Matching Operators</span></span>

<span data-ttu-id="90eec-205">Операторы LIKE ( `-like` и `-notlike` ) находят элементы, которые соответствуют или не соответствуют указанному шаблону с помощью выражений с подстановочными знаками.</span><span class="sxs-lookup"><span data-stu-id="90eec-205">The like operators (`-like` and `-notlike`) find elements that match or do not match a specified pattern using wildcard expressions.</span></span>

<span data-ttu-id="90eec-206">Синтаксис:</span><span class="sxs-lookup"><span data-stu-id="90eec-206">The syntax is:</span></span>

```powershell
<string[]> -like <wildcard-expression>
<string[]> -notlike <wildcard-expression>
```

<span data-ttu-id="90eec-207">Операторы match ( `-match` и `-notmatch` ) находят элементы, которые соответствуют или не соответствуют заданному шаблону с помощью регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="90eec-207">The match operators (`-match` and `-notmatch`) find elements that match or do not match a specified pattern using regular expressions.</span></span>

<span data-ttu-id="90eec-208">Операторы match заполняют `$Matches` автоматическую переменную, если вход (левый аргумент) к оператору является одним скалярным объектом.</span><span class="sxs-lookup"><span data-stu-id="90eec-208">The match operators populate the `$Matches` automatic variable when the input (the left-side argument) to the operator is a single scalar object.</span></span> <span data-ttu-id="90eec-209">Если входные данные скалярны, `-match` `-notmatch` операторы и возвращают логическое значение и присвойте значение `$Matches` автоматической переменной соответствующим компонентам аргумента.</span><span class="sxs-lookup"><span data-stu-id="90eec-209">When the input is scalar, the `-match` and `-notmatch` operators return a Boolean value and set the value of the `$Matches` automatic variable to the matched components of the argument.</span></span>

<span data-ttu-id="90eec-210">Синтаксис:</span><span class="sxs-lookup"><span data-stu-id="90eec-210">The syntax is:</span></span>

```powershell
<string[]> -match <regular-expression>
<string[]> -notmatch <regular-expression>
```

#### <a name="-like"></a><span data-ttu-id="90eec-211">-like</span><span class="sxs-lookup"><span data-stu-id="90eec-211">-like</span></span>

<span data-ttu-id="90eec-212">Описание: совпадение с использованием подстановочного знака ( \* ).</span><span class="sxs-lookup"><span data-stu-id="90eec-212">Description: Match using the wildcard character (\*).</span></span>

<span data-ttu-id="90eec-213">Пример</span><span class="sxs-lookup"><span data-stu-id="90eec-213">Example:</span></span>

```powershell
PS> "PowerShell" -like "*shell"
True

PS> "PowerShell", "Server" -like "*shell"
PowerShell
```

#### <a name="-notlike"></a><span data-ttu-id="90eec-214">-notlike</span><span class="sxs-lookup"><span data-stu-id="90eec-214">-notlike</span></span>

<span data-ttu-id="90eec-215">Описание: не совпадает с подстановочным знаком ( \* ).</span><span class="sxs-lookup"><span data-stu-id="90eec-215">Description: Does not match using the wildcard character (\*).</span></span>

<span data-ttu-id="90eec-216">Пример</span><span class="sxs-lookup"><span data-stu-id="90eec-216">Example:</span></span>

```powershell
PS> "PowerShell" -notlike "*shell"
False

PS> "PowerShell", "Server" -notlike "*shell"
Server
```

### <a name="-match"></a><span data-ttu-id="90eec-217">-match</span><span class="sxs-lookup"><span data-stu-id="90eec-217">-match</span></span>

<span data-ttu-id="90eec-218">Описание: соответствует строке с помощью регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="90eec-218">Description: Matches a string using regular expressions.</span></span> <span data-ttu-id="90eec-219">Если входные данные скалярны, он заполняет `$Matches` автоматическую переменную.</span><span class="sxs-lookup"><span data-stu-id="90eec-219">When the input is scalar, it populates the `$Matches` automatic variable.</span></span>

<span data-ttu-id="90eec-220">Если входные данные являются коллекцией, `-match` `-notmatch` операторы и возвращают соответствующие члены этой коллекции, но оператор не заполняет `$Matches` переменную.</span><span class="sxs-lookup"><span data-stu-id="90eec-220">If the input is a collection, the `-match` and `-notmatch` operators return the matching members of that collection, but the operator does not populate the `$Matches` variable.</span></span>

<span data-ttu-id="90eec-221">Например, следующая команда отправляет коллекцию строк `-match` оператору.</span><span class="sxs-lookup"><span data-stu-id="90eec-221">For example, the following command submits a collection of strings to the `-match` operator.</span></span> <span data-ttu-id="90eec-222">`-match`Оператор возвращает элементы в коллекции, которые соответствуют.</span><span class="sxs-lookup"><span data-stu-id="90eec-222">The `-match` operator returns the items in the collection that match.</span></span> <span data-ttu-id="90eec-223">Он не заполняет `$Matches` автоматическую переменную.</span><span class="sxs-lookup"><span data-stu-id="90eec-223">It does not populate the `$Matches` automatic variable.</span></span>

```powershell
PS> "Sunday", "Monday", "Tuesday" -match "sun"
Sunday

PS> $Matches
PS>
```

<span data-ttu-id="90eec-224">В отличие от этого, следующая команда отправляет в оператор одну строку `-match` .</span><span class="sxs-lookup"><span data-stu-id="90eec-224">In contrast, the following command submits a single string to the `-match` operator.</span></span> <span data-ttu-id="90eec-225">`-match`Оператор возвращает логическое значение и заполняет `$Matches` автоматическую переменную.</span><span class="sxs-lookup"><span data-stu-id="90eec-225">The `-match` operator returns a Boolean value and populates the `$Matches` automatic variable.</span></span> <span data-ttu-id="90eec-226">`$Matches`Автоматическая переменная является хэш- **таблицей** .</span><span class="sxs-lookup"><span data-stu-id="90eec-226">The `$Matches` automatic variable is a **Hashtable** .</span></span> <span data-ttu-id="90eec-227">Если группирование или захват не используются, заполняется только один ключ.</span><span class="sxs-lookup"><span data-stu-id="90eec-227">If no grouping or capturing is used, only one key is populated.</span></span>
<span data-ttu-id="90eec-228">`0`Ключ представляет весь совпадающий текст.</span><span class="sxs-lookup"><span data-stu-id="90eec-228">The `0` key represents all text that was matched.</span></span> <span data-ttu-id="90eec-229">Дополнительные сведения о группировании и записи с помощью регулярных выражений см. в разделе [about_Regular_Expressions](about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="90eec-229">For more information about grouping and capturing using regular expressions, see [about_Regular_Expressions](about_Regular_Expressions.md).</span></span>

```powershell
PS> "Sunday" -match "sun"
True

PS> $Matches

Name                           Value
----                           -----
0                              Sun
```

<span data-ttu-id="90eec-230">Важно отметить, что `$Matches` хэш-таблица будет содержать только первое вхождение любого совпадающего шаблона.</span><span class="sxs-lookup"><span data-stu-id="90eec-230">It is important to note that the `$Matches` hashtable will only contain the first occurrence of any matching pattern.</span></span>

```powershell
PS> "Banana" -match "na"
True

PS> $Matches

Name                           Value
----                           -----
0                              na
```

> [!IMPORTANT]
> <span data-ttu-id="90eec-231">`0`Ключ является **целым числом** .</span><span class="sxs-lookup"><span data-stu-id="90eec-231">The `0` key is an **Integer** .</span></span> <span data-ttu-id="90eec-232">Для доступа к сохраненному значению можно использовать любой метод **Hashtable** .</span><span class="sxs-lookup"><span data-stu-id="90eec-232">You can use any **Hashtable** method to access the value stored.</span></span>
>
> ```powershell
> PS> "Good Dog" -match "Dog"
> True
>
> PS> $Matches[0]
> Dog
>
> PS> $Matches.Item(0)
> Dog
>
> PS> $Matches.0
> Dog
> ```

<span data-ttu-id="90eec-233">`-notmatch`Оператор заполняет `$Matches` автоматическую переменную, если входные данные скалярны и результат имеет значение false, при обнаружении совпадения.</span><span class="sxs-lookup"><span data-stu-id="90eec-233">The `-notmatch` operator populates the `$Matches` automatic variable when the input is scalar and the result is False, that it, when it detects a match.</span></span>

```powershell
PS> "Sunday" -notmatch "rain"
True

PS> $matches
PS>

PS> "Sunday" -notmatch "day"
False

PS> $matches

Name                           Value
----                           -----
0                              day
```

#### <a name="-notmatch"></a><span data-ttu-id="90eec-234">-notmatch</span><span class="sxs-lookup"><span data-stu-id="90eec-234">-notmatch</span></span>

<span data-ttu-id="90eec-235">Описание: не соответствует строке.</span><span class="sxs-lookup"><span data-stu-id="90eec-235">Description: Does not match a string.</span></span> <span data-ttu-id="90eec-236">Использует регулярные выражения.</span><span class="sxs-lookup"><span data-stu-id="90eec-236">Uses regular expressions.</span></span> <span data-ttu-id="90eec-237">Если входные данные скалярны, он заполняет `$Matches` автоматическую переменную.</span><span class="sxs-lookup"><span data-stu-id="90eec-237">When the input is scalar, it populates the `$Matches` automatic variable.</span></span>

<span data-ttu-id="90eec-238">Пример</span><span class="sxs-lookup"><span data-stu-id="90eec-238">Example:</span></span>

```powershell
PS> "Sunday" -notmatch "sun"
False

PS> $matches
Name Value
---- -----
0    sun

PS> "Sunday", "Monday" -notmatch "sun"
Monday
```

### <a name="containment-operators"></a><span data-ttu-id="90eec-239">Операторы вложения</span><span class="sxs-lookup"><span data-stu-id="90eec-239">Containment Operators</span></span>

<span data-ttu-id="90eec-240">Операторы включения ( `-contains` и `-notcontains` ) похожи на операторы равенства.</span><span class="sxs-lookup"><span data-stu-id="90eec-240">The containment operators (`-contains` and `-notcontains`) are similar to the equality operators.</span></span> <span data-ttu-id="90eec-241">Однако операторы включения всегда возвращают логическое значение, даже если входные данные являются коллекцией.</span><span class="sxs-lookup"><span data-stu-id="90eec-241">However, the containment operators always return a Boolean value, even when the input is a collection.</span></span>

<span data-ttu-id="90eec-242">Кроме того, в отличие от операторов равенства, операторы вложения возвращают значение, как только они обнаруживают первое соответствие.</span><span class="sxs-lookup"><span data-stu-id="90eec-242">Also, unlike the equality operators, the containment operators return a value as soon as they detect the first match.</span></span> <span data-ttu-id="90eec-243">Операторы равенства оценивают все входные данные, а затем возвращают все совпадения в коллекции.</span><span class="sxs-lookup"><span data-stu-id="90eec-243">The equality operators evaluate all input and then return all the matches in the collection.</span></span>

#### <a name="-contains"></a><span data-ttu-id="90eec-244">-contains</span><span class="sxs-lookup"><span data-stu-id="90eec-244">-contains</span></span>

<span data-ttu-id="90eec-245">Описание: оператор вложения.</span><span class="sxs-lookup"><span data-stu-id="90eec-245">Description: Containment operator.</span></span> <span data-ttu-id="90eec-246">Сообщает, включает ли коллекция ссылочных значений одно тестовое значение.</span><span class="sxs-lookup"><span data-stu-id="90eec-246">Tells whether a collection of reference values includes a single test value.</span></span> <span data-ttu-id="90eec-247">Всегда возвращает логическое значение.</span><span class="sxs-lookup"><span data-stu-id="90eec-247">Always returns a Boolean value.</span></span> <span data-ttu-id="90eec-248">Возвращает значение TRUE, только если тестовое значение точно совпадает по меньшей мере с одним из ссылочных значений.</span><span class="sxs-lookup"><span data-stu-id="90eec-248">Returns TRUE only when the test value exactly matches at least one of the reference values.</span></span>

<span data-ttu-id="90eec-249">Если тестовое значение является коллекцией, оператор Contains использует равенство ссылок.</span><span class="sxs-lookup"><span data-stu-id="90eec-249">When the test value is a collection, the Contains operator uses reference equality.</span></span> <span data-ttu-id="90eec-250">Он возвращает значение TRUE, только если одно из ссылочных значений является одним и тем же экземпляром объекта тестового значения.</span><span class="sxs-lookup"><span data-stu-id="90eec-250">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="90eec-251">В очень большой коллекции `-contains` оператор возвращает результаты быстрее, чем оператор Equal to.</span><span class="sxs-lookup"><span data-stu-id="90eec-251">In a very large collection, the `-contains` operator returns results quicker than the equal to operator.</span></span>

<span data-ttu-id="90eec-252">Синтаксис:</span><span class="sxs-lookup"><span data-stu-id="90eec-252">Syntax:</span></span>

`<Reference-values> -contains <Test-value>`

<span data-ttu-id="90eec-253">Примеры:</span><span class="sxs-lookup"><span data-stu-id="90eec-253">Examples:</span></span>

```powershell
PS> "abc", "def" -contains "def"
True

PS> "Windows", "PowerShell" -contains "Shell"
False  #Not an exact match

# Does the list of computers in $DomainServers include $ThisComputer?
PS> $DomainServers -contains $thisComputer
True

PS> "abc", "def", "ghi" -contains "abc", "def"
False

PS> $a = "abc", "def"
PS> "abc", "def", "ghi" -contains $a
False
PS> $a, "ghi" -contains $a
True
```

#### <a name="-notcontains"></a><span data-ttu-id="90eec-254">-notcontains</span><span class="sxs-lookup"><span data-stu-id="90eec-254">-notcontains</span></span>

<span data-ttu-id="90eec-255">Описание: оператор вложения.</span><span class="sxs-lookup"><span data-stu-id="90eec-255">Description: Containment operator.</span></span> <span data-ttu-id="90eec-256">Сообщает, включает ли коллекция ссылочных значений одно тестовое значение.</span><span class="sxs-lookup"><span data-stu-id="90eec-256">Tells whether a collection of reference values includes a single test value.</span></span> <span data-ttu-id="90eec-257">Всегда возвращает логическое значение.</span><span class="sxs-lookup"><span data-stu-id="90eec-257">Always returns a Boolean value.</span></span> <span data-ttu-id="90eec-258">Возвращает значение TRUE, если тестовое значение не является точным соответствием по крайней мере одному из значений ссылок.</span><span class="sxs-lookup"><span data-stu-id="90eec-258">Returns TRUE when the test value is not an exact matches for at least one of the reference values.</span></span>

<span data-ttu-id="90eec-259">Если тестовое значение является коллекцией, оператор NotContains использует равенство ссылок.</span><span class="sxs-lookup"><span data-stu-id="90eec-259">When the test value is a collection, the NotContains operator uses reference equality.</span></span>

<span data-ttu-id="90eec-260">Синтаксис:</span><span class="sxs-lookup"><span data-stu-id="90eec-260">Syntax:</span></span>

`<Reference-values> -notcontains <Test-value>`

<span data-ttu-id="90eec-261">Примеры:</span><span class="sxs-lookup"><span data-stu-id="90eec-261">Examples:</span></span>

```powershell
PS> "Windows", "PowerShell" -notcontains "Shell"
True  #Not an exact match

# Get cmdlet parameters, but exclude common parameters
function get-parms ($cmdlet)
{
    $Common = "Verbose", "Debug", "WarningAction", "WarningVariable",
      "ErrorAction", "ErrorVariable", "OutVariable", "OutBuffer"

    $allparms = (Get-Command $Cmdlet).parametersets |
      foreach {$_.Parameters} |
        foreach {$_.Name} | Sort-Object | Get-Unique

    $allparms | where {$Common -notcontains $_ }
}

# Find unapproved verbs in the functions in my module
PS> $ApprovedVerbs = Get-Verb | foreach {$_.verb}
PS> $myVerbs = Get-Command -Module MyModule | foreach {$_.verb}
PS> $myVerbs | where {$ApprovedVerbs -notcontains $_}
ForEach
Sort
Tee
Where
```

#### <a name="-in"></a><span data-ttu-id="90eec-262">-in</span><span class="sxs-lookup"><span data-stu-id="90eec-262">-in</span></span>

<span data-ttu-id="90eec-263">Описание: в операторе.</span><span class="sxs-lookup"><span data-stu-id="90eec-263">Description: In operator.</span></span> <span data-ttu-id="90eec-264">Указывает, отображается ли тестовое значение в коллекции ссылочных значений.</span><span class="sxs-lookup"><span data-stu-id="90eec-264">Tells whether a test value appears in a collection of reference values.</span></span> <span data-ttu-id="90eec-265">Всегда возвращает как логическое значение.</span><span class="sxs-lookup"><span data-stu-id="90eec-265">Always return as Boolean value.</span></span> <span data-ttu-id="90eec-266">Возвращает значение TRUE, только если тестовое значение точно совпадает по меньшей мере с одним из ссылочных значений.</span><span class="sxs-lookup"><span data-stu-id="90eec-266">Returns TRUE only when the test value exactly matches at least one of the reference values.</span></span>

<span data-ttu-id="90eec-267">Если тестовое значение является коллекцией, оператор in использует равенство ссылок.</span><span class="sxs-lookup"><span data-stu-id="90eec-267">When the test value is a collection, the In operator uses reference equality.</span></span>
<span data-ttu-id="90eec-268">Он возвращает значение TRUE, только если одно из ссылочных значений является одним и тем же экземпляром объекта тестового значения.</span><span class="sxs-lookup"><span data-stu-id="90eec-268">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="90eec-269">`-in`Оператор появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="90eec-269">The `-in` operator was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="90eec-270">Синтаксис:</span><span class="sxs-lookup"><span data-stu-id="90eec-270">Syntax:</span></span>

`<Test-value> -in <Reference-values>`

<span data-ttu-id="90eec-271">Примеры:</span><span class="sxs-lookup"><span data-stu-id="90eec-271">Examples:</span></span>

```powershell
PS> "def" -in "abc", "def"
True

PS> "Shell" -in "Windows", "PowerShell"
False  #Not an exact match

PS> "Windows" -in "Windows", "PowerShell"
True  #An exact match

PS> "Windows", "PowerShell" -in "Windows", "PowerShell", "ServerManager"
False  #Using reference equality

PS> $a = "Windows", "PowerShell"
PS> $a -in $a, "ServerManager"
True  #Using reference equality

# Does the list of computers in $DomainServers include $ThisComputer?
PS> $thisComputer -in  $domainServers
True
```

#### <a name="-notin"></a><span data-ttu-id="90eec-272">-notin</span><span class="sxs-lookup"><span data-stu-id="90eec-272">-notin</span></span>

<span data-ttu-id="90eec-273">Описание: указывает, отображается ли тестовое значение в коллекции ссылочных значений.</span><span class="sxs-lookup"><span data-stu-id="90eec-273">Description: Tells whether a test value appears in a collection of reference values.</span></span> <span data-ttu-id="90eec-274">Всегда возвращает логическое значение.</span><span class="sxs-lookup"><span data-stu-id="90eec-274">Always returns a Boolean value.</span></span> <span data-ttu-id="90eec-275">Возвращает значение TRUE, если тестовое значение не является точным соответствием по крайней мере одному из значений ссылок.</span><span class="sxs-lookup"><span data-stu-id="90eec-275">Returns TRUE when the test value is not an exact match for at least one of the reference values.</span></span>

<span data-ttu-id="90eec-276">Если тестовое значение является коллекцией, оператор in использует равенство ссылок.</span><span class="sxs-lookup"><span data-stu-id="90eec-276">When the test value is a collection, the In operator uses reference equality.</span></span>
<span data-ttu-id="90eec-277">Он возвращает значение TRUE, только если одно из ссылочных значений является одним и тем же экземпляром объекта тестового значения.</span><span class="sxs-lookup"><span data-stu-id="90eec-277">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="90eec-278">`-notin`Оператор появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="90eec-278">The `-notin` operator was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="90eec-279">Синтаксис:</span><span class="sxs-lookup"><span data-stu-id="90eec-279">Syntax:</span></span>

`<Test-value> -notin <Reference-values>`

<span data-ttu-id="90eec-280">Примеры:</span><span class="sxs-lookup"><span data-stu-id="90eec-280">Examples:</span></span>

```powershell
PS> "def" -notin "abc", "def"
False

PS> "ghi" -notin "abc", "def"
True

PS> "Shell" -notin "Windows", "PowerShell"
True  #Not an exact match

PS> "Windows" -notin "Windows", "PowerShell"
False  #An exact match

# Find unapproved verbs in the functions in my module
PS> $ApprovedVerbs = Get-Verb | foreach {$_.verb}
PS> $MyVerbs = Get-Command -Module MyModule | foreach {$_.verb}

PS> $MyVerbs | where {$_ -notin $ApprovedVerbs}
ForEach
Sort
Tee
Where
```

### <a name="replacement-operator"></a><span data-ttu-id="90eec-281">Оператор замены</span><span class="sxs-lookup"><span data-stu-id="90eec-281">Replacement Operator</span></span>

<span data-ttu-id="90eec-282">`-replace`Оператор заменяет все или часть значения указанным значением с помощью регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="90eec-282">The `-replace` operator replaces all or part of a value with the specified value using regular expressions.</span></span> <span data-ttu-id="90eec-283">Оператор можно использовать `-replace` для многих административных задач, таких как переименование файлов.</span><span class="sxs-lookup"><span data-stu-id="90eec-283">You can use the `-replace` operator for many administrative tasks, such as renaming files.</span></span> <span data-ttu-id="90eec-284">Например, следующая команда изменяет расширения имен файлов всех txt в log:</span><span class="sxs-lookup"><span data-stu-id="90eec-284">For example, the following command changes the file name extensions of all .txt files to .log:</span></span>

```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.name -replace '\.txt$','.log' }
```

<span data-ttu-id="90eec-285">Синтаксис `-replace` оператора выглядит следующим образом, где `<original>` заполнитель представляет заменяемые символы, а `<substitute>` заполнитель представляет символы, которые будут заменены:</span><span class="sxs-lookup"><span data-stu-id="90eec-285">The syntax of the `-replace` operator is as follows, where the `<original>` placeholder represents the characters to be replaced, and the `<substitute>` placeholder represents the characters that will replace them:</span></span>

`<input> <operator> <original>, <substitute>`

<span data-ttu-id="90eec-286">По умолчанию `-replace` оператор не учитывает регистр.</span><span class="sxs-lookup"><span data-stu-id="90eec-286">By default, the `-replace` operator is case-insensitive.</span></span> <span data-ttu-id="90eec-287">Чтобы сделать его чувствительным к регистру, используйте `-creplace` .</span><span class="sxs-lookup"><span data-stu-id="90eec-287">To make it case sensitive, use `-creplace`.</span></span> <span data-ttu-id="90eec-288">Чтобы явно сделать регистр без учета регистра, используйте `-ireplace` .</span><span class="sxs-lookup"><span data-stu-id="90eec-288">To make it explicitly case-insensitive, use `-ireplace`.</span></span>

<span data-ttu-id="90eec-289">Рассмотрим следующие примеры.</span><span class="sxs-lookup"><span data-stu-id="90eec-289">Consider the following examples:</span></span>

```powershell
PS> "book" -replace "B", "C"
```

```Output
Cook
```

```powershell
"book" -ireplace "B", "C"
```

```Output
Cook
```

```powershell
"book" -creplace "B", "C"
```

```Output
book
```

<span data-ttu-id="90eec-290">Можно также использовать регулярные выражения для динамической замены текста с помощью захваченных групп и подстановок.</span><span class="sxs-lookup"><span data-stu-id="90eec-290">It is also possible to use regular expressions to dynamically replace text using capturing groups, and substitutions.</span></span> <span data-ttu-id="90eec-291">Дополнительные сведения см. в разделе [about_Regular_Expressions](about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="90eec-291">For more information, see [about_Regular_Expressions](about_Regular_Expressions.md).</span></span>

#### <a name="substitutions-in-regular-expressions"></a><span data-ttu-id="90eec-292">Подстановки в регулярных выражениях</span><span class="sxs-lookup"><span data-stu-id="90eec-292">Substitutions in Regular Expressions</span></span>

<span data-ttu-id="90eec-293">Кроме того, в строке можно ссылаться на захваченные группы \<substitute\> .</span><span class="sxs-lookup"><span data-stu-id="90eec-293">Additionally, capturing groups can be referenced in the \<substitute\> string.</span></span>
<span data-ttu-id="90eec-294">Это делается с помощью `$` символа перед идентификатором группы.</span><span class="sxs-lookup"><span data-stu-id="90eec-294">This is done by using the `$` character before the group identifier.</span></span>

<span data-ttu-id="90eec-295">Два способа ссылки на группы захвата — **число** и **имя**</span><span class="sxs-lookup"><span data-stu-id="90eec-295">Two of the ways to reference capturing groups is by **Number** and by **Name**</span></span>

- <span data-ttu-id="90eec-296">По **числу** -
   захваченных групп нумеруются слева направо.</span><span class="sxs-lookup"><span data-stu-id="90eec-296">By **Number** -
Capturing Groups are numbered from left to right.</span></span>

  ```powershell
  "John D. Smith" -replace "(\w+) (\w+)\. (\w+)", '$1.$2.$3@contoso.com'
  ```

  ```Output
  John.D.Smith@contoso.com
  ```

- <span data-ttu-id="90eec-297">По **имени** -
   захваченные группы также могут ссылаться по имени.</span><span class="sxs-lookup"><span data-stu-id="90eec-297">By **Name** -
Capturing Groups can also be referenced by name.</span></span>

  ```powershell
  "CONTOSO\Administrator" -replace '\w+\\(?<user>\w+)', 'FABRIKAM\${user}'
  ```

  ```Output
  FABRIKOM\Administrator
  ```

> [!WARNING]
> <span data-ttu-id="90eec-298">Поскольку `$` символ используется в расширении строки, необходимо использовать литеральные строки с подстановкой или Escape- `$` символ.</span><span class="sxs-lookup"><span data-stu-id="90eec-298">Since the `$` character is used in string expansion, you will need to use literal strings with substitution, or escape the `$` character.</span></span>
>
> ```powershell
> 'Hello World' -replace '(\w+) \w+', "`$1 Universe"
> ```
>
> ```Output
> Hello Universe
> ```
>
> <span data-ttu-id="90eec-299">Кроме того, поскольку `$` символ используется в подстановке, необходимо будет экранировать все экземпляры в строке.</span><span class="sxs-lookup"><span data-stu-id="90eec-299">Additionally, since the `$` character is used in substitution, you will need to escape any instances in your string.</span></span>
>
> ```powershell
> '5.72' -replace '(.+)', '$$$1'
> ```
>
> ```Output
> $5.72
> ```

<span data-ttu-id="90eec-300">Дополнительные сведения см. в разделе [about_Regular_Expressions](about_Regular_Expressions.md) и [подстановки в регулярных выражениях](/dotnet/standard/base-types/substitutions-in-regular-expressions) .</span><span class="sxs-lookup"><span data-stu-id="90eec-300">To learn more see [about_Regular_Expressions](about_Regular_Expressions.md) and [Substitutions in Regular Expressions](/dotnet/standard/base-types/substitutions-in-regular-expressions)</span></span>

### <a name="type-comparison"></a><span data-ttu-id="90eec-301">Сравнение типов</span><span class="sxs-lookup"><span data-stu-id="90eec-301">Type comparison</span></span>

<span data-ttu-id="90eec-302">Операторы сравнения типов ( `-is` и `-isnot` ) используются для определения того, является ли объект конкретным типом.</span><span class="sxs-lookup"><span data-stu-id="90eec-302">The type comparison operators (`-is` and `-isnot`) are used to determine if an object is a specific type.</span></span>

#### <a name="-is"></a><span data-ttu-id="90eec-303">— имеет</span><span class="sxs-lookup"><span data-stu-id="90eec-303">-is</span></span>

<span data-ttu-id="90eec-304">Синтаксис:</span><span class="sxs-lookup"><span data-stu-id="90eec-304">Syntax:</span></span>

`<object> -is <type reference>`

<span data-ttu-id="90eec-305">Пример</span><span class="sxs-lookup"><span data-stu-id="90eec-305">Example:</span></span>

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -is [int]
True
PS> $a -is $b.GetType()
False
```

#### <a name="-isnot"></a><span data-ttu-id="90eec-306">-IsNot</span><span class="sxs-lookup"><span data-stu-id="90eec-306">-isnot</span></span>

<span data-ttu-id="90eec-307">Синтаксис:</span><span class="sxs-lookup"><span data-stu-id="90eec-307">Syntax:</span></span>

`<object> -isnot <type reference>`

<span data-ttu-id="90eec-308">Пример</span><span class="sxs-lookup"><span data-stu-id="90eec-308">Example:</span></span>

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -isnot $b.GetType()
True
PS> $b -isnot [int]
True
```

## <a name="see-also"></a><span data-ttu-id="90eec-309">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="90eec-309">SEE ALSO</span></span>

- [<span data-ttu-id="90eec-310">about_Operators</span><span class="sxs-lookup"><span data-stu-id="90eec-310">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="90eec-311">about_Regular_Expressions</span><span class="sxs-lookup"><span data-stu-id="90eec-311">about_Regular_Expressions</span></span>](about_Regular_Expressions.md)
- [<span data-ttu-id="90eec-312">about_Wildcards</span><span class="sxs-lookup"><span data-stu-id="90eec-312">about_Wildcards</span></span>](about_Wildcards.md)
- [<span data-ttu-id="90eec-313">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="90eec-313">Compare-Object</span></span>](xref:Microsoft.PowerShell.Utility.Compare-Object)
- [<span data-ttu-id="90eec-314">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="90eec-314">Foreach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)
- [<span data-ttu-id="90eec-315">Where-Object</span><span class="sxs-lookup"><span data-stu-id="90eec-315">Where-Object</span></span>](xref:Microsoft.PowerShell.Core.Where-Object)
