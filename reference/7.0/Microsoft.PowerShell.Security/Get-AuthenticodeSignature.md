---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 04/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-authenticodesignature?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AuthenticodeSignature
ms.openlocfilehash: 6e205efe91f453d00f29a95f418eff89063acea8
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347148"
---
# Get-AuthenticodeSignature

## Краткий обзор
Возвращает сведения о подписи Authenticode для файла.

## SYNTAX

### ByPath (по умолчанию)

```
Get-AuthenticodeSignature [-FilePath] <String[]> [<CommonParameters>]
```

### ByLiteralPath

```
Get-AuthenticodeSignature -LiteralPath <String[]> [<CommonParameters>]
```

### биконтент

```
Get-AuthenticodeSignature -SourcePathOrExtension <String[]> -Content <Byte[]> [<CommonParameters>]
```

## DESCRIPTION

`Get-AuthenticodeSignature`Командлет получает сведения о подписи Authenticode для файла или содержимого файла в виде массива байтов. Если файл не подписан, сведения возвращаются, но поля будут пусты.

## Примеры

### Пример 1. получение подписи Authenticode для файла

```powershell
Get-AuthenticodeSignature -FilePath "C:\Test\NewScript.ps1"
```

Эта команда возвращает сведения о подписи Authenticode в файле NewScript.ps1. Для указания файла используется параметр **FilePath** .

### Пример 2. получение подписи Authenticode для нескольких файлов

```powershell
Get-AuthenticodeSignature test.ps1, test1.ps1, sign-file.ps1, makexml.ps1
```

Эта команда возвращает сведения о подписи Authenticode для четырех файлов, перечисленных в командной строке. В этом примере имя параметра **FilePath** , которое является необязательным, опускается.

### Пример 3. Получение допустимых подписей Authenticode для нескольких файлов

```powershell
Get-ChildItem $PSHOME\*.* | ForEach-object {Get-AuthenticodeSignature $_} | Where-Object {$_.status -eq "Valid"}
```

Эта команда выводит список всех файлов в `$PSHOME` каталоге с действительной подписью Authenticode. `$PSHOME`Автоматическая переменная содержит путь к каталогу установки PowerShell.

Команда использует `Get-ChildItem` командлет для получения файлов в `$PSHOME` каталоге. Он использует шаблон *.* для исключения каталогов (хотя он также исключает файлы без точки в имени файла).

Команда использует оператор конвейера ( `|` ) для отправки файлов в `$PSHOME` `ForEach-Object` командлет, где `Get-AuthenticodeSignature` вызывается для каждого файла.

Результаты `Get-AuthenticodeSignature` команды отправляются в `Where-Object` команду, которая выбирает только объекты сигнатуры с состоянием допустимо.

### Пример 4. получение подписи Authenticode для содержимого файла, указанного в виде массива байтов

```powershell
Get-AuthenticodeSignature -Content (Get-Content foo.ps1 -AsByteStream) -SourcePathorExtension ps1
```

Эта команда возвращает сведения о подписи Authenticode для содержимого файла. В этом примере расширение файла указывается вместе с содержимым файла.

## PARAMETERS

### — Содержимое

Содержимое файла в виде массива байтов, для которого получена подпись Authenticode. Этот параметр должен использоваться с параметром **саурцепасорекстенсион** . Содержимое файла должно быть в формате Unicode (UTF-16LE).

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

### -FilePath

Указывает путь к файлу для проверки. Подстановочные знаки допускаются, но путь при этом должен указывать на один файл. При указании значения для этого параметра необязательно вводить **FilePath** в командной строке.

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

### -LiteralPath

Указывает путь к анализируемому файлу. В отличие от **FilePath** значение параметра **LiteralPath** используется именно в том виде, в котором оно вводится. Никакие символы не интерпретируются как знаки подстановки. Если путь содержит escape-символ, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать символы как escape-символы.

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

### -Саурцепасорекстенсион

Путь к файлу или типу файла содержимого, для которого получена подпись Authenticode. Этот параметр используется с **содержимым** , где содержимое файла передается как массив байтов.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### System.String

Строку, содержащую путь к файлу, можно передать по конвейеру `Get-AuthenticodeSignature` .

## Выходные данные

### System. Management. Automation. Signature

`Get-AuthenticodeSignature` Возвращает объект подписи для каждой сигнатуры, которую он получает.

## ПРИМЕЧАНИЯ

Этот командлет доступен только на платформах Windows.

Сведения о подписях Authenticode в PowerShell см. в разделе [about_Signing](../Microsoft.PowerShell.Core/About/about_Signing.md).

## Связанные ссылки

[Get-ExecutionPolicy](Get-ExecutionPolicy.md)

[Set-AuthenticodeSignature](Set-AuthenticodeSignature.md)

[Set-ExecutionPolicy](Set-ExecutionPolicy.md)

[about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[about_Signing](../Microsoft.PowerShell.Core/About/about_Signing.md)
