---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/sort-object?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Sort-Object
ms.openlocfilehash: 1d27641f94d82b85bab694b392c0f09bb3265517
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2020
ms.locfileid: "93230282"
---
# <span data-ttu-id="c33a3-103">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="c33a3-103">Sort-Object</span></span>

## <span data-ttu-id="c33a3-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c33a3-104">SYNOPSIS</span></span>
<span data-ttu-id="c33a3-105">Сортирует объекты по значениям свойств.</span><span class="sxs-lookup"><span data-stu-id="c33a3-105">Sorts objects by property values.</span></span>

## <span data-ttu-id="c33a3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c33a3-106">SYNTAX</span></span>

### <span data-ttu-id="c33a3-107">Default (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="c33a3-107">Default (Default)</span></span>

```
Sort-Object [[-Property] <Object[]>] [-Descending] [-Unique] [-InputObject <psobject>]
 [-Culture <string>] [-CaseSensitive] [<CommonParameters>]
```

## <span data-ttu-id="c33a3-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c33a3-108">DESCRIPTION</span></span>

<span data-ttu-id="c33a3-109">`Sort-Object`Командлет сортирует объекты в возрастающем или убывающем порядке на основе значений свойств объектов.</span><span class="sxs-lookup"><span data-stu-id="c33a3-109">The `Sort-Object` cmdlet sorts objects in ascending or descending order based on object property values.</span></span> <span data-ttu-id="c33a3-110">Если свойства сортировки не включены в команду, PowerShell использует свойства сортировки по умолчанию первого входного объекта.</span><span class="sxs-lookup"><span data-stu-id="c33a3-110">If sort properties are not included in a command, PowerShell uses default sort properties of the first input object.</span></span> <span data-ttu-id="c33a3-111">Если тип входного объекта не имеет свойств сортировки по умолчанию, PowerShell пытается сравнить сами объекты.</span><span class="sxs-lookup"><span data-stu-id="c33a3-111">If the type of the input object has no default sort properties, PowerShell attempts to compare the objects themselves.</span></span> <span data-ttu-id="c33a3-112">Дополнительные сведения см. в разделе " [Примечания](#notes) ".</span><span class="sxs-lookup"><span data-stu-id="c33a3-112">For more information, see the [Notes](#notes) section.</span></span>

<span data-ttu-id="c33a3-113">Объекты можно сортировать по отдельному свойству или нескольким свойствам.</span><span class="sxs-lookup"><span data-stu-id="c33a3-113">You can sort objects by a single property or multiple properties.</span></span> <span data-ttu-id="c33a3-114">Несколько свойств используют хэш-таблицы для сортировки в возрастающем порядке, по убыванию или в сочетании порядка сортировки.</span><span class="sxs-lookup"><span data-stu-id="c33a3-114">Multiple properties use hash tables to sort in ascending order, descending order, or a combination of sort orders.</span></span> <span data-ttu-id="c33a3-115">Свойства сортируются с учетом регистра или без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="c33a3-115">Properties are sorted as case-sensitive or case-insensitive.</span></span> <span data-ttu-id="c33a3-116">Используйте параметр **UNIQUE** , чтобы исключить дубликаты из выходных данных.</span><span class="sxs-lookup"><span data-stu-id="c33a3-116">Use the **Unique** parameter to eliminate duplicates from the output.</span></span>

## <span data-ttu-id="c33a3-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="c33a3-117">EXAMPLES</span></span>

### <span data-ttu-id="c33a3-118">Пример 1. Сортировка текущего каталога по имени</span><span class="sxs-lookup"><span data-stu-id="c33a3-118">Example 1: Sort the current directory by name</span></span>

<span data-ttu-id="c33a3-119">Эта команда сортирует файлы и подкаталоги в каталоге.</span><span class="sxs-lookup"><span data-stu-id="c33a3-119">This command sorts the files and subdirectories in a directory.</span></span>

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

<span data-ttu-id="c33a3-120">`Get-ChildItem`Командлет получает файлы и подкаталоги из каталога, указанного параметром **path** , **C:\test** .</span><span class="sxs-lookup"><span data-stu-id="c33a3-120">The `Get-ChildItem` cmdlet gets the files and subdirectories from the directory specified by the **Path** parameter, **C:\Test** .</span></span> <span data-ttu-id="c33a3-121">Объекты отправляются по конвейеру в `Sort-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="c33a3-121">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span>
<span data-ttu-id="c33a3-122">`Sort-Object` не указывает свойство, поэтому выходные данные сортируются по свойству Sort по умолчанию, **Name** .</span><span class="sxs-lookup"><span data-stu-id="c33a3-122">`Sort-Object` does not specify a property so the output is sorted by the default sort property, **Name** .</span></span>

### <span data-ttu-id="c33a3-123">Пример 2. Сортировка текущего каталога по длине файла</span><span class="sxs-lookup"><span data-stu-id="c33a3-123">Example 2: Sort the current directory by file length</span></span>

<span data-ttu-id="c33a3-124">Эта команда отображает файлы в текущем каталоге по длине в порядке возрастания.</span><span class="sxs-lookup"><span data-stu-id="c33a3-124">This command displays the files in the current directory by length in ascending order.</span></span>

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

<span data-ttu-id="c33a3-125">`Get-ChildItem`Командлет получает файлы из каталога, указанного параметром **path** .</span><span class="sxs-lookup"><span data-stu-id="c33a3-125">The `Get-ChildItem` cmdlet gets the files from the directory specified by the **Path** parameter.</span></span>
<span data-ttu-id="c33a3-126">Параметр **File** указывает, что `Get-ChildItem` только получает объекты File.</span><span class="sxs-lookup"><span data-stu-id="c33a3-126">The **File** parameter specifies that `Get-ChildItem` only gets file objects.</span></span> <span data-ttu-id="c33a3-127">Объекты отправляются по конвейеру в `Sort-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="c33a3-127">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="c33a3-128">`Sort-Object` использует параметр **length** для сортировки файлов по длине в порядке возрастания.</span><span class="sxs-lookup"><span data-stu-id="c33a3-128">`Sort-Object` uses the **Length** parameter to sort the files by length in ascending order.</span></span>

### <span data-ttu-id="c33a3-129">Пример 3. Сортировка процессов по использованию памяти</span><span class="sxs-lookup"><span data-stu-id="c33a3-129">Example 3: Sort processes by memory usage</span></span>

<span data-ttu-id="c33a3-130">В этом примере отображаются процессы с наибольшим использованием памяти в зависимости от размера рабочего множества (WS).</span><span class="sxs-lookup"><span data-stu-id="c33a3-130">This example displays processes with the highest memory usage based on their working set (WS) size.</span></span>

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

<span data-ttu-id="c33a3-131">`Get-Process`Командлет возвращает список процессов, запущенных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c33a3-131">The `Get-Process` cmdlet gets the list of processes running on the computer.</span></span> <span data-ttu-id="c33a3-132">Объекты процесса отправляются по конвейеру в `Sort-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="c33a3-132">The process objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="c33a3-133">`Sort-Object` использует параметр **Property** для сортировки объектов по протоколу **WS** .</span><span class="sxs-lookup"><span data-stu-id="c33a3-133">`Sort-Object` uses the **Property** parameter to sort the objects by **WS** .</span></span> <span data-ttu-id="c33a3-134">Объекты отправляются по конвейеру в `Select-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="c33a3-134">The objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span>
<span data-ttu-id="c33a3-135">`Select-Object` использует **последний** параметр для указания последних пяти объектов, которые являются объектами с наибольшим использованием **WS** .</span><span class="sxs-lookup"><span data-stu-id="c33a3-135">`Select-Object` uses the **Last** parameter to specify the last five objects, which are the objects with the highest **WS** usage.</span></span>

### <span data-ttu-id="c33a3-136">Пример 4. Сортировка объектов Хисторинфо по идентификатору</span><span class="sxs-lookup"><span data-stu-id="c33a3-136">Example 4: Sort HistoryInfo objects by Id</span></span>

<span data-ttu-id="c33a3-137">Эта команда сортирует объекты **хисторинфо** сеанса PowerShell с помощью свойства **ID** .</span><span class="sxs-lookup"><span data-stu-id="c33a3-137">This command sorts the PowerShell session's **HistoryInfo** objects using the **Id** property.</span></span> <span data-ttu-id="c33a3-138">Каждый сеанс PowerShell имеет собственный журнал команд.</span><span class="sxs-lookup"><span data-stu-id="c33a3-138">Each PowerShell session has its own command history.</span></span>

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

<span data-ttu-id="c33a3-139">`Get-History`Командлет получает объекты журнала из текущего сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c33a3-139">The `Get-History` cmdlet gets the history objects from the current PowerShell session.</span></span> <span data-ttu-id="c33a3-140">Объекты отправляются по конвейеру в `Sort-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="c33a3-140">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="c33a3-141">`Sort-Object` использует параметр **Property** для сортировки объектов по **идентификатору** . Параметр **Descending** сортирует журнал команд от новых к старым.</span><span class="sxs-lookup"><span data-stu-id="c33a3-141">`Sort-Object` uses the **Property** parameter to sort the objects by **Id** . The **Descending** parameter sorts the command history from newest to oldest.</span></span>

### <span data-ttu-id="c33a3-142">Пример 5. Использование хэш-таблицы для сортировки свойств в порядке возрастания и убывания</span><span class="sxs-lookup"><span data-stu-id="c33a3-142">Example 5: Use a hash table to sort properties in ascending and descending order</span></span>

<span data-ttu-id="c33a3-143">Эта команда использует два свойства для сортировки объектов, **Status** и **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="c33a3-143">This command uses two properties to sort the objects, **Status** and **DisplayName** .</span></span> <span data-ttu-id="c33a3-144">**Состояние** сортируется в убывающем порядке, а **DisplayName** — по возрастанию.</span><span class="sxs-lookup"><span data-stu-id="c33a3-144">**Status** is sorted in descending order and **DisplayName** is sorted in ascending order.</span></span>

<span data-ttu-id="c33a3-145">Хэш-таблица используется для указания значения параметра **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="c33a3-145">A hash table is used to specify the **Property** parameter's value.</span></span> <span data-ttu-id="c33a3-146">Хэш-таблица использует выражение для указания имен свойств и порядка сортировки.</span><span class="sxs-lookup"><span data-stu-id="c33a3-146">The hash table uses an expression to specify the property names and sort orders.</span></span> <span data-ttu-id="c33a3-147">Дополнительные сведения о хэш-таблицах см. [здесь](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span><span class="sxs-lookup"><span data-stu-id="c33a3-147">For more information about hash tables, see [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span></span>

<span data-ttu-id="c33a3-148">Свойство **Status** , используемое в хэш-таблице, является перечислимым свойством.</span><span class="sxs-lookup"><span data-stu-id="c33a3-148">The **Status** property used in the hash table is an enumerated property.</span></span>
<span data-ttu-id="c33a3-149">Дополнительные сведения см. в разделе [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span><span class="sxs-lookup"><span data-stu-id="c33a3-149">For more information, see [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span></span>

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

<span data-ttu-id="c33a3-150">`Get-Service`Командлет возвращает список служб на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c33a3-150">The `Get-Service` cmdlet gets the list of services on the computer.</span></span> <span data-ttu-id="c33a3-151">Объекты службы отправляются по конвейеру в `Sort-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="c33a3-151">The service objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="c33a3-152">`Sort-Object` использует параметр **Property** с хэш-таблицей для указания имен свойств и порядка сортировки.</span><span class="sxs-lookup"><span data-stu-id="c33a3-152">`Sort-Object` uses the **Property** parameter with a hash table to specify the property names and sort orders.</span></span> <span data-ttu-id="c33a3-153">Параметр **Свойства** сортируется по двум свойствам, **состояние** в убывающем порядке и **DisplayName** в возрастающем порядке.</span><span class="sxs-lookup"><span data-stu-id="c33a3-153">The **Property** parameter is sorted by two properties, **Status** in descending order and **DisplayName** in ascending order.</span></span>

<span data-ttu-id="c33a3-154">**Status** — это перечислимое свойство.</span><span class="sxs-lookup"><span data-stu-id="c33a3-154">**Status** is an enumerated property.</span></span> <span data-ttu-id="c33a3-155">Параметр **Stopped** имеет значение **1** , а его **выполнение** имеет значение **4** .</span><span class="sxs-lookup"><span data-stu-id="c33a3-155">**Stopped** has a value of **1** and **Running** has a value of **4** .</span></span> <span data-ttu-id="c33a3-156">Параметр **Descending** имеет значение, `$True` чтобы перед **остановленными** процессами отображались **выполняющиеся** процессы.</span><span class="sxs-lookup"><span data-stu-id="c33a3-156">The **Descending** parameter is set to `$True` so that **Running** processes are displayed before **Stopped** processes.</span></span> <span data-ttu-id="c33a3-157">**DisplayName** задает для параметра по **убыванию** значение, чтобы `$False` отсортировать отображаемые имена в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="c33a3-157">**DisplayName** sets the **Descending** parameter to `$False` to sort the display names in alphabetical order.</span></span>

### <span data-ttu-id="c33a3-158">Пример 6. сортировка текстовых файлов по периоду времени</span><span class="sxs-lookup"><span data-stu-id="c33a3-158">Example 6: Sort text files by time span</span></span>

<span data-ttu-id="c33a3-159">Эта команда сортирует текстовые файлы в порядке убывания интервала времени между **CreationTime** и **LastWriteTime** .</span><span class="sxs-lookup"><span data-stu-id="c33a3-159">This command sorts text files in descending order by the time span between **CreationTime** and **LastWriteTime** .</span></span>

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

<span data-ttu-id="c33a3-160">`Get-ChildItem`Командлет использует параметр **path** для указания каталога **C:\test** и всех `*.txt` файлов.</span><span class="sxs-lookup"><span data-stu-id="c33a3-160">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory **C:\Test** and all of the `*.txt` files.</span></span> <span data-ttu-id="c33a3-161">Объекты отправляются по конвейеру в `Sort-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="c33a3-161">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span>
<span data-ttu-id="c33a3-162">`Sort-Object` использует параметр **Property** с хэш-таблицей для определения интервала времени каждого файла между **CreationTime** и **LastWriteTime** .</span><span class="sxs-lookup"><span data-stu-id="c33a3-162">`Sort-Object` uses the **Property** parameter with a hash table to determine each files time span between **CreationTime** and **LastWriteTime** .</span></span> <span data-ttu-id="c33a3-163">Параметр **Descending** имеет значение, чтобы `$False` Сортировать в порядке убывания к кратчайшему диапазону времени.</span><span class="sxs-lookup"><span data-stu-id="c33a3-163">The **Descending** parameter is set to `$False` to sort in the order of longest to shortest time span.</span></span>

### <span data-ttu-id="c33a3-164">Пример 7. Сортировка имен в текстовом файле</span><span class="sxs-lookup"><span data-stu-id="c33a3-164">Example 7: Sort names in a text file</span></span>

<span data-ttu-id="c33a3-165">В этом примере показано, как отсортировать список из текстового файла.</span><span class="sxs-lookup"><span data-stu-id="c33a3-165">This example shows how to sort a list from a text file.</span></span> <span data-ttu-id="c33a3-166">Исходный файл отображается в виде несортированного списка.</span><span class="sxs-lookup"><span data-stu-id="c33a3-166">The original file is displayed as an unsorted list.</span></span> <span data-ttu-id="c33a3-167">`Sort-Object` Сортирует содержимое, а затем сортирует содержимое с **уникальным** параметром, который удаляет дубликаты.</span><span class="sxs-lookup"><span data-stu-id="c33a3-167">`Sort-Object` sorts the contents and then sorts the contents with the **Unique** parameter that removes duplicates.</span></span>

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

<span data-ttu-id="c33a3-168">`Get-Content`Командлет использует параметр **path** , чтобы указать каталог и имя файла.</span><span class="sxs-lookup"><span data-stu-id="c33a3-168">The `Get-Content` cmdlet uses the **Path** parameter to specify the directory and file name.</span></span> <span data-ttu-id="c33a3-169">Файл **ServerNames.txt** содержит Несортированный список имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="c33a3-169">The file **ServerNames.txt** contains an unsorted list of computer names.</span></span>

<span data-ttu-id="c33a3-170">`Get-Content`Командлет использует параметр **path** , чтобы указать каталог и имя файла.</span><span class="sxs-lookup"><span data-stu-id="c33a3-170">The `Get-Content` cmdlet uses the **Path** parameter to specify the directory and file name.</span></span> <span data-ttu-id="c33a3-171">Файл **ServerNames.txt** содержит Несортированный список имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="c33a3-171">The file **ServerNames.txt** contains an unsorted list of computer names.</span></span> <span data-ttu-id="c33a3-172">Объекты отправляются по конвейеру в `Sort-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="c33a3-172">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="c33a3-173">`Sort-Object` Сортирует список в порядке по умолчанию (по возрастанию).</span><span class="sxs-lookup"><span data-stu-id="c33a3-173">`Sort-Object` sorts the list in the default order, ascending.</span></span>

<span data-ttu-id="c33a3-174">`Get-Content`Командлет использует параметр **path** , чтобы указать каталог и имя файла.</span><span class="sxs-lookup"><span data-stu-id="c33a3-174">The `Get-Content` cmdlet uses the **Path** parameter to specify the directory and file name.</span></span> <span data-ttu-id="c33a3-175">Файл **ServerNames.txt** содержит Несортированный список имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="c33a3-175">The file **ServerNames.txt** contains an unsorted list of computer names.</span></span> <span data-ttu-id="c33a3-176">Объекты отправляются по конвейеру в `Sort-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="c33a3-176">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="c33a3-177">`Sort-Object` использует параметр **UNIQUE** для удаления повторяющихся имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="c33a3-177">`Sort-Object` uses the **Unique** parameter to remove duplicate computer names.</span></span> <span data-ttu-id="c33a3-178">Список сортируется в порядке по умолчанию (по возрастанию).</span><span class="sxs-lookup"><span data-stu-id="c33a3-178">The list is sorted in the default order, ascending.</span></span>

### <span data-ttu-id="c33a3-179">Пример 8. Сортировка строки в виде целого числа</span><span class="sxs-lookup"><span data-stu-id="c33a3-179">Example 8: Sort a string as an integer</span></span>

<span data-ttu-id="c33a3-180">В этом примере показано, как выполнить сортировку текстового файла, содержащего строковые объекты, в виде целых чисел.</span><span class="sxs-lookup"><span data-stu-id="c33a3-180">This example shows how to sort a text file that contains string objects as integers.</span></span> <span data-ttu-id="c33a3-181">Можно отправить каждую команду вниз по конвейеру в `Get-Member` и убедиться, что объекты являются строками, а не целыми числами.</span><span class="sxs-lookup"><span data-stu-id="c33a3-181">You can send each command down the pipeline to `Get-Member` and verify that the objects are strings instead of integers.</span></span> <span data-ttu-id="c33a3-182">В этих примерах `ProductId.txt` файл содержит Несортированный список номеров продуктов.</span><span class="sxs-lookup"><span data-stu-id="c33a3-182">For these examples, the `ProductId.txt` file contains an unsorted list of product numbers.</span></span>

<span data-ttu-id="c33a3-183">В первом примере `Get-Content` получает содержимое файла и линий каналов в `Sort-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="c33a3-183">In the first example, `Get-Content` gets the contents of the file and pipes lines to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="c33a3-184">`Sort-Object` Сортирует строковые объекты в возрастающем порядке.</span><span class="sxs-lookup"><span data-stu-id="c33a3-184">`Sort-Object` sorts the string objects in ascending order.</span></span>

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

<span data-ttu-id="c33a3-185">Во втором примере `Get-Content` получает содержимое файла и линий каналов в `Sort-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="c33a3-185">In the second example, `Get-Content` gets the contents of the file and pipes lines to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="c33a3-186">`Sort-Object` использует блок скрипта для преобразования строк в целые числа.</span><span class="sxs-lookup"><span data-stu-id="c33a3-186">`Sort-Object` uses a script block to convert the strings to integers.</span></span> <span data-ttu-id="c33a3-187">В примере кода `[int]` преобразует строку в целое число и `$_` представляет каждую строку в том виде, в котором она поступает из конвейера.</span><span class="sxs-lookup"><span data-stu-id="c33a3-187">In the sample code, `[int]` converts the string to an integer and `$_` represents each string as it comes down the pipeline.</span></span> <span data-ttu-id="c33a3-188">Целочисленные объекты отправляются по конвейеру в `Sort-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="c33a3-188">The integer objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span>
<span data-ttu-id="c33a3-189">`Sort-Object` Сортирует целочисленные объекты в числовом порядке.</span><span class="sxs-lookup"><span data-stu-id="c33a3-189">`Sort-Object` sorts the integer objects in numeric order.</span></span>

<span data-ttu-id="c33a3-190">`Get-Content`Командлет использует параметр **path** , чтобы указать каталог и имя файла.</span><span class="sxs-lookup"><span data-stu-id="c33a3-190">The `Get-Content` cmdlet uses the **Path** parameter to specify the directory and file name.</span></span> <span data-ttu-id="c33a3-191">Файл **ProductId.txt** содержит Несортированный список номеров продуктов.</span><span class="sxs-lookup"><span data-stu-id="c33a3-191">The file **ProductId.txt** contains an unsorted list of product numbers.</span></span> <span data-ttu-id="c33a3-192">Строковые объекты отправляются в командлет по конвейеру `ForEach-Object` .</span><span class="sxs-lookup"><span data-stu-id="c33a3-192">The string objects are sent down the pipeline to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="c33a3-193">`ForEach-Object` использует блок скрипта для преобразования строк в целые числа.</span><span class="sxs-lookup"><span data-stu-id="c33a3-193">`ForEach-Object` uses a script block to convert the strings to integers.</span></span> <span data-ttu-id="c33a3-194">В примере кода `[int]` преобразует строку в целое число и `$_` представляет каждую строку в том виде, в котором она поступает из конвейера.</span><span class="sxs-lookup"><span data-stu-id="c33a3-194">In the sample code, `[int]` converts the string to an integer and `$_` represents each string as it comes down the pipeline.</span></span> <span data-ttu-id="c33a3-195">Целочисленные объекты отправляются по конвейеру в `Sort-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="c33a3-195">The integer objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="c33a3-196">`Sort-Object` Сортирует целочисленные объекты в числовом порядке.</span><span class="sxs-lookup"><span data-stu-id="c33a3-196">`Sort-Object` sorts the integer objects in numeric order.</span></span>
## <span data-ttu-id="c33a3-197">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c33a3-197">PARAMETERS</span></span>

### <span data-ttu-id="c33a3-198">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="c33a3-198">-CaseSensitive</span></span>

<span data-ttu-id="c33a3-199">Указывает, что при сортировке учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="c33a3-199">Indicates that the sort is case-sensitive.</span></span> <span data-ttu-id="c33a3-200">По умолчанию сортировка выполняется без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="c33a3-200">By default, sorts are not case-sensitive.</span></span>

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

### <span data-ttu-id="c33a3-201">-Culture</span><span class="sxs-lookup"><span data-stu-id="c33a3-201">-Culture</span></span>

<span data-ttu-id="c33a3-202">Указывает конфигурацию культуры, используемую для сортировки.</span><span class="sxs-lookup"><span data-stu-id="c33a3-202">Specifies the cultural configuration to use for sorts.</span></span> <span data-ttu-id="c33a3-203">Используется `Get-Culture` для вывода конфигурации языка и региональных параметров системы.</span><span class="sxs-lookup"><span data-stu-id="c33a3-203">Use `Get-Culture` to display the system's culture configuration.</span></span>

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

### <span data-ttu-id="c33a3-204">-По убыванию</span><span class="sxs-lookup"><span data-stu-id="c33a3-204">-Descending</span></span>

<span data-ttu-id="c33a3-205">Указывает, что `Sort-Object` сортирует объекты в порядке убывания.</span><span class="sxs-lookup"><span data-stu-id="c33a3-205">Indicates that `Sort-Object` sorts the objects in descending order.</span></span> <span data-ttu-id="c33a3-206">По умолчанию результаты сортируются по возрастанию.</span><span class="sxs-lookup"><span data-stu-id="c33a3-206">The default is ascending order.</span></span>

<span data-ttu-id="c33a3-207">Для сортировки нескольких свойств с различными порядками сортировки используйте хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="c33a3-207">To sort multiple properties with different sort orders, use a hash table.</span></span> <span data-ttu-id="c33a3-208">Например, с помощью хэш-таблицы можно отсортировать одно свойство в возрастающем порядке и другое свойство в порядке убывания.</span><span class="sxs-lookup"><span data-stu-id="c33a3-208">For example, with a hash table you can sort one property in ascending order and another property in descending order.</span></span>

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

### <span data-ttu-id="c33a3-209">-InputObject</span><span class="sxs-lookup"><span data-stu-id="c33a3-209">-InputObject</span></span>

<span data-ttu-id="c33a3-210">Чтобы отсортировать объекты, отправьте их по конвейеру в `Sort-Object` .</span><span class="sxs-lookup"><span data-stu-id="c33a3-210">To sort objects, send them down the pipeline to `Sort-Object`.</span></span> <span data-ttu-id="c33a3-211">При использовании параметра **InputObject** для отправки коллекции элементов `Sort-Object` получает один объект, представляющий коллекцию.</span><span class="sxs-lookup"><span data-stu-id="c33a3-211">If you use the **InputObject** parameter to submit a collection of items, `Sort-Object` receives one object that represents the collection.</span></span> <span data-ttu-id="c33a3-212">Поскольку один объект не может быть отсортирован, `Sort-Object` возвращает всю коллекцию без изменений.</span><span class="sxs-lookup"><span data-stu-id="c33a3-212">Because one object cannot be sorted, `Sort-Object` returns the entire collection unchanged.</span></span>

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

### <span data-ttu-id="c33a3-213">-Property</span><span class="sxs-lookup"><span data-stu-id="c33a3-213">-Property</span></span>

<span data-ttu-id="c33a3-214">Указывает имена свойств, которые `Sort-Object` используются для сортировки объектов.</span><span class="sxs-lookup"><span data-stu-id="c33a3-214">Specifies the property names that `Sort-Object` uses to sort the objects.</span></span> <span data-ttu-id="c33a3-215">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="c33a3-215">Wildcards are permitted.</span></span>
<span data-ttu-id="c33a3-216">Объекты сортируются на основе значений свойств.</span><span class="sxs-lookup"><span data-stu-id="c33a3-216">Objects are sorted based on the property values.</span></span> <span data-ttu-id="c33a3-217">Если свойство не задано, `Sort-Object` сортируется на основе свойств по умолчанию для типа объекта или самих объектов.</span><span class="sxs-lookup"><span data-stu-id="c33a3-217">If you do not specify a property, `Sort-Object` sorts based on default properties for the object type or the objects themselves.</span></span>

<span data-ttu-id="c33a3-218">Несколько свойств можно сортировать в возрастающем порядке, по убыванию или в сочетании порядка сортировки.</span><span class="sxs-lookup"><span data-stu-id="c33a3-218">Multiple properties can be sorted in ascending order, descending order, or a combination of sort orders.</span></span> <span data-ttu-id="c33a3-219">При указании нескольких свойств объекты сортируются по первому свойству.</span><span class="sxs-lookup"><span data-stu-id="c33a3-219">When you specify multiple properties, the objects are sorted by the first property.</span></span> <span data-ttu-id="c33a3-220">Если для первого свойства несколько объектов имеют одинаковое значение, эти объекты сортируются по второму свойству.</span><span class="sxs-lookup"><span data-stu-id="c33a3-220">If multiple objects have the same value for the first property, those objects are sorted by the second property.</span></span> <span data-ttu-id="c33a3-221">Это продолжается до тех пор, пока не закончатся все указанные свойства или группы объектов.</span><span class="sxs-lookup"><span data-stu-id="c33a3-221">This process continues until there are no more specified properties or no groups of objects.</span></span>

<span data-ttu-id="c33a3-222">Значение параметра **Свойства** может быть вычисляемым свойством.</span><span class="sxs-lookup"><span data-stu-id="c33a3-222">The **Property** parameter's value can be a calculated property.</span></span> <span data-ttu-id="c33a3-223">Чтобы создать вычисляемое свойство, используйте хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="c33a3-223">To create a calculated property, use a hash table.</span></span>

<span data-ttu-id="c33a3-224">Ниже приведены допустимые ключи для хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="c33a3-224">Valid keys for a hash table are as follows:</span></span>

- <span data-ttu-id="c33a3-225">`expression` - `<string>` или `<script block>`</span><span class="sxs-lookup"><span data-stu-id="c33a3-225">`expression` - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="c33a3-226">`ascending` ни `descending` - `<boolean>`</span><span class="sxs-lookup"><span data-stu-id="c33a3-226">`ascending` or `descending` - `<boolean>`</span></span>

<span data-ttu-id="c33a3-227">Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="c33a3-227">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="c33a3-228">— Уникальный</span><span class="sxs-lookup"><span data-stu-id="c33a3-228">-Unique</span></span>

<span data-ttu-id="c33a3-229">Указывает, что `Sort-Object` устраняет повторяющиеся значения и возвращает только уникальные элементы коллекции.</span><span class="sxs-lookup"><span data-stu-id="c33a3-229">Indicates that `Sort-Object` eliminates duplicates and returns only the unique members of the collection.</span></span> <span data-ttu-id="c33a3-230">Первый экземпляр уникального значения включается в отсортированные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="c33a3-230">The first instance of a unique value is included in the sorted output.</span></span>

<span data-ttu-id="c33a3-231">**Уникальный** регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="c33a3-231">**Unique** is case-insensitive.</span></span> <span data-ttu-id="c33a3-232">Строки, которые различаются только регистром символов, считаются одинаковыми.</span><span class="sxs-lookup"><span data-stu-id="c33a3-232">Strings that only differ by character case are considered the same.</span></span>
<span data-ttu-id="c33a3-233">Например, символ и символ.</span><span class="sxs-lookup"><span data-stu-id="c33a3-233">For example, character and CHARACTER.</span></span>

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

### <span data-ttu-id="c33a3-234">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="c33a3-234">CommonParameters</span></span>

<span data-ttu-id="c33a3-235">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c33a3-235">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c33a3-236">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c33a3-236">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c33a3-237">Входные данные</span><span class="sxs-lookup"><span data-stu-id="c33a3-237">INPUTS</span></span>

### <span data-ttu-id="c33a3-238">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="c33a3-238">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="c33a3-239">Объекты, которые должны быть отсортированы, можно передать по конвейеру `Sort-Object` .</span><span class="sxs-lookup"><span data-stu-id="c33a3-239">You can pipe the objects to be sorted to `Sort-Object`.</span></span>

## <span data-ttu-id="c33a3-240">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="c33a3-240">OUTPUTS</span></span>

### <span data-ttu-id="c33a3-241">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="c33a3-241">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="c33a3-242">`Sort-Object` Возвращает отсортированные объекты.</span><span class="sxs-lookup"><span data-stu-id="c33a3-242">`Sort-Object` returns the sorted objects.</span></span>

## <span data-ttu-id="c33a3-243">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="c33a3-243">NOTES</span></span>

<span data-ttu-id="c33a3-244">`Sort-Object`Командлет сортирует объекты на основе свойств, указанных в команде, или свойств сортировки по умолчанию для типа объекта.</span><span class="sxs-lookup"><span data-stu-id="c33a3-244">The `Sort-Object` cmdlet sorts objects based on properties specified in the command or the default sort properties for the object type.</span></span> <span data-ttu-id="c33a3-245">Свойства сортировки по умолчанию определяются с помощью `PropertySet` имени `DefaultKeyPropertySet` в `types.ps1xml` файле.</span><span class="sxs-lookup"><span data-stu-id="c33a3-245">Default sort properties are defined using the `PropertySet` named `DefaultKeyPropertySet` in a `types.ps1xml` file.</span></span> <span data-ttu-id="c33a3-246">Дополнительные сведения см. в разделе [about_Types.ps1XML](/powershell/module/Microsoft.PowerShell.Core/About/about_Types.ps1xml).</span><span class="sxs-lookup"><span data-stu-id="c33a3-246">For more information, see [about_Types.ps1xml](/powershell/module/Microsoft.PowerShell.Core/About/about_Types.ps1xml).</span></span>

<span data-ttu-id="c33a3-247">Если объект не имеет одного из указанных свойств, значение свойства для этого объекта интерпретируется `Sort-Object` как **null** и помещается в конец порядка сортировки.</span><span class="sxs-lookup"><span data-stu-id="c33a3-247">If an object does not have one of the specified properties, the property value for that object is interpreted by `Sort-Object` as **Null** and placed at the end of the sort order.</span></span>

<span data-ttu-id="c33a3-248">Если свойства сортировки недоступны, PowerShell пытается сравнить сами объекты.</span><span class="sxs-lookup"><span data-stu-id="c33a3-248">When no sort properties are available, PowerShell attempts to compare the objects themselves.</span></span>
<span data-ttu-id="c33a3-249">`Sort-Object` использует метод **Compare** для каждого свойства.</span><span class="sxs-lookup"><span data-stu-id="c33a3-249">`Sort-Object` uses the **Compare** method for each property.</span></span> <span data-ttu-id="c33a3-250">Если свойство не реализует интерфейс **IComparable** , командлет преобразует значение свойства в строку и использует метод **Compare** для **System. String** .</span><span class="sxs-lookup"><span data-stu-id="c33a3-250">If a property does not implement **IComparable** , the cmdlet converts the property value to a string and uses the **Compare** method for **System.String** .</span></span> <span data-ttu-id="c33a3-251">Дополнительные сведения см. в разделе [метод PSObject. CompareTo (Object)](/dotnet/api/system.management.automation.psobject.compareto).</span><span class="sxs-lookup"><span data-stu-id="c33a3-251">For more information, see [PSObject.CompareTo(Object) Method](/dotnet/api/system.management.automation.psobject.compareto).</span></span>

<span data-ttu-id="c33a3-252">При сортировке по перечисляемому свойству, такому как **Status** , `Sort-Object` сортирует их по значениям перечисления.</span><span class="sxs-lookup"><span data-stu-id="c33a3-252">If you sort on an enumerated property such as **Status** , `Sort-Object` sorts by the enumeration values.</span></span> <span data-ttu-id="c33a3-253">Для служб Windows **Остановка** имеет значение **1** , а значение " **работает** " равно **4** .</span><span class="sxs-lookup"><span data-stu-id="c33a3-253">For Windows services, **Stopped** has a value of **1** and **Running** has a value of **4** .</span></span>
<span data-ttu-id="c33a3-254">**Остановлена** сортировка перед **выполнением** из-за перечислимых значений.</span><span class="sxs-lookup"><span data-stu-id="c33a3-254">**Stopped** is sorted before **Running** because of the enumerated values.</span></span> <span data-ttu-id="c33a3-255">Дополнительные сведения см. в разделе [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span><span class="sxs-lookup"><span data-stu-id="c33a3-255">For more information, see [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span></span>

## <span data-ttu-id="c33a3-256">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="c33a3-256">RELATED LINKS</span></span>

[<span data-ttu-id="c33a3-257">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="c33a3-257">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="c33a3-258">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="c33a3-258">about_Hash_Tables</span></span>](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[<span data-ttu-id="c33a3-259">about_Types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="c33a3-259">about_Types.ps1xml</span></span>](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)

[<span data-ttu-id="c33a3-260">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="c33a3-260">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="c33a3-261">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="c33a3-261">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="c33a3-262">Group-Object</span><span class="sxs-lookup"><span data-stu-id="c33a3-262">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="c33a3-263">Measure-Object;</span><span class="sxs-lookup"><span data-stu-id="c33a3-263">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="c33a3-264">New-Object</span><span class="sxs-lookup"><span data-stu-id="c33a3-264">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="c33a3-265">Select-Object</span><span class="sxs-lookup"><span data-stu-id="c33a3-265">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="c33a3-266">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="c33a3-266">Tee-Object</span></span>](Tee-Object.md)
