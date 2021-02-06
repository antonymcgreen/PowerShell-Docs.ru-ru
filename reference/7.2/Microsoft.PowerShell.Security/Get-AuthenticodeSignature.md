---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 04/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-authenticodesignature?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AuthenticodeSignature
ms.openlocfilehash: 16c61b1fd442eb68c458c3b524a8fc55d5eedcb6
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604114"
---
# <span data-ttu-id="36d23-102">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="36d23-102">Get-AuthenticodeSignature</span></span>

## <span data-ttu-id="36d23-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="36d23-103">SYNOPSIS</span></span>
<span data-ttu-id="36d23-104">Возвращает сведения о подписи Authenticode для файла.</span><span class="sxs-lookup"><span data-stu-id="36d23-104">Gets information about the Authenticode signature for a file.</span></span>

## <span data-ttu-id="36d23-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="36d23-105">SYNTAX</span></span>

### <span data-ttu-id="36d23-106">ByPath (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="36d23-106">ByPath (Default)</span></span>

```
Get-AuthenticodeSignature [-FilePath] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="36d23-107">ByLiteralPath</span><span class="sxs-lookup"><span data-stu-id="36d23-107">ByLiteralPath</span></span>

```
Get-AuthenticodeSignature -LiteralPath <String[]> [<CommonParameters>]
```

### <span data-ttu-id="36d23-108">биконтент</span><span class="sxs-lookup"><span data-stu-id="36d23-108">ByContent</span></span>

```
Get-AuthenticodeSignature -SourcePathOrExtension <String[]> -Content <Byte[]> [<CommonParameters>]
```

## <span data-ttu-id="36d23-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="36d23-109">DESCRIPTION</span></span>

<span data-ttu-id="36d23-110">`Get-AuthenticodeSignature`Командлет получает сведения о подписи Authenticode для файла или содержимого файла в виде массива байтов.</span><span class="sxs-lookup"><span data-stu-id="36d23-110">The `Get-AuthenticodeSignature` cmdlet gets information about the Authenticode signature for a file or file content as a byte array.</span></span> <span data-ttu-id="36d23-111">Если файл не подписан, сведения возвращаются, но поля будут пусты.</span><span class="sxs-lookup"><span data-stu-id="36d23-111">If the file is not signed, the information is retrieved, but the fields are blank.</span></span>

## <span data-ttu-id="36d23-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="36d23-112">EXAMPLES</span></span>

### <span data-ttu-id="36d23-113">Пример 1. получение подписи Authenticode для файла</span><span class="sxs-lookup"><span data-stu-id="36d23-113">Example 1: Get the Authenticode signature for a file</span></span>

```powershell
Get-AuthenticodeSignature -FilePath "C:\Test\NewScript.ps1"
```

<span data-ttu-id="36d23-114">Эта команда возвращает сведения о подписи Authenticode в файле NewScript.ps1.</span><span class="sxs-lookup"><span data-stu-id="36d23-114">This command gets information about the Authenticode signature in the NewScript.ps1 file.</span></span> <span data-ttu-id="36d23-115">Для указания файла используется параметр **FilePath** .</span><span class="sxs-lookup"><span data-stu-id="36d23-115">It uses the **FilePath** parameter to specify the file.</span></span>

### <span data-ttu-id="36d23-116">Пример 2. получение подписи Authenticode для нескольких файлов</span><span class="sxs-lookup"><span data-stu-id="36d23-116">Example 2: Get the Authenticode signature for multiple files</span></span>

```powershell
Get-AuthenticodeSignature test.ps1, test1.ps1, sign-file.ps1, makexml.ps1
```

<span data-ttu-id="36d23-117">Эта команда возвращает сведения о подписи Authenticode для четырех файлов, перечисленных в командной строке.</span><span class="sxs-lookup"><span data-stu-id="36d23-117">This command gets information about the Authenticode signature for the four files listed at the command line.</span></span> <span data-ttu-id="36d23-118">В этом примере имя параметра **FilePath** , которое является необязательным, опускается.</span><span class="sxs-lookup"><span data-stu-id="36d23-118">In this example, the name of the **FilePath** parameter, which is optional, is omitted.</span></span>

### <span data-ttu-id="36d23-119">Пример 3. Получение допустимых подписей Authenticode для нескольких файлов</span><span class="sxs-lookup"><span data-stu-id="36d23-119">Example 3: Get only valid Authenticode signatures for multiple files</span></span>

```powershell
Get-ChildItem $PSHOME\*.* | ForEach-object {Get-AuthenticodeSignature $_} | Where-Object {$_.status -eq "Valid"}
```

<span data-ttu-id="36d23-120">Эта команда выводит список всех файлов в `$PSHOME` каталоге с действительной подписью Authenticode.</span><span class="sxs-lookup"><span data-stu-id="36d23-120">This command lists all of the files in the `$PSHOME` directory that have a valid Authenticode signature.</span></span> <span data-ttu-id="36d23-121">`$PSHOME`Автоматическая переменная содержит путь к каталогу установки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="36d23-121">The `$PSHOME` automatic variable contains the path to the PowerShell installation directory.</span></span>

<span data-ttu-id="36d23-122">Команда использует `Get-ChildItem` командлет для получения файлов в `$PSHOME` каталоге.</span><span class="sxs-lookup"><span data-stu-id="36d23-122">The command uses the `Get-ChildItem` cmdlet to get the files in the `$PSHOME` directory.</span></span> <span data-ttu-id="36d23-123">Он использует шаблон *.*</span><span class="sxs-lookup"><span data-stu-id="36d23-123">It uses a pattern of *.*</span></span> <span data-ttu-id="36d23-124">для исключения каталогов (хотя он также исключает файлы без точки в имени файла).</span><span class="sxs-lookup"><span data-stu-id="36d23-124">to exclude directories (although it also excludes files without a dot in the filename).</span></span>

<span data-ttu-id="36d23-125">Команда использует оператор конвейера ( `|` ) для отправки файлов в `$PSHOME` `ForEach-Object` командлет, где `Get-AuthenticodeSignature` вызывается для каждого файла.</span><span class="sxs-lookup"><span data-stu-id="36d23-125">The command uses a pipeline operator (`|`) to send the files in `$PSHOME` to the `ForEach-Object` cmdlet, where `Get-AuthenticodeSignature` is called for each file.</span></span>

<span data-ttu-id="36d23-126">Результаты `Get-AuthenticodeSignature` команды отправляются в `Where-Object` команду, которая выбирает только объекты сигнатуры с состоянием допустимо.</span><span class="sxs-lookup"><span data-stu-id="36d23-126">The results of the `Get-AuthenticodeSignature` command are sent to a `Where-Object` command that selects only the signature objects with a status of Valid.</span></span>

### <span data-ttu-id="36d23-127">Пример 4. получение подписи Authenticode для содержимого файла, указанного в виде массива байтов</span><span class="sxs-lookup"><span data-stu-id="36d23-127">Example 4: Get the Authenticode signature for a file content specified as byte array</span></span>

```powershell
Get-AuthenticodeSignature -Content (Get-Content foo.ps1 -AsByteStream) -SourcePathorExtension ps1
```

<span data-ttu-id="36d23-128">Эта команда возвращает сведения о подписи Authenticode для содержимого файла.</span><span class="sxs-lookup"><span data-stu-id="36d23-128">This command gets information about the Authenticode signature for the content of a file.</span></span> <span data-ttu-id="36d23-129">В этом примере расширение файла указывается вместе с содержимым файла.</span><span class="sxs-lookup"><span data-stu-id="36d23-129">In this example, the file extension is specified along with the content of the file.</span></span>

## <span data-ttu-id="36d23-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="36d23-130">PARAMETERS</span></span>

### <span data-ttu-id="36d23-131">— Содержимое</span><span class="sxs-lookup"><span data-stu-id="36d23-131">-Content</span></span>

<span data-ttu-id="36d23-132">Содержимое файла в виде массива байтов, для которого получена подпись Authenticode.</span><span class="sxs-lookup"><span data-stu-id="36d23-132">Contents of a file as a byte array for which the Authenticode signature is retrieved.</span></span> <span data-ttu-id="36d23-133">Этот параметр должен использоваться с параметром **саурцепасорекстенсион** .</span><span class="sxs-lookup"><span data-stu-id="36d23-133">This parameter must be used with **SourcePathOrExtension** parameter.</span></span> <span data-ttu-id="36d23-134">Содержимое файла должно быть в формате Unicode (UTF-16LE).</span><span class="sxs-lookup"><span data-stu-id="36d23-134">The contents of the file must be in Unicode (UTF-16LE) format.</span></span>

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

### <span data-ttu-id="36d23-135">-FilePath</span><span class="sxs-lookup"><span data-stu-id="36d23-135">-FilePath</span></span>

<span data-ttu-id="36d23-136">Указывает путь к файлу для проверки.</span><span class="sxs-lookup"><span data-stu-id="36d23-136">Specifies the path to the file to examine.</span></span> <span data-ttu-id="36d23-137">Подстановочные знаки допускаются, но путь при этом должен указывать на один файл.</span><span class="sxs-lookup"><span data-stu-id="36d23-137">Wildcards are permitted, but they must lead to a single file.</span></span> <span data-ttu-id="36d23-138">При указании значения для этого параметра необязательно вводить **FilePath** в командной строке.</span><span class="sxs-lookup"><span data-stu-id="36d23-138">It is not necessary to type **FilePath** at the command line when you specify a value for this parameter.</span></span>

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

### <span data-ttu-id="36d23-139">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="36d23-139">-LiteralPath</span></span>

<span data-ttu-id="36d23-140">Указывает путь к анализируемому файлу.</span><span class="sxs-lookup"><span data-stu-id="36d23-140">Specifies the path to the file being examined.</span></span> <span data-ttu-id="36d23-141">В отличие от **FilePath** значение параметра **LiteralPath** используется именно в том виде, в котором оно вводится.</span><span class="sxs-lookup"><span data-stu-id="36d23-141">Unlike **FilePath**, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="36d23-142">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="36d23-142">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="36d23-143">Если путь содержит escape-символ, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="36d23-143">If the path includes an escape character, enclose it in single quotation marks.</span></span> <span data-ttu-id="36d23-144">Одинарные кавычки указывают PowerShell не интерпретировать символы как escape-символы.</span><span class="sxs-lookup"><span data-stu-id="36d23-144">Single quotation marks tell PowerShell not to interpret any characters as escape characters.</span></span>

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

### <span data-ttu-id="36d23-145">-Саурцепасорекстенсион</span><span class="sxs-lookup"><span data-stu-id="36d23-145">-SourcePathOrExtension</span></span>

<span data-ttu-id="36d23-146">Путь к файлу или типу файла содержимого, для которого получена подпись Authenticode.</span><span class="sxs-lookup"><span data-stu-id="36d23-146">Path to the file or file type of the content for which the Authenticode signature is retrieved.</span></span> <span data-ttu-id="36d23-147">Этот параметр используется с **содержимым** , где содержимое файла передается как массив байтов.</span><span class="sxs-lookup"><span data-stu-id="36d23-147">This parameter is used with **Content** where file content is passed as a byte array.</span></span>

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

### <span data-ttu-id="36d23-148">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="36d23-148">CommonParameters</span></span>

<span data-ttu-id="36d23-149">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="36d23-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="36d23-150">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="36d23-150">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="36d23-151">Входные данные</span><span class="sxs-lookup"><span data-stu-id="36d23-151">INPUTS</span></span>

### <span data-ttu-id="36d23-152">System.String</span><span class="sxs-lookup"><span data-stu-id="36d23-152">System.String</span></span>

<span data-ttu-id="36d23-153">Строку, содержащую путь к файлу, можно передать по конвейеру `Get-AuthenticodeSignature` .</span><span class="sxs-lookup"><span data-stu-id="36d23-153">You can pipe a string that contains a file path to `Get-AuthenticodeSignature`.</span></span>

## <span data-ttu-id="36d23-154">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="36d23-154">OUTPUTS</span></span>

### <span data-ttu-id="36d23-155">System. Management. Automation. Signature</span><span class="sxs-lookup"><span data-stu-id="36d23-155">System.Management.Automation.Signature</span></span>

<span data-ttu-id="36d23-156">`Get-AuthenticodeSignature` Возвращает объект подписи для каждой сигнатуры, которую он получает.</span><span class="sxs-lookup"><span data-stu-id="36d23-156">`Get-AuthenticodeSignature` returns a signature object for each signature that it gets.</span></span>

## <span data-ttu-id="36d23-157">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="36d23-157">NOTES</span></span>

<span data-ttu-id="36d23-158">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="36d23-158">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="36d23-159">Сведения о подписях Authenticode в PowerShell см. в разделе [about_Signing](../Microsoft.PowerShell.Core/About/about_Signing.md).</span><span class="sxs-lookup"><span data-stu-id="36d23-159">For information about Authenticode signatures in PowerShell, see [about_Signing](../Microsoft.PowerShell.Core/About/about_Signing.md).</span></span>

## <span data-ttu-id="36d23-160">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="36d23-160">RELATED LINKS</span></span>

[<span data-ttu-id="36d23-161">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="36d23-161">Get-ExecutionPolicy</span></span>](Get-ExecutionPolicy.md)

[<span data-ttu-id="36d23-162">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="36d23-162">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)

[<span data-ttu-id="36d23-163">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="36d23-163">Set-ExecutionPolicy</span></span>](Set-ExecutionPolicy.md)

[<span data-ttu-id="36d23-164">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="36d23-164">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[<span data-ttu-id="36d23-165">about_Signing</span><span class="sxs-lookup"><span data-stu-id="36d23-165">about_Signing</span></span>](../Microsoft.PowerShell.Core/About/about_Signing.md)
