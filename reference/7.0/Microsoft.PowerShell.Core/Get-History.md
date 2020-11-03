---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 10/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-history?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-History
ms.openlocfilehash: 65178cc826055fe494d032705072702c7bc210b6
ms.sourcegitcommit: 1695df0d241c0390cac71a7401e61198fc6ff756
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2020
ms.locfileid: "93230745"
---
# Get-History

## Краткий обзор
Возвращает список команд, введенных во время текущего сеанса.

## SYNTAX

```
Get-History [[-Id] <Int64[]>] [[-Count] <Int32>] [<CommonParameters>]
```

## DESCRIPTION

`Get-History`Командлет возвращает журнал сеанса, то есть список команд, вводимых в текущем сеансе.

PowerShell автоматически поддерживает журнал каждого сеанса. Число записей в журнале сеанса определяется значением `$MaximumHistoryCount` привилегированной переменной. Начиная с Windows PowerShell 3,0, значение по умолчанию — `4096` . По умолчанию файлы журнала сохраняются в домашнем каталоге, но вы можете сохранить файл в любом месте. Дополнительные сведения о функциях журнала в PowerShell см. в разделе [about_History](About/about_History.md).

Журнал сеанса управляется отдельно от журнала, поддерживаемого модулем **PSReadLine** .
Оба журнала доступны в сеансах, где загружен **PSReadLine** . Этот командлет работает только с журналом сеанса. Дополнительные сведения см. в разделе [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).

## Примеры

### Пример 1. Получение журнала сеанса

Этот пример возвращает записи в журнале сеанса. По умолчанию отображается каждая команда и ее идентификатор, который указывает порядок их запуска.

```powershell
Get-History
```

### Пример 2. получение записей, содержащих строку

Этот пример получает записи в журнале команд, которые включают в себя службу String. Первая команда возвращает все записи из журнала сеанса. Оператор конвейера ( `|` ) передает результаты в `Where-Object` командлет, который выбирает только команды, включающие службу.

```powershell
Get-History | Where-Object {$_.CommandLine -like "*Service*"}
```

### Пример 3. Экспорт записей журнала по указанному ИДЕНТИФИКАТОРу

Этот пример получает пять последних записей журнала, оканчивающихся записью 7. Оператор конвейера передает результат в `Export-Csv` командлет, который форматирует журнал в виде текста с разделителями-запятыми и сохраняет его в файле History.csv. Файл содержит данные, которые отображаются при форматировании журнала в виде списка. Сюда входят состояние и время начала и окончания выполнения команды.

```powershell
Get-History -ID 7 -Count 5 | Export-Csv History.csv
```

### Пример 4. Отображение последней команды

В этом примере возвращается последняя команда в журнале команд. Последняя команда является самой последней командой. Эта команда использует параметр **Count** для вывода всего одной команды. По умолчанию `Get-History` возвращает самые последние команды. Эту команду можно сократить до "h -c 1", и она эквивалентна нажатию клавиши со стрелкой вверх.

```powershell
Get-History -Count 1
```

### Пример 5. Отображение всех свойств записей в журнале

В этом примере отображаются все свойства записей в журнале сеанса. Оператор конвейера передает результаты `Get-History` команды в `Format-List` командлет, который отображает все свойства каждой записи журнала. Сюда входят идентификатор, состояние и время начала и окончания команды.

```powershell
Get-History | Format-List -Property *
```

## PARAMETERS

### — Количество

Указывает количество последних записей журнала, которые получает этот командлет. По умолчанию `Get-History` получает все записи в журнале сеанса. Если в команде используются оба параметра **Count** и **Id** , последней выводится команда, указанная в параметре **Id** .

В Windows PowerShell 2,0 по умолчанию `Get-History` возвращает 32 последних записей.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Указывает массив идентификаторов записей в журнале сеанса. `Get-History` Возвращает только указанные записи. Если в команде используются оба параметра **ID** и **Count** , `Get-History` получает последние записи, которые заканчиваются записью, заданной параметром **ID** .

```yaml
Type: System.Int64[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Int64

ИДЕНТИФИКАТОР журнала можно передать в этот командлет по конвейеру.

## Выходные данные

### Microsoft. PowerShell. Commands. Хисторинфо

Этот командлет возвращает объект журнала для каждого элемента журнала, который он получает.

## ПРИМЕЧАНИЯ

Журнал сеанса — это список команд, введенных за время сеанса. Журнал сеанса представляет собой порядок выполнения, состояние и время начала и окончания команды. По мере ввода каждой команды PowerShell добавляет его в журнал, чтобы его можно было использовать повторно. Дополнительные сведения о журнале команд см. в разделе [about_History](About/about_History.md).

Начиная с Windows PowerShell 3,0, значением по умолчанию для `$MaximumHistoryCount` привилегированной переменной является `4096` . В Windows PowerShell 2,0 значение по умолчанию — `64` . Дополнительные сведения о `$MaximumHistoryCount` переменной см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).

## Связанные ссылки

[Add-History](Add-History.md)

[Clear-History](Clear-History.md)

[Invoke-History](Invoke-History.md)

[about_History](About/about_History.md)
