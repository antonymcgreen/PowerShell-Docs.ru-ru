---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/new-scheduledjoboption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ScheduledJobOption
ms.openlocfilehash: 35ada8d5aaa6a6c1fdc74a089308aefe13598b10
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227374"
---
# New-ScheduledJobOption

## Краткий обзор
Создает объект, содержащий дополнительные параметры для запланированного задания.

## SYNTAX

```
New-ScheduledJobOption [-RunElevated] [-HideInTaskScheduler] [-RestartOnIdleResume]
 [-MultipleInstancePolicy <TaskMultipleInstancePolicy>] [-DoNotAllowDemandStart] [-RequireNetwork]
 [-StopIfGoingOffIdle] [-WakeToRun] [-ContinueIfGoingOnBattery] [-StartIfOnBattery] [-IdleTimeout <TimeSpan>]
 [-IdleDuration <TimeSpan>] [-StartIfIdle] [<CommonParameters>]
```

## DESCRIPTION
Командлет **New-ScheduledJobOption** создает объект, содержащий дополнительные параметры для запланированного задания.

Можно использовать объект **ScheduledJobOptions** , возвращаемый **New-ScheduledJobOption** , чтобы задать параметры задания для нового или существующего запланированного задания.
Кроме того, можно задать параметры задания с помощью командлета Get-ScheduledJobOption, чтобы получить параметры задания существующего запланированного задания или использовать значение хэш-таблицы для представления параметров задания.

Без параметров командлет **New-scheduledjoboptions** создает объект, который содержит значения по умолчанию для всех параметров.
Поскольку все свойства, кроме свойства JobDefinition, доступны для изменения, вы можете использовать итоговый объект в качестве шаблона и создавать стандартные объекты параметров для своей организации.

При создании запланированных заданий и настройки их параметров проверьте значения по умолчанию для всех параметров запланированного задания.
Запланированные задания запускаются только в том случае, если соблюдены все условия их выполнения.

**New-scheduledjoboptions** — это одна из коллекций командлетов планирования заданий в модуле PSScheduledJob, который входит в состав Windows PowerShell.

Дополнительные сведения о запланированных заданиях см. в разделах описания в модуле PSScheduledJob.
Импортируйте модуль PSScheduledJob, а затем введите `Get-Help about_Scheduled*` или просмотрите статью about_Scheduled_Jobs.

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. Создание объекта параметра запланированного задания со значениями по умолчанию

```
PS C:\> New-ScheduledJobOption
StartIfOnBatteries     : False
StopIfGoingOnBatteries : True
WakeToRun              : False
StartIfNotIdle         : True
StopIfGoingOffIdle     : False
RestartOnIdleResume    : False
IdleDuration           : 00:10:00
IdleTimeout            : 01:00:00
ShowInTaskScheduler    : True
RunElevated            : False
RunWithoutNetwork      : True
DoNotAllowDemandStart  : False
MultipleInstancePolicy : Ignore
NewJobDefinition       :
```

Эта команда создает объект параметров запланированного задания со всеми значениями по умолчанию.

### Пример 2. Создание объекта параметра запланированного задания с пользовательскими значениями

```
PS C:\> New-ScheduledJobOption -RequireNetwork -StartIfOnBattery
StartIfOnBatteries     : True
StopIfGoingOnBatteries : True
WakeToRun              : False
StartIfNotIdle         : True
StopIfGoingOffIdle     : False
RestartOnIdleResume    : False
IdleDuration           : 00:10:00
IdleTimeout            : 01:00:00
ShowInTaskScheduler    : True
RunElevated            : False
RunWithoutNetwork      : False
DoNotAllowDemandStart  : False
MultipleInstancePolicy : Ignore
NewJobDefinition       :
```

Следующая команда создает объект запланированного задания, который требует наличия сети и запускает запланированное задание, даже если компьютер не подключен к электросети.

Выходные данные показывают, что параметр *рекуиренетворк* изменил значение свойства рунвисаутнетворк на $false, а параметр *стартифонбаттери* изменил значение свойства стартифонбаттериес на $true.

### Пример 3. Задание параметров для нового запланированного задания

```
The first command creates a **ScheduledJobOptions** object with the *RunElevated* parameter. It saves the object in the $RunAsAdmin variable.
PS C:\> $RunAsAdmin = New-ScheduledJobOption -RunElevated

The second command uses the Register-ScheduledJob cmdlet to create a new scheduled job. The value of the *ScheduledJobOption* parameter is the option object in the value of the $RunAsAdmin variable.
PS C:\> Register-ScheduledJob -Name Backup -FilePath D:\Scripts\Backup.ps1 -Trigger $Mondays -ScheduledJobOption $RunAsAdmin

The third command uses the Get-ScheduledJobOption cmdlet to get the job options of the Backup scheduled job.The cmdlet output shows that the RunElevated property is set to $True and the JobDefinition property of the job option object is now populated with the scheduled job object for the Backup scheduled job.
PS C:\> Get-ScheduledJobOption -Name Backup
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
MultipleInstancePolicy : IgnoreNew
JobDefinition          : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

В этом примере показано, как использовать объект **ScheduledJobOptions** , возвращаемый **New-ScheduledJobOption** , чтобы задать параметры для нового запланированного задания.

### Пример 4. Сортировка свойств объекта параметра запланированного задания

```
PS C:\> $Options = New-ScheduledJobOption -WakeToRun
PS C:\> $Options.PSObject.Properties | Sort-Object -Property Name | Format-Table -Property Name, Value -Autosize
Name                       Value
----                       -----
DoNotAllowDemandStart      False
IdleDuration            00:10:00
IdleTimeout             01:00:00
JobDefinition
MultipleInstancePolicy IgnoreNew
RestartOnIdleResume        False
RunElevated                False
RunWithoutNetwork           True
ShowInTaskScheduler         True
StartIfNotIdle              True
StartIfOnBatteries         False
StopIfGoingOffIdle         False
StopIfGoingOnBatteries      True
WakeToRun                   True
```

В этом примере показано, как сортировать свойства объекта **ScheduledJobOptions** в алфавитном порядке для облегчения процесса чтения.

Первая команда использует командлет **New-ScheduledJobOption** для создания объекта **ScheduledJobOptions** .
Команда использует параметр *WakeToRun* и сохраняет полученный объект в переменной $Options.

Чтобы получить свойства $Options в виде объектов, во второй команде используется свойство **PSObject** всех объектов Windows PowerShell и его свойство Properties.
Затем команда передает объекты свойств в командлет Sort-Object, который сортирует свойства в алфавитном порядке по имени, а затем в командлет Format-Table, в котором отображаются имена и значения свойств в таблице.

Этот формат значительно упрощает поиск свойства Вакеторун объекта **счедуледжобоптионс** в $Options и проверку того, что его значение изменилось с $False на $true.

## PARAMETERS

### -Континуеифгоингонбаттери
Не останавливайте запланированное задание, если компьютер переключается на питание от батареи (отключается от электросети) во время выполнения этого задания.
По умолчанию запланированные задания останавливаются при отключении компьютера от электросети.

Параметр *континуеифгоингонбаттери* задает для свойства стопифгоингонбаттериес запланированных заданий значение $true.

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

### -Доноталловдемандстарт
Запускайте задание только при его активации.
Пользователи не могут запускать задание вручную, например с помощью функции запуска компонентов в планировщике заданий.

Этот параметр влияет только на планировщик.
Он не запрещает пользователям использовать командлет Start-Job для запуска задания.

Параметр *доноталловдемандстарт* задает для свойства доноталловдемандстарт запланированных заданий значение $true.

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

### -Хидеинтасксчедулер
Не отображайте задание в планировщике заданий.
Это значение затрагивает только компьютер, на котором выполняется задание.
По умолчанию запланированные задачи отображаются в планировщике заданий.

Даже если задача скрыта, пользователи могут отобразить задачу, выбрав параметр Показать скрытые задачи в планировщик задач.

Параметр *хидеинтасксчедулер* задает для свойства шовинтасксчедулер запланированных заданий значение $false.

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

### -Идледуратион
Указывает, как долго компьютер должен простаивать перед запуском задания.
Значение по умолчанию — 10 минут.
Если компьютер еще не простаивает заданное время на момент истечения периода *IdleTimeout* , запланированное задание не выполняется до следующего запланированного времени, если такое имеется.

Введите объект **TimeSpan** , например созданный командлетом New-TimeSpan, или введите значение в \<hours\> \<minutes\> формате:: \<seconds\> Format, который автоматически преобразуется в объект **TimeSpan** .

Чтобы включить это значение, используйте параметр *StartIfIdle* .
По умолчанию свойство Стартифнотидле запланированных заданий имеет значение $True и Windows PowerShell игнорирует значения *идледуратион* и *IdleTimeout* .

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdleTimeout
Указывает, как долго запланированное задание ожидает нахождения компьютера в неактивном состоянии.
Если при истечении этого времени ожидания компьютер бездействует меньше периода времени, определяемого параметром *IdleDuration* , задание не выполняется до следующего запланированного времени, если оно имеется.
Значение по умолчанию — один час.

Введите объект **TimeSpan** , например созданный командлетом New-TimeSpan, или введите значение в \<hours\> \<minutes\> формате:: \<seconds\> Format, который автоматически преобразуется в объект **TimeSpan** .

Чтобы включить это значение, используйте параметр *StartIfIdle* .
По умолчанию свойство Стартифнотидле запланированных заданий имеет значение $True и Windows PowerShell игнорирует значения *идледуратион* и *IdleTimeout* .

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Мултиплеинстанцеполици
Определяет, как система реагирует на запрос о запуске экземпляра запланированного задания во время выполнения другого экземпляра этого задания.
Значение по умолчанию — Игноренев.
Допустимые значения для этого параметра:

- Игноренев.
Новый экземпляр задания игнорируется.
- Параллельный.
Новый экземпляр задания запускается немедленно.
- Очередь.
Новый экземпляр задания запускается сразу после завершения текущего экземпляра.
- Стопексистинг.
Текущий экземпляр задания останавливается и запускается новый экземпляр.

Чтобы запустить задание, должны быть выполнены все условия для расписания задания.
Например, если условия, заданные параметрами *рекуиренетворк* , *идледуратион* и *IdleTimeout* , не удовлетворены, экземпляр задания не запускается, независимо от значения этого параметра.

```yaml
Type: Microsoft.PowerShell.ScheduledJob.TaskMultipleInstancePolicy
Parameter Sets: (All)
Aliases:
Accepted values: None, IgnoreNew, Parallel, Queue, StopExisting

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Рекуиренетворк
Запускает запланированное задание только при наличии доступных сетевых подключений.

Если указать этот параметр и в запланированное время запуска задания сеть будет недоступна, задание не запускается до следующего запланированного времени запуска, если такое имеется.

Параметр *рекуиренетворк* задает для свойства рунвисаутнетворк запланированных заданий значение $false.

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

### -Рестартонидлересуме
Перезапускает запланированное задание, если компьютер переходит в состояние простоя.
Этот параметр работает с параметром *StopIfGoingOffIdle* , который приостанавливает выполнение запланированного задания, если компьютер становится активным (выходит из состояния простоя).

Параметр *рестартонидлересуме* задает для свойства рестартонидлересуме запланированных заданий значение $true.

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

### -RunElevated
Запускает запланированное задание с правами члена группы администраторов на компьютере, где выполняется задание.

Чтобы включить выполнение запланированного задания с разрешениями администратора, используйте параметр *Credential* параметра Register-ScheduledJob, чтобы предоставить явные учетные данные для задания.

Параметр *RunElevated* задает для свойства RunElevated запланированных заданий значение $true.

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

### -Стартифидле
Запускает запланированное задание, если до истечения времени, заданного параметром *IdleDuration* , компьютер уже простаивал на протяжении заданного параметром *IdleTimeout* периода.

По умолчанию параметры *IdleDuration* и *IdleTimeout* игнорируются, и задание запускается в запланированное время, даже если компьютер занят.

Если указать этот параметр и в запланированное время запуска задания компьютер будет занят (не будет простаивать), задание не запускается до следующего запланированного времени запуска, если такое имеется.

Параметр *стартифидле* задает для свойства стартифнотидле запланированных заданий значение $false.

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

### -Стартифонбаттери
Запускает запланированное задание, даже если в запланированное время запуска компьютер работает от батарей.
Значение по умолчанию — $False.

Параметр *стартифонбаттери* задает для свойства стартифонбаттериес запланированных заданий значение $true.

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

### -Стопифгоингоффидле
Приостанавливает выполнение запланированного задания, если компьютер становится активным (выходит из режима простоя) во время выполнения задания.

По умолчанию запланированное задание, которое приостанавливается при выходе компьютера из режима простоя, возобновляется, когда компьютер снова становится неактивным.
Чтобы изменить это поведение по умолчанию, используйте параметр *RestartOnIdleResume* .

Параметр *стопифгоингоффидле* задает для свойства стопифгоингоффидле запланированных заданий значение $true.

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

### -Вакеторун
Пробуждает компьютер из спящего состояния сна или гибернации в запланированное время запуска, чтобы он мог выполнить задание.
По умолчанию если компьютер находится в режиме гибернации или сна в запланированное время запуска, задание не выполняется.

Параметр *вакеторун* задает для свойства вакеторун запланированных заданий значение $true.

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

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет
В этот командлет нельзя передать входные данные.

## Выходные данные

### Microsoft. PowerShell. ScheduledJob. Счедуледжобоптионс

## ПРИМЕЧАНИЯ

* Вы можете использовать объект **счедуледжобоптионс** , который создается командлетом **New-scheduledjoboptions** в качестве значения параметра *scheduledjoboptions* для Register-ScheduledJob. Однако параметр *scheduledjoboptions* также может принимать значение хэш-таблицы, определяющее свойства объекта **счедуледжобоптионс** и их значения, такие как:

  `@{ShowInTaskScheduler=$False; RunElevated=$True; IdleDuration="00:05"}`

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
