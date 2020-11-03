---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-childitem?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ChildItem
ms.openlocfilehash: f8a2276b6121958aedc4eb297d0565b369ee401f
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225570"
---
# <span data-ttu-id="7910e-103">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="7910e-103">Get-ChildItem</span></span>

## <span data-ttu-id="7910e-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="7910e-104">SYNOPSIS</span></span>

<span data-ttu-id="7910e-105">Получает элементы и дочерние элементы в одном или нескольких указанных расположениях</span><span class="sxs-lookup"><span data-stu-id="7910e-105">Gets the items and child items in one or more specified locations.</span></span>

## <span data-ttu-id="7910e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7910e-106">SYNTAX</span></span>

### <span data-ttu-id="7910e-107">Элементы (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="7910e-107">Items (Default)</span></span>

```
Get-ChildItem [[-Path] <string[]>] [[-Filter] <string>] [-Include <string[]>] [-Exclude <string[]>]
 [-Recurse] [-Depth <uint32>] [-Force] [-Name] [-Attributes <FlagsExpression[FileAttributes]>]
 [-FollowSymlink] [-Directory] [-File] [-Hidden] [-ReadOnly] [-System] [<CommonParameters>]
```

### <span data-ttu-id="7910e-108">литералитемс</span><span class="sxs-lookup"><span data-stu-id="7910e-108">LiteralItems</span></span>

```
Get-ChildItem [[-Filter] <string>] -LiteralPath <string[]> [-Include <string[]>]
 [-Exclude <string[]>] [-Recurse] [-Depth <uint32>] [-Force] [-Name]
 [-Attributes <FlagsExpression[FileAttributes]>] [-FollowSymlink] [-Directory] [-File] [-Hidden]
 [-ReadOnly] [-System] [<CommonParameters>]
```

## <span data-ttu-id="7910e-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7910e-109">DESCRIPTION</span></span>

<span data-ttu-id="7910e-110">`Get-ChildItem`Командлет возвращает элементы в одном или нескольких указанных расположениях.</span><span class="sxs-lookup"><span data-stu-id="7910e-110">The `Get-ChildItem` cmdlet gets the items in one or more specified locations.</span></span> <span data-ttu-id="7910e-111">Если элемент является контейнером, командлет получает элементы внутри контейнера, называемые дочерними элементами.</span><span class="sxs-lookup"><span data-stu-id="7910e-111">If the item is a container, it gets the items inside the container, known as child items.</span></span> <span data-ttu-id="7910e-112">Можно использовать параметр **рекурсии** для получения элементов во всех дочерних контейнерах и использовать параметр **Depth** , чтобы ограничить число уровней для рекурсии.</span><span class="sxs-lookup"><span data-stu-id="7910e-112">You can use the **Recurse** parameter to get items in all child containers and use the **Depth** parameter to limit the number of levels to recurse.</span></span>

<span data-ttu-id="7910e-113">`Get-ChildItem` не отображает пустые каталоги.</span><span class="sxs-lookup"><span data-stu-id="7910e-113">`Get-ChildItem` doesn't display empty directories.</span></span> <span data-ttu-id="7910e-114">Если `Get-ChildItem` команда содержит **глубину** или **Рекурсивные** параметры, в выходные данные не включаются пустые каталоги.</span><span class="sxs-lookup"><span data-stu-id="7910e-114">When a `Get-ChildItem` command includes the **Depth** or **Recurse** parameters, empty directories aren't included in the output.</span></span>

<span data-ttu-id="7910e-115">Расположения предоставляются `Get-ChildItem` поставщиками PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7910e-115">Locations are exposed to `Get-ChildItem` by PowerShell providers.</span></span> <span data-ttu-id="7910e-116">Расположением может быть каталог файловой системы, куст реестра или хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="7910e-116">A location can be a file system directory, registry hive, or a certificate store.</span></span> <span data-ttu-id="7910e-117">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="7910e-117">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="7910e-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="7910e-118">EXAMPLES</span></span>

### <span data-ttu-id="7910e-119">Пример 1. Получение дочерних элементов из каталога файловой системы</span><span class="sxs-lookup"><span data-stu-id="7910e-119">Example 1: Get child items from a file system directory</span></span>

<span data-ttu-id="7910e-120">Этот пример получает дочерние элементы из каталога файловой системы.</span><span class="sxs-lookup"><span data-stu-id="7910e-120">This example gets the child items from a file system directory.</span></span> <span data-ttu-id="7910e-121">Отобразятся имена файлов и подкаталогов.</span><span class="sxs-lookup"><span data-stu-id="7910e-121">The filenames and subdirectory names are displayed.</span></span> <span data-ttu-id="7910e-122">Для пустых расположений команда не возвращает никаких выходных данных и возвращается в командную строку PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7910e-122">For empty locations, the command doesn't return any output and returns to the PowerShell prompt.</span></span>

<span data-ttu-id="7910e-123">`Get-ChildItem`Командлет использует параметр **path** для указания каталога `C:\Test` .</span><span class="sxs-lookup"><span data-stu-id="7910e-123">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory `C:\Test`.</span></span>
<span data-ttu-id="7910e-124">`Get-ChildItem` Отображает файлы и каталоги в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7910e-124">`Get-ChildItem` displays the files and directories in the PowerShell console.</span></span>

```powershell
Get-ChildItem -Path C:\Test
```

```Output
   Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/15/2019     08:29                Logs
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-a----         2/1/2019     08:43            183 CreateTestFile.ps1
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
```

<span data-ttu-id="7910e-125">По умолчанию `Get-ChildItem` перечисляет режим ( **атрибуты** ), **LastWriteTime** , размер файла ( **Длина** ) и **имя** элемента.</span><span class="sxs-lookup"><span data-stu-id="7910e-125">By default `Get-ChildItem` lists the mode ( **Attributes** ), **LastWriteTime** , file size ( **Length** ), and the **Name** of the item.</span></span> <span data-ttu-id="7910e-126">Буквы в свойстве **mode** можно интерпретировать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7910e-126">The letters in the **Mode** property can be interpreted as follows:</span></span>

- <span data-ttu-id="7910e-127">`l` ссылку</span><span class="sxs-lookup"><span data-stu-id="7910e-127">`l` (link)</span></span>
- <span data-ttu-id="7910e-128">`d` каталоги</span><span class="sxs-lookup"><span data-stu-id="7910e-128">`d` (directory)</span></span>
- <span data-ttu-id="7910e-129">`a` упражнени</span><span class="sxs-lookup"><span data-stu-id="7910e-129">`a` (archive)</span></span>
- <span data-ttu-id="7910e-130">`r` (только для чтения)</span><span class="sxs-lookup"><span data-stu-id="7910e-130">`r` (read-only)</span></span>
- <span data-ttu-id="7910e-131">`h` служеб</span><span class="sxs-lookup"><span data-stu-id="7910e-131">`h` (hidden)</span></span>
- <span data-ttu-id="7910e-132">`s` (система).</span><span class="sxs-lookup"><span data-stu-id="7910e-132">`s` (system).</span></span>

<span data-ttu-id="7910e-133">Дополнительные сведения о флагах режима см. в разделе [about_Filesystem_Provider](../microsoft.powershell.core/about/about_filesystem_provider.md#attributes-flagsexpression).</span><span class="sxs-lookup"><span data-stu-id="7910e-133">For more information about the mode flags, see [about_Filesystem_Provider](../microsoft.powershell.core/about/about_filesystem_provider.md#attributes-flagsexpression).</span></span>

### <span data-ttu-id="7910e-134">Пример 2. Получение имен дочерних элементов в каталоге</span><span class="sxs-lookup"><span data-stu-id="7910e-134">Example 2: Get child item names in a directory</span></span>

<span data-ttu-id="7910e-135">В этом примере выводятся только имена элементов в каталоге.</span><span class="sxs-lookup"><span data-stu-id="7910e-135">This example lists only the names of items in a directory.</span></span>

<span data-ttu-id="7910e-136">`Get-ChildItem`Командлет использует параметр **path** для указания каталога `C:\Test` .</span><span class="sxs-lookup"><span data-stu-id="7910e-136">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory `C:\Test`.</span></span> <span data-ttu-id="7910e-137">Параметр **Name** возвращает только имена файлов или каталогов из указанного пути.</span><span class="sxs-lookup"><span data-stu-id="7910e-137">The **Name** parameter returns only the file or directory names from the specified path.</span></span>

```powershell
Get-ChildItem -Path C:\Test -Name
```

```Output
Logs
anotherfile.txt
Command.txt
CreateTestFile.ps1
ReadOnlyFile.txt
```

### <span data-ttu-id="7910e-138">Пример 3. Получение дочерних элементов в текущем каталоге и подкаталогах</span><span class="sxs-lookup"><span data-stu-id="7910e-138">Example 3: Get child items in the current directory and subdirectories</span></span>

<span data-ttu-id="7910e-139">В этом примере отображаются **txt** файлы, расположенные в текущем каталоге и его подкаталогах.</span><span class="sxs-lookup"><span data-stu-id="7910e-139">This example displays **.txt** files that are located in the current directory and its subdirectories.</span></span>

```powershell
Get-ChildItem -Path C:\Test\*.txt -Recurse -Force
```

```Output
    Directory: C:\Test\Logs\Adirectory

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/12/2019     16:16             20 Afile4.txt
-a-h--        2/12/2019     15:52             22 hiddenfile.txt
-a----        2/13/2019     13:26             20 LogFile4.txt

    Directory: C:\Test\Logs\Backup

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/12/2019     16:16             20 ATextFile.txt
-a----        2/12/2019     15:50             20 LogFile3.txt

    Directory: C:\Test\Logs

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/12/2019     16:16             20 Afile.txt
-a-h--        2/12/2019     15:52             22 hiddenfile.txt
-a----        2/13/2019     13:26             20 LogFile1.txt

    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-a-h--        2/12/2019     15:52             22 hiddenfile.txt
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
```

<span data-ttu-id="7910e-140">`Get-ChildItem`Командлет использует параметр **path** для указания `C:\Test\*.txt` .</span><span class="sxs-lookup"><span data-stu-id="7910e-140">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify `C:\Test\*.txt`.</span></span> <span data-ttu-id="7910e-141">В **пути** используется `*` подстановочный знак звездочки () для указания всех файлов с расширением имени файла `.txt` .</span><span class="sxs-lookup"><span data-stu-id="7910e-141">**Path** uses the asterisk (`*`) wildcard to specify all files with the filename extension `.txt`.</span></span> <span data-ttu-id="7910e-142">Параметр **рекурсии** выполняет поиск в каталоге **пути к** подкаталогам, как показано в **каталоге:** заголовки.</span><span class="sxs-lookup"><span data-stu-id="7910e-142">The **Recurse** parameter searches the **Path** directory its subdirectories, as shown in the **Directory:** headings.</span></span> <span data-ttu-id="7910e-143">Параметр **Force** отображает скрытые файлы `hiddenfile.txt` , например, с режимом **h**.</span><span class="sxs-lookup"><span data-stu-id="7910e-143">The **Force** parameter displays hidden files such as `hiddenfile.txt` that have a mode of **h**.</span></span>

### <span data-ttu-id="7910e-144">Пример 4. Получение дочерних элементов с помощью параметра Include</span><span class="sxs-lookup"><span data-stu-id="7910e-144">Example 4: Get child items using the Include parameter</span></span>

<span data-ttu-id="7910e-145">В этом примере `Get-ChildItem` параметр **include** используется для поиска определенных элементов из каталога, указанного параметром **path** .</span><span class="sxs-lookup"><span data-stu-id="7910e-145">In this example `Get-ChildItem` uses the **Include** parameter to find specific items from the directory specified by the **Path** parameter.</span></span>

```powershell
# When using the -Include parameter, if you don't include an asterisk in the path
# the command returns no output.
Get-ChildItem -Path C:\Test\ -Include *.txt
```

```Output

```

```powershell
Get-ChildItem -Path C:\Test\* -Include *.txt
```

```Output
    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
```

<span data-ttu-id="7910e-146">`Get-ChildItem`Командлет использует параметр **path** для указания каталога **C:\test**.</span><span class="sxs-lookup"><span data-stu-id="7910e-146">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory **C:\Test**.</span></span> <span data-ttu-id="7910e-147">Параметр **path** включает в себя `*` подстановочный знак звездочки () для указания содержимого каталога.</span><span class="sxs-lookup"><span data-stu-id="7910e-147">The **Path** parameter includes a trailing asterisk (`*`) wildcard to specify the directory's contents.</span></span>
<span data-ttu-id="7910e-148">Параметр **include** использует `*` подстановочный знак звездочки (), чтобы указать все файлы с расширением **txt**.</span><span class="sxs-lookup"><span data-stu-id="7910e-148">The **Include** parameter uses an asterisk (`*`) wildcard to specify all files with the file name extension **.txt**.</span></span>

<span data-ttu-id="7910e-149">Если используется параметр **include** , для указания содержимого каталога параметру **path** требуется символ-шаблон звездочки ( `*` ).</span><span class="sxs-lookup"><span data-stu-id="7910e-149">When the **Include** parameter is used, the **Path** parameter needs a trailing asterisk (`*`) wildcard to specify the directory's contents.</span></span> <span data-ttu-id="7910e-150">Например, `-Path C:\Test\*`.</span><span class="sxs-lookup"><span data-stu-id="7910e-150">For example, `-Path C:\Test\*`.</span></span>

- <span data-ttu-id="7910e-151">Если в команду добавляется **рекурсивный** параметр, то символ звездочки ( `*` ) в параметре **path** является необязательным.</span><span class="sxs-lookup"><span data-stu-id="7910e-151">If the **Recurse** parameter is added to the command, the trailing asterisk (`*`) in the **Path** parameter is optional.</span></span> <span data-ttu-id="7910e-152">Параметр **рекурсии** возвращает элементы из каталога **пути** и его подкаталогов.</span><span class="sxs-lookup"><span data-stu-id="7910e-152">The **Recurse** parameter gets items from the **Path** directory and its subdirectories.</span></span> <span data-ttu-id="7910e-153">Например `-Path C:\Test\ -Recurse -Include *.txt`.</span><span class="sxs-lookup"><span data-stu-id="7910e-153">For example, `-Path C:\Test\ -Recurse -Include *.txt`</span></span>
- <span data-ttu-id="7910e-154">Если конечная звездочка ( `*` ) не включена в параметр **path** , команда не возвращает никаких выходных данных и возвращается в командную строку PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7910e-154">If a trailing asterisk (`*`) isn't included in the **Path** parameter, the command doesn't return any output and returns to the PowerShell prompt.</span></span> <span data-ttu-id="7910e-155">Например, `-Path C:\Test\`.</span><span class="sxs-lookup"><span data-stu-id="7910e-155">For example, `-Path C:\Test\`.</span></span>

### <span data-ttu-id="7910e-156">Пример 5. Получение дочерних элементов с помощью параметра Exclude</span><span class="sxs-lookup"><span data-stu-id="7910e-156">Example 5: Get child items using the Exclude parameter</span></span>

<span data-ttu-id="7910e-157">В выходных данных примера показано содержимое каталога **к:\тест\логс**.</span><span class="sxs-lookup"><span data-stu-id="7910e-157">The example's output shows the contents of the directory **C:\Test\Logs**.</span></span> <span data-ttu-id="7910e-158">Выходные данные представляют собой ссылку на другие команды, в которых используются параметры **Exclude** и **recurse** .</span><span class="sxs-lookup"><span data-stu-id="7910e-158">The output is a reference for the other commands that use the **Exclude** and **Recurse** parameters.</span></span>

```powershell
Get-ChildItem -Path C:\Test\Logs
```

```Output
    Directory: C:\Test\Logs

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/15/2019     13:21                Adirectory
d-----        2/15/2019     08:28                AnEmptyDirectory
d-----        2/15/2019     13:21                Backup
-a----        2/12/2019     16:16             20 Afile.txt
-a----        2/13/2019     13:26             20 LogFile1.txt
-a----        2/12/2019     16:24             23 systemlog1.log
```

```powershell
Get-ChildItem -Path C:\Test\Logs\* -Exclude A*
```

```Output
    Directory: C:\Test\Logs

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/15/2019     13:21                Backup
-a----        2/13/2019     13:26             20 LogFile1.txt
-a----        2/12/2019     16:24             23 systemlog1.log
```

<span data-ttu-id="7910e-159">`Get-ChildItem`Командлет использует параметр **path** для указания каталога `C:\Test\Logs` .</span><span class="sxs-lookup"><span data-stu-id="7910e-159">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory `C:\Test\Logs`.</span></span>
<span data-ttu-id="7910e-160">Параметр **Exclude** использует `*` подстановочный знак звездочки (), чтобы указать файлы или каталоги, которые **A** начинаются с **a** или, исключаются из выходных данных.</span><span class="sxs-lookup"><span data-stu-id="7910e-160">The **Exclude** parameter uses the asterisk (`*`) wildcard to specify any files or directories that begin with **A** or **a** are excluded from the output.</span></span>

<span data-ttu-id="7910e-161">При использовании параметра **Exclude** символ звездочки ( `*` ) в параметре **path** является необязательным.</span><span class="sxs-lookup"><span data-stu-id="7910e-161">When the **Exclude** parameter is used, a trailing asterisk (`*`) in the **Path** parameter is optional.</span></span> <span data-ttu-id="7910e-162">Например, `-Path C:\Test\Logs` или `-Path C:\Test\Logs\*`.</span><span class="sxs-lookup"><span data-stu-id="7910e-162">For example, `-Path C:\Test\Logs` or `-Path C:\Test\Logs\*`.</span></span>

- <span data-ttu-id="7910e-163">Если конечная звездочка ( `*` ) не включена в параметр **path** , отображается содержимое параметра **path** .</span><span class="sxs-lookup"><span data-stu-id="7910e-163">If a trailing asterisk (`*`) isn't included in the **Path** parameter, the contents of the **Path** parameter are displayed.</span></span> <span data-ttu-id="7910e-164">Исключениями являются имена файлов или подкаталогов, соответствующие значению параметра **Exclude** .</span><span class="sxs-lookup"><span data-stu-id="7910e-164">The exceptions are filenames or subdirectory names that match the **Exclude** parameter's value.</span></span>
- <span data-ttu-id="7910e-165">Если в параметр пути включена конечная звездочка ( `*` ) **Path** , команда выполняет рекурсивный путь к подкаталогам параметра **path** .</span><span class="sxs-lookup"><span data-stu-id="7910e-165">If a trailing asterisk (`*`) is included in the **Path** parameter, the command recurses into the **Path** parameter's subdirectories.</span></span> <span data-ttu-id="7910e-166">Исключениями являются имена файлов или подкаталогов, соответствующие значению параметра **Exclude** .</span><span class="sxs-lookup"><span data-stu-id="7910e-166">The exceptions are filenames or subdirectory names that match the **Exclude** parameter's value.</span></span>
- <span data-ttu-id="7910e-167">Если в команду добавляется **рекурсивный** параметр, то выходные данные рекурсии одинаковы, независимо от того, содержит ли параметр **пути** конечную звездочку ( `*` ).</span><span class="sxs-lookup"><span data-stu-id="7910e-167">If the **Recurse** parameter is added to the command, the recursion output is the same whether or not the **Path** parameter includes a trailing asterisk (`*`).</span></span>

### <span data-ttu-id="7910e-168">Пример 6. получение разделов реестра из куста реестра</span><span class="sxs-lookup"><span data-stu-id="7910e-168">Example 6: Get the registry keys from a registry hive</span></span>

<span data-ttu-id="7910e-169">Этот пример получает все разделы реестра из `HKEY_LOCAL_MACHINE\HARDWARE` .</span><span class="sxs-lookup"><span data-stu-id="7910e-169">This example gets all the registry keys from `HKEY_LOCAL_MACHINE\HARDWARE`.</span></span>

<span data-ttu-id="7910e-170">`Get-ChildItem` использует параметр **path** для указания раздела реестра `HKLM:\HARDWARE` .</span><span class="sxs-lookup"><span data-stu-id="7910e-170">`Get-ChildItem` uses the **Path** parameter to specify the registry key `HKLM:\HARDWARE`.</span></span> <span data-ttu-id="7910e-171">Путь к кусту и его верхний уровень разделов реестра отображаются в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7910e-171">The hive's path and top level of registry keys are displayed in the PowerShell console.</span></span>

<span data-ttu-id="7910e-172">Дополнительные сведения см. в разделе [about_Registry_Provider](../Microsoft.PowerShell.Core/About/about_Registry_Provider.md).</span><span class="sxs-lookup"><span data-stu-id="7910e-172">For more information, see [about_Registry_Provider](../Microsoft.PowerShell.Core/About/about_Registry_Provider.md).</span></span>

```powershell
Get-ChildItem -Path HKLM:\HARDWARE
```

```Output
    Hive: HKEY_LOCAL_MACHINE\HARDWARE

Name             Property
----             --------
ACPI
DESCRIPTION
DEVICEMAP
RESOURCEMAP
UEFI
```

```powershell
Get-ChildItem -Path HKLM:\HARDWARE -Exclude D*
```

```Output
   Hive: HKEY_LOCAL_MACHINE\HARDWARE

Name                           Property
----                           --------
ACPI
RESOURCEMAP
```

<span data-ttu-id="7910e-173">Первая команда отображает содержимое `HKLM:\HARDWARE` раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="7910e-173">The first command shows the contents of the `HKLM:\HARDWARE` registry key.</span></span> <span data-ttu-id="7910e-174">Параметр **Exclude** `Get-ChildItem` не возвращает никаких подразделов, начинающихся с `D*` .</span><span class="sxs-lookup"><span data-stu-id="7910e-174">The **Exclude** parameter tells `Get-ChildItem` not to return any subkeys that start with `D*`.</span></span> <span data-ttu-id="7910e-175">В настоящее время параметр **Exclude** работает только для подразделов, а не для свойств элемента.</span><span class="sxs-lookup"><span data-stu-id="7910e-175">Currently, the **Exclude** parameter only works on subkeys, not item properties.</span></span>

### <span data-ttu-id="7910e-176">Пример 7. получение всех сертификатов с помощью центра подписывания кода</span><span class="sxs-lookup"><span data-stu-id="7910e-176">Example 7: Get all certificates with code-signing authority</span></span>

<span data-ttu-id="7910e-177">В этом примере каждый сертификат создается на диске **сертификата PowerShell:** с центром подписывания кода.</span><span class="sxs-lookup"><span data-stu-id="7910e-177">This example gets each certificate in the PowerShell **Cert:** drive that has code-signing authority.</span></span>

<span data-ttu-id="7910e-178">`Get-ChildItem`Командлет использует параметр **path** для указания **CERT:** provider.</span><span class="sxs-lookup"><span data-stu-id="7910e-178">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the **Cert:** provider.</span></span> <span data-ttu-id="7910e-179">Параметр **рекурсии** выполняет поиск в каталоге, указанном по **пути** и его подкаталогам.</span><span class="sxs-lookup"><span data-stu-id="7910e-179">The **Recurse** parameter searches the directory specified by **Path** and its subdirectories.</span></span> <span data-ttu-id="7910e-180">Параметр **CodeSigningCert** возвращает только сертификаты, имеющие центр подписывания кода.</span><span class="sxs-lookup"><span data-stu-id="7910e-180">The **CodeSigningCert** parameter gets only certificates that have code-signing authority.</span></span>

```powershell
Get-ChildItem -Path Cert:\* -Recurse -CodeSigningCert
```

<span data-ttu-id="7910e-181">Дополнительные сведения о поставщике сертификатов и диске CERT: см. в разделе [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span><span class="sxs-lookup"><span data-stu-id="7910e-181">For more information about the Certificate provider and the Cert: drive, see [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span></span>

### <span data-ttu-id="7910e-182">Пример 8. Получение элементов с помощью параметра Depth</span><span class="sxs-lookup"><span data-stu-id="7910e-182">Example 8: Get items using the Depth parameter</span></span>

<span data-ttu-id="7910e-183">В этом примере отображаются элементы в каталоге и его подкаталогах.</span><span class="sxs-lookup"><span data-stu-id="7910e-183">This example displays the items in a directory and its subdirectories.</span></span> <span data-ttu-id="7910e-184">Параметр **Depth** определяет число уровней подкаталогов, включаемых в рекурсию.</span><span class="sxs-lookup"><span data-stu-id="7910e-184">The **Depth** parameter determines the number of subdirectory levels to include in the recursion.</span></span> <span data-ttu-id="7910e-185">Пустые каталоги исключаются из выходных данных.</span><span class="sxs-lookup"><span data-stu-id="7910e-185">Empty directories are excluded from the output.</span></span>

```powershell
Get-ChildItem -Path C:\Parent -Depth 2
```

```Output
    Directory: C:\Parent

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/14/2019     10:24                SubDir_Level1
-a----        2/13/2019     08:55             26 file.txt

    Directory: C:\Parent\SubDir_Level1

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/14/2019     10:24                SubDir_Level2
-a----        2/13/2019     08:55             26 file.txt

    Directory: C:\Parent\SubDir_Level1\SubDir_Level2

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/14/2019     10:22                SubDir_Level3
-a----        2/13/2019     08:55             26 file.txt
```

<span data-ttu-id="7910e-186">`Get-ChildItem`Командлет использует параметр **path** для указания **к:\парент**.</span><span class="sxs-lookup"><span data-stu-id="7910e-186">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify **C:\Parent**.</span></span> <span data-ttu-id="7910e-187">Параметр **Depth** указывает два уровня рекурсии.</span><span class="sxs-lookup"><span data-stu-id="7910e-187">The **Depth** parameter specifies two levels of recursion.</span></span> <span data-ttu-id="7910e-188">`Get-ChildItem` Отображает содержимое каталога, указанного параметром **path** , и двух уровней вложенных каталогов.</span><span class="sxs-lookup"><span data-stu-id="7910e-188">`Get-ChildItem` displays the contents of the directory specified by the **Path** parameter and the two levels of subdirectories.</span></span>

### <span data-ttu-id="7910e-189">Пример 9. Получение сведений о жесткой связи</span><span class="sxs-lookup"><span data-stu-id="7910e-189">Example 9: Getting hard link information</span></span>

<span data-ttu-id="7910e-190">В PowerShell 6,2 для получения сведений о жесткой связи было добавлено альтернативное представление.</span><span class="sxs-lookup"><span data-stu-id="7910e-190">In PowerShell 6.2, an alternate view was added to get hard link information.</span></span>

```powershell
Get-ChildItem -Path C:\PathContainingHardLink | Format-Table -View childrenWithHardLink
```

### <span data-ttu-id="7910e-191">Пример 9. выходные данные для экспериментальной Псуниксфилестат функции</span><span class="sxs-lookup"><span data-stu-id="7910e-191">Example 9: Output for experimental feature PSUnixFileStat</span></span>

<span data-ttu-id="7910e-192">В PowerShell 7 в системах UNIX экспериментальная функция **псуниксфилестат** предоставляет выходные данные, подобные UNIX:</span><span class="sxs-lookup"><span data-stu-id="7910e-192">In PowerShell 7 on Unix systems, the experimental feature **PSUnixFileStat** provides Unix-like output:</span></span>

```powershell
PS> Get-ChildItem /etc/r*
```

```Output
    Directory: /etc

UnixMode   User Group    LastWriteTime Size Name
--------   ---- -----    ------------- ---- ----
drwxr-xr-x root wheel  9/30/2019 19:19  128 racoon
-rw-r--r-- root wheel  9/26/2019 18:20 1560 rc.common
-rw-r--r-- root wheel  7/31/2017 17:30 1560 rc.common~previous
-rw-r--r-- root wheel  9/27/2019 20:34 5264 rc.netboot
lrwxr-xr-x root wheel  11/8/2019 15:35   22 resolv.conf -> /private/var/run/resolv.conf
-rw-r--r-- root wheel 10/23/2019 17:41    0 rmtab
-rw-r--r-- root wheel 10/23/2019 17:41 1735 rpc
-rw-r--r-- root wheel  7/25/2017 18:37 1735 rpc~previous
-rw-r--r-- root wheel 10/23/2019 18:42  891 rtadvd.conf
-rw-r--r-- root wheel  8/24/2017 21:54  891 rtadvd.conf~previous
```

<span data-ttu-id="7910e-193">Новые свойства, которые теперь являются частью выходных данных:</span><span class="sxs-lookup"><span data-stu-id="7910e-193">The new properties that are now part of the output are:</span></span>

- <span data-ttu-id="7910e-194">**Униксмоде** — это разрешения файла, представленные в системе UNIX.</span><span class="sxs-lookup"><span data-stu-id="7910e-194">**UnixMode** is the file permissions as represented on a Unix system</span></span>
- <span data-ttu-id="7910e-195">**Пользователь** является владельцем файла</span><span class="sxs-lookup"><span data-stu-id="7910e-195">**User** is the file owner</span></span>
- <span data-ttu-id="7910e-196">**Группа** является владельцем группы</span><span class="sxs-lookup"><span data-stu-id="7910e-196">**Group** is the group owner</span></span>
- <span data-ttu-id="7910e-197">**Размер** — это размер файла или каталога, представленный в системе UNIX.</span><span class="sxs-lookup"><span data-stu-id="7910e-197">**Size** is the size of the file or directory as represented on a Unix system</span></span>

## <span data-ttu-id="7910e-198">Параметры</span><span class="sxs-lookup"><span data-stu-id="7910e-198">Parameters</span></span>

### <span data-ttu-id="7910e-199">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7910e-199">-Attributes</span></span>

<span data-ttu-id="7910e-200">Извлекает файлы и папки с указанными атрибутами.</span><span class="sxs-lookup"><span data-stu-id="7910e-200">Gets files and folders with the specified attributes.</span></span> <span data-ttu-id="7910e-201">Этот параметр поддерживает все атрибуты и позволяет указывать сложные сочетания атрибутов.</span><span class="sxs-lookup"><span data-stu-id="7910e-201">This parameter supports all attributes and lets you specify complex combinations of attributes.</span></span>

<span data-ttu-id="7910e-202">Например, чтобы извлечь зашифрованные или сжатые файлы, не являющиеся системными (которые не являются каталогами), введите следующее:</span><span class="sxs-lookup"><span data-stu-id="7910e-202">For example, to get non-system files (not directories) that are encrypted or compressed, type:</span></span>

`Get-ChildItem -Attributes !Directory+!System+Encrypted, !Directory+!System+Compressed`

<span data-ttu-id="7910e-203">Чтобы найти файлы и папки с часто используемыми атрибутами, используйте параметр **Attributes** .</span><span class="sxs-lookup"><span data-stu-id="7910e-203">To find files and folders with commonly used attributes, use the **Attributes** parameter.</span></span> <span data-ttu-id="7910e-204">Или — **Каталог** параметров, **файл** , **скрытый** , **только для чтения** и **System**.</span><span class="sxs-lookup"><span data-stu-id="7910e-204">Or, the parameters **Directory** , **File** , **Hidden** , **ReadOnly** , and **System**.</span></span>

<span data-ttu-id="7910e-205">Параметр **Attributes** поддерживает следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="7910e-205">The **Attributes** parameter supports the following properties:</span></span>

- <span data-ttu-id="7910e-206">**Архив**</span><span class="sxs-lookup"><span data-stu-id="7910e-206">**Archive**</span></span>
- <span data-ttu-id="7910e-207">**Compressed**</span><span class="sxs-lookup"><span data-stu-id="7910e-207">**Compressed**</span></span>
- <span data-ttu-id="7910e-208">**Устройство**</span><span class="sxs-lookup"><span data-stu-id="7910e-208">**Device**</span></span>
- <span data-ttu-id="7910e-209">**Каталог**</span><span class="sxs-lookup"><span data-stu-id="7910e-209">**Directory**</span></span>
- <span data-ttu-id="7910e-210">**Зашифрована**</span><span class="sxs-lookup"><span data-stu-id="7910e-210">**Encrypted**</span></span>
- <span data-ttu-id="7910e-211">**Скрыта**</span><span class="sxs-lookup"><span data-stu-id="7910e-211">**Hidden**</span></span>
- <span data-ttu-id="7910e-212">**интегритистреам**</span><span class="sxs-lookup"><span data-stu-id="7910e-212">**IntegrityStream**</span></span>
- <span data-ttu-id="7910e-213">**Обычный**</span><span class="sxs-lookup"><span data-stu-id="7910e-213">**Normal**</span></span>
- <span data-ttu-id="7910e-214">**носкрубдата**</span><span class="sxs-lookup"><span data-stu-id="7910e-214">**NoScrubData**</span></span>
- <span data-ttu-id="7910e-215">**нотконтентиндексед**</span><span class="sxs-lookup"><span data-stu-id="7910e-215">**NotContentIndexed**</span></span>
- <span data-ttu-id="7910e-216">**Работа**</span><span class="sxs-lookup"><span data-stu-id="7910e-216">**Offline**</span></span>
- <span data-ttu-id="7910e-217">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="7910e-217">**ReadOnly**</span></span>
- <span data-ttu-id="7910e-218">**репарсепоинт**</span><span class="sxs-lookup"><span data-stu-id="7910e-218">**ReparsePoint**</span></span>
- <span data-ttu-id="7910e-219">**спарсефиле**</span><span class="sxs-lookup"><span data-stu-id="7910e-219">**SparseFile**</span></span>
- <span data-ttu-id="7910e-220">**Системные функции**</span><span class="sxs-lookup"><span data-stu-id="7910e-220">**System**</span></span>
- <span data-ttu-id="7910e-221">**Временные процедуры**</span><span class="sxs-lookup"><span data-stu-id="7910e-221">**Temporary**</span></span>

<span data-ttu-id="7910e-222">Описание этих атрибутов см. в описании [перечисления FileAttributes](/dotnet/api/system.io.fileattributes).</span><span class="sxs-lookup"><span data-stu-id="7910e-222">For a description of these attributes, see the [FileAttributes Enumeration](/dotnet/api/system.io.fileattributes).</span></span>

<span data-ttu-id="7910e-223">Чтобы объединить атрибуты, используйте следующие операторы:</span><span class="sxs-lookup"><span data-stu-id="7910e-223">To combine attributes, use the following operators:</span></span>

- <span data-ttu-id="7910e-224">`!` НЕДОСТАТОЧНО</span><span class="sxs-lookup"><span data-stu-id="7910e-224">`!` (NOT)</span></span>
- <span data-ttu-id="7910e-225">`+` ПЕРЕТАСКИВАНИ</span><span class="sxs-lookup"><span data-stu-id="7910e-225">`+` (AND)</span></span>
- <span data-ttu-id="7910e-226">`,` НИ</span><span class="sxs-lookup"><span data-stu-id="7910e-226">`,` (OR)</span></span>

<span data-ttu-id="7910e-227">Не используйте пробелы между оператором и его атрибутом.</span><span class="sxs-lookup"><span data-stu-id="7910e-227">Don't use spaces between an operator and its attribute.</span></span> <span data-ttu-id="7910e-228">Пробелы принимаются после запятых.</span><span class="sxs-lookup"><span data-stu-id="7910e-228">Spaces are accepted after commas.</span></span>

<span data-ttu-id="7910e-229">Для общих атрибутов используйте следующие сокращения:</span><span class="sxs-lookup"><span data-stu-id="7910e-229">For common attributes, use the following abbreviations:</span></span>

- <span data-ttu-id="7910e-230">`D` Каталоги</span><span class="sxs-lookup"><span data-stu-id="7910e-230">`D` (Directory)</span></span>
- <span data-ttu-id="7910e-231">`H` Служеб</span><span class="sxs-lookup"><span data-stu-id="7910e-231">`H` (Hidden)</span></span>
- <span data-ttu-id="7910e-232">`R` (Только для чтения)</span><span class="sxs-lookup"><span data-stu-id="7910e-232">`R` (Read-only)</span></span>
- <span data-ttu-id="7910e-233">`S` Системой</span><span class="sxs-lookup"><span data-stu-id="7910e-233">`S` (System)</span></span>

```yaml
Type: System.Management.Automation.FlagsExpression`1[System.IO.FileAttributes]
Parameter Sets: (All)
Aliases:
Accepted values: Archive, Compressed, Device, Directory, Encrypted, Hidden, IntegrityStream, Normal, NoScrubData, NotContentIndexed, Offline, ReadOnly, ReparsePoint, SparseFile, System, Temporary

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7910e-234">-Depth</span><span class="sxs-lookup"><span data-stu-id="7910e-234">-Depth</span></span>

<span data-ttu-id="7910e-235">Этот параметр был добавлен в PowerShell 5,0 и позволяет управлять глубиной рекурсии.</span><span class="sxs-lookup"><span data-stu-id="7910e-235">This parameter was added in PowerShell 5.0 and enables you to control the depth of recursion.</span></span> <span data-ttu-id="7910e-236">По умолчанию `Get-ChildItem` отображает содержимое родительского каталога.</span><span class="sxs-lookup"><span data-stu-id="7910e-236">By default, `Get-ChildItem` displays the contents of the parent directory.</span></span> <span data-ttu-id="7910e-237">Параметр **Depth** определяет количество уровней подкаталогов, включаемых в рекурсию, и отображает содержимое.</span><span class="sxs-lookup"><span data-stu-id="7910e-237">The **Depth** parameter determines the number of subdirectory levels that are included in the recursion and displays the contents.</span></span>

<span data-ttu-id="7910e-238">Например, `Depth 2` включает каталог параметра **path** , первый уровень подкаталогов и второй уровень вложенных каталогов.</span><span class="sxs-lookup"><span data-stu-id="7910e-238">For example, `Depth 2` includes the **Path** parameter's directory, first level of subdirectories, and second level of subdirectories.</span></span> <span data-ttu-id="7910e-239">По умолчанию в выходные данные включаются имена каталогов и имен файлов.</span><span class="sxs-lookup"><span data-stu-id="7910e-239">By default directory names and filenames are included in the output.</span></span>

> [!NOTE]
> <span data-ttu-id="7910e-240">На компьютере Windows из PowerShell или **cmd.exe** можно отобразить графическое представление структуры каталогов с помощью команды **Tree.com** .</span><span class="sxs-lookup"><span data-stu-id="7910e-240">On a Windows computer from PowerShell or **cmd.exe** , you can display a graphical view of a directory structure with the **tree.com** command.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7910e-241">-Directory</span><span class="sxs-lookup"><span data-stu-id="7910e-241">-Directory</span></span>

<span data-ttu-id="7910e-242">Чтобы получить список каталогов, используйте параметр **Directory** или параметр **Attributes** со свойством **Directory** .</span><span class="sxs-lookup"><span data-stu-id="7910e-242">To get a list of directories, use the **Directory** parameter or the **Attributes** parameter with the **Directory** property.</span></span> <span data-ttu-id="7910e-243">Можно использовать параметр **рекурсии** с **каталогом**.</span><span class="sxs-lookup"><span data-stu-id="7910e-243">You can use the **Recurse** parameter with **Directory**.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ad, d

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7910e-244">-Exclude</span><span class="sxs-lookup"><span data-stu-id="7910e-244">-Exclude</span></span>

<span data-ttu-id="7910e-245">Указывает свойство или свойства, исключаемые этим командлетом из операции, в виде массива строк.</span><span class="sxs-lookup"><span data-stu-id="7910e-245">Specifies, as a string array, a property or property that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="7910e-246">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="7910e-246">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="7910e-247">Введите элемент пути или шаблон, например `*.txt` или `A*` .</span><span class="sxs-lookup"><span data-stu-id="7910e-247">Enter a path element or pattern, such as `*.txt` or `A*`.</span></span> <span data-ttu-id="7910e-248">Принимаются символы-шаблоны.</span><span class="sxs-lookup"><span data-stu-id="7910e-248">Wildcard characters are accepted.</span></span>

<span data-ttu-id="7910e-249">Конечная звездочка ( `*` ) в параметре **path** является необязательной.</span><span class="sxs-lookup"><span data-stu-id="7910e-249">A trailing asterisk (`*`) in the **Path** parameter is optional.</span></span> <span data-ttu-id="7910e-250">Например, `-Path C:\Test\Logs` или `-Path C:\Test\Logs\*`.</span><span class="sxs-lookup"><span data-stu-id="7910e-250">For example, `-Path C:\Test\Logs` or `-Path C:\Test\Logs\*`.</span></span> <span data-ttu-id="7910e-251">Если включена конечная звездочка ( `*` ), команда выполняет рекурсивный путь к подкаталогам параметра **path** .</span><span class="sxs-lookup"><span data-stu-id="7910e-251">If a trailing asterisk (`*`) is included, the command recurses into the **Path** parameter's subdirectories.</span></span> <span data-ttu-id="7910e-252">Без звездочки ( `*` ) отображается содержимое параметра **path** .</span><span class="sxs-lookup"><span data-stu-id="7910e-252">Without the asterisk (`*`), the contents of the **Path** parameter are displayed.</span></span> <span data-ttu-id="7910e-253">Дополнительные сведения см. в примере 5 и в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="7910e-253">More details are included in Example 5 and the Notes section.</span></span>

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

### <span data-ttu-id="7910e-254">-File</span><span class="sxs-lookup"><span data-stu-id="7910e-254">-File</span></span>

<span data-ttu-id="7910e-255">Чтобы получить список файлов, используйте параметр **File** .</span><span class="sxs-lookup"><span data-stu-id="7910e-255">To get a list of files, use the **File** parameter.</span></span> <span data-ttu-id="7910e-256">Параметр **рекурсии** можно использовать с **File**.</span><span class="sxs-lookup"><span data-stu-id="7910e-256">You can use the **Recurse** parameter with **File**.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: af

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7910e-257">-Filter</span><span class="sxs-lookup"><span data-stu-id="7910e-257">-Filter</span></span>

<span data-ttu-id="7910e-258">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="7910e-258">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="7910e-259">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим фильтры.</span><span class="sxs-lookup"><span data-stu-id="7910e-259">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports filters.</span></span> <span data-ttu-id="7910e-260">Фильтры более эффективны, чем другие параметры.</span><span class="sxs-lookup"><span data-stu-id="7910e-260">Filters are more efficient than other parameters.</span></span> <span data-ttu-id="7910e-261">Поставщик применяет фильтр, когда командлет получает объекты, вместо того, чтобы PowerShell отфильтровывает объекты после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="7910e-261">The provider applies filter when the cmdlet gets the objects rather than having PowerShell filter the objects after they're retrieved.</span></span> <span data-ttu-id="7910e-262">Строка фильтра передается в API .NET для перечисления файлов.</span><span class="sxs-lookup"><span data-stu-id="7910e-262">The filter string is passed to the .NET API to enumerate files.</span></span> <span data-ttu-id="7910e-263">API поддерживает только `*` `?` подстановочные знаки и.</span><span class="sxs-lookup"><span data-stu-id="7910e-263">The API only supports `*` and `?` wildcards.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="7910e-264">-Фолловсимлинк</span><span class="sxs-lookup"><span data-stu-id="7910e-264">-FollowSymlink</span></span>

<span data-ttu-id="7910e-265">По умолчанию `Get-ChildItem` командлет отображает символические ссылки на каталоги, найденные во время рекурсии, но не выполняет их рекурсивный переход.</span><span class="sxs-lookup"><span data-stu-id="7910e-265">By default, the `Get-ChildItem` cmdlet displays symbolic links to directories found during recursion, but doesn't recurse into them.</span></span> <span data-ttu-id="7910e-266">Используйте параметр **фолловсимлинк** для поиска в каталогах, предназначенных для этих символьных ссылок.</span><span class="sxs-lookup"><span data-stu-id="7910e-266">Use the **FollowSymlink** parameter to search the directories that target those symbolic links.</span></span> <span data-ttu-id="7910e-267">**Фолловсимлинк** является динамическим параметром и поддерживается только в поставщике **FileSystem** .</span><span class="sxs-lookup"><span data-stu-id="7910e-267">The **FollowSymlink** is a dynamic parameter and is supported only in the **FileSystem** provider.</span></span>

<span data-ttu-id="7910e-268">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="7910e-268">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="7910e-269">-Force</span><span class="sxs-lookup"><span data-stu-id="7910e-269">-Force</span></span>

<span data-ttu-id="7910e-270">Позволяет командлету получать элементы, к которым не может получить доступ пользователь, например скрытый или системный файл.</span><span class="sxs-lookup"><span data-stu-id="7910e-270">Allows the cmdlet to get items that otherwise can't be accessed by the user, such as hidden or system files.</span></span> <span data-ttu-id="7910e-271">Параметр **Force** не переопределяет ограничения безопасности.</span><span class="sxs-lookup"><span data-stu-id="7910e-271">The **Force** parameter doesn't override security restrictions.</span></span> <span data-ttu-id="7910e-272">Реализация зависит от поставщика.</span><span class="sxs-lookup"><span data-stu-id="7910e-272">Implementation varies among providers.</span></span> <span data-ttu-id="7910e-273">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="7910e-273">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="7910e-274">-Hidden</span><span class="sxs-lookup"><span data-stu-id="7910e-274">-Hidden</span></span>

<span data-ttu-id="7910e-275">Чтобы получить только скрытые элементы, используйте параметр **Hidden** или **Attributes** со свойством **Hidden** .</span><span class="sxs-lookup"><span data-stu-id="7910e-275">To get only hidden items, use the **Hidden** parameter or the **Attributes** parameter with the **Hidden** property.</span></span> <span data-ttu-id="7910e-276">По умолчанию `Get-ChildItem` скрытые элементы не отображаются.</span><span class="sxs-lookup"><span data-stu-id="7910e-276">By default, `Get-ChildItem` doesn't display hidden items.</span></span> <span data-ttu-id="7910e-277">Для получения скрытых элементов используйте параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="7910e-277">Use the **Force** parameter to get hidden items.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ah, h

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7910e-278">-Include</span><span class="sxs-lookup"><span data-stu-id="7910e-278">-Include</span></span>

<span data-ttu-id="7910e-279">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="7910e-279">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="7910e-280">Значение этого параметра определяет параметр **Path**.</span><span class="sxs-lookup"><span data-stu-id="7910e-280">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="7910e-281">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="7910e-281">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="7910e-282">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="7910e-282">Wildcard characters are permitted.</span></span> <span data-ttu-id="7910e-283">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="7910e-283">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="7910e-284">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="7910e-284">-LiteralPath</span></span>

<span data-ttu-id="7910e-285">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="7910e-285">Specifies a path to one or more locations.</span></span> <span data-ttu-id="7910e-286">Значение **LiteralPath** используется точно так же, как типизировано.</span><span class="sxs-lookup"><span data-stu-id="7910e-286">The value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="7910e-287">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="7910e-287">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="7910e-288">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="7910e-288">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="7910e-289">Одинарные кавычки указывают PowerShell не интерпретировать символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="7910e-289">Single quotation marks tell PowerShell to not interpret any characters as escape sequences.</span></span>

<span data-ttu-id="7910e-290">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="7910e-290">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralItems
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7910e-291">-Name</span><span class="sxs-lookup"><span data-stu-id="7910e-291">-Name</span></span>

<span data-ttu-id="7910e-292">Возвращает только имена элементов в расположении.</span><span class="sxs-lookup"><span data-stu-id="7910e-292">Gets only the names of the items in the location.</span></span> <span data-ttu-id="7910e-293">Выходные данные представляют собой строковый объект, который может быть отправлен по конвейеру другим командам.</span><span class="sxs-lookup"><span data-stu-id="7910e-293">The output is a string object that can be sent down the pipeline to other commands.</span></span> <span data-ttu-id="7910e-294">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="7910e-294">Wildcards are permitted.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="7910e-295">-Path</span><span class="sxs-lookup"><span data-stu-id="7910e-295">-Path</span></span>

<span data-ttu-id="7910e-296">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="7910e-296">Specifies a path to one or more locations.</span></span> <span data-ttu-id="7910e-297">Подстановочные знаки принимаются.</span><span class="sxs-lookup"><span data-stu-id="7910e-297">Wildcards are accepted.</span></span> <span data-ttu-id="7910e-298">Расположение по умолчанию — текущий каталог ( `.` ).</span><span class="sxs-lookup"><span data-stu-id="7910e-298">The default location is the current directory (`.`).</span></span>

```yaml
Type: System.String[]
Parameter Sets: Items
Aliases:

Required: False
Position: 0
Default value: Current directory
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="7910e-299">-ReadOnly</span><span class="sxs-lookup"><span data-stu-id="7910e-299">-ReadOnly</span></span>

<span data-ttu-id="7910e-300">Чтобы получить только элементы, доступные только для чтения, используйте параметр **ReadOnly** или свойство **Attributes** **ReadOnly** .</span><span class="sxs-lookup"><span data-stu-id="7910e-300">To get only read-only items, use the **ReadOnly** parameter or the **Attributes** parameter **ReadOnly** property.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ar

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7910e-301">-Recurse</span><span class="sxs-lookup"><span data-stu-id="7910e-301">-Recurse</span></span>

<span data-ttu-id="7910e-302">Получает элементы в указанных расположениях и всех дочерних элементах расположений.</span><span class="sxs-lookup"><span data-stu-id="7910e-302">Gets the items in the specified locations and in all child items of the locations.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: s

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7910e-303">-System</span><span class="sxs-lookup"><span data-stu-id="7910e-303">-System</span></span>

<span data-ttu-id="7910e-304">Возвращает только системные файлы и каталоги.</span><span class="sxs-lookup"><span data-stu-id="7910e-304">Gets only system files and directories.</span></span> <span data-ttu-id="7910e-305">Чтобы получить только системные файлы и папки, используйте свойство **System системного параметра или** параметра **System** **Attributes** .</span><span class="sxs-lookup"><span data-stu-id="7910e-305">To get only system files and folders, use the **System** parameter or **Attributes** parameter **System** property.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: as

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7910e-306">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="7910e-306">CommonParameters</span></span>

<span data-ttu-id="7910e-307">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7910e-307">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7910e-308">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7910e-308">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7910e-309">Входные данные</span><span class="sxs-lookup"><span data-stu-id="7910e-309">INPUTS</span></span>

### <span data-ttu-id="7910e-310">System.String</span><span class="sxs-lookup"><span data-stu-id="7910e-310">System.String</span></span>

<span data-ttu-id="7910e-311">Можно передать строку, содержащую путь, в `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="7910e-311">You can pipe a string that contains a path to `Get-ChildItem`.</span></span>

## <span data-ttu-id="7910e-312">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="7910e-312">OUTPUTS</span></span>

### <span data-ttu-id="7910e-313">System.Object</span><span class="sxs-lookup"><span data-stu-id="7910e-313">System.Object</span></span>

<span data-ttu-id="7910e-314">Тип `Get-ChildItem` возвращаемого объекта определяется объектами в пути к диску поставщика.</span><span class="sxs-lookup"><span data-stu-id="7910e-314">The type of object that `Get-ChildItem` returns is determined by the objects in the provider drive path.</span></span>

### <span data-ttu-id="7910e-315">System.String</span><span class="sxs-lookup"><span data-stu-id="7910e-315">System.String</span></span>

<span data-ttu-id="7910e-316">При использовании параметра **Name** `Get-ChildItem` возвращает имена объектов в виде строк.</span><span class="sxs-lookup"><span data-stu-id="7910e-316">If you use the **Name** parameter, `Get-ChildItem` returns the object names as strings.</span></span>

## <span data-ttu-id="7910e-317">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="7910e-317">NOTES</span></span>

- <span data-ttu-id="7910e-318">`Get-ChildItem` может выполняться с помощью любого встроенного псевдонима,, `ls` `dir` и `gci` .</span><span class="sxs-lookup"><span data-stu-id="7910e-318">`Get-ChildItem` can be run using any of the built-in aliases, `ls`, `dir`, and `gci`.</span></span> <span data-ttu-id="7910e-319">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="7910e-319">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="7910e-320">`Get-ChildItem` не получает скрытые элементы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7910e-320">`Get-ChildItem` doesn't get hidden items by default.</span></span> <span data-ttu-id="7910e-321">Чтобы получить скрытые элементы, используйте параметр **Force**.</span><span class="sxs-lookup"><span data-stu-id="7910e-321">To get hidden items, use the **Force** parameter.</span></span>
- <span data-ttu-id="7910e-322">`Get-ChildItem`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="7910e-322">The `Get-ChildItem` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="7910e-323">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="7910e-323">To list the providers available in your session, type `Get-PSProvider`.</span></span>
  <span data-ttu-id="7910e-324">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="7910e-324">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="7910e-325">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="7910e-325">RELATED LINKS</span></span>

[<span data-ttu-id="7910e-326">about_Certificate_Provider</span><span class="sxs-lookup"><span data-stu-id="7910e-326">about_Certificate_Provider</span></span>](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md)

[<span data-ttu-id="7910e-327">about_Providers</span><span class="sxs-lookup"><span data-stu-id="7910e-327">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="7910e-328">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="7910e-328">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="7910e-329">about_Registry_Provider</span><span class="sxs-lookup"><span data-stu-id="7910e-329">about_Registry_Provider</span></span>](../Microsoft.PowerShell.Core/About/about_Registry_Provider.md)

[<span data-ttu-id="7910e-330">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="7910e-330">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="7910e-331">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="7910e-331">Get-Alias</span></span>](../Microsoft.PowerShell.Utility/Get-Alias.md)

[<span data-ttu-id="7910e-332">Get-Item</span><span class="sxs-lookup"><span data-stu-id="7910e-332">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="7910e-333">Get-Location</span><span class="sxs-lookup"><span data-stu-id="7910e-333">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="7910e-334">Get-Process</span><span class="sxs-lookup"><span data-stu-id="7910e-334">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="7910e-335">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="7910e-335">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="7910e-336">Split-Path</span><span class="sxs-lookup"><span data-stu-id="7910e-336">Split-Path</span></span>](Split-Path.md)
