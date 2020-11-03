---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/19/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-list?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-List
ms.openlocfilehash: df013bd6efd127a022d6bd41c5ea5fcca90dbc4a
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2020
ms.locfileid: "93230333"
---
# Format-List

## Краткий обзор
Форматирует вывод как список свойств, в котором каждое свойство отображается на новой строке.

## SYNTAX

```
Format-List [[-Property] <Object[]>] [-GroupBy <Object>] [-View <string>] [-ShowError]
[-DisplayError] [-Force] [-Expand <string>] [-InputObject <psobject>] [<CommonParameters>]
```

## DESCRIPTION

`Format-List`Командлет форматирует выходные данные команды в виде списка свойств, в которых каждое свойство отображается в отдельной строке. Можно использовать `Format-List` для форматирования и вывода всех или выбранных свойств объекта в виде списка (Format-List *).

Так как для каждого элемента в списке доступно больше места, чем в таблице, PowerShell отображает больше свойств объекта в списке, и значения свойств менее вероятно будут обрезаны.

## Примеры

### Пример 1. форматирование компьютерных служб

```powershell
Get-Service | Format-List
```

Эта команда форматирует сведения о службах на компьютере в виде списка. По умолчанию сведения о службах форматируются в виде таблицы. `Get-Service`Командлет возвращает объекты, представляющие службы на компьютере. Оператор конвейера (|) передает результаты по конвейеру в `Format-List` .
Затем `Format-List` команда форматирует сведения о службе в списке и отправляет их в выходной командлет по умолчанию для вывода.

### Пример 2. форматирование файлов PS1XML

Эти команды отображают сведения о файлах PS1XML в каталоге PowerShell в виде списка.

```powershell
$A = Get-ChildItem $pshome\*.ps1xml
Format-List -InputObject $A
```

Первая команда получает объекты, представляющие файлы, и сохраняет их в `$A` переменной.

Вторая команда использует `Format-List` для форматирования сведений об объектах, хранящихся в `$A` . Эта команда использует параметр **InputObject** для передачи переменной в `Format-List` , который затем отправляет форматированные выходные данные в выходной командлет по умолчанию для вывода.

### Пример 3. форматирование свойств процесса по имени

Эта команда отображает имя, базовый приоритет и класс приоритета каждого процесса на компьютере.

```powershell
Get-Process | Format-List -Property name, basepriority, priorityclass
```

Он использует `Get-Process` командлет для получения объекта, представляющего каждый процесс. Оператор конвейера (|) передает объекты процесса через конвейер в `Format-List` . `Format-List` Форматирует процессы в виде списка указанных свойств. Имя параметра *Свойства* является необязательным, поэтому его можно опустить.

### Пример 4. форматирование всех свойств процесса

Эта команда отображает все свойства процесса Winlogon.

```powershell
Get-Process winlogon | Format-List -Property *
```

Для получения объекта, представляющего процесс Winlogon, используется командлет Get-Process. Оператор конвейера (|) передает объект процесса Winlogon через конвейер в `Format-List` . Команда использует параметр *Property* для указания свойств и \* для указания всех свойств.
Поскольку имя параметра *Свойства* является необязательным, его можно опустить и ввести команду как `Format-List *` . `Format-List` автоматически отправляет результаты в командлет вывода по умолчанию для вывода.

### Пример 5. Устранение ошибок формата

В следующих примерах показаны результаты добавления параметров **DisplayError** или **ShowError** в выражение.

```powershell
PC /> Get-Date | Format-List DayOfWeek,{ $_ / $null } -DisplayError

DayOfWeek    : Friday
 $_ / $null  : #ERR

PC /> Get-Date | Format-List DayOfWeek,{ $_ / $null } -ShowError

DayOfWeek    : Friday
 $_ / $null  :

Failed to evaluate expression " $_ / $null ".
+ CategoryInfo          : InvalidArgument: (12/21/2018 7:59:23 AM:PSObject) [], RuntimeException
+ FullyQualifiedErrorId : PSPropertyExpressionError
```

## PARAMETERS

### -DisplayError

Указывает, что этот командлет отображает ошибки в командной строке. Этот параметр редко используется, но его можно использовать в качестве вспомогательного средства отладки при форматировании выражений в `Format-List` команде, и выражения не работают.

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

### -Expand

Задает отформатированный объект коллекции, а также объекты в коллекции. Этот параметр служит для форматирования объектов, поддерживающих интерфейс ICollection (System.Collections). По умолчанию используется значение EnumOnly. Допустимые значения для этого параметра:

- Енумонли. отображаются свойства объектов в коллекции.
- Кореонли. отображаются свойства объекта коллекции.
- Both. отображаются свойства объекта коллекции и свойства объектов, содержащихся в коллекции.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CoreOnly, EnumOnly, Both

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Указывает, что этот командлет отображает все сведения об ошибке. Используйте с параметром **DisplayError** или **ShowError** . По умолчанию при записи объекта ошибки в поток ошибок или поток отображения отображаются только некоторые сведения об ошибке.

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

### -GroupBy

Задает выходные данные в группах на основе общего свойства или значения. Введите выражение или свойство вывода.

Значением параметра **GroupBy** может быть новое вычисляемое свойство. Вычисляемое свойство может быть блоком скрипта или хэш-таблицей. Допустимые пары "ключ-значение":

- Имя (или метка) — `<string>`
- Выражение — `<string>` или `<script block>`
- FormatString `<string>`

Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Задает объекты, подлежащие форматированию. Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.

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

### -Property

Задает свойства объекта, которые будут включены в вывод, и порядок их вывода.
Разрешено использовать подстановочные знаки.

Если этот параметр не указан, свойства включаются в вывод в зависимости от отображаемого объекта. Имя параметра "свойство" является необязательным. Нельзя использовать **Свойства** и параметры **представления** в одной команде.

Значением параметра **Property** может быть новое вычисляемое свойство. Вычисляемое свойство может быть блоком скрипта или хэш-таблицей. Допустимые пары "ключ-значение":

- Имя (или метка) — `<string>`
- Выражение — `<string>` или `<script block>`
- FormatString `<string>`

Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -ShowError

Указывает, что командлет отправляет ошибки через конвейер. Этот параметр редко используется, но его можно использовать в качестве вспомогательного средства отладки при форматировании выражений в `Format-List` команде, и выражения не работают.

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

### -View

Указывает имя альтернативного формата или представления списка. Нельзя использовать **Свойства** и параметры **представления** в одной команде.

```yaml
Type: System.String
Parameter Sets: (All)
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

Любой объект можно передать по конвейеру в `Format-List` .

## Выходные данные

### Microsoft.PowerShell.Commands.Internal.Format

`Format-List` Возвращает объекты формата, представляющие список.

## ПРИМЕЧАНИЯ

Вы также можете ссылаться на Format-List по его встроенному псевдониму FL. Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

Командлеты формата, такие как `Format-List` , упорядочивают отображаемые данные, но не отображают их.
Данные отображаются выходными функциями PowerShell и командлетами, содержащими команду Out (командлеты Out), например `Out-Host` или `Out-File` .

Если командлет format не используется, PowerShell применяет этот формат по умолчанию для каждого отображаемого объекта.

Параметр **GroupBy** предполагает, что объекты сортируются. Используйте Sort-Object перед использованием `Format-List` для группирования объектов.

Параметр **View** позволяет указать альтернативный формат для таблицы. Можно использовать представления, определенные в `*.format.PS1XML` файлах в каталоге PowerShell, или создать собственные представления в новых файлах ps1xml и использовать командлет Update-FormatData, чтобы включить их в PowerShell.

Альтернативное представление для параметра **представления** должно использовать формат списка, в противном случае команда завершается ошибкой. Если альтернативное представление является таблицей, используйте `Format-Table` . Если альтернативное представление не является списком или таблицей, используйте `Format-Custom` .

## Связанные ссылки

[about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[Format-Custom](Format-Custom.md)

[Format-Hex](Format-Hex.md)

[Format-Table](Format-Table.md)

[Format-Wide](Format-Wide.md)
