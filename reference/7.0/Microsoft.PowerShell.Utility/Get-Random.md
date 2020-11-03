---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-random?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Random
ms.openlocfilehash: c45b234445a7bc2b54aefb080d2d3da65433d412
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226045"
---
# <span data-ttu-id="fbfc9-103">Get-Random</span><span class="sxs-lookup"><span data-stu-id="fbfc9-103">Get-Random</span></span>

## <span data-ttu-id="fbfc9-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="fbfc9-104">SYNOPSIS</span></span>
<span data-ttu-id="fbfc9-105">Возвращает случайное число или случайным образом выбирает объекты из коллекции.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-105">Gets a random number, or selects objects randomly from a collection.</span></span>

## <span data-ttu-id="fbfc9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fbfc9-106">SYNTAX</span></span>

### <span data-ttu-id="fbfc9-107">Рандомнумберпараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="fbfc9-107">RandomNumberParameterSet (Default)</span></span>

```
Get-Random [-SetSeed <Int32>] [[-Maximum] <Object>] [-Minimum <Object>] [-Count <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="fbfc9-108">рандомлиститемпараметерсет</span><span class="sxs-lookup"><span data-stu-id="fbfc9-108">RandomListItemParameterSet</span></span>

```
Get-Random [-SetSeed <Int32>] [-InputObject] <Object[]> [-Count <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="fbfc9-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fbfc9-109">DESCRIPTION</span></span>

<span data-ttu-id="fbfc9-110">`Get-Random`Командлет возвращает число, выбранное случайным образом.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-110">The `Get-Random` cmdlet gets a randomly selected number.</span></span> <span data-ttu-id="fbfc9-111">При отправке коллекции объектов в `Get-Random` она получает один или несколько случайно выбранных объектов из коллекции.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-111">If you submit a collection of objects to `Get-Random`, it gets one or more randomly selected objects from the collection.</span></span>

<span data-ttu-id="fbfc9-112">Без параметров или входных данных `Get-Random` команда возвращает случайное выбранное 32-разрядное целое число без знака в диапазоне от 0 (ноль) до **Int32. MaxValue** ( `0x7FFFFFFF` , `2,147,483,647` ).</span><span class="sxs-lookup"><span data-stu-id="fbfc9-112">Without parameters or input, a `Get-Random` command returns a randomly selected 32-bit unsigned integer between 0 (zero) and **Int32.MaxValue** (`0x7FFFFFFF`, `2,147,483,647`).</span></span>

<span data-ttu-id="fbfc9-113">Можно использовать параметры `Get-Random` , чтобы указать начальное значение, минимальное и максимальное значения, а также количество объектов, возвращаемых из отправленной коллекции.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-113">You can use the parameters of `Get-Random` to specify a seed number, minimum and maximum values, and the number of objects returned from a submitted collection.</span></span>

## <span data-ttu-id="fbfc9-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="fbfc9-114">EXAMPLES</span></span>

### <span data-ttu-id="fbfc9-115">Пример 1. получение случайного целого числа</span><span class="sxs-lookup"><span data-stu-id="fbfc9-115">Example 1: Get a random integer</span></span>

<span data-ttu-id="fbfc9-116">Эта команда возвращает случайное целое число от 0 (0) до **Int32. MaxValue**.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-116">This command gets a random integer between 0 (zero) and **Int32.MaxValue**.</span></span>

```powershell
Get-Random
```

```Output
3951433
```

### <span data-ttu-id="fbfc9-117">Пример 2. получение случайного целого числа от 0 до 99</span><span class="sxs-lookup"><span data-stu-id="fbfc9-117">Example 2: Get a random integer between 0 and 99</span></span>

```powershell
Get-Random -Maximum 100
```

```Output
47
```

### <span data-ttu-id="fbfc9-118">Пример 3. получение случайного целого числа от-100 до 99</span><span class="sxs-lookup"><span data-stu-id="fbfc9-118">Example 3: Get a random integer between -100 and 99</span></span>

```powershell
Get-Random -Minimum -100 -Maximum 100
```

```Output
56
```

### <span data-ttu-id="fbfc9-119">Пример 4. получение случайного числа с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="fbfc9-119">Example 4: Get a random floating-point number</span></span>

<span data-ttu-id="fbfc9-120">Эта команда возвращает случайное число с плавающей запятой, которое больше или равно 10,7 и меньше 20,92.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-120">This command gets a random floating-point number greater than or equal to 10.7 and less than 20.92.</span></span>

```powershell
Get-Random -Minimum 10.7 -Maximum 20.93
```

```Output
18.08467273887
```

### <span data-ttu-id="fbfc9-121">Пример 5. получение случайного целого числа из массива</span><span class="sxs-lookup"><span data-stu-id="fbfc9-121">Example 5: Get a random integer from an array</span></span>

<span data-ttu-id="fbfc9-122">Эта команда возвращает случайное число из указанного массива.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-122">This command gets a randomly selected number from the specified array.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random
```

```Output
8
```

### <span data-ttu-id="fbfc9-123">Пример 6. получение нескольких случайных целых чисел из массива</span><span class="sxs-lookup"><span data-stu-id="fbfc9-123">Example 6: Get several random integers from an array</span></span>

<span data-ttu-id="fbfc9-124">Эта команда получает три случайно выбранных числа в случайном порядке из массива.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-124">This command gets three randomly selected numbers in random order from an array.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random -Count 3
```

```Output
3
1
13
```

### <span data-ttu-id="fbfc9-125">Пример 7. случайный выбор всей коллекции</span><span class="sxs-lookup"><span data-stu-id="fbfc9-125">Example 7: Randomize an entire collection</span></span>

<span data-ttu-id="fbfc9-126">Эта команда возвращает всю коллекцию в случайном порядке.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-126">This command returns the entire collection in random order.</span></span>

<span data-ttu-id="fbfc9-127">Значение параметра **Count** является статическим свойством **MaxValue** целых чисел.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-127">The value of the **Count** parameter is the **MaxValue** static property of integers.</span></span>

<span data-ttu-id="fbfc9-128">Чтобы вернуть всю коллекцию в случайном порядке, введите любое число, которое больше или равно количеству объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-128">To return an entire collection in random order, enter any number that is greater than or equal to the number of objects in the collection.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random -Count ([int]::MaxValue)
```

```Output
2
3
5
1
8
13
```

### <span data-ttu-id="fbfc9-129">Пример 8. получение случайного нечислового значения</span><span class="sxs-lookup"><span data-stu-id="fbfc9-129">Example 8: Get a random non-numeric value</span></span>

<span data-ttu-id="fbfc9-130">Эта команда возвращает случайное значение из коллекции, элементы которой не являются числами.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-130">This command returns a random value from a non-numeric collection.</span></span>

```powershell
"red", "yellow", "blue" | Get-Random
```

```Output
yellow
```

### <span data-ttu-id="fbfc9-131">Пример 9. Использование параметра SetSeed</span><span class="sxs-lookup"><span data-stu-id="fbfc9-131">Example 9: Use the SetSeed parameter</span></span>

<span data-ttu-id="fbfc9-132">В этом примере показан результат применения параметра **SetSeed**.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-132">This example shows the effect of using the **SetSeed** parameter.</span></span>

<span data-ttu-id="fbfc9-133">Поскольку **SetSeed** создает неслучайное поведение, он обычно используется только для воспроизведения результатов, например при отладке или анализе скрипта.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-133">Because **SetSeed** produces non-random behavior, it's typically used only to reproduce results, such as when debugging or analyzing a script.</span></span>

```powershell
# Commands with the default seed are pseudorandom
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100
Get-Random -Maximum 100
Get-Random -Maximum 100
```

```Output
74
56
84
46
```

```powershell
# Commands with the same seed are not random
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100 -SetSeed 23
```

```Output
74
74
74
```

```powershell
# SetSeed results in a repeatable series
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100
Get-Random -Maximum 100
Get-Random -Maximum 100
```

```Output
74
56
84
46
```

### <span data-ttu-id="fbfc9-134">Пример 10. получение случайных файлов</span><span class="sxs-lookup"><span data-stu-id="fbfc9-134">Example 10: Get random files</span></span>

<span data-ttu-id="fbfc9-135">Эти команды получают случайный выбор из файлов 50 с `C:` диска локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-135">These commands get a randomly selected sample of 50 files from the `C:` drive of the local computer.</span></span>

```powershell
$Files = Get-ChildItem -Path C:\* -Recurse
$Sample = $Files | Get-Random -Count 50
```

### <span data-ttu-id="fbfc9-136">Пример 11. пробное распределение костей</span><span class="sxs-lookup"><span data-stu-id="fbfc9-136">Example 11: Roll fair dice</span></span>

<span data-ttu-id="fbfc9-137">В этом примере выполняется откат справедливого кристалла 1200 раз и подсчитывается количество результатов.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-137">This example rolls a fair die 1200 times and counts the outcomes.</span></span> <span data-ttu-id="fbfc9-138">Первая команда `For-EachObject` повторяет вызов `Get-Random` из числа переданного (1-6).</span><span class="sxs-lookup"><span data-stu-id="fbfc9-138">The first command, `For-EachObject` repeats the call to `Get-Random` from the piped in numbers (1-6).</span></span> <span data-ttu-id="fbfc9-139">Результаты группируются по значению `Group-Object` и форматируются в виде таблицы с `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="fbfc9-139">The results are grouped by their value with `Group-Object` and formatted as a table with `Select-Object`.</span></span>

```powershell
1..1200 | ForEach-Object {
    1..6 | Get-Random
} | Group-Object | Select-Object Name,Count
```

```Output
Name Count
---- -----
1      206
2      199
3      196
4      226
5      185
6      188
```

### <span data-ttu-id="fbfc9-140">Пример 12. Использование параметра count</span><span class="sxs-lookup"><span data-stu-id="fbfc9-140">Example 12: Use the Count parameter</span></span>

<span data-ttu-id="fbfc9-141">Теперь можно использовать параметр **Count** без объектов трубопроводов в `Get-Random` .</span><span class="sxs-lookup"><span data-stu-id="fbfc9-141">You can now use the **Count** parameter without piping objects to `Get-Random`.</span></span>
<span data-ttu-id="fbfc9-142">В следующем примере возвращается три случайных числа, меньшие 10.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-142">The following example gets three random numbers less than 10.</span></span>

```powershell
Get-Random -Count 3 -Maximum 10
```

```Output
9
0
8
```

### <span data-ttu-id="fbfc9-143">Пример 13. Использование параметра InputObject с пустой строкой или $null</span><span class="sxs-lookup"><span data-stu-id="fbfc9-143">Example 13: Use the InputObject parameter with an empty string or $null</span></span>

<span data-ttu-id="fbfc9-144">В этом примере параметр **InputObject** задает массив, содержащий пустую строку ( `''` ) и `$null` .</span><span class="sxs-lookup"><span data-stu-id="fbfc9-144">In this example, the **InputObject** parameter specifies an array that contains an empty string (`''`) and `$null`.</span></span>

```powershell
Get-Random -InputObject @('a','',$null)
```

<span data-ttu-id="fbfc9-145">`Get-Random` возвратит либо `a` пустую строку, либо `$null` .</span><span class="sxs-lookup"><span data-stu-id="fbfc9-145">`Get-Random` will return either `a`, empty string, or `$null`.</span></span> <span data-ttu-id="fbfc9-146">Пустой проверочного отображается в виде пустой строки и `$null` возвращается в командную строку PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-146">The empty sting displays as a blank line and `$null` returns to a PowerShell prompt.</span></span>

## <span data-ttu-id="fbfc9-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fbfc9-147">PARAMETERS</span></span>

### <span data-ttu-id="fbfc9-148">— Количество</span><span class="sxs-lookup"><span data-stu-id="fbfc9-148">-Count</span></span>

<span data-ttu-id="fbfc9-149">Указывает число возвращаемых случайных объектов или чисел.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-149">Specifies the number of random objects or numbers to return.</span></span> <span data-ttu-id="fbfc9-150">Значение по умолчанию — 1.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-150">The default is 1.</span></span>

<span data-ttu-id="fbfc9-151">При использовании с параметром `InputObject` , если значение **счетчика** превышает количество объектов в коллекции, `Get-Random` возвращает все объекты в случайном порядке.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-151">When used with `InputObject`, if the value of **Count** exceeds the number of objects in the collection, `Get-Random` returns all of the objects in random order.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbfc9-152">-InputObject</span><span class="sxs-lookup"><span data-stu-id="fbfc9-152">-InputObject</span></span>

<span data-ttu-id="fbfc9-153">Определяет коллекцию объектов.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-153">Specifies a collection of objects.</span></span> <span data-ttu-id="fbfc9-154">`Get-Random` Возвращает случайно выбранные объекты в случайном порядке из коллекции до числа, указанного параметром **Count**.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-154">`Get-Random` gets randomly selected objects in random order from the collection up to the number specified by **Count**.</span></span> <span data-ttu-id="fbfc9-155">Введите объекты, переменную, содержащую объекты, либо получающую их команду или выражение.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-155">Enter the objects, a variable that contains the objects, or a command or expression that gets the objects.</span></span> <span data-ttu-id="fbfc9-156">Можно также передать коллекцию объектов в `Get-Random` .</span><span class="sxs-lookup"><span data-stu-id="fbfc9-156">You can also pipe a collection of objects to `Get-Random`.</span></span>

<span data-ttu-id="fbfc9-157">Начиная с PowerShell 7, параметр **InputObject** принимает массивы, которые могут содержать пустую строку или `$null` .</span><span class="sxs-lookup"><span data-stu-id="fbfc9-157">Beginning in PowerShell 7, the **InputObject** parameter accepts arrays that can contain an empty string or `$null`.</span></span> <span data-ttu-id="fbfc9-158">Массив можно отправить вниз по конвейеру или в качестве значения параметра **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="fbfc9-158">The array can be sent down the pipeline or as an **InputObject** parameter value.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: RandomListItemParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="fbfc9-159">— Максимум</span><span class="sxs-lookup"><span data-stu-id="fbfc9-159">-Maximum</span></span>

<span data-ttu-id="fbfc9-160">Определяет максимальное значение случайного числа.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-160">Specifies a maximum value for the random number.</span></span> <span data-ttu-id="fbfc9-161">`Get-Random` Возвращает значение, которое меньше максимального (не равно).</span><span class="sxs-lookup"><span data-stu-id="fbfc9-161">`Get-Random` returns a value that is less than the maximum (not equal).</span></span> <span data-ttu-id="fbfc9-162">Введите целое число, число двойной точности с плавающей запятой или объект, который можно преобразовать в целое число или Double, например числовую строку ("100").</span><span class="sxs-lookup"><span data-stu-id="fbfc9-162">Enter an integer, a double-precision floating-point number, or an object that can be converted to an integer or double, such as a numeric string ("100").</span></span>

<span data-ttu-id="fbfc9-163">Значение **Maximum** должно быть больше (не равно) значения **Minimum**.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-163">The value of **Maximum** must be greater than (not equal to) the value of **Minimum**.</span></span> <span data-ttu-id="fbfc9-164">Если значение параметра **Maximum** или **Minimum** является числом с плавающей запятой, `Get-Random` возвращает случайное выбранное число с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-164">If the value of **Maximum** or **Minimum** is a floating-point number, `Get-Random` returns a randomly selected floating-point number.</span></span>

<span data-ttu-id="fbfc9-165">На 64-разрядном компьютере, если значение **минимума** является 32-битным целым числом, значение по умолчанию **Maximum** равно **Int32. MaxValue**.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-165">On a 64-bit computer, if the value of **Minimum** is a 32-bit integer, the default value of **Maximum** is **Int32.MaxValue**.</span></span>

<span data-ttu-id="fbfc9-166">Если **минимальное** значение равно Double (число с плавающей запятой), значение по умолчанию **Maximum** равно **Double. MaxValue**.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-166">If the value of **Minimum** is a double (a floating-point number), the default value of **Maximum** is **Double.MaxValue**.</span></span> <span data-ttu-id="fbfc9-167">В противном случае значение по умолчанию — **Int32. MaxValue**.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-167">Otherwise, the default value is **Int32.MaxValue**.</span></span>

```yaml
Type: System.Object
Parameter Sets: RandomNumberParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbfc9-168">— Минимум</span><span class="sxs-lookup"><span data-stu-id="fbfc9-168">-Minimum</span></span>

<span data-ttu-id="fbfc9-169">Определяет минимальное значение случайного числа.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-169">Specifies a minimum value for the random number.</span></span> <span data-ttu-id="fbfc9-170">Введите целое число, число двойной точности с плавающей запятой или объект, который можно преобразовать в целое число или Double, например числовую строку ("100").</span><span class="sxs-lookup"><span data-stu-id="fbfc9-170">Enter an integer, a double-precision floating-point number, or an object that can be converted to an integer or double, such as a numeric string ("100").</span></span> <span data-ttu-id="fbfc9-171">Значение по умолчанию — 0 (нуль).</span><span class="sxs-lookup"><span data-stu-id="fbfc9-171">The default value is 0 (zero).</span></span>

<span data-ttu-id="fbfc9-172">Значение **Minimum** должно быть меньше значения **Maximum**.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-172">The value of **Minimum** must be less than (not equal to) the value of **Maximum**.</span></span> <span data-ttu-id="fbfc9-173">Если значение параметра **Maximum** или **Minimum** является числом с плавающей запятой, `Get-Random` возвращает случайное выбранное число с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-173">If the value of **Maximum** or **Minimum** is a floating-point number, `Get-Random` returns a randomly selected floating-point number.</span></span>

```yaml
Type: System.Object
Parameter Sets: RandomNumberParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbfc9-174">-SetSeed</span><span class="sxs-lookup"><span data-stu-id="fbfc9-174">-SetSeed</span></span>

<span data-ttu-id="fbfc9-175">Определяет начальное значение случайного числа.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-175">Specifies a seed value for the random number generator.</span></span> <span data-ttu-id="fbfc9-176">Это начальное значение используется для текущей команды и для всех последующих `Get-Random` команд в текущем сеансе до повторного использования **SetSeed** или закрытия сеанса.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-176">This seed value is used for the current command and for all subsequent `Get-Random` commands in the current session until you use **SetSeed** again or close the session.</span></span> <span data-ttu-id="fbfc9-177">Нельзя сбросить начальное значение до значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-177">You can't reset the seed to its default value.</span></span>

<span data-ttu-id="fbfc9-178">Параметр **SetSeed** не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-178">The **SetSeed** parameter is not required.</span></span> <span data-ttu-id="fbfc9-179">По умолчанию `Get-Random` использует метод [рандомнумберженератор ()](/dotnet/api/system.security.cryptography.randomnumbergenerator) для создания начального значения.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-179">By default, `Get-Random` uses the [RandomNumberGenerator()](/dotnet/api/system.security.cryptography.randomnumbergenerator) method to generate a seed value.</span></span> <span data-ttu-id="fbfc9-180">Поскольку **SetSeed** приводит к неслучайному поведению, оно обычно используется только при попытке воспроизведения поведения, например при отладке или анализе скрипта, содержащего `Get-Random` команды.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-180">Because **SetSeed** results in non-random behavior, it's typically used only when trying to reproduce behavior, such as when debugging or analyzing a script that includes `Get-Random` commands.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbfc9-181">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="fbfc9-181">CommonParameters</span></span>

<span data-ttu-id="fbfc9-182">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-182">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fbfc9-183">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fbfc9-183">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fbfc9-184">Входные данные</span><span class="sxs-lookup"><span data-stu-id="fbfc9-184">INPUTS</span></span>

### <span data-ttu-id="fbfc9-185">System.Object</span><span class="sxs-lookup"><span data-stu-id="fbfc9-185">System.Object</span></span>

<span data-ttu-id="fbfc9-186">Один или несколько объектов можно передать по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-186">You can pipe one or more objects.</span></span> <span data-ttu-id="fbfc9-187">`Get-Random` выбирает значения случайным образом из перенаправленных объектов.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-187">`Get-Random` selects values randomly from the piped objects.</span></span>

## <span data-ttu-id="fbfc9-188">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="fbfc9-188">OUTPUTS</span></span>

### <span data-ttu-id="fbfc9-189">System. Int32, System. Int64, System. Double</span><span class="sxs-lookup"><span data-stu-id="fbfc9-189">System.Int32, System.Int64, System.Double</span></span>

<span data-ttu-id="fbfc9-190">`Get-Random` Возвращает целое число с плавающей запятой или объект, выбранный случайным образом из отправленной коллекции.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-190">`Get-Random` returns an integer or floating-point number, or an object selected randomly from a submitted collection.</span></span>

## <span data-ttu-id="fbfc9-191">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="fbfc9-191">NOTES</span></span>

<span data-ttu-id="fbfc9-192">`Get-Random` Задает начальное значение по умолчанию для каждого сеанса на основе системного времени, в течение которого начинается сеанс.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-192">`Get-Random` sets a default seed for each session based on the system time clock when the session starts.</span></span>

<span data-ttu-id="fbfc9-193">`Get-Random` не всегда возвращает тот же тип данных, что и входное значение.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-193">`Get-Random` does not alway return the same data type as the input value.</span></span> <span data-ttu-id="fbfc9-194">В следующей таблице показан тип выходных данных для каждого числового типа входных данных.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-194">The following table shows the output type for each of the numeric input types.</span></span>

| <span data-ttu-id="fbfc9-195">Тип входных данных</span><span class="sxs-lookup"><span data-stu-id="fbfc9-195">Input Type</span></span> | <span data-ttu-id="fbfc9-196">Тип выходных данных</span><span class="sxs-lookup"><span data-stu-id="fbfc9-196">Output Type</span></span> |
| :--------: | :---------: |
|   <span data-ttu-id="fbfc9-197">SByte</span><span class="sxs-lookup"><span data-stu-id="fbfc9-197">SByte</span></span>    |   <span data-ttu-id="fbfc9-198">Double</span><span class="sxs-lookup"><span data-stu-id="fbfc9-198">Double</span></span>    |
|    <span data-ttu-id="fbfc9-199">Byte</span><span class="sxs-lookup"><span data-stu-id="fbfc9-199">Byte</span></span>    |   <span data-ttu-id="fbfc9-200">Double</span><span class="sxs-lookup"><span data-stu-id="fbfc9-200">Double</span></span>    |
|   <span data-ttu-id="fbfc9-201">Int16</span><span class="sxs-lookup"><span data-stu-id="fbfc9-201">Int16</span></span>    |   <span data-ttu-id="fbfc9-202">Double</span><span class="sxs-lookup"><span data-stu-id="fbfc9-202">Double</span></span>    |
|   <span data-ttu-id="fbfc9-203">UInt16</span><span class="sxs-lookup"><span data-stu-id="fbfc9-203">UInt16</span></span>   |   <span data-ttu-id="fbfc9-204">Double</span><span class="sxs-lookup"><span data-stu-id="fbfc9-204">Double</span></span>    |
|   <span data-ttu-id="fbfc9-205">Int32</span><span class="sxs-lookup"><span data-stu-id="fbfc9-205">Int32</span></span>    |    <span data-ttu-id="fbfc9-206">Int32</span><span class="sxs-lookup"><span data-stu-id="fbfc9-206">Int32</span></span>    |
|   <span data-ttu-id="fbfc9-207">UInt32</span><span class="sxs-lookup"><span data-stu-id="fbfc9-207">UInt32</span></span>   |   <span data-ttu-id="fbfc9-208">Double</span><span class="sxs-lookup"><span data-stu-id="fbfc9-208">Double</span></span>    |
|   <span data-ttu-id="fbfc9-209">Int64</span><span class="sxs-lookup"><span data-stu-id="fbfc9-209">Int64</span></span>    |    <span data-ttu-id="fbfc9-210">Int64</span><span class="sxs-lookup"><span data-stu-id="fbfc9-210">Int64</span></span>    |
|   <span data-ttu-id="fbfc9-211">UInt64</span><span class="sxs-lookup"><span data-stu-id="fbfc9-211">UInt64</span></span>   |   <span data-ttu-id="fbfc9-212">Double</span><span class="sxs-lookup"><span data-stu-id="fbfc9-212">Double</span></span>    |
|   <span data-ttu-id="fbfc9-213">Double</span><span class="sxs-lookup"><span data-stu-id="fbfc9-213">Double</span></span>   |   <span data-ttu-id="fbfc9-214">Double</span><span class="sxs-lookup"><span data-stu-id="fbfc9-214">Double</span></span>    |
|   <span data-ttu-id="fbfc9-215">Single</span><span class="sxs-lookup"><span data-stu-id="fbfc9-215">Single</span></span>   |   <span data-ttu-id="fbfc9-216">Double</span><span class="sxs-lookup"><span data-stu-id="fbfc9-216">Double</span></span>    |

<span data-ttu-id="fbfc9-217">Начиная с Windows PowerShell 3,0, `Get-Random` поддерживает 64-разрядные целые числа.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-217">Beginning in Windows PowerShell 3.0, `Get-Random` supports 64-bit integers.</span></span> <span data-ttu-id="fbfc9-218">В Windows PowerShell 2,0 все значения приводятся к типу **System. Int32**.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-218">In Windows PowerShell 2.0, all values are cast to **System.Int32**.</span></span>

<span data-ttu-id="fbfc9-219">Начиная с PowerShell 7, параметр **InputObject** в наборе параметров **рандомлиститемпараметерсет** принимает массивы, содержащие пустую строку или `$null` .</span><span class="sxs-lookup"><span data-stu-id="fbfc9-219">Beginning in PowerShell 7, the **InputObject** parameter in the **RandomListItemParameterSet** parameter set accepts arrays that contain an empty string or `$null`.</span></span> <span data-ttu-id="fbfc9-220">В более ранних версиях PowerShell только параметр **Maximum** в наборе параметров **рандомнумберпараметерсет** принимает пустую строку или `$null` .</span><span class="sxs-lookup"><span data-stu-id="fbfc9-220">In earlier PowerShell versions, only the **Maximum** parameter in the **RandomNumberParameterSet** parameter set accepted an empty string or `$null`.</span></span>

## <span data-ttu-id="fbfc9-221">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="fbfc9-221">RELATED LINKS</span></span>
