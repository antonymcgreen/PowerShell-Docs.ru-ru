---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-file?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-File
ms.openlocfilehash: e3a066957ab1e6935049003f8ccf55aee8bb7c94
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600885"
---
# <span data-ttu-id="39b3c-102">Out-File</span><span class="sxs-lookup"><span data-stu-id="39b3c-102">Out-File</span></span>

## <span data-ttu-id="39b3c-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="39b3c-103">SYNOPSIS</span></span>
<span data-ttu-id="39b3c-104">Отправляет выходные данные в файл.</span><span class="sxs-lookup"><span data-stu-id="39b3c-104">Sends output to a file.</span></span>

## <span data-ttu-id="39b3c-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="39b3c-105">SYNTAX</span></span>

### <span data-ttu-id="39b3c-106">ByPath (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="39b3c-106">ByPath (Default)</span></span>

```
Out-File [-FilePath] <string> [[-Encoding] <Encoding>] [-Append] [-Force] [-NoClobber]
 [-Width <int>] [-NoNewline] [-InputObject <psobject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="39b3c-107">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="39b3c-107">ByLiteralPath</span></span>

```
Out-File [[-Encoding] <Encoding>] -LiteralPath <string> [-Append] [-Force] [-NoClobber]
 [-Width <int>] [-NoNewline] [-InputObject <psobject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="39b3c-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="39b3c-108">DESCRIPTION</span></span>

<span data-ttu-id="39b3c-109">`Out-File`Командлет отправляет выходные данные в файл.</span><span class="sxs-lookup"><span data-stu-id="39b3c-109">The `Out-File` cmdlet sends output to a file.</span></span> <span data-ttu-id="39b3c-110">Он неявно использует систему форматирования PowerShell для записи в файл.</span><span class="sxs-lookup"><span data-stu-id="39b3c-110">It implicitly uses PowerShell's formatting system to write to the file.</span></span> <span data-ttu-id="39b3c-111">Файл получает то же отображаемое представление, что и терминал.</span><span class="sxs-lookup"><span data-stu-id="39b3c-111">The file receives the same display representation as the terminal.</span></span> <span data-ttu-id="39b3c-112">Это означает, что выходные данные могут быть неидеальными для программной обработки, если только все входные объекты не являются строками.</span><span class="sxs-lookup"><span data-stu-id="39b3c-112">This means that the output may not be ideal for programmatic processing unless all input objects are strings.</span></span>
<span data-ttu-id="39b3c-113">Если необходимо указать параметры для выходных данных, используйте `Out-File` вместо оператора перенаправления ( `>` ).</span><span class="sxs-lookup"><span data-stu-id="39b3c-113">When you need to specify parameters for the output, use `Out-File` rather than the redirection operator (`>`).</span></span> <span data-ttu-id="39b3c-114">Дополнительные сведения о перенаправлении см. в разделе [about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md).</span><span class="sxs-lookup"><span data-stu-id="39b3c-114">For more information about redirection, see [about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md).</span></span>

## <span data-ttu-id="39b3c-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="39b3c-115">EXAMPLES</span></span>

### <span data-ttu-id="39b3c-116">Пример 1. Отправка выходных данных и создание файла</span><span class="sxs-lookup"><span data-stu-id="39b3c-116">Example 1: Send output and create a file</span></span>

<span data-ttu-id="39b3c-117">В этом примере показано, как отправить список процессов локального компьютера в файл.</span><span class="sxs-lookup"><span data-stu-id="39b3c-117">This example shows how to send a list of the local computer's processes to a file.</span></span> <span data-ttu-id="39b3c-118">Если файл не существует, `Out-File` создает файл по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="39b3c-118">If the file does not exist, `Out-File` creates the file in the specified path.</span></span>

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

<span data-ttu-id="39b3c-119">`Get-Process`Командлет возвращает список процессов, запущенных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="39b3c-119">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="39b3c-120">Объекты **процесса** отправляются по конвейеру в `Out-File` командлет.</span><span class="sxs-lookup"><span data-stu-id="39b3c-120">The **Process** objects are sent down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="39b3c-121">`Out-File` использует параметр **FilePath** и создает файл в текущем каталоге с именем **Process.txt**.</span><span class="sxs-lookup"><span data-stu-id="39b3c-121">`Out-File` uses the **FilePath** parameter and creates a file in the current directory named **Process.txt**.</span></span> <span data-ttu-id="39b3c-122">`Get-Content`Команда получает содержимое из файла и отображает его в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="39b3c-122">The `Get-Content` command gets content from the file and displays it in the PowerShell console.</span></span>

### <span data-ttu-id="39b3c-123">Пример 2. запрет перезаписи существующего файла</span><span class="sxs-lookup"><span data-stu-id="39b3c-123">Example 2: Prevent an existing file from being overwritten</span></span>

<span data-ttu-id="39b3c-124">Этот пример предотвращает перезапись существующего файла.</span><span class="sxs-lookup"><span data-stu-id="39b3c-124">This example prevents an existing file from being overwritten.</span></span> <span data-ttu-id="39b3c-125">По умолчанию `Out-File` перезаписывает существующие файлы.</span><span class="sxs-lookup"><span data-stu-id="39b3c-125">By default, `Out-File` overwrites existing files.</span></span>

```powershell
Get-Process | Out-File -FilePath .\Process.txt -NoClobber
```

```Output
Out-File : The file 'C:\Test\Process.txt' already exists.
At line:1 char:15
+ Get-Process | Out-File -FilePath .\Process.txt -NoClobber
+               ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
```

<span data-ttu-id="39b3c-126">`Get-Process`Командлет возвращает список процессов, запущенных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="39b3c-126">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="39b3c-127">Объекты **процесса** отправляются по конвейеру в `Out-File` командлет.</span><span class="sxs-lookup"><span data-stu-id="39b3c-127">The **Process** objects are sent down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="39b3c-128">`Out-File` использует параметр **FilePath** и пытается выполнить запись в файл в текущем каталоге с именем **Process.txt**.</span><span class="sxs-lookup"><span data-stu-id="39b3c-128">`Out-File` uses the **FilePath** parameter and attempts to write to a file in the current directory named **Process.txt**.</span></span> <span data-ttu-id="39b3c-129">Параметр **NoClobber** предотвращает перезапись файла и выводит сообщение о том, что файл уже существует.</span><span class="sxs-lookup"><span data-stu-id="39b3c-129">The **NoClobber** parameter prevents the file from being overwritten and displays a message that the file already exists.</span></span>

### <span data-ttu-id="39b3c-130">Пример 3. Отправка выходных данных в файл в формате ASCII</span><span class="sxs-lookup"><span data-stu-id="39b3c-130">Example 3: Send output to a file in ASCII format</span></span>

<span data-ttu-id="39b3c-131">В этом примере показано, как кодировать выходные данные с конкретным типом кодирования.</span><span class="sxs-lookup"><span data-stu-id="39b3c-131">This example shows how to encode output with a specific encoding type.</span></span>

```powershell
$Procs = Get-Process
Out-File -FilePath .\Process.txt -InputObject $Procs -Encoding ASCII -Width 50
```

<span data-ttu-id="39b3c-132">`Get-Process`Командлет возвращает список процессов, запущенных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="39b3c-132">The `Get-Process` cmdlet gets the list of processes running on the local computer.</span></span> <span data-ttu-id="39b3c-133">Объекты **процесса** хранятся в переменной `$Procs` .</span><span class="sxs-lookup"><span data-stu-id="39b3c-133">The **Process** objects are stored in the variable, `$Procs`.</span></span> <span data-ttu-id="39b3c-134">`Out-File` использует параметр **FilePath** и создает файл в текущем каталоге с именем **Process.txt**.</span><span class="sxs-lookup"><span data-stu-id="39b3c-134">`Out-File` uses the **FilePath** parameter and creates a file in the current directory named **Process.txt**.</span></span> <span data-ttu-id="39b3c-135">Параметр **InputObject** передает объекты процесса в `$Procs` файл **Process.txt**.</span><span class="sxs-lookup"><span data-stu-id="39b3c-135">The **InputObject** parameter passes the process objects in `$Procs` to the file **Process.txt**.</span></span> <span data-ttu-id="39b3c-136">Параметр **Encoding** преобразует выходные данные в формат **ASCII** .</span><span class="sxs-lookup"><span data-stu-id="39b3c-136">The **Encoding** parameter converts the output to **ASCII** format.</span></span> <span data-ttu-id="39b3c-137">Параметр **Width** ограничивает каждую строку в файле на 50 символов, чтобы некоторые данные могли быть обрезаны.</span><span class="sxs-lookup"><span data-stu-id="39b3c-137">The **Width** parameter limits each line in the file to 50 characters so some data might be truncated.</span></span>

### <span data-ttu-id="39b3c-138">Пример 4. Использование поставщика и отправка выходных данных в файл</span><span class="sxs-lookup"><span data-stu-id="39b3c-138">Example 4: Use a provider and send output to a file</span></span>

<span data-ttu-id="39b3c-139">В этом примере показано, как использовать `Out-File` командлет, если вы не используете диск поставщика **FileSystem** .</span><span class="sxs-lookup"><span data-stu-id="39b3c-139">This example shows how to use the `Out-File` cmdlet when you are not in a **FileSystem** provider drive.</span></span> <span data-ttu-id="39b3c-140">Используйте `Get-PSProvider` командлет для просмотра поставщиков на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="39b3c-140">Use the `Get-PSProvider` cmdlet to view the providers on your local computer.</span></span> <span data-ttu-id="39b3c-141">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.Powershell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="39b3c-141">For more information, see [about_Providers](../Microsoft.Powershell.Core/About/about_Providers.md).</span></span>

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

<span data-ttu-id="39b3c-142">`Set-Location`Команда использует параметр **path** , чтобы задать текущее расположение для поставщика реестра `Alias:` .</span><span class="sxs-lookup"><span data-stu-id="39b3c-142">The `Set-Location` command uses the **Path** parameter to set the current location to the registry provider `Alias:`.</span></span> <span data-ttu-id="39b3c-143">`Get-Location`Командлет выводит полный путь для `Alias:` .</span><span class="sxs-lookup"><span data-stu-id="39b3c-143">The `Get-Location` cmdlet displays the complete path for `Alias:`.</span></span>
<span data-ttu-id="39b3c-144">`Get-ChildItem` отправляет объекты по конвейеру в `Out-File` командлет.</span><span class="sxs-lookup"><span data-stu-id="39b3c-144">`Get-ChildItem` sends objects down the pipeline to the `Out-File` cmdlet.</span></span> <span data-ttu-id="39b3c-145">`Out-File` использует параметр **FilePath** для указания полного пути и имени файла выходных данных, **C:\TestDir\AliasNames.txt**.</span><span class="sxs-lookup"><span data-stu-id="39b3c-145">`Out-File` uses the **FilePath** parameter to specify the complete path and filename for the output, **C:\TestDir\AliasNames.txt**.</span></span> <span data-ttu-id="39b3c-146">`Get-Content`Командлет использует параметр **path** и отображает содержимое файла в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="39b3c-146">The `Get-Content` cmdlet uses the **Path** parameter and displays the file's content in the PowerShell console.</span></span>

## <span data-ttu-id="39b3c-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="39b3c-147">PARAMETERS</span></span>

### <span data-ttu-id="39b3c-148">— Добавление</span><span class="sxs-lookup"><span data-stu-id="39b3c-148">-Append</span></span>

<span data-ttu-id="39b3c-149">Добавляет выходные данные в конец существующего файла.</span><span class="sxs-lookup"><span data-stu-id="39b3c-149">Adds the output to the end of an existing file.</span></span>

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

### <span data-ttu-id="39b3c-150">-Encoding</span><span class="sxs-lookup"><span data-stu-id="39b3c-150">-Encoding</span></span>

<span data-ttu-id="39b3c-151">Указывает тип кодировки для целевого файла.</span><span class="sxs-lookup"><span data-stu-id="39b3c-151">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="39b3c-152">Значение по умолчанию — `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="39b3c-152">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="39b3c-153">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="39b3c-153">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="39b3c-154">`ascii`: Использует кодировку для набора символов ASCII (7-разрядных).</span><span class="sxs-lookup"><span data-stu-id="39b3c-154">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="39b3c-155">`bigendianunicode`: Кодируется в формате UTF-16 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="39b3c-155">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="39b3c-156">`bigendianutf32`: Кодируется в формате UTF-32 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="39b3c-156">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="39b3c-157">`oem`: Использует кодировку по умолчанию для программ MS-DOS и консолей.</span><span class="sxs-lookup"><span data-stu-id="39b3c-157">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="39b3c-158">`unicode`: Кодируется в формате UTF-16 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="39b3c-158">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="39b3c-159">`utf7`: Кодируется в формате UTF-7.</span><span class="sxs-lookup"><span data-stu-id="39b3c-159">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="39b3c-160">`utf8`: Кодируется в формате UTF-8.</span><span class="sxs-lookup"><span data-stu-id="39b3c-160">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="39b3c-161">`utf8BOM`: Кодирует в формате UTF-8 с меткой порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="39b3c-161">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="39b3c-162">`utf8NoBOM`: Кодирует в формате UTF-8 без метки порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="39b3c-162">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="39b3c-163">`utf32`: Кодируется в формате UTF-32.</span><span class="sxs-lookup"><span data-stu-id="39b3c-163">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="39b3c-164">Начиная с PowerShell 6,2, параметр **кодировки** также разрешает числовые идентификаторы зарегистрированных кодовых страниц (например `-Encoding 1251` ,) или строковых имен зарегистрированных кодовых страниц (например `-Encoding "windows-1251"` ,).</span><span class="sxs-lookup"><span data-stu-id="39b3c-164">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="39b3c-165">Дополнительные сведения см. в документации .NET по [кодированию. codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="39b3c-165">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

> [!NOTE]
> <span data-ttu-id="39b3c-166">Больше не рекомендуется использовать **UTF-7** _.</span><span class="sxs-lookup"><span data-stu-id="39b3c-166">**UTF-7** _ is no longer recommended to use.</span></span> <span data-ttu-id="39b3c-167">В PowerShell 7,1 записывается предупреждение, если указано `utf7` для параметра _ \*Encoding\*\*.</span><span class="sxs-lookup"><span data-stu-id="39b3c-167">In PowerShell 7.1, a warning is written if you specify `utf7` for the _ *Encoding*\* parameter.</span></span>

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

### <span data-ttu-id="39b3c-168">-FilePath</span><span class="sxs-lookup"><span data-stu-id="39b3c-168">-FilePath</span></span>

<span data-ttu-id="39b3c-169">Указывает путь к выходному файлу.</span><span class="sxs-lookup"><span data-stu-id="39b3c-169">Specifies the path to the output file.</span></span>

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

### <span data-ttu-id="39b3c-170">-Force</span><span class="sxs-lookup"><span data-stu-id="39b3c-170">-Force</span></span>

<span data-ttu-id="39b3c-171">Переопределяет атрибут, доступный только для чтения, и перезаписывает существующий файл, доступный только для чтения.</span><span class="sxs-lookup"><span data-stu-id="39b3c-171">Overrides the read-only attribute and overwrites an existing read-only file.</span></span> <span data-ttu-id="39b3c-172">Параметр **Force** не переопределяет ограничения безопасности.</span><span class="sxs-lookup"><span data-stu-id="39b3c-172">The **Force** parameter does not override security restrictions.</span></span>

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

### <span data-ttu-id="39b3c-173">-InputObject</span><span class="sxs-lookup"><span data-stu-id="39b3c-173">-InputObject</span></span>

<span data-ttu-id="39b3c-174">Указывает объекты, которые нужно записать в файл.</span><span class="sxs-lookup"><span data-stu-id="39b3c-174">Specifies the objects to be written to the file.</span></span> <span data-ttu-id="39b3c-175">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="39b3c-175">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="39b3c-176">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="39b3c-176">-LiteralPath</span></span>

<span data-ttu-id="39b3c-177">Указывает путь к выходному файлу.</span><span class="sxs-lookup"><span data-stu-id="39b3c-177">Specifies the path to the output file.</span></span> <span data-ttu-id="39b3c-178">Параметр **LiteralPath** используется точно так же, как он типизирован.</span><span class="sxs-lookup"><span data-stu-id="39b3c-178">The **LiteralPath** parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="39b3c-179">Подстановочные знаки не допускаются.</span><span class="sxs-lookup"><span data-stu-id="39b3c-179">Wildcard characters are not accepted.</span></span> <span data-ttu-id="39b3c-180">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="39b3c-180">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="39b3c-181">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="39b3c-181">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span> <span data-ttu-id="39b3c-182">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="39b3c-182">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="39b3c-183">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="39b3c-183">-NoClobber</span></span>

<span data-ttu-id="39b3c-184">**NoClobber** предотвращает перезапись существующего файла и выводит сообщение о том, что файл уже существует.</span><span class="sxs-lookup"><span data-stu-id="39b3c-184">**NoClobber** prevents an existing file from being overwritten and displays a message that the file already exists.</span></span> <span data-ttu-id="39b3c-185">По умолчанию, если файл существует по указанному пути, `Out-File` перезаписывает файл без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="39b3c-185">By default, if a file exists in the specified path, `Out-File` overwrites the file without warning.</span></span>

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

### <span data-ttu-id="39b3c-186">-Новая строка</span><span class="sxs-lookup"><span data-stu-id="39b3c-186">-NoNewline</span></span>

<span data-ttu-id="39b3c-187">Указывает, что содержимое, записанное в файл, не заканчивается символом новой строки.</span><span class="sxs-lookup"><span data-stu-id="39b3c-187">Specifies that the content written to the file does not end with a newline character.</span></span> <span data-ttu-id="39b3c-188">Строковые представления входных объектов сцепляются для формирования выходных данных.</span><span class="sxs-lookup"><span data-stu-id="39b3c-188">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="39b3c-189">Между выходными строками не вставляются пробелы и символы новой строки.</span><span class="sxs-lookup"><span data-stu-id="39b3c-189">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="39b3c-190">После последней выходной строки не добавляется новая строка.</span><span class="sxs-lookup"><span data-stu-id="39b3c-190">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="39b3c-191">-Width</span><span class="sxs-lookup"><span data-stu-id="39b3c-191">-Width</span></span>

<span data-ttu-id="39b3c-192">Указывает количество символов в каждой строке выходных данных.</span><span class="sxs-lookup"><span data-stu-id="39b3c-192">Specifies the number of characters in each line of output.</span></span> <span data-ttu-id="39b3c-193">Все остальные знаки отсекаются, а не переносятся на следующую строку.</span><span class="sxs-lookup"><span data-stu-id="39b3c-193">Any additional characters are truncated, not wrapped.</span></span> <span data-ttu-id="39b3c-194">Если этот параметр не используется, ширина определяется характеристиками узла.</span><span class="sxs-lookup"><span data-stu-id="39b3c-194">If this parameter is not used, the width is determined by the characteristics of the host.</span></span> <span data-ttu-id="39b3c-195">Значение по умолчанию для консоли PowerShell — 80 символов.</span><span class="sxs-lookup"><span data-stu-id="39b3c-195">The default for the PowerShell console is 80 characters.</span></span>

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

### <span data-ttu-id="39b3c-196">-Confirm</span><span class="sxs-lookup"><span data-stu-id="39b3c-196">-Confirm</span></span>

<span data-ttu-id="39b3c-197">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="39b3c-197">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="39b3c-198">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="39b3c-198">-WhatIf</span></span>

<span data-ttu-id="39b3c-199">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="39b3c-199">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="39b3c-200">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="39b3c-200">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="39b3c-201">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="39b3c-201">CommonParameters</span></span>

<span data-ttu-id="39b3c-202">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="39b3c-202">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="39b3c-203">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="39b3c-203">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="39b3c-204">Входные данные</span><span class="sxs-lookup"><span data-stu-id="39b3c-204">INPUTS</span></span>

### <span data-ttu-id="39b3c-205">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="39b3c-205">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="39b3c-206">Любой объект можно передать по конвейеру в `Out-File` .</span><span class="sxs-lookup"><span data-stu-id="39b3c-206">You can pipe any object to `Out-File`.</span></span>

## <span data-ttu-id="39b3c-207">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="39b3c-207">OUTPUTS</span></span>

### <span data-ttu-id="39b3c-208">None</span><span class="sxs-lookup"><span data-stu-id="39b3c-208">None</span></span>

<span data-ttu-id="39b3c-209">`Out-File` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="39b3c-209">`Out-File` does not generate any output.</span></span>

## <span data-ttu-id="39b3c-210">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="39b3c-210">NOTES</span></span>

<span data-ttu-id="39b3c-211">Входные объекты автоматически форматируются так же, как и в терминале, но можно использовать `Format-*` командлет для явного управления форматированием выходных данных в файле.</span><span class="sxs-lookup"><span data-stu-id="39b3c-211">Input objects are automatically formatted as they would be in the terminal, but you can use a `Format-*` cmdlet to explicitly control the formatting of the output to the file.</span></span> <span data-ttu-id="39b3c-212">Например: `Get-Date | Format-List | Out-File out.txt`</span><span class="sxs-lookup"><span data-stu-id="39b3c-212">For example, `Get-Date | Format-List | Out-File out.txt`</span></span>

<span data-ttu-id="39b3c-213">Чтобы отправить выходные данные команды PowerShell в `Out-File` командлет, используйте конвейер.</span><span class="sxs-lookup"><span data-stu-id="39b3c-213">To send a PowerShell command's output to the `Out-File` cmdlet, use the pipeline.</span></span> <span data-ttu-id="39b3c-214">Кроме того, можно хранить данные в переменной и использовать параметр **InputObject** для передачи данных в `Out-File` командлет.</span><span class="sxs-lookup"><span data-stu-id="39b3c-214">Alternatively, you can store data in a variable and use the **InputObject** parameter to pass data to the `Out-File` cmdlet.</span></span>

<span data-ttu-id="39b3c-215">`Out-File` сохраняет данные в файл, но не создает выходные объекты в конвейере.</span><span class="sxs-lookup"><span data-stu-id="39b3c-215">`Out-File` saves data to a file but it does not produce any output objects to the pipeline.</span></span>

## <span data-ttu-id="39b3c-216">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="39b3c-216">RELATED LINKS</span></span>

[<span data-ttu-id="39b3c-217">about_Providers</span><span class="sxs-lookup"><span data-stu-id="39b3c-217">about_Providers</span></span>](../Microsoft.Powershell.Core/About/about_Providers.md)

[<span data-ttu-id="39b3c-218">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="39b3c-218">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="39b3c-219">Out-Default;</span><span class="sxs-lookup"><span data-stu-id="39b3c-219">Out-Default</span></span>](../Microsoft.PowerShell.Core/Out-Default.md)

[<span data-ttu-id="39b3c-220">Out-Host</span><span class="sxs-lookup"><span data-stu-id="39b3c-220">Out-Host</span></span>](../Microsoft.PowerShell.Core/Out-Host.md)

[<span data-ttu-id="39b3c-221">Out-Null</span><span class="sxs-lookup"><span data-stu-id="39b3c-221">Out-Null</span></span>](../Microsoft.PowerShell.Core/Out-Null.md)

[<span data-ttu-id="39b3c-222">Out-String</span><span class="sxs-lookup"><span data-stu-id="39b3c-222">Out-String</span></span>](Out-String.md)

[<span data-ttu-id="39b3c-223">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="39b3c-223">Tee-Object</span></span>](Tee-Object.md)

