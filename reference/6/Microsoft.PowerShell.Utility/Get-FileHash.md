---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-filehash?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-FileHash
ms.openlocfilehash: d9a83cc20042f7613dd1e6033beaa8b2341c3d15
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228997"
---
# <span data-ttu-id="abfc8-103">Get-FileHash</span><span class="sxs-lookup"><span data-stu-id="abfc8-103">Get-FileHash</span></span>

## <span data-ttu-id="abfc8-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="abfc8-104">SYNOPSIS</span></span>
<span data-ttu-id="abfc8-105">Вычисляет хэш-значение для файла с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="abfc8-105">Computes the hash value for a file by using a specified hash algorithm.</span></span>

## <span data-ttu-id="abfc8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="abfc8-106">SYNTAX</span></span>

### <span data-ttu-id="abfc8-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="abfc8-107">Path (Default)</span></span>

```
Get-FileHash [-Path] <String[]> [[-Algorithm] <String>] [<CommonParameters>]
```

### <span data-ttu-id="abfc8-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="abfc8-108">LiteralPath</span></span>

```
Get-FileHash [-LiteralPath] <String[]> [[-Algorithm] <String>] [<CommonParameters>]
```

### <span data-ttu-id="abfc8-109">стреампараметерсет</span><span class="sxs-lookup"><span data-stu-id="abfc8-109">StreamParameterSet</span></span>

```
Get-FileHash [-InputStream] <Stream> [[-Algorithm] <String>] [<CommonParameters>]
```

## <span data-ttu-id="abfc8-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="abfc8-110">DESCRIPTION</span></span>

<span data-ttu-id="abfc8-111">`Get-FileHash`Командлет выполняет вычисление хэш-значения для файла с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="abfc8-111">The `Get-FileHash` cmdlet computes the hash value for a file by using a specified hash algorithm.</span></span>
<span data-ttu-id="abfc8-112">Хэш-значение представляет собой уникальное значение, соответствующее содержимому файла.</span><span class="sxs-lookup"><span data-stu-id="abfc8-112">A hash value is a unique value that corresponds to the content of the file.</span></span> <span data-ttu-id="abfc8-113">Вместо определения содержимого файла по его имени, расширению или иному обозначению хэш назначает содержимому файла уникальное значение.</span><span class="sxs-lookup"><span data-stu-id="abfc8-113">Rather than identifying the contents of a file by its file name, extension, or other designation, a hash assigns a unique value to the contents of a file.</span></span> <span data-ttu-id="abfc8-114">Имена и расширения файлов могут изменяться без изменения содержимого файла и без изменения хэш-значения.</span><span class="sxs-lookup"><span data-stu-id="abfc8-114">File names and extensions can be changed without altering the content of the file, and without changing the hash value.</span></span> <span data-ttu-id="abfc8-115">Аналогичным образом содержимое файла может быть изменено без изменения имени или расширения.</span><span class="sxs-lookup"><span data-stu-id="abfc8-115">Similarly, the file's content can be changed without changing the name or extension.</span></span> <span data-ttu-id="abfc8-116">Однако при изменении даже одного символа в содержимом файла хэш-значение этого файла тоже изменяется.</span><span class="sxs-lookup"><span data-stu-id="abfc8-116">However, changing even a single character in the contents of a file changes the hash value of the file.</span></span>

<span data-ttu-id="abfc8-117">Хэш-значения позволяет криптографически защищенным образом убедиться, что содержимое файла не было изменено.</span><span class="sxs-lookup"><span data-stu-id="abfc8-117">The purpose of hash values is to provide a cryptographically-secure way to verify that the contents of a file have not been changed.</span></span> <span data-ttu-id="abfc8-118">Хотя некоторые алгоритмы хэширования, включая MD5 и SHA1, больше не считаются безопасными для атаки, целью безопасного алгоритма хеширования является визуализация невозможности изменения содержимого файла или путем случайной или несанкционированной попытки — и сохранения одинакового хэш-значения.</span><span class="sxs-lookup"><span data-stu-id="abfc8-118">While some hash algorithms, including MD5 and SHA1, are no longer considered secure against attack, the goal of a secure hash algorithm is to render it impossible to change the contents of a file -- either by accident, or by malicious or unauthorized attempt -- and maintain the same hash value.</span></span> <span data-ttu-id="abfc8-119">С помощью хэш-значений также можно определить, имеют ли два разных файла эквивалентное содержимое.</span><span class="sxs-lookup"><span data-stu-id="abfc8-119">You can also use hash values to determine if two different files have exactly the same content.</span></span> <span data-ttu-id="abfc8-120">Если хэш-значения двух файлов идентичны, содержимое этих файлов также идентично.</span><span class="sxs-lookup"><span data-stu-id="abfc8-120">If the hash values of two files are identical, the contents of the files are also identical.</span></span>

<span data-ttu-id="abfc8-121">По умолчанию `Get-FileHash` командлет использует алгоритм SHA256, хотя может использоваться любой алгоритм хэширования, поддерживаемый целевой операционной системой.</span><span class="sxs-lookup"><span data-stu-id="abfc8-121">By default, the `Get-FileHash` cmdlet uses the SHA256 algorithm, although any hash algorithm that is supported by the target operating system can be used.</span></span>

## <span data-ttu-id="abfc8-122">Примеры</span><span class="sxs-lookup"><span data-stu-id="abfc8-122">EXAMPLES</span></span>

### <span data-ttu-id="abfc8-123">Пример 1. Вычисление хэш-значения для файла</span><span class="sxs-lookup"><span data-stu-id="abfc8-123">Example 1: Compute the hash value for a file</span></span>

<span data-ttu-id="abfc8-124">В этом примере `Get-FileHash` командлет используется для вычисления хэш-значения для `/etc/apt/sources.list` файла.</span><span class="sxs-lookup"><span data-stu-id="abfc8-124">This example uses the `Get-FileHash` cmdlet to compute the hash value for the `/etc/apt/sources.list` file.</span></span> <span data-ttu-id="abfc8-125">По умолчанию используется хэш-алгоритм **SHA256** .</span><span class="sxs-lookup"><span data-stu-id="abfc8-125">The hash algorithm used is the default, **SHA256** .</span></span> <span data-ttu-id="abfc8-126">Выходные данные передаются в `Format-List` командлет для форматирования выходных данных в виде списка.</span><span class="sxs-lookup"><span data-stu-id="abfc8-126">The output is piped to the `Format-List` cmdlet to format the output as a list.</span></span>

```powershell
Get-FileHash /etc/apt/sources.list | Format-List
```

```Output
Algorithm : SHA256
Hash      : 3CBCFDDEC145E3382D592266BE193E5BE53443138EE6AB6CA09FF20DF609E268
Path      : /etc/apt/sources.list
```

### <span data-ttu-id="abfc8-127">Пример 2. Вычисление значения хэша для ISO-файла</span><span class="sxs-lookup"><span data-stu-id="abfc8-127">Example 2: Compute the hash value for an ISO file</span></span>

<span data-ttu-id="abfc8-128">В этом примере используется `Get-FileHash` командлет и алгоритм **SHA384** для вычисления значения хэша для ISO-файла, который администратор загрузил из Интернета.</span><span class="sxs-lookup"><span data-stu-id="abfc8-128">This example uses the `Get-FileHash` cmdlet and the **SHA384** algorithm to compute the hash value for an ISO file that an administrator has downloaded from the internet.</span></span> <span data-ttu-id="abfc8-129">Выходные данные передаются в `Format-List` командлет для форматирования выходных данных в виде списка.</span><span class="sxs-lookup"><span data-stu-id="abfc8-129">The output is piped to the `Format-List` cmdlet to format the output as a list.</span></span>

```powershell
Get-FileHash C:\Users\user1\Downloads\Contoso8_1_ENT.iso -Algorithm SHA384 | Format-List
```

```Output
Algorithm : SHA384
Hash      : 20AB1C2EE19FC96A7C66E33917D191A24E3CE9DAC99DB7C786ACCE31E559144FEAFC695C58E508E2EBBC9D3C96F21FA3
Path      : C:\Users\user1\Downloads\Contoso8_1_ENT.iso
```

### <span data-ttu-id="abfc8-130">Пример 3. Вычисление хэш-значения потока</span><span class="sxs-lookup"><span data-stu-id="abfc8-130">Example 3: Compute the hash value of a stream</span></span>

<span data-ttu-id="abfc8-131">В этом примере мы получаем использование **System .NET. WebClient** для загрузки пакета со [страницы выпуска PowerShell](https://github.com/PowerShell/PowerShell/releases/tag/v6.2.4).</span><span class="sxs-lookup"><span data-stu-id="abfc8-131">For this example, we get are using **System.Net.WebClient** to download a package from the [Powershell release page](https://github.com/PowerShell/PowerShell/releases/tag/v6.2.4).</span></span> <span data-ttu-id="abfc8-132">На странице выпуск также документируется хэш SHA256 каждого файла пакета.</span><span class="sxs-lookup"><span data-stu-id="abfc8-132">The release page also documents the SHA256 hash of each package file.</span></span> <span data-ttu-id="abfc8-133">Мы можем сравнить опубликованное хэш-значение с тем, которое вычисляется с помощью `Get-FileHash` .</span><span class="sxs-lookup"><span data-stu-id="abfc8-133">We can compare the published hash value with the one we calculate with `Get-FileHash`.</span></span>

```powershell
$wc = [System.Net.WebClient]::new()
$pkgurl = 'https://github.com/PowerShell/PowerShell/releases/download/v6.2.4/powershell_6.2.4-1.debian.9_amd64.deb'
$publishedHash = '8E28E54D601F0751922DE24632C1E716B4684876255CF82304A9B19E89A9CCAC'
$FileHash = Get-FileHash -InputStream ($wc.OpenRead($pkgurl))
$FileHash.Hash -eq $publishedHash
```

```Output
True
```

### <span data-ttu-id="abfc8-134">Пример 4. вычисление хэша строки</span><span class="sxs-lookup"><span data-stu-id="abfc8-134">Example 4: Compute the hash of a string</span></span>

<span data-ttu-id="abfc8-135">PowerShell не предоставляет командлет для вычисления хэша строки.</span><span class="sxs-lookup"><span data-stu-id="abfc8-135">PowerShell does not provide a cmdlet to compute the hash of a string.</span></span> <span data-ttu-id="abfc8-136">Однако можно записать строку в поток и использовать параметр **InputStream** из `Get-FileHash` для получения хэш-значения.</span><span class="sxs-lookup"><span data-stu-id="abfc8-136">However, you can write a string to a stream and use the **InputStream** parameter of `Get-FileHash` to get the hash value.</span></span>

```powershell
$stringAsStream = [System.IO.MemoryStream]::new()
$writer = [System.IO.StreamWriter]::new($stringAsStream)
$writer.write("Hello world")
$writer.Flush()
$stringAsStream.Position = 0
Get-FileHash -InputStream $stringAsStream | Select-Object Hash
```

```Output
Hash
----
64EC88CA00B268E5BA1A35678A1B5316D212F4F366B2477232534A8AECA37F3C
```

## <span data-ttu-id="abfc8-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="abfc8-137">PARAMETERS</span></span>

### <span data-ttu-id="abfc8-138">Алгоритм</span><span class="sxs-lookup"><span data-stu-id="abfc8-138">-Algorithm</span></span>

<span data-ttu-id="abfc8-139">Задает криптографическую хэш-функцию, используемую для вычисления хэш-значения содержимого указанного файла или потока.</span><span class="sxs-lookup"><span data-stu-id="abfc8-139">Specifies the cryptographic hash function to use for computing the hash value of the contents of the specified file or stream.</span></span> <span data-ttu-id="abfc8-140">Криптографическая хэш-функция имеет свойство, которое не может найти два разных файла с одинаковым хэш-значением.</span><span class="sxs-lookup"><span data-stu-id="abfc8-140">A cryptographic hash function has the property that it is infeasible to find two different files with the same hash value.</span></span> <span data-ttu-id="abfc8-141">Хэш-функции обычно используются с цифровыми подписями и для обеспечения целостности данных.</span><span class="sxs-lookup"><span data-stu-id="abfc8-141">Hash functions are commonly used with digital signatures and for data integrity.</span></span> <span data-ttu-id="abfc8-142">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="abfc8-142">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="abfc8-143">SHA1</span><span class="sxs-lookup"><span data-stu-id="abfc8-143">SHA1</span></span>
- <span data-ttu-id="abfc8-144">SHA256</span><span class="sxs-lookup"><span data-stu-id="abfc8-144">SHA256</span></span>
- <span data-ttu-id="abfc8-145">SHA384</span><span class="sxs-lookup"><span data-stu-id="abfc8-145">SHA384</span></span>
- <span data-ttu-id="abfc8-146">SHA512</span><span class="sxs-lookup"><span data-stu-id="abfc8-146">SHA512</span></span>
- <span data-ttu-id="abfc8-147">MD5</span><span class="sxs-lookup"><span data-stu-id="abfc8-147">MD5</span></span>

<span data-ttu-id="abfc8-148">Если значение не указано или параметр пропущен, используется значение по умолчанию — SHA256.</span><span class="sxs-lookup"><span data-stu-id="abfc8-148">If no value is specified, or if the parameter is omitted, the default value is SHA256.</span></span>

<span data-ttu-id="abfc8-149">По соображениям безопасности алгоритмы MD5 и SHA1, которые больше не считаются безопасными, следует использовать только для проверки на наличие изменений и не следует применять для создания хэш-значений файлов, которые требуют защиты от атак или незаконного изменения.</span><span class="sxs-lookup"><span data-stu-id="abfc8-149">For security reasons, MD5 and SHA1, which are no longer considered secure, should only be used for simple change validation, and should not be used to generate hash values for files that require protection from attack or tampering.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: SHA1, SHA256, SHA384, SHA512, MD5

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="abfc8-150">-InputStream</span><span class="sxs-lookup"><span data-stu-id="abfc8-150">-InputStream</span></span>

<span data-ttu-id="abfc8-151">Задает входной поток.</span><span class="sxs-lookup"><span data-stu-id="abfc8-151">Specifies the input stream.</span></span>

```yaml
Type: System.IO.Stream
Parameter Sets: StreamParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="abfc8-152">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="abfc8-152">-LiteralPath</span></span>

<span data-ttu-id="abfc8-153">Указывает путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="abfc8-153">Specifies the path to a file.</span></span> <span data-ttu-id="abfc8-154">В отличие от параметра **Path** значение параметра **LiteralPath** используется в точности так, как вводится.</span><span class="sxs-lookup"><span data-stu-id="abfc8-154">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="abfc8-155">Никакие символы не распознаются как подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="abfc8-155">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="abfc8-156">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="abfc8-156">If the path includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="abfc8-157">Одинарные кавычки предписывает PowerShell не интерпретировать символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="abfc8-157">Single quotation marks instruct PowerShell not to interpret characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="abfc8-158">-Path</span><span class="sxs-lookup"><span data-stu-id="abfc8-158">-Path</span></span>

<span data-ttu-id="abfc8-159">Задает путь к одному или нескольким файлам в виде массива.</span><span class="sxs-lookup"><span data-stu-id="abfc8-159">Specifies the path to one or more files as an array.</span></span> <span data-ttu-id="abfc8-160">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="abfc8-160">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="abfc8-161">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="abfc8-161">CommonParameters</span></span>

<span data-ttu-id="abfc8-162">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="abfc8-162">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="abfc8-163">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="abfc8-163">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="abfc8-164">Входные данные</span><span class="sxs-lookup"><span data-stu-id="abfc8-164">INPUTS</span></span>

### <span data-ttu-id="abfc8-165">System.String</span><span class="sxs-lookup"><span data-stu-id="abfc8-165">System.String</span></span>

<span data-ttu-id="abfc8-166">Строку можно передать в `Get-FileHash` командлет, содержащий путь к одному или нескольким файлам.</span><span class="sxs-lookup"><span data-stu-id="abfc8-166">You can pipe a string to the `Get-FileHash` cmdlet that contains a path to one or more files.</span></span>

## <span data-ttu-id="abfc8-167">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="abfc8-167">OUTPUTS</span></span>

### <span data-ttu-id="abfc8-168">Microsoft. PowerShell. Utility. FileHash</span><span class="sxs-lookup"><span data-stu-id="abfc8-168">Microsoft.Powershell.Utility.FileHash</span></span>

<span data-ttu-id="abfc8-169">`Get-FileHash` Возвращает объект, представляющий путь к указанному файлу, значение вычисленного хэша и алгоритм, используемый для вычисления хэша.</span><span class="sxs-lookup"><span data-stu-id="abfc8-169">`Get-FileHash` returns an object that represents the path to the specified file, the value of the computed hash, and the algorithm used to compute the hash.</span></span>

## <span data-ttu-id="abfc8-170">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="abfc8-170">NOTES</span></span>

## <span data-ttu-id="abfc8-171">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="abfc8-171">RELATED LINKS</span></span>

[<span data-ttu-id="abfc8-172">Format-List</span><span class="sxs-lookup"><span data-stu-id="abfc8-172">Format-List</span></span>](Format-List.md)
