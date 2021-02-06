---
description: Описывает операторы, которые соединяют инструкции в PowerShell.
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_logical_operators?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Logical_Operators
ms.openlocfilehash: 8602551f3ecf74027b59715e1f47aab1b10bea92
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603108"
---
# <a name="about_logical_operators"></a><span data-ttu-id="91a7c-103">about_Logical_Operators</span><span class="sxs-lookup"><span data-stu-id="91a7c-103">about_Logical_Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="91a7c-104">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="91a7c-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="91a7c-105">Описывает операторы, которые соединяют инструкции в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91a7c-105">Describes the operators that connect statements in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="91a7c-106">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="91a7c-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="91a7c-107">Логические операторы PowerShell соединяют выражения и операторы, позволяя использовать одно выражение для проверки нескольких условий.</span><span class="sxs-lookup"><span data-stu-id="91a7c-107">The PowerShell logical operators connect expressions and statements, allowing you to use a single expression to test for multiple conditions.</span></span>

<span data-ttu-id="91a7c-108">Например, следующая инструкция использует оператор and и оператор OR для соединения трех условных операторов.</span><span class="sxs-lookup"><span data-stu-id="91a7c-108">For example, the following statement uses the and operator and the or operator to connect three conditional statements.</span></span> <span data-ttu-id="91a7c-109">Оператор имеет значение true, только если значение $a больше значения $b, а либо $a, либо $b меньше</span><span class="sxs-lookup"><span data-stu-id="91a7c-109">The statement is true only when the value of $a is greater than the value of $b, and either $a or $b is less than</span></span>
20.

```powershell
($a -gt $b) -and (($a -lt 20) -or ($b -lt 20))
```

<span data-ttu-id="91a7c-110">PowerShell поддерживает следующие логические операторы.</span><span class="sxs-lookup"><span data-stu-id="91a7c-110">PowerShell supports the following logical operators.</span></span>

|<span data-ttu-id="91a7c-111">Оператор</span><span class="sxs-lookup"><span data-stu-id="91a7c-111">Operator</span></span>|<span data-ttu-id="91a7c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="91a7c-112">Description</span></span>                        |<span data-ttu-id="91a7c-113">Пример</span><span class="sxs-lookup"><span data-stu-id="91a7c-113">Example</span></span>                   |
|--------|-----------------------------------|--------------------------|
|`-and`  |<span data-ttu-id="91a7c-114">Логический оператор AND.</span><span class="sxs-lookup"><span data-stu-id="91a7c-114">Logical AND.</span></span> <span data-ttu-id="91a7c-115">TRUE, если оба</span><span class="sxs-lookup"><span data-stu-id="91a7c-115">TRUE when both</span></span>        |`(1 -eq 1) -and (1 -eq 2)`|
|        |<span data-ttu-id="91a7c-116">операторы имеют значение TRUE.</span><span class="sxs-lookup"><span data-stu-id="91a7c-116">statements are TRUE.</span></span>               |`False`                   |
|`-or`   |<span data-ttu-id="91a7c-117">Логический оператор OR.</span><span class="sxs-lookup"><span data-stu-id="91a7c-117">Logical OR.</span></span> <span data-ttu-id="91a7c-118">TRUE, если либо</span><span class="sxs-lookup"><span data-stu-id="91a7c-118">TRUE when either</span></span>       |`(1 -eq 1) -or (1 -eq 2)` |
|        |<span data-ttu-id="91a7c-119">Инструкция имеет значение TRUE.</span><span class="sxs-lookup"><span data-stu-id="91a7c-119">statement is TRUE.</span></span>                 |`True`                    |
|`-xor`  |<span data-ttu-id="91a7c-120">Логическое ИСКЛЮЧАЮЩее или.</span><span class="sxs-lookup"><span data-stu-id="91a7c-120">Logical EXCLUSIVE OR.</span></span> <span data-ttu-id="91a7c-121">TRUE, если</span><span class="sxs-lookup"><span data-stu-id="91a7c-121">TRUE when</span></span>    |`(1 -eq 1) -xor (2 -eq 2)`|
|        |<span data-ttu-id="91a7c-122">только одна инструкция имеет значение TRUE</span><span class="sxs-lookup"><span data-stu-id="91a7c-122">only one statement is TRUE</span></span>         |`False`                   |
|`-not`  |<span data-ttu-id="91a7c-123">Логическое не.</span><span class="sxs-lookup"><span data-stu-id="91a7c-123">Logical not.</span></span> <span data-ttu-id="91a7c-124">Инвертирует оператор</span><span class="sxs-lookup"><span data-stu-id="91a7c-124">Negates the statement</span></span> |`-not (1 -eq 1)`          |
|        |<span data-ttu-id="91a7c-125">Далее.</span><span class="sxs-lookup"><span data-stu-id="91a7c-125">that follows.</span></span>                      |`False`                   |
|`!`     |<span data-ttu-id="91a7c-126">То же, что `-not`</span><span class="sxs-lookup"><span data-stu-id="91a7c-126">Same as `-not`</span></span>                     |`!(1 -eq 1)`              |
|        |                                   |`False`                   |

 <span data-ttu-id="91a7c-127">Примечание.</span><span class="sxs-lookup"><span data-stu-id="91a7c-127">Note:</span></span>

<span data-ttu-id="91a7c-128">В предыдущих примерах также используется оператор сравнения EQUAL TO `-eq` .</span><span class="sxs-lookup"><span data-stu-id="91a7c-128">The previous examples also use the equal to comparison operator `-eq`.</span></span> <span data-ttu-id="91a7c-129">Дополнительные сведения см. в разделе [about_Comparison_Operators](about_Comparison_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="91a7c-129">For more information, see [about_Comparison_Operators](about_Comparison_Operators.md).</span></span> <span data-ttu-id="91a7c-130">В примерах также используются логические значения целых чисел.</span><span class="sxs-lookup"><span data-stu-id="91a7c-130">The examples also use the Boolean values of integers.</span></span> <span data-ttu-id="91a7c-131">Целое число 0 имеет значение FALSE.</span><span class="sxs-lookup"><span data-stu-id="91a7c-131">The integer 0 has a value of FALSE.</span></span> <span data-ttu-id="91a7c-132">Все остальные целые числа имеют значение TRUE.</span><span class="sxs-lookup"><span data-stu-id="91a7c-132">All other integers have a value of TRUE.</span></span>

<span data-ttu-id="91a7c-133">Синтаксис логических операторов выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="91a7c-133">The syntax of the logical operators is as follows:</span></span>

```
<statement> {-AND | -OR | -XOR} <statement>
{! | -NOT} <statement>
```

<span data-ttu-id="91a7c-134">Инструкции, использующие логические операторы, возвращают логические значения (TRUE или FALSE).</span><span class="sxs-lookup"><span data-stu-id="91a7c-134">Statements that use the logical operators return Boolean (TRUE or FALSE) values.</span></span>

<span data-ttu-id="91a7c-135">Логические операторы PowerShell оценивают только те операторы, которые необходимы для определения истинного значения инструкции.</span><span class="sxs-lookup"><span data-stu-id="91a7c-135">The PowerShell logical operators evaluate only the statements required to determine the truth value of the statement.</span></span> <span data-ttu-id="91a7c-136">Если левый операнд в операторе, содержащем оператор and, имеет значение FALSE, правый операнд не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="91a7c-136">If the left operand in a statement that contains the and operator is FALSE, the right operand is not evaluated.</span></span>
<span data-ttu-id="91a7c-137">Если левый операнд в операторе, содержащем оператор или, имеет значение TRUE, правый операнд не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="91a7c-137">If the left operand in a statement that contains the or statement is TRUE, the right operand is not evaluated.</span></span> <span data-ttu-id="91a7c-138">В результате эти инструкции можно использовать точно так же, как при использовании `If` оператора.</span><span class="sxs-lookup"><span data-stu-id="91a7c-138">As a result, you can use these statements in the same way that you would use the `If` statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="91a7c-139">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="91a7c-139">SEE ALSO</span></span>

[<span data-ttu-id="91a7c-140">about_Operators</span><span class="sxs-lookup"><span data-stu-id="91a7c-140">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="91a7c-141">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="91a7c-141">Compare-Object</span></span>](xref:Microsoft.PowerShell.Utility.Compare-Object)

[<span data-ttu-id="91a7c-142">about_Comparison_operators</span><span class="sxs-lookup"><span data-stu-id="91a7c-142">about_Comparison_operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="91a7c-143">about_If</span><span class="sxs-lookup"><span data-stu-id="91a7c-143">about_If</span></span>](about_If.md)

