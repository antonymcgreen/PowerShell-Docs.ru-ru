---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/get-scheduledjoboption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ScheduledJobOption
ms.openlocfilehash: 5c317be9add0898137aceed6c39032f3e271bac1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227378"
---
# Get-ScheduledJobOption

## Краткий обзор
Получает параметры задания для запланированных заданий.

## SYNTAX

### JobDefinition (по умолчанию)

```
Get-ScheduledJobOption [-InputObject] <ScheduledJobDefinition> [<CommonParameters>]
```

### жобдефинитионид

```
Get-ScheduledJobOption [-Id] <Int32> [<CommonParameters>]
```

### жобдефинитионнаме

```
Get-ScheduledJobOption [-Name] <String> [<CommonParameters>]
```

## DESCRIPTION
Командлет **Get-scheduledjoboptions** Возвращает параметры задания для запланированных заданий.
Эта команда используется для проверки параметров задания или их передачи в другие командлеты.

Параметры задания не сохраняются на диск независимо; они являются частью запланированного задания.
Чтобы получить параметры запланированного задания, укажите это запланированное задание.

Используйте параметры командлета **Get-ScheduledJobOption** , чтобы определить запланированное задание.
Запланированные задания можно определить по их именам или идентификационным номерам либо путем ввода или передачи объектов **ScheduledJob** , например, возвращаемых командлетом Get-ScheduledJob, в **Get-scheduledjoboptions** .

**Get-scheduledjoboptions** — это одна из коллекций командлетов планирования заданий в модуле PSScheduledJob, который входит в состав Windows PowerShell.

Дополнительные сведения о запланированных заданиях см. в разделах описания в модуле PSScheduledJob.
Импортируйте модуль PSScheduledJob, а затем введите `Get-Help about_Scheduled*` или просмотрите статью about_Scheduled_Jobs.

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. получение параметров задания

```
PS C:\> Get-ScheduledJobOption -Name "*Backup*"
StartIfOnBatteries     : False

StopIfGoingOnBatteries : True

WakeToRun              : False

StartIfNotIdle         : True

StopIfGoingOffIdle     : False

RestartOnIdleResume    : False

IdleDuration           : 00:10:00

IdleTimeout            : 01:00:00

ShowInTaskScheduler    : True

RunElevated            : True

RunWithoutNetwork      : True

DoNotAllowDemandStart  : False

MultipleInstancePolicy : Ignore

NewJobDefinition       : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

Эта команда возвращает параметры задания для запланированных заданий, в именах которых есть резервная копия.
В результатах показан возвращенный **Get-ScheduledJobOption** объект параметров задания.

### Пример 2. получение всех параметров задания

```
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption
```

Эта команда возвращает параметры задания для всех запланированных заданий на локальном компьютере.

Он использует командлет Get-ScheduledJob для получения запланированных заданий на локальном компьютере.
Оператор конвейера (|) отправляет запланированные задания в командлет **Get-scheduledjoboptions** , который получает параметры задания для каждого запланированного задания.

### Пример 3. Получение выбранных параметров задания

```
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption | Where {$_.RunElevated -and !$_.WaketoRun}
StartIfOnBatteries     : False

StopIfGoingOnBatteries : True

WakeToRun              : True

StartIfNotIdle         : True

StopIfGoingOffIdle     : False

RestartOnIdleResume    : False

IdleDuration           : 00:10:00

IdleTimeout            : 01:00:00

ShowInTaskScheduler    : True

RunElevated            : True

RunWithoutNetwork      : True

DoNotAllowDemandStart  : False

MultipleInstancePolicy : Ignore

NewJobDefinition       : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition

The second command shows how to find to which scheduled job the job options belong. This command uses a pipeline operator (|) to send the selected job options to the ForEach-Object cmdlet, which gets the JobDefinition property of each options object. The JobDefinition property contains the originating job object. The results show that the selected options came from the DeployPkg scheduled job.
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption | Where {$_.RunElevated -and !$_.WaketoRun} | ForEach-Object {$_.JobDefinition}
Id         Name            Triggers        Command                                  Enabled

--         ----            --------        -------                                  -------

2          DeployPkg         {1, 2}        DeployPackage.ps1                        True
```

В этом примере показано, как найти объект параметров задания с определенными значениями.

Первая команда получает параметры задания, в которых свойство RunElevated имеет значение $True а свойство Рунвисаутнетворк имеет значение $False.
В выходных данных отображается выбранный объект **жобоптионс** .

### Пример 4. Использование параметров задания для создания нового задания

```
PS C:\> $Opts = Get-ScheduledJobOption -Name "BackupTestLogs"
PS C:\> Register-ScheduledJob -Name "Archive-Scripts" -FilePath "\\Srv01\Scripts\ArchiveScripts.ps1" -ScheduledJobOption $Opts
```

В этом примере показано, как использовать параметры задания, которые Get-ScheduledJobOption получаются в новом запланированном задании.

Первая команда использует **Get-scheduledjoboptions** для получения параметров заданий запланированного задания баккуптестлогс.
Команда сохраняет эти параметры в переменной $Opts.

Вторая команда использует командлет Register-ScheduledJob для создания нового запланированного задания.
Значение параметра *ScheduledJobOption* представляет собой объект параметров в переменной $Opts.

### Пример 5. получение параметров задания с удаленного компьютера

```
PS C:\> $O = Invoke-Command -ComputerName "Srv01" -ScriptBlock {Get-ScheduledJob -Name "DataDemon" }
```

Эта команда использует командлет Invoke-Command для получения параметров запланированного задания задания Датадемон на компьютере SRV01.
Команда сохраняет параметры в переменной $O.

## PARAMETERS

### -Id
Задает идентификационный номер запланированного задания.
**Get-ScheduledJobOption** получает параметры указанного запланированного задания.

Чтобы получить идентификационные номера запланированных заданий на локальном или удаленном компьютере, используйте командлет Get-ScheduledJob.

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
Введите переменную, содержащую объект **ScheduledJob** , или введите команду или выражение, которое получает объект **ScheduledJob** , например команду Get-ScheduledJob.
Можно также передать объект **ScheduledJob** в **Get-ScheduledJobOption** .

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
Задает имена запланированных заданий.
**Get-ScheduledJobOption** получает параметры указанного запланированного задания.
Поддерживаются подстановочные знаки.

Чтобы получить имена запланированных заданий на локальном или удаленном компьютере, используйте командлет Get-ScheduledJob.

```yaml
Type: System.String
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Вы можете передать запланированное задание из Get-ScheduledJob в командлет **Get-scheduledjoboptions** .

## Выходные данные

### Microsoft. PowerShell. ScheduledJob. Счедуледжобоптионс

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
