---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/stop-job?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Job.
ms.openlocfilehash: d6f1b3a719724073919930b1f1c0839250b5d2c8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229146"
---
# Stop-Job.

## Краткий обзор
Останавливает фоновое задание PowerShell.

## SYNTAX

### Сессионидпараметерсет (по умолчанию)

```
Stop-Job [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### жобпараметерсет

```
Stop-Job [-Job] <Job[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### намепараметерсет

```
Stop-Job [-PassThru] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### инстанцеидпараметерсет

```
Stop-Job [-PassThru] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### статепараметерсет

```
Stop-Job [-PassThru] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### филтерпараметерсет

```
Stop-Job [-PassThru] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Командлет **Stop-Job** останавливает выполняемые фоновые задания PowerShell.
С помощью этого командлета можно прерывать все задания или прекращать выполнение выбранных заданий по имени, ИДЕНТИФИКАТОРу, ИДЕНТИФИКАТОРу экземпляра или состоянию, передавая объект задания в качестве значения " **останавливается-Job** ".

Для отмены фоновых заданий, например тех, которые были запущены с помощью командлета Start-Job или параметра *AsJob* любого командлета, можно использовать параметр " **прерывать — задание** ".
При прекращении фонового задания PowerShell завершает все задачи, ожидающие в этой очереди заданий, а затем завершает задание.
Новые задания не добавляются в очередь после отправки этой команды.

Этот командлет не удаляет фоновые задания.
Чтобы удалить задание, используйте командлет Remove-Job.

Начиная с Windows PowerShell 3,0, **Stop-Job** также останавливает пользовательские типы заданий, такие как задания рабочего процесса и экземпляры запланированных заданий.
Чтобы включить команду " **останавливаюте задания** " для завершения задания с настраиваемым типом задания, импортируйте модуль, который поддерживает тип настраиваемого задания, в сеанс перед выполнением команды " **приостанавливает задание** " либо с помощью командлета Import-Module, либо с помощью или получения командлета в модуле.
Дополнительные сведения о определенных пользовательских типах заданий см. в разделе документации о данной функции.

## Примеры

### Пример 1. Отмена задания на удаленном компьютере с помощью Invoke-Command

```powershell
$s = New-PSSession -ComputerName Server01 -Credential Domain01\Admin02
$j = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Invoke-Command -Session $s -ScriptBlock { Stop-job -Job $Using:j }
```

В этом примере показано, как использовать командлет **Stop-Job** , чтобы остановить задание, которое выполняется на удаленном компьютере.

Поскольку задание было запущено с помощью командлета Invoke-Command для удаленного выполнения команды **запуска-задания** , объект задания хранится на удаленном компьютере.
Для удаленного выполнения команды « **Завершение задания** » необходимо использовать другую команду **Invoke-Command** .
Дополнительные сведения об удаленных фоновых заданиях см. в разделе about_Remote_Jobs.

Первая команда создает сеанс PowerShell ( **PSSession** ) на компьютере Server01, а затем сохраняет объект сеанса в переменной $s.
Команда использует учетные данные администратора домена.

Вторая команда использует командлет **Invoke-Command** для выполнения команды **Start-Job** в сеансе.
Команда в задании получает все события в системном журнале событий.
Полученный объект задания сохраняется в переменной $j.

Третья команда останавливает задание.
В нем используется командлет **Invoke-Command** для выполнения команды " **прерывать задание** " в **сеансе PSSession** на Server01.
Поскольку объекты задания хранятся в переменной $j, которая хранится на локальном компьютере, команда использует модификатор области Using, чтоб идентифицировать $j как локальную переменную.
Дополнительные сведения об использовании модификатора SCOPE см. в разделе [about_Remote_Variables](about/about_Remote_Variables.md).

По завершении выполнения команды задание останавливается и **сеанс PSSession** в $s доступен для использования.

### Пример 2. завершение фонового задания

```powershell
Stop-Job -Name "Job1"
```

Эта команда останавливает фоновое задание Job1.

### Пример 3. завершение нескольких фоновых заданий

```powershell
Stop-Job -Id 1, 3, 4
```

Эта команда останавливает три задания.
Она определяет их по идентификаторам.

### Пример 4. завершение всех фоновых заданий

```powershell
Get-Job | Stop-Job
```

Эта команда останавливает все фоновые задания в текущем сеансе.

### Пример 5. завершение всех заблокированных фоновых заданий

```powershell
Stop-Job -State Blocked
```

Эта команда останавливает все задания, которые заблокированы.

### Пример 6. завершение задания с помощью идентификатора экземпляра

```powershell
Get-Job | Format-Table ID, Name, Command, @{Label="State";Expression={$_.JobStateInfo.State}},
InstanceID -Auto
```

```Output
Id Name Command                 State  InstanceId
-- ---- -------                 -----  ----------
1 Job1 start-service schedule Running 05abb67a-2932-4bd5-b331-c0254b8d9146
3 Job3 start-service schedule Running c03cbd45-19f3-4558-ba94-ebe41b68ad03
5 Job5 get-service s*         Blocked e3bbfed1-9c53-401a-a2c3-a8db34336adf
```

```powershell
Stop-Job -InstanceId e3bbfed1-9c53-401a-a2c3-a8db34336adf
```

Эти команды позволяют остановить задание, указав идентификатор экземпляра.

Первая команда использует командлет Get-Job для получения заданий в текущем сеансе.
Команда использует оператор конвейера (|) для отправки заданий в Format-Table команду, которая отображает таблицу с указанными свойствами каждого задания.
Таблица содержит идентификатор экземпляра каждого задания.
Для отображения состояния задания используется вычисляемое свойство.

Вторая команда использует команду " **прерывать задание** " с параметром *InstanceId* для завершения выбранного задания.

### Пример 7. завершение задания на удаленном компьютере

```powershell
$j = Invoke-Command -ComputerName Server01 -ScriptBlock {Get-EventLog System} -AsJob
$j | Stop-Job -PassThru
```

```Output
Id    Name    State      HasMoreData     Location         Command
--    ----    ----       -----------     --------         -------
5     Job5    Stopped    True            user01-tablet    get-eventlog system
```

В этом примере показано, как использовать командлет **Stop-Job** , чтобы остановить задание, которое выполняется на удаленном компьютере.

Так как задание было запущено с помощью параметра *AsJob* командлета **Invoke-Command** , объект задания находится на локальном компьютере, даже если задание выполняется на удаленном компьютере.
Таким образом, для завершения задания можно использовать локальную команду « **Завершение работы** ».

Первая команда использует командлет **Invoke-Command** для запуска фонового задания на компьютере Server01.
Параметр *AsJob* применяется для выполнения удаленной команды в качестве фонового задания.

Эта команда возвращает объект задания, который является тем же объектом задания, который возвращает командлет **Start-Job** .
Команда сохраняет объект задания в переменной $j.

Вторая команда использует оператор конвейера для отправки задания в переменной $j командлету Stop-Job.
Параметр *PassThru* используется, чтобы командлет **Stop-Job** вернул объект задания.
Отобразится объект задания, подтверждающий, что состояние задания остановлено.

Дополнительные сведения об удаленных фоновых заданиях см. в разделе about_Remote_Jobs.

## PARAMETERS

### -Filter

Указывает хэш-таблицу условий.
Этот командлет останавливает задания, которые отвечают всем условиям.
Введите хэш-таблицу, где ключи являются свойствами заданий, а значения — значениями этих свойств.

Этот параметр работает только с пользовательскими типами заданий, такими как задания рабочих процессов и запланированные задания.
Он не работает со стандартными фоновыми заданиями, такими как созданные с помощью командлета **Start-Job** .
Дополнительные сведения о поддержке данного параметра см. в разделе справки о соответствующем типе заданий.

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

### -Id

Указывает идентификаторы заданий, которые останавливаются этим командлетом.
По умолчанию останавливаются все задания в текущем сеансе.

Идентификатор — это целое число, которое однозначно определяет задание в текущем сеансе.
Проще запомнить и ввести, чем идентификатор экземпляра, но он уникален только в текущем сеансе.
Можно ввести один или несколько идентификаторов, разделенных запятыми.
Чтобы найти идентификатор задания, введите `Get-Job` .

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId

Указывает идентификаторы экземпляров заданий, которые останавливает этот командлет.
По умолчанию останавливаются все задания.

Идентификатор экземпляра — это GUID, который однозначно определяет задание на компьютере.
Чтобы узнать идентификатор экземпляра задания, воспользуйтесь командлетом Get-Job.

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Job

Указывает задания, которые останавливаются этим командлетом.
Введите переменную, содержащую задания, либо команду, которая их возвращают.
Вы также можете использовать оператор конвейера для отправки заданий в командлет " **останавливает-задание** ".
По умолчанию при помощи « **останавливаемое задание** » удаляются все задания, запущенные в текущем сеансе.

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name

Указывает понятные имена заданий, которые остановит этот командлет.
Введите имена заданий в списке с разделителями запятыми или используйте подстановочные знаки (*) для ввода шаблона имени задания.
По умолчанию **Stop-Job** останавливает все задания, созданные в текущем сеансе.

Так как понятное имя не обязательно должно быть уникальным, используйте параметры *WhatIf* и *Confirm* при остановке заданий по имени.

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -PassThru

Возвращает объект, представляющий элемент, с которым вы работаете.
По умолчанию этот командлет не создает выходные данные.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -State

Указывает состояние задания.
Этот командлет останавливает только задания в указанном состоянии.
Допустимые значения для этого параметра:

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

Дополнительные сведения о состояниях заданий см. в разделе [перечисление JobState](https://msdn.microsoft.com/library/system.management.automation.jobstate) в библиотеке MSDN.

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm

Запрос подтверждения перед выполнением командлета.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Показывает, что произойдет при запуске командлета.
Командлет не выполняется.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System. Management. Automation. Ремотингжоб

Объект задания можно передать в этот командлет по конвейеру.

## Выходные данные

### Нет, System. Management. Automation. Псремотингжоб

Этот командлет возвращает объект задания, если указан параметр *PassThru* .
В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Get-Job.](Get-Job.md)

[Invoke-Command](Invoke-Command.md)

[Receive-Job.](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Start-Job](Start-Job.md)

[Wait-Job](Wait-Job.md)

[about_Job_Details](About/about_Job_Details.md)

[about_Remote_Jobs](About/about_Remote_Jobs.md)

[about_Remote_Variables](About/about_Remote_Variables.md)

[about_Jobs](About/about_Jobs.md)

[about_Scopes](About/about_scopes.md)

