---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-powershelldatafile?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PowerShellDataFile
ms.openlocfilehash: d7942abff2974064c52a8a9ac086a280959b3a63
ms.sourcegitcommit: 11880ca974fe2df308191c9f6dcdfe0b89c2dc67
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/27/2021
ms.locfileid: "99602085"
---
# Import-PowerShellDataFile

## Краткий обзор
Импортирует значения из `.PSD1` файла без вызова его содержимого.

## SYNTAX

### ByPath (по умолчанию)

```
Import-PowerShellDataFile [-Path] <String[]> [-SkipLimitCheck] [<CommonParameters>]
```

### ByLiteralPath

```
Import-PowerShellDataFile [-LiteralPath] <String[]> [-SkipLimitCheck] [<CommonParameters>]
```

## DESCRIPTION

`Import-PowerShellDataFile`Командлет безопасно импортирует пары "ключ-значение" из таблиц хэширования, определенных в `.PSD1` файле. Значения можно импортировать с помощью `Invoke-Expression` на содержимое файла.
Однако `Invoke-Expression` выполняет любой код, содержащийся в файле. Это может привести к нежелательным результатам или выполнению ненадежного кода. `Import-PowerShellDataFile` импортирует данные без вызова кода. По умолчанию существует ограничение в 500 ключей, но его можно обойти с помощью параметра **скиплимитчекк** .

## Примеры

### Пример 1. Извлечение значений из PSD1

В этом примере извлекаются пары "ключ-значение", хранящиеся в таблице хэширования, хранящейся в `Configuration.psd1` файле. `Get-Content` используется для отображения содержимого `Configuration.psd1` файла.

```powershell
Get-Content .\Configuration.psd1
$config = Import-PowerShellDataFile .\Configuration.psd1
$config.AllNodes
```

```Output
@{
    AllNodes = @(
        @{
            NodeName = 'DSC-01'
        }
        @{
            NodeName = 'DSC-02'
        }
    )
}

Name                           Value
----                           -----
NodeName                       DSC-01
NodeName                       DSC-02
```

## PARAMETERS

### -LiteralPath

Путь к импортируемому файлу. Все символы в пути рассматриваются как литеральные значения.
Подстановочные знаки не обрабатываются.

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Путь к импортируемому файлу. Подстановочные знаки допускаются, но импортируются только первый соответствующий файл.

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Скиплимитчекк

По умолчанию `Import-PowerShellDataFile` импортирует только 500 ключей из `.psd1` файла. Используйте **скиплимитчекк** для импорта более 500 ключей.

```yaml
Type: Switch
Parameter Sets: All
Aliases:

Required: False
Position: 0
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

## Выходные данные

### System.Collections.Hashtable

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Invoke-Expression](Invoke-Expression.md)

[Import-LocalizedData](Import-LocalizedData.md)
