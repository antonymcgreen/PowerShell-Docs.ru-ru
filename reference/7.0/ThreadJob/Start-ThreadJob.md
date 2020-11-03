---
external help file: ThreadJob.dll-Help.xml
Locale: en-US
Module Name: ThreadJob
ms.date: 01/28/2020
online version: https://docs.microsoft.com/powershell/module/threadjob/start-threadjob?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-ThreadJob
ms.openlocfilehash: 13c78786b3dd506af9c6efa45eef4b5be20537cd
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229590"
---
# Start-ThreadJob

## Краткий обзор
Создает фоновые задания, аналогичные `Start-Job` командлету.

## SYNTAX

### ScriptBlock

```
Start-ThreadJob [-ScriptBlock] <ScriptBlock> [-Name <String>] [-InitializationScript <ScriptBlock>]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### FilePath

```
Start-ThreadJob [-FilePath] <String> [-Name <String>] [-InitializationScript <ScriptBlock>]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [-ThrottleLimit <Int32>] [<CommonParameters>]
```

## DESCRIPTION

`Start-ThreadJob` создает фоновые задания, аналогичные `Start-Job` командлету. Основное отличие состоит в том, что создаваемые задания выполняются в отдельных потоках внутри локального процесса. По умолчанию задания используют текущий рабочий каталог вызывающей стороны, запустившего задание.

Командлет также поддерживает параметр **ThrottleLimit** для ограничения количества заданий, выполняемых в один момент времени. По мере запуска заданий они ставятся в очередь и ожидают, пока текущее число заданий не станет меньше предельного значения регулирования.

## Примеры

### Пример 1. Создание фоновых заданий с ограничением потока, равным 2

```powershell
Start-ThreadJob -ScriptBlock { 1..100 | % { sleep 1; "Output $_" } } -ThrottleLimit 2
Start-ThreadJob -ScriptBlock { 1..100 | % { sleep 1; "Output $_" } }
Start-ThreadJob -ScriptBlock { 1..100 | % { sleep 1; "Output $_" } }
Get-Job
```

```Output
Id   Name   PSJobTypeName   State        HasMoreData   Location     Command
--   ----   -------------   -----        -----------   --------     -------
1    Job1   ThreadJob       Running      True          PowerShell   1..100 | % { sleep 1;...
2    Job2   ThreadJob       Running      True          PowerShell   1..100 | % { sleep 1;...
3    Job3   ThreadJob       NotStarted   False         PowerShell   1..100 | % { sleep 1;...
```

### Пример 2. Сравнение производительности Start-Job и Start-ThreadJob

В этом примере показано различие между `Start-Job` и `Start-ThreadJob` . Задания запускают `Start-Sleep` командлет в течение 1 секунды. Так как задания выполняются параллельно, общее время выполнения составляет около 1 секунды, а также любое время, необходимое для создания заданий.

```powershell
# start five background jobs each running 1 second
Measure-Command {1..5 | % {Start-Job {Start-Sleep 1}} | Wait-Job} | Select-Object TotalSeconds
Measure-Command {1..5 | % {Start-ThreadJob {Start-Sleep 1}} | Wait-Job} | Select-Object TotalSeconds
```

```Output
TotalSeconds
------------
   5.7665849
   1.5735008
```

После вычитания 1 секунды для времени выполнения можно увидеть, что `Start-Job` для создания пяти заданий потребуется около 4,8 секунд. `Start-ThreadJob` составляет 8 раз быстрее и занимает около 0,6 секунд для создания пяти заданий. Результаты могут различаться в вашей среде, но относительное улучшение должно быть одинаковым.

### Пример 3. Создание заданий с помощью InputObject

В этом примере блок скрипта использует `$input` переменную для получения входных данных из параметра **InputObject** . Это также можно сделать с помощью конвейера объектов в `Start-ThreadJob` .

```powershell
$j = Start-ThreadJob -InputObject (Get-Process pwsh) -ScriptBlock { $input | Out-String }
$j | Wait-Job | Receive-Job
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     94   145.80     159.02      18.31   18276   1 pwsh
    101   163.30     222.05      29.00   35928   1 pwsh
```

```powershell
$j = Get-Process pwsh | Start-ThreadJob -ScriptBlock { $input | Out-String }
$j | Wait-Job | Receive-Job
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     94   145.80     159.02      18.31   18276   1 pwsh
    101   163.30     222.05      29.00   35928   1 pwsh
```

## PARAMETERS

### -ArgumentList

Задает массив аргументов или значений параметров для скрипта, заданного параметрами **FilePath** или **ScriptBlock** .

**ArgumentList** должен быть последним параметром в командной строке. Все значения, следующие за именем параметра, являются интерпретированными значениями в списке аргументов.

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

Указывает файл скрипта для запуска в качестве фонового задания. Введите путь и имя файла скрипта. Сценарий должен находиться на локальном компьютере или в папке, к которой может получить доступ локальный компьютер.

При использовании этого параметра PowerShell преобразует содержимое указанного файла скрипта в блок скрипта и запускает блок скрипта в качестве фонового задания.

```yaml
Type: System.String
Parameter Sets: FilePath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Инитиализатионскрипт

Указывает команды, выполняемые перед запуском задания. Заключите команды в фигурные скобки ( `{}` ), чтобы создать блок скрипта.

Используйте этот параметр для подготовки сеанса, в рамках которого выполняется задание. Например, его можно использовать для добавления функций и модулей в сеанс.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Указывает объекты, используемые в качестве входных данных для блока скрипта. Он также позволяет выполнять входные данные конвейера. Используйте `$input` автоматическую переменную в блоке скрипта для доступа к входным объектам.

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

### -Name

Указывает понятное имя нового задания. С помощью имени можно указать задание для других командлетов задания, например `Stop-Job` командлета.

Понятное имя по умолчанию — Job #, где "#" — порядковый номер, увеличивающийся для каждого задания.

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

### -ScriptBlock

Указывает команды, которые нужно выполнить в фоновом задании. Заключите команды в фигурные скобки ( `{}` ), чтобы создать блок скрипта. Используйте `$Input` автоматическую переменную для доступа к значению параметра **InputObject** . Этот параметр обязателен.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Стреамингхост

Этот параметр обеспечивает потокобезопасный способ, позволяющий передавать `Write-Host` выходные данные непосредственно в переданный объект **PSHost** . Без него выходные данные передаются в `Write-Host` коллекцию потока данных о задании и не отображаются в консоли узла до тех пор, пока не завершится выполнение заданий.

```yaml
Type: System.Management.Automation.Host.PSHost
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Этот параметр ограничивает количество заданий, выполняемых за один раз. При запуске заданий они помещаются в очередь и ожидают, пока поток не будет доступен в пуле потоков для выполнения задания. Ограничение по умолчанию — 5 потоков.

Размер пула потоков является глобальным по отношению к сеансу PowerShell. Указание **ThrottleLimit** в одном вызове задает ограничение для последующих вызовов в одном сеансе.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Management.Automation.PSObject

## Выходные данные

### Среаджоб. Среаджоб

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Start-Job](../Microsoft.PowerShell.Core/Start-Job.md)

[Stop-Job.](../Microsoft.PowerShell.Core/Stop-Job.md)

[Receive-Job.](../Microsoft.PowerShell.Core/Receive-Job.md)
