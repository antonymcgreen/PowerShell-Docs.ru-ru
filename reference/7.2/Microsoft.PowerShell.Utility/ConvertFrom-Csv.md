---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/21/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-csv?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Csv
ms.openlocfilehash: 951a1e4ecc46b401ae066bc3b138f264a4313e65
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599998"
---
# ConvertFrom-Csv

## Краткий обзор
Преобразует свойства объектов в формате с разделителями-запятыми (CSV) в версии CSV исходных объектов.

## SYNTAX

### Delimiter (по умолчанию)

```
ConvertFrom-Csv [[-Delimiter] <Char>] [-InputObject] <PSObject[]> [-Header <String[]>]
 [<CommonParameters>]
```

### UseCulture

```
ConvertFrom-Csv -UseCulture [-InputObject] <PSObject[]> [-Header <String[]>] [<CommonParameters>]
```

## DESCRIPTION

`ConvertFrom-Csv`Командлет создает объекты из строк переменной длины CSV, которые создаются `ConvertTo-Csv` командлетом.

С помощью параметров этого командлета можно указать строку заголовков столбцов, которая определяет имена результирующих объектов, указать разделитель элементов или направить этот командлет для использования разделителя списка для текущего языка и региональных параметров в качестве разделителя.

Создаваемые объекты `ConvertFrom-Csv` — это CSV-версии исходных объектов. Значения свойств объектов CSV представляют собой строковые версии значений свойств исходных объектов. Версии CSV объектов не имеют методов.

Также можно использовать `Export-Csv` `Import-Csv` командлеты и для преобразования объектов в строки CSV в файле (и обратно). Эти командлеты аналогичны `ConvertTo-Csv` `ConvertFrom-Csv` командлетам и, за исключением того, что они сохраняют строки CSV в файле.

## Примеры

### Пример 1. Преобразование процессов на локальном компьютере в формат CSV

В этом примере показано, как преобразовать процессы на локальном компьютере в формат CSV, а затем восстановить их в форму объекта.

```powershell
$P = Get-Process | ConvertTo-Csv
$P | ConvertFrom-Csv
```

`Get-Process`Командлет отправляет процессы по конвейеру в `ConvertTo-Csv` . `ConvertTo-Csv`Командлет преобразует объекты процесса в последовательность строк CSV. `ConvertFrom-Csv`Командлет преобразует строки CSV в CSV-версии исходных объектов процессов. Строки CSV сохраняются в `$P` переменной.

### Пример 2. преобразование объекта данных в формат CSV, а затем в формат CSV-объекта

В этом примере показано, как преобразовать объект данных в формат CSV, а затем в формат объекта CSV.

```powershell
$Date = Get-Date | ConvertTo-Csv -Delimiter ';'
ConvertFrom-Csv -InputObject $Date -Delimiter ';'
```

Первая команда использует `Get-Date` для отправки текущей даты и времени по конвейеру в `ConvertTo-Csv` . `ConvertTo-Csv`Командлет преобразует объект Date в последовательность строк CSV.
Параметр- **Разделитель** используется для указания разделителя с точкой с запятой. Строки сохраняются в `$Date` переменной.

### Пример 3. Использование параметра Header для изменения имен свойств

В этом примере показано, как использовать параметр **Header** объекта `ConvertFrom-Csv` для изменения имен свойств в результирующем импортируемом объекте.

```powershell
$J = Start-Job -ScriptBlock { Get-Process } | ConvertTo-Csv  -NoTypeInformation
$Header = 'State', 'MoreData', 'StatusMessage', 'Location', 'Command', 'StateInfo', 'Finished', 'InstanceId', 'Id', 'Name', 'ChildJobs', 'BeginTime', 'EndTime', 'JobType', 'Output', 'Error', 'Progress', 'Verbose', 'Debug', 'Warning', 'Information'
# Delete the default header from $J
$J = $J[1..($J.count - 1)]
$J | ConvertFrom-Csv -Header $Header
```

```Output
State         : Running
MoreData      : True
StatusMessage :
Location      : localhost
Command       : Get-Process
StateInfo     : Running
Finished      : System.Threading.ManualResetEvent
InstanceId    : a259eb63-6824-4b97-a033-305108ae1c2e
Id            : 1
Name          : Job1
ChildJobs     : System.Collections.Generic.List`1[System.Management.Automation.Job]
BeginTime     : 12/20/2018 18:59:57
EndTime       :
JobType       : BackgroundJob
Output        : System.Management.Automation.PSDataCollection`1[System.Management.Automation.PSObject]
Error         : System.Management.Automation.PSDataCollection`1[System.Management.Automation.ErrorRecord]
Progress      : System.Management.Automation.PSDataCollection`1[System.Management.Automation.ProgressRecord]
Verbose       : System.Management.Automation.PSDataCollection`1[System.Management.Automation.VerboseRecord]
Debug         : System.Management.Automation.PSDataCollection`1[System.Management.Automation.DebugRecord]
Warning       : System.Management.Automation.PSDataCollection`1[System.Management.Automation.WarningRecord]
Information   : System.Management.Automation.PSDataCollection`1[System.Management.Automation.InformationRecord]
```

`Start-Job`Командлет запускает фоновое задание, которое выполняется `Get-Process` . Объект задания отправляется в конвейер `ConvertTo-Csv` и преобразуется в строку CSV. Параметр **NoTypeInformation** удаляет заголовок сведений о типе из выходных данных CSV и является необязательным в PowerShell Core. `$Header`Переменная содержит пользовательский заголовок, который заменяет следующие значения по умолчанию: **хасморедата**, **JobStateInfo**, **псбегинтиме**, **псендтиме** и **псжобтипенаме**. `$J`Переменная содержит строку CSV и используется для удаления заголовка по умолчанию. `ConvertFrom-Csv`Командлет преобразует строку CSV в **PSCustomObject** и использует параметр **Header** для применения `$Header` переменной.

### Пример 4. преобразование строк CSV объектов службы

В этом примере показано, как использовать `ConvertFrom-Csv` командлет с параметром **UseCulture** .

```powershell
(Get-Culture).TextInfo.ListSeparator
$Services = (Get-Service | ConvertTo-Csv)
ConvertFrom-Csv -InputObject $Services -UseCulture
```

`Get-Culture`Командлет использует вложенные свойства **TextInfo** и **ListSeparator** для получения разделителя списка по умолчанию текущего языка и региональных параметров. `Get-Service`Командлет отправляет объекты службы по конвейеру в `ConvertTo-Csv` . `ConvertTo-Csv`Преобразует объекты службы в последовательность строк CSV. Строки CSV хранятся в `$Services` переменной. `ConvertFrom-Csv`Командлет использует параметр **InputObject** и преобразует строки CSV из `$Services` переменной. Параметр **UseCulture** использует разделитель списка по умолчанию текущего языка и региональных параметров.

При использовании параметра **UseCulture** убедитесь, что используемый по умолчанию разделитель списка текущего языка и региональных параметров соответствует разделителю, используемому в строках CSV. В противном случае `ConvertFrom-Csv` не может формировать объекты из строк CSV.

## PARAMETERS

### -Delimiter

Задает разделитель для значений свойств в строках CSV.
Разделитель по умолчанию — запятая (,).

Введите символ, например двоеточие (:).
Указание точки с запятой (;) заключите его в одинарные кавычки.

Если в файле указать символ, отличный от действительного разделителя строк, то `ConvertFrom-Csv` не сможет создать объекты из строк CSV и будет возвращать строки CSV.

```yaml
Type: System.Char
Parameter Sets: Delimiter
Aliases:

Required: False
Position: 1
Default value: comma (,)
Accept pipeline input: False
Accept wildcard characters: False
```

### -Header

Указывает альтернативную строку заголовков столбцов для импортируемой строки. Заголовок столбца определяет имена свойств объектов, созданных `ConvertFrom-Csv` .

Введите заголовки столбцов в виде списка с разделителями-запятыми. Не заключайте в кавычки строку заголовка. Заключить заголовок каждого столбца в одинарные кавычки.

Если ввести меньшее количество заголовков столбцов, чем столбцы данных, оставшиеся столбцы данных будут удалены. Если ввести больше заголовков столбцов, чем столбцы данных, то будут созданы дополнительные заголовки столбцов с пустыми столбцами данных.

При использовании параметра **Header** не указывайте строку заголовка столбца из строк CSV. В противном случае этот командлет создает дополнительный объект на основе элементов в строке заголовка.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Задает строки CSV для преобразования в объекты. Укажите переменную, содержащую строки CSV, либо введите команду или выражение, получающие эти строки. Строки CSV также можно передать в `ConvertFrom-Csv` .

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -UseCulture

Использует разделитель списка для текущего языка и региональных параметров в качестве разделителя элементов. Чтобы найти разделитель списка для языка и региональных параметров, используйте следующую команду: `(Get-Culture).TextInfo.ListSeparator` .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UseCulture
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

В этот командлет можно передать строки CSV.

## Выходные данные

### System.Management.Automation.PSObject

Этот командлет возвращает объекты, описанные в свойствах в строках CSV.

## ПРИМЕЧАНИЯ

Поскольку импортированные объекты являются версиями CSV типа объекта, они не распознаются и не форматируются с помощью записей форматирования типов PowerShell, которые отформатируют версии объектов, отформатированные не в формате CSV.

В формате CSV каждый объект представлен как разделенный запятыми список значений его свойств. Значения свойств преобразуются в строки (с помощью метода **ToString ()** объекта), поэтому они представлены именем значения свойства. Этот командлет не экспортирует методы объекта.

## Связанные ссылки

[ConvertTo-Csv](ConvertTo-Csv.md)

[Export-CSV](Export-Csv.md)

[Import-Csv](Import-Csv.md)

