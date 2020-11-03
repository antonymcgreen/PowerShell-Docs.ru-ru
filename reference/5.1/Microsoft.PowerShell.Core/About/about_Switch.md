---
description: Объясняет, как использовать параметр для выполнения нескольких `If` инструкций.
keywords: powershell,командлет
Locale: en-US
ms.date: 05/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_switch?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Switch
ms.openlocfilehash: 1cb0e95aa942af4aa29f449da0c7cbbaf15d7dc5
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231910"
---
# <a name="about-switch"></a><span data-ttu-id="d2781-104">О параметре</span><span class="sxs-lookup"><span data-stu-id="d2781-104">About Switch</span></span>

## <a name="short-description"></a><span data-ttu-id="d2781-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="d2781-105">Short description</span></span>
<span data-ttu-id="d2781-106">Объясняет, как использовать параметр для выполнения нескольких `If` инструкций.</span><span class="sxs-lookup"><span data-stu-id="d2781-106">Explains how to use a switch to handle multiple `If` statements.</span></span>

## <a name="long-description"></a><span data-ttu-id="d2781-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="d2781-107">Long description</span></span>

<span data-ttu-id="d2781-108">Чтобы проверить условие в скрипте или функции, используйте `If` инструкцию.</span><span class="sxs-lookup"><span data-stu-id="d2781-108">To check a condition in a script or function, use an `If` statement.</span></span> <span data-ttu-id="d2781-109">`If`Инструкция может проверять различные типы условий, в том числе значения переменных и свойства объектов.</span><span class="sxs-lookup"><span data-stu-id="d2781-109">The `If` statement can check many types of conditions, including the value of variables and the properties of objects.</span></span>

<span data-ttu-id="d2781-110">Чтобы проверить несколько условий, используйте `Switch` оператор.</span><span class="sxs-lookup"><span data-stu-id="d2781-110">To check multiple conditions, use a `Switch` statement.</span></span> <span data-ttu-id="d2781-111">`Switch`Оператор эквивалентен ряду `If` операторов, но проще.</span><span class="sxs-lookup"><span data-stu-id="d2781-111">The `Switch` statement is equivalent to a series of `If` statements, but it is simpler.</span></span> <span data-ttu-id="d2781-112">`Switch`Инструкция перечисляет все условия и необязательное действие.</span><span class="sxs-lookup"><span data-stu-id="d2781-112">The `Switch` statement lists each condition and an optional action.</span></span> <span data-ttu-id="d2781-113">Если условие получает значение, выполняется действие.</span><span class="sxs-lookup"><span data-stu-id="d2781-113">If a condition obtains, the action is performed.</span></span>

<span data-ttu-id="d2781-114">`Switch`Инструкция может использовать `$_` `$switch` переменные и автоматически.</span><span class="sxs-lookup"><span data-stu-id="d2781-114">The `Switch` statement can use the `$_` and `$switch` automatic variables.</span></span> <span data-ttu-id="d2781-115">Дополнительные сведения см. в разделе [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="d2781-115">For more information, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

<span data-ttu-id="d2781-116">Базовый `Switch` оператор имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="d2781-116">A basic `Switch` statement has the following format:</span></span>

```powershell
Switch (<test-value>)
{
    <condition> {<action>}
    <condition> {<action>}
}
```

<span data-ttu-id="d2781-117">Например, следующая `Switch` инструкция сравнивает тестовое значение, 3, с каждым из условий.</span><span class="sxs-lookup"><span data-stu-id="d2781-117">For example, the following `Switch` statement compares the test value, 3, to each of the conditions.</span></span> <span data-ttu-id="d2781-118">Когда тестовое значение соответствует условию, выполняется действие.</span><span class="sxs-lookup"><span data-stu-id="d2781-118">When the test value matches the condition, the action is performed.</span></span>

```powershell
switch (3)
{
    1 {"It is one."}
    2 {"It is two."}
    3 {"It is three."}
    4 {"It is four."}
}
```

```Output
It is three.
```

<span data-ttu-id="d2781-119">В этом простом примере значение сравнивается с каждым условием в списке, несмотря на совпадение со значением 3.</span><span class="sxs-lookup"><span data-stu-id="d2781-119">In this simple example, the value is compared to each condition in the list, even though there is a match for the value 3.</span></span> <span data-ttu-id="d2781-120">Следующая `Switch` инструкция имеет два условия для значения 3.</span><span class="sxs-lookup"><span data-stu-id="d2781-120">The following `Switch` statement has two conditions for a value of 3.</span></span> <span data-ttu-id="d2781-121">В нем показано, что по умолчанию проверяются все условия.</span><span class="sxs-lookup"><span data-stu-id="d2781-121">It demonstrates that, by default, all conditions are tested.</span></span>

```powershell
switch (3)
{
    1 {"It is one."}
    2 {"It is two."}
    3 {"It is three."}
    4 {"It is four."}
    3 {"Three again."}
}
```

```Output
It is three.
Three again.
```

<span data-ttu-id="d2781-122">Чтобы перенаправление `Switch` для отмены сравнения после совпадения, используйте `Break` инструкцию.</span><span class="sxs-lookup"><span data-stu-id="d2781-122">To direct the `Switch` to stop comparing after a match, use the `Break` statement.</span></span> <span data-ttu-id="d2781-123">`Break`Оператор завершает выполнение `Switch` инструкции.</span><span class="sxs-lookup"><span data-stu-id="d2781-123">The `Break` statement terminates the `Switch` statement.</span></span>

```powershell
switch (3)
{
    1 {"It is one."}
    2 {"It is two."}
    3 {"It is three."; Break}
    4 {"It is four."}
    3 {"Three again."}
}
```

```Output
It is three.
```

<span data-ttu-id="d2781-124">Если тестовое значение является коллекцией, например массивом, каждый элемент в коллекции вычисляется в том порядке, в котором он отображается.</span><span class="sxs-lookup"><span data-stu-id="d2781-124">If the test value is a collection, such as an array, each item in the collection is evaluated in the order in which it appears.</span></span> <span data-ttu-id="d2781-125">В следующих примерах вычисляется 4, а затем 2.</span><span class="sxs-lookup"><span data-stu-id="d2781-125">The following examples evaluates 4 and then 2.</span></span>

```powershell
switch (4, 2)
{
    1 {"It is one." }
    2 {"It is two." }
    3 {"It is three." }
    4 {"It is four." }
    3 {"Three again."}
}
```

```Output
It is four.
It is two.
```

<span data-ttu-id="d2781-126">Любые `Break` инструкции применяются к коллекции, а не к каждому значению, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d2781-126">Any `Break` statements apply to the collection, not to each value, as shown in the following example.</span></span> <span data-ttu-id="d2781-127">`Switch`Оператор завершается `Break` оператором в условии value 4.</span><span class="sxs-lookup"><span data-stu-id="d2781-127">The `Switch` statement is terminated by the `Break` statement in the condition of value 4.</span></span>

```powershell
switch (4, 2)
{
    1 {"It is one."; Break}
    2 {"It is two." ; Break }
    3 {"It is three." ; Break }
    4 {"It is four." ; Break }
    3 {"Three again."}
}
```

```Output
It is four.
```

### <a name="syntax"></a><span data-ttu-id="d2781-128">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d2781-128">Syntax</span></span>

<span data-ttu-id="d2781-129">Полный `Switch` синтаксис инструкции выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d2781-129">The complete `Switch` statement syntax is as follows:</span></span>

```
switch [-regex|-wildcard|-exact][-casesensitive] (<value>)
{
    "string"|number|variable|{ expression } { statementlist }
    default { statementlist }
}
```

<span data-ttu-id="d2781-130">or</span><span class="sxs-lookup"><span data-stu-id="d2781-130">or</span></span>

```
switch [-regex|-wildcard|-exact][-casesensitive] -file filename
{
    "string"|number|variable|{ expression } { statementlist }
    default { statementlist }
}
```

<span data-ttu-id="d2781-131">Если параметры не используются, `Switch` ведет себя так же, как при использовании **точного** параметра.</span><span class="sxs-lookup"><span data-stu-id="d2781-131">If no parameters are used, `Switch` behaves the same as using the **Exact** parameter.</span></span> <span data-ttu-id="d2781-132">Для этого значения выполняется сравнение без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="d2781-132">It performs a case-insensitive match for the value.</span></span> <span data-ttu-id="d2781-133">Если значение является коллекцией, каждый элемент вычисляется в том порядке, в котором он отображается.</span><span class="sxs-lookup"><span data-stu-id="d2781-133">If the value is a collection, each element is evaluated in the order in which it appears.</span></span>

<span data-ttu-id="d2781-134">`Switch`Инструкция должна включать хотя бы одну инструкцию Condition.</span><span class="sxs-lookup"><span data-stu-id="d2781-134">The `Switch` statement must include at least one condition statement.</span></span>

<span data-ttu-id="d2781-135">`Default`Предложение активируется, если значение не соответствует ни одному из условий.</span><span class="sxs-lookup"><span data-stu-id="d2781-135">The `Default` clause is triggered when the value does not match any of the conditions.</span></span> <span data-ttu-id="d2781-136">Он эквивалентен `Else` предложению в `If` операторе.</span><span class="sxs-lookup"><span data-stu-id="d2781-136">It is equivalent to an `Else` clause in an `If` statement.</span></span> <span data-ttu-id="d2781-137">`Default`В каждой инструкции допускается только одно предложение `Switch` .</span><span class="sxs-lookup"><span data-stu-id="d2781-137">Only one `Default` clause is permitted in each `Switch` statement.</span></span>

<span data-ttu-id="d2781-138">`Switch` имеет следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="d2781-138">`Switch` has the following parameters:</span></span>

- <span data-ttu-id="d2781-139">**Подстановочный знак** — указывает, что условие является строкой с подстановочными знаками.</span><span class="sxs-lookup"><span data-stu-id="d2781-139">**Wildcard** - Indicates that the condition is a wildcard string.</span></span> <span data-ttu-id="d2781-140">Если предложение Match не является строкой, параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="d2781-140">If the match clause is not a string, the parameter is ignored.</span></span> <span data-ttu-id="d2781-141">При сравнении регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="d2781-141">The comparison is case-insensitive.</span></span>
- <span data-ttu-id="d2781-142">**СОВПАД** — указывает, что предложение Match, если оно является строкой, должно точно совпадать.</span><span class="sxs-lookup"><span data-stu-id="d2781-142">**Exact** - Indicates that the match clause, if it is a string, must match exactly.</span></span> <span data-ttu-id="d2781-143">Если предложение Match не является строкой, этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="d2781-143">If the match clause is not a string, this parameter is ignored.</span></span> <span data-ttu-id="d2781-144">При сравнении регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="d2781-144">The comparison is case-insensitive.</span></span>
- <span data-ttu-id="d2781-145">**CaseSensitive** — выполняет совпадение с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="d2781-145">**CaseSensitive** - Performs a case-sensitive match.</span></span> <span data-ttu-id="d2781-146">Если предложение Match не является строкой, этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="d2781-146">If the match clause is not a string, this parameter is ignored.</span></span>
- <span data-ttu-id="d2781-147">**Файл** — принимает входные данные из файла, а не из оператора значения.</span><span class="sxs-lookup"><span data-stu-id="d2781-147">**File** - Takes input from a file rather than a value statement.</span></span> <span data-ttu-id="d2781-148">Если включено несколько параметров **файла** , используется только последний из них.</span><span class="sxs-lookup"><span data-stu-id="d2781-148">If multiple **File** parameters are included, only the last one is used.</span></span> <span data-ttu-id="d2781-149">Каждая строка файла считывается и оценивается `Switch` инструкцией.</span><span class="sxs-lookup"><span data-stu-id="d2781-149">Each line of the file is read and evaluated by the `Switch` statement.</span></span> <span data-ttu-id="d2781-150">При сравнении регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="d2781-150">The comparison is case-insensitive.</span></span>
- <span data-ttu-id="d2781-151">**Regex** — выполняет регулярное выражение, совпадающее со значением условия.</span><span class="sxs-lookup"><span data-stu-id="d2781-151">**Regex** - Performs regular expression matching of the value to the condition.</span></span> <span data-ttu-id="d2781-152">Если предложение Match не является строкой, этот параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="d2781-152">If the match clause is not a string, this parameter is ignored.</span></span>
  <span data-ttu-id="d2781-153">При сравнении регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="d2781-153">The comparison is case-insensitive.</span></span> <span data-ttu-id="d2781-154">`$matches`Автоматическая переменная доступна для использования в блоке инструкций Match.</span><span class="sxs-lookup"><span data-stu-id="d2781-154">The `$matches` automatic variable is available for use within the matching statement block.</span></span>

> [!NOTE]
> <span data-ttu-id="d2781-155">При указании конфликтующих значений, таких как **регулярное выражение** и **подстановочный знак** , последний заданный параметр имеет приоритет, а все конфликтующие параметры игнорируются.</span><span class="sxs-lookup"><span data-stu-id="d2781-155">When specifying conflicting values, like **Regex** and **Wildcard** , the last parameter specified takes precedence, and all conflicting parameters are ignored.</span></span> <span data-ttu-id="d2781-156">Также разрешено использовать несколько экземпляров параметров.</span><span class="sxs-lookup"><span data-stu-id="d2781-156">Multiple instances of parameters are also permitted.</span></span> <span data-ttu-id="d2781-157">Однако действует только последний использованный параметр.</span><span class="sxs-lookup"><span data-stu-id="d2781-157">However, only the last parameter used is effective.</span></span>

<span data-ttu-id="d2781-158">В этом примере объект, не являющийся строкой или числовыми данными, передается в `Switch` .</span><span class="sxs-lookup"><span data-stu-id="d2781-158">In this example, an object that's not a string or numerical data is passed to the `Switch`.</span></span> <span data-ttu-id="d2781-159">`Switch`Выполняет приведение строк для объекта и вычисляет результат.</span><span class="sxs-lookup"><span data-stu-id="d2781-159">The `Switch` performs a string coercion on the object and evaluates the outcome.</span></span>

```powershell
$test = @{
    Test  = 'test'
    Test2 = 'test2'
}

$test.ToString()

switch -Exact ($test)
{
    'System.Collections.Hashtable'
    {
        'Hashtable string coercion'
    }
    'test'
    {
        'Hashtable value'
    }
}
```

```Output
System.Collections.Hashtable
Hashtable string coercion
```

<span data-ttu-id="d2781-160">В этом примере нет соответствующего регистра, поэтому выходные данные отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="d2781-160">In this example, there is no matching case so there is no output.</span></span>

```powershell
switch ("fourteen")
{
    1 {"It is one."; Break}
    2 {"It is two."; Break}
    3 {"It is three."; Break}
    4 {"It is four."; Break}
    "fo*" {"That's too many."}
}
```

<span data-ttu-id="d2781-161">Добавив `Default` предложение, можно выполнить действие, когда никакие другие условия не будут выполнены.</span><span class="sxs-lookup"><span data-stu-id="d2781-161">By adding the `Default` clause, you can perform an action when no other conditions succeed.</span></span>

```powershell
switch ("fourteen")
{
    1 {"It is one."; Break}
    2 {"It is two."; Break}
    3 {"It is three."; Break}
    4 {"It is four."; Break}
    "fo*" {"That's too many."}
    Default {
        "No matches"
    }
}
```

```Output
No matches
```

<span data-ttu-id="d2781-162">Чтобы слово «четырнадцать» соответствовало регистру, необходимо использовать `-Wildcard` `-Regex` параметр или.</span><span class="sxs-lookup"><span data-stu-id="d2781-162">For the word "fourteen" to match a case you must use the `-Wildcard` or `-Regex` parameter.</span></span>

```powershell
   PS> switch -Wildcard ("fourteen")
       {
           1 {"It is one."; Break}
           2 {"It is two."; Break}
           3 {"It is three."; Break}
           4 {"It is four."; Break}
           "fo*" {"That's too many."}
       }
 ```

```Output
That's too many.
```

<span data-ttu-id="d2781-163">В следующем примере используется `-Regex` параметр.</span><span class="sxs-lookup"><span data-stu-id="d2781-163">The following example uses the `-Regex` parameter.</span></span>

```powershell
$target = 'https://bing.com'
switch -Regex ($target)
{
    '^ftp\://.*$' { "$_ is an ftp address"; Break }
    '^\w+@\w+\.com|edu|org$' { "$_ is an email address"; Break }
    '^(http[s]?)\://.*$' { "$_ is a web address that uses $($matches[1])"; Break }
}
```

```Output
https://bing.com is a web address that uses https
```

<span data-ttu-id="d2781-164">Условие оператора switch может иметь одно из следующих условий:</span><span class="sxs-lookup"><span data-stu-id="d2781-164">A Switch statement condition may be either:</span></span>

- <span data-ttu-id="d2781-165">Выражение, значение которого сравнивается с входным значением</span><span class="sxs-lookup"><span data-stu-id="d2781-165">An expression whose value is compared to the input value</span></span>
- <span data-ttu-id="d2781-166">Блок скрипта, который должен возвращать, `$true` Если условие выполнено.</span><span class="sxs-lookup"><span data-stu-id="d2781-166">A script block which should return `$true` if a condition is met.</span></span>

<span data-ttu-id="d2781-167">`$_`Автоматическая переменная содержит значение, передаваемое оператору switch, и доступно для оценки и использования в области операторов условия.</span><span class="sxs-lookup"><span data-stu-id="d2781-167">The `$_` automatic variable contains the value passed to the switch statement and is available for evaluation and use within the scope of the condition statements.</span></span>

<span data-ttu-id="d2781-168">Действие для каждого условия не зависит от действий в других условиях.</span><span class="sxs-lookup"><span data-stu-id="d2781-168">The action for each condition is independent of the actions in other conditions.</span></span>

<span data-ttu-id="d2781-169">В следующем примере показано использование блоков script в качестве `Switch` условий инструкции.</span><span class="sxs-lookup"><span data-stu-id="d2781-169">The following example demonstrates the use of script blocks as `Switch` statement conditions.</span></span>

```powershell
switch ("Test")
{
    {$_ -is [String]} {
        "Found a string"
    }
    "Test" {
        "This $_ executes as well"
    }
}
```

```Output
Found a string
This Test executes as well
```

<span data-ttu-id="d2781-170">Если значение соответствует нескольким условиям, выполняется действие для каждого условия.</span><span class="sxs-lookup"><span data-stu-id="d2781-170">If the value matches multiple conditions, the action for each condition is executed.</span></span> <span data-ttu-id="d2781-171">Чтобы изменить это поведение, используйте `Break` `Continue` Ключевые слова или.</span><span class="sxs-lookup"><span data-stu-id="d2781-171">To change this behavior, use the `Break` or `Continue` keywords.</span></span>

<span data-ttu-id="d2781-172">`Break`Ключевое слово останавливает обработку и завершает выполнение `Switch` инструкции.</span><span class="sxs-lookup"><span data-stu-id="d2781-172">The `Break` keyword stops processing and exits the `Switch` statement.</span></span>

<span data-ttu-id="d2781-173">`Continue`Ключевое слово останавливает обработку текущего значения, но возобновляет обработку всех последующих значений.</span><span class="sxs-lookup"><span data-stu-id="d2781-173">The `Continue` keyword stops processing the current value, but continues processing any subsequent values.</span></span>

<span data-ttu-id="d2781-174">В следующем примере выполняется обработка массива чисел и отображение, если они являются нечетными или четными.</span><span class="sxs-lookup"><span data-stu-id="d2781-174">The following example processes an array of numbers and displays if they are odd or even.</span></span> <span data-ttu-id="d2781-175">Отрицательные числа пропускаются с помощью `Continue` ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="d2781-175">Negative numbers are skipped with the `Continue` keyword.</span></span> <span data-ttu-id="d2781-176">Если обнаружено нечисловое значение, выполнение завершается с помощью `Break` ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="d2781-176">If a non-number is encountered, execution is terminated with the `Break` keyword.</span></span>

```powershell
switch (1,4,-1,3,"Hello",2,1)
{
    {$_ -lt 0} { Continue }
    {$_ -isnot [Int32]} { Break }
    {$_ % 2} {
        "$_ is Odd"
    }
    {-not ($_ % 2)} {
        "$_ is Even"
    }
}
```

```Output
1 is Odd
4 is Even
3 is Odd
```

## <a name="see-also"></a><span data-ttu-id="d2781-177">См. также статью</span><span class="sxs-lookup"><span data-stu-id="d2781-177">See also</span></span>

[<span data-ttu-id="d2781-178">about_Break</span><span class="sxs-lookup"><span data-stu-id="d2781-178">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="d2781-179">about_Continue</span><span class="sxs-lookup"><span data-stu-id="d2781-179">about_Continue</span></span>](about_Continue.md)

[<span data-ttu-id="d2781-180">about_If</span><span class="sxs-lookup"><span data-stu-id="d2781-180">about_If</span></span>](about_If.md)

[<span data-ttu-id="d2781-181">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="d2781-181">about_Script_Blocks</span></span>](about_Script_Blocks.md)
