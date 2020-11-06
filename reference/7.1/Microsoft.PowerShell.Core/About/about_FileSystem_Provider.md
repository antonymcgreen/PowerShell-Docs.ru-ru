---
description: FileSystem
keywords: powershell,командлет
Locale: en-US
ms.date: 06/18/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_filesystem_provider?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Поставщик FileSystem
ms.openlocfilehash: 8407dd11c3c9ead10b081b937fbac3db82735eb3
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231138"
---
# <a name="filesystem-provider"></a><span data-ttu-id="bd58e-104">Поставщик FileSystem</span><span class="sxs-lookup"><span data-stu-id="bd58e-104">FileSystem provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="bd58e-105">Имя поставщика</span><span class="sxs-lookup"><span data-stu-id="bd58e-105">Provider name</span></span>
<span data-ttu-id="bd58e-106">FileSystem</span><span class="sxs-lookup"><span data-stu-id="bd58e-106">FileSystem</span></span>

## <a name="drives"></a><span data-ttu-id="bd58e-107">Диски</span><span class="sxs-lookup"><span data-stu-id="bd58e-107">Drives</span></span>

<span data-ttu-id="bd58e-108">`C:`, `D:` ...</span><span class="sxs-lookup"><span data-stu-id="bd58e-108">`C:`, `D:` ...</span></span>

## <a name="capabilities"></a><span data-ttu-id="bd58e-109">Характеристики</span><span class="sxs-lookup"><span data-stu-id="bd58e-109">Capabilities</span></span>

<span data-ttu-id="bd58e-110">**Filter** , **ShouldProcess**</span><span class="sxs-lookup"><span data-stu-id="bd58e-110">**Filter** , **ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="bd58e-111">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="bd58e-111">Short description</span></span>

<span data-ttu-id="bd58e-112">Предоставляет доступ к файлам и каталогам.</span><span class="sxs-lookup"><span data-stu-id="bd58e-112">Provides access to files and directories.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="bd58e-113">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="bd58e-113">Detailed description</span></span>

<span data-ttu-id="bd58e-114">Поставщик **файловой** системы PowerShell позволяет получать, добавлять, изменять, очищать и удалять файлы и каталоги в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd58e-114">The PowerShell **FileSystem** provider lets you get, add, change, clear, and delete files and directories in PowerShell.</span></span>

<span data-ttu-id="bd58e-115">Диски **файловой** системы — это иерархическое пространство имен, содержащее каталоги и файлы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="bd58e-115">The **FileSystem** drives are a hierarchical namespace containing the directories and files on your computer.</span></span> <span data-ttu-id="bd58e-116">Диск **файловой** системы может быть логическим или физических диском, каталогом или сопоставленной сетевой папкой.</span><span class="sxs-lookup"><span data-stu-id="bd58e-116">A **FileSystem** drive can be a logical or phsyical drive, directory, or mapped network share.</span></span>

<span data-ttu-id="bd58e-117">Диск с именем `TEMP:` будет сопоставлен с путем к временному каталогу пользователя.</span><span class="sxs-lookup"><span data-stu-id="bd58e-117">A drive called `TEMP:` will be mapped to the user's temporary directory path.</span></span>

>[!NOTE]
> <span data-ttu-id="bd58e-118">Содержимое на диске TEMP: не удаляется автоматически с помощью PowerShell и не может управляться пользователем или операционной системой.</span><span class="sxs-lookup"><span data-stu-id="bd58e-118">Contents in the TEMP: drive are not automatically removed by PowerShell and is up to the user or operating system to manage.</span></span>

<span data-ttu-id="bd58e-119">Поставщик **FileSystem** поддерживает следующие командлеты, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="bd58e-119">The **FileSystem** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="bd58e-120">Get-Location</span><span class="sxs-lookup"><span data-stu-id="bd58e-120">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="bd58e-121">Set-Location</span><span class="sxs-lookup"><span data-stu-id="bd58e-121">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="bd58e-122">Get-Item</span><span class="sxs-lookup"><span data-stu-id="bd58e-122">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="bd58e-123">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="bd58e-123">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [<span data-ttu-id="bd58e-124">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="bd58e-124">Invoke-Item</span></span>](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [<span data-ttu-id="bd58e-125">Move-Item</span><span class="sxs-lookup"><span data-stu-id="bd58e-125">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="bd58e-126">New-Item</span><span class="sxs-lookup"><span data-stu-id="bd58e-126">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="bd58e-127">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="bd58e-127">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="bd58e-128">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="bd58e-128">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="bd58e-129">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="bd58e-129">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [<span data-ttu-id="bd58e-130">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="bd58e-130">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)
- [<span data-ttu-id="bd58e-131">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="bd58e-131">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [<span data-ttu-id="bd58e-132">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="bd58e-132">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="bd58e-133">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="bd58e-133">Remove-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)
- [<span data-ttu-id="bd58e-134">Get-Acl</span><span class="sxs-lookup"><span data-stu-id="bd58e-134">Get-Acl</span></span>](xref:Microsoft.PowerShell.Security.Get-Acl)
- [<span data-ttu-id="bd58e-135">Set-Acl</span><span class="sxs-lookup"><span data-stu-id="bd58e-135">Set-Acl</span></span>](xref:Microsoft.PowerShell.Security.Set-Acl)
- [<span data-ttu-id="bd58e-136">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="bd58e-136">Get-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Get-AuthenticodeSignature)
- [<span data-ttu-id="bd58e-137">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="bd58e-137">Set-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="bd58e-138">Типы, предоставляемые этим поставщиком</span><span class="sxs-lookup"><span data-stu-id="bd58e-138">Types exposed by this provider</span></span>

<span data-ttu-id="bd58e-139">Файлы являются экземплярами класса [System. IO. FileInfo](/dotnet/api/system.io.fileinfo) .</span><span class="sxs-lookup"><span data-stu-id="bd58e-139">Files are instances of the [System.IO.FileInfo](/dotnet/api/system.io.fileinfo) class.</span></span>  <span data-ttu-id="bd58e-140">Каталоги являются экземплярами класса [System. IO. DirectoryInfo](/dotnet/api/system.io.directoryinfo) .</span><span class="sxs-lookup"><span data-stu-id="bd58e-140">Directories are instances of the [System.IO.DirectoryInfo](/dotnet/api/system.io.directoryinfo) class.</span></span>

## <a name="navigating-the-filesystem-drives"></a><span data-ttu-id="bd58e-141">Навигация по дискам файловой системы</span><span class="sxs-lookup"><span data-stu-id="bd58e-141">Navigating the FileSystem drives</span></span>

<span data-ttu-id="bd58e-142">Поставщик **FileSystem** предоставляет свои хранилища данных путем сопоставления логических дисков на компьютере с дисками PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd58e-142">The **FileSystem** provider exposes its data stores by mapping any logical drives on the computer as PowerShell drives.</span></span> <span data-ttu-id="bd58e-143">Для работы с диском **файловой** системы можно изменить расположение на диск, выдающие имя диска, за которым следует двоеточие ( `:` ).</span><span class="sxs-lookup"><span data-stu-id="bd58e-143">To work with a **FileSystem** drive you can change your location to a drive uing the drive name followed by a colon (`:`).</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="bd58e-144">Вы также можете работать с поставщиком **FileSystem** с любого другого диска PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd58e-144">You can also work with the **FileSystem** provider from any other PowerShell drive.</span></span> <span data-ttu-id="bd58e-145">Чтобы сослаться на файл или каталог из другого расположения, используйте имя диска ( `C:` , `D:` ,...) в пути.</span><span class="sxs-lookup"><span data-stu-id="bd58e-145">To reference a file or directory from another location, use the drive name (`C:`, `D:`, ...) in the path.</span></span>

> [!NOTE]
> <span data-ttu-id="bd58e-146">PowerShell использует Псевдонимы для предоставления привычного способа работы с путями поставщика.</span><span class="sxs-lookup"><span data-stu-id="bd58e-146">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="bd58e-147">Команды, такие как `dir` и `ls` , теперь являются псевдонимами для [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` являются псевдонимом для [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span><span class="sxs-lookup"><span data-stu-id="bd58e-147">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span> <span data-ttu-id="bd58e-148">и `pwd` — это псевдоним для [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span><span class="sxs-lookup"><span data-stu-id="bd58e-148">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

## <a name="getting-files-and-directories"></a><span data-ttu-id="bd58e-149">Получение файлов и каталогов</span><span class="sxs-lookup"><span data-stu-id="bd58e-149">Getting files and directories</span></span>

<span data-ttu-id="bd58e-150">`Get-ChildItem`Командлет возвращает все файлы и каталоги в текущем расположении.</span><span class="sxs-lookup"><span data-stu-id="bd58e-150">The `Get-ChildItem` cmdlet returns all files and directories in the current location.</span></span> <span data-ttu-id="bd58e-151">Можно указать другой путь для поиска и использовать встроенные параметры для фильтрации и управления глубиной рекурсии.</span><span class="sxs-lookup"><span data-stu-id="bd58e-151">You can specify a different path to search and use built in parameters to filter and control the recursion depth.</span></span>

```powershell
Get-ChildItem
```

<span data-ttu-id="bd58e-152">Дополнительные сведения об использовании командлетов см. в статье [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem).</span><span class="sxs-lookup"><span data-stu-id="bd58e-152">To read more about cmdlet usage, see [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem).</span></span>

## <a name="copying-files-and-directories"></a><span data-ttu-id="bd58e-153">Копирование файлов и каталогов</span><span class="sxs-lookup"><span data-stu-id="bd58e-153">Copying files and directories</span></span>

<span data-ttu-id="bd58e-154">`Copy-Item`Командлет копирует файлы и каталоги в указанное расположение.</span><span class="sxs-lookup"><span data-stu-id="bd58e-154">The `Copy-Item` cmdlet copies files and directories to a location you specify.</span></span>
<span data-ttu-id="bd58e-155">Параметры можно использовать для фильтрации и рекурсии, аналогично `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="bd58e-155">Parameters are available to filter and recurse, similar to `Get-ChildItem`.</span></span>

<span data-ttu-id="bd58e-156">Следующая команда копирует все файлы и каталоги по пути "C:\temp" \" в папку "Папка c:\Windows\Temp".</span><span class="sxs-lookup"><span data-stu-id="bd58e-156">The following command copies all of the files and directories under the path "C:\temp\" to the folder "C:\Windows\Temp".</span></span>

```powershell
Copy-Item -Path C:\temp\* -Destination C:\Windows\Temp -Recurse -File
```

<span data-ttu-id="bd58e-157">`Copy-Item` перезаписывает файлы в целевом каталоге без запроса подтверждения.</span><span class="sxs-lookup"><span data-stu-id="bd58e-157">`Copy-Item` overwrites files in the destination directory without prompting for confirmation.</span></span>

<span data-ttu-id="bd58e-158">Эта команда копирует `a.txt` файл из `C:\a` каталога в `C:\a\bb` каталог.</span><span class="sxs-lookup"><span data-stu-id="bd58e-158">This command copies the `a.txt` file from the `C:\a` directory to the `C:\a\bb` directory.</span></span>

```powershell
Copy-Item -Path C:\a\a.txt -Destination C:\a\bb\a.txt
```

<span data-ttu-id="bd58e-159">Копирует все каталоги и файлы из каталога в `C:\a` `C:\c` каталог.</span><span class="sxs-lookup"><span data-stu-id="bd58e-159">Copies all the directories and files in the `C:\a` directory to the `C:\c` directory.</span></span> <span data-ttu-id="bd58e-160">Если какие-либо копируемые каталоги уже существуют в целевом каталоге, то команда завершится с ошибкой, если не указан параметр Force.</span><span class="sxs-lookup"><span data-stu-id="bd58e-160">If any of the directories to copy already exist in the destination directory, the command will fail unless you specify the Force parameter.</span></span>

```powershell
Copy-Item -Path C:\a\* -Destination C:\c -Recurse
```

<span data-ttu-id="bd58e-161">Дополнительные сведения см. в разделе [Copy-Item](xref:Microsoft.PowerShell.Management.Copy-Item).</span><span class="sxs-lookup"><span data-stu-id="bd58e-161">For more information, see [Copy-Item](xref:Microsoft.PowerShell.Management.Copy-Item).</span></span>

## <a name="moving-files-and-directories"></a><span data-ttu-id="bd58e-162">Перемещение файлов и каталогов</span><span class="sxs-lookup"><span data-stu-id="bd58e-162">Moving files and directories</span></span>

<span data-ttu-id="bd58e-163">Эта команда перемещает `c.txt` файл в `C:\a` каталог в `C:\a\aa` Каталог:</span><span class="sxs-lookup"><span data-stu-id="bd58e-163">This command moves the `c.txt` file in the `C:\a` directory to the `C:\a\aa` directory:</span></span>

```powershell
Move-Item -Path C:\a\c.txt -Destination C:\a\aa
```

<span data-ttu-id="bd58e-164">Команда не перезапишет автоматически существующий файл с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="bd58e-164">The command will not automatically overwrite an existing file that has the same name.</span></span> <span data-ttu-id="bd58e-165">Для принудительной перезаписи существующего файла необходимо задать параметр Force.</span><span class="sxs-lookup"><span data-stu-id="bd58e-165">To force the cmdlet to overwrite an existing file, specify the Force parameter.</span></span>

<span data-ttu-id="bd58e-166">Нельзя перемещать каталог, если он совпадает с текущим местоположением.</span><span class="sxs-lookup"><span data-stu-id="bd58e-166">You cannot move a directory when that directory is the current location.</span></span> <span data-ttu-id="bd58e-167">При использовании `Move-Item` для перемещения каталога в текущем расположении отображается эта ошибка.</span><span class="sxs-lookup"><span data-stu-id="bd58e-167">When you use `Move-Item` to move the directory at the current location, you see this error.</span></span>

```
C:\temp> Move-Item -Path C:\temp\ -Destination C:\Windows\Temp

Move-Item : Cannot move item because the item at 'C:\temp\' is in use.
At line:1 char:1
+ Move-Item C:\temp\ C:\temp2\
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [Move-Item], PSInvalidOperationException
    + FullyQualifiedErrorId : InvalidOperation,Microsoft.PowerShell.Commands.MoveItemCommand
```

## <a name="managing-file-content"></a><span data-ttu-id="bd58e-168">Управление содержимым файлов</span><span class="sxs-lookup"><span data-stu-id="bd58e-168">Managing file content</span></span>

### <a name="get-the-content-of-a-file"></a><span data-ttu-id="bd58e-169">Получение содержимого файла</span><span class="sxs-lookup"><span data-stu-id="bd58e-169">Get the content of a file</span></span>

<span data-ttu-id="bd58e-170">Эта команда возвращает содержимое файла "Test.txt" и отображает их в консоли.</span><span class="sxs-lookup"><span data-stu-id="bd58e-170">This command gets the contents of the "Test.txt" file and displays them in the console.</span></span>

```powershell
Get-Content -Path Test.txt
```

<span data-ttu-id="bd58e-171">Содержимое файла можно передать другому командлету по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="bd58e-171">You can pipe the contents of the file to another cmdlet.</span></span> <span data-ttu-id="bd58e-172">Например, следующая команда считывает содержимое `Test.txt` файла и затем передает его в качестве входных данных командлету [ConvertTo-HTML](xref:Microsoft.PowerShell.Utility.ConvertTo-Html) :</span><span class="sxs-lookup"><span data-stu-id="bd58e-172">For example, the following command reads the contents of the `Test.txt` file and then supplies them as input to the [ConvertTo-Html](xref:Microsoft.PowerShell.Utility.ConvertTo-Html) cmdlet:</span></span>

```powershell
Get-Content -Path Test.txt | ConvertTo-Html
```

<span data-ttu-id="bd58e-173">Можно также получить содержимое файла, указав в качестве пути к нему знак доллара ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="bd58e-173">You can also retrieve the content of a file by prefixing its provider path with the dollar sign (`$`).</span></span> <span data-ttu-id="bd58e-174">Путь должен быть заключен в фигурные скобки из-за ограничений именования переменных.</span><span class="sxs-lookup"><span data-stu-id="bd58e-174">The path must be enclosed in curly braces due to variable naming restrictions.</span></span> <span data-ttu-id="bd58e-175">Дополнительные сведения см. в разделе [about_Variables](about_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="bd58e-175">For more information, see [about_Variables](about_Variables.md).</span></span>

```powershell
${C:\Windows\System32\Drivers\etc\hosts}
```

### <a name="add-content-to-a-file"></a><span data-ttu-id="bd58e-176">Добавление содержимого в файл</span><span class="sxs-lookup"><span data-stu-id="bd58e-176">Add content to a file</span></span>

<span data-ttu-id="bd58e-177">Эта команда добавляет строку "тестовое содержимое" в `Test.txt` файл:</span><span class="sxs-lookup"><span data-stu-id="bd58e-177">This command appends the "test content" string to the `Test.txt` file:</span></span>

```powershell
Add-Content -Path test.txt -Value "test content"
```

<span data-ttu-id="bd58e-178">Существующее содержимое в `Test.txt` файле не удаляется.</span><span class="sxs-lookup"><span data-stu-id="bd58e-178">The existing content in the `Test.txt` file is not deleted.</span></span>

### <a name="replace-the-content-of-a-file"></a><span data-ttu-id="bd58e-179">Замена содержимого файла</span><span class="sxs-lookup"><span data-stu-id="bd58e-179">Replace the content of a file</span></span>

<span data-ttu-id="bd58e-180">Эта команда заменяет содержимое `Test.txt` файла строкой "Test Content":</span><span class="sxs-lookup"><span data-stu-id="bd58e-180">This command replaces the contents of the `Test.txt` file with the "test content" string:</span></span>

```powershell
Set-Content -Path test.txt -Value "test content"
```

<span data-ttu-id="bd58e-181">Он перезаписывает содержимое `Test.txt` .</span><span class="sxs-lookup"><span data-stu-id="bd58e-181">It overwrites the contents of `Test.txt`.</span></span> <span data-ttu-id="bd58e-182">Можно использовать параметр **value** командлета [New-Item](xref:Microsoft.PowerShell.Management.New-Item) , чтобы добавить содержимое в файл при его создании.</span><span class="sxs-lookup"><span data-stu-id="bd58e-182">You can use the **Value** parameter of the [New-Item](xref:Microsoft.PowerShell.Management.New-Item) cmdlet to add content to a file when you create it.</span></span>

### <a name="loop-through-the-contents-of-a-file"></a><span data-ttu-id="bd58e-183">Перебрать содержимое файла</span><span class="sxs-lookup"><span data-stu-id="bd58e-183">Loop through the contents of a file</span></span>

<span data-ttu-id="bd58e-184">По умолчанию `Get-Content` командлет использует символ конца строки в качестве разделителя, поэтому он получает файл в виде коллекции строк, каждая из которых имеет одну строку в файле.</span><span class="sxs-lookup"><span data-stu-id="bd58e-184">By default, the `Get-Content` cmdlet uses the end-of-line character as its delimiter, so it gets a file as a collection of strings, with each line as one string in the file.</span></span>

<span data-ttu-id="bd58e-185">С помощью параметра можно `-Delimiter` указать альтернативный разделитель.</span><span class="sxs-lookup"><span data-stu-id="bd58e-185">You can use the `-Delimiter` parameter to specify an alternate delimiter.</span></span> <span data-ttu-id="bd58e-186">Если в качестве его значения будут заданы символы, обозначающие конец раздела или начало следующего раздела, файл можно будет разделить на логические части.</span><span class="sxs-lookup"><span data-stu-id="bd58e-186">If you set it to the characters that denote the end of a section or the beginning of the next section, you can split the file into logical parts.</span></span>

<span data-ttu-id="bd58e-187">Первая команда получает `Employees.txt` файл и разделяет его на разделы, каждый из которых заканчивается словами "конец записи о сотруднике", и сохраняет его в `$e` переменной.</span><span class="sxs-lookup"><span data-stu-id="bd58e-187">The first command gets the `Employees.txt` file and splits it into sections, each of which ends with the words "End of Employee Record" and it saves it in the `$e` variable.</span></span>

<span data-ttu-id="bd58e-188">Вторая команда использует нотацию массива для получения первого элемента в коллекции в `$e` .</span><span class="sxs-lookup"><span data-stu-id="bd58e-188">The second command uses array notation to get the first item in the collection in `$e`.</span></span> <span data-ttu-id="bd58e-189">Он использует индекс 0, так как массивы PowerShell отсчитываются от нуля.</span><span class="sxs-lookup"><span data-stu-id="bd58e-189">It uses an index of 0, because PowerShell arrays are zero-based.</span></span>

<span data-ttu-id="bd58e-190">Дополнительные сведения о `Get-Content` командлете см. в разделе справки по разделу [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content).</span><span class="sxs-lookup"><span data-stu-id="bd58e-190">For more information about `Get-Content` cmdlet, see the help topic for the [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content).</span></span>

<span data-ttu-id="bd58e-191">Дополнительные сведения о массивах см. в разделе [about_Arrays](../About/about_Arrays.md).</span><span class="sxs-lookup"><span data-stu-id="bd58e-191">For more information about arrays, see [about_Arrays](../About/about_Arrays.md).</span></span>

```powershell
$e = Get-Content c:\test\employees.txt -Delimited "End Of Employee Record"
$e[0]
```

## <a name="managing-security-descriptors"></a><span data-ttu-id="bd58e-192">Управление дескрипторами безопасности</span><span class="sxs-lookup"><span data-stu-id="bd58e-192">Managing security descriptors</span></span>

### <a name="view-the-acl-for-a-file"></a><span data-ttu-id="bd58e-193">Просмотр списка ACL для файла</span><span class="sxs-lookup"><span data-stu-id="bd58e-193">View the ACL for a file</span></span>

<span data-ttu-id="bd58e-194">Эта команда возвращает объект [System. Security. AccessControl. FileSecurity](/dotnet/api/system.security.accesscontrol.filesecurity) :</span><span class="sxs-lookup"><span data-stu-id="bd58e-194">This command returns a [System.Security.AccessControl.FileSecurity](/dotnet/api/system.security.accesscontrol.filesecurity) object:</span></span>

```powershell
Get-Acl -Path test.txt | Format-List -Property *
```

<span data-ttu-id="bd58e-195">Чтобы получить дополнительные сведения об этом объекте, передайте команду в командлет [Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member) по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="bd58e-195">For more information about this object, pipe the command to the [Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member) cmdlet.</span></span> <span data-ttu-id="bd58e-196">Или см. раздел "класс[FileSecurity](/dotnet/api/system.security.accesscontrol.filesecurity) " в библиотеке MSDN (сеть разработчиков Microsoft Developer).</span><span class="sxs-lookup"><span data-stu-id="bd58e-196">Or, see "[FileSecurity](/dotnet/api/system.security.accesscontrol.filesecurity) Class" in the MSDN (Microsoft Developer Network) library.</span></span>

### <a name="modify-the-acl-for-a-file"></a><span data-ttu-id="bd58e-197">Изменение ACL для файла</span><span class="sxs-lookup"><span data-stu-id="bd58e-197">Modify the ACL for a file</span></span>

### <a name="create-and-set-an-acl-for-a-file"></a><span data-ttu-id="bd58e-198">Создание и задание списка управления доступом для файла</span><span class="sxs-lookup"><span data-stu-id="bd58e-198">Create and set an ACL for a file</span></span>

## <a name="creating-files-and-directories"></a><span data-ttu-id="bd58e-199">Создание файлов и каталогов</span><span class="sxs-lookup"><span data-stu-id="bd58e-199">Creating files and directories</span></span>

### <a name="create-a-directory"></a><span data-ttu-id="bd58e-200">Создание каталога</span><span class="sxs-lookup"><span data-stu-id="bd58e-200">Create a directory</span></span>

<span data-ttu-id="bd58e-201">Эта команда создает `logfiles` каталог на `C` диске:</span><span class="sxs-lookup"><span data-stu-id="bd58e-201">This command creates the `logfiles` directory on the `C` drive:</span></span>

```powershell
New-Item -Path c:\ -Name logfiles -Type directory
```

<span data-ttu-id="bd58e-202">PowerShell также включает `mkdir` функцию (псевдоним `md` ), которая использует командлет [New-Item](xref:Microsoft.PowerShell.Management.New-Item) для создания нового каталога.</span><span class="sxs-lookup"><span data-stu-id="bd58e-202">PowerShell also includes a `mkdir` function (alias `md`) that uses the [New-Item](xref:Microsoft.PowerShell.Management.New-Item) cmdlet to create a new directory.</span></span>

### <a name="create-a-file"></a><span data-ttu-id="bd58e-203">Создание файла</span><span class="sxs-lookup"><span data-stu-id="bd58e-203">Create a file</span></span>

<span data-ttu-id="bd58e-204">Эта команда создает `log2.txt` файл в `C:\logfiles` каталоге, а затем добавляет в файл строку "Журнал теста":</span><span class="sxs-lookup"><span data-stu-id="bd58e-204">This command creates the `log2.txt` file in the `C:\logfiles` directory and then adds the "test log" string to the file:</span></span>

```powershell
New-Item -Path c:\logfiles -Name log2.txt -Type file
```

### <a name="create-a-file-with-content"></a><span data-ttu-id="bd58e-205">Создание файла с содержимым</span><span class="sxs-lookup"><span data-stu-id="bd58e-205">Create a file with content</span></span>

<span data-ttu-id="bd58e-206">Создает файл с именем `log2.txt` в `C:\logfiles` каталоге и добавляет в файл строку "тестовый журнал".</span><span class="sxs-lookup"><span data-stu-id="bd58e-206">Creates a file called `log2.txt` in the `C:\logfiles` directory and adds the string "test log" to the file.</span></span>

```powershell
New-Item -Path c:\logfiles -Name log2.txt -Type file -Value "test log"
```

## <a name="renaming-files-and-directories"></a><span data-ttu-id="bd58e-207">Переименование файлов и каталогов</span><span class="sxs-lookup"><span data-stu-id="bd58e-207">Renaming files and directories</span></span>

### <a name="rename-a-file"></a><span data-ttu-id="bd58e-208">Переименование файла</span><span class="sxs-lookup"><span data-stu-id="bd58e-208">Rename a file</span></span>

<span data-ttu-id="bd58e-209">Эта команда переименовывает `a.txt` файл в `C:\a` каталоге `b.txt` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="bd58e-209">This command renames the `a.txt` file in the `C:\a` directory to `b.txt`:</span></span>

```powershell
Rename-Item -Path c:\a\a.txt -NewName b.txt
```

### <a name="rename-a-directory"></a><span data-ttu-id="bd58e-210">Переименование каталога</span><span class="sxs-lookup"><span data-stu-id="bd58e-210">Rename a directory</span></span>

<span data-ttu-id="bd58e-211">Эта команда переименовывает `C:\a\cc` каталог в `C:\a\dd` :</span><span class="sxs-lookup"><span data-stu-id="bd58e-211">This command renames the `C:\a\cc` directory to `C:\a\dd`:</span></span>

```powershell
Rename-Item -Path c:\a\cc -NewName dd
```

## <a name="deleting-files-and-directories"></a><span data-ttu-id="bd58e-212">Удаление файлов и каталогов</span><span class="sxs-lookup"><span data-stu-id="bd58e-212">Deleting files and directories</span></span>

### <a name="delete-a-file"></a><span data-ttu-id="bd58e-213">Удаление файла</span><span class="sxs-lookup"><span data-stu-id="bd58e-213">Delete a file</span></span>

<span data-ttu-id="bd58e-214">Эта команда удаляет `Test.txt` файл в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="bd58e-214">This command deletes the `Test.txt` file in the current directory:</span></span>

```powershell
Remove-Item -Path test.txt
```

### <a name="delete-files-using-wildcards"></a><span data-ttu-id="bd58e-215">Удаление файлов с помощью подстановочных знаков</span><span class="sxs-lookup"><span data-stu-id="bd58e-215">Delete files using wildcards</span></span>

<span data-ttu-id="bd58e-216">Эта команда удаляет все файлы в текущем каталоге с `.xml` расширением имени файла:</span><span class="sxs-lookup"><span data-stu-id="bd58e-216">This command deletes all the files in the current directory that have the `.xml` file name extension:</span></span>

```powershell
Remove-Item -Path *.xml
```

## <a name="starting-a-program-by-invoking-an-associated-file"></a><span data-ttu-id="bd58e-217">Запуск программы путем вызова связанного файла</span><span class="sxs-lookup"><span data-stu-id="bd58e-217">Starting a program by invoking an associated file</span></span>

### <a name="invoke-a-file"></a><span data-ttu-id="bd58e-218">Вызов файла</span><span class="sxs-lookup"><span data-stu-id="bd58e-218">Invoke a file</span></span>

<span data-ttu-id="bd58e-219">Первая команда использует командлет [Get-Service](xref:Microsoft.PowerShell.Management.Get-Service) для получения сведений о локальных службах.</span><span class="sxs-lookup"><span data-stu-id="bd58e-219">The first command uses the [Get-Service](xref:Microsoft.PowerShell.Management.Get-Service) cmdlet to get information about local services.</span></span>

<span data-ttu-id="bd58e-220">Он передает сведения в командлет [Export-CSV](xref:Microsoft.PowerShell.Utility.Export-Csv) , а затем сохраняет эти сведения в `Services.csv` файле.</span><span class="sxs-lookup"><span data-stu-id="bd58e-220">It pipes the information to the [Export-Csv](xref:Microsoft.PowerShell.Utility.Export-Csv) cmdlet and then stores that information in the `Services.csv` file.</span></span>

<span data-ttu-id="bd58e-221">Вторая команда использует [Invoke-Item](xref:Microsoft.PowerShell.Management.Invoke-Item) для открытия `services.csv` файла в программе, связанной с `.csv` расширением:</span><span class="sxs-lookup"><span data-stu-id="bd58e-221">The second command uses [Invoke-Item](xref:Microsoft.PowerShell.Management.Invoke-Item) to open the `services.csv` file in the program associated with the `.csv` extension:</span></span>

```powershell
Get-Service | Export-Csv -Path services.csv
Invoke-Item -Path services.csv
```

## <a name="getting-files-and-folders-with-specified-attributes"></a><span data-ttu-id="bd58e-222">Получение файлов и папок с указанными атрибутами</span><span class="sxs-lookup"><span data-stu-id="bd58e-222">Getting files and folders with specified attributes</span></span>

### <a name="get-system-files"></a><span data-ttu-id="bd58e-223">Получение системных файлов</span><span class="sxs-lookup"><span data-stu-id="bd58e-223">Get System files</span></span>

<span data-ttu-id="bd58e-224">Эта команда возвращает системные файлы в текущем каталоге и его подкаталогах.</span><span class="sxs-lookup"><span data-stu-id="bd58e-224">This command gets system files in the current directory and its subdirectories.</span></span>

<span data-ttu-id="bd58e-225">Он использует `-File` параметр для получения только файлов (не каталогов) и `-System` параметр для получения только элементов с атрибутом System.</span><span class="sxs-lookup"><span data-stu-id="bd58e-225">It uses the `-File` parameter to get only files (not directories) and the `-System` parameter to get only items with the "system" attribute.</span></span>

<span data-ttu-id="bd58e-226">Он использует `-Recurse` параметр для получения элементов в текущем каталоге и всех подкаталогах.</span><span class="sxs-lookup"><span data-stu-id="bd58e-226">It uses the `-Recurse` parameter to get the items in the current directory and all subdirectories.</span></span>

```powershell
Get-ChildItem -File -System -Recurse
```

### <a name="get-hidden-files"></a><span data-ttu-id="bd58e-227">Получение скрытых файлов</span><span class="sxs-lookup"><span data-stu-id="bd58e-227">Get Hidden files</span></span>

<span data-ttu-id="bd58e-228">Эта команда возвращает все файлы, включая скрытые файлы, в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="bd58e-228">This command gets all files, including hidden files, in the current directory.</span></span>

<span data-ttu-id="bd58e-229">В нем используется параметр **Attributes** с двумя значениями, `!Directory+Hidden` , который получает скрытые файлы, и `!Directory` , который получает все остальные файлы.</span><span class="sxs-lookup"><span data-stu-id="bd58e-229">It uses the **Attributes** parameter with two values, `!Directory+Hidden`, which gets hidden files, and `!Directory`, which gets all other files.</span></span>

```powershell
Get-ChildItem -Attributes !Directory,!Directory+Hidden
```

<span data-ttu-id="bd58e-230">`dir -att !d,!d+h` эквивалентна этой команде.</span><span class="sxs-lookup"><span data-stu-id="bd58e-230">`dir -att !d,!d+h` is the equivalent of this command.</span></span>

### <a name="get-compressed-and-encrypted-files"></a><span data-ttu-id="bd58e-231">Получение сжатых и зашифрованных файлов</span><span class="sxs-lookup"><span data-stu-id="bd58e-231">Get Compressed and Encrypted files</span></span>

<span data-ttu-id="bd58e-232">Эта команда возвращает файлы в текущем каталоге, которые сжаты или зашифрованы.</span><span class="sxs-lookup"><span data-stu-id="bd58e-232">This command gets files in the current directory that are either compressed or encrypted.</span></span>

<span data-ttu-id="bd58e-233">Он использует `-Attributes` параметр с двумя значениями `Compressed` и `Encrypted` .</span><span class="sxs-lookup"><span data-stu-id="bd58e-233">It uses the `-Attributes` parameter with two values, `Compressed` and `Encrypted`.</span></span> <span data-ttu-id="bd58e-234">Значения разделяются запятой, `,` которая представляет оператор "или".</span><span class="sxs-lookup"><span data-stu-id="bd58e-234">The values are separated by a comma `,` which represents the "OR" operator.</span></span>

```powershell
Get-ChildItem -Attributes Compressed,Encrypted
```

## <a name="dynamic-parameters"></a><span data-ttu-id="bd58e-235">Динамические параметры</span><span class="sxs-lookup"><span data-stu-id="bd58e-235">Dynamic parameters</span></span>

<span data-ttu-id="bd58e-236">Динамические параметры — это параметры командлета, которые добавляются поставщиком PowerShell и доступны только при использовании командлета на диске с поддержкой поставщика.</span><span class="sxs-lookup"><span data-stu-id="bd58e-236">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span>

### <a name="encoding-microsoftpowershellcommandsfilesystemcmdletproviderencoding"></a><span data-ttu-id="bd58e-237">Encoding \<Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding\></span><span class="sxs-lookup"><span data-stu-id="bd58e-237">Encoding \<Microsoft.PowerShell.Commands.FileSystemCmdletProviderEncoding\></span></span>

<span data-ttu-id="bd58e-238">Указывает кодировку файла.</span><span class="sxs-lookup"><span data-stu-id="bd58e-238">Specifies the file encoding.</span></span> <span data-ttu-id="bd58e-239">Значение по умолчанию — ASCII.</span><span class="sxs-lookup"><span data-stu-id="bd58e-239">The default is ASCII.</span></span>

- <span data-ttu-id="bd58e-240">**ASCII** : использует кодировку для набора символов ASCII (7-разрядных).</span><span class="sxs-lookup"><span data-stu-id="bd58e-240">**ASCII** :  Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="bd58e-241">**BigEndianUnicode** : кодирует в формате UTF-16 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="bd58e-241">**BigEndianUnicode** :  Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="bd58e-242">**Строка** : использует тип кодировки для строки.</span><span class="sxs-lookup"><span data-stu-id="bd58e-242">**String** :  Uses the encoding type for a string.</span></span>
- <span data-ttu-id="bd58e-243">**Юникод** : кодирует в формате UTF-16 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="bd58e-243">**Unicode** :  Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="bd58e-244">**UTF7** : кодирует в формате UTF-7.</span><span class="sxs-lookup"><span data-stu-id="bd58e-244">**UTF7** :   Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="bd58e-245">**UTF8** : кодирует в формате UTF-8.</span><span class="sxs-lookup"><span data-stu-id="bd58e-245">**UTF8** :  Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="bd58e-246">**UTF8BOM** : кодирует в формате UTF-8 с меткой порядка БАЙТОВ (BOM)</span><span class="sxs-lookup"><span data-stu-id="bd58e-246">**UTF8BOM** : Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="bd58e-247">**UF8NOBOM** : кодирует в формате UTF-8 без метки порядка БАЙТОВ (BOM)</span><span class="sxs-lookup"><span data-stu-id="bd58e-247">**UF8NOBOM** : Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="bd58e-248">**UTF32** : кодирует в формате UTF-32.</span><span class="sxs-lookup"><span data-stu-id="bd58e-248">**UTF32** :  Encodes in UTF-32 format.</span></span>
- <span data-ttu-id="bd58e-249">**По умолчанию** : кодируется на странице установленного по умолчанию кода.</span><span class="sxs-lookup"><span data-stu-id="bd58e-249">**Default** : Encodes in the default installed code page.</span></span>
- <span data-ttu-id="bd58e-250">**OEM** : использует кодировку по умолчанию для программ MS-DOS и консолей.</span><span class="sxs-lookup"><span data-stu-id="bd58e-250">**OEM** : Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="bd58e-251">**Неизвестно** : неизвестный или недопустимый тип кодировки.</span><span class="sxs-lookup"><span data-stu-id="bd58e-251">**Unknown** :  The encoding type is unknown or invalid.</span></span> <span data-ttu-id="bd58e-252">Данные можно обрабатывать как двоичные.</span><span class="sxs-lookup"><span data-stu-id="bd58e-252">The data can be treated as binary.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="bd58e-253">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="bd58e-253">Cmdlets supported</span></span>

- [<span data-ttu-id="bd58e-254">Add-Content</span><span class="sxs-lookup"><span data-stu-id="bd58e-254">Add-Content</span></span>](xref:Microsoft.PowerShell.Management.Add-Content)
- [<span data-ttu-id="bd58e-255">Get-Content</span><span class="sxs-lookup"><span data-stu-id="bd58e-255">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)
- [<span data-ttu-id="bd58e-256">Set-Content</span><span class="sxs-lookup"><span data-stu-id="bd58e-256">Set-Content</span></span>](xref:Microsoft.PowerShell.Management.Set-Content)

### <a name="delimiter-systemstring"></a><span data-ttu-id="bd58e-257">Delimiter \<System.String\></span><span class="sxs-lookup"><span data-stu-id="bd58e-257">Delimiter \<System.String\></span></span>

<span data-ttu-id="bd58e-258">Указывает разделитель, используемый командлетом [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) для разделения файла на объекты при чтении.</span><span class="sxs-lookup"><span data-stu-id="bd58e-258">Specifies the delimiter that [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) uses to divide the file into objects while it reads.</span></span>

<span data-ttu-id="bd58e-259">Значение по умолчанию — `\n` , символ конца строки.</span><span class="sxs-lookup"><span data-stu-id="bd58e-259">The default is `\n`, the end-of-line character.</span></span>

<span data-ttu-id="bd58e-260">При чтении текстового файла командлет [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) Возвращает коллекцию строковых объектов, каждая из которых заканчивается символом-разделителем.</span><span class="sxs-lookup"><span data-stu-id="bd58e-260">When reading a text file, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) returns a collection of string objects, each of which ends with the delimiter character.</span></span>

<span data-ttu-id="bd58e-261">При вводе разделителя, который не существует в файле, командлет [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) возвращает весь файл как один объект без разделителей.</span><span class="sxs-lookup"><span data-stu-id="bd58e-261">Entering a delimiter that does not exist in the file, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) returns the entire file as a single, un-delimited object.</span></span>

<span data-ttu-id="bd58e-262">Этот параметр можно использовать для разбиения большого файла на меньшие файлы, указав разделитель файла, например "Конец примера", в качестве разделителя.</span><span class="sxs-lookup"><span data-stu-id="bd58e-262">You can use this parameter to split a large file into smaller files by specifying a file separator, such as "End of Example", as the delimiter.</span></span> <span data-ttu-id="bd58e-263">Разделитель сохраняется (не удаляется) и становится последним элементом в каждом разделе файла.</span><span class="sxs-lookup"><span data-stu-id="bd58e-263">The delimiter is preserved (not discarded) and becomes the last item in each file section.</span></span>

> [!NOTE]
> <span data-ttu-id="bd58e-264">В настоящее время, если значение `-Delimiter` параметра является пустой строкой, командлет [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) не возвращает ничего.</span><span class="sxs-lookup"><span data-stu-id="bd58e-264">Currently, when the value of the `-Delimiter` parameter is an empty string, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) does not return anything.</span></span>
> <span data-ttu-id="bd58e-265">Это известная проблема.</span><span class="sxs-lookup"><span data-stu-id="bd58e-265">This is a known issue.</span></span> <span data-ttu-id="bd58e-266">Чтобы принудительно применить командлет [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) для возврата всего файла в виде единой неразделенной строки, введите значение, которое не существует в файле.</span><span class="sxs-lookup"><span data-stu-id="bd58e-266">To force [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) to return the entire file as a single, undelimited string, enter a value that does not exist in the file.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="bd58e-267">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="bd58e-267">Cmdlets supported</span></span>

- [<span data-ttu-id="bd58e-268">Get-Content</span><span class="sxs-lookup"><span data-stu-id="bd58e-268">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)

### <a name="wait-systemmanagementautomationswitchparameter"></a><span data-ttu-id="bd58e-269">Wait \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="bd58e-269">Wait \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="bd58e-270">Ожидает содержимое для добавления в файл.</span><span class="sxs-lookup"><span data-stu-id="bd58e-270">Waits for content to be appended to the file.</span></span> <span data-ttu-id="bd58e-271">Если содержимое добавлено, возвращает добавленное содержимое.</span><span class="sxs-lookup"><span data-stu-id="bd58e-271">If content is appended, it returns the appended content.</span></span> <span data-ttu-id="bd58e-272">Если содержимое не изменилось, возвращает весь файл.</span><span class="sxs-lookup"><span data-stu-id="bd58e-272">If the content has changed, it returns the entire file.</span></span>

<span data-ttu-id="bd58e-273">Во время ожидания командлет [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) проверяет файл раз в секунду, пока не будет прерван, например, нажатием сочетания клавиш CTRL+C.</span><span class="sxs-lookup"><span data-stu-id="bd58e-273">When waiting, [Get-Content](xref:Microsoft.PowerShell.Management.Get-Content) checks the file once each second until you interrupt it, such as by pressing CTRL+C.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="bd58e-274">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="bd58e-274">Cmdlets supported</span></span>

- [<span data-ttu-id="bd58e-275">Get-Content</span><span class="sxs-lookup"><span data-stu-id="bd58e-275">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)

### <a name="attributes-flagsexpression"></a><span data-ttu-id="bd58e-276">Attributes \<FlagsExpression\></span><span class="sxs-lookup"><span data-stu-id="bd58e-276">Attributes \<FlagsExpression\></span></span>

<span data-ttu-id="bd58e-277">Извлекает файлы и папки с указанными атрибутами.</span><span class="sxs-lookup"><span data-stu-id="bd58e-277">Gets files and folders with the specified attributes.</span></span> <span data-ttu-id="bd58e-278">Этот параметр поддерживает все атрибуты и позволяет указывать сложные сочетания атрибутов.</span><span class="sxs-lookup"><span data-stu-id="bd58e-278">This parameter supports all attributes and lets you specify complex combinations of attributes.</span></span>

<span data-ttu-id="bd58e-279">`-Attributes`Параметр был представлен в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="bd58e-279">The `-Attributes` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="bd58e-280">`-Attributes`Параметр поддерживает следующие атрибуты:</span><span class="sxs-lookup"><span data-stu-id="bd58e-280">The `-Attributes` parameter supports the following attributes:</span></span>

- <span data-ttu-id="bd58e-281">**Архив**</span><span class="sxs-lookup"><span data-stu-id="bd58e-281">**Archive**</span></span>
- <span data-ttu-id="bd58e-282">**Compressed**</span><span class="sxs-lookup"><span data-stu-id="bd58e-282">**Compressed**</span></span>
- <span data-ttu-id="bd58e-283">**Устройство**</span><span class="sxs-lookup"><span data-stu-id="bd58e-283">**Device**</span></span>
- <span data-ttu-id="bd58e-284">**Каталог**</span><span class="sxs-lookup"><span data-stu-id="bd58e-284">**Directory**</span></span>
- <span data-ttu-id="bd58e-285">**Зашифрована**</span><span class="sxs-lookup"><span data-stu-id="bd58e-285">**Encrypted**</span></span>
- <span data-ttu-id="bd58e-286">**Скрыта**</span><span class="sxs-lookup"><span data-stu-id="bd58e-286">**Hidden**</span></span>
- <span data-ttu-id="bd58e-287">**Обычный**</span><span class="sxs-lookup"><span data-stu-id="bd58e-287">**Normal**</span></span>
- <span data-ttu-id="bd58e-288">**нотконтентиндексед**</span><span class="sxs-lookup"><span data-stu-id="bd58e-288">**NotContentIndexed**</span></span>
- <span data-ttu-id="bd58e-289">**Работа**</span><span class="sxs-lookup"><span data-stu-id="bd58e-289">**Offline**</span></span>
- <span data-ttu-id="bd58e-290">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="bd58e-290">**ReadOnly**</span></span>
- <span data-ttu-id="bd58e-291">**репарсепоинт**</span><span class="sxs-lookup"><span data-stu-id="bd58e-291">**ReparsePoint**</span></span>
- <span data-ttu-id="bd58e-292">**спарсефиле**</span><span class="sxs-lookup"><span data-stu-id="bd58e-292">**SparseFile**</span></span>
- <span data-ttu-id="bd58e-293">**Системные функции**</span><span class="sxs-lookup"><span data-stu-id="bd58e-293">**System**</span></span>
- <span data-ttu-id="bd58e-294">**Временные процедуры**</span><span class="sxs-lookup"><span data-stu-id="bd58e-294">**Temporary**</span></span>

<span data-ttu-id="bd58e-295">Описание этих атрибутов см. в описании перечисления [FileAttributes](/dotnet/api/system.io.fileattributes) .</span><span class="sxs-lookup"><span data-stu-id="bd58e-295">For a description of these attributes, see the [FileAttributes](/dotnet/api/system.io.fileattributes) enumeration.</span></span>

<span data-ttu-id="bd58e-296">Используйте следующие операторы для объединения атрибутов.</span><span class="sxs-lookup"><span data-stu-id="bd58e-296">Use the following operators to combine attributes.</span></span>

- <span data-ttu-id="bd58e-297">`!` — НЕ</span><span class="sxs-lookup"><span data-stu-id="bd58e-297">`!` - NOT</span></span>
- <span data-ttu-id="bd58e-298">`+` -И</span><span class="sxs-lookup"><span data-stu-id="bd58e-298">`+` - AND</span></span>
- <span data-ttu-id="bd58e-299">`,` — ИЛИ</span><span class="sxs-lookup"><span data-stu-id="bd58e-299">`,` - OR</span></span>

<span data-ttu-id="bd58e-300">Пробелы между оператором и его атрибутами не допускаются.</span><span class="sxs-lookup"><span data-stu-id="bd58e-300">No spaces are permitted between an operator and its attribute.</span></span> <span data-ttu-id="bd58e-301">Однако допустима постановка пробелов перед запятыми.</span><span class="sxs-lookup"><span data-stu-id="bd58e-301">However, spaces are permitted before commas.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="bd58e-302">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="bd58e-302">Cmdlets supported</span></span>

- [<span data-ttu-id="bd58e-303">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="bd58e-303">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="directory-systemmanagementautomationswitchparameter"></a><span data-ttu-id="bd58e-304">Directory \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="bd58e-304">Directory \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="bd58e-305">Извлекает каталоги (папки).</span><span class="sxs-lookup"><span data-stu-id="bd58e-305">Gets directories (folders).</span></span>

<span data-ttu-id="bd58e-306">`-Directory`Параметр был представлен в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="bd58e-306">The `-Directory` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="bd58e-307">Чтобы получить только каталоги, используйте `-Directory` параметр и опустите `-File` параметр.</span><span class="sxs-lookup"><span data-stu-id="bd58e-307">To get only directories, use the `-Directory` parameter and omit the `-File` parameter.</span></span> <span data-ttu-id="bd58e-308">Чтобы исключить каталоги, используйте `-File` параметр и опустите `-Directory` параметр, либо используйте `-Attributes` параметр.</span><span class="sxs-lookup"><span data-stu-id="bd58e-308">To exclude directories, use the `-File` parameter and omit the `-Directory` parameter, or use the `-Attributes` parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="bd58e-309">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="bd58e-309">Cmdlets supported</span></span>

- [<span data-ttu-id="bd58e-310">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="bd58e-310">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="file-systemmanagementautomationswitchparameter"></a><span data-ttu-id="bd58e-311">File \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="bd58e-311">File \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="bd58e-312">Извлекает файлы.</span><span class="sxs-lookup"><span data-stu-id="bd58e-312">Gets files.</span></span>

<span data-ttu-id="bd58e-313">`-File`Параметр был представлен в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="bd58e-313">The `-File` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="bd58e-314">Чтобы получить только файлы, используйте `-File` параметр и опустите `-Directory` параметр.</span><span class="sxs-lookup"><span data-stu-id="bd58e-314">To get only files, use the `-File` parameter and omit the `-Directory` parameter.</span></span> <span data-ttu-id="bd58e-315">Чтобы исключить файлы, используйте `-Directory` параметр и опустите `-File` параметр, либо используйте `-Attributes` параметр.</span><span class="sxs-lookup"><span data-stu-id="bd58e-315">To exclude files, use the `-Directory` parameter and omit the `-File` parameter, or use the `-Attributes` parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="bd58e-316">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="bd58e-316">Cmdlets supported</span></span>

- [<span data-ttu-id="bd58e-317">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="bd58e-317">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="hidden-systemmanagementautomationswitchparameter"></a><span data-ttu-id="bd58e-318">Hidden \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="bd58e-318">Hidden \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="bd58e-319">Возвращает только скрытые файлы или каталоги (папки).</span><span class="sxs-lookup"><span data-stu-id="bd58e-319">Gets only hidden files and directories (folders).</span></span> <span data-ttu-id="bd58e-320">По умолчанию командлет [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) получает только нескрытые элементы.</span><span class="sxs-lookup"><span data-stu-id="bd58e-320">By default, [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) gets only non-hidden items.</span></span>

<span data-ttu-id="bd58e-321">`-Hidden`Параметр был представлен в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="bd58e-321">The `-Hidden` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="bd58e-322">Чтобы получить только скрытые элементы, используйте `-Hidden` параметр, его `h` `ah` псевдонимы или **скрытое** значение `-Attributes` параметра.</span><span class="sxs-lookup"><span data-stu-id="bd58e-322">To get only hidden items, use the `-Hidden` parameter, its `h` or `ah` aliases, or the **Hidden** value of the `-Attributes` parameter.</span></span> <span data-ttu-id="bd58e-323">Чтобы исключить скрытые элементы, опустите `-Hidden` параметр или используйте `-Attributes` параметр.</span><span class="sxs-lookup"><span data-stu-id="bd58e-323">To exclude hidden items, omit the `-Hidden` parameter or use the `-Attributes` parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="bd58e-324">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="bd58e-324">Cmdlets supported</span></span>

- [<span data-ttu-id="bd58e-325">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="bd58e-325">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="readonly-systemmanagementautomationswitchparameter"></a><span data-ttu-id="bd58e-326">ReadOnly \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="bd58e-326">ReadOnly \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="bd58e-327">Извлекает только файлы или каталоги (папки), доступные для чтения.</span><span class="sxs-lookup"><span data-stu-id="bd58e-327">Gets only read-only files and directories (folders).</span></span>

<span data-ttu-id="bd58e-328">`-ReadOnly`Параметр был представлен в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="bd58e-328">The `-ReadOnly` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="bd58e-329">Чтобы получить только элементы, доступные только для чтения, используйте `-ReadOnly` параметр, его `ar` псевдоним или значение **ReadOnly** `-Attributes` параметра.</span><span class="sxs-lookup"><span data-stu-id="bd58e-329">To get only read-only items, use the `-ReadOnly` parameter, its `ar` alias, or the **ReadOnly** value of the `-Attributes` parameter.</span></span> <span data-ttu-id="bd58e-330">Чтобы исключить элементы, предназначенные только для чтения, используйте `-Attributes` параметр.</span><span class="sxs-lookup"><span data-stu-id="bd58e-330">To exclude read-only items, use the `-Attributes` parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="bd58e-331">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="bd58e-331">Cmdlets supported</span></span>

- [<span data-ttu-id="bd58e-332">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="bd58e-332">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="system-systemmanagementautomationswitchparameter"></a><span data-ttu-id="bd58e-333">System \<System.Management.Automation.SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="bd58e-333">System \<System.Management.Automation.SwitchParameter\></span></span>

<span data-ttu-id="bd58e-334">Извлекает только системные файлы или каталоги (папки).</span><span class="sxs-lookup"><span data-stu-id="bd58e-334">Gets only system files and directories (folders).</span></span>

<span data-ttu-id="bd58e-335">`-System`Параметр был представлен в Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="bd58e-335">The `-System` parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="bd58e-336">Чтобы получить только системные файлы и папки, используйте `-System` параметр, его `as` псевдоним или **системное** значение `-Attributes` параметра.</span><span class="sxs-lookup"><span data-stu-id="bd58e-336">To get only system files and folders, use the `-System` parameter, its `as` alias, or the **System** value of the `-Attributes` parameter.</span></span> <span data-ttu-id="bd58e-337">Чтобы исключить системные файлы и папки, используйте `-Attributes` параметр.</span><span class="sxs-lookup"><span data-stu-id="bd58e-337">To exclude system files and folders, use the `-Attributes` parameter.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="bd58e-338">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="bd58e-338">Cmdlets supported</span></span>

- [<span data-ttu-id="bd58e-339">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="bd58e-339">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

### <a name="newerthan-systemdatetime"></a><span data-ttu-id="bd58e-340">NewerThan \<System.DateTime\></span><span class="sxs-lookup"><span data-stu-id="bd58e-340">NewerThan \<System.DateTime\></span></span>

<span data-ttu-id="bd58e-341">Возвращает `$True` , если `LastWriteTime` значение файла больше указанной даты.</span><span class="sxs-lookup"><span data-stu-id="bd58e-341">Returns `$True` when the `LastWriteTime` value of a file is greater than the specified date.</span></span> <span data-ttu-id="bd58e-342">В противном случае она возвращает `$False`.</span><span class="sxs-lookup"><span data-stu-id="bd58e-342">Otherwise, it returns `$False`.</span></span>

<span data-ttu-id="bd58e-343">Введите объект [DateTime](/dotnet/api/system.datetime) , например, возвращаемый командлетом [Get-Date](xref:Microsoft.PowerShell.Utility.Get-Date) , или строку, которую можно преобразовать в объект [DateTime](/dotnet/api/system.datetime) , например `"August 10, 2011 2:00 PM"` .</span><span class="sxs-lookup"><span data-stu-id="bd58e-343">Enter a [DateTime](/dotnet/api/system.datetime) object, such as one that the [Get-Date](xref:Microsoft.PowerShell.Utility.Get-Date) cmdlet returns, or a string that can be converted to a [DateTime](/dotnet/api/system.datetime) object, such as `"August 10, 2011 2:00 PM"`.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="bd58e-344">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="bd58e-344">Cmdlets supported</span></span>

- [<span data-ttu-id="bd58e-345">Test-Path</span><span class="sxs-lookup"><span data-stu-id="bd58e-345">Test-Path</span></span>](xref:Microsoft.PowerShell.Management.Test-Path)

### <a name="olderthan-systemdatetime"></a><span data-ttu-id="bd58e-346">OlderThan \<System.DateTime\></span><span class="sxs-lookup"><span data-stu-id="bd58e-346">OlderThan \<System.DateTime\></span></span>

<span data-ttu-id="bd58e-347">Возвращает `$True` , если `LastWriteTime` значение файла меньше указанной даты.</span><span class="sxs-lookup"><span data-stu-id="bd58e-347">Returns `$True` when the `LastWriteTime` value of a file is less than the specified date.</span></span> <span data-ttu-id="bd58e-348">В противном случае она возвращает `$False`.</span><span class="sxs-lookup"><span data-stu-id="bd58e-348">Otherwise, it returns `$False`.</span></span>

<span data-ttu-id="bd58e-349">Введите объект [DateTime](/dotnet/api/system.datetime) , например, возвращаемый командлетом [Get-Date](xref:Microsoft.PowerShell.Utility.Get-Date) , или строку, которую можно преобразовать в объект [DateTime](/dotnet/api/system.datetime) , например `"August 10, 2011 2:00 PM"` .</span><span class="sxs-lookup"><span data-stu-id="bd58e-349">Enter a [DateTime](/dotnet/api/system.datetime) object, such as one that the [Get-Date](xref:Microsoft.PowerShell.Utility.Get-Date) cmdlet returns, or a string that can be converted to a [DateTime](/dotnet/api/system.datetime) object, such as `"August 10, 2011 2:00 PM"`.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="bd58e-350">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="bd58e-350">Cmdlets supported</span></span>

- [<span data-ttu-id="bd58e-351">Test-Path</span><span class="sxs-lookup"><span data-stu-id="bd58e-351">Test-Path</span></span>](xref:Microsoft.PowerShell.Management.Test-Path)

### <a name="stream-systemstring"></a><span data-ttu-id="bd58e-352">Stream \<System.String\></span><span class="sxs-lookup"><span data-stu-id="bd58e-352">Stream \<System.String\></span></span>

<span data-ttu-id="bd58e-353">Управляет альтернативными потоками данных.</span><span class="sxs-lookup"><span data-stu-id="bd58e-353">Manages alternate data streams.</span></span> <span data-ttu-id="bd58e-354">Введите имя потока.</span><span class="sxs-lookup"><span data-stu-id="bd58e-354">Enter the stream name.</span></span> <span data-ttu-id="bd58e-355">Подстановочные знаки разрешены только в командах [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) для и [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item) на диске файловой системы.</span><span class="sxs-lookup"><span data-stu-id="bd58e-355">Wildcards are permitted only in [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) for and [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item) commands in a file system drive.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="bd58e-356">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="bd58e-356">Cmdlets supported</span></span>

- [<span data-ttu-id="bd58e-357">Add-Content</span><span class="sxs-lookup"><span data-stu-id="bd58e-357">Add-Content</span></span>](xref:Microsoft.PowerShell.Management.Add-Content)
- [<span data-ttu-id="bd58e-358">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="bd58e-358">Clear-Content</span></span>](xref:Microsoft.PowerShell.Management.Clear-Content)
- [<span data-ttu-id="bd58e-359">Get-Item</span><span class="sxs-lookup"><span data-stu-id="bd58e-359">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="bd58e-360">Get-Content</span><span class="sxs-lookup"><span data-stu-id="bd58e-360">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)
- [<span data-ttu-id="bd58e-361">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="bd58e-361">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="bd58e-362">Set-Content</span><span class="sxs-lookup"><span data-stu-id="bd58e-362">Set-Content</span></span>](xref:Microsoft.PowerShell.Management.Set-Content)

### <a name="raw-switchparameter"></a><span data-ttu-id="bd58e-363">Raw \<SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="bd58e-363">Raw \<SwitchParameter\></span></span>

<span data-ttu-id="bd58e-364">Игнорирует символы новой строки.</span><span class="sxs-lookup"><span data-stu-id="bd58e-364">Ignores newline characters.</span></span> <span data-ttu-id="bd58e-365">Возвращает содержимое в виде одного элемента.</span><span class="sxs-lookup"><span data-stu-id="bd58e-365">Returns contents as a single item.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="bd58e-366">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="bd58e-366">Cmdlets supported</span></span>

- [<span data-ttu-id="bd58e-367">Get-Content</span><span class="sxs-lookup"><span data-stu-id="bd58e-367">Get-Content</span></span>](xref:Microsoft.PowerShell.Management.Get-Content)

### <a name="itemtype-string"></a><span data-ttu-id="bd58e-368">ItemType \<String\></span><span class="sxs-lookup"><span data-stu-id="bd58e-368">ItemType \<String\></span></span>

<span data-ttu-id="bd58e-369">Этот параметр позволяет указать те элемента для создания `New-Item`</span><span class="sxs-lookup"><span data-stu-id="bd58e-369">This parameter allows you to specify the tye of item to create with `New-Item`</span></span>

<span data-ttu-id="bd58e-370">Доступные значения этого параметра зависят от текущего используемого поставщика.</span><span class="sxs-lookup"><span data-stu-id="bd58e-370">The available values of this parameter depend on the current provider you are using.</span></span>

<span data-ttu-id="bd58e-371">В `FileSystem` диске допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="bd58e-371">In a `FileSystem` drive, the following values are allowed:</span></span>

- <span data-ttu-id="bd58e-372">Файл</span><span class="sxs-lookup"><span data-stu-id="bd58e-372">File</span></span>
- <span data-ttu-id="bd58e-373">Каталог</span><span class="sxs-lookup"><span data-stu-id="bd58e-373">Directory</span></span>
- <span data-ttu-id="bd58e-374">SymbolicLink</span><span class="sxs-lookup"><span data-stu-id="bd58e-374">SymbolicLink</span></span>
- <span data-ttu-id="bd58e-375">Соединение</span><span class="sxs-lookup"><span data-stu-id="bd58e-375">Junction</span></span>
- <span data-ttu-id="bd58e-376">HardLink</span><span class="sxs-lookup"><span data-stu-id="bd58e-376">HardLink</span></span>

### <a name="cmdlets-supported"></a><span data-ttu-id="bd58e-377">Поддерживаемые командлеты</span><span class="sxs-lookup"><span data-stu-id="bd58e-377">Cmdlets supported</span></span>

- [<span data-ttu-id="bd58e-378">New-Item</span><span class="sxs-lookup"><span data-stu-id="bd58e-378">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

## <a name="using-the-pipeline"></a><span data-ttu-id="bd58e-379">Использование конвейера</span><span class="sxs-lookup"><span data-stu-id="bd58e-379">Using the pipeline</span></span>

<span data-ttu-id="bd58e-380">Командлеты поставщика принимают входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="bd58e-380">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="bd58e-381">Вы можете использовать конвейер для упрощения задачи, отправив данные поставщика из одного командлета другому командлету поставщика.</span><span class="sxs-lookup"><span data-stu-id="bd58e-381">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="bd58e-382">Дополнительные сведения об использовании конвейера с командлетами поставщика см. в справочнике по командлетам, приведенным в этой статье.</span><span class="sxs-lookup"><span data-stu-id="bd58e-382">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="bd58e-383">Получение справки</span><span class="sxs-lookup"><span data-stu-id="bd58e-383">Getting help</span></span>

<span data-ttu-id="bd58e-384">Начиная с Windows PowerShell 3.0, стали доступны настраиваемые разделы справки по командлетам поставщика, в которых объясняется поведение этих командлетов на диске файловой системы.</span><span class="sxs-lookup"><span data-stu-id="bd58e-384">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="bd58e-385">Чтобы получить разделы справки, настроенные для диска файловой системы, выполните команду [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) на диске файловой системы или используйте параметр командлета `-Path` [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) , чтобы указать диск файловой системы.</span><span class="sxs-lookup"><span data-stu-id="bd58e-385">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path c:
```

## <a name="see-also"></a><span data-ttu-id="bd58e-386">См. также статью</span><span class="sxs-lookup"><span data-stu-id="bd58e-386">See also</span></span>

[<span data-ttu-id="bd58e-387">about_Providers</span><span class="sxs-lookup"><span data-stu-id="bd58e-387">about_Providers</span></span>](../About/about_Providers.md)
