---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/get-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-JobTrigger
ms.openlocfilehash: 7a75a5a7e6875ed88fd31ea0f385c19f1991f8d7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227385"
---
# Get-JobTrigger

## Краткий обзор
Получает триггеры задания для запланированных заданий.

## SYNTAX

### JobDefinition (по умолчанию)

```
Get-JobTrigger [[-TriggerId] <Int32[]>] [-InputObject] <ScheduledJobDefinition> [<CommonParameters>]
```

### жобдефинитионид

```
Get-JobTrigger [[-TriggerId] <Int32[]>] [-Id] <Int32> [<CommonParameters>]
```

### жобдефинитионнаме

```
Get-JobTrigger [[-TriggerId] <Int32[]>] [-Name] <String> [<CommonParameters>]
```

## DESCRIPTION
Командлет **Get-JobTrigger** получает триггеры задания для запланированных заданий.
Эта команда используется для проверки триггеров задания или их передачи в другие командлеты.

Триггер задания определяет повторяющееся расписание или условия для запуска запланированного задания.
Триггеры задания не сохраняются на диск независимо; они являются частью запланированного задания.
Чтобы получить триггер задания, укажите запланированное задание, запускаемое триггером.

Используйте параметры командлета **Get-JobTrigger** , чтобы определить запланированные задания.
Запланированные задания можно определить по их именам или идентификационным номерам либо путем ввода или передачи объектов **ScheduledJob** , например, возвращаемых командлетом Get-ScheduledJob, в **Get-JobTrigger** .

**Get-JobTrigger** — это одна из коллекций командлетов планирования заданий в модуле PSScheduledJob, который входит в состав Windows PowerShell.

Дополнительные сведения о запланированных заданиях см. в разделах описания в модуле PSScheduledJob.
Импортируйте модуль PSScheduledJob, а затем введите `Get-Help about_Scheduled*` или просмотрите статью about_Scheduled_Jobs.

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. получение триггера задания по имени запланированного задания

```
PS C:\> Get-JobTrigger -Name "BackupJob"
```

Команда использует параметр *Name* командлета **Get-JobTrigger** , чтобы получить триггеры задания для запланированного задания баккупжоб.

### Пример 2. получение триггера задания по ИДЕНТИФИКАТОРу

```
The first command uses the Get-ScheduledJob cmdlet to display the scheduled jobs on the local computer. The display includes the IDs of the scheduled jobs.
PS C:\> Get-ScheduledJob
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          ArchiveProjects {1}             \\Server\Share\Archive-Projects.ps1      True
2          Backup          {1,2}           \\Server\Share\Run-Backup.ps1            True
3          Test-HelpFiles  {1}             \\Server\Share\Test-HelpFiles.ps1        True
4          TestJob         {}              \\Server\Share\Run-AllTests.ps1          True

The second command uses the **Get-JobTrigger** cmdlet to get the job trigger for the Test-HelpFiles job (ID = 3)
PS C:\> Get-JobTrigger -ID 3
```

В примере используется параметр *ID* командлета **Get-JobTrigger** , чтобы получить триггеры задания для запланированного задания.

### Пример 3. получение триггеров задания путем передачи задания по конвейеру

```
PS C:\> Get-ScheduledJob -Name *Backup*, *Archive* | Get-JobTrigger
```

Эта команда возвращает Триггеры заданий для всех заданий, имеющих резервную копию или Архив в именах.

### Пример 4. получение триггера задания на удаленном компьютере

```
PS C:\> Invoke-Command -ComputerName Server01 { Get-ScheduledJob Backup | Get-JobTrigger -TriggerID 2 }
```

Эта команда возвращает один из двух триггеров задания для запланированного задания на удаленном компьютере.

Команда использует командлет Invoke-Command для выполнения команды на компьютере Server01.
Он использует командлет Get-ScheduledJob, чтобы получить запланированное задание резервного копирования, которое оно передает в командлет **Get-JobTrigger** .
Для получения только второго триггера используется параметр *TriggerID* .

### Пример 5. получение всех триггеров заданий

```
PS C:\> Get-ScheduledJob | Get-JobTrigger | Format-Table -Property ID, Frequency, At, DaysOfWeek, Enabled, @{Label="ScheduledJob";Expression={$_.JobDefinition.Name}} -AutoSize
Id Frequency At                    DaysOfWeek Enabled ScheduledJob
-- --------- --                    ---------- ------- ------------
1    Weekly  9/28/2011 3:00:00 AM  {Monday}   True    Backup
1    Daily   9/27/2011 11:00:00 PM            True    Test-HelpFiles
```

Эта команда возвращает все триггеры задания для всех запланированных заданий на локальном компьютере.

Команда использует Get-ScheduledJob для получения запланированных заданий на локальном компьютере и передает их в **Get-JobTrigger** , который получает триггер задания для каждого запланированного задания (если оно есть).

Чтобы добавить имя запланированного задания к отображению триггера задания, команда использует функцию вычисленное свойство командлета Format-Table.
В дополнение к свойствам триггера задания, отображаемым по умолчанию, команда создает новое свойство ScheduledJob, которое отображает имя запланированного задания.

### Пример 6. получение свойства триггера задания для запланированного задания

```
The command uses the Get-ScheduledJob cmdlet to get the Test-HelpFiles scheduled job. Then it uses the dot method (.) to get the JobTriggers property of the Test-HelpFiles scheduled job.
PS C:\> (Get-ScheduledJob Test-HelpFiles).JobTriggers

The second command uses the Get-ScheduledJob cmdlet to get all scheduled jobs on the local computer. It uses the ForEach-Object cmdlet to get the value of the JobTrigger property of each scheduled job.
PS C:\> Get-ScheduledJob | foreach {$_.JobTriggers}
```

Триггеры задания для запланированного задания хранятся в свойстве JobTriggers задания.
В этом примере показаны альтернативные варианты использования командлета **Get-JobTrigger** для получения триггеров заданий.
Результаты аналогичны использованию командлета **Get-JobTrigger** , и эти методы являются взаимозаменяемыми.

### Пример 7. сравнение триггеров заданий

```
The first command gets the job trigger of the ArchiveProjects scheduled job. The command pipes the job trigger to the Tee-Object cmdlet, which saves the job trigger in the $T1 variable and displays it at the command line.
PS C:\> Get-ScheduledJob -Name ArchiveProjects | Get-JobTrigger | Tee-Object -Variable T1
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
0          Daily           9/26/2011 3:00:00 AM                           True

The second command gets the job trigger of the Test-HelpFiles scheduled job. The command pipes the job trigger to the Tee-Object cmdlet, which saves the job trigger in the $T2 variable and displays it at the command line.
PS C:\> Get-ScheduledJob -Name "Test-HelpFiles" | Get-JobTrigger | Tee-Object -Variable T2
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
0          Daily           9/26/2011 3:00:00 AM                           True

The third command compares the job triggers in the $t1 and $t2 variables. It uses the Get-Member cmdlet to get the properties of the job trigger in the $t1 variable. It pipes the properties to the ForEach-Object cmdlet, which compares each property to the properties of the job trigger in the $t2 variable by name. The command then pipes the differing properties to the Format-List cmdlet, which displays them in a list.The output indicates that, although the job triggers appear to be the same, the HelpFiles job trigger includes a random delay of three (3) minutes.
PS C:\> $T1 | Get-Member -Type Property | ForEach-Object { Compare-Object $T1 $T2 -Property $_.Name}
RandomDelay                                                 SideIndicator
-----------                                                 -------------
00:00:00                                                    =>
00:03:00                                                    <=
```

В этом примере показано, как сравнить триггеры задания двух запланированных заданий.

## PARAMETERS

### -Id
Задает идентификационный номер запланированного задания.
**Get-JobTrigger** получает триггер указанного запланированного задания.

Чтобы получить идентификационный номер запланированных заданий на локальном или удаленном компьютере, используйте командлет Get-ScheduledJob.

```yaml
Type: System.Int32
Parameter Sets: JobDefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Указывает запланированное задание.
Введите переменную, содержащую объекты  **ScheduledJob** , или введите команду или выражение, которое получает объекты **ScheduledJob** , такие как команда Get-ScheduledJob.
Вы также можете передать объекты **ScheduledJob** в командлет **Get-JobTrigger** .

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: JobDefinition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Указывает имя запланированного задания.
**Get-JobTrigger** получает триггер указанного запланированного задания.
Поддерживаются подстановочные знаки.

Чтобы получить имена запланированных заданий на локальном или удаленном компьютере, используйте командлет Get-ScheduledJob.

```yaml
Type: System.String
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TriggerId
Возвращает указанные триггеры задания.
Введите идентификаторы триггеров одного или нескольких запланированных заданий.
Используйте этот параметр, если запланированное задание, заданное параметрами *Name* , *ID* или *InputObject* , имеет несколько триггеров задания.

```yaml
Type: System.Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Вы можете передать запланированное задание из Get-ScheduledJob в командлет **Get-JobTrigger** .

## Выходные данные

### Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Add-JobTrigger](Add-JobTrigger.md)

[Disable-JobTrigger](Disable-JobTrigger.md)

[Disable-ScheduledJob](Disable-ScheduledJob.md)

[Enable-JobTrigger](Enable-JobTrigger.md)

[Enable-ScheduledJob](Enable-ScheduledJob.md)

[Get-JobTrigger](Get-JobTrigger.md)

[Get-ScheduledJob](Get-ScheduledJob.md)

[Get-ScheduledJobOption](Get-ScheduledJobOption.md)

[New-JobTrigger](New-JobTrigger.md)

[New-ScheduledJobOption](New-ScheduledJobOption.md)

[Register-ScheduledJob](Register-ScheduledJob.md)

[Remove-JobTrigger](Remove-JobTrigger.md)

[Set-JobTrigger](Set-JobTrigger.md)

[Set-ScheduledJob](Set-ScheduledJob.md)

[Set-ScheduledJobOption](Set-ScheduledJobOption.md)

[Unregister-ScheduledJob](Unregister-ScheduledJob.md)
