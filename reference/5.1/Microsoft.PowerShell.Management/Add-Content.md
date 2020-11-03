---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/add-content?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Content
ms.openlocfilehash: 903c4eb784c1bb86b66766c7dfb563f586545dc1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228470"
---
# <span data-ttu-id="25986-103">Add-Content</span><span class="sxs-lookup"><span data-stu-id="25986-103">Add-Content</span></span>

## <span data-ttu-id="25986-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="25986-104">SYNOPSIS</span></span>
<span data-ttu-id="25986-105">Добавляет содержимое в указанные элементы, например слова в файл.</span><span class="sxs-lookup"><span data-stu-id="25986-105">Adds content to the specified items, such as adding words to a file.</span></span>

## <span data-ttu-id="25986-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="25986-106">SYNTAX</span></span>

### <span data-ttu-id="25986-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="25986-107">Path (Default)</span></span>

```
Add-Content [-Path] <string[]> [-Value] <Object[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [-NoNewline] [-Encoding <FileSystemCmdletProviderEncoding>]
 [-Stream <string>] [<CommonParameters>]
```

### <span data-ttu-id="25986-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="25986-108">LiteralPath</span></span>

```
Add-Content [-Value] <Object[]> -LiteralPath <string[]> [-PassThru] [-Filter <string>]
 [-Include <string[]>] [-Exclude <string[]>] [-Force] [-Credential <pscredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [-NoNewline] [-Encoding <FileSystemCmdletProviderEncoding>]
 [-Stream <string>] [<CommonParameters>]
```

## <span data-ttu-id="25986-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="25986-109">DESCRIPTION</span></span>

<span data-ttu-id="25986-110">`Add-Content`Командлет добавляет содержимое в указанный элемент или файл.</span><span class="sxs-lookup"><span data-stu-id="25986-110">The `Add-Content` cmdlet appends content to a specified item or file.</span></span> <span data-ttu-id="25986-111">Содержимое можно задать прямо в команде либо путем указания объекта, в котором оно хранится.</span><span class="sxs-lookup"><span data-stu-id="25986-111">You can specify the content by typing the content in the command or by specifying an object that contains the content.</span></span>

<span data-ttu-id="25986-112">Если необходимо создать файлы или каталоги для следующих примеров, см. раздел [New-Item](New-Item.md).</span><span class="sxs-lookup"><span data-stu-id="25986-112">If you need to create files or directories for the following examples, see [New-Item](New-Item.md).</span></span>

## <span data-ttu-id="25986-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="25986-113">EXAMPLES</span></span>

### <span data-ttu-id="25986-114">Пример 1. Добавление строки во все текстовые файлы с исключением</span><span class="sxs-lookup"><span data-stu-id="25986-114">Example 1: Add a string to all text files with an exception</span></span>

<span data-ttu-id="25986-115">Этот пример добавляет значение к текстовым файлам в текущем каталоге, но исключает файлы на основе имени файла.</span><span class="sxs-lookup"><span data-stu-id="25986-115">This example appends a value to text files in the current directory but excludes files based on their file name.</span></span>

```powershell
Add-Content -Path .\*.txt -Exclude help* -Value 'End of file'
```

<span data-ttu-id="25986-116">`Add-Content`Командлет использует параметр **path** для указания всех TXT файлов в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="25986-116">The `Add-Content` cmdlet uses the **Path** parameter to specify all .txt files in the current directory.</span></span> <span data-ttu-id="25986-117">Параметр **Exclude** игнорирует имена файлов, соответствующие указанному шаблону.</span><span class="sxs-lookup"><span data-stu-id="25986-117">The **Exclude** parameter ignores file names that match the specified pattern.</span></span> <span data-ttu-id="25986-118">Параметр **value** задает текстовую строку, которая записывается в файлы.</span><span class="sxs-lookup"><span data-stu-id="25986-118">The **Value** parameter specifies the text string that is written to the files.</span></span>

<span data-ttu-id="25986-119">Чтобы отобразить содержимое этих файлов, используйте [Get-Content](Get-Content.md) .</span><span class="sxs-lookup"><span data-stu-id="25986-119">Use [Get-Content](Get-Content.md) to display the contents of these files.</span></span>

### <span data-ttu-id="25986-120">Пример 2. добавление даты в конец указанных файлов</span><span class="sxs-lookup"><span data-stu-id="25986-120">Example 2: Add a date to the end of the specified files</span></span>

<span data-ttu-id="25986-121">Этот пример добавляет дату к файлам в текущем каталоге и отображает дату в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25986-121">This example appends the date to files in the current directory and displays the date in the PowerShell console.</span></span>

```powershell
Add-Content -Path .\DateTimeFile1.log, .\DateTimeFile2.log -Value (Get-Date) -PassThru
Get-Content -Path .\DateTimeFile1.log
```

<span data-ttu-id="25986-122">`Add-Content`Командлет использует параметры **path** и **value** для создания двух новых файлов в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="25986-122">The `Add-Content` cmdlet uses the **Path** and **Value** parameters to create two new files in the current directory.</span></span> <span data-ttu-id="25986-123">Параметр **value** задает `Get-Date` командлет для получения даты и передает дату в `Add-Content` .</span><span class="sxs-lookup"><span data-stu-id="25986-123">The **Value** parameter specifies the `Get-Date` cmdlet to get the date and passes the date to `Add-Content`.</span></span> <span data-ttu-id="25986-124">`Add-Content`Командлет записывает дату в каждый файл.</span><span class="sxs-lookup"><span data-stu-id="25986-124">The `Add-Content` cmdlet writes the date to each file.</span></span> <span data-ttu-id="25986-125">Параметр **PassThru** передает объект, представляющий объект Date.</span><span class="sxs-lookup"><span data-stu-id="25986-125">The **PassThru** parameter passes an object that represents the date object.</span></span> <span data-ttu-id="25986-126">Так как нет других командлетов для получения переданного объекта, он отображается в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25986-126">Because there is no other cmdlet to receive the passed object, it is displayed in the PowerShell console.</span></span> <span data-ttu-id="25986-127">`Get-Content`Командлет отображает обновленный файл DateTimeFile1. log.</span><span class="sxs-lookup"><span data-stu-id="25986-127">The `Get-Content` cmdlet displays the updated file, DateTimeFile1.log.</span></span>

### <span data-ttu-id="25986-128">Пример 3. Добавление содержимого указанного файла в другой файл</span><span class="sxs-lookup"><span data-stu-id="25986-128">Example 3: Add the contents of a specified file to another file</span></span>

<span data-ttu-id="25986-129">Этот пример получает содержимое из файла и добавляет содержимое в другой файл.</span><span class="sxs-lookup"><span data-stu-id="25986-129">This example gets the content from a file and appends that content into another file.</span></span>

```powershell
Add-Content -Path .\CopyToFile.txt -Value (Get-Content -Path .\CopyFromFile.txt)
Get-Content -Path .\CopyToFile.txt
```

<span data-ttu-id="25986-130">`Add-Content`Командлет использует параметр **path** для указания нового файла в текущем каталоге CopyToFile.txt.</span><span class="sxs-lookup"><span data-stu-id="25986-130">The `Add-Content` cmdlet uses the **Path** parameter to specify the new file in the current directory, CopyToFile.txt.</span></span> <span data-ttu-id="25986-131">Параметр **value** использует `Get-Content` командлет для получения содержимого файла, CopyFromFile.txt.</span><span class="sxs-lookup"><span data-stu-id="25986-131">The **Value** parameter uses the `Get-Content` cmdlet to get the contents of the file, CopyFromFile.txt.</span></span> <span data-ttu-id="25986-132">Круглые скобки вокруг `Get-Content` командлета гарантируют, что команда завершится до `Add-Content` начала выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="25986-132">The parentheses around the `Get-Content` cmdlet ensure that the command finishes before the `Add-Content` command begins.</span></span> <span data-ttu-id="25986-133">Параметр **value** передается в `Add-Content` .</span><span class="sxs-lookup"><span data-stu-id="25986-133">The **Value** parameter is passed to `Add-Content`.</span></span> <span data-ttu-id="25986-134">`Add-Content`Командлет добавляет данные в файл CopyToFile.txt.</span><span class="sxs-lookup"><span data-stu-id="25986-134">The `Add-Content` cmdlet appends the data to the CopyToFile.txt file.</span></span> <span data-ttu-id="25986-135">`Get-Content`Командлет отображает обновленный файл CopyToFile.txt.</span><span class="sxs-lookup"><span data-stu-id="25986-135">The `Get-Content` cmdlet displays the updated file, CopyToFile.txt.</span></span>

### <span data-ttu-id="25986-136">Пример 4. Использование переменной для добавления содержимого указанного файла в другой файл</span><span class="sxs-lookup"><span data-stu-id="25986-136">Example 4: Use a variable to add the contents of a specified file to another file</span></span>

<span data-ttu-id="25986-137">Этот пример получает содержимое из файла и сохраняет содержимое в переменной.</span><span class="sxs-lookup"><span data-stu-id="25986-137">This example gets the content from a file and stores the content in a variable.</span></span> <span data-ttu-id="25986-138">Переменная используется для добавления содержимого в другой файл.</span><span class="sxs-lookup"><span data-stu-id="25986-138">The variable is used to append the content into another file.</span></span>

```powershell
$From = Get-Content -Path .\CopyFromFile.txt
Add-Content -Path .\CopyToFile.txt -Value $From
Get-Content -Path .\CopyToFile.txt
```

<span data-ttu-id="25986-139">`Get-Content`Командлет возвращает содержимое CopyFromFile.txt и сохраняет содержимое в `$From` переменной.</span><span class="sxs-lookup"><span data-stu-id="25986-139">The `Get-Content` cmdlet gets the contents of CopyFromFile.txt and stores the contents in the `$From` variable.</span></span> <span data-ttu-id="25986-140">`Add-Content`Командлет использует параметр **path** для указания файла CopyToFile.txt в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="25986-140">The `Add-Content` cmdlet uses the **Path** parameter to specify the CopyToFile.txt file in the current directory.</span></span> <span data-ttu-id="25986-141">Параметр **value** использует `$From` переменную и передает содержимое в `Add-Content` .</span><span class="sxs-lookup"><span data-stu-id="25986-141">The **Value** parameter uses the `$From` variable and passes the content to `Add-Content`.</span></span> <span data-ttu-id="25986-142">`Add-Content`Командлет обновляет файл CopyToFile.txt.</span><span class="sxs-lookup"><span data-stu-id="25986-142">The `Add-Content` cmdlet updates the CopyToFile.txt file.</span></span> <span data-ttu-id="25986-143">`Get-Content`Командлет отображает CopyToFile.txt.</span><span class="sxs-lookup"><span data-stu-id="25986-143">The `Get-Content` cmdlet displays CopyToFile.txt.</span></span>

### <span data-ttu-id="25986-144">Пример 5. Создание нового файла и копирование содержимого</span><span class="sxs-lookup"><span data-stu-id="25986-144">Example 5: Create a new file and copy content</span></span>

<span data-ttu-id="25986-145">В этом примере создается новый файл и копируется содержимое существующего файла в новый файл.</span><span class="sxs-lookup"><span data-stu-id="25986-145">This example creates a new file and copies an existing file's content into the new file.</span></span>

```powershell
Add-Content -Path .\NewFile.txt -Value (Get-Content -Path .\CopyFromFile.txt)
Get-Content -Path .\NewFile.txt
```

<span data-ttu-id="25986-146">`Add-Content`Командлет использует параметры **path** и **value** для создания нового файла в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="25986-146">The `Add-Content` cmdlet uses the **Path** and **Value** parameters to create a new file in the current directory.</span></span> <span data-ttu-id="25986-147">Параметр **value** использует `Get-Content` командлет для получения содержимого существующего файла, CopyFromFile.txt.</span><span class="sxs-lookup"><span data-stu-id="25986-147">The **Value** parameter uses the `Get-Content` cmdlet to get the contents of an existing file, CopyFromFile.txt.</span></span> <span data-ttu-id="25986-148">Круглые скобки вокруг `Get-Content` командлета гарантируют, что команда завершится до `Add-Content` начала выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="25986-148">The parentheses around the `Get-Content` cmdlet ensure that the command finishes before the `Add-Content` command begins.</span></span> <span data-ttu-id="25986-149">Параметр **value** передает содержимое, в `Add-Content` которое обновляется файл NewFile.txt.</span><span class="sxs-lookup"><span data-stu-id="25986-149">The **Value** parameter passes the content to `Add-Content` which updates the NewFile.txt file.</span></span> <span data-ttu-id="25986-150">`Get-Content`Командлет отображает содержимое нового файла, NewFile.txt.</span><span class="sxs-lookup"><span data-stu-id="25986-150">The `Get-Content` cmdlet displays the contents of the new file, NewFile.txt.</span></span>

### <span data-ttu-id="25986-151">Пример 6. Добавление содержимого в файл, который доступен только для чтения</span><span class="sxs-lookup"><span data-stu-id="25986-151">Example 6: Add content to a read-only file</span></span>

<span data-ttu-id="25986-152">Эта команда добавляет значение в файл, даже если атрибуту файла **IsReadOnly** присвоено значение true.</span><span class="sxs-lookup"><span data-stu-id="25986-152">This command adds the value to the file even if the **IsReadOnly** file attribute is set to True.</span></span>
<span data-ttu-id="25986-153">В примере содержатся инструкции по созданию файла, доступного только для чтения.</span><span class="sxs-lookup"><span data-stu-id="25986-153">The steps to create a read-only file are included in the example.</span></span>

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
-ar---        1/28/2019     13:35              0 IsReadOnlyTextFile.txt
```

<span data-ttu-id="25986-154">`New-Item`Командлет использует параметры **path** и **ItemType** для создания файла IsReadOnlyTextFile.txt в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="25986-154">The `New-Item` cmdlet uses the **Path** and **ItemType** parameters to create the file IsReadOnlyTextFile.txt in the current directory.</span></span> <span data-ttu-id="25986-155">`Set-ItemProperty`Командлет использует параметры **Name** и **value** , чтобы изменить свойство **IsReadOnly** для файла на true.</span><span class="sxs-lookup"><span data-stu-id="25986-155">The `Set-ItemProperty` cmdlet uses the **Name** and **Value** parameters to change the file's **IsReadOnly** property to True.</span></span> <span data-ttu-id="25986-156">`Get-ChildItem`Командлет показывает, что файл пуст (0) и имеет атрибут "только для чтения" ( `r` ).</span><span class="sxs-lookup"><span data-stu-id="25986-156">The `Get-ChildItem` cmdlet shows the file is empty (0) and has the read-only attribute (`r`).</span></span> <span data-ttu-id="25986-157">`Add-Content`Командлет использует параметр **path** для указания файла.</span><span class="sxs-lookup"><span data-stu-id="25986-157">The `Add-Content` cmdlet uses the **Path** parameter to specify the file.</span></span> <span data-ttu-id="25986-158">Параметр **value** содержит текстовую строку, добавляемую к файлу.</span><span class="sxs-lookup"><span data-stu-id="25986-158">The **Value** parameter includes the text string to append to the file.</span></span> <span data-ttu-id="25986-159">Параметр **Force** записывает текст в файл, который доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="25986-159">The **Force** parameter writes the text to the read-only file.</span></span> <span data-ttu-id="25986-160">`Get-Content`Командлет использует параметр **path** для вывода содержимого файла.</span><span class="sxs-lookup"><span data-stu-id="25986-160">The `Get-Content` cmdlet uses the **Path** parameter to display the file's contents.</span></span>

<span data-ttu-id="25986-161">Чтобы удалить атрибут только для чтения, используйте `Set-ItemProperty` команду с параметром **value** , имеющим значение `False` .</span><span class="sxs-lookup"><span data-stu-id="25986-161">To remove the read-only attribute, use the `Set-ItemProperty` command with the **Value** parameter set to `False`.</span></span>

## <span data-ttu-id="25986-162">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="25986-162">PARAMETERS</span></span>

### <span data-ttu-id="25986-163">-Confirm</span><span class="sxs-lookup"><span data-stu-id="25986-163">-Confirm</span></span>

<span data-ttu-id="25986-164">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="25986-164">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="25986-165">-Credential</span><span class="sxs-lookup"><span data-stu-id="25986-165">-Credential</span></span>

<span data-ttu-id="25986-166">Указывает учетную запись пользователя с разрешением на выполнение этого действия.</span><span class="sxs-lookup"><span data-stu-id="25986-166">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="25986-167">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="25986-167">The default is the current user.</span></span>

<span data-ttu-id="25986-168">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , например, созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="25986-168">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="25986-169">При вводе имени пользователя запрашивается пароль.</span><span class="sxs-lookup"><span data-stu-id="25986-169">If you type a user name, you will be prompted for a password.</span></span>

> [!WARNING]
> <span data-ttu-id="25986-170">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25986-170">This parameter is not supported by any providers installed with PowerShell.</span></span>

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

### <span data-ttu-id="25986-171">-Encoding</span><span class="sxs-lookup"><span data-stu-id="25986-171">-Encoding</span></span>

<span data-ttu-id="25986-172">Указывает тип кодировки для целевого файла.</span><span class="sxs-lookup"><span data-stu-id="25986-172">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="25986-173">Значение по умолчанию — `Default`.</span><span class="sxs-lookup"><span data-stu-id="25986-173">The default value is `Default`.</span></span>

<span data-ttu-id="25986-174">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="25986-174">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="25986-175">`Ascii` Использует кодировку ASCII (7-разрядных).</span><span class="sxs-lookup"><span data-stu-id="25986-175">`Ascii` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="25986-176">`BigEndianUnicode` Использует UTF-16 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="25986-176">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="25986-177">`BigEndianUTF32` Использует UTF-32 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="25986-177">`BigEndianUTF32` Uses UTF-32 with the big-endian byte order.</span></span>
- <span data-ttu-id="25986-178">`Byte` Кодирует набор символов в последовательность байтов.</span><span class="sxs-lookup"><span data-stu-id="25986-178">`Byte` Encodes a set of characters into a sequence of bytes.</span></span>
- <span data-ttu-id="25986-179">`Default` Использует кодировку, соответствующую активной кодовой странице системы (обычно ANSI).</span><span class="sxs-lookup"><span data-stu-id="25986-179">`Default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="25986-180">`Oem` Использует кодировку, соответствующую текущей кодовой странице OEM системы.</span><span class="sxs-lookup"><span data-stu-id="25986-180">`Oem` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="25986-181">`String` То же, что и **Юникод** .</span><span class="sxs-lookup"><span data-stu-id="25986-181">`String` Same as **Unicode** .</span></span>
- <span data-ttu-id="25986-182">`Unicode` Использует UTF-16 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="25986-182">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="25986-183">`Unknown` То же, что и **Юникод** .</span><span class="sxs-lookup"><span data-stu-id="25986-183">`Unknown` Same as **Unicode** .</span></span>
- <span data-ttu-id="25986-184">`UTF7` Использует UTF-7.</span><span class="sxs-lookup"><span data-stu-id="25986-184">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="25986-185">`UTF8` Использует UTF-8.</span><span class="sxs-lookup"><span data-stu-id="25986-185">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="25986-186">`UTF32` Использует UTF-32 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="25986-186">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

<span data-ttu-id="25986-187">Кодирование — это динамический параметр, который поставщик FileSystem добавляет в `Add-Content` командлет.</span><span class="sxs-lookup"><span data-stu-id="25986-187">Encoding is a dynamic parameter that the FileSystem provider adds to the `Add-Content` cmdlet.</span></span> <span data-ttu-id="25986-188">Этот параметр работает только на дисках с файловой системой.</span><span class="sxs-lookup"><span data-stu-id="25986-188">This parameter works only in file system drives.</span></span>

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

### <span data-ttu-id="25986-189">-Exclude</span><span class="sxs-lookup"><span data-stu-id="25986-189">-Exclude</span></span>

<span data-ttu-id="25986-190">Исключает указанные элементы.</span><span class="sxs-lookup"><span data-stu-id="25986-190">Omits the specified items.</span></span> <span data-ttu-id="25986-191">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="25986-191">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="25986-192">Введите элемент пути или шаблон, например **\* txt** .</span><span class="sxs-lookup"><span data-stu-id="25986-192">Enter a path element or pattern, such as **\*.txt** .</span></span> <span data-ttu-id="25986-193">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="25986-193">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="25986-194">-Filter</span><span class="sxs-lookup"><span data-stu-id="25986-194">-Filter</span></span>

<span data-ttu-id="25986-195">Задает фильтр в формате или на языке поставщика.</span><span class="sxs-lookup"><span data-stu-id="25986-195">Specifies a filter in the provider's format or language.</span></span> <span data-ttu-id="25986-196">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="25986-196">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="25986-197">Синтаксис фильтра, включая использование подстановочных знаков, зависит от поставщика.</span><span class="sxs-lookup"><span data-stu-id="25986-197">The syntax of the filter, including the use of wildcards, depends on the provider.</span></span> <span data-ttu-id="25986-198">**Фильтры** более эффективны, чем другие параметры, так как поставщик применяет фильтры при извлечении объектов.</span><span class="sxs-lookup"><span data-stu-id="25986-198">**Filters** are more efficient than other parameters because the provider applies filters when objects are retrieved.</span></span> <span data-ttu-id="25986-199">В противном случае PowerShell обрабатывает фильтры после извлечения объектов.</span><span class="sxs-lookup"><span data-stu-id="25986-199">Otherwise, PowerShell processes filters after the objects are retrieved.</span></span>

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

### <span data-ttu-id="25986-200">-Force</span><span class="sxs-lookup"><span data-stu-id="25986-200">-Force</span></span>

<span data-ttu-id="25986-201">Переопределяет атрибут «только для чтения», позволяя добавлять содержимое в файл, доступный только для чтения.</span><span class="sxs-lookup"><span data-stu-id="25986-201">Overrides the read-only attribute, allowing you to add content to a read-only file.</span></span> <span data-ttu-id="25986-202">Например, параметр **Force** позволяет переопределить атрибут «только для чтения» или создать дополнительные каталоги в пути, не меняя разрешения на доступ к файлу.</span><span class="sxs-lookup"><span data-stu-id="25986-202">For example, **Force** will override the read-only attribute or create directories to complete a file path, but it will not attempt to change file permissions.</span></span>

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

### <span data-ttu-id="25986-203">-Include</span><span class="sxs-lookup"><span data-stu-id="25986-203">-Include</span></span>

<span data-ttu-id="25986-204">Добавляет только указанные элементы.</span><span class="sxs-lookup"><span data-stu-id="25986-204">Adds only the specified items.</span></span> <span data-ttu-id="25986-205">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="25986-205">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="25986-206">Введите элемент пути или шаблон, например **\* txt** .</span><span class="sxs-lookup"><span data-stu-id="25986-206">Enter a path element or pattern, such as **\*.txt** .</span></span> <span data-ttu-id="25986-207">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="25986-207">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="25986-208">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="25986-208">-LiteralPath</span></span>

<span data-ttu-id="25986-209">Указывает путь к элементам, которые получают дополнительное содержимое.</span><span class="sxs-lookup"><span data-stu-id="25986-209">Specifies the path to the items that receive the additional content.</span></span> <span data-ttu-id="25986-210">В отличие от параметра **Path** , значение параметра **LiteralPath** используется строго в том виде, в котором оно указано.</span><span class="sxs-lookup"><span data-stu-id="25986-210">Unlike **Path** , the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="25986-211">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="25986-211">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="25986-212">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="25986-212">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="25986-213">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="25986-213">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="25986-214">-Новая строка</span><span class="sxs-lookup"><span data-stu-id="25986-214">-NoNewline</span></span>

<span data-ttu-id="25986-215">Указывает, что этот командлет не добавляет новую строку или возврат каретки к содержимому.</span><span class="sxs-lookup"><span data-stu-id="25986-215">Indicates that this cmdlet does not add a new line or carriage return to the content.</span></span>

<span data-ttu-id="25986-216">Строковые представления входных объектов сцепляются для формирования выходных данных.</span><span class="sxs-lookup"><span data-stu-id="25986-216">The string representations of the input objects are concatenated to form the output.</span></span> <span data-ttu-id="25986-217">Между выходными строками не вставляются пробелы и символы новой строки.</span><span class="sxs-lookup"><span data-stu-id="25986-217">No spaces or newlines are inserted between the output strings.</span></span> <span data-ttu-id="25986-218">После последней выходной строки не добавляется новая строка.</span><span class="sxs-lookup"><span data-stu-id="25986-218">No newline is added after the last output string.</span></span>

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

### <span data-ttu-id="25986-219">-PassThru</span><span class="sxs-lookup"><span data-stu-id="25986-219">-PassThru</span></span>

<span data-ttu-id="25986-220">Возвращает объект, представляющий добавленное содержимое.</span><span class="sxs-lookup"><span data-stu-id="25986-220">Returns an object representing the added content.</span></span> <span data-ttu-id="25986-221">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="25986-221">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="25986-222">-Path</span><span class="sxs-lookup"><span data-stu-id="25986-222">-Path</span></span>

<span data-ttu-id="25986-223">Указывает путь к элементам, которые получают дополнительное содержимое.</span><span class="sxs-lookup"><span data-stu-id="25986-223">Specifies the path to the items that receive the additional content.</span></span> <span data-ttu-id="25986-224">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="25986-224">Wildcards are permitted.</span></span> <span data-ttu-id="25986-225">Если нужно указать несколько путей, разделите их запятыми.</span><span class="sxs-lookup"><span data-stu-id="25986-225">If you specify multiple paths, use commas to separate the paths.</span></span>

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

### <span data-ttu-id="25986-226">-Stream</span><span class="sxs-lookup"><span data-stu-id="25986-226">-Stream</span></span>

<span data-ttu-id="25986-227">Указывает альтернативный поток данных для содержимого.</span><span class="sxs-lookup"><span data-stu-id="25986-227">Specifies an alternative data stream for content.</span></span> <span data-ttu-id="25986-228">Если поток не существует, этот командлет создаст его.</span><span class="sxs-lookup"><span data-stu-id="25986-228">If the stream does not exist, this cmdlet creates it.</span></span> <span data-ttu-id="25986-229">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="25986-229">Wildcard characters are not supported.</span></span>

<span data-ttu-id="25986-230">**Stream** — это динамический параметр, к которому добавляется поставщик FileSystem `Add-Content` .</span><span class="sxs-lookup"><span data-stu-id="25986-230">**Stream** is a dynamic parameter that the FileSystem provider adds to `Add-Content`.</span></span> <span data-ttu-id="25986-231">Этот параметр работает только на дисках с файловой системой.</span><span class="sxs-lookup"><span data-stu-id="25986-231">This parameter works only in file system drives.</span></span>

<span data-ttu-id="25986-232">`Add-Content`С помощью командлета можно изменить содержимое **зоны.** альтернативный поток данных идентификатора.</span><span class="sxs-lookup"><span data-stu-id="25986-232">You can use the `Add-Content` cmdlet to change the content of the **Zone.Identifier** alternate data stream.</span></span> <span data-ttu-id="25986-233">Однако не рекомендуется использовать этот способ для устранения проверок безопасности, блокирующих файлы, загружаемые из Интернета.</span><span class="sxs-lookup"><span data-stu-id="25986-233">However, we do not recommend this as a way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="25986-234">Если вы убедитесь, что скачанный файл является надежным, используйте `Unblock-File` командлет.</span><span class="sxs-lookup"><span data-stu-id="25986-234">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="25986-235">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="25986-235">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="25986-236">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="25986-236">-UseTransaction</span></span>

<span data-ttu-id="25986-237">Включает команду в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="25986-237">Includes the command in the active transaction.</span></span> <span data-ttu-id="25986-238">Этот параметр доступен только при выполнении транзакции.</span><span class="sxs-lookup"><span data-stu-id="25986-238">This parameter is valid only when a transaction is in progress.</span></span> <span data-ttu-id="25986-239">Дополнительные сведения см. в разделе [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span><span class="sxs-lookup"><span data-stu-id="25986-239">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

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

### <span data-ttu-id="25986-240">-Value</span><span class="sxs-lookup"><span data-stu-id="25986-240">-Value</span></span>

<span data-ttu-id="25986-241">Задает добавляемое содержимое.</span><span class="sxs-lookup"><span data-stu-id="25986-241">Specifies the content to be added.</span></span> <span data-ttu-id="25986-242">Введите строку в кавычках, например **данные, предназначенные только для внутреннего использования** , или укажите объект, содержащий содержимое, например объект **DateTime** , который `Get-Date` создает.</span><span class="sxs-lookup"><span data-stu-id="25986-242">Type a quoted string, such as **This data is for internal use only** , or specify an object that contains content, such as the **DateTime** object that `Get-Date` generates.</span></span>

<span data-ttu-id="25986-243">Нельзя указать содержимое файла, введя его путь, поскольку путь является просто строкой.</span><span class="sxs-lookup"><span data-stu-id="25986-243">You cannot specify the contents of a file by typing its path, because the path is just a string.</span></span>
<span data-ttu-id="25986-244">`Get-Content`Для получения содержимого и передачи его в параметр **value** можно использовать команду.</span><span class="sxs-lookup"><span data-stu-id="25986-244">You can use a `Get-Content` command to get the content and pass it to the **Value** parameter.</span></span>

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

### <span data-ttu-id="25986-245">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="25986-245">-WhatIf</span></span>

<span data-ttu-id="25986-246">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="25986-246">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="25986-247">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="25986-247">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="25986-248">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="25986-248">CommonParameters</span></span>

<span data-ttu-id="25986-249">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="25986-249">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="25986-250">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="25986-250">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="25986-251">Входные данные</span><span class="sxs-lookup"><span data-stu-id="25986-251">INPUTS</span></span>

### <span data-ttu-id="25986-252">System. Object, System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="25986-252">System.Object, System.Management.Automation.PSCredential</span></span>

<span data-ttu-id="25986-253">Можно передать значения, пути или учетные данные в `Set-Content` .</span><span class="sxs-lookup"><span data-stu-id="25986-253">You can pipe values, paths, or credentials to `Set-Content`.</span></span>

## <span data-ttu-id="25986-254">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="25986-254">OUTPUTS</span></span>

### <span data-ttu-id="25986-255">Нет или System.String</span><span class="sxs-lookup"><span data-stu-id="25986-255">None or System.String</span></span>

<span data-ttu-id="25986-256">При использовании параметра **PassThru** `Add-Content` создает объект **System. String** , представляющий содержимое.</span><span class="sxs-lookup"><span data-stu-id="25986-256">When you use the **PassThru** parameter, `Add-Content` generates a **System.String** object that represents the content.</span></span> <span data-ttu-id="25986-257">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="25986-257">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="25986-258">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="25986-258">NOTES</span></span>

<span data-ttu-id="25986-259">При передаче объекта в `Add-Content` объект преобразуется в строку перед добавлением в элемент.</span><span class="sxs-lookup"><span data-stu-id="25986-259">When you pipe an object to `Add-Content`, the object is converted to a string before it is added to the item.</span></span> <span data-ttu-id="25986-260">Формат строки определяется типом объекта, но может отличаться от используемого по умолчанию формата отображения объекта.</span><span class="sxs-lookup"><span data-stu-id="25986-260">The object type determines the string format, but the format might be different than the default display of the object.</span></span> <span data-ttu-id="25986-261">Для управления форматом строки используйте параметры форматирования отправляющего командлета.</span><span class="sxs-lookup"><span data-stu-id="25986-261">To control the string format, use the formatting parameters of the sending cmdlet.</span></span>

<span data-ttu-id="25986-262">Также можно ссылаться `Add-Content` по встроенному псевдониму `ac` .</span><span class="sxs-lookup"><span data-stu-id="25986-262">You can also refer to `Add-Content` by its built-in alias, `ac`.</span></span> <span data-ttu-id="25986-263">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="25986-263">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="25986-264">`Add-Content`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="25986-264">The `Add-Content` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="25986-265">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="25986-265">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="25986-266">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="25986-266">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="25986-267">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="25986-267">RELATED LINKS</span></span>

[<span data-ttu-id="25986-268">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="25986-268">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="25986-269">about_Providers</span><span class="sxs-lookup"><span data-stu-id="25986-269">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="25986-270">about_Transactions</span><span class="sxs-lookup"><span data-stu-id="25986-270">about_Transactions</span></span>](../Microsoft.PowerShell.Core/About/about_Transactions.md)

[<span data-ttu-id="25986-271">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="25986-271">Clear-Content</span></span>](Clear-Content.md)

[<span data-ttu-id="25986-272">Get-Content</span><span class="sxs-lookup"><span data-stu-id="25986-272">Get-Content</span></span>](Get-Content.md)

[<span data-ttu-id="25986-273">Get-Item</span><span class="sxs-lookup"><span data-stu-id="25986-273">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="25986-274">New-Item</span><span class="sxs-lookup"><span data-stu-id="25986-274">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="25986-275">Set-Content</span><span class="sxs-lookup"><span data-stu-id="25986-275">Set-Content</span></span>](Set-Content.md)
