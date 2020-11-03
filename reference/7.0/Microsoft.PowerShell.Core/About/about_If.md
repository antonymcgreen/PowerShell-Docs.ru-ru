---
description: Описывает команду языка, которую можно использовать для выполнения списков инструкций на основе результатов одного или нескольких условных тестов.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_if?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_If
ms.openlocfilehash: f5bda1b3530c104361dba12de029219a5dd0db60
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231794"
---
# <a name="about-if"></a><span data-ttu-id="be1ea-104">О программе</span><span class="sxs-lookup"><span data-stu-id="be1ea-104">About If</span></span>

## <a name="short-description"></a><span data-ttu-id="be1ea-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="be1ea-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="be1ea-106">Описывает команду языка, которую можно использовать для выполнения списков инструкций на основе результатов одного или нескольких условных тестов.</span><span class="sxs-lookup"><span data-stu-id="be1ea-106">Describes a language command you can use to run statement lists based on the results of one or more conditional tests.</span></span>

## <a name="long-description"></a><span data-ttu-id="be1ea-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="be1ea-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="be1ea-108">Можно использовать `If` инструкцию для выполнения блоков кода, если заданная условная проверка имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="be1ea-108">You can use the `If` statement to run code blocks if a specified conditional test evaluates to true.</span></span> <span data-ttu-id="be1ea-109">Можно также указать один или несколько дополнительных условных тестов для выполнения, если все предыдущие тесты имеют значение false.</span><span class="sxs-lookup"><span data-stu-id="be1ea-109">You can also specify one or more additional conditional tests to run if all the prior tests evaluate to false.</span></span> <span data-ttu-id="be1ea-110">Наконец, можно указать дополнительный блок кода, который будет выполняться, если ни одна из предыдущих условных тестов не возвращает значение true.</span><span class="sxs-lookup"><span data-stu-id="be1ea-110">Finally, you can specify an additional code block that is run if no other prior conditional test evaluates to true.</span></span>

### <a name="syntax"></a><span data-ttu-id="be1ea-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="be1ea-111">Syntax</span></span>

<span data-ttu-id="be1ea-112">В следующем примере показан `If` синтаксис инструкции:</span><span class="sxs-lookup"><span data-stu-id="be1ea-112">The following example shows the `If` statement syntax:</span></span>

```powershell
if (<test1>)
    {<statement list 1>}
[elseif (<test2>)
    {<statement list 2>}]
[else
    {<statement list 3>}]
```

<span data-ttu-id="be1ea-113">При выполнении `If` инструкции PowerShell вычисляет `<test1>` условное выражение как true или false.</span><span class="sxs-lookup"><span data-stu-id="be1ea-113">When you run an `If` statement, PowerShell evaluates the `<test1>` conditional expression as true or false.</span></span> <span data-ttu-id="be1ea-114">Если `<test1>` имеет значение true, `<statement list 1>` выполняется, а PowerShell завершает выполнение `If` инструкции.</span><span class="sxs-lookup"><span data-stu-id="be1ea-114">If `<test1>` is true, `<statement list 1>` runs, and PowerShell exits the `If` statement.</span></span> <span data-ttu-id="be1ea-115">Если `<test1>` значение равно false, то PowerShell оценивает условие, заданное `<test2>` условным оператором.</span><span class="sxs-lookup"><span data-stu-id="be1ea-115">If `<test1>` is false, PowerShell evaluates the condition specified by the `<test2>` conditional statement.</span></span>

<span data-ttu-id="be1ea-116">Если `<test2>` имеет значение true, `<statement list 2>` выполняется, а PowerShell завершает выполнение `If` инструкции.</span><span class="sxs-lookup"><span data-stu-id="be1ea-116">If `<test2>` is true, `<statement list 2>` runs, and PowerShell exits the `If` statement.</span></span> <span data-ttu-id="be1ea-117">Если оба `<test1>` `<test2>` аргумента и имеют значение false, `<statement list 3`> блок кода выполняется, а PowerShell завершает инструкцию if.</span><span class="sxs-lookup"><span data-stu-id="be1ea-117">If both `<test1>` and `<test2>` evaluate to false, the `<statement list 3`> code block runs, and PowerShell exits the If statement.</span></span>

<span data-ttu-id="be1ea-118">Можно использовать несколько операторов ElseIf для сцепления последовательности условных тестов.</span><span class="sxs-lookup"><span data-stu-id="be1ea-118">You can use multiple Elseif statements to chain a series of conditional tests.</span></span> <span data-ttu-id="be1ea-119">Таким образом, каждый тест выполняется только в том случае, если все предыдущие тесты имеют значение false.</span><span class="sxs-lookup"><span data-stu-id="be1ea-119">So, that each test is run only if all the previous tests are false.</span></span>
<span data-ttu-id="be1ea-120">Если необходимо создать `If` инструкцию, содержащую множество операторов ElseIf, рассмотрите возможность использования оператора switch.</span><span class="sxs-lookup"><span data-stu-id="be1ea-120">If you need to create an `If` statement that contains many Elseif statements, consider using a Switch statement instead.</span></span>

<span data-ttu-id="be1ea-121">Примеры:</span><span class="sxs-lookup"><span data-stu-id="be1ea-121">Examples:</span></span>

<span data-ttu-id="be1ea-122">Простейшая `If` инструкция содержит одну команду и не содержит ни операторов ElseIf, ни инструкций else.</span><span class="sxs-lookup"><span data-stu-id="be1ea-122">The simplest `If` statement contains a single command and does not contain any Elseif statements or any Else statements.</span></span> <span data-ttu-id="be1ea-123">В следующем примере показана простейшая форма `If` оператора:</span><span class="sxs-lookup"><span data-stu-id="be1ea-123">The following example shows the simplest form of the `If` statement:</span></span>

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
```

<span data-ttu-id="be1ea-124">В этом примере, если переменная $a больше 2, условие принимает значение true и выполняется список инструкций.</span><span class="sxs-lookup"><span data-stu-id="be1ea-124">In this example, if the $a variable is greater than 2, the condition evaluates to true, and the statement list runs.</span></span> <span data-ttu-id="be1ea-125">Однако если $a меньше или равно 2 или не является существующей переменной, `If` инструкция не отображает сообщение.</span><span class="sxs-lookup"><span data-stu-id="be1ea-125">However, if $a is less than or equal to 2 or is not an existing variable, the `If` statement does not display a message.</span></span>

<span data-ttu-id="be1ea-126">При добавлении инструкции else отображается сообщение, если $a меньше или равно 2.</span><span class="sxs-lookup"><span data-stu-id="be1ea-126">By adding an Else statement, a message is displayed when $a is less than or equal to 2.</span></span> <span data-ttu-id="be1ea-127">Как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="be1ea-127">As the next example shows:</span></span>

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
else {
    Write-Host ("The value $a is less than or equal to 2," +
        " is not created or is not initialized.")
}
```

<span data-ttu-id="be1ea-128">Для дальнейшего уточнения этого примера можно использовать Оператор ElseIf для вывода сообщения, если значение $a равно 2.</span><span class="sxs-lookup"><span data-stu-id="be1ea-128">To further refine this example, you can use the Elseif statement to display a message when the value of $a is equal to 2.</span></span> <span data-ttu-id="be1ea-129">Как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="be1ea-129">As the next example shows:</span></span>

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
elseif ($a -eq 2) {
    Write-Host "The value $a is equal to 2."
}
else {
    Write-Host ("The value $a is less than 2 or" +
        " was not created or initialized.")
}
```

### <a name="using-the-ternary-operator-syntax"></a><span data-ttu-id="be1ea-130">Использование синтаксиса оператора ternary</span><span class="sxs-lookup"><span data-stu-id="be1ea-130">Using the ternary operator syntax</span></span>

<span data-ttu-id="be1ea-131">В PowerShell 7,0 появился новый синтаксис с помощью оператора ternary.</span><span class="sxs-lookup"><span data-stu-id="be1ea-131">PowerShell 7.0 introduced a new syntax using the ternary operator.</span></span> <span data-ttu-id="be1ea-132">Он соответствует синтаксису оператора C# ternary:</span><span class="sxs-lookup"><span data-stu-id="be1ea-132">It follows the C# ternary operator syntax:</span></span>

```Syntax
<condition> ? <if-true> : <if-false>
```

<span data-ttu-id="be1ea-133">Оператор ternary ведет себя так же, как и упрощенная `if-else` инструкция.</span><span class="sxs-lookup"><span data-stu-id="be1ea-133">The ternary operator behaves like the simplified `if-else` statement.</span></span> <span data-ttu-id="be1ea-134">`<condition>`Выражение вычисляется, и результат преобразуется в логическое значение, чтобы определить, какую ветвь следует вычислить следующим образом:</span><span class="sxs-lookup"><span data-stu-id="be1ea-134">The `<condition>` expression is evaluated and the result is converted to a boolean to determine which branch should be evaluated next:</span></span>

- <span data-ttu-id="be1ea-135">Выражение `<if-true>` выполняется, если выражение `<condition>` имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="be1ea-135">The `<if-true>` expression is executed if the `<condition>` expression is true</span></span>
- <span data-ttu-id="be1ea-136">Выражение `<if-false>` выполняется, если выражение `<condition>` имеет значение false.</span><span class="sxs-lookup"><span data-stu-id="be1ea-136">The `<if-false>` expression is executed if the `<condition>` expression is false</span></span>

<span data-ttu-id="be1ea-137">Пример:</span><span class="sxs-lookup"><span data-stu-id="be1ea-137">For example:</span></span>

```powershell
$message = (Test-Path $path) ? "Path exists" : "Path not found"
```

<span data-ttu-id="be1ea-138">В этом примере `$message` при возврате возвращается значение «Path Exists» `Test-Path` `$true` .</span><span class="sxs-lookup"><span data-stu-id="be1ea-138">In this example, the value of `$message` is "Path exists" when `Test-Path` returns `$true`.</span></span> <span data-ttu-id="be1ea-139">При `Test-Path` возврате `$false` значение `$message` равно "путь не найден".</span><span class="sxs-lookup"><span data-stu-id="be1ea-139">When `Test-Path` returns `$false`, the value of `$message` is "Path not found".</span></span>

```powershell
$service = Get-Service BITS
$service.Status -eq 'Running' ? (Stop-Service $service) : (Start-Service $service)
```

<span data-ttu-id="be1ea-140">В этом примере, если служба запущена, она останавливается и, если ее состояние не **выполняется** , запускается.</span><span class="sxs-lookup"><span data-stu-id="be1ea-140">In this example, if the service is running, it is stopped, and if its status is not **Running** , it is started.</span></span>

## <a name="see-also"></a><span data-ttu-id="be1ea-141">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="be1ea-141">SEE ALSO</span></span>

[<span data-ttu-id="be1ea-142">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="be1ea-142">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="be1ea-143">about_Switch</span><span class="sxs-lookup"><span data-stu-id="be1ea-143">about_Switch</span></span>](about_Switch.md)
