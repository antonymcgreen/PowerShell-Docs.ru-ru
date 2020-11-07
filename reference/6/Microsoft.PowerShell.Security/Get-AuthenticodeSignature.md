---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 04/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-authenticodesignature?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AuthenticodeSignature
ms.openlocfilehash: 351d666efad82d48d6d0390f98b472316602db1d
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94343714"
---
# <span data-ttu-id="b42a0-103">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="b42a0-103">Get-AuthenticodeSignature</span></span>

## <span data-ttu-id="b42a0-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b42a0-104">SYNOPSIS</span></span>
<span data-ttu-id="b42a0-105">Возвращает сведения о подписи Authenticode для файла.</span><span class="sxs-lookup"><span data-stu-id="b42a0-105">Gets information about the Authenticode signature for a file.</span></span>

## <span data-ttu-id="b42a0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b42a0-106">SYNTAX</span></span>

### <span data-ttu-id="b42a0-107">ByPath (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="b42a0-107">ByPath (Default)</span></span>

```
Get-AuthenticodeSignature [-FilePath] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="b42a0-108">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="b42a0-108">ByLiteralPath</span></span>

```
Get-AuthenticodeSignature -LiteralPath <String[]> [<CommonParameters>]
```

### <span data-ttu-id="b42a0-109">биконтент</span><span class="sxs-lookup"><span data-stu-id="b42a0-109">ByContent</span></span>

```
Get-AuthenticodeSignature -SourcePathOrExtension <String[]> -Content <Byte[]> [<CommonParameters>]
```

## <span data-ttu-id="b42a0-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b42a0-110">DESCRIPTION</span></span>

<span data-ttu-id="b42a0-111">`Get-AuthenticodeSignature`Командлет получает сведения о подписи Authenticode для файла или содержимого файла в виде массива байтов.</span><span class="sxs-lookup"><span data-stu-id="b42a0-111">The `Get-AuthenticodeSignature` cmdlet gets information about the Authenticode signature for a file or file content as a byte array.</span></span> <span data-ttu-id="b42a0-112">Если файл не подписан, сведения возвращаются, но поля будут пусты.</span><span class="sxs-lookup"><span data-stu-id="b42a0-112">If the file is not signed, the information is retrieved, but the fields are blank.</span></span>

## <span data-ttu-id="b42a0-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="b42a0-113">EXAMPLES</span></span>

### <span data-ttu-id="b42a0-114">Пример 1. получение подписи Authenticode для файла</span><span class="sxs-lookup"><span data-stu-id="b42a0-114">Example 1: Get the Authenticode signature for a file</span></span>

```powershell
Get-AuthenticodeSignature -FilePath "C:\Test\NewScript.ps1"
```

<span data-ttu-id="b42a0-115">Эта команда возвращает сведения о подписи Authenticode в файле NewScript.ps1.</span><span class="sxs-lookup"><span data-stu-id="b42a0-115">This command gets information about the Authenticode signature in the NewScript.ps1 file.</span></span> <span data-ttu-id="b42a0-116">Для указания файла используется параметр **FilePath** .</span><span class="sxs-lookup"><span data-stu-id="b42a0-116">It uses the **FilePath** parameter to specify the file.</span></span>

### <span data-ttu-id="b42a0-117">Пример 2. получение подписи Authenticode для нескольких файлов</span><span class="sxs-lookup"><span data-stu-id="b42a0-117">Example 2: Get the Authenticode signature for multiple files</span></span>

```powershell
Get-AuthenticodeSignature test.ps1, test1.ps1, sign-file.ps1, makexml.ps1
```

<span data-ttu-id="b42a0-118">Эта команда возвращает сведения о подписи Authenticode для четырех файлов, перечисленных в командной строке.</span><span class="sxs-lookup"><span data-stu-id="b42a0-118">This command gets information about the Authenticode signature for the four files listed at the command line.</span></span> <span data-ttu-id="b42a0-119">В этом примере имя параметра **FilePath** , которое является необязательным, опускается.</span><span class="sxs-lookup"><span data-stu-id="b42a0-119">In this example, the name of the **FilePath** parameter, which is optional, is omitted.</span></span>

### <span data-ttu-id="b42a0-120">Пример 3. Получение допустимых подписей Authenticode для нескольких файлов</span><span class="sxs-lookup"><span data-stu-id="b42a0-120">Example 3: Get only valid Authenticode signatures for multiple files</span></span>

```powershell
Get-ChildItem $PSHOME\*.* | ForEach-object {Get-AuthenticodeSignature $_} | Where-Object {$_.status -eq "Valid"}
```

<span data-ttu-id="b42a0-121">Эта команда выводит список всех файлов в `$PSHOME` каталоге с действительной подписью Authenticode.</span><span class="sxs-lookup"><span data-stu-id="b42a0-121">This command lists all of the files in the `$PSHOME` directory that have a valid Authenticode signature.</span></span> <span data-ttu-id="b42a0-122">`$PSHOME`Автоматическая переменная содержит путь к каталогу установки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b42a0-122">The `$PSHOME` automatic variable contains the path to the PowerShell installation directory.</span></span>

<span data-ttu-id="b42a0-123">Команда использует `Get-ChildItem` командлет для получения файлов в `$PSHOME` каталоге.</span><span class="sxs-lookup"><span data-stu-id="b42a0-123">The command uses the `Get-ChildItem` cmdlet to get the files in the `$PSHOME` directory.</span></span> <span data-ttu-id="b42a0-124">Он использует шаблон *.*</span><span class="sxs-lookup"><span data-stu-id="b42a0-124">It uses a pattern of *.*</span></span> <span data-ttu-id="b42a0-125">для исключения каталогов (хотя он также исключает файлы без точки в имени файла).</span><span class="sxs-lookup"><span data-stu-id="b42a0-125">to exclude directories (although it also excludes files without a dot in the filename).</span></span>

<span data-ttu-id="b42a0-126">Команда использует оператор конвейера ( `|` ) для отправки файлов в `$PSHOME` `ForEach-Object` командлет, где `Get-AuthenticodeSignature` вызывается для каждого файла.</span><span class="sxs-lookup"><span data-stu-id="b42a0-126">The command uses a pipeline operator (`|`) to send the files in `$PSHOME` to the `ForEach-Object` cmdlet, where `Get-AuthenticodeSignature` is called for each file.</span></span>

<span data-ttu-id="b42a0-127">Результаты `Get-AuthenticodeSignature` команды отправляются в `Where-Object` команду, которая выбирает только объекты сигнатуры с состоянием допустимо.</span><span class="sxs-lookup"><span data-stu-id="b42a0-127">The results of the `Get-AuthenticodeSignature` command are sent to a `Where-Object` command that selects only the signature objects with a status of Valid.</span></span>

### <span data-ttu-id="b42a0-128">Пример 4. получение подписи Authenticode для содержимого файла, указанного в виде массива байтов</span><span class="sxs-lookup"><span data-stu-id="b42a0-128">Example 4: Get the Authenticode signature for a file content specified as byte array</span></span>

```powershell
Get-AuthenticodeSignature -Content (Get-Content foo.ps1 -AsByteStream) -SourcePathorExtension ps1
```

<span data-ttu-id="b42a0-129">Эта команда возвращает сведения о подписи Authenticode для содержимого файла.</span><span class="sxs-lookup"><span data-stu-id="b42a0-129">This command gets information about the Authenticode signature for the content of a file.</span></span> <span data-ttu-id="b42a0-130">В этом примере расширение файла указывается вместе с содержимым файла.</span><span class="sxs-lookup"><span data-stu-id="b42a0-130">In this example, the file extension is specified along with the content of the file.</span></span>

## <span data-ttu-id="b42a0-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b42a0-131">PARAMETERS</span></span>

### <span data-ttu-id="b42a0-132">— Содержимое</span><span class="sxs-lookup"><span data-stu-id="b42a0-132">-Content</span></span>

<span data-ttu-id="b42a0-133">Содержимое файла в виде массива байтов, для которого получена подпись Authenticode.</span><span class="sxs-lookup"><span data-stu-id="b42a0-133">Contents of a file as a byte array for which the Authenticode signature is retrieved.</span></span> <span data-ttu-id="b42a0-134">Этот параметр должен использоваться с параметром **саурцепасорекстенсион** .</span><span class="sxs-lookup"><span data-stu-id="b42a0-134">This parameter must be used with **SourcePathOrExtension** parameter.</span></span> <span data-ttu-id="b42a0-135">Содержимое файла должно быть в формате Unicode (UTF-16LE).</span><span class="sxs-lookup"><span data-stu-id="b42a0-135">The contents of the file must be in Unicode (UTF-16LE) format.</span></span>

```yaml
Type: System.Byte[]
Parameter Sets: ByContent
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b42a0-136">-FilePath</span><span class="sxs-lookup"><span data-stu-id="b42a0-136">-FilePath</span></span>

<span data-ttu-id="b42a0-137">Указывает путь к файлу для проверки.</span><span class="sxs-lookup"><span data-stu-id="b42a0-137">Specifies the path to the file to examine.</span></span> <span data-ttu-id="b42a0-138">Подстановочные знаки допускаются, но путь при этом должен указывать на один файл.</span><span class="sxs-lookup"><span data-stu-id="b42a0-138">Wildcards are permitted, but they must lead to a single file.</span></span> <span data-ttu-id="b42a0-139">При указании значения для этого параметра необязательно вводить **FilePath** в командной строке.</span><span class="sxs-lookup"><span data-stu-id="b42a0-139">It is not necessary to type **FilePath** at the command line when you specify a value for this parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="b42a0-140">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b42a0-140">-LiteralPath</span></span>

<span data-ttu-id="b42a0-141">Указывает путь к анализируемому файлу.</span><span class="sxs-lookup"><span data-stu-id="b42a0-141">Specifies the path to the file being examined.</span></span> <span data-ttu-id="b42a0-142">В отличие от **FilePath** значение параметра **LiteralPath** используется именно в том виде, в котором оно вводится.</span><span class="sxs-lookup"><span data-stu-id="b42a0-142">Unlike **FilePath** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="b42a0-143">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="b42a0-143">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="b42a0-144">Если путь содержит escape-символ, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="b42a0-144">If the path includes an escape character, enclose it in single quotation marks.</span></span> <span data-ttu-id="b42a0-145">Одинарные кавычки указывают PowerShell не интерпретировать символы как escape-символы.</span><span class="sxs-lookup"><span data-stu-id="b42a0-145">Single quotation marks tell PowerShell not to interpret any characters as escape characters.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b42a0-146">-Саурцепасорекстенсион</span><span class="sxs-lookup"><span data-stu-id="b42a0-146">-SourcePathOrExtension</span></span>

<span data-ttu-id="b42a0-147">Путь к файлу или типу файла содержимого, для которого получена подпись Authenticode.</span><span class="sxs-lookup"><span data-stu-id="b42a0-147">Path to the file or file type of the content for which the Authenticode signature is retrieved.</span></span> <span data-ttu-id="b42a0-148">Этот параметр используется с **содержимым** , где содержимое файла передается как массив байтов.</span><span class="sxs-lookup"><span data-stu-id="b42a0-148">This parameter is used with **Content** where file content is passed as a byte array.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByContent
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b42a0-149">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b42a0-149">CommonParameters</span></span>

<span data-ttu-id="b42a0-150">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b42a0-150">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b42a0-151">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="b42a0-151">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="b42a0-152">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b42a0-152">INPUTS</span></span>

### <span data-ttu-id="b42a0-153">System.String</span><span class="sxs-lookup"><span data-stu-id="b42a0-153">System.String</span></span>

<span data-ttu-id="b42a0-154">Строку, содержащую путь к файлу, можно передать по конвейеру `Get-AuthenticodeSignature` .</span><span class="sxs-lookup"><span data-stu-id="b42a0-154">You can pipe a string that contains a file path to `Get-AuthenticodeSignature`.</span></span>

## <span data-ttu-id="b42a0-155">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b42a0-155">OUTPUTS</span></span>

### <span data-ttu-id="b42a0-156">System. Management. Automation. Signature</span><span class="sxs-lookup"><span data-stu-id="b42a0-156">System.Management.Automation.Signature</span></span>

<span data-ttu-id="b42a0-157">`Get-AuthenticodeSignature` Возвращает объект подписи для каждой сигнатуры, которую он получает.</span><span class="sxs-lookup"><span data-stu-id="b42a0-157">`Get-AuthenticodeSignature` returns a signature object for each signature that it gets.</span></span>

## <span data-ttu-id="b42a0-158">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b42a0-158">NOTES</span></span>

<span data-ttu-id="b42a0-159">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="b42a0-159">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="b42a0-160">Сведения о подписях Authenticode в PowerShell см. в разделе [about_Signing](../Microsoft.PowerShell.Core/About/about_Signing.md).</span><span class="sxs-lookup"><span data-stu-id="b42a0-160">For information about Authenticode signatures in PowerShell, see [about_Signing](../Microsoft.PowerShell.Core/About/about_Signing.md).</span></span>

## <span data-ttu-id="b42a0-161">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b42a0-161">RELATED LINKS</span></span>

[<span data-ttu-id="b42a0-162">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="b42a0-162">Get-ExecutionPolicy</span></span>](Get-ExecutionPolicy.md)

[<span data-ttu-id="b42a0-163">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="b42a0-163">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)

[<span data-ttu-id="b42a0-164">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="b42a0-164">Set-ExecutionPolicy</span></span>](Set-ExecutionPolicy.md)

[<span data-ttu-id="b42a0-165">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="b42a0-165">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[<span data-ttu-id="b42a0-166">about_Signing</span><span class="sxs-lookup"><span data-stu-id="b42a0-166">about_Signing</span></span>](../Microsoft.PowerShell.Core/About/about_Signing.md)
