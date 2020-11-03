---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-custom?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Custom
ms.openlocfilehash: 89c7e8f1b70552e735fccd7b2fd45f951b81f928
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2020
ms.locfileid: "93230322"
---
# Format-Custom

## Краткий обзор
Использует пользовательское представление для форматирования выходных данных.

## SYNTAX

```
Format-Custom [[-Property] <Object[]>] [-Depth <Int32>] [-GroupBy <Object>] [-View <String>]
 [-ShowError] [-DisplayError] [-Force] [-Expand <String>] [-InputObject <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION

`Format-Custom`Командлет форматирует выходные данные команды, как определено в альтернативном представлении.
`Format-Custom` предназначен для отображения представлений, которые не просто являются таблицами или просто списками. Можно использовать представления, определенные в `*format.PS1XML` файлах в каталоге PowerShell, или создать собственные представления в новых файлах ps1xml и использовать `Update-FormatData` командлет, чтобы добавить их в PowerShell.

## Примеры

### Пример 1. Форматирование выходных данных с помощью пользовательского представления

```powershell
Get-Command Start-Transcript | Format-Custom -View MyView
```

Эта команда форматирует сведения о `Start-Transcript` командлете в формате, определенном представлением MyView, настраиваемым представлением, созданным пользователем. Чтобы успешно выполнить эту команду, необходимо сначала создать новый файл PS1XML, определить представление **MyView** , а затем использовать `Update-FormatData` команду, чтобы добавить файл ps1xml в PowerShell.

### Пример 2. Форматирование выходных данных с помощью представления по умолчанию

```powershell
Get-Process Winlogon | Format-Custom
```

Эта команда форматирует сведения о процессе **Winlogon** в альтернативном настраиваемом представлении.
Поскольку команда не использует параметр **View** , `Format-Custom` использует пользовательское представление по умолчанию для форматирования данных.

### Пример 3. Устранение ошибок формата

В следующих примерах показаны результаты добавления параметров **DisplayError** или **ShowError** в выражение.

```powershell
PC /> Get-Date | Format-Custom DayOfWeek,{ $_ / $null } -DisplayError

class DateTime
{
  DayOfWeek = Friday
   $_ / $null  = #ERR
}


PC /> Get-Date | Format-Custom DayOfWeek,{ $_ / $null } -ShowError

class DateTime
{
  DayOfWeek = Friday
   $_ / $null  =
}

Failed to evaluate expression " $_ / $null ".
+ CategoryInfo          : InvalidArgument: (12/21/2018 8:01:04 AM:PSObject) [], RuntimeException
+ FullyQualifiedErrorId : PSPropertyExpressionError
```

## PARAMETERS

### -Depth

Задает количество столбцов в отображаемых данных.

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

Отображает сообщения об ошибках в командной строке. Этот параметр редко используется, но его можно использовать в качестве вспомогательного средства отладки при форматировании выражений в `Format-Custom` команде, и выражения не работают.

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

Форматирует объект коллекции, а также объекты, содержащиеся в коллекции. Этот параметр предназначен для форматирования объектов, поддерживающих интерфейс **System. Collections. ICollection** . Значение по умолчанию — **енумонли** .

Допустимые значения:

- EnumOnly — отображаются свойства объектов в коллекции.
- CoreOnly — отображаются свойства объекта коллекции.
- Оба: отображает свойства объекта коллекции и объекты в коллекции.

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

Заставляет командлет отображать полные сведения об ошибках. Используйте с параметрами **DisplayError** или **ShowError** . По умолчанию при записи объекта ошибки в поток ошибок или поток отображения отображаются только некоторые сведения об ошибке.

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

- Имя (или метка) `<string>`
- Выражение `<string>` или `<script block>`
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

Если этот параметр не указан, свойства включаются в вывод в зависимости от отображаемого объекта. **Свойство** имени параметра является необязательным. Нельзя использовать **Свойства** и параметры **представления** в одной команде.

Значением параметра **Property** может быть новое вычисляемое свойство. Вычисляемое свойство может быть блоком скрипта или хэш-таблицей. Допустимые пары "ключ-значение":

- Выражение — `<string>` или `<script block>`
- Длина `<int32>`

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

Отправляет ошибки по конвейеру. Этот параметр редко используется, но его можно использовать в качестве вспомогательного средства отладки при форматировании выражений в `Format-Custom` команде, и выражения не работают.

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

Указывает имя альтернативного формата или представления. Если опустить этот параметр, `Format-Custom` использует настраиваемое представление по умолчанию. Нельзя использовать **Свойства** и параметры **представления** в одной команде.

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

Любой объект можно передать по конвейеру в `Format-Custom` .

## Выходные данные

### Microsoft.PowerShell.Commands.Internal.Format

`Format-Custom` Возвращает объекты формата, представляющие отображение.

## ПРИМЕЧАНИЯ

`Format-Custom` предназначен для отображения представлений, которые не просто являются таблицами или просто списками. Чтобы отобразить альтернативное табличное представление, используйте `Format-Table` . Чтобы отобразить альтернативное представление списка, используйте `Format-List` .

Также можно ссылаться `Format-Custom` по встроенному псевдониму `fc` . Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

Параметр **GroupBy** предполагает, что объекты сортируются. Перед использованием `Format-Custom` для группирования объектов используйте `Sort-Object` для сортировки.

## Связанные ссылки

[about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[Format-Hex](Format-Hex.md)

[Format-List](Format-List.md)

[Format-Table](Format-Table.md)

[Format-Wide](Format-Wide.md)

[Get-Process](../Microsoft.PowerShell.Management/Get-Process.md)
