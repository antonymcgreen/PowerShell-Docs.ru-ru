---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-content?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Content
ms.openlocfilehash: d21765541fb849aed8dc37895c167c0ea34486a3
ms.sourcegitcommit: bf07cffb2a66dec94bf3576e197090f958701f18
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2020
ms.locfileid: "97692834"
---
# <span data-ttu-id="48816-102">Set-Content</span><span class="sxs-lookup"><span data-stu-id="48816-102">Set-Content</span></span>

## <span data-ttu-id="48816-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="48816-103">SYNOPSIS</span></span>
<span data-ttu-id="48816-104">Записывает новое содержимое или заменяет существующее содержимое в файле.</span><span class="sxs-lookup"><span data-stu-id="48816-104">Writes new content or replaces existing content in a file.</span></span>

## <span data-ttu-id="48816-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="48816-105">SYNTAX</span></span>

### <span data-ttu-id="48816-106">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="48816-106">Path (Default)</span></span>

```
Set-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>]
 [-WhatIf] [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

### <span data-ttu-id="48816-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="48816-107">LiteralPath</span></span>

```
Set-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>]
 [-WhatIf] [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

## <span data-ttu-id="48816-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="48816-108">DESCRIPTION</span></span>

<span data-ttu-id="48816-109">`Set-Content` — Это командлет обработки строк, который записывает новое содержимое или заменяет содержимое в файле.</span><span class="sxs-lookup"><span data-stu-id="48816-109">`Set-Content` is a string-processing cmdlet that writes new content or replaces the content in a file.</span></span> <span data-ttu-id="48816-110">`Set-Content` Заменяет существующее содержимое и отличается от `Add-Content` командлета, который добавляет содержимое в файл.</span><span class="sxs-lookup"><span data-stu-id="48816-110">`Set-Content` replaces the existing content and differs from the `Add-Content` cmdlet that appends content to a file.</span></span> <span data-ttu-id="48816-111">Чтобы отправить содержимое в `Set-Content` , можно использовать параметр **value** в командной строке или отправить содержимое через конвейер.</span><span class="sxs-lookup"><span data-stu-id="48816-111">To send content to `Set-Content` you can use the **Value** parameter on the command line or send content through the pipeline.</span></span>

<span data-ttu-id="48816-112">Если необходимо создать файлы или каталоги для следующих примеров, см. раздел [New-Item](New-Item.md).</span><span class="sxs-lookup"><span data-stu-id="48816-112">If you need to create files or directories for the following examples, see [New-Item](New-Item.md).</span></span>

## <span data-ttu-id="48816-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="48816-113">EXAMPLES</span></span>

### <span data-ttu-id="48816-114">Пример 1. Замена содержимого нескольких файлов в каталоге</span><span class="sxs-lookup"><span data-stu-id="48816-114">Example 1: Replace the contents of multiple files in a directory</span></span>

<span data-ttu-id="48816-115">Этот пример заменяет содержимое для нескольких файлов в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="48816-115">This example replaces the content for multiple files in the current directory.</span></span>

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

<span data-ttu-id="48816-116">`Get-ChildItem`Командлет использует параметр **path** для вывода файлов **. txt** , начинающихся с `Test*` в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="48816-116">The `Get-ChildItem` cmdlet uses the **Path** parameter to list **.txt** files that begin with `Test*` in the current directory.</span></span> <span data-ttu-id="48816-117">`Set-Content`Командлет использует параметр **path** для указания `Test*.txt` файлов.</span><span class="sxs-lookup"><span data-stu-id="48816-117">The `Set-Content` cmdlet uses the **Path** parameter to specify the `Test*.txt` files.</span></span> <span data-ttu-id="48816-118">Параметр **value** предоставляет текстовую строку **Hello, World** , заменяющую существующее содержимое в каждом файле.</span><span class="sxs-lookup"><span data-stu-id="48816-118">The **Value** parameter provides the text string **Hello, World** that replaces the existing content in each file.</span></span> <span data-ttu-id="48816-119">`Get-Content`Командлет использует параметр **path** для указания `Test*.txt` файлов и отображает содержимое каждого файла в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="48816-119">The `Get-Content` cmdlet uses the **Path** parameter to specify the `Test*.txt` files and displays each file's content in the PowerShell console.</span></span>

### <span data-ttu-id="48816-120">Пример 2. Создание нового файла и запись содержимого</span><span class="sxs-lookup"><span data-stu-id="48816-120">Example 2: Create a new file and write content</span></span>

<span data-ttu-id="48816-121">В этом примере создается новый файл и записывается текущая дата и время в файл.</span><span class="sxs-lookup"><span data-stu-id="48816-121">This example creates a new file and writes the current date and time to the file.</span></span>

```powershell
Set-Content -Path .\DateTime.txt -Value (Get-Date)
Get-Content -Path .\DateTime.txt
```

```Output
1/30/2019 09:55:08
```

<span data-ttu-id="48816-122">`Set-Content` использует параметры **path** и **value** для создания нового файла с именем **DateTime.txt** в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="48816-122">`Set-Content` uses the **Path** and **Value** parameters to create a new file named **DateTime.txt** in the current directory.</span></span> <span data-ttu-id="48816-123">Параметр **value** используется `Get-Date` для получения текущих даты и времени.</span><span class="sxs-lookup"><span data-stu-id="48816-123">The **Value** parameter uses `Get-Date` to get the current date and time.</span></span>
<span data-ttu-id="48816-124">`Set-Content` Записывает объект **DateTime** в файл в виде строки.</span><span class="sxs-lookup"><span data-stu-id="48816-124">`Set-Content` writes the **DateTime** object to the file as a string.</span></span> <span data-ttu-id="48816-125">`Get-Content`Командлет использует параметр **path** для вывода содержимого **DateTime.txt** в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="48816-125">The `Get-Content` cmdlet uses the **Path** parameter to display the content of **DateTime.txt** in the PowerShell console.</span></span>

### <span data-ttu-id="48816-126">Пример 3. Замена текста в файле</span><span class="sxs-lookup"><span data-stu-id="48816-126">Example 3: Replace text in a file</span></span>

<span data-ttu-id="48816-127">Эта команда заменяет все экземпляры Word в существующем файле.</span><span class="sxs-lookup"><span data-stu-id="48816-127">This command replaces all instances of word within an existing file.</span></span>

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

<span data-ttu-id="48816-128">`Get-Content`Командлет использует параметр **path** для указания файла **Notice.txt** в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="48816-128">The `Get-Content` cmdlet uses the **Path** parameter to specify the **Notice.txt** file in the current directory.</span></span> <span data-ttu-id="48816-129">`Get-Content`Команда заключена в круглые скобки, чтобы команда закончится перед отправкой конвейера.</span><span class="sxs-lookup"><span data-stu-id="48816-129">The `Get-Content` command is wrapped with parentheses so that the command finishes before being sent down the pipeline.</span></span>

<span data-ttu-id="48816-130">Содержимое файла **Notice.txt** отправляется в командлет по конвейеру `ForEach-Object` .</span><span class="sxs-lookup"><span data-stu-id="48816-130">The contents of the **Notice.txt** file are sent down the pipeline to the `ForEach-Object` cmdlet.</span></span>
<span data-ttu-id="48816-131">`ForEach-Object` использует автоматическую переменную `$_` и заменяет каждое вхождение **предупреждения** с **осторожностью**.</span><span class="sxs-lookup"><span data-stu-id="48816-131">`ForEach-Object` uses the automatic variable `$_` and replaces each occurrence of **Warning** with **Caution**.</span></span> <span data-ttu-id="48816-132">Объекты отправляются по конвейеру в `Set-Content` командлет.</span><span class="sxs-lookup"><span data-stu-id="48816-132">The objects are sent down the pipeline to the `Set-Content` cmdlet.</span></span> <span data-ttu-id="48816-133">`Set-Content` использует параметр **path** для указания файла **Notice.txt** и записи обновленного содержимого в файл.</span><span class="sxs-lookup"><span data-stu-id="48816-133">`Set-Content` uses the **Path** parameter to specify the **Notice.txt** file and writes the updated content to the file.</span></span>

<span data-ttu-id="48816-134">Последний `Get-Content` командлет отображает обновленное содержимое файла в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="48816-134">The last `Get-Content` cmdlet displays the updated file content in the PowerShell console.</span></span>

### <span data-ttu-id="48816-135">Пример 4. Использование фильтров с Set-Content</span><span class="sxs-lookup"><span data-stu-id="48816-135">Example 4: Use Filters with Set-Content</span></span>

<span data-ttu-id="48816-136">Можно указать фильтр для `Set-Content` командлета.</span><span class="sxs-lookup"><span data-stu-id="48816-136">You can specify a filter to the `Set-Content` cmdlet.</span></span> <span data-ttu-id="48816-137">При использовании фильтров для уточнения параметра **path** необходимо включить конечную звездочку ( `*` ), чтобы указать содержимое пути.</span><span class="sxs-lookup"><span data-stu-id="48816-137">When using filters to qualify the **Path** parameter, you need to include a trailing asterisk (`*`) to indicate the contents of the path.</span></span>

<span data-ttu-id="48816-138">Следующая команда задает для содержимого всех `*.txt` файлов в `C:\Temp` каталоге пустое **значение** .</span><span class="sxs-lookup"><span data-stu-id="48816-138">The following command set the content all `*.txt` files in the `C:\Temp` directory to the **Value** empty.</span></span>

```powershell
Set-Content -Path C:\Temp\* -Filter *.txt -Value "Empty"
```

## <span data-ttu-id="48816-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="48816-139">PARAMETERS</span></span>

### <span data-ttu-id="48816-140">-Асбитестреам</span><span class="sxs-lookup"><span data-stu-id="48816-140">-AsByteStream</span></span>

<span data-ttu-id="48816-141">Указывает, что содержимое должно считываться как поток байтов.</span><span class="sxs-lookup"><span data-stu-id="48816-141">Specifies that the content should be read as a stream of bytes.</span></span> <span data-ttu-id="48816-142">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="48816-142">This parameter was introduced in PowerShell 6.0.</span></span>

<span data-ttu-id="48816-143">При использовании параметра **асбитестреам** с параметром **Encoding** возникает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="48816-143">A warning occurs when you use the **AsByteStream** parameter with the **Encoding** parameter.</span></span> <span data-ttu-id="48816-144">Параметр **асбитестреам** игнорирует любую кодировку, и выходные данные возвращаются в виде потока байтов.</span><span class="sxs-lookup"><span data-stu-id="48816-144">The **AsByteStream** parameter ignores any encoding and the output is returned as a stream of bytes.</span></span>

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

### <span data-ttu-id="48816-145">-Credential</span><span class="sxs-lookup"><span data-stu-id="48816-145">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="48816-146">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="48816-146">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="48816-147">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="48816-147">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="48816-148">-Encoding</span><span class="sxs-lookup"><span data-stu-id="48816-148">-Encoding</span></span>

<span data-ttu-id="48816-149">Указывает тип кодировки для целевого файла.</span><span class="sxs-lookup"><span data-stu-id="48816-149">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="48816-150">Значение по умолчанию — `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="48816-150">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="48816-151">Кодирование — это динамический параметр, к которому добавляется поставщик FileSystem `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="48816-151">Encoding is a dynamic parameter that the FileSystem provider adds to `Set-Content`.</span></span> <span data-ttu-id="48816-152">Этот параметр работает только на дисках с файловой системой.</span><span class="sxs-lookup"><span data-stu-id="48816-152">This parameter works only in file system drives.</span></span>

<span data-ttu-id="48816-153">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="48816-153">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="48816-154">`ascii`: Использует кодировку для набора символов ASCII (7-разрядных).</span><span class="sxs-lookup"><span data-stu-id="48816-154">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="48816-155">`bigendianunicode`: Кодируется в формате UTF-16 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="48816-155">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="48816-156">`bigendianutf32`: Кодируется в формате UTF-32 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="48816-156">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="48816-157">`oem`: Использует кодировку по умолчанию для программ MS-DOS и консолей.</span><span class="sxs-lookup"><span data-stu-id="48816-157">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="48816-158">`unicode`: Кодируется в формате UTF-16 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="48816-158">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="48816-159">`utf7`: Кодируется в формате UTF-7.</span><span class="sxs-lookup"><span data-stu-id="48816-159">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="48816-160">`utf8`: Кодируется в формате UTF-8.</span><span class="sxs-lookup"><span data-stu-id="48816-160">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="48816-161">`utf8BOM`: Кодирует в формате UTF-8 с меткой порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="48816-161">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="48816-162">`utf8NoBOM`: Кодирует в формате UTF-8 без метки порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="48816-162">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="48816-163">`utf32`: Кодируется в формате UTF-32.</span><span class="sxs-lookup"><span data-stu-id="48816-163">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="48816-164">Начиная с PowerShell 6,2, параметр **кодировки** также разрешает числовые идентификаторы зарегистрированных кодовых страниц (например `-Encoding 1251` ,) или строковых имен зарегистрированных кодовых страниц (например `-Encoding "windows-1251"` ,).</span><span class="sxs-lookup"><span data-stu-id="48816-164">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="48816-165">Дополнительные сведения см. в документации .NET по [кодированию. codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="48816-165">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

> [!NOTE]
> <span data-ttu-id="48816-166">Больше не рекомендуется использовать **UTF-7** _.</span><span class="sxs-lookup"><span data-stu-id="48816-166">**UTF-7** _ is no longer recommended to use.</span></span> <span data-ttu-id="48816-167">В PowerShell 7,1 записывается предупреждение, если указано `utf7` для параметра _ \*Encoding\*\*.</span><span class="sxs-lookup"><span data-stu-id="48816-167">In PowerShell 7.1, a warning is written if you specify `utf7` for the _ *Encoding*\* parameter.</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="48816-168">-Exclude</span><span class="sxs-lookup"><span data-stu-id="48816-168">-Exclude</span></span>

<span data-ttu-id="48816-169">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="48816-169">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="48816-170">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="48816-170">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="48816-171">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="48816-171">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="48816-172">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="48816-172">Wildcard characters are permitted.</span></span> <span data-ttu-id="48816-173">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="48816-173">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="48816-174">-Filter</span><span class="sxs-lookup"><span data-stu-id="48816-174">-Filter</span></span>

<span data-ttu-id="48816-175">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="48816-175">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="48816-176">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="48816-176">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="48816-177">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="48816-177">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="48816-178">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="48816-178">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="48816-179">-Force</span><span class="sxs-lookup"><span data-stu-id="48816-179">-Force</span></span>

<span data-ttu-id="48816-180">Заставляет командлет задать содержимое файла, даже если он доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="48816-180">Forces the cmdlet to set the contents of a file, even if the file is read-only.</span></span> <span data-ttu-id="48816-181">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="48816-181">Implementation varies from provider to provider.</span></span> <span data-ttu-id="48816-182">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="48816-182">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
<span data-ttu-id="48816-183">Параметр **Force** не переопределяет ограничения безопасности.</span><span class="sxs-lookup"><span data-stu-id="48816-183">The **Force** parameter does not override security restrictions.</span></span>

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

### <span data-ttu-id="48816-184">-Include</span><span class="sxs-lookup"><span data-stu-id="48816-184">-Include</span></span>

<span data-ttu-id="48816-185">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="48816-185">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="48816-186">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="48816-186">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="48816-187">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="48816-187">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="48816-188">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="48816-188">Wildcard characters are permitted.</span></span> <span data-ttu-id="48816-189">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="48816-189">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="48816-190">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="48816-190">-LiteralPath</span></span>

<span data-ttu-id="48816-191">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="48816-191">Specifies a path to one or more locations.</span></span> <span data-ttu-id="48816-192">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="48816-192">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="48816-193">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="48816-193">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="48816-194">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="48816-194">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="48816-195">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="48816-195">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="48816-196">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="48816-196">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="48816-197">-Новая строка</span><span class="sxs-lookup"><span data-stu-id="48816-197">-NoNewline</span></span>

<span data-ttu-id="48816-198">Строковые представления входных объектов сцепляются для формирования выходных данных.</span><span class="sxs-lookup"><span data-stu-id="48816-198">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="48816-199">Между выходными строками не вставляются пробелы и символы новой строки.</span><span class="sxs-lookup"><span data-stu-id="48816-199">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="48816-200">После последней выходной строки не добавляется новая строка.</span><span class="sxs-lookup"><span data-stu-id="48816-200">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="48816-201">-PassThru</span><span class="sxs-lookup"><span data-stu-id="48816-201">-PassThru</span></span>

<span data-ttu-id="48816-202">Возвращает объект, представляющий содержимое.</span><span class="sxs-lookup"><span data-stu-id="48816-202">Returns an object that represents the content.</span></span> <span data-ttu-id="48816-203">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="48816-203">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="48816-204">-Path</span><span class="sxs-lookup"><span data-stu-id="48816-204">-Path</span></span>

<span data-ttu-id="48816-205">Указывает путь к элементу, который получает содержимое.</span><span class="sxs-lookup"><span data-stu-id="48816-205">Specifies the path of the item that receives the content.</span></span>
<span data-ttu-id="48816-206">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="48816-206">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="48816-207">-Stream</span><span class="sxs-lookup"><span data-stu-id="48816-207">-Stream</span></span>

> [!NOTE]
> <span data-ttu-id="48816-208">Этот параметр доступен только в Windows.</span><span class="sxs-lookup"><span data-stu-id="48816-208">This Parameter is only available on Windows.</span></span>

<span data-ttu-id="48816-209">Указывает альтернативный поток данных для содержимого.</span><span class="sxs-lookup"><span data-stu-id="48816-209">Specifies an alternative data stream for content.</span></span> <span data-ttu-id="48816-210">Если поток не существует, этот командлет создаст его.</span><span class="sxs-lookup"><span data-stu-id="48816-210">If the stream does not exist, this cmdlet creates it.</span></span> <span data-ttu-id="48816-211">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="48816-211">Wildcard characters are not supported.</span></span>

<span data-ttu-id="48816-212">**Stream** — это динамический параметр, к которому добавляется поставщик **FileSystem** `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="48816-212">**Stream** is a dynamic parameter that the **FileSystem** provider adds to `Set-Content`.</span></span> <span data-ttu-id="48816-213">Этот параметр работает только на дисках с файловой системой.</span><span class="sxs-lookup"><span data-stu-id="48816-213">This parameter works only in file system drives.</span></span>

<span data-ttu-id="48816-214">Командлет можно использовать `Set-Content` для создания или обновления содержимого любого альтернативного потока данных, например `Zone.Identifier` .</span><span class="sxs-lookup"><span data-stu-id="48816-214">You can use the `Set-Content` cmdlet to create or update the content of any alternate data stream, such as `Zone.Identifier`.</span></span> <span data-ttu-id="48816-215">Однако не рекомендуется использовать этот способ для устранения проверок безопасности, блокирующих файлы, загружаемые из Интернета.</span><span class="sxs-lookup"><span data-stu-id="48816-215">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="48816-216">Если вы убедитесь, что скачанный файл является надежным, используйте `Unblock-File` командлет.</span><span class="sxs-lookup"><span data-stu-id="48816-216">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="48816-217">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="48816-217">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="48816-218">-Value</span><span class="sxs-lookup"><span data-stu-id="48816-218">-Value</span></span>

<span data-ttu-id="48816-219">Указывает новое содержимое для элемента.</span><span class="sxs-lookup"><span data-stu-id="48816-219">Specifies the new content for the item.</span></span>

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

### <span data-ttu-id="48816-220">-Confirm</span><span class="sxs-lookup"><span data-stu-id="48816-220">-Confirm</span></span>

<span data-ttu-id="48816-221">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="48816-221">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="48816-222">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="48816-222">-WhatIf</span></span>

<span data-ttu-id="48816-223">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="48816-223">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="48816-224">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="48816-224">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="48816-225">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="48816-225">CommonParameters</span></span>

<span data-ttu-id="48816-226">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="48816-226">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="48816-227">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="48816-227">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="48816-228">Входные данные</span><span class="sxs-lookup"><span data-stu-id="48816-228">INPUTS</span></span>

### <span data-ttu-id="48816-229">System.Object</span><span class="sxs-lookup"><span data-stu-id="48816-229">System.Object</span></span>

<span data-ttu-id="48816-230">Объект, содержащий новое значение для элемента, можно передать по конвейеру `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="48816-230">You can pipe an object that contains the new value for the item to `Set-Content`.</span></span>

## <span data-ttu-id="48816-231">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="48816-231">OUTPUTS</span></span>

### <span data-ttu-id="48816-232">Нет или System.String</span><span class="sxs-lookup"><span data-stu-id="48816-232">None or System.String</span></span>

<span data-ttu-id="48816-233">При использовании параметра **PassThru** `Set-Content` создает объект **System. String** , представляющий содержимое.</span><span class="sxs-lookup"><span data-stu-id="48816-233">When you use the **PassThru** parameter, `Set-Content` generates a **System.String** object that represents the content.</span></span> <span data-ttu-id="48816-234">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="48816-234">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="48816-235">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="48816-235">NOTES</span></span>

- <span data-ttu-id="48816-236">Также можно ссылаться `Set-Content` по встроенному псевдониму `sc` .</span><span class="sxs-lookup"><span data-stu-id="48816-236">You can also refer to `Set-Content` by its built-in alias, `sc`.</span></span>
  <span data-ttu-id="48816-237">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="48816-237">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="48816-238">`Set-Content` предназначен для обработки строк.</span><span class="sxs-lookup"><span data-stu-id="48816-238">`Set-Content` is designed for string processing.</span></span> <span data-ttu-id="48816-239">При передаче нестроковых объектов в `Set-Content` объект преобразуется в строку перед записью.</span><span class="sxs-lookup"><span data-stu-id="48816-239">If you pipe non-string objects to `Set-Content`, it converts the object to a string before writing it.</span></span> <span data-ttu-id="48816-240">Для записи объектов в файлы используйте `Out-File` .</span><span class="sxs-lookup"><span data-stu-id="48816-240">To write objects to files, use `Out-File`.</span></span>
- <span data-ttu-id="48816-241">`Set-Content`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="48816-241">The `Set-Content` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="48816-242">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PsProvider`.</span><span class="sxs-lookup"><span data-stu-id="48816-242">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="48816-243">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="48816-243">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="48816-244">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="48816-244">RELATED LINKS</span></span>

[<span data-ttu-id="48816-245">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="48816-245">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="48816-246">about_Automatic_Variables. md</span><span class="sxs-lookup"><span data-stu-id="48816-246">about_Automatic_Variables.md</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="48816-247">about_Providers</span><span class="sxs-lookup"><span data-stu-id="48816-247">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="48816-248">Add-Content</span><span class="sxs-lookup"><span data-stu-id="48816-248">Add-Content</span></span>](Add-Content.md)

[<span data-ttu-id="48816-249">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="48816-249">Clear-Content</span></span>](Clear-Content.md)

[<span data-ttu-id="48816-250">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="48816-250">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="48816-251">Get-Content</span><span class="sxs-lookup"><span data-stu-id="48816-251">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="48816-252">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="48816-252">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="48816-253">New-Item</span><span class="sxs-lookup"><span data-stu-id="48816-253">New-Item</span></span>](New-Item.md)
