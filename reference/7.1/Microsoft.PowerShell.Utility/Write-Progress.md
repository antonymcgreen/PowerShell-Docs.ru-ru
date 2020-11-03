---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-progress?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Progress
ms.openlocfilehash: 9e7aa9efce77e4c4c917658aeb2ecaabcd67e1e6
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "93232910"
---
# <span data-ttu-id="a0a65-103">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="a0a65-103">Write-Progress</span></span>

## <span data-ttu-id="a0a65-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a0a65-104">SYNOPSIS</span></span>
<span data-ttu-id="a0a65-105">Отображает индикатор выполнения в командном окне PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a0a65-105">Displays a progress bar within a PowerShell command window.</span></span>

## <span data-ttu-id="a0a65-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a0a65-106">SYNTAX</span></span>

```
Write-Progress [-Activity] <String> [[-Status] <String>] [[-Id] <Int32>] [-PercentComplete <Int32>]
 [-SecondsRemaining <Int32>] [-CurrentOperation <String>] [-ParentId <Int32>] [-Completed] [-SourceId <Int32>]
 [<CommonParameters>]
```

## <span data-ttu-id="a0a65-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a0a65-107">DESCRIPTION</span></span>

<span data-ttu-id="a0a65-108">`Write-Progress`Командлет отображает индикатор выполнения в командном окне PowerShell, который показывает состояние выполняемой команды или скрипта.</span><span class="sxs-lookup"><span data-stu-id="a0a65-108">The `Write-Progress` cmdlet displays a progress bar in a PowerShell command window that depicts the status of a running command or script.</span></span> <span data-ttu-id="a0a65-109">Можно выбрать параметры, которые отражает индикатор, а также текст, который отображается сверху и снизу от индикатора выполнения.</span><span class="sxs-lookup"><span data-stu-id="a0a65-109">You can select the indicators that the bar reflects and the text that appears above and below the progress bar.</span></span>

## <span data-ttu-id="a0a65-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="a0a65-110">EXAMPLES</span></span>

### <span data-ttu-id="a0a65-111">Пример 1. Отображение хода выполнения цикла for</span><span class="sxs-lookup"><span data-stu-id="a0a65-111">Example 1: Display the progress of a For loop</span></span>

```powershell
for ($i = 1; $i -le 100; $i++ )
{
    Write-Progress -Activity "Search in Progress" -Status "$i% Complete:" -PercentComplete $i;
}
```

<span data-ttu-id="a0a65-112">Эта команда отображает ход выполнения цикла For, который выполняет счет от 1 до 100.</span><span class="sxs-lookup"><span data-stu-id="a0a65-112">This command displays the progress of a For loop that counts from 1 to 100.</span></span>

<span data-ttu-id="a0a65-113">`Write-Progress`Командлет включает заголовок строки состояния `Activity` , строку состояния и переменную `$i` (счетчик в цикле for), который указывает относительную полноту задачи.</span><span class="sxs-lookup"><span data-stu-id="a0a65-113">The `Write-Progress` cmdlet includes a status bar heading `Activity`, a status line, and the variable `$i` (the counter in the For loop), which indicates the relative completeness of the task.</span></span>

### <span data-ttu-id="a0a65-114">Пример 2. Отображение хода выполнения вложенных циклов for</span><span class="sxs-lookup"><span data-stu-id="a0a65-114">Example 2: Display the progress of nested For loops</span></span>

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

<span data-ttu-id="a0a65-115">В этом примере показан ход выполнения двух вложенных циклов For, каждый из которых представлен индикатором выполнения.</span><span class="sxs-lookup"><span data-stu-id="a0a65-115">This example displays the progress of two nested For loops, each of which is represented by a progress bar.</span></span>

<span data-ttu-id="a0a65-116">`Write-Progress`Команда для второго индикатора выполнения содержит параметр **ID** , который отличает его от первого индикатора выполнения.</span><span class="sxs-lookup"><span data-stu-id="a0a65-116">The `Write-Progress` command for the second progress bar includes the **Id** parameter that distinguishes it from the first progress bar.</span></span>

<span data-ttu-id="a0a65-117">Если параметр **ID** не указан, индикаторы выполнения будут наложены друг на друга, а не появятся друг за другом.</span><span class="sxs-lookup"><span data-stu-id="a0a65-117">Without the **Id** parameter, the progress bars would be superimposed on each other instead of being displayed one below the other.</span></span>

### <span data-ttu-id="a0a65-118">Пример 3. Отображение хода выполнения при поиске строки</span><span class="sxs-lookup"><span data-stu-id="a0a65-118">Example 3: Display the progress while searching for a string</span></span>

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

<span data-ttu-id="a0a65-119">Эта команда отображает ход выполнения команды для поиска строки "bios" в журнале системных событий.</span><span class="sxs-lookup"><span data-stu-id="a0a65-119">This command displays the progress of a command to find the string "bios" in the System event log.</span></span>

<span data-ttu-id="a0a65-120">Значение параметра **PercentComplete** вычисляется путем деления количества событий, обработанных `$I` с помощью общего числа полученных событий, `$Events.count` и последующего умножения результата на 100.</span><span class="sxs-lookup"><span data-stu-id="a0a65-120">The **PercentComplete** parameter value is calculated by dividing the number of events that have been processed `$I` by the total number of events retrieved `$Events.count` and then multiplying that result by 100.</span></span>

### <span data-ttu-id="a0a65-121">Пример 4. Отображение хода выполнения для каждого уровня вложенного процесса</span><span class="sxs-lookup"><span data-stu-id="a0a65-121">Example 4: Display progress for each level of a nested process</span></span>

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

<span data-ttu-id="a0a65-122">В этом примере можно использовать параметр **ParentID** для отображения отступов, чтобы отображать отношения «родители-потомки» в ходе выполнения каждого шага.</span><span class="sxs-lookup"><span data-stu-id="a0a65-122">In this example you can use the **ParentId** parameter to have indented output to show parent/child relationships in the progress of each step.</span></span>

## <span data-ttu-id="a0a65-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a0a65-123">PARAMETERS</span></span>

### <span data-ttu-id="a0a65-124">— Действие</span><span class="sxs-lookup"><span data-stu-id="a0a65-124">-Activity</span></span>

<span data-ttu-id="a0a65-125">Указывает первую строку текста в заголовке над индикатором состояния.</span><span class="sxs-lookup"><span data-stu-id="a0a65-125">Specifies the first line of text in the heading above the status bar.</span></span>
<span data-ttu-id="a0a65-126">Этот текст описывает действие, выполнение которого отражает индикатор.</span><span class="sxs-lookup"><span data-stu-id="a0a65-126">This text describes the activity whose progress is being reported.</span></span>

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

### <span data-ttu-id="a0a65-127">— Завершено</span><span class="sxs-lookup"><span data-stu-id="a0a65-127">-Completed</span></span>

<span data-ttu-id="a0a65-128">Указывает, отображается ли индикатор выполнения.</span><span class="sxs-lookup"><span data-stu-id="a0a65-128">Indicates whether the progress bar is visible.</span></span>
<span data-ttu-id="a0a65-129">Если этот параметр не указан, `Write-Progress` отображает сведения о ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="a0a65-129">If this parameter is omitted, `Write-Progress` displays progress information.</span></span>

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

### <span data-ttu-id="a0a65-130">-CurrentOperation</span><span class="sxs-lookup"><span data-stu-id="a0a65-130">-CurrentOperation</span></span>

<span data-ttu-id="a0a65-131">Задает строку текста под индикатором выполнения.</span><span class="sxs-lookup"><span data-stu-id="a0a65-131">Specifies the line of text below the progress bar.</span></span>
<span data-ttu-id="a0a65-132">Этот текст описывает операцию, которая выполняется в данный момент.</span><span class="sxs-lookup"><span data-stu-id="a0a65-132">This text describes the operation that is currently taking place.</span></span>

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

### <span data-ttu-id="a0a65-133">-Id</span><span class="sxs-lookup"><span data-stu-id="a0a65-133">-Id</span></span>

<span data-ttu-id="a0a65-134">Указывает идентификатор, который позволяет отличить отдельный индикатор выполнения от других индикаторов.</span><span class="sxs-lookup"><span data-stu-id="a0a65-134">Specifies an ID that distinguishes each progress bar from the others.</span></span> <span data-ttu-id="a0a65-135">Используйте этот параметр при создании нескольких индикаторов выполнения в рамках одной команды.</span><span class="sxs-lookup"><span data-stu-id="a0a65-135">Use this parameter when you are creating more than one progress bar in a single command.</span></span> <span data-ttu-id="a0a65-136">Если у индикаторов выполнения нет отличающихся идентификаторов, они будут наложены друг на друга вместо отображения по порядку.</span><span class="sxs-lookup"><span data-stu-id="a0a65-136">If the progress bars do not have different IDs, they are superimposed instead of being displayed in a series.</span></span>

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

### <span data-ttu-id="a0a65-137">-ParentId</span><span class="sxs-lookup"><span data-stu-id="a0a65-137">-ParentId</span></span>

<span data-ttu-id="a0a65-138">Указывает родительское действие текущего действия.</span><span class="sxs-lookup"><span data-stu-id="a0a65-138">Specifies the parent activity of the current activity.</span></span>
<span data-ttu-id="a0a65-139">Используйте значение -1, если текущее действие не имеет родительского действия.</span><span class="sxs-lookup"><span data-stu-id="a0a65-139">Use the value -1 if the current activity has no parent activity.</span></span>

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

### <span data-ttu-id="a0a65-140">-PercentComplete</span><span class="sxs-lookup"><span data-stu-id="a0a65-140">-PercentComplete</span></span>

<span data-ttu-id="a0a65-141">Указывает процент завершения действия.</span><span class="sxs-lookup"><span data-stu-id="a0a65-141">Specifies the percentage of the activity that is completed.</span></span>
<span data-ttu-id="a0a65-142">Используйте значение -1, если процент выполнения неизвестен или неприменим.</span><span class="sxs-lookup"><span data-stu-id="a0a65-142">Use the value -1 if the percentage complete is unknown or not applicable.</span></span>

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

### <span data-ttu-id="a0a65-143">-Секондсремаининг</span><span class="sxs-lookup"><span data-stu-id="a0a65-143">-SecondsRemaining</span></span>

<span data-ttu-id="a0a65-144">Указывает предполагаемое количество секунд, оставшихся до завершения действия.</span><span class="sxs-lookup"><span data-stu-id="a0a65-144">Specifies the projected number of seconds remaining until the activity is completed.</span></span>
<span data-ttu-id="a0a65-145">Используйте значение -1, если число оставшихся секунд неизвестно или неприменимо.</span><span class="sxs-lookup"><span data-stu-id="a0a65-145">Use the value -1 if the number of seconds remaining is unknown or not applicable.</span></span>

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

### <span data-ttu-id="a0a65-146">-SourceId</span><span class="sxs-lookup"><span data-stu-id="a0a65-146">-SourceId</span></span>

<span data-ttu-id="a0a65-147">Указывает источник записи.</span><span class="sxs-lookup"><span data-stu-id="a0a65-147">Specifies the source of the record.</span></span> <span data-ttu-id="a0a65-148">Его можно использовать вместо **ID** , но нельзя использовать с другими параметрами, такими как **ParentID** .</span><span class="sxs-lookup"><span data-stu-id="a0a65-148">You can use this in place of **Id** but cannot be used with other parameters like **ParentId** .</span></span>

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

### <span data-ttu-id="a0a65-149">-Состояние</span><span class="sxs-lookup"><span data-stu-id="a0a65-149">-Status</span></span>

<span data-ttu-id="a0a65-150">Указывает вторую строку текста в заголовке над индикатором состояния.</span><span class="sxs-lookup"><span data-stu-id="a0a65-150">Specifies the second line of text in the heading above the status bar.</span></span>
<span data-ttu-id="a0a65-151">Этот текст описывает текущее состояние действия.</span><span class="sxs-lookup"><span data-stu-id="a0a65-151">This text describes current state of the activity.</span></span>

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

### <span data-ttu-id="a0a65-152">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a0a65-152">CommonParameters</span></span>

<span data-ttu-id="a0a65-153">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a0a65-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a0a65-154">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="a0a65-154">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="a0a65-155">Входные данные</span><span class="sxs-lookup"><span data-stu-id="a0a65-155">INPUTS</span></span>

### <span data-ttu-id="a0a65-156">Нет</span><span class="sxs-lookup"><span data-stu-id="a0a65-156">None</span></span>

<span data-ttu-id="a0a65-157">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="a0a65-157">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="a0a65-158">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a0a65-158">OUTPUTS</span></span>

### <span data-ttu-id="a0a65-159">Нет</span><span class="sxs-lookup"><span data-stu-id="a0a65-159">None</span></span>

<span data-ttu-id="a0a65-160">`Write-Progress` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="a0a65-160">`Write-Progress` does not generate any output.</span></span>

## <span data-ttu-id="a0a65-161">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="a0a65-161">NOTES</span></span>

<span data-ttu-id="a0a65-162">Если индикатор выполнения не отображается, проверьте значение `$ProgressPreference` переменной.</span><span class="sxs-lookup"><span data-stu-id="a0a65-162">If the progress bar does not appear, check the value of the `$ProgressPreference` variable.</span></span> <span data-ttu-id="a0a65-163">Если установлено значение SilentlyContinue, индикатор выполнения не отображаются.</span><span class="sxs-lookup"><span data-stu-id="a0a65-163">If the value is set to SilentlyContinue, the progress bar is not displayed.</span></span> <span data-ttu-id="a0a65-164">Дополнительные сведения о настройках PowerShell см. в разделе [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="a0a65-164">For more information about PowerShell preferences, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="a0a65-165">Параметры командлета соответствуют свойствам класса **System. Management. Automation. ProgressRecord** .</span><span class="sxs-lookup"><span data-stu-id="a0a65-165">The parameters of the cmdlet correspond to the properties of the **System.Management.Automation.ProgressRecord** class.</span></span> <span data-ttu-id="a0a65-166">Дополнительные сведения см. в разделе [класс ProgressRecord](/dotnet/api/system.management.automation.progressrecord).</span><span class="sxs-lookup"><span data-stu-id="a0a65-166">For more information, see [ProgressRecord Class](/dotnet/api/system.management.automation.progressrecord).</span></span>

## <span data-ttu-id="a0a65-167">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a0a65-167">RELATED LINKS</span></span>

[<span data-ttu-id="a0a65-168">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="a0a65-168">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="a0a65-169">Ошибка записи</span><span class="sxs-lookup"><span data-stu-id="a0a65-169">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="a0a65-170">Write-Host</span><span class="sxs-lookup"><span data-stu-id="a0a65-170">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="a0a65-171">Write-Output</span><span class="sxs-lookup"><span data-stu-id="a0a65-171">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="a0a65-172">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="a0a65-172">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="a0a65-173">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="a0a65-173">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="a0a65-174">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="a0a65-174">Write-Warning</span></span>](Write-Warning.md)
