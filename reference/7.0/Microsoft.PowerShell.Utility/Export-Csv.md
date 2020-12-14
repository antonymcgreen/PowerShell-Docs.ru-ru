---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-csv?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Csv
ms.openlocfilehash: bb2d077b3584d4501db00a927b83034d37dceaec
ms.sourcegitcommit: 560a9f3c3148acab4655e91e8b07745ab74d5d26
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2020
ms.locfileid: "96913365"
---
# <span data-ttu-id="0fddd-102">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="0fddd-102">Export-Csv</span></span>

## <span data-ttu-id="0fddd-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0fddd-103">SYNOPSIS</span></span>
<span data-ttu-id="0fddd-104">Преобразует объекты в последовательность строк с разделителями-запятыми (CSV) и сохраняет строки в файл.</span><span class="sxs-lookup"><span data-stu-id="0fddd-104">Converts objects into a series of comma-separated value (CSV) strings and saves the strings to a file.</span></span>

## <span data-ttu-id="0fddd-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0fddd-105">SYNTAX</span></span>

### <span data-ttu-id="0fddd-106">Delimiter (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="0fddd-106">Delimiter (Default)</span></span>

```
Export-Csv -InputObject <PSObject> [[-Path] <String>] [-LiteralPath <String>] [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-Append] [[-Delimiter] <Char>] [-IncludeTypeInformation]
 [-NoTypeInformation] [-QuoteFields <String[]>] [-UseQuotes <QuoteKind>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="0fddd-107">UseCulture</span><span class="sxs-lookup"><span data-stu-id="0fddd-107">UseCulture</span></span>

```
Export-Csv -InputObject <PSObject> [[-Path] <String>] [-LiteralPath <String>] [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-Append] [-UseCulture] [-IncludeTypeInformation] [-NoTypeInformation]
 [-QuoteFields <String[]>] [-UseQuotes <QuoteKind>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0fddd-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0fddd-108">DESCRIPTION</span></span>

<span data-ttu-id="0fddd-109">`Export-CSV`Командлет создает CSV-файл объектов, которые вы отправляете.</span><span class="sxs-lookup"><span data-stu-id="0fddd-109">The `Export-CSV` cmdlet creates a CSV file of the objects that you submit.</span></span> <span data-ttu-id="0fddd-110">Каждый объект представляет собой строку, содержащую разделенный запятыми список значений свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="0fddd-110">Each object is a row that includes a comma-separated list of the object's property values.</span></span> <span data-ttu-id="0fddd-111">С помощью `Export-CSV` командлета можно создавать электронные таблицы и обмениваться данными с программами, которые принимают CSV-файлы в качестве входных.</span><span class="sxs-lookup"><span data-stu-id="0fddd-111">You can use the `Export-CSV` cmdlet to create spreadsheets and share data with programs that accept CSV files as input.</span></span>

<span data-ttu-id="0fddd-112">Не форматируйте объекты перед их отправкой в `Export-CSV` командлет.</span><span class="sxs-lookup"><span data-stu-id="0fddd-112">Do not format objects before sending them to the `Export-CSV` cmdlet.</span></span> <span data-ttu-id="0fddd-113">Если `Export-CSV` получает отформатированные объекты, CSV-файл содержит свойства форматирования, а не свойства объекта.</span><span class="sxs-lookup"><span data-stu-id="0fddd-113">If `Export-CSV` receives formatted objects the CSV file contains the format properties rather than the object properties.</span></span> <span data-ttu-id="0fddd-114">Чтобы экспортировать только выбранные свойства объекта, используйте `Select-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="0fddd-114">To export only selected properties of an object, use the `Select-Object` cmdlet.</span></span>

## <span data-ttu-id="0fddd-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="0fddd-115">EXAMPLES</span></span>

### <span data-ttu-id="0fddd-116">Пример 1. экспорт свойств процесса в CSV-файл</span><span class="sxs-lookup"><span data-stu-id="0fddd-116">Example 1: Export process properties to a CSV file</span></span>

<span data-ttu-id="0fddd-117">В этом примере выбираются объекты **Process** с конкретными свойствами, экспортируются объекты в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="0fddd-117">This example selects **Process** objects with specific properties, exports the objects to a CSV file.</span></span>

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

<span data-ttu-id="0fddd-118">`Get-Process`Командлет возвращает объекты **процесса** .</span><span class="sxs-lookup"><span data-stu-id="0fddd-118">The `Get-Process` cmdlet gets the **Process** objects.</span></span> <span data-ttu-id="0fddd-119">Параметр **Name** фильтрует выходные данные, чтобы включить только объекты процесса WmiPrvSE.</span><span class="sxs-lookup"><span data-stu-id="0fddd-119">The **Name** parameter filters the output to include only the WmiPrvSE process objects.</span></span> <span data-ttu-id="0fddd-120">Объекты процесса отправляются по конвейеру в `Select-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="0fddd-120">The process objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="0fddd-121">`Select-Object` использует параметр **Property** для выбора подмножества свойств объекта процесса.</span><span class="sxs-lookup"><span data-stu-id="0fddd-121">`Select-Object` uses the **Property** parameter to select a subset of process object properties.</span></span> <span data-ttu-id="0fddd-122">Объекты процесса отправляются по конвейеру в `Export-Csv` командлет.</span><span class="sxs-lookup"><span data-stu-id="0fddd-122">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="0fddd-123">`Export-Csv` Преобразует объекты процесса в последовательность строк CSV.</span><span class="sxs-lookup"><span data-stu-id="0fddd-123">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="0fddd-124">Параметр **path** указывает, что файл WmiData.csv сохраняется в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="0fddd-124">The **Path** parameter specifies that the WmiData.csv file is saved in the current directory.</span></span> <span data-ttu-id="0fddd-125">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="0fddd-125">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="0fddd-126">`Import-Csv`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="0fddd-126">The `Import-Csv` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="0fddd-127">Пример 2. экспорт процессов в файл с разделителями-запятыми</span><span class="sxs-lookup"><span data-stu-id="0fddd-127">Example 2: Export processes to a comma-delimited file</span></span>

<span data-ttu-id="0fddd-128">В этом примере **выполняется** получение объектов Process и экспорт объектов в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="0fddd-128">This example gets **Process** objects and exports the objects to a CSV file.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","511","2203597099008","35364864","21979136","30048", ...
```

<span data-ttu-id="0fddd-129">`Get-Process`Командлет получает объекты **Process** .</span><span class="sxs-lookup"><span data-stu-id="0fddd-129">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="0fddd-130">Объекты процесса отправляются по конвейеру в `Export-Csv` командлет.</span><span class="sxs-lookup"><span data-stu-id="0fddd-130">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="0fddd-131">`Export-Csv` Преобразует объекты процесса в последовательность строк CSV.</span><span class="sxs-lookup"><span data-stu-id="0fddd-131">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="0fddd-132">Параметр **path** указывает, что файл Processes.csv сохраняется в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="0fddd-132">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="0fddd-133">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="0fddd-133">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="0fddd-134">`Get-Content`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="0fddd-134">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="0fddd-135">Пример 3. экспорт процессов в файл с разделителями-запятыми</span><span class="sxs-lookup"><span data-stu-id="0fddd-135">Example 3: Export processes to a semicolon delimited file</span></span>

<span data-ttu-id="0fddd-136">В этом примере **выполняется** получение объектов Process и экспорт объектов в файл с разделителем в виде точки с запятой.</span><span class="sxs-lookup"><span data-stu-id="0fddd-136">This example gets **Process** objects and exports the objects to a file with a semicolon delimiter.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -Delimiter ';' -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name";"SI";"Handles";"VM";"WS";"PM";"NPM";"Path";"Parent";"Company";"CPU";"FileVersion"; ...
"ApplicationFrameHost";"4";"509";"2203595321344";"34807808";"21770240";"29504"; ...
```

<span data-ttu-id="0fddd-137">`Get-Process`Командлет получает объекты **Process** .</span><span class="sxs-lookup"><span data-stu-id="0fddd-137">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="0fddd-138">Объекты процесса отправляются по конвейеру в `Export-Csv` командлет.</span><span class="sxs-lookup"><span data-stu-id="0fddd-138">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="0fddd-139">`Export-Csv` Преобразует объекты процесса в последовательность строк CSV.</span><span class="sxs-lookup"><span data-stu-id="0fddd-139">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="0fddd-140">Параметр **path** указывает, что файл Processes.csv сохраняется в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="0fddd-140">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="0fddd-141">Параметр- **Разделитель** задает точку с запятой для разделения строковых значений.</span><span class="sxs-lookup"><span data-stu-id="0fddd-141">The **Delimiter** parameter specifies a semicolon to separate the string values.</span></span> <span data-ttu-id="0fddd-142">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="0fddd-142">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="0fddd-143">`Get-Content`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="0fddd-143">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="0fddd-144">Пример 4. экспорт процессов с использованием разделителя списка текущего языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="0fddd-144">Example 4: Export processes using the current culture's list separator</span></span>

<span data-ttu-id="0fddd-145">В этом примере **выполняется** получение объектов Process и экспорт объектов в файл.</span><span class="sxs-lookup"><span data-stu-id="0fddd-145">This example gets **Process** objects and exports the objects to a file.</span></span> <span data-ttu-id="0fddd-146">Разделитель является разделителем списка текущего языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="0fddd-146">The delimiter is the current culture's list separator.</span></span>

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-Process | Export-Csv -Path .\Processes.csv -UseCulture -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","511","2203597099008","35364864","21979136","30048", ...
```

<span data-ttu-id="0fddd-147">`Get-Culture`Командлет использует вложенные свойства **TextInfo** и **ListSeparator** и отображает текущий разделитель списка по умолчанию для текущего языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="0fddd-147">The `Get-Culture` cmdlet uses the nested properties **TextInfo** and **ListSeparator** and displays the current culture's default list separator.</span></span> <span data-ttu-id="0fddd-148">`Get-Process`Командлет получает объекты **Process** .</span><span class="sxs-lookup"><span data-stu-id="0fddd-148">The `Get-Process` cmdlet gets **Process** objects.</span></span>
<span data-ttu-id="0fddd-149">Объекты процесса отправляются по конвейеру в `Export-Csv` командлет.</span><span class="sxs-lookup"><span data-stu-id="0fddd-149">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="0fddd-150">`Export-Csv` Преобразует объекты процесса в последовательность строк CSV.</span><span class="sxs-lookup"><span data-stu-id="0fddd-150">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="0fddd-151">Параметр **path** указывает, что файл Processes.csv сохраняется в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="0fddd-151">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="0fddd-152">Параметр **UseCulture** использует разделитель списка по умолчанию текущего языка и региональных параметров в качестве разделителя.</span><span class="sxs-lookup"><span data-stu-id="0fddd-152">The **UseCulture** parameter uses the current culture's default list separator as the delimiter.</span></span> <span data-ttu-id="0fddd-153">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="0fddd-153">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="0fddd-154">`Get-Content`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="0fddd-154">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="0fddd-155">Пример 5. экспорт процессов с информацией о типах</span><span class="sxs-lookup"><span data-stu-id="0fddd-155">Example 5: Export processes with type information</span></span>

<span data-ttu-id="0fddd-156">В этом примере объясняется, как включить данные заголовка **#TYPE** в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="0fddd-156">This example explains how to include the **#TYPE** header information in a CSV file.</span></span> <span data-ttu-id="0fddd-157">По умолчанию в версиях, предшествовавших версии PowerShell 6,0, используется заголовок **#TYPE** .</span><span class="sxs-lookup"><span data-stu-id="0fddd-157">The **#TYPE** header is the default in versions prior to PowerShell 6.0.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -IncludeTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
#TYPE System.Diagnostics.Process
"Name","SI","Handles","VM","WS","PM","NPM","Path","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","507","2203595001856","35139584","20934656","29504", ...
```

<span data-ttu-id="0fddd-158">`Get-Process`Командлет получает объекты **Process** .</span><span class="sxs-lookup"><span data-stu-id="0fddd-158">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="0fddd-159">Объекты процесса отправляются по конвейеру в `Export-Csv` командлет.</span><span class="sxs-lookup"><span data-stu-id="0fddd-159">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="0fddd-160">`Export-Csv` Преобразует объекты процесса в последовательность строк CSV.</span><span class="sxs-lookup"><span data-stu-id="0fddd-160">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="0fddd-161">Параметр **path** указывает, что файл Processes.csv сохраняется в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="0fddd-161">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="0fddd-162">**Инклудетипеинформатион** содержит заголовок **#TYPE** данных в выходных данных в формате CSV.</span><span class="sxs-lookup"><span data-stu-id="0fddd-162">The **IncludeTypeInformation** includes the **#TYPE** information header in the CSV output.</span></span> <span data-ttu-id="0fddd-163">`Get-Content`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="0fddd-163">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="0fddd-164">Пример 6. экспорт и добавление объектов в CSV-файл</span><span class="sxs-lookup"><span data-stu-id="0fddd-164">Example 6: Export and append objects to a CSV file</span></span>

<span data-ttu-id="0fddd-165">В этом примере описывается, как экспортировать объекты в CSV-файл и использовать параметр **append** для добавления объектов в существующий файл.</span><span class="sxs-lookup"><span data-stu-id="0fddd-165">This example describes how to export objects to a CSV file and use the **Append** parameter to add objects to an existing file.</span></span>

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

<span data-ttu-id="0fddd-166">`Get-Service`Командлет получает объекты службы.</span><span class="sxs-lookup"><span data-stu-id="0fddd-166">The `Get-Service` cmdlet gets service objects.</span></span> <span data-ttu-id="0fddd-167">Параметр **DisplayName** возвращает службы, содержащие слово «приложение».</span><span class="sxs-lookup"><span data-stu-id="0fddd-167">The **DisplayName** parameter returns services that contain the word Application.</span></span> <span data-ttu-id="0fddd-168">Объекты службы отправляются по конвейеру в `Select-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="0fddd-168">The service objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="0fddd-169">`Select-Object` использует параметр **Property** для задания свойств **DisplayName** и **Status** .</span><span class="sxs-lookup"><span data-stu-id="0fddd-169">`Select-Object` uses the **Property** parameter to specify the **DisplayName** and **Status** properties.</span></span> <span data-ttu-id="0fddd-170">`$AppService`Переменная хранит объекты.</span><span class="sxs-lookup"><span data-stu-id="0fddd-170">The `$AppService` variable stores the objects.</span></span>

<span data-ttu-id="0fddd-171">`$AppService`Объекты отправляются по конвейеру в `Export-Csv` командлет.</span><span class="sxs-lookup"><span data-stu-id="0fddd-171">The `$AppService` objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="0fddd-172">`Export-Csv` Преобразует объекты службы в последовательность строк CSV.</span><span class="sxs-lookup"><span data-stu-id="0fddd-172">`Export-Csv` converts the service objects to a series of CSV strings.</span></span> <span data-ttu-id="0fddd-173">Параметр **path** указывает, что файл Services.csv сохраняется в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="0fddd-173">The **Path** parameter specifies that the Services.csv file is saved in the current directory.</span></span> <span data-ttu-id="0fddd-174">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="0fddd-174">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="0fddd-175">`Get-Content`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="0fddd-175">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

<span data-ttu-id="0fddd-176">`Get-Service` `Select-Object` Командлеты и повторяются для служб, содержащих слово Windows.</span><span class="sxs-lookup"><span data-stu-id="0fddd-176">The `Get-Service` and `Select-Object` cmdlets are repeated for services that contain the word Windows.</span></span> <span data-ttu-id="0fddd-177">`$WinService`Переменная хранит объекты службы.</span><span class="sxs-lookup"><span data-stu-id="0fddd-177">The `$WinService` variable stores the service objects.</span></span> <span data-ttu-id="0fddd-178">`Export-Csv`Командлет использует параметр **append** , чтобы указать, что `$WinService` объекты добавляются в существующий файл Services.csv.</span><span class="sxs-lookup"><span data-stu-id="0fddd-178">The `Export-Csv` cmdlet uses the **Append** parameter to specify that the `$WinService` objects are added to the existing Services.csv file.</span></span> <span data-ttu-id="0fddd-179">`Get-Content`Командлет повторяется для вывода обновленного файла, содержащего добавленные данные.</span><span class="sxs-lookup"><span data-stu-id="0fddd-179">The `Get-Content` cmdlet is repeated to display the updated file that includes the appended data.</span></span>

### <span data-ttu-id="0fddd-180">Пример 7. командлет Format в конвейере создает непредвиденные результаты</span><span class="sxs-lookup"><span data-stu-id="0fddd-180">Example 7: Format cmdlet within a pipeline creates unexpected results</span></span>

<span data-ttu-id="0fddd-181">В этом примере показано, почему важно не использовать командлет Format в конвейере.</span><span class="sxs-lookup"><span data-stu-id="0fddd-181">This example shows why it is important not to use a format cmdlet within a pipeline.</span></span> <span data-ttu-id="0fddd-182">При получении непредвиденных выходных данных устраните неполадки синтаксиса конвейера.</span><span class="sxs-lookup"><span data-stu-id="0fddd-182">When unexpected output is received, troubleshoot the pipeline syntax.</span></span>

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

<span data-ttu-id="0fddd-183">`Get-Date`Командлет возвращает объект **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="0fddd-183">The `Get-Date` cmdlet gets the **DateTime** object.</span></span> <span data-ttu-id="0fddd-184">Объект отправляется по конвейеру в `Select-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="0fddd-184">The object is sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="0fddd-185">`Select-Object` использует параметр **Property** для выбора подмножества свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="0fddd-185">`Select-Object` uses the **Property** parameter to select a subset of object properties.</span></span> <span data-ttu-id="0fddd-186">Объект отправляется по конвейеру в `Export-Csv` командлет.</span><span class="sxs-lookup"><span data-stu-id="0fddd-186">The object is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="0fddd-187">`Export-Csv` Преобразует объект в формат CSV.</span><span class="sxs-lookup"><span data-stu-id="0fddd-187">`Export-Csv` converts the object to a CSV format.</span></span> <span data-ttu-id="0fddd-188">Параметр **path** указывает, что файл DateTime.csv сохраняется в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="0fddd-188">The **Path** parameter specifies that the DateTime.csv file is saved in the current directory.</span></span> <span data-ttu-id="0fddd-189">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="0fddd-189">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="0fddd-190">`Get-Content`Командлет использует параметр **path** для вывода CSV-файла, расположенного в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="0fddd-190">The `Get-Content` cmdlet uses the **Path** parameter to display the CSV file located in the current directory.</span></span>

<span data-ttu-id="0fddd-191">При `Format-Table` использовании командлета в конвейере для выбора свойств получены непредвиденные результаты.</span><span class="sxs-lookup"><span data-stu-id="0fddd-191">When the `Format-Table` cmdlet is used within the pipeline to select properties unexpected results are received.</span></span> <span data-ttu-id="0fddd-192">`Format-Table` отправляет объекты формата таблицы по конвейеру в `Export-Csv` командлет, а не в объект **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="0fddd-192">`Format-Table` sends table format objects down the pipeline to the `Export-Csv` cmdlet rather than the **DateTime** object.</span></span> <span data-ttu-id="0fddd-193">`Export-Csv` Преобразует объекты формата таблицы в последовательность строк CSV.</span><span class="sxs-lookup"><span data-stu-id="0fddd-193">`Export-Csv` converts the table format objects to a series of CSV strings.</span></span> <span data-ttu-id="0fddd-194">`Get-Content`Командлет ОТОБРАЖАЕТ CSV-файл, содержащий объекты формата таблицы.</span><span class="sxs-lookup"><span data-stu-id="0fddd-194">The `Get-Content` cmdlet displays the CSV file which contains the table format objects.</span></span>

### <span data-ttu-id="0fddd-195">Пример 8. Использование параметра Force для перезаписи файлов, которые доступны только для чтения</span><span class="sxs-lookup"><span data-stu-id="0fddd-195">Example 8: Using the Force parameter to overwrite read-only files</span></span>

<span data-ttu-id="0fddd-196">В этом примере создается пустой файл только для чтения, а для обновления файла используется параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="0fddd-196">This example creates an empty, read-only file and uses the **Force** parameter to update the file.</span></span>

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

<span data-ttu-id="0fddd-197">`New-Item`Командлет использует параметры **path** и **ItemType** для создания файла ReadOnly.csv в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="0fddd-197">The `New-Item` cmdlet uses the **Path** and **ItemType** parameters to create the ReadOnly.csv file in the current directory.</span></span> <span data-ttu-id="0fddd-198">`Set-ItemProperty`Командлет использует параметры **Name** и **value** , чтобы изменить свойство **IsReadOnly** для файла на true.</span><span class="sxs-lookup"><span data-stu-id="0fddd-198">The `Set-ItemProperty` cmdlet uses the **Name** and **Value** parameters to change the file's **IsReadOnly** property to true.</span></span> <span data-ttu-id="0fddd-199">`Get-Process`Командлет получает объекты **Process** .</span><span class="sxs-lookup"><span data-stu-id="0fddd-199">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="0fddd-200">Объекты процесса отправляются по конвейеру в `Export-Csv` командлет.</span><span class="sxs-lookup"><span data-stu-id="0fddd-200">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="0fddd-201">`Export-Csv` Преобразует объекты процесса в последовательность строк CSV.</span><span class="sxs-lookup"><span data-stu-id="0fddd-201">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="0fddd-202">Параметр **path** указывает, что файл ReadOnly.csv сохраняется в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="0fddd-202">The **Path** parameter specifies that the ReadOnly.csv file is saved in the current directory.</span></span> <span data-ttu-id="0fddd-203">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="0fddd-203">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="0fddd-204">Выходные данные показывают, что файл не записан, так как доступ запрещен.</span><span class="sxs-lookup"><span data-stu-id="0fddd-204">The output shows that the file is not written because access is denied.</span></span>

<span data-ttu-id="0fddd-205">Параметр **Force** добавляется в командлет, `Export-Csv` чтобы принудительно выполнить запись экспорта в файл.</span><span class="sxs-lookup"><span data-stu-id="0fddd-205">The **Force** parameter is added to the `Export-Csv` cmdlet to force the export to write to the file.</span></span> <span data-ttu-id="0fddd-206">`Get-Content`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="0fddd-206">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="0fddd-207">Пример 9. Использование параметра Force с Append</span><span class="sxs-lookup"><span data-stu-id="0fddd-207">Example 9: Using the Force parameter with Append</span></span>

<span data-ttu-id="0fddd-208">В этом примере показано, как использовать параметры **Force** и **append** .</span><span class="sxs-lookup"><span data-stu-id="0fddd-208">This example shows how to use the **Force** and **Append** parameters.</span></span> <span data-ttu-id="0fddd-209">Если эти параметры объединены, несоответствующие свойства объекта могут быть записаны в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="0fddd-209">When these parameters are combined, mismatched object properties can be written to a CSV file.</span></span>

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

<span data-ttu-id="0fddd-210">Выражение создает **PSCustomObject** с свойствами **Name** и **Version** .</span><span class="sxs-lookup"><span data-stu-id="0fddd-210">An expression creates the **PSCustomObject** with **Name** and **Version** properties.</span></span> <span data-ttu-id="0fddd-211">Значения хранятся в `$Content` переменной.</span><span class="sxs-lookup"><span data-stu-id="0fddd-211">The values are stored in the `$Content` variable.</span></span> <span data-ttu-id="0fddd-212">`$Content`Переменная отправляется в командлет по конвейеру `Export-Csv` .</span><span class="sxs-lookup"><span data-stu-id="0fddd-212">The `$Content` variable is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="0fddd-213">`Export-Csv` использует параметр **path** и сохраняет файл ParmFile.csv в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="0fddd-213">`Export-Csv` uses the **Path** parameter and saves the ParmFile.csv file in the current directory.</span></span> <span data-ttu-id="0fddd-214">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="0fddd-214">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

<span data-ttu-id="0fddd-215">Другое выражение создает **PSCustomObject** с свойствами **Name** и **Edition** .</span><span class="sxs-lookup"><span data-stu-id="0fddd-215">Another expression creates a **PSCustomObject** with the **Name** and **Edition** properties.</span></span> <span data-ttu-id="0fddd-216">Значения хранятся в `$AdditionalContent` переменной.</span><span class="sxs-lookup"><span data-stu-id="0fddd-216">The values are stored in the `$AdditionalContent` variable.</span></span> <span data-ttu-id="0fddd-217">`$AdditionalContent`Переменная отправляется в командлет по конвейеру `Export-Csv` .</span><span class="sxs-lookup"><span data-stu-id="0fddd-217">The `$AdditionalContent` variable is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="0fddd-218">Параметр **append** используется для добавления данных в файл.</span><span class="sxs-lookup"><span data-stu-id="0fddd-218">The **Append** parameter is used to add the data to the file.</span></span> <span data-ttu-id="0fddd-219">Добавление завершается ошибкой из-за несоответствия имени свойства **версии** и **выпуска**.</span><span class="sxs-lookup"><span data-stu-id="0fddd-219">The append fails because there is a property name mismatch between **Version** and **Edition**.</span></span>

<span data-ttu-id="0fddd-220">`Export-Csv`Параметр **Force** командлета используется для принудительной записи экспорта в файл.</span><span class="sxs-lookup"><span data-stu-id="0fddd-220">The `Export-Csv` cmdlet **Force** parameter is used to force the export to write to the file.</span></span> <span data-ttu-id="0fddd-221">Свойство **Edition** отбрасывается.</span><span class="sxs-lookup"><span data-stu-id="0fddd-221">The **Edition** property is discarded.</span></span> <span data-ttu-id="0fddd-222">`Import-Csv`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="0fddd-222">The `Import-Csv` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="0fddd-223">Пример 10. экспорт в CSV с кавычками вокруг двух столбцов</span><span class="sxs-lookup"><span data-stu-id="0fddd-223">Example 10: Export to CSV with quotes around two columns</span></span>

<span data-ttu-id="0fddd-224">В этом примере объект **DateTime** преобразуется в строку CSV.</span><span class="sxs-lookup"><span data-stu-id="0fddd-224">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
Get-Date | Export-Csv  -QuoteFields "DateTime","Date" -Path .\FTDateTime.csv
Get-Content -Path .\FTDateTime.csv
```

```Output
DisplayHint,"DateTime","Date",Day,DayOfWeek,DayOfYear,Hour,Kind,Millisecond,Minute,Month,Second,Ticks,TimeOfDay,Year
DateTime,"Thursday, August 22, 2019 11:27:34 AM","8/22/2019 12:00:00 AM",22,Thursday,234,11,Local,569,27,8,34,637020700545699784,11:27:34.5699784,2019
```

### <span data-ttu-id="0fddd-225">Пример 11. экспорт в CSV с кавычками только при необходимости</span><span class="sxs-lookup"><span data-stu-id="0fddd-225">Example 11: Export to CSV with quotes only when needed</span></span>

<span data-ttu-id="0fddd-226">В этом примере объект **DateTime** преобразуется в строку CSV.</span><span class="sxs-lookup"><span data-stu-id="0fddd-226">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
Get-Date | Export-Csv  -UseQuotes AsNeeded -Path .\FTDateTime.csv
Get-Content -Path .\FTDateTime.csv
```

```Output
DisplayHint,DateTime,Date,Day,DayOfWeek,DayOfYear,Hour,Kind,Millisecond,Minute,Month,Second,Ticks,TimeOfDay,Year
DateTime,"Thursday, August 22, 2019 11:31:00 AM",8/22/2019 12:00:00 AM,22,Thursday,234,11,Local,713,31,8,0,637020702607132640,11:31:00.7132640,2019
```

## <span data-ttu-id="0fddd-227">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0fddd-227">PARAMETERS</span></span>

### <span data-ttu-id="0fddd-228">— Добавление</span><span class="sxs-lookup"><span data-stu-id="0fddd-228">-Append</span></span>

<span data-ttu-id="0fddd-229">Используйте этот параметр, чтобы `Export-CSV` Добавить выходные данные CSV в конец указанного файла.</span><span class="sxs-lookup"><span data-stu-id="0fddd-229">Use this parameter so that `Export-CSV` adds CSV output to the end of the specified file.</span></span> <span data-ttu-id="0fddd-230">Без этого параметра `Export-CSV` заменяет содержимое файла без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="0fddd-230">Without this parameter, `Export-CSV` replaces the file contents without warning.</span></span>

<span data-ttu-id="0fddd-231">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="0fddd-231">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="0fddd-232">-Delimiter</span><span class="sxs-lookup"><span data-stu-id="0fddd-232">-Delimiter</span></span>

<span data-ttu-id="0fddd-233">Указывает разделитель для значений свойств.</span><span class="sxs-lookup"><span data-stu-id="0fddd-233">Specifies a delimiter to separate the property values.</span></span> <span data-ttu-id="0fddd-234">Значение по умолчанию — запятая ( `,` ).</span><span class="sxs-lookup"><span data-stu-id="0fddd-234">The default is a comma (`,`).</span></span> <span data-ttu-id="0fddd-235">Введите символ, например двоеточие ( `:` ).</span><span class="sxs-lookup"><span data-stu-id="0fddd-235">Enter a character, such as a colon (`:`).</span></span> <span data-ttu-id="0fddd-236">Чтобы указать точку с запятой ( `;` ), заключите ее в кавычки.</span><span class="sxs-lookup"><span data-stu-id="0fddd-236">To specify a semicolon (`;`), enclose it in quotation marks.</span></span>

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

### <span data-ttu-id="0fddd-237">-Encoding</span><span class="sxs-lookup"><span data-stu-id="0fddd-237">-Encoding</span></span>

<span data-ttu-id="0fddd-238">Указывает кодировку для экспортированного CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="0fddd-238">Specifies the encoding for the exported CSV file.</span></span> <span data-ttu-id="0fddd-239">Значение по умолчанию — `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="0fddd-239">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="0fddd-240">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="0fddd-240">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="0fddd-241">`ascii`: Использует кодировку для набора символов ASCII (7-разрядных).</span><span class="sxs-lookup"><span data-stu-id="0fddd-241">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="0fddd-242">`bigendianunicode`: Кодируется в формате UTF-16 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="0fddd-242">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="0fddd-243">`oem`: Использует кодировку по умолчанию для программ MS-DOS и консолей.</span><span class="sxs-lookup"><span data-stu-id="0fddd-243">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="0fddd-244">`unicode`: Кодируется в формате UTF-16 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="0fddd-244">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="0fddd-245">`utf7`: Кодируется в формате UTF-7.</span><span class="sxs-lookup"><span data-stu-id="0fddd-245">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="0fddd-246">`utf8`: Кодируется в формате UTF-8.</span><span class="sxs-lookup"><span data-stu-id="0fddd-246">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="0fddd-247">`utf8BOM`: Кодирует в формате UTF-8 с меткой порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="0fddd-247">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="0fddd-248">`utf8NoBOM`: Кодирует в формате UTF-8 без метки порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="0fddd-248">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="0fddd-249">`utf32`: Кодируется в формате UTF-32.</span><span class="sxs-lookup"><span data-stu-id="0fddd-249">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="0fddd-250">Начиная с PowerShell 6,2, параметр **кодировки** также разрешает числовые идентификаторы зарегистрированных кодовых страниц (например `-Encoding 1251` ,) или строковых имен зарегистрированных кодовых страниц (например `-Encoding "windows-1251"` ,).</span><span class="sxs-lookup"><span data-stu-id="0fddd-250">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="0fddd-251">Дополнительные сведения см. в документации .NET по [кодированию. codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="0fddd-251">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0fddd-252">-Force</span><span class="sxs-lookup"><span data-stu-id="0fddd-252">-Force</span></span>

<span data-ttu-id="0fddd-253">Этот параметр позволяет `Export-Csv` перезаписывать файлы с атрибутом " **только для чтения** ".</span><span class="sxs-lookup"><span data-stu-id="0fddd-253">This parameter allows `Export-Csv` to overwrite files with the **Read Only** attribute.</span></span>

<span data-ttu-id="0fddd-254">При объединении параметров **Force** и **append** объекты, содержащие несовпадающие свойства, могут быть записаны в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="0fddd-254">When **Force** and **Append** parameters are combined, objects that contain mismatched properties can be written to a CSV file.</span></span> <span data-ttu-id="0fddd-255">В файл записываются только те свойства, которые соответствуют.</span><span class="sxs-lookup"><span data-stu-id="0fddd-255">Only the properties that match are written to the file.</span></span> <span data-ttu-id="0fddd-256">Несоответствующие свойства отбрасываются.</span><span class="sxs-lookup"><span data-stu-id="0fddd-256">The mismatched properties are discarded.</span></span>

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

### <span data-ttu-id="0fddd-257">-Инклудетипеинформатион</span><span class="sxs-lookup"><span data-stu-id="0fddd-257">-IncludeTypeInformation</span></span>

<span data-ttu-id="0fddd-258">При использовании этого параметра первая строка выходных данных CSV содержит **#TYPE** , за которыми следует полное имя типа объекта.</span><span class="sxs-lookup"><span data-stu-id="0fddd-258">When this parameter is used the first line of the CSV output contains **#TYPE** followed by the fully qualified name of the object type.</span></span> <span data-ttu-id="0fddd-259">Например, **#TYPE System. Diagnostics. Process**.</span><span class="sxs-lookup"><span data-stu-id="0fddd-259">For example, **#TYPE System.Diagnostics.Process**.</span></span>

<span data-ttu-id="0fddd-260">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="0fddd-260">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ITI

Required: False
Position: Named
Default value: #TYPE <Object>
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0fddd-261">-InputObject</span><span class="sxs-lookup"><span data-stu-id="0fddd-261">-InputObject</span></span>

<span data-ttu-id="0fddd-262">Указывает экспортируемые объекты в качестве строк CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="0fddd-262">Specifies the objects to export as CSV strings.</span></span> <span data-ttu-id="0fddd-263">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="0fddd-263">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="0fddd-264">Также можно передать объекты в `Export-CSV` .</span><span class="sxs-lookup"><span data-stu-id="0fddd-264">You can also pipe objects to `Export-CSV`.</span></span>

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

### <span data-ttu-id="0fddd-265">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0fddd-265">-LiteralPath</span></span>

<span data-ttu-id="0fddd-266">Указывает путь к выходному CSV-файлу.</span><span class="sxs-lookup"><span data-stu-id="0fddd-266">Specifies the path to the CSV output file.</span></span> <span data-ttu-id="0fddd-267">В отличие от параметра **Path**, значение параметра **LiteralPath** используется в точности так, как вводится.</span><span class="sxs-lookup"><span data-stu-id="0fddd-267">Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="0fddd-268">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="0fddd-268">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="0fddd-269">Если путь содержит escape-символы, используйте одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="0fddd-269">If the path includes escape characters, use single quotation marks.</span></span> <span data-ttu-id="0fddd-270">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="0fddd-270">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath, LP

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0fddd-271">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="0fddd-271">-NoClobber</span></span>

<span data-ttu-id="0fddd-272">Используйте этот параметр, чтобы `Export-CSV` не перезаписать существующий файл.</span><span class="sxs-lookup"><span data-stu-id="0fddd-272">Use this parameter so that `Export-CSV` does not overwrite an existing file.</span></span> <span data-ttu-id="0fddd-273">По умолчанию, если файл существует по указанному пути, `Export-CSV` перезаписывает файл без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="0fddd-273">By default, if the file exists in the specified path, `Export-CSV` overwrites the file without warning.</span></span>

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

### <span data-ttu-id="0fddd-274">-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="0fddd-274">-NoTypeInformation</span></span>

<span data-ttu-id="0fddd-275">Удаляет заголовок сведений о **#TYPE** из выходных данных.</span><span class="sxs-lookup"><span data-stu-id="0fddd-275">Removes the **#TYPE** information header from the output.</span></span> <span data-ttu-id="0fddd-276">Этот параметр стал значением по умолчанию в PowerShell 6,0 и включен для обеспечения обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="0fddd-276">This parameter became the default in PowerShell 6.0 and is included for backwards compatibility.</span></span>

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

### <span data-ttu-id="0fddd-277">-Path</span><span class="sxs-lookup"><span data-stu-id="0fddd-277">-Path</span></span>

<span data-ttu-id="0fddd-278">Обязательный параметр, указывающий расположение для сохранения выходного CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="0fddd-278">A required parameter that specifies the location to save the CSV output file.</span></span>

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

### <span data-ttu-id="0fddd-279">-UseCulture</span><span class="sxs-lookup"><span data-stu-id="0fddd-279">-UseCulture</span></span>

<span data-ttu-id="0fddd-280">Использует разделитель списка для текущего языка и региональных параметров в качестве разделителя элементов.</span><span class="sxs-lookup"><span data-stu-id="0fddd-280">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="0fddd-281">Чтобы найти разделитель списка для языка и региональных параметров, используйте следующую команду: `(Get-Culture).TextInfo.ListSeparator` .</span><span class="sxs-lookup"><span data-stu-id="0fddd-281">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

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

### <span data-ttu-id="0fddd-282">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0fddd-282">-Confirm</span></span>

<span data-ttu-id="0fddd-283">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="0fddd-283">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0fddd-284">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0fddd-284">-WhatIf</span></span>

<span data-ttu-id="0fddd-285">Предотвращает обработку командлета или внесение изменений.</span><span class="sxs-lookup"><span data-stu-id="0fddd-285">Prevents the cmdlet from being processed or making changes.</span></span> <span data-ttu-id="0fddd-286">Выходные данные показывают, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="0fddd-286">The output shows what would happen if the cmdlet were run.</span></span>

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

### <span data-ttu-id="0fddd-287">-Куотефиелдс</span><span class="sxs-lookup"><span data-stu-id="0fddd-287">-QuoteFields</span></span>

<span data-ttu-id="0fddd-288">Задает имена столбцов, которые должны быть заключены в кавычки.</span><span class="sxs-lookup"><span data-stu-id="0fddd-288">Specifies the names of the columns that should be quoted.</span></span> <span data-ttu-id="0fddd-289">При использовании этого параметра только указанные столбцы заключаются в кавычки.</span><span class="sxs-lookup"><span data-stu-id="0fddd-289">When this parameter is used, only the specified columns are quoted.</span></span> <span data-ttu-id="0fddd-290">Этот параметр был добавлен в PowerShell 7,0.</span><span class="sxs-lookup"><span data-stu-id="0fddd-290">This parameter was added in PowerShell 7.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: QF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0fddd-291">-Усекуотес</span><span class="sxs-lookup"><span data-stu-id="0fddd-291">-UseQuotes</span></span>

<span data-ttu-id="0fddd-292">Указывает, когда в CSV-файлах используются кавычки.</span><span class="sxs-lookup"><span data-stu-id="0fddd-292">Specifies when quotes are used in the CSV files.</span></span> <span data-ttu-id="0fddd-293">Возможны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="0fddd-293">Possible values are:</span></span>

- <span data-ttu-id="0fddd-294">Никогда — не заключать никаких кавычек</span><span class="sxs-lookup"><span data-stu-id="0fddd-294">Never - don't quote anything</span></span>
- <span data-ttu-id="0fddd-295">Всегда-цитировать все (поведение по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="0fddd-295">Always - quote everything (default behavior)</span></span>
- <span data-ttu-id="0fddd-296">AsNeeded — поля кавычек, содержащие символ-разделитель</span><span class="sxs-lookup"><span data-stu-id="0fddd-296">AsNeeded - only quote fields that contain a delimiter character</span></span>

<span data-ttu-id="0fddd-297">Этот параметр был добавлен в PowerShell 7,0.</span><span class="sxs-lookup"><span data-stu-id="0fddd-297">This parameter was added in PowerShell 7.0.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.BaseCsvWritingCommand+QuoteKind
Parameter Sets: (All)
Aliases: UQ

Required: False
Position: Named
Default value: Always
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0fddd-298">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="0fddd-298">CommonParameters</span></span>

<span data-ttu-id="0fddd-299">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0fddd-299">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0fddd-300">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0fddd-300">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0fddd-301">Входные данные</span><span class="sxs-lookup"><span data-stu-id="0fddd-301">INPUTS</span></span>

### <span data-ttu-id="0fddd-302">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="0fddd-302">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="0fddd-303">Любой объект с адаптером системы расширенного типа (ETS) можно передать в `Export-CSV` .</span><span class="sxs-lookup"><span data-stu-id="0fddd-303">You can pipe any object with an Extended Type System (ETS) adapter to `Export-CSV`.</span></span>

## <span data-ttu-id="0fddd-304">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="0fddd-304">OUTPUTS</span></span>

### <span data-ttu-id="0fddd-305">System.String</span><span class="sxs-lookup"><span data-stu-id="0fddd-305">System.String</span></span>

<span data-ttu-id="0fddd-306">Список CSV-файлов отправляется в файл, указанный в параметре Path.</span><span class="sxs-lookup"><span data-stu-id="0fddd-306">The CSV list is sent to the file designated in the Path parameter.</span></span>

## <span data-ttu-id="0fddd-307">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="0fddd-307">NOTES</span></span>

<span data-ttu-id="0fddd-308">`Export-CSV`Командлет преобразует объекты, которые вы отправляете, в последовательность строк CSV и сохраняет их в указанном текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="0fddd-308">The `Export-CSV` cmdlet converts the objects that you submit into a series of CSV strings and saves them in the specified text file.</span></span> <span data-ttu-id="0fddd-309">Можно использовать `Export-CSV -IncludeTypeInformation` для сохранения объектов в CSV-файле, а затем использовать `Import-Csv` командлет для создания объектов из текста в CSV-файле.</span><span class="sxs-lookup"><span data-stu-id="0fddd-309">You can use `Export-CSV -IncludeTypeInformation` to save objects in a CSV file and then use the `Import-Csv` cmdlet to create objects from the text in the CSV file.</span></span>

<span data-ttu-id="0fddd-310">В CSV-файле каждый объект представлен списком значений свойств объекта с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="0fddd-310">In the CSV file, each object is represented by a comma-separated list of the property values of the object.</span></span> <span data-ttu-id="0fddd-311">Значения свойств преобразуются в строки с помощью метода **ToString ()** .</span><span class="sxs-lookup"><span data-stu-id="0fddd-311">The property values are converted to strings using the **ToString()** method.</span></span> <span data-ttu-id="0fddd-312">Строки представлены именем значения свойства.</span><span class="sxs-lookup"><span data-stu-id="0fddd-312">The strings are represented by the property value name.</span></span> <span data-ttu-id="0fddd-313">`Export-CSV -IncludeTypeInformation` не экспортирует методы объекта.</span><span class="sxs-lookup"><span data-stu-id="0fddd-313">`Export-CSV -IncludeTypeInformation` does not export the methods of the object.</span></span>

<span data-ttu-id="0fddd-314">Строки CSV выводятся следующим образом:</span><span class="sxs-lookup"><span data-stu-id="0fddd-314">The CSV strings are output as follows:</span></span>

- <span data-ttu-id="0fddd-315">Если используется **инклудетипеинформатион** , первая строка содержит заголовок **#TYPE** сведений, за которым следует полное имя типа объекта.</span><span class="sxs-lookup"><span data-stu-id="0fddd-315">If **IncludeTypeInformation** is used, the first string contains the **#TYPE** information header followed by the object type's fully qualified name.</span></span>
  <span data-ttu-id="0fddd-316">Например, **#TYPE System. Diagnostics. Process**.</span><span class="sxs-lookup"><span data-stu-id="0fddd-316">For example, **#TYPE System.Diagnostics.Process**.</span></span>
- <span data-ttu-id="0fddd-317">Если **инклудетипеинформатион** не используется, первая строка включает заголовки столбцов.</span><span class="sxs-lookup"><span data-stu-id="0fddd-317">If **IncludeTypeInformation** is not used the first string includes the column headers.</span></span> <span data-ttu-id="0fddd-318">Заголовки содержат имена свойств первого объекта в виде списка с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="0fddd-318">The headers contain the first object's property names as a comma-separated list.</span></span>
- <span data-ttu-id="0fddd-319">Остальные строки содержат разделенные запятыми списки значений свойств каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="0fddd-319">The remaining strings contain comma-separated lists of each object's property values.</span></span>

<span data-ttu-id="0fddd-320">Начиная с PowerShell 6,0 поведение по умолчанию `Export-CSV` — не включать сведения о **#TYPE** в CSV-файл, а **NoTypeInformation** является подразумеваемым.</span><span class="sxs-lookup"><span data-stu-id="0fddd-320">Beginning with PowerShell 6.0 the default behavior of `Export-CSV` is to not include the **#TYPE** information in the CSV and **NoTypeInformation** is implied.</span></span> <span data-ttu-id="0fddd-321">**Инклудетипеинформатион** можно использовать для включения сведений о **#TYPE** и эмуляции поведения по умолчанию `Export-CSV` до PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="0fddd-321">**IncludeTypeInformation** can be used to include the **#TYPE** Information and emulate the default behavior of `Export-CSV` prior to PowerShell 6.0.</span></span>

<span data-ttu-id="0fddd-322">При отправке нескольких объектов в `Export-CSV` `Export-CSV` файл упорядочивается по свойствам первого отправленного объекта.</span><span class="sxs-lookup"><span data-stu-id="0fddd-322">When you submit multiple objects to `Export-CSV`, `Export-CSV` organizes the file based on the properties of the first object that you submit.</span></span> <span data-ttu-id="0fddd-323">Если остальные объекты не имеют одного из указанных свойств, значение этого свойства для объекта будет пустым, то есть представлено двумя идущими подряд запятыми.</span><span class="sxs-lookup"><span data-stu-id="0fddd-323">If the remaining objects do not have one of the specified properties, the property value of that object is null, as represented by two consecutive commas.</span></span> <span data-ttu-id="0fddd-324">Если оставшиеся объекты содержат дополнительные свойства, их значения не включаются в файл.</span><span class="sxs-lookup"><span data-stu-id="0fddd-324">If the remaining objects have additional properties, those property values are not included in the file.</span></span>

<span data-ttu-id="0fddd-325">Командлет можно использовать `Import-Csv` для повторного создания объектов из строк CSV в файлах.</span><span class="sxs-lookup"><span data-stu-id="0fddd-325">You can use the `Import-Csv` cmdlet to recreate objects from the CSV strings in the files.</span></span> <span data-ttu-id="0fddd-326">Полученные объекты являются версиями CSV-файлов исходных объектов, которые состоят из представлений строк значений свойств без методов.</span><span class="sxs-lookup"><span data-stu-id="0fddd-326">The resulting objects are CSV versions of the original objects that consist of string representations of the property values and no methods.</span></span>

<span data-ttu-id="0fddd-327">`ConvertTo-Csv` `ConvertFrom-Csv` Командлеты и преобразуют объекты в строки CSV и из строк CSV.</span><span class="sxs-lookup"><span data-stu-id="0fddd-327">The `ConvertTo-Csv` and `ConvertFrom-Csv` cmdlets convert objects to CSV strings and from CSV strings.</span></span> <span data-ttu-id="0fddd-328">`Export-CSV` совпадает с `ConvertTo-CSV` , за исключением того, что строки CSV сохраняются в файле.</span><span class="sxs-lookup"><span data-stu-id="0fddd-328">`Export-CSV` is the same as `ConvertTo-CSV`, except that it saves the CSV strings in a file.</span></span>

## <span data-ttu-id="0fddd-329">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="0fddd-329">RELATED LINKS</span></span>

[<span data-ttu-id="0fddd-330">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="0fddd-330">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="0fddd-331">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="0fddd-331">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="0fddd-332">Format-Table</span><span class="sxs-lookup"><span data-stu-id="0fddd-332">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="0fddd-333">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="0fddd-333">Import-Csv</span></span>](Import-Csv.md)

[<span data-ttu-id="0fddd-334">Select-Object</span><span class="sxs-lookup"><span data-stu-id="0fddd-334">Select-Object</span></span>](Select-Object.md)
