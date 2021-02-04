---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 02/02/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-random?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Random
ms.openlocfilehash: 842d4ea92f60a92fddcddea11bb8155c708ac192
ms.sourcegitcommit: fa1a84c81e15f1ffac962110b0b4c850c1b173a0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2021
ms.locfileid: "99495965"
---
# Get-Random

## Краткий обзор
Возвращает случайное число или случайным образом выбирает объекты из коллекции.

## SYNTAX

### Рандомнумберпараметерсет (по умолчанию)

```
Get-Random [-SetSeed <Int32>] [[-Maximum] <Object>] [-Minimum <Object>] [-Count <Int32>] [<CommonParameters>]
```

### рандомлиститемпараметерсет

```
Get-Random [-SetSeed <Int32>] [-InputObject] <Object[]> [-Count <Int32>] [<CommonParameters>]
```

### шуффлепараметерсет

```
Get-Random [-SetSeed <Int32>] [-InputObject] <Object[]> [-Shuffle] [<CommonParameters>]
```

## DESCRIPTION

`Get-Random`Командлет возвращает число, выбранное случайным образом. При отправке коллекции объектов в `Get-Random` она получает один или несколько случайно выбранных объектов из коллекции.

Без параметров или входных данных `Get-Random` команда возвращает случайное выбранное 32-разрядное целое число без знака в диапазоне от 0 (ноль) до **Int32. MaxValue** ( `0x7FFFFFFF` , `2,147,483,647` ).

По умолчанию `Get-Random` создает криптографически безопасный случай с помощью класса [рандомнумберженератор](/dotnet/api/system.security.cryptography.randomnumbergenerator) .

Параметры класса можно использовать `Get-Random` для указания минимального и максимального значений, количества объектов, возвращаемых из коллекции, или начального номера.

> [!CAUTION]
> Установка начального значения намеренно приводит к непроизвольному, повторяемому поведению. Его следует использовать только при попытке воспроизведения поведения, например при отладке или анализе скрипта, содержащего `Get-Random` команды.
>
> Это начальное значение используется для текущей команды и для всех последующих `Get-Random` команд в текущем сеансе до повторного использования **SetSeed** или закрытия сеанса. Нельзя сбросить начальное значение до значения по умолчанию.

## Примеры

### Пример 1. получение случайного целого числа

Эта команда возвращает случайное целое число от 0 (0) до **Int32. MaxValue**.

```powershell
Get-Random
```

```Output
3951433
```

### Пример 2. получение случайного целого числа от 0 до 99

```powershell
Get-Random -Maximum 100
```

```Output
47
```

### Пример 3. получение случайного целого числа от-100 до 99

```powershell
Get-Random -Minimum -100 -Maximum 100
```

```Output
56
```

### Пример 4. получение случайного числа с плавающей запятой

Эта команда возвращает случайное число с плавающей запятой, которое больше или равно 10,7 и меньше 20,92.

```powershell
Get-Random -Minimum 10.7 -Maximum 20.93
```

```Output
18.08467273887
```

### Пример 5. получение случайного целого числа из массива

Эта команда возвращает случайное число из указанного массива.

```powershell
1, 2, 3, 5, 8, 13 | Get-Random
```

```Output
8
```

### Пример 6. получение нескольких случайных целых чисел из массива

Эта команда получает три случайно выбранных числа в случайном порядке из массива.

```powershell
1, 2, 3, 5, 8, 13 | Get-Random -Count 3
```

```Output
3
1
13
```

### Пример 7. случайный выбор всей коллекции

Начиная с PowerShell 7,1 можно использовать параметр " **случайный** ", чтобы вернуть всю коллекцию в случайном порядке.

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

### Пример 8. получение случайного нечислового значения

Эта команда возвращает случайное значение из коллекции, элементы которой не являются числами.

```powershell
"red", "yellow", "blue" | Get-Random
```

```Output
yellow
```

### Пример 9. Использование параметра SetSeed

В этом примере показан результат применения параметра **SetSeed**.

Поскольку **SetSeed** создает неслучайное поведение, он обычно используется только для воспроизведения результатов, например при отладке или анализе скрипта.

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

### Пример 10. получение случайных файлов

Эти команды получают случайный выбор из файлов 50 с `C:` диска локального компьютера.

```powershell
$Files = Get-ChildItem -Path C:\* -Recurse
$Sample = $Files | Get-Random -Count 50
```

### Пример 11. пробное распределение костей

В этом примере выполняется откат справедливого кристалла 1200 раз и подсчитывается количество результатов. Первая команда `ForEach-Object` повторяет вызов `Get-Random` из числа переданного (1-6). Результаты группируются по значению `Group-Object` и форматируются в виде таблицы с `Select-Object` .

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

### Пример 12. Использование параметра count

Теперь можно использовать параметр **Count** без объектов трубопроводов в `Get-Random` .
В следующем примере возвращается три случайных числа, меньшие 10.

```powershell
Get-Random -Count 3 -Maximum 10
```

```Output
9
0
8
```

### Пример 13. Использование параметра InputObject с пустой строкой или $null

В этом примере параметр **InputObject** задает массив, содержащий пустую строку ( `''` ) и `$null` .

```powershell
Get-Random -InputObject @('a','',$null)
```

`Get-Random` возвратит либо `a` пустую строку, либо `$null` . Пустой проверочного отображается в виде пустой строки и `$null` возвращается в командную строку PowerShell.

## PARAMETERS

### — Количество

Указывает число возвращаемых случайных объектов или чисел. Значение по умолчанию — 1.

При использовании с параметром `InputObject` , если значение **счетчика** превышает количество объектов в коллекции, `Get-Random` возвращает все объекты в случайном порядке.

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

### -InputObject

Определяет коллекцию объектов. `Get-Random` Возвращает случайно выбранные объекты в случайном порядке из коллекции до числа, указанного параметром **Count**. Введите объекты, переменную, содержащую объекты, либо получающую их команду или выражение. Можно также передать коллекцию объектов в `Get-Random` .

Начиная с PowerShell 7, параметр **InputObject** принимает массивы, которые могут содержать пустую строку или `$null` . Массив можно отправить вниз по конвейеру или в качестве значения параметра **InputObject** .

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

### — Максимум

Определяет максимальное значение случайного числа. `Get-Random` Возвращает значение, которое меньше максимального (не равно). Введите целое число, число двойной точности с плавающей запятой или объект, который можно преобразовать в целое число или Double, например числовую строку ("100").

Значение **Maximum** должно быть больше (не равно) значения **Minimum**. Если значение параметра **Maximum** или **Minimum** является числом с плавающей запятой, `Get-Random` возвращает случайное выбранное число с плавающей запятой.

На 64-разрядном компьютере, если значение **минимума** является 32-битным целым числом, значение по умолчанию **Maximum** равно **Int32. MaxValue**.

Если **минимальное** значение равно Double (число с плавающей запятой), значение по умолчанию **Maximum** равно **Double. MaxValue**. В противном случае значение по умолчанию — **Int32. MaxValue**.

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

### — Минимум

Определяет минимальное значение случайного числа. Введите целое число, число двойной точности с плавающей запятой или объект, который можно преобразовать в целое число или Double, например числовую строку ("100"). Значение по умолчанию — 0 (нуль).

Значение **Minimum** должно быть меньше значения **Maximum**. Если значение параметра **Maximum** или **Minimum** является числом с плавающей запятой, `Get-Random` возвращает случайное выбранное число с плавающей запятой.

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

### -SetSeed

Определяет начальное значение случайного числа. При использовании **SetSeed** командлет использует метод [System. Random](/dotnet/api/system.random) для создания псевдослучайное чисел, которые не являются криптографически безопасными.

> [!CAUTION]
> Установка начального значения приводит к неслучайному поведению. Его следует использовать только при попытке воспроизведения поведения, например при отладке или анализе скрипта, содержащего `Get-Random` команды.
>
> Это начальное значение используется для текущей команды и для всех последующих `Get-Random` команд в текущем сеансе до повторного использования **SetSeed** или закрытия сеанса. Нельзя сбросить начальное значение до значения по умолчанию.

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

### — В случайном порядке

Возвращает всю коллекцию в случайном порядке.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Object

Один или несколько объектов можно передать по конвейеру. `Get-Random` выбирает значения случайным образом из перенаправленных объектов.

## Выходные данные

### System. Int32, System. Int64, System. Double

`Get-Random` Возвращает целое число с плавающей запятой или объект, выбранный случайным образом из отправленной коллекции.

## ПРИМЕЧАНИЯ

По умолчанию `Get-Random` создает криптографически безопасный случай с помощью класса [рандомнумберженератор](/dotnet/api/system.security.cryptography.randomnumbergenerator) .

`Get-Random` не всегда возвращает тот же тип данных, что и входное значение. В следующей таблице показан тип выходных данных для каждого числового типа входных данных.

| Тип входных данных | Тип выходных данных |
| :--------: | :---------: |
|   SByte    |   Double    |
|    Byte    |   Double    |
|   Int16    |   Double    |
|   UInt16   |   Double    |
|   Int32    |    Int32    |
|   UInt32   |   Double    |
|   Int64    |    Int64    |
|   UInt64   |   Double    |
|   Double   |   Double    |
|   Single   |   Double    |

Начиная с Windows PowerShell 3,0, `Get-Random` поддерживает 64-разрядные целые числа. В Windows PowerShell 2,0 все значения приводятся к типу **System. Int32**.

Начиная с PowerShell 7, параметр **InputObject** в наборе параметров **рандомлиститемпараметерсет** принимает массивы, содержащие пустую строку или `$null` . В более ранних версиях PowerShell только параметр **Maximum** в наборе параметров **рандомнумберпараметерсет** принимает пустую строку или `$null` .

## Связанные ссылки

[System. Security. Cryptography. Рандомнумберженератор ()](/dotnet/api/system.security.cryptography.randomnumbergenerator)

[Sytem. Random](/dotnet/api/system.random)
