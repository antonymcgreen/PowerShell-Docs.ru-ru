---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/disable-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-JobTrigger
ms.openlocfilehash: 236e6b7e6e450bd1f3f868f889a19cf796890127
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227410"
---
# Disable-JobTrigger

## Краткий обзор
Отключает триггеры задания для запланированных заданий.

## SYNTAX

```
Disable-JobTrigger [-InputObject] <ScheduledJobTrigger[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Disable-JobTrigger** временно отключает триггеры задания для запланированных заданий.
При отключении сохраняются все свойства триггера задания, однако запрещается запуск запланированного задания триггером задания.

Чтобы использовать этот командлет, используйте командлет Get-JobTrigger, чтобы получить триггеры задания.
Затем передайте триггеры задания в командлет **Disable-JobTrigger** или используйте его параметр *InputObject* .

Чтобы отключить триггер задания, командлет **Disable-JobTrigger** задает для свойства Enabled триггера задания значение $false.
Чтобы повторно включить триггер задания, используйте командлет Enable-JobTrigger, который задает для свойства **Enabled** триггера задания значение $true.
Отключение триггера задания не приводит к отключению запланированного задания, как это делается командлетом Disable-ScheduledJob, но если отключить все триггеры заданий, то результат будет таким же, как и при отключении запланированного задания.

При отключении запланированного задания или отключении всех триггеров заданий по расписанию можно запустить задание с помощью командлета Start-Job или использовать отключенное запланированное задание в качестве шаблона.

**Disable-ScheduledJob** является одной из коллекций командлетов планирования заданий в модуле **PSScheduledJob** , включенном в Windows PowerShell.

Дополнительные сведения о запланированных заданиях см. в разделах описания в модуле PSScheduledJob.
Импортируйте модуль PSScheduledJob, а затем введите `Get-Help about_Scheduled*` или просмотрите статью about_Scheduled_Jobs.

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. Отключение триггера задания

```
PS C:\> Get-JobTrigger -Name "Backup-Archives" -TriggerID 1 | Disable-JobTrigger
```

Эта команда отключает первый триггер (с идентификатором 1) запланированного задания Backup-Archives на локальном компьютере.

Команда использует командлет Get-JobTrigger для получения триггера задания.
Конвейерный оператор отправляет триггер задания в командлет **Disable-JobTrigger** , который отключает его.

### Пример 2. Отключение всех триггеров заданий

```
The first command uses the Get-ScheduledJob cmdlet to get the Backup-Archives and Inventory scheduled jobs. A pipeline operator (|) sends the scheduled jobs to the Get-JobTrigger cmdlet, which gets all job triggers of the scheduled jobs. Another pipeline operator sends the job triggers to the **Disable-JobTrigger** cmdlet, which disables them.The first command uses the **Get-ScheduledJob** cmdlet to get the jobs, because its *Name* parameter takes multiple names.
PS C:\> Get-ScheduledJob -Name "Backup-Archives,Inventory" | Get-JobTrigger | Disable-JobTrigger

The second command displays the results. The command repeats the **Get-ScheduledJob** and **Get-JobTrigger** command. A pipeline operator sends the job triggers to the Format-Table cmdlet, which displays the job triggers in a table. The **Format-Table** command adds a JobName property that displays the value of the Name property of the scheduled job in the JobDefinition property of the job trigger object.
PS C:\> Get-ScheduledJob -Name "Backup-Archives,Inventory" | Get-JobTrigger | Format-Table -Property ID, Frequency, At, DaysOfWeek, Enabled, @{Label="JobName";Expression={$_.JobDefinition.Name}} -AutoSize
Id Frequency At                     DaysOfWeek Enabled JobName
-- --------- --                     ---------- ------- -------
1  Weekly    9/28/2011 3:00:00 AM   {Monday}   False   Backup-Archive
2  Daily     9/29/2011 1:00:00 AM              False   Backup-Archive
1  Weekly    10/20/2011 11:00:00 PM {Friday}   False   Inventory
1  Weekly    11/2/2011 2:00:00 PM   {Monday}   False   Inventory
```

Эти команды отключают все триггеры задания для двух запланированных заданий и отображают результаты.

### Пример 3. Отключение триггера задания запланированного задания на удаленном компьютере

```
PS C:\> Invoke-Command -ComputerName Server01 {Get-JobTrigger -Name DeployPackage | Where-Object {$_.Frequency -eq "Daily"} | Disable-JobTrigger}
```

Эта команда отключает триггеры задания Daily для запланированного задания DeployPackage на удаленном компьютере Server01.

Команда использует командлет Invoke-Command для выполнения команд на компьютере Server01.
Удаленная команда использует командлет Get-JobTrigger, чтобы получить триггеры для запланированного задания DeployPackage.
Конвейерный оператор отправляет триггеры задания в командлет Where-Object, который возвращает только ежедневные Триггеры заданий.
Оператор конвейера отправляет триггеры ежедневного задания в командлет **Disable-JobTrigger** , который отключает их.

## PARAMETERS

### -InputObject
Задает отключаемый триггер задания.
Введите переменную, содержащую объекты  **ScheduledJobTrigger** , или введите команду или выражение, которое получает объекты **ScheduledJobTrigger** , такие как команда Get-JobTrigger.
Можно также передать объект **ScheduledJobTrigger** в командлет **Disable-JobTrigger** .

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
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
Default value: None
Accept pipeline input: False
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

### Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger
Можно передать триггеры задания в **Disable-JobTrigger** .

## Выходные данные

### Нет
Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

* **Disable-JobTrigger** не создает ошибок или предупреждений, если отключен триггер задания, который уже отключен.

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
