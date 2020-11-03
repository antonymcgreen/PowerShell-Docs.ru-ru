---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 5/1/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-timespan?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-TimeSpan
ms.openlocfilehash: 7e96437c67180eaac0e3163eaf799b34de2b903f
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225838"
---
# <span data-ttu-id="12ed9-103">New-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="12ed9-103">New-TimeSpan</span></span>

## <span data-ttu-id="12ed9-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="12ed9-104">SYNOPSIS</span></span>
<span data-ttu-id="12ed9-105">Создает объект TimeSpan.</span><span class="sxs-lookup"><span data-stu-id="12ed9-105">Creates a TimeSpan object.</span></span>

## <span data-ttu-id="12ed9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="12ed9-106">SYNTAX</span></span>

### <span data-ttu-id="12ed9-107">Дата (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="12ed9-107">Date (Default)</span></span>

```
New-TimeSpan [[-Start] <DateTime>] [[-End] <DateTime>] [<CommonParameters>]
```

### <span data-ttu-id="12ed9-108">Время</span><span class="sxs-lookup"><span data-stu-id="12ed9-108">Time</span></span>

```
New-TimeSpan [-Days <Int32>] [-Hours <Int32>] [-Minutes <Int32>] [-Seconds <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="12ed9-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="12ed9-109">DESCRIPTION</span></span>

<span data-ttu-id="12ed9-110">`New-TimeSpan`Командлет создает объект **TimeSpan** , представляющий интервал времени.</span><span class="sxs-lookup"><span data-stu-id="12ed9-110">The `New-TimeSpan` cmdlet creates a **TimeSpan** object that represents a time interval.</span></span>
<span data-ttu-id="12ed9-111">Объект **TimeSpan** можно использовать для добавления или вычитания времени из объектов **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="12ed9-111">You can use a **TimeSpan** object to add or subtract time from **DateTime** objects.</span></span>

<span data-ttu-id="12ed9-112">Без параметров `New-TimeSpan` команда возвращает объект **TimeSpan** , представляющий интервал времени, равный нулю.</span><span class="sxs-lookup"><span data-stu-id="12ed9-112">Without parameters, a `New-TimeSpan` command returns a **TimeSpan** object that represents a time interval of zero.</span></span>

## <span data-ttu-id="12ed9-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="12ed9-113">EXAMPLES</span></span>

### <span data-ttu-id="12ed9-114">Пример 1. Создание объекта TimeSpan на указанный период</span><span class="sxs-lookup"><span data-stu-id="12ed9-114">Example 1: Create a TimeSpan object for a specified duration</span></span>

<span data-ttu-id="12ed9-115">Эта команда создает объект **TimeSpan** с длительностью в 1 час и 25 минут и сохраняет его в переменной с именем `$TimeSpan` .</span><span class="sxs-lookup"><span data-stu-id="12ed9-115">This command creates a **TimeSpan** object with a duration of 1 hour and 25 minutes and stores it in a variable named `$TimeSpan`.</span></span> <span data-ttu-id="12ed9-116">Он отображает представление объекта **TimeSpan** .</span><span class="sxs-lookup"><span data-stu-id="12ed9-116">It displays a representation of the **TimeSpan** object.</span></span>

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

### <span data-ttu-id="12ed9-117">Пример 2. Создание объекта TimeSpan для интервала времени</span><span class="sxs-lookup"><span data-stu-id="12ed9-117">Example 2: Create a TimeSpan object for a time interval</span></span>

<span data-ttu-id="12ed9-118">В этом примере создается новый объект **TimeSpan** , представляющий интервал между временем выполнения команды и 1 января 2010.</span><span class="sxs-lookup"><span data-stu-id="12ed9-118">This example creates a new **TimeSpan** object that represents the interval between the time that the command is run and January 1, 2010.</span></span>

<span data-ttu-id="12ed9-119">Эта команда не требует параметра **Start** , так как значением по умолчанию для параметра **Start** является текущая дата и время.</span><span class="sxs-lookup"><span data-stu-id="12ed9-119">This command does not require the **Start** parameter, because the default value of the **Start** parameter is the current date and time.</span></span>

```powershell
New-TimeSpan -End (Get-Date -Year 2010 -Month 1 -Day 1)
```

### <span data-ttu-id="12ed9-120">Пример 3. Получение даты 90 дней с текущей даты</span><span class="sxs-lookup"><span data-stu-id="12ed9-120">Example 3: Get the date 90 days from the current date</span></span>

```powershell
$90days = New-TimeSpan -Days 90
(Get-Date) + $90days
```

<span data-ttu-id="12ed9-121">Эти команды возвращают дату на 90 дней позднее текущей.</span><span class="sxs-lookup"><span data-stu-id="12ed9-121">These commands return the date that is 90 days after the current date.</span></span>

### <span data-ttu-id="12ed9-122">Пример 4. Обнаружение TimeSpan с момента обновления файла</span><span class="sxs-lookup"><span data-stu-id="12ed9-122">Example 4: Discover the TimeSpan since a file was updated</span></span>

<span data-ttu-id="12ed9-123">Эта команда указывает, сколько времени прошло с момента последнего обновления файла справки [about_remote](../Microsoft.PowerShell.Core/About/about_Remote.md) .</span><span class="sxs-lookup"><span data-stu-id="12ed9-123">This command tells you how long it has been since the [about_remote](../Microsoft.PowerShell.Core/About/about_Remote.md) help file was last updated.</span></span>
<span data-ttu-id="12ed9-124">Этот формат команды можно использовать для любого файла или любого другого объекта, имеющего свойство **LastWriteTime** .</span><span class="sxs-lookup"><span data-stu-id="12ed9-124">You can use this command format on any file, or any other object that has a **LastWriteTime** property.</span></span>

<span data-ttu-id="12ed9-125">Эта команда работает, так как параметр **Start** параметра `New-TimeSpan` имеет псевдоним **LastWriteTime**.</span><span class="sxs-lookup"><span data-stu-id="12ed9-125">This command works because the **Start** parameter of `New-TimeSpan` has an alias of **LastWriteTime**.</span></span> <span data-ttu-id="12ed9-126">При передаче объекта, имеющего свойство **LastWriteTime** `New-TimeSpan` , в PowerShell использует значение свойства **LastWriteTime** в качестве значения параметра **Start** .</span><span class="sxs-lookup"><span data-stu-id="12ed9-126">When you pipe an object that has a **LastWriteTime** property to `New-TimeSpan`, PowerShell uses the value of the **LastWriteTime** property as the value of the **Start** parameter.</span></span>

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

## <span data-ttu-id="12ed9-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="12ed9-127">PARAMETERS</span></span>

### <span data-ttu-id="12ed9-128">-Days</span><span class="sxs-lookup"><span data-stu-id="12ed9-128">-Days</span></span>

<span data-ttu-id="12ed9-129">Указывает дни в интервале времени.</span><span class="sxs-lookup"><span data-stu-id="12ed9-129">Specifies the days in the time span.</span></span>
<span data-ttu-id="12ed9-130">Значение по умолчанию — 0.</span><span class="sxs-lookup"><span data-stu-id="12ed9-130">The default value is 0.</span></span>

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

### <span data-ttu-id="12ed9-131">-End</span><span class="sxs-lookup"><span data-stu-id="12ed9-131">-End</span></span>

<span data-ttu-id="12ed9-132">Задает конец интервала времени.</span><span class="sxs-lookup"><span data-stu-id="12ed9-132">Specifies the end of a time span.</span></span>
<span data-ttu-id="12ed9-133">Значением по умолчанию являются текущие дата и время.</span><span class="sxs-lookup"><span data-stu-id="12ed9-133">The default value is the current date and time.</span></span>

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

### <span data-ttu-id="12ed9-134">– Часы</span><span class="sxs-lookup"><span data-stu-id="12ed9-134">-Hours</span></span>

<span data-ttu-id="12ed9-135">Указывает часы в интервале времени.</span><span class="sxs-lookup"><span data-stu-id="12ed9-135">Specifies the hours in the time span.</span></span>
<span data-ttu-id="12ed9-136">Значение по умолчанию равно нулю.</span><span class="sxs-lookup"><span data-stu-id="12ed9-136">The default value is zero.</span></span>

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

### <span data-ttu-id="12ed9-137">-Минут</span><span class="sxs-lookup"><span data-stu-id="12ed9-137">-Minutes</span></span>

<span data-ttu-id="12ed9-138">Указывает минуты в интервале времени.</span><span class="sxs-lookup"><span data-stu-id="12ed9-138">Specifies the minutes in the time span.</span></span>
<span data-ttu-id="12ed9-139">Значение по умолчанию — 0.</span><span class="sxs-lookup"><span data-stu-id="12ed9-139">The default value is 0.</span></span>

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

### <span data-ttu-id="12ed9-140">-Секунд</span><span class="sxs-lookup"><span data-stu-id="12ed9-140">-Seconds</span></span>

<span data-ttu-id="12ed9-141">Задает длину интервала времени в секундах.</span><span class="sxs-lookup"><span data-stu-id="12ed9-141">Specifies the length of the time span in seconds.</span></span>
<span data-ttu-id="12ed9-142">Значение по умолчанию — 0.</span><span class="sxs-lookup"><span data-stu-id="12ed9-142">The default value is 0.</span></span>

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

### <span data-ttu-id="12ed9-143">— Запуск</span><span class="sxs-lookup"><span data-stu-id="12ed9-143">-Start</span></span>

<span data-ttu-id="12ed9-144">Задает начало периода времени.</span><span class="sxs-lookup"><span data-stu-id="12ed9-144">Specifies the start of a time span.</span></span>
<span data-ttu-id="12ed9-145">Введите строку, представляющую дату и время, например "3/15/09", или объект **DateTime** , например, один из `Get-Date` команд.</span><span class="sxs-lookup"><span data-stu-id="12ed9-145">Enter a string that represents the date and time, such as "3/15/09" or a **DateTime** object, such as one from a `Get-Date` command.</span></span> <span data-ttu-id="12ed9-146">Значением по умолчанию являются текущие дата и время.</span><span class="sxs-lookup"><span data-stu-id="12ed9-146">The default value is the current date and time.</span></span>

<span data-ttu-id="12ed9-147">Можно использовать **Start** или его псевдоним **LastWriteTime**.</span><span class="sxs-lookup"><span data-stu-id="12ed9-147">You can use **Start** or its alias, **LastWriteTime**.</span></span>
<span data-ttu-id="12ed9-148">Псевдоним **LastWriteTime** позволяет передавать объекты, имеющие свойство **LastWriteTime** , например файлы в файловой системе `[System.Io.FileIO]` , в параметр **Start** объекта `New-TimeSpan` .</span><span class="sxs-lookup"><span data-stu-id="12ed9-148">The **LastWriteTime** alias lets you pipe objects that have a **LastWriteTime** property, such as files in the file system `[System.Io.FileIO]`, to the **Start** parameter of `New-TimeSpan`.</span></span>

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

### <span data-ttu-id="12ed9-149">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="12ed9-149">CommonParameters</span></span>

<span data-ttu-id="12ed9-150">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="12ed9-150">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="12ed9-151">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="12ed9-151">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="12ed9-152">Входные данные</span><span class="sxs-lookup"><span data-stu-id="12ed9-152">INPUTS</span></span>

### <span data-ttu-id="12ed9-153">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="12ed9-153">System.DateTime</span></span>

<span data-ttu-id="12ed9-154">Объект **DateTime** , представляющий время начала, можно передать в `New-TimeSpan` .</span><span class="sxs-lookup"><span data-stu-id="12ed9-154">You can pipe a **DateTime** object that represents that start time to `New-TimeSpan`.</span></span>

## <span data-ttu-id="12ed9-155">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="12ed9-155">OUTPUTS</span></span>

### <span data-ttu-id="12ed9-156">System.TimeSpan</span><span class="sxs-lookup"><span data-stu-id="12ed9-156">System.TimeSpan</span></span>

<span data-ttu-id="12ed9-157">`New-TimeSpan` Возвращает объект, представляющий интервал времени.</span><span class="sxs-lookup"><span data-stu-id="12ed9-157">`New-TimeSpan` returns an object that represents the time span.</span></span>

## <span data-ttu-id="12ed9-158">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="12ed9-158">NOTES</span></span>

## <span data-ttu-id="12ed9-159">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="12ed9-159">RELATED LINKS</span></span>

[<span data-ttu-id="12ed9-160">Get-Дата</span><span class="sxs-lookup"><span data-stu-id="12ed9-160">Get-Date</span></span>](Get-Date.md)

[<span data-ttu-id="12ed9-161">Set-Date</span><span class="sxs-lookup"><span data-stu-id="12ed9-161">Set-Date</span></span>](Set-Date.md)
