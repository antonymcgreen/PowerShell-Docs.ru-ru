---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-psbreakpoint?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSBreakpoint
ms.openlocfilehash: ae3dbbd062171a0185308bc120c1baf31a352c92
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226050"
---
# Get-PSBreakpoint

## Краткий обзор
Возвращает точки останова, установленные в рамках текущего сеанса.

## SYNTAX

### Скрипт (по умолчанию)

```
Get-PSBreakpoint [-Script <String[]>] [<CommonParameters>]
```

### Переменная

```
Get-PSBreakpoint [-Script <String[]>] -Variable <String[]> [<CommonParameters>]
```

### Get-Help

```
Get-PSBreakpoint [-Script <String[]>] -Command <String[]> [<CommonParameters>]
```

### Тип

```
Get-PSBreakpoint [-Script <String[]>] [-Type] <BreakpointType[]> [<CommonParameters>]
```

### Идентификатор

```
Get-PSBreakpoint [-Id] <Int32[]> [<CommonParameters>]
```

## DESCRIPTION

Командлет **Get-PSBreakpoint** возвращает точки останова, установленные в рамках текущего сеанса.
С помощью параметров командлета можно получить определенные точки останова.

Точка останова — это место в команде или сценарии, в котором выполнение временно приостанавливается, чтобы вы могли изучить инструкции.
**Get-PSBreakpoint** — это один из нескольких командлетов, предназначенных для отладки сценариев и команд PowerShell. Дополнительные сведения о отладчике PowerShell см. в разделе about_Debuggers.

## Примеры

### Пример 1. Получение всех точек останова для всех скриптов и функций

```
PS C:\> Get-PSBreakpoint
```

Эта команда возвращает все точки останова, установленные во всех сценариях и функциях текущего сеанса.

### Пример 2. Получение точек останова по идентификатору

```
PS C:\> Get-PSBreakpoint -Id 2
Function   :
IncrementAction     :
Enabled    :
TrueHitCount   : 0
Id         : 2
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

Эта команда возвращает точку останова с идентификатором 2.

### Пример 3. Передача идентификатора в командлет Get-PSBreakpoint по конвейеру

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Command "Increment"
PS C:\> $B.Id | Get-PSBreakpoint
```

Эти команды показывают, как получить точку останова путем передачи ее идентификатора по конвейеру в командлет **Get-PSBreakpoint**.

В первой команде используется командлет Set-PSBreakpoint для создания точки останова в функции Increment в сценарии Sample.ps1. Объект точки останова сохраняется в переменной $B.

Во второй команде используется оператор-точка (.) для получения свойства Id объекта точки останова в переменной $B. С помощью конвейерного оператора (|) идентификатор передается в командлет **Get-PSBreakpoint**.

В результате командлет **Get-PSBreakpoint** возвращает точку останова с указанным идентификатором.

### Пример 4. Возвращение точек останова в указанных файлах скриптов

```
PS C:\> Get-PSBreakpoint -Script "Sample.ps1, SupportScript.ps1"
```

Эта команда возвращает все точки останова в файлах Sample.ps1 и SupportScript.ps1.

Она не возвращает точки останова, которые могут быть установлены в других скриптах или функциях в рамках сеанса.

### Пример 5. Возвращение точек останова в указанных командлетах

```
PS C:\> Get-PSBreakpoint -Command "Read-Host, Write-Host" -Script "Sample.ps1"
```

Эта команда возвращает все точки останова, установленные в командах Read-Host или Write-Host в файле Sample.ps1.

### Пример 6. Возвращение точек останова команды в указанном файле

```
PS C:\> Get-PSBreakpoint -Type Command -Script "Sample.ps1"
```

Эта команда возвращает все точки останова команд в файле Sample.ps1.

### Пример 7. Получение точек останова по переменной

```
PS C:\> Get-PSBreakpoint -Variable "Index, Swap"
```

Эта команда возвращает точки останова, установленные для переменных $Index и $Swap в рамках текущего сеанса.

### Пример 8. Возвращение всех точек останова строк и переменных в файле

```
PS C:\> Get-PSBreakpoint -Type Line, Variable -Script "Sample.ps1"
```

Эта команда возвращает все точки останова строк и переменных в сценарии Sample.ps1.

## PARAMETERS

### -Command

Указывает массив точек останова, заданных для команд с указанными именами.
Введите имена команд, например имя командлета или функции.

```yaml
Type: System.String[]
Parameter Sets: Command
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Указывает идентификаторы точки останова, которую возвращает этот командлет.
Введите идентификаторы в виде разделенного запятыми списка.
Идентификаторы точек останова можно также передать в командлет **Get-PSBreakpoint** по конвейеру.

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Script

Указывает массив скриптов, содержащих точки останова.
Введите путь (необязательно) и имена одного или нескольких файлов скриптов.
Если путь не указан, расположением по умолчанию является текущий каталог.

```yaml
Type: System.String[]
Parameter Sets: Script, Variable, Command, Type
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Type

Указывает массив типов точек останова, которые возвращает этот командлет.
Введите один или несколько типов.
Допустимые значения для этого параметра:

- Линия
- Get-Help
- Переменная

Типы точек останова можно также передать в командлет **Get-PSBreakpoint** по конвейеру.

```yaml
Type: Microsoft.PowerShell.Commands.BreakpointType[]
Parameter Sets: Type
Aliases:
Accepted values: Line, Variable, Command

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Variable

Указывает массив точек останова, заданных для переменных с указанными именами.
Введите имена переменных без знака доллара.

```yaml
Type: System.String[]
Parameter Sets: Variable
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. Дополнительные сведения см. в разделе about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Int32, Microsoft.PowerShell.Commands.BreakpointType

Идентификаторы и типы точек останова можно передавать в командлет **Get-PSBreakpoint** по конвейеру.

## Выходные данные

### System.Management.Automation.Breakpoint

Командлет **Get-PSBreakpoint** возвращает объекты, которые представляют точки останова в рамках сеанса.

## ПРИМЕЧАНИЯ

* Можно использовать **Get-PSBreakpoint** или его псевдоним "GBP".

## Связанные ссылки

[Disable-PSBreakpoint](Disable-PSBreakpoint.md)

[Enable-PSBreakpoint](Enable-PSBreakpoint.md)

[Get-PSCallStack](Get-PSCallStack.md)

[Remove-PSBreakpoint](Remove-PSBreakpoint.md)

[Set-PSBreakpoint](Set-PSBreakpoint.md)
