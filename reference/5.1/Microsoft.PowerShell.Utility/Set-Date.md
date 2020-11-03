---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 4/30/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-date?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Date
ms.openlocfilehash: c3cc162fdb8b3d04236f2186438fa14b8a0b42b3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227514"
---
# <span data-ttu-id="7f6b1-103">Set-Date</span><span class="sxs-lookup"><span data-stu-id="7f6b1-103">Set-Date</span></span>

## <span data-ttu-id="7f6b1-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="7f6b1-104">SYNOPSIS</span></span>
<span data-ttu-id="7f6b1-105">Меняет системное время компьютера на указанное.</span><span class="sxs-lookup"><span data-stu-id="7f6b1-105">Changes the system time on the computer to a time that you specify.</span></span>

## <span data-ttu-id="7f6b1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7f6b1-106">SYNTAX</span></span>

### <span data-ttu-id="7f6b1-107">Дата (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="7f6b1-107">Date (Default)</span></span>

```
Set-Date [-Date] <DateTime> [-DisplayHint <DisplayHintType>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7f6b1-108">Adjust</span><span class="sxs-lookup"><span data-stu-id="7f6b1-108">Adjust</span></span>

```
Set-Date [-Adjust] <TimeSpan> [-DisplayHint <DisplayHintType>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="7f6b1-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7f6b1-109">DESCRIPTION</span></span>

<span data-ttu-id="7f6b1-110">`Set-Date`Командлет изменяет системную дату и время на компьютере на указанную дату и время.</span><span class="sxs-lookup"><span data-stu-id="7f6b1-110">The `Set-Date` cmdlet changes the system date and time on the computer to a date and time that you specify.</span></span>
<span data-ttu-id="7f6b1-111">Можно указать новую дату и (или) время, введя строку или передав объект **DateTime** или **TimeSpan** в `Set-Date` .</span><span class="sxs-lookup"><span data-stu-id="7f6b1-111">You can specify a new date and/or time by typing a string or by passing a **DateTime** or **TimeSpan** object to `Set-Date`.</span></span> <span data-ttu-id="7f6b1-112">Чтобы указать новую дату или время, используйте параметр **Date** .</span><span class="sxs-lookup"><span data-stu-id="7f6b1-112">To specify a new date or time, use the **Date** parameter.</span></span>
<span data-ttu-id="7f6b1-113">Чтобы задать интервал изменения, используйте параметр **корректировки** .</span><span class="sxs-lookup"><span data-stu-id="7f6b1-113">To specify a change interval, use the **Adjust** parameter.</span></span>

## <span data-ttu-id="7f6b1-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="7f6b1-114">EXAMPLES</span></span>

### <span data-ttu-id="7f6b1-115">Пример 1. Добавление трех дней к системной дате</span><span class="sxs-lookup"><span data-stu-id="7f6b1-115">Example 1: Add three days to the system date</span></span>

<span data-ttu-id="7f6b1-116">Эта команда добавляет к текущей системной дате три дня.</span><span class="sxs-lookup"><span data-stu-id="7f6b1-116">This command adds three days to the current system date.</span></span>
<span data-ttu-id="7f6b1-117">На время она не влияет.</span><span class="sxs-lookup"><span data-stu-id="7f6b1-117">It does not affect the time.</span></span>
<span data-ttu-id="7f6b1-118">Команда использует параметр **Date** для указания даты.</span><span class="sxs-lookup"><span data-stu-id="7f6b1-118">The command uses the **Date** parameter to specify the date.</span></span>

<span data-ttu-id="7f6b1-119">`Get-Date`Командлет возвращает текущую дату в виде объекта **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="7f6b1-119">The `Get-Date` cmdlet returns the current date as a **DateTime** object.</span></span> <span data-ttu-id="7f6b1-120">Метод **AddDays** объекта **DateTime** добавляет указанное число дней (3) к текущему объекту **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="7f6b1-120">The **DateTime** object's **AddDays** method adds a specified number of days (3) to the current **DateTime** object.</span></span>

```powershell
Set-Date -Date (Get-Date).AddDays(3)
```

### <span data-ttu-id="7f6b1-121">Пример 2. Настройка системных часов назад через 10 минут</span><span class="sxs-lookup"><span data-stu-id="7f6b1-121">Example 2: Set the system clock back 10 minutes</span></span>

<span data-ttu-id="7f6b1-122">В этом примере текущее системное время устанавливается на 10 минут.</span><span class="sxs-lookup"><span data-stu-id="7f6b1-122">This example sets the current system time back by 10 minutes.</span></span>

<span data-ttu-id="7f6b1-123">Параметр " **изменить** " позволяет указать интервал изменения (не более десяти минут) в стандартном формате времени для языкового стандарта.</span><span class="sxs-lookup"><span data-stu-id="7f6b1-123">The **Adjust** parameter allows you to specify an interval of change (minus ten minutes) in the standard time format for the locale.</span></span>

<span data-ttu-id="7f6b1-124">Параметр **дисплайхинт** указывает PowerShell отображать только время, но не влияет на объект **DateTime** , `Set-Date` возвращающий значение.</span><span class="sxs-lookup"><span data-stu-id="7f6b1-124">The **DisplayHint** parameter tells PowerShell to display only the time, but it does not affect the **DateTime** object that `Set-Date` returns.</span></span>

```powershell
Set-Date -Adjust -0:10:0 -DisplayHint Time
```

### <span data-ttu-id="7f6b1-125">Пример 3. Установка значения переменной даты и времени</span><span class="sxs-lookup"><span data-stu-id="7f6b1-125">Example 3: Set the date and time to a variable value</span></span>

<span data-ttu-id="7f6b1-126">Эти команды изменяют системную дату и время на локальном компьютере на дату и время, сохраненные в переменной `$T` .</span><span class="sxs-lookup"><span data-stu-id="7f6b1-126">These commands change the system date and time on local computer to the date and time saved in the variable `$T`.</span></span> <span data-ttu-id="7f6b1-127">Первая команда получает дату и сохраняет ее в `$T` .</span><span class="sxs-lookup"><span data-stu-id="7f6b1-127">The first command gets the date and stores it in `$T`.</span></span>

<span data-ttu-id="7f6b1-128">Вторая команда использует параметр **Date** для передачи объекта **DateTime** в `$T` `Set-Date` командлет.</span><span class="sxs-lookup"><span data-stu-id="7f6b1-128">The second command uses the **Date** parameter to pass the **DateTime** object in `$T` to the `Set-Date` cmdlet.</span></span>

```powershell
$T = Get-Date
Set-Date -Date $T
```

### <span data-ttu-id="7f6b1-129">Пример 4. Добавление в системные часы 90 минут</span><span class="sxs-lookup"><span data-stu-id="7f6b1-129">Example 4: Add 90 minutes to the system clock</span></span>

<span data-ttu-id="7f6b1-130">Эти команды переводят системное время на локальном компьютере на 90 минут вперед.</span><span class="sxs-lookup"><span data-stu-id="7f6b1-130">These commands advance the system time on the local computer by 90 minutes.</span></span>

<span data-ttu-id="7f6b1-131">Первая команда использует `New-TimeSpan` командлет для создания объекта **TimeSpan** с интервалом в 90 минут и сохраняет его в `$90mins` переменной.</span><span class="sxs-lookup"><span data-stu-id="7f6b1-131">The first command uses the `New-TimeSpan` cmdlet to create a **TimeSpan** object with a 90-minute interval, and saves it in the `$90mins` variable.</span></span>

<span data-ttu-id="7f6b1-132">Вторая команда использует параметр **корректировки** `Set-Date` для для настройки даты по значению объекта **TimeSpan** в `$90mins` переменной.</span><span class="sxs-lookup"><span data-stu-id="7f6b1-132">The second command uses the **Adjust** parameter of `Set-Date` to adjust the date by the value of the **TimeSpan** object in the `$90mins` variable.</span></span>

```powershell
$90mins = New-TimeSpan -Minutes 90
Set-Date -Adjust $90mins
```

## <span data-ttu-id="7f6b1-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7f6b1-133">PARAMETERS</span></span>

### <span data-ttu-id="7f6b1-134">— Настройка</span><span class="sxs-lookup"><span data-stu-id="7f6b1-134">-Adjust</span></span>

<span data-ttu-id="7f6b1-135">Задает значение, которое этот командлет добавляет или вычитает из текущей даты и времени.</span><span class="sxs-lookup"><span data-stu-id="7f6b1-135">Specifies the value for which this cmdlet adds or subtracts from the current date and time.</span></span>
<span data-ttu-id="7f6b1-136">можно ввести корректировку в стандартном формате даты и времени для языкового стандарта или использовать параметр " **изменить** " для передачи объекта **TimeSpan** из `New-TimeSpan` в `Set-Date` .</span><span class="sxs-lookup"><span data-stu-id="7f6b1-136">can type an adjustment in standard date and time format for your locale or use the **Adjust** parameter to pass a **TimeSpan** object from `New-TimeSpan` to `Set-Date`.</span></span>

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

### <span data-ttu-id="7f6b1-137">-Date</span><span class="sxs-lookup"><span data-stu-id="7f6b1-137">-Date</span></span>

<span data-ttu-id="7f6b1-138">Устанавливает указанные значения даты и времени.</span><span class="sxs-lookup"><span data-stu-id="7f6b1-138">Changes the date and time to the specified values.</span></span>
<span data-ttu-id="7f6b1-139">Можно ввести новую дату в кратком формате даты, а время — в стандартном формате времени для используемого языкового стандарта.</span><span class="sxs-lookup"><span data-stu-id="7f6b1-139">You can type a new date in the short date format and a time in the standard time format for your locale.</span></span> <span data-ttu-id="7f6b1-140">Или можно передать объект **DateTime** из `Get-Date` .</span><span class="sxs-lookup"><span data-stu-id="7f6b1-140">Or, you can pass a **DateTime** object from `Get-Date`.</span></span>

<span data-ttu-id="7f6b1-141">Если указать дату, но не время, `Set-Date` то изменяет время на полночь на указанную дату.</span><span class="sxs-lookup"><span data-stu-id="7f6b1-141">If you specify a date, but not a time, `Set-Date` changes the time to midnight on the specified date.</span></span> <span data-ttu-id="7f6b1-142">Если указано только время, дата не изменяется.</span><span class="sxs-lookup"><span data-stu-id="7f6b1-142">If you specify only a time, it does not change the date.</span></span>

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

### <span data-ttu-id="7f6b1-143">-DisplayHint</span><span class="sxs-lookup"><span data-stu-id="7f6b1-143">-DisplayHint</span></span>

<span data-ttu-id="7f6b1-144">Указывает, какие элементы даты и времени отображаются. Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="7f6b1-144">Specifies which elements of the date and time are displayed.The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="7f6b1-145">**Дата** .</span><span class="sxs-lookup"><span data-stu-id="7f6b1-145">**Date** .</span></span>
  <span data-ttu-id="7f6b1-146">Отображает только дату.</span><span class="sxs-lookup"><span data-stu-id="7f6b1-146">displays only the date.</span></span>
- <span data-ttu-id="7f6b1-147">**Время** .</span><span class="sxs-lookup"><span data-stu-id="7f6b1-147">**Time** .</span></span>
  <span data-ttu-id="7f6b1-148">Отображает только время.</span><span class="sxs-lookup"><span data-stu-id="7f6b1-148">displays only the time.</span></span>
- <span data-ttu-id="7f6b1-149">**Дата и время** .</span><span class="sxs-lookup"><span data-stu-id="7f6b1-149">**DateTime** .</span></span>
  <span data-ttu-id="7f6b1-150">Отображает дату и время.</span><span class="sxs-lookup"><span data-stu-id="7f6b1-150">displays the date and time.</span></span>

<span data-ttu-id="7f6b1-151">Этот параметр влияет только на отображаемые значения</span><span class="sxs-lookup"><span data-stu-id="7f6b1-151">This parameter affects only the display.</span></span>
<span data-ttu-id="7f6b1-152">Он не влияет на объект **DateTime** , который `Get-Date` получает.</span><span class="sxs-lookup"><span data-stu-id="7f6b1-152">It does not affect the **DateTime** object that `Get-Date` retrieves.</span></span>

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

### <span data-ttu-id="7f6b1-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7f6b1-153">-Confirm</span></span>

<span data-ttu-id="7f6b1-154">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="7f6b1-154">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7f6b1-155">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7f6b1-155">-WhatIf</span></span>

<span data-ttu-id="7f6b1-156">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="7f6b1-156">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="7f6b1-157">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="7f6b1-157">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="7f6b1-158">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="7f6b1-158">CommonParameters</span></span>

<span data-ttu-id="7f6b1-159">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7f6b1-159">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7f6b1-160">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="7f6b1-160">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="7f6b1-161">Входные данные</span><span class="sxs-lookup"><span data-stu-id="7f6b1-161">INPUTS</span></span>

### <span data-ttu-id="7f6b1-162">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="7f6b1-162">System.DateTime</span></span>

<span data-ttu-id="7f6b1-163">Дату можно передать в `Set-Date` .</span><span class="sxs-lookup"><span data-stu-id="7f6b1-163">You can pipe a date to `Set-Date`.</span></span>

## <span data-ttu-id="7f6b1-164">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="7f6b1-164">OUTPUTS</span></span>

### <span data-ttu-id="7f6b1-165">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="7f6b1-165">System.DateTime</span></span>

<span data-ttu-id="7f6b1-166">`Set-Date` Возвращает объект, представляющий заданную дату.</span><span class="sxs-lookup"><span data-stu-id="7f6b1-166">`Set-Date` returns an object that represents the date that it set.</span></span>

## <span data-ttu-id="7f6b1-167">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="7f6b1-167">NOTES</span></span>

- <span data-ttu-id="7f6b1-168">Используйте этот командлет с осторожностью при изменении даты и времени на компьютере.</span><span class="sxs-lookup"><span data-stu-id="7f6b1-168">Use this cmdlet cautiously when changing the date and time on the computer.</span></span> <span data-ttu-id="7f6b1-169">Из-за изменения даты или времени компьютер может не получать системные события и обновления, которые запускаются в определенный день или момент времени.</span><span class="sxs-lookup"><span data-stu-id="7f6b1-169">The change might prevent the computer from receiving system-wide events and updates that are triggered by a date or time.</span></span> <span data-ttu-id="7f6b1-170">Используйте параметры **WhatIf** и **Confirm** , чтобы избежать ошибок.</span><span class="sxs-lookup"><span data-stu-id="7f6b1-170">Use the **WhatIf** and **Confirm** parameters to avoid errors.</span></span>
- <span data-ttu-id="7f6b1-171">Вы можете использовать стандартные методы .NET с объектами **DateTime** и **TimeSpan** , которые используются с `Set-Date` , например **AddDays** , **аддмонсс** и **фромфилетиме** .</span><span class="sxs-lookup"><span data-stu-id="7f6b1-171">You can use standard .NET methods with the **DateTime** and **TimeSpan** objects used with `Set-Date`, such as **AddDays** , **AddMonths** , and **FromFileTime** .</span></span> <span data-ttu-id="7f6b1-172">Дополнительные сведения см. в разделе [методы DateTime](/dotnet/api/system.datetime) и</span><span class="sxs-lookup"><span data-stu-id="7f6b1-172">For more information, see [DateTime Methods](/dotnet/api/system.datetime) and</span></span>

  <span data-ttu-id="7f6b1-173">[Методы TimeSpan](/dotnet/api/system.timespan) в библиотеке MSDN.</span><span class="sxs-lookup"><span data-stu-id="7f6b1-173">[TimeSpan Methods](/dotnet/api/system.timespan) in the MSDN library.</span></span>

## <span data-ttu-id="7f6b1-174">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="7f6b1-174">RELATED LINKS</span></span>

[<span data-ttu-id="7f6b1-175">Get-Дата</span><span class="sxs-lookup"><span data-stu-id="7f6b1-175">Get-Date</span></span>](Get-Date.md)

[<span data-ttu-id="7f6b1-176">New-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="7f6b1-176">New-TimeSpan</span></span>](New-TimeSpan.md)
