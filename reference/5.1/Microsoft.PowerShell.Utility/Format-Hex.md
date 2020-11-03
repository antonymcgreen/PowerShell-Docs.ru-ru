---
external help file: Microsoft.PowerShell.Utility-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/17/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-hex?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Hex
ms.openlocfilehash: 514a66ebee3827de998622a738c75d4f8e0c7279
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227678"
---
# <span data-ttu-id="4f8f3-103">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="4f8f3-103">Format-Hex</span></span>

## <span data-ttu-id="4f8f3-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4f8f3-104">SYNOPSIS</span></span>

<span data-ttu-id="4f8f3-105">Отображает файл или другие входные данные в шестнадцатеричном формате.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-105">Displays a file or other input as hexadecimal.</span></span>

## <span data-ttu-id="4f8f3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4f8f3-106">SYNTAX</span></span>

### <span data-ttu-id="4f8f3-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="4f8f3-107">Path (Default)</span></span>

```
Format-Hex [-Path] <string[]> [<CommonParameters>]
```

### <span data-ttu-id="4f8f3-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="4f8f3-108">LiteralPath</span></span>

```
Format-Hex -LiteralPath <string[]> [<CommonParameters>]
```

### <span data-ttu-id="4f8f3-109">бинпутобжект</span><span class="sxs-lookup"><span data-stu-id="4f8f3-109">ByInputObject</span></span>

```
Format-Hex -InputObject <Object> [-Encoding <string>] [-Raw] [<CommonParameters>]
```

## <span data-ttu-id="4f8f3-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4f8f3-110">DESCRIPTION</span></span>

<span data-ttu-id="4f8f3-111">`Format-Hex`Командлет отображает файл или другие входные данные в виде шестнадцатеричных значений.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-111">The `Format-Hex` cmdlet displays a file or other input as hexadecimal values.</span></span> <span data-ttu-id="4f8f3-112">Чтобы определить смещение символа от выходных данных, добавьте номер, расположенный слева от строки, к номеру в верхней части столбца для этого символа.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-112">To determine the offset of a character from the output, add the number at the leftmost of the row to the number at the top of the column for that character.</span></span>

<span data-ttu-id="4f8f3-113">`Format-Hex`Командлет помогает определить тип файла поврежденного файла или файл, который может не иметь расширения имени файла.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-113">The `Format-Hex` cmdlet can help you determine the file type of a corrupted file or a file that might not have a filename extension.</span></span> <span data-ttu-id="4f8f3-114">Можно выполнить этот командлет, а затем прочитать шестнадцатеричные выходные данные, чтобы получить сведения о файле.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-114">You can run this cmdlet, and then read the hexadecimal output to get file information.</span></span>

<span data-ttu-id="4f8f3-115">При использовании `Format-Hex` для файла командлет игнорирует символы новой строки и возвращает все содержимое файла в одной строке с сохраненными символами новой строки.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-115">When using `Format-Hex` on a file, the cmdlet ignores newline characters and returns the entire contents of a file in one string with the newline characters preserved.</span></span>

## <span data-ttu-id="4f8f3-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="4f8f3-116">EXAMPLES</span></span>

### <span data-ttu-id="4f8f3-117">Пример 1. получение шестнадцатеричного представления строки</span><span class="sxs-lookup"><span data-stu-id="4f8f3-117">Example 1: Get the hexadecimal representation of a string</span></span>

<span data-ttu-id="4f8f3-118">Эта команда возвращает шестнадцатеричные значения строки.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-118">This command returns the hexadecimal values of a string.</span></span>

```powershell
'Hello World' | Format-Hex
```

```Output
           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   48 65 6C 6C 6F 20 57 6F 72 6C 64                 Hello World
```

<span data-ttu-id="4f8f3-119">Строка **Hello World** отправляется в командлет по конвейеру `Format-Hex` .</span><span class="sxs-lookup"><span data-stu-id="4f8f3-119">The string **Hello World** is sent down the pipeline to the `Format-Hex` cmdlet.</span></span> <span data-ttu-id="4f8f3-120">Шестнадцатеричные выходные данные `Format-Hex` показывают значения каждого символа в строке.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-120">The hexadecimal output from `Format-Hex` shows the values of each character in the string.</span></span>

### <span data-ttu-id="4f8f3-121">Пример 2. Поиск типа файла из шестнадцатеричного вывода</span><span class="sxs-lookup"><span data-stu-id="4f8f3-121">Example 2: Find a file type from hexadecimal output</span></span>

<span data-ttu-id="4f8f3-122">В этом примере используется шестнадцатеричный вывод для определения типа файла.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-122">This example uses the hexadecimal output to determine the file type.</span></span> <span data-ttu-id="4f8f3-123">Командлет отображает полный путь к файлу и шестнадцатеричные значения.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-123">The cmdlet displays the file's full path and the hexadecimal values.</span></span>

<span data-ttu-id="4f8f3-124">Чтобы проверить следующую команду, создайте копию существующего PDF-файла на локальном компьютере и переименуйте скопированный файл в **файл File. t7f**.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-124">To test the following command, make a copy of an existing PDF file on your local computer and rename the copied file to **File.t7f**.</span></span>

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

<span data-ttu-id="4f8f3-125">`Format-Hex`Командлет использует параметр **path** для указания имени файла в текущем каталоге, `File.t7f` .</span><span class="sxs-lookup"><span data-stu-id="4f8f3-125">The `Format-Hex` cmdlet uses the **Path** parameter to specify a filename in the current directory, `File.t7f`.</span></span> <span data-ttu-id="4f8f3-126">Расширение файла `.t7f` является редким, но шестнадцатеричные выходные данные `%PDF` показывают, что это файл PDF.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-126">The file extension `.t7f` is uncommon, but the hexadecimal output `%PDF` shows that it is a PDF file.</span></span>

### <span data-ttu-id="4f8f3-127">Пример 3. Отображение необработанных шестнадцатеричных выходных данных</span><span class="sxs-lookup"><span data-stu-id="4f8f3-127">Example 3: Display raw hexadecimal output</span></span>

<span data-ttu-id="4f8f3-128">По умолчанию `Format-Hex` имеет значение Compact для числовых типов данных: однобайтовые или двухбайтовые последовательности используются, если они достаточно малы.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-128">By default `Format-Hex` opts for compact output of numeric data types: single-byte or double-byte sequences are used if the value is small enough.</span></span> <span data-ttu-id="4f8f3-129">**Необработанный** параметр отключает такое поведение.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-129">The **Raw** parameter deactivates this behavior.</span></span>

```
PS> 1,2,3,1000 | Format-Hex

           Path:

           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   01 02 03 E8 03                                   ...è.


PS> 1,2,3,1000 | Format-Hex -Raw

           Path:

           00 01 02 03 04 05 06 07 08 09 0A 0B 0C 0D 0E 0F

00000000   01 00 00 00 02 00 00 00 03 00 00 00 E8 03 00 00  ............è...
```

<span data-ttu-id="4f8f3-130">Обратите внимание на разницу в выходных данных.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-130">Notice the difference in output.</span></span> <span data-ttu-id="4f8f3-131">Параметр **RAW** отображает числа в виде 4-байтовых значений (true) для их типов **Int32** .</span><span class="sxs-lookup"><span data-stu-id="4f8f3-131">The **Raw** parameter displays the numbers as 4-byte values, true to their **Int32** types.</span></span>

## <span data-ttu-id="4f8f3-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4f8f3-132">PARAMETERS</span></span>

### <span data-ttu-id="4f8f3-133">-Encoding</span><span class="sxs-lookup"><span data-stu-id="4f8f3-133">-Encoding</span></span>

<span data-ttu-id="4f8f3-134">Задает кодировку выходных данных.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-134">Specifies the encoding of the output.</span></span> <span data-ttu-id="4f8f3-135">Это относится только к `[string]` входным данным.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-135">This only applies to `[string]` input.</span></span> <span data-ttu-id="4f8f3-136">Параметр не влияет на числовые типы.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-136">The parameter has no effect on numeric types.</span></span> <span data-ttu-id="4f8f3-137">Значение по умолчанию — `ASCII`.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-137">The default value is `ASCII`.</span></span>

<span data-ttu-id="4f8f3-138">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="4f8f3-138">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="4f8f3-139">`Ascii` Использует кодировку ASCII (7-разрядных).</span><span class="sxs-lookup"><span data-stu-id="4f8f3-139">`Ascii` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="4f8f3-140">`BigEndianUnicode` Использует UTF-16 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-140">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="4f8f3-141">`Unicode` Использует UTF-16 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-141">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="4f8f3-142">`UTF7` Использует UTF-7.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-142">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="4f8f3-143">`UTF8` Использует UTF-8.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-143">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="4f8f3-144">`UTF32` Использует UTF-32 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-144">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

<span data-ttu-id="4f8f3-145">Символы, не входящие в набор ASCII, выводятся в виде литеральных `?` символов, что приводит к утрате информации.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-145">Non-ASCII characters in the input are output as literal `?` characters resulting in a loss of information.</span></span>

```yaml
Type: System.String
Parameter Sets: ByInputObject
Aliases:
Accepted values: ASCII, BigEndianUnicode, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: ASCII
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4f8f3-146">-InputObject</span><span class="sxs-lookup"><span data-stu-id="4f8f3-146">-InputObject</span></span>

<span data-ttu-id="4f8f3-147">Используется для входных данных конвейера.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-147">Used for pipeline input.</span></span> <span data-ttu-id="4f8f3-148">Входные данные конвейера поддерживают только определенные скалярные типы и `[system.io.fileinfo]` экземпляры для передачи по конвейеру `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="4f8f3-148">Pipeline input supports only certain scalar types and `[system.io.fileinfo]` instances for piping from `Get-ChildItem`.</span></span>

<span data-ttu-id="4f8f3-149">Поддерживаемые скалярные типы:</span><span class="sxs-lookup"><span data-stu-id="4f8f3-149">The supported scalar types are:</span></span>

- `[string]`
- `[byte]`
- <span data-ttu-id="4f8f3-150">`[int]`, `[int32]`</span><span class="sxs-lookup"><span data-stu-id="4f8f3-150">`[int]`, `[int32]`</span></span>
- <span data-ttu-id="4f8f3-151">`[long]`, `[int64]`</span><span class="sxs-lookup"><span data-stu-id="4f8f3-151">`[long]`, `[int64]`</span></span>

```yaml
Type: System.Object
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4f8f3-152">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="4f8f3-152">-LiteralPath</span></span>

<span data-ttu-id="4f8f3-153">Указывает полный путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-153">Specifies the complete path to a file.</span></span> <span data-ttu-id="4f8f3-154">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-154">The value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="4f8f3-155">Этот параметр не принимает подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-155">This parameter does not accept wildcard characters.</span></span> <span data-ttu-id="4f8f3-156">Чтобы указать несколько путей к файлам, разделяйте пути запятой.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-156">To specify multiple paths to files, separate the paths with a comma.</span></span> <span data-ttu-id="4f8f3-157">Если параметр **LiteralPath** включает escape-символы, заключите путь в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-157">If the **LiteralPath** parameter includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="4f8f3-158">PowerShell не интерпретирует символы в одной строке в кавычках как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-158">PowerShell does not interpret any characters in a single quoted string as escape sequences.</span></span> <span data-ttu-id="4f8f3-159">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="4f8f3-159">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4f8f3-160">-Path</span><span class="sxs-lookup"><span data-stu-id="4f8f3-160">-Path</span></span>

<span data-ttu-id="4f8f3-161">Указывает путь к файлам.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-161">Specifies the path to files.</span></span> <span data-ttu-id="4f8f3-162">Используйте точку ( `.` ), чтобы указать текущее расположение.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-162">Use a dot (`.`) to specify the current location.</span></span> <span data-ttu-id="4f8f3-163">Символ-шаблон ( `*` ) принимается и может использоваться для указания всех элементов в расположении.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-163">The wildcard character (`*`) is accepted and can be used to specify all the items in a location.</span></span> <span data-ttu-id="4f8f3-164">Если параметр **path** включает escape-символы, заключите путь в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-164">If the **Path** parameter includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="4f8f3-165">Чтобы указать несколько путей к файлам, разделяйте пути запятой.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-165">To specify multiple paths to files, separate the paths with a comma.</span></span>

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

### <span data-ttu-id="4f8f3-166">-RAW</span><span class="sxs-lookup"><span data-stu-id="4f8f3-166">-Raw</span></span>

<span data-ttu-id="4f8f3-167">По умолчанию `Format-Hex` имеет значение Compact для числовых типов данных: однобайтовые или двухбайтовые последовательности используются, если они достаточно малы.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-167">By default `Format-Hex` opts for compact output of numeric data types: single-byte or double-byte sequences are used if the value is small enough.</span></span> <span data-ttu-id="4f8f3-168">**Необработанный** параметр отключает такое поведение.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-168">The **Raw** parameter deactivates this behavior.</span></span>

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

### <span data-ttu-id="4f8f3-169">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="4f8f3-169">CommonParameters</span></span>

<span data-ttu-id="4f8f3-170">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-170">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4f8f3-171">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4f8f3-171">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4f8f3-172">Входные данные</span><span class="sxs-lookup"><span data-stu-id="4f8f3-172">INPUTS</span></span>

### <span data-ttu-id="4f8f3-173">System.String</span><span class="sxs-lookup"><span data-stu-id="4f8f3-173">System.String</span></span>

<span data-ttu-id="4f8f3-174">Вы можете передать строку в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-174">You can pipe a string to this cmdlet.</span></span>

## <span data-ttu-id="4f8f3-175">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="4f8f3-175">OUTPUTS</span></span>

### <span data-ttu-id="4f8f3-176">Microsoft. PowerShell. Commands. Битеколлектион</span><span class="sxs-lookup"><span data-stu-id="4f8f3-176">Microsoft.PowerShell.Commands.ByteCollection</span></span>

<span data-ttu-id="4f8f3-177">Этот командлет возвращает **битеколлектион**.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-177">This cmdlet returns a **ByteCollection**.</span></span> <span data-ttu-id="4f8f3-178">Этот объект представляет коллекцию байтов.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-178">This object represents a collection of bytes.</span></span> <span data-ttu-id="4f8f3-179">Он содержит методы, которые преобразуют коллекцию байтов в строку, отформатированную в виде каждой строки выходных данных, возвращаемых `Format-Hex` .</span><span class="sxs-lookup"><span data-stu-id="4f8f3-179">It includes methods that convert the collection of bytes to a string formatted like each line of output returned by `Format-Hex`.</span></span> <span data-ttu-id="4f8f3-180">Если указать **путь** или параметр **LiteralPath** , объект также будет содержать путь к файлу, содержащему каждый байт.</span><span class="sxs-lookup"><span data-stu-id="4f8f3-180">If you specify the **Path** or **LiteralPath** parameter, the object also contains the path of the file that contains each byte.</span></span>

## <span data-ttu-id="4f8f3-181">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="4f8f3-181">NOTES</span></span>

<span data-ttu-id="4f8f3-182">Правый столбец выходных данных пытается визуализировать байты как символы:</span><span class="sxs-lookup"><span data-stu-id="4f8f3-182">The right-most column of output tries to render the bytes as characters:</span></span>

<span data-ttu-id="4f8f3-183">Как правило, каждый байт интерпретируется как кодовая точка Юникода, что означает:</span><span class="sxs-lookup"><span data-stu-id="4f8f3-183">Generally, each byte is interpreted as a Unicode code point, which means that:</span></span>

- <span data-ttu-id="4f8f3-184">Печатаемые символы ASCII всегда отображаются правильно</span><span class="sxs-lookup"><span data-stu-id="4f8f3-184">Printable ASCII characters are always rendered correctly</span></span>
- <span data-ttu-id="4f8f3-185">Символы UTF-8 с несколькими байтами никогда не отображаются правильно</span><span class="sxs-lookup"><span data-stu-id="4f8f3-185">Multi-byte UTF-8 characters never render correctly</span></span>
- <span data-ttu-id="4f8f3-186">Символы UTF-16 отображаются правильно, только если происходит их старший байт `NUL` .</span><span class="sxs-lookup"><span data-stu-id="4f8f3-186">UTF-16 characters render correctly only if their high-order byte happens be `NUL`.</span></span>

## <span data-ttu-id="4f8f3-187">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="4f8f3-187">RELATED LINKS</span></span>

[<span data-ttu-id="4f8f3-188">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="4f8f3-188">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="4f8f3-189">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="4f8f3-189">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="4f8f3-190">Format-List</span><span class="sxs-lookup"><span data-stu-id="4f8f3-190">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="4f8f3-191">Format-Table</span><span class="sxs-lookup"><span data-stu-id="4f8f3-191">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="4f8f3-192">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="4f8f3-192">Format-Wide</span></span>](Format-Wide.md)
