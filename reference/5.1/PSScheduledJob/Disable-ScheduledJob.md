---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/disable-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-ScheduledJob
ms.openlocfilehash: a7ea520d7d0365fd0de8c9d0bb767981b68467c6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227402"
---
# Disable-ScheduledJob

## Краткий обзор
Отключает запланированное задание.

## SYNTAX

### Определение (по умолчанию)

```
Disable-ScheduledJob [-InputObject] <ScheduledJobDefinition> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DefinitionId

```
Disable-ScheduledJob [-Id] <Int32> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DefinitionName

```
Disable-ScheduledJob [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Disable-ScheduledJob** временно отключает запланированные задания.
При отключении сохраняются все свойства заданий и не отключаются триггеры задания, однако запрещается автоматический запуск запланированных заданий при их активации с помощью триггера.
Вы можете запустить отключенное запланированное задание с помощью командлета Start-Job или использовать отключенное запланированное задание в качестве шаблона.

Чтобы отключить запланированное задание, командлет **Disable-ScheduledJob** задает для свойства **Enabled** запланированного задания значение False ($false).
Чтобы повторно включить запланированное задание, используйте командлет Enable-ScheduledJob.

**Disable-ScheduledJob** является одной из коллекций командлетов планирования заданий в модуле **PSScheduledJob** , включенном в Windows PowerShell.

Дополнительные сведения о запланированных заданиях см. в разделах описания в модуле PSScheduledJob.
Импортируйте модуль PSScheduledJob, а затем введите `Get-Help about_Scheduled*` или просмотрите статью about_Scheduled_Jobs.

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. Отключение запланированного задания

```
PS C:\> Disable-ScheduledJob -ID 2 -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    False
```

Эта команда отключает запланированное задание с идентификатором 2 на локальном компьютере.
В выходных данных приведены результаты выполнения команды.

### Пример 2. Отключение всех запланированных заданий

```
PS C:\> Get-ScheduledJob | Disable-ScheduledJob -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          ArchiveProje... {}              C:\Scripts\Archive-DxProjects.ps1        False
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    False
4          Test-HelpFiles  {1}             .\Test-HelpFiles.ps1                     False
5          TestJob         {1, 2}          .\Run-AllTests.ps1                       False
```

Эта команда отключает все запланированные задания на локальном компьютере.
Он использует командлет Get-ScheduledJob, чтобы получить все запланированные задания и командлет **Disable-ScheduledJob** , чтобы отключить их.

Вы можете повторно включить запланированное задание с помощью командлета Enable-ScheduledJob и запустить отключенное запланированное задание с помощью командлета Start-Job.

**Disable-ScheduledJob** не создает предупреждения или ошибки, если отключено запланированное задание, которое уже отключено, поэтому можно отключить все запланированные задания без условий.

### Пример 3. Отключение выбранных запланированных заданий

```
PS C:\> Get-ScheduledJob | Where-Object {!$_.Credential} | Disable-ScheduledJob
```

Команда отключает запланированное задание, не имеющее учетных данных.
Задания без учетных данных запускаются с разрешения создавшего их пользователя.

Она использует командлет Get-ScheduledJob для получения всех запланированных заданий на компьютере.
Оператор конвейера отправляет запланированные задания в командлет Where-Object, который выбирает запланированные задания, не имеющие учетных данных.
Команда использует оператор not (!) и ссылается на свойство Credential запланированного задания.
Другой конвейерный оператор запланированные задания в командлет **Disable-ScheduledJob** , который отключает их.

### Пример 4. отключение запланированных заданий на удаленном компьютере

```
PS C:\> Invoke-Command -ComputerName Srv01, Srv10 -ScriptBlock {Disable-ScheduledJob -Name TestJob}
```

Эта команда отключает запланированное задание TestJob на двух удаленных компьютерах — Srv01 и Srv10.

Команда использует командлет Invoke-Command для выполнения команды **Disable-ScheduledJob** на компьютерах SRV01 и Srv10.
Команда использует параметр *Name***Disable-ScheduledJob** для выбора запланированного задания TestJob на каждом компьютере.

### Пример 5. Отключение запланированного задания по его глобальному ИДЕНТИФИКАТОРу

```
The first command demonstrates one way of finding the GlobalID of a scheduled job. The command uses the Get-ScheduledJob cmdlet to get the scheduled jobs on the computer. A pipeline operator (|) sends the scheduled jobs to the Format-Table cmdlet, which displays the Name, GlobalID, and Command properties of each job in a table.
PS C:\> Get-ScheduledJob | Format-Table -Property Name, GlobalID, Command -Autosize
Name             GlobalId                             Command
----             --------                             -------
ArchiveProjects1 a26a0b3d-b4e6-44d3-8b95-8706ef621f7c C:\Scripts\Archive-DxProjects.ps1
Inventory        3ac37e5d-84c0-4a8f-9661-7e88ebb8f914 \\Srv01\Scripts\Get-FullInventory.ps1
Backup-Scripts   4d0cc6be-c082-48d1-baec-1bd8278f3c81  Copy-Item C:\CurrentScripts\*.ps1 -Destination C:\BackupScripts
Test-HelpFiles   d77020ca-f20d-42be-86c8-fc64df97db90 .\Test-HelpFiles.ps1
Test-HelpFiles   2f1606d2-c6cf-4bef-8b1c-ae36a9cc9934 .\Test-DomainHelpFiles.ps1

The second command uses the  Get-ScheduledJob cmdlet to get the scheduled jobs on the computer. A pipeline operator (|) sends the scheduled jobs to the Where-Object cmdlet, which selects the scheduled job with the specified global ID. Another pipeline operator sends the job to the **Disable-ScheduledJob** cmdlet, which disables it.
PS C:\> Get-ScheduledJob | Where-Object {$_.GlobalID = d77020ca-f20d-42be-86c8-fc64df97db90} | Disable-ScheduledJob
```

В этих примерах показано, как отключить запланированное задание с помощью его глобального идентификатора.
Значением свойства GlobalID запланированного задания является уникальный идентификатор (GUID).
Используйте значение GlobalID, когда необходима точность, например при отключении запланированных заданий на нескольких компьютерах.

## PARAMETERS

### -Id
Отключает запланированное задание с указанным идентификационным номером (идентификатором).
Введите идентификатор запланированного задания.

```yaml
Type: System.Int32
Parameter Sets: DefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Задает отключаемое запланированное задание.
Введите переменную, содержащую объекты **ScheduledJobDefinition** , либо укажите команду или выражение, возвращающие объекты **ScheduledJobDefinition** , например команду ScheduledJob.
Можно также передать объект **ScheduledJobDefinition** в командлет **Disable-ScheduledJob** .

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: Definition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Отключает запланированные задания с указанными именами.
Введите имя запланированного задания.
Поддерживаются подстановочные знаки.

```yaml
Type: System.String
Parameter Sets: DefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
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

### Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Запланированное задание можно передать в **Disable-ScheduledJob** .

## Выходные данные

### Нет или Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
При использовании параметра **Passthru** командлет **Disable-ScheduledJob** возвращает запланированное задание, которое было отключено.
В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

* **Disable-ScheduledJob** не создает предупреждения или ошибки, если вы используете его для отключения запланированного задания, которое уже отключено.

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
