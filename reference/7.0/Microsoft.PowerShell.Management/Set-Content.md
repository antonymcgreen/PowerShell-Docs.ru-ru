---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-content?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Content
ms.openlocfilehash: 2561d569fa773d279e1e54561d6005e3eef7f7e3
ms.sourcegitcommit: bf07cffb2a66dec94bf3576e197090f958701f18
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2020
ms.locfileid: "97692778"
---
# <span data-ttu-id="5671e-102">Set-Content</span><span class="sxs-lookup"><span data-stu-id="5671e-102">Set-Content</span></span>

## <span data-ttu-id="5671e-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="5671e-103">SYNOPSIS</span></span>
<span data-ttu-id="5671e-104">Записывает новое содержимое или заменяет существующее содержимое в файле.</span><span class="sxs-lookup"><span data-stu-id="5671e-104">Writes new content or replaces existing content in a file.</span></span>

## <span data-ttu-id="5671e-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5671e-105">SYNTAX</span></span>

### <span data-ttu-id="5671e-106">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="5671e-106">Path (Default)</span></span>

```
Set-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>]
 [-WhatIf] [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

### <span data-ttu-id="5671e-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="5671e-107">LiteralPath</span></span>

```
Set-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>]
 [-WhatIf] [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

## <span data-ttu-id="5671e-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5671e-108">DESCRIPTION</span></span>

<span data-ttu-id="5671e-109">`Set-Content` — Это командлет обработки строк, который записывает новое содержимое или заменяет содержимое в файле.</span><span class="sxs-lookup"><span data-stu-id="5671e-109">`Set-Content` is a string-processing cmdlet that writes new content or replaces the content in a file.</span></span> <span data-ttu-id="5671e-110">`Set-Content` Заменяет существующее содержимое и отличается от `Add-Content` командлета, который добавляет содержимое в файл.</span><span class="sxs-lookup"><span data-stu-id="5671e-110">`Set-Content` replaces the existing content and differs from the `Add-Content` cmdlet that appends content to a file.</span></span> <span data-ttu-id="5671e-111">Чтобы отправить содержимое в `Set-Content` , можно использовать параметр **value** в командной строке или отправить содержимое через конвейер.</span><span class="sxs-lookup"><span data-stu-id="5671e-111">To send content to `Set-Content` you can use the **Value** parameter on the command line or send content through the pipeline.</span></span>

<span data-ttu-id="5671e-112">Если необходимо создать файлы или каталоги для следующих примеров, см. раздел [New-Item](New-Item.md).</span><span class="sxs-lookup"><span data-stu-id="5671e-112">If you need to create files or directories for the following examples, see [New-Item](New-Item.md).</span></span>

## <span data-ttu-id="5671e-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="5671e-113">EXAMPLES</span></span>

### <span data-ttu-id="5671e-114">Пример 1. Замена содержимого нескольких файлов в каталоге</span><span class="sxs-lookup"><span data-stu-id="5671e-114">Example 1: Replace the contents of multiple files in a directory</span></span>

<span data-ttu-id="5671e-115">Этот пример заменяет содержимое для нескольких файлов в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="5671e-115">This example replaces the content for multiple files in the current directory.</span></span>

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

<span data-ttu-id="5671e-116">`Get-ChildItem`Командлет использует параметр **path** для вывода файлов **. txt** , начинающихся с `Test*` в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="5671e-116">The `Get-ChildItem` cmdlet uses the **Path** parameter to list **.txt** files that begin with `Test*` in the current directory.</span></span> <span data-ttu-id="5671e-117">`Set-Content`Командлет использует параметр **path** для указания `Test*.txt` файлов.</span><span class="sxs-lookup"><span data-stu-id="5671e-117">The `Set-Content` cmdlet uses the **Path** parameter to specify the `Test*.txt` files.</span></span> <span data-ttu-id="5671e-118">Параметр **value** предоставляет текстовую строку **Hello, World** , заменяющую существующее содержимое в каждом файле.</span><span class="sxs-lookup"><span data-stu-id="5671e-118">The **Value** parameter provides the text string **Hello, World** that replaces the existing content in each file.</span></span> <span data-ttu-id="5671e-119">`Get-Content`Командлет использует параметр **path** для указания `Test*.txt` файлов и отображает содержимое каждого файла в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5671e-119">The `Get-Content` cmdlet uses the **Path** parameter to specify the `Test*.txt` files and displays each file's content in the PowerShell console.</span></span>

### <span data-ttu-id="5671e-120">Пример 2. Создание нового файла и запись содержимого</span><span class="sxs-lookup"><span data-stu-id="5671e-120">Example 2: Create a new file and write content</span></span>

<span data-ttu-id="5671e-121">В этом примере создается новый файл и записывается текущая дата и время в файл.</span><span class="sxs-lookup"><span data-stu-id="5671e-121">This example creates a new file and writes the current date and time to the file.</span></span>

```powershell
Set-Content -Path .\DateTime.txt -Value (Get-Date)
Get-Content -Path .\DateTime.txt
```

```Output
1/30/2019 09:55:08
```

<span data-ttu-id="5671e-122">`Set-Content` использует параметры **path** и **value** для создания нового файла с именем **DateTime.txt** в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="5671e-122">`Set-Content` uses the **Path** and **Value** parameters to create a new file named **DateTime.txt** in the current directory.</span></span> <span data-ttu-id="5671e-123">Параметр **value** используется `Get-Date` для получения текущих даты и времени.</span><span class="sxs-lookup"><span data-stu-id="5671e-123">The **Value** parameter uses `Get-Date` to get the current date and time.</span></span>
<span data-ttu-id="5671e-124">`Set-Content` Записывает объект **DateTime** в файл в виде строки.</span><span class="sxs-lookup"><span data-stu-id="5671e-124">`Set-Content` writes the **DateTime** object to the file as a string.</span></span> <span data-ttu-id="5671e-125">`Get-Content`Командлет использует параметр **path** для вывода содержимого **DateTime.txt** в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5671e-125">The `Get-Content` cmdlet uses the **Path** parameter to display the content of **DateTime.txt** in the PowerShell console.</span></span>

### <span data-ttu-id="5671e-126">Пример 3. Замена текста в файле</span><span class="sxs-lookup"><span data-stu-id="5671e-126">Example 3: Replace text in a file</span></span>

<span data-ttu-id="5671e-127">Эта команда заменяет все экземпляры Word в существующем файле.</span><span class="sxs-lookup"><span data-stu-id="5671e-127">This command replaces all instances of word within an existing file.</span></span>

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

<span data-ttu-id="5671e-128">`Get-Content`Командлет использует параметр **path** для указания файла **Notice.txt** в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="5671e-128">The `Get-Content` cmdlet uses the **Path** parameter to specify the **Notice.txt** file in the current directory.</span></span> <span data-ttu-id="5671e-129">`Get-Content`Команда заключена в круглые скобки, чтобы команда закончится перед отправкой конвейера.</span><span class="sxs-lookup"><span data-stu-id="5671e-129">The `Get-Content` command is wrapped with parentheses so that the command finishes before being sent down the pipeline.</span></span>

<span data-ttu-id="5671e-130">Содержимое файла **Notice.txt** отправляется в командлет по конвейеру `ForEach-Object` .</span><span class="sxs-lookup"><span data-stu-id="5671e-130">The contents of the **Notice.txt** file are sent down the pipeline to the `ForEach-Object` cmdlet.</span></span>
<span data-ttu-id="5671e-131">`ForEach-Object` использует автоматическую переменную `$_` и заменяет каждое вхождение **предупреждения** с **осторожностью**.</span><span class="sxs-lookup"><span data-stu-id="5671e-131">`ForEach-Object` uses the automatic variable `$_` and replaces each occurrence of **Warning** with **Caution**.</span></span> <span data-ttu-id="5671e-132">Объекты отправляются по конвейеру в `Set-Content` командлет.</span><span class="sxs-lookup"><span data-stu-id="5671e-132">The objects are sent down the pipeline to the `Set-Content` cmdlet.</span></span> <span data-ttu-id="5671e-133">`Set-Content` использует параметр **path** для указания файла **Notice.txt** и записи обновленного содержимого в файл.</span><span class="sxs-lookup"><span data-stu-id="5671e-133">`Set-Content` uses the **Path** parameter to specify the **Notice.txt** file and writes the updated content to the file.</span></span>

<span data-ttu-id="5671e-134">Последний `Get-Content` командлет отображает обновленное содержимое файла в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5671e-134">The last `Get-Content` cmdlet displays the updated file content in the PowerShell console.</span></span>

### <span data-ttu-id="5671e-135">Пример 4. Использование фильтров с Set-Content</span><span class="sxs-lookup"><span data-stu-id="5671e-135">Example 4: Use Filters with Set-Content</span></span>

<span data-ttu-id="5671e-136">Можно указать фильтр для `Set-Content` командлета.</span><span class="sxs-lookup"><span data-stu-id="5671e-136">You can specify a filter to the `Set-Content` cmdlet.</span></span> <span data-ttu-id="5671e-137">При использовании фильтров для уточнения параметра **path** необходимо включить конечную звездочку ( `*` ), чтобы указать содержимое пути.</span><span class="sxs-lookup"><span data-stu-id="5671e-137">When using filters to qualify the **Path** parameter, you need to include a trailing asterisk (`*`) to indicate the contents of the path.</span></span>

<span data-ttu-id="5671e-138">Следующая команда задает для содержимого всех `*.txt` файлов в `C:\Temp` каталоге пустое **значение** .</span><span class="sxs-lookup"><span data-stu-id="5671e-138">The following command set the content all `*.txt` files in the `C:\Temp` directory to the **Value** empty.</span></span>

```powershell
Set-Content -Path C:\Temp\* -Filter *.txt -Value "Empty"
```

## <span data-ttu-id="5671e-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5671e-139">PARAMETERS</span></span>

### <span data-ttu-id="5671e-140">-Асбитестреам</span><span class="sxs-lookup"><span data-stu-id="5671e-140">-AsByteStream</span></span>

<span data-ttu-id="5671e-141">Указывает, что содержимое должно считываться как поток байтов.</span><span class="sxs-lookup"><span data-stu-id="5671e-141">Specifies that the content should be read as a stream of bytes.</span></span> <span data-ttu-id="5671e-142">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="5671e-142">This parameter was introduced in PowerShell 6.0.</span></span>

<span data-ttu-id="5671e-143">При использовании параметра **асбитестреам** с параметром **Encoding** возникает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="5671e-143">A warning occurs when you use the **AsByteStream** parameter with the **Encoding** parameter.</span></span> <span data-ttu-id="5671e-144">Параметр **асбитестреам** игнорирует любую кодировку, и выходные данные возвращаются в виде потока байтов.</span><span class="sxs-lookup"><span data-stu-id="5671e-144">The **AsByteStream** parameter ignores any encoding and the output is returned as a stream of bytes.</span></span>

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

### <span data-ttu-id="5671e-145">-Credential</span><span class="sxs-lookup"><span data-stu-id="5671e-145">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="5671e-146">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5671e-146">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="5671e-147">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="5671e-147">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="5671e-148">-Encoding</span><span class="sxs-lookup"><span data-stu-id="5671e-148">-Encoding</span></span>

<span data-ttu-id="5671e-149">Указывает тип кодировки для целевого файла.</span><span class="sxs-lookup"><span data-stu-id="5671e-149">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="5671e-150">Значение по умолчанию — `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="5671e-150">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="5671e-151">Кодирование — это динамический параметр, к которому добавляется поставщик FileSystem `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="5671e-151">Encoding is a dynamic parameter that the FileSystem provider adds to `Set-Content`.</span></span> <span data-ttu-id="5671e-152">Этот параметр работает только на дисках с файловой системой.</span><span class="sxs-lookup"><span data-stu-id="5671e-152">This parameter works only in file system drives.</span></span>

<span data-ttu-id="5671e-153">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="5671e-153">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="5671e-154">`ascii`: Использует кодировку для набора символов ASCII (7-разрядных).</span><span class="sxs-lookup"><span data-stu-id="5671e-154">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="5671e-155">`bigendianunicode`: Кодируется в формате UTF-16 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="5671e-155">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="5671e-156">`oem`: Использует кодировку по умолчанию для программ MS-DOS и консолей.</span><span class="sxs-lookup"><span data-stu-id="5671e-156">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="5671e-157">`unicode`: Кодируется в формате UTF-16 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="5671e-157">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="5671e-158">`utf7`: Кодируется в формате UTF-7.</span><span class="sxs-lookup"><span data-stu-id="5671e-158">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="5671e-159">`utf8`: Кодируется в формате UTF-8.</span><span class="sxs-lookup"><span data-stu-id="5671e-159">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="5671e-160">`utf8BOM`: Кодирует в формате UTF-8 с меткой порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="5671e-160">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="5671e-161">`utf8NoBOM`: Кодирует в формате UTF-8 без метки порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="5671e-161">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="5671e-162">`utf32`: Кодируется в формате UTF-32.</span><span class="sxs-lookup"><span data-stu-id="5671e-162">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="5671e-163">Начиная с PowerShell 6,2, параметр **кодировки** также разрешает числовые идентификаторы зарегистрированных кодовых страниц (например `-Encoding 1251` ,) или строковых имен зарегистрированных кодовых страниц (например `-Encoding "windows-1251"` ,).</span><span class="sxs-lookup"><span data-stu-id="5671e-163">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="5671e-164">Дополнительные сведения см. в документации .NET по [кодированию. codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="5671e-164">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

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

### <span data-ttu-id="5671e-165">-Exclude</span><span class="sxs-lookup"><span data-stu-id="5671e-165">-Exclude</span></span>

<span data-ttu-id="5671e-166">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="5671e-166">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="5671e-167">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="5671e-167">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="5671e-168">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="5671e-168">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="5671e-169">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="5671e-169">Wildcard characters are permitted.</span></span> <span data-ttu-id="5671e-170">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="5671e-170">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="5671e-171">-Filter</span><span class="sxs-lookup"><span data-stu-id="5671e-171">-Filter</span></span>

<span data-ttu-id="5671e-172">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="5671e-172">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="5671e-173">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="5671e-173">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="5671e-174">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="5671e-174">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="5671e-175">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="5671e-175">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="5671e-176">-Force</span><span class="sxs-lookup"><span data-stu-id="5671e-176">-Force</span></span>

<span data-ttu-id="5671e-177">Заставляет командлет задать содержимое файла, даже если он доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="5671e-177">Forces the cmdlet to set the contents of a file, even if the file is read-only.</span></span> <span data-ttu-id="5671e-178">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="5671e-178">Implementation varies from provider to provider.</span></span> <span data-ttu-id="5671e-179">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="5671e-179">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
<span data-ttu-id="5671e-180">Параметр **Force** не переопределяет ограничения безопасности.</span><span class="sxs-lookup"><span data-stu-id="5671e-180">The **Force** parameter does not override security restrictions.</span></span>

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

### <span data-ttu-id="5671e-181">-Include</span><span class="sxs-lookup"><span data-stu-id="5671e-181">-Include</span></span>

<span data-ttu-id="5671e-182">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="5671e-182">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="5671e-183">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="5671e-183">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="5671e-184">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="5671e-184">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="5671e-185">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="5671e-185">Wildcard characters are permitted.</span></span> <span data-ttu-id="5671e-186">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="5671e-186">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="5671e-187">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="5671e-187">-LiteralPath</span></span>

<span data-ttu-id="5671e-188">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="5671e-188">Specifies a path to one or more locations.</span></span> <span data-ttu-id="5671e-189">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="5671e-189">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="5671e-190">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="5671e-190">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="5671e-191">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="5671e-191">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="5671e-192">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="5671e-192">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="5671e-193">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="5671e-193">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="5671e-194">-Новая строка</span><span class="sxs-lookup"><span data-stu-id="5671e-194">-NoNewline</span></span>

<span data-ttu-id="5671e-195">Строковые представления входных объектов сцепляются для формирования выходных данных.</span><span class="sxs-lookup"><span data-stu-id="5671e-195">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="5671e-196">Между выходными строками не вставляются пробелы и символы новой строки.</span><span class="sxs-lookup"><span data-stu-id="5671e-196">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="5671e-197">После последней выходной строки не добавляется новая строка.</span><span class="sxs-lookup"><span data-stu-id="5671e-197">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="5671e-198">-PassThru</span><span class="sxs-lookup"><span data-stu-id="5671e-198">-PassThru</span></span>

<span data-ttu-id="5671e-199">Возвращает объект, представляющий содержимое.</span><span class="sxs-lookup"><span data-stu-id="5671e-199">Returns an object that represents the content.</span></span> <span data-ttu-id="5671e-200">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="5671e-200">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="5671e-201">-Path</span><span class="sxs-lookup"><span data-stu-id="5671e-201">-Path</span></span>

<span data-ttu-id="5671e-202">Указывает путь к элементу, который получает содержимое.</span><span class="sxs-lookup"><span data-stu-id="5671e-202">Specifies the path of the item that receives the content.</span></span>
<span data-ttu-id="5671e-203">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="5671e-203">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="5671e-204">-Stream</span><span class="sxs-lookup"><span data-stu-id="5671e-204">-Stream</span></span>

> [!NOTE]
> <span data-ttu-id="5671e-205">Этот параметр доступен только в Windows.</span><span class="sxs-lookup"><span data-stu-id="5671e-205">This Parameter is only available on Windows.</span></span>

<span data-ttu-id="5671e-206">Указывает альтернативный поток данных для содержимого.</span><span class="sxs-lookup"><span data-stu-id="5671e-206">Specifies an alternative data stream for content.</span></span> <span data-ttu-id="5671e-207">Если поток не существует, этот командлет создаст его.</span><span class="sxs-lookup"><span data-stu-id="5671e-207">If the stream does not exist, this cmdlet creates it.</span></span> <span data-ttu-id="5671e-208">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="5671e-208">Wildcard characters are not supported.</span></span>

<span data-ttu-id="5671e-209">**Stream** — это динамический параметр, к которому добавляется поставщик **FileSystem** `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="5671e-209">**Stream** is a dynamic parameter that the **FileSystem** provider adds to `Set-Content`.</span></span> <span data-ttu-id="5671e-210">Этот параметр работает только на дисках с файловой системой.</span><span class="sxs-lookup"><span data-stu-id="5671e-210">This parameter works only in file system drives.</span></span>

<span data-ttu-id="5671e-211">Командлет можно использовать `Set-Content` для создания или обновления содержимого любого альтернативного потока данных, например `Zone.Identifier` .</span><span class="sxs-lookup"><span data-stu-id="5671e-211">You can use the `Set-Content` cmdlet to create or update the content of any alternate data stream, such as `Zone.Identifier`.</span></span> <span data-ttu-id="5671e-212">Однако не рекомендуется использовать этот способ для устранения проверок безопасности, блокирующих файлы, загружаемые из Интернета.</span><span class="sxs-lookup"><span data-stu-id="5671e-212">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="5671e-213">Если вы убедитесь, что скачанный файл является надежным, используйте `Unblock-File` командлет.</span><span class="sxs-lookup"><span data-stu-id="5671e-213">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="5671e-214">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="5671e-214">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="5671e-215">-Value</span><span class="sxs-lookup"><span data-stu-id="5671e-215">-Value</span></span>

<span data-ttu-id="5671e-216">Указывает новое содержимое для элемента.</span><span class="sxs-lookup"><span data-stu-id="5671e-216">Specifies the new content for the item.</span></span>

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

### <span data-ttu-id="5671e-217">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5671e-217">-Confirm</span></span>

<span data-ttu-id="5671e-218">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="5671e-218">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="5671e-219">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5671e-219">-WhatIf</span></span>

<span data-ttu-id="5671e-220">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="5671e-220">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="5671e-221">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="5671e-221">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="5671e-222">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="5671e-222">CommonParameters</span></span>

<span data-ttu-id="5671e-223">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5671e-223">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5671e-224">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5671e-224">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5671e-225">Входные данные</span><span class="sxs-lookup"><span data-stu-id="5671e-225">INPUTS</span></span>

### <span data-ttu-id="5671e-226">System.Object</span><span class="sxs-lookup"><span data-stu-id="5671e-226">System.Object</span></span>

<span data-ttu-id="5671e-227">Объект, содержащий новое значение для элемента, можно передать по конвейеру `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="5671e-227">You can pipe an object that contains the new value for the item to `Set-Content`.</span></span>

## <span data-ttu-id="5671e-228">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="5671e-228">OUTPUTS</span></span>

### <span data-ttu-id="5671e-229">Нет или System.String</span><span class="sxs-lookup"><span data-stu-id="5671e-229">None or System.String</span></span>

<span data-ttu-id="5671e-230">При использовании параметра **PassThru** `Set-Content` создает объект **System. String** , представляющий содержимое.</span><span class="sxs-lookup"><span data-stu-id="5671e-230">When you use the **PassThru** parameter, `Set-Content` generates a **System.String** object that represents the content.</span></span> <span data-ttu-id="5671e-231">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="5671e-231">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="5671e-232">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="5671e-232">NOTES</span></span>

- <span data-ttu-id="5671e-233">Также можно ссылаться `Set-Content` по встроенному псевдониму `sc` .</span><span class="sxs-lookup"><span data-stu-id="5671e-233">You can also refer to `Set-Content` by its built-in alias, `sc`.</span></span>
  <span data-ttu-id="5671e-234">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="5671e-234">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="5671e-235">`Set-Content` предназначен для обработки строк.</span><span class="sxs-lookup"><span data-stu-id="5671e-235">`Set-Content` is designed for string processing.</span></span> <span data-ttu-id="5671e-236">При передаче нестроковых объектов в `Set-Content` объект преобразуется в строку перед записью.</span><span class="sxs-lookup"><span data-stu-id="5671e-236">If you pipe non-string objects to `Set-Content`, it converts the object to a string before writing it.</span></span> <span data-ttu-id="5671e-237">Для записи объектов в файлы используйте `Out-File` .</span><span class="sxs-lookup"><span data-stu-id="5671e-237">To write objects to files, use `Out-File`.</span></span>
- <span data-ttu-id="5671e-238">`Set-Content`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="5671e-238">The `Set-Content` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="5671e-239">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PsProvider`.</span><span class="sxs-lookup"><span data-stu-id="5671e-239">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="5671e-240">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="5671e-240">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="5671e-241">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="5671e-241">RELATED LINKS</span></span>

[<span data-ttu-id="5671e-242">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="5671e-242">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="5671e-243">about_Automatic_Variables. md</span><span class="sxs-lookup"><span data-stu-id="5671e-243">about_Automatic_Variables.md</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="5671e-244">about_Providers</span><span class="sxs-lookup"><span data-stu-id="5671e-244">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="5671e-245">Add-Content</span><span class="sxs-lookup"><span data-stu-id="5671e-245">Add-Content</span></span>](Add-Content.md)

[<span data-ttu-id="5671e-246">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="5671e-246">Clear-Content</span></span>](Clear-Content.md)

[<span data-ttu-id="5671e-247">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="5671e-247">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="5671e-248">Get-Content</span><span class="sxs-lookup"><span data-stu-id="5671e-248">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="5671e-249">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="5671e-249">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="5671e-250">New-Item</span><span class="sxs-lookup"><span data-stu-id="5671e-250">New-Item</span></span>](New-Item.md)
