---
description: Целочисленные и вещественные числовые литералы могут иметь суффиксы типа и множителя.
Locale: en-US
ms.date: 04/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_numeric_literals?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: О числовых литералах
ms.openlocfilehash: 8e26e8c67b1acadc75a67cd51bd6adb07fb7daf3
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231157"
---
# <a name="about-numeric-literals"></a><span data-ttu-id="bb180-103">О числовых литералах</span><span class="sxs-lookup"><span data-stu-id="bb180-103">About numeric literals</span></span>

<span data-ttu-id="bb180-104">Существует два вида числовых литералов: integer и Real.</span><span class="sxs-lookup"><span data-stu-id="bb180-104">There are two kinds of numeric literals: integer and real.</span></span> <span data-ttu-id="bb180-105">Оба могут иметь суффиксы типа и множителя.</span><span class="sxs-lookup"><span data-stu-id="bb180-105">Both can have type and multiplier suffixes.</span></span>

## <a name="integer-literals"></a><span data-ttu-id="bb180-106">Целочисленные литералы</span><span class="sxs-lookup"><span data-stu-id="bb180-106">Integer literals</span></span>

<span data-ttu-id="bb180-107">Целочисленные литералы могут быть записаны в десятичной, шестнадцатеричной или двоичной нотации.</span><span class="sxs-lookup"><span data-stu-id="bb180-107">Integer literals can be written in decimal, hexadecimal, or binary notation.</span></span>
<span data-ttu-id="bb180-108">Шестнадцатеричные литералы начинаются с префикса `0x` , а двоичные литералы имеют префикс, `0b` чтобы отличать их от десятичных чисел.</span><span class="sxs-lookup"><span data-stu-id="bb180-108">Hexadecimal literals are prefixed with `0x` and binary literals are prefixed with `0b` to distinguish them from decimal numbers.</span></span>

<span data-ttu-id="bb180-109">Целочисленные литералы могут иметь суффикс типа и суффикс множителя.</span><span class="sxs-lookup"><span data-stu-id="bb180-109">Integer literals can have a type suffix and a multiplier suffix.</span></span>

| <span data-ttu-id="bb180-110">Суффикс</span><span class="sxs-lookup"><span data-stu-id="bb180-110">Suffix</span></span> |            <span data-ttu-id="bb180-111">Значение</span><span class="sxs-lookup"><span data-stu-id="bb180-111">Meaning</span></span>             |          <span data-ttu-id="bb180-112">Примечание</span><span class="sxs-lookup"><span data-stu-id="bb180-112">Note</span></span>           |
| ------ | ------------------------------ | ----------------------- |
| <span data-ttu-id="bb180-113">да</span><span class="sxs-lookup"><span data-stu-id="bb180-113">y</span></span>      | <span data-ttu-id="bb180-114">тип данных Byte со знаком</span><span class="sxs-lookup"><span data-stu-id="bb180-114">signed byte data type</span></span>          | <span data-ttu-id="bb180-115">Добавлено в PowerShell 6,2</span><span class="sxs-lookup"><span data-stu-id="bb180-115">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="bb180-116">Uy</span><span class="sxs-lookup"><span data-stu-id="bb180-116">uy</span></span>     | <span data-ttu-id="bb180-117">тип данных Byte без знака</span><span class="sxs-lookup"><span data-stu-id="bb180-117">unsigned byte data type</span></span>        | <span data-ttu-id="bb180-118">Добавлено в PowerShell 6,2</span><span class="sxs-lookup"><span data-stu-id="bb180-118">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="bb180-119">s</span><span class="sxs-lookup"><span data-stu-id="bb180-119">s</span></span>      | <span data-ttu-id="bb180-120">short - тип данных</span><span class="sxs-lookup"><span data-stu-id="bb180-120">short data type</span></span>                | <span data-ttu-id="bb180-121">Добавлено в PowerShell 6,2</span><span class="sxs-lookup"><span data-stu-id="bb180-121">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="bb180-122">us</span><span class="sxs-lookup"><span data-stu-id="bb180-122">us</span></span>     | <span data-ttu-id="bb180-123">короткий тип данных без знака</span><span class="sxs-lookup"><span data-stu-id="bb180-123">unsigned short data type</span></span>       | <span data-ttu-id="bb180-124">Добавлено в PowerShell 6,2</span><span class="sxs-lookup"><span data-stu-id="bb180-124">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="bb180-125">l</span><span class="sxs-lookup"><span data-stu-id="bb180-125">l</span></span>      | <span data-ttu-id="bb180-126">тип данных Long</span><span class="sxs-lookup"><span data-stu-id="bb180-126">long data type</span></span>                 |                         |
| <span data-ttu-id="bb180-127">u</span><span class="sxs-lookup"><span data-stu-id="bb180-127">u</span></span>      | <span data-ttu-id="bb180-128">целое число без знака или тип данных Long</span><span class="sxs-lookup"><span data-stu-id="bb180-128">unsigned int or long data type</span></span> | <span data-ttu-id="bb180-129">Добавлено в PowerShell 6,2</span><span class="sxs-lookup"><span data-stu-id="bb180-129">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="bb180-130">ul</span><span class="sxs-lookup"><span data-stu-id="bb180-130">ul</span></span>     | <span data-ttu-id="bb180-131">тип данных Long без знака</span><span class="sxs-lookup"><span data-stu-id="bb180-131">unsigned long data type</span></span>        | <span data-ttu-id="bb180-132">Добавлено в PowerShell 6,2</span><span class="sxs-lookup"><span data-stu-id="bb180-132">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="bb180-133">n</span><span class="sxs-lookup"><span data-stu-id="bb180-133">n</span></span>      | <span data-ttu-id="bb180-134">Тип данных BigInteger</span><span class="sxs-lookup"><span data-stu-id="bb180-134">BigInteger data type</span></span>           | <span data-ttu-id="bb180-135">Добавлено в PowerShell 7,0</span><span class="sxs-lookup"><span data-stu-id="bb180-135">Added in PowerShell 7.0</span></span> |
| <span data-ttu-id="bb180-136">kb</span><span class="sxs-lookup"><span data-stu-id="bb180-136">kb</span></span>     | <span data-ttu-id="bb180-137">множитель в килобайтах</span><span class="sxs-lookup"><span data-stu-id="bb180-137">kilobyte multiplier</span></span>            |                         |
| <span data-ttu-id="bb180-138">mb</span><span class="sxs-lookup"><span data-stu-id="bb180-138">mb</span></span>     | <span data-ttu-id="bb180-139">множитель в мегабайтах</span><span class="sxs-lookup"><span data-stu-id="bb180-139">megabyte multiplier</span></span>            |                         |
| <span data-ttu-id="bb180-140">Гбайт</span><span class="sxs-lookup"><span data-stu-id="bb180-140">gb</span></span>     | <span data-ttu-id="bb180-141">множитель гигабайта</span><span class="sxs-lookup"><span data-stu-id="bb180-141">gigabyte multiplier</span></span>            |                         |
| <span data-ttu-id="bb180-142">Тбайт</span><span class="sxs-lookup"><span data-stu-id="bb180-142">tb</span></span>     | <span data-ttu-id="bb180-143">терабайт, множитель</span><span class="sxs-lookup"><span data-stu-id="bb180-143">terabyte multiplier</span></span>            |                         |
| <span data-ttu-id="bb180-144">МС</span><span class="sxs-lookup"><span data-stu-id="bb180-144">pb</span></span>     | <span data-ttu-id="bb180-145">множитель петабайтного уровня</span><span class="sxs-lookup"><span data-stu-id="bb180-145">petabyte multiplier</span></span>            |                         |

<span data-ttu-id="bb180-146">Тип целочисленного литерала определяется его значением, суффиксом типа и суффиксом числового множителя.</span><span class="sxs-lookup"><span data-stu-id="bb180-146">The type of an integer literal is determined by its value, the type suffix, and the numeric multiplier suffix.</span></span>

<span data-ttu-id="bb180-147">Для целочисленного литерала без суффикса типа:</span><span class="sxs-lookup"><span data-stu-id="bb180-147">For an integer literal with no type suffix:</span></span>

- <span data-ttu-id="bb180-148">Если значение может быть представлено типом `[int]` , то есть его типом.</span><span class="sxs-lookup"><span data-stu-id="bb180-148">If the value can be represented by type `[int]`, that is its type.</span></span>
- <span data-ttu-id="bb180-149">В противном случае, если значение может быть представлено типом `[long]` , то есть его тип.</span><span class="sxs-lookup"><span data-stu-id="bb180-149">Otherwise, if the value can be represented by type `[long]`, that is its type.</span></span>
- <span data-ttu-id="bb180-150">В противном случае, если значение может быть представлено типом `[decimal]` , то есть его тип.</span><span class="sxs-lookup"><span data-stu-id="bb180-150">Otherwise, if the value can be represented by type `[decimal]`, that is its type.</span></span>
- <span data-ttu-id="bb180-151">В противном случае он представлен типом `[double]` .</span><span class="sxs-lookup"><span data-stu-id="bb180-151">Otherwise, it is represented by type `[double]`.</span></span>

<span data-ttu-id="bb180-152">Для целочисленного литерала с суффиксом типа:</span><span class="sxs-lookup"><span data-stu-id="bb180-152">For an integer literal with a type suffix:</span></span>

- <span data-ttu-id="bb180-153">Если суффикс типа — `u` , а значение может быть представлено типом, `[uint]` то его тип — `[uint]` .</span><span class="sxs-lookup"><span data-stu-id="bb180-153">If the type suffix is `u` and the value can be represented by type `[uint]` then its type is `[uint]`.</span></span>
- <span data-ttu-id="bb180-154">Если суффикс типа — `u` , а значение может быть представлено типом, `[ulong]` то его тип — `[ulong]` .</span><span class="sxs-lookup"><span data-stu-id="bb180-154">If the type suffix is `u` and the value can be represented by type `[ulong]` then its type is `[ulong]`.</span></span>
- <span data-ttu-id="bb180-155">Если его значение может быть представлено указанным типом, то это тип.</span><span class="sxs-lookup"><span data-stu-id="bb180-155">If its value can be represented by type specified then that is its type.</span></span>
- <span data-ttu-id="bb180-156">В противном случае этот литерал имеет неправильный формат.</span><span class="sxs-lookup"><span data-stu-id="bb180-156">Otherwise, that literal is malformed.</span></span>

## <a name="real-literals"></a><span data-ttu-id="bb180-157">Вещественные литералы</span><span class="sxs-lookup"><span data-stu-id="bb180-157">Real literals</span></span>

<span data-ttu-id="bb180-158">Реальные литералы могут быть записаны только в десятичной нотации.</span><span class="sxs-lookup"><span data-stu-id="bb180-158">Real literals can only be written in decimal notation.</span></span> <span data-ttu-id="bb180-159">Эта нотация может содержать дробные значения, следующие за десятичной запятой и экспоненциальной нотацией, с использованием экспоненциальной части.</span><span class="sxs-lookup"><span data-stu-id="bb180-159">This notation can include fractional values following a decimal point and scientific notation using an exponential part.</span></span>

<span data-ttu-id="bb180-160">Экспоненциальная часть включает символ "e", за которым следует необязательный знак (+/-) и число, представляющее показатель степени.</span><span class="sxs-lookup"><span data-stu-id="bb180-160">The exponential part includes an 'e' followed by an optional sign (+/-) and a number representing the exponent.</span></span> <span data-ttu-id="bb180-161">Например, литеральное значение `1e2` равно числовому значению 100.</span><span class="sxs-lookup"><span data-stu-id="bb180-161">For example, the literal value `1e2` equals the numeric value 100.</span></span>

<span data-ttu-id="bb180-162">Реальные литералы могут иметь суффикс типа и суффикс множителя.</span><span class="sxs-lookup"><span data-stu-id="bb180-162">Real literals can have a type suffix and a multiplier suffix.</span></span>

| <span data-ttu-id="bb180-163">Суффикс</span><span class="sxs-lookup"><span data-stu-id="bb180-163">Suffix</span></span> |       <span data-ttu-id="bb180-164">Значение</span><span class="sxs-lookup"><span data-stu-id="bb180-164">Meaning</span></span>       |
| ------ | ------------------- |
| <span data-ttu-id="bb180-165">d</span><span class="sxs-lookup"><span data-stu-id="bb180-165">d</span></span>      | <span data-ttu-id="bb180-166">тип данных decimal</span><span class="sxs-lookup"><span data-stu-id="bb180-166">decimal data type</span></span>   |
| <span data-ttu-id="bb180-167">kb</span><span class="sxs-lookup"><span data-stu-id="bb180-167">kb</span></span>     | <span data-ttu-id="bb180-168">множитель в килобайтах</span><span class="sxs-lookup"><span data-stu-id="bb180-168">kilobyte multiplier</span></span> |
| <span data-ttu-id="bb180-169">mb</span><span class="sxs-lookup"><span data-stu-id="bb180-169">mb</span></span>     | <span data-ttu-id="bb180-170">множитель в мегабайтах</span><span class="sxs-lookup"><span data-stu-id="bb180-170">megabyte multiplier</span></span> |
| <span data-ttu-id="bb180-171">Гбайт</span><span class="sxs-lookup"><span data-stu-id="bb180-171">gb</span></span>     | <span data-ttu-id="bb180-172">множитель гигабайта</span><span class="sxs-lookup"><span data-stu-id="bb180-172">gigabyte multiplier</span></span> |
| <span data-ttu-id="bb180-173">Тбайт</span><span class="sxs-lookup"><span data-stu-id="bb180-173">tb</span></span>     | <span data-ttu-id="bb180-174">терабайт, множитель</span><span class="sxs-lookup"><span data-stu-id="bb180-174">terabyte multiplier</span></span> |
| <span data-ttu-id="bb180-175">МС</span><span class="sxs-lookup"><span data-stu-id="bb180-175">pb</span></span>     | <span data-ttu-id="bb180-176">множитель петабайтного уровня</span><span class="sxs-lookup"><span data-stu-id="bb180-176">petabyte multiplier</span></span> |

<span data-ttu-id="bb180-177">Существует два вида вещественных литералов: Double и Decimal.</span><span class="sxs-lookup"><span data-stu-id="bb180-177">There are two kinds of real literal: double and decimal.</span></span> <span data-ttu-id="bb180-178">Они обозначаются отсутствием или присутствием соответственно для суффикса десятичного типа.</span><span class="sxs-lookup"><span data-stu-id="bb180-178">These are indicated by the absence or presence, respectively, of decimal-type suffix.</span></span> <span data-ttu-id="bb180-179">PowerShell не поддерживает литеральное представление `[float]` значения.</span><span class="sxs-lookup"><span data-stu-id="bb180-179">PowerShell does not support a literal representation of a `[float]` value.</span></span> <span data-ttu-id="bb180-180">Двойной вещественный литерал имеет тип `[double]` .</span><span class="sxs-lookup"><span data-stu-id="bb180-180">A double real literal has type `[double]`.</span></span> <span data-ttu-id="bb180-181">Десятичный вещественный литерал имеет тип `[decimal]` .</span><span class="sxs-lookup"><span data-stu-id="bb180-181">A decimal real literal has type `[decimal]`.</span></span>
<span data-ttu-id="bb180-182">В дробной части вещественного десятичного литерала учитываются нули в конце.</span><span class="sxs-lookup"><span data-stu-id="bb180-182">Trailing zeros in the fraction part of a decimal real literal are significant.</span></span>

<span data-ttu-id="bb180-183">Если значение числа цифр экспоненты в `[double]` вещественном литерале меньше минимального поддерживаемого значения, значение этого `[double]` литерала равно 0.</span><span class="sxs-lookup"><span data-stu-id="bb180-183">If the value of exponent-part's digits in a `[double]` real literal is less than the minimum supported, the value of that `[double]` real literal is 0.</span></span> <span data-ttu-id="bb180-184">Если значение числа цифр экспоненты в `[decimal]` вещественном литерале меньше минимального поддерживаемого значения, то литерал имеет неправильный формат.</span><span class="sxs-lookup"><span data-stu-id="bb180-184">If the value of exponent-part's digits in a `[decimal]` real literal is less than the minimum supported, that literal is malformed.</span></span> <span data-ttu-id="bb180-185">Если значение числа цифр экспоненты в `[double]` или `[decimal]` вещественном литерале больше поддерживаемого максимума, этот литерал имеет неправильный формат.</span><span class="sxs-lookup"><span data-stu-id="bb180-185">If the value of exponent-part's digits in a `[double]` or `[decimal]` real literal is greater than the maximum supported, that literal is malformed.</span></span>

> [!NOTE]
> <span data-ttu-id="bb180-186">Синтаксис допускает наличие суффикса длинного типа в двойном вещественном литерале.</span><span class="sxs-lookup"><span data-stu-id="bb180-186">The syntax permits a double real literal to have a long-type suffix.</span></span>
> <span data-ttu-id="bb180-187">PowerShell обрабатывает этот случай как целочисленный литерал, значение которого представлено типом `[long]` .</span><span class="sxs-lookup"><span data-stu-id="bb180-187">PowerShell treats this case as an integer literal whose value is represented by type `[long]`.</span></span> <span data-ttu-id="bb180-188">Эта функция была сохранена для обеспечения обратной совместимости с более ранними версиями PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bb180-188">This feature has been retained for backwards compatibility with earlier versions of PowerShell.</span></span> <span data-ttu-id="bb180-189">Однако программистам не рекомендуется использовать целочисленные литералы этой формы, так как они могут легко скрывать фактическое значение литерала.</span><span class="sxs-lookup"><span data-stu-id="bb180-189">However, programmers are discouraged from using integer literals of this form as they can easily obscure the literal's actual value.</span></span> <span data-ttu-id="bb180-190">Например, `1.2L` имеет значение 1, `1.2345e1L` значение 12 и `1.2345e-5L` имеет значение 0, ни одно из этих значений сразу не очевидно.</span><span class="sxs-lookup"><span data-stu-id="bb180-190">For example, `1.2L` has value 1, `1.2345e1L` has value 12, and `1.2345e-5L` has value 0, none of which are immediately obvious.</span></span>

## <a name="numeric-multipliers"></a><span data-ttu-id="bb180-191">Числовые множители</span><span class="sxs-lookup"><span data-stu-id="bb180-191">Numeric multipliers</span></span>

<span data-ttu-id="bb180-192">Для удобства целочисленные и реальные литералы могут содержать числовой множитель, указывающий на один из множества часто используемых степеней 2.</span><span class="sxs-lookup"><span data-stu-id="bb180-192">For convenience, integer and real literals can contain a numeric multiplier, which indicates one of a set of commonly used powers of 2.</span></span> <span data-ttu-id="bb180-193">Числовой множитель можно записать в любом сочетании прописных или строчных букв.</span><span class="sxs-lookup"><span data-stu-id="bb180-193">The numeric multiplier can be written in any combination of upper or lowercase letters.</span></span>

<span data-ttu-id="bb180-194">Суффиксы множителя могут использоваться в сочетании с любыми суффиксами типов, но должны присутствовать после суффикса типа.</span><span class="sxs-lookup"><span data-stu-id="bb180-194">The multiplier suffixes can be used in combination with any type suffixes, but must be present after the type suffix.</span></span> <span data-ttu-id="bb180-195">Например, литерал `100gbL` имеет неправильный формат, но литерал `100Lgb` является допустимым.</span><span class="sxs-lookup"><span data-stu-id="bb180-195">For example, the literal `100gbL` is malformed, but the literal `100Lgb` is valid.</span></span>

<span data-ttu-id="bb180-196">Если множитель создает значение, которое превышает возможные значения для числового типа, определенного суффиксом, литерал имеет неправильный формат.</span><span class="sxs-lookup"><span data-stu-id="bb180-196">If a multiplier creates a value that exceeds the possible values for the numeric type that the suffix specifies, the literal is malformed.</span></span> <span data-ttu-id="bb180-197">Например, литерал `1usgb` имеет неправильный формат, так как значение `1gb` больше, чем разрешено для `[ushort]` типа, указанного `us` суффиксом.</span><span class="sxs-lookup"><span data-stu-id="bb180-197">For example, the literal `1usgb` is malformed, because the value `1gb` is larger than what is permitted for the `[ushort]` type specified by the `us` suffix.</span></span>

### <a name="multiplier-examples"></a><span data-ttu-id="bb180-198">Примеры множителя</span><span class="sxs-lookup"><span data-stu-id="bb180-198">Multiplier examples</span></span>

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

## <a name="numeric-type-accelerators"></a><span data-ttu-id="bb180-199">Сочетания числовых типов</span><span class="sxs-lookup"><span data-stu-id="bb180-199">Numeric type accelerators</span></span>

<span data-ttu-id="bb180-200">PowerShell поддерживает следующие ускорители типов:</span><span class="sxs-lookup"><span data-stu-id="bb180-200">PowerShell supports the following type accelerators:</span></span>

| <span data-ttu-id="bb180-201">Accelerator</span><span class="sxs-lookup"><span data-stu-id="bb180-201">Accelerator</span></span> |         <span data-ttu-id="bb180-202">Примечание</span><span class="sxs-lookup"><span data-stu-id="bb180-202">Note</span></span>         |           <span data-ttu-id="bb180-203">Описание</span><span class="sxs-lookup"><span data-stu-id="bb180-203">Description</span></span>            |
| ----------- | -------------------- | -------------------------------- |
| `[byte]`    |                      | <span data-ttu-id="bb180-204">Byte (без знака)</span><span class="sxs-lookup"><span data-stu-id="bb180-204">Byte (unsigned)</span></span>                  |
| `[sbyte]`   |                      | <span data-ttu-id="bb180-205">Byte (со знаком)</span><span class="sxs-lookup"><span data-stu-id="bb180-205">Byte (signed)</span></span>                    |
| `[Int16]`   |                      | <span data-ttu-id="bb180-206">16-разрядное целое число</span><span class="sxs-lookup"><span data-stu-id="bb180-206">16-bit integer</span></span>                   |
| `[short]`   | <span data-ttu-id="bb180-207">псевдоним для `[int16]`</span><span class="sxs-lookup"><span data-stu-id="bb180-207">alias for `[int16]`</span></span>  | <span data-ttu-id="bb180-208">16-разрядное целое число</span><span class="sxs-lookup"><span data-stu-id="bb180-208">16-bit integer</span></span>                   |
| `[UInt16]`  |                      | <span data-ttu-id="bb180-209">16-разрядное целое число (без знака)</span><span class="sxs-lookup"><span data-stu-id="bb180-209">16-bit integer (unsigned)</span></span>        |
| `[ushort]`  | <span data-ttu-id="bb180-210">псевдоним для `[uint16]`</span><span class="sxs-lookup"><span data-stu-id="bb180-210">alias for `[uint16]`</span></span> | <span data-ttu-id="bb180-211">16-разрядное целое число (без знака)</span><span class="sxs-lookup"><span data-stu-id="bb180-211">16-bit integer (unsigned)</span></span>        |
| `[Int32]`   |                      | <span data-ttu-id="bb180-212">32-разрядное целое число</span><span class="sxs-lookup"><span data-stu-id="bb180-212">32-bit integer</span></span>                   |
| `[int]`     | <span data-ttu-id="bb180-213">псевдоним для `[int32]`</span><span class="sxs-lookup"><span data-stu-id="bb180-213">alias for `[int32]`</span></span>  | <span data-ttu-id="bb180-214">32-разрядное целое число</span><span class="sxs-lookup"><span data-stu-id="bb180-214">32-bit integer</span></span>                   |
| `[UInt32]`  |                      | <span data-ttu-id="bb180-215">32-разрядное целое число (без знака)</span><span class="sxs-lookup"><span data-stu-id="bb180-215">32-bit integer (unsigned)</span></span>        |
| `[uint]`    | <span data-ttu-id="bb180-216">псевдоним для `[uint32]`</span><span class="sxs-lookup"><span data-stu-id="bb180-216">alias for `[uint32]`</span></span> | <span data-ttu-id="bb180-217">32-разрядное целое число (без знака)</span><span class="sxs-lookup"><span data-stu-id="bb180-217">32-bit integer (unsigned)</span></span>        |
| `[Int64]`   |                      | <span data-ttu-id="bb180-218">64-разрядное целое число</span><span class="sxs-lookup"><span data-stu-id="bb180-218">64-bit integer</span></span>                   |
| `[long]`    | <span data-ttu-id="bb180-219">псевдоним для `[int64]`</span><span class="sxs-lookup"><span data-stu-id="bb180-219">alias for `[int64]`</span></span>  | <span data-ttu-id="bb180-220">64-разрядное целое число</span><span class="sxs-lookup"><span data-stu-id="bb180-220">64-bit integer</span></span>                   |
| `[UInt64]`  |                      | <span data-ttu-id="bb180-221">64-разрядное целое число (без знака)</span><span class="sxs-lookup"><span data-stu-id="bb180-221">64-bit integer (unsigned)</span></span>        |
| `[ulong]`   | <span data-ttu-id="bb180-222">псевдоним для `[uint64]`</span><span class="sxs-lookup"><span data-stu-id="bb180-222">alias for `[uint64]`</span></span> | <span data-ttu-id="bb180-223">64-разрядное целое число (без знака)</span><span class="sxs-lookup"><span data-stu-id="bb180-223">64-bit integer (unsigned)</span></span>        |
| `[bigint]`  |                      | <span data-ttu-id="bb180-224">См. [структуру BigInteger][bigint]</span><span class="sxs-lookup"><span data-stu-id="bb180-224">See [BigInteger Struct][bigint]</span></span>  |
| `[single]`  |                      | <span data-ttu-id="bb180-225">Одинарная точность с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="bb180-225">Single precision floating point</span></span>  |
| `[float]`   | <span data-ttu-id="bb180-226">псевдоним для `[single]`</span><span class="sxs-lookup"><span data-stu-id="bb180-226">alias for `[single]`</span></span> | <span data-ttu-id="bb180-227">Одинарная точность с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="bb180-227">Single precision floating point</span></span>  |
| `[double]`  |                      | <span data-ttu-id="bb180-228">Плавающая точка с двойной точностью</span><span class="sxs-lookup"><span data-stu-id="bb180-228">Double precision floating point</span></span>  |
| `[decimal]` |                      | <span data-ttu-id="bb180-229">128-разрядная с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="bb180-229">128-bit floating point</span></span>           |

> [!NOTE]
> <span data-ttu-id="bb180-230">В PowerShell 6,2 были добавлены следующие ускорители типов: `[short]` , `[ushort]` , `[uint]` , `[ulong]` .</span><span class="sxs-lookup"><span data-stu-id="bb180-230">The following type accelerators were added in PowerShell 6.2: `[short]`, `[ushort]`, `[uint]`, `[ulong]`.</span></span>

## <a name="examples"></a><span data-ttu-id="bb180-231">Примеры</span><span class="sxs-lookup"><span data-stu-id="bb180-231">Examples</span></span>

<span data-ttu-id="bb180-232">Следующая таблица содержит несколько примеров числовых литералов и перечисляет их тип и значение.</span><span class="sxs-lookup"><span data-stu-id="bb180-232">The following table contains several examples of numeric literals and lists their type and value:</span></span>

|   <span data-ttu-id="bb180-233">Число</span><span class="sxs-lookup"><span data-stu-id="bb180-233">Number</span></span>     |  <span data-ttu-id="bb180-234">Тип</span><span class="sxs-lookup"><span data-stu-id="bb180-234">Type</span></span>      |    <span data-ttu-id="bb180-235">Значение</span><span class="sxs-lookup"><span data-stu-id="bb180-235">Value</span></span>     |
| -----------: | ---------- | -----------: |
|         <span data-ttu-id="bb180-236">100</span><span class="sxs-lookup"><span data-stu-id="bb180-236">100</span></span>  | <span data-ttu-id="bb180-237">Int32</span><span class="sxs-lookup"><span data-stu-id="bb180-237">Int32</span></span>      |          <span data-ttu-id="bb180-238">100</span><span class="sxs-lookup"><span data-stu-id="bb180-238">100</span></span> |
|        <span data-ttu-id="bb180-239">100u</span><span class="sxs-lookup"><span data-stu-id="bb180-239">100u</span></span>  | <span data-ttu-id="bb180-240">UInt32</span><span class="sxs-lookup"><span data-stu-id="bb180-240">UInt32</span></span>     |          <span data-ttu-id="bb180-241">100</span><span class="sxs-lookup"><span data-stu-id="bb180-241">100</span></span> |
|        <span data-ttu-id="bb180-242">100D</span><span class="sxs-lookup"><span data-stu-id="bb180-242">100D</span></span>  | <span data-ttu-id="bb180-243">Decimal</span><span class="sxs-lookup"><span data-stu-id="bb180-243">Decimal</span></span>    |          <span data-ttu-id="bb180-244">100</span><span class="sxs-lookup"><span data-stu-id="bb180-244">100</span></span> |
|        <span data-ttu-id="bb180-245">100l</span><span class="sxs-lookup"><span data-stu-id="bb180-245">100l</span></span>  | <span data-ttu-id="bb180-246">Int64</span><span class="sxs-lookup"><span data-stu-id="bb180-246">Int64</span></span>      |          <span data-ttu-id="bb180-247">100</span><span class="sxs-lookup"><span data-stu-id="bb180-247">100</span></span> |
|       <span data-ttu-id="bb180-248">100uL</span><span class="sxs-lookup"><span data-stu-id="bb180-248">100uL</span></span>  | <span data-ttu-id="bb180-249">UInt64</span><span class="sxs-lookup"><span data-stu-id="bb180-249">UInt64</span></span>     |          <span data-ttu-id="bb180-250">100</span><span class="sxs-lookup"><span data-stu-id="bb180-250">100</span></span> |
|       <span data-ttu-id="bb180-251">100us</span><span class="sxs-lookup"><span data-stu-id="bb180-251">100us</span></span>  | <span data-ttu-id="bb180-252">UInt16</span><span class="sxs-lookup"><span data-stu-id="bb180-252">UInt16</span></span>     |          <span data-ttu-id="bb180-253">100</span><span class="sxs-lookup"><span data-stu-id="bb180-253">100</span></span> |
|       <span data-ttu-id="bb180-254">100uy</span><span class="sxs-lookup"><span data-stu-id="bb180-254">100uy</span></span>  | <span data-ttu-id="bb180-255">Byte</span><span class="sxs-lookup"><span data-stu-id="bb180-255">Byte</span></span>       |          <span data-ttu-id="bb180-256">100</span><span class="sxs-lookup"><span data-stu-id="bb180-256">100</span></span> |
|        <span data-ttu-id="bb180-257">100y</span><span class="sxs-lookup"><span data-stu-id="bb180-257">100y</span></span>  | <span data-ttu-id="bb180-258">SByte</span><span class="sxs-lookup"><span data-stu-id="bb180-258">SByte</span></span>      |          <span data-ttu-id="bb180-259">100</span><span class="sxs-lookup"><span data-stu-id="bb180-259">100</span></span> |
|         <span data-ttu-id="bb180-260">1e2</span><span class="sxs-lookup"><span data-stu-id="bb180-260">1e2</span></span>  | <span data-ttu-id="bb180-261">Double</span><span class="sxs-lookup"><span data-stu-id="bb180-261">Double</span></span>     |          <span data-ttu-id="bb180-262">100</span><span class="sxs-lookup"><span data-stu-id="bb180-262">100</span></span> |
|        <span data-ttu-id="bb180-263">1. E2</span><span class="sxs-lookup"><span data-stu-id="bb180-263">1.e2</span></span>  | <span data-ttu-id="bb180-264">Double</span><span class="sxs-lookup"><span data-stu-id="bb180-264">Double</span></span>     |          <span data-ttu-id="bb180-265">100</span><span class="sxs-lookup"><span data-stu-id="bb180-265">100</span></span> |
|       <span data-ttu-id="bb180-266">0x1e2</span><span class="sxs-lookup"><span data-stu-id="bb180-266">0x1e2</span></span>  | <span data-ttu-id="bb180-267">Int32</span><span class="sxs-lookup"><span data-stu-id="bb180-267">Int32</span></span>      |          <span data-ttu-id="bb180-268">482</span><span class="sxs-lookup"><span data-stu-id="bb180-268">482</span></span> |
|      <span data-ttu-id="bb180-269">0x1e2L</span><span class="sxs-lookup"><span data-stu-id="bb180-269">0x1e2L</span></span>  | <span data-ttu-id="bb180-270">Int64</span><span class="sxs-lookup"><span data-stu-id="bb180-270">Int64</span></span>      |          <span data-ttu-id="bb180-271">482</span><span class="sxs-lookup"><span data-stu-id="bb180-271">482</span></span> |
|      <span data-ttu-id="bb180-272">0x1e2D</span><span class="sxs-lookup"><span data-stu-id="bb180-272">0x1e2D</span></span>  | <span data-ttu-id="bb180-273">Int32</span><span class="sxs-lookup"><span data-stu-id="bb180-273">Int32</span></span>      |         <span data-ttu-id="bb180-274">7725</span><span class="sxs-lookup"><span data-stu-id="bb180-274">7725</span></span> |
|        <span data-ttu-id="bb180-275">482D</span><span class="sxs-lookup"><span data-stu-id="bb180-275">482D</span></span>  | <span data-ttu-id="bb180-276">Decimal</span><span class="sxs-lookup"><span data-stu-id="bb180-276">Decimal</span></span>    |          <span data-ttu-id="bb180-277">482</span><span class="sxs-lookup"><span data-stu-id="bb180-277">482</span></span> |
|       <span data-ttu-id="bb180-278">482gb</span><span class="sxs-lookup"><span data-stu-id="bb180-278">482gb</span></span>  | <span data-ttu-id="bb180-279">Int64</span><span class="sxs-lookup"><span data-stu-id="bb180-279">Int64</span></span>      | <span data-ttu-id="bb180-280">517543559168</span><span class="sxs-lookup"><span data-stu-id="bb180-280">517543559168</span></span> |
|       <span data-ttu-id="bb180-281">482ngb</span><span class="sxs-lookup"><span data-stu-id="bb180-281">482ngb</span></span> | <span data-ttu-id="bb180-282">BigInteger</span><span class="sxs-lookup"><span data-stu-id="bb180-282">BigInteger</span></span> | <span data-ttu-id="bb180-283">517543559168</span><span class="sxs-lookup"><span data-stu-id="bb180-283">517543559168</span></span> |
|    <span data-ttu-id="bb180-284">0x1e2lgb</span><span class="sxs-lookup"><span data-stu-id="bb180-284">0x1e2lgb</span></span>  | <span data-ttu-id="bb180-285">Int64</span><span class="sxs-lookup"><span data-stu-id="bb180-285">Int64</span></span>      | <span data-ttu-id="bb180-286">517543559168</span><span class="sxs-lookup"><span data-stu-id="bb180-286">517543559168</span></span> |
|   <span data-ttu-id="bb180-287">0b1011011</span><span class="sxs-lookup"><span data-stu-id="bb180-287">0b1011011</span></span>  | <span data-ttu-id="bb180-288">Int32</span><span class="sxs-lookup"><span data-stu-id="bb180-288">Int32</span></span>      |           <span data-ttu-id="bb180-289">91</span><span class="sxs-lookup"><span data-stu-id="bb180-289">91</span></span> |
|  <span data-ttu-id="bb180-290">0xFFFFFFFF</span><span class="sxs-lookup"><span data-stu-id="bb180-290">0xFFFFFFFF</span></span>  | <span data-ttu-id="bb180-291">Int32</span><span class="sxs-lookup"><span data-stu-id="bb180-291">Int32</span></span>      |           <span data-ttu-id="bb180-292">-1</span><span class="sxs-lookup"><span data-stu-id="bb180-292">-1</span></span> |
| <span data-ttu-id="bb180-293">-0xFFFFFFFF</span><span class="sxs-lookup"><span data-stu-id="bb180-293">-0xFFFFFFFF</span></span>  | <span data-ttu-id="bb180-294">Int32</span><span class="sxs-lookup"><span data-stu-id="bb180-294">Int32</span></span>      |            <span data-ttu-id="bb180-295">1</span><span class="sxs-lookup"><span data-stu-id="bb180-295">1</span></span> |
| <span data-ttu-id="bb180-296">0xFFFFFFFFu</span><span class="sxs-lookup"><span data-stu-id="bb180-296">0xFFFFFFFFu</span></span>  | <span data-ttu-id="bb180-297">UInt32</span><span class="sxs-lookup"><span data-stu-id="bb180-297">UInt32</span></span>     |   <span data-ttu-id="bb180-298">4294967295</span><span class="sxs-lookup"><span data-stu-id="bb180-298">4294967295</span></span> |

### <a name="working-with-binary-or-hexadecimal-numbers"></a><span data-ttu-id="bb180-299">Работа с двоичными или шестнадцатеричными числами</span><span class="sxs-lookup"><span data-stu-id="bb180-299">Working with binary or hexadecimal numbers</span></span>

<span data-ttu-id="bb180-300">Чрезмерно большие двоичные или шестнадцатеричные литералы могут возвращать `[bigint]` , а не завершать синтаксический анализ, если только `n` указан суффикс.</span><span class="sxs-lookup"><span data-stu-id="bb180-300">Overly large binary or hexadecimal literals can return as `[bigint]` rather than failing the parse, if and only if the `n` suffix is specified.</span></span> <span data-ttu-id="bb180-301">Биты подписи по-прежнему применяются к даже `[decimal]` диапазонам. Однако:</span><span class="sxs-lookup"><span data-stu-id="bb180-301">Sign bits are still respected above even `[decimal]` ranges, however:</span></span>

- <span data-ttu-id="bb180-302">Если двоичная строка представляет собой несколько из 8 битов, самый высокий бит рассматривается как бит знака.</span><span class="sxs-lookup"><span data-stu-id="bb180-302">If a binary string is some multiple of 8 bits long, the highest bit is treated as the sign bit.</span></span>
- <span data-ttu-id="bb180-303">Если шестнадцатеричная строка с длиной, кратной 8, имеет первую цифру, равную 8 или выше, то цифра считается отрицательной.</span><span class="sxs-lookup"><span data-stu-id="bb180-303">If a hex string, which has a length that is a multiple of 8, has the first digit with 8 or higher, the numeral is treated as negative.</span></span>

<span data-ttu-id="bb180-304">Указание неподписанного суффикса для двоичных и шестнадцатеричных литералов игнорирует биты знака.</span><span class="sxs-lookup"><span data-stu-id="bb180-304">Specifying an unsigned suffix on binary and hex literals ignores sign bits.</span></span> <span data-ttu-id="bb180-305">Например, `0xFFFFFFFF` возвращает `-1` , но `0xFFFFFFFFu` возвращает значение `[uint]::MaxValue` 4294967295.</span><span class="sxs-lookup"><span data-stu-id="bb180-305">For example, `0xFFFFFFFF` returns `-1`, but `0xFFFFFFFFu` returns the `[uint]::MaxValue` of 4294967295.</span></span>

<span data-ttu-id="bb180-306">Предваряющий литерал с помощью `0` будет обходить это и обрабатываться как неподписанные.</span><span class="sxs-lookup"><span data-stu-id="bb180-306">Prefixing the literal with a `0` will bypass this and be treated as unsigned.</span></span>
<span data-ttu-id="bb180-307">Например: `0b011111111`.</span><span class="sxs-lookup"><span data-stu-id="bb180-307">For example: `0b011111111`.</span></span> <span data-ttu-id="bb180-308">Это может быть необходимо при работе с литералами в `[bigint]` диапазоне, так как `u` `n` суффиксы и не могут быть объединены.</span><span class="sxs-lookup"><span data-stu-id="bb180-308">This can be necessary when working with literals in the `[bigint]` range, as the `u` and `n` suffixes cannot be combined.</span></span>

<span data-ttu-id="bb180-309">Можно также инвертировать двоичные и шестнадцатеричные литералы с помощью `-` префикса.</span><span class="sxs-lookup"><span data-stu-id="bb180-309">You can also negate binary and hex literals using the `-` prefix.</span></span> <span data-ttu-id="bb180-310">Это может привести к положительному числу, так как разрешены биты знаков.</span><span class="sxs-lookup"><span data-stu-id="bb180-310">This can result in a positive number since sign bits are permitted.</span></span>

<span data-ttu-id="bb180-311">Биты знаков принимаются для цифр с суффиксом BigInteger:</span><span class="sxs-lookup"><span data-stu-id="bb180-311">Sign bits are accepted for BigInteger-suffixed numerals:</span></span>

- <span data-ttu-id="bb180-312">BigInteger-Hex рассматривает старший бит любого литерала с длиной, кратной 8 символам, как бит знака.</span><span class="sxs-lookup"><span data-stu-id="bb180-312">BigInteger-suffixed hex treats the high bit of any literal with a length multiple of 8 characters as the sign bit.</span></span> <span data-ttu-id="bb180-313">Длина не включает `0x` префикс или суффиксы.</span><span class="sxs-lookup"><span data-stu-id="bb180-313">The length does not include the `0x` prefix or any suffixes.</span></span>
- <span data-ttu-id="bb180-314">Двоичный файл с суффиксом BigInteger принимает биты знаков 96 и 128 символов и каждые 8 символов после.</span><span class="sxs-lookup"><span data-stu-id="bb180-314">BigInteger-suffixed binary accepts sign bits at 96 and 128 characters, and at every 8 characters after.</span></span>

### <a name="commands-that-look-like-numeric-literals"></a><span data-ttu-id="bb180-315">Команды, которые выглядят как числовые литералы</span><span class="sxs-lookup"><span data-stu-id="bb180-315">Commands that look like numeric literals</span></span>

<span data-ttu-id="bb180-316">Любая команда, похожая на допустимый числовой литерал, должна выполняться с помощью оператора Call ( `&` ), в противном случае он интерпретируется как число.</span><span class="sxs-lookup"><span data-stu-id="bb180-316">Any command that looks like a valid numeric literal must be executed using the call operator (`&`), otherwise it is interpreted as a number.</span></span> <span data-ttu-id="bb180-317">Неверно сформированные литералы с допустимым синтаксисом, например `1usgb` , приведут к следующей ошибке:</span><span class="sxs-lookup"><span data-stu-id="bb180-317">Malformed literals with valid syntax like `1usgb` will result in the following error:</span></span>

```
PS> 1usgb
At line:1 char:6
+ 1usgb
+      ~
The numeric constant 1usgb is not valid.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
+ FullyQualifiedErrorId : BadNumericConstant
```

<span data-ttu-id="bb180-318">Однако неправильно сформированные литералы с недопустимым синтаксисом `1gbus` будут интерпретироваться как стандартная строка, и ее можно интерпретировать как допустимое имя команды в контекстах, где могут быть вызваны команды.</span><span class="sxs-lookup"><span data-stu-id="bb180-318">However, malformed literals with invalid syntax like `1gbus` will be interpreted as a standard bare string, and can be interpreted as a valid command name in contexts where commands may be called.</span></span>

### <a name="access-properties-and-methods-of-numeric-objects"></a><span data-ttu-id="bb180-319">Доступ к свойствам и методам числовых объектов</span><span class="sxs-lookup"><span data-stu-id="bb180-319">Access properties and methods of numeric objects</span></span>

<span data-ttu-id="bb180-320">Для доступа к элементу числового литерала бывают случаи, когда необходимо заключить литерал в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="bb180-320">To access a member of a numeric literal, there are cases when you need to enclose the literal in parentheses.</span></span>

- <span data-ttu-id="bb180-321">Литерал не имеет десятичной запятой</span><span class="sxs-lookup"><span data-stu-id="bb180-321">The literal does not have a decimal point</span></span>
- <span data-ttu-id="bb180-322">Литерал не содержит цифр после десятичной запятой</span><span class="sxs-lookup"><span data-stu-id="bb180-322">The literal does not have any digits following the decimal point</span></span>
- <span data-ttu-id="bb180-323">У литерала нет суффикса</span><span class="sxs-lookup"><span data-stu-id="bb180-323">The literal does not have a suffix</span></span>

<span data-ttu-id="bb180-324">Например, следующий пример завершается ошибкой:</span><span class="sxs-lookup"><span data-stu-id="bb180-324">For example, the following example fails:</span></span>

```
PS> 2.GetType().Name
At line:1 char:11
+ 2.GetType().Name
+           ~
An expression was expected after '('.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
+ FullyQualifiedErrorId : ExpectedExpression
```

<span data-ttu-id="bb180-325">Ниже приведены примеры работы.</span><span class="sxs-lookup"><span data-stu-id="bb180-325">The following examples work:</span></span>

```
PS> 2uL.GetType().Name
UInt64
PS> 1.234.GetType().Name
Double
PS> (2).GetType().Name
Int32
```

<span data-ttu-id="bb180-326">Первые два примера работают без заключения литерального значения в круглые скобки, так как средство синтаксического анализа PowerShell может определить, где заканчивается числовой литерал, и запустить метод **GetType** .</span><span class="sxs-lookup"><span data-stu-id="bb180-326">The first two examples work without enclosing the literal value in parentheses because the PowerShell parser can determine where the numeric literal ends and the **GetType** method starts.</span></span>

## <a name="how-powershell-parses-numeric-literals"></a><span data-ttu-id="bb180-327">Как PowerShell анализирует числовые литералы</span><span class="sxs-lookup"><span data-stu-id="bb180-327">How PowerShell parses numeric literals</span></span>

<span data-ttu-id="bb180-328">PowerShell версии 7.0 изменил способ синтаксического анализа числовых литералов, чтобы включить новые функции.</span><span class="sxs-lookup"><span data-stu-id="bb180-328">PowerShell v7.0 changed the way numeric literals are parsed to enable the new features.</span></span>

### <a name="parsing-real-numeric-literals"></a><span data-ttu-id="bb180-329">Синтаксический анализ вещественных числовых литералов</span><span class="sxs-lookup"><span data-stu-id="bb180-329">Parsing real numeric literals</span></span>

<span data-ttu-id="bb180-330">Если литерал содержит десятичную запятую или электронную нотацию, то литеральная строка анализирует вещественное число.</span><span class="sxs-lookup"><span data-stu-id="bb180-330">If the literal contains a decimal point or the e-notation, the literal string is parsed a real number.</span></span>

- <span data-ttu-id="bb180-331">Если десятичный суффикс представлен, то непосредственно в `[decimal]` .</span><span class="sxs-lookup"><span data-stu-id="bb180-331">If the decimal-suffix is present then directly into `[decimal]`.</span></span>
- <span data-ttu-id="bb180-332">В противном случае следует выполнить синтаксический анализ `[Double]` и применить множитель к значению.</span><span class="sxs-lookup"><span data-stu-id="bb180-332">Else, parse as `[Double]` and apply multiplier to the value.</span></span> <span data-ttu-id="bb180-333">Затем проверьте суффиксы типов и попытайтесь привести их в соответствующий тип.</span><span class="sxs-lookup"><span data-stu-id="bb180-333">Then check the type suffixes and attempt to cast into appropriate type.</span></span>
- <span data-ttu-id="bb180-334">Если строка не имеет суффикса типа, выполните синтаксический анализ как `[Double]` .</span><span class="sxs-lookup"><span data-stu-id="bb180-334">If the string has no type suffix, then parse as `[Double]`.</span></span>

### <a name="paring-integer-numeric-literals"></a><span data-ttu-id="bb180-335">Геосвязь целые числовые литералы</span><span class="sxs-lookup"><span data-stu-id="bb180-335">Paring integer numeric literals</span></span>

<span data-ttu-id="bb180-336">Литералы целочисленного типа анализируются с помощью следующих шагов:</span><span class="sxs-lookup"><span data-stu-id="bb180-336">Integer type literals are parsed using the following steps:</span></span>

1. <span data-ttu-id="bb180-337">Определение формата системы счисления</span><span class="sxs-lookup"><span data-stu-id="bb180-337">Determine the radix format</span></span>
   - <span data-ttu-id="bb180-338">Для двоичных форматов следует выполнить синтаксический анализ в `[BigInteger]` .</span><span class="sxs-lookup"><span data-stu-id="bb180-338">For binary formats, parse into `[BigInteger]`.</span></span>
   - <span data-ttu-id="bb180-339">Для формата в шестнадцатеричном формате следует выполнить синтаксический анализ `[BigInteger]` с помощью специального касиес, чтобы хранить исходные поведения, когда значение находится в `[int]` `[long]` диапазоне или.</span><span class="sxs-lookup"><span data-stu-id="bb180-339">For hexidecimal formats, parse into `[BigInteger]` using special casies to retain original behaviours when the value is in the `[int]` or `[long]` range.</span></span>
   - <span data-ttu-id="bb180-340">Если не задан ни двоичный, ни шестнадцатеричный, то синтаксический анализ обычно является `[BigInteger]` .</span><span class="sxs-lookup"><span data-stu-id="bb180-340">If neither binary nor hex, parse normally as a `[BigInteger]`.</span></span>
2. <span data-ttu-id="bb180-341">Примените значение множителя перед попыткой выполнить приведения, чтобы обеспечить правильную проверку границ типов без переполняется.</span><span class="sxs-lookup"><span data-stu-id="bb180-341">Apply the multiplier value before attempting any casts to ensure type bounds can be appropriately checked without overflows.</span></span>
3. <span data-ttu-id="bb180-342">Проверьте суффиксы типов.</span><span class="sxs-lookup"><span data-stu-id="bb180-342">Check type suffixes.</span></span>
   - <span data-ttu-id="bb180-343">Проверьте границы типа и попытайтесь выполнить синтаксический анализ этого типа.</span><span class="sxs-lookup"><span data-stu-id="bb180-343">Check type bounds and attempt to parse into that type.</span></span>
   - <span data-ttu-id="bb180-344">Если суффикс не используется, значение является ограничивающим и проверяется в следующем порядке, что приводит к первому успешному тестированию, определяющему тип числа.</span><span class="sxs-lookup"><span data-stu-id="bb180-344">If no suffix is used, then the value is bounds-checked in the following order, resulting in the first successful test determining the type of the number.</span></span>
     - `[int]`
     - `[long]`
     - <span data-ttu-id="bb180-345">`[decimal]` (только литералы Base-10)</span><span class="sxs-lookup"><span data-stu-id="bb180-345">`[decimal]` (base-10 literals only)</span></span>
     - <span data-ttu-id="bb180-346">`[double]` (только литералы Base-10)</span><span class="sxs-lookup"><span data-stu-id="bb180-346">`[double]` (base-10 literals only)</span></span>
   - <span data-ttu-id="bb180-347">Если значение выходит за пределы `[long]` диапазона для шестнадцатеричных и двоичных чисел, анализ завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="bb180-347">If the value is outside the `[long]` range for hex and binary numbers, the parse fails.</span></span>
   - <span data-ttu-id="bb180-348">Если значение находится за пределами `[double]` диапазона для базового 10 числа, анализ завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="bb180-348">If the value is outside the `[double]` range for base 10 number, the parse fails.</span></span>
   - <span data-ttu-id="bb180-349">Более высокие значения должны быть написаны явным образом с помощью `n` суффикса, чтобы проанализировать литерал как `BigInteger` .</span><span class="sxs-lookup"><span data-stu-id="bb180-349">Higher values must be explicitly written using the `n` suffix to parse the literal as a `BigInteger`.</span></span>

### <a name="parsing-large-value-literals"></a><span data-ttu-id="bb180-350">Синтаксический анализ литералов с большими значениями</span><span class="sxs-lookup"><span data-stu-id="bb180-350">Parsing large value literals</span></span>

<span data-ttu-id="bb180-351">Ранее более высокие целочисленные значения были проанализированы как Double перед их приведением к любому другому типу.</span><span class="sxs-lookup"><span data-stu-id="bb180-351">Previously, higher integer values were parsed as double before being cast to any other type.</span></span> <span data-ttu-id="bb180-352">Это приводит к утрате точности в более высоких диапазонах.</span><span class="sxs-lookup"><span data-stu-id="bb180-352">This results in a loss of precision in the higher ranges.</span></span> <span data-ttu-id="bb180-353">Пример:</span><span class="sxs-lookup"><span data-stu-id="bb180-353">For example:</span></span>

```
PS> [bigint]111111111111111111111111111111111111111111111111111111
111111111111111100905595216014112456735339620444667904
```

<span data-ttu-id="bb180-354">Чтобы избежать этой проблемы, необходимо было записывать значения как строки и затем преобразовывать их:</span><span class="sxs-lookup"><span data-stu-id="bb180-354">To avoid this problem you had to write values as strings and then convert them:</span></span>

```
PS> [bigint]'111111111111111111111111111111111111111111111111111111'
111111111111111111111111111111111111111111111111111111
```

<span data-ttu-id="bb180-355">В PowerShell 7,0 необходимо использовать `N` суффикс.</span><span class="sxs-lookup"><span data-stu-id="bb180-355">In PowerShell 7.0 you must use the `N` suffix.</span></span>

```
PS> 111111111111111111111111111111111111111111111111111111n
111111111111111111111111111111111111111111111111111111
```

<span data-ttu-id="bb180-356">Кроме того, значения между `[ulong]::MaxValue` и `[decimal]::MaxValue` должны быть отмечены с помощью десятичного суффикса `D` для обеспечения точности.</span><span class="sxs-lookup"><span data-stu-id="bb180-356">Also values between `[ulong]::MaxValue` and `[decimal]::MaxValue` should be denoted using the decimal-suffix `D` to maintain accuracy.</span></span> <span data-ttu-id="bb180-357">Без суффикса эти значения анализируются `[Double]` с использованием режима реального анализа.</span><span class="sxs-lookup"><span data-stu-id="bb180-357">Without the suffix, these values are parsed as `[Double]` using the real-parsing mode.</span></span>

<!-- reference links -->
[bigint]: /dotnet/api/system.numerics.biginteger?view=netcore-2.2
