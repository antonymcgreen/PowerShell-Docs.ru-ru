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
# <span data-ttu-id="60d37-103">Import-Counter</span><span class="sxs-lookup"><span data-stu-id="60d37-103">Import-Counter</span></span>

## <span data-ttu-id="60d37-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="60d37-104">SYNOPSIS</span></span>
<span data-ttu-id="60d37-105">Импортирует файлы журналов счетчиков производительности и создает объекты, представляющие пример каждого счетчика в журнале.</span><span class="sxs-lookup"><span data-stu-id="60d37-105">Imports performance counter log files and creates the objects that represent each counter sample in the log.</span></span>

## <span data-ttu-id="60d37-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="60d37-106">SYNTAX</span></span>

### <span data-ttu-id="60d37-107">CounterSet (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="60d37-107">GetCounterSet (Default)</span></span>

```
Import-Counter [-Path] <String[]> [-StartTime <DateTime>] [-EndTime <DateTime>] [-Counter <String[]>]
 [-MaxSamples <Int64>] [<CommonParameters>]
```

### <span data-ttu-id="60d37-108">листсетсет</span><span class="sxs-lookup"><span data-stu-id="60d37-108">ListSetSet</span></span>

```
Import-Counter [-Path] <String[]> -ListSet <String[]> [<CommonParameters>]
```

### <span data-ttu-id="60d37-109">Сводный список</span><span class="sxs-lookup"><span data-stu-id="60d37-109">SummarySet</span></span>

```
Import-Counter [-Path] <String[]> [-Summary] [<CommonParameters>]
```

## <span data-ttu-id="60d37-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="60d37-110">DESCRIPTION</span></span>

<span data-ttu-id="60d37-111">Командлет **Import-Counter** импортирует данные счетчика производительности из файлов журнала счетчика производительности и создает объекты для каждого образца счетчика в файле.</span><span class="sxs-lookup"><span data-stu-id="60d37-111">The **Import-Counter** cmdlet imports performance counter data from performance counter log files and creates objects for each counter sample in the file.</span></span>
<span data-ttu-id="60d37-112">Создаваемые им объекты **PerformanceCounterSampleSet** идентичны объектам, возвращаемым командлетом **Get-Counter** при сборе данных счетчиков производительности.</span><span class="sxs-lookup"><span data-stu-id="60d37-112">The **PerformanceCounterSampleSet** objects that it creates are identical to the objects that **Get-Counter** returns when it collects performance counter data.</span></span>

<span data-ttu-id="60d37-113">Вы можете импортировать данные из файлов журнала производительности в формате CSV, TSV и BLG.</span><span class="sxs-lookup"><span data-stu-id="60d37-113">You can import data from comma-separated value (.csv), tab-separated value ( .tsv), and binary performance log (.blg) performance log files.</span></span>
<span data-ttu-id="60d37-114">При использовании BLG Files можно импортировать до 32 файлов в каждой команде.</span><span class="sxs-lookup"><span data-stu-id="60d37-114">If you are using .blg files, you can import up to 32 files in each command.</span></span>
<span data-ttu-id="60d37-115">Параметры **импорта-Counter** можно использовать для фильтрации импортируемых данных.</span><span class="sxs-lookup"><span data-stu-id="60d37-115">You can use the parameters of **Import-Counter** to filter the data that you import.</span></span>

<span data-ttu-id="60d37-116">Вместе с командлетами Get-Counter и Export-Counter эта функция позволяет собрать, экспортировать, импортировать, объединить, отфильтровать и повторно экспортировать данные счетчиков производительности в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="60d37-116">Along with the Get-Counter and Export-Counter cmdlets, this feature lets you collect, export, import, combine, filter, manipulate, and re-export performance counter data within Windows PowerShell.</span></span>

## <span data-ttu-id="60d37-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="60d37-117">EXAMPLES</span></span>

### <span data-ttu-id="60d37-118">Пример 1. импорт всех данных счетчиков из файла</span><span class="sxs-lookup"><span data-stu-id="60d37-118">Example 1: Import all counter data from a file</span></span>

```powershell
$Data = Import-Counter -Path ProcessorData.csv
```

<span data-ttu-id="60d37-119">Эта команда импортирует все данные счетчиков из файла ProcessorData.csv в переменную $Data.</span><span class="sxs-lookup"><span data-stu-id="60d37-119">This command imports all counter data from the ProcessorData.csv file into the $Data variable.</span></span>

### <span data-ttu-id="60d37-120">Пример 2. импорт конкретных данных счетчиков из файла</span><span class="sxs-lookup"><span data-stu-id="60d37-120">Example 2: Import specific counter data from a file</span></span>

```
PS C:\> $I = Import-Counter -Path "ProcessorData.blg" -Counter "\\SERVER01\Processor(_Total)\Interrupts/sec"
```

<span data-ttu-id="60d37-121">Эта команда импортирует данные счетчика **"процессор (_Total) \ прерываний/с"** из файла процессордата. blg в переменную $I.</span><span class="sxs-lookup"><span data-stu-id="60d37-121">This command imports only the **"Processor(_total)\Interrupts/sec"** counter data from the ProcessorData.blg file into the $I variable.</span></span>

### <span data-ttu-id="60d37-122">Пример 3. Выбор данных из счетчика производительности с последующим экспортом в файл</span><span class="sxs-lookup"><span data-stu-id="60d37-122">Example 3: Select data from a performance counter then export it to a file</span></span>

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

<span data-ttu-id="60d37-123">В этом примере показано, как выбрать данные из файла журнала счетчиков производительности (BLG), а затем экспортировать их в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="60d37-123">This example shows how to select data from a performance counter log file (.blg) and then export the selected data to a .csv file.</span></span>
<span data-ttu-id="60d37-124">Первые четыре команды получают пути счетчиков из файла и сохраняют их в переменной с именем $Data.</span><span class="sxs-lookup"><span data-stu-id="60d37-124">The first four commands get the counter paths from the file and save them in the variable named $Data.</span></span>
<span data-ttu-id="60d37-125">Последние две команды импортируют выбранные данные, а затем экспортируют только выбранные данные.</span><span class="sxs-lookup"><span data-stu-id="60d37-125">The last two commands import selected data and then export only the selected data.</span></span>

### <span data-ttu-id="60d37-126">Пример 4. Отображение всех путей счетчиков в группе импортированных наборов счетчиков</span><span class="sxs-lookup"><span data-stu-id="60d37-126">Example 4: Display all counter paths in a group of imported counter sets</span></span>

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

<span data-ttu-id="60d37-127">В этом примере показано, как показать все пути счетчиков в группе импортированных наборов счетчиков.</span><span class="sxs-lookup"><span data-stu-id="60d37-127">This example shows how to display all the counter paths in a group of imported counter sets.</span></span>

### <span data-ttu-id="60d37-128">Пример 5. Импорт данных счетчика из диапазона меток времени</span><span class="sxs-lookup"><span data-stu-id="60d37-128">Example 5: Import counter data from a range of time stamps</span></span>

```
The first command lists in a table the time stamps of all of the data in the ProcessorData.blg file.
PS C:\> Import-Counter -Path ".\disk.blg" | Format-Table -Property Timestamp

The second command saves particular time stamps in the $Start and $End variables. The strings are cast to **DateTime** objects.
PS C:\> $Start = [datetime]"7/9/2008 3:47:00 PM"; $End = [datetime]"7/9/2008 3:47:59 PM"

The third command uses the **Import-Counter** cmdlet to get only counter data that has a time stamp between the start and end times (inclusive). The command uses the *StartTime* and *EndTime* parameters of **Import-Counter** to specify the range.
PS C:\> Import-Counter -Path Disk.blg -StartTime $start -EndTime $end
```

<span data-ttu-id="60d37-129">В этом примере показано, как импортировать только данные счетчиков с отметкой времени между начальным и конечным диапазонами, указанными в команде.</span><span class="sxs-lookup"><span data-stu-id="60d37-129">This example imports only the counter data that has a time stamp between the starting an ending ranges specified in the command.</span></span>

### <span data-ttu-id="60d37-130">Пример 6. импорт указанного числа самых старых выборок из файла журнала счетчика производительности</span><span class="sxs-lookup"><span data-stu-id="60d37-130">Example 6: Import a specified number of the oldest samples from a performance counter log file</span></span>

```
The first command uses the **Import-Counter** cmdlet to import the first (oldest) five samples from the Disk.blg file. The command uses the *MaxSamples* parameter to limit the import to five counter samples.
PS C:\> Import-Counter -Path "Disk.blg" -MaxSamples 5

The second command uses array notation and the Windows PowerShell range operator (..) to get the last five counter samples from the file. These are the five newest samples.
PS C:\> (Import-Counter -Path Disk.blg)[-1 .. -5]
```

<span data-ttu-id="60d37-131">В этом примере показано, как импортировать пять самых старых и пять самых новых показаний из файла журнала счетчиков производительности.</span><span class="sxs-lookup"><span data-stu-id="60d37-131">This example shows how to import the five oldest and five newest samples from a performance counter log file.</span></span>

### <span data-ttu-id="60d37-132">Пример 7. получение сводки данных счетчиков из файла</span><span class="sxs-lookup"><span data-stu-id="60d37-132">Example 7: Get a summary of counter data from a file</span></span>

```
PS C:\> Import-Counter "D:\Samples\Memory.blg" -Summary

OldestRecord            NewestRecord            SampleCount
------------            ------------            -----------
7/10/2008 2:59:18 PM    7/10/2008 3:00:27 PM    1000
```

<span data-ttu-id="60d37-133">Эта команда использует параметр *Summary* командлета **Import-Counter** , чтобы получить сводку данных счетчиков в файле Memory.blg.</span><span class="sxs-lookup"><span data-stu-id="60d37-133">This command uses the *Summary* parameter of the **Import-Counter** cmdlet to get a summary of the counter data in the Memory.blg file.</span></span>

### <span data-ttu-id="60d37-134">Пример 8. Обновление файла журнала счетчика производительности</span><span class="sxs-lookup"><span data-stu-id="60d37-134">Example 8: Update a performance counter log file</span></span>

```
The first command uses the *ListSet* parameter of **Import-Counter** to get the counters in OldData.blg, an existing counter log file. The command uses a pipeline operator (|) to send the data to a ForEach-Object command that gets only the values of the **PathsWithInstances** property of each object
PS C:\> $Counters = Import-Counter OldData.blg -ListSet * | ForEach-Object {$_.PathsWithInstances}

The second command gets updated data for the counters in the $Counters variable. It uses the Get-Counter cmdlet to get a current sample, and then export the results to the NewData.blg file.
PS C:\> Get-Counter -Counter $Counters -MaxSamples 20 | Export-Counter C:\Logs\NewData.blg
```

<span data-ttu-id="60d37-135">Этот пример обновляет файл журнала счетчиков производительности.</span><span class="sxs-lookup"><span data-stu-id="60d37-135">This example updates a performance counter log file.</span></span>

### <span data-ttu-id="60d37-136">Пример 9. Импорт данных журнала производительности из нескольких файлов и их сохранение</span><span class="sxs-lookup"><span data-stu-id="60d37-136">Example 9: Import performance log data from multiple files and then save it</span></span>

```
PS C:\> $Counters = "D:\test\pdata.blg", "D:\samples\netlog.blg" | Import-Counter
```

<span data-ttu-id="60d37-137">Эта команда импортирует данные журнала производительности из двух журналов и сохраняет их в переменной $Counters.</span><span class="sxs-lookup"><span data-stu-id="60d37-137">This command imports performance log data from two logs and saves the data in the $Counters variable.</span></span>
<span data-ttu-id="60d37-138">Команда использует оператор конвейера для передачи путей журнала производительности командлету Import-Counter, который импортирует данные из указанных путей.</span><span class="sxs-lookup"><span data-stu-id="60d37-138">The command uses a pipeline operator to send the performance log paths to Import-Counter, which imports the data from the specified paths.</span></span>

<span data-ttu-id="60d37-139">Обратите внимание, что каждый путь заключен в кавычки и что пути разделены запятыми.</span><span class="sxs-lookup"><span data-stu-id="60d37-139">Notice that each path is enclosed in quotation marks and that the paths are separated from each other by a comma.</span></span>

## <span data-ttu-id="60d37-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="60d37-140">PARAMETERS</span></span>

### <span data-ttu-id="60d37-141">-Counter</span><span class="sxs-lookup"><span data-stu-id="60d37-141">-Counter</span></span>

<span data-ttu-id="60d37-142">Указывает счетчики производительности в виде массива строк.</span><span class="sxs-lookup"><span data-stu-id="60d37-142">Specifies, as a string array, the performance counters.</span></span>
<span data-ttu-id="60d37-143">По умолчанию Import **-Counter** импортирует все данные из всех счетчиков во входных файлах.</span><span class="sxs-lookup"><span data-stu-id="60d37-143">By default, **Import-Counter** imports all data from all counters in the input files.</span></span>
<span data-ttu-id="60d37-144">Введите один или несколько путей счетчиков.</span><span class="sxs-lookup"><span data-stu-id="60d37-144">Enter one or more counter paths.</span></span>
<span data-ttu-id="60d37-145">Знаки подстановки разрешены в части Instance.</span><span class="sxs-lookup"><span data-stu-id="60d37-145">Wildcards are permitted in the Instance part of the path.</span></span>

<span data-ttu-id="60d37-146">Для каждого пути счетчика используется следующий формат.</span><span class="sxs-lookup"><span data-stu-id="60d37-146">Each counter path has the following format.</span></span>
<span data-ttu-id="60d37-147">В пути требуется значение ComputerName.</span><span class="sxs-lookup"><span data-stu-id="60d37-147">The ComputerName value is required in the path.</span></span>
<span data-ttu-id="60d37-148">например</span><span class="sxs-lookup"><span data-stu-id="60d37-148">For instance:</span></span>

- `\\<ComputerName>\<CounterSet>(<Instance>)\<CounterName>`

<span data-ttu-id="60d37-149">Пример:</span><span class="sxs-lookup"><span data-stu-id="60d37-149">For example:</span></span>

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

### <span data-ttu-id="60d37-150">-EndTime</span><span class="sxs-lookup"><span data-stu-id="60d37-150">-EndTime</span></span>

<span data-ttu-id="60d37-151">Задает конечную дату и время, когда этот командлет импортирует данные счетчика между значениями времени *начала* и этого параметра.</span><span class="sxs-lookup"><span data-stu-id="60d37-151">Specifies an end date and time that this cmdlet imports counter data between the *StartTime* and this parameter timestamps.</span></span>
<span data-ttu-id="60d37-152">Введите объект **DateTime** , например созданный командлетом Get-Date.</span><span class="sxs-lookup"><span data-stu-id="60d37-152">Enter a **DateTime** object, such as one created by the Get-Date cmdlet.</span></span>
<span data-ttu-id="60d37-153">По умолчанию командлет **Import-Counter** импортирует все данные счетчиков в файлах, указанных параметром *path* .</span><span class="sxs-lookup"><span data-stu-id="60d37-153">By default, **Import-Counter** imports all counter data in the files specified by the *Path* parameter.</span></span>

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

### <span data-ttu-id="60d37-154">— Список</span><span class="sxs-lookup"><span data-stu-id="60d37-154">-ListSet</span></span>

<span data-ttu-id="60d37-155">Задает наборы счетчиков производительности, которые представлены в экспортированных файлах.</span><span class="sxs-lookup"><span data-stu-id="60d37-155">Specifies the performance counter sets that are represented in the exported files.</span></span>
<span data-ttu-id="60d37-156">Команды с этим параметром не импортируют какие-либо данные.</span><span class="sxs-lookup"><span data-stu-id="60d37-156">Commands with this parameter do not import any data.</span></span>

<span data-ttu-id="60d37-157">Введите одно или несколько имен наборов счетчиков.</span><span class="sxs-lookup"><span data-stu-id="60d37-157">Enter one or more counter set names.</span></span>
<span data-ttu-id="60d37-158">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="60d37-158">Wildcards are permitted.</span></span>
<span data-ttu-id="60d37-159">Чтобы получить все наборы счетчиков в файле, введите `Import-Counter -ListSet *` .</span><span class="sxs-lookup"><span data-stu-id="60d37-159">To get all counter sets in the file, type `Import-Counter -ListSet *`.</span></span>

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

### <span data-ttu-id="60d37-160">-Макссамплес</span><span class="sxs-lookup"><span data-stu-id="60d37-160">-MaxSamples</span></span>

<span data-ttu-id="60d37-161">Указывает максимальное число выборок каждого счетчика, которые необходимо импортировать.</span><span class="sxs-lookup"><span data-stu-id="60d37-161">Specifies the maximum number of samples of each counter to import.</span></span>
<span data-ttu-id="60d37-162">По умолчанию командлет **Get-Counter** импортирует все данные в файлах, указанных параметром *path* .</span><span class="sxs-lookup"><span data-stu-id="60d37-162">By default, **Get-Counter** imports all of the data in the files specified by the *Path* parameter.</span></span>

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

### <span data-ttu-id="60d37-163">-Path</span><span class="sxs-lookup"><span data-stu-id="60d37-163">-Path</span></span>

<span data-ttu-id="60d37-164">Указывает путей к файлам для импорта.</span><span class="sxs-lookup"><span data-stu-id="60d37-164">Specifies the file paths of the files to be imported.</span></span>
<span data-ttu-id="60d37-165">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="60d37-165">This parameter is required.</span></span>

<span data-ttu-id="60d37-166">Введите путь и имя файла, CSV,,. tsv или. BLG, экспортированного с помощью командлета **Export-Counter** .</span><span class="sxs-lookup"><span data-stu-id="60d37-166">Enter the path and file name of a, .csv,, .tsv, or .blg file that you exported by using the **Export-Counter** cmdlet.</span></span>
<span data-ttu-id="60d37-167">Можно указать только один CSV- или TSV-файл, но в каждой команде можно задать до 32 BLG-файлов.</span><span class="sxs-lookup"><span data-stu-id="60d37-167">You can specify only one .csv or .tsv file, but you can specify multiple .blg files (up to 32) in each command.</span></span>
<span data-ttu-id="60d37-168">Можно также передать строки пути к файлам (в кавычках) в командлет **Import-Counter**.</span><span class="sxs-lookup"><span data-stu-id="60d37-168">You can also pipe file path strings (in quotation marks) to **Import-Counter**.</span></span>

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

### <span data-ttu-id="60d37-169">-StartTime</span><span class="sxs-lookup"><span data-stu-id="60d37-169">-StartTime</span></span>

<span data-ttu-id="60d37-170">Указывает начальную дату и время, в которые этот командлет получает данные счетчика.</span><span class="sxs-lookup"><span data-stu-id="60d37-170">Specifies the start date and time in which this cmdlet gets counter data.</span></span>
<span data-ttu-id="60d37-171">Введите объект **DateTime** , например созданный командлетом **Get-Date** .</span><span class="sxs-lookup"><span data-stu-id="60d37-171">Enter a **DateTime** object, such as one created by the **Get-Date** cmdlet.</span></span>
<span data-ttu-id="60d37-172">По умолчанию командлет **Import-Counter** импортирует все данные счетчиков в файлах, указанных параметром *path* .</span><span class="sxs-lookup"><span data-stu-id="60d37-172">By default, **Import-Counter** imports all counter data in the files specified by the *Path* parameter.</span></span>

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

### <span data-ttu-id="60d37-173">-Summary</span><span class="sxs-lookup"><span data-stu-id="60d37-173">-Summary</span></span>

<span data-ttu-id="60d37-174">Указывает, что этот командлет получает сводку импортированных данных вместо отдельных выборок данных счетчиков.</span><span class="sxs-lookup"><span data-stu-id="60d37-174">Indicates that this cmdlet gets a summary of the imported data, instead of getting individual counter data samples.</span></span>

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

### <span data-ttu-id="60d37-175">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="60d37-175">CommonParameters</span></span>

<span data-ttu-id="60d37-176">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="60d37-176">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="60d37-177">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="60d37-177">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="60d37-178">Входные данные</span><span class="sxs-lookup"><span data-stu-id="60d37-178">INPUTS</span></span>

### <span data-ttu-id="60d37-179">System.String</span><span class="sxs-lookup"><span data-stu-id="60d37-179">System.String</span></span>

<span data-ttu-id="60d37-180">К этому командлету можно передать пути журналов счетчиков производительности.</span><span class="sxs-lookup"><span data-stu-id="60d37-180">You can pipe performance counter log paths to this cmdlet.</span></span>

## <span data-ttu-id="60d37-181">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="60d37-181">OUTPUTS</span></span>

### <span data-ttu-id="60d37-182">Microsoft. PowerShell. Commands. NOCOUNT. PerformanceCounterSampleSet, Microsoft. PowerShell. Commands. NOCOUNT. Counters, Microsoft. PowerShell. Commands. NOCOUNT. Каунтерфилеинфо</span><span class="sxs-lookup"><span data-stu-id="60d37-182">Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet, Microsoft.PowerShell.Commands.GetCounter.CounterSet, Microsoft.PowerShell.Commands.GetCounter.CounterFileInfo</span></span>

<span data-ttu-id="60d37-183">Этот командлет возвращает объект **Microsoft. PowerShell. Commands. NOCOUNT. PerformanceCounterSampleSet**.</span><span class="sxs-lookup"><span data-stu-id="60d37-183">This cmdlet returns a **Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet**.</span></span>
<span data-ttu-id="60d37-184">Если используется параметр *List* , этот командлет возвращает объект **Microsoft. PowerShell. Commands. NOCOUNT. Counter** .</span><span class="sxs-lookup"><span data-stu-id="60d37-184">If you use the *ListSet* parameter, this cmdlet returns a **Microsoft.PowerShell.Commands.GetCounter.CounterSet** object.</span></span>
<span data-ttu-id="60d37-185">При использовании параметра *сводки* этот командлет возвращает объект **Microsoft. PowerShell. Commands. GetObject. каунтерфилеинфо** .</span><span class="sxs-lookup"><span data-stu-id="60d37-185">If you use the *Summary* parameter, this cmdlet returns a **Microsoft.PowerShell.Commands.GetCounter.CounterFileInfo** object.</span></span>

## <span data-ttu-id="60d37-186">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="60d37-186">NOTES</span></span>

* <span data-ttu-id="60d37-187">У этого командлета нет параметра *ComputerName* .</span><span class="sxs-lookup"><span data-stu-id="60d37-187">This cmdlet does not have a *ComputerName* parameter.</span></span> <span data-ttu-id="60d37-188">Однако если компьютер настроен для удаленного взаимодействия Windows PowerShell, можно использовать командлет Invoke-Command для выполнения команды **Import-Counter** на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="60d37-188">However, if the computer is configured for Windows PowerShell remoting, you can use the Invoke-Command cmdlet to run an **Import-Counter** command on a remote computer.</span></span>

## <span data-ttu-id="60d37-189">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="60d37-189">RELATED LINKS</span></span>

[<span data-ttu-id="60d37-190">Export-Counter</span><span class="sxs-lookup"><span data-stu-id="60d37-190">Export-Counter</span></span>](Export-Counter.md)

[<span data-ttu-id="60d37-191">Get-Counter</span><span class="sxs-lookup"><span data-stu-id="60d37-191">Get-Counter</span></span>](Get-Counter.md)
