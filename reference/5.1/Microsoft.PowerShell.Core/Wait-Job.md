---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/wait-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Job
ms.openlocfilehash: 0e2888ca7d0b601b1d67fb0a8dd756b653ad8dbc
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388388"
---
# Wait-Job

## Краткий обзор
Подавляет командную строку до завершения выполнения одного или всех фоновых заданий PowerShell, выполняемых в этом сеансе.

## SYNTAX

### Сессионидпараметерсет (по умолчанию)

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Id] <Int32[]> [<CommonParameters>]
```

### жобпараметерсет

```
Wait-Job [-Job] <Job[]> [-Any] [-Timeout <Int32>] [-Force] [<CommonParameters>]
```

### намепараметерсет

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Name] <String[]> [<CommonParameters>]
```

### инстанцеидпараметерсет

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### статепараметерсет

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-State] <JobState> [<CommonParameters>]
```

### филтерпараметерсет

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Filter] <Hashtable> [<CommonParameters>]
```

## DESCRIPTION

`Wait-Job`Командлет ожидает завершения фоновых заданий Windows PowerShell, прежде чем отобразит командную строку. При этом можно командлет может ожидать завершения одного или всех фоновых заданий либо ограничиваться максимальным временем ожидания.

После завершения выполнения команд в задании `Wait-Job` отображает командную строку и возвращает объект задания, чтобы можно было передать его в другую команду.

Командлет можно использовать `Wait-Job` для ожидания фоновых заданий, например тех, которые были запущены с помощью `Start-Job` командлета или параметра **AsJob** `Invoke-Command` командлета. Дополнительные сведения о фоновых заданиях Windows PowerShell см. в разделе [about_Jobs](./about/about_Jobs.md).

Начиная с Windows PowerShell 3,0, `Wait-Job` командлет также ждет выполнения пользовательских типов заданий, таких как задания рабочего процесса и экземпляры запланированных заданий. Чтобы разрешить `Wait-Job` Ожидание заданий определенного типа, импортируйте модуль, который поддерживает тип настраиваемого задания, в сеанс перед выполнением `Get-Job` командлета либо с помощью командлета, либо `Import-Module` путем получения командлета в модуле. Дополнительные сведения о определенных пользовательских типах заданий см. в разделе документации о данной функции.

## Примеры

### Пример 1. Ожидание всех заданий

```powershell
Get-Job | Wait-Job
```

Эта команда ожидает завершения всех фоновых заданий, выполняемых в сеансе.

### Пример 2. Ожидание запуска заданий на удаленных компьютерах с помощью Start-Job

```powershell
$s = New-PSSession Server01, Server02, Server03
Invoke-Command -Session $s -ScriptBlock {Start-Job -Name Date1 -ScriptBlock {Get-Date}}
$done = Invoke-Command -Session $s -Command {Wait-Job -Name Date1}
$done.Count
```

```Output
3
```

В этом примере показано, как использовать `Wait-Job` командлет с заданиями, запущенными на удаленных компьютерах с помощью `Start-Job` командлета. Обе `Start-Job` `Wait-Job` команды и передаются на удаленный компьютер с помощью `Invoke-Command` командлета.

В этом примере используется `Wait-Job` , чтобы определить, `Get-Date` завершена ли команда, выполняемая как фоновое задание на трех разных компьютерах.

Первая команда создает сеанс Windows PowerShell ( **PSSession** ) на каждом из трех удаленных компьютеров и сохраняет их в `$s` переменной.

Вторая команда использует `Invoke-Command` для выполнения `Start-Job` в каждом из трех сеансов в `$s` .
Все задания имеют имя Date1.

Третья команда использует `Invoke-Command` для запуска `Wait-Job` . Эта команда ожидает завершения заданий Date1 на каждом компьютере. В нем сохраняется результирующая коллекция (array) объектов Job в `$done` переменной.

Четвертая команда использует свойство **Count** массива объектов задания в `$done` переменной, чтобы определить, сколько заданий завершено.

### Пример 3. Определение времени завершения первого фонового задания

```powershell
$s = New-PSSession (Get-Content Machines.txt)
$c = 'Get-EventLog -LogName System | where {$_.EntryType -eq "error" --and $_.Source -eq "LSASRV"} | Out-File Errors.txt'
Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {$Using:c}
Invoke-Command -Session $s -ScriptBlock {Wait-Job -Any}
```

В этом примере используется параметр **ANY** `Wait-Job` для определения времени выполнения первого из многих фоновых заданий, выполняемых в текущем сеансе. В нем также показано, как использовать `Wait-Job` командлет для ожидания завершения удаленных заданий.

Первая команда создает **сеанс PSSession** на каждом из компьютеров, перечисленных в файле Machines.txt, и сохраняет объекты **PSSession** в `$s` переменной. Команда использует `Get-Content` командлет для получения содержимого файла. `Get-Content`Команда заключается в круглые скобки, чтобы убедиться, что она выполняется перед `New-PSSession` командой.

Вторая команда сохраняет `Get-EventLog` командную строку в кавычках в `$c` переменной.

Третья команда использует `Invoke-Command` командлет для выполнения `Start-Job` в каждом сеансе в `$s` .
`Start-Job`Команда запускает фоновое задание, которое выполняет `Get-EventLog` команду в `$c` переменной.

Команда использует модификатор области **using** , чтобы указать, что `$c` переменная была определена на локальном компьютере. Модификатор области **Using** был введен в Windows PowerShell 3.0. Дополнительные сведения об **использовании** модификатора SCOPE см. в разделе [about_Remote_Variables](./about/about_Remote_Variables.md).

Четвертая команда использует `Invoke-Command` для выполнения `Wait-Job` команды в сеансах. Он использует параметр **ANY** для ожидания завершения первого задания на удаленных компьютерах.

### Пример 4. Задание времени ожидания для заданий на удаленных компьютерах

```powershell
$s = New-PSSession Server01, Server02, Server03
$jobs = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {Get-Date}}
$done = Invoke-Command -Session $s -ScriptBlock {Wait-Job -Timeout 30}
```

В этом примере показано, как использовать параметр **timeout** в, `Wait-Job` чтобы задать максимальное время ожидания для заданий, выполняемых на удаленных компьютерах.

Первая команда создает **сеанс PSSession** на каждом из трех удаленных компьютеров (Server01, Server02 и Server03), а затем сохраняет объекты **PSSession** в `$s` переменной.

Вторая команда использует `Invoke-Command` для выполнения `Start-Job` в каждом из объектов **PSSession** в `$s` . Он сохраняет результирующие объекты задания в `$jobs` переменной.

Третья команда использует `Invoke-Command` для выполнения `Wait-Job` в каждом сеансе в `$s` . `Wait-Job`Команда определяет, выполнены ли все команды в течение 30 секунд. Он использует параметр **timeout** со значением 30 для установки максимального времени ожидания, а затем сохраняет результаты выполнения команды в `$done` переменной.

В данном случае по истечении 30 секунд была завершена только команда на компьютере Server02. `Wait-Job` завершает ожидание, выводит командную строку и возвращает объект, представляющий задание, которое было завершено.

`$done`Переменная содержит объект задания, который представляет задание, которое выполнялось в Server02.

### Пример 5. Ожидание завершения одного из нескольких заданий

```powershell
Wait-Job -id 1,2,5 -Any
```

Эта команда определяет три задания по их идентификаторам и ожидает завершения одного из них.
Командная строка возвращает время завершения первого задания.

### Пример 6. Ожидание периода, а затем разрешение на продолжение работы в фоновом режиме

```powershell
Wait-Job -Name "DailyLog" -Timeout 120
```

Эта команда ожидает завершения задания Даилилог в течение 120 с (две минуты). Если задание не завершается в течение следующих двух минут, Командная строка все равно возвращается, и задание продолжит выполняться в фоновом режиме.

### Пример 7. Ожидание задания по имени

```powershell
Wait-Job -Name "Job3"
```

Эта команда использует имя задания для указания задания, которое требуется подождать.

### Пример 8. Ожидание запуска заданий на локальном компьютере с Start-Job

```powershell
$j = Start-Job -ScriptBlock {Get-ChildItem *.ps1| where {$_lastwritetime -gt ((Get-Date) - (New-TimeSpan -Days 7))}}
$j | Wait-Job
```

В этом примере показано, как использовать `Wait-Job` командлет с заданиями, запущенными на локальном компьютере с помощью `Start-Job` .

Эти команды запускают задание, которое получает список файлов скриптов Windows PowerShell, добавленных или измененных в течение последней недели.

Первая команда использует `Start-Job` для запуска фонового задания на локальном компьютере. Задание выполняет `Get-ChildItem` команду, которая получает все файлы с расширением PS1, которые были добавлены или обновлены за последнюю неделю.

Третья команда использует `Wait-Job` для ожидания завершения задания. После завершения задания команда отображает объект задания, содержащий сведения о задании.

### Пример 9. Ожидание запуска заданий на удаленных компьютерах с помощью Invoke-Command

```powershell
$s = New-PSSession Server01, Server02, Server03
$j = Invoke-Command -Session $s -ScriptBlock {Get-Process} -AsJob
$j | Wait-Job
```

В этом примере показано, как использовать `Wait-Job` с заданиями, запущенными на удаленных компьютерах, с помощью параметра **AsJob** в `Invoke-Command` . При использовании **AsJob** задание создается на локальном компьютере, а результаты автоматически возвращаются на локальный компьютер, даже если задание выполняется на удаленных компьютерах.

В этом примере используется `Wait-Job` для определения, `Get-Process` завершена ли команда, выполняемая в сеансах на трех удаленных компьютерах.

Первая команда создает объекты **PSSession** на трех компьютерах и сохраняет их в `$s` переменной.

Вторая команда использует `Invoke-Command` для выполнения `Get-Process` в каждом из трех сеансов в `$s` .
Команда использует параметр **AsJob** для асинхронного выполнения команды в качестве фонового задания. Команда возвращает объект задания, как и задания, запущенные с помощью `Start-Job` , а объект задания хранится в `$j` переменной.

Третья команда использует конвейерный оператор ( `|` ) для отправки объекта задания в `$j` `Wait-Job` командлет. `Invoke-Command`В этом случае команда не требуется, так как задание находится на локальном компьютере.

### Пример 10. Ожидание задания с ИДЕНТИФИКАТОРом

```powershell
Get-Job
```

```Output
Id   Name     State      HasMoreData     Location             Command
--   ----     -----      -----------     --------             -------
1    Job1     Completed  True            localhost,Server01.. get-service
4    Job4     Completed  True            localhost            dir | where
```

```powershell
Wait-Job -Id 1
```

Эта команда ожидает завершения задания с идентификатором 1.

## PARAMETERS

### -Any

Указывает, что этот командлет отображает командную строку и возвращает объект задания при завершении любого задания. По умолчанию `Wait-Job` ожидает завершения всех указанных заданий перед отображением запроса.

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

### -Filter

Указывает хэш-таблицу условий. Этот командлет ожидает задания, которые отвечают всем условиям в хэш-таблице. Введите хэш-таблицу, где ключи являются свойствами заданий, а значения — значениями этих свойств.

Этот параметр работает только с пользовательскими типами заданий, такими как задания рабочих процессов и запланированные задания. Он не работает со стандартными фоновыми заданиями, такими как созданные с помощью `Start-Job` командлета. Дополнительные сведения о поддержке данного параметра см. в разделе справки о соответствующем типе заданий.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: FilterParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force

Указывает, что этот командлет продолжает ожидать задания в приостановленном или отключенном состоянии. По умолчанию `Wait-Job` Возвращает или завершает ожидание, если задания находятся в одном из следующих состояний:

- Завершено
- Ошибка
- Остановлена
- Приостановлена
- Отключено

Этот параметр впервые появился в Windows PowerShell 3.0.

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

### -Id

Указывает массив идентификаторов заданий, для которых этот командлет ожидает выполнения.

Идентификатор — это целое число, которое однозначно определяет задание в текущем сеансе. Проще запомнить и ввести, чем идентификатор экземпляра, но он уникален только в текущем сеансе. Можно ввести один или несколько идентификаторов, разделенных запятыми. Чтобы найти идентификатор задания, введите `Get-Job` .

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId

Указывает массив идентификаторов экземпляров заданий, для которых этот командлет ожидает выполнения. По умолчанию останавливаются все задания.

Идентификатор экземпляра — это GUID, который однозначно определяет задание на компьютере. Чтобы найти идентификатор экземпляра задания, используйте `Get-Job` .

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Job

Указывает задания, для которых этот командлет ожидает. Введите переменную, содержащую объекты заданий, либо команду, которая их возвращают. Для отправки объектов заданий в командлет можно также использовать оператор конвейера `Wait-Job` . По умолчанию `Wait-Job` ожидает всех заданий, созданных в текущем сеансе.

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name

Указывает понятные имена заданий, для которых этот командлет ожидает выполнения.

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -State

Указывает состояние задания. Этот командлет ожидает только задания в указанном состоянии. Допустимые значения для этого параметра:

- NotStarted
- Запущен
- Завершено
- Ошибка
- Остановлена
- Блокировано
- Приостановлена
- Отключено
- Приостановка
- Остановка

Дополнительные сведения о состояниях заданий см. в разделе [JobState enumeration](/dotnet/api/system.management.automation.jobstate).

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Timeout

Задает максимальное время ожидания для каждого фонового задания в секундах. Значение по умолчанию – 1 указывает, что командлет ожидает завершения задания. Время начинается при отправке `Wait-Job` команды, а не `Start-Job` команды.

Если указанное время истекло, ожидание прекращается, а окно командной строки становится активным, даже если задание все еще выполняется. Команда не отображает сообщение об ошибке.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System. Management. Automation. Ремотингжоб

Объект задания можно передать в этот командлет по конвейеру.

## Выходные данные

### System. Management. Automation. Псремотингжоб

Этот командлет возвращает объекты задания, представляющие завершенные задания. Если ожидание заканчивается из-за превышения значения параметра **timeout** , не `Wait-Job` возвращает никаких объектов.

## ПРИМЕЧАНИЯ

По умолчанию `Wait-Job` Возвращает или завершает ожидание, если задания находятся в одном из следующих состояний:

- Завершено
- Ошибка
- Остановлена
- Приостановлена
- Отключено. чтобы `Wait-Job` продолжить ожидание приостановленных и отключенных заданий, используйте параметр **Force** .

## Связанные ссылки

[Get-Job.](Get-Job.md)

[Invoke-Command](Invoke-Command.md)

[Receive-Job.](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Resume-Job](Resume-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job.](Stop-Job.md)

[Suspend-Job](Suspend-Job.md)
