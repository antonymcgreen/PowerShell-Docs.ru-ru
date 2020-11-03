---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/disable-psbreakpoint?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSBreakpoint
ms.openlocfilehash: 80d0c77e4c54dbc7e501339f5550c87f5f1ddbed
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226030"
---
# Disable-PSBreakpoint

## Краткий обзор
Отключает точки останова в текущей консоли.

## SYNTAX

### Точка останова (по умолчанию)

```
Disable-PSBreakpoint [-PassThru] [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Идентификатор

```
Disable-PSBreakpoint [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Командлет **Disable-PSBreakpoint** отключает точки останова, что гарантирует, что они не будут достигнуты при выполнении скрипта.
С помощью этого командлета можно отключить все точки останова или указать конкретные точки, задав соответствующие объекты или их идентификаторы.

Технически этот командлет изменяет значение свойства Enabled объекта точки останова на значение False.
Для повторного включения точки останова используется командлет Enable-PSBreakpoint.
Точки останова по умолчанию включаются при их создании с помощью командлета Set-PSBreakpoint.

Точка останова — это точка в скрипте, на которой выполнение временно останавливается, чтобы можно было проверить инструкции скрипта.
**Disable-PSBreakpoint** — это один из нескольких командлетов, предназначенных для отладки скриптов PowerShell.
Дополнительные сведения о отладчике PowerShell см. в разделе about_Debuggers.

## Примеры

### Пример 1. Установка точки останова и ее отключение

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Variable "name"
PS C:\> $B | Disable-PSBreakpoint
```

Эти команды отключают только что созданную точку останова.

Первая команда использует командлет Set-PSBreakpoint для создания точки останова на переменной *Name* в скрипте Sample.ps1.
Затем она сохраняет объект точки останова в переменной $b.

Вторая команда использует командлет **Disable-PSBreakpoint** для отключения новой точки останова.
Для отправки объекта точки останова в $B в командлет **Disable-PSBreakpoint** используется оператор конвейера (|).

В результате выполнения этой команды значение свойства Enabled объекта точки останова в $B равно false.

### Пример 2. Отключение точки останова

```
PS C:\> Disable-PSBreakpoint -Id 0
```

Эта команда отключает точку останова с идентификатором 0.

### Пример 3. Создание отключенной точки останова

```
PS C:\> Disable-PSBreakpoint -Breakpoint ($B = Set-PSBreakpoint -Script "sample.ps1" -Line 5)
PS C:\> $B
```

Эта команда создает новую точку останова, которая остается отключенной, пока пользователь ее не включит.

Для отключения точки останова используется командлет **Disable-PSBreakpoint** .
Значение параметра *точки останова* — это Set-PSBreakpoint команда, которая задает новую точку останова, создает объект точки останова и сохраняет объект в переменной $B.

Параметры командлета, принимающие в качестве значений объекты, могут принять переменную, которая содержит объект, или команду, которая получает или создает объект.
В этом случае, поскольку командлет **Set-PSBreakpoint** создает объект точки останова, его можно использовать в качестве значения параметра *точки останова* .

Вторая команда отображает объект точки останова в значении переменной $B.

### Пример 4. Отключение всех точек останова в текущей консоли

```
PS C:\> Get-PSBreakpoint | Disable-PSBreakpoint
```

Эта команда отключает все точки останова в текущей консоли.
Эту команду можно сократить следующим образом: "GBP | DBP».

## PARAMETERS

### -Breakpoint

Определяет точки останова, которые нужно отключить.
Введите переменную, которая содержит объекты точек останова, или команду, которая их получает (например, Get-PSBreakpoint).
Объекты точки останова также можно передать в командлет **Disable-PSBreakpoint** .

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

Отключает точки останова с указанными идентификаторами.
Введите идентификаторы или переменную, которая их содержит.
Невозможно передать идентификаторы в командлет **Disable-PSBreakpoint**.

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

### -PassThru

Возвращает объект, представляющий включенные точки останова.
По умолчанию этот командлет не создает выходные данные.

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

Объект точки останова можно передать в командлет **Disable-PSBreakpoint** по конвейеру.

## Выходные данные

### Нет или System.Management.Automation.Breakpoint

При использовании параметра *PassThru* командлет **Disable-PSBreakpoint** возвращает объект, представляющий отключенную точку останова.
В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Enable-PSBreakpoint](Enable-PSBreakpoint.md)

[Get-PSBreakpoint](Get-PSBreakpoint.md)

[Get-PSCallStack](Get-PSCallStack.md)

[Remove-PSBreakpoint](Remove-PSBreakpoint.md)

[Set-PSBreakpoint](Set-PSBreakpoint.md)
