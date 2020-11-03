---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Job.
ms.openlocfilehash: 0b9c76ca1e26adaa244473366c2eabdaaa28452c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226681"
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

### коммандпараметерсет

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Command <String[]>] [<CommonParameters>]
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

### филтерпараметерсет

```
Get-Job [-Filter] <Hashtable> [<CommonParameters>]
```

## DESCRIPTION

Командлет **Get-Job** возвращает объекты, которые представляют фоновые задания, запущенные в рамках текущего сеанса.
**Get-Job** можно использовать для получения заданий, запущенных с помощью командлета Start-Job, или с помощью параметра *AsJob* любого командлета.

Без параметров команда **Get-Job** возвращает все задания в текущем сеансе.
С помощью параметров командлета **Get-Job** можно получить определенные задания.

Объект задания, возвращаемый командлетом **Get-Job** , содержит полезную информацию о задании, но не содержит результатов его выполнения.
Чтобы получить результаты, используйте командлет Receive-Job.

Фоновое задание Windows PowerShell — это команда, которая выполняется в фоновом режиме без взаимодействия с текущим сеансом.
Как правило, для выполнения сложной команды, которая занимает много времени, используется фоновое задание.
Дополнительные сведения о фоновых заданиях в Windows PowerShell см. в разделе about_Jobs.

Начиная с выпуска Windows PowerShell 3.0 командлет **Get-Job** также возвращает задания настраиваемых типов, такие как задания рабочих процессов и экземпляры запланированных заданий.
Чтобы определить тип задания, используйте его свойство **PSJobTypeName**.

Чтобы включить командлет **Get-Job** для получения настраиваемого типа задания, импортируйте модуль, который поддерживает тип настраиваемого задания, в сеанс перед выполнением команды **get-job** с помощью Import-Moduleого или с помощью или получения командлета в модуле.
Дополнительные сведения о определенных пользовательских типах заданий см. в разделе документации о данной функции.

## Примеры

### Пример 1. получение всех фоновых заданий, запущенных в текущем сеансе

```
PS C:\> Get-Job
```

Эта команда возвращает все фоновые задания, запущенные в рамках текущего сеанса.
Сюда не включаются задания, созданные в рамках других сеансов, даже если они выполняются на локальном компьютере.

### Пример 2. завершение задания с помощью идентификатора экземпляра

```
The first command uses the **Get-Job** cmdlet to get a job. It uses the *Name* parameter to identify the job. The command stores the job object that **Get-Job** returns in the $j variable. In this example, there is only one job with the specified name.
PS C:\> $j = Get-Job -Name Job1

The second command gets the **InstanceId** property of the object in the $j variable and stores it in the $ID variable.
PS C:\> $ID = $j.InstanceID

The third command displays the value of the $ID variable.
PS C:\> $ID

Guid
----
03c3232e-1d23-453b-a6f4-ed73c9e29d55

The fourth command uses Stop-Job cmdlet to stop the job. It uses the *InstanceId* parameter to identify the job and $ID variable to represent the instance ID of the job.
PS C:\> Stop-Job -InstanceId $ID
```

Эти команды показывают, как получить идентификатор экземпляра задания, а затем с его помощью остановить задание.
В отличие от имени задания, идентификатор экземпляра уникален.

### Пример 3. получение заданий, включающих определенную команду

```
PS C:\> Get-Job -Command "*get-process*"
```

Эта команда возвращает задания в системе, которые содержат команду Get-Process.
В ней используется параметр *Command* командлета **Get-Job** для ограничения получаемых заданий.
Команда использует подстановочные знаки (*) для получения заданий, включающих команду **Get-Process** в любом месте командной строки.

### Пример 4. получение заданий, включающих определенную команду, с помощью конвейера

```
PS C:\> "*get-process*" | Get-Job
```

Как и команда в предыдущем примере, эта команда возвращает задания в системе, которые включают команду **Get-Process** .
Команда использует оператор конвейера (|) для отправки строки в кавычках командлету **Get-Job** .
Это равносильно предыдущей команде.

### Пример 5. получение заданий, которые не были запущены

```
PS C:\> Get-Job -State NotStarted
```

Эта команда возвращает только те задания, которые созданы, но еще не запущены.
Сюда входят задания, запланированные к выполнению в будущем, и задания, выполнение которых еще не запланировано.

### Пример 6. получение заданий, которым не было назначено имя

```
PS C:\> Get-Job -Name Job*
```

Эта команда возвращает все задания с именами заданий, которые начинаются с Job.
Так как задание \<number\> является именем задания по умолчанию, эта команда возвращает все задания, которым не назначено явное имя.

### Пример 7. Использование объекта задания для представления задания в команде

```
The first command uses the **Start-Job** cmdlet to start a background job that runs a **Get-Process** command on the local computer. The command uses the *Name* parameter of **Start-Job** to assign a friendly name to the job.
PS C:\> Start-Job -ScriptBlock {Get-Process} -Name MyJob

The second command uses Get-Job to get the job. It uses the *Name* parameter of **Get-Job** to identify the job. The command saves the resulting job object in the $j variable.
PS C:\> $j = Get-Job -Name MyJob

The third command displays the value of the job object in the $j variable. The value of the **State** property shows that the job is completed. The value of the **HasMoreData** property shows that there are results available from the job that have not yet been retrieved.
PS C:\> $j
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
6      MyJob           BackgroundJob   Completed     True            localhost            Get-Process

The fourth command uses the **Receive-Job** cmdlet to get the results of the job. It uses the job object in the $j variable to represent the job. You can also use a pipeline operator to send a job object to **Receive-Job**.
PS C:\> Receive-Job -Job $j
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    124       4    13572      12080    59            1140 audiodg
    783      16    11428      13636   100             548 CcmExec
     96       4     4252       3764    59            3856 ccmsetup
...
```

В этом примере показано, как использовать командлет **Get-Job** для получения объекта задания и как затем использовать этот объект для представления задания в команде.

### Пример 8. получение всех заданий, включая задания, запущенные другим методом

```
The first command uses the **Start-Job** cmdlet to start a job on the local computer.
PS C:\> Start-Job -ScriptBlock {Get-EventLog System}

The second command uses the *AsJob* parameter of the **Invoke-Command** cmdlet to start a job on the S1 computer. Even though the commands in the job run on the remote computer, the job object is created on the local computer, so you use local commands to manage the job.
PS C:\> Invoke-Command -ComputerName S1 -ScriptBlock {Get-EventLog System} -AsJob

The third command uses the **Invoke-Command** cmdlet to run a **Start-Job** command on the S2 computer. By using this method, the job object is created on the remote computer, so you use remote commands to manage the job.
PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}

The fourth command uses **Get-Job** to get the jobs stored on the local computer. The **PSJobTypeName** property of jobs, introduced in Windows PowerShell 3.0, shows that the local job started by using the **Start-Job** cmdlet is a background job and the job started in a remote session by using the **Invoke-Command** cmdlet is a remote job.
PS C:\> Get-Job
Id     Name       PSJobTypeName   State         HasMoreData     Location        Command
--     ----       -------------   -----         -----------     --------        -------
1      Job1       BackgroundJob   Running       True            localhost       Get-EventLog System
2      Job2       RemoteJob       Running       True            S1              Get-EventLog System

The fifth command uses **Invoke-Command** to run a **Get-Job** command on the S2 computer.The sample output shows the results of the Get-Job command. On the S2 computer, the job appears to be a local job. The computer name is localhost and the job type is a background job.For more information about how to run background jobs on remote computers, see about_Remote_Jobs.
PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Id    Name     PSJobTypeName  State      HasMoreData   Location   Command
--    ----     -------------  -----      -----------   -------    -------
4     Job4     BackgroundJob  Running    True          localhost  Get-Eventlog System
```

В этом примере показано, что командлет **Get-Job** может получить все задания, запущенные в текущем сеансе, даже если они были запущены с помощью различных методов.

### Пример 9. исследование невыполненного задания

```
The first command uses the **Start-Job** cmdlet to start a job on the local computer. The job object that **Start-Job** returns shows that the job failed. The value of the **State** property is Failed.
PS C:\> Start-Job -ScriptBlock {Get-Process}
Id     Name       PSJobTypeName   State       HasMoreData     Location             Command
--     ----       -------------   -----       -----------     --------             -------
1      Job1       BackgroundJob   Failed      False           localhost            Get-Process

The second command uses the **Get-Job** cmdlet to get the job. The command uses the dot method to get the value of the **JobStateInfo** property of the object. It uses a pipeline operator to send the object in the **JobStateInfo** property to the Format-List cmdlet, which formats all of the properties of the object (*) in a list.The result of the **Format-List** command shows that the value of the **Reason** property of the job is blank.
PS C:\> (Get-Job).JobStateInfo | Format-List -Property *
State  : Failed
Reason :

The third command investigates more. It uses a **Get-Job** command to get the job and then uses a pipeline operator to send the whole job object to the **Format-List** cmdlet, which displays all of the properties of the job in a list.The display of all properties in the job object shows that the job contains a child job named Job2.
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

The fourth command uses **Get-Job** to get the job object that represents the Job2 child job. This is the job in which the command actually ran. It uses the dot method to get the **Reason** property of the **JobStateInfo** property.The result shows that the job failed because of an Access Denied error. In this case, the user forgot to use the Run as administrator option when starting Windows PowerShell.Because background jobs use the remoting features of Windows PowerShell, the computer must be configured for remoting to run a job, even when the job runs on the local computer.For information about requirements for remoting in Windows PowerShell, see about_Remote_Requirements. For troubleshooting tips, see about_Remote_Troubleshooting.
PS C:\> (Get-Job -Name job2).JobStateInfo.Reason
Connecting to remote server using WSManCreateShellEx api failed. The async callback gave the following error message: Access is denied.
```

Эта команда показывает, как использовать объект задания, возвращаемый командлетом **Get-Job** , чтобы выяснить причину сбоя задания.
Она также показывает, как получить дочерние задания каждого задания.

### Пример 10. получение отфильтрованных результатов

```
The first command uses the **Workflow** keyword to create the WFProcess workflow.
PS C:\> Workflow WFProcess {Get-Process}

The second command uses the *AsJob* parameter of the WFProcess workflow to run the workflow as a background job. It uses the *JobName* parameter of the workflow to specify a name for the job, and the *PSPrivateMetadata* parameter of the workflow to specify a custom ID.
PS C:\> WFProcess -AsJob -JobName WFProcessJob -PSPrivateMetadata @{MyCustomId = 92107}

The third command uses the *Filter* parameter of **Get-Job** to get the job by custom ID that was specified in the *PSPrivateMetadata* parameter.
PS C:\> Get-Job -Filter @{MyCustomId = 92107}
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
1      WFProcessJob    Completed     True            localhost            WFProcess
```

В этом примере показано, как использовать параметр *Filter* для получения задания рабочего процесса.
Параметр *Filter* , появившийся в Windows PowerShell 3.0, действует только применительно к заданиям настраиваемых типов, таким как задания рабочих процессов и запланированные задания.

### Пример 11. Получение сведений о дочерних заданиях

```
The first command gets the jobs in the current session. The output includes a background job, a remote job and several instances of a scheduled job. The remote job, Job4, appears to have failed.
PS C:\> Get-Job
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost            .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02   .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

The second command uses the *IncludeChildJob* parameter of **Get-Job**. The output adds the child jobs of all jobs that have child jobs.In this case, the revised output shows that only the Job5 child job of Job4 failed.
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

The third command uses the *ChildJobState* parameter with a value of Failed.The output includes all parent jobs and only the child jobs that failed.
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

The fifth command uses the **JobStateInfo** property of jobs and its **Reason** property to discover why Job5 failed.
PS C:\> (Get-Job -Name Job5).JobStateInfo.Reason
Connecting to remote server Server01 failed with the following error message:
Access is denied.
For more information, see the about_Remote_Troubleshooting Help topic.
```

В этом примере показан результат использования параметров *IncludeChildJob* и *ChildJobState* командлета **Get-Job**.

## PARAMETERS

### -After

Возвращает выполненные задания, которые завершились после указанных даты и времени.
Введите объект **DateTime** , например, возвращаемый командлетом Get-Date, или строку, которую можно преобразовать в объект **DateTime** , например `Dec 1, 2012 2:00 AM` или `11/06` .

Этот параметр применим только к заданиям настраиваемых типов, таким как задания рабочих процессов и запланированные задания, имеющим свойство **EndTime**.
Он не работает со стандартными фоновыми заданиями, такими как созданные с помощью командлета **Start-Job** .
Дополнительные сведения о поддержке данного параметра см. в разделе справки о соответствующем типе заданий.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — До

Возвращает выполненные задания, которые завершились до указанных даты и времени.
Введите объект **DateTime** .

Этот параметр применим только к заданиям настраиваемых типов, таким как задания рабочих процессов и запланированные задания, имеющим свойство **EndTime**.
Он не работает со стандартными фоновыми заданиями, такими как созданные с помощью командлета **Start-Job** .
Дополнительные сведения о поддержке данного параметра см. в разделе справки о соответствующем типе заданий.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Чилджобстате

Возвращает только те дочерние задания, которые находятся в указанном состоянии.
Допустимые значения для этого параметра:

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

По умолчанию командлет **Get-Job** не возвращает дочерние задания.
С помощью параметра *инклудечилджоб* командлет **Get-Job** получает все дочерние задания.
При использовании параметра *ChildJobState* параметр *IncludeChildJob* не действует.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Command

Указывает массив команд в виде строк.
Этот командлет возвращает задания, включающие указанные команды.
По умолчанию останавливаются все задания.
Для указания шаблона команды можно использовать подстановочные знаки.

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

Указывает хэш-таблицу условий.
Этот командлет возвращает задания, которые отвечают всем условиям.
Введите хэш-таблицу, где ключи являются свойствами заданий, а значения — значениями этих свойств.

Этот параметр работает только с пользовательскими типами заданий, такими как задания рабочих процессов и запланированные задания.
Он не работает со стандартными фоновыми заданиями, такими как созданные с помощью командлета **Start-Job** .
Дополнительные сведения о поддержке данного параметра см. в разделе справки о соответствующем типе заданий.

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
Свойство **HasMoreData** указывает, были ли все результаты задания получены в рамках текущего сеанса.
Чтобы получить задания с дополнительными результатами, укажите значение $True.
Чтобы получить задания, которые не имеют дополнительных результатов, укажите значение $False.

Чтобы получить результаты задания, используйте командлет Receive-Job.

При использовании командлета **Receive-Job** он удаляет из его хранилища возвращаемые результаты.
Когда он возвращает все результаты задания в текущем сеансе, он устанавливает для свойства **хасморедата** задания значение $false), чтобы указать, что он больше не имеет результатов для задания в текущем сеансе.
Чтобы запретить командлету *Receive-Job* удалять результаты и изменять значение свойства **HasMoreData** , используйте параметр **Keep** командлета **Receive-Job**.
Для получения дополнительных сведений введите `Get-Help Receive-Job`.

Свойство **HasMoreData** относится к текущему сеансу.
Если результаты для пользовательского типа задания сохраняются за пределами сеанса, например тип запланированного задания, который сохраняет результаты задания на диске, можно использовать командлет **Receive-Job** в другом сеансе для повторного получения результатов задания, даже если значение **хасморедата** равно $false.
Подробнее см. в разделах справки по настраиваемому типу задания.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Boolean
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Указывает массив идентификаторов заданий, которые получает этот командлет.

Идентификатор — это целое число, которое однозначно определяет задание в текущем сеансе.
Проще запомнить и ввести, чем идентификатор экземпляра, но он уникален только в текущем сеансе.
Можно ввести один или несколько идентификаторов, разделенных запятыми.
Чтобы найти идентификатор задания, введите `Get-Job` без параметров.

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

Этот параметр особенно полезен для изучения заданий рабочего процесса, для которых командлет **Get-Job** Возвращает родительское задание контейнера, а также сбои заданий, так как причина сбоя сохраняется в свойстве дочернего задания.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceId

Указывает массив идентификаторов экземпляров заданий, которые получает этот командлет.
По умолчанию останавливаются все задания.

Идентификатор экземпляра — это GUID, который однозначно определяет задание на компьютере.
Чтобы узнать идентификатор экземпляра задания, используйте командлет **Get-Job**.

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

Указывает массив понятных имен экземпляров заданий, которые получает этот командлет.
Введите имя задания или используйте подстановочные знаки для ввода шаблона имени задания.
По умолчанию командлет **Get-Job** возвращает все задания в текущем сеансе.

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

Указывает число заданий для получения.
Этот командлет возвращает задания, которые были завершены недавно.

Параметр *Newest* не сортирует задания по времени завершения.
Чтобы отсортировать выходные данные, используйте командлет Sort-Object.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Int32
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -State

Указывает состояние задания.
Этот командлет возвращает только задания в указанном состоянии.
Допустимые значения для этого параметра:

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

По умолчанию командлет **Get-Job** возвращает все задания в текущем сеансе.

Дополнительные сведения о состояниях заданий см. в разделе [перечисление JobState](https://msdn.microsoft.com/library/system.management.automation.jobstate) в библиотеке MSDN.

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

* Свойство **PSJobTypeName** задания указывает на его тип. Значение свойства определяется автором типа задания. Ниже приведен список распространенных типов заданий.

  - **Баккграунджоб**.
Локальное задание запущено с помощью команды **Start-Job**.

  - **Ремотежоб**.
Задание запущено в **PSSession** с помощью параметра *AsJob* командлета Invoke-Command.

  - **Псворкфловжоб**.
задание, запущенное с помощью общего параметра *AsJob* рабочих процессов.

## Связанные ссылки

[Invoke-Command](Invoke-Command.md)

[Receive-Job.](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Resume-Job](Resume-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job.](Stop-Job.md)

[Suspend-Job](Suspend-Job.md)

[Wait-Job](Wait-Job.md)

[about_Jobs](About/about_Jobs.md)

[about_Job_Details](About/about_Job_Details.md)

[about_Remote_Jobs](About/about_Remote_Jobs.md)

[about_Scheduled_Jobs](../PSScheduledJob/About/about_Scheduled_Jobs.md)
