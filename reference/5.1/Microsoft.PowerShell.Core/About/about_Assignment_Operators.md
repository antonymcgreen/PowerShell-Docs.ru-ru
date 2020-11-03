---
description: Описывает использование операторов для присвоения значений переменным.
keywords: powershell,командлет
ms.date: 04/26/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_assignment_operators?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Assignment_Operators
ms.openlocfilehash: b9cb0f6a972ef627b7ce2621db489896992b406e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232073"
---
# <a name="about-assignment-operators"></a><span data-ttu-id="7bd32-104">Сведения об операторах присваивания</span><span class="sxs-lookup"><span data-stu-id="7bd32-104">About Assignment Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="7bd32-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="7bd32-105">Short description</span></span>
<span data-ttu-id="7bd32-106">Описывает использование операторов для присвоения значений переменным.</span><span class="sxs-lookup"><span data-stu-id="7bd32-106">Describes how to use operators to assign values to variables.</span></span>

## <a name="long-description"></a><span data-ttu-id="7bd32-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="7bd32-107">Long description</span></span>

<span data-ttu-id="7bd32-108">Операторы присваивания присваивают одному или нескольким значениям переменной.</span><span class="sxs-lookup"><span data-stu-id="7bd32-108">Assignment operators assign one or more values to a variable.</span></span> <span data-ttu-id="7bd32-109">Они могут выполнять числовые операции над значениями перед назначением.</span><span class="sxs-lookup"><span data-stu-id="7bd32-109">They can perform numeric operations on the values before the assignment.</span></span>

<span data-ttu-id="7bd32-110">PowerShell поддерживает следующие операторы присваивания.</span><span class="sxs-lookup"><span data-stu-id="7bd32-110">PowerShell supports the following assignment operators.</span></span>

|<span data-ttu-id="7bd32-111">Оператор</span><span class="sxs-lookup"><span data-stu-id="7bd32-111">Operator</span></span>|<span data-ttu-id="7bd32-112">Описание</span><span class="sxs-lookup"><span data-stu-id="7bd32-112">Description</span></span>                                                  |
|--------|-------------------------------------------------------------|
|=       |<span data-ttu-id="7bd32-113">Устанавливает значение переменной в указанное значение.</span><span class="sxs-lookup"><span data-stu-id="7bd32-113">Sets the value of a variable to the specified value.</span></span>         |
|+=      |<span data-ttu-id="7bd32-114">Увеличивает значение переменной по указанному значению или</span><span class="sxs-lookup"><span data-stu-id="7bd32-114">Increases the value of a variable by the specified value, or</span></span> |
|        |<span data-ttu-id="7bd32-115">Добавляет указанное значение к существующему значению.</span><span class="sxs-lookup"><span data-stu-id="7bd32-115">appends the specified value to the existing value.</span></span>           |
|-=      |<span data-ttu-id="7bd32-116">Уменьшает значение переменной на указанное значение.</span><span class="sxs-lookup"><span data-stu-id="7bd32-116">Decreases the value of a variable by the specified value.</span></span>    |
|*=      |<span data-ttu-id="7bd32-117">Умножает значение переменной на указанное значение или</span><span class="sxs-lookup"><span data-stu-id="7bd32-117">Multiplies the value of a variable by the specified value, or</span></span>|
|        |<span data-ttu-id="7bd32-118">Добавляет указанное значение к существующему значению.</span><span class="sxs-lookup"><span data-stu-id="7bd32-118">appends the specified value to the existing value.</span></span>           |
|/=      |<span data-ttu-id="7bd32-119">Делит значение переменной на указанное значение.</span><span class="sxs-lookup"><span data-stu-id="7bd32-119">Divides the value of a variable by the specified value.</span></span>      |
|%=      |<span data-ttu-id="7bd32-120">Делит значение переменной на указанное значение и</span><span class="sxs-lookup"><span data-stu-id="7bd32-120">Divides the value of a variable by the specified value and</span></span>   |
|        |<span data-ttu-id="7bd32-121">затем присваивает переменной остаток (остаток от деления).</span><span class="sxs-lookup"><span data-stu-id="7bd32-121">then assigns the remainder (modulus) to the variable.</span></span>        |
|++      |<span data-ttu-id="7bd32-122">Увеличивает значение переменной, назначаемое свойство или</span><span class="sxs-lookup"><span data-stu-id="7bd32-122">Increases the value of a variable, assignable property, or</span></span>   |
|        |<span data-ttu-id="7bd32-123">элемент массива на 1.</span><span class="sxs-lookup"><span data-stu-id="7bd32-123">array element by 1.</span></span>                                          |
|--      |<span data-ttu-id="7bd32-124">Уменьшает значение переменной, присваиваемого свойства или</span><span class="sxs-lookup"><span data-stu-id="7bd32-124">Decreases the value of a variable, assignable property, or</span></span>   |
|        |<span data-ttu-id="7bd32-125">элемент массива на 1.</span><span class="sxs-lookup"><span data-stu-id="7bd32-125">array element by 1.</span></span>                                          |

## <a name="syntax"></a><span data-ttu-id="7bd32-126">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7bd32-126">Syntax</span></span>

<span data-ttu-id="7bd32-127">Синтаксис операторов присваивания выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7bd32-127">The syntax of the assignment operators is as follows:</span></span>

<span data-ttu-id="7bd32-128">`<assignable-expression>` `<assignment-operator>` `<value>`</span><span class="sxs-lookup"><span data-stu-id="7bd32-128">`<assignable-expression>` `<assignment-operator>` `<value>`</span></span>

<span data-ttu-id="7bd32-129">Назначаемые выражения включают переменные и свойства.</span><span class="sxs-lookup"><span data-stu-id="7bd32-129">Assignable expressions include variables and properties.</span></span> <span data-ttu-id="7bd32-130">Значением может быть одиночное значение, массив значений, команда, выражение или оператор.</span><span class="sxs-lookup"><span data-stu-id="7bd32-130">The value can be a single value, an array of values, or a command, expression, or statement.</span></span>

<span data-ttu-id="7bd32-131">Операторы инкремента и декремента являются унарными операторами.</span><span class="sxs-lookup"><span data-stu-id="7bd32-131">The increment and decrement operators are unary operators.</span></span> <span data-ttu-id="7bd32-132">Каждый из них имеет префиксную и постфиксную версии.</span><span class="sxs-lookup"><span data-stu-id="7bd32-132">Each has prefix and postfix versions.</span></span>

`<assignable-expression><operator>`
`<operator><assignable-expression>`

<span data-ttu-id="7bd32-133">Выражение, присваиваемое, должно быть числом или должно быть преобразовано в число.</span><span class="sxs-lookup"><span data-stu-id="7bd32-133">The assignable expression must be a number or it must be convertible to a number.</span></span>

## <a name="assigning-values"></a><span data-ttu-id="7bd32-134">Присвоение значений</span><span class="sxs-lookup"><span data-stu-id="7bd32-134">Assigning values</span></span>

<span data-ttu-id="7bd32-135">Переменные — это именованные пространства памяти, в которых хранятся значения.</span><span class="sxs-lookup"><span data-stu-id="7bd32-135">Variables are named memory spaces that store values.</span></span> <span data-ttu-id="7bd32-136">Значения в переменных хранятся с помощью оператора присваивания `=` .</span><span class="sxs-lookup"><span data-stu-id="7bd32-136">You store the values in variables by using the assignment operator `=`.</span></span> <span data-ttu-id="7bd32-137">Новое значение может заменить существующее значение переменной или добавить новое значение к существующему значению.</span><span class="sxs-lookup"><span data-stu-id="7bd32-137">The new value can replace the existing value of the variable, or you can append a new value to the existing value.</span></span>

<span data-ttu-id="7bd32-138">Базовым оператором присваивания является знак равенства `=` `(ASCII 61)` .</span><span class="sxs-lookup"><span data-stu-id="7bd32-138">The basic assignment operator is the equal sign `=` `(ASCII 61)`.</span></span> <span data-ttu-id="7bd32-139">Например, следующая инструкция присваивает переменной PowerShell значение `$MyShell` :</span><span class="sxs-lookup"><span data-stu-id="7bd32-139">For example, the following statement assigns the value PowerShell to the `$MyShell` variable:</span></span>

```powershell
$MyShell = "PowerShell"
```

<span data-ttu-id="7bd32-140">При присвоении значения переменной в PowerShell переменная создается, если она еще не существовала.</span><span class="sxs-lookup"><span data-stu-id="7bd32-140">When you assign a value to a variable in PowerShell, the variable is created if it did not already exist.</span></span> <span data-ttu-id="7bd32-141">Например, первая из следующих двух инструкций присваивания создает `$a` переменную и присваивает ей значение 6 `$a` .</span><span class="sxs-lookup"><span data-stu-id="7bd32-141">For example, the first of the following two assignment statements creates the `$a` variable and assigns a value of 6 to `$a`.</span></span> <span data-ttu-id="7bd32-142">Вторая инструкция присваивания присваивает значение 12 `$a` .</span><span class="sxs-lookup"><span data-stu-id="7bd32-142">The second assignment statement assigns a value of 12 to `$a`.</span></span> <span data-ttu-id="7bd32-143">Первая инструкция создает новую переменную.</span><span class="sxs-lookup"><span data-stu-id="7bd32-143">The first statement creates a new variable.</span></span> <span data-ttu-id="7bd32-144">Вторая инструкция изменяет только свое значение:</span><span class="sxs-lookup"><span data-stu-id="7bd32-144">The second statement changes only its value:</span></span>

```powershell
$a = 6
$a = 12
```

<span data-ttu-id="7bd32-145">Переменные в PowerShell не имеют определенного типа данных, пока они не будут преобразованы.</span><span class="sxs-lookup"><span data-stu-id="7bd32-145">Variables in PowerShell do not have a specific data type unless you cast them.</span></span>
<span data-ttu-id="7bd32-146">Если переменная содержит только один объект, переменная принимает тип данных этого объекта.</span><span class="sxs-lookup"><span data-stu-id="7bd32-146">When a variable contains only one object, the variable takes the data type of that object.</span></span> <span data-ttu-id="7bd32-147">Если переменная содержит коллекцию объектов, переменная имеет тип данных System. Object.</span><span class="sxs-lookup"><span data-stu-id="7bd32-147">When a variable contains a collection of objects, the variable has the System.Object data type.</span></span> <span data-ttu-id="7bd32-148">Таким образом, в коллекцию можно назначить любой тип объекта.</span><span class="sxs-lookup"><span data-stu-id="7bd32-148">Therefore, you can assign any type of object to the collection.</span></span> <span data-ttu-id="7bd32-149">В следующем примере показано, как добавить объекты Process, объекты служб, строки и целые числа в переменную без создания ошибки:</span><span class="sxs-lookup"><span data-stu-id="7bd32-149">The following example shows that you can add process objects, service objects, strings, and integers to a variable without generating an error:</span></span>

```powershell
$a = Get-Process
$a += Get-Service
$a += "string"
$a += 12
```

<span data-ttu-id="7bd32-150">Поскольку оператор присваивания `=` имеет более низкий приоритет, чем оператор конвейера `|` , круглые скобки не являются обязательными для назначения результата конвейера команды переменной.</span><span class="sxs-lookup"><span data-stu-id="7bd32-150">Because the assignment operator `=` has a lower precedence than the pipeline operator `|`, parentheses are not required to assign the result of a command pipeline to a variable.</span></span> <span data-ttu-id="7bd32-151">Например, следующая команда сортирует службы на компьютере, а затем присваивает этой переменной отсортированные службы `$a` :</span><span class="sxs-lookup"><span data-stu-id="7bd32-151">For example, the following command sorts the services on the computer and then assigns the sorted services to the `$a` variable:</span></span>

```powershell
$a = Get-Service | Sort-Object -Property name
```

<span data-ttu-id="7bd32-152">Можно также присвоить значение, созданное инструкцией, переменной, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="7bd32-152">You can also assign the value created by a statement to a variable, as in the following example:</span></span>

```powershell
$a = if ($b -lt 0) { 0 } else { $b }
```

<span data-ttu-id="7bd32-153">В этом примере ноль присваивается `$a` переменной, если значение `$b` меньше нуля.</span><span class="sxs-lookup"><span data-stu-id="7bd32-153">This example assigns zero to the `$a` variable if the value of `$b` is less than zero.</span></span> <span data-ttu-id="7bd32-154">Он присваивает значение значению, `$b` `$a` Если значение не `$b` меньше нуля.</span><span class="sxs-lookup"><span data-stu-id="7bd32-154">It assigns the value of `$b` to `$a` if the value of `$b` is not less than zero.</span></span>

### <a name="the-assignment-operator"></a><span data-ttu-id="7bd32-155">Оператор присваивания</span><span class="sxs-lookup"><span data-stu-id="7bd32-155">The assignment operator</span></span>

<span data-ttu-id="7bd32-156">Оператор присваивания `=` присваивает значения переменным.</span><span class="sxs-lookup"><span data-stu-id="7bd32-156">The assignment operator `=` assigns values to variables.</span></span> <span data-ttu-id="7bd32-157">Если переменная уже имеет значение, оператор присваивания `=` заменяет значение без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="7bd32-157">If the variable already has a value, the assignment operator `=` replaces the value without warning.</span></span>

<span data-ttu-id="7bd32-158">Следующая инструкция присваивает переменной целочисленное значение 6 `$a` :</span><span class="sxs-lookup"><span data-stu-id="7bd32-158">The following statement assigns the integer value 6 to the `$a` variable:</span></span>

```powershell
$a = 6
```

<span data-ttu-id="7bd32-159">Чтобы присвоить строковое значение переменной, заключите строковое значение в кавычки следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7bd32-159">To assign a string value to a variable, enclose the string value in quotation marks, as follows:</span></span>

```powershell
$a = "baseball"
```

<span data-ttu-id="7bd32-160">Чтобы присвоить переменной массив (несколько значений), разделите значения запятыми следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7bd32-160">To assign an array (multiple values) to a variable, separate the values with commas, as follows:</span></span>

```powershell
$a = "apple", "orange", "lemon", "grape"
```

<span data-ttu-id="7bd32-161">Чтобы присвоить переменной хэш-таблицу, используйте стандартную нотацию хэш-таблицы в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7bd32-161">To assign a hash table to a variable, use the standard hash table notation in PowerShell.</span></span> <span data-ttu-id="7bd32-162">Введите знак AT, `@` а затем пары "ключ-значение", разделенные точкой с запятой `;` и заключенные в фигурные скобки `{ }` .</span><span class="sxs-lookup"><span data-stu-id="7bd32-162">Type an at sign `@` followed by key/value pairs that are separated by semicolons `;` and enclosed in braces `{ }`.</span></span> <span data-ttu-id="7bd32-163">Например, чтобы присвоить переменной хэш-таблицу `$a` , введите:</span><span class="sxs-lookup"><span data-stu-id="7bd32-163">For example, to assign a hash table to the `$a` variable, type:</span></span>

```powershell
$a = @{one=1; two=2; three=3}
```

<span data-ttu-id="7bd32-164">Чтобы присвоить шестнадцатеричные значения переменной, перед значением укажите `0x` .</span><span class="sxs-lookup"><span data-stu-id="7bd32-164">To assign hexadecimal values to a variable, precede the value with `0x`.</span></span>
<span data-ttu-id="7bd32-165">PowerShell преобразует шестнадцатеричное значение (0x10) в десятичное значение (в данном случае 16) и присваивает `$a` переменной значение.</span><span class="sxs-lookup"><span data-stu-id="7bd32-165">PowerShell converts the hexadecimal value (0x10) to a decimal value (in this case, 16) and assigns that value to the `$a` variable.</span></span> <span data-ttu-id="7bd32-166">Например, чтобы присвоить переменной значение 0x10 `$a` , введите:</span><span class="sxs-lookup"><span data-stu-id="7bd32-166">For example, to assign a value of 0x10 to the `$a` variable, type:</span></span>

```powershell
$a = 0x10
```

<span data-ttu-id="7bd32-167">Чтобы присвоить переменной экспоненциальное значение, введите корневой номер, букву `e` и число, кратное 10.</span><span class="sxs-lookup"><span data-stu-id="7bd32-167">To assign an exponential value to a variable, type the root number, the letter `e`, and a number that represents a multiple of 10.</span></span> <span data-ttu-id="7bd32-168">Например, чтобы присвоить значение 3,1415 для переменной степени 1 000 `$a` , введите:</span><span class="sxs-lookup"><span data-stu-id="7bd32-168">For example, to assign a value of 3.1415 to the power of 1,000 to the `$a` variable, type:</span></span>

```powershell
$a = 3.1415e3
```

<span data-ttu-id="7bd32-169">PowerShell также может преобразовывать килобайты `KB` , мегабайты `MB` и гигабайты `GB` в байты.</span><span class="sxs-lookup"><span data-stu-id="7bd32-169">PowerShell can also convert kilobytes `KB`, megabytes `MB`, and gigabytes `GB` into bytes.</span></span> <span data-ttu-id="7bd32-170">Например, чтобы присвоить переменной значение 10 килобайт `$a` , введите:</span><span class="sxs-lookup"><span data-stu-id="7bd32-170">For example, to assign a value of 10 kilobytes to the `$a` variable, type:</span></span>

```powershell
$a = 10kb
```

### <a name="the-assignment-by-addition-operator"></a><span data-ttu-id="7bd32-171">Оператор присваивания с помощью оператора сложения</span><span class="sxs-lookup"><span data-stu-id="7bd32-171">The assignment by addition operator</span></span>

<span data-ttu-id="7bd32-172">Оператор присваивания путем сложения `+=` либо увеличивает значение переменной, либо добавляет указанное значение к существующему значению.</span><span class="sxs-lookup"><span data-stu-id="7bd32-172">The assignment by addition operator `+=` either increments the value of a variable or appends the specified value to the existing value.</span></span> <span data-ttu-id="7bd32-173">Действие зависит от того, имеет ли переменная числовой или строковый тип и указывает, содержит ли переменная одно значение (скалярное) или несколько значений (коллекция).</span><span class="sxs-lookup"><span data-stu-id="7bd32-173">The action depends on whether the variable has a numeric or string type and whether the variable contains a single value (a scalar) or multiple values (a collection).</span></span>

<span data-ttu-id="7bd32-174">`+=`Оператор объединяет две операции.</span><span class="sxs-lookup"><span data-stu-id="7bd32-174">The `+=` operator combines two operations.</span></span> <span data-ttu-id="7bd32-175">Сначала он добавляет, а затем назначает.</span><span class="sxs-lookup"><span data-stu-id="7bd32-175">First, it adds, and then it assigns.</span></span>
<span data-ttu-id="7bd32-176">Поэтому следующие операторы эквивалентны:</span><span class="sxs-lookup"><span data-stu-id="7bd32-176">Therefore, the following statements are equivalent:</span></span>

```powershell
$a += 2
$a = ($a + 2)
```

<span data-ttu-id="7bd32-177">Если переменная содержит одно числовое значение, `+=` оператор увеличивает существующее значение на величину в правой части оператора.</span><span class="sxs-lookup"><span data-stu-id="7bd32-177">When the variable contains a single numeric value, the `+=` operator increments the existing value by the amount on the right side of the operator.</span></span> <span data-ttu-id="7bd32-178">Затем оператор присваивает результирующее значение переменной.</span><span class="sxs-lookup"><span data-stu-id="7bd32-178">Then, the operator assigns the resulting value to the variable.</span></span> <span data-ttu-id="7bd32-179">В следующем примере показано, как использовать `+=` оператор для увеличения значения переменной:</span><span class="sxs-lookup"><span data-stu-id="7bd32-179">The following example shows how to use the `+=` operator to increase the value of a variable:</span></span>

```powershell
$a = 4
$a += 2
$a
```

```
6
```

<span data-ttu-id="7bd32-180">Если значение переменной является строкой, то значение справа от оператора добавляется к строке следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7bd32-180">When the value of the variable is a string, the value on the right side of the operator is appended to the string, as follows:</span></span>

```powershell
$a = "Windows"
$a += " PowerShell"
$a
```

```
Windows PowerShell
```

<span data-ttu-id="7bd32-181">Если значение переменной является массивом, `+=` оператор добавляет значения в правой части оператора в массив.</span><span class="sxs-lookup"><span data-stu-id="7bd32-181">When the value of the variable is an array, the `+=` operator appends the values on the right side of the operator to the array.</span></span> <span data-ttu-id="7bd32-182">Если массив явно не вводится путем приведения, можно добавить в массив любой тип значения, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="7bd32-182">Unless the array is explicitly typed by casting, you can append any type of value to the array, as follows:</span></span>

```powershell
$a = 1,2,3
$a += 2
$a
```

```
1
2
3
2
```

<span data-ttu-id="7bd32-183">and</span><span class="sxs-lookup"><span data-stu-id="7bd32-183">and</span></span>

```powershell
$a += "String"
$a
```

```
1
2
3
2
String
```

<span data-ttu-id="7bd32-184">Если значение переменной является хэш-таблицей, `+=` оператор добавляет значение в правой части оператора в хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="7bd32-184">When the value of a variable is a hash table, the `+=` operator appends the value on the right side of the operator to the hash table.</span></span> <span data-ttu-id="7bd32-185">Однако, поскольку единственным типом, который можно добавить в хэш-таблицу, является другая хэш-таблица, все остальные назначения завершаются ошибкой.</span><span class="sxs-lookup"><span data-stu-id="7bd32-185">However, because the only type that you can add to a hash table is another hash table, all other assignments fail.</span></span>

<span data-ttu-id="7bd32-186">Например, следующая команда назначает хэш-таблицу `$a` переменной.</span><span class="sxs-lookup"><span data-stu-id="7bd32-186">For example, the following command assigns a hash table to the `$a` variable.</span></span>
<span data-ttu-id="7bd32-187">Затем он использует оператор, `+=` чтобы присоединить другую хэш-таблицу к существующей хэш-таблице, фактически добавив новую пару «ключ-значение» в существующую хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="7bd32-187">Then, it uses the `+=` operator to append another hash table to the existing hash table, effectively adding a new key/value pair to the existing hash table.</span></span>
<span data-ttu-id="7bd32-188">Эта команда выполняется, как показано в выходных данных:</span><span class="sxs-lookup"><span data-stu-id="7bd32-188">This command succeeds, as shown in the output:</span></span>

```powershell
$a = @{a = 1; b = 2; c = 3}
$a += @{mode = "write"}
$a
```

```
Name                           Value
----                           -----
a                              1
b                              2
mode                           write
c                              3
```

<span data-ttu-id="7bd32-189">Следующая команда пытается добавить целое число "1" в хэш-таблицу в `$a` переменной.</span><span class="sxs-lookup"><span data-stu-id="7bd32-189">The following command attempts to append an integer "1" to the hash table in the `$a` variable.</span></span> <span data-ttu-id="7bd32-190">Эта команда завершается ошибкой:</span><span class="sxs-lookup"><span data-stu-id="7bd32-190">This command fails:</span></span>

```powershell
$a = @{a = 1; b = 2; c = 3}
$a += 1
```

```
You can add another hash table only to a hash table.
At line:1 char:6
+ $a += <<<<  1
```

### <a name="the-assignment-by-subtraction-operator"></a><span data-ttu-id="7bd32-191">Оператор присваивания с вычитанием</span><span class="sxs-lookup"><span data-stu-id="7bd32-191">The assignment by subtraction operator</span></span>

<span data-ttu-id="7bd32-192">Оператор присваивания с вычитанием `-=` уменьшает значение переменной на значение, указанное в правой части оператора.</span><span class="sxs-lookup"><span data-stu-id="7bd32-192">The assignment by subtraction operator `-=` decrements the value of a variable by the value that is specified on the right side of the operator.</span></span> <span data-ttu-id="7bd32-193">Этот оператор не может использоваться со строковыми переменными и не может использоваться для удаления элемента из коллекции.</span><span class="sxs-lookup"><span data-stu-id="7bd32-193">This operator cannot be used with string variables, and it cannot be used to remove an element from a collection.</span></span>

<span data-ttu-id="7bd32-194">`-=`Оператор объединяет две операции.</span><span class="sxs-lookup"><span data-stu-id="7bd32-194">The `-=` operator combines two operations.</span></span> <span data-ttu-id="7bd32-195">Сначала вычитается, а затем назначается.</span><span class="sxs-lookup"><span data-stu-id="7bd32-195">First, it subtracts, and then it assigns.</span></span> <span data-ttu-id="7bd32-196">Поэтому следующие операторы эквивалентны:</span><span class="sxs-lookup"><span data-stu-id="7bd32-196">Therefore, the following statements are equivalent:</span></span>

```powershell
$a -= 2
$a = ($a - 2)
```

<span data-ttu-id="7bd32-197">В следующем примере показано использование `-=` оператора для уменьшения значения переменной:</span><span class="sxs-lookup"><span data-stu-id="7bd32-197">The following example shows how to use of the `-=` operator to decrease the value of a variable:</span></span>

```powershell
$a = 8
$a -= 2
$a
```

```
6
```

<span data-ttu-id="7bd32-198">`-=`Оператор присваивания также можно использовать для уменьшения значения элемента числового массива.</span><span class="sxs-lookup"><span data-stu-id="7bd32-198">You can also use the `-=` assignment operator to decrease the value of a member of a numeric array.</span></span> <span data-ttu-id="7bd32-199">Для этого укажите индекс элемента массива, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="7bd32-199">To do this, specify the index of the array element that you want to change.</span></span> <span data-ttu-id="7bd32-200">В следующем примере значение третьего элемента массива (элемент 2) уменьшается на 1:</span><span class="sxs-lookup"><span data-stu-id="7bd32-200">In the following example, the value of the third element of an array (element 2) is decreased by 1:</span></span>

```powershell
$a = 1,2,3
$a[2] -= 1
$a
```

```
1
2
2
```

<span data-ttu-id="7bd32-201">Нельзя использовать `-=` оператор для удаления значений переменной.</span><span class="sxs-lookup"><span data-stu-id="7bd32-201">You cannot use the `-=` operator to delete the values of a variable.</span></span> <span data-ttu-id="7bd32-202">Чтобы удалить все значения, назначенные переменной, используйте командлеты [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item) или [clear-variable](xref:Microsoft.PowerShell.Utility.Clear-Variable) , чтобы присвоить значение `$null` `""` переменной или.</span><span class="sxs-lookup"><span data-stu-id="7bd32-202">To delete all the values that are assigned to a variable, use the [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item) or [Clear-Variable](xref:Microsoft.PowerShell.Utility.Clear-Variable) cmdlets to assign a value of `$null` or `""` to the variable.</span></span>

```powershell
$a = $null
```

<span data-ttu-id="7bd32-203">Чтобы удалить определенное значение из массива, используйте нотацию массива, чтобы присвоить значение `$null` конкретному элементу.</span><span class="sxs-lookup"><span data-stu-id="7bd32-203">To delete a particular value from an array, use array notation to assign a value of `$null` to the particular item.</span></span> <span data-ttu-id="7bd32-204">Например, следующая инструкция удаляет второе значение (позиция индекса 1) из массива.</span><span class="sxs-lookup"><span data-stu-id="7bd32-204">For example, the following statement deletes the second value (index position 1) from an array:</span></span>

```powershell
$a = 1,2,3
$a
```

```
1
2
3
```

```powershell
$a[1] = $null
$a
```

```
1
3
```

<span data-ttu-id="7bd32-205">Чтобы удалить переменную, используйте командлет [Remove-Variable](xref:Microsoft.PowerShell.Utility.Remove-Variable) .</span><span class="sxs-lookup"><span data-stu-id="7bd32-205">To delete a variable, use the [Remove-Variable](xref:Microsoft.PowerShell.Utility.Remove-Variable) cmdlet.</span></span> <span data-ttu-id="7bd32-206">Этот метод полезен, если переменная явно приведена к определенному типу данных и требуется нетипизированная переменная.</span><span class="sxs-lookup"><span data-stu-id="7bd32-206">This method is useful when the variable is explicitly cast to a particular data type, and you want an untyped variable.</span></span> <span data-ttu-id="7bd32-207">Следующая команда удаляет `$a` переменную:</span><span class="sxs-lookup"><span data-stu-id="7bd32-207">The following command deletes the `$a` variable:</span></span>

```powershell
Remove-Variable -Name a
```

### <a name="the-assignment-by-multiplication-operator"></a><span data-ttu-id="7bd32-208">Назначение по оператору умножения</span><span class="sxs-lookup"><span data-stu-id="7bd32-208">The assignment by multiplication operator</span></span>

<span data-ttu-id="7bd32-209">Оператор присваивания по умножению `*=` умножает числовое значение или добавляет указанное число копий строкового значения переменной.</span><span class="sxs-lookup"><span data-stu-id="7bd32-209">The assignment by multiplication operator `*=` multiplies a numeric value or appends the specified number of copies of the string value of a variable.</span></span>

<span data-ttu-id="7bd32-210">Если переменная содержит одно числовое значение, это значение умножается на значение в правой части оператора.</span><span class="sxs-lookup"><span data-stu-id="7bd32-210">When a variable contains a single numeric value, that value is multiplied by the value on the right side of the operator.</span></span> <span data-ttu-id="7bd32-211">Например, в следующем примере показано использование `*=` оператора для умножения значения переменной:</span><span class="sxs-lookup"><span data-stu-id="7bd32-211">For example, the following example shows how to use the `*=` operator to multiply the value of a variable:</span></span>

```powershell
$a = 3
$a *= 4
$a
```

```
12
```

<span data-ttu-id="7bd32-212">В этом случае `*=` оператор объединяет две операции.</span><span class="sxs-lookup"><span data-stu-id="7bd32-212">In this case, the `*=` operator combines two operations.</span></span> <span data-ttu-id="7bd32-213">Сначала он умножается, а затем назначается.</span><span class="sxs-lookup"><span data-stu-id="7bd32-213">First, it multiplies, and then it assigns.</span></span> <span data-ttu-id="7bd32-214">Поэтому следующие операторы эквивалентны:</span><span class="sxs-lookup"><span data-stu-id="7bd32-214">Therefore, the following statements are equivalent:</span></span>

```powershell
$a *= 2
$a = ($a * 2)
```

<span data-ttu-id="7bd32-215">Если переменная содержит строковое значение, PowerShell добавляет указанное число строк к значению следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7bd32-215">When a variable contains a string value, PowerShell appends the specified number of strings to the value, as follows:</span></span>

```powershell
$a = "file"
$a *= 4
$a
```

```
filefilefilefile
```

<span data-ttu-id="7bd32-216">Чтобы умножить элемент массива, используйте индекс для задания элемента, который необходимо умножить.</span><span class="sxs-lookup"><span data-stu-id="7bd32-216">To multiply an element of an array, use an index to identify the element that you want to multiply.</span></span> <span data-ttu-id="7bd32-217">Например, следующая команда умножает первый элемент массива (позиция индекса 0) на 2:</span><span class="sxs-lookup"><span data-stu-id="7bd32-217">For example, the following command multiplies the first element in the array (index position 0) by 2:</span></span>

```powershell
$a[0] *= 2
```

### <a name="the-assignment-by-division-operator"></a><span data-ttu-id="7bd32-218">Оператор присваивания по делениям</span><span class="sxs-lookup"><span data-stu-id="7bd32-218">The assignment by division operator</span></span>

<span data-ttu-id="7bd32-219">Оператор присваивания по делениям `/=` делит числовое значение на значение, указанное в правой части оператора.</span><span class="sxs-lookup"><span data-stu-id="7bd32-219">The assignment by division operator `/=` divides a numeric value by the value that is specified on the right side of the operator.</span></span> <span data-ttu-id="7bd32-220">Оператор не может использоваться со строковыми переменными.</span><span class="sxs-lookup"><span data-stu-id="7bd32-220">The operator cannot be used with string variables.</span></span>

<span data-ttu-id="7bd32-221">`/=`Оператор объединяет две операции.</span><span class="sxs-lookup"><span data-stu-id="7bd32-221">The `/=` operator combines two operations.</span></span> <span data-ttu-id="7bd32-222">Сначала он делит, а затем назначает.</span><span class="sxs-lookup"><span data-stu-id="7bd32-222">First, it divides, and then it assigns.</span></span> <span data-ttu-id="7bd32-223">Поэтому следующие две инструкции эквивалентны:</span><span class="sxs-lookup"><span data-stu-id="7bd32-223">Therefore, the following two statements are equivalent:</span></span>

```powershell
$a /= 2
$a = ($a / 2)
```

<span data-ttu-id="7bd32-224">Например, следующая команда использует `/=` оператор для деления значения переменной:</span><span class="sxs-lookup"><span data-stu-id="7bd32-224">For example, the following command uses the `/=` operator to divide the value of a variable:</span></span>

```powershell
$a = 8
$a /=2
$a
```

```
4
```

<span data-ttu-id="7bd32-225">Чтобы разделить элемент массива, используйте индекс для задания элемента, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="7bd32-225">To divide an element of an array, use an index to identify the element that you want to change.</span></span> <span data-ttu-id="7bd32-226">Например, следующая команда делит второй элемент массива (позиция индекса 1) на 2:</span><span class="sxs-lookup"><span data-stu-id="7bd32-226">For example, the following command divides the second element in the array (index position 1) by 2:</span></span>

```powershell
$a[1] /= 2
```

### <a name="the-assignment-by-modulus-operator"></a><span data-ttu-id="7bd32-227">Оператор присваивания по модулю</span><span class="sxs-lookup"><span data-stu-id="7bd32-227">The assignment by modulus operator</span></span>

<span data-ttu-id="7bd32-228">Оператор присваивания по модулю `%=` делит значение переменной на значение в правой части оператора.</span><span class="sxs-lookup"><span data-stu-id="7bd32-228">The assignment by modulus operator `%=` divides the value of a variable by the value on the right side of the operator.</span></span> <span data-ttu-id="7bd32-229">Затем `%=` оператор присваивает переменной остаток (известный как модуль).</span><span class="sxs-lookup"><span data-stu-id="7bd32-229">Then, the `%=` operator assigns the remainder (known as the modulus) to the variable.</span></span> <span data-ttu-id="7bd32-230">Этот оператор можно использовать, только если переменная содержит одно числовое значение.</span><span class="sxs-lookup"><span data-stu-id="7bd32-230">You can use this operator only when a variable contains a single numeric value.</span></span> <span data-ttu-id="7bd32-231">Этот оператор нельзя использовать, если переменная содержит строковую переменную или массив.</span><span class="sxs-lookup"><span data-stu-id="7bd32-231">You cannot use this operator when a variable contains a string variable or an array.</span></span>

<span data-ttu-id="7bd32-232">`%=`Оператор объединяет две операции.</span><span class="sxs-lookup"><span data-stu-id="7bd32-232">The `%=` operator combines two operations.</span></span> <span data-ttu-id="7bd32-233">Сначала он делит и определяет остаток, а затем назначает остаток переменной.</span><span class="sxs-lookup"><span data-stu-id="7bd32-233">First, it divides and determines the remainder, and then it assigns the remainder to the variable.</span></span> <span data-ttu-id="7bd32-234">Поэтому следующие операторы эквивалентны:</span><span class="sxs-lookup"><span data-stu-id="7bd32-234">Therefore, the following statements are equivalent:</span></span>

```powershell
$a %= 2
$a = ($a % 2)
```

<span data-ttu-id="7bd32-235">В следующем примере показано, как использовать `%=` оператор для сохранения модуля частного:</span><span class="sxs-lookup"><span data-stu-id="7bd32-235">The following example shows how to use the `%=` operator to save the modulus of a quotient:</span></span>

```powershell
$a = 7
$a %= 4
$a
```

```
3
```

## <a name="the-increment-and-decrement-operators"></a><span data-ttu-id="7bd32-236">Операторы инкремента и декремента</span><span class="sxs-lookup"><span data-stu-id="7bd32-236">The increment and decrement operators</span></span>

<span data-ttu-id="7bd32-237">Оператор инкремента `++` увеличивает значение переменной на 1.</span><span class="sxs-lookup"><span data-stu-id="7bd32-237">The increment operator `++` increases the value of a variable by 1.</span></span> <span data-ttu-id="7bd32-238">При использовании оператора инкремента в простой инструкции значение не возвращается.</span><span class="sxs-lookup"><span data-stu-id="7bd32-238">When you use the increment operator in a simple statement, no value is returned.</span></span> <span data-ttu-id="7bd32-239">Чтобы просмотреть результат, отобразите значение переменной следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7bd32-239">To view the result, display the value of the variable, as follows:</span></span>

```powershell
$a = 7
++$a
$a
```

```
8
```

<span data-ttu-id="7bd32-240">Чтобы принудительно вернуть значение, заключите переменную и оператор в круглые скобки следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7bd32-240">To force a value to be returned, enclose the variable and the operator in parentheses, as follows:</span></span>

```powershell
$a = 7
(++$a)
```

```
8
```

<span data-ttu-id="7bd32-241">Оператор инкремента может быть помещен перед переменной (prefix) или после нее (постфикс).</span><span class="sxs-lookup"><span data-stu-id="7bd32-241">The increment operator can be placed before (prefix) or after (postfix) a variable.</span></span> <span data-ttu-id="7bd32-242">Префиксная версия оператора увеличивает переменную перед использованием ее значения в инструкции следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7bd32-242">The prefix version of the operator increments a variable before its value is used in the statement, as follows:</span></span>

```powershell
$a = 7
$c = ++$a
$a
```

```
8
```

```powershell
$c
```

```
8
```

<span data-ttu-id="7bd32-243">Постфиксная версия оператора увеличивает переменную после использования ее значения в инструкции.</span><span class="sxs-lookup"><span data-stu-id="7bd32-243">The postfix version of the operator increments a variable after its value is used in the statement.</span></span> <span data-ttu-id="7bd32-244">В следующем примере `$c` `$a` переменные и имеют разные значения, так как перед изменениями присваивается значение `$c` `$a` .</span><span class="sxs-lookup"><span data-stu-id="7bd32-244">In the following example, the `$c` and `$a` variables have different values because the value is assigned to `$c` before `$a` changes:</span></span>

```powershell
$a = 7
$c = $a++
$a
```

```
8
```

```powershell
$c
```

```
7
```

<span data-ttu-id="7bd32-245">Оператор декремента `--` уменьшает значение переменной на 1.</span><span class="sxs-lookup"><span data-stu-id="7bd32-245">The decrement operator `--` decreases the value of a variable by 1.</span></span> <span data-ttu-id="7bd32-246">Как и в случае с оператором инкремента, при использовании оператора в простой инструкции значение не возвращается.</span><span class="sxs-lookup"><span data-stu-id="7bd32-246">As with the increment operator, no value is returned when you use the operator in a simple statement.</span></span> <span data-ttu-id="7bd32-247">Для возврата значения используйте круглые скобки следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7bd32-247">Use parentheses to return a value, as follows:</span></span>

```powershell
$a = 7
--$a
$a
```

```
6
```

```powershell
(--$a)
```

```
5
```

<span data-ttu-id="7bd32-248">Префиксная версия оператора уменьшает переменную перед использованием ее значения в инструкции следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7bd32-248">The prefix version of the operator decrements a variable before its value is used in the statement, as follows:</span></span>

```powershell
$a = 7
$c = --$a
$a
```

```
6
```

```powershell
$c
```

```
6
```

<span data-ttu-id="7bd32-249">Постфиксная версия оператора уменьшает переменную после того, как ее значение используется в инструкции.</span><span class="sxs-lookup"><span data-stu-id="7bd32-249">The postfix version of the operator decrements a variable after its value is used in the statement.</span></span> <span data-ttu-id="7bd32-250">В следующем примере `$d` `$a` переменные и имеют разные значения, так как перед изменениями присваивается значение `$d` `$a` .</span><span class="sxs-lookup"><span data-stu-id="7bd32-250">In the following example, the `$d` and `$a` variables have different values because the value is assigned to `$d` before `$a` changes:</span></span>

```powershell
$a = 7
$d = $a--
$a
```

```
6
```

```powershell
$d
```

```
7
```

## <a name="microsoft-net-framework-types"></a><span data-ttu-id="7bd32-251">Типы Microsoft .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7bd32-251">Microsoft .NET Framework types</span></span>

<span data-ttu-id="7bd32-252">По умолчанию, если переменная имеет только одно значение, то значение, присвоенное переменной, определяет тип данных переменной.</span><span class="sxs-lookup"><span data-stu-id="7bd32-252">By default, when a variable has only one value, the value that is assigned to the variable determines the data type of the variable.</span></span> <span data-ttu-id="7bd32-253">Например, следующая команда создает переменную с типом "integer" (тип System. Int32):</span><span class="sxs-lookup"><span data-stu-id="7bd32-253">For example, the following command creates a variable that has the "Integer" (System.Int32) type:</span></span>

```powershell
$a = 6
```

<span data-ttu-id="7bd32-254">Чтобы найти тип .NET Framework переменной, используйте метод **GetType** и его свойство **FullName** , как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="7bd32-254">To find the .NET Framework type of a variable, use the **GetType** method and its **FullName** property, as follows.</span></span> <span data-ttu-id="7bd32-255">Не забудьте добавить круглые скобки после имени метода **GetType** , даже если у вызова метода нет аргументов:</span><span class="sxs-lookup"><span data-stu-id="7bd32-255">Be sure to include the parentheses after the **GetType** method name, even though the method call has no arguments:</span></span>

```powershell
$a = 6
$a.GetType().FullName
```

```
System.Int32
```

<span data-ttu-id="7bd32-256">Чтобы создать переменную, содержащую строку, присвойте переменной строковое значение.</span><span class="sxs-lookup"><span data-stu-id="7bd32-256">To create a variable that contains a string, assign a string value to the variable.</span></span> <span data-ttu-id="7bd32-257">Чтобы указать, что значение является строкой, заключите его в кавычки следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7bd32-257">To indicate that the value is a string, enclose it in quotation marks, as follows:</span></span>

```powershell
$a = "6"
$a.GetType().FullName
```

```
System.String
```

<span data-ttu-id="7bd32-258">Если первое значение, присвоенное переменной, является строкой, PowerShell обрабатывает все операции как строковые операции и приводит новые значения к строкам.</span><span class="sxs-lookup"><span data-stu-id="7bd32-258">If the first value that is assigned to the variable is a string, PowerShell treats all operations as string operations and casts new values to strings.</span></span>
<span data-ttu-id="7bd32-259">Это происходит в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="7bd32-259">This occurs in the following example:</span></span>

```powershell
$a = "file"
$a += 3
$a
```

```
file3
```

<span data-ttu-id="7bd32-260">Если первое значение является целым числом, то PowerShell обрабатывает все операции как целочисленные операции и приводит новые значения к целому числу.</span><span class="sxs-lookup"><span data-stu-id="7bd32-260">If the first value is an integer, PowerShell treats all operations as integer operations and casts new values to integers.</span></span> <span data-ttu-id="7bd32-261">Это происходит в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="7bd32-261">This occurs in the following example:</span></span>

```powershell
$a = 6
$a += "3"
$a
```

```
9
```

<span data-ttu-id="7bd32-262">Новую скалярную переменную можно привести в качестве любого типа .NET Framework, поместив имя типа в скобки перед именем переменной или первым значением присваивания.</span><span class="sxs-lookup"><span data-stu-id="7bd32-262">You can cast a new scalar variable as any .NET Framework type by placing the type name in brackets that precede either the variable name or the first assignment value.</span></span> <span data-ttu-id="7bd32-263">При приведении переменной можно определить типы данных, которые могут храниться в переменной.</span><span class="sxs-lookup"><span data-stu-id="7bd32-263">When you cast a variable, you can determine the types of data that can be stored in the variable.</span></span> <span data-ttu-id="7bd32-264">Кроме того, можно определить, как переменная ведет себя при управлении ею.</span><span class="sxs-lookup"><span data-stu-id="7bd32-264">And, you can determine how the variable behaves when you manipulate it.</span></span>

<span data-ttu-id="7bd32-265">Например, следующая команда приводит переменную в виде строкового типа:</span><span class="sxs-lookup"><span data-stu-id="7bd32-265">For example, the following command casts the variable as a string type:</span></span>

```powershell
[string]$a = 27
$a += 3
$a
```

```
273
```

<span data-ttu-id="7bd32-266">В следующем примере первое значение приводится вместо приведения переменной:</span><span class="sxs-lookup"><span data-stu-id="7bd32-266">The following example casts the first value, instead of casting the variable:</span></span>

```powershell
$a = [string]27
```

<span data-ttu-id="7bd32-267">При приведении переменной к конкретному типу распространенным соглашением является приведение переменной, а не значения.</span><span class="sxs-lookup"><span data-stu-id="7bd32-267">When you cast a variable to a specific type, the common convention is to cast the variable, not the value.</span></span> <span data-ttu-id="7bd32-268">Однако нельзя выполнить операцию переприведения типа данных существующей переменной, если ее значение не может быть преобразовано в новый тип данных.</span><span class="sxs-lookup"><span data-stu-id="7bd32-268">However, you cannot recast the data type of an existing variable if its value cannot be converted to the new data type.</span></span> <span data-ttu-id="7bd32-269">Чтобы изменить тип данных, необходимо заменить его значение следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7bd32-269">To change the data type, you must replace its value, as follows:</span></span>

```powershell
$a = "string"
[int]$a
```

```
Cannot convert value "string" to type "System.Int32". Error: "Input string was
not in a correct format." At line:1 char:8 + [int]$a <<<<
```

```powershell
[int]$a = 3
```

<span data-ttu-id="7bd32-270">Кроме того, если вы предшествует имени переменной с типом данных, тип этой переменной блокируется, если тип не был явно переопределен путем указания другого типа данных.</span><span class="sxs-lookup"><span data-stu-id="7bd32-270">In addition, when you precede a variable name with a data type, the type of that variable is locked unless you explicitly override the type by specifying another data type.</span></span> <span data-ttu-id="7bd32-271">Если попытаться присвоить значение, несовместимое с существующим типом, и не переопределить тип явным образом, PowerShell выведет ошибку, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="7bd32-271">If you try to assign a value that is incompatible with the existing type, and you do not explicitly override the type, PowerShell displays an error, as shown in the following example:</span></span>

```powershell
$a = 3
$a = "string"
[int]$a = 3
$a = "string"
```

```
Cannot convert value "string" to type "System.Int32". Error: "Input
string was not in a correct format."
At line:1 char:3
+ $a <<<<  = "string"
```

```powershell
[string]$a = "string"
```

<span data-ttu-id="7bd32-272">В PowerShell типы данных переменных, содержащих несколько элементов в массиве, обрабатываются не так, как типы данных переменных, содержащих один элемент.</span><span class="sxs-lookup"><span data-stu-id="7bd32-272">In PowerShell, the data types of variables that contain multiple items in an array are handled differently from the data types of variables that contain a single item.</span></span> <span data-ttu-id="7bd32-273">Если тип данных специально не назначен переменной массива, тип данных всегда имеет значение `System.Object []` .</span><span class="sxs-lookup"><span data-stu-id="7bd32-273">Unless a data type is specifically assigned to an array variable, the data type is always `System.Object []`.</span></span> <span data-ttu-id="7bd32-274">Этот тип данных относится только к массивам.</span><span class="sxs-lookup"><span data-stu-id="7bd32-274">This data type is specific to arrays.</span></span>

<span data-ttu-id="7bd32-275">Иногда можно переопределить тип по умолчанию, указав другой тип.</span><span class="sxs-lookup"><span data-stu-id="7bd32-275">Sometimes, you can override the default type by specifying another type.</span></span> <span data-ttu-id="7bd32-276">Например, следующая команда приводит переменную в качестве `string []` типа массива:</span><span class="sxs-lookup"><span data-stu-id="7bd32-276">For example, the following command casts the variable as a `string []` array type:</span></span>

```powershell
[string []] $a = "one", "two", "three"
```

<span data-ttu-id="7bd32-277">Переменные PowerShell могут быть любого типа данных .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7bd32-277">PowerShell variables can be any .NET Framework data type.</span></span> <span data-ttu-id="7bd32-278">Кроме того, можно назначить любой полный .NET Framework тип данных, доступный в текущем процессе.</span><span class="sxs-lookup"><span data-stu-id="7bd32-278">In addition, you can assign any fully qualified .NET Framework data type that is available in the current process.</span></span> <span data-ttu-id="7bd32-279">Например, следующая команда задает `System.DateTime` тип данных:</span><span class="sxs-lookup"><span data-stu-id="7bd32-279">For example, the following command specifies a `System.DateTime` data type:</span></span>

```powershell
[System.DateTime]$a = "5/31/2005"
```

<span data-ttu-id="7bd32-280">Переменной будет присвоено значение, соответствующее `System.DateTime` типу данных.</span><span class="sxs-lookup"><span data-stu-id="7bd32-280">The variable will be assigned a value that conforms to the `System.DateTime` data type.</span></span> <span data-ttu-id="7bd32-281">Значение `$a` переменной будет следующим:</span><span class="sxs-lookup"><span data-stu-id="7bd32-281">The value of the `$a` variable would be the following:</span></span>

```
Tuesday, May 31, 2005 12:00:00 AM
```

## <a name="assigning-multiple-variables"></a><span data-ttu-id="7bd32-282">Назначение нескольких переменных</span><span class="sxs-lookup"><span data-stu-id="7bd32-282">Assigning multiple variables</span></span>

<span data-ttu-id="7bd32-283">В PowerShell можно назначить значения нескольким переменным с помощью одной команды.</span><span class="sxs-lookup"><span data-stu-id="7bd32-283">In PowerShell, you can assign values to multiple variables by using a single command.</span></span> <span data-ttu-id="7bd32-284">Первый элемент значения присваивания присваивается первой переменной, второй элемент присваивается второй переменной, третий элемент — третьей переменной и т. д.</span><span class="sxs-lookup"><span data-stu-id="7bd32-284">The first element of the assignment value is assigned to the first variable, the second element is assigned to the second variable, the third element to the third variable, and so on.</span></span> <span data-ttu-id="7bd32-285">Например, следующая команда присваивает значение 1 `$a` переменной, значение 2 — переменной `$b` , а значение 3 `$c` — переменной:</span><span class="sxs-lookup"><span data-stu-id="7bd32-285">For example, the following command assigns the value 1 to the `$a` variable, the value 2 to the `$b` variable, and the value 3 to the `$c` variable:</span></span>

```powershell
$a, $b, $c = 1, 2, 3
```

<span data-ttu-id="7bd32-286">Если значение назначения содержит больше элементов, чем переменные, все остальные значения присваиваются последней переменной.</span><span class="sxs-lookup"><span data-stu-id="7bd32-286">If the assignment value contains more elements than variables, all the remaining values are assigned to the last variable.</span></span> <span data-ttu-id="7bd32-287">Например, следующая команда содержит три переменные и пять значений:</span><span class="sxs-lookup"><span data-stu-id="7bd32-287">For example, the following command contains three variables and five values:</span></span>

```powershell
$a, $b, $c = 1, 2, 3, 4, 5
```

<span data-ttu-id="7bd32-288">Таким образом, PowerShell присваивает переменной значение 1 `$a` , а значение 2 — `$b` переменной.</span><span class="sxs-lookup"><span data-stu-id="7bd32-288">Therefore, PowerShell assigns the value 1 to the `$a` variable and the value 2 to the `$b` variable.</span></span> <span data-ttu-id="7bd32-289">Она присваивает переменной значения 3, 4 и 5 `$c` .</span><span class="sxs-lookup"><span data-stu-id="7bd32-289">It assigns the values 3, 4, and 5 to the `$c` variable.</span></span>
<span data-ttu-id="7bd32-290">Чтобы присвоить значения в `$c` переменной трем другим переменным, используйте следующий формат:</span><span class="sxs-lookup"><span data-stu-id="7bd32-290">To assign the values in the `$c` variable to three other variables, use the following format:</span></span>

```powershell
$d, $e, $f = $c
```

<span data-ttu-id="7bd32-291">Эта команда присваивает переменной значение 3 `$d` , значение 4 `$e` — переменной, а значение 5 — `$f` переменной.</span><span class="sxs-lookup"><span data-stu-id="7bd32-291">This command assigns the value 3 to the `$d` variable, the value 4 to the `$e` variable, and the value 5 to the `$f` variable.</span></span>

<span data-ttu-id="7bd32-292">Если значение назначения содержит меньше элементов, чем переменные, все остальные переменные в конце не будут иметь никаких значений.</span><span class="sxs-lookup"><span data-stu-id="7bd32-292">If the assignment value contains less elements than variables, all the remaining variables at the end are not assigned any values.</span></span> <span data-ttu-id="7bd32-293">Например, следующая команда содержит три переменные и два значения:</span><span class="sxs-lookup"><span data-stu-id="7bd32-293">For example, the following command contains three variables and two values:</span></span>

```powershell
$a, $b, $c = 1, 2
```

<span data-ttu-id="7bd32-294">Таким образом, PowerShell присваивает переменной значение 1 `$a` , а значение 2 — `$b` переменной.</span><span class="sxs-lookup"><span data-stu-id="7bd32-294">Therefore, PowerShell assigns the value 1 to the `$a` variable and the value 2 to the `$b` variable.</span></span> <span data-ttu-id="7bd32-295">Переменной не будет присвоено значение `$c` .</span><span class="sxs-lookup"><span data-stu-id="7bd32-295">It will not assign any value to the `$c` variable.</span></span>

<span data-ttu-id="7bd32-296">Можно также назначить одно значение нескольким переменным путем сцепления переменных.</span><span class="sxs-lookup"><span data-stu-id="7bd32-296">You can also assign a single value to multiple variables by chaining the variables.</span></span> <span data-ttu-id="7bd32-297">Например, следующая команда присваивает значение "три" всем четырем переменным:</span><span class="sxs-lookup"><span data-stu-id="7bd32-297">For example, the following command assigns a value of "three" to all four variables:</span></span>

```powershell
$a = $b = $c = $d = "three"
```

## <a name="variable-related-cmdlets"></a><span data-ttu-id="7bd32-298">Командлеты, связанные с переменными</span><span class="sxs-lookup"><span data-stu-id="7bd32-298">Variable-related cmdlets</span></span>

<span data-ttu-id="7bd32-299">В дополнение к использованию операции присваивания для задания значения переменной можно также использовать командлет [Set-Variable](xref:Microsoft.PowerShell.Utility.Set-Variable) .</span><span class="sxs-lookup"><span data-stu-id="7bd32-299">In addition to using an assignment operation to set a variable value, you can also use the [Set-Variable](xref:Microsoft.PowerShell.Utility.Set-Variable) cmdlet.</span></span> <span data-ttu-id="7bd32-300">Например, следующая команда использует `Set-Variable` для присвоения переменной массива из 1, 2, 3 `$a` .</span><span class="sxs-lookup"><span data-stu-id="7bd32-300">For example, the following command uses `Set-Variable` to assign an array of 1, 2, 3 to the `$a` variable.</span></span>

```powershell
Set-Variable -Name a -Value 1, 2, 3
```

## <a name="see-also"></a><span data-ttu-id="7bd32-301">См. также статью</span><span class="sxs-lookup"><span data-stu-id="7bd32-301">See also</span></span>

[<span data-ttu-id="7bd32-302">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="7bd32-302">about_Arrays</span></span>](about_Arrays.md)

[<span data-ttu-id="7bd32-303">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="7bd32-303">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="7bd32-304">about_Variables</span><span class="sxs-lookup"><span data-stu-id="7bd32-304">about_Variables</span></span>](about_Variables.md)

[<span data-ttu-id="7bd32-305">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="7bd32-305">Clear-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Clear-Variable)

[<span data-ttu-id="7bd32-306">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="7bd32-306">Remove-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Remove-Variable)

[<span data-ttu-id="7bd32-307">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="7bd32-307">Set-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Set-Variable)
