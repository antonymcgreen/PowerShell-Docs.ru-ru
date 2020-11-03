---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/07/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-item?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Item
ms.openlocfilehash: b50decf6757140d4273dd2f3ed58281fe6f8f903
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229141"
---
# <span data-ttu-id="b35d3-103">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="b35d3-103">Remove-Item</span></span>

## <span data-ttu-id="b35d3-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b35d3-104">SYNOPSIS</span></span>
<span data-ttu-id="b35d3-105">Удаляет указанные элементы.</span><span class="sxs-lookup"><span data-stu-id="b35d3-105">Deletes the specified items.</span></span>

## <span data-ttu-id="b35d3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b35d3-106">SYNTAX</span></span>

### <span data-ttu-id="b35d3-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="b35d3-107">Path (Default)</span></span>

```
Remove-Item [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Recurse] [-Force] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="b35d3-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b35d3-108">LiteralPath</span></span>

```
Remove-Item -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Recurse] [-Force] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-Stream <String[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="b35d3-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b35d3-109">DESCRIPTION</span></span>

<span data-ttu-id="b35d3-110">`Remove-Item`Командлет удаляет один или несколько элементов.</span><span class="sxs-lookup"><span data-stu-id="b35d3-110">The `Remove-Item` cmdlet deletes one or more items.</span></span> <span data-ttu-id="b35d3-111">Так как он поддерживается многими поставщиками, он может удалять множество различных типов элементов, включая файлы, папки, разделы реестра, переменные, псевдонимы и функции.</span><span class="sxs-lookup"><span data-stu-id="b35d3-111">Because it is supported by many providers, it can delete many different types of items, including files, folders, registry keys, variables, aliases, and functions.</span></span>

## <span data-ttu-id="b35d3-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="b35d3-112">EXAMPLES</span></span>

### <span data-ttu-id="b35d3-113">Пример 1. Удаление файлов, имеющих любое расширение имени файла</span><span class="sxs-lookup"><span data-stu-id="b35d3-113">Example 1: Delete files that have any file name extension</span></span>

<span data-ttu-id="b35d3-114">В этом примере из папки удаляются все файлы, имена которых содержат точку ( `.` ) `C:\Test` .</span><span class="sxs-lookup"><span data-stu-id="b35d3-114">This example deletes all of the files that have names that include a dot (`.`) from the `C:\Test` folder.</span></span> <span data-ttu-id="b35d3-115">Поскольку команда задает точку, команда не удаляет папки или файлы, не имеющие расширения имени файла.</span><span class="sxs-lookup"><span data-stu-id="b35d3-115">Because the command specifies a dot, the command does not delete folders or files that have no file name extension.</span></span>

```powershell
Remove-Item C:\Test\*.*
```

### <span data-ttu-id="b35d3-116">Пример 2. Удаление некоторых файлов документов в папке</span><span class="sxs-lookup"><span data-stu-id="b35d3-116">Example 2: Delete some of the document files in a folder</span></span>

<span data-ttu-id="b35d3-117">В этом примере удаляется из текущей папки все файлы, имеющие `.doc` расширение имени файла, и имя, которое не включает `*1*` .</span><span class="sxs-lookup"><span data-stu-id="b35d3-117">This example deletes from the current folder all files that have a `.doc` file name extension and a name that does not include `*1*`.</span></span>

```powershell
Remove-Item * -Include *.doc -Exclude *1*
```

<span data-ttu-id="b35d3-118">`*`Для указания содержимого текущей папки используется подстановочный знак ().</span><span class="sxs-lookup"><span data-stu-id="b35d3-118">It uses the wildcard character (`*`) to specify the contents of the current folder.</span></span> <span data-ttu-id="b35d3-119">Для указания удаляемых файлов используются параметры **include** и **Exclude** .</span><span class="sxs-lookup"><span data-stu-id="b35d3-119">It uses the **Include** and **Exclude** parameters to specify the files to delete.</span></span>

### <span data-ttu-id="b35d3-120">Пример 3. Удаление скрытых файлов, доступ только для чтения</span><span class="sxs-lookup"><span data-stu-id="b35d3-120">Example 3: Delete hidden, read-only files</span></span>

<span data-ttu-id="b35d3-121">Эта команда удаляет файл, который как *скрытый* , так и *только для чтения*.</span><span class="sxs-lookup"><span data-stu-id="b35d3-121">This command deletes a file that is both *hidden* and *read-only*.</span></span>

```powershell
Remove-Item -Path C:\Test\hidden-RO-file.txt -Force
```

<span data-ttu-id="b35d3-122">Для указания файла используется параметр **path** .</span><span class="sxs-lookup"><span data-stu-id="b35d3-122">It uses the **Path** parameter to specify the file.</span></span> <span data-ttu-id="b35d3-123">Для его удаления используется параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="b35d3-123">It uses the **Force** parameter to delete it.</span></span> <span data-ttu-id="b35d3-124">Без **принудительного** использования нельзя удалять файлы, которые _доступны только для чтения_ или _скрыты_ .</span><span class="sxs-lookup"><span data-stu-id="b35d3-124">Without **Force** , you cannot delete _read-only_ or _hidden_ files.</span></span>

### <span data-ttu-id="b35d3-125">Пример 4. рекурсивное удаление файлов во вложенных папках</span><span class="sxs-lookup"><span data-stu-id="b35d3-125">Example 4: Delete files in subfolders recursively</span></span>

<span data-ttu-id="b35d3-126">Эта команда рекурсивно удаляет все CSV-файлы в текущей папке и во всех вложенных папках.</span><span class="sxs-lookup"><span data-stu-id="b35d3-126">This command deletes all of the CSV files in the current folder and all subfolders recursively.</span></span>

<span data-ttu-id="b35d3-127">Поскольку **рекурсивный** параметр в `Remove-Item` имеет известную ошибку, команда в этом примере использует `Get-ChildItem` для получения нужных файлов, а затем использует оператор конвейера для передачи их в `Remove-Item` .</span><span class="sxs-lookup"><span data-stu-id="b35d3-127">Because the **Recurse** parameter in `Remove-Item` has a known issue, the command in this example uses `Get-ChildItem` to get the desired files, and then uses the pipeline operator to pass them to `Remove-Item`.</span></span>

```powershell
Get-ChildItem * -Include *.csv -Recurse | Remove-Item
```

<span data-ttu-id="b35d3-128">В `Get-ChildItem` команде **path** имеет значение ( `*` ), которое представляет содержимое текущей папки.</span><span class="sxs-lookup"><span data-stu-id="b35d3-128">In the `Get-ChildItem` command, **Path** has a value of (`*`), which represents the contents of the current folder.</span></span> <span data-ttu-id="b35d3-129">Он использует параметр **include** для указания типа CSV-файла и использует рекурсию, чтобы сделать **возможной** рекурсивный выбор.</span><span class="sxs-lookup"><span data-stu-id="b35d3-129">It uses **Include** to specify the CSV file type, and it uses **Recurse** to make the retrieval recursive.</span></span> <span data-ttu-id="b35d3-130">При попытке указать тип файла путь, например `-Path *.csv` , командлет интерпретирует тему поиска как файл, не имеющий дочерних элементов, и **рекурсия** завершается сбоем.</span><span class="sxs-lookup"><span data-stu-id="b35d3-130">If you try to specify the file type the path, such as `-Path *.csv`, the cmdlet interprets the subject of the search to be a file that has no child items, and **Recurse** fails.</span></span>

### <span data-ttu-id="b35d3-131">Пример 5. рекурсивное удаление подразделов</span><span class="sxs-lookup"><span data-stu-id="b35d3-131">Example 5: Delete subkeys recursively</span></span>

<span data-ttu-id="b35d3-132">Эта команда удаляет раздел реестра "Олдапп" и все его подразделы и значения.</span><span class="sxs-lookup"><span data-stu-id="b35d3-132">This command deletes the "OldApp" registry key and all its subkeys and values.</span></span> <span data-ttu-id="b35d3-133">Он использует `Remove-Item` для удаления ключа.</span><span class="sxs-lookup"><span data-stu-id="b35d3-133">It uses `Remove-Item` to remove the key.</span></span> <span data-ttu-id="b35d3-134">Путь указан, но необязательное имя параметра ( **путь** ) пропущено.</span><span class="sxs-lookup"><span data-stu-id="b35d3-134">The path is specified, but the optional parameter name ( **Path** ) is omitted.</span></span>

<span data-ttu-id="b35d3-135">**Рекурсивный параметр удаляет** все содержимое ключа "олдапп" рекурсивно.</span><span class="sxs-lookup"><span data-stu-id="b35d3-135">The **Recurse** parameter deletes all of the contents of the "OldApp" key recursively.</span></span> <span data-ttu-id="b35d3-136">Если ключ содержит подразделы и не указан параметр **рекурсии** , вам будет предложено подтвердить удаление содержимого ключа.</span><span class="sxs-lookup"><span data-stu-id="b35d3-136">If the key contains subkeys and you omit the **Recurse** parameter, you are prompted to confirm that you want to delete the contents of the key.</span></span>

```powershell
Remove-Item HKLM:\Software\MyCompany\OldApp -Recurse
```

### <span data-ttu-id="b35d3-137">Пример 6. Удаление файлов со специальными символами</span><span class="sxs-lookup"><span data-stu-id="b35d3-137">Example 6: Deleting files with special characters</span></span>

<span data-ttu-id="b35d3-138">В следующем примере показано, как удалить файлы, содержащие специальные символы, такие как квадратные скобки или круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="b35d3-138">The following example shows how to delete files that contain special characters like brackets or parentheses.</span></span>

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

### <span data-ttu-id="b35d3-139">Пример 7. Удаление альтернативного потока данных</span><span class="sxs-lookup"><span data-stu-id="b35d3-139">Example 7: Remove an alternate data stream</span></span>

<span data-ttu-id="b35d3-140">В этом примере показано, как использовать динамический параметр **Stream** `Remove-Item` командлета для удаления альтернативного потока данных.</span><span class="sxs-lookup"><span data-stu-id="b35d3-140">This example shows how to use the **Stream** dynamic parameter of the `Remove-Item` cmdlet to delete an alternate data stream.</span></span> <span data-ttu-id="b35d3-141">Параметр Stream появился в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="b35d3-141">The stream parameter is introduced in Windows PowerShell 3.0.</span></span>

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

<span data-ttu-id="b35d3-142">Параметр **Stream** `Get-Item` получает поток **. идентификатор файла Zone** . `Copy-Script.ps1`</span><span class="sxs-lookup"><span data-stu-id="b35d3-142">The **Stream** parameter `Get-Item` gets the **Zone.Identifier** stream of the `Copy-Script.ps1` file.</span></span> <span data-ttu-id="b35d3-143">`Remove-Item` использует параметр **Stream** для удаления файла **Zone. identifier** .</span><span class="sxs-lookup"><span data-stu-id="b35d3-143">`Remove-Item` uses the **Stream** parameter to remove the **Zone.Identifier** stream of the file.</span></span> <span data-ttu-id="b35d3-144">Наконец, `Get-Item` командлет показывает, что **зона. идентификатор** потока удалена.</span><span class="sxs-lookup"><span data-stu-id="b35d3-144">Finally, the `Get-Item` cmdlet shows that the **Zone.Identifier** stream was deleted.</span></span>

## <span data-ttu-id="b35d3-145">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b35d3-145">PARAMETERS</span></span>

### <span data-ttu-id="b35d3-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="b35d3-146">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="b35d3-147">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b35d3-147">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="b35d3-148">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="b35d3-148">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="b35d3-149">-Exclude</span><span class="sxs-lookup"><span data-stu-id="b35d3-149">-Exclude</span></span>

<span data-ttu-id="b35d3-150">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="b35d3-150">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="b35d3-151">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="b35d3-151">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="b35d3-152">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="b35d3-152">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="b35d3-153">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b35d3-153">Wildcard characters are permitted.</span></span> <span data-ttu-id="b35d3-154">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="b35d3-154">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="b35d3-155">-Filter</span><span class="sxs-lookup"><span data-stu-id="b35d3-155">-Filter</span></span>

<span data-ttu-id="b35d3-156">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="b35d3-156">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="b35d3-157">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="b35d3-157">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="b35d3-158">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="b35d3-158">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="b35d3-159">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="b35d3-159">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="b35d3-160">-Force</span><span class="sxs-lookup"><span data-stu-id="b35d3-160">-Force</span></span>

<span data-ttu-id="b35d3-161">Заставляет командлет удалять элементы, которые в противном случае не могут быть изменены, например скрытые или только для чтения, а также псевдонимы или переменные только для чтения.</span><span class="sxs-lookup"><span data-stu-id="b35d3-161">Forces the cmdlet to remove items that cannot otherwise be changed, such as hidden or read-only files or read-only aliases or variables.</span></span> <span data-ttu-id="b35d3-162">С помощью этого командлета нельзя удалять постоянные псевдонимы или переменные.</span><span class="sxs-lookup"><span data-stu-id="b35d3-162">The cmdlet cannot remove constant aliases or variables.</span></span>
<span data-ttu-id="b35d3-163">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="b35d3-163">Implementation varies from provider to provider.</span></span> <span data-ttu-id="b35d3-164">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="b35d3-164">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span> <span data-ttu-id="b35d3-165">Даже при использовании параметра **Force** командлет не может переопределять ограничения безопасности.</span><span class="sxs-lookup"><span data-stu-id="b35d3-165">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

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

### <span data-ttu-id="b35d3-166">-Include</span><span class="sxs-lookup"><span data-stu-id="b35d3-166">-Include</span></span>

<span data-ttu-id="b35d3-167">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="b35d3-167">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="b35d3-168">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="b35d3-168">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="b35d3-169">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="b35d3-169">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="b35d3-170">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b35d3-170">Wildcard characters are permitted.</span></span> <span data-ttu-id="b35d3-171">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="b35d3-171">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="b35d3-172">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b35d3-172">-LiteralPath</span></span>

<span data-ttu-id="b35d3-173">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="b35d3-173">Specifies a path to one or more locations.</span></span> <span data-ttu-id="b35d3-174">Значение **LiteralPath** используется точно так же, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="b35d3-174">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="b35d3-175">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="b35d3-175">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="b35d3-176">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="b35d3-176">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="b35d3-177">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="b35d3-177">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="b35d3-178">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="b35d3-178">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="b35d3-179">-Path</span><span class="sxs-lookup"><span data-stu-id="b35d3-179">-Path</span></span>

<span data-ttu-id="b35d3-180">Указывает путь удаляемых элементов.</span><span class="sxs-lookup"><span data-stu-id="b35d3-180">Specifies a path of the items being removed.</span></span>
<span data-ttu-id="b35d3-181">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b35d3-181">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="b35d3-182">-Recurse</span><span class="sxs-lookup"><span data-stu-id="b35d3-182">-Recurse</span></span>

<span data-ttu-id="b35d3-183">Указывает, что этот командлет удаляет элементы в указанных расположениях и во всех дочерних элементах расположений.</span><span class="sxs-lookup"><span data-stu-id="b35d3-183">Indicates that this cmdlet deletes the items in the specified locations and in all child items of the locations.</span></span>

<span data-ttu-id="b35d3-184">При использовании с параметром **include** **рекурсивный** параметр может не удалить все вложенные папки или все дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="b35d3-184">When it is used with the **Include** parameter, the **Recurse** parameter might not delete all subfolders or all child items.</span></span> <span data-ttu-id="b35d3-185">Это известная проблема.</span><span class="sxs-lookup"><span data-stu-id="b35d3-185">This is a known issue.</span></span> <span data-ttu-id="b35d3-186">В качестве обходного решения попробуйте выполнить конвейерную `Get-ChildItem -Recurse` команду `Remove-Item` , как описано в примере 4 в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="b35d3-186">As a workaround, try piping results of the `Get-ChildItem -Recurse` command to `Remove-Item`, as described in "Example 4" in this topic.</span></span>

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

### <span data-ttu-id="b35d3-187">-Stream</span><span class="sxs-lookup"><span data-stu-id="b35d3-187">-Stream</span></span>

<span data-ttu-id="b35d3-188">Параметр **потока** — это динамический параметр, к которому добавляется поставщик FileSystem `Remove-Item` .</span><span class="sxs-lookup"><span data-stu-id="b35d3-188">The **Stream** parameter is a dynamic parameter that the FileSystem provider adds to `Remove-Item`.</span></span>
<span data-ttu-id="b35d3-189">Этот параметр работает только на дисках с файловой системой.</span><span class="sxs-lookup"><span data-stu-id="b35d3-189">This parameter works only in file system drives.</span></span>

<span data-ttu-id="b35d3-190">Можно использовать `Remove-Item` для удаления альтернативного потока данных.</span><span class="sxs-lookup"><span data-stu-id="b35d3-190">You can use `Remove-Item` to delete an alternative data stream.</span></span> <span data-ttu-id="b35d3-191">Однако не рекомендуется отменять проверки безопасности, которые блокируют файлы, загруженные из Интернета.</span><span class="sxs-lookup"><span data-stu-id="b35d3-191">However, it is not the recommended way to eliminate security checks that block files that are downloaded from the Internet.</span></span> <span data-ttu-id="b35d3-192">Если вы убедитесь, что скачанный файл является надежным, используйте `Unblock-File` командлет.</span><span class="sxs-lookup"><span data-stu-id="b35d3-192">If you verify that a downloaded file is safe, use the `Unblock-File` cmdlet.</span></span>

<span data-ttu-id="b35d3-193">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="b35d3-193">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="b35d3-194">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b35d3-194">-Confirm</span></span>

<span data-ttu-id="b35d3-195">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="b35d3-195">Prompts you for confirmation before running the cmdlet.</span></span> <span data-ttu-id="b35d3-196">Дополнительные сведения см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="b35d3-196">For more information, see the following articles:</span></span>

- [<span data-ttu-id="b35d3-197">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="b35d3-197">about_Preference_Variables</span></span>](../microsoft.powershell.core/about/about_preference_variables.md#confirmpreference)
- [<span data-ttu-id="b35d3-198">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="b35d3-198">about_Functions_CmdletBindingAttribute</span></span>](../microsoft.powershell.core/about/about_functions_cmdletbindingattribute.md?#confirmimpact)

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

### <span data-ttu-id="b35d3-199">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b35d3-199">-WhatIf</span></span>

<span data-ttu-id="b35d3-200">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="b35d3-200">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="b35d3-201">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="b35d3-201">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b35d3-202">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b35d3-202">CommonParameters</span></span>

<span data-ttu-id="b35d3-203">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="b35d3-203">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="b35d3-204">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="b35d3-204">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="b35d3-205">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b35d3-205">INPUTS</span></span>

### <span data-ttu-id="b35d3-206">System.String</span><span class="sxs-lookup"><span data-stu-id="b35d3-206">System.String</span></span>

<span data-ttu-id="b35d3-207">В этот командлет можно передать по конвейеру строку, содержащую путь, но не литеральный путь.</span><span class="sxs-lookup"><span data-stu-id="b35d3-207">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="b35d3-208">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b35d3-208">OUTPUTS</span></span>

### <span data-ttu-id="b35d3-209">Нет</span><span class="sxs-lookup"><span data-stu-id="b35d3-209">None</span></span>

<span data-ttu-id="b35d3-210">Этот командлет не возвращает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="b35d3-210">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="b35d3-211">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b35d3-211">NOTES</span></span>

<span data-ttu-id="b35d3-212">`Remove-Item`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="b35d3-212">The `Remove-Item` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="b35d3-213">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PsProvider`.</span><span class="sxs-lookup"><span data-stu-id="b35d3-213">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="b35d3-214">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="b35d3-214">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="b35d3-215">При попытке удалить папку, содержащую элементы, не используя параметр **рекурсии** , командлет запрашивает подтверждение.</span><span class="sxs-lookup"><span data-stu-id="b35d3-215">When you try to delete a folder that contains items without using the **Recurse** parameter, the cmdlet prompts for confirmation.</span></span> <span data-ttu-id="b35d3-216">Использование не `-Confirm:$false` подавляет запрос.</span><span class="sxs-lookup"><span data-stu-id="b35d3-216">Using `-Confirm:$false` does not suppress the prompt.</span></span> <span data-ttu-id="b35d3-217">Это сделано намеренно.</span><span class="sxs-lookup"><span data-stu-id="b35d3-217">This is by design.</span></span>

## <span data-ttu-id="b35d3-218">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b35d3-218">RELATED LINKS</span></span>

[<span data-ttu-id="b35d3-219">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="b35d3-219">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="b35d3-220">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="b35d3-220">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="b35d3-221">Get-Item</span><span class="sxs-lookup"><span data-stu-id="b35d3-221">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="b35d3-222">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="b35d3-222">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="b35d3-223">Move-Item</span><span class="sxs-lookup"><span data-stu-id="b35d3-223">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="b35d3-224">New-Item</span><span class="sxs-lookup"><span data-stu-id="b35d3-224">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="b35d3-225">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b35d3-225">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="b35d3-226">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="b35d3-226">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="b35d3-227">Set-Item</span><span class="sxs-lookup"><span data-stu-id="b35d3-227">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="b35d3-228">about_Providers</span><span class="sxs-lookup"><span data-stu-id="b35d3-228">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="b35d3-229">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="b35d3-229">about_Preference_Variables</span></span>](../microsoft.powershell.core/about/about_preference_variables.md#confirmpreference)

[<span data-ttu-id="b35d3-230">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="b35d3-230">about_Functions_CmdletBindingAttribute</span></span>](../microsoft.powershell.core/about/about_functions_cmdletbindingattribute.md?#confirmimpact)
