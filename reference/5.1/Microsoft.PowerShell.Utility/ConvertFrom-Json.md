---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-json?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Json
ms.openlocfilehash: e1bab9250269dadf0d899f9e172e8a4a8387271d
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388133"
---
# <span data-ttu-id="23557-103">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="23557-103">ConvertFrom-Json</span></span>

## <span data-ttu-id="23557-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="23557-104">SYNOPSIS</span></span>
<span data-ttu-id="23557-105">Преобразует строку в формате JSON в пользовательский объект.</span><span class="sxs-lookup"><span data-stu-id="23557-105">Converts a JSON-formatted string to a custom object.</span></span>

## <span data-ttu-id="23557-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="23557-106">SYNTAX</span></span>

```
ConvertFrom-Json [-InputObject] <String> [<CommonParameters>]
```

## <span data-ttu-id="23557-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="23557-107">DESCRIPTION</span></span>

<span data-ttu-id="23557-108">`ConvertFrom-Json`Командлет преобразует строку в формате нотация объектов JavaScript (JSON) в пользовательский объект **PSCustomObject** , имеющий свойство для каждого поля в строке JSON.</span><span class="sxs-lookup"><span data-stu-id="23557-108">The `ConvertFrom-Json` cmdlet converts a JavaScript Object Notation (JSON) formatted string to a custom **PSCustomObject** object that has a property for each field in the JSON string.</span></span> <span data-ttu-id="23557-109">Формат JSON обычно используется на веб-сайтах для текстового представления объектов.</span><span class="sxs-lookup"><span data-stu-id="23557-109">JSON is commonly used by web sites to provide a textual representation of objects.</span></span> <span data-ttu-id="23557-110">Стандарт JSON не запрещает использование, которое запрещено **PSCustomObject**.</span><span class="sxs-lookup"><span data-stu-id="23557-110">The JSON standard does not prohibit usage that is prohibited with a **PSCustomObject**.</span></span> <span data-ttu-id="23557-111">Например, если строка JSON содержит дублирующиеся ключи, этот командлет использует только последний ключ.</span><span class="sxs-lookup"><span data-stu-id="23557-111">For example, if the JSON string contains duplicate keys, only the last key is used by this cmdlet.</span></span> <span data-ttu-id="23557-112">См. Другие примеры ниже.</span><span class="sxs-lookup"><span data-stu-id="23557-112">See other examples below.</span></span>

<span data-ttu-id="23557-113">Чтобы создать строку JSON из любого объекта, используйте `ConvertTo-Json` командлет.</span><span class="sxs-lookup"><span data-stu-id="23557-113">To generate a JSON string from any object, use the `ConvertTo-Json` cmdlet.</span></span>

<span data-ttu-id="23557-114">Этот командлет появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="23557-114">This cmdlet was introduced in PowerShell 3.0.</span></span>

> [!NOTE]
> <span data-ttu-id="23557-115">Этот командлет не поддерживает JSON с комментариями.</span><span class="sxs-lookup"><span data-stu-id="23557-115">This cmdlet doesn't support JSON with comments.</span></span>

## <span data-ttu-id="23557-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="23557-116">EXAMPLES</span></span>

### <span data-ttu-id="23557-117">Пример 1. преобразование объекта DateTime в объект JSON</span><span class="sxs-lookup"><span data-stu-id="23557-117">Example 1: Convert a DateTime object to a JSON object</span></span>

<span data-ttu-id="23557-118">Эта команда использует `ConvertTo-Json` `ConvertFrom-Json` командлеты и для преобразования объекта **DateTime** из `Get-Date` командлета в объект JSON и затем в **PSCustomObject**.</span><span class="sxs-lookup"><span data-stu-id="23557-118">This command uses the `ConvertTo-Json` and `ConvertFrom-Json` cmdlets to convert a **DateTime** object from the `Get-Date` cmdlet to a JSON object then to a **PSCustomObject**.</span></span>

```powershell
Get-Date | Select-Object -Property * | ConvertTo-Json | ConvertFrom-Json
```

```Output
DisplayHint : 2
DateTime    : Friday, January 13, 2012 8:06:31 PM
Date        : 1/13/2012 8:00:00 AM
Day         : 13
DayOfWeek   : 5
DayOfYear   : 13
Hour        : 20
Kind        : 2
Millisecond : 400
Minute      : 6
Month       : 1
Second      : 31
Ticks       : 634620819914009002
TimeOfDay   : @{Ticks=723914009002; Days=0; Hours=20; Milliseconds=400; Minutes=6; Seconds=31; TotalDays=0.83786343634490734; TotalHours=20.108722472277776; TotalMilliseconds=72391400.900200009; TotalMinutes=1206.5233483366667;TotalSeconds=72391.4009002}
Year        : 2012
```

<span data-ttu-id="23557-119">В примере используется `Select-Object` командлет для получения всех свойств объекта **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="23557-119">The example uses the `Select-Object` cmdlet to get all of the properties of the **DateTime** object.</span></span> <span data-ttu-id="23557-120">Он использует `ConvertTo-Json` командлет для преобразования объекта **DateTime** в строку, отформатированную в виде объекта JSON, и `ConvertFrom-Json` командлет для преобразования строки в формате JSON в объект **PSCustomObject** .</span><span class="sxs-lookup"><span data-stu-id="23557-120">It uses the `ConvertTo-Json` cmdlet to convert the **DateTime** object to a string formatted as a JSON object and the `ConvertFrom-Json` cmdlet to convert the JSON-formatted string to a **PSCustomObject** object.</span></span>

### <span data-ttu-id="23557-121">Пример 2. Получение строк JSON из веб-службы и их преобразование в объекты PowerShell</span><span class="sxs-lookup"><span data-stu-id="23557-121">Example 2: Get JSON strings from a web service and convert them to PowerShell objects</span></span>

<span data-ttu-id="23557-122">Эта команда использует `Invoke-WebRequest` командлет для получения строк JSON из веб-службы, а затем использует `ConvertFrom-Json` командлет для преобразования содержимого JSON в объекты, которыми можно управлять в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23557-122">This command uses the `Invoke-WebRequest` cmdlet to get JSON strings from a web service and then it uses the `ConvertFrom-Json` cmdlet to convert JSON content to objects that can be managed in PowerShell.</span></span>

```powershell
# Ensures that Invoke-WebRequest uses TLS 1.2
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
$j = Invoke-WebRequest 'https://api.github.com/repos/PowerShell/PowerShell/issues' | ConvertFrom-Json
```

<span data-ttu-id="23557-123">Можно также использовать `Invoke-RestMethod` командлет, который автоматически преобразует содержимое JSON в объекты.</span><span class="sxs-lookup"><span data-stu-id="23557-123">You can also use the `Invoke-RestMethod` cmdlet, which automatically converts JSON content to objects.</span></span>

### <span data-ttu-id="23557-124">Пример 3. Преобразование строки JSON в пользовательский объект</span><span class="sxs-lookup"><span data-stu-id="23557-124">Example 3: Convert a JSON string to a custom object</span></span>

<span data-ttu-id="23557-125">В этом примере показано, как использовать `ConvertFrom-Json` командлет для преобразования JSON-файла в пользовательский объект PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23557-125">This example shows how to use the `ConvertFrom-Json` cmdlet to convert a JSON file to a PowerShell custom object.</span></span>

```powershell
Get-Content JsonFile.JSON | ConvertFrom-Json
```

<span data-ttu-id="23557-126">Команда использует командлет Get-Content для получения строк в JSON-файле.</span><span class="sxs-lookup"><span data-stu-id="23557-126">The command uses Get-Content cmdlet to get the strings in a JSON file.</span></span> <span data-ttu-id="23557-127">Затем он использует оператор конвейера для отправки строки с разделителями в `ConvertFrom-Json` командлет, который преобразует его в пользовательский объект.</span><span class="sxs-lookup"><span data-stu-id="23557-127">Then it uses the pipeline operator to send the delimited string to the `ConvertFrom-Json` cmdlet, which converts it to a custom object.</span></span>

## <span data-ttu-id="23557-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="23557-128">PARAMETERS</span></span>

### <span data-ttu-id="23557-129">-InputObject</span><span class="sxs-lookup"><span data-stu-id="23557-129">-InputObject</span></span>

<span data-ttu-id="23557-130">Указывает строки JSON, которые нужно преобразовать в объекты JSON.</span><span class="sxs-lookup"><span data-stu-id="23557-130">Specifies the JSON strings to convert to JSON objects.</span></span> <span data-ttu-id="23557-131">Введите переменную, содержащую строку, либо введите команду или выражение для получения строки.</span><span class="sxs-lookup"><span data-stu-id="23557-131">Enter a variable that contains the string, or type a command or expression that gets the string.</span></span> <span data-ttu-id="23557-132">Можно также передать строку в `ConvertFrom-Json` .</span><span class="sxs-lookup"><span data-stu-id="23557-132">You can also pipe a string to `ConvertFrom-Json`.</span></span>

<span data-ttu-id="23557-133">Параметр **InputObject** обязателен, но его значением может быть пустая строка.</span><span class="sxs-lookup"><span data-stu-id="23557-133">The **InputObject** parameter is required, but its value can be an empty string.</span></span> <span data-ttu-id="23557-134">Если входной объект является пустой строкой, `ConvertFrom-Json` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="23557-134">When the input object is an empty string, `ConvertFrom-Json` does not generate any output.</span></span> <span data-ttu-id="23557-135">Значение **InputObject** не может быть `$null` .</span><span class="sxs-lookup"><span data-stu-id="23557-135">The **InputObject** value cannot be `$null`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="23557-136">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="23557-136">CommonParameters</span></span>

<span data-ttu-id="23557-137">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="23557-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="23557-138">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="23557-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="23557-139">Входные данные</span><span class="sxs-lookup"><span data-stu-id="23557-139">INPUTS</span></span>

### <span data-ttu-id="23557-140">System.String</span><span class="sxs-lookup"><span data-stu-id="23557-140">System.String</span></span>

<span data-ttu-id="23557-141">Строку JSON можно передать в `ConvertFrom-Json` .</span><span class="sxs-lookup"><span data-stu-id="23557-141">You can pipe a JSON string to `ConvertFrom-Json`.</span></span>

## <span data-ttu-id="23557-142">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="23557-142">OUTPUTS</span></span>

### <span data-ttu-id="23557-143">PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="23557-143">PSCustomObject</span></span>

## <span data-ttu-id="23557-144">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="23557-144">NOTES</span></span>

<span data-ttu-id="23557-145">`ConvertFrom-Json`Командлет реализуется с помощью [класса JavaScriptSerializer](/dotnet/api/system.web.script.serialization.javascriptserializer).</span><span class="sxs-lookup"><span data-stu-id="23557-145">The `ConvertFrom-Json` cmdlet is implemented using the [JavaScriptSerializer class](/dotnet/api/system.web.script.serialization.javascriptserializer).</span></span>

## <span data-ttu-id="23557-146">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="23557-146">RELATED LINKS</span></span>

<span data-ttu-id="23557-147">[Введение в нотация объектов JavaScript (JSON) в JavaScript и .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="23557-147">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="23557-148">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="23557-148">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="23557-149">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="23557-149">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="23557-150">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="23557-150">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)
