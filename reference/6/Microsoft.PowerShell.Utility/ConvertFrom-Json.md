---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-json?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Json
ms.openlocfilehash: 0cf439651d3382ce5abf3e5de4812df92cb8492d
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94389850"
---
# <span data-ttu-id="a1404-103">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="a1404-103">ConvertFrom-Json</span></span>

## <span data-ttu-id="a1404-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a1404-104">SYNOPSIS</span></span>
<span data-ttu-id="a1404-105">Преобразует строку в формате JSON в пользовательский объект или хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="a1404-105">Converts a JSON-formatted string to a custom object or a hash table.</span></span>

## <span data-ttu-id="a1404-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a1404-106">SYNTAX</span></span>

```
ConvertFrom-Json [-InputObject] <String> [-AsHashtable] [-Depth <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="a1404-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a1404-107">DESCRIPTION</span></span>

<span data-ttu-id="a1404-108">`ConvertFrom-Json`Командлет преобразует строку в формате нотация объектов JavaScript (JSON) в пользовательский объект **PSCustomObject** , имеющий свойство для каждого поля в строке JSON.</span><span class="sxs-lookup"><span data-stu-id="a1404-108">The `ConvertFrom-Json` cmdlet converts a JavaScript Object Notation (JSON) formatted string to a custom **PSCustomObject** object that has a property for each field in the JSON string.</span></span> <span data-ttu-id="a1404-109">Формат JSON обычно используется на веб-сайтах для текстового представления объектов.</span><span class="sxs-lookup"><span data-stu-id="a1404-109">JSON is commonly used by web sites to provide a textual representation of objects.</span></span> <span data-ttu-id="a1404-110">Стандарт JSON не запрещает использование, которое запрещено **PSCustomObject**.</span><span class="sxs-lookup"><span data-stu-id="a1404-110">The JSON standard does not prohibit usage that is prohibited with a **PSCustomObject**.</span></span> <span data-ttu-id="a1404-111">Например, если строка JSON содержит дублирующиеся ключи, этот командлет использует только последний ключ.</span><span class="sxs-lookup"><span data-stu-id="a1404-111">For example, if the JSON string contains duplicate keys, only the last key is used by this cmdlet.</span></span> <span data-ttu-id="a1404-112">См. Другие примеры ниже.</span><span class="sxs-lookup"><span data-stu-id="a1404-112">See other examples below.</span></span>

<span data-ttu-id="a1404-113">Чтобы создать строку JSON из любого объекта, используйте `ConvertTo-Json` командлет.</span><span class="sxs-lookup"><span data-stu-id="a1404-113">To generate a JSON string from any object, use the `ConvertTo-Json` cmdlet.</span></span>

<span data-ttu-id="a1404-114">Этот командлет появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="a1404-114">This cmdlet was introduced in PowerShell 3.0.</span></span>

> [!NOTE]
> <span data-ttu-id="a1404-115">Начиная с PowerShell 6, этот командлет поддерживает JSON с комментариями.</span><span class="sxs-lookup"><span data-stu-id="a1404-115">Beginning with PowerShell 6, this cmdlet supports JSON with comments.</span></span> <span data-ttu-id="a1404-116">Принятые комментарии запускаются с двумя косыми чертами ( `//` ).</span><span class="sxs-lookup"><span data-stu-id="a1404-116">Accepted comments are started with two forward slashes (`//`).</span></span> <span data-ttu-id="a1404-117">Комментарий не будет представлен в данных и может быть записан в файл без повреждения данных или вызова ошибки, как это делалось в PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="a1404-117">The comment will not be represented in the data and can be written in the file without corrupting the data or throwing an error as it did in PowerShell 5.1.</span></span>

## <span data-ttu-id="a1404-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="a1404-118">EXAMPLES</span></span>

### <span data-ttu-id="a1404-119">Пример 1. преобразование объекта DateTime в объект JSON</span><span class="sxs-lookup"><span data-stu-id="a1404-119">Example 1: Convert a DateTime object to a JSON object</span></span>

<span data-ttu-id="a1404-120">Эта команда использует `ConvertTo-Json` `ConvertFrom-Json` командлеты и для преобразования объекта **DateTime** из `Get-Date` командлета в объект JSON и затем в **PSCustomObject**.</span><span class="sxs-lookup"><span data-stu-id="a1404-120">This command uses the `ConvertTo-Json` and `ConvertFrom-Json` cmdlets to convert a **DateTime** object from the `Get-Date` cmdlet to a JSON object then to a **PSCustomObject**.</span></span>

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

<span data-ttu-id="a1404-121">В примере используется `Select-Object` командлет для получения всех свойств объекта **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="a1404-121">The example uses the `Select-Object` cmdlet to get all of the properties of the **DateTime** object.</span></span> <span data-ttu-id="a1404-122">Он использует `ConvertTo-Json` командлет для преобразования объекта **DateTime** в строку, отформатированную в виде объекта JSON, и `ConvertFrom-Json` командлет для преобразования строки в формате JSON в объект **PSCustomObject** .</span><span class="sxs-lookup"><span data-stu-id="a1404-122">It uses the `ConvertTo-Json` cmdlet to convert the **DateTime** object to a string formatted as a JSON object and the `ConvertFrom-Json` cmdlet to convert the JSON-formatted string to a **PSCustomObject** object.</span></span>

### <span data-ttu-id="a1404-123">Пример 2. Получение строк JSON из веб-службы и их преобразование в объекты PowerShell</span><span class="sxs-lookup"><span data-stu-id="a1404-123">Example 2: Get JSON strings from a web service and convert them to PowerShell objects</span></span>

<span data-ttu-id="a1404-124">Эта команда использует `Invoke-WebRequest` командлет для получения строк JSON из веб-службы, а затем использует `ConvertFrom-Json` командлет для преобразования содержимого JSON в объекты, которыми можно управлять в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a1404-124">This command uses the `Invoke-WebRequest` cmdlet to get JSON strings from a web service and then it uses the `ConvertFrom-Json` cmdlet to convert JSON content to objects that can be managed in PowerShell.</span></span>

```powershell
# Ensures that Invoke-WebRequest uses TLS 1.2
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
$j = Invoke-WebRequest 'https://api.github.com/repos/PowerShell/PowerShell/issues' | ConvertFrom-Json
```

<span data-ttu-id="a1404-125">Можно также использовать `Invoke-RestMethod` командлет, который автоматически преобразует содержимое JSON в объекты.</span><span class="sxs-lookup"><span data-stu-id="a1404-125">You can also use the `Invoke-RestMethod` cmdlet, which automatically converts JSON content to objects.</span></span>

### <span data-ttu-id="a1404-126">Пример 3. Преобразование строки JSON в пользовательский объект</span><span class="sxs-lookup"><span data-stu-id="a1404-126">Example 3: Convert a JSON string to a custom object</span></span>

<span data-ttu-id="a1404-127">В этом примере показано, как использовать `ConvertFrom-Json` командлет для преобразования JSON-файла в пользовательский объект PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a1404-127">This example shows how to use the `ConvertFrom-Json` cmdlet to convert a JSON file to a PowerShell custom object.</span></span>

```powershell
Get-Content JsonFile.JSON | ConvertFrom-Json
```

<span data-ttu-id="a1404-128">Команда использует командлет Get-Content для получения строк в JSON-файле.</span><span class="sxs-lookup"><span data-stu-id="a1404-128">The command uses Get-Content cmdlet to get the strings in a JSON file.</span></span> <span data-ttu-id="a1404-129">Затем он использует оператор конвейера для отправки строки с разделителями в `ConvertFrom-Json` командлет, который преобразует его в пользовательский объект.</span><span class="sxs-lookup"><span data-stu-id="a1404-129">Then it uses the pipeline operator to send the delimited string to the `ConvertFrom-Json` cmdlet, which converts it to a custom object.</span></span>

### <span data-ttu-id="a1404-130">Пример 4. Преобразование строки JSON в хэш-таблицу</span><span class="sxs-lookup"><span data-stu-id="a1404-130">Example 4: Convert a JSON string to a hash table</span></span>

<span data-ttu-id="a1404-131">Эта команда показывает пример, в котором `-AsHashtable` коммутатор может преодолеть ограничения команды.</span><span class="sxs-lookup"><span data-stu-id="a1404-131">This command shows an example where the `-AsHashtable` switch can overcome limitations of the command.</span></span>

```powershell
'{ "key":"value1", "Key":"value2" }' | ConvertFrom-Json -AsHashtable
```

<span data-ttu-id="a1404-132">Строка JSON содержит две пары "ключ — значение" с ключами, которые отличаются только регистром.</span><span class="sxs-lookup"><span data-stu-id="a1404-132">The JSON string contains two key value pairs with keys that differ only in casing.</span></span> <span data-ttu-id="a1404-133">Без параметра команда вызовет ошибку.</span><span class="sxs-lookup"><span data-stu-id="a1404-133">Without the switch, the command would have thrown an error.</span></span>

## <span data-ttu-id="a1404-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a1404-134">PARAMETERS</span></span>

### <span data-ttu-id="a1404-135">-AsHashtable</span><span class="sxs-lookup"><span data-stu-id="a1404-135">-AsHashtable</span></span>

<span data-ttu-id="a1404-136">Преобразует JSON в объект хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="a1404-136">Converts the JSON to a hash table object.</span></span> <span data-ttu-id="a1404-137">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="a1404-137">This switch was introduced in PowerShell 6.0.</span></span> <span data-ttu-id="a1404-138">Существует несколько сценариев, в которых можно преодолеть некоторые ограничения `ConvertFrom-Json` командлета.</span><span class="sxs-lookup"><span data-stu-id="a1404-138">There are several scenarios where it can overcome some limitations of the `ConvertFrom-Json` cmdlet.</span></span>

- <span data-ttu-id="a1404-139">Если в JSON содержится список с ключами, отличающимися только регистром.</span><span class="sxs-lookup"><span data-stu-id="a1404-139">If the JSON contains a list with keys that only differ in casing.</span></span> <span data-ttu-id="a1404-140">Без параметра эти ключи будут рассматриваться как идентичные ключи, поэтому будет использоваться только последний из них.</span><span class="sxs-lookup"><span data-stu-id="a1404-140">Without the switch, those keys would be seen as identical keys and therefore only the last one would get used.</span></span>
- <span data-ttu-id="a1404-141">Если в JSON содержится ключ, являющийся пустой строкой.</span><span class="sxs-lookup"><span data-stu-id="a1404-141">If the JSON contains a key that is an empty string.</span></span> <span data-ttu-id="a1404-142">Без параметра командлет выдаст ошибку, так как не разрешает это `PSCustomObject` , но хэш-таблица делает это.</span><span class="sxs-lookup"><span data-stu-id="a1404-142">Without the switch, the cmdlet would throw an error since a `PSCustomObject` does not allow for that but a hash table does.</span></span> <span data-ttu-id="a1404-143">В качестве примера использования может возникнуть ситуация, когда это `project.lock.json` файлы.</span><span class="sxs-lookup"><span data-stu-id="a1404-143">An example use case where this can occurs are `project.lock.json` files.</span></span>
- <span data-ttu-id="a1404-144">Хэш-таблицы могут обрабатываться быстрее для определенных структур данных.</span><span class="sxs-lookup"><span data-stu-id="a1404-144">Hash tables can be processed faster for certain data structures.</span></span>

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

### <span data-ttu-id="a1404-145">-Depth</span><span class="sxs-lookup"><span data-stu-id="a1404-145">-Depth</span></span>

<span data-ttu-id="a1404-146">Возвращает или задает максимальную глубину, которой может обладать входные данные JSON.</span><span class="sxs-lookup"><span data-stu-id="a1404-146">Gets or sets the maximum depth the JSON input is allowed to have.</span></span> <span data-ttu-id="a1404-147">По умолчанию это 1024.</span><span class="sxs-lookup"><span data-stu-id="a1404-147">By default, it is 1024.</span></span>

<span data-ttu-id="a1404-148">Этот параметр появился в PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="a1404-148">This parameter was introduced in PowerShell 6.2.</span></span>

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

### <span data-ttu-id="a1404-149">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a1404-149">-InputObject</span></span>

<span data-ttu-id="a1404-150">Указывает строки JSON, которые нужно преобразовать в объекты JSON.</span><span class="sxs-lookup"><span data-stu-id="a1404-150">Specifies the JSON strings to convert to JSON objects.</span></span> <span data-ttu-id="a1404-151">Введите переменную, содержащую строку, либо введите команду или выражение для получения строки.</span><span class="sxs-lookup"><span data-stu-id="a1404-151">Enter a variable that contains the string, or type a command or expression that gets the string.</span></span> <span data-ttu-id="a1404-152">Можно также передать строку в `ConvertFrom-Json` .</span><span class="sxs-lookup"><span data-stu-id="a1404-152">You can also pipe a string to `ConvertFrom-Json`.</span></span>

<span data-ttu-id="a1404-153">Параметр **InputObject** обязателен, но его значением может быть пустая строка.</span><span class="sxs-lookup"><span data-stu-id="a1404-153">The **InputObject** parameter is required, but its value can be an empty string.</span></span> <span data-ttu-id="a1404-154">Если входной объект является пустой строкой, `ConvertFrom-Json` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="a1404-154">When the input object is an empty string, `ConvertFrom-Json` does not generate any output.</span></span> <span data-ttu-id="a1404-155">Значение **InputObject** не может быть `$null` .</span><span class="sxs-lookup"><span data-stu-id="a1404-155">The **InputObject** value cannot be `$null`.</span></span>

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

### <span data-ttu-id="a1404-156">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a1404-156">CommonParameters</span></span>

<span data-ttu-id="a1404-157">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a1404-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a1404-158">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a1404-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a1404-159">Входные данные</span><span class="sxs-lookup"><span data-stu-id="a1404-159">INPUTS</span></span>

### <span data-ttu-id="a1404-160">System.String</span><span class="sxs-lookup"><span data-stu-id="a1404-160">System.String</span></span>

<span data-ttu-id="a1404-161">Строку JSON можно передать в `ConvertFrom-Json` .</span><span class="sxs-lookup"><span data-stu-id="a1404-161">You can pipe a JSON string to `ConvertFrom-Json`.</span></span>

## <span data-ttu-id="a1404-162">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a1404-162">OUTPUTS</span></span>

### <span data-ttu-id="a1404-163">PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="a1404-163">PSCustomObject</span></span>

### <span data-ttu-id="a1404-164">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="a1404-164">System.Collections.Hashtable</span></span>

## <span data-ttu-id="a1404-165">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="a1404-165">NOTES</span></span>

<span data-ttu-id="a1404-166">Этот командлет реализуется с помощью [Newtonsoft JSON.NET](https://www.newtonsoft.com/json).</span><span class="sxs-lookup"><span data-stu-id="a1404-166">This cmdlet is implemented using [Newtonsoft Json.NET](https://www.newtonsoft.com/json).</span></span>

<span data-ttu-id="a1404-167">Начиная с PowerShell 6, `ConvertTo-Json` пытается преобразовать строки, отформатированные как метки времени, в значения **типа DateTime** .</span><span class="sxs-lookup"><span data-stu-id="a1404-167">Beginning in PowerShell 6, `ConvertTo-Json` attempts to convert strings formatted as timestamps to **DateTime** values.</span></span> <span data-ttu-id="a1404-168">Преобразованное значение является `[datetime]` экземпляром с `Kind` набором свойств следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a1404-168">The converted value is a `[datetime]` instance with a `Kind` property set as follows:</span></span>

- <span data-ttu-id="a1404-169">`Unspecified`значение, если во входной строке нет сведений о часовом поясе.</span><span class="sxs-lookup"><span data-stu-id="a1404-169">`Unspecified`, if there is no time zone information in the input string.</span></span>
- <span data-ttu-id="a1404-170">`Utc`значение, если сведения о часовом поясе являются конечными `Z` .</span><span class="sxs-lookup"><span data-stu-id="a1404-170">`Utc`, if the time zone information is a trailing `Z`.</span></span>
- <span data-ttu-id="a1404-171">`Local`значение, если сведения о часовом поясе заданы в качестве _смещения_ в конце UTC, например `+02:00` .</span><span class="sxs-lookup"><span data-stu-id="a1404-171">`Local`, if the time zone information is given as a trailing UTC _offset_ like `+02:00`.</span></span> <span data-ttu-id="a1404-172">Смещение правильно преобразуется в настроенный часовой пояс вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="a1404-172">The offset is properly converted to the caller's configured time zone.</span></span> <span data-ttu-id="a1404-173">Форматирование выхода по умолчанию не указывает на исходное смещение часового пояса.</span><span class="sxs-lookup"><span data-stu-id="a1404-173">The default output formatting does not indicate the original time zone offset.</span></span>

## <span data-ttu-id="a1404-174">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a1404-174">RELATED LINKS</span></span>

<span data-ttu-id="a1404-175">[Введение в нотация объектов JavaScript (JSON) в JavaScript и .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="a1404-175">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="a1404-176">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="a1404-176">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="a1404-177">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="a1404-177">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="a1404-178">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="a1404-178">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)
