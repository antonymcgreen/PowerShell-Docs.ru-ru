---
description: Описывает команду языка, которую можно использовать для выполнения инструкций на основе условного теста.
keywords: powershell,командлет
Locale: en-US
ms.date: 3/4/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_for?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_For
ms.openlocfilehash: 07037b73a5507bb0ef420ad39271be8832f7500b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231125"
---
# <a name="about-for"></a><span data-ttu-id="67146-104">О программе для</span><span class="sxs-lookup"><span data-stu-id="67146-104">About For</span></span>

## <a name="short-description"></a><span data-ttu-id="67146-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="67146-105">Short description</span></span>
<span data-ttu-id="67146-106">Описывает команду языка, которую можно использовать для выполнения инструкций на основе условного теста.</span><span class="sxs-lookup"><span data-stu-id="67146-106">Describes a language command you can use to run statements based on a conditional test.</span></span>

## <a name="long-description"></a><span data-ttu-id="67146-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="67146-107">Long description</span></span>

<span data-ttu-id="67146-108">`For`Оператор (также называемый `For` циклом) — это языковая конструкция, которую можно использовать для создания цикла, запускающего команды в блоке команд, пока заданное условие принимает значение `$true` .</span><span class="sxs-lookup"><span data-stu-id="67146-108">The `For` statement (also known as a `For` loop) is a language construct you can use to create a loop that runs commands in a command block while a specified condition evaluates to `$true`.</span></span>

<span data-ttu-id="67146-109">Обычно `For` цикл используется для прохода по массиву значений и для работы с подмножеством этих значений.</span><span class="sxs-lookup"><span data-stu-id="67146-109">A typical use of the `For` loop is to iterate an array of values and to operate on a subset of these values.</span></span> <span data-ttu-id="67146-110">В большинстве случаев, если необходимо выполнить итерацию всех значений в массиве, рассмотрите возможность использования `Foreach` оператора.</span><span class="sxs-lookup"><span data-stu-id="67146-110">In most cases, if you want to iterate all the values in an array, consider using a `Foreach` statement.</span></span>

### <a name="syntax"></a><span data-ttu-id="67146-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67146-111">Syntax</span></span>

<span data-ttu-id="67146-112">Ниже показан `For` синтаксис инструкции.</span><span class="sxs-lookup"><span data-stu-id="67146-112">The following shows the `For` statement syntax.</span></span>

```
for (<Init>; <Condition>; <Repeat>)
{
    <Statement list>
}
```

<span data-ttu-id="67146-113">Заполнитель **init** представляет одну или несколько команд, выполняемых перед началом цикла.</span><span class="sxs-lookup"><span data-stu-id="67146-113">The **Init** placeholder represents one or more commands that are run before the loop begins.</span></span> <span data-ttu-id="67146-114">Для создания и инициализации переменной с начальным значением обычно используется часть **init** инструкции.</span><span class="sxs-lookup"><span data-stu-id="67146-114">You typically use the **Init** portion of the statement to create and initialize a variable with a starting value.</span></span>

<span data-ttu-id="67146-115">Эта переменная будет использоваться в качестве основания для проверки условия в следующей части `For` инструкции.</span><span class="sxs-lookup"><span data-stu-id="67146-115">This variable will then be the basis for the condition to be tested in the next portion of the `For` statement.</span></span>

<span data-ttu-id="67146-116">Заполнитель **условия** представляет часть `For` инструкции, которая разрешается в `$true` `$false` **логическое** значение или.</span><span class="sxs-lookup"><span data-stu-id="67146-116">The **Condition** placeholder represents the portion of the `For` statement that resolves to a `$true` or `$false` **Boolean** value.</span></span> <span data-ttu-id="67146-117">PowerShell оценивает условие при каждом `For` выполнении цикла.</span><span class="sxs-lookup"><span data-stu-id="67146-117">PowerShell evaluates the condition each time the `For` loop runs.</span></span> <span data-ttu-id="67146-118">Если инструкция имеет значение `$true` , команды в блоке команд выполняются, а инструкция вычисляется снова.</span><span class="sxs-lookup"><span data-stu-id="67146-118">If the statement is `$true`, the commands in the command block run, and the statement is evaluated again.</span></span> <span data-ttu-id="67146-119">Если условие по-прежнему выполняется `$true` , команды в **списке инструкций** выполняются снова.</span><span class="sxs-lookup"><span data-stu-id="67146-119">If the condition is still `$true`, the commands in the **Statement list** run again.</span></span> <span data-ttu-id="67146-120">Цикл повторяется до тех пор, пока не будет выполнено условие `$false` .</span><span class="sxs-lookup"><span data-stu-id="67146-120">The loop is repeated until the condition becomes `$false`.</span></span>

<span data-ttu-id="67146-121">Заполнитель **Repeat** представляет одну или несколько команд, разделенных запятыми, которые выполняются каждый раз при повторении цикла.</span><span class="sxs-lookup"><span data-stu-id="67146-121">The **Repeat** placeholder represents one or more commands, separated by commas, that are executed each time the loop repeats.</span></span> <span data-ttu-id="67146-122">Как правило, он используется для изменения переменной, которая проверяется внутри **условия** инструкции.</span><span class="sxs-lookup"><span data-stu-id="67146-122">Typically, this is used to modify a variable that is tested inside the **Condition** part of the statement.</span></span>

<span data-ttu-id="67146-123">Заполнитель **списка инструкций** представляет набор из одной или нескольких команд, которые выполняются при каждом входе или повторении цикла.</span><span class="sxs-lookup"><span data-stu-id="67146-123">The **Statement list** placeholder represents a set of one or more commands that are run each time the loop is entered or repeated.</span></span> <span data-ttu-id="67146-124">Содержимое **списка инструкций** заключено в фигурные скобки.</span><span class="sxs-lookup"><span data-stu-id="67146-124">The contents of the **Statement list** are surrounded by braces.</span></span>

### <a name="support-for-multiple-operations"></a><span data-ttu-id="67146-125">Поддержка нескольких операций</span><span class="sxs-lookup"><span data-stu-id="67146-125">Support for multiple operations</span></span>

<span data-ttu-id="67146-126">Для нескольких операций присваивания в операторе **init** поддерживаются следующие синтаксисы:</span><span class="sxs-lookup"><span data-stu-id="67146-126">The following syntaxes are supported for multiple assignment operations in the **Init** statement:</span></span>

```powershell
# Comma separated assignment expressions enclosed in parenthesis.
for (($i = 0), ($j = 0); $i -lt 10; $i++)
{
    "`$i:$i"
    "`$j:$j"
}

# Sub-expression using the semicolon to separate statements.
for ($($i = 0;$j = 0); $i -lt 10; $i++)
{
    "`$i:$i"
    "`$j:$j"
}
```

<span data-ttu-id="67146-127">Для нескольких операций присваивания в операторе **Repeat** поддерживаются следующие синтаксисы:</span><span class="sxs-lookup"><span data-stu-id="67146-127">The following syntaxes are supported for multiple assignment operations in the **Repeat** statement:</span></span>

```powershell
# Comma separated assignment expressions.
for (($i = 0), ($j = 0); $i -lt 10; $i++)
{
    "`$i:$i"
    "`$j:$j"
}

# Comma separated assignment expressions enclosed in parenthesis.
for (($i = 0), ($j = 0); $i -lt 10; ($i++), ($j++))
{
    "`$i:$i"
    "`$j:$j"
}

# Sub-expression using the semicolon to separate statements.
for ($($i = 0;$j = 0); $i -lt 10; $($i++;$j++))
{
    "`$i:$i"
    "`$j:$j"
}
```

> [!NOTE]
> <span data-ttu-id="67146-128">Операции, отличные от pre или Increment, могут не работать со всеми синтаксисами.</span><span class="sxs-lookup"><span data-stu-id="67146-128">Operations other than pre or post increment may not work with all syntaxes.</span></span>

<span data-ttu-id="67146-129">Для нескольких **условий** используйте логические операторы, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="67146-129">For multiple **Conditions** use logical operators as demonstrated by the following example.</span></span>

```powershell
for (($i = 0), ($j = 0); $i -lt 10 -and $j -lt 10; $i++,$j++)
{
    "`$i:$i"
    "`$j:$j"
}
```

<span data-ttu-id="67146-130">Дополнительные сведения см. в разделе [about_Logical_Operators](about_Logical_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="67146-130">For more information, see [about_Logical_Operators](about_Logical_Operators.md).</span></span>

### <a name="examples"></a><span data-ttu-id="67146-131">Примеры</span><span class="sxs-lookup"><span data-stu-id="67146-131">Examples</span></span>

<span data-ttu-id="67146-132">Как минимум, `For` оператор требует круглых скобок, окружающих **init** , **Condition** и **Repeat** , а также команду, заключенную в фигурные скобки в части оператора **List** .</span><span class="sxs-lookup"><span data-stu-id="67146-132">At a minimum, a `For` statement requires the parenthesis surrounding the **Init** , **Condition** , and **Repeat** part of the statement and a command surrounded by braces in the **Statement list** part of the statement.</span></span>

<span data-ttu-id="67146-133">Обратите внимание, что будущие примеры намеренно демонстрируют код за пределами `For` оператора.</span><span class="sxs-lookup"><span data-stu-id="67146-133">Note that the upcoming examples intentionally show code outside the `For` statement.</span></span> <span data-ttu-id="67146-134">В последующих примерах код интегрируется в `For` инструкцию.</span><span class="sxs-lookup"><span data-stu-id="67146-134">In later examples, code is integrated into the `For` statement.</span></span>

<span data-ttu-id="67146-135">Например, следующая `For` инструкция непрерывно отображает значение `$i` переменной, пока вы не выйдете из команды вручную, нажав клавиши CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="67146-135">For example, the following `For` statement continually displays the value of the `$i` variable until you manually break out of the command by pressing CTRL+C.</span></span>

```powershell
$i = 1
for (;;)
{
    Write-Host $i
}
```

<span data-ttu-id="67146-136">В список инструкций можно добавить дополнительные команды, чтобы значение `$i` увеличивалось на 1 каждый раз при выполнении цикла, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="67146-136">You can add additional commands to the statement list so that the value of `$i` is incremented by 1 each time the loop is run, as the following example shows.</span></span>

```powershell
for (;;)
{
    $i++; Write-Host $i
}
```

<span data-ttu-id="67146-137">До выхода из команды нажатием клавиш CTRL + C эта инструкция будет постоянно отображать значение `$i` переменной, так как оно увеличивается на 1 при каждом выполнении цикла.</span><span class="sxs-lookup"><span data-stu-id="67146-137">Until you break out of the command by pressing CTRL+C, this statement will continually display the value of the `$i` variable as it is incremented by 1 each time the loop is run.</span></span>

<span data-ttu-id="67146-138">Вместо того, чтобы изменять значение переменной в списке инструкций `For` , можно использовать **повторную** часть `For` инструкции, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="67146-138">Rather than change the value of the variable in the statement list part of the `For` statement, you can use the **Repeat** portion of the `For` statement instead, as follows.</span></span>

```powershell
$i=1
for (;;$i++)
{
    Write-Host $i
}
```

<span data-ttu-id="67146-139">Эта инструкция по-прежнему будет повторяться бессрочно, пока вы не завершите выполнение команды, нажав клавиши CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="67146-139">This statement will still repeat indefinitely until you break out of the command by pressing CTRL+C.</span></span>

<span data-ttu-id="67146-140">Можно завершить цикл, `For` используя *условие*.</span><span class="sxs-lookup"><span data-stu-id="67146-140">You can terminate the `For` loop using a *condition*.</span></span> <span data-ttu-id="67146-141">Условие можно разместить с помощью части **Condition** `For` инструкции.</span><span class="sxs-lookup"><span data-stu-id="67146-141">You can place a condition using the **Condition** portion of the `For` statement.</span></span> <span data-ttu-id="67146-142">`For`Цикл завершается, когда условие принимает значение `$false` .</span><span class="sxs-lookup"><span data-stu-id="67146-142">The `For` loop terminates when the condition evaluates to `$false`.</span></span>

<span data-ttu-id="67146-143">В следующем примере `For` цикл выполняется, пока значение `$i` меньше или равно 10.</span><span class="sxs-lookup"><span data-stu-id="67146-143">In the following example, the `For` loop runs while the value of `$i` is less than or equal to 10.</span></span>

```powershell
$i=1
for(;$i -le 10;$i++)
{
    Write-Host $i
}
```

<span data-ttu-id="67146-144">Вместо создания и инициализации переменной за пределами `For` инструкции эту задачу можно выполнить внутри `For` цикла, используя часть **init** `For` инструкции.</span><span class="sxs-lookup"><span data-stu-id="67146-144">Instead of creating and initializing the variable outside the `For` statement, you can perform this task inside the `For` loop by using the **Init** portion of the `For` statement.</span></span>

```powershell
for($i=1; $i -le 10; $i++){Write-Host $i}
```

<span data-ttu-id="67146-145">Вместо точек с запятой можно использовать символы возврата каретки, чтобы ограничить количество частей инструкции **init** , **Condition** и **Repeat** `For` .</span><span class="sxs-lookup"><span data-stu-id="67146-145">You can use carriage returns instead of semicolons to delimit the **Init** , **Condition** , and **Repeat** portions of the `For` statement.</span></span> <span data-ttu-id="67146-146">В следующем примере показан объект `For` , который использует этот альтернативный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="67146-146">The following example shows a `For` that uses this alternative syntax.</span></span>

```powershell
for ($i = 0
  $i -lt 10
  $i++){
  $i
}
```

<span data-ttu-id="67146-147">Эта альтернативная форма `For` инструкции работает в файлах скриптов PowerShell и в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67146-147">This alternative form of the `For` statement works in PowerShell script files and at the PowerShell command prompt.</span></span> <span data-ttu-id="67146-148">Однако `For` при вводе интерактивных команд в командной строке проще использовать синтаксис инструкции с точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="67146-148">However, it is easier to use the `For` statement syntax with semicolons when you enter interactive commands at the command prompt.</span></span>

<span data-ttu-id="67146-149">`For`Цикл является более гибким, чем `Foreach` цикл, поскольку он позволяет увеличивать значения в массиве или коллекции с помощью шаблонов.</span><span class="sxs-lookup"><span data-stu-id="67146-149">The `For` loop is more flexible than the `Foreach` loop because it allows you to increment values in an array or collection by using patterns.</span></span> <span data-ttu-id="67146-150">В следующем примере `$i` переменная увеличивается на 2 в **повторяющейся** части `For` инструкции.</span><span class="sxs-lookup"><span data-stu-id="67146-150">In the following example, the `$i` variable is incremented by 2 in the **Repeat** portion of the `For` statement.</span></span>

```powershell
for ($i = 0; $i -le 20; $i += 2)
{
    Write-Host $i
}
```

<span data-ttu-id="67146-151">`For`Цикл также можно записать на одной строке, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="67146-151">The `For` loop can also be written on one line as in the following example.</span></span>

```powershell
for ($i = 0; $i -lt 10; $i++) { Write-Host $i }
```

## <a name="see-also"></a><span data-ttu-id="67146-152">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="67146-152">SEE ALSO</span></span>

[<span data-ttu-id="67146-153">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="67146-153">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="67146-154">about_Foreach</span><span class="sxs-lookup"><span data-stu-id="67146-154">about_Foreach</span></span>](about_Foreach.md)

