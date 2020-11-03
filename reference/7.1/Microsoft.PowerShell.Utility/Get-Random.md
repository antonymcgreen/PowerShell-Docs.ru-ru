---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/20/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-random?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Random
ms.openlocfilehash: 644663c8871233bae84288f83492b518405d14ff
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227182"
---
# <span data-ttu-id="17155-103">Get-Random</span><span class="sxs-lookup"><span data-stu-id="17155-103">Get-Random</span></span>

## <span data-ttu-id="17155-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="17155-104">SYNOPSIS</span></span>
<span data-ttu-id="17155-105">Возвращает случайное число или случайным образом выбирает объекты из коллекции.</span><span class="sxs-lookup"><span data-stu-id="17155-105">Gets a random number, or selects objects randomly from a collection.</span></span>

## <span data-ttu-id="17155-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="17155-106">SYNTAX</span></span>

### <span data-ttu-id="17155-107">Рандомнумберпараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="17155-107">RandomNumberParameterSet (Default)</span></span>

```
Get-Random [-SetSeed <Int32>] [[-Maximum] <Object>] [-Minimum <Object>] [-Count <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="17155-108">рандомлиститемпараметерсет</span><span class="sxs-lookup"><span data-stu-id="17155-108">RandomListItemParameterSet</span></span>

```
Get-Random [-SetSeed <Int32>] [-InputObject] <Object[]> [-Count <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="17155-109">шуффлепараметерсет</span><span class="sxs-lookup"><span data-stu-id="17155-109">ShuffleParameterSet</span></span>

```
Get-Random [-SetSeed <Int32>] [-InputObject] <Object[]> [-Shuffle] [<CommonParameters>]
```

## <span data-ttu-id="17155-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="17155-110">DESCRIPTION</span></span>

<span data-ttu-id="17155-111">`Get-Random`Командлет возвращает число, выбранное случайным образом.</span><span class="sxs-lookup"><span data-stu-id="17155-111">The `Get-Random` cmdlet gets a randomly selected number.</span></span> <span data-ttu-id="17155-112">При отправке коллекции объектов в `Get-Random` она получает один или несколько случайно выбранных объектов из коллекции.</span><span class="sxs-lookup"><span data-stu-id="17155-112">If you submit a collection of objects to `Get-Random`, it gets one or more randomly selected objects from the collection.</span></span>

<span data-ttu-id="17155-113">Без параметров или входных данных `Get-Random` команда возвращает случайное выбранное 32-разрядное целое число без знака в диапазоне от 0 (ноль) до **Int32. MaxValue** ( `0x7FFFFFFF` , `2,147,483,647` ).</span><span class="sxs-lookup"><span data-stu-id="17155-113">Without parameters or input, a `Get-Random` command returns a randomly selected 32-bit unsigned integer between 0 (zero) and **Int32.MaxValue** (`0x7FFFFFFF`, `2,147,483,647`).</span></span>

<span data-ttu-id="17155-114">Можно использовать параметры `Get-Random` , чтобы указать начальное значение, минимальное и максимальное значения, количество объектов, возвращаемых из отправленной коллекции, и всю коллекцию в случайном порядке.</span><span class="sxs-lookup"><span data-stu-id="17155-114">You can use the parameters of `Get-Random` to specify a seed number, minimum and maximum values, the number of objects returned from a submitted collection, and the entire collection in a random order.</span></span>

## <span data-ttu-id="17155-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="17155-115">EXAMPLES</span></span>

### <span data-ttu-id="17155-116">Пример 1. получение случайного целого числа</span><span class="sxs-lookup"><span data-stu-id="17155-116">Example 1: Get a random integer</span></span>

<span data-ttu-id="17155-117">Эта команда возвращает случайное целое число от 0 (0) до **Int32. MaxValue**.</span><span class="sxs-lookup"><span data-stu-id="17155-117">This command gets a random integer between 0 (zero) and **Int32.MaxValue**.</span></span>

```powershell
Get-Random
```

```Output
3951433
```

### <span data-ttu-id="17155-118">Пример 2. получение случайного целого числа от 0 до 99</span><span class="sxs-lookup"><span data-stu-id="17155-118">Example 2: Get a random integer between 0 and 99</span></span>

```powershell
Get-Random -Maximum 100
```

```Output
47
```

### <span data-ttu-id="17155-119">Пример 3. получение случайного целого числа от-100 до 99</span><span class="sxs-lookup"><span data-stu-id="17155-119">Example 3: Get a random integer between -100 and 99</span></span>

```powershell
Get-Random -Minimum -100 -Maximum 100
```

```Output
56
```

### <span data-ttu-id="17155-120">Пример 4. получение случайного числа с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="17155-120">Example 4: Get a random floating-point number</span></span>

<span data-ttu-id="17155-121">Эта команда возвращает случайное число с плавающей запятой, которое больше или равно 10,7 и меньше 20,92.</span><span class="sxs-lookup"><span data-stu-id="17155-121">This command gets a random floating-point number greater than or equal to 10.7 and less than 20.92.</span></span>

```powershell
Get-Random -Minimum 10.7 -Maximum 20.93
```

```Output
18.08467273887
```

### <span data-ttu-id="17155-122">Пример 5. получение случайного целого числа из массива</span><span class="sxs-lookup"><span data-stu-id="17155-122">Example 5: Get a random integer from an array</span></span>

<span data-ttu-id="17155-123">Эта команда возвращает случайное число из указанного массива.</span><span class="sxs-lookup"><span data-stu-id="17155-123">This command gets a randomly selected number from the specified array.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random
```

```Output
8
```

### <span data-ttu-id="17155-124">Пример 6. получение нескольких случайных целых чисел из массива</span><span class="sxs-lookup"><span data-stu-id="17155-124">Example 6: Get several random integers from an array</span></span>

<span data-ttu-id="17155-125">Эта команда получает три случайно выбранных числа в случайном порядке из массива.</span><span class="sxs-lookup"><span data-stu-id="17155-125">This command gets three randomly selected numbers in random order from an array.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random -Count 3
```

```Output
3
1
13
```

### <span data-ttu-id="17155-126">Пример 7. случайный выбор всей коллекции</span><span class="sxs-lookup"><span data-stu-id="17155-126">Example 7: Randomize an entire collection</span></span>

<span data-ttu-id="17155-127">Начиная с PowerShell 7,1 можно использовать параметр " **случайный** ", чтобы вернуть всю коллекцию в случайном порядке.</span><span class="sxs-lookup"><span data-stu-id="17155-127">Starting in PowerShell 7.1, you can use the **Shuffle** parameter to return the entire collection in a random order.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random -Shuffle
```

```Output
2
3
5
1
8
13
```

### <span data-ttu-id="17155-128">Пример 8. получение случайного нечислового значения</span><span class="sxs-lookup"><span data-stu-id="17155-128">Example 8: Get a random non-numeric value</span></span>

<span data-ttu-id="17155-129">Эта команда возвращает случайное значение из коллекции, элементы которой не являются числами.</span><span class="sxs-lookup"><span data-stu-id="17155-129">This command returns a random value from a non-numeric collection.</span></span>

```powershell
"red", "yellow", "blue" | Get-Random
```

```Output
yellow
```

### <span data-ttu-id="17155-130">Пример 9. Использование параметра SetSeed</span><span class="sxs-lookup"><span data-stu-id="17155-130">Example 9: Use the SetSeed parameter</span></span>

<span data-ttu-id="17155-131">В этом примере показан результат применения параметра **SetSeed**.</span><span class="sxs-lookup"><span data-stu-id="17155-131">This example shows the effect of using the **SetSeed** parameter.</span></span>

<span data-ttu-id="17155-132">Поскольку **SetSeed** создает неслучайное поведение, он обычно используется только для воспроизведения результатов, например при отладке или анализе скрипта.</span><span class="sxs-lookup"><span data-stu-id="17155-132">Because **SetSeed** produces non-random behavior, it's typically used only to reproduce results, such as when debugging or analyzing a script.</span></span>

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

### <span data-ttu-id="17155-133">Пример 10. получение случайных файлов</span><span class="sxs-lookup"><span data-stu-id="17155-133">Example 10: Get random files</span></span>

<span data-ttu-id="17155-134">Эти команды получают случайный выбор из файлов 50 с `C:` диска локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="17155-134">These commands get a randomly selected sample of 50 files from the `C:` drive of the local computer.</span></span>

```powershell
$Files = Get-ChildItem -Path C:\* -Recurse
$Sample = $Files | Get-Random -Count 50
```

### <span data-ttu-id="17155-135">Пример 11. пробное распределение костей</span><span class="sxs-lookup"><span data-stu-id="17155-135">Example 11: Roll fair dice</span></span>

<span data-ttu-id="17155-136">В этом примере выполняется откат справедливого кристалла 1200 раз и подсчитывается количество результатов.</span><span class="sxs-lookup"><span data-stu-id="17155-136">This example rolls a fair die 1200 times and counts the outcomes.</span></span> <span data-ttu-id="17155-137">Первая команда `For-EachObject` повторяет вызов `Get-Random` из числа переданного (1-6).</span><span class="sxs-lookup"><span data-stu-id="17155-137">The first command, `For-EachObject` repeats the call to `Get-Random` from the piped in numbers (1-6).</span></span> <span data-ttu-id="17155-138">Результаты группируются по значению `Group-Object` и форматируются в виде таблицы с `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="17155-138">The results are grouped by their value with `Group-Object` and formatted as a table with `Select-Object`.</span></span>

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

### <span data-ttu-id="17155-139">Пример 12. Использование параметра count</span><span class="sxs-lookup"><span data-stu-id="17155-139">Example 12: Use the Count parameter</span></span>

<span data-ttu-id="17155-140">Теперь можно использовать параметр **Count** без объектов трубопроводов в `Get-Random` .</span><span class="sxs-lookup"><span data-stu-id="17155-140">You can now use the **Count** parameter without piping objects to `Get-Random`.</span></span>
<span data-ttu-id="17155-141">В следующем примере возвращается три случайных числа, меньшие 10.</span><span class="sxs-lookup"><span data-stu-id="17155-141">The following example gets three random numbers less than 10.</span></span>

```powershell
Get-Random -Count 3 -Maximum 10
```

```Output
9
0
8
```

### <span data-ttu-id="17155-142">Пример 13. Использование параметра InputObject с пустой строкой или $null</span><span class="sxs-lookup"><span data-stu-id="17155-142">Example 13: Use the InputObject parameter with an empty string or $null</span></span>

<span data-ttu-id="17155-143">В этом примере параметр **InputObject** задает массив, содержащий пустую строку ( `''` ) и `$null` .</span><span class="sxs-lookup"><span data-stu-id="17155-143">In this example, the **InputObject** parameter specifies an array that contains an empty string (`''`) and `$null`.</span></span>

```powershell
Get-Random -InputObject @('a','',$null)
```

<span data-ttu-id="17155-144">`Get-Random` возвратит либо `a` пустую строку, либо `$null` .</span><span class="sxs-lookup"><span data-stu-id="17155-144">`Get-Random` will return either `a`, empty string, or `$null`.</span></span> <span data-ttu-id="17155-145">Пустой проверочного отображается в виде пустой строки и `$null` возвращается в командную строку PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17155-145">The empty sting displays as a blank line and `$null` returns to a PowerShell prompt.</span></span>

## <span data-ttu-id="17155-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="17155-146">PARAMETERS</span></span>

### <span data-ttu-id="17155-147">— Количество</span><span class="sxs-lookup"><span data-stu-id="17155-147">-Count</span></span>

<span data-ttu-id="17155-148">Указывает число возвращаемых случайных объектов или чисел.</span><span class="sxs-lookup"><span data-stu-id="17155-148">Specifies the number of random objects or numbers to return.</span></span> <span data-ttu-id="17155-149">Значение по умолчанию — 1.</span><span class="sxs-lookup"><span data-stu-id="17155-149">The default is 1.</span></span>

<span data-ttu-id="17155-150">При использовании с параметром `InputObject` , если значение **счетчика** превышает количество объектов в коллекции, `Get-Random` возвращает все объекты в случайном порядке.</span><span class="sxs-lookup"><span data-stu-id="17155-150">When used with `InputObject`, if the value of **Count** exceeds the number of objects in the collection, `Get-Random` returns all of the objects in random order.</span></span>

```yaml
Type: System.Int32
Parameter Sets: RandomNumberParameterSet, RandomListItemParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="17155-151">-InputObject</span><span class="sxs-lookup"><span data-stu-id="17155-151">-InputObject</span></span>

<span data-ttu-id="17155-152">Определяет коллекцию объектов.</span><span class="sxs-lookup"><span data-stu-id="17155-152">Specifies a collection of objects.</span></span> <span data-ttu-id="17155-153">`Get-Random` Возвращает случайно выбранные объекты в случайном порядке из коллекции до числа, указанного параметром **Count**.</span><span class="sxs-lookup"><span data-stu-id="17155-153">`Get-Random` gets randomly selected objects in random order from the collection up to the number specified by **Count**.</span></span> <span data-ttu-id="17155-154">Введите объекты, переменную, содержащую объекты, либо получающую их команду или выражение.</span><span class="sxs-lookup"><span data-stu-id="17155-154">Enter the objects, a variable that contains the objects, or a command or expression that gets the objects.</span></span> <span data-ttu-id="17155-155">Можно также передать коллекцию объектов в `Get-Random` .</span><span class="sxs-lookup"><span data-stu-id="17155-155">You can also pipe a collection of objects to `Get-Random`.</span></span>

<span data-ttu-id="17155-156">Начиная с PowerShell 7, параметр **InputObject** принимает массивы, которые могут содержать пустую строку или `$null` .</span><span class="sxs-lookup"><span data-stu-id="17155-156">Beginning in PowerShell 7, the **InputObject** parameter accepts arrays that can contain an empty string or `$null`.</span></span> <span data-ttu-id="17155-157">Массив можно отправить вниз по конвейеру или в качестве значения параметра **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="17155-157">The array can be sent down the pipeline or as an **InputObject** parameter value.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: RandomListItemParameterSet, ShuffleParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="17155-158">— Максимум</span><span class="sxs-lookup"><span data-stu-id="17155-158">-Maximum</span></span>

<span data-ttu-id="17155-159">Определяет максимальное значение случайного числа.</span><span class="sxs-lookup"><span data-stu-id="17155-159">Specifies a maximum value for the random number.</span></span> <span data-ttu-id="17155-160">`Get-Random` Возвращает значение, которое меньше максимального (не равно).</span><span class="sxs-lookup"><span data-stu-id="17155-160">`Get-Random` returns a value that is less than the maximum (not equal).</span></span> <span data-ttu-id="17155-161">Введите целое число, число двойной точности с плавающей запятой или объект, который можно преобразовать в целое число или Double, например числовую строку ("100").</span><span class="sxs-lookup"><span data-stu-id="17155-161">Enter an integer, a double-precision floating-point number, or an object that can be converted to an integer or double, such as a numeric string ("100").</span></span>

<span data-ttu-id="17155-162">Значение **Maximum** должно быть больше (не равно) значения **Minimum**.</span><span class="sxs-lookup"><span data-stu-id="17155-162">The value of **Maximum** must be greater than (not equal to) the value of **Minimum**.</span></span> <span data-ttu-id="17155-163">Если значение параметра **Maximum** или **Minimum** является числом с плавающей запятой, `Get-Random` возвращает случайное выбранное число с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="17155-163">If the value of **Maximum** or **Minimum** is a floating-point number, `Get-Random` returns a randomly selected floating-point number.</span></span>

<span data-ttu-id="17155-164">На 64-разрядном компьютере, если значение **минимума** является 32-битным целым числом, значение по умолчанию **Maximum** равно **Int32. MaxValue**.</span><span class="sxs-lookup"><span data-stu-id="17155-164">On a 64-bit computer, if the value of **Minimum** is a 32-bit integer, the default value of **Maximum** is **Int32.MaxValue**.</span></span>

<span data-ttu-id="17155-165">Если **минимальное** значение равно Double (число с плавающей запятой), значение по умолчанию **Maximum** равно **Double. MaxValue**.</span><span class="sxs-lookup"><span data-stu-id="17155-165">If the value of **Minimum** is a double (a floating-point number), the default value of **Maximum** is **Double.MaxValue**.</span></span> <span data-ttu-id="17155-166">В противном случае значение по умолчанию — **Int32. MaxValue**.</span><span class="sxs-lookup"><span data-stu-id="17155-166">Otherwise, the default value is **Int32.MaxValue**.</span></span>

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

### <span data-ttu-id="17155-167">— Минимум</span><span class="sxs-lookup"><span data-stu-id="17155-167">-Minimum</span></span>

<span data-ttu-id="17155-168">Определяет минимальное значение случайного числа.</span><span class="sxs-lookup"><span data-stu-id="17155-168">Specifies a minimum value for the random number.</span></span> <span data-ttu-id="17155-169">Введите целое число, число двойной точности с плавающей запятой или объект, который можно преобразовать в целое число или Double, например числовую строку ("100").</span><span class="sxs-lookup"><span data-stu-id="17155-169">Enter an integer, a double-precision floating-point number, or an object that can be converted to an integer or double, such as a numeric string ("100").</span></span> <span data-ttu-id="17155-170">Значение по умолчанию — 0 (нуль).</span><span class="sxs-lookup"><span data-stu-id="17155-170">The default value is 0 (zero).</span></span>

<span data-ttu-id="17155-171">Значение **Minimum** должно быть меньше значения **Maximum**.</span><span class="sxs-lookup"><span data-stu-id="17155-171">The value of **Minimum** must be less than (not equal to) the value of **Maximum**.</span></span> <span data-ttu-id="17155-172">Если значение параметра **Maximum** или **Minimum** является числом с плавающей запятой, `Get-Random` возвращает случайное выбранное число с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="17155-172">If the value of **Maximum** or **Minimum** is a floating-point number, `Get-Random` returns a randomly selected floating-point number.</span></span>

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

### <span data-ttu-id="17155-173">-SetSeed</span><span class="sxs-lookup"><span data-stu-id="17155-173">-SetSeed</span></span>

<span data-ttu-id="17155-174">Определяет начальное значение случайного числа.</span><span class="sxs-lookup"><span data-stu-id="17155-174">Specifies a seed value for the random number generator.</span></span> <span data-ttu-id="17155-175">Это начальное значение используется для текущей команды и для всех последующих `Get-Random` команд в текущем сеансе до повторного использования **SetSeed** или закрытия сеанса.</span><span class="sxs-lookup"><span data-stu-id="17155-175">This seed value is used for the current command and for all subsequent `Get-Random` commands in the current session until you use **SetSeed** again or close the session.</span></span> <span data-ttu-id="17155-176">Нельзя сбросить начальное значение до значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="17155-176">You can't reset the seed to its default value.</span></span>

<span data-ttu-id="17155-177">Параметр **SetSeed** не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="17155-177">The **SetSeed** parameter is not required.</span></span> <span data-ttu-id="17155-178">По умолчанию `Get-Random` использует метод [рандомнумберженератор ()](/dotnet/api/system.security.cryptography.randomnumbergenerator) для создания начального значения.</span><span class="sxs-lookup"><span data-stu-id="17155-178">By default, `Get-Random` uses the [RandomNumberGenerator()](/dotnet/api/system.security.cryptography.randomnumbergenerator) method to generate a seed value.</span></span> <span data-ttu-id="17155-179">Поскольку **SetSeed** приводит к неслучайному поведению, оно обычно используется только при попытке воспроизведения поведения, например при отладке или анализе скрипта, содержащего `Get-Random` команды.</span><span class="sxs-lookup"><span data-stu-id="17155-179">Because **SetSeed** results in non-random behavior, it's typically used only when trying to reproduce behavior, such as when debugging or analyzing a script that includes `Get-Random` commands.</span></span>

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

### <span data-ttu-id="17155-180">— В случайном порядке</span><span class="sxs-lookup"><span data-stu-id="17155-180">-Shuffle</span></span>

<span data-ttu-id="17155-181">Возвращает всю коллекцию в случайном порядке.</span><span class="sxs-lookup"><span data-stu-id="17155-181">Returns the entire collection in a randomized order.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ShuffleParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="17155-182">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="17155-182">CommonParameters</span></span>

<span data-ttu-id="17155-183">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="17155-183">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="17155-184">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="17155-184">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="17155-185">Входные данные</span><span class="sxs-lookup"><span data-stu-id="17155-185">INPUTS</span></span>

### <span data-ttu-id="17155-186">System.Object</span><span class="sxs-lookup"><span data-stu-id="17155-186">System.Object</span></span>

<span data-ttu-id="17155-187">Один или несколько объектов можно передать по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="17155-187">You can pipe one or more objects.</span></span> <span data-ttu-id="17155-188">`Get-Random` выбирает значения случайным образом из перенаправленных объектов.</span><span class="sxs-lookup"><span data-stu-id="17155-188">`Get-Random` selects values randomly from the piped objects.</span></span>

## <span data-ttu-id="17155-189">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="17155-189">OUTPUTS</span></span>

### <span data-ttu-id="17155-190">System. Int32, System. Int64, System. Double</span><span class="sxs-lookup"><span data-stu-id="17155-190">System.Int32, System.Int64, System.Double</span></span>

<span data-ttu-id="17155-191">`Get-Random` Возвращает целое число с плавающей запятой или объект, выбранный случайным образом из отправленной коллекции.</span><span class="sxs-lookup"><span data-stu-id="17155-191">`Get-Random` returns an integer or floating-point number, or an object selected randomly from a submitted collection.</span></span>

## <span data-ttu-id="17155-192">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="17155-192">NOTES</span></span>

<span data-ttu-id="17155-193">`Get-Random` Задает начальное значение по умолчанию для каждого сеанса на основе системного времени, в течение которого начинается сеанс.</span><span class="sxs-lookup"><span data-stu-id="17155-193">`Get-Random` sets a default seed for each session based on the system time clock when the session starts.</span></span>

<span data-ttu-id="17155-194">`Get-Random` не всегда возвращает тот же тип данных, что и входное значение.</span><span class="sxs-lookup"><span data-stu-id="17155-194">`Get-Random` does not alway return the same data type as the input value.</span></span> <span data-ttu-id="17155-195">В следующей таблице показан тип выходных данных для каждого числового типа входных данных.</span><span class="sxs-lookup"><span data-stu-id="17155-195">The following table shows the output type for each of the numeric input types.</span></span>

| <span data-ttu-id="17155-196">Тип входных данных</span><span class="sxs-lookup"><span data-stu-id="17155-196">Input Type</span></span> | <span data-ttu-id="17155-197">Тип выходных данных</span><span class="sxs-lookup"><span data-stu-id="17155-197">Output Type</span></span> |
| :--------: | :---------: |
|   <span data-ttu-id="17155-198">SByte</span><span class="sxs-lookup"><span data-stu-id="17155-198">SByte</span></span>    |   <span data-ttu-id="17155-199">Double</span><span class="sxs-lookup"><span data-stu-id="17155-199">Double</span></span>    |
|    <span data-ttu-id="17155-200">Byte</span><span class="sxs-lookup"><span data-stu-id="17155-200">Byte</span></span>    |   <span data-ttu-id="17155-201">Double</span><span class="sxs-lookup"><span data-stu-id="17155-201">Double</span></span>    |
|   <span data-ttu-id="17155-202">Int16</span><span class="sxs-lookup"><span data-stu-id="17155-202">Int16</span></span>    |   <span data-ttu-id="17155-203">Double</span><span class="sxs-lookup"><span data-stu-id="17155-203">Double</span></span>    |
|   <span data-ttu-id="17155-204">UInt16</span><span class="sxs-lookup"><span data-stu-id="17155-204">UInt16</span></span>   |   <span data-ttu-id="17155-205">Double</span><span class="sxs-lookup"><span data-stu-id="17155-205">Double</span></span>    |
|   <span data-ttu-id="17155-206">Int32</span><span class="sxs-lookup"><span data-stu-id="17155-206">Int32</span></span>    |    <span data-ttu-id="17155-207">Int32</span><span class="sxs-lookup"><span data-stu-id="17155-207">Int32</span></span>    |
|   <span data-ttu-id="17155-208">UInt32</span><span class="sxs-lookup"><span data-stu-id="17155-208">UInt32</span></span>   |   <span data-ttu-id="17155-209">Double</span><span class="sxs-lookup"><span data-stu-id="17155-209">Double</span></span>    |
|   <span data-ttu-id="17155-210">Int64</span><span class="sxs-lookup"><span data-stu-id="17155-210">Int64</span></span>    |    <span data-ttu-id="17155-211">Int64</span><span class="sxs-lookup"><span data-stu-id="17155-211">Int64</span></span>    |
|   <span data-ttu-id="17155-212">UInt64</span><span class="sxs-lookup"><span data-stu-id="17155-212">UInt64</span></span>   |   <span data-ttu-id="17155-213">Double</span><span class="sxs-lookup"><span data-stu-id="17155-213">Double</span></span>    |
|   <span data-ttu-id="17155-214">Double</span><span class="sxs-lookup"><span data-stu-id="17155-214">Double</span></span>   |   <span data-ttu-id="17155-215">Double</span><span class="sxs-lookup"><span data-stu-id="17155-215">Double</span></span>    |
|   <span data-ttu-id="17155-216">Single</span><span class="sxs-lookup"><span data-stu-id="17155-216">Single</span></span>   |   <span data-ttu-id="17155-217">Double</span><span class="sxs-lookup"><span data-stu-id="17155-217">Double</span></span>    |

<span data-ttu-id="17155-218">Начиная с Windows PowerShell 3,0, `Get-Random` поддерживает 64-разрядные целые числа.</span><span class="sxs-lookup"><span data-stu-id="17155-218">Beginning in Windows PowerShell 3.0, `Get-Random` supports 64-bit integers.</span></span> <span data-ttu-id="17155-219">В Windows PowerShell 2,0 все значения приводятся к типу **System. Int32**.</span><span class="sxs-lookup"><span data-stu-id="17155-219">In Windows PowerShell 2.0, all values are cast to **System.Int32**.</span></span>

<span data-ttu-id="17155-220">Начиная с PowerShell 7, параметр **InputObject** в наборе параметров **рандомлиститемпараметерсет** принимает массивы, содержащие пустую строку или `$null` .</span><span class="sxs-lookup"><span data-stu-id="17155-220">Beginning in PowerShell 7, the **InputObject** parameter in the **RandomListItemParameterSet** parameter set accepts arrays that contain an empty string or `$null`.</span></span> <span data-ttu-id="17155-221">В более ранних версиях PowerShell только параметр **Maximum** в наборе параметров **рандомнумберпараметерсет** принимает пустую строку или `$null` .</span><span class="sxs-lookup"><span data-stu-id="17155-221">In earlier PowerShell versions, only the **Maximum** parameter in the **RandomNumberParameterSet** parameter set accepted an empty string or `$null`.</span></span>

## <span data-ttu-id="17155-222">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="17155-222">RELATED LINKS</span></span>

