---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/add-content?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Content
ms.openlocfilehash: 291ec8f3a3958aa726fafb8032b996296272a21e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226949"
---
# <span data-ttu-id="b816e-103">Add-Content</span><span class="sxs-lookup"><span data-stu-id="b816e-103">Add-Content</span></span>

## <span data-ttu-id="b816e-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b816e-104">SYNOPSIS</span></span>
<span data-ttu-id="b816e-105">Добавляет содержимое в указанные элементы, например слова в файл.</span><span class="sxs-lookup"><span data-stu-id="b816e-105">Adds content to the specified items, such as adding words to a file.</span></span>

## <span data-ttu-id="b816e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b816e-106">SYNTAX</span></span>

### <span data-ttu-id="b816e-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="b816e-107">Path (Default)</span></span>

```
Add-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

### <span data-ttu-id="b816e-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b816e-108">LiteralPath</span></span>

```
Add-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-NoNewline] [-Encoding <Encoding>] [-AsByteStream] [-Stream <string>]
 [<CommonParameters>]
```

## <span data-ttu-id="b816e-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b816e-109">DESCRIPTION</span></span>

<span data-ttu-id="b816e-110">`Add-Content`Командлет добавляет содержимое в указанный элемент или файл.</span><span class="sxs-lookup"><span data-stu-id="b816e-110">The `Add-Content` cmdlet appends content to a specified item or file.</span></span> <span data-ttu-id="b816e-111">Содержимое можно задать прямо в команде либо путем указания объекта, в котором оно хранится.</span><span class="sxs-lookup"><span data-stu-id="b816e-111">You can specify the content by typing the content in the command or by specifying an object that contains the content.</span></span>

<span data-ttu-id="b816e-112">Если необходимо создать файлы или каталоги для следующих примеров, см. раздел [New-Item](New-Item.md).</span><span class="sxs-lookup"><span data-stu-id="b816e-112">If you need to create files or directories for the following examples, see [New-Item](New-Item.md).</span></span>

## <span data-ttu-id="b816e-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="b816e-113">EXAMPLES</span></span>

### <span data-ttu-id="b816e-114">Пример 1. Добавление строки во все текстовые файлы с исключением</span><span class="sxs-lookup"><span data-stu-id="b816e-114">Example 1: Add a string to all text files with an exception</span></span>

<span data-ttu-id="b816e-115">Этот пример добавляет значение к текстовым файлам в текущем каталоге, но исключает файлы на основе имени файла.</span><span class="sxs-lookup"><span data-stu-id="b816e-115">This example appends a value to text files in the current directory but excludes files based on their file name.</span></span>

```powershell
Add-Content -Path .\*.txt -Exclude help* -Value 'End of file'
```

<span data-ttu-id="b816e-116">Параметр **path** указывает все `.txt` файлы в текущем каталоге, но параметр **Exclude** игнорирует имена файлов, соответствующие указанному шаблону.</span><span class="sxs-lookup"><span data-stu-id="b816e-116">The **Path** parameter specifies all `.txt` files in the current directory, but the **Exclude** parameter ignores file names that match the specified pattern.</span></span> <span data-ttu-id="b816e-117">Параметр **value** задает текстовую строку, которая записывается в файлы.</span><span class="sxs-lookup"><span data-stu-id="b816e-117">The **Value** parameter specifies the text string that is written to the files.</span></span>

### <span data-ttu-id="b816e-118">Пример 2. добавление даты в конец указанных файлов</span><span class="sxs-lookup"><span data-stu-id="b816e-118">Example 2: Add a date to the end of the specified files</span></span>

<span data-ttu-id="b816e-119">Этот пример добавляет дату к файлам в текущем каталоге и отображает дату в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b816e-119">This example appends the date to files in the current directory and displays the date in the PowerShell console.</span></span>

```powershell
Add-Content -Path .\DateTimeFile1.log, .\DateTimeFile2.log -Value (Get-Date) -PassThru
Get-Content -Path .\DateTimeFile1.log
```

```Output
Tuesday, May 14, 2019 8:24:27 AM
Tuesday, May 14, 2019 8:24:27 AM
5/14/2019 8:24:27 AM
```

<span data-ttu-id="b816e-120">`Add-Content`Командлет создает два новых файла в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="b816e-120">The `Add-Content` cmdlet creates two new files in the current directory.</span></span> <span data-ttu-id="b816e-121">Параметр **value** содержит выходные данные `Get-Date` командлета.</span><span class="sxs-lookup"><span data-stu-id="b816e-121">The **Value** parameter contains the output of the `Get-Date` cmdlet.</span></span> <span data-ttu-id="b816e-122">Параметр **PassThru** выводит добавленное содержимое в конвейер.</span><span class="sxs-lookup"><span data-stu-id="b816e-122">The **PassThru** parameter outputs the added contents to the pipeline.</span></span>
<span data-ttu-id="b816e-123">Так как нет других командлетов для получения выходных данных, он отображается в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b816e-123">Because there is no other cmdlet to receive the output, it is displayed in the PowerShell console.</span></span>
<span data-ttu-id="b816e-124">`Get-Content`Командлет отображает обновленный файл, `DateTimeFile1.log` .</span><span class="sxs-lookup"><span data-stu-id="b816e-124">The `Get-Content` cmdlet displays the updated file, `DateTimeFile1.log`.</span></span>

### <span data-ttu-id="b816e-125">Пример 3. Добавление содержимого указанного файла в другой файл</span><span class="sxs-lookup"><span data-stu-id="b816e-125">Example 3: Add the contents of a specified file to another file</span></span>

<span data-ttu-id="b816e-126">Этот пример получает содержимое из файла и сохраняет содержимое в переменной.</span><span class="sxs-lookup"><span data-stu-id="b816e-126">This example gets the content from a file and stores the content in a variable.</span></span> <span data-ttu-id="b816e-127">Переменная используется для добавления содержимого в другой файл.</span><span class="sxs-lookup"><span data-stu-id="b816e-127">The variable is used to append the content into another file.</span></span>

```powershell
$From = Get-Content -Path .\CopyFromFile.txt
Add-Content -Path .\CopyToFile.txt -Value $From
Get-Content -Path .\CopyToFile.txt
```

- <span data-ttu-id="b816e-128">`Get-Content`Командлет получает содержимое `CopyFromFile.txt` и сохраняет содержимое `$From` переменной.</span><span class="sxs-lookup"><span data-stu-id="b816e-128">The `Get-Content` cmdlet gets the contents of `CopyFromFile.txt` and stores the contents in the `$From` variable.</span></span>
- <span data-ttu-id="b816e-129">`Add-Content`Командлет обновляет файл, `CopyToFile.txt` используя содержимое `$From` переменной.</span><span class="sxs-lookup"><span data-stu-id="b816e-129">The `Add-Content` cmdlet updates the `CopyToFile.txt` file using the contents of the `$From` variable.</span></span>
- <span data-ttu-id="b816e-130">`Get-Content`Командлет отображает CopyToFile.txt.</span><span class="sxs-lookup"><span data-stu-id="b816e-130">The `Get-Content` cmdlet displays CopyToFile.txt.</span></span>

### <span data-ttu-id="b816e-131">Пример 4. Добавление содержимого указанного файла в другой файл с помощью конвейера</span><span class="sxs-lookup"><span data-stu-id="b816e-131">Example 4: Add the contents of a specified file to another file using the pipeline</span></span>

<span data-ttu-id="b816e-132">Этот пример получает содержимое из файла и передает его в `Add-Content` командлет.</span><span class="sxs-lookup"><span data-stu-id="b816e-132">This example gets the content from a file and pipes it to the `Add-Content` cmdlet.</span></span>

```powershell
Get-Content -Path .\CopyFromFile.txt | Add-Content -Path .\CopyToFile.txt
Get-Content -Path .\CopyToFile.txt
```

<span data-ttu-id="b816e-133">`Get-Content`Командлет возвращает содержимое `CopyFromFile.txt` .</span><span class="sxs-lookup"><span data-stu-id="b816e-133">The `Get-Content` cmdlet gets the contents of `CopyFromFile.txt`.</span></span> <span data-ttu-id="b816e-134">Результаты передаются в `Add-Content` командлет, который обновляет `CopyToFile.txt` .</span><span class="sxs-lookup"><span data-stu-id="b816e-134">The results are piped to the `Add-Content` cmdlet, which updates the `CopyToFile.txt`.</span></span>
<span data-ttu-id="b816e-135">Последний `Get-Content` командлет выводит на экран `CopyToFile.txt` .</span><span class="sxs-lookup"><span data-stu-id="b816e-135">The last `Get-Content` cmdlet displays `CopyToFile.txt`.</span></span>

### <span data-ttu-id="b816e-136">Пример 5. Создание нового файла и копирование содержимого</span><span class="sxs-lookup"><span data-stu-id="b816e-136">Example 5: Create a new file and copy content</span></span>

<span data-ttu-id="b816e-137">В этом примере создается новый файл и копируется содержимое существующего файла в новый файл.</span><span class="sxs-lookup"><span data-stu-id="b816e-137">This example creates a new file and copies an existing file's content into the new file.</span></span>

```powershell
Add-Content -Path .\NewFile.txt -Value (Get-Content -Path .\CopyFromFile.txt)
Get-Content -Path .\NewFile.txt
```

- <span data-ttu-id="b816e-138">`Add-Content`Командлет использует параметры **path** и **value** для создания нового файла в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="b816e-138">The `Add-Content` cmdlet uses the **Path** and **Value** parameters to create a new file in the current directory.</span></span>
- <span data-ttu-id="b816e-139">`Get-Content`Командлет получает содержимое существующего файла `CopyFromFile.txt` и передает его в параметр **value** .</span><span class="sxs-lookup"><span data-stu-id="b816e-139">The `Get-Content` cmdlet gets the contents of an existing file, `CopyFromFile.txt` and passes it to the **Value** parameter.</span></span> <span data-ttu-id="b816e-140">Круглые скобки вокруг `Get-Content` командлета гарантируют, что команда завершится до `Add-Content` начала выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="b816e-140">The parentheses around the `Get-Content` cmdlet ensure that the command finishes before the `Add-Content` command begins.</span></span>
- <span data-ttu-id="b816e-141">`Get-Content`Командлет отображает содержимое нового файла, `NewFile.txt` .</span><span class="sxs-lookup"><span data-stu-id="b816e-141">The `Get-Content` cmdlet displays the contents of the new file, `NewFile.txt`.</span></span>

### <span data-ttu-id="b816e-142">Пример 6. Добавление содержимого в файл, который доступен только для чтения</span><span class="sxs-lookup"><span data-stu-id="b816e-142">Example 6: Add content to a read-only file</span></span>

<span data-ttu-id="b816e-143">Эта команда добавляет значение в файл, даже если атрибуту файла **IsReadOnly** присвоено значение **true**.</span><span class="sxs-lookup"><span data-stu-id="b816e-143">This command adds a value to the file even if the **IsReadOnly** file attribute is set to **True**.</span></span>
<span data-ttu-id="b816e-144">В примере содержатся инструкции по созданию файла, доступного только для чтения.</span><span class="sxs-lookup"><span data-stu-id="b816e-144">The steps to create a read-only file are included in the example.</span></span>

```powershell
New-Item -Path .\IsReadOnlyTextFile.txt -ItemType File
Set-ItemProperty -Path .\IsReadOnlyTextFile.txt -Name IsReadOnly -Value $True
Get-ChildItem -Path .\IsReadOnlyTextFile.txt
Add-Content -Path .\IsReadOnlyTextFile.txt -Value 'Add value to read-only text file' -Force
Get-Content -Path .\IsReadOnlyTextFile.txt
```

```Output
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-ar--         1/28/2019     13:35              0 IsReadOnlyTextFile.txt
```

- <span data-ttu-id="b816e-145">`New-Item`Командлет использует параметры **path** и **ItemType** для создания файла `IsReadOnlyTextFile.txt` в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="b816e-145">The `New-Item` cmdlet uses the **Path** and **ItemType** parameters to create the file `IsReadOnlyTextFile.txt` in the current directory.</span></span>
- <span data-ttu-id="b816e-146">`Set-ItemProperty`Командлет использует параметры **Name** и **value** , чтобы изменить свойство **IsReadOnly** для файла на true.</span><span class="sxs-lookup"><span data-stu-id="b816e-146">The `Set-ItemProperty` cmdlet uses the **Name** and **Value** parameters to change the file's **IsReadOnly** property to True.</span></span>
- <span data-ttu-id="b816e-147">`Get-ChildItem`Командлет показывает, что файл пуст (0) и имеет атрибут "только для чтения" ( `r` ).</span><span class="sxs-lookup"><span data-stu-id="b816e-147">The `Get-ChildItem` cmdlet shows the file is empty (0) and has the read-only attribute (`r`).</span></span>
- <span data-ttu-id="b816e-148">`Add-Content`Командлет использует параметр **path** для указания файла.</span><span class="sxs-lookup"><span data-stu-id="b816e-148">The `Add-Content` cmdlet uses the **Path** parameter to specify the file.</span></span> <span data-ttu-id="b816e-149">Параметр **value** содержит текстовую строку, добавляемую к файлу.</span><span class="sxs-lookup"><span data-stu-id="b816e-149">The **Value** parameter includes the text string to append to the file.</span></span> <span data-ttu-id="b816e-150">Параметр **Force** записывает текст в файл, который доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="b816e-150">The **Force** parameter writes the text to the read-only file.</span></span>
- <span data-ttu-id="b816e-151">`Get-Content`Командлет использует параметр **path** для вывода содержимого файла.</span><span class="sxs-lookup"><span data-stu-id="b816e-151">The `Get-Content` cmdlet uses the **Path** parameter to display the file's contents.</span></span>

<span data-ttu-id="b816e-152">Чтобы удалить атрибут только для чтения, используйте `Set-ItemProperty` команду с параметром **value** , имеющим значение `False` .</span><span class="sxs-lookup"><span data-stu-id="b816e-152">To remove the read-only attribute, use the `Set-ItemProperty` command with the **Value** parameter set to `False`.</span></span>

### <span data-ttu-id="b816e-153">Пример 7. Использование фильтров с Add-Content</span><span class="sxs-lookup"><span data-stu-id="b816e-153">Example 7: Use Filters with Add-Content</span></span>

<span data-ttu-id="b816e-154">Можно указать фильтр для `Add-Content` командлета.</span><span class="sxs-lookup"><span data-stu-id="b816e-154">You can specify a filter to the `Add-Content` cmdlet.</span></span> <span data-ttu-id="b816e-155">При использовании фильтров для уточнения параметра **path** необходимо включить конечную звездочку ( `*` ), чтобы указать содержимое пути.</span><span class="sxs-lookup"><span data-stu-id="b816e-155">When using filters to qualify the **Path** parameter, you need to include a trailing asterisk (`*`) to indicate the contents of the path.</span></span>

<span data-ttu-id="b816e-156">Следующая команда добавляет слово "Готово" к содержимому всех `*.txt` файлов в `C:\Temp` каталоге.</span><span class="sxs-lookup"><span data-stu-id="b816e-156">The following command adds the word "Done" the content of all `*.txt` files in the `C:\Temp` directory.</span></span>

```powershell
Add-Content -Path C:\Temp\* -Filter *.txt -Value "Done"
```

## <span data-ttu-id="b816e-157">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b816e-157">PARAMETERS</span></span>

### <span data-ttu-id="b816e-158">-Асбитестреам</span><span class="sxs-lookup"><span data-stu-id="b816e-158">-AsByteStream</span></span>

<span data-ttu-id="b816e-159">Указывает, что содержимое должно считываться как поток байтов.</span><span class="sxs-lookup"><span data-stu-id="b816e-159">Specifies that the content should be read as a stream of bytes.</span></span> <span data-ttu-id="b816e-160">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="b816e-160">This parameter was introduced in PowerShell 6.0.</span></span>

<span data-ttu-id="b816e-161">При использовании параметра **асбитестреам** с параметром **Encoding** возникает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="b816e-161">A warning occurs when you use the **AsByteStream** parameter with the **Encoding** parameter.</span></span> <span data-ttu-id="b816e-162">Параметр **асбитестреам** игнорирует любую кодировку, и выходные данные возвращаются в виде потока байтов.</span><span class="sxs-lookup"><span data-stu-id="b816e-162">The **AsByteStream** parameter ignores any encoding and the output is returned as a stream of bytes.</span></span>

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

### <span data-ttu-id="b816e-163">-Credential</span><span class="sxs-lookup"><span data-stu-id="b816e-163">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="b816e-164">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b816e-164">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="b816e-165">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="b816e-165">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="b816e-166">-Encoding</span><span class="sxs-lookup"><span data-stu-id="b816e-166">-Encoding</span></span>

<span data-ttu-id="b816e-167">Указывает тип кодировки для целевого файла.</span><span class="sxs-lookup"><span data-stu-id="b816e-167">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="b816e-168">Значение по умолчанию — `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="b816e-168">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="b816e-169">Кодирование — это динамический параметр, который поставщик FileSystem добавляет в `Add-Content` командлет.</span><span class="sxs-lookup"><span data-stu-id="b816e-169">Encoding is a dynamic parameter that the FileSystem provider adds to the `Add-Content` cmdlet.</span></span> <span data-ttu-id="b816e-170">Этот параметр работает только на дисках с файловой системой.</span><span class="sxs-lookup"><span data-stu-id="b816e-170">This parameter works only in file system drives.</span></span>

<span data-ttu-id="b816e-171">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="b816e-171">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="b816e-172">`ascii`: Использует кодировку для набора символов ASCII (7-разрядных).</span><span class="sxs-lookup"><span data-stu-id="b816e-172">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="b816e-173">`bigendianunicode`: Кодируется в формате UTF-16 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="b816e-173">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="b816e-174">`oem`: Использует кодировку по умолчанию для программ MS-DOS и консолей.</span><span class="sxs-lookup"><span data-stu-id="b816e-174">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="b816e-175">`unicode`: Кодируется в формате UTF-16 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="b816e-175">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="b816e-176">`utf7`: Кодируется в формате UTF-7.</span><span class="sxs-lookup"><span data-stu-id="b816e-176">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="b816e-177">`utf8`: Кодируется в формате UTF-8.</span><span class="sxs-lookup"><span data-stu-id="b816e-177">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="b816e-178">`utf8BOM`: Кодирует в формате UTF-8 с меткой порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="b816e-178">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="b816e-179">`utf8NoBOM`: Кодирует в формате UTF-8 без метки порядка байтов (BOM)</span><span class="sxs-lookup"><span data-stu-id="b816e-179">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="b816e-180">`utf32`: Кодируется в формате UTF-32.</span><span class="sxs-lookup"><span data-stu-id="b816e-180">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="b816e-181">Начиная с PowerShell 6,2, параметр **кодировки** также разрешает числовые идентификаторы зарегистрированных кодовых страниц (например `-Encoding 1251` ,) или строковых имен зарегистрированных кодовых страниц (например `-Encoding "windows-1251"` ,).</span><span class="sxs-lookup"><span data-stu-id="b816e-181">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="b816e-182">Дополнительные сведения см. в документации .NET по [кодированию. codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="b816e-182">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

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

### <span data-ttu-id="b816e-183">-Exclude</span><span class="sxs-lookup"><span data-stu-id="b816e-183">-Exclude</span></span>

<span data-ttu-id="b816e-184">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="b816e-184">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="b816e-185">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="b816e-185">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="b816e-186">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="b816e-186">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="b816e-187">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b816e-187">Wildcard characters are permitted.</span></span> <span data-ttu-id="b816e-188">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="b816e-188">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="b816e-189">-Filter</span><span class="sxs-lookup"><span data-stu-id="b816e-189">-Filter</span></span>

<span data-ttu-id="b816e-190">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="b816e-190">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="b816e-191">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="b816e-191">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="b816e-192">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="b816e-192">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="b816e-193">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="b816e-193">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="b816e-194">-Force</span><span class="sxs-lookup"><span data-stu-id="b816e-194">-Force</span></span>

<span data-ttu-id="b816e-195">Переопределяет атрибут «только для чтения», позволяя добавлять содержимое в файл, доступный только для чтения.</span><span class="sxs-lookup"><span data-stu-id="b816e-195">Overrides the read-only attribute, allowing you to add content to a read-only file.</span></span> <span data-ttu-id="b816e-196">Например, параметр **Force** позволяет переопределить атрибут «только для чтения» или создать дополнительные каталоги в пути, не меняя разрешения на доступ к файлу.</span><span class="sxs-lookup"><span data-stu-id="b816e-196">For example, **Force** will override the read-only attribute or create directories to complete a file path, but it will not attempt to change file permissions.</span></span>

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

### <span data-ttu-id="b816e-197">-Include</span><span class="sxs-lookup"><span data-stu-id="b816e-197">-Include</span></span>

<span data-ttu-id="b816e-198">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="b816e-198">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="b816e-199">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="b816e-199">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="b816e-200">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="b816e-200">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="b816e-201">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b816e-201">Wildcard characters are permitted.</span></span> <span data-ttu-id="b816e-202">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="b816e-202">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="b816e-203">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b816e-203">-LiteralPath</span></span>

<span data-ttu-id="b816e-204">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="b816e-204">Specifies a path to one or more locations.</span></span> <span data-ttu-id="b816e-205">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="b816e-205">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="b816e-206">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="b816e-206">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="b816e-207">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="b816e-207">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="b816e-208">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="b816e-208">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="b816e-209">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="b816e-209">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="b816e-210">-Новая строка</span><span class="sxs-lookup"><span data-stu-id="b816e-210">-NoNewline</span></span>

<span data-ttu-id="b816e-211">Указывает, что этот командлет не добавляет новую строку или возврат каретки к содержимому.</span><span class="sxs-lookup"><span data-stu-id="b816e-211">Indicates that this cmdlet does not add a new line or carriage return to the content.</span></span>

<span data-ttu-id="b816e-212">Строковые представления входных объектов сцепляются для формирования выходных данных.</span><span class="sxs-lookup"><span data-stu-id="b816e-212">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="b816e-213">Между выходными строками не вставляются пробелы и символы новой строки.</span><span class="sxs-lookup"><span data-stu-id="b816e-213">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="b816e-214">После последней выходной строки не добавляется новая строка.</span><span class="sxs-lookup"><span data-stu-id="b816e-214">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="b816e-215">-PassThru</span><span class="sxs-lookup"><span data-stu-id="b816e-215">-PassThru</span></span>

<span data-ttu-id="b816e-216">Возвращает объект, представляющий добавленное содержимое.</span><span class="sxs-lookup"><span data-stu-id="b816e-216">Returns an object representing the added content.</span></span> <span data-ttu-id="b816e-217">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="b816e-217">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="b816e-218">-Path</span><span class="sxs-lookup"><span data-stu-id="b816e-218">-Path</span></span>

<span data-ttu-id="b816e-219">Указывает путь к элементам, которые получают дополнительное содержимое.</span><span class="sxs-lookup"><span data-stu-id="b816e-219">Specifies the path to the items that receive the additional content.</span></span>
<span data-ttu-id="b816e-220">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b816e-220">Wildcard characters are permitted.</span></span>
<span data-ttu-id="b816e-221">Пути должны вести к элементам, а не к контейнерам.</span><span class="sxs-lookup"><span data-stu-id="b816e-221">The paths must be paths to items, not to containers.</span></span>
<span data-ttu-id="b816e-222">Например, нужно указать путь к одному или нескольким файлам, а не путь к каталогу.</span><span class="sxs-lookup"><span data-stu-id="b816e-222">For example, you must specify a path to one or more files, not a path to a directory.</span></span>
<span data-ttu-id="b816e-223">Если нужно указать несколько путей, разделите их запятыми.</span><span class="sxs-lookup"><span data-stu-id="b816e-223">If you specify multiple paths, use commas to separate the paths.</span></span>

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

### <span data-ttu-id="b816e-224">-Stream</span><span class="sxs-lookup"><span data-stu-id="b816e-224">-Stream</span></span>

<span data-ttu-id="b816e-225">Указывает альтернативный поток данных для содержимого.</span><span class="sxs-lookup"><span data-stu-id="b816e-225">Specifies an alternative data stream for content.</span></span> <span data-ttu-id="b816e-226">Если поток не существует, этот командлет создаст его.</span><span class="sxs-lookup"><span data-stu-id="b816e-226">If the stream does not exist, this cmdlet creates it.</span></span> <span data-ttu-id="b816e-227">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="b816e-227">Wildcard characters are not supported.</span></span>

<span data-ttu-id="b816e-228">**Stream** — это динамический параметр, к которому добавляется поставщик FileSystem `Add-Content` .</span><span class="sxs-lookup"><span data-stu-id="b816e-228">**Stream** is a dynamic parameter that the FileSystem provider adds to `Add-Content`.</span></span> <span data-ttu-id="b816e-229">Этот параметр работает только на дисках с файловой системой.</span><span class="sxs-lookup"><span data-stu-id="b816e-229">This parameter works only in file system drives.</span></span>

<span data-ttu-id="b816e-230">`Add-Content`С помощью командлета можно изменить содержимое **зоны.** альтернативный поток данных идентификатора.</span><span class="sxs-lookup"><span data-stu-id="b816e-230">You can use the `Add-Content` cmdlet to change the content of the **Zone.Identifier** alternate data stream.</span></span> <span data-ttu-id="b816e-231">Однако не рекомендуется использовать этот способ для устранения проверок безопасности, блокирующих файлы, загружаемые из Интернета.</span><span class="sxs-lookup"><span data-stu-id="b816e-231">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="b816e-232">Если вы убедитесь, что скачанный файл является надежным, используйте `Unblock-File` командлет.</span><span class="sxs-lookup"><span data-stu-id="b816e-232">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="b816e-233">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="b816e-233">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="b816e-234">-Value</span><span class="sxs-lookup"><span data-stu-id="b816e-234">-Value</span></span>

<span data-ttu-id="b816e-235">Задает добавляемое содержимое.</span><span class="sxs-lookup"><span data-stu-id="b816e-235">Specifies the content to be added.</span></span> <span data-ttu-id="b816e-236">Введите строку в кавычках, например **данные, предназначенные только для внутреннего использования** , или укажите объект, содержащий содержимое, например объект **DateTime** , который `Get-Date` создает.</span><span class="sxs-lookup"><span data-stu-id="b816e-236">Type a quoted string, such as **This data is for internal use only** , or specify an object that contains content, such as the **DateTime** object that `Get-Date` generates.</span></span>

<span data-ttu-id="b816e-237">Нельзя указать содержимое файла, введя его путь, поскольку путь является просто строкой.</span><span class="sxs-lookup"><span data-stu-id="b816e-237">You cannot specify the contents of a file by typing its path, because the path is just a string.</span></span>
<span data-ttu-id="b816e-238">`Get-Content`Для получения содержимого и передачи его в параметр **value** можно использовать команду.</span><span class="sxs-lookup"><span data-stu-id="b816e-238">You can use a `Get-Content` command to get the content and pass it to the **Value** parameter.</span></span>

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

### <span data-ttu-id="b816e-239">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b816e-239">-Confirm</span></span>

<span data-ttu-id="b816e-240">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="b816e-240">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b816e-241">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b816e-241">-WhatIf</span></span>

<span data-ttu-id="b816e-242">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="b816e-242">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="b816e-243">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="b816e-243">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b816e-244">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b816e-244">CommonParameters</span></span>

<span data-ttu-id="b816e-245">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="b816e-245">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="b816e-246">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="b816e-246">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="b816e-247">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b816e-247">INPUTS</span></span>

### <span data-ttu-id="b816e-248">System. Object, System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="b816e-248">System.Object, System.Management.Automation.PSCredential</span></span>

<span data-ttu-id="b816e-249">Можно передать значения, пути или учетные данные в `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="b816e-249">You can pipe values, paths, or credentials to `Set-Content`.</span></span>

## <span data-ttu-id="b816e-250">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b816e-250">OUTPUTS</span></span>

### <span data-ttu-id="b816e-251">Нет или System.String</span><span class="sxs-lookup"><span data-stu-id="b816e-251">None or System.String</span></span>

<span data-ttu-id="b816e-252">При использовании параметра **PassThru** `Add-Content` создает объект **System. String** , представляющий содержимое.</span><span class="sxs-lookup"><span data-stu-id="b816e-252">When you use the **PassThru** parameter, `Add-Content` generates a **System.String** object that represents the content.</span></span> <span data-ttu-id="b816e-253">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="b816e-253">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b816e-254">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b816e-254">NOTES</span></span>

- <span data-ttu-id="b816e-255">При передаче объекта в `Add-Content` объект преобразуется в строку перед добавлением в элемент.</span><span class="sxs-lookup"><span data-stu-id="b816e-255">When you pipe an object to `Add-Content`, the object is converted to a string before it is added to the item.</span></span> <span data-ttu-id="b816e-256">Формат строки определяется типом объекта, но может отличаться от используемого по умолчанию формата отображения объекта.</span><span class="sxs-lookup"><span data-stu-id="b816e-256">The object type determines the string format, but the format might be different than the default display of the object.</span></span> <span data-ttu-id="b816e-257">Для управления форматом строки используйте параметры форматирования отправляющего командлета.</span><span class="sxs-lookup"><span data-stu-id="b816e-257">To control the string format, use the formatting parameters of the sending cmdlet.</span></span>
- <span data-ttu-id="b816e-258">Также можно ссылаться `Add-Content` по встроенному псевдониму `ac` .</span><span class="sxs-lookup"><span data-stu-id="b816e-258">You can also refer to `Add-Content` by its built-in alias, `ac`.</span></span> <span data-ttu-id="b816e-259">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="b816e-259">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="b816e-260">`Add-Content`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="b816e-260">The `Add-Content` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="b816e-261">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="b816e-261">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="b816e-262">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="b816e-262">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="b816e-263">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b816e-263">RELATED LINKS</span></span>

[<span data-ttu-id="b816e-264">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="b816e-264">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="b816e-265">about_Providers</span><span class="sxs-lookup"><span data-stu-id="b816e-265">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="b816e-266">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="b816e-266">Clear-Content</span></span>](Clear-Content.md)

[<span data-ttu-id="b816e-267">Get-Content</span><span class="sxs-lookup"><span data-stu-id="b816e-267">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="b816e-268">Get-Item</span><span class="sxs-lookup"><span data-stu-id="b816e-268">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="b816e-269">New-Item</span><span class="sxs-lookup"><span data-stu-id="b816e-269">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="b816e-270">Set-Content</span><span class="sxs-lookup"><span data-stu-id="b816e-270">Set-Content</span></span>](Set-Content.md)