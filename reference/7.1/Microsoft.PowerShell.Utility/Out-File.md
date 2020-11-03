---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-file?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-File
ms.openlocfilehash: 3a3d431276074d7c2b66b442307071076fdfebd5
ms.sourcegitcommit: d757d64ea8c8af4d92596e8fbe15f2f40d48d3ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "93230682"
---
# <span data-ttu-id="fe7ff-103">Out-File</span><span class="sxs-lookup"><span data-stu-id="fe7ff-103">Out-File</span></span>

## <span data-ttu-id="fe7ff-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="fe7ff-104">SYNOPSIS</span></span>
<span data-ttu-id="fe7ff-105">Отправляет выходные данные в файл.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-105">Sends output to a file.</span></span>

## <span data-ttu-id="fe7ff-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fe7ff-106">SYNTAX</span></span>

### <span data-ttu-id="fe7ff-107">ByPath (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="fe7ff-107">ByPath (Default)</span></span>

```
Out-File [-FilePath] <string> [[-Encoding] <Encoding>] [-Append] [-Force] [-NoClobber]
 [-Width <int>] [-NoNewline] [-InputObject <psobject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="fe7ff-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="fe7ff-108">ByLiteralPath</span></span>

```
Out-File [[-Encoding] <Encoding>] -LiteralPath <string> [-Append] [-Force] [-NoClobber]
 [-Width <int>] [-NoNewline] [-InputObject <psobject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="fe7ff-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fe7ff-109">DESCRIPTION</span></span>

<span data-ttu-id="fe7ff-110">`Out-File`Командлет отправляет выходные данные в файл.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-110">The `Out-File` cmdlet sends output to a file.</span></span> <span data-ttu-id="fe7ff-111">Он неявно использует систему форматирования PowerShell для записи в файл.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-111">It implicitly uses PowerShell's formatting system to write to the file.</span></span> <span data-ttu-id="fe7ff-112">Файл получает то же отображаемое представление, что и терминал.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-112">The file receives the same display representation as the terminal.</span></span> <span data-ttu-id="fe7ff-113">Это означает, что выходные данные могут быть неидеальными для программной обработки, если только все входные объекты не являются строками.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-113">This means that the output may not be ideal for programmatic processing unless all input objects are strings.</span></span>
<span data-ttu-id="fe7ff-114">Если необходимо указать параметры для выходных данных, используйте `Out-File` вместо оператора перенаправления ( `>` ).</span><span class="sxs-lookup"><span data-stu-id="fe7ff-114">When you need to specify parameters for the output, use `Out-File` rather than the redirection operator (`>`).</span></span> <span data-ttu-id="fe7ff-115">Дополнительные сведения о перенаправлении см. в разделе [about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md).</span><span class="sxs-lookup"><span data-stu-id="fe7ff-115">For more information about redirection, see [about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md).</span></span>

## <span data-ttu-id="fe7ff-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="fe7ff-116">EXAMPLES</span></span>

### <span data-ttu-id="fe7ff-117">Пример 1. Отправка выходных данных и создание файла</span><span class="sxs-lookup"><span data-stu-id="fe7ff-117">Example 1: Send output and create a file</span></span>

<span data-ttu-id="fe7ff-118">В этом примере показано, как отправить список процессов локального компьютера в файл.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-118">This example shows how to send a list of the local computer's processes to a file.</span></span> <span data-ttu-id="fe7ff-119">Если файл не существует, `Out-File` создает файл по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-119">If the file does not exist, `Out-File` creates the file in the specified path.</span></span>

```powershell
Get-Process | Out-File -FilePath .\Process.txt
Get-Content -Path .\Process.txt
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     29    22.39      35.40      10.98   42764   9 Application
     53    99.04     113.96       0.00   32664   0 CcmExec
     27    96.62     112.43     113.00   17720   9 Code
```

<span data-ttu-id="fe7ff-120">`Get-Process`Командлет возвращает список процессов, запущенных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-120">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="fe7ff-121">Объекты **процесса** отправляются по конвейеру в `Out-File` командлет.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-121">The **Process** objects are sent down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="fe7ff-122">`Out-File` использует параметр **FilePath** и создает файл в текущем каталоге с именем **Process.txt** .</span><span class="sxs-lookup"><span data-stu-id="fe7ff-122">`Out-File` uses the **FilePath** parameter and creates a file in the current directory named **Process.txt** .</span></span> <span data-ttu-id="fe7ff-123">`Get-Content`Команда получает содержимое из файла и отображает его в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-123">The `Get-Content` command gets content from the file and displays it in the PowerShell console.</span></span>

### <span data-ttu-id="fe7ff-124">Пример 2. запрет перезаписи существующего файла</span><span class="sxs-lookup"><span data-stu-id="fe7ff-124">Example 2: Prevent an existing file from being overwritten</span></span>

<span data-ttu-id="fe7ff-125">Этот пример предотвращает перезапись существующего файла.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-125">This example prevents an existing file from being overwritten.</span></span> <span data-ttu-id="fe7ff-126">По умолчанию `Out-File` перезаписывает существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-126">By default, `Out-File` overwrites existing files.</span></span>

```powershell
Get-Process | Out-File -FilePath .\Process.txt -NoClobber
```

```Output
Out-File : The file 'C:\Test\Process.txt' already exists.
At line:1 char:15
+ Get-Process | Out-File -FilePath .\Process.txt -NoClobber
+               ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
```

<span data-ttu-id="fe7ff-127">`Get-Process`Командлет возвращает список процессов, запущенных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-127">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="fe7ff-128">Объекты **процесса** отправляются по конвейеру в `Out-File` командлет.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-128">The **Process** objects are sent down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="fe7ff-129">`Out-File` использует параметр **FilePath** и пытается выполнить запись в файл в текущем каталоге с именем **Process.txt** .</span><span class="sxs-lookup"><span data-stu-id="fe7ff-129">`Out-File` uses the **FilePath** parameter and attempts to write to a file in the current directory named **Process.txt** .</span></span> <span data-ttu-id="fe7ff-130">Параметр **NoClobber** предотвращает перезапись файла и выводит сообщение о том, что файл уже существует.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-130">The **NoClobber** parameter prevents the file from being overwritten and displays a message that the file already exists.</span></span>

### <span data-ttu-id="fe7ff-131">Пример 3. Отправка выходных данных в файл в формате ASCII</span><span class="sxs-lookup"><span data-stu-id="fe7ff-131">Example 3: Send output to a file in ASCII format</span></span>

<span data-ttu-id="fe7ff-132">В этом примере показано, как кодировать выходные данные с конкретным типом кодирования.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-132">This example shows how to encode output with a specific encoding type.</span></span>

```powershell
$Procs = Get-Process
Out-File -FilePath .\Process.txt -InputObject $Procs -Encoding ASCII -Width 50
```

<span data-ttu-id="fe7ff-133">`Get-Process`Командлет возвращает список процессов, запущенных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-133">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="fe7ff-134">Объекты **процесса** хранятся в переменной `$Procs` .</span><span class="sxs-lookup"><span data-stu-id="fe7ff-134">The **Process** objects are stored in the variable, `$Procs`.</span></span> <span data-ttu-id="fe7ff-135">`Out-File` использует параметр **FilePath** и создает файл в текущем каталоге с именем **Process.txt** .</span><span class="sxs-lookup"><span data-stu-id="fe7ff-135">`Out-File` uses the **FilePath** parameter and creates a file in the current directory named **Process.txt** .</span></span> <span data-ttu-id="fe7ff-136">Параметр **InputObject** передает объекты процесса в `$Procs` файл **Process.txt** .</span><span class="sxs-lookup"><span data-stu-id="fe7ff-136">The **InputObject** parameter passes the process objects in `$Procs` to the file **Process.txt** .</span></span> <span data-ttu-id="fe7ff-137">Параметр **Encoding** преобразует выходные данные в формат **ASCII** .</span><span class="sxs-lookup"><span data-stu-id="fe7ff-137">The **Encoding** parameter converts the output to **ASCII** format.</span></span> <span data-ttu-id="fe7ff-138">Параметр **Width** ограничивает каждую строку в файле на 50 символов, чтобы некоторые данные могли быть обрезаны.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-138">The **Width** parameter limits each line in the file to 50 characters so some data might be truncated.</span></span>

### <span data-ttu-id="fe7ff-139">Пример 4. Использование поставщика и отправка выходных данных в файл</span><span class="sxs-lookup"><span data-stu-id="fe7ff-139">Example 4: Use a provider and send output to a file</span></span>

<span data-ttu-id="fe7ff-140">В этом примере показано, как использовать `Out-File` командлет, если вы не используете диск поставщика **FileSystem** .</span><span class="sxs-lookup"><span data-stu-id="fe7ff-140">This example shows how to use the `Out-File` cmdlet when you are not in a **FileSystem** provider drive.</span></span> <span data-ttu-id="fe7ff-141">Используйте `Get-PSProvider` командлет для просмотра поставщиков на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-141">Use the `Get-PSProvider` cmdlet to view the providers on your local computer.</span></span> <span data-ttu-id="fe7ff-142">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.Powershell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="fe7ff-142">For more information, see [about_Providers](../Microsoft.Powershell.Core/About/about_Providers.md).</span></span>

```
PS> Set-Location -Path Alias:

PS> Get-Location

Path
----
Alias:\

PS> Get-ChildItem | Out-File -FilePath C:\TestDir\AliasNames.txt

PS> Get-Content -Path C:\TestDir\AliasNames.txt

CommandType     Name
-----------     ----
Alias           % -> ForEach-Object
Alias           ? -> Where-Object
Alias           ac -> Add-Content
Alias           cat -> Get-Content
```

<span data-ttu-id="fe7ff-143">`Set-Location`Команда использует параметр **path** , чтобы задать текущее расположение для поставщика реестра `Alias:` .</span><span class="sxs-lookup"><span data-stu-id="fe7ff-143">The `Set-Location` command uses the **Path** parameter to set the current location to the registry provider `Alias:`.</span></span> <span data-ttu-id="fe7ff-144">`Get-Location`Командлет выводит полный путь для `Alias:` .</span><span class="sxs-lookup"><span data-stu-id="fe7ff-144">The `Get-Location` cmdlet displays the complete path for `Alias:`.</span></span>
<span data-ttu-id="fe7ff-145">`Get-ChildItem` отправляет объекты по конвейеру в `Out-File` командлет.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-145">`Get-ChildItem` sends objects down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="fe7ff-146">`Out-File` использует параметр **FilePath** для указания полного пути и имени файла выходных данных, **C:\TestDir\AliasNames.txt** .</span><span class="sxs-lookup"><span data-stu-id="fe7ff-146">`Out-File` uses the **FilePath** parameter to specify the complete path and filename for the output, **C:\TestDir\AliasNames.txt** .</span></span> <span data-ttu-id="fe7ff-147">`Get-Content`Командлет использует параметр **path** и отображает содержимое файла в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-147">The `Get-Content` cmdlet uses the **Path** parameter and displays the file's content in the PowerShell console.</span></span>

## <span data-ttu-id="fe7ff-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fe7ff-148">PARAMETERS</span></span>

### <span data-ttu-id="fe7ff-149">— Добавление</span><span class="sxs-lookup"><span data-stu-id="fe7ff-149">-Append</span></span>

<span data-ttu-id="fe7ff-150">Добавляет выходные данные в конец существующего файла.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-150">Adds the output to the end of an existing file.</span></span>

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

### <span data-ttu-id="fe7ff-151">-Encoding</span><span class="sxs-lookup"><span data-stu-id="fe7ff-151">-Encoding</span></span>

<span data-ttu-id="fe7ff-152">Указывает тип кодировки для целевого файла.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-152">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="fe7ff-153">Значение по умолчанию — `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-153">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="fe7ff-154">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="fe7ff-154">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="fe7ff-155">`ascii`: Использует кодировку для набора символов ASCII (7-разрядных).</span><span class="sxs-lookup"><span data-stu-id="fe7ff-155">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="fe7ff-156">`bigendianunicode`: Кодируется в формате UTF-16 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-156">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="fe7ff-157">`bigendianutf32`: Кодируется в формате UTF-32 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-157">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="fe7ff-158">`oem`: Использует кодировку по умолчанию для программ MS-DOS и консолей.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-158">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="fe7ff-159">`unicode`: Кодируется в формате UTF-16 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-159">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="fe7ff-160">`utf7`: Кодируется в формате UTF-7.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-160">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="fe7ff-161">`utf8`: Кодируется в формате UTF-8.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-161">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="fe7ff-162">`utf8BOM`: Кодирует в формате UTF-8 с меткой порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="fe7ff-162">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="fe7ff-163">`utf8NoBOM`: Кодирует в формате UTF-8 без метки порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="fe7ff-163">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="fe7ff-164">`utf32`: Кодируется в формате UTF-32.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-164">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="fe7ff-165">Начиная с PowerShell 6,2, параметр **кодировки** также разрешает числовые идентификаторы зарегистрированных кодовых страниц (например `-Encoding 1251` ,) или строковых имен зарегистрированных кодовых страниц (например `-Encoding "windows-1251"` ,).</span><span class="sxs-lookup"><span data-stu-id="fe7ff-165">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="fe7ff-166">Дополнительные сведения см. в документации .NET по [кодированию. codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="fe7ff-166">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

> [!NOTE]
> <span data-ttu-id="fe7ff-167">Больше не рекомендуется использовать **UTF-7** \*.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-167">**UTF-7** \* is no longer recommended to use.</span></span> <span data-ttu-id="fe7ff-168">В PowerShell 7,1 при указании параметра Encoding записывается предупреждение `utf7` . **Encoding**</span><span class="sxs-lookup"><span data-stu-id="fe7ff-168">In PowerShell 7.1, a warning is written if you specify `utf7` for the **Encoding** parameter.</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: 1
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fe7ff-169">-FilePath</span><span class="sxs-lookup"><span data-stu-id="fe7ff-169">-FilePath</span></span>

<span data-ttu-id="fe7ff-170">Указывает путь к выходному файлу.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-170">Specifies the path to the output file.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases: Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fe7ff-171">-Force</span><span class="sxs-lookup"><span data-stu-id="fe7ff-171">-Force</span></span>

<span data-ttu-id="fe7ff-172">Переопределяет атрибут, доступный только для чтения, и перезаписывает существующий файл, доступный только для чтения.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-172">Overrides the read-only attribute and overwrites an existing read-only file.</span></span> <span data-ttu-id="fe7ff-173">Параметр **Force** не переопределяет ограничения безопасности.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-173">The **Force** parameter does not override security restrictions.</span></span>

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

### <span data-ttu-id="fe7ff-174">-InputObject</span><span class="sxs-lookup"><span data-stu-id="fe7ff-174">-InputObject</span></span>

<span data-ttu-id="fe7ff-175">Указывает объекты, которые нужно записать в файл.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-175">Specifies the objects to be written to the file.</span></span> <span data-ttu-id="fe7ff-176">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-176">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="fe7ff-177">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="fe7ff-177">-LiteralPath</span></span>

<span data-ttu-id="fe7ff-178">Указывает путь к выходному файлу.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-178">Specifies the path to the output file.</span></span> <span data-ttu-id="fe7ff-179">Параметр **LiteralPath** используется точно так же, как он типизирован.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-179">The **LiteralPath** parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="fe7ff-180">Подстановочные знаки не допускаются.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-180">Wildcard characters are not accepted.</span></span> <span data-ttu-id="fe7ff-181">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-181">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="fe7ff-182">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-182">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span> <span data-ttu-id="fe7ff-183">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="fe7ff-183">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fe7ff-184">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="fe7ff-184">-NoClobber</span></span>

<span data-ttu-id="fe7ff-185">**NoClobber** предотвращает перезапись существующего файла и выводит сообщение о том, что файл уже существует.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-185">**NoClobber** prevents an existing file from being overwritten and displays a message that the file already exists.</span></span> <span data-ttu-id="fe7ff-186">По умолчанию, если файл существует по указанному пути, `Out-File` перезаписывает файл без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-186">By default, if a file exists in the specified path, `Out-File` overwrites the file without warning.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fe7ff-187">-Новая строка</span><span class="sxs-lookup"><span data-stu-id="fe7ff-187">-NoNewline</span></span>

<span data-ttu-id="fe7ff-188">Указывает, что содержимое, записанное в файл, не заканчивается символом новой строки.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-188">Specifies that the content written to the file does not end with a newline character.</span></span> <span data-ttu-id="fe7ff-189">Строковые представления входных объектов сцепляются для формирования выходных данных.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-189">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="fe7ff-190">Между выходными строками не вставляются пробелы и символы новой строки.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-190">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="fe7ff-191">После последней выходной строки не добавляется новая строка.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-191">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="fe7ff-192">-Width</span><span class="sxs-lookup"><span data-stu-id="fe7ff-192">-Width</span></span>

<span data-ttu-id="fe7ff-193">Указывает количество символов в каждой строке выходных данных.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-193">Specifies the number of characters in each line of output.</span></span> <span data-ttu-id="fe7ff-194">Все остальные знаки отсекаются, а не переносятся на следующую строку.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-194">Any additional characters are truncated, not wrapped.</span></span> <span data-ttu-id="fe7ff-195">Если этот параметр не используется, ширина определяется характеристиками узла.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-195">If this parameter is not used, the width is determined by the characteristics of the host.</span></span> <span data-ttu-id="fe7ff-196">Значение по умолчанию для консоли PowerShell — 80 символов.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-196">The default for the PowerShell console is 80 characters.</span></span>

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

### <span data-ttu-id="fe7ff-197">-Confirm</span><span class="sxs-lookup"><span data-stu-id="fe7ff-197">-Confirm</span></span>

<span data-ttu-id="fe7ff-198">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-198">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="fe7ff-199">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="fe7ff-199">-WhatIf</span></span>

<span data-ttu-id="fe7ff-200">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-200">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="fe7ff-201">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-201">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="fe7ff-202">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="fe7ff-202">CommonParameters</span></span>

<span data-ttu-id="fe7ff-203">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-203">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fe7ff-204">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fe7ff-204">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fe7ff-205">Входные данные</span><span class="sxs-lookup"><span data-stu-id="fe7ff-205">INPUTS</span></span>

### <span data-ttu-id="fe7ff-206">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="fe7ff-206">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="fe7ff-207">Любой объект можно передать по конвейеру в `Out-File` .</span><span class="sxs-lookup"><span data-stu-id="fe7ff-207">You can pipe any object to `Out-File`.</span></span>

## <span data-ttu-id="fe7ff-208">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="fe7ff-208">OUTPUTS</span></span>

### <span data-ttu-id="fe7ff-209">Нет</span><span class="sxs-lookup"><span data-stu-id="fe7ff-209">None</span></span>

<span data-ttu-id="fe7ff-210">`Out-File` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-210">`Out-File` does not generate any output.</span></span>

## <span data-ttu-id="fe7ff-211">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="fe7ff-211">NOTES</span></span>

<span data-ttu-id="fe7ff-212">Входные объекты автоматически форматируются так же, как и в терминале, но можно использовать `Format-*` командлет для явного управления форматированием выходных данных в файле.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-212">Input objects are automatically formatted as they would be in the terminal, but you can use a `Format-*` cmdlet to explicitly control the formatting of the output to the file.</span></span> <span data-ttu-id="fe7ff-213">Например `Get-Date | Format-List | Out-File out.txt`.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-213">For example, `Get-Date | Format-List | Out-File out.txt`</span></span>

<span data-ttu-id="fe7ff-214">Чтобы отправить выходные данные команды PowerShell в `Out-File` командлет, используйте конвейер.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-214">To send a PowerShell command's output to the `Out-File` cmdlet, use the pipeline.</span></span> <span data-ttu-id="fe7ff-215">Кроме того, можно хранить данные в переменной и использовать параметр **InputObject** для передачи данных в `Out-File` командлет.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-215">Alternatively, you can store data in a variable and use the **InputObject** parameter to pass data to the `Out-File` cmdlet.</span></span>

<span data-ttu-id="fe7ff-216">`Out-File` сохраняет данные в файл, но не создает выходные объекты в конвейере.</span><span class="sxs-lookup"><span data-stu-id="fe7ff-216">`Out-File` saves data to a file but it does not produce any output objects to the pipeline.</span></span>

## <span data-ttu-id="fe7ff-217">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="fe7ff-217">RELATED LINKS</span></span>

[<span data-ttu-id="fe7ff-218">about_Providers</span><span class="sxs-lookup"><span data-stu-id="fe7ff-218">about_Providers</span></span>](../Microsoft.Powershell.Core/About/about_Providers.md)

[<span data-ttu-id="fe7ff-219">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="fe7ff-219">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="fe7ff-220">Out-Default;</span><span class="sxs-lookup"><span data-stu-id="fe7ff-220">Out-Default</span></span>](../Microsoft.PowerShell.Core/Out-Default.md)

[<span data-ttu-id="fe7ff-221">Out-Host</span><span class="sxs-lookup"><span data-stu-id="fe7ff-221">Out-Host</span></span>](../Microsoft.PowerShell.Core/Out-Host.md)

[<span data-ttu-id="fe7ff-222">Out-Null</span><span class="sxs-lookup"><span data-stu-id="fe7ff-222">Out-Null</span></span>](../Microsoft.PowerShell.Core/Out-Null.md)

[<span data-ttu-id="fe7ff-223">Out-String</span><span class="sxs-lookup"><span data-stu-id="fe7ff-223">Out-String</span></span>](Out-String.md)

[<span data-ttu-id="fe7ff-224">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="fe7ff-224">Tee-Object</span></span>](Tee-Object.md)

