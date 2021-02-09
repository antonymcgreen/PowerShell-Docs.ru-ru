---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Date
ms.openlocfilehash: 6f5c76faafa2c68a6d9dfc604238c514489aa717
ms.sourcegitcommit: 3a1d80e27438976101f216b8c3d623c61b868db8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "99975062"
---
# <span data-ttu-id="f5616-102">Get-Date</span><span class="sxs-lookup"><span data-stu-id="f5616-102">Get-Date</span></span>

## <span data-ttu-id="f5616-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="f5616-103">SYNOPSIS</span></span>
<span data-ttu-id="f5616-104">Получает текущую дату и время.</span><span class="sxs-lookup"><span data-stu-id="f5616-104">Gets the current date and time.</span></span>

## <span data-ttu-id="f5616-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f5616-105">SYNTAX</span></span>

### <span data-ttu-id="f5616-106">Дата (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="f5616-106">Date (Default)</span></span>

```
Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 [-Format <String>] [-AsUTC] [<CommonParameters>]
```

### <span data-ttu-id="f5616-107">датеуформат</span><span class="sxs-lookup"><span data-stu-id="f5616-107">DateUFormat</span></span>

```
Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 -UFormat <String> [<CommonParameters>]
```

### <span data-ttu-id="f5616-108">уникстимесекондс</span><span class="sxs-lookup"><span data-stu-id="f5616-108">UnixTimeSeconds</span></span>

```
Get-Date -UnixTimeSeconds <Int64> [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 [-Format <String>] [-AsUTC] [<CommonParameters>]
```

### <span data-ttu-id="f5616-109">уникстимесекондсуформат</span><span class="sxs-lookup"><span data-stu-id="f5616-109">UnixTimeSecondsUFormat</span></span>

```
Get-Date -UnixTimeSeconds <Int64> [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 -UFormat <String> [<CommonParameters>]
```

## <span data-ttu-id="f5616-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f5616-110">DESCRIPTION</span></span>

<span data-ttu-id="f5616-111">`Get-Date`Командлет возвращает объект **DateTime** , представляющий текущую дату или указанную дату.</span><span class="sxs-lookup"><span data-stu-id="f5616-111">The `Get-Date` cmdlet gets a **DateTime** object that represents the current date or a date that you specify.</span></span> <span data-ttu-id="f5616-112">`Get-Date` может форматировать дату и время в нескольких форматах .NET и UNIX.</span><span class="sxs-lookup"><span data-stu-id="f5616-112">`Get-Date` can format the date and time in several .NET and UNIX formats.</span></span> <span data-ttu-id="f5616-113">Можно использовать `Get-Date` для создания строки символов даты или времени, а затем отправить строку другим командлетам или программам.</span><span class="sxs-lookup"><span data-stu-id="f5616-113">You can use `Get-Date` to generate a date or time character string, and then send the string to other cmdlets or programs.</span></span>

<span data-ttu-id="f5616-114">`Get-Date` использует параметры языка и региональных параметров компьютера для определения формата выходных данных.</span><span class="sxs-lookup"><span data-stu-id="f5616-114">`Get-Date` uses the computer's culture settings to determine how the output is formatted.</span></span> <span data-ttu-id="f5616-115">Чтобы просмотреть параметры компьютера, используйте `(Get-Culture).DateTimeFormat` .</span><span class="sxs-lookup"><span data-stu-id="f5616-115">To view your computer's settings, use `(Get-Culture).DateTimeFormat`.</span></span>

## <span data-ttu-id="f5616-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="f5616-116">EXAMPLES</span></span>

### <span data-ttu-id="f5616-117">Пример 1. Получение текущей даты и времени</span><span class="sxs-lookup"><span data-stu-id="f5616-117">Example 1: Get the current date and time</span></span>

<span data-ttu-id="f5616-118">В этом примере `Get-Date` выводит текущую системную дату и время.</span><span class="sxs-lookup"><span data-stu-id="f5616-118">In this example, `Get-Date` displays the current system date and time.</span></span> <span data-ttu-id="f5616-119">Выходные данные имеют формат длинной даты и длительное время.</span><span class="sxs-lookup"><span data-stu-id="f5616-119">The output is in the long-date and long-time formats.</span></span>

```powershell
Get-Date
```

```Output
Tuesday, June 25, 2019 14:53:32
```

### <span data-ttu-id="f5616-120">Пример 2. Получение элементов текущей даты и времени</span><span class="sxs-lookup"><span data-stu-id="f5616-120">Example 2: Get elements of the current date and time</span></span>

<span data-ttu-id="f5616-121">В этом примере показано, как использовать `Get-Date` для получения элемента даты или времени.</span><span class="sxs-lookup"><span data-stu-id="f5616-121">This example shows how to use `Get-Date` to get either the date or time element.</span></span> <span data-ttu-id="f5616-122">Параметр использует аргументы **Date**, **time** или **DateTime**.</span><span class="sxs-lookup"><span data-stu-id="f5616-122">The parameter uses the arguments **Date**, **Time**, or **DateTime**.</span></span>

```powershell
Get-Date -DisplayHint Date
```

```Output
Tuesday, June 25, 2019
```

<span data-ttu-id="f5616-123">`Get-Date` использует параметр **дисплайхинт** с аргументом **Date** , чтобы получить только дату.</span><span class="sxs-lookup"><span data-stu-id="f5616-123">`Get-Date` uses the **DisplayHint** parameter with the **Date** argument to get only the date.</span></span>

### <span data-ttu-id="f5616-124">Пример 3. Получение даты и времени с помощью описателя формата .NET</span><span class="sxs-lookup"><span data-stu-id="f5616-124">Example 3: Get the date and time with a .NET format specifier</span></span>

<span data-ttu-id="f5616-125">В этом примере используется описатель формата .NET для настройки формата вывода.</span><span class="sxs-lookup"><span data-stu-id="f5616-125">In this example, a .NET format specifier is used to customize the output's format.</span></span> <span data-ttu-id="f5616-126">Выходные данные представляют собой **строковый** объект.</span><span class="sxs-lookup"><span data-stu-id="f5616-126">The output is a **String** object.</span></span>

```powershell
Get-Date -Format "dddd MM/dd/yyyy HH:mm K"
```

```Output
Tuesday 06/25/2019 16:17 -07:00
```

<span data-ttu-id="f5616-127">`Get-Date` использует параметр **Format** для указания нескольких описателей формата.</span><span class="sxs-lookup"><span data-stu-id="f5616-127">`Get-Date` uses the **Format** parameter to specify several format specifiers.</span></span>

<span data-ttu-id="f5616-128">Описатели формата .NET, используемые в этом примере, определяются следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f5616-128">The .NET format specifiers used in this example are defined as follows:</span></span>

| <span data-ttu-id="f5616-129">Описатель</span><span class="sxs-lookup"><span data-stu-id="f5616-129">Specifier</span></span> |                      <span data-ttu-id="f5616-130">Определение</span><span class="sxs-lookup"><span data-stu-id="f5616-130">Definition</span></span>                       |
| --------- | ----------------------------------------------------- |
| `dddd`    | <span data-ttu-id="f5616-131">День недели — полное имя</span><span class="sxs-lookup"><span data-stu-id="f5616-131">Day of the week - full name</span></span>                           |
| `MM`      | <span data-ttu-id="f5616-132">Номер месяца.</span><span class="sxs-lookup"><span data-stu-id="f5616-132">Month number</span></span>                                          |
| `dd`      | <span data-ttu-id="f5616-133">День месяца-2 цифры</span><span class="sxs-lookup"><span data-stu-id="f5616-133">Day of the month - 2 digits</span></span>                           |
| `yyyy`    | <span data-ttu-id="f5616-134">Год в 4-значном формате</span><span class="sxs-lookup"><span data-stu-id="f5616-134">Year in 4-digit format</span></span>                                |
| `HH:mm`   | <span data-ttu-id="f5616-135">Время в 24-часовом формате — нет секунд</span><span class="sxs-lookup"><span data-stu-id="f5616-135">Time in 24-hour format - no seconds</span></span>                    |
| `K`       | <span data-ttu-id="f5616-136">Смещение часового пояса от универсальной координаты времени (UTC)</span><span class="sxs-lookup"><span data-stu-id="f5616-136">Time zone offset from Universal Time Coordinate (UTC)</span></span> |

<span data-ttu-id="f5616-137">Дополнительные сведения о спецификаторах формата .NET см. в разделе [строки настраиваемых форматов даты и времени](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span><span class="sxs-lookup"><span data-stu-id="f5616-137">For more information about .NET format specifiers, see [Custom date and time format strings](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span></span>

### <span data-ttu-id="f5616-138">Пример 4. Получение даты и времени с помощью описателя UFormat</span><span class="sxs-lookup"><span data-stu-id="f5616-138">Example 4: Get the date and time with a UFormat specifier</span></span>

<span data-ttu-id="f5616-139">В этом примере для настройки формата вывода используются несколько описателей формата **UFormat** .</span><span class="sxs-lookup"><span data-stu-id="f5616-139">In this example, several **UFormat** format specifiers are used to customize the output's format.</span></span>
<span data-ttu-id="f5616-140">Выходные данные представляют собой **строковый** объект.</span><span class="sxs-lookup"><span data-stu-id="f5616-140">The output is a **String** object.</span></span>

```powershell
Get-Date -UFormat "%A %m/%d/%Y %R %Z"
```

```Output
Tuesday 06/25/2019 16:19 -07
```

<span data-ttu-id="f5616-141">`Get-Date` использует параметр **UFormat** для указания нескольких описателей формата.</span><span class="sxs-lookup"><span data-stu-id="f5616-141">`Get-Date` uses the **UFormat** parameter to specify several format specifiers.</span></span>

<span data-ttu-id="f5616-142">Описатели формата **UFormat** , используемые в этом примере, определяются следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f5616-142">The **UFormat** format specifiers used in this example are defined as follows:</span></span>

| <span data-ttu-id="f5616-143">Описатель</span><span class="sxs-lookup"><span data-stu-id="f5616-143">Specifier</span></span> |                      <span data-ttu-id="f5616-144">Определение</span><span class="sxs-lookup"><span data-stu-id="f5616-144">Definition</span></span>                       |
| --------- | ----------------------------------------------------- |
| `%A`      | <span data-ttu-id="f5616-145">День недели — полное имя</span><span class="sxs-lookup"><span data-stu-id="f5616-145">Day of the week - full name</span></span>                           |
| `%m`      | <span data-ttu-id="f5616-146">Номер месяца.</span><span class="sxs-lookup"><span data-stu-id="f5616-146">Month number</span></span>                                          |
| `%d`      | <span data-ttu-id="f5616-147">День месяца-2 цифры</span><span class="sxs-lookup"><span data-stu-id="f5616-147">Day of the month - 2 digits</span></span>                           |
| `%Y`      | <span data-ttu-id="f5616-148">Год в 4-значном формате</span><span class="sxs-lookup"><span data-stu-id="f5616-148">Year in 4-digit format</span></span>                                |
| `%R`      | <span data-ttu-id="f5616-149">Время в 24-часовом формате — нет секунд</span><span class="sxs-lookup"><span data-stu-id="f5616-149">Time in 24-hour format - no seconds</span></span>                    |
| `%Z`      | <span data-ttu-id="f5616-150">Смещение часового пояса от универсальной координаты времени (UTC)</span><span class="sxs-lookup"><span data-stu-id="f5616-150">Time zone offset from Universal Time Coordinate (UTC)</span></span> |

<span data-ttu-id="f5616-151">Список допустимых описателей формата **UFormat** см. в разделе " [Примечания](#notes) ".</span><span class="sxs-lookup"><span data-stu-id="f5616-151">For a list of valid **UFormat** format specifiers, see the [Notes](#notes) section.</span></span>

### <span data-ttu-id="f5616-152">Пример 5. получение дня года для даты</span><span class="sxs-lookup"><span data-stu-id="f5616-152">Example 5: Get a date's day of the year</span></span>

<span data-ttu-id="f5616-153">В этом примере свойство используется для получения числового дня года.</span><span class="sxs-lookup"><span data-stu-id="f5616-153">In this example, a property is used to get the numeric day of the year.</span></span>

<span data-ttu-id="f5616-154">В григорианском календаре 365 дней, за исключением високосных лет, имеющих 366 дней.</span><span class="sxs-lookup"><span data-stu-id="f5616-154">The Gregorian calendar has 365 days, except for leap years that have 366 days.</span></span> <span data-ttu-id="f5616-155">Например, 31 декабря 2020 — это день 366.</span><span class="sxs-lookup"><span data-stu-id="f5616-155">For example, December 31, 2020 is day 366.</span></span>

```powershell
(Get-Date -Year 2020 -Month 12 -Day 31).DayOfYear
```

```Output
366
```

<span data-ttu-id="f5616-156">`Get-Date` использует три параметра для указания даты: **год**, **месяц** и **день**.</span><span class="sxs-lookup"><span data-stu-id="f5616-156">`Get-Date` uses three parameters to specify the date: **Year**, **Month**, and **Day**.</span></span> <span data-ttu-id="f5616-157">Команда заключена в круглые скобки, поэтому результат вычисляется свойством **DayofYear** .</span><span class="sxs-lookup"><span data-stu-id="f5616-157">The command is wrapped with parentheses so that the result is evaluated by the **DayofYear** property.</span></span>

### <span data-ttu-id="f5616-158">Пример 6. Проверка того, скорректирована ли дата на летнее время</span><span class="sxs-lookup"><span data-stu-id="f5616-158">Example 6: Check if a date is adjusted for daylight savings time</span></span>

<span data-ttu-id="f5616-159">В этом примере используется логический метод для проверки, корректируется ли дата на летнее время.</span><span class="sxs-lookup"><span data-stu-id="f5616-159">This example uses a boolean method to verify if a date is adjusted by daylight savings time.</span></span>

```powershell
$DST = Get-Date
$DST.IsDaylightSavingTime()
```

```Output
True
```

<span data-ttu-id="f5616-160">Переменная, `$DST` в которой хранится результат `Get-Date` .</span><span class="sxs-lookup"><span data-stu-id="f5616-160">A variable, `$DST` stores the result of `Get-Date`.</span></span> <span data-ttu-id="f5616-161">`$DST` проверяет, корректируется ли дата на летнее время, с помощью метода **исдайлигхтсавингтиме** .</span><span class="sxs-lookup"><span data-stu-id="f5616-161">`$DST` uses the **IsDaylightSavingTime** method to test if the date is adjusted for daylight savings time.</span></span>

### <span data-ttu-id="f5616-162">Пример 7. Преобразование текущего времени в время в формате UTC</span><span class="sxs-lookup"><span data-stu-id="f5616-162">Example 7: Convert the current time to UTC time</span></span>

<span data-ttu-id="f5616-163">В этом примере текущее время преобразуется в время в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="f5616-163">In this example, the current time is converted to UTC time.</span></span> <span data-ttu-id="f5616-164">Для преобразования времени используется смещение в формате UTC для языкового стандарта системы.</span><span class="sxs-lookup"><span data-stu-id="f5616-164">The UTC offset for the system's locale is used to convert the time.</span></span> <span data-ttu-id="f5616-165">В таблице в разделе " [Примечания](#notes) " перечислены допустимые описатели формата **UFormat** .</span><span class="sxs-lookup"><span data-stu-id="f5616-165">A table in the [Notes](#notes) section lists the valid **UFormat** format specifiers.</span></span>

```powershell
Get-Date -UFormat "%A %B/%d/%Y %T %Z"
$Time = Get-Date
$Time.ToUniversalTime()
```

```Output
Wednesday June/26/2019 10:45:26 -07

Wednesday, June 26, 2019 17:45:26
```

<span data-ttu-id="f5616-166">`Get-Date` использует параметр **UFormat** с описателями формата для вывода текущей системной даты и времени.</span><span class="sxs-lookup"><span data-stu-id="f5616-166">`Get-Date` uses the **UFormat** parameter with format specifiers to display the current system date and time.</span></span> <span data-ttu-id="f5616-167">Описатель формата **% Z** представляет смещение в формате UTC, равное **-07**.</span><span class="sxs-lookup"><span data-stu-id="f5616-167">The format specifier **%Z** represents the UTC offset of **-07**.</span></span>

<span data-ttu-id="f5616-168">`$Time`Переменная хранит текущую системную дату и время.</span><span class="sxs-lookup"><span data-stu-id="f5616-168">The `$Time` variable stores the current system date and time.</span></span> <span data-ttu-id="f5616-169">`$Time` использует метод **ToUniversalTime ()** для преобразования времени на основе смещения UTC компьютера.</span><span class="sxs-lookup"><span data-stu-id="f5616-169">`$Time` uses the **ToUniversalTime()** method to convert the time based on the computer's UTC offset.</span></span>

### <span data-ttu-id="f5616-170">Пример 8. Создание метки времени</span><span class="sxs-lookup"><span data-stu-id="f5616-170">Example 8: Create a timestamp</span></span>

<span data-ttu-id="f5616-171">В этом примере описатель формата создает объект **строки** метки времени для имени каталога.</span><span class="sxs-lookup"><span data-stu-id="f5616-171">In this example, a format specifier creates a timestamp **String** object for a directory name.</span></span> <span data-ttu-id="f5616-172">Метка времени включает дату, время и смещение в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="f5616-172">The timestamp includes the date, time, and UTC offset.</span></span>

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

<span data-ttu-id="f5616-173">`$timestamp`Переменная хранит результаты выполнения `Get-Date` команды.</span><span class="sxs-lookup"><span data-stu-id="f5616-173">The `$timestamp` variable stores the results of a `Get-Date` command.</span></span> <span data-ttu-id="f5616-174">`Get-Date` использует параметр **Format** с описателем формата "нижний регистр" `o` для создания объекта **строки** метки времени.</span><span class="sxs-lookup"><span data-stu-id="f5616-174">`Get-Date` uses the **Format** parameter with the format specifier of lowercase `o` to create a timestamp **String** object.</span></span> <span data-ttu-id="f5616-175">Объект отправляется по конвейеру в `ForEach-Object` .</span><span class="sxs-lookup"><span data-stu-id="f5616-175">The object is sent down the pipeline to `ForEach-Object`.</span></span> <span data-ttu-id="f5616-176">Блок **ScriptBlock** содержит `$_` переменную, представляющую текущий объект конвейера.</span><span class="sxs-lookup"><span data-stu-id="f5616-176">A **ScriptBlock** contains the `$_` variable that represents the current pipeline object.</span></span> <span data-ttu-id="f5616-177">Строка метки времени разделяются двоеточиями, которые заменяются точками.</span><span class="sxs-lookup"><span data-stu-id="f5616-177">The timestamp string is delimited by colons that are replaced by periods.</span></span>

<span data-ttu-id="f5616-178">`New-Item` использует параметр **path** для указания расположения нового каталога.</span><span class="sxs-lookup"><span data-stu-id="f5616-178">`New-Item` uses the **Path** parameter to specify the location for a new directory.</span></span> <span data-ttu-id="f5616-179">Путь включает `$timestamp` переменную в качестве имени каталога.</span><span class="sxs-lookup"><span data-stu-id="f5616-179">The path includes the `$timestamp` variable as the directory name.</span></span> <span data-ttu-id="f5616-180">Параметр **типа** указывает, что каталог создан.</span><span class="sxs-lookup"><span data-stu-id="f5616-180">The **Type** parameter specifies that a directory is created.</span></span>

### <span data-ttu-id="f5616-181">Пример 9. Преобразование метки времени Unix</span><span class="sxs-lookup"><span data-stu-id="f5616-181">Example 9: Convert a Unix timestamp</span></span>

<span data-ttu-id="f5616-182">В этом примере время в формате Unix (представленное количеством секунд с 0:00:00 01.01.1970) преобразуется в тип DateTime.</span><span class="sxs-lookup"><span data-stu-id="f5616-182">This example converts a Unix time (represented by the number of seconds since 1970-01-01 0:00:00) to DateTime.</span></span>

```powershell
Get-Date -UnixTimeSeconds 1577836800
```

```Output
Wednesday, January 01, 2020 12:00:00 AM
```

### <span data-ttu-id="f5616-183">Пример 10. Возврат значения даты, интерпретируемого как время в формате UTC</span><span class="sxs-lookup"><span data-stu-id="f5616-183">Example 10: Return a date value interpreted as UTC</span></span>

<span data-ttu-id="f5616-184">В этом примере показано, как интерпретировать значение даты как эквивалент UTC.</span><span class="sxs-lookup"><span data-stu-id="f5616-184">This example shows how to interpret a date value as its UTC equivalent.</span></span> <span data-ttu-id="f5616-185">Для этого примера этот компьютер настроен на **стандартное тихоокеанское время**.</span><span class="sxs-lookup"><span data-stu-id="f5616-185">For the example, this machine is set to **Pacific Standard Time**.</span></span> <span data-ttu-id="f5616-186">По умолчанию `Get-Date` возвращает значения для этого часового пояса.</span><span class="sxs-lookup"><span data-stu-id="f5616-186">By default, `Get-Date` returns values for that timezone.</span></span> <span data-ttu-id="f5616-187">Используйте параметр **асутк** , чтобы преобразовать значение в время в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="f5616-187">Use the **AsUTC** parameter to convert the value to the UTC equivalent time.</span></span>

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

## <span data-ttu-id="f5616-188">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f5616-188">PARAMETERS</span></span>

### <span data-ttu-id="f5616-189">-Асутк</span><span class="sxs-lookup"><span data-stu-id="f5616-189">-AsUTC</span></span>

<span data-ttu-id="f5616-190">Преобразует значение даты в эквивалентное время в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="f5616-190">Converts the date value to the equivalent time in UTC.</span></span>

<span data-ttu-id="f5616-191">Этот параметр появился в PowerShell 7,1.</span><span class="sxs-lookup"><span data-stu-id="f5616-191">This parameter was introduced in PowerShell 7.1.</span></span>

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

### <span data-ttu-id="f5616-192">-Date</span><span class="sxs-lookup"><span data-stu-id="f5616-192">-Date</span></span>

<span data-ttu-id="f5616-193">Указывает дату и время.</span><span class="sxs-lookup"><span data-stu-id="f5616-193">Specifies a date and time.</span></span> <span data-ttu-id="f5616-194">Время является необязательным и, если не указано, возвращает 00:00:00.</span><span class="sxs-lookup"><span data-stu-id="f5616-194">Time is optional and if not specified, returns 00:00:00.</span></span>

<span data-ttu-id="f5616-195">Введите дату и время в формате, стандартном для национальной настройки системы.</span><span class="sxs-lookup"><span data-stu-id="f5616-195">Enter the date and time in a format that is standard for the system locale.</span></span>

<span data-ttu-id="f5616-196">Например, на английском языке США:</span><span class="sxs-lookup"><span data-stu-id="f5616-196">For example, in US English:</span></span>

<span data-ttu-id="f5616-197">`Get-Date -Date "6/25/2019 12:30:22"` Возвращает вторник, 25 июня 2019 12:30:22</span><span class="sxs-lookup"><span data-stu-id="f5616-197">`Get-Date -Date "6/25/2019 12:30:22"` returns Tuesday, June 25, 2019 12:30:22</span></span>

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

### <span data-ttu-id="f5616-198">-Day</span><span class="sxs-lookup"><span data-stu-id="f5616-198">-Day</span></span>

<span data-ttu-id="f5616-199">Указывает выводимый день месяца.</span><span class="sxs-lookup"><span data-stu-id="f5616-199">Specifies the day of the month that is displayed.</span></span> <span data-ttu-id="f5616-200">Введите значение от 1 до 31.</span><span class="sxs-lookup"><span data-stu-id="f5616-200">Enter a value from 1 to 31.</span></span>

<span data-ttu-id="f5616-201">Если указанное значение больше числа дней в месяце, PowerShell добавляет число дней в месяц.</span><span class="sxs-lookup"><span data-stu-id="f5616-201">If the specified value is greater than the number of days in a month, PowerShell adds the number of days to the month.</span></span> <span data-ttu-id="f5616-202">Например, `Get-Date -Month 2 -Day 31` отображается **3 марта**, а не **31 февраля**.</span><span class="sxs-lookup"><span data-stu-id="f5616-202">For example, `Get-Date -Month 2 -Day 31` displays **March 3**, not **February 31**.</span></span>

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

### <span data-ttu-id="f5616-203">-DisplayHint</span><span class="sxs-lookup"><span data-stu-id="f5616-203">-DisplayHint</span></span>

<span data-ttu-id="f5616-204">Определяет, какие элементы даты и времени будут отображаться.</span><span class="sxs-lookup"><span data-stu-id="f5616-204">Determines which elements of the date and time are displayed.</span></span>

<span data-ttu-id="f5616-205">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f5616-205">The accepted values are as follows:</span></span>

- <span data-ttu-id="f5616-206">**Date:** отображается только дата;</span><span class="sxs-lookup"><span data-stu-id="f5616-206">**Date**: displays only the date</span></span>
- <span data-ttu-id="f5616-207">**Time:** отображается только время;</span><span class="sxs-lookup"><span data-stu-id="f5616-207">**Time**: displays only the time</span></span>
- <span data-ttu-id="f5616-208">**DateTime:** отображаются дата и время.</span><span class="sxs-lookup"><span data-stu-id="f5616-208">**DateTime**: displays the date and time</span></span>

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

### <span data-ttu-id="f5616-209">-Format</span><span class="sxs-lookup"><span data-stu-id="f5616-209">-Format</span></span>

<span data-ttu-id="f5616-210">Выводит дату и время в формате Microsoft .NET Framework, определяемом спецификатором формата.</span><span class="sxs-lookup"><span data-stu-id="f5616-210">Displays the date and time in the Microsoft .NET Framework format indicated by the format specifier.</span></span>
<span data-ttu-id="f5616-211">Параметр **Format** выводит **строковый** объект.</span><span class="sxs-lookup"><span data-stu-id="f5616-211">The **Format** parameter outputs a **String** object.</span></span>

<span data-ttu-id="f5616-212">Список доступных описателей формата .NET см. в разделе [строки настраиваемых форматов даты и времени](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span><span class="sxs-lookup"><span data-stu-id="f5616-212">For a list of available .NET format specifiers, see [Custom date and time format strings](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span></span>

<span data-ttu-id="f5616-213">При использовании параметра **Format** `Get-Date` получает только свойства объекта **DateTime** , необходимые для вывода даты.</span><span class="sxs-lookup"><span data-stu-id="f5616-213">When the **Format** parameter is used, `Get-Date` only gets the **DateTime** object's properties necessary to display the date.</span></span> <span data-ttu-id="f5616-214">Поэтому некоторые свойства и методы объекта **DateTime** могут быть недоступны.</span><span class="sxs-lookup"><span data-stu-id="f5616-214">As a result, some of the properties and methods of **DateTime** objects might not be available.</span></span>

<span data-ttu-id="f5616-215">Начиная с PowerShell 5,0, в качестве значений параметра **Format** можно использовать следующие дополнительные форматы.</span><span class="sxs-lookup"><span data-stu-id="f5616-215">Starting in PowerShell 5.0, you can use the following additional formats as values for the **Format** parameter.</span></span>

- <span data-ttu-id="f5616-216">**Филедате**.</span><span class="sxs-lookup"><span data-stu-id="f5616-216">**FileDate**.</span></span> <span data-ttu-id="f5616-217">Представление текущей даты в формате местного времени в файле или пути.</span><span class="sxs-lookup"><span data-stu-id="f5616-217">A file or path-friendly representation of the current date in local time.</span></span> <span data-ttu-id="f5616-218">Формат (с `yyyyMMdd` учетом регистра, с использованием 4-значного года, 2-значный месяц и день в 2 цифры).</span><span class="sxs-lookup"><span data-stu-id="f5616-218">The format is `yyyyMMdd` (case-sensitive, using a 4-digit year, 2-digit month, and 2-digit day).</span></span> <span data-ttu-id="f5616-219">Пример:</span><span class="sxs-lookup"><span data-stu-id="f5616-219">For example:</span></span>
  20190627.

- <span data-ttu-id="f5616-220">**Филедатеуниверсал**.</span><span class="sxs-lookup"><span data-stu-id="f5616-220">**FileDateUniversal**.</span></span> <span data-ttu-id="f5616-221">Представление текущей даты в формате UTC в виде файла или пути.</span><span class="sxs-lookup"><span data-stu-id="f5616-221">A file or path-friendly representation of the current date in universal time (UTC).</span></span> <span data-ttu-id="f5616-222">Формат (с `yyyyMMddZ` учетом регистра, с использованием 4-разрядного года, месяца, 2 цифры и буквы в `Z` качестве индикатора времени в формате UTC).</span><span class="sxs-lookup"><span data-stu-id="f5616-222">The format is `yyyyMMddZ` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, and the letter `Z` as the UTC indicator).</span></span> <span data-ttu-id="f5616-223">Например: 20190627Z.</span><span class="sxs-lookup"><span data-stu-id="f5616-223">For example: 20190627Z.</span></span>

- <span data-ttu-id="f5616-224">**Филедатетиме**.</span><span class="sxs-lookup"><span data-stu-id="f5616-224">**FileDateTime**.</span></span> <span data-ttu-id="f5616-225">Представление текущей даты и времени по местному времени в 24-часовом формате в виде файла или пути.</span><span class="sxs-lookup"><span data-stu-id="f5616-225">A file or path-friendly representation of the current date and time in local time, in 24-hour format.</span></span> <span data-ttu-id="f5616-226">Формат (с `yyyyMMddTHHmmssffff` учетом регистра, с использованием 4-разрядного года, 2-значный месяц, с двумя цифрами, буква в `T` качестве разделителя времени, 2-значный час, 2-значная минута, 2-значная секунда и 4-значная миллисекунда).</span><span class="sxs-lookup"><span data-stu-id="f5616-226">The format is `yyyyMMddTHHmmssffff` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, the letter `T` as a time separator, 2-digit hour, 2-digit minute, 2-digit second, and 4-digit millisecond).</span></span> <span data-ttu-id="f5616-227">Например: 20190627T0840107271.</span><span class="sxs-lookup"><span data-stu-id="f5616-227">For example: 20190627T0840107271.</span></span>

- <span data-ttu-id="f5616-228">**Филедатетимеуниверсал**.</span><span class="sxs-lookup"><span data-stu-id="f5616-228">**FileDateTimeUniversal**.</span></span> <span data-ttu-id="f5616-229">Представление текущей даты и времени в формате UTC в 24-часовом виде файла или пути.</span><span class="sxs-lookup"><span data-stu-id="f5616-229">A file or path-friendly representation of the current date and time in universal time (UTC), in 24-hour format.</span></span> <span data-ttu-id="f5616-230">Формат (с `yyyyMMddTHHmmssffffZ` учетом регистра, с использованием 4-разрядного года, 2-значного месяца, буквы в 2 цифры, буква в `T` качестве разделителя времени, 2-значный час, 2-значная минута, 2-значная секунда, 4-разрядная миллисекунда и букву в `Z` качестве индикатора времени в формате UTC).</span><span class="sxs-lookup"><span data-stu-id="f5616-230">The format is `yyyyMMddTHHmmssffffZ` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, the letter `T` as a time separator, 2-digit hour, 2-digit minute, 2-digit second, 4-digit millisecond, and the letter `Z` as the UTC indicator).</span></span> <span data-ttu-id="f5616-231">Например: 20190627T1540500718Z.</span><span class="sxs-lookup"><span data-stu-id="f5616-231">For example: 20190627T1540500718Z.</span></span>

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

### <span data-ttu-id="f5616-232">-Hour</span><span class="sxs-lookup"><span data-stu-id="f5616-232">-Hour</span></span>

<span data-ttu-id="f5616-233">Указывает выводимый час.</span><span class="sxs-lookup"><span data-stu-id="f5616-233">Specifies the hour that is displayed.</span></span> <span data-ttu-id="f5616-234">Введите значение от 0 до 23.</span><span class="sxs-lookup"><span data-stu-id="f5616-234">Enter a value from 0 to 23.</span></span>

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

### <span data-ttu-id="f5616-235">-Millisecond</span><span class="sxs-lookup"><span data-stu-id="f5616-235">-Millisecond</span></span>

<span data-ttu-id="f5616-236">Указывает миллисекунды в дате.</span><span class="sxs-lookup"><span data-stu-id="f5616-236">Specifies the milliseconds in the date.</span></span> <span data-ttu-id="f5616-237">Введите значение от 0 до 999.</span><span class="sxs-lookup"><span data-stu-id="f5616-237">Enter a value from 0 to 999.</span></span>

<span data-ttu-id="f5616-238">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="f5616-238">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="f5616-239">-Minute</span><span class="sxs-lookup"><span data-stu-id="f5616-239">-Minute</span></span>

<span data-ttu-id="f5616-240">Указывает выводимую минуту.</span><span class="sxs-lookup"><span data-stu-id="f5616-240">Specifies the minute that is displayed.</span></span> <span data-ttu-id="f5616-241">Введите значение от 0 до 59.</span><span class="sxs-lookup"><span data-stu-id="f5616-241">Enter a value from 0 to 59.</span></span>

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

### <span data-ttu-id="f5616-242">-Month</span><span class="sxs-lookup"><span data-stu-id="f5616-242">-Month</span></span>

<span data-ttu-id="f5616-243">Указывает выводимый месяц.</span><span class="sxs-lookup"><span data-stu-id="f5616-243">Specifies the month that is displayed.</span></span> <span data-ttu-id="f5616-244">Введите значение от 1 до 12.</span><span class="sxs-lookup"><span data-stu-id="f5616-244">Enter a value from 1 to 12.</span></span>

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

### <span data-ttu-id="f5616-245">-Second</span><span class="sxs-lookup"><span data-stu-id="f5616-245">-Second</span></span>

<span data-ttu-id="f5616-246">Указывает выводимую секунду.</span><span class="sxs-lookup"><span data-stu-id="f5616-246">Specifies the second that is displayed.</span></span> <span data-ttu-id="f5616-247">Введите значение от 0 до 59.</span><span class="sxs-lookup"><span data-stu-id="f5616-247">Enter a value from 0 to 59.</span></span>

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

### <span data-ttu-id="f5616-248">-UFormat</span><span class="sxs-lookup"><span data-stu-id="f5616-248">-UFormat</span></span>

<span data-ttu-id="f5616-249">Выводит дату и время в формате UNIX.</span><span class="sxs-lookup"><span data-stu-id="f5616-249">Displays the date and time in UNIX format.</span></span> <span data-ttu-id="f5616-250">Параметр **UFormat** выводит строковый объект.</span><span class="sxs-lookup"><span data-stu-id="f5616-250">The **UFormat** parameter outputs a string object.</span></span>

<span data-ttu-id="f5616-251">Спецификаторам **UFormat** предшествует знак процента (), например,, `%` `%m` `%d` и `%Y` .</span><span class="sxs-lookup"><span data-stu-id="f5616-251">**UFormat** specifiers are preceded by a percent sign (`%`), for example, `%m`, `%d`, and `%Y`.</span></span> <span data-ttu-id="f5616-252">В разделе " [Примечания](#notes) " содержится таблица допустимых **описателей UFormat**.</span><span class="sxs-lookup"><span data-stu-id="f5616-252">The [Notes](#notes) section contains a table of valid **UFormat specifiers**.</span></span>

<span data-ttu-id="f5616-253">При использовании параметра **UFormat** `Get-Date` получает только свойства объекта **DateTime** , необходимые для вывода даты.</span><span class="sxs-lookup"><span data-stu-id="f5616-253">When the **UFormat** parameter is used, `Get-Date` only gets the **DateTime** object's properties necessary to display the date.</span></span> <span data-ttu-id="f5616-254">Поэтому некоторые свойства и методы объекта **DateTime** могут быть недоступны.</span><span class="sxs-lookup"><span data-stu-id="f5616-254">As a result, some of the properties and methods of **DateTime** objects might not be available.</span></span>

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

### <span data-ttu-id="f5616-255">-Уникстимесекондс</span><span class="sxs-lookup"><span data-stu-id="f5616-255">-UnixTimeSeconds</span></span>

<span data-ttu-id="f5616-256">Дата и время, представленные в секундах с 1 января 1970 0:00:00.</span><span class="sxs-lookup"><span data-stu-id="f5616-256">Date and time represented in seconds since January 1, 1970, 0:00:00.</span></span>

<span data-ttu-id="f5616-257">Этот параметр появился в PowerShell 7,1.</span><span class="sxs-lookup"><span data-stu-id="f5616-257">This parameter was introduced in PowerShell 7.1.</span></span>

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

### <span data-ttu-id="f5616-258">-Year</span><span class="sxs-lookup"><span data-stu-id="f5616-258">-Year</span></span>

<span data-ttu-id="f5616-259">Указывает выводимый год.</span><span class="sxs-lookup"><span data-stu-id="f5616-259">Specifies the year that is displayed.</span></span> <span data-ttu-id="f5616-260">Введите значение от 1 до 9999.</span><span class="sxs-lookup"><span data-stu-id="f5616-260">Enter a value from 1 to 9999.</span></span>

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

### <span data-ttu-id="f5616-261">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="f5616-261">CommonParameters</span></span>

<span data-ttu-id="f5616-262">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f5616-262">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f5616-263">См. сведения в разделе [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f5616-263">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f5616-264">Входные данные</span><span class="sxs-lookup"><span data-stu-id="f5616-264">INPUTS</span></span>

### <span data-ttu-id="f5616-265">Входные данные конвейера</span><span class="sxs-lookup"><span data-stu-id="f5616-265">Pipeline input</span></span>

<span data-ttu-id="f5616-266">`Get-Date` принимает входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="f5616-266">`Get-Date` accepts pipeline input.</span></span> <span data-ttu-id="f5616-267">Например, `Get-ChildItem | Get-Date`.</span><span class="sxs-lookup"><span data-stu-id="f5616-267">For example, `Get-ChildItem | Get-Date`.</span></span>

## <span data-ttu-id="f5616-268">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="f5616-268">OUTPUTS</span></span>

### <span data-ttu-id="f5616-269">System.DateTime или System.String</span><span class="sxs-lookup"><span data-stu-id="f5616-269">System.DateTime or System.String</span></span>

<span data-ttu-id="f5616-270">`Get-Date` Возвращает объект **DateTime** , за исключением случаев, когда используются параметры **Format** и **UFormat** .</span><span class="sxs-lookup"><span data-stu-id="f5616-270">`Get-Date` returns a **DateTime** object except when the **Format** and **UFormat** parameters are used.</span></span> <span data-ttu-id="f5616-271">Параметры **Format** или **UFormat** возвращают **строковые** объекты.</span><span class="sxs-lookup"><span data-stu-id="f5616-271">The **Format** or **UFormat** parameters return **String** objects.</span></span>

<span data-ttu-id="f5616-272">Когда объект **DateTime** отправляется по конвейеру в командлет, например, при `Add-Content` ожидании ввода строки, PowerShell преобразует объект в **строковый** объект.</span><span class="sxs-lookup"><span data-stu-id="f5616-272">When a **DateTime** object is sent down the pipeline to a cmdlet such as `Add-Content` that expects string input, PowerShell converts the object to a **String** object.</span></span>

<span data-ttu-id="f5616-273">Метод `(Get-Date).ToString()` преобразует объект **DateTime** в объект **String** .</span><span class="sxs-lookup"><span data-stu-id="f5616-273">The method `(Get-Date).ToString()` converts a **DateTime** object a **String** object.</span></span>

<span data-ttu-id="f5616-274">Чтобы отобразить свойства и методы объекта, отправьте объект по конвейеру в `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="f5616-274">To display an object's properties and methods, send the object down the pipeline to `Get-Member`.</span></span>
<span data-ttu-id="f5616-275">Например, `Get-Date | Get-Member`.</span><span class="sxs-lookup"><span data-stu-id="f5616-275">For example, `Get-Date | Get-Member`.</span></span>

## <span data-ttu-id="f5616-276">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="f5616-276">NOTES</span></span>

<span data-ttu-id="f5616-277">Объекты **DateTime** имеют формат длинной даты и длительное время для национальной настройки системы.</span><span class="sxs-lookup"><span data-stu-id="f5616-277">**DateTime** objects are in long-date and long-time formats for the system locale.</span></span>

<span data-ttu-id="f5616-278">В следующей таблице показаны допустимые **описатели UFormat** .</span><span class="sxs-lookup"><span data-stu-id="f5616-278">The valid **UFormat specifiers** are displayed in the following table:</span></span>

| <span data-ttu-id="f5616-279">Описатель формата</span><span class="sxs-lookup"><span data-stu-id="f5616-279">Format specifier</span></span> |                                 <span data-ttu-id="f5616-280">Значение</span><span class="sxs-lookup"><span data-stu-id="f5616-280">Meaning</span></span>                     |         <span data-ttu-id="f5616-281">Пример</span><span class="sxs-lookup"><span data-stu-id="f5616-281">Example</span></span>          |
| ---- | ----------------------------------------------------------------------- | ------------------------ |
| `%A` | <span data-ttu-id="f5616-282">День недели — полное имя</span><span class="sxs-lookup"><span data-stu-id="f5616-282">Day of the week - full name</span></span>                                             | <span data-ttu-id="f5616-283">Понедельник</span><span class="sxs-lookup"><span data-stu-id="f5616-283">Monday</span></span>                   |
| `%a` | <span data-ttu-id="f5616-284">День в сокращенном названии недели</span><span class="sxs-lookup"><span data-stu-id="f5616-284">Day of the week - abbreviated name</span></span>                                      | <span data-ttu-id="f5616-285">Mon</span><span class="sxs-lookup"><span data-stu-id="f5616-285">Mon</span></span>                      |
| `%B` | <span data-ttu-id="f5616-286">Имя месяца — полное</span><span class="sxs-lookup"><span data-stu-id="f5616-286">Month name - full</span></span>                                                       | <span data-ttu-id="f5616-287">Январь</span><span class="sxs-lookup"><span data-stu-id="f5616-287">January</span></span>                  |
| `%b` | <span data-ttu-id="f5616-288">Название месяца — сокращенное</span><span class="sxs-lookup"><span data-stu-id="f5616-288">Month name - abbreviated</span></span>                                                | <span data-ttu-id="f5616-289">Январь</span><span class="sxs-lookup"><span data-stu-id="f5616-289">Jan</span></span>                      |
| `%C` | <span data-ttu-id="f5616-290">Век</span><span class="sxs-lookup"><span data-stu-id="f5616-290">Century</span></span>                                                                 | <span data-ttu-id="f5616-291">20 для 2019</span><span class="sxs-lookup"><span data-stu-id="f5616-291">20 for 2019</span></span>              |
| `%c` | <span data-ttu-id="f5616-292">Дата и время-сокращенные</span><span class="sxs-lookup"><span data-stu-id="f5616-292">Date and time - abbreviated</span></span>                                             | <span data-ttu-id="f5616-293">Четверг июня 27 08:44:18 2019</span><span class="sxs-lookup"><span data-stu-id="f5616-293">Thu Jun 27 08:44:18 2019</span></span> |
| `%D` | <span data-ttu-id="f5616-294">Дата в формате мм/дд/гг</span><span class="sxs-lookup"><span data-stu-id="f5616-294">Date in mm/dd/yy format</span></span>                                                 | <span data-ttu-id="f5616-295">06/27/19</span><span class="sxs-lookup"><span data-stu-id="f5616-295">06/27/19</span></span>                 |
| `%d` | <span data-ttu-id="f5616-296">День месяца-2 цифры</span><span class="sxs-lookup"><span data-stu-id="f5616-296">Day of the month - 2 digits</span></span>                                             | <span data-ttu-id="f5616-297">05</span><span class="sxs-lookup"><span data-stu-id="f5616-297">05</span></span>                       |
| `%e` | <span data-ttu-id="f5616-298">День месяца — предшествует пробел, если только одна цифра</span><span class="sxs-lookup"><span data-stu-id="f5616-298">Day of the month - preceded by a space if only a single digit</span></span>           | <span data-ttu-id="f5616-299">\<space\>5.0</span><span class="sxs-lookup"><span data-stu-id="f5616-299">\<space\>5</span></span>               |
| `%F` | <span data-ttu-id="f5616-300">Дата в формате гггг-мм-дд равна% Y-% m-% d (формат даты ISO 8601)</span><span class="sxs-lookup"><span data-stu-id="f5616-300">Date in YYYY-mm-dd format, equal to %Y-%m-%d (the ISO 8601 date format)</span></span> | <span data-ttu-id="f5616-301">2019-06-27</span><span class="sxs-lookup"><span data-stu-id="f5616-301">2019-06-27</span></span>               |
| `%G` | <span data-ttu-id="f5616-302">То же, что "Y"</span><span class="sxs-lookup"><span data-stu-id="f5616-302">Same as 'Y'</span></span>                                                             |                          |
| `%g` | <span data-ttu-id="f5616-303">То же, что "y"</span><span class="sxs-lookup"><span data-stu-id="f5616-303">Same as 'y'</span></span>                                                             |                          |
| `%H` | <span data-ttu-id="f5616-304">Час в 24-часовом формате</span><span class="sxs-lookup"><span data-stu-id="f5616-304">Hour in 24-hour format</span></span>                                                  | <span data-ttu-id="f5616-305">17</span><span class="sxs-lookup"><span data-stu-id="f5616-305">17</span></span>                       |
| `%h` | <span data-ttu-id="f5616-306">То же, что "b"</span><span class="sxs-lookup"><span data-stu-id="f5616-306">Same as 'b'</span></span>                                                             |                          |
| `%I` | <span data-ttu-id="f5616-307">Час в 12-часовом формате</span><span class="sxs-lookup"><span data-stu-id="f5616-307">Hour in 12-hour format</span></span>                                                  | <span data-ttu-id="f5616-308">05</span><span class="sxs-lookup"><span data-stu-id="f5616-308">05</span></span>                       |
| `%j` | <span data-ttu-id="f5616-309">День года</span><span class="sxs-lookup"><span data-stu-id="f5616-309">Day of the year</span></span>                                                         | <span data-ttu-id="f5616-310">1-366</span><span class="sxs-lookup"><span data-stu-id="f5616-310">1-366</span></span>                    |
| `%k` | <span data-ttu-id="f5616-311">То же, что "H"</span><span class="sxs-lookup"><span data-stu-id="f5616-311">Same as 'H'</span></span>                                                             |                          |
| `%l` | <span data-ttu-id="f5616-312">То же, что "I" (верхний регистр I)</span><span class="sxs-lookup"><span data-stu-id="f5616-312">Same as 'I' (Upper-case I)</span></span>                                              | <span data-ttu-id="f5616-313">05</span><span class="sxs-lookup"><span data-stu-id="f5616-313">05</span></span>                       |
| `%M` | <span data-ttu-id="f5616-314">Минуты</span><span class="sxs-lookup"><span data-stu-id="f5616-314">Minutes</span></span>                                                                 | <span data-ttu-id="f5616-315">35</span><span class="sxs-lookup"><span data-stu-id="f5616-315">35</span></span>                       |
| `%m` | <span data-ttu-id="f5616-316">Номер месяца.</span><span class="sxs-lookup"><span data-stu-id="f5616-316">Month number</span></span>                                                            | <span data-ttu-id="f5616-317">06</span><span class="sxs-lookup"><span data-stu-id="f5616-317">06</span></span>                       |
| `%n` | <span data-ttu-id="f5616-318">символ новой строки</span><span class="sxs-lookup"><span data-stu-id="f5616-318">newline character</span></span>                                                       |                          |
| `%p` | <span data-ttu-id="f5616-319">AM или PM</span><span class="sxs-lookup"><span data-stu-id="f5616-319">AM or PM</span></span>                                                                |                          |
| `%R` | <span data-ttu-id="f5616-320">Время в 24-часовом формате — нет секунд</span><span class="sxs-lookup"><span data-stu-id="f5616-320">Time in 24-hour format -no seconds</span></span>                                      | <span data-ttu-id="f5616-321">17:45</span><span class="sxs-lookup"><span data-stu-id="f5616-321">17:45</span></span>                    |
| `%r` | <span data-ttu-id="f5616-322">Время в 12-часовом формате</span><span class="sxs-lookup"><span data-stu-id="f5616-322">Time in 12-hour format</span></span>                                                  | <span data-ttu-id="f5616-323">09:15:36 AM</span><span class="sxs-lookup"><span data-stu-id="f5616-323">09:15:36 AM</span></span>              |
| `%S` | <span data-ttu-id="f5616-324">Секунды</span><span class="sxs-lookup"><span data-stu-id="f5616-324">Seconds</span></span>                                                                 | <span data-ttu-id="f5616-325">05</span><span class="sxs-lookup"><span data-stu-id="f5616-325">05</span></span>                       |
| `%s` | <span data-ttu-id="f5616-326">Секунды, прошедшие с 1 января 1970 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f5616-326">Seconds elapsed since January 1, 1970 00:00:00</span></span>                          | <span data-ttu-id="f5616-327">1150451174</span><span class="sxs-lookup"><span data-stu-id="f5616-327">1150451174</span></span>               |
| `%t` | <span data-ttu-id="f5616-328">Символ горизонтальной табуляции</span><span class="sxs-lookup"><span data-stu-id="f5616-328">Horizontal tab character</span></span>                                                |                          |
| `%T` | <span data-ttu-id="f5616-329">Время в 24-часовом формате</span><span class="sxs-lookup"><span data-stu-id="f5616-329">Time in 24-hour format</span></span>                                                  | <span data-ttu-id="f5616-330">17:45:52</span><span class="sxs-lookup"><span data-stu-id="f5616-330">17:45:52</span></span>                 |
| `%U` | <span data-ttu-id="f5616-331">То же, что "W"</span><span class="sxs-lookup"><span data-stu-id="f5616-331">Same as 'W'</span></span>                                                             |                          |
| `%u` | <span data-ttu-id="f5616-332">Числовой день недели (1-7)</span><span class="sxs-lookup"><span data-stu-id="f5616-332">Numeric day of the week (1-7)</span></span>                                           | <span data-ttu-id="f5616-333">Понедельник = 1, воскресенье = 7</span><span class="sxs-lookup"><span data-stu-id="f5616-333">Monday = 1, Sunday = 7</span></span>   |
| `%V` | <span data-ttu-id="f5616-334">Неделя года</span><span class="sxs-lookup"><span data-stu-id="f5616-334">Week of the year</span></span>                                                        | <span data-ttu-id="f5616-335">01-53</span><span class="sxs-lookup"><span data-stu-id="f5616-335">01-53</span></span>                    |
| `%w` | <span data-ttu-id="f5616-336">Числовой день недели (0-6)</span><span class="sxs-lookup"><span data-stu-id="f5616-336">Numeric day of the week (0-6)</span></span>                                           | <span data-ttu-id="f5616-337">Воскресенье = 0, суббота = 6</span><span class="sxs-lookup"><span data-stu-id="f5616-337">Sunday = 0, Saturday = 6</span></span> |
| `%W` | <span data-ttu-id="f5616-338">Неделя года</span><span class="sxs-lookup"><span data-stu-id="f5616-338">Week of the year</span></span>                                                        | <span data-ttu-id="f5616-339">00-52</span><span class="sxs-lookup"><span data-stu-id="f5616-339">00-52</span></span>                    |
| `%X` | <span data-ttu-id="f5616-340">То же, что 'T»</span><span class="sxs-lookup"><span data-stu-id="f5616-340">Same as 'T'</span></span>                                                             |                          |
| `%x` | <span data-ttu-id="f5616-341">Дата в стандартном формате для языкового стандарта</span><span class="sxs-lookup"><span data-stu-id="f5616-341">Date in standard format for locale</span></span>                                      | <span data-ttu-id="f5616-342">06/27/19 для английского языка США</span><span class="sxs-lookup"><span data-stu-id="f5616-342">06/27/19 for English-US</span></span>  |
| `%Y` | <span data-ttu-id="f5616-343">Год в 4-значном формате</span><span class="sxs-lookup"><span data-stu-id="f5616-343">Year in 4-digit format</span></span>                                                  | <span data-ttu-id="f5616-344">2019</span><span class="sxs-lookup"><span data-stu-id="f5616-344">2019</span></span>                     |
| `%y` | <span data-ttu-id="f5616-345">Год в формате 2 цифр</span><span class="sxs-lookup"><span data-stu-id="f5616-345">Year in 2-digit format</span></span>                                                  | <span data-ttu-id="f5616-346">19</span><span class="sxs-lookup"><span data-stu-id="f5616-346">19</span></span>                       |
| `%Z` | <span data-ttu-id="f5616-347">Смещение часового пояса от универсальной координаты времени (UTC)</span><span class="sxs-lookup"><span data-stu-id="f5616-347">Time zone offset from Universal Time Coordinate (UTC)</span></span>                   | <span data-ttu-id="f5616-348">-07</span><span class="sxs-lookup"><span data-stu-id="f5616-348">-07</span></span>                      |

## <span data-ttu-id="f5616-349">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="f5616-349">RELATED LINKS</span></span>

[<span data-ttu-id="f5616-350">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="f5616-350">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="f5616-351">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="f5616-351">Get-Culture</span></span>](Get-Culture.md)

[<span data-ttu-id="f5616-352">Get-Member</span><span class="sxs-lookup"><span data-stu-id="f5616-352">Get-Member</span></span>](Get-Member.md)

[<span data-ttu-id="f5616-353">New-Item</span><span class="sxs-lookup"><span data-stu-id="f5616-353">New-Item</span></span>](../Microsoft.PowerShell.Management/New-Item.md)

[<span data-ttu-id="f5616-354">New-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="f5616-354">New-TimeSpan</span></span>](New-TimeSpan.md)

[<span data-ttu-id="f5616-355">Set-Date</span><span class="sxs-lookup"><span data-stu-id="f5616-355">Set-Date</span></span>](Set-Date.md)
