---
description: Описывает операторы, выполняющие арифметические действия в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 10/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arithmetic_operators?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Arithmetic_Operators
ms.openlocfilehash: c7885e31e4b5b661473d5241b6629bbe05810824
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231577"
---
# <a name="about-arithmetic-operators"></a><span data-ttu-id="0dfe5-104">Об арифметических операторах</span><span class="sxs-lookup"><span data-stu-id="0dfe5-104">About Arithmetic Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="0dfe5-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="0dfe5-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="0dfe5-106">Описывает операторы, выполняющие арифметические действия в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-106">Describes the operators that perform arithmetic in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="0dfe5-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="0dfe5-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="0dfe5-108">Арифметические операторы вычисляют числовые значения.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-108">Arithmetic operators calculate numeric values.</span></span> <span data-ttu-id="0dfe5-109">Можно использовать один или несколько арифметических операторов для добавления, вычитания, умножения и деления значений, а также для вычисления остатка (остатка от деления) операции деления.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-109">You can use one or more arithmetic operators to add, subtract, multiply, and divide values, and to calculate the remainder (modulus) of a division operation.</span></span>

<span data-ttu-id="0dfe5-110">Кроме того, оператор сложения ( `+` ) и оператор умножения ( `*` ) также работают с строками, массивами и хэш-таблицами.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-110">In addition, the addition operator (`+`) and multiplication operator (`*`) also operate on strings, arrays, and hash tables.</span></span> <span data-ttu-id="0dfe5-111">Оператор сложения объединяет входные данные.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-111">The addition operator concatenates the input.</span></span> <span data-ttu-id="0dfe5-112">Оператор умножения возвращает несколько копий входных данных.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-112">The multiplication operator returns multiple copies of the input.</span></span> <span data-ttu-id="0dfe5-113">Можно даже смешивать типы объектов в арифметическом операторе.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-113">You can even mix object types in an arithmetic statement.</span></span> <span data-ttu-id="0dfe5-114">Метод, используемый для вычисления инструкции, определяется типом самого левого объекта в выражении.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-114">The method that is used to evaluate the statement is determined by the type of the leftmost object in the expression.</span></span>

<span data-ttu-id="0dfe5-115">Начиная с PowerShell 2,0, все арифметические операторы работают с 64-разрядными числами.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-115">Beginning in PowerShell 2.0, all arithmetic operators work on 64-bit numbers.</span></span>

<span data-ttu-id="0dfe5-116">Начиная с PowerShell 3,0, `-shr` `-shl` для поддержки побитовых арифметических операций в PowerShell добавляются (Shift-Right) и (Shift-Left).</span><span class="sxs-lookup"><span data-stu-id="0dfe5-116">Beginning in PowerShell 3.0, the `-shr` (shift-right) and `-shl` (shift-left) are added to support bitwise arithmetic in PowerShell.</span></span>

<span data-ttu-id="0dfe5-117">PowerShell поддерживает следующие арифметические операторы:</span><span class="sxs-lookup"><span data-stu-id="0dfe5-117">PowerShell supports the following arithmetic operators:</span></span>

|<span data-ttu-id="0dfe5-118">Оператор</span><span class="sxs-lookup"><span data-stu-id="0dfe5-118">Operator</span></span>|<span data-ttu-id="0dfe5-119">Описание</span><span class="sxs-lookup"><span data-stu-id="0dfe5-119">Description</span></span>                       |<span data-ttu-id="0dfe5-120">Пример</span><span class="sxs-lookup"><span data-stu-id="0dfe5-120">Example</span></span>                      |
|--------|----------------------------------|-----------------------------|
| +      |<span data-ttu-id="0dfe5-121">Добавляет целые числа; объединяет</span><span class="sxs-lookup"><span data-stu-id="0dfe5-121">Adds integers; concatenates</span></span>       |`6 + 2`                      |
|        |<span data-ttu-id="0dfe5-122">строки, массивы и хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-122">strings, arrays, and hash tables.</span></span> |`"file" + "name"`            |
|        |                                  |`@(1, "one") + @(2.0, "two")`|
|        |                                  |`@{"one" = 1} + @{"two" = 2}`|
| -      |<span data-ttu-id="0dfe5-123">Вычитает одно значение из другого</span><span class="sxs-lookup"><span data-stu-id="0dfe5-123">Subtracts one value from another</span></span>  |`6 - 2`                      |
|        |<span data-ttu-id="0dfe5-124">value</span><span class="sxs-lookup"><span data-stu-id="0dfe5-124">value</span></span>                             |                             |
| -      |<span data-ttu-id="0dfe5-125">Делает число отрицательным числом</span><span class="sxs-lookup"><span data-stu-id="0dfe5-125">Makes a number a negative number</span></span>  |`-6`                         |
|        |                                  |`(Get-Date).AddDays(-1)`     |
| *      |<span data-ttu-id="0dfe5-126">Умножение чисел или копирование строк</span><span class="sxs-lookup"><span data-stu-id="0dfe5-126">Multiply numbers or copy strings</span></span>  |`6 * 2`                      |
|        |<span data-ttu-id="0dfe5-127">и массивов с указанным числом</span><span class="sxs-lookup"><span data-stu-id="0dfe5-127">and arrays the specified number</span></span>   |`@("!") * 4`                 |
|        |<span data-ttu-id="0dfe5-128">раз.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-128">of times.</span></span>                         |`"!" * 3`                    |
| /      |<span data-ttu-id="0dfe5-129">Производит деление двух значений.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-129">Divides two values.</span></span>               |`6 / 2`                      |
| %      |<span data-ttu-id="0dfe5-130">Модуль — возвращает остаток от</span><span class="sxs-lookup"><span data-stu-id="0dfe5-130">Modulus - returns the remainder of</span></span>|`7 % 2`                      |
|        |<span data-ttu-id="0dfe5-131">Операция деления.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-131">a division operation.</span></span>             |                             |
|<span data-ttu-id="0dfe5-132">-Band</span><span class="sxs-lookup"><span data-stu-id="0dfe5-132">-band</span></span>   |<span data-ttu-id="0dfe5-133">Побитовое И</span><span class="sxs-lookup"><span data-stu-id="0dfe5-133">Bitwise AND</span></span>                       |`5 -band 3`                  |
|<span data-ttu-id="0dfe5-134">-бнот</span><span class="sxs-lookup"><span data-stu-id="0dfe5-134">-bnot</span></span>   |<span data-ttu-id="0dfe5-135">Побитовое НЕ</span><span class="sxs-lookup"><span data-stu-id="0dfe5-135">Bitwise NOT</span></span>                       |`-bnot 5`                    |
|<span data-ttu-id="0dfe5-136">-Бор</span><span class="sxs-lookup"><span data-stu-id="0dfe5-136">-bor</span></span>    |<span data-ttu-id="0dfe5-137">Побитовое ИЛИ</span><span class="sxs-lookup"><span data-stu-id="0dfe5-137">Bitwise OR</span></span>                        |`5 -bor 0x03`                |
|<span data-ttu-id="0dfe5-138">-бксор</span><span class="sxs-lookup"><span data-stu-id="0dfe5-138">-bxor</span></span>   |<span data-ttu-id="0dfe5-139">Побитовое исключающее ИЛИ</span><span class="sxs-lookup"><span data-stu-id="0dfe5-139">Bitwise XOR</span></span>                       |`5 -bxor 3`                  |
|<span data-ttu-id="0dfe5-140">-Шл</span><span class="sxs-lookup"><span data-stu-id="0dfe5-140">-shl</span></span>    |<span data-ttu-id="0dfe5-141">Сдвигает биты влево</span><span class="sxs-lookup"><span data-stu-id="0dfe5-141">Shifts bits to the left</span></span>           |`102 -shl 2`                 |
|<span data-ttu-id="0dfe5-142">-SHR</span><span class="sxs-lookup"><span data-stu-id="0dfe5-142">-shr</span></span>    |<span data-ttu-id="0dfe5-143">Сдвигает биты вправо</span><span class="sxs-lookup"><span data-stu-id="0dfe5-143">Shifts bits to the right</span></span>          |`102 -shr 2`                 |

<span data-ttu-id="0dfe5-144">Битовые операторы работают только с целочисленными типами.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-144">The bitwise operators only work on integer types.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="0dfe5-145">ПРИОРИТЕТ ОПЕРАТОРОВ</span><span class="sxs-lookup"><span data-stu-id="0dfe5-145">OPERATOR PRECEDENCE</span></span>

<span data-ttu-id="0dfe5-146">PowerShell обрабатывает арифметические операторы в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="0dfe5-146">PowerShell processes arithmetic operators in the following order:</span></span>

|<span data-ttu-id="0dfe5-147">Приоритет</span><span class="sxs-lookup"><span data-stu-id="0dfe5-147">Precedence</span></span>|<span data-ttu-id="0dfe5-148">Оператор</span><span class="sxs-lookup"><span data-stu-id="0dfe5-148">Operator</span></span>          |<span data-ttu-id="0dfe5-149">Описание</span><span class="sxs-lookup"><span data-stu-id="0dfe5-149">Description</span></span>                            |
|----------|------------------|---------------------------------------|
|<span data-ttu-id="0dfe5-150">1</span><span class="sxs-lookup"><span data-stu-id="0dfe5-150">1</span></span>         | `()`             |<span data-ttu-id="0dfe5-151">Круглые скобки</span><span class="sxs-lookup"><span data-stu-id="0dfe5-151">Parentheses</span></span>                            |
|<span data-ttu-id="0dfe5-152">2</span><span class="sxs-lookup"><span data-stu-id="0dfe5-152">2</span></span>         | `-`              |<span data-ttu-id="0dfe5-153">Для отрицательного числа или унарного оператора</span><span class="sxs-lookup"><span data-stu-id="0dfe5-153">For a negative number or unary operator</span></span>|
|<span data-ttu-id="0dfe5-154">3</span><span class="sxs-lookup"><span data-stu-id="0dfe5-154">3</span></span>         | <span data-ttu-id="0dfe5-155">`*`, `/`, `%`</span><span class="sxs-lookup"><span data-stu-id="0dfe5-155">`*`, `/`, `%`</span></span>    |<span data-ttu-id="0dfe5-156">Для умножения и деления</span><span class="sxs-lookup"><span data-stu-id="0dfe5-156">For multiplication and division</span></span>        |
|<span data-ttu-id="0dfe5-157">4</span><span class="sxs-lookup"><span data-stu-id="0dfe5-157">4</span></span>         | <span data-ttu-id="0dfe5-158">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="0dfe5-158">`+`, `-`</span></span>         |<span data-ttu-id="0dfe5-159">Для сложения и вычитания</span><span class="sxs-lookup"><span data-stu-id="0dfe5-159">For addition and subtraction</span></span>           |
|<span data-ttu-id="0dfe5-160">5</span><span class="sxs-lookup"><span data-stu-id="0dfe5-160">5</span></span>         | <span data-ttu-id="0dfe5-161">`-band`, `-bnot`</span><span class="sxs-lookup"><span data-stu-id="0dfe5-161">`-band`, `-bnot`</span></span> |<span data-ttu-id="0dfe5-162">Для побитовых операций</span><span class="sxs-lookup"><span data-stu-id="0dfe5-162">For bitwise operations</span></span>                 |
|<span data-ttu-id="0dfe5-163">5</span><span class="sxs-lookup"><span data-stu-id="0dfe5-163">5</span></span>         | <span data-ttu-id="0dfe5-164">`-bor`, `-bxor`</span><span class="sxs-lookup"><span data-stu-id="0dfe5-164">`-bor`, `-bxor`</span></span>  |<span data-ttu-id="0dfe5-165">Для побитовых операций</span><span class="sxs-lookup"><span data-stu-id="0dfe5-165">For bitwise operations</span></span>                 |
|<span data-ttu-id="0dfe5-166">5</span><span class="sxs-lookup"><span data-stu-id="0dfe5-166">5</span></span>         | <span data-ttu-id="0dfe5-167">`-shr`, `-shl`</span><span class="sxs-lookup"><span data-stu-id="0dfe5-167">`-shr`, `-shl`</span></span>   |<span data-ttu-id="0dfe5-168">Для побитовых операций</span><span class="sxs-lookup"><span data-stu-id="0dfe5-168">For bitwise operations</span></span>                 |

<span data-ttu-id="0dfe5-169">PowerShell обрабатывает выражения слева направо в соответствии с правилами приоритета.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-169">PowerShell processes the expressions from left to right according to the precedence rules.</span></span> <span data-ttu-id="0dfe5-170">В следующих примерах показан результат применения правил приоритета.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-170">The following examples show the effect of the precedence rules:</span></span>

|<span data-ttu-id="0dfe5-171">Выражение</span><span class="sxs-lookup"><span data-stu-id="0dfe5-171">Expression</span></span> |<span data-ttu-id="0dfe5-172">Результат</span><span class="sxs-lookup"><span data-stu-id="0dfe5-172">Result</span></span>|
|-----------|------|
|`3+6/3*4`  |`11`  |
|`3+6/(3*4)`|`3.5` |
|`(3+6)/3*4`|`12`  |

<span data-ttu-id="0dfe5-173">Порядок, в котором PowerShell вычисляет выражения, может отличаться от других используемых языков программирования и сценариев.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-173">The order in which PowerShell evaluates expressions might differ from other programming and scripting languages that you have used.</span></span> <span data-ttu-id="0dfe5-174">В следующем примере показана сложная инструкция присваивания.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-174">The following example shows a complicated assignment statement.</span></span>

```powershell
$a = 0
$b = @(1,2)
$c = @(-1,-2)

$b[$a] = $c[$a++]
```

<span data-ttu-id="0dfe5-175">В этом примере выражение `$a++` вычисляется раньше `$b[$a]` .</span><span class="sxs-lookup"><span data-stu-id="0dfe5-175">In this example, the expression `$a++` is evaluated before `$b[$a]`.</span></span>
<span data-ttu-id="0dfe5-176">Вычисление `$a++` изменяет значение `$a` после его использования в операторе `$c[$a++]` , но до того, как оно будет использовано в `$b[$a]` .</span><span class="sxs-lookup"><span data-stu-id="0dfe5-176">Evaluating `$a++` changes the value of `$a` after it is used in the statement `$c[$a++]`; but, before it is used in `$b[$a]`.</span></span> <span data-ttu-id="0dfe5-177">Переменная `$a` в `$b[$a]` равно, а `1` не `0` ; поэтому оператор присваивает значение `$b[1]` , а не `$b[0]` .</span><span class="sxs-lookup"><span data-stu-id="0dfe5-177">The variable `$a` in `$b[$a]` equals `1`, not `0`; so, the statement assigns a value to `$b[1]`, not `$b[0]`.</span></span>

<span data-ttu-id="0dfe5-178">Приведенный выше код эквивалентен:</span><span class="sxs-lookup"><span data-stu-id="0dfe5-178">The above code is equivalent to:</span></span>

```powershell
$a = 0
$b = @(1,2)
$c = @(-1,-2)

$tmp = $c[$a]
$a = $a + 1
$b[$a] = $tmp
```

## <a name="division-and-rounding"></a><span data-ttu-id="0dfe5-179">ДЕЛЕНИЕ И ОКРУГЛЕНИЕ</span><span class="sxs-lookup"><span data-stu-id="0dfe5-179">DIVISION AND ROUNDING</span></span>

<span data-ttu-id="0dfe5-180">Если частная операция деления является целым числом, PowerShell Округляет значение до ближайшего целого числа.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-180">When the quotient of a division operation is an integer, PowerShell rounds the value to the nearest integer.</span></span> <span data-ttu-id="0dfe5-181">Если значение равно `.5` , оно округляет до ближайшего четного целого числа.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-181">When the value is `.5`, it rounds to the nearest even integer.</span></span>

<span data-ttu-id="0dfe5-182">В следующем примере показан результат округления до ближайшего четного целого числа.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-182">The following example shows the effect of rounding to the nearest even integer.</span></span>

|<span data-ttu-id="0dfe5-183">Выражение</span><span class="sxs-lookup"><span data-stu-id="0dfe5-183">Expression</span></span>      |<span data-ttu-id="0dfe5-184">Результат</span><span class="sxs-lookup"><span data-stu-id="0dfe5-184">Result</span></span>|
|----------------|------|
|`[int]( 5 / 2 )`|`2`   |
|`[int]( 7 / 2 )`|`4`   |

<span data-ttu-id="0dfe5-185">Обратите внимание, что **_5/2_ = 2,5** округляется до **2**.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-185">Notice how **_5/2_ = 2.5** gets rounded to **2**.</span></span> <span data-ttu-id="0dfe5-186">Но **_7/2_ = 3,5** округляется до **4**.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-186">But, **_7/2_ = 3.5** gets rounded to **4**.</span></span>

<span data-ttu-id="0dfe5-187">Можно использовать класс, `[Math]` чтобы получить разное поведение округления.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-187">You can use the `[Math]` class to get different rounding behavior.</span></span>

|                          <span data-ttu-id="0dfe5-188">Выражение</span><span class="sxs-lookup"><span data-stu-id="0dfe5-188">Expression</span></span>                          | <span data-ttu-id="0dfe5-189">Результат</span><span class="sxs-lookup"><span data-stu-id="0dfe5-189">Result</span></span> |
| ------------------------------------------------------------ | ------ |
| `[int][Math]::Round(5 / 2,[MidpointRounding]::AwayFromZero)` | `3`    |
| `[int][Math]::Ceiling(5 / 2)`                                | `3`    |
| `[int][Math]::Floor(5 / 2)`                                  | `2`    |

<span data-ttu-id="0dfe5-190">Дополнительные сведения см. в описании метода [Math. Round](/dotnet/api/system.math.round) .</span><span class="sxs-lookup"><span data-stu-id="0dfe5-190">For more information, see the [Math.Round](/dotnet/api/system.math.round) method.</span></span>

## <a name="adding-and-multiplying-non-numeric-types"></a><span data-ttu-id="0dfe5-191">ДОБАВЛЕНИЕ И УМНОЖЕНИЕ НЕЧИСЛОВЫХ ТИПОВ</span><span class="sxs-lookup"><span data-stu-id="0dfe5-191">ADDING AND MULTIPLYING NON-NUMERIC TYPES</span></span>

<span data-ttu-id="0dfe5-192">Можно добавлять числа, строки, массивы и хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-192">You can add numbers, strings, arrays, and hash tables.</span></span> <span data-ttu-id="0dfe5-193">И можно умножить числа, строки и массивы.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-193">And, you can multiply numbers, strings, and arrays.</span></span> <span data-ttu-id="0dfe5-194">Однако нельзя умножить хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-194">However, you cannot multiply hash tables.</span></span>

<span data-ttu-id="0dfe5-195">При добавлении строк, массивов или хэш-таблиц элементы объединяются.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-195">When you add strings, arrays, or hash tables, the elements are concatenated.</span></span> <span data-ttu-id="0dfe5-196">При сцеплении коллекций, таких как массивы или хэш-таблицы, создается новый объект, содержащий объекты из обеих коллекций.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-196">When you concatenate collections, such as arrays or hash tables, a new object is created that contains the objects from both collections.</span></span> <span data-ttu-id="0dfe5-197">При попытке объединить хэш-таблицы с одним и тем же ключом операция завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-197">If you try to concatenate hash tables that have the same key, the operation fails.</span></span>

<span data-ttu-id="0dfe5-198">Например, следующие команды создают два массива, а затем добавляют их:</span><span class="sxs-lookup"><span data-stu-id="0dfe5-198">For example, the following commands create two arrays and then add them:</span></span>

```powershell
$a = 1,2,3
$b = "A","B","C"
$a + $b
```

```output
1
2
3
A
B
C
```

<span data-ttu-id="0dfe5-199">Также можно выполнять арифметические операции с объектами различных типов.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-199">You can also perform arithmetic operations on objects of different types.</span></span>
<span data-ttu-id="0dfe5-200">Операция, выполняемая PowerShell, определяется Microsoft .NET типом платформы самого левого объекта в операции.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-200">The operation that PowerShell performs is determined by the Microsoft .NET Framework type of the leftmost object in the operation.</span></span> <span data-ttu-id="0dfe5-201">PowerShell пытается преобразовать все объекты в операции в тип .NET Framework первого объекта.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-201">PowerShell tries to convert all the objects in the operation to the .NET Framework type of the first object.</span></span> <span data-ttu-id="0dfe5-202">Если при преобразовании объектов он будет выполнен, он выполняет операцию, соответствующую типу .NET Framework первого объекта.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-202">If it succeeds in converting the objects, it performs the operation appropriate to the .NET Framework type of the first object.</span></span> <span data-ttu-id="0dfe5-203">Если не удается преобразовать ни один из объектов, операция завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-203">If it fails to convert any of the objects, the operation fails.</span></span>

<span data-ttu-id="0dfe5-204">В следующих примерах демонстрируется использование операторов сложения и умножения. в операциях, включающих различные типы объектов.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-204">The following examples demonstrate the use of the addition and multiplication operators; in operations that include different object types.</span></span> <span data-ttu-id="0dfe5-205">Предположим `$array = 1,2,3` :</span><span class="sxs-lookup"><span data-stu-id="0dfe5-205">Assume `$array = 1,2,3`:</span></span>

|<span data-ttu-id="0dfe5-206">Выражение</span><span class="sxs-lookup"><span data-stu-id="0dfe5-206">Expression</span></span>       |<span data-ttu-id="0dfe5-207">Результат</span><span class="sxs-lookup"><span data-stu-id="0dfe5-207">Result</span></span>                 |
|-----------------|-----------------------|
|`"file" + 16`    |`file16`               |
|`$array + 16`    |<span data-ttu-id="0dfe5-208">`1`,`2`,`3`,`16`</span><span class="sxs-lookup"><span data-stu-id="0dfe5-208">`1`,`2`,`3`,`16`</span></span>       |
|`$array + "file"`|<span data-ttu-id="0dfe5-209">`1`,`2`,`3`,`file`</span><span class="sxs-lookup"><span data-stu-id="0dfe5-209">`1`,`2`,`3`,`file`</span></span>     |
|`$array * 2`     |<span data-ttu-id="0dfe5-210">`1`,`2`,`3`,`1`,`2`,`3`</span><span class="sxs-lookup"><span data-stu-id="0dfe5-210">`1`,`2`,`3`,`1`,`2`,`3`</span></span>|
|`"file" * 3`     |`filefilefile`         |

<span data-ttu-id="0dfe5-211">Поскольку метод, используемый для вычисления инструкций, определяется крайним левым объектом, Добавление и умножение в PowerShell не строго коммутативной.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-211">Because the method that is used to evaluate statements is determined by the leftmost object, addition and multiplication in PowerShell are not strictly commutative.</span></span> <span data-ttu-id="0dfe5-212">Например, не `(a + b)` всегда равно и не `(b + a)` `(ab)` всегда равно `(ba)` .</span><span class="sxs-lookup"><span data-stu-id="0dfe5-212">For example, `(a + b)` does not always equal `(b + a)`, and `(ab)` does not always equal `(ba)`.</span></span>

<span data-ttu-id="0dfe5-213">Этот принцип демонстрируется в следующих примерах:</span><span class="sxs-lookup"><span data-stu-id="0dfe5-213">The following examples demonstrate this principle:</span></span>

|<span data-ttu-id="0dfe5-214">Выражение</span><span class="sxs-lookup"><span data-stu-id="0dfe5-214">Expression</span></span>   |<span data-ttu-id="0dfe5-215">Результат</span><span class="sxs-lookup"><span data-stu-id="0dfe5-215">Result</span></span>                                               |
|-------------|-----------------------------------------------------|
|`"file" + 16`|`file16`                                             |
|`16 + "file"`|`Cannot convert value "file" to type "System.Int32".`|
|             |`Error: "Input string was not in a correct format."` |
|             |`At line:1 char:1`                                   |
|             |<span data-ttu-id="0dfe5-216">+ 16 + "файл"</span><span class="sxs-lookup"><span data-stu-id="0dfe5-216">+ 16 + "file"\`</span></span>                                       |

<span data-ttu-id="0dfe5-217">Хэш-таблицы являются слегка отличающимися регистром.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-217">Hash tables are a slightly different case.</span></span> <span data-ttu-id="0dfe5-218">Можно добавить хэш-таблицы в другую хэш-таблицу при условии, что в добавленных хэш-таблицах нет повторяющихся ключей.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-218">You can add hash tables to another hash table, as long as, the added hash tables don't have duplicate keys.</span></span>

<span data-ttu-id="0dfe5-219">В следующем примере показано, как добавить хэш-таблицы друг в друга.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-219">The following example show how to add hash tables to each other.</span></span>

```powershell
$hash1 = @{a=1; b=2; c=3}
$hash2 = @{c1="Server01"; c2="Server02"}
$hash1 + $hash2
```

```output
Name                           Value
----                           -----
c2                             Server02
a                              1
b                              2
c1                             Server01
c                              3
```

<span data-ttu-id="0dfe5-220">В следующем примере возникает ошибка, так как один из ключей дублируется в обеих хэш-таблицах.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-220">The following example throws an error because one of the keys is duplicated in both hash tables.</span></span>

```powershell
$hash1 = @{a=1; b=2; c=3}
$hash2 = @{c1="Server01"; c="Server02"}
$hash1 + $hash2
```

```output
Item has already been added. Key in dictionary: 'c'  Key being added: 'c'
At line:3 char:1
+ $hash1 + $hash2
+ ~~~~~~~~~~~~~~~
    + CategoryInfo          : OperationStopped: (:) [], ArgumentException
    + FullyQualifiedErrorId : System.ArgumentException
```

<span data-ttu-id="0dfe5-221">Кроме того, можно добавить хэш-таблицу в массив. и вся хэш-таблица преобразуется в элемент массива.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-221">Also, you can add a hash table to an array; and, the entire hash table becomes an item in the array.</span></span>

```powershell
$array1 = @(0, "Hello World", [datetime]::Now)
$hash1 = @{a=1; b=2}
$array2 = $array1 + $hash1
$array2
```

```output
0
Hello World

Monday, June 12, 2017 3:05:46 PM

Key   : a
Value : 1
Name  : a

Key   : b
Value : 2
Name  : b
```

<span data-ttu-id="0dfe5-222">Однако в хэш-таблицу нельзя добавить любой другой тип.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-222">However, you cannot add any other type to a hash table.</span></span>

```powershell
$hash1 + 2
```

```output
A hash table can only be added to another hash table.
At line:3 char:1
+ $hash1 + 2
```

<span data-ttu-id="0dfe5-223">Хотя операторы сложения очень полезны, используйте операторы присваивания для добавления элементов в хэш-таблицы и массивы.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-223">Although the addition operators are very useful, use the assignment operators to add elements to hash tables and arrays.</span></span> <span data-ttu-id="0dfe5-224">Дополнительные сведения см. в разделе [about_assignment_operators](about_Assignment_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="0dfe5-224">For more information see [about_assignment_operators](about_Assignment_Operators.md).</span></span> <span data-ttu-id="0dfe5-225">В следующих примерах для `+=` добавления элементов в массив используется оператор присваивания:</span><span class="sxs-lookup"><span data-stu-id="0dfe5-225">The following examples use the `+=` assignment operator to add items to an array:</span></span>

```powershell
$array = @()
(0..9).foreach{ $array += $_ }
$array
```

```output
0
1
2
```

## <a name="type-conversion-to-accommodate-result"></a><span data-ttu-id="0dfe5-226">ПРЕОБРАЗОВАНИЕ ТИПОВ В СООТВЕТСТВИИ С РЕЗУЛЬТАТОМ</span><span class="sxs-lookup"><span data-stu-id="0dfe5-226">TYPE CONVERSION TO ACCOMMODATE RESULT</span></span>

<span data-ttu-id="0dfe5-227">PowerShell автоматически выбирает .NET Framework числовой тип, который наилучшим образом выражает результат без потери точности.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-227">PowerShell automatically selects the .NET Framework numeric type that best expresses the result without losing precision.</span></span> <span data-ttu-id="0dfe5-228">Пример:</span><span class="sxs-lookup"><span data-stu-id="0dfe5-228">For example:</span></span>

```powershell
2 + 3.1

(2). GetType().FullName
(2 + 3.1).GetType().FullName
```

```output
5.1
System.Int32
System.Double
```

<span data-ttu-id="0dfe5-229">Если результат операции слишком велик для типа, тип результата расширяется в соответствии с результатом, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="0dfe5-229">If the result of an operation is too large for the type, the type of the result is widened to accommodate the result, as in the following example:</span></span>

```powershell
(512MB).GetType().FullName
(512MB * 512MB).GetType().FullName
```

```output
System.Int32
System.Double
```

<span data-ttu-id="0dfe5-230">Тип результата не обязательно будет таким же, как и один из операндов.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-230">The type of the result will not necessarily be the same as one of the operands.</span></span> <span data-ttu-id="0dfe5-231">В следующем примере отрицательное значение не может быть приведено к целому числу без знака, а целое число без знака слишком велико для приведения к `Int32` :</span><span class="sxs-lookup"><span data-stu-id="0dfe5-231">In the following example, the negative value cannot be cast to an unsigned integer, and the unsigned integer is too large to be cast to `Int32`:</span></span>

```powershell
([int32]::minvalue + [uint32]::maxvalue).gettype().fullname
```

```output
System.Int64
```

<span data-ttu-id="0dfe5-232">В этом примере `Int64` может соответствовать обоим типам.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-232">In this example, `Int64` can accommodate both types.</span></span>

<span data-ttu-id="0dfe5-233">`System.Decimal`Тип является исключением.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-233">The `System.Decimal` type is an exception.</span></span> <span data-ttu-id="0dfe5-234">Если любой из операндов имеет десятичный тип, результат будет иметь тип Decimal.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-234">If either operand has the Decimal type, the result will be of the Decimal type.</span></span> <span data-ttu-id="0dfe5-235">Если результат слишком велик для типа Decimal, он не будет приведен к типу Double.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-235">If the result is too large for the Decimal type, it will not be cast to Double.</span></span> <span data-ttu-id="0dfe5-236">Вместо этого возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-236">Instead, an error results.</span></span>

|<span data-ttu-id="0dfe5-237">Выражение</span><span class="sxs-lookup"><span data-stu-id="0dfe5-237">Expression</span></span>               |<span data-ttu-id="0dfe5-238">Результат</span><span class="sxs-lookup"><span data-stu-id="0dfe5-238">Result</span></span>                                         |
|-------------------------|-----------------------------------------------|
|`[Decimal]::maxvalue`    |`79228162514264337593543950335`                |
|`[Decimal]::maxvalue + 1`|`Value was either too large or too small for a`|
|                         |`Decimal.`                                     |

## <a name="arithmetic-operators-and-variables"></a><span data-ttu-id="0dfe5-239">АРИФМЕТИЧЕСКИЕ ОПЕРАТОРЫ И ПЕРЕМЕННЫЕ</span><span class="sxs-lookup"><span data-stu-id="0dfe5-239">ARITHMETIC OPERATORS AND VARIABLES</span></span>

<span data-ttu-id="0dfe5-240">Кроме того, арифметические операторы можно использовать с переменными.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-240">You can also use arithmetic operators with variables.</span></span> <span data-ttu-id="0dfe5-241">Операторы действуют на значения переменных.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-241">The operators act on the values of the variables.</span></span> <span data-ttu-id="0dfe5-242">В следующих примерах демонстрируется использование арифметических операторов с переменными:</span><span class="sxs-lookup"><span data-stu-id="0dfe5-242">The following examples demonstrate the use of arithmetic operators with variables:</span></span>

| <span data-ttu-id="0dfe5-243">Выражение</span><span class="sxs-lookup"><span data-stu-id="0dfe5-243">Expression</span></span>                                    |<span data-ttu-id="0dfe5-244">Результат</span><span class="sxs-lookup"><span data-stu-id="0dfe5-244">Result</span></span>      |
|-----------------------------------------------|------------|
|`$intA = 6`<br/>`$intB = 4`<br/>`$intA + $intB`|`10`        |
|`$a = "Power"`<br/>`$b = "Shell"`<br/>`$a + $b`|`PowerShell`|

## <a name="arithmetic-operators-and-commands"></a><span data-ttu-id="0dfe5-245">АРИФМЕТИЧЕСКИЕ ОПЕРАТОРЫ И КОМАНДЫ</span><span class="sxs-lookup"><span data-stu-id="0dfe5-245">ARITHMETIC OPERATORS AND COMMANDS</span></span>

<span data-ttu-id="0dfe5-246">Обычно арифметические операторы используются в выражениях с числами, строками и массивами.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-246">Typically, you use the arithmetic operators in expressions with numbers, strings, and arrays.</span></span> <span data-ttu-id="0dfe5-247">Однако арифметические операторы также можно использовать с объектами, возвращаемыми командами, и со свойствами этих объектов.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-247">However, you can also use arithmetic operators with the objects that commands return and with the properties of those objects.</span></span>

<span data-ttu-id="0dfe5-248">В следующих примерах показано, как использовать арифметические операторы в выражениях с командами PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0dfe5-248">The following examples show how to use the arithmetic operators in expressions with PowerShell commands:</span></span>

```powershell
(get-date) + (new-timespan -day 1)
```

<span data-ttu-id="0dfe5-249">Оператор скобки вызывает принудительное вычисление `get-date` командлета и вычисление `new-timespan -day 1` выражения командлета в указанном порядке.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-249">The parenthesis operator forces the evaluation of the `get-date` cmdlet and the evaluation of the `new-timespan -day 1` cmdlet expression, in that order.</span></span> <span data-ttu-id="0dfe5-250">Затем оба результата добавляются с помощью `+` оператора.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-250">Both results are then added using the `+` operator.</span></span>

```powershell
Get-Process | Where-Object { ($_.ws * 2) -gt 50mb }
```

```output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
   1896      39    50968      30620   264 1,572.55   1104 explorer
  12802      78   188468      81032   753 3,676.39   5676 OUTLOOK
    660       9    36168      26956   143    12.20    988 PowerShell
    561      14     6592      28144   110 1,010.09    496 services
   3476      80    34664      26092   234 ...45.69    876 svchost
    967      30    58804      59496   416   930.97   2508 WINWORD
```

<span data-ttu-id="0dfe5-251">В приведенном выше выражении каждое рабочее пространство процесса ( `$_.ws` ) умножается на `2` ; и результат сравнивается с, `50mb` чтобы узнать, больше ли оно.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-251">In the above expression, each process working space (`$_.ws`) is multiplied by `2`; and, the result, compared against `50mb` to see if it is greater than that.</span></span>

## <a name="bitwise-operators"></a><span data-ttu-id="0dfe5-252">Побитовые операторы</span><span class="sxs-lookup"><span data-stu-id="0dfe5-252">Bitwise Operators</span></span>

<span data-ttu-id="0dfe5-253">PowerShell поддерживает стандартные битовые операторы, включая битовые и ( `-bAnd` ), включающие и исключающие побитовые ОПЕРАТОРЫ or ( `-bOr` и `-bXor` ), а также побитовое не ( `-bNot` ).</span><span class="sxs-lookup"><span data-stu-id="0dfe5-253">PowerShell supports the standard bitwise operators, including bitwise-AND (`-bAnd`), the inclusive and exclusive bitwise-OR operators (`-bOr` and `-bXor`), and bitwise-NOT (`-bNot`).</span></span>

<span data-ttu-id="0dfe5-254">Начиная с PowerShell 2,0, все битовые операторы работают с 64-разрядными целыми числами.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-254">Beginning in PowerShell 2.0, all bitwise operators work with 64-bit integers.</span></span>

<span data-ttu-id="0dfe5-255">Начиная с PowerShell 3,0, `-shr` `-shl` для поддержки побитовых арифметических операций в PowerShell появились (Shift-Right) и (Shift-Left).</span><span class="sxs-lookup"><span data-stu-id="0dfe5-255">Beginning in PowerShell 3.0, the `-shr` (shift-right) and `-shl` (shift-left) are introduced to support bitwise arithmetic in PowerShell.</span></span>

<span data-ttu-id="0dfe5-256">PowerShell поддерживает следующие Побитовые операторы.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-256">PowerShell supports the following bitwise operators.</span></span>

| <span data-ttu-id="0dfe5-257">Оператор</span><span class="sxs-lookup"><span data-stu-id="0dfe5-257">Operator</span></span> | <span data-ttu-id="0dfe5-258">Описание</span><span class="sxs-lookup"><span data-stu-id="0dfe5-258">Description</span></span>            | <span data-ttu-id="0dfe5-259">Выражение</span><span class="sxs-lookup"><span data-stu-id="0dfe5-259">Expression</span></span>   | <span data-ttu-id="0dfe5-260">Результат</span><span class="sxs-lookup"><span data-stu-id="0dfe5-260">Result</span></span> |
| -------- | ---------------------- | ------------ | ------ |
| `-band`  | <span data-ttu-id="0dfe5-261">Побитовое И</span><span class="sxs-lookup"><span data-stu-id="0dfe5-261">Bitwise AND</span></span>            | `10 -band 3` | <span data-ttu-id="0dfe5-262">2</span><span class="sxs-lookup"><span data-stu-id="0dfe5-262">2</span></span>      |
| `-bor`   | <span data-ttu-id="0dfe5-263">Побитовое или (включительно)</span><span class="sxs-lookup"><span data-stu-id="0dfe5-263">Bitwise OR (inclusive)</span></span> | `10 -bor 3`  | <span data-ttu-id="0dfe5-264">11</span><span class="sxs-lookup"><span data-stu-id="0dfe5-264">11</span></span>     |
| `-bxor`  | <span data-ttu-id="0dfe5-265">Побитовое или (Эксклюзивное)</span><span class="sxs-lookup"><span data-stu-id="0dfe5-265">Bitwise OR (exclusive)</span></span> | `10 -bxor 3` | <span data-ttu-id="0dfe5-266">9</span><span class="sxs-lookup"><span data-stu-id="0dfe5-266">9</span></span>      |
| `-bnot`  | <span data-ttu-id="0dfe5-267">Побитовое НЕ</span><span class="sxs-lookup"><span data-stu-id="0dfe5-267">Bitwise NOT</span></span>            | `-bNot 10`   | <span data-ttu-id="0dfe5-268">-11</span><span class="sxs-lookup"><span data-stu-id="0dfe5-268">-11</span></span>    |
| `-shl`   | <span data-ttu-id="0dfe5-269">Сдвиг влево</span><span class="sxs-lookup"><span data-stu-id="0dfe5-269">Shift-left</span></span>             | `102 -shl 2` | <span data-ttu-id="0dfe5-270">408</span><span class="sxs-lookup"><span data-stu-id="0dfe5-270">408</span></span>    |
| `-shr`   | <span data-ttu-id="0dfe5-271">Shift справа</span><span class="sxs-lookup"><span data-stu-id="0dfe5-271">Shift-right</span></span>            | `102 -shr 1` | <span data-ttu-id="0dfe5-272">51</span><span class="sxs-lookup"><span data-stu-id="0dfe5-272">51</span></span>     |

<span data-ttu-id="0dfe5-273">Битовые операторы работают с двоичным форматом значения.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-273">Bitwise operators act on the binary format of a value.</span></span> <span data-ttu-id="0dfe5-274">Например, битовая структура для числа 10 — 00001010 (на основе 1 байта), а битовая структура для числа 3 — 00000011.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-274">For example, the bit structure for the number 10 is 00001010 (based on 1 byte), and the bit structure for the number 3 is 00000011.</span></span> <span data-ttu-id="0dfe5-275">При использовании побитового оператора для сравнения 10 и 3 отдельные биты в каждом байте сравниваются.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-275">When you use a bitwise operator to compare 10 to 3, the individual bits in each byte are compared.</span></span>

<span data-ttu-id="0dfe5-276">В побитовой операции AND полученный бит устанавливается в значение 1 только в том случае, если оба входных бита равны 1.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-276">In a bitwise AND operation, the resulting bit is set to 1 only when both input bits are 1.</span></span>

```
1010      (10)
0011      ( 3)
--------------  bAND
0010      ( 2)
```

<span data-ttu-id="0dfe5-277">При выполнении операции побитового или (включительно) полученный бит устанавливается в значение 1, если один или оба входных бита равны 1.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-277">In a bitwise OR (inclusive) operation, the resulting bit is set to 1 when either or both input bits are 1.</span></span> <span data-ttu-id="0dfe5-278">Полученный бит имеет значение 0, только если оба входных бита имеют значение 0.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-278">The resulting bit is set to 0 only when both input bits are set to 0.</span></span>

```
1010      (10)
0011      ( 3)
--------------  bOR (inclusive)
1011      (11)
```

<span data-ttu-id="0dfe5-279">В побитовой операции или (исключающей) полученный бит устанавливается в значение 1 только в том случае, если один входной бит равен 1.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-279">In a bitwise OR (exclusive) operation, the resulting bit is set to 1 only when one input bit is 1.</span></span>

```
1010      (10)
0011      ( 3)
--------------  bXOR (exclusive)
1001      ( 9)
```

<span data-ttu-id="0dfe5-280">Оператор побитового не является унарным оператором, который создает двоичный дополнение к значению.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-280">The bitwise NOT operator is a unary operator that produces the binary complement of the value.</span></span> <span data-ttu-id="0dfe5-281">Бит 1 имеет значение 0, а бит 0 имеет значение 1.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-281">A bit of 1 is set to 0 and a bit of 0 is set to 1.</span></span>

<span data-ttu-id="0dfe5-282">Например, дополняющий двоичный код 0 равен-1, максимальное целое число без знака (0xFFFFFFFF) и двоичное дополнение-1 — 0.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-282">For example, the binary complement of 0 is -1, the maximum unsigned integer (0xffffffff), and the binary complement of -1 is 0.</span></span>

```powershell
-bNot 10
```

```Output
-11
```

```
0000 0000 0000 1010  (10)
------------------------- bNOT
1111 1111 1111 0101  (-11, xfffffff5)
```

<span data-ttu-id="0dfe5-283">В операции побитового сдвига влево все биты перемещаются слева, где n — это значение правого операнда.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-283">In a bitwise shift-left operation, all bits are moved "n" places to the left, where "n" is the value of the right operand.</span></span> <span data-ttu-id="0dfe5-284">В место размещения вставляется ноль.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-284">A zero is inserted in the ones place.</span></span>

<span data-ttu-id="0dfe5-285">Если левый операнд является целочисленным (32-разрядным) значением, младшие 5 разрядов правого операнда определяют, сколько битов левого операнда смещается.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-285">When the left operand is an Integer (32-bit) value, the lower 5 bits of the right operand determine how many bits of the left operand are shifted.</span></span>

<span data-ttu-id="0dfe5-286">Если левый операнд является длинным (64-битным) значением, младшие 6 разрядов правого операнда определяют, сколько битов левого операнда смещается.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-286">When the left operand is a Long (64-bit) value, the lower 6 bits of the right operand determine how many bits of the left operand are shifted.</span></span>

|<span data-ttu-id="0dfe5-287">Выражение</span><span class="sxs-lookup"><span data-stu-id="0dfe5-287">Expression</span></span> |<span data-ttu-id="0dfe5-288">Результат</span><span class="sxs-lookup"><span data-stu-id="0dfe5-288">Result</span></span>|<span data-ttu-id="0dfe5-289">Двоичный результат</span><span class="sxs-lookup"><span data-stu-id="0dfe5-289">Binary Result</span></span>|
|-----------|------|-------------|
|`21 -shl 0`|<span data-ttu-id="0dfe5-290">21</span><span class="sxs-lookup"><span data-stu-id="0dfe5-290">21</span></span>    |<span data-ttu-id="0dfe5-291">0001 0101</span><span class="sxs-lookup"><span data-stu-id="0dfe5-291">0001 0101</span></span>    |
|`21 -shl 1`|<span data-ttu-id="0dfe5-292">42</span><span class="sxs-lookup"><span data-stu-id="0dfe5-292">42</span></span>    |<span data-ttu-id="0dfe5-293">0010 1010</span><span class="sxs-lookup"><span data-stu-id="0dfe5-293">0010 1010</span></span>    |
|`21 -shl 2`|<span data-ttu-id="0dfe5-294">84</span><span class="sxs-lookup"><span data-stu-id="0dfe5-294">84</span></span>    |<span data-ttu-id="0dfe5-295">0101 0100</span><span class="sxs-lookup"><span data-stu-id="0dfe5-295">0101 0100</span></span>    |

<span data-ttu-id="0dfe5-296">В операции побитового сдвига вправо все биты перемещаются справа, где "n" указывается правым операндом.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-296">In a bitwise shift-right operation, all bits are moved "n" places to the right, where "n" is specified by the right operand.</span></span> <span data-ttu-id="0dfe5-297">Оператор сдвига вправо (-SHR) вставляет ноль в крайнее левое место при перемещении положительного или неподписанного значения вправо.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-297">The shift-right operator (-shr) inserts a zero in the left-most place when shifting a positive or unsigned value to the right.</span></span>

<span data-ttu-id="0dfe5-298">Если левый операнд является целочисленным (32-разрядным) значением, младшие 5 разрядов правого операнда определяют, сколько битов левого операнда смещается.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-298">When the left operand is an Integer (32-bit) value, the lower 5 bits of the right operand determine how many bits of the left operand are shifted.</span></span>

<span data-ttu-id="0dfe5-299">Если левый операнд является длинным (64-битным) значением, младшие 6 разрядов правого операнда определяют, сколько битов левого операнда смещается.</span><span class="sxs-lookup"><span data-stu-id="0dfe5-299">When the left operand is a Long (64-bit) value, the lower 6 bits of the right operand determine how many bits of the left operand are shifted.</span></span>

|<span data-ttu-id="0dfe5-300">Выражение</span><span class="sxs-lookup"><span data-stu-id="0dfe5-300">Expression</span></span>              |<span data-ttu-id="0dfe5-301">Результат</span><span class="sxs-lookup"><span data-stu-id="0dfe5-301">Result</span></span>      |<span data-ttu-id="0dfe5-302">Двоичные данные</span><span class="sxs-lookup"><span data-stu-id="0dfe5-302">Binary</span></span>     |<span data-ttu-id="0dfe5-303">Hex</span><span class="sxs-lookup"><span data-stu-id="0dfe5-303">Hex</span></span>         |
|------------------------|------------|-----------|------------|
|`21 -shr 0`             | <span data-ttu-id="0dfe5-304">21</span><span class="sxs-lookup"><span data-stu-id="0dfe5-304">21</span></span>         | <span data-ttu-id="0dfe5-305">0001 0101</span><span class="sxs-lookup"><span data-stu-id="0dfe5-305">0001 0101</span></span> | <span data-ttu-id="0dfe5-306">0x15</span><span class="sxs-lookup"><span data-stu-id="0dfe5-306">0x15</span></span>       |
|`21 -shr 1`             | <span data-ttu-id="0dfe5-307">10</span><span class="sxs-lookup"><span data-stu-id="0dfe5-307">10</span></span>         | <span data-ttu-id="0dfe5-308">0000 1010</span><span class="sxs-lookup"><span data-stu-id="0dfe5-308">0000 1010</span></span> | <span data-ttu-id="0dfe5-309">0x0A</span><span class="sxs-lookup"><span data-stu-id="0dfe5-309">0x0A</span></span>       |
|`21 -shr 2`             | <span data-ttu-id="0dfe5-310">5</span><span class="sxs-lookup"><span data-stu-id="0dfe5-310">5</span></span>          | <span data-ttu-id="0dfe5-311">0000 0101</span><span class="sxs-lookup"><span data-stu-id="0dfe5-311">0000 0101</span></span> | <span data-ttu-id="0dfe5-312">0x05</span><span class="sxs-lookup"><span data-stu-id="0dfe5-312">0x05</span></span>       |
|`21 -shr 31`            | <span data-ttu-id="0dfe5-313">0</span><span class="sxs-lookup"><span data-stu-id="0dfe5-313">0</span></span>          | <span data-ttu-id="0dfe5-314">0000 0000</span><span class="sxs-lookup"><span data-stu-id="0dfe5-314">0000 0000</span></span> | <span data-ttu-id="0dfe5-315">0x00</span><span class="sxs-lookup"><span data-stu-id="0dfe5-315">0x00</span></span>       |
|`21 -shr 32`            | <span data-ttu-id="0dfe5-316">21</span><span class="sxs-lookup"><span data-stu-id="0dfe5-316">21</span></span>         | <span data-ttu-id="0dfe5-317">0001 0101</span><span class="sxs-lookup"><span data-stu-id="0dfe5-317">0001 0101</span></span> | <span data-ttu-id="0dfe5-318">0x15</span><span class="sxs-lookup"><span data-stu-id="0dfe5-318">0x15</span></span>       |
|`21 -shr 64`            | <span data-ttu-id="0dfe5-319">21</span><span class="sxs-lookup"><span data-stu-id="0dfe5-319">21</span></span>         | <span data-ttu-id="0dfe5-320">0001 0101</span><span class="sxs-lookup"><span data-stu-id="0dfe5-320">0001 0101</span></span> | <span data-ttu-id="0dfe5-321">0x15</span><span class="sxs-lookup"><span data-stu-id="0dfe5-321">0x15</span></span>       |
|`21 -shr 65`            | <span data-ttu-id="0dfe5-322">10</span><span class="sxs-lookup"><span data-stu-id="0dfe5-322">10</span></span>         | <span data-ttu-id="0dfe5-323">0000 1010</span><span class="sxs-lookup"><span data-stu-id="0dfe5-323">0000 1010</span></span> | <span data-ttu-id="0dfe5-324">0x0A</span><span class="sxs-lookup"><span data-stu-id="0dfe5-324">0x0A</span></span>       |
|`21 -shr 66`            | <span data-ttu-id="0dfe5-325">5</span><span class="sxs-lookup"><span data-stu-id="0dfe5-325">5</span></span>          | <span data-ttu-id="0dfe5-326">0000 0101</span><span class="sxs-lookup"><span data-stu-id="0dfe5-326">0000 0101</span></span> | <span data-ttu-id="0dfe5-327">0x05</span><span class="sxs-lookup"><span data-stu-id="0dfe5-327">0x05</span></span>       |
|`[int]::MaxValue -shr 1`| <span data-ttu-id="0dfe5-328">1073741823</span><span class="sxs-lookup"><span data-stu-id="0dfe5-328">1073741823</span></span> |           | <span data-ttu-id="0dfe5-329">0x3FFFFFFF</span><span class="sxs-lookup"><span data-stu-id="0dfe5-329">0x3FFFFFFF</span></span> |
|`[int]::MinValue -shr 1`| <span data-ttu-id="0dfe5-330">— 1073741824</span><span class="sxs-lookup"><span data-stu-id="0dfe5-330">-1073741824</span></span>|           | <span data-ttu-id="0dfe5-331">0xC0000000</span><span class="sxs-lookup"><span data-stu-id="0dfe5-331">0xC0000000</span></span> |
|`-1 -shr 1`             | <span data-ttu-id="0dfe5-332">-1</span><span class="sxs-lookup"><span data-stu-id="0dfe5-332">-1</span></span>         |           | <span data-ttu-id="0dfe5-333">0xFFFFFFFF</span><span class="sxs-lookup"><span data-stu-id="0dfe5-333">0xFFFFFFFF</span></span> |

## <a name="see-also"></a><span data-ttu-id="0dfe5-334">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="0dfe5-334">SEE ALSO</span></span>

- [<span data-ttu-id="0dfe5-335">about_arrays</span><span class="sxs-lookup"><span data-stu-id="0dfe5-335">about_arrays</span></span>](about_Arrays.md)
- [<span data-ttu-id="0dfe5-336">about_assignment_operators</span><span class="sxs-lookup"><span data-stu-id="0dfe5-336">about_assignment_operators</span></span>](about_Assignment_Operators.md)
- [<span data-ttu-id="0dfe5-337">about_comparison_operators</span><span class="sxs-lookup"><span data-stu-id="0dfe5-337">about_comparison_operators</span></span>](about_Comparison_Operators.md)
- [<span data-ttu-id="0dfe5-338">about_hash_tables</span><span class="sxs-lookup"><span data-stu-id="0dfe5-338">about_hash_tables</span></span>](about_Hash_Tables.md)
- [<span data-ttu-id="0dfe5-339">about_operators</span><span class="sxs-lookup"><span data-stu-id="0dfe5-339">about_operators</span></span>](about_Operators.md)
- [<span data-ttu-id="0dfe5-340">about_variables</span><span class="sxs-lookup"><span data-stu-id="0dfe5-340">about_variables</span></span>](about_Variables.md)
- [<span data-ttu-id="0dfe5-341">Get-Дата</span><span class="sxs-lookup"><span data-stu-id="0dfe5-341">Get-Date</span></span>](xref:Microsoft.PowerShell.Utility.Get-Date)
- [<span data-ttu-id="0dfe5-342">New-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="0dfe5-342">New-TimeSpan</span></span>](xref:Microsoft.PowerShell.Utility.New-TimeSpan)
