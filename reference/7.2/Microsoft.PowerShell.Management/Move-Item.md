---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/move-item?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Move-Item
ms.openlocfilehash: a47c017371fe5fe87618c11551cd1ecba76d5c60
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605549"
---
# <span data-ttu-id="e1d5c-102">Move-Item</span><span class="sxs-lookup"><span data-stu-id="e1d5c-102">Move-Item</span></span>

## <span data-ttu-id="e1d5c-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e1d5c-103">SYNOPSIS</span></span>
<span data-ttu-id="e1d5c-104">Перемещает элемент из одного расположения в другое.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-104">Moves an item from one location to another.</span></span>

## <span data-ttu-id="e1d5c-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e1d5c-105">SYNTAX</span></span>

### <span data-ttu-id="e1d5c-106">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="e1d5c-106">Path (Default)</span></span>

```
Move-Item [-Path] <String[]> [[-Destination] <String>] [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-PassThru] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e1d5c-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="e1d5c-107">LiteralPath</span></span>

```
Move-Item -LiteralPath <String[]> [[-Destination] <String>] [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-PassThru] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e1d5c-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e1d5c-108">DESCRIPTION</span></span>

<span data-ttu-id="e1d5c-109">`Move-Item`Командлет перемещает элемент, включая его свойства, содержимое и дочерние элементы, из одного расположения в другое.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-109">The `Move-Item` cmdlet moves an item, including its properties, contents, and child items, from one location to another location.</span></span> <span data-ttu-id="e1d5c-110">Оба расположения должны поддерживаться одним и тем же поставщиком.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-110">The locations must be supported by the same provider.</span></span>
<span data-ttu-id="e1d5c-111">Например, файл или вложенный каталог можно переместить из одного каталога в другой, а подраздел реестра — из одного раздела в другой.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-111">For example, it can move a file or subdirectory from one directory to another or move a registry subkey from one key to another.</span></span>
<span data-ttu-id="e1d5c-112">При перемещении элемент удаляется в исходном расположении и создается в новом.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-112">When you move an item, it is added to the new location and deleted from its original location.</span></span>

## <span data-ttu-id="e1d5c-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="e1d5c-113">EXAMPLES</span></span>

### <span data-ttu-id="e1d5c-114">Пример 1. Перемещение файла в другой каталог и его переименование</span><span class="sxs-lookup"><span data-stu-id="e1d5c-114">Example 1: Move a file to another directory and rename it</span></span>

<span data-ttu-id="e1d5c-115">Эта команда перемещает `Test.txt` файл с `C:` диска в `E:\Temp` каталог и переименовывает его с `test.txt` на `tst.txt` .</span><span class="sxs-lookup"><span data-stu-id="e1d5c-115">This command moves the `Test.txt` file from the `C:` drive to the `E:\Temp` directory and renames it from `test.txt` to `tst.txt`.</span></span>

```powershell
Move-Item -Path C:\test.txt -Destination E:\Temp\tst.txt
```

### <span data-ttu-id="e1d5c-116">Пример 2. Перемещение каталога и его содержимого в другой каталог</span><span class="sxs-lookup"><span data-stu-id="e1d5c-116">Example 2: Move a directory and its contents to another directory</span></span>

<span data-ttu-id="e1d5c-117">Эта команда перемещает `C:\Temp` каталог и его содержимое в `C:\Logs` каталог.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-117">This command moves the `C:\Temp` directory and its contents to the `C:\Logs` directory.</span></span>
<span data-ttu-id="e1d5c-118">Каталог "Temp" и все его подкаталоги и файлы появятся в каталоге "Logs".</span><span class="sxs-lookup"><span data-stu-id="e1d5c-118">The "Temp" directory, and all of its subdirectories and files, then appear in the "Logs" directory.</span></span>

```powershell
Move-Item -Path C:\Temp -Destination C:\Logs
```

### <span data-ttu-id="e1d5c-119">Пример 3. Перемещение всех файлов указанного расширения из текущего каталога в другой каталог</span><span class="sxs-lookup"><span data-stu-id="e1d5c-119">Example 3: Move all files of a specified extension from the current directory to another directory</span></span>

<span data-ttu-id="e1d5c-120">Эта команда перемещает все текстовые файлы ( `*.txt` ) в текущем каталоге (представленные точкой ( `.` )) в `C:\Logs` каталог.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-120">This command moves all of the text files (`*.txt`) in the current directory (represented by a dot (`.`)) to the `C:\Logs` directory.</span></span>

```powershell
Move-Item -Path .\*.txt -Destination C:\Logs
```

### <span data-ttu-id="e1d5c-121">Пример 4. рекурсивное перемещение всех файлов указанного расширения из текущего каталога в другой каталог</span><span class="sxs-lookup"><span data-stu-id="e1d5c-121">Example 4: Recursively move all files of a specified extension from the current directory to another directory</span></span>

<span data-ttu-id="e1d5c-122">Эта команда рекурсивно перемещает все текстовые файлы из текущего каталога и всех подкаталогов в каталог "К:\текстфилес".</span><span class="sxs-lookup"><span data-stu-id="e1d5c-122">This command moves all of the text files from the current directory and all subdirectories, recursively, to the "C:\TextFiles" directory.</span></span>

```powershell
Get-ChildItem -Path ".\*.txt" -Recurse | Move-Item -Destination "C:\TextFiles"
```

<span data-ttu-id="e1d5c-123">Команда использует командлет, `Get-ChildItem` чтобы получить все дочерние элементы в текущем каталоге (представленном точкой \[ \] ) и его подкаталогах с *расширением txt. Он использует параметр  рекурсии, чтобы получить рекурсивные значения и параметр Include, чтобы ограничить извлечение* файлами. txt.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-123">The command uses the `Get-ChildItem` cmdlet to get all of the child items in the current directory (represented by the dot \[.\]) and its subdirectories that have a "*.txt" file name extension. It uses the **Recurse** parameter to make the retrieval recursive and the Include parameter to limit the retrieval to "*.txt" files.</span></span>

<span data-ttu-id="e1d5c-124">Оператор конвейера ( `|` ) отправляет результаты этой команды в `Move-Item` , который перемещает текстовые файлы в каталог "Textfiles".</span><span class="sxs-lookup"><span data-stu-id="e1d5c-124">The pipeline operator (`|`) sends the results of this command to `Move-Item`, which moves the text files to the "TextFiles" directory.</span></span>

<span data-ttu-id="e1d5c-125">Если файлы, которые нужно переместить в "К:\текстфилес", имеют одинаковое имя, `Move-Item` выводит сообщение об ошибке и продолжается, но перемещает только один файл с каждым именем в "к:\текстфилес".</span><span class="sxs-lookup"><span data-stu-id="e1d5c-125">If files that are to be moved to "C:\Textfiles" have the same name, `Move-Item` displays an error and continues, but it moves only one file with each name to "C:\Textfiles".</span></span>
<span data-ttu-id="e1d5c-126">Другие файлы остаются в исходных каталогах.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-126">The other files remain in their original directories.</span></span>

<span data-ttu-id="e1d5c-127">Если каталог "Textfiles" (или любой другой элемент конечного пути) не существует, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-127">If the "Textfiles" directory (or any other element of the destination path) does not exist, the command fails.</span></span>
<span data-ttu-id="e1d5c-128">Отсутствующий каталог не создается, даже если используется параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="e1d5c-128">The missing directory is not created for you, even if you use the **Force** parameter.</span></span>
<span data-ttu-id="e1d5c-129">`Move-Item` перемещает первый элемент в файл с именем «Textfiles», а затем выводит сообщение об ошибке, объясняющее, что файл уже существует.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-129">`Move-Item` moves the first item to a file called "Textfiles" and then displays an error explaining that the file already exists.</span></span>

<span data-ttu-id="e1d5c-130">Кроме того, по умолчанию не `Get-ChildItem` перемещает скрытые файлы.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-130">Also, by default, `Get-ChildItem` does not move hidden files.</span></span>
<span data-ttu-id="e1d5c-131">Чтобы переместить скрытые файлы, используйте параметр **Force** с `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="e1d5c-131">To move hidden files, use the **Force** parameter with `Get-ChildItem`.</span></span>

> [!NOTE]
> <span data-ttu-id="e1d5c-132">В Windows PowerShell 2,0 при использовании параметра **рекурсии** `Get-ChildItem` командлета значение параметра **path** должно быть контейнером.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-132">In Windows PowerShell 2.0, when using the **Recurse** parameter of the `Get-ChildItem` cmdlet, the value of the **Path** parameter must be a container.</span></span>
> <span data-ttu-id="e1d5c-133">Используйте параметр **include** , чтобы указать txt-файл для расширения имени файла ( `Get-ChildItem -Path .\* -Include *.txt -Recurse | Move-Item -Destination C:\TextFiles` ).</span><span class="sxs-lookup"><span data-stu-id="e1d5c-133">Use the **Include** parameter to specify the .txt file name extension filter (`Get-ChildItem -Path .\* -Include *.txt -Recurse | Move-Item -Destination C:\TextFiles`).</span></span>

### <span data-ttu-id="e1d5c-134">Пример 5. перемещение разделов и значений реестра в другой раздел</span><span class="sxs-lookup"><span data-stu-id="e1d5c-134">Example 5: Move registry keys and values to another key</span></span>

<span data-ttu-id="e1d5c-135">Эта команда перемещает разделы и значения реестра, содержащиеся в разделе реестра MyCompany, в `HKLM\Software` раздел "миневкомпани".</span><span class="sxs-lookup"><span data-stu-id="e1d5c-135">This command moves the registry keys and values within the "MyCompany" registry key in `HKLM\Software` to the "MyNewCompany" key.</span></span>
<span data-ttu-id="e1d5c-136">Символ-шаблон ( `*` ) указывает, что необходимо переместить содержимое ключа MyCompany, а не сам ключ.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-136">The wildcard character (`*`) indicates that the contents of the "MyCompany" key should be moved, not the key itself.</span></span>
<span data-ttu-id="e1d5c-137">В этой команде необязательные имена параметров **path** и **Destination** опускаются.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-137">In this command, the optional **Path** and **Destination** parameter names are omitted.</span></span>

```powershell
Move-Item "HKLM:\software\mycompany\*" "HKLM:\software\mynewcompany"
```

### <span data-ttu-id="e1d5c-138">Пример 6. Перемещение каталога и его содержимого в подкаталог указанного каталога</span><span class="sxs-lookup"><span data-stu-id="e1d5c-138">Example 6: Move a directory and its contents to a subdirectory of the specified directory</span></span>

<span data-ttu-id="e1d5c-139">Эта команда перемещает каталог " \[ logs \` 2006 \] " (и его содержимое) в каталог "Logs \[ 2006 \] ".</span><span class="sxs-lookup"><span data-stu-id="e1d5c-139">This command moves the "Logs\[Sept\`06\]" directory (and its contents) into the "Logs\[2006\]" directory.</span></span>

```powershell
Move-Item -LiteralPath 'Logs[Sept`06]' -Destination 'Logs[2006]'
```

<span data-ttu-id="e1d5c-140">Параметр **LiteralPath** используется вместо **path**, так как имя исходного каталога включает открывающую и закрывающую квадратные скобки (" \[ " и " \] ").</span><span class="sxs-lookup"><span data-stu-id="e1d5c-140">The **LiteralPath** parameter is used instead of **Path**, because the original directory name includes left bracket and right bracket characters ("\[" and "\]").</span></span>
<span data-ttu-id="e1d5c-141">Путь также заключается в одинарные кавычки (' '), поэтому символ обратного апострофа ( \` ) не интерпретируется правильно.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-141">The path is also enclosed in single quotation marks (' '), so that the backtick symbol (\`) is not misinterpreted.</span></span>

<span data-ttu-id="e1d5c-142">Параметру **назначения** не требуется путь к литералу, так как переменная назначения также должна быть заключена в одинарные кавычки, так как она содержит скобки, которые могут быть неверно интерпретированы.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-142">The **Destination** parameter does not require a literal path, because the Destination variable also must be enclosed in single quotation marks, because it includes brackets that can be misinterpreted.</span></span>

## <span data-ttu-id="e1d5c-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e1d5c-143">PARAMETERS</span></span>

### <span data-ttu-id="e1d5c-144">-Credential</span><span class="sxs-lookup"><span data-stu-id="e1d5c-144">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="e1d5c-145">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-145">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="e1d5c-146">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="e1d5c-146">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="e1d5c-147">-Destination</span><span class="sxs-lookup"><span data-stu-id="e1d5c-147">-Destination</span></span>

<span data-ttu-id="e1d5c-148">Указывает путь к новому расположению элементов.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-148">Specifies the path to the location where the items are being moved.</span></span>
<span data-ttu-id="e1d5c-149">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-149">The default is the current directory.</span></span>
<span data-ttu-id="e1d5c-150">Знаки подстановки использовать можно, но в результате должно быть задано только одно расположение.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-150">Wildcards are permitted, but the result must specify a single location.</span></span>

<span data-ttu-id="e1d5c-151">Чтобы переименовать перемещаемый элемент, укажите новое имя в значении параметра **Destination** .</span><span class="sxs-lookup"><span data-stu-id="e1d5c-151">To rename the item being moved, specify a new name in the value of the **Destination** parameter.</span></span>

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

### <span data-ttu-id="e1d5c-152">-Exclude</span><span class="sxs-lookup"><span data-stu-id="e1d5c-152">-Exclude</span></span>

<span data-ttu-id="e1d5c-153">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-153">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="e1d5c-154">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-154">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="e1d5c-155">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="e1d5c-155">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="e1d5c-156">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-156">Wildcard characters are permitted.</span></span> <span data-ttu-id="e1d5c-157">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-157">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="e1d5c-158">-Filter</span><span class="sxs-lookup"><span data-stu-id="e1d5c-158">-Filter</span></span>

<span data-ttu-id="e1d5c-159">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="e1d5c-159">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="e1d5c-160">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-160">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="e1d5c-161">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="e1d5c-161">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="e1d5c-162">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-162">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="e1d5c-163">-Force</span><span class="sxs-lookup"><span data-stu-id="e1d5c-163">-Force</span></span>

<span data-ttu-id="e1d5c-164">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-164">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="e1d5c-165">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-165">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="e1d5c-166">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="e1d5c-166">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="e1d5c-167">-Include</span><span class="sxs-lookup"><span data-stu-id="e1d5c-167">-Include</span></span>

<span data-ttu-id="e1d5c-168">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-168">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="e1d5c-169">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-169">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="e1d5c-170">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="e1d5c-170">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="e1d5c-171">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-171">Wildcard characters are permitted.</span></span> <span data-ttu-id="e1d5c-172">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-172">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="e1d5c-173">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="e1d5c-173">-LiteralPath</span></span>

<span data-ttu-id="e1d5c-174">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-174">Specifies a path to one or more locations.</span></span> <span data-ttu-id="e1d5c-175">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-175">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="e1d5c-176">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-176">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="e1d5c-177">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-177">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="e1d5c-178">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-178">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="e1d5c-179">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="e1d5c-179">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="e1d5c-180">-PassThru</span><span class="sxs-lookup"><span data-stu-id="e1d5c-180">-PassThru</span></span>

<span data-ttu-id="e1d5c-181">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-181">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="e1d5c-182">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-182">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="e1d5c-183">-Path</span><span class="sxs-lookup"><span data-stu-id="e1d5c-183">-Path</span></span>

<span data-ttu-id="e1d5c-184">Указывает путь к текущему расположению элементов.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-184">Specifies the path to the current location of the items.</span></span>
<span data-ttu-id="e1d5c-185">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-185">The default is the current directory.</span></span>
<span data-ttu-id="e1d5c-186">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-186">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="e1d5c-187">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e1d5c-187">-Confirm</span></span>

<span data-ttu-id="e1d5c-188">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-188">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e1d5c-189">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e1d5c-189">-WhatIf</span></span>

<span data-ttu-id="e1d5c-190">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-190">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="e1d5c-191">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-191">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e1d5c-192">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e1d5c-192">CommonParameters</span></span>

<span data-ttu-id="e1d5c-193">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="e1d5c-193">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="e1d5c-194">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="e1d5c-194">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="e1d5c-195">Входные данные</span><span class="sxs-lookup"><span data-stu-id="e1d5c-195">INPUTS</span></span>

### <span data-ttu-id="e1d5c-196">System.String</span><span class="sxs-lookup"><span data-stu-id="e1d5c-196">System.String</span></span>

<span data-ttu-id="e1d5c-197">В этот командлет можно передать по конвейеру строку, содержащую путь.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-197">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="e1d5c-198">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="e1d5c-198">OUTPUTS</span></span>

### <span data-ttu-id="e1d5c-199">Нет или объект, представляющий перемещенный элемент</span><span class="sxs-lookup"><span data-stu-id="e1d5c-199">None or an object representing the moved item</span></span>

<span data-ttu-id="e1d5c-200">При использовании параметра *PassThru* этот командлет создает объект, представляющий перемещенный элемент.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-200">When you use the *PassThru* parameter, this cmdlet generates an object representing the moved item.</span></span>
<span data-ttu-id="e1d5c-201">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-201">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="e1d5c-202">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="e1d5c-202">NOTES</span></span>

- <span data-ttu-id="e1d5c-203">Этот командлет переместит файлы между дисками, которые поддерживаются одним и тем же поставщиком, но переместит каталоги только в пределах одного диска.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-203">This cmdlet will move files between drives that are supported by the same provider, but it will move directories only within the same drive.</span></span>
- <span data-ttu-id="e1d5c-204">Поскольку `Move-Item` команда перемещает свойства, содержимое и дочерние элементы элемента, все перемещения по умолчанию являются рекурсивными.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-204">Because a `Move-Item` command moves the properties, contents, and child items of an item, all moves are recursive by default.</span></span>
- <span data-ttu-id="e1d5c-205">Этот командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-205">This cmdlet is designed to work with the data exposed by any provider.</span></span>
  <span data-ttu-id="e1d5c-206">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="e1d5c-206">To list the providers available in your session, type `Get-PSProvider`.</span></span>
  <span data-ttu-id="e1d5c-207">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="e1d5c-207">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="e1d5c-208">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="e1d5c-208">RELATED LINKS</span></span>

[<span data-ttu-id="e1d5c-209">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="e1d5c-209">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="e1d5c-210">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="e1d5c-210">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="e1d5c-211">Get-Item</span><span class="sxs-lookup"><span data-stu-id="e1d5c-211">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="e1d5c-212">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="e1d5c-212">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="e1d5c-213">New-Item</span><span class="sxs-lookup"><span data-stu-id="e1d5c-213">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="e1d5c-214">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="e1d5c-214">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="e1d5c-215">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="e1d5c-215">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="e1d5c-216">Set-Item</span><span class="sxs-lookup"><span data-stu-id="e1d5c-216">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="e1d5c-217">about_Providers</span><span class="sxs-lookup"><span data-stu-id="e1d5c-217">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

