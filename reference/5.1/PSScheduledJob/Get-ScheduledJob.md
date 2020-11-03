---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/get-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ScheduledJob
ms.openlocfilehash: 40224432c208ee45efc20f556312fa250e9bb7a6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227382"
---
# Get-ScheduledJob

## Краткий обзор
Получает запланированные задания на локальном компьютере.

## SYNTAX

### DefinitionId (по умолчанию)

```
Get-ScheduledJob [[-Id] <Int32[]>] [<CommonParameters>]
```

### DefinitionName

```
Get-ScheduledJob [-Name] <String[]> [<CommonParameters>]
```

## DESCRIPTION
Командлет **Get-ScheduledJob** возвращает запланированные задания на локальном компьютере.
**Get-ScheduledJob** возвращает только запланированные задания, созданные текущим пользователем с помощью командлета Register-ScheduledJob.

Хотя задания, созданные с помощью командлета **Register-ScheduledJob** , отображаются в планировщике заданий, **Get-ScheduledJob** возвращает только запланированные задания.
Он не возвращает запланированные задачи, созданные в планировщике.

Без параметров **Get-ScheduledJob** возвращает все запланированные задания на компьютере.
Можно использовать параметры командлета **Get-ScheduledJob** для получения запланированных заданий по идентификатору или имени и проверять их или передавать в другие командлеты.

**Get-ScheduledJob** — это одна из коллекций командлетов планирования заданий в модуле **PSScheduledJob** , который входит в состав Windows PowerShell.

Дополнительные сведения о запланированных заданиях см. в разделах описания в модуле PSScheduledJob.
Импортируйте модуль PSScheduledJob, а затем введите `Get-Help about_Scheduled*` или просмотрите статью about_Scheduled_Jobs.

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. получение всех запланированных заданий

```
PS C:\> Get-ScheduledJob
```

Эта команда возвращает все запланированные задания на локальном компьютере.

### Пример 2. Получение запланированных заданий по имени

```
PS C:\> Get-ScheduledJob -Name *Backup*, *Archive*
```

Эта команда возвращает все запланированные задания на компьютере, имена которых содержат резервную копию или Архив.
Формат этой команды позволяет искать определенные задания.

### Пример 3. Получение запланированных заданий на удаленных компьютерах

```
PS C:\> Invoke-Command -ComputerName (Get-Content Servers.txt) {Get-ScheduledJob}
```

Эта команда возвращает все запланированные задания на компьютерах, которые указаны в файле Servers.txt.
Команда использует командлет Invoke-Command для выполнения команды **Get-ScheduleJob** на каждом компьютере.

### Пример 4. Передача запланированных заданий по конвейеру другим командлетам

```
PS C:\> Get-ScheduledJob DailyBackup, WeeklyBackup | Get-JobTrigger
```

Эта команда получает триггеры задания для запланированных заданий DailyBackup и WeeklyBackup.
Он использует командлет **Get-ScheduledJob** для получения запланированных заданий и командлет Get-JobTrigger для получения триггеров заданий запланированных заданий.

## PARAMETERS

### -Id
Возвращает только запланированные задания с указанным идентификационным номером (идентификатором).
Введите один или несколько идентификаторов запланированных заданий на компьютере.
По умолчанию **Get-ScheduledJob** возвращает все запланированные задания на компьютере.

```yaml
Type: System.Int32[]
Parameter Sets: DefinitionId
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Возвращает только запланированные задания с указанными именами.
Введите одно или несколько имен запланированных заданий на компьютере.
Поддерживаются подстановочные знаки.
По умолчанию **Get-ScheduledJob** возвращает все запланированные задания на компьютере.

```yaml
Type: System.String[]
Parameter Sets: DefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет
Нельзя передать входные данные в командлет **Get-ScheduledJob** с помощью конвейера.

## Выходные данные

### Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition

## ПРИМЕЧАНИЯ

* Каждое запланированное задание сохраняется в подкаталоге каталога $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs на локальном компьютере. Этот подкаталог назван по имени запланированного задания и содержит XML-файл для этого задания и записи его журнала выполнения. Дополнительные сведения о запланированных заданиях на диске см. в описании about_Scheduled_Jobs_Advanced.
* Запланированные задания, созданные в Windows PowerShell, отображаются в планировщике заданий в папке "Библиотека планировщика заданий\Microsoft\Windows\PowerShell\ScheduledJobs". Планировщик заданий можно использовать для просмотра и изменения запланированного задания.
* Планировщик заданий, средство командной строки SchTasks.exe и командлеты планировщика заданий можно использовать для управления запланированными заданиями, созданные с помощью командлетов запланированных заданий. Однако нельзя использовать командлеты запланированных заданий для управления задачами, созданными в планировщике заданий.

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
