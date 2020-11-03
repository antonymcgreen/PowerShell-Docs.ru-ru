---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-item?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Item
ms.openlocfilehash: b1657d369d44d575ee7bed8b76d36224ea2748f2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227973"
---
# <span data-ttu-id="52096-103">New-Item</span><span class="sxs-lookup"><span data-stu-id="52096-103">New-Item</span></span>

## <span data-ttu-id="52096-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="52096-104">SYNOPSIS</span></span>
<span data-ttu-id="52096-105">Создает новый элемент.</span><span class="sxs-lookup"><span data-stu-id="52096-105">Creates a new item.</span></span>

## <span data-ttu-id="52096-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="52096-106">SYNTAX</span></span>

### <span data-ttu-id="52096-107">Path (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="52096-107">pathSet (Default)</span></span>

```
New-Item [-Path] <String[]> [-ItemType <String>] [-Value <Object>] [-Force] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="52096-108">имя</span><span class="sxs-lookup"><span data-stu-id="52096-108">nameSet</span></span>

```
New-Item [[-Path] <String[]>] -Name <String> [-ItemType <String>] [-Value <Object>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="52096-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="52096-109">DESCRIPTION</span></span>

<span data-ttu-id="52096-110">`New-Item`Командлет создает новый элемент и задает его значение.</span><span class="sxs-lookup"><span data-stu-id="52096-110">The `New-Item` cmdlet creates a new item and sets its value.</span></span> <span data-ttu-id="52096-111">Типы элементов, которые могут быть созданы, зависят от расположения элемента.</span><span class="sxs-lookup"><span data-stu-id="52096-111">The types of items that can be created depend on the location of the item.</span></span> <span data-ttu-id="52096-112">Например, в файловой системе `New-Item` создаются файлы и папки.</span><span class="sxs-lookup"><span data-stu-id="52096-112">For example, in the file system, `New-Item` creates files and folders.</span></span> <span data-ttu-id="52096-113">В реестре `New-Item` создает разделы и записи реестра.</span><span class="sxs-lookup"><span data-stu-id="52096-113">In the registry, `New-Item` creates registry keys and entries.</span></span>

<span data-ttu-id="52096-114">`New-Item` также может задавать значения создаваемых элементов.</span><span class="sxs-lookup"><span data-stu-id="52096-114">`New-Item` can also set the value of the items that it creates.</span></span> <span data-ttu-id="52096-115">Например, при создании нового файла `New-Item` может добавить в файл начальное содержимое.</span><span class="sxs-lookup"><span data-stu-id="52096-115">For example, when it creates a new file, `New-Item` can add initial content to the file.</span></span>

## <span data-ttu-id="52096-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="52096-116">EXAMPLES</span></span>

### <span data-ttu-id="52096-117">Пример 1. Создание файла в текущем каталоге</span><span class="sxs-lookup"><span data-stu-id="52096-117">Example 1: Create a file in the current directory</span></span>

<span data-ttu-id="52096-118">Эта команда создает текстовый файл с именем "testfile1.txt" в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="52096-118">This command creates a text file that is named "testfile1.txt" in the current directory.</span></span> <span data-ttu-id="52096-119">Точка (".") в значении параметра **path** указывает текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="52096-119">The dot ('.') in the value of the **Path** parameter indicates the current directory.</span></span> <span data-ttu-id="52096-120">Текст в кавычках, следующий за параметром **value** , добавляется в файл как содержимое.</span><span class="sxs-lookup"><span data-stu-id="52096-120">The quoted text that follows the **Value** parameter is added to the file as content.</span></span>

```powershell
New-Item -Path . -Name "testfile1.txt" -ItemType "file" -Value "This is a text string."
```

### <span data-ttu-id="52096-121">Пример 2. Создание каталога</span><span class="sxs-lookup"><span data-stu-id="52096-121">Example 2: Create a directory</span></span>

<span data-ttu-id="52096-122">Эта команда создает каталог с именем "файл_журнала" на `C:` диске.</span><span class="sxs-lookup"><span data-stu-id="52096-122">This command creates a directory named "Logfiles" in the `C:` drive.</span></span> <span data-ttu-id="52096-123">Параметр **ItemType** указывает, что новый элемент является каталогом, а не файлом или другим объектом файловой системы.</span><span class="sxs-lookup"><span data-stu-id="52096-123">The **ItemType** parameter specifies that the new item is a directory, not a file or other file system object.</span></span>

```powershell
New-Item -Path "c:\" -Name "logfiles" -ItemType "directory"
```

### <span data-ttu-id="52096-124">Пример 3. Создание профиля</span><span class="sxs-lookup"><span data-stu-id="52096-124">Example 3: Create a profile</span></span>

<span data-ttu-id="52096-125">Эта команда создает профиль PowerShell по пути, указанному `$profile` переменной.</span><span class="sxs-lookup"><span data-stu-id="52096-125">This command creates a PowerShell profile in the path that is specified by the `$profile` variable.</span></span>

<span data-ttu-id="52096-126">Для настройки PowerShell можно использовать профили.</span><span class="sxs-lookup"><span data-stu-id="52096-126">You can use profiles to customize PowerShell.</span></span> <span data-ttu-id="52096-127">`$profile` — Это автоматическая (встроенная) переменная, в которой хранится путь и имя файла профиля "CurrentUser/CurrentHost".</span><span class="sxs-lookup"><span data-stu-id="52096-127">`$profile` is an automatic (built-in) variable that stores the path and file name of the "CurrentUser/CurrentHost" profile.</span></span> <span data-ttu-id="52096-128">По умолчанию профиль не существует, несмотря на то, что PowerShell сохраняет путь и имя файла для него.</span><span class="sxs-lookup"><span data-stu-id="52096-128">By default, the profile does not exist, even though PowerShell stores a path and file name for it.</span></span>

<span data-ttu-id="52096-129">В этой команде `$profile` переменная представляет путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="52096-129">In this command, the `$profile` variable represents the path of the file.</span></span> <span data-ttu-id="52096-130">Параметр **ItemType** указывает, что команда создает файл.</span><span class="sxs-lookup"><span data-stu-id="52096-130">**ItemType** parameter specifies that the command creates a file.</span></span> <span data-ttu-id="52096-131">Параметр **Force** позволяет создать файл в пути профиля, даже если каталоги в пути не существуют.</span><span class="sxs-lookup"><span data-stu-id="52096-131">The **Force** parameter lets you create a file in the profile path, even when the directories in the path do not exist.</span></span>

<span data-ttu-id="52096-132">После создания профиля можно ввести в профиль псевдонимы, функции и скрипты, чтобы настроить оболочку.</span><span class="sxs-lookup"><span data-stu-id="52096-132">After you create a profile, you can enter aliases, functions, and scripts in the profile to customize your shell.</span></span>

<span data-ttu-id="52096-133">Дополнительные сведения см. в разделе [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md) и [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="52096-133">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md) and [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

```powershell
New-Item -Path $profile -ItemType "file" -Force
```

> [!NOTE]
> <span data-ttu-id="52096-134">При создании файла с помощью этого метода полученный файл кодируется как UTF-8 без отметки порядка байтов (BOM).</span><span class="sxs-lookup"><span data-stu-id="52096-134">When you create a file using this method, the resulting file is encoded as UTF-8 without a byte-order-mark (BOM).</span></span>

### <span data-ttu-id="52096-135">Пример 4. Создание каталога в другом каталоге</span><span class="sxs-lookup"><span data-stu-id="52096-135">Example 4: Create a directory in a different directory</span></span>

<span data-ttu-id="52096-136">В этом примере создается новый каталог Scripts в каталоге "К:\пс-тест".</span><span class="sxs-lookup"><span data-stu-id="52096-136">This example creates a new Scripts directory in the "C:\PS-Test" directory.</span></span>

<span data-ttu-id="52096-137">Имя нового элемента каталога, «Scripts», включается в значение параметра **path** , а не указывается в значении **Name** .</span><span class="sxs-lookup"><span data-stu-id="52096-137">The name of the new directory item, "Scripts", is included in the value of **Path** parameter, instead of being specified in the value of **Name** .</span></span> <span data-ttu-id="52096-138">Как указывается в синтаксисе, любая форма команды допустима.</span><span class="sxs-lookup"><span data-stu-id="52096-138">As indicated by the syntax, either command form is valid.</span></span>

```powershell
New-Item -ItemType "directory" -Path "c:\ps-test\scripts"
```

### <span data-ttu-id="52096-139">Пример 5. Создание нескольких файлов</span><span class="sxs-lookup"><span data-stu-id="52096-139">Example 5: Create multiple files</span></span>

<span data-ttu-id="52096-140">В этом примере создаются файлы в двух разных каталогах.</span><span class="sxs-lookup"><span data-stu-id="52096-140">This example creates files in two different directories.</span></span> <span data-ttu-id="52096-141">Поскольку **путь** принимает несколько строк, его можно использовать для создания нескольких элементов.</span><span class="sxs-lookup"><span data-stu-id="52096-141">Because **Path** takes multiple strings, you can use it to create multiple items.</span></span>

```powershell
New-Item -ItemType "file" -Path "c:\ps-test\test.txt", "c:\ps-test\Logs\test.log"
```

### <span data-ttu-id="52096-142">Пример 6. Использование параметра-Force для попыток повторного создания папок</span><span class="sxs-lookup"><span data-stu-id="52096-142">Example 6: Use the -Force parameter to attempt to recreate folders</span></span>

<span data-ttu-id="52096-143">В этом примере создается папка с файлом внутри.</span><span class="sxs-lookup"><span data-stu-id="52096-143">This example creates a folder with a file inside.</span></span> <span data-ttu-id="52096-144">Затем пытается создать ту же папку с помощью `-Force` .</span><span class="sxs-lookup"><span data-stu-id="52096-144">Then, attempts to create the same folder using `-Force`.</span></span> <span data-ttu-id="52096-145">Она не перезаписывает папку, а просто возвращает существующий объект Folder с нетронутым файлом.</span><span class="sxs-lookup"><span data-stu-id="52096-145">It will not overwrite the folder but simply return the existing folder object with the file created intact.</span></span>

```powershell
PS> New-Item -Path .\TestFolder -ItemType Directory
PS> New-Item -Path .\TestFolder\TestFile.txt -ItemType File

PS> New-Item -Path .\TestFolder -ItemType Directory -Force

    Directory: C:\
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         5/1/2020   8:03 AM                TestFolder

PS> Get-ChildItem .\TestFolder\

    Directory: C:\TestFolder
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/1/2020   8:03 AM              0 TestFile.txt
```

### <span data-ttu-id="52096-146">Пример 7. Использование параметра-Force для перезаписи существующих файлов</span><span class="sxs-lookup"><span data-stu-id="52096-146">Example 7: Use the -Force parameter to overwrite existing files</span></span>

<span data-ttu-id="52096-147">В этом примере создается файл со значением, а затем создается файл повторно с помощью `-Force` .</span><span class="sxs-lookup"><span data-stu-id="52096-147">This example creates a file with a value and then recreates the file using `-Force`.</span></span> <span data-ttu-id="52096-148">При этом существующий файл перезаписывается, и его содержимое будет потеряно, как видно в свойстве Length.</span><span class="sxs-lookup"><span data-stu-id="52096-148">This overwrites The existing file and it will lose it's content as you can see by the length property</span></span>

```powershell
PS> New-Item ./TestFile.txt -ItemType File -Value 'This is just a test file'

    Directory: C:\Source\Test
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/1/2020   8:32 AM             24 TestFile.txt

New-Item ./TestFile.txt -ItemType File -Force

    Directory: C:\Source\Test
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/1/2020   8:32 AM              0 TestFile.txt
```

> [!NOTE]
> <span data-ttu-id="52096-149">При использовании `New-Item` с `-Force` параметром для создания разделов реестра команда будет вести себя так же, как при перезаписи файла.</span><span class="sxs-lookup"><span data-stu-id="52096-149">When using `New-Item` with the `-Force` switch to create registry keys, the command will behave the same as when overwriting a file.</span></span> <span data-ttu-id="52096-150">Если раздел реестра уже существует, ключ и все его свойства и значения будут перезаписаны пустым ключом реестра.</span><span class="sxs-lookup"><span data-stu-id="52096-150">If the registry key already exists, the key and all properties and values will be overwritten with an empty registry key.</span></span>

## <span data-ttu-id="52096-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="52096-151">PARAMETERS</span></span>

### <span data-ttu-id="52096-152">-Credential</span><span class="sxs-lookup"><span data-stu-id="52096-152">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="52096-153">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="52096-153">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="52096-154">Чтобы олицетворить другого пользователя или повысить свои учетные данные при запуске этого командлета, используйте `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="52096-154">To impersonate another user or elevate your credentials when running this cmdlet, use `Invoke-Command`.</span></span>

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

### <span data-ttu-id="52096-155">-Force</span><span class="sxs-lookup"><span data-stu-id="52096-155">-Force</span></span>

<span data-ttu-id="52096-156">Заставляет этот командлет создать элемент, записывающий существующий элемент только для чтения.</span><span class="sxs-lookup"><span data-stu-id="52096-156">Forces this cmdlet to create an item that writes over an existing read-only item.</span></span> <span data-ttu-id="52096-157">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="52096-157">Implementation varies from provider to provider.</span></span> <span data-ttu-id="52096-158">Даже при использовании параметра **Force** командлет не может переопределять ограничения безопасности.</span><span class="sxs-lookup"><span data-stu-id="52096-158">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

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

### <span data-ttu-id="52096-159">-ItemType</span><span class="sxs-lookup"><span data-stu-id="52096-159">-ItemType</span></span>

<span data-ttu-id="52096-160">Указывает тип нового элемента, заданный поставщиком.</span><span class="sxs-lookup"><span data-stu-id="52096-160">Specifies the provider-specified type of the new item.</span></span> <span data-ttu-id="52096-161">Доступные значения этого параметра зависят от текущего используемого поставщика.</span><span class="sxs-lookup"><span data-stu-id="52096-161">The available values of this parameter depend on the current provider you are using.</span></span>

<span data-ttu-id="52096-162">Если расположение находится в `FileSystem` диске, допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="52096-162">If your location is in a `FileSystem` drive, the following values are allowed:</span></span>

- <span data-ttu-id="52096-163">Файл</span><span class="sxs-lookup"><span data-stu-id="52096-163">File</span></span>
- <span data-ttu-id="52096-164">Каталог</span><span class="sxs-lookup"><span data-stu-id="52096-164">Directory</span></span>
- <span data-ttu-id="52096-165">SymbolicLink</span><span class="sxs-lookup"><span data-stu-id="52096-165">SymbolicLink</span></span>
- <span data-ttu-id="52096-166">Соединение</span><span class="sxs-lookup"><span data-stu-id="52096-166">Junction</span></span>
- <span data-ttu-id="52096-167">HardLink</span><span class="sxs-lookup"><span data-stu-id="52096-167">HardLink</span></span>

<span data-ttu-id="52096-168">При создании файла с помощью этого метода полученный файл кодируется как UTF-8 без отметки порядка байтов (BOM).</span><span class="sxs-lookup"><span data-stu-id="52096-168">When you create a file using this method, the resulting file is encoded as UTF-8 without a byte-order-mark (BOM).</span></span>

<span data-ttu-id="52096-169">На `Certificate` диске можно указать следующие значения:</span><span class="sxs-lookup"><span data-stu-id="52096-169">In a `Certificate` drive, these are the values you can specify:</span></span>

- <span data-ttu-id="52096-170">Поставщик Certificate</span><span class="sxs-lookup"><span data-stu-id="52096-170">Certificate Provider</span></span>
- <span data-ttu-id="52096-171">Сертификат</span><span class="sxs-lookup"><span data-stu-id="52096-171">Certificate</span></span>
- <span data-ttu-id="52096-172">Магазин</span><span class="sxs-lookup"><span data-stu-id="52096-172">Store</span></span>
- <span data-ttu-id="52096-173">StoreLocation</span><span class="sxs-lookup"><span data-stu-id="52096-173">StoreLocation</span></span>

<span data-ttu-id="52096-174">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="52096-174">For more information see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Type

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="52096-175">-Name</span><span class="sxs-lookup"><span data-stu-id="52096-175">-Name</span></span>

<span data-ttu-id="52096-176">Указывает имя нового элемента.</span><span class="sxs-lookup"><span data-stu-id="52096-176">Specifies the name of the new item.</span></span> <span data-ttu-id="52096-177">Можно указать имя нового элемента в значении параметра **Name** или **path** , а также указать путь к новому элементу в значении **имени** или **пути** .</span><span class="sxs-lookup"><span data-stu-id="52096-177">You can specify the name of the new item in the **Name** or **Path** parameter value, and you can specify the path of the new item in **Name** or **Path** value.</span></span> <span data-ttu-id="52096-178">Имена элементов, переданных с помощью параметра **Name** , создаются относительно значения параметра **path** .</span><span class="sxs-lookup"><span data-stu-id="52096-178">Items names passed using the **Name** parameter are created relative to the value of the **Path** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: nameSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="52096-179">-Path</span><span class="sxs-lookup"><span data-stu-id="52096-179">-Path</span></span>

<span data-ttu-id="52096-180">Указывает путь к расположению нового элемента.</span><span class="sxs-lookup"><span data-stu-id="52096-180">Specifies the path of the location of the new item.</span></span> <span data-ttu-id="52096-181">По умолчанию используется текущее расположение, когда **путь** опущен.</span><span class="sxs-lookup"><span data-stu-id="52096-181">The default is the current location when **Path** is omitted.</span></span> <span data-ttu-id="52096-182">Можно указать имя нового элемента в **поле имя** или включить его в **путь** .</span><span class="sxs-lookup"><span data-stu-id="52096-182">You can specify the name of the new item in **Name** , or include it in **Path** .</span></span> <span data-ttu-id="52096-183">Имена элементов, переданных с помощью параметра **Name** , создаются относительно значения параметра **path** .</span><span class="sxs-lookup"><span data-stu-id="52096-183">Items names passed using the **Name** parameter are created relative to the value of the **Path** parameter.</span></span>

<span data-ttu-id="52096-184">Для этого командлета параметр **path** работает как параметр **LiteralPath** других командлетов.</span><span class="sxs-lookup"><span data-stu-id="52096-184">For this cmdlet, the **Path** parameter works like the **LiteralPath** parameter of other cmdlets.</span></span>
<span data-ttu-id="52096-185">Символы-шаблоны не обрабатываются.</span><span class="sxs-lookup"><span data-stu-id="52096-185">Wildcard characters are not interpreted.</span></span> <span data-ttu-id="52096-186">Все символы передаются поставщику расположения.</span><span class="sxs-lookup"><span data-stu-id="52096-186">All characters are passed to the location's provider.</span></span> <span data-ttu-id="52096-187">Поставщик может не поддерживать все символы.</span><span class="sxs-lookup"><span data-stu-id="52096-187">The provider may not support all characters.</span></span> <span data-ttu-id="52096-188">Например, нельзя создать имя файла, содержащее символ звездочки ( `*` ).</span><span class="sxs-lookup"><span data-stu-id="52096-188">For example, you cannot create a filename that contains an asterisk (`*`) character.</span></span>

```yaml
Type: System.String[]
Parameter Sets: pathSet, nameSet
Aliases:

Required: True (pathSet), False (nameSet)
Position: 0
Default value: Current location
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="52096-189">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="52096-189">-UseTransaction</span></span>

<span data-ttu-id="52096-190">Включает команду в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="52096-190">Includes the command in the active transaction.</span></span> <span data-ttu-id="52096-191">Этот параметр доступен только при выполнении транзакции.</span><span class="sxs-lookup"><span data-stu-id="52096-191">This parameter is valid only when a transaction is in progress.</span></span> <span data-ttu-id="52096-192">Дополнительные сведения см. в разделе [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span><span class="sxs-lookup"><span data-stu-id="52096-192">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

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

### <span data-ttu-id="52096-193">-Value</span><span class="sxs-lookup"><span data-stu-id="52096-193">-Value</span></span>

<span data-ttu-id="52096-194">Указывает значение нового элемента.</span><span class="sxs-lookup"><span data-stu-id="52096-194">Specifies the value of the new item.</span></span> <span data-ttu-id="52096-195">Можно также передать значение в `New-Item` .</span><span class="sxs-lookup"><span data-stu-id="52096-195">You can also pipe a value to `New-Item`.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases: Target

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="52096-196">-Confirm</span><span class="sxs-lookup"><span data-stu-id="52096-196">-Confirm</span></span>

<span data-ttu-id="52096-197">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="52096-197">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="52096-198">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="52096-198">-WhatIf</span></span>

<span data-ttu-id="52096-199">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="52096-199">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="52096-200">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="52096-200">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="52096-201">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="52096-201">CommonParameters</span></span>

<span data-ttu-id="52096-202">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="52096-202">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="52096-203">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="52096-203">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="52096-204">Входные данные</span><span class="sxs-lookup"><span data-stu-id="52096-204">INPUTS</span></span>

### <span data-ttu-id="52096-205">System.Object</span><span class="sxs-lookup"><span data-stu-id="52096-205">System.Object</span></span>

<span data-ttu-id="52096-206">В этот командлет можно передать значение для нового элемента.</span><span class="sxs-lookup"><span data-stu-id="52096-206">You can pipe a value for the new item to this cmdlet.</span></span>

## <span data-ttu-id="52096-207">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="52096-207">OUTPUTS</span></span>

### <span data-ttu-id="52096-208">System.Object</span><span class="sxs-lookup"><span data-stu-id="52096-208">System.Object</span></span>

<span data-ttu-id="52096-209">Этот командлет возвращает элемент, который он создает.</span><span class="sxs-lookup"><span data-stu-id="52096-209">This cmdlet returns the item that it creates.</span></span>

## <span data-ttu-id="52096-210">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="52096-210">NOTES</span></span>

<span data-ttu-id="52096-211">`New-Item` предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="52096-211">`New-Item` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="52096-212">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PsProvider`.</span><span class="sxs-lookup"><span data-stu-id="52096-212">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="52096-213">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="52096-213">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="52096-214">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="52096-214">RELATED LINKS</span></span>

[<span data-ttu-id="52096-215">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="52096-215">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="52096-216">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="52096-216">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="52096-217">Get-Item</span><span class="sxs-lookup"><span data-stu-id="52096-217">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="52096-218">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="52096-218">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="52096-219">Move-Item</span><span class="sxs-lookup"><span data-stu-id="52096-219">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="52096-220">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="52096-220">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="52096-221">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="52096-221">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="52096-222">Set-Item</span><span class="sxs-lookup"><span data-stu-id="52096-222">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="52096-223">about_Providers</span><span class="sxs-lookup"><span data-stu-id="52096-223">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
