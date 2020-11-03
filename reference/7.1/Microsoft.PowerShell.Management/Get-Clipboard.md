---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-clipboard?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Clipboard
ms.openlocfilehash: e3c762f1d88efce9e7a126840e2c4348abe3648c
ms.sourcegitcommit: d757d64ea8c8af4d92596e8fbe15f2f40d48d3ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "93230693"
---
# Get-Clipboard

## Краткий обзор
Возвращает содержимое буфера обмена.

[!NOTE]
> В Linux для этого командлета требуется, `xclip` чтобы программа была в пути.

## SYNTAX

```
Get-Clipboard [-Raw] [<CommonParameters>]
```

## DESCRIPTION

`Get-Clipboard`Командлет получает содержимое буфера обмена в виде текста. Несколько строк текста возвращаются в виде массива строк, аналогичного `Get-Content` .

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

