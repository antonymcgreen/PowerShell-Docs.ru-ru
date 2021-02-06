---
external help file: Microsoft.PowerShell.Archive-help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Archive
ms.date: 02/20/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.archive/compress-archive?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Compress-Archive
ms.openlocfilehash: 58807ba0745a6b09e7956547425c489b427d4f4b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605039"
---
# <span data-ttu-id="62550-102">Compress-Archive</span><span class="sxs-lookup"><span data-stu-id="62550-102">Compress-Archive</span></span>

## <span data-ttu-id="62550-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="62550-103">SYNOPSIS</span></span>
<span data-ttu-id="62550-104">Создает сжатый архив или ZIP-файл из указанных файлов и каталогов.</span><span class="sxs-lookup"><span data-stu-id="62550-104">Creates a compressed archive, or zipped file, from specified files and directories.</span></span>

## <span data-ttu-id="62550-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="62550-105">SYNTAX</span></span>

### <span data-ttu-id="62550-106">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="62550-106">Path (Default)</span></span>

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="62550-107">пасвисупдате</span><span class="sxs-lookup"><span data-stu-id="62550-107">PathWithUpdate</span></span>

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>] -Update
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="62550-108">пасвисфорце</span><span class="sxs-lookup"><span data-stu-id="62550-108">PathWithForce</span></span>

```
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-CompressionLevel <String>] -Force
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="62550-109">литералпасвисупдате</span><span class="sxs-lookup"><span data-stu-id="62550-109">LiteralPathWithUpdate</span></span>

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 -Update [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="62550-110">литералпасвисфорце</span><span class="sxs-lookup"><span data-stu-id="62550-110">LiteralPathWithForce</span></span>

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 -Force [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="62550-111">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="62550-111">LiteralPath</span></span>

```
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-CompressionLevel <String>]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="62550-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="62550-112">DESCRIPTION</span></span>

<span data-ttu-id="62550-113">`Compress-Archive`Командлет создает сжатый или ZIP-файл архива из одного или нескольких указанных файлов или каталогов.</span><span class="sxs-lookup"><span data-stu-id="62550-113">The `Compress-Archive` cmdlet creates a compressed, or zipped, archive file from one or more specified files or directories.</span></span> <span data-ttu-id="62550-114">Архив упаковывает несколько файлов с необязательным сжатием в один ZIP-файл для упрощения распространения и хранения.</span><span class="sxs-lookup"><span data-stu-id="62550-114">An archive packages multiple files, with optional compression, into a single zipped file for easier distribution and storage.</span></span> <span data-ttu-id="62550-115">Файл архива можно сжать с помощью алгоритма сжатия, заданного параметром **CompressionLevel** .</span><span class="sxs-lookup"><span data-stu-id="62550-115">An archive file can be compressed by using the compression algorithm specified by the **CompressionLevel** parameter.</span></span>

<span data-ttu-id="62550-116">`Compress-Archive`Командлет использует Microsoft .NET API [System.IO.Compression.ZipArchive](/dotnet/api/system.io.compression.ziparchive) для сжатия файлов.</span><span class="sxs-lookup"><span data-stu-id="62550-116">The `Compress-Archive` cmdlet uses the Microsoft .NET API [System.IO.Compression.ZipArchive](/dotnet/api/system.io.compression.ziparchive) to compress files.</span></span>
<span data-ttu-id="62550-117">Максимальный размер файла составляет 2 ГБ, так как имеется ограничение на базовый API.</span><span class="sxs-lookup"><span data-stu-id="62550-117">The maximum file size is 2 GB because there's a limitation of the underlying API.</span></span>

<span data-ttu-id="62550-118">В некоторых примерах Сплаттинг используется для сокращения длины строки примеров кода.</span><span class="sxs-lookup"><span data-stu-id="62550-118">Some examples use splatting to reduce the line length of the code samples.</span></span> <span data-ttu-id="62550-119">Дополнительные сведения см. в разделе [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="62550-119">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

## <span data-ttu-id="62550-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="62550-120">EXAMPLES</span></span>

### <span data-ttu-id="62550-121">Пример 1. сжатие файлов для создания файла архива</span><span class="sxs-lookup"><span data-stu-id="62550-121">Example 1: Compress files to create an archive file</span></span>

<span data-ttu-id="62550-122">В этом примере производится сжатие файлов из разных каталогов и создание файла архива.</span><span class="sxs-lookup"><span data-stu-id="62550-122">This example compresses files from different directories and creates an archive file.</span></span> <span data-ttu-id="62550-123">Для получения всех файлов с определенным расширением файла используется подстановочный знак.</span><span class="sxs-lookup"><span data-stu-id="62550-123">A wildcard is used to get all files with a particular file extension.</span></span> <span data-ttu-id="62550-124">В файле архива нет структуры каталогов, так как **путь** указывает только имена файлов.</span><span class="sxs-lookup"><span data-stu-id="62550-124">There's no directory structure in the archive file because the **Path** only specifies file names.</span></span>

```powershell
$compress = @{
  Path = "C:\Reference\Draftdoc.docx", "C:\Reference\Images\*.vsd"
  CompressionLevel = "Fastest"
  DestinationPath = "C:\Archives\Draft.Zip"
}
Compress-Archive @compress
```

<span data-ttu-id="62550-125">Параметр **path** принимает определенные имена файлов и имена файлов с подстановочными знаками, `*.vsd` .</span><span class="sxs-lookup"><span data-stu-id="62550-125">The **Path** parameter accepts specific file names and file names with wildcards, `*.vsd`.</span></span> <span data-ttu-id="62550-126">**Путь** использует список с разделителями-запятыми для получения файлов из разных каталогов.</span><span class="sxs-lookup"><span data-stu-id="62550-126">The **Path** uses a comma-separated list to get files from different directories.</span></span> <span data-ttu-id="62550-127">Уровень сжатия **быстрее** всего используется для сокращения времени обработки.</span><span class="sxs-lookup"><span data-stu-id="62550-127">The compression level is **Fastest** to reduce processing time.</span></span> <span data-ttu-id="62550-128">Параметр **DestinationPath** задает расположение `Draft.zip` файла.</span><span class="sxs-lookup"><span data-stu-id="62550-128">The **DestinationPath** parameter specifies the location for the `Draft.zip` file.</span></span> <span data-ttu-id="62550-129">`Draft.zip`Файл содержит `Draftdoc.docx` и все файлы с `.vsd` расширением.</span><span class="sxs-lookup"><span data-stu-id="62550-129">The `Draft.zip` file contains `Draftdoc.docx` and all the files with a `.vsd` extension.</span></span>

### <span data-ttu-id="62550-130">Пример 2. сжатие файлов с помощью LiteralPath</span><span class="sxs-lookup"><span data-stu-id="62550-130">Example 2: Compress files using a LiteralPath</span></span>

<span data-ttu-id="62550-131">Этот пример сжимает определенные именованные файлы и создает новый файл архива.</span><span class="sxs-lookup"><span data-stu-id="62550-131">This example compresses specific named files and creates a new archive file.</span></span> <span data-ttu-id="62550-132">В файле архива нет структуры каталогов, так как **путь** указывает только имена файлов.</span><span class="sxs-lookup"><span data-stu-id="62550-132">There's no directory structure in the archive file because the **Path** only specifies file names.</span></span>

```powershell
$compress = @{
LiteralPath= "C:\Reference\Draft Doc.docx", "C:\Reference\Images\diagram2.vsd"
CompressionLevel = "Fastest"
DestinationPath = "C:\Archives\Draft.Zip"
}
Compress-Archive @compress
```

<span data-ttu-id="62550-133">Используется абсолютный путь и имена файлов, так как параметр **LiteralPath** не принимает подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="62550-133">Absolute path and file names are used because the **LiteralPath** parameter doesn't accept wildcards.</span></span> <span data-ttu-id="62550-134">**Путь** использует список с разделителями-запятыми для получения файлов из разных каталогов.</span><span class="sxs-lookup"><span data-stu-id="62550-134">The **Path** uses a comma-separated list to get files from different directories.</span></span> <span data-ttu-id="62550-135">Уровень сжатия **быстрее** всего используется для сокращения времени обработки.</span><span class="sxs-lookup"><span data-stu-id="62550-135">The compression level is **Fastest** to reduce processing time.</span></span> <span data-ttu-id="62550-136">Параметр **DestinationPath** задает расположение `Draft.zip` файла.</span><span class="sxs-lookup"><span data-stu-id="62550-136">The **DestinationPath** parameter specifies the location for the `Draft.zip` file.</span></span> <span data-ttu-id="62550-137">`Draft.zip`Файл содержит только `Draftdoc.docx` и `diagram2.vsd` .</span><span class="sxs-lookup"><span data-stu-id="62550-137">The `Draft.zip` file only contains `Draftdoc.docx` and `diagram2.vsd`.</span></span>

### <span data-ttu-id="62550-138">Пример 3. Сжатие каталога, содержащего корневой каталог</span><span class="sxs-lookup"><span data-stu-id="62550-138">Example 3: Compress a directory that includes the root directory</span></span>

<span data-ttu-id="62550-139">В этом примере сжимается каталог и создается файл архива, **содержащий** корневой каталог и все его файлы и подкаталоги.</span><span class="sxs-lookup"><span data-stu-id="62550-139">This example compresses a directory and creates an archive file that **includes** the root directory, and all its files and subdirectories.</span></span> <span data-ttu-id="62550-140">Файл архива имеет структуру каталогов, так как **путь** указывает корневой каталог.</span><span class="sxs-lookup"><span data-stu-id="62550-140">The archive file has a directory structure because the **Path** specifies a root directory.</span></span>

```powershell
Compress-Archive -Path C:\Reference -DestinationPath C:\Archives\Draft.zip
```

<span data-ttu-id="62550-141">`Compress-Archive` использует параметр **path** для указания корневого каталога `C:\Reference` .</span><span class="sxs-lookup"><span data-stu-id="62550-141">`Compress-Archive` uses the **Path** parameter to specify the root directory, `C:\Reference`.</span></span> <span data-ttu-id="62550-142">Параметр **DestinationPath** указывает расположение файла архива.</span><span class="sxs-lookup"><span data-stu-id="62550-142">The **DestinationPath** parameter specifies the location for the archive file.</span></span> <span data-ttu-id="62550-143">`Draft.zip`Архив включает `Reference` корневой каталог и все его файлы и подкаталоги.</span><span class="sxs-lookup"><span data-stu-id="62550-143">The `Draft.zip` archive includes the `Reference` root directory, and all its files and subdirectories.</span></span>

### <span data-ttu-id="62550-144">Пример 4. Сжатие каталога, который исключает корневой каталог</span><span class="sxs-lookup"><span data-stu-id="62550-144">Example 4: Compress a directory that excludes the root directory</span></span>

<span data-ttu-id="62550-145">В этом примере выполняется сжатие каталога и создается файл архива, который **исключает** корневой каталог, поскольку **путь** использует `*` подстановочный знак звездочки ().</span><span class="sxs-lookup"><span data-stu-id="62550-145">This example compresses a directory and creates an archive file that **excludes** the root directory because the **Path** uses an asterisk (`*`) wildcard.</span></span> <span data-ttu-id="62550-146">Архив содержит структуру каталогов, содержащую файлы и подкаталоги корневого каталога.</span><span class="sxs-lookup"><span data-stu-id="62550-146">The archive contains a directory structure that contains the root directory's files and subdirectories.</span></span>

```powershell
Compress-Archive -Path C:\Reference\* -DestinationPath C:\Archives\Draft.zip
```

<span data-ttu-id="62550-147">`Compress-Archive` использует параметр **path** для указания корневого каталога `C:\Reference` с `*` подстановочным знаком звездочки ().</span><span class="sxs-lookup"><span data-stu-id="62550-147">`Compress-Archive` uses the **Path** parameter to specify the root directory, `C:\Reference` with an asterisk (`*`) wildcard.</span></span> <span data-ttu-id="62550-148">Параметр **DestinationPath** указывает расположение файла архива.</span><span class="sxs-lookup"><span data-stu-id="62550-148">The **DestinationPath** parameter specifies the location for the archive file.</span></span> <span data-ttu-id="62550-149">`Draft.zip`Архив содержит файлы и подкаталоги корневого каталога.</span><span class="sxs-lookup"><span data-stu-id="62550-149">The `Draft.zip` archive contains the root directory's files and subdirectories.</span></span> <span data-ttu-id="62550-150">`Reference`Корневой каталог исключается из архива.</span><span class="sxs-lookup"><span data-stu-id="62550-150">The `Reference` root directory is excluded from the archive.</span></span>

### <span data-ttu-id="62550-151">Пример 5. сжатие только файлов в корневом каталоге</span><span class="sxs-lookup"><span data-stu-id="62550-151">Example 5: Compress only the files in a root directory</span></span>

<span data-ttu-id="62550-152">В этом примере выполняется сжатие только файлов в корневом каталоге и создание файла архива.</span><span class="sxs-lookup"><span data-stu-id="62550-152">This example compresses only the files in a root directory and creates an archive file.</span></span> <span data-ttu-id="62550-153">В архиве нет структуры каталогов, поскольку сжаты только файлы.</span><span class="sxs-lookup"><span data-stu-id="62550-153">There's no directory structure in the archive because only files are compressed.</span></span>

```powershell
Compress-Archive -Path C:\Reference\*.* -DestinationPath C:\Archives\Draft.zip
```

<span data-ttu-id="62550-154">`Compress-Archive` использует параметр **path** для указания корневого каталога `C:\Reference` с подстановочным знаком **"звезда-точка-звезда** " ( `*.*` ).</span><span class="sxs-lookup"><span data-stu-id="62550-154">`Compress-Archive` uses the **Path** parameter to specify the root directory, `C:\Reference` with a **star-dot-star** (`*.*`) wildcard.</span></span> <span data-ttu-id="62550-155">Параметр **DestinationPath** указывает расположение файла архива.</span><span class="sxs-lookup"><span data-stu-id="62550-155">The **DestinationPath** parameter specifies the location for the archive file.</span></span> <span data-ttu-id="62550-156">`Draft.zip`Архив содержит только `Reference` файлы корневого каталога, а корневой каталог исключается.</span><span class="sxs-lookup"><span data-stu-id="62550-156">The `Draft.zip` archive only contains the `Reference` root directory's files and the root directory is excluded.</span></span>

### <span data-ttu-id="62550-157">Пример 6. Использование конвейера для архивации файлов</span><span class="sxs-lookup"><span data-stu-id="62550-157">Example 6: Use the pipeline to archive files</span></span>

<span data-ttu-id="62550-158">В этом примере файлы посылаются по конвейеру для создания архива.</span><span class="sxs-lookup"><span data-stu-id="62550-158">This example sends files down the pipeline to create an archive.</span></span> <span data-ttu-id="62550-159">В файле архива нет структуры каталогов, так как **путь** указывает только имена файлов.</span><span class="sxs-lookup"><span data-stu-id="62550-159">There's no directory structure in the archive file because the **Path** only specifies file names.</span></span>

```powershell
Get-ChildItem -Path C:\Reference\Afile.txt, C:\Reference\Images\Bfile.txt |
  Compress-Archive -DestinationPath C:\Archives\PipelineFiles.zip
```

<span data-ttu-id="62550-160">`Get-ChildItem` использует параметр **path** для указания двух файлов из разных каталогов.</span><span class="sxs-lookup"><span data-stu-id="62550-160">`Get-ChildItem` uses the **Path** parameter to specify two files from different directories.</span></span> <span data-ttu-id="62550-161">Каждый файл представлен объектом **FileInfo** и отправляется по конвейеру в `Compress-Archive` .</span><span class="sxs-lookup"><span data-stu-id="62550-161">Each file is represented by a **FileInfo** object and is sent down the pipeline to `Compress-Archive`.</span></span>
<span data-ttu-id="62550-162">Два указанных файла архивируются в `PipelineFiles.zip` .</span><span class="sxs-lookup"><span data-stu-id="62550-162">The two specified files are archived in `PipelineFiles.zip`.</span></span>

### <span data-ttu-id="62550-163">Пример 7. Использование конвейера для архивации каталога</span><span class="sxs-lookup"><span data-stu-id="62550-163">Example 7: Use the pipeline to archive a directory</span></span>

<span data-ttu-id="62550-164">В этом примере каталог посылается по конвейеру для создания архива.</span><span class="sxs-lookup"><span data-stu-id="62550-164">This example sends a directory down the pipeline to create an archive.</span></span> <span data-ttu-id="62550-165">Файлы отправляются как объекты и каталоги **FileInfo** как объекты **DirectoryInfo** .</span><span class="sxs-lookup"><span data-stu-id="62550-165">Files are sent as **FileInfo** objects and directories as **DirectoryInfo** objects.</span></span> <span data-ttu-id="62550-166">Структура каталогов архива не включает корневой каталог, но его файлы и подкаталоги включены в архив.</span><span class="sxs-lookup"><span data-stu-id="62550-166">The archive's directory structure doesn't include the root directory, but its files and subdirectories are included in the archive.</span></span>

```powershell
Get-ChildItem -Path C:\LogFiles | Compress-Archive -DestinationPath C:\Archives\PipelineDir.zip
```

<span data-ttu-id="62550-167">`Get-ChildItem` использует параметр **path** для указания `C:\LogFiles` корневого каталога.</span><span class="sxs-lookup"><span data-stu-id="62550-167">`Get-ChildItem` uses the **Path** parameter to specify the `C:\LogFiles` root directory.</span></span> <span data-ttu-id="62550-168">Каждый объект **FileInfo** и **DirectoryInfo** отправляется по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="62550-168">Each **FileInfo** and **DirectoryInfo** object is sent down the pipeline.</span></span>

<span data-ttu-id="62550-169">`Compress-Archive` добавляет каждый объект в `PipelineDir.zip` Архив.</span><span class="sxs-lookup"><span data-stu-id="62550-169">`Compress-Archive` adds each object to the `PipelineDir.zip` archive.</span></span> <span data-ttu-id="62550-170">Параметр **пути** не указан, так как объекты конвейера получены в положении параметра 0.</span><span class="sxs-lookup"><span data-stu-id="62550-170">The **Path** parameter isn't specified because the pipeline objects are received into parameter position 0.</span></span>

### <span data-ttu-id="62550-171">Пример 8. как рекурсия может повлиять на архивы</span><span class="sxs-lookup"><span data-stu-id="62550-171">Example 8: How recursion can affect archives</span></span>

<span data-ttu-id="62550-172">В этом примере показано, как рекурсия может дублировать файлы в архиве.</span><span class="sxs-lookup"><span data-stu-id="62550-172">This example shows how recursion can duplicate files in your archive.</span></span> <span data-ttu-id="62550-173">Например, при использовании `Get-ChildItem` с параметром **рекурсии** .</span><span class="sxs-lookup"><span data-stu-id="62550-173">For example, if you use `Get-ChildItem` with the **Recurse** parameter.</span></span> <span data-ttu-id="62550-174">В качестве процессов рекурсии каждый объект **FileInfo** и **DirectoryInfo** отсылается по конвейеру и добавляется в архив.</span><span class="sxs-lookup"><span data-stu-id="62550-174">As recursion processes, each **FileInfo** and **DirectoryInfo** object is sent down the pipeline and added to the archive.</span></span>

```powershell
Get-ChildItem -Path C:\TestLog -Recurse |
  Compress-Archive -DestinationPath C:\Archives\PipelineRecurse.zip
```

<span data-ttu-id="62550-175">`C:\TestLog`Каталог не содержит файлов.</span><span class="sxs-lookup"><span data-stu-id="62550-175">The `C:\TestLog` directory doesn't contain any files.</span></span> <span data-ttu-id="62550-176">Он содержит подкаталог с именем `testsub` , содержащий `testlog.txt` файл.</span><span class="sxs-lookup"><span data-stu-id="62550-176">It does contain a subdirectory named `testsub` that contains the `testlog.txt` file.</span></span>

<span data-ttu-id="62550-177">`Get-ChildItem` использует параметр **path** для указания корневого каталога `C:\TestLog` .</span><span class="sxs-lookup"><span data-stu-id="62550-177">`Get-ChildItem` uses the **Path** parameter to specify the root directory, `C:\TestLog`.</span></span> <span data-ttu-id="62550-178">**Рекурсивный** параметр обрабатывает файлы и каталоги.</span><span class="sxs-lookup"><span data-stu-id="62550-178">The **Recurse** parameter processes the files and directories.</span></span> <span data-ttu-id="62550-179">Создается объект **DirectoryInfo** для `testsub` и объекта **FileInfo** `testlog.txt` .</span><span class="sxs-lookup"><span data-stu-id="62550-179">A **DirectoryInfo** object is created for `testsub` and a **FileInfo** object `testlog.txt`.</span></span>

<span data-ttu-id="62550-180">Каждый объект отправляется по конвейеру в `Compress-Archive` .</span><span class="sxs-lookup"><span data-stu-id="62550-180">Each object is sent down the pipeline to `Compress-Archive`.</span></span> <span data-ttu-id="62550-181">**DestinationPath** указывает расположение файла архива.</span><span class="sxs-lookup"><span data-stu-id="62550-181">The **DestinationPath** specifies the location for the archive file.</span></span> <span data-ttu-id="62550-182">Параметр **пути** не указан, так как объекты конвейера получены в положении параметра 0.</span><span class="sxs-lookup"><span data-stu-id="62550-182">The **Path** parameter isn't specified because the pipeline objects are received into parameter position 0.</span></span>

<span data-ttu-id="62550-183">Следующая сводка описывает `PipelineRecurse.zip` содержимое архива, которое содержит дубликат файла:</span><span class="sxs-lookup"><span data-stu-id="62550-183">The following summary describes the `PipelineRecurse.zip` archive's contents that contains a duplicate file:</span></span>

- <span data-ttu-id="62550-184">Объект **DirectoryInfo** создает `testsub` каталог и содержит `testlog.txt` файл, который отражает исходную структуру каталогов.</span><span class="sxs-lookup"><span data-stu-id="62550-184">The **DirectoryInfo** object creates the `testsub` directory and contains the `testlog.txt` file, which reflects the original directory structure.</span></span>
- <span data-ttu-id="62550-185">Объект **FileInfo** создает дубликат `testlog.txt` в корне архива.</span><span class="sxs-lookup"><span data-stu-id="62550-185">The **FileInfo** object creates a duplicate `testlog.txt` in the archive's root.</span></span> <span data-ttu-id="62550-186">Создается повторяющийся файл, так как рекурсия отправляет объект File в `Compress-Archive` .</span><span class="sxs-lookup"><span data-stu-id="62550-186">The duplicate file is created because recursion sent a file object to `Compress-Archive`.</span></span> <span data-ttu-id="62550-187">Это ожидаемое поведение, поскольку каждый объект, отправленный по конвейеру, добавляется в архив.</span><span class="sxs-lookup"><span data-stu-id="62550-187">This behavior is expected because each object sent down the pipeline is added to the archive.</span></span>

### <span data-ttu-id="62550-188">Пример 9. Обновление существующего файла архива</span><span class="sxs-lookup"><span data-stu-id="62550-188">Example 9: Update an existing archive file</span></span>

<span data-ttu-id="62550-189">В этом примере выполняется обновление существующего файла архива `Draft.Zip` в `C:\Archives` каталоге.</span><span class="sxs-lookup"><span data-stu-id="62550-189">This example updates an existing archive file, `Draft.Zip`, in the `C:\Archives` directory.</span></span> <span data-ttu-id="62550-190">В этом примере существующий файл архива содержит корневой каталог, а также его файлы и подкаталоги.</span><span class="sxs-lookup"><span data-stu-id="62550-190">In this example, the existing archive file contains the root directory, and its files and subdirectories.</span></span>

```powershell
Compress-Archive -Path C:\Reference -Update -DestinationPath C:\Archives\Draft.Zip
```

<span data-ttu-id="62550-191">Команда обновляется `Draft.Zip` с использованием более новых версий существующих файлов в `C:\Reference` каталоге и его подкаталогах.</span><span class="sxs-lookup"><span data-stu-id="62550-191">The command updates `Draft.Zip` with newer versions of existing files in the `C:\Reference` directory and its subdirectories.</span></span> <span data-ttu-id="62550-192">Новые файлы, добавленные в `C:\Reference` или его подкаталоги, включаются в обновленный `Draft.Zip` Архив.</span><span class="sxs-lookup"><span data-stu-id="62550-192">And, new files that were added to `C:\Reference` or its subdirectories are included in the updated `Draft.Zip` archive.</span></span>

## <span data-ttu-id="62550-193">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="62550-193">PARAMETERS</span></span>

### <span data-ttu-id="62550-194">-CompressionLevel</span><span class="sxs-lookup"><span data-stu-id="62550-194">-CompressionLevel</span></span>

<span data-ttu-id="62550-195">Задает степень сжатия, применяемого при создании файла архива.</span><span class="sxs-lookup"><span data-stu-id="62550-195">Specifies how much compression to apply when you're creating the archive file.</span></span> <span data-ttu-id="62550-196">Более быстрое сжатие требует меньше времени на создание файла, но может привести к увеличению размеров файлов.</span><span class="sxs-lookup"><span data-stu-id="62550-196">Faster compression requires less time to create the file, but can result in larger file sizes.</span></span>

<span data-ttu-id="62550-197">Если этот параметр не указан, команда использует значение по умолчанию — **оптимальный**.</span><span class="sxs-lookup"><span data-stu-id="62550-197">If this parameter isn't specified, the command uses the default value, **Optimal**.</span></span>

<span data-ttu-id="62550-198">Ниже приведены допустимые значения для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="62550-198">The following are the acceptable values for this parameter:</span></span>

- <span data-ttu-id="62550-199">**Самый быстрый**.</span><span class="sxs-lookup"><span data-stu-id="62550-199">**Fastest**.</span></span> <span data-ttu-id="62550-200">Используйте самый быстрый метод сжатия, чтобы сократить время обработки.</span><span class="sxs-lookup"><span data-stu-id="62550-200">Use the fastest compression method available to reduce processing time.</span></span> <span data-ttu-id="62550-201">Более быстрое сжатие может привести к увеличению размеров файлов.</span><span class="sxs-lookup"><span data-stu-id="62550-201">Faster compression can result in larger file sizes.</span></span>
- <span data-ttu-id="62550-202">**Несжатие**.</span><span class="sxs-lookup"><span data-stu-id="62550-202">**NoCompression**.</span></span> <span data-ttu-id="62550-203">Не сжимает исходные файлы.</span><span class="sxs-lookup"><span data-stu-id="62550-203">Doesn't compress the source files.</span></span>
- <span data-ttu-id="62550-204">**Оптимальный**.</span><span class="sxs-lookup"><span data-stu-id="62550-204">**Optimal**.</span></span> <span data-ttu-id="62550-205">Время обработки зависит от размера файла.</span><span class="sxs-lookup"><span data-stu-id="62550-205">Processing time is dependent on file size.</span></span>

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

### <span data-ttu-id="62550-206">-Confirm</span><span class="sxs-lookup"><span data-stu-id="62550-206">-Confirm</span></span>

<span data-ttu-id="62550-207">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="62550-207">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="62550-208">-DestinationPath</span><span class="sxs-lookup"><span data-stu-id="62550-208">-DestinationPath</span></span>

<span data-ttu-id="62550-209">Этот параметр является обязательным и указывает путь к выходному файлу архива.</span><span class="sxs-lookup"><span data-stu-id="62550-209">This parameter is required and specifies the path to the archive output file.</span></span> <span data-ttu-id="62550-210">**DestinationPath** должен включать имя ZIP-файла, а также абсолютный или относительный путь к ZIP-файлу.</span><span class="sxs-lookup"><span data-stu-id="62550-210">The **DestinationPath** should include the name of the zipped file, and either the absolute or relative path to the zipped file.</span></span>

<span data-ttu-id="62550-211">Если имя файла в **DestinationPath** не имеет `.zip` расширения имени файла, командлет добавляет `.zip` расширение имени файла.</span><span class="sxs-lookup"><span data-stu-id="62550-211">If the file name in **DestinationPath** doesn't have a `.zip` file name extension, the cmdlet adds the `.zip` file name extension.</span></span>

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

### <span data-ttu-id="62550-212">-Force</span><span class="sxs-lookup"><span data-stu-id="62550-212">-Force</span></span>

<span data-ttu-id="62550-213">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="62550-213">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="62550-214">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="62550-214">-LiteralPath</span></span>

<span data-ttu-id="62550-215">Указывает путь или пути к файлам, которые необходимо добавить в архивный zip-файл.</span><span class="sxs-lookup"><span data-stu-id="62550-215">Specifies the path or paths to the files that you want to add to the archive zipped file.</span></span> <span data-ttu-id="62550-216">В отличие от параметра **path** , значение **LiteralPath** используется точно так же, как типизировано.</span><span class="sxs-lookup"><span data-stu-id="62550-216">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="62550-217">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="62550-217">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="62550-218">Если путь содержит escape-символы, заключите каждый escape-символ в одинарные кавычки, чтобы заставить PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="62550-218">If the path includes escape characters, enclose each escape character in single quotation marks, to instruct PowerShell not to interpret any characters as escape sequences.</span></span>
<span data-ttu-id="62550-219">Чтобы указать несколько путей и включить файлы в несколько расположений в выходном ZIP-файле, используйте запятые для разделения путей.</span><span class="sxs-lookup"><span data-stu-id="62550-219">To specify multiple paths, and include files in multiple locations in your output zipped file, use commas to separate the paths.</span></span>

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

### <span data-ttu-id="62550-220">-PassThru</span><span class="sxs-lookup"><span data-stu-id="62550-220">-PassThru</span></span>

<span data-ttu-id="62550-221">Заставляет командлет вывести объект File, представляющий созданный файл архива.</span><span class="sxs-lookup"><span data-stu-id="62550-221">Causes the cmdlet to output a file object representing the archive file created.</span></span>

<span data-ttu-id="62550-222">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="62550-222">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="62550-223">-Path</span><span class="sxs-lookup"><span data-stu-id="62550-223">-Path</span></span>

<span data-ttu-id="62550-224">Указывает путь или пути к файлам, которые необходимо добавить в архивный zip-файл.</span><span class="sxs-lookup"><span data-stu-id="62550-224">Specifies the path or paths to the files that you want to add to the archive zipped file.</span></span> <span data-ttu-id="62550-225">Чтобы указать несколько путей и включить файлы в нескольких местах, используйте запятые для разделения путей.</span><span class="sxs-lookup"><span data-stu-id="62550-225">To specify multiple paths, and include files in multiple locations, use commas to separate the paths.</span></span>

<span data-ttu-id="62550-226">Этот параметр принимает подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="62550-226">This parameter accepts wildcard characters.</span></span> <span data-ttu-id="62550-227">Подстановочные знаки позволяют добавлять все файлы в каталоге в файл архива.</span><span class="sxs-lookup"><span data-stu-id="62550-227">Wildcard characters allow you to add all files in a directory to your archive file.</span></span>

<span data-ttu-id="62550-228">Использование подстановочных знаков с корневым каталогом влияет на содержимое архива:</span><span class="sxs-lookup"><span data-stu-id="62550-228">Using wildcards with a root directory affects the archive's contents:</span></span>

- <span data-ttu-id="62550-229">Чтобы создать архив, **включающий** корневой каталог и все его файлы и подкаталоги, укажите корневой каталог в **пути** без подстановочных знаков.</span><span class="sxs-lookup"><span data-stu-id="62550-229">To create an archive that **includes** the root directory, and all its files and subdirectories, specify the root directory in the **Path** without wildcards.</span></span> <span data-ttu-id="62550-230">Пример: `-Path C:\Reference`</span><span class="sxs-lookup"><span data-stu-id="62550-230">For example: `-Path C:\Reference`</span></span>
- <span data-ttu-id="62550-231">Чтобы создать архив, **исключающий** корневой каталог, но zips все его файлы и подкаталоги, используйте подстановочный знак "звездочка" ( `*` ).</span><span class="sxs-lookup"><span data-stu-id="62550-231">To create an archive that **excludes** the root directory, but zips all its files and subdirectories, use the asterisk (`*`) wildcard.</span></span> <span data-ttu-id="62550-232">Пример: `-Path C:\Reference\*`</span><span class="sxs-lookup"><span data-stu-id="62550-232">For example: `-Path C:\Reference\*`</span></span>
- <span data-ttu-id="62550-233">Чтобы создать архив, zips только файлы в корневом каталоге, используйте подстановочный знак **"звезда-точка-звезда** " ( `*.*` ).</span><span class="sxs-lookup"><span data-stu-id="62550-233">To create an archive that only zips the files in the root directory, use the **star-dot-star** (`*.*`) wildcard.</span></span> <span data-ttu-id="62550-234">Подкаталоги корневого каталога не включаются в архив.</span><span class="sxs-lookup"><span data-stu-id="62550-234">Subdirectories of the root aren't included in the archive.</span></span> <span data-ttu-id="62550-235">Пример: `-Path C:\Reference\*.*`</span><span class="sxs-lookup"><span data-stu-id="62550-235">For example: `-Path C:\Reference\*.*`</span></span>

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

### <span data-ttu-id="62550-236">— Обновление</span><span class="sxs-lookup"><span data-stu-id="62550-236">-Update</span></span>

<span data-ttu-id="62550-237">Обновляет указанный архив, заменяя старые версии файлов в архиве более новыми версиями с теми же именами.</span><span class="sxs-lookup"><span data-stu-id="62550-237">Updates the specified archive by replacing older file versions in the archive with newer file versions that have the same names.</span></span> <span data-ttu-id="62550-238">Можно также добавить этот параметр, чтобы добавить файлы в существующий архив.</span><span class="sxs-lookup"><span data-stu-id="62550-238">You can also add this parameter to add files to an existing archive.</span></span>

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

### <span data-ttu-id="62550-239">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="62550-239">-WhatIf</span></span>

<span data-ttu-id="62550-240">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="62550-240">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="62550-241">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="62550-241">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="62550-242">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="62550-242">CommonParameters</span></span>

<span data-ttu-id="62550-243">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="62550-243">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="62550-244">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="62550-244">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="62550-245">Входные данные</span><span class="sxs-lookup"><span data-stu-id="62550-245">INPUTS</span></span>

### <span data-ttu-id="62550-246">System.String</span><span class="sxs-lookup"><span data-stu-id="62550-246">System.String</span></span>

<span data-ttu-id="62550-247">Строку, содержащую путь, можно передать в один или несколько файлов.</span><span class="sxs-lookup"><span data-stu-id="62550-247">You can pipe a string that contains a path to one or more files.</span></span>

## <span data-ttu-id="62550-248">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="62550-248">OUTPUTS</span></span>

### <span data-ttu-id="62550-249">System. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="62550-249">System.IO.FileInfo</span></span>

<span data-ttu-id="62550-250">Командлет возвращает объект **FileInfo** только при использовании параметра **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="62550-250">The cmdlet only returns a **FileInfo** object when you use the **PassThru** parameter.</span></span>

## <span data-ttu-id="62550-251">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="62550-251">NOTES</span></span>

<span data-ttu-id="62550-252">Использование рекурсии и отправка объектов вниз по конвейеру могут дублировать файлы в архиве.</span><span class="sxs-lookup"><span data-stu-id="62550-252">Using recursion and sending objects down the pipeline can duplicate files in your archive.</span></span> <span data-ttu-id="62550-253">Например, при использовании `Get-ChildItem` с параметром **рекурсии** каждый объект **FileInfo** и **DirectoryInfo** , отправленный по конвейеру, добавляется в архив.</span><span class="sxs-lookup"><span data-stu-id="62550-253">For example, if you use `Get-ChildItem` with the **Recurse** parameter, each **FileInfo** and **DirectoryInfo** object that's sent down the pipeline is added to the archive.</span></span>

<span data-ttu-id="62550-254">В [спецификации ZIP-файла](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) не указан стандартный способ кодирования имен файлов, содержащих символы, не входящие в набор ASCII.</span><span class="sxs-lookup"><span data-stu-id="62550-254">The [ZIP file specification](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) does not specify a standard way of encoding filenames that contain non-ASCII characters.</span></span> <span data-ttu-id="62550-255">`Compress-Archive`Командлет использует кодировку UTF-8.</span><span class="sxs-lookup"><span data-stu-id="62550-255">The `Compress-Archive` cmdlet uses UTF-8 encoding.</span></span> <span data-ttu-id="62550-256">Другие средства архивирования ZIP могут использовать другую схему кодирования.</span><span class="sxs-lookup"><span data-stu-id="62550-256">Other ZIP archive tools may use a different encoding scheme.</span></span> <span data-ttu-id="62550-257">При извлечении файлов с именами, которые не хранятся в кодировке UTF-8, `Expand-Archive` использует необработанное значение, найденное в архиве.</span><span class="sxs-lookup"><span data-stu-id="62550-257">When extracting files with filenames not stored using UTF-8 encoding, `Expand-Archive` uses the raw value found in the archive.</span></span> <span data-ttu-id="62550-258">Это может привести к тому, что имя файла будет отличаться от исходного имени файла, хранящегося в архиве.</span><span class="sxs-lookup"><span data-stu-id="62550-258">This can result in a filename that is different than the source filename stored in the archive.</span></span>

## <span data-ttu-id="62550-259">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="62550-259">RELATED LINKS</span></span>

[<span data-ttu-id="62550-260">Expand-Archive</span><span class="sxs-lookup"><span data-stu-id="62550-260">Expand-Archive</span></span>](Expand-Archive.md)

[<span data-ttu-id="62550-261">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="62550-261">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)

