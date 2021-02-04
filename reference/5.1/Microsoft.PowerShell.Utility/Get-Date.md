---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Date
ms.openlocfilehash: bb7f169e0c01c73bb4e834375f341bf795e37ce7
ms.sourcegitcommit: f5986121386c81acddcf324eb0526d7d092bcc8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/20/2021
ms.locfileid: "98584661"
---
# <span data-ttu-id="631a8-103">Get-Date</span><span class="sxs-lookup"><span data-stu-id="631a8-103">Get-Date</span></span>

## <span data-ttu-id="631a8-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="631a8-104">SYNOPSIS</span></span>
<span data-ttu-id="631a8-105">Получает текущую дату и время.</span><span class="sxs-lookup"><span data-stu-id="631a8-105">Gets the current date and time.</span></span>

## <span data-ttu-id="631a8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="631a8-106">SYNTAX</span></span>

### <span data-ttu-id="631a8-107">net (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="631a8-107">net (Default)</span></span>

```
Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 [-Format <String>] [<CommonParameters>]
```

### <span data-ttu-id="631a8-108">UFormat</span><span class="sxs-lookup"><span data-stu-id="631a8-108">UFormat</span></span>

```
Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 [-UFormat <String>] [<CommonParameters>]
```

## <span data-ttu-id="631a8-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="631a8-109">DESCRIPTION</span></span>

<span data-ttu-id="631a8-110">`Get-Date`Командлет возвращает объект **DateTime** , представляющий текущую дату или указанную дату.</span><span class="sxs-lookup"><span data-stu-id="631a8-110">The `Get-Date` cmdlet gets a **DateTime** object that represents the current date or a date that you specify.</span></span> <span data-ttu-id="631a8-111">`Get-Date` может форматировать дату и время в нескольких форматах .NET и UNIX.</span><span class="sxs-lookup"><span data-stu-id="631a8-111">`Get-Date` can format the date and time in several .NET and UNIX formats.</span></span> <span data-ttu-id="631a8-112">Можно использовать `Get-Date` для создания строки символов даты или времени, а затем отправить строку другим командлетам или программам.</span><span class="sxs-lookup"><span data-stu-id="631a8-112">You can use `Get-Date` to generate a date or time character string, and then send the string to other cmdlets or programs.</span></span>

<span data-ttu-id="631a8-113">`Get-Date` использует параметры языка и региональных параметров компьютера для определения формата выходных данных.</span><span class="sxs-lookup"><span data-stu-id="631a8-113">`Get-Date` uses the computer's culture settings to determine how the output is formatted.</span></span> <span data-ttu-id="631a8-114">Чтобы просмотреть параметры компьютера, используйте `(Get-Culture).DateTimeFormat` .</span><span class="sxs-lookup"><span data-stu-id="631a8-114">To view your computer's settings, use `(Get-Culture).DateTimeFormat`.</span></span>

## <span data-ttu-id="631a8-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="631a8-115">EXAMPLES</span></span>

### <span data-ttu-id="631a8-116">Пример 1. Получение текущей даты и времени</span><span class="sxs-lookup"><span data-stu-id="631a8-116">Example 1: Get the current date and time</span></span>

<span data-ttu-id="631a8-117">В этом примере `Get-Date` выводит текущую системную дату и время.</span><span class="sxs-lookup"><span data-stu-id="631a8-117">In this example, `Get-Date` displays the current system date and time.</span></span> <span data-ttu-id="631a8-118">Выходные данные имеют формат длинной даты и длительное время.</span><span class="sxs-lookup"><span data-stu-id="631a8-118">The output is in the long-date and long-time formats.</span></span>

```powershell
Get-Date
```

```Output
Tuesday, June 25, 2019 14:53:32
```

### <span data-ttu-id="631a8-119">Пример 2. Получение элементов текущей даты и времени</span><span class="sxs-lookup"><span data-stu-id="631a8-119">Example 2: Get elements of the current date and time</span></span>

<span data-ttu-id="631a8-120">В этом примере показано, как использовать `Get-Date` для получения элемента даты или времени.</span><span class="sxs-lookup"><span data-stu-id="631a8-120">This example shows how to use `Get-Date` to get either the date or time element.</span></span> <span data-ttu-id="631a8-121">Параметр использует аргументы **Date**, **time** или **DateTime**.</span><span class="sxs-lookup"><span data-stu-id="631a8-121">The parameter uses the arguments **Date**, **Time**, or **DateTime**.</span></span>

```powershell
Get-Date -DisplayHint Date
```

```Output
Tuesday, June 25, 2019
```

<span data-ttu-id="631a8-122">`Get-Date` использует параметр **дисплайхинт** с аргументом **Date** , чтобы получить только дату.</span><span class="sxs-lookup"><span data-stu-id="631a8-122">`Get-Date` uses the **DisplayHint** parameter with the **Date** argument to get only the date.</span></span>

### <span data-ttu-id="631a8-123">Пример 3. Получение даты и времени с помощью описателя формата .NET</span><span class="sxs-lookup"><span data-stu-id="631a8-123">Example 3: Get the date and time with a .NET format specifier</span></span>

<span data-ttu-id="631a8-124">В этом примере используется описатель формата .NET для настройки формата вывода.</span><span class="sxs-lookup"><span data-stu-id="631a8-124">In this example, a .NET format specifier is used to customize the output's format.</span></span> <span data-ttu-id="631a8-125">Выходные данные представляют собой **строковый** объект.</span><span class="sxs-lookup"><span data-stu-id="631a8-125">The output is a **String** object.</span></span>

```powershell
Get-Date -Format "dddd MM/dd/yyyy HH:mm K"
```

```Output
Tuesday 06/25/2019 16:17 -07:00
```

<span data-ttu-id="631a8-126">`Get-Date` использует параметр **Format** для указания нескольких описателей формата.</span><span class="sxs-lookup"><span data-stu-id="631a8-126">`Get-Date` uses the **Format** parameter to specify several format specifiers.</span></span>

<span data-ttu-id="631a8-127">Описатели формата .NET, используемые в этом примере, определяются следующим образом:</span><span class="sxs-lookup"><span data-stu-id="631a8-127">The .NET format specifiers used in this example are defined as follows:</span></span>

| <span data-ttu-id="631a8-128">Описатель</span><span class="sxs-lookup"><span data-stu-id="631a8-128">Specifier</span></span> | <span data-ttu-id="631a8-129">Определение</span><span class="sxs-lookup"><span data-stu-id="631a8-129">Definition</span></span> |
| --- | --- |
| `dddd` | <span data-ttu-id="631a8-130">День недели — полное имя</span><span class="sxs-lookup"><span data-stu-id="631a8-130">Day of the week - full name</span></span> |
| `MM` | <span data-ttu-id="631a8-131">Номер месяца.</span><span class="sxs-lookup"><span data-stu-id="631a8-131">Month number</span></span> |
| `dd` | <span data-ttu-id="631a8-132">День месяца-2 цифры</span><span class="sxs-lookup"><span data-stu-id="631a8-132">Day of the month - 2 digits</span></span> |
| `yyyy` | <span data-ttu-id="631a8-133">Год в 4-значном формате</span><span class="sxs-lookup"><span data-stu-id="631a8-133">Year in 4-digit format</span></span> |
| `HH:mm` | <span data-ttu-id="631a8-134">Время в 24-часовом формате — нет секунд</span><span class="sxs-lookup"><span data-stu-id="631a8-134">Time in 24-hour format -no seconds</span></span> |
| `K` | <span data-ttu-id="631a8-135">Смещение часового пояса от универсальной координаты времени (UTC)</span><span class="sxs-lookup"><span data-stu-id="631a8-135">Time zone offset from Universal Time Coordinate (UTC)</span></span> |

<span data-ttu-id="631a8-136">Дополнительные сведения о спецификаторах формата .NET см. в разделе [строки настраиваемых форматов даты и времени](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span><span class="sxs-lookup"><span data-stu-id="631a8-136">For more information about .NET format specifiers, see [Custom date and time format strings](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span></span>

### <span data-ttu-id="631a8-137">Пример 4. Получение даты и времени с помощью описателя UFormat</span><span class="sxs-lookup"><span data-stu-id="631a8-137">Example 4: Get the date and time with a UFormat specifier</span></span>

<span data-ttu-id="631a8-138">В этом примере для настройки формата вывода используются несколько описателей формата **UFormat** .</span><span class="sxs-lookup"><span data-stu-id="631a8-138">In this example, several **UFormat** format specifiers are used to customize the output's format.</span></span>
<span data-ttu-id="631a8-139">Выходные данные представляют собой **строковый** объект.</span><span class="sxs-lookup"><span data-stu-id="631a8-139">The output is a **String** object.</span></span>

```powershell
Get-Date -UFormat "%A %m/%d/%Y %R %Z"
```

```Output
Tuesday 06/25/2019 16:19 -07
```

<span data-ttu-id="631a8-140">`Get-Date` использует параметр **UFormat** для указания нескольких описателей формата.</span><span class="sxs-lookup"><span data-stu-id="631a8-140">`Get-Date` uses the **UFormat** parameter to specify several format specifiers.</span></span>

<span data-ttu-id="631a8-141">Описатели формата **UFormat** , используемые в этом примере, определяются следующим образом:</span><span class="sxs-lookup"><span data-stu-id="631a8-141">The **UFormat** format specifiers used in this example are defined as follows:</span></span>

| <span data-ttu-id="631a8-142">Описатель</span><span class="sxs-lookup"><span data-stu-id="631a8-142">Specifier</span></span> | <span data-ttu-id="631a8-143">Определение</span><span class="sxs-lookup"><span data-stu-id="631a8-143">Definition</span></span> |
| --- | --- |
| `%A` | <span data-ttu-id="631a8-144">День недели — полное имя</span><span class="sxs-lookup"><span data-stu-id="631a8-144">Day of the week - full name</span></span> |
| `%m` | <span data-ttu-id="631a8-145">Номер месяца.</span><span class="sxs-lookup"><span data-stu-id="631a8-145">Month number</span></span> |
| `%d` | <span data-ttu-id="631a8-146">День месяца-2 цифры</span><span class="sxs-lookup"><span data-stu-id="631a8-146">Day of the month - 2 digits</span></span> |
| `%Y` | <span data-ttu-id="631a8-147">Год в 4-значном формате</span><span class="sxs-lookup"><span data-stu-id="631a8-147">Year in 4-digit format</span></span> |
| `%R` | <span data-ttu-id="631a8-148">Время в 24-часовом формате — нет секунд</span><span class="sxs-lookup"><span data-stu-id="631a8-148">Time in 24-hour format -no seconds</span></span> |
| `%Z` | <span data-ttu-id="631a8-149">Смещение часового пояса от универсальной координаты времени (UTC)</span><span class="sxs-lookup"><span data-stu-id="631a8-149">Time zone offset from Universal Time Coordinate (UTC)</span></span> |

<span data-ttu-id="631a8-150">Список допустимых описателей формата **UFormat** см. в разделе " [Примечания](#notes) ".</span><span class="sxs-lookup"><span data-stu-id="631a8-150">For a list of valid **UFormat** format specifiers, see the [Notes](#notes) section.</span></span>

### <span data-ttu-id="631a8-151">Пример 5. получение дня года для даты</span><span class="sxs-lookup"><span data-stu-id="631a8-151">Example 5: Get a date's day of the year</span></span>

<span data-ttu-id="631a8-152">В этом примере свойство используется для получения числового дня года.</span><span class="sxs-lookup"><span data-stu-id="631a8-152">In this example, a property is used to get the numeric day of the year.</span></span>

<span data-ttu-id="631a8-153">В григорианском календаре 365 дней, за исключением високосных лет, имеющих 366 дней.</span><span class="sxs-lookup"><span data-stu-id="631a8-153">The Gregorian calendar has 365 days, except for leap years that have 366 days.</span></span> <span data-ttu-id="631a8-154">Например, 31 декабря 2020 — это день 366.</span><span class="sxs-lookup"><span data-stu-id="631a8-154">For example, December 31, 2020 is day 366.</span></span>

```powershell
(Get-Date -Year 2020 -Month 12 -Day 31).DayOfYear
```

```Output
366
```

<span data-ttu-id="631a8-155">`Get-Date` использует три параметра для указания даты: **год**, **месяц** и **день**.</span><span class="sxs-lookup"><span data-stu-id="631a8-155">`Get-Date` uses three parameters to specify the date: **Year**, **Month**, and **Day**.</span></span> <span data-ttu-id="631a8-156">Команда заключена в круглые скобки, поэтому результат вычисляется свойством **DayofYear** .</span><span class="sxs-lookup"><span data-stu-id="631a8-156">The command is wrapped with parentheses so that the result is evaluated by the **DayofYear** property.</span></span>

### <span data-ttu-id="631a8-157">Пример 6. Проверка того, скорректирована ли дата на летнее время</span><span class="sxs-lookup"><span data-stu-id="631a8-157">Example 6: Check if a date is adjusted for daylight savings time</span></span>

<span data-ttu-id="631a8-158">В этом примере используется логический метод для проверки, корректируется ли дата на летнее время.</span><span class="sxs-lookup"><span data-stu-id="631a8-158">This example uses a boolean method to verify if a date is adjusted by daylight savings time.</span></span>

```powershell
$DST = Get-Date
$DST.IsDaylightSavingTime()
```

```Output
True
```

<span data-ttu-id="631a8-159">Переменная, `$DST` в которой хранится результат `Get-Date` .</span><span class="sxs-lookup"><span data-stu-id="631a8-159">A variable, `$DST` stores the result of `Get-Date`.</span></span> <span data-ttu-id="631a8-160">`$DST` проверяет, корректируется ли дата на летнее время, с помощью метода **исдайлигхтсавингтиме** .</span><span class="sxs-lookup"><span data-stu-id="631a8-160">`$DST` uses the **IsDaylightSavingTime** method to test if the date is adjusted for daylight savings time.</span></span>

### <span data-ttu-id="631a8-161">Пример 7. Преобразование текущего времени в время в формате UTC</span><span class="sxs-lookup"><span data-stu-id="631a8-161">Example 7: Convert the current time to UTC time</span></span>

<span data-ttu-id="631a8-162">В этом примере текущее время преобразуется в время в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="631a8-162">In this example, the current time is converted to UTC time.</span></span> <span data-ttu-id="631a8-163">Для преобразования времени используется смещение в формате UTC для языкового стандарта системы.</span><span class="sxs-lookup"><span data-stu-id="631a8-163">The UTC offset for the system's locale is used to convert the time.</span></span> <span data-ttu-id="631a8-164">В таблице в разделе " [Примечания](#notes) " перечислены допустимые описатели формата **UFormat** .</span><span class="sxs-lookup"><span data-stu-id="631a8-164">A table in the [Notes](#notes) section lists the valid **UFormat** format specifiers.</span></span>

```powershell
Get-Date -UFormat "%A %B/%d/%Y %T %Z"
$Time = Get-Date
$Time.ToUniversalTime()
```

```Output
Wednesday June/26/2019 10:45:26 -07

Wednesday, June 26, 2019 17:45:26
```

<span data-ttu-id="631a8-165">`Get-Date` использует параметр **UFormat** с описателями формата для вывода текущей системной даты и времени.</span><span class="sxs-lookup"><span data-stu-id="631a8-165">`Get-Date` uses the **UFormat** parameter with format specifiers to display the current system date and time.</span></span> <span data-ttu-id="631a8-166">Описатель формата **% Z** представляет смещение в формате UTC, равное **-07**.</span><span class="sxs-lookup"><span data-stu-id="631a8-166">The format specifier **%Z** represents the UTC offset of **-07**.</span></span>

<span data-ttu-id="631a8-167">`$Time`Переменная хранит текущую системную дату и время.</span><span class="sxs-lookup"><span data-stu-id="631a8-167">The `$Time` variable stores the current system date and time.</span></span> <span data-ttu-id="631a8-168">`$Time` использует метод **ToUniversalTime ()** для преобразования времени на основе смещения UTC компьютера.</span><span class="sxs-lookup"><span data-stu-id="631a8-168">`$Time` uses the **ToUniversalTime()** method to convert the time based on the computer's UTC offset.</span></span>

### <span data-ttu-id="631a8-169">Пример 8. Создание метки времени</span><span class="sxs-lookup"><span data-stu-id="631a8-169">Example 8: Create a timestamp</span></span>

<span data-ttu-id="631a8-170">В этом примере описатель формата создает объект **строки** метки времени для имени каталога.</span><span class="sxs-lookup"><span data-stu-id="631a8-170">In this example, a format specifier creates a timestamp **String** object for a directory name.</span></span> <span data-ttu-id="631a8-171">Метка времени включает дату, время и смещение в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="631a8-171">The timestamp includes the date, time, and UTC offset.</span></span>

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

<span data-ttu-id="631a8-172">`$timestamp`Переменная хранит результаты выполнения `Get-Date` команды.</span><span class="sxs-lookup"><span data-stu-id="631a8-172">The `$timestamp` variable stores the results of a `Get-Date` command.</span></span> <span data-ttu-id="631a8-173">`Get-Date` использует параметр **Format** с описателем формата "нижний регистр" `o` для создания объекта **строки** метки времени.</span><span class="sxs-lookup"><span data-stu-id="631a8-173">`Get-Date` uses the **Format** parameter with the format specifier of lowercase `o` to create a timestamp **String** object.</span></span> <span data-ttu-id="631a8-174">Объект отправляется по конвейеру в `ForEach-Object` .</span><span class="sxs-lookup"><span data-stu-id="631a8-174">The object is sent down the pipeline to `ForEach-Object`.</span></span> <span data-ttu-id="631a8-175">Блок **ScriptBlock** содержит `$_` переменную, представляющую текущий объект конвейера.</span><span class="sxs-lookup"><span data-stu-id="631a8-175">A **ScriptBlock** contains the `$_` variable that represents the current pipeline object.</span></span> <span data-ttu-id="631a8-176">Строка метки времени разделяются двоеточиями, которые заменяются точками.</span><span class="sxs-lookup"><span data-stu-id="631a8-176">The timestamp string is delimited by colons that are replaced by periods.</span></span>

<span data-ttu-id="631a8-177">`New-Item` использует параметр **path** для указания расположения нового каталога.</span><span class="sxs-lookup"><span data-stu-id="631a8-177">`New-Item` uses the **Path** parameter to specify the location for a new directory.</span></span> <span data-ttu-id="631a8-178">Путь включает `$timestamp` переменную в качестве имени каталога.</span><span class="sxs-lookup"><span data-stu-id="631a8-178">The path includes the `$timestamp` variable as the directory name.</span></span> <span data-ttu-id="631a8-179">Параметр **типа** указывает, что каталог создан.</span><span class="sxs-lookup"><span data-stu-id="631a8-179">The **Type** parameter specifies that a directory is created.</span></span>

## <span data-ttu-id="631a8-180">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="631a8-180">PARAMETERS</span></span>

### <span data-ttu-id="631a8-181">-Date</span><span class="sxs-lookup"><span data-stu-id="631a8-181">-Date</span></span>

<span data-ttu-id="631a8-182">Указывает дату и время.</span><span class="sxs-lookup"><span data-stu-id="631a8-182">Specifies a date and time.</span></span> <span data-ttu-id="631a8-183">Время является необязательным и, если не указано, возвращает 00:00:00.</span><span class="sxs-lookup"><span data-stu-id="631a8-183">Time is optional and if not specified, returns 00:00:00.</span></span>

<span data-ttu-id="631a8-184">Введите дату и время в формате, стандартном для национальной настройки системы.</span><span class="sxs-lookup"><span data-stu-id="631a8-184">Enter the date and time in a format that is standard for the system locale.</span></span>

<span data-ttu-id="631a8-185">Например, на английском языке США:</span><span class="sxs-lookup"><span data-stu-id="631a8-185">For example, in US English:</span></span>

<span data-ttu-id="631a8-186">`Get-Date -Date "6/25/2019 12:30:22"` Возвращает вторник, 25 июня 2019 12:30:22</span><span class="sxs-lookup"><span data-stu-id="631a8-186">`Get-Date -Date "6/25/2019 12:30:22"` returns Tuesday, June 25, 2019 12:30:22</span></span>

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

### <span data-ttu-id="631a8-187">-Day</span><span class="sxs-lookup"><span data-stu-id="631a8-187">-Day</span></span>

<span data-ttu-id="631a8-188">Указывает выводимый день месяца.</span><span class="sxs-lookup"><span data-stu-id="631a8-188">Specifies the day of the month that is displayed.</span></span> <span data-ttu-id="631a8-189">Введите значение от 1 до 31.</span><span class="sxs-lookup"><span data-stu-id="631a8-189">Enter a value from 1 to 31.</span></span>

<span data-ttu-id="631a8-190">Если указанное значение больше числа дней в месяце, PowerShell добавляет число дней в месяц.</span><span class="sxs-lookup"><span data-stu-id="631a8-190">If the specified value is greater than the number of days in a month, PowerShell adds the number of days to the month.</span></span> <span data-ttu-id="631a8-191">Например, `Get-Date -Month 2 -Day 31` отображается **3 марта**, а не **31 февраля**.</span><span class="sxs-lookup"><span data-stu-id="631a8-191">For example, `Get-Date -Month 2 -Day 31` displays **March 3**, not **February 31**.</span></span>

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

### <span data-ttu-id="631a8-192">-DisplayHint</span><span class="sxs-lookup"><span data-stu-id="631a8-192">-DisplayHint</span></span>

<span data-ttu-id="631a8-193">Определяет, какие элементы даты и времени будут отображаться.</span><span class="sxs-lookup"><span data-stu-id="631a8-193">Determines which elements of the date and time are displayed.</span></span>

<span data-ttu-id="631a8-194">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="631a8-194">The accepted values are as follows:</span></span>

- <span data-ttu-id="631a8-195">**Date:** отображается только дата;</span><span class="sxs-lookup"><span data-stu-id="631a8-195">**Date**: displays only the date</span></span>
- <span data-ttu-id="631a8-196">**Time:** отображается только время;</span><span class="sxs-lookup"><span data-stu-id="631a8-196">**Time**: displays only the time</span></span>
- <span data-ttu-id="631a8-197">**DateTime:** отображаются дата и время.</span><span class="sxs-lookup"><span data-stu-id="631a8-197">**DateTime**: displays the date and time</span></span>

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

### <span data-ttu-id="631a8-198">-Format</span><span class="sxs-lookup"><span data-stu-id="631a8-198">-Format</span></span>

<span data-ttu-id="631a8-199">Выводит дату и время в формате Microsoft .NET Framework, определяемом спецификатором формата.</span><span class="sxs-lookup"><span data-stu-id="631a8-199">Displays the date and time in the Microsoft .NET Framework format indicated by the format specifier.</span></span>
<span data-ttu-id="631a8-200">Параметр **Format** выводит **строковый** объект.</span><span class="sxs-lookup"><span data-stu-id="631a8-200">The **Format** parameter outputs a **String** object.</span></span>

<span data-ttu-id="631a8-201">Список доступных описателей формата .NET см. в разделе [строки настраиваемых форматов даты и времени](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span><span class="sxs-lookup"><span data-stu-id="631a8-201">For a list of available .NET format specifiers, see [Custom date and time format strings](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span></span>

<span data-ttu-id="631a8-202">При использовании параметра **Format** `Get-Date` получает только свойства объекта **DateTime** , необходимые для вывода даты.</span><span class="sxs-lookup"><span data-stu-id="631a8-202">When the **Format** parameter is used, `Get-Date` only gets the **DateTime** object's properties necessary to display the date.</span></span> <span data-ttu-id="631a8-203">Поэтому некоторые свойства и методы объекта **DateTime** могут быть недоступны.</span><span class="sxs-lookup"><span data-stu-id="631a8-203">As a result, some of the properties and methods of **DateTime** objects might not be available.</span></span>

<span data-ttu-id="631a8-204">Начиная с PowerShell 5,0, в качестве значений параметра **Format** можно использовать следующие дополнительные форматы.</span><span class="sxs-lookup"><span data-stu-id="631a8-204">Starting in PowerShell 5.0, you can use the following additional formats as values for the **Format** parameter.</span></span>

- <span data-ttu-id="631a8-205">**Филедате**.</span><span class="sxs-lookup"><span data-stu-id="631a8-205">**FileDate**.</span></span> <span data-ttu-id="631a8-206">Представление текущей даты в формате местного времени в файле или пути.</span><span class="sxs-lookup"><span data-stu-id="631a8-206">A file or path-friendly representation of the current date in local time.</span></span> <span data-ttu-id="631a8-207">Формат (с `yyyyMMdd` учетом регистра, с использованием 4-значного года, 2-значный месяц и день в 2 цифры).</span><span class="sxs-lookup"><span data-stu-id="631a8-207">The format is `yyyyMMdd` (case-sensitive, using a 4-digit year, 2-digit month, and 2-digit day).</span></span> <span data-ttu-id="631a8-208">Пример:</span><span class="sxs-lookup"><span data-stu-id="631a8-208">For example:</span></span>
  20190627.

- <span data-ttu-id="631a8-209">**Филедатеуниверсал**.</span><span class="sxs-lookup"><span data-stu-id="631a8-209">**FileDateUniversal**.</span></span> <span data-ttu-id="631a8-210">Представление текущей даты в формате UTC в виде файла или пути.</span><span class="sxs-lookup"><span data-stu-id="631a8-210">A file or path-friendly representation of the current date in universal time (UTC).</span></span> <span data-ttu-id="631a8-211">Формат (с `yyyyMMddZ` учетом регистра, с использованием 4-разрядного года, месяца, 2 цифры и буквы в `Z` качестве индикатора времени в формате UTC).</span><span class="sxs-lookup"><span data-stu-id="631a8-211">The format is `yyyyMMddZ` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, and the letter `Z` as the UTC indicator).</span></span> <span data-ttu-id="631a8-212">Например: 20190627Z.</span><span class="sxs-lookup"><span data-stu-id="631a8-212">For example: 20190627Z.</span></span>

- <span data-ttu-id="631a8-213">**Филедатетиме**.</span><span class="sxs-lookup"><span data-stu-id="631a8-213">**FileDateTime**.</span></span> <span data-ttu-id="631a8-214">Представление текущей даты и времени по местному времени в 24-часовом формате в виде файла или пути.</span><span class="sxs-lookup"><span data-stu-id="631a8-214">A file or path-friendly representation of the current date and time in local time, in 24-hour format.</span></span> <span data-ttu-id="631a8-215">Формат (с `yyyyMMddTHHmmssffff` учетом регистра, с использованием 4-разрядного года, 2-значный месяц, с двумя цифрами, буква в `T` качестве разделителя времени, 2-значный час, 2-значная минута, 2-значная секунда и 4-значная миллисекунда).</span><span class="sxs-lookup"><span data-stu-id="631a8-215">The format is `yyyyMMddTHHmmssffff` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, the letter `T` as a time separator, 2-digit hour, 2-digit minute, 2-digit second, and 4-digit millisecond).</span></span> <span data-ttu-id="631a8-216">Например: 20190627T0840107271.</span><span class="sxs-lookup"><span data-stu-id="631a8-216">For example: 20190627T0840107271.</span></span>

- <span data-ttu-id="631a8-217">**Филедатетимеуниверсал**.</span><span class="sxs-lookup"><span data-stu-id="631a8-217">**FileDateTimeUniversal**.</span></span> <span data-ttu-id="631a8-218">Представление текущей даты и времени в формате UTC в 24-часовом виде файла или пути.</span><span class="sxs-lookup"><span data-stu-id="631a8-218">A file or path-friendly representation of the current date and time in universal time (UTC), in 24-hour format.</span></span> <span data-ttu-id="631a8-219">Формат (с `yyyyMMddTHHmmssffffZ` учетом регистра, с использованием 4-разрядного года, 2-значного месяца, буквы в 2 цифры, буква в `T` качестве разделителя времени, 2-значный час, 2-значная минута, 2-значная секунда, 4-разрядная миллисекунда и букву в `Z` качестве индикатора времени в формате UTC).</span><span class="sxs-lookup"><span data-stu-id="631a8-219">The format is `yyyyMMddTHHmmssffffZ` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, the letter `T` as a time separator, 2-digit hour, 2-digit minute, 2-digit second, 4-digit millisecond, and the letter `Z` as the UTC indicator).</span></span> <span data-ttu-id="631a8-220">Например: 20190627T1540500718Z.</span><span class="sxs-lookup"><span data-stu-id="631a8-220">For example: 20190627T1540500718Z.</span></span>

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

### <span data-ttu-id="631a8-221">-Hour</span><span class="sxs-lookup"><span data-stu-id="631a8-221">-Hour</span></span>

<span data-ttu-id="631a8-222">Указывает выводимый час.</span><span class="sxs-lookup"><span data-stu-id="631a8-222">Specifies the hour that is displayed.</span></span> <span data-ttu-id="631a8-223">Введите значение от 0 до 23.</span><span class="sxs-lookup"><span data-stu-id="631a8-223">Enter a value from 0 to 23.</span></span>

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

### <span data-ttu-id="631a8-224">-Millisecond</span><span class="sxs-lookup"><span data-stu-id="631a8-224">-Millisecond</span></span>

<span data-ttu-id="631a8-225">Указывает миллисекунды в дате.</span><span class="sxs-lookup"><span data-stu-id="631a8-225">Specifies the milliseconds in the date.</span></span> <span data-ttu-id="631a8-226">Введите значение от 0 до 999.</span><span class="sxs-lookup"><span data-stu-id="631a8-226">Enter a value from 0 to 999.</span></span>

<span data-ttu-id="631a8-227">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="631a8-227">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="631a8-228">-Minute</span><span class="sxs-lookup"><span data-stu-id="631a8-228">-Minute</span></span>

<span data-ttu-id="631a8-229">Указывает выводимую минуту.</span><span class="sxs-lookup"><span data-stu-id="631a8-229">Specifies the minute that is displayed.</span></span> <span data-ttu-id="631a8-230">Введите значение от 0 до 59.</span><span class="sxs-lookup"><span data-stu-id="631a8-230">Enter a value from 0 to 59.</span></span>

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

### <span data-ttu-id="631a8-231">-Month</span><span class="sxs-lookup"><span data-stu-id="631a8-231">-Month</span></span>

<span data-ttu-id="631a8-232">Указывает выводимый месяц.</span><span class="sxs-lookup"><span data-stu-id="631a8-232">Specifies the month that is displayed.</span></span> <span data-ttu-id="631a8-233">Введите значение от 1 до 12.</span><span class="sxs-lookup"><span data-stu-id="631a8-233">Enter a value from 1 to 12.</span></span>

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

### <span data-ttu-id="631a8-234">-Second</span><span class="sxs-lookup"><span data-stu-id="631a8-234">-Second</span></span>

<span data-ttu-id="631a8-235">Указывает выводимую секунду.</span><span class="sxs-lookup"><span data-stu-id="631a8-235">Specifies the second that is displayed.</span></span> <span data-ttu-id="631a8-236">Введите значение от 0 до 59.</span><span class="sxs-lookup"><span data-stu-id="631a8-236">Enter a value from 0 to 59.</span></span>

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

### <span data-ttu-id="631a8-237">-UFormat</span><span class="sxs-lookup"><span data-stu-id="631a8-237">-UFormat</span></span>

<span data-ttu-id="631a8-238">Выводит дату и время в формате UNIX.</span><span class="sxs-lookup"><span data-stu-id="631a8-238">Displays the date and time in UNIX format.</span></span> <span data-ttu-id="631a8-239">Параметр **UFormat** выводит строковый объект.</span><span class="sxs-lookup"><span data-stu-id="631a8-239">The **UFormat** parameter outputs a string object.</span></span>

<span data-ttu-id="631a8-240">Спецификаторам **UFormat** предшествует знак процента (), например,, `%` `%m` `%d` и `%Y` .</span><span class="sxs-lookup"><span data-stu-id="631a8-240">**UFormat** specifiers are preceded by a percent sign (`%`), for example, `%m`, `%d`, and `%Y`.</span></span> <span data-ttu-id="631a8-241">В разделе " [Примечания](#notes) " содержится таблица допустимых **описателей UFormat**.</span><span class="sxs-lookup"><span data-stu-id="631a8-241">The [Notes](#notes) section contains a table of valid **UFormat specifiers**.</span></span>

<span data-ttu-id="631a8-242">При использовании параметра **UFormat** `Get-Date` получает только свойства объекта **DateTime** , необходимые для вывода даты.</span><span class="sxs-lookup"><span data-stu-id="631a8-242">When the **UFormat** parameter is used, `Get-Date` only gets the **DateTime** object's properties necessary to display the date.</span></span> <span data-ttu-id="631a8-243">Поэтому некоторые свойства и методы объекта **DateTime** могут быть недоступны.</span><span class="sxs-lookup"><span data-stu-id="631a8-243">As a result, some of the properties and methods of **DateTime** objects might not be available.</span></span>

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

### <span data-ttu-id="631a8-244">-Year</span><span class="sxs-lookup"><span data-stu-id="631a8-244">-Year</span></span>

<span data-ttu-id="631a8-245">Указывает выводимый год.</span><span class="sxs-lookup"><span data-stu-id="631a8-245">Specifies the year that is displayed.</span></span> <span data-ttu-id="631a8-246">Введите значение от 1 до 9999.</span><span class="sxs-lookup"><span data-stu-id="631a8-246">Enter a value from 1 to 9999.</span></span>

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

### <span data-ttu-id="631a8-247">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="631a8-247">CommonParameters</span></span>

<span data-ttu-id="631a8-248">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="631a8-248">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="631a8-249">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="631a8-249">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="631a8-250">Входные данные</span><span class="sxs-lookup"><span data-stu-id="631a8-250">INPUTS</span></span>

### <span data-ttu-id="631a8-251">Входные данные конвейера</span><span class="sxs-lookup"><span data-stu-id="631a8-251">Pipeline input</span></span>

<span data-ttu-id="631a8-252">`Get-Date` принимает входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="631a8-252">`Get-Date` accepts pipeline input.</span></span> <span data-ttu-id="631a8-253">Например, `Get-ChildItem | Get-Date`.</span><span class="sxs-lookup"><span data-stu-id="631a8-253">For example, `Get-ChildItem | Get-Date`.</span></span>

## <span data-ttu-id="631a8-254">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="631a8-254">OUTPUTS</span></span>

### <span data-ttu-id="631a8-255">System.DateTime или System.String</span><span class="sxs-lookup"><span data-stu-id="631a8-255">System.DateTime or System.String</span></span>

<span data-ttu-id="631a8-256">`Get-Date` Возвращает объект **DateTime** , за исключением случаев, когда используются параметры **Format** и **UFormat** .</span><span class="sxs-lookup"><span data-stu-id="631a8-256">`Get-Date` returns a **DateTime** object except when the **Format** and **UFormat** parameters are used.</span></span> <span data-ttu-id="631a8-257">Параметры **Format** или **UFormat** возвращают **строковые** объекты.</span><span class="sxs-lookup"><span data-stu-id="631a8-257">The **Format** or **UFormat** parameters return **String** objects.</span></span>

<span data-ttu-id="631a8-258">Когда объект **DateTime** отправляется по конвейеру в командлет, например, при `Add-Content` ожидании ввода строки, PowerShell преобразует объект в **строковый** объект.</span><span class="sxs-lookup"><span data-stu-id="631a8-258">When a **DateTime** object is sent down the pipeline to a cmdlet such as `Add-Content` that expects string input, PowerShell converts the object to a **String** object.</span></span>

<span data-ttu-id="631a8-259">Метод `(Get-Date).ToString()` преобразует объект **DateTime** в объект **String** .</span><span class="sxs-lookup"><span data-stu-id="631a8-259">The method `(Get-Date).ToString()` converts a **DateTime** object a **String** object.</span></span>

<span data-ttu-id="631a8-260">Чтобы отобразить свойства и методы объекта, отправьте объект по конвейеру в `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="631a8-260">To display an object's properties and methods, send the object down the pipeline to `Get-Member`.</span></span>
<span data-ttu-id="631a8-261">Например, `Get-Date | Get-Member`.</span><span class="sxs-lookup"><span data-stu-id="631a8-261">For example, `Get-Date | Get-Member`.</span></span>

## <span data-ttu-id="631a8-262">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="631a8-262">NOTES</span></span>

<span data-ttu-id="631a8-263">Объекты **DateTime** имеют формат длинной даты и длительное время для национальной настройки системы.</span><span class="sxs-lookup"><span data-stu-id="631a8-263">**DateTime** objects are in long-date and long-time formats for the system locale.</span></span>

<span data-ttu-id="631a8-264">В следующей таблице показаны допустимые **описатели UFormat** .</span><span class="sxs-lookup"><span data-stu-id="631a8-264">The valid **UFormat specifiers** are displayed in the following table:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="631a8-265">В более новых версиях PowerShell добавляются дополнительные описатели **UFormat** .</span><span class="sxs-lookup"><span data-stu-id="631a8-265">Additional **UFormat** specifiers are added in newer versions of PowerShell.</span></span> <span data-ttu-id="631a8-266">Например, `%F` был добавлен в powershell 6,2, поэтому он недоступен в Windows powershell 5,1 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="631a8-266">For example, `%F` was added in PowerShell 6.2, so it isn't available in Windows PowerShell 5.1 or older.</span></span> <span data-ttu-id="631a8-267">Это следует учитывать при использовании описателей **UFormat** в сценариях, предназначенных для выполнения в нескольких версиях PowerShell.</span><span class="sxs-lookup"><span data-stu-id="631a8-267">Keep this in mind when using **UFormat** specifiers in scripts designed to be run on multiple versions of PowerShell.</span></span>

| <span data-ttu-id="631a8-268">Описатель формата</span><span class="sxs-lookup"><span data-stu-id="631a8-268">Format specifier</span></span> |                                 <span data-ttu-id="631a8-269">Значение</span><span class="sxs-lookup"><span data-stu-id="631a8-269">Meaning</span></span>                     |         <span data-ttu-id="631a8-270">Пример</span><span class="sxs-lookup"><span data-stu-id="631a8-270">Example</span></span>          |
| ---- | ----------------------------------------------------------------------- | ------------------------ |
| `%A` | <span data-ttu-id="631a8-271">День недели — полное имя</span><span class="sxs-lookup"><span data-stu-id="631a8-271">Day of the week - full name</span></span>                                             | <span data-ttu-id="631a8-272">Понедельник</span><span class="sxs-lookup"><span data-stu-id="631a8-272">Monday</span></span>                   |
| `%a` | <span data-ttu-id="631a8-273">День в сокращенном названии недели</span><span class="sxs-lookup"><span data-stu-id="631a8-273">Day of the week - abbreviated name</span></span>                                      | <span data-ttu-id="631a8-274">Mon</span><span class="sxs-lookup"><span data-stu-id="631a8-274">Mon</span></span>                      |
| `%B` | <span data-ttu-id="631a8-275">Имя месяца — полное</span><span class="sxs-lookup"><span data-stu-id="631a8-275">Month name - full</span></span>                                                       | <span data-ttu-id="631a8-276">Январь</span><span class="sxs-lookup"><span data-stu-id="631a8-276">January</span></span>                  |
| `%b` | <span data-ttu-id="631a8-277">Название месяца — сокращенное</span><span class="sxs-lookup"><span data-stu-id="631a8-277">Month name - abbreviated</span></span>                                                | <span data-ttu-id="631a8-278">Январь</span><span class="sxs-lookup"><span data-stu-id="631a8-278">Jan</span></span>                      |
| `%C` | <span data-ttu-id="631a8-279">Век</span><span class="sxs-lookup"><span data-stu-id="631a8-279">Century</span></span>                                                                 | <span data-ttu-id="631a8-280">20 для 2019</span><span class="sxs-lookup"><span data-stu-id="631a8-280">20 for 2019</span></span>              |
| `%c` | <span data-ttu-id="631a8-281">Дата и время-сокращенные</span><span class="sxs-lookup"><span data-stu-id="631a8-281">Date and time - abbreviated</span></span>                                             | <span data-ttu-id="631a8-282">Четверг июня 27 08:44:18 2019</span><span class="sxs-lookup"><span data-stu-id="631a8-282">Thu Jun 27 08:44:18 2019</span></span> |
| `%D` | <span data-ttu-id="631a8-283">Дата в формате мм/дд/гг</span><span class="sxs-lookup"><span data-stu-id="631a8-283">Date in mm/dd/yy format</span></span>                                                 | <span data-ttu-id="631a8-284">06/27/19</span><span class="sxs-lookup"><span data-stu-id="631a8-284">06/27/19</span></span>                 |
| `%d` | <span data-ttu-id="631a8-285">День месяца-2 цифры</span><span class="sxs-lookup"><span data-stu-id="631a8-285">Day of the month - 2 digits</span></span>                                             | <span data-ttu-id="631a8-286">05</span><span class="sxs-lookup"><span data-stu-id="631a8-286">05</span></span>                       |
| `%e` | <span data-ttu-id="631a8-287">День месяца — предшествует пробел, если только одна цифра</span><span class="sxs-lookup"><span data-stu-id="631a8-287">Day of the month - preceded by a space if only a single digit</span></span>           | <span data-ttu-id="631a8-288">\<space\>5.0</span><span class="sxs-lookup"><span data-stu-id="631a8-288">\<space\>5</span></span>               |
| `%G` | <span data-ttu-id="631a8-289">То же, что "Y"</span><span class="sxs-lookup"><span data-stu-id="631a8-289">Same as 'Y'</span></span>                                                             |                          |
| `%g` | <span data-ttu-id="631a8-290">То же, что "y"</span><span class="sxs-lookup"><span data-stu-id="631a8-290">Same as 'y'</span></span>                                                             |                          |
| `%H` | <span data-ttu-id="631a8-291">Час в 24-часовом формате</span><span class="sxs-lookup"><span data-stu-id="631a8-291">Hour in 24-hour format</span></span>                                                  | <span data-ttu-id="631a8-292">17</span><span class="sxs-lookup"><span data-stu-id="631a8-292">17</span></span>                       |
| `%h` | <span data-ttu-id="631a8-293">То же, что "b"</span><span class="sxs-lookup"><span data-stu-id="631a8-293">Same as 'b'</span></span>                                                             |                          |
| `%I` | <span data-ttu-id="631a8-294">Час в 12-часовом формате</span><span class="sxs-lookup"><span data-stu-id="631a8-294">Hour in 12-hour format</span></span>                                                  | <span data-ttu-id="631a8-295">05</span><span class="sxs-lookup"><span data-stu-id="631a8-295">05</span></span>                       |
| `%j` | <span data-ttu-id="631a8-296">День года (не включает в себя начальные `0` исправления в PowerShell 6 +)</span><span class="sxs-lookup"><span data-stu-id="631a8-296">Day of the year (does not include leading `0` - Fixed in PowerShell 6+)</span></span> | <span data-ttu-id="631a8-297">1-366</span><span class="sxs-lookup"><span data-stu-id="631a8-297">1-366</span></span>                    |
| `%k` | <span data-ttu-id="631a8-298">То же, что "H"</span><span class="sxs-lookup"><span data-stu-id="631a8-298">Same as 'H'</span></span>                                                             |                          |
| `%l` | <span data-ttu-id="631a8-299">То же, что "I" (верхний регистр I)</span><span class="sxs-lookup"><span data-stu-id="631a8-299">Same as 'I' (Upper-case I)</span></span>                                              | <span data-ttu-id="631a8-300">05</span><span class="sxs-lookup"><span data-stu-id="631a8-300">05</span></span>                       |
| `%M` | <span data-ttu-id="631a8-301">Минуты</span><span class="sxs-lookup"><span data-stu-id="631a8-301">Minutes</span></span>                                                                 | <span data-ttu-id="631a8-302">35</span><span class="sxs-lookup"><span data-stu-id="631a8-302">35</span></span>                       |
| `%m` | <span data-ttu-id="631a8-303">Номер месяца.</span><span class="sxs-lookup"><span data-stu-id="631a8-303">Month number</span></span>                                                            | <span data-ttu-id="631a8-304">06</span><span class="sxs-lookup"><span data-stu-id="631a8-304">06</span></span>                       |
| `%n` | <span data-ttu-id="631a8-305">символ новой строки</span><span class="sxs-lookup"><span data-stu-id="631a8-305">newline character</span></span>                                                       |                          |
| `%p` | <span data-ttu-id="631a8-306">AM или PM</span><span class="sxs-lookup"><span data-stu-id="631a8-306">AM or PM</span></span>                                                                |                          |
| `%R` | <span data-ttu-id="631a8-307">Время в 24-часовом формате — нет секунд</span><span class="sxs-lookup"><span data-stu-id="631a8-307">Time in 24-hour format -no seconds</span></span>                                      | <span data-ttu-id="631a8-308">17:45</span><span class="sxs-lookup"><span data-stu-id="631a8-308">17:45</span></span>                    |
| `%r` | <span data-ttu-id="631a8-309">Время в 12-часовом формате</span><span class="sxs-lookup"><span data-stu-id="631a8-309">Time in 12-hour format</span></span>                                                  | <span data-ttu-id="631a8-310">09:15:36 AM</span><span class="sxs-lookup"><span data-stu-id="631a8-310">09:15:36 AM</span></span>              |
| `%S` | <span data-ttu-id="631a8-311">Секунды</span><span class="sxs-lookup"><span data-stu-id="631a8-311">Seconds</span></span>                                                                 | <span data-ttu-id="631a8-312">05</span><span class="sxs-lookup"><span data-stu-id="631a8-312">05</span></span>                       |
| `%s` | <span data-ttu-id="631a8-313">Секунды, прошедшие с 1 января 1970 00:00:00</span><span class="sxs-lookup"><span data-stu-id="631a8-313">Seconds elapsed since January 1, 1970 00:00:00</span></span>                          | <span data-ttu-id="631a8-314">1150451174,95705</span><span class="sxs-lookup"><span data-stu-id="631a8-314">1150451174.95705</span></span>         |
| `%t` | <span data-ttu-id="631a8-315">Символ горизонтальной табуляции</span><span class="sxs-lookup"><span data-stu-id="631a8-315">Horizontal tab character</span></span>                                                |                          |
| `%T` | <span data-ttu-id="631a8-316">Время в 24-часовом формате</span><span class="sxs-lookup"><span data-stu-id="631a8-316">Time in 24-hour format</span></span>                                                  | <span data-ttu-id="631a8-317">17:45:52</span><span class="sxs-lookup"><span data-stu-id="631a8-317">17:45:52</span></span>                 |
| `%U` | <span data-ttu-id="631a8-318">То же, что "W"</span><span class="sxs-lookup"><span data-stu-id="631a8-318">Same as 'W'</span></span>                                                             |                          |
| `%u` | <span data-ttu-id="631a8-319">День недели — номер</span><span class="sxs-lookup"><span data-stu-id="631a8-319">Day of the week - number</span></span>                                                | <span data-ttu-id="631a8-320">Воскресенье = 0</span><span class="sxs-lookup"><span data-stu-id="631a8-320">Sunday = 0</span></span>               |
| `%V` | <span data-ttu-id="631a8-321">Неделя года</span><span class="sxs-lookup"><span data-stu-id="631a8-321">Week of the year</span></span>                                                        | <span data-ttu-id="631a8-322">01-53</span><span class="sxs-lookup"><span data-stu-id="631a8-322">01-53</span></span>                    |
| `%w` | <span data-ttu-id="631a8-323">То же, что и "u"</span><span class="sxs-lookup"><span data-stu-id="631a8-323">Same as 'u'</span></span>                                                             |                          |
| `%W` | <span data-ttu-id="631a8-324">Неделя года</span><span class="sxs-lookup"><span data-stu-id="631a8-324">Week of the year</span></span>                                                        | <span data-ttu-id="631a8-325">00-52</span><span class="sxs-lookup"><span data-stu-id="631a8-325">00-52</span></span>                    |
| `%X` | <span data-ttu-id="631a8-326">То же, что 'T»</span><span class="sxs-lookup"><span data-stu-id="631a8-326">Same as 'T'</span></span>                                                             |                          |
| `%x` | <span data-ttu-id="631a8-327">Дата в стандартном формате для языкового стандарта</span><span class="sxs-lookup"><span data-stu-id="631a8-327">Date in standard format for locale</span></span>                                      | <span data-ttu-id="631a8-328">06/27/19 для английского языка США</span><span class="sxs-lookup"><span data-stu-id="631a8-328">06/27/19 for English-US</span></span>  |
| `%Y` | <span data-ttu-id="631a8-329">Год в 4-значном формате</span><span class="sxs-lookup"><span data-stu-id="631a8-329">Year in 4-digit format</span></span>                                                  | <span data-ttu-id="631a8-330">2019</span><span class="sxs-lookup"><span data-stu-id="631a8-330">2019</span></span>                     |
| `%y` | <span data-ttu-id="631a8-331">Год в формате 2 цифр</span><span class="sxs-lookup"><span data-stu-id="631a8-331">Year in 2-digit format</span></span>                                                  | <span data-ttu-id="631a8-332">19</span><span class="sxs-lookup"><span data-stu-id="631a8-332">19</span></span>                       |
| `%Z` | <span data-ttu-id="631a8-333">Смещение часового пояса от универсальной координаты времени (UTC)</span><span class="sxs-lookup"><span data-stu-id="631a8-333">Time zone offset from Universal Time Coordinate (UTC)</span></span>                   | <span data-ttu-id="631a8-334">-07</span><span class="sxs-lookup"><span data-stu-id="631a8-334">-07</span></span>                      |

## <span data-ttu-id="631a8-335">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="631a8-335">RELATED LINKS</span></span>

[<span data-ttu-id="631a8-336">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="631a8-336">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="631a8-337">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="631a8-337">Get-Culture</span></span>](Get-Culture.md)

[<span data-ttu-id="631a8-338">Get-Member</span><span class="sxs-lookup"><span data-stu-id="631a8-338">Get-Member</span></span>](Get-Member.md)

[<span data-ttu-id="631a8-339">New-Item</span><span class="sxs-lookup"><span data-stu-id="631a8-339">New-Item</span></span>](../Microsoft.PowerShell.Management/New-Item.md)

[<span data-ttu-id="631a8-340">New-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="631a8-340">New-TimeSpan</span></span>](New-TimeSpan.md)

[<span data-ttu-id="631a8-341">Set-Date</span><span class="sxs-lookup"><span data-stu-id="631a8-341">Set-Date</span></span>](Set-Date.md)
