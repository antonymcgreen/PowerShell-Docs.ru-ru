---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/unregister-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-ScheduledJob
ms.openlocfilehash: 0c0b55513bcfdcebdcd5d8a6f17968a4a45e2839
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227350"
---
# Unregister-ScheduledJob

## Краткий обзор
Удаляет запланированные задания на локальном компьютере.

## SYNTAX

### Определение (по умолчанию)

```
Unregister-ScheduledJob [-InputObject] <ScheduledJobDefinition[]> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DefinitionId

```
Unregister-ScheduledJob [-Id] <Int32[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DefinitionName

```
Unregister-ScheduledJob [-Name] <String[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Unregister-ScheduledJob** удаляет запланированные задания с локального компьютера.

При удалении или отмене регистрации запланированного задания **Unregister-ScheduledJob** удаляет каталог для запланированного задания (в каталоге $Home \аппдата\локал\микрософт\виндовс\повершелл\счедуледжобс), который содержит XML-файл, определяющий запланированное задание, журнал выполнения задания и все результаты задания.
Это действие также удаляет задание из планировщика заданий.

**Unregister-ScheduledJob** удаляет только запланированные задания, созданные с помощью командлета Register-ScheduledJob.
Он не удаляет запланированные задания, созданные в планировщике заданий.

Для удаления запланированных заданий по ИДЕНТИФИКАТОРу или имени можно использовать параметры командлета **Unregister-ScheduledJob** , а также передавать запланированные задания из Get-ScheduledJob в **Reregister-ScheduledJob** .

**Unregister-ScheduledJob** — это одна из коллекций командлетов планирования заданий в модуле PSScheduledJob, который входит в состав Windows PowerShell.

Дополнительные сведения о запланированных заданиях см. в разделах описания в модуле PSScheduledJob.
Импортируйте модуль PSScheduledJob, а затем введите `Get-Help about_Scheduled*` или просмотрите статью about_Scheduled_Jobs.

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. Удаление запланированного задания

```
PS C:\> Unregister-ScheduledJob TestJob
```

Эта команда удаляет запланированное задание TestJob на локальном компьютере.

### Пример 2. Удаление всех запланированных заданий

```
PS C:\> Get-ScheduledJob | Unregister-ScheduledJob -Force
PS C:\> Unregister-ScheduledJob -Name "*" -Force
```

В этом примере показаны две разные команды, которые удаляют все запланированные задания на локальном компьютере.

Первая команда использует командлет Get-ScheduledJob для получения всех запланированных заданий на локальном компьютере.
Конвейерный оператор (|) отправляет запланированные задания в командлет **Unregister-ScheduleJob** , который удаляет их.

Вторая команда использует параметр *Name* командлета **Unregister-ScheduledJob** со значением "все" (*) для удаления всех запланированных заданий.

Обе команды используют параметр *Force* , который удаляет запланированное задание, даже если выполняется его экземпляр.

### Пример 3. Удаление запланированного задания на удаленном компьютере

```
PS C:\> Invoke-Command -ComputerName "Server01" { Unregister-ScheduledJob -Name "Test*"}
```

Эта команда удаляет запланированные задания с именами, которые начинаются с Test на удаленном компьютере Server01.
Команда использует командлет Invoke-Command для выполнения команды **Unregister-ScheduledJob** на компьютере Server02.

## PARAMETERS

### -Force
Удаляет запланированное задание, даже если выполняется его экземпляр.
По умолчанию **Unregister-ScheduledJob** не приводит к прекращению выполнения заданий.

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
Удаляет запланированные задания с указанными идентификационными номерами (идентификаторами).
Введите идентификаторы запланированных заданий на компьютере.

```yaml
Type: System.Int32[]
Parameter Sets: DefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Указывает запланированное задание.
Введите переменную, содержащую объекты **ScheduledJob** , или введите команду или выражение, которое получает объекты **ScheduledJob** , такие как команда Get-ScheduledJob.
Вы также можете передать объекты **ScheduledJob** в командлет **Reregister-JobTrigger** .

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition[]
Parameter Sets: Definition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Удаляет запланированные задания с указанными именами.
Введите имена одного или нескольких запланированных заданий на компьютере.
Поддерживаются подстановочные знаки.

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
Можно передать запланированные задания в Unregister-ScheduledJob.

## Выходные данные

### Нет
Этот командлет не формирует никаких выходных данных.

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
