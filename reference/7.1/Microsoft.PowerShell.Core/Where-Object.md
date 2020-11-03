---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Where-Object
ms.openlocfilehash: b5f4a64cceffa1f4f9884bb4de3211e129871ba7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229478"
---
# Where-Object

## Краткий обзор
Выбирает объекты из коллекции на основании значения их свойств.

## SYNTAX

### Equals (по умолчанию)

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-EQ]
 [<CommonParameters>]
```

### скриптблокксет

```
Where-Object [-InputObject <PSObject>] [-FilterScript] <ScriptBlock> [<CommonParameters>]
```

### Match

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Match
 [<CommonParameters>]
```

### касесенситивикуалсет

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CEQ
 [<CommonParameters>]
```

### нотекуалсет

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NE
 [<CommonParameters>]
```

### касесенситивенотекуалсет

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNE
 [<CommonParameters>]
```

### греатерсансет

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -GT
 [<CommonParameters>]
```

### касесенситивегреатерсансет

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CGT
 [<CommonParameters>]
```

### лесссансет

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -LT
 [<CommonParameters>]
```

### касесенситивелесссансет

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLT
 [<CommonParameters>]
```

### греатерорекуалсет

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -GE
 [<CommonParameters>]
```

### касесенситивегреатерорекуалсет

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CGE
 [<CommonParameters>]
```

### лессорекуалсет

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -LE
 [<CommonParameters>]
```

### касесенситивелессорекуалсет

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLE
 [<CommonParameters>]
```

### Аналогичный

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Like
 [<CommonParameters>]
```

### касесенситивеликесет

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLike
 [<CommonParameters>]
```

### нотликесет

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotLike
 [<CommonParameters>]
```

### касесенситивенотликесет

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotLike
 [<CommonParameters>]
```

### касесенситивематчсет

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CMatch
 [<CommonParameters>]
```

### нотматчсет

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotMatch
 [<CommonParameters>]
```

### касесенситивенотматчсет

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotMatch
 [<CommonParameters>]
```

### Contains

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Contains
 [<CommonParameters>]
```

### касесенситивеконтаинссет

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CContains
 [<CommonParameters>]
```

### нотконтаинссет

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotContains
 [<CommonParameters>]
```

### касесенситивенотконтаинссет

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotContains
 [<CommonParameters>]
```

### Вставка

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -In
 [<CommonParameters>]
```

### касесенситивеинсет

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CIn
 [<CommonParameters>]
```

### нотинсет

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotIn
 [<CommonParameters>]
```

### касесенситивенотинсет

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotIn
 [<CommonParameters>]
```

### иссет

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Is
 [<CommonParameters>]
```

### иснотсет

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -IsNot
 [<CommonParameters>]
```

### Not

```
Where-Object [-InputObject <PSObject>] [-Property] <String> -Not [<CommonParameters>]
```

## DESCRIPTION

`Where-Object`Командлет выбирает объекты, имеющие определенные значения свойств, из коллекции объектов, которые передаются в него. Например, командлет можно использовать `Where-Object` для выбора файлов, созданных после определенной даты, событий с определенным идентификатором, или компьютеров, использующих определенную версию Windows.

Начиная с Windows PowerShell 3,0 существует два разных способа создания `Where-Object` команды.

- **Блок скрипта** . Для указания имени свойства, оператора сравнения и значения свойства можно использовать блок сценария. `Where-Object` Возвращает все объекты, для которых инструкция блока скрипта имеет значение true.

  Например, следующая команда получает процессы в классе с нормальным приоритетом, то есть обрабатывает, где значение свойства **PriorityClass значение** равно "Обычная".

  `Get-Process | Where-Object {$_.PriorityClass -eq "Normal"}`

  Все операторы сравнения PowerShell допустимы в формате блока сценария. Дополнительные сведения об операторах сравнения см. в разделе [about_Comparison_Operators](./About/about_Comparison_Operators.md).

- **Оператор сравнения** . Можно также написать оператор сравнения, который больше похож на естественный язык. Операторы сравнения были представлены в Windows PowerShell 3.0.

  Например, следующие команды также получают процессы, имеющие класс приоритета "Обычная". Эти команды эквивалентны и взаимозаменяемы.

  `Get-Process | Where-Object -Property PriorityClass -eq -Value "Normal"`

  `Get-Process | Where-Object PriorityClass -eq "Normal"`

  Начиная с Windows PowerShell 3,0, `Where-Object` в команде добавляются операторы сравнения в качестве параметров `Where-Object` . Если не указано иначе, все операторы вводятся без учета регистра. До Windows PowerShell 3,0 операторы сравнения в языке PowerShell можно использовать только в блоках сценариев.

При предоставлении одного **Свойства** в `Where-Object` значение свойства обрабатывается как логическое выражение. Если значение **length** не равно нулю, выражение принимает **значение true** . Пример: `('hi', '', 'there') | Where-Object Length`

Предыдущий пример функционально эквивалентен:

- `('hi', '', 'there') | Where-Object Length -GT 0`
- `('hi', '', 'there') | Where-Object {$_.Length -gt 0}`

## Примеры

### Пример 1. получение остановленных служб

Эти команды получают список всех служб, остановленных в данный момент. `$_`Автоматическая переменная представляет каждый объект, передаваемый в `Where-Object` командлет.

Первая команда использует формат блока сценария, вторая команда использует формат инструкции сравнения. Команды эквивалентны и взаимозаменяемы.

```powershell
Get-Service | Where-Object {$_.Status -eq "Stopped"}
Get-Service | where Status -eq "Stopped"
```

### Пример 2. получение процессов на основе рабочего набора

Эти команды содержат список процессов, имеющих рабочий набор, превышающий 250 мегабайт (КБ). Синтаксис ScriptBlock и инструкции эквивалентен и может использоваться взаимозаменяемым.

```powershell
Get-Process | Where-Object {$_.WorkingSet -GT 250MB}
Get-Process | Where-Object WorkingSet -GT (250MB)
```

### Пример 3. получение процессов на основе имени процесса

Эти команды получают процессы со значением свойства **processName** , которое начинается с буквы `p` . Оператор **Match** позволяет использовать совпадения регулярных выражений.

Синтаксис ScriptBlock и инструкции эквивалентен и может использоваться взаимозаменяемым.

```powershell
Get-Process | Where-Object {$_.ProcessName -Match "^p.*"}
Get-Process | Where-Object ProcessName -Match "^p.*"
```

### Пример 4. Использование формата инструкции сравнения

В этом примере показано, как использовать новый формат инструкции сравнения `Where-Object` командлета.

Вторая команда использует формат оператора сравнения.
В этой команде не используются псевдонимы, и все параметры включают имя параметра.

Вторая команда является более естественным способом использованием формата команды сравнения. `where`Псевдоним заменяется `Where-Object` именем командлета, а все необязательные имена параметров опускаются.

```powershell
Get-Process | Where-Object -Property Handles -GE -Value 1000
Get-Process | where Handles -GE 1000
```

### Пример 5. получение команд на основе свойств

В этом примере показано, как написать команды, которые возвращают элементы, имеющие значения true или false или любые значения для указанного свойства. В каждом примере показаны форматы блока скрипта и инструкции сравнения для команды.

```powershell
# Use Where-Object to get commands that have any value for the OutputType property of the command.
# This omits commands that do not have an OutputType property and those that have an OutputType property, but no property value.
Get-Command | where OutputType
Get-Command | where {$_.OutputType}
```

```powershell
# Use Where-Object to get objects that are containers.
# This gets objects that have the **PSIsContainer** property with a value of $True and excludes all others.
Get-ChildItem | where PSIsContainer
Get-ChildItem | where {$_.PSIsContainer}
```

```powershell
# Finally, use the Not operator (!) to get objects that are not containers.
# This gets objects that do have the **PSIsContainer** property and those that have a value of $False for the **PSIsContainer** property.
Get-ChildItem | where {!$_.PSIsContainer}
# You cannot use the Not operator (!) in the comparison statement format of the command.
Get-ChildItem | where PSIsContainer -eq $False
```

### Пример 6. Использование нескольких условий

```powershell
Get-Module -ListAvailable | where {($_.Name -notlike "Microsoft*" -and $_.Name -notlike "PS*") -and $_.HelpInfoUri}
```

В этом примере показано, как создать `Where-Object` команду с несколькими условиями.

Эта команда получает вспомогательные модули, которые поддерживают функцию обновляемой справки. Команда использует параметр **ListAvailable** `Get-Module` командлета для получения всех модулей на компьютере. Оператор конвейера ( `|` ) отправляет модули в `Where-Object` командлет, который получает модули, имена которых не начинаются с Microsoft или PS, и имеют значение для свойства **HelpInfoURI** , которое сообщает PowerShell, где найти обновленные файлы справки для модуля. Операторы сравнения соединены логическим оператором **и** .

В примере используется формат команды блока сценария. Логические операторы, такие как **и** и **или** , допустимы только в блоках скриптов. Их нельзя использовать в формате инструкции сравнения `Where-Object` команды.

- Дополнительные сведения о логических операторах PowerShell см. в разделе [about_Logical_Operators](./About/about_logical_operators.md).
- Дополнительные сведения о функции обновляемой справки см. в разделе [about_Updatable_Help](./About/about_Updatable_Help.md).

## PARAMETERS

### -Кконтаинс

Указывает, что этот командлет получает объекты из коллекции, если значение свойства объекта является точным соответствием для указанного значения. В этой операции учитывается регистр.

Пример: `Get-Process | where ProcessName -CContains "svchost"`

**Кконтаинс** ссылается на коллекцию значений и имеет значение true, если коллекция содержит элемент, который является точным соответствием для указанного значения. Если входные данные являются одним объектом, PowerShell преобразует его в коллекцию одного объекта.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveContainsSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ЦЕК

Указывает, что этот командлет получает объекты, если значение свойства совпадает с указанным значением.
В этой операции учитывается регистр.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CGE

Указывает, что этот командлет получает объекты, если значение свойства больше или равно указанному значению. В этой операции учитывается регистр.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveGreaterOrEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -КГТ

Указывает, что этот командлет получает объекты, если значение свойства больше указанного значения.
В этой операции учитывается регистр.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveGreaterThanSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CIn

Указывает, что этот командлет получает объекты, если значение свойства включает указанное значение. В этой операции учитывается регистр.

Пример: `Get-Process | where -Value "svchost" -CIn ProcessName`

**CIn** напоминает **кконтаинс** , за исключением того, что позиции свойства и значения реверсируются. Например обе следующие инструкции верны.

`"abc", "def" -CContains "abc"`

`"abc" -CIn "abc", "def"`

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveInSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CLE

Указывает, что этот командлет получает объекты, если значение свойства меньше или равно указанному значению. В этой операции учитывается регистр.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveLessOrEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Клике

Указывает, что этот командлет получает объекты, если значение свойства соответствует значению, включающему символы-шаблоны. В этой операции учитывается регистр.

Пример: `Get-Process | where ProcessName -CLike "*host"`

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveLikeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — Средство регистрации звонков

Указывает, что этот командлет получает объекты, если значение свойства меньше указанного значения. В этой операции учитывается регистр.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveLessThanSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CMatch

Указывает, что этот командлет получает объекты, если значение свойства соответствует указанному регулярному выражению. В этой операции учитывается регистр. Если входные данные скалярны, сопоставленное значение сохраняется в `$Matches` автоматической переменной.

Пример: `Get-Process | where ProcessName -CMatch "Shell"`

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveMatchSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CNE

Указывает, что этот командлет получает объекты, если значение свойства отличается от указанного значения.
В этой операции учитывается регистр.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Кнотконтаинс

Указывает, что этот командлет получает объекты, если значение свойства объекта не является точным соответствием для указанного значения. В этой операции учитывается регистр.

Пример: `Get-Process | where ProcessName -CNotContains "svchost"`

**NotContains** и **кнотконтаинс** ссылаются на коллекцию значений и имеют значение true, если коллекция не содержит элементов, которые точно соответствуют заданному значению. Если входные данные являются одним объектом, PowerShell преобразует его в коллекцию одного объекта.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotContainsSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Кнотин

Указывает, что этот командлет получает объекты, если значение свойства не является точным соответствием для указанного значения. В этой операции учитывается регистр.

Пример: `Get-Process | where -Value "svchost" -CNotIn -Property ProcessName`

Операторы **NotIn** и **Кнотин** похожи на **NotContains** и **кнотконтаинс** , за исключением того, что позиции свойств и значений реверсируются. Например, обе следующие инструкции верны.

`"abc", "def" -CNotContains "Abc"`

`"abc" -CNotIn "Abc", "def"`

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotInSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Кнотлике

Указывает, что этот командлет получает объекты, если значение свойства не соответствует значению, включающему символы-шаблоны. В этой операции учитывается регистр.

Пример: `Get-Process | where ProcessName -CNotLike "*host"`

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotLikeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Кнотматч

Указывает, что этот командлет получает объекты, если значение свойства не совпадает с указанным регулярным выражением. В этой операции учитывается регистр. Если входные данные скалярны, сопоставленное значение сохраняется в `$Matches` автоматической переменной.

Пример: `Get-Process | where ProcessName -CNotMatch "Shell"`

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotMatchSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — Содержит

Указывает, что этот командлет получает объекты, если какой-либо элемент в значении свойства объекта является точным соответствием для указанного значения.

Пример: `Get-Process | where ProcessName -Contains "Svchost"`

Если значение свойства содержит один объект, PowerShell преобразует его в коллекцию одного объекта.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ContainsSet
Aliases: IContains

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EQ

Указывает, что этот командлет получает объекты, если значение свойства совпадает с указанным значением.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: EqualSet
Aliases: IEQ

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilterScript представляет собой

Задает блок сценария, который используется для фильтрации объектов. Заключите блок скрипта в фигурные скобки ( `{}` ).

Имя параметра, **FilterScript представляет собой** , является необязательным.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlockSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GE

Указывает, что этот командлет получает объекты, если значение свойства больше или равно указанному значению.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GreaterOrEqualSet
Aliases: IGE

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GT

Указывает, что этот командлет получает объекты, если значение свойства больше указанного значения.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GreaterThanSet
Aliases: IGT

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — В

Указывает, что этот командлет получает объекты, если значение свойства совпадает с любым из указанных значений.
Пример:

`Get-Process | where -Property ProcessName -in -Value "Svchost", "TaskHost", "WsmProvHost"`

Если значение параметра **value** является одним объектом, PowerShell преобразует его в коллекцию одного объекта.

Если значение свойства объекта является массивом, PowerShell использует ссылочное равенство для определения совпадения. `Where-Object` Возвращает объект только в том случае, если значение параметра **Property** и любое значение **value** являются одним и тем же экземпляром объекта.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: InSet
Aliases: IIn

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Задает объекты для фильтрации. Также можно передать объекты в `Where-Object` .

При использовании параметра **InputObject** с параметром `Where-Object` , а не с результатами команды трубопроводов в `Where-Object` значение **InputObject** рассматривается как один объект. Это справедливо, даже если значением является коллекция, которая является результатом команды, например `-InputObject (Get-Process)` . Поскольку **InputObject** не может возвращать отдельные свойства из массива или коллекции объектов, рекомендуется `Where-Object` использовать для фильтрации коллекции объектов для объектов, имеющих определенные значения в определенных свойствах, `Where-Object` в конвейере, как показано в примерах этого раздела.

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

### — Имеет

Указывает, что этот командлет получает объекты, если значение свойства является экземпляром указанного типа .NET. Заключите имя типа в квадратные скобки.

Например `Get-Process | where StartTime -Is [DateTime]`.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IsSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsNot

Указывает, что этот командлет получает объекты, если значение свойства не является экземпляром указанного типа .NET.

Например `Get-Process | where StartTime -IsNot [DateTime]`.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IsNotSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LE

Указывает, что этот командлет получает объекты, если значение свойства меньше или равно указанному значению.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LessOrEqualSet
Aliases: ILE

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Like

Указывает, что этот командлет получает объекты, если значение свойства соответствует значению, включающему символы-шаблоны.

Пример: `Get-Process | where ProcessName -Like "*host"`

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LikeSet
Aliases: ILike

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LT

Указывает, что этот командлет получает объекты, если значение свойства меньше указанного значения.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LessThanSet
Aliases: ILT

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Match

Указывает, что этот командлет получает объекты, если значение свойства соответствует указанному регулярному выражению. Если входные данные скалярны, сопоставленное значение сохраняется в `$Matches` автоматической переменной.

Пример: `Get-Process | where ProcessName -Match "shell"`

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: MatchSet
Aliases: IMatch

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NE

Указывает, что этот командлет получает объекты, если значение свойства отличается от указанного значения.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotEqualSet
Aliases: INE

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — Не

Указывает, что этот командлет получает объекты, если свойство не существует или имеет значение null или false.

Пример: `Get-Service | where -Not "DependentServices"`

Этот параметр появился в Windows PowerShell 6,1.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Not
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NotContains

Указывает, что этот командлет получает объекты, если ни один из элементов в значении свойства не является точным соответствием для указанного значения.

Пример: `Get-Process | where ProcessName -NotContains "Svchost"`

**NotContains** ссылается на коллекцию значений и имеет значение true, если коллекция не содержит элементов, которые точно совпадают с указанным значением. Если входные данные являются одним объектом, PowerShell преобразует его в коллекцию одного объекта.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotContainsSet
Aliases: INotContains

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NotIn

Указывает, что этот командлет получает объекты, если значение свойства не является точным соответствием для любого из указанных значений.

Пример: `Get-Process | where -Value "svchost" -NotIn -Property ProcessName`

Если значение **value** является одним объектом, PowerShell преобразует его в коллекцию одного объекта.

Если значение свойства объекта является массивом, PowerShell использует ссылочное равенство для определения совпадения. `Where-Object` Возвращает объект только в том случае, если значение **Свойства** и любое значение **значения** не являются одним и тем же экземпляром объекта.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotInSet
Aliases: INotIn

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NotLike

Указывает, что этот командлет получает объекты, если значение свойства не соответствует значению, включающему символы-шаблоны.

Пример: `Get-Process | where ProcessName -NotLike "*host"`

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotLikeSet
Aliases: INotLike

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NotMatch

Указывает, что этот командлет получает объекты, если значение свойства не совпадает с указанным регулярным выражением. Если входные данные скалярны, сопоставленное значение сохраняется в `$Matches` автоматической переменной.

Пример: `Get-Process | where ProcessName -NotMatch "PowerShell"`

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotMatchSet
Aliases: INotMatch

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Property

Задает имя свойства объекта. Имя параметра, **свойство** , является необязательным.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.String
Parameter Sets: EqualSet, LessOrEqualSet, CaseSensitiveEqualSet, NotEqualSet, CaseSensitiveNotEqualSet, GreaterThanSet, CaseSensitiveGreaterThanSet, LessThanSet, CaseSensitiveLessThanSet, GreaterOrEqualSet, CaseSensitiveGreaterOrEqualSet, CaseSensitiveLessOrEqualSet, LikeSet, CaseSensitiveLikeSet, NotLikeSet, CaseSensitiveNotLikeSet, MatchSet, CaseSensitiveMatchSet, NotMatchSet, CaseSensitiveNotMatchSet, ContainsSet, CaseSensitiveContainsSet, NotContainsSet, CaseSensitiveNotContainsSet, InSet, CaseSensitiveInSet, NotInSet, CaseSensitiveNotInSet, IsSet, IsNotSet, Not
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value

Задает значение свойства. Имя параметра, **значение** является необязательным. Этот параметр принимает подстановочные знаки при использовании со следующими параметрами сравнения:

- **клике**
- **кнотлике**
- **Например**
- **NotLike**

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Object
Parameter Sets: EqualSet, LessOrEqualSet, CaseSensitiveEqualSet, NotEqualSet, CaseSensitiveNotEqualSet, GreaterThanSet, CaseSensitiveGreaterThanSet, LessThanSet, CaseSensitiveLessThanSet, GreaterOrEqualSet, CaseSensitiveGreaterOrEqualSet, CaseSensitiveLessOrEqualSet, LikeSet, CaseSensitiveLikeSet, NotLikeSet, CaseSensitiveNotLikeSet, MatchSet, CaseSensitiveMatchSet, NotMatchSet, CaseSensitiveNotMatchSet, ContainsSet, CaseSensitiveContainsSet, NotContainsSet, CaseSensitiveNotContainsSet, InSet, CaseSensitiveInSet, NotInSet, CaseSensitiveNotInSet, IsSet, IsNotSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Management.Automation.PSObject

Объекты можно передать в этот командлет по конвейеру.

## Выходные данные

### Объект

Этот командлет возвращает выбранные элементы из набора входных объектов.

## ПРИМЕЧАНИЯ

Начиная с Windows PowerShell 4,0, `Where` `ForEach` методы были добавлены для использования с коллекциями.

Дополнительные сведения об этих новых методах можно узнать здесь [about_arrays](./About/about_Arrays.md)

## Связанные ссылки

[Compare-Object](../Microsoft.PowerShell.Utility/Compare-Object.md)

[ForEach-Object](ForEach-Object.md)

[Group-Object](../Microsoft.PowerShell.Utility/Group-Object.md)

[Measure-Object;](../Microsoft.PowerShell.Utility/Measure-Object.md)

[New-Object](../Microsoft.PowerShell.Utility/New-Object.md)

[Select-Object](../Microsoft.PowerShell.Utility/Select-Object.md)

[Sort-Object](../Microsoft.PowerShell.Utility/Sort-Object.md)

[Tee-Object](../Microsoft.PowerShell.Utility/Tee-Object.md)

