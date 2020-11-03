---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 1/7/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-csv?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Csv
ms.openlocfilehash: 7d399661e4514c0a39ad00601d554c41c2897ff9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227733"
---
# <span data-ttu-id="04856-103">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="04856-103">ConvertTo-Csv</span></span>

## <span data-ttu-id="04856-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="04856-104">SYNOPSIS</span></span>
<span data-ttu-id="04856-105">Преобразует объекты .NET в последовательность строк значений с разделителями-запятыми (CSV).</span><span class="sxs-lookup"><span data-stu-id="04856-105">Converts .NET objects into a series of comma-separated value (CSV) strings.</span></span>

## <span data-ttu-id="04856-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="04856-106">SYNTAX</span></span>

### <span data-ttu-id="04856-107">Delimiter (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="04856-107">Delimiter (Default)</span></span>

```
ConvertTo-Csv [-InputObject] <psobject> [[-Delimiter] <char>] [-NoTypeInformation]
 [<CommonParameters>]
```

### <span data-ttu-id="04856-108">UseCulture</span><span class="sxs-lookup"><span data-stu-id="04856-108">UseCulture</span></span>

```
ConvertTo-Csv [-InputObject] <psobject> [-UseCulture] [-NoTypeInformation] [<CommonParameters>]
```

## <span data-ttu-id="04856-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="04856-109">DESCRIPTION</span></span>

<span data-ttu-id="04856-110">`ConvertTo-CSV`Командлет возвращает ряд строк с разделителями-запятыми (CSV), представляющих отправляемые объекты.</span><span class="sxs-lookup"><span data-stu-id="04856-110">The `ConvertTo-CSV` cmdlet returns a series of comma-separated value (CSV) strings that represent the objects that you submit.</span></span> <span data-ttu-id="04856-111">Затем можно использовать `ConvertFrom-Csv` командлет для повторного создания объектов из строк CSV.</span><span class="sxs-lookup"><span data-stu-id="04856-111">You can then use the `ConvertFrom-Csv` cmdlet to recreate objects from the CSV strings.</span></span> <span data-ttu-id="04856-112">Объекты, преобразованные из CSV, являются строковыми значениями исходных объектов, которые содержат значения свойств и не имеют методов.</span><span class="sxs-lookup"><span data-stu-id="04856-112">The objects converted from CSV are string values of the original objects that contain property values and no methods.</span></span>

<span data-ttu-id="04856-113">`Export-Csv`Для преобразования объектов в строки CSV можно использовать командлет.</span><span class="sxs-lookup"><span data-stu-id="04856-113">You can use the `Export-Csv` cmdlet to convert objects to CSV strings.</span></span> <span data-ttu-id="04856-114">`Export-CSV` аналогичен `ConvertTo-CSV` , за исключением того, что строки CSV сохраняются в файл.</span><span class="sxs-lookup"><span data-stu-id="04856-114">`Export-CSV` is similar to `ConvertTo-CSV`, except that it saves the CSV strings to a file.</span></span>

<span data-ttu-id="04856-115">`ConvertTo-CSV`Командлет имеет параметры для указания разделителя, отличного от запятой, или использовать текущий язык и региональные параметры в качестве разделителя.</span><span class="sxs-lookup"><span data-stu-id="04856-115">The `ConvertTo-CSV` cmdlet has parameters to specify a delimiter other than a comma or use the current culture as the delimiter.</span></span>

## <span data-ttu-id="04856-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="04856-116">EXAMPLES</span></span>

### <span data-ttu-id="04856-117">Пример 1. преобразование объекта в CSV-файл</span><span class="sxs-lookup"><span data-stu-id="04856-117">Example 1: Convert an object to CSV</span></span>

<span data-ttu-id="04856-118">В этом примере объект **процесса** преобразуется в строку CSV.</span><span class="sxs-lookup"><span data-stu-id="04856-118">This example converts a **Process** object to a CSV string.</span></span>

```powershell
Get-Process -Name 'PowerShell' | ConvertTo-Csv -NoTypeInformation
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Company","CPU","FileVersion", ...
"powershell","11","691","2204036739072","175943680","132665344","33312", ...
```

<span data-ttu-id="04856-119">`Get-Process`Командлет получает объект **процесса** и использует параметр **Name** для указания процесса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="04856-119">The `Get-Process` cmdlet gets the **Process** object and uses the **Name** parameter to specify the PowerShell process.</span></span> <span data-ttu-id="04856-120">Объект процесса отправляется в командлет по конвейеру `ConvertTo-CSV` .</span><span class="sxs-lookup"><span data-stu-id="04856-120">The process object is sent down the pipeline to the `ConvertTo-CSV` cmdlet.</span></span> <span data-ttu-id="04856-121">`ConvertTo-CSV`Командлет преобразует объект в строки CSV.</span><span class="sxs-lookup"><span data-stu-id="04856-121">The `ConvertTo-CSV` cmdlet converts the object to CSV strings.</span></span> <span data-ttu-id="04856-122">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV.</span><span class="sxs-lookup"><span data-stu-id="04856-122">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output.</span></span>

### <span data-ttu-id="04856-123">Пример 2. преобразование объекта DateTime в CSV-файл</span><span class="sxs-lookup"><span data-stu-id="04856-123">Example 2: Convert a DateTime object to CSV</span></span>

<span data-ttu-id="04856-124">В этом примере объект **DateTime** преобразуется в строку CSV.</span><span class="sxs-lookup"><span data-stu-id="04856-124">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
$Date = Get-Date
ConvertTo-Csv -InputObject $Date -Delimiter ';' -NoTypeInformation
```

```Output
"DisplayHint";"DateTime";"Date";"Day";"DayOfWeek";"DayOfYear";"Hour";"Kind";"Millisecond";"Minute";"Month";"Second";"Ticks";"TimeOfDay";"Year"
"DateTime";"Friday, January 4, 2019 14:40:51";"1/4/2019 00:00:00";"4";"Friday";"4";"14";"Local";"711";"40";"1";"51";"636822096517114991";"14:40:51.7114991";"2019"
```

<span data-ttu-id="04856-125">`Get-Date`Командлет возвращает объект **DateTime** и сохраняет его в `$Date` переменной.</span><span class="sxs-lookup"><span data-stu-id="04856-125">The `Get-Date` cmdlet gets the **DateTime** object and saves it in the `$Date` variable.</span></span> <span data-ttu-id="04856-126">`ConvertTo-Csv`Командлет преобразует объект **DateTime** в строки.</span><span class="sxs-lookup"><span data-stu-id="04856-126">The `ConvertTo-Csv` cmdlet converts the **DateTime** object to strings.</span></span> <span data-ttu-id="04856-127">Параметр **InputObject** использует объект **DateTime** , хранящийся в `$Date` переменной.</span><span class="sxs-lookup"><span data-stu-id="04856-127">The **InputObject** parameter uses the **DateTime** object stored in the `$Date` variable.</span></span> <span data-ttu-id="04856-128">Параметр- **Разделитель** задает точку с запятой для разделения строковых значений.</span><span class="sxs-lookup"><span data-stu-id="04856-128">The **Delimiter** parameter specifies a semicolon to separate the string values.</span></span> <span data-ttu-id="04856-129">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV.</span><span class="sxs-lookup"><span data-stu-id="04856-129">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output.</span></span>

### <span data-ttu-id="04856-130">Пример 3. преобразование журнала событий PowerShell в CSV-файл</span><span class="sxs-lookup"><span data-stu-id="04856-130">Example 3: Convert the PowerShell event log to CSV</span></span>

<span data-ttu-id="04856-131">В этом примере журнал событий Windows для PowerShell преобразуется в последовательность строк CSV.</span><span class="sxs-lookup"><span data-stu-id="04856-131">This example converts the Windows event log for PowerShell to a series of CSV strings.</span></span>

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-WinEvent -LogName 'Windows PowerShell' | ConvertTo-Csv -UseCulture -NoTypeInformation
```

```Output
,
"Message","Id","Version","Qualifiers","Level","Task","Opcode","Keywords","RecordId", ...
"Error Message = System error","403",,"0","4","4",,"36028797018963968","46891","PowerShell", ...
```

<span data-ttu-id="04856-132">`Get-Culture`Командлет использует вложенные свойства **TextInfo** и **ListSeparator** и отображает текущий разделитель списка по умолчанию для текущего языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="04856-132">The `Get-Culture` cmdlet uses the nested properties **TextInfo** and **ListSeparator** and displays the current culture's default list separator.</span></span> <span data-ttu-id="04856-133">`Get-WinEvent`Командлет получает объекты журнала событий и использует параметр " **/l** " для указания имени файла журнала.</span><span class="sxs-lookup"><span data-stu-id="04856-133">The `Get-WinEvent` cmdlet gets the event log objects and uses the **LogName** parameter to specify the log file name.</span></span> <span data-ttu-id="04856-134">Объекты журнала событий отправляются по конвейеру в `ConvertTo-Csv` командлет.</span><span class="sxs-lookup"><span data-stu-id="04856-134">The event log objects are sent down the pipeline to the `ConvertTo-Csv` cmdlet.</span></span> <span data-ttu-id="04856-135">`ConvertTo-Csv`Командлет преобразует объекты журнала событий в последовательность строк CSV.</span><span class="sxs-lookup"><span data-stu-id="04856-135">The `ConvertTo-Csv` cmdlet converts the event log objects to a series of CSV strings.</span></span> <span data-ttu-id="04856-136">Параметр **UseCulture** использует разделитель списка по умолчанию текущего языка и региональных параметров в качестве разделителя.</span><span class="sxs-lookup"><span data-stu-id="04856-136">The **UseCulture** parameter uses the current culture's default list separator as the delimiter.</span></span> <span data-ttu-id="04856-137">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV.</span><span class="sxs-lookup"><span data-stu-id="04856-137">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output.</span></span>

## <span data-ttu-id="04856-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="04856-138">PARAMETERS</span></span>

### <span data-ttu-id="04856-139">-Delimiter</span><span class="sxs-lookup"><span data-stu-id="04856-139">-Delimiter</span></span>

<span data-ttu-id="04856-140">Задает разделитель значений свойств в строках CSV.</span><span class="sxs-lookup"><span data-stu-id="04856-140">Specifies the delimiter to separate the property values in CSV strings.</span></span> <span data-ttu-id="04856-141">Значение по умолчанию — запятая ( `,` ).</span><span class="sxs-lookup"><span data-stu-id="04856-141">The default is a comma (`,`).</span></span> <span data-ttu-id="04856-142">Введите символ, например двоеточие ( `:` ).</span><span class="sxs-lookup"><span data-stu-id="04856-142">Enter a character, such as a colon (`:`).</span></span> <span data-ttu-id="04856-143">Чтобы указать точку с запятой ( `;` ), заключите ее в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="04856-143">To specify a semicolon (`;`) enclose it in single quotation marks.</span></span>

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

### <span data-ttu-id="04856-144">-InputObject</span><span class="sxs-lookup"><span data-stu-id="04856-144">-InputObject</span></span>

<span data-ttu-id="04856-145">Указывает объекты, которые преобразуются в строки CSV.</span><span class="sxs-lookup"><span data-stu-id="04856-145">Specifies the objects that are converted to CSV strings.</span></span> <span data-ttu-id="04856-146">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="04856-146">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="04856-147">Также можно передать объекты в `ConvertTo-CSV` .</span><span class="sxs-lookup"><span data-stu-id="04856-147">You can also pipe objects to `ConvertTo-CSV`.</span></span>

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

### <span data-ttu-id="04856-148">-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="04856-148">-NoTypeInformation</span></span>

<span data-ttu-id="04856-149">Удаляет заголовок сведений о **#TYPE** из выходных данных.</span><span class="sxs-lookup"><span data-stu-id="04856-149">Removes the **#TYPE** information header from the output.</span></span> <span data-ttu-id="04856-150">Этот параметр стал значением по умолчанию в PowerShell 6,0 и включен для обеспечения обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="04856-150">This parameter became the default in PowerShell 6.0 and is included for backwards compatibility.</span></span>

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

### <span data-ttu-id="04856-151">-UseCulture</span><span class="sxs-lookup"><span data-stu-id="04856-151">-UseCulture</span></span>

<span data-ttu-id="04856-152">Использует разделитель списка для текущего языка и региональных параметров в качестве разделителя элементов.</span><span class="sxs-lookup"><span data-stu-id="04856-152">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="04856-153">Чтобы найти разделитель списка для языка и региональных параметров, используйте следующую команду: `(Get-Culture).TextInfo.ListSeparator` .</span><span class="sxs-lookup"><span data-stu-id="04856-153">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

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

### <span data-ttu-id="04856-154">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="04856-154">CommonParameters</span></span>

<span data-ttu-id="04856-155">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="04856-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="04856-156">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="04856-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="04856-157">Входные данные</span><span class="sxs-lookup"><span data-stu-id="04856-157">INPUTS</span></span>

### <span data-ttu-id="04856-158">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="04856-158">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="04856-159">Любой объект, имеющий адаптер расширенной системы типов (ETS), можно передать в `ConvertTo-CSV` .</span><span class="sxs-lookup"><span data-stu-id="04856-159">You can pipe any object that has an Extended Type System (ETS) adapter to `ConvertTo-CSV`.</span></span>

## <span data-ttu-id="04856-160">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="04856-160">OUTPUTS</span></span>

### <span data-ttu-id="04856-161">System.String</span><span class="sxs-lookup"><span data-stu-id="04856-161">System.String</span></span>

<span data-ttu-id="04856-162">Выходные данные в формате CSV возвращаются в виде коллекции строк.</span><span class="sxs-lookup"><span data-stu-id="04856-162">The CSV output is returned as a collection of strings.</span></span>

## <span data-ttu-id="04856-163">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="04856-163">NOTES</span></span>

<span data-ttu-id="04856-164">В формате CSV каждый объект представлен как разделенный запятыми список значений свойств.</span><span class="sxs-lookup"><span data-stu-id="04856-164">In CSV format, each object is represented by a comma-separated list of its property value.</span></span> <span data-ttu-id="04856-165">Значения свойств преобразуются в строки с помощью метода **ToString ()** объекта.</span><span class="sxs-lookup"><span data-stu-id="04856-165">The property values are converted to strings using the object's **ToString()** method.</span></span> <span data-ttu-id="04856-166">Строки представлены именем значения свойства.</span><span class="sxs-lookup"><span data-stu-id="04856-166">The strings are represented by the property value name.</span></span> <span data-ttu-id="04856-167">`ConvertTo-CSV` не экспортирует методы объекта.</span><span class="sxs-lookup"><span data-stu-id="04856-167">`ConvertTo-CSV` does not export the object's methods.</span></span>

<span data-ttu-id="04856-168">Строки CSV выводятся следующим образом:</span><span class="sxs-lookup"><span data-stu-id="04856-168">The CSV strings are output as follows:</span></span>

- <span data-ttu-id="04856-169">По умолчанию первая строка содержит заголовок **#TYPE** сведений, за которым следует полное имя типа объекта.</span><span class="sxs-lookup"><span data-stu-id="04856-169">By default the first string contains the **#TYPE** information header followed by the object type's fully qualified name.</span></span> <span data-ttu-id="04856-170">Например, **#TYPE System. Diagnostics. Process**.</span><span class="sxs-lookup"><span data-stu-id="04856-170">For example, **#TYPE System.Diagnostics.Process**.</span></span>
- <span data-ttu-id="04856-171">Если используется **NoTypeInformation** , первая строка включает заголовки столбцов.</span><span class="sxs-lookup"><span data-stu-id="04856-171">If **NoTypeInformation** is used the first string includes the column headers.</span></span> <span data-ttu-id="04856-172">Заголовки содержат имена свойств первого объекта в виде списка с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="04856-172">The headers contain the first object's property names as a comma-separated list.</span></span>
- <span data-ttu-id="04856-173">Остальные строки содержат разделенные запятыми списки значений свойств каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="04856-173">The remaining strings contain comma-separated lists of each object's property values.</span></span>

<span data-ttu-id="04856-174">При отправке нескольких объектов в `ConvertTo-CSV` `ConvertTo-CSV` упорядочивает строки на основе свойств первого отправленного объекта.</span><span class="sxs-lookup"><span data-stu-id="04856-174">When you submit multiple objects to `ConvertTo-CSV`, `ConvertTo-CSV` orders the strings based on the properties of the first object that you submit.</span></span> <span data-ttu-id="04856-175">Если остальные объекты не имеют одного из указанных свойств, значение свойства этого объекта равно null, как представлено двумя последовательными запятыми.</span><span class="sxs-lookup"><span data-stu-id="04856-175">If the remaining objects do not have one of the specified properties, the property value of that object is Null, as represented by two consecutive commas.</span></span> <span data-ttu-id="04856-176">Если у остальных объектов есть дополнительные свойства, их значения игнорируются.</span><span class="sxs-lookup"><span data-stu-id="04856-176">If the remaining objects have additional properties, those property values are ignored.</span></span>

## <span data-ttu-id="04856-177">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="04856-177">RELATED LINKS</span></span>

[<span data-ttu-id="04856-178">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="04856-178">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="04856-179">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="04856-179">Export-Csv</span></span>](Export-Csv.md)

[<span data-ttu-id="04856-180">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="04856-180">Import-Csv</span></span>](Import-Csv.md)
