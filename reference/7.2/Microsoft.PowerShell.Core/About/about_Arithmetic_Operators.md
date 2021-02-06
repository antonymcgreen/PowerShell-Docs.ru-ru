---
description: Описывает операторы, выполняющие арифметические действия в PowerShell.
Locale: en-US
ms.date: 10/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arithmetic_operators?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Arithmetic_Operators
ms.openlocfilehash: 174b3cb72f6b5eb1cc39c4974613d9b9c8dd81a7
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605553"
---
# <a name="about-arithmetic-operators"></a><span data-ttu-id="55017-103">Об арифметических операторах</span><span class="sxs-lookup"><span data-stu-id="55017-103">About Arithmetic Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="55017-104">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="55017-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="55017-105">Описывает операторы, выполняющие арифметические действия в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="55017-105">Describes the operators that perform arithmetic in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="55017-106">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="55017-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="55017-107">Арифметические операторы вычисляют числовые значения.</span><span class="sxs-lookup"><span data-stu-id="55017-107">Arithmetic operators calculate numeric values.</span></span> <span data-ttu-id="55017-108">Можно использовать один или несколько арифметических операторов для добавления, вычитания, умножения и деления значений, а также для вычисления остатка (остатка от деления) операции деления.</span><span class="sxs-lookup"><span data-stu-id="55017-108">You can use one or more arithmetic operators to add, subtract, multiply, and divide values, and to calculate the remainder (modulus) of a division operation.</span></span>

<span data-ttu-id="55017-109">Кроме того, оператор сложения ( `+` ) и оператор умножения ( `*` ) также работают с строками, массивами и хэш-таблицами.</span><span class="sxs-lookup"><span data-stu-id="55017-109">In addition, the addition operator (`+`) and multiplication operator (`*`) also operate on strings, arrays, and hash tables.</span></span> <span data-ttu-id="55017-110">Оператор сложения объединяет входные данные.</span><span class="sxs-lookup"><span data-stu-id="55017-110">The addition operator concatenates the input.</span></span> <span data-ttu-id="55017-111">Оператор умножения возвращает несколько копий входных данных.</span><span class="sxs-lookup"><span data-stu-id="55017-111">The multiplication operator returns multiple copies of the input.</span></span> <span data-ttu-id="55017-112">Можно даже смешивать типы объектов в арифметическом операторе.</span><span class="sxs-lookup"><span data-stu-id="55017-112">You can even mix object types in an arithmetic statement.</span></span> <span data-ttu-id="55017-113">Метод, используемый для вычисления инструкции, определяется типом самого левого объекта в выражении.</span><span class="sxs-lookup"><span data-stu-id="55017-113">The method that is used to evaluate the statement is determined by the type of the leftmost object in the expression.</span></span>

<span data-ttu-id="55017-114">Начиная с PowerShell 2,0, все арифметические операторы работают с 64-разрядными числами.</span><span class="sxs-lookup"><span data-stu-id="55017-114">Beginning in PowerShell 2.0, all arithmetic operators work on 64-bit numbers.</span></span>

<span data-ttu-id="55017-115">Начиная с PowerShell 3,0, `-shr` `-shl` для поддержки побитовых арифметических операций в PowerShell добавляются (Shift-Right) и (Shift-Left).</span><span class="sxs-lookup"><span data-stu-id="55017-115">Beginning in PowerShell 3.0, the `-shr` (shift-right) and `-shl` (shift-left) are added to support bitwise arithmetic in PowerShell.</span></span>

<span data-ttu-id="55017-116">PowerShell поддерживает следующие арифметические операторы:</span><span class="sxs-lookup"><span data-stu-id="55017-116">PowerShell supports the following arithmetic operators:</span></span>

|<span data-ttu-id="55017-117">Оператор</span><span class="sxs-lookup"><span data-stu-id="55017-117">Operator</span></span>|<span data-ttu-id="55017-118">Описание</span><span class="sxs-lookup"><span data-stu-id="55017-118">Description</span></span>                       |<span data-ttu-id="55017-119">Пример</span><span class="sxs-lookup"><span data-stu-id="55017-119">Example</span></span>                      |
|--------|----------------------------------|-----------------------------|
| +      |<span data-ttu-id="55017-120">Добавляет целые числа; объединяет</span><span class="sxs-lookup"><span data-stu-id="55017-120">Adds integers; concatenates</span></span>       |`6 + 2`                      |
|        |<span data-ttu-id="55017-121">строки, массивы и хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="55017-121">strings, arrays, and hash tables.</span></span> |`"file" + "name"`            |
|        |                                  |`@(1, "one") + @(2.0, "two")`|
|        |                                  |`@{"one" = 1} + @{"two" = 2}`|
| -      |<span data-ttu-id="55017-122">Вычитает одно значение из другого</span><span class="sxs-lookup"><span data-stu-id="55017-122">Subtracts one value from another</span></span>  |`6 - 2`                      |
|        |<span data-ttu-id="55017-123">значение</span><span class="sxs-lookup"><span data-stu-id="55017-123">value</span></span>                             |                             |
| -      |<span data-ttu-id="55017-124">Делает число отрицательным числом</span><span class="sxs-lookup"><span data-stu-id="55017-124">Makes a number a negative number</span></span>  |`-6`                         |
|        |                                  |`(Get-Date).AddDays(-1)`     |
| *      |<span data-ttu-id="55017-125">Умножение чисел или копирование строк</span><span class="sxs-lookup"><span data-stu-id="55017-125">Multiply numbers or copy strings</span></span>  |`6 * 2`                      |
|        |<span data-ttu-id="55017-126">и массивов с указанным числом</span><span class="sxs-lookup"><span data-stu-id="55017-126">and arrays the specified number</span></span>   |`@("!") * 4`                 |
|        |<span data-ttu-id="55017-127">раз.</span><span class="sxs-lookup"><span data-stu-id="55017-127">of times.</span></span>                         |`"!" * 3`                    |
| /      |<span data-ttu-id="55017-128">Производит деление двух значений.</span><span class="sxs-lookup"><span data-stu-id="55017-128">Divides two values.</span></span>               |`6 / 2`                      |
| %      |<span data-ttu-id="55017-129">Модуль — возвращает остаток от</span><span class="sxs-lookup"><span data-stu-id="55017-129">Modulus - returns the remainder of</span></span>|`7 % 2`                      |
|        |<span data-ttu-id="55017-130">Операция деления.</span><span class="sxs-lookup"><span data-stu-id="55017-130">a division operation.</span></span>             |                             |
|<span data-ttu-id="55017-131">-Band</span><span class="sxs-lookup"><span data-stu-id="55017-131">-band</span></span>   |<span data-ttu-id="55017-132">Побитовое И</span><span class="sxs-lookup"><span data-stu-id="55017-132">Bitwise AND</span></span>                       |`5 -band 3`                  |
|<span data-ttu-id="55017-133">-бнот</span><span class="sxs-lookup"><span data-stu-id="55017-133">-bnot</span></span>   |<span data-ttu-id="55017-134">Побитовое НЕ</span><span class="sxs-lookup"><span data-stu-id="55017-134">Bitwise NOT</span></span>                       |`-bnot 5`                    |
|<span data-ttu-id="55017-135">-Бор</span><span class="sxs-lookup"><span data-stu-id="55017-135">-bor</span></span>    |<span data-ttu-id="55017-136">Побитовое ИЛИ</span><span class="sxs-lookup"><span data-stu-id="55017-136">Bitwise OR</span></span>                        |`5 -bor 0x03`                |
|<span data-ttu-id="55017-137">-бксор</span><span class="sxs-lookup"><span data-stu-id="55017-137">-bxor</span></span>   |<span data-ttu-id="55017-138">Побитовое исключающее ИЛИ</span><span class="sxs-lookup"><span data-stu-id="55017-138">Bitwise XOR</span></span>                       |`5 -bxor 3`                  |
|<span data-ttu-id="55017-139">-Шл</span><span class="sxs-lookup"><span data-stu-id="55017-139">-shl</span></span>    |<span data-ttu-id="55017-140">Сдвигает биты влево</span><span class="sxs-lookup"><span data-stu-id="55017-140">Shifts bits to the left</span></span>           |`102 -shl 2`                 |
|<span data-ttu-id="55017-141">-SHR</span><span class="sxs-lookup"><span data-stu-id="55017-141">-shr</span></span>    |<span data-ttu-id="55017-142">Сдвигает биты вправо</span><span class="sxs-lookup"><span data-stu-id="55017-142">Shifts bits to the right</span></span>          |`102 -shr 2`                 |

<span data-ttu-id="55017-143">Битовые операторы работают только с целочисленными типами.</span><span class="sxs-lookup"><span data-stu-id="55017-143">The bitwise operators only work on integer types.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="55017-144">ПРИОРИТЕТ ОПЕРАТОРОВ</span><span class="sxs-lookup"><span data-stu-id="55017-144">OPERATOR PRECEDENCE</span></span>

<span data-ttu-id="55017-145">PowerShell обрабатывает арифметические операторы в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="55017-145">PowerShell processes arithmetic operators in the following order:</span></span>

|<span data-ttu-id="55017-146">Приоритет</span><span class="sxs-lookup"><span data-stu-id="55017-146">Precedence</span></span>|<span data-ttu-id="55017-147">Оператор</span><span class="sxs-lookup"><span data-stu-id="55017-147">Operator</span></span>          |<span data-ttu-id="55017-148">Описание</span><span class="sxs-lookup"><span data-stu-id="55017-148">Description</span></span>                            |
|----------|------------------|---------------------------------------|
|<span data-ttu-id="55017-149">1</span><span class="sxs-lookup"><span data-stu-id="55017-149">1</span></span>         | `()`             |<span data-ttu-id="55017-150">Круглые скобки</span><span class="sxs-lookup"><span data-stu-id="55017-150">Parentheses</span></span>                            |
|<span data-ttu-id="55017-151">2</span><span class="sxs-lookup"><span data-stu-id="55017-151">2</span></span>         | `-`              |<span data-ttu-id="55017-152">Для отрицательного числа или унарного оператора</span><span class="sxs-lookup"><span data-stu-id="55017-152">For a negative number or unary operator</span></span>|
|<span data-ttu-id="55017-153">3</span><span class="sxs-lookup"><span data-stu-id="55017-153">3</span></span>         | <span data-ttu-id="55017-154">`*`, `/`, `%`</span><span class="sxs-lookup"><span data-stu-id="55017-154">`*`, `/`, `%`</span></span>    |<span data-ttu-id="55017-155">Для умножения и деления</span><span class="sxs-lookup"><span data-stu-id="55017-155">For multiplication and division</span></span>        |
|<span data-ttu-id="55017-156">4</span><span class="sxs-lookup"><span data-stu-id="55017-156">4</span></span>         | <span data-ttu-id="55017-157">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="55017-157">`+`, `-`</span></span>         |<span data-ttu-id="55017-158">Для сложения и вычитания</span><span class="sxs-lookup"><span data-stu-id="55017-158">For addition and subtraction</span></span>           |
|<span data-ttu-id="55017-159">5</span><span class="sxs-lookup"><span data-stu-id="55017-159">5</span></span>         | <span data-ttu-id="55017-160">`-band`, `-bnot`</span><span class="sxs-lookup"><span data-stu-id="55017-160">`-band`, `-bnot`</span></span> |<span data-ttu-id="55017-161">Для побитовых операций</span><span class="sxs-lookup"><span data-stu-id="55017-161">For bitwise operations</span></span>                 |
|<span data-ttu-id="55017-162">5</span><span class="sxs-lookup"><span data-stu-id="55017-162">5</span></span>         | <span data-ttu-id="55017-163">`-bor`, `-bxor`</span><span class="sxs-lookup"><span data-stu-id="55017-163">`-bor`, `-bxor`</span></span>  |<span data-ttu-id="55017-164">Для побитовых операций</span><span class="sxs-lookup"><span data-stu-id="55017-164">For bitwise operations</span></span>                 |
|<span data-ttu-id="55017-165">5</span><span class="sxs-lookup"><span data-stu-id="55017-165">5</span></span>         | <span data-ttu-id="55017-166">`-shr`, `-shl`</span><span class="sxs-lookup"><span data-stu-id="55017-166">`-shr`, `-shl`</span></span>   |<span data-ttu-id="55017-167">Для побитовых операций</span><span class="sxs-lookup"><span data-stu-id="55017-167">For bitwise operations</span></span>                 |

<span data-ttu-id="55017-168">PowerShell обрабатывает выражения слева направо в соответствии с правилами приоритета.</span><span class="sxs-lookup"><span data-stu-id="55017-168">PowerShell processes the expressions from left to right according to the precedence rules.</span></span> <span data-ttu-id="55017-169">В следующих примерах показан результат применения правил приоритета.</span><span class="sxs-lookup"><span data-stu-id="55017-169">The following examples show the effect of the precedence rules:</span></span>

|<span data-ttu-id="55017-170">Выражение</span><span class="sxs-lookup"><span data-stu-id="55017-170">Expression</span></span> |<span data-ttu-id="55017-171">Результат</span><span class="sxs-lookup"><span data-stu-id="55017-171">Result</span></span>|
|-----------|------|
|`3+6/3*4`  |`11`  |
|`3+6/(3*4)`|`3.5` |
|`(3+6)/3*4`|`12`  |

<span data-ttu-id="55017-172">Порядок, в котором PowerShell вычисляет выражения, может отличаться от других используемых языков программирования и сценариев.</span><span class="sxs-lookup"><span data-stu-id="55017-172">The order in which PowerShell evaluates expressions might differ from other programming and scripting languages that you have used.</span></span> <span data-ttu-id="55017-173">В следующем примере показана сложная инструкция присваивания.</span><span class="sxs-lookup"><span data-stu-id="55017-173">The following example shows a complicated assignment statement.</span></span>

```powershell
$a = 0
$b = @(1,2)
$c = @(-1,-2)

$b[$a] = $c[$a++]
```

<span data-ttu-id="55017-174">В этом примере выражение `$a++` вычисляется раньше `$b[$a]` .</span><span class="sxs-lookup"><span data-stu-id="55017-174">In this example, the expression `$a++` is evaluated before `$b[$a]`.</span></span>
<span data-ttu-id="55017-175">Вычисление `$a++` изменяет значение `$a` после его использования в операторе `$c[$a++]` , но до того, как оно будет использовано в `$b[$a]` .</span><span class="sxs-lookup"><span data-stu-id="55017-175">Evaluating `$a++` changes the value of `$a` after it is used in the statement `$c[$a++]`; but, before it is used in `$b[$a]`.</span></span> <span data-ttu-id="55017-176">Переменная `$a` в `$b[$a]` равно, а `1` не `0` ; поэтому оператор присваивает значение `$b[1]` , а не `$b[0]` .</span><span class="sxs-lookup"><span data-stu-id="55017-176">The variable `$a` in `$b[$a]` equals `1`, not `0`; so, the statement assigns a value to `$b[1]`, not `$b[0]`.</span></span>

<span data-ttu-id="55017-177">Приведенный выше код эквивалентен:</span><span class="sxs-lookup"><span data-stu-id="55017-177">The above code is equivalent to:</span></span>

```powershell
$a = 0
$b = @(1,2)
$c = @(-1,-2)

$tmp = $c[$a]
$a = $a + 1
$b[$a] = $tmp
```

## <a name="division-and-rounding"></a><span data-ttu-id="55017-178">ДЕЛЕНИЕ И ОКРУГЛЕНИЕ</span><span class="sxs-lookup"><span data-stu-id="55017-178">DIVISION AND ROUNDING</span></span>

<span data-ttu-id="55017-179">Если частная операция деления является целым числом, PowerShell Округляет значение до ближайшего целого числа.</span><span class="sxs-lookup"><span data-stu-id="55017-179">When the quotient of a division operation is an integer, PowerShell rounds the value to the nearest integer.</span></span> <span data-ttu-id="55017-180">Если значение равно `.5` , оно округляет до ближайшего четного целого числа.</span><span class="sxs-lookup"><span data-stu-id="55017-180">When the value is `.5`, it rounds to the nearest even integer.</span></span>

<span data-ttu-id="55017-181">В следующем примере показан результат округления до ближайшего четного целого числа.</span><span class="sxs-lookup"><span data-stu-id="55017-181">The following example shows the effect of rounding to the nearest even integer.</span></span>

|<span data-ttu-id="55017-182">Выражение</span><span class="sxs-lookup"><span data-stu-id="55017-182">Expression</span></span>      |<span data-ttu-id="55017-183">Результат</span><span class="sxs-lookup"><span data-stu-id="55017-183">Result</span></span>|
|----------------|------|
|`[int]( 5 / 2 )`|`2`   |
|`[int]( 7 / 2 )`|`4`   |

<span data-ttu-id="55017-184">Обратите внимание, что **_5/2_ = 2,5** округляется до **2**.</span><span class="sxs-lookup"><span data-stu-id="55017-184">Notice how **_5/2_ = 2.5** gets rounded to **2**.</span></span> <span data-ttu-id="55017-185">Но **_7/2_ = 3,5** округляется до **4**.</span><span class="sxs-lookup"><span data-stu-id="55017-185">But, **_7/2_ = 3.5** gets rounded to **4**.</span></span>

<span data-ttu-id="55017-186">Можно использовать класс, `[Math]` чтобы получить разное поведение округления.</span><span class="sxs-lookup"><span data-stu-id="55017-186">You can use the `[Math]` class to get different rounding behavior.</span></span>

|                          <span data-ttu-id="55017-187">Выражение</span><span class="sxs-lookup"><span data-stu-id="55017-187">Expression</span></span>                          | <span data-ttu-id="55017-188">Результат</span><span class="sxs-lookup"><span data-stu-id="55017-188">Result</span></span> |
| ------------------------------------------------------------ | ------ |
| `[int][Math]::Round(5 / 2,[MidpointRounding]::AwayFromZero)` | `3`    |
| `[int][Math]::Ceiling(5 / 2)`                                | `3`    |
| `[int][Math]::Floor(5 / 2)`                                  | `2`    |

<span data-ttu-id="55017-189">Дополнительные сведения см. в описании метода [Math. Round](/dotnet/api/system.math.round) .</span><span class="sxs-lookup"><span data-stu-id="55017-189">For more information, see the [Math.Round](/dotnet/api/system.math.round) method.</span></span>

## <a name="adding-and-multiplying-non-numeric-types"></a><span data-ttu-id="55017-190">ДОБАВЛЕНИЕ И УМНОЖЕНИЕ НЕЧИСЛОВЫХ ТИПОВ</span><span class="sxs-lookup"><span data-stu-id="55017-190">ADDING AND MULTIPLYING NON-NUMERIC TYPES</span></span>

<span data-ttu-id="55017-191">Можно добавлять числа, строки, массивы и хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="55017-191">You can add numbers, strings, arrays, and hash tables.</span></span> <span data-ttu-id="55017-192">И можно умножить числа, строки и массивы.</span><span class="sxs-lookup"><span data-stu-id="55017-192">And, you can multiply numbers, strings, and arrays.</span></span> <span data-ttu-id="55017-193">Однако нельзя умножить хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="55017-193">However, you cannot multiply hash tables.</span></span>

<span data-ttu-id="55017-194">При добавлении строк, массивов или хэш-таблиц элементы объединяются.</span><span class="sxs-lookup"><span data-stu-id="55017-194">When you add strings, arrays, or hash tables, the elements are concatenated.</span></span> <span data-ttu-id="55017-195">При сцеплении коллекций, таких как массивы или хэш-таблицы, создается новый объект, содержащий объекты из обеих коллекций.</span><span class="sxs-lookup"><span data-stu-id="55017-195">When you concatenate collections, such as arrays or hash tables, a new object is created that contains the objects from both collections.</span></span> <span data-ttu-id="55017-196">При попытке объединить хэш-таблицы с одним и тем же ключом операция завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="55017-196">If you try to concatenate hash tables that have the same key, the operation fails.</span></span>

<span data-ttu-id="55017-197">Например, следующие команды создают два массива, а затем добавляют их:</span><span class="sxs-lookup"><span data-stu-id="55017-197">For example, the following commands create two arrays and then add them:</span></span>

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

<span data-ttu-id="55017-198">Также можно выполнять арифметические операции с объектами различных типов.</span><span class="sxs-lookup"><span data-stu-id="55017-198">You can also perform arithmetic operations on objects of different types.</span></span>
<span data-ttu-id="55017-199">Операция, выполняемая PowerShell, определяется Microsoft .NET типом платформы самого левого объекта в операции.</span><span class="sxs-lookup"><span data-stu-id="55017-199">The operation that PowerShell performs is determined by the Microsoft .NET Framework type of the leftmost object in the operation.</span></span> <span data-ttu-id="55017-200">PowerShell пытается преобразовать все объекты в операции в тип платформа .NET Framework первого объекта.</span><span class="sxs-lookup"><span data-stu-id="55017-200">PowerShell tries to convert all the objects in the operation to the .NET Framework type of the first object.</span></span> <span data-ttu-id="55017-201">Если при преобразовании объектов он будет выполнен, он выполняет операцию, соответствующую типу платформа .NET Framework первого объекта.</span><span class="sxs-lookup"><span data-stu-id="55017-201">If it succeeds in converting the objects, it performs the operation appropriate to the .NET Framework type of the first object.</span></span> <span data-ttu-id="55017-202">Если не удается преобразовать ни один из объектов, операция завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="55017-202">If it fails to convert any of the objects, the operation fails.</span></span>

<span data-ttu-id="55017-203">В следующих примерах демонстрируется использование операторов сложения и умножения. в операциях, включающих различные типы объектов.</span><span class="sxs-lookup"><span data-stu-id="55017-203">The following examples demonstrate the use of the addition and multiplication operators; in operations that include different object types.</span></span> <span data-ttu-id="55017-204">Предположим `$array = 1,2,3` :</span><span class="sxs-lookup"><span data-stu-id="55017-204">Assume `$array = 1,2,3`:</span></span>

|<span data-ttu-id="55017-205">Выражение</span><span class="sxs-lookup"><span data-stu-id="55017-205">Expression</span></span>       |<span data-ttu-id="55017-206">Результат</span><span class="sxs-lookup"><span data-stu-id="55017-206">Result</span></span>                 |
|-----------------|-----------------------|
|`"file" + 16`    |`file16`               |
|`$array + 16`    |<span data-ttu-id="55017-207">`1`,`2`,`3`,`16`</span><span class="sxs-lookup"><span data-stu-id="55017-207">`1`,`2`,`3`,`16`</span></span>       |
|`$array + "file"`|<span data-ttu-id="55017-208">`1`,`2`,`3`,`file`</span><span class="sxs-lookup"><span data-stu-id="55017-208">`1`,`2`,`3`,`file`</span></span>     |
|`$array * 2`     |<span data-ttu-id="55017-209">`1`,`2`,`3`,`1`,`2`,`3`</span><span class="sxs-lookup"><span data-stu-id="55017-209">`1`,`2`,`3`,`1`,`2`,`3`</span></span>|
|`"file" * 3`     |`filefilefile`         |

<span data-ttu-id="55017-210">Поскольку метод, используемый для вычисления инструкций, определяется крайним левым объектом, Добавление и умножение в PowerShell не строго коммутативной.</span><span class="sxs-lookup"><span data-stu-id="55017-210">Because the method that is used to evaluate statements is determined by the leftmost object, addition and multiplication in PowerShell are not strictly commutative.</span></span> <span data-ttu-id="55017-211">Например, не `(a + b)` всегда равно и не `(b + a)` `(ab)` всегда равно `(ba)` .</span><span class="sxs-lookup"><span data-stu-id="55017-211">For example, `(a + b)` does not always equal `(b + a)`, and `(ab)` does not always equal `(ba)`.</span></span>

<span data-ttu-id="55017-212">Этот принцип демонстрируется в следующих примерах:</span><span class="sxs-lookup"><span data-stu-id="55017-212">The following examples demonstrate this principle:</span></span>

|<span data-ttu-id="55017-213">Выражение</span><span class="sxs-lookup"><span data-stu-id="55017-213">Expression</span></span>   |<span data-ttu-id="55017-214">Результат</span><span class="sxs-lookup"><span data-stu-id="55017-214">Result</span></span>                                               |
|-------------|-----------------------------------------------------|
|`"file" + 16`|`file16`                                             |
|`16 + "file"`|`Cannot convert value "file" to type "System.Int32".`|
|             |`Error: "Input string was not in a correct format."` |
|             |`At line:1 char:1`                                   |
|             |<span data-ttu-id="55017-215">+ 16 + "файл"</span><span class="sxs-lookup"><span data-stu-id="55017-215">+ 16 + "file"\`</span></span>                                       |

<span data-ttu-id="55017-216">Хэш-таблицы являются слегка отличающимися регистром.</span><span class="sxs-lookup"><span data-stu-id="55017-216">Hash tables are a slightly different case.</span></span> <span data-ttu-id="55017-217">Можно добавить хэш-таблицы в другую хэш-таблицу при условии, что в добавленных хэш-таблицах нет повторяющихся ключей.</span><span class="sxs-lookup"><span data-stu-id="55017-217">You can add hash tables to another hash table, as long as, the added hash tables don't have duplicate keys.</span></span>

<span data-ttu-id="55017-218">В следующем примере показано, как добавить хэш-таблицы друг в друга.</span><span class="sxs-lookup"><span data-stu-id="55017-218">The following example show how to add hash tables to each other.</span></span>

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

<span data-ttu-id="55017-219">В следующем примере возникает ошибка, так как один из ключей дублируется в обеих хэш-таблицах.</span><span class="sxs-lookup"><span data-stu-id="55017-219">The following example throws an error because one of the keys is duplicated in both hash tables.</span></span>

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

<span data-ttu-id="55017-220">Кроме того, можно добавить хэш-таблицу в массив. и вся хэш-таблица преобразуется в элемент массива.</span><span class="sxs-lookup"><span data-stu-id="55017-220">Also, you can add a hash table to an array; and, the entire hash table becomes an item in the array.</span></span>

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

<span data-ttu-id="55017-221">Однако в хэш-таблицу нельзя добавить любой другой тип.</span><span class="sxs-lookup"><span data-stu-id="55017-221">However, you cannot add any other type to a hash table.</span></span>

```powershell
$hash1 + 2
```

```output
A hash table can only be added to another hash table.
At line:3 char:1
+ $hash1 + 2
```

<span data-ttu-id="55017-222">Хотя операторы сложения очень полезны, используйте операторы присваивания для добавления элементов в хэш-таблицы и массивы.</span><span class="sxs-lookup"><span data-stu-id="55017-222">Although the addition operators are very useful, use the assignment operators to add elements to hash tables and arrays.</span></span> <span data-ttu-id="55017-223">Дополнительные сведения см. в разделе [about_assignment_operators](about_Assignment_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="55017-223">For more information see [about_assignment_operators](about_Assignment_Operators.md).</span></span> <span data-ttu-id="55017-224">В следующих примерах для `+=` добавления элементов в массив используется оператор присваивания:</span><span class="sxs-lookup"><span data-stu-id="55017-224">The following examples use the `+=` assignment operator to add items to an array:</span></span>

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

## <a name="type-conversion-to-accommodate-result"></a><span data-ttu-id="55017-225">ПРЕОБРАЗОВАНИЕ ТИПОВ В СООТВЕТСТВИИ С РЕЗУЛЬТАТОМ</span><span class="sxs-lookup"><span data-stu-id="55017-225">TYPE CONVERSION TO ACCOMMODATE RESULT</span></span>

<span data-ttu-id="55017-226">PowerShell автоматически выбирает платформа .NET Framework числовой тип, который наилучшим образом выражает результат без потери точности.</span><span class="sxs-lookup"><span data-stu-id="55017-226">PowerShell automatically selects the .NET Framework numeric type that best expresses the result without losing precision.</span></span> <span data-ttu-id="55017-227">Пример:</span><span class="sxs-lookup"><span data-stu-id="55017-227">For example:</span></span>

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

<span data-ttu-id="55017-228">Если результат операции слишком велик для типа, тип результата расширяется в соответствии с результатом, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="55017-228">If the result of an operation is too large for the type, the type of the result is widened to accommodate the result, as in the following example:</span></span>

```powershell
(512MB).GetType().FullName
(512MB * 512MB).GetType().FullName
```

```output
System.Int32
System.Double
```

<span data-ttu-id="55017-229">Тип результата не обязательно будет таким же, как и один из операндов.</span><span class="sxs-lookup"><span data-stu-id="55017-229">The type of the result will not necessarily be the same as one of the operands.</span></span> <span data-ttu-id="55017-230">В следующем примере отрицательное значение не может быть приведено к целому числу без знака, а целое число без знака слишком велико для приведения к `Int32` :</span><span class="sxs-lookup"><span data-stu-id="55017-230">In the following example, the negative value cannot be cast to an unsigned integer, and the unsigned integer is too large to be cast to `Int32`:</span></span>

```powershell
([int32]::minvalue + [uint32]::maxvalue).gettype().fullname
```

```output
System.Int64
```

<span data-ttu-id="55017-231">В этом примере `Int64` может соответствовать обоим типам.</span><span class="sxs-lookup"><span data-stu-id="55017-231">In this example, `Int64` can accommodate both types.</span></span>

<span data-ttu-id="55017-232">`System.Decimal`Тип является исключением.</span><span class="sxs-lookup"><span data-stu-id="55017-232">The `System.Decimal` type is an exception.</span></span> <span data-ttu-id="55017-233">Если любой из операндов имеет десятичный тип, результат будет иметь тип Decimal.</span><span class="sxs-lookup"><span data-stu-id="55017-233">If either operand has the Decimal type, the result will be of the Decimal type.</span></span> <span data-ttu-id="55017-234">Если результат слишком велик для типа Decimal, он не будет приведен к типу Double.</span><span class="sxs-lookup"><span data-stu-id="55017-234">If the result is too large for the Decimal type, it will not be cast to Double.</span></span> <span data-ttu-id="55017-235">Вместо этого возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="55017-235">Instead, an error results.</span></span>

|<span data-ttu-id="55017-236">Выражение</span><span class="sxs-lookup"><span data-stu-id="55017-236">Expression</span></span>               |<span data-ttu-id="55017-237">Результат</span><span class="sxs-lookup"><span data-stu-id="55017-237">Result</span></span>                                         |
|-------------------------|-----------------------------------------------|
|`[Decimal]::maxvalue`    |`79228162514264337593543950335`                |
|`[Decimal]::maxvalue + 1`|`Value was either too large or too small for a`|
|                         |`Decimal.`                                     |

## <a name="arithmetic-operators-and-variables"></a><span data-ttu-id="55017-238">АРИФМЕТИЧЕСКИЕ ОПЕРАТОРЫ И ПЕРЕМЕННЫЕ</span><span class="sxs-lookup"><span data-stu-id="55017-238">ARITHMETIC OPERATORS AND VARIABLES</span></span>

<span data-ttu-id="55017-239">Кроме того, арифметические операторы можно использовать с переменными.</span><span class="sxs-lookup"><span data-stu-id="55017-239">You can also use arithmetic operators with variables.</span></span> <span data-ttu-id="55017-240">Операторы действуют на значения переменных.</span><span class="sxs-lookup"><span data-stu-id="55017-240">The operators act on the values of the variables.</span></span> <span data-ttu-id="55017-241">В следующих примерах демонстрируется использование арифметических операторов с переменными:</span><span class="sxs-lookup"><span data-stu-id="55017-241">The following examples demonstrate the use of arithmetic operators with variables:</span></span>

| <span data-ttu-id="55017-242">Выражение</span><span class="sxs-lookup"><span data-stu-id="55017-242">Expression</span></span>                                    |<span data-ttu-id="55017-243">Результат</span><span class="sxs-lookup"><span data-stu-id="55017-243">Result</span></span>      |
|-----------------------------------------------|------------|
|`$intA = 6`<br/>`$intB = 4`<br/>`$intA + $intB`|`10`        |
|`$a = "Power"`<br/>`$b = "Shell"`<br/>`$a + $b`|`PowerShell`|

## <a name="arithmetic-operators-and-commands"></a><span data-ttu-id="55017-244">АРИФМЕТИЧЕСКИЕ ОПЕРАТОРЫ И КОМАНДЫ</span><span class="sxs-lookup"><span data-stu-id="55017-244">ARITHMETIC OPERATORS AND COMMANDS</span></span>

<span data-ttu-id="55017-245">Обычно арифметические операторы используются в выражениях с числами, строками и массивами.</span><span class="sxs-lookup"><span data-stu-id="55017-245">Typically, you use the arithmetic operators in expressions with numbers, strings, and arrays.</span></span> <span data-ttu-id="55017-246">Однако арифметические операторы также можно использовать с объектами, возвращаемыми командами, и со свойствами этих объектов.</span><span class="sxs-lookup"><span data-stu-id="55017-246">However, you can also use arithmetic operators with the objects that commands return and with the properties of those objects.</span></span>

<span data-ttu-id="55017-247">В следующих примерах показано, как использовать арифметические операторы в выражениях с командами PowerShell:</span><span class="sxs-lookup"><span data-stu-id="55017-247">The following examples show how to use the arithmetic operators in expressions with PowerShell commands:</span></span>

```powershell
(get-date) + (new-timespan -day 1)
```

<span data-ttu-id="55017-248">Оператор скобки вызывает принудительное вычисление `get-date` командлета и вычисление `new-timespan -day 1` выражения командлета в указанном порядке.</span><span class="sxs-lookup"><span data-stu-id="55017-248">The parenthesis operator forces the evaluation of the `get-date` cmdlet and the evaluation of the `new-timespan -day 1` cmdlet expression, in that order.</span></span> <span data-ttu-id="55017-249">Затем оба результата добавляются с помощью `+` оператора.</span><span class="sxs-lookup"><span data-stu-id="55017-249">Both results are then added using the `+` operator.</span></span>

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

<span data-ttu-id="55017-250">В приведенном выше выражении каждое рабочее пространство процесса ( `$_.ws` ) умножается на `2` ; и результат сравнивается с, `50mb` чтобы узнать, больше ли оно.</span><span class="sxs-lookup"><span data-stu-id="55017-250">In the above expression, each process working space (`$_.ws`) is multiplied by `2`; and, the result, compared against `50mb` to see if it is greater than that.</span></span>

## <a name="bitwise-operators"></a><span data-ttu-id="55017-251">Побитовые операторы</span><span class="sxs-lookup"><span data-stu-id="55017-251">Bitwise Operators</span></span>

<span data-ttu-id="55017-252">PowerShell поддерживает стандартные битовые операторы, включая битовые и ( `-bAnd` ), включающие и исключающие побитовые ОПЕРАТОРЫ or ( `-bOr` и `-bXor` ), а также побитовое не ( `-bNot` ).</span><span class="sxs-lookup"><span data-stu-id="55017-252">PowerShell supports the standard bitwise operators, including bitwise-AND (`-bAnd`), the inclusive and exclusive bitwise-OR operators (`-bOr` and `-bXor`), and bitwise-NOT (`-bNot`).</span></span>

<span data-ttu-id="55017-253">Начиная с PowerShell 2,0, все битовые операторы работают с 64-разрядными целыми числами.</span><span class="sxs-lookup"><span data-stu-id="55017-253">Beginning in PowerShell 2.0, all bitwise operators work with 64-bit integers.</span></span>

<span data-ttu-id="55017-254">Начиная с PowerShell 3,0, `-shr` `-shl` для поддержки побитовых арифметических операций в PowerShell появились (Shift-Right) и (Shift-Left).</span><span class="sxs-lookup"><span data-stu-id="55017-254">Beginning in PowerShell 3.0, the `-shr` (shift-right) and `-shl` (shift-left) are introduced to support bitwise arithmetic in PowerShell.</span></span>

<span data-ttu-id="55017-255">PowerShell поддерживает следующие Побитовые операторы.</span><span class="sxs-lookup"><span data-stu-id="55017-255">PowerShell supports the following bitwise operators.</span></span>

| <span data-ttu-id="55017-256">Оператор</span><span class="sxs-lookup"><span data-stu-id="55017-256">Operator</span></span> | <span data-ttu-id="55017-257">Описание</span><span class="sxs-lookup"><span data-stu-id="55017-257">Description</span></span>            | <span data-ttu-id="55017-258">Выражение</span><span class="sxs-lookup"><span data-stu-id="55017-258">Expression</span></span>   | <span data-ttu-id="55017-259">Результат</span><span class="sxs-lookup"><span data-stu-id="55017-259">Result</span></span> |
| -------- | ---------------------- | ------------ | ------ |
| `-band`  | <span data-ttu-id="55017-260">Побитовое И</span><span class="sxs-lookup"><span data-stu-id="55017-260">Bitwise AND</span></span>            | `10 -band 3` | <span data-ttu-id="55017-261">2</span><span class="sxs-lookup"><span data-stu-id="55017-261">2</span></span>      |
| `-bor`   | <span data-ttu-id="55017-262">Побитовое или (включительно)</span><span class="sxs-lookup"><span data-stu-id="55017-262">Bitwise OR (inclusive)</span></span> | `10 -bor 3`  | <span data-ttu-id="55017-263">11</span><span class="sxs-lookup"><span data-stu-id="55017-263">11</span></span>     |
| `-bxor`  | <span data-ttu-id="55017-264">Побитовое или (Эксклюзивное)</span><span class="sxs-lookup"><span data-stu-id="55017-264">Bitwise OR (exclusive)</span></span> | `10 -bxor 3` | <span data-ttu-id="55017-265">9</span><span class="sxs-lookup"><span data-stu-id="55017-265">9</span></span>      |
| `-bnot`  | <span data-ttu-id="55017-266">Побитовое НЕ</span><span class="sxs-lookup"><span data-stu-id="55017-266">Bitwise NOT</span></span>            | `-bNot 10`   | <span data-ttu-id="55017-267">-11</span><span class="sxs-lookup"><span data-stu-id="55017-267">-11</span></span>    |
| `-shl`   | <span data-ttu-id="55017-268">Сдвиг влево</span><span class="sxs-lookup"><span data-stu-id="55017-268">Shift-left</span></span>             | `102 -shl 2` | <span data-ttu-id="55017-269">408</span><span class="sxs-lookup"><span data-stu-id="55017-269">408</span></span>    |
| `-shr`   | <span data-ttu-id="55017-270">Shift справа</span><span class="sxs-lookup"><span data-stu-id="55017-270">Shift-right</span></span>            | `102 -shr 1` | <span data-ttu-id="55017-271">51</span><span class="sxs-lookup"><span data-stu-id="55017-271">51</span></span>     |

<span data-ttu-id="55017-272">Битовые операторы работают с двоичным форматом значения.</span><span class="sxs-lookup"><span data-stu-id="55017-272">Bitwise operators act on the binary format of a value.</span></span> <span data-ttu-id="55017-273">Например, битовая структура для числа 10 — 00001010 (на основе 1 байта), а битовая структура для числа 3 — 00000011.</span><span class="sxs-lookup"><span data-stu-id="55017-273">For example, the bit structure for the number 10 is 00001010 (based on 1 byte), and the bit structure for the number 3 is 00000011.</span></span> <span data-ttu-id="55017-274">При использовании побитового оператора для сравнения 10 и 3 отдельные биты в каждом байте сравниваются.</span><span class="sxs-lookup"><span data-stu-id="55017-274">When you use a bitwise operator to compare 10 to 3, the individual bits in each byte are compared.</span></span>

<span data-ttu-id="55017-275">В побитовой операции AND полученный бит устанавливается в значение 1 только в том случае, если оба входных бита равны 1.</span><span class="sxs-lookup"><span data-stu-id="55017-275">In a bitwise AND operation, the resulting bit is set to 1 only when both input bits are 1.</span></span>

```
1010      (10)
0011      ( 3)
--------------  bAND
0010      ( 2)
```

<span data-ttu-id="55017-276">При выполнении операции побитового или (включительно) полученный бит устанавливается в значение 1, если один или оба входных бита равны 1.</span><span class="sxs-lookup"><span data-stu-id="55017-276">In a bitwise OR (inclusive) operation, the resulting bit is set to 1 when either or both input bits are 1.</span></span> <span data-ttu-id="55017-277">Полученный бит имеет значение 0, только если оба входных бита имеют значение 0.</span><span class="sxs-lookup"><span data-stu-id="55017-277">The resulting bit is set to 0 only when both input bits are set to 0.</span></span>

```
1010      (10)
0011      ( 3)
--------------  bOR (inclusive)
1011      (11)
```

<span data-ttu-id="55017-278">В побитовой операции или (исключающей) полученный бит устанавливается в значение 1 только в том случае, если один входной бит равен 1.</span><span class="sxs-lookup"><span data-stu-id="55017-278">In a bitwise OR (exclusive) operation, the resulting bit is set to 1 only when one input bit is 1.</span></span>

```
1010      (10)
0011      ( 3)
--------------  bXOR (exclusive)
1001      ( 9)
```

<span data-ttu-id="55017-279">Оператор побитового не является унарным оператором, который создает двоичный дополнение к значению.</span><span class="sxs-lookup"><span data-stu-id="55017-279">The bitwise NOT operator is a unary operator that produces the binary complement of the value.</span></span> <span data-ttu-id="55017-280">Бит 1 имеет значение 0, а бит 0 имеет значение 1.</span><span class="sxs-lookup"><span data-stu-id="55017-280">A bit of 1 is set to 0 and a bit of 0 is set to 1.</span></span>

<span data-ttu-id="55017-281">Например, дополняющий двоичный код 0 равен-1, максимальное целое число без знака (0xFFFFFFFF) и двоичное дополнение-1 — 0.</span><span class="sxs-lookup"><span data-stu-id="55017-281">For example, the binary complement of 0 is -1, the maximum unsigned integer (0xffffffff), and the binary complement of -1 is 0.</span></span>

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

<span data-ttu-id="55017-282">В операции побитового сдвига влево все биты перемещаются слева, где n — это значение правого операнда.</span><span class="sxs-lookup"><span data-stu-id="55017-282">In a bitwise shift-left operation, all bits are moved "n" places to the left, where "n" is the value of the right operand.</span></span> <span data-ttu-id="55017-283">В место размещения вставляется ноль.</span><span class="sxs-lookup"><span data-stu-id="55017-283">A zero is inserted in the ones place.</span></span>

<span data-ttu-id="55017-284">Если левый операнд является целочисленным (32-разрядным) значением, младшие 5 разрядов правого операнда определяют, сколько битов левого операнда смещается.</span><span class="sxs-lookup"><span data-stu-id="55017-284">When the left operand is an Integer (32-bit) value, the lower 5 bits of the right operand determine how many bits of the left operand are shifted.</span></span>

<span data-ttu-id="55017-285">Если левый операнд является длинным (64-битным) значением, младшие 6 разрядов правого операнда определяют, сколько битов левого операнда смещается.</span><span class="sxs-lookup"><span data-stu-id="55017-285">When the left operand is a Long (64-bit) value, the lower 6 bits of the right operand determine how many bits of the left operand are shifted.</span></span>

|<span data-ttu-id="55017-286">Выражение</span><span class="sxs-lookup"><span data-stu-id="55017-286">Expression</span></span> |<span data-ttu-id="55017-287">Результат</span><span class="sxs-lookup"><span data-stu-id="55017-287">Result</span></span>|<span data-ttu-id="55017-288">Двоичный результат</span><span class="sxs-lookup"><span data-stu-id="55017-288">Binary Result</span></span>|
|-----------|------|-------------|
|`21 -shl 0`|<span data-ttu-id="55017-289">21</span><span class="sxs-lookup"><span data-stu-id="55017-289">21</span></span>    |<span data-ttu-id="55017-290">0001 0101</span><span class="sxs-lookup"><span data-stu-id="55017-290">0001 0101</span></span>    |
|`21 -shl 1`|<span data-ttu-id="55017-291">42</span><span class="sxs-lookup"><span data-stu-id="55017-291">42</span></span>    |<span data-ttu-id="55017-292">0010 1010</span><span class="sxs-lookup"><span data-stu-id="55017-292">0010 1010</span></span>    |
|`21 -shl 2`|<span data-ttu-id="55017-293">84</span><span class="sxs-lookup"><span data-stu-id="55017-293">84</span></span>    |<span data-ttu-id="55017-294">0101 0100</span><span class="sxs-lookup"><span data-stu-id="55017-294">0101 0100</span></span>    |

<span data-ttu-id="55017-295">В операции побитового сдвига вправо все биты перемещаются справа, где "n" указывается правым операндом.</span><span class="sxs-lookup"><span data-stu-id="55017-295">In a bitwise shift-right operation, all bits are moved "n" places to the right, where "n" is specified by the right operand.</span></span> <span data-ttu-id="55017-296">Оператор сдвига вправо (-SHR) вставляет ноль в крайнее левое место при перемещении положительного или неподписанного значения вправо.</span><span class="sxs-lookup"><span data-stu-id="55017-296">The shift-right operator (-shr) inserts a zero in the left-most place when shifting a positive or unsigned value to the right.</span></span>

<span data-ttu-id="55017-297">Если левый операнд является целочисленным (32-разрядным) значением, младшие 5 разрядов правого операнда определяют, сколько битов левого операнда смещается.</span><span class="sxs-lookup"><span data-stu-id="55017-297">When the left operand is an Integer (32-bit) value, the lower 5 bits of the right operand determine how many bits of the left operand are shifted.</span></span>

<span data-ttu-id="55017-298">Если левый операнд является длинным (64-битным) значением, младшие 6 разрядов правого операнда определяют, сколько битов левого операнда смещается.</span><span class="sxs-lookup"><span data-stu-id="55017-298">When the left operand is a Long (64-bit) value, the lower 6 bits of the right operand determine how many bits of the left operand are shifted.</span></span>

|<span data-ttu-id="55017-299">Выражение</span><span class="sxs-lookup"><span data-stu-id="55017-299">Expression</span></span>              |<span data-ttu-id="55017-300">Результат</span><span class="sxs-lookup"><span data-stu-id="55017-300">Result</span></span>      |<span data-ttu-id="55017-301">Двоичные данные</span><span class="sxs-lookup"><span data-stu-id="55017-301">Binary</span></span>     |<span data-ttu-id="55017-302">Hex</span><span class="sxs-lookup"><span data-stu-id="55017-302">Hex</span></span>         |
|------------------------|------------|-----------|------------|
|`21 -shr 0`             | <span data-ttu-id="55017-303">21</span><span class="sxs-lookup"><span data-stu-id="55017-303">21</span></span>         | <span data-ttu-id="55017-304">0001 0101</span><span class="sxs-lookup"><span data-stu-id="55017-304">0001 0101</span></span> | <span data-ttu-id="55017-305">0x15</span><span class="sxs-lookup"><span data-stu-id="55017-305">0x15</span></span>       |
|`21 -shr 1`             | <span data-ttu-id="55017-306">10</span><span class="sxs-lookup"><span data-stu-id="55017-306">10</span></span>         | <span data-ttu-id="55017-307">0000 1010</span><span class="sxs-lookup"><span data-stu-id="55017-307">0000 1010</span></span> | <span data-ttu-id="55017-308">0x0A</span><span class="sxs-lookup"><span data-stu-id="55017-308">0x0A</span></span>       |
|`21 -shr 2`             | <span data-ttu-id="55017-309">5</span><span class="sxs-lookup"><span data-stu-id="55017-309">5</span></span>          | <span data-ttu-id="55017-310">0000 0101</span><span class="sxs-lookup"><span data-stu-id="55017-310">0000 0101</span></span> | <span data-ttu-id="55017-311">0x05</span><span class="sxs-lookup"><span data-stu-id="55017-311">0x05</span></span>       |
|`21 -shr 31`            | <span data-ttu-id="55017-312">0</span><span class="sxs-lookup"><span data-stu-id="55017-312">0</span></span>          | <span data-ttu-id="55017-313">0000 0000</span><span class="sxs-lookup"><span data-stu-id="55017-313">0000 0000</span></span> | <span data-ttu-id="55017-314">0x00</span><span class="sxs-lookup"><span data-stu-id="55017-314">0x00</span></span>       |
|`21 -shr 32`            | <span data-ttu-id="55017-315">21</span><span class="sxs-lookup"><span data-stu-id="55017-315">21</span></span>         | <span data-ttu-id="55017-316">0001 0101</span><span class="sxs-lookup"><span data-stu-id="55017-316">0001 0101</span></span> | <span data-ttu-id="55017-317">0x15</span><span class="sxs-lookup"><span data-stu-id="55017-317">0x15</span></span>       |
|`21 -shr 64`            | <span data-ttu-id="55017-318">21</span><span class="sxs-lookup"><span data-stu-id="55017-318">21</span></span>         | <span data-ttu-id="55017-319">0001 0101</span><span class="sxs-lookup"><span data-stu-id="55017-319">0001 0101</span></span> | <span data-ttu-id="55017-320">0x15</span><span class="sxs-lookup"><span data-stu-id="55017-320">0x15</span></span>       |
|`21 -shr 65`            | <span data-ttu-id="55017-321">10</span><span class="sxs-lookup"><span data-stu-id="55017-321">10</span></span>         | <span data-ttu-id="55017-322">0000 1010</span><span class="sxs-lookup"><span data-stu-id="55017-322">0000 1010</span></span> | <span data-ttu-id="55017-323">0x0A</span><span class="sxs-lookup"><span data-stu-id="55017-323">0x0A</span></span>       |
|`21 -shr 66`            | <span data-ttu-id="55017-324">5</span><span class="sxs-lookup"><span data-stu-id="55017-324">5</span></span>          | <span data-ttu-id="55017-325">0000 0101</span><span class="sxs-lookup"><span data-stu-id="55017-325">0000 0101</span></span> | <span data-ttu-id="55017-326">0x05</span><span class="sxs-lookup"><span data-stu-id="55017-326">0x05</span></span>       |
|`[int]::MaxValue -shr 1`| <span data-ttu-id="55017-327">1073741823</span><span class="sxs-lookup"><span data-stu-id="55017-327">1073741823</span></span> |           | <span data-ttu-id="55017-328">0x3FFFFFFF</span><span class="sxs-lookup"><span data-stu-id="55017-328">0x3FFFFFFF</span></span> |
|`[int]::MinValue -shr 1`| <span data-ttu-id="55017-329">— 1073741824</span><span class="sxs-lookup"><span data-stu-id="55017-329">-1073741824</span></span>|           | <span data-ttu-id="55017-330">0xC0000000</span><span class="sxs-lookup"><span data-stu-id="55017-330">0xC0000000</span></span> |
|`-1 -shr 1`             | <span data-ttu-id="55017-331">-1</span><span class="sxs-lookup"><span data-stu-id="55017-331">-1</span></span>         |           | <span data-ttu-id="55017-332">0xFFFFFFFF</span><span class="sxs-lookup"><span data-stu-id="55017-332">0xFFFFFFFF</span></span> |

## <a name="see-also"></a><span data-ttu-id="55017-333">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="55017-333">SEE ALSO</span></span>

- [<span data-ttu-id="55017-334">about_arrays</span><span class="sxs-lookup"><span data-stu-id="55017-334">about_arrays</span></span>](about_Arrays.md)
- [<span data-ttu-id="55017-335">about_assignment_operators</span><span class="sxs-lookup"><span data-stu-id="55017-335">about_assignment_operators</span></span>](about_Assignment_Operators.md)
- [<span data-ttu-id="55017-336">about_comparison_operators</span><span class="sxs-lookup"><span data-stu-id="55017-336">about_comparison_operators</span></span>](about_Comparison_Operators.md)
- [<span data-ttu-id="55017-337">about_hash_tables</span><span class="sxs-lookup"><span data-stu-id="55017-337">about_hash_tables</span></span>](about_Hash_Tables.md)
- [<span data-ttu-id="55017-338">about_operators</span><span class="sxs-lookup"><span data-stu-id="55017-338">about_operators</span></span>](about_Operators.md)
- [<span data-ttu-id="55017-339">about_variables</span><span class="sxs-lookup"><span data-stu-id="55017-339">about_variables</span></span>](about_Variables.md)
- [<span data-ttu-id="55017-340">Get-Дата</span><span class="sxs-lookup"><span data-stu-id="55017-340">Get-Date</span></span>](xref:Microsoft.PowerShell.Utility.Get-Date)
- [<span data-ttu-id="55017-341">New-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="55017-341">New-TimeSpan</span></span>](xref:Microsoft.PowerShell.Utility.New-TimeSpan)
