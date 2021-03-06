---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/show-markdown?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-Markdown
ms.openlocfilehash: f4740bca33bd70d4d8eca51ed45ba6204b5d2acb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226549"
---
# Show-Markdown

## Краткий обзор
Показывает Markdown файл или строку в консоли с помощью escape-последовательностей VT100 или в браузере, использующем HTML.

## SYNTAX

### Путь (по умолчанию)

```
Show-Markdown [-Path] <String[]> [-UseBrowser] [<CommonParameters>]
```

### InputObject

```
Show-Markdown -InputObject <PSObject> [-UseBrowser] [<CommonParameters>]
```

### LiteralPath

```
Show-Markdown -LiteralPath <String[]> [-UseBrowser] [<CommonParameters>]
```

## DESCRIPTION

`Show-Markdown`Командлет используется для визуализации Markdown в удобном для чтения формате либо в терминале, либо в браузере.

`Show-Markdown` может возвращать строку, включающую escape-последовательности VT100, которые отрисовывается терминалом (если он поддерживает escape-последовательности VT100). В основном это используется для просмотра файлов Markdown в терминале. Эту строку также можно получить через, `ConvertFrom-Markdown` указав параметр **AsVT100EncodedString** .

`Show-Markdown` также имеет возможность открыть браузер и отобразить подготовленную версию Markdown. Он отображает Markdown, преобразуя его в HTML и открывая HTML-файл в браузере по умолчанию.

Вы можете изменить способ `Show-Markdown` отрисовки Markdown в терминале с помощью `Set-MarkdownOption` .

Этот командлет появился в PowerShell 6,1.

## Примеры

### Пример 1. простой пример указания пути

```powershell
Show-Markdown -Path ./README.md
```

### Пример 2. простой пример указания строки

```powershell
@"
# Show-Markdown

## Markdown

You can now interact with Markdown via PowerShell!

*stars*
__underlines__
"@ | Show-Markdown
```

### Пример 2. Открытие Markdown в браузере

```powershell
Show-Markdown -Path ./README.md -UseBrowser
```

## PARAMETERS

### -InputObject

Строка Markdown, которая будет отображаться в терминале. Если не передать поддерживаемый формат, выдаст `Show-Markdown` ошибку.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LiteralPath

Указывает путь к Markdown-файлу. В отличие от параметра Path, значение LiteralPath используется именно так, как оно введено. Никакие символы не интерпретируются как знаки подстановки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Указывает путь к файлу Markdown для подготовки к просмотру.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Усебровсер

Компилирует входные данные Markdown в формате HTML и открывает их в браузере по умолчанию.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Management.Automation.PSObject

### System.String[]

## Выходные данные

### System.String

## ПРИМЕЧАНИЯ

## Связанные ссылки

[ConvertFrom-Markdown](ConvertFrom-Markdown.md)

