---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-json?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Json
ms.openlocfilehash: d598fe2b1aefdae046b0f1a0893bf4fc407fa7a7
ms.sourcegitcommit: 11880ca974fe2df308191c9f6dcdfe0b89c2dc67
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/27/2021
ms.locfileid: "99599397"
---
# <span data-ttu-id="00ddf-102">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="00ddf-102">ConvertTo-Json</span></span>

## <span data-ttu-id="00ddf-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="00ddf-103">SYNOPSIS</span></span>
<span data-ttu-id="00ddf-104">Преобразует объект в строку в формате JSON.</span><span class="sxs-lookup"><span data-stu-id="00ddf-104">Converts an object to a JSON-formatted string.</span></span>

## <span data-ttu-id="00ddf-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="00ddf-105">SYNTAX</span></span>

```
ConvertTo-Json [-InputObject] <Object> [-Depth <Int32>] [-Compress]
[-EnumsAsStrings] [-AsArray] [-EscapeHandling <StringEscapeHandling>]
[<CommonParameters>]
```

## <span data-ttu-id="00ddf-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="00ddf-106">DESCRIPTION</span></span>

<span data-ttu-id="00ddf-107">`ConvertTo-Json`Командлет преобразует любой объект .NET в строку в формате нотация объектов JavaScript (JSON).</span><span class="sxs-lookup"><span data-stu-id="00ddf-107">The `ConvertTo-Json` cmdlet converts any .NET object to a string in JavaScript Object Notation (JSON) format.</span></span> <span data-ttu-id="00ddf-108">Свойства преобразуются в имена полей, значения полей преобразуются в значения свойств, а методы удаляются.</span><span class="sxs-lookup"><span data-stu-id="00ddf-108">The properties are converted to field names, the field values are converted to property values, and the methods are removed.</span></span>

<span data-ttu-id="00ddf-109">Затем можно использовать `ConvertFrom-Json` командлет для преобразования строки в формате JSON в объект JSON, который легко управляется в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="00ddf-109">You can then use the `ConvertFrom-Json` cmdlet to convert a JSON-formatted string to a JSON object, which is easily managed in PowerShell.</span></span>

<span data-ttu-id="00ddf-110">Многие веб-сайты используют нотацию JSON вместо XML для сериализации данных для взаимодействия между серверами и веб-приложениями.</span><span class="sxs-lookup"><span data-stu-id="00ddf-110">Many web sites use JSON instead of XML to serialize data for communication between servers and web-based apps.</span></span>

<span data-ttu-id="00ddf-111">Начиная с PowerShell 7,2, `ConvertTo-Json` выдает предупреждение, если глубина входного объекта превышает глубину, указанную для команды.</span><span class="sxs-lookup"><span data-stu-id="00ddf-111">As of PowerShell 7.2, `ConvertTo-Json` emits a warning if the depth of the input object exceeds the depth specified for the command.</span></span> <span data-ttu-id="00ddf-112">Это предотвращает нежелательные потери данных при преобразовании объектов.</span><span class="sxs-lookup"><span data-stu-id="00ddf-112">This prevents unwanted data loss when converting objects.</span></span>

<span data-ttu-id="00ddf-113">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="00ddf-113">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="00ddf-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="00ddf-114">EXAMPLES</span></span>

### <span data-ttu-id="00ddf-115">Пример 1</span><span class="sxs-lookup"><span data-stu-id="00ddf-115">Example 1</span></span>

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

<span data-ttu-id="00ddf-116">Эта команда использует `ConvertTo-Json` командлет для преобразования объекта GregorianCalendar в строку в формате JSON.</span><span class="sxs-lookup"><span data-stu-id="00ddf-116">This command uses the `ConvertTo-Json` cmdlet to convert a GregorianCalendar object to a JSON-formatted string.</span></span>

### <span data-ttu-id="00ddf-117">Пример 2</span><span class="sxs-lookup"><span data-stu-id="00ddf-117">Example 2</span></span>

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

<span data-ttu-id="00ddf-118">В этом примере показаны выходные данные `ConvertTo-Json` командлета с параметром **асаррай** и без него.</span><span class="sxs-lookup"><span data-stu-id="00ddf-118">This example shows the output from `ConvertTo-Json` cmdlet with and without the **AsArray** switch parameter.</span></span> <span data-ttu-id="00ddf-119">Можно увидеть, что вторая часть выходных данных заключена в скобки массива.</span><span class="sxs-lookup"><span data-stu-id="00ddf-119">You can see the second portion of the output is wrapped in array brackets.</span></span>

### <span data-ttu-id="00ddf-120">Пример 3</span><span class="sxs-lookup"><span data-stu-id="00ddf-120">Example 3</span></span>

```powershell
@{Account="User01";Domain="Domain01";Admin="True"} | ConvertTo-Json -Compress
```

```Output
{"Domain":"Domain01","Account":"User01","Admin":"True"}
```

<span data-ttu-id="00ddf-121">Эта команда показывает результат применения параметра **сжатия** `ConvertTo-Json` .</span><span class="sxs-lookup"><span data-stu-id="00ddf-121">This command shows the effect of using the **Compress** parameter of `ConvertTo-Json`.</span></span> <span data-ttu-id="00ddf-122">Сжатие влияет только на внешний вид строки, но не на ее действительность.</span><span class="sxs-lookup"><span data-stu-id="00ddf-122">The compression affects only the appearance of the string, not its validity.</span></span>

### <span data-ttu-id="00ddf-123">Пример 4</span><span class="sxs-lookup"><span data-stu-id="00ddf-123">Example 4</span></span>

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

<span data-ttu-id="00ddf-124">В этом примере `ConvertTo-Json` командлет используется для преобразования объекта **System. DateTime** из `Get-Date` командлета в строку в формате JSON.</span><span class="sxs-lookup"><span data-stu-id="00ddf-124">This example uses the `ConvertTo-Json` cmdlet to convert a **System.DateTime** object from the `Get-Date` cmdlet to a JSON-formatted string.</span></span> <span data-ttu-id="00ddf-125">Команда использует `Select-Object` командлет для получения всех ( `*` ) свойств объекта **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="00ddf-125">The command uses the `Select-Object` cmdlet to get all (`*`) of the properties of the **DateTime** object.</span></span> <span data-ttu-id="00ddf-126">В выходных данных отображается строка JSON, которая `ConvertTo-Json` возвращает.</span><span class="sxs-lookup"><span data-stu-id="00ddf-126">The output shows the JSON string that `ConvertTo-Json` returned.</span></span>

### <span data-ttu-id="00ddf-127">Пример 5</span><span class="sxs-lookup"><span data-stu-id="00ddf-127">Example 5</span></span>

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

<span data-ttu-id="00ddf-128">В этом примере показано, как использовать `ConvertTo-Json` `ConvertFrom-Json` командлеты и для преобразования объекта в строку JSON и объект JSON.</span><span class="sxs-lookup"><span data-stu-id="00ddf-128">This example shows how to use the `ConvertTo-Json` and `ConvertFrom-Json` cmdlets to convert an object to a JSON string and a JSON object.</span></span>

## <span data-ttu-id="00ddf-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="00ddf-129">PARAMETERS</span></span>

### <span data-ttu-id="00ddf-130">-Асаррай</span><span class="sxs-lookup"><span data-stu-id="00ddf-130">-AsArray</span></span>

<span data-ttu-id="00ddf-131">Выводит объект в скобках массива, даже если входные данные являются одним объектом.</span><span class="sxs-lookup"><span data-stu-id="00ddf-131">Outputs the object in array brackets, even if the input is a single object.</span></span>

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

### <span data-ttu-id="00ddf-132">-Сжимать</span><span class="sxs-lookup"><span data-stu-id="00ddf-132">-Compress</span></span>

<span data-ttu-id="00ddf-133">Исключает пробелы и отступы в выходной строке.</span><span class="sxs-lookup"><span data-stu-id="00ddf-133">Omits white space and indented formatting in the output string.</span></span>

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

### <span data-ttu-id="00ddf-134">-Depth</span><span class="sxs-lookup"><span data-stu-id="00ddf-134">-Depth</span></span>

<span data-ttu-id="00ddf-135">Указывает, сколько уровней вложенных объектов включается в JSON-представление.</span><span class="sxs-lookup"><span data-stu-id="00ddf-135">Specifies how many levels of contained objects are included in the JSON representation.</span></span> <span data-ttu-id="00ddf-136">Значение по умолчанию — 2.</span><span class="sxs-lookup"><span data-stu-id="00ddf-136">The default value is 2.</span></span> <span data-ttu-id="00ddf-137">Начиная с PowerShell 7,2, `ConvertTo-Json` выдает предупреждение, если количество уровней во входном объекте превышает это число.</span><span class="sxs-lookup"><span data-stu-id="00ddf-137">As of PowerShell 7.2, `ConvertTo-Json` emits a warning if the number of levels in an input object exceeds this number.</span></span>

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

### <span data-ttu-id="00ddf-138">-Енумсасстрингс</span><span class="sxs-lookup"><span data-stu-id="00ddf-138">-EnumsAsStrings</span></span>

<span data-ttu-id="00ddf-139">Предоставляет альтернативный параметр сериализации, который преобразует все перечисления в их строковое представление.</span><span class="sxs-lookup"><span data-stu-id="00ddf-139">Provides an alternative serialization option that converts all enumerations to their string representation.</span></span>

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

### <span data-ttu-id="00ddf-140">-Ескапехандлинг</span><span class="sxs-lookup"><span data-stu-id="00ddf-140">-EscapeHandling</span></span>

<span data-ttu-id="00ddf-141">Определяет, как определенные символы экранированы в результирующем выходных данных JSON.</span><span class="sxs-lookup"><span data-stu-id="00ddf-141">Controls how certain characters are escaped in the resulting JSON output.</span></span> <span data-ttu-id="00ddf-142">По умолчанию escape-последовательности обрабатываются только управляющие символы (например, символ новой строки).</span><span class="sxs-lookup"><span data-stu-id="00ddf-142">By default, only control characters (like newline) are escaped.</span></span>

<span data-ttu-id="00ddf-143">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="00ddf-143">Acceptable values are:</span></span>

- <span data-ttu-id="00ddf-144">Управляющие символы по умолчанию преобразуются в escape-последовательность.</span><span class="sxs-lookup"><span data-stu-id="00ddf-144">Default - Only control characters are escaped.</span></span>
- <span data-ttu-id="00ddf-145">ЕскапенонасЦии — все символы, отличные от ASCII, и управляющие знаки преобразуются в escape-последовательность.</span><span class="sxs-lookup"><span data-stu-id="00ddf-145">EscapeNonAscii - All non-ASCII and control characters are escaped.</span></span>
- <span data-ttu-id="00ddf-146">Ескапехтмл-HTML ( `<` , `>` , `&` , `'` , `"` ) и управляющие символы экранированы.</span><span class="sxs-lookup"><span data-stu-id="00ddf-146">EscapeHtml - HTML (`<`, `>`, `&`, `'`, `"`) and control characters are escaped.</span></span>

<span data-ttu-id="00ddf-147">Этот параметр появился в PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="00ddf-147">This parameter was introduced in PowerShell 6.2.</span></span>

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

### <span data-ttu-id="00ddf-148">-InputObject</span><span class="sxs-lookup"><span data-stu-id="00ddf-148">-InputObject</span></span>

<span data-ttu-id="00ddf-149">Задает объекты для преобразования в формат JSON.</span><span class="sxs-lookup"><span data-stu-id="00ddf-149">Specifies the objects to convert to JSON format.</span></span> <span data-ttu-id="00ddf-150">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="00ddf-150">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="00ddf-151">Также можно передать объект в `ConvertTo-Json` .</span><span class="sxs-lookup"><span data-stu-id="00ddf-151">You can also pipe an object to `ConvertTo-Json`.</span></span>

<span data-ttu-id="00ddf-152">Параметр **InputObject** является обязательным, но его значение может быть равно null ( `$null` ) или пустой строке.</span><span class="sxs-lookup"><span data-stu-id="00ddf-152">The **InputObject** parameter is required, but its value can be null (`$null`) or an empty string.</span></span>
<span data-ttu-id="00ddf-153">Если входной объект имеет значение `$null` , не `ConvertTo-Json` создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="00ddf-153">When the input object is `$null`, `ConvertTo-Json` does not generate any output.</span></span> <span data-ttu-id="00ddf-154">Если входной объект является пустой строкой, `ConvertTo-Json` возвращает пустую строку.</span><span class="sxs-lookup"><span data-stu-id="00ddf-154">When the input object is an empty string, `ConvertTo-Json` returns an empty string.</span></span>

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

### <span data-ttu-id="00ddf-155">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="00ddf-155">CommonParameters</span></span>

<span data-ttu-id="00ddf-156">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="00ddf-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="00ddf-157">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="00ddf-157">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="00ddf-158">Входные данные</span><span class="sxs-lookup"><span data-stu-id="00ddf-158">INPUTS</span></span>

### <span data-ttu-id="00ddf-159">System.Object</span><span class="sxs-lookup"><span data-stu-id="00ddf-159">System.Object</span></span>

<span data-ttu-id="00ddf-160">Любой объект можно передать по конвейеру в `ConvertTo-Json` .</span><span class="sxs-lookup"><span data-stu-id="00ddf-160">You can pipe any object to `ConvertTo-Json`.</span></span>

## <span data-ttu-id="00ddf-161">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="00ddf-161">OUTPUTS</span></span>

### <span data-ttu-id="00ddf-162">System.String</span><span class="sxs-lookup"><span data-stu-id="00ddf-162">System.String</span></span>

## <span data-ttu-id="00ddf-163">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="00ddf-163">NOTES</span></span>

<span data-ttu-id="00ddf-164">`ConvertTo-Json`Командлет реализуется с помощью [Newtonsoft JSON.NET](https://www.newtonsoft.com/json).</span><span class="sxs-lookup"><span data-stu-id="00ddf-164">The `ConvertTo-Json` cmdlet is implemented using [Newtonsoft Json.NET](https://www.newtonsoft.com/json).</span></span>

## <span data-ttu-id="00ddf-165">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="00ddf-165">RELATED LINKS</span></span>

<span data-ttu-id="00ddf-166">[Введение в нотация объектов JavaScript (JSON) в JavaScript и .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="00ddf-166">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="00ddf-167">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="00ddf-167">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="00ddf-168">Get-Content</span><span class="sxs-lookup"><span data-stu-id="00ddf-168">Get-Content</span></span>](../Microsoft.PowerShell.Management/Get-Content.md)

[<span data-ttu-id="00ddf-169">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="00ddf-169">Get-UICulture</span></span>](Get-UICulture.md)

[<span data-ttu-id="00ddf-170">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="00ddf-170">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="00ddf-171">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="00ddf-171">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)

[<span data-ttu-id="00ddf-172">NewtonSoft.Js. стринжескапехандлинг</span><span class="sxs-lookup"><span data-stu-id="00ddf-172">NewtonSoft.Json.StringEscapeHandling</span></span>](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm)
