---
description: Описывает запланированные задания и объясняет, как использовать запланированные задания и управлять ими в PowerShell и в планировщик задач.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/about/about_scheduled_jobs?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scheduled_Jobs
ms.openlocfilehash: 4d4e86957a584bb4deb47cadcd8588c1236455ac
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231634"
---
# <a name="about-scheduled-jobs"></a>О запланированных заданиях

## <a name="short-description"></a>Краткое описание

Описывает запланированные задания и объясняет, как использовать запланированные задания и управлять ими в PowerShell и в планировщик задач.

## <a name="long-description"></a>Подробное описание

Запланированные задания PowerShell — это полезная гибрид фоновых заданий PowerShell и планировщик задач задач.

Как и фоновые задания PowerShell, запланированные задания выполняются асинхронно в фоновом режиме. Экземпляры выполняемых запланированных заданий можно управлять с помощью командлетов задания, таких как,, `Start-Job` `Get-Job` `Stop-Job` и `Receive-Job` .

Как и планировщик задач задачи, запланированные задания сохраняются на диск. Вы можете просматривать задания и управлять ими в планировщик задач, включать и отключать их по мере необходимости, запускать их или использовать в качестве шаблонов, устанавливать однократные или повторяющиеся расписания для запуска заданий или задавать условия, при которых задания запускаются.

Кроме того, результаты выполнения экземпляров запланированных заданий сохраняются на диске в удобном для использования формате, предоставляя выполнение журнала выходных данных задания. Запланированные задания поставляются с настроенным набором командлетов для управления ими. Командлеты позволяют создавать, изменять, управлять, отключать и повторно включать запланированные задания, триггеры заданий и параметры задания.

Этот всеобъемлющий и гибкий набор средств делает запланированные задания ключевым компонентом многих профессиональных ИТ-решений PowerShell.

Командлеты запланированных заданий входят в модуль **PSScheduledJob** , который устанавливается вместе с PowerShell. Этот модуль появился в PowerShell 3,0 и работает в PowerShell 3,0 и более поздних версиях PowerShell. Дополнительные сведения о командлетах, содержащихся в модуле **PSScheduledJob** , см. в разделе [PSScheduledJob](xref:PSScheduledJob).

Дополнительные сведения о фоновых заданиях PowerShell см. в разделе [about_Jobs](../../Microsoft.PowerShell.Core/About/about_Jobs.md).

Дополнительные сведения о планировщик задач см. в разделе [планировщик задач](/windows/desktop/TaskSchd/task-scheduler-reference).

> [!NOTE]
> Вы можете просматривать запланированные задания PowerShell и управлять ими в планировщик задач. Задания PowerShell и командлеты запланированных заданий работают только с запланированными заданиями, созданными в PowerShell.

## <a name="quick-start"></a>Быстрый запуск

В этом примере создается запланированное задание, которое запускается каждый день в 3:00 AM и запускается `Get-Process` командлет. Задание запускается, даже если компьютер работает от батарей.

```powershell
$trigger = New-JobTrigger -Daily -At 3AM
$options = New-ScheduledJobOption -StartIfOnBattery
Register-ScheduledJob -Name ProcessJob -ScriptBlock {Get-Process} `
-Trigger $trigger -ScheduledJobOption $options
```

`Get-ScheduledJob`Командлет возвращает запланированные задания на локальном компьютере.

```powershell
Get-ScheduledJob
```

```Output
Id         Name            Triggers        Command            Enabled
--         ----            --------        -------            -------
7          ProcessJob      {1}             Get-Process        True
```

`Get-JobTrigger` Возвращает триггеры задания **процессжоб** . Входные параметры задают запланированное задание, а не триггер, так как триггеры сохраняются в запланированном задании.

```powershell
Get-JobTrigger -Name ProcessJob
```

```Output
Id         Frequency       Time                   DaysOfWeek        Enabled
--         ---------       ----                   ----------        -------
1          Daily           11/5/2011 3:00:00 AM                     True
```

В этом примере используется параметр **континуеифгоингонбаттери** `Set-ScheduledJob` командлета, чтобы изменить свойство **Стопифгоингонбаттериес** объекта **процессжоб** на **false** .

```powershell
Get-ScheduledJob -Name ProcessJob | Set-ScheduledJobOption `
-ContinueIfGoingOnBattery -Passthru
```

```Output
StartIfOnBatteries     : True
StopIfGoingOnBatteries : False
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
MultipleInstancePolicy : IgnoreNew
JobDefinition          : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

`Get-ScheduledJob`Командлет возвращает запланированное задание **процессжоб** .

```powershell
Get-ScheduledJob ProcessJob
```

```Output
Id         Name            Triggers        Command        Enabled
--         ----            --------        -------        -------
7          ProcessJob      {1}             Get-Process    True
```

`Get-Job`Командлет возвращает все экземпляры запланированного задания **процессжоб** , которые были запущены на данный момент. `Get-Job`Командлет получает запланированные задания только при импорте модуля **PSScheduledJob** в текущий сеанс.

> [!TIP]
> Обратите внимание, что командлеты запланированных заданий используются для управления запланированными заданиями, но для управления экземплярами запланированных заданий используются командлеты задания.

```powershell
Get-Job -Name ProcessJob
```

```Output
Id     Name        PSJobTypeName  State    HasMoreData   Location   Command
--     ----        ------------   -----    -----------   --------   -------
45     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
46     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
47     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
48     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
49     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
50     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
51     ProcessJob  PSScheduledJob Completed       True   localhost   Get-Process
```

`Receive-Job`Командлет возвращает результаты последнего экземпляра запланированного задания **ПРОЦЕССЖОБ** (ИД = 51).

```powershell
Receive-Job -ID 51
```

Несмотря на то `Receive-Job` , что команда не включала параметр **сохранения** , результаты задания сохраняются на диске, пока вы не удалите их или не превышено максимальное число результатов.

Результаты задания больше не доступны в этом сеансе, но если вы запускаете новый сеанс или открываете новое окно PowerShell, результаты задания снова становятся доступными.

Следующая команда использует параметр **DefinitionName** `Start-Job` командлета для запуска запланированного задания **процессжоб** .

Задания, запускаемые с помощью `Start-Job` командлета, являются стандартными фоновыми заданиями PowerShell, а не экземплярами запланированного задания. Как и все фоновые задания, эти задания запускаются немедленно, они не подчиняются параметрам задания или не зависят от триггеров заданий, а их выходные данные не сохраняются в выходном каталоге каталога запланированных заданий.

```powershell
Start-Job -DefinitionName ProcessJob
```

`Unregister-ScheduledJob`Командлет удаляет запланированное задание **процессжоб** и все сохраненные результаты его экземпляров.

```powershell
Unregister-ScheduledJob ProcessJob
```

## <a name="scheduled-jobs-concepts"></a>Основные понятия запланированных заданий

Запланированное задание запускает команды или скрипт. Запланированное задание может включать триггеры заданий, запускающие задания и параметры задания, которые задают условия для выполнения задания.

Триггер задания автоматически запускает запланированное задание. Триггер задания может включать разовое или повторяющееся расписание или указывать событие, например, когда пользователь входит в систему или запускается Windows. Запланированное задание может иметь один или несколько триггеров заданий, а также создавать, добавлять, включать, отключать и получать Триггеры заданий.

Триггеры задания не являются обязательными. Запланированные задания можно запускать немедленно с помощью `Start-Job cmdlet` или путем добавления параметра **RunNow** в `Register-ScheduledJob` команду.

Параметры задания задают условия для выполнения запланированного задания. У каждого запланированного задания есть один объект параметров задания. Вы можете создавать и изменять объекты параметров задания, а также добавлять их в одно или несколько запланированных заданий.

При каждом запуске запланированного задания создается экземпляр задания. Используйте командлеты задания PowerShell для просмотра экземпляра задания и управления им.

Запланированные задания сохраняются на диске и используют команду командлета, `Register` вместо `New` . XML-файлы находятся на локальном компьютере в каталоге `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` .

PowerShell создает каталог для каждого запланированного задания и сохраняет команды задания, триггеры заданий, параметры задания и результаты задания в каталоге запланированных заданий. Триггеры задания и параметры задания не сохраняются на диск независимо друг от друга.
Они сохраняются в XML-коде запланированного задания для каждого запланированного задания, с которым они связаны.

Запланированные задания, триггеры заданий и параметры задания отображаются в PowerShell как объекты.
Объекты взаимосвязаны, что упрощает их обнаружение и использование в командах и скриптах.

Запланированные задания отображаются как объекты **ScheduledJobDefinition** . Объект **ScheduledJobDefinition** имеет свойство **жобтригжерс** , которое содержит триггеры заданий запланированного задания и свойство **Options** , которое содержит параметры задания. Объекты **счедуледжобтригжерс** и **счедуледжобоптионс** , которые представляют триггеры задания и параметры задания соответственно, имеют свойство **JobDefinition** , содержащее запланированное задание, с которым они связаны. Это рекурсивное межсоединение позволяет легко найти триггеры и параметры запланированного задания, а также найти, создать скрипт и отобразить запланированное задание, связанное с любым триггером задания или параметром задания.

## <a name="see-also"></a>См. также статью

[about_Scheduled_Jobs_Basics](about_Scheduled_Jobs_Basics.md)

[about_Scheduled_Jobs_Advanced](about_Scheduled_Jobs_Advanced.md)

[about_Scheduled_Jobs_Troubleshooting](about_Scheduled_Jobs_Troubleshooting.md)

Командлеты модуля [PSScheduledJob](xref:PSScheduledJob)

[Планировщик заданий](/windows/desktop/TaskSchd/task-scheduler-reference)
