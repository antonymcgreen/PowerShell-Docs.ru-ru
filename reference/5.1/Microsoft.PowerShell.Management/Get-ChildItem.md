---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-childitem?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ChildItem
ms.openlocfilehash: 9c613686765aa735e1e2cc58bfab533d1dc1e89f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228409"
---
# <span data-ttu-id="6db73-103">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="6db73-103">Get-ChildItem</span></span>

## <span data-ttu-id="6db73-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="6db73-104">SYNOPSIS</span></span>

<span data-ttu-id="6db73-105">Получает элементы и дочерние элементы в одном или нескольких указанных расположениях</span><span class="sxs-lookup"><span data-stu-id="6db73-105">Gets the items and child items in one or more specified locations.</span></span>

## <span data-ttu-id="6db73-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6db73-106">SYNTAX</span></span>

### <span data-ttu-id="6db73-107">Элементы (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="6db73-107">Items (Default)</span></span>

```
Get-ChildItem [[-Path] <string[]>] [[-Filter] <string>] [-Include <string[]>] [-Exclude <string[]>]
 [-Recurse] [-Depth <uint32>] [-Force] [-Name] [-UseTransaction]
 [-Attributes <FlagsExpression[FileAttributes]>] [-Directory] [-File] [-Hidden] [-ReadOnly] [-System]
 [<CommonParameters>]
```

### <span data-ttu-id="6db73-108">литералитемс</span><span class="sxs-lookup"><span data-stu-id="6db73-108">LiteralItems</span></span>

```
Get-ChildItem [[-Filter] <string>] -LiteralPath <string[]> [-Include <string[]>]
 [-Exclude <string[]>] [-Recurse] [-Depth <uint32>] [-Force] [-Name] [-UseTransaction]
 [-Attributes <FlagsExpression[FileAttributes]>] [-Directory] [-File] [-Hidden] [-ReadOnly] [-System]
 [<CommonParameters>]
```

## <span data-ttu-id="6db73-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6db73-109">DESCRIPTION</span></span>

<span data-ttu-id="6db73-110">`Get-ChildItem`Командлет возвращает элементы в одном или нескольких указанных расположениях.</span><span class="sxs-lookup"><span data-stu-id="6db73-110">The `Get-ChildItem` cmdlet gets the items in one or more specified locations.</span></span> <span data-ttu-id="6db73-111">Если элемент является контейнером, командлет получает элементы внутри контейнера, называемые дочерними элементами.</span><span class="sxs-lookup"><span data-stu-id="6db73-111">If the item is a container, it gets the items inside the container, known as child items.</span></span> <span data-ttu-id="6db73-112">Можно использовать параметр **рекурсии** для получения элементов во всех дочерних контейнерах и использовать параметр **Depth** , чтобы ограничить число уровней для рекурсии.</span><span class="sxs-lookup"><span data-stu-id="6db73-112">You can use the **Recurse** parameter to get items in all child containers and use the **Depth** parameter to limit the number of levels to recurse.</span></span>

<span data-ttu-id="6db73-113">`Get-ChildItem` не отображает пустые каталоги.</span><span class="sxs-lookup"><span data-stu-id="6db73-113">`Get-ChildItem` doesn't display empty directories.</span></span> <span data-ttu-id="6db73-114">Если `Get-ChildItem` команда содержит **глубину** или **Рекурсивные** параметры, в выходные данные не включаются пустые каталоги.</span><span class="sxs-lookup"><span data-stu-id="6db73-114">When a `Get-ChildItem` command includes the **Depth** or **Recurse** parameters, empty directories aren't included in the output.</span></span>

<span data-ttu-id="6db73-115">Расположения предоставляются `Get-ChildItem` поставщиками PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6db73-115">Locations are exposed to `Get-ChildItem` by PowerShell providers.</span></span> <span data-ttu-id="6db73-116">Расположением может быть каталог файловой системы, куст реестра или хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="6db73-116">A location can be a file system directory, registry hive, or a certificate store.</span></span> <span data-ttu-id="6db73-117">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="6db73-117">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="6db73-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="6db73-118">EXAMPLES</span></span>

### <span data-ttu-id="6db73-119">Пример 1. Получение дочерних элементов из каталога файловой системы</span><span class="sxs-lookup"><span data-stu-id="6db73-119">Example 1: Get child items from a file system directory</span></span>

<span data-ttu-id="6db73-120">Этот пример получает дочерние элементы из каталога файловой системы.</span><span class="sxs-lookup"><span data-stu-id="6db73-120">This example gets the child items from a file system directory.</span></span> <span data-ttu-id="6db73-121">Отобразятся имена файлов и подкаталогов.</span><span class="sxs-lookup"><span data-stu-id="6db73-121">The filenames and subdirectory names are displayed.</span></span> <span data-ttu-id="6db73-122">Для пустых расположений команда не возвращает никаких выходных данных и возвращается в командную строку PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6db73-122">For empty locations, the command doesn't return any output and returns to the PowerShell prompt.</span></span>

<span data-ttu-id="6db73-123">`Get-ChildItem`Командлет использует параметр **path** для указания каталога `C:\Test` .</span><span class="sxs-lookup"><span data-stu-id="6db73-123">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory `C:\Test`.</span></span>
<span data-ttu-id="6db73-124">`Get-ChildItem` Отображает файлы и каталоги в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6db73-124">`Get-ChildItem` displays the files and directories in the PowerShell console.</span></span>

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

<span data-ttu-id="6db73-125">По умолчанию `Get-ChildItem` перечисляет режим ( **атрибуты** ), **LastWriteTime** , размер файла ( **Длина** ) и **имя** элемента.</span><span class="sxs-lookup"><span data-stu-id="6db73-125">By default `Get-ChildItem` lists the mode ( **Attributes** ), **LastWriteTime** , file size ( **Length** ), and the **Name** of the item.</span></span> <span data-ttu-id="6db73-126">Буквы в свойстве **mode** можно интерпретировать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6db73-126">The letters in the **Mode** property can be interpreted as follows:</span></span>

- <span data-ttu-id="6db73-127">`l` ссылку</span><span class="sxs-lookup"><span data-stu-id="6db73-127">`l` (link)</span></span>
- <span data-ttu-id="6db73-128">`d` каталоги</span><span class="sxs-lookup"><span data-stu-id="6db73-128">`d` (directory)</span></span>
- <span data-ttu-id="6db73-129">`a` упражнени</span><span class="sxs-lookup"><span data-stu-id="6db73-129">`a` (archive)</span></span>
- <span data-ttu-id="6db73-130">`r` (только для чтения)</span><span class="sxs-lookup"><span data-stu-id="6db73-130">`r` (read-only)</span></span>
- <span data-ttu-id="6db73-131">`h` служеб</span><span class="sxs-lookup"><span data-stu-id="6db73-131">`h` (hidden)</span></span>
- <span data-ttu-id="6db73-132">`s` (система).</span><span class="sxs-lookup"><span data-stu-id="6db73-132">`s` (system).</span></span>

<span data-ttu-id="6db73-133">Дополнительные сведения о флагах режима см. в разделе [about_Filesystem_Provider](../microsoft.powershell.core/about/about_filesystem_provider.md#attributes-flagsexpression).</span><span class="sxs-lookup"><span data-stu-id="6db73-133">For more information about the mode flags, see [about_Filesystem_Provider](../microsoft.powershell.core/about/about_filesystem_provider.md#attributes-flagsexpression).</span></span>

### <span data-ttu-id="6db73-134">Пример 2. Получение имен дочерних элементов в каталоге</span><span class="sxs-lookup"><span data-stu-id="6db73-134">Example 2: Get child item names in a directory</span></span>

<span data-ttu-id="6db73-135">В этом примере выводятся только имена элементов в каталоге.</span><span class="sxs-lookup"><span data-stu-id="6db73-135">This example lists only the names of items in a directory.</span></span>

<span data-ttu-id="6db73-136">`Get-ChildItem`Командлет использует параметр **path** для указания каталога `C:\Test` .</span><span class="sxs-lookup"><span data-stu-id="6db73-136">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory `C:\Test`.</span></span> <span data-ttu-id="6db73-137">Параметр **Name** возвращает только имена файлов или каталогов из указанного пути.</span><span class="sxs-lookup"><span data-stu-id="6db73-137">The **Name** parameter returns only the file or directory names from the specified path.</span></span>

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

### <span data-ttu-id="6db73-138">Пример 3. Получение дочерних элементов в текущем каталоге и подкаталогах</span><span class="sxs-lookup"><span data-stu-id="6db73-138">Example 3: Get child items in the current directory and subdirectories</span></span>

<span data-ttu-id="6db73-139">В этом примере отображаются **txt** файлы, расположенные в текущем каталоге и его подкаталогах.</span><span class="sxs-lookup"><span data-stu-id="6db73-139">This example displays **.txt** files that are located in the current directory and its subdirectories.</span></span>

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

<span data-ttu-id="6db73-140">`Get-ChildItem`Командлет использует параметр **path** для указания `C:\Test\*.txt` .</span><span class="sxs-lookup"><span data-stu-id="6db73-140">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify `C:\Test\*.txt`.</span></span> <span data-ttu-id="6db73-141">В **пути** используется `*` подстановочный знак звездочки () для указания всех файлов с расширением имени файла `.txt` .</span><span class="sxs-lookup"><span data-stu-id="6db73-141">**Path** uses the asterisk (`*`) wildcard to specify all files with the filename extension `.txt`.</span></span> <span data-ttu-id="6db73-142">Параметр **рекурсии** выполняет поиск в каталоге **пути к** подкаталогам, как показано в **каталоге:** заголовки.</span><span class="sxs-lookup"><span data-stu-id="6db73-142">The **Recurse** parameter searches the **Path** directory its subdirectories, as shown in the **Directory:** headings.</span></span> <span data-ttu-id="6db73-143">Параметр **Force** отображает скрытые файлы `hiddenfile.txt` , например, с режимом **h** .</span><span class="sxs-lookup"><span data-stu-id="6db73-143">The **Force** parameter displays hidden files such as `hiddenfile.txt` that have a mode of **h** .</span></span>

### <span data-ttu-id="6db73-144">Пример 4. Получение дочерних элементов с помощью параметра Include</span><span class="sxs-lookup"><span data-stu-id="6db73-144">Example 4: Get child items using the Include parameter</span></span>

<span data-ttu-id="6db73-145">В этом примере `Get-ChildItem` параметр **include** используется для поиска определенных элементов из каталога, указанного параметром **path** .</span><span class="sxs-lookup"><span data-stu-id="6db73-145">In this example `Get-ChildItem` uses the **Include** parameter to find specific items from the directory specified by the **Path** parameter.</span></span>

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

<span data-ttu-id="6db73-146">`Get-ChildItem`Командлет использует параметр **path** для указания каталога **C:\test** .</span><span class="sxs-lookup"><span data-stu-id="6db73-146">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory **C:\Test** .</span></span> <span data-ttu-id="6db73-147">Параметр **path** включает в себя `*` подстановочный знак звездочки () для указания содержимого каталога.</span><span class="sxs-lookup"><span data-stu-id="6db73-147">The **Path** parameter includes a trailing asterisk (`*`) wildcard to specify the directory's contents.</span></span>
<span data-ttu-id="6db73-148">Параметр **include** использует `*` подстановочный знак звездочки (), чтобы указать все файлы с расширением **txt** .</span><span class="sxs-lookup"><span data-stu-id="6db73-148">The **Include** parameter uses an asterisk (`*`) wildcard to specify all files with the file name extension **.txt** .</span></span>

<span data-ttu-id="6db73-149">Если используется параметр **include** , для указания содержимого каталога параметру **path** требуется символ-шаблон звездочки ( `*` ).</span><span class="sxs-lookup"><span data-stu-id="6db73-149">When the **Include** parameter is used, the **Path** parameter needs a trailing asterisk (`*`) wildcard to specify the directory's contents.</span></span> <span data-ttu-id="6db73-150">Например, `-Path C:\Test\*`.</span><span class="sxs-lookup"><span data-stu-id="6db73-150">For example, `-Path C:\Test\*`.</span></span>

- <span data-ttu-id="6db73-151">Если в команду добавляется **рекурсивный** параметр, то символ звездочки ( `*` ) в параметре **path** является необязательным.</span><span class="sxs-lookup"><span data-stu-id="6db73-151">If the **Recurse** parameter is added to the command, the trailing asterisk (`*`) in the **Path** parameter is optional.</span></span> <span data-ttu-id="6db73-152">Параметр **рекурсии** возвращает элементы из каталога **пути** и его подкаталогов.</span><span class="sxs-lookup"><span data-stu-id="6db73-152">The **Recurse** parameter gets items from the **Path** directory and its subdirectories.</span></span> <span data-ttu-id="6db73-153">Например `-Path C:\Test\ -Recurse -Include *.txt`.</span><span class="sxs-lookup"><span data-stu-id="6db73-153">For example, `-Path C:\Test\ -Recurse -Include *.txt`</span></span>
- <span data-ttu-id="6db73-154">Если конечная звездочка ( `*` ) не включена в параметр **path** , команда не возвращает никаких выходных данных и возвращается в командную строку PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6db73-154">If a trailing asterisk (`*`) isn't included in the **Path** parameter, the command doesn't return any output and returns to the PowerShell prompt.</span></span> <span data-ttu-id="6db73-155">Например, `-Path C:\Test\`.</span><span class="sxs-lookup"><span data-stu-id="6db73-155">For example, `-Path C:\Test\`.</span></span>

### <span data-ttu-id="6db73-156">Пример 5. Получение дочерних элементов с помощью параметра Exclude</span><span class="sxs-lookup"><span data-stu-id="6db73-156">Example 5: Get child items using the Exclude parameter</span></span>

<span data-ttu-id="6db73-157">В выходных данных примера показано содержимое каталога **к:\тест\логс** .</span><span class="sxs-lookup"><span data-stu-id="6db73-157">The example's output shows the contents of the directory **C:\Test\Logs** .</span></span> <span data-ttu-id="6db73-158">Выходные данные представляют собой ссылку на другие команды, в которых используются параметры **Exclude** и **recurse** .</span><span class="sxs-lookup"><span data-stu-id="6db73-158">The output is a reference for the other commands that use the **Exclude** and **Recurse** parameters.</span></span>

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

<span data-ttu-id="6db73-159">`Get-ChildItem`Командлет использует параметр **path** для указания каталога `C:\Test\Logs` .</span><span class="sxs-lookup"><span data-stu-id="6db73-159">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory `C:\Test\Logs`.</span></span>
<span data-ttu-id="6db73-160">Параметр **Exclude** использует `*` подстановочный знак звездочки (), чтобы указать файлы или каталоги, которые **A** начинаются с **a** или, исключаются из выходных данных.</span><span class="sxs-lookup"><span data-stu-id="6db73-160">The **Exclude** parameter uses the asterisk (`*`) wildcard to specify any files or directories that begin with **A** or **a** are excluded from the output.</span></span>

<span data-ttu-id="6db73-161">При использовании параметра **Exclude** символ звездочки ( `*` ) в параметре **path** является необязательным.</span><span class="sxs-lookup"><span data-stu-id="6db73-161">When the **Exclude** parameter is used, a trailing asterisk (`*`) in the **Path** parameter is optional.</span></span> <span data-ttu-id="6db73-162">Например, `-Path C:\Test\Logs` или `-Path C:\Test\Logs\*`.</span><span class="sxs-lookup"><span data-stu-id="6db73-162">For example, `-Path C:\Test\Logs` or `-Path C:\Test\Logs\*`.</span></span>

- <span data-ttu-id="6db73-163">Если конечная звездочка ( `*` ) не включена в параметр **path** , отображается содержимое параметра **path** .</span><span class="sxs-lookup"><span data-stu-id="6db73-163">If a trailing asterisk (`*`) isn't included in the **Path** parameter, the contents of the **Path** parameter are displayed.</span></span> <span data-ttu-id="6db73-164">Исключениями являются имена файлов или подкаталогов, соответствующие значению параметра **Exclude** .</span><span class="sxs-lookup"><span data-stu-id="6db73-164">The exceptions are filenames or subdirectory names that match the **Exclude** parameter's value.</span></span>
- <span data-ttu-id="6db73-165">Если в параметр пути включена конечная звездочка ( `*` ) **Path** , команда выполняет рекурсивный путь к подкаталогам параметра **path** .</span><span class="sxs-lookup"><span data-stu-id="6db73-165">If a trailing asterisk (`*`) is included in the **Path** parameter, the command recurses into the **Path** parameter's subdirectories.</span></span> <span data-ttu-id="6db73-166">Исключениями являются имена файлов или подкаталогов, соответствующие значению параметра **Exclude** .</span><span class="sxs-lookup"><span data-stu-id="6db73-166">The exceptions are filenames or subdirectory names that match the **Exclude** parameter's value.</span></span>
- <span data-ttu-id="6db73-167">Если в команду добавляется **рекурсивный** параметр, то выходные данные рекурсии одинаковы, независимо от того, содержит ли параметр **пути** конечную звездочку ( `*` ).</span><span class="sxs-lookup"><span data-stu-id="6db73-167">If the **Recurse** parameter is added to the command, the recursion output is the same whether or not the **Path** parameter includes a trailing asterisk (`*`).</span></span>

### <span data-ttu-id="6db73-168">Пример 6. получение разделов реестра из куста реестра</span><span class="sxs-lookup"><span data-stu-id="6db73-168">Example 6: Get the registry keys from a registry hive</span></span>

<span data-ttu-id="6db73-169">Этот пример получает все разделы реестра из `HKEY_LOCAL_MACHINE\HARDWARE` .</span><span class="sxs-lookup"><span data-stu-id="6db73-169">This example gets all the registry keys from `HKEY_LOCAL_MACHINE\HARDWARE`.</span></span>

<span data-ttu-id="6db73-170">`Get-ChildItem` использует параметр **path** для указания раздела реестра `HKLM:\HARDWARE` .</span><span class="sxs-lookup"><span data-stu-id="6db73-170">`Get-ChildItem` uses the **Path** parameter to specify the registry key `HKLM:\HARDWARE`.</span></span> <span data-ttu-id="6db73-171">Путь к кусту и его верхний уровень разделов реестра отображаются в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6db73-171">The hive's path and top level of registry keys are displayed in the PowerShell console.</span></span>

<span data-ttu-id="6db73-172">Дополнительные сведения см. в разделе [about_Registry_Provider](../Microsoft.PowerShell.Core/About/about_Registry_Provider.md).</span><span class="sxs-lookup"><span data-stu-id="6db73-172">For more information, see [about_Registry_Provider](../Microsoft.PowerShell.Core/About/about_Registry_Provider.md).</span></span>

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

<span data-ttu-id="6db73-173">Первая команда отображает содержимое `HKLM:\HARDWARE` раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="6db73-173">The first command shows the contents of the `HKLM:\HARDWARE` registry key.</span></span> <span data-ttu-id="6db73-174">Параметр **Exclude** `Get-ChildItem` не возвращает никаких подразделов, начинающихся с `D*` .</span><span class="sxs-lookup"><span data-stu-id="6db73-174">The **Exclude** parameter tells `Get-ChildItem` not to return any subkeys that start with `D*`.</span></span> <span data-ttu-id="6db73-175">В настоящее время параметр **Exclude** работает только для подразделов, а не для свойств элемента.</span><span class="sxs-lookup"><span data-stu-id="6db73-175">Currently, the **Exclude** parameter only works on subkeys, not item properties.</span></span>

### <span data-ttu-id="6db73-176">Пример 7. получение всех сертификатов с помощью центра подписывания кода</span><span class="sxs-lookup"><span data-stu-id="6db73-176">Example 7: Get all certificates with code-signing authority</span></span>

<span data-ttu-id="6db73-177">В этом примере каждый сертификат создается на диске **сертификата PowerShell:** с центром подписывания кода.</span><span class="sxs-lookup"><span data-stu-id="6db73-177">This example gets each certificate in the PowerShell **Cert:** drive that has code-signing authority.</span></span>

<span data-ttu-id="6db73-178">`Get-ChildItem`Командлет использует параметр **path** для указания **CERT:** provider.</span><span class="sxs-lookup"><span data-stu-id="6db73-178">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the **Cert:** provider.</span></span> <span data-ttu-id="6db73-179">Параметр **рекурсии** выполняет поиск в каталоге, указанном по **пути** и его подкаталогам.</span><span class="sxs-lookup"><span data-stu-id="6db73-179">The **Recurse** parameter searches the directory specified by **Path** and its subdirectories.</span></span> <span data-ttu-id="6db73-180">Параметр **CodeSigningCert** возвращает только сертификаты, имеющие центр подписывания кода.</span><span class="sxs-lookup"><span data-stu-id="6db73-180">The **CodeSigningCert** parameter gets only certificates that have code-signing authority.</span></span>

```powershell
Get-ChildItem -Path Cert:\* -Recurse -CodeSigningCert
```

<span data-ttu-id="6db73-181">Дополнительные сведения о поставщике сертификатов и диске CERT: см. в разделе [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span><span class="sxs-lookup"><span data-stu-id="6db73-181">For more information about the Certificate provider and the Cert: drive, see [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span></span>

### <span data-ttu-id="6db73-182">Пример 8. Получение элементов с помощью параметра Depth</span><span class="sxs-lookup"><span data-stu-id="6db73-182">Example 8: Get items using the Depth parameter</span></span>

<span data-ttu-id="6db73-183">В этом примере отображаются элементы в каталоге и его подкаталогах.</span><span class="sxs-lookup"><span data-stu-id="6db73-183">This example displays the items in a directory and its subdirectories.</span></span> <span data-ttu-id="6db73-184">Параметр **Depth** определяет число уровней подкаталогов, включаемых в рекурсию.</span><span class="sxs-lookup"><span data-stu-id="6db73-184">The **Depth** parameter determines the number of subdirectory levels to include in the recursion.</span></span> <span data-ttu-id="6db73-185">Пустые каталоги исключаются из выходных данных.</span><span class="sxs-lookup"><span data-stu-id="6db73-185">Empty directories are excluded from the output.</span></span>

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

<span data-ttu-id="6db73-186">`Get-ChildItem`Командлет использует параметр **path** для указания **к:\парент** .</span><span class="sxs-lookup"><span data-stu-id="6db73-186">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify **C:\Parent** .</span></span> <span data-ttu-id="6db73-187">Параметр **Depth** указывает два уровня рекурсии.</span><span class="sxs-lookup"><span data-stu-id="6db73-187">The **Depth** parameter specifies two levels of recursion.</span></span> <span data-ttu-id="6db73-188">`Get-ChildItem` Отображает содержимое каталога, указанного параметром **path** , и двух уровней вложенных каталогов.</span><span class="sxs-lookup"><span data-stu-id="6db73-188">`Get-ChildItem` displays the contents of the directory specified by the **Path** parameter and the two levels of subdirectories.</span></span>

## <span data-ttu-id="6db73-189">Параметры</span><span class="sxs-lookup"><span data-stu-id="6db73-189">Parameters</span></span>

### <span data-ttu-id="6db73-190">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6db73-190">-Attributes</span></span>

<span data-ttu-id="6db73-191">Извлекает файлы и папки с указанными атрибутами.</span><span class="sxs-lookup"><span data-stu-id="6db73-191">Gets files and folders with the specified attributes.</span></span> <span data-ttu-id="6db73-192">Этот параметр поддерживает все атрибуты и позволяет указывать сложные сочетания атрибутов.</span><span class="sxs-lookup"><span data-stu-id="6db73-192">This parameter supports all attributes and lets you specify complex combinations of attributes.</span></span>

<span data-ttu-id="6db73-193">Например, чтобы извлечь зашифрованные или сжатые файлы, не являющиеся системными (которые не являются каталогами), введите следующее:</span><span class="sxs-lookup"><span data-stu-id="6db73-193">For example, to get non-system files (not directories) that are encrypted or compressed, type:</span></span>

`Get-ChildItem -Attributes !Directory+!System+Encrypted, !Directory+!System+Compressed`

<span data-ttu-id="6db73-194">Чтобы найти файлы и папки с часто используемыми атрибутами, используйте параметр **Attributes** .</span><span class="sxs-lookup"><span data-stu-id="6db73-194">To find files and folders with commonly used attributes, use the **Attributes** parameter.</span></span> <span data-ttu-id="6db73-195">Или — **Каталог** параметров, **файл** , **скрытый** , **только для чтения** и **System** .</span><span class="sxs-lookup"><span data-stu-id="6db73-195">Or, the parameters **Directory** , **File** , **Hidden** , **ReadOnly** , and **System** .</span></span>

<span data-ttu-id="6db73-196">Параметр **Attributes** поддерживает следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="6db73-196">The **Attributes** parameter supports the following properties:</span></span>

- <span data-ttu-id="6db73-197">**Архив**</span><span class="sxs-lookup"><span data-stu-id="6db73-197">**Archive**</span></span>
- <span data-ttu-id="6db73-198">**Compressed**</span><span class="sxs-lookup"><span data-stu-id="6db73-198">**Compressed**</span></span>
- <span data-ttu-id="6db73-199">**Устройство**</span><span class="sxs-lookup"><span data-stu-id="6db73-199">**Device**</span></span>
- <span data-ttu-id="6db73-200">**Каталог**</span><span class="sxs-lookup"><span data-stu-id="6db73-200">**Directory**</span></span>
- <span data-ttu-id="6db73-201">**Зашифрована**</span><span class="sxs-lookup"><span data-stu-id="6db73-201">**Encrypted**</span></span>
- <span data-ttu-id="6db73-202">**Скрыта**</span><span class="sxs-lookup"><span data-stu-id="6db73-202">**Hidden**</span></span>
- <span data-ttu-id="6db73-203">**интегритистреам**</span><span class="sxs-lookup"><span data-stu-id="6db73-203">**IntegrityStream**</span></span>
- <span data-ttu-id="6db73-204">**Обычный**</span><span class="sxs-lookup"><span data-stu-id="6db73-204">**Normal**</span></span>
- <span data-ttu-id="6db73-205">**носкрубдата**</span><span class="sxs-lookup"><span data-stu-id="6db73-205">**NoScrubData**</span></span>
- <span data-ttu-id="6db73-206">**нотконтентиндексед**</span><span class="sxs-lookup"><span data-stu-id="6db73-206">**NotContentIndexed**</span></span>
- <span data-ttu-id="6db73-207">**Работа**</span><span class="sxs-lookup"><span data-stu-id="6db73-207">**Offline**</span></span>
- <span data-ttu-id="6db73-208">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="6db73-208">**ReadOnly**</span></span>
- <span data-ttu-id="6db73-209">**репарсепоинт**</span><span class="sxs-lookup"><span data-stu-id="6db73-209">**ReparsePoint**</span></span>
- <span data-ttu-id="6db73-210">**спарсефиле**</span><span class="sxs-lookup"><span data-stu-id="6db73-210">**SparseFile**</span></span>
- <span data-ttu-id="6db73-211">**Системные функции**</span><span class="sxs-lookup"><span data-stu-id="6db73-211">**System**</span></span>
- <span data-ttu-id="6db73-212">**Временные процедуры**</span><span class="sxs-lookup"><span data-stu-id="6db73-212">**Temporary**</span></span>

<span data-ttu-id="6db73-213">Описание этих атрибутов см. в описании [перечисления FileAttributes](/dotnet/api/system.io.fileattributes).</span><span class="sxs-lookup"><span data-stu-id="6db73-213">For a description of these attributes, see the [FileAttributes Enumeration](/dotnet/api/system.io.fileattributes).</span></span>

<span data-ttu-id="6db73-214">Чтобы объединить атрибуты, используйте следующие операторы:</span><span class="sxs-lookup"><span data-stu-id="6db73-214">To combine attributes, use the following operators:</span></span>

- <span data-ttu-id="6db73-215">`!` НЕДОСТАТОЧНО</span><span class="sxs-lookup"><span data-stu-id="6db73-215">`!` (NOT)</span></span>
- <span data-ttu-id="6db73-216">`+` ПЕРЕТАСКИВАНИ</span><span class="sxs-lookup"><span data-stu-id="6db73-216">`+` (AND)</span></span>
- <span data-ttu-id="6db73-217">`,` НИ</span><span class="sxs-lookup"><span data-stu-id="6db73-217">`,` (OR)</span></span>

<span data-ttu-id="6db73-218">Не используйте пробелы между оператором и его атрибутом.</span><span class="sxs-lookup"><span data-stu-id="6db73-218">Don't use spaces between an operator and its attribute.</span></span> <span data-ttu-id="6db73-219">Пробелы принимаются после запятых.</span><span class="sxs-lookup"><span data-stu-id="6db73-219">Spaces are accepted after commas.</span></span>

<span data-ttu-id="6db73-220">Для общих атрибутов используйте следующие сокращения:</span><span class="sxs-lookup"><span data-stu-id="6db73-220">For common attributes, use the following abbreviations:</span></span>

- <span data-ttu-id="6db73-221">`D` Каталоги</span><span class="sxs-lookup"><span data-stu-id="6db73-221">`D` (Directory)</span></span>
- <span data-ttu-id="6db73-222">`H` Служеб</span><span class="sxs-lookup"><span data-stu-id="6db73-222">`H` (Hidden)</span></span>
- <span data-ttu-id="6db73-223">`R` (Только для чтения)</span><span class="sxs-lookup"><span data-stu-id="6db73-223">`R` (Read-only)</span></span>
- <span data-ttu-id="6db73-224">`S` Системой</span><span class="sxs-lookup"><span data-stu-id="6db73-224">`S` (System)</span></span>

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

### <span data-ttu-id="6db73-225">-Depth</span><span class="sxs-lookup"><span data-stu-id="6db73-225">-Depth</span></span>

<span data-ttu-id="6db73-226">Этот параметр был добавлен в PowerShell 5,0 и позволяет управлять глубиной рекурсии.</span><span class="sxs-lookup"><span data-stu-id="6db73-226">This parameter was added in PowerShell 5.0 and enables you to control the depth of recursion.</span></span> <span data-ttu-id="6db73-227">По умолчанию `Get-ChildItem` отображает содержимое родительского каталога.</span><span class="sxs-lookup"><span data-stu-id="6db73-227">By default, `Get-ChildItem` displays the contents of the parent directory.</span></span> <span data-ttu-id="6db73-228">Параметр **Depth** определяет количество уровней подкаталогов, включаемых в рекурсию, и отображает содержимое.</span><span class="sxs-lookup"><span data-stu-id="6db73-228">The **Depth** parameter determines the number of subdirectory levels that are included in the recursion and displays the contents.</span></span>

<span data-ttu-id="6db73-229">Например, `Depth 2` включает каталог параметра **path** , первый уровень подкаталогов и второй уровень вложенных каталогов.</span><span class="sxs-lookup"><span data-stu-id="6db73-229">For example, `Depth 2` includes the **Path** parameter's directory, first level of subdirectories, and second level of subdirectories.</span></span> <span data-ttu-id="6db73-230">По умолчанию в выходные данные включаются имена каталогов и имен файлов.</span><span class="sxs-lookup"><span data-stu-id="6db73-230">By default directory names and filenames are included in the output.</span></span>

> [!NOTE]
> <span data-ttu-id="6db73-231">На компьютере Windows из PowerShell или **cmd.exe** можно отобразить графическое представление структуры каталогов с помощью команды **Tree.com** .</span><span class="sxs-lookup"><span data-stu-id="6db73-231">On a Windows computer from PowerShell or **cmd.exe** , you can display a graphical view of a directory structure with the **tree.com** command.</span></span>

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

### <span data-ttu-id="6db73-232">-Directory</span><span class="sxs-lookup"><span data-stu-id="6db73-232">-Directory</span></span>

<span data-ttu-id="6db73-233">Чтобы получить список каталогов, используйте параметр **Directory** или параметр **Attributes** со свойством **Directory** .</span><span class="sxs-lookup"><span data-stu-id="6db73-233">To get a list of directories, use the **Directory** parameter or the **Attributes** parameter with the **Directory** property.</span></span> <span data-ttu-id="6db73-234">Можно использовать параметр **рекурсии** с **каталогом** .</span><span class="sxs-lookup"><span data-stu-id="6db73-234">You can use the **Recurse** parameter with **Directory** .</span></span>

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

### <span data-ttu-id="6db73-235">-Exclude</span><span class="sxs-lookup"><span data-stu-id="6db73-235">-Exclude</span></span>

<span data-ttu-id="6db73-236">Указывает свойство или свойства, исключаемые этим командлетом из операции, в виде массива строк.</span><span class="sxs-lookup"><span data-stu-id="6db73-236">Specifies, as a string array, a property or property that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="6db73-237">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="6db73-237">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="6db73-238">Введите элемент пути или шаблон, например `*.txt` или `A*` .</span><span class="sxs-lookup"><span data-stu-id="6db73-238">Enter a path element or pattern, such as `*.txt` or `A*`.</span></span> <span data-ttu-id="6db73-239">Принимаются символы-шаблоны.</span><span class="sxs-lookup"><span data-stu-id="6db73-239">Wildcard characters are accepted.</span></span>

<span data-ttu-id="6db73-240">Конечная звездочка ( `*` ) в параметре **path** является необязательной.</span><span class="sxs-lookup"><span data-stu-id="6db73-240">A trailing asterisk (`*`) in the **Path** parameter is optional.</span></span> <span data-ttu-id="6db73-241">Например, `-Path C:\Test\Logs` или `-Path C:\Test\Logs\*`.</span><span class="sxs-lookup"><span data-stu-id="6db73-241">For example, `-Path C:\Test\Logs` or `-Path C:\Test\Logs\*`.</span></span> <span data-ttu-id="6db73-242">Если включена конечная звездочка ( `*` ), команда выполняет рекурсивный путь к подкаталогам параметра **path** .</span><span class="sxs-lookup"><span data-stu-id="6db73-242">If a trailing asterisk (`*`) is included, the command recurses into the **Path** parameter's subdirectories.</span></span> <span data-ttu-id="6db73-243">Без звездочки ( `*` ) отображается содержимое параметра **path** .</span><span class="sxs-lookup"><span data-stu-id="6db73-243">Without the asterisk (`*`), the contents of the **Path** parameter are displayed.</span></span> <span data-ttu-id="6db73-244">Дополнительные сведения см. в примере 5 и в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="6db73-244">More details are included in Example 5 and the Notes section.</span></span>

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

### <span data-ttu-id="6db73-245">-File</span><span class="sxs-lookup"><span data-stu-id="6db73-245">-File</span></span>

<span data-ttu-id="6db73-246">Чтобы получить список файлов, используйте параметр **File** .</span><span class="sxs-lookup"><span data-stu-id="6db73-246">To get a list of files, use the **File** parameter.</span></span> <span data-ttu-id="6db73-247">Параметр **рекурсии** можно использовать с **File** .</span><span class="sxs-lookup"><span data-stu-id="6db73-247">You can use the **Recurse** parameter with **File** .</span></span>

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

### <span data-ttu-id="6db73-248">-Filter</span><span class="sxs-lookup"><span data-stu-id="6db73-248">-Filter</span></span>

<span data-ttu-id="6db73-249">Задает фильтр для уточнения параметра **пути** .</span><span class="sxs-lookup"><span data-stu-id="6db73-249">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="6db73-250">Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим фильтры.</span><span class="sxs-lookup"><span data-stu-id="6db73-250">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports filters.</span></span> <span data-ttu-id="6db73-251">Фильтры более эффективны, чем другие параметры.</span><span class="sxs-lookup"><span data-stu-id="6db73-251">Filters are more efficient than other parameters.</span></span> <span data-ttu-id="6db73-252">Поставщик применяет фильтр, когда командлет получает объекты, вместо того, чтобы PowerShell отфильтровывает объекты после их извлечения.</span><span class="sxs-lookup"><span data-stu-id="6db73-252">The provider applies filter when the cmdlet gets the objects rather than having PowerShell filter the objects after they're retrieved.</span></span> <span data-ttu-id="6db73-253">Строка фильтра передается в API .NET для перечисления файлов.</span><span class="sxs-lookup"><span data-stu-id="6db73-253">The filter string is passed to the .NET API to enumerate files.</span></span> <span data-ttu-id="6db73-254">API поддерживает только `*` `?` подстановочные знаки и.</span><span class="sxs-lookup"><span data-stu-id="6db73-254">The API only supports `*` and `?` wildcards.</span></span>

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

### <span data-ttu-id="6db73-255">-Force</span><span class="sxs-lookup"><span data-stu-id="6db73-255">-Force</span></span>

<span data-ttu-id="6db73-256">Позволяет командлету получать элементы, к которым не может получить доступ пользователь, например скрытый или системный файл.</span><span class="sxs-lookup"><span data-stu-id="6db73-256">Allows the cmdlet to get items that otherwise can't be accessed by the user, such as hidden or system files.</span></span> <span data-ttu-id="6db73-257">Параметр **Force** не переопределяет ограничения безопасности.</span><span class="sxs-lookup"><span data-stu-id="6db73-257">The **Force** parameter doesn't override security restrictions.</span></span> <span data-ttu-id="6db73-258">Реализация зависит от поставщика.</span><span class="sxs-lookup"><span data-stu-id="6db73-258">Implementation varies among providers.</span></span> <span data-ttu-id="6db73-259">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="6db73-259">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="6db73-260">-Hidden</span><span class="sxs-lookup"><span data-stu-id="6db73-260">-Hidden</span></span>

<span data-ttu-id="6db73-261">Чтобы получить только скрытые элементы, используйте параметр **Hidden** или **Attributes** со свойством **Hidden** .</span><span class="sxs-lookup"><span data-stu-id="6db73-261">To get only hidden items, use the **Hidden** parameter or the **Attributes** parameter with the **Hidden** property.</span></span> <span data-ttu-id="6db73-262">По умолчанию `Get-ChildItem` скрытые элементы не отображаются.</span><span class="sxs-lookup"><span data-stu-id="6db73-262">By default, `Get-ChildItem` doesn't display hidden items.</span></span> <span data-ttu-id="6db73-263">Для получения скрытых элементов используйте параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="6db73-263">Use the **Force** parameter to get hidden items.</span></span>

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

### <span data-ttu-id="6db73-264">-Include</span><span class="sxs-lookup"><span data-stu-id="6db73-264">-Include</span></span>

<span data-ttu-id="6db73-265">Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию.</span><span class="sxs-lookup"><span data-stu-id="6db73-265">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="6db73-266">Значение этого параметра определяет параметр **Path** .</span><span class="sxs-lookup"><span data-stu-id="6db73-266">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="6db73-267">Введите элемент пути или шаблон, например `"*.txt"` .</span><span class="sxs-lookup"><span data-stu-id="6db73-267">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="6db73-268">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="6db73-268">Wildcard characters are permitted.</span></span> <span data-ttu-id="6db73-269">Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.</span><span class="sxs-lookup"><span data-stu-id="6db73-269">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="6db73-270">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="6db73-270">-LiteralPath</span></span>

<span data-ttu-id="6db73-271">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="6db73-271">Specifies a path to one or more locations.</span></span> <span data-ttu-id="6db73-272">Значение **LiteralPath** используется точно так же, как типизировано.</span><span class="sxs-lookup"><span data-stu-id="6db73-272">The value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="6db73-273">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="6db73-273">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="6db73-274">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="6db73-274">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="6db73-275">Одинарные кавычки указывают PowerShell не интерпретировать символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="6db73-275">Single quotation marks tell PowerShell to not interpret any characters as escape sequences.</span></span>

<span data-ttu-id="6db73-276">Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="6db73-276">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralItems
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6db73-277">-Name</span><span class="sxs-lookup"><span data-stu-id="6db73-277">-Name</span></span>

<span data-ttu-id="6db73-278">Возвращает только имена элементов в расположении.</span><span class="sxs-lookup"><span data-stu-id="6db73-278">Gets only the names of the items in the location.</span></span> <span data-ttu-id="6db73-279">Выходные данные представляют собой строковый объект, который может быть отправлен по конвейеру другим командам.</span><span class="sxs-lookup"><span data-stu-id="6db73-279">The output is a string object that can be sent down the pipeline to other commands.</span></span> <span data-ttu-id="6db73-280">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="6db73-280">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="6db73-281">-Path</span><span class="sxs-lookup"><span data-stu-id="6db73-281">-Path</span></span>

<span data-ttu-id="6db73-282">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="6db73-282">Specifies a path to one or more locations.</span></span> <span data-ttu-id="6db73-283">Подстановочные знаки принимаются.</span><span class="sxs-lookup"><span data-stu-id="6db73-283">Wildcards are accepted.</span></span> <span data-ttu-id="6db73-284">Расположение по умолчанию — текущий каталог ( `.` ).</span><span class="sxs-lookup"><span data-stu-id="6db73-284">The default location is the current directory (`.`).</span></span>

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

### <span data-ttu-id="6db73-285">-ReadOnly</span><span class="sxs-lookup"><span data-stu-id="6db73-285">-ReadOnly</span></span>

<span data-ttu-id="6db73-286">Чтобы получить только элементы, доступные только для чтения, используйте параметр **ReadOnly** или свойство **Attributes** **ReadOnly** .</span><span class="sxs-lookup"><span data-stu-id="6db73-286">To get only read-only items, use the **ReadOnly** parameter or the **Attributes** parameter **ReadOnly** property.</span></span>

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

### <span data-ttu-id="6db73-287">-Recurse</span><span class="sxs-lookup"><span data-stu-id="6db73-287">-Recurse</span></span>

<span data-ttu-id="6db73-288">Получает элементы в указанных расположениях и всех дочерних элементах расположений.</span><span class="sxs-lookup"><span data-stu-id="6db73-288">Gets the items in the specified locations and in all child items of the locations.</span></span>

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

### <span data-ttu-id="6db73-289">-System</span><span class="sxs-lookup"><span data-stu-id="6db73-289">-System</span></span>

<span data-ttu-id="6db73-290">Возвращает только системные файлы и каталоги.</span><span class="sxs-lookup"><span data-stu-id="6db73-290">Gets only system files and directories.</span></span> <span data-ttu-id="6db73-291">Чтобы получить только системные файлы и папки, используйте свойство **System системного параметра или** параметра **System** **Attributes** .</span><span class="sxs-lookup"><span data-stu-id="6db73-291">To get only system files and folders, use the **System** parameter or **Attributes** parameter **System** property.</span></span>

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

### <span data-ttu-id="6db73-292">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="6db73-292">-UseTransaction</span></span>

<span data-ttu-id="6db73-293">Включает команду в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="6db73-293">Includes the command in the active transaction.</span></span> <span data-ttu-id="6db73-294">Этот параметр доступен только при выполнении транзакции.</span><span class="sxs-lookup"><span data-stu-id="6db73-294">This parameter is valid only when a transaction is in progress.</span></span> <span data-ttu-id="6db73-295">Дополнительные сведения см. в разделе [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span><span class="sxs-lookup"><span data-stu-id="6db73-295">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

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

### <span data-ttu-id="6db73-296">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="6db73-296">CommonParameters</span></span>

<span data-ttu-id="6db73-297">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6db73-297">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6db73-298">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6db73-298">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6db73-299">Входные данные</span><span class="sxs-lookup"><span data-stu-id="6db73-299">INPUTS</span></span>

### <span data-ttu-id="6db73-300">System.String</span><span class="sxs-lookup"><span data-stu-id="6db73-300">System.String</span></span>

<span data-ttu-id="6db73-301">Можно передать строку, содержащую путь, в `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="6db73-301">You can pipe a string that contains a path to `Get-ChildItem`.</span></span>

## <span data-ttu-id="6db73-302">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="6db73-302">OUTPUTS</span></span>

### <span data-ttu-id="6db73-303">System.Object</span><span class="sxs-lookup"><span data-stu-id="6db73-303">System.Object</span></span>

<span data-ttu-id="6db73-304">Тип `Get-ChildItem` возвращаемого объекта определяется объектами в пути к диску поставщика.</span><span class="sxs-lookup"><span data-stu-id="6db73-304">The type of object that `Get-ChildItem` returns is determined by the objects in the provider drive path.</span></span>

### <span data-ttu-id="6db73-305">System.String</span><span class="sxs-lookup"><span data-stu-id="6db73-305">System.String</span></span>

<span data-ttu-id="6db73-306">При использовании параметра **Name** `Get-ChildItem` возвращает имена объектов в виде строк.</span><span class="sxs-lookup"><span data-stu-id="6db73-306">If you use the **Name** parameter, `Get-ChildItem` returns the object names as strings.</span></span>

## <span data-ttu-id="6db73-307">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="6db73-307">NOTES</span></span>

- <span data-ttu-id="6db73-308">`Get-ChildItem` может выполняться с помощью любого встроенного псевдонима,, `ls` `dir` и `gci` .</span><span class="sxs-lookup"><span data-stu-id="6db73-308">`Get-ChildItem` can be run using any of the built-in aliases, `ls`, `dir`, and `gci`.</span></span> <span data-ttu-id="6db73-309">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="6db73-309">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="6db73-310">`Get-ChildItem` не получает скрытые элементы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6db73-310">`Get-ChildItem` doesn't get hidden items by default.</span></span> <span data-ttu-id="6db73-311">Чтобы получить скрытые элементы, используйте параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="6db73-311">To get hidden items, use the **Force** parameter.</span></span>
- <span data-ttu-id="6db73-312">`Get-ChildItem`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком.</span><span class="sxs-lookup"><span data-stu-id="6db73-312">The `Get-ChildItem` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="6db73-313">Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`.</span><span class="sxs-lookup"><span data-stu-id="6db73-313">To list the providers available in your session, type `Get-PSProvider`.</span></span>
  <span data-ttu-id="6db73-314">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="6db73-314">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="6db73-315">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="6db73-315">RELATED LINKS</span></span>

[<span data-ttu-id="6db73-316">about_Certificate_Provider</span><span class="sxs-lookup"><span data-stu-id="6db73-316">about_Certificate_Provider</span></span>](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md)

[<span data-ttu-id="6db73-317">about_Providers</span><span class="sxs-lookup"><span data-stu-id="6db73-317">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="6db73-318">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="6db73-318">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="6db73-319">about_Registry_Provider</span><span class="sxs-lookup"><span data-stu-id="6db73-319">about_Registry_Provider</span></span>](../Microsoft.PowerShell.Core/About/about_Registry_Provider.md)

[<span data-ttu-id="6db73-320">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="6db73-320">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="6db73-321">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="6db73-321">Get-Alias</span></span>](../Microsoft.PowerShell.Utility/Get-Alias.md)

[<span data-ttu-id="6db73-322">Get-Item</span><span class="sxs-lookup"><span data-stu-id="6db73-322">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="6db73-323">Get-Location</span><span class="sxs-lookup"><span data-stu-id="6db73-323">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="6db73-324">Get-Process</span><span class="sxs-lookup"><span data-stu-id="6db73-324">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="6db73-325">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="6db73-325">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="6db73-326">Split-Path</span><span class="sxs-lookup"><span data-stu-id="6db73-326">Split-Path</span></span>](Split-Path.md)
