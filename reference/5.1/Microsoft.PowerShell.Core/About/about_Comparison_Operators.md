---
description: Описывает операторы, которые сравнивают значения в PowerShell.
Locale: en-US
ms.date: 12/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comparison_Operators
ms.openlocfilehash: ba671ae51d458a2e0074a85d4de859795c20a3d5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "97069909"
---
# <a name="about-comparison-operators"></a><span data-ttu-id="5b43a-103">Сведения об операторах сравнения</span><span class="sxs-lookup"><span data-stu-id="5b43a-103">About Comparison Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="5b43a-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="5b43a-104">Short description</span></span>
<span data-ttu-id="5b43a-105">Описывает операторы, которые сравнивают значения в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5b43a-105">Describes the operators that compare values in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="5b43a-106">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="5b43a-106">Long description</span></span>

<span data-ttu-id="5b43a-107">Операторы сравнения позволяют задавать условия для сравнения значений и поиска значений, соответствующих указанным шаблонам.</span><span class="sxs-lookup"><span data-stu-id="5b43a-107">Comparison operators let you specify conditions for comparing values and finding values that match specified patterns.</span></span> <span data-ttu-id="5b43a-108">Чтобы использовать оператор сравнения, укажите значения, которые необходимо сравнить с оператором, разделяющим эти значения.</span><span class="sxs-lookup"><span data-stu-id="5b43a-108">To use a comparison operator, specify the values that you want to compare together with an operator that separates these values.</span></span>

<span data-ttu-id="5b43a-109">PowerShell содержит следующие операторы сравнения:</span><span class="sxs-lookup"><span data-stu-id="5b43a-109">PowerShell includes the following comparison operators:</span></span>

| <span data-ttu-id="5b43a-110">Тип</span><span class="sxs-lookup"><span data-stu-id="5b43a-110">Type</span></span>        | <span data-ttu-id="5b43a-111">Операторы</span><span class="sxs-lookup"><span data-stu-id="5b43a-111">Operators</span></span>    | <span data-ttu-id="5b43a-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="5b43a-112">Description</span></span>                                 |
| ----------- | ------------ | --------------------------------------------|
| <span data-ttu-id="5b43a-113">Равенство</span><span class="sxs-lookup"><span data-stu-id="5b43a-113">Equality</span></span>    | <span data-ttu-id="5b43a-114">-eq</span><span class="sxs-lookup"><span data-stu-id="5b43a-114">-eq</span></span>          | <span data-ttu-id="5b43a-115">equals</span><span class="sxs-lookup"><span data-stu-id="5b43a-115">equals</span></span>                                      |
|             | <span data-ttu-id="5b43a-116">-ne</span><span class="sxs-lookup"><span data-stu-id="5b43a-116">-ne</span></span>          | <span data-ttu-id="5b43a-117">не равно</span><span class="sxs-lookup"><span data-stu-id="5b43a-117">not equals</span></span>                                  |
|             | <span data-ttu-id="5b43a-118">-gt</span><span class="sxs-lookup"><span data-stu-id="5b43a-118">-gt</span></span>          | <span data-ttu-id="5b43a-119">больше чем</span><span class="sxs-lookup"><span data-stu-id="5b43a-119">greater than</span></span>                                |
|             | <span data-ttu-id="5b43a-120">-ge</span><span class="sxs-lookup"><span data-stu-id="5b43a-120">-ge</span></span>          | <span data-ttu-id="5b43a-121">больше или равно</span><span class="sxs-lookup"><span data-stu-id="5b43a-121">greater than or equal</span></span>                       |
|             | <span data-ttu-id="5b43a-122">-lt</span><span class="sxs-lookup"><span data-stu-id="5b43a-122">-lt</span></span>          | <span data-ttu-id="5b43a-123">меньше чем</span><span class="sxs-lookup"><span data-stu-id="5b43a-123">less than</span></span>                                   |
|             | <span data-ttu-id="5b43a-124">-le</span><span class="sxs-lookup"><span data-stu-id="5b43a-124">-le</span></span>          | <span data-ttu-id="5b43a-125">меньше или равно</span><span class="sxs-lookup"><span data-stu-id="5b43a-125">less than or equal</span></span>                          |
|             |              |                                             |
| <span data-ttu-id="5b43a-126">Matching</span><span class="sxs-lookup"><span data-stu-id="5b43a-126">Matching</span></span>    | <span data-ttu-id="5b43a-127">-like</span><span class="sxs-lookup"><span data-stu-id="5b43a-127">-like</span></span>        | <span data-ttu-id="5b43a-128">Возвращает значение true, если строка соответствует подстановочному знаку</span><span class="sxs-lookup"><span data-stu-id="5b43a-128">Returns true when string matches wildcard</span></span>   |
|             |              | <span data-ttu-id="5b43a-129">pattern</span><span class="sxs-lookup"><span data-stu-id="5b43a-129">pattern</span></span>                                     |
|             | <span data-ttu-id="5b43a-130">-notlike</span><span class="sxs-lookup"><span data-stu-id="5b43a-130">-notlike</span></span>     | <span data-ttu-id="5b43a-131">Возвращает значение true, если строка не соответствует</span><span class="sxs-lookup"><span data-stu-id="5b43a-131">Returns true when string does not match</span></span>     |
|             |              | <span data-ttu-id="5b43a-132">Шаблон подстановочного знака</span><span class="sxs-lookup"><span data-stu-id="5b43a-132">wildcard pattern</span></span>                            |
|             | <span data-ttu-id="5b43a-133">-match</span><span class="sxs-lookup"><span data-stu-id="5b43a-133">-match</span></span>       | <span data-ttu-id="5b43a-134">Возвращает значение true, если строка соответствует регулярному выражению</span><span class="sxs-lookup"><span data-stu-id="5b43a-134">Returns true when string matches regex</span></span>      |
|             |              | <span data-ttu-id="5b43a-135">пакет $matches содержит совпадающие строки</span><span class="sxs-lookup"><span data-stu-id="5b43a-135">pattern; $matches contains matching strings</span></span> |
|             | <span data-ttu-id="5b43a-136">-notmatch</span><span class="sxs-lookup"><span data-stu-id="5b43a-136">-notmatch</span></span>    | <span data-ttu-id="5b43a-137">Возвращает значение true, если строка не соответствует</span><span class="sxs-lookup"><span data-stu-id="5b43a-137">Returns true when string does not match</span></span>     |
|             |              | <span data-ttu-id="5b43a-138">шаблон регулярного выражения; $matches содержит сопоставление</span><span class="sxs-lookup"><span data-stu-id="5b43a-138">regex pattern; $matches contains matching</span></span>   |
|             |              | <span data-ttu-id="5b43a-139">строки;</span><span class="sxs-lookup"><span data-stu-id="5b43a-139">strings</span></span>                                     |
|             |              |                                             |
| <span data-ttu-id="5b43a-140">Containment</span><span class="sxs-lookup"><span data-stu-id="5b43a-140">Containment</span></span> | <span data-ttu-id="5b43a-141">-contains</span><span class="sxs-lookup"><span data-stu-id="5b43a-141">-contains</span></span>    | <span data-ttu-id="5b43a-142">Возвращает значение true, если содержалось ссылочное значение</span><span class="sxs-lookup"><span data-stu-id="5b43a-142">Returns true when reference value contained</span></span> |
|             |              | <span data-ttu-id="5b43a-143">в коллекции</span><span class="sxs-lookup"><span data-stu-id="5b43a-143">in a collection</span></span>                             |
|             | <span data-ttu-id="5b43a-144">-notcontains</span><span class="sxs-lookup"><span data-stu-id="5b43a-144">-notcontains</span></span> | <span data-ttu-id="5b43a-145">Возвращает значение true, если значение ссылки не</span><span class="sxs-lookup"><span data-stu-id="5b43a-145">Returns true when reference value not</span></span>       |
|             |              | <span data-ttu-id="5b43a-146">содержится в коллекции</span><span class="sxs-lookup"><span data-stu-id="5b43a-146">contained in a collection</span></span>                   |
|             | <span data-ttu-id="5b43a-147">-in</span><span class="sxs-lookup"><span data-stu-id="5b43a-147">-in</span></span>          | <span data-ttu-id="5b43a-148">Возвращает значение true, если значение теста содержится в элементе</span><span class="sxs-lookup"><span data-stu-id="5b43a-148">Returns true when test value contained in a</span></span> |
|             |              | <span data-ttu-id="5b43a-149">коллекция</span><span class="sxs-lookup"><span data-stu-id="5b43a-149">collection</span></span>                                  |
|             | <span data-ttu-id="5b43a-150">-notin</span><span class="sxs-lookup"><span data-stu-id="5b43a-150">-notin</span></span>       | <span data-ttu-id="5b43a-151">Возвращает значение true, если тестовое значение не содержится</span><span class="sxs-lookup"><span data-stu-id="5b43a-151">Returns true when test value not contained</span></span>  |
|             |              | <span data-ttu-id="5b43a-152">в коллекции</span><span class="sxs-lookup"><span data-stu-id="5b43a-152">in a collection</span></span>                             |
|             |              |                                             |
| <span data-ttu-id="5b43a-153">Замена</span><span class="sxs-lookup"><span data-stu-id="5b43a-153">Replacement</span></span> | <span data-ttu-id="5b43a-154">-Replace</span><span class="sxs-lookup"><span data-stu-id="5b43a-154">-replace</span></span>     | <span data-ttu-id="5b43a-155">Заменяет шаблон строки</span><span class="sxs-lookup"><span data-stu-id="5b43a-155">Replaces a string pattern</span></span>                   |
|             |              |                                             |
| <span data-ttu-id="5b43a-156">Тип</span><span class="sxs-lookup"><span data-stu-id="5b43a-156">Type</span></span>        | <span data-ttu-id="5b43a-157">— имеет</span><span class="sxs-lookup"><span data-stu-id="5b43a-157">-is</span></span>          | <span data-ttu-id="5b43a-158">Возвращает значение true, если оба объекта одинаковы</span><span class="sxs-lookup"><span data-stu-id="5b43a-158">Returns true if both object are the same</span></span>    |
|             |              | <span data-ttu-id="5b43a-159">тип</span><span class="sxs-lookup"><span data-stu-id="5b43a-159">type</span></span>                                        |
|             | <span data-ttu-id="5b43a-160">-IsNot</span><span class="sxs-lookup"><span data-stu-id="5b43a-160">-isnot</span></span>       | <span data-ttu-id="5b43a-161">Возвращает значение true, если объекты не совпадают</span><span class="sxs-lookup"><span data-stu-id="5b43a-161">Returns true if the objects are not the same</span></span>|
|             |              | <span data-ttu-id="5b43a-162">тип</span><span class="sxs-lookup"><span data-stu-id="5b43a-162">type</span></span>                                        |

<span data-ttu-id="5b43a-163">По умолчанию все операторы сравнения не учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="5b43a-163">By default, all comparison operators are case-insensitive.</span></span> <span data-ttu-id="5b43a-164">Чтобы выполнить оператор сравнения с учетом регистра, перед именем оператора введите `c` .</span><span class="sxs-lookup"><span data-stu-id="5b43a-164">To make a comparison operator case-sensitive, precede the operator name with a `c`.</span></span> <span data-ttu-id="5b43a-165">Например, версия с учетом регистра `-eq` — `-ceq` .</span><span class="sxs-lookup"><span data-stu-id="5b43a-165">For example, the case-sensitive version of `-eq` is `-ceq`.</span></span> <span data-ttu-id="5b43a-166">Чтобы явно сделать регистр без учета регистра, перед оператором следует использовать `i` .</span><span class="sxs-lookup"><span data-stu-id="5b43a-166">To make the case-insensitivity explicit, precede the operator with an `i`.</span></span> <span data-ttu-id="5b43a-167">Например, явная версия без учета регистра `-eq` — `-ieq` .</span><span class="sxs-lookup"><span data-stu-id="5b43a-167">For example, the explicitly case-insensitive version of `-eq` is `-ieq`.</span></span>

<span data-ttu-id="5b43a-168">Если входные данные оператора являются скалярным значением, операторы сравнения возвращают логическое значение.</span><span class="sxs-lookup"><span data-stu-id="5b43a-168">When the input to an operator is a scalar value, comparison operators return a Boolean value.</span></span> <span data-ttu-id="5b43a-169">Если входные данные представляют собой коллекцию значений, то операторы сравнения возвращают все совпадающие значения.</span><span class="sxs-lookup"><span data-stu-id="5b43a-169">When the input is a collection of values, the comparison operators return any matching values.</span></span> <span data-ttu-id="5b43a-170">Если в коллекции нет совпадений, операторы сравнения возвращают пустой массив.</span><span class="sxs-lookup"><span data-stu-id="5b43a-170">If there are no matches in a collection, comparison operators return an empty array.</span></span>

```powershell
PS> (1, 2 -eq 3).GetType().FullName
System.Object[]
```

<span data-ttu-id="5b43a-171">Исключениями являются операторы включения, операторы in и операторы типа, которые всегда возвращают **логическое** значение.</span><span class="sxs-lookup"><span data-stu-id="5b43a-171">The exceptions are the containment operators, the In operators, and the type operators, which always return a **Boolean** value.</span></span>

> [!NOTE]
> <span data-ttu-id="5b43a-172">Если необходимо сравнить значение с `$null` , необходимо разместить `$null` в левой части сравнения.</span><span class="sxs-lookup"><span data-stu-id="5b43a-172">If you need to compare a value to `$null` you should put `$null` on the left-hand side of the comparison.</span></span> <span data-ttu-id="5b43a-173">При сравнении `$null` с **объектом []** результат равен **false** , поскольку объект сравнения является массивом.</span><span class="sxs-lookup"><span data-stu-id="5b43a-173">When you compare `$null` to an **Object[]** the result is **False** because the comparison object is an array.</span></span> <span data-ttu-id="5b43a-174">При сравнении массива со `$null` значением сравнения отфильтровывает все значения, `$null` хранящиеся в массиве.</span><span class="sxs-lookup"><span data-stu-id="5b43a-174">When you compare an array to `$null`, the comparison filters out any `$null` values stored in the array.</span></span> <span data-ttu-id="5b43a-175">Пример:</span><span class="sxs-lookup"><span data-stu-id="5b43a-175">For example:</span></span>
>
> ```powershell
> PS> $null -ne $null, "hello"
> True
> PS> $null, "hello" -ne $null
> hello
> ```

## <a name="equality-operators"></a><span data-ttu-id="5b43a-176">Операторы равенства</span><span class="sxs-lookup"><span data-stu-id="5b43a-176">Equality operators</span></span>

<span data-ttu-id="5b43a-177">Операторы равенства ( `-eq` , `-ne` ) возвращают значение true или совпадения, если одно или несколько входных значений идентичны заданному шаблону.</span><span class="sxs-lookup"><span data-stu-id="5b43a-177">The equality operators (`-eq`, `-ne`) return a value of TRUE or the matches when one or more of the input values is identical to the specified pattern.</span></span> <span data-ttu-id="5b43a-178">Весь шаблон должен соответствовать всему значению.</span><span class="sxs-lookup"><span data-stu-id="5b43a-178">The entire pattern must match an entire value.</span></span>

<span data-ttu-id="5b43a-179">Пример</span><span class="sxs-lookup"><span data-stu-id="5b43a-179">Example:</span></span>

### <a name="-eq"></a><span data-ttu-id="5b43a-180">-eq</span><span class="sxs-lookup"><span data-stu-id="5b43a-180">-eq</span></span>

<span data-ttu-id="5b43a-181">Описание: равно.</span><span class="sxs-lookup"><span data-stu-id="5b43a-181">Description: Equal to.</span></span> <span data-ttu-id="5b43a-182">Содержит идентичное значение.</span><span class="sxs-lookup"><span data-stu-id="5b43a-182">Includes an identical value.</span></span>

<span data-ttu-id="5b43a-183">Пример</span><span class="sxs-lookup"><span data-stu-id="5b43a-183">Example:</span></span>

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

### <a name="-ne"></a><span data-ttu-id="5b43a-184">-ne</span><span class="sxs-lookup"><span data-stu-id="5b43a-184">-ne</span></span>

<span data-ttu-id="5b43a-185">Описание: не равно.</span><span class="sxs-lookup"><span data-stu-id="5b43a-185">Description: Not equal to.</span></span> <span data-ttu-id="5b43a-186">Содержит другое значение.</span><span class="sxs-lookup"><span data-stu-id="5b43a-186">Includes a different value.</span></span>

<span data-ttu-id="5b43a-187">Пример</span><span class="sxs-lookup"><span data-stu-id="5b43a-187">Example:</span></span>

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

### <a name="-gt"></a><span data-ttu-id="5b43a-188">-gt</span><span class="sxs-lookup"><span data-stu-id="5b43a-188">-gt</span></span>

<span data-ttu-id="5b43a-189">Описание: "больше чем".</span><span class="sxs-lookup"><span data-stu-id="5b43a-189">Description: Greater-than.</span></span>

<span data-ttu-id="5b43a-190">Пример</span><span class="sxs-lookup"><span data-stu-id="5b43a-190">Example:</span></span>

```powershell
PS> 8 -gt 6
True

PS> 7, 8, 9 -gt 8
9
```

> [!NOTE]
> <span data-ttu-id="5b43a-191">Это не следует путать с `>` оператором "больше" во многих других языках программирования.</span><span class="sxs-lookup"><span data-stu-id="5b43a-191">This should not to be confused with `>`, the greater-than operator in many other programming languages.</span></span> <span data-ttu-id="5b43a-192">В PowerShell `>` используется для перенаправления.</span><span class="sxs-lookup"><span data-stu-id="5b43a-192">In PowerShell, `>` is used for redirection.</span></span> <span data-ttu-id="5b43a-193">Дополнительные сведения см. в разделе [About_redirection](about_Redirection.md#potential-confusion-with-comparison-operators).</span><span class="sxs-lookup"><span data-stu-id="5b43a-193">For more information, see [About_redirection](about_Redirection.md#potential-confusion-with-comparison-operators).</span></span>

### <a name="-ge"></a><span data-ttu-id="5b43a-194">-ge</span><span class="sxs-lookup"><span data-stu-id="5b43a-194">-ge</span></span>

<span data-ttu-id="5b43a-195">Описание: больше или равно.</span><span class="sxs-lookup"><span data-stu-id="5b43a-195">Description: Greater-than or equal to.</span></span>

<span data-ttu-id="5b43a-196">Пример</span><span class="sxs-lookup"><span data-stu-id="5b43a-196">Example:</span></span>

```powershell
PS> 8 -ge 8
True

PS> 7, 8, 9 -ge 8
8
9
```

### <a name="-lt"></a><span data-ttu-id="5b43a-197">-lt</span><span class="sxs-lookup"><span data-stu-id="5b43a-197">-lt</span></span>

<span data-ttu-id="5b43a-198">Описание: "меньше чем".</span><span class="sxs-lookup"><span data-stu-id="5b43a-198">Description: Less-than.</span></span>

<span data-ttu-id="5b43a-199">Пример</span><span class="sxs-lookup"><span data-stu-id="5b43a-199">Example:</span></span>

```powershell

PS> 8 -lt 6
False

PS> 7, 8, 9 -lt 8
7
```

### <a name="-le"></a><span data-ttu-id="5b43a-200">-le</span><span class="sxs-lookup"><span data-stu-id="5b43a-200">-le</span></span>

<span data-ttu-id="5b43a-201">Описание: меньше или равно.</span><span class="sxs-lookup"><span data-stu-id="5b43a-201">Description: Less-than or equal to.</span></span>

<span data-ttu-id="5b43a-202">Пример</span><span class="sxs-lookup"><span data-stu-id="5b43a-202">Example:</span></span>

```powershell
PS> 6 -le 8
True

PS> 7, 8, 9 -le 8
7
8
```

## <a name="matching-operators"></a><span data-ttu-id="5b43a-203">Соответствующие операторы</span><span class="sxs-lookup"><span data-stu-id="5b43a-203">Matching operators</span></span>

<span data-ttu-id="5b43a-204">Операторы LIKE ( `-like` и `-notlike` ) находят элементы, которые соответствуют или не соответствуют указанному шаблону с помощью выражений с подстановочными знаками.</span><span class="sxs-lookup"><span data-stu-id="5b43a-204">The like operators (`-like` and `-notlike`) find elements that match or do not match a specified pattern using wildcard expressions.</span></span>

<span data-ttu-id="5b43a-205">Синтаксис:</span><span class="sxs-lookup"><span data-stu-id="5b43a-205">The syntax is:</span></span>

```powershell
<string[]> -like <wildcard-expression>
<string[]> -notlike <wildcard-expression>
```

<span data-ttu-id="5b43a-206">Операторы match ( `-match` и `-notmatch` ) находят элементы, которые соответствуют или не соответствуют заданному шаблону с помощью регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="5b43a-206">The match operators (`-match` and `-notmatch`) find elements that match or do not match a specified pattern using regular expressions.</span></span>

<span data-ttu-id="5b43a-207">Операторы match заполняют `$Matches` автоматическую переменную, если вход (левый аргумент) к оператору является одним скалярным объектом.</span><span class="sxs-lookup"><span data-stu-id="5b43a-207">The match operators populate the `$Matches` automatic variable when the input (the left-side argument) to the operator is a single scalar object.</span></span> <span data-ttu-id="5b43a-208">Если входные данные скалярны, `-match` `-notmatch` операторы и возвращают логическое значение и присвойте значение `$Matches` автоматической переменной соответствующим компонентам аргумента.</span><span class="sxs-lookup"><span data-stu-id="5b43a-208">When the input is scalar, the `-match` and `-notmatch` operators return a Boolean value and set the value of the `$Matches` automatic variable to the matched components of the argument.</span></span>

<span data-ttu-id="5b43a-209">Синтаксис:</span><span class="sxs-lookup"><span data-stu-id="5b43a-209">The syntax is:</span></span>

```powershell
<string[]> -match <regular-expression>
<string[]> -notmatch <regular-expression>
```

### <a name="-like"></a><span data-ttu-id="5b43a-210">-like</span><span class="sxs-lookup"><span data-stu-id="5b43a-210">-like</span></span>

<span data-ttu-id="5b43a-211">Описание: совпадение с использованием подстановочного знака ( \* ).</span><span class="sxs-lookup"><span data-stu-id="5b43a-211">Description: Match using the wildcard character (\*).</span></span>

<span data-ttu-id="5b43a-212">Пример</span><span class="sxs-lookup"><span data-stu-id="5b43a-212">Example:</span></span>

```powershell
PS> "PowerShell" -like "*shell"
True

PS> "PowerShell", "Server" -like "*shell"
PowerShell
```

### <a name="-notlike"></a><span data-ttu-id="5b43a-213">-notlike</span><span class="sxs-lookup"><span data-stu-id="5b43a-213">-notlike</span></span>

<span data-ttu-id="5b43a-214">Описание: не совпадает с подстановочным знаком ( \* ).</span><span class="sxs-lookup"><span data-stu-id="5b43a-214">Description: Does not match using the wildcard character (\*).</span></span>

<span data-ttu-id="5b43a-215">Пример</span><span class="sxs-lookup"><span data-stu-id="5b43a-215">Example:</span></span>

```powershell
PS> "PowerShell" -notlike "*shell"
False

PS> "PowerShell", "Server" -notlike "*shell"
Server
```

### <a name="-match"></a><span data-ttu-id="5b43a-216">-match</span><span class="sxs-lookup"><span data-stu-id="5b43a-216">-match</span></span>

<span data-ttu-id="5b43a-217">Описание: соответствует строке с помощью регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="5b43a-217">Description: Matches a string using regular expressions.</span></span> <span data-ttu-id="5b43a-218">Если входные данные скалярны, он заполняет `$Matches` автоматическую переменную.</span><span class="sxs-lookup"><span data-stu-id="5b43a-218">When the input is scalar, it populates the `$Matches` automatic variable.</span></span>

<span data-ttu-id="5b43a-219">Если входные данные являются коллекцией, `-match` `-notmatch` операторы и возвращают соответствующие члены этой коллекции, но оператор не заполняет `$Matches` переменную.</span><span class="sxs-lookup"><span data-stu-id="5b43a-219">If the input is a collection, the `-match` and `-notmatch` operators return the matching members of that collection, but the operator does not populate the `$Matches` variable.</span></span>

<span data-ttu-id="5b43a-220">Например, следующая команда отправляет коллекцию строк `-match` оператору.</span><span class="sxs-lookup"><span data-stu-id="5b43a-220">For example, the following command submits a collection of strings to the `-match` operator.</span></span> <span data-ttu-id="5b43a-221">`-match`Оператор возвращает элементы в коллекции, которые соответствуют.</span><span class="sxs-lookup"><span data-stu-id="5b43a-221">The `-match` operator returns the items in the collection that match.</span></span> <span data-ttu-id="5b43a-222">Он не заполняет `$Matches` автоматическую переменную.</span><span class="sxs-lookup"><span data-stu-id="5b43a-222">It does not populate the `$Matches` automatic variable.</span></span>

```powershell
PS> "Sunday", "Monday", "Tuesday" -match "sun"
Sunday

PS> $Matches
PS>
```

<span data-ttu-id="5b43a-223">В отличие от этого, следующая команда отправляет в оператор одну строку `-match` .</span><span class="sxs-lookup"><span data-stu-id="5b43a-223">In contrast, the following command submits a single string to the `-match` operator.</span></span> <span data-ttu-id="5b43a-224">`-match`Оператор возвращает логическое значение и заполняет `$Matches` автоматическую переменную.</span><span class="sxs-lookup"><span data-stu-id="5b43a-224">The `-match` operator returns a Boolean value and populates the `$Matches` automatic variable.</span></span> <span data-ttu-id="5b43a-225">`$Matches`Автоматическая переменная является хэш- **таблицей**.</span><span class="sxs-lookup"><span data-stu-id="5b43a-225">The `$Matches` automatic variable is a **Hashtable**.</span></span> <span data-ttu-id="5b43a-226">Если группирование или захват не используются, заполняется только один ключ.</span><span class="sxs-lookup"><span data-stu-id="5b43a-226">If no grouping or capturing is used, only one key is populated.</span></span>
<span data-ttu-id="5b43a-227">`0`Ключ представляет весь совпадающий текст.</span><span class="sxs-lookup"><span data-stu-id="5b43a-227">The `0` key represents all text that was matched.</span></span> <span data-ttu-id="5b43a-228">Дополнительные сведения о группировании и записи с помощью регулярных выражений см. в разделе [about_Regular_Expressions](about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="5b43a-228">For more information about grouping and capturing using regular expressions, see [about_Regular_Expressions](about_Regular_Expressions.md).</span></span>

```powershell
PS> "Sunday" -match "sun"
True

PS> $Matches

Name                           Value
----                           -----
0                              Sun
```

<span data-ttu-id="5b43a-229">Важно отметить, что `$Matches` хэш-таблица будет содержать только первое вхождение любого совпадающего шаблона.</span><span class="sxs-lookup"><span data-stu-id="5b43a-229">It is important to note that the `$Matches` hashtable will only contain the first occurrence of any matching pattern.</span></span>

```powershell
PS> "Banana" -match "na"
True

PS> $Matches

Name                           Value
----                           -----
0                              na
```

> [!IMPORTANT]
> <span data-ttu-id="5b43a-230">`0`Ключ является **целым числом**.</span><span class="sxs-lookup"><span data-stu-id="5b43a-230">The `0` key is an **Integer**.</span></span> <span data-ttu-id="5b43a-231">Для доступа к сохраненному значению можно использовать любой метод **Hashtable** .</span><span class="sxs-lookup"><span data-stu-id="5b43a-231">You can use any **Hashtable** method to access the value stored.</span></span>
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

<span data-ttu-id="5b43a-232">`-notmatch`Оператор заполняет `$Matches` автоматическую переменную, если входные данные скалярны и результат имеет значение false, при обнаружении совпадения.</span><span class="sxs-lookup"><span data-stu-id="5b43a-232">The `-notmatch` operator populates the `$Matches` automatic variable when the input is scalar and the result is False, that it, when it detects a match.</span></span>

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

### <a name="-notmatch"></a><span data-ttu-id="5b43a-233">-notmatch</span><span class="sxs-lookup"><span data-stu-id="5b43a-233">-notmatch</span></span>

<span data-ttu-id="5b43a-234">Описание: не соответствует строке.</span><span class="sxs-lookup"><span data-stu-id="5b43a-234">Description: Does not match a string.</span></span> <span data-ttu-id="5b43a-235">Использует регулярные выражения.</span><span class="sxs-lookup"><span data-stu-id="5b43a-235">Uses regular expressions.</span></span> <span data-ttu-id="5b43a-236">Если входные данные скалярны, он заполняет `$Matches` автоматическую переменную.</span><span class="sxs-lookup"><span data-stu-id="5b43a-236">When the input is scalar, it populates the `$Matches` automatic variable.</span></span>

<span data-ttu-id="5b43a-237">Пример</span><span class="sxs-lookup"><span data-stu-id="5b43a-237">Example:</span></span>

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

## <a name="containment-operators"></a><span data-ttu-id="5b43a-238">Операторы вложения</span><span class="sxs-lookup"><span data-stu-id="5b43a-238">Containment operators</span></span>

<span data-ttu-id="5b43a-239">Операторы включения ( `-contains` и `-notcontains` ) похожи на операторы равенства.</span><span class="sxs-lookup"><span data-stu-id="5b43a-239">The containment operators (`-contains` and `-notcontains`) are similar to the equality operators.</span></span> <span data-ttu-id="5b43a-240">Однако операторы включения всегда возвращают логическое значение, даже если входные данные являются коллекцией.</span><span class="sxs-lookup"><span data-stu-id="5b43a-240">However, the containment operators always return a Boolean value, even when the input is a collection.</span></span>

<span data-ttu-id="5b43a-241">Кроме того, в отличие от операторов равенства, операторы вложения возвращают значение, как только они обнаруживают первое соответствие.</span><span class="sxs-lookup"><span data-stu-id="5b43a-241">Also, unlike the equality operators, the containment operators return a value as soon as they detect the first match.</span></span> <span data-ttu-id="5b43a-242">Операторы равенства оценивают все входные данные, а затем возвращают все совпадения в коллекции.</span><span class="sxs-lookup"><span data-stu-id="5b43a-242">The equality operators evaluate all input and then return all the matches in the collection.</span></span>

### <a name="-contains"></a><span data-ttu-id="5b43a-243">-contains</span><span class="sxs-lookup"><span data-stu-id="5b43a-243">-contains</span></span>

<span data-ttu-id="5b43a-244">Описание: оператор вложения.</span><span class="sxs-lookup"><span data-stu-id="5b43a-244">Description: Containment operator.</span></span> <span data-ttu-id="5b43a-245">Сообщает, включает ли коллекция ссылочных значений одно тестовое значение.</span><span class="sxs-lookup"><span data-stu-id="5b43a-245">Tells whether a collection of reference values includes a single test value.</span></span> <span data-ttu-id="5b43a-246">Всегда возвращает логическое значение.</span><span class="sxs-lookup"><span data-stu-id="5b43a-246">Always returns a Boolean value.</span></span> <span data-ttu-id="5b43a-247">Возвращает значение TRUE, только если тестовое значение точно совпадает по меньшей мере с одним из ссылочных значений.</span><span class="sxs-lookup"><span data-stu-id="5b43a-247">Returns TRUE only when the test value exactly matches at least one of the reference values.</span></span>

<span data-ttu-id="5b43a-248">Если тестовое значение является коллекцией, оператор Contains использует равенство ссылок.</span><span class="sxs-lookup"><span data-stu-id="5b43a-248">When the test value is a collection, the Contains operator uses reference equality.</span></span> <span data-ttu-id="5b43a-249">Он возвращает значение TRUE, только если одно из ссылочных значений является одним и тем же экземпляром объекта тестового значения.</span><span class="sxs-lookup"><span data-stu-id="5b43a-249">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="5b43a-250">В очень большой коллекции `-contains` оператор возвращает результаты быстрее, чем оператор Equal to.</span><span class="sxs-lookup"><span data-stu-id="5b43a-250">In a very large collection, the `-contains` operator returns results quicker than the equal to operator.</span></span>

<span data-ttu-id="5b43a-251">Синтаксис:</span><span class="sxs-lookup"><span data-stu-id="5b43a-251">Syntax:</span></span>

`<Reference-values> -contains <Test-value>`

<span data-ttu-id="5b43a-252">Примеры:</span><span class="sxs-lookup"><span data-stu-id="5b43a-252">Examples:</span></span>

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

### <a name="-notcontains"></a><span data-ttu-id="5b43a-253">-notcontains</span><span class="sxs-lookup"><span data-stu-id="5b43a-253">-notcontains</span></span>

<span data-ttu-id="5b43a-254">Описание: оператор вложения.</span><span class="sxs-lookup"><span data-stu-id="5b43a-254">Description: Containment operator.</span></span> <span data-ttu-id="5b43a-255">Сообщает, включает ли коллекция ссылочных значений одно тестовое значение.</span><span class="sxs-lookup"><span data-stu-id="5b43a-255">Tells whether a collection of reference values includes a single test value.</span></span> <span data-ttu-id="5b43a-256">Всегда возвращает логическое значение.</span><span class="sxs-lookup"><span data-stu-id="5b43a-256">Always returns a Boolean value.</span></span> <span data-ttu-id="5b43a-257">Возвращает значение TRUE, если тестовое значение не является точным соответствием по крайней мере одному из значений ссылок.</span><span class="sxs-lookup"><span data-stu-id="5b43a-257">Returns TRUE when the test value is not an exact matches for at least one of the reference values.</span></span>

<span data-ttu-id="5b43a-258">Если тестовое значение является коллекцией, оператор NotContains использует равенство ссылок.</span><span class="sxs-lookup"><span data-stu-id="5b43a-258">When the test value is a collection, the NotContains operator uses reference equality.</span></span>

<span data-ttu-id="5b43a-259">Синтаксис:</span><span class="sxs-lookup"><span data-stu-id="5b43a-259">Syntax:</span></span>

`<Reference-values> -notcontains <Test-value>`

<span data-ttu-id="5b43a-260">Примеры:</span><span class="sxs-lookup"><span data-stu-id="5b43a-260">Examples:</span></span>

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

### <a name="-in"></a><span data-ttu-id="5b43a-261">-in</span><span class="sxs-lookup"><span data-stu-id="5b43a-261">-in</span></span>

<span data-ttu-id="5b43a-262">Описание: в операторе.</span><span class="sxs-lookup"><span data-stu-id="5b43a-262">Description: In operator.</span></span> <span data-ttu-id="5b43a-263">Указывает, отображается ли тестовое значение в коллекции ссылочных значений.</span><span class="sxs-lookup"><span data-stu-id="5b43a-263">Tells whether a test value appears in a collection of reference values.</span></span> <span data-ttu-id="5b43a-264">Всегда возвращает как логическое значение.</span><span class="sxs-lookup"><span data-stu-id="5b43a-264">Always return as Boolean value.</span></span> <span data-ttu-id="5b43a-265">Возвращает значение TRUE, только если тестовое значение точно совпадает по меньшей мере с одним из ссылочных значений.</span><span class="sxs-lookup"><span data-stu-id="5b43a-265">Returns TRUE only when the test value exactly matches at least one of the reference values.</span></span>

<span data-ttu-id="5b43a-266">Если тестовое значение является коллекцией, оператор in использует равенство ссылок.</span><span class="sxs-lookup"><span data-stu-id="5b43a-266">When the test value is a collection, the In operator uses reference equality.</span></span>
<span data-ttu-id="5b43a-267">Он возвращает значение TRUE, только если одно из ссылочных значений является одним и тем же экземпляром объекта тестового значения.</span><span class="sxs-lookup"><span data-stu-id="5b43a-267">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="5b43a-268">`-in`Оператор появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="5b43a-268">The `-in` operator was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="5b43a-269">Синтаксис:</span><span class="sxs-lookup"><span data-stu-id="5b43a-269">Syntax:</span></span>

`<Test-value> -in <Reference-values>`

<span data-ttu-id="5b43a-270">Примеры:</span><span class="sxs-lookup"><span data-stu-id="5b43a-270">Examples:</span></span>

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

### <a name="-notin"></a><span data-ttu-id="5b43a-271">-notin</span><span class="sxs-lookup"><span data-stu-id="5b43a-271">-notin</span></span>

<span data-ttu-id="5b43a-272">Описание: указывает, отображается ли тестовое значение в коллекции ссылочных значений.</span><span class="sxs-lookup"><span data-stu-id="5b43a-272">Description: Tells whether a test value appears in a collection of reference values.</span></span> <span data-ttu-id="5b43a-273">Всегда возвращает логическое значение.</span><span class="sxs-lookup"><span data-stu-id="5b43a-273">Always returns a Boolean value.</span></span> <span data-ttu-id="5b43a-274">Возвращает значение TRUE, если тестовое значение не является точным соответствием по крайней мере одному из значений ссылок.</span><span class="sxs-lookup"><span data-stu-id="5b43a-274">Returns TRUE when the test value is not an exact match for at least one of the reference values.</span></span>

<span data-ttu-id="5b43a-275">Если тестовое значение является коллекцией, оператор in использует равенство ссылок.</span><span class="sxs-lookup"><span data-stu-id="5b43a-275">When the test value is a collection, the In operator uses reference equality.</span></span>
<span data-ttu-id="5b43a-276">Он возвращает значение TRUE, только если одно из ссылочных значений является одним и тем же экземпляром объекта тестового значения.</span><span class="sxs-lookup"><span data-stu-id="5b43a-276">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="5b43a-277">`-notin`Оператор появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="5b43a-277">The `-notin` operator was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="5b43a-278">Синтаксис:</span><span class="sxs-lookup"><span data-stu-id="5b43a-278">Syntax:</span></span>

`<Test-value> -notin <Reference-values>`

<span data-ttu-id="5b43a-279">Примеры:</span><span class="sxs-lookup"><span data-stu-id="5b43a-279">Examples:</span></span>

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

## <a name="replacement-operator"></a><span data-ttu-id="5b43a-280">Оператор замены</span><span class="sxs-lookup"><span data-stu-id="5b43a-280">Replacement Operator</span></span>

<span data-ttu-id="5b43a-281">`-replace`Оператор имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="5b43a-281">The `-replace` operator has the following syntax:</span></span>

`<input> -replace <original>, <substitute>`

<span data-ttu-id="5b43a-282">`<original>`Заполнитель — это регулярное выражение, соответствующее заменяемым символам.</span><span class="sxs-lookup"><span data-stu-id="5b43a-282">The `<original>` placeholder is a regular expression matching the characters to be replaced.</span></span> <span data-ttu-id="5b43a-283">`<substitute>`Заполнитель — это строка литерала, которая заменяет их.</span><span class="sxs-lookup"><span data-stu-id="5b43a-283">The `<substitute>` placeholder is a literal string that replaces them.</span></span>

<span data-ttu-id="5b43a-284">Оператор заменяет все или часть значения указанным значением с помощью регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="5b43a-284">The operator replaces all or part of a value with the specified value using regular expressions.</span></span> <span data-ttu-id="5b43a-285">Оператор можно использовать для многих административных задач, таких как переименование файлов.</span><span class="sxs-lookup"><span data-stu-id="5b43a-285">You can use the operator for many administrative tasks, such as renaming files.</span></span> <span data-ttu-id="5b43a-286">Например, следующая команда изменяет расширения имен файлов всех `.txt` файлов на `.log` :</span><span class="sxs-lookup"><span data-stu-id="5b43a-286">For example, the following command changes the file name extensions of all `.txt` files to `.log`:</span></span>

```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.name -replace '\.txt$','.log' }
```

### <a name="case-sensitive-matches"></a><span data-ttu-id="5b43a-287">Совпадения с учетом регистра</span><span class="sxs-lookup"><span data-stu-id="5b43a-287">Case-sensitive matches</span></span>

<span data-ttu-id="5b43a-288">По умолчанию `-replace` оператор не учитывает регистр.</span><span class="sxs-lookup"><span data-stu-id="5b43a-288">By default, the `-replace` operator is case-insensitive.</span></span> <span data-ttu-id="5b43a-289">Чтобы сделать его чувствительным к регистру, используйте `-creplace` .</span><span class="sxs-lookup"><span data-stu-id="5b43a-289">To make it case sensitive, use `-creplace`.</span></span> <span data-ttu-id="5b43a-290">Чтобы явно сделать регистр без учета регистра, используйте `-ireplace` .</span><span class="sxs-lookup"><span data-stu-id="5b43a-290">To make it explicitly case-insensitive, use `-ireplace`.</span></span>

<span data-ttu-id="5b43a-291">Рассмотрим следующие примеры:</span><span class="sxs-lookup"><span data-stu-id="5b43a-291">Consider the following examples:</span></span>

```powershell
PS> "book" -replace "B", "C"
Cook
```

```powershell
PS> "book" -ireplace "B", "C"
Cook
```

```powershell
PS> "book" -creplace "B", "C"
book
```

### <a name="substitutions-in-regular-expressions"></a><span data-ttu-id="5b43a-292">Подстановки в регулярных выражениях</span><span class="sxs-lookup"><span data-stu-id="5b43a-292">Substitutions in regular expressions</span></span>

<span data-ttu-id="5b43a-293">Можно также использовать регулярные выражения для динамической замены текста с помощью захваченных групп и подстановок.</span><span class="sxs-lookup"><span data-stu-id="5b43a-293">It is also possible to use regular expressions to dynamically replace text using capturing groups, and substitutions.</span></span> <span data-ttu-id="5b43a-294">На группы записи можно ссылаться в `<substitute>` строке, используя знак доллара ( `$` ) перед идентификатором группы.</span><span class="sxs-lookup"><span data-stu-id="5b43a-294">Capture groups can be referenced in the `<substitute>` string using the dollar sign (`$`) character before the group identifier.</span></span>

<span data-ttu-id="5b43a-295">На группы захвата можно ссылаться по **номеру** или **имени**</span><span class="sxs-lookup"><span data-stu-id="5b43a-295">Capture groups can be referenced by **Number** or **Name**</span></span>

- <span data-ttu-id="5b43a-296">По **числу** групп записи нумеруются слева направо.</span><span class="sxs-lookup"><span data-stu-id="5b43a-296">By **Number** - Capturing Groups are numbered from left to right.</span></span>

  ```powershell
  PS> "John D. Smith" -replace "(\w+) (\w+)\. (\w+)", '$1.$2.$3@contoso.com'
  John.D.Smith@contoso.com
  ```

- <span data-ttu-id="5b43a-297">По именам групп также можно ссылаться **по имени.**</span><span class="sxs-lookup"><span data-stu-id="5b43a-297">By **Name** - Capturing Groups can also be referenced by name.</span></span>

  ```powershell
  PS> "CONTOSO\Administrator" -replace '\w+\\(?<user>\w+)', 'FABRIKAM\${user}'
  FABRIKAM\Administrator
  ```

> [!WARNING]
> <span data-ttu-id="5b43a-298">Поскольку `$` символ используется в расширении строки, необходимо использовать литеральные строки или Escape- `$` символ.</span><span class="sxs-lookup"><span data-stu-id="5b43a-298">Since the `$` character is used in string expansion, you must use literal strings or escape the `$` character.</span></span>
>
> ```powershell
> PS> 'Hello World' -replace '(\w+) \w+', "`$1 Universe"
> Hello Universe
> ```
>
> <span data-ttu-id="5b43a-299">Кроме того, поскольку `$` символ используется в подстановке, необходимо экранировать все экземпляры в строке.</span><span class="sxs-lookup"><span data-stu-id="5b43a-299">Additionally, since the `$` character is used in substitution, you must escape any instances in your string.</span></span>
>
> ```powershell
> PS> '5.72' -replace '(.+)', '$$$1'
> $5.72
> ```

<span data-ttu-id="5b43a-300">Дополнительные сведения см. в разделе [about_Regular_Expressions](about_Regular_Expressions.md) и [подстановки в регулярных выражениях](/dotnet/standard/base-types/substitutions-in-regular-expressions) .</span><span class="sxs-lookup"><span data-stu-id="5b43a-300">To learn more see [about_Regular_Expressions](about_Regular_Expressions.md) and [Substitutions in Regular Expressions](/dotnet/standard/base-types/substitutions-in-regular-expressions)</span></span>

### <a name="substituting-in-a-collection"></a><span data-ttu-id="5b43a-301">Подстановка в коллекции</span><span class="sxs-lookup"><span data-stu-id="5b43a-301">Substituting in a collection</span></span>

<span data-ttu-id="5b43a-302">Если `<input>` `-replace` оператор to является коллекцией, PowerShell применяет замену к каждому значению в коллекции.</span><span class="sxs-lookup"><span data-stu-id="5b43a-302">When the `<input>` to the `-replace` operator is a collection, PowerShell applies the replacement to every value in the collection.</span></span> <span data-ttu-id="5b43a-303">Пример:</span><span class="sxs-lookup"><span data-stu-id="5b43a-303">For example:</span></span>

```powershell
"B1","B2","B3","B4","B5" -replace "B", 'a'
a1
a2
a3
a4
a5
```

## <a name="type-comparison"></a><span data-ttu-id="5b43a-304">Сравнение типов</span><span class="sxs-lookup"><span data-stu-id="5b43a-304">Type comparison</span></span>

<span data-ttu-id="5b43a-305">Операторы сравнения типов ( `-is` и `-isnot` ) используются для определения того, является ли объект конкретным типом.</span><span class="sxs-lookup"><span data-stu-id="5b43a-305">The type comparison operators (`-is` and `-isnot`) are used to determine if an object is a specific type.</span></span>

### <a name="-is"></a><span data-ttu-id="5b43a-306">— имеет</span><span class="sxs-lookup"><span data-stu-id="5b43a-306">-is</span></span>

<span data-ttu-id="5b43a-307">Синтаксис:</span><span class="sxs-lookup"><span data-stu-id="5b43a-307">Syntax:</span></span>

`<object> -is <type reference>`

<span data-ttu-id="5b43a-308">Пример</span><span class="sxs-lookup"><span data-stu-id="5b43a-308">Example:</span></span>

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -is [int]
True
PS> $a -is $b.GetType()
False
```

### <a name="-isnot"></a><span data-ttu-id="5b43a-309">-IsNot</span><span class="sxs-lookup"><span data-stu-id="5b43a-309">-isnot</span></span>

<span data-ttu-id="5b43a-310">Синтаксис:</span><span class="sxs-lookup"><span data-stu-id="5b43a-310">Syntax:</span></span>

`<object> -isnot <type reference>`

<span data-ttu-id="5b43a-311">Пример</span><span class="sxs-lookup"><span data-stu-id="5b43a-311">Example:</span></span>

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -isnot $b.GetType()
True
PS> $b -isnot [int]
True
```

## <a name="see-also"></a><span data-ttu-id="5b43a-312">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5b43a-312">See also</span></span>

- [<span data-ttu-id="5b43a-313">about_Operators</span><span class="sxs-lookup"><span data-stu-id="5b43a-313">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="5b43a-314">about_Regular_Expressions</span><span class="sxs-lookup"><span data-stu-id="5b43a-314">about_Regular_Expressions</span></span>](about_Regular_Expressions.md)
- [<span data-ttu-id="5b43a-315">about_Wildcards</span><span class="sxs-lookup"><span data-stu-id="5b43a-315">about_Wildcards</span></span>](about_Wildcards.md)
- [<span data-ttu-id="5b43a-316">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="5b43a-316">Compare-Object</span></span>](xref:Microsoft.PowerShell.Utility.Compare-Object)
- [<span data-ttu-id="5b43a-317">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="5b43a-317">Foreach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)
- [<span data-ttu-id="5b43a-318">Where-Object</span><span class="sxs-lookup"><span data-stu-id="5b43a-318">Where-Object</span></span>](xref:Microsoft.PowerShell.Core.Where-Object)
