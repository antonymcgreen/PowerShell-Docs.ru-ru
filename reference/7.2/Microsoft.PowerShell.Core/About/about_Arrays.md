---
description: Описывает массивы, которые представляют собой структуры данных, предназначенные для хранения коллекций элементов.
Locale: en-US
ms.date: 08/26/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Arrays
ms.openlocfilehash: 2e7cf9c8f7d4e6f1d5bc66310f56d3de9461e592
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604431"
---
# <a name="about-arrays"></a><span data-ttu-id="42f3d-103">О массивах</span><span class="sxs-lookup"><span data-stu-id="42f3d-103">About Arrays</span></span>

## <a name="short-description"></a><span data-ttu-id="42f3d-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="42f3d-104">Short Description</span></span>
<span data-ttu-id="42f3d-105">Описывает массивы, которые представляют собой структуры данных, предназначенные для хранения коллекций элементов.</span><span class="sxs-lookup"><span data-stu-id="42f3d-105">Describes arrays, which are data structures designed to store collections of items.</span></span>

## <a name="long-description"></a><span data-ttu-id="42f3d-106">Полное описание</span><span class="sxs-lookup"><span data-stu-id="42f3d-106">Long Description</span></span>

<span data-ttu-id="42f3d-107">Массив — это структура данных, предназначенная для хранения коллекции элементов.</span><span class="sxs-lookup"><span data-stu-id="42f3d-107">An array is a data structure that is designed to store a collection of items.</span></span>
<span data-ttu-id="42f3d-108">Элементы могут быть одного типа или разных типов.</span><span class="sxs-lookup"><span data-stu-id="42f3d-108">The items can be the same type or different types.</span></span>

<span data-ttu-id="42f3d-109">Начиная с Windows PowerShell 3,0, коллекция из нуля или одного объекта имеет некоторые свойства массивов.</span><span class="sxs-lookup"><span data-stu-id="42f3d-109">Beginning in Windows PowerShell 3.0, a collection of zero or one object has some properties of arrays.</span></span>

## <a name="creating-and-initializing-an-array"></a><span data-ttu-id="42f3d-110">Создание и инициализация массива</span><span class="sxs-lookup"><span data-stu-id="42f3d-110">Creating and initializing an array</span></span>

<span data-ttu-id="42f3d-111">Чтобы создать и инициализировать массив, присвойте переменной несколько значений.</span><span class="sxs-lookup"><span data-stu-id="42f3d-111">To create and initialize an array, assign multiple values to a variable.</span></span> <span data-ttu-id="42f3d-112">Значения, хранящиеся в массиве, разделяются запятыми и отделены от имени переменной оператором присваивания ( `=` ).</span><span class="sxs-lookup"><span data-stu-id="42f3d-112">The values stored in the array are delimited with a comma and separated from the variable name by the assignment operator (`=`).</span></span>

<span data-ttu-id="42f3d-113">Например, чтобы создать массив с именем `$A` , содержащий семь числовых значений (int), равных 22, 5, 10, 8, 12, 9 и 80, введите:</span><span class="sxs-lookup"><span data-stu-id="42f3d-113">For example, to create an array named `$A` that contains the seven numeric (int) values of 22, 5, 10, 8, 12, 9, and 80, type:</span></span>

```powershell
$A = 22,5,10,8,12,9,80
```

<span data-ttu-id="42f3d-114">Запятую также можно использовать для инициализации массива с одним элементом, поместив запятую перед отдельным элементом.</span><span class="sxs-lookup"><span data-stu-id="42f3d-114">The comma can also be used to initialize a single item array by placing the comma before the single item.</span></span>

<span data-ttu-id="42f3d-115">Например, чтобы создать один массив элементов с именем `$B` , содержащий единственное значение 7, введите:</span><span class="sxs-lookup"><span data-stu-id="42f3d-115">For example, to create a single item array named `$B` containing the single value of 7, type:</span></span>

```powershell
$B = ,7
```

<span data-ttu-id="42f3d-116">Можно также создать и инициализировать массив с помощью оператора Range ( `..` ).</span><span class="sxs-lookup"><span data-stu-id="42f3d-116">You can also create and initialize an array by using the range operator (`..`).</span></span>
<span data-ttu-id="42f3d-117">В следующем примере создается массив, содержащий значения от 5 до 8.</span><span class="sxs-lookup"><span data-stu-id="42f3d-117">The following example creates an array containing the values 5 through 8.</span></span>

```powershell
$C = 5..8
```

<span data-ttu-id="42f3d-118">В результате `$C` содержит четыре значения: 5, 6, 7 и 8.</span><span class="sxs-lookup"><span data-stu-id="42f3d-118">As a result, `$C` contains four values: 5, 6, 7, and 8.</span></span>

<span data-ttu-id="42f3d-119">Если тип данных не указан, PowerShell создает каждый массив как массив объектов (**System. Object []**).</span><span class="sxs-lookup"><span data-stu-id="42f3d-119">When no data type is specified, PowerShell creates each array as an object array (**System.Object[]**).</span></span> <span data-ttu-id="42f3d-120">Чтобы определить тип данных массива, используйте метод **GetType ()** .</span><span class="sxs-lookup"><span data-stu-id="42f3d-120">To determine the data type of an array, use the **GetType()** method.</span></span> <span data-ttu-id="42f3d-121">Например, чтобы определить тип данных `$A` массива, введите:</span><span class="sxs-lookup"><span data-stu-id="42f3d-121">For example, to determine the data type of the `$A` array, type:</span></span>

```powershell
$A.GetType()
```

<span data-ttu-id="42f3d-122">Чтобы создать строго типизированный массив, то есть массив, который может содержать только значения определенного типа, приведите переменную к типу массива, например **String []**, **Long []** или **Int32 []**.</span><span class="sxs-lookup"><span data-stu-id="42f3d-122">To create a strongly typed array, that is, an array that can contain only values of a particular type, cast the variable as an array type, such as **string[]**, **long[]**, or **int32[]**.</span></span> <span data-ttu-id="42f3d-123">Для приведения массива перед именем переменной укажите тип массива, заключенный в квадратные скобки.</span><span class="sxs-lookup"><span data-stu-id="42f3d-123">To cast an array, precede the variable name with an array type enclosed in brackets.</span></span> <span data-ttu-id="42f3d-124">Например, чтобы создать массив 32-разрядных целых чисел с именем `$ia` , содержащим четыре целых числа (1500, 2230, 3350 и 4000), введите:</span><span class="sxs-lookup"><span data-stu-id="42f3d-124">For example, to create a 32-bit integer array named `$ia` containing four integers (1500, 2230, 3350, and 4000), type:</span></span>

```powershell
[int32[]]$ia = 1500,2230,3350,4000
```

<span data-ttu-id="42f3d-125">В результате `$ia` массив может содержать только целые числа.</span><span class="sxs-lookup"><span data-stu-id="42f3d-125">As a result, the `$ia` array can contain only integers.</span></span>

<span data-ttu-id="42f3d-126">Можно создавать массивы, приводимые к любому поддерживаемому типу в Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="42f3d-126">You can create arrays that are cast to any supported type in the Microsoft .NET Framework.</span></span> <span data-ttu-id="42f3d-127">Например, объекты, `Get-Process` получаемые для представления процессов, имеют тип **System. Diagnostics. Process** .</span><span class="sxs-lookup"><span data-stu-id="42f3d-127">For example, the objects that `Get-Process` retrieves to represent processes are of the **System.Diagnostics.Process** type.</span></span> <span data-ttu-id="42f3d-128">Чтобы создать строго типизированный массив объектов Process, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="42f3d-128">To create a strongly typed array of process objects, enter the following command:</span></span>

```powershell
[Diagnostics.Process[]]$zz = Get-Process
```

## <a name="the-array-sub-expression-operator"></a><span data-ttu-id="42f3d-129">Оператор "часть выражения массива"</span><span class="sxs-lookup"><span data-stu-id="42f3d-129">The array sub-expression operator</span></span>

<span data-ttu-id="42f3d-130">Оператор "вложенное выражение массива" создает массив из инструкций внутри него.</span><span class="sxs-lookup"><span data-stu-id="42f3d-130">The array sub-expression operator creates an array from the statements inside it.</span></span> <span data-ttu-id="42f3d-131">Независимо от оператора внутри оператора, оператор помещает его в массив.</span><span class="sxs-lookup"><span data-stu-id="42f3d-131">Whatever the statement inside the operator produces, the operator will place it in an array.</span></span> <span data-ttu-id="42f3d-132">Даже при наличии нуля или одного объекта.</span><span class="sxs-lookup"><span data-stu-id="42f3d-132">Even if there is zero or one object.</span></span>

<span data-ttu-id="42f3d-133">Синтаксис оператора Array выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="42f3d-133">The syntax of the array operator is as follows:</span></span>

```syntax
@( ... )
```

<span data-ttu-id="42f3d-134">Оператор Array можно использовать для создания массива из нуля или одного объекта.</span><span class="sxs-lookup"><span data-stu-id="42f3d-134">You can use the array operator to create an array of zero or one object.</span></span> <span data-ttu-id="42f3d-135">Пример:</span><span class="sxs-lookup"><span data-stu-id="42f3d-135">For example:</span></span>

```powershell
$a = @("Hello World")
$a.Count
```

```Output
1
```

```powershell
$b = @()
$b.Count
```

```Output
0
```

<span data-ttu-id="42f3d-136">Оператор Array полезен в сценариях при получении объектов, но неизвестно, сколько объектов вы получаете.</span><span class="sxs-lookup"><span data-stu-id="42f3d-136">The array operator is useful in scripts when you are getting objects, but do not know how many objects you get.</span></span> <span data-ttu-id="42f3d-137">Пример:</span><span class="sxs-lookup"><span data-stu-id="42f3d-137">For example:</span></span>

```powershell
$p = @(Get-Process Notepad)
```

<span data-ttu-id="42f3d-138">Дополнительные сведения о операторе "часть выражения массива" см. в разделе [about_Operators](about_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="42f3d-138">For more information about the array sub-expression operator, see [about_Operators](about_Operators.md).</span></span>

## <a name="accessing-and-using-array-elements"></a><span data-ttu-id="42f3d-139">Доступ к элементам массива и использование</span><span class="sxs-lookup"><span data-stu-id="42f3d-139">Accessing and using array elements</span></span>

### <a name="reading-an-array"></a><span data-ttu-id="42f3d-140">Чтение массива</span><span class="sxs-lookup"><span data-stu-id="42f3d-140">Reading an array</span></span>

<span data-ttu-id="42f3d-141">Можно ссылаться на массив, используя имя его переменной.</span><span class="sxs-lookup"><span data-stu-id="42f3d-141">You can refer to an array by using its variable name.</span></span> <span data-ttu-id="42f3d-142">Чтобы отобразить все элементы в массиве, введите имя массива.</span><span class="sxs-lookup"><span data-stu-id="42f3d-142">To display all the elements in the array, type the array name.</span></span> <span data-ttu-id="42f3d-143">Например, предполагается, что `$a` это массив, содержащий целые числа 0, 1, 2, до 9; введите:</span><span class="sxs-lookup"><span data-stu-id="42f3d-143">For example, assuming `$a` is an array containing integers 0, 1, 2, until 9; typing:</span></span>

```powershell
$a
```

```Output
0
1
2
3
4
5
6
7
8
9
```

<span data-ttu-id="42f3d-144">Можно ссылаться на элементы в массиве с помощью индекса, начиная с позиции 0.</span><span class="sxs-lookup"><span data-stu-id="42f3d-144">You can refer to the elements in an array by using an index, beginning at position 0.</span></span> <span data-ttu-id="42f3d-145">Заключите номер индекса в квадратные скобки.</span><span class="sxs-lookup"><span data-stu-id="42f3d-145">Enclose the index number in brackets.</span></span> <span data-ttu-id="42f3d-146">Например, чтобы отобразить первый элемент в `$a` массиве, введите:</span><span class="sxs-lookup"><span data-stu-id="42f3d-146">For example, to display the first element in the `$a` array, type:</span></span>

```powershell
$a[0]
```

```Output
0
```

<span data-ttu-id="42f3d-147">Чтобы отобразить третий элемент в `$a` массиве, введите:</span><span class="sxs-lookup"><span data-stu-id="42f3d-147">To display the third element in the `$a` array, type:</span></span>

```powershell
$a[2]
```

```Output
2
```

<span data-ttu-id="42f3d-148">Можно извлечь часть массива с помощью оператора Range для индекса.</span><span class="sxs-lookup"><span data-stu-id="42f3d-148">You can retrieve part of the array using a range operator for the index.</span></span> <span data-ttu-id="42f3d-149">Например, чтобы получить второй массив для пятого элемента массива, введите:</span><span class="sxs-lookup"><span data-stu-id="42f3d-149">For example, to retrieve the second to fifth elements of the array, you would type:</span></span>

```powershell
$a[1..4]
```

```Output
1
2
3
4
```

<span data-ttu-id="42f3d-150">Число отрицательных чисел от конца массива.</span><span class="sxs-lookup"><span data-stu-id="42f3d-150">Negative numbers count from the end of the array.</span></span> <span data-ttu-id="42f3d-151">Например, "-1" относится к последнему элементу массива.</span><span class="sxs-lookup"><span data-stu-id="42f3d-151">For example, "-1" refers to the last element of the array.</span></span> <span data-ttu-id="42f3d-152">Чтобы отобразить последние три элемента массива в порядке возрастания, введите:</span><span class="sxs-lookup"><span data-stu-id="42f3d-152">To display the last three elements of the array, in index ascending order, type:</span></span>

```powershell
$a = 0 .. 9
$a[-3..-1]
```

```Output
7
8
9
```

<span data-ttu-id="42f3d-153">Если ввести отрицательные индексы в порядке убывания, выходные данные будут изменены.</span><span class="sxs-lookup"><span data-stu-id="42f3d-153">If you type negative indexes in descending order, your output changes.</span></span>

```powershell
$a = 0 .. 9
$a[-1..-3]
```

```Output
9
8
7
```

<span data-ttu-id="42f3d-154">Однако при использовании этой нотации будьте осторожны.</span><span class="sxs-lookup"><span data-stu-id="42f3d-154">However, be cautious when using this notation.</span></span> <span data-ttu-id="42f3d-155">Нотация выполняет цикл от конечной границы до начала массива.</span><span class="sxs-lookup"><span data-stu-id="42f3d-155">The notation cycles from the end boundary to the beginning of the array.</span></span>

```powershell
$a = 0 .. 9
$a[2..-2]
```

```Output
2
1
0
9
8
```

<span data-ttu-id="42f3d-156">Кроме того, одна из распространенных ошибок состоит в том, чтобы предположить `$a[0..-2]` , что ссылается на все элементы массива, за исключением последнего.</span><span class="sxs-lookup"><span data-stu-id="42f3d-156">Also, one common mistake is to assume `$a[0..-2]` refers to all the elements of the array, except for the last one.</span></span> <span data-ttu-id="42f3d-157">Он относится к первым, последним и вторым элементам в массиве.</span><span class="sxs-lookup"><span data-stu-id="42f3d-157">It refers to the first, last, and second-to-last elements in the array.</span></span>

<span data-ttu-id="42f3d-158">Оператор «плюс» () можно использовать `+` для объединения диапазонов со списком элементов в массиве.</span><span class="sxs-lookup"><span data-stu-id="42f3d-158">You can use the plus operator (`+`) to combine a ranges with a list of elements in an array.</span></span> <span data-ttu-id="42f3d-159">Например, чтобы отобразить элементы с позициями индекса 0, 2 и 4 до 6, введите:</span><span class="sxs-lookup"><span data-stu-id="42f3d-159">For example, to display the elements at index positions 0, 2, and 4 through 6, type:</span></span>

```powershell
$a = 0 .. 9
$a[0,2+4..6]
```

```Output
0
2
4
5
6
```

<span data-ttu-id="42f3d-160">Кроме того, для перечисления нескольких диапазонов и отдельных элементов можно использовать оператор «плюс».</span><span class="sxs-lookup"><span data-stu-id="42f3d-160">Also, to list multiple ranges and individual elements you can use the plus operator.</span></span> <span data-ttu-id="42f3d-161">Например, для перечисления элементов от 0 до 2, от 4 до шести и элемента в восьмом позиционированном типе:</span><span class="sxs-lookup"><span data-stu-id="42f3d-161">For example, to list elements zero to two, four to six, and the element at eighth positional type:</span></span>

```powershell
$a = 0..9
$a[+0..2+4..6+8]
```

```Output
0
1
2
4
5
6
8
```

### <a name="iterations-over-array-elements"></a><span data-ttu-id="42f3d-162">Итерации по элементам массива</span><span class="sxs-lookup"><span data-stu-id="42f3d-162">Iterations over array elements</span></span>

<span data-ttu-id="42f3d-163">Можно также использовать циклические конструкции, такие как циклы ForEach, for и while, для ссылки на элементы в массиве.</span><span class="sxs-lookup"><span data-stu-id="42f3d-163">You can also use looping constructs, such as ForEach, For, and While loops, to refer to the elements in an array.</span></span> <span data-ttu-id="42f3d-164">Например, чтобы использовать цикл ForEach для вывода элементов в `$a` массиве, введите:</span><span class="sxs-lookup"><span data-stu-id="42f3d-164">For example, to use a ForEach loop to display the elements in the `$a` array, type:</span></span>

```powershell
$a = 0..9
foreach ($element in $a) {
  $element
}
```

```Output
0
1
2
3
4
5
6
7
8
9
```

<span data-ttu-id="42f3d-165">Цикл foreach выполняет итерацию по массиву и возвращает каждое значение в массиве, пока не достигнет конца массива.</span><span class="sxs-lookup"><span data-stu-id="42f3d-165">The Foreach loop iterates through the array and returns each value in the array until reaching the end of the array.</span></span>

<span data-ttu-id="42f3d-166">Цикл for полезен при увеличении счетчиков при проверке элементов в массиве.</span><span class="sxs-lookup"><span data-stu-id="42f3d-166">The For loop is useful when you are incrementing counters while examining the elements in an array.</span></span> <span data-ttu-id="42f3d-167">Например, чтобы использовать цикл for для возврата всех остальных значений в массиве, введите:</span><span class="sxs-lookup"><span data-stu-id="42f3d-167">For example, to use a For loop to return every other value in an array, type:</span></span>

```powershell
$a = 0..9
for ($i = 0; $i -le ($a.length - 1); $i += 2) {
  $a[$i]
}
```

```Output
0
2
4
6
8
```

<span data-ttu-id="42f3d-168">Можно использовать цикл while для вывода элементов в массиве до тех пор, пока определенное условие не станет истинным.</span><span class="sxs-lookup"><span data-stu-id="42f3d-168">You can use a While loop to display the elements in an array until a defined condition is no longer true.</span></span> <span data-ttu-id="42f3d-169">Например, чтобы отобразить элементы в `$a` массиве, если индекс массива меньше 4, введите:</span><span class="sxs-lookup"><span data-stu-id="42f3d-169">For example, to display the elements in the `$a` array while the array index is less than 4, type:</span></span>

```powershell
$a = 0..9
$i=0
while($i -lt 4) {
  $a[$i];
  $i++
}
```

```Output
0
1
2
3
```

## <a name="properties-of-arrays"></a><span data-ttu-id="42f3d-170">Свойства массивов</span><span class="sxs-lookup"><span data-stu-id="42f3d-170">Properties of arrays</span></span>

### <a name="count-or-length-or-longlength"></a><span data-ttu-id="42f3d-171">Количество или длина или Лонгленгс</span><span class="sxs-lookup"><span data-stu-id="42f3d-171">Count or Length or LongLength</span></span>

<span data-ttu-id="42f3d-172">Чтобы определить, сколько элементов находится в массиве, используйте `Length` свойство или его `Count` псевдоним.</span><span class="sxs-lookup"><span data-stu-id="42f3d-172">To determine how many items are in an array, use the `Length` property or its `Count` alias.</span></span> <span data-ttu-id="42f3d-173">`Longlength` может использоваться, если массив содержит более 2 147 483 647 элементов.</span><span class="sxs-lookup"><span data-stu-id="42f3d-173">`Longlength` is useful if the array contains more than 2,147,483,647 elements.</span></span>

```powershell
$a = 0..9
$a.Count
$a.Length
```

```Output
10
10
```

### <a name="rank"></a><span data-ttu-id="42f3d-174">Ранг</span><span class="sxs-lookup"><span data-stu-id="42f3d-174">Rank</span></span>

<span data-ttu-id="42f3d-175">Возвращает число измерений в массиве.</span><span class="sxs-lookup"><span data-stu-id="42f3d-175">Returns the number of dimensions in the array.</span></span> <span data-ttu-id="42f3d-176">Большинство массивов в PowerShell имеют только одно измерение.</span><span class="sxs-lookup"><span data-stu-id="42f3d-176">Most arrays in PowerShell have one dimension, only.</span></span> <span data-ttu-id="42f3d-177">Даже если вы считаете, что создаете многомерный массив; как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="42f3d-177">Even when you think you are building a multidimensional array; like the following example:</span></span>

```powershell
$a = @(
  @(0,1),
  @("b", "c"),
  @(Get-Process)
)

[int]$r = $a.Rank
"`$a rank: $r"
```

```Output
$a rank: 1
```

<span data-ttu-id="42f3d-178">В следующем примере показано создание действительного многомерного массива с помощью .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="42f3d-178">The following example shows how to create a truly multidimensional array using the .Net Framework.</span></span>

```powershell
[int[,]]$rank2 = [int[,]]::new(5,5)
$rank2.rank
```

```Output
2
```

## <a name="methods-of-arrays"></a><span data-ttu-id="42f3d-179">Методы массивов</span><span class="sxs-lookup"><span data-stu-id="42f3d-179">Methods of arrays</span></span>

### <a name="clear"></a><span data-ttu-id="42f3d-180">Очистить</span><span class="sxs-lookup"><span data-stu-id="42f3d-180">Clear</span></span>

<span data-ttu-id="42f3d-181">Устанавливает все значения элементов в _значение по умолчанию_ для типа элемента массива.</span><span class="sxs-lookup"><span data-stu-id="42f3d-181">Sets all element values to the _default value_ of the array's element type.</span></span>
<span data-ttu-id="42f3d-182">Метод Clear () не сбрасывает размер массива.</span><span class="sxs-lookup"><span data-stu-id="42f3d-182">The Clear() method does not reset the size of the array.</span></span>

<span data-ttu-id="42f3d-183">В следующем примере `$a` представлен массив объектов.</span><span class="sxs-lookup"><span data-stu-id="42f3d-183">In the following example `$a` is an array of objects.</span></span>

```powershell
$a = 1, 2, 3
$a.Clear()
$a | % { $null -eq $_ }
```

```Output
True
True
True
```

<span data-ttu-id="42f3d-184">В этом примере `$intA` явным образом вводится для хранения целых чисел.</span><span class="sxs-lookup"><span data-stu-id="42f3d-184">In this example, `$intA` is explicitly typed to contain integers.</span></span>

```powershell
[int[]] $intA = 1, 2, 3
$intA.Clear()
$intA
```

```Output
0
0
0
```

### <a name="foreach"></a><span data-ttu-id="42f3d-185">ForEach</span><span class="sxs-lookup"><span data-stu-id="42f3d-185">ForEach</span></span>

<span data-ttu-id="42f3d-186">Позволяет перебирать все элементы в массиве и выполнять заданную операцию для каждого элемента массива.</span><span class="sxs-lookup"><span data-stu-id="42f3d-186">Allows to iterate over all elements in the array and perform a given operation for each element of the array.</span></span>

<span data-ttu-id="42f3d-187">Метод ForEach имеет несколько перегрузок, выполняющих различные операции.</span><span class="sxs-lookup"><span data-stu-id="42f3d-187">The ForEach method has several overloads that perform different operations.</span></span>

```
ForEach(scriptblock expression)
ForEach(scriptblock expression, object[] arguments)
ForEach(type convertToType)
ForEach(string propertyName)
ForEach(string propertyName, object[] newValue)
ForEach(string methodName)
ForEach(string methodName, object[] arguments)
```

#### <a name="foreachscriptblock-expression"></a><span data-ttu-id="42f3d-188">ForEach (выражение ScriptBlock)</span><span class="sxs-lookup"><span data-stu-id="42f3d-188">ForEach(scriptblock expression)</span></span>

#### <a name="foreachscriptblock-expression-object-arguments"></a><span data-ttu-id="42f3d-189">ForEach (выражение ScriptBlock, аргументы объекта [])</span><span class="sxs-lookup"><span data-stu-id="42f3d-189">ForEach(scriptblock expression, object[] arguments)</span></span>

<span data-ttu-id="42f3d-190">Этот метод был добавлен в PowerShell v4.</span><span class="sxs-lookup"><span data-stu-id="42f3d-190">This method was added in PowerShell v4.</span></span>

> [!NOTE]
> <span data-ttu-id="42f3d-191">Синтаксис требует использования блока скрипта.</span><span class="sxs-lookup"><span data-stu-id="42f3d-191">The syntax requires the usage of a script block.</span></span> <span data-ttu-id="42f3d-192">Круглые скобки необязательны, если блок ScriptBlock является единственным параметром.</span><span class="sxs-lookup"><span data-stu-id="42f3d-192">Parentheses are optional if the scriptblock is the only parameter.</span></span> <span data-ttu-id="42f3d-193">Кроме того, не должно быть пробелов между методом и открывающей круглой скобкой или фигурной скобкой.</span><span class="sxs-lookup"><span data-stu-id="42f3d-193">Also, there must not be a space between the method and the opening parenthesis or brace.</span></span>

<span data-ttu-id="42f3d-194">В следующем примере показано, как использовать метод ForEach.</span><span class="sxs-lookup"><span data-stu-id="42f3d-194">The following example shows how use the foreach method.</span></span> <span data-ttu-id="42f3d-195">В этом случае целью является создание квадратного значения элементов в массиве.</span><span class="sxs-lookup"><span data-stu-id="42f3d-195">In this case the intent is to generate the square value of the elements in the array.</span></span>

```powershell
$a = @(0 .. 3)
$a.ForEach({ $_ * $_})
```

```Output
0
1
4
9
```

<span data-ttu-id="42f3d-196">Как и `-ArgumentList` параметр параметра `ForEach-Object` , `arguments` параметр позволяет передавать массив аргументов в блок сценария, настроенный для их принятия.</span><span class="sxs-lookup"><span data-stu-id="42f3d-196">Just like the `-ArgumentList` parameter of `ForEach-Object`, the `arguments` parameter allows the passing of an array of arguments to a script block configured to accept them.</span></span>

<span data-ttu-id="42f3d-197">Дополнительные сведения о поведении **ArgumentList** см. в разделе [about_Splatting](about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="42f3d-197">For more information about the behavior of **ArgumentList**, see [about_Splatting](about_Splatting.md#splatting-with-arrays).</span></span>

#### <a name="foreachtype-converttotype"></a><span data-ttu-id="42f3d-198">ForEach (тип Конверттотипе)</span><span class="sxs-lookup"><span data-stu-id="42f3d-198">ForEach(type convertToType)</span></span>

<span data-ttu-id="42f3d-199">`ForEach`Метод можно использовать для приведения элементов к другому типу. в следующем примере показано, как преобразовать список строковых дат в `[DateTime]` тип.</span><span class="sxs-lookup"><span data-stu-id="42f3d-199">The `ForEach` method can be used to swiftly cast the elements to a different type; the following example shows how to convert a list of string dates to `[DateTime]` type.</span></span>

```powershell
@("1/1/2017", "2/1/2017", "3/1/2017").ForEach([datetime])
```

```Output

Sunday, January 1, 2017 12:00:00 AM
Wednesday, February 1, 2017 12:00:00 AM
Wednesday, March 1, 2017 12:00:00 AM
```

#### <a name="foreachstring-propertyname"></a><span data-ttu-id="42f3d-200">ForEach (строка propertyName)</span><span class="sxs-lookup"><span data-stu-id="42f3d-200">ForEach(string propertyName)</span></span>

#### <a name="foreachstring-propertyname-object-newvalue"></a><span data-ttu-id="42f3d-201">ForEach (строка propertyName, объект [] newValue)</span><span class="sxs-lookup"><span data-stu-id="42f3d-201">ForEach(string propertyName, object[] newValue)</span></span>

<span data-ttu-id="42f3d-202">`ForEach`Метод также можно использовать для быстрого получения или установки значений свойств для каждого элемента в коллекции.</span><span class="sxs-lookup"><span data-stu-id="42f3d-202">The `ForEach` method can also be used to quickly retrieve, or set property values for every item in the collection.</span></span>

```powershell
# Set all LastAccessTime properties of files to the current date.
(dir 'C:\Temp').ForEach('LastAccessTime', (Get-Date))
# View the newly set LastAccessTime of all items, and find Unique entries.
(dir 'C:\Temp').ForEach('LastAccessTime') | Get-Unique
```

```Output
Wednesday, June 20, 2018 9:21:57 AM
```

#### <a name="foreachstring-methodname"></a><span data-ttu-id="42f3d-203">ForEach (String methodName)</span><span class="sxs-lookup"><span data-stu-id="42f3d-203">ForEach(string methodName)</span></span>

#### <a name="foreachstring-methodname-object-arguments"></a><span data-ttu-id="42f3d-204">ForEach (String имя_метода, Object [] аргументы)</span><span class="sxs-lookup"><span data-stu-id="42f3d-204">ForEach(string methodName, object[] arguments)</span></span>

<span data-ttu-id="42f3d-205">Наконец, `ForEach` методы можно использовать для выполнения метода для каждого элемента в коллекции.</span><span class="sxs-lookup"><span data-stu-id="42f3d-205">Lastly, `ForEach` methods can be used to execute a method on every item in the collection.</span></span>

```powershell
("one", "two", "three").ForEach("ToUpper")
```

```Output
ONE
TWO
THREE
```

<span data-ttu-id="42f3d-206">Как и `-ArgumentList` параметр параметра `ForEach-Object` , `arguments` параметр позволяет передавать массив аргументов в блок сценария, настроенный для их принятия.</span><span class="sxs-lookup"><span data-stu-id="42f3d-206">Just like the `-ArgumentList` parameter of `ForEach-Object`, the `arguments` parameter allows the passing of an array of arguments to a script block configured to accept them.</span></span>

> [!NOTE]
> <span data-ttu-id="42f3d-207">Начиная с Windows PowerShell 3,0. получение свойств и исполнение методов для каждого элемента коллекции также можно выполнить с помощью "методов скалярных объектов и коллекций". Дополнительные сведения об этом можно узнать здесь [about_methods](about_methods.md).</span><span class="sxs-lookup"><span data-stu-id="42f3d-207">Starting in Windows PowerShell 3.0 retrieving properties and executing methods for each item in a collection can also be accomplished using "Methods of scalar objects and collections" You can read more about that here [about_methods](about_methods.md).</span></span>

### <a name="where"></a><span data-ttu-id="42f3d-208">Where</span><span class="sxs-lookup"><span data-stu-id="42f3d-208">Where</span></span>

<span data-ttu-id="42f3d-209">Позволяет фильтровать или выбирать элементы массива.</span><span class="sxs-lookup"><span data-stu-id="42f3d-209">Allows to filter or select the elements of the array.</span></span> <span data-ttu-id="42f3d-210">Скрипт должен иметь значение, отличное от: ноль (0), пустая строка `$false` или, `$null` чтобы элемент отображался после элемента `Where`</span><span class="sxs-lookup"><span data-stu-id="42f3d-210">The script must evaluate to anything different than: zero (0), empty string, `$false` or `$null` for the element to show after the `Where`</span></span>

<span data-ttu-id="42f3d-211">Существует одно определение для `Where` метода.</span><span class="sxs-lookup"><span data-stu-id="42f3d-211">There is one definition for the `Where` method.</span></span>

```
Where(scriptblock expression[, WhereOperatorSelectionMode mode
                            [, int numberToReturn]])
```

> [!NOTE]
> <span data-ttu-id="42f3d-212">Синтаксис требует использования блока скрипта.</span><span class="sxs-lookup"><span data-stu-id="42f3d-212">The syntax requires the usage of a script block.</span></span> <span data-ttu-id="42f3d-213">Круглые скобки необязательны, если блок ScriptBlock является единственным параметром.</span><span class="sxs-lookup"><span data-stu-id="42f3d-213">Parentheses are optional if the scriptblock is the only parameter.</span></span> <span data-ttu-id="42f3d-214">Кроме того, не должно быть пробелов между методом и открывающей круглой скобкой или фигурной скобкой.</span><span class="sxs-lookup"><span data-stu-id="42f3d-214">Also, there must not be a space between the method and the opening parenthesis or brace.</span></span>

<span data-ttu-id="42f3d-215">`Expression`Для фильтрации необходим блок ScriptBlock, `mode` необязательный аргумент позволяет выбрать дополнительные возможности выбора, а `numberToReturn` необязательный аргумент позволяет ограничить количество элементов, возвращаемых фильтром.</span><span class="sxs-lookup"><span data-stu-id="42f3d-215">The `Expression` is scriptblock that is required for filtering, the `mode` optional argument allows additional selection capabilities, and the `numberToReturn` optional argument allows the ability to limit how many items are returned from the filter.</span></span>

<span data-ttu-id="42f3d-216">Допустимые значения для `mode` :</span><span class="sxs-lookup"><span data-stu-id="42f3d-216">The acceptable values for `mode` are:</span></span>

- <span data-ttu-id="42f3d-217">По умолчанию (0) — возврат всех элементов</span><span class="sxs-lookup"><span data-stu-id="42f3d-217">Default (0) - Return all items</span></span>
- <span data-ttu-id="42f3d-218">First (1) — возврат первого элемента</span><span class="sxs-lookup"><span data-stu-id="42f3d-218">First (1) - Return the first item</span></span>
- <span data-ttu-id="42f3d-219">Last (2) — Возврат последнего элемента</span><span class="sxs-lookup"><span data-stu-id="42f3d-219">Last (2) - Return the last item</span></span>
- <span data-ttu-id="42f3d-220">SkipUntil (3) — пропустить элементы до тех пор, пока условие не будет равно true, возвращает оставшиеся элементы.</span><span class="sxs-lookup"><span data-stu-id="42f3d-220">SkipUntil (3) - Skip items until condition is true, the return the remaining items</span></span>
- <span data-ttu-id="42f3d-221">До (4) — возврат всех элементов до истинного условия</span><span class="sxs-lookup"><span data-stu-id="42f3d-221">Until (4) - Return all items until condition is true</span></span>
- <span data-ttu-id="42f3d-222">Split (5) — Возврат массива из двух элементов</span><span class="sxs-lookup"><span data-stu-id="42f3d-222">Split (5) - Return an array of two elements</span></span>
  - <span data-ttu-id="42f3d-223">Первый элемент содержит совпадающие элементы</span><span class="sxs-lookup"><span data-stu-id="42f3d-223">The first element contains matching items</span></span>
  - <span data-ttu-id="42f3d-224">Второй элемент содержит оставшиеся элементы</span><span class="sxs-lookup"><span data-stu-id="42f3d-224">The second element contains the remaining items</span></span>

<span data-ttu-id="42f3d-225">В следующем примере показано, как выбрать все нечетные числа из массива.</span><span class="sxs-lookup"><span data-stu-id="42f3d-225">The following example shows how to select all odd numbers from the array.</span></span>

```powershell
(0..9).Where{ $_ % 2 }
```

```Output
1
3
5
7
9
```

<span data-ttu-id="42f3d-226">В этом примере показано, как выбрать непустые строки.</span><span class="sxs-lookup"><span data-stu-id="42f3d-226">This example show how to select the strings that are not empty.</span></span>

```powershell
('hi', '', 'there').Where({$_.Length})
```

```Output
hi
there
```

#### <a name="default"></a><span data-ttu-id="42f3d-227">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="42f3d-227">Default</span></span>

<span data-ttu-id="42f3d-228">`Default`Режим фильтрует элементы с помощью `Expression` ScriptBlock.</span><span class="sxs-lookup"><span data-stu-id="42f3d-228">The `Default` mode filters items using the `Expression` scriptblock.</span></span>

<span data-ttu-id="42f3d-229">Если `numberToReturn` предоставлено значение, оно указывает максимальное число возвращаемых элементов.</span><span class="sxs-lookup"><span data-stu-id="42f3d-229">If a `numberToReturn` is provided, it specifies the maximum number of items to return.</span></span>

```powershell
# Get the zip files in the current users profile, sorted by LastAccessTime.
$Zips = dir $env:userprofile -Recurse '*.zip' | Sort-Object LastAccessTime
# Get the least accessed file over 100MB
$Zips.Where({$_.Length -gt 100MB}, 'Default', 1)
```

> [!NOTE]
> <span data-ttu-id="42f3d-230">`Default`Режим и `First` режим возвращают первые `numberToReturn` элементы () и могут использоваться взаимозаменяемыми.</span><span class="sxs-lookup"><span data-stu-id="42f3d-230">Both the `Default` mode and `First` mode return the first (`numberToReturn`) items, and can be used interchangeably.</span></span>

#### <a name="last"></a><span data-ttu-id="42f3d-231">Последний</span><span class="sxs-lookup"><span data-stu-id="42f3d-231">Last</span></span>

```powershell
$h = (Get-Date).AddHours(-1)
$logs = dir 'C:\' -Recurse '*.log' | Sort-Object CreationTime
# Find the last 5 log files created in the past hour.
$logs.Where({$_.CreationTime -gt $h}, 'Last', 5)
```

#### <a name="skipuntil"></a><span data-ttu-id="42f3d-232">SkipUntil</span><span class="sxs-lookup"><span data-stu-id="42f3d-232">SkipUntil</span></span>

<span data-ttu-id="42f3d-233">`SkipUntil`Режим пропускает все объекты в коллекции до тех пор, пока объект не передаст фильтр выражений блока скрипта.</span><span class="sxs-lookup"><span data-stu-id="42f3d-233">The `SkipUntil` mode skips all objects in a collection until an object passes the script block expression filter.</span></span> <span data-ttu-id="42f3d-234">Затем он возвращает **все** остальные элементы сбора, не проверяя их.</span><span class="sxs-lookup"><span data-stu-id="42f3d-234">It then returns **ALL** remaining collection items without testing them.</span></span> <span data-ttu-id="42f3d-235">_Тестируется только один передающий элемент_.</span><span class="sxs-lookup"><span data-stu-id="42f3d-235">_Only one passing item is tested_.</span></span>

<span data-ttu-id="42f3d-236">Это означает, что возвращаемая коллекция содержит как _передающие_ , так и _непройденные_ элементы, которые не были проверены.</span><span class="sxs-lookup"><span data-stu-id="42f3d-236">This means the returned collection contains both _passing_ and _non-passing_ items that have NOT been tested.</span></span>

<span data-ttu-id="42f3d-237">Количество возвращаемых элементов может быть ограничено путем передачи значения в `numberToReturn` аргумент.</span><span class="sxs-lookup"><span data-stu-id="42f3d-237">The number of items returned can be limited by passing a value to the `numberToReturn` argument.</span></span>

```powershell
$computers = "Server01", "Server02", "Server03", "localhost", "Server04"
# Find the first available online server.
$computers.Where({ Test-Connection $_ }, 'SkipUntil', 1)
```

```Output
localhost
```

#### <a name="until"></a><span data-ttu-id="42f3d-238">Вплот</span><span class="sxs-lookup"><span data-stu-id="42f3d-238">Until</span></span>

<span data-ttu-id="42f3d-239">`Until`Режим инвертирует `SkipUntil` режим.</span><span class="sxs-lookup"><span data-stu-id="42f3d-239">The `Until` mode inverts the `SkipUntil` mode.</span></span>  <span data-ttu-id="42f3d-240">Он возвращает **все** элементы в коллекции, пока элемент не передаст выражение блока скрипта.</span><span class="sxs-lookup"><span data-stu-id="42f3d-240">It returns **ALL** items in a collection until an item passes the script block expression.</span></span> <span data-ttu-id="42f3d-241">Когда элемент _передает_ выражение ScriptBlock, `Where` метод останавливает обработку элементов.</span><span class="sxs-lookup"><span data-stu-id="42f3d-241">Once an item _passes_ the scriptblock expression, the `Where` method stops processing items.</span></span>

<span data-ttu-id="42f3d-242">Это означает, что вы получаете первый набор _непередающих_ элементов из `Where` метода.</span><span class="sxs-lookup"><span data-stu-id="42f3d-242">This means that you receive the first set of _non-passing_ items from the `Where` method.</span></span> <span data-ttu-id="42f3d-243">_После_ передачи одного элемента остальные не проверяются и не возвращаются.</span><span class="sxs-lookup"><span data-stu-id="42f3d-243">_After_ one item passes, the rest are NOT tested or returned.</span></span>

<span data-ttu-id="42f3d-244">Количество возвращаемых элементов может быть ограничено путем передачи значения в `numberToReturn` аргумент.</span><span class="sxs-lookup"><span data-stu-id="42f3d-244">The number of items returned can be limited by passing a value to the `numberToReturn` argument.</span></span>

```powershell
# Retrieve the first set of numbers less than or equal to 10.
(1..50).Where({$_ -gt 10}, 'Until')
# This would perform the same operation.
(1..50).Where({$_ -le 10})
```

```Output
1
2
3
4
5
6
7
8
9
10
```

> [!NOTE]
> <span data-ttu-id="42f3d-245">`Until`И, и `SkipUntil` работают не в ходе тестирования пакета элементов.</span><span class="sxs-lookup"><span data-stu-id="42f3d-245">Both `Until` and `SkipUntil` operate under the premise of NOT testing a batch of items.</span></span>
>
> <span data-ttu-id="42f3d-246">`Until` Возвращает элементы **перед** первым _прохождением_.</span><span class="sxs-lookup"><span data-stu-id="42f3d-246">`Until` returns the items **BEFORE** the first _pass_.</span></span>
>
> <span data-ttu-id="42f3d-247">`SkipUntil` Возвращает все элементы **после** первого _прохода_, включая первый передающий элемент.</span><span class="sxs-lookup"><span data-stu-id="42f3d-247">`SkipUntil` returns all the items **AFTER** the first _pass_, including the first passing item.</span></span>

#### <a name="split"></a><span data-ttu-id="42f3d-248">Разделение</span><span class="sxs-lookup"><span data-stu-id="42f3d-248">Split</span></span>

<span data-ttu-id="42f3d-249">`Split`Режим разделяет или группирует элементы коллекции в две отдельные коллекции.</span><span class="sxs-lookup"><span data-stu-id="42f3d-249">The `Split` mode splits, or groups collection items into two separate collections.</span></span> <span data-ttu-id="42f3d-250">Те, которые передают выражение ScriptBlock, и те, которые не имеют.</span><span class="sxs-lookup"><span data-stu-id="42f3d-250">Those that pass the scriptblock expression, and those that do not.</span></span>

<span data-ttu-id="42f3d-251">Если `numberToReturn` указан параметр, то первая коллекция содержит _передаваемые_ элементы, а не превысить указанное значение.</span><span class="sxs-lookup"><span data-stu-id="42f3d-251">If a `numberToReturn` is specified, the first collection, contains the _passing_ items, not to exceed the value specified.</span></span>

<span data-ttu-id="42f3d-252">Остальные объекты, даже те, которые **передают** фильтр выражения, возвращаются во второй коллекции.</span><span class="sxs-lookup"><span data-stu-id="42f3d-252">The remaining objects, even those that **PASS** the expression filter, are returned in the second collection.</span></span>

```powershell
$running, $stopped = (Get-Service).Where({$_.Status -eq 'Running'}, 'Split')
$running
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  Appinfo            Application Information
Running  AudioEndpointBu... Windows Audio Endpoint Builder
Running  Audiosrv           Windows Audio
...
```

```powershell
$stopped
```

```Output
Status   Name               DisplayName
------   ----               -----------
Stopped  AJRouter           AllJoyn Router Service
Stopped  ALG                Application Layer Gateway Service
Stopped  AppIDSvc           Application Identity
...
```

## <a name="get-the-members-of-an-array"></a><span data-ttu-id="42f3d-253">Получение элементов массива</span><span class="sxs-lookup"><span data-stu-id="42f3d-253">Get the members of an array</span></span>

<span data-ttu-id="42f3d-254">Чтобы получить свойства и методы массива, такие как свойство Length и метод **SetValue** , используйте параметр **InputObject** `Get-Member` командлета.</span><span class="sxs-lookup"><span data-stu-id="42f3d-254">To get the properties and methods of an array, such as the Length property and the **SetValue** method, use the **InputObject** parameter of the `Get-Member` cmdlet.</span></span>

<span data-ttu-id="42f3d-255">При передаче массива в `Get-Member` оболочка PowerShell отправляет элементы по одной за раз и `Get-Member` возвращает тип каждого элемента в массиве (игнорируя дубликаты).</span><span class="sxs-lookup"><span data-stu-id="42f3d-255">When you pipe an array to `Get-Member`, PowerShell sends the items one at a time and `Get-Member` returns the type of each item in the array (ignoring duplicates).</span></span>

<span data-ttu-id="42f3d-256">При использовании параметра **InputObject** `Get-Member` возвращает элементы массива.</span><span class="sxs-lookup"><span data-stu-id="42f3d-256">When you use the **InputObject** parameter, `Get-Member` returns the members of the array.</span></span>

<span data-ttu-id="42f3d-257">Например, следующая команда возвращает элементы `$a` переменной массива.</span><span class="sxs-lookup"><span data-stu-id="42f3d-257">For example, the following command gets the members of the `$a` array variable.</span></span>

```powershell
Get-Member -InputObject $a
```

<span data-ttu-id="42f3d-258">Кроме того, элементы массива можно получить, введя запятую (,) перед значением, перенаправленным в `Get-Member` командлет.</span><span class="sxs-lookup"><span data-stu-id="42f3d-258">You can also get the members of an array by typing a comma (,) before the value that is piped to the `Get-Member` cmdlet.</span></span> <span data-ttu-id="42f3d-259">Запятая делает массив вторым элементом массива массивов.</span><span class="sxs-lookup"><span data-stu-id="42f3d-259">The comma makes the array the second item in an array of arrays.</span></span> <span data-ttu-id="42f3d-260">PowerShell передает массивы по одному за раз и `Get-Member` возвращает элементы массива.</span><span class="sxs-lookup"><span data-stu-id="42f3d-260">PowerShell pipes the arrays one at a time and `Get-Member` returns the members of the array.</span></span> <span data-ttu-id="42f3d-261">Как и в следующих двух примерах.</span><span class="sxs-lookup"><span data-stu-id="42f3d-261">Like the next two examples.</span></span>

```powershell
,$a | Get-Member

,(1,2,3) | Get-Member
```

## <a name="manipulating-an-array"></a><span data-ttu-id="42f3d-262">Управление массивом</span><span class="sxs-lookup"><span data-stu-id="42f3d-262">Manipulating an array</span></span>

<span data-ttu-id="42f3d-263">Можно изменить элементы в массиве, добавить элемент в массив и объединить значения из двух массивов в третий массив.</span><span class="sxs-lookup"><span data-stu-id="42f3d-263">You can change the elements in an array, add an element to an array, and combine the values from two arrays into a third array.</span></span>

<span data-ttu-id="42f3d-264">Чтобы изменить значение определенного элемента в массиве, укажите имя массива и индекс элемента, который требуется изменить, а затем используйте оператор присваивания ( `=` ), чтобы указать новое значение для элемента.</span><span class="sxs-lookup"><span data-stu-id="42f3d-264">To change the value of a particular element in an array, specify the array name and the index of the element that you want to change, and then use the assignment operator (`=`) to specify a new value for the element.</span></span> <span data-ttu-id="42f3d-265">Например, чтобы изменить значение второго элемента в `$a` массиве (позиция с индексом 1) на 10, введите:</span><span class="sxs-lookup"><span data-stu-id="42f3d-265">For example, to change the value of the second item in the `$a` array (index position 1) to 10, type:</span></span>

```powershell
$a[1] = 10
```

<span data-ttu-id="42f3d-266">Для изменения значения можно также использовать метод **SetValue** массива.</span><span class="sxs-lookup"><span data-stu-id="42f3d-266">You can also use the **SetValue** method of an array to change a value.</span></span> <span data-ttu-id="42f3d-267">Следующий пример изменяет второе значение (позиция индекса 1) `$a` массива на 500:</span><span class="sxs-lookup"><span data-stu-id="42f3d-267">The following example changes the second value (index position 1) of the `$a` array to 500:</span></span>

```powershell
$a.SetValue(500,1)
```

<span data-ttu-id="42f3d-268">Оператор можно использовать `+=` для добавления элемента в массив.</span><span class="sxs-lookup"><span data-stu-id="42f3d-268">You can use the `+=` operator to add an element to an array.</span></span> <span data-ttu-id="42f3d-269">В следующем примере показано, как добавить элемент в `$a` массив.</span><span class="sxs-lookup"><span data-stu-id="42f3d-269">The following example shows how to add an element to the `$a` array.</span></span>

```powershell
$a = @(0..4)
$a += 5
```

> [!NOTE]
> <span data-ttu-id="42f3d-270">При использовании `+=` оператора PowerShell фактически создает новый массив со значениями исходного массива и добавленного значения.</span><span class="sxs-lookup"><span data-stu-id="42f3d-270">When you use the `+=` operator, PowerShell actually creates a new array with the values of the original array and the added value.</span></span> <span data-ttu-id="42f3d-271">Это может вызвать проблемы с производительностью, если операция повторяется несколько раз или размер массива слишком велик.</span><span class="sxs-lookup"><span data-stu-id="42f3d-271">This might cause performance issues if the operation is repeated several times or the size of the array is too big.</span></span>

<span data-ttu-id="42f3d-272">Удалять элементы из массива несложно, но можно создать новый массив, содержащий только выбранные элементы существующего массива.</span><span class="sxs-lookup"><span data-stu-id="42f3d-272">It is not easy to delete elements from an array, but you can create a new array that contains only selected elements of an existing array.</span></span> <span data-ttu-id="42f3d-273">Например, чтобы создать `$t` массив со всеми элементами в `$a` массиве, за исключением значения в позиции 2 индекса, введите:</span><span class="sxs-lookup"><span data-stu-id="42f3d-273">For example, to create the `$t` array with all the elements in the `$a` array except for the value at index position 2, type:</span></span>

```powershell
$t = $a[0,1 + 3..($a.length - 1)]
```

<span data-ttu-id="42f3d-274">Чтобы объединить два массива в один, используйте оператор «плюс» ( `+` ).</span><span class="sxs-lookup"><span data-stu-id="42f3d-274">To combine two arrays into a single array, use the plus operator (`+`).</span></span> <span data-ttu-id="42f3d-275">Следующий пример создает два массива, объединяет их, а затем отображает полученный объединенный массив.</span><span class="sxs-lookup"><span data-stu-id="42f3d-275">The following example creates two arrays, combines them, and then displays the resulting combined array.</span></span>

```powershell
$x = 1,3
$y = 5,9
$z = $x + $y
```

<span data-ttu-id="42f3d-276">В результате `$z` массив содержит 1, 3, 5 и 9.</span><span class="sxs-lookup"><span data-stu-id="42f3d-276">As a result, the `$z` array contains 1, 3, 5, and 9.</span></span>

<span data-ttu-id="42f3d-277">Чтобы удалить массив, присвойте значение `$null` массиву.</span><span class="sxs-lookup"><span data-stu-id="42f3d-277">To delete an array, assign a value of `$null` to the array.</span></span> <span data-ttu-id="42f3d-278">Следующая команда удаляет массив в `$a` переменной.</span><span class="sxs-lookup"><span data-stu-id="42f3d-278">The following command deletes the array in the `$a` variable.</span></span>

`$a = $null`

<span data-ttu-id="42f3d-279">Можно также использовать `Remove-Item` командлет, но присваивание значения `$null` выполняется быстрее, особенно для больших массивов.</span><span class="sxs-lookup"><span data-stu-id="42f3d-279">You can also use the `Remove-Item` cmdlet, but assigning a value of `$null` is faster, especially for large arrays.</span></span>

## <a name="arrays-of-zero-or-one"></a><span data-ttu-id="42f3d-280">Массивы 0 или 1</span><span class="sxs-lookup"><span data-stu-id="42f3d-280">Arrays of zero or one</span></span>

<span data-ttu-id="42f3d-281">Начиная с Windows PowerShell 3,0, коллекция с нулевым или одним объектом имеет свойство Count и length.</span><span class="sxs-lookup"><span data-stu-id="42f3d-281">Beginning in Windows PowerShell 3.0, a collection of zero or one object has the Count and Length property.</span></span> <span data-ttu-id="42f3d-282">Кроме того, можно индексировать в массив одного объекта.</span><span class="sxs-lookup"><span data-stu-id="42f3d-282">Also, you can index into an array of one object.</span></span> <span data-ttu-id="42f3d-283">Эта функция позволяет избежать ошибок скрипта, происходящих, когда команда, ожидающую сбор, получает менее двух элементов.</span><span class="sxs-lookup"><span data-stu-id="42f3d-283">This feature helps you to avoid scripting errors that occur when a command that expects a collection gets fewer than two items.</span></span>

<span data-ttu-id="42f3d-284">Эта функция демонстрируется в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="42f3d-284">The following examples demonstrate this feature.</span></span>

### <a name="zero-objects"></a><span data-ttu-id="42f3d-285">Нуль объектов</span><span class="sxs-lookup"><span data-stu-id="42f3d-285">Zero objects</span></span>

```powershell
$a = $null
$a.Count
$a.Length
```

```Output
0
0
```

### <a name="one-object"></a><span data-ttu-id="42f3d-286">Один объект</span><span class="sxs-lookup"><span data-stu-id="42f3d-286">One object</span></span>

```powershell
$a = 4
$a.Count
$a.Length
$a[0]
$a[-1]
```

```Output
1
1
4
4
```

## <a name="indexing-support-for-systemtuple-objects"></a><span data-ttu-id="42f3d-287">Поддержка индексирования для объектов System. Tuple</span><span class="sxs-lookup"><span data-stu-id="42f3d-287">Indexing support for System.Tuple objects</span></span>

<span data-ttu-id="42f3d-288">В PowerShell 6,1 добавлена поддержка индексированного доступа к объектам **кортежей** , аналогичная массивам.</span><span class="sxs-lookup"><span data-stu-id="42f3d-288">PowerShell 6.1 added the support for indexed access of **Tuple** objects, similar to arrays.</span></span>
<span data-ttu-id="42f3d-289">Пример:</span><span class="sxs-lookup"><span data-stu-id="42f3d-289">For example:</span></span>

```powershell
PS> $tuple = [Tuple]::Create(1, 'test')
PS> $tuple[0]
1
PS> $tuple[1]
test
PS> $tuple[0..1]
1
test
PS> $tuple[-1]
test
```

<span data-ttu-id="42f3d-290">В отличие от массивов и других объектов коллекции, объекты **кортежей** обрабатываются как один объект при передаче через конвейер или с помощью параметров, поддерживающих массивы объектов.</span><span class="sxs-lookup"><span data-stu-id="42f3d-290">Unlike arrays and other collection objects, **Tuple** objects are treated as a single object when passed through the pipeline or by parameters that support arrays of objects.</span></span>

<span data-ttu-id="42f3d-291">Дополнительные сведения см. в разделе [System. Tuple](/dotnet/api/system.tuple).</span><span class="sxs-lookup"><span data-stu-id="42f3d-291">For more information, see [System.Tuple](/dotnet/api/system.tuple).</span></span>

## <a name="see-also"></a><span data-ttu-id="42f3d-292">См. также</span><span class="sxs-lookup"><span data-stu-id="42f3d-292">See also</span></span>

- [<span data-ttu-id="42f3d-293">about_Assignment_Operators</span><span class="sxs-lookup"><span data-stu-id="42f3d-293">about_Assignment_Operators</span></span>](about_Assignment_Operators.md)
- [<span data-ttu-id="42f3d-294">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="42f3d-294">about_Hash_Tables</span></span>](about_Hash_Tables.md)
- [<span data-ttu-id="42f3d-295">about_Operators</span><span class="sxs-lookup"><span data-stu-id="42f3d-295">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="42f3d-296">about_For</span><span class="sxs-lookup"><span data-stu-id="42f3d-296">about_For</span></span>](about_For.md)
- [<span data-ttu-id="42f3d-297">about_Foreach</span><span class="sxs-lookup"><span data-stu-id="42f3d-297">about_Foreach</span></span>](about_Foreach.md)
- [<span data-ttu-id="42f3d-298">about_While</span><span class="sxs-lookup"><span data-stu-id="42f3d-298">about_While</span></span>](about_While.md)

