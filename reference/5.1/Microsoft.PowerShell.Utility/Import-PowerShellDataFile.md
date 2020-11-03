---
external help file: Microsoft.PowerShell.Utility-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-powershelldatafile?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PowerShellDataFile
ms.openlocfilehash: 61e3a7f941155ccf3db84a7e9ec8d2c48b4cceea
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227594"
---
# Import-PowerShellDataFile

## Краткий обзор
Импортирует значения из `.PSD1` файла без вызова его содержимого.

## SYNTAX

### ByPath (по умолчанию)

```
Import-PowerShellDataFile [[-Path] <String[]>] [<CommonParameters>]
```

### ByLiteralPath

```
Import-PowerShellDataFile [-LiteralPath <String[]>] [<CommonParameters>]
```

## DESCRIPTION

`Import-PowerShellDataFile`Командлет безопасно импортирует пары "ключ-значение" из таблиц хэширования, определенных в `.PSD1` файле. Значения можно импортировать с помощью `Invoke-Expression` на содержимое файла.
Однако `Invoke-Expression` выполняет любой код, содержащийся в файле. Это может привести к нежелательным результатам или выполнению ненадежного кода. `Import-PowerShellDataFile` импортирует данные без вызова кода.

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
Aliases: PSPath

Required: False
Position: Named
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

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
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
