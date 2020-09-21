---
ms.date: 07/28/2020
keywords: powershell,командлет
title: Работа с файлами, папками и разделами реестра
ms.openlocfilehash: 7ead5d0e82feb852845468fb3a012a0908a4ce75
ms.sourcegitcommit: 339e5fc8a4cc18b4ff6956fe5180343588e40e30
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87410195"
---
# <a name="working-with-files-folders-and-registry-keys"></a><span data-ttu-id="8e26c-103">Работа с файлами, папками и разделами реестра</span><span class="sxs-lookup"><span data-stu-id="8e26c-103">Working With Files, Folders and Registry Keys</span></span>

<span data-ttu-id="8e26c-104">Windows PowerShell использует существительное **Item**, чтобы ссылаться на элементы, найденные на диске Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8e26c-104">Windows PowerShell uses the noun **Item** to refer to items found on a Windows PowerShell drive.</span></span>
<span data-ttu-id="8e26c-105">При работе с поставщиком FileSystem Windows PowerShell **Item** может быть файлом, папкой или диском Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8e26c-105">When dealing with the Windows PowerShell FileSystem provider, an **Item** might be a file, a folder, or the Windows PowerShell drive.</span></span> <span data-ttu-id="8e26c-106">Создание списков элементов и работа с ними является критически важной задачей в большинстве административных учреждений, поэтому необходимо подробно обсудить ее.</span><span class="sxs-lookup"><span data-stu-id="8e26c-106">Listing and working with these items is a critical basic task in most administrative settings, so we want to discuss these tasks in detail.</span></span>

## <a name="enumerating-files-folders-and-registry-keys-get-childitem"></a><span data-ttu-id="8e26c-107">Перечисление файлов, папок и разделов реестра (Get-ChildItem)</span><span class="sxs-lookup"><span data-stu-id="8e26c-107">Enumerating Files, Folders, and Registry Keys (Get-ChildItem)</span></span>

<span data-ttu-id="8e26c-108">Так как получение коллекции элементов из определенного расположения является обычной задачей, командлет `Get-ChildItem` предназначен специально для возврата всех элементов, найденных в контейнере, например в папке.</span><span class="sxs-lookup"><span data-stu-id="8e26c-108">Since getting a collection of items from a particular location is such a common task, the `Get-ChildItem` cmdlet is designed specifically to return all items found within a container such as a folder.</span></span>

<span data-ttu-id="8e26c-109">Если необходимо вернуть все файлы и папки, которые находятся непосредственно в папке C:\\Windows, введите:</span><span class="sxs-lookup"><span data-stu-id="8e26c-109">If you want to return all files and folders that are contained directly within the folder C:\\Windows, type:</span></span>

```
PS> Get-ChildItem -Path C:\Windows
    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\Windows

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2006-05-16   8:10 AM          0 0.log
-a---        2005-11-29   3:16 PM         97 acc1.txt
-a---        2005-10-23  11:21 PM       3848 actsetup.log
...
```

<span data-ttu-id="8e26c-110">Списки выглядят аналогично тем спискам, которые появляются при вводе команды `dir` в **Cmd.exe** или команды `ls` в командной оболочке UNIX.</span><span class="sxs-lookup"><span data-stu-id="8e26c-110">The listing looks similar to what you would see when you enter the `dir` command in **Cmd.exe**, or the `ls` command in a UNIX command shell.</span></span>

<span data-ttu-id="8e26c-111">С помощью параметров командлета `Get-ChildItem` можно создавать очень сложные списки.</span><span class="sxs-lookup"><span data-stu-id="8e26c-111">You can perform very complex listings by using parameters of the `Get-ChildItem` cmdlet.</span></span> <span data-ttu-id="8e26c-112">Далее рассмотрим несколько сценариев.</span><span class="sxs-lookup"><span data-stu-id="8e26c-112">We will look at a few scenarios next.</span></span> <span data-ttu-id="8e26c-113">Синтаксис командлета `Get-ChildItem` можно увидеть, введя следующее.</span><span class="sxs-lookup"><span data-stu-id="8e26c-113">You can see the syntax the `Get-ChildItem` cmdlet by typing:</span></span>

```powershell
Get-Command -Name Get-ChildItem -Syntax
```

<span data-ttu-id="8e26c-114">Эти параметры можно скомбинировать и сопоставить для получения настраиваемых выходных данных.</span><span class="sxs-lookup"><span data-stu-id="8e26c-114">These parameters can be mixed and matched to get highly customized output.</span></span>

### <a name="listing-all-contained-items--recurse"></a><span data-ttu-id="8e26c-115">Перечисление всех элементов в контейнере (-Recurse)</span><span class="sxs-lookup"><span data-stu-id="8e26c-115">Listing all Contained Items (-Recurse)</span></span>

<span data-ttu-id="8e26c-116">Чтобы увидеть оба элемента в папке Windows и все элементы во вложенных папках, используйте параметр **Recurse** для `Get-ChildItem`.</span><span class="sxs-lookup"><span data-stu-id="8e26c-116">To see both the items inside a Windows folder and any items that are contained within the subfolders, use the **Recurse** parameter of `Get-ChildItem`.</span></span> <span data-ttu-id="8e26c-117">В списке отображается все, что находится в папке Windows, а также элементы в ее вложенных папках.</span><span class="sxs-lookup"><span data-stu-id="8e26c-117">The listing displays everything within the Windows folder and the items in its subfolders.</span></span> <span data-ttu-id="8e26c-118">Пример:</span><span class="sxs-lookup"><span data-stu-id="8e26c-118">For example:</span></span>

```
PS> Get-ChildItem -Path C:\WINDOWS -Recurse

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\WINDOWS
    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\WINDOWS\AppPatch
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2004-08-04   8:00 AM    1852416 AcGenral.dll
...
```

### <a name="filtering-items-by-name--name"></a><span data-ttu-id="8e26c-119">Фильтрация элементов по имени (-Name)</span><span class="sxs-lookup"><span data-stu-id="8e26c-119">Filtering Items by Name (-Name)</span></span>

<span data-ttu-id="8e26c-120">Чтобы отобразить только имена элементов, используйте параметр **Name** для `Get-Childitem`.</span><span class="sxs-lookup"><span data-stu-id="8e26c-120">To display only the names of items, use the **Name** parameter of `Get-Childitem`:</span></span>

```
PS> Get-ChildItem -Path C:\WINDOWS -Name
addins
AppPatch
assembly
...
```

### <a name="forcibly-listing-hidden-items--force"></a><span data-ttu-id="8e26c-121">Принудительное перечисление скрытых элементов (-Force)</span><span class="sxs-lookup"><span data-stu-id="8e26c-121">Forcibly Listing Hidden Items (-Force)</span></span>

<span data-ttu-id="8e26c-122">В выходных данных команды `Get-ChildItem` не отображаются элементы, которые обычно невидимы в проводнике или Cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="8e26c-122">Items that are normally invisible in File Explorer or Cmd.exe are not displayed in the output of a `Get-ChildItem` command.</span></span> <span data-ttu-id="8e26c-123">Чтобы показать скрытые элементы, используйте параметр **Force** для `Get-ChildItem`.</span><span class="sxs-lookup"><span data-stu-id="8e26c-123">To display hidden items, use the **Force** parameter of `Get-ChildItem`.</span></span>
<span data-ttu-id="8e26c-124">Пример:</span><span class="sxs-lookup"><span data-stu-id="8e26c-124">For example:</span></span>

```powershell
Get-ChildItem -Path C:\Windows -Force
```

<span data-ttu-id="8e26c-125">Этот параметр называется Force, так как позволяет принудительно переопределить обычное поведение команды `Get-ChildItem`.</span><span class="sxs-lookup"><span data-stu-id="8e26c-125">This parameter is named Force because you can forcibly override the normal behavior of the `Get-ChildItem` command.</span></span> <span data-ttu-id="8e26c-126">Параметр Force широко используется для принудительного выполнения действия командлетом. Тем не менее, он не будет выполнять действия, компрометирующие систему безопасности.</span><span class="sxs-lookup"><span data-stu-id="8e26c-126">Force is a widely used parameter that forces an action that a cmdlet would not normally perform, although it will not perform any action that compromises the security of the system.</span></span>

### <a name="matching-item-names-with-wildcards"></a><span data-ttu-id="8e26c-127">Сопоставление имен элементов с подстановочными знаками</span><span class="sxs-lookup"><span data-stu-id="8e26c-127">Matching Item Names with Wildcards</span></span>

<span data-ttu-id="8e26c-128">Команда `Get-ChildItem` принимает подстановочные знаки в пути к элементам списка.</span><span class="sxs-lookup"><span data-stu-id="8e26c-128">The `Get-ChildItem` command accepts wildcards in the path of the items to list.</span></span>

<span data-ttu-id="8e26c-129">Так как сопоставление с подстановочными знаками обрабатывается подсистемой Windows PowerShell, все командлеты, которые принимают подстановочные знаки, используют одну нотацию и имеют одно поведение сопоставления.</span><span class="sxs-lookup"><span data-stu-id="8e26c-129">Because wildcard matching is handled by the Windows PowerShell engine, all cmdlets that accepts wildcards use the same notation and have the same matching behavior.</span></span> <span data-ttu-id="8e26c-130">В нотацию подстановочных знаков Windows PowerShell входит:</span><span class="sxs-lookup"><span data-stu-id="8e26c-130">The Windows PowerShell wildcard notation includes:</span></span>

- <span data-ttu-id="8e26c-131">Звездочка (`*`) соответствует нулю или большему количеству вхождений любого символа.</span><span class="sxs-lookup"><span data-stu-id="8e26c-131">Asterisk (`*`) matches zero or more occurrences of any character.</span></span>

- <span data-ttu-id="8e26c-132">Знак вопроса (`?`) соответствует ровно одному символу.</span><span class="sxs-lookup"><span data-stu-id="8e26c-132">Question mark (`?`) matches exactly one character.</span></span>

- <span data-ttu-id="8e26c-133">Открывающая квадратная скобка (`[`) и закрывающая квадратная скобка (`]`) заключают в себя набор символов для сопоставления.</span><span class="sxs-lookup"><span data-stu-id="8e26c-133">Left bracket (`[`) character and right bracket (`]`) character surround a set of characters to be matched.</span></span>

<span data-ttu-id="8e26c-134">Далее приводится несколько примеров работы спецификации из подстановочных знаков.</span><span class="sxs-lookup"><span data-stu-id="8e26c-134">Here are some examples of how wildcard specification works.</span></span>

<span data-ttu-id="8e26c-135">Чтобы найти в каталоге Windows все файлы, имеющие суффикс `.log` и ровно пять символов в основном имени, введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="8e26c-135">To find all files in the Windows directory with the suffix `.log` and exactly five characters in the base name, enter the following command:</span></span>

```
PS> Get-ChildItem -Path C:\Windows\?????.log

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\Windows
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
...
-a---        2006-05-11   6:31 PM     204276 ocgen.log
-a---        2006-05-11   6:31 PM      22365 ocmsn.log
...
-a---        2005-11-11   4:55 AM         64 setup.log
-a---        2005-12-15   2:24 PM      17719 VxSDM.log
...
```

<span data-ttu-id="8e26c-136">Чтобы найти в каталоге Windows все файлы с именами, начинающимися на букву `x`, введите следующее.</span><span class="sxs-lookup"><span data-stu-id="8e26c-136">To find all files that begin with the letter `x` in the Windows directory, type:</span></span>

```powershell
Get-ChildItem -Path C:\Windows\x*
```

<span data-ttu-id="8e26c-137">Чтобы найти все файлы с именами, начинающимися на x или z, введите следующее.</span><span class="sxs-lookup"><span data-stu-id="8e26c-137">To find all files whose names begin with "x" or "z", type:</span></span>

```powershell
Get-ChildItem -Path C:\Windows\[xz]*
```

<span data-ttu-id="8e26c-138">Дополнительные сведения о подстановочных знаках см. в разделе [about_Wildcards](/powershell/module/microsoft.powershell.core/about/about_wildcards).</span><span class="sxs-lookup"><span data-stu-id="8e26c-138">For more information about wildcards, see [about_Wildcards](/powershell/module/microsoft.powershell.core/about/about_wildcards).</span></span>

### <a name="excluding-items--exclude"></a><span data-ttu-id="8e26c-139">Исключение элементов (-Exclude)</span><span class="sxs-lookup"><span data-stu-id="8e26c-139">Excluding Items (-Exclude)</span></span>

<span data-ttu-id="8e26c-140">Вы можете исключить определенные элементы с помощью параметра **Exclude** для `Get-ChildItem`.</span><span class="sxs-lookup"><span data-stu-id="8e26c-140">You can exclude specific items by using the **Exclude** parameter of `Get-ChildItem`.</span></span> <span data-ttu-id="8e26c-141">Это позволит вам выполнить сложную фильтрацию в одном операторе.</span><span class="sxs-lookup"><span data-stu-id="8e26c-141">This lets you perform complex filtering in a single statement.</span></span>

<span data-ttu-id="8e26c-142">Например, вы пытаетесь найти библиотеку службы времени Windows в папке **System32** и все, что вам известно об имени библиотеки, — то, что оно начинается с W и содержит 32.</span><span class="sxs-lookup"><span data-stu-id="8e26c-142">For example, suppose you are trying to find the Windows Time Service DLL in the **System32** folder, and all you can remember about the DLL name is that it begins with "W" and has "32" in it.</span></span>

<span data-ttu-id="8e26c-143">Такое выражение, как `w*32*.dll`, найдет все библиотеки DLL, которые отвечают этим условиям, но вам может потребоваться дополнительно отфильтровать файлы и пропустить все файлы win32.</span><span class="sxs-lookup"><span data-stu-id="8e26c-143">An expression like `w*32*.dll` will find all DLLs that satisfy the conditions, but you may want to further filter out the files and omit any win32 files.</span></span> <span data-ttu-id="8e26c-144">Эти файлы можно пропустить с помощью параметра **Exclude** с шаблоном `win*`.</span><span class="sxs-lookup"><span data-stu-id="8e26c-144">You can omit these files by using the **Exclude** parameter with the pattern `win*`:</span></span>

```
PS> Get-ChildItem -Path C:\WINDOWS\System32\w*32*.dll -Exclude win*

    Directory: C:\WINDOWS\System32

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           3/18/2019  9:43 PM         495616 w32time.dll
-a---           3/18/2019  9:44 PM          35328 w32topl.dll
-a---           1/24/2020  5:44 PM         401920 Wldap32.dll
-a---          10/10/2019  5:40 PM         442704 ws2_32.dll
-a---           3/18/2019  9:44 PM          66048 wsnmp32.dll
-a---           3/18/2019  9:44 PM          18944 wsock32.dll
-a---           3/18/2019  9:44 PM          64792 wtsapi32.dll
```

### <a name="mixing-get-childitem-parameters"></a><span data-ttu-id="8e26c-145">Смешение параметров Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="8e26c-145">Mixing Get-ChildItem Parameters</span></span>

<span data-ttu-id="8e26c-146">В одной команде можно использовать несколько параметров командлета `Get-ChildItem`.</span><span class="sxs-lookup"><span data-stu-id="8e26c-146">You can use several of the parameters of the `Get-ChildItem` cmdlet in the same command.</span></span> <span data-ttu-id="8e26c-147">Перед тем как комбинировать параметры, убедитесь, что понимаете принципы сопоставления подстановочных знаков.</span><span class="sxs-lookup"><span data-stu-id="8e26c-147">Before you mix parameters, be sure that you understand wildcard matching.</span></span> <span data-ttu-id="8e26c-148">Например, следующая команда не возвращает результатов:</span><span class="sxs-lookup"><span data-stu-id="8e26c-148">For example, the following command returns no results:</span></span>

```powershell
Get-ChildItem -Path C:\Windows\*.dll -Recurse -Exclude [a-y]*.dll
```

<span data-ttu-id="8e26c-149">Результаты отсутствуют, даже если существуют две библиотеки, которые начинаются на букву z в папке Windows.</span><span class="sxs-lookup"><span data-stu-id="8e26c-149">There are no results, even though there are two DLLs that begin with the letter "z" in the Windows folder.</span></span>

<span data-ttu-id="8e26c-150">Результаты не возвращены, так как подстановочный знак указан как часть пути.</span><span class="sxs-lookup"><span data-stu-id="8e26c-150">No results were returned because we specified the wildcard as part of the path.</span></span> <span data-ttu-id="8e26c-151">Хотя команда и была рекурсивной, командлет `Get-ChildItem` ограничил элементы до тех, которые находятся в папке Windows с именами, заканчивающимися на `.dll`.</span><span class="sxs-lookup"><span data-stu-id="8e26c-151">Even though the command was recursive, the `Get-ChildItem` cmdlet restricted the items to those that are in the Windows folder with names ending with `.dll`.</span></span>

<span data-ttu-id="8e26c-152">Чтобы указать рекурсивный поиск для файлов, имена которых соответствуют специальному шаблону, используйте параметр **Include**.</span><span class="sxs-lookup"><span data-stu-id="8e26c-152">To specify a recursive search for files whose names match a special pattern, use the **Include** parameter.</span></span>

```
PS> Get-ChildItem -Path C:\Windows -Include *.dll -Recurse -Exclude [a-y]*.dll

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\Windows\System32\Setup

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2004-08-04   8:00 AM       8261 zoneoc.dll

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\Windows\System32

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2004-08-04   8:00 AM     337920 zipfldr.dll
```
