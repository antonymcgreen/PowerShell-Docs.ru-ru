---
external help file: Microsoft.PowerShell.ScheduledJob.dll-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/add-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-JobTrigger
ms.openlocfilehash: 6066b8f91c99830fefb09a8bea13fac6ddf958e9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227413"
---
# Add-JobTrigger

## Краткий обзор
Добавляет триггеры задания в запланированные задания.

## SYNTAX

### JobDefinition (по умолчанию)

```
Add-JobTrigger [-Trigger] <ScheduledJobTrigger[]> [-InputObject] <ScheduledJobDefinition[]>
 [<CommonParameters>]
```

### жобдефинитионид

```
Add-JobTrigger [-Trigger] <ScheduledJobTrigger[]> [-Id] <Int32[]> [<CommonParameters>]
```

### жобдефинитионнаме

```
Add-JobTrigger [-Trigger] <ScheduledJobTrigger[]> [-Name] <String[]> [<CommonParameters>]
```

## DESCRIPTION
Командлет **Add-JobTrigger** добавляет триггеры задания в запланированные задания.
Его можно использовать для добавления нескольких триггеров в несколько запланированных заданий.

Триггер задания запускает запланированное задание в однократном или повторяющемся расписании или при возникновении события.

Используйте параметр *Trigger* командлета **Add-JobTrigger** , чтобы указать триггеры заданий для добавления.
Используйте параметры *Name* , *ID* или *InputObject* командлета **Add-JobTrigger** , чтобы указать запланированное задание, в которое добавляются триггеры.

Чтобы создать триггеры задания для значения параметра *Trigger* , используйте командлет New-JobTrigger или хэш-таблицу, чтобы указать триггер задания.

**Add-JobTrigger** — это одна из коллекций командлетов планирования заданий в модуле **PSScheduledJob** , который входит в состав Windows PowerShell.

Дополнительные сведения о запланированных заданиях см. в разделах описания в модуле PSScheduledJob.
Импортируйте модуль PSScheduledJob, а затем введите `Get-Help about_Scheduled*` или просмотрите статью about_Scheduled_Jobs.

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. добавление триггера задания в запланированное задание

```
PS C:\> $Daily = New-JobTrigger -Daily -At 3AMPS
PS C:\> Add-JobTrigger -Trigger $Daily -Name "TestJob"
```

Эти команды добавляют триггер задания Daily в запланированное задание TestJob.

Первая команда использует командлет New-JobTrigger для создания триггера задания, запускающего запланированное задание каждый день в 3:00 утра.
Команда сохраняет триггер задания в переменной $Daily.

Вторая команда использует командлет **Add-JobTrigger** , чтобы добавить триггер задания в переменной $Startup в запланированное задание TestJob.

### Пример 2. добавление триггера задания в несколько запланированных заданий

```
PS C:\> Get-ScheduledJob | Add-JobTrigger -Trigger (New-JobTrigger -AtStartup)
```

Эта команда добавляет триггер задания AtStartup во все запланированные задания на локальном компьютере.
Для получения всех запланированных заданий на компьютере используется Get-ScheduledJob.
Она использует конвейерный оператор (|) для отправки заданий в командлет **Add-JobTrigger** , который добавляет триггер задания для каждого из запланированных заданий.
Значением параметра *Trigger* является New-JobTrigger команда, создающая триггер задания AtStartup.

### Пример 3. копирование триггера задания

```
PS C:\> $T = Get-JobTrigger -Name "BackupArchives"
PS C:\> Add-JobTrigger -Name "TestBackup,BackupLogs" -Trigger $T
```

Эти команды копируют триггер задания из запланированного задания BackupArchives и добавляют его в запланированные задания TestBackup и BackupLogs.

Первая команда использует командлет Get-JobTrigger для получения триггера задания запланированного задания запланированного.
Команда сохраняет триггер в переменной $t.

Вторая команда использует командлет **Add-JobTrigger** , чтобы добавить триггер задания в переменной $t в запланированные задания TestBackup и BackupLogs.

## PARAMETERS

### -Id
Задает идентификационные номера запланированных заданий.
**Add-JobTrigger** добавляет триггер задания для указанных запланированных заданий.

Чтобы получить идентификационный номер запланированных заданий на локальном или удаленном компьютере, используйте командлет Get-ScheduledJob.

```yaml
Type: System.Int32[]
Parameter Sets: JobDefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Указывает запланированные задания.
Введите переменную, содержащую объекты **ScheduledJob** , или введите команду или выражение, которое получает объекты **ScheduledJob** , такие как команда Get-ScheduledJob.
Вы также можете передать объекты **ScheduledJob** в командлет **Add-JobTrigger** .

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition[]
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
**Add-JobTrigger** добавляет триггеры задания для указанных запланированных заданий.
Поддерживаются подстановочные знаки.

Чтобы получить имена запланированных заданий на локальном или удаленном компьютере, используйте командлет Get-ScheduledJob.

```yaml
Type: System.String[]
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Триггер
Указывает триггеры задания для добавления.
Введите хэш-таблицу, которая указывает триггеры задания или переменную, содержащую объекты **ScheduledJobTrigger** , либо введите команду или выражение, которое получает объекты **ScheduledJobTrigger** , например команду Get-JobTrigger.
Вы также можете передать объекты **ScheduledJobTrigger** в командлет **Add-JobTrigger** .

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Microsoft. PowerShell. ScheduledJob. ScheduledJobTrigger, Microsoft. PowerShell. ScheduledJob. ScheduledJobDefinition
Можно передать триггеры задания или запланированные задания в **Add-JobTrigger** .

## Выходные данные

### Нет
Этот командлет не возвращает никакие выходные данные.

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
