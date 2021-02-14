---
description: Описывает операторы, которые сравнивают значения в PowerShell.
Locale: en-US
ms.date: 01/20/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comparison_Operators
ms.openlocfilehash: 179798b490855cd463e2348acaf1292f042ba173
ms.sourcegitcommit: 77f6225ab0c8ea9faa1fe46b2ea15c178ec170e3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100500165"
---
# <a name="about-comparison-operators"></a><span data-ttu-id="52d8c-103">Сведения об операторах сравнения</span><span class="sxs-lookup"><span data-stu-id="52d8c-103">About Comparison Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="52d8c-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="52d8c-104">Short description</span></span>

<span data-ttu-id="52d8c-105">Операторы сравнения в PowerShell могут либо сравнивать два значения, либо фильтровать элементы коллекции по входному значению.</span><span class="sxs-lookup"><span data-stu-id="52d8c-105">The comparison operators in PowerShell can either compare two values or filter elements of a collection against an input value.</span></span>

## <a name="long-description"></a><span data-ttu-id="52d8c-106">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="52d8c-106">Long description</span></span>

<span data-ttu-id="52d8c-107">Операторы сравнения позволяют сравнивать значения или находить значения, соответствующие указанным шаблонам.</span><span class="sxs-lookup"><span data-stu-id="52d8c-107">Comparison operators let you compare values or finding values that match specified patterns.</span></span> <span data-ttu-id="52d8c-108">PowerShell содержит следующие операторы сравнения:</span><span class="sxs-lookup"><span data-stu-id="52d8c-108">PowerShell includes the following comparison operators:</span></span>

|    <span data-ttu-id="52d8c-109">Тип</span><span class="sxs-lookup"><span data-stu-id="52d8c-109">Type</span></span>     |   <span data-ttu-id="52d8c-110">Оператор</span><span class="sxs-lookup"><span data-stu-id="52d8c-110">Operator</span></span>   |              <span data-ttu-id="52d8c-111">Тест сравнения</span><span class="sxs-lookup"><span data-stu-id="52d8c-111">Comparison test</span></span>              |
| ----------- | ------------ | ----------------------------------------- |
| <span data-ttu-id="52d8c-112">Равенство</span><span class="sxs-lookup"><span data-stu-id="52d8c-112">Equality</span></span>    | <span data-ttu-id="52d8c-113">-eq</span><span class="sxs-lookup"><span data-stu-id="52d8c-113">-eq</span></span>          | <span data-ttu-id="52d8c-114">equals</span><span class="sxs-lookup"><span data-stu-id="52d8c-114">equals</span></span>                                    |
|             | <span data-ttu-id="52d8c-115">-ne</span><span class="sxs-lookup"><span data-stu-id="52d8c-115">-ne</span></span>          | <span data-ttu-id="52d8c-116">не равно</span><span class="sxs-lookup"><span data-stu-id="52d8c-116">not equals</span></span>                                |
|             | <span data-ttu-id="52d8c-117">-gt</span><span class="sxs-lookup"><span data-stu-id="52d8c-117">-gt</span></span>          | <span data-ttu-id="52d8c-118">больше чем</span><span class="sxs-lookup"><span data-stu-id="52d8c-118">greater than</span></span>                              |
|             | <span data-ttu-id="52d8c-119">-ge</span><span class="sxs-lookup"><span data-stu-id="52d8c-119">-ge</span></span>          | <span data-ttu-id="52d8c-120">больше или равно</span><span class="sxs-lookup"><span data-stu-id="52d8c-120">greater than or equal</span></span>                     |
|             | <span data-ttu-id="52d8c-121">-lt</span><span class="sxs-lookup"><span data-stu-id="52d8c-121">-lt</span></span>          | <span data-ttu-id="52d8c-122">меньше чем</span><span class="sxs-lookup"><span data-stu-id="52d8c-122">less than</span></span>                                 |
|             | <span data-ttu-id="52d8c-123">-le</span><span class="sxs-lookup"><span data-stu-id="52d8c-123">-le</span></span>          | <span data-ttu-id="52d8c-124">меньше или равно</span><span class="sxs-lookup"><span data-stu-id="52d8c-124">less than or equal</span></span>                        |
| <span data-ttu-id="52d8c-125">Matching</span><span class="sxs-lookup"><span data-stu-id="52d8c-125">Matching</span></span>    | <span data-ttu-id="52d8c-126">-like</span><span class="sxs-lookup"><span data-stu-id="52d8c-126">-like</span></span>        | <span data-ttu-id="52d8c-127">строка соответствует шаблону шаблона</span><span class="sxs-lookup"><span data-stu-id="52d8c-127">string matches wildcard pattern</span></span>           |
|             | <span data-ttu-id="52d8c-128">-notlike</span><span class="sxs-lookup"><span data-stu-id="52d8c-128">-notlike</span></span>     | <span data-ttu-id="52d8c-129">строка не соответствует шаблону шаблона</span><span class="sxs-lookup"><span data-stu-id="52d8c-129">string does not match wildcard pattern</span></span>    |
|             | <span data-ttu-id="52d8c-130">-match</span><span class="sxs-lookup"><span data-stu-id="52d8c-130">-match</span></span>       | <span data-ttu-id="52d8c-131">строка соответствует шаблону регулярного выражения</span><span class="sxs-lookup"><span data-stu-id="52d8c-131">string matches regex pattern</span></span>              |
|             | <span data-ttu-id="52d8c-132">-notmatch</span><span class="sxs-lookup"><span data-stu-id="52d8c-132">-notmatch</span></span>    | <span data-ttu-id="52d8c-133">строка не соответствует шаблону регулярного выражения</span><span class="sxs-lookup"><span data-stu-id="52d8c-133">string does not match regex pattern</span></span>       |
| <span data-ttu-id="52d8c-134">Замена</span><span class="sxs-lookup"><span data-stu-id="52d8c-134">Replacement</span></span> | <span data-ttu-id="52d8c-135">-Replace</span><span class="sxs-lookup"><span data-stu-id="52d8c-135">-replace</span></span>     | <span data-ttu-id="52d8c-136">заменяет строки, соответствующие шаблону регулярного выражения</span><span class="sxs-lookup"><span data-stu-id="52d8c-136">replaces strings matching a regex pattern</span></span> |
| <span data-ttu-id="52d8c-137">Containment</span><span class="sxs-lookup"><span data-stu-id="52d8c-137">Containment</span></span> | <span data-ttu-id="52d8c-138">-contains</span><span class="sxs-lookup"><span data-stu-id="52d8c-138">-contains</span></span>    | <span data-ttu-id="52d8c-139">Коллекция содержит значение</span><span class="sxs-lookup"><span data-stu-id="52d8c-139">collection contains a value</span></span>               |
|             | <span data-ttu-id="52d8c-140">-notcontains</span><span class="sxs-lookup"><span data-stu-id="52d8c-140">-notcontains</span></span> | <span data-ttu-id="52d8c-141">Коллекция не содержит значение</span><span class="sxs-lookup"><span data-stu-id="52d8c-141">collection does not contain a value</span></span>       |
|             | <span data-ttu-id="52d8c-142">-in</span><span class="sxs-lookup"><span data-stu-id="52d8c-142">-in</span></span>          | <span data-ttu-id="52d8c-143">значение находится в коллекции</span><span class="sxs-lookup"><span data-stu-id="52d8c-143">value is in a collection</span></span>                  |
|             | <span data-ttu-id="52d8c-144">-notin</span><span class="sxs-lookup"><span data-stu-id="52d8c-144">-notin</span></span>       | <span data-ttu-id="52d8c-145">значение не находится в коллекции</span><span class="sxs-lookup"><span data-stu-id="52d8c-145">value is not in a collection</span></span>              |
| <span data-ttu-id="52d8c-146">Type</span><span class="sxs-lookup"><span data-stu-id="52d8c-146">Type</span></span>        | <span data-ttu-id="52d8c-147">— имеет</span><span class="sxs-lookup"><span data-stu-id="52d8c-147">-is</span></span>          | <span data-ttu-id="52d8c-148">Оба объекта имеют одинаковый тип</span><span class="sxs-lookup"><span data-stu-id="52d8c-148">both objects are the same type</span></span>            |
|             | <span data-ttu-id="52d8c-149">-IsNot</span><span class="sxs-lookup"><span data-stu-id="52d8c-149">-isnot</span></span>       | <span data-ttu-id="52d8c-150">объекты имеют разные типы</span><span class="sxs-lookup"><span data-stu-id="52d8c-150">the objects are not the same type</span></span>         |

## <a name="common-features"></a><span data-ttu-id="52d8c-151">Общие возможности</span><span class="sxs-lookup"><span data-stu-id="52d8c-151">Common features</span></span>

<span data-ttu-id="52d8c-152">По умолчанию все операторы сравнения не учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="52d8c-152">By default, all comparison operators are case-insensitive.</span></span> <span data-ttu-id="52d8c-153">Чтобы выполнить оператор сравнения с учетом регистра, добавьте `c` после `-` .</span><span class="sxs-lookup"><span data-stu-id="52d8c-153">To make a comparison operator case-sensitive, add a `c` after the `-`.</span></span> <span data-ttu-id="52d8c-154">Например, `-ceq` — это версия с учетом регистра `-eq` .</span><span class="sxs-lookup"><span data-stu-id="52d8c-154">For example, `-ceq` is the case-sensitive version of `-eq`.</span></span> <span data-ttu-id="52d8c-155">Чтобы сделать явный учет регистра нечувствительным, добавьте `i` перед `-` .</span><span class="sxs-lookup"><span data-stu-id="52d8c-155">To make the case-insensitivity explicit, add an `i` before `-`.</span></span> <span data-ttu-id="52d8c-156">Например, `-ieq` является явной версией без учета регистра `-eq` .</span><span class="sxs-lookup"><span data-stu-id="52d8c-156">For example, `-ieq` is the explicitly case-insensitive version of `-eq`.</span></span>

<span data-ttu-id="52d8c-157">Если входные данные оператора являются скалярным значением, оператор возвращает **логическое** значение.</span><span class="sxs-lookup"><span data-stu-id="52d8c-157">When the input of an operator is a scalar value, the operator returns a **Boolean** value.</span></span> <span data-ttu-id="52d8c-158">Если входные данные являются коллекцией, оператор возвращает элементы коллекции, соответствующие правому значению выражения.</span><span class="sxs-lookup"><span data-stu-id="52d8c-158">When the input is a collection, the operator returns the elements of the collection that match the right-hand value of the expression.</span></span>
<span data-ttu-id="52d8c-159">Если в коллекции нет совпадений, операторы сравнения возвращают пустой массив.</span><span class="sxs-lookup"><span data-stu-id="52d8c-159">If there are no matches in the collection, comparison operators return an empty array.</span></span> <span data-ttu-id="52d8c-160">Пример:</span><span class="sxs-lookup"><span data-stu-id="52d8c-160">For example:</span></span>

```powershell
$a = (1, 2 -eq 3)
$a.GetType().Name
$a.Count
```

```output
Object[]
0
```

<span data-ttu-id="52d8c-161">Существует несколько исключений:</span><span class="sxs-lookup"><span data-stu-id="52d8c-161">There are a few exceptions:</span></span>

- <span data-ttu-id="52d8c-162">Операторы включения и типа всегда возвращают **логическое** значение.</span><span class="sxs-lookup"><span data-stu-id="52d8c-162">The containment and type operators always return a **Boolean** value</span></span>
- <span data-ttu-id="52d8c-163">`-replace`Оператор возвращает результат замены</span><span class="sxs-lookup"><span data-stu-id="52d8c-163">The `-replace` operator returns the replacement result</span></span>
- <span data-ttu-id="52d8c-164">`-match`Операторы и `-notmatch` также заполняют `$Matches` автоматическую переменную</span><span class="sxs-lookup"><span data-stu-id="52d8c-164">The `-match` and `-notmatch` operators also populate the `$Matches` automatic variable</span></span>

## <a name="equality-operators"></a><span data-ttu-id="52d8c-165">Операторы равенства</span><span class="sxs-lookup"><span data-stu-id="52d8c-165">Equality operators</span></span>

### <a name="-eq-and--ne"></a><span data-ttu-id="52d8c-166">-eq и -ne</span><span class="sxs-lookup"><span data-stu-id="52d8c-166">-eq and -ne</span></span>

<span data-ttu-id="52d8c-167">Если левая часть является скалярной, `-eq` возвращает **значение true** , если правая часть является точным совпадением, в противном случае `-eq` возвращает **значение false**.</span><span class="sxs-lookup"><span data-stu-id="52d8c-167">When the left-hand side is scalar, `-eq` returns **True** if the right-hand side is an exact match, otherwise, `-eq` returns **False**.</span></span> <span data-ttu-id="52d8c-168">`-ne` выполняет противоположный; При совпадении обоих сторон возвращается **значение false** . в противном случае `-ne` возвращает значение true.</span><span class="sxs-lookup"><span data-stu-id="52d8c-168">`-ne` does the opposite; it returns **False** when both sides match; otherwise, `-ne` returns True.</span></span>

<span data-ttu-id="52d8c-169">Пример:</span><span class="sxs-lookup"><span data-stu-id="52d8c-169">Example:</span></span>

```powershell
2 -eq 2                 # Output: True
2 -eq 3                 # Output: False
"abc" -eq "abc"         # Output: True
"abc" -eq "abc", "def"  # Output: False
"abc" -ne "def"         # Output: True
"abc" -ne "abc"         # Output: False
"abc" -ne "abc", "def"  # Output: True
```

<span data-ttu-id="52d8c-170">Если левая часть является коллекцией, `-eq` возвращает элементы, соответствующие правой части, и `-ne` отфильтровывает их.</span><span class="sxs-lookup"><span data-stu-id="52d8c-170">When the left-hand side is a collection, `-eq` returns those members that match the right-hand side, while `-ne` filters them out.</span></span>

<span data-ttu-id="52d8c-171">Пример:</span><span class="sxs-lookup"><span data-stu-id="52d8c-171">Example:</span></span>

```powershell
1,2,3 -eq 2             # Output: 2
"abc", "def" -eq "abc"  # Output: abc
"abc", "def" -ne "abc"  # Output: def
```

<span data-ttu-id="52d8c-172">Эти операторы обрабатывают все элементы коллекции.</span><span class="sxs-lookup"><span data-stu-id="52d8c-172">These operators process all elements of the collection.</span></span> <span data-ttu-id="52d8c-173">Пример:</span><span class="sxs-lookup"><span data-stu-id="52d8c-173">Example:</span></span>

```powershell
"zzz", "def", "zzz" -eq "zzz"
```

```output
zzz
zzz
```

<span data-ttu-id="52d8c-174">Операторы равенства принимают любые два объекта, а не только скаляр или коллекция.</span><span class="sxs-lookup"><span data-stu-id="52d8c-174">The equality operators accept any two objects, not just a scalar or collection.</span></span>
<span data-ttu-id="52d8c-175">Однако результат сравнения не гарантируется для конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="52d8c-175">But the comparison result is not guaranteed to be meaningful for the end-user.</span></span>
<span data-ttu-id="52d8c-176">В следующем примере показана эта ошибка.</span><span class="sxs-lookup"><span data-stu-id="52d8c-176">The following example demonstrates the issue.</span></span>

```powershell
class MyFileInfoSet {
    [String]$File
    [Int64]$Size
}
$a = [MyFileInfoSet]@{File = "C:\Windows\explorer.exe"; Size = 4651032}
$b = [MyFileInfoSet]@{File = "C:\Windows\explorer.exe"; Size = 4651032}
$a -eq $b
```

```Output
False
```

<span data-ttu-id="52d8c-177">В этом примере мы создали два объекта с одинаковыми свойствами.</span><span class="sxs-lookup"><span data-stu-id="52d8c-177">In this example, we created two objects with identical properties.</span></span> <span data-ttu-id="52d8c-178">Однако результат проверки равенства имеет **значение false** , так как они являются разными объектами.</span><span class="sxs-lookup"><span data-stu-id="52d8c-178">Yet, the equality test result is **False** because they are different objects.</span></span> <span data-ttu-id="52d8c-179">Чтобы создать сравнимые классы, необходимо реализовать [System. IEquatable \<T> ][2] в своем классе.</span><span class="sxs-lookup"><span data-stu-id="52d8c-179">To create comparable classes, you need to implement [System.IEquatable\<T>][2] in your class.</span></span> <span data-ttu-id="52d8c-180">В следующем примере демонстрируется частичная реализация класса **мифилеинфосет** , который реализует [System. IEquatable \<T>][2] и имеет два свойства: **File** и **size**.</span><span class="sxs-lookup"><span data-stu-id="52d8c-180">The following example demonstrates the partial implementation of a **MyFileInfoSet** class that implements [System.IEquatable\<T>][2] and has two properties, **File** and **Size**.</span></span> <span data-ttu-id="52d8c-181">`Equals()`Метод возвращает значение true, если свойства File и size двух объектов **мифилеинфосет** одинаковы.</span><span class="sxs-lookup"><span data-stu-id="52d8c-181">The `Equals()` method returns True if the File and Size properties of two **MyFileInfoSet** objects are the same.</span></span>

```powershell
class MyFileInfoSet : System.IEquatable[Object] {
    [String]$File
    [Int64]$Size

    [bool] Equals([Object] $obj) {
        return ($this.File -eq $obj.File) -and ($this.Size -eq $obj.Size)
    }
}
$a = [MyFileInfoSet]@{File = "C:\Windows\explorer.exe"; Size = 4651032}
$b = [MyFileInfoSet]@{File = "C:\Windows\explorer.exe"; Size = 4651032}
$a -eq $b
```

```Output
True
```

<span data-ttu-id="52d8c-182">Заметным примером сравнения произвольных объектов является определение того, равны ли они значению NULL.</span><span class="sxs-lookup"><span data-stu-id="52d8c-182">A prominent example of comparing arbitrary objects is to find out if they are null.</span></span> <span data-ttu-id="52d8c-183">Но если необходимо определить, является ли переменная `$null` , необходимо разместить `$null` в левой части оператора равенства.</span><span class="sxs-lookup"><span data-stu-id="52d8c-183">But if you need to determine whether a variable is `$null`, you must put `$null` on the left-hand side of the equality operator.</span></span> <span data-ttu-id="52d8c-184">Размещение с правой стороны не делает то, что вы ждете.</span><span class="sxs-lookup"><span data-stu-id="52d8c-184">Putting it on the right-hand side does not do what you expect.</span></span>

<span data-ttu-id="52d8c-185">Например, пусть `$a` массив содержит элементы со значением NULL:</span><span class="sxs-lookup"><span data-stu-id="52d8c-185">For example, let `$a` be an array containing null elements:</span></span>

```powershell
$a = 1, 2, $null, 4, $null, 6
```

<span data-ttu-id="52d8c-186">Следующие тесты `$a` не имеют значение null.</span><span class="sxs-lookup"><span data-stu-id="52d8c-186">The following tests that `$a` is not null.</span></span>

```powershell
$null -ne $a
```

```output
False
```

<span data-ttu-id="52d8c-187">Однако в следующем примере фильтрами определенными все элементы NULL из `$a` :</span><span class="sxs-lookup"><span data-stu-id="52d8c-187">The following, however, filers out all null elements from `$a`:</span></span>

```powershell
$a -ne $null # Output: 1, 2, 4, 6
```

```output
1
2
4
6
```

### <a name="-gt--ge--lt-and--le"></a><span data-ttu-id="52d8c-188">-gt,-GE,-lt и-Le</span><span class="sxs-lookup"><span data-stu-id="52d8c-188">-gt, -ge, -lt, and -le</span></span>

<span data-ttu-id="52d8c-189">`-gt`, `-ge` , `-lt` и `-le` ведут себя точно так же.</span><span class="sxs-lookup"><span data-stu-id="52d8c-189">`-gt`, `-ge`, `-lt`, and `-le` behave very similarly.</span></span> <span data-ttu-id="52d8c-190">Если обе стороны скалярны, они возвращают **значение true** или **false** в зависимости от того, как сравниваются две стороны:</span><span class="sxs-lookup"><span data-stu-id="52d8c-190">When both sides are scalar they return **True** or **False** depending on how the two sides compare:</span></span>

| <span data-ttu-id="52d8c-191">Оператор</span><span class="sxs-lookup"><span data-stu-id="52d8c-191">Operator</span></span> | <span data-ttu-id="52d8c-192">Возвращает значение true, если...</span><span class="sxs-lookup"><span data-stu-id="52d8c-192">Returns True when...</span></span>                   |
| -------- | -------------------------------------- |
| <span data-ttu-id="52d8c-193">-gt</span><span class="sxs-lookup"><span data-stu-id="52d8c-193">-gt</span></span>      | <span data-ttu-id="52d8c-194">Левая часть больше</span><span class="sxs-lookup"><span data-stu-id="52d8c-194">The left-hand side is greater</span></span>          |
| <span data-ttu-id="52d8c-195">-ge</span><span class="sxs-lookup"><span data-stu-id="52d8c-195">-ge</span></span>      | <span data-ttu-id="52d8c-196">Левая часть больше или равна</span><span class="sxs-lookup"><span data-stu-id="52d8c-196">The left-hand side is greater or equal</span></span> |
| <span data-ttu-id="52d8c-197">-lt</span><span class="sxs-lookup"><span data-stu-id="52d8c-197">-lt</span></span>      | <span data-ttu-id="52d8c-198">Левый край меньше</span><span class="sxs-lookup"><span data-stu-id="52d8c-198">The left-hand side is smaller</span></span>          |
| <span data-ttu-id="52d8c-199">-le</span><span class="sxs-lookup"><span data-stu-id="52d8c-199">-le</span></span>      | <span data-ttu-id="52d8c-200">Левая часть меньше или равна</span><span class="sxs-lookup"><span data-stu-id="52d8c-200">The left-hand side is smaller or equal</span></span> |

<span data-ttu-id="52d8c-201">В следующих примерах все инструкции возвращают значение true.</span><span class="sxs-lookup"><span data-stu-id="52d8c-201">In the following examples, all statements return True.</span></span>

```powershell
8 -gt 6  # Output: True
8 -ge 8  # Output: True
6 -lt 8  # Output: True
8 -le 8  # Output: True
```

> [!NOTE]
> <span data-ttu-id="52d8c-202">В большинстве языков программирования оператор «больше» имеет значение `>` .</span><span class="sxs-lookup"><span data-stu-id="52d8c-202">In most programming languages the greater-than operator is `>`.</span></span> <span data-ttu-id="52d8c-203">В PowerShell этот символ используется для перенаправления.</span><span class="sxs-lookup"><span data-stu-id="52d8c-203">In PowerShell, this character is used for redirection.</span></span> <span data-ttu-id="52d8c-204">Дополнительные сведения см. в разделе [about_Redirection][3].</span><span class="sxs-lookup"><span data-stu-id="52d8c-204">For details, see [about_Redirection][3].</span></span>

<span data-ttu-id="52d8c-205">Если левая часть является коллекцией, эти операторы сравнивают каждый элемент коллекции с правой стороны.</span><span class="sxs-lookup"><span data-stu-id="52d8c-205">When the left-hand side is a collection, these operators compare each member of the collection with the right-hand side.</span></span> <span data-ttu-id="52d8c-206">В зависимости от логики они либо сохраняют, либо отклоняют элемент.</span><span class="sxs-lookup"><span data-stu-id="52d8c-206">Depending on their logic, they either keep or discard the member.</span></span>

<span data-ttu-id="52d8c-207">Пример:</span><span class="sxs-lookup"><span data-stu-id="52d8c-207">Example:</span></span>

```powershell
$a=5, 6, 7, 8, 9

Write-Output "Test collection:"
$a

Write-Output "`nMembers greater than 7"
$a -gt 7

Write-Output "`nMembers greater than or equal to 7"
$a -ge 7

Write-Output "`nMembers smaller than 7"
$a -lt 7

Write-Output "`nMembers smaller than or equal to 7"
$a -le 7
```

```output
Test collection:
5
6
7
8
9

Members greater than 7
8
9

Members greater than or equal to 7
7
8
9

Members smaller than 7
5
6

Members smaller than or equal to 7
5
6
7
```

<span data-ttu-id="52d8c-208">Эти операторы работают с любым классом, реализующим [System. IComparable][1].</span><span class="sxs-lookup"><span data-stu-id="52d8c-208">These operators work with any class that implements [System.IComparable][1].</span></span>

<span data-ttu-id="52d8c-209">Примеры:</span><span class="sxs-lookup"><span data-stu-id="52d8c-209">Examples:</span></span>

```powershell
# Date comparison
[DateTime]'2001-11-12' -lt [DateTime]'2020-08-01' # True

# Sorting order comparison
'a' -lt 'z'           # True; 'a' comes before 'z'
'macOS' -ilt 'MacOS'  # False
'MacOS' -ilt 'macOS'  # False
'macOS' -clt 'MacOS'  # True; 'm' comes before 'M'
```

<span data-ttu-id="52d8c-210">В следующем примере показано, что на клавиатуре QWERTY для американского типа «а» нет символа, который сортируется после «a».</span><span class="sxs-lookup"><span data-stu-id="52d8c-210">The following example demonstrates that there is no symbol on an American QWERTY keyboard that gets sorted after 'a'.</span></span> <span data-ttu-id="52d8c-211">Он передает набор, содержащий все символы `-gt` оператора, для сравнения их с "a".</span><span class="sxs-lookup"><span data-stu-id="52d8c-211">It feeds a set containing all such symbols to the `-gt` operator to compare them against 'a'.</span></span> <span data-ttu-id="52d8c-212">Выходные данные представляют собой пустой массив.</span><span class="sxs-lookup"><span data-stu-id="52d8c-212">The output is an empty array.</span></span>

```powershell
$a=' ','`','~','!','@','#','$','%','^','&','*','(',')','_','+','-','=',
   '{','}','[',']',':',';','"','''','\','|','/','?','.','>',',','<'
$a -gt 'a'
# Output: Nothing
```

<span data-ttu-id="52d8c-213">Если две стороны операторов не являются достаточно сравнимыми, эти операторы вызывают неустранимую ошибку.</span><span class="sxs-lookup"><span data-stu-id="52d8c-213">If the two sides of the operators are not reasonably comparable, these operators raise a non-terminating error.</span></span>

## <a name="matching-operators"></a><span data-ttu-id="52d8c-214">Соответствующие операторы</span><span class="sxs-lookup"><span data-stu-id="52d8c-214">Matching operators</span></span>

<span data-ttu-id="52d8c-215">Операторы сопоставления ( `-like` ,, `-notlike` `-match` и `-notmatch` ) находят элементы, которые соответствуют или не соответствуют указанному шаблону.</span><span class="sxs-lookup"><span data-stu-id="52d8c-215">The matching operators (`-like`, `-notlike`, `-match`, and `-notmatch`) find elements that match or do not match a specified pattern.</span></span> <span data-ttu-id="52d8c-216">Шаблон для `-like` и `-notlike` является выражением-шаблоном (содержащим `*` , `?` и `[ ]` ), а `-match` также `-notmatch` принимает регулярное выражение (Regex).</span><span class="sxs-lookup"><span data-stu-id="52d8c-216">The pattern for `-like` and `-notlike` is a wildcard expression (containing `*`, `?`, and `[ ]`), while `-match` and `-notmatch` accept a regular expression (Regex).</span></span>

<span data-ttu-id="52d8c-217">Синтаксис:</span><span class="sxs-lookup"><span data-stu-id="52d8c-217">The syntax is:</span></span>

```
<string[]> -like    <wildcard-expression>
<string[]> -notlike <wildcard-expression>
<string[]> -match    <regular-expression>
<string[]> -notmatch <regular-expression>
```

<span data-ttu-id="52d8c-218">Если входные данные этих операторов являются скалярным значением, они возвращают **логическое** значение.</span><span class="sxs-lookup"><span data-stu-id="52d8c-218">When the input of these operators is a scalar value, they return a **Boolean** value.</span></span> <span data-ttu-id="52d8c-219">Если входные данные являются коллекцией значений, операторы возвращают все совпадающие элементы.</span><span class="sxs-lookup"><span data-stu-id="52d8c-219">When the input is a collection of values, the operators return any matching members.</span></span> <span data-ttu-id="52d8c-220">Если в коллекции нет совпадений, операторы возвращают пустой массив.</span><span class="sxs-lookup"><span data-stu-id="52d8c-220">If there are no matches in a collection, the operators return an empty array.</span></span>

### <a name="-like-and--notlike"></a><span data-ttu-id="52d8c-221">-Like и-notlike</span><span class="sxs-lookup"><span data-stu-id="52d8c-221">-like and -notlike</span></span>

<span data-ttu-id="52d8c-222">`-like` и `-notlike` ведут себя аналогично `-eq` и `-ne` , но правая часть может быть строкой, содержащей [подстановочные знаки](about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="52d8c-222">`-like` and `-notlike` behave similarly to `-eq` and `-ne`, but the right-hand side could be a string containing [wildcards](about_Wildcards.md).</span></span>

<span data-ttu-id="52d8c-223">Пример:</span><span class="sxs-lookup"><span data-stu-id="52d8c-223">Example:</span></span>

```powershell
"PowerShell" -like    "*shell"           # Output: True
"PowerShell" -notlike "*shell"           # Output: False
"PowerShell" -like    "Power?hell"       # Output: True
"PowerShell" -notlike "Power?hell"       # Output: False
"PowerShell" -like    "Power[p-w]hell"   # Output: True
"PowerShell" -notlike "Power[p-w]hell"   # Output: False

"PowerShell", "Server" -like "*shell"    # Output: PowerShell
"PowerShell", "Server" -notlike "*shell" # Output: Server
```

### <a name="-match-and--notmatch"></a><span data-ttu-id="52d8c-224">-Match и-notmatch</span><span class="sxs-lookup"><span data-stu-id="52d8c-224">-match and -notmatch</span></span>

<span data-ttu-id="52d8c-225">`-match` и `-notmatch` используют регулярные выражения для поиска шаблона в левой части значений.</span><span class="sxs-lookup"><span data-stu-id="52d8c-225">`-match` and `-notmatch` use regular expressions to search for pattern in the left-hand side values.</span></span> <span data-ttu-id="52d8c-226">Регулярные выражения могут сопоставлять сложные шаблоны, такие как адреса электронной почты, пути UNC или отформатированные номера телефонов.</span><span class="sxs-lookup"><span data-stu-id="52d8c-226">Regular expressions can match complex patterns like email addresses, UNC paths, or formatted phone numbers.</span></span> <span data-ttu-id="52d8c-227">Правая строка должна соответствовать правилам [регулярных выражений](about_Regular_Expressions.md) .</span><span class="sxs-lookup"><span data-stu-id="52d8c-227">The right-hand side string must adhere to the [regular expressions](about_Regular_Expressions.md) rules.</span></span>

<span data-ttu-id="52d8c-228">Скалярные примеры:</span><span class="sxs-lookup"><span data-stu-id="52d8c-228">Scalar examples:</span></span>

```powershell
# Partial match test, showing how differently -match and -like behave
"PowerShell" -match 'shell'        # Output: True
"PowerShell" -like  'shell'        # Output: False

# Regex syntax test
"PowerShell" -match    '^Power\w+' # Output: True
'bag'        -notmatch 'b[iou]g'   # Output: True
```

<span data-ttu-id="52d8c-229">Если входные данные являются коллекцией, операторы возвращают соответствующие члены этой коллекции.</span><span class="sxs-lookup"><span data-stu-id="52d8c-229">If the input is a collection, the operators return the matching members of that collection.</span></span>

<span data-ttu-id="52d8c-230">Примеры коллекций:</span><span class="sxs-lookup"><span data-stu-id="52d8c-230">Collection examples:</span></span>

```powershell
"PowerShell", "Super PowerShell", "Power's hell" -match '^Power\w+'
# Output: PowerShell

"Rhell", "Chell", "Mel", "Smell", "Shell" -match "hell"
# Output: Rhell, Chell, Shell

"Bag", "Beg", "Big", "Bog", "Bug"  -match 'b[iou]g'
#Output: Big, Bog, Bug

"Bag", "Beg", "Big", "Bog", "Bug"  -notmatch 'b[iou]g'
#Output: Bag, Beg
```

<span data-ttu-id="52d8c-231">`-match` и `-notmatch` поддерживают регулярные выражения группы записи.</span><span class="sxs-lookup"><span data-stu-id="52d8c-231">`-match` and `-notmatch` support regex capture groups.</span></span> <span data-ttu-id="52d8c-232">При каждом запуске они перезапишут `$Matches` автоматическую переменную.</span><span class="sxs-lookup"><span data-stu-id="52d8c-232">Each time they run, they overwrite the `$Matches` automatic variable.</span></span> <span data-ttu-id="52d8c-233">Если `<input>` является коллекцией, `$Matches` переменная имеет значение `$null` .</span><span class="sxs-lookup"><span data-stu-id="52d8c-233">When `<input>` is a collection the `$Matches` variable is `$null`.</span></span> <span data-ttu-id="52d8c-234">`$Matches` — Это **хэш-таблица** , которая всегда содержит ключ с именем "0", в котором сохраняется все совпадение.</span><span class="sxs-lookup"><span data-stu-id="52d8c-234">`$Matches` is a **Hashtable** that always has a key named '0', which stores the entire match.</span></span> <span data-ttu-id="52d8c-235">Если регулярное выражение содержит группы захвата, `$Matches` содержит дополнительные ключи для каждой группы.</span><span class="sxs-lookup"><span data-stu-id="52d8c-235">If the regular expression contains capture groups, the `$Matches` contains additional keys for each group.</span></span>

<span data-ttu-id="52d8c-236">Пример:</span><span class="sxs-lookup"><span data-stu-id="52d8c-236">Example:</span></span>

```powershell
$string = 'The last logged on user was CONTOSO\jsmith'
$string -match 'was (?<domain>.+)\\(?<user>.+)'

$Matches

Write-Output "`nDomain name:"
$Matches.domain

Write-Output "`nUser name:"
$Matches.user
```

```output
True

Name                           Value
----                           -----
domain                         CONTOSO
user                           jsmith
0                              was CONTOSO\jsmith

Domain name:
CONTOSO

User name:
jsmith
```

<span data-ttu-id="52d8c-237">Дополнительные сведения см. в разделе [about_Regular_Expressions](about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="52d8c-237">For details, see [about_Regular_Expressions](about_Regular_Expressions.md).</span></span>

## <a name="replacement-operator"></a><span data-ttu-id="52d8c-238">Оператор замены</span><span class="sxs-lookup"><span data-stu-id="52d8c-238">Replacement operator</span></span>

### <a name="replacement-with-regular-expressions"></a><span data-ttu-id="52d8c-239">Замена с помощью регулярных выражений</span><span class="sxs-lookup"><span data-stu-id="52d8c-239">Replacement with regular expressions</span></span>

<span data-ttu-id="52d8c-240">Например `-match` , `-replace` оператор использует регулярные выражения для поиска указанного шаблона.</span><span class="sxs-lookup"><span data-stu-id="52d8c-240">Like `-match`, the `-replace` operator uses regular expressions to find the specified pattern.</span></span> <span data-ttu-id="52d8c-241">Но в отличие от `-match` он заменяет совпадения другим указанным значением.</span><span class="sxs-lookup"><span data-stu-id="52d8c-241">But unlike `-match`, it replaces the matches with another specified value.</span></span>

<span data-ttu-id="52d8c-242">Синтаксис:</span><span class="sxs-lookup"><span data-stu-id="52d8c-242">Syntax:</span></span>

```
<input> -replace <regular-expression>, <substitute>
```

<span data-ttu-id="52d8c-243">Оператор заменяет все или часть значения указанным значением с помощью регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="52d8c-243">The operator replaces all or part of a value with the specified value using regular expressions.</span></span> <span data-ttu-id="52d8c-244">Оператор можно использовать для многих административных задач, таких как переименование файлов.</span><span class="sxs-lookup"><span data-stu-id="52d8c-244">You can use the operator for many administrative tasks, such as renaming files.</span></span> <span data-ttu-id="52d8c-245">Например, следующая команда изменяет расширения имен файлов всех `.txt` файлов на `.log` :</span><span class="sxs-lookup"><span data-stu-id="52d8c-245">For example, the following command changes the file name extensions of all `.txt` files to `.log`:</span></span>

```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.name -replace '\.txt$','.log' }
```

<span data-ttu-id="52d8c-246">По умолчанию `-replace` оператор не учитывает регистр.</span><span class="sxs-lookup"><span data-stu-id="52d8c-246">By default, the `-replace` operator is case-insensitive.</span></span> <span data-ttu-id="52d8c-247">Чтобы сделать его чувствительным к регистру, используйте `-creplace` .</span><span class="sxs-lookup"><span data-stu-id="52d8c-247">To make it case sensitive, use `-creplace`.</span></span> <span data-ttu-id="52d8c-248">Чтобы явно сделать регистр без учета регистра, используйте `-ireplace` .</span><span class="sxs-lookup"><span data-stu-id="52d8c-248">To make it explicitly case-insensitive, use `-ireplace`.</span></span>

<span data-ttu-id="52d8c-249">Примеры:</span><span class="sxs-lookup"><span data-stu-id="52d8c-249">Examples:</span></span>

```powershell
"book" -ireplace "B", "C" # Case insensitive
"book" -creplace "B", "C" # Case-sensitive; hence, nothing to replace
```

```Output
Cook
book
```

### <a name="regular-expressions-substitutions"></a><span data-ttu-id="52d8c-250">Подстановки регулярных выражений</span><span class="sxs-lookup"><span data-stu-id="52d8c-250">Regular expressions substitutions</span></span>

<span data-ttu-id="52d8c-251">Можно также использовать регулярные выражения для динамической замены текста с помощью захваченных групп и подстановок.</span><span class="sxs-lookup"><span data-stu-id="52d8c-251">It is also possible to use regular expressions to dynamically replace text using capturing groups, and substitutions.</span></span> <span data-ttu-id="52d8c-252">На группы записи можно ссылаться в `<substitute>` строке, используя знак доллара ( `$` ) перед идентификатором группы.</span><span class="sxs-lookup"><span data-stu-id="52d8c-252">Capture groups can be referenced in the `<substitute>` string using the dollar sign (`$`) character before the group identifier.</span></span>

<span data-ttu-id="52d8c-253">В следующем примере `-replace` оператор принимает имя пользователя в формате `DomainName\Username` и преобразует его в `Username@DomainName` Формат:</span><span class="sxs-lookup"><span data-stu-id="52d8c-253">In the following example, the `-replace` operator accepts a username in the form of `DomainName\Username` and converts to the `Username@DomainName` format:</span></span>

```powershell
$SearchExp = '^(?<DomainName>[\w-.]+)\\(?<Username>[\w-.]+)$'
$ReplaceExp = '${Username}@${DomainName}'

'Contoso.local\John.Doe' -replace $SearchExp,$ReplaceExp
```

```output
John.Doe@Contoso.local
```

> [!WARNING]
> <span data-ttu-id="52d8c-254">Этот `$` символ имеет синтатик роли в PowerShell и в регулярных выражениях:</span><span class="sxs-lookup"><span data-stu-id="52d8c-254">The `$` character has syntatic roles in both PowerShell and regular expressions:</span></span>
>
> - <span data-ttu-id="52d8c-255">В PowerShell между двойными кавычками они обозначают переменные и действуют как операторы части выражения.</span><span class="sxs-lookup"><span data-stu-id="52d8c-255">In PowerShell, between double quotation marks, it designates variables and acts as a subexpression operator.</span></span>
> - <span data-ttu-id="52d8c-256">В строках поиска регулярных выражений это означает конец строки.</span><span class="sxs-lookup"><span data-stu-id="52d8c-256">In Regex search strings, it denotes end of the line</span></span>
> - <span data-ttu-id="52d8c-257">В строках подстановки Regex он означает захваченные группы. Не забудьте поместить регулярные выражения в одинарные кавычки или вставить `` ` `` символ обратной черты () перед ними.</span><span class="sxs-lookup"><span data-stu-id="52d8c-257">In Regex substitution strings, it denotes captured groups.Be sure to either put your regular expressions between single quotation marks or insert a backtick (`` ` ``) character before them.</span></span>

<span data-ttu-id="52d8c-258">Пример:</span><span class="sxs-lookup"><span data-stu-id="52d8c-258">For example:</span></span>

```powershell
$1 = 'Goodbye'

'Hello World' -replace '(\w+) \w+', "$1 Universe"
# Output: Goodbye Universe

'Hello World' -replace '(\w+) \w+', '$1 Universe'
# Output: Hello Universe
```

<span data-ttu-id="52d8c-259">`$$` в регулярном выражении обозначает литерал `$` .</span><span class="sxs-lookup"><span data-stu-id="52d8c-259">`$$` in Regex denotes a literal `$`.</span></span> <span data-ttu-id="52d8c-260">`$$`В строке подстановки, чтобы включить литерал `$` в результирующую замену.</span><span class="sxs-lookup"><span data-stu-id="52d8c-260">This `$$` in the substitution string to include a literal `$` in the resulting replacement.</span></span> <span data-ttu-id="52d8c-261">Пример:</span><span class="sxs-lookup"><span data-stu-id="52d8c-261">For example:</span></span>

```powershell
'5.72' -replace '(.+)', '$ $1' # Output: $ 5.72
'5.72' -replace '(.+)', '$$$1' # Output: $5.72
'5.72' -replace '(.+)', '$$1'  # Output: $1
```

<span data-ttu-id="52d8c-262">Дополнительные сведения см. в разделе [about_Regular_Expressions](about_Regular_Expressions.md) и [подстановки в регулярных выражениях][4].</span><span class="sxs-lookup"><span data-stu-id="52d8c-262">To learn more, see [about_Regular_Expressions](about_Regular_Expressions.md) and [Substitutions in Regular Expressions][4].</span></span>

### <a name="substituting-in-a-collection"></a><span data-ttu-id="52d8c-263">Подстановка в коллекции</span><span class="sxs-lookup"><span data-stu-id="52d8c-263">Substituting in a collection</span></span>

<span data-ttu-id="52d8c-264">Если `<input>` `-replace` оператор to является коллекцией, PowerShell применяет замену к каждому значению в коллекции.</span><span class="sxs-lookup"><span data-stu-id="52d8c-264">When the `<input>` to the `-replace` operator is a collection, PowerShell applies the replacement to every value in the collection.</span></span> <span data-ttu-id="52d8c-265">Пример:</span><span class="sxs-lookup"><span data-stu-id="52d8c-265">For example:</span></span>

```powershell
"B1","B2","B3","B4","B5" -replace "B", 'a'
a1
a2
a3
a4
a5
```

### <a name="replacement-with-a-script-block"></a><span data-ttu-id="52d8c-266">Замена блоком сценария</span><span class="sxs-lookup"><span data-stu-id="52d8c-266">Replacement with a script block</span></span>

<span data-ttu-id="52d8c-267">В PowerShell 6 и более поздних версиях `-replace` оператор также принимает блок сценария, который выполняет замену.</span><span class="sxs-lookup"><span data-stu-id="52d8c-267">In PowerShell 6 and later, the `-replace` operator also accepts a script block that performs the replacement.</span></span> <span data-ttu-id="52d8c-268">Блок скрипта выполняется один раз для каждого совпадения.</span><span class="sxs-lookup"><span data-stu-id="52d8c-268">The script block runs once for every match.</span></span>

<span data-ttu-id="52d8c-269">Синтаксис:</span><span class="sxs-lookup"><span data-stu-id="52d8c-269">Syntax:</span></span>

```powershell
<String> -replace <regular-expression>, {<Script-block>}
```

<span data-ttu-id="52d8c-270">В блоке скрипта используйте `$_` автоматическую переменную для доступа к заменяемому входному тексту и другим полезным сведениям.</span><span class="sxs-lookup"><span data-stu-id="52d8c-270">Within the script block, use the `$_` automatic variable to access the input text being replaced and other useful information.</span></span> <span data-ttu-id="52d8c-271">Тип класса этой переменной — [System. Text. RegularExpressions. Match][2].</span><span class="sxs-lookup"><span data-stu-id="52d8c-271">This variable's class type is [System.Text.RegularExpressions.Match][2].</span></span>

<span data-ttu-id="52d8c-272">В следующем примере каждая последовательность из трех цифр заменяется эквивалентными символами.</span><span class="sxs-lookup"><span data-stu-id="52d8c-272">The following example replaces each sequence of three digits with the character equivalents.</span></span> <span data-ttu-id="52d8c-273">Блок скрипта выполняется для каждого набора из трех цифр, которые необходимо заменить.</span><span class="sxs-lookup"><span data-stu-id="52d8c-273">The script block runs for each set of three digits that needs to be replaced.</span></span>

```powershell
"072101108108111" -replace "\d{3}", {return [char][int]$_.Value}
```

```output
Hello
```

## <a name="containment-operators"></a><span data-ttu-id="52d8c-274">Операторы вложения</span><span class="sxs-lookup"><span data-stu-id="52d8c-274">Containment operators</span></span>

<span data-ttu-id="52d8c-275">Операторы вложения ( `-contains` , `-notcontains` , `-in` и `-notin` ) похожи на операторы равенства, за исключением того, что они всегда возвращают **логическое** значение, даже если входные данные являются коллекцией.</span><span class="sxs-lookup"><span data-stu-id="52d8c-275">The containment operators (`-contains`, `-notcontains`, `-in`, and `-notin`) are similar to the equality operators, except that they always return a **Boolean** value, even when the input is a collection.</span></span> <span data-ttu-id="52d8c-276">Эти операторы прекращают сравнение, как только они обнаруживают первое совпадение, в то время как операторы равенства оценивают все входные элементы.</span><span class="sxs-lookup"><span data-stu-id="52d8c-276">These operators stop comparing as soon as they detect the first match, whereas the equality operators evaluate all input members.</span></span> <span data-ttu-id="52d8c-277">В очень больших коллекциях эти операторы возвращают более быстрый результат, чем операторы равенства.</span><span class="sxs-lookup"><span data-stu-id="52d8c-277">In a very large collection, these operators return quicker than the equality operators.</span></span>

<span data-ttu-id="52d8c-278">Синтаксис:</span><span class="sxs-lookup"><span data-stu-id="52d8c-278">Syntax:</span></span>

```
<Collection> -contains <Test-object>
<Collection> -notcontains <Test-object>
<Test-object> -in <Collection>
<Test-object> -notin <Collection>
```

### <a name="-contains-and--notcontains"></a><span data-ttu-id="52d8c-279">-Contains и-notcontains</span><span class="sxs-lookup"><span data-stu-id="52d8c-279">-contains and -notcontains</span></span>

<span data-ttu-id="52d8c-280">Эти операторы определяют, включает ли набор определенный элемент.</span><span class="sxs-lookup"><span data-stu-id="52d8c-280">These operators tell whether a set includes a certain element.</span></span> <span data-ttu-id="52d8c-281">`-contains` Возвращает значение true, если правая часть (тестовый объект) соответствует одному из элементов в наборе.</span><span class="sxs-lookup"><span data-stu-id="52d8c-281">`-contains` returns True when the right-hand side (test object) matches one of the elements in the set.</span></span> <span data-ttu-id="52d8c-282">`-notcontains` Вместо этого возвращает значение false.</span><span class="sxs-lookup"><span data-stu-id="52d8c-282">`-notcontains` returns False instead.</span></span> <span data-ttu-id="52d8c-283">Если объект теста является коллекцией, эти операторы используют равенство ссылок, т. е. они проверяют, является ли один из элементов набора одним и тем же экземпляром тестового объекта.</span><span class="sxs-lookup"><span data-stu-id="52d8c-283">When the test object is a collection, these operators use reference equality, i.e. they check whether one of the set's elements is the same instance of the test object.</span></span>

<span data-ttu-id="52d8c-284">Примеры:</span><span class="sxs-lookup"><span data-stu-id="52d8c-284">Examples:</span></span>

```powershell
"abc", "def" -contains "def"                  # Output: True
"abc", "def" -notcontains "def"               # Output: False
"Windows", "PowerShell" -contains "Shell"     # Output: False
"Windows", "PowerShell" -notcontains "Shell"  # Output: True
"abc", "def", "ghi" -contains "abc", "def"    # Output: False
"abc", "def", "ghi" -notcontains "abc", "def" # Output: True
```

<span data-ttu-id="52d8c-285">Более сложные примеры:</span><span class="sxs-lookup"><span data-stu-id="52d8c-285">More complex examples:</span></span>

```powershell
$DomainServers = "ContosoDC1","ContosoDC2","ContosoFileServer","ContosoDNS",
                 "ContosoDHCP","ContosoWSUS"
$thisComputer  = "ContosoDC2"

$DomainServers -contains $thisComputer
# Output: True

$a = "abc", "def"
"abc", "def", "ghi" -contains $a # Output: False
$a, "ghi" -contains $a           # Output: True
```

### <a name="-in-and--notin"></a><span data-ttu-id="52d8c-286">-in и-notin</span><span class="sxs-lookup"><span data-stu-id="52d8c-286">-in and -notin</span></span>

<span data-ttu-id="52d8c-287">`-in` `notin` Операторы and были введены в PowerShell 3 в качестве синтаксических обратных `contains` `-notcontain` операторов и.</span><span class="sxs-lookup"><span data-stu-id="52d8c-287">The `-in` and -`notin` operators were introduced in PowerShell 3 as the syntactic reverse of the of `contains` and `-notcontain` operators.</span></span> <span data-ttu-id="52d8c-288">`-in` Возвращает **значение true** , если левая `<test-object>` часть соответствует одному из элементов в наборе.</span><span class="sxs-lookup"><span data-stu-id="52d8c-288">`-in` returns **True** when the left-hand side `<test-object>` matches one of the elements in the set.</span></span> <span data-ttu-id="52d8c-289">`-notin` Вместо этого возвращает **значение false** .</span><span class="sxs-lookup"><span data-stu-id="52d8c-289">`-notin` returns **False** instead.</span></span> <span data-ttu-id="52d8c-290">Если тестовый объект является набором, эти операторы используют равенство ссылок для проверки того, является ли один из элементов набора одним и тем же экземпляром тестового объекта.</span><span class="sxs-lookup"><span data-stu-id="52d8c-290">When the test object is a set, these operators use reference equality to check whether one of the set's elements is the same instance of the test object.</span></span>

<span data-ttu-id="52d8c-291">Следующие примеры выполняют те же действия, что и примеры для `-contain` и `-notcontain` Do, но они записываются с помощью `-in` и `-notin` .</span><span class="sxs-lookup"><span data-stu-id="52d8c-291">The following examples do the same thing that the examples for `-contain` and `-notcontain` do, but they are written with `-in` and `-notin` instead.</span></span>

```powershell
"def" -in "abc", "def"                  # Output: True
"def" -notin "abc", "def"               # Output: False
"Shell" -in "Windows", "PowerShell"     # Output: False
"Shell" -notin "Windows", "PowerShell"  # Output: True
"abc", "def" -in "abc", "def", "ghi"    # Output: False
"abc", "def" -notin "abc", "def", "ghi" # Output: True
```

<span data-ttu-id="52d8c-292">Более сложные примеры:</span><span class="sxs-lookup"><span data-stu-id="52d8c-292">More complex examples:</span></span>

```powershell
$DomainServers = "ContosoDC1","ContosoDC2","ContosoFileServer","ContosoDNS",
                 "ContosoDHCP","ContosoWSUS"
$thisComputer  = "ContosoDC2"

$thisComputer -in $DomainServers
# Output: True

$a = "abc", "def"
$a -in "abc", "def", "ghi" # Output: False
$a -in $a, "ghi"           # Output: True
```

## <a name="type-comparison"></a><span data-ttu-id="52d8c-293">Сравнение типов</span><span class="sxs-lookup"><span data-stu-id="52d8c-293">Type comparison</span></span>

<span data-ttu-id="52d8c-294">Операторы сравнения типов ( `-is` и `-isnot` ) используются для определения того, является ли объект конкретным типом.</span><span class="sxs-lookup"><span data-stu-id="52d8c-294">The type comparison operators (`-is` and `-isnot`) are used to determine if an object is a specific type.</span></span>

<span data-ttu-id="52d8c-295">Синтаксис:</span><span class="sxs-lookup"><span data-stu-id="52d8c-295">Syntax:</span></span>

```powershell
<object> -is <type-reference>
<object> -isnot <type-reference>
```

<span data-ttu-id="52d8c-296">Пример:</span><span class="sxs-lookup"><span data-stu-id="52d8c-296">Example:</span></span>

```powershell
$a = 1
$b = "1"
$a -is [int]           # Output: True
$a -is $b.GetType()    # Output: False
$b -isnot [int]        # Output: True
$a -isnot $b.GetType() # Output: True
```

## <a name="see-also"></a><span data-ttu-id="52d8c-297">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="52d8c-297">SEE ALSO</span></span>

- [<span data-ttu-id="52d8c-298">about_Operators</span><span class="sxs-lookup"><span data-stu-id="52d8c-298">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="52d8c-299">about_Regular_Expressions</span><span class="sxs-lookup"><span data-stu-id="52d8c-299">about_Regular_Expressions</span></span>](about_Regular_Expressions.md)
- [<span data-ttu-id="52d8c-300">about_Wildcards</span><span class="sxs-lookup"><span data-stu-id="52d8c-300">about_Wildcards</span></span>](about_Wildcards.md)
- [<span data-ttu-id="52d8c-301">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="52d8c-301">Compare-Object</span></span>](xref:Microsoft.PowerShell.Utility.Compare-Object)
- [<span data-ttu-id="52d8c-302">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="52d8c-302">Foreach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)
- [<span data-ttu-id="52d8c-303">Where-Object</span><span class="sxs-lookup"><span data-stu-id="52d8c-303">Where-Object</span></span>](xref:Microsoft.PowerShell.Core.Where-Object)

[1]: /dotnet/api/system.icomparable
[2]: /dotnet/api/system.iequatable-1
[3]: /dotnet/api/system.text.regularexpressions.match
[4]: about_Redirection.md#potential-confusion-with-comparison-operators
[5]: /dotnet/standard/base-types/substitutions-in-regular-expressions
