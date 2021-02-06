---
description: Перечисляет операторы PowerShell в порядке очередности.
Locale: en-US
ms.date: 11/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_operator_precedence?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Operator_Precedence
ms.openlocfilehash: d4031a9d9a67340470d5418a9c2d3e33c5caed13
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600685"
---
# <a name="about-operator-precedence"></a><span data-ttu-id="3709e-103">О приоритете операторов</span><span class="sxs-lookup"><span data-stu-id="3709e-103">About Operator Precedence</span></span>

## <a name="short-description"></a><span data-ttu-id="3709e-104">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="3709e-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="3709e-105">Перечисляет операторы PowerShell в порядке очередности.</span><span class="sxs-lookup"><span data-stu-id="3709e-105">Lists the PowerShell operators in precedence order.</span></span>

## <a name="long-description"></a><span data-ttu-id="3709e-106">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="3709e-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="3709e-107">Операторы PowerShell позволяют создавать простые, но мощные выражения.</span><span class="sxs-lookup"><span data-stu-id="3709e-107">PowerShell operators let you construct simple, but powerful expressions.</span></span> <span data-ttu-id="3709e-108">В этом разделе перечислены операторы в порядке очередности.</span><span class="sxs-lookup"><span data-stu-id="3709e-108">This topic lists the operators in precedence order.</span></span> <span data-ttu-id="3709e-109">Порядок очередности — это порядок, в котором PowerShell вычисляет операторы, если в одном выражении отображается несколько операторов.</span><span class="sxs-lookup"><span data-stu-id="3709e-109">Precedence order is the order in which PowerShell evaluates the operators when multiple operators appear in the same expression.</span></span>

<span data-ttu-id="3709e-110">Если у операторов одинаковый приоритет, PowerShell вычисляет их слева направо, как они появляются в выражении.</span><span class="sxs-lookup"><span data-stu-id="3709e-110">When operators have equal precedence, PowerShell evaluates them from left to right as they appear within the expression.</span></span> <span data-ttu-id="3709e-111">Исключениями являются операторы присваивания, операторы CAST и операторы отрицания ( `!` , `-not` , `-bnot` ), которые вычисляются справа налево.</span><span class="sxs-lookup"><span data-stu-id="3709e-111">The exceptions are the assignment operators, the cast operators, and the negation operators (`!`, `-not`, `-bnot`), which are evaluated from right to left.</span></span>

<span data-ttu-id="3709e-112">Можно использовать вложения, например круглые скобки, для переопределения стандартного порядка приоритетов и принудительного выполнения PowerShell для вычисления вложенной части выражения перед незамкнутой частью.</span><span class="sxs-lookup"><span data-stu-id="3709e-112">You can use enclosures, such as parentheses, to override the standard precedence order and force PowerShell to evaluate the enclosed part of an expression before an unenclosed part.</span></span>

<span data-ttu-id="3709e-113">В следующем списке Операторы перечисляются в том порядке, в котором они оцениваются.</span><span class="sxs-lookup"><span data-stu-id="3709e-113">In the following list, operators are listed in the order that they are evaluated.</span></span> <span data-ttu-id="3709e-114">Операторы на одной строке или в одной группе имеют одинаковый приоритет.</span><span class="sxs-lookup"><span data-stu-id="3709e-114">Operators on the same line, or in the same group, have equal precedence.</span></span>

<span data-ttu-id="3709e-115">В столбце Оператор перечислены операторы.</span><span class="sxs-lookup"><span data-stu-id="3709e-115">The Operator column lists the operators.</span></span> <span data-ttu-id="3709e-116">Ссылочный столбец содержит раздел справки PowerShell, в котором описывается оператор.</span><span class="sxs-lookup"><span data-stu-id="3709e-116">The Reference column lists the PowerShell Help topic in which the operator is described.</span></span> <span data-ttu-id="3709e-117">Чтобы отобразить раздел, введите `get-help <topic-name>` .</span><span class="sxs-lookup"><span data-stu-id="3709e-117">To display the topic, type `get-help <topic-name>`.</span></span>

|         <span data-ttu-id="3709e-118">OPERATOR</span><span class="sxs-lookup"><span data-stu-id="3709e-118">OPERATOR</span></span>         |           <span data-ttu-id="3709e-119">ISREFERENCE</span><span class="sxs-lookup"><span data-stu-id="3709e-119">REFERENCE</span></span>            |
| ------------------------ | ------------------------------ |
| `$() @() () @{}`         | <span data-ttu-id="3709e-120">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-120">[about_Operators][]</span></span>            |
| <span data-ttu-id="3709e-121">`. ?.` (доступ к членам)</span><span class="sxs-lookup"><span data-stu-id="3709e-121">`. ?.` (member access)</span></span>   | <span data-ttu-id="3709e-122">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-122">[about_Operators][]</span></span>            |
| <span data-ttu-id="3709e-123">`::` статически</span><span class="sxs-lookup"><span data-stu-id="3709e-123">`::` (static)</span></span>            | <span data-ttu-id="3709e-124">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-124">[about_Operators][]</span></span>            |
| <span data-ttu-id="3709e-125">`[0] ?[0]` (Оператор Index)</span><span class="sxs-lookup"><span data-stu-id="3709e-125">`[0] ?[0]` (index operator)</span></span> | <span data-ttu-id="3709e-126">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-126">[about_Operators][]</span></span>         |
| <span data-ttu-id="3709e-127">`[int]` (операторы CAST)</span><span class="sxs-lookup"><span data-stu-id="3709e-127">`[int]` (cast operators)</span></span> | <span data-ttu-id="3709e-128">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-128">[about_Operators][]</span></span>            |
| <span data-ttu-id="3709e-129">`-split` унар</span><span class="sxs-lookup"><span data-stu-id="3709e-129">`-split` (unary)</span></span>         | <span data-ttu-id="3709e-130">[about_Split][]</span><span class="sxs-lookup"><span data-stu-id="3709e-130">[about_Split][]</span></span>                |
| <span data-ttu-id="3709e-131">`-join` унар</span><span class="sxs-lookup"><span data-stu-id="3709e-131">`-join` (unary)</span></span>          | <span data-ttu-id="3709e-132">[about_Join][]</span><span class="sxs-lookup"><span data-stu-id="3709e-132">[about_Join][]</span></span>                 |
| <span data-ttu-id="3709e-133">`,` (оператор запятой)</span><span class="sxs-lookup"><span data-stu-id="3709e-133">`,` (comma operator)</span></span>     | <span data-ttu-id="3709e-134">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-134">[about_Operators][]</span></span>            |
| `++ --`                  | <span data-ttu-id="3709e-135">[about_Assignment_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-135">[about_Assignment_Operators][]</span></span> |
| `! -not`                 | <span data-ttu-id="3709e-136">[about_Logical_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-136">[about_Logical_Operators][]</span></span>    |
| <span data-ttu-id="3709e-137">`..` (оператор Range)</span><span class="sxs-lookup"><span data-stu-id="3709e-137">`..` (range operator)</span></span>    | <span data-ttu-id="3709e-138">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-138">[about_Operators][]</span></span>            |
| <span data-ttu-id="3709e-139">`-f` (оператор Format)</span><span class="sxs-lookup"><span data-stu-id="3709e-139">`-f` (format operator)</span></span>   | <span data-ttu-id="3709e-140">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-140">[about_Operators][]</span></span>            |
| <span data-ttu-id="3709e-141">`-` (унарный/отрицательный)</span><span class="sxs-lookup"><span data-stu-id="3709e-141">`-` (unary/negative)</span></span>     | <span data-ttu-id="3709e-142">[about_Arithmetic_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-142">[about_Arithmetic_Operators][]</span></span> |
| `* / %`                  | <span data-ttu-id="3709e-143">[about_Arithmetic_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-143">[about_Arithmetic_Operators][]</span></span> |
| `+ -`                    | <span data-ttu-id="3709e-144">[about_Arithmetic_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-144">[about_Arithmetic_Operators][]</span></span> |

<span data-ttu-id="3709e-145">Следующая группа операторов имеет одинаковый приоритет.</span><span class="sxs-lookup"><span data-stu-id="3709e-145">The following group of operators have equal precedence.</span></span> <span data-ttu-id="3709e-146">С учетом регистра и без учета регистра одни и те же варианты имеют одинаковый приоритет.</span><span class="sxs-lookup"><span data-stu-id="3709e-146">Their case-sensitive and explicitly case-insensitive variants have the same precedence.</span></span>

|         <span data-ttu-id="3709e-147">OPERATOR</span><span class="sxs-lookup"><span data-stu-id="3709e-147">OPERATOR</span></span>          |           <span data-ttu-id="3709e-148">ISREFERENCE</span><span class="sxs-lookup"><span data-stu-id="3709e-148">REFERENCE</span></span>            |
| ------------------------- | ------------------------------ |
| <span data-ttu-id="3709e-149">`-split` двоичный</span><span class="sxs-lookup"><span data-stu-id="3709e-149">`-split` (binary)</span></span>         | <span data-ttu-id="3709e-150">[about_Split][]</span><span class="sxs-lookup"><span data-stu-id="3709e-150">[about_Split][]</span></span>                |
| <span data-ttu-id="3709e-151">`-join` двоичный</span><span class="sxs-lookup"><span data-stu-id="3709e-151">`-join` (binary)</span></span>          | <span data-ttu-id="3709e-152">[about_Join][]</span><span class="sxs-lookup"><span data-stu-id="3709e-152">[about_Join][]</span></span>                 |
| `-is -isnot -as`          | <span data-ttu-id="3709e-153">[about_Type_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-153">[about_Type_Operators][]</span></span>       |
| `-eq -ne -gt -gt -lt -le` | <span data-ttu-id="3709e-154">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-154">[about_Comparison_Operators][]</span></span> |
| `-like -notlike`          | <span data-ttu-id="3709e-155">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-155">[about_Comparison_Operators][]</span></span> |
| `-match -notmatch`        | <span data-ttu-id="3709e-156">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-156">[about_Comparison_Operators][]</span></span> |
| `-in -notIn`              | <span data-ttu-id="3709e-157">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-157">[about_Comparison_Operators][]</span></span> |
| `-contains -notContains`  | <span data-ttu-id="3709e-158">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-158">[about_Comparison_Operators][]</span></span> |
| `-replace`                | <span data-ttu-id="3709e-159">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-159">[about_Comparison_Operators][]</span></span> |

<span data-ttu-id="3709e-160">Список возобновляется с помощью следующих операторов в порядке очередности:</span><span class="sxs-lookup"><span data-stu-id="3709e-160">The list resumes here with the following operators in precedence order:</span></span>

|                <span data-ttu-id="3709e-161">OPERATOR</span><span class="sxs-lookup"><span data-stu-id="3709e-161">OPERATOR</span></span>                 |           <span data-ttu-id="3709e-162">ISREFERENCE</span><span class="sxs-lookup"><span data-stu-id="3709e-162">REFERENCE</span></span>            |
| --------------------------------------- | ------------------------------ |
| `-band -bnot -bor -bxor -shr -shl`      | <span data-ttu-id="3709e-163">[about_Arithmetic_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-163">[about_Arithmetic_Operators][]</span></span> |
| `-and -or -xor`                         | <span data-ttu-id="3709e-164">[about_Logical_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-164">[about_Logical_Operators][]</span></span>    |

<span data-ttu-id="3709e-165">Следующие элементы не являются истинными операторами.</span><span class="sxs-lookup"><span data-stu-id="3709e-165">The following items are not true operators.</span></span> <span data-ttu-id="3709e-166">Они являются частью синтаксиса команд PowerShell, а не синтаксиса выражений.</span><span class="sxs-lookup"><span data-stu-id="3709e-166">They are part of PowerShell's command syntax, not expression syntax.</span></span> <span data-ttu-id="3709e-167">Назначение всегда является последним выполняемым действием.</span><span class="sxs-lookup"><span data-stu-id="3709e-167">Assignment is always the last action that happens.</span></span>

|                <span data-ttu-id="3709e-168">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3709e-168">SYNTAX</span></span>                   |           <span data-ttu-id="3709e-169">ISREFERENCE</span><span class="sxs-lookup"><span data-stu-id="3709e-169">REFERENCE</span></span>            |
| --------------------------------------- | ------------------------------ |
| <span data-ttu-id="3709e-170">`.` (точка-источник)</span><span class="sxs-lookup"><span data-stu-id="3709e-170">`.` (dot-source)</span></span>                        | <span data-ttu-id="3709e-171">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-171">[about_Operators][]</span></span>            |
| <span data-ttu-id="3709e-172">`&` обращение</span><span class="sxs-lookup"><span data-stu-id="3709e-172">`&` (call)</span></span>                              | <span data-ttu-id="3709e-173">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-173">[about_Operators][]</span></span>            |
| <span data-ttu-id="3709e-174">`? <if-true> : <if-false>` (Оператор Ternary)</span><span class="sxs-lookup"><span data-stu-id="3709e-174">`? <if-true> : <if-false>` (Ternary operator)</span></span> | <span data-ttu-id="3709e-175">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-175">[about_Operators][]</span></span>      |
| <span data-ttu-id="3709e-176">`??` (оператор, сокрывающийся со значением NULL)</span><span class="sxs-lookup"><span data-stu-id="3709e-176">`??` (null-coalese operator)</span></span>            | <span data-ttu-id="3709e-177">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-177">[about_Operators][]</span></span>            |
| <span data-ttu-id="3709e-178"><code>&#124;</code> (оператор конвейера)</span><span class="sxs-lookup"><span data-stu-id="3709e-178"><code>&#124;</code> (pipeline operator)</span></span> | <span data-ttu-id="3709e-179">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-179">[about_Operators][]</span></span>            |
| `> >> 2> 2>> 2>&1`                      | <span data-ttu-id="3709e-180">[about_Redirection][]</span><span class="sxs-lookup"><span data-stu-id="3709e-180">[about_Redirection][]</span></span>          |
| <span data-ttu-id="3709e-181"><code>&& &#124;&#124;</code> (операторы цепочки конвейеров)</span><span class="sxs-lookup"><span data-stu-id="3709e-181"><code>&& &#124;&#124;</code> (pipeline chain operators)</span></span> | <span data-ttu-id="3709e-182">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-182">[about_Operators][]</span></span> |
| `= += -= *= /= %= ??=`                  | <span data-ttu-id="3709e-183">[about_Assignment_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-183">[about_Assignment_Operators][]</span></span> |

## <a name="examples"></a><span data-ttu-id="3709e-184">Примеры</span><span class="sxs-lookup"><span data-stu-id="3709e-184">EXAMPLES</span></span>

<span data-ttu-id="3709e-185">Следующие две команды показывают арифметические операторы и результат использования круглых скобок для принудительного вычисления в PowerShell заключенной в нем части выражения.</span><span class="sxs-lookup"><span data-stu-id="3709e-185">The following two commands show the arithmetic operators and the effect of using parentheses to force PowerShell to evaluate the enclosed part of the expression first.</span></span>

```powershell
PS> 2 + 3 * 4
14

PS> (2 + 3) * 4
20
```

<span data-ttu-id="3709e-186">В следующем примере выполняется получение текстовых файлов только для чтения из локального каталога и их сохранение в `$read_only` переменной.</span><span class="sxs-lookup"><span data-stu-id="3709e-186">The following example gets the read-only text files from the local directory and saves them in the `$read_only` variable.</span></span>

```powershell
$read_only = Get-ChildItem *.txt | Where-Object {$_.isReadOnly}
```

<span data-ttu-id="3709e-187">Это эквивалентно следующему примеру.</span><span class="sxs-lookup"><span data-stu-id="3709e-187">It is equivalent to the following example.</span></span>

```powershell
$read_only = ( Get-ChildItem *.txt | Where-Object {$_.isReadOnly} )
```

<span data-ttu-id="3709e-188">Так как оператор конвейера ( `|` ) имеет более высокий приоритет, чем оператор присваивания ( `=` ), файлы, получаемые `Get-ChildItem` командлетом, отправляются в `Where-Object` командлет для фильтрации до того, как они будут назначены `$read_only` переменной.</span><span class="sxs-lookup"><span data-stu-id="3709e-188">Because the pipeline operator (`|`) has a higher precedence than the assignment operator (`=`), the files that the `Get-ChildItem` cmdlet gets are sent to the `Where-Object` cmdlet for filtering before they are assigned to the `$read_only` variable.</span></span>

<span data-ttu-id="3709e-189">В следующем примере показано, что оператор index имеет приоритет над оператором Cast.</span><span class="sxs-lookup"><span data-stu-id="3709e-189">The following example demonstrates that the index operator takes precedence over the cast operator.</span></span>

<span data-ttu-id="3709e-190">Это выражение создает массив из трех строк.</span><span class="sxs-lookup"><span data-stu-id="3709e-190">This expression creates an array of three strings.</span></span> <span data-ttu-id="3709e-191">Затем он использует оператор index со значением 0 для выбора первого объекта в массиве, который является первой строкой.</span><span class="sxs-lookup"><span data-stu-id="3709e-191">Then, it uses the index operator with a value of 0 to select the first object in the array, which is the first string.</span></span> <span data-ttu-id="3709e-192">Наконец, выбранный объект приводится в виде строки.</span><span class="sxs-lookup"><span data-stu-id="3709e-192">Finally, it casts the selected object as a string.</span></span> <span data-ttu-id="3709e-193">В этом случае приведение не оказывает никакого влияния.</span><span class="sxs-lookup"><span data-stu-id="3709e-193">In this case, the cast has no effect.</span></span>

```powershell
PS> [string]@('Windows','PowerShell','2.0')[0]
Windows
```

<span data-ttu-id="3709e-194">Это выражение использует круглые скобки, чтобы принудительно выполнить операцию приведения перед выбором индекса.</span><span class="sxs-lookup"><span data-stu-id="3709e-194">This expression uses parentheses to force the cast operation to occur before the index selection.</span></span> <span data-ttu-id="3709e-195">В результате весь массив приводится к строковому типу (Single).</span><span class="sxs-lookup"><span data-stu-id="3709e-195">As a result, the entire array is cast as a (single) string.</span></span> <span data-ttu-id="3709e-196">Затем оператор index выбирает первый элемент в массиве строк, который является первым символом.</span><span class="sxs-lookup"><span data-stu-id="3709e-196">Then, the index operator selects the first item in the string array, which is the first character.</span></span>

```powershell
PS> ([string]@('Windows','PowerShell','2.0'))[0]
W
```

<span data-ttu-id="3709e-197">В следующем примере, поскольку оператор « `-gt` больше чем» имеет более высокий приоритет, чем `-and` оператор (логический и), результатом выражения будет false.</span><span class="sxs-lookup"><span data-stu-id="3709e-197">In the following example, because the `-gt` (greater-than) operator has a higher precedence than the `-and` (logical AND) operator, the result of the expression is FALSE.</span></span>

```powershell
PS> 2 -gt 4 -and 1
False
```

<span data-ttu-id="3709e-198">Он эквивалентен следующему выражению.</span><span class="sxs-lookup"><span data-stu-id="3709e-198">It is equivalent to the following expression.</span></span>

```powershell
PS> (2 -gt 4) -and 1
False
```

<span data-ttu-id="3709e-199">Если оператор-and имеет более высокий приоритет, ответ будет равен TRUE.</span><span class="sxs-lookup"><span data-stu-id="3709e-199">If the -and operator had higher precedence, the answer would be TRUE.</span></span>

```powershell
PS> 2 -gt (4 -and 1)
True
```

<span data-ttu-id="3709e-200">Однако в этом примере демонстрируется важный принцип управления приоритетом операторов.</span><span class="sxs-lookup"><span data-stu-id="3709e-200">However, this example demonstrates an important principle of managing operator precedence.</span></span> <span data-ttu-id="3709e-201">Если выражение трудно интерпретировать, используйте круглые скобки, чтобы принудительно применить порядок вычисления, даже если он вызывает приоритет оператора по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3709e-201">When an expression is difficult for people to interpret, use parentheses to force the evaluation order, even when it forces the default operator precedence.</span></span> <span data-ttu-id="3709e-202">Круглые скобки делают ваши намерения понятными для тех, кто читает и обслуживает ваши сценарии.</span><span class="sxs-lookup"><span data-stu-id="3709e-202">The parentheses make your intentions clear to people who are reading and maintaining your scripts.</span></span>

## <a name="see-also"></a><span data-ttu-id="3709e-203">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="3709e-203">SEE ALSO</span></span>

<span data-ttu-id="3709e-204">[about_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-204">[about_Operators][]</span></span>

<span data-ttu-id="3709e-205">[about_Assignment_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-205">[about_Assignment_Operators][]</span></span>

<span data-ttu-id="3709e-206">[about_Comparison_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-206">[about_Comparison_Operators][]</span></span>

<span data-ttu-id="3709e-207">[about_Arithmetic_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-207">[about_Arithmetic_Operators][]</span></span>

<span data-ttu-id="3709e-208">[about_Join][]</span><span class="sxs-lookup"><span data-stu-id="3709e-208">[about_Join][]</span></span>

<span data-ttu-id="3709e-209">[about_Redirection][]</span><span class="sxs-lookup"><span data-stu-id="3709e-209">[about_Redirection][]</span></span>

<span data-ttu-id="3709e-210">[about_Scopes][]</span><span class="sxs-lookup"><span data-stu-id="3709e-210">[about_Scopes][]</span></span>

<span data-ttu-id="3709e-211">[about_Split][]</span><span class="sxs-lookup"><span data-stu-id="3709e-211">[about_Split][]</span></span>

<span data-ttu-id="3709e-212">[about_Type_Operators][]</span><span class="sxs-lookup"><span data-stu-id="3709e-212">[about_Type_Operators][]</span></span>

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
