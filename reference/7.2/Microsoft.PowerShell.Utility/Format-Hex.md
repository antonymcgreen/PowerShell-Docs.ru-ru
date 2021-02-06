---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-hex?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Hex
ms.openlocfilehash: a45e7919b5a24189ca7f50661795ff035c38a037
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602700"
---
# <span data-ttu-id="68e93-102">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="68e93-102">Format-Hex</span></span>

## <span data-ttu-id="68e93-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="68e93-103">SYNOPSIS</span></span>

<span data-ttu-id="68e93-104">Отображает файл или другие входные данные в шестнадцатеричном формате.</span><span class="sxs-lookup"><span data-stu-id="68e93-104">Displays a file or other input as hexadecimal.</span></span>

## <span data-ttu-id="68e93-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="68e93-105">SYNTAX</span></span>

### <span data-ttu-id="68e93-106">Путь</span><span class="sxs-lookup"><span data-stu-id="68e93-106">Path</span></span>

```
Format-Hex [-Path] <String[]> [-Count <Int64>] [-Offset <Int64>] [<CommonParameters>]
```

### <span data-ttu-id="68e93-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="68e93-107">LiteralPath</span></span>

```
Format-Hex -LiteralPath <String[]> [-Count <Int64>] [-Offset <Int64>] [<CommonParameters>]
```

### <span data-ttu-id="68e93-108">бинпутобжект</span><span class="sxs-lookup"><span data-stu-id="68e93-108">ByInputObject</span></span>

```
Format-Hex -InputObject <PSObject> [-Encoding <Encoding>] [-Count <Int64>] [-Offset <Int64>] [-Raw]
 [<CommonParameters>]
```

## <span data-ttu-id="68e93-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="68e93-109">DESCRIPTION</span></span>

<span data-ttu-id="68e93-110">`Format-Hex`Командлет отображает файл или другие входные данные в виде шестнадцатеричных значений.</span><span class="sxs-lookup"><span data-stu-id="68e93-110">The `Format-Hex` cmdlet displays a file or other input as hexadecimal values.</span></span> <span data-ttu-id="68e93-111">Чтобы определить смещение символа от выходных данных, добавьте номер, расположенный слева от строки, к номеру в верхней части столбца для этого символа.</span><span class="sxs-lookup"><span data-stu-id="68e93-111">To determine the offset of a character from the output, add the number at the leftmost of the row to the number at the top of the column for that character.</span></span>

<span data-ttu-id="68e93-112">`Format-Hex`Командлет помогает определить тип файла поврежденного файла или файл, который может не иметь расширения имени файла.</span><span class="sxs-lookup"><span data-stu-id="68e93-112">The `Format-Hex` cmdlet can help you determine the file type of a corrupted file or a file that might not have a filename extension.</span></span> <span data-ttu-id="68e93-113">Можно выполнить этот командлет, а затем прочитать шестнадцатеричные выходные данные, чтобы получить сведения о файле.</span><span class="sxs-lookup"><span data-stu-id="68e93-113">You can run this cmdlet, and then read the hexadecimal output to get file information.</span></span>

<span data-ttu-id="68e93-114">При использовании `Format-Hex` для файла командлет игнорирует символы новой строки и возвращает все содержимое файла в одной строке с сохраненными символами новой строки.</span><span class="sxs-lookup"><span data-stu-id="68e93-114">When using `Format-Hex` on a file, the cmdlet ignores newline characters and returns the entire contents of a file in one string with the newline characters preserved.</span></span>

## <span data-ttu-id="68e93-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="68e93-115">EXAMPLES</span></span>

### <span data-ttu-id="68e93-116">Пример 1. получение шестнадцатеричного представления строки</span><span class="sxs-lookup"><span data-stu-id="68e93-116">Example 1: Get the hexadecimal representation of a string</span></span>

<span data-ttu-id="68e93-117">Эта команда возвращает шестнадцатеричные значения строки.</span><span class="sxs-lookup"><span data-stu-id="68e93-117">This command returns the hexadecimal values of a string.</span></span>

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

<span data-ttu-id="68e93-118">Строка **Hello World** отправляется в командлет по конвейеру `Format-Hex` .</span><span class="sxs-lookup"><span data-stu-id="68e93-118">The string **Hello World** is sent down the pipeline to the `Format-Hex` cmdlet.</span></span> <span data-ttu-id="68e93-119">Шестнадцатеричные выходные данные `Format-Hex` показывают значения каждого символа в строке.</span><span class="sxs-lookup"><span data-stu-id="68e93-119">The hexadecimal output from `Format-Hex` shows the values of each character in the string.</span></span>

### <span data-ttu-id="68e93-120">Пример 2. Поиск типа файла из шестнадцатеричного вывода</span><span class="sxs-lookup"><span data-stu-id="68e93-120">Example 2: Find a file type from hexadecimal output</span></span>

<span data-ttu-id="68e93-121">В этом примере используется шестнадцатеричный вывод для определения типа файла.</span><span class="sxs-lookup"><span data-stu-id="68e93-121">This example uses the hexadecimal output to determine the file type.</span></span> <span data-ttu-id="68e93-122">Командлет отображает полный путь к файлу и шестнадцатеричные значения.</span><span class="sxs-lookup"><span data-stu-id="68e93-122">The cmdlet displays the file's full path and the hexadecimal values.</span></span>

<span data-ttu-id="68e93-123">Чтобы проверить следующую команду, создайте копию существующего PDF-файла на локальном компьютере и переименуйте скопированный файл в `File.t7f` .</span><span class="sxs-lookup"><span data-stu-id="68e93-123">To test the following command, make a copy of an existing PDF file on your local computer and rename the copied file to `File.t7f`.</span></span>

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

<span data-ttu-id="68e93-124">`Format-Hex`Командлет использует параметр **path** для указания имени файла в текущем каталоге, `File.t7f` .</span><span class="sxs-lookup"><span data-stu-id="68e93-124">The `Format-Hex` cmdlet uses the **Path** parameter to specify a filename in the current directory, `File.t7f`.</span></span> <span data-ttu-id="68e93-125">Расширение файла `.t7f` является редким, но шестнадцатеричные выходные данные `%PDF` показывают, что это файл PDF.</span><span class="sxs-lookup"><span data-stu-id="68e93-125">The file extension `.t7f` is uncommon, but the hexadecimal output `%PDF` shows that it is a PDF file.</span></span> <span data-ttu-id="68e93-126">В этом примере параметр **Count** используется для ограничения выходных данных до первых 48 байт файла.</span><span class="sxs-lookup"><span data-stu-id="68e93-126">In this example, the **Count** parameter is used to limit the output to the first 48 bytes of the file.</span></span>

### <span data-ttu-id="68e93-127">Пример 3. форматирование массива различных типов данных</span><span class="sxs-lookup"><span data-stu-id="68e93-127">Example 3: Format an array of different data types</span></span>

<span data-ttu-id="68e93-128">В этом примере используется массив различных типов данных для выделения `Format-Hex` их обработки в конвейере.</span><span class="sxs-lookup"><span data-stu-id="68e93-128">This example uses an array of different data types to highlight how `Format-Hex` handles them in the Pipeline.</span></span>

<span data-ttu-id="68e93-129">Он будет передавать каждый объект через конвейер и обрабатывать его по отдельности.</span><span class="sxs-lookup"><span data-stu-id="68e93-129">It will pass each object through the Pipeline and process individually.</span></span> <span data-ttu-id="68e93-130">Однако если это числовые данные, а смежный объект также является числовым, он будет сгруппирован в один выходной блок.</span><span class="sxs-lookup"><span data-stu-id="68e93-130">However, if it's numeric data, and the adjacent object is also numeric, it will group them into a single output block.</span></span>

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
0000000000000000 EF BE AD DE 00 00 00 40 5C 03 00 00             ï¾-Þ   @\�

   Label: Boolean (System.Boolean) <7D8C4C1D>

          Offset Bytes                                           Ascii
                 00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F
          ------ ----------------------------------------------- -----
0000000000000000 01 00 00 00 00 00 00 00                         �
```

## <span data-ttu-id="68e93-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="68e93-131">PARAMETERS</span></span>

### <span data-ttu-id="68e93-132">-Encoding</span><span class="sxs-lookup"><span data-stu-id="68e93-132">-Encoding</span></span>

<span data-ttu-id="68e93-133">Задает кодировку входных строк.</span><span class="sxs-lookup"><span data-stu-id="68e93-133">Specifies the encoding of the input strings.</span></span> <span data-ttu-id="68e93-134">Это относится только к `[string]` входным данным.</span><span class="sxs-lookup"><span data-stu-id="68e93-134">This only applies to `[string]` input.</span></span> <span data-ttu-id="68e93-135">Параметр не влияет на числовые типы.</span><span class="sxs-lookup"><span data-stu-id="68e93-135">The parameter has no effect on numeric types.</span></span> <span data-ttu-id="68e93-136">Выходное значение всегда равно `utf8NoBOM` .</span><span class="sxs-lookup"><span data-stu-id="68e93-136">The output value is always `utf8NoBOM`.</span></span>

<span data-ttu-id="68e93-137">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="68e93-137">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="68e93-138">`ascii`: Использует кодировку для набора символов ASCII (7-разрядных).</span><span class="sxs-lookup"><span data-stu-id="68e93-138">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="68e93-139">`bigendianunicode`: Кодируется в формате UTF-16 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="68e93-139">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="68e93-140">`bigendianutf32`: Кодируется в формате UTF-32 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="68e93-140">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="68e93-141">`oem`: Использует кодировку по умолчанию для программ MS-DOS и консолей.</span><span class="sxs-lookup"><span data-stu-id="68e93-141">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="68e93-142">`unicode`: Кодируется в формате UTF-16 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="68e93-142">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="68e93-143">`utf7`: Кодируется в формате UTF-7.</span><span class="sxs-lookup"><span data-stu-id="68e93-143">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="68e93-144">`utf8`: Кодируется в формате UTF-8.</span><span class="sxs-lookup"><span data-stu-id="68e93-144">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="68e93-145">`utf8BOM`: Кодирует в формате UTF-8 с меткой порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="68e93-145">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="68e93-146">`utf8NoBOM`: Кодирует в формате UTF-8 без метки порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="68e93-146">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="68e93-147">`utf32`: Кодируется в формате UTF-32.</span><span class="sxs-lookup"><span data-stu-id="68e93-147">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="68e93-148">Начиная с PowerShell 6,2, параметр **кодировки** также разрешает числовые идентификаторы зарегистрированных кодовых страниц (например `-Encoding 1251` ,) или строковых имен зарегистрированных кодовых страниц (например `-Encoding "windows-1251"` ,).</span><span class="sxs-lookup"><span data-stu-id="68e93-148">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="68e93-149">Дополнительные сведения см. в документации .NET по [кодированию. codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="68e93-149">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

> [!NOTE]
> <span data-ttu-id="68e93-150">Больше не рекомендуется использовать **UTF-7** _.</span><span class="sxs-lookup"><span data-stu-id="68e93-150">**UTF-7** _ is no longer recommended to use.</span></span> <span data-ttu-id="68e93-151">В PowerShell 7,1 записывается предупреждение, если указано `utf7` для параметра _ \*Encoding\*\*.</span><span class="sxs-lookup"><span data-stu-id="68e93-151">In PowerShell 7.1, a warning is written if you specify `utf7` for the _ *Encoding*\* parameter.</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: ByInputObject
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="68e93-152">-InputObject</span><span class="sxs-lookup"><span data-stu-id="68e93-152">-InputObject</span></span>

<span data-ttu-id="68e93-153">Используется для входных данных конвейера.</span><span class="sxs-lookup"><span data-stu-id="68e93-153">Used for pipeline input.</span></span> <span data-ttu-id="68e93-154">Входные данные конвейера поддерживают только определенные скалярные типы и `[system.io.fileinfo]` экземпляры для передачи по конвейеру `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="68e93-154">Pipeline input supports only certain scalar types and `[system.io.fileinfo]` instances for piping from `Get-ChildItem`.</span></span>

<span data-ttu-id="68e93-155">Поддерживаемые скалярные типы:</span><span class="sxs-lookup"><span data-stu-id="68e93-155">The supported scalar types are:</span></span>

- <span data-ttu-id="68e93-156">`[string]`, `[char]`</span><span class="sxs-lookup"><span data-stu-id="68e93-156">`[string]`, `[char]`</span></span>
- <span data-ttu-id="68e93-157">`[byte]`, `[sbyte]`</span><span class="sxs-lookup"><span data-stu-id="68e93-157">`[byte]`, `[sbyte]`</span></span>
- <span data-ttu-id="68e93-158">`[int16]`, `[uint16]`, `[short]`, `[ushort]`</span><span class="sxs-lookup"><span data-stu-id="68e93-158">`[int16]`, `[uint16]`, `[short]`, `[ushort]`</span></span>
- <span data-ttu-id="68e93-159">`[int]`, `[uint]`, `[int32]`, `[uint32]`,</span><span class="sxs-lookup"><span data-stu-id="68e93-159">`[int]`, `[uint]`, `[int32]`, `[uint32]`,</span></span>
- <span data-ttu-id="68e93-160">`[long]`, `[ulong]`, `[int64]`, `[uint64]`</span><span class="sxs-lookup"><span data-stu-id="68e93-160">`[long]`, `[ulong]`, `[int64]`, `[uint64]`</span></span>
- <span data-ttu-id="68e93-161">`[single]`, `[float]`, `[double]`</span><span class="sxs-lookup"><span data-stu-id="68e93-161">`[single]`, `[float]`, `[double]`</span></span>
- `[boolean]`

<span data-ttu-id="68e93-162">До выхода версии PowerShell 6,2 `Format-Hex` обрабатывает входные данные конвейера с несколькими типами входных данных, объединяя все объекты, аналогичные.</span><span class="sxs-lookup"><span data-stu-id="68e93-162">Prior to PowerShell 6.2, `Format-Hex` would handle a Pipeline input with multiple input types by grouping all like objects together.</span></span> <span data-ttu-id="68e93-163">Теперь он обрабатывает каждый отдельный объект по мере его прохождения через конвейер и не будет группировать объекты вместе, если они не являются смежными объектами.</span><span class="sxs-lookup"><span data-stu-id="68e93-163">Now, it handles each individual object as it passes through the Pipeline and won't group objects together unless like objects are adjacent.</span></span>

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

### <span data-ttu-id="68e93-164">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="68e93-164">-LiteralPath</span></span>

<span data-ttu-id="68e93-165">Указывает полный путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="68e93-165">Specifies the complete path to a file.</span></span> <span data-ttu-id="68e93-166">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="68e93-166">The value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="68e93-167">Этот параметр не принимает подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="68e93-167">This parameter does not accept wildcard characters.</span></span> <span data-ttu-id="68e93-168">Чтобы указать несколько путей к файлам, разделяйте пути запятой.</span><span class="sxs-lookup"><span data-stu-id="68e93-168">To specify multiple paths to files, separate the paths with a comma.</span></span> <span data-ttu-id="68e93-169">Если параметр **LiteralPath** включает escape-символы, заключите путь в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="68e93-169">If the **LiteralPath** parameter includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="68e93-170">PowerShell не интерпретирует символы в одной строке в кавычках как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="68e93-170">PowerShell does not interpret any characters in a single quoted string as escape sequences.</span></span> <span data-ttu-id="68e93-171">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="68e93-171">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="68e93-172">-Path</span><span class="sxs-lookup"><span data-stu-id="68e93-172">-Path</span></span>

<span data-ttu-id="68e93-173">Указывает путь к файлам.</span><span class="sxs-lookup"><span data-stu-id="68e93-173">Specifies the path to files.</span></span> <span data-ttu-id="68e93-174">Используйте точку ( `.` ), чтобы указать текущее расположение.</span><span class="sxs-lookup"><span data-stu-id="68e93-174">Use a dot (`.`) to specify the current location.</span></span> <span data-ttu-id="68e93-175">Символ-шаблон ( `*` ) принимается и может использоваться для указания всех элементов в расположении.</span><span class="sxs-lookup"><span data-stu-id="68e93-175">The wildcard character (`*`) is accepted and can be used to specify all the items in a location.</span></span> <span data-ttu-id="68e93-176">Если параметр **path** включает escape-символы, заключите путь в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="68e93-176">If the **Path** parameter includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="68e93-177">Чтобы указать несколько путей к файлам, разделяйте пути запятой.</span><span class="sxs-lookup"><span data-stu-id="68e93-177">To specify multiple paths to files, separate the paths with a comma.</span></span>

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

### <span data-ttu-id="68e93-178">-RAW</span><span class="sxs-lookup"><span data-stu-id="68e93-178">-Raw</span></span>

<span data-ttu-id="68e93-179">Этот параметр больше не выполняет никаких действий.</span><span class="sxs-lookup"><span data-stu-id="68e93-179">This parameter no longer does anything.</span></span> <span data-ttu-id="68e93-180">Он сохраняется для совместимости скриптов.</span><span class="sxs-lookup"><span data-stu-id="68e93-180">It is retained for script compatibility.</span></span>

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

### <span data-ttu-id="68e93-181">-Offset</span><span class="sxs-lookup"><span data-stu-id="68e93-181">-Offset</span></span>

<span data-ttu-id="68e93-182">Представляет число байтов, которые нужно пропустить, после которого они являются частью шестнадцатеричного вывода.</span><span class="sxs-lookup"><span data-stu-id="68e93-182">This represents the number of bytes to skip from being part of the hex output.</span></span>

<span data-ttu-id="68e93-183">Этот параметр появился в PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="68e93-183">This parameter was introduced in PowerShell 6.2.</span></span>

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

### <span data-ttu-id="68e93-184">— Количество</span><span class="sxs-lookup"><span data-stu-id="68e93-184">-Count</span></span>

<span data-ttu-id="68e93-185">Представляет число байтов, включаемых в Шестнадцатеричный вывод.</span><span class="sxs-lookup"><span data-stu-id="68e93-185">This represents the number of bytes to include in the hex output.</span></span>

<span data-ttu-id="68e93-186">Этот параметр появился в PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="68e93-186">This parameter was introduced in PowerShell 6.2.</span></span>

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

### <span data-ttu-id="68e93-187">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="68e93-187">CommonParameters</span></span>

<span data-ttu-id="68e93-188">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="68e93-188">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="68e93-189">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="68e93-189">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="68e93-190">Входные данные</span><span class="sxs-lookup"><span data-stu-id="68e93-190">INPUTS</span></span>

### <span data-ttu-id="68e93-191">System.String</span><span class="sxs-lookup"><span data-stu-id="68e93-191">System.String</span></span>

<span data-ttu-id="68e93-192">Вы можете передать строку в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="68e93-192">You can pipe a string to this cmdlet.</span></span>

## <span data-ttu-id="68e93-193">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="68e93-193">OUTPUTS</span></span>

### <span data-ttu-id="68e93-194">Microsoft. PowerShell. Commands. Битеколлектион</span><span class="sxs-lookup"><span data-stu-id="68e93-194">Microsoft.PowerShell.Commands.ByteCollection</span></span>

<span data-ttu-id="68e93-195">Этот командлет возвращает **битеколлектион**.</span><span class="sxs-lookup"><span data-stu-id="68e93-195">This cmdlet returns a **ByteCollection**.</span></span> <span data-ttu-id="68e93-196">Этот объект представляет коллекцию байтов.</span><span class="sxs-lookup"><span data-stu-id="68e93-196">This object represents a collection of bytes.</span></span> <span data-ttu-id="68e93-197">Он содержит методы, которые преобразуют коллекцию байтов в строку, отформатированную в виде каждой строки выходных данных, возвращаемых `Format-Hex` .</span><span class="sxs-lookup"><span data-stu-id="68e93-197">It includes methods that convert the collection of bytes to a string formatted like each line of output returned by `Format-Hex`.</span></span> <span data-ttu-id="68e93-198">В выходных данных также указывается тип обрабатываемых байтов.</span><span class="sxs-lookup"><span data-stu-id="68e93-198">The output also states they type of bytes being processed.</span></span> <span data-ttu-id="68e93-199">При указании параметра **path** или **LiteralPath** объект содержит путь к файлу, содержащему каждый байт.</span><span class="sxs-lookup"><span data-stu-id="68e93-199">If you specify the **Path** or **LiteralPath** parameter, the object contains the path of the file that contains each byte.</span></span> <span data-ttu-id="68e93-200">Если передать строку, логическое значение, целое число и т. д., она будет помечена соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="68e93-200">If you pass a string, boolean, integer, etc, it will be labeled appropriately.</span></span>

## <span data-ttu-id="68e93-201">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="68e93-201">NOTES</span></span>

<span data-ttu-id="68e93-202">Правый столбец выходных данных пытается отобразить байты как символы ASCII:</span><span class="sxs-lookup"><span data-stu-id="68e93-202">The right-most column of output tries to render the bytes as ASCII characters:</span></span>

<span data-ttu-id="68e93-203">Как правило, каждый байт интерпретируется как кодовая точка Юникода, что означает:</span><span class="sxs-lookup"><span data-stu-id="68e93-203">Generally, each byte is interpreted as a Unicode code point, which means that:</span></span>

- <span data-ttu-id="68e93-204">Печатаемые символы ASCII всегда отображаются правильно</span><span class="sxs-lookup"><span data-stu-id="68e93-204">Printable ASCII characters are always rendered correctly</span></span>
- <span data-ttu-id="68e93-205">Символы UTF-8 с несколькими байтами никогда не отображаются правильно</span><span class="sxs-lookup"><span data-stu-id="68e93-205">Multi-byte UTF-8 characters never render correctly</span></span>
- <span data-ttu-id="68e93-206">Символы UTF-16 отображаются правильно, только если происходит их старший байт `NUL` .</span><span class="sxs-lookup"><span data-stu-id="68e93-206">UTF-16 characters render correctly only if their high-order byte happens be `NUL`.</span></span>

## <span data-ttu-id="68e93-207">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="68e93-207">RELATED LINKS</span></span>

[<span data-ttu-id="68e93-208">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="68e93-208">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="68e93-209">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="68e93-209">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="68e93-210">Format-List</span><span class="sxs-lookup"><span data-stu-id="68e93-210">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="68e93-211">Format-Table</span><span class="sxs-lookup"><span data-stu-id="68e93-211">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="68e93-212">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="68e93-212">Format-Wide</span></span>](Format-Wide.md)

