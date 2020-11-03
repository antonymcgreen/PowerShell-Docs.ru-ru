---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/enable-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-JobTrigger
ms.openlocfilehash: d08b55f4ba78af69608ac74c097fc6851164093b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227386"
---
# Enable-JobTrigger

## Краткий обзор
Включает триггеры задания для запланированных заданий.

## SYNTAX

```
Enable-JobTrigger [-InputObject] <ScheduledJobTrigger[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Enable-JobTrigger** повторно включает отключенные триггеры запланированных заданий, например те, которые были отключены с помощью командлета Disable-JobTrigger.
Включенные и повторно включенные триггеры заданий могут запускать запланированные задания сразу же, не требуя перезагрузки Windows или Windows PowerShell.

Чтобы использовать этот командлет, воспользуйтесь командлетом Get-JobTrigger для получения триггеров заданий.
Затем передайте триггеры заданий в командлет **Enable-JobTrigger** или используйте его параметр *InputObject* .

Чтобы включить триггер задания, командлет **Enable-JobTrigger** задает для свойства Enabled триггера задания значение $true.

**Enabled-ScheduledJob** входит в коллекцию командлетов планирования заданий в модуле **PSScheduledJob** в составе Windows PowerShell.

Дополнительные сведения о запланированных заданиях см. в разделах описания в модуле PSScheduledJob.
Импортируйте модуль PSScheduledJob, а затем введите `Get-Help about_Scheduled*` или просмотрите статью about_Scheduled_Jobs.

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. Включение триггера задания

```
PS C:\> Get-JobTrigger -Name Backup-Archives -TriggerID 1 | Enable-JobTrigger
```

Эта команда включает первый триггер (с идентификатором 1) запланированного задания Backup-Archives на локальном компьютере.

Команда использует командлет Get-JobTrigger для получения триггера задания.
Конвейерный оператор отправляет триггер задания в командлет **Enable-JobTrigger** , который включает его.

### Пример 2. Включение всех триггеров заданий

```
PS C:\> Get-ScheduledJob | Get-JobTrigger | Enable-JobTrigger
```

Она использует командлет Get-ScheduledJob для получения запланированных заданий на локальном компьютере.
Конвейерный оператор (|) отправляет запланированные задания в командлет Get-JobTrigger, который получает все триггеры для каждого из запланированных заданий.
Другой конвейерный оператор отправляет триггеры заданий в командлет **Enable-JobTrigger** , который включает их.

### Пример 3. Включение триггера задания запланированного задания на удаленном компьютере

```
PS C:\> Invoke-Command -ComputerName Server01 {Get-JobTrigger -Name DeployPackage | Where-Object {$_.Frequency -eq "AtLogon"} | Enable-JobTrigger}
```

Эта команда повторно включает триггеры заданий AtLogon для запланированного задания DeployPackage на удаленном компьютере Server01.

Команда использует командлет Invoke-Command для выполнения команд на компьютере Server01.
Удаленная команда использует командлет Get-JobTrigger, чтобы получить триггеры для запланированного задания DeployPackage.
Конвейерный оператор отправляет триггеры заданий в командлет Where-Object, который возвращает только триггеры заданий AtLogon.
Конвейерный оператор отправляет триггеры задания AtLogon в командлет **Enable-JobTrigger** , который включает их.

### Пример 4. Отображение отключенных триггеров заданий

```
PS C:\> Get-ScheduledJob | Get-JobTrigger | where {!$_.Enabled} | Format-Table Id, Frequency, At, DaysOfWeek, Enabled, @{Label="JobName";Expression={$_.JobDefinition.Name}}
Id Frequency At                     DaysOfWeek Enabled JobName
-- --------- --                     ---------- ------- -------
 1    Weekly 9/28/2011 3:00:00 AM   {Monday}   False   Backup-Archive
 2    Daily  9/29/2011 1:00:00 AM              False   Backup-Archive
 1    Weekly 10/20/2011 11:00:00 PM {Friday}   False   Inventory
 1    Weekly 11/2/2011 2:00:00 PM   {Monday}   False   Inventory
```

Эта команда отображает все отключенные триггеры всех запланированных заданий в таблице.
Данную команду можно использовать для поиска триггеров заданий, которые может потребоваться включить.

Команда использует командлет Get-ScheduledJob для получения запланированных заданий на локальном компьютере.
Конвейерный оператор (|) отправляет запланированные задания в командлет Get-JobTrigger, который получает все триггеры для каждого из запланированных заданий.
Другой конвейерный оператор отправляет триггеры заданий в командлет Where-Object, который возвращает только отключенные триггеры заданий, то есть тех, где значение свойства Enabled триггера задания отличается (!) от true.

Другой конвейерный оператор отправляет отключенные триггеры заданий в командлет Format-Table, который отображает выбранные свойства триггеров заданий в таблице.
В набор свойств входит новое свойство JobName, которое отображает имя запланированного задания в свойстве JobDefinition триггера задания.

## PARAMETERS

### -InputObject
Указывает триггер задания для включения.
Введите переменную, содержащую объекты **ScheduledJobTrigger** , или введите команду или выражение, которое получает объекты **ScheduledJobTrigger** , такие как команда Get-JobTrigger.
Можно также передать по конвейеру объект **ScheduledJobTrigger** в командлет **Enable-JobTrigger** .

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
Можно передать триггеры заданий в **Enable-JobTrigger** .

## Выходные данные

### Нет
Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

* **Enable-JobTrigger** не выдает предупреждения или ошибки при включении триггера задания, который уже включен.

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
