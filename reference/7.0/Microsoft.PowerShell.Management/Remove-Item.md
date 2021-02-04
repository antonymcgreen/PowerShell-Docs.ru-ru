---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-item?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Item
ms.openlocfilehash: 9b8d81c84a5dab8fa5f5e216c8c4eb5b5f6022b7
ms.sourcegitcommit: bf07cffb2a66dec94bf3576e197090f958701f18
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2020
ms.locfileid: "97692857"
---
# <span data-ttu-id="73d01-102">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="73d01-102">Remove-Item</span></span>

## <span data-ttu-id="73d01-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="73d01-103">SYNOPSIS</span></span>
<span data-ttu-id="73d01-104">Удаляет указанные элементы.</span><span class="sxs-lookup"><span data-stu-id="73d01-104">Deletes the specified items.</span></span>

## <span data-ttu-id="73d01-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="73d01-105">SYNTAX</span></span>

### <span data-ttu-id="73d01-106">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="73d01-106">Path (Default)</span></span>

```
Remove-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Recurse] [-Force] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="73d01-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="73d01-107">LiteralPath</span></span>

```
Remove-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Recurse] [-Force] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="73d01-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="73d01-108">DESCRIPTION</span></span>

<span data-ttu-id="73d01-109">`Remove-Item`Командлет удаляет один или несколько элементов.</span><span class="sxs-lookup"><span data-stu-id="73d01-109">The `Remove-Item` cmdlet deletes one or more items.</span></span> <span data-ttu-id="73d01-110">Так как он поддерживается многими поставщиками, он может удалять множество различных типов элементов, включая файлы, папки, разделы реестра, переменные, псевдонимы и функции.</span><span class="sxs-lookup"><span data-stu-id="73d01-110">Because it is supported by many providers, it can delete many different types of items, including files, folders, registry keys, variables, aliases, and functions.</span></span>

## <span data-ttu-id="73d01-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="73d01-111">EXAMPLES</span></span>

### <span data-ttu-id="73d01-112">Пример 1. Удаление файлов, имеющих любое расширение имени файла</span><span class="sxs-lookup"><span data-stu-id="73d01-112">Example 1: Delete files that have any file name extension</span></span>

<span data-ttu-id="73d01-113">В этом примере из папки удаляются все файлы, имена которых содержат точку ( `.` ) `C:\Test` .</span><span class="sxs-lookup"><span data-stu-id="73d01-113">This example deletes all of the files that have names that include a dot (`.`) from the `C:\Test` folder.</span></span> <span data-ttu-id="73d01-114">Поскольку команда задает точку, команда не удаляет папки или файлы, не имеющие расширения имени файла.</span><span class="sxs-lookup"><span data-stu-id="73d01-114">Because the command specifies a dot, the command does not delete folders or files that have no file name extension.</span></span>

```powershell
Remove-Item C:\Test\*.*
```

### <span data-ttu-id="73d01-115">Пример 2. Удаление некоторых файлов документов в папке</span><span class="sxs-lookup"><span data-stu-id="73d01-115">Example 2: Delete some of the document files in a folder</span></span>

<span data-ttu-id="73d01-116">В этом примере удаляется из текущей папки все файлы, имеющие `.doc` расширение имени файла, и имя, которое не включает `*1*` .</span><span class="sxs-lookup"><span data-stu-id="73d01-116">This example deletes from the current folder all files that have a `.doc` file name extension and a name that does not include `*1*`.</span></span>

```powershell
Remove-Item * -Include *.doc -Exclude *1*
```

<span data-ttu-id="73d01-117">`*`Для указания содержимого текущей папки используется подстановочный знак ().</span><span class="sxs-lookup"><span data-stu-id="73d01-117">It uses the wildcard character (`*`) to specify the contents of the current folder.</span></span> <span data-ttu-id="73d01-118">Для указания удаляемых файлов используются параметры **include** и **Exclude** .</span><span class="sxs-lookup"><span data-stu-id="73d01-118">It uses the **Include** and **Exclude** parameters to specify the files to delete.</span></span>

### <span data-ttu-id="73d01-119">Пример 3. Удаление скрытых файлов, доступ только для чтения</span><span class="sxs-lookup"><span data-stu-id="73d01-119">Example 3: Delete hidden, read-only files</span></span>

<span data-ttu-id="73d01-120">Эта команда удаляет файл, который как *скрытый* , так и *только для чтения*.</span><span class="sxs-lookup"><span data-stu-id="73d01-120">This command deletes a file that is both *hidden* and *read-only*.</span></span>

```powershell
Remove-Item -Path C:\Test\hidden-RO-file.txt -Force
```

<span data-ttu-id="73d01-121">Для указания файла используется параметр **path** .</span><span class="sxs-lookup"><span data-stu-id="73d01-121">It uses the **Path** parameter to specify the file.</span></span> <span data-ttu-id="73d01-122">Для его удаления используется параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="73d01-122">It uses the **Force** parameter to delete it.</span></span> <span data-ttu-id="73d01-123">Без **принудительного** использования нельзя удалять файлы, которые _доступны только для чтения_ или _скрыты_ .</span><span class="sxs-lookup"><span data-stu-id="73d01-123">Without **Force**, you cannot delete _read-only_ or _hidden_ files.</span></span>

### <span data-ttu-id="73d01-124">Пример 4. рекурсивное удаление файлов во вложенных папках</span><span class="sxs-lookup"><span data-stu-id="73d01-124">Example 4: Delete files in subfolders recursively</span></span>

<span data-ttu-id="73d01-125">Эта команда рекурсивно удаляет все CSV-файлы в текущей папке и во всех вложенных папках.</span><span class="sxs-lookup"><span data-stu-id="73d01-125">This command deletes all of the CSV files in the current folder and all subfolders recursively.</span></span>

<span data-ttu-id="73d01-126">Поскольку **рекурсивный** параметр в `Remove-Item` имеет известную ошибку, команда в этом примере использует `Get-ChildItem` для получения нужных файлов, а затем использует оператор конвейера для передачи их в `Remove-Item` .</span><span class="sxs-lookup"><span data-stu-id="73d01-126">Because the **Recurse** parameter in `Remove-Item` has a known issue, the command in this example uses `Get-ChildItem` to get the desired files, and then uses the pipeline operator to pass them to `Remove-Item`.</span></span>

```powershell
Get-ChildItem * -Include *.csv -Recurse | Remove-Item
```

<span data-ttu-id="73d01-127">В `Get-ChildItem` команде **path** имеет значение ( `*` ), которое представляет содержимое текущей папки.</span><span class="sxs-lookup"><span data-stu-id="73d01-127">In the `Get-ChildItem` command, **Path** has a value of (`*`), which represents the contents of the current folder.</span></span> <span data-ttu-id="73d01-128">Он использует параметр **include** для указания типа CSV-файла и использует рекурсию, чтобы сделать **возможной** рекурсивный выбор.</span><span class="sxs-lookup"><span data-stu-id="73d01-128">It uses **Include** to specify the CSV file type, and it uses **Recurse** to make the retrieval recursive.</span></span> <span data-ttu-id="73d01-129">При попытке указать тип файла путь, например `-Path *.csv` , командлет интерпретирует тему поиска как файл, не имеющий дочерних элементов, и **рекурсия** завершается сбоем.</span><span class="sxs-lookup"><span data-stu-id="73d01-129">If you try to specify the file type the path, such as `-Path *.csv`, the cmdlet interprets the subject of the search to be a file that has no child items, and **Recurse** fails.</span></span>

### <span data-ttu-id="73d01-130">Пример 5. рекурсивное удаление подразделов</span><span class="sxs-lookup"><span data-stu-id="73d01-130">Example 5: Delete subkeys recursively</span></span>

<span data-ttu-id="73d01-131">Эта команда удаляет раздел реестра "Олдапп" и все его подразделы и значения.</span><span class="sxs-lookup"><span data-stu-id="73d01-131">This command deletes the "OldApp" registry key and all its subkeys and values.</span></span> <span data-ttu-id="73d01-132">Он использует `Remove-Item` для удаления ключа.</span><span class="sxs-lookup"><span data-stu-id="73d01-132">It uses `Remove-Item` to remove the key.</span></span> <span data-ttu-id="73d01-133">Путь указан, но необязательное имя параметра (**путь**) пропущено.</span><span class="sxs-lookup"><span data-stu-id="73d01-133">The path is specified, but the optional parameter name (**Path**) is omitted.</span></span>

<span data-ttu-id="73d01-134">**Рекурсивный параметр удаляет** все содержимое ключа "олдапп" рекурсивно.</span><span class="sxs-lookup"><span data-stu-id="73d01-134">The **Recurse** parameter deletes all of the contents of the "OldApp" key recursively.</span></span> <span data-ttu-id="73d01-135">Если ключ содержит подразделы и не указан параметр **рекурсии** , вам будет предложено подтвердить удаление содержимого ключа.</span><span class="sxs-lookup"><span data-stu-id="73d01-135">If the key contains subkeys and you omit the **Recurse** parameter, you are prompted to confirm that you want to delete the contents of the key.</span></span>

```powershell
Remove-Item HKLM:\Software\MyCompany\OldApp -Recurse
```

### <span data-ttu-id="73d01-136">Пример 6. Удаление файлов со специальными символами</span><span class="sxs-lookup"><span data-stu-id="73d01-136">Example 6: Deleting files with special characters</span></span>

<span data-ttu-id="73d01-137">В следующем примере показано, как удалить файлы, содержащие специальные символы, такие как квадратные скобки или круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="73d01-137">The following example shows how to delete files that contain special characters like brackets or parentheses.</span></span>

```powershell
Get-ChildItem
```

```Output
    Directory: C:\temp\Downloads

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a---          6/1/2018  12:19 PM           1362 myFile.txt
-a---          6/1/2018  12:30 PM           1132 myFile[1].txt
-a---          6/1/2018  12:19 PM           1283 myFile[2].txt
-a---          6/1/2018  12:19 PM           1432 myFile[3].txt

```

```powershell
Get-ChildItem | Where-Object Name -Like '*`[*'
```

```Output
    Directory: C:\temp\Downloads

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a---          6/1/2018  12:30 PM           1132 myFile[1].txt
-a---          6/1/2018  12:19 PM           1283 myFile[2].txt
-a---          6/1/2018  12:19 PM           1432 myFile[3].txt

```

```powershell
Get-ChildItem | Where-Object Name -Like '*`[*' | ForEach-Object { Remove-Item -LiteralPath $_.Name }
Get-ChildItem
```

```Output
    Directory: C:\temp\Downloads

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a---          6/1/2018  12:19 PM           1362 myFile.txt
```

### <span data-ttu-id="73d01-138">Пример 7. Удаление альтернативного потока данных</span><span class="sxs-lookup"><span data-stu-id="73d01-138">Example 7: Remove an alternate data stream</span></span>

<span data-ttu-id="73d01-139">В этом примере показано, как использовать динамический параметр **Stream** `Remove-Item` командлета для удаления альтернативного потока данных.</span><span class="sxs-lookup"><span data-stu-id="73d01-139">This example shows how to use the **Stream** dynamic parameter of the `Remove-Item` cmdlet to delete an alternate data stream.</span></span> <span data-ttu-id="73d01-140">Параметр Stream появился в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="73d01-140">The stream parameter is introduced in Windows PowerShell 3.0.</span></span>

```powershell
Get-Item C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
```

```Output
   FileName: \\C:\Test\Copy-Script.ps1

Stream                   Length
------                   ------
Zone.Identifier              26

```

```powershell
Remove-Item C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
Get-Item C:\Test\Copy-Script.ps1 -Stream Zone.Identifier
```

```Output
Get-Item : Could not open alternate data stream 'Zone.Identifier' of file 'C:\Test\Copy-Script.ps1'.
At line:1 char:1
+ Get-Item 'C:\Test\Copy-Script.ps1' -Stream Zone.Identifier
+ [!INCLUDE[]()][!INCLUDE[]()][!INCLUDE[]()][!INCLUDE[]()][!INCLUDE[]()]~~
    + CategoryInfo          : ObjectNotFound: (C:\Test\Copy-Script.ps1:String) [Get-Item], FileNotFoundE
   xception
    + FullyQualifiedErrorId : AlternateDataStreamNotFound,Microsoft.PowerShell.Commands.GetItemCommand

```

<span data-ttu-id="73d01-141">Параметр **Stream** `Get-Item` получает `Zone.Identifier` поток `Copy-Script.ps1` файла.</span><span class="sxs-lookup"><span data-stu-id="73d01-141">The **Stream** parameter `Get-Item` gets the `Zone.Identifier` stream of the `Copy-Script.ps1` file.</span></span> <span data-ttu-id="73d01-142">`Remove-Item` использует параметр **Stream** для удаления `Zone.Identifier` потока файла.</span><span class="sxs-lookup"><span data-stu-id="73d01-142">`Remove-Item` uses the **Stream** parameter to remove the `Zone.Identifier` stream of the file.</span></span> <span data-ttu-id="73d01-143">Наконец, `Get-Item` командлет показывает, что `Zone.Identifier` поток удален.</span><span class="sxs-lookup"><span data-stu-id="73d01-143">Finally, the `Get-Item` cmdlet shows that the `Zone.Identifier` stream was deleted.</span></span>

## <span data-ttu-id="73d01-144">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="73d01-144">PARAMETERS</span></span>

### <span data-ttu-id="73d01-145">-Credential</span><span class="sxs-lookup"><span data-stu-id="73d01-145">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="73d01-146">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="73d01-146">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="73d01-147">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="73d01-147">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="73d01-148">-Exclude</span><span class="sxs-lookup"><span data-stu-id="73d01-148">-Exclude</span></span>

<span data-ttu-id="73d01-149">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="73d01-149">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="73d01-150">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="73d01-150">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="73d01-151">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="73d01-151">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="73d01-152">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="73d01-152">Wildcard characters are permitted.</span></span> <span data-ttu-id="73d01-153">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="73d01-153">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="73d01-154">-Filter</span><span class="sxs-lookup"><span data-stu-id="73d01-154">-Filter</span></span>

<span data-ttu-id="73d01-155">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="73d01-155">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="73d01-156">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="73d01-156">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="73d01-157">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="73d01-157">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span> <span data-ttu-id="73d01-158">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="73d01-158">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="73d01-159">-Force</span><span class="sxs-lookup"><span data-stu-id="73d01-159">-Force</span></span>

<span data-ttu-id="73d01-160">Заставляет командлет удалять элементы, которые в противном случае не могут быть изменены, например скрытые или только для чтения, а также псевдонимы или переменные только для чтения.</span><span class="sxs-lookup"><span data-stu-id="73d01-160">Forces the cmdlet to remove items that cannot otherwise be changed, such as hidden or read-only files or read-only aliases or variables.</span></span> <span data-ttu-id="73d01-161">С помощью этого командлета нельзя удалять постоянные псевдонимы или переменные.</span><span class="sxs-lookup"><span data-stu-id="73d01-161">The cmdlet cannot remove constant aliases or variables.</span></span>
<span data-ttu-id="73d01-162">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="73d01-162">Implementation varies from provider to provider.</span></span> <span data-ttu-id="73d01-163">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="73d01-163">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span> <span data-ttu-id="73d01-164">Даже при использовании параметра **Force** командлет не может переопределять ограничения безопасности.</span><span class="sxs-lookup"><span data-stu-id="73d01-164">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

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

### <span data-ttu-id="73d01-165">-Include</span><span class="sxs-lookup"><span data-stu-id="73d01-165">-Include</span></span>

<span data-ttu-id="73d01-166">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="73d01-166">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="73d01-167">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="73d01-167">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="73d01-168">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="73d01-168">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="73d01-169">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="73d01-169">Wildcard characters are permitted.</span></span> <span data-ttu-id="73d01-170">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="73d01-170">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="73d01-171">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="73d01-171">-LiteralPath</span></span>

<span data-ttu-id="73d01-172">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="73d01-172">Specifies a path to one or more locations.</span></span> <span data-ttu-id="73d01-173">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="73d01-173">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="73d01-174">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="73d01-174">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="73d01-175">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="73d01-175">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="73d01-176">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="73d01-176">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="73d01-177">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="73d01-177">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="73d01-178">-Path</span><span class="sxs-lookup"><span data-stu-id="73d01-178">-Path</span></span>

<span data-ttu-id="73d01-179">Указывает путь удаляемых элементов.</span><span class="sxs-lookup"><span data-stu-id="73d01-179">Specifies a path of the items being removed.</span></span>
<span data-ttu-id="73d01-180">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="73d01-180">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="73d01-181">-Recurse</span><span class="sxs-lookup"><span data-stu-id="73d01-181">-Recurse</span></span>

<span data-ttu-id="73d01-182">Указывает, что этот командлет удаляет элементы в указанных расположениях и во всех дочерних элементах расположений.</span><span class="sxs-lookup"><span data-stu-id="73d01-182">Indicates that this cmdlet deletes the items in the specified locations and in all child items of the locations.</span></span>

<span data-ttu-id="73d01-183">При использовании с параметром **include** **рекурсивный** параметр может не удалить все вложенные папки или все дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="73d01-183">When it is used with the **Include** parameter, the **Recurse** parameter might not delete all subfolders or all child items.</span></span> <span data-ttu-id="73d01-184">Это известная проблема.</span><span class="sxs-lookup"><span data-stu-id="73d01-184">This is a known issue.</span></span> <span data-ttu-id="73d01-185">В качестве обходного решения попробуйте выполнить конвейерную `Get-ChildItem -Recurse` команду `Remove-Item` , как описано в примере 4 в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="73d01-185">As a workaround, try piping results of the `Get-ChildItem -Recurse` command to `Remove-Item`, as described in "Example 4" in this topic.</span></span>

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

### <span data-ttu-id="73d01-186">-Stream</span><span class="sxs-lookup"><span data-stu-id="73d01-186">-Stream</span></span>

> [!NOTE]
> <span data-ttu-id="73d01-187">Этот параметр доступен только в Windows.</span><span class="sxs-lookup"><span data-stu-id="73d01-187">This Parameter is only available on Windows.</span></span>

<span data-ttu-id="73d01-188">Параметр **потока** — это динамический параметр, к которому добавляется поставщик FileSystem `Remove-Item` .</span><span class="sxs-lookup"><span data-stu-id="73d01-188">The **Stream** parameter is a dynamic parameter that the FileSystem provider adds to `Remove-Item`.</span></span>
<span data-ttu-id="73d01-189">Этот параметр работает только на дисках с файловой системой.</span><span class="sxs-lookup"><span data-stu-id="73d01-189">This parameter works only in file system drives.</span></span>

<span data-ttu-id="73d01-190">Можно использовать `Remove-Item` для удаления альтернативного потока данных, например `Zone.Identifier` .</span><span class="sxs-lookup"><span data-stu-id="73d01-190">You can use `Remove-Item` to delete an alternative data stream, such as `Zone.Identifier`.</span></span>
<span data-ttu-id="73d01-191">Однако не рекомендуется отменять проверки безопасности, которые блокируют файлы, загруженные из Интернета.</span><span class="sxs-lookup"><span data-stu-id="73d01-191">However, it is not the recommended way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="73d01-192">Если вы убедитесь, что скачанный файл является надежным, используйте `Unblock-File` командлет.</span><span class="sxs-lookup"><span data-stu-id="73d01-192">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="73d01-193">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="73d01-193">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="73d01-194">-Confirm</span><span class="sxs-lookup"><span data-stu-id="73d01-194">-Confirm</span></span>

<span data-ttu-id="73d01-195">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="73d01-195">Prompts you for confirmation before running the cmdlet.</span></span> <span data-ttu-id="73d01-196">Дополнительные сведения см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="73d01-196">For more information, see the following articles:</span></span>

- [<span data-ttu-id="73d01-197">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="73d01-197">about_Preference_Variables</span></span>](../microsoft.powershell.core/about/about_preference_variables.md#confirmpreference)
- [<span data-ttu-id="73d01-198">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="73d01-198">about_Functions_CmdletBindingAttribute</span></span>](../microsoft.powershell.core/about/about_functions_cmdletbindingattribute.md?#confirmimpact)

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

### <span data-ttu-id="73d01-199">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="73d01-199">-WhatIf</span></span>

<span data-ttu-id="73d01-200">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="73d01-200">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="73d01-201">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="73d01-201">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="73d01-202">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="73d01-202">CommonParameters</span></span>

<span data-ttu-id="73d01-203">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="73d01-203">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="73d01-204">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="73d01-204">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>


## <span data-ttu-id="73d01-205">Входные данные</span><span class="sxs-lookup"><span data-stu-id="73d01-205">INPUTS</span></span>

### <span data-ttu-id="73d01-206">System.String</span><span class="sxs-lookup"><span data-stu-id="73d01-206">System.String</span></span>

<span data-ttu-id="73d01-207">В этот командлет можно передать по конвейеру строку, содержащую путь, но не литеральный путь.</span><span class="sxs-lookup"><span data-stu-id="73d01-207">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="73d01-208">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="73d01-208">OUTPUTS</span></span>

### <span data-ttu-id="73d01-209">Нет</span><span class="sxs-lookup"><span data-stu-id="73d01-209">None</span></span>

<span data-ttu-id="73d01-210">Этот командлет не возвращает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="73d01-210">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="73d01-211">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="73d01-211">NOTES</span></span>

<span data-ttu-id="73d01-212">`Remove-Item`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="73d01-212">The `Remove-Item` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="73d01-213">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PsProvider`.</span><span class="sxs-lookup"><span data-stu-id="73d01-213">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="73d01-214">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="73d01-214">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="73d01-215">При попытке удалить папку, содержащую элементы, не используя параметр **рекурсии** , командлет запрашивает подтверждение.</span><span class="sxs-lookup"><span data-stu-id="73d01-215">When you try to delete a folder that contains items without using the **Recurse** parameter, the cmdlet prompts for confirmation.</span></span> <span data-ttu-id="73d01-216">Использование не `-Confirm:$false` подавляет запрос.</span><span class="sxs-lookup"><span data-stu-id="73d01-216">Using `-Confirm:$false` does not suppress the prompt.</span></span> <span data-ttu-id="73d01-217">Это сделано намеренно.</span><span class="sxs-lookup"><span data-stu-id="73d01-217">This is by design.</span></span>

## <span data-ttu-id="73d01-218">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="73d01-218">RELATED LINKS</span></span>

[<span data-ttu-id="73d01-219">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="73d01-219">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="73d01-220">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="73d01-220">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="73d01-221">Get-Item</span><span class="sxs-lookup"><span data-stu-id="73d01-221">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="73d01-222">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="73d01-222">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="73d01-223">Move-Item</span><span class="sxs-lookup"><span data-stu-id="73d01-223">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="73d01-224">New-Item</span><span class="sxs-lookup"><span data-stu-id="73d01-224">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="73d01-225">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="73d01-225">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="73d01-226">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="73d01-226">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="73d01-227">Set-Item</span><span class="sxs-lookup"><span data-stu-id="73d01-227">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="73d01-228">about_Providers</span><span class="sxs-lookup"><span data-stu-id="73d01-228">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="73d01-229">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="73d01-229">about_Preference_Variables</span></span>](../microsoft.powershell.core/about/about_preference_variables.md#confirmpreference)

[<span data-ttu-id="73d01-230">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="73d01-230">about_Functions_CmdletBindingAttribute</span></span>](../microsoft.powershell.core/about/about_functions_cmdletbindingattribute.md?#confirmimpact)
