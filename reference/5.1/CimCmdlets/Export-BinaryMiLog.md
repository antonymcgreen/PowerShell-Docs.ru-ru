---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/20/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/export-binarymilog?WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-BinaryMiLog
ms.openlocfilehash: cf03ad884121c6cf8cf65cdb791cbdc4e587c3b9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226893"
---
# Export-BinaryMiLog

## Краткий обзор
Создает представление объекта или объектов в двоичном кодировке и сохраняет его в файле.

## SYNTAX

```
Export-BinaryMiLog [-InputObject <CimInstance>] [-Path] <String> [<CommonParameters>]
```

## DESCRIPTION

`Export-BinaryMILog`Командлет создает двоичное представление объекта или объектов и сохраняет его в файле. Затем можно использовать `Import-BinaryMiLog` командлет для повторного создания сохраненного объекта на основе содержимого этого файла.

Этот командлет аналогичен `Import-Clixml` , за исключением того, что `Export-BinaryMILog` сохраняет полученный объект в двоичном кодированном файле.

## Примеры

### Пример 1. Создание двоичного представления Циминстанцес

```powershell
Get-CimInstance Win32_Process | Export-BinaryMiLog -Path "Processes.bmil"
```

Эта команда экспортирует **Циминстанцес** в файл журнала ДВОИЧной MI, заданный параметром path. См. пример для Import-BinaryMiLog, чтобы узнать, как повторно создать **Циминстанцес** путем импорта этого файла.

## PARAMETERS

### -InputObject

Задает входные данные для этого командлета. Можно использовать данный параметр или передавать входные данные в этот командлет.

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

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

### Microsoft.Management.Infrastructure.CimInstance

## Выходные данные

### System.Object

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Get-CimInstance](get-ciminstance.md)

[Import-BinaryMiLog](import-binarymilog.md)

[Import-Clixml](../microsoft.powershell.utility/import-clixml.md)
