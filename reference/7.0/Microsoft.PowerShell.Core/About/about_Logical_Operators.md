---
description: Описывает операторы, которые соединяют инструкции в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_logical_operators?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Logical_Operators
ms.openlocfilehash: 1262ed0f5797d8dcb8cb4719cad69ac6b6a28d59
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231758"
---
# <a name="about_logical_operators"></a><span data-ttu-id="5bf85-104">about_Logical_Operators</span><span class="sxs-lookup"><span data-stu-id="5bf85-104">about_Logical_Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="5bf85-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="5bf85-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="5bf85-106">Описывает операторы, которые соединяют инструкции в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5bf85-106">Describes the operators that connect statements in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="5bf85-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="5bf85-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="5bf85-108">Логические операторы PowerShell соединяют выражения и операторы, позволяя использовать одно выражение для проверки нескольких условий.</span><span class="sxs-lookup"><span data-stu-id="5bf85-108">The PowerShell logical operators connect expressions and statements, allowing you to use a single expression to test for multiple conditions.</span></span>

<span data-ttu-id="5bf85-109">Например, следующая инструкция использует оператор and и оператор OR для соединения трех условных операторов.</span><span class="sxs-lookup"><span data-stu-id="5bf85-109">For example, the following statement uses the and operator and the or operator to connect three conditional statements.</span></span> <span data-ttu-id="5bf85-110">Оператор имеет значение true, только если значение $a больше значения $b, а либо $a, либо $b меньше</span><span class="sxs-lookup"><span data-stu-id="5bf85-110">The statement is true only when the value of $a is greater than the value of $b, and either $a or $b is less than</span></span>
20.

```powershell
($a -gt $b) -and (($a -lt 20) -or ($b -lt 20))
```

<span data-ttu-id="5bf85-111">PowerShell поддерживает следующие логические операторы.</span><span class="sxs-lookup"><span data-stu-id="5bf85-111">PowerShell supports the following logical operators.</span></span>

|<span data-ttu-id="5bf85-112">Оператор</span><span class="sxs-lookup"><span data-stu-id="5bf85-112">Operator</span></span>|<span data-ttu-id="5bf85-113">Описание</span><span class="sxs-lookup"><span data-stu-id="5bf85-113">Description</span></span>                        |<span data-ttu-id="5bf85-114">Пример</span><span class="sxs-lookup"><span data-stu-id="5bf85-114">Example</span></span>                   |
|--------|-----------------------------------|--------------------------|
|`-and`  |<span data-ttu-id="5bf85-115">Логический оператор AND.</span><span class="sxs-lookup"><span data-stu-id="5bf85-115">Logical AND.</span></span> <span data-ttu-id="5bf85-116">TRUE, если оба</span><span class="sxs-lookup"><span data-stu-id="5bf85-116">TRUE when both</span></span>        |`(1 -eq 1) -and (1 -eq 2)`|
|        |<span data-ttu-id="5bf85-117">операторы имеют значение TRUE.</span><span class="sxs-lookup"><span data-stu-id="5bf85-117">statements are TRUE.</span></span>               |`False`                   |
|`-or`   |<span data-ttu-id="5bf85-118">Логический оператор OR.</span><span class="sxs-lookup"><span data-stu-id="5bf85-118">Logical OR.</span></span> <span data-ttu-id="5bf85-119">TRUE, если либо</span><span class="sxs-lookup"><span data-stu-id="5bf85-119">TRUE when either</span></span>       |`(1 -eq 1) -or (1 -eq 2)` |
|        |<span data-ttu-id="5bf85-120">Инструкция имеет значение TRUE.</span><span class="sxs-lookup"><span data-stu-id="5bf85-120">statement is TRUE.</span></span>                 |`True`                    |
|`-xor`  |<span data-ttu-id="5bf85-121">Логическое ИСКЛЮЧАЮЩее или.</span><span class="sxs-lookup"><span data-stu-id="5bf85-121">Logical EXCLUSIVE OR.</span></span> <span data-ttu-id="5bf85-122">TRUE, если</span><span class="sxs-lookup"><span data-stu-id="5bf85-122">TRUE when</span></span>    |`(1 -eq 1) -xor (2 -eq 2)`|
|        |<span data-ttu-id="5bf85-123">только одна инструкция имеет значение TRUE</span><span class="sxs-lookup"><span data-stu-id="5bf85-123">only one statement is TRUE</span></span>         |`False`                   |
|`-not`  |<span data-ttu-id="5bf85-124">Логическое не.</span><span class="sxs-lookup"><span data-stu-id="5bf85-124">Logical not.</span></span> <span data-ttu-id="5bf85-125">Инвертирует оператор</span><span class="sxs-lookup"><span data-stu-id="5bf85-125">Negates the statement</span></span> |`-not (1 -eq 1)`          |
|        |<span data-ttu-id="5bf85-126">Далее.</span><span class="sxs-lookup"><span data-stu-id="5bf85-126">that follows.</span></span>                      |`False`                   |
|`!`     |<span data-ttu-id="5bf85-127">То же, что `-not`</span><span class="sxs-lookup"><span data-stu-id="5bf85-127">Same as `-not`</span></span>                     |`!(1 -eq 1)`              |
|        |                                   |`False`                   |

 <span data-ttu-id="5bf85-128">Примечание.</span><span class="sxs-lookup"><span data-stu-id="5bf85-128">Note:</span></span>

<span data-ttu-id="5bf85-129">В предыдущих примерах также используется оператор сравнения EQUAL TO `-eq` .</span><span class="sxs-lookup"><span data-stu-id="5bf85-129">The previous examples also use the equal to comparison operator `-eq`.</span></span> <span data-ttu-id="5bf85-130">Дополнительные сведения см. в разделе [about_Comparison_Operators](about_Comparison_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="5bf85-130">For more information, see [about_Comparison_Operators](about_Comparison_Operators.md).</span></span> <span data-ttu-id="5bf85-131">В примерах также используются логические значения целых чисел.</span><span class="sxs-lookup"><span data-stu-id="5bf85-131">The examples also use the Boolean values of integers.</span></span> <span data-ttu-id="5bf85-132">Целое число 0 имеет значение FALSE.</span><span class="sxs-lookup"><span data-stu-id="5bf85-132">The integer 0 has a value of FALSE.</span></span> <span data-ttu-id="5bf85-133">Все остальные целые числа имеют значение TRUE.</span><span class="sxs-lookup"><span data-stu-id="5bf85-133">All other integers have a value of TRUE.</span></span>

<span data-ttu-id="5bf85-134">Синтаксис логических операторов выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5bf85-134">The syntax of the logical operators is as follows:</span></span>

```
<statement> {-AND | -OR | -XOR} <statement>
{! | -NOT} <statement>
```

<span data-ttu-id="5bf85-135">Инструкции, использующие логические операторы, возвращают логические значения (TRUE или FALSE).</span><span class="sxs-lookup"><span data-stu-id="5bf85-135">Statements that use the logical operators return Boolean (TRUE or FALSE) values.</span></span>

<span data-ttu-id="5bf85-136">Логические операторы PowerShell оценивают только те операторы, которые необходимы для определения истинного значения инструкции.</span><span class="sxs-lookup"><span data-stu-id="5bf85-136">The PowerShell logical operators evaluate only the statements required to determine the truth value of the statement.</span></span> <span data-ttu-id="5bf85-137">Если левый операнд в операторе, содержащем оператор and, имеет значение FALSE, правый операнд не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="5bf85-137">If the left operand in a statement that contains the and operator is FALSE, the right operand is not evaluated.</span></span>
<span data-ttu-id="5bf85-138">Если левый операнд в операторе, содержащем оператор или, имеет значение TRUE, правый операнд не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="5bf85-138">If the left operand in a statement that contains the or statement is TRUE, the right operand is not evaluated.</span></span> <span data-ttu-id="5bf85-139">В результате эти инструкции можно использовать точно так же, как при использовании `If` оператора.</span><span class="sxs-lookup"><span data-stu-id="5bf85-139">As a result, you can use these statements in the same way that you would use the `If` statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="5bf85-140">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="5bf85-140">SEE ALSO</span></span>

[<span data-ttu-id="5bf85-141">about_Operators</span><span class="sxs-lookup"><span data-stu-id="5bf85-141">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="5bf85-142">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="5bf85-142">Compare-Object</span></span>](xref:Microsoft.PowerShell.Utility.Compare-Object)

[<span data-ttu-id="5bf85-143">about_Comparison_operators</span><span class="sxs-lookup"><span data-stu-id="5bf85-143">about_Comparison_operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="5bf85-144">about_If</span><span class="sxs-lookup"><span data-stu-id="5bf85-144">about_If</span></span>](about_If.md)
