---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-content?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Content
ms.openlocfilehash: f8072e9c93d368fd9ebe49459199d21480031275
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225949"
---
# <span data-ttu-id="3dc73-103">Set-Content</span><span class="sxs-lookup"><span data-stu-id="3dc73-103">Set-Content</span></span>

## <span data-ttu-id="3dc73-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3dc73-104">SYNOPSIS</span></span>
<span data-ttu-id="3dc73-105">Записывает новое содержимое или заменяет существующее содержимое в файле.</span><span class="sxs-lookup"><span data-stu-id="3dc73-105">Writes new content or replaces existing content in a file.</span></span>

## <span data-ttu-id="3dc73-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3dc73-106">SYNTAX</span></span>

### <span data-ttu-id="3dc73-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="3dc73-107">Path (Default)</span></span>

```
Set-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>]
 [-WhatIf] [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

### <span data-ttu-id="3dc73-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="3dc73-108">LiteralPath</span></span>

```
Set-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>]
 [-WhatIf] [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

## <span data-ttu-id="3dc73-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3dc73-109">DESCRIPTION</span></span>

<span data-ttu-id="3dc73-110">`Set-Content` — Это командлет обработки строк, который записывает новое содержимое или заменяет содержимое в файле.</span><span class="sxs-lookup"><span data-stu-id="3dc73-110">`Set-Content` is a string-processing cmdlet that writes new content or replaces the content in a file.</span></span> <span data-ttu-id="3dc73-111">`Set-Content` Заменяет существующее содержимое и отличается от `Add-Content` командлета, который добавляет содержимое в файл.</span><span class="sxs-lookup"><span data-stu-id="3dc73-111">`Set-Content` replaces the existing content and differs from the `Add-Content` cmdlet that appends content to a file.</span></span> <span data-ttu-id="3dc73-112">Чтобы отправить содержимое в `Set-Content` , можно использовать параметр **value** в командной строке или отправить содержимое через конвейер.</span><span class="sxs-lookup"><span data-stu-id="3dc73-112">To send content to `Set-Content` you can use the **Value** parameter on the command line or send content through the pipeline.</span></span>

<span data-ttu-id="3dc73-113">Если необходимо создать файлы или каталоги для следующих примеров, см. раздел [New-Item](New-Item.md).</span><span class="sxs-lookup"><span data-stu-id="3dc73-113">If you need to create files or directories for the following examples, see [New-Item](New-Item.md).</span></span>

## <span data-ttu-id="3dc73-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="3dc73-114">EXAMPLES</span></span>

### <span data-ttu-id="3dc73-115">Пример 1. Замена содержимого нескольких файлов в каталоге</span><span class="sxs-lookup"><span data-stu-id="3dc73-115">Example 1: Replace the contents of multiple files in a directory</span></span>

<span data-ttu-id="3dc73-116">Этот пример заменяет содержимое для нескольких файлов в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3dc73-116">This example replaces the content for multiple files in the current directory.</span></span>

```powershell
Get-ChildItem -Path .\Test*.txt
```

```Output
Test1.txt
Test2.txt
Test3.txt
```

```powershell
Set-Content -Path .\Test*.txt -Value 'Hello, World'
Get-Content -Path .\Test*.txt
```

```Output
Hello, World
Hello, World
Hello, World
```

<span data-ttu-id="3dc73-117">`Get-ChildItem`Командлет использует параметр **path** для вывода файлов **. txt** , начинающихся с `Test*` в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3dc73-117">The `Get-ChildItem` cmdlet uses the **Path** parameter to list **.txt** files that begin with `Test*` in the current directory.</span></span> <span data-ttu-id="3dc73-118">`Set-Content`Командлет использует параметр **path** для указания `Test*.txt` файлов.</span><span class="sxs-lookup"><span data-stu-id="3dc73-118">The `Set-Content` cmdlet uses the **Path** parameter to specify the `Test*.txt` files.</span></span> <span data-ttu-id="3dc73-119">Параметр **value** предоставляет текстовую строку **Hello, World** , заменяющую существующее содержимое в каждом файле.</span><span class="sxs-lookup"><span data-stu-id="3dc73-119">The **Value** parameter provides the text string **Hello, World** that replaces the existing content in each file.</span></span> <span data-ttu-id="3dc73-120">`Get-Content`Командлет использует параметр **path** для указания `Test*.txt` файлов и отображает содержимое каждого файла в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3dc73-120">The `Get-Content` cmdlet uses the **Path** parameter to specify the `Test*.txt` files and displays each file's content in the PowerShell console.</span></span>

### <span data-ttu-id="3dc73-121">Пример 2. Создание нового файла и запись содержимого</span><span class="sxs-lookup"><span data-stu-id="3dc73-121">Example 2: Create a new file and write content</span></span>

<span data-ttu-id="3dc73-122">В этом примере создается новый файл и записывается текущая дата и время в файл.</span><span class="sxs-lookup"><span data-stu-id="3dc73-122">This example creates a new file and writes the current date and time to the file.</span></span>

```powershell
Set-Content -Path .\DateTime.txt -Value (Get-Date)
Get-Content -Path .\DateTime.txt
```

```Output
1/30/2019 09:55:08
```

<span data-ttu-id="3dc73-123">`Set-Content` использует параметры **path** и **value** для создания нового файла с именем **DateTime.txt** в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3dc73-123">`Set-Content` uses the **Path** and **Value** parameters to create a new file named **DateTime.txt** in the current directory.</span></span> <span data-ttu-id="3dc73-124">Параметр **value** используется `Get-Date` для получения текущих даты и времени.</span><span class="sxs-lookup"><span data-stu-id="3dc73-124">The **Value** parameter uses `Get-Date` to get the current date and time.</span></span>
<span data-ttu-id="3dc73-125">`Set-Content` Записывает объект **DateTime** в файл в виде строки.</span><span class="sxs-lookup"><span data-stu-id="3dc73-125">`Set-Content` writes the **DateTime** object to the file as a string.</span></span> <span data-ttu-id="3dc73-126">`Get-Content`Командлет использует параметр **path** для вывода содержимого **DateTime.txt** в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3dc73-126">The `Get-Content` cmdlet uses the **Path** parameter to display the content of **DateTime.txt** in the PowerShell console.</span></span>

### <span data-ttu-id="3dc73-127">Пример 3. Замена текста в файле</span><span class="sxs-lookup"><span data-stu-id="3dc73-127">Example 3: Replace text in a file</span></span>

<span data-ttu-id="3dc73-128">Эта команда заменяет все экземпляры Word в существующем файле.</span><span class="sxs-lookup"><span data-stu-id="3dc73-128">This command replaces all instances of word within an existing file.</span></span>

```powershell
Get-Content -Path .\Notice.txt
```

```Output
Warning
Replace Warning with a new word.
The word Warning was replaced.
```

```powershell
(Get-Content -Path .\Notice.txt) |
    ForEach-Object {$_ -Replace 'Warning', 'Caution'} |
        Set-Content -Path .\Notice.txt
Get-Content -Path .\Notice.txt
```

```Output
Caution
Replace Caution with a new word.
The word Caution was replaced.
```

<span data-ttu-id="3dc73-129">`Get-Content`Командлет использует параметр **path** для указания файла **Notice.txt** в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3dc73-129">The `Get-Content` cmdlet uses the **Path** parameter to specify the **Notice.txt** file in the current directory.</span></span> <span data-ttu-id="3dc73-130">`Get-Content`Команда заключена в круглые скобки, чтобы команда закончится перед отправкой конвейера.</span><span class="sxs-lookup"><span data-stu-id="3dc73-130">The `Get-Content` command is wrapped with parentheses so that the command finishes before being sent down the pipeline.</span></span>

<span data-ttu-id="3dc73-131">Содержимое файла **Notice.txt** отправляется в командлет по конвейеру `ForEach-Object` .</span><span class="sxs-lookup"><span data-stu-id="3dc73-131">The contents of the **Notice.txt** file are sent down the pipeline to the `ForEach-Object` cmdlet.</span></span>
<span data-ttu-id="3dc73-132">`ForEach-Object` использует автоматическую переменную `$_` и заменяет каждое вхождение **предупреждения** с **осторожностью**.</span><span class="sxs-lookup"><span data-stu-id="3dc73-132">`ForEach-Object` uses the automatic variable `$_` and replaces each occurrence of **Warning** with **Caution**.</span></span> <span data-ttu-id="3dc73-133">Объекты отправляются по конвейеру в `Set-Content` командлет.</span><span class="sxs-lookup"><span data-stu-id="3dc73-133">The objects are sent down the pipeline to the `Set-Content` cmdlet.</span></span> <span data-ttu-id="3dc73-134">`Set-Content` использует параметр **path** для указания файла **Notice.txt** и записи обновленного содержимого в файл.</span><span class="sxs-lookup"><span data-stu-id="3dc73-134">`Set-Content` uses the **Path** parameter to specify the **Notice.txt** file and writes the updated content to the file.</span></span>

<span data-ttu-id="3dc73-135">Последний `Get-Content` командлет отображает обновленное содержимое файла в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3dc73-135">The last `Get-Content` cmdlet displays the updated file content in the PowerShell console.</span></span>

### <span data-ttu-id="3dc73-136">Пример 4. Использование фильтров с Set-Content</span><span class="sxs-lookup"><span data-stu-id="3dc73-136">Example 4: Use Filters with Set-Content</span></span>

<span data-ttu-id="3dc73-137">Можно указать фильтр для `Set-Content` командлета.</span><span class="sxs-lookup"><span data-stu-id="3dc73-137">You can specify a filter to the `Set-Content` cmdlet.</span></span> <span data-ttu-id="3dc73-138">При использовании фильтров для уточнения параметра **path** необходимо включить конечную звездочку ( `*` ), чтобы указать содержимое пути.</span><span class="sxs-lookup"><span data-stu-id="3dc73-138">When using filters to qualify the **Path** parameter, you need to include a trailing asterisk (`*`) to indicate the contents of the path.</span></span>

<span data-ttu-id="3dc73-139">Следующая команда задает для содержимого всех `*.txt` файлов в `C:\Temp` каталоге пустое **значение** .</span><span class="sxs-lookup"><span data-stu-id="3dc73-139">The following command set the content all `*.txt` files in the `C:\Temp` directory to the **Value** empty.</span></span>

```powershell
Set-Content -Path C:\Temp\* -Filter *.txt -Value "Empty"
```

## <span data-ttu-id="3dc73-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3dc73-140">PARAMETERS</span></span>

### <span data-ttu-id="3dc73-141">-Асбитестреам</span><span class="sxs-lookup"><span data-stu-id="3dc73-141">-AsByteStream</span></span>

<span data-ttu-id="3dc73-142">Указывает, что содержимое должно считываться как поток байтов.</span><span class="sxs-lookup"><span data-stu-id="3dc73-142">Specifies that the content should be read as a stream of bytes.</span></span> <span data-ttu-id="3dc73-143">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="3dc73-143">This parameter was introduced in PowerShell 6.0.</span></span>

<span data-ttu-id="3dc73-144">При использовании параметра **асбитестреам** с параметром **Encoding** возникает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="3dc73-144">A warning occurs when you use the **AsByteStream** parameter with the **Encoding** parameter.</span></span> <span data-ttu-id="3dc73-145">Параметр **асбитестреам** игнорирует любую кодировку, и выходные данные возвращаются в виде потока байтов.</span><span class="sxs-lookup"><span data-stu-id="3dc73-145">The **AsByteStream** parameter ignores any encoding and the output is returned as a stream of bytes.</span></span>

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

### <span data-ttu-id="3dc73-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="3dc73-146">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="3dc73-147">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3dc73-147">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="3dc73-148">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="3dc73-148">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3dc73-149">-Encoding</span><span class="sxs-lookup"><span data-stu-id="3dc73-149">-Encoding</span></span>

<span data-ttu-id="3dc73-150">Указывает тип кодировки для целевого файла.</span><span class="sxs-lookup"><span data-stu-id="3dc73-150">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="3dc73-151">Значение по умолчанию — `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="3dc73-151">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="3dc73-152">Кодирование — это динамический параметр, к которому добавляется поставщик FileSystem `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="3dc73-152">Encoding is a dynamic parameter that the FileSystem provider adds to `Set-Content`.</span></span> <span data-ttu-id="3dc73-153">Этот параметр работает только на дисках с файловой системой.</span><span class="sxs-lookup"><span data-stu-id="3dc73-153">This parameter works only in file system drives.</span></span>

<span data-ttu-id="3dc73-154">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="3dc73-154">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="3dc73-155">`ascii`: Использует кодировку для набора символов ASCII (7-разрядных).</span><span class="sxs-lookup"><span data-stu-id="3dc73-155">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="3dc73-156">`bigendianunicode`: Кодируется в формате UTF-16 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="3dc73-156">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="3dc73-157">`oem`: Использует кодировку по умолчанию для программ MS-DOS и консолей.</span><span class="sxs-lookup"><span data-stu-id="3dc73-157">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="3dc73-158">`unicode`: Кодируется в формате UTF-16 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="3dc73-158">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="3dc73-159">`utf7`: Кодируется в формате UTF-7.</span><span class="sxs-lookup"><span data-stu-id="3dc73-159">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="3dc73-160">`utf8`: Кодируется в формате UTF-8.</span><span class="sxs-lookup"><span data-stu-id="3dc73-160">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="3dc73-161">`utf8BOM`: Кодирует в формате UTF-8 с меткой порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="3dc73-161">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="3dc73-162">`utf8NoBOM`: Кодирует в формате UTF-8 без метки порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="3dc73-162">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="3dc73-163">`utf32`: Кодируется в формате UTF-32.</span><span class="sxs-lookup"><span data-stu-id="3dc73-163">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="3dc73-164">Начиная с PowerShell 6,2, параметр **кодировки** также разрешает числовые идентификаторы зарегистрированных кодовых страниц (например `-Encoding 1251` ,) или строковых имен зарегистрированных кодовых страниц (например `-Encoding "windows-1251"` ,).</span><span class="sxs-lookup"><span data-stu-id="3dc73-164">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="3dc73-165">Дополнительные сведения см. в документации .NET по [кодированию. codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="3dc73-165">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

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

### <span data-ttu-id="3dc73-166">-Exclude</span><span class="sxs-lookup"><span data-stu-id="3dc73-166">-Exclude</span></span>

<span data-ttu-id="3dc73-167">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="3dc73-167">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="3dc73-168">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="3dc73-168">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="3dc73-169">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="3dc73-169">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="3dc73-170">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="3dc73-170">Wildcard characters are permitted.</span></span> <span data-ttu-id="3dc73-171">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="3dc73-171">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="3dc73-172">-Filter</span><span class="sxs-lookup"><span data-stu-id="3dc73-172">-Filter</span></span>

<span data-ttu-id="3dc73-173">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="3dc73-173">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="3dc73-174">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="3dc73-174">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="3dc73-175">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="3dc73-175">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="3dc73-176">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="3dc73-176">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="3dc73-177">-Force</span><span class="sxs-lookup"><span data-stu-id="3dc73-177">-Force</span></span>

<span data-ttu-id="3dc73-178">Заставляет командлет задать содержимое файла, даже если он доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="3dc73-178">Forces the cmdlet to set the contents of a file, even if the file is read-only.</span></span> <span data-ttu-id="3dc73-179">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="3dc73-179">Implementation varies from provider to provider.</span></span> <span data-ttu-id="3dc73-180">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="3dc73-180">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
<span data-ttu-id="3dc73-181">Параметр **Force** не переопределяет ограничения безопасности.</span><span class="sxs-lookup"><span data-stu-id="3dc73-181">The **Force** parameter does not override security restrictions.</span></span>

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

### <span data-ttu-id="3dc73-182">-Include</span><span class="sxs-lookup"><span data-stu-id="3dc73-182">-Include</span></span>

<span data-ttu-id="3dc73-183">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="3dc73-183">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="3dc73-184">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="3dc73-184">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="3dc73-185">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="3dc73-185">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="3dc73-186">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="3dc73-186">Wildcard characters are permitted.</span></span> <span data-ttu-id="3dc73-187">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="3dc73-187">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="3dc73-188">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="3dc73-188">-LiteralPath</span></span>

<span data-ttu-id="3dc73-189">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="3dc73-189">Specifies a path to one or more locations.</span></span> <span data-ttu-id="3dc73-190">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="3dc73-190">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="3dc73-191">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="3dc73-191">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="3dc73-192">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="3dc73-192">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="3dc73-193">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="3dc73-193">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="3dc73-194">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="3dc73-194">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="3dc73-195">-Новая строка</span><span class="sxs-lookup"><span data-stu-id="3dc73-195">-NoNewline</span></span>

<span data-ttu-id="3dc73-196">Строковые представления входных объектов сцепляются для формирования выходных данных.</span><span class="sxs-lookup"><span data-stu-id="3dc73-196">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="3dc73-197">Между выходными строками не вставляются пробелы и символы новой строки.</span><span class="sxs-lookup"><span data-stu-id="3dc73-197">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="3dc73-198">После последней выходной строки не добавляется новая строка.</span><span class="sxs-lookup"><span data-stu-id="3dc73-198">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="3dc73-199">-PassThru</span><span class="sxs-lookup"><span data-stu-id="3dc73-199">-PassThru</span></span>

<span data-ttu-id="3dc73-200">Возвращает объект, представляющий содержимое.</span><span class="sxs-lookup"><span data-stu-id="3dc73-200">Returns an object that represents the content.</span></span> <span data-ttu-id="3dc73-201">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="3dc73-201">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="3dc73-202">-Path</span><span class="sxs-lookup"><span data-stu-id="3dc73-202">-Path</span></span>

<span data-ttu-id="3dc73-203">Указывает путь к элементу, который получает содержимое.</span><span class="sxs-lookup"><span data-stu-id="3dc73-203">Specifies the path of the item that receives the content.</span></span>
<span data-ttu-id="3dc73-204">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="3dc73-204">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="3dc73-205">-Stream</span><span class="sxs-lookup"><span data-stu-id="3dc73-205">-Stream</span></span>

<span data-ttu-id="3dc73-206">Указывает альтернативный поток данных для содержимого.</span><span class="sxs-lookup"><span data-stu-id="3dc73-206">Specifies an alternative data stream for content.</span></span> <span data-ttu-id="3dc73-207">Если поток не существует, этот командлет создаст его.</span><span class="sxs-lookup"><span data-stu-id="3dc73-207">If the stream does not exist, this cmdlet creates it.</span></span> <span data-ttu-id="3dc73-208">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="3dc73-208">Wildcard characters are not supported.</span></span>

<span data-ttu-id="3dc73-209">**Stream** — это динамический параметр, к которому добавляется поставщик **FileSystem** `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="3dc73-209">**Stream** is a dynamic parameter that the **FileSystem** provider adds to `Set-Content`.</span></span> <span data-ttu-id="3dc73-210">Этот параметр работает только на дисках с файловой системой.</span><span class="sxs-lookup"><span data-stu-id="3dc73-210">This parameter works only in file system drives.</span></span>

<span data-ttu-id="3dc73-211">`Set-Content`С помощью командлета можно изменить содержимое **зоны.** альтернативный поток данных идентификатора.</span><span class="sxs-lookup"><span data-stu-id="3dc73-211">You can use the `Set-Content` cmdlet to change the content of the **Zone.Identifier** alternate data stream.</span></span> <span data-ttu-id="3dc73-212">Однако не рекомендуется использовать этот способ для устранения проверок безопасности, блокирующих файлы, загружаемые из Интернета.</span><span class="sxs-lookup"><span data-stu-id="3dc73-212">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="3dc73-213">Если вы убедитесь, что скачанный файл является надежным, используйте `Unblock-File` командлет.</span><span class="sxs-lookup"><span data-stu-id="3dc73-213">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="3dc73-214">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="3dc73-214">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="3dc73-215">-Value</span><span class="sxs-lookup"><span data-stu-id="3dc73-215">-Value</span></span>

<span data-ttu-id="3dc73-216">Указывает новое содержимое для элемента.</span><span class="sxs-lookup"><span data-stu-id="3dc73-216">Specifies the new content for the item.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="3dc73-217">-Confirm</span><span class="sxs-lookup"><span data-stu-id="3dc73-217">-Confirm</span></span>

<span data-ttu-id="3dc73-218">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="3dc73-218">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3dc73-219">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="3dc73-219">-WhatIf</span></span>

<span data-ttu-id="3dc73-220">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="3dc73-220">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="3dc73-221">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="3dc73-221">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3dc73-222">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3dc73-222">CommonParameters</span></span>

<span data-ttu-id="3dc73-223">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="3dc73-223">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span>
<span data-ttu-id="3dc73-224">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="3dc73-224">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="3dc73-225">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3dc73-225">INPUTS</span></span>

### <span data-ttu-id="3dc73-226">System.Object</span><span class="sxs-lookup"><span data-stu-id="3dc73-226">System.Object</span></span>

<span data-ttu-id="3dc73-227">Объект, содержащий новое значение для элемента, можно передать по конвейеру `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="3dc73-227">You can pipe an object that contains the new value for the item to `Set-Content`.</span></span>

## <span data-ttu-id="3dc73-228">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3dc73-228">OUTPUTS</span></span>

### <span data-ttu-id="3dc73-229">Нет или System.String</span><span class="sxs-lookup"><span data-stu-id="3dc73-229">None or System.String</span></span>

<span data-ttu-id="3dc73-230">При использовании параметра **PassThru** `Set-Content` создает объект **System. String** , представляющий содержимое.</span><span class="sxs-lookup"><span data-stu-id="3dc73-230">When you use the **PassThru** parameter, `Set-Content` generates a **System.String** object that represents the content.</span></span> <span data-ttu-id="3dc73-231">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="3dc73-231">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="3dc73-232">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3dc73-232">NOTES</span></span>

- <span data-ttu-id="3dc73-233">Также можно ссылаться `Set-Content` по встроенному псевдониму `sc` .</span><span class="sxs-lookup"><span data-stu-id="3dc73-233">You can also refer to `Set-Content` by its built-in alias, `sc`.</span></span>
  <span data-ttu-id="3dc73-234">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="3dc73-234">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="3dc73-235">`Set-Content` предназначен для обработки строк.</span><span class="sxs-lookup"><span data-stu-id="3dc73-235">`Set-Content` is designed for string processing.</span></span> <span data-ttu-id="3dc73-236">При передаче нестроковых объектов в `Set-Content` объект преобразуется в строку перед записью.</span><span class="sxs-lookup"><span data-stu-id="3dc73-236">If you pipe non-string objects to `Set-Content`, it converts the object to a string before writing it.</span></span> <span data-ttu-id="3dc73-237">Для записи объектов в файлы используйте `Out-File` .</span><span class="sxs-lookup"><span data-stu-id="3dc73-237">To write objects to files, use `Out-File`.</span></span>
- <span data-ttu-id="3dc73-238">`Set-Content`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="3dc73-238">The `Set-Content` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="3dc73-239">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PsProvider`.</span><span class="sxs-lookup"><span data-stu-id="3dc73-239">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="3dc73-240">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="3dc73-240">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="3dc73-241">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3dc73-241">RELATED LINKS</span></span>

[<span data-ttu-id="3dc73-242">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="3dc73-242">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="3dc73-243">about_Automatic_Variables. md</span><span class="sxs-lookup"><span data-stu-id="3dc73-243">about_Automatic_Variables.md</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="3dc73-244">about_Providers</span><span class="sxs-lookup"><span data-stu-id="3dc73-244">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="3dc73-245">Add-Content</span><span class="sxs-lookup"><span data-stu-id="3dc73-245">Add-Content</span></span>](Add-Content.md)

[<span data-ttu-id="3dc73-246">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="3dc73-246">Clear-Content</span></span>](Clear-Content.md)

[<span data-ttu-id="3dc73-247">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="3dc73-247">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="3dc73-248">Get-Content</span><span class="sxs-lookup"><span data-stu-id="3dc73-248">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="3dc73-249">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="3dc73-249">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="3dc73-250">New-Item</span><span class="sxs-lookup"><span data-stu-id="3dc73-250">New-Item</span></span>](New-Item.md)
