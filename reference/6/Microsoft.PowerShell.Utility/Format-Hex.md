---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/17/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-hex?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Hex
ms.openlocfilehash: 64275e72f8c21942179431b3aed4a17d328aa2e9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229026"
---
# <span data-ttu-id="fbff2-103">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="fbff2-103">Format-Hex</span></span>

## <span data-ttu-id="fbff2-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="fbff2-104">SYNOPSIS</span></span>

<span data-ttu-id="fbff2-105">Отображает файл или другие входные данные в шестнадцатеричном формате.</span><span class="sxs-lookup"><span data-stu-id="fbff2-105">Displays a file or other input as hexadecimal.</span></span>

## <span data-ttu-id="fbff2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fbff2-106">SYNTAX</span></span>

### <span data-ttu-id="fbff2-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="fbff2-107">Path (Default)</span></span>

```
Format-Hex [-Path] <string[]> [-Count <long>] [-Offset <long>] [<CommonParameters>]
```

### <span data-ttu-id="fbff2-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="fbff2-108">LiteralPath</span></span>

```
Format-Hex -LiteralPath <string[]> [-Count <long>] [-Offset <long>] [<CommonParameters>]
```

### <span data-ttu-id="fbff2-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="fbff2-109">InputObject</span></span>

```
Format-Hex -InputObject <psobject> [-Encoding <Encoding>] [-Count <long>] [-Offset <long>] [-Raw] [<CommonParameters>]
```

## <span data-ttu-id="fbff2-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fbff2-110">DESCRIPTION</span></span>

<span data-ttu-id="fbff2-111">`Format-Hex`Командлет отображает файл или другие входные данные в виде шестнадцатеричных значений.</span><span class="sxs-lookup"><span data-stu-id="fbff2-111">The `Format-Hex` cmdlet displays a file or other input as hexadecimal values.</span></span> <span data-ttu-id="fbff2-112">Чтобы определить смещение символа от выходных данных, добавьте номер, расположенный слева от строки, к номеру в верхней части столбца для этого символа.</span><span class="sxs-lookup"><span data-stu-id="fbff2-112">To determine the offset of a character from the output, add the number at the leftmost of the row to the number at the top of the column for that character.</span></span>

<span data-ttu-id="fbff2-113">`Format-Hex`Командлет помогает определить тип файла поврежденного файла или файл, который может не иметь расширения имени файла.</span><span class="sxs-lookup"><span data-stu-id="fbff2-113">The `Format-Hex` cmdlet can help you determine the file type of a corrupted file or a file that might not have a filename extension.</span></span> <span data-ttu-id="fbff2-114">Можно выполнить этот командлет, а затем прочитать шестнадцатеричные выходные данные, чтобы получить сведения о файле.</span><span class="sxs-lookup"><span data-stu-id="fbff2-114">You can run this cmdlet, and then read the hexadecimal output to get file information.</span></span>

<span data-ttu-id="fbff2-115">При использовании `Format-Hex` для файла командлет игнорирует символы новой строки и возвращает все содержимое файла в одной строке с сохраненными символами новой строки.</span><span class="sxs-lookup"><span data-stu-id="fbff2-115">When using `Format-Hex` on a file, the cmdlet ignores newline characters and returns the entire contents of a file in one string with the newline characters preserved.</span></span>

## <span data-ttu-id="fbff2-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="fbff2-116">EXAMPLES</span></span>

### <span data-ttu-id="fbff2-117">Пример 1. получение шестнадцатеричного представления строки</span><span class="sxs-lookup"><span data-stu-id="fbff2-117">Example 1: Get the hexadecimal representation of a string</span></span>

<span data-ttu-id="fbff2-118">Эта команда возвращает шестнадцатеричные значения строки.</span><span class="sxs-lookup"><span data-stu-id="fbff2-118">This command returns the hexadecimal values of a string.</span></span>

```powershell
'Hello World' | Format-Hex
```

```Output
           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   48 65 6C 6C 6F 20 57 6F 72 6C 64                 Hello World
```

<span data-ttu-id="fbff2-119">Строка **Hello World** отправляется в командлет по конвейеру `Format-Hex` .</span><span class="sxs-lookup"><span data-stu-id="fbff2-119">The string **Hello World** is sent down the pipeline to the `Format-Hex` cmdlet.</span></span> <span data-ttu-id="fbff2-120">Шестнадцатеричные выходные данные `Format-Hex` показывают значения каждого символа в строке.</span><span class="sxs-lookup"><span data-stu-id="fbff2-120">The hexadecimal output from `Format-Hex` shows the values of each character in the string.</span></span>

### <span data-ttu-id="fbff2-121">Пример 2. Поиск типа файла из шестнадцатеричного вывода</span><span class="sxs-lookup"><span data-stu-id="fbff2-121">Example 2: Find a file type from hexadecimal output</span></span>

<span data-ttu-id="fbff2-122">В этом примере используется шестнадцатеричный вывод для определения типа файла.</span><span class="sxs-lookup"><span data-stu-id="fbff2-122">This example uses the hexadecimal output to determine the file type.</span></span> <span data-ttu-id="fbff2-123">Командлет отображает полный путь к файлу и шестнадцатеричные значения.</span><span class="sxs-lookup"><span data-stu-id="fbff2-123">The cmdlet displays the file's full path and the hexadecimal values.</span></span>

<span data-ttu-id="fbff2-124">Чтобы проверить следующую команду, создайте копию существующего PDF-файла на локальном компьютере и переименуйте скопированный файл в `File.t7f` .</span><span class="sxs-lookup"><span data-stu-id="fbff2-124">To test the following command, make a copy of an existing PDF file on your local computer and rename the copied file to `File.t7f`.</span></span>

```powershell
Format-Hex -Path .\File.t7f
```

```Output
           Path: C:\Test\File.t7f

           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   25 50 44 46 2D 31 2E 35 0D 0A 25 B5 B5 B5 B5 0D  %PDF-1.5..%????.
00000010   0A 31 20 30 20 6F 62 6A 0D 0A 3C 3C 2F 54 79 70  .1 0 obj..<</Typ
00000020   65 2F 43 61 74 61 6C 6F 67 2F 50 61 67 65 73 20  e/Catalog/Pages
```

<span data-ttu-id="fbff2-125">`Format-Hex`Командлет использует параметр **path** для указания имени файла в текущем каталоге **File. t7f** .</span><span class="sxs-lookup"><span data-stu-id="fbff2-125">The `Format-Hex` cmdlet uses the **Path** parameter to specify a filename in the current directory, **File.t7f** .</span></span> <span data-ttu-id="fbff2-126">Расширение файла **. t7f** является редким, но Шестнадцатеричный вывод **% PDF** показывает, что это файл PDF.</span><span class="sxs-lookup"><span data-stu-id="fbff2-126">The file extension **.t7f** is uncommon, but the hexadecimal output **%PDF** shows that it is a PDF file.</span></span>

## <span data-ttu-id="fbff2-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fbff2-127">PARAMETERS</span></span>

### <span data-ttu-id="fbff2-128">-Encoding</span><span class="sxs-lookup"><span data-stu-id="fbff2-128">-Encoding</span></span>

<span data-ttu-id="fbff2-129">Задает кодировку выходных данных.</span><span class="sxs-lookup"><span data-stu-id="fbff2-129">Specifies the encoding of the output.</span></span> <span data-ttu-id="fbff2-130">Это относится только к `[string]` входным данным.</span><span class="sxs-lookup"><span data-stu-id="fbff2-130">This only applies to `[string]` input.</span></span> <span data-ttu-id="fbff2-131">Параметр не влияет на числовые типы.</span><span class="sxs-lookup"><span data-stu-id="fbff2-131">The parameter has no effect on numeric types.</span></span> <span data-ttu-id="fbff2-132">Значение по умолчанию — `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="fbff2-132">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="fbff2-133">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="fbff2-133">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="fbff2-134">`ascii`: Использует кодировку для набора символов ASCII (7-разрядных).</span><span class="sxs-lookup"><span data-stu-id="fbff2-134">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="fbff2-135">`bigendianunicode`: Кодируется в формате UTF-16 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="fbff2-135">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="fbff2-136">`oem`: Использует кодировку по умолчанию для программ MS-DOS и консолей.</span><span class="sxs-lookup"><span data-stu-id="fbff2-136">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="fbff2-137">`unicode`: Кодируется в формате UTF-16 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="fbff2-137">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="fbff2-138">`utf7`: Кодируется в формате UTF-7.</span><span class="sxs-lookup"><span data-stu-id="fbff2-138">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="fbff2-139">`utf8`: Кодируется в формате UTF-8.</span><span class="sxs-lookup"><span data-stu-id="fbff2-139">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="fbff2-140">`utf8BOM`: Кодирует в формате UTF-8 с меткой порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="fbff2-140">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="fbff2-141">`utf8NoBOM`: Кодирует в формате UTF-8 без метки порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="fbff2-141">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="fbff2-142">`utf32`: Кодируется в формате UTF-32.</span><span class="sxs-lookup"><span data-stu-id="fbff2-142">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="fbff2-143">Начиная с PowerShell 6,2, параметр **кодировки** также разрешает числовые идентификаторы зарегистрированных кодовых страниц (например `-Encoding 1251` ,) или строковых имен зарегистрированных кодовых страниц (например `-Encoding "windows-1251"` ,).</span><span class="sxs-lookup"><span data-stu-id="fbff2-143">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="fbff2-144">Дополнительные сведения см. в документации .NET по [кодированию. codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="fbff2-144">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

```yaml
Type: Encoding
Parameter Sets: ByInputObject
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fbff2-145">-InputObject</span><span class="sxs-lookup"><span data-stu-id="fbff2-145">-InputObject</span></span>

<span data-ttu-id="fbff2-146">Используется для входных данных конвейера.</span><span class="sxs-lookup"><span data-stu-id="fbff2-146">Used for pipeline input.</span></span> <span data-ttu-id="fbff2-147">Входные данные конвейера поддерживают только определенные скалярные типы и `[system.io.fileinfo]` экземпляры для передачи по конвейеру `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="fbff2-147">Pipeline input supports only certain scalar types and `[system.io.fileinfo]` instances for piping from `Get-ChildItem`.</span></span>

<span data-ttu-id="fbff2-148">Поддерживаемые скалярные типы:</span><span class="sxs-lookup"><span data-stu-id="fbff2-148">The supported scalar types are:</span></span>

- <span data-ttu-id="fbff2-149">`[string]`, `[char]`</span><span class="sxs-lookup"><span data-stu-id="fbff2-149">`[string]`, `[char]`</span></span>
- <span data-ttu-id="fbff2-150">`[byte]`, `[sbyte]`</span><span class="sxs-lookup"><span data-stu-id="fbff2-150">`[byte]`, `[sbyte]`</span></span>
- <span data-ttu-id="fbff2-151">`[int16]`, `[uint16]`, `[short]`, `[ushort]`</span><span class="sxs-lookup"><span data-stu-id="fbff2-151">`[int16]`, `[uint16]`, `[short]`, `[ushort]`</span></span>
- <span data-ttu-id="fbff2-152">`[int]`, `[uint]`, `[int32]`, `[uint32]`,</span><span class="sxs-lookup"><span data-stu-id="fbff2-152">`[int]`, `[uint]`, `[int32]`, `[uint32]`,</span></span>
- <span data-ttu-id="fbff2-153">`[long]`, `[ulong]`, `[int64]`, `[uint64]`</span><span class="sxs-lookup"><span data-stu-id="fbff2-153">`[long]`, `[ulong]`, `[int64]`, `[uint64]`</span></span>
- <span data-ttu-id="fbff2-154">`[single]`, `[float]`, `[double]`</span><span class="sxs-lookup"><span data-stu-id="fbff2-154">`[single]`, `[float]`, `[double]`</span></span>

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

### <span data-ttu-id="fbff2-155">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="fbff2-155">-LiteralPath</span></span>

<span data-ttu-id="fbff2-156">Указывает полный путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="fbff2-156">Specifies the complete path to a file.</span></span> <span data-ttu-id="fbff2-157">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="fbff2-157">The value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="fbff2-158">Этот параметр не принимает подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="fbff2-158">This parameter does not accept wildcard characters.</span></span> <span data-ttu-id="fbff2-159">Чтобы указать несколько путей к файлам, разделяйте пути запятой.</span><span class="sxs-lookup"><span data-stu-id="fbff2-159">To specify multiple paths to files, separate the paths with a comma.</span></span> <span data-ttu-id="fbff2-160">Если параметр **LiteralPath** включает escape-символы, заключите путь в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="fbff2-160">If the **LiteralPath** parameter includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="fbff2-161">PowerShell не интерпретирует символы в одной строке в кавычках как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="fbff2-161">PowerShell does not interpret any characters in a single quoted string as escape sequences.</span></span> <span data-ttu-id="fbff2-162">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="fbff2-162">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="fbff2-163">-Path</span><span class="sxs-lookup"><span data-stu-id="fbff2-163">-Path</span></span>

<span data-ttu-id="fbff2-164">Указывает путь к файлам.</span><span class="sxs-lookup"><span data-stu-id="fbff2-164">Specifies the path to files.</span></span> <span data-ttu-id="fbff2-165">Используйте точку ( `.` ), чтобы указать текущее расположение.</span><span class="sxs-lookup"><span data-stu-id="fbff2-165">Use a dot (`.`) to specify the current location.</span></span> <span data-ttu-id="fbff2-166">Символ-шаблон ( `*` ) принимается и может использоваться для указания всех элементов в расположении.</span><span class="sxs-lookup"><span data-stu-id="fbff2-166">The wildcard character (`*`) is accepted and can be used to specify all the items in a location.</span></span> <span data-ttu-id="fbff2-167">Если параметр **path** включает escape-символы, заключите путь в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="fbff2-167">If the **Path** parameter includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="fbff2-168">Чтобы указать несколько путей к файлам, разделяйте пути запятой.</span><span class="sxs-lookup"><span data-stu-id="fbff2-168">To specify multiple paths to files, separate the paths with a comma.</span></span>

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

### <span data-ttu-id="fbff2-169">-RAW</span><span class="sxs-lookup"><span data-stu-id="fbff2-169">-Raw</span></span>

<span data-ttu-id="fbff2-170">Этот параметр больше не выполняет никаких действий.</span><span class="sxs-lookup"><span data-stu-id="fbff2-170">This parameter no longer does anything.</span></span> <span data-ttu-id="fbff2-171">Он сохраняется для совместимости скриптов.</span><span class="sxs-lookup"><span data-stu-id="fbff2-171">It is retained for script compatibility.</span></span>

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

### <span data-ttu-id="fbff2-172">-Offset</span><span class="sxs-lookup"><span data-stu-id="fbff2-172">-Offset</span></span>

<span data-ttu-id="fbff2-173">Представляет число байтов, которые нужно пропустить, после которого они являются частью шестнадцатеричного вывода.</span><span class="sxs-lookup"><span data-stu-id="fbff2-173">This represents the number of bytes to skip from being part of the hex output.</span></span>

<span data-ttu-id="fbff2-174">Этот параметр появился в PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="fbff2-174">This parameter was introduced in PowerShell 6.2.</span></span>

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

### <span data-ttu-id="fbff2-175">— Количество</span><span class="sxs-lookup"><span data-stu-id="fbff2-175">-Count</span></span>

<span data-ttu-id="fbff2-176">Представляет число байтов, включаемых в Шестнадцатеричный вывод.</span><span class="sxs-lookup"><span data-stu-id="fbff2-176">This represents the number of bytes to include in the hex output.</span></span>

<span data-ttu-id="fbff2-177">Этот параметр появился в PowerShell 6,2.</span><span class="sxs-lookup"><span data-stu-id="fbff2-177">This parameter was introduced in PowerShell 6.2.</span></span>

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

### <span data-ttu-id="fbff2-178">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="fbff2-178">CommonParameters</span></span>

<span data-ttu-id="fbff2-179">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fbff2-179">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fbff2-180">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fbff2-180">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fbff2-181">Входные данные</span><span class="sxs-lookup"><span data-stu-id="fbff2-181">INPUTS</span></span>

### <span data-ttu-id="fbff2-182">System.String</span><span class="sxs-lookup"><span data-stu-id="fbff2-182">System.String</span></span>

<span data-ttu-id="fbff2-183">Вы можете передать строку в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="fbff2-183">You can pipe a string to this cmdlet.</span></span>

## <span data-ttu-id="fbff2-184">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="fbff2-184">OUTPUTS</span></span>

### <span data-ttu-id="fbff2-185">Microsoft. PowerShell. Commands. Битеколлектион</span><span class="sxs-lookup"><span data-stu-id="fbff2-185">Microsoft.PowerShell.Commands.ByteCollection</span></span>

<span data-ttu-id="fbff2-186">Этот командлет возвращает **битеколлектион** .</span><span class="sxs-lookup"><span data-stu-id="fbff2-186">This cmdlet returns a **ByteCollection** .</span></span> <span data-ttu-id="fbff2-187">Этот объект представляет коллекцию байтов.</span><span class="sxs-lookup"><span data-stu-id="fbff2-187">This object represents a collection of bytes.</span></span> <span data-ttu-id="fbff2-188">Он содержит методы, которые преобразуют коллекцию байтов в строку, отформатированную в виде каждой строки выходных данных, возвращаемых `Format-Hex` .</span><span class="sxs-lookup"><span data-stu-id="fbff2-188">It includes methods that convert the collection of bytes to a string formatted like each line of output returned by `Format-Hex`.</span></span> <span data-ttu-id="fbff2-189">Если указать **путь** или параметр **LiteralPath** , объект также будет содержать путь к файлу, содержащему каждый байт.</span><span class="sxs-lookup"><span data-stu-id="fbff2-189">If you specify the **Path** or **LiteralPath** parameter, the object also contains the path of the file that contains each byte.</span></span>

## <span data-ttu-id="fbff2-190">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="fbff2-190">NOTES</span></span>

<span data-ttu-id="fbff2-191">Правый столбец выходных данных пытается отобразить байты как символы ASCII:</span><span class="sxs-lookup"><span data-stu-id="fbff2-191">The right-most column of output tries to render the bytes as ASCII characters:</span></span>

<span data-ttu-id="fbff2-192">Как правило, каждый байт интерпретируется как кодовая точка Юникода, что означает:</span><span class="sxs-lookup"><span data-stu-id="fbff2-192">Generally, each byte is interpreted as a Unicode code point, which means that:</span></span>

- <span data-ttu-id="fbff2-193">Печатаемые символы ASCII всегда отображаются правильно</span><span class="sxs-lookup"><span data-stu-id="fbff2-193">Printable ASCII characters are always rendered correctly</span></span>
- <span data-ttu-id="fbff2-194">Символы UTF-8 с несколькими байтами никогда не отображаются правильно</span><span class="sxs-lookup"><span data-stu-id="fbff2-194">Multi-byte UTF-8 characters never render correctly</span></span>
- <span data-ttu-id="fbff2-195">Символы UTF-16 отображаются правильно, только если происходит их старший байт `NUL` .</span><span class="sxs-lookup"><span data-stu-id="fbff2-195">UTF-16 characters render correctly only if their high-order byte happens be `NUL`.</span></span>

## <span data-ttu-id="fbff2-196">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="fbff2-196">RELATED LINKS</span></span>

[<span data-ttu-id="fbff2-197">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="fbff2-197">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="fbff2-198">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="fbff2-198">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="fbff2-199">Format-List</span><span class="sxs-lookup"><span data-stu-id="fbff2-199">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="fbff2-200">Format-Table</span><span class="sxs-lookup"><span data-stu-id="fbff2-200">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="fbff2-201">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="fbff2-201">Format-Wide</span></span>](Format-Wide.md)
