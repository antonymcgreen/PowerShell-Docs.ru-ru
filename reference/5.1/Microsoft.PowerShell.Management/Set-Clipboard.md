---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-clipboard?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Clipboard
ms.openlocfilehash: f3230c247296d5fd907d580e719cbbbc560183a9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227898"
---
# Set-Clipboard

## Краткий обзор
Задает текущую запись в буфере обмена Windows.

## SYNTAX

### Строка (по умолчанию)

```
Set-Clipboard [-Append] [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Значение

```
Set-Clipboard [-Value] <String[]> [-Append] [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Путь

```
Set-Clipboard [-Append] -Path <String[]> [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### LiteralPath

```
Set-Clipboard [-Append] -LiteralPath <String[]> [-AsHtml] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Set-Clipboard`Командлет задает текущую запись в буфере обмена Windows.

## Примеры

### Пример 1. копирование текста в буфер обмена

```powershell
Set-Clipboard -Value "This is a test string"
```

### Пример 2. копирование содержимого каталога в буфер обмена

Эта команда копирует содержимое указанной папки в буфер обмена.

```powershell
Set-Clipboard -Path "C:\Staging\"
```

## PARAMETERS

### — Добавление

Указывает, что командлет не очищает буфер обмена и добавляет к нему содержимое.

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

### -Аштмл

Указывает, что командлет преобразует содержимое в HTML-код в буфер обмена.

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

Задает путь к элементу, который копируется в буфер обмена. В отличие от параметра **Path** , значение параметра **LiteralPath** используется строго в том виде, в котором оно указано. Никакие символы не интерпретируются как знаки подстановки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Это позволит Windows PowerShell не интерпретировать какие-либо символы как символы Escape-последовательности.

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

### -Path

Задает путь к элементу, который копируется в буфер обмена. Можно использовать подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Value

Указывает в виде массива строк содержимое для копирования в буфер обмена.

```yaml
Type: System.String[]
Parameter Sets: Value
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

### System.String[]

## Выходные данные

## ПРИМЕЧАНИЯ

В редких случаях при `Set-Clipboard` быстром выполнении с большим количеством значений, например в цикле, вы можете регулярно получать пустое значение из буфера обмена. Это можно исправить с помощью `Start-Sleep -Milliseconds 1` в цикле.

## Связанные ссылки

[Get-Clipboard](Get-Clipboard.md)
