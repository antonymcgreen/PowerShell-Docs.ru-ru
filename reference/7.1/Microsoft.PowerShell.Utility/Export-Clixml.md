---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-clixml?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Clixml
ms.openlocfilehash: 8e1557bca62ade784bd5b4ed5cb170bbf079b423
ms.sourcegitcommit: 9a8bb1b459b5939c95e1f6d9499fcb13d01a58c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "93230502"
---
# <span data-ttu-id="831c1-103">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="831c1-103">Export-Clixml</span></span>

## <span data-ttu-id="831c1-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="831c1-104">SYNOPSIS</span></span>
<span data-ttu-id="831c1-105">Создает XML-представление объекта или объектов и сохраняет его в файл.</span><span class="sxs-lookup"><span data-stu-id="831c1-105">Creates an XML-based representation of an object or objects and stores it in a file.</span></span>

## <span data-ttu-id="831c1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="831c1-106">SYNTAX</span></span>

### <span data-ttu-id="831c1-107">ByPath (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="831c1-107">ByPath (Default)</span></span>

```
Export-Clixml [-Depth <Int32>] [-Path] <String> -InputObject <PSObject> [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="831c1-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="831c1-108">ByLiteralPath</span></span>

```
Export-Clixml [-Depth <Int32>] -LiteralPath <String> -InputObject <PSObject> [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="831c1-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="831c1-109">DESCRIPTION</span></span>

<span data-ttu-id="831c1-110">`Export-Clixml`Командлет создает Common Language Infrastructure представление объекта или объектов (CLI) на основе XML и сохраняет их в файле.</span><span class="sxs-lookup"><span data-stu-id="831c1-110">The `Export-Clixml` cmdlet creates a Common Language Infrastructure (CLI) XML-based representation of an object or objects and stores it in a file.</span></span> <span data-ttu-id="831c1-111">Затем можно использовать `Import-Clixml` командлет для повторного создания сохраненного объекта на основе содержимого этого файла.</span><span class="sxs-lookup"><span data-stu-id="831c1-111">You can then use the `Import-Clixml` cmdlet to recreate the saved object based on the contents of that file.</span></span>
<span data-ttu-id="831c1-112">Дополнительные сведения о интерфейсе командной строки см. в разделе [независимость от языка](/dotnet/standard/language-independence).</span><span class="sxs-lookup"><span data-stu-id="831c1-112">For more information about CLI, see [Language independence](/dotnet/standard/language-independence).</span></span>

<span data-ttu-id="831c1-113">Этот командлет аналогичен `ConvertTo-Xml` , за исключением того, что `Export-Clixml` сохраняет результирующий XML в файле.</span><span class="sxs-lookup"><span data-stu-id="831c1-113">This cmdlet is similar to `ConvertTo-Xml`, except that `Export-Clixml` stores the resulting XML in a file.</span></span> <span data-ttu-id="831c1-114">`ConvertTo-XML` Возвращает XML, поэтому вы можете продолжить его обработку в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="831c1-114">`ConvertTo-XML` returns the XML, so you can continue to process it in PowerShell.</span></span>

<span data-ttu-id="831c1-115">Важным применением `Export-Clixml` на компьютерах с Windows является экспорт учетных данных и защита строк безопасно в виде XML.</span><span class="sxs-lookup"><span data-stu-id="831c1-115">A valuable use of `Export-Clixml` on Windows computers is to export credentials and secure strings securely as XML.</span></span> <span data-ttu-id="831c1-116">Пример см. в примере 3.</span><span class="sxs-lookup"><span data-stu-id="831c1-116">For an example, see Example 3.</span></span>

## <span data-ttu-id="831c1-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="831c1-117">EXAMPLES</span></span>

### <span data-ttu-id="831c1-118">Пример 1. Экспорт строки в XML-файл</span><span class="sxs-lookup"><span data-stu-id="831c1-118">Example 1: Export a string to an XML file</span></span>

<span data-ttu-id="831c1-119">В этом примере создается XML-файл, хранящийся в текущем каталоге, представление строки, которая **является тестом** .</span><span class="sxs-lookup"><span data-stu-id="831c1-119">This example creates an XML file that stores in the current directory, a representation of the string **This is a test** .</span></span>

```powershell
"This is a test" | Export-Clixml -Path .\sample.xml
```

<span data-ttu-id="831c1-120">Строка `This is a test` отправляется по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="831c1-120">The string `This is a test` is sent down the pipeline.</span></span> <span data-ttu-id="831c1-121">`Export-Clixml` использует параметр **path** для создания XML-файла с именем `sample.xml` в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="831c1-121">`Export-Clixml` uses the **Path** parameter to create an XML file named `sample.xml` in the current directory.</span></span>

### <span data-ttu-id="831c1-122">Пример 2. экспорт объекта в XML-файл</span><span class="sxs-lookup"><span data-stu-id="831c1-122">Example 2: Export an object to an XML file</span></span>

<span data-ttu-id="831c1-123">В этом примере показано, как экспортировать объект в XML-файл и затем создать объект путем импорта из XML-файла.</span><span class="sxs-lookup"><span data-stu-id="831c1-123">This example shows how to export an object to an XML file and then create an object by importing the XML from the file.</span></span>

```powershell
Get-Acl C:\test.txt | Export-Clixml -Path .\FileACL.xml
$fileacl = Import-Clixml -Path .\FileACL.xml
```

<span data-ttu-id="831c1-124">`Get-Acl`Командлет возвращает дескриптор безопасности `Test.txt` файла.</span><span class="sxs-lookup"><span data-stu-id="831c1-124">The `Get-Acl` cmdlet gets the security descriptor of the `Test.txt` file.</span></span> <span data-ttu-id="831c1-125">Он отправляет объект по конвейеру, чтобы передать дескриптор безопасности в `Export-Clixml` .</span><span class="sxs-lookup"><span data-stu-id="831c1-125">It sends the object down the pipeline to pass the security descriptor to `Export-Clixml`.</span></span> <span data-ttu-id="831c1-126">Представление объекта, основанное на XML, хранится в файле с именем `FileACL.xml` .</span><span class="sxs-lookup"><span data-stu-id="831c1-126">The XML-based representation of the object is stored in a file named `FileACL.xml`.</span></span>

<span data-ttu-id="831c1-127">`Import-Clixml`Командлет создает объект из XML- `FileACL.xml` файла в файле.</span><span class="sxs-lookup"><span data-stu-id="831c1-127">The `Import-Clixml` cmdlet creates an object from the XML in the `FileACL.xml` file.</span></span> <span data-ttu-id="831c1-128">Затем объект сохраняется в `$fileacl` переменной.</span><span class="sxs-lookup"><span data-stu-id="831c1-128">Then, it saves the object in the `$fileacl` variable.</span></span>

### <span data-ttu-id="831c1-129">Пример 3. шифрование экспортированного объекта учетных данных в Windows</span><span class="sxs-lookup"><span data-stu-id="831c1-129">Example 3: Encrypt an exported credential object on Windows</span></span>

<span data-ttu-id="831c1-130">В этом примере с учетными данными, сохраненными в `$Credential` переменной путем запуска `Get-Credential` командлета, можно выполнить `Export-Clixml` командлет, чтобы сохранить учетные данные на диске.</span><span class="sxs-lookup"><span data-stu-id="831c1-130">In this example, given a credential that you've stored in the `$Credential` variable by running the `Get-Credential` cmdlet, you can run the `Export-Clixml` cmdlet to save the credential to disk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="831c1-131">`Export-Clixml` экспортирует только зашифрованные учетные данные в Windows.</span><span class="sxs-lookup"><span data-stu-id="831c1-131">`Export-Clixml` only exports encrypted credentials on Windows.</span></span> <span data-ttu-id="831c1-132">В операционных системах, отличных от Windows, таких как macOS и Linux, учетные данные экспортируются в виде обычного текста, хранящегося в виде массива символов Юникода.</span><span class="sxs-lookup"><span data-stu-id="831c1-132">On non-Windows operating systems such as macOS and Linux, credentials are exported as a plain text stored as a Unicode character array.</span></span> <span data-ttu-id="831c1-133">Это обеспечивает некоторую маскировку, но не обеспечивает шифрование.</span><span class="sxs-lookup"><span data-stu-id="831c1-133">This provides some obfuscation but does not provide encryption.</span></span>

```powershell
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential | Export-Clixml $Credxmlpath
$Credxmlpath = Join-Path (Split-Path $Profile) TestScript.ps1.credential
$Credential = Import-Clixml $Credxmlpath
```

<span data-ttu-id="831c1-134">`Export-Clixml`Командлет шифрует объекты учетных данных с помощью [API защиты данных](/previous-versions/windows/apps/hh464970(v=win.10))Windows.</span><span class="sxs-lookup"><span data-stu-id="831c1-134">The `Export-Clixml` cmdlet encrypts credential objects by using the Windows [Data Protection API](/previous-versions/windows/apps/hh464970(v=win.10)).</span></span> <span data-ttu-id="831c1-135">Шифрование гарантирует, что только учетная запись пользователя на этом компьютере сможет расшифровать содержимое объекта учетных данных.</span><span class="sxs-lookup"><span data-stu-id="831c1-135">The encryption ensures that only your user account on only that computer can decrypt the contents of the credential object.</span></span>
<span data-ttu-id="831c1-136">Экспортированный `CLIXML` файл нельзя использовать на другом компьютере или другом пользователе.</span><span class="sxs-lookup"><span data-stu-id="831c1-136">The exported `CLIXML` file can't be used on a different computer or by a different user.</span></span>

<span data-ttu-id="831c1-137">В этом примере файл, в котором хранятся учетные данные, представлен `TestScript.ps1.credential` .</span><span class="sxs-lookup"><span data-stu-id="831c1-137">In the example, the file in which the credential is stored is represented by `TestScript.ps1.credential`.</span></span> <span data-ttu-id="831c1-138">Замените **TestScript** именем скрипта, с которым загружаются учетные данные.</span><span class="sxs-lookup"><span data-stu-id="831c1-138">Replace **TestScript** with the name of the script with which you're loading the credential.</span></span>

<span data-ttu-id="831c1-139">Вы отправляете объект учетных данных по конвейеру в `Export-Clixml` и сохраняете его по пути, `$Credxmlpath` указанному в первой команде.</span><span class="sxs-lookup"><span data-stu-id="831c1-139">You send the credential object down the pipeline to `Export-Clixml`, and save it to the path, `$Credxmlpath`, that you specified in the first command.</span></span>

<span data-ttu-id="831c1-140">Чтобы автоматически импортировать учетные данные в скрипт, выполните последние две команды.</span><span class="sxs-lookup"><span data-stu-id="831c1-140">To import the credential automatically into your script, run the final two commands.</span></span> <span data-ttu-id="831c1-141">Выполните команду `Import-Clixml` , чтобы импортировать защищенный объект учетных данных в скрипт.</span><span class="sxs-lookup"><span data-stu-id="831c1-141">Run `Import-Clixml` to import the secured credential object into your script.</span></span> <span data-ttu-id="831c1-142">Этот импорт устраняет риск предоставления в скрипте обычных текстовых паролей.</span><span class="sxs-lookup"><span data-stu-id="831c1-142">This import eliminates the risk of exposing plain-text passwords in your script.</span></span>

### <span data-ttu-id="831c1-143">Пример 4. экспорт объекта учетных данных в Linux или macOS</span><span class="sxs-lookup"><span data-stu-id="831c1-143">Example 4: Exporting a credential object on Linux or macOS</span></span>

<span data-ttu-id="831c1-144">В этом примере мы создаем **PSCredential** в `$Credential` переменной с помощью `Get-Credential` командлета.</span><span class="sxs-lookup"><span data-stu-id="831c1-144">In this example, we create a **PSCredential** in the `$Credential` variable using the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="831c1-145">Затем мы используем `Export-Clixml` для сохранения учетных данных на диске.</span><span class="sxs-lookup"><span data-stu-id="831c1-145">Then we use `Export-Clixml` to save the credential to disk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="831c1-146">`Export-Clixml` экспортирует только зашифрованные учетные данные в Windows.</span><span class="sxs-lookup"><span data-stu-id="831c1-146">`Export-Clixml` only exports encrypted credentials on Windows.</span></span> <span data-ttu-id="831c1-147">В операционных системах, отличных от Windows, таких как macOS и Linux, учетные данные экспортируются в виде обычного текста, хранящегося в виде массива символов Юникода.</span><span class="sxs-lookup"><span data-stu-id="831c1-147">On non-Windows operating systems such as macOS and Linux, credentials are exported as a plain text stored as a Unicode character array.</span></span> <span data-ttu-id="831c1-148">Это обеспечивает некоторую маскировку, но не обеспечивает шифрование.</span><span class="sxs-lookup"><span data-stu-id="831c1-148">This provides some obfuscation but does not provide encryption.</span></span>

```powershell
PS> $Credential = Get-Credential

PowerShell credential request
Enter your credentials.
User: User1
Password for user User1: ********

PS> $Credential | Export-Clixml ./cred2.xml
PS> Get-Content ./cred2.xml

...
    <Props>
      <S N="UserName">User1</S>
      <SS N="Password">700061007300730077006f0072006400</SS>
    </Props>
...

PS> 'password' | Format-Hex -Encoding unicode

   Label: String (System.String) <52D60C91>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 70 00 61 00 73 00 73 00 77 00 6F 00 72 00 64 00 p a s s w o r d
```

<span data-ttu-id="831c1-149">Выходные данные `Get-Content` в этом примере были усечены, чтобы сосредоточиться на учетных данных в XML-файле.</span><span class="sxs-lookup"><span data-stu-id="831c1-149">The output of `Get-Content` in this example has been truncate to focus on the credential information in the XML file.</span></span> <span data-ttu-id="831c1-150">Обратите внимание, что обычное текстовое значение пароля хранится в XML-файле в виде массива символов Юникода, проверенного `Format-Hex` .</span><span class="sxs-lookup"><span data-stu-id="831c1-150">Note that the plain text value of the password is stored in the XML file as a Unicode character array as proven by `Format-Hex`.</span></span> <span data-ttu-id="831c1-151">Поэтому значение кодируется, но не шифруется.</span><span class="sxs-lookup"><span data-stu-id="831c1-151">So the value is encoded but not encrypted.</span></span>

## <span data-ttu-id="831c1-152">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="831c1-152">PARAMETERS</span></span>

### <span data-ttu-id="831c1-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="831c1-153">-Confirm</span></span>

<span data-ttu-id="831c1-154">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="831c1-154">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="831c1-155">-Depth</span><span class="sxs-lookup"><span data-stu-id="831c1-155">-Depth</span></span>

<span data-ttu-id="831c1-156">Указывает, сколько уровней вложенных объектов включается в XML-представление.</span><span class="sxs-lookup"><span data-stu-id="831c1-156">Specifies how many levels of contained objects are included in the XML representation.</span></span> <span data-ttu-id="831c1-157">Значение по умолчанию — `2`.</span><span class="sxs-lookup"><span data-stu-id="831c1-157">The default value is `2`.</span></span>

<span data-ttu-id="831c1-158">Значение по умолчанию может быть переопределено для типа объекта в `Types.ps1xml` файлах.</span><span class="sxs-lookup"><span data-stu-id="831c1-158">The default value can be overridden for the object type in the `Types.ps1xml` files.</span></span> <span data-ttu-id="831c1-159">Дополнительные сведения см. в разделе [about_Types.ps1XML](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="831c1-159">For more information, see [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 2
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="831c1-160">-Encoding</span><span class="sxs-lookup"><span data-stu-id="831c1-160">-Encoding</span></span>

<span data-ttu-id="831c1-161">Указывает тип кодировки для целевого файла.</span><span class="sxs-lookup"><span data-stu-id="831c1-161">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="831c1-162">Значение по умолчанию — `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="831c1-162">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="831c1-163">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="831c1-163">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="831c1-164">`ascii`: Использует кодировку для набора символов ASCII (7-разрядных).</span><span class="sxs-lookup"><span data-stu-id="831c1-164">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="831c1-165">`bigendianunicode`: Кодируется в формате UTF-16 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="831c1-165">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="831c1-166">`bigendianutf32`: Кодируется в формате UTF-32 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="831c1-166">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="831c1-167">`oem`: Использует кодировку по умолчанию для программ MS-DOS и консолей.</span><span class="sxs-lookup"><span data-stu-id="831c1-167">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="831c1-168">`unicode`: Кодируется в формате UTF-16 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="831c1-168">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="831c1-169">`utf7`: Кодируется в формате UTF-7.</span><span class="sxs-lookup"><span data-stu-id="831c1-169">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="831c1-170">`utf8`: Кодируется в формате UTF-8.</span><span class="sxs-lookup"><span data-stu-id="831c1-170">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="831c1-171">`utf8BOM`: Кодирует в формате UTF-8 с меткой порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="831c1-171">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="831c1-172">`utf8NoBOM`: Кодирует в формате UTF-8 без метки порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="831c1-172">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="831c1-173">`utf32`: Кодируется в формате UTF-32.</span><span class="sxs-lookup"><span data-stu-id="831c1-173">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="831c1-174">Начиная с PowerShell 6,2, параметр **кодировки** также разрешает числовые идентификаторы зарегистрированных кодовых страниц (например `-Encoding 1251` ,) или строковых имен зарегистрированных кодовых страниц (например `-Encoding "windows-1251"` ,).</span><span class="sxs-lookup"><span data-stu-id="831c1-174">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="831c1-175">Дополнительные сведения см. в документации .NET по [кодированию. codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="831c1-175">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

> [!NOTE]
> <span data-ttu-id="831c1-176">Больше не рекомендуется использовать **UTF-7** \*.</span><span class="sxs-lookup"><span data-stu-id="831c1-176">**UTF-7** \* is no longer recommended to use.</span></span> <span data-ttu-id="831c1-177">В PowerShell 7,1 при указании параметра Encoding записывается предупреждение `utf7` . **Encoding**</span><span class="sxs-lookup"><span data-stu-id="831c1-177">In PowerShell 7.1, a warning is written if you specify `utf7` for the **Encoding** parameter.</span></span>

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

### <span data-ttu-id="831c1-178">-Force</span><span class="sxs-lookup"><span data-stu-id="831c1-178">-Force</span></span>

<span data-ttu-id="831c1-179">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="831c1-179">Forces the command to run without asking for user confirmation.</span></span>

<span data-ttu-id="831c1-180">В результате командлет снимает атрибут только для чтения выходного файла при необходимости.</span><span class="sxs-lookup"><span data-stu-id="831c1-180">Causes the cmdlet to clear the read-only attribute of the output file if necessary.</span></span> <span data-ttu-id="831c1-181">Командлет попытается сбросить атрибут "только для чтения" после выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="831c1-181">The cmdlet will attempt to reset the read-only attribute when the command completes.</span></span>

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

### <span data-ttu-id="831c1-182">-InputObject</span><span class="sxs-lookup"><span data-stu-id="831c1-182">-InputObject</span></span>

<span data-ttu-id="831c1-183">Задает объект для преобразования.</span><span class="sxs-lookup"><span data-stu-id="831c1-183">Specifies the object to be converted.</span></span> <span data-ttu-id="831c1-184">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="831c1-184">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="831c1-185">Также можно передать объекты в `Export-Clixml` .</span><span class="sxs-lookup"><span data-stu-id="831c1-185">You can also pipe objects to `Export-Clixml`.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="831c1-186">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="831c1-186">-LiteralPath</span></span>

<span data-ttu-id="831c1-187">Указывает путь к файлу, где будет храниться XML-представление объекта.</span><span class="sxs-lookup"><span data-stu-id="831c1-187">Specifies the path to the file where the XML representation of the object will be stored.</span></span> <span data-ttu-id="831c1-188">В отличие от **path** , значение параметра **LiteralPath** используется точно так же, как типизировано.</span><span class="sxs-lookup"><span data-stu-id="831c1-188">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="831c1-189">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="831c1-189">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="831c1-190">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="831c1-190">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="831c1-191">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="831c1-191">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="831c1-192">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="831c1-192">-NoClobber</span></span>

<span data-ttu-id="831c1-193">Указывает, что командлет не перезаписывает содержимое существующего файла.</span><span class="sxs-lookup"><span data-stu-id="831c1-193">Indicates that the cmdlet doesn't overwrite the contents of an existing file.</span></span> <span data-ttu-id="831c1-194">По умолчанию, если файл существует по указанному пути, `Export-Clixml` перезаписывает файл без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="831c1-194">By default, if a file exists in the specified path, `Export-Clixml` overwrites the file without warning.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="831c1-195">-Path</span><span class="sxs-lookup"><span data-stu-id="831c1-195">-Path</span></span>

<span data-ttu-id="831c1-196">Указывает путь к файлу, где будет храниться XML-представление объекта.</span><span class="sxs-lookup"><span data-stu-id="831c1-196">Specifies the path to the file where the XML representation of the object will be stored.</span></span>

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

### <span data-ttu-id="831c1-197">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="831c1-197">-WhatIf</span></span>

<span data-ttu-id="831c1-198">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="831c1-198">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="831c1-199">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="831c1-199">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="831c1-200">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="831c1-200">CommonParameters</span></span>

<span data-ttu-id="831c1-201">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="831c1-201">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="831c1-202">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="831c1-202">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="831c1-203">Входные данные</span><span class="sxs-lookup"><span data-stu-id="831c1-203">INPUTS</span></span>

### <span data-ttu-id="831c1-204">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="831c1-204">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="831c1-205">Можно выполнить конвейер любого объекта в `Export-Clixml` .</span><span class="sxs-lookup"><span data-stu-id="831c1-205">You can pipeline any object to `Export-Clixml`.</span></span>

## <span data-ttu-id="831c1-206">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="831c1-206">OUTPUTS</span></span>

### <span data-ttu-id="831c1-207">System. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="831c1-207">System.IO.FileInfo</span></span>

<span data-ttu-id="831c1-208">`Export-Clixml` создает файл, содержащий XML.</span><span class="sxs-lookup"><span data-stu-id="831c1-208">`Export-Clixml` creates a file that contains the XML.</span></span>

## <span data-ttu-id="831c1-209">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="831c1-209">NOTES</span></span>

## <span data-ttu-id="831c1-210">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="831c1-210">RELATED LINKS</span></span>

[<span data-ttu-id="831c1-211">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="831c1-211">ConvertTo-Html</span></span>](ConvertTo-Html.md)

[<span data-ttu-id="831c1-212">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="831c1-212">ConvertTo-Xml</span></span>](ConvertTo-Xml.md)

[<span data-ttu-id="831c1-213">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="831c1-213">Export-Csv</span></span>](Export-Csv.md)

[<span data-ttu-id="831c1-214">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="831c1-214">Import-Clixml</span></span>](Import-Clixml.md)

[<span data-ttu-id="831c1-215">Join-Path</span><span class="sxs-lookup"><span data-stu-id="831c1-215">Join-Path</span></span>](../Microsoft.PowerShell.Management/Join-Path.md)

<span data-ttu-id="831c1-216">[Securely Store Credentials on Disk](https://powershellcookbook.com/recipe/PukO/securely-store-credentials-on-disk) (Безопасное хранение учетных данных на диске)</span><span class="sxs-lookup"><span data-stu-id="831c1-216">[Securely Store Credentials on Disk](https://powershellcookbook.com/recipe/PukO/securely-store-credentials-on-disk)</span></span>

<span data-ttu-id="831c1-217">[Use PowerShell to Pass Credentials to Legacy Systems](https://devblogs.microsoft.com/scripting/use-powershell-to-pass-credentials-to-legacy-systems/) (Передача учетных данных в устаревшие системы с помощью PowerShell)</span><span class="sxs-lookup"><span data-stu-id="831c1-217">[Use PowerShell to Pass Credentials to Legacy Systems](https://devblogs.microsoft.com/scripting/use-powershell-to-pass-credentials-to-legacy-systems/)</span></span>

[<span data-ttu-id="831c1-218">Windows.Security.Cryptography.DataProtection</span><span class="sxs-lookup"><span data-stu-id="831c1-218">Windows.Security.Cryptography.DataProtection</span></span>](/uwp/api/windows.security.cryptography.dataprotection)
