---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-json?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Json
ms.openlocfilehash: 9831249a9f1ffcc65fc275e44da04fde9348ae71
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388065"
---
# <span data-ttu-id="6ce78-103">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="6ce78-103">ConvertTo-Json</span></span>

## <span data-ttu-id="6ce78-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="6ce78-104">SYNOPSIS</span></span>
<span data-ttu-id="6ce78-105">Преобразует объект в строку в формате JSON.</span><span class="sxs-lookup"><span data-stu-id="6ce78-105">Converts an object to a JSON-formatted string.</span></span>

## <span data-ttu-id="6ce78-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6ce78-106">SYNTAX</span></span>

```
ConvertTo-Json [-InputObject] <Object> [-Depth <Int32>] [-Compress]
 [<CommonParameters>]
```

## <span data-ttu-id="6ce78-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6ce78-107">DESCRIPTION</span></span>

<span data-ttu-id="6ce78-108">`ConvertTo-Json`Командлет преобразует любой объект .NET в строку в формате нотация объектов JavaScript (JSON).</span><span class="sxs-lookup"><span data-stu-id="6ce78-108">The `ConvertTo-Json` cmdlet converts any .NET object to a string in JavaScript Object Notation (JSON) format.</span></span> <span data-ttu-id="6ce78-109">Свойства преобразуются в имена полей, значения полей преобразуются в значения свойств, а методы удаляются.</span><span class="sxs-lookup"><span data-stu-id="6ce78-109">The properties are converted to field names, the field values are converted to property values, and the methods are removed.</span></span>

<span data-ttu-id="6ce78-110">Затем можно использовать `ConvertFrom-Json` командлет для преобразования строки в формате JSON в объект JSON, который легко управляется в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ce78-110">You can then use the `ConvertFrom-Json` cmdlet to convert a JSON-formatted string to a JSON object, which is easily managed in PowerShell.</span></span>

<span data-ttu-id="6ce78-111">Многие веб-сайты используют нотацию JSON вместо XML для сериализации данных для взаимодействия между серверами и веб-приложениями.</span><span class="sxs-lookup"><span data-stu-id="6ce78-111">Many web sites use JSON instead of XML to serialize data for communication between servers and web-based apps.</span></span>

<span data-ttu-id="6ce78-112">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="6ce78-112">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="6ce78-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="6ce78-113">EXAMPLES</span></span>

### <span data-ttu-id="6ce78-114">Пример 1</span><span class="sxs-lookup"><span data-stu-id="6ce78-114">Example 1</span></span>

```powershell
(Get-UICulture).Calendar | ConvertTo-Json
```

```Output
{
    "MinSupportedDateTime":  "\/Date(-62135596800000)\/",
    "MaxSupportedDateTime":  "\/Date(253402300799999)\/",
    "AlgorithmType":  1,
    "CalendarType":  1,
    "Eras":  [
                 1
             ],
    "TwoDigitYearMax":  2029,
    "IsReadOnly":  false
}
```

<span data-ttu-id="6ce78-115">Эта команда использует `ConvertTo-Json` командлет для преобразования объекта GregorianCalendar в строку в формате JSON.</span><span class="sxs-lookup"><span data-stu-id="6ce78-115">This command uses the `ConvertTo-Json` cmdlet to convert a GregorianCalendar object to a JSON-formatted string.</span></span>

### <span data-ttu-id="6ce78-116">Пример 2</span><span class="sxs-lookup"><span data-stu-id="6ce78-116">Example 2</span></span>

```powershell
@{Account="User01";Domain="Domain01";Admin="True"} | ConvertTo-Json -Compress
```

```Output
{"Domain":"Domain01","Account":"User01","Admin":"True"}
```

<span data-ttu-id="6ce78-117">Эта команда показывает результат применения параметра **сжатия** `ConvertTo-Json` .</span><span class="sxs-lookup"><span data-stu-id="6ce78-117">This command shows the effect of using the **Compress** parameter of `ConvertTo-Json`.</span></span> <span data-ttu-id="6ce78-118">Сжатие влияет только на внешний вид строки, но не на ее действительность.</span><span class="sxs-lookup"><span data-stu-id="6ce78-118">The compression affects only the appearance of the string, not its validity.</span></span>

### <span data-ttu-id="6ce78-119">Пример 3</span><span class="sxs-lookup"><span data-stu-id="6ce78-119">Example 3</span></span>

```powershell
Get-Date | Select-Object -Property * | ConvertTo-Json
```

```Output
{
    "DisplayHint":  2,
    "DateTime":  "Friday, January 13, 2012 8:06:16 PM",
    "Date":  "\/Date(1326441600000)\/",
    "Day":  13,
    "DayOfWeek":  5,
    "DayOfYear":  13,
    "Hour":  20,
    "Kind":  2,
    "Millisecond":  221,
    "Minute":  6,
    "Month":  1,
    "Second":  16,
    "Ticks":  634620819762218083,
    "TimeOfDay":  {
                      "Ticks":  723762218083,
                      "Days":  0,
                      "Hours":  20,
                      "Milliseconds":  221,
                      "Minutes":  6,
                      "Seconds":  16,
                      "TotalDays":  0.83768775241087956,
                      "TotalHours":  20.104506057861109,
                      "TotalMilliseconds":  72376221.8083,
                      "TotalMinutes":  1206.2703634716668,
                      "TotalSeconds":  72376.22180829999
                  },
    "Year":  2012
}
```

<span data-ttu-id="6ce78-120">В этом примере `ConvertTo-Json` командлет используется для преобразования объекта **System. DateTime** из `Get-Date` командлета в строку в формате JSON.</span><span class="sxs-lookup"><span data-stu-id="6ce78-120">This example uses the `ConvertTo-Json` cmdlet to convert a **System.DateTime** object from the `Get-Date` cmdlet to a JSON-formatted string.</span></span> <span data-ttu-id="6ce78-121">Команда использует `Select-Object` командлет для получения всех ( `*` ) свойств объекта **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="6ce78-121">The command uses the `Select-Object` cmdlet to get all (`*`) of the properties of the **DateTime** object.</span></span> <span data-ttu-id="6ce78-122">В выходных данных отображается строка JSON, которая `ConvertTo-Json` возвращает.</span><span class="sxs-lookup"><span data-stu-id="6ce78-122">The output shows the JSON string that `ConvertTo-Json` returned.</span></span>

### <span data-ttu-id="6ce78-123">Пример 4</span><span class="sxs-lookup"><span data-stu-id="6ce78-123">Example 4</span></span>

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

<span data-ttu-id="6ce78-124">В этом примере показано, как использовать `ConvertTo-Json` `ConvertFrom-Json` командлеты и для преобразования объекта в строку JSON и объект JSON.</span><span class="sxs-lookup"><span data-stu-id="6ce78-124">This example shows how to use the `ConvertTo-Json` and `ConvertFrom-Json` cmdlets to convert an object to a JSON string and a JSON object.</span></span>

## <span data-ttu-id="6ce78-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6ce78-125">PARAMETERS</span></span>

### <span data-ttu-id="6ce78-126">-Сжимать</span><span class="sxs-lookup"><span data-stu-id="6ce78-126">-Compress</span></span>

<span data-ttu-id="6ce78-127">Исключает пробелы и отступы в выходной строке.</span><span class="sxs-lookup"><span data-stu-id="6ce78-127">Omits white space and indented formatting in the output string.</span></span>

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

### <span data-ttu-id="6ce78-128">-Depth</span><span class="sxs-lookup"><span data-stu-id="6ce78-128">-Depth</span></span>

<span data-ttu-id="6ce78-129">Указывает, сколько уровней вложенных объектов включается в JSON-представление.</span><span class="sxs-lookup"><span data-stu-id="6ce78-129">Specifies how many levels of contained objects are included in the JSON representation.</span></span> <span data-ttu-id="6ce78-130">Значение по умолчанию — 2.</span><span class="sxs-lookup"><span data-stu-id="6ce78-130">The default value is 2.</span></span>

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

### <span data-ttu-id="6ce78-131">-InputObject</span><span class="sxs-lookup"><span data-stu-id="6ce78-131">-InputObject</span></span>

<span data-ttu-id="6ce78-132">Задает объекты для преобразования в формат JSON.</span><span class="sxs-lookup"><span data-stu-id="6ce78-132">Specifies the objects to convert to JSON format.</span></span> <span data-ttu-id="6ce78-133">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="6ce78-133">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="6ce78-134">Также можно передать объект в `ConvertTo-Json` .</span><span class="sxs-lookup"><span data-stu-id="6ce78-134">You can also pipe an object to `ConvertTo-Json`.</span></span>

<span data-ttu-id="6ce78-135">Параметр **InputObject** является обязательным, но его значение может быть равно null ( `$null` ) или пустой строке.</span><span class="sxs-lookup"><span data-stu-id="6ce78-135">The **InputObject** parameter is required, but its value can be null (`$null`) or an empty string.</span></span>
<span data-ttu-id="6ce78-136">Если входной объект имеет значение `$null` , не `ConvertTo-Json` создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="6ce78-136">When the input object is `$null`, `ConvertTo-Json` does not generate any output.</span></span> <span data-ttu-id="6ce78-137">Если входной объект является пустой строкой, `ConvertTo-Json` возвращает пустую строку.</span><span class="sxs-lookup"><span data-stu-id="6ce78-137">When the input object is an empty string, `ConvertTo-Json` returns an empty string.</span></span>

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

### <span data-ttu-id="6ce78-138">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="6ce78-138">CommonParameters</span></span>

<span data-ttu-id="6ce78-139">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6ce78-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6ce78-140">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="6ce78-140">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="6ce78-141">Входные данные</span><span class="sxs-lookup"><span data-stu-id="6ce78-141">INPUTS</span></span>

### <span data-ttu-id="6ce78-142">System.Object</span><span class="sxs-lookup"><span data-stu-id="6ce78-142">System.Object</span></span>

<span data-ttu-id="6ce78-143">Любой объект можно передать по конвейеру в `ConvertTo-Json` .</span><span class="sxs-lookup"><span data-stu-id="6ce78-143">You can pipe any object to `ConvertTo-Json`.</span></span>

## <span data-ttu-id="6ce78-144">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="6ce78-144">OUTPUTS</span></span>

### <span data-ttu-id="6ce78-145">System.String</span><span class="sxs-lookup"><span data-stu-id="6ce78-145">System.String</span></span>

## <span data-ttu-id="6ce78-146">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="6ce78-146">NOTES</span></span>

<span data-ttu-id="6ce78-147">`ConvertTo-Json`Командлет реализуется с помощью [класса JavaScriptSerializer](/dotnet/api/system.web.script.serialization.javascriptserializer).</span><span class="sxs-lookup"><span data-stu-id="6ce78-147">The `ConvertTo-Json` cmdlet is implemented using the [JavaScriptSerializer class](/dotnet/api/system.web.script.serialization.javascriptserializer).</span></span>

## <span data-ttu-id="6ce78-148">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="6ce78-148">RELATED LINKS</span></span>

<span data-ttu-id="6ce78-149">[Введение в нотация объектов JavaScript (JSON) в JavaScript и .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="6ce78-149">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="6ce78-150">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="6ce78-150">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="6ce78-151">Get-Content</span><span class="sxs-lookup"><span data-stu-id="6ce78-151">Get-Content</span></span>](../Microsoft.PowerShell.Management/Get-Content.md)

[<span data-ttu-id="6ce78-152">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="6ce78-152">Get-UICulture</span></span>](Get-UICulture.md)

[<span data-ttu-id="6ce78-153">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="6ce78-153">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="6ce78-154">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="6ce78-154">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)
