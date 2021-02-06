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
# Get-FileHash

## Краткий обзор
Вычисляет хэш-значение для файла с помощью указанного хэш-алгоритма.

## SYNTAX

### Путь (по умолчанию)

```
Get-FileHash [-Path] <String[]> [[-Algorithm] <String>] [<CommonParameters>]
```

### LiteralPath

```
Get-FileHash [-LiteralPath] <String[]> [[-Algorithm] <String>] [<CommonParameters>]
```

### стреампараметерсет

```
Get-FileHash [-InputStream] <Stream> [[-Algorithm] <String>] [<CommonParameters>]
```

## DESCRIPTION

`Get-FileHash`Командлет выполняет вычисление хэш-значения для файла с помощью указанного хэш-алгоритма.
Хэш-значение представляет собой уникальное значение, соответствующее содержимому файла. Вместо определения содержимого файла по его имени, расширению или иному обозначению хэш назначает содержимому файла уникальное значение. Имена и расширения файлов могут изменяться без изменения содержимого файла и без изменения хэш-значения. Аналогичным образом содержимое файла может быть изменено без изменения имени или расширения. Однако при изменении даже одного символа в содержимом файла хэш-значение этого файла тоже изменяется.

Хэш-значения позволяет криптографически защищенным образом убедиться, что содержимое файла не было изменено. Хотя некоторые алгоритмы хэширования, включая MD5 и SHA1, больше не считаются безопасными для атаки, целью безопасного алгоритма хеширования является визуализация невозможности изменения содержимого файла или путем случайной или несанкционированной попытки — и сохранения одинакового хэш-значения. С помощью хэш-значений также можно определить, имеют ли два разных файла эквивалентное содержимое. Если хэш-значения двух файлов идентичны, содержимое этих файлов также идентично.

По умолчанию `Get-FileHash` командлет использует алгоритм SHA256, хотя может использоваться любой алгоритм хэширования, поддерживаемый целевой операционной системой.

## Примеры

### Пример 1. Вычисление хэш-значения для файла

В этом примере `Get-FileHash` командлет используется для вычисления хэш-значения для `/etc/apt/sources.list` файла. По умолчанию используется хэш-алгоритм **SHA256**. Выходные данные передаются в `Format-List` командлет для форматирования выходных данных в виде списка.

```powershell
Get-FileHash /etc/apt/sources.list | Format-List
```

```Output
Algorithm : SHA256
Hash      : 3CBCFDDEC145E3382D592266BE193E5BE53443138EE6AB6CA09FF20DF609E268
Path      : /etc/apt/sources.list
```

### Пример 2. Вычисление значения хэша для ISO-файла

В этом примере используется `Get-FileHash` командлет и алгоритм **SHA384** для вычисления значения хэша для ISO-файла, который администратор загрузил из Интернета. Выходные данные передаются в `Format-List` командлет для форматирования выходных данных в виде списка.

```powershell
Get-FileHash C:\Users\user1\Downloads\Contoso8_1_ENT.iso -Algorithm SHA384 | Format-List
```

```Output
Algorithm : SHA384
Hash      : 20AB1C2EE19FC96A7C66E33917D191A24E3CE9DAC99DB7C786ACCE31E559144FEAFC695C58E508E2EBBC9D3C96F21FA3
Path      : C:\Users\user1\Downloads\Contoso8_1_ENT.iso
```

### Пример 3. Вычисление хэш-значения потока

В этом примере мы получаем использование **System .NET. WebClient** для загрузки пакета со [страницы выпуска PowerShell](https://github.com/PowerShell/PowerShell/releases/tag/v6.2.4). На странице выпуск также документируется хэш SHA256 каждого файла пакета. Мы можем сравнить опубликованное хэш-значение с тем, которое вычисляется с помощью `Get-FileHash` .

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

### Пример 4. вычисление хэша строки

PowerShell не предоставляет командлет для вычисления хэша строки. Однако можно записать строку в поток и использовать параметр **InputStream** из `Get-FileHash` для получения хэш-значения.

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

## PARAMETERS

### Алгоритм

Задает криптографическую хэш-функцию, используемую для вычисления хэш-значения содержимого указанного файла или потока. Криптографическая хэш-функция имеет свойство, которое не может найти два разных файла с одинаковым хэш-значением. Хэш-функции обычно используются с цифровыми подписями и для обеспечения целостности данных. Допустимые значения для этого параметра:

- SHA1
- SHA256
- SHA384
- SHA512
- MD5

Если значение не указано или параметр пропущен, используется значение по умолчанию — SHA256.

По соображениям безопасности алгоритмы MD5 и SHA1, которые больше не считаются безопасными, следует использовать только для проверки на наличие изменений и не следует применять для создания хэш-значений файлов, которые требуют защиты от атак или незаконного изменения.

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

### -InputStream

Задает входной поток.

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

### -LiteralPath

Указывает путь к файлу. В отличие от параметра **Path** значение параметра **LiteralPath** используется в точности так, как вводится. Никакие символы не распознаются как подстановочные знаки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки предписывает PowerShell не интерпретировать символы как escape-последовательности.

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

### -Path

Задает путь к одному или нескольким файлам в виде массива. Можно использовать подстановочные знаки.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

Строку можно передать в `Get-FileHash` командлет, содержащий путь к одному или нескольким файлам.

## Выходные данные

### Microsoft. PowerShell. Utility. FileHash

`Get-FileHash` Возвращает объект, представляющий путь к указанному файлу, значение вычисленного хэша и алгоритм, используемый для вычисления хэша.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Format-List](Format-List.md)

