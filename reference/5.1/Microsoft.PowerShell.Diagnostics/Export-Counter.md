---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 10/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/export-counter?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Counter
ms.openlocfilehash: 54498eb504a1d13a5b96a2583b5e5d6e4c08735e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231053"
---
# <span data-ttu-id="04cc3-103">Export-Counter</span><span class="sxs-lookup"><span data-stu-id="04cc3-103">Export-Counter</span></span>

## <span data-ttu-id="04cc3-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="04cc3-104">SYNOPSIS</span></span>
<span data-ttu-id="04cc3-105">Экспортирует данные счетчика производительности в файлы журнала.</span><span class="sxs-lookup"><span data-stu-id="04cc3-105">Exports performance counter data to log files.</span></span>

## <span data-ttu-id="04cc3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="04cc3-106">SYNTAX</span></span>

```
Export-Counter [-Path] <String> [-FileFormat <String>] [-MaxSize <UInt32>]
 -InputObject <PerformanceCounterSampleSet[]> [-Force] [-Circular] [<CommonParameters>]
```

## <span data-ttu-id="04cc3-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="04cc3-107">DESCRIPTION</span></span>

<span data-ttu-id="04cc3-108">`Export-Counter`Командлет экспортирует данные счетчика производительности (объекты PerformanceCounterSampleSet) в файлы журнала в двоичном файле журнала производительности (. blg), с разделителями-запятыми (CSV) или в формате с разделителями-символами табуляции (TSV).</span><span class="sxs-lookup"><span data-stu-id="04cc3-108">The `Export-Counter` cmdlet exports performance counter data (PerformanceCounterSampleSet objects) to log files in binary performance log (.blg), comma-separated value (.csv), or tab-separated value (.tsv) format.</span></span> <span data-ttu-id="04cc3-109">Этот командлет используется для записи данных счетчика производительности.</span><span class="sxs-lookup"><span data-stu-id="04cc3-109">You use this cmdlet to log performance counter data.</span></span>

<span data-ttu-id="04cc3-110">`Export-Counter`Командлет предназначен для экспорта данных, возвращаемых `Get-Counter` `Import-Counter` командлетами и.</span><span class="sxs-lookup"><span data-stu-id="04cc3-110">The `Export-Counter` cmdlet is designed to export data that is returned by the `Get-Counter` and `Import-Counter` cmdlets.</span></span>

<span data-ttu-id="04cc3-111">Этот командлет выполняется только в Windows 7, Windows Server 2008 R2 и более поздних версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="04cc3-111">This cmdlet runs only on Windows 7, Windows Server 2008 R2, and later versions of Windows.</span></span>

## <span data-ttu-id="04cc3-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="04cc3-112">EXAMPLES</span></span>

### <span data-ttu-id="04cc3-113">Пример 1. экспорт данных счетчиков в файл</span><span class="sxs-lookup"><span data-stu-id="04cc3-113">EXAMPLE 1: Export counter data to a file</span></span>

<span data-ttu-id="04cc3-114">В этом примере данные счетчика экспортируются в BLG-файл.</span><span class="sxs-lookup"><span data-stu-id="04cc3-114">This example exports counter data to a BLG file.</span></span>

```powershell
Get-Counter "\Processor(*)\% Processor Time" | Export-Counter -Path $home\Counters.blg
```

<span data-ttu-id="04cc3-115">Команда использует `Get-Counter` командлет для получения данных о времени процессора.</span><span class="sxs-lookup"><span data-stu-id="04cc3-115">The command uses the `Get-Counter` cmdlet to collect processor time data.</span></span> <span data-ttu-id="04cc3-116">Для отправки данных в командлет используется оператор конвейера (|) `Export-Counter` .</span><span class="sxs-lookup"><span data-stu-id="04cc3-116">It uses a pipeline operator (|) to send the data to the `Export-Counter` cmdlet.</span></span> <span data-ttu-id="04cc3-117">`Export-Counter`Команда использует переменную **path** для указания выходного файла.</span><span class="sxs-lookup"><span data-stu-id="04cc3-117">The `Export-Counter` command uses the **Path** variable to specify the output file.</span></span>

<span data-ttu-id="04cc3-118">Так как набор данных может быть очень большим, в этом примере данные отправляются `Export-Counter` через конвейер.</span><span class="sxs-lookup"><span data-stu-id="04cc3-118">Because the data set might be very large, this example sends the data to `Export-Counter` through the pipeline.</span></span> <span data-ttu-id="04cc3-119">Если данные были сохранены в переменной, то можно использовать непропорциональное количество памяти.</span><span class="sxs-lookup"><span data-stu-id="04cc3-119">If the data were saved in a variable, you might use a disproportionate amount of memory.</span></span>

### <span data-ttu-id="04cc3-120">Пример 2. Экспорт файла в формат файла счетчика</span><span class="sxs-lookup"><span data-stu-id="04cc3-120">Example 2: Export a file to a counter file format</span></span>

<span data-ttu-id="04cc3-121">В этом примере CSV-файл преобразуется в формат BLG данных счетчика.</span><span class="sxs-lookup"><span data-stu-id="04cc3-121">This example converts a CSV file to a counter data BLG format.</span></span>

<span data-ttu-id="04cc3-122">`Import-Counter`Командлет импортирует данные счетчика производительности из `Threads.csv` файла.</span><span class="sxs-lookup"><span data-stu-id="04cc3-122">The `Import-Counter` cmdlet imports performance counter data from the `Threads.csv` file.</span></span> <span data-ttu-id="04cc3-123">В примере предполагается, что этот файл был ранее экспортирован с помощью `Export-Counter` командлета.</span><span class="sxs-lookup"><span data-stu-id="04cc3-123">The example presumes that this file was previously exported by using the `Export-Counter` cmdlet.</span></span> <span data-ttu-id="04cc3-124">Оператор конвейера ( `|` ) отправляет импортированные данные в `Export-Counter` командлет.</span><span class="sxs-lookup"><span data-stu-id="04cc3-124">A pipeline operator (`|`) sends the imported data to the `Export-Counter` cmdlet.</span></span> <span data-ttu-id="04cc3-125">Команда использует параметр **Path** , чтобы указать расположение выходного файла.</span><span class="sxs-lookup"><span data-stu-id="04cc3-125">The command uses the **Path** parameter to specify the location of the output file.</span></span> <span data-ttu-id="04cc3-126">Он использует параметры **циклического** и **MAXSIZE** , чтобы направить `Export-Counter` командлету создание циклического журнала, который включает в себя 1 ГБ.</span><span class="sxs-lookup"><span data-stu-id="04cc3-126">It uses the **Circular** and **MaxSize** parameters to direct the `Export-Counter` cmdlet to create a circular log that wraps at 1 GB.</span></span> <span data-ttu-id="04cc3-127">Параметр **MAXSIZE** выражается в мегабайтах.</span><span class="sxs-lookup"><span data-stu-id="04cc3-127">The **MaxSize** parameter is expressed in megabytes.</span></span>

```powershell
$1GBInMB = 1024 # 1GB = 1024MB
Import-Counter Threads.csv | Export-Counter -Path ThreadTest.blg -Circular -MaxSize $1GBInMB
```

### <span data-ttu-id="04cc3-128">Пример 3. получение данных счетчика с удаленного компьютера и сохранение данных в файле</span><span class="sxs-lookup"><span data-stu-id="04cc3-128">Example 3: Get counter data from a remote computer and save the data to a file</span></span>

<span data-ttu-id="04cc3-129">В этом примере показано, как получить данные счетчиков производительности с удаленного компьютера и сохранить данные в файл на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="04cc3-129">This example shows how to get performance counter data from a remote computer and save the data in a file on the remote computer.</span></span>

<span data-ttu-id="04cc3-130">Первая команда использует `Get-Counter` командлет для получения данных счетчика рабочего набора из Server01, удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="04cc3-130">The first command uses the `Get-Counter` cmdlet to collect working set counter data from Server01, a remote computer.</span></span> <span data-ttu-id="04cc3-131">Команда сохраняет данные в `$C` переменной.</span><span class="sxs-lookup"><span data-stu-id="04cc3-131">The command saves the data in the `$C` variable.</span></span>

<span data-ttu-id="04cc3-132">Вторая команда использует оператор конвейера ( `|` ) для отправки данных в `$C` `Export-Counter` командлет, который сохраняет его в `Workingset.blg` файле в общей папке производительности на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="04cc3-132">The second command uses a pipeline operator (`|`) to send the data in `$C` to the `Export-Counter` cmdlet, which saves it in the `Workingset.blg` file in the Perf share of the Server01 computer.</span></span>

```powershell
$C = Get-Counter -ComputerName Server01 -Counter "\Process(*)\Working Set - Private" -MaxSamples $C | Export-Counter -Path \\Server01\Perf\WorkingSet.blg
```

```Output
20
```

### <span data-ttu-id="04cc3-133">Пример 4. повторное ведение журнала существующих данных</span><span class="sxs-lookup"><span data-stu-id="04cc3-133">Example 4: Re-log existing data</span></span>

<span data-ttu-id="04cc3-134">В этом примере показано, как использовать `Import-Counter` `Export-Counter` командлеты и для повторного ведения журнала существующих данных.</span><span class="sxs-lookup"><span data-stu-id="04cc3-134">This example shows how to use the `Import-Counter` and `Export-Counter` cmdlets to re-log existing data.</span></span>

<span data-ttu-id="04cc3-135">Первая команда использует `Import-Counter` командлет для импорта данных счетчиков производительности из журнала места. blg.</span><span class="sxs-lookup"><span data-stu-id="04cc3-135">The first command uses the `Import-Counter` cmdlet to import performance counter data from the DiskSpace.blg log.</span></span> <span data-ttu-id="04cc3-136">Данные сохраняются в `$All` переменной.</span><span class="sxs-lookup"><span data-stu-id="04cc3-136">It saves the data in the `$All` variable.</span></span> <span data-ttu-id="04cc3-137">Этот файл содержит примеры \% счетчика "свободное место на диске" на более чем 200 удаленных компьютерах в Организации.</span><span class="sxs-lookup"><span data-stu-id="04cc3-137">This file contains samples of the "LogicalDisk\% Free Space" counter on more than 200 remote computers in the enterprise.</span></span>

<span data-ttu-id="04cc3-138">Вторая команда использует `Where-Object` командлет для выбора объектов с **кукедвалуе** менее 15 (процентов).</span><span class="sxs-lookup"><span data-stu-id="04cc3-138">The second command uses the `Where-Object` cmdlet to select objects with **CookedValue** of less than 15 (percent).</span></span> <span data-ttu-id="04cc3-139">Команда сохраняет результаты в `$LowSpace` переменной.</span><span class="sxs-lookup"><span data-stu-id="04cc3-139">The command saves the results in the `$LowSpace` variable.</span></span>

<span data-ttu-id="04cc3-140">Третья команда использует конвейерный оператор ( `|` ) для отправки данных `$LowSpace` переменной в `Export-Counter` командлет.</span><span class="sxs-lookup"><span data-stu-id="04cc3-140">The third command uses a pipeline operator (`|`) to send the data in the `$LowSpace` variable to the `Export-Counter` cmdlet.</span></span> <span data-ttu-id="04cc3-141">Команда использует параметр **Path** , чтобы указать, что выбранные данные следует зарегистрировать в файле LowDiskSpace.blg.</span><span class="sxs-lookup"><span data-stu-id="04cc3-141">The command uses the **Path** parameter to indicate that the selected data should be logged in the LowDiskSpace.blg file.</span></span>

```powershell
$All = Import-Counter DiskSpace.blg
$LowSpace = $All | Where-Object {$_.CounterSamples.CookedValue -lt 15}
$LowSpace | Export-Counter -Path LowDiskSpace.blg
```

## <span data-ttu-id="04cc3-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="04cc3-142">PARAMETERS</span></span>

### <span data-ttu-id="04cc3-143">-Циклический</span><span class="sxs-lookup"><span data-stu-id="04cc3-143">-Circular</span></span>

<span data-ttu-id="04cc3-144">Указывает, что выходной файл является циклическим журналом с первым в, первым выходом (FIFO).</span><span class="sxs-lookup"><span data-stu-id="04cc3-144">Indicates that the output file is a circular log with first in, first out (FIFO) format.</span></span>
<span data-ttu-id="04cc3-145">Если вы включаете этот параметр, необходимо указать параметр **MaxSize**.</span><span class="sxs-lookup"><span data-stu-id="04cc3-145">When you include this parameter, the **MaxSize** parameter is required.</span></span>

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

### <span data-ttu-id="04cc3-146">-FileFormat</span><span class="sxs-lookup"><span data-stu-id="04cc3-146">-FileFormat</span></span>

<span data-ttu-id="04cc3-147">Задает выходной формат выходного файла журнала.</span><span class="sxs-lookup"><span data-stu-id="04cc3-147">Specifies the output format of the output log file.</span></span>

<span data-ttu-id="04cc3-148">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="04cc3-148">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="04cc3-149">CSV</span><span class="sxs-lookup"><span data-stu-id="04cc3-149">CSV</span></span>
- <span data-ttu-id="04cc3-150">TSV</span><span class="sxs-lookup"><span data-stu-id="04cc3-150">TSV</span></span>
- <span data-ttu-id="04cc3-151">BLG</span><span class="sxs-lookup"><span data-stu-id="04cc3-151">BLG</span></span>

<span data-ttu-id="04cc3-152">Значение по умолчанию: BLG.</span><span class="sxs-lookup"><span data-stu-id="04cc3-152">The default value is BLG.</span></span>

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

### <span data-ttu-id="04cc3-153">-Force</span><span class="sxs-lookup"><span data-stu-id="04cc3-153">-Force</span></span>

<span data-ttu-id="04cc3-154">Перезаписывает и заменяет существующий файл, если он существует в расположении, указанном параметром **path** .</span><span class="sxs-lookup"><span data-stu-id="04cc3-154">Overwrites and replaces an existing file if one exists in the location specified by the **Path** parameter.</span></span>

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

### <span data-ttu-id="04cc3-155">-InputObject</span><span class="sxs-lookup"><span data-stu-id="04cc3-155">-InputObject</span></span>

<span data-ttu-id="04cc3-156">Указывает в виде массива данные счетчика для экспорта.</span><span class="sxs-lookup"><span data-stu-id="04cc3-156">Specifies, as an array, the counter data to export.</span></span> <span data-ttu-id="04cc3-157">Введите переменную, которая содержит данные, или команду, которая получает данные, например `Get-Counter` `Import-Counter` командлет или.</span><span class="sxs-lookup"><span data-stu-id="04cc3-157">Enter a variable that contains the data or a command that gets the data, such as the `Get-Counter` or `Import-Counter` cmdlet.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="04cc3-158">-MaxSize</span><span class="sxs-lookup"><span data-stu-id="04cc3-158">-MaxSize</span></span>

<span data-ttu-id="04cc3-159">Указывает максимальный размер выходного файла в мегабайтах (МБ).</span><span class="sxs-lookup"><span data-stu-id="04cc3-159">Specifies the maximum size of the output file in megabytes (MB).</span></span>

<span data-ttu-id="04cc3-160">Если указан **циклический** параметр, то при достижении указанного максимального размера файла журнала самые старые записи удаляются по мере добавления новых.</span><span class="sxs-lookup"><span data-stu-id="04cc3-160">If the **Circular** parameter is specified, then when the log file reaches the specified maximum size, the oldest entries are deleted as newer ones are added.</span></span> <span data-ttu-id="04cc3-161">Если **циклический** параметр не указан, то при достижении файлом журнала указанного максимального размера новые данные не добавляются и командлет создает неустранимую ошибку.</span><span class="sxs-lookup"><span data-stu-id="04cc3-161">If the **Circular** parameter is not specified, then when the log file reaches the specified maximum size, no new data is added and the cmdlet generates a non-terminating error.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="04cc3-162">-Path</span><span class="sxs-lookup"><span data-stu-id="04cc3-162">-Path</span></span>

<span data-ttu-id="04cc3-163">Задает путь и имя выходного файла.</span><span class="sxs-lookup"><span data-stu-id="04cc3-163">Specifies the path and file name of the output file.</span></span> <span data-ttu-id="04cc3-164">Введите относительный или абсолютный путь на локальном компьютере или UNC-путь к удаленному компьютеру, например `\\Computer\Share\file.blg` .</span><span class="sxs-lookup"><span data-stu-id="04cc3-164">Enter a relative or absolute path on the local computer, or a Uniform Naming Convention (UNC) path to a remote computer, such as `\\Computer\Share\file.blg`.</span></span> <span data-ttu-id="04cc3-165">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="04cc3-165">This parameter is required.</span></span>

<span data-ttu-id="04cc3-166">Формат файла определяется значением параметра **FileFormat** , а не расширением имени файла в пути.</span><span class="sxs-lookup"><span data-stu-id="04cc3-166">The file format is determined by the value of the **FileFormat** parameter, not by the file name extension in the path.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="04cc3-167">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="04cc3-167">CommonParameters</span></span>

<span data-ttu-id="04cc3-168">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="04cc3-168">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="04cc3-169">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="04cc3-169">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="04cc3-170">Входные данные</span><span class="sxs-lookup"><span data-stu-id="04cc3-170">INPUTS</span></span>

### <span data-ttu-id="04cc3-171">Microsoft. PowerShell. Commands. NOCOUNT. PerformanceCounterSampleSet</span><span class="sxs-lookup"><span data-stu-id="04cc3-171">Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet</span></span>

<span data-ttu-id="04cc3-172">Данные счетчика производительности можно передать в `Get-Counter` Этот командлет по конвейеру `Import-Counter` .</span><span class="sxs-lookup"><span data-stu-id="04cc3-172">You can pipe performance counter data from `Get-Counter` or `Import-Counter` to this cmdlet.</span></span>

## <span data-ttu-id="04cc3-173">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="04cc3-173">OUTPUTS</span></span>

### <span data-ttu-id="04cc3-174">Нет</span><span class="sxs-lookup"><span data-stu-id="04cc3-174">None</span></span>

## <span data-ttu-id="04cc3-175">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="04cc3-175">NOTES</span></span>

<span data-ttu-id="04cc3-176">Генератор файлов журнала ожидает, что все входные объекты имеют один и тот же путь счетчика и объекты располагаются в порядке возрастания по времени.</span><span class="sxs-lookup"><span data-stu-id="04cc3-176">The log file generator expects that all input objects have the same counter path and that the objects are arranged in ascending time order.</span></span>

<span data-ttu-id="04cc3-177">Тип счетчика и путь первого входного объекта определяет свойства, записываемые в файл журнала.</span><span class="sxs-lookup"><span data-stu-id="04cc3-177">The counter type and path of the first input object determines the properties recorded in the log file.</span></span> <span data-ttu-id="04cc3-178">Если другие входные объекты не имеют значений для записанного свойства, поле свойства будет пустым.</span><span class="sxs-lookup"><span data-stu-id="04cc3-178">If other input objects do not have a value for a recorded property, the property field is empty.</span></span> <span data-ttu-id="04cc3-179">Если объекты имеют значения свойств, которые не были записаны, дополнительные значения свойств игнорируются.</span><span class="sxs-lookup"><span data-stu-id="04cc3-179">If the objects have property values that were not recorded, the extra property values are ignored.</span></span>

<span data-ttu-id="04cc3-180">Возможно, системный монитор не сможет считывать все журналы, создаваемые `Export-Counter` .</span><span class="sxs-lookup"><span data-stu-id="04cc3-180">Performance Monitor might not be able to read all logs that `Export-Counter` generates.</span></span> <span data-ttu-id="04cc3-181">Например, системный монитор требует, чтобы все объекты имели одинаковый путь, а все объекты были разделены одним и тем же интервалом времени.</span><span class="sxs-lookup"><span data-stu-id="04cc3-181">For instance, Performance Monitor requires that all objects have the same path and that all objects are separated by the same time interval.</span></span>

<span data-ttu-id="04cc3-182">`Import-Counter`Командлет не имеет параметра **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="04cc3-182">The `Import-Counter` cmdlet does not have a **ComputerName** parameter.</span></span> <span data-ttu-id="04cc3-183">Однако если компьютер настроен для удаленной оболочки Windows PowerShell Windows PowerShell, можно использовать `Invoke-Command` командлет для выполнения `Import-Counter` команды на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="04cc3-183">However, if the computer is configured for remote Windows PowerShell Windows PowerShell, you can use the `Invoke-Command` cmdlet to run an `Import-Counter` command on a remote computer.</span></span>

## <span data-ttu-id="04cc3-184">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="04cc3-184">RELATED LINKS</span></span>

[<span data-ttu-id="04cc3-185">Get-Counter</span><span class="sxs-lookup"><span data-stu-id="04cc3-185">Get-Counter</span></span>](Get-Counter.md)

[<span data-ttu-id="04cc3-186">Import-Counter</span><span class="sxs-lookup"><span data-stu-id="04cc3-186">Import-Counter</span></span>](Import-Counter.md)
