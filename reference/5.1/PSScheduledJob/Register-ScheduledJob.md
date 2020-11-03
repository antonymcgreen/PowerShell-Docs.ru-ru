---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/register-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-ScheduledJob
ms.openlocfilehash: 89887474142490a71d372577576fb0059b4ff12e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227373"
---
# Register-ScheduledJob

## Краткий обзор
Создает запланированное задание.

## SYNTAX

### ScriptBlock (по умолчанию)

```
Register-ScheduledJob [-ScriptBlock] <ScriptBlock> [-Name] <String>
 [-Trigger <ScheduledJobTrigger[]>] [-InitializationScript <ScriptBlock>] [-RunAs32]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-ScheduledJobOption <ScheduledJobOptions>] [-ArgumentList <Object[]>] [-MaxResultCount <Int32>]
 [-RunNow] [-RunEvery <TimeSpan>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FilePath

```
Register-ScheduledJob [-FilePath] <String> [-Name] <String> [-Trigger <ScheduledJobTrigger[]>]
 [-InitializationScript <ScriptBlock>] [-RunAs32] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-ScheduledJobOption <ScheduledJobOptions>]
 [-ArgumentList <Object[]>] [-MaxResultCount <Int32>] [-RunNow] [-RunEvery <TimeSpan>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Register-ScheduledJob`Командлет создает запланированные задания на локальном компьютере.

Запланированное задание — это фоновое задание Windows PowerShell, которое можно запустить автоматически при однократном или повторяющемся расписании. Запланированные задания хранятся на диске и регистрируются в планировщик задач.
Заданиями можно управлять в планировщик задач или с помощью командлетов запланированных заданий в Windows PowerShell.

При запуске запланированного задания создается экземпляр запланированного задания. Экземпляры запланированного задания идентичны фоновым заданиям Windows PowerShell, за исключением того, что результаты сохраняются на диске. Используйте командлеты задания, такие как `Start-Job` , `Get-Job` и, `Receive-Job` чтобы запустить, просмотреть и получить результаты экземпляров задания.

Используйте `Register-ScheduledJob` для создания нового запланированного задания. Чтобы указать команды, выполняемые запланированным заданием, используйте параметр **ScriptBlock** . Чтобы указать скрипт, выполняемый заданием, используйте параметр **FilePath** .

Windows PowerShell — запланированные задания используют те же Триггеры заданий и параметры задания, которые планировщик задач используют для запланированных задач.

Параметр **триггера** `Register-ScheduledJob` добавляет один или несколько триггеров задания, которые запускают задание. Параметр **Trigger** является необязательным, поэтому можно добавлять триггеры при создании запланированного задания, добавлять Триггеры заданий позже, добавлять параметр **RunNow** для немедленного запуска задания, использовать `Start-Job` командлет для немедленного запуска задания в любое время или сохранить неактивированное запланированное задание в качестве шаблона для других заданий.

Параметр **Options** позволяет настраивать параметры для запланированного задания. Параметр **Options** является необязательным, поэтому можно задать параметры задания при создании запланированного задания или изменить их в любое время. Поскольку значения параметров задания могут запрещать выполнение запланированного задания, проверьте параметры задания и внимательно настройте их.

`Register-ScheduledJob` является одной из коллекций командлетов планирования заданий в модуле **PSScheduledJob** , который входит в состав Windows PowerShell.

Дополнительные сведения о запланированных заданиях см. в разделе о статьях в модуле **PSScheduledJob** .
Импортируйте модуль **PSScheduledJob** и введите: `Get-Help about_Scheduled*` или см. [about_Scheduled_Jobs](./about/about_scheduled_jobs.md).

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. Создание запланированного задания

В этом примере создается запланированное задание на локальном компьютере.

```powershell
Register-ScheduledJob -Name "Archive-Scripts" -ScriptBlock {
  Get-ChildItem $home\*.ps1 -Recurse |
    Copy-Item -Destination "\\Server\Share\PSScriptArchive"
}
```

`Register-ScheduledJob` использует параметр **Name** для создания запланированного задания **Archive-Scripts** .
Запускается параметр **ScriptBlock** `Get-ChildItem` , который рекурсивно ищет `$home` файлы в каталоге `.ps1` . `Copy-Item`Командлет копирует файлы в каталог, указанный параметром **Destination** .

Так как запланированное задание не содержит триггер, оно не запускается автоматически. Можно добавить триггеры заданий с помощью `Add-JobTrigger` `Start-Job` командлета, чтобы запустить задание по требованию, или использовать запланированное задание в качестве шаблона для других запланированных заданий.

### Пример 2. Создание запланированного задания с триггерами и настраиваемыми параметрами

В этом примере показано, как создать запланированное задание, имеющее триггер задания и пользовательские параметры задания.

```powershell
$O = New-ScheduledJobOption -WakeToRun -StartIfIdle -MultipleInstancePolicy Queue
$T = New-JobTrigger -Weekly -At "9:00 PM" -DaysOfWeek Monday -WeeksInterval 2
$path = "\\Srv01\Scripts\UpdateVersion.ps1"
Register-ScheduledJob -Name "UpdateVersion" -FilePath $path -ScheduledJobOption $O -Trigger $T
```

`$O`Переменная хранит объект параметра задания, `New-ScheduledJobOption` созданный командлетом. Эти параметры запускают запланированное задание, даже если компьютер не находится в режиме простоя, пробуждает компьютер для запуска задания, если это необходимо, и позволяет выполнять несколько экземпляров задания в ряде.

`$T`Переменная сохраняет результат `New-JobTrigger` командлета для создания триггера задания, который запускает задание каждый второй понедельник в 9:00 PM.

`$path`Переменная хранит путь к `UpdateVersion.ps1` файлу скрипта.

`Register-ScheduledJob` использует параметр **Name** для создания запланированного задания **упдатеверсион** .
Параметр **FilePath** используется `$path` для указания скрипта, выполняемого заданием. Параметр **scheduledjoboptions** использует параметры задания, хранящиеся в `$O` . Параметр **Trigger** использует Триггеры заданий, хранимые в `$T` .

### Пример 3. Использование хэш-таблиц для задания параметров триггера и запланированного задания

Этот пример действует так же, как и команда в примере 2. Он создает запланированное задание, используя хэш-таблицы для указания значений параметров **Trigger** и **scheduledjoboptions** . `$O`Переменные и, `$T` определенные в примере 2, заменяются хэш-таблицами.

```powershell
$T = @{
  Frequency="Weekly"
  At="9:00PM"
  DaysOfWeek="Monday"
  Interval=2
}
$O = @{
  WakeToRun=$true
  StartIfNotIdle=$false
  MultipleInstancePolicy="Queue"
}
Register-ScheduledJob -Trigger $T -ScheduledJobOption $O -Name UpdateVersion -FilePath "\\Srv01\Scripts\Update-Version.ps1"
```

### Пример 4. создание запланированных заданий на удаленных компьютерах

В этом примере запланированное задание **енергидата** создается на нескольких удаленных компьютерах. Запланированное задание запускает сценарий, собирающий необработанные данные и сохраняющий их в запущенном журнале на удаленном компьютере.

```powershell
$Cred = Get-Credential
$O = New-ScheduledJobOption -WakeToRun -StartIfIdle -MultipleInstancePolicy Queue
$T = New-JobTrigger -Weekly -At "9:00 PM" -DaysOfWeek Monday -WeeksInterval 2
Invoke-Command -ComputerName (Get-Content Servers.txt) -Credential $Cred -ScriptBlock {
  $params = @{
      Name = "Get-EnergyData"
      FilePath = "\\Srv01\Scripts\Get-EnergyData.ps1"
      ScheduledJobOption = $using:O
      Trigger = $using:T
  }
  Register-ScheduledJob @params
}
```

`$Cred`Переменная сохраняет учетные данные в объекте **PSCredential** для пользователя с разрешениями на создание запланированных заданий. `$O`Переменная хранит параметры задания, созданные с помощью `New-ScheduledJobOption` . `$T`Переменная хранит Триггеры заданий, созданные с помощью `New-JobTrigger` .

`Invoke-Command`Командлет использует параметр **ComputerName** для получения списка имен серверов из `Servers.txt` файла. Параметр **Credential** получает объект учетных данных, хранящийся в `$Cred` .
Параметр **ScriptBlock** выполняет `Register-ScheduledJob` команду на компьютерах в `Servers.txt` файле.

Параметры для определяются `Register-ScheduledJob` параметром `$params` . Параметры **Name** указывают, что задание называется **Get-енергидата** на каждом удаленном компьютере. **FilePath** задает расположение `EnergyData.ps1` скрипта. Сценарий находится на файловом сервере, доступном всем участвующим компьютерам. Задание выполняется по расписанию, заданному триггерами заданий в `$T` , а также в параметрах задания в `$O` .

`Register-ScheduledJob @params`Команда создает запланированное задание с параметрами из блока script.

### Пример 5. Создание запланированного задания, запускающего сценарий на удаленных компьютерах

В этом примере создается запланированное задание **коллектенергидата** на локальном компьютере. Задание выполняется на нескольких удаленных компьютерах.

```powershell
$Admin = Get-Credential
$T = New-JobTrigger -Weekly -At "9:00 PM" -DaysOfWeek Monday -WeeksInterval 2
Register-ScheduledJob -Name "CollectEnergyData" -Trigger $T -MaxResultCount 99 -ScriptBlock {
  $params = @{
    AsJob = $true
    ComputerName = (Get-Content Servers.txt)
    FilePath = '\\Srv01\Scripts\Get-EnergyData.ps1'
    Credential = $using:Admin
    Authentication = 'CredSSP'
  }
  Invoke-Command @params
}
```

`$Admin`Переменная хранит учетные данные пользователя с разрешениями на выполнение команд в объекте **PSCredential** . `$T`Переменная хранит Триггеры заданий, созданные с помощью `New-JobTrigger` .

`Register-ScheduledJob`Командлет использует параметр **Name** для создания запланированного задания **коллектенергидата** на локальном компьютере. Параметр **Trigger** указывает триггеры задания в `$T` , а параметр **максресулткаунт** увеличивает число сохраненных результатов до 99.

Параметр **ScriptBlock** определяет `Invoke-Command` параметры с помощью `$params` . Параметр **AsJob** создает объект фонового задания на локальном компьютере, даже если `Energydata.ps1` сценарий выполняется на удаленных компьютерах. Параметр **ComputerName** возвращает список имен серверов из `Servers.txt` файла. Параметр **Credential** указывает учетную запись пользователя, имеющую разрешение на выполнение скриптов на удаленных компьютерах. И параметр **authentication** задает значение **CredSSP** , разрешающее делегированные учетные данные.

`Invoke-Command @params`Запускает команду с параметрами из блока скрипта.

## PARAMETERS

### -ArgumentList

Указывает значения для параметров сценария, который определяется параметром **FilePath** , или для команды, которая определяется параметром **ScriptBlock** .

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Authentication

Задает механизм, используемый при проверке подлинности учетных данных пользователя. Значение по умолчанию — Default.

Допустимые значения для этого параметра:

- По умолчанию
- Базовый
- CredSSP
- Digest (дайджест)
- Kerberos
- Согласование
- NegotiateWithImplicitCredential

Дополнительные сведения о значениях этого параметра см. в разделе [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

> [!CAUTION]
> Проверка подлинности CredSSP, при применении которой учетные данные пользователя передаются на удаленный компьютер, предназначена для команд, требующих проверки подлинности для нескольких ресурсов, например для доступа к удаленной сетевой папке. Этот механизм повышает риск безопасности удаленной операции. Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

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

### -Credential

Указывает учетную запись пользователя, обладающую разрешением для выполнения запланированного задания. По умолчанию используется текущий пользователь.

Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , например один из `Get-Credential` командлетов. Если ввести только имя пользователя, появится запрос на ввод пароля.

Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

Указывает сценарий, запускаемый запланированным заданием. Введите путь к `.ps1` файлу на локальном компьютере. Чтобы задать значения по умолчанию для параметров сценария, используйте параметр **ArgumentList** .
Каждая `Register-ScheduledJob` команда должна использовать либо параметры **ScriptBlock** , либо **FilePath** .

```yaml
Type: System.String
Parameter Sets: FilePath
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Инитиализатионскрипт

Указывает полный путь к сценарию Windows PowerShell ( `.ps1` ). Сценарий инициализации выполняется в сеансе, который создается для фонового задания перед командами, которые задаются параметром **ScriptBlock** , или сценарием, который задается параметром **FilePath** . Сценарий инициализации можно использовать для настройки сеанса, например, для добавления файлов, функций или псевдонимов, создания каталогов или проверки наличия необходимых компонентов.

Чтобы задать сценарий, который выполняет команды основного задания, используйте параметр **FilePath** .

Если скрипт инициализации создает ошибку, даже устранимую ошибку, текущий экземпляр запланированного задания не выполняется и его состояние — **Failed** .

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Максресулткаунт

Указывает, сколько записей результатов задания хранится для запланированного задания. Значение по умолчанию: 32.

Windows PowerShell сохраняет журнал выполнения и результаты каждого активированного экземпляра запланированного задания на диске. Значение этого параметра определяет количество результатов экземпляра задания, сохраняемых для данного запланированного задания. Когда число результатов экземпляра задания превышает это значение, Windows PowerShell удаляет результаты самого старого экземпляра задания, чтобы освободить место для результатов более нового экземпляра задания.

Журнал выполнения задания и результаты задания сохраняются в `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs\<JobName>\Output\<Timestamp>`
каталоги на компьютере, на котором создается задание. Чтобы просмотреть журнал выполнения, используйте `Get-Job` командлет. Чтобы получить результаты задания, используйте `Receive-Job` командлет.

Параметр **MaxResultCount** задает значение свойства ExecutionHistoryLength для запланированного задания.

Чтобы удалить текущий журнал выполнения и результаты задания, используйте параметр **клеарексекутионхистори** `Set-ScheduledJob` командлета.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Задает имя для запланированного задания. Данное имя также используется для всех запущенных экземпляров этого запланированного задания. Это имя должно быть уникальным на компьютере. Этот параметр обязателен.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAs32

Запускает запланированное задание в 32-разрядном процессе.

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

### -Руневери

Используется для указания периодичности выполнения задания. Например, этот параметр используется для запуска задания каждые 15 минут.

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

### -RunNow

Запускает задание немедленно, как только `Register-ScheduledJob` запускается командлет. Этот параметр устраняет необходимость в активации планировщик задач для запуска сценария Windows PowerShell сразу после регистрации и не требует от пользователей создания триггера, указывающего дату и время начала.

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

### -Scheduledjoboptions

Задает параметры для запланированного задания. Введите объект **счедуледжобоптионс** , например, созданный с помощью `New-ScheduledJobOption` командлета, или значение хэш-таблицы.

Параметры запланированного задания можно задать при регистрации задания по расписанию или с помощью `Set-ScheduledJobOption` `Set-ScheduledJob` командлетов или для изменения параметров.

Многие параметры и их значения по умолчанию определяют, запускается ли запланированное задание и когда это происходит. Обязательно просмотрите эти параметры перед планированием задания. Описание параметров запланированного задания, включая значения по умолчанию, см. в разделе `New-ScheduledJobOption` .

Чтобы отправить хэш-таблицу, используйте следующие ключи. Ключи в следующей хэш-таблице ключи приведены со значениями по умолчанию.

`@{StartIfOnBattery=$False; StopIfGoingOnBattery=$True; WakeToRun=$False; StartIfNotIdle=$False; IdleDuration="00:10:00"; IdleTimeout="01:00:00"; StopIfGoingOffIdle=$True; RestartOnIdleResume=$False; ShowInTaskScheduler=$True; RunElevated=$False; RunWithoutNetwork=$False; DoNotAllowDemandStart=$False; MultipleInstancePolicy="IgnoreNew"}`

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptBlock

Указывает команды, выполняемые запланированным заданием. Чтобы создать блок скрипта, заключите команды в фигурные скобки ( `{}` ). Чтобы задать значения по умолчанию для параметров команды, используйте параметр **ArgumentList** .

Каждая `Register-ScheduledJob` команда должна использовать либо параметры **ScriptBlock** , либо **FilePath** .

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Триггер

Задает триггеры для запланированного задания. Введите один или несколько объектов **ScheduledJobTrigger** , например объекты, `New-JobTrigger` возвращаемые командлетом, или хэш-таблицу ключей и значений триггера задания.

Триггер задания запускает задание по расписанию. Триггер может указывать однократное или регулярное расписание или событие, например вход пользователя в систему или запуск Windows.

Параметр **Trigger** не является обязательным. Вы можете добавить триггер при создании запланированного задания, использовать `Add-JobTrigger` `Set-JobTrigger` командлеты, или, `Set-ScheduledJob` чтобы добавить или изменить триггеры заданий позже, или использовать `Start-Job` командлет для немедленного запуска запланированного задания. Можно также создать и поддерживать запланированное задание без триггера, используемое в качестве шаблона.

Чтобы отправить хэш-таблицу, используйте следующие ключи:

- **Частота** : ежедневно, еженедельно, AtStartup, AtLogon
- **At** : любая допустимая строка времени
- **DaysOfWeek** — любое сочетание названий дней
- **Interval** — любой допустимый интервал частоты
- **Рандомделай** : любая допустимая строка TimeSpan
- **Пользователь** : любой допустимый пользователь. Используется только с значением частоты AtLogon

Пример:

`@{Frequency="Once"; At="3am"; DaysOfWeek="Monday", "Wednesday"; Interval=2; RandomDelay="30minutes"; User="Domain1\User01"}`

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Показывает, что произойдет при запуске командлета. Командлет не выполняется.

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

### Нет

Вы не можете отправить входные данные по конвейеру в этот командлет.

## Выходные данные

### Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition

## ПРИМЕЧАНИЯ

Каждое запланированное задание сохраняется в подкаталоге `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` каталога на локальном компьютере.
Подкаталог имеет имя для запланированного задания и содержит XML-файл для запланированного задания и записи его журнала выполнения. Дополнительные сведения о запланированных заданиях на диске см. в разделе [about_Scheduled_Jobs_Advanced](./about/about_scheduled_jobs_advanced.md).

Запланированные задания, создаваемые в Windows PowerShell, отображаются в планировщик задач в `Library\Microsoft\Windows\PowerShell\ScheduledJobs` папке планировщик задач. Планировщик заданий можно использовать для просмотра и изменения запланированного задания.

Для управления запланированными заданиями, созданными с помощью командлетов запланированных заданий, можно использовать планировщик задач, средство командной строки **schtasks.exe** и командлеты планировщик задач. Однако нельзя использовать командлеты запланированных заданий для управления задачами, созданными в планировщик задач.

При сбое команды запланированного задания Windows PowerShell возвращает сообщение об ошибке. Однако если задание завершается сбоем, когда планировщик задач пытается его запустить, то эта ошибка недоступна для Windows PowerShell.

Если запланированное задание не выполняется, используйте следующие методы, чтобы найти причину:

- Убедитесь, что триггер задания задан правильно.
  - Убедитесь, что условия, заданные в параметрах задания, удовлетворены.
- Убедитесь, что учетная запись пользователя, под которой выполняется задание, имеет разрешение на выполнение команд или скриптов в задании.
- Проверьте журнал планировщик задач на наличие ошибок.
- Проверьте журнал событий планировщик задач на наличие ошибок.

Дополнительные сведения см. в разделе [about_Scheduled_Jobs_Troubleshooting](./about/about_scheduled_jobs_troubleshooting.md).

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
