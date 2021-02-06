---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/sort-object?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Sort-Object
ms.openlocfilehash: fead3b3d109a79186bc82f3c9f212f11f7b0bc57
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604357"
---
# <span data-ttu-id="50607-102">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="50607-102">Sort-Object</span></span>

## <span data-ttu-id="50607-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="50607-103">SYNOPSIS</span></span>
<span data-ttu-id="50607-104">Сортирует объекты по значениям свойств.</span><span class="sxs-lookup"><span data-stu-id="50607-104">Sorts objects by property values.</span></span>

## <span data-ttu-id="50607-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="50607-105">SYNTAX</span></span>

### <span data-ttu-id="50607-106">Default (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="50607-106">Default (Default)</span></span>

```
Sort-Object [-Stable] [-Descending] [-Unique] [-InputObject <PSObject>] [[-Property] <Object[]>]
 [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

### <span data-ttu-id="50607-107">TOP</span><span class="sxs-lookup"><span data-stu-id="50607-107">Top</span></span>

```
Sort-Object [-Descending] [-Unique] -Top <Int32> [-InputObject <PSObject>] [[-Property] <Object[]>]
 [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

### <span data-ttu-id="50607-108">Нижнее</span><span class="sxs-lookup"><span data-stu-id="50607-108">Bottom</span></span>

```
Sort-Object [-Descending] [-Unique] -Bottom <Int32> [-InputObject <PSObject>] [[-Property] <Object[]>]
 [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

## <span data-ttu-id="50607-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="50607-109">DESCRIPTION</span></span>

<span data-ttu-id="50607-110">`Sort-Object`Командлет сортирует объекты в возрастающем или убывающем порядке на основе значений свойств объектов.</span><span class="sxs-lookup"><span data-stu-id="50607-110">The `Sort-Object` cmdlet sorts objects in ascending or descending order based on object property values.</span></span> <span data-ttu-id="50607-111">Если свойства сортировки не включены в команду, PowerShell использует свойства сортировки по умолчанию первого входного объекта.</span><span class="sxs-lookup"><span data-stu-id="50607-111">If sort properties are not included in a command, PowerShell uses default sort properties of the first input object.</span></span> <span data-ttu-id="50607-112">Если тип входного объекта не имеет свойств сортировки по умолчанию, PowerShell пытается сравнить сами объекты.</span><span class="sxs-lookup"><span data-stu-id="50607-112">If the type of the input object has no default sort properties, PowerShell attempts to compare the objects themselves.</span></span> <span data-ttu-id="50607-113">Дополнительные сведения см. в разделе " [Примечания](#notes) ".</span><span class="sxs-lookup"><span data-stu-id="50607-113">For more information, see the [Notes](#notes) section.</span></span>

<span data-ttu-id="50607-114">Объекты можно сортировать по отдельному свойству или нескольким свойствам.</span><span class="sxs-lookup"><span data-stu-id="50607-114">You can sort objects by a single property or multiple properties.</span></span> <span data-ttu-id="50607-115">Несколько свойств используют хэш-таблицы для сортировки в возрастающем порядке, по убыванию или в сочетании порядка сортировки.</span><span class="sxs-lookup"><span data-stu-id="50607-115">Multiple properties use hash tables to sort in ascending order, descending order, or a combination of sort orders.</span></span> <span data-ttu-id="50607-116">Свойства сортируются с учетом регистра или без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="50607-116">Properties are sorted as case-sensitive or case-insensitive.</span></span> <span data-ttu-id="50607-117">Используйте параметр **UNIQUE** , чтобы исключить дубликаты из выходных данных.</span><span class="sxs-lookup"><span data-stu-id="50607-117">Use the **Unique** parameter to eliminate duplicates from the output.</span></span>

## <span data-ttu-id="50607-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="50607-118">EXAMPLES</span></span>

### <span data-ttu-id="50607-119">Пример 1. Сортировка текущего каталога по имени</span><span class="sxs-lookup"><span data-stu-id="50607-119">Example 1: Sort the current directory by name</span></span>

<span data-ttu-id="50607-120">В этом примере выполняется сортировка файлов и подкаталогов в каталоге.</span><span class="sxs-lookup"><span data-stu-id="50607-120">This example sorts the files and subdirectories in a directory.</span></span>

```
PS> Get-ChildItem -Path C:\Test | Sort-Object

    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/13/2019     13:26             20 Bfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-a----         2/1/2019     08:43            183 CreateTestFile.ps1
d-----        2/25/2019     18:25                Files
d-----        2/25/2019     18:24                Logs
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
-a----        2/12/2019     16:24             23 Zsystemlog.log
```

<span data-ttu-id="50607-121">`Get-ChildItem`Командлет получает файлы и подкаталоги из каталога, указанного параметром **path** , **C:\test**.</span><span class="sxs-lookup"><span data-stu-id="50607-121">The `Get-ChildItem` cmdlet gets the files and subdirectories from the directory specified by the **Path** parameter, **C:\Test**.</span></span> <span data-ttu-id="50607-122">Объекты отправляются по конвейеру в `Sort-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="50607-122">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span>
<span data-ttu-id="50607-123">`Sort-Object` не указывает свойство, поэтому выходные данные сортируются по свойству Sort по умолчанию, **Name**.</span><span class="sxs-lookup"><span data-stu-id="50607-123">`Sort-Object` does not specify a property so the output is sorted by the default sort property, **Name**.</span></span>

### <span data-ttu-id="50607-124">Пример 2. Сортировка текущего каталога по длине файла</span><span class="sxs-lookup"><span data-stu-id="50607-124">Example 2: Sort the current directory by file length</span></span>

<span data-ttu-id="50607-125">Эта команда отображает файлы в текущем каталоге по длине в порядке возрастания.</span><span class="sxs-lookup"><span data-stu-id="50607-125">This command displays the files in the current directory by length in ascending order.</span></span>

```
PS> Get-ChildItem -Path C:\Test -File | Sort-Object -Property Length

    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     13:26             20 Bfile.txt
-a----        2/12/2019     16:24             23 Zsystemlog.log
-a----        2/13/2019     08:55             26 anotherfile.txt
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
-a----         2/1/2019     08:43            183 CreateTestFile.ps1
-a----        2/12/2019     15:40         118014 Command.txt
```

<span data-ttu-id="50607-126">`Get-ChildItem`Командлет получает файлы из каталога, указанного параметром **path** .</span><span class="sxs-lookup"><span data-stu-id="50607-126">The `Get-ChildItem` cmdlet gets the files from the directory specified by the **Path** parameter.</span></span>
<span data-ttu-id="50607-127">Параметр **File** указывает, что `Get-ChildItem` только получает объекты File.</span><span class="sxs-lookup"><span data-stu-id="50607-127">The **File** parameter specifies that `Get-ChildItem` only gets file objects.</span></span> <span data-ttu-id="50607-128">Объекты отправляются по конвейеру в `Sort-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="50607-128">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="50607-129">`Sort-Object` использует параметр **length** для сортировки файлов по длине в порядке возрастания.</span><span class="sxs-lookup"><span data-stu-id="50607-129">`Sort-Object` uses the **Length** parameter to sort the files by length in ascending order.</span></span>

### <span data-ttu-id="50607-130">Пример 3. Сортировка процессов по использованию памяти</span><span class="sxs-lookup"><span data-stu-id="50607-130">Example 3: Sort processes by memory usage</span></span>

<span data-ttu-id="50607-131">В этом примере отображаются процессы с наибольшим использованием памяти в зависимости от размера рабочего множества (WS).</span><span class="sxs-lookup"><span data-stu-id="50607-131">This example displays processes with the highest memory usage based on their working set (WS) size.</span></span>

```
PS> Get-Process | Sort-Object -Property WS | Select-Object -Last 5

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    136   193.92     217.11     889.16   87492   8 OUTLOOK
    112   347.73     297.02      95.19  106908   8 Teams
    206   266.54     323.71      37.17   60620   8 MicrosoftEdgeCP
     35   552.19     549.94     131.66    6552   8 Code
      0     1.43     595.12       0.00    2780   0 Memory Compression
```

<span data-ttu-id="50607-132">`Get-Process`Командлет возвращает список процессов, запущенных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="50607-132">The `Get-Process` cmdlet gets the list of processes running on the computer.</span></span> <span data-ttu-id="50607-133">Объекты процесса отправляются по конвейеру в `Sort-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="50607-133">The process objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="50607-134">`Sort-Object` использует параметр **Property** для сортировки объектов по протоколу **WS**.</span><span class="sxs-lookup"><span data-stu-id="50607-134">`Sort-Object` uses the **Property** parameter to sort the objects by **WS**.</span></span> <span data-ttu-id="50607-135">Объекты отправляются по конвейеру в `Select-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="50607-135">The objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span>
<span data-ttu-id="50607-136">`Select-Object` использует **последний** параметр для указания последних пяти объектов, которые являются объектами с наибольшим использованием **WS** .</span><span class="sxs-lookup"><span data-stu-id="50607-136">`Select-Object` uses the **Last** parameter to specify the last five objects, which are the objects with the highest **WS** usage.</span></span>

<span data-ttu-id="50607-137">В PowerShell 6 `Sort-Object` параметр **Bottom** является альтернативой для `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="50607-137">In PowerShell 6, the `Sort-Object` parameter **Bottom** is an alternative to `Select-Object`.</span></span> <span data-ttu-id="50607-138">Пример: `Get-Process | Sort-Object -Property WS -Bottom 5`.</span><span class="sxs-lookup"><span data-stu-id="50607-138">For example, `Get-Process | Sort-Object -Property WS -Bottom 5`.</span></span>

### <span data-ttu-id="50607-139">Пример 4. Сортировка объектов Хисторинфо по идентификатору</span><span class="sxs-lookup"><span data-stu-id="50607-139">Example 4: Sort HistoryInfo objects by Id</span></span>

<span data-ttu-id="50607-140">Эта команда сортирует объекты **хисторинфо** сеанса PowerShell с помощью свойства **ID** .</span><span class="sxs-lookup"><span data-stu-id="50607-140">This command sorts the PowerShell session's **HistoryInfo** objects using the **Id** property.</span></span> <span data-ttu-id="50607-141">Каждый сеанс PowerShell имеет собственный журнал команд.</span><span class="sxs-lookup"><span data-stu-id="50607-141">Each PowerShell session has its own command history.</span></span>

```
PS> Get-History | Sort-Object -Property Id -Descending

  Id CommandLine
  -- -----------
  10 Get-Command Sort-Object -Syntax
   9 $PSVersionTable
   8 Get-Command Sort-Object -Syntax
   7 Get-Command Sort-Object -ShowCommandInfo
   6 Get-ChildItem -Path C:\Test | Sort-Object -Property Length
   5 Get-Help Clear-History -online
   4 Get-Help Clear-History -full
   3 Get-ChildItem | Get-Member
   2 Get-Command Sort-Object -Syntax
   1 Set-Location C:\Test\
```

<span data-ttu-id="50607-142">`Get-History`Командлет получает объекты журнала из текущего сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50607-142">The `Get-History` cmdlet gets the history objects from the current PowerShell session.</span></span> <span data-ttu-id="50607-143">Объекты отправляются по конвейеру в `Sort-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="50607-143">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="50607-144">`Sort-Object` использует параметр **Property** для сортировки объектов по **идентификатору**. Параметр **Descending** сортирует журнал команд от новых к старым.</span><span class="sxs-lookup"><span data-stu-id="50607-144">`Sort-Object` uses the **Property** parameter to sort the objects by **Id**. The **Descending** parameter sorts the command history from newest to oldest.</span></span>

### <span data-ttu-id="50607-145">Пример 5. Использование хэш-таблицы для сортировки свойств в порядке возрастания и убывания</span><span class="sxs-lookup"><span data-stu-id="50607-145">Example 5: Use a hash table to sort properties in ascending and descending order</span></span>

<span data-ttu-id="50607-146">В этом примере используются два свойства для сортировки объектов, **Status** и **DisplayName**.</span><span class="sxs-lookup"><span data-stu-id="50607-146">This example uses two properties to sort the objects, **Status** and **DisplayName**.</span></span> <span data-ttu-id="50607-147">**Состояние** сортируется в убывающем порядке, а **DisplayName** — по возрастанию.</span><span class="sxs-lookup"><span data-stu-id="50607-147">**Status** is sorted in descending order and **DisplayName** is sorted in ascending order.</span></span>

<span data-ttu-id="50607-148">Хэш-таблица используется для указания значения параметра **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="50607-148">A hash table is used to specify the **Property** parameter's value.</span></span> <span data-ttu-id="50607-149">Хэш-таблица использует выражение для указания имен свойств и порядка сортировки.</span><span class="sxs-lookup"><span data-stu-id="50607-149">The hash table uses an expression to specify the property names and sort orders.</span></span> <span data-ttu-id="50607-150">Дополнительные сведения о хэш-таблицах см. [здесь](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span><span class="sxs-lookup"><span data-stu-id="50607-150">For more information about hash tables, see [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span></span>

<span data-ttu-id="50607-151">Свойство **Status** , используемое в хэш-таблице, является перечислимым свойством.</span><span class="sxs-lookup"><span data-stu-id="50607-151">The **Status** property used in the hash table is an enumerated property.</span></span>
<span data-ttu-id="50607-152">Дополнительные сведения см. в разделе [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span><span class="sxs-lookup"><span data-stu-id="50607-152">For more information, see [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span></span>

```
PS C:\> Get-Service | Sort-Object -Property @{Expression = "Status"; Descending = $True}, @{Expression = "DisplayName"; Descending = $False}

Status   Name               DisplayName
------   ----               -----------
Running  Appinfo            Application Information
Running  BthAvctpSvc        AVCTP service
Running  BrokerInfrastru... Background Tasks Infrastructure Ser...
Running  BDESVC             BitLocker Drive Encryption Service
Running  CoreMessagingRe... CoreMessaging
Running  VaultSvc           Credential Manager
Running  DsSvc              Data Sharing Service
Running  Dhcp               DHCP Client
...
Stopped  ALG                Application Layer Gateway Service
Stopped  AppMgmt            Application Management
Stopped  BITS               Background Intelligent Transfer Ser...
Stopped  wbengine           Block Level Backup Engine Service
Stopped  BluetoothUserSe... Bluetooth User Support Service_14fb...
Stopped  COMSysApp          COM+ System Application
Stopped  smstsmgr           ConfigMgr Task Sequence Agent
Stopped  DeviceInstall      Device Install Service
Stopped  MSDTC              Distributed Transaction Coordinator
```

<span data-ttu-id="50607-153">`Get-Service`Командлет возвращает список служб на компьютере.</span><span class="sxs-lookup"><span data-stu-id="50607-153">The `Get-Service` cmdlet gets the list of services on the computer.</span></span> <span data-ttu-id="50607-154">Объекты службы отправляются по конвейеру в `Sort-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="50607-154">The service objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="50607-155">`Sort-Object` использует параметр **Property** с хэш-таблицей для указания имен свойств и порядка сортировки.</span><span class="sxs-lookup"><span data-stu-id="50607-155">`Sort-Object` uses the **Property** parameter with a hash table to specify the property names and sort orders.</span></span> <span data-ttu-id="50607-156">Параметр **Свойства** сортируется по двум свойствам, **состояние** в убывающем порядке и **DisplayName** в возрастающем порядке.</span><span class="sxs-lookup"><span data-stu-id="50607-156">The **Property** parameter is sorted by two properties, **Status** in descending order and **DisplayName** in ascending order.</span></span>

<span data-ttu-id="50607-157">**Status** — это перечислимое свойство.</span><span class="sxs-lookup"><span data-stu-id="50607-157">**Status** is an enumerated property.</span></span> <span data-ttu-id="50607-158">Параметр **Stopped** имеет значение **1** , а его **выполнение** имеет значение **4**.</span><span class="sxs-lookup"><span data-stu-id="50607-158">**Stopped** has a value of **1** and **Running** has a value of **4**.</span></span> <span data-ttu-id="50607-159">Параметр **Descending** имеет значение, `$True` чтобы перед **остановленными** процессами отображались **выполняющиеся** процессы.</span><span class="sxs-lookup"><span data-stu-id="50607-159">The **Descending** parameter is set to `$True` so that **Running** processes are displayed before **Stopped** processes.</span></span> <span data-ttu-id="50607-160">**DisplayName** задает для параметра по **убыванию** значение, чтобы `$False` отсортировать отображаемые имена в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="50607-160">**DisplayName** sets the **Descending** parameter to `$False` to sort the display names in alphabetical order.</span></span>

### <span data-ttu-id="50607-161">Пример 6. сортировка текстовых файлов по периоду времени</span><span class="sxs-lookup"><span data-stu-id="50607-161">Example 6: Sort text files by time span</span></span>

<span data-ttu-id="50607-162">Эта команда сортирует текстовые файлы в порядке убывания интервала времени между **CreationTime** и **LastWriteTime**.</span><span class="sxs-lookup"><span data-stu-id="50607-162">This command sorts text files in descending order by the time span between **CreationTime** and **LastWriteTime**.</span></span>

```
PS> Get-ChildItem -Path C:\Test\*.txt | Sort-Object -Property @{Expression = {$_.CreationTime - $_.LastWriteTime}; Descending = $False} | Format-Table CreationTime, LastWriteTime, FullName

CreationTime          LastWriteTime        FullName
------------          -------------        --------
11/21/2018 12:39:01   2/26/2019 08:59:36   C:\Test\test2.txt
12/4/2018 08:29:41    2/26/2019 08:57:05   C:\Test\powershell_list.txt
2/20/2019 08:15:59    2/26/2019 12:09:43   C:\Test\CreateTestFile.txt
2/20/2019 08:15:59    2/26/2019 12:07:41   C:\Test\Command.txt
2/20/2019 08:15:59    2/26/2019 08:57:52   C:\Test\ReadOnlyFile.txt
11/29/2018 15:16:50   12/4/2018 16:16:24   C:\Test\LogData.txt
2/25/2019 18:25:11    2/26/2019 12:08:47   C:\Test\Zsystemlog.txt
2/25/2019 18:25:11    2/26/2019 08:55:33   C:\Test\Bfile.txt
2/26/2019 08:46:59    2/26/2019 12:12:19   C:\Test\LogFile3.txt
```

<span data-ttu-id="50607-163">`Get-ChildItem`Командлет использует параметр **path** для указания каталога **C:\test** и всех `*.txt` файлов.</span><span class="sxs-lookup"><span data-stu-id="50607-163">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory **C:\Test** and all of the `*.txt` files.</span></span> <span data-ttu-id="50607-164">Объекты отправляются по конвейеру в `Sort-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="50607-164">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span>
<span data-ttu-id="50607-165">`Sort-Object` использует параметр **Property** с хэш-таблицей для определения интервала времени каждого файла между **CreationTime** и **LastWriteTime**.</span><span class="sxs-lookup"><span data-stu-id="50607-165">`Sort-Object` uses the **Property** parameter with a hash table to determine each files time span between **CreationTime** and **LastWriteTime**.</span></span> <span data-ttu-id="50607-166">Параметр **Descending** имеет значение, чтобы `$False` Сортировать в порядке убывания к кратчайшему диапазону времени.</span><span class="sxs-lookup"><span data-stu-id="50607-166">The **Descending** parameter is set to `$False` to sort in the order of longest to shortest time span.</span></span>

### <span data-ttu-id="50607-167">Пример 7. Сортировка имен в текстовом файле</span><span class="sxs-lookup"><span data-stu-id="50607-167">Example 7: Sort names in a text file</span></span>

<span data-ttu-id="50607-168">В этом примере показано, как отсортировать список из текстового файла.</span><span class="sxs-lookup"><span data-stu-id="50607-168">This example shows how to sort a list from a text file.</span></span> <span data-ttu-id="50607-169">Исходный файл отображается в виде несортированного списка.</span><span class="sxs-lookup"><span data-stu-id="50607-169">The original file is displayed as an unsorted list.</span></span> <span data-ttu-id="50607-170">`Sort-Object` Сортирует содержимое, а затем сортирует содержимое с **уникальным** параметром, который удаляет дубликаты.</span><span class="sxs-lookup"><span data-stu-id="50607-170">`Sort-Object` sorts the contents and then sorts the contents with the **Unique** parameter that removes duplicates.</span></span>

```
PS> Get-Content -Path C:\Test\ServerNames.txt
localhost
server01
server25
LOCALHOST
Server19
server3
localhost

PS> Get-Content -Path C:\Test\ServerNames.txt | Sort-Object
localhost
LOCALHOST
localhost
server01
Server19
server25
server3

PS> Get-Content -Path C:\Test\ServerNames.txt | Sort-Object -Unique
localhost
server01
Server19
server25
server3
```

<span data-ttu-id="50607-171">`Get-Content`Командлет использует параметр **path** , чтобы указать каталог и имя файла.</span><span class="sxs-lookup"><span data-stu-id="50607-171">The `Get-Content` cmdlet uses the **Path** parameter to specify the directory and file name.</span></span> <span data-ttu-id="50607-172">Файл **ServerNames.txt** содержит Несортированный список имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="50607-172">The file **ServerNames.txt** contains an unsorted list of computer names.</span></span>

<span data-ttu-id="50607-173">`Get-Content`Командлет использует параметр **path** , чтобы указать каталог и имя файла.</span><span class="sxs-lookup"><span data-stu-id="50607-173">The `Get-Content` cmdlet uses the **Path** parameter to specify the directory and file name.</span></span> <span data-ttu-id="50607-174">Файл **ServerNames.txt** содержит Несортированный список имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="50607-174">The file **ServerNames.txt** contains an unsorted list of computer names.</span></span> <span data-ttu-id="50607-175">Объекты отправляются по конвейеру в `Sort-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="50607-175">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="50607-176">`Sort-Object` Сортирует список в порядке по умолчанию (по возрастанию).</span><span class="sxs-lookup"><span data-stu-id="50607-176">`Sort-Object` sorts the list in the default order, ascending.</span></span>

<span data-ttu-id="50607-177">`Get-Content`Командлет использует параметр **path** , чтобы указать каталог и имя файла.</span><span class="sxs-lookup"><span data-stu-id="50607-177">The `Get-Content` cmdlet uses the **Path** parameter to specify the directory and file name.</span></span> <span data-ttu-id="50607-178">Файл **ServerNames.txt** содержит Несортированный список имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="50607-178">The file **ServerNames.txt** contains an unsorted list of computer names.</span></span> <span data-ttu-id="50607-179">Объекты отправляются по конвейеру в `Sort-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="50607-179">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="50607-180">`Sort-Object` использует параметр **UNIQUE** для удаления повторяющихся имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="50607-180">`Sort-Object` uses the **Unique** parameter to remove duplicate computer names.</span></span> <span data-ttu-id="50607-181">Список сортируется в порядке по умолчанию (по возрастанию).</span><span class="sxs-lookup"><span data-stu-id="50607-181">The list is sorted in the default order, ascending.</span></span>

### <span data-ttu-id="50607-182">Пример 8. Сортировка строки в виде целого числа</span><span class="sxs-lookup"><span data-stu-id="50607-182">Example 8: Sort a string as an integer</span></span>

<span data-ttu-id="50607-183">В этом примере показано, как выполнить сортировку текстового файла, содержащего строковые объекты, в виде целых чисел.</span><span class="sxs-lookup"><span data-stu-id="50607-183">This example shows how to sort a text file that contains string objects as integers.</span></span> <span data-ttu-id="50607-184">Можно отправить каждую команду вниз по конвейеру в `Get-Member` и убедиться, что объекты являются строками, а не целыми числами.</span><span class="sxs-lookup"><span data-stu-id="50607-184">You can send each command down the pipeline to `Get-Member` and verify that the objects are strings instead of integers.</span></span> <span data-ttu-id="50607-185">В этих примерах `ProductId.txt` файл содержит Несортированный список номеров продуктов.</span><span class="sxs-lookup"><span data-stu-id="50607-185">For these examples, the `ProductId.txt` file contains an unsorted list of product numbers.</span></span>

<span data-ttu-id="50607-186">В первом примере `Get-Content` получает содержимое файла и линий каналов в `Sort-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="50607-186">In the first example, `Get-Content` gets the contents of the file and pipes lines to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="50607-187">`Sort-Object` Сортирует строковые объекты в возрастающем порядке.</span><span class="sxs-lookup"><span data-stu-id="50607-187">`Sort-Object` sorts the string objects in ascending order.</span></span>

```
PS> Get-Content -Path C:\Test\ProductId.txt | Sort-Object
0
1
12345
1500
2
2800
3500
4100
500
6200
77
88
99999

PS> Get-Content -Path C:\Test\ProductId.txt | Sort-Object {[int]$_}
0
1
2
77
88
500
1500
2800
3500
4100
6200
12345
99999
```

<span data-ttu-id="50607-188">Во втором примере `Get-Content` получает содержимое файла и линий каналов в `Sort-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="50607-188">In the second example, `Get-Content` gets the contents of the file and pipes lines to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="50607-189">`Sort-Object` использует блок скрипта для преобразования строк в целые числа.</span><span class="sxs-lookup"><span data-stu-id="50607-189">`Sort-Object` uses a script block to convert the strings to integers.</span></span> <span data-ttu-id="50607-190">В примере кода `[int]` преобразует строку в целое число и `$_` представляет каждую строку в том виде, в котором она поступает из конвейера.</span><span class="sxs-lookup"><span data-stu-id="50607-190">In the sample code, `[int]` converts the string to an integer and `$_` represents each string as it comes down the pipeline.</span></span> <span data-ttu-id="50607-191">Целочисленные объекты отправляются по конвейеру в `Sort-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="50607-191">The integer objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span>
<span data-ttu-id="50607-192">`Sort-Object` Сортирует целочисленные объекты в числовом порядке.</span><span class="sxs-lookup"><span data-stu-id="50607-192">`Sort-Object` sorts the integer objects in numeric order.</span></span>

### <span data-ttu-id="50607-193">Пример 9. использование стабильных сортировок</span><span class="sxs-lookup"><span data-stu-id="50607-193">Example 9: Using stable sorts</span></span>

<span data-ttu-id="50607-194">При использовании параметров **Top**, **Bottom** или **stable** отсортированные объекты доставляются в том порядке, в котором они были получены, `Sort-Object` если критерии сортировки равны.</span><span class="sxs-lookup"><span data-stu-id="50607-194">When you use the **Top**, **Bottom**, or **Stable** parameters, the sorted objects are delivered in the order they were received by `Sort-Object` when the sort criteria are equal.</span></span> <span data-ttu-id="50607-195">В этом примере мы будем сортировать числа от 1 до 20, используя их значение "остаток от деления 3".</span><span class="sxs-lookup"><span data-stu-id="50607-195">In this example, we are sorting the numbers one through 20 by the their value 'modulo 3'.</span></span> <span data-ttu-id="50607-196">Значение по модулю лежит в диапазоне от нуля до 2.</span><span class="sxs-lookup"><span data-stu-id="50607-196">The modulo value ranges from zero to two.</span></span>

```powershell
PS> 1..20 |Sort-Object {$_ % 3}
18
3
15
6
12
9
1
16
13
10
7
4
19
11
8
14
5
17
2
20

PS> 1..20 |Sort-Object {$_ % 3} -Stable
3
6
9
12
15
18
1
4
7
10
13
16
19
2
5
8
11
14
17
20
```

<span data-ttu-id="50607-197">Выходные данные первой сортировки правильно группируются по значению модуля, но отдельные элементы не сортируются в диапазоне модуля.</span><span class="sxs-lookup"><span data-stu-id="50607-197">The output from the first sort is correctly grouped by the modulus value but the individual items are not sorted within the modulus range.</span></span> <span data-ttu-id="50607-198">Вторая Сортировка использует **стабильный** параметр для возврата стабильной сортировки.</span><span class="sxs-lookup"><span data-stu-id="50607-198">The second sort uses the **Stable** option to return a stable sort.</span></span>

## <span data-ttu-id="50607-199">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="50607-199">PARAMETERS</span></span>

### <span data-ttu-id="50607-200">-Снизу</span><span class="sxs-lookup"><span data-stu-id="50607-200">-Bottom</span></span>

<span data-ttu-id="50607-201">Указывает количество объектов, получаемых от конца отсортированного массива объектов.</span><span class="sxs-lookup"><span data-stu-id="50607-201">Specifies the number of objects to get from the end of a sorted object array.</span></span> <span data-ttu-id="50607-202">Это приводит к стабильной сортировке.</span><span class="sxs-lookup"><span data-stu-id="50607-202">This results in a stable sort.</span></span>

<span data-ttu-id="50607-203">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="50607-203">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Bottom
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="50607-204">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="50607-204">-CaseSensitive</span></span>

<span data-ttu-id="50607-205">Указывает, что при сортировке учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="50607-205">Indicates that the sort is case-sensitive.</span></span> <span data-ttu-id="50607-206">По умолчанию сортировка выполняется без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="50607-206">By default, sorts are not case-sensitive.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Case-insensitive
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="50607-207">-Culture</span><span class="sxs-lookup"><span data-stu-id="50607-207">-Culture</span></span>

<span data-ttu-id="50607-208">Указывает конфигурацию культуры, используемую для сортировки.</span><span class="sxs-lookup"><span data-stu-id="50607-208">Specifies the cultural configuration to use for sorts.</span></span> <span data-ttu-id="50607-209">Используется `Get-Culture` для вывода конфигурации языка и региональных параметров системы.</span><span class="sxs-lookup"><span data-stu-id="50607-209">Use `Get-Culture` to display the system's culture configuration.</span></span>

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

### <span data-ttu-id="50607-210">-По убыванию</span><span class="sxs-lookup"><span data-stu-id="50607-210">-Descending</span></span>

<span data-ttu-id="50607-211">Указывает, что `Sort-Object` сортирует объекты в порядке убывания.</span><span class="sxs-lookup"><span data-stu-id="50607-211">Indicates that `Sort-Object` sorts the objects in descending order.</span></span> <span data-ttu-id="50607-212">По умолчанию результаты сортируются по возрастанию.</span><span class="sxs-lookup"><span data-stu-id="50607-212">The default is ascending order.</span></span>

<span data-ttu-id="50607-213">Для сортировки нескольких свойств с различными порядками сортировки используйте хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="50607-213">To sort multiple properties with different sort orders, use a hash table.</span></span> <span data-ttu-id="50607-214">Например, с помощью хэш-таблицы можно отсортировать одно свойство в возрастающем порядке и другое свойство в порядке убывания.</span><span class="sxs-lookup"><span data-stu-id="50607-214">For example, with a hash table you can sort one property in ascending order and another property in descending order.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Ascending
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="50607-215">-InputObject</span><span class="sxs-lookup"><span data-stu-id="50607-215">-InputObject</span></span>

<span data-ttu-id="50607-216">Чтобы отсортировать объекты, отправьте их по конвейеру в `Sort-Object` .</span><span class="sxs-lookup"><span data-stu-id="50607-216">To sort objects, send them down the pipeline to `Sort-Object`.</span></span> <span data-ttu-id="50607-217">При использовании параметра **InputObject** для отправки коллекции элементов `Sort-Object` получает один объект, представляющий коллекцию.</span><span class="sxs-lookup"><span data-stu-id="50607-217">If you use the **InputObject** parameter to submit a collection of items, `Sort-Object` receives one object that represents the collection.</span></span> <span data-ttu-id="50607-218">Поскольку один объект не может быть отсортирован, `Sort-Object` возвращает всю коллекцию без изменений.</span><span class="sxs-lookup"><span data-stu-id="50607-218">Because one object cannot be sorted, `Sort-Object` returns the entire collection unchanged.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="50607-219">-Property</span><span class="sxs-lookup"><span data-stu-id="50607-219">-Property</span></span>

<span data-ttu-id="50607-220">Указывает имена свойств, которые `Sort-Object` используются для сортировки объектов.</span><span class="sxs-lookup"><span data-stu-id="50607-220">Specifies the property names that `Sort-Object` uses to sort the objects.</span></span> <span data-ttu-id="50607-221">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="50607-221">Wildcards are permitted.</span></span>
<span data-ttu-id="50607-222">Объекты сортируются на основе значений свойств.</span><span class="sxs-lookup"><span data-stu-id="50607-222">Objects are sorted based on the property values.</span></span> <span data-ttu-id="50607-223">Если свойство не задано, `Sort-Object` сортируется на основе свойств по умолчанию для типа объекта или самих объектов.</span><span class="sxs-lookup"><span data-stu-id="50607-223">If you do not specify a property, `Sort-Object` sorts based on default properties for the object type or the objects themselves.</span></span>

<span data-ttu-id="50607-224">Несколько свойств можно сортировать в возрастающем порядке, по убыванию или в сочетании порядка сортировки.</span><span class="sxs-lookup"><span data-stu-id="50607-224">Multiple properties can be sorted in ascending order, descending order, or a combination of sort orders.</span></span> <span data-ttu-id="50607-225">При указании нескольких свойств объекты сортируются по первому свойству.</span><span class="sxs-lookup"><span data-stu-id="50607-225">When you specify multiple properties, the objects are sorted by the first property.</span></span> <span data-ttu-id="50607-226">Если для первого свойства несколько объектов имеют одинаковое значение, эти объекты сортируются по второму свойству.</span><span class="sxs-lookup"><span data-stu-id="50607-226">If multiple objects have the same value for the first property, those objects are sorted by the second property.</span></span> <span data-ttu-id="50607-227">Это продолжается до тех пор, пока не закончатся все указанные свойства или группы объектов.</span><span class="sxs-lookup"><span data-stu-id="50607-227">This process continues until there are no more specified properties or no groups of objects.</span></span>

<span data-ttu-id="50607-228">Значение параметра **Свойства** может быть вычисляемым свойством.</span><span class="sxs-lookup"><span data-stu-id="50607-228">The **Property** parameter's value can be a calculated property.</span></span> <span data-ttu-id="50607-229">Чтобы создать вычисляемое свойство, используйте хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="50607-229">To create a calculated property, use a hash table.</span></span>

<span data-ttu-id="50607-230">Ниже приведены допустимые ключи для хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="50607-230">Valid keys for a hash table are as follows:</span></span>

- <span data-ttu-id="50607-231">`expression` - `<string>` или `<script block>`</span><span class="sxs-lookup"><span data-stu-id="50607-231">`expression` - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="50607-232">`ascending` ни `descending` - `<boolean>`</span><span class="sxs-lookup"><span data-stu-id="50607-232">`ascending` or `descending` - `<boolean>`</span></span>

<span data-ttu-id="50607-233">Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="50607-233">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: Default properties
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="50607-234">-Сверху</span><span class="sxs-lookup"><span data-stu-id="50607-234">-Top</span></span>

<span data-ttu-id="50607-235">Указывает количество объектов, получаемых с начала отсортированного массива объектов.</span><span class="sxs-lookup"><span data-stu-id="50607-235">Specifies the number of objects to get from the start of a sorted object array.</span></span> <span data-ttu-id="50607-236">Это приводит к стабильной сортировке.</span><span class="sxs-lookup"><span data-stu-id="50607-236">This results in a stable sort.</span></span>

<span data-ttu-id="50607-237">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="50607-237">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Top
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="50607-238">— Уникальный</span><span class="sxs-lookup"><span data-stu-id="50607-238">-Unique</span></span>

<span data-ttu-id="50607-239">Указывает, что `Sort-Object` устраняет повторяющиеся значения и возвращает только уникальные элементы коллекции.</span><span class="sxs-lookup"><span data-stu-id="50607-239">Indicates that `Sort-Object` eliminates duplicates and returns only the unique members of the collection.</span></span> <span data-ttu-id="50607-240">Первый экземпляр уникального значения включается в отсортированные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="50607-240">The first instance of a unique value is included in the sorted output.</span></span>

<span data-ttu-id="50607-241">**Уникальный** регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="50607-241">**Unique** is case-insensitive.</span></span> <span data-ttu-id="50607-242">Строки, которые различаются только регистром символов, считаются одинаковыми.</span><span class="sxs-lookup"><span data-stu-id="50607-242">Strings that only differ by character case are considered the same.</span></span>
<span data-ttu-id="50607-243">Например, символ и символ.</span><span class="sxs-lookup"><span data-stu-id="50607-243">For example, character and CHARACTER.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: All
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="50607-244">— Стабильный</span><span class="sxs-lookup"><span data-stu-id="50607-244">-Stable</span></span>

<span data-ttu-id="50607-245">Отсортированные объекты доставляются в том порядке, в котором они были получены, если критерии сортировки равны.</span><span class="sxs-lookup"><span data-stu-id="50607-245">The sorted objects are delivered in the order they were received when the sort criteria are equal.</span></span>

<span data-ttu-id="50607-246">Этот параметр был добавлен в PowerShell v 6.2.0.</span><span class="sxs-lookup"><span data-stu-id="50607-246">This parameter was added in PowerShell v6.2.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="50607-247">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="50607-247">CommonParameters</span></span>

<span data-ttu-id="50607-248">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="50607-248">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="50607-249">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="50607-249">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="50607-250">Входные данные</span><span class="sxs-lookup"><span data-stu-id="50607-250">INPUTS</span></span>

### <span data-ttu-id="50607-251">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="50607-251">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="50607-252">Объекты, которые должны быть отсортированы, можно передать по конвейеру `Sort-Object` .</span><span class="sxs-lookup"><span data-stu-id="50607-252">You can pipe the objects to be sorted to `Sort-Object`.</span></span>

## <span data-ttu-id="50607-253">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="50607-253">OUTPUTS</span></span>

### <span data-ttu-id="50607-254">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="50607-254">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="50607-255">`Sort-Object` Возвращает отсортированные объекты.</span><span class="sxs-lookup"><span data-stu-id="50607-255">`Sort-Object` returns the sorted objects.</span></span>

## <span data-ttu-id="50607-256">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="50607-256">NOTES</span></span>

<span data-ttu-id="50607-257">`Sort-Object`Командлет сортирует объекты на основе свойств, указанных в команде, или свойств сортировки по умолчанию для типа объекта.</span><span class="sxs-lookup"><span data-stu-id="50607-257">The `Sort-Object` cmdlet sorts objects based on properties specified in the command or the default sort properties for the object type.</span></span> <span data-ttu-id="50607-258">Свойства сортировки по умолчанию определяются с помощью `PropertySet` имени `DefaultKeyPropertySet` в `types.ps1xml` файле.</span><span class="sxs-lookup"><span data-stu-id="50607-258">Default sort properties are defined using the `PropertySet` named `DefaultKeyPropertySet` in a `types.ps1xml` file.</span></span> <span data-ttu-id="50607-259">Дополнительные сведения см. в разделе [about_Types.ps1XML](/powershell/module/Microsoft.PowerShell.Core/About/about_Types.ps1xml).</span><span class="sxs-lookup"><span data-stu-id="50607-259">For more information, see [about_Types.ps1xml](/powershell/module/Microsoft.PowerShell.Core/About/about_Types.ps1xml).</span></span>

<span data-ttu-id="50607-260">Если объект не имеет одного из указанных свойств, значение свойства для этого объекта интерпретируется `Sort-Object` как **null** и помещается в конец порядка сортировки.</span><span class="sxs-lookup"><span data-stu-id="50607-260">If an object does not have one of the specified properties, the property value for that object is interpreted by `Sort-Object` as **Null** and placed at the end of the sort order.</span></span>

<span data-ttu-id="50607-261">Если свойства сортировки недоступны, PowerShell пытается сравнить сами объекты.</span><span class="sxs-lookup"><span data-stu-id="50607-261">When no sort properties are available, PowerShell attempts to compare the objects themselves.</span></span>
<span data-ttu-id="50607-262">`Sort-Object` использует метод **Compare** для каждого свойства.</span><span class="sxs-lookup"><span data-stu-id="50607-262">`Sort-Object` uses the **Compare** method for each property.</span></span> <span data-ttu-id="50607-263">Если свойство не реализует интерфейс **IComparable**, командлет преобразует значение свойства в строку и использует метод **Compare** для **System. String**.</span><span class="sxs-lookup"><span data-stu-id="50607-263">If a property does not implement **IComparable**, the cmdlet converts the property value to a string and uses the **Compare** method for **System.String**.</span></span> <span data-ttu-id="50607-264">Дополнительные сведения см. в разделе [метод PSObject. CompareTo (Object)](/dotnet/api/system.management.automation.psobject.compareto).</span><span class="sxs-lookup"><span data-stu-id="50607-264">For more information, see [PSObject.CompareTo(Object) Method](/dotnet/api/system.management.automation.psobject.compareto).</span></span>

<span data-ttu-id="50607-265">При сортировке по перечисляемому свойству, такому как **Status**, `Sort-Object` сортирует их по значениям перечисления.</span><span class="sxs-lookup"><span data-stu-id="50607-265">If you sort on an enumerated property such as **Status**, `Sort-Object` sorts by the enumeration values.</span></span> <span data-ttu-id="50607-266">Для служб Windows **Остановка** имеет значение **1** , а значение " **работает** " равно **4**.</span><span class="sxs-lookup"><span data-stu-id="50607-266">For Windows services, **Stopped** has a value of **1** and **Running** has a value of **4**.</span></span>
<span data-ttu-id="50607-267">**Остановлена** сортировка перед **выполнением** из-за перечислимых значений.</span><span class="sxs-lookup"><span data-stu-id="50607-267">**Stopped** is sorted before **Running** because of the enumerated values.</span></span> <span data-ttu-id="50607-268">Дополнительные сведения см. в разделе [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span><span class="sxs-lookup"><span data-stu-id="50607-268">For more information, see [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span></span>

<span data-ttu-id="50607-269">При стабильной сортировке производительность алгоритма сортировки снижается.</span><span class="sxs-lookup"><span data-stu-id="50607-269">The performance of the sorting algorithm is slower when doing a stable sort.</span></span>

## <span data-ttu-id="50607-270">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="50607-270">RELATED LINKS</span></span>

[<span data-ttu-id="50607-271">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="50607-271">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="50607-272">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="50607-272">about_Hash_Tables</span></span>](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[<span data-ttu-id="50607-273">about_Types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="50607-273">about_Types.ps1xml</span></span>](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)

[<span data-ttu-id="50607-274">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="50607-274">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="50607-275">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="50607-275">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="50607-276">Group-Object</span><span class="sxs-lookup"><span data-stu-id="50607-276">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="50607-277">Measure-Object;</span><span class="sxs-lookup"><span data-stu-id="50607-277">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="50607-278">New-Object</span><span class="sxs-lookup"><span data-stu-id="50607-278">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="50607-279">Select-Object</span><span class="sxs-lookup"><span data-stu-id="50607-279">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="50607-280">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="50607-280">Tee-Object</span></span>](Tee-Object.md)
