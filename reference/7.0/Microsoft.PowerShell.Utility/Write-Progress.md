---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-progress?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Progress
ms.openlocfilehash: 35b417b35d67e5cbe0df8719ba790135645d64e1
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "93232870"
---
# Write-Progress

## Краткий обзор
Отображает индикатор выполнения в командном окне PowerShell.

## SYNTAX

```
Write-Progress [-Activity] <String> [[-Status] <String>] [[-Id] <Int32>] [-PercentComplete <Int32>]
 [-SecondsRemaining <Int32>] [-CurrentOperation <String>] [-ParentId <Int32>] [-Completed] [-SourceId <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION

`Write-Progress`Командлет отображает индикатор выполнения в командном окне PowerShell, который показывает состояние выполняемой команды или скрипта. Можно выбрать параметры, которые отражает индикатор, а также текст, который отображается сверху и снизу от индикатора выполнения.

## Примеры

### Пример 1. Отображение хода выполнения цикла for

```powershell
for ($i = 1; $i -le 100; $i++ )
{
    Write-Progress -Activity "Search in Progress" -Status "$i% Complete:" -PercentComplete $i;
}
```

Эта команда отображает ход выполнения цикла For, который выполняет счет от 1 до 100.

`Write-Progress`Командлет включает заголовок строки состояния `Activity` , строку состояния и переменную `$i` (счетчик в цикле for), который указывает относительную полноту задачи.

### Пример 2. Отображение хода выполнения вложенных циклов for

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

В этом примере показан ход выполнения двух вложенных циклов For, каждый из которых представлен индикатором выполнения.

`Write-Progress`Команда для второго индикатора выполнения содержит параметр **ID** , который отличает его от первого индикатора выполнения.

Если параметр **ID** не указан, индикаторы выполнения будут наложены друг на друга, а не появятся друг за другом.

### Пример 3. Отображение хода выполнения при поиске строки

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

Эта команда отображает ход выполнения команды для поиска строки "bios" в журнале системных событий.

Значение параметра **PercentComplete** вычисляется путем деления количества событий, обработанных `$I` с помощью общего числа полученных событий, `$Events.count` и последующего умножения результата на 100.

### Пример 4. Отображение хода выполнения для каждого уровня вложенного процесса

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

В этом примере можно использовать параметр **ParentID** для отображения отступов, чтобы отображать отношения «родители-потомки» в ходе выполнения каждого шага.

## PARAMETERS

### — Действие

Указывает первую строку текста в заголовке над индикатором состояния.
Этот текст описывает действие, выполнение которого отражает индикатор.

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

### — Завершено

Указывает, отображается ли индикатор выполнения.
Если этот параметр не указан, `Write-Progress` отображает сведения о ходе выполнения.

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

### -CurrentOperation

Задает строку текста под индикатором выполнения.
Этот текст описывает операцию, которая выполняется в данный момент.

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

### -Id

Указывает идентификатор, который позволяет отличить отдельный индикатор выполнения от других индикаторов. Используйте этот параметр при создании нескольких индикаторов выполнения в рамках одной команды. Если у индикаторов выполнения нет отличающихся идентификаторов, они будут наложены друг на друга вместо отображения по порядку.

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

### -ParentId

Указывает родительское действие текущего действия.
Используйте значение -1, если текущее действие не имеет родительского действия.

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

### -PercentComplete

Указывает процент завершения действия.
Используйте значение -1, если процент выполнения неизвестен или неприменим.

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

### -Секондсремаининг

Указывает предполагаемое количество секунд, оставшихся до завершения действия.
Используйте значение -1, если число оставшихся секунд неизвестно или неприменимо.

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

### -SourceId

Указывает источник записи. Его можно использовать вместо **ID** , но нельзя использовать с другими параметрами, такими как **ParentID**.

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

### -Состояние

Указывает вторую строку текста в заголовке над индикатором состояния.
Этот текст описывает текущее состояние действия.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### Нет

В этот командлет нельзя передать входные данные.

## Выходные данные

### Нет

`Write-Progress` не создает никаких выходных данных.

## ПРИМЕЧАНИЯ

Если индикатор выполнения не отображается, проверьте значение `$ProgressPreference` переменной. Если установлено значение SilentlyContinue, индикатор выполнения не отображаются. Дополнительные сведения о настройках PowerShell см. в разделе [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).

Параметры командлета соответствуют свойствам класса **System. Management. Automation. ProgressRecord** . Дополнительные сведения см. в разделе [класс ProgressRecord](/dotnet/api/system.management.automation.progressrecord).

## Связанные ссылки

[Write-Debug](Write-Debug.md)

[Ошибка записи](Write-Error.md)

[Write-Host](Write-Host.md)

[Write-Output](Write-Output.md)

[Write-Progress](Write-Progress.md)

[Write-Verbose](Write-Verbose.md)

[Write-Warning](Write-Warning.md)
