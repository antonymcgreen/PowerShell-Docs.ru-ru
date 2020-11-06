---
description: Описание операторов, поддерживаемых PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 10/28/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_operators?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Operators
ms.openlocfilehash: a8c9c60c9c1513e1ee4ce71c8c880e20bf1df7b3
ms.sourcegitcommit: c1e4739f5d52282fb05a8cff92b0f5d10e2edac1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "93233305"
---
# <a name="about-operators"></a><span data-ttu-id="ae6e5-104">Об операторах</span><span class="sxs-lookup"><span data-stu-id="ae6e5-104">About Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="ae6e5-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="ae6e5-105">Short description</span></span>
<span data-ttu-id="ae6e5-106">Описание операторов, поддерживаемых PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-106">Describes the operators that are supported by PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="ae6e5-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="ae6e5-107">Long description</span></span>

<span data-ttu-id="ae6e5-108">Оператор — это элемент языка, который можно использовать в команде или выражении.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-108">An operator is a language element that you can use in a command or expression.</span></span>
<span data-ttu-id="ae6e5-109">PowerShell поддерживает несколько типов операторов, помогающих управлять значениями.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-109">PowerShell supports several types of operators to help you manipulate values.</span></span>

### <a name="arithmetic-operators"></a><span data-ttu-id="ae6e5-110">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="ae6e5-110">Arithmetic Operators</span></span>

<span data-ttu-id="ae6e5-111">Используйте арифметические операторы ( `+` , `-` ,, `*` `/` , `%` ) для вычисления значений в команде или выражении.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-111">Use arithmetic operators (`+`, `-`, `*`, `/`, `%`) to calculate values in a command or expression.</span></span> <span data-ttu-id="ae6e5-112">С помощью этих операторов можно добавлять, вычитать, умножать или делить значения, а также вычислять остаток (остаток от деления) операции деления.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-112">With these operators, you can add, subtract, multiply, or divide values, and calculate the remainder (modulus) of a division operation.</span></span>

<span data-ttu-id="ae6e5-113">Оператор сложения объединяет элементы.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-113">The addition operator concatenates elements.</span></span> <span data-ttu-id="ae6e5-114">Оператор умножения возвращает указанное количество копий каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-114">The multiplication operator returns the specified number of copies of each element.</span></span> <span data-ttu-id="ae6e5-115">Арифметические операторы можно использовать для любого типа .NET, который их реализует, например: `Int` ,,, `String` `DateTime` `Hashtable` и.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-115">You can use arithmetic operators on any .NET type that implements them, such as: `Int`, `String`, `DateTime`, `Hashtable`, and Arrays.</span></span>

<span data-ttu-id="ae6e5-116">Битовые операторы ( `-band` , `-bor` , `-bxor` , `-bnot` , `-shl` , `-shr` ) управляют битовыми шаблонами в значениях.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-116">Bitwise operators (`-band`, `-bor`, `-bxor`, `-bnot`, `-shl`, `-shr`) manipulate the bit patterns in values.</span></span>

<span data-ttu-id="ae6e5-117">Дополнительные сведения см. в разделе [about_Arithmetic_Operators](about_Arithmetic_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="ae6e5-117">For more information, see [about_Arithmetic_Operators](about_Arithmetic_Operators.md).</span></span>

### <a name="assignment-operators"></a><span data-ttu-id="ae6e5-118">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="ae6e5-118">Assignment Operators</span></span>

<span data-ttu-id="ae6e5-119">Операторы присваивания (,,,, `=` `+=` `-=` `*=` `/=` , `%=` ) используются для назначения, изменения или добавления значений переменным.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-119">Use assignment operators (`=`, `+=`, `-=`, `*=`, `/=`, `%=`) to assign, change, or append values to variables.</span></span> <span data-ttu-id="ae6e5-120">Арифметические операторы можно объединять с оператором присваивания, чтобы присвоить результат арифметической операции переменной.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-120">You can combine arithmetic operators with assignment to assign the result of the arithmetic operation to a variable.</span></span>

<span data-ttu-id="ae6e5-121">Дополнительные сведения см. в разделе [about_Assignment_Operators](about_Assignment_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="ae6e5-121">For more information, see [about_Assignment_Operators](about_Assignment_Operators.md).</span></span>

### <a name="comparison-operators"></a><span data-ttu-id="ae6e5-122">Операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="ae6e5-122">Comparison Operators</span></span>

<span data-ttu-id="ae6e5-123">Используйте операторы сравнения ( `-eq` , `-ne` ,,, `-gt` `-lt` `-le` , `-ge` ) для сравнения значений и условий теста.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-123">Use comparison operators (`-eq`, `-ne`, `-gt`, `-lt`, `-le`, `-ge`) to compare values and test conditions.</span></span> <span data-ttu-id="ae6e5-124">Например, можно сравнить два строковых значения, чтобы определить, равны ли они.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-124">For example, you can compare two string values to determine whether they are equal.</span></span>

<span data-ttu-id="ae6e5-125">Операторы сравнения также включают операторы, которые находят или заменяют закономерности в тексте.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-125">The comparison operators also include operators that find or replace patterns in text.</span></span> <span data-ttu-id="ae6e5-126">Операторы ( `-match` , `-notmatch` , `-replace` ) используют регулярные выражения, а ( `-like` , `-notlike` ) используют подстановочные знаки `*` .</span><span class="sxs-lookup"><span data-stu-id="ae6e5-126">The (`-match`, `-notmatch`, `-replace`) operators use regular expressions, and (`-like`, `-notlike`) use wildcards `*`.</span></span>

<span data-ttu-id="ae6e5-127">Операторы сравнения вложений определяют, отображается ли тестовое значение в наборе ссылок ( `-in` ,, `-notin` `-contains` , `-notcontains` ).</span><span class="sxs-lookup"><span data-stu-id="ae6e5-127">Containment comparison operators determine whether a test value appears in a reference set (`-in`, `-notin`, `-contains`, `-notcontains`).</span></span>

<span data-ttu-id="ae6e5-128">Операторы сравнения типов ( `-is` , `-isnot` ) определяют, относится ли объект к данному типу.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-128">Type comparison operators (`-is`, `-isnot`) determine whether an object is of a given type.</span></span>

<span data-ttu-id="ae6e5-129">Дополнительные сведения см. в разделе [about_Comparison_Operators](about_Comparison_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="ae6e5-129">For more information, see [about_Comparison_Operators](about_Comparison_Operators.md).</span></span>

### <a name="logical-operators"></a><span data-ttu-id="ae6e5-130">Логические операторы</span><span class="sxs-lookup"><span data-stu-id="ae6e5-130">Logical Operators</span></span>

<span data-ttu-id="ae6e5-131">Используйте логические операторы ( `-and` , `-or` , `-xor` , `-not` , `!` ) для подключения условных операторов к одному сложному условию.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-131">Use logical operators (`-and`, `-or`, `-xor`, `-not`, `!`) to connect conditional statements into a single complex conditional.</span></span> <span data-ttu-id="ae6e5-132">Например, логический оператор можно использовать `-and` для создания фильтра объектов с двумя различными условиями.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-132">For example, you can use a logical `-and` operator to create an object filter with two different conditions.</span></span>

<span data-ttu-id="ae6e5-133">Дополнительные сведения см. в разделе [about_Logical_Operators](about_logical_operators.md).</span><span class="sxs-lookup"><span data-stu-id="ae6e5-133">For more information, see [about_Logical_Operators](about_logical_operators.md).</span></span>

### <a name="redirection-operators"></a><span data-ttu-id="ae6e5-134">Операторы перенаправления</span><span class="sxs-lookup"><span data-stu-id="ae6e5-134">Redirection Operators</span></span>

<span data-ttu-id="ae6e5-135">Используйте операторы перенаправления ( `>` ,, `>>` `2>` , `2>>` и `2>&1` ) для отправки выходных данных команды или выражения в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-135">Use redirection operators (`>`, `>>`, `2>`, `2>>`, and `2>&1`) to send the output of a command or expression to a text file.</span></span> <span data-ttu-id="ae6e5-136">Операторы перенаправления работают как `Out-File` командлет (без параметров), но они также позволяют перенаправлять вывод ошибок в указанные файлы.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-136">The redirection operators work like the `Out-File` cmdlet (without parameters) but they also let you redirect error output to specified files.</span></span> <span data-ttu-id="ae6e5-137">Можно также использовать `Tee-Object` командлет для перенаправления выходных данных.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-137">You can also use the `Tee-Object` cmdlet to redirect output.</span></span>

<span data-ttu-id="ae6e5-138">Дополнительные сведения см. в разделе [about_Redirection](about_Redirection.md)</span><span class="sxs-lookup"><span data-stu-id="ae6e5-138">For more information, see [about_Redirection](about_Redirection.md)</span></span>

### <a name="split-and-join-operators"></a><span data-ttu-id="ae6e5-139">Операторы Split и Join</span><span class="sxs-lookup"><span data-stu-id="ae6e5-139">Split and Join Operators</span></span>

<span data-ttu-id="ae6e5-140">`-split`Операторы and `-join` делят и объединяют подстроки.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-140">The `-split` and `-join` operators divide and combine substrings.</span></span> <span data-ttu-id="ae6e5-141">`-split`Оператор разделяет строку на подстроки.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-141">The `-split` operator splits a string into substrings.</span></span> <span data-ttu-id="ae6e5-142">`-join`Оператор объединяет несколько строк в одну строку.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-142">The `-join` operator concatenates multiple strings into a single string.</span></span>

<span data-ttu-id="ae6e5-143">Дополнительные сведения см. в разделе [about_Split](about_Split.md) и [about_Join](about_Join.md).</span><span class="sxs-lookup"><span data-stu-id="ae6e5-143">For more information, see [about_Split](about_Split.md) and [about_Join](about_Join.md).</span></span>

### <a name="type-operators"></a><span data-ttu-id="ae6e5-144">Операторы работы с типами</span><span class="sxs-lookup"><span data-stu-id="ae6e5-144">Type Operators</span></span>

<span data-ttu-id="ae6e5-145">Используйте операторы типа ( `-is` , `-isnot` ,), `-as` чтобы найти или изменить тип .NET Framework объекта.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-145">Use the type operators (`-is`, `-isnot`, `-as`) to find or change the .NET Framework type of an object.</span></span>

<span data-ttu-id="ae6e5-146">Дополнительные сведения см. в разделе [about_Type_Operators](about_Type_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="ae6e5-146">For more information, see [about_Type_Operators](about_Type_Operators.md).</span></span>

### <a name="unary-operators"></a><span data-ttu-id="ae6e5-147">Унарные операторы</span><span class="sxs-lookup"><span data-stu-id="ae6e5-147">Unary Operators</span></span>

<span data-ttu-id="ae6e5-148">Используйте унарные операторы для увеличения или уменьшения числа переменных или свойств объектов, а также для присвоения целочисленных значений положительным или отрицательным числам.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-148">Use unary operators to increment or decrement variables or object properties and to set integers to positive or negative numbers.</span></span> <span data-ttu-id="ae6e5-149">Например, чтобы увеличить переменную `$a` с `9` на `10` , введите `$a++` .</span><span class="sxs-lookup"><span data-stu-id="ae6e5-149">For example, to increment the variable `$a` from `9` to `10`, you type `$a++`.</span></span>

### <a name="special-operators"></a><span data-ttu-id="ae6e5-150">Специальные операторы</span><span class="sxs-lookup"><span data-stu-id="ae6e5-150">Special Operators</span></span>

<span data-ttu-id="ae6e5-151">Специальные операторы имеют особые варианты использования, которые не помещаются в любую другую группу операторов.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-151">Special operators have specific use-cases that do not fit into any other operator group.</span></span> <span data-ttu-id="ae6e5-152">Например, Специальные операторы позволяют выполнять команды, изменять тип данных значения или извлекать элементы из массива.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-152">For example, special operators allow you to run commands, change a value's data type, or retrieve elements from an array.</span></span>

#### <a name="grouping-operator--"></a><span data-ttu-id="ae6e5-153">Оператор группирования `( )`</span><span class="sxs-lookup"><span data-stu-id="ae6e5-153">Grouping operator `( )`</span></span>

<span data-ttu-id="ae6e5-154">Как и в других языках, `(...)` служит для переопределения приоритета операторов в выражениях.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-154">As in other languages, `(...)` serves to override operator precedence in expressions.</span></span> <span data-ttu-id="ae6e5-155">Пример: `(1 + 2) / 3`</span><span class="sxs-lookup"><span data-stu-id="ae6e5-155">For example: `(1 + 2) / 3`</span></span>

<span data-ttu-id="ae6e5-156">Однако в PowerShell существуют дополнительные поведения.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-156">However, in PowerShell, there are additional behaviors.</span></span>

- <span data-ttu-id="ae6e5-157">`(...)` позволяет разрешить выходные данные _команды_ участвовать в выражении.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-157">`(...)` allows you to let output from a _command_ participate in an expression.</span></span> <span data-ttu-id="ae6e5-158">Пример:</span><span class="sxs-lookup"><span data-stu-id="ae6e5-158">For example:</span></span>

  ```powershell
  PS> (Get-Item *.txt).Count -gt 10
  True
  ```

- <span data-ttu-id="ae6e5-159">При использовании в качестве первого сегмента конвейера, заключение команды или выражения в круглые скобки неизменно приводит к _перечислению_ результата выражения.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-159">When used as the first segment of a pipeline, wrapping a command or expression in parentheses invariably causes _enumeration_ of the expression result.</span></span> <span data-ttu-id="ae6e5-160">Если скобки заключают _команду_ в оболочку, она выполняется до завершения со всеми данными, _собранными в памяти_ до отправки результатов через конвейер.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-160">If the parentheses wrap a _command_ , it is run to completion with all output _collected in memory_ before the results are sent through the pipeline.</span></span>

> [!NOTE]
> <span data-ttu-id="ae6e5-161">Заключение команды в круглые скобки приводит к тому, что автоматическая переменная `$?` устанавливается в значение `$true` , даже если сама вложенная команда имеет значение `$?` `$false` .</span><span class="sxs-lookup"><span data-stu-id="ae6e5-161">Wrapping a command in parentheses causes the automatic variable `$?` to be set to `$true`, even when the enclosed command itself set `$?` to `$false`.</span></span>
> <span data-ttu-id="ae6e5-162">Например, `(Get-Item /Nosuch); $?` неожиданно возвращает **значение true**.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-162">For example, `(Get-Item /Nosuch); $?` unexpectedly yields **True**.</span></span> <span data-ttu-id="ae6e5-163">Дополнительные сведения о `$?` см. в разделе [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="ae6e5-163">For more information about `$?`, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

#### <a name="subexpression-operator--"></a><span data-ttu-id="ae6e5-164">Оператор части выражения `$( )`</span><span class="sxs-lookup"><span data-stu-id="ae6e5-164">Subexpression operator `$( )`</span></span>

<span data-ttu-id="ae6e5-165">Возвращает результат одной или нескольких инструкций.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-165">Returns the result of one or more statements.</span></span> <span data-ttu-id="ae6e5-166">Для одного результата возвращает скалярное значение.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-166">For a single result, returns a scalar.</span></span> <span data-ttu-id="ae6e5-167">Для нескольких результатов возвращает массив.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-167">For multiple results, returns an array.</span></span> <span data-ttu-id="ae6e5-168">Используйте этот параметр, если требуется использовать выражение в другом выражении.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-168">Use this when you want to use an expression within another expression.</span></span> <span data-ttu-id="ae6e5-169">Например, чтобы внедрить результаты команды в строковое выражение.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-169">For example, to embed the results of command in a string expression.</span></span>

```powershell
PS> "Today is $(Get-Date)"
Today is 12/02/2019 13:15:20

PS> "Folder list: $((dir c:\ -dir).Name -join ', ')"
Folder list: Program Files, Program Files (x86), Users, Windows
```

#### <a name="array-subexpression-operator--"></a><span data-ttu-id="ae6e5-170">Оператор части выражения массива `@( )`</span><span class="sxs-lookup"><span data-stu-id="ae6e5-170">Array subexpression operator `@( )`</span></span>

<span data-ttu-id="ae6e5-171">Возвращает результат одной или нескольких инструкций в виде массива.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-171">Returns the result of one or more statements as an array.</span></span> <span data-ttu-id="ae6e5-172">Если имеется только один элемент, массив содержит только один элемент.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-172">If there is only one item, the array has only one member.</span></span>

```powershell
@(Get-CimInstance win32_logicalDisk)
```

#### <a name="call-operator-"></a><span data-ttu-id="ae6e5-173">Оператор Call `&`</span><span class="sxs-lookup"><span data-stu-id="ae6e5-173">Call operator `&`</span></span>

<span data-ttu-id="ae6e5-174">Выполняет команду, сценарий или блок скрипта.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-174">Runs a command, script, or script block.</span></span> <span data-ttu-id="ae6e5-175">Оператор Call, также известный как «оператор вызова», позволяет выполнять команды, которые хранятся в переменных и представляются строками или блоками сценариев.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-175">The call operator, also known as the "invocation operator", lets you run commands that are stored in variables and represented by strings or script blocks.</span></span> <span data-ttu-id="ae6e5-176">Оператор Call выполняется в дочерней области.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-176">The call operator executes in a child scope.</span></span> <span data-ttu-id="ae6e5-177">Дополнительные сведения об областях см. в разделе [about_Scopes](about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="ae6e5-177">For more about scopes, see [about_Scopes](about_Scopes.md).</span></span>

<span data-ttu-id="ae6e5-178">В этом примере команда сохраняется в строке и выполняется с помощью оператора Call.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-178">This example stores a command in a string and executes it using the call operator.</span></span>

```
PS> $c = "get-executionpolicy"
PS> $c
get-executionpolicy
PS> & $c
AllSigned
```

<span data-ttu-id="ae6e5-179">Оператор Call не выполняет синтаксический анализ строк.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-179">The call operator does not parse strings.</span></span> <span data-ttu-id="ae6e5-180">Это означает, что нельзя использовать параметры команды в строке при использовании оператора Call.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-180">This means that you cannot use command parameters within a string when you use the call operator.</span></span>

```
PS> $c = "Get-Service -Name Spooler"
PS> $c
Get-Service -Name Spooler
PS> & $c
& : The term 'Get-Service -Name Spooler' is not recognized as the name of a
cmdlet, function, script file, or operable program. Check the spelling of
the name, or if a path was included, verify that the path is correct and
try again.
At line:1 char:2
+ & $c
+  ~~
    + CategoryInfo          : ObjectNotFound: (Get-Service -Name Spooler:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

<span data-ttu-id="ae6e5-181">Командлет [Invoke-Expression](xref:Microsoft.PowerShell.Utility.Invoke-Expression) может выполнять код, который вызывает ошибки синтаксического анализа при использовании оператора Call.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-181">The [Invoke-Expression](xref:Microsoft.PowerShell.Utility.Invoke-Expression) cmdlet can execute code that causes parsing errors when using the call operator.</span></span>

```
PS> & "1+1"
& : The term '1+1' is not recognized as the name of a cmdlet, function, script
file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At line:1 char:2
+ & "1+1"
+  ~~~~~
    + CategoryInfo          : ObjectNotFound: (1+1:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
PS> Invoke-Expression "1+1"
2
```

<span data-ttu-id="ae6e5-182">Оператор Call можно использовать для выполнения скриптов, использующих их имена файлов.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-182">You can use the call operator to execute scripts using their filenames.</span></span> <span data-ttu-id="ae6e5-183">В следующем примере показано имя файла скрипта, содержащего пробелы.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-183">The example below shows a script filename that contains spaces.</span></span> <span data-ttu-id="ae6e5-184">При попытке выполнить скрипт PowerShell вместо этого отображает содержимое строки в кавычках, содержащей имя файла.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-184">When you try to execute the script, PowerShell instead displays the contents of the quoted string containing the filename.</span></span> <span data-ttu-id="ae6e5-185">Оператор Call позволяет выполнить содержимое строки, содержащей имя файла.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-185">The call operator allows you to execute the contents of the string containing the filename.</span></span>

```
PS C:\Scripts> Get-ChildItem

    Directory: C:\Scripts


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        8/28/2018   1:36 PM             58 script name with spaces.ps1

PS C:\Scripts> ".\script name with spaces.ps1"
.\script name with spaces.ps1
PS C:\Scripts> & ".\script name with spaces.ps1"
Hello World!
```

<span data-ttu-id="ae6e5-186">Дополнительные сведения о блоках скриптов см. в разделе [about_Script_Blocks](about_Script_Blocks.md).</span><span class="sxs-lookup"><span data-stu-id="ae6e5-186">For more about script blocks, see [about_Script_Blocks](about_Script_Blocks.md).</span></span>

#### <a name="cast-operator--"></a><span data-ttu-id="ae6e5-187">Оператор CAST `[ ]`</span><span class="sxs-lookup"><span data-stu-id="ae6e5-187">Cast operator `[ ]`</span></span>

<span data-ttu-id="ae6e5-188">Преобразует или ограничивает объекты указанным типом.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-188">Converts or limits objects to the specified type.</span></span> <span data-ttu-id="ae6e5-189">Если не удается преобразовать объекты, PowerShell выдает ошибку.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-189">If the objects cannot be converted, PowerShell generates an error.</span></span>

```powershell
[DateTime]"2/20/88" - [DateTime]"1/20/88"
[Int] (7/2)
[String] 1 + 0
[Int] '1' + 0
```

<span data-ttu-id="ae6e5-190">Приведение также можно выполнить, если переменная назначена с помощью [нотации приведения](about_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="ae6e5-190">A cast can also be performed when a variable is assigned to using [cast notation](about_Variables.md).</span></span>

#### <a name="comma-operator-"></a><span data-ttu-id="ae6e5-191">Запятая, оператор `,`</span><span class="sxs-lookup"><span data-stu-id="ae6e5-191">Comma operator `,`</span></span>

<span data-ttu-id="ae6e5-192">Как бинарный оператор, запятая создает массив или добавляет к создаваемому массиву.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-192">As a binary operator, the comma creates an array or appends to the array being created.</span></span> <span data-ttu-id="ae6e5-193">В режиме выражения в качестве унарного оператора запятая создает массив только с одним элементом.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-193">In expression mode, as a unary operator, the comma creates an array with just one member.</span></span> <span data-ttu-id="ae6e5-194">Поместите запятую перед элементом.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-194">Place the comma before the member.</span></span>

```powershell
$myArray = 1,2,3
$SingleArray = ,1
Write-Output (,1)
```

<span data-ttu-id="ae6e5-195">Поскольку `Write-Object` предполагает аргумент, выражение должно быть заключено в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-195">Since `Write-Object` expects an argument, you must put the expression in parentheses.</span></span>

#### <a name="dot-sourcing-operator-"></a><span data-ttu-id="ae6e5-196">Оператор "точка с точкой" `.`</span><span class="sxs-lookup"><span data-stu-id="ae6e5-196">Dot sourcing operator `.`</span></span>

<span data-ttu-id="ae6e5-197">Выполняет скрипт в текущей области, чтобы все функции, псевдонимы и переменные, создаваемые сценарием, добавлялись в текущую область, переопределяя существующие.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-197">Runs a script in the current scope so that any functions, aliases, and variables that the script creates are added to the current scope, overriding existing ones.</span></span> <span data-ttu-id="ae6e5-198">Параметры, объявленные сценарием, становятся переменными.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-198">Parameters declared by the script become variables.</span></span> <span data-ttu-id="ae6e5-199">Параметры, для которых не было указано значение, становятся переменными без значения.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-199">Parameters for which no value has been given become variables with no value.</span></span> <span data-ttu-id="ae6e5-200">Однако автоматическая переменная `$args` сохраняется.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-200">However, the automatic variable `$args` is preserved.</span></span>

```powershell
. c:\scripts\sample.ps1 1 2 -Also:3
```

> [!NOTE]
> <span data-ttu-id="ae6e5-201">За оператором «точка» следует пробел.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-201">The dot sourcing operator is followed by a space.</span></span> <span data-ttu-id="ae6e5-202">Используйте пробел, чтобы отличить точку от символа точки ( `.` ), который представляет текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-202">Use the space to distinguish the dot from the dot (`.`) symbol that represents the current directory.</span></span>
>
> <span data-ttu-id="ae6e5-203">В следующем примере сценарий Sample.ps1 в текущем каталоге выполняется в текущей области.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-203">In the following example, the Sample.ps1 script in the current directory is run in the current scope.</span></span>
>
> ```powershell
> . .\sample.ps1
> ```

#### <a name="format-operator--f"></a><span data-ttu-id="ae6e5-204">Format, оператор `-f`</span><span class="sxs-lookup"><span data-stu-id="ae6e5-204">Format operator `-f`</span></span>

<span data-ttu-id="ae6e5-205">Форматирует строки с помощью метода Format строковых объектов.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-205">Formats strings by using the format method of string objects.</span></span> <span data-ttu-id="ae6e5-206">Введите строку формата слева от оператора и объекты, которые должны быть отформатированы с правой стороны оператора.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-206">Enter the format string on the left side of the operator and the objects to be formatted on the right side of the operator.</span></span>

```powershell
"{0} {1,-10} {2:N}" -f 1,"hello",[math]::pi
```

```output
1 hello      3.14
```

<span data-ttu-id="ae6e5-207">Если необходимо, чтобы фигурные скобки ( `{}` ) в форматируемой строке были заключены в квадратные скобки, их можно поэкранировать.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-207">If you need to keep the curly braces (`{}`) in the formatted string, you can escape them by doubling the curly braces.</span></span>

```powershell
"{0} vs. {{0}}" -f 'foo'
```

```Output
foo vs. {0}
```

<span data-ttu-id="ae6e5-208">Дополнительные сведения см. в разделе метод [String. Format](/dotnet/api/system.string.format) и [составное форматирование](/dotnet/standard/base-types/composite-formatting).</span><span class="sxs-lookup"><span data-stu-id="ae6e5-208">For more information, see the [String.Format](/dotnet/api/system.string.format) method and [Composite Formatting](/dotnet/standard/base-types/composite-formatting).</span></span>

#### <a name="index-operator--"></a><span data-ttu-id="ae6e5-209">Оператор индекса `[ ]`</span><span class="sxs-lookup"><span data-stu-id="ae6e5-209">Index operator `[ ]`</span></span>

<span data-ttu-id="ae6e5-210">Выбирает объекты из индексированных коллекций, таких как массивы и хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-210">Selects objects from indexed collections, such as arrays and hash tables.</span></span> <span data-ttu-id="ae6e5-211">Индексы массива отсчитываются от нуля, поэтому первый объект индексируется как `[0]` .</span><span class="sxs-lookup"><span data-stu-id="ae6e5-211">Array indexes are zero-based, so the first object is indexed as `[0]`.</span></span> <span data-ttu-id="ae6e5-212">Для массивов (только) для получения последних значений можно также использовать отрицательные индексы.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-212">For arrays (only), you can also use negative indexes to get the last values.</span></span> <span data-ttu-id="ae6e5-213">Хэш-таблицы индексируются по значению ключа.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-213">Hash tables are indexed by key value.</span></span>

```
PS> $a = 1, 2, 3
PS> $a[0]
1
PS> $a[-1]
3
```

```powershell
(Get-HotFix | Sort-Object installedOn)[-1]
```

```powershell
$h = @{key="value"; name="PowerShell"; version="2.0"}
$h["name"]
```

```output
PowerShell
```

```powershell
$x = [xml]"<doc><intro>Once upon a time...</intro></doc>"
$x["doc"]
```

```output
intro
-----
Once upon a time...
```

#### <a name="pipeline-operator-"></a><span data-ttu-id="ae6e5-214">Конвейерный оператор `|`</span><span class="sxs-lookup"><span data-stu-id="ae6e5-214">Pipeline operator `|`</span></span>

<span data-ttu-id="ae6e5-215">Отправляет ("pipe") выходные данные команды, предшествующей ей, с помощью команды, следующей за ней.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-215">Sends ("pipes") the output of the command that precedes it to the command that follows it.</span></span> <span data-ttu-id="ae6e5-216">Если выходные данные содержат более одного объекта ("Коллекция"), оператор конвейера посылает объекты по одному за раз.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-216">When the output includes more than one object (a "collection"), the pipeline operator sends the objects one at a time.</span></span>

```powershell
Get-Process | Get-Member
Get-Service | Where-Object {$_.StartType -eq 'Automatic'}
```

#### <a name="range-operator-"></a><span data-ttu-id="ae6e5-217">Оператор Range `..`</span><span class="sxs-lookup"><span data-stu-id="ae6e5-217">Range operator `..`</span></span>

<span data-ttu-id="ae6e5-218">Представляет последовательные целые числа в массиве целых чисел с учетом верхней и нижней границ.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-218">Represents the sequential integers in an integer array, given an upper, and lower boundary.</span></span>

```powershell
1..10
foreach ($a in 1..$max) {Write-Host $a}
```

<span data-ttu-id="ae6e5-219">Можно также создавать диапазоны в обратных последовательностях.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-219">You can also create ranges in reverse order.</span></span>

```powershell
10..1
5..-5 | ForEach-Object {Write-Output $_}
```

#### <a name="member-access-operator-"></a><span data-ttu-id="ae6e5-220">Оператор доступа к членам `.`</span><span class="sxs-lookup"><span data-stu-id="ae6e5-220">Member access operator `.`</span></span>

<span data-ttu-id="ae6e5-221">Обращается к свойствам и методам объекта.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-221">Accesses the properties and methods of an object.</span></span> <span data-ttu-id="ae6e5-222">Имя члена может быть выражением.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-222">The member name may be an expression.</span></span>

```powershell
$myProcess.peakWorkingSet
(Get-Process PowerShell).kill()
'OS', 'Platform' | Foreach-Object { $PSVersionTable. $_ }
```

#### <a name="static-member-operator-"></a><span data-ttu-id="ae6e5-223">Статический оператор члена `::`</span><span class="sxs-lookup"><span data-stu-id="ae6e5-223">Static member operator `::`</span></span>

<span data-ttu-id="ae6e5-224">Вызывает статические свойства и методы класса .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-224">Calls the static properties and methods of a .NET Framework class.</span></span> <span data-ttu-id="ae6e5-225">Чтобы найти статические свойства и методы объекта, используйте статический параметр `Get-Member` командлета.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-225">To find the static properties and methods of an object, use the Static parameter of the `Get-Member` cmdlet.</span></span>  <span data-ttu-id="ae6e5-226">Имя члена может быть выражением.</span><span class="sxs-lookup"><span data-stu-id="ae6e5-226">The member name may be an expression.</span></span>

```powershell
[datetime]::Now
'MinValue', 'MaxValue' | Foreach-Object { [int]:: $_ }
```

## <a name="see-also"></a><span data-ttu-id="ae6e5-227">См. также статью</span><span class="sxs-lookup"><span data-stu-id="ae6e5-227">See also</span></span>

[<span data-ttu-id="ae6e5-228">about_Arithmetic_Operators</span><span class="sxs-lookup"><span data-stu-id="ae6e5-228">about_Arithmetic_Operators</span></span>](about_Arithmetic_Operators.md)

[<span data-ttu-id="ae6e5-229">about_Assignment_Operators</span><span class="sxs-lookup"><span data-stu-id="ae6e5-229">about_Assignment_Operators</span></span>](about_Assignment_Operators.md)

[<span data-ttu-id="ae6e5-230">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="ae6e5-230">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="ae6e5-231">about_Logical_Operators</span><span class="sxs-lookup"><span data-stu-id="ae6e5-231">about_Logical_Operators</span></span>](about_logical_operators.md)

[<span data-ttu-id="ae6e5-232">about_Operator_Precedence</span><span class="sxs-lookup"><span data-stu-id="ae6e5-232">about_Operator_Precedence</span></span>](about_operator_precedence.md)

[<span data-ttu-id="ae6e5-233">about_Type_Operators</span><span class="sxs-lookup"><span data-stu-id="ae6e5-233">about_Type_Operators</span></span>](about_Type_Operators.md)

[<span data-ttu-id="ae6e5-234">about_Split</span><span class="sxs-lookup"><span data-stu-id="ae6e5-234">about_Split</span></span>](about_Split.md)

[<span data-ttu-id="ae6e5-235">about_Join</span><span class="sxs-lookup"><span data-stu-id="ae6e5-235">about_Join</span></span>](about_Join.md)

[<span data-ttu-id="ae6e5-236">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="ae6e5-236">about_Redirection</span></span>](about_Redirection.md)