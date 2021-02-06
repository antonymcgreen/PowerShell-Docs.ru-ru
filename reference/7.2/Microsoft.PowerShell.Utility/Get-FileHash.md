---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-filehash?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-FileHash
ms.openlocfilehash: 0b31409d1da56979887e606b76ddf20532b188c1
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605281"
---
# <span data-ttu-id="de5e1-102">Get-FileHash</span><span class="sxs-lookup"><span data-stu-id="de5e1-102">Get-FileHash</span></span>

## <span data-ttu-id="de5e1-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="de5e1-103">SYNOPSIS</span></span>
<span data-ttu-id="de5e1-104">Вычисляет хэш-значение для файла с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="de5e1-104">Computes the hash value for a file by using a specified hash algorithm.</span></span>

## <span data-ttu-id="de5e1-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="de5e1-105">SYNTAX</span></span>

### <span data-ttu-id="de5e1-106">Путь (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="de5e1-106">Path (Default)</span></span>

```
Get-FileHash [-Path] <String[]> [[-Algorithm] <String>] [<CommonParameters>]
```

### <span data-ttu-id="de5e1-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="de5e1-107">LiteralPath</span></span>

```
Get-FileHash [-LiteralPath] <String[]> [[-Algorithm] <String>] [<CommonParameters>]
```

### <span data-ttu-id="de5e1-108">стреампараметерсет</span><span class="sxs-lookup"><span data-stu-id="de5e1-108">StreamParameterSet</span></span>

```
Get-FileHash [-InputStream] <Stream> [[-Algorithm] <String>] [<CommonParameters>]
```

## <span data-ttu-id="de5e1-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="de5e1-109">DESCRIPTION</span></span>

<span data-ttu-id="de5e1-110">`Get-FileHash`Командлет выполняет вычисление хэш-значения для файла с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="de5e1-110">The `Get-FileHash` cmdlet computes the hash value for a file by using a specified hash algorithm.</span></span>
<span data-ttu-id="de5e1-111">Хэш-значение представляет собой уникальное значение, соответствующее содержимому файла.</span><span class="sxs-lookup"><span data-stu-id="de5e1-111">A hash value is a unique value that corresponds to the content of the file.</span></span> <span data-ttu-id="de5e1-112">Вместо определения содержимого файла по его имени, расширению или иному обозначению хэш назначает содержимому файла уникальное значение.</span><span class="sxs-lookup"><span data-stu-id="de5e1-112">Rather than identifying the contents of a file by its file name, extension, or other designation, a hash assigns a unique value to the contents of a file.</span></span> <span data-ttu-id="de5e1-113">Имена и расширения файлов могут изменяться без изменения содержимого файла и без изменения хэш-значения.</span><span class="sxs-lookup"><span data-stu-id="de5e1-113">File names and extensions can be changed without altering the content of the file, and without changing the hash value.</span></span> <span data-ttu-id="de5e1-114">Аналогичным образом содержимое файла может быть изменено без изменения имени или расширения.</span><span class="sxs-lookup"><span data-stu-id="de5e1-114">Similarly, the file's content can be changed without changing the name or extension.</span></span> <span data-ttu-id="de5e1-115">Однако при изменении даже одного символа в содержимом файла хэш-значение этого файла тоже изменяется.</span><span class="sxs-lookup"><span data-stu-id="de5e1-115">However, changing even a single character in the contents of a file changes the hash value of the file.</span></span>

<span data-ttu-id="de5e1-116">Хэш-значения позволяет криптографически защищенным образом убедиться, что содержимое файла не было изменено.</span><span class="sxs-lookup"><span data-stu-id="de5e1-116">The purpose of hash values is to provide a cryptographically-secure way to verify that the contents of a file have not been changed.</span></span> <span data-ttu-id="de5e1-117">Хотя некоторые алгоритмы хэширования, включая MD5 и SHA1, больше не считаются безопасными для атаки, целью безопасного алгоритма хеширования является визуализация невозможности изменения содержимого файла или путем случайной или несанкционированной попытки — и сохранения одинакового хэш-значения.</span><span class="sxs-lookup"><span data-stu-id="de5e1-117">While some hash algorithms, including MD5 and SHA1, are no longer considered secure against attack, the goal of a secure hash algorithm is to render it impossible to change the contents of a file -- either by accident, or by malicious or unauthorized attempt -- and maintain the same hash value.</span></span> <span data-ttu-id="de5e1-118">С помощью хэш-значений также можно определить, имеют ли два разных файла эквивалентное содержимое.</span><span class="sxs-lookup"><span data-stu-id="de5e1-118">You can also use hash values to determine if two different files have exactly the same content.</span></span> <span data-ttu-id="de5e1-119">Если хэш-значения двух файлов идентичны, содержимое этих файлов также идентично.</span><span class="sxs-lookup"><span data-stu-id="de5e1-119">If the hash values of two files are identical, the contents of the files are also identical.</span></span>

<span data-ttu-id="de5e1-120">По умолчанию `Get-FileHash` командлет использует алгоритм SHA256, хотя может использоваться любой алгоритм хэширования, поддерживаемый целевой операционной системой.</span><span class="sxs-lookup"><span data-stu-id="de5e1-120">By default, the `Get-FileHash` cmdlet uses the SHA256 algorithm, although any hash algorithm that is supported by the target operating system can be used.</span></span>

## <span data-ttu-id="de5e1-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="de5e1-121">EXAMPLES</span></span>

### <span data-ttu-id="de5e1-122">Пример 1. Вычисление хэш-значения для файла</span><span class="sxs-lookup"><span data-stu-id="de5e1-122">Example 1: Compute the hash value for a file</span></span>

<span data-ttu-id="de5e1-123">В этом примере `Get-FileHash` командлет используется для вычисления хэш-значения для `/etc/apt/sources.list` файла.</span><span class="sxs-lookup"><span data-stu-id="de5e1-123">This example uses the `Get-FileHash` cmdlet to compute the hash value for the `/etc/apt/sources.list` file.</span></span> <span data-ttu-id="de5e1-124">По умолчанию используется хэш-алгоритм **SHA256**.</span><span class="sxs-lookup"><span data-stu-id="de5e1-124">The hash algorithm used is the default, **SHA256**.</span></span> <span data-ttu-id="de5e1-125">Выходные данные передаются в `Format-List` командлет для форматирования выходных данных в виде списка.</span><span class="sxs-lookup"><span data-stu-id="de5e1-125">The output is piped to the `Format-List` cmdlet to format the output as a list.</span></span>

```powershell
Get-FileHash /etc/apt/sources.list | Format-List
```

```Output
Algorithm : SHA256
Hash      : 3CBCFDDEC145E3382D592266BE193E5BE53443138EE6AB6CA09FF20DF609E268
Path      : /etc/apt/sources.list
```

### <span data-ttu-id="de5e1-126">Пример 2. Вычисление значения хэша для ISO-файла</span><span class="sxs-lookup"><span data-stu-id="de5e1-126">Example 2: Compute the hash value for an ISO file</span></span>

<span data-ttu-id="de5e1-127">В этом примере используется `Get-FileHash` командлет и алгоритм **SHA384** для вычисления значения хэша для ISO-файла, который администратор загрузил из Интернета.</span><span class="sxs-lookup"><span data-stu-id="de5e1-127">This example uses the `Get-FileHash` cmdlet and the **SHA384** algorithm to compute the hash value for an ISO file that an administrator has downloaded from the internet.</span></span> <span data-ttu-id="de5e1-128">Выходные данные передаются в `Format-List` командлет для форматирования выходных данных в виде списка.</span><span class="sxs-lookup"><span data-stu-id="de5e1-128">The output is piped to the `Format-List` cmdlet to format the output as a list.</span></span>

```powershell
Get-FileHash C:\Users\user1\Downloads\Contoso8_1_ENT.iso -Algorithm SHA384 | Format-List
```

```Output
Algorithm : SHA384
Hash      : 20AB1C2EE19FC96A7C66E33917D191A24E3CE9DAC99DB7C786ACCE31E559144FEAFC695C58E508E2EBBC9D3C96F21FA3
Path      : C:\Users\user1\Downloads\Contoso8_1_ENT.iso
```

### <span data-ttu-id="de5e1-129">Пример 3. Вычисление хэш-значения потока</span><span class="sxs-lookup"><span data-stu-id="de5e1-129">Example 3: Compute the hash value of a stream</span></span>

<span data-ttu-id="de5e1-130">В этом примере мы получаем использование **System .NET. WebClient** для загрузки пакета со [страницы выпуска PowerShell](https://github.com/PowerShell/PowerShell/releases/tag/v6.2.4).</span><span class="sxs-lookup"><span data-stu-id="de5e1-130">For this example, we get are using **System.Net.WebClient** to download a package from the [Powershell release page](https://github.com/PowerShell/PowerShell/releases/tag/v6.2.4).</span></span> <span data-ttu-id="de5e1-131">На странице выпуск также документируется хэш SHA256 каждого файла пакета.</span><span class="sxs-lookup"><span data-stu-id="de5e1-131">The release page also documents the SHA256 hash of each package file.</span></span> <span data-ttu-id="de5e1-132">Мы можем сравнить опубликованное хэш-значение с тем, которое вычисляется с помощью `Get-FileHash` .</span><span class="sxs-lookup"><span data-stu-id="de5e1-132">We can compare the published hash value with the one we calculate with `Get-FileHash`.</span></span>

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

### <span data-ttu-id="de5e1-133">Пример 4. вычисление хэша строки</span><span class="sxs-lookup"><span data-stu-id="de5e1-133">Example 4: Compute the hash of a string</span></span>

<span data-ttu-id="de5e1-134">PowerShell не предоставляет командлет для вычисления хэша строки.</span><span class="sxs-lookup"><span data-stu-id="de5e1-134">PowerShell does not provide a cmdlet to compute the hash of a string.</span></span> <span data-ttu-id="de5e1-135">Однако можно записать строку в поток и использовать параметр **InputStream** из `Get-FileHash` для получения хэш-значения.</span><span class="sxs-lookup"><span data-stu-id="de5e1-135">However, you can write a string to a stream and use the **InputStream** parameter of `Get-FileHash` to get the hash value.</span></span>

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

## <span data-ttu-id="de5e1-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="de5e1-136">PARAMETERS</span></span>

### <span data-ttu-id="de5e1-137">Алгоритм</span><span class="sxs-lookup"><span data-stu-id="de5e1-137">-Algorithm</span></span>

<span data-ttu-id="de5e1-138">Задает криптографическую хэш-функцию, используемую для вычисления хэш-значения содержимого указанного файла или потока.</span><span class="sxs-lookup"><span data-stu-id="de5e1-138">Specifies the cryptographic hash function to use for computing the hash value of the contents of the specified file or stream.</span></span> <span data-ttu-id="de5e1-139">Криптографическая хэш-функция имеет свойство, которое не может найти два разных файла с одинаковым хэш-значением.</span><span class="sxs-lookup"><span data-stu-id="de5e1-139">A cryptographic hash function has the property that it is infeasible to find two different files with the same hash value.</span></span> <span data-ttu-id="de5e1-140">Хэш-функции обычно используются с цифровыми подписями и для обеспечения целостности данных.</span><span class="sxs-lookup"><span data-stu-id="de5e1-140">Hash functions are commonly used with digital signatures and for data integrity.</span></span> <span data-ttu-id="de5e1-141">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="de5e1-141">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="de5e1-142">SHA1</span><span class="sxs-lookup"><span data-stu-id="de5e1-142">SHA1</span></span>
- <span data-ttu-id="de5e1-143">SHA256</span><span class="sxs-lookup"><span data-stu-id="de5e1-143">SHA256</span></span>
- <span data-ttu-id="de5e1-144">SHA384</span><span class="sxs-lookup"><span data-stu-id="de5e1-144">SHA384</span></span>
- <span data-ttu-id="de5e1-145">SHA512</span><span class="sxs-lookup"><span data-stu-id="de5e1-145">SHA512</span></span>
- <span data-ttu-id="de5e1-146">MD5</span><span class="sxs-lookup"><span data-stu-id="de5e1-146">MD5</span></span>

<span data-ttu-id="de5e1-147">Если значение не указано или параметр пропущен, используется значение по умолчанию — SHA256.</span><span class="sxs-lookup"><span data-stu-id="de5e1-147">If no value is specified, or if the parameter is omitted, the default value is SHA256.</span></span>

<span data-ttu-id="de5e1-148">По соображениям безопасности алгоритмы MD5 и SHA1, которые больше не считаются безопасными, следует использовать только для проверки на наличие изменений и не следует применять для создания хэш-значений файлов, которые требуют защиты от атак или незаконного изменения.</span><span class="sxs-lookup"><span data-stu-id="de5e1-148">For security reasons, MD5 and SHA1, which are no longer considered secure, should only be used for simple change validation, and should not be used to generate hash values for files that require protection from attack or tampering.</span></span>

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

### <span data-ttu-id="de5e1-149">-InputStream</span><span class="sxs-lookup"><span data-stu-id="de5e1-149">-InputStream</span></span>

<span data-ttu-id="de5e1-150">Задает входной поток.</span><span class="sxs-lookup"><span data-stu-id="de5e1-150">Specifies the input stream.</span></span>

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

### <span data-ttu-id="de5e1-151">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="de5e1-151">-LiteralPath</span></span>

<span data-ttu-id="de5e1-152">Указывает путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="de5e1-152">Specifies the path to a file.</span></span> <span data-ttu-id="de5e1-153">В отличие от параметра **Path** значение параметра **LiteralPath** используется в точности так, как вводится.</span><span class="sxs-lookup"><span data-stu-id="de5e1-153">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="de5e1-154">Никакие символы не распознаются как подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="de5e1-154">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="de5e1-155">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="de5e1-155">If the path includes escape characters, enclose the path in single quotation marks.</span></span> <span data-ttu-id="de5e1-156">Одинарные кавычки предписывает PowerShell не интерпретировать символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="de5e1-156">Single quotation marks instruct PowerShell not to interpret characters as escape sequences.</span></span>

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

### <span data-ttu-id="de5e1-157">-Path</span><span class="sxs-lookup"><span data-stu-id="de5e1-157">-Path</span></span>

<span data-ttu-id="de5e1-158">Задает путь к одному или нескольким файлам в виде массива.</span><span class="sxs-lookup"><span data-stu-id="de5e1-158">Specifies the path to one or more files as an array.</span></span> <span data-ttu-id="de5e1-159">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="de5e1-159">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="de5e1-160">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="de5e1-160">CommonParameters</span></span>

<span data-ttu-id="de5e1-161">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="de5e1-161">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="de5e1-162">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="de5e1-162">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="de5e1-163">Входные данные</span><span class="sxs-lookup"><span data-stu-id="de5e1-163">INPUTS</span></span>

### <span data-ttu-id="de5e1-164">System.String</span><span class="sxs-lookup"><span data-stu-id="de5e1-164">System.String</span></span>

<span data-ttu-id="de5e1-165">Строку можно передать в `Get-FileHash` командлет, содержащий путь к одному или нескольким файлам.</span><span class="sxs-lookup"><span data-stu-id="de5e1-165">You can pipe a string to the `Get-FileHash` cmdlet that contains a path to one or more files.</span></span>

## <span data-ttu-id="de5e1-166">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="de5e1-166">OUTPUTS</span></span>

### <span data-ttu-id="de5e1-167">Microsoft. PowerShell. Utility. FileHash</span><span class="sxs-lookup"><span data-stu-id="de5e1-167">Microsoft.Powershell.Utility.FileHash</span></span>

<span data-ttu-id="de5e1-168">`Get-FileHash` Возвращает объект, представляющий путь к указанному файлу, значение вычисленного хэша и алгоритм, используемый для вычисления хэша.</span><span class="sxs-lookup"><span data-stu-id="de5e1-168">`Get-FileHash` returns an object that represents the path to the specified file, the value of the computed hash, and the algorithm used to compute the hash.</span></span>

## <span data-ttu-id="de5e1-169">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="de5e1-169">NOTES</span></span>

## <span data-ttu-id="de5e1-170">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="de5e1-170">RELATED LINKS</span></span>

[<span data-ttu-id="de5e1-171">Format-List</span><span class="sxs-lookup"><span data-stu-id="de5e1-171">Format-List</span></span>](Format-List.md)

