---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/set-scheduledjoboption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ScheduledJobOption
ms.openlocfilehash: 6647e9ba4e2ee49afa90dd382573d437d2deaee6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227353"
---
# Set-ScheduledJobOption

## Краткий обзор
Изменяет параметры задания для запланированного задания.

## SYNTAX

```
Set-ScheduledJobOption [-InputObject] <ScheduledJobOptions> [-PassThru] [-RunElevated] [-HideInTaskScheduler]
 [-RestartOnIdleResume] [-MultipleInstancePolicy <TaskMultipleInstancePolicy>] [-DoNotAllowDemandStart]
 [-RequireNetwork] [-StopIfGoingOffIdle] [-WakeToRun] [-ContinueIfGoingOnBattery] [-StartIfOnBattery]
 [-IdleTimeout <TimeSpan>] [-IdleDuration <TimeSpan>] [-StartIfIdle] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Set-ScheduledJobOptions** изменяет параметры задания для запланированных заданий.

Чтобы изменить параметры запланированного задания, начните с использования командлета Get-ScheduledJobOption, чтобы получить параметры задания для запланированного задания.
Затем передайте параметры в **Set-ScheduledJobOption** или сохраните их  в переменной и используйте параметр *InputObject* командлета **Set-ScheduledJobOption** для идентификации параметров.
Используйте остальные параметры **Set-ScheduledJobOption** для изменения параметров задания.

Чтобы включить параметр задания, используйте параметр, который задает соответствующий параметр.
Чтобы отключить параметр, введите имя параметра, двоеточие (:) и $False.
Например, чтобы отключить параметр *RunElevated* , введите `-RunElevated:$False` .

Каждый объект параметров задания имеет свойство JobDefinition, содержащее запланированное задание, поэтому при изменении параметров задания связь с запланированным заданием сохраняется.

Параметры запланированного задания определяют, как задание выполняется в случае запуска планировщиком.
Эти параметры не применяются при использовании командлета Start-Job для запуска запланированного задания.

**Set-scheduledjoboptions** — это одна из коллекций командлетов планирования заданий в модуле PSScheduledJob, который входит в состав Windows PowerShell.

Дополнительные сведения о запланированных заданиях см. в разделах описания в модуле PSScheduledJob.
Импортируйте модуль PSScheduledJob, а затем введите `Get-Help about_Scheduled*` или просмотрите статью about_Scheduled_Jobs.

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. изменение параметров задания

```
PS C:\> Get-ScheduledJobOption -Name "DeployPackage"
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
RunWithoutNetwork      : False
DoNotAllowDemandStart  : False
MultipleInstancePolicy : IgnoreNew
JobDefinition          :

The second command uses the **Set-ScheduledJobOpton** cmdlet to change the job options so the values of the WakeToRun and RunWithoutNetwork properties are $True. The command uses the *Passthru* parameter to return the trigger after the change.
PS C:\> Get-ScheduledJobOption -Name "DeployPackage" | Set-ScheduledJobOption -WakeToRun -RequireNetwork:$False -Passthru
StartIfOnBatteries     : False
StopIfGoingOnBatteries : True
WakeToRun              : True
StartIfNotIdle         : True
StopIfGoingOffIdle     : False
RestartOnIdleResume    : False
IdleDuration           : 00:10:00
IdleTimeout            : 01:00:00
ShowInTaskScheduler    : True
RunElevated            : False
RunWithoutNetwork      : True
DoNotAllowDemandStart  : False
MultipleInstancePolicy : IgnoreNewJobDefinition          :
```

В этом примере показано, как изменить параметры запланированного задания на локальном компьютере.

Первая команда использует командлет Get-ScheduledJobOption для получения параметров задания запланированного задания DeployPackage.
Выходные данные показывают, что для свойств Вакеторун и RunElevated задано значение $False.

Эта команда не является обязательной, она включена только для того, чтобы показать эффект изменения параметров.

### Пример 2. изменение параметра для всех удаленных запланированных заданий

```
PS C:\> Invoke-Command -Computer "Server01" -ScriptBlock {Get-ScheduledJob | Get-ScheduledJobOption | Set-ScheduledJobOption -IdleTimeout 2:00:00}
```

Эта команда изменяет значение *IdleTimeout* с 1 часа (значение по умолчанию) на два часа для всех запланированных заданий на компьютере Server01.

Команда использует командлет Invoke-Command для выполнения команды на компьютере Server01.

Удаленная команда начинается с Get-ScheduledJob команды, которая получает все запланированные задания на компьютере.
Запланированные задания передаются в командлет Get-ScheduledJobOption, который получает параметры задания для запланированных заданий.
Каждый объект параметров задания имеет свойство JobDefinition, которое содержит запланированное задание, поэтому объект параметров остается связанным с запланированным заданием даже в случае его изменения.

Триггеры заданий передаются в командлет **Set-scheduledjoboptions** , который изменяет значение параметра *IdleTimeout* на два часа (2:00:00).

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

Даже если задача скрыта, пользователи могут отобразить задачу, выбрав параметр **Показать скрытые задачи** в планировщик задач.

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

Введите объект TimeSpan, например созданный командлетом New-TimeSpan, или введите значение в \<hours\> \<minutes\> формате:: \<seconds\> Format, который автоматически преобразуется в объект **TimeSpan** .

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
Указывает, как долго компьютер должен простаивать перед запуском задания.
Значение по умолчанию — 10 минут.
Если компьютер еще не простаивает заданное время на момент истечения периода **IdleTimeout** , запланированное задание не выполняется до следующего запланированного времени, если такое имеется.

Введите объект TimeSpan, например созданный командлетом New-TimeSpan, или введите значение в \<hours\> \<minutes\> формате:: \<seconds\> Format, который автоматически преобразуется в объект **TimeSpan** .

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

### -InputObject
Указывает параметры задания.
Введите переменную, содержащую объекты **счедуледжобоптионс** , или введите команду или выражение, которое получает объекты **счедуледжобоптионс** , такие как команда Get-ScheduledJobOption.
Можно также передать объект **счедуледжобоптионс** в командлет **Set-scheduledjoboptions** .

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Мултиплеинстанцеполици
Определяет, как система реагирует на запрос о запуске экземпляра запланированного задания во время выполнения другого экземпляра этого задания.
Допустимые значения для этого параметра:

- Игноренев.
Новый экземпляр задания игнорируется.
Это значение по умолчанию.
- Параллельный.
Новый экземпляр задания запускается немедленно.
- Очередь.
Новый экземпляр задания запускается сразу после завершения текущего экземпляра.
- Стопексистинг.
Текущий экземпляр задания останавливается, и запускается новый экземпляр.

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

Параметр **RunElevated** задает значение true для свойства **RunElevated** запланированных заданий.

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
Запускает запланированное задание, если до истечения времени, заданного параметром **IdleDuration** , компьютер уже простаивал на протяжении заданного параметром *IdleTimeout* периода.

По умолчанию параметры *IdleDuration* и *IdleTimeout* игнорируются, и задание запускается в запланированное время, даже если компьютер занят.

Если указать этот параметр и в запланированное время запуска задания компьютер будет занят (не будет простаивать), задание не запускается до следующего запланированного времени запуска, если такое имеется.

Параметр *стартифидле* задает для свойства **стартифнотидле** запланированных заданий значение false.

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
Значение по умолчанию равно False.

Параметр *стартифонбаттери* задает для свойства **стартифонбаттериес** запланированных заданий значение $true.

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

### Microsoft. PowerShell. ScheduledJob. Счедуледжобоптионс
Объект параметров запланированного задания можно передать в **Set-ScheduledJobOption** .

## Выходные данные

### Нет или Microsoft. PowerShell. ScheduledJob. Счедуледжобоптионс
При использовании параметра *Passthru* командлет **Set-ScheduledJobOption** возвращает параметры задания, которые были изменены.
В противном случае командлет не формирует никаких выходных данных.

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
