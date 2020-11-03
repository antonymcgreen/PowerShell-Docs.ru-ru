---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-content?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Content
ms.openlocfilehash: 897029cab790487f6834d021bfc447060fd39812
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227901"
---
# <span data-ttu-id="304b0-103">Set-Content</span><span class="sxs-lookup"><span data-stu-id="304b0-103">Set-Content</span></span>

## <span data-ttu-id="304b0-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="304b0-104">SYNOPSIS</span></span>
<span data-ttu-id="304b0-105">Записывает новое содержимое или заменяет существующее содержимое в файле.</span><span class="sxs-lookup"><span data-stu-id="304b0-105">Writes new content or replaces existing content in a file.</span></span>

## <span data-ttu-id="304b0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="304b0-106">SYNTAX</span></span>

### <span data-ttu-id="304b0-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="304b0-107">Path (Default)</span></span>

```
Set-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [-NoNewline] [-Encoding <FileSystemCmdletProviderEncoding>]
 [-Stream <string>] [<CommonParameters>]
```

### <span data-ttu-id="304b0-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="304b0-108">LiteralPath</span></span>

```
Set-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [-NoNewline] [-Encoding <FileSystemCmdletProviderEncoding>]
 [-Stream <string>] [<CommonParameters>]
```

## <span data-ttu-id="304b0-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="304b0-109">DESCRIPTION</span></span>

<span data-ttu-id="304b0-110">`Set-Content` — Это командлет обработки строк, который записывает новое содержимое или заменяет содержимое в файле.</span><span class="sxs-lookup"><span data-stu-id="304b0-110">`Set-Content` is a string-processing cmdlet that writes new content or replaces the content in a file.</span></span> <span data-ttu-id="304b0-111">`Set-Content` Заменяет существующее содержимое и отличается от `Add-Content` командлета, который добавляет содержимое в файл.</span><span class="sxs-lookup"><span data-stu-id="304b0-111">`Set-Content` replaces the existing content and differs from the `Add-Content` cmdlet that appends content to a file.</span></span> <span data-ttu-id="304b0-112">Чтобы отправить содержимое в `Set-Content` , можно использовать параметр **value** в командной строке или отправить содержимое через конвейер.</span><span class="sxs-lookup"><span data-stu-id="304b0-112">To send content to `Set-Content` you can use the **Value** parameter on the command line or send content through the pipeline.</span></span>

<span data-ttu-id="304b0-113">Если необходимо создать файлы или каталоги для следующих примеров, см. раздел [New-Item](New-Item.md).</span><span class="sxs-lookup"><span data-stu-id="304b0-113">If you need to create files or directories for the following examples, see [New-Item](New-Item.md).</span></span>

## <span data-ttu-id="304b0-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="304b0-114">EXAMPLES</span></span>

### <span data-ttu-id="304b0-115">Пример 1. Замена содержимого нескольких файлов в каталоге</span><span class="sxs-lookup"><span data-stu-id="304b0-115">Example 1: Replace the contents of multiple files in a directory</span></span>

<span data-ttu-id="304b0-116">Этот пример заменяет содержимое для нескольких файлов в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="304b0-116">This example replaces the content for multiple files in the current directory.</span></span>

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

<span data-ttu-id="304b0-117">`Get-ChildItem`Командлет использует параметр **path** для вывода файлов **. txt** , начинающихся с `Test*` в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="304b0-117">The `Get-ChildItem` cmdlet uses the **Path** parameter to list **.txt** files that begin with `Test*` in the current directory.</span></span> <span data-ttu-id="304b0-118">`Set-Content`Командлет использует параметр **path** для указания `Test*.txt` файлов.</span><span class="sxs-lookup"><span data-stu-id="304b0-118">The `Set-Content` cmdlet uses the **Path** parameter to specify the `Test*.txt` files.</span></span> <span data-ttu-id="304b0-119">Параметр **value** предоставляет текстовую строку **Hello, World** , заменяющую существующее содержимое в каждом файле.</span><span class="sxs-lookup"><span data-stu-id="304b0-119">The **Value** parameter provides the text string **Hello, World** that replaces the existing content in each file.</span></span> <span data-ttu-id="304b0-120">`Get-Content`Командлет использует параметр **path** для указания `Test*.txt` файлов и отображает содержимое каждого файла в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="304b0-120">The `Get-Content` cmdlet uses the **Path** parameter to specify the `Test*.txt` files and displays each file's content in the PowerShell console.</span></span>

### <span data-ttu-id="304b0-121">Пример 2. Создание нового файла и запись содержимого</span><span class="sxs-lookup"><span data-stu-id="304b0-121">Example 2: Create a new file and write content</span></span>

<span data-ttu-id="304b0-122">В этом примере создается новый файл и записывается текущая дата и время в файл.</span><span class="sxs-lookup"><span data-stu-id="304b0-122">This example creates a new file and writes the current date and time to the file.</span></span>

```powershell
Set-Content -Path .\DateTime.txt -Value (Get-Date)
Get-Content -Path .\DateTime.txt
```

```Output
1/30/2019 09:55:08
```

<span data-ttu-id="304b0-123">`Set-Content` использует параметры **path** и **value** для создания нового файла с именем **DateTime.txt** в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="304b0-123">`Set-Content` uses the **Path** and **Value** parameters to create a new file named **DateTime.txt** in the current directory.</span></span> <span data-ttu-id="304b0-124">Параметр **value** используется `Get-Date` для получения текущих даты и времени.</span><span class="sxs-lookup"><span data-stu-id="304b0-124">The **Value** parameter uses `Get-Date` to get the current date and time.</span></span>
<span data-ttu-id="304b0-125">`Set-Content` Записывает объект **DateTime** в файл в виде строки.</span><span class="sxs-lookup"><span data-stu-id="304b0-125">`Set-Content` writes the **DateTime** object to the file as a string.</span></span> <span data-ttu-id="304b0-126">`Get-Content`Командлет использует параметр **path** для вывода содержимого **DateTime.txt** в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="304b0-126">The `Get-Content` cmdlet uses the **Path** parameter to display the content of **DateTime.txt** in the PowerShell console.</span></span>

### <span data-ttu-id="304b0-127">Пример 3. Замена текста в файле</span><span class="sxs-lookup"><span data-stu-id="304b0-127">Example 3: Replace text in a file</span></span>

<span data-ttu-id="304b0-128">Эта команда заменяет все экземпляры Word в существующем файле.</span><span class="sxs-lookup"><span data-stu-id="304b0-128">This command replaces all instances of word within an existing file.</span></span>

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

<span data-ttu-id="304b0-129">`Get-Content`Командлет использует параметр **path** для указания файла **Notice.txt** в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="304b0-129">The `Get-Content` cmdlet uses the **Path** parameter to specify the **Notice.txt** file in the current directory.</span></span> <span data-ttu-id="304b0-130">`Get-Content`Команда заключена в круглые скобки, чтобы команда закончится перед отправкой конвейера.</span><span class="sxs-lookup"><span data-stu-id="304b0-130">The `Get-Content` command is wrapped with parentheses so that the command finishes before being sent down the pipeline.</span></span>

<span data-ttu-id="304b0-131">Содержимое файла **Notice.txt** отправляется в командлет по конвейеру `ForEach-Object` .</span><span class="sxs-lookup"><span data-stu-id="304b0-131">The contents of the **Notice.txt** file are sent down the pipeline to the `ForEach-Object` cmdlet.</span></span>
<span data-ttu-id="304b0-132">`ForEach-Object` использует автоматическую переменную `$_` и заменяет каждое вхождение **предупреждения** с **осторожностью** .</span><span class="sxs-lookup"><span data-stu-id="304b0-132">`ForEach-Object` uses the automatic variable `$_` and replaces each occurrence of **Warning** with **Caution** .</span></span> <span data-ttu-id="304b0-133">Объекты отправляются по конвейеру в `Set-Content` командлет.</span><span class="sxs-lookup"><span data-stu-id="304b0-133">The objects are sent down the pipeline to the `Set-Content` cmdlet.</span></span> <span data-ttu-id="304b0-134">`Set-Content` использует параметр **path** для указания файла **Notice.txt** и записи обновленного содержимого в файл.</span><span class="sxs-lookup"><span data-stu-id="304b0-134">`Set-Content` uses the **Path** parameter to specify the **Notice.txt** file and writes the updated content to the file.</span></span>

<span data-ttu-id="304b0-135">Последний `Get-Content` командлет отображает обновленное содержимое файла в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="304b0-135">The last `Get-Content` cmdlet displays the updated file content in the PowerShell console.</span></span>

### <span data-ttu-id="304b0-136">Пример 4. Использование фильтров с Set-Content</span><span class="sxs-lookup"><span data-stu-id="304b0-136">Example 4: Use Filters with Set-Content</span></span>

<span data-ttu-id="304b0-137">Можно указать фильтр для `Set-Content` командлета.</span><span class="sxs-lookup"><span data-stu-id="304b0-137">You can specify a filter to the `Set-Content` cmdlet.</span></span> <span data-ttu-id="304b0-138">При использовании фильтров для уточнения параметра **path** необходимо включить конечную звездочку ( `*` ), чтобы указать содержимое пути.</span><span class="sxs-lookup"><span data-stu-id="304b0-138">When using filters to qualify the **Path** parameter, you need to include a trailing asterisk (`*`) to indicate the contents of the path.</span></span>

<span data-ttu-id="304b0-139">Следующая команда задает для содержимого всех `*.txt` файлов в `C:\Temp` каталоге пустое **значение** .</span><span class="sxs-lookup"><span data-stu-id="304b0-139">The following command set the content all `*.txt` files in the `C:\Temp` directory to the **Value** empty.</span></span>

```powershell
Set-Content -Path C:\Temp\* -Filter *.txt -Value "Empty"
```

## <span data-ttu-id="304b0-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="304b0-140">PARAMETERS</span></span>

### <span data-ttu-id="304b0-141">-Credential</span><span class="sxs-lookup"><span data-stu-id="304b0-141">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="304b0-142">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="304b0-142">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="304b0-143">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="304b0-143">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="304b0-144">-Encoding</span><span class="sxs-lookup"><span data-stu-id="304b0-144">-Encoding</span></span>

<span data-ttu-id="304b0-145">Указывает тип кодировки для целевого файла.</span><span class="sxs-lookup"><span data-stu-id="304b0-145">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="304b0-146">Значение по умолчанию — `Default`.</span><span class="sxs-lookup"><span data-stu-id="304b0-146">The default value is `Default`.</span></span>

<span data-ttu-id="304b0-147">Кодирование — это динамический параметр, к которому добавляется поставщик FileSystem `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="304b0-147">Encoding is a dynamic parameter that the FileSystem provider adds to `Set-Content`.</span></span> <span data-ttu-id="304b0-148">Этот параметр работает только на дисках с файловой системой.</span><span class="sxs-lookup"><span data-stu-id="304b0-148">This parameter works only in file system drives.</span></span>

<span data-ttu-id="304b0-149">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="304b0-149">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="304b0-150">`Ascii` Использует кодировку ASCII (7-разрядных).</span><span class="sxs-lookup"><span data-stu-id="304b0-150">`Ascii` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="304b0-151">`BigEndianUnicode` Использует UTF-16 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="304b0-151">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="304b0-152">`BigEndianUTF32` Использует UTF-32 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="304b0-152">`BigEndianUTF32` Uses UTF-32 with the big-endian byte order.</span></span>
- <span data-ttu-id="304b0-153">`Byte` Кодирует набор символов в последовательность байтов.</span><span class="sxs-lookup"><span data-stu-id="304b0-153">`Byte` Encodes a set of characters into a sequence of bytes.</span></span>
- <span data-ttu-id="304b0-154">`Default` Использует кодировку, соответствующую активной кодовой странице системы (обычно ANSI).</span><span class="sxs-lookup"><span data-stu-id="304b0-154">`Default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="304b0-155">`Oem` Использует кодировку, соответствующую текущей кодовой странице OEM системы.</span><span class="sxs-lookup"><span data-stu-id="304b0-155">`Oem` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="304b0-156">`String` аналогичен `Unicode`.</span><span class="sxs-lookup"><span data-stu-id="304b0-156">`String` Same as `Unicode`.</span></span>
- <span data-ttu-id="304b0-157">`Unicode` Использует UTF-16 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="304b0-157">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="304b0-158">`Unknown` аналогичен `Unicode`.</span><span class="sxs-lookup"><span data-stu-id="304b0-158">`Unknown` Same as `Unicode`.</span></span>
- <span data-ttu-id="304b0-159">`UTF7` Использует UTF-7.</span><span class="sxs-lookup"><span data-stu-id="304b0-159">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="304b0-160">`UTF8` Использует UTF-8.</span><span class="sxs-lookup"><span data-stu-id="304b0-160">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="304b0-161">`UTF32` Использует UTF-32 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="304b0-161">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

<span data-ttu-id="304b0-162">Кодирование — это динамический параметр, к которому добавляется поставщик FileSystem `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="304b0-162">Encoding is a dynamic parameter that the FileSystem provider adds to `Set-Content`.</span></span> <span data-ttu-id="304b0-163">Этот параметр работает только на дисках с файловой системой.</span><span class="sxs-lookup"><span data-stu-id="304b0-163">This parameter works only in file system drives.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, Byte, Default, OEM, String, Unicode, Unknown, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="304b0-164">-Exclude</span><span class="sxs-lookup"><span data-stu-id="304b0-164">-Exclude</span></span>

<span data-ttu-id="304b0-165">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="304b0-165">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="304b0-166">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="304b0-166">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="304b0-167">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="304b0-167">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="304b0-168">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="304b0-168">Wildcard characters are permitted.</span></span> <span data-ttu-id="304b0-169">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="304b0-169">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="304b0-170">-Filter</span><span class="sxs-lookup"><span data-stu-id="304b0-170">-Filter</span></span>

<span data-ttu-id="304b0-171">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="304b0-171">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="304b0-172">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="304b0-172">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="304b0-173">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="304b0-173">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="304b0-174">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="304b0-174">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="304b0-175">-Force</span><span class="sxs-lookup"><span data-stu-id="304b0-175">-Force</span></span>

<span data-ttu-id="304b0-176">Заставляет командлет задать содержимое файла, даже если он доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="304b0-176">Forces the cmdlet to set the contents of a file, even if the file is read-only.</span></span> <span data-ttu-id="304b0-177">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="304b0-177">Implementation varies from provider to provider.</span></span> <span data-ttu-id="304b0-178">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="304b0-178">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
<span data-ttu-id="304b0-179">Параметр **Force** не переопределяет ограничения безопасности.</span><span class="sxs-lookup"><span data-stu-id="304b0-179">The **Force** parameter does not override security restrictions.</span></span>

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

### <span data-ttu-id="304b0-180">-Include</span><span class="sxs-lookup"><span data-stu-id="304b0-180">-Include</span></span>

<span data-ttu-id="304b0-181">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="304b0-181">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="304b0-182">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="304b0-182">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="304b0-183">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="304b0-183">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="304b0-184">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="304b0-184">Wildcard characters are permitted.</span></span> <span data-ttu-id="304b0-185">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="304b0-185">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="304b0-186">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="304b0-186">-LiteralPath</span></span>

<span data-ttu-id="304b0-187">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="304b0-187">Specifies a path to one or more locations.</span></span> <span data-ttu-id="304b0-188">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="304b0-188">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="304b0-189">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="304b0-189">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="304b0-190">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="304b0-190">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="304b0-191">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="304b0-191">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="304b0-192">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="304b0-192">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="304b0-193">-Новая строка</span><span class="sxs-lookup"><span data-stu-id="304b0-193">-NoNewline</span></span>

<span data-ttu-id="304b0-194">Строковые представления входных объектов сцепляются для формирования выходных данных.</span><span class="sxs-lookup"><span data-stu-id="304b0-194">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="304b0-195">Между выходными строками не вставляются пробелы и символы новой строки.</span><span class="sxs-lookup"><span data-stu-id="304b0-195">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="304b0-196">После последней выходной строки не добавляется новая строка.</span><span class="sxs-lookup"><span data-stu-id="304b0-196">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="304b0-197">-PassThru</span><span class="sxs-lookup"><span data-stu-id="304b0-197">-PassThru</span></span>

<span data-ttu-id="304b0-198">Возвращает объект, представляющий содержимое.</span><span class="sxs-lookup"><span data-stu-id="304b0-198">Returns an object that represents the content.</span></span> <span data-ttu-id="304b0-199">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="304b0-199">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="304b0-200">-Path</span><span class="sxs-lookup"><span data-stu-id="304b0-200">-Path</span></span>

<span data-ttu-id="304b0-201">Указывает путь к элементу, который получает содержимое.</span><span class="sxs-lookup"><span data-stu-id="304b0-201">Specifies the path of the item that receives the content.</span></span>
<span data-ttu-id="304b0-202">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="304b0-202">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="304b0-203">-Stream</span><span class="sxs-lookup"><span data-stu-id="304b0-203">-Stream</span></span>

<span data-ttu-id="304b0-204">Указывает альтернативный поток данных для содержимого.</span><span class="sxs-lookup"><span data-stu-id="304b0-204">Specifies an alternative data stream for content.</span></span> <span data-ttu-id="304b0-205">Если поток не существует, этот командлет создаст его.</span><span class="sxs-lookup"><span data-stu-id="304b0-205">If the stream does not exist, this cmdlet creates it.</span></span> <span data-ttu-id="304b0-206">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="304b0-206">Wildcard characters are not supported.</span></span>

<span data-ttu-id="304b0-207">**Stream** — это динамический параметр, к которому добавляется поставщик **FileSystem** `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="304b0-207">**Stream** is a dynamic parameter that the **FileSystem** provider adds to `Set-Content`.</span></span> <span data-ttu-id="304b0-208">Этот параметр работает только на дисках с файловой системой.</span><span class="sxs-lookup"><span data-stu-id="304b0-208">This parameter works only in file system drives.</span></span>

<span data-ttu-id="304b0-209">`Set-Content`С помощью командлета можно изменить содержимое **зоны.** альтернативный поток данных идентификатора.</span><span class="sxs-lookup"><span data-stu-id="304b0-209">You can use the `Set-Content` cmdlet to change the content of the **Zone.Identifier** alternate data stream.</span></span> <span data-ttu-id="304b0-210">Однако не рекомендуется использовать этот способ для устранения проверок безопасности, блокирующих файлы, загружаемые из Интернета.</span><span class="sxs-lookup"><span data-stu-id="304b0-210">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="304b0-211">Если вы убедитесь, что скачанный файл является надежным, используйте `Unblock-File` командлет.</span><span class="sxs-lookup"><span data-stu-id="304b0-211">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="304b0-212">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="304b0-212">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="304b0-213">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="304b0-213">-UseTransaction</span></span>

<span data-ttu-id="304b0-214">Включает команду в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="304b0-214">Includes the command in the active transaction.</span></span> <span data-ttu-id="304b0-215">Этот параметр доступен только при выполнении транзакции.</span><span class="sxs-lookup"><span data-stu-id="304b0-215">This parameter is valid only when a transaction is in progress.</span></span> <span data-ttu-id="304b0-216">Дополнительные сведения см. в разделе [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span><span class="sxs-lookup"><span data-stu-id="304b0-216">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="304b0-217">-Value</span><span class="sxs-lookup"><span data-stu-id="304b0-217">-Value</span></span>

<span data-ttu-id="304b0-218">Указывает новое содержимое для элемента.</span><span class="sxs-lookup"><span data-stu-id="304b0-218">Specifies the new content for the item.</span></span>

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

### <span data-ttu-id="304b0-219">-Confirm</span><span class="sxs-lookup"><span data-stu-id="304b0-219">-Confirm</span></span>

<span data-ttu-id="304b0-220">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="304b0-220">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="304b0-221">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="304b0-221">-WhatIf</span></span>

<span data-ttu-id="304b0-222">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="304b0-222">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="304b0-223">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="304b0-223">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="304b0-224">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="304b0-224">CommonParameters</span></span>

<span data-ttu-id="304b0-225">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="304b0-225">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span>
<span data-ttu-id="304b0-226">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="304b0-226">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="304b0-227">Входные данные</span><span class="sxs-lookup"><span data-stu-id="304b0-227">INPUTS</span></span>

### <span data-ttu-id="304b0-228">System.Object</span><span class="sxs-lookup"><span data-stu-id="304b0-228">System.Object</span></span>

<span data-ttu-id="304b0-229">Объект, содержащий новое значение для элемента, можно передать по конвейеру `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="304b0-229">You can pipe an object that contains the new value for the item to `Set-Content`.</span></span>

## <span data-ttu-id="304b0-230">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="304b0-230">OUTPUTS</span></span>

### <span data-ttu-id="304b0-231">Нет или System.String</span><span class="sxs-lookup"><span data-stu-id="304b0-231">None or System.String</span></span>

<span data-ttu-id="304b0-232">При использовании параметра **PassThru** `Set-Content` создает объект **System. String** , представляющий содержимое.</span><span class="sxs-lookup"><span data-stu-id="304b0-232">When you use the **PassThru** parameter, `Set-Content` generates a **System.String** object that represents the content.</span></span> <span data-ttu-id="304b0-233">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="304b0-233">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="304b0-234">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="304b0-234">NOTES</span></span>

- <span data-ttu-id="304b0-235">Также можно ссылаться `Set-Content` по встроенному псевдониму `sc` .</span><span class="sxs-lookup"><span data-stu-id="304b0-235">You can also refer to `Set-Content` by its built-in alias, `sc`.</span></span>
  <span data-ttu-id="304b0-236">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="304b0-236">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="304b0-237">`Set-Content` предназначен для обработки строк.</span><span class="sxs-lookup"><span data-stu-id="304b0-237">`Set-Content` is designed for string processing.</span></span> <span data-ttu-id="304b0-238">При передаче нестроковых объектов в `Set-Content` объект преобразуется в строку перед записью.</span><span class="sxs-lookup"><span data-stu-id="304b0-238">If you pipe non-string objects to `Set-Content`, it converts the object to a string before writing it.</span></span> <span data-ttu-id="304b0-239">Для записи объектов в файлы используйте `Out-File` .</span><span class="sxs-lookup"><span data-stu-id="304b0-239">To write objects to files, use `Out-File`.</span></span>
- <span data-ttu-id="304b0-240">`Set-Content`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="304b0-240">The `Set-Content` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="304b0-241">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PsProvider`.</span><span class="sxs-lookup"><span data-stu-id="304b0-241">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="304b0-242">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="304b0-242">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="304b0-243">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="304b0-243">RELATED LINKS</span></span>

[<span data-ttu-id="304b0-244">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="304b0-244">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="304b0-245">about_Automatic_Variables. md</span><span class="sxs-lookup"><span data-stu-id="304b0-245">about_Automatic_Variables.md</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[<span data-ttu-id="304b0-246">about_Providers</span><span class="sxs-lookup"><span data-stu-id="304b0-246">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="304b0-247">about_Transactions</span><span class="sxs-lookup"><span data-stu-id="304b0-247">about_Transactions</span></span>](../Microsoft.PowerShell.Core/About/about_Transactions.md)

[<span data-ttu-id="304b0-248">Add-Content</span><span class="sxs-lookup"><span data-stu-id="304b0-248">Add-Content</span></span>](Add-Content.md)

[<span data-ttu-id="304b0-249">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="304b0-249">Clear-Content</span></span>](Clear-Content.md)

[<span data-ttu-id="304b0-250">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="304b0-250">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="304b0-251">Get-Content</span><span class="sxs-lookup"><span data-stu-id="304b0-251">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="304b0-252">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="304b0-252">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="304b0-253">New-Item</span><span class="sxs-lookup"><span data-stu-id="304b0-253">New-Item</span></span>](New-Item.md)
