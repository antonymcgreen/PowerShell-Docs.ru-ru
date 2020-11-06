---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/17/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-hex?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Hex
ms.openlocfilehash: 6cb02f1c6f2583ce4146356fac3553e99a54c7c2
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226181"
---
# <span data-ttu-id="ccc56-103">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="ccc56-103">Format-Hex</span></span>

## <span data-ttu-id="ccc56-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ccc56-104">SYNOPSIS</span></span>

<span data-ttu-id="ccc56-105">Отображает файл или другие входные данные в шестнадцатеричном формате.</span><span class="sxs-lookup"><span data-stu-id="ccc56-105">Displays a file or other input as hexadecimal.</span></span>

## <span data-ttu-id="ccc56-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ccc56-106">SYNTAX</span></span>

### <span data-ttu-id="ccc56-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="ccc56-107">Path (Default)</span></span>

```
Format-Hex [-Path] <String[]> [-Count <Int64>] [-Offset <Int64>] [<CommonParameters>]
```

### <span data-ttu-id="ccc56-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="ccc56-108">LiteralPath</span></span>

```
Format-Hex -LiteralPath <String[]> [-Count <Int64>] [-Offset <Int64>] [<CommonParameters>]
```

### <span data-ttu-id="ccc56-109">бинпутобжект</span><span class="sxs-lookup"><span data-stu-id="ccc56-109">ByInputObject</span></span>
```
Format-Hex -InputObject <PSObject> [-Encoding <Encoding>] [-Count <Int64>] [-Offset <Int64>] [-Raw]
 [<CommonParameters>]
```

## <span data-ttu-id="ccc56-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ccc56-110">DESCRIPTION</span></span>

<span data-ttu-id="ccc56-111">`Format-Hex`Командлет отображает файл или другие входные данные в виде шестнадцатеричных значений.</span><span class="sxs-lookup"><span data-stu-id="ccc56-111">The `Format-Hex` cmdlet displays a file or other input as hexadecimal values.</span></span> <span data-ttu-id="ccc56-112">Чтобы определить смещение символа от выходных данных, добавьте номер, расположенный слева от строки, к номеру в верхней части столбца для этого символа.</span><span class="sxs-lookup"><span data-stu-id="ccc56-112">To determine the offset of a character from the output, add the number at the leftmost of the row to the number at the top of the column for that character.</span></span>

<span data-ttu-id="ccc56-113">`Format-Hex`Командлет помогает определить тип файла поврежденного файла или файл, который может не иметь расширения имени файла.</span><span class="sxs-lookup"><span data-stu-id="ccc56-113">The `Format-Hex` cmdlet can help you determine the file type of a corrupted file or a file that might not have a filename extension.</span></span> <span data-ttu-id="ccc56-114">Можно выполнить этот командлет, а затем прочитать шестнадцатеричные выходные данные, чтобы получить сведения о файле.</span><span class="sxs-lookup"><span data-stu-id="ccc56-114">You can run this cmdlet, and then read the hexadecimal output to get file information.</span></span>

<span data-ttu-id="ccc56-115">При использовании `Format-Hex` для файла командлет игнорирует символы новой строки и возвращает все содержимое файла в одной строке с сохраненными символами новой строки.</span><span class="sxs-lookup"><span data-stu-id="ccc56-115">When using `Format-Hex` on a file, the cmdlet ignores newline characters and returns the entire contents of a file in one string with the newline characters preserved.</span></span>

## <span data-ttu-id="ccc56-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="ccc56-116">EXAMPLES</span></span>

### <span data-ttu-id="ccc56-117">Пример 1. получение шестнадцатеричного представления строки</span><span class="sxs-lookup"><span data-stu-id="ccc56-117">Example 1: Get the hexadecimal representation of a string</span></span>

<span data-ttu-id="ccc56-118">Эта команда возвращает шестнадцатеричные значения строки.</span><span class="sxs-lookup"><span data-stu-id="ccc56-118">This command returns the hexadecimal values of a string.</span></span>

```powershell
'Hello World' | Format-Hex
```

```Output
   Label: String (System.String) <2944BEC3>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 48 65 6C 6C 6F 20 57 6F 72 6C 64                Hello World
```

<span data-ttu-id="ccc56-119">Строка **Hello World** отправляется в командлет по конвейеру `Format-Hex` .</span><span class="sxs-lookup"><span data-stu-id="ccc56-119">The string **Hello World** is sent down the pipeline to the `Format-Hex` cmdlet.</span></span> <span data-ttu-id="ccc56-120">Шестнадцатеричные выходные данные `Format-Hex` показывают значения каждого символа в строке.</span><span class="sxs-lookup"><span data-stu-id="ccc56-120">The hexadecimal output from `Format-Hex` shows the values of each character in the string.</span></span>

### <span data-ttu-id="ccc56-121">Пример 2. Поиск типа файла из шестнадцатеричного вывода</span><span class="sxs-lookup"><span data-stu-id="ccc56-121">Example 2: Find a file type from hexadecimal output</span></span>

<span data-ttu-id="ccc56-122">В этом примере используется шестнадцатеричный вывод для определения типа файла.</span><span class="sxs-lookup"><span data-stu-id="ccc56-122">This example uses the hexadecimal output to determine the file type.</span></span> <span data-ttu-id="ccc56-123">Командлет отображает полный путь к файлу и шестнадцатеричные значения.</span><span class="sxs-lookup"><span data-stu-id="ccc56-123">The cmdlet displays the file's full path and the hexadecimal values.</span></span>

<span data-ttu-id="ccc56-124">Чтобы проверить следующую команду, создайте копию существующего PDF-файла на локальном компьютере и переименуйте скопированный файл в `File.t7f` .</span><span class="sxs-lookup"><span data-stu-id="ccc56-124">To test the following command, make a copy of an existing PDF file on your local computer and rename the copied file to `File.t7f`.</span></span>

```powershell
Format-Hex -Path .\File.t7f -Count 48
```

```Output
   Label: C:\Test\File.t7f

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 25 50 44 46 2D 31 2E 35 0D 0A 25 B5 B5 B5 B5 0D %PDF-1.5..%????.
0000000000000010 0A 31 20 30 20 6F 62 6A 0D 0A 3C 3C 2F 54 79 70 .1 0 obj..<</Typ
0000000000000020 65 2F 43 61 74 61 6C 6F 67 2F 50 61 67 65 73 20 e/Catalog/Pages
```

<span data-ttu-id="ccc56-125">`Format-Hex`Командлет использует параметр **path** для указания имени файла в текущем каталоге, `File.t7f` .</span><span class="sxs-lookup"><span data-stu-id="ccc56-125">The `Format-Hex` cmdlet uses the **Path** parameter to specify a filename in the current directory, `File.t7f`.</span></span> <span data-ttu-id="ccc56-126">Расширение файла `.t7f` является редким, но шестнадцатеричные выходные данные `%PDF` показывают, что это файл PDF.</span><span class="sxs-lookup"><span data-stu-id="ccc56-126">The file extension `.t7f` is uncommon, but the hexadecimal output `%PDF` shows that it is a PDF file.</span></span> <span data-ttu-id="ccc56-127">В этом примере параметр **Count** используется для ограничения выходных данных до первых 48 байт файла.</span><span class="sxs-lookup"><span data-stu-id="ccc56-127">In this example, the **Count** parameter is used to limit the output to the first 48 bytes of the file.</span></span>

### <span data-ttu-id="ccc56-128">Пример 3. форматирование массива различных типов данных</span><span class="sxs-lookup"><span data-stu-id="ccc56-128">Example 3: Format an array of different data types</span></span>

<span data-ttu-id="ccc56-129">В этом примере используется массив различных типов данных для выделения `Format-Hex` их обработки в конвейере.</span><span class="sxs-lookup"><span data-stu-id="ccc56-129">This example uses an array of different data types to highlight how `Format-Hex` handles them in the Pipeline.</span></span>

<span data-ttu-id="ccc56-130">Он будет передавать каждый объект через конвейер и обрабатывать его по отдельности.</span><span class="sxs-lookup"><span data-stu-id="ccc56-130">It will pass each object through the Pipeline and process individually.</span></span> <span data-ttu-id="ccc56-131">Однако если это числовые данные, а смежный объект также является числовым, он будет сгруппирован в один выходной блок.</span><span class="sxs-lookup"><span data-stu-id="ccc56-131">However, if it's numeric data, and the adjacent object is also numeric, it will group them into a single output block.</span></span>

```powershell
'Hello world!', 1, 1138, 'foo', 'bar', 0xdeadbeef, 1gb, 0b1101011100 , $true, $false | Format-Hex
```

```Output
   Label: String (System.String) <24F1F0A3>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 48 65 6C 6C 6F 20 77 6F 72 6C 64 21             Hello world!

   Label: Int32 (System.Int32) <2EB933C5>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 01 00 00 00 72 04 00 00                         �   r�

   Label: String (System.String) <4078B66C>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 66 6F 6F                                        foo

   Label: String (System.String) <51E4A317>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 62 61 72                                        bar

   Label: Int32 (System.Int32) <5ADF167B>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 EF BE AD DE 00 00 00 40 5C 03 00 00             ï¾­Þ   @\�

   Label: Boolean (System.Boolean) <7D8C4C1D>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 01 00 00 00 00 00 00 00                         �
```

## <span data-ttu-id="ccc56-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ccc56-132">PARAMETERS</span></span>

### <span data-ttu-id="ccc56-133">-Encoding</span><span class="sxs-lookup"><span data-stu-id="ccc56-133">-Encoding</span></span>

<span data-ttu-id="ccc56-134">Задает кодировку входных строк.</span><span class="sxs-lookup"><span data-stu-id="ccc56-134">Specifies the encoding of the input strings.</span></span> <span data-ttu-id="ccc56-135">Это относится только к `[string]` входным данным.</span><span class="sxs-lookup"><span data-stu-id="ccc56-135">This only applies to `[string]` input.</span></span> <span data-ttu-id="ccc56-136">Параметр не влияет на числовые типы.</span><span class="sxs-lookup"><span data-stu-id="ccc56-136">The parameter has no effect on numeric types.</span></span> <span data-ttu-id="ccc56-137">Выходное значение всегда равно `utf8NoBOM` .</span><span class="sxs-lookup"><span data-stu-id="ccc56-137">The output value is always `utf8NoBOM`.</span></span>

<span data-ttu-id="ccc56-138">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="ccc56-138">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="ccc56-139">`ascii`: Использует кодировку для набора символов ASCII (7-разрядных).</span><span class="sxs-lookup"><span data-stu-id="ccc56-139">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="ccc56-140">`bigendianunicode`: Кодируется в формате UTF-16 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="ccc56-140">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="ccc56-141">`oem`: Использует кодировку по умолчанию для программ MS-DOS и консолей.</span><span class="sxs-lookup"><span data-stu-id="ccc56-141">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="ccc56-142">`unicode`: Кодируется в формате UTF-16 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="ccc56-142">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="ccc56-143">`utf7`: Кодируется в формате UTF-7.</span><span class="sxs-lookup"><span data-stu-id="ccc56-143">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="ccc56-144">`utf8`: Кодируется в формате UTF-8.</span><span class="sxs-lookup"><span data-stu-id="ccc56-144">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="ccc56-145">`utf8BOM`: Кодирует в формате UTF-8 с меткой порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="ccc56-145">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="ccc56-146">`utf8NoBOM`: Кодирует в формате UTF-8 без метки порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="ccc56-146">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="ccc56-147">`utf32`: Кодируется в формате UTF-32.</span><span class="sxs-lookup"><span data-stu-id="ccc56-147">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="ccc56-148">Начиная с PowerShell 6,2, параметр **кодировки** также разрешает числовые идентификаторы зарегистрированных кодовых страниц (например `-Encoding 1251` ,) или строковых имен зарегистрированных кодовых страниц (например `-Encoding "windows-1251"` ,).</span><span class="sxs-lookup"><span data-stu-id="ccc56-148">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="ccc56-149">Дополнительные сведения см. в документации .NET по [кодированию. codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="ccc56-149">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: ByInputObject
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ccc56-150">-InputObject</span><span class="sxs-lookup"><span data-stu-id="ccc56-150">-InputObject</span></span>

<span data-ttu-id="ccc56-151">Используется для входных данных конвейера.</span><span class="sxs-lookup"><span data-stu-id="ccc56-151">Used for pipeline input.</span></span> <span data-ttu-id="ccc56-152">Входные данные конвейера поддерживают только определенные скалярные типы и `[system.io.fileinfo]` экземпляры для передачи по конвейеру `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="ccc56-152">Pipeline input supports only certain scalar types and `[system.io.fileinfo]` instances for piping from `Get-ChildItem`.</span></span>

<span data-ttu-id="ccc56-153">Поддерживаемые скалярные типы:</span><span class="sxs-lookup"><span data-stu-id="ccc56-153">The supported scalar types are:</span></span>

- <span data-ttu-id="ccc56-154">`[string]`, `[char]`</span><span class="sxs-lookup"><span data-stu-id="ccc56-154">`[string]`, `[char]`</span></span>
- <span data-ttu-id="ccc56-155">`[byte]`, `[sbyte]`</span><span class="sxs-lookup"><span data-stu-id="ccc56-155">`[byte]`, `[sbyte]`</span></span>
- <span data-ttu-id="ccc56-156">`[int16]`, `[uint16]`, `[short]`, `[ushort]`</span><span class="sxs-lookup"><span data-stu-id="ccc56-156">`[int16]`, `[uint16]`, `[short]`, `[ushort]`</span></span>
- <span data-ttu-id="ccc56-157">`[int]`, `[uint]`, `[int32]`, `[uint32]`,</span><span class="sxs-lookup"><span data-stu-id="ccc56-157">`[int]`, `[uint]`, `[int32]`, `[uint32]`,</span></span>
- <span data-ttu-id="ccc56-158">`[long]`, `[ulong]`, `[int64]`, `[uint64]`</span><span class="sxs-lookup"><span data-stu-id="ccc56-158">`[long]`, `[ulong]`, `[int64]`, `[uint64]`</span></span>
- <span data-ttu-id="ccc56-159">`[single]`, `[float]`, `[double]`</span><span class="sxs-lookup"><span data-stu-id="ccc56-159">`[single]`, `[float]`, `[double]`</span></span>
- `[boolean]`

<span data-ttu-id="ccc56-160">До выхода версии PowerShell 6,2 `Format-Hex` обрабатывает входные данные конвейера с несколькими типами входных данных, объединяя все объекты, аналогичные.</span><span class="sxs-lookup"><span data-stu-id="ccc56-160">Prior to PowerShell 6.2, `Format-Hex` would handle a Pipeline input with multiple input types by grouping all like objects together.</span></span> <span data-ttu-id="ccc56-161">Теперь он обрабатывает каждый отдельный объект по мере его прохождения через конвейер и не будет группировать объекты вместе, если они не являются смежными объектами.</span><span class="sxs-lookup"><span data-stu-id="ccc56-161">Now, it handles each individual object as it passes through the Pipeline and won't group objects together unless like objects are adjacent.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ccc56-162">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="ccc56-162">-LiteralPath</span></span>

<span data-ttu-id="ccc56-163">Указывает полный путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="ccc56-163">Specifies the complete path to a file.</span></span> <span data-ttu-id="ccc56-164">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="ccc56-164">The value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="ccc56-165">Этот параметр не принимает подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="ccc56-165">This parameter does not accept wildcard characters.</span></span> <span data-ttu-id="ccc56-166">Чтобы указать несколько путей к файлам, разделяйте пути запятой.</span><span class="sxs-lookup"><span data-stu-id="ccc56-166">To specify multiple paths to files, separate the paths with a comma.</span></span> <span data-ttu-id="ccc56-167">Если параметр **LiteralPath** включает escape-символы, заключите путь в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="ccc56-167">If the **LiteralPath** parameter includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="ccc56-168">PowerShell не интерпретирует символы в одной строке в кавычках как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="ccc56-168">PowerShell does not interpret any characters in a single quoted string as escape sequences.</span></span> <span data-ttu-id="ccc56-169">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="ccc56-169">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ccc56-170">-Path</span><span class="sxs-lookup"><span data-stu-id="ccc56-170">-Path</span></span>

<span data-ttu-id="ccc56-171">Указывает путь к файлам.</span><span class="sxs-lookup"><span data-stu-id="ccc56-171">Specifies the path to files.</span></span> <span data-ttu-id="ccc56-172">Используйте точку ( `.` ), чтобы указать текущее расположение.</span><span class="sxs-lookup"><span data-stu-id="ccc56-172">Use a dot (`.`) to specify the current location.</span></span> <span data-ttu-id="ccc56-173">Символ-шаблон ( `*` ) принимается и может использоваться для указания всех элементов в расположении.</span><span class="sxs-lookup"><span data-stu-id="ccc56-173">The wildcard character (`*`) is accepted and can be used to specify all the items in a location.</span></span> <span data-ttu-id="ccc56-174">Если параметр **path** включает escape-символы, заключите путь в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="ccc56-174">If the **Path** parameter includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="ccc56-175">Чтобы указать несколько путей к файлам, разделяйте пути запятой.</span><span class="sxs-lookup"><span data-stu-id="ccc56-175">To specify multiple paths to files, separate the paths with a comma.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="ccc56-176">-RAW</span><span class="sxs-lookup"><span data-stu-id="ccc56-176">-Raw</span></span>

<span data-ttu-id="ccc56-177">Этот параметр больше не выполняет никаких действий.</span><span class="sxs-lookup"><span data-stu-id="ccc56-177">This parameter no longer does anything.</span></span> <span data-ttu-id="ccc56-178">Он сохраняется для совместимости скриптов.</span><span class="sxs-lookup"><span data-stu-id="ccc56-178">It is retained for script compatibility.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ccc56-179">-Offset</span><span class="sxs-lookup"><span data-stu-id="ccc56-179">-Offset</span></span>

<span data-ttu-id="ccc56-180">Представляет число байтов, которые нужно пропустить, после которого они являются частью шестнадцатеричного вывода.</span><span class="sxs-lookup"><span data-stu-id="ccc56-180">This represents the number of bytes to skip from being part of the hex output.</span></span>

<span data-ttu-id="ccc56-181">Этот параметр появился в PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="ccc56-181">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ccc56-182">— Количество</span><span class="sxs-lookup"><span data-stu-id="ccc56-182">-Count</span></span>

<span data-ttu-id="ccc56-183">Представляет число байтов, включаемых в Шестнадцатеричный вывод.</span><span class="sxs-lookup"><span data-stu-id="ccc56-183">This represents the number of bytes to include in the hex output.</span></span>

<span data-ttu-id="ccc56-184">Этот параметр появился в PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="ccc56-184">This parameter was introduced in PowerShell 6.2.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Int64.MaxValue
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ccc56-185">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="ccc56-185">CommonParameters</span></span>

<span data-ttu-id="ccc56-186">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ccc56-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ccc56-187">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ccc56-187">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ccc56-188">Входные данные</span><span class="sxs-lookup"><span data-stu-id="ccc56-188">INPUTS</span></span>

### <span data-ttu-id="ccc56-189">System.String</span><span class="sxs-lookup"><span data-stu-id="ccc56-189">System.String</span></span>

<span data-ttu-id="ccc56-190">Вы можете передать строку в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="ccc56-190">You can pipe a string to this cmdlet.</span></span>

## <span data-ttu-id="ccc56-191">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="ccc56-191">OUTPUTS</span></span>

### <span data-ttu-id="ccc56-192">Microsoft. PowerShell. Commands. Битеколлектион</span><span class="sxs-lookup"><span data-stu-id="ccc56-192">Microsoft.PowerShell.Commands.ByteCollection</span></span>

<span data-ttu-id="ccc56-193">Этот командлет возвращает **битеколлектион**.</span><span class="sxs-lookup"><span data-stu-id="ccc56-193">This cmdlet returns a **ByteCollection**.</span></span> <span data-ttu-id="ccc56-194">Этот объект представляет коллекцию байтов.</span><span class="sxs-lookup"><span data-stu-id="ccc56-194">This object represents a collection of bytes.</span></span> <span data-ttu-id="ccc56-195">Он содержит методы, которые преобразуют коллекцию байтов в строку, отформатированную в виде каждой строки выходных данных, возвращаемых `Format-Hex` .</span><span class="sxs-lookup"><span data-stu-id="ccc56-195">It includes methods that convert the collection of bytes to a string formatted like each line of output returned by `Format-Hex`.</span></span> <span data-ttu-id="ccc56-196">В выходных данных также указывается тип обрабатываемых байтов.</span><span class="sxs-lookup"><span data-stu-id="ccc56-196">The output also states they type of bytes being processed.</span></span> <span data-ttu-id="ccc56-197">При указании параметра **path** или **LiteralPath** объект содержит путь к файлу, содержащему каждый байт.</span><span class="sxs-lookup"><span data-stu-id="ccc56-197">If you specify the **Path** or **LiteralPath** parameter, the object contains the path of the file that contains each byte.</span></span> <span data-ttu-id="ccc56-198">Если передать строку, логическое значение, целое число и т. д., она будет помечена соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="ccc56-198">If you pass a string, boolean, integer, etc, it will be labeled appropriately.</span></span>

## <span data-ttu-id="ccc56-199">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="ccc56-199">NOTES</span></span>

<span data-ttu-id="ccc56-200">Правый столбец выходных данных пытается отобразить байты как символы ASCII:</span><span class="sxs-lookup"><span data-stu-id="ccc56-200">The right-most column of output tries to render the bytes as ASCII characters:</span></span>

<span data-ttu-id="ccc56-201">Как правило, каждый байт интерпретируется как кодовая точка Юникода, что означает:</span><span class="sxs-lookup"><span data-stu-id="ccc56-201">Generally, each byte is interpreted as a Unicode code point, which means that:</span></span>

- <span data-ttu-id="ccc56-202">Печатаемые символы ASCII всегда отображаются правильно</span><span class="sxs-lookup"><span data-stu-id="ccc56-202">Printable ASCII characters are always rendered correctly</span></span>
- <span data-ttu-id="ccc56-203">Символы UTF-8 с несколькими байтами никогда не отображаются правильно</span><span class="sxs-lookup"><span data-stu-id="ccc56-203">Multi-byte UTF-8 characters never render correctly</span></span>
- <span data-ttu-id="ccc56-204">Символы UTF-16 отображаются правильно, только если происходит их старший байт `NUL` .</span><span class="sxs-lookup"><span data-stu-id="ccc56-204">UTF-16 characters render correctly only if their high-order byte happens be `NUL`.</span></span>

## <span data-ttu-id="ccc56-205">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ccc56-205">RELATED LINKS</span></span>

[<span data-ttu-id="ccc56-206">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="ccc56-206">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="ccc56-207">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="ccc56-207">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="ccc56-208">Format-List</span><span class="sxs-lookup"><span data-stu-id="ccc56-208">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="ccc56-209">Format-Table</span><span class="sxs-lookup"><span data-stu-id="ccc56-209">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="ccc56-210">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="ccc56-210">Format-Wide</span></span>](Format-Wide.md)