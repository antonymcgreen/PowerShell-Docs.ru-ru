---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-formatdata?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-FormatData;
ms.openlocfilehash: 0024bb83b983d0b13e2fbfafb24505849acf15f6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227205"
---
# Get-FormatData;

## Краткий обзор
Получает данные форматирования в текущем сеансе.

## SYNTAX

```
Get-FormatData [[-TypeName] <String[]>] [-PowerShellVersion <Version>] [<CommonParameters>]
```

## DESCRIPTION

`Get-FormatData`Командлет возвращает данные форматирования в текущем сеансе.

Данные форматирования в сеансе включают данные форматирования из `Format.ps1xml` файлов форматирования, такие как в `$PSHOME` каталоге, форматирование данных для модулей, импортированных в сеанс, и форматирование данных для команд, импортируемых в сеанс с помощью `Import-PSSession` командлета.

С помощью этого командлета можно изучать данные форматирования. Затем можно использовать `Export-FormatData` командлет для сериализации объектов, преобразования их в формат XML и сохранения в `Format.ps1xml` файлах.

Дополнительные сведения о файлах форматирования в PowerShell см. в разделе [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).

## Примеры

### Пример 1. получение всех данных форматирования

В этом примере выполняется получение всех данных форматирования в сеансе.

```powershell
Get-FormatData
```

### Пример 2. получение данных форматирования по имени типа

Этот пример возвращает элементы данных форматирования, имена которых начинаются с `System.Management.Automation.Cmd` .

```powershell
Get-FormatData -TypeName 'System.Management.Automation.Cmd*'
```

### Пример 3. Проверка объекта данных форматирования

В этом примере показано, как получить объект данных форматирования и изучить его свойства.

```powershell
$F = Get-FormatData -TypeName 'System.Management.Automation.Cmd*'
$F
```

```Output
TypeName        FormatViewDefinition
--------        --------------------
HelpInfoShort   {help , TableControl}
```

```powershell
$F.FormatViewDefinition[0].control
```

```Output
Headers          : {System.Management.Automation.TableControlColumnHeader,
                   System.Management.Automation.TableControlColumnHeader,
                   System.Management.Automation.TableControlColumnHeader,
                   System.Management.Automation.TableControlColumnHeader}
Rows             : {System.Management.Automation.TableControlRow}
AutoSize         : False
HideTableHeaders : False
GroupBy          :
OutOfBand        : False
```

```powershell
$F.FormatViewDefinition[0].control.Headers
```

```Output
Label       Alignment Width
-----       --------- -----
CommandType Undefined    15
Name        Undefined    50
Version     Undefined    10
Source      Undefined     0
```

### Пример 4. получение данных форматирования и их экспорт

В этом примере показано, как использовать `Get-FormatData` и `Export-FormatData` для экспорта данных форматирования, добавленных модулем.

```powershell
$A = Get-FormatData
Import-Module bitstransfer
$B = Get-FormatData
Compare-Object $A $B
```

```Output
InputObject                                                SideIndicator
-----------                                                -------------
Microsoft.BackgroundIntelligentTransfer.Management.BitsJob =>
```

```powershell
Get-FormatData *bits* | Export-FormatData -FilePath c:\test\bits.format.ps1xml
Get-Content c:\test\bits.format.ps1xml
```

```Output
<?xml version="1.0" encoding="utf-8"?><Configuration><ViewDefinitions>
<View><Name>Microsoft.BackgroundIntelligentTransfer.Management.BitsJob</Name>
...
```

Первые четыре команды используют `Get-FormatData` `Import-Module` `Compare-Object` командлеты, и для задания типа формата, который модуль **BitsTransfer** добавляет в сеанс.

Пятая команда использует `Get-FormatData` командлет для получения типа формата, добавляемого модулем **BitsTransfer** . Он использует оператор конвейера ( `|` ) для отправки в командлет объекта типа формата `Export-FormatData` , который преобразует его обратно в XML и сохраняет в указанном `format.ps1xml` файле.

Последняя команда показывает выдержку из `format.ps1xml` содержимого файла.

### Пример 5. получение данных форматирования на основе указанной версии PowerShell

В этом примере показано, как использовать `Get-FormatData` для получения данных форматирования для указанных **имени TypeName** и версии PowerShell.

```powershell
Get-FormatData -TypeName 'Microsoft.Powershell.Utility.FileHash' -PowerShellVersion $PSVersionTable.PSVersion

TypeNames                               FormatViewDefinition
---------                               --------------------
{Microsoft.Powershell.Utility.FileHash} {Microsoft.Powershell.Utility.FileHash}
```

## PARAMETERS

### -PowerShellVersion

Укажите версию PowerShell, которую этот командлет получает для данных форматирования. Введите значение из двух цифр, разделенных точкой.

Этот параметр был добавлен в PowerShell 5,1 для улучшения совместимости при удаленном использовании компьютеров с более ранними версиями PowerShell.

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TypeName

Указывает имена типов, которые этот командлет получает для данных форматирования.
Введите имена типов.
Разрешено использовать подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

В этот командлет нельзя передать входные данные.

## Выходные данные

### System. Management. Automation. Екстендедтипедефинитион

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Export-FormatData](Export-FormatData.md)

[Update-FormatData](Update-FormatData.md)
