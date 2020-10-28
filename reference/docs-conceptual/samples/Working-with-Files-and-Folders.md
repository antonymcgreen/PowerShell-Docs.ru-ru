---
ms.date: 06/05/2017
keywords: powershell,командлет
title: Работа с файлами и папками
description: В этой статье описывается выполнение конкретных задач по управлению файлами и папками с помощью PowerShell.
ms.openlocfilehash: c0c3abb082b05296daa480ac06bcbfa3a784e0c9
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500034"
---
# <a name="working-with-files-and-folders"></a><span data-ttu-id="b4d43-104">Работа с файлами и папками</span><span class="sxs-lookup"><span data-stu-id="b4d43-104">Working with Files and Folders</span></span>

<span data-ttu-id="b4d43-105">Просмотр содержимого дисков Windows PowerShell и управление хранящимися на них элементами аналогично управлению файлами и папками на физических дисках Windows.</span><span class="sxs-lookup"><span data-stu-id="b4d43-105">Navigating through Windows PowerShell drives and manipulating the items on them is similar to manipulating files and folders on Windows physical disk drives.</span></span> <span data-ttu-id="b4d43-106">В этой статье описывается выполнение конкретных задач по управлению файлами и папками с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b4d43-106">This article discusses how to deal with specific file and folder manipulation tasks using PowerShell.</span></span>

## <a name="listing-all-the-files-and-folders-within-a-folder"></a><span data-ttu-id="b4d43-107">Получение списка файлов и папок, содержащихся в папке</span><span class="sxs-lookup"><span data-stu-id="b4d43-107">Listing All the Files and Folders Within a Folder</span></span>

<span data-ttu-id="b4d43-108">Извлечь все элементы непосредственно из папки можно с помощью командлета `Get-ChildItem`.</span><span class="sxs-lookup"><span data-stu-id="b4d43-108">You can get all items directly within a folder by using `Get-ChildItem`.</span></span> <span data-ttu-id="b4d43-109">Для отображения скрытых и системных элементов добавьте необязательный параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="b4d43-109">Add the optional **Force** parameter to display hidden or system items.</span></span> <span data-ttu-id="b4d43-110">Например, эта команда отображает непосредственное содержимое диска C Windows PowerShell (которое совпадает с содержимым физического диска C Windows):</span><span class="sxs-lookup"><span data-stu-id="b4d43-110">For example, this command displays the direct contents of Windows PowerShell Drive C (which is the same as the Windows physical drive C):</span></span>

```powershell
Get-ChildItem -Path C:\ -Force
```

<span data-ttu-id="b4d43-111">Эта команда выводит только элементы, содержащиеся на диске непосредственно, так же как и команда `DIR` оболочки `Cmd.exe` или команда `ls` оболочки UNIX.</span><span class="sxs-lookup"><span data-stu-id="b4d43-111">The command lists only the directly contained items, much like using `Cmd.exe`'s `DIR` command or `ls` in a UNIX shell.</span></span> <span data-ttu-id="b4d43-112">Для показа вложенных элементов необходимо также указать параметр `-Recurse`.</span><span class="sxs-lookup"><span data-stu-id="b4d43-112">In order to show contained items, you need to specify the `-Recurse` parameter as well.</span></span> <span data-ttu-id="b4d43-113">(Время выполнения этой операции будет очень велико.) Для вывода всего содержимого диска C введите:</span><span class="sxs-lookup"><span data-stu-id="b4d43-113">(This can take an extremely long time to complete.) To list everything on the C drive:</span></span>

```powershell
Get-ChildItem -Path C:\ -Force -Recurse
```

<span data-ttu-id="b4d43-114">Командлет `Get-ChildItem` позволяет отфильтровать элементы с помощью параметров **Path** , **Filter** , **Include** и **Exclude** , но обычно осуществляется лишь фильтрация по имени.</span><span class="sxs-lookup"><span data-stu-id="b4d43-114">`Get-ChildItem` can filter items with its **Path** , **Filter** , **Include** , and **Exclude** parameters, but those are typically based only on name.</span></span> <span data-ttu-id="b4d43-115">Сложную фильтрацию на основе других свойств элементов можно выполнить с помощью `Where-Object`.</span><span class="sxs-lookup"><span data-stu-id="b4d43-115">You can perform complex filtering based on other properties of items by using `Where-Object`.</span></span>

<span data-ttu-id="b4d43-116">Следующая команда находит все исполняемые файлы в папке Program Files, которые были в последний раз изменены после 1 октября 2005 г. и размер которых не менее одного мегабайта и не более десяти мегабайт:</span><span class="sxs-lookup"><span data-stu-id="b4d43-116">The following command finds all executables within the Program Files folder that were last modified after October 1, 2005 and which are neither smaller than 1 megabyte nor larger than 10 megabytes:</span></span>

```powershell
Get-ChildItem -Path $env:ProgramFiles -Recurse -Include *.exe | Where-Object -FilterScript {($_.LastWriteTime -gt '2005-10-01') -and ($_.Length -ge 1mb) -and ($_.Length -le 10mb)}
```

## <a name="copying-files-and-folders"></a><span data-ttu-id="b4d43-117">Копирование файлов и папок</span><span class="sxs-lookup"><span data-stu-id="b4d43-117">Copying Files and Folders</span></span>

<span data-ttu-id="b4d43-118">Копирование выполняется с помощью командлета `Copy-Item`.</span><span class="sxs-lookup"><span data-stu-id="b4d43-118">Copying is done with `Copy-Item`.</span></span> <span data-ttu-id="b4d43-119">Следующая команда создает резервную копию C:\\boot.ini в C:\\boot.bak:</span><span class="sxs-lookup"><span data-stu-id="b4d43-119">The following command backs up C:\\boot.ini to C:\\boot.bak:</span></span>

```powershell
Copy-Item -Path C:\boot.ini -Destination C:\boot.bak
```

<span data-ttu-id="b4d43-120">Если целевой файл уже существует, то попытка копирования завершается неудачей.</span><span class="sxs-lookup"><span data-stu-id="b4d43-120">If the destination file already exists, the copy attempt fails.</span></span> <span data-ttu-id="b4d43-121">Чтобы перезаписать имеющийся целевой файл, используйте параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="b4d43-121">To overwrite a pre-existing destination, use the **Force** parameter:</span></span>

```powershell
Copy-Item -Path C:\boot.ini -Destination C:\boot.bak -Force
```

<span data-ttu-id="b4d43-122">Эта команда работает, даже если целевой объект доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="b4d43-122">This command works even when the destination is read-only.</span></span>

<span data-ttu-id="b4d43-123">Так же выполняется и копирование папок.</span><span class="sxs-lookup"><span data-stu-id="b4d43-123">Folder copying works the same way.</span></span> <span data-ttu-id="b4d43-124">Эта команда копирует папку `C:\temp\test1` в новую папку `C:\temp\DeleteMe` рекурсивно.</span><span class="sxs-lookup"><span data-stu-id="b4d43-124">This command copies the folder `C:\temp\test1` to the new folder `C:\temp\DeleteMe` recursively:</span></span>

```powershell
Copy-Item C:\temp\test1 -Recurse C:\temp\DeleteMe
```

<span data-ttu-id="b4d43-125">Можно также скопировать избранные элементы.</span><span class="sxs-lookup"><span data-stu-id="b4d43-125">You can also copy a selection of items.</span></span> <span data-ttu-id="b4d43-126">Следующая команда копирует все файлы TXT, содержащиеся в папке `C:\data`, в папку `C:\temp\text`:</span><span class="sxs-lookup"><span data-stu-id="b4d43-126">The following command copies all .txt files contained anywhere in `C:\data` to `C:\temp\text`:</span></span>

```powershell
Copy-Item -Filter *.txt -Path c:\data -Recurse -Destination C:\temp\text
```

<span data-ttu-id="b4d43-127">Для копирования элементов файловой системы можно использовать и другие средства.</span><span class="sxs-lookup"><span data-stu-id="b4d43-127">You can still use other tools to perform file system copies.</span></span> <span data-ttu-id="b4d43-128">В Windows PowerShell по-прежнему работают команды XCOPY, ROBOCOPY и такие COM-объекты, как **Scripting.FileSystemObject** .</span><span class="sxs-lookup"><span data-stu-id="b4d43-128">XCOPY, ROBOCOPY, and COM objects, such as the **Scripting.FileSystemObject,** all work in Windows PowerShell.</span></span> <span data-ttu-id="b4d43-129">Например, можно воспользоваться COM-классом **Scripting.FileSystem** сервера сценариев Windows для создания резервной копии файла `C:\boot.ini` в файле `C:\boot.bak`:</span><span class="sxs-lookup"><span data-stu-id="b4d43-129">For example, you can use the Windows Script Host **Scripting.FileSystem COM** class to back up `C:\boot.ini` to `C:\boot.bak`:</span></span>

```powershell
(New-Object -ComObject Scripting.FileSystemObject).CopyFile('C:\boot.ini', 'C:\boot.bak')
```

## <a name="creating-files-and-folders"></a><span data-ttu-id="b4d43-130">Создание файлов и папок</span><span class="sxs-lookup"><span data-stu-id="b4d43-130">Creating Files and Folders</span></span>

<span data-ttu-id="b4d43-131">Создание новых элементов осуществляется одинаковым образом всеми поставщиками Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b4d43-131">Creating new items works the same on all Windows PowerShell providers.</span></span> <span data-ttu-id="b4d43-132">Если поставщик Windows PowerShell поддерживает более одного типа элементов (например, поставщик Windows PowerShell FileSystem различает каталоги и файлы), необходимо указать тип элемента.</span><span class="sxs-lookup"><span data-stu-id="b4d43-132">If a Windows PowerShell provider has more than one type of item—for example, the FileSystem Windows PowerShell provider distinguishes between directories and files—you need to specify the item type.</span></span>

<span data-ttu-id="b4d43-133">Эта команда создает папку `C:\temp\New Folder`:</span><span class="sxs-lookup"><span data-stu-id="b4d43-133">This command creates a new folder `C:\temp\New Folder`:</span></span>

```powershell
New-Item -Path 'C:\temp\New Folder' -ItemType Directory
```

<span data-ttu-id="b4d43-134">Эта команда создает пустой файл `C:\temp\New Folder\file.txt`.</span><span class="sxs-lookup"><span data-stu-id="b4d43-134">This command creates a new empty file `C:\temp\New Folder\file.txt`</span></span>

```powershell
New-Item -Path 'C:\temp\New Folder\file.txt' -ItemType File
```

> [!IMPORTANT]
> <span data-ttu-id="b4d43-135">При использовании параметра **Force** с командой `New-Item` для создания папки, которая уже существует, она _не_ перезапишет и не заменит папку.</span><span class="sxs-lookup"><span data-stu-id="b4d43-135">When using the **Force** switch with the `New-Item` command to create a folder, and the folder already exists, it _won't_ overwrite or replace the folder.</span></span> <span data-ttu-id="b4d43-136">Будет просто возвращен имеющийся объект папки.</span><span class="sxs-lookup"><span data-stu-id="b4d43-136">It will simply return the existing folder object.</span></span> <span data-ttu-id="b4d43-137">Однако, если использовать `New-Item -Force` в уже имеющимся файле, файл _будет_ полностью перезаписан.</span><span class="sxs-lookup"><span data-stu-id="b4d43-137">However, if you use `New-Item -Force` on a file that already exists, the file _will_ be completely overwritten.</span></span>

## <a name="removing-all-files-and-folders-within-a-folder"></a><span data-ttu-id="b4d43-138">Удаление всех файлов и папок, содержащихся в папке</span><span class="sxs-lookup"><span data-stu-id="b4d43-138">Removing All Files and Folders Within a Folder</span></span>

<span data-ttu-id="b4d43-139">Удалить вложенные элементы можно с помощью командлета `Remove-Item`, однако он потребует подтверждения удаления, если элемент сам что-нибудь содержит.</span><span class="sxs-lookup"><span data-stu-id="b4d43-139">You can remove contained items using `Remove-Item`, but you will be prompted to confirm the removal if the item contains anything else.</span></span> <span data-ttu-id="b4d43-140">Например, при попытке удаления папки `C:\temp\DeleteMe`, которая содержит другие элементы, Windows PowerShell предварительно предложит подтвердить удаление этой папки:</span><span class="sxs-lookup"><span data-stu-id="b4d43-140">For example, if you attempt to delete the folder `C:\temp\DeleteMe` that contains other items, Windows PowerShell prompts you for confirmation before deleting the folder:</span></span>

```
Remove-Item -Path C:\temp\DeleteMe

Confirm
The item at C:\temp\DeleteMe has children and the Recurse parameter was not
specified. If you continue, all children will be removed with the item. Are you
sure you want to continue?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"):
```

<span data-ttu-id="b4d43-141">Если подтверждение для каждого вложенного элемента нежелательно, задайте параметр **Recurse** :</span><span class="sxs-lookup"><span data-stu-id="b4d43-141">If you do not want to be prompted for each contained item, specify the **Recurse** parameter:</span></span>

```powershell
Remove-Item -Path C:\temp\DeleteMe -Recurse
```

## <a name="mapping-a-local-folder-as-a-drive"></a><span data-ttu-id="b4d43-142">Подключение локальной папки как диска</span><span class="sxs-lookup"><span data-stu-id="b4d43-142">Mapping a Local Folder as a drive</span></span>

<span data-ttu-id="b4d43-143">Отобразить локальную папку можно с помощью команды `New-PSDrive`.</span><span class="sxs-lookup"><span data-stu-id="b4d43-143">You can also map a local folder, using the `New-PSDrive` command.</span></span> <span data-ttu-id="b4d43-144">Следующая команда создает локальный диск `P:`, корневым каталогом которого является локальный каталог Program Files, отображающийся только в сеансе PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b4d43-144">The following command creates a local drive `P:` rooted in the local Program Files directory, visible only from the PowerShell session:</span></span>

```powershell
New-PSDrive -Name P -Root $env:ProgramFiles -PSProvider FileSystem
```

<span data-ttu-id="b4d43-145">Как и при использовании сетевых дисков, диски, отображенные в Windows PowerShell, немедленно становятся доступными оболочке Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b4d43-145">Just as with network drives, drives mapped within Windows PowerShell are immediately visible to the Windows PowerShell shell.</span></span> <span data-ttu-id="b4d43-146">Чтобы создать подключенный диск, отображающийся в проводнике, нужен параметр `-Persist`.</span><span class="sxs-lookup"><span data-stu-id="b4d43-146">In order to create a mapped drive visible from File Explorer, the parameter `-Persist` is needed.</span></span> <span data-ttu-id="b4d43-147">Но с этим параметром можно использовать только удаленные пути.</span><span class="sxs-lookup"><span data-stu-id="b4d43-147">However, only remote paths can be used with Persist.</span></span>

## <a name="reading-a-text-file-into-an-array"></a><span data-ttu-id="b4d43-148">Чтение текстового файла в массив</span><span class="sxs-lookup"><span data-stu-id="b4d43-148">Reading a Text File into an Array</span></span>

<span data-ttu-id="b4d43-149">Одним из наиболее общих форматов хранения текстовых данных является файл, отдельные строки которого рассматриваются как отдельные элементы.</span><span class="sxs-lookup"><span data-stu-id="b4d43-149">One of the more common storage formats for text data is in a file with separate lines treated as distinct data elements.</span></span> <span data-ttu-id="b4d43-150">Командлет `Get-Content` используется для чтения всего файла за один шаг, как показано далее:</span><span class="sxs-lookup"><span data-stu-id="b4d43-150">The `Get-Content` cmdlet can be used to read an entire file in one step, as shown here:</span></span>

```
PS> Get-Content -Path C:\boot.ini
[boot loader]
timeout=5
default=multi(0)disk(0)rdisk(0)partition(1)\WINDOWS
[operating systems]
multi(0)disk(0)rdisk(0)partition(1)\WINDOWS="Microsoft Windows XP Professional"
 /noexecute=AlwaysOff /fastdetect
multi(0)disk(0)rdisk(0)partition(1)\WINDOWS=" Microsoft Windows XP Professional
with Data Execution Prevention" /noexecute=optin /fastdetect
```

<span data-ttu-id="b4d43-151">Командлет `Get-Content` сразу рассматривает данные, считанные из файла, как массив с одним элементом на строку содержимого файла.</span><span class="sxs-lookup"><span data-stu-id="b4d43-151">`Get-Content` already treats the data read from the file as an array, with one element per line of file content.</span></span> <span data-ttu-id="b4d43-152">Убедиться в этом можно, проверив свойство **Length** полученного содержимого:</span><span class="sxs-lookup"><span data-stu-id="b4d43-152">You can confirm this by checking the **Length** of the returned content:</span></span>

```
PS> (Get-Content -Path C:\boot.ini).Length
6
```

<span data-ttu-id="b4d43-153">Эта команда наиболее полезна для непосредственного ввода в Windows PowerShell информационных списков.</span><span class="sxs-lookup"><span data-stu-id="b4d43-153">This command is most useful for getting lists of information into Windows PowerShell directly.</span></span> <span data-ttu-id="b4d43-154">Например, можно хранить в файле `C:\temp\domainMembers.txt` список имен компьютеров или IP-адресов по одному имени на каждую строку файла.</span><span class="sxs-lookup"><span data-stu-id="b4d43-154">For example, you might store a list of computer names or IP addresses in a file `C:\temp\domainMembers.txt`, with one name on each line of the file.</span></span> <span data-ttu-id="b4d43-155">Вы можете использовать командлет `Get-Content`, чтобы извлечь содержимое файла и поместить его в переменную `$Computers`:</span><span class="sxs-lookup"><span data-stu-id="b4d43-155">You can use `Get-Content` to retrieve the file contents and put them in the variable `$Computers`:</span></span>

```powershell
$Computers = Get-Content -Path C:\temp\DomainMembers.txt
```

<span data-ttu-id="b4d43-156">Теперь переменная `$Computers` представляет собой массив, содержащий в каждом элементе имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="b4d43-156">`$Computers` is now an array containing a computer name in each element.</span></span>
