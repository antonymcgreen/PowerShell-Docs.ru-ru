---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/enable-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-ScheduledJob
ms.openlocfilehash: 757402a348a6b694d2f2aee53053a1b7615dbb53
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227389"
---
# Enable-ScheduledJob

## Краткий обзор
Включает запланированное задание.

## SYNTAX

### Определение (по умолчанию)

```
Enable-ScheduledJob [-InputObject] <ScheduledJobDefinition> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DefinitionId

```
Enable-ScheduledJob [-Id] <Int32> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DefinitionName

```
Enable-ScheduledJob [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Enable-ScheduledJob** повторно включает отключенные запланированные задания, например те, которые отключены с помощью командлета Disable-ScheduledJob.
Включенные задания запускаются автоматически при активации триггера.

Чтобы включить запланированное задание, командлет **Enable-ScheduledJob** задает для свойства Enabled запланированного задания значение $true.

**Enabled-ScheduledJob** входит в коллекцию командлетов планирования заданий в модуле **PSScheduledJob** в составе Windows PowerShell.

Дополнительные сведения о запланированных заданиях см. в разделах описания в модуле PSScheduledJob.
Импортируйте модуль PSScheduledJob, а затем введите `Get-Help about_Scheduled*` или просмотрите статью about_Scheduled_Jobs.

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. Включение запланированного задания

```
PS C:\> Enable-ScheduledJob -ID 2 -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    True
```

Эта команда включает запланированное задание с идентификатором 2 на локальном компьютере.
В выходных данных приведены результаты выполнения команды.

### Пример 2. Включение всех запланированных заданий

```
PS C:\> Get-ScheduledJob | Enable-ScheduledJob -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          ArchiveProje... {}              C:\Scripts\Archive-DxProjects.ps1        True
2          Inventory       {1, 2}          \\Srv01\Scripts\Get-FullInventory.ps1    True
4          Test-HelpFiles  {1}             .\Test-HelpFiles.ps1                     True
5          TestJob         {1, 2}          .\Run-AllTests.ps1                       True
```

Эта команда включает все запланированные задания на локальном компьютере.
Она использует командлет Get-ScheduledJob для получения всех запланированных заданий и командлет **Enable-ScheduledJob** для их включения.

**Enable-ScheduledJob** не выдает предупреждения или ошибки при включении запланированного задания, которое уже включено, поэтому вы можете включить все запланированные задания без условий.

### Пример 3. Включение выбранных запланированных заданий

```
PS C:\> Get-ScheduledJob | Get-ScheduledJobOption | Where-Object {$_.RunWithoutNetwork} | ForEach-Object {Enable-ScheduledJob -InputObject $_.JobDefinition}
```

Эта команда включает запланированные задания, которые не требуют подключения к сети.

Она использует командлет Get-ScheduledJob для получения всех запланированных заданий на компьютере.
Конвейерный оператор отправляет запланированные задания в командлет Get-ScheduledJobOptions, который получает параметры задания для каждого из этих запланированных заданий.
Каждый объект параметров задания имеет свойство JobDefinition, которое содержит связанное запланированное задание.
Свойство JobDefinition используется для выполнения данной команды.

Команда использует оператор конвейера (|) для отправки параметров задания в командлет Where-Object, который выбирает объекты параметров запланированного задания, в которых свойство **рунвисаутнетворк** имеет значение True ($true).
Другой конвейерный оператор отправляет выбранные объекты параметров запланированного задания в командлет ForEach-Object, который выполняет команду **Enable-ScheduledJob** с запланированным заданием в значении свойства JobDefinition каждого объекта параметров задания.

### Пример 4. Включение запланированных заданий на удаленном компьютере

```
PS C:\> Invoke-Command -ComputerName "Srv01,Srv10" -ScriptBlock {Enable-ScheduledJob -Name "Inventory"}
```

Эта команда включает запланированные задания, которые имеют слово test в именах, на двух удаленных компьютерах — Srv01 и Srv10.

Она использует командлет Invoke-Command для выполнения команды **Enable-ScheduledJob** на компьютерах Srv01 и Srv10.
Команда использует параметр *Name***Enable-ScheduledJob** для включения запланированного задания инвентаризации на каждом компьютере.

## PARAMETERS

### -Id
Включает запланированное задание с указанным идентификационным номером (идентификатором).
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
Указывает запланированное задание, которое необходимо включить.
Введите переменную, содержащую объекты **ScheduledJobDefinition** , или введите команду или выражение, которое получает объекты **ScheduledJobDefinition** , такие как команда Get-ScheduledJob.
Вы также можете передать по конвейеру объект **ScheduledJobDefinition** в командлет **Enable-ScheduledJob** .

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
Включает запланированные задания с указанными именами.
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
Запланированное задание можно передать по конвейеру в **Enable-ScheduledJob** .

## Выходные данные

### Нет или Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
При использовании параметра **Passthru** командлет **Enable-ScheduledJob** возвращает запланированное задание, которое было включено.
В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

* **Enable-ScheduledJob** не выдает предупреждения или ошибки, если используется для включения запланированного задания, которое уже включено.

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
