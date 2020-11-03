---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-psbreakpoint?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSBreakpoint
ms.openlocfilehash: a20b9114858a83de2b334340500efcf92e5d258d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228041"
---
# Remove-PSBreakpoint

## Краткий обзор
Удаляет из текущей консоли точки останова.

## SYNTAX

### Точка останова (по умолчанию)

```
Remove-PSBreakpoint [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Идентификатор

```
Remove-PSBreakpoint [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Remove-PSBreakpoint** удаляет точку останова.
Введите объект или идентификатор точки останова.

При удалении точки останова объект точки останова становится недоступным и перестает функционировать.
Если объект точки останова сохранен в переменную, ссылка остается, но точка останова не работает.

**Remove-PSBreakpoint** — это один из нескольких командлетов, предназначенных для отладки скриптов PowerShell.
Дополнительные сведения о отладчике PowerShell см. в разделе about_Debuggers.

## Примеры

### Пример 1. Удаление всех точек останова

```
PS C:\> Get-PSBreakpoint | Remove-PSBreakpoint
```

Эта команда удаляет все точки останова в текущей консоли.

### Пример 2. Удаление указанной точки останова

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Variable "Name"
PS C:\> $B | Remove-PSBreakpoint
```

Эта команда удаляет точку останова.

Первая команда использует командлет Set-PSBreakpoint для создания точки останова на переменной Name в скрипте Sample.ps1.
Затем она сохраняет объект точки останова в переменной $b.

Вторая команда использует командлет **Remove-PSBreakpoint** для удаления новой точки останова.
Он использует оператор конвейера (|) для отправки объекта точки останова в переменную $B в командлет **Remove-PSBreakpoint** .

В результате выполнения этой команды запущенный скрипт выполняется до завершения без остановки.
Кроме того, командлет **Get-PSBreakpoint** не возвращает эту точку останова.

### Пример 3. Удаление точки останова по ИДЕНТИФИКАТОРу

```
PS C:\> Remove-PSBreakpoint -Id 2
```

Эта команда удаляет точку останова с идентификатором 2.

### Пример 4. Удаление всех точек останова с помощью функции

```
PS C:\> function del-psb { get-psbreakpoint | remove-psbreakpoint }
```

Эта простая функция удаляет все точки останова в текущей консоли.
С помощью командлета Get-PSBreakpoint она получает точки останова.
Затем он использует оператор конвейера (|) для отправки точек останова в командлет **Remove-PSBreakpoint** , который удаляет их.

В результате `del-psb` вместо более длинной команды можно ввести.

Чтобы сохранить функцию, добавьте ее в профиль PowerShell.

## PARAMETERS

### -Breakpoint
Определяет точки останова для удаления.
Введите переменную, которая содержит объекты точки останова, или команду, которая получает объекты точки останова, такие как команда **Get-PSBreakpoint** .
Кроме того, можно передать объекты точки останова в командлет **Remove-PSBreakpoint** .

```yaml
Type: System.Management.Automation.Breakpoint[]
Parameter Sets: Breakpoint
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Id
Указывает идентификаторы точек останова, для которых этот командлет удаляет точки останова.

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Показывает, что произойдет при запуске командлета.
Командлет не выполняется.

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

### System.Management.Automation.Breakpoint
Объекты точки останова можно передать в командлет **Remove-PSBreakpoint** по конвейеру.

## Выходные данные

### Нет
Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Disable-PSBreakpoint](Disable-PSBreakpoint.md)

[Enable-PSBreakpoint](Enable-PSBreakpoint.md)

[Get-PSBreakpoint](Get-PSBreakpoint.md)

[Get-PSCallStack](Get-PSCallStack.md)

[Set-PSBreakpoint](Set-PSBreakpoint.md)

