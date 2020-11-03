---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/set-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-JobTrigger
ms.openlocfilehash: 8d1b12b67ccf695e1c4b948e6eeecf292c588af4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227365"
---
# Set-JobTrigger

## Краткий обзор
Изменяет триггер задания для запланированного задания.

## SYNTAX

```
Set-JobTrigger [-InputObject] <ScheduledJobTrigger[]> [-DaysInterval <Int32>] [-WeeksInterval <Int32>]
 [-RandomDelay <TimeSpan>] [-At <DateTime>] [-User <String>] [-DaysOfWeek <DayOfWeek[]>] [-AtStartup]
 [-AtLogOn] [-Once] [-RepetitionInterval <TimeSpan>] [-RepetitionDuration <TimeSpan>] [-RepeatIndefinitely]
 [-Daily] [-Weekly] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Set-JobTrigger** изменяет свойства триггеров задания для запланированных заданий.
Его можно использовать для изменения времени или частоты, с которой запускаются задания, а также для перехода от расписаний на основе времени к расписаниям, где активация осуществляется при загрузке системы или входе в нее.

Триггер задания определяет повторяющееся расписание или условия для запуска запланированного задания.
Хотя триггеры задания не сохраняются на диске, можно изменить триггеры задания для сохраненных на диск запланированных заданий.

Чтобы изменить триггер задания для запланированного задания, начните с использования командлета Get-JobTrigger, чтобы получить триггер задания для запланированного задания.
Затем передайте триггер в **Set-JobTrigger** или сохраните его в переменной и используйте параметр *InputObject* командлета **Set-JobTrigger** для идентификации триггера.
Используйте остальные параметры **Set-JobTrigger** для изменения триггера задания.

При изменении типа триггера задания, например при изменении триггера задания с ежедневного или еженедельного триггера на триггер *AtLogon* , исходные свойства триггера удаляются.
Однако при изменении значений триггера, но не его типа, например, при изменении дней еженедельного триггера, изменяются только задаваемые свойства.
Все остальные свойства исходного триггера задания сохраняются.

**Set-JobTrigger** — это одна из коллекций командлетов планирования заданий в модуле PSScheduledJob, который входит в состав Windows PowerShell.

Дополнительные сведения о запланированных заданиях см. в разделах описания в модуле PSScheduledJob.
Импортируйте модуль PSScheduledJob и введите: `Get-Help about_Scheduled*`  или см. about_Scheduled_Jobs.

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. изменение дней в триггере задания

```
PS C:\> Get-JobTrigger -Name "DeployPackage"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Weekly          9/29/2011 12:00:00 AM  {Wednesday, Saturday}   True

The second command uses the Get-JobTrigger cmdlet to get the job trigger of the DeployPackage scheduled job. A pipeline operator (|) sends the trigger to the **Set-JobTrigger** cmdlet, which changes the job trigger so that it starts the DeployPackage job on Wednesdays and Sundays. The command uses the *Passthru* parameter to return the trigger after the change.
PS C:\> Get-JobTrigger -Name "DeployPackage" | Set-JobTrigger -DaysOfWeek "Wednesday", "Sunday" -Passthru
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Weekly          9/29/2011 12:00:00 AM  {Wednesday, Sunday}     True
```

В этом примере показано, как изменить дни в еженедельном триггере задания.

Первая команда использует командлет Get-JobTrigger для получения триггера задания запланированного задания DeployPackage.
Выходные данные показывают, что триггер запускает задание в полночь по средам и субботам.

Эта команда не является обязательной, она включена только для того, чтобы показать эффект изменения триггера.

### Пример 2. изменение типа триггера задания

```
PS C:\> Get-JobTrigger -Name "Inventory"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Daily           9/27/2011 11:00:00 PM                          True
2          AtStartup                                                      True

The second command uses the **Get-JobTrigger** cmdlet to get the *AtStartup* job trigger of the Inventory job. The command uses the *TriggerID* parameter to identify the job trigger. A pipeline operator (|) sends the job trigger to the **Set-JobTrigger** cmdlet, which changes it to a weekly job trigger that runs every four weeks on Monday at midnight. The command uses the *Passthru* parameter to return the trigger after the change.
PS C:\> Get-JobTrigger -Name "Inventory" -TriggerID 2 | Set-JobTrigger -Weekly -WeeksInterval 4 -DaysOfWeek Monday -At "12:00 AM"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Daily           9/27/2011 11:00:00 PM                          True
2          Weekly          10/31/2011 12:00:00 AM {Monday}                True
```

В этом примере показано, как изменить тип триггера задания, который запускает задание.
Команды в этом примере заменяют триггер задания AtStartup еженедельным триггером.

Первая команда использует командлет Get-JobTrigger, чтобы получить триггер задания для запланированного задания инвентаризации.
Выходные данные показывают, что задание имеет два триггера: ежедневный триггер и триггер *AtStartup* .

Эта команда не является обязательной, она включена только для того, чтобы показать эффект изменения триггера.

### Пример 3. изменение пользователя для триггера удаленного задания

```
PS C:\> Invoke-Command -ComputerName "Server01" -ScriptBlock {Get-ScheduledJob | Get-JobTrigger | Where-Object {$_.User} | Set-JobTrigger -User "Domain01/Admin02"}
```

Эта команда изменяет пользователя во всех триггерах заданий *AtLogon* запланированных заданий на компьютере Server01.

Команда использует командлет Invoke-Command для выполнения команды на компьютере Server01.

Удаленная команда начинается с Get-ScheduledJob команды, которая получает все запланированные задания на компьютере.
Запланированные задания передаются в командлет Get-JobTrigger, который получает Триггеры заданий запланированных заданий.
Каждый триггер задания имеет свойство JobDefinition, которое содержит запланированное задание, поэтому триггер остается связанным с запланированным заданием даже в случае его изменения.

Триггеры задания передаются в командлет Where-Object, который получает Триггеры заданий, имеющие свойство User.
Выбранные триггеры задания передаются в командлет **Set-JobTrigger** , который изменяет пользователя на Domain01\Admin02.

### Пример 4. изменение одного из множества триггеров заданий

```
PS C:\> Get-JobTrigger -Name "SecurityCheck"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Daily           4/24/2013 3:00:00 AM                           True
2          Weekly          4/24/2013 4:00:00 PM   {Sunday}                True
3          Once            4/24/2013 4:00:00 PM                           True

The second command uses the **TriggerID** parameter of the **Get-JobTrigger** cmdlet to get the *Once* trigger of the SecurityCheck scheduled job. The command pipes the trigger to the Format-List cmdlet, which displays all of the properties of the *Once* job trigger.The output shows that the trigger starts the job once every hour (RepetitionInterval = 1 hour) for one day (RepetitionDuration = 1 day).
PS C:\> Get-JobTrigger -Name "SecurityCheck" -TriggerID 3 | Format-List -Property *
At                 : 4/24/2012 4:00:00 PM
DaysOfWeek         :
Interval           : 1
Frequency          : Once
RandomDelay        : 00:00:00
RepetitionInterval : 01:00:00
RepetitionDuration : 1.00:00:00
User               :
Id                 : 3
Enabled            : True
JobDefinition      : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition

The third command changes the repetition interval of the job trigger from one hour to 90 minutes. The command does not return any output.
PS C:\> Get-JobTrigger -Name "SecurityCheck" -TriggerId 3 | Set-JobTrigger -RepetitionInterval (New-TimeSpan -Minutes 90)

The fourth command displays the effect of the change.The output shows that the trigger starts the job once every 90 minutes (RepetitionInterval = 1 hour, 30 minutes) for one day (RepetitionDuration = 1 day).
PS C:\> Get-JobTrigger -Name "SecurityCheck" -TriggerID 3 | Format-List -Property *
At                 : 4/24/2012 4:00:00 PM
DaysOfWeek         :
Interval           : 1
Frequency          : Once
RandomDelay        : 00:00:00
RepetitionInterval : 01:30:00
RepetitionDuration : 1.00:00:00
User               :
Id                 : 3
Enabled            : True
JobDefinition      : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

Команды в этом примере изменяют интервал повторения триггера задания *Once* для запланированного задания SecurityCheck с 60 минут на 90 минут.
Запланированное задание Секуритичекк имеет три триггера заданий, поэтому команды используют параметр *TriggerId* командлета Get-JobTrigger для обнаружения изменяемого триггера задания.

Первая команда использует командлет **Get-JobTrigger** для получения всех триггеров запланированного задания SecurityCheck.
Выходные данные, содержащие идентификаторы триггеров задания, показывают, что триггер задания *Once* имеет идентификатор 3.

## PARAMETERS

### -At
Запускает задание в указанный день и указанное время.
Введите объект **DateTime** , например, возвращаемый командлетом Get-Date, или строку, которую можно преобразовать в время, например "19 апреля, 2012 15:00", "12/31/2013 9:00 PM" или "03:00".

Если не указать элемент объекта **DateTime** , например секунды, этот элемент триггера задания не изменится.
Если исходный триггер задания не включал в себя объект **DateTime** и вы не пропускаете элемент, триггер задания создается с соответствующим элементом из текущих даты и времени.

При использовании параметра *Once* задайте в качестве значения параметра *At* определенную дату и определенное время.
Поскольку по умолчанию дата в объекте **DateTime** является текущей, при указании момента времени до текущего времени без явной даты триггер задания создается для времени в прошлом.

Объекты **DateTime** и строки, которые преобразуются в объекты **DateTime** , автоматически настраиваются для совместимости с форматами даты и времени, выбранными для локального компьютера в области и языка на панели управления.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AtLogOn
Запускает запланированное задание при входе указанных пользователей на компьютер.
Чтобы указать пользователя, используйте параметр *User* .

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

### -AtStartup
Запускает запланированное задание при запуске Windows.

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

### — Ежедневно
Указывает регулярное ежедневное расписание задания.
Используйте другие параметры из набора *ежедневных* параметров, чтобы указать сведения о расписании.

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

### -Дайсинтервал
Указывает количество дней между выполнениями для ежедневного расписания.
Например, при значении 3 запланированное задание запускается в следующие дни: 1, 4, 7 и т. д.
Значение по умолчанию — 1.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DaysOfWeek
Указывает дни недели, по которым выполняется запланированное задание.
Введите названия дней, например понедельник, четверг, целые числа 0-6, где 0 означает воскресенье, или звездочку ( \* ), представляющую каждый день.
Этот параметр необходим в наборе параметров Weekly.

Названия дней преобразуются в их целочисленные значения в триггере задания.
В команде заключайте название каждого дня в отдельные кавычки, например Monday, Tuesday.
Если заключить несколько названий дней в одну пару одинарных кавычек, соответствующие целые значения суммируются.
Например, Monday, Tuesday (1, 2) дает значение Wednesday (3).

```yaml
Type: System.DayOfWeek[]
Parameter Sets: (All)
Aliases:
Accepted values: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Указывает триггеры задания.
Введите переменную, содержащую объекты **ScheduledJobTrigger** , или введите команду или выражение, которое получает объекты **ScheduledJobTrigger** , такие как команда Get-JobTrigger.
Можно также передать объект **ScheduledJobTrigger** в командлет **Set-JobTrigger** .

При указании нескольких триггеров заданий **Set-JobTrigger** вносит одинаковые изменения во все триггеры задания.

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Один раз
Задает разовое (неповторяющееся) расписание.

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

### -PassThru
Возвращает изменившиеся триггеры задания.
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

### -Рандомделай
Включает случайную задержку, которая начинается в запланированное время начала, и задает максимальное значение этой задержки.
Длительность задержки задается для каждого запуска псевдослучайным образом и лежит в диапазоне от нуля до значения этого параметра.
Нулевое значение по умолчанию (00:00:00) отключает случайную задержку.

Введите объект TimeSpan, например возвращаемый командлетом New-TimeSpan, или введите значение в \<hours\> \<minutes\> формате:: \<seconds\> Format, которое автоматически преобразуется в объект TimeSpan.

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

### -RepeatIndefinitely
Этот параметр, который доступен, начиная с Windows PowerShell 4.0, устраняет необходимость в указании значения **TimeSpan.MaxValue** параметра *RepetitionDuration* для выполнения задания по расписанию в течение неопределенного времени.

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

### -RepetitionDuration
Повторяет задание до истечения заданного времени.
Частота повторения определяется значением параметра *RepetitionInterval* .
Например, если значение **RepetitionInterval** составляет 5 минут, а значение *RepetitionDuration* составляет 2 часа, задание запускается каждые пять минут в течение двух часов.

Введите объект TimeSpan, например, возвращаемый командлетом New-TimeSpan, или строку, которую можно преобразовать в объект TimeSpan, например "1:05:30".

Для бессрочного выполнения задания добавьте вместо этого параметр *RepeatIndefinitely* .

Чтобы остановить задание до истечения срока повторения триггера задания, задайте для **RepetitionDuration** нулевое значение (0).

Чтобы изменить длительность повторения или интервал повторения триггера задания *Once* , команда должна содержать оба параметра **RepetitionInterval** и **RepetitionDuration** .
Чтобы изменить длительность повторения или интервалы повторения других типов триггеров задания, команда должна содержать параметры *Once* , *At* , *RepetitionInterval* и *RepetitionDuration* .

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

### -Репетитионинтервал
Повторяет задание с определенным интервалом.
Например, если значение этого параметра равно 2 часам, задание активируется каждые два часа.
При использовании нулевого значения по умолчанию задание не запускается повторно.

Введите объект TimeSpan, например, возвращаемый командлетом New-TimeSpan, или строку, которую можно преобразовать в объект TimeSpan, например "1:05:30".

Чтобы изменить длительность повторения или интервал повторения триггера задания **Once** , команда должна содержать оба параметра **RepetitionInterval** и **RepetitionDuration** .
Чтобы изменить длительность повторения или интервалы повторения других типов триггеров задания, команда должна содержать параметры **Once** , **At** , **RepetitionInterval** и **RepetitionDuration** .

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

### -User
Указывает пользователей, которые активируют запуск *AtLogon* запланированного задания.
Введите имя пользователя в \<UserName\> \<Domain\Username\> формате или введите звездочку ( \* ) для представления всех пользователей.
По умолчанию заданы все пользователи.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — Еженедельно
Указывает регулярное еженедельное расписание задания.
Используйте другие параметры из набора *еженедельных* параметров, чтобы указать сведения о расписании.

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

### -Виксинтервал
Указывает количество недель между выполнениями для еженедельного расписания.
Например, при значении 3 запланированное задание запускается в следующие недели: 1, 4, 7 и т. д.
Значение по умолчанию — 1.

```yaml
Type: System.Int32
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

### Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger
Можно передать несколько триггеров задания в командлет **Set-JobTrigger** .

## Выходные данные

### Нет или Microsoft. PowerShell. ScheduledJob. ScheduledJobTrigger
При использовании параметра *Passthru* командлет **Set-JobTrigger** возвращает триггеры задания, которые были изменены.
В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

* Триггеры задания имеют свойство JobDefintion, которое связывает их с запланированным заданием. При изменении триггера запланированного заданий изменяется и это задание. Для применения измененного триггера к запланированному заданию не нужно использовать команду Set-ScheduledJob.

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
