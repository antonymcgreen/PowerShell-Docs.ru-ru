---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-item?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Item
ms.openlocfilehash: 4c247513ab06f1bcba648a62969fb7d458e0d35d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602094"
---
# <span data-ttu-id="8113b-102">New-Item</span><span class="sxs-lookup"><span data-stu-id="8113b-102">New-Item</span></span>

## <span data-ttu-id="8113b-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="8113b-103">SYNOPSIS</span></span>
<span data-ttu-id="8113b-104">Создает новый элемент.</span><span class="sxs-lookup"><span data-stu-id="8113b-104">Creates a new item.</span></span>

## <span data-ttu-id="8113b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8113b-105">SYNTAX</span></span>

### <span data-ttu-id="8113b-106">Path (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8113b-106">pathSet (Default)</span></span>

```
New-Item [-Path] <String[]> [-ItemType <String>] [-Value <Object>] [-Force] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="8113b-107">имя</span><span class="sxs-lookup"><span data-stu-id="8113b-107">nameSet</span></span>

```
New-Item [[-Path] <String[]>] -Name <String> [-ItemType <String>] [-Value <Object>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="8113b-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8113b-108">DESCRIPTION</span></span>

<span data-ttu-id="8113b-109">`New-Item`Командлет создает новый элемент и задает его значение.</span><span class="sxs-lookup"><span data-stu-id="8113b-109">The `New-Item` cmdlet creates a new item and sets its value.</span></span> <span data-ttu-id="8113b-110">Типы элементов, которые могут быть созданы, зависят от расположения элемента.</span><span class="sxs-lookup"><span data-stu-id="8113b-110">The types of items that can be created depend on the location of the item.</span></span> <span data-ttu-id="8113b-111">Например, в файловой системе `New-Item` создаются файлы и папки.</span><span class="sxs-lookup"><span data-stu-id="8113b-111">For example, in the file system, `New-Item` creates files and folders.</span></span> <span data-ttu-id="8113b-112">В реестре `New-Item` создает разделы и записи реестра.</span><span class="sxs-lookup"><span data-stu-id="8113b-112">In the registry, `New-Item` creates registry keys and entries.</span></span>

<span data-ttu-id="8113b-113">`New-Item` также может задавать значения создаваемых элементов.</span><span class="sxs-lookup"><span data-stu-id="8113b-113">`New-Item` can also set the value of the items that it creates.</span></span> <span data-ttu-id="8113b-114">Например, при создании нового файла `New-Item` может добавить в файл начальное содержимое.</span><span class="sxs-lookup"><span data-stu-id="8113b-114">For example, when it creates a new file, `New-Item` can add initial content to the file.</span></span>

## <span data-ttu-id="8113b-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="8113b-115">EXAMPLES</span></span>

### <span data-ttu-id="8113b-116">Пример 1. Создание файла в текущем каталоге</span><span class="sxs-lookup"><span data-stu-id="8113b-116">Example 1: Create a file in the current directory</span></span>

<span data-ttu-id="8113b-117">Эта команда создает текстовый файл с именем "testfile1.txt" в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="8113b-117">This command creates a text file that is named "testfile1.txt" in the current directory.</span></span> <span data-ttu-id="8113b-118">Точка (".") в значении параметра **path** указывает текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="8113b-118">The dot ('.') in the value of the **Path** parameter indicates the current directory.</span></span> <span data-ttu-id="8113b-119">Текст в кавычках, следующий за параметром **value** , добавляется в файл как содержимое.</span><span class="sxs-lookup"><span data-stu-id="8113b-119">The quoted text that follows the **Value** parameter is added to the file as content.</span></span>

```powershell
New-Item -Path . -Name "testfile1.txt" -ItemType "file" -Value "This is a text string."
```

### <span data-ttu-id="8113b-120">Пример 2. Создание каталога</span><span class="sxs-lookup"><span data-stu-id="8113b-120">Example 2: Create a directory</span></span>

<span data-ttu-id="8113b-121">Эта команда создает каталог с именем "файл_журнала" на `C:` диске.</span><span class="sxs-lookup"><span data-stu-id="8113b-121">This command creates a directory named "Logfiles" in the `C:` drive.</span></span> <span data-ttu-id="8113b-122">Параметр **ItemType** указывает, что новый элемент является каталогом, а не файлом или другим объектом файловой системы.</span><span class="sxs-lookup"><span data-stu-id="8113b-122">The **ItemType** parameter specifies that the new item is a directory, not a file or other file system object.</span></span>

```powershell
New-Item -Path "c:\" -Name "logfiles" -ItemType "directory"
```

### <span data-ttu-id="8113b-123">Пример 3. Создание профиля</span><span class="sxs-lookup"><span data-stu-id="8113b-123">Example 3: Create a profile</span></span>

<span data-ttu-id="8113b-124">Эта команда создает профиль PowerShell по пути, указанному `$profile` переменной.</span><span class="sxs-lookup"><span data-stu-id="8113b-124">This command creates a PowerShell profile in the path that is specified by the `$profile` variable.</span></span>

<span data-ttu-id="8113b-125">Для настройки PowerShell можно использовать профили.</span><span class="sxs-lookup"><span data-stu-id="8113b-125">You can use profiles to customize PowerShell.</span></span> <span data-ttu-id="8113b-126">`$profile` — Это автоматическая (встроенная) переменная, в которой хранится путь и имя файла профиля "CurrentUser/CurrentHost".</span><span class="sxs-lookup"><span data-stu-id="8113b-126">`$profile` is an automatic (built-in) variable that stores the path and file name of the "CurrentUser/CurrentHost" profile.</span></span> <span data-ttu-id="8113b-127">По умолчанию профиль не существует, несмотря на то, что PowerShell сохраняет путь и имя файла для него.</span><span class="sxs-lookup"><span data-stu-id="8113b-127">By default, the profile does not exist, even though PowerShell stores a path and file name for it.</span></span>

<span data-ttu-id="8113b-128">В этой команде `$profile` переменная представляет путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="8113b-128">In this command, the `$profile` variable represents the path of the file.</span></span> <span data-ttu-id="8113b-129">Параметр **ItemType** указывает, что команда создает файл.</span><span class="sxs-lookup"><span data-stu-id="8113b-129">**ItemType** parameter specifies that the command creates a file.</span></span> <span data-ttu-id="8113b-130">Параметр **Force** позволяет создать файл в пути профиля, даже если каталоги в пути не существуют.</span><span class="sxs-lookup"><span data-stu-id="8113b-130">The **Force** parameter lets you create a file in the profile path, even when the directories in the path do not exist.</span></span>

<span data-ttu-id="8113b-131">После создания профиля можно ввести в профиль псевдонимы, функции и скрипты, чтобы настроить оболочку.</span><span class="sxs-lookup"><span data-stu-id="8113b-131">After you create a profile, you can enter aliases, functions, and scripts in the profile to customize your shell.</span></span>

<span data-ttu-id="8113b-132">Дополнительные сведения см. в разделе [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md) и [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="8113b-132">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md) and [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

```powershell
New-Item -Path $profile -ItemType "file" -Force
```

### <span data-ttu-id="8113b-133">Пример 4. Создание каталога в другом каталоге</span><span class="sxs-lookup"><span data-stu-id="8113b-133">Example 4: Create a directory in a different directory</span></span>

<span data-ttu-id="8113b-134">В этом примере создается новый каталог Scripts в каталоге "К:\пс-тест".</span><span class="sxs-lookup"><span data-stu-id="8113b-134">This example creates a new Scripts directory in the "C:\PS-Test" directory.</span></span>

<span data-ttu-id="8113b-135">Имя нового элемента каталога, «Scripts», включается в значение параметра **path** , а не указывается в значении **Name**.</span><span class="sxs-lookup"><span data-stu-id="8113b-135">The name of the new directory item, "Scripts", is included in the value of **Path** parameter, instead of being specified in the value of **Name**.</span></span> <span data-ttu-id="8113b-136">Как указывается в синтаксисе, любая форма команды допустима.</span><span class="sxs-lookup"><span data-stu-id="8113b-136">As indicated by the syntax, either command form is valid.</span></span>

```powershell
New-Item -ItemType "directory" -Path "c:\ps-test\scripts"
```

### <span data-ttu-id="8113b-137">Пример 5. Создание нескольких файлов</span><span class="sxs-lookup"><span data-stu-id="8113b-137">Example 5: Create multiple files</span></span>

<span data-ttu-id="8113b-138">В этом примере создаются файлы в двух разных каталогах.</span><span class="sxs-lookup"><span data-stu-id="8113b-138">This example creates files in two different directories.</span></span> <span data-ttu-id="8113b-139">Поскольку **путь** принимает несколько строк, его можно использовать для создания нескольких элементов.</span><span class="sxs-lookup"><span data-stu-id="8113b-139">Because **Path** takes multiple strings, you can use it to create multiple items.</span></span>

```powershell
New-Item -ItemType "file" -Path "c:\ps-test\test.txt", "c:\ps-test\Logs\test.log"
```

### <span data-ttu-id="8113b-140">Пример 6. Использование подстановочных знаков для создания файлов в нескольких каталогах</span><span class="sxs-lookup"><span data-stu-id="8113b-140">Example 6: Use wildcards to create files in multiple directories</span></span>

<span data-ttu-id="8113b-141">`New-Item`Командлет поддерживает подстановочные знаки в параметре **path** .</span><span class="sxs-lookup"><span data-stu-id="8113b-141">The `New-Item` cmdlet supports wildcards in the **Path** parameter.</span></span> <span data-ttu-id="8113b-142">Следующая команда создает `temp.txt` файл во всех каталогах, указанных подстановочными знаками в параметре **path** .</span><span class="sxs-lookup"><span data-stu-id="8113b-142">The following command creates a `temp.txt` file in all of the directories specified by the wildcards in the **Path** parameter.</span></span>

```powershell
Get-ChildItem -Path C:\Temp\
```

```Output
    Directory:  C:\Temp

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d-----        5/15/2019   6:45 AM        1   One
d-----        5/15/2019   6:45 AM        1   Two
d-----        5/15/2019   6:45 AM        1   Three
```

```powershell
New-Item -Path * -Name temp.txt -ItemType File | Select-Object FullName
```

```Output
FullName
--------
C:\Temp\One\temp.txt
C:\Temp\Three\temp.txt
C:\Temp\Two\temp.txt
```

<span data-ttu-id="8113b-143">`Get-ChildItem`Командлет показывает три `C:\Temp` каталога в каталоге.</span><span class="sxs-lookup"><span data-stu-id="8113b-143">The `Get-ChildItem` cmdlet shows three directories under the `C:\Temp` directory.</span></span> <span data-ttu-id="8113b-144">Использование подстановочных знаков `New-Item` командлет создает `temp.txt` файл во всех каталогах в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="8113b-144">Using wildcards the `New-Item` cmdlet creates a `temp.txt` file in all of the directories under the current directory.</span></span> <span data-ttu-id="8113b-145">`New-Item`Командлет выводит созданные элементы, которые передаются в, чтобы `Select-Object` проверить пути к вновь созданным файлам.</span><span class="sxs-lookup"><span data-stu-id="8113b-145">The `New-Item` cmdlet outputs the items you created, which is piped to `Select-Object` to verify the paths of the newly created files.</span></span>

### <span data-ttu-id="8113b-146">Пример 7. Создание символьной ссылки на файл или папку</span><span class="sxs-lookup"><span data-stu-id="8113b-146">Example 7: Create a symbolic link to a file or folder</span></span>

<span data-ttu-id="8113b-147">В этом примере создается символьная ссылка на файл Notice.txt в текущей папке.</span><span class="sxs-lookup"><span data-stu-id="8113b-147">This example creates a symbolic link to the Notice.txt file in the current folder.</span></span>

```powershell
$link = New-Item -ItemType SymbolicLink -Path .\link -Target .\Notice.txt
$link | Select-Object LinkType, Target
```

```Output
LinkType     Target
--------     ------
SymbolicLink {.\Notice.txt}
```

<span data-ttu-id="8113b-148">В этом примере **Target** является псевдонимом для параметра **value** .</span><span class="sxs-lookup"><span data-stu-id="8113b-148">In this example, **Target** is an alias for the **Value** parameter.</span></span> <span data-ttu-id="8113b-149">Целью символьной ссылки может быть относительный путь.</span><span class="sxs-lookup"><span data-stu-id="8113b-149">The target of the symbolic link can be a relative path.</span></span> <span data-ttu-id="8113b-150">До PowerShell версии 6.2 целевой объект должен быть полным путем.</span><span class="sxs-lookup"><span data-stu-id="8113b-150">Prior to PowerShell v6.2, the target must be a fully-qualified path.</span></span>

<span data-ttu-id="8113b-151">Начиная с PowerShell 7,1, теперь можно создать **SymbolicLink** для папки в Windows, используя относительный путь.</span><span class="sxs-lookup"><span data-stu-id="8113b-151">Beginning in PowerShell 7.1, you can now create to a **SymbolicLink** to a folder on Windows using a relative path.</span></span>

### <span data-ttu-id="8113b-152">Пример 8. Использование параметра-Force для попыток повторного создания папок</span><span class="sxs-lookup"><span data-stu-id="8113b-152">Example 8: Use the -Force parameter to attempt to recreate folders</span></span>

<span data-ttu-id="8113b-153">В этом примере создается папка с файлом внутри.</span><span class="sxs-lookup"><span data-stu-id="8113b-153">This example creates a folder with a file inside.</span></span> <span data-ttu-id="8113b-154">Затем пытается создать ту же папку с помощью `-Force` .</span><span class="sxs-lookup"><span data-stu-id="8113b-154">Then, attempts to create the same folder using `-Force`.</span></span> <span data-ttu-id="8113b-155">Она не перезаписывает папку, а просто возвращает существующий объект Folder с нетронутым файлом.</span><span class="sxs-lookup"><span data-stu-id="8113b-155">It will not overwrite the folder but simply return the existing folder object with the file created intact.</span></span>

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

### <span data-ttu-id="8113b-156">Пример 9. Использование параметра-Force для перезаписи существующих файлов</span><span class="sxs-lookup"><span data-stu-id="8113b-156">Example 9: Use the -Force parameter to overwrite existing files</span></span>

<span data-ttu-id="8113b-157">В этом примере создается файл со значением, а затем создается файл повторно с помощью `-Force` .</span><span class="sxs-lookup"><span data-stu-id="8113b-157">This example creates a file with a value and then recreates the file using `-Force`.</span></span> <span data-ttu-id="8113b-158">При этом существующий файл перезаписывается, и его содержимое будет потеряно, как видно в свойстве Length.</span><span class="sxs-lookup"><span data-stu-id="8113b-158">This overwrites The existing file and it will lose it's content as you can see by the length property</span></span>

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
> <span data-ttu-id="8113b-159">При использовании `New-Item` с `-Force` параметром для создания разделов реестра команда будет вести себя так же, как при перезаписи файла.</span><span class="sxs-lookup"><span data-stu-id="8113b-159">When using `New-Item` with the `-Force` switch to create registry keys, the command will behave the same as when overwriting a file.</span></span> <span data-ttu-id="8113b-160">Если раздел реестра уже существует, ключ и все его свойства и значения будут перезаписаны пустым ключом реестра.</span><span class="sxs-lookup"><span data-stu-id="8113b-160">If the registry key already exists, the key and all properties and values will be overwritten with an empty registry key.</span></span>

## <span data-ttu-id="8113b-161">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8113b-161">PARAMETERS</span></span>

### <span data-ttu-id="8113b-162">-Credential</span><span class="sxs-lookup"><span data-stu-id="8113b-162">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="8113b-163">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8113b-163">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="8113b-164">Чтобы олицетворить другого пользователя или повысить свои учетные данные при запуске этого командлета, используйте `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="8113b-164">To impersonate another user or elevate your credentials when running this cmdlet, use `Invoke-Command`.</span></span>

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

### <span data-ttu-id="8113b-165">-Force</span><span class="sxs-lookup"><span data-stu-id="8113b-165">-Force</span></span>

<span data-ttu-id="8113b-166">Заставляет этот командлет создать элемент, записывающий существующий элемент только для чтения.</span><span class="sxs-lookup"><span data-stu-id="8113b-166">Forces this cmdlet to create an item that writes over an existing read-only item.</span></span> <span data-ttu-id="8113b-167">Применение этого параметра зависит от конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="8113b-167">Implementation varies from provider to provider.</span></span> <span data-ttu-id="8113b-168">Даже при использовании параметра **Force** командлет не может переопределять ограничения безопасности.</span><span class="sxs-lookup"><span data-stu-id="8113b-168">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

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

### <span data-ttu-id="8113b-169">-ItemType</span><span class="sxs-lookup"><span data-stu-id="8113b-169">-ItemType</span></span>

<span data-ttu-id="8113b-170">Указывает тип нового элемента, заданный поставщиком.</span><span class="sxs-lookup"><span data-stu-id="8113b-170">Specifies the provider-specified type of the new item.</span></span> <span data-ttu-id="8113b-171">Доступные значения этого параметра зависят от текущего используемого поставщика.</span><span class="sxs-lookup"><span data-stu-id="8113b-171">The available values of this parameter depend on the current provider you are using.</span></span>

<span data-ttu-id="8113b-172">Если расположение находится в `FileSystem` диске, допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="8113b-172">If your location is in a `FileSystem` drive, the following values are allowed:</span></span>

- <span data-ttu-id="8113b-173">Файл</span><span class="sxs-lookup"><span data-stu-id="8113b-173">File</span></span>
- <span data-ttu-id="8113b-174">Каталог</span><span class="sxs-lookup"><span data-stu-id="8113b-174">Directory</span></span>
- <span data-ttu-id="8113b-175">SymbolicLink</span><span class="sxs-lookup"><span data-stu-id="8113b-175">SymbolicLink</span></span>
- <span data-ttu-id="8113b-176">Соединение</span><span class="sxs-lookup"><span data-stu-id="8113b-176">Junction</span></span>
- <span data-ttu-id="8113b-177">HardLink</span><span class="sxs-lookup"><span data-stu-id="8113b-177">HardLink</span></span>

> [!NOTE]
> <span data-ttu-id="8113b-178">Для создания `SymbolicLink` типа в Windows требуется повышение прав от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="8113b-178">Creating a `SymbolicLink` type on Windows requires elevation as administrator.</span></span> <span data-ttu-id="8113b-179">Однако в Windows 10 (сборка 14972 или более новая версия) с включенным режимом разработчика больше не требуется повышение прав на создание символьных ссылок.</span><span class="sxs-lookup"><span data-stu-id="8113b-179">However, Windows 10 (build 14972 or newer) with Developer Mode enabled no longer requires elevation creating symbolic links.</span></span>

<span data-ttu-id="8113b-180">На `Certificate` диске можно указать следующие значения:</span><span class="sxs-lookup"><span data-stu-id="8113b-180">In a `Certificate` drive, these are the values you can specify:</span></span>

- <span data-ttu-id="8113b-181">Поставщик Certificate</span><span class="sxs-lookup"><span data-stu-id="8113b-181">Certificate Provider</span></span>
- <span data-ttu-id="8113b-182">Certificate</span><span class="sxs-lookup"><span data-stu-id="8113b-182">Certificate</span></span>
- <span data-ttu-id="8113b-183">Магазин</span><span class="sxs-lookup"><span data-stu-id="8113b-183">Store</span></span>
- <span data-ttu-id="8113b-184">StoreLocation</span><span class="sxs-lookup"><span data-stu-id="8113b-184">StoreLocation</span></span>

<span data-ttu-id="8113b-185">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="8113b-185">For more information see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="8113b-186">-Name</span><span class="sxs-lookup"><span data-stu-id="8113b-186">-Name</span></span>

<span data-ttu-id="8113b-187">Указывает имя нового элемента.</span><span class="sxs-lookup"><span data-stu-id="8113b-187">Specifies the name of the new item.</span></span> <span data-ttu-id="8113b-188">Можно указать имя нового элемента в значении параметра **Name** или **path** , а также указать путь к новому элементу в значении **имени** или **пути** .</span><span class="sxs-lookup"><span data-stu-id="8113b-188">You can specify the name of the new item in the **Name** or **Path** parameter value, and you can specify the path of the new item in **Name** or **Path** value.</span></span> <span data-ttu-id="8113b-189">Имена элементов, переданных с помощью параметра **Name** , создаются относительно значения параметра **path** .</span><span class="sxs-lookup"><span data-stu-id="8113b-189">Items names passed using the **Name** parameter are created relative to the value of the **Path** parameter.</span></span>

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

### <span data-ttu-id="8113b-190">-Path</span><span class="sxs-lookup"><span data-stu-id="8113b-190">-Path</span></span>

<span data-ttu-id="8113b-191">Указывает путь к расположению нового элемента.</span><span class="sxs-lookup"><span data-stu-id="8113b-191">Specifies the path of the location of the new item.</span></span> <span data-ttu-id="8113b-192">По умолчанию используется текущее расположение, когда **путь** опущен.</span><span class="sxs-lookup"><span data-stu-id="8113b-192">The default is the current location when **Path** is omitted.</span></span> <span data-ttu-id="8113b-193">Можно указать имя нового элемента в **поле имя** или включить его в **путь**.</span><span class="sxs-lookup"><span data-stu-id="8113b-193">You can specify the name of the new item in **Name**, or include it in **Path**.</span></span> <span data-ttu-id="8113b-194">Имена элементов, переданных с помощью параметра **Name** , создаются относительно значения параметра **path** .</span><span class="sxs-lookup"><span data-stu-id="8113b-194">Items names passed using the **Name** parameter are created relative to the value of the **Path** parameter.</span></span>

<span data-ttu-id="8113b-195">Для этого командлета параметр **path** работает как параметр **LiteralPath** других командлетов.</span><span class="sxs-lookup"><span data-stu-id="8113b-195">For this cmdlet, the **Path** parameter works like the **LiteralPath** parameter of other cmdlets.</span></span>
<span data-ttu-id="8113b-196">Символы-шаблоны не обрабатываются.</span><span class="sxs-lookup"><span data-stu-id="8113b-196">Wildcard characters are not interpreted.</span></span> <span data-ttu-id="8113b-197">Все символы передаются поставщику расположения.</span><span class="sxs-lookup"><span data-stu-id="8113b-197">All characters are passed to the location's provider.</span></span> <span data-ttu-id="8113b-198">Поставщик может не поддерживать все символы.</span><span class="sxs-lookup"><span data-stu-id="8113b-198">The provider may not support all characters.</span></span> <span data-ttu-id="8113b-199">Например, нельзя создать имя файла, содержащее символ звездочки ( `*` ).</span><span class="sxs-lookup"><span data-stu-id="8113b-199">For example, you cannot create a filename that contains an asterisk (`*`) character.</span></span>

```yaml
Type: System.String[]
Parameter Sets: pathSet
Aliases:

Required: True (pathSet), False (nameSet)
Position: 0
Default value: Current location
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8113b-200">-Value</span><span class="sxs-lookup"><span data-stu-id="8113b-200">-Value</span></span>

<span data-ttu-id="8113b-201">Указывает значение нового элемента.</span><span class="sxs-lookup"><span data-stu-id="8113b-201">Specifies the value of the new item.</span></span> <span data-ttu-id="8113b-202">Можно также передать значение в `New-Item` .</span><span class="sxs-lookup"><span data-stu-id="8113b-202">You can also pipe a value to `New-Item`.</span></span>

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

### <span data-ttu-id="8113b-203">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8113b-203">-Confirm</span></span>

<span data-ttu-id="8113b-204">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="8113b-204">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="8113b-205">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8113b-205">-WhatIf</span></span>

<span data-ttu-id="8113b-206">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="8113b-206">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="8113b-207">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="8113b-207">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="8113b-208">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="8113b-208">CommonParameters</span></span>

<span data-ttu-id="8113b-209">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="8113b-209">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="8113b-210">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="8113b-210">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="8113b-211">Входные данные</span><span class="sxs-lookup"><span data-stu-id="8113b-211">INPUTS</span></span>

### <span data-ttu-id="8113b-212">System.Object</span><span class="sxs-lookup"><span data-stu-id="8113b-212">System.Object</span></span>

<span data-ttu-id="8113b-213">В этот командлет можно передать значение для нового элемента.</span><span class="sxs-lookup"><span data-stu-id="8113b-213">You can pipe a value for the new item to this cmdlet.</span></span>

## <span data-ttu-id="8113b-214">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="8113b-214">OUTPUTS</span></span>

### <span data-ttu-id="8113b-215">System.Object</span><span class="sxs-lookup"><span data-stu-id="8113b-215">System.Object</span></span>

<span data-ttu-id="8113b-216">Этот командлет возвращает элемент, который он создает.</span><span class="sxs-lookup"><span data-stu-id="8113b-216">This cmdlet returns the item that it creates.</span></span>

## <span data-ttu-id="8113b-217">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="8113b-217">NOTES</span></span>

<span data-ttu-id="8113b-218">`New-Item` предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="8113b-218">`New-Item` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="8113b-219">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PsProvider`.</span><span class="sxs-lookup"><span data-stu-id="8113b-219">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="8113b-220">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="8113b-220">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="8113b-221">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="8113b-221">RELATED LINKS</span></span>

[<span data-ttu-id="8113b-222">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="8113b-222">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="8113b-223">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="8113b-223">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="8113b-224">Get-Item</span><span class="sxs-lookup"><span data-stu-id="8113b-224">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="8113b-225">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="8113b-225">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="8113b-226">Move-Item</span><span class="sxs-lookup"><span data-stu-id="8113b-226">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="8113b-227">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="8113b-227">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="8113b-228">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="8113b-228">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="8113b-229">Set-Item</span><span class="sxs-lookup"><span data-stu-id="8113b-229">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="8113b-230">about_Providers</span><span class="sxs-lookup"><span data-stu-id="8113b-230">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

