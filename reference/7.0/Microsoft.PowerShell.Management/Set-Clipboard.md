---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/09/2019
online version: https://go.microsoft.com/fwlink/?linkid=526220
schema: 2.0.0
title: Set-Clipboard
ms.openlocfilehash: 271d9191a0968b03b1e7ec3d283eacc36e633516
ms.sourcegitcommit: fcf7bd222f5ee3fdbe21ffddcae47050cffe7e42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "93239805"
---
# Set-Clipboard

## Краткий обзор
Задает содержимое буфера обмена.

## SYNTAX

```
Set-Clipboard [-Value] <string[]> [-Append] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Set-Clipboard`Командлет задает содержимое буфера обмена.

> [!NOTE]
> В Linux для этого командлета требуется, `xclip` чтобы программа была в пути.

## Примеры

### Пример 1. копирование текста в буфер обмена

```powershell
Set-Clipboard -Value "This is a test string"
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

### -Value

Строковые значения, которые необходимо добавить в буфер обмена.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
