---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-uiculture?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-UICulture
ms.openlocfilehash: cd5bbcae124b1c24438d2821c4da9d71a22d38a2
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209217"
---
# Get-UICulture

## Краткий обзор
Возвращает текущие параметры языка и региональных параметров пользовательского интерфейса в операционной системе.

## SYNTAX

```
Get-UICulture [<CommonParameters>]
```

## DESCRIPTION

`Get-UICulture`Командлет возвращает сведения о текущем языке и региональных параметрах пользовательского интерфейса для Windows.
Язык и региональные параметры пользовательского интерфейса определяют, какие строки текста используются для элементов пользовательского интерфейса, например меню и сообщений.

Можно также использовать `Get-Culture` командлет, который получает текущий язык и региональные параметры в системе.
Язык и региональные параметры определяют формат отображения таких элементов, как числа, валюты и даты.

## Примеры

### Пример 1. получение языка и региональных параметров пользовательского интерфейса

```powershell
Get-UICulture
```

Эта команда получает сведения о текущем языке и региональных параметрах пользовательского интерфейса.

### Пример 2. получение языка и региональных параметров пользовательского интерфейса и форматирование результатов

```powershell
Get-UICulture | Format-List *
```

Эта команда отображает значения всех свойств текущего языка и региональных параметров пользовательского интерфейса в списке.

### Пример 3. получение значения свойства Calendar

```powershell
(Get-UICulture).Calendar
```

Эта команда отображает текущие значения свойства **Calendar** текущего языка и региональных параметров пользовательского интерфейса.
Calendar — это только одно из свойств языка и региональных параметров пользовательского интерфейса.
Чтобы просмотреть все свойства, введите `Get-UICulture | Get-Member` .

### Пример 4. получение краткого шаблона даты

```powershell
(Get-UICulture).DateTimeFormat.ShortDatePattern
```

Эта команда отображает шаблон краткой даты для текущего языка и региональных параметров пользовательского интерфейса.
Чтобы просмотреть все вложенные свойства свойства **DateTimeFormat** языка и региональных параметров пользовательского интерфейса, введите `(Get-UICulture).DateTimeFormat | gm` .

## PARAMETERS

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### Нет

В этот командлет нельзя передать входные данные.

## Выходные данные

### System. Globalization. CultureInfo, Microsoft. PowerShell. Вистакултуреинфо

`Get-UICulture` Возвращает объект, представляющий текущий язык и региональные параметры пользовательского интерфейса.
В Windows PowerShell 3,0 он возвращает объект **CultureInfo** .
В Windows PowerShell 2,0 он возвращает объект **вистакултуреинфо** .

## ПРИМЕЧАНИЯ

- Можно также использовать `$PsCulture` `$PsUICulture` переменные и. `$PsCulture`Переменная хранит имя текущего языка и региональных параметров, а `$PsUICulture` переменная сохраняет имя текущего языка и региональных параметров пользовательского интерфейса.

## Связанные ссылки
