---
external help file: Microsoft.PowerShell.Archive-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Archive
ms.date: 07/17/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.archive/expand-archive?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Expand-Archive
ms.openlocfilehash: 6b89512ebc786a47ae47dd2cd8f51cb532382e02
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "93229701"
---
# <span data-ttu-id="85627-103">Expand-Archive</span><span class="sxs-lookup"><span data-stu-id="85627-103">Expand-Archive</span></span>

## <span data-ttu-id="85627-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="85627-104">SYNOPSIS</span></span>
<span data-ttu-id="85627-105">Извлекает файлы из указанного ZIP-файла архива.</span><span class="sxs-lookup"><span data-stu-id="85627-105">Extracts files from a specified archive (zipped) file.</span></span>

## <span data-ttu-id="85627-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="85627-106">SYNTAX</span></span>

### <span data-ttu-id="85627-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="85627-107">Path (Default)</span></span>

```
Expand-Archive [-Path] <String> [[-DestinationPath] <String>] [-Force] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="85627-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="85627-108">LiteralPath</span></span>

```
Expand-Archive -LiteralPath <String> [[-DestinationPath] <String>] [-Force] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="85627-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="85627-109">DESCRIPTION</span></span>

<span data-ttu-id="85627-110">`Expand-Archive`Командлет извлекает файлы из указанного ZIP-файла архива в указанную папку назначения.</span><span class="sxs-lookup"><span data-stu-id="85627-110">The `Expand-Archive` cmdlet extracts files from a specified zipped archive file to a specified destination folder.</span></span> <span data-ttu-id="85627-111">Файл архива позволяет упаковать и при необходимости сжать несколько файлов в один сжатый ZIP-файл для упрощения распространения и хранения.</span><span class="sxs-lookup"><span data-stu-id="85627-111">An archive file allows multiple files to be packaged, and optionally compressed, into a single zipped file for easier distribution and storage.</span></span>

## <span data-ttu-id="85627-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="85627-112">EXAMPLES</span></span>

### <span data-ttu-id="85627-113">Пример 1. Извлечение содержимого архива</span><span class="sxs-lookup"><span data-stu-id="85627-113">Example 1: Extract the contents of an archive</span></span>

<span data-ttu-id="85627-114">В этом примере содержимое существующего файла архива извлекается в папку, указанную параметром **DestinationPath** .</span><span class="sxs-lookup"><span data-stu-id="85627-114">This example extracts the contents of an existing archive file into the folder specified by the **DestinationPath** parameter.</span></span>

```powershell
Expand-Archive -LiteralPath 'C:\Archives\Draft[v1].Zip' -DestinationPath C:\Reference
```

<span data-ttu-id="85627-115">В этом примере используется параметр **LiteralPath** , так как имя файла содержит символы, которые можно интерпретировать как подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="85627-115">In this example, the **LiteralPath** parameter is used because the filename contains characters that could be interpreted as wildcards.</span></span>

### <span data-ttu-id="85627-116">Пример 2. Извлечение содержимого архива в текущей папке</span><span class="sxs-lookup"><span data-stu-id="85627-116">Example 2: Extract the contents of an archive in the current folder</span></span>

<span data-ttu-id="85627-117">Этот пример извлекает содержимое существующего файла архива в текущей папке в папку, указанную параметром **DestinationPath** .</span><span class="sxs-lookup"><span data-stu-id="85627-117">This example extracts the contents of an existing archive file in the current folder into the folder specified by the **DestinationPath** parameter.</span></span>

```powershell
Expand-Archive -Path Draftv2.Zip -DestinationPath C:\Reference
```

## <span data-ttu-id="85627-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="85627-118">PARAMETERS</span></span>

### <span data-ttu-id="85627-119">-DestinationPath</span><span class="sxs-lookup"><span data-stu-id="85627-119">-DestinationPath</span></span>

<span data-ttu-id="85627-120">По умолчанию `Expand-Archive` создает папку в текущем расположении с тем же именем, что и у ZIP-файла.</span><span class="sxs-lookup"><span data-stu-id="85627-120">By default, `Expand-Archive` creates a folder in the current location that is the same name as the ZIP file.</span></span> <span data-ttu-id="85627-121">Параметр позволяет указать путь к другой папке.</span><span class="sxs-lookup"><span data-stu-id="85627-121">The parameter allows you to specify the path to a different folder.</span></span> <span data-ttu-id="85627-122">Если целевая папка не существует, она будет создана.</span><span class="sxs-lookup"><span data-stu-id="85627-122">The target folder is created if it does not exist.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: A folder in the current location
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85627-123">-Force</span><span class="sxs-lookup"><span data-stu-id="85627-123">-Force</span></span>

<span data-ttu-id="85627-124">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="85627-124">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="85627-125">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="85627-125">-LiteralPath</span></span>

<span data-ttu-id="85627-126">Определяет путь к файлу архива.</span><span class="sxs-lookup"><span data-stu-id="85627-126">Specifies the path to an archive file.</span></span> <span data-ttu-id="85627-127">В отличие от параметра **Path** , значение **LiteralPath** используется именно так, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="85627-127">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="85627-128">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="85627-128">Wildcard characters are not supported.</span></span> <span data-ttu-id="85627-129">Если путь содержит escape-символы, заключите каждый escape-символ в одинарные кавычки, чтобы заставить PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="85627-129">If the path includes escape characters, enclose each escape character in single quotation marks, to instruct PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="85627-130">-PassThru</span><span class="sxs-lookup"><span data-stu-id="85627-130">-PassThru</span></span>

<span data-ttu-id="85627-131">Предписывает командлету выводить список файлов, развернутых из архива.</span><span class="sxs-lookup"><span data-stu-id="85627-131">Causes the cmdlet to output a list of the files expanded from the archive.</span></span>

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

### <span data-ttu-id="85627-132">-Path</span><span class="sxs-lookup"><span data-stu-id="85627-132">-Path</span></span>

<span data-ttu-id="85627-133">Указывает путь к файлу архива.</span><span class="sxs-lookup"><span data-stu-id="85627-133">Specifies the path to the archive file.</span></span>

```yaml
Type: System.String
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="85627-134">-Confirm</span><span class="sxs-lookup"><span data-stu-id="85627-134">-Confirm</span></span>

<span data-ttu-id="85627-135">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="85627-135">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="85627-136">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="85627-136">-WhatIf</span></span>

<span data-ttu-id="85627-137">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="85627-137">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="85627-138">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="85627-138">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="85627-139">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="85627-139">CommonParameters</span></span>
<span data-ttu-id="85627-140">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="85627-140">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="85627-141">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="85627-141">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="85627-142">Входные данные</span><span class="sxs-lookup"><span data-stu-id="85627-142">INPUTS</span></span>

### <span data-ttu-id="85627-143">System.String</span><span class="sxs-lookup"><span data-stu-id="85627-143">System.String</span></span>

<span data-ttu-id="85627-144">Строку, содержащую путь, можно передать по конвейеру в существующий файл архива.</span><span class="sxs-lookup"><span data-stu-id="85627-144">You can pipe a string that contains a path to an existing archive file.</span></span>

## <span data-ttu-id="85627-145">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="85627-145">OUTPUTS</span></span>

### <span data-ttu-id="85627-146">System. IO. Филесистеминфо</span><span class="sxs-lookup"><span data-stu-id="85627-146">System.IO.FileSystemInfo</span></span>

<span data-ttu-id="85627-147">При `-PassThru` использовании параметра командлет выводит список файлов, которые были развернуты из архива.</span><span class="sxs-lookup"><span data-stu-id="85627-147">When the `-PassThru` parameter is used, the cmdlet outputs a list of files that were expanded from the archive.</span></span>

## <span data-ttu-id="85627-148">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="85627-148">NOTES</span></span>

<span data-ttu-id="85627-149">В [спецификации ZIP-файла](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) не указан стандартный способ кодирования имен файлов, содержащих символы, не входящие в набор ASCII.</span><span class="sxs-lookup"><span data-stu-id="85627-149">The [ZIP file specification](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) does not specify a standard way of encoding filenames that contain non-ASCII characters.</span></span> <span data-ttu-id="85627-150">`Compress-Archive`Командлет использует кодировку UTF-8.</span><span class="sxs-lookup"><span data-stu-id="85627-150">The `Compress-Archive` cmdlet uses UTF-8 encoding.</span></span> <span data-ttu-id="85627-151">Другие средства архивирования ZIP могут использовать другую схему кодирования.</span><span class="sxs-lookup"><span data-stu-id="85627-151">Other ZIP archive tools may use a different encoding scheme.</span></span> <span data-ttu-id="85627-152">При извлечении файлов с именами, которые не хранятся в кодировке UTF-8, `Expand-Archive` использует необработанное значение, найденное в архиве.</span><span class="sxs-lookup"><span data-stu-id="85627-152">When extracting files with filenames not stored using UTF-8 encoding, `Expand-Archive` uses the raw value found in the archive.</span></span> <span data-ttu-id="85627-153">Это может привести к тому, что имя файла будет отличаться от исходного имени файла, хранящегося в архиве.</span><span class="sxs-lookup"><span data-stu-id="85627-153">This can result in a filename that is different than the source filename stored in the archive.</span></span>

## <span data-ttu-id="85627-154">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="85627-154">RELATED LINKS</span></span>

[<span data-ttu-id="85627-155">Compress-Archive</span><span class="sxs-lookup"><span data-stu-id="85627-155">Compress-Archive</span></span>](compress-archive.md)
