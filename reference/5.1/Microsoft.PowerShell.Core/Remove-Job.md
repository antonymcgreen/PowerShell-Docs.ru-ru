---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Job
ms.openlocfilehash: 589c43c814d5d68e57fd20226c675bf0f9587b69
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227061"
---
# Remove-Job

## Краткий обзор
Удаляет фоновое задание PowerShell.

## SYNTAX

### Сессионидпараметерсет (по умолчанию)

```
Remove-Job [-Id] <Int32[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### жобпараметерсет

```
Remove-Job [-Job] <Job[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### намепараметерсет

```
Remove-Job [-Name] <String[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### инстанцеидпараметерсет

```
Remove-Job [-InstanceId] <Guid[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### филтерпараметерсет

```
Remove-Job [-Filter] <Hashtable> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### статепараметерсет

```
Remove-Job [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### коммандпараметерсет

```
Remove-Job [-Command <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Remove-Job`Командлет удаляет фоновые задания PowerShell, которые были запущены `Start-Job` командлетом или командлетами `Invoke-Command` , например, поддерживают параметр **AsJob** .

Можно использовать `Remove-Job` для удаления всех заданий или удаления выбранных заданий. Задания идентифицируются по **имени** , **ИДЕНТИФИКАТОРу** , **идентификатору экземпляра** , **команде** или **состоянию**. Или же объект задания может быть отправлен в конвейер в `Remove-Job` . Без параметров и значений параметров не оказывает никакого `Remove-Job` влияния.

Поскольку PowerShell 3,0, `Remove-Job` может удалять пользовательские типы заданий, такие как запланированные задания и задания рабочего процесса. Например, `Remove-Job` удаляет запланированное задание, все экземпляры запланированного задания на диске и результаты всех запущенных экземпляров заданий.

При попытке удалить выполняющееся задание `Remove-Job` завершается ошибкой. Используйте `Stop-Job` командлет для завершения выполняющегося задания. Или используйте `Remove-Job` с параметром **Force** для удаления выполняющегося задания.

Задания остаются в глобальном кэше заданий до тех пор, пока не будет удалено фоновое задание или не будет закрыт сеанс PowerShell.

## Примеры

### Пример 1. Удаление задания с использованием его имени

В этом примере используется переменная и конвейер для удаления задания по имени.

```powershell
$batch = Get-Job -Name BatchJob
$batch | Remove-Job
```

`Get-Job` использует параметр **Name** для указания задания **батчжоб**. Объект задания хранится в `$batch` переменной. Объект в отправляется в `$batch` конвейер в `Remove-Job` .

Альтернативой является использование параметра **задания** , например `Remove-Job -Job $batch` .

### Пример 2. Удаление всех заданий в сеансе

В этом примере удаляются все задания в текущем сеансе PowerShell.

```powershell
Get-job | Remove-Job
```

`Get-Job` Возвращает все задания в текущем сеансе PowerShell. Объекты задания отправляются по конвейеру в `Remove-Job` .

### Пример 3. Удаление заданий NotStarted

В этом примере удаляются все задания из текущего сеанса PowerShell, который еще не запущен.

```powershell
Remove-Job -State NotStarted
```

`Remove-Job` Задает состояние задания с помощью параметра **State** .

### Пример 4. Удаление заданий с помощью понятного имени

В этом примере удаляются все задания из текущего сеанса с понятными именами, заканчивающимися на * Batch * *, включая выполняемые задания.

```powershell
Remove-Job -Name *batch -Force
```

`Remove-Job` использует параметр **Name** для указания шаблона имени задания. Шаблон содержит `*` подстановочный знак звездочки () для поиска всех имен заданий, заканчивающихся **пакетной** службой. Параметр **Force** удаляет задания, выполняющие.

### Пример 5. Удаление задания, созданного с помощью Invoke-Command

В этом примере удаляется задание, запущенное на удаленном компьютере с `Invoke-Command` параметром **AsJob** .

Так как в примере используется параметр **AsJob** , объект задания создается на локальном компьютере.
Но задание выполняется на удаленном компьютере. Таким образом, для управления заданием можно использовать локальные команды.

```powershell
$job = Invoke-Command -ComputerName Server01 -ScriptBlock {Get-Process} -AsJob
$job | Remove-Job
```

`Invoke-Command` запускает задание на компьютере **Server01** . Параметр **AsJob** запускает **ScriptBlock** как фоновое задание. Объект задания хранится в `$job` переменной. `$job`Объект переменной отправляется по конвейеру в `Remove-Job` .

### Пример 6. Удаление задания, созданного с помощью Invoke-Command и Start-Job

В этом примере показано, как удалить задание на удаленном компьютере, запущенном с помощью команды `Invoke-Command` для запуска `Start-Job` . Объект задания создается на удаленном компьютере, а для управления заданием используются удаленные команды. При выполнении удаленной команды требуется постоянное подключение `Start-Job` .

```powershell
$S = New-PSSession -ComputerName Server01
Invoke-Command -Session $S -ScriptBlock {Start-Job -ScriptBlock {Get-Process} -Name MyJob}
Invoke-Command -Session $S -ScriptBlock {Remove-Job -Name MyJob}
```

`New-PSSession`создает на компьютере **Server01** **сеанс PSSession** , постоянное подключение. Соединение сохраняется в `$S` переменной.

`Invoke-Command` подключается к сеансу, сохраненному в `$S` . Блок **ScriptBlock** использует `Start-Job` для запуска удаленного задания. Задание выполняет `Get-Process` команду и использует параметр **Name** для указания понятного имени задания **MyJob**.

`Invoke-Command` использует `$S` сеанс и выполняется `Remove-Job` . Параметр **Name** указывает, что задание с именем **MyJob** будет удалено.

### Пример 7. Удаление задания с помощью InstanceId

В этом примере удаляется задание, основанное на его **InstanceId**.

```powershell
$job = Start-Job -ScriptBlock {Get-Process PowerShell}
$job | Format-List -Property *
Remove-Job -InstanceId ad02b942-8007-4407-87f3-d23e71955872
```

```Output
State         : Completed
HasMoreData   : True
StatusMessage :
Location      : localhost
Command       : Get-Process PowerShell
JobStateInfo  : Completed
Finished      : System.Threading.ManualResetEvent
InstanceId    : ad02b942-8007-4407-87f3-d23e71955872
Id            : 3
Name          : Job3
ChildJobs     : {Job4}
PSBeginTime   : 7/26/2019 11:36:56
PSEndTime     : 7/26/2019 11:36:57
PSJobTypeName : BackgroundJob
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
Information   : {}
```

`Start-Job` Запускает фоновое задание, а объект задания сохраняется в `$job` переменной.

Объект в отправляется в `$job` конвейер в `Format-List` . Параметр **Property** использует звездочку ( `*` ), чтобы указать, что все свойства объекта отображаются в списке.

`Remove-Job` задает удаляемое задание с помощью параметра **InstanceId** .

## PARAMETERS

### -Command

Удаляет задания, в команды которых входят указанные слова. Можно ввести разделенный запятыми массив.

```yaml
Type: System.String[]
Parameter Sets: CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm

Запрашивает подтверждение перед `Remove-Job` запуском.

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

### -Filter

Удаляет задания, которые соответствуют всем условиям, установленным в связанной хэш-таблице. Введите хэш-таблицу, где ключи являются свойствами заданий, а значения — значениями этих свойств.

Этот параметр работает только с пользовательскими типами заданий, такими как задания рабочих процессов и запланированные задания. Он не работает со стандартными фоновыми заданиями, такими как созданные с помощью `Start-Job` .

Этот параметр впервые появился в PowerShell 3.0.

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

### -Force

Удаляет задание, даже если состояние задания — **работает**. Если параметр **Force** не указан, то `Remove-Job` не удаляет выполняющиеся задания.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SessionIdParameterSet, JobParameterSet, NameParameterSet, InstanceIdParameterSet, FilterParameterSet
Aliases: F

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Удаляет фоновые задания с указанным **идентификатором**. Можно ввести разделенный запятыми массив. **Идентификатор** задания — это уникальное целое число, определяющее задание в текущем сеансе.

Чтобы найти **идентификатор** задания, используйте `Get-Job` параметр без параметров.

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

Удаляет задания с указанным **InstanceId**. Можно ввести разделенный запятыми массив. **InstanceId** — это уникальный идентификатор GUID, определяющий задание.

Чтобы найти **InstanceId** задания, используйте `Get-Job` .

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

### -Job

Указывает задания, которые требуется удалить. Введите переменную, содержащую задания, либо команду, которая их возвращают. Можно ввести разделенный запятыми массив.

Объекты задания можно отправить по конвейеру в `Remove-Job` .

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name

Удаляет только задания с указанным понятным именем. Разрешено использовать подстановочные знаки. Можно ввести разделенный запятыми массив.

Понятные имена для заданий не обязательно должны быть уникальными даже в рамках сеанса PowerShell. Используйте параметры **WhatIf** и **Confirm** при удалении файлов по имени.

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

### -State

Удаляет только задания с указанным состоянием. Чтобы удалить задания с состоянием **работает** , используйте параметр **Force** .

Допустимые значения:

- AtBreakpoint
- Блокировано
- Завершено
- Отключено
- Сбой
- NotStarted
- Запущен
- Остановлена
- Остановка
- Приостановлена
- Приостановка

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: AtBreakpoint, Blocked, Completed, Disconnected, Failed, NotStarted, Running, Stopped, Stopping, Suspended, Suspending

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf

Показывает, что произойдет при `Remove-Job` запуске. Командлет не выполняется.

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

### System. Management. Automation. job

Объект задания можно отправить по конвейеру в `Remove-Job` .

## Выходные данные

### Нет

`Remove-Job` не создает никаких выходных данных.

## ПРИМЕЧАНИЯ

Задание PowerShell создает новый процесс. После завершения задания процесс завершается. При `Remove-Job` запуске состояние задания удаляется.

Если задание останавливается до завершения и его процесс не завершается, процесс принудительно завершается.

## Связанные ссылки

[about_Jobs](./About/about_Jobs.md)

[about_Job_Details](./About/about_Job_Details.md)

[about_Remote_Jobs](./About/about_Remote_Jobs.md)

[Get-Job.](Get-Job.md)

[Invoke-Command](Invoke-Command.md)

[Receive-Job.](Receive-Job.md)

[Resume-Job](Resume-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job.](Stop-Job.md)

[Suspend-Job](Suspend-Job.md)

[Wait-Job](Wait-Job.md)
