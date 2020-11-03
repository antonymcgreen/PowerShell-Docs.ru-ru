---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/new-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-JobTrigger
ms.openlocfilehash: de49ab937c6f3a8187f5aecd6aafc81425b8cd00
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227377"
---
# New-JobTrigger

## Краткий обзор
Создает триггер задания для запланированного задания.

## SYNTAX

### Однократно (по умолчанию)

```
New-JobTrigger [-RandomDelay <TimeSpan>] -At <DateTime> [-Once] [-RepetitionInterval <TimeSpan>]
 [-RepetitionDuration <TimeSpan>] [-RepeatIndefinitely] [<CommonParameters>]
```

### Ежедневно

```
New-JobTrigger [-DaysInterval <Int32>] [-RandomDelay <TimeSpan>] -At <DateTime> [-Daily] [<CommonParameters>]
```

### Weekly (Еженедельно);

```
New-JobTrigger [-WeeksInterval <Int32>] [-RandomDelay <TimeSpan>] -At <DateTime> -DaysOfWeek <DayOfWeek[]>
 [-Weekly] [<CommonParameters>]
```

### AtStartup

```
New-JobTrigger [-RandomDelay <TimeSpan>] [-AtStartup] [<CommonParameters>]
```

### AtLogon

```
New-JobTrigger [-RandomDelay <TimeSpan>] [-User <String>] [-AtLogOn] [<CommonParameters>]
```

## DESCRIPTION
Командлет **New-JobTrigger** создает триггер задания, который запускает запланированное задание при однократном или повторяющемся расписании или при возникновении события.

Можно использовать объект **ScheduledJobTrigger** , возвращаемый **New-JobTrigger** , чтобы задать триггер задания для нового или существующего запланированного задания.
Можно также создать триггер задания с помощью командлета Get-JobTrigger, чтобы получить триггер задания для существующего запланированного задания или использовать значение хэш-таблицы для представления триггера задания.

При создании триггера задания проверьте значения по умолчанию для параметров, заданных в командлете New-ScheduledJobOption.
Эти свойства, у которых допустимые значения и значения по умолчанию совпадают с соответствующими параметрами в **Task Scheduler** , влияют на график и периодичность запланированных заданий.

**New-JobTrigger** — это одна из коллекций командлетов планирования заданий в модуле PSScheduledJob, который входит в состав Windows PowerShell.

Дополнительные сведения о запланированных заданиях см. в разделах описания в модуле PSScheduledJob.
Импортируйте модуль PSScheduledJob, а затем введите `Get-Help about_Scheduled*` или просмотрите статью about_Scheduled_Jobs.

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. однократное расписание

```
PS C:\> New-JobTrigger -Once -At "1/20/2012 3:00 AM"
```

Эта команда использует командлет **New-JobTrigger** , чтобы создать триггер задания, который запускает запланированное задание только один раз.
Значение параметра *At* представляет собой строку, которую Windows PowerShell преобразует в объект **DateTime** .
Значение параметра *At* включает в себя не только время, но и дату в явном виде.
Если дата была пропущена, триггер создается с текущей датой и временем 3:00, что с большой вероятностью относится ко времени в прошлом.

### Пример 2. ежедневное расписание

```
PS C:\> New-JobTrigger -Daily -At "4:15 AM" -DaysInterval 3
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
0          Daily           9/21/2012 4:15:00 AM                           True
```

Эта команда создает триггер задания, который запускает запланированное задание каждые 3 дня в 4:15.

Поскольку значение параметра *At* не включает в себя дату, в качестве значения даты в объекте **DateTime** используется текущая дата.
Если дата и время относятся к прошлому, запланированное задание запускается в следующий допустимый момент, который на 3 дня позднее значения параметра *At* .

### Пример 3. еженедельное расписание

```
PS C:\> New-JobTrigger -Weekly -DaysOfWeek Monday, Wednesday, Friday -At "23:00" -WeeksInterval 4
Id Frequency Time                  DaysOfWeek                  Enabled
-- --------- ----                  ----------                  -------
0  Weekly    9/21/2012 11:00:00 PM {Monday, Wednesday, Friday} True
```

Эта команда создает триггер задания, который запускает запланированное задание каждые 4 недели в понедельник, среду и пятницу в 23:00.

Можно также ввести значение параметра *DaysOfWeek* в целых числах, например `-DaysOfWeek 1, 5` .

### Пример 4. расписание входа

```
PS C:\> New-JobTrigger -AtLogOn -User Domain01\Admin01
```

Эта команда создает триггер задания, который запускает запланированное задание каждый раз, когда администратор домена выполняет вход в систему на компьютере.

### Пример 5. использование случайной задержки

```
PS C:\> New-JobTrigger -Daily -At 1:00 -RandomDelay 00:20:00
```

Эта команда создает триггер задания, который запускает запланированное задание каждый день в 1:00.
Команда использует параметр *RandomDelay* для указания максимальной задержки (до 20 минут).
В результате задание выполняется ежедневно в интервале с 1:00 до 1:20, изменяющемся псевдослучайным образом.

Случайную задержку можно использовать для выборки, балансировки нагрузки и других административных задач.
При задании значения задержки изучите действующие и значения по умолчанию для командлета New-ScheduledJobOption и согласуйте задержку с настройками параметров.

### Пример 6. Создание триггера задания для нового запланированного задания

```
The first command uses the **New-JobTrigger** cmdlet to create a job trigger that starts a job every Monday, Wednesday, and Friday at 12:01 AM. The command saves the job trigger in the $T variable.
PS C:\> $T = New-JobTrigger -Weekly -DaysOfWeek 1,3,5 -At 12:01AM


The second command uses the Register-ScheduledJob cmdlet to create a scheduled job that starts a job every Monday, Wednesday, and Friday at 12:01 AM. The value of the *Trigger* parameter is the trigger that is stored in the $T variable.
PS C:\> Register-ScheduledJob -Name Test-HelpFiles -FilePath C:\Scripts\Test-HelpFiles.ps1 -Trigger $T
```

Эти команды используют триггер задания для создания нового запланированного задания.

### Пример 7. добавление триггера задания в запланированное задание

```
PS C:\> Add-JobTrigger -Name SynchronizeApps -Trigger (New-JobTrigger -Daily -At 3:10AM)
```

В этом примере показано, как добавить триггер задания в существующее запланированное задания.
Для любого запланированного задания можно добавить несколько триггеров задания.

Команда использует командлет Add-JobTrigger, чтобы добавить триггер задания в запланированное задание Синчронизеаппс.
Значением параметра *Trigger* является команда **New-JobTrigger** , которая запускает задание каждый день в 3:10.

После завершения выполнения команды SynchronizeApps становится запланированным заданием, которое запускается во время, заданное триггером задания.

### Пример 8. Создание повторяющегося триггера задания

```
PS C:\> New-JobTrigger -Once -At "09/12/2013 1:00:00" -RepetitionInterval (New-TimeSpan -Hours 1) -RepetitionDuration (New-Timespan -Hours 48)
```

Эта команда создает триггер задания, который запускает задание каждые 60 минут в течение 48 часов, начиная с 12 сентября 2013 в 1:00 AM.

### Пример 9. Завершение повторяющегося триггера задания

```
PS C:\> Get-JobTrigger -Name SecurityCheck | Set-JobTrigger -RepetitionInterval 0:00 -RepetitionDuration 0:00
```

Эта команда принудительно останавливает задание SecurityCheck, которое активируется для запуска каждые 60 минут до истечения срока действия триггера задания.

Чтобы предотвратить повторение задания, команда использует Get-JobTrigger для получения триггера задания задания Секуритичекк и командлета Set-JobTrigger, чтобы изменить интервал повтора и длительность повтора для триггера задания на ноль (0).

### Пример 10. Создание триггера ежечасного задания

```
PS C:\> New-JobTrigger -Once -At "9/21/2012 0am" -RepetitionInterval (New-TimeSpan -Hour 12) -RepetitionDuration ([TimeSpan]::MaxValue)
```

Следующая команда создает триггер задания, который запускает запланированное задание каждые 12 часов в течение неопределенного периода времени.
Расписание начинается завтра (9/21/2012) в полночь (0:00).

## PARAMETERS

### -At
Запускает задание в указанный день и указанное время.
Введите объект **DateTime** , например, возвращаемый командлетом Get-Date, или строку, которую можно преобразовать в дату и время, например "19 апреля, 2012 15:00", "12/31" или "03:00".
Если не указать элемент даты, например год, дата в триггере имеет соответствующий элемент с учетом текущей даты.

При использовании параметра *Once* задайте в качестве значения параметра *At* дату и время в будущем.
Поскольку по умолчанию дата в объекте **DateTime** является текущей, при указании момента времени до текущего времени без явной даты триггер задания создается для времени в прошлом.

Объекты **DateTime** и строки, которые преобразуются в объекты **DateTime** , автоматически настраиваются для совместимости с форматами даты и времени, выбранными для локального компьютера в области и языка на панели управления.

```yaml
Type: System.DateTime
Parameter Sets: Once, Daily, Weekly
Aliases:

Required: True
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
Parameter Sets: AtLogon
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AtStartup
Запускает запланированное задание при запуске Windows.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AtStartup
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — Ежедневно
Указывает регулярное ежедневное расписание задания.
Используйте другие параметры из набора *ежедневных* параметров, чтобы указать сведения о расписании.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Daily
Aliases:

Required: True
Position: 0
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
Parameter Sets: Daily
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DaysOfWeek
Указывает дни недели, по которым выполняется запланированное задание.
Введите названия дней, например Monday, или целые числа от 0 до 6, где 0 — воскресенье.
Этот параметр необходим в наборе параметров Weekly.

Названия дней преобразуются в их целочисленные значения в триггере задания.
В команде заключайте название каждого дня в отдельные кавычки, например Monday, Tuesday.
Если заключить несколько названий дней в одну пару одинарных кавычек, соответствующие целые значения суммируются.
Например, Monday, Tuesday (1, 2) дает значение Wednesday (3).

```yaml
Type: System.DayOfWeek[]
Parameter Sets: Weekly
Aliases:
Accepted values: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Один раз
Задает разовое (неповторяющееся) или пользовательское расписание.
Чтобы создать повторяющееся расписание, используйте параметр *Once* с параметрами *RepetitionDuration* и *RepetitionInterval* .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Once
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Рандомделай
Включает случайную задержку, которая начинается в запланированное время начала, и задает максимальное значение этой задержки.
Длительность задержки задается для каждого запуска псевдослучайным образом и лежит в диапазоне от нуля до значения этого параметра.
Нулевое значение по умолчанию (00:00:00) отключает случайную задержку.

Введите объект TimeSpan, например возвращаемый командлетом New-TimeSpan, или введите значение в \<hours\> \<minutes\> формате:: \<seconds\> Format, которое автоматически преобразуется в объект **TimeSpan** .

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
Parameter Sets: Once
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
Например, если значение **RepetitionInterval** составляет 5 минут, а значение **RepetitionDuration** составляет 2 часа, задание запускается каждые пять минут в течение двух часов.

Введите объект TimeSpan, например, возвращаемый командлетом New-TimeSpan, или строку, которую можно преобразовать в объект TimeSpan, например "1:05:30".

Для бессрочного выполнения задания добавьте вместо этого параметр *RepeatIndefinitely* .

Чтобы прерывать задание до истечения срока действия триггера задания, используйте командлет Set-JobTrigger, чтобы установить значение *RepetitionDuration* равным нулю (0).

Этот параметр активен, только если в команде также используются параметры *Once* , *At* и *RepetitionInterval* .

```yaml
Type: System.TimeSpan
Parameter Sets: Once
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

Этот параметр активен, только если в команде также используются параметры *Once* , *At* и *RepetitionDuration* .

```yaml
Type: System.TimeSpan
Parameter Sets: Once
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
Parameter Sets: AtLogon
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — Еженедельно
Указывает регулярное еженедельное расписание задания.
Используйте другие параметры в наборе параметров Weekly, чтобы указать сведения о расписании.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Weekly
Aliases:

Required: True
Position: 0
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
Parameter Sets: Weekly
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

### Нет
В этот командлет нельзя передать входные данные.

## Выходные данные

### Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger

## ПРИМЕЧАНИЯ

* Триггеры задания не сохраняются на диск. Однако запланированные задания сохраняются на диск, и вы можете использовать Get-JobTrigger, чтобы получить триггер задания для любого запланированного задания.
* **New-JobTrigger** не препятствует созданию триггера задания, который не будет выполнять запланированное задание, например одноразовый триггер для даты в прошлом.
* Командлет Register-ScheduledJob принимает объект ScheduledJobTrigger, например, возвращаемый командлетами **New-JobTrigger** или Get-JobTrigger, или хэш-таблицу со значениями триггера.

  Чтобы отправить хэш-таблицу, используйте следующие ключи.

  `@{Frequency="Once" (or Daily, Weekly, AtStartup, AtLogon);At="3am"` (или любая допустимая строка времени); `DaysOfWeek="Monday", "Wednesday"` (или любое сочетание названий дней); `Interval=2` (или любой допустимый интервал частоты); `RandomDelay="30minutes"` (или любая допустимая строка TimeSpan); `User="Domain1\User01` (или любой допустимый пользователь; используется только со значением частоты *AtLogon* )}

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
