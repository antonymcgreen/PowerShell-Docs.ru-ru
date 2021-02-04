---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 02/02/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-random?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Random
ms.openlocfilehash: 97576832ea851f01b463f63948fbd80028c9a6fb
ms.sourcegitcommit: fa1a84c81e15f1ffac962110b0b4c850c1b173a0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2021
ms.locfileid: "99495848"
---
# <span data-ttu-id="c1db8-102">Get-Random</span><span class="sxs-lookup"><span data-stu-id="c1db8-102">Get-Random</span></span>

## <span data-ttu-id="c1db8-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c1db8-103">SYNOPSIS</span></span>
<span data-ttu-id="c1db8-104">Возвращает случайное число или случайным образом выбирает объекты из коллекции.</span><span class="sxs-lookup"><span data-stu-id="c1db8-104">Gets a random number, or selects objects randomly from a collection.</span></span>

## <span data-ttu-id="c1db8-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c1db8-105">SYNTAX</span></span>

### <span data-ttu-id="c1db8-106">Рандомнумберпараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="c1db8-106">RandomNumberParameterSet (Default)</span></span>

```
Get-Random [-SetSeed <Int32>] [[-Maximum] <Object>] [-Minimum <Object>] [<CommonParameters>]
```

### <span data-ttu-id="c1db8-107">рандомлиститемпараметерсет</span><span class="sxs-lookup"><span data-stu-id="c1db8-107">RandomListItemParameterSet</span></span>

```
Get-Random [-SetSeed <Int32>] [-InputObject] <Object[]> [-Count <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="c1db8-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c1db8-108">DESCRIPTION</span></span>

<span data-ttu-id="c1db8-109">`Get-Random`Командлет возвращает число, выбранное случайным образом.</span><span class="sxs-lookup"><span data-stu-id="c1db8-109">The `Get-Random` cmdlet gets a randomly selected number.</span></span> <span data-ttu-id="c1db8-110">При отправке коллекции объектов в `Get-Random` она получает один или несколько случайно выбранных объектов из коллекции.</span><span class="sxs-lookup"><span data-stu-id="c1db8-110">If you submit a collection of objects to `Get-Random`, it gets one or more randomly selected objects from the collection.</span></span>

<span data-ttu-id="c1db8-111">Без параметров или входных данных `Get-Random` команда возвращает случайное выбранное 32-разрядное целое число без знака в диапазоне от 0 (ноль) до **Int32. MaxValue** ( `0x7FFFFFFF` , `2,147,483,647` ).</span><span class="sxs-lookup"><span data-stu-id="c1db8-111">Without parameters or input, a `Get-Random` command returns a randomly selected 32-bit unsigned integer between 0 (zero) and **Int32.MaxValue** (`0x7FFFFFFF`, `2,147,483,647`).</span></span>

<span data-ttu-id="c1db8-112">По умолчанию `Get-Random` создает криптографически безопасный случай с помощью класса [рандомнумберженератор](/dotnet/api/system.security.cryptography.randomnumbergenerator) .</span><span class="sxs-lookup"><span data-stu-id="c1db8-112">By default, `Get-Random` generates cryptographically secure randomness using the [RandomNumberGenerator](/dotnet/api/system.security.cryptography.randomnumbergenerator) class.</span></span>

<span data-ttu-id="c1db8-113">Параметры класса можно использовать `Get-Random` для указания минимального и максимального значений, количества объектов, возвращаемых из коллекции, или начального номера.</span><span class="sxs-lookup"><span data-stu-id="c1db8-113">You can use the parameters of `Get-Random` to specify the minimum and maximum values, the number of objects returned from a collection, or a seed number.</span></span>

> [!CAUTION]
> <span data-ttu-id="c1db8-114">Установка начального значения намеренно приводит к непроизвольному, повторяемому поведению.</span><span class="sxs-lookup"><span data-stu-id="c1db8-114">Setting the seed deliberately results in non-random, repeatable behavior.</span></span> <span data-ttu-id="c1db8-115">Его следует использовать только при попытке воспроизведения поведения, например при отладке или анализе скрипта, содержащего `Get-Random` команды.</span><span class="sxs-lookup"><span data-stu-id="c1db8-115">It should only be used when trying to reproduce behavior, such as when debugging or analyzing a script that includes `Get-Random` commands.</span></span>
>
> <span data-ttu-id="c1db8-116">Это начальное значение используется для текущей команды и для всех последующих `Get-Random` команд в текущем сеансе до повторного использования **SetSeed** или закрытия сеанса.</span><span class="sxs-lookup"><span data-stu-id="c1db8-116">This seed value is used for the current command and for all subsequent `Get-Random` commands in the current session until you use **SetSeed** again or close the session.</span></span> <span data-ttu-id="c1db8-117">Нельзя сбросить начальное значение до значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c1db8-117">You can't reset the seed to its default value.</span></span>

## <span data-ttu-id="c1db8-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="c1db8-118">EXAMPLES</span></span>

### <span data-ttu-id="c1db8-119">Пример 1. получение случайного целого числа</span><span class="sxs-lookup"><span data-stu-id="c1db8-119">Example 1: Get a random integer</span></span>

<span data-ttu-id="c1db8-120">Эта команда возвращает случайное целое число от 0 (0) до **Int32. MaxValue**.</span><span class="sxs-lookup"><span data-stu-id="c1db8-120">This command gets a random integer between 0 (zero) and **Int32.MaxValue**.</span></span>

```powershell
Get-Random
```

```Output
3951433
```

### <span data-ttu-id="c1db8-121">Пример 2. получение случайного целого числа от 0 до 99</span><span class="sxs-lookup"><span data-stu-id="c1db8-121">Example 2: Get a random integer between 0 and 99</span></span>

```powershell
Get-Random -Maximum 100
```

```Output
47
```

### <span data-ttu-id="c1db8-122">Пример 3. получение случайного целого числа от-100 до 99</span><span class="sxs-lookup"><span data-stu-id="c1db8-122">Example 3: Get a random integer between -100 and 99</span></span>

```powershell
Get-Random -Minimum -100 -Maximum 100
```

```Output
56
```

### <span data-ttu-id="c1db8-123">Пример 4. получение случайного числа с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="c1db8-123">Example 4: Get a random floating-point number</span></span>

<span data-ttu-id="c1db8-124">Эта команда возвращает случайное число с плавающей запятой, которое больше или равно 10,7 и меньше 20,92.</span><span class="sxs-lookup"><span data-stu-id="c1db8-124">This command gets a random floating-point number greater than or equal to 10.7 and less than 20.92.</span></span>

```powershell
Get-Random -Minimum 10.7 -Maximum 20.93
```

```Output
18.08467273887
```

### <span data-ttu-id="c1db8-125">Пример 5. получение случайного целого числа из массива</span><span class="sxs-lookup"><span data-stu-id="c1db8-125">Example 5: Get a random integer from an array</span></span>

<span data-ttu-id="c1db8-126">Эта команда возвращает случайное число из указанного массива.</span><span class="sxs-lookup"><span data-stu-id="c1db8-126">This command gets a randomly selected number from the specified array.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random
```

```Output
8
```

### <span data-ttu-id="c1db8-127">Пример 6. получение нескольких случайных целых чисел из массива</span><span class="sxs-lookup"><span data-stu-id="c1db8-127">Example 6: Get several random integers from an array</span></span>

<span data-ttu-id="c1db8-128">Эта команда получает три случайно выбранных числа в случайном порядке из массива.</span><span class="sxs-lookup"><span data-stu-id="c1db8-128">This command gets three randomly selected numbers in random order from an array.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random -Count 3
```

```Output
3
1
13
```

### <span data-ttu-id="c1db8-129">Пример 7. случайный выбор всей коллекции</span><span class="sxs-lookup"><span data-stu-id="c1db8-129">Example 7: Randomize an entire collection</span></span>

<span data-ttu-id="c1db8-130">Эта команда возвращает всю коллекцию в случайном порядке.</span><span class="sxs-lookup"><span data-stu-id="c1db8-130">This command returns the entire collection in random order.</span></span>

<span data-ttu-id="c1db8-131">Значение параметра **Count** является статическим свойством **MaxValue** целых чисел.</span><span class="sxs-lookup"><span data-stu-id="c1db8-131">The value of the **Count** parameter is the **MaxValue** static property of integers.</span></span>

<span data-ttu-id="c1db8-132">Чтобы вернуть всю коллекцию в случайном порядке, введите любое число, которое больше или равно количеству объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="c1db8-132">To return an entire collection in random order, enter any number that is greater than or equal to the number of objects in the collection.</span></span>

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

### <span data-ttu-id="c1db8-133">Пример 8. получение случайного нечислового значения</span><span class="sxs-lookup"><span data-stu-id="c1db8-133">Example 8: Get a random non-numeric value</span></span>

<span data-ttu-id="c1db8-134">Эта команда возвращает случайное значение из коллекции, элементы которой не являются числами.</span><span class="sxs-lookup"><span data-stu-id="c1db8-134">This command returns a random value from a non-numeric collection.</span></span>

```powershell
"red", "yellow", "blue" | Get-Random
```

```Output
yellow
```

### <span data-ttu-id="c1db8-135">Пример 9. Использование параметра SetSeed</span><span class="sxs-lookup"><span data-stu-id="c1db8-135">Example 9: Use the SetSeed parameter</span></span>

<span data-ttu-id="c1db8-136">В этом примере показан результат применения параметра **SetSeed**.</span><span class="sxs-lookup"><span data-stu-id="c1db8-136">This example shows the effect of using the **SetSeed** parameter.</span></span>

<span data-ttu-id="c1db8-137">Поскольку **SetSeed** создает неслучайное поведение, он обычно используется только для воспроизведения результатов, например при отладке или анализе скрипта.</span><span class="sxs-lookup"><span data-stu-id="c1db8-137">Because **SetSeed** produces non-random behavior, it's typically used only to reproduce results, such as when debugging or analyzing a script.</span></span>

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

### <span data-ttu-id="c1db8-138">Пример 10. получение случайных файлов</span><span class="sxs-lookup"><span data-stu-id="c1db8-138">Example 10: Get random files</span></span>

<span data-ttu-id="c1db8-139">Эти команды получают случайный выбор из файлов 50 с `C:` диска локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="c1db8-139">These commands get a randomly selected sample of 50 files from the `C:` drive of the local computer.</span></span>

```powershell
$Files = Get-ChildItem -Path C:\* -Recurse
$Sample = $Files | Get-Random -Count 50
```

### <span data-ttu-id="c1db8-140">Пример 11. пробное распределение костей</span><span class="sxs-lookup"><span data-stu-id="c1db8-140">Example 11: Roll fair dice</span></span>

<span data-ttu-id="c1db8-141">В этом примере выполняется откат справедливого кристалла 1200 раз и подсчитывается количество результатов.</span><span class="sxs-lookup"><span data-stu-id="c1db8-141">This example rolls a fair die 1200 times and counts the outcomes.</span></span> <span data-ttu-id="c1db8-142">Первая команда `ForEach-Object` повторяет вызов `Get-Random` из числа переданного (1-6).</span><span class="sxs-lookup"><span data-stu-id="c1db8-142">The first command, `ForEach-Object` repeats the call to `Get-Random` from the piped in numbers (1-6).</span></span> <span data-ttu-id="c1db8-143">Результаты группируются по значению `Group-Object` и форматируются в виде таблицы с `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="c1db8-143">The results are grouped by their value with `Group-Object` and formatted as a table with `Select-Object`.</span></span>

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

## <span data-ttu-id="c1db8-144">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c1db8-144">PARAMETERS</span></span>

### <span data-ttu-id="c1db8-145">— Количество</span><span class="sxs-lookup"><span data-stu-id="c1db8-145">-Count</span></span>

<span data-ttu-id="c1db8-146">Указывает число возвращаемых случайных объектов или чисел.</span><span class="sxs-lookup"><span data-stu-id="c1db8-146">Specifies the number of random objects or numbers to return.</span></span> <span data-ttu-id="c1db8-147">Значение по умолчанию — 1.</span><span class="sxs-lookup"><span data-stu-id="c1db8-147">The default is 1.</span></span>

<span data-ttu-id="c1db8-148">При использовании с параметром `InputObject` , если значение **счетчика** превышает количество объектов в коллекции, `Get-Random` возвращает все объекты в случайном порядке.</span><span class="sxs-lookup"><span data-stu-id="c1db8-148">When used with `InputObject`, if the value of **Count** exceeds the number of objects in the collection, `Get-Random` returns all of the objects in random order.</span></span>

```yaml
Type: System.Int32
Parameter Sets: RandomListItemParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c1db8-149">-InputObject</span><span class="sxs-lookup"><span data-stu-id="c1db8-149">-InputObject</span></span>

<span data-ttu-id="c1db8-150">Определяет коллекцию объектов.</span><span class="sxs-lookup"><span data-stu-id="c1db8-150">Specifies a collection of objects.</span></span> <span data-ttu-id="c1db8-151">`Get-Random` Возвращает случайно выбранные объекты в случайном порядке из коллекции до числа, указанного параметром **Count**.</span><span class="sxs-lookup"><span data-stu-id="c1db8-151">`Get-Random` gets randomly selected objects in random order from the collection up to the number specified by **Count**.</span></span> <span data-ttu-id="c1db8-152">Введите объекты, переменную, содержащую объекты, либо получающую их команду или выражение.</span><span class="sxs-lookup"><span data-stu-id="c1db8-152">Enter the objects, a variable that contains the objects, or a command or expression that gets the objects.</span></span> <span data-ttu-id="c1db8-153">Можно также передать коллекцию объектов в `Get-Random` .</span><span class="sxs-lookup"><span data-stu-id="c1db8-153">You can also pipe a collection of objects to `Get-Random`.</span></span>

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

### <span data-ttu-id="c1db8-154">— Максимум</span><span class="sxs-lookup"><span data-stu-id="c1db8-154">-Maximum</span></span>

<span data-ttu-id="c1db8-155">Определяет максимальное значение случайного числа.</span><span class="sxs-lookup"><span data-stu-id="c1db8-155">Specifies a maximum value for the random number.</span></span> <span data-ttu-id="c1db8-156">`Get-Random` Возвращает значение, которое меньше максимального (не равно).</span><span class="sxs-lookup"><span data-stu-id="c1db8-156">`Get-Random` returns a value that is less than the maximum (not equal).</span></span> <span data-ttu-id="c1db8-157">Введите целое число, число двойной точности с плавающей запятой или объект, который можно преобразовать в целое число или Double, например числовую строку ("100").</span><span class="sxs-lookup"><span data-stu-id="c1db8-157">Enter an integer, a double-precision floating-point number, or an object that can be converted to an integer or double, such as a numeric string ("100").</span></span>

<span data-ttu-id="c1db8-158">Значение **Maximum** должно быть больше (не равно) значения **Minimum**.</span><span class="sxs-lookup"><span data-stu-id="c1db8-158">The value of **Maximum** must be greater than (not equal to) the value of **Minimum**.</span></span> <span data-ttu-id="c1db8-159">Если значение параметра **Maximum** или **Minimum** является числом с плавающей запятой, `Get-Random` возвращает случайное выбранное число с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="c1db8-159">If the value of **Maximum** or **Minimum** is a floating-point number, `Get-Random` returns a randomly selected floating-point number.</span></span>

<span data-ttu-id="c1db8-160">На 64-разрядном компьютере, если значение **минимума** является 32-битным целым числом, значение по умолчанию **Maximum** равно **Int32. MaxValue**.</span><span class="sxs-lookup"><span data-stu-id="c1db8-160">On a 64-bit computer, if the value of **Minimum** is a 32-bit integer, the default value of **Maximum** is **Int32.MaxValue**.</span></span>

<span data-ttu-id="c1db8-161">Если **минимальное** значение равно Double (число с плавающей запятой), значение по умолчанию **Maximum** равно **Double. MaxValue**.</span><span class="sxs-lookup"><span data-stu-id="c1db8-161">If the value of **Minimum** is a double (a floating-point number), the default value of **Maximum** is **Double.MaxValue**.</span></span> <span data-ttu-id="c1db8-162">В противном случае значение по умолчанию — **Int32. MaxValue**.</span><span class="sxs-lookup"><span data-stu-id="c1db8-162">Otherwise, the default value is **Int32.MaxValue**.</span></span>

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

### <span data-ttu-id="c1db8-163">— Минимум</span><span class="sxs-lookup"><span data-stu-id="c1db8-163">-Minimum</span></span>

<span data-ttu-id="c1db8-164">Определяет минимальное значение случайного числа.</span><span class="sxs-lookup"><span data-stu-id="c1db8-164">Specifies a minimum value for the random number.</span></span> <span data-ttu-id="c1db8-165">Введите целое число, число двойной точности с плавающей запятой или объект, который можно преобразовать в целое число или Double, например числовую строку ("100").</span><span class="sxs-lookup"><span data-stu-id="c1db8-165">Enter an integer, a double-precision floating-point number, or an object that can be converted to an integer or double, such as a numeric string ("100").</span></span> <span data-ttu-id="c1db8-166">Значение по умолчанию — 0 (нуль).</span><span class="sxs-lookup"><span data-stu-id="c1db8-166">The default value is 0 (zero).</span></span>

<span data-ttu-id="c1db8-167">Значение **Minimum** должно быть меньше значения **Maximum**.</span><span class="sxs-lookup"><span data-stu-id="c1db8-167">The value of **Minimum** must be less than (not equal to) the value of **Maximum**.</span></span> <span data-ttu-id="c1db8-168">Если значение параметра **Maximum** или **Minimum** является числом с плавающей запятой, `Get-Random` возвращает случайное выбранное число с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="c1db8-168">If the value of **Maximum** or **Minimum** is a floating-point number, `Get-Random` returns a randomly selected floating-point number.</span></span>

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

### <span data-ttu-id="c1db8-169">-SetSeed</span><span class="sxs-lookup"><span data-stu-id="c1db8-169">-SetSeed</span></span>

<span data-ttu-id="c1db8-170">Определяет начальное значение случайного числа.</span><span class="sxs-lookup"><span data-stu-id="c1db8-170">Specifies a seed value for the random number generator.</span></span> <span data-ttu-id="c1db8-171">При использовании **SetSeed** командлет использует метод [System. Random](/dotnet/api/system.random) для создания псевдослучайное чисел, которые не являются криптографически безопасными.</span><span class="sxs-lookup"><span data-stu-id="c1db8-171">When you use **SetSeed**, the cmdlet uses the [System.Random](/dotnet/api/system.random) method to generate pseudorandom numbers, which is not cryptographically secure.</span></span>

> [!CAUTION]
> <span data-ttu-id="c1db8-172">Установка начального значения приводит к неслучайному поведению.</span><span class="sxs-lookup"><span data-stu-id="c1db8-172">Setting the seed results in non-random behavior.</span></span> <span data-ttu-id="c1db8-173">Его следует использовать только при попытке воспроизведения поведения, например при отладке или анализе скрипта, содержащего `Get-Random` команды.</span><span class="sxs-lookup"><span data-stu-id="c1db8-173">It should only be used when trying to reproduce behavior, such as when debugging or analyzing a script that includes `Get-Random` commands.</span></span>
>
> <span data-ttu-id="c1db8-174">Это начальное значение используется для текущей команды и для всех последующих `Get-Random` команд в текущем сеансе до повторного использования **SetSeed** или закрытия сеанса.</span><span class="sxs-lookup"><span data-stu-id="c1db8-174">This seed value is used for the current command and for all subsequent `Get-Random` commands in the current session until you use **SetSeed** again or close the session.</span></span> <span data-ttu-id="c1db8-175">Нельзя сбросить начальное значение до значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c1db8-175">You can't reset the seed to its default value.</span></span>

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

### <span data-ttu-id="c1db8-176">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="c1db8-176">CommonParameters</span></span>

<span data-ttu-id="c1db8-177">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c1db8-177">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c1db8-178">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c1db8-178">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c1db8-179">Входные данные</span><span class="sxs-lookup"><span data-stu-id="c1db8-179">INPUTS</span></span>

### <span data-ttu-id="c1db8-180">System.Object</span><span class="sxs-lookup"><span data-stu-id="c1db8-180">System.Object</span></span>

<span data-ttu-id="c1db8-181">Один или несколько объектов можно передать по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="c1db8-181">You can pipe one or more objects.</span></span> <span data-ttu-id="c1db8-182">`Get-Random` выбирает значения случайным образом из перенаправленных объектов.</span><span class="sxs-lookup"><span data-stu-id="c1db8-182">`Get-Random` selects values randomly from the piped objects.</span></span>

## <span data-ttu-id="c1db8-183">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="c1db8-183">OUTPUTS</span></span>

### <span data-ttu-id="c1db8-184">System. Int32, System. Int64, System. Double</span><span class="sxs-lookup"><span data-stu-id="c1db8-184">System.Int32, System.Int64, System.Double</span></span>

<span data-ttu-id="c1db8-185">`Get-Random` Возвращает целое число с плавающей запятой или объект, выбранный случайным образом из отправленной коллекции.</span><span class="sxs-lookup"><span data-stu-id="c1db8-185">`Get-Random` returns an integer or floating-point number, or an object selected randomly from a submitted collection.</span></span>

## <span data-ttu-id="c1db8-186">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="c1db8-186">NOTES</span></span>

<span data-ttu-id="c1db8-187">По умолчанию `Get-Random` создает криптографически безопасный случай с помощью класса [рандомнумберженератор](/dotnet/api/system.security.cryptography.randomnumbergenerator) .</span><span class="sxs-lookup"><span data-stu-id="c1db8-187">By default, `Get-Random` generates cryptographically secure randomness using the [RandomNumberGenerator](/dotnet/api/system.security.cryptography.randomnumbergenerator) class.</span></span>

<span data-ttu-id="c1db8-188">`Get-Random` не всегда возвращает тот же тип данных, что и входное значение.</span><span class="sxs-lookup"><span data-stu-id="c1db8-188">`Get-Random` does not alway return the same data type as the input value.</span></span> <span data-ttu-id="c1db8-189">В следующей таблице показан тип выходных данных для каждого числового типа входных данных.</span><span class="sxs-lookup"><span data-stu-id="c1db8-189">The following table shows the output type for each of the numeric input types.</span></span>

| <span data-ttu-id="c1db8-190">Тип входных данных</span><span class="sxs-lookup"><span data-stu-id="c1db8-190">Input Type</span></span> | <span data-ttu-id="c1db8-191">Тип выходных данных</span><span class="sxs-lookup"><span data-stu-id="c1db8-191">Output Type</span></span> |
| :--------: | :---------: |
|   <span data-ttu-id="c1db8-192">SByte</span><span class="sxs-lookup"><span data-stu-id="c1db8-192">SByte</span></span>    |   <span data-ttu-id="c1db8-193">Double</span><span class="sxs-lookup"><span data-stu-id="c1db8-193">Double</span></span>    |
|    <span data-ttu-id="c1db8-194">Byte</span><span class="sxs-lookup"><span data-stu-id="c1db8-194">Byte</span></span>    |   <span data-ttu-id="c1db8-195">Double</span><span class="sxs-lookup"><span data-stu-id="c1db8-195">Double</span></span>    |
|   <span data-ttu-id="c1db8-196">Int16</span><span class="sxs-lookup"><span data-stu-id="c1db8-196">Int16</span></span>    |   <span data-ttu-id="c1db8-197">Double</span><span class="sxs-lookup"><span data-stu-id="c1db8-197">Double</span></span>    |
|   <span data-ttu-id="c1db8-198">UInt16</span><span class="sxs-lookup"><span data-stu-id="c1db8-198">UInt16</span></span>   |   <span data-ttu-id="c1db8-199">Double</span><span class="sxs-lookup"><span data-stu-id="c1db8-199">Double</span></span>    |
|   <span data-ttu-id="c1db8-200">Int32</span><span class="sxs-lookup"><span data-stu-id="c1db8-200">Int32</span></span>    |    <span data-ttu-id="c1db8-201">Int32</span><span class="sxs-lookup"><span data-stu-id="c1db8-201">Int32</span></span>    |
|   <span data-ttu-id="c1db8-202">UInt32</span><span class="sxs-lookup"><span data-stu-id="c1db8-202">UInt32</span></span>   |   <span data-ttu-id="c1db8-203">Double</span><span class="sxs-lookup"><span data-stu-id="c1db8-203">Double</span></span>    |
|   <span data-ttu-id="c1db8-204">Int64</span><span class="sxs-lookup"><span data-stu-id="c1db8-204">Int64</span></span>    |    <span data-ttu-id="c1db8-205">Int64</span><span class="sxs-lookup"><span data-stu-id="c1db8-205">Int64</span></span>    |
|   <span data-ttu-id="c1db8-206">UInt64</span><span class="sxs-lookup"><span data-stu-id="c1db8-206">UInt64</span></span>   |   <span data-ttu-id="c1db8-207">Double</span><span class="sxs-lookup"><span data-stu-id="c1db8-207">Double</span></span>    |
|   <span data-ttu-id="c1db8-208">Double</span><span class="sxs-lookup"><span data-stu-id="c1db8-208">Double</span></span>   |   <span data-ttu-id="c1db8-209">Double</span><span class="sxs-lookup"><span data-stu-id="c1db8-209">Double</span></span>    |
|   <span data-ttu-id="c1db8-210">Single</span><span class="sxs-lookup"><span data-stu-id="c1db8-210">Single</span></span>   |   <span data-ttu-id="c1db8-211">Double</span><span class="sxs-lookup"><span data-stu-id="c1db8-211">Double</span></span>    |

<span data-ttu-id="c1db8-212">Начиная с Windows PowerShell 3,0, `Get-Random` поддерживает 64-разрядные целые числа.</span><span class="sxs-lookup"><span data-stu-id="c1db8-212">Beginning in Windows PowerShell 3.0, `Get-Random` supports 64-bit integers.</span></span> <span data-ttu-id="c1db8-213">В Windows PowerShell 2,0 все значения приводятся к типу **System. Int32**.</span><span class="sxs-lookup"><span data-stu-id="c1db8-213">In Windows PowerShell 2.0, all values are cast to **System.Int32**.</span></span>

## <span data-ttu-id="c1db8-214">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="c1db8-214">RELATED LINKS</span></span>

[<span data-ttu-id="c1db8-215">System. Security. Cryptography. Рандомнумберженератор ()</span><span class="sxs-lookup"><span data-stu-id="c1db8-215">System.Security.Cryptography.RandomNumberGenerator()</span></span>](/dotnet/api/system.security.cryptography.randomnumbergenerator)

[<span data-ttu-id="c1db8-216">Sytem. Random</span><span class="sxs-lookup"><span data-stu-id="c1db8-216">Sytem.Random</span></span>](/dotnet/api/system.random)
