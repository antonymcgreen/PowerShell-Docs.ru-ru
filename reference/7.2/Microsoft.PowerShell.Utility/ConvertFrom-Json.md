---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-json?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Json
ms.openlocfilehash: 525b123d48b0f88ca3eef85a3f95cc303a981ca3
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605054"
---
# <span data-ttu-id="627f6-102">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="627f6-102">ConvertFrom-Json</span></span>

## <span data-ttu-id="627f6-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="627f6-103">SYNOPSIS</span></span>
<span data-ttu-id="627f6-104">Преобразует строку в формате JSON в пользовательский объект или хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="627f6-104">Converts a JSON-formatted string to a custom object or a hash table.</span></span>

## <span data-ttu-id="627f6-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="627f6-105">SYNTAX</span></span>

```
ConvertFrom-Json [-InputObject] <String> [-AsHashtable] [-Depth <Int32>] [-NoEnumerate] [<CommonParameters>]
```

## <span data-ttu-id="627f6-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="627f6-106">DESCRIPTION</span></span>

<span data-ttu-id="627f6-107">`ConvertFrom-Json`Командлет преобразует строку в формате нотация объектов JavaScript (JSON) в пользовательский объект **PSCustomObject** , имеющий свойство для каждого поля в строке JSON.</span><span class="sxs-lookup"><span data-stu-id="627f6-107">The `ConvertFrom-Json` cmdlet converts a JavaScript Object Notation (JSON) formatted string to a custom **PSCustomObject** object that has a property for each field in the JSON string.</span></span> <span data-ttu-id="627f6-108">Формат JSON обычно используется на веб-сайтах для текстового представления объектов.</span><span class="sxs-lookup"><span data-stu-id="627f6-108">JSON is commonly used by web sites to provide a textual representation of objects.</span></span> <span data-ttu-id="627f6-109">Стандарт JSON не запрещает использование, которое запрещено **PSCustomObject**.</span><span class="sxs-lookup"><span data-stu-id="627f6-109">The JSON standard does not prohibit usage that is prohibited with a **PSCustomObject**.</span></span> <span data-ttu-id="627f6-110">Например, если строка JSON содержит дублирующиеся ключи, этот командлет использует только последний ключ.</span><span class="sxs-lookup"><span data-stu-id="627f6-110">For example, if the JSON string contains duplicate keys, only the last key is used by this cmdlet.</span></span> <span data-ttu-id="627f6-111">См. Другие примеры ниже.</span><span class="sxs-lookup"><span data-stu-id="627f6-111">See other examples below.</span></span>

<span data-ttu-id="627f6-112">Чтобы создать строку JSON из любого объекта, используйте `ConvertTo-Json` командлет.</span><span class="sxs-lookup"><span data-stu-id="627f6-112">To generate a JSON string from any object, use the `ConvertTo-Json` cmdlet.</span></span>

<span data-ttu-id="627f6-113">Этот командлет появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="627f6-113">This cmdlet was introduced in PowerShell 3.0.</span></span>

> [!NOTE]
> <span data-ttu-id="627f6-114">Начиная с PowerShell 6, этот командлет поддерживает JSON с комментариями.</span><span class="sxs-lookup"><span data-stu-id="627f6-114">Beginning with PowerShell 6, this cmdlet supports JSON with comments.</span></span> <span data-ttu-id="627f6-115">Принятые комментарии запускаются с двумя косыми чертами ( `//` ).</span><span class="sxs-lookup"><span data-stu-id="627f6-115">Accepted comments are started with two forward slashes (`//`).</span></span> <span data-ttu-id="627f6-116">Комментарий не будет представлен в данных и может быть записан в файл без повреждения данных или вызова ошибки, как это делалось в PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="627f6-116">The comment will not be represented in the data and can be written in the file without corrupting the data or throwing an error as it did in PowerShell 5.1.</span></span>

## <span data-ttu-id="627f6-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="627f6-117">EXAMPLES</span></span>

### <span data-ttu-id="627f6-118">Пример 1. преобразование объекта DateTime в объект JSON</span><span class="sxs-lookup"><span data-stu-id="627f6-118">Example 1: Convert a DateTime object to a JSON object</span></span>

<span data-ttu-id="627f6-119">Эта команда использует `ConvertTo-Json` `ConvertFrom-Json` командлеты и для преобразования объекта **DateTime** из `Get-Date` командлета в объект JSON и затем в **PSCustomObject**.</span><span class="sxs-lookup"><span data-stu-id="627f6-119">This command uses the `ConvertTo-Json` and `ConvertFrom-Json` cmdlets to convert a **DateTime** object from the `Get-Date` cmdlet to a JSON object then to a **PSCustomObject**.</span></span>

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

<span data-ttu-id="627f6-120">В примере используется `Select-Object` командлет для получения всех свойств объекта **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="627f6-120">The example uses the `Select-Object` cmdlet to get all of the properties of the **DateTime** object.</span></span> <span data-ttu-id="627f6-121">Он использует `ConvertTo-Json` командлет для преобразования объекта **DateTime** в строку, отформатированную в виде объекта JSON, и `ConvertFrom-Json` командлет для преобразования строки в формате JSON в объект **PSCustomObject** .</span><span class="sxs-lookup"><span data-stu-id="627f6-121">It uses the `ConvertTo-Json` cmdlet to convert the **DateTime** object to a string formatted as a JSON object and the `ConvertFrom-Json` cmdlet to convert the JSON-formatted string to a **PSCustomObject** object.</span></span>

### <span data-ttu-id="627f6-122">Пример 2. Получение строк JSON из веб-службы и их преобразование в объекты PowerShell</span><span class="sxs-lookup"><span data-stu-id="627f6-122">Example 2: Get JSON strings from a web service and convert them to PowerShell objects</span></span>

<span data-ttu-id="627f6-123">Эта команда использует `Invoke-WebRequest` командлет для получения строк JSON из веб-службы, а затем использует `ConvertFrom-Json` командлет для преобразования содержимого JSON в объекты, которыми можно управлять в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="627f6-123">This command uses the `Invoke-WebRequest` cmdlet to get JSON strings from a web service and then it uses the `ConvertFrom-Json` cmdlet to convert JSON content to objects that can be managed in PowerShell.</span></span>

```powershell
# Ensures that Invoke-WebRequest uses TLS 1.2
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
$j = Invoke-WebRequest 'https://api.github.com/repos/PowerShell/PowerShell/issues' | ConvertFrom-Json
```

<span data-ttu-id="627f6-124">Можно также использовать `Invoke-RestMethod` командлет, который автоматически преобразует содержимое JSON в объекты.</span><span class="sxs-lookup"><span data-stu-id="627f6-124">You can also use the `Invoke-RestMethod` cmdlet, which automatically converts JSON content to objects.</span></span>

### <span data-ttu-id="627f6-125">Пример 3. Преобразование строки JSON в пользовательский объект</span><span class="sxs-lookup"><span data-stu-id="627f6-125">Example 3: Convert a JSON string to a custom object</span></span>

<span data-ttu-id="627f6-126">В этом примере показано, как использовать `ConvertFrom-Json` командлет для преобразования JSON-файла в пользовательский объект PowerShell.</span><span class="sxs-lookup"><span data-stu-id="627f6-126">This example shows how to use the `ConvertFrom-Json` cmdlet to convert a JSON file to a PowerShell custom object.</span></span>

```powershell
Get-Content JsonFile.JSON | ConvertFrom-Json
```

<span data-ttu-id="627f6-127">Команда использует командлет Get-Content для получения строк в JSON-файле.</span><span class="sxs-lookup"><span data-stu-id="627f6-127">The command uses Get-Content cmdlet to get the strings in a JSON file.</span></span> <span data-ttu-id="627f6-128">Затем он использует оператор конвейера для отправки строки с разделителями в `ConvertFrom-Json` командлет, который преобразует его в пользовательский объект.</span><span class="sxs-lookup"><span data-stu-id="627f6-128">Then it uses the pipeline operator to send the delimited string to the `ConvertFrom-Json` cmdlet, which converts it to a custom object.</span></span>

### <span data-ttu-id="627f6-129">Пример 4. Преобразование строки JSON в хэш-таблицу</span><span class="sxs-lookup"><span data-stu-id="627f6-129">Example 4: Convert a JSON string to a hash table</span></span>

<span data-ttu-id="627f6-130">Эта команда показывает пример, в котором `-AsHashtable` коммутатор может преодолеть ограничения команды.</span><span class="sxs-lookup"><span data-stu-id="627f6-130">This command shows an example where the `-AsHashtable` switch can overcome limitations of the command.</span></span>

```powershell
'{ "key":"value1", "Key":"value2" }' | ConvertFrom-Json -AsHashtable
```

<span data-ttu-id="627f6-131">Строка JSON содержит две пары "ключ — значение" с ключами, которые отличаются только регистром.</span><span class="sxs-lookup"><span data-stu-id="627f6-131">The JSON string contains two key value pairs with keys that differ only in casing.</span></span> <span data-ttu-id="627f6-132">Без параметра команда вызовет ошибку.</span><span class="sxs-lookup"><span data-stu-id="627f6-132">Without the switch, the command would have thrown an error.</span></span>

### <span data-ttu-id="627f6-133">Пример 5. цикл обработки одного массива элементов</span><span class="sxs-lookup"><span data-stu-id="627f6-133">Example 5: Round-trip a single element array</span></span>

<span data-ttu-id="627f6-134">Эта команда показывает пример, в котором `-NoEnumerate` параметр используется для приема-передачи массива JSON с одним элементом.</span><span class="sxs-lookup"><span data-stu-id="627f6-134">This command shows an example where the `-NoEnumerate` switch is used to round-trip a single element JSON array.</span></span>

```powershell
Write-Output "With -NoEnumerate: $('[1]' | ConvertFrom-Json -NoEnumerate | ConvertTo-Json -Compress)"
Write-Output "Without -NoEnumerate: $('[1]' | ConvertFrom-Json | ConvertTo-Json -Compress)"
```

```Output
With -NoEnumerate: [1]
Without -NoEnumerate: 1
```

<span data-ttu-id="627f6-135">Строка JSON содержит массив с одним элементом.</span><span class="sxs-lookup"><span data-stu-id="627f6-135">The JSON string contains an array with a single element.</span></span> <span data-ttu-id="627f6-136">Без параметра преобразование JSON в PSObject, а затем преобразование его обратно с помощью `ConvertTo-Json` команды приводит к одному целому числу.</span><span class="sxs-lookup"><span data-stu-id="627f6-136">Without the switch, converting the JSON to a PSObject and then converting it back with the `ConvertTo-Json` command results in a single integer.</span></span>

## <span data-ttu-id="627f6-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="627f6-137">PARAMETERS</span></span>

### <span data-ttu-id="627f6-138">-AsHashtable</span><span class="sxs-lookup"><span data-stu-id="627f6-138">-AsHashtable</span></span>

<span data-ttu-id="627f6-139">Преобразует JSON в объект хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="627f6-139">Converts the JSON to a hash table object.</span></span> <span data-ttu-id="627f6-140">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="627f6-140">This switch was introduced in PowerShell 6.0.</span></span> <span data-ttu-id="627f6-141">Существует несколько сценариев, в которых можно преодолеть некоторые ограничения `ConvertFrom-Json` командлета.</span><span class="sxs-lookup"><span data-stu-id="627f6-141">There are several scenarios where it can overcome some limitations of the `ConvertFrom-Json` cmdlet.</span></span>

- <span data-ttu-id="627f6-142">Если в JSON содержится список с ключами, отличающимися только регистром.</span><span class="sxs-lookup"><span data-stu-id="627f6-142">If the JSON contains a list with keys that only differ in casing.</span></span> <span data-ttu-id="627f6-143">Без параметра эти ключи будут рассматриваться как идентичные ключи, поэтому будет использоваться только последний из них.</span><span class="sxs-lookup"><span data-stu-id="627f6-143">Without the switch, those keys would be seen as identical keys and therefore only the last one would get used.</span></span>
- <span data-ttu-id="627f6-144">Если в JSON содержится ключ, являющийся пустой строкой.</span><span class="sxs-lookup"><span data-stu-id="627f6-144">If the JSON contains a key that is an empty string.</span></span> <span data-ttu-id="627f6-145">Без параметра командлет выдаст ошибку, так как не разрешает это `PSCustomObject` , но хэш-таблица делает это.</span><span class="sxs-lookup"><span data-stu-id="627f6-145">Without the switch, the cmdlet would throw an error since a `PSCustomObject` does not allow for that but a hash table does.</span></span> <span data-ttu-id="627f6-146">В качестве примера использования может возникнуть ситуация, когда это `project.lock.json` файлы.</span><span class="sxs-lookup"><span data-stu-id="627f6-146">An example use case where this can occurs are `project.lock.json` files.</span></span>
- <span data-ttu-id="627f6-147">Хэш-таблицы могут обрабатываться быстрее для определенных структур данных.</span><span class="sxs-lookup"><span data-stu-id="627f6-147">Hash tables can be processed faster for certain data structures.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="627f6-148">-Depth</span><span class="sxs-lookup"><span data-stu-id="627f6-148">-Depth</span></span>

<span data-ttu-id="627f6-149">Возвращает или задает максимальную глубину, которой может обладать входные данные JSON.</span><span class="sxs-lookup"><span data-stu-id="627f6-149">Gets or sets the maximum depth the JSON input is allowed to have.</span></span> <span data-ttu-id="627f6-150">По умолчанию это 1024.</span><span class="sxs-lookup"><span data-stu-id="627f6-150">By default, it is 1024.</span></span>

<span data-ttu-id="627f6-151">Этот параметр появился в PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="627f6-151">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="627f6-152">-InputObject</span><span class="sxs-lookup"><span data-stu-id="627f6-152">-InputObject</span></span>

<span data-ttu-id="627f6-153">Указывает строки JSON, которые нужно преобразовать в объекты JSON.</span><span class="sxs-lookup"><span data-stu-id="627f6-153">Specifies the JSON strings to convert to JSON objects.</span></span> <span data-ttu-id="627f6-154">Введите переменную, содержащую строку, либо введите команду или выражение для получения строки.</span><span class="sxs-lookup"><span data-stu-id="627f6-154">Enter a variable that contains the string, or type a command or expression that gets the string.</span></span> <span data-ttu-id="627f6-155">Можно также передать строку в `ConvertFrom-Json` .</span><span class="sxs-lookup"><span data-stu-id="627f6-155">You can also pipe a string to `ConvertFrom-Json`.</span></span>

<span data-ttu-id="627f6-156">Параметр **InputObject** обязателен, но его значением может быть пустая строка.</span><span class="sxs-lookup"><span data-stu-id="627f6-156">The **InputObject** parameter is required, but its value can be an empty string.</span></span> <span data-ttu-id="627f6-157">Если входной объект является пустой строкой, `ConvertFrom-Json` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="627f6-157">When the input object is an empty string, `ConvertFrom-Json` does not generate any output.</span></span> <span data-ttu-id="627f6-158">Значение **InputObject** не может быть `$null` .</span><span class="sxs-lookup"><span data-stu-id="627f6-158">The **InputObject** value cannot be `$null`.</span></span>

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

### <span data-ttu-id="627f6-159">-Не перечислять</span><span class="sxs-lookup"><span data-stu-id="627f6-159">-NoEnumerate</span></span>

<span data-ttu-id="627f6-160">Указывает, что выходные данные не перечисляются.</span><span class="sxs-lookup"><span data-stu-id="627f6-160">Specifies that output is not enumerated.</span></span>

<span data-ttu-id="627f6-161">Установка этого параметра приводит к тому, что массивы отправляются в виде одного объекта вместо отправки каждого элемента отдельно.</span><span class="sxs-lookup"><span data-stu-id="627f6-161">Setting this parameter causes arrays to be sent as a single object instead of sending every element separately.</span></span> <span data-ttu-id="627f6-162">Это гарантирует, что JSON можно будет обрабатывать с помощью `ConvertTo-Json` .</span><span class="sxs-lookup"><span data-stu-id="627f6-162">This guarantees that JSON can be round-tripped via `ConvertTo-Json`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="627f6-163">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="627f6-163">CommonParameters</span></span>

<span data-ttu-id="627f6-164">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="627f6-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="627f6-165">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="627f6-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="627f6-166">Входные данные</span><span class="sxs-lookup"><span data-stu-id="627f6-166">INPUTS</span></span>

### <span data-ttu-id="627f6-167">System.String</span><span class="sxs-lookup"><span data-stu-id="627f6-167">System.String</span></span>

<span data-ttu-id="627f6-168">Строку JSON можно передать в `ConvertFrom-Json` .</span><span class="sxs-lookup"><span data-stu-id="627f6-168">You can pipe a JSON string to `ConvertFrom-Json`.</span></span>

## <span data-ttu-id="627f6-169">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="627f6-169">OUTPUTS</span></span>

### <span data-ttu-id="627f6-170">PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="627f6-170">PSCustomObject</span></span>

### <span data-ttu-id="627f6-171">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="627f6-171">System.Collections.Hashtable</span></span>

## <span data-ttu-id="627f6-172">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="627f6-172">NOTES</span></span>

<span data-ttu-id="627f6-173">Этот командлет реализуется с помощью [Newtonsoft JSON.NET](https://www.newtonsoft.com/json).</span><span class="sxs-lookup"><span data-stu-id="627f6-173">This cmdlet is implemented using [Newtonsoft Json.NET](https://www.newtonsoft.com/json).</span></span>

<span data-ttu-id="627f6-174">Начиная с PowerShell 6, `ConvertTo-Json` пытается преобразовать строки, отформатированные как метки времени, в значения **типа DateTime** .</span><span class="sxs-lookup"><span data-stu-id="627f6-174">Beginning in PowerShell 6, `ConvertTo-Json` attempts to convert strings formatted as timestamps to **DateTime** values.</span></span> <span data-ttu-id="627f6-175">Преобразованное значение является `[datetime]` экземпляром с `Kind` набором свойств следующим образом:</span><span class="sxs-lookup"><span data-stu-id="627f6-175">The converted value is a `[datetime]` instance with a `Kind` property set as follows:</span></span>

- <span data-ttu-id="627f6-176">`Unspecified`значение, если во входной строке нет сведений о часовом поясе.</span><span class="sxs-lookup"><span data-stu-id="627f6-176">`Unspecified`, if there is no time zone information in the input string.</span></span>
- <span data-ttu-id="627f6-177">`Utc`значение, если сведения о часовом поясе являются конечными `Z` .</span><span class="sxs-lookup"><span data-stu-id="627f6-177">`Utc`, if the time zone information is a trailing `Z`.</span></span>
- <span data-ttu-id="627f6-178">`Local`значение, если сведения о часовом поясе заданы в качестве _смещения_ в конце UTC, например `+02:00` .</span><span class="sxs-lookup"><span data-stu-id="627f6-178">`Local`, if the time zone information is given as a trailing UTC _offset_ like `+02:00`.</span></span> <span data-ttu-id="627f6-179">Смещение правильно преобразуется в настроенный часовой пояс вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="627f6-179">The offset is properly converted to the caller's configured time zone.</span></span> <span data-ttu-id="627f6-180">Форматирование выхода по умолчанию не указывает на исходное смещение часового пояса.</span><span class="sxs-lookup"><span data-stu-id="627f6-180">The default output formatting does not indicate the original time zone offset.</span></span>

## <span data-ttu-id="627f6-181">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="627f6-181">RELATED LINKS</span></span>

<span data-ttu-id="627f6-182">[Введение в нотация объектов JavaScript (JSON) в JavaScript и .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="627f6-182">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="627f6-183">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="627f6-183">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="627f6-184">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="627f6-184">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="627f6-185">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="627f6-185">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)
