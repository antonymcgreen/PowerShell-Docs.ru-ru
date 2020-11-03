---
description: Целочисленные и вещественные числовые литералы могут иметь суффиксы типа и множителя.
Locale: en-US
ms.date: 04/09/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_numeric_literals?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: О числовых литералах
ms.openlocfilehash: 62f00ae9f3643724808146134fd03b6f01c29bce
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "93233009"
---
# <a name="about-numeric-literals"></a><span data-ttu-id="d480f-103">О числовых литералах</span><span class="sxs-lookup"><span data-stu-id="d480f-103">About numeric literals</span></span>

<span data-ttu-id="d480f-104">Существует два вида числовых литералов: integer и Real.</span><span class="sxs-lookup"><span data-stu-id="d480f-104">There are two kinds of numeric literals: integer and real.</span></span> <span data-ttu-id="d480f-105">Оба могут иметь суффиксы типа и множителя.</span><span class="sxs-lookup"><span data-stu-id="d480f-105">Both can have type and multiplier suffixes.</span></span>

## <a name="integer-literals"></a><span data-ttu-id="d480f-106">Целочисленные литералы</span><span class="sxs-lookup"><span data-stu-id="d480f-106">Integer literals</span></span>

<span data-ttu-id="d480f-107">Целочисленные литералы могут быть записаны в десятичной или шестнадцатеричной нотации.</span><span class="sxs-lookup"><span data-stu-id="d480f-107">Integer literals can be written in decimal or hexadecimal notation.</span></span> <span data-ttu-id="d480f-108">Шестнадцатеричные литералы начинаются с префикса, `0x` чтобы отличать их от десятичных чисел.</span><span class="sxs-lookup"><span data-stu-id="d480f-108">Hexadecimal literals are prefixed with `0x` to distinguish them from decimal numbers.</span></span>

<span data-ttu-id="d480f-109">Целочисленные литералы могут иметь суффикс типа и суффикс множителя.</span><span class="sxs-lookup"><span data-stu-id="d480f-109">Integer literals can have a type suffix and a multiplier suffix.</span></span>

| <span data-ttu-id="d480f-110">Суффикс</span><span class="sxs-lookup"><span data-stu-id="d480f-110">Suffix</span></span> |            <span data-ttu-id="d480f-111">Значение</span><span class="sxs-lookup"><span data-stu-id="d480f-111">Meaning</span></span>             |          <span data-ttu-id="d480f-112">Примечание</span><span class="sxs-lookup"><span data-stu-id="d480f-112">Note</span></span>           |
| ------ | ------------------------------ | ----------------------- |
| <span data-ttu-id="d480f-113">да</span><span class="sxs-lookup"><span data-stu-id="d480f-113">y</span></span>      | <span data-ttu-id="d480f-114">тип данных Byte со знаком</span><span class="sxs-lookup"><span data-stu-id="d480f-114">signed byte data type</span></span>          | <span data-ttu-id="d480f-115">Добавлено в PowerShell 6,2</span><span class="sxs-lookup"><span data-stu-id="d480f-115">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="d480f-116">Uy</span><span class="sxs-lookup"><span data-stu-id="d480f-116">uy</span></span>     | <span data-ttu-id="d480f-117">тип данных Byte без знака</span><span class="sxs-lookup"><span data-stu-id="d480f-117">unsigned byte data type</span></span>        | <span data-ttu-id="d480f-118">Добавлено в PowerShell 6,2</span><span class="sxs-lookup"><span data-stu-id="d480f-118">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="d480f-119">s</span><span class="sxs-lookup"><span data-stu-id="d480f-119">s</span></span>      | <span data-ttu-id="d480f-120">short - тип данных</span><span class="sxs-lookup"><span data-stu-id="d480f-120">short data type</span></span>                | <span data-ttu-id="d480f-121">Добавлено в PowerShell 6,2</span><span class="sxs-lookup"><span data-stu-id="d480f-121">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="d480f-122">us</span><span class="sxs-lookup"><span data-stu-id="d480f-122">us</span></span>     | <span data-ttu-id="d480f-123">короткий тип данных без знака</span><span class="sxs-lookup"><span data-stu-id="d480f-123">unsigned short data type</span></span>       | <span data-ttu-id="d480f-124">Добавлено в PowerShell 6,2</span><span class="sxs-lookup"><span data-stu-id="d480f-124">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="d480f-125">l</span><span class="sxs-lookup"><span data-stu-id="d480f-125">l</span></span>      | <span data-ttu-id="d480f-126">тип данных Long</span><span class="sxs-lookup"><span data-stu-id="d480f-126">long data type</span></span>                 |                         |
| <span data-ttu-id="d480f-127">u</span><span class="sxs-lookup"><span data-stu-id="d480f-127">u</span></span>      | <span data-ttu-id="d480f-128">целое число без знака или тип данных Long</span><span class="sxs-lookup"><span data-stu-id="d480f-128">unsigned int or long data type</span></span> | <span data-ttu-id="d480f-129">Добавлено в PowerShell 6,2</span><span class="sxs-lookup"><span data-stu-id="d480f-129">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="d480f-130">ul</span><span class="sxs-lookup"><span data-stu-id="d480f-130">ul</span></span>     | <span data-ttu-id="d480f-131">тип данных Long без знака</span><span class="sxs-lookup"><span data-stu-id="d480f-131">unsigned long data type</span></span>        | <span data-ttu-id="d480f-132">Добавлено в PowerShell 6,2</span><span class="sxs-lookup"><span data-stu-id="d480f-132">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="d480f-133">kb</span><span class="sxs-lookup"><span data-stu-id="d480f-133">kb</span></span>     | <span data-ttu-id="d480f-134">множитель в килобайтах</span><span class="sxs-lookup"><span data-stu-id="d480f-134">kilobyte multiplier</span></span>            |                         |
| <span data-ttu-id="d480f-135">mb</span><span class="sxs-lookup"><span data-stu-id="d480f-135">mb</span></span>     | <span data-ttu-id="d480f-136">множитель в мегабайтах</span><span class="sxs-lookup"><span data-stu-id="d480f-136">megabyte multiplier</span></span>            |                         |
| <span data-ttu-id="d480f-137">Гбайт</span><span class="sxs-lookup"><span data-stu-id="d480f-137">gb</span></span>     | <span data-ttu-id="d480f-138">множитель гигабайта</span><span class="sxs-lookup"><span data-stu-id="d480f-138">gigabyte multiplier</span></span>            |                         |
| <span data-ttu-id="d480f-139">Тбайт</span><span class="sxs-lookup"><span data-stu-id="d480f-139">tb</span></span>     | <span data-ttu-id="d480f-140">терабайт, множитель</span><span class="sxs-lookup"><span data-stu-id="d480f-140">terabyte multiplier</span></span>            |                         |
| <span data-ttu-id="d480f-141">МС</span><span class="sxs-lookup"><span data-stu-id="d480f-141">pb</span></span>     | <span data-ttu-id="d480f-142">множитель петабайтного уровня</span><span class="sxs-lookup"><span data-stu-id="d480f-142">petabyte multiplier</span></span>            |                         |

<span data-ttu-id="d480f-143">Тип целочисленного литерала определяется его значением, суффиксом типа и суффиксом числового множителя.</span><span class="sxs-lookup"><span data-stu-id="d480f-143">The type of an integer literal is determined by its value, the type suffix, and the numeric multiplier suffix.</span></span>

<span data-ttu-id="d480f-144">Для целочисленного литерала без суффикса типа:</span><span class="sxs-lookup"><span data-stu-id="d480f-144">For an integer literal with no type suffix:</span></span>

- <span data-ttu-id="d480f-145">Если значение может быть представлено типом `[int]` , то есть его типом.</span><span class="sxs-lookup"><span data-stu-id="d480f-145">If the value can be represented by type `[int]`, that is its type.</span></span>
- <span data-ttu-id="d480f-146">В противном случае, если значение может быть представлено типом `[long]` , то есть его тип.</span><span class="sxs-lookup"><span data-stu-id="d480f-146">Otherwise, if the value can be represented by type `[long]`, that is its type.</span></span>
- <span data-ttu-id="d480f-147">В противном случае, если значение может быть представлено типом `[decimal]` , то есть его тип.</span><span class="sxs-lookup"><span data-stu-id="d480f-147">Otherwise, if the value can be represented by type `[decimal]`, that is its type.</span></span>
- <span data-ttu-id="d480f-148">В противном случае он представлен типом `[double]` .</span><span class="sxs-lookup"><span data-stu-id="d480f-148">Otherwise, it is represented by type `[double]`.</span></span>

<span data-ttu-id="d480f-149">Для целочисленного литерала с суффиксом типа:</span><span class="sxs-lookup"><span data-stu-id="d480f-149">For an integer literal with a type suffix:</span></span>

- <span data-ttu-id="d480f-150">Если суффикс типа — `u` , а значение может быть представлено типом, `[uint]` то его тип — `[uint]` .</span><span class="sxs-lookup"><span data-stu-id="d480f-150">If the type suffix is `u` and the value can be represented by type `[uint]` then its type is `[uint]`.</span></span>
- <span data-ttu-id="d480f-151">Если суффикс типа — `u` , а значение может быть представлено типом, `[ulong]` то его тип — `[ulong]` .</span><span class="sxs-lookup"><span data-stu-id="d480f-151">If the type suffix is `u` and the value can be represented by type `[ulong]` then its type is `[ulong]`.</span></span>
- <span data-ttu-id="d480f-152">Если его значение может быть представлено указанным типом, то это тип.</span><span class="sxs-lookup"><span data-stu-id="d480f-152">If its value can be represented by type specified then that is its type.</span></span>
- <span data-ttu-id="d480f-153">В противном случае этот литерал имеет неправильный формат.</span><span class="sxs-lookup"><span data-stu-id="d480f-153">Otherwise, that literal is malformed.</span></span>

## <a name="real-literals"></a><span data-ttu-id="d480f-154">Вещественные литералы</span><span class="sxs-lookup"><span data-stu-id="d480f-154">Real literals</span></span>

<span data-ttu-id="d480f-155">Реальные литералы могут быть записаны только в десятичной нотации.</span><span class="sxs-lookup"><span data-stu-id="d480f-155">Real literals can only be written in decimal notation.</span></span> <span data-ttu-id="d480f-156">Эта нотация может содержать дробные значения, следующие за десятичной запятой и экспоненциальной нотацией, с использованием экспоненциальной части.</span><span class="sxs-lookup"><span data-stu-id="d480f-156">This notation can include fractional values following a decimal point and scientific notation using an exponential part.</span></span>

<span data-ttu-id="d480f-157">Экспоненциальная часть включает символ "e", за которым следует необязательный знак (+/-) и число, представляющее показатель степени.</span><span class="sxs-lookup"><span data-stu-id="d480f-157">The exponential part includes an 'e' followed by an optional sign (+/-) and a number representing the exponent.</span></span> <span data-ttu-id="d480f-158">Например, литеральное значение `1e2` равно числовому значению 100.</span><span class="sxs-lookup"><span data-stu-id="d480f-158">For example, the literal value `1e2` equals the numeric value 100.</span></span>

<span data-ttu-id="d480f-159">Реальные литералы могут иметь суффикс типа и суффикс множителя.</span><span class="sxs-lookup"><span data-stu-id="d480f-159">Real literals can have a type suffix and a multiplier suffix.</span></span>

| <span data-ttu-id="d480f-160">Суффикс</span><span class="sxs-lookup"><span data-stu-id="d480f-160">Suffix</span></span> |       <span data-ttu-id="d480f-161">Значение</span><span class="sxs-lookup"><span data-stu-id="d480f-161">Meaning</span></span>       |
| ------ | ------------------- |
| <span data-ttu-id="d480f-162">d</span><span class="sxs-lookup"><span data-stu-id="d480f-162">d</span></span>      | <span data-ttu-id="d480f-163">тип данных decimal</span><span class="sxs-lookup"><span data-stu-id="d480f-163">decimal data type</span></span>   |
| <span data-ttu-id="d480f-164">kb</span><span class="sxs-lookup"><span data-stu-id="d480f-164">kb</span></span>     | <span data-ttu-id="d480f-165">множитель в килобайтах</span><span class="sxs-lookup"><span data-stu-id="d480f-165">kilobyte multiplier</span></span> |
| <span data-ttu-id="d480f-166">mb</span><span class="sxs-lookup"><span data-stu-id="d480f-166">mb</span></span>     | <span data-ttu-id="d480f-167">множитель в мегабайтах</span><span class="sxs-lookup"><span data-stu-id="d480f-167">megabyte multiplier</span></span> |
| <span data-ttu-id="d480f-168">Гбайт</span><span class="sxs-lookup"><span data-stu-id="d480f-168">gb</span></span>     | <span data-ttu-id="d480f-169">множитель гигабайта</span><span class="sxs-lookup"><span data-stu-id="d480f-169">gigabyte multiplier</span></span> |
| <span data-ttu-id="d480f-170">Тбайт</span><span class="sxs-lookup"><span data-stu-id="d480f-170">tb</span></span>     | <span data-ttu-id="d480f-171">терабайт, множитель</span><span class="sxs-lookup"><span data-stu-id="d480f-171">terabyte multiplier</span></span> |
| <span data-ttu-id="d480f-172">МС</span><span class="sxs-lookup"><span data-stu-id="d480f-172">pb</span></span>     | <span data-ttu-id="d480f-173">множитель петабайтного уровня</span><span class="sxs-lookup"><span data-stu-id="d480f-173">petabyte multiplier</span></span> |

<span data-ttu-id="d480f-174">Существует два вида вещественных литералов: Double и Decimal.</span><span class="sxs-lookup"><span data-stu-id="d480f-174">There are two kinds of real literal: double and decimal.</span></span> <span data-ttu-id="d480f-175">Они обозначаются отсутствием или присутствием соответственно для суффикса десятичного типа.</span><span class="sxs-lookup"><span data-stu-id="d480f-175">These are indicated by the absence or presence, respectively, of decimal-type suffix.</span></span> <span data-ttu-id="d480f-176">PowerShell не поддерживает литеральное представление `[float]` значения.</span><span class="sxs-lookup"><span data-stu-id="d480f-176">PowerShell does not support a literal representation of a `[float]` value.</span></span> <span data-ttu-id="d480f-177">Двойной вещественный литерал имеет тип `[double]` .</span><span class="sxs-lookup"><span data-stu-id="d480f-177">A double real literal has type `[double]`.</span></span> <span data-ttu-id="d480f-178">Десятичный вещественный литерал имеет тип `[decimal]` .</span><span class="sxs-lookup"><span data-stu-id="d480f-178">A decimal real literal has type `[decimal]`.</span></span>
<span data-ttu-id="d480f-179">В дробной части вещественного десятичного литерала учитываются нули в конце.</span><span class="sxs-lookup"><span data-stu-id="d480f-179">Trailing zeros in the fraction part of a decimal real literal are significant.</span></span>

<span data-ttu-id="d480f-180">Если значение числа цифр экспоненты в `[double]` вещественном литерале меньше минимального поддерживаемого значения, значение этого `[double]` литерала равно 0.</span><span class="sxs-lookup"><span data-stu-id="d480f-180">If the value of exponent-part's digits in a `[double]` real literal is less than the minimum supported, the value of that `[double]` real literal is 0.</span></span> <span data-ttu-id="d480f-181">Если значение числа цифр экспоненты в `[decimal]` вещественном литерале меньше минимального поддерживаемого значения, то литерал имеет неправильный формат.</span><span class="sxs-lookup"><span data-stu-id="d480f-181">If the value of exponent-part's digits in a `[decimal]` real literal is less than the minimum supported, that literal is malformed.</span></span> <span data-ttu-id="d480f-182">Если значение числа цифр экспоненты в `[double]` или `[decimal]` вещественном литерале больше поддерживаемого максимума, этот литерал имеет неправильный формат.</span><span class="sxs-lookup"><span data-stu-id="d480f-182">If the value of exponent-part's digits in a `[double]` or `[decimal]` real literal is greater than the maximum supported, that literal is malformed.</span></span>

> [!NOTE]
> <span data-ttu-id="d480f-183">Синтаксис допускает наличие суффикса длинного типа в двойном вещественном литерале.</span><span class="sxs-lookup"><span data-stu-id="d480f-183">The syntax permits a double real literal to have a long-type suffix.</span></span>
> <span data-ttu-id="d480f-184">PowerShell обрабатывает этот случай как целочисленный литерал, значение которого представлено типом `[long]` .</span><span class="sxs-lookup"><span data-stu-id="d480f-184">PowerShell treats this case as an integer literal whose value is represented by type `[long]`.</span></span> <span data-ttu-id="d480f-185">Эта функция была сохранена для обеспечения обратной совместимости с более ранними версиями PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d480f-185">This feature has been retained for backwards compatibility with earlier versions of PowerShell.</span></span> <span data-ttu-id="d480f-186">Однако программистам не рекомендуется использовать целочисленные литералы этой формы, так как они могут легко скрывать фактическое значение литерала.</span><span class="sxs-lookup"><span data-stu-id="d480f-186">However, programmers are discouraged from using integer literals of this form as they can easily obscure the literal's actual value.</span></span> <span data-ttu-id="d480f-187">Например, `1.2L` имеет значение 1, `1.2345e1L` значение 12 и `1.2345e-5L` имеет значение 0, ни одно из этих значений сразу не очевидно.</span><span class="sxs-lookup"><span data-stu-id="d480f-187">For example, `1.2L` has value 1, `1.2345e1L` has value 12, and `1.2345e-5L` has value 0, none of which are immediately obvious.</span></span>

## <a name="numeric-multipliers"></a><span data-ttu-id="d480f-188">Числовые множители</span><span class="sxs-lookup"><span data-stu-id="d480f-188">Numeric multipliers</span></span>

<span data-ttu-id="d480f-189">Для удобства целочисленные и реальные литералы могут содержать числовой множитель, указывающий на один из множества часто используемых степеней 2.</span><span class="sxs-lookup"><span data-stu-id="d480f-189">For convenience, integer and real literals can contain a numeric multiplier, which indicates one of a set of commonly used powers of 2.</span></span> <span data-ttu-id="d480f-190">Числовой множитель можно записать в любом сочетании прописных или строчных букв.</span><span class="sxs-lookup"><span data-stu-id="d480f-190">The numeric multiplier can be written in any combination of upper or lowercase letters.</span></span>

<span data-ttu-id="d480f-191">Суффиксы множителя можно использовать в сочетании с `u` `ul` `l` суффиксами типов, и.</span><span class="sxs-lookup"><span data-stu-id="d480f-191">The multiplier suffixes can be used in combination with the `u`, `ul`, and `l` type suffixes.</span></span>

### <a name="multiplier-examples"></a><span data-ttu-id="d480f-192">Примеры множителя</span><span class="sxs-lookup"><span data-stu-id="d480f-192">Multiplier examples</span></span>

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

## <a name="numeric-type-accelerators"></a><span data-ttu-id="d480f-193">Сочетания числовых типов</span><span class="sxs-lookup"><span data-stu-id="d480f-193">Numeric type accelerators</span></span>

<span data-ttu-id="d480f-194">PowerShell поддерживает следующие ускорители типов:</span><span class="sxs-lookup"><span data-stu-id="d480f-194">PowerShell supports the following type accelerators:</span></span>

| <span data-ttu-id="d480f-195">Accelerator</span><span class="sxs-lookup"><span data-stu-id="d480f-195">Accelerator</span></span> |         <span data-ttu-id="d480f-196">Примечание</span><span class="sxs-lookup"><span data-stu-id="d480f-196">Note</span></span>         |           <span data-ttu-id="d480f-197">Описание</span><span class="sxs-lookup"><span data-stu-id="d480f-197">Description</span></span>            |
| ----------- | -------------------- | -------------------------------- |
| `[byte]`    |                      | <span data-ttu-id="d480f-198">Byte (без знака)</span><span class="sxs-lookup"><span data-stu-id="d480f-198">Byte (unsigned)</span></span>                  |
| `[sbyte]`   |                      | <span data-ttu-id="d480f-199">Byte (со знаком)</span><span class="sxs-lookup"><span data-stu-id="d480f-199">Byte (signed)</span></span>                    |
| `[Int16]`   |                      | <span data-ttu-id="d480f-200">16-разрядное целое число</span><span class="sxs-lookup"><span data-stu-id="d480f-200">16-bit integer</span></span>                   |
| `[short]`   | <span data-ttu-id="d480f-201">псевдоним для `[int16]`</span><span class="sxs-lookup"><span data-stu-id="d480f-201">alias for `[int16]`</span></span>  | <span data-ttu-id="d480f-202">16-разрядное целое число</span><span class="sxs-lookup"><span data-stu-id="d480f-202">16-bit integer</span></span>                   |
| `[UInt16]`  |                      | <span data-ttu-id="d480f-203">16-разрядное целое число (без знака)</span><span class="sxs-lookup"><span data-stu-id="d480f-203">16-bit integer (unsigned)</span></span>        |
| `[ushort]`  | <span data-ttu-id="d480f-204">псевдоним для `[uint16]`</span><span class="sxs-lookup"><span data-stu-id="d480f-204">alias for `[uint16]`</span></span> | <span data-ttu-id="d480f-205">16-разрядное целое число (без знака)</span><span class="sxs-lookup"><span data-stu-id="d480f-205">16-bit integer (unsigned)</span></span>        |
| `[Int32]`   |                      | <span data-ttu-id="d480f-206">32-разрядное целое число</span><span class="sxs-lookup"><span data-stu-id="d480f-206">32-bit integer</span></span>                   |
| `[int]`     | <span data-ttu-id="d480f-207">псевдоним для `[int32]`</span><span class="sxs-lookup"><span data-stu-id="d480f-207">alias for `[int32]`</span></span>  | <span data-ttu-id="d480f-208">32-разрядное целое число</span><span class="sxs-lookup"><span data-stu-id="d480f-208">32-bit integer</span></span>                   |
| `[UInt32]`  |                      | <span data-ttu-id="d480f-209">32-разрядное целое число (без знака)</span><span class="sxs-lookup"><span data-stu-id="d480f-209">32-bit integer (unsigned)</span></span>        |
| `[uint]`    | <span data-ttu-id="d480f-210">псевдоним для `[uint32]`</span><span class="sxs-lookup"><span data-stu-id="d480f-210">alias for `[uint32]`</span></span> | <span data-ttu-id="d480f-211">32-разрядное целое число (без знака)</span><span class="sxs-lookup"><span data-stu-id="d480f-211">32-bit integer (unsigned)</span></span>        |
| `[Int64]`   |                      | <span data-ttu-id="d480f-212">64-разрядное целое число</span><span class="sxs-lookup"><span data-stu-id="d480f-212">64-bit integer</span></span>                   |
| `[long]`    | <span data-ttu-id="d480f-213">псевдоним для `[int64]`</span><span class="sxs-lookup"><span data-stu-id="d480f-213">alias for `[int64]`</span></span>  | <span data-ttu-id="d480f-214">64-разрядное целое число</span><span class="sxs-lookup"><span data-stu-id="d480f-214">64-bit integer</span></span>                   |
| `[UInt64]`  |                      | <span data-ttu-id="d480f-215">64-разрядное целое число (без знака)</span><span class="sxs-lookup"><span data-stu-id="d480f-215">64-bit integer (unsigned)</span></span>        |
| `[ulong]`   | <span data-ttu-id="d480f-216">псевдоним для `[uint64]`</span><span class="sxs-lookup"><span data-stu-id="d480f-216">alias for `[uint64]`</span></span> | <span data-ttu-id="d480f-217">64-разрядное целое число (без знака)</span><span class="sxs-lookup"><span data-stu-id="d480f-217">64-bit integer (unsigned)</span></span>        |
| `[bigint]`  |                      | <span data-ttu-id="d480f-218">См. [структуру BigInteger][bigint]</span><span class="sxs-lookup"><span data-stu-id="d480f-218">See [BigInteger Struct][bigint]</span></span>  |
| `[single]`  |                      | <span data-ttu-id="d480f-219">Одинарная точность с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="d480f-219">Single precision floating point</span></span>  |
| `[float]`   | <span data-ttu-id="d480f-220">псевдоним для `[single]`</span><span class="sxs-lookup"><span data-stu-id="d480f-220">alias for `[single]`</span></span> | <span data-ttu-id="d480f-221">Одинарная точность с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="d480f-221">Single precision floating point</span></span>  |
| `[double]`  |                      | <span data-ttu-id="d480f-222">Плавающая точка с двойной точностью</span><span class="sxs-lookup"><span data-stu-id="d480f-222">Double precision floating point</span></span>  |
| `[decimal]` |                      | <span data-ttu-id="d480f-223">128-разрядная с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="d480f-223">128-bit floating point</span></span>           |

> [!NOTE]
> <span data-ttu-id="d480f-224">В PowerShell 6,2 были добавлены следующие ускорители типов: `[short]` , `[ushort]` , `[uint]` , `[ulong]` .</span><span class="sxs-lookup"><span data-stu-id="d480f-224">The following type accelerators were added in PowerShell 6.2: `[short]`, `[ushort]`, `[uint]`, `[ulong]`.</span></span>

### <a name="working-with-other-numeric-types"></a><span data-ttu-id="d480f-225">Работа с другими числовыми типами</span><span class="sxs-lookup"><span data-stu-id="d480f-225">Working with other numeric types</span></span>

<span data-ttu-id="d480f-226">Для работы с любыми другими числовыми типами необходимо использовать ускорители типов, которые не позволяют устранить некоторые проблемы.</span><span class="sxs-lookup"><span data-stu-id="d480f-226">To work with any other numeric types you must use type accelerators, which is not without some problems.</span></span> <span data-ttu-id="d480f-227">Например, большие целочисленные значения всегда анализируются как Double перед их приведением к любому другому типу.</span><span class="sxs-lookup"><span data-stu-id="d480f-227">For example, high integer values are always parsed as double before being cast to any other type.</span></span>

```
PS> [bigint]111111111111111111111111111111111111111111111111111111
111111111111111100905595216014112456735339620444667904
```

<span data-ttu-id="d480f-228">Значение сначала анализируется как Double, что приводит к потере точности в более высоких диапазонах.</span><span class="sxs-lookup"><span data-stu-id="d480f-228">The value is parsed as a double first, losing precision in the higher ranges.</span></span>
<span data-ttu-id="d480f-229">Чтобы избежать этой проблемы, введите значения в виде строк, а затем преобразуйте их:</span><span class="sxs-lookup"><span data-stu-id="d480f-229">To avoid this problem, enter values as strings and then convert them:</span></span>

```
PS> [bigint]'111111111111111111111111111111111111111111111111111111'
111111111111111111111111111111111111111111111111111111
```

## <a name="examples"></a><span data-ttu-id="d480f-230">Примеры</span><span class="sxs-lookup"><span data-stu-id="d480f-230">Examples</span></span>

<span data-ttu-id="d480f-231">Следующая таблица содержит несколько примеров числовых литералов и перечисляет их тип и значение.</span><span class="sxs-lookup"><span data-stu-id="d480f-231">The following table contains several examples of numeric literals and lists their type and value:</span></span>

|  <span data-ttu-id="d480f-232">Число</span><span class="sxs-lookup"><span data-stu-id="d480f-232">Number</span></span>  |  <span data-ttu-id="d480f-233">Тип</span><span class="sxs-lookup"><span data-stu-id="d480f-233">Type</span></span>   |    <span data-ttu-id="d480f-234">Значение</span><span class="sxs-lookup"><span data-stu-id="d480f-234">Value</span></span>     |
| -------: | ------- | -----------: |
|      <span data-ttu-id="d480f-235">100</span><span class="sxs-lookup"><span data-stu-id="d480f-235">100</span></span> | <span data-ttu-id="d480f-236">Int32</span><span class="sxs-lookup"><span data-stu-id="d480f-236">Int32</span></span>   |          <span data-ttu-id="d480f-237">100</span><span class="sxs-lookup"><span data-stu-id="d480f-237">100</span></span> |
|     <span data-ttu-id="d480f-238">100D</span><span class="sxs-lookup"><span data-stu-id="d480f-238">100D</span></span> | <span data-ttu-id="d480f-239">Decimal</span><span class="sxs-lookup"><span data-stu-id="d480f-239">Decimal</span></span> |          <span data-ttu-id="d480f-240">100</span><span class="sxs-lookup"><span data-stu-id="d480f-240">100</span></span> |
|     <span data-ttu-id="d480f-241">100l</span><span class="sxs-lookup"><span data-stu-id="d480f-241">100l</span></span> | <span data-ttu-id="d480f-242">Int64</span><span class="sxs-lookup"><span data-stu-id="d480f-242">Int64</span></span>   |          <span data-ttu-id="d480f-243">100</span><span class="sxs-lookup"><span data-stu-id="d480f-243">100</span></span> |
|    <span data-ttu-id="d480f-244">100uL</span><span class="sxs-lookup"><span data-stu-id="d480f-244">100uL</span></span> | <span data-ttu-id="d480f-245">UInt64</span><span class="sxs-lookup"><span data-stu-id="d480f-245">UInt64</span></span>  |          <span data-ttu-id="d480f-246">100</span><span class="sxs-lookup"><span data-stu-id="d480f-246">100</span></span> |
|    <span data-ttu-id="d480f-247">100us</span><span class="sxs-lookup"><span data-stu-id="d480f-247">100us</span></span> | <span data-ttu-id="d480f-248">UInt16</span><span class="sxs-lookup"><span data-stu-id="d480f-248">UInt16</span></span>  |          <span data-ttu-id="d480f-249">100</span><span class="sxs-lookup"><span data-stu-id="d480f-249">100</span></span> |
|    <span data-ttu-id="d480f-250">100uy</span><span class="sxs-lookup"><span data-stu-id="d480f-250">100uy</span></span> | <span data-ttu-id="d480f-251">Byte</span><span class="sxs-lookup"><span data-stu-id="d480f-251">Byte</span></span>    |          <span data-ttu-id="d480f-252">100</span><span class="sxs-lookup"><span data-stu-id="d480f-252">100</span></span> |
|     <span data-ttu-id="d480f-253">100y</span><span class="sxs-lookup"><span data-stu-id="d480f-253">100y</span></span> | <span data-ttu-id="d480f-254">SByte</span><span class="sxs-lookup"><span data-stu-id="d480f-254">SByte</span></span>   |          <span data-ttu-id="d480f-255">100</span><span class="sxs-lookup"><span data-stu-id="d480f-255">100</span></span> |
|      <span data-ttu-id="d480f-256">1e2</span><span class="sxs-lookup"><span data-stu-id="d480f-256">1e2</span></span> | <span data-ttu-id="d480f-257">Double</span><span class="sxs-lookup"><span data-stu-id="d480f-257">Double</span></span>  |          <span data-ttu-id="d480f-258">100</span><span class="sxs-lookup"><span data-stu-id="d480f-258">100</span></span> |
|     <span data-ttu-id="d480f-259">1. E2</span><span class="sxs-lookup"><span data-stu-id="d480f-259">1.e2</span></span> | <span data-ttu-id="d480f-260">Double</span><span class="sxs-lookup"><span data-stu-id="d480f-260">Double</span></span>  |          <span data-ttu-id="d480f-261">100</span><span class="sxs-lookup"><span data-stu-id="d480f-261">100</span></span> |
|    <span data-ttu-id="d480f-262">0x1e2</span><span class="sxs-lookup"><span data-stu-id="d480f-262">0x1e2</span></span> | <span data-ttu-id="d480f-263">Int32</span><span class="sxs-lookup"><span data-stu-id="d480f-263">Int32</span></span>   |          <span data-ttu-id="d480f-264">482</span><span class="sxs-lookup"><span data-stu-id="d480f-264">482</span></span> |
|   <span data-ttu-id="d480f-265">0x1e2L</span><span class="sxs-lookup"><span data-stu-id="d480f-265">0x1e2L</span></span> | <span data-ttu-id="d480f-266">Int64</span><span class="sxs-lookup"><span data-stu-id="d480f-266">Int64</span></span>   |          <span data-ttu-id="d480f-267">482</span><span class="sxs-lookup"><span data-stu-id="d480f-267">482</span></span> |
|   <span data-ttu-id="d480f-268">0x1e2D</span><span class="sxs-lookup"><span data-stu-id="d480f-268">0x1e2D</span></span> | <span data-ttu-id="d480f-269">Int32</span><span class="sxs-lookup"><span data-stu-id="d480f-269">Int32</span></span>   |         <span data-ttu-id="d480f-270">7725</span><span class="sxs-lookup"><span data-stu-id="d480f-270">7725</span></span> |
|     <span data-ttu-id="d480f-271">482D</span><span class="sxs-lookup"><span data-stu-id="d480f-271">482D</span></span> | <span data-ttu-id="d480f-272">Decimal</span><span class="sxs-lookup"><span data-stu-id="d480f-272">Decimal</span></span> |          <span data-ttu-id="d480f-273">482</span><span class="sxs-lookup"><span data-stu-id="d480f-273">482</span></span> |
|    <span data-ttu-id="d480f-274">482gb</span><span class="sxs-lookup"><span data-stu-id="d480f-274">482gb</span></span> | <span data-ttu-id="d480f-275">Int64</span><span class="sxs-lookup"><span data-stu-id="d480f-275">Int64</span></span>   | <span data-ttu-id="d480f-276">517543559168</span><span class="sxs-lookup"><span data-stu-id="d480f-276">517543559168</span></span> |
| <span data-ttu-id="d480f-277">0x1e2lgb</span><span class="sxs-lookup"><span data-stu-id="d480f-277">0x1e2lgb</span></span> | <span data-ttu-id="d480f-278">Int64</span><span class="sxs-lookup"><span data-stu-id="d480f-278">Int64</span></span>   | <span data-ttu-id="d480f-279">517543559168</span><span class="sxs-lookup"><span data-stu-id="d480f-279">517543559168</span></span> |

### <a name="commands-that-look-like-numeric-literals"></a><span data-ttu-id="d480f-280">Команды, которые выглядят как числовые литералы</span><span class="sxs-lookup"><span data-stu-id="d480f-280">Commands that look like numeric literals</span></span>

<span data-ttu-id="d480f-281">Любая команда, похожая на числовой литерал, должна выполняться с помощью оператора Call ( `&` ), в противном случае он интерпретируется как число связанного типа.</span><span class="sxs-lookup"><span data-stu-id="d480f-281">Any command that looks like a numeric literal must be executed using the the call operator (`&`), otherwise it is interpreted as a number of the associated type.</span></span>

### <a name="access-properties-and-methods-of-numeric-objects"></a><span data-ttu-id="d480f-282">Доступ к свойствам и методам числовых объектов</span><span class="sxs-lookup"><span data-stu-id="d480f-282">Access properties and methods of numeric objects</span></span>

<span data-ttu-id="d480f-283">Для доступа к элементу числового литерала бывают случаи, когда необходимо заключить литерал в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="d480f-283">To access a member of a numeric literal, there are cases when you need to enclose the literal in parentheses.</span></span>

- <span data-ttu-id="d480f-284">Литерал не имеет десятичной запятой</span><span class="sxs-lookup"><span data-stu-id="d480f-284">The literal does not have a decimal point</span></span>
- <span data-ttu-id="d480f-285">Литерал не содержит цифр после десятичной запятой</span><span class="sxs-lookup"><span data-stu-id="d480f-285">The literal does not have any digits following the decimal point</span></span>
- <span data-ttu-id="d480f-286">У литерала нет суффикса</span><span class="sxs-lookup"><span data-stu-id="d480f-286">The literal does not have a suffix</span></span>

<span data-ttu-id="d480f-287">Например, следующий пример завершается ошибкой:</span><span class="sxs-lookup"><span data-stu-id="d480f-287">For example, the following example fails:</span></span>

```
PS> 2.GetType().Name
At line:1 char:11
+ 2.GetType().Name
+           ~
An expression was expected after '('.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
+ FullyQualifiedErrorId : ExpectedExpression
```

<span data-ttu-id="d480f-288">Ниже приведены примеры работы.</span><span class="sxs-lookup"><span data-stu-id="d480f-288">The following examples work:</span></span>

```
PS> 2uL.GetType().Name
UInt64
PS> 1.234.GetType().Name
Double
PS> (2).GetType().Name
Int32
```

<span data-ttu-id="d480f-289">Первые два примера работают без заключения литерального значения в круглые скобки, так как средство синтаксического анализа PowerShell может определить, где заканчивается числовой литерал, и запустить метод **GetType** .</span><span class="sxs-lookup"><span data-stu-id="d480f-289">The first two examples work without enclosing the literal value in parentheses because the PowerShell parser can determine where the numeric literal ends and the **GetType** method starts.</span></span>

<!-- reference links -->
[bigint]: /dotnet/api/system.numerics.biginteger?view=netcore-2.2
