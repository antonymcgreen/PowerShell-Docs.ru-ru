---
external help file: Microsoft.PowerShell.Archive-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Archive
ms.date: 02/20/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.archive/compress-archive?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Compress-Archive
ms.openlocfilehash: 796d510a1f7fd9bd7206e313dd23409fd8b2de1d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226853"
---
# <span data-ttu-id="a621f-103">Compress-Archive</span><span class="sxs-lookup"><span data-stu-id="a621f-103">Compress-Archive</span></span>

## <span data-ttu-id="a621f-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a621f-104">SYNOPSIS</span></span>
<span data-ttu-id="a621f-105">Создает сжатый архив или ZIP-файл из указанных файлов и каталогов.</span><span class="sxs-lookup"><span data-stu-id="a621f-105">Creates a compressed archive, or zipped file, from specified files and directories.</span></span>

## <span data-ttu-id="a621f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a621f-106">SYNTAX</span></span>

### <span data-ttu-id="a621f-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="a621f-107">Path (Default)</span></span>

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a621f-108">пасвисупдате</span><span class="sxs-lookup"><span data-stu-id="a621f-108">PathWithUpdate</span></span>

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>] -Update
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a621f-109">пасвисфорце</span><span class="sxs-lookup"><span data-stu-id="a621f-109">PathWithForce</span></span>

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>] -Force
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a621f-110">литералпасвисупдате</span><span class="sxs-lookup"><span data-stu-id="a621f-110">LiteralPathWithUpdate</span></span>

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 -Update [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a621f-111">литералпасвисфорце</span><span class="sxs-lookup"><span data-stu-id="a621f-111">LiteralPathWithForce</span></span>

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 -Force [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a621f-112">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a621f-112">LiteralPath</span></span>

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a621f-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a621f-113">DESCRIPTION</span></span>

<span data-ttu-id="a621f-114">`Compress-Archive`Командлет создает сжатый или ZIP-файл архива из одного или нескольких указанных файлов или каталогов.</span><span class="sxs-lookup"><span data-stu-id="a621f-114">The `Compress-Archive` cmdlet creates a compressed, or zipped, archive file from one or more specified files or directories.</span></span> <span data-ttu-id="a621f-115">Архив упаковывает несколько файлов с необязательным сжатием в один ZIP-файл для упрощения распространения и хранения.</span><span class="sxs-lookup"><span data-stu-id="a621f-115">An archive packages multiple files, with optional compression, into a single zipped file for easier distribution and storage.</span></span> <span data-ttu-id="a621f-116">Файл архива можно сжать с помощью алгоритма сжатия, заданного параметром **CompressionLevel** .</span><span class="sxs-lookup"><span data-stu-id="a621f-116">An archive file can be compressed by using the compression algorithm specified by the **CompressionLevel** parameter.</span></span>

<span data-ttu-id="a621f-117">`Compress-Archive`Командлет использует Microsoft .NET API [System.IO.Compression.ZipArchive](/dotnet/api/system.io.compression.ziparchive) для сжатия файлов.</span><span class="sxs-lookup"><span data-stu-id="a621f-117">The `Compress-Archive` cmdlet uses the Microsoft .NET API [System.IO.Compression.ZipArchive](/dotnet/api/system.io.compression.ziparchive) to compress files.</span></span>
<span data-ttu-id="a621f-118">Максимальный размер файла составляет 2 ГБ, так как имеется ограничение на базовый API.</span><span class="sxs-lookup"><span data-stu-id="a621f-118">The maximum file size is 2 GB because there's a limitation of the underlying API.</span></span>

<span data-ttu-id="a621f-119">В некоторых примерах Сплаттинг используется для сокращения длины строки примеров кода.</span><span class="sxs-lookup"><span data-stu-id="a621f-119">Some examples use splatting to reduce the line length of the code samples.</span></span> <span data-ttu-id="a621f-120">Дополнительные сведения см. в разделе [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="a621f-120">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

## <span data-ttu-id="a621f-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="a621f-121">EXAMPLES</span></span>

### <span data-ttu-id="a621f-122">Пример 1. сжатие файлов для создания файла архива</span><span class="sxs-lookup"><span data-stu-id="a621f-122">Example 1: Compress files to create an archive file</span></span>

<span data-ttu-id="a621f-123">В этом примере производится сжатие файлов из разных каталогов и создание файла архива.</span><span class="sxs-lookup"><span data-stu-id="a621f-123">This example compresses files from different directories and creates an archive file.</span></span> <span data-ttu-id="a621f-124">Для получения всех файлов с определенным расширением файла используется подстановочный знак.</span><span class="sxs-lookup"><span data-stu-id="a621f-124">A wildcard is used to get all files with a particular file extension.</span></span> <span data-ttu-id="a621f-125">В файле архива нет структуры каталогов, так как **путь** указывает только имена файлов.</span><span class="sxs-lookup"><span data-stu-id="a621f-125">There's no directory structure in the archive file because the **Path** only specifies file names.</span></span>

```powershell
$compress = @{
  Path = "C:\Reference\Draftdoc.docx", "C:\Reference\Images\*.vsd"
  CompressionLevel = "Fastest"
  DestinationPath = "C:\Archives\Draft.Zip"
}
Compress-Archive @compress
```

<span data-ttu-id="a621f-126">Параметр **path** принимает определенные имена файлов и имена файлов с подстановочными знаками, `*.vsd` .</span><span class="sxs-lookup"><span data-stu-id="a621f-126">The **Path** parameter accepts specific file names and file names with wildcards, `*.vsd`.</span></span> <span data-ttu-id="a621f-127">**Путь** использует список с разделителями-запятыми для получения файлов из разных каталогов.</span><span class="sxs-lookup"><span data-stu-id="a621f-127">The **Path** uses a comma-separated list to get files from different directories.</span></span> <span data-ttu-id="a621f-128">Уровень сжатия **быстрее** всего используется для сокращения времени обработки.</span><span class="sxs-lookup"><span data-stu-id="a621f-128">The compression level is **Fastest** to reduce processing time.</span></span> <span data-ttu-id="a621f-129">Параметр **DestinationPath** задает расположение `Draft.zip` файла.</span><span class="sxs-lookup"><span data-stu-id="a621f-129">The **DestinationPath** parameter specifies the location for the `Draft.zip` file.</span></span> <span data-ttu-id="a621f-130">`Draft.zip`Файл содержит `Draftdoc.docx` и все файлы с `.vsd` расширением.</span><span class="sxs-lookup"><span data-stu-id="a621f-130">The `Draft.zip` file contains `Draftdoc.docx` and all the files with a `.vsd` extension.</span></span>

### <span data-ttu-id="a621f-131">Пример 2. сжатие файлов с помощью LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a621f-131">Example 2: Compress files using a LiteralPath</span></span>

<span data-ttu-id="a621f-132">Этот пример сжимает определенные именованные файлы и создает новый файл архива.</span><span class="sxs-lookup"><span data-stu-id="a621f-132">This example compresses specific named files and creates a new archive file.</span></span> <span data-ttu-id="a621f-133">В файле архива нет структуры каталогов, так как **путь** указывает только имена файлов.</span><span class="sxs-lookup"><span data-stu-id="a621f-133">There's no directory structure in the archive file because the **Path** only specifies file names.</span></span>

```powershell
$compress = @{
LiteralPath= "C:\Reference\Draft Doc.docx", "C:\Reference\Images\diagram2.vsd"
CompressionLevel = "Fastest"
DestinationPath = "C:\Archives\Draft.Zip"
}
Compress-Archive @compress
```

<span data-ttu-id="a621f-134">Используется абсолютный путь и имена файлов, так как параметр **LiteralPath** не принимает подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="a621f-134">Absolute path and file names are used because the **LiteralPath** parameter doesn't accept wildcards.</span></span> <span data-ttu-id="a621f-135">**Путь** использует список с разделителями-запятыми для получения файлов из разных каталогов.</span><span class="sxs-lookup"><span data-stu-id="a621f-135">The **Path** uses a comma-separated list to get files from different directories.</span></span> <span data-ttu-id="a621f-136">Уровень сжатия **быстрее** всего используется для сокращения времени обработки.</span><span class="sxs-lookup"><span data-stu-id="a621f-136">The compression level is **Fastest** to reduce processing time.</span></span> <span data-ttu-id="a621f-137">Параметр **DestinationPath** задает расположение `Draft.zip` файла.</span><span class="sxs-lookup"><span data-stu-id="a621f-137">The **DestinationPath** parameter specifies the location for the `Draft.zip` file.</span></span> <span data-ttu-id="a621f-138">`Draft.zip`Файл содержит только `Draftdoc.docx` и `diagram2.vsd` .</span><span class="sxs-lookup"><span data-stu-id="a621f-138">The `Draft.zip` file only contains `Draftdoc.docx` and `diagram2.vsd`.</span></span>

### <span data-ttu-id="a621f-139">Пример 3. Сжатие каталога, содержащего корневой каталог</span><span class="sxs-lookup"><span data-stu-id="a621f-139">Example 3: Compress a directory that includes the root directory</span></span>

<span data-ttu-id="a621f-140">В этом примере сжимается каталог и создается файл архива, **содержащий** корневой каталог и все его файлы и подкаталоги.</span><span class="sxs-lookup"><span data-stu-id="a621f-140">This example compresses a directory and creates an archive file that **includes** the root directory, and all its files and subdirectories.</span></span> <span data-ttu-id="a621f-141">Файл архива имеет структуру каталогов, так как **путь** указывает корневой каталог.</span><span class="sxs-lookup"><span data-stu-id="a621f-141">The archive file has a directory structure because the **Path** specifies a root directory.</span></span>

```powershell
Compress-Archive -Path C:\Reference -DestinationPath C:\Archives\Draft.zip
```

<span data-ttu-id="a621f-142">`Compress-Archive` использует параметр **path** для указания корневого каталога `C:\Reference` .</span><span class="sxs-lookup"><span data-stu-id="a621f-142">`Compress-Archive` uses the **Path** parameter to specify the root directory, `C:\Reference`.</span></span> <span data-ttu-id="a621f-143">Параметр **DestinationPath** указывает расположение файла архива.</span><span class="sxs-lookup"><span data-stu-id="a621f-143">The **DestinationPath** parameter specifies the location for the archive file.</span></span> <span data-ttu-id="a621f-144">`Draft.zip`Архив включает `Reference` корневой каталог и все его файлы и подкаталоги.</span><span class="sxs-lookup"><span data-stu-id="a621f-144">The `Draft.zip` archive includes the `Reference` root directory, and all its files and subdirectories.</span></span>

### <span data-ttu-id="a621f-145">Пример 4. Сжатие каталога, который исключает корневой каталог</span><span class="sxs-lookup"><span data-stu-id="a621f-145">Example 4: Compress a directory that excludes the root directory</span></span>

<span data-ttu-id="a621f-146">В этом примере выполняется сжатие каталога и создается файл архива, который **исключает** корневой каталог, поскольку **путь** использует `*` подстановочный знак звездочки ().</span><span class="sxs-lookup"><span data-stu-id="a621f-146">This example compresses a directory and creates an archive file that **excludes** the root directory because the **Path** uses an asterisk (`*`) wildcard.</span></span> <span data-ttu-id="a621f-147">Архив содержит структуру каталогов, содержащую файлы и подкаталоги корневого каталога.</span><span class="sxs-lookup"><span data-stu-id="a621f-147">The archive contains a directory structure that contains the root directory's files and subdirectories.</span></span>

```powershell
Compress-Archive -Path C:\Reference\* -DestinationPath C:\Archives\Draft.zip
```

<span data-ttu-id="a621f-148">`Compress-Archive` использует параметр **path** для указания корневого каталога `C:\Reference` с `*` подстановочным знаком звездочки ().</span><span class="sxs-lookup"><span data-stu-id="a621f-148">`Compress-Archive` uses the **Path** parameter to specify the root directory, `C:\Reference` with an asterisk (`*`) wildcard.</span></span> <span data-ttu-id="a621f-149">Параметр **DestinationPath** указывает расположение файла архива.</span><span class="sxs-lookup"><span data-stu-id="a621f-149">The **DestinationPath** parameter specifies the location for the archive file.</span></span> <span data-ttu-id="a621f-150">`Draft.zip`Архив содержит файлы и подкаталоги корневого каталога.</span><span class="sxs-lookup"><span data-stu-id="a621f-150">The `Draft.zip` archive contains the root directory's files and subdirectories.</span></span> <span data-ttu-id="a621f-151">`Reference`Корневой каталог исключается из архива.</span><span class="sxs-lookup"><span data-stu-id="a621f-151">The `Reference` root directory is excluded from the archive.</span></span>

### <span data-ttu-id="a621f-152">Пример 5. сжатие только файлов в корневом каталоге</span><span class="sxs-lookup"><span data-stu-id="a621f-152">Example 5: Compress only the files in a root directory</span></span>

<span data-ttu-id="a621f-153">В этом примере выполняется сжатие только файлов в корневом каталоге и создание файла архива.</span><span class="sxs-lookup"><span data-stu-id="a621f-153">This example compresses only the files in a root directory and creates an archive file.</span></span> <span data-ttu-id="a621f-154">В архиве нет структуры каталогов, поскольку сжаты только файлы.</span><span class="sxs-lookup"><span data-stu-id="a621f-154">There's no directory structure in the archive because only files are compressed.</span></span>

```powershell
Compress-Archive -Path C:\Reference\*.* -DestinationPath C:\Archives\Draft.zip
```

<span data-ttu-id="a621f-155">`Compress-Archive` использует параметр **path** для указания корневого каталога `C:\Reference` с подстановочным знаком **"звезда-точка-звезда** " ( `*.*` ).</span><span class="sxs-lookup"><span data-stu-id="a621f-155">`Compress-Archive` uses the **Path** parameter to specify the root directory, `C:\Reference` with a **star-dot-star** (`*.*`) wildcard.</span></span> <span data-ttu-id="a621f-156">Параметр **DestinationPath** указывает расположение файла архива.</span><span class="sxs-lookup"><span data-stu-id="a621f-156">The **DestinationPath** parameter specifies the location for the archive file.</span></span> <span data-ttu-id="a621f-157">`Draft.zip`Архив содержит только `Reference` файлы корневого каталога, а корневой каталог исключается.</span><span class="sxs-lookup"><span data-stu-id="a621f-157">The `Draft.zip` archive only contains the `Reference` root directory's files and the root directory is excluded.</span></span>

### <span data-ttu-id="a621f-158">Пример 6. Использование конвейера для архивации файлов</span><span class="sxs-lookup"><span data-stu-id="a621f-158">Example 6: Use the pipeline to archive files</span></span>

<span data-ttu-id="a621f-159">В этом примере файлы посылаются по конвейеру для создания архива.</span><span class="sxs-lookup"><span data-stu-id="a621f-159">This example sends files down the pipeline to create an archive.</span></span> <span data-ttu-id="a621f-160">В файле архива нет структуры каталогов, так как **путь** указывает только имена файлов.</span><span class="sxs-lookup"><span data-stu-id="a621f-160">There's no directory structure in the archive file because the **Path** only specifies file names.</span></span>

```powershell
Get-ChildItem -Path C:\Reference\Afile.txt, C:\Reference\Images\Bfile.txt |
  Compress-Archive -DestinationPath C:\Archives\PipelineFiles.zip
```

<span data-ttu-id="a621f-161">`Get-ChildItem` использует параметр **path** для указания двух файлов из разных каталогов.</span><span class="sxs-lookup"><span data-stu-id="a621f-161">`Get-ChildItem` uses the **Path** parameter to specify two files from different directories.</span></span> <span data-ttu-id="a621f-162">Каждый файл представлен объектом **FileInfo** и отправляется по конвейеру в `Compress-Archive` .</span><span class="sxs-lookup"><span data-stu-id="a621f-162">Each file is represented by a **FileInfo** object and is sent down the pipeline to `Compress-Archive`.</span></span>
<span data-ttu-id="a621f-163">Два указанных файла архивируются в `PipelineFiles.zip` .</span><span class="sxs-lookup"><span data-stu-id="a621f-163">The two specified files are archived in `PipelineFiles.zip`.</span></span>

### <span data-ttu-id="a621f-164">Пример 7. Использование конвейера для архивации каталога</span><span class="sxs-lookup"><span data-stu-id="a621f-164">Example 7: Use the pipeline to archive a directory</span></span>

<span data-ttu-id="a621f-165">В этом примере каталог посылается по конвейеру для создания архива.</span><span class="sxs-lookup"><span data-stu-id="a621f-165">This example sends a directory down the pipeline to create an archive.</span></span> <span data-ttu-id="a621f-166">Файлы отправляются как объекты и каталоги **FileInfo** как объекты **DirectoryInfo** .</span><span class="sxs-lookup"><span data-stu-id="a621f-166">Files are sent as **FileInfo** objects and directories as **DirectoryInfo** objects.</span></span> <span data-ttu-id="a621f-167">Структура каталогов архива не включает корневой каталог, но его файлы и подкаталоги включены в архив.</span><span class="sxs-lookup"><span data-stu-id="a621f-167">The archive's directory structure doesn't include the root directory, but its files and subdirectories are included in the archive.</span></span>

```powershell
Get-ChildItem -Path C:\LogFiles | Compress-Archive -DestinationPath C:\Archives\PipelineDir.zip
```

<span data-ttu-id="a621f-168">`Get-ChildItem` использует параметр **path** для указания `C:\LogFiles` корневого каталога.</span><span class="sxs-lookup"><span data-stu-id="a621f-168">`Get-ChildItem` uses the **Path** parameter to specify the `C:\LogFiles` root directory.</span></span> <span data-ttu-id="a621f-169">Каждый объект **FileInfo** и **DirectoryInfo** отправляется по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="a621f-169">Each **FileInfo** and **DirectoryInfo** object is sent down the pipeline.</span></span>

<span data-ttu-id="a621f-170">`Compress-Archive` добавляет каждый объект в `PipelineDir.zip` Архив.</span><span class="sxs-lookup"><span data-stu-id="a621f-170">`Compress-Archive` adds each object to the `PipelineDir.zip` archive.</span></span> <span data-ttu-id="a621f-171">Параметр **пути** не указан, так как объекты конвейера получены в положении параметра 0.</span><span class="sxs-lookup"><span data-stu-id="a621f-171">The **Path** parameter isn't specified because the pipeline objects are received into parameter position 0.</span></span>

### <span data-ttu-id="a621f-172">Пример 8. как рекурсия может повлиять на архивы</span><span class="sxs-lookup"><span data-stu-id="a621f-172">Example 8: How recursion can affect archives</span></span>

<span data-ttu-id="a621f-173">В этом примере показано, как рекурсия может дублировать файлы в архиве.</span><span class="sxs-lookup"><span data-stu-id="a621f-173">This example shows how recursion can duplicate files in your archive.</span></span> <span data-ttu-id="a621f-174">Например, при использовании `Get-ChildItem` с параметром **рекурсии** .</span><span class="sxs-lookup"><span data-stu-id="a621f-174">For example, if you use `Get-ChildItem` with the **Recurse** parameter.</span></span> <span data-ttu-id="a621f-175">В качестве процессов рекурсии каждый объект **FileInfo** и **DirectoryInfo** отсылается по конвейеру и добавляется в архив.</span><span class="sxs-lookup"><span data-stu-id="a621f-175">As recursion processes, each **FileInfo** and **DirectoryInfo** object is sent down the pipeline and added to the archive.</span></span>

```powershell
Get-ChildItem -Path C:\TestLog -Recurse |
  Compress-Archive -DestinationPath C:\Archives\PipelineRecurse.zip
```

<span data-ttu-id="a621f-176">`C:\TestLog`Каталог не содержит файлов.</span><span class="sxs-lookup"><span data-stu-id="a621f-176">The `C:\TestLog` directory doesn't contain any files.</span></span> <span data-ttu-id="a621f-177">Он содержит подкаталог с именем `testsub` , содержащий `testlog.txt` файл.</span><span class="sxs-lookup"><span data-stu-id="a621f-177">It does contain a subdirectory named `testsub` that contains the `testlog.txt` file.</span></span>

<span data-ttu-id="a621f-178">`Get-ChildItem` использует параметр **path** для указания корневого каталога `C:\TestLog` .</span><span class="sxs-lookup"><span data-stu-id="a621f-178">`Get-ChildItem` uses the **Path** parameter to specify the root directory, `C:\TestLog`.</span></span> <span data-ttu-id="a621f-179">**Рекурсивный** параметр обрабатывает файлы и каталоги.</span><span class="sxs-lookup"><span data-stu-id="a621f-179">The **Recurse** parameter processes the files and directories.</span></span> <span data-ttu-id="a621f-180">Создается объект **DirectoryInfo** для `testsub` и объекта **FileInfo** `testlog.txt` .</span><span class="sxs-lookup"><span data-stu-id="a621f-180">A **DirectoryInfo** object is created for `testsub` and a **FileInfo** object `testlog.txt`.</span></span>

<span data-ttu-id="a621f-181">Каждый объект отправляется по конвейеру в `Compress-Archive` .</span><span class="sxs-lookup"><span data-stu-id="a621f-181">Each object is sent down the pipeline to `Compress-Archive`.</span></span> <span data-ttu-id="a621f-182">**DestinationPath** указывает расположение файла архива.</span><span class="sxs-lookup"><span data-stu-id="a621f-182">The **DestinationPath** specifies the location for the archive file.</span></span> <span data-ttu-id="a621f-183">Параметр **пути** не указан, так как объекты конвейера получены в положении параметра 0.</span><span class="sxs-lookup"><span data-stu-id="a621f-183">The **Path** parameter isn't specified because the pipeline objects are received into parameter position 0.</span></span>

<span data-ttu-id="a621f-184">Следующая сводка описывает `PipelineRecurse.zip` содержимое архива, которое содержит дубликат файла:</span><span class="sxs-lookup"><span data-stu-id="a621f-184">The following summary describes the `PipelineRecurse.zip` archive's contents that contains a duplicate file:</span></span>

- <span data-ttu-id="a621f-185">Объект **DirectoryInfo** создает `testsub` каталог и содержит `testlog.txt` файл, который отражает исходную структуру каталогов.</span><span class="sxs-lookup"><span data-stu-id="a621f-185">The **DirectoryInfo** object creates the `testsub` directory and contains the `testlog.txt` file, which reflects the original directory structure.</span></span>
- <span data-ttu-id="a621f-186">Объект **FileInfo** создает дубликат `testlog.txt` в корне архива.</span><span class="sxs-lookup"><span data-stu-id="a621f-186">The **FileInfo** object creates a duplicate `testlog.txt` in the archive's root.</span></span> <span data-ttu-id="a621f-187">Создается повторяющийся файл, так как рекурсия отправляет объект File в `Compress-Archive` .</span><span class="sxs-lookup"><span data-stu-id="a621f-187">The duplicate file is created because recursion sent a file object to `Compress-Archive`.</span></span> <span data-ttu-id="a621f-188">Это ожидаемое поведение, поскольку каждый объект, отправленный по конвейеру, добавляется в архив.</span><span class="sxs-lookup"><span data-stu-id="a621f-188">This behavior is expected because each object sent down the pipeline is added to the archive.</span></span>

### <span data-ttu-id="a621f-189">Пример 9. Обновление существующего файла архива</span><span class="sxs-lookup"><span data-stu-id="a621f-189">Example 9: Update an existing archive file</span></span>

<span data-ttu-id="a621f-190">В этом примере выполняется обновление существующего файла архива `Draft.Zip` в `C:\Archives` каталоге.</span><span class="sxs-lookup"><span data-stu-id="a621f-190">This example updates an existing archive file, `Draft.Zip`, in the `C:\Archives` directory.</span></span> <span data-ttu-id="a621f-191">В этом примере существующий файл архива содержит корневой каталог, а также его файлы и подкаталоги.</span><span class="sxs-lookup"><span data-stu-id="a621f-191">In this example, the existing archive file contains the root directory, and its files and subdirectories.</span></span>

```powershell
Compress-Archive -Path C:\Reference -Update -DestinationPath C:\Archives\Draft.Zip
```

<span data-ttu-id="a621f-192">Команда обновляется `Draft.Zip` с использованием более новых версий существующих файлов в `C:\Reference` каталоге и его подкаталогах.</span><span class="sxs-lookup"><span data-stu-id="a621f-192">The command updates `Draft.Zip` with newer versions of existing files in the `C:\Reference` directory and its subdirectories.</span></span> <span data-ttu-id="a621f-193">Новые файлы, добавленные в `C:\Reference` или его подкаталоги, включаются в обновленный `Draft.Zip` Архив.</span><span class="sxs-lookup"><span data-stu-id="a621f-193">And, new files that were added to `C:\Reference` or its subdirectories are included in the updated `Draft.Zip` archive.</span></span>

## <span data-ttu-id="a621f-194">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a621f-194">PARAMETERS</span></span>

### <span data-ttu-id="a621f-195">-CompressionLevel</span><span class="sxs-lookup"><span data-stu-id="a621f-195">-CompressionLevel</span></span>

<span data-ttu-id="a621f-196">Задает степень сжатия, применяемого при создании файла архива.</span><span class="sxs-lookup"><span data-stu-id="a621f-196">Specifies how much compression to apply when you're creating the archive file.</span></span> <span data-ttu-id="a621f-197">Более быстрое сжатие требует меньше времени на создание файла, но может привести к увеличению размеров файлов.</span><span class="sxs-lookup"><span data-stu-id="a621f-197">Faster compression requires less time to create the file, but can result in larger file sizes.</span></span>

<span data-ttu-id="a621f-198">Если этот параметр не указан, команда использует значение по умолчанию — **оптимальный**.</span><span class="sxs-lookup"><span data-stu-id="a621f-198">If this parameter isn't specified, the command uses the default value, **Optimal**.</span></span>

<span data-ttu-id="a621f-199">Ниже приведены допустимые значения для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="a621f-199">The following are the acceptable values for this parameter:</span></span>

- <span data-ttu-id="a621f-200">**Самый быстрый**.</span><span class="sxs-lookup"><span data-stu-id="a621f-200">**Fastest**.</span></span> <span data-ttu-id="a621f-201">Используйте самый быстрый метод сжатия, чтобы сократить время обработки.</span><span class="sxs-lookup"><span data-stu-id="a621f-201">Use the fastest compression method available to reduce processing time.</span></span> <span data-ttu-id="a621f-202">Более быстрое сжатие может привести к увеличению размеров файлов.</span><span class="sxs-lookup"><span data-stu-id="a621f-202">Faster compression can result in larger file sizes.</span></span>
- <span data-ttu-id="a621f-203">**Несжатие**.</span><span class="sxs-lookup"><span data-stu-id="a621f-203">**NoCompression**.</span></span> <span data-ttu-id="a621f-204">Не сжимает исходные файлы.</span><span class="sxs-lookup"><span data-stu-id="a621f-204">Doesn't compress the source files.</span></span>
- <span data-ttu-id="a621f-205">**Оптимальный**.</span><span class="sxs-lookup"><span data-stu-id="a621f-205">**Optimal**.</span></span> <span data-ttu-id="a621f-206">Время обработки зависит от размера файла.</span><span class="sxs-lookup"><span data-stu-id="a621f-206">Processing time is dependent on file size.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Optimal, NoCompression, Fastest

Required: False
Position: Named
Default value: Optimal
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a621f-207">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a621f-207">-Confirm</span></span>

<span data-ttu-id="a621f-208">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="a621f-208">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a621f-209">-DestinationPath</span><span class="sxs-lookup"><span data-stu-id="a621f-209">-DestinationPath</span></span>

<span data-ttu-id="a621f-210">Этот параметр является обязательным и указывает путь к выходному файлу архива.</span><span class="sxs-lookup"><span data-stu-id="a621f-210">This parameter is required and specifies the path to the archive output file.</span></span> <span data-ttu-id="a621f-211">**DestinationPath** должен включать имя ZIP-файла, а также абсолютный или относительный путь к ZIP-файлу.</span><span class="sxs-lookup"><span data-stu-id="a621f-211">The **DestinationPath** should include the name of the zipped file, and either the absolute or relative path to the zipped file.</span></span>

<span data-ttu-id="a621f-212">Если имя файла в **DestinationPath** не имеет `.zip` расширения имени файла, командлет добавляет `.zip` расширение имени файла.</span><span class="sxs-lookup"><span data-stu-id="a621f-212">If the file name in **DestinationPath** doesn't have a `.zip` file name extension, the cmdlet adds the `.zip` file name extension.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a621f-213">-Force</span><span class="sxs-lookup"><span data-stu-id="a621f-213">-Force</span></span>

<span data-ttu-id="a621f-214">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="a621f-214">Forces the command to run without asking for user confirmation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PathWithForce, LiteralPathWithForce
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a621f-215">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a621f-215">-LiteralPath</span></span>

<span data-ttu-id="a621f-216">Указывает путь или пути к файлам, которые необходимо добавить в архивный zip-файл.</span><span class="sxs-lookup"><span data-stu-id="a621f-216">Specifies the path or paths to the files that you want to add to the archive zipped file.</span></span> <span data-ttu-id="a621f-217">В отличие от параметра **path** , значение **LiteralPath** используется точно так же, как типизировано.</span><span class="sxs-lookup"><span data-stu-id="a621f-217">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="a621f-218">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="a621f-218">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="a621f-219">Если путь содержит escape-символы, заключите каждый escape-символ в одинарные кавычки, чтобы заставить PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="a621f-219">If the path includes escape characters, enclose each escape character in single quotation marks, to instruct PowerShell not to interpret any characters as escape sequences.</span></span>
<span data-ttu-id="a621f-220">Чтобы указать несколько путей и включить файлы в несколько расположений в выходном ZIP-файле, используйте запятые для разделения путей.</span><span class="sxs-lookup"><span data-stu-id="a621f-220">To specify multiple paths, and include files in multiple locations in your output zipped file, use commas to separate the paths.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPathWithUpdate, LiteralPathWithForce, LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a621f-221">-Path</span><span class="sxs-lookup"><span data-stu-id="a621f-221">-Path</span></span>

<span data-ttu-id="a621f-222">Указывает путь или пути к файлам, которые необходимо добавить в архивный zip-файл.</span><span class="sxs-lookup"><span data-stu-id="a621f-222">Specifies the path or paths to the files that you want to add to the archive zipped file.</span></span> <span data-ttu-id="a621f-223">Чтобы указать несколько путей и включить файлы в нескольких местах, используйте запятые для разделения путей.</span><span class="sxs-lookup"><span data-stu-id="a621f-223">To specify multiple paths, and include files in multiple locations, use commas to separate the paths.</span></span>

<span data-ttu-id="a621f-224">Этот параметр принимает подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="a621f-224">This parameter accepts wildcard characters.</span></span> <span data-ttu-id="a621f-225">Подстановочные знаки позволяют добавлять все файлы в каталоге в файл архива.</span><span class="sxs-lookup"><span data-stu-id="a621f-225">Wildcard characters allow you to add all files in a directory to your archive file.</span></span>

<span data-ttu-id="a621f-226">Использование подстановочных знаков с корневым каталогом влияет на содержимое архива:</span><span class="sxs-lookup"><span data-stu-id="a621f-226">Using wildcards with a root directory affects the archive's contents:</span></span>

- <span data-ttu-id="a621f-227">Чтобы создать архив, **включающий** корневой каталог и все его файлы и подкаталоги, укажите корневой каталог в **пути** без подстановочных знаков.</span><span class="sxs-lookup"><span data-stu-id="a621f-227">To create an archive that **includes** the root directory, and all its files and subdirectories, specify the root directory in the **Path** without wildcards.</span></span> <span data-ttu-id="a621f-228">Пример: `-Path C:\Reference`</span><span class="sxs-lookup"><span data-stu-id="a621f-228">For example: `-Path C:\Reference`</span></span>
- <span data-ttu-id="a621f-229">Чтобы создать архив, **исключающий** корневой каталог, но zips все его файлы и подкаталоги, используйте подстановочный знак "звездочка" ( `*` ).</span><span class="sxs-lookup"><span data-stu-id="a621f-229">To create an archive that **excludes** the root directory, but zips all its files and subdirectories, use the asterisk (`*`) wildcard.</span></span> <span data-ttu-id="a621f-230">Пример: `-Path C:\Reference\*`</span><span class="sxs-lookup"><span data-stu-id="a621f-230">For example: `-Path C:\Reference\*`</span></span>
- <span data-ttu-id="a621f-231">Чтобы создать архив, zips только файлы в корневом каталоге, используйте подстановочный знак **"звезда-точка-звезда** " ( `*.*` ).</span><span class="sxs-lookup"><span data-stu-id="a621f-231">To create an archive that only zips the files in the root directory, use the **star-dot-star** (`*.*`) wildcard.</span></span> <span data-ttu-id="a621f-232">Подкаталоги корневого каталога не включаются в архив.</span><span class="sxs-lookup"><span data-stu-id="a621f-232">Subdirectories of the root aren't included in the archive.</span></span> <span data-ttu-id="a621f-233">Пример: `-Path C:\Reference\*.*`</span><span class="sxs-lookup"><span data-stu-id="a621f-233">For example: `-Path C:\Reference\*.*`</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path, PathWithUpdate, PathWithForce
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="a621f-234">— Обновление</span><span class="sxs-lookup"><span data-stu-id="a621f-234">-Update</span></span>

<span data-ttu-id="a621f-235">Обновляет указанный архив, заменяя старые версии файлов в архиве более новыми версиями с теми же именами.</span><span class="sxs-lookup"><span data-stu-id="a621f-235">Updates the specified archive by replacing older file versions in the archive with newer file versions that have the same names.</span></span> <span data-ttu-id="a621f-236">Можно также добавить этот параметр, чтобы добавить файлы в существующий архив.</span><span class="sxs-lookup"><span data-stu-id="a621f-236">You can also add this parameter to add files to an existing archive.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PathWithUpdate, LiteralPathWithUpdate
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a621f-237">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a621f-237">-WhatIf</span></span>

<span data-ttu-id="a621f-238">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="a621f-238">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="a621f-239">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="a621f-239">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="a621f-240">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a621f-240">CommonParameters</span></span>

<span data-ttu-id="a621f-241">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a621f-241">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a621f-242">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a621f-242">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a621f-243">Входные данные</span><span class="sxs-lookup"><span data-stu-id="a621f-243">INPUTS</span></span>

### <span data-ttu-id="a621f-244">System.String</span><span class="sxs-lookup"><span data-stu-id="a621f-244">System.String</span></span>

<span data-ttu-id="a621f-245">Строку, содержащую путь, можно передать в один или несколько файлов.</span><span class="sxs-lookup"><span data-stu-id="a621f-245">You can pipe a string that contains a path to one or more files.</span></span>

## <span data-ttu-id="a621f-246">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a621f-246">OUTPUTS</span></span>

### <span data-ttu-id="a621f-247">Нет</span><span class="sxs-lookup"><span data-stu-id="a621f-247">None</span></span>

## <span data-ttu-id="a621f-248">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="a621f-248">NOTES</span></span>

<span data-ttu-id="a621f-249">Использование рекурсии и отправка объектов вниз по конвейеру могут дублировать файлы в архиве.</span><span class="sxs-lookup"><span data-stu-id="a621f-249">Using recursion and sending objects down the pipeline can duplicate files in your archive.</span></span> <span data-ttu-id="a621f-250">Например, при использовании `Get-ChildItem` с параметром **рекурсии** каждый объект **FileInfo** и **DirectoryInfo** , отправленный по конвейеру, добавляется в архив.</span><span class="sxs-lookup"><span data-stu-id="a621f-250">For example, if you use `Get-ChildItem` with the **Recurse** parameter, each **FileInfo** and **DirectoryInfo** object that's sent down the pipeline is added to the archive.</span></span>

<span data-ttu-id="a621f-251">В [спецификации ZIP-файла](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) не указан стандартный способ кодирования имен файлов, содержащих символы, не входящие в набор ASCII.</span><span class="sxs-lookup"><span data-stu-id="a621f-251">The [ZIP file specification](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) does not specify a standard way of encoding filenames that contain non-ASCII characters.</span></span> <span data-ttu-id="a621f-252">`Compress-Archive`Командлет использует кодировку UTF-8.</span><span class="sxs-lookup"><span data-stu-id="a621f-252">The `Compress-Archive` cmdlet uses UTF-8 encoding.</span></span> <span data-ttu-id="a621f-253">Другие средства архивирования ZIP могут использовать другую схему кодирования.</span><span class="sxs-lookup"><span data-stu-id="a621f-253">Other ZIP archive tools may use a different encoding scheme.</span></span> <span data-ttu-id="a621f-254">При извлечении файлов с именами, которые не хранятся в кодировке UTF-8, `Expand-Archive` использует необработанное значение, найденное в архиве.</span><span class="sxs-lookup"><span data-stu-id="a621f-254">When extracting files with filenames not stored using UTF-8 encoding, `Expand-Archive` uses the raw value found in the archive.</span></span> <span data-ttu-id="a621f-255">Это может привести к тому, что имя файла будет отличаться от исходного имени файла, хранящегося в архиве.</span><span class="sxs-lookup"><span data-stu-id="a621f-255">This can result in a filename that is different than the source filename stored in the archive.</span></span>

## <span data-ttu-id="a621f-256">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a621f-256">RELATED LINKS</span></span>

[<span data-ttu-id="a621f-257">Expand-Archive</span><span class="sxs-lookup"><span data-stu-id="a621f-257">Expand-Archive</span></span>](Expand-Archive.md)

[<span data-ttu-id="a621f-258">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="a621f-258">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)