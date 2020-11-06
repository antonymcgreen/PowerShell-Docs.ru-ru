---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-content?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Content
ms.openlocfilehash: 951edd4219b3d35530b691be9faa8595da297b5c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228834"
---
# <span data-ttu-id="96b91-103">Get-Content</span><span class="sxs-lookup"><span data-stu-id="96b91-103">Get-Content</span></span>

## <span data-ttu-id="96b91-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="96b91-104">SYNOPSIS</span></span>
<span data-ttu-id="96b91-105">Получает содержимое элемента в указанном расположении.</span><span class="sxs-lookup"><span data-stu-id="96b91-105">Gets the content of the item at the specified location.</span></span>

## <span data-ttu-id="96b91-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="96b91-106">SYNTAX</span></span>

### <span data-ttu-id="96b91-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="96b91-107">Path (Default)</span></span>

```
Get-Content [-ReadCount <Int64>] [-TotalCount <Int64>] [-Tail <Int32>] [-Path] <String[]>
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force] [-Credential <PSCredential>]
 [-Delimiter <String>] [-Wait] [-Raw] [-Encoding <Encoding>] [-AsByteStream] [-Stream <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="96b91-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="96b91-108">LiteralPath</span></span>

```
Get-Content [-ReadCount <Int64>] [-TotalCount <Int64>] [-Tail <Int32>] -LiteralPath <String[]>
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force] [-Credential <PSCredential>]
 [-Delimiter <String>] [-Wait] [-Raw] [-Encoding <Encoding>] [-AsByteStream] [-Stream <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="96b91-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="96b91-109">DESCRIPTION</span></span>

<span data-ttu-id="96b91-110">`Get-Content`Командлет возвращает содержимое элемента в расположении, указанном путем, например текст в файле или содержимое функции.</span><span class="sxs-lookup"><span data-stu-id="96b91-110">The `Get-Content` cmdlet gets the content of the item at the location specified by the path, such as the text in a file or the content of a function.</span></span> <span data-ttu-id="96b91-111">Для файлов содержимое считывается по одной строке за раз и возвращает коллекцию объектов, каждая из которых представляет строку содержимого.</span><span class="sxs-lookup"><span data-stu-id="96b91-111">For files, the content is read one line at a time and returns a collection of objects, each of which represents a line of content.</span></span>

<span data-ttu-id="96b91-112">Начиная с версии PowerShell 3,0, `Get-Content` может также получить указанное число строк с начала или с конца элемента.</span><span class="sxs-lookup"><span data-stu-id="96b91-112">Beginning in PowerShell 3.0, `Get-Content` can also get a specified number of lines from the beginning or end of an item.</span></span>

## <span data-ttu-id="96b91-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="96b91-113">EXAMPLES</span></span>

### <span data-ttu-id="96b91-114">Пример 1. получение содержимого текстового файла</span><span class="sxs-lookup"><span data-stu-id="96b91-114">Example 1: Get the content of a text file</span></span>

<span data-ttu-id="96b91-115">Этот пример получает содержимое файла в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="96b91-115">This example gets the content of a file in the current directory.</span></span> <span data-ttu-id="96b91-116">`LineNumbers.txt`Файл содержит 100 строк в формате, **это строка X** и используется в нескольких примерах.</span><span class="sxs-lookup"><span data-stu-id="96b91-116">The `LineNumbers.txt` file contains 100 lines in the format, **This is Line X** and is used in several examples.</span></span>

```powershell
1..100 | ForEach-Object { Add-Content -Path .\LineNumbers.txt -Value "This is line $_." }
Get-Content -Path .\LineNumbers.txt
```

```Output
This is Line 1
This is Line 2
...
This is line 99.
This is line 100.
```

<span data-ttu-id="96b91-117">Значения массива 1-100 отправляются в командлет по конвейеру `ForEach-Object` .</span><span class="sxs-lookup"><span data-stu-id="96b91-117">The array values 1-100 are sent down the pipeline to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="96b91-118">`ForEach-Object` использует блок скрипта с `Add-Content` командлетом для создания `LineNumbers.txt` файла.</span><span class="sxs-lookup"><span data-stu-id="96b91-118">`ForEach-Object` uses a script block with the `Add-Content` cmdlet to create the `LineNumbers.txt` file.</span></span> <span data-ttu-id="96b91-119">Переменная `$_` представляет значения массива, так как каждый объект отправляется по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="96b91-119">The variable `$_` represents the array values as each object is sent down the pipeline.</span></span> <span data-ttu-id="96b91-120">`Get-Content`Командлет использует параметр **path** для указания `LineNumbers.txt` файла и отображает содержимое в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="96b91-120">The `Get-Content` cmdlet uses the **Path** parameter to specify the `LineNumbers.txt` file and displays the content in the PowerShell console.</span></span>

### <span data-ttu-id="96b91-121">Пример 2. Ограничение числа строк Get-Content возвратов</span><span class="sxs-lookup"><span data-stu-id="96b91-121">Example 2: Limit the number of lines Get-Content returns</span></span>

<span data-ttu-id="96b91-122">Эта команда возвращает первые пять строк файла.</span><span class="sxs-lookup"><span data-stu-id="96b91-122">This command gets the first five lines of a file.</span></span> <span data-ttu-id="96b91-123">Параметр **totalCount** используется для получения первых пяти строк содержимого.</span><span class="sxs-lookup"><span data-stu-id="96b91-123">The **TotalCount** parameter is used to gets the first five lines of content.</span></span> <span data-ttu-id="96b91-124">В этом примере используется `LineNumbers.txt` файл, созданный в примере 1.</span><span class="sxs-lookup"><span data-stu-id="96b91-124">This example uses the `LineNumbers.txt` file that was created in Example 1.</span></span>

```powershell
Get-Content -Path .\LineNumbers.txt -TotalCount 5
```

```Output
This is Line 1
This is Line 2
This is Line 3
This is Line 4
This is Line 5
```

### <span data-ttu-id="96b91-125">Пример 3. получение определенной строки содержимого из текстового файла</span><span class="sxs-lookup"><span data-stu-id="96b91-125">Example 3: Get a specific line of content from a text file</span></span>

<span data-ttu-id="96b91-126">Эта команда возвращает определенное количество строк из файла, а затем отображает только последнюю строку этого содержимого.</span><span class="sxs-lookup"><span data-stu-id="96b91-126">This command gets a specific number of lines from a file and then displays only the last line of that content.</span></span> <span data-ttu-id="96b91-127">Параметр **totalCount** получает первые 25 строк содержимого.</span><span class="sxs-lookup"><span data-stu-id="96b91-127">The **TotalCount** parameter gets the first 25 lines of content.</span></span> <span data-ttu-id="96b91-128">В этом примере используется `LineNumbers.txt` файл, созданный в примере 1.</span><span class="sxs-lookup"><span data-stu-id="96b91-128">This example uses the `LineNumbers.txt` file that was created in Example 1.</span></span>

```powershell
(Get-Content -Path .\LineNumbers.txt -TotalCount 25)[-1]
```

```Output
This is Line 25
```

<span data-ttu-id="96b91-129">`Get-Content`Команда заносится в круглые скобки, чтобы команда была выполнена перед переходом к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="96b91-129">The `Get-Content` command is wrapped in parentheses so that the command completes before going to the next step.</span></span> <span data-ttu-id="96b91-130">`Get-Content`Возвращает массив строк. Это позволяет добавить нотацию индекса после круглых скобок для получения определенного номера строки.</span><span class="sxs-lookup"><span data-stu-id="96b91-130">`Get-Content`returns an array of lines, this allows you to add the index notation after the parenthesis to retrieve a specific line number.</span></span> <span data-ttu-id="96b91-131">В этом случае `[-1]` индекс задает последний индекс в возвращенном массиве из 25 полученных строк.</span><span class="sxs-lookup"><span data-stu-id="96b91-131">In this case, the `[-1]` index specifies the last index in the returned array of 25 retrieved lines.</span></span>

### <span data-ttu-id="96b91-132">Пример 4. Получение последней строки текстового файла</span><span class="sxs-lookup"><span data-stu-id="96b91-132">Example 4: Get the last line of a text file</span></span>

<span data-ttu-id="96b91-133">Эта команда получает первую строку и последнюю строку содержимого из файла.</span><span class="sxs-lookup"><span data-stu-id="96b91-133">This command gets the first line and last line of content from a file.</span></span> <span data-ttu-id="96b91-134">В этом примере используется `LineNumbers.txt` файл, созданный в примере 1.</span><span class="sxs-lookup"><span data-stu-id="96b91-134">This example uses the `LineNumbers.txt` file that was created in Example 1.</span></span>

```powershell
Get-Item -Path .\LineNumbers.txt | Get-Content -Tail 1
```

```Output
This is Line 100
```

<span data-ttu-id="96b91-135">В этом примере используется `Get-Item` командлет, чтобы продемонстрировать, что можно передать файлы в `Get-Content` параметр.</span><span class="sxs-lookup"><span data-stu-id="96b91-135">This example uses the `Get-Item` cmdlet to demonstrate that you can pipe files into the `Get-Content` parameter.</span></span> <span data-ttu-id="96b91-136">Параметр **tail** получает последнюю строку файла.</span><span class="sxs-lookup"><span data-stu-id="96b91-136">The **Tail** parameter gets the last line of the file.</span></span> <span data-ttu-id="96b91-137">Этот метод выполняется быстрее, чем получение всех строк и использование `[-1]` нотации индекса.</span><span class="sxs-lookup"><span data-stu-id="96b91-137">This method is faster than retrieving all of the lines and using the `[-1]` index notation.</span></span>

### <span data-ttu-id="96b91-138">Пример 5. получение содержимого альтернативного потока данных</span><span class="sxs-lookup"><span data-stu-id="96b91-138">Example 5: Get the content of an alternate data stream</span></span>

<span data-ttu-id="96b91-139">В этом примере описывается использование параметра **Stream** для получения содержимого альтернативного потока данных для файлов, хранящихся на томе NTFS Windows.</span><span class="sxs-lookup"><span data-stu-id="96b91-139">This example describes how to use the **Stream** parameter to get the content of an alternate data stream for files stored on a Windows NTFS volume.</span></span> <span data-ttu-id="96b91-140">В этом примере `Set-Content` командлет используется для создания примера содержимого в файле с именем `Stream.txt` .</span><span class="sxs-lookup"><span data-stu-id="96b91-140">In this example, the `Set-Content` cmdlet is used to create sample content in a file named `Stream.txt`.</span></span>

```powershell
Set-Content -Path .\Stream.txt -Value 'This is the content of the Stream.txt file'
# Specify a wildcard to the Stream parameter to display all streams of the recently created file.
Get-Item -Path .\Stream.txt -Stream *
```

```Output
PSPath        : Microsoft.PowerShell.Core\FileSystem::C:\Test\Stream.txt::$DATA
PSParentPath  : Microsoft.PowerShell.Core\FileSystem::C:\Test
PSChildName   : Stream.txt::$DATA
PSDrive       : C
PSProvider    : Microsoft.PowerShell.Core\FileSystem
PSIsContainer : False
FileName      : C:\Test\Stream.txt
Stream        : :$DATA
Length        : 44
```

```powershell
# Retrieve the content of the primary, or $DATA stream.
Get-Content -Path .\Stream.txt -Stream $DATA
```

```Output
This is the content of the Stream.txt file
```

```powershell
# Use the Stream parameter of Add-Content to create a new Stream containing sample content.
Add-Content -Path .\Stream.txt -Stream NewStream -Value 'Added a stream named NewStream to Stream.txt'
# Use Get-Item to verify the stream was created.
Get-Item -Path .\Stream.txt -Stream *
```

```Output
PSPath        : Microsoft.PowerShell.Core\FileSystem::C:\Test\Stream.txt::$DATA
PSParentPath  : Microsoft.PowerShell.Core\FileSystem::C:\Test
PSChildName   : Stream.txt::$DATA
PSDrive       : C
PSProvider    : Microsoft.PowerShell.Core\FileSystem
PSIsContainer : False
FileName      : C:\Test\Stream.txt
Stream        : :$DATA
Length        : 44

PSPath        : Microsoft.PowerShell.Core\FileSystem::C:\Test\Stream.txt:NewStream
PSParentPath  : Microsoft.PowerShell.Core\FileSystem::C:\Test
PSChildName   : Stream.txt:NewStream
PSDrive       : C
PSProvider    : Microsoft.PowerShell.Core\FileSystem
PSIsContainer : False
FileName      : C:\Test\Stream.txt
Stream        : NewStream
Length        : 46
```

```powershell
# Retrieve the content of your newly created Stream.
Get-Content -Path .\Stream.txt -Stream NewStream
```

```Output
Added a stream named NewStream to Stream.txt
```

<span data-ttu-id="96b91-141">Параметр **Stream** является динамическим параметром [поставщика FileSystem](../microsoft.powershell.core/about/about_filesystem_provider.md#stream-systemstring).</span><span class="sxs-lookup"><span data-stu-id="96b91-141">The **Stream** parameter is a dynamic parameter of the [FileSystem provider](../microsoft.powershell.core/about/about_filesystem_provider.md#stream-systemstring).</span></span>
<span data-ttu-id="96b91-142">По умолчанию `Get-Content` получает только данные из первичного или `$DATA` потока.</span><span class="sxs-lookup"><span data-stu-id="96b91-142">By default `Get-Content` only retrieves data from the primary, or `$DATA` stream.</span></span> <span data-ttu-id="96b91-143">**Потоки** можно использовать для хранения скрытых данных, таких как атрибуты, параметры безопасности или другие данные.</span><span class="sxs-lookup"><span data-stu-id="96b91-143">**Streams** can be used to store hidden data such as attributes, security settings, or other data.</span></span>

### <span data-ttu-id="96b91-144">Пример 6. получение необработанного содержимого</span><span class="sxs-lookup"><span data-stu-id="96b91-144">Example 6: Get raw content</span></span>

<span data-ttu-id="96b91-145">Команды в этом примере получают содержимое файла в виде одной строки, а не массива строк.</span><span class="sxs-lookup"><span data-stu-id="96b91-145">The commands in this example get the contents of a file as one string, instead of an array of strings.</span></span> <span data-ttu-id="96b91-146">По умолчанию без **необработанного** динамического параметра содержимое возвращается в виде массива строк, разделенных символами новой строки.</span><span class="sxs-lookup"><span data-stu-id="96b91-146">By default, without the **Raw** dynamic parameter, content is returned as an array of newline-delimited strings.</span></span> <span data-ttu-id="96b91-147">В этом примере используется `LineNumbers.txt` файл, созданный в примере.</span><span class="sxs-lookup"><span data-stu-id="96b91-147">This example uses the `LineNumbers.txt` file that was created in Example</span></span>
1.

```powershell
$raw = Get-Content -Path .\LineNumbers.txt -Raw
$lines = Get-Content -Path .\LineNumbers.txt
Write-Host "Raw contains $($raw.Count) lines."
Write-Host "Lines contains $($lines.Count) lines."
```

```Output
Raw contains 1 lines.
Lines contains 100 lines.
```

### <span data-ttu-id="96b91-148">Пример 7. Использование фильтров с Get-Content</span><span class="sxs-lookup"><span data-stu-id="96b91-148">Example 7: Use Filters with Get-Content</span></span>

<span data-ttu-id="96b91-149">Можно указать фильтр для `Get-Content` командлета.</span><span class="sxs-lookup"><span data-stu-id="96b91-149">You can specify a filter to the `Get-Content` cmdlet.</span></span> <span data-ttu-id="96b91-150">При использовании фильтров для уточнения параметра **path** необходимо включить конечную звездочку ( `*` ), чтобы указать содержимое пути.</span><span class="sxs-lookup"><span data-stu-id="96b91-150">When using filters to qualify the **Path** parameter, you need to include a trailing asterisk (`*`) to indicate the contents of the path.</span></span>

<span data-ttu-id="96b91-151">Следующая команда возвращает содержимое всех `*.log` файлов в `C:\Temp` каталоге.</span><span class="sxs-lookup"><span data-stu-id="96b91-151">The following command gets the content of all `*.log` files in the `C:\Temp` directory.</span></span>

```powershell
Get-Content -Path C:\Temp\* -Filter *.log
```

### <span data-ttu-id="96b91-152">Пример 8. получение содержимого файла в виде массива байтов</span><span class="sxs-lookup"><span data-stu-id="96b91-152">Example 8: Get file contents as a byte array</span></span>

<span data-ttu-id="96b91-153">В этом примере показано, как получить содержимое файла в виде `[byte[]]` одного объекта.</span><span class="sxs-lookup"><span data-stu-id="96b91-153">This example demonstrates how to get the contents of a file as a `[byte[]]` as a single object.</span></span>

```powershell
$byteArray = Get-Content -Path C:\temp\test.txt -AsByteStream -Raw
Get-Member -InputObject $bytearray
```

```Output
   TypeName: System.Byte[]

Name           MemberType            Definition
----           ----------            ----------
Count          AliasProperty         Count = Length
Add            Method                int IList.Add(System.Object value)
```

<span data-ttu-id="96b91-154">Первая команда использует параметр **асбитестреам** для получения потока байтов из файла.</span><span class="sxs-lookup"><span data-stu-id="96b91-154">The first command uses the **AsByteStream** parameter to get the stream of bytes from the file.</span></span>
<span data-ttu-id="96b91-155">Параметр **RAW** гарантирует, что байты возвращаются в виде `[System.Byte[]]` .</span><span class="sxs-lookup"><span data-stu-id="96b91-155">The **Raw** parameter ensures that the bytes are returned as a `[System.Byte[]]`.</span></span> <span data-ttu-id="96b91-156">Если **необработанный** параметр отсутствовал, возвращаемое значение представляет собой поток байтов, интерпретируемый PowerShell как `[System.Object[]]` .</span><span class="sxs-lookup"><span data-stu-id="96b91-156">If the **Raw** parameter was absent, the return value is a stream of bytes, which is interpreted by PowerShell as `[System.Object[]]`.</span></span>

## <span data-ttu-id="96b91-157">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="96b91-157">PARAMETERS</span></span>

### <span data-ttu-id="96b91-158">-Path</span><span class="sxs-lookup"><span data-stu-id="96b91-158">-Path</span></span>

<span data-ttu-id="96b91-159">Указывает путь к элементу, где `Get-Content` получается содержимое.</span><span class="sxs-lookup"><span data-stu-id="96b91-159">Specifies the path to an item where `Get-Content` gets the content.</span></span> <span data-ttu-id="96b91-160">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="96b91-160">Wildcard characters are permitted.</span></span> <span data-ttu-id="96b91-161">Пути должны вести к элементам, а не к контейнерам.</span><span class="sxs-lookup"><span data-stu-id="96b91-161">The paths must be paths to items, not to containers.</span></span> <span data-ttu-id="96b91-162">Например, нужно указать путь к одному или нескольким файлам, а не путь к каталогу.</span><span class="sxs-lookup"><span data-stu-id="96b91-162">For example, you must specify a path to one or more files, not a path to a directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="96b91-163">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="96b91-163">-LiteralPath</span></span>

<span data-ttu-id="96b91-164">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="96b91-164">Specifies a path to one or more locations.</span></span> <span data-ttu-id="96b91-165">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="96b91-165">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="96b91-166">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="96b91-166">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="96b91-167">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="96b91-167">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="96b91-168">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="96b91-168">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="96b91-169">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="96b91-169">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="96b91-170">-ReadCount</span><span class="sxs-lookup"><span data-stu-id="96b91-170">-ReadCount</span></span>

<span data-ttu-id="96b91-171">Определяет количество строк содержимого, передаваемых по конвейеру за один раз.</span><span class="sxs-lookup"><span data-stu-id="96b91-171">Specifies how many lines of content are sent through the pipeline at a time.</span></span> <span data-ttu-id="96b91-172">Значение по умолчанию — 1.</span><span class="sxs-lookup"><span data-stu-id="96b91-172">The default value is 1.</span></span>
<span data-ttu-id="96b91-173">Если значение равно 0 (нулю), все содержимое отправляется за один раз.</span><span class="sxs-lookup"><span data-stu-id="96b91-173">A value of 0 (zero) sends all of the content at one time.</span></span>

<span data-ttu-id="96b91-174">Этот параметр не изменяет отображаемое содержимое, но влияет на время его отображения.</span><span class="sxs-lookup"><span data-stu-id="96b91-174">This parameter does not change the content displayed, but it does affect the time it takes to display the content.</span></span> <span data-ttu-id="96b91-175">При увеличении значения параметра **ReadCount** время, необходимое для возврата первой строки, возрастает, но общее время выполнения операции сокращается.</span><span class="sxs-lookup"><span data-stu-id="96b91-175">As the value of **ReadCount** increases, the time it takes to return the first line increases, but the total time for the operation decreases.</span></span> <span data-ttu-id="96b91-176">Это может сделать заметное различие в больших элементах.</span><span class="sxs-lookup"><span data-stu-id="96b91-176">This can make a perceptible difference in large items.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="96b91-177">-TotalCount</span><span class="sxs-lookup"><span data-stu-id="96b91-177">-TotalCount</span></span>

<span data-ttu-id="96b91-178">Указывает число строк от начала файла или другого элемента.</span><span class="sxs-lookup"><span data-stu-id="96b91-178">Specifies the number of lines from the beginning of a file or other item.</span></span> <span data-ttu-id="96b91-179">По умолчанию используется значение -1 (все строки).</span><span class="sxs-lookup"><span data-stu-id="96b91-179">The default is -1 (all lines).</span></span>

<span data-ttu-id="96b91-180">Можно использовать имя параметра **totalCount** или его псевдонимы, **First** или **head** .</span><span class="sxs-lookup"><span data-stu-id="96b91-180">You can use the **TotalCount** parameter name or its aliases, **First** or **Head** .</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases: First, Head

Required: False
Position: Named
Default value: -1
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="96b91-181">— Хвост</span><span class="sxs-lookup"><span data-stu-id="96b91-181">-Tail</span></span>

<span data-ttu-id="96b91-182">Указывает число строк из конца файла или другого элемента.</span><span class="sxs-lookup"><span data-stu-id="96b91-182">Specifies the number of lines from the end of a file or other item.</span></span> <span data-ttu-id="96b91-183">Можно использовать имя параметра **tail** или его псевдонима **Last** .</span><span class="sxs-lookup"><span data-stu-id="96b91-183">You can use the **Tail** parameter name or its alias, **Last** .</span></span> <span data-ttu-id="96b91-184">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="96b91-184">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: Last

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="96b91-185">-Filter</span><span class="sxs-lookup"><span data-stu-id="96b91-185">-Filter</span></span>

<span data-ttu-id="96b91-186">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="96b91-186">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="96b91-187">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="96b91-187">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="96b91-188">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="96b91-188">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="96b91-189">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="96b91-189">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="96b91-190">-Include</span><span class="sxs-lookup"><span data-stu-id="96b91-190">-Include</span></span>

<span data-ttu-id="96b91-191">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="96b91-191">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="96b91-192">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="96b91-192">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="96b91-193">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="96b91-193">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="96b91-194">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="96b91-194">Wildcard characters are permitted.</span></span> <span data-ttu-id="96b91-195">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="96b91-195">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="96b91-196">-Exclude</span><span class="sxs-lookup"><span data-stu-id="96b91-196">-Exclude</span></span>

<span data-ttu-id="96b91-197">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="96b91-197">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span>
<span data-ttu-id="96b91-198">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="96b91-198">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="96b91-199">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="96b91-199">Enter a path element or pattern, such as `*.txt`.</span></span>
<span data-ttu-id="96b91-200">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="96b91-200">Wildcard characters are permitted.</span></span>

<span data-ttu-id="96b91-201">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="96b91-201">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="96b91-202">-Force</span><span class="sxs-lookup"><span data-stu-id="96b91-202">-Force</span></span>

<span data-ttu-id="96b91-203">**Force** будет переопределять атрибут только для чтения или создавать каталоги для завершения пути к файлу.</span><span class="sxs-lookup"><span data-stu-id="96b91-203">**Force** will override a read-only attribute or create directories to complete a file path.</span></span> <span data-ttu-id="96b91-204">Параметр **Force** не пытается изменить разрешения файла или переопределить ограничения безопасности.</span><span class="sxs-lookup"><span data-stu-id="96b91-204">The **Force** parameter does not attempt to change file permissions or override security restrictions.</span></span>

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

### <span data-ttu-id="96b91-205">-Credential</span><span class="sxs-lookup"><span data-stu-id="96b91-205">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="96b91-206">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="96b91-206">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="96b91-207">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="96b91-207">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="96b91-208">-Delimiter</span><span class="sxs-lookup"><span data-stu-id="96b91-208">-Delimiter</span></span>

<span data-ttu-id="96b91-209">Задает разделитель, который `Get-Content` использует для разделения файла на объекты во время чтения.</span><span class="sxs-lookup"><span data-stu-id="96b91-209">Specifies the delimiter that `Get-Content` uses to divide the file into objects while it reads.</span></span> <span data-ttu-id="96b91-210">Значение по умолчанию — `\n` , символ конца строки.</span><span class="sxs-lookup"><span data-stu-id="96b91-210">The default is `\n`, the end-of-line character.</span></span> <span data-ttu-id="96b91-211">При чтении текстового файла `Get-Content` возвращает коллекцию строковых объектов, каждая из которых заканчивается символом конца строки.</span><span class="sxs-lookup"><span data-stu-id="96b91-211">When reading a text file, `Get-Content` returns a collection of string objects, each of which ends with an end-of-line character.</span></span> <span data-ttu-id="96b91-212">При вводе разделителя, который не существует в файле, `Get-Content` возвращает весь файл как отдельный объект без разделителей.</span><span class="sxs-lookup"><span data-stu-id="96b91-212">When you enter a delimiter that does not exist in the file, `Get-Content` returns the entire file as a single, undelimited object.</span></span>

<span data-ttu-id="96b91-213">С помощью этого параметра можно разделить большой файл на небольшие файлы, указав разделитель файлов в качестве разделителя.</span><span class="sxs-lookup"><span data-stu-id="96b91-213">You can use this parameter to split a large file into smaller files by specifying a file separator, as the delimiter.</span></span> <span data-ttu-id="96b91-214">Разделитель сохраняется (не удаляется) и становится последним элементом в каждом разделе файла.</span><span class="sxs-lookup"><span data-stu-id="96b91-214">The delimiter is preserved (not discarded) and becomes the last item in each file section.</span></span>

<span data-ttu-id="96b91-215">**Разделитель** — это динамический параметр, который поставщик **FileSystem** добавляет в `Get-Content` командлет.</span><span class="sxs-lookup"><span data-stu-id="96b91-215">**Delimiter** is a dynamic parameter that the **FileSystem** provider adds to the `Get-Content` cmdlet.</span></span> <span data-ttu-id="96b91-216">Этот параметр работает только на дисках с файловой системой.</span><span class="sxs-lookup"><span data-stu-id="96b91-216">This parameter works only in file system drives.</span></span>

> [!NOTE]
> <span data-ttu-id="96b91-217">В настоящее время, если значение параметра- **разделителя** является пустой строкой, `Get-Content` не возвращает ничего.</span><span class="sxs-lookup"><span data-stu-id="96b91-217">Currently, when the value of the **Delimiter** parameter is an empty string, `Get-Content` does not return anything.</span></span> <span data-ttu-id="96b91-218">Это известная проблема.</span><span class="sxs-lookup"><span data-stu-id="96b91-218">This is a known issue.</span></span> <span data-ttu-id="96b91-219">Для принудительного `Get-Content` возврата всего файла в виде одной строки с неограниченным разделителем.</span><span class="sxs-lookup"><span data-stu-id="96b91-219">To force `Get-Content` to return the entire file as a single, undelimited string.</span></span> <span data-ttu-id="96b91-220">Введите значение, которое не существует в файле.</span><span class="sxs-lookup"><span data-stu-id="96b91-220">Enter a value that does not exist in the file.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: End-of-line character
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="96b91-221">-Wait</span><span class="sxs-lookup"><span data-stu-id="96b91-221">-Wait</span></span>

<span data-ttu-id="96b91-222">Сохраняет файл открытым после вывода всех существующих строк.</span><span class="sxs-lookup"><span data-stu-id="96b91-222">Keeps the file open after all existing lines have been output.</span></span> <span data-ttu-id="96b91-223">Во время ожидания `Get-Content` проверяет файл один раз в секунду и выводит новые строки, если они есть.</span><span class="sxs-lookup"><span data-stu-id="96b91-223">While waiting, `Get-Content` checks the file once each second and outputs new lines if present.</span></span> <span data-ttu-id="96b91-224">Можно прервать **Ожидание** , нажав клавиши **CTRL + C** .</span><span class="sxs-lookup"><span data-stu-id="96b91-224">You can interrupt **Wait** by pressing **CTRL+C** .</span></span> <span data-ttu-id="96b91-225">Ожидание также завершается, если файл удаляется, в этом случае сообщается о неустранимой ошибке.</span><span class="sxs-lookup"><span data-stu-id="96b91-225">Waiting also ends if the file gets deleted, in which case a non-terminating error is reported.</span></span>

<span data-ttu-id="96b91-226">**Wait** — это динамический параметр, который поставщик FileSystem добавляет в `Get-Content` командлет.</span><span class="sxs-lookup"><span data-stu-id="96b91-226">**Wait** is a dynamic parameter that the FileSystem provider adds to the `Get-Content` cmdlet.</span></span> <span data-ttu-id="96b91-227">Этот параметр работает только на дисках с файловой системой.</span><span class="sxs-lookup"><span data-stu-id="96b91-227">This parameter works only in file system drives.</span></span> <span data-ttu-id="96b91-228">**Wait** не может сочетаться с **RAW** .</span><span class="sxs-lookup"><span data-stu-id="96b91-228">**Wait** cannot be combined with **Raw** .</span></span>

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

### <span data-ttu-id="96b91-229">-RAW</span><span class="sxs-lookup"><span data-stu-id="96b91-229">-Raw</span></span>

<span data-ttu-id="96b91-230">Игнорирует символы новой строки и возвращает все содержимое файла в одной строке с сохраненными символами новой строки.</span><span class="sxs-lookup"><span data-stu-id="96b91-230">Ignores newline characters and returns the entire contents of a file in one string with the newlines preserved.</span></span> <span data-ttu-id="96b91-231">По умолчанию символы новой строки в файле используются в качестве разделителей для разделения входных данных на массив строк.</span><span class="sxs-lookup"><span data-stu-id="96b91-231">By default, newline characters in a file are used as delimiters to separate the input into an array of strings.</span></span> <span data-ttu-id="96b91-232">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="96b91-232">This parameter was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="96b91-233">**RAW** — это динамический параметр, который поставщик **FileSystem** добавляет в `Get-Content` командлет. Этот параметр работает только на дисках файловой системы.</span><span class="sxs-lookup"><span data-stu-id="96b91-233">**Raw** is a dynamic parameter that the **FileSystem** provider adds to the `Get-Content` cmdlet This parameter works only in file system drives.</span></span>

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

### <span data-ttu-id="96b91-234">-Encoding</span><span class="sxs-lookup"><span data-stu-id="96b91-234">-Encoding</span></span>

<span data-ttu-id="96b91-235">Указывает тип кодировки для целевого файла.</span><span class="sxs-lookup"><span data-stu-id="96b91-235">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="96b91-236">Значение по умолчанию — `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="96b91-236">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="96b91-237">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="96b91-237">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="96b91-238">`ascii`: Использует кодировку для набора символов ASCII (7-разрядных).</span><span class="sxs-lookup"><span data-stu-id="96b91-238">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="96b91-239">`bigendianunicode`: Кодируется в формате UTF-16 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="96b91-239">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="96b91-240">`oem`: Использует кодировку по умолчанию для программ MS-DOS и консолей.</span><span class="sxs-lookup"><span data-stu-id="96b91-240">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="96b91-241">`unicode`: Кодируется в формате UTF-16 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="96b91-241">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="96b91-242">`utf7`: Кодируется в формате UTF-7.</span><span class="sxs-lookup"><span data-stu-id="96b91-242">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="96b91-243">`utf8`: Кодируется в формате UTF-8.</span><span class="sxs-lookup"><span data-stu-id="96b91-243">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="96b91-244">`utf8BOM`: Кодирует в формате UTF-8 с меткой порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="96b91-244">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="96b91-245">`utf8NoBOM`: Кодирует в формате UTF-8 без метки порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="96b91-245">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="96b91-246">`utf32`: Кодируется в формате UTF-32.</span><span class="sxs-lookup"><span data-stu-id="96b91-246">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="96b91-247">Кодирование — это динамический параметр, который поставщик **FileSystem** добавляет в `Get-Content` командлет.</span><span class="sxs-lookup"><span data-stu-id="96b91-247">Encoding is a dynamic parameter that the **FileSystem** provider adds to the `Get-Content` cmdlet.</span></span>
<span data-ttu-id="96b91-248">Этот параметр доступен только в дисках файловой системы.</span><span class="sxs-lookup"><span data-stu-id="96b91-248">This parameter is available only in file system drives.</span></span>

<span data-ttu-id="96b91-249">При чтении из двоичных файлов и записи в них используйте параметр **асбитестреам** и значение 0 для параметра **readCount** .</span><span class="sxs-lookup"><span data-stu-id="96b91-249">When reading from and writing to binary files, use the **AsByteStream** parameter and a value of 0 for the **ReadCount** parameter.</span></span> <span data-ttu-id="96b91-250">Значение **readCount** , равное 0, считывает весь файл в одной операции чтения.</span><span class="sxs-lookup"><span data-stu-id="96b91-250">A **ReadCount** value of 0 reads the entire file in a single read operation.</span></span> <span data-ttu-id="96b91-251">Значение **readCount** по умолчанию, равное 1, считывает один байт в каждой операции чтения и преобразует каждый байт в отдельный объект, что приводит к ошибкам при использовании `Set-Content` командлета для записи байтов в файл, если не используется параметр **асбитестреам** .</span><span class="sxs-lookup"><span data-stu-id="96b91-251">The default **ReadCount** value, 1, reads one byte in each read operation and converts each byte into a separate object, which causes errors when you use the `Set-Content` cmdlet to write the bytes to a file unless you use **AsByteStream** parameter.</span></span>

<span data-ttu-id="96b91-252">Начиная с PowerShell 6,2, параметр **кодировки** также разрешает числовые идентификаторы зарегистрированных кодовых страниц (например `-Encoding 1251` ,) или строковых имен зарегистрированных кодовых страниц (например `-Encoding "windows-1251"` ,).</span><span class="sxs-lookup"><span data-stu-id="96b91-252">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="96b91-253">Дополнительные сведения см. в документации .NET по [кодированию. codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="96b91-253">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

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

### <span data-ttu-id="96b91-254">-Stream</span><span class="sxs-lookup"><span data-stu-id="96b91-254">-Stream</span></span>

<span data-ttu-id="96b91-255">Возвращает содержимое указанного альтернативного файлового потока NTFS из файла.</span><span class="sxs-lookup"><span data-stu-id="96b91-255">Gets the contents of the specified alternate NTFS file stream from the file.</span></span> <span data-ttu-id="96b91-256">Введите имя потока.</span><span class="sxs-lookup"><span data-stu-id="96b91-256">Enter the stream name.</span></span>
<span data-ttu-id="96b91-257">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="96b91-257">Wildcards are not supported.</span></span>

<span data-ttu-id="96b91-258">**Stream** — это динамический параметр, который поставщик **FileSystem** добавляет в `Get-Content` командлет.</span><span class="sxs-lookup"><span data-stu-id="96b91-258">**Stream** is a dynamic parameter that the **FileSystem** provider adds to the `Get-Content` cmdlet.</span></span>
<span data-ttu-id="96b91-259">Этот параметр работает только в дисках файловой системы в системах Windows.</span><span class="sxs-lookup"><span data-stu-id="96b91-259">This parameter works only in file system drives on Windows systems.</span></span> <span data-ttu-id="96b91-260">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="96b91-260">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="96b91-261">-Асбитестреам</span><span class="sxs-lookup"><span data-stu-id="96b91-261">-AsByteStream</span></span>

<span data-ttu-id="96b91-262">Указывает, что содержимое должно считываться как поток байтов.</span><span class="sxs-lookup"><span data-stu-id="96b91-262">Specifies that the content should be read as a stream of bytes.</span></span> <span data-ttu-id="96b91-263">Параметр **асбитестреам** появился в Windows PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="96b91-263">The **AsByteStream** parameter was introduced in Windows PowerShell 6.0.</span></span>

<span data-ttu-id="96b91-264">При использовании параметра **асбитестреам** с параметром **Encoding** возникает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="96b91-264">A warning occurs when you use the **AsByteStream** parameter with the **Encoding** parameter.</span></span> <span data-ttu-id="96b91-265">Параметр **асбитестреам** игнорирует любую кодировку, и выходные данные возвращаются в виде потока байтов.</span><span class="sxs-lookup"><span data-stu-id="96b91-265">The **AsByteStream** parameter ignores any encoding and the output is returned as a stream of bytes.</span></span>

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

### <span data-ttu-id="96b91-266">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="96b91-266">CommonParameters</span></span>

<span data-ttu-id="96b91-267">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="96b91-267">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="96b91-268">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="96b91-268">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="96b91-269">Входные данные</span><span class="sxs-lookup"><span data-stu-id="96b91-269">INPUTS</span></span>

### <span data-ttu-id="96b91-270">System.Int64, System.String[], System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="96b91-270">System.Int64, System.String[], System.Management.Automation.PSCredential</span></span>

<span data-ttu-id="96b91-271">Количество операций чтения, общее число, пути или учетные данные можно передать в `Get-Content` .</span><span class="sxs-lookup"><span data-stu-id="96b91-271">You can pipe the read count, total count, paths, or credentials to `Get-Content`.</span></span>

## <span data-ttu-id="96b91-272">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="96b91-272">OUTPUTS</span></span>

### <span data-ttu-id="96b91-273">System. Byte, System. String</span><span class="sxs-lookup"><span data-stu-id="96b91-273">System.Byte, System.String</span></span>

<span data-ttu-id="96b91-274">`Get-Content` Возвращает строки или байты.</span><span class="sxs-lookup"><span data-stu-id="96b91-274">`Get-Content` returns strings or bytes.</span></span> <span data-ttu-id="96b91-275">Тип выходных данных зависит от типа содержимого, указанного в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="96b91-275">The output type depends upon the type of content that you specify as input.</span></span>

## <span data-ttu-id="96b91-276">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="96b91-276">NOTES</span></span>

<span data-ttu-id="96b91-277">`Get-Content`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="96b91-277">The `Get-Content` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="96b91-278">Чтобы получить поставщиков в сеансе, используйте `Get-PSProvider` командлет.</span><span class="sxs-lookup"><span data-stu-id="96b91-278">To get the providers in your session, use the `Get-PSProvider` cmdlet.</span></span> <span data-ttu-id="96b91-279">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="96b91-279">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="96b91-280">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="96b91-280">RELATED LINKS</span></span>

[<span data-ttu-id="96b91-281">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="96b91-281">about_Automatic_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="96b91-282">about_Providers</span><span class="sxs-lookup"><span data-stu-id="96b91-282">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="96b91-283">Add-Content</span><span class="sxs-lookup"><span data-stu-id="96b91-283">Add-Content</span></span>](Add-Content.md)

[<span data-ttu-id="96b91-284">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="96b91-284">Clear-Content</span></span>](Clear-Content.md)

[<span data-ttu-id="96b91-285">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="96b91-285">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="96b91-286">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="96b91-286">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="96b91-287">Set-Content</span><span class="sxs-lookup"><span data-stu-id="96b91-287">Set-Content</span></span>](Set-Content.md)