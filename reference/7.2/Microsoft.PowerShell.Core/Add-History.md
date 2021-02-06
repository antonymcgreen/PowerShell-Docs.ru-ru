---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/add-history?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-History
ms.openlocfilehash: d2c0abb0e6742de3e316fe964d5945375591ef4d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605528"
---
# Add-History

## Краткий обзор
Добавляет записи в журнал сеанса.

## SYNTAX

```
Add-History [[-InputObject] <PSObject[]>] [-Passthru] [<CommonParameters>]
```

## DESCRIPTION

`Add-History`Командлет добавляет записи в конец журнала сеанса, то есть список команд, введенных во время текущего сеанса.

Журнал сеанса — это список команд, введенных за время сеанса. В журнале сеанса представлен порядок выполнения, состояние, время начала и завершения выполнения команды. По мере ввода каждой команды PowerShell добавляет его в журнал, чтобы его можно было использовать повторно. Дополнительные сведения о журнале сеанса см. в разделе [about_History](About/about_History.md).

Журнал сеанса управляется отдельно от журнала, поддерживаемого модулем **PSReadLine** .
Оба журнала доступны в сеансах, где загружен **PSReadLine** . Этот командлет работает только с журналом сеанса. Дополнительные сведения см. в разделе [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).

Командлет можно использовать `Get-History` для получения команд и передачи их в `Add-History` , либо можно экспортировать команды в CSV-или XML файл, затем импортировать команды и передать импортированный файл в `Add-History` . Этот командлет позволяет добавить определенные команды в журнал или создать единый файл журнала, в котором содержатся команды, введенные в течение нескольких сеансов.

## Примеры

### Пример 1. Добавление команд в журнал другого сеанса

Этот пример добавляет команды, введенные в один сеанс PowerShell, в журнал другого сеанса PowerShell.

```powershell
Get-History | Export-Csv c:\testing\history.csv -IncludeTypeInformation
Import-Csv c:\testing\history.csv | Add-History
```

Первая команда получает объекты, представляющие команды в журнале, и экспортирует их в `History.csv` файл.

Вторая команда должна вводится в командной строке другого сеанса. Он использует `Import-Csv` командлет для импорта объектов в `History.csv` файл. Оператор конвейера ( `|` ) передает объекты в `Add-History` командлет, который добавляет объекты, представляющие команды в файле, в `History.csv` текущий журнал сеанса.

### Пример 2. команды Import и Run

Этот пример импортирует команды из `History.xml` файла, добавляет их в текущий журнал сеанса, а затем выполняет команды в объединенном журнале.

```powershell
Import-Clixml c:\temp\history.xml | Add-History -PassThru | ForEach-Object -Process {Invoke-History}
```

Первая команда использует `Import-Clixml` командлет для импорта журнала команд, экспортированного в `History.xml` файл. Оператор конвейера передает команды в `Add-History` командлет, который добавляет команды в текущий журнал сеанса. Параметр **PassThru** передает объекты, представляющие добавленные команды, в конвейер.

Затем команда использует `ForEach-Object` командлет для применения `Invoke-History` команды к каждой из команд в объединенном журнале. `Invoke-History`Команда форматируется как блок скрипта, заключенный в фигурные скобки ( `{}` ), как это  требуется параметру Process `ForEach-Object` командлета.

### Пример 3. Добавление команд в журнал в конец журнала

В этом примере первые пять команд в журнале добавляются в конец списка журнала.

```powershell
Get-History -Id 5 -Count 5 | Add-History
```

`Get-History`Командлет получает пять команд, которые заканчиваются командой 5. Оператор конвейера передает их в `Add-History` командлет, который добавляет их к текущему журналу. `Add-History`Команда не содержит никаких параметров, но PowerShell связывает объекты, переданные через конвейер, с параметром **InputObject** `Add-History` .

### Пример 4. Добавление команд в CSV-файл к текущему журналу

В этом примере команды добавляются в `History.csv` файл в журнал текущего сеанса.

```powershell
$a = Import-Csv c:\testing\history.csv
Add-History -InputObject $a -PassThru
```

`Import-Csv`Командлет импортирует команды в `History.csv` файл и сохраняет его содержимое в переменной `$a` .

Вторая команда использует `Add-History` командлет для добавления команд из `History.csv` в текущий журнал сеанса. Он использует параметр **InputObject** для указания `$a` переменной, а параметр **PassThru** — для создания объекта, отображаемого в командной строке. Без параметра **PassThru** `Add-History` командлет не создает никаких выходных данных.

### Пример 5. Добавление команд в XML-файл в текущий журнал

В этом примере команды добавляются в `history.xml` файл в журнал текущего сеанса.

```powershell
Add-History -InputObject (Import-Clixml c:\temp\history.xml)
```

Параметр **InputObject** передает результаты команды в круглые скобки в `Add-History` командлет. Команда в круглых скобках, которая выполняется в первую очередь, импортирует `history.xml` файл в PowerShell. `Add-History`Затем командлет добавляет команды в файл в журнал сеанса.

## PARAMETERS

### -InputObject

Указывает массив записей для добавления в журнал в качестве объекта **хисторинфо** в журнал сеанса.
Этот параметр можно использовать для отправки объекта **хисторинфо** , например, тех, которые возвращаются `Get-History` `Import-Clixml` `Import-Csv` командлетами, или, в `Add-History` .

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru

Указывает, что этот командлет возвращает объект **хисторинфо** для каждой записи журнала. По умолчанию этот командлет не создает выходные данные.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Microsoft. PowerShell. Commands. Хисторинфо

Объект **хисторинфо** можно передать в этот командлет по конвейеру.

## Выходные данные

### Нет или Microsoft. PowerShell. Commands. Хисторинфо

Этот командлет возвращает объект **хисторинфо** , если указан параметр **PassThru** . В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

Журнал сеанса — это список команд, вводимых в сеансе вместе с ИДЕНТИФИКАТОРом. В журнале сеанса представлен порядок выполнения, состояние, время начала и завершения выполнения команды. По мере ввода каждой команды PowerShell добавляет его в журнал, чтобы его можно было использовать повторно. Дополнительные сведения о журнале сеанса см. в разделе [about_History](About/about_History.md).

Чтобы указать команды, которые нужно добавить в журнал, используйте параметр **InputObject**. `Add-History`Команда принимает только объекты **хисторинфо** , например, возвращаемые командлетом для каждой команды `Get-History` . Передать путь и имя файла или список команд по конвейеру нельзя.

Параметр **InputObject** можно использовать для передачи файла **хисторинфо** объектов в `Add-History` . Для этого экспортируйте результаты `Get-History` команды в файл с помощью `Export-Csv` `Export-Clixml` командлета или, а затем импортируйте файл с помощью `Import-Csv` `Import-Clixml` командлетов или. Затем можно передать файл импортированных объектов **хисторинфо** в `Add-History` конвейер или в переменную. Дополнительные сведения см. в примерах.

Файл объектов **хисторинфо** , передаваемый в `Add-History` командлет, должен включать сведения о типе, заголовки столбцов и все свойства объектов **хисторинфо** . Если предполагается передать объекты обратно `Add-History` , не используйте параметр **NoTypeInformation** `Export-Csv` командлета и не удаляйте сведения о типе, заголовки столбцов или поля в файле.

Чтобы изменить журнал сеанса, экспортируйте сеанс в файл CSV или XML, измените файл, импортируйте файл и используйте `Add-History` , чтобы добавить его в текущий журнал сеанса.

## Связанные ссылки

[Clear-History](Clear-History.md)

[Get-History](Get-History.md)

[Invoke-History](Invoke-History.md)

[about_PSReadLine](../PSReadLine/About/about_PSReadLine.md)

[Get-PSReadLineOption](/powershell/module/psreadline/get-psreadlineoption)

[Set-PSReadLineOption](/powershell/module/psreadline/set-psreadlineoption)

