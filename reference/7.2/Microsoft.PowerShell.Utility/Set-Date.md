---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/30/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-date?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Date
ms.openlocfilehash: 0f35eea0dfca76b535aad3bdb663d55c224a11d2
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602840"
---
# <span data-ttu-id="8d014-102">Set-Date</span><span class="sxs-lookup"><span data-stu-id="8d014-102">Set-Date</span></span>

## <span data-ttu-id="8d014-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="8d014-103">SYNOPSIS</span></span>
<span data-ttu-id="8d014-104">Меняет системное время компьютера на указанное.</span><span class="sxs-lookup"><span data-stu-id="8d014-104">Changes the system time on the computer to a time that you specify.</span></span>

## <span data-ttu-id="8d014-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8d014-105">SYNTAX</span></span>

### <span data-ttu-id="8d014-106">Дата (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8d014-106">Date (Default)</span></span>

```
Set-Date [-Date] <DateTime> [-DisplayHint <DisplayHintType>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="8d014-107">Adjust</span><span class="sxs-lookup"><span data-stu-id="8d014-107">Adjust</span></span>

```
Set-Date [-Adjust] <TimeSpan> [-DisplayHint <DisplayHintType>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="8d014-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8d014-108">DESCRIPTION</span></span>

<span data-ttu-id="8d014-109">`Set-Date`Командлет изменяет системную дату и время на компьютере на указанную дату и время.</span><span class="sxs-lookup"><span data-stu-id="8d014-109">The `Set-Date` cmdlet changes the system date and time on the computer to a date and time that you specify.</span></span>
<span data-ttu-id="8d014-110">Можно указать новую дату и (или) время, введя строку или передав объект **DateTime** или **TimeSpan** в `Set-Date` .</span><span class="sxs-lookup"><span data-stu-id="8d014-110">You can specify a new date and/or time by typing a string or by passing a **DateTime** or **TimeSpan** object to `Set-Date`.</span></span> <span data-ttu-id="8d014-111">Чтобы указать новую дату или время, используйте параметр **Date** .</span><span class="sxs-lookup"><span data-stu-id="8d014-111">To specify a new date or time, use the **Date** parameter.</span></span>
<span data-ttu-id="8d014-112">Чтобы задать интервал изменения, используйте параметр **корректировки** .</span><span class="sxs-lookup"><span data-stu-id="8d014-112">To specify a change interval, use the **Adjust** parameter.</span></span>

## <span data-ttu-id="8d014-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="8d014-113">EXAMPLES</span></span>

### <span data-ttu-id="8d014-114">Пример 1. Добавление трех дней к системной дате</span><span class="sxs-lookup"><span data-stu-id="8d014-114">Example 1: Add three days to the system date</span></span>

<span data-ttu-id="8d014-115">Эта команда добавляет к текущей системной дате три дня.</span><span class="sxs-lookup"><span data-stu-id="8d014-115">This command adds three days to the current system date.</span></span>
<span data-ttu-id="8d014-116">На время она не влияет.</span><span class="sxs-lookup"><span data-stu-id="8d014-116">It does not affect the time.</span></span>
<span data-ttu-id="8d014-117">Команда использует параметр **Date** для указания даты.</span><span class="sxs-lookup"><span data-stu-id="8d014-117">The command uses the **Date** parameter to specify the date.</span></span>

<span data-ttu-id="8d014-118">`Get-Date`Командлет возвращает текущую дату в виде объекта **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="8d014-118">The `Get-Date` cmdlet returns the current date as a **DateTime** object.</span></span> <span data-ttu-id="8d014-119">Метод **AddDays** объекта **DateTime** добавляет указанное число дней (3) к текущему объекту **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="8d014-119">The **DateTime** object's **AddDays** method adds a specified number of days (3) to the current **DateTime** object.</span></span>

```powershell
Set-Date -Date (Get-Date).AddDays(3)
```

### <span data-ttu-id="8d014-120">Пример 2. Настройка системных часов назад через 10 минут</span><span class="sxs-lookup"><span data-stu-id="8d014-120">Example 2: Set the system clock back 10 minutes</span></span>

<span data-ttu-id="8d014-121">В этом примере текущее системное время устанавливается на 10 минут.</span><span class="sxs-lookup"><span data-stu-id="8d014-121">This example sets the current system time back by 10 minutes.</span></span>

<span data-ttu-id="8d014-122">Параметр " **изменить** " позволяет указать интервал изменения (не более десяти минут) в стандартном формате времени для языкового стандарта.</span><span class="sxs-lookup"><span data-stu-id="8d014-122">The **Adjust** parameter allows you to specify an interval of change (minus ten minutes) in the standard time format for the locale.</span></span>

<span data-ttu-id="8d014-123">Параметр **дисплайхинт** указывает PowerShell отображать только время, но не влияет на объект **DateTime** , `Set-Date` возвращающий значение.</span><span class="sxs-lookup"><span data-stu-id="8d014-123">The **DisplayHint** parameter tells PowerShell to display only the time, but it does not affect the **DateTime** object that `Set-Date` returns.</span></span>

```powershell
Set-Date -Adjust -0:10:0 -DisplayHint Time
```

### <span data-ttu-id="8d014-124">Пример 3. Установка значения переменной даты и времени</span><span class="sxs-lookup"><span data-stu-id="8d014-124">Example 3: Set the date and time to a variable value</span></span>

<span data-ttu-id="8d014-125">Эти команды изменяют системную дату и время на локальном компьютере на дату и время, сохраненные в переменной `$T` .</span><span class="sxs-lookup"><span data-stu-id="8d014-125">These commands change the system date and time on local computer to the date and time saved in the variable `$T`.</span></span> <span data-ttu-id="8d014-126">Первая команда получает дату и сохраняет ее в `$T` .</span><span class="sxs-lookup"><span data-stu-id="8d014-126">The first command gets the date and stores it in `$T`.</span></span>

<span data-ttu-id="8d014-127">Вторая команда использует параметр **Date** для передачи объекта **DateTime** в `$T` `Set-Date` командлет.</span><span class="sxs-lookup"><span data-stu-id="8d014-127">The second command uses the **Date** parameter to pass the **DateTime** object in `$T` to the `Set-Date` cmdlet.</span></span>

```powershell
$T = Get-Date
Set-Date -Date $T
```

### <span data-ttu-id="8d014-128">Пример 4. Добавление в системные часы 90 минут</span><span class="sxs-lookup"><span data-stu-id="8d014-128">Example 4: Add 90 minutes to the system clock</span></span>

<span data-ttu-id="8d014-129">Эти команды переводят системное время на локальном компьютере на 90 минут вперед.</span><span class="sxs-lookup"><span data-stu-id="8d014-129">These commands advance the system time on the local computer by 90 minutes.</span></span>

<span data-ttu-id="8d014-130">Первая команда использует `New-TimeSpan` командлет для создания объекта **TimeSpan** с интервалом в 90 минут и сохраняет его в `$90mins` переменной.</span><span class="sxs-lookup"><span data-stu-id="8d014-130">The first command uses the `New-TimeSpan` cmdlet to create a **TimeSpan** object with a 90-minute interval, and saves it in the `$90mins` variable.</span></span>

<span data-ttu-id="8d014-131">Вторая команда использует параметр **корректировки** `Set-Date` для для настройки даты по значению объекта **TimeSpan** в `$90mins` переменной.</span><span class="sxs-lookup"><span data-stu-id="8d014-131">The second command uses the **Adjust** parameter of `Set-Date` to adjust the date by the value of the **TimeSpan** object in the `$90mins` variable.</span></span>

```powershell
$90mins = New-TimeSpan -Minutes 90
Set-Date -Adjust $90mins
```

## <span data-ttu-id="8d014-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8d014-132">PARAMETERS</span></span>

### <span data-ttu-id="8d014-133">— Настройка</span><span class="sxs-lookup"><span data-stu-id="8d014-133">-Adjust</span></span>

<span data-ttu-id="8d014-134">Задает значение, которое этот командлет добавляет или вычитает из текущей даты и времени.</span><span class="sxs-lookup"><span data-stu-id="8d014-134">Specifies the value for which this cmdlet adds or subtracts from the current date and time.</span></span>
<span data-ttu-id="8d014-135">можно ввести корректировку в стандартном формате даты и времени для языкового стандарта или использовать параметр " **изменить** " для передачи объекта **TimeSpan** из `New-TimeSpan` в `Set-Date` .</span><span class="sxs-lookup"><span data-stu-id="8d014-135">can type an adjustment in standard date and time format for your locale or use the **Adjust** parameter to pass a **TimeSpan** object from `New-TimeSpan` to `Set-Date`.</span></span>

```yaml
Type: System.TimeSpan
Parameter Sets: Adjust
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8d014-136">-Date</span><span class="sxs-lookup"><span data-stu-id="8d014-136">-Date</span></span>

<span data-ttu-id="8d014-137">Устанавливает указанные значения даты и времени.</span><span class="sxs-lookup"><span data-stu-id="8d014-137">Changes the date and time to the specified values.</span></span>
<span data-ttu-id="8d014-138">Можно ввести новую дату в кратком формате даты, а время — в стандартном формате времени для используемого языкового стандарта.</span><span class="sxs-lookup"><span data-stu-id="8d014-138">You can type a new date in the short date format and a time in the standard time format for your locale.</span></span> <span data-ttu-id="8d014-139">Или можно передать объект **DateTime** из `Get-Date` .</span><span class="sxs-lookup"><span data-stu-id="8d014-139">Or, you can pass a **DateTime** object from `Get-Date`.</span></span>

<span data-ttu-id="8d014-140">Если указать дату, но не время, `Set-Date` то изменяет время на полночь на указанную дату.</span><span class="sxs-lookup"><span data-stu-id="8d014-140">If you specify a date, but not a time, `Set-Date` changes the time to midnight on the specified date.</span></span> <span data-ttu-id="8d014-141">Если указано только время, дата не изменяется.</span><span class="sxs-lookup"><span data-stu-id="8d014-141">If you specify only a time, it does not change the date.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: Date
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8d014-142">-DisplayHint</span><span class="sxs-lookup"><span data-stu-id="8d014-142">-DisplayHint</span></span>

<span data-ttu-id="8d014-143">Указывает, какие элементы даты и времени отображаются. Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="8d014-143">Specifies which elements of the date and time are displayed.The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="8d014-144">**Дата** — отображает только дату.</span><span class="sxs-lookup"><span data-stu-id="8d014-144">**Date** - displays only the date.</span></span>
- <span data-ttu-id="8d014-145">**Время** — отображает только время.</span><span class="sxs-lookup"><span data-stu-id="8d014-145">**Time** - displays only the time.</span></span>
- <span data-ttu-id="8d014-146">**DateTime** — отображает дату и время.</span><span class="sxs-lookup"><span data-stu-id="8d014-146">**DateTime** - displays the date and time.</span></span>

<span data-ttu-id="8d014-147">Этот параметр влияет только на отображаемые значения</span><span class="sxs-lookup"><span data-stu-id="8d014-147">This parameter affects only the display.</span></span>
<span data-ttu-id="8d014-148">Он не влияет на объект **DateTime** , который `Get-Date` получает.</span><span class="sxs-lookup"><span data-stu-id="8d014-148">It does not affect the **DateTime** object that `Get-Date` retrieves.</span></span>

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

### <span data-ttu-id="8d014-149">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8d014-149">-Confirm</span></span>

<span data-ttu-id="8d014-150">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="8d014-150">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8d014-151">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8d014-151">-WhatIf</span></span>

<span data-ttu-id="8d014-152">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="8d014-152">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="8d014-153">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="8d014-153">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8d014-154">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="8d014-154">CommonParameters</span></span>

<span data-ttu-id="8d014-155">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8d014-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8d014-156">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="8d014-156">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="8d014-157">Входные данные</span><span class="sxs-lookup"><span data-stu-id="8d014-157">INPUTS</span></span>

### <span data-ttu-id="8d014-158">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="8d014-158">System.DateTime</span></span>

<span data-ttu-id="8d014-159">Дату можно передать в `Set-Date` .</span><span class="sxs-lookup"><span data-stu-id="8d014-159">You can pipe a date to `Set-Date`.</span></span>

## <span data-ttu-id="8d014-160">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="8d014-160">OUTPUTS</span></span>

### <span data-ttu-id="8d014-161">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="8d014-161">System.DateTime</span></span>

<span data-ttu-id="8d014-162">`Set-Date` Возвращает объект, представляющий заданную дату.</span><span class="sxs-lookup"><span data-stu-id="8d014-162">`Set-Date` returns an object that represents the date that it set.</span></span>

## <span data-ttu-id="8d014-163">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="8d014-163">NOTES</span></span>

- <span data-ttu-id="8d014-164">Используйте этот командлет с осторожностью при изменении даты и времени на компьютере.</span><span class="sxs-lookup"><span data-stu-id="8d014-164">Use this cmdlet cautiously when changing the date and time on the computer.</span></span> <span data-ttu-id="8d014-165">Из-за изменения даты или времени компьютер может не получать системные события и обновления, которые запускаются в определенный день или момент времени.</span><span class="sxs-lookup"><span data-stu-id="8d014-165">The change might prevent the computer from receiving system-wide events and updates that are triggered by a date or time.</span></span> <span data-ttu-id="8d014-166">Используйте параметры **WhatIf** и **Confirm** , чтобы избежать ошибок.</span><span class="sxs-lookup"><span data-stu-id="8d014-166">Use the **WhatIf** and **Confirm** parameters to avoid errors.</span></span>
- <span data-ttu-id="8d014-167">Вы можете использовать стандартные методы .NET с объектами **DateTime** и **TimeSpan** , которые используются с `Set-Date` , например **AddDays**, **аддмонсс** и **фромфилетиме**.</span><span class="sxs-lookup"><span data-stu-id="8d014-167">You can use standard .NET methods with the **DateTime** and **TimeSpan** objects used with `Set-Date`, such as **AddDays**, **AddMonths**, and **FromFileTime**.</span></span> <span data-ttu-id="8d014-168">Дополнительные сведения см. в разделе [методы DateTime](/dotnet/api/system.datetime) и</span><span class="sxs-lookup"><span data-stu-id="8d014-168">For more information, see [DateTime Methods](/dotnet/api/system.datetime) and</span></span>

  <span data-ttu-id="8d014-169">[Методы TimeSpan](/dotnet/api/system.timespan) в пакете SDK для .NET.</span><span class="sxs-lookup"><span data-stu-id="8d014-169">[TimeSpan Methods](/dotnet/api/system.timespan) in the .NET SDK.</span></span>

## <span data-ttu-id="8d014-170">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="8d014-170">RELATED LINKS</span></span>

[<span data-ttu-id="8d014-171">Get-Дата</span><span class="sxs-lookup"><span data-stu-id="8d014-171">Get-Date</span></span>](Get-Date.md)

[<span data-ttu-id="8d014-172">New-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="8d014-172">New-TimeSpan</span></span>](New-TimeSpan.md)
