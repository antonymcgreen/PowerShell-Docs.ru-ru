---
external help file: Microsoft.PowerShell.Archive-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Archive
ms.date: 02/20/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.archive/compress-archive?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Compress-Archive
ms.openlocfilehash: 7bf349c82133b275f0539db7b78c3583d00da31c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228222"
---
# <span data-ttu-id="8f2cc-103">Compress-Archive</span><span class="sxs-lookup"><span data-stu-id="8f2cc-103">Compress-Archive</span></span>

## <span data-ttu-id="8f2cc-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="8f2cc-104">SYNOPSIS</span></span>
<span data-ttu-id="8f2cc-105">Создает сжатый архив или ZIP-файл из указанных файлов и каталогов.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-105">Creates a compressed archive, or zipped file, from specified files and directories.</span></span>

## <span data-ttu-id="8f2cc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8f2cc-106">SYNTAX</span></span>

### <span data-ttu-id="8f2cc-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8f2cc-107">Path (Default)</span></span>

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="8f2cc-108">пасвисупдате</span><span class="sxs-lookup"><span data-stu-id="8f2cc-108">PathWithUpdate</span></span>

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>] -Update
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="8f2cc-109">пасвисфорце</span><span class="sxs-lookup"><span data-stu-id="8f2cc-109">PathWithForce</span></span>

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>] -Force
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="8f2cc-110">литералпасвисупдате</span><span class="sxs-lookup"><span data-stu-id="8f2cc-110">LiteralPathWithUpdate</span></span>

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 -Update [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="8f2cc-111">литералпасвисфорце</span><span class="sxs-lookup"><span data-stu-id="8f2cc-111">LiteralPathWithForce</span></span>

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 -Force [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="8f2cc-112">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="8f2cc-112">LiteralPath</span></span>

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="8f2cc-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8f2cc-113">DESCRIPTION</span></span>

<span data-ttu-id="8f2cc-114">`Compress-Archive`Командлет создает сжатый или ZIP-файл архива из одного или нескольких указанных файлов или каталогов.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-114">The `Compress-Archive` cmdlet creates a compressed, or zipped, archive file from one or more specified files or directories.</span></span> <span data-ttu-id="8f2cc-115">Архив упаковывает несколько файлов с необязательным сжатием в один ZIP-файл для упрощения распространения и хранения.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-115">An archive packages multiple files, with optional compression, into a single zipped file for easier distribution and storage.</span></span> <span data-ttu-id="8f2cc-116">Файл архива можно сжать с помощью алгоритма сжатия, заданного параметром **CompressionLevel** .</span><span class="sxs-lookup"><span data-stu-id="8f2cc-116">An archive file can be compressed by using the compression algorithm specified by the **CompressionLevel** parameter.</span></span>

<span data-ttu-id="8f2cc-117">`Compress-Archive`Командлет использует Microsoft .NET API [System.IO.Compression.ZipArchive](/dotnet/api/system.io.compression.ziparchive) для сжатия файлов.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-117">The `Compress-Archive` cmdlet uses the Microsoft .NET API [System.IO.Compression.ZipArchive](/dotnet/api/system.io.compression.ziparchive) to compress files.</span></span>
<span data-ttu-id="8f2cc-118">Максимальный размер файла составляет 2 ГБ, так как имеется ограничение на базовый API.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-118">The maximum file size is 2 GB because there's a limitation of the underlying API.</span></span>

<span data-ttu-id="8f2cc-119">В некоторых примерах Сплаттинг используется для сокращения длины строки примеров кода.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-119">Some examples use splatting to reduce the line length of the code samples.</span></span> <span data-ttu-id="8f2cc-120">Дополнительные сведения см. в разделе [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="8f2cc-120">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

## <span data-ttu-id="8f2cc-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="8f2cc-121">EXAMPLES</span></span>

### <span data-ttu-id="8f2cc-122">Пример 1. сжатие файлов для создания файла архива</span><span class="sxs-lookup"><span data-stu-id="8f2cc-122">Example 1: Compress files to create an archive file</span></span>

<span data-ttu-id="8f2cc-123">В этом примере производится сжатие файлов из разных каталогов и создание файла архива.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-123">This example compresses files from different directories and creates an archive file.</span></span> <span data-ttu-id="8f2cc-124">Для получения всех файлов с определенным расширением файла используется подстановочный знак.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-124">A wildcard is used to get all files with a particular file extension.</span></span> <span data-ttu-id="8f2cc-125">В файле архива нет структуры каталогов, так как **путь** указывает только имена файлов.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-125">There's no directory structure in the archive file because the **Path** only specifies file names.</span></span>

```powershell
$compress = @{
  Path = "C:\Reference\Draftdoc.docx", "C:\Reference\Images\*.vsd"
  CompressionLevel = "Fastest"
  DestinationPath = "C:\Archives\Draft.Zip"
}
Compress-Archive @compress
```

<span data-ttu-id="8f2cc-126">Параметр **path** принимает определенные имена файлов и имена файлов с подстановочными знаками, `*.vsd` .</span><span class="sxs-lookup"><span data-stu-id="8f2cc-126">The **Path** parameter accepts specific file names and file names with wildcards, `*.vsd`.</span></span> <span data-ttu-id="8f2cc-127">**Путь** использует список с разделителями-запятыми для получения файлов из разных каталогов.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-127">The **Path** uses a comma-separated list to get files from different directories.</span></span> <span data-ttu-id="8f2cc-128">Уровень сжатия **быстрее** всего используется для сокращения времени обработки.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-128">The compression level is **Fastest** to reduce processing time.</span></span> <span data-ttu-id="8f2cc-129">Параметр **DestinationPath** задает расположение `Draft.zip` файла.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-129">The **DestinationPath** parameter specifies the location for the `Draft.zip` file.</span></span> <span data-ttu-id="8f2cc-130">`Draft.zip`Файл содержит `Draftdoc.docx` и все файлы с `.vsd` расширением.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-130">The `Draft.zip` file contains `Draftdoc.docx` and all the files with a `.vsd` extension.</span></span>

### <span data-ttu-id="8f2cc-131">Пример 2. сжатие файлов с помощью LiteralPath</span><span class="sxs-lookup"><span data-stu-id="8f2cc-131">Example 2: Compress files using a LiteralPath</span></span>

<span data-ttu-id="8f2cc-132">Этот пример сжимает определенные именованные файлы и создает новый файл архива.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-132">This example compresses specific named files and creates a new archive file.</span></span> <span data-ttu-id="8f2cc-133">В файле архива нет структуры каталогов, так как **путь** указывает только имена файлов.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-133">There's no directory structure in the archive file because the **Path** only specifies file names.</span></span>

```powershell
$compress = @{
LiteralPath= "C:\Reference\Draft Doc.docx", "C:\Reference\Images\diagram2.vsd"
CompressionLevel = "Fastest"
DestinationPath = "C:\Archives\Draft.Zip"
}
Compress-Archive @compress
```

<span data-ttu-id="8f2cc-134">Используется абсолютный путь и имена файлов, так как параметр **LiteralPath** не принимает подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-134">Absolute path and file names are used because the **LiteralPath** parameter doesn't accept wildcards.</span></span> <span data-ttu-id="8f2cc-135">**Путь** использует список с разделителями-запятыми для получения файлов из разных каталогов.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-135">The **Path** uses a comma-separated list to get files from different directories.</span></span> <span data-ttu-id="8f2cc-136">Уровень сжатия **быстрее** всего используется для сокращения времени обработки.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-136">The compression level is **Fastest** to reduce processing time.</span></span> <span data-ttu-id="8f2cc-137">Параметр **DestinationPath** задает расположение `Draft.zip` файла.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-137">The **DestinationPath** parameter specifies the location for the `Draft.zip` file.</span></span> <span data-ttu-id="8f2cc-138">`Draft.zip`Файл содержит только `Draftdoc.docx` и `diagram2.vsd` .</span><span class="sxs-lookup"><span data-stu-id="8f2cc-138">The `Draft.zip` file only contains `Draftdoc.docx` and `diagram2.vsd`.</span></span>

### <span data-ttu-id="8f2cc-139">Пример 3. Сжатие каталога, содержащего корневой каталог</span><span class="sxs-lookup"><span data-stu-id="8f2cc-139">Example 3: Compress a directory that includes the root directory</span></span>

<span data-ttu-id="8f2cc-140">В этом примере сжимается каталог и создается файл архива, **содержащий** корневой каталог и все его файлы и подкаталоги.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-140">This example compresses a directory and creates an archive file that **includes** the root directory, and all its files and subdirectories.</span></span> <span data-ttu-id="8f2cc-141">Файл архива имеет структуру каталогов, так как **путь** указывает корневой каталог.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-141">The archive file has a directory structure because the **Path** specifies a root directory.</span></span>

```powershell
Compress-Archive -Path C:\Reference -DestinationPath C:\Archives\Draft.zip
```

<span data-ttu-id="8f2cc-142">`Compress-Archive` использует параметр **path** для указания корневого каталога `C:\Reference` .</span><span class="sxs-lookup"><span data-stu-id="8f2cc-142">`Compress-Archive` uses the **Path** parameter to specify the root directory, `C:\Reference`.</span></span> <span data-ttu-id="8f2cc-143">Параметр **DestinationPath** указывает расположение файла архива.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-143">The **DestinationPath** parameter specifies the location for the archive file.</span></span> <span data-ttu-id="8f2cc-144">`Draft.zip`Архив включает `Reference` корневой каталог и все его файлы и подкаталоги.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-144">The `Draft.zip` archive includes the `Reference` root directory, and all its files and subdirectories.</span></span>

### <span data-ttu-id="8f2cc-145">Пример 4. Сжатие каталога, который исключает корневой каталог</span><span class="sxs-lookup"><span data-stu-id="8f2cc-145">Example 4: Compress a directory that excludes the root directory</span></span>

<span data-ttu-id="8f2cc-146">В этом примере выполняется сжатие каталога и создается файл архива, который **исключает** корневой каталог, поскольку **путь** использует `*` подстановочный знак звездочки ().</span><span class="sxs-lookup"><span data-stu-id="8f2cc-146">This example compresses a directory and creates an archive file that **excludes** the root directory because the **Path** uses an asterisk (`*`) wildcard.</span></span> <span data-ttu-id="8f2cc-147">Архив содержит структуру каталогов, содержащую файлы и подкаталоги корневого каталога.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-147">The archive contains a directory structure that contains the root directory's files and subdirectories.</span></span>

```powershell
Compress-Archive -Path C:\Reference\* -DestinationPath C:\Archives\Draft.zip
```

<span data-ttu-id="8f2cc-148">`Compress-Archive` использует параметр **path** для указания корневого каталога `C:\Reference` с `*` подстановочным знаком звездочки ().</span><span class="sxs-lookup"><span data-stu-id="8f2cc-148">`Compress-Archive` uses the **Path** parameter to specify the root directory, `C:\Reference` with an asterisk (`*`) wildcard.</span></span> <span data-ttu-id="8f2cc-149">Параметр **DestinationPath** указывает расположение файла архива.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-149">The **DestinationPath** parameter specifies the location for the archive file.</span></span> <span data-ttu-id="8f2cc-150">`Draft.zip`Архив содержит файлы и подкаталоги корневого каталога.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-150">The `Draft.zip` archive contains the root directory's files and subdirectories.</span></span> <span data-ttu-id="8f2cc-151">`Reference`Корневой каталог исключается из архива.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-151">The `Reference` root directory is excluded from the archive.</span></span>

### <span data-ttu-id="8f2cc-152">Пример 5. сжатие только файлов в корневом каталоге</span><span class="sxs-lookup"><span data-stu-id="8f2cc-152">Example 5: Compress only the files in a root directory</span></span>

<span data-ttu-id="8f2cc-153">В этом примере выполняется сжатие только файлов в корневом каталоге и создание файла архива.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-153">This example compresses only the files in a root directory and creates an archive file.</span></span> <span data-ttu-id="8f2cc-154">В архиве нет структуры каталогов, поскольку сжаты только файлы.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-154">There's no directory structure in the archive because only files are compressed.</span></span>

```powershell
Compress-Archive -Path C:\Reference\*.* -DestinationPath C:\Archives\Draft.zip
```

<span data-ttu-id="8f2cc-155">`Compress-Archive` использует параметр **path** для указания корневого каталога `C:\Reference` с подстановочным знаком **"звезда-точка-звезда** " ( `*.*` ).</span><span class="sxs-lookup"><span data-stu-id="8f2cc-155">`Compress-Archive` uses the **Path** parameter to specify the root directory, `C:\Reference` with a **star-dot-star** (`*.*`) wildcard.</span></span> <span data-ttu-id="8f2cc-156">Параметр **DestinationPath** указывает расположение файла архива.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-156">The **DestinationPath** parameter specifies the location for the archive file.</span></span> <span data-ttu-id="8f2cc-157">`Draft.zip`Архив содержит только `Reference` файлы корневого каталога, а корневой каталог исключается.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-157">The `Draft.zip` archive only contains the `Reference` root directory's files and the root directory is excluded.</span></span>

### <span data-ttu-id="8f2cc-158">Пример 6. Использование конвейера для архивации файлов</span><span class="sxs-lookup"><span data-stu-id="8f2cc-158">Example 6: Use the pipeline to archive files</span></span>

<span data-ttu-id="8f2cc-159">В этом примере файлы посылаются по конвейеру для создания архива.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-159">This example sends files down the pipeline to create an archive.</span></span> <span data-ttu-id="8f2cc-160">В файле архива нет структуры каталогов, так как **путь** указывает только имена файлов.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-160">There's no directory structure in the archive file because the **Path** only specifies file names.</span></span>

```powershell
Get-ChildItem -Path C:\Reference\Afile.txt, C:\Reference\Images\Bfile.txt |
  Compress-Archive -DestinationPath C:\Archives\PipelineFiles.zip
```

<span data-ttu-id="8f2cc-161">`Get-ChildItem` использует параметр **path** для указания двух файлов из разных каталогов.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-161">`Get-ChildItem` uses the **Path** parameter to specify two files from different directories.</span></span> <span data-ttu-id="8f2cc-162">Каждый файл представлен объектом **FileInfo** и отправляется по конвейеру в `Compress-Archive` .</span><span class="sxs-lookup"><span data-stu-id="8f2cc-162">Each file is represented by a **FileInfo** object and is sent down the pipeline to `Compress-Archive`.</span></span>
<span data-ttu-id="8f2cc-163">Два указанных файла архивируются в `PipelineFiles.zip` .</span><span class="sxs-lookup"><span data-stu-id="8f2cc-163">The two specified files are archived in `PipelineFiles.zip`.</span></span>

### <span data-ttu-id="8f2cc-164">Пример 7. Использование конвейера для архивации каталога</span><span class="sxs-lookup"><span data-stu-id="8f2cc-164">Example 7: Use the pipeline to archive a directory</span></span>

<span data-ttu-id="8f2cc-165">В этом примере каталог посылается по конвейеру для создания архива.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-165">This example sends a directory down the pipeline to create an archive.</span></span> <span data-ttu-id="8f2cc-166">Файлы отправляются как объекты и каталоги **FileInfo** как объекты **DirectoryInfo** .</span><span class="sxs-lookup"><span data-stu-id="8f2cc-166">Files are sent as **FileInfo** objects and directories as **DirectoryInfo** objects.</span></span> <span data-ttu-id="8f2cc-167">Структура каталогов архива не включает корневой каталог, но его файлы и подкаталоги включены в архив.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-167">The archive's directory structure doesn't include the root directory, but its files and subdirectories are included in the archive.</span></span>

```powershell
Get-ChildItem -Path C:\LogFiles | Compress-Archive -DestinationPath C:\Archives\PipelineDir.zip
```

<span data-ttu-id="8f2cc-168">`Get-ChildItem` использует параметр **path** для указания `C:\LogFiles` корневого каталога.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-168">`Get-ChildItem` uses the **Path** parameter to specify the `C:\LogFiles` root directory.</span></span> <span data-ttu-id="8f2cc-169">Каждый объект **FileInfo** и **DirectoryInfo** отправляется по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-169">Each **FileInfo** and **DirectoryInfo** object is sent down the pipeline.</span></span>

<span data-ttu-id="8f2cc-170">`Compress-Archive` добавляет каждый объект в `PipelineDir.zip` Архив.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-170">`Compress-Archive` adds each object to the `PipelineDir.zip` archive.</span></span> <span data-ttu-id="8f2cc-171">Параметр **пути** не указан, так как объекты конвейера получены в положении параметра 0.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-171">The **Path** parameter isn't specified because the pipeline objects are received into parameter position 0.</span></span>

### <span data-ttu-id="8f2cc-172">Пример 8. как рекурсия может повлиять на архивы</span><span class="sxs-lookup"><span data-stu-id="8f2cc-172">Example 8: How recursion can affect archives</span></span>

<span data-ttu-id="8f2cc-173">В этом примере показано, как рекурсия может дублировать файлы в архиве.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-173">This example shows how recursion can duplicate files in your archive.</span></span> <span data-ttu-id="8f2cc-174">Например, при использовании `Get-ChildItem` с параметром **рекурсии** .</span><span class="sxs-lookup"><span data-stu-id="8f2cc-174">For example, if you use `Get-ChildItem` with the **Recurse** parameter.</span></span> <span data-ttu-id="8f2cc-175">В качестве процессов рекурсии каждый объект **FileInfo** и **DirectoryInfo** отсылается по конвейеру и добавляется в архив.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-175">As recursion processes, each **FileInfo** and **DirectoryInfo** object is sent down the pipeline and added to the archive.</span></span>

```powershell
Get-ChildItem -Path C:\TestLog -Recurse |
  Compress-Archive -DestinationPath C:\Archives\PipelineRecurse.zip
```

<span data-ttu-id="8f2cc-176">`C:\TestLog`Каталог не содержит файлов.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-176">The `C:\TestLog` directory doesn't contain any files.</span></span> <span data-ttu-id="8f2cc-177">Он содержит подкаталог с именем `testsub` , содержащий `testlog.txt` файл.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-177">It does contain a subdirectory named `testsub` that contains the `testlog.txt` file.</span></span>

<span data-ttu-id="8f2cc-178">`Get-ChildItem` использует параметр **path** для указания корневого каталога `C:\TestLog` .</span><span class="sxs-lookup"><span data-stu-id="8f2cc-178">`Get-ChildItem` uses the **Path** parameter to specify the root directory, `C:\TestLog`.</span></span> <span data-ttu-id="8f2cc-179">**Рекурсивный** параметр обрабатывает файлы и каталоги.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-179">The **Recurse** parameter processes the files and directories.</span></span> <span data-ttu-id="8f2cc-180">Создается объект **DirectoryInfo** для `testsub` и объекта **FileInfo** `testlog.txt` .</span><span class="sxs-lookup"><span data-stu-id="8f2cc-180">A **DirectoryInfo** object is created for `testsub` and a **FileInfo** object `testlog.txt`.</span></span>

<span data-ttu-id="8f2cc-181">Каждый объект отправляется по конвейеру в `Compress-Archive` .</span><span class="sxs-lookup"><span data-stu-id="8f2cc-181">Each object is sent down the pipeline to `Compress-Archive`.</span></span> <span data-ttu-id="8f2cc-182">**DestinationPath** указывает расположение файла архива.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-182">The **DestinationPath** specifies the location for the archive file.</span></span> <span data-ttu-id="8f2cc-183">Параметр **пути** не указан, так как объекты конвейера получены в положении параметра 0.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-183">The **Path** parameter isn't specified because the pipeline objects are received into parameter position 0.</span></span>

<span data-ttu-id="8f2cc-184">Следующая сводка описывает `PipelineRecurse.zip` содержимое архива, которое содержит дубликат файла:</span><span class="sxs-lookup"><span data-stu-id="8f2cc-184">The following summary describes the `PipelineRecurse.zip` archive's contents that contains a duplicate file:</span></span>

- <span data-ttu-id="8f2cc-185">Объект **DirectoryInfo** создает `testsub` каталог и содержит `testlog.txt` файл, который отражает исходную структуру каталогов.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-185">The **DirectoryInfo** object creates the `testsub` directory and contains the `testlog.txt` file, which reflects the original directory structure.</span></span>
- <span data-ttu-id="8f2cc-186">Объект **FileInfo** создает дубликат `testlog.txt` в корне архива.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-186">The **FileInfo** object creates a duplicate `testlog.txt` in the archive's root.</span></span> <span data-ttu-id="8f2cc-187">Создается повторяющийся файл, так как рекурсия отправляет объект File в `Compress-Archive` .</span><span class="sxs-lookup"><span data-stu-id="8f2cc-187">The duplicate file is created because recursion sent a file object to `Compress-Archive`.</span></span> <span data-ttu-id="8f2cc-188">Это ожидаемое поведение, поскольку каждый объект, отправленный по конвейеру, добавляется в архив.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-188">This behavior is expected because each object sent down the pipeline is added to the archive.</span></span>

### <span data-ttu-id="8f2cc-189">Пример 9. Обновление существующего файла архива</span><span class="sxs-lookup"><span data-stu-id="8f2cc-189">Example 9: Update an existing archive file</span></span>

<span data-ttu-id="8f2cc-190">В этом примере выполняется обновление существующего файла архива `Draft.Zip` в `C:\Archives` каталоге.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-190">This example updates an existing archive file, `Draft.Zip`, in the `C:\Archives` directory.</span></span> <span data-ttu-id="8f2cc-191">В этом примере существующий файл архива содержит корневой каталог, а также его файлы и подкаталоги.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-191">In this example, the existing archive file contains the root directory, and its files and subdirectories.</span></span>

```powershell
Compress-Archive -Path C:\Reference -Update -DestinationPath C:\Archives\Draft.Zip
```

<span data-ttu-id="8f2cc-192">Команда обновляется `Draft.Zip` с использованием более новых версий существующих файлов в `C:\Reference` каталоге и его подкаталогах.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-192">The command updates `Draft.Zip` with newer versions of existing files in the `C:\Reference` directory and its subdirectories.</span></span> <span data-ttu-id="8f2cc-193">Новые файлы, добавленные в `C:\Reference` или его подкаталоги, включаются в обновленный `Draft.Zip` Архив.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-193">And, new files that were added to `C:\Reference` or its subdirectories are included in the updated `Draft.Zip` archive.</span></span>

## <span data-ttu-id="8f2cc-194">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8f2cc-194">PARAMETERS</span></span>

### <span data-ttu-id="8f2cc-195">-CompressionLevel</span><span class="sxs-lookup"><span data-stu-id="8f2cc-195">-CompressionLevel</span></span>

<span data-ttu-id="8f2cc-196">Задает степень сжатия, применяемого при создании файла архива.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-196">Specifies how much compression to apply when you're creating the archive file.</span></span> <span data-ttu-id="8f2cc-197">Более быстрое сжатие требует меньше времени на создание файла, но может привести к увеличению размеров файлов.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-197">Faster compression requires less time to create the file, but can result in larger file sizes.</span></span>

<span data-ttu-id="8f2cc-198">Если этот параметр не указан, команда использует значение по умолчанию — **оптимальный** .</span><span class="sxs-lookup"><span data-stu-id="8f2cc-198">If this parameter isn't specified, the command uses the default value, **Optimal** .</span></span>

<span data-ttu-id="8f2cc-199">Ниже приведены допустимые значения для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-199">The following are the acceptable values for this parameter:</span></span>

- <span data-ttu-id="8f2cc-200">**Самый быстрый** .</span><span class="sxs-lookup"><span data-stu-id="8f2cc-200">**Fastest** .</span></span> <span data-ttu-id="8f2cc-201">Используйте самый быстрый метод сжатия, чтобы сократить время обработки.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-201">Use the fastest compression method available to reduce processing time.</span></span> <span data-ttu-id="8f2cc-202">Более быстрое сжатие может привести к увеличению размеров файлов.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-202">Faster compression can result in larger file sizes.</span></span>
- <span data-ttu-id="8f2cc-203">**Несжатие** .</span><span class="sxs-lookup"><span data-stu-id="8f2cc-203">**NoCompression** .</span></span> <span data-ttu-id="8f2cc-204">Не сжимает исходные файлы.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-204">Doesn't compress the source files.</span></span>
- <span data-ttu-id="8f2cc-205">**Оптимальный** .</span><span class="sxs-lookup"><span data-stu-id="8f2cc-205">**Optimal** .</span></span> <span data-ttu-id="8f2cc-206">Время обработки зависит от размера файла.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-206">Processing time is dependent on file size.</span></span>

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

### <span data-ttu-id="8f2cc-207">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8f2cc-207">-Confirm</span></span>

<span data-ttu-id="8f2cc-208">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-208">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="8f2cc-209">-DestinationPath</span><span class="sxs-lookup"><span data-stu-id="8f2cc-209">-DestinationPath</span></span>

<span data-ttu-id="8f2cc-210">Этот параметр является обязательным и указывает путь к выходному файлу архива.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-210">This parameter is required and specifies the path to the archive output file.</span></span> <span data-ttu-id="8f2cc-211">**DestinationPath** должен включать имя ZIP-файла, а также абсолютный или относительный путь к ZIP-файлу.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-211">The **DestinationPath** should include the name of the zipped file, and either the absolute or relative path to the zipped file.</span></span>

<span data-ttu-id="8f2cc-212">Если имя файла в **DestinationPath** не имеет `.zip` расширения имени файла, командлет добавляет `.zip` расширение имени файла.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-212">If the file name in **DestinationPath** doesn't have a `.zip` file name extension, the cmdlet adds the `.zip` file name extension.</span></span>

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

### <span data-ttu-id="8f2cc-213">-Force</span><span class="sxs-lookup"><span data-stu-id="8f2cc-213">-Force</span></span>

<span data-ttu-id="8f2cc-214">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-214">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="8f2cc-215">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="8f2cc-215">-LiteralPath</span></span>

<span data-ttu-id="8f2cc-216">Указывает путь или пути к файлам, которые необходимо добавить в архивный zip-файл.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-216">Specifies the path or paths to the files that you want to add to the archive zipped file.</span></span> <span data-ttu-id="8f2cc-217">В отличие от параметра **path** , значение **LiteralPath** используется точно так же, как типизировано.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-217">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="8f2cc-218">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-218">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="8f2cc-219">Если путь содержит escape-символы, заключите каждый escape-символ в одинарные кавычки, чтобы заставить PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-219">If the path includes escape characters, enclose each escape character in single quotation marks, to instruct PowerShell not to interpret any characters as escape sequences.</span></span>
<span data-ttu-id="8f2cc-220">Чтобы указать несколько путей и включить файлы в несколько расположений в выходном ZIP-файле, используйте запятые для разделения путей.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-220">To specify multiple paths, and include files in multiple locations in your output zipped file, use commas to separate the paths.</span></span>

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

### <span data-ttu-id="8f2cc-221">-PassThru</span><span class="sxs-lookup"><span data-stu-id="8f2cc-221">-PassThru</span></span>

<span data-ttu-id="8f2cc-222">Заставляет командлет вывести объект File, представляющий созданный файл архива.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-222">Causes the cmdlet to output a file object representing the archive file created.</span></span>

<span data-ttu-id="8f2cc-223">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-223">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="8f2cc-224">-Path</span><span class="sxs-lookup"><span data-stu-id="8f2cc-224">-Path</span></span>

<span data-ttu-id="8f2cc-225">Указывает путь или пути к файлам, которые необходимо добавить в архивный zip-файл.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-225">Specifies the path or paths to the files that you want to add to the archive zipped file.</span></span> <span data-ttu-id="8f2cc-226">Чтобы указать несколько путей и включить файлы в нескольких местах, используйте запятые для разделения путей.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-226">To specify multiple paths, and include files in multiple locations, use commas to separate the paths.</span></span>

<span data-ttu-id="8f2cc-227">Этот параметр принимает подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-227">This parameter accepts wildcard characters.</span></span> <span data-ttu-id="8f2cc-228">Подстановочные знаки позволяют добавлять все файлы в каталоге в файл архива.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-228">Wildcard characters allow you to add all files in a directory to your archive file.</span></span>

<span data-ttu-id="8f2cc-229">Использование подстановочных знаков с корневым каталогом влияет на содержимое архива:</span><span class="sxs-lookup"><span data-stu-id="8f2cc-229">Using wildcards with a root directory affects the archive's contents:</span></span>

- <span data-ttu-id="8f2cc-230">Чтобы создать архив, **включающий** корневой каталог и все его файлы и подкаталоги, укажите корневой каталог в **пути** без подстановочных знаков.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-230">To create an archive that **includes** the root directory, and all its files and subdirectories, specify the root directory in the **Path** without wildcards.</span></span> <span data-ttu-id="8f2cc-231">Пример: `-Path C:\Reference`</span><span class="sxs-lookup"><span data-stu-id="8f2cc-231">For example: `-Path C:\Reference`</span></span>
- <span data-ttu-id="8f2cc-232">Чтобы создать архив, **исключающий** корневой каталог, но zips все его файлы и подкаталоги, используйте подстановочный знак "звездочка" ( `*` ).</span><span class="sxs-lookup"><span data-stu-id="8f2cc-232">To create an archive that **excludes** the root directory, but zips all its files and subdirectories, use the asterisk (`*`) wildcard.</span></span> <span data-ttu-id="8f2cc-233">Пример: `-Path C:\Reference\*`</span><span class="sxs-lookup"><span data-stu-id="8f2cc-233">For example: `-Path C:\Reference\*`</span></span>
- <span data-ttu-id="8f2cc-234">Чтобы создать архив, zips только файлы в корневом каталоге, используйте подстановочный знак **"звезда-точка-звезда** " ( `*.*` ).</span><span class="sxs-lookup"><span data-stu-id="8f2cc-234">To create an archive that only zips the files in the root directory, use the **star-dot-star** (`*.*`) wildcard.</span></span> <span data-ttu-id="8f2cc-235">Подкаталоги корневого каталога не включаются в архив.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-235">Subdirectories of the root aren't included in the archive.</span></span> <span data-ttu-id="8f2cc-236">Пример: `-Path C:\Reference\*.*`</span><span class="sxs-lookup"><span data-stu-id="8f2cc-236">For example: `-Path C:\Reference\*.*`</span></span>

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

### <span data-ttu-id="8f2cc-237">— Обновление</span><span class="sxs-lookup"><span data-stu-id="8f2cc-237">-Update</span></span>

<span data-ttu-id="8f2cc-238">Обновляет указанный архив, заменяя старые версии файлов в архиве более новыми версиями с теми же именами.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-238">Updates the specified archive by replacing older file versions in the archive with newer file versions that have the same names.</span></span> <span data-ttu-id="8f2cc-239">Можно также добавить этот параметр, чтобы добавить файлы в существующий архив.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-239">You can also add this parameter to add files to an existing archive.</span></span>

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

### <span data-ttu-id="8f2cc-240">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8f2cc-240">-WhatIf</span></span>

<span data-ttu-id="8f2cc-241">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-241">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="8f2cc-242">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-242">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="8f2cc-243">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="8f2cc-243">CommonParameters</span></span>

<span data-ttu-id="8f2cc-244">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-244">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8f2cc-245">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8f2cc-245">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8f2cc-246">Входные данные</span><span class="sxs-lookup"><span data-stu-id="8f2cc-246">INPUTS</span></span>

### <span data-ttu-id="8f2cc-247">System.String</span><span class="sxs-lookup"><span data-stu-id="8f2cc-247">System.String</span></span>

<span data-ttu-id="8f2cc-248">Строку, содержащую путь, можно передать в один или несколько файлов.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-248">You can pipe a string that contains a path to one or more files.</span></span>

## <span data-ttu-id="8f2cc-249">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="8f2cc-249">OUTPUTS</span></span>

### <span data-ttu-id="8f2cc-250">System. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="8f2cc-250">System.IO.FileInfo</span></span>

<span data-ttu-id="8f2cc-251">Командлет возвращает объект **FileInfo** только при использовании параметра **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="8f2cc-251">The cmdlet only returns a **FileInfo** object when you use the **PassThru** parameter.</span></span>

## <span data-ttu-id="8f2cc-252">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="8f2cc-252">NOTES</span></span>

<span data-ttu-id="8f2cc-253">Использование рекурсии и отправка объектов вниз по конвейеру могут дублировать файлы в архиве.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-253">Using recursion and sending objects down the pipeline can duplicate files in your archive.</span></span> <span data-ttu-id="8f2cc-254">Например, при использовании `Get-ChildItem` с параметром **рекурсии** каждый объект **FileInfo** и **DirectoryInfo** , отправленный по конвейеру, добавляется в архив.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-254">For example, if you use `Get-ChildItem` with the **Recurse** parameter, each **FileInfo** and **DirectoryInfo** object that's sent down the pipeline is added to the archive.</span></span>

<span data-ttu-id="8f2cc-255">В [спецификации ZIP-файла](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) не указан стандартный способ кодирования имен файлов, содержащих символы, не входящие в набор ASCII.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-255">The [ZIP file specification](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) does not specify a standard way of encoding filenames that contain non-ASCII characters.</span></span> <span data-ttu-id="8f2cc-256">`Compress-Archive`Командлет использует кодировку UTF-8.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-256">The `Compress-Archive` cmdlet uses UTF-8 encoding.</span></span> <span data-ttu-id="8f2cc-257">Другие средства архивирования ZIP могут использовать другую схему кодирования.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-257">Other ZIP archive tools may use a different encoding scheme.</span></span> <span data-ttu-id="8f2cc-258">При извлечении файлов с именами, которые не хранятся в кодировке UTF-8, `Expand-Archive` использует необработанное значение, найденное в архиве.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-258">When extracting files with filenames not stored using UTF-8 encoding, `Expand-Archive` uses the raw value found in the archive.</span></span> <span data-ttu-id="8f2cc-259">Это может привести к тому, что имя файла будет отличаться от исходного имени файла, хранящегося в архиве.</span><span class="sxs-lookup"><span data-stu-id="8f2cc-259">This can result in a filename that is different than the source filename stored in the archive.</span></span>

## <span data-ttu-id="8f2cc-260">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="8f2cc-260">RELATED LINKS</span></span>

[<span data-ttu-id="8f2cc-261">Expand-Archive</span><span class="sxs-lookup"><span data-stu-id="8f2cc-261">Expand-Archive</span></span>](Expand-Archive.md)

[<span data-ttu-id="8f2cc-262">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="8f2cc-262">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)
