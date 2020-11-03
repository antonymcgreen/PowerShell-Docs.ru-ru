---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/select-object?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Select-Object;
ms.openlocfilehash: 4b1d1fc9961f453c43981c7c81c7de5f059a790e
ms.sourcegitcommit: f9ae48d026d65833b9c8ca881058dda0bbd067b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2020
ms.locfileid: "93230713"
---
# Select-Object;

## Краткий обзор
Выбирает объекты или свойства объектов.

## SYNTAX

### Дефаултпараметер (по умолчанию)

```
Select-Object [-InputObject <PSObject>] [[-Property] <Object[]>] [-ExcludeProperty <String[]>]
 [-ExpandProperty <String>] [-Unique] [-Last <Int32>] [-First <Int32>] [-Skip <Int32>] [-Wait]
 [<CommonParameters>]
```

### скипластпараметер

```
Select-Object [-InputObject <PSObject>] [[-Property] <Object[]>] [-ExcludeProperty <String[]>]
 [-ExpandProperty <String>] [-Unique] [-SkipLast <Int32>] [<CommonParameters>]
```

### индекспараметер

```
Select-Object [-InputObject <PSObject>] [-Unique] [-Wait] [-Index <Int32[]>] [<CommonParameters>]
```

### скипиндекспараметер

```
Select-Object [-InputObject <PSObject>] [-Unique] [-SkipIndex <Int32[]>] [<CommonParameters>]
```

## DESCRIPTION

`Select-Object`Командлет выбирает указанные свойства объекта или набора объектов. Он также может выбирать уникальные объекты, указанное число объектов или объекты в указанной позиции в массиве.

Чтобы выбрать объекты из коллекции, используйте параметры **First** , **Last** , **Unique** , **Skip** и **Index** . Чтобы выбрать свойства объектов, используйте параметр **Property** . При выборе свойства `Select-Object` возвращает новые объекты, которые имеют только указанные свойства.

Начиная с Windows PowerShell 3,0, `Select-Object` включает функцию оптимизации, которая предотвращает создание и обработку неиспользуемых объектов командами.

При включении `Select-Object` команды с **первым** или **индексными** параметрами в конвейере команд PowerShell останавливает команду, создающую объекты, как только выбранное число объектов будет создано, даже если команда, создающая объекты, появилась перед `Select-Object` командой в конвейере. Чтобы отключить эту функцию оптимизации, используйте параметр **Wait** .

## Примеры

### Пример 1. Выбор объектов по свойству

В этом примере создаются объекты, имеющие свойства **Name** , **ID** и Working Set ( **WS** ) объектов Process.

```powershell
Get-Process | Select-Object -Property ProcessName, Id, WS
```

### Пример 2. Выбор объектов по свойству и форматирование результатов

Этот пример возвращает сведения о модулях, используемых процессами на компьютере. Он использует `Get-Process` командлет для получения процесса на компьютере.

Он использует `Select-Object` командлет для вывода массива `[System.Diagnostics.ProcessModule]` экземпляров, содержащихся в свойстве **modules** каждого `System.Diagnostics.Process` экземпляра, с помощью `Get-Process` .

Параметр **Property** `Select-Object` командлета выбирает имена процессов. Это добавляет `ProcessName` **NoteProperty** к каждому `[System.Diagnostics.ProcessModule]` экземпляру и заполняет его значением свойства **processName** текущего процесса.

Наконец, `Format-List` командлет используется для вывода имени и модулей каждого процесса в списке.

```powershell
Get-Process Explorer | Select-Object -Property ProcessName -ExpandProperty Modules | Format-List
```

```Output
ProcessName       : explorer
ModuleName        : explorer.exe
FileName          : C:\WINDOWS\explorer.exe
BaseAddress       : 140697278152704
ModuleMemorySize  : 3919872
EntryPointAddress : 140697278841168
FileVersionInfo   : File:             C:\WINDOWS\explorer.exe
                    InternalName:     explorer
                    OriginalFilename: EXPLORER.EXE.MUI
                    FileVersion:      10.0.17134.1 (WinBuild.160101.0800)
                    FileDescription:  Windows Explorer
                    Product:          Microsoft Windows Operating System
                    ProductVersion:   10.0.17134.1
...
```

### Пример 3. Выбор процессов с наибольшим объемом памяти

Этот пример получает пять процессов, использующих наибольшую память. `Get-Process`Командлет возвращает процессы на компьютере. `Sort-Object`Командлет сортирует процессы в соответствии с использованием памяти (рабочего набора), и `Select-Object` командлет выбирает только последние пять элементов результирующего массива объектов.

Параметр **Wait** не требуется в командах, включающих `Sort-Object` командлет, так как `Sort-Object` обрабатывает все объекты, а затем возвращает коллекцию. `Select-Object`Оптимизация доступна только для команд, которые возвращают объекты по отдельности при их обработке.

```powershell
Get-Process | Sort-Object -Property WS | Select-Object -Last 5
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VS(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
2866     320       33432      45764   203   222.41   1292 svchost
577      17        23676      50516   265    50.58   4388 WINWORD
826      11        75448      76712   188    19.77   3780 Ps
1367     14        73152      88736   216    61.69    676 Ps
1612     44        66080      92780   380   900.59   6132 INFOPATH
```

### Пример 4. выбор уникальных символов из массива

В этом примере **Unique** `Select-Object` для получения уникальных символов из массива символов используется параметр Unique объекта.

```powershell
"a","b","c","a","a","a" | Select-Object -Unique
```

```Output
a
b
c
```

### Пример 5. Выбор новых и старых событий в журнале событий

Этот пример получает первые (самые новые) и последние (самые старые) события в журнале событий Windows PowerShell.

`Get-EventLog` Возвращает все события в журнале Windows PowerShell и сохраняет их в `$a` переменной.
Затем `$a` передается в `Select-Object` командлет. `Select-Object`Команда использует параметр **index** для выбора событий из массива событий в `$a` переменной. Индекс первого события равен 0. Индекс последнего события — это число элементов за `$a` вычетом 1.

```powershell
$a = Get-EventLog -LogName "Windows PowerShell"
$a | Select-Object -Index 0, ($A.count - 1)
```

### Пример 6. выделение всех объектов, кроме первого

В этом примере создается новый сеанс PSSession на каждом из компьютеров, перечисленных в файлах Servers.txt, за исключением первого.

`Select-Object` выбирает все компьютеры, кроме первого, в списке имен компьютеров. Результирующий список компьютеров задается в качестве значения параметра **ComputerName** `New-PSSession` командлета.

```powershell
New-PSSession -ComputerName (Get-Content Servers.txt | Select-Object -Skip 1)
```

### Пример 7. Переименование файлов и выбор нескольких для проверки

В этом примере добавляется суффикс "-RO" к базовым именам текстовых файлов с атрибутом "только для чтения", а затем выводятся первые пять файлов, чтобы пользователь мог увидеть образец этого действия.

`Get-ChildItem` использует динамический параметр ReadOnly для получения файлов, доступных только **для** чтения. Результирующие файлы передаются в `Rename-Item` командлет, который переименовывает файл. Параметр **PassThru** параметра используется `Rename-Item` для отправки переименованных файлов в `Select-Object` командлет, который выбирает первые 5 для экрана.

Параметр **Wait** `Select-Object` предотвращает остановку `Get-ChildItem` командлета PowerShell после получения первых пяти текстовых файлов, которые доступны только для чтения. Без этого параметра были бы переименованы только первые пять таких файлов.

```powershell
Get-ChildItem *.txt -ReadOnly |
    Rename-Item -NewName {$_.BaseName + "-ro.txt"} -PassThru |
    Select-Object -First 5 -Wait
```

### Пример 8. Демонстрация тонкостей параметра-Експандпроперти

В этом примере демонстрируются сложности параметра **експандпроперти** .

Обратите внимание, что создаваемые выходные данные были массивом `[System.Int32]` экземпляров. Экземпляры соответствуют стандартным правилам форматирования **представления вывода** . Это справедливо для всех *развернутых* свойств. Если выводимые объекты имеют конкретный стандартный формат, то развернутое свойство может быть невидимым.

```powershell
# Create a custom object to use for the Select-Object example.
$object = [pscustomobject]@{Name="CustomObject";Expand=@(1,2,3,4,5)}
# Use the ExpandProperty parameter to Expand the property.
$object | Select-Object -ExpandProperty Expand -Property Name
```

```Output
1
2
3
4
5
```

```powershell
# The output did not contain the Name property, but it was added successfully.
# Use Get-Member to confirm the Name property was added and populated.
$object | Select-Object -ExpandProperty Expand -Property Name | Get-Member
```

```Output
   TypeName: System.Int32

Name        MemberType   Definition
----        ----------   ----------
CompareTo   Method       int CompareTo(System.Object value), int CompareTo(int value), int IComparable.CompareTo(System.Object obj)...
Equals      Method       bool Equals(System.Object obj), bool Equals(int obj), bool IEquatable[int].Equals(int other)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
GetTypeCode Method       System.TypeCode GetTypeCode(), System.TypeCode IConvertible.GetTypeCode()
ToBoolean   Method       bool IConvertible.ToBoolean(System.IFormatProvider provider)
ToByte      Method       byte IConvertible.ToByte(System.IFormatProvider provider)
ToChar      Method       char IConvertible.ToChar(System.IFormatProvider provider)
ToDateTime  Method       datetime IConvertible.ToDateTime(System.IFormatProvider provider)
ToDecimal   Method       decimal IConvertible.ToDecimal(System.IFormatProvider provider)
ToDouble    Method       double IConvertible.ToDouble(System.IFormatProvider provider)
ToInt16     Method       int16 IConvertible.ToInt16(System.IFormatProvider provider)
ToInt32     Method       int IConvertible.ToInt32(System.IFormatProvider provider)
ToInt64     Method       long IConvertible.ToInt64(System.IFormatProvider provider)
ToSByte     Method       sbyte IConvertible.ToSByte(System.IFormatProvider provider)
ToSingle    Method       float IConvertible.ToSingle(System.IFormatProvider provider)
ToString    Method       string ToString(), string ToString(string format), string ToString(System.IFormatProvider provider)...
ToType      Method       System.Object IConvertible.ToType(type conversionType, System.IFormatProvider provider)
ToUInt16    Method       uint16 IConvertible.ToUInt16(System.IFormatProvider provider)
ToUInt32    Method       uint32 IConvertible.ToUInt32(System.IFormatProvider provider)
ToUInt64    Method       uint64 IConvertible.ToUInt64(System.IFormatProvider provider)
Name        NoteProperty string Name=CustomObject
```

### Пример 9. Создание пользовательских свойств для объектов

В следующем примере демонстрируется использование `Select-Object` для добавления пользовательского свойства в любой объект.
При указании несуществующего имени свойства `Select-Object` создает это свойство как **NoteProperty** для каждого переданного объекта.

```powershell
$customObject = 1 | Select-Object -Property MyCustomProperty
$customObject.MyCustomProperty = "New Custom Property"
$customObject
```

```Output
MyCustomProperty
----------------
New Custom Property
```

### Пример 10. Создание вычисляемых свойств для каждого InputObject

В этом примере демонстрируется использование `Select-Object` для добавления вычисляемых свойств к входным данным. Передача параметра **ScriptBlock** в параметр **Property** приводит `Select-Object` к вычислению выражения для каждого переданного объекта и добавлению результатов в выходные данные. В блоке **сценария** можно использовать `$_` переменную для ссылки на текущий объект в конвейере.

По умолчанию в `Select-Object` качестве имени свойства будет использоваться строка **ScriptBlock** . С помощью **хэш-таблицы** можно пометить выходные данные **ScriptBlock** как пользовательское свойство, добавляемое к каждому объекту. К каждому объекту, переданному в, можно добавить несколько вычисляемых свойств `Select-Object` .

```powershell
# Create a calculated property called $_.StartTime.DayOfWeek
Get-Process | Select-Object -Property ProcessName,{$_.StartTime.DayOfWeek}
```

```Output
ProcessName  $_.StartTime.DayOfWeek
----         ----------------------
alg                       Wednesday
ati2evxx                  Wednesday
ati2evxx                   Thursday
...
```

```powershell
# Add a custom property to calculate the size in KiloBytes of each FileInfo object you pass in.
# Use the pipeline variable to divide each file's length by 1 KiloBytes
$size = @{label="Size(KB)";expression={$_.length/1KB}}
# Create an additional calculated property with the number of Days since the file was last accessed.
# You can also shorten the key names to be 'l', and 'e', or use Name instead of Label.
$days = @{l="Days";e={((Get-Date) - $_.LastAccessTime).Days}}
# You can also shorten the name of your label key to 'l' and your expression key to 'e'.
Get-ChildItem $PSHOME -File | Select-Object Name, $size, $days
```

```Output
Name                        Size(KB)        Days
----                        --------        ----
Certificate.format.ps1xml   12.5244140625   223
Diagnostics.Format.ps1xml   4.955078125     223
DotNetTypes.format.ps1xml   134.9833984375  223
```

## PARAMETERS

### -ExcludeProperty командлета

Указывает свойства, которые этот командлет исключает из операции. Разрешено использовать подстановочные знаки.

Начиная с PowerShell 6, больше не требуется включать параметр **Property** для **ExcludeProperty командлета** в работу.

```yaml
Type: System.String[]
Parameter Sets: DefaultParameter, SkipLastParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Експандпроперти

Задает свойство, которое нужно выбрать, и указывает, что нужно попытаться расширить его.

- Если указанное свойство является массивом, каждое значение массива включается в выход.
- Если указанное свойство является объектом, то свойства объектов разворачиваются для каждого объекта **InputObject** .

В любом случае **тип** выходных данных объектов будет соответствовать **типу** развернутого свойства.

Если указан параметр **Property** , `Select-Object` попытается добавить каждое выбранное свойство как **NoteProperty** в каждый выведенный объект.

> [!WARNING]
> Если возникает ошибка: SELECT: свойство не может быть обработано, так как свойство `<PropertyName>` уже существует, учтите следующее.
> Обратите внимание, что при использовании `-ExpandProperty` `Select-Object` не может заменить существующее свойство.
> Это означает следующее:
>
> - Если развернутый объект имеет свойство с тем же именем, возникнет ошибка.
> - Если у *выбранного* объекта есть свойство с тем же именем, что и у *развернутого* свойства объектов, возникнет ошибка.

```yaml
Type: System.String
Parameter Sets: DefaultParameter, SkipLastParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -First

Указывает число объектов, которое нужно выбрать с начала массива входных объектов.

```yaml
Type: System.Int32
Parameter Sets: DefaultParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Index

Выбирает объекты из массива в соответствии со значениями индекса. Введите индексы в виде разделенного запятыми списка. Индексы массива начинаются с нуля, то есть 0 представляет первое значение, а (n-1) — последнее значение.

```yaml
Type: System.Int32[]
Parameter Sets: IndexParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Указывает объекты, которые необходимо передать в командлет по конвейеру. Этот параметр позволяет передавать объекты в `Select-Object` .

При передаче объектов в параметр **InputObject** вместо использования конвейера `Select-Object` обрабатывает **InputObject** как отдельный объект, даже если это значение является коллекцией. Рекомендуется использовать конвейер при передаче коллекций в `Select-Object` .

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

### -Last

Указывает число объектов, которое нужно выбрать с конца массива входных объектов.

```yaml
Type: System.Int32
Parameter Sets: DefaultParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Property

Указывает свойства, которые нужно выбрать. Эти свойства добавляются в выходные объекты в качестве элементов **NoteProperty** . Разрешено использовать подстановочные знаки.

Значением параметра **Property** может быть новое вычисляемое свойство. Чтобы создать вычисляемое свойство, используйте хэш-таблицу.

Допустимые разделы следующие:

- Имя (или метка) — `<string>`
- Выражение — `<string>` или `<script block>`

Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).

```yaml
Type: System.Object[]
Parameter Sets: DefaultParameter, SkipLastParameter
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Skip

Пропускает (не выбирает) указанное число элементов. По умолчанию параметр **Skip** подсчитывает число с начала массива или списка объектов, но если команда использует **последний** параметр, она подсчитывается из конца списка или массива.

В отличие от параметра **Index** , значение которого отсчитывается от 0, параметр **Skip** начинается с единицы.

```yaml
Type: System.Int32
Parameter Sets: DefaultParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Скипласт

Пропускает (не выбирает) указанное число элементов из конца списка или массива. Работает так же, как при использовании функции **Skip** вместе с **последним** параметром.

В отличие от параметра **index** , при котором отсчет начинается с 0, параметр **скипласт** начинается с 1.

```yaml
Type: System.Int32
Parameter Sets: SkipLastParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — Уникальный

Указывает, что, если подмножество входных объектов имеет идентичные свойства и значения, выбран будет только один член подмножества.

Этот параметр чувствителен к регистру. Поэтому строки, которые отличаются только регистром символов, считаются уникальными.

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

### -Wait

Указывает, что командлет отключает оптимизацию. PowerShell выполняет команды в том порядке, в котором они отображаются в конвейере команд, и позволяет им создавать все объекты. По умолчанию при включении `Select-Object` команды с **первым** или **индексным** параметром в конвейере команд PowerShell останавливает команду, создающую объекты, как только выбранное число объектов будет создано.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DefaultParameter, IndexParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Скипиндекс

```yaml
Type: System.Int32[]
Parameter Sets: SkipIndexParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### System.Management.Automation.PSObject

Любой объект можно передать по конвейеру в `Select-Object` .

## Выходные данные

### System.Management.Automation.PSObject

## ПРИМЕЧАНИЯ

- Также можно ссылаться на `Select-Object` командлет по его встроенному псевдониму `select` . Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

- Функция оптимизации `Select-Object` доступна только для команд, которые записывают объекты в конвейер по мере их обработки. Она не действует для команд, которые буферизуют обработанные объекты и записывают их в виде коллекции. При разработке командлетов рекомендуется немедленно записывать объекты. Дополнительные сведения см. в статье _Создание отдельных записей в конвейере_ в [строго рекомендуемых рекомендациях по разработке](/powershell/scripting/developer/windows-powershell).

## Связанные ссылки

[about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[Group-Object](Group-Object.md)

[Sort-Object](Sort-Object.md)

[Where-Object](../Microsoft.PowerShell.Core/Where-Object.md)
