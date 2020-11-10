---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-job?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Job.
ms.openlocfilehash: e93a46d863fb560c70d9257270af1e6f43d3f248
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94391193"
---
# Get-Job.

## Краткий обзор
Возвращает фоновые задания PowerShell, выполняемые в текущем сеансе.

## SYNTAX

### Сессионидпараметерсет (по умолчанию)

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [[-Id] <Int32[]>] [<CommonParameters>]
```

### инстанцеидпараметерсет

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### намепараметерсет

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Name] <String[]> [<CommonParameters>]
```

### статепараметерсет

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-State] <JobState> [<CommonParameters>]
```

### коммандпараметерсет

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Command <String[]>] [<CommonParameters>]
```

### филтерпараметерсет

```
Get-Job [-Filter] <Hashtable> [<CommonParameters>]
```

## DESCRIPTION

`Get-Job`Командлет возвращает объекты, представляющие фоновые задания, которые были запущены в текущем сеансе. Можно использовать `Get-Job` для получения заданий, запущенных с помощью `Start-Job` командлета, или с помощью параметра **AsJob** любого командлета.

Без параметров `Get-Job` команда возвращает все задания в текущем сеансе. `Get-Job`Для получения конкретных заданий можно использовать параметры.

Объект задания, который `Get-Job` возвращает, содержит полезные сведения о задании, но не содержит результатов задания. Чтобы получить результаты, используйте `Receive-Job` командлет.

Фоновое задание Windows PowerShell — это команда, которая выполняется в фоновом режиме без взаимодействия с текущим сеансом. Как правило, для выполнения сложной команды, которая занимает много времени, используется фоновое задание. Дополнительные сведения о фоновых заданиях в Windows PowerShell см. в разделе [about_Jobs](./about/about_Jobs.md).

Начиная с Windows PowerShell 3,0, `Get-Job` командлет также получает пользовательские типы заданий, такие как задания рабочего процесса и экземпляры запланированных заданий. Чтобы определить тип задания, используйте его свойство **PSJobTypeName**.

Чтобы разрешить `Get-Job` получение настраиваемого типа задания, импортируйте модуль, который поддерживает тип настраиваемого задания, в сеанс перед выполнением `Get-Job` команды либо с помощью `Import-Module` командлета, либо путем получения командлета в модуле. Дополнительные сведения о определенных пользовательских типах заданий см. в разделе документации о данной функции.

## Примеры

### Пример 1. получение всех фоновых заданий, запущенных в текущем сеансе

Эта команда возвращает все фоновые задания, запущенные в рамках текущего сеанса. Сюда не включаются задания, созданные в рамках других сеансов, даже если они выполняются на локальном компьютере.

```
PS C:\> Get-Job
```

### Пример 2. завершение задания с помощью идентификатора экземпляра

Эти команды показывают, как получить идентификатор экземпляра задания, а затем с его помощью остановить задание. В отличие от имени задания, идентификатор экземпляра уникален.

Первая команда использует `Get-Job` командлет для получения задания. Для обнаружения задания используется параметр **Name** . Команда сохраняет объект задания, который `Get-Job` возвращает значение в `$j` переменной. В этом примере имеется только одно задание с указанным именем. Вторая команда получает свойство **InstanceId** объекта в `$j` переменной и сохраняет его в `$ID` переменной. Третья команда отображает значение `$ID` переменной. Четвертая команда использует `Stop-Job` командлет для завершения задания.
Он использует параметр **InstanceId** для идентификации задания и переменной, `$ID` представляющей идентификатор экземпляра задания.

```
PS C:\> $j = Get-Job -Name Job1
PS C:\> $ID = $j.InstanceID
PS C:\> $ID

Guid
----
03c3232e-1d23-453b-a6f4-ed73c9e29d55

PS C:\> Stop-Job -InstanceId $ID
```

### Пример 3. получение заданий, включающих определенную команду

Эта команда возвращает задания в системе, содержащие `Get-Process` команду. Команда использует параметр **Command** аргумента `Get-Job` для ограничения числа извлекаемых заданий. Команда использует подстановочные знаки ( `*` ) для получения заданий, включающих `Get-Process` команду в любом месте командной строки.

```
PS C:\> Get-Job -Command "*get-process*"
```

### Пример 4. получение заданий, включающих определенную команду, с помощью конвейера

Как и команда в предыдущем примере, эта команда возвращает задания в системе, которые включают `Get-Process` команду. Команда использует оператор конвейера ( `|` ) для отправки строки в кавычки в `Get-Job` командлет. Это равносильно предыдущей команде.

```
PS C:\> "*get-process*" | Get-Job
```

### Пример 5. получение заданий, которые не были запущены

Эта команда возвращает только те задания, которые созданы, но еще не запущены. Сюда входят задания, запланированные к выполнению в будущем, и задания, выполнение которых еще не запланировано.

```
PS C:\> Get-Job -State NotStarted
```

### Пример 6. получение заданий, которым не было назначено имя

Эта команда возвращает все задания с именами заданий, которые начинаются с Job. Поскольку `job<number>` является именем задания по умолчанию, эта команда возвращает все задания, которым не назначено явное имя.

```
PS C:\> Get-Job -Name Job*
```

### Пример 7. Использование объекта задания для представления задания в команде

В этом примере показано, как использовать `Get-Job` для получения объекта задания, а затем показано, как использовать объект задания для представления задания в команде.

Первая команда использует `Start-Job` командлет для запуска фонового задания, запускающего `Get-Process` команду на локальном компьютере. Команда использует параметр **Name** параметра, `Start-Job` чтобы присвоить заданию понятное имя. Вторая команда использует `Get-Job` для получения задания. Для обнаружения задания используется параметр **Name** объекта `Get-Job` . Команда сохраняет результирующий объект задания в `$j` переменной. Третья команда отображает значение объекта задания в `$j` переменной. Значение свойства **State** показывает, что задание завершено. Значение свойства **HasMoreData** показывает, что есть результаты задания, которые еще не были получены. Четвертая команда использует `Receive-Job` командлет для получения результатов задания. Он использует объект задания в `$j` переменной для представления задания. Можно также использовать оператор конвейера для отправки объекта задания в `Receive-Job` .

```
PS C:\> Start-Job -ScriptBlock {Get-Process} -Name MyJob
PS C:\> $j = Get-Job -Name MyJob
PS C:\> $j
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
6      MyJob           BackgroundJob   Completed     True            localhost            Get-Process

PS C:\> Receive-Job -Job $j
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    124       4    13572      12080    59            1140 audiodg
    783      16    11428      13636   100             548 CcmExec
     96       4     4252       3764    59            3856 ccmsetup
...
```


### Пример 8. получение всех заданий, включая задания, запущенные другим методом

В этом примере показано, что `Get-Job` командлет может получить все задания, запущенные в текущем сеансе, даже если они были запущены с помощью различных методов.

Первая команда использует `Start-Job` командлет для запуска задания на локальном компьютере. Вторая команда использует параметр **AsJob** `Invoke-Command` командлета для запуска задания на компьютере S1. Хотя команды задания выполняются на удаленном компьютере, объект задания создается на локальном, поэтому вы можете управлять заданием с помощью локальных команд. Третья команда использует `Invoke-Command` командлет для выполнения `Start-Job` команды на компьютере S2. При использовании этого метода объект задания создается на удаленном компьютере, поэтому для управления заданием используются удаленные команды. Четвертая команда использует `Get-Job` для получения заданий, хранящихся на локальном компьютере. Свойство **псжобтипенаме** заданий, представленное в Windows PowerShell 3,0, показывает, что локальное задание, запущенное с помощью `Start-Job` командлета, является фоновым заданием и заданием, запущенным в удаленном сеансе с помощью `Invoke-Command` командлета, является удаленное задание. Пятая команда использует `Invoke-Command` для выполнения `Get-Job` команды на компьютере S2. В выходных данных примера показаны результаты выполнения `Get-Job` команды. На компьютере S2 задание отображается как локальное. Имя компьютера — localhost, а тип задания — фоновое задание. Дополнительные сведения о выполнении фоновых заданий на удаленных компьютерах см. в разделе [about_Remote_Jobs](./about/about_Remote_Jobs.md).

```
PS C:\> Start-Job -ScriptBlock {Get-EventLog System}
PS C:\> Invoke-Command -ComputerName S1 -ScriptBlock {Get-EventLog System} -AsJob
PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
PS C:\> Get-Job
Id     Name       PSJobTypeName   State         HasMoreData     Location        Command
--     ----       -------------   -----         -----------     --------        -------
1      Job1       BackgroundJob   Running       True            localhost       Get-EventLog System
2      Job2       RemoteJob       Running       True            S1              Get-EventLog System

PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Id    Name     PSJobTypeName  State      HasMoreData   Location   Command
--    ----     -------------  -----      -----------   -------    -------
4     Job4     BackgroundJob  Running    True          localhost  Get-Eventlog System
```

### Пример 9. исследование невыполненного задания

Эта команда показывает, как использовать объект задания, который `Get-Job` возвращает, чтобы выяснить причину сбоя задания.
Она также показывает, как получить дочерние задания каждого задания.

Первая команда использует `Start-Job` командлет для запуска задания на локальном компьютере. Объект задания, который `Start-Job` возвращает значение, показывает, что задание завершилось ошибкой. Значение свойства **State** не выполнено.

Вторая команда использует `Get-Job` командлет для получения задания. С помощью точечной нотации извлекается значение свойства **JobStateInfo** объекта. Он использует оператор конвейера для отправки объекта в свойство **JobStateInfo** в `Format-List` командлет, который форматирует все свойства объекта ( `*` ) в списке. Результат выполнения `Format-List` команды показывает, что значение свойства **Reason** задания пусто.

Третья команда изучает дополнительные сведения. Он использует `Get-Job` команду для получения задания, а затем использует оператор конвейера для отправки всего объекта задания в `Format-List` командлет, который отображает все свойства задания в списке. Отображение всех свойств в объекте задания показывает, что задание содержит дочернее задание с именем Job2.

Четвертая команда использует `Get-Job` для получения объекта задания, представляющего дочернее задание Job2. Это задание, в котором на самом деле выполнялась команда. Он использует метод Dot для получения свойства **Reason** свойства **JobStateInfo** . Результат показывает, что задание завершилось сбоем из-за ошибки отказа в доступе. В этом случае пользователь забыл использовать параметр Запуск от имени администратора при запуске Windows PowerShell. Поскольку фоновые задания используют функции удаленного взаимодействия Windows PowerShell, компьютер должен быть настроен для запуска задания, даже если задание выполняется на локальном компьютере. Сведения о требованиях для удаленного взаимодействия в Windows PowerShell см. в разделе [about_Remote_Requirements](./about/about_Remote_Requirements.md). Советы по устранению неполадок см. в разделе [about_Remote_Troubleshooting](./about/about_Remote_Troubleshooting.md).

```
PS C:\> Start-Job -ScriptBlock {Get-Process}
Id     Name       PSJobTypeName   State       HasMoreData     Location             Command
--     ----       -------------   -----       -----------     --------             -------
1      Job1       BackgroundJob   Failed      False           localhost            Get-Process

PS C:\> (Get-Job).JobStateInfo | Format-List -Property *
State  : Failed
Reason :

PS C:\> Get-Job | Format-List -Property *
HasMoreData   : False
StatusMessage :
Location      : localhost
Command       : get-process
JobStateInfo  : Failed
Finished      : System.Threading.ManualReset
EventInstanceId    : fb792295-1318-4f5d-8ac8-8a89c5261507
Id            : 1
Name          : Job1
ChildJobs     : {Job2}
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
StateChanged  :

PS C:\> (Get-Job -Name job2).JobStateInfo.Reason
Connecting to remote server using WSManCreateShellEx api failed. The async callback gave the
following error message: Access is denied.
```

### Пример 10. получение отфильтрованных результатов

В этом примере показано, как использовать параметр **Filter** для получения задания рабочего процесса. Параметр **Filter** , появившийся в Windows PowerShell 3.0, действует только применительно к заданиям настраиваемых типов, таким как задания рабочих процессов и запланированные задания.

Первая команда использует ключевое слово **рабочего процесса** для создания рабочего процесса вфпроцесс. Вторая команда использует параметр **AsJob** рабочего процесса вфпроцесс для запуска рабочего процесса в качестве фонового задания. Параметр **JobName** рабочего процесса используется для указания имени задания, а параметр **PSPrivateMetadata** рабочего процесса — для указания настраиваемого идентификатора. Третья команда использует параметр **Filter** объекта `Get-Job` для получения задания по пользовательскому идентификатору, указанному в параметре **псприватеметадата** .

```
PS C:\> Workflow WFProcess {Get-Process}
PS C:\> WFProcess -AsJob -JobName WFProcessJob -PSPrivateMetadata @{MyCustomId = 92107}
PS C:\> Get-Job -Filter @{MyCustomId = 92107}
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
1      WFProcessJob    Completed     True            localhost            WFProcess
```

### Пример 11. Получение сведений о дочерних заданиях

В этом примере показан результат использования параметров **инклудечилджоб** и **чилджобстате** `Get-Job` командлета.

Первая команда возвращает задания в текущем сеансе. Выходные данные включают в себя фоновое задание, удаленное задание и несколько экземпляров запланированного задания. Удаленное задание Job4, по-видимому, завершилось сбоем.
Вторая команда использует параметр **инклудечилджоб** объекта `Get-Job` . Выходные данные добавляют дочерние задания всех заданий, имеющих дочерние задания. В этом случае измененные выходные данные показывают, что не удалось выполнить дочернее задание Job5 в Job4. Третья команда использует параметр **чилджобстате** со значением Failed. выходные данные включают все родительские задания и только дочерние задания, для которых произошел сбой. Пятая команда использует свойство **JobStateInfo** заданий и свойство **Reason** для выяснения причины сбоя Job5.

```
PS C:\> Get-Job
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost            .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02   .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

PS C:\> Get-Job -IncludeChildJob
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost           .\Get-Archive.ps1
3      Job3                            Completed     True            localhost           .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02  .\Get-Archive.ps1
5      Job5                            Failed        False           Server01            .\Get-Archive.ps1
6      Job6                            Completed     True            Server02            .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

PS C:\> Get-Job -Name Job4 -ChildJobState Failed
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost           .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02  .\Get-Archive.ps1
5      Job5                            Failed        False           Server01            .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

PS C:\> (Get-Job -Name Job5).JobStateInfo.Reason
Connecting to remote server Server01 failed with the following error message:
Access is denied.
```

Дополнительные сведения см. в разделе справки [about_Remote_Troubleshooting](./about/about_Remote_Troubleshooting.md) .

## PARAMETERS

### -After

Возвращает выполненные задания, которые завершились после указанных даты и времени. Введите объект **DateTime** , например, возвращаемый `Get-Date` командлетом, или строку, которую можно преобразовать в объект **DateTime** , например `Dec 1, 2012 2:00 AM` или `11/06` .

Этот параметр применим только к заданиям настраиваемых типов, таким как задания рабочих процессов и запланированные задания, имеющим свойство **EndTime**. Он не работает со стандартными фоновыми заданиями, такими как созданные с помощью `Start-Job` командлета. Дополнительные сведения о поддержке данного параметра см. в разделе справки о соответствующем типе заданий.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — До

Возвращает выполненные задания, которые завершились до указанных даты и времени. Введите объект **DateTime** .

Этот параметр применим только к заданиям настраиваемых типов, таким как задания рабочих процессов и запланированные задания, имеющим свойство **EndTime**. Он не работает со стандартными фоновыми заданиями, такими как созданные с помощью `Start-Job` командлета. Дополнительные сведения о поддержке данного параметра см. в разделе справки о соответствующем типе заданий.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Чилджобстате

Возвращает только те дочерние задания, которые находятся в указанном состоянии. Допустимые значения для этого параметра:

- NotStarted
- Запущен
- Завершено
- Ошибка
- Остановлена
- Блокировано
- Приостановлена
- Отключено
- Приостановка
- Остановка

По умолчанию не `Get-Job` получает дочерних заданий. С помощью параметра **инклудечилджоб** `Get-Job` получает все дочерние задания. При использовании параметра **ChildJobState** параметр **IncludeChildJob** не действует.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Command

Указывает массив команд в виде строк. Этот командлет возвращает задания, включающие указанные команды. По умолчанию останавливаются все задания. Для указания шаблона команды можно использовать подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Filter

Указывает хэш-таблицу условий. Этот командлет возвращает задания, которые отвечают всем условиям.
Введите хэш-таблицу, где ключи являются свойствами заданий, а значения — значениями этих свойств.

Этот параметр работает только с пользовательскими типами заданий, такими как задания рабочих процессов и запланированные задания. Он не работает со стандартными фоновыми заданиями, такими как созданные с помощью `Start-Job` командлета. Дополнительные сведения о поддержке данного параметра см. в разделе справки о соответствующем типе заданий.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: FilterParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Хасморедата

Указывает, получает ли этот командлет только задания с указанным значением свойства **хасморедата** .
Свойство **HasMoreData** указывает, были ли все результаты задания получены в рамках текущего сеанса. Чтобы получить задания с дополнительными результатами, укажите значение `$True` . Чтобы получить задания, которые не имеют дополнительных результатов, укажите значение `$False` .

Чтобы получить результаты задания, используйте `Receive-Job` командлет.

При использовании `Receive-Job` командлета он удаляет из его хранилища, зависящего от сеанса, возвращаемые результаты. Когда он возвращает все результаты задания в текущем сеансе, он устанавливает для свойства **хасморедата** задания значение `$False` ), чтобы показать, что оно больше не содержит результатов для задания в текущем сеансе. Используйте параметр **держитесь** параметра, `Receive-Job` чтобы предотвратить `Receive-Job` Удаление результатов и изменение значения свойства **хасморедата** .
Для получения дополнительных сведений введите `Get-Help Receive-Job`.

Свойство **HasMoreData** относится к текущему сеансу. Если результаты для пользовательского типа задания сохраняются за пределами сеанса, например типа запланированного задания, который сохраняет результаты задания на диске, можно использовать `Receive-Job` командлет в другом сеансе для повторного получения результатов задания, даже если значение **хасморедата** равно `$False` . Подробнее см. в разделах справки по настраиваемому типу задания.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Boolean
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Указывает массив идентификаторов заданий, которые получает этот командлет.

Идентификатор — это целое число, которое однозначно определяет задание в текущем сеансе. Проще запомнить и ввести, чем идентификатор экземпляра, но он уникален только в текущем сеансе. Можно ввести один или несколько идентификаторов, разделенных запятыми. Чтобы найти идентификатор задания, введите `Get-Job` без параметров.

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Инклудечилджоб

Указывает, что этот командлет возвращает дочерние задания в дополнение к родительским заданиям.

Этот параметр особенно полезен для изучения заданий рабочего процесса, для которых `Get-Job` возвращается родительское задание контейнера и сбои заданий, поскольку причина сбоя сохраняется в свойстве дочернего задания.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceId

Указывает массив идентификаторов экземпляров заданий, которые получает этот командлет. По умолчанию останавливаются все задания.

Идентификатор экземпляра — это GUID, который однозначно определяет задание на компьютере. Чтобы найти идентификатор экземпляра задания, используйте `Get-Job` .

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Указывает массив понятных имен экземпляров заданий, которые получает этот командлет. Введите имя задания или используйте подстановочные знаки для ввода шаблона имени задания. По умолчанию `Get-Job` получает все задания в текущем сеансе.

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### — Самый новый

Указывает число заданий для получения. Этот командлет возвращает задания, которые были завершены недавно.

Параметр **Newest** не сортирует задания по времени завершения. Чтобы отсортировать выходные данные, используйте `Sort-Object` командлет.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Int32
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -State

Указывает состояние задания. Этот командлет возвращает только задания в указанном состоянии. Допустимые значения для этого параметра:

- NotStarted
- Запущен
- Завершено
- Ошибка
- Остановлена
- Блокировано
- Приостановлена
- Отключено
- Приостановка
- Остановка

По умолчанию `Get-Job` получает все задания в текущем сеансе.

Дополнительные сведения о состояниях заданий см. в разделе [JobState enumeration](/dotnet/api/system.management.automation.jobstate).

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

В этот командлет нельзя передать входные данные.

## Выходные данные

### System. Management. Automation. Ремотингжоб

Этот командлет возвращает объекты, представляющие задания в сеансе.

## ПРИМЕЧАНИЯ

Свойство **PSJobTypeName** задания указывает на его тип. Значение свойства определяется автором типа задания. Ниже приведен список распространенных типов заданий.

- **Баккграунджоб**. Локальное задание запущено с помощью `Start-Job` .
- **Ремотежоб**. Задание запущено в **PSSession** с помощью параметра **AsJob** `Invoke-Command` командлета.
- **Псворкфловжоб**. задание, запущенное с помощью общего параметра **AsJob** рабочих процессов.

## Связанные ссылки

[Invoke-Command](Invoke-Command.md)

[Receive-Job.](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job.](Stop-Job.md)

[Wait-Job](Wait-Job.md)

[about_Jobs](About/about_Jobs.md)

[about_Job_Details](About/about_Job_Details.md)

[about_Remote_Jobs](About/about_Remote_Jobs.md)
