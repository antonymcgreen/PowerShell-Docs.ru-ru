---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/set-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ScheduledJob
ms.openlocfilehash: 6144d9f19b86727bc09d07e94f4bcf158e3b7071
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94387912"
---
# Set-ScheduledJob

## Краткий обзор
Изменяет запланированные задания.

## SYNTAX

### ScriptBlock (по умолчанию)

```
Set-ScheduledJob [-Name <String>] [-ScriptBlock <ScriptBlock>] [-Trigger <ScheduledJobTrigger[]>]
 [-InitializationScript <ScriptBlock>] [-RunAs32] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-ScheduledJobOption <ScheduledJobOptions>]
 [-InputObject] <ScheduledJobDefinition> [-MaxResultCount <Int32>] [-PassThru] [-ArgumentList <Object[]>]
 [-RunNow] [-RunEvery <TimeSpan>] [<CommonParameters>]
```

### FilePath

```
Set-ScheduledJob [-Name <String>] [-FilePath <String>] [-Trigger <ScheduledJobTrigger[]>]
 [-InitializationScript <ScriptBlock>] [-RunAs32] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-ScheduledJobOption <ScheduledJobOptions>]
 [-InputObject] <ScheduledJobDefinition> [-MaxResultCount <Int32>] [-PassThru] [-ArgumentList <Object[]>]
 [-RunNow] [-RunEvery <TimeSpan>] [<CommonParameters>]
```

### Выполнение

```
Set-ScheduledJob [-InputObject] <ScheduledJobDefinition> [-ClearExecutionHistory] [-PassThru]
 [<CommonParameters>]
```

## DESCRIPTION
Командлет **Set-ScheduledJob** изменяет свойства запланированных заданий, например, команды, которые выполняют задания, или учетные данные, необходимые для выполнения задания.
Его также можно использовать для очистки журнала выполнения запланированного задания.

Чтобы использовать этот командлет, начните с использования командлета Get-ScheduledJob для получения запланированного задания.
Затем передавайте по конвейеру запланированное задание в командлет **Set-ScheduledJob** или сохраните задание в переменной и используйте параметр *InputObject* , чтобы определить задание.
Используйте остальные параметры **Set-ScheduledJob** для изменения свойств задания или очистки журнала выполнения.

Несмотря на то, что командлет **Set-ScheduledJob** можно использовать для изменения триггеров и параметров запланированного задания, команды Add-JobTrigger, Set-JobTrigger и Set-ScheduledJobOption предоставляют гораздо более простые способы выполнения этих задач.
Чтобы создать новое запланированное задание, используйте командлет Register-ScheduledJob.

Параметр *Trigger* командлета **Set-ScheduledJob** добавляет один или несколько триггеров задания, которые запускают задание.
Параметр *Trigger* является необязательным, поэтому можно добавлять триггеры при создании запланированного задания, добавлять Триггеры заданий позже, добавлять параметр *RunNow* для немедленного запуска задания, использовать командлет Start-Job для немедленного запуска задания в любое время или сохранить неактивированное запланированное задание в качестве шаблона для других заданий.

**Set-ScheduledJob** — это одна из коллекций командлетов планирования заданий в модуле PSScheduledJob, который входит в состав Windows PowerShell.

Дополнительные сведения о запланированных заданиях см. в разделах описания в модуле PSScheduledJob.
Импортируйте модуль PSScheduledJob, а затем введите `Get-Help about_Scheduled*` или просмотрите статью about_Scheduled_Jobs.

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. изменение скрипта, выполняемого заданием

```
PS C:\> Get-ScheduledJob -Name "Inventory"
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          Inventory       {1}             C:\Scripts\Get-Inventory.ps1             True

The second command uses the Get-ScheduledJob cmdlet to get the Inventory scheduled job. A pipeline operator (|) sends the scheduled job to the **Set-ScheduledJob** cmdlet. The **Set-ScheduledJob** cmdlet uses the *Script* parameter to specify a new script, Get-FullInventory.ps1. The command uses the *Passthru* parameter to return the scheduled job after the change.
PS C:\> Get-ScheduledJob -Name "Inventory" | Set-ScheduledJob -FilePath "C:\Scripts\Get-FullInventory.ps1" -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          Inventory       {1}             C:\Scripts\Get-FullInventory.ps1         True
```

В этом примере показано, как изменить сценарий, который выполняется в запланированном задании.

Первая команда использует командлет Get-ScheduledJob для получения запланированного задания инвентаризации.
Выходные данные показывают, что задание выполняет сценарий Get-Inventory.ps1.

Эта команда не является обязательной, она включена только для того, чтобы показать эффект изменения сценария.

### Пример 2. Удаление журнала выполнения запланированного задания

```
PS C:\> Get-ScheduledJob BackupArchive | Set-ScheduledJob -ClearExecutionHistory
```

Эта команда удаляет текущий журнал выполнения и сохраненные результаты задания для запланированного задания BackupArchive.

Команда использует командлет Get-ScheduledJob для получения запланированного задания запланированного backuparchive.
Конвейерный оператор (|) отправляет задание в командлет **Set-ScheduledJob** , который изменяет его.
Командлет **Set-ScheduledJob** использует параметр *клеарексекутионхистори* для удаления журнала выполнения и сохраненных результатов.

Дополнительные сведения о журнале выполнения и сохраненных результатах задания для запланированных заданий см. в описании about_Scheduled_Jobs.

### Пример 3. изменение запланированных заданий на удаленном компьютере

```
PS C:\> Invoke-Command -Computer "Server01, Server02" -ScriptBlock {Get-ScheduledJob | Set-ScheduledJob -InitializationScript \\SrvA\Scripts\SetForRun.ps1}
```

Эта команда изменяет сценарий инициализации во всех запланированных заданиях на компьютерах Server01 и Server02.

Команда использует командлет Invoke-Command для выполнения команды на компьютерах Server01 и Server02.

Удаленная команда начинается с Get-ScheduledJob команды, которая получает все запланированные задания на компьютере.
Запланированные задания передаются в командлет **Set-ScheduledJob** , который изменяет скрипт инициализации на SetForRun.ps1.

## PARAMETERS

### -ArgumentList
Указывает значения для параметров сценария, который определяется параметром *FilePath* , или для команды, которая определяется параметром *ScriptBlock*.

```yaml
Type: System.Object[]
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Authentication
Задает механизм, используемый при проверке подлинности учетных данных пользователя.
Допустимые значения для этого параметра:

- По умолчанию
- Basic
- CredSSP
- Digest (дайджест)
- Kerberos
- Согласование
- NegotiateWithImplicitCredential

Значение по умолчанию — Default. Дополнительные сведения о значениях этого параметра см. в разделе [перечисление AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism) в пакете SDK для PowerShell.

Внимание! Аутентификация CredSSP, в рамках которой учетные данные пользователя передаются на удаленный компьютер для проверки, предназначена для команд, требующих аутентификацию нескольких ресурсов, например для доступа к удаленной сетевой папке.
Этот механизм повышает риск безопасности удаленной операции.
Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ScriptBlock, FilePath
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Клеарексекутионхистори
Удаляет текущий журнал выполнения и сохраненные результаты запланированного задания.

Журнал выполнения заданий и результаты задания сохраняются вместе с запланированным заданием в каталоге $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs на компьютере, где это задание создано.
Чтобы просмотреть журнал выполнения, используйте командлет Get-Job.
Чтобы получить результаты задания, используйте командлет Receive-Job.

Этот параметр не влияет на события, которые планировщик записывает в журналы событий Windows, и не запрещает Windows PowerShell сохранять результаты заданий.
Чтобы управлять объемом сохраняемых результатов заданий, используйте параметр *MaxResultCount*.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Execution
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Указывает учетную запись пользователя, обладающую разрешением для выполнения запланированного задания.
По умолчанию используется текущий пользователь.

Введите имя пользователя, например User01 или Domain01\User01, или введите объект **PSCredential** , например один из командлета Get-Credential.
Если ввести только имя пользователя, появится приглашение ввести пароль.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath
Указывает сценарий, запускаемый запланированным заданием.
Введите путь к PS1-файлу на локальном компьютере.
Чтобы задать значения по умолчанию для параметров сценария, используйте параметр *ArgumentList*.
Каждое запланированное задание должно иметь либо значение *ScriptBlock* , либо значение *FilePath*.

```yaml
Type: System.String
Parameter Sets: FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Инитиализатионскрипт
Указывает полный путь к сценарию Windows PowerShell (PS1).
Сценарий инициализации выполняется в сеансе, который создается для фонового задания перед командами, которые задаются параметром *ScriptBlock* , или сценарием, который задается параметром *FilePath*.
Сценарий инициализации можно использовать для настройки сеанса, например, для добавления файлов, функций или псевдонимов, создания каталогов или проверки наличия необходимых компонентов.

Чтобы задать сценарий, который выполняет команды основного задания, используйте параметр *FilePath*.

Если скрипт инициализации создает ошибку, включая устранимую ошибку, текущий экземпляр запланированного задания не выполняется и его состояние — Failed.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Задает изменяемое запланированное задание.
Введите переменную, содержащую объекты **ScheduledJobDefinition** , или введите команду или выражение, которое получает объекты **ScheduledJobDefinition** , такие как команда Get-ScheduledJob.
Можно также передать объект **ScheduledJobDefinition** в командлет **Set-ScheduledJob**.

При указании нескольких запланированных заданий **Set-ScheduledJob** вносит одинаковые изменения во все задания.

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Максресулткаунт
Указывает, сколько записей результатов задания хранится для запланированного задания.
Значение по умолчанию: 32.

Windows PowerShell сохраняет журнал выполнения и результаты каждого активированного экземпляра запланированного задания на диске.
Значение этого параметра определяет количество результатов экземпляра задания, сохраняемых для данного запланированного задания.
Когда число результатов экземпляра задания превышает это значение, Windows PowerShell удаляет результаты самого старого экземпляра задания, чтобы освободить место для результатов более нового экземпляра задания.

Журнал выполнения задания и результаты задания сохраняются в \\ \<JobName\> каталогах $Home \аппдата\локал\микрософт\виндовс\повершелл\счедуледжобс \аутпут \\ \<Timestamp\> на компьютере, где создается задание.
Чтобы просмотреть журнал выполнения, используйте командлет Get-Job.
Чтобы получить результаты задания, используйте командлет Receive-Job.

Параметр *MaxResultCount* задает значение свойства ExecutionHistoryLength для запланированного задания.

Чтобы удалить текущие результаты задания и журнал выполнения, используйте параметр *ClearExecutionHistory*.

```yaml
Type: System.Int32
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Указывает новое имя для запланированного задания и его экземпляров.
Это имя должно быть уникальным на локальном компьютере.

Чтобы определить запланированное задание, которое необходимо изменить, используйте параметр *InputObject* или передайте запланированное задание по конвейеру из Get-ScheduledJob в командлет **Set-ScheduledJob**.

Этот параметр не изменяет имена экземпляров задания на диске.
Он затрагивает только те экземпляры задания, которые запускаются после выполнения этой команды.

```yaml
Type: System.String
Parameter Sets: ScriptBlock, FilePath
Aliases:

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

### -RunAs32
Запускает запланированное задание в 32-разрядном процессе.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Руневери

Используется для указания периодичности выполнения задания. Например, этот параметр используется для запуска задания каждые 15 минут.

```yaml
Type: System.TimeSpan
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunNow
Запускает задание немедленно, как только выполняется командлет **Set-ScheduledJob** .
Этот параметр устраняет необходимость запуска планировщика заданий для выполнения сценария Windows PowerShell сразу после регистрации и не требует от пользователей создания триггера, который указывает начальную дату и время.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scheduledjoboptions
Задает параметры для запланированного задания.
Введите объект **счедуледжобоптионс** , например, созданный с помощью командлета New-ScheduledJobOption, или значение хэш-таблицы.

Вы можете задать параметры для запланированного задания при регистрации запланированного задания или с помощью командлетов Set-ScheduledJobOption или **Set-ScheduledJob** , чтобы задать или изменить параметры.

Многие параметры и их значения по умолчанию определяют, запускается ли запланированное задание и когда это происходит.
Обязательно просмотрите эти параметры перед планированием задания.
Описание параметров запланированного задания, включая значения по умолчанию, см. в разделе New-Scheduledjoboptions.

Чтобы отправить хэш-таблицу, используйте следующие ключи.
Ключи в следующей хэш-таблице ключи приведены со значениями по умолчанию.

`@{# Power SettingsStartIfOnBattery=$False;StopIfGoingOnBattery=$True; WakeToRun=$False; # Idle SettingsStartIfNotIdle=$False; IdleDuration="00:10:00"; IdleTimeout="01:00:00"; StopIfGoingOffIdle=$True; RestartOnIdleResume=$False;# Security settingsShowInTaskScheduler=$TrueRunElevated=$False;# MiscRunWithoutNetwork=$False;DoNotAllowDemandStart=$False;MultipleInstancePolicy=IgnoreNew# Can be IgnoreNew, Parallel, Queue, StopExisting}`

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptBlock
Указывает команды, выполняемые запланированным заданием.
Чтобы создать блок скрипта, заключите команды в скобки ( { } ).
Чтобы задать значения по умолчанию для параметров команды, используйте параметр *ArgumentList*.

Каждая команда Register-ScheduledJob должна использовать либо параметр *ScriptBlock* , либо параметр *FilePath*.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Триггер
Задает триггеры для запланированного задания.
Введите один или несколько объектов **ScheduledJobTrigger** , например объекты, возвращаемые командлетом New-JobTrigger, или хэш-таблицу ключей и значений триггера задания.

Триггер задания запускает запланированное задание автоматически при однократном или повторяющемся расписании или при возникновении события.

Триггеры задания не являются обязательными.
Вы можете добавить триггер при создании запланированного задания, использовать командлеты Add-JobTrigger или **Set-ScheduledJob** , чтобы добавить триггеры позже, или использовать командлет Start-Job для немедленного запуска запланированного задания.
Можно также создать и поддерживать запланированное задание, которое не имеет триггеров задания.

Чтобы отправить хэш-таблицу, используйте следующие ключи.

`@{Frequency="Once" (or Daily, Weekly, AtStartup, AtLogon);At="3am"` (или любая допустимая строка времени); `DaysOfWeek="Monday", "Wednesday"` (или любое сочетание названий дней); `Interval=2` (или любой допустимый интервал частоты); `RandomDelay="30minutes"` (или любая допустимая строка TimeSpan); `User="Domain1\User01"` (или любой допустимый пользователь; используется только со значением частоты AtLogon)

}

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: ScriptBlock, FilePath
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
Можно передать запланированные задания в **Set-ScheduledJob**.

## Выходные данные

### Нет или Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
При использовании параметра *Passthru* командлет **Set-ScheduledJob** возвращает запланированное задание, которое было изменено.
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
