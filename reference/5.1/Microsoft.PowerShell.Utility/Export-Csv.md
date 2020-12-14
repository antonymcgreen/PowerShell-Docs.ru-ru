---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-csv?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Csv
ms.openlocfilehash: 17c3ef3046ba8f0cca9a85cf41aaf683212a58e9
ms.sourcegitcommit: 560a9f3c3148acab4655e91e8b07745ab74d5d26
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2020
ms.locfileid: "96913348"
---
# <span data-ttu-id="4372b-102">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="4372b-102">Export-Csv</span></span>

## <span data-ttu-id="4372b-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4372b-103">SYNOPSIS</span></span>
<span data-ttu-id="4372b-104">Преобразует объекты в последовательность строк с разделителями-запятыми (CSV) и сохраняет строки в файл.</span><span class="sxs-lookup"><span data-stu-id="4372b-104">Converts objects into a series of comma-separated value (CSV) strings and saves the strings to a file.</span></span>

## <span data-ttu-id="4372b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4372b-105">SYNTAX</span></span>

### <span data-ttu-id="4372b-106">Delimiter (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="4372b-106">Delimiter (Default)</span></span>

```
Export-Csv [[-Path] <string>] [[-Delimiter] <char>] -InputObject <psobject> [-LiteralPath <string>]
 [-Force] [-NoClobber] [-Encoding <string>] [-Append] [-NoTypeInformation] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="4372b-107">UseCulture</span><span class="sxs-lookup"><span data-stu-id="4372b-107">UseCulture</span></span>

```
Export-Csv [[-Path] <string>] -InputObject <psobject> [-LiteralPath <string>] [-Force] [-NoClobber]
 [-Encoding <string>] [-Append] [-UseCulture] [-NoTypeInformation] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="4372b-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4372b-108">DESCRIPTION</span></span>

<span data-ttu-id="4372b-109">`Export-CSV`Командлет создает CSV-файл объектов, которые вы отправляете.</span><span class="sxs-lookup"><span data-stu-id="4372b-109">The `Export-CSV` cmdlet creates a CSV file of the objects that you submit.</span></span> <span data-ttu-id="4372b-110">Каждый объект представляет собой строку, содержащую разделенный запятыми список значений свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="4372b-110">Each object is a row that includes a comma-separated list of the object's property values.</span></span> <span data-ttu-id="4372b-111">С помощью `Export-CSV` командлета можно создавать электронные таблицы и обмениваться данными с программами, которые принимают CSV-файлы в качестве входных.</span><span class="sxs-lookup"><span data-stu-id="4372b-111">You can use the `Export-CSV` cmdlet to create spreadsheets and share data with programs that accept CSV files as input.</span></span>

<span data-ttu-id="4372b-112">Не форматируйте объекты перед их отправкой в `Export-CSV` командлет.</span><span class="sxs-lookup"><span data-stu-id="4372b-112">Do not format objects before sending them to the `Export-CSV` cmdlet.</span></span> <span data-ttu-id="4372b-113">Если `Export-CSV` получает отформатированные объекты, CSV-файл содержит свойства форматирования, а не свойства объекта.</span><span class="sxs-lookup"><span data-stu-id="4372b-113">If `Export-CSV` receives formatted objects the CSV file contains the format properties rather than the object properties.</span></span> <span data-ttu-id="4372b-114">Чтобы экспортировать только выбранные свойства объекта, используйте `Select-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="4372b-114">To export only selected properties of an object, use the `Select-Object` cmdlet.</span></span>

## <span data-ttu-id="4372b-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="4372b-115">EXAMPLES</span></span>

### <span data-ttu-id="4372b-116">Пример 1. экспорт свойств процесса в CSV-файл</span><span class="sxs-lookup"><span data-stu-id="4372b-116">Example 1: Export process properties to a CSV file</span></span>

<span data-ttu-id="4372b-117">В этом примере выбираются объекты **Process** с конкретными свойствами, экспортируются объекты в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="4372b-117">This example selects **Process** objects with specific properties, exports the objects to a CSV file.</span></span>

```powershell
Get-Process -Name WmiPrvSE | Select-Object -Property BasePriority,Id,SessionId,WorkingSet |
  Export-Csv -Path .\WmiData.csv -NoTypeInformation
Import-Csv -Path .\WmiData.csv
```

```Output
BasePriority Id    SessionId WorkingSet
------------ --    --------- ----------
8            976   0         20267008
8            2292  0         36786176
8            3816  0         30351360
8            8604  0         15011840
8            10008 0         8830976
8            11764 0         14237696
8            54632 0         9502720
```

<span data-ttu-id="4372b-118">`Get-Process`Командлет возвращает объекты **процесса** .</span><span class="sxs-lookup"><span data-stu-id="4372b-118">The `Get-Process` cmdlet gets the **Process** objects.</span></span> <span data-ttu-id="4372b-119">Параметр **Name** фильтрует выходные данные, чтобы включить только объекты процесса WmiPrvSE.</span><span class="sxs-lookup"><span data-stu-id="4372b-119">The **Name** parameter filters the output to include only the WmiPrvSE process objects.</span></span> <span data-ttu-id="4372b-120">Объекты процесса отправляются по конвейеру в `Select-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="4372b-120">The process objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="4372b-121">`Select-Object` использует параметр **Property** для выбора подмножества свойств объекта процесса.</span><span class="sxs-lookup"><span data-stu-id="4372b-121">`Select-Object` uses the **Property** parameter to select a subset of process object properties.</span></span> <span data-ttu-id="4372b-122">Объекты процесса отправляются по конвейеру в `Export-Csv` командлет.</span><span class="sxs-lookup"><span data-stu-id="4372b-122">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="4372b-123">`Export-Csv` Преобразует объекты процесса в последовательность строк CSV.</span><span class="sxs-lookup"><span data-stu-id="4372b-123">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="4372b-124">Параметр **path** указывает, что файл WmiData.csv сохраняется в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4372b-124">The **Path** parameter specifies that the WmiData.csv file is saved in the current directory.</span></span> <span data-ttu-id="4372b-125">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="4372b-125">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="4372b-126">`Import-Csv`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4372b-126">The `Import-Csv` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="4372b-127">Пример 2. экспорт процессов в файл с разделителями-запятыми</span><span class="sxs-lookup"><span data-stu-id="4372b-127">Example 2: Export processes to a comma-delimited file</span></span>

<span data-ttu-id="4372b-128">В этом примере **выполняется** получение объектов Process и экспорт объектов в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="4372b-128">This example gets **Process** objects and exports the objects to a CSV file.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","511","2203597099008","35364864","21979136","30048", ...
```

<span data-ttu-id="4372b-129">`Get-Process`Командлет получает объекты **Process** .</span><span class="sxs-lookup"><span data-stu-id="4372b-129">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="4372b-130">Объекты процесса отправляются по конвейеру в `Export-Csv` командлет.</span><span class="sxs-lookup"><span data-stu-id="4372b-130">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="4372b-131">`Export-Csv` Преобразует объекты процесса в последовательность строк CSV.</span><span class="sxs-lookup"><span data-stu-id="4372b-131">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="4372b-132">Параметр **path** указывает, что файл Processes.csv сохраняется в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4372b-132">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="4372b-133">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="4372b-133">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="4372b-134">`Get-Content`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4372b-134">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="4372b-135">Пример 3. экспорт процессов в файл с разделителями-запятыми</span><span class="sxs-lookup"><span data-stu-id="4372b-135">Example 3: Export processes to a semicolon delimited file</span></span>

<span data-ttu-id="4372b-136">В этом примере **выполняется** получение объектов Process и экспорт объектов в файл с разделителем в виде точки с запятой.</span><span class="sxs-lookup"><span data-stu-id="4372b-136">This example gets **Process** objects and exports the objects to a file with a semicolon delimiter.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -Delimiter ';' -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name";"SI";"Handles";"VM";"WS";"PM";"NPM";"Path";"Parent";"Company";"CPU";"FileVersion"; ...
"ApplicationFrameHost";"4";"509";"2203595321344";"34807808";"21770240";"29504"; ...
```

<span data-ttu-id="4372b-137">`Get-Process`Командлет получает объекты **Process** .</span><span class="sxs-lookup"><span data-stu-id="4372b-137">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="4372b-138">Объекты процесса отправляются по конвейеру в `Export-Csv` командлет.</span><span class="sxs-lookup"><span data-stu-id="4372b-138">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="4372b-139">`Export-Csv` Преобразует объекты процесса в последовательность строк CSV.</span><span class="sxs-lookup"><span data-stu-id="4372b-139">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="4372b-140">Параметр **path** указывает, что файл Processes.csv сохраняется в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4372b-140">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="4372b-141">Параметр- **Разделитель** задает точку с запятой для разделения строковых значений.</span><span class="sxs-lookup"><span data-stu-id="4372b-141">The **Delimiter** parameter specifies a semicolon to separate the string values.</span></span> <span data-ttu-id="4372b-142">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="4372b-142">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="4372b-143">`Get-Content`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4372b-143">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="4372b-144">Пример 4. экспорт процессов с использованием разделителя списка текущего языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="4372b-144">Example 4: Export processes using the current culture's list separator</span></span>

<span data-ttu-id="4372b-145">В этом примере **выполняется** получение объектов Process и экспорт объектов в файл.</span><span class="sxs-lookup"><span data-stu-id="4372b-145">This example gets **Process** objects and exports the objects to a file.</span></span> <span data-ttu-id="4372b-146">Разделитель является разделителем списка текущего языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="4372b-146">The delimiter is the current culture's list separator.</span></span>

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-Process | Export-Csv -Path .\Processes.csv -UseCulture -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","511","2203597099008","35364864","21979136","30048", ...
```

<span data-ttu-id="4372b-147">`Get-Culture`Командлет использует вложенные свойства **TextInfo** и **ListSeparator** и отображает текущий разделитель списка по умолчанию для текущего языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="4372b-147">The `Get-Culture` cmdlet uses the nested properties **TextInfo** and **ListSeparator** and displays the current culture's default list separator.</span></span> <span data-ttu-id="4372b-148">`Get-Process`Командлет получает объекты **Process** .</span><span class="sxs-lookup"><span data-stu-id="4372b-148">The `Get-Process` cmdlet gets **Process** objects.</span></span>
<span data-ttu-id="4372b-149">Объекты процесса отправляются по конвейеру в `Export-Csv` командлет.</span><span class="sxs-lookup"><span data-stu-id="4372b-149">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="4372b-150">`Export-Csv` Преобразует объекты процесса в последовательность строк CSV.</span><span class="sxs-lookup"><span data-stu-id="4372b-150">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="4372b-151">Параметр **path** указывает, что файл Processes.csv сохраняется в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4372b-151">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="4372b-152">Параметр **UseCulture** использует разделитель списка по умолчанию текущего языка и региональных параметров в качестве разделителя.</span><span class="sxs-lookup"><span data-stu-id="4372b-152">The **UseCulture** parameter uses the current culture's default list separator as the delimiter.</span></span> <span data-ttu-id="4372b-153">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="4372b-153">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="4372b-154">`Get-Content`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4372b-154">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="4372b-155">Пример 5. экспорт процессов с информацией о типах</span><span class="sxs-lookup"><span data-stu-id="4372b-155">Example 5: Export processes with type information</span></span>

<span data-ttu-id="4372b-156">В этом примере объясняется, как включить данные заголовка **#TYPE** в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="4372b-156">This example explains how to include the **#TYPE** header information in a CSV file.</span></span> <span data-ttu-id="4372b-157">По умолчанию в версиях, предшествовавших версии PowerShell 6,0, используется заголовок **#TYPE** .</span><span class="sxs-lookup"><span data-stu-id="4372b-157">The **#TYPE** header is the default in versions prior to PowerShell 6.0.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv
Get-Content -Path .\Processes.csv
```

```Output
#TYPE System.Diagnostics.Process
"Name","SI","Handles","VM","WS","PM","NPM","Path","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","507","2203595001856","35139584","20934656","29504", ...
```

<span data-ttu-id="4372b-158">`Get-Process`Командлет получает объекты **Process** .</span><span class="sxs-lookup"><span data-stu-id="4372b-158">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="4372b-159">Объекты процесса отправляются по конвейеру в `Export-Csv` командлет.</span><span class="sxs-lookup"><span data-stu-id="4372b-159">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="4372b-160">`Export-Csv` Преобразует объекты процесса в последовательность строк CSV.</span><span class="sxs-lookup"><span data-stu-id="4372b-160">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="4372b-161">Параметр **path** указывает, что файл Processes.csv сохраняется в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4372b-161">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="4372b-162">`Get-Content`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4372b-162">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="4372b-163">Пример 6. экспорт и добавление объектов в CSV-файл</span><span class="sxs-lookup"><span data-stu-id="4372b-163">Example 6: Export and append objects to a CSV file</span></span>

<span data-ttu-id="4372b-164">В этом примере описывается, как экспортировать объекты в CSV-файл и использовать параметр **append** для добавления объектов в существующий файл.</span><span class="sxs-lookup"><span data-stu-id="4372b-164">This example describes how to export objects to a CSV file and use the **Append** parameter to add objects to an existing file.</span></span>

```powershell
$AppService = (Get-Service -DisplayName *Application* | Select-Object -Property DisplayName, Status)
$AppService | Export-Csv -Path .\Services.Csv -NoTypeInformation
Get-Content -Path .\Services.Csv
$WinService = (Get-Service -DisplayName *Windows* | Select-Object -Property DisplayName, Status)
$WinService | Export-Csv -Path ./Services.csv -NoTypeInformation -Append
Get-Content -Path .\Services.Csv
```

```Output
"DisplayName","Status"
"Application Layer Gateway Service","Stopped"
"Application Identity","Running"
"Windows Audio Endpoint Builder","Running"
"Windows Audio","Running"
"Windows Event Log","Running"
```

<span data-ttu-id="4372b-165">`Get-Service`Командлет получает объекты службы.</span><span class="sxs-lookup"><span data-stu-id="4372b-165">The `Get-Service` cmdlet gets service objects.</span></span> <span data-ttu-id="4372b-166">Параметр **DisplayName** возвращает службы, содержащие слово «приложение».</span><span class="sxs-lookup"><span data-stu-id="4372b-166">The **DisplayName** parameter returns services that contain the word Application.</span></span> <span data-ttu-id="4372b-167">Объекты службы отправляются по конвейеру в `Select-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="4372b-167">The service objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="4372b-168">`Select-Object` использует параметр **Property** для задания свойств **DisplayName** и **Status** .</span><span class="sxs-lookup"><span data-stu-id="4372b-168">`Select-Object` uses the **Property** parameter to specify the **DisplayName** and **Status** properties.</span></span> <span data-ttu-id="4372b-169">`$AppService`Переменная хранит объекты.</span><span class="sxs-lookup"><span data-stu-id="4372b-169">The `$AppService` variable stores the objects.</span></span>

<span data-ttu-id="4372b-170">`$AppService`Объекты отправляются по конвейеру в `Export-Csv` командлет.</span><span class="sxs-lookup"><span data-stu-id="4372b-170">The `$AppService` objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="4372b-171">`Export-Csv` Преобразует объекты службы в последовательность строк CSV.</span><span class="sxs-lookup"><span data-stu-id="4372b-171">`Export-Csv` converts the service objects to a series of CSV strings.</span></span> <span data-ttu-id="4372b-172">Параметр **path** указывает, что файл Services.csv сохраняется в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4372b-172">The **Path** parameter specifies that the Services.csv file is saved in the current directory.</span></span> <span data-ttu-id="4372b-173">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="4372b-173">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="4372b-174">`Get-Content`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4372b-174">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

<span data-ttu-id="4372b-175">`Get-Service` `Select-Object` Командлеты и повторяются для служб, содержащих слово Windows.</span><span class="sxs-lookup"><span data-stu-id="4372b-175">The `Get-Service` and `Select-Object` cmdlets are repeated for services that contain the word Windows.</span></span> <span data-ttu-id="4372b-176">`$WinService`Переменная хранит объекты службы.</span><span class="sxs-lookup"><span data-stu-id="4372b-176">The `$WinService` variable stores the service objects.</span></span> <span data-ttu-id="4372b-177">`Export-Csv`Командлет использует параметр **append** , чтобы указать, что `$WinService` объекты добавляются в существующий файл Services.csv.</span><span class="sxs-lookup"><span data-stu-id="4372b-177">The `Export-Csv` cmdlet uses the **Append** parameter to specify that the `$WinService` objects are added to the existing Services.csv file.</span></span> <span data-ttu-id="4372b-178">`Get-Content`Командлет повторяется для вывода обновленного файла, содержащего добавленные данные.</span><span class="sxs-lookup"><span data-stu-id="4372b-178">The `Get-Content` cmdlet is repeated to display the updated file that includes the appended data.</span></span>

### <span data-ttu-id="4372b-179">Пример 7. командлет Format в конвейере создает непредвиденные результаты</span><span class="sxs-lookup"><span data-stu-id="4372b-179">Example 7: Format cmdlet within a pipeline creates unexpected results</span></span>

<span data-ttu-id="4372b-180">В этом примере показано, почему важно не использовать командлет Format в конвейере.</span><span class="sxs-lookup"><span data-stu-id="4372b-180">This example shows why it is important not to use a format cmdlet within a pipeline.</span></span> <span data-ttu-id="4372b-181">При получении непредвиденных выходных данных устраните неполадки синтаксиса конвейера.</span><span class="sxs-lookup"><span data-stu-id="4372b-181">When unexpected output is received, troubleshoot the pipeline syntax.</span></span>

```powershell
Get-Date | Select-Object -Property DateTime, Day, DayOfWeek, DayOfYear |
 Export-Csv -Path .\DateTime.csv -NoTypeInformation
Get-Content -Path .\DateTime.csv
```

```Output
"DateTime","Day","DayOfWeek","DayOfYear"
"Wednesday, January 2, 2019 14:59:34","2","Wednesday","2"
```

```powershell
Get-Date | Format-Table -Property DateTime, Day, DayOfWeek, DayOfYear |
 Export-Csv -Path .\FTDateTime.csv -NoTypeInformation
Get-Content -Path .\FTDateTime.csv
```

```Output
"ClassId2e4f51ef21dd47e99d3c952918aff9cd","pageHeaderEntry","pageFooterEntry","autosizeInfo", ...
"033ecb2bc07a4d43b5ef94ed5a35d280",,,,"Microsoft.PowerShell.Commands.Internal.Format. ...
"9e210fe47d09416682b841769c78b8a3",,,,,
"27c87ef9bbda4f709f6b4002fa4af63c",,,,,
"4ec4f0187cb04f4cb6973460dfe252df",,,,,
"cf522b78d86c486691226b40aa69e95c",,,,,
```

<span data-ttu-id="4372b-182">`Get-Date`Командлет возвращает объект **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="4372b-182">The `Get-Date` cmdlet gets the **DateTime** object.</span></span> <span data-ttu-id="4372b-183">Объект отправляется по конвейеру в `Select-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="4372b-183">The object is sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="4372b-184">`Select-Object` использует параметр **Property** для выбора подмножества свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="4372b-184">`Select-Object` uses the **Property** parameter to select a subset of object properties.</span></span> <span data-ttu-id="4372b-185">Объект отправляется по конвейеру в `Export-Csv` командлет.</span><span class="sxs-lookup"><span data-stu-id="4372b-185">The object is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="4372b-186">`Export-Csv` Преобразует объект в формат CSV.</span><span class="sxs-lookup"><span data-stu-id="4372b-186">`Export-Csv` converts the object to a CSV format.</span></span> <span data-ttu-id="4372b-187">Параметр **path** указывает, что файл DateTime.csv сохраняется в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4372b-187">The **Path** parameter specifies that the DateTime.csv file is saved in the current directory.</span></span> <span data-ttu-id="4372b-188">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="4372b-188">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="4372b-189">`Get-Content`Командлет использует параметр **path** для вывода CSV-файла, расположенного в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4372b-189">The `Get-Content` cmdlet uses the **Path** parameter to display the CSV file located in the current directory.</span></span>

<span data-ttu-id="4372b-190">При `Format-Table` использовании командлета в конвейере для выбора свойств получены непредвиденные результаты.</span><span class="sxs-lookup"><span data-stu-id="4372b-190">When the `Format-Table` cmdlet is used within the pipeline to select properties unexpected results are received.</span></span> <span data-ttu-id="4372b-191">`Format-Table` отправляет объекты формата таблицы по конвейеру в `Export-Csv` командлет, а не в объект **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="4372b-191">`Format-Table` sends table format objects down the pipeline to the `Export-Csv` cmdlet rather than the **DateTime** object.</span></span> <span data-ttu-id="4372b-192">`Export-Csv` Преобразует объекты формата таблицы в последовательность строк CSV.</span><span class="sxs-lookup"><span data-stu-id="4372b-192">`Export-Csv` converts the table format objects to a series of CSV strings.</span></span> <span data-ttu-id="4372b-193">`Get-Content`Командлет ОТОБРАЖАЕТ CSV-файл, содержащий объекты формата таблицы.</span><span class="sxs-lookup"><span data-stu-id="4372b-193">The `Get-Content` cmdlet displays the CSV file which contains the table format objects.</span></span>

### <span data-ttu-id="4372b-194">Пример 8. Использование параметра Force для перезаписи файлов, которые доступны только для чтения</span><span class="sxs-lookup"><span data-stu-id="4372b-194">Example 8: Using the Force parameter to overwrite read-only files</span></span>

<span data-ttu-id="4372b-195">В этом примере создается пустой файл только для чтения, а для обновления файла используется параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="4372b-195">This example creates an empty, read-only file and uses the **Force** parameter to update the file.</span></span>

```powershell
New-Item -Path .\ReadOnly.csv -ItemType File
Set-ItemProperty -Path .\ReadOnly.csv -Name IsReadOnly -Value $true
Get-Process | Export-Csv -Path .\ReadOnly.csv -NoTypeInformation
```

```Output
Export-Csv : Access to the path 'C:\ReadOnly.csv' is denied.
At line:1 char:15
+ Get-Process | Export-Csv -Path .\ReadOnly.csv -NoTypeInformation
+               ~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : OpenError: (:) [Export-Csv], UnauthorizedAccessException
+ FullyQualifiedErrorId : FileOpenFailure,Microsoft.PowerShell.Commands.ExportCsvCommand
```

```powershell
Get-Process | Export-Csv -Path .\ReadOnly.csv -NoTypeInformation -Force
Get-Content -Path .\ReadOnly.csv
```

```Output
"Name";"SI";"Handles";"VM";"WS";"PM";"NPM";"Path";"Parent";"Company";"CPU";"FileVersion"; ...
"ApplicationFrameHost";"4";"509";"2203595321344";"34807808";"21770240";"29504"; ...
```

<span data-ttu-id="4372b-196">`New-Item`Командлет использует параметры **path** и **ItemType** для создания файла ReadOnly.csv в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4372b-196">The `New-Item` cmdlet uses the **Path** and **ItemType** parameters to create the ReadOnly.csv file in the current directory.</span></span> <span data-ttu-id="4372b-197">`Set-ItemProperty`Командлет использует параметры **Name** и **value** , чтобы изменить свойство **IsReadOnly** для файла на true.</span><span class="sxs-lookup"><span data-stu-id="4372b-197">The `Set-ItemProperty` cmdlet uses the **Name** and **Value** parameters to change the file's **IsReadOnly** property to true.</span></span> <span data-ttu-id="4372b-198">`Get-Process`Командлет получает объекты **Process** .</span><span class="sxs-lookup"><span data-stu-id="4372b-198">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="4372b-199">Объекты процесса отправляются по конвейеру в `Export-Csv` командлет.</span><span class="sxs-lookup"><span data-stu-id="4372b-199">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="4372b-200">`Export-Csv` Преобразует объекты процесса в последовательность строк CSV.</span><span class="sxs-lookup"><span data-stu-id="4372b-200">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="4372b-201">Параметр **path** указывает, что файл ReadOnly.csv сохраняется в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4372b-201">The **Path** parameter specifies that the ReadOnly.csv file is saved in the current directory.</span></span> <span data-ttu-id="4372b-202">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="4372b-202">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="4372b-203">Выходные данные показывают, что файл не записан, так как доступ запрещен.</span><span class="sxs-lookup"><span data-stu-id="4372b-203">The output shows that the file is not written because access is denied.</span></span>

<span data-ttu-id="4372b-204">Параметр **Force** добавляется в командлет, `Export-Csv` чтобы принудительно выполнить запись экспорта в файл.</span><span class="sxs-lookup"><span data-stu-id="4372b-204">The **Force** parameter is added to the `Export-Csv` cmdlet to force the export to write to the file.</span></span> <span data-ttu-id="4372b-205">`Get-Content`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4372b-205">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="4372b-206">Пример 9. Использование параметра Force с Append</span><span class="sxs-lookup"><span data-stu-id="4372b-206">Example 9: Using the Force parameter with Append</span></span>

<span data-ttu-id="4372b-207">В этом примере показано, как использовать параметры **Force** и **append** .</span><span class="sxs-lookup"><span data-stu-id="4372b-207">This example shows how to use the **Force** and **Append** parameters.</span></span> <span data-ttu-id="4372b-208">Если эти параметры объединены, несоответствующие свойства объекта могут быть записаны в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="4372b-208">When these parameters are combined, mismatched object properties can be written to a CSV file.</span></span>

```powershell
$Content = [PSCustomObject]@{Name = 'PowerShell Core'; Version = '6.0'}
$Content | Export-Csv -Path .\ParmFile.csv -NoTypeInformation
$AdditionalContent = [PSCustomObject]@{Name = 'Windows PowerShell'; Edition = 'Desktop'}
$AdditionalContent | Export-Csv -Path .\ParmFile.csv -NoTypeInformation -Append
```

```Output
Export-Csv : Cannot append CSV content to the following file: ParmFile.csv.
The appended object does not have a property that corresponds to the following column:
Version. To continue with mismatched properties, add the -Force parameter, and then retry
 the command.
At line:1 char:22
+ $AdditionalContent | Export-Csv -Path .\ParmFile.csv -NoTypeInformation -Append
+                      ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : InvalidData: (Version:String) [Export-Csv], InvalidOperationException
+ FullyQualifiedErrorId : CannotAppendCsvWithMismatchedPropertyNames,Microsoft.PowerShell. ...
```

```powershell
$AdditionalContent | Export-Csv -Path .\ParmFile.csv -NoTypeInformation -Append -Force
Import-Csv -Path .\ParmFile.csv
```

```Output
Name               Version
----               -------
PowerShell Core    6.0
Windows PowerShell
```

<span data-ttu-id="4372b-209">Выражение создает **PSCustomObject** с свойствами **Name** и **Version** .</span><span class="sxs-lookup"><span data-stu-id="4372b-209">An expression creates the **PSCustomObject** with **Name** and **Version** properties.</span></span> <span data-ttu-id="4372b-210">Значения хранятся в `$Content` переменной.</span><span class="sxs-lookup"><span data-stu-id="4372b-210">The values are stored in the `$Content` variable.</span></span> <span data-ttu-id="4372b-211">`$Content`Переменная отправляется в командлет по конвейеру `Export-Csv` .</span><span class="sxs-lookup"><span data-stu-id="4372b-211">The `$Content` variable is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="4372b-212">`Export-Csv` использует параметр **path** и сохраняет файл ParmFile.csv в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4372b-212">`Export-Csv` uses the **Path** parameter and saves the ParmFile.csv file in the current directory.</span></span> <span data-ttu-id="4372b-213">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="4372b-213">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

<span data-ttu-id="4372b-214">Другое выражение создает **PSCustomObject** с свойствами **Name** и **Edition** .</span><span class="sxs-lookup"><span data-stu-id="4372b-214">Another expression creates a **PSCustomObject** with the **Name** and **Edition** properties.</span></span> <span data-ttu-id="4372b-215">Значения хранятся в `$AdditionalContent` переменной.</span><span class="sxs-lookup"><span data-stu-id="4372b-215">The values are stored in the `$AdditionalContent` variable.</span></span> <span data-ttu-id="4372b-216">`$AdditionalContent`Переменная отправляется в командлет по конвейеру `Export-Csv` .</span><span class="sxs-lookup"><span data-stu-id="4372b-216">The `$AdditionalContent` variable is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="4372b-217">Параметр **append** используется для добавления данных в файл.</span><span class="sxs-lookup"><span data-stu-id="4372b-217">The **Append** parameter is used to add the data to the file.</span></span> <span data-ttu-id="4372b-218">Добавление завершается ошибкой из-за несоответствия имени свойства **версии** и **выпуска**.</span><span class="sxs-lookup"><span data-stu-id="4372b-218">The append fails because there is a property name mismatch between **Version** and **Edition**.</span></span>

<span data-ttu-id="4372b-219">`Export-Csv`Параметр **Force** командлета используется для принудительной записи экспорта в файл.</span><span class="sxs-lookup"><span data-stu-id="4372b-219">The `Export-Csv` cmdlet **Force** parameter is used to force the export to write to the file.</span></span> <span data-ttu-id="4372b-220">Свойство **Edition** отбрасывается.</span><span class="sxs-lookup"><span data-stu-id="4372b-220">The **Edition** property is discarded.</span></span> <span data-ttu-id="4372b-221">`Import-Csv`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4372b-221">The `Import-Csv` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

## <span data-ttu-id="4372b-222">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4372b-222">PARAMETERS</span></span>

### <span data-ttu-id="4372b-223">— Добавление</span><span class="sxs-lookup"><span data-stu-id="4372b-223">-Append</span></span>

<span data-ttu-id="4372b-224">Используйте этот параметр, чтобы `Export-CSV` Добавить выходные данные CSV в конец указанного файла.</span><span class="sxs-lookup"><span data-stu-id="4372b-224">Use this parameter so that `Export-CSV` adds CSV output to the end of the specified file.</span></span> <span data-ttu-id="4372b-225">Без этого параметра `Export-CSV` заменяет содержимое файла без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="4372b-225">Without this parameter, `Export-CSV` replaces the file contents without warning.</span></span>

<span data-ttu-id="4372b-226">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="4372b-226">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="4372b-227">-Delimiter</span><span class="sxs-lookup"><span data-stu-id="4372b-227">-Delimiter</span></span>

<span data-ttu-id="4372b-228">Указывает разделитель для значений свойств.</span><span class="sxs-lookup"><span data-stu-id="4372b-228">Specifies a delimiter to separate the property values.</span></span> <span data-ttu-id="4372b-229">Значение по умолчанию — запятая ( `,` ).</span><span class="sxs-lookup"><span data-stu-id="4372b-229">The default is a comma (`,`).</span></span> <span data-ttu-id="4372b-230">Введите символ, например двоеточие ( `:` ).</span><span class="sxs-lookup"><span data-stu-id="4372b-230">Enter a character, such as a colon (`:`).</span></span> <span data-ttu-id="4372b-231">Чтобы указать точку с запятой ( `;` ), заключите ее в кавычки.</span><span class="sxs-lookup"><span data-stu-id="4372b-231">To specify a semicolon (`;`), enclose it in quotation marks.</span></span>

```yaml
Type: System.Char
Parameter Sets: Delimiter
Aliases:

Required: False
Position: 1
Default value: comma (,)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4372b-232">-Encoding</span><span class="sxs-lookup"><span data-stu-id="4372b-232">-Encoding</span></span>

<span data-ttu-id="4372b-233">Указывает тип кодировки для целевого файла.</span><span class="sxs-lookup"><span data-stu-id="4372b-233">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="4372b-234">Значение по умолчанию — `ASCII`.</span><span class="sxs-lookup"><span data-stu-id="4372b-234">The default value is `ASCII`.</span></span>

<span data-ttu-id="4372b-235">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="4372b-235">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="4372b-236">`ASCII` Использует кодировку ASCII (7-разрядных).</span><span class="sxs-lookup"><span data-stu-id="4372b-236">`ASCII` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="4372b-237">`BigEndianUnicode` Использует UTF-16 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="4372b-237">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="4372b-238">`Default` Использует кодировку, соответствующую активной кодовой странице системы (обычно ANSI).</span><span class="sxs-lookup"><span data-stu-id="4372b-238">`Default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="4372b-239">`OEM` Использует кодировку, соответствующую текущей кодовой странице OEM системы.</span><span class="sxs-lookup"><span data-stu-id="4372b-239">`OEM` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="4372b-240">`Unicode` Использует UTF-16 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="4372b-240">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="4372b-241">`UTF7` Использует UTF-7.</span><span class="sxs-lookup"><span data-stu-id="4372b-241">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="4372b-242">`UTF8` Использует UTF-8.</span><span class="sxs-lookup"><span data-stu-id="4372b-242">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="4372b-243">`UTF32` Использует UTF-32 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="4372b-243">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, Default, OEM, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: ASCII
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4372b-244">-Force</span><span class="sxs-lookup"><span data-stu-id="4372b-244">-Force</span></span>

<span data-ttu-id="4372b-245">Этот параметр позволяет `Export-Csv` перезаписывать файлы с атрибутом " **только для чтения** ".</span><span class="sxs-lookup"><span data-stu-id="4372b-245">This parameter allows `Export-Csv` to overwrite files with the **Read Only** attribute.</span></span>

<span data-ttu-id="4372b-246">При объединении параметров **Force** и **append** объекты, содержащие несовпадающие свойства, могут быть записаны в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="4372b-246">When **Force** and **Append** parameters are combined, objects that contain mismatched properties can be written to a CSV file.</span></span> <span data-ttu-id="4372b-247">В файл записываются только те свойства, которые соответствуют.</span><span class="sxs-lookup"><span data-stu-id="4372b-247">Only the properties that match are written to the file.</span></span> <span data-ttu-id="4372b-248">Несоответствующие свойства отбрасываются.</span><span class="sxs-lookup"><span data-stu-id="4372b-248">The mismatched properties are discarded.</span></span>

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

### <span data-ttu-id="4372b-249">-InputObject</span><span class="sxs-lookup"><span data-stu-id="4372b-249">-InputObject</span></span>

<span data-ttu-id="4372b-250">Указывает экспортируемые объекты в качестве строк CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="4372b-250">Specifies the objects to export as CSV strings.</span></span> <span data-ttu-id="4372b-251">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="4372b-251">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="4372b-252">Также можно передать объекты в `Export-CSV` .</span><span class="sxs-lookup"><span data-stu-id="4372b-252">You can also pipe objects to `Export-CSV`.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4372b-253">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="4372b-253">-LiteralPath</span></span>

<span data-ttu-id="4372b-254">Указывает путь к выходному CSV-файлу.</span><span class="sxs-lookup"><span data-stu-id="4372b-254">Specifies the path to the CSV output file.</span></span> <span data-ttu-id="4372b-255">В отличие от параметра **Path**, значение параметра **LiteralPath** используется в точности так, как вводится.</span><span class="sxs-lookup"><span data-stu-id="4372b-255">Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="4372b-256">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="4372b-256">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="4372b-257">Если путь содержит escape-символы, используйте одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="4372b-257">If the path includes escape characters, use single quotation marks.</span></span> <span data-ttu-id="4372b-258">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="4372b-258">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4372b-259">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="4372b-259">-NoClobber</span></span>

<span data-ttu-id="4372b-260">Используйте этот параметр, чтобы `Export-CSV` не перезаписать существующий файл.</span><span class="sxs-lookup"><span data-stu-id="4372b-260">Use this parameter so that `Export-CSV` does not overwrite an existing file.</span></span> <span data-ttu-id="4372b-261">По умолчанию, если файл существует по указанному пути, `Export-CSV` перезаписывает файл без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="4372b-261">By default, if the file exists in the specified path, `Export-CSV` overwrites the file without warning.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4372b-262">-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="4372b-262">-NoTypeInformation</span></span>

<span data-ttu-id="4372b-263">Удаляет заголовок сведений о **#TYPE** из выходных данных.</span><span class="sxs-lookup"><span data-stu-id="4372b-263">Removes the **#TYPE** information header from the output.</span></span> <span data-ttu-id="4372b-264">Этот параметр стал значением по умолчанию в PowerShell 6,0 и включен для обеспечения обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="4372b-264">This parameter became the default in PowerShell 6.0 and is included for backwards compatibility.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NTI

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4372b-265">-Path</span><span class="sxs-lookup"><span data-stu-id="4372b-265">-Path</span></span>

<span data-ttu-id="4372b-266">Обязательный параметр, указывающий расположение для сохранения выходного CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="4372b-266">A required parameter that specifies the location to save the CSV output file.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4372b-267">-UseCulture</span><span class="sxs-lookup"><span data-stu-id="4372b-267">-UseCulture</span></span>

<span data-ttu-id="4372b-268">Использует разделитель списка для текущего языка и региональных параметров в качестве разделителя элементов.</span><span class="sxs-lookup"><span data-stu-id="4372b-268">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="4372b-269">Чтобы найти разделитель списка для языка и региональных параметров, используйте следующую команду: `(Get-Culture).TextInfo.ListSeparator` .</span><span class="sxs-lookup"><span data-stu-id="4372b-269">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UseCulture
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4372b-270">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4372b-270">-Confirm</span></span>

<span data-ttu-id="4372b-271">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="4372b-271">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4372b-272">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4372b-272">-WhatIf</span></span>

<span data-ttu-id="4372b-273">Предотвращает обработку командлета или внесение изменений.</span><span class="sxs-lookup"><span data-stu-id="4372b-273">Prevents the cmdlet from being processed or making changes.</span></span> <span data-ttu-id="4372b-274">Выходные данные показывают, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="4372b-274">The output shows what would happen if the cmdlet were run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4372b-275">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="4372b-275">CommonParameters</span></span>

<span data-ttu-id="4372b-276">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4372b-276">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4372b-277">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4372b-277">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4372b-278">Входные данные</span><span class="sxs-lookup"><span data-stu-id="4372b-278">INPUTS</span></span>

### <span data-ttu-id="4372b-279">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="4372b-279">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="4372b-280">Любой объект с адаптером системы расширенного типа (ETS) можно передать в `Export-CSV` .</span><span class="sxs-lookup"><span data-stu-id="4372b-280">You can pipe any object with an Extended Type System (ETS) adapter to `Export-CSV`.</span></span>

## <span data-ttu-id="4372b-281">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="4372b-281">OUTPUTS</span></span>

### <span data-ttu-id="4372b-282">System.String</span><span class="sxs-lookup"><span data-stu-id="4372b-282">System.String</span></span>

<span data-ttu-id="4372b-283">Список CSV-файлов отправляется в файл, указанный в параметре Path.</span><span class="sxs-lookup"><span data-stu-id="4372b-283">The CSV list is sent to the file designated in the Path parameter.</span></span>

## <span data-ttu-id="4372b-284">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="4372b-284">NOTES</span></span>

<span data-ttu-id="4372b-285">`Export-CSV`Командлет преобразует объекты, которые вы отправляете, в последовательность строк CSV и сохраняет их в указанном текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="4372b-285">The `Export-CSV` cmdlet converts the objects that you submit into a series of CSV strings and saves them in the specified text file.</span></span> <span data-ttu-id="4372b-286">Можно использовать `Export-CSV` для сохранения объектов в CSV-файле, а затем с помощью `Import-Csv` командлета создавать объекты из файла CSV.</span><span class="sxs-lookup"><span data-stu-id="4372b-286">You can use `Export-CSV` to save objects in a CSV file and then use the `Import-Csv` cmdlet to create objects from the CSV file.</span></span>

<span data-ttu-id="4372b-287">В CSV-файле каждый объект представлен списком значений свойств объекта с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="4372b-287">In the CSV file, each object is represented by a comma-separated list of the property values of the object.</span></span> <span data-ttu-id="4372b-288">Значения свойств преобразуются в строки с помощью метода **ToString ()** .</span><span class="sxs-lookup"><span data-stu-id="4372b-288">The property values are converted to strings using the **ToString()** method.</span></span> <span data-ttu-id="4372b-289">Строки представлены именем значения свойства.</span><span class="sxs-lookup"><span data-stu-id="4372b-289">The strings are represented by the property value name.</span></span> <span data-ttu-id="4372b-290">Export-CSV не экспортирует методы объекта.</span><span class="sxs-lookup"><span data-stu-id="4372b-290">\`Export-CSV does not export the methods of the object.</span></span>

<span data-ttu-id="4372b-291">Строки CSV выводятся следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4372b-291">The CSV strings are output as follows:</span></span>

- <span data-ttu-id="4372b-292">По умолчанию первая строка содержит заголовок **#TYPE** сведений, за которым следует полное имя типа объекта.</span><span class="sxs-lookup"><span data-stu-id="4372b-292">By default the first string contains the **#TYPE** information header followed by the object type's fully qualified name.</span></span> <span data-ttu-id="4372b-293">Например, **#TYPE System. Diagnostics. Process**.</span><span class="sxs-lookup"><span data-stu-id="4372b-293">For example, **#TYPE System.Diagnostics.Process**.</span></span>
- <span data-ttu-id="4372b-294">Если используется **NoTypeInformation** , первая строка включает заголовки столбцов.</span><span class="sxs-lookup"><span data-stu-id="4372b-294">If **NoTypeInformation** is used the first string includes the column headers.</span></span> <span data-ttu-id="4372b-295">Заголовки содержат имена свойств первого объекта в виде списка с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="4372b-295">The headers contain the first object's property names as a comma-separated list.</span></span>
- <span data-ttu-id="4372b-296">Остальные строки содержат разделенные запятыми списки значений свойств каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="4372b-296">The remaining strings contain comma-separated lists of each object's property values.</span></span>

<span data-ttu-id="4372b-297">При отправке нескольких объектов в `Export-CSV` `Export-CSV` файл упорядочивается по свойствам первого отправленного объекта.</span><span class="sxs-lookup"><span data-stu-id="4372b-297">When you submit multiple objects to `Export-CSV`, `Export-CSV` organizes the file based on the properties of the first object that you submit.</span></span> <span data-ttu-id="4372b-298">Если остальные объекты не имеют одного из указанных свойств, значение этого свойства для объекта будет пустым, то есть представлено двумя идущими подряд запятыми.</span><span class="sxs-lookup"><span data-stu-id="4372b-298">If the remaining objects do not have one of the specified properties, the property value of that object is null, as represented by two consecutive commas.</span></span> <span data-ttu-id="4372b-299">Если оставшиеся объекты содержат дополнительные свойства, их значения не включаются в файл.</span><span class="sxs-lookup"><span data-stu-id="4372b-299">If the remaining objects have additional properties, those property values are not included in the file.</span></span>

<span data-ttu-id="4372b-300">Командлет можно использовать `Import-Csv` для повторного создания объектов из строк CSV в файлах.</span><span class="sxs-lookup"><span data-stu-id="4372b-300">You can use the `Import-Csv` cmdlet to recreate objects from the CSV strings in the files.</span></span> <span data-ttu-id="4372b-301">Полученные объекты являются версиями CSV-файлов исходных объектов, которые состоят из представлений строк значений свойств без методов.</span><span class="sxs-lookup"><span data-stu-id="4372b-301">The resulting objects are CSV versions of the original objects that consist of string representations of the property values and no methods.</span></span>

<span data-ttu-id="4372b-302">`ConvertTo-Csv` `ConvertFrom-Csv` Командлеты и преобразуют объекты в строки CSV и из строк CSV.</span><span class="sxs-lookup"><span data-stu-id="4372b-302">The `ConvertTo-Csv` and `ConvertFrom-Csv` cmdlets convert objects to CSV strings and from CSV strings.</span></span> <span data-ttu-id="4372b-303">`Export-CSV` совпадает с `ConvertTo-CSV` , за исключением того, что строки CSV сохраняются в файле.</span><span class="sxs-lookup"><span data-stu-id="4372b-303">`Export-CSV` is the same as `ConvertTo-CSV`, except that it saves the CSV strings in a file.</span></span>

## <span data-ttu-id="4372b-304">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="4372b-304">RELATED LINKS</span></span>

[<span data-ttu-id="4372b-305">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="4372b-305">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="4372b-306">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="4372b-306">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="4372b-307">Format-Table</span><span class="sxs-lookup"><span data-stu-id="4372b-307">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="4372b-308">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="4372b-308">Import-Csv</span></span>](Import-Csv.md)

[<span data-ttu-id="4372b-309">Select-Object</span><span class="sxs-lookup"><span data-stu-id="4372b-309">Select-Object</span></span>](Select-Object.md)
