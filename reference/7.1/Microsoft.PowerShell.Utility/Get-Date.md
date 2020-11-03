---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Date
ms.openlocfilehash: a299b04c8e041819ef2870abe263fae381b1d5dc
ms.sourcegitcommit: ea9270bacee7dd1b9df2519384de277576357ce2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "93230529"
---
# <span data-ttu-id="9ca78-103">Get-Date</span><span class="sxs-lookup"><span data-stu-id="9ca78-103">Get-Date</span></span>

## <span data-ttu-id="9ca78-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="9ca78-104">SYNOPSIS</span></span>
<span data-ttu-id="9ca78-105">Получает текущую дату и время.</span><span class="sxs-lookup"><span data-stu-id="9ca78-105">Gets the current date and time.</span></span>

## <span data-ttu-id="9ca78-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9ca78-106">SYNTAX</span></span>

### <span data-ttu-id="9ca78-107">Дата (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="9ca78-107">Date (Default)</span></span>

```
Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 [-Format <String>] [-AsUTC] [<CommonParameters>]
```

### <span data-ttu-id="9ca78-108">датеуформат</span><span class="sxs-lookup"><span data-stu-id="9ca78-108">DateUFormat</span></span>

```
Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 -UFormat <String> [<CommonParameters>]
```

### <span data-ttu-id="9ca78-109">уникстимесекондс</span><span class="sxs-lookup"><span data-stu-id="9ca78-109">UnixTimeSeconds</span></span>

```
Get-Date -UnixTimeSeconds <Int64> [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 [-Format <String>] [-AsUTC] [<CommonParameters>]
```

### <span data-ttu-id="9ca78-110">уникстимесекондсуформат</span><span class="sxs-lookup"><span data-stu-id="9ca78-110">UnixTimeSecondsUFormat</span></span>

```
Get-Date -UnixTimeSeconds <Int64> [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 -UFormat <String> [<CommonParameters>]
```

## <span data-ttu-id="9ca78-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9ca78-111">DESCRIPTION</span></span>

<span data-ttu-id="9ca78-112">`Get-Date`Командлет возвращает объект **DateTime** , представляющий текущую дату или указанную дату.</span><span class="sxs-lookup"><span data-stu-id="9ca78-112">The `Get-Date` cmdlet gets a **DateTime** object that represents the current date or a date that you specify.</span></span> <span data-ttu-id="9ca78-113">`Get-Date` может форматировать дату и время в нескольких форматах .NET и UNIX.</span><span class="sxs-lookup"><span data-stu-id="9ca78-113">`Get-Date` can format the date and time in several .NET and UNIX formats.</span></span> <span data-ttu-id="9ca78-114">Можно использовать `Get-Date` для создания строки символов даты или времени, а затем отправить строку другим командлетам или программам.</span><span class="sxs-lookup"><span data-stu-id="9ca78-114">You can use `Get-Date` to generate a date or time character string, and then send the string to other cmdlets or programs.</span></span>

<span data-ttu-id="9ca78-115">`Get-Date` использует параметры языка и региональных параметров компьютера для определения формата выходных данных.</span><span class="sxs-lookup"><span data-stu-id="9ca78-115">`Get-Date` uses the computer's culture settings to determine how the output is formatted.</span></span> <span data-ttu-id="9ca78-116">Чтобы просмотреть параметры компьютера, используйте `(Get-Culture).DateTimeFormat` .</span><span class="sxs-lookup"><span data-stu-id="9ca78-116">To view your computer's settings, use `(Get-Culture).DateTimeFormat`.</span></span>

## <span data-ttu-id="9ca78-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="9ca78-117">EXAMPLES</span></span>

### <span data-ttu-id="9ca78-118">Пример 1. Получение текущей даты и времени</span><span class="sxs-lookup"><span data-stu-id="9ca78-118">Example 1: Get the current date and time</span></span>

<span data-ttu-id="9ca78-119">В этом примере `Get-Date` выводит текущую системную дату и время.</span><span class="sxs-lookup"><span data-stu-id="9ca78-119">In this example, `Get-Date` displays the current system date and time.</span></span> <span data-ttu-id="9ca78-120">Выходные данные имеют формат длинной даты и длительное время.</span><span class="sxs-lookup"><span data-stu-id="9ca78-120">The output is in the long-date and long-time formats.</span></span>

```powershell
Get-Date
```

```Output
Tuesday, June 25, 2019 14:53:32
```

### <span data-ttu-id="9ca78-121">Пример 2. Получение элементов текущей даты и времени</span><span class="sxs-lookup"><span data-stu-id="9ca78-121">Example 2: Get elements of the current date and time</span></span>

<span data-ttu-id="9ca78-122">В этом примере показано, как использовать `Get-Date` для получения элемента даты или времени.</span><span class="sxs-lookup"><span data-stu-id="9ca78-122">This example shows how to use `Get-Date` to get either the date or time element.</span></span> <span data-ttu-id="9ca78-123">Параметр использует аргументы **Date** , **time** или **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="9ca78-123">The parameter uses the arguments **Date** , **Time** , or **DateTime** .</span></span>

```powershell
Get-Date -DisplayHint Date
```

```Output
Tuesday, June 25, 2019
```

<span data-ttu-id="9ca78-124">`Get-Date` использует параметр **дисплайхинт** с аргументом **Date** , чтобы получить только дату.</span><span class="sxs-lookup"><span data-stu-id="9ca78-124">`Get-Date` uses the **DisplayHint** parameter with the **Date** argument to get only the date.</span></span>

### <span data-ttu-id="9ca78-125">Пример 3. Получение даты и времени с помощью описателя формата .NET</span><span class="sxs-lookup"><span data-stu-id="9ca78-125">Example 3: Get the date and time with a .NET format specifier</span></span>

<span data-ttu-id="9ca78-126">В этом примере используется описатель формата .NET для настройки формата вывода.</span><span class="sxs-lookup"><span data-stu-id="9ca78-126">In this example, a .NET format specifier is used to customize the output's format.</span></span> <span data-ttu-id="9ca78-127">Выходные данные представляют собой **строковый** объект.</span><span class="sxs-lookup"><span data-stu-id="9ca78-127">The output is a **String** object.</span></span>

```powershell
Get-Date -Format "dddd MM/dd/yyyy HH:mm K"
```

```Output
Tuesday 06/25/2019 16:17 -07:00
```

<span data-ttu-id="9ca78-128">`Get-Date` использует параметр **Format** для указания нескольких описателей формата.</span><span class="sxs-lookup"><span data-stu-id="9ca78-128">`Get-Date` uses the **Format** parameter to specify several format specifiers.</span></span>

<span data-ttu-id="9ca78-129">Описатели формата .NET, используемые в этом примере, определяются следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9ca78-129">The .NET format specifiers used in this example are defined as follows:</span></span>

| <span data-ttu-id="9ca78-130">Описатель</span><span class="sxs-lookup"><span data-stu-id="9ca78-130">Specifier</span></span> |                      <span data-ttu-id="9ca78-131">Определение</span><span class="sxs-lookup"><span data-stu-id="9ca78-131">Definition</span></span>                       |
| --------- | ----------------------------------------------------- |
| `dddd`    | <span data-ttu-id="9ca78-132">День недели — полное имя</span><span class="sxs-lookup"><span data-stu-id="9ca78-132">Day of the week - full name</span></span>                           |
| `MM`      | <span data-ttu-id="9ca78-133">Номер месяца.</span><span class="sxs-lookup"><span data-stu-id="9ca78-133">Month number</span></span>                                          |
| `dd`      | <span data-ttu-id="9ca78-134">День месяца-2 цифры</span><span class="sxs-lookup"><span data-stu-id="9ca78-134">Day of the month - 2 digits</span></span>                           |
| `yyyy`    | <span data-ttu-id="9ca78-135">Год в 4-значном формате</span><span class="sxs-lookup"><span data-stu-id="9ca78-135">Year in 4-digit format</span></span>                                |
| `HH:mm`   | <span data-ttu-id="9ca78-136">Время в 24-часовом формате — нет секунд</span><span class="sxs-lookup"><span data-stu-id="9ca78-136">Time in 24-hour format - no seconds</span></span>                    |
| `K`       | <span data-ttu-id="9ca78-137">Смещение часового пояса от универсальной координаты времени (UTC)</span><span class="sxs-lookup"><span data-stu-id="9ca78-137">Time zone offset from Universal Time Coordinate (UTC)</span></span> |

<span data-ttu-id="9ca78-138">Дополнительные сведения о спецификаторах формата .NET см. в разделе [строки настраиваемых форматов даты и времени](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span><span class="sxs-lookup"><span data-stu-id="9ca78-138">For more information about .NET format specifiers, see [Custom date and time format strings](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span></span>

### <span data-ttu-id="9ca78-139">Пример 4. Получение даты и времени с помощью описателя UFormat</span><span class="sxs-lookup"><span data-stu-id="9ca78-139">Example 4: Get the date and time with a UFormat specifier</span></span>

<span data-ttu-id="9ca78-140">В этом примере для настройки формата вывода используются несколько описателей формата **UFormat** .</span><span class="sxs-lookup"><span data-stu-id="9ca78-140">In this example, several **UFormat** format specifiers are used to customize the output's format.</span></span>
<span data-ttu-id="9ca78-141">Выходные данные представляют собой **строковый** объект.</span><span class="sxs-lookup"><span data-stu-id="9ca78-141">The output is a **String** object.</span></span>

```powershell
Get-Date -UFormat "%A %m/%d/%Y %R %Z"
```

```Output
Tuesday 06/25/2019 16:19 -07
```

<span data-ttu-id="9ca78-142">`Get-Date` использует параметр **UFormat** для указания нескольких описателей формата.</span><span class="sxs-lookup"><span data-stu-id="9ca78-142">`Get-Date` uses the **UFormat** parameter to specify several format specifiers.</span></span>

<span data-ttu-id="9ca78-143">Описатели формата **UFormat** , используемые в этом примере, определяются следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9ca78-143">The **UFormat** format specifiers used in this example are defined as follows:</span></span>

| <span data-ttu-id="9ca78-144">Описатель</span><span class="sxs-lookup"><span data-stu-id="9ca78-144">Specifier</span></span> |                      <span data-ttu-id="9ca78-145">Определение</span><span class="sxs-lookup"><span data-stu-id="9ca78-145">Definition</span></span>                       |
| --------- | ----------------------------------------------------- |
| `%A`      | <span data-ttu-id="9ca78-146">День недели — полное имя</span><span class="sxs-lookup"><span data-stu-id="9ca78-146">Day of the week - full name</span></span>                           |
| `%m`      | <span data-ttu-id="9ca78-147">Номер месяца.</span><span class="sxs-lookup"><span data-stu-id="9ca78-147">Month number</span></span>                                          |
| `%d`      | <span data-ttu-id="9ca78-148">День месяца-2 цифры</span><span class="sxs-lookup"><span data-stu-id="9ca78-148">Day of the month - 2 digits</span></span>                           |
| `%Y`      | <span data-ttu-id="9ca78-149">Год в 4-значном формате</span><span class="sxs-lookup"><span data-stu-id="9ca78-149">Year in 4-digit format</span></span>                                |
| `%R`      | <span data-ttu-id="9ca78-150">Время в 24-часовом формате — нет секунд</span><span class="sxs-lookup"><span data-stu-id="9ca78-150">Time in 24-hour format - no seconds</span></span>                    |
| `%Z`      | <span data-ttu-id="9ca78-151">Смещение часового пояса от универсальной координаты времени (UTC)</span><span class="sxs-lookup"><span data-stu-id="9ca78-151">Time zone offset from Universal Time Coordinate (UTC)</span></span> |

<span data-ttu-id="9ca78-152">Список допустимых описателей формата **UFormat** см. в разделе " [Примечания](#notes) ".</span><span class="sxs-lookup"><span data-stu-id="9ca78-152">For a list of valid **UFormat** format specifiers, see the [Notes](#notes) section.</span></span>

### <span data-ttu-id="9ca78-153">Пример 5. получение дня года для даты</span><span class="sxs-lookup"><span data-stu-id="9ca78-153">Example 5: Get a date's day of the year</span></span>

<span data-ttu-id="9ca78-154">В этом примере свойство используется для получения числового дня года.</span><span class="sxs-lookup"><span data-stu-id="9ca78-154">In this example, a property is used to get the numeric day of the year.</span></span>

<span data-ttu-id="9ca78-155">В григорианском календаре 365 дней, за исключением високосных лет, имеющих 366 дней.</span><span class="sxs-lookup"><span data-stu-id="9ca78-155">The Gregorian calendar has 365 days, except for leap years that have 366 days.</span></span> <span data-ttu-id="9ca78-156">Например, 31 декабря 2020 — это день 366.</span><span class="sxs-lookup"><span data-stu-id="9ca78-156">For example, December 31, 2020 is day 366.</span></span>

```powershell
(Get-Date -Year 2020 -Month 12 -Day 31).DayOfYear
```

```Output
366
```

<span data-ttu-id="9ca78-157">`Get-Date` использует три параметра для указания даты: **год** , **месяц** и **день** .</span><span class="sxs-lookup"><span data-stu-id="9ca78-157">`Get-Date` uses three parameters to specify the date: **Year** , **Month** , and **Day** .</span></span> <span data-ttu-id="9ca78-158">Команда заключена в круглые скобки, поэтому результат вычисляется свойством **DayofYear** .</span><span class="sxs-lookup"><span data-stu-id="9ca78-158">The command is wrapped with parentheses so that the result is evaluated by the **DayofYear** property.</span></span>

### <span data-ttu-id="9ca78-159">Пример 6. Проверка того, скорректирована ли дата на летнее время</span><span class="sxs-lookup"><span data-stu-id="9ca78-159">Example 6: Check if a date is adjusted for daylight savings time</span></span>

<span data-ttu-id="9ca78-160">В этом примере используется логический метод для проверки, корректируется ли дата на летнее время.</span><span class="sxs-lookup"><span data-stu-id="9ca78-160">This example uses a boolean method to verify if a date is adjusted by daylight savings time.</span></span>

```powershell
$DST = Get-Date
$DST.IsDaylightSavingTime()
```

```Output
True
```

<span data-ttu-id="9ca78-161">Переменная, `$DST` в которой хранится результат `Get-Date` .</span><span class="sxs-lookup"><span data-stu-id="9ca78-161">A variable, `$DST` stores the result of `Get-Date`.</span></span> <span data-ttu-id="9ca78-162">`$DST` проверяет, корректируется ли дата на летнее время, с помощью метода **исдайлигхтсавингтиме** .</span><span class="sxs-lookup"><span data-stu-id="9ca78-162">`$DST` uses the **IsDaylightSavingTime** method to test if the date is adjusted for daylight savings time.</span></span>

### <span data-ttu-id="9ca78-163">Пример 7. Преобразование текущего времени в время в формате UTC</span><span class="sxs-lookup"><span data-stu-id="9ca78-163">Example 7: Convert the current time to UTC time</span></span>

<span data-ttu-id="9ca78-164">В этом примере текущее время преобразуется в время в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="9ca78-164">In this example, the current time is converted to UTC time.</span></span> <span data-ttu-id="9ca78-165">Для преобразования времени используется смещение в формате UTC для языкового стандарта системы.</span><span class="sxs-lookup"><span data-stu-id="9ca78-165">The UTC offset for the system's locale is used to convert the time.</span></span> <span data-ttu-id="9ca78-166">В таблице в разделе " [Примечания](#notes) " перечислены допустимые описатели формата **UFormat** .</span><span class="sxs-lookup"><span data-stu-id="9ca78-166">A table in the [Notes](#notes) section lists the valid **UFormat** format specifiers.</span></span>

```powershell
Get-Date -UFormat "%A %B/%d/%Y %T %Z"
$Time = Get-Date
$Time.ToUniversalTime()
```

```Output
Wednesday June/26/2019 10:45:26 -07

Wednesday, June 26, 2019 17:45:26
```

<span data-ttu-id="9ca78-167">`Get-Date` использует параметр **UFormat** с описателями формата для вывода текущей системной даты и времени.</span><span class="sxs-lookup"><span data-stu-id="9ca78-167">`Get-Date` uses the **UFormat** parameter with format specifiers to display the current system date and time.</span></span> <span data-ttu-id="9ca78-168">Описатель формата **% Z** представляет смещение в формате UTC, равное **-07** .</span><span class="sxs-lookup"><span data-stu-id="9ca78-168">The format specifier **%Z** represents the UTC offset of **-07** .</span></span>

<span data-ttu-id="9ca78-169">`$Time`Переменная хранит текущую системную дату и время.</span><span class="sxs-lookup"><span data-stu-id="9ca78-169">The `$Time` variable stores the current system date and time.</span></span> <span data-ttu-id="9ca78-170">`$Time` использует метод **ToUniversalTime ()** для преобразования времени на основе смещения UTC компьютера.</span><span class="sxs-lookup"><span data-stu-id="9ca78-170">`$Time` uses the **ToUniversalTime()** method to convert the time based on the computer's UTC offset.</span></span>

### <span data-ttu-id="9ca78-171">Пример 8. Создание метки времени</span><span class="sxs-lookup"><span data-stu-id="9ca78-171">Example 8: Create a timestamp</span></span>

<span data-ttu-id="9ca78-172">В этом примере описатель формата создает объект **строки** метки времени для имени каталога.</span><span class="sxs-lookup"><span data-stu-id="9ca78-172">In this example, a format specifier creates a timestamp **String** object for a directory name.</span></span> <span data-ttu-id="9ca78-173">Метка времени включает дату, время и смещение в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="9ca78-173">The timestamp includes the date, time, and UTC offset.</span></span>

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

<span data-ttu-id="9ca78-174">`$timestamp`Переменная хранит результаты выполнения `Get-Date` команды.</span><span class="sxs-lookup"><span data-stu-id="9ca78-174">The `$timestamp` variable stores the results of a `Get-Date` command.</span></span> <span data-ttu-id="9ca78-175">`Get-Date` использует параметр **Format** с описателем формата "нижний регистр" `o` для создания объекта **строки** метки времени.</span><span class="sxs-lookup"><span data-stu-id="9ca78-175">`Get-Date` uses the **Format** parameter with the format specifier of lowercase `o` to create a timestamp **String** object.</span></span> <span data-ttu-id="9ca78-176">Объект отправляется по конвейеру в `ForEach-Object` .</span><span class="sxs-lookup"><span data-stu-id="9ca78-176">The object is sent down the pipeline to `ForEach-Object`.</span></span> <span data-ttu-id="9ca78-177">Блок **ScriptBlock** содержит `$_` переменную, представляющую текущий объект конвейера.</span><span class="sxs-lookup"><span data-stu-id="9ca78-177">A **ScriptBlock** contains the `$_` variable that represents the current pipeline object.</span></span> <span data-ttu-id="9ca78-178">Строка метки времени разделяются двоеточиями, которые заменяются точками.</span><span class="sxs-lookup"><span data-stu-id="9ca78-178">The timestamp string is delimited by colons that are replaced by periods.</span></span>

<span data-ttu-id="9ca78-179">`New-Item` использует параметр **path** для указания расположения нового каталога.</span><span class="sxs-lookup"><span data-stu-id="9ca78-179">`New-Item` uses the **Path** parameter to specify the location for a new directory.</span></span> <span data-ttu-id="9ca78-180">Путь включает `$timestamp` переменную в качестве имени каталога.</span><span class="sxs-lookup"><span data-stu-id="9ca78-180">The path includes the `$timestamp` variable as the directory name.</span></span> <span data-ttu-id="9ca78-181">Параметр **типа** указывает, что каталог создан.</span><span class="sxs-lookup"><span data-stu-id="9ca78-181">The **Type** parameter specifies that a directory is created.</span></span>

### <span data-ttu-id="9ca78-182">Пример 9. Преобразование метки времени Unix</span><span class="sxs-lookup"><span data-stu-id="9ca78-182">Example 9: Convert a Unix timestamp</span></span>

<span data-ttu-id="9ca78-183">Этот пример преобразует время UNIX (представленное числом секунд с 1970-01-01 0:00:00) в DateTime.</span><span class="sxs-lookup"><span data-stu-id="9ca78-183">This example converts a Unix time (represented by the number of seconds since 1970-01-01 0:00:00) to DateTime.</span></span>

```powershell
Get-Date -UnixTimeSeconds 1577836800
```

```Output
Wednesday, January 01, 2020 12:00:00 AM
```

### <span data-ttu-id="9ca78-184">Пример 10. Возврат значения даты, интерпретируемого как время в формате UTC</span><span class="sxs-lookup"><span data-stu-id="9ca78-184">Example 10: Return a date value interpreted as UTC</span></span>

<span data-ttu-id="9ca78-185">В этом примере показано, как интерпретировать значение даты как эквивалент UTC.</span><span class="sxs-lookup"><span data-stu-id="9ca78-185">This example shows how to interpret a date value as its UTC equivalent.</span></span> <span data-ttu-id="9ca78-186">Для этого примера этот компьютер настроен на **стандартное тихоокеанское время** .</span><span class="sxs-lookup"><span data-stu-id="9ca78-186">For the example, this machine is set to **Pacific Standard Time** .</span></span> <span data-ttu-id="9ca78-187">По умолчанию `Get-Date` возвращает значения для этого часового пояса.</span><span class="sxs-lookup"><span data-stu-id="9ca78-187">By default, `Get-Date` returns values for that timezone.</span></span> <span data-ttu-id="9ca78-188">Используйте параметр **асутк** , чтобы преобразовать значение в время в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="9ca78-188">Use the **AsUTC** parameter to convert the value to the UTC equivalent time.</span></span>

```powershell
PS> Get-TimeZone

Id                         : Pacific Standard Time
DisplayName                : (UTC-08:00) Pacific Time (US & Canada)
StandardName               : Pacific Standard Time
DaylightName               : Pacific Daylight Time
BaseUtcOffset              : -08:00:00
SupportsDaylightSavingTime : True

PS> (Get-Date -Date "2020-01-01T00:00:00").Kind
Unspecified

PS> Get-Date -Date "2020-01-01T00:00:00"

Wednesday, January 1, 2020 12:00:00 AM

PS> (Get-Date -Date "2020-01-01T00:00:00" -AsUTC).Kind
Utc

PS> Get-Date -Date "2020-01-01T00:00:00" -AsUTC

Wednesday, January 1, 2020 8:00:00 AM
```

## <span data-ttu-id="9ca78-189">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9ca78-189">PARAMETERS</span></span>

### <span data-ttu-id="9ca78-190">-Асутк</span><span class="sxs-lookup"><span data-stu-id="9ca78-190">-AsUTC</span></span>

<span data-ttu-id="9ca78-191">Преобразует значение даты в эквивалентное время в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="9ca78-191">Converts the date value to the equivalent time in UTC.</span></span>

<span data-ttu-id="9ca78-192">Этот параметр появился в PowerShell 7,1.</span><span class="sxs-lookup"><span data-stu-id="9ca78-192">This parameter was introduced in PowerShell 7.1.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9ca78-193">-Date</span><span class="sxs-lookup"><span data-stu-id="9ca78-193">-Date</span></span>

<span data-ttu-id="9ca78-194">Указывает дату и время.</span><span class="sxs-lookup"><span data-stu-id="9ca78-194">Specifies a date and time.</span></span> <span data-ttu-id="9ca78-195">Время является необязательным и, если не указано, возвращает 00:00:00.</span><span class="sxs-lookup"><span data-stu-id="9ca78-195">Time is optional and if not specified, returns 00:00:00.</span></span>

<span data-ttu-id="9ca78-196">Введите дату и время в формате, стандартном для национальной настройки системы.</span><span class="sxs-lookup"><span data-stu-id="9ca78-196">Enter the date and time in a format that is standard for the system locale.</span></span>

<span data-ttu-id="9ca78-197">Например, на английском языке США:</span><span class="sxs-lookup"><span data-stu-id="9ca78-197">For example, in US English:</span></span>

<span data-ttu-id="9ca78-198">`Get-Date -Date "6/25/2019 12:30:22"` Возвращает вторник, 25 июня 2019 12:30:22</span><span class="sxs-lookup"><span data-stu-id="9ca78-198">`Get-Date -Date "6/25/2019 12:30:22"` returns Tuesday, June 25, 2019 12:30:22</span></span>

```yaml
Type: System.DateTime
Parameter Sets: DateAndFormat, DateAndUFormat
Aliases: LastWriteTime

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="9ca78-199">-Day</span><span class="sxs-lookup"><span data-stu-id="9ca78-199">-Day</span></span>

<span data-ttu-id="9ca78-200">Указывает выводимый день месяца.</span><span class="sxs-lookup"><span data-stu-id="9ca78-200">Specifies the day of the month that is displayed.</span></span> <span data-ttu-id="9ca78-201">Введите значение от 1 до 31.</span><span class="sxs-lookup"><span data-stu-id="9ca78-201">Enter a value from 1 to 31.</span></span>

<span data-ttu-id="9ca78-202">Если указанное значение больше числа дней в месяце, PowerShell добавляет число дней в месяц.</span><span class="sxs-lookup"><span data-stu-id="9ca78-202">If the specified value is greater than the number of days in a month, PowerShell adds the number of days to the month.</span></span> <span data-ttu-id="9ca78-203">Например, `Get-Date -Month 2 -Day 31` отображается **3 марта** , а не **31 февраля** .</span><span class="sxs-lookup"><span data-stu-id="9ca78-203">For example, `Get-Date -Month 2 -Day 31` displays **March 3** , not **February 31** .</span></span>

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

### <span data-ttu-id="9ca78-204">-DisplayHint</span><span class="sxs-lookup"><span data-stu-id="9ca78-204">-DisplayHint</span></span>

<span data-ttu-id="9ca78-205">Определяет, какие элементы даты и времени будут отображаться.</span><span class="sxs-lookup"><span data-stu-id="9ca78-205">Determines which elements of the date and time are displayed.</span></span>

<span data-ttu-id="9ca78-206">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="9ca78-206">The accepted values are as follows:</span></span>

- <span data-ttu-id="9ca78-207">**Date:** отображается только дата;</span><span class="sxs-lookup"><span data-stu-id="9ca78-207">**Date** : displays only the date</span></span>
- <span data-ttu-id="9ca78-208">**Time:** отображается только время;</span><span class="sxs-lookup"><span data-stu-id="9ca78-208">**Time** : displays only the time</span></span>
- <span data-ttu-id="9ca78-209">**DateTime:** отображаются дата и время.</span><span class="sxs-lookup"><span data-stu-id="9ca78-209">**DateTime** : displays the date and time</span></span>

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

### <span data-ttu-id="9ca78-210">-Format</span><span class="sxs-lookup"><span data-stu-id="9ca78-210">-Format</span></span>

<span data-ttu-id="9ca78-211">Выводит дату и время в формате Microsoft .NET Framework, определяемом спецификатором формата.</span><span class="sxs-lookup"><span data-stu-id="9ca78-211">Displays the date and time in the Microsoft .NET Framework format indicated by the format specifier.</span></span>
<span data-ttu-id="9ca78-212">Параметр **Format** выводит **строковый** объект.</span><span class="sxs-lookup"><span data-stu-id="9ca78-212">The **Format** parameter outputs a **String** object.</span></span>

<span data-ttu-id="9ca78-213">Список доступных описателей формата .NET см. в разделе [строки настраиваемых форматов даты и времени](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span><span class="sxs-lookup"><span data-stu-id="9ca78-213">For a list of available .NET format specifiers, see [Custom date and time format strings](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span></span>

<span data-ttu-id="9ca78-214">При использовании параметра **Format** `Get-Date` получает только свойства объекта **DateTime** , необходимые для вывода даты.</span><span class="sxs-lookup"><span data-stu-id="9ca78-214">When the **Format** parameter is used, `Get-Date` only gets the **DateTime** object's properties necessary to display the date.</span></span> <span data-ttu-id="9ca78-215">Поэтому некоторые свойства и методы объекта **DateTime** могут быть недоступны.</span><span class="sxs-lookup"><span data-stu-id="9ca78-215">As a result, some of the properties and methods of **DateTime** objects might not be available.</span></span>

<span data-ttu-id="9ca78-216">Начиная с PowerShell 5,0, в качестве значений параметра **Format** можно использовать следующие дополнительные форматы.</span><span class="sxs-lookup"><span data-stu-id="9ca78-216">Starting in PowerShell 5.0, you can use the following additional formats as values for the **Format** parameter.</span></span>

- <span data-ttu-id="9ca78-217">**Филедате** .</span><span class="sxs-lookup"><span data-stu-id="9ca78-217">**FileDate** .</span></span> <span data-ttu-id="9ca78-218">Представление текущей даты в формате местного времени в файле или пути.</span><span class="sxs-lookup"><span data-stu-id="9ca78-218">A file or path-friendly representation of the current date in local time.</span></span> <span data-ttu-id="9ca78-219">Формат (с `yyyyMMdd` учетом регистра, с использованием 4-значного года, 2-значный месяц и день в 2 цифры).</span><span class="sxs-lookup"><span data-stu-id="9ca78-219">The format is `yyyyMMdd` (case-sensitive, using a 4-digit year, 2-digit month, and 2-digit day).</span></span> <span data-ttu-id="9ca78-220">Пример:</span><span class="sxs-lookup"><span data-stu-id="9ca78-220">For example:</span></span>
  20190627.

- <span data-ttu-id="9ca78-221">**Филедатеуниверсал** .</span><span class="sxs-lookup"><span data-stu-id="9ca78-221">**FileDateUniversal** .</span></span> <span data-ttu-id="9ca78-222">Представление текущей даты в формате UTC в виде файла или пути.</span><span class="sxs-lookup"><span data-stu-id="9ca78-222">A file or path-friendly representation of the current date in universal time (UTC).</span></span> <span data-ttu-id="9ca78-223">Формат (с `yyyyMMddZ` учетом регистра, с использованием 4-разрядного года, месяца, 2 цифры и буквы в `Z` качестве индикатора времени в формате UTC).</span><span class="sxs-lookup"><span data-stu-id="9ca78-223">The format is `yyyyMMddZ` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, and the letter `Z` as the UTC indicator).</span></span> <span data-ttu-id="9ca78-224">Например: 20190627Z.</span><span class="sxs-lookup"><span data-stu-id="9ca78-224">For example: 20190627Z.</span></span>

- <span data-ttu-id="9ca78-225">**Филедатетиме** .</span><span class="sxs-lookup"><span data-stu-id="9ca78-225">**FileDateTime** .</span></span> <span data-ttu-id="9ca78-226">Представление текущей даты и времени по местному времени в 24-часовом формате в виде файла или пути.</span><span class="sxs-lookup"><span data-stu-id="9ca78-226">A file or path-friendly representation of the current date and time in local time, in 24-hour format.</span></span> <span data-ttu-id="9ca78-227">Формат (с `yyyyMMddTHHmmssffff` учетом регистра, с использованием 4-разрядного года, 2-значный месяц, с двумя цифрами, буква в `T` качестве разделителя времени, 2-значный час, 2-значная минута, 2-значная секунда и 4-значная миллисекунда).</span><span class="sxs-lookup"><span data-stu-id="9ca78-227">The format is `yyyyMMddTHHmmssffff` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, the letter `T` as a time separator, 2-digit hour, 2-digit minute, 2-digit second, and 4-digit millisecond).</span></span> <span data-ttu-id="9ca78-228">Например: 20190627T0840107271.</span><span class="sxs-lookup"><span data-stu-id="9ca78-228">For example: 20190627T0840107271.</span></span>

- <span data-ttu-id="9ca78-229">**Филедатетимеуниверсал** .</span><span class="sxs-lookup"><span data-stu-id="9ca78-229">**FileDateTimeUniversal** .</span></span> <span data-ttu-id="9ca78-230">Представление текущей даты и времени в формате UTC в 24-часовом виде файла или пути.</span><span class="sxs-lookup"><span data-stu-id="9ca78-230">A file or path-friendly representation of the current date and time in universal time (UTC), in 24-hour format.</span></span> <span data-ttu-id="9ca78-231">Формат (с `yyyyMMddTHHmmssffffZ` учетом регистра, с использованием 4-разрядного года, 2-значного месяца, буквы в 2 цифры, буква в `T` качестве разделителя времени, 2-значный час, 2-значная минута, 2-значная секунда, 4-разрядная миллисекунда и букву в `Z` качестве индикатора времени в формате UTC).</span><span class="sxs-lookup"><span data-stu-id="9ca78-231">The format is `yyyyMMddTHHmmssffffZ` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, the letter `T` as a time separator, 2-digit hour, 2-digit minute, 2-digit second, 4-digit millisecond, and the letter `Z` as the UTC indicator).</span></span> <span data-ttu-id="9ca78-232">Например: 20190627T1540500718Z.</span><span class="sxs-lookup"><span data-stu-id="9ca78-232">For example: 20190627T1540500718Z.</span></span>

```yaml
Type: System.String
Parameter Sets: DateAndFormat, UnixTimeSecondsAndFormat
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9ca78-233">-Hour</span><span class="sxs-lookup"><span data-stu-id="9ca78-233">-Hour</span></span>

<span data-ttu-id="9ca78-234">Указывает выводимый час.</span><span class="sxs-lookup"><span data-stu-id="9ca78-234">Specifies the hour that is displayed.</span></span> <span data-ttu-id="9ca78-235">Введите значение от 0 до 23.</span><span class="sxs-lookup"><span data-stu-id="9ca78-235">Enter a value from 0 to 23.</span></span>

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

### <span data-ttu-id="9ca78-236">-Millisecond</span><span class="sxs-lookup"><span data-stu-id="9ca78-236">-Millisecond</span></span>

<span data-ttu-id="9ca78-237">Указывает миллисекунды в дате.</span><span class="sxs-lookup"><span data-stu-id="9ca78-237">Specifies the milliseconds in the date.</span></span> <span data-ttu-id="9ca78-238">Введите значение от 0 до 999.</span><span class="sxs-lookup"><span data-stu-id="9ca78-238">Enter a value from 0 to 999.</span></span>

<span data-ttu-id="9ca78-239">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="9ca78-239">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="9ca78-240">-Minute</span><span class="sxs-lookup"><span data-stu-id="9ca78-240">-Minute</span></span>

<span data-ttu-id="9ca78-241">Указывает выводимую минуту.</span><span class="sxs-lookup"><span data-stu-id="9ca78-241">Specifies the minute that is displayed.</span></span> <span data-ttu-id="9ca78-242">Введите значение от 0 до 59.</span><span class="sxs-lookup"><span data-stu-id="9ca78-242">Enter a value from 0 to 59.</span></span>

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

### <span data-ttu-id="9ca78-243">-Month</span><span class="sxs-lookup"><span data-stu-id="9ca78-243">-Month</span></span>

<span data-ttu-id="9ca78-244">Указывает выводимый месяц.</span><span class="sxs-lookup"><span data-stu-id="9ca78-244">Specifies the month that is displayed.</span></span> <span data-ttu-id="9ca78-245">Введите значение от 1 до 12.</span><span class="sxs-lookup"><span data-stu-id="9ca78-245">Enter a value from 1 to 12.</span></span>

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

### <span data-ttu-id="9ca78-246">-Second</span><span class="sxs-lookup"><span data-stu-id="9ca78-246">-Second</span></span>

<span data-ttu-id="9ca78-247">Указывает выводимую секунду.</span><span class="sxs-lookup"><span data-stu-id="9ca78-247">Specifies the second that is displayed.</span></span> <span data-ttu-id="9ca78-248">Введите значение от 0 до 59.</span><span class="sxs-lookup"><span data-stu-id="9ca78-248">Enter a value from 0 to 59.</span></span>

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

### <span data-ttu-id="9ca78-249">-UFormat</span><span class="sxs-lookup"><span data-stu-id="9ca78-249">-UFormat</span></span>

<span data-ttu-id="9ca78-250">Выводит дату и время в формате UNIX.</span><span class="sxs-lookup"><span data-stu-id="9ca78-250">Displays the date and time in UNIX format.</span></span> <span data-ttu-id="9ca78-251">Параметр **UFormat** выводит строковый объект.</span><span class="sxs-lookup"><span data-stu-id="9ca78-251">The **UFormat** parameter outputs a string object.</span></span>

<span data-ttu-id="9ca78-252">Спецификаторам **UFormat** предшествует знак процента (), например,, `%` `%m` `%d` и `%Y` .</span><span class="sxs-lookup"><span data-stu-id="9ca78-252">**UFormat** specifiers are preceded by a percent sign (`%`), for example, `%m`, `%d`, and `%Y`.</span></span> <span data-ttu-id="9ca78-253">В разделе " [Примечания](#notes) " содержится таблица допустимых **описателей UFormat** .</span><span class="sxs-lookup"><span data-stu-id="9ca78-253">The [Notes](#notes) section contains a table of valid **UFormat specifiers** .</span></span>

<span data-ttu-id="9ca78-254">При использовании параметра **UFormat** `Get-Date` получает только свойства объекта **DateTime** , необходимые для вывода даты.</span><span class="sxs-lookup"><span data-stu-id="9ca78-254">When the **UFormat** parameter is used, `Get-Date` only gets the **DateTime** object's properties necessary to display the date.</span></span> <span data-ttu-id="9ca78-255">Поэтому некоторые свойства и методы объекта **DateTime** могут быть недоступны.</span><span class="sxs-lookup"><span data-stu-id="9ca78-255">As a result, some of the properties and methods of **DateTime** objects might not be available.</span></span>

```yaml
Type: System.String
Parameter Sets: DateAndUFormat, UnixTimeSecondsAndUFormat
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9ca78-256">-Уникстимесекондс</span><span class="sxs-lookup"><span data-stu-id="9ca78-256">-UnixTimeSeconds</span></span>

<span data-ttu-id="9ca78-257">Дата и время, представленные в секундах с 1 января 1970 0:00:00.</span><span class="sxs-lookup"><span data-stu-id="9ca78-257">Date and time represented in seconds since January 1, 1970, 0:00:00.</span></span>

<span data-ttu-id="9ca78-258">Этот параметр появился в PowerShell 7,1.</span><span class="sxs-lookup"><span data-stu-id="9ca78-258">This parameter was introduced in PowerShell 7.1.</span></span>

```yaml
Type: System.Int64
Parameter Sets: UnixTimeSecondsAndFormat, UnixTimeSecondsAndUFormat
Aliases: UnixTime

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9ca78-259">-Year</span><span class="sxs-lookup"><span data-stu-id="9ca78-259">-Year</span></span>

<span data-ttu-id="9ca78-260">Указывает выводимый год.</span><span class="sxs-lookup"><span data-stu-id="9ca78-260">Specifies the year that is displayed.</span></span> <span data-ttu-id="9ca78-261">Введите значение от 1 до 9999.</span><span class="sxs-lookup"><span data-stu-id="9ca78-261">Enter a value from 1 to 9999.</span></span>

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

### <span data-ttu-id="9ca78-262">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="9ca78-262">CommonParameters</span></span>

<span data-ttu-id="9ca78-263">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9ca78-263">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9ca78-264">См. сведения в разделе [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9ca78-264">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9ca78-265">Входные данные</span><span class="sxs-lookup"><span data-stu-id="9ca78-265">INPUTS</span></span>

### <span data-ttu-id="9ca78-266">Входные данные конвейера</span><span class="sxs-lookup"><span data-stu-id="9ca78-266">Pipeline input</span></span>

<span data-ttu-id="9ca78-267">`Get-Date` принимает входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="9ca78-267">`Get-Date` accepts pipeline input.</span></span> <span data-ttu-id="9ca78-268">Например, `Get-ChildItem | Get-Date`.</span><span class="sxs-lookup"><span data-stu-id="9ca78-268">For example, `Get-ChildItem | Get-Date`.</span></span>

## <span data-ttu-id="9ca78-269">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="9ca78-269">OUTPUTS</span></span>

### <span data-ttu-id="9ca78-270">System.DateTime или System.String</span><span class="sxs-lookup"><span data-stu-id="9ca78-270">System.DateTime or System.String</span></span>

<span data-ttu-id="9ca78-271">`Get-Date` Возвращает объект **DateTime** , за исключением случаев, когда используются параметры **Format** и **UFormat** .</span><span class="sxs-lookup"><span data-stu-id="9ca78-271">`Get-Date` returns a **DateTime** object except when the **Format** and **UFormat** parameters are used.</span></span> <span data-ttu-id="9ca78-272">Параметры **Format** или **UFormat** возвращают **строковые** объекты.</span><span class="sxs-lookup"><span data-stu-id="9ca78-272">The **Format** or **UFormat** parameters return **String** objects.</span></span>

<span data-ttu-id="9ca78-273">Когда объект **DateTime** отправляется по конвейеру в командлет, например, при `Add-Content` ожидании ввода строки, PowerShell преобразует объект в **строковый** объект.</span><span class="sxs-lookup"><span data-stu-id="9ca78-273">When a **DateTime** object is sent down the pipeline to a cmdlet such as `Add-Content` that expects string input, PowerShell converts the object to a **String** object.</span></span>

<span data-ttu-id="9ca78-274">Метод `(Get-Date).ToString()` преобразует объект **DateTime** в объект **String** .</span><span class="sxs-lookup"><span data-stu-id="9ca78-274">The method `(Get-Date).ToString()` converts a **DateTime** object a **String** object.</span></span>

<span data-ttu-id="9ca78-275">Чтобы отобразить свойства и методы объекта, отправьте объект по конвейеру в `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="9ca78-275">To display an object's properties and methods, send the object down the pipeline to `Get-Member`.</span></span>
<span data-ttu-id="9ca78-276">Например, `Get-Date | Get-Member`.</span><span class="sxs-lookup"><span data-stu-id="9ca78-276">For example, `Get-Date | Get-Member`.</span></span>

## <span data-ttu-id="9ca78-277">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="9ca78-277">NOTES</span></span>

<span data-ttu-id="9ca78-278">Объекты **DateTime** имеют формат длинной даты и длительное время для национальной настройки системы.</span><span class="sxs-lookup"><span data-stu-id="9ca78-278">**DateTime** objects are in long-date and long-time formats for the system locale.</span></span>

<span data-ttu-id="9ca78-279">В следующей таблице показаны допустимые **описатели UFormat** .</span><span class="sxs-lookup"><span data-stu-id="9ca78-279">The valid **UFormat specifiers** are displayed in the following table:</span></span>

| <span data-ttu-id="9ca78-280">Описатель формата</span><span class="sxs-lookup"><span data-stu-id="9ca78-280">Format specifier</span></span> |                                 <span data-ttu-id="9ca78-281">Значение</span><span class="sxs-lookup"><span data-stu-id="9ca78-281">Meaning</span></span>                     |         <span data-ttu-id="9ca78-282">Пример</span><span class="sxs-lookup"><span data-stu-id="9ca78-282">Example</span></span>          |
| ---- | ----------------------------------------------------------------------- | ------------------------ |
| `%A` | <span data-ttu-id="9ca78-283">День недели — полное имя</span><span class="sxs-lookup"><span data-stu-id="9ca78-283">Day of the week - full name</span></span>                                             | <span data-ttu-id="9ca78-284">Понедельник</span><span class="sxs-lookup"><span data-stu-id="9ca78-284">Monday</span></span>                   |
| `%a` | <span data-ttu-id="9ca78-285">День в сокращенном названии недели</span><span class="sxs-lookup"><span data-stu-id="9ca78-285">Day of the week - abbreviated name</span></span>                                      | <span data-ttu-id="9ca78-286">Mon</span><span class="sxs-lookup"><span data-stu-id="9ca78-286">Mon</span></span>                      |
| `%B` | <span data-ttu-id="9ca78-287">Имя месяца — полное</span><span class="sxs-lookup"><span data-stu-id="9ca78-287">Month name - full</span></span>                                                       | <span data-ttu-id="9ca78-288">Январь</span><span class="sxs-lookup"><span data-stu-id="9ca78-288">January</span></span>                  |
| `%b` | <span data-ttu-id="9ca78-289">Название месяца — сокращенное</span><span class="sxs-lookup"><span data-stu-id="9ca78-289">Month name - abbreviated</span></span>                                                | <span data-ttu-id="9ca78-290">Январь</span><span class="sxs-lookup"><span data-stu-id="9ca78-290">Jan</span></span>                      |
| `%C` | <span data-ttu-id="9ca78-291">Век</span><span class="sxs-lookup"><span data-stu-id="9ca78-291">Century</span></span>                                                                 | <span data-ttu-id="9ca78-292">20 для 2019</span><span class="sxs-lookup"><span data-stu-id="9ca78-292">20 for 2019</span></span>              |
| `%c` | <span data-ttu-id="9ca78-293">Дата и время-сокращенные</span><span class="sxs-lookup"><span data-stu-id="9ca78-293">Date and time - abbreviated</span></span>                                             | <span data-ttu-id="9ca78-294">Четверг июня 27 08:44:18 2019</span><span class="sxs-lookup"><span data-stu-id="9ca78-294">Thu Jun 27 08:44:18 2019</span></span> |
| `%D` | <span data-ttu-id="9ca78-295">Дата в формате мм/дд/гг</span><span class="sxs-lookup"><span data-stu-id="9ca78-295">Date in mm/dd/yy format</span></span>                                                 | <span data-ttu-id="9ca78-296">06/27/19</span><span class="sxs-lookup"><span data-stu-id="9ca78-296">06/27/19</span></span>                 |
| `%d` | <span data-ttu-id="9ca78-297">День месяца-2 цифры</span><span class="sxs-lookup"><span data-stu-id="9ca78-297">Day of the month - 2 digits</span></span>                                             | <span data-ttu-id="9ca78-298">05</span><span class="sxs-lookup"><span data-stu-id="9ca78-298">05</span></span>                       |
| `%e` | <span data-ttu-id="9ca78-299">День месяца — цифра, предшествующая пробелом</span><span class="sxs-lookup"><span data-stu-id="9ca78-299">Day of the month - digit preceded by a space</span></span>                            | <span data-ttu-id="9ca78-300">\<space\>5.0</span><span class="sxs-lookup"><span data-stu-id="9ca78-300">\<space\>5</span></span>               |
| `%F` | <span data-ttu-id="9ca78-301">Дата в формате гггг-мм-дд равна% Y-% m-% d (формат даты ISO 8601)</span><span class="sxs-lookup"><span data-stu-id="9ca78-301">Date in YYYY-mm-dd format, equal to %Y-%m-%d (the ISO 8601 date format)</span></span> | <span data-ttu-id="9ca78-302">2019-06-27</span><span class="sxs-lookup"><span data-stu-id="9ca78-302">2019-06-27</span></span>               |
| `%G` | <span data-ttu-id="9ca78-303">То же, что "Y"</span><span class="sxs-lookup"><span data-stu-id="9ca78-303">Same as 'Y'</span></span>                                                             |                          |
| `%g` | <span data-ttu-id="9ca78-304">То же, что "y"</span><span class="sxs-lookup"><span data-stu-id="9ca78-304">Same as 'y'</span></span>                                                             |                          |
| `%H` | <span data-ttu-id="9ca78-305">Час в 24-часовом формате</span><span class="sxs-lookup"><span data-stu-id="9ca78-305">Hour in 24-hour format</span></span>                                                  | <span data-ttu-id="9ca78-306">17</span><span class="sxs-lookup"><span data-stu-id="9ca78-306">17</span></span>                       |
| `%h` | <span data-ttu-id="9ca78-307">То же, что "b"</span><span class="sxs-lookup"><span data-stu-id="9ca78-307">Same as 'b'</span></span>                                                             |                          |
| `%I` | <span data-ttu-id="9ca78-308">Час в 12-часовом формате</span><span class="sxs-lookup"><span data-stu-id="9ca78-308">Hour in 12-hour format</span></span>                                                  | <span data-ttu-id="9ca78-309">05</span><span class="sxs-lookup"><span data-stu-id="9ca78-309">05</span></span>                       |
| `%j` | <span data-ttu-id="9ca78-310">День года</span><span class="sxs-lookup"><span data-stu-id="9ca78-310">Day of the year</span></span>                                                         | <span data-ttu-id="9ca78-311">1-366</span><span class="sxs-lookup"><span data-stu-id="9ca78-311">1-366</span></span>                    |
| `%k` | <span data-ttu-id="9ca78-312">То же, что "H"</span><span class="sxs-lookup"><span data-stu-id="9ca78-312">Same as 'H'</span></span>                                                             |                          |
| `%l` | <span data-ttu-id="9ca78-313">То же, что "I" (верхний регистр I)</span><span class="sxs-lookup"><span data-stu-id="9ca78-313">Same as 'I' (Upper-case I)</span></span>                                              | <span data-ttu-id="9ca78-314">05</span><span class="sxs-lookup"><span data-stu-id="9ca78-314">05</span></span>                       |
| `%M` | <span data-ttu-id="9ca78-315">Минуты</span><span class="sxs-lookup"><span data-stu-id="9ca78-315">Minutes</span></span>                                                                 | <span data-ttu-id="9ca78-316">35</span><span class="sxs-lookup"><span data-stu-id="9ca78-316">35</span></span>                       |
| `%m` | <span data-ttu-id="9ca78-317">Номер месяца.</span><span class="sxs-lookup"><span data-stu-id="9ca78-317">Month number</span></span>                                                            | <span data-ttu-id="9ca78-318">06</span><span class="sxs-lookup"><span data-stu-id="9ca78-318">06</span></span>                       |
| `%n` | <span data-ttu-id="9ca78-319">символ новой строки</span><span class="sxs-lookup"><span data-stu-id="9ca78-319">newline character</span></span>                                                       |                          |
| `%p` | <span data-ttu-id="9ca78-320">AM или PM</span><span class="sxs-lookup"><span data-stu-id="9ca78-320">AM or PM</span></span>                                                                |                          |
| `%R` | <span data-ttu-id="9ca78-321">Время в 24-часовом формате — нет секунд</span><span class="sxs-lookup"><span data-stu-id="9ca78-321">Time in 24-hour format -no seconds</span></span>                                      | <span data-ttu-id="9ca78-322">17:45</span><span class="sxs-lookup"><span data-stu-id="9ca78-322">17:45</span></span>                    |
| `%r` | <span data-ttu-id="9ca78-323">Время в 12-часовом формате</span><span class="sxs-lookup"><span data-stu-id="9ca78-323">Time in 12-hour format</span></span>                                                  | <span data-ttu-id="9ca78-324">09:15:36 AM</span><span class="sxs-lookup"><span data-stu-id="9ca78-324">09:15:36 AM</span></span>              |
| `%S` | <span data-ttu-id="9ca78-325">Секунды</span><span class="sxs-lookup"><span data-stu-id="9ca78-325">Seconds</span></span>                                                                 | <span data-ttu-id="9ca78-326">05</span><span class="sxs-lookup"><span data-stu-id="9ca78-326">05</span></span>                       |
| `%s` | <span data-ttu-id="9ca78-327">Секунды, прошедшие с 1 января 1970 00:00:00</span><span class="sxs-lookup"><span data-stu-id="9ca78-327">Seconds elapsed since January 1, 1970 00:00:00</span></span>                          | <span data-ttu-id="9ca78-328">1150451174</span><span class="sxs-lookup"><span data-stu-id="9ca78-328">1150451174</span></span>               |
| `%t` | <span data-ttu-id="9ca78-329">Символ горизонтальной табуляции</span><span class="sxs-lookup"><span data-stu-id="9ca78-329">Horizontal tab character</span></span>                                                |                          |
| `%T` | <span data-ttu-id="9ca78-330">Время в 24-часовом формате</span><span class="sxs-lookup"><span data-stu-id="9ca78-330">Time in 24-hour format</span></span>                                                  | <span data-ttu-id="9ca78-331">17:45:52</span><span class="sxs-lookup"><span data-stu-id="9ca78-331">17:45:52</span></span>                 |
| `%U` | <span data-ttu-id="9ca78-332">То же, что "W"</span><span class="sxs-lookup"><span data-stu-id="9ca78-332">Same as 'W'</span></span>                                                             |                          |
| `%u` | <span data-ttu-id="9ca78-333">День недели — номер</span><span class="sxs-lookup"><span data-stu-id="9ca78-333">Day of the week - number</span></span>                                                | <span data-ttu-id="9ca78-334">Воскресенье = 0</span><span class="sxs-lookup"><span data-stu-id="9ca78-334">Sunday = 0</span></span>               |
| `%V` | <span data-ttu-id="9ca78-335">Неделя года</span><span class="sxs-lookup"><span data-stu-id="9ca78-335">Week of the year</span></span>                                                        | <span data-ttu-id="9ca78-336">01-53</span><span class="sxs-lookup"><span data-stu-id="9ca78-336">01-53</span></span>                    |
| `%w` | <span data-ttu-id="9ca78-337">То же, что и "u"</span><span class="sxs-lookup"><span data-stu-id="9ca78-337">Same as 'u'</span></span>                                                             |                          |
| `%W` | <span data-ttu-id="9ca78-338">Неделя года</span><span class="sxs-lookup"><span data-stu-id="9ca78-338">Week of the year</span></span>                                                        | <span data-ttu-id="9ca78-339">00-52</span><span class="sxs-lookup"><span data-stu-id="9ca78-339">00-52</span></span>                    |
| `%X` | <span data-ttu-id="9ca78-340">То же, что 'T»</span><span class="sxs-lookup"><span data-stu-id="9ca78-340">Same as 'T'</span></span>                                                             |                          |
| `%x` | <span data-ttu-id="9ca78-341">Дата в стандартном формате для языкового стандарта</span><span class="sxs-lookup"><span data-stu-id="9ca78-341">Date in standard format for locale</span></span>                                      | <span data-ttu-id="9ca78-342">06/27/19 для английского языка США</span><span class="sxs-lookup"><span data-stu-id="9ca78-342">06/27/19 for English-US</span></span>  |
| `%Y` | <span data-ttu-id="9ca78-343">Год в 4-значном формате</span><span class="sxs-lookup"><span data-stu-id="9ca78-343">Year in 4-digit format</span></span>                                                  | <span data-ttu-id="9ca78-344">2019</span><span class="sxs-lookup"><span data-stu-id="9ca78-344">2019</span></span>                     |
| `%y` | <span data-ttu-id="9ca78-345">Год в формате 2 цифр</span><span class="sxs-lookup"><span data-stu-id="9ca78-345">Year in 2-digit format</span></span>                                                  | <span data-ttu-id="9ca78-346">19</span><span class="sxs-lookup"><span data-stu-id="9ca78-346">19</span></span>                       |
| `%Z` | <span data-ttu-id="9ca78-347">Смещение часового пояса от универсальной координаты времени (UTC)</span><span class="sxs-lookup"><span data-stu-id="9ca78-347">Time zone offset from Universal Time Coordinate (UTC)</span></span>                   | <span data-ttu-id="9ca78-348">-07</span><span class="sxs-lookup"><span data-stu-id="9ca78-348">-07</span></span>                      |

## <span data-ttu-id="9ca78-349">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="9ca78-349">RELATED LINKS</span></span>

[<span data-ttu-id="9ca78-350">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="9ca78-350">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="9ca78-351">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="9ca78-351">Get-Culture</span></span>](Get-Culture.md)

[<span data-ttu-id="9ca78-352">Get-Member</span><span class="sxs-lookup"><span data-stu-id="9ca78-352">Get-Member</span></span>](Get-Member.md)

[<span data-ttu-id="9ca78-353">New-Item</span><span class="sxs-lookup"><span data-stu-id="9ca78-353">New-Item</span></span>](../Microsoft.PowerShell.Management/New-Item.md)

[<span data-ttu-id="9ca78-354">New-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="9ca78-354">New-TimeSpan</span></span>](New-TimeSpan.md)

[<span data-ttu-id="9ca78-355">Set-Date</span><span class="sxs-lookup"><span data-stu-id="9ca78-355">Set-Date</span></span>](Set-Date.md)
