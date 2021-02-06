---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-csv?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Csv
ms.openlocfilehash: df41ccf696e39d0bd6c90c118bd715ab83934cf2
ms.sourcegitcommit: 560a9f3c3148acab4655e91e8b07745ab74d5d26
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2020
ms.locfileid: "99600481"
---
# <span data-ttu-id="8ac2b-102">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="8ac2b-102">ConvertTo-Csv</span></span>

## <span data-ttu-id="8ac2b-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="8ac2b-103">SYNOPSIS</span></span>
<span data-ttu-id="8ac2b-104">Преобразует объекты .NET в последовательность строк значений, разделенных символами (CSV).</span><span class="sxs-lookup"><span data-stu-id="8ac2b-104">Converts .NET objects into a series of character-separated value (CSV) strings.</span></span>

## <span data-ttu-id="8ac2b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8ac2b-105">SYNTAX</span></span>

### <span data-ttu-id="8ac2b-106">Delimiter (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8ac2b-106">Delimiter (Default)</span></span>

```
ConvertTo-Csv [-InputObject] <PSObject> [[-Delimiter] <Char>] [-IncludeTypeInformation]
 [-NoTypeInformation] [-QuoteFields <String[]>] [-UseQuotes <QuoteKind>] [<CommonParameters>]
```

### <span data-ttu-id="8ac2b-107">UseCulture</span><span class="sxs-lookup"><span data-stu-id="8ac2b-107">UseCulture</span></span>

```
ConvertTo-Csv [-InputObject] <PSObject> [-UseCulture] [-IncludeTypeInformation] [-NoTypeInformation]
 [-QuoteFields <String[]>] [-UseQuotes <QuoteKind>] [<CommonParameters>]
```

## <span data-ttu-id="8ac2b-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8ac2b-108">DESCRIPTION</span></span>

<span data-ttu-id="8ac2b-109">`ConvertTo-CSV`Командлет возвращает ряд строк с разделителями-запятыми (CSV), представляющих отправляемые объекты.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-109">The `ConvertTo-CSV` cmdlet returns a series of comma-separated value (CSV) strings that represent the objects that you submit.</span></span> <span data-ttu-id="8ac2b-110">Затем можно использовать `ConvertFrom-Csv` командлет для повторного создания объектов из строк CSV.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-110">You can then use the `ConvertFrom-Csv` cmdlet to recreate objects from the CSV strings.</span></span> <span data-ttu-id="8ac2b-111">Объекты, преобразованные из CSV, являются строковыми значениями исходных объектов, которые содержат значения свойств и не имеют методов.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-111">The objects converted from CSV are string values of the original objects that contain property values and no methods.</span></span>

<span data-ttu-id="8ac2b-112">`Export-Csv`Для преобразования объектов в строки CSV можно использовать командлет.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-112">You can use the `Export-Csv` cmdlet to convert objects to CSV strings.</span></span> <span data-ttu-id="8ac2b-113">`Export-CSV` аналогичен `ConvertTo-CSV` , за исключением того, что строки CSV сохраняются в файл.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-113">`Export-CSV` is similar to `ConvertTo-CSV`, except that it saves the CSV strings to a file.</span></span>

<span data-ttu-id="8ac2b-114">`ConvertTo-CSV`Командлет имеет параметры для указания разделителя, отличного от запятой, или использовать текущий язык и региональные параметры в качестве разделителя.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-114">The `ConvertTo-CSV` cmdlet has parameters to specify a delimiter other than a comma or use the current culture as the delimiter.</span></span>

## <span data-ttu-id="8ac2b-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="8ac2b-115">EXAMPLES</span></span>

### <span data-ttu-id="8ac2b-116">Пример 1. преобразование объекта в CSV-файл</span><span class="sxs-lookup"><span data-stu-id="8ac2b-116">Example 1: Convert an object to CSV</span></span>

<span data-ttu-id="8ac2b-117">В этом примере объект **процесса** преобразуется в строку CSV.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-117">This example converts a **Process** object to a CSV string.</span></span>

```powershell
Get-Process -Name pwsh | ConvertTo-Csv -NoTypeInformation
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"pwsh","8","950","2204001161216","100925440","59686912","67104", ...
```

<span data-ttu-id="8ac2b-118">`Get-Process`Командлет получает объект **процесса** и использует параметр **Name** для указания процесса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-118">The `Get-Process` cmdlet gets the **Process** object and uses the **Name** parameter to specify the PowerShell process.</span></span> <span data-ttu-id="8ac2b-119">Объект процесса отправляется в командлет по конвейеру `ConvertTo-CSV` .</span><span class="sxs-lookup"><span data-stu-id="8ac2b-119">The process object is sent down the pipeline to the `ConvertTo-CSV` cmdlet.</span></span> <span data-ttu-id="8ac2b-120">`ConvertTo-CSV`Командлет преобразует объект в строки CSV.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-120">The `ConvertTo-CSV` cmdlet converts the object to CSV strings.</span></span> <span data-ttu-id="8ac2b-121">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-121">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

### <span data-ttu-id="8ac2b-122">Пример 2. преобразование объекта DateTime в CSV-файл</span><span class="sxs-lookup"><span data-stu-id="8ac2b-122">Example 2: Convert a DateTime object to CSV</span></span>

<span data-ttu-id="8ac2b-123">В этом примере объект **DateTime** преобразуется в строку CSV.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-123">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
$Date = Get-Date
ConvertTo-Csv -InputObject $Date -Delimiter ';' -NoTypeInformation
```

```Output
"DisplayHint";"DateTime";"Date";"Day";"DayOfWeek";"DayOfYear";"Hour";"Kind";"Millisecond";"Minute";"Month";"Second";"Ticks";"TimeOfDay";"Year"
"DateTime";"Friday, January 4, 2019 14:40:51";"1/4/2019 00:00:00";"4";"Friday";"4";"14";"Local";"711";"40";"1";"51";"636822096517114991";"14:40:51.7114991";"2019"
```

<span data-ttu-id="8ac2b-124">`Get-Date`Командлет возвращает объект **DateTime** и сохраняет его в `$Date` переменной.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-124">The `Get-Date` cmdlet gets the **DateTime** object and saves it in the `$Date` variable.</span></span> <span data-ttu-id="8ac2b-125">`ConvertTo-Csv`Командлет преобразует объект **DateTime** в строки.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-125">The `ConvertTo-Csv` cmdlet converts the **DateTime** object to strings.</span></span> <span data-ttu-id="8ac2b-126">Параметр **InputObject** использует объект **DateTime** , хранящийся в `$Date` переменной.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-126">The **InputObject** parameter uses the **DateTime** object stored in the `$Date` variable.</span></span> <span data-ttu-id="8ac2b-127">Параметр- **Разделитель** задает точку с запятой для разделения строковых значений.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-127">The **Delimiter** parameter specifies a semicolon to separate the string values.</span></span> <span data-ttu-id="8ac2b-128">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-128">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

### <span data-ttu-id="8ac2b-129">Пример 3. преобразование журнала событий PowerShell в CSV-файл</span><span class="sxs-lookup"><span data-stu-id="8ac2b-129">Example 3: Convert the PowerShell event log to CSV</span></span>

<span data-ttu-id="8ac2b-130">В этом примере журнал событий Windows для PowerShell преобразуется в последовательность строк CSV.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-130">This example converts the Windows event log for PowerShell to a series of CSV strings.</span></span>

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-WinEvent -LogName 'PowerShellCore/Operational' | ConvertTo-Csv -UseCulture -NoTypeInformation
```

```Output
,
"Message","Id","Version","Qualifiers","Level","Task","Opcode","Keywords","RecordId", ...
"Error Message = System error""4100","1",,"3","106","19","0","31716","PowerShellCore", ...
```

<span data-ttu-id="8ac2b-131">`Get-Culture`Командлет использует вложенные свойства **TextInfo** и **ListSeparator** и отображает текущий разделитель списка по умолчанию для текущего языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-131">The `Get-Culture` cmdlet uses the nested properties **TextInfo** and **ListSeparator** and displays the current culture's default list separator.</span></span> <span data-ttu-id="8ac2b-132">`Get-WinEvent`Командлет получает объекты журнала событий и использует параметр " **/l** " для указания имени файла журнала.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-132">The `Get-WinEvent` cmdlet gets the event log objects and uses the **LogName** parameter to specify the log file name.</span></span> <span data-ttu-id="8ac2b-133">Объекты журнала событий отправляются по конвейеру в `ConvertTo-Csv` командлет.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-133">The event log objects are sent down the pipeline to the `ConvertTo-Csv` cmdlet.</span></span> <span data-ttu-id="8ac2b-134">`ConvertTo-Csv`Командлет преобразует объекты журнала событий в последовательность строк CSV.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-134">The `ConvertTo-Csv` cmdlet converts the event log objects to a series of CSV strings.</span></span> <span data-ttu-id="8ac2b-135">Параметр **UseCulture** использует разделитель списка по умолчанию текущего языка и региональных параметров в качестве разделителя.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-135">The **UseCulture** parameter uses the current culture's default list separator as the delimiter.</span></span> <span data-ttu-id="8ac2b-136">Параметр **NoTypeInformation** удаляет заголовок данных **#TYPE** из выходных данных CSV и не является обязательным в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-136">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

### <span data-ttu-id="8ac2b-137">Пример 4. преобразование в CSV с кавычками вокруг двух столбцов</span><span class="sxs-lookup"><span data-stu-id="8ac2b-137">Example 4: Convert to CSV with quotes around two columns</span></span>

<span data-ttu-id="8ac2b-138">В этом примере объект **DateTime** преобразуется в строку CSV.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-138">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
Get-Date | ConvertTo-Csv -QuoteFields "DateTime","Date"
```

```Output
DisplayHint,"DateTime","Date",Day,DayOfWeek,DayOfYear,Hour,Kind,Millisecond,Minute,Month,Second,Ticks,TimeOfDay,Year
DateTime,"Thursday, August 22, 2019 11:27:34 AM","8/22/2019 12:00:00 AM",22,Thursday,234,11,Local,569,27,8,34,637020700545699784,11:27:34.5699784,2019
```

### <span data-ttu-id="8ac2b-139">Пример 4. преобразование в CSV с кавычками только при необходимости</span><span class="sxs-lookup"><span data-stu-id="8ac2b-139">Example 4: Convert to CSV with quotes only when needed</span></span>

<span data-ttu-id="8ac2b-140">В этом примере объект **DateTime** преобразуется в строку CSV.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-140">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
Get-Date | ConvertTo-Csv -UseQuotes AsNeeded
```

```Output
DisplayHint,DateTime,Date,Day,DayOfWeek,DayOfYear,Hour,Kind,Millisecond,Minute,Month,Second,Ticks,TimeOfDay,Year
DateTime,"Thursday, August 22, 2019 11:31:00 AM",8/22/2019 12:00:00 AM,22,Thursday,234,11,Local,713,31,8,0,637020702607132640,11:31:00.7132640,2019
```

## <span data-ttu-id="8ac2b-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8ac2b-141">PARAMETERS</span></span>

### <span data-ttu-id="8ac2b-142">-Delimiter</span><span class="sxs-lookup"><span data-stu-id="8ac2b-142">-Delimiter</span></span>

<span data-ttu-id="8ac2b-143">Задает разделитель значений свойств в строках CSV.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-143">Specifies the delimiter to separate the property values in CSV strings.</span></span> <span data-ttu-id="8ac2b-144">Значение по умолчанию — запятая ( `,` ).</span><span class="sxs-lookup"><span data-stu-id="8ac2b-144">The default is a comma (`,`).</span></span> <span data-ttu-id="8ac2b-145">Введите символ, например двоеточие ( `:` ).</span><span class="sxs-lookup"><span data-stu-id="8ac2b-145">Enter a character, such as a colon (`:`).</span></span> <span data-ttu-id="8ac2b-146">Чтобы указать точку с запятой ( `;` ), заключите ее в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-146">To specify a semicolon (`;`) enclose it in single quotation marks.</span></span>

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

### <span data-ttu-id="8ac2b-147">-Инклудетипеинформатион</span><span class="sxs-lookup"><span data-stu-id="8ac2b-147">-IncludeTypeInformation</span></span>

<span data-ttu-id="8ac2b-148">При использовании этого параметра первая строка выходных данных содержит **#TYPE** , за которыми следует полное имя типа объекта.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-148">When this parameter is used the first line of the output contains **#TYPE** followed by the fully qualified name of the object type.</span></span> <span data-ttu-id="8ac2b-149">Например, **#TYPE System. Diagnostics. Process**.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-149">For example, **#TYPE System.Diagnostics.Process**.</span></span>

<span data-ttu-id="8ac2b-150">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-150">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="8ac2b-151">-InputObject</span><span class="sxs-lookup"><span data-stu-id="8ac2b-151">-InputObject</span></span>

<span data-ttu-id="8ac2b-152">Указывает объекты, которые преобразуются в строки CSV.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-152">Specifies the objects that are converted to CSV strings.</span></span> <span data-ttu-id="8ac2b-153">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-153">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="8ac2b-154">Также можно передать объекты в `ConvertTo-CSV` .</span><span class="sxs-lookup"><span data-stu-id="8ac2b-154">You can also pipe objects to `ConvertTo-CSV`.</span></span>

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

### <span data-ttu-id="8ac2b-155">-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="8ac2b-155">-NoTypeInformation</span></span>

<span data-ttu-id="8ac2b-156">Удаляет заголовок сведений о **#TYPE** из выходных данных.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-156">Removes the **#TYPE** information header from the output.</span></span> <span data-ttu-id="8ac2b-157">Этот параметр стал значением по умолчанию в PowerShell 6,0 и включен для обеспечения обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-157">This parameter became the default in PowerShell 6.0 and is included for backwards compatibility.</span></span>

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

### <span data-ttu-id="8ac2b-158">-UseCulture</span><span class="sxs-lookup"><span data-stu-id="8ac2b-158">-UseCulture</span></span>

<span data-ttu-id="8ac2b-159">Использует разделитель списка для текущего языка и региональных параметров в качестве разделителя элементов.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-159">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="8ac2b-160">Чтобы найти разделитель списка для языка и региональных параметров, используйте следующую команду: `(Get-Culture).TextInfo.ListSeparator` .</span><span class="sxs-lookup"><span data-stu-id="8ac2b-160">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

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

### <span data-ttu-id="8ac2b-161">-Куотефиелдс</span><span class="sxs-lookup"><span data-stu-id="8ac2b-161">-QuoteFields</span></span>

<span data-ttu-id="8ac2b-162">Задает имена столбцов, которые должны быть заключены в кавычки.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-162">Specifies the names of the columns that should be quoted.</span></span> <span data-ttu-id="8ac2b-163">При использовании этого параметра только указанные столбцы заключаются в кавычки.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-163">When this parameter is used only the specified columns are quoted.</span></span> <span data-ttu-id="8ac2b-164">Этот параметр был добавлен в PowerShell 7,0.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-164">This parameter was added in PowerShell 7.0.</span></span>

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

### <span data-ttu-id="8ac2b-165">-Усекуотес</span><span class="sxs-lookup"><span data-stu-id="8ac2b-165">-UseQuotes</span></span>

<span data-ttu-id="8ac2b-166">Указывает, когда в CSV-файлах используются кавычки.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-166">Specifies when quotes are used in the CSV files.</span></span> <span data-ttu-id="8ac2b-167">Доступны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="8ac2b-167">Possible values are:</span></span>

- <span data-ttu-id="8ac2b-168">Никогда — не заключать никаких кавычек</span><span class="sxs-lookup"><span data-stu-id="8ac2b-168">Never - don't quote anything</span></span>
- <span data-ttu-id="8ac2b-169">Всегда-цитировать все (поведение по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8ac2b-169">Always - quote everything (default behavior)</span></span>
- <span data-ttu-id="8ac2b-170">AsNeeded — поля кавычек, содержащие символ-разделитель</span><span class="sxs-lookup"><span data-stu-id="8ac2b-170">AsNeeded - only quote fields that contain a delimiter character</span></span>

<span data-ttu-id="8ac2b-171">Этот параметр был добавлен в PowerShell 7,0.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-171">This parameter was added in PowerShell 7.0.</span></span>

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

### <span data-ttu-id="8ac2b-172">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="8ac2b-172">CommonParameters</span></span>

<span data-ttu-id="8ac2b-173">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-173">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8ac2b-174">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8ac2b-174">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8ac2b-175">Входные данные</span><span class="sxs-lookup"><span data-stu-id="8ac2b-175">INPUTS</span></span>

### <span data-ttu-id="8ac2b-176">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="8ac2b-176">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="8ac2b-177">Любой объект, имеющий адаптер расширенной системы типов (ETS), можно передать в `ConvertTo-CSV` .</span><span class="sxs-lookup"><span data-stu-id="8ac2b-177">You can pipe any object that has an Extended Type System (ETS) adapter to `ConvertTo-CSV`.</span></span>

## <span data-ttu-id="8ac2b-178">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="8ac2b-178">OUTPUTS</span></span>

### <span data-ttu-id="8ac2b-179">System.String</span><span class="sxs-lookup"><span data-stu-id="8ac2b-179">System.String</span></span>

<span data-ttu-id="8ac2b-180">Выходные данные в формате CSV возвращаются в виде коллекции строк.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-180">The CSV output is returned as a collection of strings.</span></span>

## <span data-ttu-id="8ac2b-181">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="8ac2b-181">NOTES</span></span>

<span data-ttu-id="8ac2b-182">В формате CSV каждый объект представлен как разделенный запятыми список значений свойств.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-182">In CSV format, each object is represented by a comma-separated list of its property value.</span></span> <span data-ttu-id="8ac2b-183">Значения свойств преобразуются в строки с помощью метода **ToString ()** объекта.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-183">The property values are converted to strings using the object's **ToString()** method.</span></span> <span data-ttu-id="8ac2b-184">Строки представлены именем значения свойства.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-184">The strings are represented by the property value name.</span></span> <span data-ttu-id="8ac2b-185">`ConvertTo-CSV` не экспортирует методы объекта.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-185">`ConvertTo-CSV` does not export the object's methods.</span></span>

<span data-ttu-id="8ac2b-186">Строки CSV выводятся следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8ac2b-186">The CSV strings are output as follows:</span></span>

- <span data-ttu-id="8ac2b-187">Если используется **инклудетипеинформатион** , первая строка состоит из **#TYPE** , за которой следует полное имя типа объекта.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-187">If **IncludeTypeInformation** is used, the first string consists of **#TYPE** followed by the object type's fully qualified name.</span></span> <span data-ttu-id="8ac2b-188">Например, **#TYPE System. Diagnostics. Process**.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-188">For example, **#TYPE System.Diagnostics.Process**.</span></span>
- <span data-ttu-id="8ac2b-189">Если **инклудетипеинформатион** не используется, первая строка включает заголовки столбцов.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-189">If **IncludeTypeInformation** is not used the first string includes the column headers.</span></span> <span data-ttu-id="8ac2b-190">Заголовки содержат имена свойств первого объекта в виде списка с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-190">The headers contain the first object's property names as a comma-separated list.</span></span>
- <span data-ttu-id="8ac2b-191">Остальные строки содержат разделенные запятыми списки значений свойств каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-191">The remaining strings contain comma-separated lists of each object's property values.</span></span>

<span data-ttu-id="8ac2b-192">Начиная с PowerShell 6,0 поведение по умолчанию `ConvertTo-CSV` — не включать сведения о **#TYPE** в CSV-файл, а **NoTypeInformation** является подразумеваемым.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-192">Beginning with PowerShell 6.0 the default behavior of `ConvertTo-CSV` is to not include the **#TYPE** information in the CSV and **NoTypeInformation** is implied.</span></span> <span data-ttu-id="8ac2b-193">**Инклудетипеинформатион** можно использовать для включения сведений о **#TYPE** и эмуляции поведения по умолчанию `ConvertTo-CSV` до PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-193">**IncludeTypeInformation** can be used to include the **#TYPE** information and emulate the default behavior of `ConvertTo-CSV` prior to PowerShell 6.0.</span></span>

<span data-ttu-id="8ac2b-194">При отправке нескольких объектов в `ConvertTo-CSV` `ConvertTo-CSV` упорядочивает строки на основе свойств первого отправленного объекта.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-194">When you submit multiple objects to `ConvertTo-CSV`, `ConvertTo-CSV` orders the strings based on the properties of the first object that you submit.</span></span> <span data-ttu-id="8ac2b-195">Если остальные объекты не имеют одного из указанных свойств, значение свойства этого объекта равно null, как представлено двумя последовательными запятыми.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-195">If the remaining objects do not have one of the specified properties, the property value of that object is Null, as represented by two consecutive commas.</span></span> <span data-ttu-id="8ac2b-196">Если у остальных объектов есть дополнительные свойства, их значения игнорируются.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-196">If the remaining objects have additional properties, those property values are ignored.</span></span>

## <span data-ttu-id="8ac2b-197">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="8ac2b-197">RELATED LINKS</span></span>

[<span data-ttu-id="8ac2b-198">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="8ac2b-198">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="8ac2b-199">Export-CSV</span><span class="sxs-lookup"><span data-stu-id="8ac2b-199">Export-Csv</span></span>](Export-Csv.md)

[<span data-ttu-id="8ac2b-200">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="8ac2b-200">Import-Csv</span></span>](Import-Csv.md)
