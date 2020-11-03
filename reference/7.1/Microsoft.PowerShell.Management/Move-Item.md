---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/move-item?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Move-Item
ms.openlocfilehash: 1898d0b80e715c817612b54d795d0c2f57b6c6b7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226470"
---
# <span data-ttu-id="c6fa9-103">Move-Item</span><span class="sxs-lookup"><span data-stu-id="c6fa9-103">Move-Item</span></span>

## <span data-ttu-id="c6fa9-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c6fa9-104">SYNOPSIS</span></span>
<span data-ttu-id="c6fa9-105">Перемещает элемент из одного расположения в другое.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-105">Moves an item from one location to another.</span></span>

## <span data-ttu-id="c6fa9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c6fa9-106">SYNTAX</span></span>

### <span data-ttu-id="c6fa9-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="c6fa9-107">Path (Default)</span></span>

```
Move-Item [-Path] <String[]> [[-Destination] <String>] [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-PassThru] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c6fa9-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="c6fa9-108">LiteralPath</span></span>

```
Move-Item -LiteralPath <String[]> [[-Destination] <String>] [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-PassThru] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c6fa9-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c6fa9-109">DESCRIPTION</span></span>

<span data-ttu-id="c6fa9-110">`Move-Item`Командлет перемещает элемент, включая его свойства, содержимое и дочерние элементы, из одного расположения в другое.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-110">The `Move-Item` cmdlet moves an item, including its properties, contents, and child items, from one location to another location.</span></span> <span data-ttu-id="c6fa9-111">Оба расположения должны поддерживаться одним и тем же поставщиком.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-111">The locations must be supported by the same provider.</span></span>
<span data-ttu-id="c6fa9-112">Например, файл или вложенный каталог можно переместить из одного каталога в другой, а подраздел реестра — из одного раздела в другой.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-112">For example, it can move a file or subdirectory from one directory to another or move a registry subkey from one key to another.</span></span>
<span data-ttu-id="c6fa9-113">При перемещении элемент удаляется в исходном расположении и создается в новом.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-113">When you move an item, it is added to the new location and deleted from its original location.</span></span>

## <span data-ttu-id="c6fa9-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="c6fa9-114">EXAMPLES</span></span>

### <span data-ttu-id="c6fa9-115">Пример 1. Перемещение файла в другой каталог и его переименование</span><span class="sxs-lookup"><span data-stu-id="c6fa9-115">Example 1: Move a file to another directory and rename it</span></span>

<span data-ttu-id="c6fa9-116">Эта команда перемещает `Test.txt` файл с `C:` диска в `E:\Temp` каталог и переименовывает его с `test.txt` на `tst.txt` .</span><span class="sxs-lookup"><span data-stu-id="c6fa9-116">This command moves the `Test.txt` file from the `C:` drive to the `E:\Temp` directory and renames it from `test.txt` to `tst.txt`.</span></span>

```powershell
Move-Item -Path C:\test.txt -Destination E:\Temp\tst.txt
```

### <span data-ttu-id="c6fa9-117">Пример 2. Перемещение каталога и его содержимого в другой каталог</span><span class="sxs-lookup"><span data-stu-id="c6fa9-117">Example 2: Move a directory and its contents to another directory</span></span>

<span data-ttu-id="c6fa9-118">Эта команда перемещает `C:\Temp` каталог и его содержимое в `C:\Logs` каталог.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-118">This command moves the `C:\Temp` directory and its contents to the `C:\Logs` directory.</span></span>
<span data-ttu-id="c6fa9-119">Каталог "Temp" и все его подкаталоги и файлы появятся в каталоге "Logs".</span><span class="sxs-lookup"><span data-stu-id="c6fa9-119">The "Temp" directory, and all of its subdirectories and files, then appear in the "Logs" directory.</span></span>

```powershell
Move-Item -Path C:\Temp -Destination C:\Logs
```

### <span data-ttu-id="c6fa9-120">Пример 3. Перемещение всех файлов указанного расширения из текущего каталога в другой каталог</span><span class="sxs-lookup"><span data-stu-id="c6fa9-120">Example 3: Move all files of a specified extension from the current directory to another directory</span></span>

<span data-ttu-id="c6fa9-121">Эта команда перемещает все текстовые файлы ( `*.txt` ) в текущем каталоге (представленные точкой ( `.` )) в `C:\Logs` каталог.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-121">This command moves all of the text files (`*.txt`) in the current directory (represented by a dot (`.`)) to the `C:\Logs` directory.</span></span>

```powershell
Move-Item -Path .\*.txt -Destination C:\Logs
```

### <span data-ttu-id="c6fa9-122">Пример 4. рекурсивное перемещение всех файлов указанного расширения из текущего каталога в другой каталог</span><span class="sxs-lookup"><span data-stu-id="c6fa9-122">Example 4: Recursively move all files of a specified extension from the current directory to another directory</span></span>

<span data-ttu-id="c6fa9-123">Эта команда рекурсивно перемещает все текстовые файлы из текущего каталога и всех подкаталогов в каталог "К:\текстфилес".</span><span class="sxs-lookup"><span data-stu-id="c6fa9-123">This command moves all of the text files from the current directory and all subdirectories, recursively, to the "C:\TextFiles" directory.</span></span>

```powershell
Get-ChildItem -Path ".\*.txt" -Recurse | Move-Item -Destination "C:\TextFiles"
```

<span data-ttu-id="c6fa9-124">Команда использует командлет, `Get-ChildItem` чтобы получить все дочерние элементы в текущем каталоге (представленном точкой \[ \] ) и его подкаталогах с *расширением txt. Он использует параметр **Recurse** рекурсии, чтобы получить рекурсивные значения и параметр Include, чтобы ограничить извлечение* файлами. txt.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-124">The command uses the `Get-ChildItem` cmdlet to get all of the child items in the current directory (represented by the dot \[.\]) and its subdirectories that have a " *.txt" file name extension. It uses the **Recurse** parameter to make the retrieval recursive and the Include parameter to limit the retrieval to "*.txt" files.</span></span>

<span data-ttu-id="c6fa9-125">Оператор конвейера ( `|` ) отправляет результаты этой команды в `Move-Item` , который перемещает текстовые файлы в каталог "Textfiles".</span><span class="sxs-lookup"><span data-stu-id="c6fa9-125">The pipeline operator (`|`) sends the results of this command to `Move-Item`, which moves the text files to the "TextFiles" directory.</span></span>

<span data-ttu-id="c6fa9-126">Если файлы, которые нужно переместить в "К:\текстфилес", имеют одинаковое имя, `Move-Item` выводит сообщение об ошибке и продолжается, но перемещает только один файл с каждым именем в "к:\текстфилес".</span><span class="sxs-lookup"><span data-stu-id="c6fa9-126">If files that are to be moved to "C:\Textfiles" have the same name, `Move-Item` displays an error and continues, but it moves only one file with each name to "C:\Textfiles".</span></span>
<span data-ttu-id="c6fa9-127">Другие файлы остаются в исходных каталогах.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-127">The other files remain in their original directories.</span></span>

<span data-ttu-id="c6fa9-128">Если каталог "Textfiles" (или любой другой элемент конечного пути) не существует, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-128">If the "Textfiles" directory (or any other element of the destination path) does not exist, the command fails.</span></span>
<span data-ttu-id="c6fa9-129">Отсутствующий каталог не создается, даже если используется параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="c6fa9-129">The missing directory is not created for you, even if you use the **Force** parameter.</span></span>
<span data-ttu-id="c6fa9-130">`Move-Item` перемещает первый элемент в файл с именем «Textfiles», а затем выводит сообщение об ошибке, объясняющее, что файл уже существует.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-130">`Move-Item` moves the first item to a file called "Textfiles" and then displays an error explaining that the file already exists.</span></span>

<span data-ttu-id="c6fa9-131">Кроме того, по умолчанию не `Get-ChildItem` перемещает скрытые файлы.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-131">Also, by default, `Get-ChildItem` does not move hidden files.</span></span>
<span data-ttu-id="c6fa9-132">Чтобы переместить скрытые файлы, используйте параметр **Force** с `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="c6fa9-132">To move hidden files, use the **Force** parameter with `Get-ChildItem`.</span></span>

> [!NOTE]
> <span data-ttu-id="c6fa9-133">В Windows PowerShell 2,0 при использовании параметра **рекурсии** `Get-ChildItem` командлета значение параметра **path** должно быть контейнером.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-133">In Windows PowerShell 2.0, when using the **Recurse** parameter of the `Get-ChildItem` cmdlet, the value of the **Path** parameter must be a container.</span></span>
> <span data-ttu-id="c6fa9-134">Используйте параметр **include** , чтобы указать txt-файл для расширения имени файла ( `Get-ChildItem -Path .\* -Include *.txt -Recurse | Move-Item -Destination C:\TextFiles` ).</span><span class="sxs-lookup"><span data-stu-id="c6fa9-134">Use the **Include** parameter to specify the .txt file name extension filter (`Get-ChildItem -Path .\* -Include *.txt -Recurse | Move-Item -Destination C:\TextFiles`).</span></span>

### <span data-ttu-id="c6fa9-135">Пример 5. перемещение разделов и значений реестра в другой раздел</span><span class="sxs-lookup"><span data-stu-id="c6fa9-135">Example 5: Move registry keys and values to another key</span></span>

<span data-ttu-id="c6fa9-136">Эта команда перемещает разделы и значения реестра, содержащиеся в разделе реестра MyCompany, в `HKLM\Software` раздел "миневкомпани".</span><span class="sxs-lookup"><span data-stu-id="c6fa9-136">This command moves the registry keys and values within the "MyCompany" registry key in `HKLM\Software` to the "MyNewCompany" key.</span></span>
<span data-ttu-id="c6fa9-137">Символ-шаблон ( `*` ) указывает, что необходимо переместить содержимое ключа MyCompany, а не сам ключ.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-137">The wildcard character (`*`) indicates that the contents of the "MyCompany" key should be moved, not the key itself.</span></span>
<span data-ttu-id="c6fa9-138">В этой команде необязательные имена параметров **path** и **Destination** опускаются.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-138">In this command, the optional **Path** and **Destination** parameter names are omitted.</span></span>

```powershell
Move-Item "HKLM:\software\mycompany\*" "HKLM:\software\mynewcompany"
```

### <span data-ttu-id="c6fa9-139">Пример 6. Перемещение каталога и его содержимого в подкаталог указанного каталога</span><span class="sxs-lookup"><span data-stu-id="c6fa9-139">Example 6: Move a directory and its contents to a subdirectory of the specified directory</span></span>

<span data-ttu-id="c6fa9-140">Эта команда перемещает каталог " \[ logs \` 2006 \] " (и его содержимое) в каталог "Logs \[ 2006 \] ".</span><span class="sxs-lookup"><span data-stu-id="c6fa9-140">This command moves the "Logs\[Sept\`06\]" directory (and its contents) into the "Logs\[2006\]" directory.</span></span>

```powershell
Move-Item -LiteralPath 'Logs[Sept`06]' -Destination 'Logs[2006]'
```

<span data-ttu-id="c6fa9-141">Параметр **LiteralPath** используется вместо **path** , так как имя исходного каталога включает открывающую и закрывающую квадратные скобки (" \[ " и " \] ").</span><span class="sxs-lookup"><span data-stu-id="c6fa9-141">The **LiteralPath** parameter is used instead of **Path** , because the original directory name includes left bracket and right bracket characters ("\[" and "\]").</span></span>
<span data-ttu-id="c6fa9-142">Путь также заключается в одинарные кавычки (' '), поэтому символ обратного апострофа ( \` ) не интерпретируется правильно.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-142">The path is also enclosed in single quotation marks (' '), so that the backtick symbol (\`) is not misinterpreted.</span></span>

<span data-ttu-id="c6fa9-143">Параметру **назначения** не требуется путь к литералу, так как переменная назначения также должна быть заключена в одинарные кавычки, так как она содержит скобки, которые могут быть неверно интерпретированы.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-143">The **Destination** parameter does not require a literal path, because the Destination variable also must be enclosed in single quotation marks, because it includes brackets that can be misinterpreted.</span></span>

## <span data-ttu-id="c6fa9-144">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c6fa9-144">PARAMETERS</span></span>

### <span data-ttu-id="c6fa9-145">-Credential</span><span class="sxs-lookup"><span data-stu-id="c6fa9-145">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="c6fa9-146">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-146">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="c6fa9-147">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="c6fa9-147">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c6fa9-148">-Destination</span><span class="sxs-lookup"><span data-stu-id="c6fa9-148">-Destination</span></span>

<span data-ttu-id="c6fa9-149">Указывает путь к новому расположению элементов.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-149">Specifies the path to the location where the items are being moved.</span></span>
<span data-ttu-id="c6fa9-150">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-150">The default is the current directory.</span></span>
<span data-ttu-id="c6fa9-151">Знаки подстановки использовать можно, но в результате должно быть задано только одно расположение.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-151">Wildcards are permitted, but the result must specify a single location.</span></span>

<span data-ttu-id="c6fa9-152">Чтобы переименовать перемещаемый элемент, укажите новое имя в значении параметра **Destination** .</span><span class="sxs-lookup"><span data-stu-id="c6fa9-152">To rename the item being moved, specify a new name in the value of the **Destination** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current directory
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="c6fa9-153">-Exclude</span><span class="sxs-lookup"><span data-stu-id="c6fa9-153">-Exclude</span></span>

<span data-ttu-id="c6fa9-154">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-154">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="c6fa9-155">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-155">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="c6fa9-156">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="c6fa9-156">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="c6fa9-157">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-157">Wildcard characters are permitted.</span></span> <span data-ttu-id="c6fa9-158">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-158">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="c6fa9-159">-Filter</span><span class="sxs-lookup"><span data-stu-id="c6fa9-159">-Filter</span></span>

<span data-ttu-id="c6fa9-160">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="c6fa9-160">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="c6fa9-161">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-161">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="c6fa9-162">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="c6fa9-162">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="c6fa9-163">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-163">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="c6fa9-164">-Force</span><span class="sxs-lookup"><span data-stu-id="c6fa9-164">-Force</span></span>

<span data-ttu-id="c6fa9-165">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-165">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="c6fa9-166">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-166">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="c6fa9-167">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="c6fa9-167">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="c6fa9-168">-Include</span><span class="sxs-lookup"><span data-stu-id="c6fa9-168">-Include</span></span>

<span data-ttu-id="c6fa9-169">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-169">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="c6fa9-170">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-170">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="c6fa9-171">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="c6fa9-171">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="c6fa9-172">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-172">Wildcard characters are permitted.</span></span> <span data-ttu-id="c6fa9-173">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-173">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="c6fa9-174">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="c6fa9-174">-LiteralPath</span></span>

<span data-ttu-id="c6fa9-175">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-175">Specifies a path to one or more locations.</span></span> <span data-ttu-id="c6fa9-176">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-176">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="c6fa9-177">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-177">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="c6fa9-178">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-178">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="c6fa9-179">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-179">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="c6fa9-180">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="c6fa9-180">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="c6fa9-181">-PassThru</span><span class="sxs-lookup"><span data-stu-id="c6fa9-181">-PassThru</span></span>

<span data-ttu-id="c6fa9-182">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-182">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="c6fa9-183">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-183">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="c6fa9-184">-Path</span><span class="sxs-lookup"><span data-stu-id="c6fa9-184">-Path</span></span>

<span data-ttu-id="c6fa9-185">Указывает путь к текущему расположению элементов.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-185">Specifies the path to the current location of the items.</span></span>
<span data-ttu-id="c6fa9-186">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-186">The default is the current directory.</span></span>
<span data-ttu-id="c6fa9-187">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-187">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: Current directory
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="c6fa9-188">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c6fa9-188">-Confirm</span></span>

<span data-ttu-id="c6fa9-189">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-189">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c6fa9-190">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c6fa9-190">-WhatIf</span></span>

<span data-ttu-id="c6fa9-191">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-191">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="c6fa9-192">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-192">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c6fa9-193">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="c6fa9-193">CommonParameters</span></span>

<span data-ttu-id="c6fa9-194">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="c6fa9-194">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="c6fa9-195">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="c6fa9-195">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="c6fa9-196">Входные данные</span><span class="sxs-lookup"><span data-stu-id="c6fa9-196">INPUTS</span></span>

### <span data-ttu-id="c6fa9-197">System.String</span><span class="sxs-lookup"><span data-stu-id="c6fa9-197">System.String</span></span>

<span data-ttu-id="c6fa9-198">В этот командлет можно передать по конвейеру строку, содержащую путь.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-198">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="c6fa9-199">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="c6fa9-199">OUTPUTS</span></span>

### <span data-ttu-id="c6fa9-200">Нет или объект, представляющий перемещенный элемент</span><span class="sxs-lookup"><span data-stu-id="c6fa9-200">None or an object representing the moved item</span></span>

<span data-ttu-id="c6fa9-201">При использовании параметра *PassThru* этот командлет создает объект, представляющий перемещенный элемент.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-201">When you use the *PassThru* parameter, this cmdlet generates an object representing the moved item.</span></span>
<span data-ttu-id="c6fa9-202">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-202">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="c6fa9-203">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="c6fa9-203">NOTES</span></span>

- <span data-ttu-id="c6fa9-204">Этот командлет переместит файлы между дисками, которые поддерживаются одним и тем же поставщиком, но переместит каталоги только в пределах одного диска.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-204">This cmdlet will move files between drives that are supported by the same provider, but it will move directories only within the same drive.</span></span>
- <span data-ttu-id="c6fa9-205">Поскольку `Move-Item` команда перемещает свойства, содержимое и дочерние элементы элемента, все перемещения по умолчанию являются рекурсивными.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-205">Because a `Move-Item` command moves the properties, contents, and child items of an item, all moves are recursive by default.</span></span>
- <span data-ttu-id="c6fa9-206">Этот командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-206">This cmdlet is designed to work with the data exposed by any provider.</span></span>
  <span data-ttu-id="c6fa9-207">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="c6fa9-207">To list the providers available in your session, type `Get-PSProvider`.</span></span>
  <span data-ttu-id="c6fa9-208">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="c6fa9-208">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="c6fa9-209">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="c6fa9-209">RELATED LINKS</span></span>

[<span data-ttu-id="c6fa9-210">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="c6fa9-210">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="c6fa9-211">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="c6fa9-211">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="c6fa9-212">Get-Item</span><span class="sxs-lookup"><span data-stu-id="c6fa9-212">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="c6fa9-213">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="c6fa9-213">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="c6fa9-214">New-Item</span><span class="sxs-lookup"><span data-stu-id="c6fa9-214">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="c6fa9-215">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="c6fa9-215">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="c6fa9-216">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="c6fa9-216">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="c6fa9-217">Set-Item</span><span class="sxs-lookup"><span data-stu-id="c6fa9-217">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="c6fa9-218">about_Providers</span><span class="sxs-lookup"><span data-stu-id="c6fa9-218">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

