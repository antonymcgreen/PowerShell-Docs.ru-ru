---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 1/7/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-csv?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Csv
ms.openlocfilehash: 551646fba0523a03954295eb42380e7245ec319b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229041"
---
# <span data-ttu-id="3429d-103">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="3429d-103">Export-Csv</span></span>

## <span data-ttu-id="3429d-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3429d-104">SYNOPSIS</span></span>
<span data-ttu-id="3429d-105">Преобразует объекты в последовательность строк с разделителями-запятыми (CSV) и сохраняет строки в файл.</span><span class="sxs-lookup"><span data-stu-id="3429d-105">Converts objects into a series of comma-separated value (CSV) strings and saves the strings to a file.</span></span>

## <span data-ttu-id="3429d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3429d-106">SYNTAX</span></span>

### <span data-ttu-id="3429d-107">Delimiter (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="3429d-107">Delimiter (Default)</span></span>

```
Export-Csv -InputObject <PSObject> [[-Path] <String>] [-LiteralPath <String>] [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-Append] [[-Delimiter] <Char>] [-IncludeTypeInformation]
 [-NoTypeInformation] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="3429d-108">UseCulture</span><span class="sxs-lookup"><span data-stu-id="3429d-108">UseCulture</span></span>

```
Export-Csv -InputObject <PSObject> [[-Path] <String>] [-LiteralPath <String>] [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-Append] [-UseCulture] [-IncludeTypeInformation] [-NoTypeInformation]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="3429d-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3429d-109">DESCRIPTION</span></span>

<span data-ttu-id="3429d-110">`Export-CSV`Командлет создает CSV-файл объектов, которые вы отправляете.</span><span class="sxs-lookup"><span data-stu-id="3429d-110">The `Export-CSV` cmdlet creates a CSV file of the objects that you submit.</span></span> <span data-ttu-id="3429d-111">Каждый объект представляет собой строку, содержащую разделенный запятыми список значений свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="3429d-111">Each object is a row that includes a comma-separated list of the object's property values.</span></span> <span data-ttu-id="3429d-112">С помощью `Export-CSV` командлета можно создавать электронные таблицы и обмениваться данными с программами, которые принимают CSV-файлы в качестве входных.</span><span class="sxs-lookup"><span data-stu-id="3429d-112">You can use the `Export-CSV` cmdlet to create spreadsheets and share data with programs that accept CSV files as input.</span></span>

<span data-ttu-id="3429d-113">Не форматируйте объекты перед их отправкой в `Export-CSV` командлет.</span><span class="sxs-lookup"><span data-stu-id="3429d-113">Do not format objects before sending them to the `Export-CSV` cmdlet.</span></span> <span data-ttu-id="3429d-114">Если `Export-CSV` получает отформатированные объекты, CSV-файл содержит свойства форматирования, а не свойства объекта.</span><span class="sxs-lookup"><span data-stu-id="3429d-114">If `Export-CSV` receives formatted objects the CSV file contains the format properties rather than the object properties.</span></span> <span data-ttu-id="3429d-115">Чтобы экспортировать только выбранные свойства объекта, используйте `Select-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="3429d-115">To export only selected properties of an object, use the `Select-Object` cmdlet.</span></span>

## <span data-ttu-id="3429d-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="3429d-116">EXAMPLES</span></span>

### <span data-ttu-id="3429d-117">Пример 1. экспорт свойств процесса в CSV-файл</span><span class="sxs-lookup"><span data-stu-id="3429d-117">Example 1: Export process properties to a CSV file</span></span>

<span data-ttu-id="3429d-118">В этом примере выбираются объекты **Process** с конкретными свойствами, экспортируются объекты в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="3429d-118">This example selects **Process** objects with specific properties, exports the objects to a CSV file.</span></span>

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

<span data-ttu-id="3429d-119">`Get-Process`Командлет возвращает объекты **процесса** .</span><span class="sxs-lookup"><span data-stu-id="3429d-119">The `Get-Process` cmdlet gets the **Process** objects.</span></span> <span data-ttu-id="3429d-120">Параметр **Name** фильтрует выходные данные, чтобы включить только объекты процесса WmiPrvSE.</span><span class="sxs-lookup"><span data-stu-id="3429d-120">The **Name** parameter filters the output to include only the WmiPrvSE process objects.</span></span> <span data-ttu-id="3429d-121">Объекты процесса отправляются по конвейеру в `Select-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="3429d-121">The process objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="3429d-122">`Select-Object` использует параметр **Property** для выбора подмножества свойств объекта процесса.</span><span class="sxs-lookup"><span data-stu-id="3429d-122">`Select-Object` uses the **Property** parameter to select a subset of process object properties.</span></span> <span data-ttu-id="3429d-123">Объекты процесса отправляются по конвейеру в `Export-Csv` командлет.</span><span class="sxs-lookup"><span data-stu-id="3429d-123">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="3429d-124">`Export-Csv` Преобразует объекты процесса в последовательность строк CSV.</span><span class="sxs-lookup"><span data-stu-id="3429d-124">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="3429d-125">Параметр **path** указывает, что файл WmiData.csv сохраняется в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3429d-125">The **Path** parameter specifies that the WmiData.csv file is saved in the current directory.</span></span> <span data-ttu-id="3429d-126">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="3429d-126">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="3429d-127">`Import-Csv`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3429d-127">The `Import-Csv` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="3429d-128">Пример 2. экспорт процессов в файл с разделителями-запятыми</span><span class="sxs-lookup"><span data-stu-id="3429d-128">Example 2: Export processes to a comma-delimited file</span></span>

<span data-ttu-id="3429d-129">В этом примере **выполняется** получение объектов Process и экспорт объектов в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="3429d-129">This example gets **Process** objects and exports the objects to a CSV file.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","511","2203597099008","35364864","21979136","30048", ...
```

<span data-ttu-id="3429d-130">`Get-Process`Командлет получает объекты **Process** .</span><span class="sxs-lookup"><span data-stu-id="3429d-130">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="3429d-131">Объекты процесса отправляются по конвейеру в `Export-Csv` командлет.</span><span class="sxs-lookup"><span data-stu-id="3429d-131">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="3429d-132">`Export-Csv` Преобразует объекты процесса в последовательность строк CSV.</span><span class="sxs-lookup"><span data-stu-id="3429d-132">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="3429d-133">Параметр **path** указывает, что файл Processes.csv сохраняется в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3429d-133">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="3429d-134">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="3429d-134">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="3429d-135">`Get-Content`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3429d-135">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="3429d-136">Пример 3. экспорт процессов в файл с разделителями-запятыми</span><span class="sxs-lookup"><span data-stu-id="3429d-136">Example 3: Export processes to a semicolon delimited file</span></span>

<span data-ttu-id="3429d-137">В этом примере **выполняется** получение объектов Process и экспорт объектов в файл с разделителем в виде точки с запятой.</span><span class="sxs-lookup"><span data-stu-id="3429d-137">This example gets **Process** objects and exports the objects to a file with a semicolon delimiter.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -Delimiter ';' -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name";"SI";"Handles";"VM";"WS";"PM";"NPM";"Path";"Parent";"Company";"CPU";"FileVersion"; ...
"ApplicationFrameHost";"4";"509";"2203595321344";"34807808";"21770240";"29504"; ...
```

<span data-ttu-id="3429d-138">`Get-Process`Командлет получает объекты **Process** .</span><span class="sxs-lookup"><span data-stu-id="3429d-138">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="3429d-139">Объекты процесса отправляются по конвейеру в `Export-Csv` командлет.</span><span class="sxs-lookup"><span data-stu-id="3429d-139">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="3429d-140">`Export-Csv` Преобразует объекты процесса в последовательность строк CSV.</span><span class="sxs-lookup"><span data-stu-id="3429d-140">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="3429d-141">Параметр **path** указывает, что файл Processes.csv сохраняется в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3429d-141">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="3429d-142">Параметр- **Разделитель** задает точку с запятой для разделения строковых значений.</span><span class="sxs-lookup"><span data-stu-id="3429d-142">The **Delimiter** parameter specifies a semicolon to separate the string values.</span></span> <span data-ttu-id="3429d-143">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="3429d-143">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="3429d-144">`Get-Content`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3429d-144">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="3429d-145">Пример 4. экспорт процессов с использованием разделителя списка текущего языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="3429d-145">Example 4: Export processes using the current culture's list separator</span></span>

<span data-ttu-id="3429d-146">В этом примере **выполняется** получение объектов Process и экспорт объектов в файл.</span><span class="sxs-lookup"><span data-stu-id="3429d-146">This example gets **Process** objects and exports the objects to a file.</span></span> <span data-ttu-id="3429d-147">Разделитель является разделителем списка текущего языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="3429d-147">The delimiter is the current culture's list separator.</span></span>

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-Process | Export-Csv -Path .\Processes.csv -UseCulture -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","511","2203597099008","35364864","21979136","30048", ...
```

<span data-ttu-id="3429d-148">`Get-Culture`Командлет использует вложенные свойства **TextInfo** и **ListSeparator** и отображает текущий разделитель списка по умолчанию для текущего языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="3429d-148">The `Get-Culture` cmdlet uses the nested properties **TextInfo** and **ListSeparator** and displays the current culture's default list separator.</span></span> <span data-ttu-id="3429d-149">`Get-Process`Командлет получает объекты **Process** .</span><span class="sxs-lookup"><span data-stu-id="3429d-149">The `Get-Process` cmdlet gets **Process** objects.</span></span>
<span data-ttu-id="3429d-150">Объекты процесса отправляются по конвейеру в `Export-Csv` командлет.</span><span class="sxs-lookup"><span data-stu-id="3429d-150">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="3429d-151">`Export-Csv` Преобразует объекты процесса в последовательность строк CSV.</span><span class="sxs-lookup"><span data-stu-id="3429d-151">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="3429d-152">Параметр **path** указывает, что файл Processes.csv сохраняется в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3429d-152">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="3429d-153">Параметр **UseCulture** использует разделитель списка по умолчанию текущего языка и региональных параметров в качестве разделителя.</span><span class="sxs-lookup"><span data-stu-id="3429d-153">The **UseCulture** parameter uses the current culture's default list separator as the delimiter.</span></span> <span data-ttu-id="3429d-154">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="3429d-154">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="3429d-155">`Get-Content`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3429d-155">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="3429d-156">Пример 5. экспорт процессов с информацией о типах</span><span class="sxs-lookup"><span data-stu-id="3429d-156">Example 5: Export processes with type information</span></span>

<span data-ttu-id="3429d-157">В этом примере объясняется, как включить данные заголовка **#TYPE** в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="3429d-157">This example explains how to include the **#TYPE** header information in a CSV file.</span></span> <span data-ttu-id="3429d-158">По умолчанию в версиях, предшествовавших версии PowerShell 6,0, используется заголовок **#TYPE** .</span><span class="sxs-lookup"><span data-stu-id="3429d-158">The **#TYPE** header is the default in versions prior to PowerShell 6.0.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -IncludeTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
#TYPE System.Diagnostics.Process
"Name","SI","Handles","VM","WS","PM","NPM","Path","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","507","2203595001856","35139584","20934656","29504", ...
```

<span data-ttu-id="3429d-159">`Get-Process`Командлет получает объекты **Process** .</span><span class="sxs-lookup"><span data-stu-id="3429d-159">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="3429d-160">Объекты процесса отправляются по конвейеру в `Export-Csv` командлет.</span><span class="sxs-lookup"><span data-stu-id="3429d-160">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="3429d-161">`Export-Csv` Преобразует объекты процесса в последовательность строк CSV.</span><span class="sxs-lookup"><span data-stu-id="3429d-161">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="3429d-162">Параметр **path** указывает, что файл Processes.csv сохраняется в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3429d-162">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="3429d-163">**Инклудетипеинформатион** содержит заголовок **#TYPE** данных в выходных данных в формате CSV.</span><span class="sxs-lookup"><span data-stu-id="3429d-163">The **IncludeTypeInformation** includes the **#TYPE** information header in the CSV output.</span></span> <span data-ttu-id="3429d-164">`Get-Content`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3429d-164">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="3429d-165">Пример 6. экспорт и добавление объектов в CSV-файл</span><span class="sxs-lookup"><span data-stu-id="3429d-165">Example 6: Export and append objects to a CSV file</span></span>

<span data-ttu-id="3429d-166">В этом примере описывается, как экспортировать объекты в CSV-файл и использовать параметр **append** для добавления объектов в существующий файл.</span><span class="sxs-lookup"><span data-stu-id="3429d-166">This example describes how to export objects to a CSV file and use the **Append** parameter to add objects to an existing file.</span></span>

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

<span data-ttu-id="3429d-167">`Get-Service`Командлет получает объекты службы.</span><span class="sxs-lookup"><span data-stu-id="3429d-167">The `Get-Service` cmdlet gets service objects.</span></span> <span data-ttu-id="3429d-168">Параметр **DisplayName** возвращает службы, содержащие слово «приложение».</span><span class="sxs-lookup"><span data-stu-id="3429d-168">The **DisplayName** parameter returns services that contain the word Application.</span></span> <span data-ttu-id="3429d-169">Объекты службы отправляются по конвейеру в `Select-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="3429d-169">The service objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="3429d-170">`Select-Object` использует параметр **Property** для задания свойств **DisplayName** и **Status** .</span><span class="sxs-lookup"><span data-stu-id="3429d-170">`Select-Object` uses the **Property** parameter to specify the **DisplayName** and **Status** properties.</span></span> <span data-ttu-id="3429d-171">`$AppService`Переменная хранит объекты.</span><span class="sxs-lookup"><span data-stu-id="3429d-171">The `$AppService` variable stores the objects.</span></span>

<span data-ttu-id="3429d-172">`$AppService`Объекты отправляются по конвейеру в `Export-Csv` командлет.</span><span class="sxs-lookup"><span data-stu-id="3429d-172">The `$AppService` objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="3429d-173">`Export-Csv` Преобразует объекты службы в последовательность строк CSV.</span><span class="sxs-lookup"><span data-stu-id="3429d-173">`Export-Csv` converts the service objects to a series of CSV strings.</span></span> <span data-ttu-id="3429d-174">Параметр **path** указывает, что файл Services.csv сохраняется в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3429d-174">The **Path** parameter specifies that the Services.csv file is saved in the current directory.</span></span> <span data-ttu-id="3429d-175">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="3429d-175">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="3429d-176">`Get-Content`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3429d-176">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

<span data-ttu-id="3429d-177">`Get-Service` `Select-Object` Командлеты и повторяются для служб, содержащих слово Windows.</span><span class="sxs-lookup"><span data-stu-id="3429d-177">The `Get-Service` and `Select-Object` cmdlets are repeated for services that contain the word Windows.</span></span> <span data-ttu-id="3429d-178">`$WinService`Переменная хранит объекты службы.</span><span class="sxs-lookup"><span data-stu-id="3429d-178">The `$WinService` variable stores the service objects.</span></span> <span data-ttu-id="3429d-179">`Export-Csv`Командлет использует параметр **append** , чтобы указать, что `$WinService` объекты добавляются в существующий файл Services.csv.</span><span class="sxs-lookup"><span data-stu-id="3429d-179">The `Export-Csv` cmdlet uses the **Append** parameter to specify that the `$WinService` objects are added to the existing Services.csv file.</span></span> <span data-ttu-id="3429d-180">`Get-Content`Командлет повторяется для вывода обновленного файла, содержащего добавленные данные.</span><span class="sxs-lookup"><span data-stu-id="3429d-180">The `Get-Content` cmdlet is repeated to display the updated file that includes the appended data.</span></span>

### <span data-ttu-id="3429d-181">Пример 7. командлет Format в конвейере создает непредвиденные результаты</span><span class="sxs-lookup"><span data-stu-id="3429d-181">Example 7: Format cmdlet within a pipeline creates unexpected results</span></span>

<span data-ttu-id="3429d-182">В этом примере показано, почему важно не использовать командлет Format в конвейере.</span><span class="sxs-lookup"><span data-stu-id="3429d-182">This example shows why it is important not to use a format cmdlet within a pipeline.</span></span> <span data-ttu-id="3429d-183">При получении непредвиденных выходных данных устраните неполадки синтаксиса конвейера.</span><span class="sxs-lookup"><span data-stu-id="3429d-183">When unexpected output is received, troubleshoot the pipeline syntax.</span></span>

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

<span data-ttu-id="3429d-184">`Get-Date`Командлет возвращает объект **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="3429d-184">The `Get-Date` cmdlet gets the **DateTime** object.</span></span> <span data-ttu-id="3429d-185">Объект отправляется по конвейеру в `Select-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="3429d-185">The object is sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="3429d-186">`Select-Object` использует параметр **Property** для выбора подмножества свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="3429d-186">`Select-Object` uses the **Property** parameter to select a subset of object properties.</span></span> <span data-ttu-id="3429d-187">Объект отправляется по конвейеру в `Export-Csv` командлет.</span><span class="sxs-lookup"><span data-stu-id="3429d-187">The object is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="3429d-188">`Export-Csv` Преобразует объект в формат CSV.</span><span class="sxs-lookup"><span data-stu-id="3429d-188">`Export-Csv` converts the object to a CSV format.</span></span> <span data-ttu-id="3429d-189">Параметр **path** указывает, что файл DateTime.csv сохраняется в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3429d-189">The **Path** parameter specifies that the DateTime.csv file is saved in the current directory.</span></span> <span data-ttu-id="3429d-190">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="3429d-190">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="3429d-191">`Get-Content`Командлет использует параметр **path** для вывода CSV-файла, расположенного в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3429d-191">The `Get-Content` cmdlet uses the **Path** parameter to display the CSV file located in the current directory.</span></span>

<span data-ttu-id="3429d-192">При `Format-Table` использовании командлета в конвейере для выбора свойств получены непредвиденные результаты.</span><span class="sxs-lookup"><span data-stu-id="3429d-192">When the `Format-Table` cmdlet is used within the pipeline to select properties unexpected results are received.</span></span> <span data-ttu-id="3429d-193">`Format-Table` отправляет объекты формата таблицы по конвейеру в `Export-Csv` командлет, а не в объект **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="3429d-193">`Format-Table` sends table format objects down the pipeline to the `Export-Csv` cmdlet rather than the **DateTime** object.</span></span> <span data-ttu-id="3429d-194">`Export-Csv` Преобразует объекты формата таблицы в последовательность строк CSV.</span><span class="sxs-lookup"><span data-stu-id="3429d-194">`Export-Csv` converts the table format objects to a series of CSV strings.</span></span> <span data-ttu-id="3429d-195">`Get-Content`Командлет ОТОБРАЖАЕТ CSV-файл, содержащий объекты формата таблицы.</span><span class="sxs-lookup"><span data-stu-id="3429d-195">The `Get-Content` cmdlet displays the CSV file which contains the table format objects.</span></span>

### <span data-ttu-id="3429d-196">Пример 8. Использование параметра Force для перезаписи файлов, которые доступны только для чтения</span><span class="sxs-lookup"><span data-stu-id="3429d-196">Example 8: Using the Force parameter to overwrite read-only files</span></span>

<span data-ttu-id="3429d-197">В этом примере создается пустой файл только для чтения, а для обновления файла используется параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="3429d-197">This example creates an empty, read-only file and uses the **Force** parameter to update the file.</span></span>

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

<span data-ttu-id="3429d-198">`New-Item`Командлет использует параметры **path** и **ItemType** для создания файла ReadOnly.csv в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3429d-198">The `New-Item` cmdlet uses the **Path** and **ItemType** parameters to create the ReadOnly.csv file in the current directory.</span></span> <span data-ttu-id="3429d-199">`Set-ItemProperty`Командлет использует параметры **Name** и **value** , чтобы изменить свойство **IsReadOnly** для файла на true.</span><span class="sxs-lookup"><span data-stu-id="3429d-199">The `Set-ItemProperty` cmdlet uses the **Name** and **Value** parameters to change the file's **IsReadOnly** property to true.</span></span> <span data-ttu-id="3429d-200">`Get-Process`Командлет получает объекты **Process** .</span><span class="sxs-lookup"><span data-stu-id="3429d-200">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="3429d-201">Объекты процесса отправляются по конвейеру в `Export-Csv` командлет.</span><span class="sxs-lookup"><span data-stu-id="3429d-201">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="3429d-202">`Export-Csv` Преобразует объекты процесса в последовательность строк CSV.</span><span class="sxs-lookup"><span data-stu-id="3429d-202">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="3429d-203">Параметр **path** указывает, что файл ReadOnly.csv сохраняется в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3429d-203">The **Path** parameter specifies that the ReadOnly.csv file is saved in the current directory.</span></span> <span data-ttu-id="3429d-204">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="3429d-204">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="3429d-205">Выходные данные показывают, что файл не записан, так как доступ запрещен.</span><span class="sxs-lookup"><span data-stu-id="3429d-205">The output shows that the file is not written because access is denied.</span></span>

<span data-ttu-id="3429d-206">Параметр **Force** добавляется в командлет, `Export-Csv` чтобы принудительно выполнить запись экспорта в файл.</span><span class="sxs-lookup"><span data-stu-id="3429d-206">The **Force** parameter is added to the `Export-Csv` cmdlet to force the export to write to the file.</span></span> <span data-ttu-id="3429d-207">`Get-Content`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3429d-207">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="3429d-208">Пример 9. Использование параметра Force с Append</span><span class="sxs-lookup"><span data-stu-id="3429d-208">Example 9: Using the Force parameter with Append</span></span>

<span data-ttu-id="3429d-209">В этом примере показано, как использовать параметры **Force** и **append** .</span><span class="sxs-lookup"><span data-stu-id="3429d-209">This example shows how to use the **Force** and **Append** parameters.</span></span> <span data-ttu-id="3429d-210">Если эти параметры объединены, несоответствующие свойства объекта могут быть записаны в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="3429d-210">When these parameters are combined, mismatched object properties can be written to a CSV file.</span></span>

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

<span data-ttu-id="3429d-211">Выражение создает **PSCustomObject** с свойствами **Name** и **Version** .</span><span class="sxs-lookup"><span data-stu-id="3429d-211">An expression creates the **PSCustomObject** with **Name** and **Version** properties.</span></span> <span data-ttu-id="3429d-212">Значения хранятся в `$Content` переменной.</span><span class="sxs-lookup"><span data-stu-id="3429d-212">The values are stored in the `$Content` variable.</span></span> <span data-ttu-id="3429d-213">`$Content`Переменная отправляется в командлет по конвейеру `Export-Csv` .</span><span class="sxs-lookup"><span data-stu-id="3429d-213">The `$Content` variable is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="3429d-214">`Export-Csv` использует параметр **path** и сохраняет файл ParmFile.csv в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3429d-214">`Export-Csv` uses the **Path** parameter and saves the ParmFile.csv file in the current directory.</span></span> <span data-ttu-id="3429d-215">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="3429d-215">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

<span data-ttu-id="3429d-216">Другое выражение создает **PSCustomObject** с свойствами **Name** и **Edition** .</span><span class="sxs-lookup"><span data-stu-id="3429d-216">Another expression creates a **PSCustomObject** with the **Name** and **Edition** properties.</span></span> <span data-ttu-id="3429d-217">Значения хранятся в `$AdditionalContent` переменной.</span><span class="sxs-lookup"><span data-stu-id="3429d-217">The values are stored in the `$AdditionalContent` variable.</span></span> <span data-ttu-id="3429d-218">`$AdditionalContent`Переменная отправляется в командлет по конвейеру `Export-Csv` .</span><span class="sxs-lookup"><span data-stu-id="3429d-218">The `$AdditionalContent` variable is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="3429d-219">Параметр **append** используется для добавления данных в файл.</span><span class="sxs-lookup"><span data-stu-id="3429d-219">The **Append** parameter is used to add the data to the file.</span></span> <span data-ttu-id="3429d-220">Добавление завершается ошибкой из-за несоответствия имени свойства **версии** и **выпуска** .</span><span class="sxs-lookup"><span data-stu-id="3429d-220">The append fails because there is a property name mismatch between **Version** and **Edition** .</span></span>

<span data-ttu-id="3429d-221">`Export-Csv`Параметр **Force** командлета используется для принудительной записи экспорта в файл.</span><span class="sxs-lookup"><span data-stu-id="3429d-221">The `Export-Csv` cmdlet **Force** parameter is used to force the export to write to the file.</span></span> <span data-ttu-id="3429d-222">Свойство **Edition** отбрасывается.</span><span class="sxs-lookup"><span data-stu-id="3429d-222">The **Edition** property is discarded.</span></span> <span data-ttu-id="3429d-223">`Import-Csv`Командлет использует параметр **path** для вывода файла, расположенного в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3429d-223">The `Import-Csv` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

## <span data-ttu-id="3429d-224">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3429d-224">PARAMETERS</span></span>

### <span data-ttu-id="3429d-225">— Добавление</span><span class="sxs-lookup"><span data-stu-id="3429d-225">-Append</span></span>

<span data-ttu-id="3429d-226">Используйте этот параметр, чтобы `Export-CSV` Добавить выходные данные CSV в конец указанного файла.</span><span class="sxs-lookup"><span data-stu-id="3429d-226">Use this parameter so that `Export-CSV` adds CSV output to the end of the specified file.</span></span> <span data-ttu-id="3429d-227">Без этого параметра `Export-CSV` заменяет содержимое файла без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="3429d-227">Without this parameter, `Export-CSV` replaces the file contents without warning.</span></span>

<span data-ttu-id="3429d-228">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="3429d-228">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3429d-229">-Delimiter</span><span class="sxs-lookup"><span data-stu-id="3429d-229">-Delimiter</span></span>

<span data-ttu-id="3429d-230">Указывает разделитель для значений свойств.</span><span class="sxs-lookup"><span data-stu-id="3429d-230">Specifies a delimiter to separate the property values.</span></span> <span data-ttu-id="3429d-231">Значение по умолчанию — запятая ( `,` ).</span><span class="sxs-lookup"><span data-stu-id="3429d-231">The default is a comma (`,`).</span></span> <span data-ttu-id="3429d-232">Введите символ, например двоеточие ( `:` ).</span><span class="sxs-lookup"><span data-stu-id="3429d-232">Enter a character, such as a colon (`:`).</span></span> <span data-ttu-id="3429d-233">Чтобы указать точку с запятой ( `;` ), заключите ее в кавычки.</span><span class="sxs-lookup"><span data-stu-id="3429d-233">To specify a semicolon (`;`), enclose it in quotation marks.</span></span>

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

### <span data-ttu-id="3429d-234">-Encoding</span><span class="sxs-lookup"><span data-stu-id="3429d-234">-Encoding</span></span>

<span data-ttu-id="3429d-235">Указывает кодировку для экспортированного CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="3429d-235">Specifies the encoding for the exported CSV file.</span></span> <span data-ttu-id="3429d-236">Значение по умолчанию — `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="3429d-236">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="3429d-237">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="3429d-237">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="3429d-238">`ascii`: Использует кодировку для набора символов ASCII (7-разрядных).</span><span class="sxs-lookup"><span data-stu-id="3429d-238">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="3429d-239">`bigendianunicode`: Кодируется в формате UTF-16 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="3429d-239">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="3429d-240">`oem`: Использует кодировку по умолчанию для программ MS-DOS и консолей.</span><span class="sxs-lookup"><span data-stu-id="3429d-240">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="3429d-241">`unicode`: Кодируется в формате UTF-16 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="3429d-241">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="3429d-242">`utf7`: Кодируется в формате UTF-7.</span><span class="sxs-lookup"><span data-stu-id="3429d-242">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="3429d-243">`utf8`: Кодируется в формате UTF-8.</span><span class="sxs-lookup"><span data-stu-id="3429d-243">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="3429d-244">`utf8BOM`: Кодирует в формате UTF-8 с меткой порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="3429d-244">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="3429d-245">`utf8NoBOM`: Кодирует в формате UTF-8 без метки порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="3429d-245">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="3429d-246">`utf32`: Кодируется в формате UTF-32.</span><span class="sxs-lookup"><span data-stu-id="3429d-246">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="3429d-247">Начиная с PowerShell 6,2, параметр **кодировки** также разрешает числовые идентификаторы зарегистрированных кодовых страниц (например `-Encoding 1251` ,) или строковых имен зарегистрированных кодовых страниц (например `-Encoding "windows-1251"` ,).</span><span class="sxs-lookup"><span data-stu-id="3429d-247">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="3429d-248">Дополнительные сведения см. в документации .NET по [кодированию. codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="3429d-248">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

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

### <span data-ttu-id="3429d-249">-Force</span><span class="sxs-lookup"><span data-stu-id="3429d-249">-Force</span></span>

<span data-ttu-id="3429d-250">Этот параметр позволяет `Export-Csv` перезаписывать файлы с атрибутом " **только для чтения** ".</span><span class="sxs-lookup"><span data-stu-id="3429d-250">This parameter allows `Export-Csv` to overwrite files with the **Read Only** attribute.</span></span>

<span data-ttu-id="3429d-251">При объединении параметров **Force** и **append** объекты, содержащие несовпадающие свойства, могут быть записаны в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="3429d-251">When **Force** and **Append** parameters are combined, objects that contain mismatched properties can be written to a CSV file.</span></span> <span data-ttu-id="3429d-252">В файл записываются только те свойства, которые соответствуют.</span><span class="sxs-lookup"><span data-stu-id="3429d-252">Only the properties that match are written to the file.</span></span> <span data-ttu-id="3429d-253">Несоответствующие свойства отбрасываются.</span><span class="sxs-lookup"><span data-stu-id="3429d-253">The mismatched properties are discarded.</span></span>

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

### <span data-ttu-id="3429d-254">-Инклудетипеинформатион</span><span class="sxs-lookup"><span data-stu-id="3429d-254">-IncludeTypeInformation</span></span>

<span data-ttu-id="3429d-255">При использовании этого параметра первая строка выходных данных CSV содержит **#TYPE** , за которыми следует полное имя типа объекта.</span><span class="sxs-lookup"><span data-stu-id="3429d-255">When this parameter is used the first line of the CSV output contains **#TYPE** followed by the fully qualified name of the object type.</span></span> <span data-ttu-id="3429d-256">Например, **#TYPE System. Diagnostics. Process** .</span><span class="sxs-lookup"><span data-stu-id="3429d-256">For example, **#TYPE System.Diagnostics.Process** .</span></span>

<span data-ttu-id="3429d-257">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="3429d-257">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="3429d-258">-InputObject</span><span class="sxs-lookup"><span data-stu-id="3429d-258">-InputObject</span></span>

<span data-ttu-id="3429d-259">Указывает экспортируемые объекты в качестве строк CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="3429d-259">Specifies the objects to export as CSV strings.</span></span> <span data-ttu-id="3429d-260">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="3429d-260">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="3429d-261">Также можно передать объекты в `Export-CSV` .</span><span class="sxs-lookup"><span data-stu-id="3429d-261">You can also pipe objects to `Export-CSV`.</span></span>

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

### <span data-ttu-id="3429d-262">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="3429d-262">-LiteralPath</span></span>

<span data-ttu-id="3429d-263">Указывает путь к выходному CSV-файлу.</span><span class="sxs-lookup"><span data-stu-id="3429d-263">Specifies the path to the CSV output file.</span></span> <span data-ttu-id="3429d-264">В отличие от параметра **Path** , значение параметра **LiteralPath** используется в точности так, как вводится.</span><span class="sxs-lookup"><span data-stu-id="3429d-264">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="3429d-265">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="3429d-265">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="3429d-266">Если путь содержит escape-символы, используйте одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="3429d-266">If the path includes escape characters, use single quotation marks.</span></span> <span data-ttu-id="3429d-267">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="3429d-267">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="3429d-268">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="3429d-268">-NoClobber</span></span>

<span data-ttu-id="3429d-269">Используйте этот параметр, чтобы `Export-CSV` не перезаписать существующий файл.</span><span class="sxs-lookup"><span data-stu-id="3429d-269">Use this parameter so that `Export-CSV` does not overwrite an existing file.</span></span> <span data-ttu-id="3429d-270">По умолчанию, если файл существует по указанному пути, `Export-CSV` перезаписывает файл без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="3429d-270">By default, if the file exists in the specified path, `Export-CSV` overwrites the file without warning.</span></span>

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

### <span data-ttu-id="3429d-271">-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="3429d-271">-NoTypeInformation</span></span>

<span data-ttu-id="3429d-272">Удаляет заголовок сведений о **#TYPE** из выходных данных.</span><span class="sxs-lookup"><span data-stu-id="3429d-272">Removes the **#TYPE** information header from the output.</span></span> <span data-ttu-id="3429d-273">Этот параметр стал значением по умолчанию в PowerShell 6,0 и включен для обеспечения обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="3429d-273">This parameter became the default in PowerShell 6.0 and is included for backwards compatibility.</span></span>

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

### <span data-ttu-id="3429d-274">-Path</span><span class="sxs-lookup"><span data-stu-id="3429d-274">-Path</span></span>

<span data-ttu-id="3429d-275">Обязательный параметр, указывающий расположение для сохранения выходного CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="3429d-275">A required parameter that specifies the location to save the CSV output file.</span></span>

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

### <span data-ttu-id="3429d-276">-UseCulture</span><span class="sxs-lookup"><span data-stu-id="3429d-276">-UseCulture</span></span>

<span data-ttu-id="3429d-277">Использует разделитель списка для текущего языка и региональных параметров в качестве разделителя элементов.</span><span class="sxs-lookup"><span data-stu-id="3429d-277">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="3429d-278">Чтобы найти разделитель списка для языка и региональных параметров, используйте следующую команду: `(Get-Culture).TextInfo.ListSeparator` .</span><span class="sxs-lookup"><span data-stu-id="3429d-278">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

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

### <span data-ttu-id="3429d-279">-Confirm</span><span class="sxs-lookup"><span data-stu-id="3429d-279">-Confirm</span></span>

<span data-ttu-id="3429d-280">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="3429d-280">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="3429d-281">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="3429d-281">-WhatIf</span></span>

<span data-ttu-id="3429d-282">Предотвращает обработку командлета или внесение изменений.</span><span class="sxs-lookup"><span data-stu-id="3429d-282">Prevents the cmdlet from being processed or making changes.</span></span> <span data-ttu-id="3429d-283">Выходные данные показывают, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="3429d-283">The output shows what would happen if the cmdlet were run.</span></span>

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

### <span data-ttu-id="3429d-284">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3429d-284">CommonParameters</span></span>

<span data-ttu-id="3429d-285">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3429d-285">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3429d-286">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3429d-286">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3429d-287">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3429d-287">INPUTS</span></span>

### <span data-ttu-id="3429d-288">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="3429d-288">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="3429d-289">Любой объект с адаптером системы расширенного типа (ETS) можно передать в `Export-CSV` .</span><span class="sxs-lookup"><span data-stu-id="3429d-289">You can pipe any object with an Extended Type System (ETS) adapter to `Export-CSV`.</span></span>

## <span data-ttu-id="3429d-290">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3429d-290">OUTPUTS</span></span>

### <span data-ttu-id="3429d-291">System.String</span><span class="sxs-lookup"><span data-stu-id="3429d-291">System.String</span></span>

<span data-ttu-id="3429d-292">Список CSV-файлов отправляется в файл, указанный в параметре Path.</span><span class="sxs-lookup"><span data-stu-id="3429d-292">The CSV list is sent to the file designated in the Path parameter.</span></span>

## <span data-ttu-id="3429d-293">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3429d-293">NOTES</span></span>

<span data-ttu-id="3429d-294">`Export-CSV`Командлет преобразует объекты, которые вы отправляете, в последовательность строк CSV и сохраняет их в указанном текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="3429d-294">The `Export-CSV` cmdlet converts the objects that you submit into a series of CSV strings and saves them in the specified text file.</span></span> <span data-ttu-id="3429d-295">Можно использовать `Export-CSV -IncludeTypeInformation` для сохранения объектов в CSV-файле, а затем использовать `Import-Csv` командлет для создания объектов из текста в CSV-файле.</span><span class="sxs-lookup"><span data-stu-id="3429d-295">You can use `Export-CSV -IncludeTypeInformation` to save objects in a CSV file and then use the `Import-Csv` cmdlet to create objects from the text in the CSV file.</span></span>

<span data-ttu-id="3429d-296">В CSV-файле каждый объект представлен списком значений свойств объекта с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="3429d-296">In the CSV file, each object is represented by a comma-separated list of the property values of the object.</span></span> <span data-ttu-id="3429d-297">Значения свойств преобразуются в строки с помощью метода **ToString ()** .</span><span class="sxs-lookup"><span data-stu-id="3429d-297">The property values are converted to strings using the **ToString()** method.</span></span> <span data-ttu-id="3429d-298">Строки представлены именем значения свойства.</span><span class="sxs-lookup"><span data-stu-id="3429d-298">The strings are represented by the property value name.</span></span> <span data-ttu-id="3429d-299">`Export-CSV -IncludeTypeInformation` не экспортирует методы объекта.</span><span class="sxs-lookup"><span data-stu-id="3429d-299">`Export-CSV -IncludeTypeInformation` does not export the methods of the object.</span></span>

<span data-ttu-id="3429d-300">Строки CSV выводятся следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3429d-300">The CSV strings are output as follows:</span></span>

- <span data-ttu-id="3429d-301">Если используется **инклудетипеинформатион** , первая строка содержит заголовок **#TYPE** сведений, за которым следует полное имя типа объекта.</span><span class="sxs-lookup"><span data-stu-id="3429d-301">If **IncludeTypeInformation** is used, the first string contains the **#TYPE** information header followed by the object type's fully qualified name.</span></span>
  <span data-ttu-id="3429d-302">Например, **#TYPE System. Diagnostics. Process** .</span><span class="sxs-lookup"><span data-stu-id="3429d-302">For example, **#TYPE System.Diagnostics.Process** .</span></span>
- <span data-ttu-id="3429d-303">Если **инклудетипеинформатион** не используется, первая строка включает заголовки столбцов.</span><span class="sxs-lookup"><span data-stu-id="3429d-303">If **IncludeTypeInformation** is not used the first string includes the column headers.</span></span> <span data-ttu-id="3429d-304">Заголовки содержат имена свойств первого объекта в виде списка с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="3429d-304">The headers contain the first object's property names as a comma-separated list.</span></span>
- <span data-ttu-id="3429d-305">Остальные строки содержат разделенные запятыми списки значений свойств каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="3429d-305">The remaining strings contain comma-separated lists of each object's property values.</span></span>

<span data-ttu-id="3429d-306">Начиная с PowerShell 6,0 поведение по умолчанию `Export-CSV` — не включать сведения о **#TYPE** в CSV-файл, а **NoTypeInformation** является подразумеваемым.</span><span class="sxs-lookup"><span data-stu-id="3429d-306">Beginning with PowerShell 6.0 the default behavior of `Export-CSV` is to not include the **#TYPE** information in the CSV and **NoTypeInformation** is implied.</span></span> <span data-ttu-id="3429d-307">**Инклудетипеинформатион** можно использовать для включения сведений о **#TYPE** и эмуляции поведения по умолчанию `Export-CSV` до PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="3429d-307">**IncludeTypeInformation** can be used to include the **#TYPE** Information and emulate the default behavior of `Export-CSV` prior to PowerShell 6.0.</span></span>

<span data-ttu-id="3429d-308">При отправке нескольких объектов в `Export-CSV` `Export-CSV` файл упорядочивается по свойствам первого отправленного объекта.</span><span class="sxs-lookup"><span data-stu-id="3429d-308">When you submit multiple objects to `Export-CSV`, `Export-CSV` organizes the file based on the properties of the first object that you submit.</span></span> <span data-ttu-id="3429d-309">Если остальные объекты не имеют одного из указанных свойств, значение этого свойства для объекта будет пустым, то есть представлено двумя идущими подряд запятыми.</span><span class="sxs-lookup"><span data-stu-id="3429d-309">If the remaining objects do not have one of the specified properties, the property value of that object is null, as represented by two consecutive commas.</span></span> <span data-ttu-id="3429d-310">Если оставшиеся объекты содержат дополнительные свойства, их значения не включаются в файл.</span><span class="sxs-lookup"><span data-stu-id="3429d-310">If the remaining objects have additional properties, those property values are not included in the file.</span></span>

<span data-ttu-id="3429d-311">Командлет можно использовать `Import-Csv` для повторного создания объектов из строк CSV в файлах.</span><span class="sxs-lookup"><span data-stu-id="3429d-311">You can use the `Import-Csv` cmdlet to recreate objects from the CSV strings in the files.</span></span> <span data-ttu-id="3429d-312">Полученные объекты являются версиями CSV-файлов исходных объектов, которые состоят из представлений строк значений свойств без методов.</span><span class="sxs-lookup"><span data-stu-id="3429d-312">The resulting objects are CSV versions of the original objects that consist of string representations of the property values and no methods.</span></span>

<span data-ttu-id="3429d-313">`ConvertTo-Csv` `ConvertFrom-Csv` Командлеты и преобразуют объекты в строки CSV и из строк CSV.</span><span class="sxs-lookup"><span data-stu-id="3429d-313">The `ConvertTo-Csv` and `ConvertFrom-Csv` cmdlets convert objects to CSV strings and from CSV strings.</span></span> <span data-ttu-id="3429d-314">`Export-CSV` совпадает с `ConvertTo-CSV` , за исключением того, что строки CSV сохраняются в файле.</span><span class="sxs-lookup"><span data-stu-id="3429d-314">`Export-CSV` is the same as `ConvertTo-CSV`, except that it saves the CSV strings in a file.</span></span>

## <span data-ttu-id="3429d-315">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3429d-315">RELATED LINKS</span></span>

[<span data-ttu-id="3429d-316">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="3429d-316">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="3429d-317">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="3429d-317">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="3429d-318">Format-Table</span><span class="sxs-lookup"><span data-stu-id="3429d-318">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="3429d-319">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="3429d-319">Import-Csv</span></span>](Import-Csv.md)

[<span data-ttu-id="3429d-320">Select-Object</span><span class="sxs-lookup"><span data-stu-id="3429d-320">Select-Object</span></span>](Select-Object.md)
