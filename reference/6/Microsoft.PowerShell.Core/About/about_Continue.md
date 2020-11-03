---
description: Описывает, как `continue` инструкция немедленно возвращает поток программы в начало цикла программы, `switch` инструкции или `trap` инструкции.
keywords: powershell,командлет
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_continue?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Continue
ms.openlocfilehash: e2e1c3e6d1a1881919c69d52c1fdf27814450293
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231534"
---
# <a name="about-continue"></a><span data-ttu-id="b0de7-104">Сведения о продолжении</span><span class="sxs-lookup"><span data-stu-id="b0de7-104">About Continue</span></span>

## <a name="short-description"></a><span data-ttu-id="b0de7-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="b0de7-105">Short description</span></span>

<span data-ttu-id="b0de7-106">Описывает, как `continue` инструкция немедленно возвращает поток программы в начало цикла программы, `switch` инструкции или `trap` инструкции.</span><span class="sxs-lookup"><span data-stu-id="b0de7-106">Describes how the `continue` statement immediately returns the program flow to the top of a program loop, a `switch` statement, or a `trap` statement.</span></span>

## <a name="long-description"></a><span data-ttu-id="b0de7-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="b0de7-107">Long description</span></span>

<span data-ttu-id="b0de7-108">`continue`Оператор позволяет выйти из текущего блока управления, но продолжить выполнение, а не выйти полностью.</span><span class="sxs-lookup"><span data-stu-id="b0de7-108">The `continue` statement provides a way to exit the current control block but continue execution, rather than exit completely.</span></span> <span data-ttu-id="b0de7-109">Инструкция поддерживает метки.</span><span class="sxs-lookup"><span data-stu-id="b0de7-109">The statement supports labels.</span></span>
<span data-ttu-id="b0de7-110">Метка — это имя, назначаемое оператору в скрипте.</span><span class="sxs-lookup"><span data-stu-id="b0de7-110">A label is a name you assign to a statement in a script.</span></span>

## <a name="using-continue-in-loops"></a><span data-ttu-id="b0de7-111">Использование циклов continue в</span><span class="sxs-lookup"><span data-stu-id="b0de7-111">Using continue in loops</span></span>

<span data-ttu-id="b0de7-112">Оператор без метки `continue` немедленно возвращает поток программы в начало самого внутреннего цикла, управляемого `for` `foreach` `do` оператором,, или `while` .</span><span class="sxs-lookup"><span data-stu-id="b0de7-112">An unlabeled `continue` statement immediately returns the program flow to the top of the innermost loop that is controlled by a `for`, `foreach`, `do`, or `while` statement.</span></span> <span data-ttu-id="b0de7-113">Текущая итерация цикла завершается, а цикл переходит к следующей итерации.</span><span class="sxs-lookup"><span data-stu-id="b0de7-113">The current iteration of the loop is terminated and the loop continues with the next iteration.</span></span>

<span data-ttu-id="b0de7-114">В следующем примере программный поток возвращается в начало `while` цикла, если `$ctr` переменная равна 5.</span><span class="sxs-lookup"><span data-stu-id="b0de7-114">In the following example, program flow returns to the top of the `while` loop if the `$ctr` variable is equal to 5.</span></span> <span data-ttu-id="b0de7-115">В результате отображаются все числа от 1 до 10, за исключением 5:</span><span class="sxs-lookup"><span data-stu-id="b0de7-115">As a result, all the numbers between 1 and 10 are displayed except for 5:</span></span>

```powershell
while ($ctr -lt 10)
{
    $ctr += 1
    if ($ctr -eq 5)
    {
        continue
    }

    Write-Host -Object $ctr
}
```

<span data-ttu-id="b0de7-116">При использовании `for` цикла выполнение продолжится в `<Repeat>` операторе, за которым следует `<Condition>` тест.</span><span class="sxs-lookup"><span data-stu-id="b0de7-116">When using a `for` loop, execution continues at the `<Repeat>` statement, followed by the `<Condition>` test.</span></span> <span data-ttu-id="b0de7-117">В приведенном ниже примере бесконечный цикл не будет выполняться, поскольку уменьшение `$i` происходит после `continue` ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="b0de7-117">In the example below, an infinite loop will not occur because the decrement of `$i` occurs after the `continue` keyword.</span></span>

```powershell
#   <Init>  <Condition> <Repeat>
for ($i = 0; $i -lt 10; $i++)
{
    Write-Host -Object $i
    if ($i -eq 5)
    {
        continue
        # Will not result in an infinite loop.
        $i--
    }
}
```

### <a name="using-a-labeled-continue-in-a-loop"></a><span data-ttu-id="b0de7-118">Использование метки continue в цикле</span><span class="sxs-lookup"><span data-stu-id="b0de7-118">Using a labeled continue in a loop</span></span>

<span data-ttu-id="b0de7-119">Оператор с меткой `continue` завершает выполнение итерации и передает управление целевой включающей итерации или `switch` метке оператора.</span><span class="sxs-lookup"><span data-stu-id="b0de7-119">A labeled `continue` statement terminates execution of the iteration and transfers control to the targeted enclosing iteration or `switch` statement label.</span></span>

<span data-ttu-id="b0de7-120">В следующем примере внутренний `for` конец завершается, когда `$condition` имеет **значение true** , а итерация переходит во второй `for` цикл в `labelB` .</span><span class="sxs-lookup"><span data-stu-id="b0de7-120">In the following example, the innermost `for` is terminated when `$condition` is **True** and iteration continues with the second `for` loop at `labelB`.</span></span>

```powershell
:labelA for ($i = 1; $i -le 10; $i++) {
    :labelB for ($j = 1; $j -le 10; $j++) {
        :labelC for ($k = 1; $k -le 10; $k++) {
            if ($condition) {
                continue labelB
            } else {
                $condition = Update-Condition
            }
        }
    }
}
```

## <a name="using-continue-in-a-switch-statement"></a><span data-ttu-id="b0de7-121">Использование Continue в операторе switch</span><span class="sxs-lookup"><span data-stu-id="b0de7-121">Using continue in a switch statement</span></span>

<span data-ttu-id="b0de7-122">Оператор без метки в компоненте `continue` `switch` завершает выполнение текущей `switch` итерации и передает управление в начало, `switch` чтобы получить следующий входной элемент.</span><span class="sxs-lookup"><span data-stu-id="b0de7-122">An unlabeled `continue` statement within a `switch` terminates execution of the current `switch` iteration and transfers control to the top of the `switch` to get the next input item.</span></span>

<span data-ttu-id="b0de7-123">При наличии одного входного элемента `continue` завершается вся `switch` инструкция.</span><span class="sxs-lookup"><span data-stu-id="b0de7-123">When there is a single input item `continue` exits the entire `switch` statement.</span></span>
<span data-ttu-id="b0de7-124">Если `switch` входные данные являются коллекцией, то `switch` проверяет каждый элемент коллекции.</span><span class="sxs-lookup"><span data-stu-id="b0de7-124">When the `switch` input is a collection, the `switch` tests each element of the collection.</span></span> <span data-ttu-id="b0de7-125">Выполняет `continue` выход из текущей итерации и `switch` переходит к следующему элементу.</span><span class="sxs-lookup"><span data-stu-id="b0de7-125">The `continue` exits the current iteration and the `switch` continues with the next element.</span></span>

```powershell
switch (1,2,3) {
  2 { continue }  # moves on to the next element, 3
  default { $_ }
}
```

```Output
1
3
```

## <a name="using-continue-in-a-trap-statement"></a><span data-ttu-id="b0de7-126">Использование Continue в операторе Trap</span><span class="sxs-lookup"><span data-stu-id="b0de7-126">Using continue in a trap statement</span></span>

<span data-ttu-id="b0de7-127">Если итоговая инструкция, выполненная в теле `trap` оператора, имеет значение `continue` , то перехваченная ошибка пропускается без уведомления, и выполнение переходит к выполнению инструкции, следующей за той причиной, в которой она `trap` возникла.</span><span class="sxs-lookup"><span data-stu-id="b0de7-127">If the final statement executed in the body a `trap` statement is `continue`, the trapped error is silently ignored and execution continues with the statement immediately following the one that caused `trap` to occur.</span></span>

## <a name="do-not-use-continue-outside-of-a-loop-switch-or-trap"></a><span data-ttu-id="b0de7-128">Не используйте оператор continue вне цикла, переключателя или ловушки</span><span class="sxs-lookup"><span data-stu-id="b0de7-128">Do not use continue outside of a loop, switch, or trap</span></span>

<span data-ttu-id="b0de7-129">Если `continue` используется вне конструкции, которая напрямую поддерживает эту функцию (циклы, `switch` , `trap` ), PowerShell ищет _Стек вызовов_ для включающей конструкции.</span><span class="sxs-lookup"><span data-stu-id="b0de7-129">When `continue` is used outside of a construct that directly supports it (loops, `switch`, `trap`), PowerShell looks _up the call stack_ for an enclosing construct.</span></span> <span data-ttu-id="b0de7-130">Если не удается найти включающую конструкцию, текущее пространство выполнения беззвучно завершается.</span><span class="sxs-lookup"><span data-stu-id="b0de7-130">If it can't find an enclosing construct, the current runspace is quietly terminated.</span></span>

<span data-ttu-id="b0de7-131">Это означает, что функции и скрипты, которые непреднамеренно используют `continue` вне окружающей конструкции, поддерживающей эту функцию, могут случайно завершить свои _вызывающие объекты_.</span><span class="sxs-lookup"><span data-stu-id="b0de7-131">This means that functions and scripts that inadvertently use a `continue` outside of an enclosing construct that supports it, can inadvertently terminate their _callers_.</span></span>

<span data-ttu-id="b0de7-132">Использование `continue` внутри конвейера, такого как `ForEach-Object` блок скрипта, не только завершает работу конвейера, TT потенциально завершает все пространство выполнения.</span><span class="sxs-lookup"><span data-stu-id="b0de7-132">Using `continue` inside a pipeline, such as a `ForEach-Object` script block, not only exits the pipeline, tt potentially terminates the entire runspace.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0de7-133">См. также статью</span><span class="sxs-lookup"><span data-stu-id="b0de7-133">See also</span></span>

[<span data-ttu-id="b0de7-134">about_Break</span><span class="sxs-lookup"><span data-stu-id="b0de7-134">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="b0de7-135">about_For</span><span class="sxs-lookup"><span data-stu-id="b0de7-135">about_For</span></span>](about_For.md)

[<span data-ttu-id="b0de7-136">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="b0de7-136">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="b0de7-137">about_Throw</span><span class="sxs-lookup"><span data-stu-id="b0de7-137">about_Throw</span></span>](about_Throw.md)

[<span data-ttu-id="b0de7-138">about_Trap</span><span class="sxs-lookup"><span data-stu-id="b0de7-138">about_Trap</span></span>](about_Trap.md)

[<span data-ttu-id="b0de7-139">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="b0de7-139">about_Try_Catch_Finally</span></span>](about_Try_Catch_Finally.md)
