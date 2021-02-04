---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 02/02/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-random?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Random
ms.openlocfilehash: 007f8f2e377af0620d439f5a35be51aace032dc1
ms.sourcegitcommit: fa1a84c81e15f1ffac962110b0b4c850c1b173a0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2021
ms.locfileid: "99496063"
---
# <span data-ttu-id="83187-102">Get-Random</span><span class="sxs-lookup"><span data-stu-id="83187-102">Get-Random</span></span>

## <span data-ttu-id="83187-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="83187-103">SYNOPSIS</span></span>
<span data-ttu-id="83187-104">Возвращает случайное число или случайным образом выбирает объекты из коллекции.</span><span class="sxs-lookup"><span data-stu-id="83187-104">Gets a random number, or selects objects randomly from a collection.</span></span>

## <span data-ttu-id="83187-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="83187-105">SYNTAX</span></span>

### <span data-ttu-id="83187-106">Рандомнумберпараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="83187-106">RandomNumberParameterSet (Default)</span></span>

```
Get-Random [-SetSeed <Int32>] [[-Maximum] <Object>] [-Minimum <Object>] [-Count <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="83187-107">рандомлиститемпараметерсет</span><span class="sxs-lookup"><span data-stu-id="83187-107">RandomListItemParameterSet</span></span>

```
Get-Random [-SetSeed <Int32>] [-InputObject] <Object[]> [-Count <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="83187-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="83187-108">DESCRIPTION</span></span>

<span data-ttu-id="83187-109">`Get-Random`Командлет возвращает число, выбранное случайным образом.</span><span class="sxs-lookup"><span data-stu-id="83187-109">The `Get-Random` cmdlet gets a randomly selected number.</span></span> <span data-ttu-id="83187-110">При отправке коллекции объектов в `Get-Random` она получает один или несколько случайно выбранных объектов из коллекции.</span><span class="sxs-lookup"><span data-stu-id="83187-110">If you submit a collection of objects to `Get-Random`, it gets one or more randomly selected objects from the collection.</span></span>

<span data-ttu-id="83187-111">Без параметров или входных данных `Get-Random` команда возвращает случайное выбранное 32-разрядное целое число без знака в диапазоне от 0 (ноль) до **Int32. MaxValue** ( `0x7FFFFFFF` , `2,147,483,647` ).</span><span class="sxs-lookup"><span data-stu-id="83187-111">Without parameters or input, a `Get-Random` command returns a randomly selected 32-bit unsigned integer between 0 (zero) and **Int32.MaxValue** (`0x7FFFFFFF`, `2,147,483,647`).</span></span>

<span data-ttu-id="83187-112">По умолчанию `Get-Random` создает криптографически безопасный случай с помощью класса [рандомнумберженератор](/dotnet/api/system.security.cryptography.randomnumbergenerator) .</span><span class="sxs-lookup"><span data-stu-id="83187-112">By default, `Get-Random` generates cryptographically secure randomness using the [RandomNumberGenerator](/dotnet/api/system.security.cryptography.randomnumbergenerator) class.</span></span>

<span data-ttu-id="83187-113">Параметры класса можно использовать `Get-Random` для указания минимального и максимального значений, количества объектов, возвращаемых из коллекции, или начального номера.</span><span class="sxs-lookup"><span data-stu-id="83187-113">You can use the parameters of `Get-Random` to specify the minimum and maximum values, the number of objects returned from a collection, or a seed number.</span></span>

> [!CAUTION]
> <span data-ttu-id="83187-114">Установка начального значения намеренно приводит к непроизвольному, повторяемому поведению.</span><span class="sxs-lookup"><span data-stu-id="83187-114">Setting the seed deliberately results in non-random, repeatable behavior.</span></span> <span data-ttu-id="83187-115">Его следует использовать только при попытке воспроизведения поведения, например при отладке или анализе скрипта, содержащего `Get-Random` команды.</span><span class="sxs-lookup"><span data-stu-id="83187-115">It should only be used when trying to reproduce behavior, such as when debugging or analyzing a script that includes `Get-Random` commands.</span></span>
>
> <span data-ttu-id="83187-116">Это начальное значение используется для текущей команды и для всех последующих `Get-Random` команд в текущем сеансе до повторного использования **SetSeed** или закрытия сеанса.</span><span class="sxs-lookup"><span data-stu-id="83187-116">This seed value is used for the current command and for all subsequent `Get-Random` commands in the current session until you use **SetSeed** again or close the session.</span></span> <span data-ttu-id="83187-117">Нельзя сбросить начальное значение до значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="83187-117">You can't reset the seed to its default value.</span></span>

## <span data-ttu-id="83187-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="83187-118">EXAMPLES</span></span>

### <span data-ttu-id="83187-119">Пример 1. получение случайного целого числа</span><span class="sxs-lookup"><span data-stu-id="83187-119">Example 1: Get a random integer</span></span>

<span data-ttu-id="83187-120">Эта команда возвращает случайное целое число от 0 (0) до **Int32. MaxValue**.</span><span class="sxs-lookup"><span data-stu-id="83187-120">This command gets a random integer between 0 (zero) and **Int32.MaxValue**.</span></span>

```powershell
Get-Random
```

```Output
3951433
```

### <span data-ttu-id="83187-121">Пример 2. получение случайного целого числа от 0 до 99</span><span class="sxs-lookup"><span data-stu-id="83187-121">Example 2: Get a random integer between 0 and 99</span></span>

```powershell
Get-Random -Maximum 100
```

```Output
47
```

### <span data-ttu-id="83187-122">Пример 3. получение случайного целого числа от-100 до 99</span><span class="sxs-lookup"><span data-stu-id="83187-122">Example 3: Get a random integer between -100 and 99</span></span>

```powershell
Get-Random -Minimum -100 -Maximum 100
```

```Output
56
```

### <span data-ttu-id="83187-123">Пример 4. получение случайного числа с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="83187-123">Example 4: Get a random floating-point number</span></span>

<span data-ttu-id="83187-124">Эта команда возвращает случайное число с плавающей запятой, которое больше или равно 10,7 и меньше 20,92.</span><span class="sxs-lookup"><span data-stu-id="83187-124">This command gets a random floating-point number greater than or equal to 10.7 and less than 20.92.</span></span>

```powershell
Get-Random -Minimum 10.7 -Maximum 20.93
```

```Output
18.08467273887
```

### <span data-ttu-id="83187-125">Пример 5. получение случайного целого числа из массива</span><span class="sxs-lookup"><span data-stu-id="83187-125">Example 5: Get a random integer from an array</span></span>

<span data-ttu-id="83187-126">Эта команда возвращает случайное число из указанного массива.</span><span class="sxs-lookup"><span data-stu-id="83187-126">This command gets a randomly selected number from the specified array.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random
```

```Output
8
```

### <span data-ttu-id="83187-127">Пример 6. получение нескольких случайных целых чисел из массива</span><span class="sxs-lookup"><span data-stu-id="83187-127">Example 6: Get several random integers from an array</span></span>

<span data-ttu-id="83187-128">Эта команда получает три случайно выбранных числа в случайном порядке из массива.</span><span class="sxs-lookup"><span data-stu-id="83187-128">This command gets three randomly selected numbers in random order from an array.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random -Count 3
```

```Output
3
1
13
```

### <span data-ttu-id="83187-129">Пример 7. случайный выбор всей коллекции</span><span class="sxs-lookup"><span data-stu-id="83187-129">Example 7: Randomize an entire collection</span></span>

<span data-ttu-id="83187-130">Эта команда возвращает всю коллекцию в случайном порядке.</span><span class="sxs-lookup"><span data-stu-id="83187-130">This command returns the entire collection in random order.</span></span>

<span data-ttu-id="83187-131">Значение параметра **Count** является статическим свойством **MaxValue** целых чисел.</span><span class="sxs-lookup"><span data-stu-id="83187-131">The value of the **Count** parameter is the **MaxValue** static property of integers.</span></span>

<span data-ttu-id="83187-132">Чтобы вернуть всю коллекцию в случайном порядке, введите любое число, которое больше или равно количеству объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="83187-132">To return an entire collection in random order, enter any number that is greater than or equal to the number of objects in the collection.</span></span>

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

### <span data-ttu-id="83187-133">Пример 8. получение случайного нечислового значения</span><span class="sxs-lookup"><span data-stu-id="83187-133">Example 8: Get a random non-numeric value</span></span>

<span data-ttu-id="83187-134">Эта команда возвращает случайное значение из коллекции, элементы которой не являются числами.</span><span class="sxs-lookup"><span data-stu-id="83187-134">This command returns a random value from a non-numeric collection.</span></span>

```powershell
"red", "yellow", "blue" | Get-Random
```

```Output
yellow
```

### <span data-ttu-id="83187-135">Пример 9. Использование параметра SetSeed</span><span class="sxs-lookup"><span data-stu-id="83187-135">Example 9: Use the SetSeed parameter</span></span>

<span data-ttu-id="83187-136">В этом примере показан результат применения параметра **SetSeed**.</span><span class="sxs-lookup"><span data-stu-id="83187-136">This example shows the effect of using the **SetSeed** parameter.</span></span>

<span data-ttu-id="83187-137">Поскольку **SetSeed** создает неслучайное поведение, он обычно используется только для воспроизведения результатов, например при отладке или анализе скрипта.</span><span class="sxs-lookup"><span data-stu-id="83187-137">Because **SetSeed** produces non-random behavior, it's typically used only to reproduce results, such as when debugging or analyzing a script.</span></span>

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

### <span data-ttu-id="83187-138">Пример 10. получение случайных файлов</span><span class="sxs-lookup"><span data-stu-id="83187-138">Example 10: Get random files</span></span>

<span data-ttu-id="83187-139">Эти команды получают случайный выбор из файлов 50 с `C:` диска локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="83187-139">These commands get a randomly selected sample of 50 files from the `C:` drive of the local computer.</span></span>

```powershell
$Files = Get-ChildItem -Path C:\* -Recurse
$Sample = $Files | Get-Random -Count 50
```

### <span data-ttu-id="83187-140">Пример 11. пробное распределение костей</span><span class="sxs-lookup"><span data-stu-id="83187-140">Example 11: Roll fair dice</span></span>

<span data-ttu-id="83187-141">В этом примере выполняется откат справедливого кристалла 1200 раз и подсчитывается количество результатов.</span><span class="sxs-lookup"><span data-stu-id="83187-141">This example rolls a fair die 1200 times and counts the outcomes.</span></span> <span data-ttu-id="83187-142">Первая команда `ForEach-Object` повторяет вызов `Get-Random` из числа переданного (1-6).</span><span class="sxs-lookup"><span data-stu-id="83187-142">The first command, `ForEach-Object` repeats the call to `Get-Random` from the piped in numbers (1-6).</span></span> <span data-ttu-id="83187-143">Результаты группируются по значению `Group-Object` и форматируются в виде таблицы с `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="83187-143">The results are grouped by their value with `Group-Object` and formatted as a table with `Select-Object`.</span></span>

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

### <span data-ttu-id="83187-144">Пример 12. Использование параметра count</span><span class="sxs-lookup"><span data-stu-id="83187-144">Example 12: Use the Count parameter</span></span>

<span data-ttu-id="83187-145">Теперь можно использовать параметр **Count** без объектов трубопроводов в `Get-Random` .</span><span class="sxs-lookup"><span data-stu-id="83187-145">You can now use the **Count** parameter without piping objects to `Get-Random`.</span></span>
<span data-ttu-id="83187-146">В следующем примере возвращается три случайных числа, меньшие 10.</span><span class="sxs-lookup"><span data-stu-id="83187-146">The following example gets three random numbers less than 10.</span></span>

```powershell
Get-Random -Count 3 -Maximum 10
```

```Output
9
0
8
```

### <span data-ttu-id="83187-147">Пример 13. Использование параметра InputObject с пустой строкой или $null</span><span class="sxs-lookup"><span data-stu-id="83187-147">Example 13: Use the InputObject parameter with an empty string or $null</span></span>

<span data-ttu-id="83187-148">В этом примере параметр **InputObject** задает массив, содержащий пустую строку ( `''` ) и `$null` .</span><span class="sxs-lookup"><span data-stu-id="83187-148">In this example, the **InputObject** parameter specifies an array that contains an empty string (`''`) and `$null`.</span></span>

```powershell
Get-Random -InputObject @('a','',$null)
```

<span data-ttu-id="83187-149">`Get-Random` возвратит либо `a` пустую строку, либо `$null` .</span><span class="sxs-lookup"><span data-stu-id="83187-149">`Get-Random` will return either `a`, empty string, or `$null`.</span></span> <span data-ttu-id="83187-150">Пустой проверочного отображается в виде пустой строки и `$null` возвращается в командную строку PowerShell.</span><span class="sxs-lookup"><span data-stu-id="83187-150">The empty sting displays as a blank line and `$null` returns to a PowerShell prompt.</span></span>

## <span data-ttu-id="83187-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="83187-151">PARAMETERS</span></span>

### <span data-ttu-id="83187-152">— Количество</span><span class="sxs-lookup"><span data-stu-id="83187-152">-Count</span></span>

<span data-ttu-id="83187-153">Указывает число возвращаемых случайных объектов или чисел.</span><span class="sxs-lookup"><span data-stu-id="83187-153">Specifies the number of random objects or numbers to return.</span></span> <span data-ttu-id="83187-154">Значение по умолчанию — 1.</span><span class="sxs-lookup"><span data-stu-id="83187-154">The default is 1.</span></span>

<span data-ttu-id="83187-155">При использовании с параметром `InputObject` , если значение **счетчика** превышает количество объектов в коллекции, `Get-Random` возвращает все объекты в случайном порядке.</span><span class="sxs-lookup"><span data-stu-id="83187-155">When used with `InputObject`, if the value of **Count** exceeds the number of objects in the collection, `Get-Random` returns all of the objects in random order.</span></span>

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

### <span data-ttu-id="83187-156">-InputObject</span><span class="sxs-lookup"><span data-stu-id="83187-156">-InputObject</span></span>

<span data-ttu-id="83187-157">Определяет коллекцию объектов.</span><span class="sxs-lookup"><span data-stu-id="83187-157">Specifies a collection of objects.</span></span> <span data-ttu-id="83187-158">`Get-Random` Возвращает случайно выбранные объекты в случайном порядке из коллекции до числа, указанного параметром **Count**.</span><span class="sxs-lookup"><span data-stu-id="83187-158">`Get-Random` gets randomly selected objects in random order from the collection up to the number specified by **Count**.</span></span> <span data-ttu-id="83187-159">Введите объекты, переменную, содержащую объекты, либо получающую их команду или выражение.</span><span class="sxs-lookup"><span data-stu-id="83187-159">Enter the objects, a variable that contains the objects, or a command or expression that gets the objects.</span></span> <span data-ttu-id="83187-160">Можно также передать коллекцию объектов в `Get-Random` .</span><span class="sxs-lookup"><span data-stu-id="83187-160">You can also pipe a collection of objects to `Get-Random`.</span></span>

<span data-ttu-id="83187-161">Начиная с PowerShell 7, параметр **InputObject** принимает массивы, которые могут содержать пустую строку или `$null` .</span><span class="sxs-lookup"><span data-stu-id="83187-161">Beginning in PowerShell 7, the **InputObject** parameter accepts arrays that can contain an empty string or `$null`.</span></span> <span data-ttu-id="83187-162">Массив можно отправить вниз по конвейеру или в качестве значения параметра **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="83187-162">The array can be sent down the pipeline or as an **InputObject** parameter value.</span></span>

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

### <span data-ttu-id="83187-163">— Максимум</span><span class="sxs-lookup"><span data-stu-id="83187-163">-Maximum</span></span>

<span data-ttu-id="83187-164">Определяет максимальное значение случайного числа.</span><span class="sxs-lookup"><span data-stu-id="83187-164">Specifies a maximum value for the random number.</span></span> <span data-ttu-id="83187-165">`Get-Random` Возвращает значение, которое меньше максимального (не равно).</span><span class="sxs-lookup"><span data-stu-id="83187-165">`Get-Random` returns a value that is less than the maximum (not equal).</span></span> <span data-ttu-id="83187-166">Введите целое число, число двойной точности с плавающей запятой или объект, который можно преобразовать в целое число или Double, например числовую строку ("100").</span><span class="sxs-lookup"><span data-stu-id="83187-166">Enter an integer, a double-precision floating-point number, or an object that can be converted to an integer or double, such as a numeric string ("100").</span></span>

<span data-ttu-id="83187-167">Значение **Maximum** должно быть больше (не равно) значения **Minimum**.</span><span class="sxs-lookup"><span data-stu-id="83187-167">The value of **Maximum** must be greater than (not equal to) the value of **Minimum**.</span></span> <span data-ttu-id="83187-168">Если значение параметра **Maximum** или **Minimum** является числом с плавающей запятой, `Get-Random` возвращает случайное выбранное число с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="83187-168">If the value of **Maximum** or **Minimum** is a floating-point number, `Get-Random` returns a randomly selected floating-point number.</span></span>

<span data-ttu-id="83187-169">На 64-разрядном компьютере, если значение **минимума** является 32-битным целым числом, значение по умолчанию **Maximum** равно **Int32. MaxValue**.</span><span class="sxs-lookup"><span data-stu-id="83187-169">On a 64-bit computer, if the value of **Minimum** is a 32-bit integer, the default value of **Maximum** is **Int32.MaxValue**.</span></span>

<span data-ttu-id="83187-170">Если **минимальное** значение равно Double (число с плавающей запятой), значение по умолчанию **Maximum** равно **Double. MaxValue**.</span><span class="sxs-lookup"><span data-stu-id="83187-170">If the value of **Minimum** is a double (a floating-point number), the default value of **Maximum** is **Double.MaxValue**.</span></span> <span data-ttu-id="83187-171">В противном случае значение по умолчанию — **Int32. MaxValue**.</span><span class="sxs-lookup"><span data-stu-id="83187-171">Otherwise, the default value is **Int32.MaxValue**.</span></span>

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

### <span data-ttu-id="83187-172">— Минимум</span><span class="sxs-lookup"><span data-stu-id="83187-172">-Minimum</span></span>

<span data-ttu-id="83187-173">Определяет минимальное значение случайного числа.</span><span class="sxs-lookup"><span data-stu-id="83187-173">Specifies a minimum value for the random number.</span></span> <span data-ttu-id="83187-174">Введите целое число, число двойной точности с плавающей запятой или объект, который можно преобразовать в целое число или Double, например числовую строку ("100").</span><span class="sxs-lookup"><span data-stu-id="83187-174">Enter an integer, a double-precision floating-point number, or an object that can be converted to an integer or double, such as a numeric string ("100").</span></span> <span data-ttu-id="83187-175">Значение по умолчанию — 0 (нуль).</span><span class="sxs-lookup"><span data-stu-id="83187-175">The default value is 0 (zero).</span></span>

<span data-ttu-id="83187-176">Значение **Minimum** должно быть меньше значения **Maximum**.</span><span class="sxs-lookup"><span data-stu-id="83187-176">The value of **Minimum** must be less than (not equal to) the value of **Maximum**.</span></span> <span data-ttu-id="83187-177">Если значение параметра **Maximum** или **Minimum** является числом с плавающей запятой, `Get-Random` возвращает случайное выбранное число с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="83187-177">If the value of **Maximum** or **Minimum** is a floating-point number, `Get-Random` returns a randomly selected floating-point number.</span></span>

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

### <span data-ttu-id="83187-178">-SetSeed</span><span class="sxs-lookup"><span data-stu-id="83187-178">-SetSeed</span></span>

<span data-ttu-id="83187-179">Определяет начальное значение случайного числа.</span><span class="sxs-lookup"><span data-stu-id="83187-179">Specifies a seed value for the random number generator.</span></span> <span data-ttu-id="83187-180">При использовании **SetSeed** командлет использует метод [System. Random](/dotnet/api/system.random) для создания псевдослучайное чисел, которые не являются криптографически безопасными.</span><span class="sxs-lookup"><span data-stu-id="83187-180">When you use **SetSeed**, the cmdlet uses the [System.Random](/dotnet/api/system.random) method to generate pseudorandom numbers, which is not cryptographically secure.</span></span>

> [!CAUTION]
> <span data-ttu-id="83187-181">Установка начального значения приводит к неслучайному поведению.</span><span class="sxs-lookup"><span data-stu-id="83187-181">Setting the seed results in non-random behavior.</span></span> <span data-ttu-id="83187-182">Его следует использовать только при попытке воспроизведения поведения, например при отладке или анализе скрипта, содержащего `Get-Random` команды.</span><span class="sxs-lookup"><span data-stu-id="83187-182">It should only be used when trying to reproduce behavior, such as when debugging or analyzing a script that includes `Get-Random` commands.</span></span>
>
> <span data-ttu-id="83187-183">Это начальное значение используется для текущей команды и для всех последующих `Get-Random` команд в текущем сеансе до повторного использования **SetSeed** или закрытия сеанса.</span><span class="sxs-lookup"><span data-stu-id="83187-183">This seed value is used for the current command and for all subsequent `Get-Random` commands in the current session until you use **SetSeed** again or close the session.</span></span> <span data-ttu-id="83187-184">Нельзя сбросить начальное значение до значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="83187-184">You can't reset the seed to its default value.</span></span>

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

### <span data-ttu-id="83187-185">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="83187-185">CommonParameters</span></span>

<span data-ttu-id="83187-186">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="83187-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="83187-187">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="83187-187">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="83187-188">Входные данные</span><span class="sxs-lookup"><span data-stu-id="83187-188">INPUTS</span></span>

### <span data-ttu-id="83187-189">System.Object</span><span class="sxs-lookup"><span data-stu-id="83187-189">System.Object</span></span>

<span data-ttu-id="83187-190">Один или несколько объектов можно передать по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="83187-190">You can pipe one or more objects.</span></span> <span data-ttu-id="83187-191">`Get-Random` выбирает значения случайным образом из перенаправленных объектов.</span><span class="sxs-lookup"><span data-stu-id="83187-191">`Get-Random` selects values randomly from the piped objects.</span></span>

## <span data-ttu-id="83187-192">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="83187-192">OUTPUTS</span></span>

### <span data-ttu-id="83187-193">System. Int32, System. Int64, System. Double</span><span class="sxs-lookup"><span data-stu-id="83187-193">System.Int32, System.Int64, System.Double</span></span>

<span data-ttu-id="83187-194">`Get-Random` Возвращает целое число с плавающей запятой или объект, выбранный случайным образом из отправленной коллекции.</span><span class="sxs-lookup"><span data-stu-id="83187-194">`Get-Random` returns an integer or floating-point number, or an object selected randomly from a submitted collection.</span></span>

## <span data-ttu-id="83187-195">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="83187-195">NOTES</span></span>

<span data-ttu-id="83187-196">По умолчанию `Get-Random` создает криптографически безопасный случай с помощью класса [рандомнумберженератор](/dotnet/api/system.security.cryptography.randomnumbergenerator) .</span><span class="sxs-lookup"><span data-stu-id="83187-196">By default, `Get-Random` generates cryptographically secure randomness using the [RandomNumberGenerator](/dotnet/api/system.security.cryptography.randomnumbergenerator) class.</span></span>

<span data-ttu-id="83187-197">`Get-Random` не всегда возвращает тот же тип данных, что и входное значение.</span><span class="sxs-lookup"><span data-stu-id="83187-197">`Get-Random` does not alway return the same data type as the input value.</span></span> <span data-ttu-id="83187-198">В следующей таблице показан тип выходных данных для каждого числового типа входных данных.</span><span class="sxs-lookup"><span data-stu-id="83187-198">The following table shows the output type for each of the numeric input types.</span></span>

| <span data-ttu-id="83187-199">Тип входных данных</span><span class="sxs-lookup"><span data-stu-id="83187-199">Input Type</span></span> | <span data-ttu-id="83187-200">Тип выходных данных</span><span class="sxs-lookup"><span data-stu-id="83187-200">Output Type</span></span> |
| :--------: | :---------: |
|   <span data-ttu-id="83187-201">SByte</span><span class="sxs-lookup"><span data-stu-id="83187-201">SByte</span></span>    |   <span data-ttu-id="83187-202">Double</span><span class="sxs-lookup"><span data-stu-id="83187-202">Double</span></span>    |
|    <span data-ttu-id="83187-203">Byte</span><span class="sxs-lookup"><span data-stu-id="83187-203">Byte</span></span>    |   <span data-ttu-id="83187-204">Double</span><span class="sxs-lookup"><span data-stu-id="83187-204">Double</span></span>    |
|   <span data-ttu-id="83187-205">Int16</span><span class="sxs-lookup"><span data-stu-id="83187-205">Int16</span></span>    |   <span data-ttu-id="83187-206">Double</span><span class="sxs-lookup"><span data-stu-id="83187-206">Double</span></span>    |
|   <span data-ttu-id="83187-207">UInt16</span><span class="sxs-lookup"><span data-stu-id="83187-207">UInt16</span></span>   |   <span data-ttu-id="83187-208">Double</span><span class="sxs-lookup"><span data-stu-id="83187-208">Double</span></span>    |
|   <span data-ttu-id="83187-209">Int32</span><span class="sxs-lookup"><span data-stu-id="83187-209">Int32</span></span>    |    <span data-ttu-id="83187-210">Int32</span><span class="sxs-lookup"><span data-stu-id="83187-210">Int32</span></span>    |
|   <span data-ttu-id="83187-211">UInt32</span><span class="sxs-lookup"><span data-stu-id="83187-211">UInt32</span></span>   |   <span data-ttu-id="83187-212">Double</span><span class="sxs-lookup"><span data-stu-id="83187-212">Double</span></span>    |
|   <span data-ttu-id="83187-213">Int64</span><span class="sxs-lookup"><span data-stu-id="83187-213">Int64</span></span>    |    <span data-ttu-id="83187-214">Int64</span><span class="sxs-lookup"><span data-stu-id="83187-214">Int64</span></span>    |
|   <span data-ttu-id="83187-215">UInt64</span><span class="sxs-lookup"><span data-stu-id="83187-215">UInt64</span></span>   |   <span data-ttu-id="83187-216">Double</span><span class="sxs-lookup"><span data-stu-id="83187-216">Double</span></span>    |
|   <span data-ttu-id="83187-217">Double</span><span class="sxs-lookup"><span data-stu-id="83187-217">Double</span></span>   |   <span data-ttu-id="83187-218">Double</span><span class="sxs-lookup"><span data-stu-id="83187-218">Double</span></span>    |
|   <span data-ttu-id="83187-219">Single</span><span class="sxs-lookup"><span data-stu-id="83187-219">Single</span></span>   |   <span data-ttu-id="83187-220">Double</span><span class="sxs-lookup"><span data-stu-id="83187-220">Double</span></span>    |

<span data-ttu-id="83187-221">Начиная с Windows PowerShell 3,0, `Get-Random` поддерживает 64-разрядные целые числа.</span><span class="sxs-lookup"><span data-stu-id="83187-221">Beginning in Windows PowerShell 3.0, `Get-Random` supports 64-bit integers.</span></span> <span data-ttu-id="83187-222">В Windows PowerShell 2,0 все значения приводятся к типу **System. Int32**.</span><span class="sxs-lookup"><span data-stu-id="83187-222">In Windows PowerShell 2.0, all values are cast to **System.Int32**.</span></span>

<span data-ttu-id="83187-223">Начиная с PowerShell 7, параметр **InputObject** в наборе параметров **рандомлиститемпараметерсет** принимает массивы, содержащие пустую строку или `$null` .</span><span class="sxs-lookup"><span data-stu-id="83187-223">Beginning in PowerShell 7, the **InputObject** parameter in the **RandomListItemParameterSet** parameter set accepts arrays that contain an empty string or `$null`.</span></span> <span data-ttu-id="83187-224">В более ранних версиях PowerShell только параметр **Maximum** в наборе параметров **рандомнумберпараметерсет** принимает пустую строку или `$null` .</span><span class="sxs-lookup"><span data-stu-id="83187-224">In earlier PowerShell versions, only the **Maximum** parameter in the **RandomNumberParameterSet** parameter set accepted an empty string or `$null`.</span></span>

## <span data-ttu-id="83187-225">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="83187-225">RELATED LINKS</span></span>

[<span data-ttu-id="83187-226">System. Security. Cryptography. Рандомнумберженератор ()</span><span class="sxs-lookup"><span data-stu-id="83187-226">System.Security.Cryptography.RandomNumberGenerator()</span></span>](/dotnet/api/system.security.cryptography.randomnumbergenerator)

[<span data-ttu-id="83187-227">Sytem. Random</span><span class="sxs-lookup"><span data-stu-id="83187-227">Sytem.Random</span></span>](/dotnet/api/system.random)
