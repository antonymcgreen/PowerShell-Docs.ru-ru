---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 11/06/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/get-counter?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Counter
ms.openlocfilehash: b7eafd52393a1e7e80a12e5bc982965b0af12fd5
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226249"
---
# <span data-ttu-id="6030f-103">Get-Counter</span><span class="sxs-lookup"><span data-stu-id="6030f-103">Get-Counter</span></span>

## <span data-ttu-id="6030f-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="6030f-104">SYNOPSIS</span></span>
<span data-ttu-id="6030f-105">Получает данные счетчиков производительности с локальных и удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="6030f-105">Gets performance counter data from local and remote computers.</span></span>

## <span data-ttu-id="6030f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6030f-106">SYNTAX</span></span>

### <span data-ttu-id="6030f-107">CounterSet (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="6030f-107">GetCounterSet (Default)</span></span>

```
Get-Counter [[-Counter] <String[]>] [-SampleInterval <Int32>] [-MaxSamples <Int64>] [-Continuous]
 [-ComputerName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="6030f-108">листсетсет</span><span class="sxs-lookup"><span data-stu-id="6030f-108">ListSetSet</span></span>

```
Get-Counter [-ListSet] <String[]> [-ComputerName <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="6030f-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6030f-109">DESCRIPTION</span></span>

<span data-ttu-id="6030f-110">`Get-Counter`Командлет получает данные счетчика производительности непосредственно из инструментария наблюдения за производительностью в семействе операционных систем Windows.</span><span class="sxs-lookup"><span data-stu-id="6030f-110">The `Get-Counter` cmdlet gets performance counter data directly from the performance monitoring instrumentation in the Windows family of operating systems.</span></span> <span data-ttu-id="6030f-111">`Get-Counter` Возвращает данные о производительности с локального компьютера или удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="6030f-111">`Get-Counter` gets performance data from a local computer or remote computers.</span></span>

<span data-ttu-id="6030f-112">С помощью параметров можно `Get-Counter` указать один или несколько компьютеров, список наборов счетчиков производительности и содержащихся в них экземпляров, задать интервалы выборки и указать максимальное число выборок.</span><span class="sxs-lookup"><span data-stu-id="6030f-112">You can use the `Get-Counter` parameters to specify one or more computers, list the performance counter sets and the instances they contain, set the sample intervals, and specify the maximum number of samples.</span></span> <span data-ttu-id="6030f-113">Без параметров `Get-Counter` получает данные счетчика производительности для набора системных счетчиков.</span><span class="sxs-lookup"><span data-stu-id="6030f-113">Without parameters, `Get-Counter` gets performance counter data for a set of system counters.</span></span>

<span data-ttu-id="6030f-114">Многие наборы счетчиков защищены списками управления доступом (ACL).</span><span class="sxs-lookup"><span data-stu-id="6030f-114">Many counter sets are protected by access control lists (ACL).</span></span> <span data-ttu-id="6030f-115">Чтобы просмотреть все наборы счетчиков, откройте PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="6030f-115">To see all counter sets, open PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="6030f-116">Этот командлет был повторно введен в PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="6030f-116">This cmdlet was reintroduced in PowerShell 7.</span></span>

## <span data-ttu-id="6030f-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="6030f-117">EXAMPLES</span></span>

### <span data-ttu-id="6030f-118">Пример 1. Получение списка наборов счетчиков</span><span class="sxs-lookup"><span data-stu-id="6030f-118">Example 1: Get the counter set list</span></span>

<span data-ttu-id="6030f-119">В этом примере получается список наборов счетчиков локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="6030f-119">This example gets the local computer's list of counter sets.</span></span>

```powershell
Get-Counter -ListSet *
```

```Output
CounterSetName     : Processor
MachineName        : .
CounterSetType     : MultiInstance
Description        : The Processor performance object consists of counters that measure aspects ...
                     computer that performs arithmetic and logical computations, initiates ...
                     computer can have multiple processors.  The processor object represents ...
Paths              : {\Processor(*)\% Processor Time, \Processor(*)\% User Time, ...
PathsWithInstances : {\Processor(0)\% Processor Time, \Processor(1)\% Processor Time, ...
Counter            : {\Processor(*)\% Processor Time, \Processor(*)\% User Time, ...
```

<span data-ttu-id="6030f-120">`Get-Counter` использует параметр **List** со звездочкой ( `*` ) для получения списка наборов счетчиков.</span><span class="sxs-lookup"><span data-stu-id="6030f-120">`Get-Counter` uses the **ListSet** parameter with an asterisk (`*`) to get the list of counter sets.</span></span>
<span data-ttu-id="6030f-121">Точка ( `.` ) в столбце **MachineName** представляет локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="6030f-121">The dot (`.`) in the **MachineName** column represents the local computer.</span></span>

### <span data-ttu-id="6030f-122">Пример 2. Указание SampleInterval и Макссамплес</span><span class="sxs-lookup"><span data-stu-id="6030f-122">Example 2: Specify the SampleInterval and MaxSamples</span></span>

<span data-ttu-id="6030f-123">Этот пример возвращает данные счетчика для всех процессоров на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="6030f-123">This examples gets the counter data for all processors on the local computer.</span></span> <span data-ttu-id="6030f-124">Данные собираются с интервалом в две секунды, пока не будут представлены три примера.</span><span class="sxs-lookup"><span data-stu-id="6030f-124">Data is collected at two-second intervals until there are three samples.</span></span>

```powershell
Get-Counter -Counter "\Processor(_Total)\% Processor Time" -SampleInterval 2 -MaxSamples 3
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/18/2019 14:39:56        \\Computer01\processor(_total)\% processor time :
                          20.7144271584086

6/18/2019 14:39:58        \\Computer01\processor(_total)\% processor time :
                          10.4391790575511

6/18/2019 14:40:01        \\Computer01\processor(_total)\% processor time :
                          37.5968799396998
```

<span data-ttu-id="6030f-125">`Get-Counter` использует параметр **Counter** для указания пути счетчика `\Processor(_Total)\% Processor Time` .</span><span class="sxs-lookup"><span data-stu-id="6030f-125">`Get-Counter` uses the **Counter** parameter to specify the counter path `\Processor(_Total)\% Processor Time`.</span></span> <span data-ttu-id="6030f-126">Параметр **SampleInterval** задает интервал в два секунды для проверки счетчика.</span><span class="sxs-lookup"><span data-stu-id="6030f-126">The **SampleInterval** parameter sets a two-second interval to check the counter.</span></span> <span data-ttu-id="6030f-127">**Макссамплес** определяет, что три — это максимальное число раз для проверки счетчика.</span><span class="sxs-lookup"><span data-stu-id="6030f-127">**MaxSamples** determines that three is the maximum number of times to check the counter.</span></span>

### <span data-ttu-id="6030f-128">Пример 3. получение непрерывных выборок счетчика</span><span class="sxs-lookup"><span data-stu-id="6030f-128">Example 3: Get continuous samples of a counter</span></span>

<span data-ttu-id="6030f-129">Этот пример получает непрерывные выборки для счетчика каждую секунду.</span><span class="sxs-lookup"><span data-stu-id="6030f-129">This examples gets continuous samples for a counter every second.</span></span> <span data-ttu-id="6030f-130">Чтобы прерывать выполнение команды, нажмите клавиши <kbd>CTRL</kbd> + <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="6030f-130">To stop the command, press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span> <span data-ttu-id="6030f-131">Чтобы указать более длинный интервал между выборками, используйте параметр **SampleInterval** .</span><span class="sxs-lookup"><span data-stu-id="6030f-131">To specify a longer interval between samples, use the **SampleInterval** parameter.</span></span>

```powershell
Get-Counter -Counter "\Processor(_Total)\% Processor Time" -Continuous
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/19/2019 15:35:03        \\Computer01\processor(_total)\% processor time :
                          43.8522842937022

6/19/2019 15:35:04        \\Computer01\processor(_total)\% processor time :
                          29.7896844697383

6/19/2019 15:35:05        \\Computer01\processor(_total)\% processor time :
                          29.4962645638135

6/19/2019 15:35:06        \\Computer01\processor(_total)\% processor time :
                          25.5901500127408
```

<span data-ttu-id="6030f-132">`Get-Counter` использует параметр **Counter** для указания `\Processor\% Processor Time` счетчика.</span><span class="sxs-lookup"><span data-stu-id="6030f-132">`Get-Counter` uses the **Counter** parameter to specify the `\Processor\% Processor Time` counter.</span></span>
<span data-ttu-id="6030f-133">Параметр **непрерывно** задает получение образцов каждую секунду до тех пор, пока команда не будет остановлена с помощью <kbd>клавиши CTRL</kbd> + <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="6030f-133">The **Continuous** parameter specifies to get samples every second until the command is stopped with <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span>

### <span data-ttu-id="6030f-134">Пример 4. Алфавитный список наборов счетчиков</span><span class="sxs-lookup"><span data-stu-id="6030f-134">Example 4: Alphabetical list of counter sets</span></span>

<span data-ttu-id="6030f-135">В этом примере используется конвейер для получения набора списка счетчиков, а затем сортировка списка в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="6030f-135">This example uses the pipeline to get the counter list set and then sort the list in alphabetical order.</span></span>

```powershell
Get-Counter -ListSet * |
  Sort-Object -Property CounterSetName |
    Format-Table CounterSetName, CounterSetType -AutoSize
```

```Output
CounterSetName                        CounterSetType
--------------                        --------------
.NET CLR Data                         SingleInstance
.NET Data Provider for SqlServer      SingleInstance
AppV Client Streamed Data Percentage  SingleInstance
Authorization Manager Applications    SingleInstance
BitLocker                             MultiInstance
Bluetooth Device                      SingleInstance
Cache                                 SingleInstance
Client Side Caching                   SingleInstance
```

<span data-ttu-id="6030f-136">`Get-Counter` использует параметр **List** со звездочкой ( `*` ) для получения полного списка наборов счетчиков.</span><span class="sxs-lookup"><span data-stu-id="6030f-136">`Get-Counter` uses the **ListSet** parameter with an asterisk (`*`) to get a complete list of counter sets.</span></span> <span data-ttu-id="6030f-137">Объекты **CounterSet** отправляются по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="6030f-137">The **CounterSet** objects are sent down the pipeline.</span></span> <span data-ttu-id="6030f-138">`Sort-Object` использует параметр **Property** , чтобы указать, что объекты сортируются по **CounterSetName**.</span><span class="sxs-lookup"><span data-stu-id="6030f-138">`Sort-Object` uses the **Property** parameter to specify that the objects are sorted by **CounterSetName**.</span></span> <span data-ttu-id="6030f-139">Объекты отправляются по конвейеру в `Format-Table` .</span><span class="sxs-lookup"><span data-stu-id="6030f-139">The objects are sent down the pipeline to `Format-Table`.</span></span> <span data-ttu-id="6030f-140">Параметр **AutoSize** корректирует ширину столбцов для сокращения усечения.</span><span class="sxs-lookup"><span data-stu-id="6030f-140">The **AutoSize** parameter adjusts the column widths to minimize truncation.</span></span>

<span data-ttu-id="6030f-141">Точка ( `.` ) в столбце **MachineName** представляет локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="6030f-141">The dot (`.`) in the **MachineName** column represents the local computer.</span></span>

### <span data-ttu-id="6030f-142">Пример 5. Запуск фонового задания для получения данных счетчика</span><span class="sxs-lookup"><span data-stu-id="6030f-142">Example 5: Run a background job to get counter data</span></span>

<span data-ttu-id="6030f-143">В этом примере `Start-Job` выполняет команду в `Get-Counter` качестве фонового задания на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="6030f-143">In this example, `Start-Job` runs a `Get-Counter` command as a background job on the local computer.</span></span>
<span data-ttu-id="6030f-144">Чтобы просмотреть выходные данные счетчика производительности задания, используйте `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="6030f-144">To view the performance counter output from the job, use the `Receive-Job` cmdlet.</span></span>

```powershell
Start-Job -ScriptBlock {Get-Counter -Counter "\LogicalDisk(_Total)\% Free Space" -MaxSamples 1000}
```

```Output
Id     Name  PSJobTypeName   State    HasMoreData  Location   Command
--     ----  -------------   -----    -----------  --------   -------
1      Job1  BackgroundJob   Running  True         localhost  Get-Counter -Counter
```

<span data-ttu-id="6030f-145">`Start-Job` использует параметр **ScriptBlock** для выполнения `Get-Counter` команды.</span><span class="sxs-lookup"><span data-stu-id="6030f-145">`Start-Job` uses the **ScriptBlock** parameter to run a `Get-Counter` command.</span></span> <span data-ttu-id="6030f-146">`Get-Counter` использует параметр **Counter** для указания пути счетчика `\LogicalDisk(_Total)\% Free Space` .</span><span class="sxs-lookup"><span data-stu-id="6030f-146">`Get-Counter` uses the **Counter** parameter to specify the counter path `\LogicalDisk(_Total)\% Free Space`.</span></span> <span data-ttu-id="6030f-147">Параметр **макссамплес** указывает, что получение образцов счетчика 1000.</span><span class="sxs-lookup"><span data-stu-id="6030f-147">The **MaxSamples** parameter specifies to get 1000 samples of the counter.</span></span>

### <span data-ttu-id="6030f-148">Пример 6. получение данных счетчиков с нескольких компьютеров</span><span class="sxs-lookup"><span data-stu-id="6030f-148">Example 6: Get counter data from multiple computers</span></span>

<span data-ttu-id="6030f-149">В этом примере используется переменная для получения данных счетчиков производительности с двух компьютеров.</span><span class="sxs-lookup"><span data-stu-id="6030f-149">This example uses a variable to get performance counter data from two computers.</span></span>

```powershell
$DiskReads = "\LogicalDisk(C:)\Disk Reads/sec"
$DiskReads | Get-Counter -ComputerName Server01, Server02 -MaxSamples 10
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/21/2019 10:51:04        \\Server01\logicaldisk(c:)\disk reads/sec :
                          0

                          \\Server02\logicaldisk(c:)\disk reads/sec :
                          0.983050344269146
```

<span data-ttu-id="6030f-150">`$DiskReads`Переменная хранит `\LogicalDisk(C:)\Disk Reads/sec` путь счетчика.</span><span class="sxs-lookup"><span data-stu-id="6030f-150">The `$DiskReads` variable stores the `\LogicalDisk(C:)\Disk Reads/sec` counter path.</span></span> <span data-ttu-id="6030f-151">`$DiskReads`Переменная отправляется по конвейеру в `Get-Counter` .</span><span class="sxs-lookup"><span data-stu-id="6030f-151">The `$DiskReads` variable is sent down the pipeline to `Get-Counter`.</span></span> <span data-ttu-id="6030f-152">Значение **Counter** является первым параметром позиционирования и принимает путь, хранящийся в `$DiskReads` .</span><span class="sxs-lookup"><span data-stu-id="6030f-152">**Counter** is the first position parameter and accepts the path stored in `$DiskReads`.</span></span> <span data-ttu-id="6030f-153">**ComputerName** указывает два компьютера и **макссамплес** указывает на получение 10 образцов с каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="6030f-153">**ComputerName** specifies the two computers and **MaxSamples** specifies to get 10 samples from each computer.</span></span>

### <span data-ttu-id="6030f-154">Пример 7. Получение значений экземпляра счетчика из нескольких случайных компьютеров</span><span class="sxs-lookup"><span data-stu-id="6030f-154">Example 7: Get a counter's instance values from multiple random computers</span></span>

<span data-ttu-id="6030f-155">В этом примере возвращается значение счетчика производительности на 50 случайных удаленных компьютеров в Организации.</span><span class="sxs-lookup"><span data-stu-id="6030f-155">This example gets the value of a performance counter on 50 random, remote computers in the enterprise.</span></span> <span data-ttu-id="6030f-156">Параметр **ComputerName** использует случайные имена компьютеров, хранящиеся в переменной.</span><span class="sxs-lookup"><span data-stu-id="6030f-156">The **ComputerName** parameter uses random computer names stored in a variable.</span></span> <span data-ttu-id="6030f-157">Чтобы обновить имена компьютеров в переменной, повторно создайте переменную.</span><span class="sxs-lookup"><span data-stu-id="6030f-157">To update the computer names in the variable, recreate the variable.</span></span>

<span data-ttu-id="6030f-158">Альтернативой для имен серверов в параметре **ComputerName** является использование текстового файла.</span><span class="sxs-lookup"><span data-stu-id="6030f-158">An alternative for the server names in the **ComputerName** parameter is to use a text file.</span></span> <span data-ttu-id="6030f-159">Пример:</span><span class="sxs-lookup"><span data-stu-id="6030f-159">For example:</span></span>

`-ComputerName (Get-Random (Get-Content -Path C:\Servers.txt) -Count 50)`

<span data-ttu-id="6030f-160">Путь к счетчику содержит звездочку ( `*` ) в имени экземпляра для получения данных для каждого из процессоров удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="6030f-160">The counter path includes an asterisk (`*`) in the instance name to get the data for each of the remote computer's processors.</span></span>

```powershell
$Servers = Get-Random (Get-Content -Path C:\Servers.txt) -Count 50
$Counter = "\Processor(*)\% Processor Time"
Get-Counter -Counter $Counter -ComputerName $Servers
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/20/2019 12:20:35        \\Server01\processor(0)\% processor time :
                          6.52610319637854

                          \\Server01\processor(1)\% processor time :
                          3.41030663625782

                          \\Server01\processor(2)\% processor time :
                          9.64189975649925

                          \\Server01\processor(3)\% processor time :
                          1.85240835619747

                          \\Server01\processor(_total)\% processor time :
                          5.35768447160776
```

<span data-ttu-id="6030f-161">`Get-Random`Командлет использует `Get-Content` для выбора 50 случайных имен компьютеров из `Servers.txt` файла.</span><span class="sxs-lookup"><span data-stu-id="6030f-161">The `Get-Random` cmdlet uses `Get-Content` to select 50 random computer names from the `Servers.txt` file.</span></span> <span data-ttu-id="6030f-162">Имена удаленных компьютеров хранятся в `$Servers` переменной.</span><span class="sxs-lookup"><span data-stu-id="6030f-162">The remote computer names are stored in the `$Servers` variable.</span></span> <span data-ttu-id="6030f-163">`\Processor(*)\% Processor Time`Путь к счетчику хранится в `$Counter` переменной.</span><span class="sxs-lookup"><span data-stu-id="6030f-163">The `\Processor(*)\% Processor Time` counter's path is stored in the `$Counter` variable.</span></span> <span data-ttu-id="6030f-164">`Get-Counter` использует параметр **Counter** для указания счетчиков в `$Counter` переменной.</span><span class="sxs-lookup"><span data-stu-id="6030f-164">`Get-Counter` uses the **Counter** parameter to specify the counters in the `$Counter` variable.</span></span> <span data-ttu-id="6030f-165">Параметр **ComputerName** задает имена компьютеров в `$Servers` переменной.</span><span class="sxs-lookup"><span data-stu-id="6030f-165">The **ComputerName** parameter specifies the computer names in the `$Servers` variable.</span></span>

### <span data-ttu-id="6030f-166">Пример 8. использование свойства Path для получения форматированных имен путей</span><span class="sxs-lookup"><span data-stu-id="6030f-166">Example 8: Use the Path property to get formatted path names</span></span>

<span data-ttu-id="6030f-167">В этом примере используется свойство **path** набора счетчиков, чтобы найти отформатированные имена путей для счетчиков производительности.</span><span class="sxs-lookup"><span data-stu-id="6030f-167">This example uses the **Path** property of a counter set to find the formatted path names for the performance counters.</span></span>

<span data-ttu-id="6030f-168">Конвейер используется с `Where-Object` командлетом для поиска подмножества имен путей.</span><span class="sxs-lookup"><span data-stu-id="6030f-168">The pipeline is used with the `Where-Object` cmdlet to find a subset of the path names.</span></span> <span data-ttu-id="6030f-169">Чтобы найти набор счетчиков полный список путей к счетчикам, удалите конвейер ( `|` ) и `Where-Object` команду.</span><span class="sxs-lookup"><span data-stu-id="6030f-169">To find a counter sets complete list of counter paths, remove the pipeline (`|`) and `Where-Object` command.</span></span>

<span data-ttu-id="6030f-170">`$_`— Это автоматическая переменная для текущего объекта в конвейере.</span><span class="sxs-lookup"><span data-stu-id="6030f-170">The `$_` is an automatic variable for the current object in the pipeline.</span></span>
<span data-ttu-id="6030f-171">Дополнительные сведения см. в разделе [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="6030f-171">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

```powershell
(Get-Counter -ListSet Memory).Paths | Where-Object { $_ -like "*Cache*" }
```

```Output
\Memory\Cache Faults/sec
\Memory\Cache Bytes
\Memory\Cache Bytes Peak
\Memory\System Cache Resident Bytes
\Memory\Standby Cache Reserve Bytes
\Memory\Standby Cache Normal Priority Bytes
\Memory\Standby Cache Core Bytes
\Memory\Long-Term Average Standby Cache Lifetime (s)
```

<span data-ttu-id="6030f-172">`Get-Counter` использует параметр **List** для указания набора счетчиков **памяти** .</span><span class="sxs-lookup"><span data-stu-id="6030f-172">`Get-Counter` uses the **ListSet** parameter to specify the **Memory** counter set.</span></span> <span data-ttu-id="6030f-173">Команда заключается в круглые скобки **, чтобы свойство** paths возвращало каждый путь в виде строки.</span><span class="sxs-lookup"><span data-stu-id="6030f-173">The command is enclosed in parentheses so that the **Paths** property returns each path as a string.</span></span> <span data-ttu-id="6030f-174">Объекты отправляются по конвейеру в `Where-Object` .</span><span class="sxs-lookup"><span data-stu-id="6030f-174">The objects are sent down the pipeline to `Where-Object`.</span></span> <span data-ttu-id="6030f-175">`Where-Object` использует переменную `$_` для обработки каждого объекта и использует `-like` оператор для поиска совпадений для строки `*Cache*` .</span><span class="sxs-lookup"><span data-stu-id="6030f-175">`Where-Object` uses the variable `$_` to process each object and uses the `-like` operator to find matches for the string `*Cache*`.</span></span> <span data-ttu-id="6030f-176">Звездочки () являются символами- `*` шаблонами для любых символов.</span><span class="sxs-lookup"><span data-stu-id="6030f-176">The asterisks (`*`) are wildcards for any characters.</span></span>

### <span data-ttu-id="6030f-177">Пример 9. использование свойства Пассвисинстанцес для получения форматированных имен путей</span><span class="sxs-lookup"><span data-stu-id="6030f-177">Example 9: Use the PathsWithInstances property to get formatted path names</span></span>

<span data-ttu-id="6030f-178">Этот пример возвращает отформатированные имена путей, которые включают экземпляры счетчиков производительности " **физический диск** ".</span><span class="sxs-lookup"><span data-stu-id="6030f-178">This example gets the formatted path names that include the instances for the **PhysicalDisk** performance counters.</span></span>

```powershell
(Get-Counter -ListSet PhysicalDisk).PathsWithInstances
```

```Output
\PhysicalDisk(0 C:)\Current Disk Queue Length
\PhysicalDisk(_Total)\Current Disk Queue Length
\PhysicalDisk(0 C:)\% Disk Time
\PhysicalDisk(_Total)\% Disk Time
\PhysicalDisk(0 C:)\Avg. Disk Queue Length
\PhysicalDisk(_Total)\Avg. Disk Queue Length
\PhysicalDisk(0 C:)\% Disk Read Time
\PhysicalDisk(_Total)\% Disk Read Time
```

<span data-ttu-id="6030f-179">`Get-Counter` использует параметр **List** для указания набора счетчиков " **физический диск** ".</span><span class="sxs-lookup"><span data-stu-id="6030f-179">`Get-Counter` uses the **ListSet** parameter to specify the **PhysicalDisk** counter set.</span></span> <span data-ttu-id="6030f-180">Команда заключается в круглые скобки, чтобы свойство **пассвисинстанцес** возвращало каждый экземпляр пути в виде строки.</span><span class="sxs-lookup"><span data-stu-id="6030f-180">The command is enclosed in parentheses so that the **PathsWithInstances** property returns each path instance as a string.</span></span>

### <span data-ttu-id="6030f-181">Пример 10. получение одного значения для каждого счетчика в наборе счетчиков</span><span class="sxs-lookup"><span data-stu-id="6030f-181">Example 10: Get a single value for each counter in a counter set</span></span>

<span data-ttu-id="6030f-182">В этом примере возвращается одно значение для каждого счетчика производительности в наборе счетчиков **памяти** на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="6030f-182">In this example, a single value is returned for each performance counter in the local computer's **Memory** counter set.</span></span>

```powershell
$MemCounters = (Get-Counter -ListSet Memory).Paths
Get-Counter -Counter $MemCounters
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/19/2019 12:05:00        \\Computer01\memory\page faults/sec :
                          868.772077545597

                          \\Computer01\memory\available bytes :
                          9031176192

                          \\Computer01\memory\committed bytes :
                          8242982912

                          \\Computer01\memory\commit limit :
                          19603333120
```

<span data-ttu-id="6030f-183">`Get-Counter` использует параметр **List** для указания набора счетчиков **памяти** .</span><span class="sxs-lookup"><span data-stu-id="6030f-183">`Get-Counter` uses the **ListSet** parameter to specify the **Memory** counter set.</span></span> <span data-ttu-id="6030f-184">Команда заключается в круглые скобки **, чтобы свойство** paths возвращало каждый путь в виде строки.</span><span class="sxs-lookup"><span data-stu-id="6030f-184">The command is enclosed in parentheses so that the **Paths** property returns each path as a string.</span></span> <span data-ttu-id="6030f-185">Пути хранятся в `$MemCounters` переменной.</span><span class="sxs-lookup"><span data-stu-id="6030f-185">The paths are stored in the `$MemCounters` variable.</span></span> <span data-ttu-id="6030f-186">`Get-Counter` использует параметр **Counter** для указания путей к счетчику в `$MemCounters` переменной.</span><span class="sxs-lookup"><span data-stu-id="6030f-186">`Get-Counter` uses the **Counter** parameter to specify the counter paths in the `$MemCounters` variable.</span></span>

### <span data-ttu-id="6030f-187">Пример 11. Отображение значений свойств объекта</span><span class="sxs-lookup"><span data-stu-id="6030f-187">Example 11: Display an object's property values</span></span>

<span data-ttu-id="6030f-188">Значения свойств в объекте **перформанцекаунтерсампле** представляют образец каждого из данных.</span><span class="sxs-lookup"><span data-stu-id="6030f-188">The property values in the **PerformanceCounterSample** object represent each data sample.</span></span> <span data-ttu-id="6030f-189">В этом примере мы используем свойства объекта **каунтерсамплес** для проверки, выбора, сортировки и группирования данных.</span><span class="sxs-lookup"><span data-stu-id="6030f-189">In this example we use the properties of the **CounterSamples** object to examine, select, sort, and group the data.</span></span>

```powershell
$Counter = "\\Server01\Process(Idle)\% Processor Time"
$Data = Get-Counter $Counter
$Data.CounterSamples | Format-List -Property *
```

```Output
Path             : \\Server01\process(idle)\% processor time
InstanceName     : idle
CookedValue      : 198.467899571389
RawValue         : 14329160321003
SecondValue      : 128606459528326201
MultipleCount    : 1
CounterType      : Timer100Ns
Timestamp        : 6/19/2019 12:20:49
Timestamp100NSec : 128606207528320000
Status           : 0
DefaultScale     : 0
TimeBase         : 10000000
```

<span data-ttu-id="6030f-190">Путь к счетчику хранится в `$Counter` переменной.</span><span class="sxs-lookup"><span data-stu-id="6030f-190">The counter path is stored in the `$Counter` variable.</span></span> <span data-ttu-id="6030f-191">`Get-Counter` Возвращает один образец значений счетчика и сохраняет результаты в `$Data` переменной.</span><span class="sxs-lookup"><span data-stu-id="6030f-191">`Get-Counter` gets one sample of the counter values and stores the results in the `$Data` variable.</span></span> <span data-ttu-id="6030f-192">`$Data`Переменная использует свойство **каунтерсамплес** для получения свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="6030f-192">The `$Data` variable uses the **CounterSamples** property to get the object's properties.</span></span> <span data-ttu-id="6030f-193">Объект отправляется по конвейеру в `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="6030f-193">The object is sent down the pipeline to `Format-List`.</span></span> <span data-ttu-id="6030f-194">Параметр **Property** использует `*` подстановочный знак звездочки () для выбора всех свойств.</span><span class="sxs-lookup"><span data-stu-id="6030f-194">The **Property** parameter uses an asterisk (`*`) wildcard to select all the properties.</span></span>

### <span data-ttu-id="6030f-195">Пример 12. значения массива счетчиков производительности</span><span class="sxs-lookup"><span data-stu-id="6030f-195">Example 12: Performance counter array values</span></span>

<span data-ttu-id="6030f-196">В этом примере переменная хранит каждый счетчик производительности.</span><span class="sxs-lookup"><span data-stu-id="6030f-196">In this example, a variable stores each performance counter.</span></span> <span data-ttu-id="6030f-197">Свойство **каунтерсамплес** — это массив, который может отображать определенные значения счетчика.</span><span class="sxs-lookup"><span data-stu-id="6030f-197">The **CounterSamples** property is an array that can display specific counter values.</span></span>

<span data-ttu-id="6030f-198">Для просмотра каждого образца счетчика используйте `$Counter.CounterSamples` .</span><span class="sxs-lookup"><span data-stu-id="6030f-198">To display each counter sample, use `$Counter.CounterSamples`.</span></span>

```powershell
$Counter = Get-Counter -Counter "\Processor(*)\% Processor Time"
$Counter.CounterSamples[0]
```

```Output
Path                                         InstanceName        CookedValue
----                                         ------------        -----------
\\Computer01\processor(0)\% processor time   0              1.33997091699662
```

<span data-ttu-id="6030f-199">`Get-Counter` использует параметр **Counter** для указания счетчика `\Processor(*)\% Processor Time` .</span><span class="sxs-lookup"><span data-stu-id="6030f-199">`Get-Counter` uses the **Counter** parameter to specify the counter `\Processor(*)\% Processor Time`.</span></span> <span data-ttu-id="6030f-200">Значения хранятся в `$Counter` переменной.</span><span class="sxs-lookup"><span data-stu-id="6030f-200">The values are stored in the `$Counter` variable.</span></span>
<span data-ttu-id="6030f-201">`$Counter.CounterSamples[0]` Отображает значение массива для первого значения счетчика.</span><span class="sxs-lookup"><span data-stu-id="6030f-201">`$Counter.CounterSamples[0]` displays the array value for the first counter value.</span></span>

### <span data-ttu-id="6030f-202">Пример 13. Сравнение значений счетчиков производительности</span><span class="sxs-lookup"><span data-stu-id="6030f-202">Example 13: Compare performance counter values</span></span>

<span data-ttu-id="6030f-203">Этот пример находит количество процессорного времени, используемого каждым процессором на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="6030f-203">This example finds the amount of processor time used by each processor on the local computer.</span></span> <span data-ttu-id="6030f-204">Свойство **каунтерсамплес** используется для сравнения данных счетчика с указанным значением.</span><span class="sxs-lookup"><span data-stu-id="6030f-204">The **CounterSamples** property is used to compare the counter data against a specified value.</span></span>

<span data-ttu-id="6030f-205">Для просмотра каждого образца счетчика используйте `$Counter.CounterSamples` .</span><span class="sxs-lookup"><span data-stu-id="6030f-205">To display each counter sample, use `$Counter.CounterSamples`.</span></span>

```powershell
$Counter = Get-Counter -Counter "\Processor(*)\% Processor Time"
$Counter.CounterSamples | Where-Object { $_.CookedValue -lt "20" }
```

```Output
Path                                         InstanceName        CookedValue
----                                         ------------        -----------
\\Computer01\processor(0)\% processor time   0              12.6398025240208
\\Computer01\processor(1)\% processor time   1              15.7598095767344
```

<span data-ttu-id="6030f-206">`Get-Counter` использует параметр **Counter** для указания счетчика `\Processor(*)\% Processor Time` .</span><span class="sxs-lookup"><span data-stu-id="6030f-206">`Get-Counter` uses the **Counter** parameter to specify the counter `\Processor(*)\% Processor Time`.</span></span> <span data-ttu-id="6030f-207">Значения хранятся в `$Counter` переменной.</span><span class="sxs-lookup"><span data-stu-id="6030f-207">The values are stored in the `$Counter` variable.</span></span> <span data-ttu-id="6030f-208">Объекты, хранящиеся в `$Counter.CounterSamples` , отправляются по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="6030f-208">The objects stored in `$Counter.CounterSamples` are sent down the pipeline.</span></span> <span data-ttu-id="6030f-209">`Where-Object` использует блок скрипта для сравнения значения каждого объекта с указанным значением 20.</span><span class="sxs-lookup"><span data-stu-id="6030f-209">`Where-Object` uses a script block to compare each objects value against a specified value of 20.</span></span> <span data-ttu-id="6030f-210">`$_.CookedValue`— Это переменная для текущего объекта в конвейере.</span><span class="sxs-lookup"><span data-stu-id="6030f-210">The `$_.CookedValue` is a variable for the current object in the pipeline.</span></span> <span data-ttu-id="6030f-211">Отображаются счетчики с **кукедвалуе** меньше 20.</span><span class="sxs-lookup"><span data-stu-id="6030f-211">Counters with a **CookedValue** that is less than 20 are displayed.</span></span>

### <span data-ttu-id="6030f-212">Пример 14. Сортировка данных счетчика производительности</span><span class="sxs-lookup"><span data-stu-id="6030f-212">Example 14: Sort performance counter data</span></span>

<span data-ttu-id="6030f-213">В этом примере показано, как сортировать данные счетчиков производительности.</span><span class="sxs-lookup"><span data-stu-id="6030f-213">This example shows how to sort performance counter data.</span></span> <span data-ttu-id="6030f-214">В примере выполняется поиск процессов на компьютере, которые используют наибольшее время процессора во время выполнения примера.</span><span class="sxs-lookup"><span data-stu-id="6030f-214">The example finds the processes on the computer that are using the most processor time during the sample.</span></span>

```powershell
$Procs = Get-Counter -Counter "\Process(*)\% Processor Time"
$Procs.CounterSamples | Sort-Object -Property CookedValue -Descending |
   Format-Table -Property Path, InstanceName, CookedValue -AutoSize
```

```Output
Path                                                         InstanceName             CookedValue
----                                                         ------------             -----------
\\Computer01\process(_total)\% processor time                _total              395.464129650573
\\Computer01\process(idle)\% processor time                  idle                389.356575524695
\\Computer01\process(mssense)\% processor time               mssense             3.05377706293879
\\Computer01\process(csrss#1)\% processor time               csrss               1.52688853146939
\\Computer01\process(microsoftedgecp#10)\% processor time    microsoftedgecp     1.52688853146939
\\Computer01\process(runtimebroker#5)\% processor time       runtimebroker                      0
\\Computer01\process(settingsynchost)\% processor time       settingsynchost                    0
\\Computer01\process(microsoftedgecp#16)\% processor time    microsoftedgecp                    0
```

<span data-ttu-id="6030f-215">`Get-Counter` использует параметр **Counter** , чтобы указать `\Process(*)\% Processor Time` Счетчик для всех процессов на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="6030f-215">`Get-Counter` uses the **Counter** parameter to specify the `\Process(*)\% Processor Time` counter for all the processes on the local computer.</span></span> <span data-ttu-id="6030f-216">Результат сохраняется в `$Procs` переменной.</span><span class="sxs-lookup"><span data-stu-id="6030f-216">The result is stored in the `$Procs` variable.</span></span> <span data-ttu-id="6030f-217">`$Procs`Переменная со свойством **каунтерсамплес** отправляет объекты **перформанцекаунтерсампле** вниз по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="6030f-217">The `$Procs` variable with the **CounterSamples** property sends the **PerformanceCounterSample** objects down the pipeline.</span></span> <span data-ttu-id="6030f-218">`Sort-Object` использует параметр **Property** для сортировки объектов по **Кукедвалуе** в порядке **убывания** .</span><span class="sxs-lookup"><span data-stu-id="6030f-218">`Sort-Object` uses the **Property** parameter to sort the objects by **CookedValue** in **Descending** order.</span></span> <span data-ttu-id="6030f-219">`Format-Table` использует параметр **Property** для выбора столбцов для выходных данных.</span><span class="sxs-lookup"><span data-stu-id="6030f-219">`Format-Table` uses the **Property** parameter to select the columns for the output.</span></span> <span data-ttu-id="6030f-220">Параметр **AutoSize** корректирует ширину столбцов для сокращения усечения.</span><span class="sxs-lookup"><span data-stu-id="6030f-220">The **AutoSize** parameter adjusts the column widths to minimize truncation.</span></span>

## <span data-ttu-id="6030f-221">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6030f-221">PARAMETERS</span></span>

### <span data-ttu-id="6030f-222">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="6030f-222">-ComputerName</span></span>

<span data-ttu-id="6030f-223">Указывает одно имя компьютера или разделенный запятыми массив имен **удаленных** компьютеров.</span><span class="sxs-lookup"><span data-stu-id="6030f-223">Specifies one computer name or a comma-separated array of **remote** computer names.</span></span> <span data-ttu-id="6030f-224">Используйте имя NetBIOS, IP-адрес или полное доменное имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="6030f-224">Use the NetBIOS name, an IP address, or the computer's fully qualified domain name.</span></span>

<span data-ttu-id="6030f-225">Чтобы получить данные счетчиков производительности с **локального** компьютера, исключите параметр **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="6030f-225">To get performance counter data from the **local** computer, exclude the **ComputerName** parameter.</span></span>
<span data-ttu-id="6030f-226">Для выходных данных, таких как **список** , содержащий столбец **MachineName** , точка ( `.` ) обозначает локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="6030f-226">For output such as a **ListSet** that contains the **MachineName** column, a dot (`.`) indicates the local computer.</span></span>

<span data-ttu-id="6030f-227">`Get-Counter` не зависит от удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6030f-227">`Get-Counter` doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="6030f-228">Параметр **ComputerName** можно использовать, даже если компьютер не настроен для выполнения удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="6030f-228">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6030f-229">-Continuous</span><span class="sxs-lookup"><span data-stu-id="6030f-229">-Continuous</span></span>

<span data-ttu-id="6030f-230">Если указан параметр **Continuous** , `Get-Counter` получает выборки до нажатия клавиши <kbd>CTRL</kbd> + <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="6030f-230">When the **Continuous** is specified, `Get-Counter` gets samples until you press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span> <span data-ttu-id="6030f-231">Выборки получаются каждую секунду для каждого указанного счетчика производительности.</span><span class="sxs-lookup"><span data-stu-id="6030f-231">Samples are obtained every second for each specified performance counter.</span></span> <span data-ttu-id="6030f-232">Используйте параметр **SampleInterval** , чтобы увеличить интервал между непрерывными примерами.</span><span class="sxs-lookup"><span data-stu-id="6030f-232">Use the **SampleInterval** parameter to increase the interval between continuous samples.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6030f-233">-Counter</span><span class="sxs-lookup"><span data-stu-id="6030f-233">-Counter</span></span>

<span data-ttu-id="6030f-234">Указывает путь к одному или нескольким путям счетчиков.</span><span class="sxs-lookup"><span data-stu-id="6030f-234">Specifies the path to one or more counter paths.</span></span> <span data-ttu-id="6030f-235">Пути являются входными данными в виде массива с разделителями-запятыми, переменной или значений из текстового файла.</span><span class="sxs-lookup"><span data-stu-id="6030f-235">Paths are input as a comma-separated array, a variable, or values from a text file.</span></span> <span data-ttu-id="6030f-236">Строки пути счетчика можно отправить по конвейеру в `Get-Counter` .</span><span class="sxs-lookup"><span data-stu-id="6030f-236">You can send counter path strings down the pipeline to `Get-Counter`.</span></span>

<span data-ttu-id="6030f-237">Пути счетчиков используют следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="6030f-237">Counter paths use the following syntax:</span></span>

`\\ComputerName\CounterSet(Instance)\CounterName`

`\CounterSet(Instance)\CounterName`

<span data-ttu-id="6030f-238">Пример:</span><span class="sxs-lookup"><span data-stu-id="6030f-238">For example:</span></span>

`\\Server01\Processor(*)\% User Time`

`\Processor(*)\% User Time`

<span data-ttu-id="6030f-239">Параметр `\\ComputerName` является необязательным в пути счетчика производительности.</span><span class="sxs-lookup"><span data-stu-id="6030f-239">The `\\ComputerName` is optional in a performance counter path.</span></span> <span data-ttu-id="6030f-240">Если путь счетчика не содержит имя компьютера, `Get-Counter` использует локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="6030f-240">If the counter path doesn't include the computer name, `Get-Counter` uses the local computer.</span></span>

<span data-ttu-id="6030f-241">Звездочка ( `*` ) в экземпляре является символом-шаблоном для получения всех экземпляров счетчика.</span><span class="sxs-lookup"><span data-stu-id="6030f-241">An asterisk (`*`) in the instance is a wildcard character to get all instances of the counter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="6030f-242">— Список</span><span class="sxs-lookup"><span data-stu-id="6030f-242">-ListSet</span></span>

<span data-ttu-id="6030f-243">Список наборов счетчиков производительности на компьютерах.</span><span class="sxs-lookup"><span data-stu-id="6030f-243">Lists the performance counter sets on the computers.</span></span> <span data-ttu-id="6030f-244">`*`Для указания всех наборов счетчиков используйте звездочку ().</span><span class="sxs-lookup"><span data-stu-id="6030f-244">Use an asterisk (`*`) to specify all counter sets.</span></span> <span data-ttu-id="6030f-245">Введите одно имя или строку с разделителями-запятыми в именах наборов счетчиков.</span><span class="sxs-lookup"><span data-stu-id="6030f-245">Enter one name or a comma-separated string of counter set names.</span></span> <span data-ttu-id="6030f-246">Имена наборов счетчиков можно отправить по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="6030f-246">You can send counter set names down the pipeline.</span></span>

<span data-ttu-id="6030f-247">Чтобы получить наборы счетчиков с отформатированными путями счетчиков, используйте параметр **List** .</span><span class="sxs-lookup"><span data-stu-id="6030f-247">To get a counter sets formatted counter paths, use the **ListSet** parameter.</span></span> <span data-ttu-id="6030f-248">Свойства **paths** и **пассвисинстанцес** каждого набора счетчиков содержат отдельные пути счетчиков, отформатированные в виде строки.</span><span class="sxs-lookup"><span data-stu-id="6030f-248">The **Paths** and **PathsWithInstances** properties of each counter set contain the individual counter paths formatted as a string.</span></span>

<span data-ttu-id="6030f-249">Можно сохранить строки пути счетчика в переменной или использовать конвейер для отправки строки другой `Get-Counter` команде.</span><span class="sxs-lookup"><span data-stu-id="6030f-249">You can save the counter path strings in a variable or use the pipeline to send the string to another `Get-Counter` command.</span></span>

<span data-ttu-id="6030f-250">Например, для отправки каждого пути счетчика **процессора** в `Get-Counter` :</span><span class="sxs-lookup"><span data-stu-id="6030f-250">For example to send each **Processor** counter path to `Get-Counter`:</span></span>

`Get-Counter -ListSet Processor | Get-Counter`

> [!NOTE]
> <span data-ttu-id="6030f-251">В PowerShell 7 `Get-Counter` не удается получить свойство **Description** набора счетчиков.</span><span class="sxs-lookup"><span data-stu-id="6030f-251">In PowerShell 7, `Get-Counter` can't retrieve the **Description** property of the counter set.</span></span> <span data-ttu-id="6030f-252">**Описание** имеет значение `$null` .</span><span class="sxs-lookup"><span data-stu-id="6030f-252">The **Description** is set to `$null`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ListSetSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="6030f-253">-Макссамплес</span><span class="sxs-lookup"><span data-stu-id="6030f-253">-MaxSamples</span></span>

<span data-ttu-id="6030f-254">Указывает число выборок, получаемых из каждого указанного счетчика производительности.</span><span class="sxs-lookup"><span data-stu-id="6030f-254">Specifies the number of samples to get from each specified performance counter.</span></span> <span data-ttu-id="6030f-255">Чтобы получить постоянный поток образцов, используйте параметр **Continuous** .</span><span class="sxs-lookup"><span data-stu-id="6030f-255">To get a constant stream of samples, use the **Continuous** parameter.</span></span>

<span data-ttu-id="6030f-256">Если параметр **макссамплес** не указан, `Get-Counter` получает только один выборку для каждого указанного счетчика.</span><span class="sxs-lookup"><span data-stu-id="6030f-256">If the **MaxSamples** parameter isn't specified, `Get-Counter` only gets one sample for each specified counter.</span></span>

<span data-ttu-id="6030f-257">Чтобы получить большой набор данных, выполните в `Get-Counter` качестве фонового задания PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6030f-257">To collect a large data set, run `Get-Counter` as a PowerShell background job.</span></span> <span data-ttu-id="6030f-258">См. дополнительные сведения о [заданиях](../Microsoft.PowerShell.Core/About/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="6030f-258">For more information, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md).</span></span>

```yaml
Type: System.Int64
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6030f-259">-SampleInterval</span><span class="sxs-lookup"><span data-stu-id="6030f-259">-SampleInterval</span></span>

<span data-ttu-id="6030f-260">Указывает количество секунд между выборками для каждого указанного счетчика производительности.</span><span class="sxs-lookup"><span data-stu-id="6030f-260">Specifies the number of seconds between samples for each specified performance counter.</span></span> <span data-ttu-id="6030f-261">Если параметр **SampleInterval** не указан, `Get-Counter` используется интервал в 1 секунду.</span><span class="sxs-lookup"><span data-stu-id="6030f-261">If the **SampleInterval** parameter isn't specified, `Get-Counter` uses a one-second interval.</span></span>

```yaml
Type: System.Int32
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6030f-262">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="6030f-262">CommonParameters</span></span>

<span data-ttu-id="6030f-263">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6030f-263">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6030f-264">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6030f-264">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6030f-265">Входные данные</span><span class="sxs-lookup"><span data-stu-id="6030f-265">INPUTS</span></span>

### <span data-ttu-id="6030f-266">System.String[]</span><span class="sxs-lookup"><span data-stu-id="6030f-266">System.String[]</span></span>

<span data-ttu-id="6030f-267">`Get-Counter` принимает входные данные конвейера для путей счетчиков и имен наборов счетчиков.</span><span class="sxs-lookup"><span data-stu-id="6030f-267">`Get-Counter` accepts pipeline input for counter paths and counter set names.</span></span>

## <span data-ttu-id="6030f-268">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="6030f-268">OUTPUTS</span></span>

### <span data-ttu-id="6030f-269">Microsoft. PowerShell. Commands. NOCOUNT. Counters, Microsoft. PowerShell. Commands. NOCOUNT. PerformanceCounterSampleSet, Microsoft. PowerShell. Commands. NOCOUNT. Перформанцекаунтерсампле</span><span class="sxs-lookup"><span data-stu-id="6030f-269">Microsoft.PowerShell.Commands.GetCounter.CounterSet, Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet, Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSample</span></span>

<span data-ttu-id="6030f-270">Чтобы просмотреть свойства объекта, отправьте выходные данные по конвейеру в `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="6030f-270">To view an object's properties, send the output down the pipeline to `Get-Member`.</span></span> <span data-ttu-id="6030f-271">Ниже приведены типы объектов, которые являются выходными данными.</span><span class="sxs-lookup"><span data-stu-id="6030f-271">The object types that are output are as follows:</span></span>

<span data-ttu-id="6030f-272">**Параметр CounterSet** : **Microsoft. PowerShell. Commands. NOCOUNT. CounterSet**</span><span class="sxs-lookup"><span data-stu-id="6030f-272">**ListSet** parameter: **Microsoft.PowerShell.Commands.GetCounter.CounterSet**</span></span>

<span data-ttu-id="6030f-273">Параметр **счетчика** : **Microsoft. PowerShell. Commands. NOCOUNT. PerformanceCounterSampleSet**</span><span class="sxs-lookup"><span data-stu-id="6030f-273">**Counter** parameter: **Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet**</span></span>

<span data-ttu-id="6030f-274">Свойство **каунтерсамплес** : **Microsoft. PowerShell. Commands. NOCOUNT. перформанцекаунтерсампле**</span><span class="sxs-lookup"><span data-stu-id="6030f-274">**CounterSamples** property: **Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSample**</span></span>

## <span data-ttu-id="6030f-275">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="6030f-275">NOTES</span></span>

<span data-ttu-id="6030f-276">Если параметры не указаны, `Get-Counter` получает один выборку для каждого указанного счетчика производительности.</span><span class="sxs-lookup"><span data-stu-id="6030f-276">If no parameters are specified, `Get-Counter` gets one sample for each specified performance counter.</span></span> <span data-ttu-id="6030f-277">Используйте параметры **макссамплес** и **Continuous** для получения дополнительных образцов.</span><span class="sxs-lookup"><span data-stu-id="6030f-277">Use the **MaxSamples** and **Continuous** parameters to get more samples.</span></span>

<span data-ttu-id="6030f-278">`Get-Counter` использует интервал в 1 секунду между образцами.</span><span class="sxs-lookup"><span data-stu-id="6030f-278">`Get-Counter` uses a one-second interval between samples.</span></span> <span data-ttu-id="6030f-279">Чтобы увеличить интервал, используйте параметр **SampleInterval** .</span><span class="sxs-lookup"><span data-stu-id="6030f-279">Use the **SampleInterval** parameter to increase the interval.</span></span>

<span data-ttu-id="6030f-280">Значения **макссамплес** и **SampleInterval** применяются ко всем счетчикам на каждом компьютере в команде.</span><span class="sxs-lookup"><span data-stu-id="6030f-280">The **MaxSamples** and **SampleInterval** values apply to all the counters on each computer in the command.</span></span> <span data-ttu-id="6030f-281">Чтобы задать различные значения для разных счетчиков, введите отдельные `Get-Counter` команды.</span><span class="sxs-lookup"><span data-stu-id="6030f-281">To set different values for different counters, enter separate `Get-Counter` commands.</span></span>

<span data-ttu-id="6030f-282">В PowerShell 7 при использовании параметра **List** `Get-Counter` не может получить свойство **Description** набора счетчиков.</span><span class="sxs-lookup"><span data-stu-id="6030f-282">In PowerShell 7, when using the **ListSet** parameter, `Get-Counter` can't retrieve the **Description** property of the counter set.</span></span> <span data-ttu-id="6030f-283">**Описание** имеет значение `$null` .</span><span class="sxs-lookup"><span data-stu-id="6030f-283">The **Description** is set to `$null`.</span></span>

## <span data-ttu-id="6030f-284">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="6030f-284">RELATED LINKS</span></span>

[<span data-ttu-id="6030f-285">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="6030f-285">about_Automatic_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="6030f-286">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="6030f-286">about_Jobs</span></span>](../Microsoft.PowerShell.Core/About/about_Jobs.md)

[<span data-ttu-id="6030f-287">Format-List</span><span class="sxs-lookup"><span data-stu-id="6030f-287">Format-List</span></span>](../Microsoft.PowerShell.Utility/Format-List.md)

[<span data-ttu-id="6030f-288">Format-Table</span><span class="sxs-lookup"><span data-stu-id="6030f-288">Format-Table</span></span>](../Microsoft.PowerShell.Utility/Format-Table.md)

[<span data-ttu-id="6030f-289">Get-Member</span><span class="sxs-lookup"><span data-stu-id="6030f-289">Get-Member</span></span>](../Microsoft.PowerShell.Utility/Get-Member.md)

[<span data-ttu-id="6030f-290">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="6030f-290">Receive-Job</span></span>](../Microsoft.PowerShell.Core/Receive-Job.md)

[<span data-ttu-id="6030f-291">Start-Job</span><span class="sxs-lookup"><span data-stu-id="6030f-291">Start-Job</span></span>](../Microsoft.PowerShell.Core/Start-Job.md)

[<span data-ttu-id="6030f-292">Where-Object</span><span class="sxs-lookup"><span data-stu-id="6030f-292">Where-Object</span></span>](..//Microsoft.PowerShell.Core/Where-Object.md)
