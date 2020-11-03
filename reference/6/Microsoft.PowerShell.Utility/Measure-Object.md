---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/measure-object?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Measure-Object;
ms.openlocfilehash: a4d80876136ca2c5837be9288c22776dc5a6a6f2
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2020
ms.locfileid: "93230338"
---
# Measure-Object;

## Краткий обзор
Рассчитывает числовые свойства объектов, а также количество знаков, слов и строк в строковых объектах, например в текстовых файлах.

## SYNTAX

### Женерикмеасуре (по умолчанию)

```
Measure-Object [[-Property] <PSPropertyExpression[]>] [-InputObject <PSObject>] [-StandardDeviation]
 [-Sum] [-AllStats] [-Average] [-Maximum] [-Minimum] [<CommonParameters>]
```

### текстмеасуре

```
Measure-Object [[-Property] <PSPropertyExpression[]>] [-InputObject <PSObject>] [-Line] [-Word]
 [-Character] [-IgnoreWhiteSpace] [<CommonParameters>]
```

## DESCRIPTION

`Measure-Object`Командлет вычисляет значения свойств определенных типов объектов.
`Measure-Object` выполняет три типа измерений в зависимости от параметров в команде.

`Measure-Object`Командлет выполняет вычисления со значениями свойств объектов. Можно использовать `Measure-Object` для подсчета объектов или количества объектов с указанным **свойством** . Можно также использовать `Measure-Object` для вычисления **минимального** , **максимального** , **итогового** , **стандартное отклонение** и **среднего** значения числовых значений. Для **строковых** объектов можно также использовать `Measure-Object` для подсчета количества строк, слов и символов.

## Примеры

### Пример 1. подсчет файлов и папок в каталоге

Эта команда определяет количество файлов и папок в текущем каталоге.

```powershell
Get-ChildItem | Measure-Object
```

### Пример 2. Измерение файлов в каталоге

Эта команда отображает **минимальные** , **максимальные** и **суммарные** размеры всех файлов в текущем каталоге, а также средний размер файла в каталоге.

```powershell
Get-ChildItem | Measure-Object -Property length -Minimum -Maximum -Average
```

### Пример 3. измерение текста в текстовом файле

Эта команда отображает количество знаков, слов и строк в файле Text.txt.
Без параметра **RAW** `Get-Content` выводит файл в виде массива строк.

Первая команда использует `Set-Content` для добавления текста по умолчанию в файл.

```powershell
"One", "Two", "Three", "Four" | Set-Content -Path C:\Temp\tmp.txt
Get-Content C:\Temp\tmp.txt | Measure-Object -Character -Line -Word
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    4     4         15
```

### Пример 4. Измерение объектов, содержащих указанное свойство

В этом примере подсчитывается количество объектов со свойством **DisplayName** . Первые две команды извлекают все службы и процессы на локальном компьютере. Третья команда подсчитывает общее число служб и процессов. Последняя команда объединяет две коллекции и передает результат в `Measure-Object` .

Объект **System. Diagnostics. Process** не имеет свойства **DisplayName** и не является окончательным числом.

```powershell
$services = Get-Service
$processes = Get-Process
$services + $processes | Measure-Object
$services + $processes | Measure-Object -Property DisplayName
```

```Output
Count    : 682
Average  :
Sum      :
Maximum  :
Minimum  :
Property :

Count    : 290
Average  :
Sum      :
Maximum  :
Minimum  :
Property : DisplayName
```

### Пример 5. Измерение содержимого CSV-файла

Эта команда вычисляет среднее время работы сотрудников в компании.

`ServiceYrs.csv`Файл представляет собой CSV-файл, содержащий номер сотрудника и годы обслуживания каждого сотрудника. Первая строка в таблице представляет собой строку заголовка **емпно** , **years** .

При использовании `Import-Csv` для импорта файла результатом является **PSCustomObject** со свойствами заметок **емпно** и **years** .
Можно использовать `Measure-Object` для вычисления значений этих свойств, как и для любого другого свойства объекта.

```powershell
Import-Csv d:\test\serviceyrs.csv | Measure-Object -Property years -Minimum -Maximum -Average
```

### Пример 6. Измерение логических значений

В этом примере показано, как `Measure-Object` можно измерять логические значения.
В этом случае используется **логическое** свойство **PSIsContainer** , которое измеряет совпадение папок (VS. Files) в текущем каталоге.

```powershell
Get-ChildItem | Measure-Object -Property psiscontainer -Maximum -Sum -Minimum -Average
```

```Output
Count             : 126
Average           : 0.0634920634920635
Sum               : 8
Maximum           : 1
Minimum           : 0
StandardDeviation :
Property          : PSIsContainer
```

### Пример 7. строки мер

В следующем примере измеряется количество строк, сначала одна строка, а затем несколько строк. Символ новой строки <code>`n</code> разделяет строки на несколько строк.

```powershell
# The newline character `n separates the string into separate lines, as shown in the output.
"One`nTwo`nThree"
"One`nTwo`nThree" | Measure-Object -Line
```

```Output
One
Two
Three


Lines Words Characters Property
----- ----- ---------- --------
    3
```

```powershell
# The first string counts as a single line.
# The second string is separated into two lines by the newline character.
"One", "Two`nThree" | Measure-Object -Line
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    3
```

```powershell
# The Word switch counts the number of words in each InputObject
# Each InputObject is treated as a single line.
"One, Two", "Three", "Four Five" | Measure-Object -Word -Line
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    3     5
```

### Пример 8. Измерение всех значений

Начиная с PowerShell 6, параметр **аллстатс** параметра `Measure-Object` позволяет измерять всю статистику вместе.

```powershell
1..5 | Measure-Object -AllStats
```

```output
Count             : 5
Average           : 3
Sum               : 15
Maximum           : 5
Minimum           : 1
StandardDeviation : 1.58113883008419
Property          :
```

### Пример 9. мера с использованием свойств ScriptBlock

Начиная с PowerShell 6, `Measure-Object` поддерживает свойства **ScriptBlock** . В следующем примере показано, как использовать свойство **ScriptBlock** для определения размера всех файлов в каталоге (в мегабайтах).

```powershell
Get-ChildItem | Measure-Object -Sum {$_.Length/1MB}
```

### Пример 10. хэш-таблицы мер

Начиная с PowerShell 6, `Measure-Object` поддерживает измерение входных **хэш-таблиц** . В следующем примере определяется максимальное значение `num` ключа из трех объектов **Hashtable** .

```powershell
@{num=3}, @{num=4}, @{num=5} | Measure-Object -Maximum Num
```

```output
Count             : 3
Average           :
Sum               :
Maximum           : 5
Minimum           :
StandardDeviation :
Property          : num
```

### Пример 11. измерение стандартного отклонения

Начиная с PowerShell 6, `Measure-Object` поддерживает `-StandardDeviation` параметр. В следующем примере определяется *стандартное отклонение* для ЦП, используемого всеми процессами. Большое отклонение указывает на небольшое количество процессов, которые потребляют больше всего ресурсов ЦП.

```powershell
Get-Process | Measure-Object -Average -StandardDeviation CPU
```

```output
Count             : 303
Average           : 163.032384488449
Sum               :
Maximum           :
Minimum           :
StandardDeviation : 859.444048419069
Property          : CPU
```

### Пример 12. мера с использованием подстановочных знаков

Начиная с PowerShell 6, `Measure-Object` поддерживает измерение объектов с помощью подстановочных знаков в именах свойств. В приведенном ниже примере определяется максимальное использование страничной памяти любого типа в наборе процессов.

```powershell
Get-Process | Measure-Object -Maximum *paged*memory*size
```

```output
Count             : 303
Average           :
Sum               :
Maximum           : 735784
Minimum           :
StandardDeviation :
Property          : NonpagedSystemMemorySize

Count             : 303
Average           :
Sum               :
Maximum           : 352104448
Minimum           :
StandardDeviation :
Property          : PagedMemorySize

Count             : 303
Average           :
Sum               :
Maximum           : 2201968
Minimum           :
StandardDeviation :
Property          : PagedSystemMemorySize

Count             : 303
Average           :
Sum               :
Maximum           : 719032320
Minimum           :
StandardDeviation :
Property          : PeakPagedMemorySize
```

## PARAMETERS

### — Среднее значение

Указывает, что командлет отображает среднее значение указанных свойств.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — Символ

Указывает, что командлет подсчитывает количество символов во входных объектах.

> [!NOTE]
> **Слова** , **char** и **line** переключаются *внутри* каждого входного объекта, а также *во* входных объектах. См. Пример 7.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Игноревхитеспаце

Указывает, что командлет игнорирует пробелы в количестве символов.
По умолчанию пробелы учитываются.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Указывает, какие объекты нужно измерять.
Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.

При использовании параметра **InputObject** с параметром `Measure-Object` , а не с результатами команды трубопроводов в `Measure-Object` значение **InputObject** рассматривается как один объект.

Рекомендуется использовать `Measure-Object` в конвейере, если необходимо измерять коллекцию объектов в зависимости от того, имеют ли объекты определенные значения в определенных свойствах.

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

### -Line

Указывает, что командлет подсчитывает количество строк во входных объектах.

> [!NOTE]
> **Слова** , **char** и **line** переключаются *внутри* каждого входного объекта, а также *во* входных объектах. См. Пример 7.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — Максимум

Указывает, что командлет отображает максимальное значение указанных свойств.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — Минимум

Указывает, что командлет отображает минимальное значение указанных свойств.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Property

Указывает одно или несколько свойств для измерения. Если не указать другие меры, `Measure-Object` подсчитывает количество объектов, которые имеют указанные свойства.

Значением параметра **Property** может быть новое вычисляемое свойство. Вычисляемое свойство должно быть блоком скрипта. Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).

```yaml
Type: Microsoft.PowerShell.Commands.PSPropertyExpression[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Стандартное отклонение

Указывает, что командлет отображает стандартное отклонение значений указанных свойств.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sum

Указывает, что командлет отображает сумму значений указанных свойств.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Аллстатс

Указывает, что командлет отображает всю статистику указанных свойств.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Слово

Указывает, что командлет подсчитывает количество слов во входных объектах.

> [!NOTE]
> **Слова** , **char** и **line** переключаются *внутри* каждого входного объекта, а также *во* входных объектах. См. Пример 7.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Management.Automation.PSObject

Вы можете передать объекты в `Measure-Object` .

## Выходные данные

### Microsoft. PowerShell. Commands. Женерикмеасуреинфо

### Microsoft. PowerShell. Commands. Текстмеасуреинфо

При использовании параметра **Word** `Measure-Object` возвращает объект **текстмеасуреинфо** .
В противном случае возвращается объект **женерикмеасуреинфо** .

## ПРИМЕЧАНИЯ

## Связанные ссылки

[about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[Compare-Object](Compare-Object.md)

[ForEach-Object](../Microsoft.PowerShell.Core/ForEach-Object.md)

[Group-Object](Group-Object.md)

[New-Object](New-Object.md)

[Select-Object](Select-Object.md)

[Sort-Object](Sort-Object.md)

[Tee-Object](Tee-Object.md)

[Where-Object](../Microsoft.PowerShell.Core/Where-Object.md)
