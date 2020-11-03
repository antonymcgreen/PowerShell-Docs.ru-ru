---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-file?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-File
ms.openlocfilehash: 71602cb0621c835257f556a0a9db15bd754a3aee
ms.sourcegitcommit: d757d64ea8c8af4d92596e8fbe15f2f40d48d3ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "93230705"
---
# <span data-ttu-id="ce083-103">Out-File</span><span class="sxs-lookup"><span data-stu-id="ce083-103">Out-File</span></span>

## <span data-ttu-id="ce083-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ce083-104">SYNOPSIS</span></span>
<span data-ttu-id="ce083-105">Отправляет выходные данные в файл.</span><span class="sxs-lookup"><span data-stu-id="ce083-105">Sends output to a file.</span></span>

## <span data-ttu-id="ce083-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ce083-106">SYNTAX</span></span>

### <span data-ttu-id="ce083-107">ByPath (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="ce083-107">ByPath (Default)</span></span>

```
Out-File [-FilePath] <string> [[-Encoding] <string>] [-Append] [-Force] [-NoClobber] [-Width <int>]
 [-NoNewline] [-InputObject <psobject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ce083-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="ce083-108">ByLiteralPath</span></span>

```
Out-File [[-Encoding] <string>] -LiteralPath <string> [-Append] [-Force] [-NoClobber] [-Width <int>]
 [-NoNewline] [-InputObject <psobject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ce083-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ce083-109">DESCRIPTION</span></span>

<span data-ttu-id="ce083-110">`Out-File`Командлет отправляет выходные данные в файл.</span><span class="sxs-lookup"><span data-stu-id="ce083-110">The `Out-File` cmdlet sends output to a file.</span></span> <span data-ttu-id="ce083-111">Он неявно использует систему форматирования PowerShell для записи в файл.</span><span class="sxs-lookup"><span data-stu-id="ce083-111">It implicitly uses PowerShell's formatting system to write to the file.</span></span> <span data-ttu-id="ce083-112">Файл получает то же отображаемое представление, что и терминал.</span><span class="sxs-lookup"><span data-stu-id="ce083-112">The file receives the same display representation as the terminal.</span></span> <span data-ttu-id="ce083-113">Это означает, что выходные данные могут быть неидеальными для программной обработки, если только все входные объекты не являются строками.</span><span class="sxs-lookup"><span data-stu-id="ce083-113">This means that the output may not be ideal for programmatic processing unless all input objects are strings.</span></span>
<span data-ttu-id="ce083-114">Если необходимо указать параметры для выходных данных, используйте `Out-File` вместо оператора перенаправления ( `>` ).</span><span class="sxs-lookup"><span data-stu-id="ce083-114">When you need to specify parameters for the output, use `Out-File` rather than the redirection operator (`>`).</span></span> <span data-ttu-id="ce083-115">Дополнительные сведения о перенаправлении см. в разделе [about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md).</span><span class="sxs-lookup"><span data-stu-id="ce083-115">For more information about redirection, see [about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md).</span></span>

## <span data-ttu-id="ce083-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="ce083-116">EXAMPLES</span></span>

### <span data-ttu-id="ce083-117">Пример 1. Отправка выходных данных и создание файла</span><span class="sxs-lookup"><span data-stu-id="ce083-117">Example 1: Send output and create a file</span></span>

<span data-ttu-id="ce083-118">В этом примере показано, как отправить список процессов локального компьютера в файл.</span><span class="sxs-lookup"><span data-stu-id="ce083-118">This example shows how to send a list of the local computer's processes to a file.</span></span> <span data-ttu-id="ce083-119">Если файл не существует, `Out-File` создает файл по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="ce083-119">If the file does not exist, `Out-File` creates the file in the specified path.</span></span>

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

<span data-ttu-id="ce083-120">`Get-Process`Командлет возвращает список процессов, запущенных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ce083-120">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="ce083-121">Объекты **процесса** отправляются по конвейеру в `Out-File` командлет.</span><span class="sxs-lookup"><span data-stu-id="ce083-121">The **Process** objects are sent down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="ce083-122">`Out-File` использует параметр **FilePath** и создает файл в текущем каталоге с именем **Process.txt** .</span><span class="sxs-lookup"><span data-stu-id="ce083-122">`Out-File` uses the **FilePath** parameter and creates a file in the current directory named **Process.txt** .</span></span> <span data-ttu-id="ce083-123">`Get-Content`Команда получает содержимое из файла и отображает его в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ce083-123">The `Get-Content` command gets content from the file and displays it in the PowerShell console.</span></span>

### <span data-ttu-id="ce083-124">Пример 2. запрет перезаписи существующего файла</span><span class="sxs-lookup"><span data-stu-id="ce083-124">Example 2: Prevent an existing file from being overwritten</span></span>

<span data-ttu-id="ce083-125">Этот пример предотвращает перезапись существующего файла.</span><span class="sxs-lookup"><span data-stu-id="ce083-125">This example prevents an existing file from being overwritten.</span></span> <span data-ttu-id="ce083-126">По умолчанию `Out-File` перезаписывает существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="ce083-126">By default, `Out-File` overwrites existing files.</span></span>

```powershell
Get-Process | Out-File -FilePath .\Process.txt -NoClobber
```

```Output
Out-File : The file 'C:\Test\Process.txt' already exists.
At line:1 char:15
+ Get-Process | Out-File -FilePath .\Process.txt -NoClobber
+               ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
```

<span data-ttu-id="ce083-127">`Get-Process`Командлет возвращает список процессов, запущенных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ce083-127">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="ce083-128">Объекты **процесса** отправляются по конвейеру в `Out-File` командлет.</span><span class="sxs-lookup"><span data-stu-id="ce083-128">The **Process** objects are sent down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="ce083-129">`Out-File` использует параметр **FilePath** и пытается выполнить запись в файл в текущем каталоге с именем **Process.txt** .</span><span class="sxs-lookup"><span data-stu-id="ce083-129">`Out-File` uses the **FilePath** parameter and attempts to write to a file in the current directory named **Process.txt** .</span></span> <span data-ttu-id="ce083-130">Параметр **NoClobber** предотвращает перезапись файла и выводит сообщение о том, что файл уже существует.</span><span class="sxs-lookup"><span data-stu-id="ce083-130">The **NoClobber** parameter prevents the file from being overwritten and displays a message that the file already exists.</span></span>

### <span data-ttu-id="ce083-131">Пример 3. Отправка выходных данных в файл в формате ASCII</span><span class="sxs-lookup"><span data-stu-id="ce083-131">Example 3: Send output to a file in ASCII format</span></span>

<span data-ttu-id="ce083-132">В этом примере показано, как кодировать выходные данные с конкретным типом кодирования.</span><span class="sxs-lookup"><span data-stu-id="ce083-132">This example shows how to encode output with a specific encoding type.</span></span>

```powershell
$Procs = Get-Process
Out-File -FilePath .\Process.txt -InputObject $Procs -Encoding ASCII -Width 50
```

<span data-ttu-id="ce083-133">`Get-Process`Командлет возвращает список процессов, запущенных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ce083-133">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="ce083-134">Объекты **процесса** хранятся в переменной `$Procs` .</span><span class="sxs-lookup"><span data-stu-id="ce083-134">The **Process** objects are stored in the variable, `$Procs`.</span></span> <span data-ttu-id="ce083-135">`Out-File` использует параметр **FilePath** и создает файл в текущем каталоге с именем **Process.txt** .</span><span class="sxs-lookup"><span data-stu-id="ce083-135">`Out-File` uses the **FilePath** parameter and creates a file in the current directory named **Process.txt** .</span></span> <span data-ttu-id="ce083-136">Параметр **InputObject** передает объекты процесса в `$Procs` файл **Process.txt** .</span><span class="sxs-lookup"><span data-stu-id="ce083-136">The **InputObject** parameter passes the process objects in `$Procs` to the file **Process.txt** .</span></span> <span data-ttu-id="ce083-137">Параметр **Encoding** преобразует выходные данные в формат **ASCII** .</span><span class="sxs-lookup"><span data-stu-id="ce083-137">The **Encoding** parameter converts the output to **ASCII** format.</span></span> <span data-ttu-id="ce083-138">Параметр **Width** ограничивает каждую строку в файле на 50 символов, чтобы некоторые данные могли быть обрезаны.</span><span class="sxs-lookup"><span data-stu-id="ce083-138">The **Width** parameter limits each line in the file to 50 characters so some data might be truncated.</span></span>

### <span data-ttu-id="ce083-139">Пример 4. Использование поставщика и отправка выходных данных в файл</span><span class="sxs-lookup"><span data-stu-id="ce083-139">Example 4: Use a provider and send output to a file</span></span>

<span data-ttu-id="ce083-140">В этом примере показано, как использовать `Out-File` командлет, если вы не используете диск поставщика **FileSystem** .</span><span class="sxs-lookup"><span data-stu-id="ce083-140">This example shows how to use the `Out-File` cmdlet when you are not in a **FileSystem** provider drive.</span></span> <span data-ttu-id="ce083-141">Используйте `Get-PSProvider` командлет для просмотра поставщиков на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ce083-141">Use the `Get-PSProvider` cmdlet to view the providers on your local computer.</span></span> <span data-ttu-id="ce083-142">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.Powershell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="ce083-142">For more information, see [about_Providers](../Microsoft.Powershell.Core/About/about_Providers.md).</span></span>

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

<span data-ttu-id="ce083-143">`Set-Location`Команда использует параметр **path** , чтобы задать текущее расположение для поставщика реестра `Alias:` .</span><span class="sxs-lookup"><span data-stu-id="ce083-143">The `Set-Location` command uses the **Path** parameter to set the current location to the registry provider `Alias:`.</span></span> <span data-ttu-id="ce083-144">`Get-Location`Командлет выводит полный путь для `Alias:` .</span><span class="sxs-lookup"><span data-stu-id="ce083-144">The `Get-Location` cmdlet displays the complete path for `Alias:`.</span></span>
<span data-ttu-id="ce083-145">`Get-ChildItem` отправляет объекты по конвейеру в `Out-File` командлет.</span><span class="sxs-lookup"><span data-stu-id="ce083-145">`Get-ChildItem` sends objects down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="ce083-146">`Out-File` использует параметр **FilePath** для указания полного пути и имени файла выходных данных, **C:\TestDir\AliasNames.txt** .</span><span class="sxs-lookup"><span data-stu-id="ce083-146">`Out-File` uses the **FilePath** parameter to specify the complete path and filename for the output, **C:\TestDir\AliasNames.txt** .</span></span> <span data-ttu-id="ce083-147">`Get-Content`Командлет использует параметр **path** и отображает содержимое файла в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ce083-147">The `Get-Content` cmdlet uses the **Path** parameter and displays the file's content in the PowerShell console.</span></span>

## <span data-ttu-id="ce083-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ce083-148">PARAMETERS</span></span>

### <span data-ttu-id="ce083-149">— Добавление</span><span class="sxs-lookup"><span data-stu-id="ce083-149">-Append</span></span>

<span data-ttu-id="ce083-150">Добавляет выходные данные в конец существующего файла.</span><span class="sxs-lookup"><span data-stu-id="ce083-150">Adds the output to the end of an existing file.</span></span> <span data-ttu-id="ce083-151">Если **Кодировка** не указана, командлет использует кодировку по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ce083-151">If no **Encoding** is specified, the cmdlet uses the default encoding.</span></span> <span data-ttu-id="ce083-152">Эта кодировка может не соответствовать кодировке целевого файла.</span><span class="sxs-lookup"><span data-stu-id="ce083-152">That encoding may not match the encoding of the target file.</span></span> <span data-ttu-id="ce083-153">Это то же поведение, что и оператор перенаправления ( `>>` ).</span><span class="sxs-lookup"><span data-stu-id="ce083-153">This is the same behavior as the redirection operator (`>>`).</span></span>

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

### <span data-ttu-id="ce083-154">-Encoding</span><span class="sxs-lookup"><span data-stu-id="ce083-154">-Encoding</span></span>

<span data-ttu-id="ce083-155">Указывает тип кодировки для целевого файла.</span><span class="sxs-lookup"><span data-stu-id="ce083-155">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="ce083-156">Значение по умолчанию — `unicode`.</span><span class="sxs-lookup"><span data-stu-id="ce083-156">The default value is `unicode`.</span></span>

<span data-ttu-id="ce083-157">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="ce083-157">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="ce083-158">`ascii` Использует кодировку ASCII (7-разрядных).</span><span class="sxs-lookup"><span data-stu-id="ce083-158">`ascii` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="ce083-159">`bigendianunicode` Использует UTF-16 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="ce083-159">`bigendianunicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="ce083-160">`default` Использует кодировку, соответствующую активной кодовой странице системы (обычно ANSI).</span><span class="sxs-lookup"><span data-stu-id="ce083-160">`default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="ce083-161">`oem` Использует кодировку, соответствующую текущей кодовой странице OEM системы.</span><span class="sxs-lookup"><span data-stu-id="ce083-161">`oem` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="ce083-162">`string` аналогичен `unicode`.</span><span class="sxs-lookup"><span data-stu-id="ce083-162">`string` Same as `unicode`.</span></span>
- <span data-ttu-id="ce083-163">`unicode` Использует UTF-16 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="ce083-163">`unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="ce083-164">`unknown` аналогичен `unicode`.</span><span class="sxs-lookup"><span data-stu-id="ce083-164">`unknown` Same as `unicode`.</span></span>
- <span data-ttu-id="ce083-165">`utf7` Использует UTF-7.</span><span class="sxs-lookup"><span data-stu-id="ce083-165">`utf7` Uses UTF-7.</span></span>
- <span data-ttu-id="ce083-166">`utf8` Использует UTF-8.</span><span class="sxs-lookup"><span data-stu-id="ce083-166">`utf8` Uses UTF-8.</span></span>
- <span data-ttu-id="ce083-167">`utf32` Использует UTF-32 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="ce083-167">`utf32` Uses UTF-32 with the little-endian byte order.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, Default, OEM, String, Unicode, Unknown, UTF7, UTF8, UTF32

Required: False
Position: 1
Default value: Unicode
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce083-168">-FilePath</span><span class="sxs-lookup"><span data-stu-id="ce083-168">-FilePath</span></span>

<span data-ttu-id="ce083-169">Указывает путь к выходному файлу.</span><span class="sxs-lookup"><span data-stu-id="ce083-169">Specifies the path to the output file.</span></span>

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ce083-170">-Force</span><span class="sxs-lookup"><span data-stu-id="ce083-170">-Force</span></span>

<span data-ttu-id="ce083-171">Переопределяет атрибут, доступный только для чтения, и перезаписывает существующий файл, доступный только для чтения.</span><span class="sxs-lookup"><span data-stu-id="ce083-171">Overrides the read-only attribute and overwrites an existing read-only file.</span></span> <span data-ttu-id="ce083-172">Параметр **Force** не переопределяет ограничения безопасности.</span><span class="sxs-lookup"><span data-stu-id="ce083-172">The **Force** parameter does not override security restrictions.</span></span>

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

### <span data-ttu-id="ce083-173">-InputObject</span><span class="sxs-lookup"><span data-stu-id="ce083-173">-InputObject</span></span>

<span data-ttu-id="ce083-174">Указывает объекты, которые нужно записать в файл.</span><span class="sxs-lookup"><span data-stu-id="ce083-174">Specifies the objects to be written to the file.</span></span> <span data-ttu-id="ce083-175">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="ce083-175">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="ce083-176">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="ce083-176">-LiteralPath</span></span>

<span data-ttu-id="ce083-177">Указывает путь к выходному файлу.</span><span class="sxs-lookup"><span data-stu-id="ce083-177">Specifies the path to the output file.</span></span> <span data-ttu-id="ce083-178">Параметр **LiteralPath** используется точно так же, как он типизирован.</span><span class="sxs-lookup"><span data-stu-id="ce083-178">The **LiteralPath** parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="ce083-179">Подстановочные знаки не допускаются.</span><span class="sxs-lookup"><span data-stu-id="ce083-179">Wildcard characters are not accepted.</span></span> <span data-ttu-id="ce083-180">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="ce083-180">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="ce083-181">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="ce083-181">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span> <span data-ttu-id="ce083-182">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="ce083-182">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ce083-183">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="ce083-183">-NoClobber</span></span>

<span data-ttu-id="ce083-184">**NoClobber** предотвращает перезапись существующего файла и выводит сообщение о том, что файл уже существует.</span><span class="sxs-lookup"><span data-stu-id="ce083-184">**NoClobber** prevents an existing file from being overwritten and displays a message that the file already exists.</span></span> <span data-ttu-id="ce083-185">По умолчанию, если файл существует по указанному пути, `Out-File` перезаписывает файл без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="ce083-185">By default, if a file exists in the specified path, `Out-File` overwrites the file without warning.</span></span>

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

### <span data-ttu-id="ce083-186">-Новая строка</span><span class="sxs-lookup"><span data-stu-id="ce083-186">-NoNewline</span></span>

<span data-ttu-id="ce083-187">Указывает, что содержимое, записанное в файл, не заканчивается символом новой строки.</span><span class="sxs-lookup"><span data-stu-id="ce083-187">Specifies that the content written to the file does not end with a newline character.</span></span> <span data-ttu-id="ce083-188">Строковые представления входных объектов сцепляются для формирования выходных данных.</span><span class="sxs-lookup"><span data-stu-id="ce083-188">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="ce083-189">Между выходными строками не вставляются пробелы и символы новой строки.</span><span class="sxs-lookup"><span data-stu-id="ce083-189">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="ce083-190">После последней выходной строки не добавляется новая строка.</span><span class="sxs-lookup"><span data-stu-id="ce083-190">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="ce083-191">-Width</span><span class="sxs-lookup"><span data-stu-id="ce083-191">-Width</span></span>

<span data-ttu-id="ce083-192">Указывает количество символов в каждой строке выходных данных.</span><span class="sxs-lookup"><span data-stu-id="ce083-192">Specifies the number of characters in each line of output.</span></span> <span data-ttu-id="ce083-193">Все остальные знаки отсекаются, а не переносятся на следующую строку.</span><span class="sxs-lookup"><span data-stu-id="ce083-193">Any additional characters are truncated, not wrapped.</span></span> <span data-ttu-id="ce083-194">Если этот параметр не используется, ширина определяется характеристиками узла.</span><span class="sxs-lookup"><span data-stu-id="ce083-194">If this parameter is not used, the width is determined by the characteristics of the host.</span></span> <span data-ttu-id="ce083-195">Значение по умолчанию для консоли PowerShell — 80 символов.</span><span class="sxs-lookup"><span data-stu-id="ce083-195">The default for the PowerShell console is 80 characters.</span></span>

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

### <span data-ttu-id="ce083-196">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ce083-196">-Confirm</span></span>

<span data-ttu-id="ce083-197">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="ce083-197">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="ce083-198">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ce083-198">-WhatIf</span></span>

<span data-ttu-id="ce083-199">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="ce083-199">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="ce083-200">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="ce083-200">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="ce083-201">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="ce083-201">CommonParameters</span></span>

<span data-ttu-id="ce083-202">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ce083-202">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ce083-203">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ce083-203">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ce083-204">Входные данные</span><span class="sxs-lookup"><span data-stu-id="ce083-204">INPUTS</span></span>

### <span data-ttu-id="ce083-205">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="ce083-205">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="ce083-206">Любой объект можно передать по конвейеру в `Out-File` .</span><span class="sxs-lookup"><span data-stu-id="ce083-206">You can pipe any object to `Out-File`.</span></span>

## <span data-ttu-id="ce083-207">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="ce083-207">OUTPUTS</span></span>

### <span data-ttu-id="ce083-208">Нет</span><span class="sxs-lookup"><span data-stu-id="ce083-208">None</span></span>

<span data-ttu-id="ce083-209">`Out-File` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="ce083-209">`Out-File` does not generate any output.</span></span>

## <span data-ttu-id="ce083-210">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="ce083-210">NOTES</span></span>

<span data-ttu-id="ce083-211">Входные объекты автоматически форматируются так же, как и в терминале, но можно использовать `Format-*` командлет для явного управления форматированием выходных данных в файле.</span><span class="sxs-lookup"><span data-stu-id="ce083-211">Input objects are automatically formatted as they would be in the terminal, but you can use a `Format-*` cmdlet to explicitly control the formatting of the output to the file.</span></span> <span data-ttu-id="ce083-212">Например `Get-Date | Format-List | Out-File out.txt`.</span><span class="sxs-lookup"><span data-stu-id="ce083-212">For example, `Get-Date | Format-List | Out-File out.txt`</span></span>

<span data-ttu-id="ce083-213">Чтобы отправить выходные данные команды PowerShell в `Out-File` командлет, используйте конвейер.</span><span class="sxs-lookup"><span data-stu-id="ce083-213">To send a PowerShell command's output to the `Out-File` cmdlet, use the pipeline.</span></span> <span data-ttu-id="ce083-214">Кроме того, можно хранить данные в переменной и использовать параметр **InputObject** для передачи данных в `Out-File` командлет.</span><span class="sxs-lookup"><span data-stu-id="ce083-214">Alternatively, you can store data in a variable and use the **InputObject** parameter to pass data to the `Out-File` cmdlet.</span></span>

<span data-ttu-id="ce083-215">`Out-File` сохраняет данные в файл, но не создает выходные объекты в конвейере.</span><span class="sxs-lookup"><span data-stu-id="ce083-215">`Out-File` saves data to a file but it does not produce any output objects to the pipeline.</span></span>

## <span data-ttu-id="ce083-216">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ce083-216">RELATED LINKS</span></span>

[<span data-ttu-id="ce083-217">about_Providers</span><span class="sxs-lookup"><span data-stu-id="ce083-217">about_Providers</span></span>](../Microsoft.Powershell.Core/About/about_Providers.md)

[<span data-ttu-id="ce083-218">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="ce083-218">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="ce083-219">Out-Default;</span><span class="sxs-lookup"><span data-stu-id="ce083-219">Out-Default</span></span>](../Microsoft.PowerShell.Core/Out-Default.md)

[<span data-ttu-id="ce083-220">Out-GridView</span><span class="sxs-lookup"><span data-stu-id="ce083-220">Out-GridView</span></span>](Out-GridView.md)

[<span data-ttu-id="ce083-221">Out-Host</span><span class="sxs-lookup"><span data-stu-id="ce083-221">Out-Host</span></span>](../Microsoft.PowerShell.Core/Out-Host.md)

[<span data-ttu-id="ce083-222">Out-Null</span><span class="sxs-lookup"><span data-stu-id="ce083-222">Out-Null</span></span>](../Microsoft.PowerShell.Core/Out-Null.md)

[<span data-ttu-id="ce083-223">Out-Printer</span><span class="sxs-lookup"><span data-stu-id="ce083-223">Out-Printer</span></span>](Out-Printer.md)

[<span data-ttu-id="ce083-224">Out-String</span><span class="sxs-lookup"><span data-stu-id="ce083-224">Out-String</span></span>](Out-String.md)

[<span data-ttu-id="ce083-225">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="ce083-225">Tee-Object</span></span>](Tee-Object.md)
