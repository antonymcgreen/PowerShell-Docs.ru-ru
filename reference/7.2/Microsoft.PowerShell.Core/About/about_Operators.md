---
description: Описание операторов, поддерживаемых PowerShell.
Locale: en-US
ms.date: 10/28/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_operators?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Operators
ms.openlocfilehash: c3884c7fc6c45e52ac9bccbe6c016908c242b8ef
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "99600464"
---
# <a name="about-operators"></a><span data-ttu-id="0ce04-103">Об операторах</span><span class="sxs-lookup"><span data-stu-id="0ce04-103">About Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="0ce04-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="0ce04-104">Short description</span></span>
<span data-ttu-id="0ce04-105">Описание операторов, поддерживаемых PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0ce04-105">Describes the operators that are supported by PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="0ce04-106">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="0ce04-106">Long description</span></span>

<span data-ttu-id="0ce04-107">Оператор — это элемент языка, который можно использовать в команде или выражении.</span><span class="sxs-lookup"><span data-stu-id="0ce04-107">An operator is a language element that you can use in a command or expression.</span></span>
<span data-ttu-id="0ce04-108">PowerShell поддерживает несколько типов операторов, помогающих управлять значениями.</span><span class="sxs-lookup"><span data-stu-id="0ce04-108">PowerShell supports several types of operators to help you manipulate values.</span></span>

### <a name="arithmetic-operators"></a><span data-ttu-id="0ce04-109">Арифметические операторы</span><span class="sxs-lookup"><span data-stu-id="0ce04-109">Arithmetic Operators</span></span>

<span data-ttu-id="0ce04-110">Используйте арифметические операторы ( `+` , `-` ,, `*` `/` , `%` ) для вычисления значений в команде или выражении.</span><span class="sxs-lookup"><span data-stu-id="0ce04-110">Use arithmetic operators (`+`, `-`, `*`, `/`, `%`) to calculate values in a command or expression.</span></span> <span data-ttu-id="0ce04-111">С помощью этих операторов можно добавлять, вычитать, умножать или делить значения, а также вычислять остаток (остаток от деления) операции деления.</span><span class="sxs-lookup"><span data-stu-id="0ce04-111">With these operators, you can add, subtract, multiply, or divide values, and calculate the remainder (modulus) of a division operation.</span></span>

<span data-ttu-id="0ce04-112">Оператор сложения объединяет элементы.</span><span class="sxs-lookup"><span data-stu-id="0ce04-112">The addition operator concatenates elements.</span></span> <span data-ttu-id="0ce04-113">Оператор умножения возвращает указанное количество копий каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="0ce04-113">The multiplication operator returns the specified number of copies of each element.</span></span> <span data-ttu-id="0ce04-114">Арифметические операторы можно использовать для любого типа .NET, который их реализует, например: `Int` ,,, `String` `DateTime` `Hashtable` и.</span><span class="sxs-lookup"><span data-stu-id="0ce04-114">You can use arithmetic operators on any .NET type that implements them, such as: `Int`, `String`, `DateTime`, `Hashtable`, and Arrays.</span></span>

<span data-ttu-id="0ce04-115">Битовые операторы ( `-band` , `-bor` , `-bxor` , `-bnot` , `-shl` , `-shr` ) управляют битовыми шаблонами в значениях.</span><span class="sxs-lookup"><span data-stu-id="0ce04-115">Bitwise operators (`-band`, `-bor`, `-bxor`, `-bnot`, `-shl`, `-shr`) manipulate the bit patterns in values.</span></span>

<span data-ttu-id="0ce04-116">Дополнительные сведения см. в разделе [about_Arithmetic_Operators](about_Arithmetic_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="0ce04-116">For more information, see [about_Arithmetic_Operators](about_Arithmetic_Operators.md).</span></span>

### <a name="assignment-operators"></a><span data-ttu-id="0ce04-117">Операторы присваивания</span><span class="sxs-lookup"><span data-stu-id="0ce04-117">Assignment Operators</span></span>

<span data-ttu-id="0ce04-118">Операторы присваивания (,,,, `=` `+=` `-=` `*=` `/=` , `%=` ) используются для назначения, изменения или добавления значений переменным.</span><span class="sxs-lookup"><span data-stu-id="0ce04-118">Use assignment operators (`=`, `+=`, `-=`, `*=`, `/=`, `%=`) to assign, change, or append values to variables.</span></span> <span data-ttu-id="0ce04-119">Арифметические операторы можно объединять с оператором присваивания, чтобы присвоить результат арифметической операции переменной.</span><span class="sxs-lookup"><span data-stu-id="0ce04-119">You can combine arithmetic operators with assignment to assign the result of the arithmetic operation to a variable.</span></span>

<span data-ttu-id="0ce04-120">Дополнительные сведения см. в разделе [about_Assignment_Operators](about_Assignment_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="0ce04-120">For more information, see [about_Assignment_Operators](about_Assignment_Operators.md).</span></span>

### <a name="comparison-operators"></a><span data-ttu-id="0ce04-121">Операторы сравнения</span><span class="sxs-lookup"><span data-stu-id="0ce04-121">Comparison Operators</span></span>

<span data-ttu-id="0ce04-122">Используйте операторы сравнения ( `-eq` , `-ne` ,,, `-gt` `-lt` `-le` , `-ge` ) для сравнения значений и условий теста.</span><span class="sxs-lookup"><span data-stu-id="0ce04-122">Use comparison operators (`-eq`, `-ne`, `-gt`, `-lt`, `-le`, `-ge`) to compare values and test conditions.</span></span> <span data-ttu-id="0ce04-123">Например, можно сравнить два строковых значения, чтобы определить, равны ли они.</span><span class="sxs-lookup"><span data-stu-id="0ce04-123">For example, you can compare two string values to determine whether they are equal.</span></span>

<span data-ttu-id="0ce04-124">Операторы сравнения также включают операторы, которые находят или заменяют закономерности в тексте.</span><span class="sxs-lookup"><span data-stu-id="0ce04-124">The comparison operators also include operators that find or replace patterns in text.</span></span> <span data-ttu-id="0ce04-125">Операторы ( `-match` , `-notmatch` , `-replace` ) используют регулярные выражения, а ( `-like` , `-notlike` ) используют подстановочные знаки `*` .</span><span class="sxs-lookup"><span data-stu-id="0ce04-125">The (`-match`, `-notmatch`, `-replace`) operators use regular expressions, and (`-like`, `-notlike`) use wildcards `*`.</span></span>

<span data-ttu-id="0ce04-126">Операторы сравнения вложений определяют, отображается ли тестовое значение в наборе ссылок ( `-in` ,, `-notin` `-contains` , `-notcontains` ).</span><span class="sxs-lookup"><span data-stu-id="0ce04-126">Containment comparison operators determine whether a test value appears in a reference set (`-in`, `-notin`, `-contains`, `-notcontains`).</span></span>

<span data-ttu-id="0ce04-127">Операторы сравнения типов ( `-is` , `-isnot` ) определяют, относится ли объект к данному типу.</span><span class="sxs-lookup"><span data-stu-id="0ce04-127">Type comparison operators (`-is`, `-isnot`) determine whether an object is of a given type.</span></span>

<span data-ttu-id="0ce04-128">Дополнительные сведения см. в разделе [about_Comparison_Operators](about_Comparison_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="0ce04-128">For more information, see [about_Comparison_Operators](about_Comparison_Operators.md).</span></span>

### <a name="logical-operators"></a><span data-ttu-id="0ce04-129">Логические операторы</span><span class="sxs-lookup"><span data-stu-id="0ce04-129">Logical Operators</span></span>

<span data-ttu-id="0ce04-130">Используйте логические операторы ( `-and` , `-or` , `-xor` , `-not` , `!` ) для подключения условных операторов к одному сложному условию.</span><span class="sxs-lookup"><span data-stu-id="0ce04-130">Use logical operators (`-and`, `-or`, `-xor`, `-not`, `!`) to connect conditional statements into a single complex conditional.</span></span> <span data-ttu-id="0ce04-131">Например, логический оператор можно использовать `-and` для создания фильтра объектов с двумя различными условиями.</span><span class="sxs-lookup"><span data-stu-id="0ce04-131">For example, you can use a logical `-and` operator to create an object filter with two different conditions.</span></span>

<span data-ttu-id="0ce04-132">Дополнительные сведения см. в разделе [about_Logical_Operators](about_logical_operators.md).</span><span class="sxs-lookup"><span data-stu-id="0ce04-132">For more information, see [about_Logical_Operators](about_logical_operators.md).</span></span>

### <a name="redirection-operators"></a><span data-ttu-id="0ce04-133">Операторы перенаправления</span><span class="sxs-lookup"><span data-stu-id="0ce04-133">Redirection Operators</span></span>

<span data-ttu-id="0ce04-134">Используйте операторы перенаправления ( `>` ,, `>>` `2>` , `2>>` и `2>&1` ) для отправки выходных данных команды или выражения в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="0ce04-134">Use redirection operators (`>`, `>>`, `2>`, `2>>`, and `2>&1`) to send the output of a command or expression to a text file.</span></span> <span data-ttu-id="0ce04-135">Операторы перенаправления работают как `Out-File` командлет (без параметров), но они также позволяют перенаправлять вывод ошибок в указанные файлы.</span><span class="sxs-lookup"><span data-stu-id="0ce04-135">The redirection operators work like the `Out-File` cmdlet (without parameters) but they also let you redirect error output to specified files.</span></span> <span data-ttu-id="0ce04-136">Можно также использовать `Tee-Object` командлет для перенаправления выходных данных.</span><span class="sxs-lookup"><span data-stu-id="0ce04-136">You can also use the `Tee-Object` cmdlet to redirect output.</span></span>

<span data-ttu-id="0ce04-137">Дополнительные сведения см. в разделе [about_Redirection](about_Redirection.md)</span><span class="sxs-lookup"><span data-stu-id="0ce04-137">For more information, see [about_Redirection](about_Redirection.md)</span></span>

### <a name="split-and-join-operators"></a><span data-ttu-id="0ce04-138">Операторы Split и Join</span><span class="sxs-lookup"><span data-stu-id="0ce04-138">Split and Join Operators</span></span>

<span data-ttu-id="0ce04-139">`-split`Операторы and `-join` делят и объединяют подстроки.</span><span class="sxs-lookup"><span data-stu-id="0ce04-139">The `-split` and `-join` operators divide and combine substrings.</span></span> <span data-ttu-id="0ce04-140">`-split`Оператор разделяет строку на подстроки.</span><span class="sxs-lookup"><span data-stu-id="0ce04-140">The `-split` operator splits a string into substrings.</span></span> <span data-ttu-id="0ce04-141">`-join`Оператор объединяет несколько строк в одну строку.</span><span class="sxs-lookup"><span data-stu-id="0ce04-141">The `-join` operator concatenates multiple strings into a single string.</span></span>

<span data-ttu-id="0ce04-142">Дополнительные сведения см. в разделе [about_Split](about_Split.md) и [about_Join](about_Join.md).</span><span class="sxs-lookup"><span data-stu-id="0ce04-142">For more information, see [about_Split](about_Split.md) and [about_Join](about_Join.md).</span></span>

### <a name="type-operators"></a><span data-ttu-id="0ce04-143">Операторы работы с типами</span><span class="sxs-lookup"><span data-stu-id="0ce04-143">Type Operators</span></span>

<span data-ttu-id="0ce04-144">Используйте операторы типа ( `-is` , `-isnot` ,), `-as` чтобы найти или изменить тип платформа .NET Framework объекта.</span><span class="sxs-lookup"><span data-stu-id="0ce04-144">Use the type operators (`-is`, `-isnot`, `-as`) to find or change the .NET Framework type of an object.</span></span>

<span data-ttu-id="0ce04-145">Дополнительные сведения см. в разделе [about_Type_Operators](about_Type_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="0ce04-145">For more information, see [about_Type_Operators](about_Type_Operators.md).</span></span>

### <a name="unary-operators"></a><span data-ttu-id="0ce04-146">Унарные операторы</span><span class="sxs-lookup"><span data-stu-id="0ce04-146">Unary Operators</span></span>

<span data-ttu-id="0ce04-147">Используйте унарные операторы для увеличения или уменьшения числа переменных или свойств объектов, а также для присвоения целочисленных значений положительным или отрицательным числам.</span><span class="sxs-lookup"><span data-stu-id="0ce04-147">Use unary operators to increment or decrement variables or object properties and to set integers to positive or negative numbers.</span></span> <span data-ttu-id="0ce04-148">Например, чтобы увеличить переменную `$a` с `9` на `10` , введите `$a++` .</span><span class="sxs-lookup"><span data-stu-id="0ce04-148">For example, to increment the variable `$a` from `9` to `10`, you type `$a++`.</span></span>

### <a name="special-operators"></a><span data-ttu-id="0ce04-149">Специальные операторы</span><span class="sxs-lookup"><span data-stu-id="0ce04-149">Special Operators</span></span>

<span data-ttu-id="0ce04-150">Специальные операторы имеют особые варианты использования, которые не помещаются в любую другую группу операторов.</span><span class="sxs-lookup"><span data-stu-id="0ce04-150">Special operators have specific use-cases that do not fit into any other operator group.</span></span> <span data-ttu-id="0ce04-151">Например, Специальные операторы позволяют выполнять команды, изменять тип данных значения или извлекать элементы из массива.</span><span class="sxs-lookup"><span data-stu-id="0ce04-151">For example, special operators allow you to run commands, change a value's data type, or retrieve elements from an array.</span></span>

#### <a name="grouping-operator--"></a><span data-ttu-id="0ce04-152">Оператор группирования `( )`</span><span class="sxs-lookup"><span data-stu-id="0ce04-152">Grouping operator `( )`</span></span>

<span data-ttu-id="0ce04-153">Как и в других языках, `(...)` служит для переопределения приоритета операторов в выражениях.</span><span class="sxs-lookup"><span data-stu-id="0ce04-153">As in other languages, `(...)` serves to override operator precedence in expressions.</span></span> <span data-ttu-id="0ce04-154">Пример: `(1 + 2) / 3`</span><span class="sxs-lookup"><span data-stu-id="0ce04-154">For example: `(1 + 2) / 3`</span></span>

<span data-ttu-id="0ce04-155">Однако в PowerShell существуют дополнительные поведения.</span><span class="sxs-lookup"><span data-stu-id="0ce04-155">However, in PowerShell, there are additional behaviors.</span></span>

- <span data-ttu-id="0ce04-156">`(...)` позволяет разрешить выходные данные _команды_ участвовать в выражении.</span><span class="sxs-lookup"><span data-stu-id="0ce04-156">`(...)` allows you to let output from a _command_ participate in an expression.</span></span> <span data-ttu-id="0ce04-157">Пример:</span><span class="sxs-lookup"><span data-stu-id="0ce04-157">For example:</span></span>

  ```powershell
  PS> (Get-Item *.txt).Count -gt 10
  True
  ```

- <span data-ttu-id="0ce04-158">При использовании в качестве первого сегмента конвейера, заключение команды или выражения в круглые скобки неизменно приводит к _перечислению_ результата выражения.</span><span class="sxs-lookup"><span data-stu-id="0ce04-158">When used as the first segment of a pipeline, wrapping a command or expression in parentheses invariably causes _enumeration_ of the expression result.</span></span> <span data-ttu-id="0ce04-159">Если скобки заключают _команду_ в оболочку, она выполняется до завершения со всеми данными, _собранными в памяти_ до отправки результатов через конвейер.</span><span class="sxs-lookup"><span data-stu-id="0ce04-159">If the parentheses wrap a _command_, it is run to completion with all output _collected in memory_ before the results are sent through the pipeline.</span></span>

#### <a name="subexpression-operator--"></a><span data-ttu-id="0ce04-160">Оператор части выражения `$( )`</span><span class="sxs-lookup"><span data-stu-id="0ce04-160">Subexpression operator `$( )`</span></span>

<span data-ttu-id="0ce04-161">Возвращает результат одной или нескольких инструкций.</span><span class="sxs-lookup"><span data-stu-id="0ce04-161">Returns the result of one or more statements.</span></span> <span data-ttu-id="0ce04-162">Для одного результата возвращает скалярное значение.</span><span class="sxs-lookup"><span data-stu-id="0ce04-162">For a single result, returns a scalar.</span></span> <span data-ttu-id="0ce04-163">Для нескольких результатов возвращает массив.</span><span class="sxs-lookup"><span data-stu-id="0ce04-163">For multiple results, returns an array.</span></span> <span data-ttu-id="0ce04-164">Используйте этот параметр, если требуется использовать выражение в другом выражении.</span><span class="sxs-lookup"><span data-stu-id="0ce04-164">Use this when you want to use an expression within another expression.</span></span> <span data-ttu-id="0ce04-165">Например, чтобы внедрить результаты команды в строковое выражение.</span><span class="sxs-lookup"><span data-stu-id="0ce04-165">For example, to embed the results of command in a string expression.</span></span>

```powershell
PS> "Today is $(Get-Date)"
Today is 12/02/2019 13:15:20

PS> "Folder list: $((dir c:\ -dir).Name -join ', ')"
Folder list: Program Files, Program Files (x86), Users, Windows
```

#### <a name="array-subexpression-operator--"></a><span data-ttu-id="0ce04-166">Оператор части выражения массива `@( )`</span><span class="sxs-lookup"><span data-stu-id="0ce04-166">Array subexpression operator `@( )`</span></span>

<span data-ttu-id="0ce04-167">Возвращает результат одной или нескольких инструкций в виде массива.</span><span class="sxs-lookup"><span data-stu-id="0ce04-167">Returns the result of one or more statements as an array.</span></span> <span data-ttu-id="0ce04-168">Если имеется только один элемент, массив содержит только один элемент.</span><span class="sxs-lookup"><span data-stu-id="0ce04-168">If there is only one item, the array has only one member.</span></span>

```powershell
@(Get-CimInstance win32_logicalDisk)
```

#### <a name="hash-table-literal-syntax-"></a><span data-ttu-id="0ce04-169">Синтаксис литерала хэш-таблицы `@{}`</span><span class="sxs-lookup"><span data-stu-id="0ce04-169">Hash table literal syntax `@{}`</span></span>

<span data-ttu-id="0ce04-170">Как и часть выражения массива, этот синтаксис используется для объявления хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="0ce04-170">Similar to the array subexpression, this syntax is used to declare a hash table.</span></span>
<span data-ttu-id="0ce04-171">Дополнительные сведения см. в разделе [about_Hash_Tables](about_Hash_Tables.md).</span><span class="sxs-lookup"><span data-stu-id="0ce04-171">For more information, see [about_Hash_Tables](about_Hash_Tables.md).</span></span>

#### <a name="call-operator-"></a><span data-ttu-id="0ce04-172">Оператор Call `&`</span><span class="sxs-lookup"><span data-stu-id="0ce04-172">Call operator `&`</span></span>

<span data-ttu-id="0ce04-173">Выполняет команду, сценарий или блок скрипта.</span><span class="sxs-lookup"><span data-stu-id="0ce04-173">Runs a command, script, or script block.</span></span> <span data-ttu-id="0ce04-174">Оператор Call, также известный как «оператор вызова», позволяет выполнять команды, которые хранятся в переменных и представляются строками или блоками сценариев.</span><span class="sxs-lookup"><span data-stu-id="0ce04-174">The call operator, also known as the "invocation operator", lets you run commands that are stored in variables and represented by strings or script blocks.</span></span> <span data-ttu-id="0ce04-175">Оператор Call выполняется в дочерней области.</span><span class="sxs-lookup"><span data-stu-id="0ce04-175">The call operator executes in a child scope.</span></span> <span data-ttu-id="0ce04-176">Дополнительные сведения об областях см. в разделе [about_Scopes](about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="0ce04-176">For more about scopes, see [about_Scopes](about_Scopes.md).</span></span>

<span data-ttu-id="0ce04-177">В этом примере команда сохраняется в строке и выполняется с помощью оператора Call.</span><span class="sxs-lookup"><span data-stu-id="0ce04-177">This example stores a command in a string and executes it using the call operator.</span></span>

```
PS> $c = "get-executionpolicy"
PS> $c
get-executionpolicy
PS> & $c
AllSigned
```

<span data-ttu-id="0ce04-178">Оператор Call не выполняет синтаксический анализ строк.</span><span class="sxs-lookup"><span data-stu-id="0ce04-178">The call operator does not parse strings.</span></span> <span data-ttu-id="0ce04-179">Это означает, что нельзя использовать параметры команды в строке при использовании оператора Call.</span><span class="sxs-lookup"><span data-stu-id="0ce04-179">This means that you cannot use command parameters within a string when you use the call operator.</span></span>

```
PS> $c = "Get-Service -Name Spooler"
PS> $c
Get-Service -Name Spooler
PS> & $c
& : The term 'Get-Service -Name Spooler' is not recognized as the name of a
cmdlet, function, script file, or operable program. Check the spelling of
the name, or if a path was included, verify that the path is correct and
try again.
```

<span data-ttu-id="0ce04-180">Командлет [Invoke-Expression](xref:Microsoft.PowerShell.Utility.Invoke-Expression) может выполнять код, который вызывает ошибки синтаксического анализа при использовании оператора Call.</span><span class="sxs-lookup"><span data-stu-id="0ce04-180">The [Invoke-Expression](xref:Microsoft.PowerShell.Utility.Invoke-Expression) cmdlet can execute code that causes parsing errors when using the call operator.</span></span>

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

<span data-ttu-id="0ce04-181">Оператор Call можно использовать для выполнения скриптов, использующих их имена файлов.</span><span class="sxs-lookup"><span data-stu-id="0ce04-181">You can use the call operator to execute scripts using their filenames.</span></span> <span data-ttu-id="0ce04-182">В следующем примере показано имя файла скрипта, содержащего пробелы.</span><span class="sxs-lookup"><span data-stu-id="0ce04-182">The example below shows a script filename that contains spaces.</span></span> <span data-ttu-id="0ce04-183">При попытке выполнить скрипт PowerShell вместо этого отображает содержимое строки в кавычках, содержащей имя файла.</span><span class="sxs-lookup"><span data-stu-id="0ce04-183">When you try to execute the script, PowerShell instead displays the contents of the quoted string containing the filename.</span></span> <span data-ttu-id="0ce04-184">Оператор Call позволяет выполнить содержимое строки, содержащей имя файла.</span><span class="sxs-lookup"><span data-stu-id="0ce04-184">The call operator allows you to execute the contents of the string containing the filename.</span></span>

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

<span data-ttu-id="0ce04-185">Дополнительные сведения о блоках скриптов см. в разделе [about_Script_Blocks](about_Script_Blocks.md).</span><span class="sxs-lookup"><span data-stu-id="0ce04-185">For more about script blocks, see [about_Script_Blocks](about_Script_Blocks.md).</span></span>

#### <a name="background-operator-"></a><span data-ttu-id="0ce04-186">Оператор Background `&`</span><span class="sxs-lookup"><span data-stu-id="0ce04-186">Background operator `&`</span></span>

<span data-ttu-id="0ce04-187">Запускает конвейер перед в фоновом режиме в задании PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0ce04-187">Runs the pipeline before it in the background, in a PowerShell job.</span></span> <span data-ttu-id="0ce04-188">Этот оператор действует аналогично оператору управления UNIX "амперсанд ( `&` )", который выполняет команду до ее асинхронного выполнения в качестве задания.</span><span class="sxs-lookup"><span data-stu-id="0ce04-188">This operator acts similarly to the UNIX control operator ampersand (`&`), which runs the command before it asynchronously in subshell as a job.</span></span>

<span data-ttu-id="0ce04-189">Этот оператор функционально эквивалентен `Start-Job` .</span><span class="sxs-lookup"><span data-stu-id="0ce04-189">This operator is functionally equivalent to `Start-Job`.</span></span> <span data-ttu-id="0ce04-190">По умолчанию оператор Background запускает задания в текущем рабочем каталоге вызывающего объекта, который запустил параллельные задачи.</span><span class="sxs-lookup"><span data-stu-id="0ce04-190">By default, the background operator starts the jobs in the current working directory of the caller that started the parallel tasks.</span></span> <span data-ttu-id="0ce04-191">В следующем примере демонстрируется базовое использование оператора фонового задания.</span><span class="sxs-lookup"><span data-stu-id="0ce04-191">The following example demonstrates basic usage of the background job operator.</span></span>

```powershell
Get-Process -Name pwsh &
```

<span data-ttu-id="0ce04-192">Эта команда функционально эквивалентна следующему использованию `Start-Job` :</span><span class="sxs-lookup"><span data-stu-id="0ce04-192">That command is functionally equivalent to the following usage of `Start-Job`:</span></span>

```powershell
Start-Job -ScriptBlock {Get-Process -Name pwsh}
```

<span data-ttu-id="0ce04-193">Как и `Start-Job` в случае, `&` оператор Background возвращает `Job` объект.</span><span class="sxs-lookup"><span data-stu-id="0ce04-193">Just like `Start-Job`, the `&` background operator returns a `Job` object.</span></span> <span data-ttu-id="0ce04-194">Этот объект можно использовать с `Receive-Job` и `Remove-Job` , точно так же, как если бы вы использовали `Start-Job` для запуска задания.</span><span class="sxs-lookup"><span data-stu-id="0ce04-194">This object can be used with `Receive-Job` and `Remove-Job`, just as if you had used `Start-Job` to start the job.</span></span>

```powershell
$job = Get-Process -Name pwsh &
Receive-Job $job -Wait
```

```Output

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
      0     0.00     221.16      25.90    6988 988 pwsh
      0     0.00     140.12      29.87   14845 845 pwsh
      0     0.00      85.51       0.91   19639 988 pwsh

```

```powershell
Remove-Job $job
```

<span data-ttu-id="0ce04-195">`&`Фоновый оператор также является признаком конца инструкции, как и оператором управления UNIX ( `&` ).</span><span class="sxs-lookup"><span data-stu-id="0ce04-195">The `&` background operator is also a statement terminator, just like the UNIX control operator ampersand (`&`).</span></span> <span data-ttu-id="0ce04-196">Это позволяет вызывать дополнительные команды после `&` фонового оператора.</span><span class="sxs-lookup"><span data-stu-id="0ce04-196">This allows you to invoke additional commands after the `&` background operator.</span></span> <span data-ttu-id="0ce04-197">В следующем примере демонстрируется вызов дополнительных команд после `&` оператора Background.</span><span class="sxs-lookup"><span data-stu-id="0ce04-197">The following example demonstrates the invocation of additional commands after the `&` background operator.</span></span>

```powershell
$job = Get-Process -Name pwsh & Receive-Job $job -Wait
```

```Output

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
      0     0.00     221.16      25.90    6988 988 pwsh
      0     0.00     140.12      29.87   14845 845 pwsh
      0     0.00      85.51       0.91   19639 988 pwsh

```

<span data-ttu-id="0ce04-198">Это эквивалентно следующему сценарию:</span><span class="sxs-lookup"><span data-stu-id="0ce04-198">This is equivalent to the following script:</span></span>

```powershell
$job = Start-Job -ScriptBlock {Get-Process -Name pwsh}
Receive-Job $job -Wait
```

<span data-ttu-id="0ce04-199">Если требуется выполнить несколько команд, каждая из которых находится в собственном фоновом процессе, но все они находятся на одной строке, просто поместите их `&` между и после каждой команды.</span><span class="sxs-lookup"><span data-stu-id="0ce04-199">If you want to run multiple commands, each in their own background process but all on one line, simply place `&` between and after each of the commands.</span></span>

```powershell
Get-Process -Name pwsh & Get-Service -Name BITS & Get-CimInstance -ClassName Win32_ComputerSystem &
```

<span data-ttu-id="0ce04-200">Дополнительные сведения о заданиях PowerShell см. в разделе [about_Jobs](about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="0ce04-200">For more information on PowerShell jobs, see [about_Jobs](about_Jobs.md).</span></span>

#### <a name="cast-operator--"></a><span data-ttu-id="0ce04-201">Оператор CAST `[ ]`</span><span class="sxs-lookup"><span data-stu-id="0ce04-201">Cast operator `[ ]`</span></span>

<span data-ttu-id="0ce04-202">Преобразует или ограничивает объекты указанным типом.</span><span class="sxs-lookup"><span data-stu-id="0ce04-202">Converts or limits objects to the specified type.</span></span> <span data-ttu-id="0ce04-203">Если не удается преобразовать объекты, PowerShell выдает ошибку.</span><span class="sxs-lookup"><span data-stu-id="0ce04-203">If the objects cannot be converted, PowerShell generates an error.</span></span>

```powershell
[DateTime]"2/20/88" - [DateTime]"1/20/88"
[Int] (7/2)
[String] 1 + 0
[Int] '1' + 0
```

<span data-ttu-id="0ce04-204">Приведение также можно выполнить, если переменная назначена с помощью [нотации приведения](about_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="0ce04-204">A cast can also be performed when a variable is assigned to using [cast notation](about_Variables.md).</span></span>

#### <a name="comma-operator-"></a><span data-ttu-id="0ce04-205">Запятая, оператор `,`</span><span class="sxs-lookup"><span data-stu-id="0ce04-205">Comma operator `,`</span></span>

<span data-ttu-id="0ce04-206">Как бинарный оператор, запятая создает массив или добавляет к создаваемому массиву.</span><span class="sxs-lookup"><span data-stu-id="0ce04-206">As a binary operator, the comma creates an array or appends to the array being created.</span></span> <span data-ttu-id="0ce04-207">В режиме выражения в качестве унарного оператора запятая создает массив только с одним элементом.</span><span class="sxs-lookup"><span data-stu-id="0ce04-207">In expression mode, as a unary operator, the comma creates an array with just one member.</span></span> <span data-ttu-id="0ce04-208">Поместите запятую перед элементом.</span><span class="sxs-lookup"><span data-stu-id="0ce04-208">Place the comma before the member.</span></span>

```powershell
$myArray = 1,2,3
$SingleArray = ,1
Write-Output (,1)
```

<span data-ttu-id="0ce04-209">Поскольку `Write-Object` предполагает аргумент, выражение должно быть заключено в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="0ce04-209">Since `Write-Object` expects an argument, you must put the expression in parentheses.</span></span>

#### <a name="dot-sourcing-operator-"></a><span data-ttu-id="0ce04-210">Оператор "точка с точкой" `.`</span><span class="sxs-lookup"><span data-stu-id="0ce04-210">Dot sourcing operator `.`</span></span>

<span data-ttu-id="0ce04-211">Выполняет скрипт в текущей области, чтобы все функции, псевдонимы и переменные, создаваемые сценарием, добавлялись в текущую область, переопределяя существующие.</span><span class="sxs-lookup"><span data-stu-id="0ce04-211">Runs a script in the current scope so that any functions, aliases, and variables that the script creates are added to the current scope, overriding existing ones.</span></span> <span data-ttu-id="0ce04-212">Параметры, объявленные сценарием, становятся переменными.</span><span class="sxs-lookup"><span data-stu-id="0ce04-212">Parameters declared by the script become variables.</span></span> <span data-ttu-id="0ce04-213">Параметры, для которых не было указано значение, становятся переменными без значения.</span><span class="sxs-lookup"><span data-stu-id="0ce04-213">Parameters for which no value has been given become variables with no value.</span></span> <span data-ttu-id="0ce04-214">Однако автоматическая переменная `$args` сохраняется.</span><span class="sxs-lookup"><span data-stu-id="0ce04-214">However, the automatic variable `$args` is preserved.</span></span>

```powershell
. c:\scripts\sample.ps1 1 2 -Also:3
```

> [!NOTE]
> <span data-ttu-id="0ce04-215">За оператором «точка» следует пробел.</span><span class="sxs-lookup"><span data-stu-id="0ce04-215">The dot sourcing operator is followed by a space.</span></span> <span data-ttu-id="0ce04-216">Используйте пробел, чтобы отличить точку от символа точки ( `.` ), который представляет текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="0ce04-216">Use the space to distinguish the dot from the dot (`.`) symbol that represents the current directory.</span></span>
>
> <span data-ttu-id="0ce04-217">В следующем примере сценарий Sample.ps1 в текущем каталоге выполняется в текущей области.</span><span class="sxs-lookup"><span data-stu-id="0ce04-217">In the following example, the Sample.ps1 script in the current directory is run in the current scope.</span></span>
>
> ```powershell
> . .\sample.ps1
> ```

#### <a name="format-operator--f"></a><span data-ttu-id="0ce04-218">Format, оператор `-f`</span><span class="sxs-lookup"><span data-stu-id="0ce04-218">Format operator `-f`</span></span>

<span data-ttu-id="0ce04-219">Форматирует строки с помощью метода Format строковых объектов.</span><span class="sxs-lookup"><span data-stu-id="0ce04-219">Formats strings by using the format method of string objects.</span></span> <span data-ttu-id="0ce04-220">Введите строку формата слева от оператора и объекты, которые должны быть отформатированы с правой стороны оператора.</span><span class="sxs-lookup"><span data-stu-id="0ce04-220">Enter the format string on the left side of the operator and the objects to be formatted on the right side of the operator.</span></span>

```powershell
"{0} {1,-10} {2:N}" -f 1,"hello",[math]::pi
```

```output
1 hello      3.14
```

<span data-ttu-id="0ce04-221">Если необходимо, чтобы фигурные скобки ( `{}` ) в форматируемой строке были заключены в квадратные скобки, их можно поэкранировать.</span><span class="sxs-lookup"><span data-stu-id="0ce04-221">If you need to keep the curly braces (`{}`) in the formatted string, you can escape them by doubling the curly braces.</span></span>

```powershell
"{0} vs. {{0}}" -f 'foo'
```

```Output
foo vs. {0}
```

<span data-ttu-id="0ce04-222">Дополнительные сведения см. в разделе метод [String. Format](/dotnet/api/system.string.format) и [составное форматирование](/dotnet/standard/base-types/composite-formatting).</span><span class="sxs-lookup"><span data-stu-id="0ce04-222">For more information, see the [String.Format](/dotnet/api/system.string.format) method and [Composite Formatting](/dotnet/standard/base-types/composite-formatting).</span></span>

#### <a name="index-operator--"></a><span data-ttu-id="0ce04-223">Оператор индекса `[ ]`</span><span class="sxs-lookup"><span data-stu-id="0ce04-223">Index operator `[ ]`</span></span>

<span data-ttu-id="0ce04-224">Выбирает объекты из индексированных коллекций, таких как массивы и хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="0ce04-224">Selects objects from indexed collections, such as arrays and hash tables.</span></span> <span data-ttu-id="0ce04-225">Индексы массива отсчитываются от нуля, поэтому первый объект индексируется как `[0]` .</span><span class="sxs-lookup"><span data-stu-id="0ce04-225">Array indexes are zero-based, so the first object is indexed as `[0]`.</span></span> <span data-ttu-id="0ce04-226">Для массивов (только) для получения последних значений можно также использовать отрицательные индексы.</span><span class="sxs-lookup"><span data-stu-id="0ce04-226">For arrays (only), you can also use negative indexes to get the last values.</span></span> <span data-ttu-id="0ce04-227">Хэш-таблицы индексируются по значению ключа.</span><span class="sxs-lookup"><span data-stu-id="0ce04-227">Hash tables are indexed by key value.</span></span>

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

#### <a name="pipeline-operator-"></a><span data-ttu-id="0ce04-228">Конвейерный оператор `|`</span><span class="sxs-lookup"><span data-stu-id="0ce04-228">Pipeline operator `|`</span></span>

<span data-ttu-id="0ce04-229">Отправляет ("pipe") выходные данные команды, предшествующей ей, с помощью команды, следующей за ней.</span><span class="sxs-lookup"><span data-stu-id="0ce04-229">Sends ("pipes") the output of the command that precedes it to the command that follows it.</span></span> <span data-ttu-id="0ce04-230">Если выходные данные содержат более одного объекта ("Коллекция"), оператор конвейера посылает объекты по одному за раз.</span><span class="sxs-lookup"><span data-stu-id="0ce04-230">When the output includes more than one object (a "collection"), the pipeline operator sends the objects one at a time.</span></span>

```powershell
Get-Process | Get-Member
Get-Service | Where-Object {$_.StartType -eq 'Automatic'}
```

#### <a name="pipeline-chain-operators--and-"></a><span data-ttu-id="0ce04-231">Операторы цепочки конвейеров `&&` и `||`</span><span class="sxs-lookup"><span data-stu-id="0ce04-231">Pipeline chain operators `&&` and `||`</span></span>

<span data-ttu-id="0ce04-232">Условно выполняет правый конвейер в зависимости от успешности конвейера левой части.</span><span class="sxs-lookup"><span data-stu-id="0ce04-232">Conditionally execute the right-hand side pipeline based on the success of the left-hand side pipeline.</span></span>

```powershell
# If Get-Process successfully finds a process called notepad,
# Stop-Process -Name notepad is called
Get-Process notepad && Stop-Process -Name notepad
```

```powershell
# If npm install fails, the node_modules directory is removed
npm install || Remove-Item -Recurse ./node_modules
```

<span data-ttu-id="0ce04-233">Дополнительные сведения см. в разделе [About_Pipeline_Chain_Operators](About_Pipeline_Chain_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="0ce04-233">For more information, see [About_Pipeline_Chain_Operators](About_Pipeline_Chain_Operators.md).</span></span>

#### <a name="range-operator-"></a><span data-ttu-id="0ce04-234">Оператор Range `..`</span><span class="sxs-lookup"><span data-stu-id="0ce04-234">Range operator `..`</span></span>

<span data-ttu-id="0ce04-235">Представляет последовательные целые числа в массиве целых чисел с учетом верхней и нижней границ.</span><span class="sxs-lookup"><span data-stu-id="0ce04-235">Represents the sequential integers in an integer array, given an upper, and lower boundary.</span></span>

```powershell
1..10
foreach ($a in 1..$max) {Write-Host $a}
```

<span data-ttu-id="0ce04-236">Можно также создавать диапазоны в обратных последовательностях.</span><span class="sxs-lookup"><span data-stu-id="0ce04-236">You can also create ranges in reverse order.</span></span>

```powershell
10..1
5..-5 | ForEach-Object {Write-Output $_}
```

<span data-ttu-id="0ce04-237">Начиная с PowerShell 6 оператор Range работает с **символами** , а также с **целыми числами**.</span><span class="sxs-lookup"><span data-stu-id="0ce04-237">Beginning in PowerShell 6, the range operator works with **Characters** as well as **Integers**.</span></span>

<span data-ttu-id="0ce04-238">Чтобы создать диапазон символов, заключите эти символы в кавычки.</span><span class="sxs-lookup"><span data-stu-id="0ce04-238">To create a range of characters, enclose the boundary characters in quotes.</span></span>

```powershell
PS> 'a'..'f'
a
b
c
d
e
f
```

```powershell
PS> 'F'..'A'
F
E
D
C
B
A
```

#### <a name="member-access-operator-"></a><span data-ttu-id="0ce04-239">Оператор доступа к членам `.`</span><span class="sxs-lookup"><span data-stu-id="0ce04-239">Member access operator `.`</span></span>

<span data-ttu-id="0ce04-240">Обращается к свойствам и методам объекта.</span><span class="sxs-lookup"><span data-stu-id="0ce04-240">Accesses the properties and methods of an object.</span></span> <span data-ttu-id="0ce04-241">Имя члена может быть выражением.</span><span class="sxs-lookup"><span data-stu-id="0ce04-241">The member name may be an expression.</span></span>

```powershell
$myProcess.peakWorkingSet
(Get-Process PowerShell).kill()
'OS', 'Platform' | Foreach-Object { $PSVersionTable. $_ }
```

#### <a name="static-member-operator-"></a><span data-ttu-id="0ce04-242">Статический оператор члена `::`</span><span class="sxs-lookup"><span data-stu-id="0ce04-242">Static member operator `::`</span></span>

<span data-ttu-id="0ce04-243">Вызывает статические свойства и методы класса платформа .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0ce04-243">Calls the static properties and methods of a .NET Framework class.</span></span> <span data-ttu-id="0ce04-244">Чтобы найти статические свойства и методы объекта, используйте статический параметр `Get-Member` командлета.</span><span class="sxs-lookup"><span data-stu-id="0ce04-244">To find the static properties and methods of an object, use the Static parameter of the `Get-Member` cmdlet.</span></span>  <span data-ttu-id="0ce04-245">Имя члена может быть выражением.</span><span class="sxs-lookup"><span data-stu-id="0ce04-245">The member name may be an expression.</span></span>

```powershell
[datetime]::Now
'MinValue', 'MaxValue' | Foreach-Object { [int]:: $_ }
```

#### <a name="ternary-operator--if-true--if-false"></a><span data-ttu-id="0ce04-246">Оператор Ternary `? <if-true> : <if-false>`</span><span class="sxs-lookup"><span data-stu-id="0ce04-246">Ternary operator `? <if-true> : <if-false>`</span></span>

<span data-ttu-id="0ce04-247">Оператор ternary можно использовать в качестве замены `if-else` инструкции в простых условных случаях.</span><span class="sxs-lookup"><span data-stu-id="0ce04-247">You can use the ternary operator as a replacement for the `if-else` statement in simple conditional cases.</span></span>

<span data-ttu-id="0ce04-248">Дополнительные сведения см. в разделе [about_If](about_If.md).</span><span class="sxs-lookup"><span data-stu-id="0ce04-248">For more information, see [about_If](about_If.md).</span></span>

#### <a name="null-coalescing-operator-"></a><span data-ttu-id="0ce04-249">Оператор объединения со значением NULL `??`</span><span class="sxs-lookup"><span data-stu-id="0ce04-249">Null-coalescing operator `??`</span></span>

<span data-ttu-id="0ce04-250">Оператор объединения со значением NULL `??` возвращает значение левого операнда, если оно не равно NULL.</span><span class="sxs-lookup"><span data-stu-id="0ce04-250">The null-coalescing operator `??` returns the value of its left-hand operand if it isn't null.</span></span> <span data-ttu-id="0ce04-251">В противном случае он вычисляет правый операнд и возвращает результат.</span><span class="sxs-lookup"><span data-stu-id="0ce04-251">Otherwise, it evaluates the right-hand operand and returns its result.</span></span> <span data-ttu-id="0ce04-252">Оператор `??` не вычисляет правый операнд, если значение левого операнда отлично от NULL.</span><span class="sxs-lookup"><span data-stu-id="0ce04-252">The `??` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

```powershell
$x = $null
$x ?? 100
```

```Output
100
```

<span data-ttu-id="0ce04-253">В следующем примере правый операнд не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="0ce04-253">In the following example, the right-hand operand won't be evaluated.</span></span>

```powershell
[string] $todaysDate = '1/10/2020'
$todaysDate ?? (Get-Date).ToShortDateString()
```

```Output
1/10/2020
```

#### <a name="null-coalescing-assignment-operator-"></a><span data-ttu-id="0ce04-254">Оператор присваивания, объединяющий значения NULL `??=`</span><span class="sxs-lookup"><span data-stu-id="0ce04-254">Null-coalescing assignment operator `??=`</span></span>

<span data-ttu-id="0ce04-255">Оператор присваивания, объединяющего значение null, `??=` присваивает значение правого операнда левому операнду только в том случае, если левый операнд принимает значение null.</span><span class="sxs-lookup"><span data-stu-id="0ce04-255">The null-coalescing assignment operator `??=` assigns the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to null.</span></span> <span data-ttu-id="0ce04-256">Оператор `??=` не вычисляет правый операнд, если значение левого операнда отлично от NULL.</span><span class="sxs-lookup"><span data-stu-id="0ce04-256">The `??=` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

```powershell
$x = $null
$x ??= 100
$x
```

```Output
100
```

<span data-ttu-id="0ce04-257">В следующем примере правый операнд не вычисляется.</span><span class="sxs-lookup"><span data-stu-id="0ce04-257">In the following example, the right-hand operand won't be evaluated.</span></span>

```powershell
[string] $todaysDate = '1/10/2020'
$todaysDate ??= (Get-Date).ToShortDateString()
```

```Output
1/10/2020
```

#### <a name="null-conditional-operators--and-"></a><span data-ttu-id="0ce04-258">Условные операторы NULL `?.` и `?[]`</span><span class="sxs-lookup"><span data-stu-id="0ce04-258">Null-conditional operators `?.` and `?[]`</span></span>

> [!NOTE]
> <span data-ttu-id="0ce04-259">Этот компонент был перемещен из экспериментального в основной в PowerShell 7,1.</span><span class="sxs-lookup"><span data-stu-id="0ce04-259">This feature was moved from experimental to mainstream in PowerShell 7.1.</span></span>

<span data-ttu-id="0ce04-260">Условный оператор NULL применяет к `?.` операнду доступ к элементу,, или к нему, `?[]` только если этот операнд принимает значение, отличное от NULL; в противном случае возвращается значение null.</span><span class="sxs-lookup"><span data-stu-id="0ce04-260">A null-conditional operator applies a member access, `?.`, or element access, `?[]`, operation to its operand only if that operand evaluates to non-null; otherwise, it returns null.</span></span>

<span data-ttu-id="0ce04-261">Так как в PowerShell символ `?` может быть частью имени переменной, для использования этих операторов требуется формальное указание имени переменной.</span><span class="sxs-lookup"><span data-stu-id="0ce04-261">Since PowerShell allows `?` to be part of the variable name, formal specification of the variable name is required for using these operators.</span></span> <span data-ttu-id="0ce04-262">Поэтому имена переменных необходимо заключать в фигурные скобки `{}`, например `${a}`, в том числе если имена содержат символ `?`: `${a?}`.</span><span class="sxs-lookup"><span data-stu-id="0ce04-262">So it is required to use `{}` around the variable names like `${a}` or when `?` is part of the variable name `${a?}`.</span></span>

<span data-ttu-id="0ce04-263">В следующем примере возвращается значение **пропнаме** .</span><span class="sxs-lookup"><span data-stu-id="0ce04-263">In the following example, the value of **PropName** is returned.</span></span>

```powershell
$a = @{ PropName = 100 }
${a}?.PropName
```

```Output
100
```

<span data-ttu-id="0ce04-264">Следующий пример вернет значение null, не пытаясь получить доступ к имени члена **пропнаме**.</span><span class="sxs-lookup"><span data-stu-id="0ce04-264">The following example will return null, without trying to access the member name **PropName**.</span></span>

```powershell
$a = $null
${a}?.PropName
```

<span data-ttu-id="0ce04-265">Аналогичным образом будет возвращено значение элемента.</span><span class="sxs-lookup"><span data-stu-id="0ce04-265">Similarly, the value of the element will be returned.</span></span>

```powershell
$a = 1..10
${a}?[0]
```

```Output
1
```

<span data-ttu-id="0ce04-266">Если операнд имеет значение null, доступ к элементу отсутствует, и возвращается значение null.</span><span class="sxs-lookup"><span data-stu-id="0ce04-266">And when the operand is null, the element isn't accessed and null is returned.</span></span>

```PowerShell
$a = $null
${a}?[0]
```

> [!NOTE]
> <span data-ttu-id="0ce04-267">Так как в PowerShell символ `?` может быть частью имени переменной, для использования этих операторов требуется формальное указание имени переменной.</span><span class="sxs-lookup"><span data-stu-id="0ce04-267">Since PowerShell allows `?` to be part of the variable name, formal specification of the variable name is required for using these operators.</span></span> <span data-ttu-id="0ce04-268">Поэтому имена переменных необходимо заключать в фигурные скобки `{}`, например `${a}`, в том числе если имена содержат символ `?`: `${a?}`.</span><span class="sxs-lookup"><span data-stu-id="0ce04-268">So it is required to use `{}` around the variable names like `${a}` or when `?` is part of the variable name `${a?}`.</span></span>
>
> <span data-ttu-id="0ce04-269">Синтаксис имени переменной `${<name>}` не должен путать с `$()` оператором части выражения.</span><span class="sxs-lookup"><span data-stu-id="0ce04-269">The variable name syntax of `${<name>}` should not be confused with the `$()` subexpression operator.</span></span> <span data-ttu-id="0ce04-270">Дополнительные сведения см. в разделе Имя переменной в [about_Variables](about_Variables.md#variable-names-that-include-special-characters).</span><span class="sxs-lookup"><span data-stu-id="0ce04-270">For more information, see Variable name section of [about_Variables](about_Variables.md#variable-names-that-include-special-characters).</span></span>

## <a name="see-also"></a><span data-ttu-id="0ce04-271">См. также</span><span class="sxs-lookup"><span data-stu-id="0ce04-271">See also</span></span>

[<span data-ttu-id="0ce04-272">about_Arithmetic_Operators</span><span class="sxs-lookup"><span data-stu-id="0ce04-272">about_Arithmetic_Operators</span></span>](about_Arithmetic_Operators.md)

[<span data-ttu-id="0ce04-273">about_Assignment_Operators</span><span class="sxs-lookup"><span data-stu-id="0ce04-273">about_Assignment_Operators</span></span>](about_Assignment_Operators.md)

[<span data-ttu-id="0ce04-274">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="0ce04-274">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="0ce04-275">about_Logical_Operators</span><span class="sxs-lookup"><span data-stu-id="0ce04-275">about_Logical_Operators</span></span>](about_logical_operators.md)

[<span data-ttu-id="0ce04-276">about_Operator_Precedence</span><span class="sxs-lookup"><span data-stu-id="0ce04-276">about_Operator_Precedence</span></span>](about_operator_precedence.md)

[<span data-ttu-id="0ce04-277">about_Type_Operators</span><span class="sxs-lookup"><span data-stu-id="0ce04-277">about_Type_Operators</span></span>](about_Type_Operators.md)

[<span data-ttu-id="0ce04-278">about_Pipeline_Chain_Operators</span><span class="sxs-lookup"><span data-stu-id="0ce04-278">about_Pipeline_Chain_Operators</span></span>](about_Pipeline_Chain_Operators.md)

[<span data-ttu-id="0ce04-279">about_Split</span><span class="sxs-lookup"><span data-stu-id="0ce04-279">about_Split</span></span>](about_Split.md)

[<span data-ttu-id="0ce04-280">about_Join</span><span class="sxs-lookup"><span data-stu-id="0ce04-280">about_Join</span></span>](about_Join.md)

[<span data-ttu-id="0ce04-281">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="0ce04-281">about_Redirection</span></span>](about_Redirection.md)
