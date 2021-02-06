---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-progress?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Progress
ms.openlocfilehash: 2e2bd5474198745d72ad2b87c3c305695a198f22
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602288"
---
# <span data-ttu-id="5271c-102">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="5271c-102">Write-Progress</span></span>

## <span data-ttu-id="5271c-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="5271c-103">SYNOPSIS</span></span>
<span data-ttu-id="5271c-104">Отображает индикатор выполнения в командном окне PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5271c-104">Displays a progress bar within a PowerShell command window.</span></span>

## <span data-ttu-id="5271c-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5271c-105">SYNTAX</span></span>

```
Write-Progress [-Activity] <String> [[-Status] <String>] [[-Id] <Int32>] [-PercentComplete <Int32>]
 [-SecondsRemaining <Int32>] [-CurrentOperation <String>] [-ParentId <Int32>] [-Completed] [-SourceId <Int32>]
 [<CommonParameters>]
```

## <span data-ttu-id="5271c-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5271c-106">DESCRIPTION</span></span>

<span data-ttu-id="5271c-107">`Write-Progress`Командлет отображает индикатор выполнения в командном окне PowerShell, который показывает состояние выполняемой команды или скрипта.</span><span class="sxs-lookup"><span data-stu-id="5271c-107">The `Write-Progress` cmdlet displays a progress bar in a PowerShell command window that depicts the status of a running command or script.</span></span> <span data-ttu-id="5271c-108">Можно выбрать параметры, которые отражает индикатор, а также текст, который отображается сверху и снизу от индикатора выполнения.</span><span class="sxs-lookup"><span data-stu-id="5271c-108">You can select the indicators that the bar reflects and the text that appears above and below the progress bar.</span></span>

## <span data-ttu-id="5271c-109">Примеры</span><span class="sxs-lookup"><span data-stu-id="5271c-109">EXAMPLES</span></span>

### <span data-ttu-id="5271c-110">Пример 1. Отображение хода выполнения цикла for</span><span class="sxs-lookup"><span data-stu-id="5271c-110">Example 1: Display the progress of a For loop</span></span>

```powershell
for ($i = 1; $i -le 100; $i++ )
{
    Write-Progress -Activity "Search in Progress" -Status "$i% Complete:" -PercentComplete $i;
}
```

<span data-ttu-id="5271c-111">Эта команда отображает ход выполнения цикла For, который выполняет счет от 1 до 100.</span><span class="sxs-lookup"><span data-stu-id="5271c-111">This command displays the progress of a For loop that counts from 1 to 100.</span></span>

<span data-ttu-id="5271c-112">`Write-Progress`Командлет включает заголовок строки состояния `Activity` , строку состояния и переменную `$i` (счетчик в цикле for), который указывает относительную полноту задачи.</span><span class="sxs-lookup"><span data-stu-id="5271c-112">The `Write-Progress` cmdlet includes a status bar heading `Activity`, a status line, and the variable `$i` (the counter in the For loop), which indicates the relative completeness of the task.</span></span>

### <span data-ttu-id="5271c-113">Пример 2. Отображение хода выполнения вложенных циклов for</span><span class="sxs-lookup"><span data-stu-id="5271c-113">Example 2: Display the progress of nested For loops</span></span>

```powershell
for($I = 1; $I -lt 101; $I++ )
{
    Write-Progress -Activity Updating -Status 'Progress->' -PercentComplete $I -CurrentOperation OuterLoop
    for($j = 1; $j -lt 101; $j++ )
    {
        Write-Progress -Id 1 -Activity Updating -Status 'Progress' -PercentComplete $j -CurrentOperation InnerLoop
    }
}
```

```Output
Updating
Progress ->
 [ooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooo]
OuterLoop
Updating
Progress
 [oooooooooooooooooo                                                   ]
InnerLoop
```

<span data-ttu-id="5271c-114">В этом примере показан ход выполнения двух вложенных циклов For, каждый из которых представлен индикатором выполнения.</span><span class="sxs-lookup"><span data-stu-id="5271c-114">This example displays the progress of two nested For loops, each of which is represented by a progress bar.</span></span>

<span data-ttu-id="5271c-115">`Write-Progress`Команда для второго индикатора выполнения содержит параметр **ID** , который отличает его от первого индикатора выполнения.</span><span class="sxs-lookup"><span data-stu-id="5271c-115">The `Write-Progress` command for the second progress bar includes the **Id** parameter that distinguishes it from the first progress bar.</span></span>

<span data-ttu-id="5271c-116">Если параметр **ID** не указан, индикаторы выполнения будут наложены друг на друга, а не появятся друг за другом.</span><span class="sxs-lookup"><span data-stu-id="5271c-116">Without the **Id** parameter, the progress bars would be superimposed on each other instead of being displayed one below the other.</span></span>

### <span data-ttu-id="5271c-117">Пример 3. Отображение хода выполнения при поиске строки</span><span class="sxs-lookup"><span data-stu-id="5271c-117">Example 3: Display the progress while searching for a string</span></span>

```powershell
# Use Get-EventLog to get the events in the System log and store them in the $Events variable.
$Events = Get-EventLog -LogName system
# Pipe the events to the ForEach-Object cmdlet.
$Events | ForEach-Object -Begin {
    # In the Begin block, use Clear-Host to clear the screen.
    Clear-Host
    # Set the $i counter variable to zero.
    $i = 0
    # Set the $out variable to a empty string.
    $out = ""
} -Process {
    # In the Process script block search the message property of each incoming object for "bios".
    if($_.message -like "*bios*")
    {
        # Append the matching message to the out variable.
        $out=$out + $_.Message
    }
    # Increment the $i counter variable which is used to create the progress bar.
    $i = $i+1
    # Use Write-Progress to output a progress bar.
    # The Activity and Status parameters create the first and second lines of the progress bar heading, respectively.
    Write-Progress -Activity "Searching Events" -Status "Progress:" -PercentComplete ($i/$Events.count*100)
} -End {
    # Display the matching messages using the out variable.
    $out
}
```

<span data-ttu-id="5271c-118">Эта команда отображает ход выполнения команды для поиска строки "bios" в журнале системных событий.</span><span class="sxs-lookup"><span data-stu-id="5271c-118">This command displays the progress of a command to find the string "bios" in the System event log.</span></span>

<span data-ttu-id="5271c-119">Значение параметра **PercentComplete** вычисляется путем деления количества событий, обработанных `$I` с помощью общего числа полученных событий, `$Events.count` и последующего умножения результата на 100.</span><span class="sxs-lookup"><span data-stu-id="5271c-119">The **PercentComplete** parameter value is calculated by dividing the number of events that have been processed `$I` by the total number of events retrieved `$Events.count` and then multiplying that result by 100.</span></span>

### <span data-ttu-id="5271c-120">Пример 4. Отображение хода выполнения для каждого уровня вложенного процесса</span><span class="sxs-lookup"><span data-stu-id="5271c-120">Example 4: Display progress for each level of a nested process</span></span>

```powershell
foreach ( $i in 1..10 ) {
  Write-Progress -Id 0 "Step $i"
  foreach ( $j in 1..10 ) {
    Write-Progress -Id 1 -ParentId 0 "Step $i - Substep $j"
    foreach ( $k in 1..10 ) {
      Write-Progress -Id 2  -ParentId 1 "Step $i - Substep $j - iteration $k"; start-sleep -m 150
    }
  }
}
```

```Output
Step 1
     Processing
    Step 1 - Substep 2
         Processing
        Step 1 - Substep 2 - Iteration 3
             Processing
```

<span data-ttu-id="5271c-121">В этом примере можно использовать параметр **ParentID** для отображения отступов, чтобы отображать отношения «родители-потомки» в ходе выполнения каждого шага.</span><span class="sxs-lookup"><span data-stu-id="5271c-121">In this example you can use the **ParentId** parameter to have indented output to show parent/child relationships in the progress of each step.</span></span>

## <span data-ttu-id="5271c-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5271c-122">PARAMETERS</span></span>

### <span data-ttu-id="5271c-123">— Действие</span><span class="sxs-lookup"><span data-stu-id="5271c-123">-Activity</span></span>

<span data-ttu-id="5271c-124">Указывает первую строку текста в заголовке над индикатором состояния.</span><span class="sxs-lookup"><span data-stu-id="5271c-124">Specifies the first line of text in the heading above the status bar.</span></span>
<span data-ttu-id="5271c-125">Этот текст описывает действие, выполнение которого отражает индикатор.</span><span class="sxs-lookup"><span data-stu-id="5271c-125">This text describes the activity whose progress is being reported.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5271c-126">— Завершено</span><span class="sxs-lookup"><span data-stu-id="5271c-126">-Completed</span></span>

<span data-ttu-id="5271c-127">Указывает, отображается ли индикатор выполнения.</span><span class="sxs-lookup"><span data-stu-id="5271c-127">Indicates whether the progress bar is visible.</span></span>
<span data-ttu-id="5271c-128">Если этот параметр не указан, `Write-Progress` отображает сведения о ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="5271c-128">If this parameter is omitted, `Write-Progress` displays progress information.</span></span>

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

### <span data-ttu-id="5271c-129">-CurrentOperation</span><span class="sxs-lookup"><span data-stu-id="5271c-129">-CurrentOperation</span></span>

<span data-ttu-id="5271c-130">Задает строку текста под индикатором выполнения.</span><span class="sxs-lookup"><span data-stu-id="5271c-130">Specifies the line of text below the progress bar.</span></span>
<span data-ttu-id="5271c-131">Этот текст описывает операцию, которая выполняется в данный момент.</span><span class="sxs-lookup"><span data-stu-id="5271c-131">This text describes the operation that is currently taking place.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5271c-132">-Id</span><span class="sxs-lookup"><span data-stu-id="5271c-132">-Id</span></span>

<span data-ttu-id="5271c-133">Указывает идентификатор, который позволяет отличить отдельный индикатор выполнения от других индикаторов.</span><span class="sxs-lookup"><span data-stu-id="5271c-133">Specifies an ID that distinguishes each progress bar from the others.</span></span> <span data-ttu-id="5271c-134">Используйте этот параметр при создании нескольких индикаторов выполнения в рамках одной команды.</span><span class="sxs-lookup"><span data-stu-id="5271c-134">Use this parameter when you are creating more than one progress bar in a single command.</span></span> <span data-ttu-id="5271c-135">Если у индикаторов выполнения нет отличающихся идентификаторов, они будут наложены друг на друга вместо отображения по порядку.</span><span class="sxs-lookup"><span data-stu-id="5271c-135">If the progress bars do not have different IDs, they are superimposed instead of being displayed in a series.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5271c-136">-ParentId</span><span class="sxs-lookup"><span data-stu-id="5271c-136">-ParentId</span></span>

<span data-ttu-id="5271c-137">Указывает родительское действие текущего действия.</span><span class="sxs-lookup"><span data-stu-id="5271c-137">Specifies the parent activity of the current activity.</span></span>
<span data-ttu-id="5271c-138">Используйте значение -1, если текущее действие не имеет родительского действия.</span><span class="sxs-lookup"><span data-stu-id="5271c-138">Use the value -1 if the current activity has no parent activity.</span></span>

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

### <span data-ttu-id="5271c-139">-PercentComplete</span><span class="sxs-lookup"><span data-stu-id="5271c-139">-PercentComplete</span></span>

<span data-ttu-id="5271c-140">Указывает процент завершения действия.</span><span class="sxs-lookup"><span data-stu-id="5271c-140">Specifies the percentage of the activity that is completed.</span></span>
<span data-ttu-id="5271c-141">Используйте значение -1, если процент выполнения неизвестен или неприменим.</span><span class="sxs-lookup"><span data-stu-id="5271c-141">Use the value -1 if the percentage complete is unknown or not applicable.</span></span>

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

### <span data-ttu-id="5271c-142">-Секондсремаининг</span><span class="sxs-lookup"><span data-stu-id="5271c-142">-SecondsRemaining</span></span>

<span data-ttu-id="5271c-143">Указывает предполагаемое количество секунд, оставшихся до завершения действия.</span><span class="sxs-lookup"><span data-stu-id="5271c-143">Specifies the projected number of seconds remaining until the activity is completed.</span></span>
<span data-ttu-id="5271c-144">Используйте значение -1, если число оставшихся секунд неизвестно или неприменимо.</span><span class="sxs-lookup"><span data-stu-id="5271c-144">Use the value -1 if the number of seconds remaining is unknown or not applicable.</span></span>

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

### <span data-ttu-id="5271c-145">-SourceId</span><span class="sxs-lookup"><span data-stu-id="5271c-145">-SourceId</span></span>

<span data-ttu-id="5271c-146">Указывает источник записи.</span><span class="sxs-lookup"><span data-stu-id="5271c-146">Specifies the source of the record.</span></span> <span data-ttu-id="5271c-147">Его можно использовать вместо **ID** , но нельзя использовать с другими параметрами, такими как **ParentID**.</span><span class="sxs-lookup"><span data-stu-id="5271c-147">You can use this in place of **Id** but cannot be used with other parameters like **ParentId**.</span></span>

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

### <span data-ttu-id="5271c-148">-Состояние</span><span class="sxs-lookup"><span data-stu-id="5271c-148">-Status</span></span>

<span data-ttu-id="5271c-149">Указывает вторую строку текста в заголовке над индикатором состояния.</span><span class="sxs-lookup"><span data-stu-id="5271c-149">Specifies the second line of text in the heading above the status bar.</span></span>
<span data-ttu-id="5271c-150">Этот текст описывает текущее состояние действия.</span><span class="sxs-lookup"><span data-stu-id="5271c-150">This text describes current state of the activity.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5271c-151">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="5271c-151">CommonParameters</span></span>

<span data-ttu-id="5271c-152">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5271c-152">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5271c-153">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="5271c-153">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="5271c-154">Входные данные</span><span class="sxs-lookup"><span data-stu-id="5271c-154">INPUTS</span></span>

### <span data-ttu-id="5271c-155">None</span><span class="sxs-lookup"><span data-stu-id="5271c-155">None</span></span>

<span data-ttu-id="5271c-156">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="5271c-156">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="5271c-157">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="5271c-157">OUTPUTS</span></span>

### <span data-ttu-id="5271c-158">None</span><span class="sxs-lookup"><span data-stu-id="5271c-158">None</span></span>

<span data-ttu-id="5271c-159">`Write-Progress` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="5271c-159">`Write-Progress` does not generate any output.</span></span>

## <span data-ttu-id="5271c-160">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="5271c-160">NOTES</span></span>

<span data-ttu-id="5271c-161">Если индикатор выполнения не отображается, проверьте значение `$ProgressPreference` переменной.</span><span class="sxs-lookup"><span data-stu-id="5271c-161">If the progress bar does not appear, check the value of the `$ProgressPreference` variable.</span></span> <span data-ttu-id="5271c-162">Если установлено значение SilentlyContinue, индикатор выполнения не отображаются.</span><span class="sxs-lookup"><span data-stu-id="5271c-162">If the value is set to SilentlyContinue, the progress bar is not displayed.</span></span> <span data-ttu-id="5271c-163">Дополнительные сведения о настройках PowerShell см. в разделе [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="5271c-163">For more information about PowerShell preferences, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="5271c-164">Параметры командлета соответствуют свойствам класса **System. Management. Automation. ProgressRecord** .</span><span class="sxs-lookup"><span data-stu-id="5271c-164">The parameters of the cmdlet correspond to the properties of the **System.Management.Automation.ProgressRecord** class.</span></span> <span data-ttu-id="5271c-165">Дополнительные сведения см. в разделе [класс ProgressRecord](/dotnet/api/system.management.automation.progressrecord).</span><span class="sxs-lookup"><span data-stu-id="5271c-165">For more information, see [ProgressRecord Class](/dotnet/api/system.management.automation.progressrecord).</span></span>

## <span data-ttu-id="5271c-166">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="5271c-166">RELATED LINKS</span></span>

[<span data-ttu-id="5271c-167">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="5271c-167">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="5271c-168">Write-Error</span><span class="sxs-lookup"><span data-stu-id="5271c-168">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="5271c-169">Write-Host</span><span class="sxs-lookup"><span data-stu-id="5271c-169">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="5271c-170">Write-Output</span><span class="sxs-lookup"><span data-stu-id="5271c-170">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="5271c-171">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="5271c-171">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="5271c-172">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="5271c-172">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="5271c-173">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="5271c-173">Write-Warning</span></span>](Write-Warning.md)
