---
description: Перечисляет операторы PowerShell в порядке очередности.
keywords: powershell,командлет
Locale: en-US
ms.date: 11/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_operator_precedence?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Operator_Precedence
ms.openlocfilehash: 27cc1be95067a38e6c210b37a3398416d0845846
ms.sourcegitcommit: 768816a5c05cc2d07ffd84bed95b0499f4b49f2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2020
ms.locfileid: "94483049"
---
# <a name="about-operator-precedence"></a><span data-ttu-id="ad2ab-104">О приоритете операторов</span><span class="sxs-lookup"><span data-stu-id="ad2ab-104">About Operator Precedence</span></span>

## <a name="short-description"></a><span data-ttu-id="ad2ab-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="ad2ab-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="ad2ab-106">Перечисляет операторы PowerShell в порядке очередности.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-106">Lists the PowerShell operators in precedence order.</span></span>

## <a name="long-description"></a><span data-ttu-id="ad2ab-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="ad2ab-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="ad2ab-108">Операторы PowerShell позволяют создавать простые, но мощные выражения.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-108">PowerShell operators let you construct simple, but powerful expressions.</span></span> <span data-ttu-id="ad2ab-109">В этом разделе перечислены операторы в порядке очередности.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-109">This topic lists the operators in precedence order.</span></span> <span data-ttu-id="ad2ab-110">Порядок очередности — это порядок, в котором PowerShell вычисляет операторы, если в одном выражении отображается несколько операторов.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-110">Precedence order is the order in which PowerShell evaluates the operators when multiple operators appear in the same expression.</span></span>

<span data-ttu-id="ad2ab-111">Если у операторов одинаковый приоритет, PowerShell вычисляет их слева направо, как они появляются в выражении.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-111">When operators have equal precedence, PowerShell evaluates them from left to right as they appear within the expression.</span></span> <span data-ttu-id="ad2ab-112">Исключениями являются операторы присваивания, операторы CAST и операторы отрицания ( `!` , `-not` , `-bnot` ), которые вычисляются справа налево.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-112">The exceptions are the assignment operators, the cast operators, and the negation operators (`!`, `-not`, `-bnot`), which are evaluated from right to left.</span></span>

<span data-ttu-id="ad2ab-113">Можно использовать вложения, например круглые скобки, для переопределения стандартного порядка приоритетов и принудительного выполнения PowerShell для вычисления вложенной части выражения перед незамкнутой частью.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-113">You can use enclosures, such as parentheses, to override the standard precedence order and force PowerShell to evaluate the enclosed part of an expression before an unenclosed part.</span></span>

<span data-ttu-id="ad2ab-114">В следующем списке Операторы перечисляются в том порядке, в котором они оцениваются.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-114">In the following list, operators are listed in the order that they are evaluated.</span></span> <span data-ttu-id="ad2ab-115">Операторы на одной строке или в одной группе имеют одинаковый приоритет.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-115">Operators on the same line, or in the same group, have equal precedence.</span></span>

<span data-ttu-id="ad2ab-116">В столбце Оператор перечислены операторы.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-116">The Operator column lists the operators.</span></span> <span data-ttu-id="ad2ab-117">Ссылочный столбец содержит раздел справки PowerShell, в котором описывается оператор.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-117">The Reference column lists the PowerShell Help topic in which the operator is described.</span></span> <span data-ttu-id="ad2ab-118">Чтобы отобразить раздел, введите `get-help <topic-name>` .</span><span class="sxs-lookup"><span data-stu-id="ad2ab-118">To display the topic, type `get-help <topic-name>`.</span></span>

|         <span data-ttu-id="ad2ab-119">OPERATOR</span><span class="sxs-lookup"><span data-stu-id="ad2ab-119">OPERATOR</span></span>         |           <span data-ttu-id="ad2ab-120">ISREFERENCE</span><span class="sxs-lookup"><span data-stu-id="ad2ab-120">REFERENCE</span></span>            |
| ------------------------ | ------------------------------ |
| `$() @() () @{}`         | <span data-ttu-id="ad2ab-121">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-121">[about_Operators][]</span></span>            |
| <span data-ttu-id="ad2ab-122">`.` (доступ к членам)</span><span class="sxs-lookup"><span data-stu-id="ad2ab-122">`.` (member access)</span></span>      | <span data-ttu-id="ad2ab-123">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-123">[about_Operators][]</span></span>            |
| <span data-ttu-id="ad2ab-124">`::` статически</span><span class="sxs-lookup"><span data-stu-id="ad2ab-124">`::` (static)</span></span>            | <span data-ttu-id="ad2ab-125">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-125">[about_Operators][]</span></span>            |
| <span data-ttu-id="ad2ab-126">`[0]` (Оператор Index)</span><span class="sxs-lookup"><span data-stu-id="ad2ab-126">`[0]` (index operator)</span></span>   | <span data-ttu-id="ad2ab-127">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-127">[about_Operators][]</span></span>            |
| <span data-ttu-id="ad2ab-128">`[int]` (операторы CAST)</span><span class="sxs-lookup"><span data-stu-id="ad2ab-128">`[int]` (cast operators)</span></span> | <span data-ttu-id="ad2ab-129">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-129">[about_Operators][]</span></span>            |
| <span data-ttu-id="ad2ab-130">`-split` унар</span><span class="sxs-lookup"><span data-stu-id="ad2ab-130">`-split` (unary)</span></span>         | <span data-ttu-id="ad2ab-131">[about_Split][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-131">[about_Split][]</span></span>                |
| <span data-ttu-id="ad2ab-132">`-join` унар</span><span class="sxs-lookup"><span data-stu-id="ad2ab-132">`-join` (unary)</span></span>          | <span data-ttu-id="ad2ab-133">[about_Join][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-133">[about_Join][]</span></span>                 |
| <span data-ttu-id="ad2ab-134">`,` (оператор запятой)</span><span class="sxs-lookup"><span data-stu-id="ad2ab-134">`,` (comma operator)</span></span>     | <span data-ttu-id="ad2ab-135">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-135">[about_Operators][]</span></span>            |
| `++ --`                  | <span data-ttu-id="ad2ab-136">[about_Assignment_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-136">[about_Assignment_Operators][]</span></span> |
| `! -not`                 | <span data-ttu-id="ad2ab-137">[about_Logical_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-137">[about_Logical_Operators][]</span></span>    |
| <span data-ttu-id="ad2ab-138">`..` (оператор Range)</span><span class="sxs-lookup"><span data-stu-id="ad2ab-138">`..` (range operator)</span></span>    | <span data-ttu-id="ad2ab-139">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-139">[about_Operators][]</span></span>            |
| <span data-ttu-id="ad2ab-140">`-f` (оператор Format)</span><span class="sxs-lookup"><span data-stu-id="ad2ab-140">`-f` (format operator)</span></span>   | <span data-ttu-id="ad2ab-141">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-141">[about_Operators][]</span></span>            |
| <span data-ttu-id="ad2ab-142">`-` (унарный/отрицательный)</span><span class="sxs-lookup"><span data-stu-id="ad2ab-142">`-` (unary/negative)</span></span>     | <span data-ttu-id="ad2ab-143">[about_Arithmetic_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-143">[about_Arithmetic_Operators][]</span></span> |
| `* / %`                  | <span data-ttu-id="ad2ab-144">[about_Arithmetic_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-144">[about_Arithmetic_Operators][]</span></span> |
| `+ -`                    | <span data-ttu-id="ad2ab-145">[about_Arithmetic_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-145">[about_Arithmetic_Operators][]</span></span> |

<span data-ttu-id="ad2ab-146">Следующая группа операторов имеет одинаковый приоритет.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-146">The following group of operators have equal precedence.</span></span> <span data-ttu-id="ad2ab-147">С учетом регистра и без учета регистра одни и те же варианты имеют одинаковый приоритет.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-147">Their case-sensitive and explicitly case-insensitive variants have the same precedence.</span></span>

|         <span data-ttu-id="ad2ab-148">OPERATOR</span><span class="sxs-lookup"><span data-stu-id="ad2ab-148">OPERATOR</span></span>          |           <span data-ttu-id="ad2ab-149">ISREFERENCE</span><span class="sxs-lookup"><span data-stu-id="ad2ab-149">REFERENCE</span></span>            |
| ------------------------- | ------------------------------ |
| <span data-ttu-id="ad2ab-150">`-split` двоичный</span><span class="sxs-lookup"><span data-stu-id="ad2ab-150">`-split` (binary)</span></span>         | <span data-ttu-id="ad2ab-151">[about_Split][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-151">[about_Split][]</span></span>                |
| <span data-ttu-id="ad2ab-152">`-join` двоичный</span><span class="sxs-lookup"><span data-stu-id="ad2ab-152">`-join` (binary)</span></span>          | <span data-ttu-id="ad2ab-153">[about_Join][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-153">[about_Join][]</span></span>                 |
| `-is -isnot -as`          | <span data-ttu-id="ad2ab-154">[about_Type_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-154">[about_Type_Operators][]</span></span>       |
| `-eq -ne -gt -gt -lt -le` | <span data-ttu-id="ad2ab-155">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-155">[about_Comparison_Operators][]</span></span> |
| `-like -notlike`          | <span data-ttu-id="ad2ab-156">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-156">[about_Comparison_Operators][]</span></span> |
| `-match -notmatch`        | <span data-ttu-id="ad2ab-157">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-157">[about_Comparison_Operators][]</span></span> |
| `-in -notIn`              | <span data-ttu-id="ad2ab-158">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-158">[about_Comparison_Operators][]</span></span> |
| `-contains -notContains`  | <span data-ttu-id="ad2ab-159">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-159">[about_Comparison_Operators][]</span></span> |
| `-replace`                | <span data-ttu-id="ad2ab-160">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-160">[about_Comparison_Operators][]</span></span> |

<span data-ttu-id="ad2ab-161">Список возобновляется с помощью следующих операторов в порядке очередности:</span><span class="sxs-lookup"><span data-stu-id="ad2ab-161">The list resumes here with the following operators in precedence order:</span></span>

|                <span data-ttu-id="ad2ab-162">OPERATOR</span><span class="sxs-lookup"><span data-stu-id="ad2ab-162">OPERATOR</span></span>                 |           <span data-ttu-id="ad2ab-163">ISREFERENCE</span><span class="sxs-lookup"><span data-stu-id="ad2ab-163">REFERENCE</span></span>            |
| --------------------------------------- | ------------------------------ |
| `-band -bnot -bor -bxor -shr -shl`      | <span data-ttu-id="ad2ab-164">[about_Arithmetic_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-164">[about_Arithmetic_Operators][]</span></span> |
| `-and -or -xor`                         | <span data-ttu-id="ad2ab-165">[about_Logical_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-165">[about_Logical_Operators][]</span></span>    |

<span data-ttu-id="ad2ab-166">Следующие элементы не являются истинными операторами.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-166">The following items are not true operators.</span></span> <span data-ttu-id="ad2ab-167">Они являются частью синтаксиса команд PowerShell, а не синтаксиса выражений.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-167">They are part of PowerShell's command syntax, not expression syntax.</span></span> <span data-ttu-id="ad2ab-168">Назначение всегда является последним выполняемым действием.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-168">Assignment is always the last action that happens.</span></span>

|                <span data-ttu-id="ad2ab-169">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ad2ab-169">SYNTAX</span></span>                   |           <span data-ttu-id="ad2ab-170">ISREFERENCE</span><span class="sxs-lookup"><span data-stu-id="ad2ab-170">REFERENCE</span></span>            |
| --------------------------------------- | ------------------------------ |
| <span data-ttu-id="ad2ab-171">`.` (точка-источник)</span><span class="sxs-lookup"><span data-stu-id="ad2ab-171">`.` (dot-source)</span></span>                        | <span data-ttu-id="ad2ab-172">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-172">[about_Operators][]</span></span>            |
| <span data-ttu-id="ad2ab-173">`&` обращение</span><span class="sxs-lookup"><span data-stu-id="ad2ab-173">`&` (call)</span></span>                              | <span data-ttu-id="ad2ab-174">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-174">[about_Operators][]</span></span>            |
| <span data-ttu-id="ad2ab-175"><code>&#124;</code> (оператор конвейера)</span><span class="sxs-lookup"><span data-stu-id="ad2ab-175"><code>&#124;</code> (pipeline operator)</span></span> | <span data-ttu-id="ad2ab-176">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-176">[about_Operators][]</span></span>            |
| `> >> 2> 2>> 2>&1`                      | <span data-ttu-id="ad2ab-177">[about_Redirection][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-177">[about_Redirection][]</span></span>          |
| `= += -= *= /= %=`                      | <span data-ttu-id="ad2ab-178">[about_Assignment_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-178">[about_Assignment_Operators][]</span></span> |

## <a name="examples"></a><span data-ttu-id="ad2ab-179">Примеры</span><span class="sxs-lookup"><span data-stu-id="ad2ab-179">EXAMPLES</span></span>

<span data-ttu-id="ad2ab-180">Следующие две команды показывают арифметические операторы и результат использования круглых скобок для принудительного вычисления в PowerShell заключенной в нем части выражения.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-180">The following two commands show the arithmetic operators and the effect of using parentheses to force PowerShell to evaluate the enclosed part of the expression first.</span></span>

```powershell
PS> 2 + 3 * 4
14

PS> (2 + 3) * 4
20
```

<span data-ttu-id="ad2ab-181">В следующем примере выполняется получение текстовых файлов только для чтения из локального каталога и их сохранение в `$read_only` переменной.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-181">The following example gets the read-only text files from the local directory and saves them in the `$read_only` variable.</span></span>

```powershell
$read_only = Get-ChildItem *.txt | Where-Object {$_.isReadOnly}
```

<span data-ttu-id="ad2ab-182">Это эквивалентно следующему примеру.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-182">It is equivalent to the following example.</span></span>

```powershell
$read_only = ( Get-ChildItem *.txt | Where-Object {$_.isReadOnly} )
```

<span data-ttu-id="ad2ab-183">Так как оператор конвейера ( `|` ) имеет более высокий приоритет, чем оператор присваивания ( `=` ), файлы, получаемые `Get-ChildItem` командлетом, отправляются в `Where-Object` командлет для фильтрации до того, как они будут назначены `$read_only` переменной.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-183">Because the pipeline operator (`|`) has a higher precedence than the assignment operator (`=`), the files that the `Get-ChildItem` cmdlet gets are sent to the `Where-Object` cmdlet for filtering before they are assigned to the `$read_only` variable.</span></span>

<span data-ttu-id="ad2ab-184">В следующем примере показано, что оператор index имеет приоритет над оператором Cast.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-184">The following example demonstrates that the index operator takes precedence over the cast operator.</span></span>

<span data-ttu-id="ad2ab-185">Это выражение создает массив из трех строк.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-185">This expression creates an array of three strings.</span></span> <span data-ttu-id="ad2ab-186">Затем он использует оператор index со значением 0 для выбора первого объекта в массиве, который является первой строкой.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-186">Then, it uses the index operator with a value of 0 to select the first object in the array, which is the first string.</span></span> <span data-ttu-id="ad2ab-187">Наконец, выбранный объект приводится в виде строки.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-187">Finally, it casts the selected object as a string.</span></span> <span data-ttu-id="ad2ab-188">В этом случае приведение не оказывает никакого влияния.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-188">In this case, the cast has no effect.</span></span>

```powershell
PS> [string]@('Windows','PowerShell','2.0')[0]
Windows
```

<span data-ttu-id="ad2ab-189">Это выражение использует круглые скобки, чтобы принудительно выполнить операцию приведения перед выбором индекса.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-189">This expression uses parentheses to force the cast operation to occur before the index selection.</span></span> <span data-ttu-id="ad2ab-190">В результате весь массив приводится к строковому типу (Single).</span><span class="sxs-lookup"><span data-stu-id="ad2ab-190">As a result, the entire array is cast as a (single) string.</span></span> <span data-ttu-id="ad2ab-191">Затем оператор index выбирает первый элемент в массиве строк, который является первым символом.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-191">Then, the index operator selects the first item in the string array, which is the first character.</span></span>

```powershell
PS> ([string]@('Windows','PowerShell','2.0'))[0]
W
```

<span data-ttu-id="ad2ab-192">В следующем примере, поскольку оператор « `-gt` больше чем» имеет более высокий приоритет, чем `-and` оператор (логический и), результатом выражения будет false.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-192">In the following example, because the `-gt` (greater-than) operator has a higher precedence than the `-and` (logical AND) operator, the result of the expression is FALSE.</span></span>

```powershell
PS> 2 -gt 4 -and 1
False
```

<span data-ttu-id="ad2ab-193">Он эквивалентен следующему выражению.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-193">It is equivalent to the following expression.</span></span>

```powershell
PS> (2 -gt 4) -and 1
False
```

<span data-ttu-id="ad2ab-194">Если оператор-and имеет более высокий приоритет, ответ будет равен TRUE.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-194">If the -and operator had higher precedence, the answer would be TRUE.</span></span>

```powershell
PS> 2 -gt (4 -and 1)
True
```

<span data-ttu-id="ad2ab-195">Однако в этом примере демонстрируется важный принцип управления приоритетом операторов.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-195">However, this example demonstrates an important principle of managing operator precedence.</span></span> <span data-ttu-id="ad2ab-196">Если выражение трудно интерпретировать, используйте круглые скобки, чтобы принудительно применить порядок вычисления, даже если он вызывает приоритет оператора по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-196">When an expression is difficult for people to interpret, use parentheses to force the evaluation order, even when it forces the default operator precedence.</span></span> <span data-ttu-id="ad2ab-197">Круглые скобки делают ваши намерения понятными для тех, кто читает и обслуживает ваши сценарии.</span><span class="sxs-lookup"><span data-stu-id="ad2ab-197">The parentheses make your intentions clear to people who are reading and maintaining your scripts.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad2ab-198">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="ad2ab-198">SEE ALSO</span></span>

<span data-ttu-id="ad2ab-199">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-199">[about_Operators][]</span></span>

<span data-ttu-id="ad2ab-200">[about_Assignment_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-200">[about_Assignment_Operators][]</span></span>

<span data-ttu-id="ad2ab-201">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-201">[about_Comparison_Operators][]</span></span>

<span data-ttu-id="ad2ab-202">[about_Arithmetic_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-202">[about_Arithmetic_Operators][]</span></span>

<span data-ttu-id="ad2ab-203">[about_Join][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-203">[about_Join][]</span></span>

<span data-ttu-id="ad2ab-204">[about_Redirection][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-204">[about_Redirection][]</span></span>

<span data-ttu-id="ad2ab-205">[about_Scopes][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-205">[about_Scopes][]</span></span>

<span data-ttu-id="ad2ab-206">[about_Split][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-206">[about_Split][]</span></span>

<span data-ttu-id="ad2ab-207">[about_Type_Operators][]</span><span class="sxs-lookup"><span data-stu-id="ad2ab-207">[about_Type_Operators][]</span></span>

<!-- reference links -->
[about_Arithmetic_Operators]: about_Arithmetic_Operators.md
[about_Assignment_Operators]: about_Assignment_Operators.md
[about_Comparison_Operators]: about_Comparison_Operators.md
[about_Join]: about_Join.md
[about_Logical_Operators]: about_logical_operators.md
[about_Operators]: about_Operators.md
[about_Redirection]: about_Redirection.md
[about_Scopes]: about_Scopes.md
[about_Split]: about_Split.md
[about_Type_Operators]: about_Type_Operators.md
