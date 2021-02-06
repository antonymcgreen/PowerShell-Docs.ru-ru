---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/01/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-timespan?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-TimeSpan
ms.openlocfilehash: 5808685a5560d1cbf91c6705b90643c35702b28a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603955"
---
# <span data-ttu-id="4513d-102">New-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="4513d-102">New-TimeSpan</span></span>

## <span data-ttu-id="4513d-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4513d-103">SYNOPSIS</span></span>
<span data-ttu-id="4513d-104">Создает объект TimeSpan.</span><span class="sxs-lookup"><span data-stu-id="4513d-104">Creates a TimeSpan object.</span></span>

## <span data-ttu-id="4513d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4513d-105">SYNTAX</span></span>

### <span data-ttu-id="4513d-106">Дата (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="4513d-106">Date (Default)</span></span>

```
New-TimeSpan [[-Start] <DateTime>] [[-End] <DateTime>] [<CommonParameters>]
```

### <span data-ttu-id="4513d-107">время;</span><span class="sxs-lookup"><span data-stu-id="4513d-107">Time</span></span>

```
New-TimeSpan [-Days <Int32>] [-Hours <Int32>] [-Minutes <Int32>] [-Seconds <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="4513d-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4513d-108">DESCRIPTION</span></span>

<span data-ttu-id="4513d-109">`New-TimeSpan`Командлет создает объект **TimeSpan** , представляющий интервал времени.</span><span class="sxs-lookup"><span data-stu-id="4513d-109">The `New-TimeSpan` cmdlet creates a **TimeSpan** object that represents a time interval.</span></span>
<span data-ttu-id="4513d-110">Объект **TimeSpan** можно использовать для добавления или вычитания времени из объектов **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="4513d-110">You can use a **TimeSpan** object to add or subtract time from **DateTime** objects.</span></span>

<span data-ttu-id="4513d-111">Без параметров `New-TimeSpan` команда возвращает объект **TimeSpan** , представляющий интервал времени, равный нулю.</span><span class="sxs-lookup"><span data-stu-id="4513d-111">Without parameters, a `New-TimeSpan` command returns a **TimeSpan** object that represents a time interval of zero.</span></span>

## <span data-ttu-id="4513d-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="4513d-112">EXAMPLES</span></span>

### <span data-ttu-id="4513d-113">Пример 1. Создание объекта TimeSpan на указанный период</span><span class="sxs-lookup"><span data-stu-id="4513d-113">Example 1: Create a TimeSpan object for a specified duration</span></span>

<span data-ttu-id="4513d-114">Эта команда создает объект **TimeSpan** с длительностью в 1 час и 25 минут и сохраняет его в переменной с именем `$TimeSpan` .</span><span class="sxs-lookup"><span data-stu-id="4513d-114">This command creates a **TimeSpan** object with a duration of 1 hour and 25 minutes and stores it in a variable named `$TimeSpan`.</span></span> <span data-ttu-id="4513d-115">Он отображает представление объекта **TimeSpan** .</span><span class="sxs-lookup"><span data-stu-id="4513d-115">It displays a representation of the **TimeSpan** object.</span></span>

```powershell
$TimeSpan = New-TimeSpan -Hours 1 -Minutes 25
$TimeSpan
```

```Output
Days              : 0
Hours             : 1
Minutes           : 25
Seconds           : 0
Milliseconds      : 0
Ticks             : 51000000000
TotalDays         : 0.0590277777777778
TotalHours        : 1.41666666666667
TotalMinutes      : 85
TotalSeconds      : 5100
TotalMilliseconds : 5100000
```

### <span data-ttu-id="4513d-116">Пример 2. Создание объекта TimeSpan для интервала времени</span><span class="sxs-lookup"><span data-stu-id="4513d-116">Example 2: Create a TimeSpan object for a time interval</span></span>

<span data-ttu-id="4513d-117">В этом примере создается новый объект **TimeSpan** , представляющий интервал между временем выполнения команды и 1 января 2010.</span><span class="sxs-lookup"><span data-stu-id="4513d-117">This example creates a new **TimeSpan** object that represents the interval between the time that the command is run and January 1, 2010.</span></span>

<span data-ttu-id="4513d-118">Эта команда не требует параметра **Start** , так как значением по умолчанию для параметра **Start** является текущая дата и время.</span><span class="sxs-lookup"><span data-stu-id="4513d-118">This command does not require the **Start** parameter, because the default value of the **Start** parameter is the current date and time.</span></span>

```powershell
New-TimeSpan -End (Get-Date -Year 2010 -Month 1 -Day 1)
```

### <span data-ttu-id="4513d-119">Пример 3. Получение даты 90 дней с текущей даты</span><span class="sxs-lookup"><span data-stu-id="4513d-119">Example 3: Get the date 90 days from the current date</span></span>

```powershell
$90days = New-TimeSpan -Days 90
(Get-Date) + $90days
```

<span data-ttu-id="4513d-120">Эти команды возвращают дату на 90 дней позднее текущей.</span><span class="sxs-lookup"><span data-stu-id="4513d-120">These commands return the date that is 90 days after the current date.</span></span>

### <span data-ttu-id="4513d-121">Пример 4. Обнаружение TimeSpan с момента обновления файла</span><span class="sxs-lookup"><span data-stu-id="4513d-121">Example 4: Discover the TimeSpan since a file was updated</span></span>

<span data-ttu-id="4513d-122">Эта команда указывает, сколько времени прошло с момента последнего обновления файла справки [about_remote](../Microsoft.PowerShell.Core/About/about_Remote.md) .</span><span class="sxs-lookup"><span data-stu-id="4513d-122">This command tells you how long it has been since the [about_remote](../Microsoft.PowerShell.Core/About/about_Remote.md) help file was last updated.</span></span>
<span data-ttu-id="4513d-123">Этот формат команды можно использовать для любого файла или любого другого объекта, имеющего свойство **LastWriteTime** .</span><span class="sxs-lookup"><span data-stu-id="4513d-123">You can use this command format on any file, or any other object that has a **LastWriteTime** property.</span></span>

<span data-ttu-id="4513d-124">Эта команда работает, так как параметр **Start** параметра `New-TimeSpan` имеет псевдоним **LastWriteTime**.</span><span class="sxs-lookup"><span data-stu-id="4513d-124">This command works because the **Start** parameter of `New-TimeSpan` has an alias of **LastWriteTime**.</span></span> <span data-ttu-id="4513d-125">При передаче объекта, имеющего свойство **LastWriteTime** `New-TimeSpan` , в PowerShell использует значение свойства **LastWriteTime** в качестве значения параметра **Start** .</span><span class="sxs-lookup"><span data-stu-id="4513d-125">When you pipe an object that has a **LastWriteTime** property to `New-TimeSpan`, PowerShell uses the value of the **LastWriteTime** property as the value of the **Start** parameter.</span></span>

```powershell
Get-ChildItem $PSHOME\en-us\about_remote.help.txt | New-TimeSpan
```

```Output
Days              : 321
Hours             : 21
Minutes           : 59
Seconds           : 22
Milliseconds      : 312
Ticks             : 278135623127728
TotalDays         : 321.916230471907
TotalHours        : 7725.98953132578
TotalMinutes      : 463559.371879547
TotalSeconds      : 27813562.3127728
TotalMilliseconds : 27813562312.7728
```

## <span data-ttu-id="4513d-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4513d-126">PARAMETERS</span></span>

### <span data-ttu-id="4513d-127">-Days</span><span class="sxs-lookup"><span data-stu-id="4513d-127">-Days</span></span>

<span data-ttu-id="4513d-128">Указывает дни в интервале времени.</span><span class="sxs-lookup"><span data-stu-id="4513d-128">Specifies the days in the time span.</span></span>
<span data-ttu-id="4513d-129">Значение по умолчанию — 0.</span><span class="sxs-lookup"><span data-stu-id="4513d-129">The default value is 0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Time
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4513d-130">-End</span><span class="sxs-lookup"><span data-stu-id="4513d-130">-End</span></span>

<span data-ttu-id="4513d-131">Задает конец интервала времени.</span><span class="sxs-lookup"><span data-stu-id="4513d-131">Specifies the end of a time span.</span></span>
<span data-ttu-id="4513d-132">Значением по умолчанию являются текущие дата и время.</span><span class="sxs-lookup"><span data-stu-id="4513d-132">The default value is the current date and time.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: Date
Aliases:

Required: False
Position: 1
Default value: Current date and time
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="4513d-133">– Часы</span><span class="sxs-lookup"><span data-stu-id="4513d-133">-Hours</span></span>

<span data-ttu-id="4513d-134">Указывает часы в интервале времени.</span><span class="sxs-lookup"><span data-stu-id="4513d-134">Specifies the hours in the time span.</span></span>
<span data-ttu-id="4513d-135">Значение по умолчанию равно нулю.</span><span class="sxs-lookup"><span data-stu-id="4513d-135">The default value is zero.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Time
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4513d-136">-Минут</span><span class="sxs-lookup"><span data-stu-id="4513d-136">-Minutes</span></span>

<span data-ttu-id="4513d-137">Указывает минуты в интервале времени.</span><span class="sxs-lookup"><span data-stu-id="4513d-137">Specifies the minutes in the time span.</span></span>
<span data-ttu-id="4513d-138">Значение по умолчанию — 0.</span><span class="sxs-lookup"><span data-stu-id="4513d-138">The default value is 0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Time
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4513d-139">-Секунд</span><span class="sxs-lookup"><span data-stu-id="4513d-139">-Seconds</span></span>

<span data-ttu-id="4513d-140">Задает длину интервала времени в секундах.</span><span class="sxs-lookup"><span data-stu-id="4513d-140">Specifies the length of the time span in seconds.</span></span>
<span data-ttu-id="4513d-141">Значение по умолчанию — 0.</span><span class="sxs-lookup"><span data-stu-id="4513d-141">The default value is 0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Time
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4513d-142">— Запуск</span><span class="sxs-lookup"><span data-stu-id="4513d-142">-Start</span></span>

<span data-ttu-id="4513d-143">Задает начало периода времени.</span><span class="sxs-lookup"><span data-stu-id="4513d-143">Specifies the start of a time span.</span></span>
<span data-ttu-id="4513d-144">Введите строку, представляющую дату и время, например "3/15/09", или объект **DateTime** , например, один из `Get-Date` команд.</span><span class="sxs-lookup"><span data-stu-id="4513d-144">Enter a string that represents the date and time, such as "3/15/09" or a **DateTime** object, such as one from a `Get-Date` command.</span></span> <span data-ttu-id="4513d-145">Значением по умолчанию являются текущие дата и время.</span><span class="sxs-lookup"><span data-stu-id="4513d-145">The default value is the current date and time.</span></span>

<span data-ttu-id="4513d-146">Можно использовать **Start** или его псевдоним **LastWriteTime**.</span><span class="sxs-lookup"><span data-stu-id="4513d-146">You can use **Start** or its alias, **LastWriteTime**.</span></span>
<span data-ttu-id="4513d-147">Псевдоним **LastWriteTime** позволяет передавать объекты, имеющие свойство **LastWriteTime** , например файлы в файловой системе `[System.Io.FileIO]` , в параметр **Start** объекта `New-TimeSpan` .</span><span class="sxs-lookup"><span data-stu-id="4513d-147">The **LastWriteTime** alias lets you pipe objects that have a **LastWriteTime** property, such as files in the file system `[System.Io.FileIO]`, to the **Start** parameter of `New-TimeSpan`.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: Date
Aliases: LastWriteTime

Required: False
Position: 0
Default value: Current date and time
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4513d-148">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="4513d-148">CommonParameters</span></span>

<span data-ttu-id="4513d-149">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4513d-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4513d-150">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="4513d-150">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="4513d-151">Входные данные</span><span class="sxs-lookup"><span data-stu-id="4513d-151">INPUTS</span></span>

### <span data-ttu-id="4513d-152">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="4513d-152">System.DateTime</span></span>

<span data-ttu-id="4513d-153">Объект **DateTime** , представляющий время начала, можно передать в `New-TimeSpan` .</span><span class="sxs-lookup"><span data-stu-id="4513d-153">You can pipe a **DateTime** object that represents that start time to `New-TimeSpan`.</span></span>

## <span data-ttu-id="4513d-154">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="4513d-154">OUTPUTS</span></span>

### <span data-ttu-id="4513d-155">System.TimeSpan</span><span class="sxs-lookup"><span data-stu-id="4513d-155">System.TimeSpan</span></span>

<span data-ttu-id="4513d-156">`New-TimeSpan` Возвращает объект, представляющий интервал времени.</span><span class="sxs-lookup"><span data-stu-id="4513d-156">`New-TimeSpan` returns an object that represents the time span.</span></span>

## <span data-ttu-id="4513d-157">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="4513d-157">NOTES</span></span>

## <span data-ttu-id="4513d-158">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="4513d-158">RELATED LINKS</span></span>

[<span data-ttu-id="4513d-159">Get-Дата</span><span class="sxs-lookup"><span data-stu-id="4513d-159">Get-Date</span></span>](Get-Date.md)

[<span data-ttu-id="4513d-160">Set-Date</span><span class="sxs-lookup"><span data-stu-id="4513d-160">Set-Date</span></span>](Set-Date.md)

