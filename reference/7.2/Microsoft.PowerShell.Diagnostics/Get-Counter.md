---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 11/06/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/get-counter?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Counter
ms.openlocfilehash: 4aed8db557b2d623aba4cd7218524af9957674c9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605527"
---
# <span data-ttu-id="12647-102">Get-Counter</span><span class="sxs-lookup"><span data-stu-id="12647-102">Get-Counter</span></span>

## <span data-ttu-id="12647-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="12647-103">SYNOPSIS</span></span>
<span data-ttu-id="12647-104">Получает данные счетчиков производительности с локальных и удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="12647-104">Gets performance counter data from local and remote computers.</span></span>

## <span data-ttu-id="12647-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="12647-105">SYNTAX</span></span>

### <span data-ttu-id="12647-106">CounterSet (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="12647-106">GetCounterSet (Default)</span></span>

```
Get-Counter [[-Counter] <String[]>] [-SampleInterval <Int32>] [-MaxSamples <Int64>] [-Continuous]
 [-ComputerName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="12647-107">листсетсет</span><span class="sxs-lookup"><span data-stu-id="12647-107">ListSetSet</span></span>

```
Get-Counter [-ListSet] <String[]> [-ComputerName <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="12647-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="12647-108">DESCRIPTION</span></span>

<span data-ttu-id="12647-109">`Get-Counter`Командлет получает данные счетчика производительности непосредственно из инструментария наблюдения за производительностью в семействе операционных систем Windows.</span><span class="sxs-lookup"><span data-stu-id="12647-109">The `Get-Counter` cmdlet gets performance counter data directly from the performance monitoring instrumentation in the Windows family of operating systems.</span></span> <span data-ttu-id="12647-110">`Get-Counter` Возвращает данные о производительности с локального компьютера или удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="12647-110">`Get-Counter` gets performance data from a local computer or remote computers.</span></span>

<span data-ttu-id="12647-111">С помощью параметров можно `Get-Counter` указать один или несколько компьютеров, список наборов счетчиков производительности и содержащихся в них экземпляров, задать интервалы выборки и указать максимальное число выборок.</span><span class="sxs-lookup"><span data-stu-id="12647-111">You can use the `Get-Counter` parameters to specify one or more computers, list the performance counter sets and the instances they contain, set the sample intervals, and specify the maximum number of samples.</span></span> <span data-ttu-id="12647-112">Без параметров `Get-Counter` получает данные счетчика производительности для набора системных счетчиков.</span><span class="sxs-lookup"><span data-stu-id="12647-112">Without parameters, `Get-Counter` gets performance counter data for a set of system counters.</span></span>

<span data-ttu-id="12647-113">Многие наборы счетчиков защищены списками управления доступом (ACL).</span><span class="sxs-lookup"><span data-stu-id="12647-113">Many counter sets are protected by access control lists (ACL).</span></span> <span data-ttu-id="12647-114">Чтобы просмотреть все наборы счетчиков, откройте PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="12647-114">To see all counter sets, open PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="12647-115">Этот командлет был повторно введен в PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="12647-115">This cmdlet was reintroduced in PowerShell 7.</span></span>

## <span data-ttu-id="12647-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="12647-116">EXAMPLES</span></span>

### <span data-ttu-id="12647-117">Пример 1. Получение списка наборов счетчиков</span><span class="sxs-lookup"><span data-stu-id="12647-117">Example 1: Get the counter set list</span></span>

<span data-ttu-id="12647-118">В этом примере получается список наборов счетчиков локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="12647-118">This example gets the local computer's list of counter sets.</span></span>

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

<span data-ttu-id="12647-119">`Get-Counter` использует параметр **List** со звездочкой ( `*` ) для получения списка наборов счетчиков.</span><span class="sxs-lookup"><span data-stu-id="12647-119">`Get-Counter` uses the **ListSet** parameter with an asterisk (`*`) to get the list of counter sets.</span></span>
<span data-ttu-id="12647-120">Точка ( `.` ) в столбце **MachineName** представляет локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="12647-120">The dot (`.`) in the **MachineName** column represents the local computer.</span></span>

### <span data-ttu-id="12647-121">Пример 2. Указание SampleInterval и Макссамплес</span><span class="sxs-lookup"><span data-stu-id="12647-121">Example 2: Specify the SampleInterval and MaxSamples</span></span>

<span data-ttu-id="12647-122">Этот пример возвращает данные счетчика для всех процессоров на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="12647-122">This examples gets the counter data for all processors on the local computer.</span></span> <span data-ttu-id="12647-123">Данные собираются с интервалом в две секунды, пока не будут представлены три примера.</span><span class="sxs-lookup"><span data-stu-id="12647-123">Data is collected at two-second intervals until there are three samples.</span></span>

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

<span data-ttu-id="12647-124">`Get-Counter` использует параметр **Counter** для указания пути счетчика `\Processor(_Total)\% Processor Time` .</span><span class="sxs-lookup"><span data-stu-id="12647-124">`Get-Counter` uses the **Counter** parameter to specify the counter path `\Processor(_Total)\% Processor Time`.</span></span> <span data-ttu-id="12647-125">Параметр **SampleInterval** задает интервал в два секунды для проверки счетчика.</span><span class="sxs-lookup"><span data-stu-id="12647-125">The **SampleInterval** parameter sets a two-second interval to check the counter.</span></span> <span data-ttu-id="12647-126">**Макссамплес** определяет, что три — это максимальное число раз для проверки счетчика.</span><span class="sxs-lookup"><span data-stu-id="12647-126">**MaxSamples** determines that three is the maximum number of times to check the counter.</span></span>

### <span data-ttu-id="12647-127">Пример 3. получение непрерывных выборок счетчика</span><span class="sxs-lookup"><span data-stu-id="12647-127">Example 3: Get continuous samples of a counter</span></span>

<span data-ttu-id="12647-128">Этот пример получает непрерывные выборки для счетчика каждую секунду.</span><span class="sxs-lookup"><span data-stu-id="12647-128">This examples gets continuous samples for a counter every second.</span></span> <span data-ttu-id="12647-129">Чтобы прерывать выполнение команды, нажмите клавиши <kbd>CTRL</kbd> + <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="12647-129">To stop the command, press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span> <span data-ttu-id="12647-130">Чтобы указать более длинный интервал между выборками, используйте параметр **SampleInterval** .</span><span class="sxs-lookup"><span data-stu-id="12647-130">To specify a longer interval between samples, use the **SampleInterval** parameter.</span></span>

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

<span data-ttu-id="12647-131">`Get-Counter` использует параметр **Counter** для указания `\Processor\% Processor Time` счетчика.</span><span class="sxs-lookup"><span data-stu-id="12647-131">`Get-Counter` uses the **Counter** parameter to specify the `\Processor\% Processor Time` counter.</span></span>
<span data-ttu-id="12647-132">Параметр **непрерывно** задает получение образцов каждую секунду до тех пор, пока команда не будет остановлена с помощью <kbd>клавиши CTRL</kbd> + <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="12647-132">The **Continuous** parameter specifies to get samples every second until the command is stopped with <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span>

### <span data-ttu-id="12647-133">Пример 4. Алфавитный список наборов счетчиков</span><span class="sxs-lookup"><span data-stu-id="12647-133">Example 4: Alphabetical list of counter sets</span></span>

<span data-ttu-id="12647-134">В этом примере используется конвейер для получения набора списка счетчиков, а затем сортировка списка в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="12647-134">This example uses the pipeline to get the counter list set and then sort the list in alphabetical order.</span></span>

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

<span data-ttu-id="12647-135">`Get-Counter` использует параметр **List** со звездочкой ( `*` ) для получения полного списка наборов счетчиков.</span><span class="sxs-lookup"><span data-stu-id="12647-135">`Get-Counter` uses the **ListSet** parameter with an asterisk (`*`) to get a complete list of counter sets.</span></span> <span data-ttu-id="12647-136">Объекты **CounterSet** отправляются по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="12647-136">The **CounterSet** objects are sent down the pipeline.</span></span> <span data-ttu-id="12647-137">`Sort-Object` использует параметр **Property** , чтобы указать, что объекты сортируются по **CounterSetName**.</span><span class="sxs-lookup"><span data-stu-id="12647-137">`Sort-Object` uses the **Property** parameter to specify that the objects are sorted by **CounterSetName**.</span></span> <span data-ttu-id="12647-138">Объекты отправляются по конвейеру в `Format-Table` .</span><span class="sxs-lookup"><span data-stu-id="12647-138">The objects are sent down the pipeline to `Format-Table`.</span></span> <span data-ttu-id="12647-139">Параметр **AutoSize** корректирует ширину столбцов для сокращения усечения.</span><span class="sxs-lookup"><span data-stu-id="12647-139">The **AutoSize** parameter adjusts the column widths to minimize truncation.</span></span>

<span data-ttu-id="12647-140">Точка ( `.` ) в столбце **MachineName** представляет локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="12647-140">The dot (`.`) in the **MachineName** column represents the local computer.</span></span>

### <span data-ttu-id="12647-141">Пример 5. Запуск фонового задания для получения данных счетчика</span><span class="sxs-lookup"><span data-stu-id="12647-141">Example 5: Run a background job to get counter data</span></span>

<span data-ttu-id="12647-142">В этом примере `Start-Job` выполняет команду в `Get-Counter` качестве фонового задания на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="12647-142">In this example, `Start-Job` runs a `Get-Counter` command as a background job on the local computer.</span></span>
<span data-ttu-id="12647-143">Чтобы просмотреть выходные данные счетчика производительности задания, используйте `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="12647-143">To view the performance counter output from the job, use the `Receive-Job` cmdlet.</span></span>

```powershell
Start-Job -ScriptBlock {Get-Counter -Counter "\LogicalDisk(_Total)\% Free Space" -MaxSamples 1000}
```

```Output
Id     Name  PSJobTypeName   State    HasMoreData  Location   Command
--     ----  -------------   -----    -----------  --------   -------
1      Job1  BackgroundJob   Running  True         localhost  Get-Counter -Counter
```

<span data-ttu-id="12647-144">`Start-Job` использует параметр **ScriptBlock** для выполнения `Get-Counter` команды.</span><span class="sxs-lookup"><span data-stu-id="12647-144">`Start-Job` uses the **ScriptBlock** parameter to run a `Get-Counter` command.</span></span> <span data-ttu-id="12647-145">`Get-Counter` использует параметр **Counter** для указания пути счетчика `\LogicalDisk(_Total)\% Free Space` .</span><span class="sxs-lookup"><span data-stu-id="12647-145">`Get-Counter` uses the **Counter** parameter to specify the counter path `\LogicalDisk(_Total)\% Free Space`.</span></span> <span data-ttu-id="12647-146">Параметр **макссамплес** указывает, что получение образцов счетчика 1000.</span><span class="sxs-lookup"><span data-stu-id="12647-146">The **MaxSamples** parameter specifies to get 1000 samples of the counter.</span></span>

### <span data-ttu-id="12647-147">Пример 6. получение данных счетчиков с нескольких компьютеров</span><span class="sxs-lookup"><span data-stu-id="12647-147">Example 6: Get counter data from multiple computers</span></span>

<span data-ttu-id="12647-148">В этом примере используется переменная для получения данных счетчиков производительности с двух компьютеров.</span><span class="sxs-lookup"><span data-stu-id="12647-148">This example uses a variable to get performance counter data from two computers.</span></span>

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

<span data-ttu-id="12647-149">`$DiskReads`Переменная хранит `\LogicalDisk(C:)\Disk Reads/sec` путь счетчика.</span><span class="sxs-lookup"><span data-stu-id="12647-149">The `$DiskReads` variable stores the `\LogicalDisk(C:)\Disk Reads/sec` counter path.</span></span> <span data-ttu-id="12647-150">`$DiskReads`Переменная отправляется по конвейеру в `Get-Counter` .</span><span class="sxs-lookup"><span data-stu-id="12647-150">The `$DiskReads` variable is sent down the pipeline to `Get-Counter`.</span></span> <span data-ttu-id="12647-151">Значение **Counter** является первым параметром позиционирования и принимает путь, хранящийся в `$DiskReads` .</span><span class="sxs-lookup"><span data-stu-id="12647-151">**Counter** is the first position parameter and accepts the path stored in `$DiskReads`.</span></span> <span data-ttu-id="12647-152">**ComputerName** указывает два компьютера и **макссамплес** указывает на получение 10 образцов с каждого компьютера.</span><span class="sxs-lookup"><span data-stu-id="12647-152">**ComputerName** specifies the two computers and **MaxSamples** specifies to get 10 samples from each computer.</span></span>

### <span data-ttu-id="12647-153">Пример 7. Получение значений экземпляра счетчика из нескольких случайных компьютеров</span><span class="sxs-lookup"><span data-stu-id="12647-153">Example 7: Get a counter's instance values from multiple random computers</span></span>

<span data-ttu-id="12647-154">В этом примере возвращается значение счетчика производительности на 50 случайных удаленных компьютеров в Организации.</span><span class="sxs-lookup"><span data-stu-id="12647-154">This example gets the value of a performance counter on 50 random, remote computers in the enterprise.</span></span> <span data-ttu-id="12647-155">Параметр **ComputerName** использует случайные имена компьютеров, хранящиеся в переменной.</span><span class="sxs-lookup"><span data-stu-id="12647-155">The **ComputerName** parameter uses random computer names stored in a variable.</span></span> <span data-ttu-id="12647-156">Чтобы обновить имена компьютеров в переменной, повторно создайте переменную.</span><span class="sxs-lookup"><span data-stu-id="12647-156">To update the computer names in the variable, recreate the variable.</span></span>

<span data-ttu-id="12647-157">Альтернативой для имен серверов в параметре **ComputerName** является использование текстового файла.</span><span class="sxs-lookup"><span data-stu-id="12647-157">An alternative for the server names in the **ComputerName** parameter is to use a text file.</span></span> <span data-ttu-id="12647-158">Пример:</span><span class="sxs-lookup"><span data-stu-id="12647-158">For example:</span></span>

`-ComputerName (Get-Random (Get-Content -Path C:\Servers.txt) -Count 50)`

<span data-ttu-id="12647-159">Путь к счетчику содержит звездочку ( `*` ) в имени экземпляра для получения данных для каждого из процессоров удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="12647-159">The counter path includes an asterisk (`*`) in the instance name to get the data for each of the remote computer's processors.</span></span>

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

<span data-ttu-id="12647-160">`Get-Random`Командлет использует `Get-Content` для выбора 50 случайных имен компьютеров из `Servers.txt` файла.</span><span class="sxs-lookup"><span data-stu-id="12647-160">The `Get-Random` cmdlet uses `Get-Content` to select 50 random computer names from the `Servers.txt` file.</span></span> <span data-ttu-id="12647-161">Имена удаленных компьютеров хранятся в `$Servers` переменной.</span><span class="sxs-lookup"><span data-stu-id="12647-161">The remote computer names are stored in the `$Servers` variable.</span></span> <span data-ttu-id="12647-162">`\Processor(*)\% Processor Time`Путь к счетчику хранится в `$Counter` переменной.</span><span class="sxs-lookup"><span data-stu-id="12647-162">The `\Processor(*)\% Processor Time` counter's path is stored in the `$Counter` variable.</span></span> <span data-ttu-id="12647-163">`Get-Counter` использует параметр **Counter** для указания счетчиков в `$Counter` переменной.</span><span class="sxs-lookup"><span data-stu-id="12647-163">`Get-Counter` uses the **Counter** parameter to specify the counters in the `$Counter` variable.</span></span> <span data-ttu-id="12647-164">Параметр **ComputerName** задает имена компьютеров в `$Servers` переменной.</span><span class="sxs-lookup"><span data-stu-id="12647-164">The **ComputerName** parameter specifies the computer names in the `$Servers` variable.</span></span>

### <span data-ttu-id="12647-165">Пример 8. использование свойства Path для получения форматированных имен путей</span><span class="sxs-lookup"><span data-stu-id="12647-165">Example 8: Use the Path property to get formatted path names</span></span>

<span data-ttu-id="12647-166">В этом примере используется свойство **path** набора счетчиков, чтобы найти отформатированные имена путей для счетчиков производительности.</span><span class="sxs-lookup"><span data-stu-id="12647-166">This example uses the **Path** property of a counter set to find the formatted path names for the performance counters.</span></span>

<span data-ttu-id="12647-167">Конвейер используется с `Where-Object` командлетом для поиска подмножества имен путей.</span><span class="sxs-lookup"><span data-stu-id="12647-167">The pipeline is used with the `Where-Object` cmdlet to find a subset of the path names.</span></span> <span data-ttu-id="12647-168">Чтобы найти набор счетчиков полный список путей к счетчикам, удалите конвейер ( `|` ) и `Where-Object` команду.</span><span class="sxs-lookup"><span data-stu-id="12647-168">To find a counter sets complete list of counter paths, remove the pipeline (`|`) and `Where-Object` command.</span></span>

<span data-ttu-id="12647-169">`$_`— Это автоматическая переменная для текущего объекта в конвейере.</span><span class="sxs-lookup"><span data-stu-id="12647-169">The `$_` is an automatic variable for the current object in the pipeline.</span></span>
<span data-ttu-id="12647-170">Дополнительные сведения см. в разделе [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="12647-170">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

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

<span data-ttu-id="12647-171">`Get-Counter` использует параметр **List** для указания набора счетчиков **памяти** .</span><span class="sxs-lookup"><span data-stu-id="12647-171">`Get-Counter` uses the **ListSet** parameter to specify the **Memory** counter set.</span></span> <span data-ttu-id="12647-172">Команда заключается в круглые скобки **, чтобы свойство** paths возвращало каждый путь в виде строки.</span><span class="sxs-lookup"><span data-stu-id="12647-172">The command is enclosed in parentheses so that the **Paths** property returns each path as a string.</span></span> <span data-ttu-id="12647-173">Объекты отправляются по конвейеру в `Where-Object` .</span><span class="sxs-lookup"><span data-stu-id="12647-173">The objects are sent down the pipeline to `Where-Object`.</span></span> <span data-ttu-id="12647-174">`Where-Object` использует переменную `$_` для обработки каждого объекта и использует `-like` оператор для поиска совпадений для строки `*Cache*` .</span><span class="sxs-lookup"><span data-stu-id="12647-174">`Where-Object` uses the variable `$_` to process each object and uses the `-like` operator to find matches for the string `*Cache*`.</span></span> <span data-ttu-id="12647-175">Звездочки () являются символами- `*` шаблонами для любых символов.</span><span class="sxs-lookup"><span data-stu-id="12647-175">The asterisks (`*`) are wildcards for any characters.</span></span>

### <span data-ttu-id="12647-176">Пример 9. использование свойства Пассвисинстанцес для получения форматированных имен путей</span><span class="sxs-lookup"><span data-stu-id="12647-176">Example 9: Use the PathsWithInstances property to get formatted path names</span></span>

<span data-ttu-id="12647-177">Этот пример возвращает отформатированные имена путей, которые включают экземпляры счетчиков производительности " **физический диск** ".</span><span class="sxs-lookup"><span data-stu-id="12647-177">This example gets the formatted path names that include the instances for the **PhysicalDisk** performance counters.</span></span>

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

<span data-ttu-id="12647-178">`Get-Counter` использует параметр **List** для указания набора счетчиков " **физический диск** ".</span><span class="sxs-lookup"><span data-stu-id="12647-178">`Get-Counter` uses the **ListSet** parameter to specify the **PhysicalDisk** counter set.</span></span> <span data-ttu-id="12647-179">Команда заключается в круглые скобки, чтобы свойство **пассвисинстанцес** возвращало каждый экземпляр пути в виде строки.</span><span class="sxs-lookup"><span data-stu-id="12647-179">The command is enclosed in parentheses so that the **PathsWithInstances** property returns each path instance as a string.</span></span>

### <span data-ttu-id="12647-180">Пример 10. получение одного значения для каждого счетчика в наборе счетчиков</span><span class="sxs-lookup"><span data-stu-id="12647-180">Example 10: Get a single value for each counter in a counter set</span></span>

<span data-ttu-id="12647-181">В этом примере возвращается одно значение для каждого счетчика производительности в наборе счетчиков **памяти** на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="12647-181">In this example, a single value is returned for each performance counter in the local computer's **Memory** counter set.</span></span>

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

<span data-ttu-id="12647-182">`Get-Counter` использует параметр **List** для указания набора счетчиков **памяти** .</span><span class="sxs-lookup"><span data-stu-id="12647-182">`Get-Counter` uses the **ListSet** parameter to specify the **Memory** counter set.</span></span> <span data-ttu-id="12647-183">Команда заключается в круглые скобки **, чтобы свойство** paths возвращало каждый путь в виде строки.</span><span class="sxs-lookup"><span data-stu-id="12647-183">The command is enclosed in parentheses so that the **Paths** property returns each path as a string.</span></span> <span data-ttu-id="12647-184">Пути хранятся в `$MemCounters` переменной.</span><span class="sxs-lookup"><span data-stu-id="12647-184">The paths are stored in the `$MemCounters` variable.</span></span> <span data-ttu-id="12647-185">`Get-Counter` использует параметр **Counter** для указания путей к счетчику в `$MemCounters` переменной.</span><span class="sxs-lookup"><span data-stu-id="12647-185">`Get-Counter` uses the **Counter** parameter to specify the counter paths in the `$MemCounters` variable.</span></span>

### <span data-ttu-id="12647-186">Пример 11. Отображение значений свойств объекта</span><span class="sxs-lookup"><span data-stu-id="12647-186">Example 11: Display an object's property values</span></span>

<span data-ttu-id="12647-187">Значения свойств в объекте **перформанцекаунтерсампле** представляют образец каждого из данных.</span><span class="sxs-lookup"><span data-stu-id="12647-187">The property values in the **PerformanceCounterSample** object represent each data sample.</span></span> <span data-ttu-id="12647-188">В этом примере мы используем свойства объекта **каунтерсамплес** для проверки, выбора, сортировки и группирования данных.</span><span class="sxs-lookup"><span data-stu-id="12647-188">In this example we use the properties of the **CounterSamples** object to examine, select, sort, and group the data.</span></span>

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

<span data-ttu-id="12647-189">Путь к счетчику хранится в `$Counter` переменной.</span><span class="sxs-lookup"><span data-stu-id="12647-189">The counter path is stored in the `$Counter` variable.</span></span> <span data-ttu-id="12647-190">`Get-Counter` Возвращает один образец значений счетчика и сохраняет результаты в `$Data` переменной.</span><span class="sxs-lookup"><span data-stu-id="12647-190">`Get-Counter` gets one sample of the counter values and stores the results in the `$Data` variable.</span></span> <span data-ttu-id="12647-191">`$Data`Переменная использует свойство **каунтерсамплес** для получения свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="12647-191">The `$Data` variable uses the **CounterSamples** property to get the object's properties.</span></span> <span data-ttu-id="12647-192">Объект отправляется по конвейеру в `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="12647-192">The object is sent down the pipeline to `Format-List`.</span></span> <span data-ttu-id="12647-193">Параметр **Property** использует `*` подстановочный знак звездочки () для выбора всех свойств.</span><span class="sxs-lookup"><span data-stu-id="12647-193">The **Property** parameter uses an asterisk (`*`) wildcard to select all the properties.</span></span>

### <span data-ttu-id="12647-194">Пример 12. значения массива счетчиков производительности</span><span class="sxs-lookup"><span data-stu-id="12647-194">Example 12: Performance counter array values</span></span>

<span data-ttu-id="12647-195">В этом примере переменная хранит каждый счетчик производительности.</span><span class="sxs-lookup"><span data-stu-id="12647-195">In this example, a variable stores each performance counter.</span></span> <span data-ttu-id="12647-196">Свойство **каунтерсамплес** — это массив, который может отображать определенные значения счетчика.</span><span class="sxs-lookup"><span data-stu-id="12647-196">The **CounterSamples** property is an array that can display specific counter values.</span></span>

<span data-ttu-id="12647-197">Для просмотра каждого образца счетчика используйте `$Counter.CounterSamples` .</span><span class="sxs-lookup"><span data-stu-id="12647-197">To display each counter sample, use `$Counter.CounterSamples`.</span></span>

```powershell
$Counter = Get-Counter -Counter "\Processor(*)\% Processor Time"
$Counter.CounterSamples[0]
```

```Output
Path                                         InstanceName        CookedValue
----                                         ------------        -----------
\\Computer01\processor(0)\% processor time   0              1.33997091699662
```

<span data-ttu-id="12647-198">`Get-Counter` использует параметр **Counter** для указания счетчика `\Processor(*)\% Processor Time` .</span><span class="sxs-lookup"><span data-stu-id="12647-198">`Get-Counter` uses the **Counter** parameter to specify the counter `\Processor(*)\% Processor Time`.</span></span> <span data-ttu-id="12647-199">Значения хранятся в `$Counter` переменной.</span><span class="sxs-lookup"><span data-stu-id="12647-199">The values are stored in the `$Counter` variable.</span></span>
<span data-ttu-id="12647-200">`$Counter.CounterSamples[0]` Отображает значение массива для первого значения счетчика.</span><span class="sxs-lookup"><span data-stu-id="12647-200">`$Counter.CounterSamples[0]` displays the array value for the first counter value.</span></span>

### <span data-ttu-id="12647-201">Пример 13. Сравнение значений счетчиков производительности</span><span class="sxs-lookup"><span data-stu-id="12647-201">Example 13: Compare performance counter values</span></span>

<span data-ttu-id="12647-202">Этот пример находит количество процессорного времени, используемого каждым процессором на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="12647-202">This example finds the amount of processor time used by each processor on the local computer.</span></span> <span data-ttu-id="12647-203">Свойство **каунтерсамплес** используется для сравнения данных счетчика с указанным значением.</span><span class="sxs-lookup"><span data-stu-id="12647-203">The **CounterSamples** property is used to compare the counter data against a specified value.</span></span>

<span data-ttu-id="12647-204">Для просмотра каждого образца счетчика используйте `$Counter.CounterSamples` .</span><span class="sxs-lookup"><span data-stu-id="12647-204">To display each counter sample, use `$Counter.CounterSamples`.</span></span>

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

<span data-ttu-id="12647-205">`Get-Counter` использует параметр **Counter** для указания счетчика `\Processor(*)\% Processor Time` .</span><span class="sxs-lookup"><span data-stu-id="12647-205">`Get-Counter` uses the **Counter** parameter to specify the counter `\Processor(*)\% Processor Time`.</span></span> <span data-ttu-id="12647-206">Значения хранятся в `$Counter` переменной.</span><span class="sxs-lookup"><span data-stu-id="12647-206">The values are stored in the `$Counter` variable.</span></span> <span data-ttu-id="12647-207">Объекты, хранящиеся в `$Counter.CounterSamples` , отправляются по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="12647-207">The objects stored in `$Counter.CounterSamples` are sent down the pipeline.</span></span> <span data-ttu-id="12647-208">`Where-Object` использует блок скрипта для сравнения значения каждого объекта с указанным значением 20.</span><span class="sxs-lookup"><span data-stu-id="12647-208">`Where-Object` uses a script block to compare each objects value against a specified value of 20.</span></span> <span data-ttu-id="12647-209">`$_.CookedValue`— Это переменная для текущего объекта в конвейере.</span><span class="sxs-lookup"><span data-stu-id="12647-209">The `$_.CookedValue` is a variable for the current object in the pipeline.</span></span> <span data-ttu-id="12647-210">Отображаются счетчики с **кукедвалуе** меньше 20.</span><span class="sxs-lookup"><span data-stu-id="12647-210">Counters with a **CookedValue** that is less than 20 are displayed.</span></span>

### <span data-ttu-id="12647-211">Пример 14. Сортировка данных счетчика производительности</span><span class="sxs-lookup"><span data-stu-id="12647-211">Example 14: Sort performance counter data</span></span>

<span data-ttu-id="12647-212">В этом примере показано, как сортировать данные счетчиков производительности.</span><span class="sxs-lookup"><span data-stu-id="12647-212">This example shows how to sort performance counter data.</span></span> <span data-ttu-id="12647-213">В примере выполняется поиск процессов на компьютере, которые используют наибольшее время процессора во время выполнения примера.</span><span class="sxs-lookup"><span data-stu-id="12647-213">The example finds the processes on the computer that are using the most processor time during the sample.</span></span>

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

<span data-ttu-id="12647-214">`Get-Counter` использует параметр **Counter** , чтобы указать `\Process(*)\% Processor Time` Счетчик для всех процессов на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="12647-214">`Get-Counter` uses the **Counter** parameter to specify the `\Process(*)\% Processor Time` counter for all the processes on the local computer.</span></span> <span data-ttu-id="12647-215">Результат сохраняется в `$Procs` переменной.</span><span class="sxs-lookup"><span data-stu-id="12647-215">The result is stored in the `$Procs` variable.</span></span> <span data-ttu-id="12647-216">`$Procs`Переменная со свойством **каунтерсамплес** отправляет объекты **перформанцекаунтерсампле** вниз по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="12647-216">The `$Procs` variable with the **CounterSamples** property sends the **PerformanceCounterSample** objects down the pipeline.</span></span> <span data-ttu-id="12647-217">`Sort-Object` использует параметр **Property** для сортировки объектов по **Кукедвалуе** в порядке **убывания** .</span><span class="sxs-lookup"><span data-stu-id="12647-217">`Sort-Object` uses the **Property** parameter to sort the objects by **CookedValue** in **Descending** order.</span></span> <span data-ttu-id="12647-218">`Format-Table` использует параметр **Property** для выбора столбцов для выходных данных.</span><span class="sxs-lookup"><span data-stu-id="12647-218">`Format-Table` uses the **Property** parameter to select the columns for the output.</span></span> <span data-ttu-id="12647-219">Параметр **AutoSize** корректирует ширину столбцов для сокращения усечения.</span><span class="sxs-lookup"><span data-stu-id="12647-219">The **AutoSize** parameter adjusts the column widths to minimize truncation.</span></span>

## <span data-ttu-id="12647-220">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="12647-220">PARAMETERS</span></span>

### <span data-ttu-id="12647-221">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="12647-221">-ComputerName</span></span>

<span data-ttu-id="12647-222">Указывает одно имя компьютера или разделенный запятыми массив имен **удаленных** компьютеров.</span><span class="sxs-lookup"><span data-stu-id="12647-222">Specifies one computer name or a comma-separated array of **remote** computer names.</span></span> <span data-ttu-id="12647-223">Используйте имя NetBIOS, IP-адрес или полное доменное имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="12647-223">Use the NetBIOS name, an IP address, or the computer's fully qualified domain name.</span></span>

<span data-ttu-id="12647-224">Чтобы получить данные счетчиков производительности с **локального** компьютера, исключите параметр **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="12647-224">To get performance counter data from the **local** computer, exclude the **ComputerName** parameter.</span></span>
<span data-ttu-id="12647-225">Для выходных данных, таких как **список** , содержащий столбец **MachineName** , точка ( `.` ) обозначает локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="12647-225">For output such as a **ListSet** that contains the **MachineName** column, a dot (`.`) indicates the local computer.</span></span>

<span data-ttu-id="12647-226">`Get-Counter` не зависит от удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12647-226">`Get-Counter` doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="12647-227">Параметр **ComputerName** можно использовать, даже если компьютер не настроен для выполнения удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="12647-227">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

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

### <span data-ttu-id="12647-228">-Continuous</span><span class="sxs-lookup"><span data-stu-id="12647-228">-Continuous</span></span>

<span data-ttu-id="12647-229">Если указан параметр **Continuous** , `Get-Counter` получает выборки до нажатия клавиши <kbd>CTRL</kbd> + <kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="12647-229">When the **Continuous** is specified, `Get-Counter` gets samples until you press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span> <span data-ttu-id="12647-230">Выборки получаются каждую секунду для каждого указанного счетчика производительности.</span><span class="sxs-lookup"><span data-stu-id="12647-230">Samples are obtained every second for each specified performance counter.</span></span> <span data-ttu-id="12647-231">Используйте параметр **SampleInterval** , чтобы увеличить интервал между непрерывными примерами.</span><span class="sxs-lookup"><span data-stu-id="12647-231">Use the **SampleInterval** parameter to increase the interval between continuous samples.</span></span>

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

### <span data-ttu-id="12647-232">-Counter</span><span class="sxs-lookup"><span data-stu-id="12647-232">-Counter</span></span>

<span data-ttu-id="12647-233">Указывает путь к одному или нескольким путям счетчиков.</span><span class="sxs-lookup"><span data-stu-id="12647-233">Specifies the path to one or more counter paths.</span></span> <span data-ttu-id="12647-234">Пути являются входными данными в виде массива с разделителями-запятыми, переменной или значений из текстового файла.</span><span class="sxs-lookup"><span data-stu-id="12647-234">Paths are input as a comma-separated array, a variable, or values from a text file.</span></span> <span data-ttu-id="12647-235">Строки пути счетчика можно отправить по конвейеру в `Get-Counter` .</span><span class="sxs-lookup"><span data-stu-id="12647-235">You can send counter path strings down the pipeline to `Get-Counter`.</span></span>

<span data-ttu-id="12647-236">Пути счетчиков используют следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="12647-236">Counter paths use the following syntax:</span></span>

`\\ComputerName\CounterSet(Instance)\CounterName`

`\CounterSet(Instance)\CounterName`

<span data-ttu-id="12647-237">Пример:</span><span class="sxs-lookup"><span data-stu-id="12647-237">For example:</span></span>

`\\Server01\Processor(*)\% User Time`

`\Processor(*)\% User Time`

<span data-ttu-id="12647-238">Параметр `\\ComputerName` является необязательным в пути счетчика производительности.</span><span class="sxs-lookup"><span data-stu-id="12647-238">The `\\ComputerName` is optional in a performance counter path.</span></span> <span data-ttu-id="12647-239">Если путь счетчика не содержит имя компьютера, `Get-Counter` использует локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="12647-239">If the counter path doesn't include the computer name, `Get-Counter` uses the local computer.</span></span>

<span data-ttu-id="12647-240">Звездочка ( `*` ) в экземпляре является символом-шаблоном для получения всех экземпляров счетчика.</span><span class="sxs-lookup"><span data-stu-id="12647-240">An asterisk (`*`) in the instance is a wildcard character to get all instances of the counter.</span></span>

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

### <span data-ttu-id="12647-241">— Список</span><span class="sxs-lookup"><span data-stu-id="12647-241">-ListSet</span></span>

<span data-ttu-id="12647-242">Список наборов счетчиков производительности на компьютерах.</span><span class="sxs-lookup"><span data-stu-id="12647-242">Lists the performance counter sets on the computers.</span></span> <span data-ttu-id="12647-243">`*`Для указания всех наборов счетчиков используйте звездочку ().</span><span class="sxs-lookup"><span data-stu-id="12647-243">Use an asterisk (`*`) to specify all counter sets.</span></span> <span data-ttu-id="12647-244">Введите одно имя или строку с разделителями-запятыми в именах наборов счетчиков.</span><span class="sxs-lookup"><span data-stu-id="12647-244">Enter one name or a comma-separated string of counter set names.</span></span> <span data-ttu-id="12647-245">Имена наборов счетчиков можно отправить по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="12647-245">You can send counter set names down the pipeline.</span></span>

<span data-ttu-id="12647-246">Чтобы получить наборы счетчиков с отформатированными путями счетчиков, используйте параметр **List** .</span><span class="sxs-lookup"><span data-stu-id="12647-246">To get a counter sets formatted counter paths, use the **ListSet** parameter.</span></span> <span data-ttu-id="12647-247">Свойства **paths** и **пассвисинстанцес** каждого набора счетчиков содержат отдельные пути счетчиков, отформатированные в виде строки.</span><span class="sxs-lookup"><span data-stu-id="12647-247">The **Paths** and **PathsWithInstances** properties of each counter set contain the individual counter paths formatted as a string.</span></span>

<span data-ttu-id="12647-248">Можно сохранить строки пути счетчика в переменной или использовать конвейер для отправки строки другой `Get-Counter` команде.</span><span class="sxs-lookup"><span data-stu-id="12647-248">You can save the counter path strings in a variable or use the pipeline to send the string to another `Get-Counter` command.</span></span>

<span data-ttu-id="12647-249">Например, для отправки каждого пути счетчика **процессора** в `Get-Counter` :</span><span class="sxs-lookup"><span data-stu-id="12647-249">For example to send each **Processor** counter path to `Get-Counter`:</span></span>

`Get-Counter -ListSet Processor | Get-Counter`

> [!NOTE]
> <span data-ttu-id="12647-250">В PowerShell 7 `Get-Counter` не удается получить свойство **Description** набора счетчиков.</span><span class="sxs-lookup"><span data-stu-id="12647-250">In PowerShell 7, `Get-Counter` can't retrieve the **Description** property of the counter set.</span></span> <span data-ttu-id="12647-251">**Описание** имеет значение `$null` .</span><span class="sxs-lookup"><span data-stu-id="12647-251">The **Description** is set to `$null`.</span></span>

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

### <span data-ttu-id="12647-252">-Макссамплес</span><span class="sxs-lookup"><span data-stu-id="12647-252">-MaxSamples</span></span>

<span data-ttu-id="12647-253">Указывает число выборок, получаемых из каждого указанного счетчика производительности.</span><span class="sxs-lookup"><span data-stu-id="12647-253">Specifies the number of samples to get from each specified performance counter.</span></span> <span data-ttu-id="12647-254">Чтобы получить постоянный поток образцов, используйте параметр **Continuous** .</span><span class="sxs-lookup"><span data-stu-id="12647-254">To get a constant stream of samples, use the **Continuous** parameter.</span></span>

<span data-ttu-id="12647-255">Если параметр **макссамплес** не указан, `Get-Counter` получает только один выборку для каждого указанного счетчика.</span><span class="sxs-lookup"><span data-stu-id="12647-255">If the **MaxSamples** parameter isn't specified, `Get-Counter` only gets one sample for each specified counter.</span></span>

<span data-ttu-id="12647-256">Чтобы получить большой набор данных, выполните в `Get-Counter` качестве фонового задания PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12647-256">To collect a large data set, run `Get-Counter` as a PowerShell background job.</span></span> <span data-ttu-id="12647-257">См. дополнительные сведения о [заданиях](../Microsoft.PowerShell.Core/About/about_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="12647-257">For more information, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md).</span></span>

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

### <span data-ttu-id="12647-258">-SampleInterval</span><span class="sxs-lookup"><span data-stu-id="12647-258">-SampleInterval</span></span>

<span data-ttu-id="12647-259">Указывает количество секунд между выборками для каждого указанного счетчика производительности.</span><span class="sxs-lookup"><span data-stu-id="12647-259">Specifies the number of seconds between samples for each specified performance counter.</span></span> <span data-ttu-id="12647-260">Если параметр **SampleInterval** не указан, `Get-Counter` используется интервал в 1 секунду.</span><span class="sxs-lookup"><span data-stu-id="12647-260">If the **SampleInterval** parameter isn't specified, `Get-Counter` uses a one-second interval.</span></span>

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

### <span data-ttu-id="12647-261">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="12647-261">CommonParameters</span></span>

<span data-ttu-id="12647-262">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="12647-262">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="12647-263">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="12647-263">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="12647-264">Входные данные</span><span class="sxs-lookup"><span data-stu-id="12647-264">INPUTS</span></span>

### <span data-ttu-id="12647-265">System.String[]</span><span class="sxs-lookup"><span data-stu-id="12647-265">System.String[]</span></span>

<span data-ttu-id="12647-266">`Get-Counter` принимает входные данные конвейера для путей счетчиков и имен наборов счетчиков.</span><span class="sxs-lookup"><span data-stu-id="12647-266">`Get-Counter` accepts pipeline input for counter paths and counter set names.</span></span>

## <span data-ttu-id="12647-267">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="12647-267">OUTPUTS</span></span>

### <span data-ttu-id="12647-268">Microsoft. PowerShell. Commands. NOCOUNT. Counters, Microsoft. PowerShell. Commands. NOCOUNT. PerformanceCounterSampleSet, Microsoft. PowerShell. Commands. NOCOUNT. Перформанцекаунтерсампле</span><span class="sxs-lookup"><span data-stu-id="12647-268">Microsoft.PowerShell.Commands.GetCounter.CounterSet, Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet, Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSample</span></span>

<span data-ttu-id="12647-269">Чтобы просмотреть свойства объекта, отправьте выходные данные по конвейеру в `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="12647-269">To view an object's properties, send the output down the pipeline to `Get-Member`.</span></span> <span data-ttu-id="12647-270">Ниже приведены типы объектов, которые являются выходными данными.</span><span class="sxs-lookup"><span data-stu-id="12647-270">The object types that are output are as follows:</span></span>

<span data-ttu-id="12647-271">**Параметр CounterSet** : **Microsoft. PowerShell. Commands. NOCOUNT. CounterSet**</span><span class="sxs-lookup"><span data-stu-id="12647-271">**ListSet** parameter: **Microsoft.PowerShell.Commands.GetCounter.CounterSet**</span></span>

<span data-ttu-id="12647-272">Параметр **счетчика** : **Microsoft. PowerShell. Commands. NOCOUNT. PerformanceCounterSampleSet**</span><span class="sxs-lookup"><span data-stu-id="12647-272">**Counter** parameter: **Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSampleSet**</span></span>

<span data-ttu-id="12647-273">Свойство **каунтерсамплес** : **Microsoft. PowerShell. Commands. NOCOUNT. перформанцекаунтерсампле**</span><span class="sxs-lookup"><span data-stu-id="12647-273">**CounterSamples** property: **Microsoft.PowerShell.Commands.GetCounter.PerformanceCounterSample**</span></span>

## <span data-ttu-id="12647-274">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="12647-274">NOTES</span></span>

<span data-ttu-id="12647-275">Если параметры не указаны, `Get-Counter` получает один выборку для каждого указанного счетчика производительности.</span><span class="sxs-lookup"><span data-stu-id="12647-275">If no parameters are specified, `Get-Counter` gets one sample for each specified performance counter.</span></span> <span data-ttu-id="12647-276">Используйте параметры **макссамплес** и **Continuous** для получения дополнительных образцов.</span><span class="sxs-lookup"><span data-stu-id="12647-276">Use the **MaxSamples** and **Continuous** parameters to get more samples.</span></span>

<span data-ttu-id="12647-277">`Get-Counter` использует интервал в 1 секунду между образцами.</span><span class="sxs-lookup"><span data-stu-id="12647-277">`Get-Counter` uses a one-second interval between samples.</span></span> <span data-ttu-id="12647-278">Чтобы увеличить интервал, используйте параметр **SampleInterval** .</span><span class="sxs-lookup"><span data-stu-id="12647-278">Use the **SampleInterval** parameter to increase the interval.</span></span>

<span data-ttu-id="12647-279">Значения **макссамплес** и **SampleInterval** применяются ко всем счетчикам на каждом компьютере в команде.</span><span class="sxs-lookup"><span data-stu-id="12647-279">The **MaxSamples** and **SampleInterval** values apply to all the counters on each computer in the command.</span></span> <span data-ttu-id="12647-280">Чтобы задать различные значения для разных счетчиков, введите отдельные `Get-Counter` команды.</span><span class="sxs-lookup"><span data-stu-id="12647-280">To set different values for different counters, enter separate `Get-Counter` commands.</span></span>

<span data-ttu-id="12647-281">В PowerShell 7 при использовании параметра **List** `Get-Counter` не может получить свойство **Description** набора счетчиков.</span><span class="sxs-lookup"><span data-stu-id="12647-281">In PowerShell 7, when using the **ListSet** parameter, `Get-Counter` can't retrieve the **Description** property of the counter set.</span></span> <span data-ttu-id="12647-282">**Описание** имеет значение `$null` .</span><span class="sxs-lookup"><span data-stu-id="12647-282">The **Description** is set to `$null`.</span></span>

## <span data-ttu-id="12647-283">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="12647-283">RELATED LINKS</span></span>

[<span data-ttu-id="12647-284">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="12647-284">about_Automatic_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="12647-285">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="12647-285">about_Jobs</span></span>](../Microsoft.PowerShell.Core/About/about_Jobs.md)

[<span data-ttu-id="12647-286">Format-List</span><span class="sxs-lookup"><span data-stu-id="12647-286">Format-List</span></span>](../Microsoft.PowerShell.Utility/Format-List.md)

[<span data-ttu-id="12647-287">Format-Table</span><span class="sxs-lookup"><span data-stu-id="12647-287">Format-Table</span></span>](../Microsoft.PowerShell.Utility/Format-Table.md)

[<span data-ttu-id="12647-288">Get-Member</span><span class="sxs-lookup"><span data-stu-id="12647-288">Get-Member</span></span>](../Microsoft.PowerShell.Utility/Get-Member.md)

[<span data-ttu-id="12647-289">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="12647-289">Receive-Job</span></span>](../Microsoft.PowerShell.Core/Receive-Job.md)

[<span data-ttu-id="12647-290">Start-Job</span><span class="sxs-lookup"><span data-stu-id="12647-290">Start-Job</span></span>](../Microsoft.PowerShell.Core/Start-Job.md)

[<span data-ttu-id="12647-291">Where-Object</span><span class="sxs-lookup"><span data-stu-id="12647-291">Where-Object</span></span>](..//Microsoft.PowerShell.Core/Where-Object.md)

