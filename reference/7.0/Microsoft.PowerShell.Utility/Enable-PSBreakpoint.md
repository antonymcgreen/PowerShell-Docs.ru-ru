---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/enable-psbreakpoint?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSBreakpoint
ms.openlocfilehash: 606ac3205dae254c7f1290f51f80b61e472fbece
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226413"
---
# Enable-PSBreakpoint

## Краткий обзор
Включает точки останова в текущей консоли.

## SYNTAX

### Id (по умолчанию)

```
Enable-PSBreakpoint [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Точка останова

```
Enable-PSBreakpoint [-PassThru] [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

`Enable-PSBreakpoint`Командлет повторно включает отключенные точки останова. Его можно использовать для включения всех точек останова или конкретных точек останова, предоставляя объекты или идентификаторы точек останова.

Точка останова — это точка в скрипте, в которой выполнение останавливается временно, чтобы можно было проверить состояние скрипта. Вновь созданные точки останова включаются автоматически, но могут быть отключены с помощью `Disable-PSBreakpoint` .

Технически этот командлет изменяет значение свойства **Enabled** объекта точки останова на **true**.

`Enable-PSBreakpoint` является одним из нескольких командлетов, предназначенных для отладки скриптов PowerShell. Дополнительные сведения о отладчике PowerShell см. в разделе [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).

## Примеры

### Пример 1. Включение всех точек останова

В этом примере включаются все точки останова в текущем сеансе.

```powershell
Get-PSBreakpoint | Enable-PSBreakpoint
```

С помощью псевдонимов этот пример можно сократить на `gbp | ebp` .

### Пример 2. Включение точек останова по идентификатору

Этот пример включает несколько точек останова, использующих их идентификаторы точек останова.

```powershell
Enable-PSBreakpoint -Id 0, 1, 5
```

### Пример 3. Включение отключенной точки останова

В этом примере повторно включается Отключенная точка останова.

```powershell
$B = Set-PSBreakpoint -Script "sample.ps1" -Variable Name -PassThru
$B | Enable-PSBreakpoint -PassThru
```

```Output
AccessMode : Write
Variable   : Name
Action     :
Enabled    : False
HitCount   : 0
Id         : 0
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1

AccessMode : Write
Variable   : Name
Action     :
Enabled    : True
HitCount   : 0
Id         : 0
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

`Set-PSBreakpoint` Создает точку останова в переменной **Name** в `Sample.ps1` скрипте, сохранив объект точки останова в `$B` переменной. Параметр **PassThru** отображает значение свойства **Enabled** точки останова равно **false**.

`Enable-PSBreakpoint` повторно включает точку останова. Опять же, с помощью параметра **PassThru** мы видим, что значение свойства **Enabled** равно **true**.

### Пример 4. Включение точек останова с помощью переменной

Этот пример включает набор точек останова с помощью объектов точки останова.

```powershell
$B = Get-PSBreakpoint -Id 3, 5
Enable-PSBreakpoint -Breakpoint $B
```

`Get-PSBreakpoint` Возвращает точки останова и сохраняет их в `$B` переменной. Использование параметра **точки останова** `Enable-PSBreakpoint` включает точки останова.

Этот пример эквивалентен запуску `Enable-PSBreakpoint -Id 3, 5` .

## PARAMETERS

### -Breakpoint

Задает точки останова для включения. Укажите переменную, содержащую точки останова, или команду, которая получает объекты точек останова, такие как `Get-PSBreakpoint` . Также можно передать объекты точки останова по конвейеру в `Enable-PSBreakpoint` .

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

Указывает номера **идентификаторов** точек останова, которые необходимо включить. Значение по умолчанию — все точки останова.
Укажите **ID** по номеру или в переменной. Вы не можете передавать номера **идентификаторов** в `Enable-PSBreakpoint` . Чтобы найти **идентификатор** точки останова, используйте `Get-PSBreakpoint` командлет.

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

Возвращает объект, представляющий включенную точку останова. По умолчанию этот командлет не создает никаких выходных данных.

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

Показывает, что произойдет при запуске командлета. Командлет не выполняется.

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

Объект точки останова можно передать в `Enable-PSBreakpoint` .

## Выходные данные

### Нет или System.Management.Automation.Breakpoint

При использовании параметра **PassThru** `Enable-PSBreakpoint` возвращает объект точки останова, представляющий включенную точку останова. В противном случае этот командлет не создает никаких выходных данных.

## ПРИМЕЧАНИЯ

- `Enable-PSBreakpoint`Если вы попытаетесь включить уже включенную точку останова, командлет не выдаст ошибку. Таким образом, можно включить все точки останова, не опасаясь ошибок, даже если только некоторые из них отключены.

- Точки останова включаются при их создании с помощью `Set-PSBreakpoint` командлета. Не нужно включать вновь созданные точки останова.

## Связанные ссылки

[Disable-PSBreakpoint](Disable-PSBreakpoint.md)

[Get-PSBreakpoint](Get-PSBreakpoint.md)

[Get-PSCallStack](Get-PSCallStack.md)

[Remove-PSBreakpoint](Remove-PSBreakpoint.md)

[Set-PSBreakpoint](Set-PSBreakpoint.md)
