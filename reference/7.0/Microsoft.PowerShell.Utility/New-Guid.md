---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Guid
ms.openlocfilehash: 0356b0f9a0792cd75828bf735e7806b5cca0daa3
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "93208977"
---
# New-Guid

## Краткий обзор
Создает глобальный уникальный идентификатор (GUID).

## SYNTAX

```
New-Guid [<CommonParameters>]
```

## DESCRIPTION

Командлет **New-Guid** создает случайный идентификатор GUID.
Если в скрипте требуется уникальный идентификатор, при необходимости можно создать идентификатор GUID.

## Примеры

### Пример 1. Создание идентификатора GUID

```
PS C:\> New-Guid
Guid
----
0352cf0f-2e7a-4aee-801d-7f27f8344c77
```

Эта команда создает случайный идентификатор GUID.
Выходные данные этого командлета можно хранить в переменных, а затем использовать их в другом месте в скрипте.

## PARAMETERS

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

## Выходные данные

### System.Guid

Этот командлет возвращает идентификатор GUID.

## ПРИМЕЧАНИЯ

## Связанные ссылки
