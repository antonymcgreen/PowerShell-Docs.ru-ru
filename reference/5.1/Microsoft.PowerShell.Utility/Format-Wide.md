---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-wide?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Wide
ms.openlocfilehash: f2dccb4d0fb2d39114e5b24af8085424938ea9c7
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2020
ms.locfileid: "93230313"
---
# Format-Wide

## Краткий обзор
Форматирует объекты в виде широкой таблицы, в которой отображается только одно свойство каждого объекта.

## SYNTAX

```
Format-Wide [[-Property] <Object>] [-AutoSize] [-Column <int>] [-GroupBy <Object>] [-View <string>]
  [-ShowError] [-DisplayError] [-Force] [-Expand <string>] [-InputObject <psobject>]
  [<CommonParameters>]
```

## DESCRIPTION

`Format-Wide`Командлет форматирует объекты в виде широкой таблицы, в которой отображается только одно свойство каждого объекта. Для определения отображаемого свойства можно использовать параметр **Property** .

## Примеры

### Пример 1. форматирование имен файлов в текущем каталоге

Эта команда отображает имена файлов в текущем каталоге в трех столбцах на весь экран.

```powershell
Get-ChildItem | Format-Wide -Column 3
```

Командлет Get-ChildItem получает объекты, представляющие каждый файл в каталоге. Оператор конвейера (|) передает объекты файлов через конвейер в `Format-Wide` , который форматирует их для вывода. Параметр **Column** указывает количество столбцов.

### Пример 2. форматирование имен разделов реестра

Эта команда выводит на экран имена разделов реестров в разделе HKEY_CURRENT_USER\Software\Microsoft.

```powershell
Get-ChildItem HKCU:\software\microsoft | Format-Wide -Property pschildname -AutoSize
```

Командлет Get-ChildItem получает объекты, представляющие разделы. Путь указывается в разделе HKCU:, на одном из дисков, предоставляемых поставщиком реестра PowerShell, за которым следует путь к ключу. Оператор конвейера (|) передает объекты раздела реестра по конвейеру в `Format-Wide` , который форматирует их для вывода. Параметр **Property** задает имя свойства, а параметр **AutoSize** корректирует столбцы для удобства чтения.

### Пример 3. Устранение ошибок формата

В следующих примерах показаны результаты добавления параметров **DisplayError** или **ShowError** в выражение.

```powershell
PS /> Get-Date | Format-Wide { $_ / $null } -DisplayError


#ERR

PS /> Get-Date | Format-Wide { $_ / $null } -ShowError


Failed to evaluate expression " $_ / $null ".
+ CategoryInfo          : InvalidArgument: (12/21/2018 8:18:01 AM:PSObject) [], RuntimeException
+ FullyQualifiedErrorId : PSPropertyExpressionError
```

## PARAMETERS

### -AutoSize

Корректирует размер столбца и количество столбцов в зависимости от ширины данных. По умолчанию размер и количество столбцов определяются представлением. Нельзя использовать параметры **AutoSize** и **Column** в одной команде.

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

### -Column

Задает количество столбцов в отображаемых данных. Нельзя использовать параметры **AutoSize** и **Column** в одной команде.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayError

Отображает сообщения об ошибках в командной строке. Этот параметр редко используется, но его можно использовать в качестве вспомогательного средства отладки при форматировании выражений в `Format-Wide` команде, и выражения не работают.

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

Форматирует объект коллекции, а также объекты, содержащиеся в коллекции. Этот параметр служит для форматирования объектов, поддерживающих интерфейс ICollection (System.Collections). Значение по умолчанию — **енумонли** .

Допустимые значения:

- EnumOnly — отображаются свойства объектов в коллекции.
- CoreOnly — отображаются свойства объекта коллекции.
- Both — отображаются свойства объекта коллекции и свойства объектов, содержащихся в коллекции.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CoreOnly, EnumOnly, Both

Required: False
Position: Named
Default value: EnumOnly
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Указывает, что этот командлет переопределяет ограничения, препятствующие выполнению команды, так что изменения не нарушают безопасность. Например, параметр **Force** позволяет переопределить атрибут «только для чтения» или создать дополнительные каталоги в пути, не меняя разрешения на доступ к файлу.

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

Форматирует вывод в группы на основе общего свойства или значения. Введите выражение или свойство вывода.

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

Задает объекты для форматирования. Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.

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

- Выражение — `<string>` или `<script block>`
- FormatString `<string>`

Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -ShowError

Отправляет ошибки по конвейеру. Этот параметр редко используется, но его можно использовать в качестве вспомогательного средства отладки при форматировании выражений в `Format-Wide` команде, и выражения не работают.

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

Указывает имя альтернативного формата таблицы или представления. Нельзя использовать **Свойства** и параметры **представления** в одной команде.

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

Любой объект можно передать по конвейеру в `Format-Wide` .

## Выходные данные

### Microsoft.PowerShell.Commands.Internal.Format

`Format-Wide` Возвращает объекты форматирования, представляющие таблицу.

## ПРИМЕЧАНИЯ

Также можно ссылаться `Format-Wide` по встроенному псевдониму `fw` . Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

Параметр **GroupBy** предполагает, что объекты сортируются. Используйте `Sort-Object` перед использованием `Format-Custom` для группирования объектов.

Параметр **View** позволяет указать альтернативный формат для таблицы. Вы можете использовать представления, определенные в `*.format.PS1XML` файлах в каталоге PowerShell, или создать собственные представления в новых файлах ps1xml и использовать `Update-FormatData` командлет для их включения в PowerShell.

Альтернативное представление для параметра **представления** должно использовать формат таблицы. в противном случае команда завершается ошибкой. Если альтернативное представление является списком, используйте `Format-List` . Если альтернативное представление не является ни списком, ни таблицей, используйте командлет Format-Custom.

## Связанные ссылки

[about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[Format-Custom](Format-Custom.md)

[Format-Hex](Format-Hex.md)

[Format-List](Format-List.md)

[Format-Table](Format-Table.md)
