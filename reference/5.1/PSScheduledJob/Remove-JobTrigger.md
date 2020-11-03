---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/remove-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-JobTrigger
ms.openlocfilehash: adcd74361b1a045a57c7db2f15996f4ea53d6d5b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227370"
---
# Remove-JobTrigger

## Краткий обзор
Удаление триггеров заданий из запланированных заданий.

## SYNTAX

### JobDefinition (по умолчанию)

```
Remove-JobTrigger [-TriggerId <Int32[]>] [-InputObject] <ScheduledJobDefinition[]> [<CommonParameters>]
```

### жобдефинитионид

```
Remove-JobTrigger [-TriggerId <Int32[]>] [-Id] <Int32[]> [<CommonParameters>]
```

### жобдефинитионнаме

```
Remove-JobTrigger [-TriggerId <Int32[]>] [-Name] <String[]> [<CommonParameters>]
```

## DESCRIPTION
Командлет **Remove-JobTrigger** удаляет Триггеры заданий из запланированных заданий.

Триггер задания определяет повторяющееся расписание или условия для запуска запланированного задания.
Для управления триггерами заданий используйте командлеты New-JobTrigger, Add-JobTrigger, Set-JobTrigger и Set-ScheduledJob.

Используйте параметры *Name* , *ID* , или *InputObject* командлета **Remove-JobTrigger** для идентификации запланированных заданий, из которых удаляются триггеры.
Используйте параметр *TriggerID* , чтобы указать триггеры задания для удаления.
По умолчанию **Remove-JobTrigger** удаляет все триггеры задания для запланированных заданий.

**Remove-JobTrigger** — это одна из коллекций командлетов планирования заданий в модуле PSScheduledJob, который входит в состав Windows PowerShell.

Дополнительные сведения о запланированных заданиях см. в разделах описания в модуле PSScheduledJob.
Импортируйте модуль PSScheduledJob, а затем введите `Get-Help about_Scheduled*` или просмотрите статью about_Scheduled_Jobs.

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. Удаление всех триггеров заданий

```
PS C:\> Remove-JobTrigger -Name "Test*"
```

Эта команда удаляет все триггеры заданий из запланированного задания, имена которых начинаются с Test.

### Пример 2. Удаление выбранных триггеров заданий

```
PS C:\> Remove-JobTrigger -Name "BackupArchive" -TriggerID 3
```

Эта команда удаляет только третий триггер (с идентификатором 3) из запланированного задания BackupArchive.

### Пример 3. Удаление триггеров заданий AtStartup из всех запланированных заданий

```
PS C:\> function Delete-AtStartup
{
    Get-ScheduledJob | Get-JobTrigger | Where-Object {$_.Frequency -eq "AtStartup"} | ForEach-Object { Remove-JobTrigger -InputObject $_.JobDefinition -TriggerID $_.ID}
}
```

Эта функция удаляет все триггеры задания AtStartup из всех заданий на локальном компьютере.
Чтобы использовать функцию, запустите в сеансе функцию и введите `Delete-AtStartup` .

Функция Delete-AtStartup содержит одну команду.
Команда использует командлет Get-ScheduledJob для получения запланированных заданий на локальном компьютере.
Оператор конвейера (|) отправляет запланированные задания в командлет Get-JobTrigger, который получает все триггеры заданий из каждого из запланированных заданий.
Конвейерный оператор отправляет триггеры задания в командлет Where-Object, который выбирает Триггеры заданий, где значение свойства Frequency триггера задания равно AtStartup.

Объекты **JobTrigger** имеют свойство **JobDefinition** , которое содержит запланированное задание, которое они активируют.
Остальная часть команды использует эту функцию.

Конвейерный оператор отправляет триггеры задания AtStartup в командлет ForEach-Object, который выполняет команду **Remove-JobTrigger** для каждого триггера AtStartup.
Значением параметра *InputObject* командлета **Remove-JobTrigger** является запланированное задание в свойстве JobDefinition триггера задания.
Значением параметра *TriggerID* является идентификатор в свойстве ID триггера задания.

### Пример 4. Удаление триггера задания из удаленного запланированного задания

```
PS C:\> Invoke-Command -ComputerName "Server01" { Remove-JobTrigger -ID 38 -TriggerID 1 }
```

Эта команда удаляет первый триггер задания из задания Inventory на компьютере Server01.

Команда использует командлет **Invoke-Command** для выполнения командлета **Remove-JobTrigger** на компьютере Server01.
Командлет **Remove-JobTrigger** использует параметр *ID* для определения запланированного задания инвентаризации и параметр *TriggerID* для указания первого триггера.
Параметр *ID* особенно полезен, если несколько запланированных заданий имеют одинаковые или похожие имена.

## PARAMETERS

### -Id
Задает идентификационные номера запланированных заданий.
**Remove-JobTrigger** удаляет триггеры задания из указанных запланированных заданий.

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
Можно также передать объекты **ScheduledJob** в **Remove-JobTrigger** .

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
**Remove-JobTrigger** удаляет триггеры задания из указанных запланированных заданий.
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

### -TriggerId
Удаляет только указанные триггеры задания.
По умолчанию **Remove-JobTrigger** удаляет все триггеры из запланированных заданий.
Используйте этот параметр, если запланированные задания имеют несколько триггеров задания.

Введите идентификаторы триггеров одного или нескольких запланированных заданий.
Если указано несколько запланированных заданий, **Remove-JobTrigger** удаляет триггер задания с указанным идентификатором из всех запланированных заданий.

```yaml
Type: System.Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Можно передать запланированные задания в командлет **Remove-JobTrigger** .

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
