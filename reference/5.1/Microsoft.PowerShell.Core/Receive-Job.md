---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/receive-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Receive-Job.
ms.openlocfilehash: 7b872c2a28943ee3d2b9ab27459ddb87722cc954
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227085"
---
# Receive-Job.

## Краткий обзор
Возвращает результаты фоновых заданий PowerShell в текущем сеансе.

## SYNTAX

### Расположение (по умолчанию)

```
Receive-Job [-Job] <Job[]> [[-Location] <String[]>] [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob]
 [-WriteEvents] [-WriteJobInResults] [<CommonParameters>]
```

### Сеанс

```
Receive-Job [-Job] <Job[]> [[-Session] <PSSession[]>] [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob]
 [-WriteEvents] [-WriteJobInResults] [<CommonParameters>]
```

### ИмяКомпьютера

```
Receive-Job [-Job] <Job[]> [[-ComputerName] <String[]>] [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob]
 [-WriteEvents] [-WriteJobInResults] [<CommonParameters>]
```

### намепараметерсет

```
Receive-Job [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob] [-WriteEvents] [-WriteJobInResults]
 [-Name] <String[]> [<CommonParameters>]
```

### инстанцеидпараметерсет

```
Receive-Job [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob] [-WriteEvents] [-WriteJobInResults]
 [-InstanceId] <Guid[]> [<CommonParameters>]
```

### сессионидпараметерсет

```
Receive-Job [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob] [-WriteEvents] [-WriteJobInResults]
 [-Id] <Int32[]> [<CommonParameters>]
```

## DESCRIPTION

`Receive-Job`Командлет получает результаты фоновых заданий PowerShell, таких как запущенные с помощью `Start-Job` командлета или параметра **AsJob** любого командлета.
Можно получить результаты всех заданий или указать задания по имени, идентификатору, идентификатору экземпляра, имени компьютера, расположению или сеансу или путем отправки объекта задания.

При запуске фонового задания PowerShell задание запускается, но результаты не отображаются немедленно. Вместо этого команда возвращает объект, представляющий фоновое задание.
Объект задания содержит полезные сведения о задании, но не содержит результатов.
Этот метод позволяет продолжить работу в сеансе во время выполнения задания.
Дополнительные сведения о фоновых заданиях в PowerShell см. в разделе [about_Jobs](./About/about_Jobs.md).

`Receive-Job`Командлет возвращает результаты, созданные в момент `Receive-Job` отправки команды.
Если результаты еще не завершены, можно выполнить дополнительные команды, `Receive-Job` чтобы получить оставшиеся результаты.

По умолчанию результаты задания удаляются из системы при их получении, однако можно использовать параметр **Keep** для сохранения результатов, чтобы можно было получить их снова.
Чтобы удалить результаты задания, выполните `Receive-Job` команду еще раз без параметра **сохранения** , закройте сеанс или используйте `Remove-Job` командлет для удаления задания из сеанса.

Начиная с Windows PowerShell 3,0, `Receive-Job` также получает результаты пользовательских типов заданий, таких как задания рабочего процесса и экземпляры запланированных заданий.
Чтобы обеспечить `Receive-Job` Получение результатов настраиваемого типа задания, импортируйте модуль, который поддерживает пользовательский тип задания, в сеанс перед выполнением `Receive-Job` команды либо с помощью `Import-Module` командлета, либо путем получения командлета в модуле.
Дополнительные сведения о определенных пользовательских типах заданий см. в разделе документации о данной функции.

## Примеры

### Пример 1. получение результатов для определенного задания

```powershell
$job = Start-Job -ScriptBlock {Get-Process}
Receive-Job -Job $job
```

Эти команды используют параметр **задания** `Receive-Job` для для получения результатов определенного задания.

Первая команда запускает задание с параметром `Start-Job` и сохраняет объект задания в `$job` переменной.

Вторая команда использует `Receive-Job` командлет для получения результатов задания.
Она использует параметр **Job** для указания задания.

### Пример 2. Использование параметра "Держитесь"

```powershell
$job = Start-Job -ScriptBlock {Get-Service dhcp, fakeservice}
$job | Receive-Job -Keep
```

```Output
Cannot find any service with service name 'fakeservice'.
    + CategoryInfo          : ObjectNotFound: (fakeservice:String) [Get-Service], ServiceCommandException
    + FullyQualifiedErrorId : NoServiceFoundForGivenName,Microsoft.PowerShell.Commands.GetServiceCommand
    + PSComputerName        : localhost

Status   Name               DisplayName
------   ----               -----------
Running  dhcp               DHCP Client
```

```powershell
$job | Receive-Job -Keep
```

```output
Cannot find any service with service name 'fakeservice'.
    + CategoryInfo          : ObjectNotFound: (fakeservice:String) [Get-Service], ServiceCommandException
    + FullyQualifiedErrorId : NoServiceFoundForGivenName,Microsoft.PowerShell.Commands.GetServiceCommand
    + PSComputerName        : localhost

Status   Name               DisplayName
------   ----               -----------
Running  dhcp               DHCP Client
```

В этом примере задание сохраняется в `$job` переменной и передает задание в `Receive-Job` командлет. `-Keep`Параметр также используется, чтобы разрешить повторное извлечение всех агрегированных данных потока после первого представления.

### Пример 3. получение результатов нескольких фоновых заданий

При использовании параметра **AsJob** `Invoke-Command` для запуска задания объект задания создается на локальном компьютере, даже если задание выполняется на удаленных компьютерах.
Таким образом, для управления заданием можно использовать локальные команды.

Кроме того, при использовании **AsJob** PowerShell возвращает один объект задания, содержащий дочернее задание для каждого запущенного задания. В этом случае объект задания содержит три дочерних задания (по одному для каждого задания на каждом удаленном компьютере).

```powershell
# Use the Invoke-Command cmdlet with the -AsJob parameter to start a background job that runs a Get-Service command on three remote computers.
# Store the resulting job object in the $j variable
$j = Invoke-Command -ComputerName Server01, Server02, Server03 -ScriptBlock {Get-Service} -AsJob
# Display the value of the **ChildJobs** property of the job object in $j.
# The display shows that the command created three child jobs, one for the job on each remote computer.
# You could also use the -IncludeChildJobs parameter of the Get-Job cmdlet.
$j.ChildJobs
```

```Output
Id   Name     State      HasMoreData   Location       Command
--   ----     -----      -----------   --------       -------
2    Job2     Completed  True          Server01       Get-Service
3    Job3     Completed  True          Server02       Get-Service
4    Job4     Completed  True          Server03       Get-Service
```

```powershell
# Use the Receive-Job cmdlet to get the results of just the Job3 child job that ran on the Server02 computer.
# Use the *Keep* parameter to allow you to view the aggregated stream data more than once.
Receive-Job -Name Job3 -Keep
```

```Output
Status  Name        DisplayName                        PSComputerName
------  ----------- -----------                        --------------
Running AeLookupSvc Application Experience             Server02
Stopped ALG         Application Layer Gateway Service  Server02
Running Appinfo     Application Information            Server02
Running AppMgmt     Application Management             Server02
```

### Пример 4. получение результатов фоновых заданий на нескольких удаленных компьютерах

```powershell
# Use the New-PSSession cmdlet to create three user-managed PSSessions on three servers, and save the sessions in the $s variable.
$s = New-PSSession -ComputerName Server01, Server02, Server03
# Use Invoke-Command run a Start-Job command in each of the PSSessions in the $s variable.
# The job outputs the ComputerName of each server.
# Save the job objects in the $j variable.
$j = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {$env:COMPUTERNAME}}
# To confirm that these job objects are from the remote machines, run Get-Job to show no local jobs running.
Get-Job
```

```Output

```

```powershell
# Display the three job objects in $j.
# Note that the Localhost location is not the local computer, but instead localhost as it relates to the job on each Server.
$j
```

```Output
Id   Name     State      HasMoreData   Location   Command
--   ----     -----      -----------   --------   -------
1    Job1     Completed  True          Localhost  $env:COMPUTERNAME
2    Job2     Completed  True          Localhost  $env:COMPUTERNAME
3    Job3     Completed  True          Localhost  $env:COMPUTERNAME
```

```powershell
# Use Invoke-Command to run a Receive-Job command in each of the sessions in the $s variable and save the results in the $Results variable.
# The Receive-Job command must be run in each session because the jobs were run locally on each server.
$results = Invoke-Command -Session $s -ScriptBlock {Receive-Job -Job $Using:j}
```

```Output
Server01
Server02
Server03
```

В этом примере показано, как получить результаты фоновых заданий, выполняющихся на трех удаленных компьютерах.
В отличие от предыдущего примера, использование `Invoke-Command` для выполнения `Start-Job` команды на самом деле запускает три независимых задания на каждом из трех компьютеров. В результате команда вернула три объекта заданий, представляющие три задания, выполняемые локально на трех разных компьютерах.

> [!NOTE]
> В последней команде, поскольку `$j` является локальной переменной, блок скрипта использует модификатор области **using** для определения `$j` переменной. Дополнительные сведения об **использовании** модификатора SCOPE см. в разделе [about_Remote_Variables](./About/about_Remote_Variables.md).

### Пример 5. доступ к дочерним заданиям

`-Keep`Параметр сохраняет состояние агрегированных потоков задания, чтобы его можно было снова просмотреть. Без этого параметра все агрегированные данные потока удаляются при получении задания. Дополнительные сведения см. в разделе [about_Job_Details](About/about_Job_Details.md#child-jobs)

> [!NOTE]
> Агрегированные потоки включают потоки всех дочерних заданий. Вы по-прежнему можете обращаться к отдельным потокам данных через объект задания и дочерние объекты задания.

```powershell
Start-Job -Name TestJob -ScriptBlock {dir C:\, Z:\}
# Without the Keep parameter, aggregated child job data is displayed once.
# Then destroyed.
Receive-Job -Name TestJob
```

```output
    Directory: C:\

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-r---        1/24/2019   7:11 AM                Program Files
d-r---        2/13/2019   8:32 AM                Program Files (x86)
d-r---        10/3/2018  11:47 AM                Users
d-----         2/7/2019   1:52 AM                Windows
Cannot find drive. A drive with the name 'Z' does not exist.
    + CategoryInfo          : ObjectNotFound: (Z:String) [Get-ChildItem], DriveNotFoundException
    + FullyQualifiedErrorId : DriveNotFound,Microsoft.PowerShell.Commands.GetChildItemCommand
    + PSComputerName        : localhost
```

```powershell
# It would seem that the child job data is gone.
Receive-Job -Name TestJob
```

```output

```

```powershell
# Using the object model, you can still retrieve child job data and streams.
$job = Get-Job -Name TestJob
$job.ChildJobs[0].Error
```

```output
Cannot find drive. A drive with the name 'Z' does not exist.
    + CategoryInfo          : ObjectNotFound: (Z:String) [Get-ChildItem], DriveNotFoundException
    + FullyQualifiedErrorId : DriveNotFound,Microsoft.PowerShell.Commands.GetChildItemCommand
    + PSComputerName        : localhost
```

## PARAMETERS

### -Ауторемовежоб

Указывает, что этот командлет удаляет задание после того, как оно возвращает результаты задания.
Если задание имеет больше результатов, оно по-прежнему удаляется, но `Receive-Job` отображает сообщение.

Этот параметр работает только для настраиваемых типов заданий.
Он предназначен для экземпляров типов заданий, которые сохраняют задание или тип вне сеанса, например для экземпляров запланированных заданий.

Этот параметр нельзя использовать без параметра **Wait** .

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Указывает массив имен компьютеров.

Этот параметр выбирает результаты задания, которые хранятся на локальном компьютере.
Он не получает данные для заданий, выполняемых на удаленных компьютерах.
Чтобы получить результаты задания, хранящиеся на удаленных компьютерах, используйте `Invoke-Command` командлет для `Receive-Job` удаленного выполнения команды.

```yaml
Type: System.String[]
Parameter Sets: ComputerName
Aliases: Cn

Required: False
Position: 1
Default value: All computers available
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Force

Указывает, что этот командлет продолжает ожидать, если задания находятся в **приостановленном** или **отключенном** состоянии. По умолчанию параметр **Wait** для `Receive-Job` Возвращает или прерывает ожидание, если задания находятся в одном из следующих состояний:

- Завершено
- Ошибка
- Остановлена
- Приостановлена
- отключен.

Параметр **Force** допустим, только если в команде также используется параметр **Wait**.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Задает массив идентификаторов.
Этот командлет возвращает результаты заданий с указанными идентификаторами.

Идентификатор — это целое число, которое однозначно определяет задание в текущем сеансе.
Проще запомнить и ввести, чем идентификатор экземпляра, но он уникален только в текущем сеансе. Можно ввести один или несколько идентификаторов, разделенных запятыми.
Чтобы найти идентификатор задания, используйте `Get-Job` .

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId

Указывает массив идентификаторов экземпляров.
Этот командлет возвращает результаты заданий с указанными идентификаторами экземпляров.

Идентификатор экземпляра — это GUID, который однозначно определяет задание на компьютере.
Чтобы найти идентификатор экземпляра задания, используйте `Get-Job` командлет.

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: All instances
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Job

Указывает задание, для которого получаются результаты.

Введите переменную, содержащую задание, или команду, которая получает задание.
Можно также передать объект задания в `Receive-Job` .

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: Location, Session, ComputerName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Держитесь

Указывает, что этот командлет сохраняет агрегированные потоковые данные в системе даже после их получения. По умолчанию агрегированные данные потока удаляются после просмотра с помощью `Receive-Job` .

Закрытие сеанса или удаление задания с помощью `Remove-Job` командлета также приводит к удалению агрегированных данных потока.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### — Расположение

Задает массив расположений.
Этот командлет возвращает только результаты заданий в указанных расположениях.

```yaml
Type: System.String[]
Parameter Sets: Location
Aliases:

Required: False
Position: 1
Default value: All locations
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Указывает массив понятных имен.
Этот командлет возвращает результаты заданий с указанными именами.
Поддерживаются подстановочные знаки.

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

### -Неповторение

Указывает, что этот командлет получает результаты только из указанного задания.
По умолчанию `Receive-Job` также получает результаты всех дочерних заданий указанного задания.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Session

Указывает массив сеансов.
Этот командлет возвращает результаты заданий, выполненных в указанном сеансе PowerShell ( **PSSession** ).
Введите переменную, содержащую **PSSession** или команду, которая получает **PSSession** , например `Get-PSSession` команду.

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: False
Position: 1
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Wait

Указывает, что этот командлет подавляет командную строку, пока не будут получены все результаты задания.
По умолчанию `Receive-Job` немедленно возвращает доступные результаты.

По умолчанию параметр **Wait** ожидает, пока задание не перейдет в одно из следующих состояний:

- Завершено
- Ошибка
- Остановлена
- Приостановлена
- отключен.

Чтобы указать, что параметр **Wait** должен продолжать ожидание, если состояние задания — suspended или DISCONNECTED, используйте параметр **Force** вместе с параметром **Wait** .

Этот параметр впервые появился в Windows PowerShell 3.0.

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

### -Вритивентс

Указывает, что этот командлет сообщает об изменениях в состоянии задания, пока он ожидает завершения задания.

Этот параметр допустим, только если параметр **Wait** используется в команде и опущен параметр **Keep**.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Вритежобинресултс

Указывает, что этот командлет возвращает объект задания, за которым следуют результаты.

Этот параметр допустим, только если параметр **Wait** используется в команде и опущен параметр **Keep**.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](./About/about_CommonParameters.md).

## Входные данные

### System. Management. Automation. job

К этому командлету можно передать объекты заданий.

## Выходные данные

### PSObject

Этот командлет возвращает результаты выполнения команд в задании.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Get-Job.](Get-Job.md)

[Invoke-Command](Invoke-Command.md)

[Remove-Job](Remove-Job.md)

[Resume-Job](Resume-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job.](Stop-Job.md)

[Suspend-Job](Suspend-Job.md)

[Wait-Job](Wait-Job.md)
