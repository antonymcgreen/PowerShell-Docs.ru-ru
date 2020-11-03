---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-tracesource?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TraceSource
ms.openlocfilehash: 024fa690ff9ddd4eae2d7fd6203e83f56fef6cd7
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226038"
---
# Get-TraceSource

## Краткий обзор
Возвращает компоненты PowerShell, инструментированные для трассировки.

## SYNTAX

```
Get-TraceSource [[-Name] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

Командлет **Get-TraceSource** получает источники трассировки для компонентов PowerShell, которые используются в данный момент.
Данные можно использовать для определения компонентов PowerShell, которые можно отслеживать.
При трассировке компонент создает подробные сообщения о каждом шаге внутренней обработки.
Разработчики используют данные трассировки для мониторинга потока данных, выполнения программ и ошибок.

Командлеты трассировки были разработаны для разработчиков PowerShell, но они доступны всем пользователям.

## Примеры

### Пример 1. получение источников трассировки по имени

```
PS C:\> Get-TraceSource -Name "*provider*"
```

Эта команда возвращает все источники трассировки с именами, которые включают в себя поставщик.

### Пример 2. получение всех источников трассировки

```
PS C:\> Get-TraceSource
```

Эта команда возвращает все компоненты PowerShell, которые можно отслеживать.

## PARAMETERS

### -Name

Указывает получаемые источники трассировки.
Разрешено использовать подстановочные знаки.
*Имя параметра является* необязательным.

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

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

Строку, содержащую имя источника трассировки, можно передать в командлет **Get-TraceSource** по конвейеру.

## Выходные данные

### System. Management. Automation. Пстрацесаурце

Командлет **Get-TraceSource** возвращает объекты, представляющие источники трассировки.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Set-TraceSource](Set-TraceSource.md)

[Trace-Command](Trace-Command.md)
