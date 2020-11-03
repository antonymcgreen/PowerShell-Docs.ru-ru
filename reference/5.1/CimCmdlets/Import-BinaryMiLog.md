---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/20/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/import-binarymilog?WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-BinaryMiLog
ms.openlocfilehash: ce5dd31170bc47edaa04ca3c31deab62dc4ec354
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226877"
---
# Import-BinaryMiLog

## Краткий обзор
Используется для повторного создания сохраненных объектов на основе содержимого файла экспорта.

## SYNTAX

```
Import-BinaryMiLog [-Path] <String> [<CommonParameters>]
```

## DESCRIPTION

Используйте этот командлет для повторного создания сохраненных объектов на основе содержимого файла экспорта, созданного `Export-BinaryMILog` . Этот командлет аналогичен `Import-Clixml` , за исключением того, что `Export-BinaryMILog` сохраняет полученный объект в двоичном кодированном файле.

## Примеры

### Пример 1. восстановление объектов, экспортированных в файл

```powershell
Import-BinaryMiLog -Path "Processes.bmil"
```

## PARAMETERS

### -Path

Задает путь к файлу, в котором сохраняется двоичное представление объекта. Параметр **path** поддерживает подстановочные знаки и относительные пути. Этот командлет выдает ошибку, если путь разрешается в более чем один файл.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

## Выходные данные

### System.Object

## ПРИМЕЧАНИЯ

## Связанные ссылки
