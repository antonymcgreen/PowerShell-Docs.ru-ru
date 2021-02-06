---
external help file: Microsoft.PowerShell.Archive-help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Archive
ms.date: 07/17/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.archive/expand-archive?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Expand-Archive
ms.openlocfilehash: a4cf8970156f524578f7c9747aef1ffbf9f3eb58
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605061"
---
# <span data-ttu-id="1d833-102">Expand-Archive</span><span class="sxs-lookup"><span data-stu-id="1d833-102">Expand-Archive</span></span>

## <span data-ttu-id="1d833-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="1d833-103">SYNOPSIS</span></span>
<span data-ttu-id="1d833-104">Извлекает файлы из указанного ZIP-файла архива.</span><span class="sxs-lookup"><span data-stu-id="1d833-104">Extracts files from a specified archive (zipped) file.</span></span>

## <span data-ttu-id="1d833-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1d833-105">SYNTAX</span></span>

### <span data-ttu-id="1d833-106">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="1d833-106">Path (Default)</span></span>

```
Expand-Archive [-Path] <String> [[-DestinationPath] <String>] [-Force] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="1d833-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="1d833-107">LiteralPath</span></span>

```
Expand-Archive -LiteralPath <String> [[-DestinationPath] <String>] [-Force] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="1d833-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1d833-108">DESCRIPTION</span></span>

<span data-ttu-id="1d833-109">`Expand-Archive`Командлет извлекает файлы из указанного ZIP-файла архива в указанную папку назначения.</span><span class="sxs-lookup"><span data-stu-id="1d833-109">The `Expand-Archive` cmdlet extracts files from a specified zipped archive file to a specified destination folder.</span></span> <span data-ttu-id="1d833-110">Файл архива позволяет упаковать и при необходимости сжать несколько файлов в один сжатый ZIP-файл для упрощения распространения и хранения.</span><span class="sxs-lookup"><span data-stu-id="1d833-110">An archive file allows multiple files to be packaged, and optionally compressed, into a single zipped file for easier distribution and storage.</span></span>

## <span data-ttu-id="1d833-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="1d833-111">EXAMPLES</span></span>

### <span data-ttu-id="1d833-112">Пример 1. Извлечение содержимого архива</span><span class="sxs-lookup"><span data-stu-id="1d833-112">Example 1: Extract the contents of an archive</span></span>

<span data-ttu-id="1d833-113">В этом примере содержимое существующего файла архива извлекается в папку, указанную параметром **DestinationPath** .</span><span class="sxs-lookup"><span data-stu-id="1d833-113">This example extracts the contents of an existing archive file into the folder specified by the **DestinationPath** parameter.</span></span>

```powershell
Expand-Archive -LiteralPath 'C:\Archives\Draft[v1].Zip' -DestinationPath C:\Reference
```

<span data-ttu-id="1d833-114">В этом примере используется параметр **LiteralPath** , так как имя файла содержит символы, которые можно интерпретировать как подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="1d833-114">In this example, the **LiteralPath** parameter is used because the filename contains characters that could be interpreted as wildcards.</span></span>

### <span data-ttu-id="1d833-115">Пример 2. Извлечение содержимого архива в текущей папке</span><span class="sxs-lookup"><span data-stu-id="1d833-115">Example 2: Extract the contents of an archive in the current folder</span></span>

<span data-ttu-id="1d833-116">Этот пример извлекает содержимое существующего файла архива в текущей папке в папку, указанную параметром **DestinationPath** .</span><span class="sxs-lookup"><span data-stu-id="1d833-116">This example extracts the contents of an existing archive file in the current folder into the folder specified by the **DestinationPath** parameter.</span></span>

```powershell
Expand-Archive -Path Draftv2.Zip -DestinationPath C:\Reference
```

## <span data-ttu-id="1d833-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1d833-117">PARAMETERS</span></span>

### <span data-ttu-id="1d833-118">-DestinationPath</span><span class="sxs-lookup"><span data-stu-id="1d833-118">-DestinationPath</span></span>

<span data-ttu-id="1d833-119">По умолчанию `Expand-Archive` создает папку в текущем расположении с тем же именем, что и у ZIP-файла.</span><span class="sxs-lookup"><span data-stu-id="1d833-119">By default, `Expand-Archive` creates a folder in the current location that is the same name as the ZIP file.</span></span> <span data-ttu-id="1d833-120">Параметр позволяет указать путь к другой папке.</span><span class="sxs-lookup"><span data-stu-id="1d833-120">The parameter allows you to specify the path to a different folder.</span></span> <span data-ttu-id="1d833-121">Если целевая папка не существует, она будет создана.</span><span class="sxs-lookup"><span data-stu-id="1d833-121">The target folder is created if it does not exist.</span></span>

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

### <span data-ttu-id="1d833-122">-Force</span><span class="sxs-lookup"><span data-stu-id="1d833-122">-Force</span></span>

<span data-ttu-id="1d833-123">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="1d833-123">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="1d833-124">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="1d833-124">-LiteralPath</span></span>

<span data-ttu-id="1d833-125">Определяет путь к файлу архива.</span><span class="sxs-lookup"><span data-stu-id="1d833-125">Specifies the path to an archive file.</span></span> <span data-ttu-id="1d833-126">В отличие от параметра **Path**, значение **LiteralPath** используется именно так, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="1d833-126">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="1d833-127">Подстановочные знаки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="1d833-127">Wildcard characters are not supported.</span></span> <span data-ttu-id="1d833-128">Если путь содержит escape-символы, заключите каждый escape-символ в одинарные кавычки, чтобы заставить PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="1d833-128">If the path includes escape characters, enclose each escape character in single quotation marks, to instruct PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="1d833-129">-PassThru</span><span class="sxs-lookup"><span data-stu-id="1d833-129">-PassThru</span></span>

<span data-ttu-id="1d833-130">Предписывает командлету выводить список файлов, развернутых из архива.</span><span class="sxs-lookup"><span data-stu-id="1d833-130">Causes the cmdlet to output a list of the files expanded from the archive.</span></span>

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

### <span data-ttu-id="1d833-131">-Path</span><span class="sxs-lookup"><span data-stu-id="1d833-131">-Path</span></span>

<span data-ttu-id="1d833-132">Указывает путь к файлу архива.</span><span class="sxs-lookup"><span data-stu-id="1d833-132">Specifies the path to the archive file.</span></span>

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

### <span data-ttu-id="1d833-133">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1d833-133">-Confirm</span></span>

<span data-ttu-id="1d833-134">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="1d833-134">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="1d833-135">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1d833-135">-WhatIf</span></span>

<span data-ttu-id="1d833-136">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="1d833-136">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="1d833-137">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="1d833-137">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="1d833-138">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="1d833-138">CommonParameters</span></span>
<span data-ttu-id="1d833-139">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1d833-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1d833-140">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1d833-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1d833-141">Входные данные</span><span class="sxs-lookup"><span data-stu-id="1d833-141">INPUTS</span></span>

### <span data-ttu-id="1d833-142">System.String</span><span class="sxs-lookup"><span data-stu-id="1d833-142">System.String</span></span>

<span data-ttu-id="1d833-143">Строку, содержащую путь, можно передать по конвейеру в существующий файл архива.</span><span class="sxs-lookup"><span data-stu-id="1d833-143">You can pipe a string that contains a path to an existing archive file.</span></span>

## <span data-ttu-id="1d833-144">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1d833-144">OUTPUTS</span></span>

### <span data-ttu-id="1d833-145">System. IO. Филесистеминфо</span><span class="sxs-lookup"><span data-stu-id="1d833-145">System.IO.FileSystemInfo</span></span>

<span data-ttu-id="1d833-146">При `-PassThru` использовании параметра командлет выводит список файлов, которые были развернуты из архива.</span><span class="sxs-lookup"><span data-stu-id="1d833-146">When the `-PassThru` parameter is used, the cmdlet outputs a list of files that were expanded from the archive.</span></span>

## <span data-ttu-id="1d833-147">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="1d833-147">NOTES</span></span>

<span data-ttu-id="1d833-148">В [спецификации ZIP-файла](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) не указан стандартный способ кодирования имен файлов, содержащих символы, не входящие в набор ASCII.</span><span class="sxs-lookup"><span data-stu-id="1d833-148">The [ZIP file specification](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) does not specify a standard way of encoding filenames that contain non-ASCII characters.</span></span> <span data-ttu-id="1d833-149">`Compress-Archive`Командлет использует кодировку UTF-8.</span><span class="sxs-lookup"><span data-stu-id="1d833-149">The `Compress-Archive` cmdlet uses UTF-8 encoding.</span></span> <span data-ttu-id="1d833-150">Другие средства архивирования ZIP могут использовать другую схему кодирования.</span><span class="sxs-lookup"><span data-stu-id="1d833-150">Other ZIP archive tools may use a different encoding scheme.</span></span> <span data-ttu-id="1d833-151">При извлечении файлов с именами, которые не хранятся в кодировке UTF-8, `Expand-Archive` использует необработанное значение, найденное в архиве.</span><span class="sxs-lookup"><span data-stu-id="1d833-151">When extracting files with filenames not stored using UTF-8 encoding, `Expand-Archive` uses the raw value found in the archive.</span></span> <span data-ttu-id="1d833-152">Это может привести к тому, что имя файла будет отличаться от исходного имени файла, хранящегося в архиве.</span><span class="sxs-lookup"><span data-stu-id="1d833-152">This can result in a filename that is different than the source filename stored in the archive.</span></span>

## <span data-ttu-id="1d833-153">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="1d833-153">RELATED LINKS</span></span>

[<span data-ttu-id="1d833-154">Compress-Archive</span><span class="sxs-lookup"><span data-stu-id="1d833-154">Compress-Archive</span></span>](compress-archive.md)
