---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/24/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/measure-command?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Measure-Command
ms.openlocfilehash: 0cf5ac4df506b5882dd2dbf87ce6ad05845e0c94
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227130"
---
# Measure-Command

## Краткий обзор
Измеряет время выполнения блоков скриптов и командлетов.

## SYNTAX

```
Measure-Command [-InputObject <PSObject>] [-Expression] <ScriptBlock> [<CommonParameters>]
```

## DESCRIPTION

`Measure-Command`Командлет выполняет блок скрипта или командлет внутренне, время выполнения операции и возвращает время выполнения.

> [!NOTE]
> Блоки скриптов, выполняемые, `Measure-Command` выполняются в текущей области, а не в дочерней области.

## Примеры

### Пример 1. Измерение команды

В этом примере измеряется время, затрачиваемое на выполнение `Get-EventLog` команды, получающей события в журнале событий Windows PowerShell.

```powershell
Measure-Command { Get-EventLog "windows powershell" }
```

### Пример 2. Сравнение двух выходных данных из Measure-Command

Первая команда измеряет время, затрачиваемое на обработку рекурсивной `Get-ChildItem` команды, которая использует параметр **path** для получения только `.txt` файлов в `C:\Windows` каталоге и его подкаталогах.

Вторая команда измеряет время, затрачиваемое на обработку рекурсивной `Get-ChildItem` команды, использующей параметр, зависящий от поставщика.

Эти команды показывают значение с помощью фильтра, зависящего от поставщика, в командах PowerShell.

```powershell
Measure-Command { Get-ChildItem -Path C:\Windows\*.txt -Recurse }
```

```Output
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 8
Milliseconds      : 618
Ticks             : 86182763
TotalDays         : 9.9748568287037E-05
TotalHours        : 0.00239396563888889
TotalMinutes      : 0.143637938333333
TotalSeconds      : 8.6182763
TotalMilliseconds : 8618.2763
```

```powershell
Measure-Command {Get-ChildItem C:\Windows -Filter "*.txt" -Recurse}
```

```Output
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 1
Milliseconds      : 140
Ticks             : 11409189
TotalDays         : 1.32050798611111E-05
TotalHours        : 0.000316921916666667
TotalMinutes      : 0.019015315
TotalSeconds      : 1.1409189
TotalMilliseconds : 1140.9189
```

### Пример 3. входные данные конвейера в Measure-Command

Объекты, `Measure-Command` передаваемые в, доступны блоку скрипта, который передается в параметр **Expression** . Блок скрипта выполняется один раз для каждого объекта в конвейере.

```powershell
# Perform a simple operation to demonstrate the InputObject parameter
# Note that no output is displayed.
10, 20, 50 | Measure-Command -Expression { for ($i=0; $i -lt $_ i++) {$i} }
```

```Output
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 0
Milliseconds      : 12
Ticks             : 122672
TotalDays         : 1.41981481481481E-07
TotalHours        : 3.40755555555556E-06
TotalMinutes      : 0.000204453333333333
TotalSeconds      : 0.0122672
TotalMilliseconds : 12.2672
```

### Пример 4. Отображение выходных данных команды отсчитывая

Чтобы отобразить выходные данные выражения в `Measure-Command` , можно использовать канал в `Out-Default` .

```powershell
# Perform the same operation as above adding Out-Default to every execution.
# This will show that the ScriptBlock is in fact executing for every item.
10, 20, 50 | Measure-Command -Expression {for ($i=0; $i -lt $_; $i++) {$i}; "$($_)" | Out-Default }
```

```Output
10
20
50


Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 0
Milliseconds      : 11
Ticks             : 113745
TotalDays         : 1.31649305555556E-07
TotalHours        : 3.15958333333333E-06
TotalMinutes      : 0.000189575
TotalSeconds      : 0.0113745
TotalMilliseconds : 11.3745
```

### Пример 5. измерение выполнения в дочерней области

`Measure-Command` выполняет блок скрипта в текущей области, поэтому блок скрипта может изменять значения в текущей области. Чтобы избежать изменений в текущей области, необходимо заключить блок скрипта в фигурные скобки ( `{}` ) и использовать оператор вызова ( `&` ) для выполнения блока в дочерней области.

```powershell
$foo = 'Value 1'
$null = Measure-Command { $foo = 'Value 2' }
$foo
$null = Measure-Command { & { $foo = 'Value 3' } }
$foo
```

```Output
Value 2
Value 2
```

Дополнительные сведения об операторе вызова см. в разделе [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md#call-operator-).

## PARAMETERS

### -Expression

Определяет выражение, время выполнения которого нужно определить. Заключите выражение в фигурные скобки ( `{}` ).

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Объекты, привязанные к параметру **InputObject** , являются необязательными входными данными для блока скрипта, передаваемого в параметр **Expression** . Внутри блока script `$_` можно использовать для ссылки на текущий объект в конвейере.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Management.Automation.PSObject

Объект можно передать в `Measure-Command` .

## Выходные данные

### System.TimeSpan

`Measure-Command` Возвращает объект интервала времени, представляющий результат.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)

[Trace-Command](Trace-Command.md)

