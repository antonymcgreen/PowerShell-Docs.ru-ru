---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-childitem?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ChildItem
ms.openlocfilehash: 14b1c5d0f37301a5312f37a115f0abc1c7b5990e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228838"
---
# <span data-ttu-id="80ee2-103">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="80ee2-103">Get-ChildItem</span></span>

## <span data-ttu-id="80ee2-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="80ee2-104">SYNOPSIS</span></span>

<span data-ttu-id="80ee2-105">Получает элементы и дочерние элементы в одном или нескольких указанных расположениях</span><span class="sxs-lookup"><span data-stu-id="80ee2-105">Gets the items and child items in one or more specified locations.</span></span>

## <span data-ttu-id="80ee2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="80ee2-106">SYNTAX</span></span>

### <span data-ttu-id="80ee2-107">Элементы (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="80ee2-107">Items (Default)</span></span>

```
Get-ChildItem [[-Path] <string[]>] [[-Filter] <string>] [-Include <string[]>] [-Exclude <string[]>]
 [-Recurse] [-Depth <uint32>] [-Force] [-Name] [-Attributes <FlagsExpression[FileAttributes]>]
 [-FollowSymlink] [-Directory] [-File] [-Hidden] [-ReadOnly] [-System] [<CommonParameters>]
```

### <span data-ttu-id="80ee2-108">литералитемс</span><span class="sxs-lookup"><span data-stu-id="80ee2-108">LiteralItems</span></span>

```
Get-ChildItem [[-Filter] <string>] -LiteralPath <string[]> [-Include <string[]>]
 [-Exclude <string[]>] [-Recurse] [-Depth <uint32>] [-Force] [-Name]
 [-Attributes <FlagsExpression[FileAttributes]>] [-FollowSymlink] [-Directory] [-File] [-Hidden]
 [-ReadOnly] [-System] [<CommonParameters>]
```

## <span data-ttu-id="80ee2-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="80ee2-109">DESCRIPTION</span></span>

<span data-ttu-id="80ee2-110">`Get-ChildItem`Командлет возвращает элементы в одном или нескольких указанных расположениях.</span><span class="sxs-lookup"><span data-stu-id="80ee2-110">The `Get-ChildItem` cmdlet gets the items in one or more specified locations.</span></span> <span data-ttu-id="80ee2-111">Если элемент является контейнером, командлет получает элементы внутри контейнера, называемые дочерними элементами.</span><span class="sxs-lookup"><span data-stu-id="80ee2-111">If the item is a container, it gets the items inside the container, known as child items.</span></span> <span data-ttu-id="80ee2-112">Можно использовать параметр **рекурсии** для получения элементов во всех дочерних контейнерах и использовать параметр **Depth** , чтобы ограничить число уровней для рекурсии.</span><span class="sxs-lookup"><span data-stu-id="80ee2-112">You can use the **Recurse** parameter to get items in all child containers and use the **Depth** parameter to limit the number of levels to recurse.</span></span>

<span data-ttu-id="80ee2-113">`Get-ChildItem` не отображает пустые каталоги.</span><span class="sxs-lookup"><span data-stu-id="80ee2-113">`Get-ChildItem` doesn't display empty directories.</span></span> <span data-ttu-id="80ee2-114">Если `Get-ChildItem` команда содержит **глубину** или **Рекурсивные** параметры, в выходные данные не включаются пустые каталоги.</span><span class="sxs-lookup"><span data-stu-id="80ee2-114">When a `Get-ChildItem` command includes the **Depth** or **Recurse** parameters, empty directories aren't included in the output.</span></span>

<span data-ttu-id="80ee2-115">Расположения предоставляются `Get-ChildItem` поставщиками PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80ee2-115">Locations are exposed to `Get-ChildItem` by PowerShell providers.</span></span> <span data-ttu-id="80ee2-116">Расположением может быть каталог файловой системы, куст реестра или хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="80ee2-116">A location can be a file system directory, registry hive, or a certificate store.</span></span> <span data-ttu-id="80ee2-117">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="80ee2-117">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="80ee2-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="80ee2-118">EXAMPLES</span></span>

### <span data-ttu-id="80ee2-119">Пример 1. Получение дочерних элементов из каталога файловой системы</span><span class="sxs-lookup"><span data-stu-id="80ee2-119">Example 1: Get child items from a file system directory</span></span>

<span data-ttu-id="80ee2-120">Этот пример получает дочерние элементы из каталога файловой системы.</span><span class="sxs-lookup"><span data-stu-id="80ee2-120">This example gets the child items from a file system directory.</span></span> <span data-ttu-id="80ee2-121">Отобразятся имена файлов и подкаталогов.</span><span class="sxs-lookup"><span data-stu-id="80ee2-121">The filenames and subdirectory names are displayed.</span></span> <span data-ttu-id="80ee2-122">Для пустых расположений команда не возвращает никаких выходных данных и возвращается в командную строку PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80ee2-122">For empty locations, the command doesn't return any output and returns to the PowerShell prompt.</span></span>

<span data-ttu-id="80ee2-123">`Get-ChildItem`Командлет использует параметр **path** для указания каталога `C:\Test` .</span><span class="sxs-lookup"><span data-stu-id="80ee2-123">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory `C:\Test`.</span></span>
<span data-ttu-id="80ee2-124">`Get-ChildItem` Отображает файлы и каталоги в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80ee2-124">`Get-ChildItem` displays the files and directories in the PowerShell console.</span></span>

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

<span data-ttu-id="80ee2-125">По умолчанию `Get-ChildItem` перечисляет режим ( **атрибуты** ), **LastWriteTime** , размер файла ( **Длина** ) и **имя** элемента.</span><span class="sxs-lookup"><span data-stu-id="80ee2-125">By default `Get-ChildItem` lists the mode ( **Attributes** ), **LastWriteTime** , file size ( **Length** ), and the **Name** of the item.</span></span> <span data-ttu-id="80ee2-126">Буквы в свойстве **mode** можно интерпретировать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="80ee2-126">The letters in the **Mode** property can be interpreted as follows:</span></span>

- <span data-ttu-id="80ee2-127">`l` ссылку</span><span class="sxs-lookup"><span data-stu-id="80ee2-127">`l` (link)</span></span>
- <span data-ttu-id="80ee2-128">`d` каталоги</span><span class="sxs-lookup"><span data-stu-id="80ee2-128">`d` (directory)</span></span>
- <span data-ttu-id="80ee2-129">`a` упражнени</span><span class="sxs-lookup"><span data-stu-id="80ee2-129">`a` (archive)</span></span>
- <span data-ttu-id="80ee2-130">`r` (только для чтения)</span><span class="sxs-lookup"><span data-stu-id="80ee2-130">`r` (read-only)</span></span>
- <span data-ttu-id="80ee2-131">`h` служеб</span><span class="sxs-lookup"><span data-stu-id="80ee2-131">`h` (hidden)</span></span>
- <span data-ttu-id="80ee2-132">`s` (система).</span><span class="sxs-lookup"><span data-stu-id="80ee2-132">`s` (system).</span></span>

<span data-ttu-id="80ee2-133">Дополнительные сведения о флагах режима см. в разделе [about_Filesystem_Provider](../microsoft.powershell.core/about/about_filesystem_provider.md#attributes-flagsexpression).</span><span class="sxs-lookup"><span data-stu-id="80ee2-133">For more information about the mode flags, see [about_Filesystem_Provider](../microsoft.powershell.core/about/about_filesystem_provider.md#attributes-flagsexpression).</span></span>

### <span data-ttu-id="80ee2-134">Пример 2. Получение имен дочерних элементов в каталоге</span><span class="sxs-lookup"><span data-stu-id="80ee2-134">Example 2: Get child item names in a directory</span></span>

<span data-ttu-id="80ee2-135">В этом примере выводятся только имена элементов в каталоге.</span><span class="sxs-lookup"><span data-stu-id="80ee2-135">This example lists only the names of items in a directory.</span></span>

<span data-ttu-id="80ee2-136">`Get-ChildItem`Командлет использует параметр **path** для указания каталога `C:\Test` .</span><span class="sxs-lookup"><span data-stu-id="80ee2-136">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory `C:\Test`.</span></span> <span data-ttu-id="80ee2-137">Параметр **Name** возвращает только имена файлов или каталогов из указанного пути.</span><span class="sxs-lookup"><span data-stu-id="80ee2-137">The **Name** parameter returns only the file or directory names from the specified path.</span></span>

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

### <span data-ttu-id="80ee2-138">Пример 3. Получение дочерних элементов в текущем каталоге и подкаталогах</span><span class="sxs-lookup"><span data-stu-id="80ee2-138">Example 3: Get child items in the current directory and subdirectories</span></span>

<span data-ttu-id="80ee2-139">В этом примере отображаются **txt** файлы, расположенные в текущем каталоге и его подкаталогах.</span><span class="sxs-lookup"><span data-stu-id="80ee2-139">This example displays **.txt** files that are located in the current directory and its subdirectories.</span></span>

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

<span data-ttu-id="80ee2-140">`Get-ChildItem`Командлет использует параметр **path** для указания `C:\Test\*.txt` .</span><span class="sxs-lookup"><span data-stu-id="80ee2-140">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify `C:\Test\*.txt`.</span></span> <span data-ttu-id="80ee2-141">В **пути** используется `*` подстановочный знак звездочки () для указания всех файлов с расширением имени файла `.txt` .</span><span class="sxs-lookup"><span data-stu-id="80ee2-141">**Path** uses the asterisk (`*`) wildcard to specify all files with the filename extension `.txt`.</span></span> <span data-ttu-id="80ee2-142">Параметр **рекурсии** выполняет поиск в каталоге **пути к** подкаталогам, как показано в **каталоге:** заголовки.</span><span class="sxs-lookup"><span data-stu-id="80ee2-142">The **Recurse** parameter searches the **Path** directory its subdirectories, as shown in the **Directory:** headings.</span></span> <span data-ttu-id="80ee2-143">Параметр **Force** отображает скрытые файлы `hiddenfile.txt` , например, с режимом **h** .</span><span class="sxs-lookup"><span data-stu-id="80ee2-143">The **Force** parameter displays hidden files such as `hiddenfile.txt` that have a mode of **h** .</span></span>

### <span data-ttu-id="80ee2-144">Пример 4. Получение дочерних элементов с помощью параметра Include</span><span class="sxs-lookup"><span data-stu-id="80ee2-144">Example 4: Get child items using the Include parameter</span></span>

<span data-ttu-id="80ee2-145">В этом примере `Get-ChildItem` параметр **include** используется для поиска определенных элементов из каталога, указанного параметром **path** .</span><span class="sxs-lookup"><span data-stu-id="80ee2-145">In this example `Get-ChildItem` uses the **Include** parameter to find specific items from the directory specified by the **Path** parameter.</span></span>

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

<span data-ttu-id="80ee2-146">`Get-ChildItem`Командлет использует параметр **path** для указания каталога **C:\test** .</span><span class="sxs-lookup"><span data-stu-id="80ee2-146">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory **C:\Test** .</span></span> <span data-ttu-id="80ee2-147">Параметр **path** включает в себя `*` подстановочный знак звездочки () для указания содержимого каталога.</span><span class="sxs-lookup"><span data-stu-id="80ee2-147">The **Path** parameter includes a trailing asterisk (`*`) wildcard to specify the directory's contents.</span></span>
<span data-ttu-id="80ee2-148">Параметр **include** использует `*` подстановочный знак звездочки (), чтобы указать все файлы с расширением **txt** .</span><span class="sxs-lookup"><span data-stu-id="80ee2-148">The **Include** parameter uses an asterisk (`*`) wildcard to specify all files with the file name extension **.txt** .</span></span>

<span data-ttu-id="80ee2-149">Если используется параметр **include** , для указания содержимого каталога параметру **path** требуется символ-шаблон звездочки ( `*` ).</span><span class="sxs-lookup"><span data-stu-id="80ee2-149">When the **Include** parameter is used, the **Path** parameter needs a trailing asterisk (`*`) wildcard to specify the directory's contents.</span></span> <span data-ttu-id="80ee2-150">Например, `-Path C:\Test\*`.</span><span class="sxs-lookup"><span data-stu-id="80ee2-150">For example, `-Path C:\Test\*`.</span></span>

- <span data-ttu-id="80ee2-151">Если в команду добавляется **рекурсивный** параметр, то символ звездочки ( `*` ) в параметре **path** является необязательным.</span><span class="sxs-lookup"><span data-stu-id="80ee2-151">If the **Recurse** parameter is added to the command, the trailing asterisk (`*`) in the **Path** parameter is optional.</span></span> <span data-ttu-id="80ee2-152">Параметр **рекурсии** возвращает элементы из каталога **пути** и его подкаталогов.</span><span class="sxs-lookup"><span data-stu-id="80ee2-152">The **Recurse** parameter gets items from the **Path** directory and its subdirectories.</span></span> <span data-ttu-id="80ee2-153">Например `-Path C:\Test\ -Recurse -Include *.txt`.</span><span class="sxs-lookup"><span data-stu-id="80ee2-153">For example, `-Path C:\Test\ -Recurse -Include *.txt`</span></span>
- <span data-ttu-id="80ee2-154">Если конечная звездочка ( `*` ) не включена в параметр **path** , команда не возвращает никаких выходных данных и возвращается в командную строку PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80ee2-154">If a trailing asterisk (`*`) isn't included in the **Path** parameter, the command doesn't return any output and returns to the PowerShell prompt.</span></span> <span data-ttu-id="80ee2-155">Например, `-Path C:\Test\`.</span><span class="sxs-lookup"><span data-stu-id="80ee2-155">For example, `-Path C:\Test\`.</span></span>

### <span data-ttu-id="80ee2-156">Пример 5. Получение дочерних элементов с помощью параметра Exclude</span><span class="sxs-lookup"><span data-stu-id="80ee2-156">Example 5: Get child items using the Exclude parameter</span></span>

<span data-ttu-id="80ee2-157">В выходных данных примера показано содержимое каталога **к:\тест\логс** .</span><span class="sxs-lookup"><span data-stu-id="80ee2-157">The example's output shows the contents of the directory **C:\Test\Logs** .</span></span> <span data-ttu-id="80ee2-158">Выходные данные представляют собой ссылку на другие команды, в которых используются параметры **Exclude** и **recurse** .</span><span class="sxs-lookup"><span data-stu-id="80ee2-158">The output is a reference for the other commands that use the **Exclude** and **Recurse** parameters.</span></span>

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

<span data-ttu-id="80ee2-159">`Get-ChildItem`Командлет использует параметр **path** для указания каталога `C:\Test\Logs` .</span><span class="sxs-lookup"><span data-stu-id="80ee2-159">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory `C:\Test\Logs`.</span></span>
<span data-ttu-id="80ee2-160">Параметр **Exclude** использует `*` подстановочный знак звездочки (), чтобы указать файлы или каталоги, которые **A** начинаются с **a** или, исключаются из выходных данных.</span><span class="sxs-lookup"><span data-stu-id="80ee2-160">The **Exclude** parameter uses the asterisk (`*`) wildcard to specify any files or directories that begin with **A** or **a** are excluded from the output.</span></span>

<span data-ttu-id="80ee2-161">При использовании параметра **Exclude** символ звездочки ( `*` ) в параметре **path** является необязательным.</span><span class="sxs-lookup"><span data-stu-id="80ee2-161">When the **Exclude** parameter is used, a trailing asterisk (`*`) in the **Path** parameter is optional.</span></span> <span data-ttu-id="80ee2-162">Например, `-Path C:\Test\Logs` или `-Path C:\Test\Logs\*`.</span><span class="sxs-lookup"><span data-stu-id="80ee2-162">For example, `-Path C:\Test\Logs` or `-Path C:\Test\Logs\*`.</span></span>

- <span data-ttu-id="80ee2-163">Если конечная звездочка ( `*` ) не включена в параметр **path** , отображается содержимое параметра **path** .</span><span class="sxs-lookup"><span data-stu-id="80ee2-163">If a trailing asterisk (`*`) isn't included in the **Path** parameter, the contents of the **Path** parameter are displayed.</span></span> <span data-ttu-id="80ee2-164">Исключениями являются имена файлов или подкаталогов, соответствующие значению параметра **Exclude** .</span><span class="sxs-lookup"><span data-stu-id="80ee2-164">The exceptions are filenames or subdirectory names that match the **Exclude** parameter's value.</span></span>
- <span data-ttu-id="80ee2-165">Если в параметр пути включена конечная звездочка ( `*` ) **Path** , команда выполняет рекурсивный путь к подкаталогам параметра **path** .</span><span class="sxs-lookup"><span data-stu-id="80ee2-165">If a trailing asterisk (`*`) is included in the **Path** parameter, the command recurses into the **Path** parameter's subdirectories.</span></span> <span data-ttu-id="80ee2-166">Исключениями являются имена файлов или подкаталогов, соответствующие значению параметра **Exclude** .</span><span class="sxs-lookup"><span data-stu-id="80ee2-166">The exceptions are filenames or subdirectory names that match the **Exclude** parameter's value.</span></span>
- <span data-ttu-id="80ee2-167">Если в команду добавляется **рекурсивный** параметр, то выходные данные рекурсии одинаковы, независимо от того, содержит ли параметр **пути** конечную звездочку ( `*` ).</span><span class="sxs-lookup"><span data-stu-id="80ee2-167">If the **Recurse** parameter is added to the command, the recursion output is the same whether or not the **Path** parameter includes a trailing asterisk (`*`).</span></span>

### <span data-ttu-id="80ee2-168">Пример 6. получение разделов реестра из куста реестра</span><span class="sxs-lookup"><span data-stu-id="80ee2-168">Example 6: Get the registry keys from a registry hive</span></span>

<span data-ttu-id="80ee2-169">Этот пример получает все разделы реестра из `HKEY_LOCAL_MACHINE\HARDWARE` .</span><span class="sxs-lookup"><span data-stu-id="80ee2-169">This example gets all the registry keys from `HKEY_LOCAL_MACHINE\HARDWARE`.</span></span>

<span data-ttu-id="80ee2-170">`Get-ChildItem` использует параметр **path** для указания раздела реестра `HKLM:\HARDWARE` .</span><span class="sxs-lookup"><span data-stu-id="80ee2-170">`Get-ChildItem` uses the **Path** parameter to specify the registry key `HKLM:\HARDWARE`.</span></span> <span data-ttu-id="80ee2-171">Путь к кусту и его верхний уровень разделов реестра отображаются в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80ee2-171">The hive's path and top level of registry keys are displayed in the PowerShell console.</span></span>

<span data-ttu-id="80ee2-172">Дополнительные сведения см. в разделе [about_Registry_Provider](../Microsoft.PowerShell.Core/About/about_Registry_Provider.md).</span><span class="sxs-lookup"><span data-stu-id="80ee2-172">For more information, see [about_Registry_Provider](../Microsoft.PowerShell.Core/About/about_Registry_Provider.md).</span></span>

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

<span data-ttu-id="80ee2-173">Первая команда отображает содержимое `HKLM:\HARDWARE` раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="80ee2-173">The first command shows the contents of the `HKLM:\HARDWARE` registry key.</span></span> <span data-ttu-id="80ee2-174">Параметр **Exclude** `Get-ChildItem` не возвращает никаких подразделов, начинающихся с `D*` .</span><span class="sxs-lookup"><span data-stu-id="80ee2-174">The **Exclude** parameter tells `Get-ChildItem` not to return any subkeys that start with `D*`.</span></span> <span data-ttu-id="80ee2-175">В настоящее время параметр **Exclude** работает только для подразделов, а не для свойств элемента.</span><span class="sxs-lookup"><span data-stu-id="80ee2-175">Currently, the **Exclude** parameter only works on subkeys, not item properties.</span></span>

### <span data-ttu-id="80ee2-176">Пример 7. получение всех сертификатов с помощью центра подписывания кода</span><span class="sxs-lookup"><span data-stu-id="80ee2-176">Example 7: Get all certificates with code-signing authority</span></span>

<span data-ttu-id="80ee2-177">В этом примере каждый сертификат создается на диске **сертификата PowerShell:** с центром подписывания кода.</span><span class="sxs-lookup"><span data-stu-id="80ee2-177">This example gets each certificate in the PowerShell **Cert:** drive that has code-signing authority.</span></span>

<span data-ttu-id="80ee2-178">`Get-ChildItem`Командлет использует параметр **path** для указания **CERT:** provider.</span><span class="sxs-lookup"><span data-stu-id="80ee2-178">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the **Cert:** provider.</span></span> <span data-ttu-id="80ee2-179">Параметр **рекурсии** выполняет поиск в каталоге, указанном по **пути** и его подкаталогам.</span><span class="sxs-lookup"><span data-stu-id="80ee2-179">The **Recurse** parameter searches the directory specified by **Path** and its subdirectories.</span></span> <span data-ttu-id="80ee2-180">Параметр **CodeSigningCert** возвращает только сертификаты, имеющие центр подписывания кода.</span><span class="sxs-lookup"><span data-stu-id="80ee2-180">The **CodeSigningCert** parameter gets only certificates that have code-signing authority.</span></span>

```powershell
Get-ChildItem -Path Cert:\* -Recurse -CodeSigningCert
```

<span data-ttu-id="80ee2-181">Дополнительные сведения о поставщике сертификатов и диске CERT: см. в разделе [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span><span class="sxs-lookup"><span data-stu-id="80ee2-181">For more information about the Certificate provider and the Cert: drive, see [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span></span>

### <span data-ttu-id="80ee2-182">Пример 8. Получение элементов с помощью параметра Depth</span><span class="sxs-lookup"><span data-stu-id="80ee2-182">Example 8: Get items using the Depth parameter</span></span>

<span data-ttu-id="80ee2-183">В этом примере отображаются элементы в каталоге и его подкаталогах.</span><span class="sxs-lookup"><span data-stu-id="80ee2-183">This example displays the items in a directory and its subdirectories.</span></span> <span data-ttu-id="80ee2-184">Параметр **Depth** определяет число уровней подкаталогов, включаемых в рекурсию.</span><span class="sxs-lookup"><span data-stu-id="80ee2-184">The **Depth** parameter determines the number of subdirectory levels to include in the recursion.</span></span> <span data-ttu-id="80ee2-185">Пустые каталоги исключаются из выходных данных.</span><span class="sxs-lookup"><span data-stu-id="80ee2-185">Empty directories are excluded from the output.</span></span>

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

<span data-ttu-id="80ee2-186">`Get-ChildItem`Командлет использует параметр **path** для указания **к:\парент** .</span><span class="sxs-lookup"><span data-stu-id="80ee2-186">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify **C:\Parent** .</span></span> <span data-ttu-id="80ee2-187">Параметр **Depth** указывает два уровня рекурсии.</span><span class="sxs-lookup"><span data-stu-id="80ee2-187">The **Depth** parameter specifies two levels of recursion.</span></span> <span data-ttu-id="80ee2-188">`Get-ChildItem` Отображает содержимое каталога, указанного параметром **path** , и двух уровней вложенных каталогов.</span><span class="sxs-lookup"><span data-stu-id="80ee2-188">`Get-ChildItem` displays the contents of the directory specified by the **Path** parameter and the two levels of subdirectories.</span></span>

### <span data-ttu-id="80ee2-189">Пример 9. Получение сведений о жесткой связи</span><span class="sxs-lookup"><span data-stu-id="80ee2-189">Example 9: Getting hard link information</span></span>

<span data-ttu-id="80ee2-190">В PowerShell 6,2 для получения сведений о жесткой связи было добавлено альтернативное представление.</span><span class="sxs-lookup"><span data-stu-id="80ee2-190">In PowerShell 6.2, an alternate view was added to get hard link information.</span></span>

```powershell
Get-ChildItem -Path C:\PathContainingHardLink | Format-Table -View childrenWithHardLink
```

## <span data-ttu-id="80ee2-191">Параметры</span><span class="sxs-lookup"><span data-stu-id="80ee2-191">Parameters</span></span>

### <span data-ttu-id="80ee2-192">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="80ee2-192">-Attributes</span></span>

<span data-ttu-id="80ee2-193">Извлекает файлы и папки с указанными атрибутами.</span><span class="sxs-lookup"><span data-stu-id="80ee2-193">Gets files and folders with the specified attributes.</span></span> <span data-ttu-id="80ee2-194">Этот параметр поддерживает все атрибуты и позволяет указывать сложные сочетания атрибутов.</span><span class="sxs-lookup"><span data-stu-id="80ee2-194">This parameter supports all attributes and lets you specify complex combinations of attributes.</span></span>

<span data-ttu-id="80ee2-195">Например, чтобы извлечь зашифрованные или сжатые файлы, не являющиеся системными (которые не являются каталогами), введите следующее:</span><span class="sxs-lookup"><span data-stu-id="80ee2-195">For example, to get non-system files (not directories) that are encrypted or compressed, type:</span></span>

`Get-ChildItem -Attributes !Directory+!System+Encrypted, !Directory+!System+Compressed`

<span data-ttu-id="80ee2-196">Чтобы найти файлы и папки с часто используемыми атрибутами, используйте параметр **Attributes** .</span><span class="sxs-lookup"><span data-stu-id="80ee2-196">To find files and folders with commonly used attributes, use the **Attributes** parameter.</span></span> <span data-ttu-id="80ee2-197">Или — **Каталог** параметров, **файл** , **скрытый** , **только для чтения** и **System** .</span><span class="sxs-lookup"><span data-stu-id="80ee2-197">Or, the parameters **Directory** , **File** , **Hidden** , **ReadOnly** , and **System** .</span></span>

<span data-ttu-id="80ee2-198">Параметр **Attributes** поддерживает следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="80ee2-198">The **Attributes** parameter supports the following properties:</span></span>

- <span data-ttu-id="80ee2-199">**Архив**</span><span class="sxs-lookup"><span data-stu-id="80ee2-199">**Archive**</span></span>
- <span data-ttu-id="80ee2-200">**Compressed**</span><span class="sxs-lookup"><span data-stu-id="80ee2-200">**Compressed**</span></span>
- <span data-ttu-id="80ee2-201">**Устройство**</span><span class="sxs-lookup"><span data-stu-id="80ee2-201">**Device**</span></span>
- <span data-ttu-id="80ee2-202">**Каталог**</span><span class="sxs-lookup"><span data-stu-id="80ee2-202">**Directory**</span></span>
- <span data-ttu-id="80ee2-203">**Зашифрована**</span><span class="sxs-lookup"><span data-stu-id="80ee2-203">**Encrypted**</span></span>
- <span data-ttu-id="80ee2-204">**Скрыта**</span><span class="sxs-lookup"><span data-stu-id="80ee2-204">**Hidden**</span></span>
- <span data-ttu-id="80ee2-205">**интегритистреам**</span><span class="sxs-lookup"><span data-stu-id="80ee2-205">**IntegrityStream**</span></span>
- <span data-ttu-id="80ee2-206">**Обычный**</span><span class="sxs-lookup"><span data-stu-id="80ee2-206">**Normal**</span></span>
- <span data-ttu-id="80ee2-207">**носкрубдата**</span><span class="sxs-lookup"><span data-stu-id="80ee2-207">**NoScrubData**</span></span>
- <span data-ttu-id="80ee2-208">**нотконтентиндексед**</span><span class="sxs-lookup"><span data-stu-id="80ee2-208">**NotContentIndexed**</span></span>
- <span data-ttu-id="80ee2-209">**Работа**</span><span class="sxs-lookup"><span data-stu-id="80ee2-209">**Offline**</span></span>
- <span data-ttu-id="80ee2-210">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="80ee2-210">**ReadOnly**</span></span>
- <span data-ttu-id="80ee2-211">**репарсепоинт**</span><span class="sxs-lookup"><span data-stu-id="80ee2-211">**ReparsePoint**</span></span>
- <span data-ttu-id="80ee2-212">**спарсефиле**</span><span class="sxs-lookup"><span data-stu-id="80ee2-212">**SparseFile**</span></span>
- <span data-ttu-id="80ee2-213">**Системные функции**</span><span class="sxs-lookup"><span data-stu-id="80ee2-213">**System**</span></span>
- <span data-ttu-id="80ee2-214">**Временные процедуры**</span><span class="sxs-lookup"><span data-stu-id="80ee2-214">**Temporary**</span></span>

<span data-ttu-id="80ee2-215">Описание этих атрибутов см. в описании [перечисления FileAttributes](/dotnet/api/system.io.fileattributes).</span><span class="sxs-lookup"><span data-stu-id="80ee2-215">For a description of these attributes, see the [FileAttributes Enumeration](/dotnet/api/system.io.fileattributes).</span></span>

<span data-ttu-id="80ee2-216">Чтобы объединить атрибуты, используйте следующие операторы:</span><span class="sxs-lookup"><span data-stu-id="80ee2-216">To combine attributes, use the following operators:</span></span>

- <span data-ttu-id="80ee2-217">`!` НЕДОСТАТОЧНО</span><span class="sxs-lookup"><span data-stu-id="80ee2-217">`!` (NOT)</span></span>
- <span data-ttu-id="80ee2-218">`+` ПЕРЕТАСКИВАНИ</span><span class="sxs-lookup"><span data-stu-id="80ee2-218">`+` (AND)</span></span>
- <span data-ttu-id="80ee2-219">`,` НИ</span><span class="sxs-lookup"><span data-stu-id="80ee2-219">`,` (OR)</span></span>

<span data-ttu-id="80ee2-220">Не используйте пробелы между оператором и его атрибутом.</span><span class="sxs-lookup"><span data-stu-id="80ee2-220">Don't use spaces between an operator and its attribute.</span></span> <span data-ttu-id="80ee2-221">Пробелы принимаются после запятых.</span><span class="sxs-lookup"><span data-stu-id="80ee2-221">Spaces are accepted after commas.</span></span>

<span data-ttu-id="80ee2-222">Для общих атрибутов используйте следующие сокращения:</span><span class="sxs-lookup"><span data-stu-id="80ee2-222">For common attributes, use the following abbreviations:</span></span>

- <span data-ttu-id="80ee2-223">`D` Каталоги</span><span class="sxs-lookup"><span data-stu-id="80ee2-223">`D` (Directory)</span></span>
- <span data-ttu-id="80ee2-224">`H` Служеб</span><span class="sxs-lookup"><span data-stu-id="80ee2-224">`H` (Hidden)</span></span>
- <span data-ttu-id="80ee2-225">`R` (Только для чтения)</span><span class="sxs-lookup"><span data-stu-id="80ee2-225">`R` (Read-only)</span></span>
- <span data-ttu-id="80ee2-226">`S` Системой</span><span class="sxs-lookup"><span data-stu-id="80ee2-226">`S` (System)</span></span>

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

### <span data-ttu-id="80ee2-227">-Depth</span><span class="sxs-lookup"><span data-stu-id="80ee2-227">-Depth</span></span>

<span data-ttu-id="80ee2-228">Этот параметр был добавлен в PowerShell 5,0 и позволяет управлять глубиной рекурсии.</span><span class="sxs-lookup"><span data-stu-id="80ee2-228">This parameter was added in PowerShell 5.0 and enables you to control the depth of recursion.</span></span> <span data-ttu-id="80ee2-229">По умолчанию `Get-ChildItem` отображает содержимое родительского каталога.</span><span class="sxs-lookup"><span data-stu-id="80ee2-229">By default, `Get-ChildItem` displays the contents of the parent directory.</span></span> <span data-ttu-id="80ee2-230">Параметр **Depth** определяет количество уровней подкаталогов, включаемых в рекурсию, и отображает содержимое.</span><span class="sxs-lookup"><span data-stu-id="80ee2-230">The **Depth** parameter determines the number of subdirectory levels that are included in the recursion and displays the contents.</span></span>

<span data-ttu-id="80ee2-231">Например, `Depth 2` включает каталог параметра **path** , первый уровень подкаталогов и второй уровень вложенных каталогов.</span><span class="sxs-lookup"><span data-stu-id="80ee2-231">For example, `Depth 2` includes the **Path** parameter's directory, first level of subdirectories, and second level of subdirectories.</span></span> <span data-ttu-id="80ee2-232">По умолчанию в выходные данные включаются имена каталогов и имен файлов.</span><span class="sxs-lookup"><span data-stu-id="80ee2-232">By default directory names and filenames are included in the output.</span></span>

> [!NOTE]
> <span data-ttu-id="80ee2-233">На компьютере Windows из PowerShell или **cmd.exe** можно отобразить графическое представление структуры каталогов с помощью команды **Tree.com** .</span><span class="sxs-lookup"><span data-stu-id="80ee2-233">On a Windows computer from PowerShell or **cmd.exe** , you can display a graphical view of a directory structure with the **tree.com** command.</span></span>

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

### <span data-ttu-id="80ee2-234">-Directory</span><span class="sxs-lookup"><span data-stu-id="80ee2-234">-Directory</span></span>

<span data-ttu-id="80ee2-235">Чтобы получить список каталогов, используйте параметр **Directory** или параметр **Attributes** со свойством **Directory** .</span><span class="sxs-lookup"><span data-stu-id="80ee2-235">To get a list of directories, use the **Directory** parameter or the **Attributes** parameter with the **Directory** property.</span></span> <span data-ttu-id="80ee2-236">Можно использовать параметр **рекурсии** с **каталогом** .</span><span class="sxs-lookup"><span data-stu-id="80ee2-236">You can use the **Recurse** parameter with **Directory** .</span></span>

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

### <span data-ttu-id="80ee2-237">-Exclude</span><span class="sxs-lookup"><span data-stu-id="80ee2-237">-Exclude</span></span>

<span data-ttu-id="80ee2-238">Указывает свойство или свойства, исключаемые этим командлетом из операции, в виде массива строк.</span><span class="sxs-lookup"><span data-stu-id="80ee2-238">Specifies, as a string array, a property or property that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="80ee2-239">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="80ee2-239">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="80ee2-240">Введите элемент пути или шаблон, например `*.txt` или `A*` .</span><span class="sxs-lookup"><span data-stu-id="80ee2-240">Enter a path element or pattern, such as `*.txt` or `A*`.</span></span> <span data-ttu-id="80ee2-241">Принимаются символы-шаблоны.</span><span class="sxs-lookup"><span data-stu-id="80ee2-241">Wildcard characters are accepted.</span></span>

<span data-ttu-id="80ee2-242">Конечная звездочка ( `*` ) в параметре **path** является необязательной.</span><span class="sxs-lookup"><span data-stu-id="80ee2-242">A trailing asterisk (`*`) in the **Path** parameter is optional.</span></span> <span data-ttu-id="80ee2-243">Например, `-Path C:\Test\Logs` или `-Path C:\Test\Logs\*`.</span><span class="sxs-lookup"><span data-stu-id="80ee2-243">For example, `-Path C:\Test\Logs` or `-Path C:\Test\Logs\*`.</span></span> <span data-ttu-id="80ee2-244">Если включена конечная звездочка ( `*` ), команда выполняет рекурсивный путь к подкаталогам параметра **path** .</span><span class="sxs-lookup"><span data-stu-id="80ee2-244">If a trailing asterisk (`*`) is included, the command recurses into the **Path** parameter's subdirectories.</span></span> <span data-ttu-id="80ee2-245">Без звездочки ( `*` ) отображается содержимое параметра **path** .</span><span class="sxs-lookup"><span data-stu-id="80ee2-245">Without the asterisk (`*`), the contents of the **Path** parameter are displayed.</span></span> <span data-ttu-id="80ee2-246">Дополнительные сведения см. в примере 5 и в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="80ee2-246">More details are included in Example 5 and the Notes section.</span></span>

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

### <span data-ttu-id="80ee2-247">-File</span><span class="sxs-lookup"><span data-stu-id="80ee2-247">-File</span></span>

<span data-ttu-id="80ee2-248">Чтобы получить список файлов, используйте параметр **File** .</span><span class="sxs-lookup"><span data-stu-id="80ee2-248">To get a list of files, use the **File** parameter.</span></span> <span data-ttu-id="80ee2-249">Параметр **рекурсии** можно использовать с **File** .</span><span class="sxs-lookup"><span data-stu-id="80ee2-249">You can use the **Recurse** parameter with **File** .</span></span>

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

### <span data-ttu-id="80ee2-250">-Filter</span><span class="sxs-lookup"><span data-stu-id="80ee2-250">-Filter</span></span>

<span data-ttu-id="80ee2-251">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="80ee2-251">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="80ee2-252">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим фильтры.</span><span class="sxs-lookup"><span data-stu-id="80ee2-252">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports filters.</span></span> <span data-ttu-id="80ee2-253">Фильтры более эффективны, чем другие параметры.</span><span class="sxs-lookup"><span data-stu-id="80ee2-253">Filters are more efficient than other parameters.</span></span> <span data-ttu-id="80ee2-254">Поставщик применяет фильтр, когда командлет получает объекты, вместо того, чтобы PowerShell отфильтровывает объекты после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="80ee2-254">The provider applies filter when the cmdlet gets the objects rather than having PowerShell filter the objects after they're retrieved.</span></span> <span data-ttu-id="80ee2-255">Строка фильтра передается в API .NET для перечисления файлов.</span><span class="sxs-lookup"><span data-stu-id="80ee2-255">The filter string is passed to the .NET API to enumerate files.</span></span> <span data-ttu-id="80ee2-256">API поддерживает только `*` `?` подстановочные знаки и.</span><span class="sxs-lookup"><span data-stu-id="80ee2-256">The API only supports `*` and `?` wildcards.</span></span>

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

### <span data-ttu-id="80ee2-257">-Фолловсимлинк</span><span class="sxs-lookup"><span data-stu-id="80ee2-257">-FollowSymlink</span></span>

<span data-ttu-id="80ee2-258">По умолчанию `Get-ChildItem` командлет отображает символические ссылки на каталоги, найденные во время рекурсии, но не выполняет их рекурсивный переход.</span><span class="sxs-lookup"><span data-stu-id="80ee2-258">By default, the `Get-ChildItem` cmdlet displays symbolic links to directories found during recursion, but doesn't recurse into them.</span></span> <span data-ttu-id="80ee2-259">Используйте параметр **фолловсимлинк** для поиска в каталогах, предназначенных для этих символьных ссылок.</span><span class="sxs-lookup"><span data-stu-id="80ee2-259">Use the **FollowSymlink** parameter to search the directories that target those symbolic links.</span></span> <span data-ttu-id="80ee2-260">**Фолловсимлинк** является динамическим параметром и поддерживается только в поставщике **FileSystem** .</span><span class="sxs-lookup"><span data-stu-id="80ee2-260">The **FollowSymlink** is a dynamic parameter and is supported only in the **FileSystem** provider.</span></span>

<span data-ttu-id="80ee2-261">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="80ee2-261">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="80ee2-262">-Force</span><span class="sxs-lookup"><span data-stu-id="80ee2-262">-Force</span></span>

<span data-ttu-id="80ee2-263">Позволяет командлету получать элементы, к которым не может получить доступ пользователь, например скрытый или системный файл.</span><span class="sxs-lookup"><span data-stu-id="80ee2-263">Allows the cmdlet to get items that otherwise can't be accessed by the user, such as hidden or system files.</span></span> <span data-ttu-id="80ee2-264">Параметр **Force** не переопределяет ограничения безопасности.</span><span class="sxs-lookup"><span data-stu-id="80ee2-264">The **Force** parameter doesn't override security restrictions.</span></span> <span data-ttu-id="80ee2-265">Реализация зависит от поставщика.</span><span class="sxs-lookup"><span data-stu-id="80ee2-265">Implementation varies among providers.</span></span> <span data-ttu-id="80ee2-266">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="80ee2-266">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="80ee2-267">-Hidden</span><span class="sxs-lookup"><span data-stu-id="80ee2-267">-Hidden</span></span>

<span data-ttu-id="80ee2-268">Чтобы получить только скрытые элементы, используйте параметр **Hidden** или **Attributes** со свойством **Hidden** .</span><span class="sxs-lookup"><span data-stu-id="80ee2-268">To get only hidden items, use the **Hidden** parameter or the **Attributes** parameter with the **Hidden** property.</span></span> <span data-ttu-id="80ee2-269">По умолчанию `Get-ChildItem` скрытые элементы не отображаются.</span><span class="sxs-lookup"><span data-stu-id="80ee2-269">By default, `Get-ChildItem` doesn't display hidden items.</span></span> <span data-ttu-id="80ee2-270">Для получения скрытых элементов используйте параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="80ee2-270">Use the **Force** parameter to get hidden items.</span></span>

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

### <span data-ttu-id="80ee2-271">-Include</span><span class="sxs-lookup"><span data-stu-id="80ee2-271">-Include</span></span>

<span data-ttu-id="80ee2-272">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="80ee2-272">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="80ee2-273">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="80ee2-273">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="80ee2-274">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="80ee2-274">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="80ee2-275">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="80ee2-275">Wildcard characters are permitted.</span></span> <span data-ttu-id="80ee2-276">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="80ee2-276">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="80ee2-277">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="80ee2-277">-LiteralPath</span></span>

<span data-ttu-id="80ee2-278">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="80ee2-278">Specifies a path to one or more locations.</span></span> <span data-ttu-id="80ee2-279">Значение **LiteralPath** используется точно так же, как типизировано.</span><span class="sxs-lookup"><span data-stu-id="80ee2-279">The value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="80ee2-280">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="80ee2-280">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="80ee2-281">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="80ee2-281">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="80ee2-282">Одинарные кавычки указывают PowerShell не интерпретировать символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="80ee2-282">Single quotation marks tell PowerShell to not interpret any characters as escape sequences.</span></span>

<span data-ttu-id="80ee2-283">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="80ee2-283">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="80ee2-284">-Name</span><span class="sxs-lookup"><span data-stu-id="80ee2-284">-Name</span></span>

<span data-ttu-id="80ee2-285">Возвращает только имена элементов в расположении.</span><span class="sxs-lookup"><span data-stu-id="80ee2-285">Gets only the names of the items in the location.</span></span> <span data-ttu-id="80ee2-286">Выходные данные представляют собой строковый объект, который может быть отправлен по конвейеру другим командам.</span><span class="sxs-lookup"><span data-stu-id="80ee2-286">The output is a string object that can be sent down the pipeline to other commands.</span></span> <span data-ttu-id="80ee2-287">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="80ee2-287">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="80ee2-288">-Path</span><span class="sxs-lookup"><span data-stu-id="80ee2-288">-Path</span></span>

<span data-ttu-id="80ee2-289">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="80ee2-289">Specifies a path to one or more locations.</span></span> <span data-ttu-id="80ee2-290">Подстановочные знаки принимаются.</span><span class="sxs-lookup"><span data-stu-id="80ee2-290">Wildcards are accepted.</span></span> <span data-ttu-id="80ee2-291">Расположение по умолчанию — текущий каталог ( `.` ).</span><span class="sxs-lookup"><span data-stu-id="80ee2-291">The default location is the current directory (`.`).</span></span>

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

### <span data-ttu-id="80ee2-292">-ReadOnly</span><span class="sxs-lookup"><span data-stu-id="80ee2-292">-ReadOnly</span></span>

<span data-ttu-id="80ee2-293">Чтобы получить только элементы, доступные только для чтения, используйте параметр **ReadOnly** или свойство **Attributes** **ReadOnly** .</span><span class="sxs-lookup"><span data-stu-id="80ee2-293">To get only read-only items, use the **ReadOnly** parameter or the **Attributes** parameter **ReadOnly** property.</span></span>

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

### <span data-ttu-id="80ee2-294">-Recurse</span><span class="sxs-lookup"><span data-stu-id="80ee2-294">-Recurse</span></span>

<span data-ttu-id="80ee2-295">Получает элементы в указанных расположениях и всех дочерних элементах расположений.</span><span class="sxs-lookup"><span data-stu-id="80ee2-295">Gets the items in the specified locations and in all child items of the locations.</span></span>

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

### <span data-ttu-id="80ee2-296">-System</span><span class="sxs-lookup"><span data-stu-id="80ee2-296">-System</span></span>

<span data-ttu-id="80ee2-297">Возвращает только системные файлы и каталоги.</span><span class="sxs-lookup"><span data-stu-id="80ee2-297">Gets only system files and directories.</span></span> <span data-ttu-id="80ee2-298">Чтобы получить только системные файлы и папки, используйте свойство **System системного параметра или** параметра **System** **Attributes** .</span><span class="sxs-lookup"><span data-stu-id="80ee2-298">To get only system files and folders, use the **System** parameter or **Attributes** parameter **System** property.</span></span>

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

### <span data-ttu-id="80ee2-299">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="80ee2-299">CommonParameters</span></span>

<span data-ttu-id="80ee2-300">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="80ee2-300">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="80ee2-301">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="80ee2-301">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="80ee2-302">Входные данные</span><span class="sxs-lookup"><span data-stu-id="80ee2-302">INPUTS</span></span>

### <span data-ttu-id="80ee2-303">System.String</span><span class="sxs-lookup"><span data-stu-id="80ee2-303">System.String</span></span>

<span data-ttu-id="80ee2-304">Можно передать строку, содержащую путь, в `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="80ee2-304">You can pipe a string that contains a path to `Get-ChildItem`.</span></span>

## <span data-ttu-id="80ee2-305">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="80ee2-305">OUTPUTS</span></span>

### <span data-ttu-id="80ee2-306">System.Object</span><span class="sxs-lookup"><span data-stu-id="80ee2-306">System.Object</span></span>

<span data-ttu-id="80ee2-307">Тип `Get-ChildItem` возвращаемого объекта определяется объектами в пути к диску поставщика.</span><span class="sxs-lookup"><span data-stu-id="80ee2-307">The type of object that `Get-ChildItem` returns is determined by the objects in the provider drive path.</span></span>

### <span data-ttu-id="80ee2-308">System.String</span><span class="sxs-lookup"><span data-stu-id="80ee2-308">System.String</span></span>

<span data-ttu-id="80ee2-309">При использовании параметра **Name** `Get-ChildItem` возвращает имена объектов в виде строк.</span><span class="sxs-lookup"><span data-stu-id="80ee2-309">If you use the **Name** parameter, `Get-ChildItem` returns the object names as strings.</span></span>

## <span data-ttu-id="80ee2-310">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="80ee2-310">NOTES</span></span>

- <span data-ttu-id="80ee2-311">`Get-ChildItem` может выполняться с помощью любого встроенного псевдонима,, `ls` `dir` и `gci` .</span><span class="sxs-lookup"><span data-stu-id="80ee2-311">`Get-ChildItem` can be run using any of the built-in aliases, `ls`, `dir`, and `gci`.</span></span> <span data-ttu-id="80ee2-312">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="80ee2-312">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="80ee2-313">`Get-ChildItem` не получает скрытые элементы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="80ee2-313">`Get-ChildItem` doesn't get hidden items by default.</span></span> <span data-ttu-id="80ee2-314">Чтобы получить скрытые элементы, используйте параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="80ee2-314">To get hidden items, use the **Force** parameter.</span></span>
- <span data-ttu-id="80ee2-315">`Get-ChildItem`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="80ee2-315">The `Get-ChildItem` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="80ee2-316">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="80ee2-316">To list the providers available in your session, type `Get-PSProvider`.</span></span>
  <span data-ttu-id="80ee2-317">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="80ee2-317">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="80ee2-318">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="80ee2-318">RELATED LINKS</span></span>

[<span data-ttu-id="80ee2-319">about_Certificate_Provider</span><span class="sxs-lookup"><span data-stu-id="80ee2-319">about_Certificate_Provider</span></span>](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md)

[<span data-ttu-id="80ee2-320">about_Providers</span><span class="sxs-lookup"><span data-stu-id="80ee2-320">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="80ee2-321">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="80ee2-321">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="80ee2-322">about_Registry_Provider</span><span class="sxs-lookup"><span data-stu-id="80ee2-322">about_Registry_Provider</span></span>](../Microsoft.PowerShell.Core/About/about_Registry_Provider.md)

[<span data-ttu-id="80ee2-323">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="80ee2-323">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="80ee2-324">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="80ee2-324">Get-Alias</span></span>](../Microsoft.PowerShell.Utility/Get-Alias.md)

[<span data-ttu-id="80ee2-325">Get-Item</span><span class="sxs-lookup"><span data-stu-id="80ee2-325">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="80ee2-326">Get-Location</span><span class="sxs-lookup"><span data-stu-id="80ee2-326">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="80ee2-327">Get-Process</span><span class="sxs-lookup"><span data-stu-id="80ee2-327">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="80ee2-328">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="80ee2-328">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="80ee2-329">Split-Path</span><span class="sxs-lookup"><span data-stu-id="80ee2-329">Split-Path</span></span>](Split-Path.md)
