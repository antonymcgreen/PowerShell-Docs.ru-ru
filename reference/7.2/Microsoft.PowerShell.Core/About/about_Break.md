---
description: Описывает инструкцию, которую можно использовать для немедленного выхода из операторов,,,, `foreach` `for` `while` `do` `switch` или `trap` .
Locale: en-US
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_break?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Break
ms.openlocfilehash: 3c418f5bae11f957880c8b53ee0bcf2fb44515ee
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604498"
---
# <a name="about-break"></a><span data-ttu-id="d4c87-103">О прерывании</span><span class="sxs-lookup"><span data-stu-id="d4c87-103">About Break</span></span>

## <a name="short-description"></a><span data-ttu-id="d4c87-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="d4c87-104">Short description</span></span>

<span data-ttu-id="d4c87-105">Описывает инструкцию, которую можно использовать для немедленного выхода из операторов,,,, `foreach` `for` `while` `do` `switch` или `trap` .</span><span class="sxs-lookup"><span data-stu-id="d4c87-105">Describes a statement you can use to immediately exit `foreach`, `for`, `while`, `do`, `switch`, or `trap` statements.</span></span>

## <a name="long-description"></a><span data-ttu-id="d4c87-106">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="d4c87-106">Long description</span></span>

<span data-ttu-id="d4c87-107">`break`Оператор предоставляет способ выхода из текущего управляющего блока.</span><span class="sxs-lookup"><span data-stu-id="d4c87-107">The `break` statement provides a way to exit the current control block.</span></span>
<span data-ttu-id="d4c87-108">Выполнение продолжится в следующей инструкции после блока управления.</span><span class="sxs-lookup"><span data-stu-id="d4c87-108">Execution continues at the next statement after the control block.</span></span> <span data-ttu-id="d4c87-109">Инструкция поддерживает метки.</span><span class="sxs-lookup"><span data-stu-id="d4c87-109">The statement supports labels.</span></span> <span data-ttu-id="d4c87-110">Метка — это имя, назначаемое оператору в скрипте.</span><span class="sxs-lookup"><span data-stu-id="d4c87-110">A label is a name you assign to a statement in a script.</span></span>

## <a name="using-break-in-loops"></a><span data-ttu-id="d4c87-111">Использование циклов Break</span><span class="sxs-lookup"><span data-stu-id="d4c87-111">Using break in loops</span></span>

<span data-ttu-id="d4c87-112">Если `break` оператор присутствует в цикле, таком как `foreach` цикл,, `for` `do` или `while` , PowerShell немедленно завершает работу цикла.</span><span class="sxs-lookup"><span data-stu-id="d4c87-112">When a `break` statement appears in a loop, such as a `foreach`, `for`, `do`, or `while` loop, PowerShell immediately exits the loop.</span></span>

<span data-ttu-id="d4c87-113">`break`Оператор может включать метку, которая позволяет выйти из встраиваемых циклов.</span><span class="sxs-lookup"><span data-stu-id="d4c87-113">A `break` statement can include a label that lets you exit embedded loops.</span></span> <span data-ttu-id="d4c87-114">Метка может указывать любое ключевое слово Loop, такое как `foreach` , `for` или `while` , в скрипте.</span><span class="sxs-lookup"><span data-stu-id="d4c87-114">A label can specify any loop keyword, such as `foreach`, `for`, or `while`, in a script.</span></span>

<span data-ttu-id="d4c87-115">В следующем примере показано, как использовать `break` оператор для выхода из `for` оператора:</span><span class="sxs-lookup"><span data-stu-id="d4c87-115">The following example shows how to use a `break` statement to exit a `for` statement:</span></span>

```powershell
for($i=1; $i -le 10; $i++) {
   Write-Host $i
   break
}
```

<span data-ttu-id="d4c87-116">В этом примере `break` оператор завершает `for` цикл, если `$i` переменная равна 1.</span><span class="sxs-lookup"><span data-stu-id="d4c87-116">In this example, the `break` statement exits the `for` loop when the `$i` variable equals 1.</span></span> <span data-ttu-id="d4c87-117">Несмотря на то `for` , что оператор принимает **значение true** до тех пор `$i` , пока не будет больше 10, PowerShell достигают оператора break при первом `for` запуске цикла.</span><span class="sxs-lookup"><span data-stu-id="d4c87-117">Even though the `for` statement evaluates to **True** until `$i` is greater than 10, PowerShell reaches the break statement the first time the `for` loop is run.</span></span>

<span data-ttu-id="d4c87-118">Чаще используется `break` оператор в цикле, где должно выполняться внутреннее условие.</span><span class="sxs-lookup"><span data-stu-id="d4c87-118">It is more common to use the `break` statement in a loop where an inner condition must be met.</span></span> <span data-ttu-id="d4c87-119">Рассмотрим следующий `foreach` пример инструкции:</span><span class="sxs-lookup"><span data-stu-id="d4c87-119">Consider the following `foreach` statement example:</span></span>

```powershell
$i=0
$varB = 10,20,30,40
foreach ($val in $varB) {
  if ($val -eq 30) {
    break
  }
  $i++
}
Write-Host "30 was found in array index $i"
```

<span data-ttu-id="d4c87-120">В этом примере `foreach` оператор выполняет итерацию `$varB` массива.</span><span class="sxs-lookup"><span data-stu-id="d4c87-120">In this example, the `foreach` statement iterates the `$varB` array.</span></span> <span data-ttu-id="d4c87-121">`if`Оператор возвращает значение false, если первые два раза выполняются в цикле, а переменная `$i` увеличивается на 1.</span><span class="sxs-lookup"><span data-stu-id="d4c87-121">The `if` statement evaluates to False the first two times the loop is run and the variable `$i` is incremented by 1.</span></span> <span data-ttu-id="d4c87-122">Третье время выполнения цикла `$i` равно 2, а `$val` переменная равна 30.</span><span class="sxs-lookup"><span data-stu-id="d4c87-122">The third time the loop is run, `$i` equals 2, and the `$val` variable equals 30.</span></span> <span data-ttu-id="d4c87-123">На этом этапе `break` выполняется инструкция, и `foreach` цикл завершает работу.</span><span class="sxs-lookup"><span data-stu-id="d4c87-123">At this point, the `break` statement runs, and the `foreach` loop exits.</span></span>

### <a name="using-a-labeled-break-in-a-loop"></a><span data-ttu-id="d4c87-124">Использование приостановки с меткой в цикле</span><span class="sxs-lookup"><span data-stu-id="d4c87-124">Using a labeled break in a loop</span></span>

<span data-ttu-id="d4c87-125">`break`Оператор может включать метку.</span><span class="sxs-lookup"><span data-stu-id="d4c87-125">A `break` statement can include a label.</span></span> <span data-ttu-id="d4c87-126">При использовании `break` ключевого слова с меткой PowerShell выходит из цикла с меткой, а не выходит из текущего цикла.</span><span class="sxs-lookup"><span data-stu-id="d4c87-126">If you use the `break` keyword with a label, PowerShell exits the labeled loop instead of exiting the current loop.</span></span>
<span data-ttu-id="d4c87-127">Метка — это двоеточие, за которым следует присвоенное имя.</span><span class="sxs-lookup"><span data-stu-id="d4c87-127">The label is a colon followed by a name that you assign.</span></span> <span data-ttu-id="d4c87-128">Метка должна быть первой лексемой в операторе, а за ней должно следовать ключевое слово Loop, например `while` .</span><span class="sxs-lookup"><span data-stu-id="d4c87-128">The label must be the first token in a statement, and it must be followed by the looping keyword, such as `while`.</span></span>

<span data-ttu-id="d4c87-129">`break` Перемещает выполнение из цикла с меткой.</span><span class="sxs-lookup"><span data-stu-id="d4c87-129">`break` moves execution out of the labeled loop.</span></span> <span data-ttu-id="d4c87-130">Во встроенных циклах результат отличается от результата `break` ключевого слова при его использовании.</span><span class="sxs-lookup"><span data-stu-id="d4c87-130">In embedded loops, this has a different result than the `break` keyword has when it is used by itself.</span></span> <span data-ttu-id="d4c87-131">В этом примере имеется `while` оператор с `for` оператором:</span><span class="sxs-lookup"><span data-stu-id="d4c87-131">This example has a `while` statement with a `for` statement:</span></span>

```powershell
:myLabel while (<condition 1>) {
  for ($item in $items) {
    if (<condition 2>) {
      break myLabel
    }
    $item = $x   # A statement inside the For-loop
  }
}
$a = $c  # A statement after the labeled While-loop
```

<span data-ttu-id="d4c87-132">Если условие 2 принимает **значение true**, выполнение сценария пропускается до оператора после помеченного цикла.</span><span class="sxs-lookup"><span data-stu-id="d4c87-132">If condition 2 evaluates to **True**, the execution of the script skips down to the statement after the labeled loop.</span></span> <span data-ttu-id="d4c87-133">В этом примере выполнение начинается с оператора `$a = $c` .</span><span class="sxs-lookup"><span data-stu-id="d4c87-133">In the example, execution starts again with the statement `$a = $c`.</span></span>

<span data-ttu-id="d4c87-134">Можно вложить много циклов с метками, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d4c87-134">You can nest many labeled loops, as shown in the following example.</span></span>

```powershell
:red while (<condition1>) {
  :yellow while (<condition2>) {
    while (<condition3>) {
      if ($a) {break}
      if ($b) {break red}
      if ($c) {break yellow}
    }
    Write-Host "After innermost loop"
  }
  Write-Host "After yellow loop"
}
Write-Host "After red loop"
```

<span data-ttu-id="d4c87-135">Если `$b` переменная имеет значение true, выполнение сценария возобновляется после цикла, помеченного как "Red".</span><span class="sxs-lookup"><span data-stu-id="d4c87-135">If the `$b` variable evaluates to True, execution of the script resumes after the loop that is labeled "red".</span></span> <span data-ttu-id="d4c87-136">Если значение `$c` переменной равно true, выполнение элемента управления скрипта возобновляется после цикла, помеченного как "желтый".</span><span class="sxs-lookup"><span data-stu-id="d4c87-136">If the `$c` variable evaluates to True, execution of the script control resumes after the loop that is labeled "yellow".</span></span>

<span data-ttu-id="d4c87-137">Если значение `$a` переменной равно true, выполнение возобновляется после самого внутреннего цикла.</span><span class="sxs-lookup"><span data-stu-id="d4c87-137">If the `$a` variable evaluates to True, execution resumes after the innermost loop.</span></span> <span data-ttu-id="d4c87-138">Метка не требуется.</span><span class="sxs-lookup"><span data-stu-id="d4c87-138">No label is needed.</span></span>

<span data-ttu-id="d4c87-139">PowerShell не ограничивает, насколько далеко могут возобновить выполнение меток.</span><span class="sxs-lookup"><span data-stu-id="d4c87-139">PowerShell does not limit how far labels can resume execution.</span></span> <span data-ttu-id="d4c87-140">Метка может даже передавать управление между скриптом и границами вызовов функций.</span><span class="sxs-lookup"><span data-stu-id="d4c87-140">The label can even pass control across script and function call boundaries.</span></span>

## <a name="using-break-in-a-switch-statement"></a><span data-ttu-id="d4c87-141">Использование оператора break в операторе switch</span><span class="sxs-lookup"><span data-stu-id="d4c87-141">Using break in a switch statement</span></span>

<span data-ttu-id="d4c87-142">В `switch` конструкции `break` заставляет PowerShell выйти из `switch` блока кода.</span><span class="sxs-lookup"><span data-stu-id="d4c87-142">In a `switch`construct, `break` causes PowerShell to exit the `switch` code block.</span></span>

<span data-ttu-id="d4c87-143">`break`Ключевое слово используется для выхода из `switch` конструкции.</span><span class="sxs-lookup"><span data-stu-id="d4c87-143">The `break` keyword is used to leave the `switch` construct.</span></span> <span data-ttu-id="d4c87-144">Например, следующая `switch` инструкция использует `break` инструкции для проверки наиболее конкретного условия:</span><span class="sxs-lookup"><span data-stu-id="d4c87-144">For example, the following `switch` statement uses `break` statements to test for the most specific condition:</span></span>

```powershell
$var = "word2"
switch -regex ($var) {
    "word2" {
      Write-Host "Exact" $_
      break
    }

    "word.*" {
      Write-Host "Match on the prefix" $_
      break
    }

    "w.*" {
      Write-Host "Match on at least the first letter" $_
      break
    }

    default {
      Write-Host "No match" $_
      break
    }
}
```

<span data-ttu-id="d4c87-145">В этом примере `$var` переменная создается и инициализируется строковым значением `word2` .</span><span class="sxs-lookup"><span data-stu-id="d4c87-145">In this example, the `$var` variable is created and initialized to a string value of `word2`.</span></span> <span data-ttu-id="d4c87-146">`switch`Инструкция использует класс **Regex** для сопоставления значения переменной сначала с термином `word2` .</span><span class="sxs-lookup"><span data-stu-id="d4c87-146">The `switch` statement uses the **Regex** class to match the variable value first with the term `word2`.</span></span> <span data-ttu-id="d4c87-147">Так как значение переменной и первый тест в `switch` операторе совпадают, первый блок кода в `switch` операторе выполняется.</span><span class="sxs-lookup"><span data-stu-id="d4c87-147">Because the variable value and the first test in the `switch` statement match, the first code block in the `switch` statement runs.</span></span>

<span data-ttu-id="d4c87-148">Когда PowerShell достигает первого `break` оператора, `switch` инструкция завершается.</span><span class="sxs-lookup"><span data-stu-id="d4c87-148">When PowerShell reaches the first `break` statement, the `switch` statement exits.</span></span> <span data-ttu-id="d4c87-149">Если четыре `break` инструкции удаляются из примера, выполняются все четыре условия.</span><span class="sxs-lookup"><span data-stu-id="d4c87-149">If the four `break` statements are removed from the example, all four conditions are met.</span></span> <span data-ttu-id="d4c87-150">В этом примере используется `break` оператор для вывода результатов при выполнении наиболее конкретного условия.</span><span class="sxs-lookup"><span data-stu-id="d4c87-150">This example uses the `break` statement to display results when the most specific condition is met.</span></span>

## <a name="using-break-in-a-trap-statement"></a><span data-ttu-id="d4c87-151">Использование функции break в операторе Trap</span><span class="sxs-lookup"><span data-stu-id="d4c87-151">Using break in a trap statement</span></span>

<span data-ttu-id="d4c87-152">Если последняя инструкция, выполняемая в теле `trap` инструкции, имеет значение `break` , то объект Error подавляется и исключение создается повторно.</span><span class="sxs-lookup"><span data-stu-id="d4c87-152">If the final statement executed in the body of a `trap` statement is `break`, the error object is suppressed and the exception is re-thrown.</span></span>

<span data-ttu-id="d4c87-153">В следующем примере создается исключение **DivideByZeroException** , перехваченное с помощью `trap` инструкции.</span><span class="sxs-lookup"><span data-stu-id="d4c87-153">The following example create a **DivideByZeroException** exception that is trapped using the `trap` statement.</span></span>

```powershell
function test {
  trap [DivideByZeroException] {
    Write-Host 'divide by zero trapped'
    break
  }

  $i = 3
  'Before loop'
  while ($true) {
     "1 / $i = " + (1 / $i--)
  }
  'After loop'
}
test
```

Обратите внимание, что выполнение останавливается при возникновении исключения. <span data-ttu-id="d4c87-155">`After loop`Никогда не достигается.</span><span class="sxs-lookup"><span data-stu-id="d4c87-155">The `After loop` is never reached.</span></span>
<span data-ttu-id="d4c87-156">Исключение создается повторно после `trap` выполнения.</span><span class="sxs-lookup"><span data-stu-id="d4c87-156">The exception is re-thrown after the `trap` executes.</span></span>

```Output
Before loop
1 / 3 = 0.333333333333333
1 / 2 = 0.5
1 / 1 = 1
divide by zero trapped
ParentContainsErrorRecordException:
Line |
  10 |       "1 / $i = " + (1 / $i--)
     |       ~~~~~~~~~~~~~~~~~~~~~~~~
     | Attempted to divide by zero.
```

## <a name="do-not-use-break-outside-of-a-loop-switch-or-trap"></a><span data-ttu-id="d4c87-157">Не используйте Break вне цикла, переключателя или ловушки</span><span class="sxs-lookup"><span data-stu-id="d4c87-157">Do not use break outside of a loop, switch, or trap</span></span>

<span data-ttu-id="d4c87-158">Если `break` используется вне конструкции, которая напрямую поддерживает эту функцию (циклы, `switch` , `trap` ), PowerShell ищет _Стек вызовов_ для включающей конструкции.</span><span class="sxs-lookup"><span data-stu-id="d4c87-158">When `break` is used outside of a construct that directly supports it (loops, `switch`, `trap`), PowerShell looks _up the call stack_ for an enclosing construct.</span></span> <span data-ttu-id="d4c87-159">Если не удается найти включающую конструкцию, текущее пространство выполнения беззвучно завершается.</span><span class="sxs-lookup"><span data-stu-id="d4c87-159">If it can't find an enclosing construct, the current runspace is quietly terminated.</span></span>

<span data-ttu-id="d4c87-160">Это означает, что функции и скрипты, которые случайно используют `break` вне включающей конструкции, поддерживающей эту функцию, могут случайно завершить свои _вызывающие объекты_.</span><span class="sxs-lookup"><span data-stu-id="d4c87-160">This means that functions and scripts that inadvertently use a `break` outside of an enclosing construct that supports it can inadvertently terminate their _callers_.</span></span>

<span data-ttu-id="d4c87-161">Использование `break` внутри конвейера `break` , такого как `ForEach-Object` блок скрипта, не только завершает работу конвейера, но и может привести к завершению всего пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="d4c87-161">Using `break` inside a pipeline `break`, such as a `ForEach-Object` script block, not only exits the pipeline, it potentially terminates the entire runspace.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4c87-162">См. также</span><span class="sxs-lookup"><span data-stu-id="d4c87-162">See also</span></span>

[<span data-ttu-id="d4c87-163">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="d4c87-163">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="d4c87-164">about_Continue</span><span class="sxs-lookup"><span data-stu-id="d4c87-164">about_Continue</span></span>](about_Continue.md)

[<span data-ttu-id="d4c87-165">about_For</span><span class="sxs-lookup"><span data-stu-id="d4c87-165">about_For</span></span>](about_For.md)

[<span data-ttu-id="d4c87-166">about_Foreach</span><span class="sxs-lookup"><span data-stu-id="d4c87-166">about_Foreach</span></span>](about_Foreach.md)

[<span data-ttu-id="d4c87-167">about_Switch</span><span class="sxs-lookup"><span data-stu-id="d4c87-167">about_Switch</span></span>](about_Switch.md)

[<span data-ttu-id="d4c87-168">about_Throw</span><span class="sxs-lookup"><span data-stu-id="d4c87-168">about_Throw</span></span>](about_Throw.md)

[<span data-ttu-id="d4c87-169">about_Trap</span><span class="sxs-lookup"><span data-stu-id="d4c87-169">about_Trap</span></span>](about_Trap.md)

[<span data-ttu-id="d4c87-170">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="d4c87-170">about_Try_Catch_Finally</span></span>](about_Try_Catch_Finally.md)

[<span data-ttu-id="d4c87-171">about_While</span><span class="sxs-lookup"><span data-stu-id="d4c87-171">about_While</span></span>](about_While.md)
