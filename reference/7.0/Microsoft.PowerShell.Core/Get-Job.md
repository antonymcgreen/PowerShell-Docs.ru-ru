---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-job?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Job.
ms.openlocfilehash: 76644dbf15d2bdabd7a365f4bd5910a50502e17d
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226321"
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

Командлет **Get-Job** возвращает объекты, которые представляют фоновые задания, запущенные в рамках текущего сеанса. **Get-Job** можно использовать для получения заданий, запущенных с помощью командлета Start-Job, или с помощью параметра *AsJob* любого командлета.

Без параметров команда **Get-Job** возвращает все задания в текущем сеансе.
С помощью параметров командлета **Get-Job** можно получить определенные задания.

Объект задания, возвращаемый командлетом **Get-Job** , содержит полезную информацию о задании, но не содержит результатов его выполнения. Чтобы получить результаты, используйте командлет Receive-Job.

Фоновое задание PowerShell — это команда, которая выполняется в фоновом режиме без взаимодействия с текущим сеансом. Как правило, для выполнения сложной команды, которая занимает много времени, используется фоновое задание. Дополнительные сведения о фоновых заданиях в PowerShell см. в разделе about_Jobs.

Начиная с выпуска Windows PowerShell 3.0 командлет **Get-Job** также возвращает задания настраиваемых типов, такие как задания рабочих процессов и экземпляры запланированных заданий. Чтобы определить тип задания, используйте его свойство **PSJobTypeName**.

Чтобы включить командлет **Get-Job** для получения настраиваемого типа задания, импортируйте модуль, который поддерживает тип настраиваемого задания, в сеанс перед выполнением команды **get-job** с помощью Import-Moduleого или с помощью или получения командлета в модуле. Дополнительные сведения о определенных пользовательских типах заданий см. в разделе документации о данной функции.

## Примеры

### Пример 1. получение всех фоновых заданий, запущенных в текущем сеансе

```powershell
Get-Job
```

Эта команда возвращает все фоновые задания, запущенные в рамках текущего сеанса.
Сюда не включаются задания, созданные в рамках других сеансов, даже если они выполняются на локальном компьютере.

### Пример 2. завершение задания с помощью идентификатора экземпляра

Эти команды показывают, как получить идентификатор экземпляра задания, а затем с его помощью остановить задание.
В отличие от имени задания, идентификатор экземпляра уникален.

```powershell
$j = Get-Job -Name Job1
$ID = $j.InstanceID
$ID
```

```Output
Guid
----
03c3232e-1d23-453b-a6f4-ed73c9e29d55
```

```powershell
Stop-Job -InstanceId $ID
```

В первой команде используется командлет **Get-Job** для получения задания. Для обнаружения задания используется параметр *Name* . Объект задания, который возвращает командлет **Get-Job** , сохраняется в переменной $j. В этом примере имеется только одно задание с указанным именем.

Вторая команда возвращает свойство **InstanceId** объекта в переменной $j и сохраняет его в переменной $ID.

Третья команда выводит значение переменной $ID.

Четвертая команда использует командлет Stop-Job для завершения задания. Параметр *InstanceId* определяет задание, а переменная $ID содержит идентификатор экземпляра задания.

### Пример 3. получение заданий, включающих определенную команду

```powershell
Get-Job -Command "*get-process*"
```

Эта команда возвращает задания в системе, которые содержат команду Get-Process. В ней используется параметр *Command* командлета **Get-Job** для ограничения получаемых заданий. Команда использует подстановочные знаки (*) для получения заданий, включающих команду **Get-Process** в любом месте командной строки.

### Пример 4. получение заданий, включающих определенную команду, с помощью конвейера

```powershell
"*get-process*" | Get-Job
```

Как и команда в предыдущем примере, эта команда возвращает задания в системе, которые включают команду **Get-Process** . Команда использует оператор конвейера (|) для отправки строки в кавычках командлету **Get-Job** . Это равносильно предыдущей команде.

### Пример 5. получение заданий, которые не были запущены

```powershell
Get-Job -State NotStarted
```

Эта команда возвращает только те задания, которые созданы, но еще не запущены.
Сюда входят задания, запланированные к выполнению в будущем, и задания, выполнение которых еще не запланировано.

### Пример 6. получение заданий, которым не было назначено имя

```powershell
Get-Job -Name Job*
```

Эта команда возвращает все задания с именами заданий, которые начинаются с Job.
Так как задание \<number\> является именем задания по умолчанию, эта команда возвращает все задания, которым не назначено явное имя.

### Пример 7. Использование объекта задания для представления задания в команде

В этом примере показано, как использовать командлет **Get-Job** для получения объекта задания и как затем использовать этот объект для представления задания в команде.

```powershell
Start-Job -ScriptBlock {Get-Process} -Name MyJob
$j = Get-Job -Name MyJob
$j
```

```Output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
6      MyJob           BackgroundJob   Completed     True            localhost            Get-Process
```

```powershell
Receive-Job -Job $j
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    124       4    13572      12080    59            1140 audiodg
    783      16    11428      13636   100             548 CcmExec
     96       4     4252       3764    59            3856 ccmsetup
...
```

Первая команда использует командлет **Start-Job** для запуска фонового задания, запускающего команду **Get-Process** на локальном компьютере. С помощью параметра *Name* командлета **Start-Job** заданию присваивается понятное имя.

Во второй команде используется командлет Get-Job для получения задания. Задание определяется с помощью параметра *Name* командлета **Get-Job**. Полученный объект задания сохраняется в переменную $j.

Третья команда выводит значение объекта задания в переменной $j. Значение свойства **State** показывает, что задание завершено. Значение свойства **HasMoreData** показывает, что есть результаты задания, которые еще не были получены.

Четвертая команда использует командлет **Receive-Job** для получения результатов задания. Объект задания в переменной $j представляет задание. Можно также использовать оператор конвейера для отправки объекта задания в **Receive-Job**.

### Пример 8. получение всех заданий, включая задания, запущенные другим методом

В этом примере показано, что командлет **Get-Job** может получить все задания, запущенные в текущем сеансе, даже если они были запущены с помощью различных методов.

```powershell
Start-Job -ScriptBlock {Get-EventLog System}
Invoke-Command -ComputerName S1 -ScriptBlock {Get-EventLog System} -AsJob
Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Get-Job
```

```Output
Id     Name       PSJobTypeName   State         HasMoreData     Location        Command
--     ----       -------------   -----         -----------     --------        -------
1      Job1       BackgroundJob   Running       True            localhost       Get-EventLog System
2      Job2       RemoteJob       Running       True            S1              Get-EventLog System
```

```powershell
Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
```

```Output
Id    Name     PSJobTypeName  State      HasMoreData   Location   Command
--    ----     -------------  -----      -----------   -------    -------
4     Job4     BackgroundJob  Running    True          localhost  Get-Eventlog System
```

Первая команда использует командлет **Start-Job** для запуска задания на локальном компьютере.

Вторая команда использует параметр *AsJob* командлета **Invoke-Command** для запуска задания на компьютере S1. Хотя команды задания выполняются на удаленном компьютере, объект задания создается на локальном, поэтому вы можете управлять заданием с помощью локальных команд.

В третьей команде используется командлет **Invoke-Command** для выполнения команды **Start-Job** на компьютере S2. При использовании этого метода объект задания создается на удаленном компьютере, поэтому для управления заданием используются удаленные команды.

В четвертой команде используется командлет **Get-Job** для получения заданий, сохраненных на локальном компьютере. Свойство **псжобтипенаме** заданий, представленное в Windows PowerShell 3,0, показывает, что локальное задание, запущенное с помощью командлета **Start-Job** , является фоновым заданием и заданием, запущенным в удаленном сеансе с помощью командлета **Invoke-Command** , является удаленное задание.

Пятая команда использует **командлет Invoke-Command** для выполнения команды **Get-Job** на компьютере S2. В выходных данных примера показаны результаты выполнения команды Get-Job. На компьютере S2 задание отображается как локальное. Имя компьютера — localhost, а тип задания — фоновое задание.

Дополнительные сведения о выполнении фоновых заданий на удаленных компьютерах см. в разделе about_Remote_Jobs.

### Пример 9. исследование невыполненного задания

```powershell
Start-Job -ScriptBlock {Get-Process}
```

```Output
Id     Name       PSJobTypeName   State       HasMoreData     Location             Command
--     ----       -------------   -----       -----------     --------             -------
1      Job1       BackgroundJob   Failed      False           localhost            Get-Process
```

```powershell
(Get-Job).JobStateInfo | Format-List -Property *
```

```Output
State  : Failed
Reason :
```

```powershell
Get-Job | Format-List -Property *
```

```Output
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
```

```powershell
(Get-Job -Name job2).JobStateInfo.Reason
```

```Output
Connecting to remote server using WSManCreateShellEx api failed. The async callback gave the following error message: Access is denied.

For information about requirements for remoting in PowerShell, see about_Remote_Requirements. For
troubleshooting tips, see about_Remote_Troubleshooting.
```

Эта команда показывает, как использовать объект задания, возвращаемый командлетом **Get-Job** , чтобы выяснить причину сбоя задания.
Она также показывает, как получить дочерние задания каждого задания.

Первая команда использует командлет **Start-Job** для запуска задания на локальном компьютере. Объект задания, который возвращает командлет **Start-Job** , показывает, что задание завершилось сбоем. Значение свойства **State** не выполнено.

Во второй команде используется командлет **Get-Job** для получения задания. С помощью точечной нотации извлекается значение свойства **JobStateInfo** объекта. Он использует оператор конвейера для отправки объекта из свойства **JobStateInfo** в командлет Format-List, который форматирует все свойства объекта (*) в списке. Результат выполнения команды **Format-List** показывает, что значение свойства **Reason** задания пусто.

Третья команда изучает дополнительные сведения. Он использует команду **Get-Job** для получения задания, а затем использует оператор конвейера для отправки всего объекта задания в командлет **Format-List** , который отображает все свойства задания в списке. Отображение всех свойств в объекте задания показывает, что задание содержит дочернее задание с именем Job2.

В четвертой команде используется командлет **Get-Job** для получения объекта задания, который представляет дочернее задание Job2. Это задание, в котором на самом деле выполнялась команда. Он использует метод Dot для получения свойства **Reason** свойства **JobStateInfo** . Результат показывает, что задание завершилось сбоем из-за ошибки отказа в доступе. В этом случае пользователь забыл использовать параметр Запуск от имени администратора при запуске PowerShell. Поскольку фоновые задания используют функции удаленного взаимодействия PowerShell, компьютер должен быть настроен для запуска задания, даже если задание выполняется на локальном компьютере.

### Пример 10. получение отфильтрованных результатов

В этом примере показано, как использовать параметр *Filter* для получения задания рабочего процесса.
Параметр *Filter* , появившийся в Windows PowerShell 3.0, действует только применительно к заданиям настраиваемых типов, таким как задания рабочих процессов и запланированные задания.

```powershell
Workflow WFProcess {Get-Process}
WFProcess -AsJob -JobName WFProcessJob -PSPrivateMetadata @{MyCustomId = 92107}
Get-Job -Filter @{MyCustomId = 92107}
```

```Output
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
1      WFProcessJob    Completed     True            localhost            WFProcess
```

Первая команда использует ключевое слово **рабочего процесса** для создания рабочего процесса вфпроцесс.

Вторая команда использует параметр *AsJob* рабочего процесса вфпроцесс для запуска рабочего процесса в качестве фонового задания. Параметр *JobName* рабочего процесса используется для указания имени задания, а параметр *PSPrivateMetadata* рабочего процесса — для указания настраиваемого идентификатора.

В третьей команде используется параметр *Filter* командлета **Get-Job** для получения задания по настраиваемому идентификатору, который был указан в параметре *PSPrivateMetadata*.

### Пример 11. Получение сведений о дочерних заданиях

В этом примере показан результат использования параметров *IncludeChildJob* и *ChildJobState* командлета **Get-Job**.

```powershell
Get-Job
```

```Output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost            .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02   .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
```

```powershell
Get-Job -IncludeChildJob
```

```Output
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
```

```powershell
Get-Job -Name Job4 -ChildJobState Failed
```

```Output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost           .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02  .\Get-Archive.ps1
5      Job5                            Failed        False           Server01            .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
```

```powershell
(Get-Job -Name Job5).JobStateInfo.Reason
```

```Output
Connecting to remote server Server01 failed with the following error message:
Access is denied.
For more information, see the about_Remote_Troubleshooting Help topic.
```

Первая команда возвращает задания в текущем сеансе. Выходные данные включают в себя фоновое задание, удаленное задание и несколько экземпляров запланированного задания. Удаленное задание Job4, по-видимому, завершилось сбоем.

Во второй команде используется параметр *IncludeChildJob* командлета **Get-Job**. Выходные данные добавляют дочерние задания всех заданий, имеющих дочерние задания. В этом случае измененные выходные данные показывают, что не удалось выполнить дочернее задание Job5 в Job4.

Третья команда использует параметр *чилджобстате* со значением Failed. выходные данные включают все родительские задания и только дочерние задания, для которых произошел сбой.

Четвертая команда использует свойство **JobStateInfo** заданий и свойство **Reason** для выяснения причины сбоя Job5.

## PARAMETERS

### -After

Возвращает выполненные задания, которые завершились после указанных даты и времени. Введите объект **DateTime** , например, возвращаемый командлетом Get-Date, или строку, которую можно преобразовать в объект **DateTime** , например `Dec 1, 2012 2:00 AM` или `11/06` .

Этот параметр применим только к заданиям настраиваемых типов, таким как задания рабочих процессов и запланированные задания, имеющим свойство **EndTime**. Он не работает со стандартными фоновыми заданиями, такими как созданные с помощью командлета **Start-Job** . Дополнительные сведения о поддержке данного параметра см. в разделе справки о соответствующем типе заданий.

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

Возвращает выполненные задания, которые завершились до указанных даты и времени.
Введите объект **DateTime** .

Этот параметр применим только к заданиям настраиваемых типов, таким как задания рабочих процессов и запланированные задания, имеющим свойство **EndTime**. Он не работает со стандартными фоновыми заданиями, такими как созданные с помощью командлета **Start-Job** . Дополнительные сведения о поддержке данного параметра см. в разделе справки о соответствующем типе заданий.

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

При использовании командлета **Receive-Job** он удаляет из его хранилища возвращаемые результаты. Когда он возвращает все результаты задания в текущем сеансе, он устанавливает для свойства **хасморедата** задания значение $false), чтобы указать, что он больше не имеет результатов для задания в текущем сеансе. Чтобы запретить командлету *Receive-Job* удалять результаты и изменять значение свойства **HasMoreData** , используйте параметр **Keep** командлета **Receive-Job**. Для получения дополнительных сведений введите `Get-Help Receive-Job`.

Свойство **HasMoreData** относится к текущему сеансу. Если результаты для пользовательского типа задания сохраняются за пределами сеанса, например тип запланированного задания, который сохраняет результаты задания на диске, можно использовать командлет **Receive-Job** в другом сеансе для повторного получения результатов задания, даже если значение **хасморедата** равно $false. Подробнее см. в разделах справки по настраиваемому типу задания.

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
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
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
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
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

[Start-Job](Start-Job.md)

[Stop-Job.](Stop-Job.md)

[Wait-Job](Wait-Job.md)
