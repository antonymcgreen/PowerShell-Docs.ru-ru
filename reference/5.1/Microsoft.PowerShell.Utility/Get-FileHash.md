---
external help file: Microsoft.PowerShell.Utility-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-filehash?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-FileHash
ms.openlocfilehash: ce0ecdfc216680f255718b1a03f78276364b1c50
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227657"
---
# <span data-ttu-id="021f5-103">Get-FileHash</span><span class="sxs-lookup"><span data-stu-id="021f5-103">Get-FileHash</span></span>

## <span data-ttu-id="021f5-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="021f5-104">SYNOPSIS</span></span>
<span data-ttu-id="021f5-105">Вычисляет хэш-значение для файла с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="021f5-105">Computes the hash value for a file by using a specified hash algorithm.</span></span>

## <span data-ttu-id="021f5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="021f5-106">SYNTAX</span></span>

### <span data-ttu-id="021f5-107">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="021f5-107">Path (Default)</span></span>

```
Get-FileHash [-Path] <String[]> [-Algorithm <String>] [<CommonParameters>]
```

### <span data-ttu-id="021f5-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="021f5-108">LiteralPath</span></span>

```
Get-FileHash -LiteralPath <String[]> [-Algorithm <String>] [<CommonParameters>]
```

### <span data-ttu-id="021f5-109">STREAM</span><span class="sxs-lookup"><span data-stu-id="021f5-109">Stream</span></span>

```
Get-FileHash -InputStream <Stream> [-Algorithm <String>] [<CommonParameters>]
```

## <span data-ttu-id="021f5-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="021f5-110">DESCRIPTION</span></span>

<span data-ttu-id="021f5-111">`Get-FileHash`Командлет выполняет вычисление хэш-значения для файла с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="021f5-111">The `Get-FileHash` cmdlet computes the hash value for a file by using a specified hash algorithm.</span></span>
<span data-ttu-id="021f5-112">Хэш-значение представляет собой уникальное значение, соответствующее содержимому файла.</span><span class="sxs-lookup"><span data-stu-id="021f5-112">A hash value is a unique value that corresponds to the content of the file.</span></span> <span data-ttu-id="021f5-113">Вместо определения содержимого файла по его имени, расширению или иному обозначению хэш назначает содержимому файла уникальное значение.</span><span class="sxs-lookup"><span data-stu-id="021f5-113">Rather than identifying the contents of a file by its file name, extension, or other designation, a hash assigns a unique value to the contents of a file.</span></span> <span data-ttu-id="021f5-114">Имена и расширения файлов могут изменяться без изменения содержимого файла и без изменения хэш-значения.</span><span class="sxs-lookup"><span data-stu-id="021f5-114">File names and extensions can be changed without altering the content of the file, and without changing the hash value.</span></span> <span data-ttu-id="021f5-115">Аналогичным образом содержимое файла может быть изменено без изменения имени или расширения.</span><span class="sxs-lookup"><span data-stu-id="021f5-115">Similarly, the file's content can be changed without changing the name or extension.</span></span> <span data-ttu-id="021f5-116">Однако при изменении даже одного символа в содержимом файла хэш-значение этого файла тоже изменяется.</span><span class="sxs-lookup"><span data-stu-id="021f5-116">However, changing even a single character in the contents of a file changes the hash value of the file.</span></span>

<span data-ttu-id="021f5-117">Хэш-значения позволяет криптографически защищенным образом убедиться, что содержимое файла не было изменено.</span><span class="sxs-lookup"><span data-stu-id="021f5-117">The purpose of hash values is to provide a cryptographically-secure way to verify that the contents of a file have not been changed.</span></span> <span data-ttu-id="021f5-118">Хотя некоторые алгоритмы хэширования, включая MD5 и SHA1, больше не считаются безопасными для атаки, целью безопасного алгоритма хеширования является визуализация невозможности изменения содержимого файла или путем случайной или несанкционированной попытки — и сохранения одинакового хэш-значения.</span><span class="sxs-lookup"><span data-stu-id="021f5-118">While some hash algorithms, including MD5 and SHA1, are no longer considered secure against attack, the goal of a secure hash algorithm is to render it impossible to change the contents of a file -- either by accident, or by malicious or unauthorized attempt -- and maintain the same hash value.</span></span> <span data-ttu-id="021f5-119">С помощью хэш-значений также можно определить, имеют ли два разных файла эквивалентное содержимое.</span><span class="sxs-lookup"><span data-stu-id="021f5-119">You can also use hash values to determine if two different files have exactly the same content.</span></span> <span data-ttu-id="021f5-120">Если хэш-значения двух файлов идентичны, содержимое этих файлов также идентично.</span><span class="sxs-lookup"><span data-stu-id="021f5-120">If the hash values of two files are identical, the contents of the files are also identical.</span></span>

<span data-ttu-id="021f5-121">По умолчанию `Get-FileHash` командлет использует алгоритм SHA256, хотя может использоваться любой алгоритм хэширования, поддерживаемый целевой операционной системой.</span><span class="sxs-lookup"><span data-stu-id="021f5-121">By default, the `Get-FileHash` cmdlet uses the SHA256 algorithm, although any hash algorithm that is supported by the target operating system can be used.</span></span>

## <span data-ttu-id="021f5-122">Примеры</span><span class="sxs-lookup"><span data-stu-id="021f5-122">EXAMPLES</span></span>

### <span data-ttu-id="021f5-123">Пример 1. Вычисление хэш-значения для файла</span><span class="sxs-lookup"><span data-stu-id="021f5-123">Example 1: Compute the hash value for a file</span></span>

<span data-ttu-id="021f5-124">В этом примере `Get-FileHash` командлет используется для вычисления хэш-значения для `Powershell.exe` файла.</span><span class="sxs-lookup"><span data-stu-id="021f5-124">This example uses the `Get-FileHash` cmdlet to compute the hash value for the `Powershell.exe` file.</span></span>
<span data-ttu-id="021f5-125">Используется хэш-алгоритм по умолчанию — SHA256.</span><span class="sxs-lookup"><span data-stu-id="021f5-125">The hash algorithm used is the default, SHA256.</span></span> <span data-ttu-id="021f5-126">Выходные данные передаются в `Format-List` командлет для форматирования выходных данных в виде списка.</span><span class="sxs-lookup"><span data-stu-id="021f5-126">The output is piped to the `Format-List` cmdlet to format the output as a list.</span></span>

```powershell
Get-FileHash $PSHOME\powershell.exe | Format-List
```

```Output
Algorithm : SHA256
Hash      : 908B64B1971A979C7E3E8CE4621945CBA84854CB98D76367B791A6E22B5F6D53
Path      : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe
```

### <span data-ttu-id="021f5-127">Пример 2. Вычисление значения хэша для ISO-файла</span><span class="sxs-lookup"><span data-stu-id="021f5-127">Example 2: Compute the hash value for an ISO file</span></span>

<span data-ttu-id="021f5-128">В этом примере используется `Get-FileHash` командлет и алгоритм **SHA384** для вычисления значения хэша для ISO-файла, который администратор загрузил из Интернета.</span><span class="sxs-lookup"><span data-stu-id="021f5-128">This example uses the `Get-FileHash` cmdlet and the **SHA384** algorithm to compute the hash value for an ISO file that an administrator has downloaded from the internet.</span></span> <span data-ttu-id="021f5-129">Выходные данные передаются в `Format-List` командлет для форматирования выходных данных в виде списка.</span><span class="sxs-lookup"><span data-stu-id="021f5-129">The output is piped to the `Format-List` cmdlet to format the output as a list.</span></span>

```powershell
Get-FileHash C:\Users\user1\Downloads\Contoso8_1_ENT.iso -Algorithm SHA384 | Format-List
```

```Output
Algorithm : SHA384
Hash      : 20AB1C2EE19FC96A7C66E33917D191A24E3CE9DAC99DB7C786ACCE31E559144FEAFC695C58E508E2EBBC9D3C96F21FA3
Path      : C:\Users\user1\Downloads\Contoso8_1_ENT.iso
```

### <span data-ttu-id="021f5-130">Пример 3. Вычисление хэш-значения потока</span><span class="sxs-lookup"><span data-stu-id="021f5-130">Example 3: Compute the hash value of a stream</span></span>

<span data-ttu-id="021f5-131">В этом примере мы получаем использование **System .NET. WebClient** для загрузки пакета со [страницы выпуска PowerShell](https://github.com/PowerShell/PowerShell/releases/tag/v6.2.4).</span><span class="sxs-lookup"><span data-stu-id="021f5-131">For this example, we get are using **System.Net.WebClient** to download a package from the [Powershell release page](https://github.com/PowerShell/PowerShell/releases/tag/v6.2.4).</span></span> <span data-ttu-id="021f5-132">На странице выпуск также документируется хэш SHA256 каждого файла пакета.</span><span class="sxs-lookup"><span data-stu-id="021f5-132">The release page also documents the SHA256 hash of each package file.</span></span> <span data-ttu-id="021f5-133">Мы можем сравнить опубликованное хэш-значение с тем, которое вычисляется с помощью `Get-FileHash` .</span><span class="sxs-lookup"><span data-stu-id="021f5-133">We can compare the published hash value with the one we calculate with `Get-FileHash`.</span></span>

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

### <span data-ttu-id="021f5-134">Пример 4. вычисление хэша строки</span><span class="sxs-lookup"><span data-stu-id="021f5-134">Example 4: Compute the hash of a string</span></span>

<span data-ttu-id="021f5-135">PowerShell не предоставляет командлет для вычисления хэша строки.</span><span class="sxs-lookup"><span data-stu-id="021f5-135">PowerShell does not provide a cmdlet to compute the hash of a string.</span></span> <span data-ttu-id="021f5-136">Однако можно записать строку в поток и использовать параметр **InputStream** из `Get-FileHash` для получения хэш-значения.</span><span class="sxs-lookup"><span data-stu-id="021f5-136">However, you can write a string to a stream and use the **InputStream** parameter of `Get-FileHash` to get the hash value.</span></span>

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

## <span data-ttu-id="021f5-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="021f5-137">PARAMETERS</span></span>

### <span data-ttu-id="021f5-138">Алгоритм</span><span class="sxs-lookup"><span data-stu-id="021f5-138">-Algorithm</span></span>

<span data-ttu-id="021f5-139">Задает криптографическую хэш-функцию, используемую для вычисления хэш-значения содержимого указанного файла или потока.</span><span class="sxs-lookup"><span data-stu-id="021f5-139">Specifies the cryptographic hash function to use for computing the hash value of the contents of the specified file or stream.</span></span> <span data-ttu-id="021f5-140">Криптографическая хэш-функция имеет свойство, которое не может найти два разных файла с одинаковым хэш-значением.</span><span class="sxs-lookup"><span data-stu-id="021f5-140">A cryptographic hash function has the property that it is infeasible to find two different files with the same hash value.</span></span> <span data-ttu-id="021f5-141">Хэш-функции обычно используются с цифровыми подписями и для обеспечения целостности данных.</span><span class="sxs-lookup"><span data-stu-id="021f5-141">Hash functions are commonly used with digital signatures and for data integrity.</span></span> <span data-ttu-id="021f5-142">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="021f5-142">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="021f5-143">SHA1</span><span class="sxs-lookup"><span data-stu-id="021f5-143">SHA1</span></span>
- <span data-ttu-id="021f5-144">SHA256</span><span class="sxs-lookup"><span data-stu-id="021f5-144">SHA256</span></span>
- <span data-ttu-id="021f5-145">SHA384</span><span class="sxs-lookup"><span data-stu-id="021f5-145">SHA384</span></span>
- <span data-ttu-id="021f5-146">SHA512</span><span class="sxs-lookup"><span data-stu-id="021f5-146">SHA512</span></span>
- <span data-ttu-id="021f5-147">MACTripleDES</span><span class="sxs-lookup"><span data-stu-id="021f5-147">MACTripleDES</span></span>
- <span data-ttu-id="021f5-148">MD5</span><span class="sxs-lookup"><span data-stu-id="021f5-148">MD5</span></span>
- <span data-ttu-id="021f5-149">RIPEMD160</span><span class="sxs-lookup"><span data-stu-id="021f5-149">RIPEMD160</span></span>

<span data-ttu-id="021f5-150">Если значение не указано или параметр пропущен, используется значение по умолчанию — SHA256.</span><span class="sxs-lookup"><span data-stu-id="021f5-150">If no value is specified, or if the parameter is omitted, the default value is SHA256.</span></span>

<span data-ttu-id="021f5-151">По соображениям безопасности алгоритмы MD5 и SHA1, которые больше не считаются безопасными, следует использовать только для проверки на наличие изменений и не следует применять для создания хэш-значений файлов, которые требуют защиты от атак или незаконного изменения.</span><span class="sxs-lookup"><span data-stu-id="021f5-151">For security reasons, MD5 and SHA1, which are no longer considered secure, should only be used for simple change validation, and should not be used to generate hash values for files that require protection from attack or tampering.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: SHA1, SHA256, SHA384, SHA512, MACTripleDES, MD5, RIPEMD160

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="021f5-152">-InputStream</span><span class="sxs-lookup"><span data-stu-id="021f5-152">-InputStream</span></span>

<span data-ttu-id="021f5-153">Задает входной поток.</span><span class="sxs-lookup"><span data-stu-id="021f5-153">Specifies the input stream.</span></span>

```yaml
Type: System.IO.Stream
Parameter Sets: Stream
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="021f5-154">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="021f5-154">-LiteralPath</span></span>

<span data-ttu-id="021f5-155">Указывает путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="021f5-155">Specifies the path to a file.</span></span> <span data-ttu-id="021f5-156">В отличие от параметра **Path** значение параметра **LiteralPath** используется в точности так, как вводится.</span><span class="sxs-lookup"><span data-stu-id="021f5-156">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="021f5-157">Никакие символы не распознаются как подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="021f5-157">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="021f5-158">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="021f5-158">If the path includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="021f5-159">Одинарные кавычки предписывает PowerShell не интерпретировать символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="021f5-159">Single quotation marks instruct PowerShell not to interpret characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="021f5-160">-Path</span><span class="sxs-lookup"><span data-stu-id="021f5-160">-Path</span></span>

<span data-ttu-id="021f5-161">Задает путь к одному или нескольким файлам в виде массива.</span><span class="sxs-lookup"><span data-stu-id="021f5-161">Specifies the path to one or more files as an array.</span></span> <span data-ttu-id="021f5-162">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="021f5-162">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="021f5-163">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="021f5-163">CommonParameters</span></span>

<span data-ttu-id="021f5-164">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="021f5-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="021f5-165">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="021f5-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="021f5-166">Входные данные</span><span class="sxs-lookup"><span data-stu-id="021f5-166">INPUTS</span></span>

### <span data-ttu-id="021f5-167">System.String</span><span class="sxs-lookup"><span data-stu-id="021f5-167">System.String</span></span>

<span data-ttu-id="021f5-168">Строку можно передать в `Get-FileHash` командлет, содержащий путь к одному или нескольким файлам.</span><span class="sxs-lookup"><span data-stu-id="021f5-168">You can pipe a string to the `Get-FileHash` cmdlet that contains a path to one or more files.</span></span>

## <span data-ttu-id="021f5-169">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="021f5-169">OUTPUTS</span></span>

### <span data-ttu-id="021f5-170">Microsoft. PowerShell. Utility. FileHash</span><span class="sxs-lookup"><span data-stu-id="021f5-170">Microsoft.Powershell.Utility.FileHash</span></span>

<span data-ttu-id="021f5-171">`Get-FileHash` Возвращает объект, представляющий путь к указанному файлу, значение вычисленного хэша и алгоритм, используемый для вычисления хэша.</span><span class="sxs-lookup"><span data-stu-id="021f5-171">`Get-FileHash` returns an object that represents the path to the specified file, the value of the computed hash, and the algorithm used to compute the hash.</span></span>

## <span data-ttu-id="021f5-172">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="021f5-172">NOTES</span></span>

## <span data-ttu-id="021f5-173">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="021f5-173">RELATED LINKS</span></span>

[<span data-ttu-id="021f5-174">Format-List</span><span class="sxs-lookup"><span data-stu-id="021f5-174">Format-List</span></span>](Format-List.md)
