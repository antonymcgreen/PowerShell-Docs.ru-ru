---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/import-counter?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Counter
ms.openlocfilehash: 837f6b4b3b2869c6f74b3b02904dd43b73f6bcd5
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227001"
---
# Import-Counter

## Краткий обзор
Импортирует файлы журналов счетчиков производительности и создает объекты, представляющие пример каждого счетчика в журнале.

## SYNTAX

### CounterSet (по умолчанию)

```
Import-Counter [-Path] <String[]> [-StartTime <DateTime>] [-EndTime <DateTime>] [-Counter <String[]>]
 [-MaxSamples <Int64>] [<CommonParameters>]
```

### листсетсет

```
Import-Counter [-Path] <String[]> -ListSet <String[]> [<CommonParameters>]
```

### Сводный список

```
Import-Counter [-Path] <String[]> [-Summary] [<CommonParameters>]
```

## DESCRIPTION

Командлет **Import-Counter** импортирует данные счетчика производительности из файлов журнала счетчика производительности и создает объекты для каждого образца счетчика в файле.
Создаваемые им объекты **PerformanceCounterSampleSet** идентичны объектам, возвращаемым командлетом **Get-Counter** при сборе данных счетчиков производительности.

Вы можете импортировать данные из файлов журнала производительности в формате CSV, TSV и BLG.
При использовании BLG Files можно импортировать до 32 файлов в каждой команде.
Параметры **импорта-Counter** можно использовать для фильтрации импортируемых данных.

Вместе с командлетами Get-Counter и Export-Counter эта функция позволяет собрать, экспортировать, импортировать, объединить, отфильтровать и повторно экспортировать данные счетчиков производительности в Windows PowerShell.

## Примеры

### Пример 1. импорт всех данных счетчиков из файла

```powershell
$Data = Import-Counter -Path ProcessorData.csv
```

Эта команда импортирует все данные счетчиков из файла ProcessorData.csv в переменную $Data.

### Пример 2. импорт конкретных данных счетчиков из файла

```
PS C:\> $I = Import-Counter -Path "ProcessorData.blg" -Counter "\\SERVER01\Processor(_Total)\Interrupts/sec"
```

Эта команда импортирует данные счетчика **"процессор (_Total) \ прерываний/с"** из файла процессордата. blg в переменную $I.

### Пример 3. Выбор данных из счетчика производительности с последующим экспортом в файл

```
The first command uses **Import-Counter** to import all of the performance counter data from the ProcessorData.blg files. The command saves the data in the $Data variable.
PS C:\> $Data = Import-Counter .\ProcessorData.blg

The second command displays the counter paths in the $Data variable. To get the display shown in the command output, the example uses the Format-Table cmdlet to format as a table the counter paths of the first counter in the $Data variable.
PS C:\> $Data[0].CounterSamples | Format-Table -Property Path

Path
----
\\SERVER01\Processor(_Total)\DPC Rate
\\SERVER01\Processor(1)\DPC Rate
\\SERVER01\Processor(0)\DPC Rate
\\SERVER01\Processor(_Total)\% Idle Time
\\SERVER01\Processor(1)\% Idle Time
\\SERVER01\Processor(0)\% Idle Time
\\SERVER01\Processor(_Total)\% C3 Time
\\SERVER01\Processor(1)\% C3 Time

The third command gets the counter paths that end in "Interrupts/sec" and saves the paths in the $IntCtrs variable. It uses the Where-Object cmdlet to filter the counter paths and the ForEach-Object cmdlet to get only the value of the **Path** property of each selected path object.
PS C:\> $IntCtrs = $Data[0].Countersamples | Where-Object {$_.Path -like "*Interrupts/sec"} | ForEach-Object {$_.Path}

The fourth command displays the selected counter paths in the $IntCtrs variable.
PS C:\> $IntCtrs

\\SERVER01\Processor(_Total)\Interrupts/sec
\\SERVER01\Processor(1)\Interrupts/sec
\\SERVER01\Processor(0)\Interrupts/sec

The fifth command uses the **Import-Counter** cmdlet to import the data. It uses the $IntCtrs variable as the value of the *Counter* parameter to import only data for the counter paths in $IntCtrs.
PS C:\> $I = Import-Counter -Path .\ProcessorData.blg -Counter $intCtrs

The sixth command uses the Export-Counter cmdlet to export the data to the Interrupts.csv file.
PS C:\> $I | Export-Counter -Path .\Interrupts.csv -Format CSV
```

В этом примере показано, как выбрать данные из файла журнала счетчиков производительности (BLG), а затем экспортировать их в CSV-файл.
Первые четыре команды получают пути счетчиков из файла и сохраняют их в переменной с именем $Data.
Последние две команды импортируют выбранные данные, а затем экспортируют только выбранные данные.

### Пример 4. Отображение всех путей счетчиков в группе импортированных наборов счетчиков

```
The first command uses the *ListSet* parameter of the **Import-Counter** cmdlet to get all of the counter sets that are represented in a counter data file.
PS C:\> Import-Counter -Path ProcessorData.csv -ListSet *

CounterSetName     : Processor
MachineName        : \\SERVER01
CounterSetType     : MultiInstance
Description        :
Paths              : {\\SERVER01\Processor(*)\DPC Rate, \\SERVER01\Processor(*)\% Idle Time, \\SERVER01
\Processor(*)\% C3 Time, \\SERVER01\Processor(*)\% Interrupt Time...}
PathsWithInstances : {\\SERVER01\Processor(_Total)\DPC Rate, \\SERVER01\Processor(1)\DPC Rate, \\SERVER01
\Processor(0)\DPC Rate, \\SERVER01\Processor(_Total)\% Idle Time...}
Counter            : {\\SERVER01\Processor(*)\DPC Rate, \\SERVER01\Processor(*)\% Idle Time, \\SERVER01
\Processor(*)\% C3 Time, \\SERVER01\Processor(*)\% Interrupt Time...}

The second command gets all of the counter paths from the list set.
PS C:\> Import-Counter -Path ProcessorData.csv -ListSet * | ForEach-Object {$_.Paths}

\\SERVER01\Processor(*)\DPC Rate
\\SERVER01\Processor(*)\% Idle Time
\\SERVER01\Processor(*)\% C3 Time
\\SERVER01\Processor(*)\% Interrupt Time
\\SERVER01\Processor(*)\% C2 Time
\\SERVER01\Processor(*)\% User Time
\\SERVER01\Processor(*)\% C1 Time
\\SERVER01\Processor(*)\% Processor Time
\\SERVER01\Processor(*)\C1 Transitions/sec
\\SERVER01\Processor(*)\% DPC Time
\\SERVER01\Processor(*)\C2 Transitions/sec
\\SERVER01\Processor(*)\% Privileged Time
\\SERVER01\Processor(*)\C3 Transitions/sec
\\SERVER01\Processor(*)\DPCs Queued/sec
\\SERVER01\Processor(*)\Interrupts/sec
```

В этом примере показано, как показать все пути счетчиков в группе импортированных наборов счетчиков.

### Пример 5. Импорт данных счетчика из диапазона меток времени

```
The first command lists in a table the time stamps of all of the data in the ProcessorData.blg file.
PS C:\> Import-Counter -Path ".\disk.blg" | Format-Table -Property Timestamp

The second command saves particular time stamps in the $Start and $End variables. The strings are cast to **DateTime** objects.
PS C:\> $Start = [datetime]"7/9/2008 3:47:00 PM"; $End = [datetime]"7/9/2008 3:47:59 PM"

The third command uses the **Import-Counter** cmdlet to get only counter data that has a time stamp between the start and end times (inclusive). The command uses the *StartTime* and *EndTime* parameters of **Import-Counter** to specify the range.
PS C:\> Import-Counter -Path Disk.blg -StartTime $start -EndTime $end
```

В этом примере показано, как импортировать только данные счетчиков с отметкой времени между начальным и конечным диапазонами, указанными в команде.

### Пример 6. импорт указанного числа самых старых выборок из файла журнала счетчика производительности

```
The first command uses the **Import-Counter** cmdlet to import the first (oldest) five samples from the Disk.blg file. The command uses the *MaxSamples* parameter to limit the import to five counter samples.
PS C:\> Import-Counter -Path "Disk.blg" -MaxSamples 5

The second command uses array notation and the Windows PowerShell range operator (..) to get the last five counter samples from the file. These are the five newest samples.
PS C:\> (Import-Counter -Path Disk.blg)[-1 .. -5]
```

В этом примере показано, как импортировать пять самых старых и пять самых новых показаний из файла журнала счетчиков производительности.

### Пример 7. получение сводки данных счетчиков из файла

```
PS C:\> Import-Counter "D:\Samples\Memory.blg" -Summary

OldestRecord            NewestRecord            SampleCount
------------            ------------            -----------
7/10/2008 2:59:18 PM    7/10/2008 3:00:27 PM    1000
```

Эта команда использует параметр *Summary* командлета **Import-Counter** , чтобы получить сводку данных счетчиков в файле Memory.blg.

### Пример 8. Обновление файла журнала счетчика производительности

```
The first command uses the *ListSet* parameter of **Import-Counter** to get the counters in OldData.blg, an existing counter log file. The command uses a pipeline operator (|) to send the data to a ForEach-Object command that gets only the values of the **PathsWithInstances** property of each object
PS C:\> $Counters = Import-Counter OldData.blg -ListSet * | ForEach-Object {$_.PathsWithInstances}

The second command gets updated data for the counters in the $Counters variable. It uses the Get-Counter cmdlet to get a current sample, and then export the results to the NewData.blg file.
PS C:\> Get-Counter -Counter $Counters -MaxSamples 20 | Export-Counter C:\Logs\NewData.blg
```

Этот пример обновляет файл журнала счетчиков производительности.

### Пример 9. Импорт данных журнала производительности из нескольких файлов и их сохранение

```
PS C:\> $Counters = "D:\test\pdata.blg", "D:\samples\netlog.blg" | Import-Counter
```

Эта команда импортирует данные журнала производительности из двух журналов и сохраняет их в переменной $Counters.
Команда использует оператор конвейера для передачи путей журнала производительности командлету Import-Counter, который импортирует данные из указанных путей.

Обратите внимание, что каждый путь заключен в кавычки и что пути разделены запятыми.

## PARAMETERS

### -Counter

Указывает счетчики производительности в виде массива строк.
По умолчанию Import **-Counter** импортирует все данные из всех счетчиков во входных файлах.
Введите один или несколько путей счетчиков.
Знаки подстановки разрешены в части Instance.

Для каждого пути счетчика используется следующий формат.
В пути требуется значение ComputerName.
например

- `\\<ComputerName>\<CounterSet>(<Instance>)\<CounterName>`

Пример:

- `\\Server01\Processor(2)\% User Time`
- `\\Server01\Processor(*)\% Processor Time`

```yaml
Type: System.String[]
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: All counter
Accept pipeline input: False
Accept wildcard characters: True
```

### -EndTime

Задает конечную дату и время, когда этот командлет импортирует данные счетчика между значениями времени *начала* и этого параметра.
Введите объект **DateTime** , например созданный командлетом Get-Date.
По умолчанию командлет **Import-Counter** импортирует все данные счетчиков в файлах, указанных параметром *path* .

```yaml
Type: System.DateTime
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: No end time
Accept pipeline input: False
Accept wildcard characters: False
```

### — Список

Задает наборы счетчиков производительности, которые представлены в экспортированных файлах.
Команды с этим параметром не импортируют какие-либо данные.

Введите одно или несколько имен наборов счетчиков.
Разрешено использовать подстановочные знаки.
Чтобы получить все наборы счетчиков в файле, введите `Import-Counter -ListSet *` .

```yaml
Type: System.String[]
Parameter Sets: ListSetSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Макссамплес

Указывает максимальное число выборок каждого счетчика, которые необходимо импортировать.
По умолчанию командлет **Get-Counter** импортирует все данные в файлах, указанных параметром *path* .

```yaml
Type: System.Int64
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: No maximum
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Указывает путей к файлам для импорта.
Этот параметр обязателен.

Введите путь и имя файла, CSV,,. tsv или. BLG, экспортированного с помощью командлета **Export-Counter** .
Можно указать только один CSV- или TSV-файл, но в каждой команде можно задать до 32 BLG-файлов.
Можно также передать строки пути к файлам (в кавычках) в командлет **Import-Counter**.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -StartTime

Указывает начальную дату и время, в которые этот командлет получает данные счетчика.
Введите объект **DateTime** , например созданный командлетом **Get-Date** .
По умолчанию командлет **Import-Counter** импортирует все данные счетчиков в файлах, указанных параметром *path* .

```yaml
Type: System.DateTime
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: No start time
Accept pipeline input: False
Accept wildcard characters: False
```

### -Summary

Указывает, что этот командлет получает сводку импортированных данных вместо отдельных выборок данных счетчиков.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SummarySet
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

К этому командлету можно передать пути журналов счетчиков производительности.

## Выходные данные

### Microsoft. PowerShell. Commands. NOCOUNT. PerformanceCounterSampleSet, Microsoft. PowerShell. Commands. NOCOUNT. Counters, Microsoft. PowerShell. Commands. NOCOUNT. Каунтерфилеинфо

Этот командлет возвращает объект **Microsoft. PowerShell. Commands. NOCOUNT. PerformanceCounterSampleSet**.
Если используется параметр *List* , этот командлет возвращает объект **Microsoft. PowerShell. Commands. NOCOUNT. Counter** .
При использовании параметра *сводки* этот командлет возвращает объект **Microsoft. PowerShell. Commands. GetObject. каунтерфилеинфо** .

## ПРИМЕЧАНИЯ

* У этого командлета нет параметра *ComputerName* . Однако если компьютер настроен для удаленного взаимодействия Windows PowerShell, можно использовать командлет Invoke-Command для выполнения команды **Import-Counter** на удаленном компьютере.

## Связанные ссылки

[Export-Counter](Export-Counter.md)

[Get-Counter](Get-Counter.md)
