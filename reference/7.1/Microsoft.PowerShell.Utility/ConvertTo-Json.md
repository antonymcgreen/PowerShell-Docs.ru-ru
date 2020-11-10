---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-json?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Json
ms.openlocfilehash: acfeae4025b3a32d2a04307609597cf30332d708
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94389459"
---
# <span data-ttu-id="29379-103">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="29379-103">ConvertTo-Json</span></span>

## <span data-ttu-id="29379-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="29379-104">SYNOPSIS</span></span>
<span data-ttu-id="29379-105">Преобразует объект в строку в формате JSON.</span><span class="sxs-lookup"><span data-stu-id="29379-105">Converts an object to a JSON-formatted string.</span></span>

## <span data-ttu-id="29379-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="29379-106">SYNTAX</span></span>

```
ConvertTo-Json [-InputObject] <Object> [-Depth <Int32>] [-Compress]
[-EnumsAsStrings] [-AsArray] [-EscapeHandling <StringEscapeHandling>]
[<CommonParameters>]
```

## <span data-ttu-id="29379-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="29379-107">DESCRIPTION</span></span>

<span data-ttu-id="29379-108">`ConvertTo-Json`Командлет преобразует любой объект .NET в строку в формате нотация объектов JavaScript (JSON).</span><span class="sxs-lookup"><span data-stu-id="29379-108">The `ConvertTo-Json` cmdlet converts any .NET object to a string in JavaScript Object Notation (JSON) format.</span></span> <span data-ttu-id="29379-109">Свойства преобразуются в имена полей, значения полей преобразуются в значения свойств, а методы удаляются.</span><span class="sxs-lookup"><span data-stu-id="29379-109">The properties are converted to field names, the field values are converted to property values, and the methods are removed.</span></span>

<span data-ttu-id="29379-110">Затем можно использовать `ConvertFrom-Json` командлет для преобразования строки в формате JSON в объект JSON, который легко управляется в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29379-110">You can then use the `ConvertFrom-Json` cmdlet to convert a JSON-formatted string to a JSON object, which is easily managed in PowerShell.</span></span>

<span data-ttu-id="29379-111">Многие веб-сайты используют нотацию JSON вместо XML для сериализации данных для взаимодействия между серверами и веб-приложениями.</span><span class="sxs-lookup"><span data-stu-id="29379-111">Many web sites use JSON instead of XML to serialize data for communication between servers and web-based apps.</span></span>

<span data-ttu-id="29379-112">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="29379-112">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="29379-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="29379-113">EXAMPLES</span></span>

### <span data-ttu-id="29379-114">Пример 1</span><span class="sxs-lookup"><span data-stu-id="29379-114">Example 1</span></span>

```powershell
(Get-UICulture).Calendar | ConvertTo-Json
```

```Output
{
  "MinSupportedDateTime": "0001-01-01T00:00:00",
  "MaxSupportedDateTime": "9999-12-31T23:59:59.9999999",
  "AlgorithmType": 1,
  "CalendarType": 1,
  "Eras": [
    1
  ],
  "TwoDigitYearMax": 2029,
  "IsReadOnly": true
}
```

<span data-ttu-id="29379-115">Эта команда использует `ConvertTo-Json` командлет для преобразования объекта GregorianCalendar в строку в формате JSON.</span><span class="sxs-lookup"><span data-stu-id="29379-115">This command uses the `ConvertTo-Json` cmdlet to convert a GregorianCalendar object to a JSON-formatted string.</span></span>

### <span data-ttu-id="29379-116">Пример 2</span><span class="sxs-lookup"><span data-stu-id="29379-116">Example 2</span></span>

```powershell
Get-Date | ConvertTo-Json; Get-Date | ConvertTo-Json -AsArray
```

```Output
{
  "value": "2018-10-12T23:07:18.8450248-05:00",
  "DisplayHint": 2,
  "DateTime": "October 12, 2018 11:07:18 PM"
}
[
  {
    "value": "2018-10-12T23:07:18.8480668-05:00",
    "DisplayHint": 2,
    "DateTime": "October 12, 2018 11:07:18 PM"
  }
]
```

<span data-ttu-id="29379-117">В этом примере показаны выходные данные `ConvertTo-Json` командлета с параметром **асаррай** и без него.</span><span class="sxs-lookup"><span data-stu-id="29379-117">This example shows the output from `ConvertTo-Json` cmdlet with and without the **AsArray** switch parameter.</span></span> <span data-ttu-id="29379-118">Можно увидеть, что вторая часть выходных данных заключена в скобки массива.</span><span class="sxs-lookup"><span data-stu-id="29379-118">You can see the second portion of the output is wrapped in array brackets.</span></span>

### <span data-ttu-id="29379-119">Пример 3</span><span class="sxs-lookup"><span data-stu-id="29379-119">Example 3</span></span>

```powershell
@{Account="User01";Domain="Domain01";Admin="True"} | ConvertTo-Json -Compress
```

```Output
{"Domain":"Domain01","Account":"User01","Admin":"True"}
```

<span data-ttu-id="29379-120">Эта команда показывает результат применения параметра **сжатия** `ConvertTo-Json` .</span><span class="sxs-lookup"><span data-stu-id="29379-120">This command shows the effect of using the **Compress** parameter of `ConvertTo-Json`.</span></span> <span data-ttu-id="29379-121">Сжатие влияет только на внешний вид строки, но не на ее действительность.</span><span class="sxs-lookup"><span data-stu-id="29379-121">The compression affects only the appearance of the string, not its validity.</span></span>

### <span data-ttu-id="29379-122">Пример 4</span><span class="sxs-lookup"><span data-stu-id="29379-122">Example 4</span></span>

```powershell
Get-Date | Select-Object -Property * | ConvertTo-Json
```

```Output
{
  "DisplayHint": 2,
  "DateTime": "October 12, 2018 10:55:32 PM",
  "Date": "2018-10-12T00:00:00-05:00",
  "Day": 12,
  "DayOfWeek": 5,
  "DayOfYear": 285,
  "Hour": 22,
  "Kind": 2,
  "Millisecond": 639,
  "Minute": 55,
  "Month": 10,
  "Second": 32,
  "Ticks": 636749817326397744,
  "TimeOfDay": {
    "Ticks": 825326397744,
    "Days": 0,
    "Hours": 22,
    "Milliseconds": 639,
    "Minutes": 55,
    "Seconds": 32,
    "TotalDays": 0.95523888627777775,
    "TotalHours": 22.925733270666665,
    "TotalMilliseconds": 82532639.774400011,
    "TotalMinutes": 1375.54399624,
    "TotalSeconds": 82532.6397744
  },
  "Year": 2018
}
```

<span data-ttu-id="29379-123">В этом примере `ConvertTo-Json` командлет используется для преобразования объекта **System. DateTime** из `Get-Date` командлета в строку в формате JSON.</span><span class="sxs-lookup"><span data-stu-id="29379-123">This example uses the `ConvertTo-Json` cmdlet to convert a **System.DateTime** object from the `Get-Date` cmdlet to a JSON-formatted string.</span></span> <span data-ttu-id="29379-124">Команда использует `Select-Object` командлет для получения всех ( `*` ) свойств объекта **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="29379-124">The command uses the `Select-Object` cmdlet to get all (`*`) of the properties of the **DateTime** object.</span></span> <span data-ttu-id="29379-125">В выходных данных отображается строка JSON, которая `ConvertTo-Json` возвращает.</span><span class="sxs-lookup"><span data-stu-id="29379-125">The output shows the JSON string that `ConvertTo-Json` returned.</span></span>

### <span data-ttu-id="29379-126">Пример 5</span><span class="sxs-lookup"><span data-stu-id="29379-126">Example 5</span></span>

```powershell
Get-Date | Select-Object -Property * | ConvertTo-Json | ConvertFrom-Json
```

```Output
DisplayHint : 2
DateTime    : October 12, 2018 10:55:52 PM
Date        : 2018-10-12 12:00:00 AM
Day         : 12
DayOfWeek   : 5
DayOfYear   : 285
Hour        : 22
Kind        : 2
Millisecond : 768
Minute      : 55
Month       : 10
Second      : 52
Ticks       : 636749817527683372
TimeOfDay   : @{Ticks=825527683372; Days=0; Hours=22; Milliseconds=768; Minutes=55; Seconds=52;
              TotalDays=0.95547185575463; TotalHours=22.9313245381111; TotalMilliseconds=82552768.3372;
              TotalMinutes=1375.87947228667; TotalSeconds=82552.7683372}
Year        : 2018
```

<span data-ttu-id="29379-127">В этом примере показано, как использовать `ConvertTo-Json` `ConvertFrom-Json` командлеты и для преобразования объекта в строку JSON и объект JSON.</span><span class="sxs-lookup"><span data-stu-id="29379-127">This example shows how to use the `ConvertTo-Json` and `ConvertFrom-Json` cmdlets to convert an object to a JSON string and a JSON object.</span></span>

## <span data-ttu-id="29379-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="29379-128">PARAMETERS</span></span>

### <span data-ttu-id="29379-129">-Асаррай</span><span class="sxs-lookup"><span data-stu-id="29379-129">-AsArray</span></span>

<span data-ttu-id="29379-130">Выводит объект в скобках массива, даже если входные данные являются одним объектом.</span><span class="sxs-lookup"><span data-stu-id="29379-130">Outputs the object in array brackets, even if the input is a single object.</span></span>

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

### <span data-ttu-id="29379-131">-Сжимать</span><span class="sxs-lookup"><span data-stu-id="29379-131">-Compress</span></span>

<span data-ttu-id="29379-132">Исключает пробелы и отступы в выходной строке.</span><span class="sxs-lookup"><span data-stu-id="29379-132">Omits white space and indented formatting in the output string.</span></span>

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

### <span data-ttu-id="29379-133">-Depth</span><span class="sxs-lookup"><span data-stu-id="29379-133">-Depth</span></span>

<span data-ttu-id="29379-134">Указывает, сколько уровней вложенных объектов включается в JSON-представление.</span><span class="sxs-lookup"><span data-stu-id="29379-134">Specifies how many levels of contained objects are included in the JSON representation.</span></span> <span data-ttu-id="29379-135">Значение по умолчанию — 2.</span><span class="sxs-lookup"><span data-stu-id="29379-135">The default value is 2.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 2
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="29379-136">-Енумсасстрингс</span><span class="sxs-lookup"><span data-stu-id="29379-136">-EnumsAsStrings</span></span>

<span data-ttu-id="29379-137">Предоставляет альтернативный параметр сериализации, который преобразует все перечисления в их строковое представление.</span><span class="sxs-lookup"><span data-stu-id="29379-137">Provides an alternative serialization option that converts all enumerations to their string representation.</span></span>

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

### <span data-ttu-id="29379-138">-Ескапехандлинг</span><span class="sxs-lookup"><span data-stu-id="29379-138">-EscapeHandling</span></span>

<span data-ttu-id="29379-139">Определяет, как определенные символы экранированы в результирующем выходных данных JSON.</span><span class="sxs-lookup"><span data-stu-id="29379-139">Controls how certain characters are escaped in the resulting JSON output.</span></span> <span data-ttu-id="29379-140">По умолчанию escape-последовательности обрабатываются только управляющие символы (например, символ новой строки).</span><span class="sxs-lookup"><span data-stu-id="29379-140">By default, only control characters (like newline) are escaped.</span></span>

<span data-ttu-id="29379-141">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="29379-141">Acceptable values are:</span></span>

- <span data-ttu-id="29379-142">Управляющие символы по умолчанию преобразуются в escape-последовательность.</span><span class="sxs-lookup"><span data-stu-id="29379-142">Default - Only control characters are escaped.</span></span>
- <span data-ttu-id="29379-143">ЕскапенонасЦии — все символы, отличные от ASCII, и управляющие знаки преобразуются в escape-последовательность.</span><span class="sxs-lookup"><span data-stu-id="29379-143">EscapeNonAscii - All non-ASCII and control characters are escaped.</span></span>
- <span data-ttu-id="29379-144">Ескапехтмл-HTML ( `<` , `>` , `&` , `'` , `"` ) и управляющие символы экранированы.</span><span class="sxs-lookup"><span data-stu-id="29379-144">EscapeHtml - HTML (`<`, `>`, `&`, `'`, `"`) and control characters are escaped.</span></span>

<span data-ttu-id="29379-145">Этот параметр появился в PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="29379-145">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: Newtonsoft.Json.StringEscapeHandling
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="29379-146">-InputObject</span><span class="sxs-lookup"><span data-stu-id="29379-146">-InputObject</span></span>

<span data-ttu-id="29379-147">Задает объекты для преобразования в формат JSON.</span><span class="sxs-lookup"><span data-stu-id="29379-147">Specifies the objects to convert to JSON format.</span></span> <span data-ttu-id="29379-148">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="29379-148">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="29379-149">Также можно передать объект в `ConvertTo-Json` .</span><span class="sxs-lookup"><span data-stu-id="29379-149">You can also pipe an object to `ConvertTo-Json`.</span></span>

<span data-ttu-id="29379-150">Параметр **InputObject** является обязательным, но его значение может быть равно null ( `$null` ) или пустой строке.</span><span class="sxs-lookup"><span data-stu-id="29379-150">The **InputObject** parameter is required, but its value can be null (`$null`) or an empty string.</span></span>
<span data-ttu-id="29379-151">Если входной объект имеет значение `$null` , не `ConvertTo-Json` создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="29379-151">When the input object is `$null`, `ConvertTo-Json` does not generate any output.</span></span> <span data-ttu-id="29379-152">Если входной объект является пустой строкой, `ConvertTo-Json` возвращает пустую строку.</span><span class="sxs-lookup"><span data-stu-id="29379-152">When the input object is an empty string, `ConvertTo-Json` returns an empty string.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="29379-153">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="29379-153">CommonParameters</span></span>

<span data-ttu-id="29379-154">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="29379-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="29379-155">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="29379-155">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="29379-156">Входные данные</span><span class="sxs-lookup"><span data-stu-id="29379-156">INPUTS</span></span>

### <span data-ttu-id="29379-157">System.Object</span><span class="sxs-lookup"><span data-stu-id="29379-157">System.Object</span></span>

<span data-ttu-id="29379-158">Любой объект можно передать по конвейеру в `ConvertTo-Json` .</span><span class="sxs-lookup"><span data-stu-id="29379-158">You can pipe any object to `ConvertTo-Json`.</span></span>

## <span data-ttu-id="29379-159">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="29379-159">OUTPUTS</span></span>

### <span data-ttu-id="29379-160">System.String</span><span class="sxs-lookup"><span data-stu-id="29379-160">System.String</span></span>

## <span data-ttu-id="29379-161">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="29379-161">NOTES</span></span>

<span data-ttu-id="29379-162">`ConvertTo-Json`Командлет реализуется с помощью [Newtonsoft JSON.NET](https://www.newtonsoft.com/json).</span><span class="sxs-lookup"><span data-stu-id="29379-162">The `ConvertTo-Json` cmdlet is implemented using [Newtonsoft Json.NET](https://www.newtonsoft.com/json).</span></span>

## <span data-ttu-id="29379-163">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="29379-163">RELATED LINKS</span></span>

<span data-ttu-id="29379-164">[Введение в нотация объектов JavaScript (JSON) в JavaScript и .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="29379-164">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="29379-165">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="29379-165">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="29379-166">Get-Content</span><span class="sxs-lookup"><span data-stu-id="29379-166">Get-Content</span></span>](../Microsoft.PowerShell.Management/Get-Content.md)

[<span data-ttu-id="29379-167">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="29379-167">Get-UICulture</span></span>](Get-UICulture.md)

[<span data-ttu-id="29379-168">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="29379-168">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="29379-169">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="29379-169">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)

[<span data-ttu-id="29379-170">NewtonSoft.Js. стринжескапехандлинг</span><span class="sxs-lookup"><span data-stu-id="29379-170">NewtonSoft.Json.StringEscapeHandling</span></span>](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm)
