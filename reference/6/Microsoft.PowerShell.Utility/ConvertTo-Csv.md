---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 1/7/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-csv?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Csv
ms.openlocfilehash: 5de6a3bd28b850d3fc1632e26998986f302b78f8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229078"
---
# <span data-ttu-id="19277-103">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="19277-103">ConvertTo-Csv</span></span>

## <span data-ttu-id="19277-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="19277-104">SYNOPSIS</span></span>
<span data-ttu-id="19277-105">Преобразует объекты .NET в последовательность строк значений, разделенных символами (CSV).</span><span class="sxs-lookup"><span data-stu-id="19277-105">Converts .NET objects into a series of character-separated value (CSV) strings.</span></span>

## <span data-ttu-id="19277-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="19277-106">SYNTAX</span></span>

### <span data-ttu-id="19277-107">Делимитерпас (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="19277-107">DelimiterPath (Default)</span></span>

```
ConvertTo-Csv [-InputObject] <PSObject> [-IncludeTypeInformation] [-NoTypeInformation]
 [<CommonParameters>]
```

### <span data-ttu-id="19277-108">Разделитель</span><span class="sxs-lookup"><span data-stu-id="19277-108">Delimiter</span></span>

```
ConvertTo-Csv [-InputObject] <PSObject> [[-Delimiter] <Char>] [-IncludeTypeInformation]
 [-NoTypeInformation] [<CommonParameters>]
```

### <span data-ttu-id="19277-109">UseCulture</span><span class="sxs-lookup"><span data-stu-id="19277-109">UseCulture</span></span>

```
ConvertTo-Csv [-InputObject] <PSObject> [-UseCulture] [-IncludeTypeInformation] [-NoTypeInformation]
 [<CommonParameters>]
```

## <span data-ttu-id="19277-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="19277-110">DESCRIPTION</span></span>

<span data-ttu-id="19277-111">`ConvertTo-CSV`Командлет возвращает ряд строк с разделителями-запятыми (CSV), представляющих отправляемые объекты.</span><span class="sxs-lookup"><span data-stu-id="19277-111">The `ConvertTo-CSV` cmdlet returns a series of comma-separated value (CSV) strings that represent the objects that you submit.</span></span> <span data-ttu-id="19277-112">Затем можно использовать `ConvertFrom-Csv` командлет для повторного создания объектов из строк CSV.</span><span class="sxs-lookup"><span data-stu-id="19277-112">You can then use the `ConvertFrom-Csv` cmdlet to recreate objects from the CSV strings.</span></span> <span data-ttu-id="19277-113">Объекты, преобразованные из CSV, являются строковыми значениями исходных объектов, которые содержат значения свойств и не имеют методов.</span><span class="sxs-lookup"><span data-stu-id="19277-113">The objects converted from CSV are string values of the original objects that contain property values and no methods.</span></span>

<span data-ttu-id="19277-114">`Export-Csv`Для преобразования объектов в строки CSV можно использовать командлет.</span><span class="sxs-lookup"><span data-stu-id="19277-114">You can use the `Export-Csv` cmdlet to convert objects to CSV strings.</span></span> <span data-ttu-id="19277-115">`Export-CSV` аналогичен `ConvertTo-CSV` , за исключением того, что строки CSV сохраняются в файл.</span><span class="sxs-lookup"><span data-stu-id="19277-115">`Export-CSV` is similar to `ConvertTo-CSV`, except that it saves the CSV strings to a file.</span></span>

<span data-ttu-id="19277-116">`ConvertTo-CSV`Командлет имеет параметры для указания разделителя, отличного от запятой, или использовать текущий язык и региональные параметры в качестве разделителя.</span><span class="sxs-lookup"><span data-stu-id="19277-116">The `ConvertTo-CSV` cmdlet has parameters to specify a delimiter other than a comma or use the current culture as the delimiter.</span></span>

## <span data-ttu-id="19277-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="19277-117">EXAMPLES</span></span>

### <span data-ttu-id="19277-118">Пример 1. преобразование объекта в CSV-файл</span><span class="sxs-lookup"><span data-stu-id="19277-118">Example 1: Convert an object to CSV</span></span>

<span data-ttu-id="19277-119">В этом примере объект **процесса** преобразуется в строку CSV.</span><span class="sxs-lookup"><span data-stu-id="19277-119">This example converts a **Process** object to a CSV string.</span></span>

```powershell
Get-Process -Name pwsh | ConvertTo-Csv -NoTypeInformation
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"pwsh","8","950","2204001161216","100925440","59686912","67104", ...
```

<span data-ttu-id="19277-120">`Get-Process`Командлет получает объект **процесса** и использует параметр **Name** для указания процесса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19277-120">The `Get-Process` cmdlet gets the **Process** object and uses the **Name** parameter to specify the PowerShell process.</span></span> <span data-ttu-id="19277-121">Объект процесса отправляется в командлет по конвейеру `ConvertTo-CSV` .</span><span class="sxs-lookup"><span data-stu-id="19277-121">The process object is sent down the pipeline to the `ConvertTo-CSV` cmdlet.</span></span> <span data-ttu-id="19277-122">`ConvertTo-CSV`Командлет преобразует объект в строки CSV.</span><span class="sxs-lookup"><span data-stu-id="19277-122">The `ConvertTo-CSV` cmdlet converts the object to CSV strings.</span></span> <span data-ttu-id="19277-123">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="19277-123">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

### <span data-ttu-id="19277-124">Пример 2. преобразование объекта DateTime в CSV-файл</span><span class="sxs-lookup"><span data-stu-id="19277-124">Example 2: Convert a DateTime object to CSV</span></span>

<span data-ttu-id="19277-125">В этом примере объект **DateTime** преобразуется в строку CSV.</span><span class="sxs-lookup"><span data-stu-id="19277-125">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
$Date = Get-Date
ConvertTo-Csv -InputObject $Date -Delimiter ';' -NoTypeInformation
```

```Output
"DisplayHint";"DateTime";"Date";"Day";"DayOfWeek";"DayOfYear";"Hour";"Kind";"Millisecond";"Minute";"Month";"Second";"Ticks";"TimeOfDay";"Year"
"DateTime";"Friday, January 4, 2019 14:40:51";"1/4/2019 00:00:00";"4";"Friday";"4";"14";"Local";"711";"40";"1";"51";"636822096517114991";"14:40:51.7114991";"2019"
```

<span data-ttu-id="19277-126">`Get-Date`Командлет возвращает объект **DateTime** и сохраняет его в `$Date` переменной.</span><span class="sxs-lookup"><span data-stu-id="19277-126">The `Get-Date` cmdlet gets the **DateTime** object and saves it in the `$Date` variable.</span></span> <span data-ttu-id="19277-127">`ConvertTo-Csv`Командлет преобразует объект **DateTime** в строки.</span><span class="sxs-lookup"><span data-stu-id="19277-127">The `ConvertTo-Csv` cmdlet converts the **DateTime** object to strings.</span></span> <span data-ttu-id="19277-128">Параметр **InputObject** использует объект **DateTime** , хранящийся в `$Date` переменной.</span><span class="sxs-lookup"><span data-stu-id="19277-128">The **InputObject** parameter uses the **DateTime** object stored in the `$Date` variable.</span></span> <span data-ttu-id="19277-129">Параметр- **Разделитель** задает точку с запятой для разделения строковых значений.</span><span class="sxs-lookup"><span data-stu-id="19277-129">The **Delimiter** parameter specifies a semicolon to separate the string values.</span></span> <span data-ttu-id="19277-130">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="19277-130">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

### <span data-ttu-id="19277-131">Пример 3. преобразование журнала событий PowerShell в CSV-файл</span><span class="sxs-lookup"><span data-stu-id="19277-131">Example 3: Convert the PowerShell event log to CSV</span></span>

<span data-ttu-id="19277-132">В этом примере журнал событий Windows для PowerShell преобразуется в последовательность строк CSV.</span><span class="sxs-lookup"><span data-stu-id="19277-132">This example converts the Windows event log for PowerShell to a series of CSV strings.</span></span>

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-WinEvent -LogName 'PowerShellCore/Operational' | ConvertTo-Csv -UseCulture -NoTypeInformation
```

```Output
,
"Message","Id","Version","Qualifiers","Level","Task","Opcode","Keywords","RecordId", ...
"Error Message = System error""4100","1",,"3","106","19","0","31716","PowerShellCore", ...
```

<span data-ttu-id="19277-133">`Get-Culture`Командлет использует вложенные свойства **TextInfo** и **ListSeparator** и отображает текущий разделитель списка по умолчанию для текущего языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="19277-133">The `Get-Culture` cmdlet uses the nested properties **TextInfo** and **ListSeparator** and displays the current culture's default list separator.</span></span> <span data-ttu-id="19277-134">`Get-WinEvent`Командлет получает объекты журнала событий и использует параметр " **/l** " для указания имени файла журнала.</span><span class="sxs-lookup"><span data-stu-id="19277-134">The `Get-WinEvent` cmdlet gets the event log objects and uses the **LogName** parameter to specify the log file name.</span></span> <span data-ttu-id="19277-135">Объекты журнала событий отправляются по конвейеру в `ConvertTo-Csv` командлет.</span><span class="sxs-lookup"><span data-stu-id="19277-135">The event log objects are sent down the pipeline to the `ConvertTo-Csv` cmdlet.</span></span> <span data-ttu-id="19277-136">`ConvertTo-Csv`Командлет преобразует объекты журнала событий в последовательность строк CSV.</span><span class="sxs-lookup"><span data-stu-id="19277-136">The `ConvertTo-Csv` cmdlet converts the event log objects to a series of CSV strings.</span></span> <span data-ttu-id="19277-137">Параметр **UseCulture** использует разделитель списка по умолчанию текущего языка и региональных параметров в качестве разделителя.</span><span class="sxs-lookup"><span data-stu-id="19277-137">The **UseCulture** parameter uses the current culture's default list separator as the delimiter.</span></span> <span data-ttu-id="19277-138">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="19277-138">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

## <span data-ttu-id="19277-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="19277-139">PARAMETERS</span></span>

### <span data-ttu-id="19277-140">-Delimiter</span><span class="sxs-lookup"><span data-stu-id="19277-140">-Delimiter</span></span>

<span data-ttu-id="19277-141">Задает разделитель значений свойств в строках CSV.</span><span class="sxs-lookup"><span data-stu-id="19277-141">Specifies the delimiter to separate the property values in CSV strings.</span></span> <span data-ttu-id="19277-142">Значение по умолчанию — запятая ( `,` ).</span><span class="sxs-lookup"><span data-stu-id="19277-142">The default is a comma (`,`).</span></span> <span data-ttu-id="19277-143">Введите символ, например двоеточие ( `:` ).</span><span class="sxs-lookup"><span data-stu-id="19277-143">Enter a character, such as a colon (`:`).</span></span> <span data-ttu-id="19277-144">Чтобы указать точку с запятой ( `;` ), заключите ее в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="19277-144">To specify a semicolon (`;`) enclose it in single quotation marks.</span></span>

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

### <span data-ttu-id="19277-145">-Инклудетипеинформатион</span><span class="sxs-lookup"><span data-stu-id="19277-145">-IncludeTypeInformation</span></span>

<span data-ttu-id="19277-146">При использовании этого параметра первая строка выходных данных содержит **#TYPE** , за которыми следует полное имя типа объекта.</span><span class="sxs-lookup"><span data-stu-id="19277-146">When this parameter is used the first line of the output contains **#TYPE** followed by the fully qualified name of the object type.</span></span> <span data-ttu-id="19277-147">Например, **#TYPE System. Diagnostics. Process** .</span><span class="sxs-lookup"><span data-stu-id="19277-147">For example, **#TYPE System.Diagnostics.Process** .</span></span>

<span data-ttu-id="19277-148">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="19277-148">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="19277-149">-InputObject</span><span class="sxs-lookup"><span data-stu-id="19277-149">-InputObject</span></span>

<span data-ttu-id="19277-150">Указывает объекты, которые преобразуются в строки CSV.</span><span class="sxs-lookup"><span data-stu-id="19277-150">Specifies the objects that are converted to CSV strings.</span></span> <span data-ttu-id="19277-151">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="19277-151">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="19277-152">Также можно передать объекты в `ConvertTo-CSV` .</span><span class="sxs-lookup"><span data-stu-id="19277-152">You can also pipe objects to `ConvertTo-CSV`.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="19277-153">-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="19277-153">-NoTypeInformation</span></span>

<span data-ttu-id="19277-154">Удаляет заголовок сведений о **#TYPE** из выходных данных.</span><span class="sxs-lookup"><span data-stu-id="19277-154">Removes the **#TYPE** information header from the output.</span></span> <span data-ttu-id="19277-155">Этот параметр стал значением по умолчанию в PowerShell 6,0 и включен для обеспечения обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="19277-155">This parameter became the default in PowerShell 6.0 and is included for backwards compatibility.</span></span>

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

### <span data-ttu-id="19277-156">-UseCulture</span><span class="sxs-lookup"><span data-stu-id="19277-156">-UseCulture</span></span>

<span data-ttu-id="19277-157">Использует разделитель списка для текущего языка и региональных параметров в качестве разделителя элементов.</span><span class="sxs-lookup"><span data-stu-id="19277-157">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="19277-158">Чтобы найти разделитель списка для языка и региональных параметров, используйте следующую команду: `(Get-Culture).TextInfo.ListSeparator` .</span><span class="sxs-lookup"><span data-stu-id="19277-158">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

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

### <span data-ttu-id="19277-159">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="19277-159">CommonParameters</span></span>

<span data-ttu-id="19277-160">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="19277-160">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="19277-161">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="19277-161">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="19277-162">Входные данные</span><span class="sxs-lookup"><span data-stu-id="19277-162">INPUTS</span></span>

### <span data-ttu-id="19277-163">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="19277-163">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="19277-164">Любой объект, имеющий адаптер расширенной системы типов (ETS), можно передать в `ConvertTo-CSV` .</span><span class="sxs-lookup"><span data-stu-id="19277-164">You can pipe any object that has an Extended Type System (ETS) adapter to `ConvertTo-CSV`.</span></span>

## <span data-ttu-id="19277-165">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="19277-165">OUTPUTS</span></span>

### <span data-ttu-id="19277-166">System.String</span><span class="sxs-lookup"><span data-stu-id="19277-166">System.String</span></span>

<span data-ttu-id="19277-167">Выходные данные в формате CSV возвращаются в виде коллекции строк.</span><span class="sxs-lookup"><span data-stu-id="19277-167">The CSV output is returned as a collection of strings.</span></span>

## <span data-ttu-id="19277-168">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="19277-168">NOTES</span></span>

<span data-ttu-id="19277-169">В формате CSV каждый объект представлен как разделенный запятыми список значений свойств.</span><span class="sxs-lookup"><span data-stu-id="19277-169">In CSV format, each object is represented by a comma-separated list of its property value.</span></span> <span data-ttu-id="19277-170">Значения свойств преобразуются в строки с помощью метода **ToString ()** объекта.</span><span class="sxs-lookup"><span data-stu-id="19277-170">The property values are converted to strings using the object's **ToString()** method.</span></span> <span data-ttu-id="19277-171">Строки представлены именем значения свойства.</span><span class="sxs-lookup"><span data-stu-id="19277-171">The strings are represented by the property value name.</span></span> <span data-ttu-id="19277-172">`ConvertTo-CSV` не экспортирует методы объекта.</span><span class="sxs-lookup"><span data-stu-id="19277-172">`ConvertTo-CSV` does not export the object's methods.</span></span>

<span data-ttu-id="19277-173">Строки CSV выводятся следующим образом:</span><span class="sxs-lookup"><span data-stu-id="19277-173">The CSV strings are output as follows:</span></span>

- <span data-ttu-id="19277-174">Если используется **инклудетипеинформатион** , первая строка состоит из **#TYPE** , за которой следует полное имя типа объекта.</span><span class="sxs-lookup"><span data-stu-id="19277-174">If **IncludeTypeInformation** is used, the first string consists of **#TYPE** followed by the object type's fully qualified name.</span></span> <span data-ttu-id="19277-175">Например, **#TYPE System. Diagnostics. Process** .</span><span class="sxs-lookup"><span data-stu-id="19277-175">For example, **#TYPE System.Diagnostics.Process** .</span></span>
- <span data-ttu-id="19277-176">Если **инклудетипеинформатион** не используется, первая строка включает заголовки столбцов.</span><span class="sxs-lookup"><span data-stu-id="19277-176">If **IncludeTypeInformation** is not used the first string includes the column headers.</span></span> <span data-ttu-id="19277-177">Заголовки содержат имена свойств первого объекта в виде списка с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="19277-177">The headers contain the first object's property names as a comma-separated list.</span></span>
- <span data-ttu-id="19277-178">Остальные строки содержат разделенные запятыми списки значений свойств каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="19277-178">The remaining strings contain comma-separated lists of each object's property values.</span></span>

<span data-ttu-id="19277-179">Начиная с PowerShell 6,0 поведение по умолчанию `ConvertTo-CSV` — не включать сведения о **#TYPE** в CSV-файл, а **NoTypeInformation** является подразумеваемым.</span><span class="sxs-lookup"><span data-stu-id="19277-179">Beginning with PowerShell 6.0 the default behavior of `ConvertTo-CSV` is to not include the **#TYPE** information in the CSV and **NoTypeInformation** is implied.</span></span> <span data-ttu-id="19277-180">**Инклудетипеинформатион** можно использовать для включения сведений о **#TYPE** и эмуляции поведения по умолчанию `ConvertTo-CSV` до PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="19277-180">**IncludeTypeInformation** can be used to include the **#TYPE** information and emulate the default behavior of `ConvertTo-CSV` prior to PowerShell 6.0.</span></span>

<span data-ttu-id="19277-181">При отправке нескольких объектов в `ConvertTo-CSV` `ConvertTo-CSV` упорядочивает строки на основе свойств первого отправленного объекта.</span><span class="sxs-lookup"><span data-stu-id="19277-181">When you submit multiple objects to `ConvertTo-CSV`, `ConvertTo-CSV` orders the strings based on the properties of the first object that you submit.</span></span> <span data-ttu-id="19277-182">Если остальные объекты не имеют одного из указанных свойств, значение свойства этого объекта равно null, как представлено двумя последовательными запятыми.</span><span class="sxs-lookup"><span data-stu-id="19277-182">If the remaining objects do not have one of the specified properties, the property value of that object is Null, as represented by two consecutive commas.</span></span> <span data-ttu-id="19277-183">Если у остальных объектов есть дополнительные свойства, их значения игнорируются.</span><span class="sxs-lookup"><span data-stu-id="19277-183">If the remaining objects have additional properties, those property values are ignored.</span></span>

## <span data-ttu-id="19277-184">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="19277-184">RELATED LINKS</span></span>

[<span data-ttu-id="19277-185">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="19277-185">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="19277-186">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="19277-186">Export-Csv</span></span>](Export-Csv.md)

[<span data-ttu-id="19277-187">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="19277-187">Import-Csv</span></span>](Import-Csv.md)
