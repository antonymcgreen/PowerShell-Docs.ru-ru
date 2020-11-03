---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/copy-item?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Copy-Item
ms.openlocfilehash: 393e0afafebf30e4b300c4200be6f9fa7a93bfc8
ms.sourcegitcommit: 33ac34789e86ffb4e7e69453ae38fc0bd24933dd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2020
ms.locfileid: "93230546"
---
# <span data-ttu-id="ddad7-103">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="ddad7-103">Copy-Item</span></span>

## <span data-ttu-id="ddad7-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ddad7-104">SYNOPSIS</span></span>
<span data-ttu-id="ddad7-105">Копирует элемент из одного расположения в другое.</span><span class="sxs-lookup"><span data-stu-id="ddad7-105">Copies an item from one location to another.</span></span>

## <span data-ttu-id="ddad7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ddad7-106">SYNTAX</span></span>

### <span data-ttu-id="ddad7-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="ddad7-107">Path (Default)</span></span>

```
Copy-Item [-Path] <String[]> [[-Destination] <String>] [-Container] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Recurse] [-PassThru] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-FromSession <PSSession>] [-ToSession <PSSession>] [<CommonParameters>]
```

### <span data-ttu-id="ddad7-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="ddad7-108">LiteralPath</span></span>

```
Copy-Item -LiteralPath <String[]> [[-Destination] <String>] [-Container] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Recurse] [-PassThru] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-FromSession <PSSession>] [-ToSession <PSSession>] [<CommonParameters>]
```

## <span data-ttu-id="ddad7-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ddad7-109">DESCRIPTION</span></span>

<span data-ttu-id="ddad7-110">`Copy-Item`Командлет копирует элемент из одного расположения в другое расположение в том же пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="ddad7-110">The `Copy-Item` cmdlet copies an item from one location to another location in the same namespace.</span></span>
<span data-ttu-id="ddad7-111">Например, он может скопировать файл в папку, но не может скопировать файл на диск сертификата.</span><span class="sxs-lookup"><span data-stu-id="ddad7-111">For instance, it can copy a file to a folder, but it can't copy a file to a certificate drive.</span></span>

<span data-ttu-id="ddad7-112">Этот командлет не вырезает и не удаляет копируемые элементы.</span><span class="sxs-lookup"><span data-stu-id="ddad7-112">This cmdlet doesn't cut or delete the items being copied.</span></span> <span data-ttu-id="ddad7-113">Отдельные элементы, которые может копировать командлет, зависят от поставщика PowerShell, предоставляющего элемент.</span><span class="sxs-lookup"><span data-stu-id="ddad7-113">The particular items that the cmdlet can copy depend on the PowerShell provider that exposes the item.</span></span> <span data-ttu-id="ddad7-114">Например, он может копировать файлы и каталоги в диск файловой системы, разделы реестра и записи на диске реестра.</span><span class="sxs-lookup"><span data-stu-id="ddad7-114">For instance, it can copy files and directories in a file system drive and registry keys and entries in the registry drive.</span></span>

<span data-ttu-id="ddad7-115">Этот командлет может копировать и переименовывать элементы в одной команде.</span><span class="sxs-lookup"><span data-stu-id="ddad7-115">This cmdlet can copy and rename items in the same command.</span></span> <span data-ttu-id="ddad7-116">Чтобы переименовать элемент, введите новое имя в качестве значения параметра **Destination** .</span><span class="sxs-lookup"><span data-stu-id="ddad7-116">To rename an item, enter the new name in the value of the **Destination** parameter.</span></span> <span data-ttu-id="ddad7-117">Чтобы переименовать элемент и не копировать его, используйте `Rename-Item` командлет.</span><span class="sxs-lookup"><span data-stu-id="ddad7-117">To rename an item and not copy it, use the `Rename-Item` cmdlet.</span></span>

## <span data-ttu-id="ddad7-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="ddad7-118">EXAMPLES</span></span>

### <span data-ttu-id="ddad7-119">Пример 1. копирование файла в указанный каталог</span><span class="sxs-lookup"><span data-stu-id="ddad7-119">Example 1: Copy a file to the specified directory</span></span>

<span data-ttu-id="ddad7-120">В этом примере файл копируется `mar1604.log.txt` в `C:\Presentation` каталог.</span><span class="sxs-lookup"><span data-stu-id="ddad7-120">This example copies the `mar1604.log.txt` file to the `C:\Presentation` directory.</span></span> <span data-ttu-id="ddad7-121">Исходный файл не удаляется.</span><span class="sxs-lookup"><span data-stu-id="ddad7-121">The original file isn't deleted.</span></span>

```powershell
Copy-Item "C:\Wabash\Logfiles\mar1604.log.txt" -Destination "C:\Presentation"
```

### <span data-ttu-id="ddad7-122">Пример 2. копирование содержимого каталога в существующий каталог</span><span class="sxs-lookup"><span data-stu-id="ddad7-122">Example 2: Copy directory contents to an existing directory</span></span>

<span data-ttu-id="ddad7-123">В этом примере содержимое каталога копируется `C:\Logfiles` в существующий `C:\Drawings` каталог.</span><span class="sxs-lookup"><span data-stu-id="ddad7-123">This example copies the contents of the `C:\Logfiles` directory into the existing `C:\Drawings` directory.</span></span> <span data-ttu-id="ddad7-124">`Logfiles`Каталог не копируется.</span><span class="sxs-lookup"><span data-stu-id="ddad7-124">The `Logfiles` directory isn't copied.</span></span>

<span data-ttu-id="ddad7-125">Если `Logfiles` Каталог содержит файлы в подкаталогах, то эти подкаталоги копируются без изменений в их деревьях файлов.</span><span class="sxs-lookup"><span data-stu-id="ddad7-125">If the `Logfiles` directory contains files in subdirectories, those subdirectories are copied with their file trees intact.</span></span> <span data-ttu-id="ddad7-126">По умолчанию параметр **контейнера** имеет значение **true** , сохраняющее структуру каталогов.</span><span class="sxs-lookup"><span data-stu-id="ddad7-126">By default, the **Container** parameter is set to **True** , which preserves the directory structure.</span></span>

```powershell
Copy-Item -Path "C:\Logfiles\*" -Destination "C:\Drawings" -Recurse
```

> [!NOTE]
> <span data-ttu-id="ddad7-127">Если необходимо включить `Logfiles` каталог в копию, удалите `\*` из **пути** .</span><span class="sxs-lookup"><span data-stu-id="ddad7-127">If you need to include the `Logfiles` directory in the copy, remove the `\*` from the **Path** .</span></span>
> <span data-ttu-id="ddad7-128">Пример:</span><span class="sxs-lookup"><span data-stu-id="ddad7-128">For example:</span></span>
>
> `Copy-Item -Path "C:\Logfiles" -Destination "C:\Drawings" -Recurse`

### <span data-ttu-id="ddad7-129">Пример 3. копирование каталога и содержимого в новый каталог</span><span class="sxs-lookup"><span data-stu-id="ddad7-129">Example 3: Copy directory and contents to a new directory</span></span>

<span data-ttu-id="ddad7-130">В этом примере копируется содержимое `C:\Logfiles` исходного каталога и создается новый каталог назначения.</span><span class="sxs-lookup"><span data-stu-id="ddad7-130">This example copies the contents of the `C:\Logfiles` source directory and creates a new destination directory.</span></span> <span data-ttu-id="ddad7-131">Новый каталог назначения `\Logs` создается в `C:\Drawings` .</span><span class="sxs-lookup"><span data-stu-id="ddad7-131">The new destination directory, `\Logs` is created in `C:\Drawings`.</span></span>

<span data-ttu-id="ddad7-132">Чтобы включить имя исходного каталога, скопируйте его в существующий каталог назначения, как показано в **примере 2** .</span><span class="sxs-lookup"><span data-stu-id="ddad7-132">To include the source directory's name, copy to an existing destination directory as shown in **Example 2** .</span></span> <span data-ttu-id="ddad7-133">Или назовите новый каталог назначения так же, как и исходный каталог.</span><span class="sxs-lookup"><span data-stu-id="ddad7-133">Or, name the new destination directory with the same as the source directory.</span></span>

```powershell
Copy-Item -Path "C:\Logfiles" -Destination "C:\Drawings\Logs" -Recurse
```

> [!NOTE]
> <span data-ttu-id="ddad7-134">Если **путь** включает `\*` , все содержимое файла каталога, включая деревья подкаталогов, копируется в новый каталог назначения.</span><span class="sxs-lookup"><span data-stu-id="ddad7-134">If the **Path** includes `\*`, all the directory's file contents, including the subdirectory trees, are copied to the new destination directory.</span></span> <span data-ttu-id="ddad7-135">Пример:</span><span class="sxs-lookup"><span data-stu-id="ddad7-135">For example:</span></span>
>
> `Copy-Item -Path "C:\Logfiles\*" -Destination "C:\Drawings\Logs" -Recurse`

### <span data-ttu-id="ddad7-136">Пример 4. копирование файла в указанный каталог и переименование файла</span><span class="sxs-lookup"><span data-stu-id="ddad7-136">Example 4: Copy a file to the specified directory and rename the file</span></span>

<span data-ttu-id="ddad7-137">В этом примере `Copy-Item` командлет используется для копирования `Get-Widget.ps1` скрипта из `\\Server01\Share` каталога в `\\Server12\ScriptArchive` каталог.</span><span class="sxs-lookup"><span data-stu-id="ddad7-137">This example uses the `Copy-Item` cmdlet to copy the `Get-Widget.ps1` script from the `\\Server01\Share` directory to the `\\Server12\ScriptArchive` directory.</span></span> <span data-ttu-id="ddad7-138">В ходе операции копирования команда изменяет имя элемента с `Get-Widget.ps1` на `Get-Widget.ps1.txt` , поэтому оно может быть присоединено к сообщениям электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ddad7-138">As part of the copy operation, the command changes the item name from `Get-Widget.ps1` to `Get-Widget.ps1.txt`, so it can be attached to email messages.</span></span>

```powershell
Copy-Item "\\Server01\Share\Get-Widget.ps1" -Destination "\\Server12\ScriptArchive\Get-Widget.ps1.txt"
```

### <span data-ttu-id="ddad7-139">Пример 5. копирование файла на удаленный компьютер</span><span class="sxs-lookup"><span data-stu-id="ddad7-139">Example 5: Copy a file to a remote computer</span></span>

<span data-ttu-id="ddad7-140">Сеанс создается для удаленного компьютера с именем **Server01** с учетными данными `Contoso\User01` и сохраняет результаты в переменной с именем `$Session` .</span><span class="sxs-lookup"><span data-stu-id="ddad7-140">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="ddad7-141">`Copy-Item`Командлет копирует `test.log` из `D:\Folder001` папки в `C:\Folder001_Copy` папку на удаленном компьютере, используя сведения о сеансе, хранящиеся в `$Session` переменной.</span><span class="sxs-lookup"><span data-stu-id="ddad7-141">The `Copy-Item` cmdlet copies `test.log` from the `D:\Folder001` folder to the `C:\Folder001_Copy` folder on the remote computer using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="ddad7-142">Исходный файл не удаляется.</span><span class="sxs-lookup"><span data-stu-id="ddad7-142">The original file isn't deleted.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "D:\Folder001\test.log" -Destination "C:\Folder001_Copy\" -ToSession $Session
```

### <span data-ttu-id="ddad7-143">Пример 6. Копирование папки на удаленный компьютер</span><span class="sxs-lookup"><span data-stu-id="ddad7-143">Example 6: Copy a folder to a remote computer</span></span>

<span data-ttu-id="ddad7-144">Сеанс создается для удаленного компьютера с именем **Server01** с учетными данными `Contoso\User01` и сохраняет результаты в переменной с именем `$Session` .</span><span class="sxs-lookup"><span data-stu-id="ddad7-144">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="ddad7-145">`Copy-Item`Командлет копирует папку в `D:\Folder002` `C:\Folder002_Copy` каталог на удаленном компьютере, используя сведения о сеансе, хранящиеся в `$Session` переменной.</span><span class="sxs-lookup"><span data-stu-id="ddad7-145">The `Copy-Item` cmdlet copies the `D:\Folder002` folder to the `C:\Folder002_Copy` directory on the remote computer using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="ddad7-146">Все вложенные папки или файлы не копируются без использования **рекурсивного** переключателя.</span><span class="sxs-lookup"><span data-stu-id="ddad7-146">Any subfolders or files are not copied without using the **Recurse** switch.</span></span>
<span data-ttu-id="ddad7-147">Операция создает папку, `Folder002_Copy` если она еще не существует.</span><span class="sxs-lookup"><span data-stu-id="ddad7-147">The operation creates the `Folder002_Copy` folder if it doesn't already exist.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server02" -Credential "Contoso\User01"
Copy-Item "D:\Folder002\" -Destination "C:\Folder002_Copy\" -ToSession $Session
```

### <span data-ttu-id="ddad7-148">Пример 7. рекурсивное копирование всего содержимого папки на удаленный компьютер</span><span class="sxs-lookup"><span data-stu-id="ddad7-148">Example 7: Recursively copy the entire contents of a folder to a remote computer</span></span>

<span data-ttu-id="ddad7-149">Сеанс создается для удаленного компьютера с именем **Server01** с учетными данными `Contoso\User01` и сохраняет результаты в переменной с именем `$Session` .</span><span class="sxs-lookup"><span data-stu-id="ddad7-149">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="ddad7-150">`Copy-Item`Командлет копирует все содержимое из `D:\Folder003` папки в `C:\Folder003_Copy` каталог на удаленном компьютере, используя сведения о сеансе, хранящиеся в `$Session` переменной.</span><span class="sxs-lookup"><span data-stu-id="ddad7-150">The `Copy-Item` cmdlet copies the entire contents from the `D:\Folder003` folder to the `C:\Folder003_Copy` directory on the remote computer using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="ddad7-151">Вложенные папки копируются без изменений в их деревьях файлов.</span><span class="sxs-lookup"><span data-stu-id="ddad7-151">The subfolders are copied with their file trees intact.</span></span> <span data-ttu-id="ddad7-152">Операция создает папку, `Folder003_Copy` если она еще не существует.</span><span class="sxs-lookup"><span data-stu-id="ddad7-152">The operation creates the `Folder003_Copy` folder if it doesn't already exist.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server04" -Credential "Contoso\User01"
Copy-Item "D:\Folder003\" -Destination "C:\Folder003_Copy\" -ToSession $Session -Recurse
```

### <span data-ttu-id="ddad7-153">Пример 8. копирование файла на удаленный компьютер и его переименование</span><span class="sxs-lookup"><span data-stu-id="ddad7-153">Example 8: Copy a file to a remote computer and then rename the file</span></span>

<span data-ttu-id="ddad7-154">Сеанс создается для удаленного компьютера с именем **Server01** с учетными данными `Contoso\User01` и сохраняет результаты в переменной с именем `$Session` .</span><span class="sxs-lookup"><span data-stu-id="ddad7-154">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="ddad7-155">`Copy-Item`Командлет копирует `scriptingexample.ps1` из `D:\Folder004` папки в `C:\Folder004_Copy` папку на удаленном компьютере, используя сведения о сеансе, хранящиеся в `$Session` переменной.</span><span class="sxs-lookup"><span data-stu-id="ddad7-155">The `Copy-Item` cmdlet copies `scriptingexample.ps1` from the `D:\Folder004` folder to the `C:\Folder004_Copy` folder on the remote computer using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="ddad7-156">В ходе операции копирования команда изменяет имя элемента с `scriptingexample.ps1` на `scriptingexample_copy.ps1` , поэтому оно может быть присоединено к сообщениям электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ddad7-156">As part of the copy operation, the command changes the item name from `scriptingexample.ps1` to `scriptingexample_copy.ps1`, so it can be attached to email messages.</span></span> <span data-ttu-id="ddad7-157">Исходный файл не удаляется.</span><span class="sxs-lookup"><span data-stu-id="ddad7-157">The original file isn't deleted.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server04" -Credential "Contoso\User01"
Copy-Item "D:\Folder004\scriptingexample.ps1" -Destination "C:\Folder004_Copy\scriptingexample_copy.ps1" -ToSession $Session
```

### <span data-ttu-id="ddad7-158">Пример 9. Копирование удаленного файла на локальный компьютер</span><span class="sxs-lookup"><span data-stu-id="ddad7-158">Example 9: Copy a remote file to the local computer</span></span>

<span data-ttu-id="ddad7-159">Сеанс создается для удаленного компьютера с именем **Server01** с учетными данными `Contoso\User01` и сохраняет результаты в переменной с именем `$Session` .</span><span class="sxs-lookup"><span data-stu-id="ddad7-159">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="ddad7-160">`Copy-Item`Командлет копирует `test.log` из удаленной `C:\MyRemoteData\` папки в локальную `D:\MyLocalData` папку, используя сведения о сеансе, хранящиеся в `$Session` переменной.</span><span class="sxs-lookup"><span data-stu-id="ddad7-160">The `Copy-Item` cmdlet copies `test.log` from the remote `C:\MyRemoteData\` to the local `D:\MyLocalData` folder using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="ddad7-161">Исходный файл не удаляется.</span><span class="sxs-lookup"><span data-stu-id="ddad7-161">The original file isn't deleted.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "C:\MyRemoteData\test.log" -Destination "D:\MyLocalData\" -FromSession $Session
```

### <span data-ttu-id="ddad7-162">Пример 10. копирование всего содержимого удаленной папки на локальный компьютер</span><span class="sxs-lookup"><span data-stu-id="ddad7-162">Example 10: Copy the entire contents of a remote folder to the local computer</span></span>

<span data-ttu-id="ddad7-163">Сеанс создается для удаленного компьютера с именем **Server01** с учетными данными `Contoso\User01` и сохраняет результаты в переменной с именем `$Session` .</span><span class="sxs-lookup"><span data-stu-id="ddad7-163">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="ddad7-164">`Copy-Item`Командлет копирует все содержимое из удаленной `C:\MyRemoteData\scripts` папки в локальную `D:\MyLocalData` папку, используя сведения о сеансе, хранящиеся в `$Session` переменной.</span><span class="sxs-lookup"><span data-stu-id="ddad7-164">The `Copy-Item` cmdlet copies the entire contents from the remote `C:\MyRemoteData\scripts` folder to the local `D:\MyLocalData` folder using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="ddad7-165">Если папка Scripts содержит файлы во вложенных папках, эти вложенные папки копируются без изменений.</span><span class="sxs-lookup"><span data-stu-id="ddad7-165">If the scripts folder contains files in subfolders, those subfolders are copied with their file trees intact.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "C:\MyRemoteData\scripts" -Destination "D:\MyLocalData\" -FromSession $Session
```

### <span data-ttu-id="ddad7-166">Пример 11. рекурсивное копирование всего содержимого удаленной папки на локальный компьютер</span><span class="sxs-lookup"><span data-stu-id="ddad7-166">Example 11: Recursively copy the entire contents of a remote folder to the local computer</span></span>

<span data-ttu-id="ddad7-167">Сеанс создается для удаленного компьютера с именем **Server01** с учетными данными `Contoso\User01` и сохраняет результаты в переменной с именем `$Session` .</span><span class="sxs-lookup"><span data-stu-id="ddad7-167">A session is created to the remote computer named **Server01** with the credential of `Contoso\User01` and stores the results in the variable named `$Session`.</span></span>

<span data-ttu-id="ddad7-168">`Copy-Item`Командлет копирует все содержимое из удаленной `C:\MyRemoteData\scripts` папки в локальную `D:\MyLocalData\scripts` папку, используя сведения о сеансе, хранящиеся в `$Session` переменной.</span><span class="sxs-lookup"><span data-stu-id="ddad7-168">The `Copy-Item` cmdlet copies the entire contents from the remote `C:\MyRemoteData\scripts` folder to the local `D:\MyLocalData\scripts` folder using the session information stored in the `$Session` variable.</span></span> <span data-ttu-id="ddad7-169">Так как используется параметр **рекурсии** , операция создает папку Scripts, если она еще не существует.</span><span class="sxs-lookup"><span data-stu-id="ddad7-169">Because the **Recurse** parameter is used, the operation creates the scripts folder if it doesn't already exist.</span></span> <span data-ttu-id="ddad7-170">Если папка Scripts содержит файлы во вложенных папках, эти вложенные папки копируются без изменений.</span><span class="sxs-lookup"><span data-stu-id="ddad7-170">If the scripts folder contains files in subfolders, those subfolders are copied with their file trees intact.</span></span>

```powershell
$Session = New-PSSession -ComputerName "Server01" -Credential "Contoso\User01"
Copy-Item "C:\MyRemoteData\scripts" -Destination "D:\MyLocalData\scripts" -FromSession $Session -Recurse
```

### <span data-ttu-id="ddad7-171">Пример 12. рекурсивное копирование файлов из дерева папок в текущую папку</span><span class="sxs-lookup"><span data-stu-id="ddad7-171">Example 12: Recursively copy files from a folder tree into the current folder</span></span>

<span data-ttu-id="ddad7-172">В этом примере показано, как скопировать файлы из многоуровневой структуры папок в одну неструктурированную папку.</span><span class="sxs-lookup"><span data-stu-id="ddad7-172">This example shows how to copy files from a multilevel folder structure into a single flat folder.</span></span>
<span data-ttu-id="ddad7-173">Первые три команды отображают существующую структуру папок и содержимое двух файлов, оба имени `file3.txt` .</span><span class="sxs-lookup"><span data-stu-id="ddad7-173">The first three commands show the existing folder structure and the contents of two files, both names `file3.txt`.</span></span>

```powershell
PS C:\temp\test> (Get-ChildItem C:\temp\tree -Recurse).FullName
C:\temp\tree\subfolder
C:\temp\tree\file1.txt
C:\temp\tree\file2.txt
C:\temp\tree\file3.txt
C:\temp\tree\subfolder\file3.txt
C:\temp\tree\subfolder\file4.txt
C:\temp\tree\subfolder\file5.txt

PS C:\temp\test> Get-Content C:\temp\tree\file3.txt
This is file3.txt in the root folder

PS C:\temp\test> Get-Content C:\temp\tree\subfolder\file3.txt
This is file3.txt in the subfolder

PS C:\temp\test> Copy-Item -Path C:\temp\tree -Filter *.txt -Recurse -Container:$false
PS C:\temp\test> (Get-ChildItem . -Recurse).FullName
C:\temp\test\subfolder
C:\temp\test\file1.txt
C:\temp\test\file2.txt
C:\temp\test\file3.txt
C:\temp\test\file4.txt
C:\temp\test\file5.txt

PS C:\temp\test> Get-Content .\file3.txt
This is file3.txt in the subfolder
```

<span data-ttu-id="ddad7-174">`Copy-Item`Для командлета параметр **контейнера** имеет значение `$false` .</span><span class="sxs-lookup"><span data-stu-id="ddad7-174">The `Copy-Item` cmdlet has the **Container** parameter set to `$false`.</span></span> <span data-ttu-id="ddad7-175">В результате содержимое исходной папки копируется, но структура папок не сохраняется.</span><span class="sxs-lookup"><span data-stu-id="ddad7-175">This causes the contents of the source folder to be copied but does not preserve the folder structure.</span></span> <span data-ttu-id="ddad7-176">Обратите внимание, что файлы с одинаковыми именами перезаписываются в папку назначения.</span><span class="sxs-lookup"><span data-stu-id="ddad7-176">Notice that files with the same name are overwritten in the destination folder.</span></span>

## <span data-ttu-id="ddad7-177">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ddad7-177">PARAMETERS</span></span>

### <span data-ttu-id="ddad7-178">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ddad7-178">-Confirm</span></span>

<span data-ttu-id="ddad7-179">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="ddad7-179">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="ddad7-180">-Container</span><span class="sxs-lookup"><span data-stu-id="ddad7-180">-Container</span></span>

<span data-ttu-id="ddad7-181">Указывает, что этот командлет сохраняет объекты контейнера во время операции копирования.</span><span class="sxs-lookup"><span data-stu-id="ddad7-181">Indicates that this cmdlet preserves container objects during the copy operation.</span></span> <span data-ttu-id="ddad7-182">По умолчанию параметр **контейнера** имеет значение **true** .</span><span class="sxs-lookup"><span data-stu-id="ddad7-182">By default, the **Container** parameter is set to **True** .</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ddad7-183">-Credential</span><span class="sxs-lookup"><span data-stu-id="ddad7-183">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="ddad7-184">Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ddad7-184">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="ddad7-185">Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span><span class="sxs-lookup"><span data-stu-id="ddad7-185">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="ddad7-186">-Destination</span><span class="sxs-lookup"><span data-stu-id="ddad7-186">-Destination</span></span>

<span data-ttu-id="ddad7-187">Указывает путь к новому расположению.</span><span class="sxs-lookup"><span data-stu-id="ddad7-187">Specifies the path to the new location.</span></span> <span data-ttu-id="ddad7-188">Значением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="ddad7-188">The default is the current directory.</span></span>

<span data-ttu-id="ddad7-189">Чтобы переименовать копируемый элемент, укажите новое имя в значении параметра **Destination** .</span><span class="sxs-lookup"><span data-stu-id="ddad7-189">To rename the item being copied, specify a new name in the value of the **Destination** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current directory
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ddad7-190">-Exclude</span><span class="sxs-lookup"><span data-stu-id="ddad7-190">-Exclude</span></span>

<span data-ttu-id="ddad7-191">Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.</span><span class="sxs-lookup"><span data-stu-id="ddad7-191">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="ddad7-192">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="ddad7-192">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="ddad7-193">Введите элемент пути или шаблон, например `*.txt` .</span><span class="sxs-lookup"><span data-stu-id="ddad7-193">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="ddad7-194">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="ddad7-194">Wildcard characters are permitted.</span></span> <span data-ttu-id="ddad7-195">Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="ddad7-195">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="ddad7-196">-Filter</span><span class="sxs-lookup"><span data-stu-id="ddad7-196">-Filter</span></span>

<span data-ttu-id="ddad7-197">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="ddad7-197">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="ddad7-198">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров.</span><span class="sxs-lookup"><span data-stu-id="ddad7-198">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="ddad7-199">Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="ddad7-199">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="ddad7-200">Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, вместо того, чтобы PowerShell отфильтровывает объекты после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="ddad7-200">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they're retrieved.</span></span>

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

### <span data-ttu-id="ddad7-201">-Force</span><span class="sxs-lookup"><span data-stu-id="ddad7-201">-Force</span></span>

<span data-ttu-id="ddad7-202">Указывает, что этот командлет копирует элементы, которые не могут быть изменены другим способом, например копирование файла или псевдонима, доступного только для чтения.</span><span class="sxs-lookup"><span data-stu-id="ddad7-202">Indicates that this cmdlet copies items that can't otherwise be changed, such as copying over a read-only file or alias.</span></span>

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

### <span data-ttu-id="ddad7-203">-FromSession</span><span class="sxs-lookup"><span data-stu-id="ddad7-203">-FromSession</span></span>

<span data-ttu-id="ddad7-204">Указывает объект **PSSession** , из которого копируется удаленный файл.</span><span class="sxs-lookup"><span data-stu-id="ddad7-204">Specifies the **PSSession** object from which a remote file is being copied.</span></span> <span data-ttu-id="ddad7-205">При использовании этого параметра параметры **path** и **LiteralPath** ссылаются на локальный путь на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ddad7-205">When you use this parameter, the **Path** and **LiteralPath** parameters refer to the local path on the remote machine.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ddad7-206">-Include</span><span class="sxs-lookup"><span data-stu-id="ddad7-206">-Include</span></span>

<span data-ttu-id="ddad7-207">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="ddad7-207">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="ddad7-208">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="ddad7-208">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="ddad7-209">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="ddad7-209">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="ddad7-210">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="ddad7-210">Wildcard characters are permitted.</span></span> <span data-ttu-id="ddad7-211">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="ddad7-211">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="ddad7-212">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="ddad7-212">-LiteralPath</span></span>

<span data-ttu-id="ddad7-213">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="ddad7-213">Specifies a path to one or more locations.</span></span> <span data-ttu-id="ddad7-214">Значение **LiteralPath** используется точно так же, как типизировано.</span><span class="sxs-lookup"><span data-stu-id="ddad7-214">The value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="ddad7-215">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="ddad7-215">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="ddad7-216">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="ddad7-216">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="ddad7-217">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="ddad7-217">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="ddad7-218">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="ddad7-218">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="ddad7-219">-PassThru</span><span class="sxs-lookup"><span data-stu-id="ddad7-219">-PassThru</span></span>

<span data-ttu-id="ddad7-220">Возвращает объект, представляющий элемент, с которым выполняется работа.</span><span class="sxs-lookup"><span data-stu-id="ddad7-220">Returns an object that represents the item with which you're working.</span></span> <span data-ttu-id="ddad7-221">По умолчанию этот командлет не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="ddad7-221">By default, this cmdlet doesn't generate any output.</span></span>

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

### <span data-ttu-id="ddad7-222">-Path</span><span class="sxs-lookup"><span data-stu-id="ddad7-222">-Path</span></span>

<span data-ttu-id="ddad7-223">Указывает в виде массива строк путь к копируемым элементам.</span><span class="sxs-lookup"><span data-stu-id="ddad7-223">Specifies, as a string array, the path to the items to copy.</span></span> <span data-ttu-id="ddad7-224">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="ddad7-224">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="ddad7-225">-Recurse</span><span class="sxs-lookup"><span data-stu-id="ddad7-225">-Recurse</span></span>

<span data-ttu-id="ddad7-226">Указывает, что этот командлет выполняет рекурсивную копию.</span><span class="sxs-lookup"><span data-stu-id="ddad7-226">Indicates that this cmdlet does a recursive copy.</span></span>

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

### <span data-ttu-id="ddad7-227">-ToSession</span><span class="sxs-lookup"><span data-stu-id="ddad7-227">-ToSession</span></span>

<span data-ttu-id="ddad7-228">Указывает объект **PSSession** , в который копируется удаленный файл.</span><span class="sxs-lookup"><span data-stu-id="ddad7-228">Specifies the **PSSession** object to which a remote file is being copied.</span></span> <span data-ttu-id="ddad7-229">При использовании этого параметра параметр **назначения** ссылается на локальный путь на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ddad7-229">When you use this parameter, the **Destination** parameter refers to the local path on the remote machine.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ddad7-230">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ddad7-230">-WhatIf</span></span>

<span data-ttu-id="ddad7-231">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="ddad7-231">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="ddad7-232">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="ddad7-232">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="ddad7-233">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="ddad7-233">CommonParameters</span></span>

<span data-ttu-id="ddad7-234">Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="ddad7-234">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="ddad7-235">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ddad7-235">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ddad7-236">Входные данные</span><span class="sxs-lookup"><span data-stu-id="ddad7-236">INPUTS</span></span>

### <span data-ttu-id="ddad7-237">System.String</span><span class="sxs-lookup"><span data-stu-id="ddad7-237">System.String</span></span>

<span data-ttu-id="ddad7-238">В этот командлет можно передать по конвейеру строку, содержащую путь.</span><span class="sxs-lookup"><span data-stu-id="ddad7-238">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="ddad7-239">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="ddad7-239">OUTPUTS</span></span>

### <span data-ttu-id="ddad7-240">Нет или объект, представляющий скопированный элемент</span><span class="sxs-lookup"><span data-stu-id="ddad7-240">None or an object representing the copied item</span></span>

<span data-ttu-id="ddad7-241">При использовании параметра **PassThru** этот командлет возвращает объект, представляющий скопированный элемент.</span><span class="sxs-lookup"><span data-stu-id="ddad7-241">When you use the **PassThru** parameter, this cmdlet returns an object that represents the copied item.</span></span> <span data-ttu-id="ddad7-242">В противном случае этот командлет не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="ddad7-242">Otherwise, this cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="ddad7-243">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="ddad7-243">NOTES</span></span>

<span data-ttu-id="ddad7-244">Этот командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="ddad7-244">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="ddad7-245">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="ddad7-245">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="ddad7-246">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="ddad7-246">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="ddad7-247">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ddad7-247">RELATED LINKS</span></span>

[<span data-ttu-id="ddad7-248">about_Providers</span><span class="sxs-lookup"><span data-stu-id="ddad7-248">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="ddad7-249">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="ddad7-249">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="ddad7-250">Get-Item</span><span class="sxs-lookup"><span data-stu-id="ddad7-250">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="ddad7-251">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="ddad7-251">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="ddad7-252">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="ddad7-252">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="ddad7-253">Move-Item</span><span class="sxs-lookup"><span data-stu-id="ddad7-253">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="ddad7-254">New-Item</span><span class="sxs-lookup"><span data-stu-id="ddad7-254">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="ddad7-255">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="ddad7-255">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="ddad7-256">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="ddad7-256">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="ddad7-257">Set-Item</span><span class="sxs-lookup"><span data-stu-id="ddad7-257">Set-Item</span></span>](Set-Item.md)

