---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-formatdata?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-FormatData
ms.openlocfilehash: d89d80b296d8800d65c5acfae37434e9b3f3bce9
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226186"
---
# Export-FormatData

## Краткий обзор
Сохраняет данные форматирования текущего сеанса в файле форматирования.

## SYNTAX

### ByPath (по умолчанию)

```
Export-FormatData -InputObject <ExtendedTypeDefinition[]> -Path <String> [-Force] [-NoClobber]
 [-IncludeScriptBlock] [<CommonParameters>]
```

### ByLiteralPath

```
Export-FormatData -InputObject <ExtendedTypeDefinition[]> -LiteralPath <String> [-Force] [-NoClobber]
 [-IncludeScriptBlock] [<CommonParameters>]
```

## DESCRIPTION

`Export-FormatData`Командлет создает файлы форматирования PowerShell (format.ps1XML) из объектов форматирования в текущем сеансе. Он принимает объекты **екстендедтипедефинитион** , которые `Get-FormatData` возвращают и сохраняет их в файле в формате XML.

PowerShell использует данные в файлах форматирования (format.ps1XML), чтобы создать отображение по умолчанию Microsoft .NET объектов платформы в сеансе. Вы можете просматривать и изменять файлы форматирования и использовать командлет Update-FormatData для добавления данных форматирования в сеанс.

Дополнительные сведения о файлах форматирования в PowerShell см. в разделе [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).

## Примеры

### Пример 1. экспорт данных в формате сеанса

```powershell
Get-FormatData -TypeName "*" -PowerShellVersion 5.1 | Export-FormatData -Path "allformat.ps1xml" -IncludeScriptBlock
```

Эта команда экспортирует все данные форматирования из сеанса в файл AllFormat.ps1xml.

Команда использует `Get-FormatData` командлет для получения данных формата в сеансе. Значение `*` (ALL) для параметра **TypeName** указывает командлету получить все данные в сеансе.

Команда использует оператор конвейера ( `|` ) для отправки данных формата из `Get-FormatData` команды в `Export-FormatData` командлет, который экспортирует данные формата в файл AllFormat.ps1.

`Export-FormatData`Команда использует параметр **IncludeScriptBlock** для включения блоков скрипта в формат данных в файле.

### Пример 2. экспорт данных формата для типа

```powershell
$F = Get-FormatData -TypeName "helpinfoshort" -PowerShellVersion 5.1
Export-FormatData -InputObject $F -Path "c:\test\help.format.ps1xml" -IncludeScriptBlock
```

Эти команды экспортируют данные формата для типа **HelpInfoShort** в XML-файл Help.format.ps1.

Первая команда использует `Get-FormatData` командлет для получения данных формата для типа **HelpInfoShort** и сохраняет его в `$F` переменной.

Вторая команда использует параметр **InputObject** `Export-FormatData` командлета для ввода данных формата, сохраненных в `$F` переменной. Он также использует параметр **IncludeScriptBlock** для включения в выходные данные блоков сценариев.

### Пример 3. экспорт данных формата без блока сценария

```powershell
Get-FormatData -TypeName "System.Diagnostics.Process" -PowerShellVersion 5.1 | Export-FormatData -Path process.format.ps1xml
Update-FormatData -PrependPath ".\process.format.ps1xml"
Get-Process p*
```

```Output
Handles  NPM(K)  PM(K)  WS(K) VM(M)   CPU(s)    Id ProcessName
-------  ------  -----  ----- -----   ------    -- -----------
323                                       5600 powershell
336                                       3900 powershell_ise
138                                       4076 PresentationFontCache
```

В этом примере показан результат пропуска параметра **IncludeScriptBlock** из `Export-FormatData` команды.

Первая команда использует `Get-FormatData` командлет для получения данных формата для объекта **System. Diagnostics. Process** , возвращаемого командлетом Get-Process. Команда использует оператор конвейера ( `|` ) для отправки данных форматирования в `Export-FormatData` командлет, который экспортирует его в Process.format.ps1XML-файл в текущем каталоге.

В этом случае `Export-FormatData` команда не использует параметр **IncludeScriptBlock** .

Вторая команда использует `Update-FormatData` командлет для добавления Process.format.ps1XML-файла в текущий сеанс. Команда использует параметр **препендпас** , чтобы убедиться, что данные форматирования для объектов обработки в Process.format.ps1XML-файле найдены перед стандартными данными форматирования для объектов обработки.

Третья команда демонстрирует последствия этого изменения. Команда использует `Get-Process` командлет для получения процессов, имена которых начинаются с P. Выходные данные показывают, что значения свойств, вычисляемые с помощью блоков скриптов, отсутствуют на экране.

## PARAMETERS

### -Force

Принудительное выполнение команды без запроса на подтверждение пользователем.

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

### -IncludeScriptBlock

Указывает, экспортируются ли блоки скриптов в данных формата.

Так как блоки сценариев содержат код и могут использоваться во вредоносных целях, по умолчанию они не экспортируются.

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

### -InputObject

Указывает объекты данных форматирования для экспорта. Введите переменную, которая содержит объекты, или команду, которая получает объекты, например `Get-FormatData` команду. Можно также передать объекты по конвейеру из `Get-FormatData` в `Export-FormatData` .

```yaml
Type: System.Management.Automation.ExtendedTypeDefinition[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LiteralPath

Задает расположение выходного файла. В отличие от параметра **Path** , значение **LiteralPath** используется именно так, как оно введено. Никакие символы не интерпретируются как знаки подстановки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoClobber

Указывает, что командлет не перезаписывает существующие файлы. По умолчанию `Export-FormatData` перезаписывает файлы без предупреждения, если только файл не имеет атрибута только для чтения.

Чтобы направлять `Export-FormatData` Перезапись файлов только для чтения, используйте параметр **Force** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Задает расположение выходного файла.
Введите путь (необязательно) и имя файла с расширением format.ps1xml.
Если опустить путь, `Export-FormatData` создает файл в текущем каталоге.

Если используется расширение имени файла, отличное от. ps1xml, `Update-FormatData` командлет не сможет распознать файл.

При указании существующего файла `Export-FormatData` перезаписывает файл без предупреждения, если только файл не имеет атрибута только для чтения. Чтобы перезаписать файл, доступный только для чтения, используйте параметр **Force** . Чтобы предотвратить перезапись файлов, используйте параметр **NoClobber** .

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases: FilePath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System. Management. Automation. Екстендедтипедефинитион

Вы можете передать объекты **екстендедтипедефинитион** из `Get-FormatData` в `Export-FormatData` .

## Выходные данные

### Нет

`Export-FormatData` не возвращает никаких объектов.
Он создает файл и сохраняет его по указанному пути.

## ПРИМЕЧАНИЯ

- Для использования любого файла форматирования, включая экспортированный, политика выполнения сеанса должна разрешать запуск сценариев и файлов конфигурации. Подробнее см. в разделе [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).

## Связанные ссылки

[Get-FormatData;](Get-FormatData.md)

[Update-FormatData](Update-FormatData.md)
