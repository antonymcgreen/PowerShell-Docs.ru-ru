---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-clipboard?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Clipboard
ms.openlocfilehash: da1df360d7c471d925bd2f57f5258ecb2d60e631
ms.sourcegitcommit: fcf7bd222f5ee3fdbe21ffddcae47050cffe7e42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "93239985"
---
# Get-Clipboard

## Краткий обзор
Возвращает содержимое буфера обмена.

## SYNTAX

```
Get-Clipboard [-Raw] [<CommonParameters>]
```

## DESCRIPTION

`Get-Clipboard`Командлет получает содержимое буфера обмена в виде текста. Несколько строк текста возвращаются в виде массива строк, аналогичного `Get-Content` .

> [!NOTE]
> В Linux для этого командлета требуется, `xclip` чтобы программа была в пути.

## Примеры

### Пример 1. получение содержимого буфера обмена и его отображение в командной строке

В этом примере мы скопировали текст "Hello" в буфер обмена.

```powershell
Get-Clipboard
```

```Output
hello
```

## PARAMETERS

### -RAW

Возвращает все содержимое буфера обмена. Многострочный текст возвращается в виде одной многострочной строки, а не массива строк.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

## Выходные данные

### System.String

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Set-Clipboard](Set-Clipboard.md)

