---
description: Целочисленные и вещественные числовые литералы могут иметь суффиксы типа и множителя.
Locale: en-US
ms.date: 04/09/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_numeric_literals?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: О числовых литералах
ms.openlocfilehash: 99fa8c1a751551d028fe6df0b0cec94e07f19c59
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "93233145"
---
# <a name="about-numeric-literals"></a><span data-ttu-id="04743-103">О числовых литералах</span><span class="sxs-lookup"><span data-stu-id="04743-103">About numeric literals</span></span>

<span data-ttu-id="04743-104">Существует два вида числовых литералов: integer и Real.</span><span class="sxs-lookup"><span data-stu-id="04743-104">There are two kinds of numeric literals: integer and real.</span></span> <span data-ttu-id="04743-105">Оба могут иметь суффиксы типа и множителя.</span><span class="sxs-lookup"><span data-stu-id="04743-105">Both can have type and multiplier suffixes.</span></span>

## <a name="integer-literals"></a><span data-ttu-id="04743-106">Целочисленные литералы</span><span class="sxs-lookup"><span data-stu-id="04743-106">Integer literals</span></span>

<span data-ttu-id="04743-107">Целочисленные литералы могут быть записаны в десятичной или шестнадцатеричной нотации.</span><span class="sxs-lookup"><span data-stu-id="04743-107">Integer literals can be written in decimal or hexadecimal notation.</span></span> <span data-ttu-id="04743-108">Шестнадцатеричные литералы начинаются с префикса, `0x` чтобы отличать их от десятичных чисел.</span><span class="sxs-lookup"><span data-stu-id="04743-108">Hexadecimal literals are prefixed with `0x` to distinguish them from decimal numbers.</span></span>

<span data-ttu-id="04743-109">Целочисленные литералы могут иметь суффикс типа и суффикс множителя.</span><span class="sxs-lookup"><span data-stu-id="04743-109">Integer literals can have a type suffix and a multiplier suffix.</span></span>

| <span data-ttu-id="04743-110">Суффикс</span><span class="sxs-lookup"><span data-stu-id="04743-110">Suffix</span></span> |       <span data-ttu-id="04743-111">Значение</span><span class="sxs-lookup"><span data-stu-id="04743-111">Meaning</span></span>       |
| ------ | ------------------- |
| <span data-ttu-id="04743-112">l</span><span class="sxs-lookup"><span data-stu-id="04743-112">l</span></span>      | <span data-ttu-id="04743-113">тип данных Long</span><span class="sxs-lookup"><span data-stu-id="04743-113">long data type</span></span>      |
| <span data-ttu-id="04743-114">kb</span><span class="sxs-lookup"><span data-stu-id="04743-114">kb</span></span>     | <span data-ttu-id="04743-115">множитель в килобайтах</span><span class="sxs-lookup"><span data-stu-id="04743-115">kilobyte multiplier</span></span> |
| <span data-ttu-id="04743-116">mb</span><span class="sxs-lookup"><span data-stu-id="04743-116">mb</span></span>     | <span data-ttu-id="04743-117">множитель в мегабайтах</span><span class="sxs-lookup"><span data-stu-id="04743-117">megabyte multiplier</span></span> |
| <span data-ttu-id="04743-118">Гбайт</span><span class="sxs-lookup"><span data-stu-id="04743-118">gb</span></span>     | <span data-ttu-id="04743-119">множитель гигабайта</span><span class="sxs-lookup"><span data-stu-id="04743-119">gigabyte multiplier</span></span> |
| <span data-ttu-id="04743-120">Тбайт</span><span class="sxs-lookup"><span data-stu-id="04743-120">tb</span></span>     | <span data-ttu-id="04743-121">терабайт, множитель</span><span class="sxs-lookup"><span data-stu-id="04743-121">terabyte multiplier</span></span> |
| <span data-ttu-id="04743-122">МС</span><span class="sxs-lookup"><span data-stu-id="04743-122">pb</span></span>     | <span data-ttu-id="04743-123">множитель петабайтного уровня</span><span class="sxs-lookup"><span data-stu-id="04743-123">petabyte multiplier</span></span> |

<span data-ttu-id="04743-124">Тип целочисленного литерала определяется его значением, суффиксом типа и суффиксом числового множителя.</span><span class="sxs-lookup"><span data-stu-id="04743-124">The type of an integer literal is determined by its value, the type suffix, and the numeric multiplier suffix.</span></span>

<span data-ttu-id="04743-125">Для целочисленного литерала без суффикса типа:</span><span class="sxs-lookup"><span data-stu-id="04743-125">For an integer literal with no type suffix:</span></span>

- <span data-ttu-id="04743-126">Если значение может быть представлено типом `[int]` , то есть его типом.</span><span class="sxs-lookup"><span data-stu-id="04743-126">If the value can be represented by type `[int]`, that is its type.</span></span>
- <span data-ttu-id="04743-127">В противном случае, если значение может быть представлено типом `[long]` , то есть его тип.</span><span class="sxs-lookup"><span data-stu-id="04743-127">Otherwise, if the value can be represented by type `[long]`, that is its type.</span></span>
- <span data-ttu-id="04743-128">В противном случае, если значение может быть представлено типом `[decimal]` , то есть его тип.</span><span class="sxs-lookup"><span data-stu-id="04743-128">Otherwise, if the value can be represented by type `[decimal]`, that is its type.</span></span>
- <span data-ttu-id="04743-129">В противном случае он представлен типом `[double]` .</span><span class="sxs-lookup"><span data-stu-id="04743-129">Otherwise, it is represented by type `[double]`.</span></span>

<span data-ttu-id="04743-130">Для целочисленного литерала с суффиксом типа:</span><span class="sxs-lookup"><span data-stu-id="04743-130">For an integer literal with a type suffix:</span></span>

- <span data-ttu-id="04743-131">Если суффикс типа — `u` , а значение может быть представлено типом, `[int]` то его тип — `[int]` .</span><span class="sxs-lookup"><span data-stu-id="04743-131">If the type suffix is `u` and the value can be represented by type `[int]` then its type is `[int]`.</span></span>
- <span data-ttu-id="04743-132">Если суффикс типа — `u` , а значение может быть представлено типом, `[long]` то его тип — `[long]` .</span><span class="sxs-lookup"><span data-stu-id="04743-132">If the type suffix is `u` and the value can be represented by type `[long]` then its type is `[long]`.</span></span>
- <span data-ttu-id="04743-133">Если его значение может быть представлено указанным типом, то это тип.</span><span class="sxs-lookup"><span data-stu-id="04743-133">If its value can be represented by type specified then that is its type.</span></span>
- <span data-ttu-id="04743-134">В противном случае этот литерал имеет неправильный формат.</span><span class="sxs-lookup"><span data-stu-id="04743-134">Otherwise, that literal is malformed.</span></span>

## <a name="real-literals"></a><span data-ttu-id="04743-135">Вещественные литералы</span><span class="sxs-lookup"><span data-stu-id="04743-135">Real literals</span></span>

<span data-ttu-id="04743-136">Реальные литералы могут быть записаны только в десятичной нотации.</span><span class="sxs-lookup"><span data-stu-id="04743-136">Real literals can only be written in decimal notation.</span></span> <span data-ttu-id="04743-137">Эта нотация может содержать дробные значения, следующие за десятичной запятой и экспоненциальной нотацией, с использованием экспоненциальной части.</span><span class="sxs-lookup"><span data-stu-id="04743-137">This notation can include fractional values following a decimal point and scientific notation using an exponential part.</span></span>

<span data-ttu-id="04743-138">Экспоненциальная часть включает символ "e", за которым следует необязательный знак (+/-) и число, представляющее показатель степени.</span><span class="sxs-lookup"><span data-stu-id="04743-138">The exponential part includes an 'e' followed by an optional sign (+/-) and a number representing the exponent.</span></span> <span data-ttu-id="04743-139">Например, литеральное значение `1e2` равно числовому значению 100.</span><span class="sxs-lookup"><span data-stu-id="04743-139">For example, the literal value `1e2` equals the numeric value 100.</span></span>

<span data-ttu-id="04743-140">Реальные литералы могут иметь суффикс типа и суффикс множителя.</span><span class="sxs-lookup"><span data-stu-id="04743-140">Real literals can have a type suffix and a multiplier suffix.</span></span>

| <span data-ttu-id="04743-141">Суффикс</span><span class="sxs-lookup"><span data-stu-id="04743-141">Suffix</span></span> |       <span data-ttu-id="04743-142">Значение</span><span class="sxs-lookup"><span data-stu-id="04743-142">Meaning</span></span>       |
| ------ | ------------------- |
| <span data-ttu-id="04743-143">d</span><span class="sxs-lookup"><span data-stu-id="04743-143">d</span></span>      | <span data-ttu-id="04743-144">тип данных decimal</span><span class="sxs-lookup"><span data-stu-id="04743-144">decimal data type</span></span>   |
| <span data-ttu-id="04743-145">kb</span><span class="sxs-lookup"><span data-stu-id="04743-145">kb</span></span>     | <span data-ttu-id="04743-146">множитель в килобайтах</span><span class="sxs-lookup"><span data-stu-id="04743-146">kilobyte multiplier</span></span> |
| <span data-ttu-id="04743-147">mb</span><span class="sxs-lookup"><span data-stu-id="04743-147">mb</span></span>     | <span data-ttu-id="04743-148">множитель в мегабайтах</span><span class="sxs-lookup"><span data-stu-id="04743-148">megabyte multiplier</span></span> |
| <span data-ttu-id="04743-149">Гбайт</span><span class="sxs-lookup"><span data-stu-id="04743-149">gb</span></span>     | <span data-ttu-id="04743-150">множитель гигабайта</span><span class="sxs-lookup"><span data-stu-id="04743-150">gigabyte multiplier</span></span> |
| <span data-ttu-id="04743-151">Тбайт</span><span class="sxs-lookup"><span data-stu-id="04743-151">tb</span></span>     | <span data-ttu-id="04743-152">терабайт, множитель</span><span class="sxs-lookup"><span data-stu-id="04743-152">terabyte multiplier</span></span> |
| <span data-ttu-id="04743-153">МС</span><span class="sxs-lookup"><span data-stu-id="04743-153">pb</span></span>     | <span data-ttu-id="04743-154">множитель петабайтного уровня</span><span class="sxs-lookup"><span data-stu-id="04743-154">petabyte multiplier</span></span> |

<span data-ttu-id="04743-155">Существует два вида вещественных литералов: Double и Decimal.</span><span class="sxs-lookup"><span data-stu-id="04743-155">There are two kinds of real literal: double and decimal.</span></span> <span data-ttu-id="04743-156">Они обозначаются отсутствием или присутствием соответственно для суффикса десятичного типа.</span><span class="sxs-lookup"><span data-stu-id="04743-156">These are indicated by the absence or presence, respectively, of decimal-type suffix.</span></span> <span data-ttu-id="04743-157">PowerShell не поддерживает литеральное представление `[float]` значения.</span><span class="sxs-lookup"><span data-stu-id="04743-157">PowerShell does not support a literal representation of a `[float]` value.</span></span> <span data-ttu-id="04743-158">Двойной вещественный литерал имеет тип `[double]` .</span><span class="sxs-lookup"><span data-stu-id="04743-158">A double real literal has type `[double]`.</span></span> <span data-ttu-id="04743-159">Десятичный вещественный литерал имеет тип `[decimal]` .</span><span class="sxs-lookup"><span data-stu-id="04743-159">A decimal real literal has type `[decimal]`.</span></span>
<span data-ttu-id="04743-160">В дробной части вещественного десятичного литерала учитываются нули в конце.</span><span class="sxs-lookup"><span data-stu-id="04743-160">Trailing zeros in the fraction part of a decimal real literal are significant.</span></span>

<span data-ttu-id="04743-161">Если значение числа цифр экспоненты в `[double]` вещественном литерале меньше минимального поддерживаемого значения, значение этого `[double]` литерала равно 0.</span><span class="sxs-lookup"><span data-stu-id="04743-161">If the value of exponent-part's digits in a `[double]` real literal is less than the minimum supported, the value of that `[double]` real literal is 0.</span></span> <span data-ttu-id="04743-162">Если значение числа цифр экспоненты в `[decimal]` вещественном литерале меньше минимального поддерживаемого значения, то литерал имеет неправильный формат.</span><span class="sxs-lookup"><span data-stu-id="04743-162">If the value of exponent-part's digits in a `[decimal]` real literal is less than the minimum supported, that literal is malformed.</span></span> <span data-ttu-id="04743-163">Если значение числа цифр экспоненты в `[double]` или `[decimal]` вещественном литерале больше поддерживаемого максимума, этот литерал имеет неправильный формат.</span><span class="sxs-lookup"><span data-stu-id="04743-163">If the value of exponent-part's digits in a `[double]` or `[decimal]` real literal is greater than the maximum supported, that literal is malformed.</span></span>

> [!NOTE]
> <span data-ttu-id="04743-164">Синтаксис допускает наличие суффикса длинного типа в двойном вещественном литерале.</span><span class="sxs-lookup"><span data-stu-id="04743-164">The syntax permits a double real literal to have a long-type suffix.</span></span>
> <span data-ttu-id="04743-165">PowerShell обрабатывает этот случай как целочисленный литерал, значение которого представлено типом `[long]` .</span><span class="sxs-lookup"><span data-stu-id="04743-165">PowerShell treats this case as an integer literal whose value is represented by type `[long]`.</span></span> <span data-ttu-id="04743-166">Эта функция была сохранена для обеспечения обратной совместимости с более ранними версиями PowerShell.</span><span class="sxs-lookup"><span data-stu-id="04743-166">This feature has been retained for backwards compatibility with earlier versions of PowerShell.</span></span> <span data-ttu-id="04743-167">Однако программистам не рекомендуется использовать целочисленные литералы этой формы, так как они могут легко скрывать фактическое значение литерала.</span><span class="sxs-lookup"><span data-stu-id="04743-167">However, programmers are discouraged from using integer literals of this form as they can easily obscure the literal's actual value.</span></span> <span data-ttu-id="04743-168">Например, `1.2L` имеет значение 1, `1.2345e1L` значение 12 и `1.2345e-5L` имеет значение 0, ни одно из этих значений сразу не очевидно.</span><span class="sxs-lookup"><span data-stu-id="04743-168">For example, `1.2L` has value 1, `1.2345e1L` has value 12, and `1.2345e-5L` has value 0, none of which are immediately obvious.</span></span>

## <a name="numeric-multipliers"></a><span data-ttu-id="04743-169">Числовые множители</span><span class="sxs-lookup"><span data-stu-id="04743-169">Numeric multipliers</span></span>

<span data-ttu-id="04743-170">Для удобства целочисленные и реальные литералы могут содержать числовой множитель, указывающий на один из множества часто используемых степеней 2.</span><span class="sxs-lookup"><span data-stu-id="04743-170">For convenience, integer and real literals can contain a numeric multiplier, which indicates one of a set of commonly used powers of 2.</span></span> <span data-ttu-id="04743-171">Числовой множитель можно записать в любом сочетании прописных или строчных букв.</span><span class="sxs-lookup"><span data-stu-id="04743-171">The numeric multiplier can be written in any combination of upper or lowercase letters.</span></span>

<span data-ttu-id="04743-172">Суффиксы множителя можно использовать в сочетании с `u` `ul` `l` суффиксами типов, и.</span><span class="sxs-lookup"><span data-stu-id="04743-172">The multiplier suffixes can be used in combination with the `u`, `ul`, and `l` type suffixes.</span></span>

### <a name="multiplier-examples"></a><span data-ttu-id="04743-173">Примеры множителя</span><span class="sxs-lookup"><span data-stu-id="04743-173">Multiplier examples</span></span>

```
PS> 1kb
1024

PS> 1.30Dmb
1363148.80

PS> 0x10Gb
17179869184

PS> 1.4e23tb
1.5393162788864E+35

PS> 0x12Lpb
20266198323167232
```

## <a name="numeric-type-accelerators"></a><span data-ttu-id="04743-174">Сочетания числовых типов</span><span class="sxs-lookup"><span data-stu-id="04743-174">Numeric type accelerators</span></span>

<span data-ttu-id="04743-175">PowerShell поддерживает следующие ускорители типов:</span><span class="sxs-lookup"><span data-stu-id="04743-175">PowerShell supports the following type accelerators:</span></span>

| <span data-ttu-id="04743-176">Accelerator</span><span class="sxs-lookup"><span data-stu-id="04743-176">Accelerator</span></span> |         <span data-ttu-id="04743-177">Примечание</span><span class="sxs-lookup"><span data-stu-id="04743-177">Note</span></span>         |           <span data-ttu-id="04743-178">Описание</span><span class="sxs-lookup"><span data-stu-id="04743-178">Description</span></span>            |
| ----------- | -------------------- | -------------------------------- |
| `[byte]`    |                      | <span data-ttu-id="04743-179">Byte (без знака)</span><span class="sxs-lookup"><span data-stu-id="04743-179">Byte (unsigned)</span></span>                  |
| `[sbyte]`   |                      | <span data-ttu-id="04743-180">Byte (со знаком)</span><span class="sxs-lookup"><span data-stu-id="04743-180">Byte (signed)</span></span>                    |
| `[Int16]`   |                      | <span data-ttu-id="04743-181">16-разрядное целое число</span><span class="sxs-lookup"><span data-stu-id="04743-181">16-bit integer</span></span>                   |
| `[UInt16]`  |                      | <span data-ttu-id="04743-182">16-разрядное целое число (без знака)</span><span class="sxs-lookup"><span data-stu-id="04743-182">16-bit integer (unsigned)</span></span>        |
| `[Int32]`   |                      | <span data-ttu-id="04743-183">32-разрядное целое число</span><span class="sxs-lookup"><span data-stu-id="04743-183">32-bit integer</span></span>                   |
| `[int]`     | <span data-ttu-id="04743-184">псевдоним для `[int32]`</span><span class="sxs-lookup"><span data-stu-id="04743-184">alias for `[int32]`</span></span>  | <span data-ttu-id="04743-185">32-разрядное целое число</span><span class="sxs-lookup"><span data-stu-id="04743-185">32-bit integer</span></span>                   |
| `[UInt32]`  |                      | <span data-ttu-id="04743-186">32-разрядное целое число (без знака)</span><span class="sxs-lookup"><span data-stu-id="04743-186">32-bit integer (unsigned)</span></span>        |
| `[Int64]`   |                      | <span data-ttu-id="04743-187">64-разрядное целое число</span><span class="sxs-lookup"><span data-stu-id="04743-187">64-bit integer</span></span>                   |
| `[long]`    | <span data-ttu-id="04743-188">псевдоним для `[int64]`</span><span class="sxs-lookup"><span data-stu-id="04743-188">alias for `[int64]`</span></span>  | <span data-ttu-id="04743-189">64-разрядное целое число</span><span class="sxs-lookup"><span data-stu-id="04743-189">64-bit integer</span></span>                   |
| `[UInt64]`  |                      | <span data-ttu-id="04743-190">64-разрядное целое число (без знака)</span><span class="sxs-lookup"><span data-stu-id="04743-190">64-bit integer (unsigned)</span></span>        |
| `[bigint]`  |                      | <span data-ttu-id="04743-191">См. [структуру BigInteger][bigint]</span><span class="sxs-lookup"><span data-stu-id="04743-191">See [BigInteger Struct][bigint]</span></span>  |
| `[single]`  |                      | <span data-ttu-id="04743-192">Одинарная точность с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="04743-192">Single precision floating point</span></span>  |
| `[float]`   | <span data-ttu-id="04743-193">псевдоним для `[single]`</span><span class="sxs-lookup"><span data-stu-id="04743-193">alias for `[single]`</span></span> | <span data-ttu-id="04743-194">Одинарная точность с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="04743-194">Single precision floating point</span></span>  |
| `[double]`  |                      | <span data-ttu-id="04743-195">Плавающая точка с двойной точностью</span><span class="sxs-lookup"><span data-stu-id="04743-195">Double precision floating point</span></span>  |
| `[decimal]` |                      | <span data-ttu-id="04743-196">128-разрядная с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="04743-196">128-bit floating point</span></span>           |

### <a name="working-with-other-numeric-types"></a><span data-ttu-id="04743-197">Работа с другими числовыми типами</span><span class="sxs-lookup"><span data-stu-id="04743-197">Working with other numeric types</span></span>

<span data-ttu-id="04743-198">Для работы с любыми другими числовыми типами необходимо использовать ускорители типов, которые не позволяют устранить некоторые проблемы.</span><span class="sxs-lookup"><span data-stu-id="04743-198">To work with any other numeric types you must use type accelerators, which is not without some problems.</span></span> <span data-ttu-id="04743-199">Например, большие целочисленные значения всегда анализируются как Double перед их приведением к любому другому типу.</span><span class="sxs-lookup"><span data-stu-id="04743-199">For example, high integer values are always parsed as double before being cast to any other type.</span></span>

```
PS> [bigint]111111111111111111111111111111111111111111111111111111
111111111111111100905595216014112456735339620444667904
```

<span data-ttu-id="04743-200">Значение сначала анализируется как Double, что приводит к потере точности в более высоких диапазонах.</span><span class="sxs-lookup"><span data-stu-id="04743-200">The value is parsed as a double first, losing precision in the higher ranges.</span></span>
<span data-ttu-id="04743-201">Чтобы избежать этой проблемы, введите значения в виде строк, а затем преобразуйте их:</span><span class="sxs-lookup"><span data-stu-id="04743-201">To avoid this problem, enter values as strings and then convert them:</span></span>

```
PS> [bigint]'111111111111111111111111111111111111111111111111111111'
111111111111111111111111111111111111111111111111111111
```

## <a name="examples"></a><span data-ttu-id="04743-202">Примеры</span><span class="sxs-lookup"><span data-stu-id="04743-202">Examples</span></span>

<span data-ttu-id="04743-203">Следующая таблица содержит несколько примеров числовых литералов и перечисляет их тип и значение.</span><span class="sxs-lookup"><span data-stu-id="04743-203">The following table contains several examples of numeric literals and lists their type and value:</span></span>

|  <span data-ttu-id="04743-204">Число</span><span class="sxs-lookup"><span data-stu-id="04743-204">Number</span></span>  |  <span data-ttu-id="04743-205">Тип</span><span class="sxs-lookup"><span data-stu-id="04743-205">Type</span></span>   |    <span data-ttu-id="04743-206">Значение</span><span class="sxs-lookup"><span data-stu-id="04743-206">Value</span></span>     |
| -------: | ------- | -----------: |
|      <span data-ttu-id="04743-207">100</span><span class="sxs-lookup"><span data-stu-id="04743-207">100</span></span> | <span data-ttu-id="04743-208">Int32</span><span class="sxs-lookup"><span data-stu-id="04743-208">Int32</span></span>   |          <span data-ttu-id="04743-209">100</span><span class="sxs-lookup"><span data-stu-id="04743-209">100</span></span> |
|     <span data-ttu-id="04743-210">100D</span><span class="sxs-lookup"><span data-stu-id="04743-210">100D</span></span> | <span data-ttu-id="04743-211">Decimal</span><span class="sxs-lookup"><span data-stu-id="04743-211">Decimal</span></span> |          <span data-ttu-id="04743-212">100</span><span class="sxs-lookup"><span data-stu-id="04743-212">100</span></span> |
|     <span data-ttu-id="04743-213">100l</span><span class="sxs-lookup"><span data-stu-id="04743-213">100l</span></span> | <span data-ttu-id="04743-214">Int64</span><span class="sxs-lookup"><span data-stu-id="04743-214">Int64</span></span>   |          <span data-ttu-id="04743-215">100</span><span class="sxs-lookup"><span data-stu-id="04743-215">100</span></span> |
|      <span data-ttu-id="04743-216">1e2</span><span class="sxs-lookup"><span data-stu-id="04743-216">1e2</span></span> | <span data-ttu-id="04743-217">Double</span><span class="sxs-lookup"><span data-stu-id="04743-217">Double</span></span>  |          <span data-ttu-id="04743-218">100</span><span class="sxs-lookup"><span data-stu-id="04743-218">100</span></span> |
|     <span data-ttu-id="04743-219">1. E2</span><span class="sxs-lookup"><span data-stu-id="04743-219">1.e2</span></span> | <span data-ttu-id="04743-220">Double</span><span class="sxs-lookup"><span data-stu-id="04743-220">Double</span></span>  |          <span data-ttu-id="04743-221">100</span><span class="sxs-lookup"><span data-stu-id="04743-221">100</span></span> |
|    <span data-ttu-id="04743-222">0x1e2</span><span class="sxs-lookup"><span data-stu-id="04743-222">0x1e2</span></span> | <span data-ttu-id="04743-223">Int32</span><span class="sxs-lookup"><span data-stu-id="04743-223">Int32</span></span>   |          <span data-ttu-id="04743-224">482</span><span class="sxs-lookup"><span data-stu-id="04743-224">482</span></span> |
|   <span data-ttu-id="04743-225">0x1e2L</span><span class="sxs-lookup"><span data-stu-id="04743-225">0x1e2L</span></span> | <span data-ttu-id="04743-226">Int64</span><span class="sxs-lookup"><span data-stu-id="04743-226">Int64</span></span>   |          <span data-ttu-id="04743-227">482</span><span class="sxs-lookup"><span data-stu-id="04743-227">482</span></span> |
|   <span data-ttu-id="04743-228">0x1e2D</span><span class="sxs-lookup"><span data-stu-id="04743-228">0x1e2D</span></span> | <span data-ttu-id="04743-229">Int32</span><span class="sxs-lookup"><span data-stu-id="04743-229">Int32</span></span>   |         <span data-ttu-id="04743-230">7725</span><span class="sxs-lookup"><span data-stu-id="04743-230">7725</span></span> |
|     <span data-ttu-id="04743-231">482D</span><span class="sxs-lookup"><span data-stu-id="04743-231">482D</span></span> | <span data-ttu-id="04743-232">Decimal</span><span class="sxs-lookup"><span data-stu-id="04743-232">Decimal</span></span> |          <span data-ttu-id="04743-233">482</span><span class="sxs-lookup"><span data-stu-id="04743-233">482</span></span> |
|    <span data-ttu-id="04743-234">482gb</span><span class="sxs-lookup"><span data-stu-id="04743-234">482gb</span></span> | <span data-ttu-id="04743-235">Int64</span><span class="sxs-lookup"><span data-stu-id="04743-235">Int64</span></span>   | <span data-ttu-id="04743-236">517543559168</span><span class="sxs-lookup"><span data-stu-id="04743-236">517543559168</span></span> |
| <span data-ttu-id="04743-237">0x1e2lgb</span><span class="sxs-lookup"><span data-stu-id="04743-237">0x1e2lgb</span></span> | <span data-ttu-id="04743-238">Int64</span><span class="sxs-lookup"><span data-stu-id="04743-238">Int64</span></span>   | <span data-ttu-id="04743-239">517543559168</span><span class="sxs-lookup"><span data-stu-id="04743-239">517543559168</span></span> |

### <a name="commands-that-look-like-numeric-literals"></a><span data-ttu-id="04743-240">Команды, которые выглядят как числовые литералы</span><span class="sxs-lookup"><span data-stu-id="04743-240">Commands that look like numeric literals</span></span>

<span data-ttu-id="04743-241">Любая команда, похожая на числовой литерал, должна выполняться с помощью оператора Call ( `&` ), в противном случае он интерпретируется как число связанного типа.</span><span class="sxs-lookup"><span data-stu-id="04743-241">Any command that looks like a numeric literal must be executed using the the call operator (`&`), otherwise it is interpreted as a number of the associated type.</span></span>

### <a name="access-properties-and-methods-of-numeric-objects"></a><span data-ttu-id="04743-242">Доступ к свойствам и методам числовых объектов</span><span class="sxs-lookup"><span data-stu-id="04743-242">Access properties and methods of numeric objects</span></span>

<span data-ttu-id="04743-243">Для доступа к элементу числового литерала бывают случаи, когда необходимо заключить литерал в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="04743-243">To access a member of a numeric literal, there are cases when you need to enclose the literal in parentheses.</span></span>

- <span data-ttu-id="04743-244">Литерал не имеет десятичной запятой</span><span class="sxs-lookup"><span data-stu-id="04743-244">The literal does not have a decimal point</span></span>
- <span data-ttu-id="04743-245">Литерал не содержит цифр после десятичной запятой</span><span class="sxs-lookup"><span data-stu-id="04743-245">The literal does not have any digits following the decimal point</span></span>
- <span data-ttu-id="04743-246">У литерала нет суффикса</span><span class="sxs-lookup"><span data-stu-id="04743-246">The literal does not have a suffix</span></span>

<span data-ttu-id="04743-247">Например, следующий пример завершается ошибкой:</span><span class="sxs-lookup"><span data-stu-id="04743-247">For example, the following example fails:</span></span>

```
PS> 2.GetType().Name
At line:1 char:11
+ 2.GetType().Name
+           ~
An expression was expected after '('.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
+ FullyQualifiedErrorId : ExpectedExpression
```

<span data-ttu-id="04743-248">Ниже приведены примеры работы.</span><span class="sxs-lookup"><span data-stu-id="04743-248">The following examples work:</span></span>

```
PS> 2L.GetType().Name
Int64
PS> 1.234.GetType().Name
Double
PS> (2).GetType().Name
Int32
```

<span data-ttu-id="04743-249">Первые два примера работают без заключения литерального значения в круглые скобки, так как средство синтаксического анализа PowerShell может определить, где заканчивается числовой литерал, и запустить метод **GetType** .</span><span class="sxs-lookup"><span data-stu-id="04743-249">The first two examples work without enclosing the literal value in parentheses because the PowerShell parser can determine where the numeric literal ends and the **GetType** method starts.</span></span>

<!-- reference links -->
[bigint]: /dotnet/api/system.numerics.biginteger
