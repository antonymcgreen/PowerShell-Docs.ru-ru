---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-computerinfo?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ComputerInfo
ms.openlocfilehash: bb3f2b78fecd33288a0febd2882277721d9cf289
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94342694"
---
# Get-ComputerInfo

## Краткий обзор
Возвращает объединенный объект систем и свойств операционной системы.

## SYNTAX

```
Get-ComputerInfo [[-Property] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

`Get-ComputerInfo`Командлет возвращает объединенный объект систем и свойств операционной системы.
Этот командлет появился в Windows PowerShell 5,1.

## Примеры

### Пример 1. получение свойств всех компьютеров

```powershell
Get-ComputerInfo
```

Эта команда возвращает все свойства системы и операционной системы с компьютера.

### Пример 2. получение свойств операционной системы для всех компьютеров

```powershell
Get-ComputerInfo -Property "os*"
```

Эта команда возвращает все свойства операционной системы с компьютера.

## PARAMETERS

### -Property

Указывает в виде массива строк свойства компьютера, в которых отображается этот командлет.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### System.String[]

## Выходные данные

### Microsoft. PowerShell. Management. Компутеринфо

## ПРИМЕЧАНИЯ

## Связанные ссылки
