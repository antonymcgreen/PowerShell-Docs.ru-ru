---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Date
ms.openlocfilehash: 4ae3734d0ce41ef2faa7bcf3e07f136b9e9916a2
ms.sourcegitcommit: 077488408c820c860131382324bdd576d0edf52a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95514965"
---
# <span data-ttu-id="ec517-103">Get-Date</span><span class="sxs-lookup"><span data-stu-id="ec517-103">Get-Date</span></span>

## <span data-ttu-id="ec517-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ec517-104">SYNOPSIS</span></span>
<span data-ttu-id="ec517-105">Получает текущую дату и время.</span><span class="sxs-lookup"><span data-stu-id="ec517-105">Gets the current date and time.</span></span>

## <span data-ttu-id="ec517-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ec517-106">SYNTAX</span></span>

### <span data-ttu-id="ec517-107">net (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="ec517-107">net (Default)</span></span>

```
Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 [-Format <String>] [<CommonParameters>]
```

### <span data-ttu-id="ec517-108">UFormat</span><span class="sxs-lookup"><span data-stu-id="ec517-108">UFormat</span></span>

```
Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 [-UFormat <String>] [<CommonParameters>]
```

## <span data-ttu-id="ec517-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ec517-109">DESCRIPTION</span></span>

<span data-ttu-id="ec517-110">`Get-Date`Командлет возвращает объект **DateTime** , представляющий текущую дату или указанную дату.</span><span class="sxs-lookup"><span data-stu-id="ec517-110">The `Get-Date` cmdlet gets a **DateTime** object that represents the current date or a date that you specify.</span></span> <span data-ttu-id="ec517-111">`Get-Date` может форматировать дату и время в нескольких форматах .NET и UNIX.</span><span class="sxs-lookup"><span data-stu-id="ec517-111">`Get-Date` can format the date and time in several .NET and UNIX formats.</span></span> <span data-ttu-id="ec517-112">Можно использовать `Get-Date` для создания строки символов даты или времени, а затем отправить строку другим командлетам или программам.</span><span class="sxs-lookup"><span data-stu-id="ec517-112">You can use `Get-Date` to generate a date or time character string, and then send the string to other cmdlets or programs.</span></span>

<span data-ttu-id="ec517-113">`Get-Date` использует параметры языка и региональных параметров компьютера для определения формата выходных данных.</span><span class="sxs-lookup"><span data-stu-id="ec517-113">`Get-Date` uses the computer's culture settings to determine how the output is formatted.</span></span> <span data-ttu-id="ec517-114">Чтобы просмотреть параметры компьютера, используйте `(Get-Culture).DateTimeFormat` .</span><span class="sxs-lookup"><span data-stu-id="ec517-114">To view your computer's settings, use `(Get-Culture).DateTimeFormat`.</span></span>

## <span data-ttu-id="ec517-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="ec517-115">EXAMPLES</span></span>

### <span data-ttu-id="ec517-116">Пример 1. Получение текущей даты и времени</span><span class="sxs-lookup"><span data-stu-id="ec517-116">Example 1: Get the current date and time</span></span>

<span data-ttu-id="ec517-117">В этом примере `Get-Date` выводит текущую системную дату и время.</span><span class="sxs-lookup"><span data-stu-id="ec517-117">In this example, `Get-Date` displays the current system date and time.</span></span> <span data-ttu-id="ec517-118">Выходные данные имеют формат длинной даты и длительное время.</span><span class="sxs-lookup"><span data-stu-id="ec517-118">The output is in the long-date and long-time formats.</span></span>

```powershell
Get-Date
```

```Output
Tuesday, June 25, 2019 14:53:32
```

### <span data-ttu-id="ec517-119">Пример 2. Получение элементов текущей даты и времени</span><span class="sxs-lookup"><span data-stu-id="ec517-119">Example 2: Get elements of the current date and time</span></span>

<span data-ttu-id="ec517-120">В этом примере показано, как использовать `Get-Date` для получения элемента даты или времени.</span><span class="sxs-lookup"><span data-stu-id="ec517-120">This example shows how to use `Get-Date` to get either the date or time element.</span></span> <span data-ttu-id="ec517-121">Параметр использует аргументы **Date**, **time** или **DateTime**.</span><span class="sxs-lookup"><span data-stu-id="ec517-121">The parameter uses the arguments **Date**, **Time**, or **DateTime**.</span></span>

```powershell
Get-Date -DisplayHint Date
```

```Output
Tuesday, June 25, 2019
```

<span data-ttu-id="ec517-122">`Get-Date` использует параметр **дисплайхинт** с аргументом **Date** , чтобы получить только дату.</span><span class="sxs-lookup"><span data-stu-id="ec517-122">`Get-Date` uses the **DisplayHint** parameter with the **Date** argument to get only the date.</span></span>

### <span data-ttu-id="ec517-123">Пример 3. Получение даты и времени с помощью описателя формата .NET</span><span class="sxs-lookup"><span data-stu-id="ec517-123">Example 3: Get the date and time with a .NET format specifier</span></span>

<span data-ttu-id="ec517-124">В этом примере используется описатель формата .NET для настройки формата вывода.</span><span class="sxs-lookup"><span data-stu-id="ec517-124">In this example, a .NET format specifier is used to customize the output's format.</span></span> <span data-ttu-id="ec517-125">Выходные данные представляют собой **строковый** объект.</span><span class="sxs-lookup"><span data-stu-id="ec517-125">The output is a **String** object.</span></span>

```powershell
Get-Date -Format "dddd MM/dd/yyyy HH:mm K"
```

```Output
Tuesday 06/25/2019 16:17 -07:00
```

<span data-ttu-id="ec517-126">`Get-Date` использует параметр **Format** для указания нескольких описателей формата.</span><span class="sxs-lookup"><span data-stu-id="ec517-126">`Get-Date` uses the **Format** parameter to specify several format specifiers.</span></span>

<span data-ttu-id="ec517-127">Описатели формата .NET, используемые в этом примере, определяются следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ec517-127">The .NET format specifiers used in this example are defined as follows:</span></span>

| <span data-ttu-id="ec517-128">Описатель</span><span class="sxs-lookup"><span data-stu-id="ec517-128">Specifier</span></span> | <span data-ttu-id="ec517-129">Определение</span><span class="sxs-lookup"><span data-stu-id="ec517-129">Definition</span></span> |
| --- | --- |
| `dddd` | <span data-ttu-id="ec517-130">День недели — полное имя</span><span class="sxs-lookup"><span data-stu-id="ec517-130">Day of the week - full name</span></span> |
| `MM` | <span data-ttu-id="ec517-131">Номер месяца.</span><span class="sxs-lookup"><span data-stu-id="ec517-131">Month number</span></span> |
| `dd` | <span data-ttu-id="ec517-132">День месяца-2 цифры</span><span class="sxs-lookup"><span data-stu-id="ec517-132">Day of the month - 2 digits</span></span> |
| `yyyy` | <span data-ttu-id="ec517-133">Год в 4-значном формате</span><span class="sxs-lookup"><span data-stu-id="ec517-133">Year in 4-digit format</span></span> |
| `HH:mm` | <span data-ttu-id="ec517-134">Время в 24-часовом формате — нет секунд</span><span class="sxs-lookup"><span data-stu-id="ec517-134">Time in 24-hour format -no seconds</span></span> |
| `K` | <span data-ttu-id="ec517-135">Смещение часового пояса от универсальной координаты времени (UTC)</span><span class="sxs-lookup"><span data-stu-id="ec517-135">Time zone offset from Universal Time Coordinate (UTC)</span></span> |

<span data-ttu-id="ec517-136">Дополнительные сведения о спецификаторах формата .NET см. в разделе [строки настраиваемых форматов даты и времени](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span><span class="sxs-lookup"><span data-stu-id="ec517-136">For more information about .NET format specifiers, see [Custom date and time format strings](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span></span>

### <span data-ttu-id="ec517-137">Пример 4. Получение даты и времени с помощью описателя UFormat</span><span class="sxs-lookup"><span data-stu-id="ec517-137">Example 4: Get the date and time with a UFormat specifier</span></span>

<span data-ttu-id="ec517-138">В этом примере для настройки формата вывода используются несколько описателей формата **UFormat** .</span><span class="sxs-lookup"><span data-stu-id="ec517-138">In this example, several **UFormat** format specifiers are used to customize the output's format.</span></span>
<span data-ttu-id="ec517-139">Выходные данные представляют собой **строковый** объект.</span><span class="sxs-lookup"><span data-stu-id="ec517-139">The output is a **String** object.</span></span>

```powershell
Get-Date -UFormat "%A %m/%d/%Y %R %Z"
```

```Output
Tuesday 06/25/2019 16:19 -07
```

<span data-ttu-id="ec517-140">`Get-Date` использует параметр **UFormat** для указания нескольких описателей формата.</span><span class="sxs-lookup"><span data-stu-id="ec517-140">`Get-Date` uses the **UFormat** parameter to specify several format specifiers.</span></span>

<span data-ttu-id="ec517-141">Описатели формата **UFormat** , используемые в этом примере, определяются следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ec517-141">The **UFormat** format specifiers used in this example are defined as follows:</span></span>

| <span data-ttu-id="ec517-142">Описатель</span><span class="sxs-lookup"><span data-stu-id="ec517-142">Specifier</span></span> | <span data-ttu-id="ec517-143">Определение</span><span class="sxs-lookup"><span data-stu-id="ec517-143">Definition</span></span> |
| --- | --- |
| `%A` | <span data-ttu-id="ec517-144">День недели — полное имя</span><span class="sxs-lookup"><span data-stu-id="ec517-144">Day of the week - full name</span></span> |
| `%m` | <span data-ttu-id="ec517-145">Номер месяца.</span><span class="sxs-lookup"><span data-stu-id="ec517-145">Month number</span></span> |
| `%d` | <span data-ttu-id="ec517-146">День месяца-2 цифры</span><span class="sxs-lookup"><span data-stu-id="ec517-146">Day of the month - 2 digits</span></span> |
| `%Y` | <span data-ttu-id="ec517-147">Год в 4-значном формате</span><span class="sxs-lookup"><span data-stu-id="ec517-147">Year in 4-digit format</span></span> |
| `%R` | <span data-ttu-id="ec517-148">Время в 24-часовом формате — нет секунд</span><span class="sxs-lookup"><span data-stu-id="ec517-148">Time in 24-hour format -no seconds</span></span> |
| `%Z` | <span data-ttu-id="ec517-149">Смещение часового пояса от универсальной координаты времени (UTC)</span><span class="sxs-lookup"><span data-stu-id="ec517-149">Time zone offset from Universal Time Coordinate (UTC)</span></span> |

<span data-ttu-id="ec517-150">Список допустимых описателей формата **UFormat** см. в разделе " [Примечания](#notes) ".</span><span class="sxs-lookup"><span data-stu-id="ec517-150">For a list of valid **UFormat** format specifiers, see the [Notes](#notes) section.</span></span>

### <span data-ttu-id="ec517-151">Пример 5. получение дня года для даты</span><span class="sxs-lookup"><span data-stu-id="ec517-151">Example 5: Get a date's day of the year</span></span>

<span data-ttu-id="ec517-152">В этом примере свойство используется для получения числового дня года.</span><span class="sxs-lookup"><span data-stu-id="ec517-152">In this example, a property is used to get the numeric day of the year.</span></span>

<span data-ttu-id="ec517-153">В григорианском календаре 365 дней, за исключением високосных лет, имеющих 366 дней.</span><span class="sxs-lookup"><span data-stu-id="ec517-153">The Gregorian calendar has 365 days, except for leap years that have 366 days.</span></span> <span data-ttu-id="ec517-154">Например, 31 декабря 2020 — это день 366.</span><span class="sxs-lookup"><span data-stu-id="ec517-154">For example, December 31, 2020 is day 366.</span></span>

```powershell
(Get-Date -Year 2020 -Month 12 -Day 31).DayOfYear
```

```Output
366
```

<span data-ttu-id="ec517-155">`Get-Date` использует три параметра для указания даты: **год**, **месяц** и **день**.</span><span class="sxs-lookup"><span data-stu-id="ec517-155">`Get-Date` uses three parameters to specify the date: **Year**, **Month**, and **Day**.</span></span> <span data-ttu-id="ec517-156">Команда заключена в круглые скобки, поэтому результат вычисляется свойством **DayofYear** .</span><span class="sxs-lookup"><span data-stu-id="ec517-156">The command is wrapped with parentheses so that the result is evaluated by the **DayofYear** property.</span></span>

### <span data-ttu-id="ec517-157">Пример 6. Проверка того, скорректирована ли дата на летнее время</span><span class="sxs-lookup"><span data-stu-id="ec517-157">Example 6: Check if a date is adjusted for daylight savings time</span></span>

<span data-ttu-id="ec517-158">В этом примере используется логический метод для проверки, корректируется ли дата на летнее время.</span><span class="sxs-lookup"><span data-stu-id="ec517-158">This example uses a boolean method to verify if a date is adjusted by daylight savings time.</span></span>

```powershell
$DST = Get-Date
$DST.IsDaylightSavingTime()
```

```Output
True
```

<span data-ttu-id="ec517-159">Переменная, `$DST` в которой хранится результат `Get-Date` .</span><span class="sxs-lookup"><span data-stu-id="ec517-159">A variable, `$DST` stores the result of `Get-Date`.</span></span> <span data-ttu-id="ec517-160">`$DST` проверяет, корректируется ли дата на летнее время, с помощью метода **исдайлигхтсавингтиме** .</span><span class="sxs-lookup"><span data-stu-id="ec517-160">`$DST` uses the **IsDaylightSavingTime** method to test if the date is adjusted for daylight savings time.</span></span>

### <span data-ttu-id="ec517-161">Пример 7. Преобразование текущего времени в время в формате UTC</span><span class="sxs-lookup"><span data-stu-id="ec517-161">Example 7: Convert the current time to UTC time</span></span>

<span data-ttu-id="ec517-162">В этом примере текущее время преобразуется в время в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="ec517-162">In this example, the current time is converted to UTC time.</span></span> <span data-ttu-id="ec517-163">Для преобразования времени используется смещение в формате UTC для языкового стандарта системы.</span><span class="sxs-lookup"><span data-stu-id="ec517-163">The UTC offset for the system's locale is used to convert the time.</span></span> <span data-ttu-id="ec517-164">В таблице в разделе " [Примечания](#notes) " перечислены допустимые описатели формата **UFormat** .</span><span class="sxs-lookup"><span data-stu-id="ec517-164">A table in the [Notes](#notes) section lists the valid **UFormat** format specifiers.</span></span>

```powershell
Get-Date -UFormat "%A %B/%d/%Y %T %Z"
$Time = Get-Date
$Time.ToUniversalTime()
```

```Output
Wednesday June/26/2019 10:45:26 -07

Wednesday, June 26, 2019 17:45:26
```

<span data-ttu-id="ec517-165">`Get-Date` использует параметр **UFormat** с описателями формата для вывода текущей системной даты и времени.</span><span class="sxs-lookup"><span data-stu-id="ec517-165">`Get-Date` uses the **UFormat** parameter with format specifiers to display the current system date and time.</span></span> <span data-ttu-id="ec517-166">Описатель формата **% Z** представляет смещение в формате UTC, равное **-07**.</span><span class="sxs-lookup"><span data-stu-id="ec517-166">The format specifier **%Z** represents the UTC offset of **-07**.</span></span>

<span data-ttu-id="ec517-167">`$Time`Переменная хранит текущую системную дату и время.</span><span class="sxs-lookup"><span data-stu-id="ec517-167">The `$Time` variable stores the current system date and time.</span></span> <span data-ttu-id="ec517-168">`$Time` использует метод **ToUniversalTime ()** для преобразования времени на основе смещения UTC компьютера.</span><span class="sxs-lookup"><span data-stu-id="ec517-168">`$Time` uses the **ToUniversalTime()** method to convert the time based on the computer's UTC offset.</span></span>

### <span data-ttu-id="ec517-169">Пример 8. Создание метки времени</span><span class="sxs-lookup"><span data-stu-id="ec517-169">Example 8: Create a timestamp</span></span>

<span data-ttu-id="ec517-170">В этом примере описатель формата создает объект **строки** метки времени для имени каталога.</span><span class="sxs-lookup"><span data-stu-id="ec517-170">In this example, a format specifier creates a timestamp **String** object for a directory name.</span></span> <span data-ttu-id="ec517-171">Метка времени включает дату, время и смещение в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="ec517-171">The timestamp includes the date, time, and UTC offset.</span></span>

```powershell
$timestamp = Get-Date -Format o | ForEach-Object { $_ -replace ":", "." }
New-Item -Path C:\Test\$timestamp -Type Directory
```

```Output
    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         6/27/2019    07:59                2019-06-27T07.59.24.4603750-07.00
```

<span data-ttu-id="ec517-172">`$timestamp`Переменная хранит результаты выполнения `Get-Date` команды.</span><span class="sxs-lookup"><span data-stu-id="ec517-172">The `$timestamp` variable stores the results of a `Get-Date` command.</span></span> <span data-ttu-id="ec517-173">`Get-Date` использует параметр **Format** с описателем формата "нижний регистр" `o` для создания объекта **строки** метки времени.</span><span class="sxs-lookup"><span data-stu-id="ec517-173">`Get-Date` uses the **Format** parameter with the format specifier of lowercase `o` to create a timestamp **String** object.</span></span> <span data-ttu-id="ec517-174">Объект отправляется по конвейеру в `ForEach-Object` .</span><span class="sxs-lookup"><span data-stu-id="ec517-174">The object is sent down the pipeline to `ForEach-Object`.</span></span> <span data-ttu-id="ec517-175">Блок **ScriptBlock** содержит `$_` переменную, представляющую текущий объект конвейера.</span><span class="sxs-lookup"><span data-stu-id="ec517-175">A **ScriptBlock** contains the `$_` variable that represents the current pipeline object.</span></span> <span data-ttu-id="ec517-176">Строка метки времени разделяются двоеточиями, которые заменяются точками.</span><span class="sxs-lookup"><span data-stu-id="ec517-176">The timestamp string is delimited by colons that are replaced by periods.</span></span>

<span data-ttu-id="ec517-177">`New-Item` использует параметр **path** для указания расположения нового каталога.</span><span class="sxs-lookup"><span data-stu-id="ec517-177">`New-Item` uses the **Path** parameter to specify the location for a new directory.</span></span> <span data-ttu-id="ec517-178">Путь включает `$timestamp` переменную в качестве имени каталога.</span><span class="sxs-lookup"><span data-stu-id="ec517-178">The path includes the `$timestamp` variable as the directory name.</span></span> <span data-ttu-id="ec517-179">Параметр **типа** указывает, что каталог создан.</span><span class="sxs-lookup"><span data-stu-id="ec517-179">The **Type** parameter specifies that a directory is created.</span></span>

## <span data-ttu-id="ec517-180">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ec517-180">PARAMETERS</span></span>

### <span data-ttu-id="ec517-181">-Date</span><span class="sxs-lookup"><span data-stu-id="ec517-181">-Date</span></span>

<span data-ttu-id="ec517-182">Указывает дату и время.</span><span class="sxs-lookup"><span data-stu-id="ec517-182">Specifies a date and time.</span></span> <span data-ttu-id="ec517-183">Время является необязательным и, если не указано, возвращает 00:00:00.</span><span class="sxs-lookup"><span data-stu-id="ec517-183">Time is optional and if not specified, returns 00:00:00.</span></span>

<span data-ttu-id="ec517-184">Введите дату и время в формате, стандартном для национальной настройки системы.</span><span class="sxs-lookup"><span data-stu-id="ec517-184">Enter the date and time in a format that is standard for the system locale.</span></span>

<span data-ttu-id="ec517-185">Например, на английском языке США:</span><span class="sxs-lookup"><span data-stu-id="ec517-185">For example, in US English:</span></span>

<span data-ttu-id="ec517-186">`Get-Date -Date "6/25/2019 12:30:22"` Возвращает вторник, 25 июня 2019 12:30:22</span><span class="sxs-lookup"><span data-stu-id="ec517-186">`Get-Date -Date "6/25/2019 12:30:22"` returns Tuesday, June 25, 2019 12:30:22</span></span>

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases: LastWriteTime

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ec517-187">-Day</span><span class="sxs-lookup"><span data-stu-id="ec517-187">-Day</span></span>

<span data-ttu-id="ec517-188">Указывает выводимый день месяца.</span><span class="sxs-lookup"><span data-stu-id="ec517-188">Specifies the day of the month that is displayed.</span></span> <span data-ttu-id="ec517-189">Введите значение от 1 до 31.</span><span class="sxs-lookup"><span data-stu-id="ec517-189">Enter a value from 1 to 31.</span></span>

<span data-ttu-id="ec517-190">Если указанное значение больше числа дней в месяце, PowerShell добавляет число дней в месяц.</span><span class="sxs-lookup"><span data-stu-id="ec517-190">If the specified value is greater than the number of days in a month, PowerShell adds the number of days to the month.</span></span> <span data-ttu-id="ec517-191">Например, `Get-Date -Month 2 -Day 31` отображается **3 марта**, а не **31 февраля**.</span><span class="sxs-lookup"><span data-stu-id="ec517-191">For example, `Get-Date -Month 2 -Day 31` displays **March 3**, not **February 31**.</span></span>

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

### <span data-ttu-id="ec517-192">-DisplayHint</span><span class="sxs-lookup"><span data-stu-id="ec517-192">-DisplayHint</span></span>

<span data-ttu-id="ec517-193">Определяет, какие элементы даты и времени будут отображаться.</span><span class="sxs-lookup"><span data-stu-id="ec517-193">Determines which elements of the date and time are displayed.</span></span>

<span data-ttu-id="ec517-194">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="ec517-194">The accepted values are as follows:</span></span>

- <span data-ttu-id="ec517-195">**Date:** отображается только дата;</span><span class="sxs-lookup"><span data-stu-id="ec517-195">**Date**: displays only the date</span></span>
- <span data-ttu-id="ec517-196">**Time:** отображается только время;</span><span class="sxs-lookup"><span data-stu-id="ec517-196">**Time**: displays only the time</span></span>
- <span data-ttu-id="ec517-197">**DateTime:** отображаются дата и время.</span><span class="sxs-lookup"><span data-stu-id="ec517-197">**DateTime**: displays the date and time</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.DisplayHintType
Parameter Sets: (All)
Aliases:
Accepted values: Date, Time, DateTime

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ec517-198">-Format</span><span class="sxs-lookup"><span data-stu-id="ec517-198">-Format</span></span>

<span data-ttu-id="ec517-199">Выводит дату и время в формате Microsoft .NET Framework, определяемом спецификатором формата.</span><span class="sxs-lookup"><span data-stu-id="ec517-199">Displays the date and time in the Microsoft .NET Framework format indicated by the format specifier.</span></span>
<span data-ttu-id="ec517-200">Параметр **Format** выводит **строковый** объект.</span><span class="sxs-lookup"><span data-stu-id="ec517-200">The **Format** parameter outputs a **String** object.</span></span>

<span data-ttu-id="ec517-201">Список доступных описателей формата .NET см. в разделе [строки настраиваемых форматов даты и времени](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span><span class="sxs-lookup"><span data-stu-id="ec517-201">For a list of available .NET format specifiers, see [Custom date and time format strings](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span></span>

<span data-ttu-id="ec517-202">При использовании параметра **Format** `Get-Date` получает только свойства объекта **DateTime** , необходимые для вывода даты.</span><span class="sxs-lookup"><span data-stu-id="ec517-202">When the **Format** parameter is used, `Get-Date` only gets the **DateTime** object's properties necessary to display the date.</span></span> <span data-ttu-id="ec517-203">Поэтому некоторые свойства и методы объекта **DateTime** могут быть недоступны.</span><span class="sxs-lookup"><span data-stu-id="ec517-203">As a result, some of the properties and methods of **DateTime** objects might not be available.</span></span>

<span data-ttu-id="ec517-204">Начиная с PowerShell 5,0, в качестве значений параметра **Format** можно использовать следующие дополнительные форматы.</span><span class="sxs-lookup"><span data-stu-id="ec517-204">Starting in PowerShell 5.0, you can use the following additional formats as values for the **Format** parameter.</span></span>

- <span data-ttu-id="ec517-205">**Филедате**.</span><span class="sxs-lookup"><span data-stu-id="ec517-205">**FileDate**.</span></span> <span data-ttu-id="ec517-206">Представление текущей даты в формате местного времени в файле или пути.</span><span class="sxs-lookup"><span data-stu-id="ec517-206">A file or path-friendly representation of the current date in local time.</span></span> <span data-ttu-id="ec517-207">Формат (с `yyyyMMdd` учетом регистра, с использованием 4-значного года, 2-значный месяц и день в 2 цифры).</span><span class="sxs-lookup"><span data-stu-id="ec517-207">The format is `yyyyMMdd` (case-sensitive, using a 4-digit year, 2-digit month, and 2-digit day).</span></span> <span data-ttu-id="ec517-208">Пример:</span><span class="sxs-lookup"><span data-stu-id="ec517-208">For example:</span></span>
  20190627.

- <span data-ttu-id="ec517-209">**Филедатеуниверсал**.</span><span class="sxs-lookup"><span data-stu-id="ec517-209">**FileDateUniversal**.</span></span> <span data-ttu-id="ec517-210">Представление текущей даты в формате UTC в виде файла или пути.</span><span class="sxs-lookup"><span data-stu-id="ec517-210">A file or path-friendly representation of the current date in universal time (UTC).</span></span> <span data-ttu-id="ec517-211">Формат (с `yyyyMMddZ` учетом регистра, с использованием 4-разрядного года, месяца, 2 цифры и буквы в `Z` качестве индикатора времени в формате UTC).</span><span class="sxs-lookup"><span data-stu-id="ec517-211">The format is `yyyyMMddZ` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, and the letter `Z` as the UTC indicator).</span></span> <span data-ttu-id="ec517-212">Например: 20190627Z.</span><span class="sxs-lookup"><span data-stu-id="ec517-212">For example: 20190627Z.</span></span>

- <span data-ttu-id="ec517-213">**Филедатетиме**.</span><span class="sxs-lookup"><span data-stu-id="ec517-213">**FileDateTime**.</span></span> <span data-ttu-id="ec517-214">Представление текущей даты и времени по местному времени в 24-часовом формате в виде файла или пути.</span><span class="sxs-lookup"><span data-stu-id="ec517-214">A file or path-friendly representation of the current date and time in local time, in 24-hour format.</span></span> <span data-ttu-id="ec517-215">Формат (с `yyyyMMddTHHmmssffff` учетом регистра, с использованием 4-разрядного года, 2-значный месяц, с двумя цифрами, буква в `T` качестве разделителя времени, 2-значный час, 2-значная минута, 2-значная секунда и 4-значная миллисекунда).</span><span class="sxs-lookup"><span data-stu-id="ec517-215">The format is `yyyyMMddTHHmmssffff` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, the letter `T` as a time separator, 2-digit hour, 2-digit minute, 2-digit second, and 4-digit millisecond).</span></span> <span data-ttu-id="ec517-216">Например: 20190627T0840107271.</span><span class="sxs-lookup"><span data-stu-id="ec517-216">For example: 20190627T0840107271.</span></span>

- <span data-ttu-id="ec517-217">**Филедатетимеуниверсал**.</span><span class="sxs-lookup"><span data-stu-id="ec517-217">**FileDateTimeUniversal**.</span></span> <span data-ttu-id="ec517-218">Представление текущей даты и времени в формате UTC в 24-часовом виде файла или пути.</span><span class="sxs-lookup"><span data-stu-id="ec517-218">A file or path-friendly representation of the current date and time in universal time (UTC), in 24-hour format.</span></span> <span data-ttu-id="ec517-219">Формат (с `yyyyMMddTHHmmssffffZ` учетом регистра, с использованием 4-разрядного года, 2-значного месяца, буквы в 2 цифры, буква в `T` качестве разделителя времени, 2-значный час, 2-значная минута, 2-значная секунда, 4-разрядная миллисекунда и букву в `Z` качестве индикатора времени в формате UTC).</span><span class="sxs-lookup"><span data-stu-id="ec517-219">The format is `yyyyMMddTHHmmssffffZ` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, the letter `T` as a time separator, 2-digit hour, 2-digit minute, 2-digit second, 4-digit millisecond, and the letter `Z` as the UTC indicator).</span></span> <span data-ttu-id="ec517-220">Например: 20190627T1540500718Z.</span><span class="sxs-lookup"><span data-stu-id="ec517-220">For example: 20190627T1540500718Z.</span></span>

```yaml
Type: System.String
Parameter Sets: net
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ec517-221">-Hour</span><span class="sxs-lookup"><span data-stu-id="ec517-221">-Hour</span></span>

<span data-ttu-id="ec517-222">Указывает выводимый час.</span><span class="sxs-lookup"><span data-stu-id="ec517-222">Specifies the hour that is displayed.</span></span> <span data-ttu-id="ec517-223">Введите значение от 0 до 23.</span><span class="sxs-lookup"><span data-stu-id="ec517-223">Enter a value from 0 to 23.</span></span>

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

### <span data-ttu-id="ec517-224">-Millisecond</span><span class="sxs-lookup"><span data-stu-id="ec517-224">-Millisecond</span></span>

<span data-ttu-id="ec517-225">Указывает миллисекунды в дате.</span><span class="sxs-lookup"><span data-stu-id="ec517-225">Specifies the milliseconds in the date.</span></span> <span data-ttu-id="ec517-226">Введите значение от 0 до 999.</span><span class="sxs-lookup"><span data-stu-id="ec517-226">Enter a value from 0 to 999.</span></span>

<span data-ttu-id="ec517-227">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="ec517-227">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="ec517-228">-Minute</span><span class="sxs-lookup"><span data-stu-id="ec517-228">-Minute</span></span>

<span data-ttu-id="ec517-229">Указывает выводимую минуту.</span><span class="sxs-lookup"><span data-stu-id="ec517-229">Specifies the minute that is displayed.</span></span> <span data-ttu-id="ec517-230">Введите значение от 0 до 59.</span><span class="sxs-lookup"><span data-stu-id="ec517-230">Enter a value from 0 to 59.</span></span>

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

### <span data-ttu-id="ec517-231">-Month</span><span class="sxs-lookup"><span data-stu-id="ec517-231">-Month</span></span>

<span data-ttu-id="ec517-232">Указывает выводимый месяц.</span><span class="sxs-lookup"><span data-stu-id="ec517-232">Specifies the month that is displayed.</span></span> <span data-ttu-id="ec517-233">Введите значение от 1 до 12.</span><span class="sxs-lookup"><span data-stu-id="ec517-233">Enter a value from 1 to 12.</span></span>

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

### <span data-ttu-id="ec517-234">-Second</span><span class="sxs-lookup"><span data-stu-id="ec517-234">-Second</span></span>

<span data-ttu-id="ec517-235">Указывает выводимую секунду.</span><span class="sxs-lookup"><span data-stu-id="ec517-235">Specifies the second that is displayed.</span></span> <span data-ttu-id="ec517-236">Введите значение от 0 до 59.</span><span class="sxs-lookup"><span data-stu-id="ec517-236">Enter a value from 0 to 59.</span></span>

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

### <span data-ttu-id="ec517-237">-UFormat</span><span class="sxs-lookup"><span data-stu-id="ec517-237">-UFormat</span></span>

<span data-ttu-id="ec517-238">Выводит дату и время в формате UNIX.</span><span class="sxs-lookup"><span data-stu-id="ec517-238">Displays the date and time in UNIX format.</span></span> <span data-ttu-id="ec517-239">Параметр **UFormat** выводит строковый объект.</span><span class="sxs-lookup"><span data-stu-id="ec517-239">The **UFormat** parameter outputs a string object.</span></span>

<span data-ttu-id="ec517-240">Спецификаторам **UFormat** предшествует знак процента (), например,, `%` `%m` `%d` и `%Y` .</span><span class="sxs-lookup"><span data-stu-id="ec517-240">**UFormat** specifiers are preceded by a percent sign (`%`), for example, `%m`, `%d`, and `%Y`.</span></span> <span data-ttu-id="ec517-241">В разделе " [Примечания](#notes) " содержится таблица допустимых **описателей UFormat**.</span><span class="sxs-lookup"><span data-stu-id="ec517-241">The [Notes](#notes) section contains a table of valid **UFormat specifiers**.</span></span>

<span data-ttu-id="ec517-242">При использовании параметра **UFormat** `Get-Date` получает только свойства объекта **DateTime** , необходимые для вывода даты.</span><span class="sxs-lookup"><span data-stu-id="ec517-242">When the **UFormat** parameter is used, `Get-Date` only gets the **DateTime** object's properties necessary to display the date.</span></span> <span data-ttu-id="ec517-243">Поэтому некоторые свойства и методы объекта **DateTime** могут быть недоступны.</span><span class="sxs-lookup"><span data-stu-id="ec517-243">As a result, some of the properties and methods of **DateTime** objects might not be available.</span></span>

```yaml
Type: System.String
Parameter Sets: UFormat
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ec517-244">-Year</span><span class="sxs-lookup"><span data-stu-id="ec517-244">-Year</span></span>

<span data-ttu-id="ec517-245">Указывает выводимый год.</span><span class="sxs-lookup"><span data-stu-id="ec517-245">Specifies the year that is displayed.</span></span> <span data-ttu-id="ec517-246">Введите значение от 1 до 9999.</span><span class="sxs-lookup"><span data-stu-id="ec517-246">Enter a value from 1 to 9999.</span></span>

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

### <span data-ttu-id="ec517-247">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="ec517-247">CommonParameters</span></span>

<span data-ttu-id="ec517-248">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ec517-248">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ec517-249">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ec517-249">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ec517-250">Входные данные</span><span class="sxs-lookup"><span data-stu-id="ec517-250">INPUTS</span></span>

### <span data-ttu-id="ec517-251">Входные данные конвейера</span><span class="sxs-lookup"><span data-stu-id="ec517-251">Pipeline input</span></span>

<span data-ttu-id="ec517-252">`Get-Date` принимает входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="ec517-252">`Get-Date` accepts pipeline input.</span></span> <span data-ttu-id="ec517-253">Например, `Get-ChildItem | Get-Date`.</span><span class="sxs-lookup"><span data-stu-id="ec517-253">For example, `Get-ChildItem | Get-Date`.</span></span>

## <span data-ttu-id="ec517-254">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="ec517-254">OUTPUTS</span></span>

### <span data-ttu-id="ec517-255">System.DateTime или System.String</span><span class="sxs-lookup"><span data-stu-id="ec517-255">System.DateTime or System.String</span></span>

<span data-ttu-id="ec517-256">`Get-Date` Возвращает объект **DateTime** , за исключением случаев, когда используются параметры **Format** и **UFormat** .</span><span class="sxs-lookup"><span data-stu-id="ec517-256">`Get-Date` returns a **DateTime** object except when the **Format** and **UFormat** parameters are used.</span></span> <span data-ttu-id="ec517-257">Параметры **Format** или **UFormat** возвращают **строковые** объекты.</span><span class="sxs-lookup"><span data-stu-id="ec517-257">The **Format** or **UFormat** parameters return **String** objects.</span></span>

<span data-ttu-id="ec517-258">Когда объект **DateTime** отправляется по конвейеру в командлет, например, при `Add-Content` ожидании ввода строки, PowerShell преобразует объект в **строковый** объект.</span><span class="sxs-lookup"><span data-stu-id="ec517-258">When a **DateTime** object is sent down the pipeline to a cmdlet such as `Add-Content` that expects string input, PowerShell converts the object to a **String** object.</span></span>

<span data-ttu-id="ec517-259">Метод `(Get-Date).ToString()` преобразует объект **DateTime** в объект **String** .</span><span class="sxs-lookup"><span data-stu-id="ec517-259">The method `(Get-Date).ToString()` converts a **DateTime** object a **String** object.</span></span>

<span data-ttu-id="ec517-260">Чтобы отобразить свойства и методы объекта, отправьте объект по конвейеру в `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="ec517-260">To display an object's properties and methods, send the object down the pipeline to `Get-Member`.</span></span>
<span data-ttu-id="ec517-261">Например, `Get-Date | Get-Member`.</span><span class="sxs-lookup"><span data-stu-id="ec517-261">For example, `Get-Date | Get-Member`.</span></span>

## <span data-ttu-id="ec517-262">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="ec517-262">NOTES</span></span>

<span data-ttu-id="ec517-263">Объекты **DateTime** имеют формат длинной даты и длительное время для национальной настройки системы.</span><span class="sxs-lookup"><span data-stu-id="ec517-263">**DateTime** objects are in long-date and long-time formats for the system locale.</span></span>

<span data-ttu-id="ec517-264">В следующей таблице показаны допустимые **описатели UFormat** .</span><span class="sxs-lookup"><span data-stu-id="ec517-264">The valid **UFormat specifiers** are displayed in the following table:</span></span>

| <span data-ttu-id="ec517-265">Описатель формата</span><span class="sxs-lookup"><span data-stu-id="ec517-265">Format specifier</span></span> |                                 <span data-ttu-id="ec517-266">Значение</span><span class="sxs-lookup"><span data-stu-id="ec517-266">Meaning</span></span>                     |         <span data-ttu-id="ec517-267">Пример</span><span class="sxs-lookup"><span data-stu-id="ec517-267">Example</span></span>          |
| ---- | ----------------------------------------------------------------------- | ------------------------ |
| `%A` | <span data-ttu-id="ec517-268">День недели — полное имя</span><span class="sxs-lookup"><span data-stu-id="ec517-268">Day of the week - full name</span></span>                                             | <span data-ttu-id="ec517-269">Понедельник</span><span class="sxs-lookup"><span data-stu-id="ec517-269">Monday</span></span>                   |
| `%a` | <span data-ttu-id="ec517-270">День в сокращенном названии недели</span><span class="sxs-lookup"><span data-stu-id="ec517-270">Day of the week - abbreviated name</span></span>                                      | <span data-ttu-id="ec517-271">Mon</span><span class="sxs-lookup"><span data-stu-id="ec517-271">Mon</span></span>                      |
| `%B` | <span data-ttu-id="ec517-272">Имя месяца — полное</span><span class="sxs-lookup"><span data-stu-id="ec517-272">Month name - full</span></span>                                                       | <span data-ttu-id="ec517-273">Январь</span><span class="sxs-lookup"><span data-stu-id="ec517-273">January</span></span>                  |
| `%b` | <span data-ttu-id="ec517-274">Название месяца — сокращенное</span><span class="sxs-lookup"><span data-stu-id="ec517-274">Month name - abbreviated</span></span>                                                | <span data-ttu-id="ec517-275">Январь</span><span class="sxs-lookup"><span data-stu-id="ec517-275">Jan</span></span>                      |
| `%C` | <span data-ttu-id="ec517-276">Век</span><span class="sxs-lookup"><span data-stu-id="ec517-276">Century</span></span>                                                                 | <span data-ttu-id="ec517-277">20 для 2019</span><span class="sxs-lookup"><span data-stu-id="ec517-277">20 for 2019</span></span>              |
| `%c` | <span data-ttu-id="ec517-278">Дата и время-сокращенные</span><span class="sxs-lookup"><span data-stu-id="ec517-278">Date and time - abbreviated</span></span>                                             | <span data-ttu-id="ec517-279">Четверг июня 27 08:44:18 2019</span><span class="sxs-lookup"><span data-stu-id="ec517-279">Thu Jun 27 08:44:18 2019</span></span> |
| `%D` | <span data-ttu-id="ec517-280">Дата в формате мм/дд/гг</span><span class="sxs-lookup"><span data-stu-id="ec517-280">Date in mm/dd/yy format</span></span>                                                 | <span data-ttu-id="ec517-281">06/27/19</span><span class="sxs-lookup"><span data-stu-id="ec517-281">06/27/19</span></span>                 |
| `%d` | <span data-ttu-id="ec517-282">День месяца-2 цифры</span><span class="sxs-lookup"><span data-stu-id="ec517-282">Day of the month - 2 digits</span></span>                                             | <span data-ttu-id="ec517-283">05</span><span class="sxs-lookup"><span data-stu-id="ec517-283">05</span></span>                       |
| `%e` | <span data-ttu-id="ec517-284">День месяца — предшествует пробел, если только одна цифра</span><span class="sxs-lookup"><span data-stu-id="ec517-284">Day of the month - preceded by a space if only a single digit</span></span>           | <span data-ttu-id="ec517-285">\<space\>5.0</span><span class="sxs-lookup"><span data-stu-id="ec517-285">\<space\>5</span></span>               |
| `%F` | <span data-ttu-id="ec517-286">Дата в формате гггг-мм-дд равна% Y-% m-% d (формат даты ISO 8601)</span><span class="sxs-lookup"><span data-stu-id="ec517-286">Date in YYYY-mm-dd format, equal to %Y-%m-%d (the ISO 8601 date format)</span></span> | <span data-ttu-id="ec517-287">2019-06-27</span><span class="sxs-lookup"><span data-stu-id="ec517-287">2019-06-27</span></span>               |
| `%G` | <span data-ttu-id="ec517-288">То же, что "Y"</span><span class="sxs-lookup"><span data-stu-id="ec517-288">Same as 'Y'</span></span>                                                             |                          |
| `%g` | <span data-ttu-id="ec517-289">То же, что "y"</span><span class="sxs-lookup"><span data-stu-id="ec517-289">Same as 'y'</span></span>                                                             |                          |
| `%H` | <span data-ttu-id="ec517-290">Час в 24-часовом формате</span><span class="sxs-lookup"><span data-stu-id="ec517-290">Hour in 24-hour format</span></span>                                                  | <span data-ttu-id="ec517-291">17</span><span class="sxs-lookup"><span data-stu-id="ec517-291">17</span></span>                       |
| `%h` | <span data-ttu-id="ec517-292">То же, что "b"</span><span class="sxs-lookup"><span data-stu-id="ec517-292">Same as 'b'</span></span>                                                             |                          |
| `%I` | <span data-ttu-id="ec517-293">Час в 12-часовом формате</span><span class="sxs-lookup"><span data-stu-id="ec517-293">Hour in 12-hour format</span></span>                                                  | <span data-ttu-id="ec517-294">05</span><span class="sxs-lookup"><span data-stu-id="ec517-294">05</span></span>                       |
| `%j` | <span data-ttu-id="ec517-295">День года</span><span class="sxs-lookup"><span data-stu-id="ec517-295">Day of the year</span></span>                                                         | <span data-ttu-id="ec517-296">1-366</span><span class="sxs-lookup"><span data-stu-id="ec517-296">1-366</span></span>                    |
| `%k` | <span data-ttu-id="ec517-297">То же, что "H"</span><span class="sxs-lookup"><span data-stu-id="ec517-297">Same as 'H'</span></span>                                                             |                          |
| `%l` | <span data-ttu-id="ec517-298">То же, что "I" (верхний регистр I)</span><span class="sxs-lookup"><span data-stu-id="ec517-298">Same as 'I' (Upper-case I)</span></span>                                              | <span data-ttu-id="ec517-299">05</span><span class="sxs-lookup"><span data-stu-id="ec517-299">05</span></span>                       |
| `%M` | <span data-ttu-id="ec517-300">Минуты</span><span class="sxs-lookup"><span data-stu-id="ec517-300">Minutes</span></span>                                                                 | <span data-ttu-id="ec517-301">35</span><span class="sxs-lookup"><span data-stu-id="ec517-301">35</span></span>                       |
| `%m` | <span data-ttu-id="ec517-302">Номер месяца.</span><span class="sxs-lookup"><span data-stu-id="ec517-302">Month number</span></span>                                                            | <span data-ttu-id="ec517-303">06</span><span class="sxs-lookup"><span data-stu-id="ec517-303">06</span></span>                       |
| `%n` | <span data-ttu-id="ec517-304">символ новой строки</span><span class="sxs-lookup"><span data-stu-id="ec517-304">newline character</span></span>                                                       |                          |
| `%p` | <span data-ttu-id="ec517-305">AM или PM</span><span class="sxs-lookup"><span data-stu-id="ec517-305">AM or PM</span></span>                                                                |                          |
| `%R` | <span data-ttu-id="ec517-306">Время в 24-часовом формате — нет секунд</span><span class="sxs-lookup"><span data-stu-id="ec517-306">Time in 24-hour format -no seconds</span></span>                                      | <span data-ttu-id="ec517-307">17:45</span><span class="sxs-lookup"><span data-stu-id="ec517-307">17:45</span></span>                    |
| `%r` | <span data-ttu-id="ec517-308">Время в 12-часовом формате</span><span class="sxs-lookup"><span data-stu-id="ec517-308">Time in 12-hour format</span></span>                                                  | <span data-ttu-id="ec517-309">09:15:36 AM</span><span class="sxs-lookup"><span data-stu-id="ec517-309">09:15:36 AM</span></span>              |
| `%S` | <span data-ttu-id="ec517-310">Секунды</span><span class="sxs-lookup"><span data-stu-id="ec517-310">Seconds</span></span>                                                                 | <span data-ttu-id="ec517-311">05</span><span class="sxs-lookup"><span data-stu-id="ec517-311">05</span></span>                       |
| `%s` | <span data-ttu-id="ec517-312">Секунды, прошедшие с 1 января 1970 00:00:00</span><span class="sxs-lookup"><span data-stu-id="ec517-312">Seconds elapsed since January 1, 1970 00:00:00</span></span>                          | <span data-ttu-id="ec517-313">1150451174</span><span class="sxs-lookup"><span data-stu-id="ec517-313">1150451174</span></span>               |
| `%t` | <span data-ttu-id="ec517-314">Символ горизонтальной табуляции</span><span class="sxs-lookup"><span data-stu-id="ec517-314">Horizontal tab character</span></span>                                                |                          |
| `%T` | <span data-ttu-id="ec517-315">Время в 24-часовом формате</span><span class="sxs-lookup"><span data-stu-id="ec517-315">Time in 24-hour format</span></span>                                                  | <span data-ttu-id="ec517-316">17:45:52</span><span class="sxs-lookup"><span data-stu-id="ec517-316">17:45:52</span></span>                 |
| `%U` | <span data-ttu-id="ec517-317">То же, что "W"</span><span class="sxs-lookup"><span data-stu-id="ec517-317">Same as 'W'</span></span>                                                             |                          |
| `%u` | <span data-ttu-id="ec517-318">День недели — номер</span><span class="sxs-lookup"><span data-stu-id="ec517-318">Day of the week - number</span></span>                                                | <span data-ttu-id="ec517-319">Воскресенье = 0</span><span class="sxs-lookup"><span data-stu-id="ec517-319">Sunday = 0</span></span>               |
| `%V` | <span data-ttu-id="ec517-320">Неделя года</span><span class="sxs-lookup"><span data-stu-id="ec517-320">Week of the year</span></span>                                                        | <span data-ttu-id="ec517-321">01-53</span><span class="sxs-lookup"><span data-stu-id="ec517-321">01-53</span></span>                    |
| `%w` | <span data-ttu-id="ec517-322">То же, что и "u"</span><span class="sxs-lookup"><span data-stu-id="ec517-322">Same as 'u'</span></span>                                                             |                          |
| `%W` | <span data-ttu-id="ec517-323">Неделя года</span><span class="sxs-lookup"><span data-stu-id="ec517-323">Week of the year</span></span>                                                        | <span data-ttu-id="ec517-324">00-52</span><span class="sxs-lookup"><span data-stu-id="ec517-324">00-52</span></span>                    |
| `%X` | <span data-ttu-id="ec517-325">То же, что 'T»</span><span class="sxs-lookup"><span data-stu-id="ec517-325">Same as 'T'</span></span>                                                             |                          |
| `%x` | <span data-ttu-id="ec517-326">Дата в стандартном формате для языкового стандарта</span><span class="sxs-lookup"><span data-stu-id="ec517-326">Date in standard format for locale</span></span>                                      | <span data-ttu-id="ec517-327">06/27/19 для английского языка США</span><span class="sxs-lookup"><span data-stu-id="ec517-327">06/27/19 for English-US</span></span>  |
| `%Y` | <span data-ttu-id="ec517-328">Год в 4-значном формате</span><span class="sxs-lookup"><span data-stu-id="ec517-328">Year in 4-digit format</span></span>                                                  | <span data-ttu-id="ec517-329">2019</span><span class="sxs-lookup"><span data-stu-id="ec517-329">2019</span></span>                     |
| `%y` | <span data-ttu-id="ec517-330">Год в формате 2 цифр</span><span class="sxs-lookup"><span data-stu-id="ec517-330">Year in 2-digit format</span></span>                                                  | <span data-ttu-id="ec517-331">19</span><span class="sxs-lookup"><span data-stu-id="ec517-331">19</span></span>                       |
| `%Z` | <span data-ttu-id="ec517-332">Смещение часового пояса от универсальной координаты времени (UTC)</span><span class="sxs-lookup"><span data-stu-id="ec517-332">Time zone offset from Universal Time Coordinate (UTC)</span></span>                   | <span data-ttu-id="ec517-333">-07</span><span class="sxs-lookup"><span data-stu-id="ec517-333">-07</span></span>                      |

## <span data-ttu-id="ec517-334">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ec517-334">RELATED LINKS</span></span>

[<span data-ttu-id="ec517-335">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="ec517-335">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="ec517-336">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="ec517-336">Get-Culture</span></span>](Get-Culture.md)

[<span data-ttu-id="ec517-337">Get-Member</span><span class="sxs-lookup"><span data-stu-id="ec517-337">Get-Member</span></span>](Get-Member.md)

[<span data-ttu-id="ec517-338">New-Item</span><span class="sxs-lookup"><span data-stu-id="ec517-338">New-Item</span></span>](../Microsoft.PowerShell.Management/New-Item.md)

[<span data-ttu-id="ec517-339">New-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="ec517-339">New-TimeSpan</span></span>](New-TimeSpan.md)

[<span data-ttu-id="ec517-340">Set-Date</span><span class="sxs-lookup"><span data-stu-id="ec517-340">Set-Date</span></span>](Set-Date.md)
