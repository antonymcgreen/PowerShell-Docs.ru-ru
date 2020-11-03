---
external help file: Microsoft.PowerShell.Archive-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Archive
ms.date: 07/17/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.archive/expand-archive?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Expand-Archive
ms.openlocfilehash: 41d571747a9b81cafff8c0ca20d5121163ece452
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "93229702"
---
# Expand-Archive

## Краткий обзор
Извлекает файлы из указанного ZIP-файла архива.

## SYNTAX

### Путь (по умолчанию)

```
Expand-Archive [-Path] <String> [[-DestinationPath] <String>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### LiteralPath

```
Expand-Archive -LiteralPath <String> [[-DestinationPath] <String>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

`Expand-Archive`Командлет извлекает файлы из указанного ZIP-файла архива в указанную папку назначения. Файл архива позволяет упаковать и при необходимости сжать несколько файлов в один сжатый ZIP-файл для упрощения распространения и хранения.

## Примеры

### Пример 1. Извлечение содержимого архива

В этом примере содержимое существующего файла архива извлекается в папку, указанную параметром **DestinationPath** .

```powershell
Expand-Archive -LiteralPath 'C:\Archives\Draft[v1].Zip' -DestinationPath C:\Reference
```

В этом примере используется параметр **LiteralPath** , так как имя файла содержит символы, которые можно интерпретировать как подстановочные знаки.

### Пример 2. Извлечение содержимого архива в текущей папке

Этот пример извлекает содержимое существующего файла архива в текущей папке в папку, указанную параметром **DestinationPath** .

```powershell
Expand-Archive -Path Draftv2.Zip -DestinationPath C:\Reference
```

## PARAMETERS

### -DestinationPath

По умолчанию `Expand-Archive` создает папку в текущем расположении с тем же именем, что и у ZIP-файла. Параметр позволяет указать путь к другой папке. Если целевая папка не существует, она будет создана.

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

### -Force

Принудительное выполнение команды без запроса на подтверждение пользователем.

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

### -LiteralPath

Определяет путь к файлу архива. В отличие от параметра **Path** , значение **LiteralPath** используется именно так, как оно введено. Подстановочные знаки не поддерживаются. Если путь содержит escape-символы, заключите каждый escape-символ в одинарные кавычки, чтобы заставить PowerShell не интерпретировать какие-либо символы как escape-последовательности.

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

### -Path

Указывает путь к файлу архива.

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

### -Confirm

Запрос подтверждения перед выполнением командлета.

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

### -WhatIf

Показывает, что произойдет при запуске командлета. Командлет не выполняется.

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

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

Строку, содержащую путь, можно передать по конвейеру в существующий файл архива.

## Выходные данные

### Нет

## ПРИМЕЧАНИЯ

В [спецификации ZIP-файла](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) не указан стандартный способ кодирования имен файлов, содержащих символы, не входящие в набор ASCII. `Compress-Archive`Командлет использует кодировку UTF-8. Другие средства архивирования ZIP могут использовать другую схему кодирования. При извлечении файлов с именами, которые не хранятся в кодировке UTF-8, `Expand-Archive` использует необработанное значение, найденное в архиве. Это может привести к тому, что имя файла будет отличаться от исходного имени файла, хранящегося в архиве.

## Связанные ссылки

[Compress-Archive](compress-archive.md)
