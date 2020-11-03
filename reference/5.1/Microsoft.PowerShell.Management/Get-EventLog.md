---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 3/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-EventLog
ms.openlocfilehash: ab1a97dc3c78bbfdcc239fd573ef3b1f839e2b21
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228398"
---
# Get-EventLog

## Краткий обзор
Возвращает события в журнале событий или список журналов событий на локальном компьютере или на удаленных компьютерах.

## SYNTAX

### "Автозначение" (по умолчанию)

```
Get-EventLog [-LogName] <String> [-ComputerName <String[]>] [-Newest <Int32>] [-After <DateTime>]
 [-Before <DateTime>] [-UserName <String[]>] [[-InstanceId] <Int64[]>] [-Index <Int32[]>]
 [-EntryType <String[]>] [-Source <String[]>] [-Message <String>] [-AsBaseObject]
 [<CommonParameters>]
```

### Список

```
Get-EventLog [-ComputerName <String[]>] [-List] [-AsString] [<CommonParameters>]
```

## DESCRIPTION

`Get-EventLog`Командлет получает события и журналы событий с локальных и удаленных компьютеров. По умолчанию `Get-EventLog` получает журналы с локального компьютера. Чтобы получить журналы с удаленных компьютеров, используйте параметр **ComputerName** .

`Get-EventLog`Для поиска событий можно использовать параметры и значения свойств. Командлет возвращает события, соответствующие указанным значениям свойств.

Командлеты PowerShell, которые содержат `EventLog` существительное, работают только с классическими журналами событий Windows, такими как приложение, система или безопасность. Для получения журналов, использующих технологию журнала событий Windows в Windows Vista и более поздних версиях Windows, используйте `Get-WinEvent` .

> [!NOTE]
> `Get-EventLog` использует API Win32, который является устаревшим. Результаты могут быть неточными. `Get-WinEvent`Вместо этого используйте командлет.

## Примеры

### Пример 1. получение журналов событий на локальном компьютере

В этом примере отображается список журналов событий, доступных на локальном компьютере. Имена в столбце log используются с параметром "имя **журнала",** чтобы указать, в каком журнале выполняется поиск событий.

```powershell
Get-EventLog -List
```

```Output
Max(K)   Retain   OverflowAction      Entries  Log
------   ------   --------------      -------  ---
15,168        0   OverwriteAsNeeded   20,792   Application
15,168        0   OverwriteAsNeeded   12,559   System
15,360        0   OverwriteAsNeeded   11,173   Windows PowerShell
```

`Get-EventLog`Командлет использует параметр **List** для вывода доступных журналов.

### Пример 2. Получение последних записей из журнала событий на локальном компьютере

Этот пример получает последние записи из журнала системных событий.

```powershell
Get-EventLog -LogName System -Newest 5
```

```Output
Index   Time          EntryType    Source              InstanceID   Message
-----   ----          ---------    ------              ----------   -------
13820   Jan 17 19:16  Error        DCOM                     10016   The description for Event...
13819   Jan 17 19:08  Error        DCOM                     10016   The description for Event...
13818   Jan 17 19:06  Information  Service Control...  1073748864   The start type of the Back...
13817   Jan 17 19:05  Error        DCOM                     10016   The description for Event...
13815   Jan 17 19:03  Information  Microsoft-Windows...        35   The time service is now sync...
```

`Get-EventLog`Командлет использует параметр " **/l** " для указания журнала системных событий. **Последний** параметр возвращает пять последних событий.

### Пример 3. Поиск всех источников для определенного числа записей в журнале событий

В этом примере показано, как найти все источники, которые включены в 1000 последних записей в журнале системных событий.

```powershell
$Events = Get-EventLog -LogName System -Newest 1000
$Events | Group-Object -Property Source -NoElement | Sort-Object -Property Count -Descending
```

```Output
Count   Name
-----   ----
  110   DCOM
   65   Service Control Manager
   51   Microsoft-Windows-Kern...
   14   EventLog
   14   BTHUSB
   13   Win32k
```

`Get-EventLog`Для указания системного журнала командлет использует параметр " **/l** ". Последний **параметр выбирает** 1000 последних событий. Объекты событий хранятся в `$Events` переменной. `$Events`Объекты отправляются по конвейеру в `Group-Object` командлет.
`Group-Object` использует параметр **Property** для группирования объектов по источнику и подсчитывает количество объектов для каждого источника. Параметр **элемента** удаления удаляет члены группы из выходных данных.
`Sort-Object`Командлет использует параметр **Property** для сортировки по количеству имен источников.
Параметр **сортировки** сортирует список в порядке по числу от самого высокого до самого низкого.

### Пример 4. получение событий ошибки из определенного журнала событий

Этот пример получает события ошибки из журнала системных событий.

```powershell
Get-EventLog -LogName System -EntryType Error
```

```Output
Index Time          EntryType   Source  InstanceID Message
----- ----          ---------   ------  ---------- -------
13296 Jan 16 13:53  Error       DCOM    10016 The description for Event ID '10016' in Source...
13291 Jan 16 13:51  Error       DCOM    10016 The description for Event ID '10016' in Source...
13245 Jan 16 11:45  Error       DCOM    10016 The description for Event ID '10016' in Source...
13230 Jan 16 11:07  Error       DCOM    10016 The description for Event ID '10016' in Source...
```

`Get-EventLog`Для указания системного журнала командлет использует параметр " **/l** ". Параметр **EntryType** фильтрует события, чтобы отображались только события ошибок.

### Пример 5. получение событий из журнала событий с идентификатором InstanceId и исходным значением

Этот пример получает события из системного журнала для конкретного InstanceId и источника.

```powershell
Get-EventLog -LogName System -InstanceId 10016 -Source DCOM
```

```Output
Index Time          EntryType  Source  InstanceID  Message
----- ----          ---------  ------  ----------  -------
13245 Jan 16 11:45  Error      DCOM         10016  The description for Event ID '10016' in Source...
13230 Jan 16 11:07  Error      DCOM         10016  The description for Event ID '10016' in Source...
13219 Jan 16 10:00  Error      DCOM         10016  The description for Event ID '10016' in Source...
```

`Get-EventLog`Для указания системного журнала командлет использует параметр " **/l** ". Параметр **InstanceId** выбирает события с указанным идентификатором экземпляра. Параметр **Source** указывает свойство события.

### Пример 6. получение событий с нескольких компьютеров

Эта команда получает события из журнала системных событий на трех компьютерах: Server01, Server02 и Server03.

```powershell
Get-EventLog -LogName System -ComputerName Server01, Server02, Server03
```

`Get-EventLog`Для указания системного журнала командлет использует параметр " **/l** ". Параметр **ComputerName** использует строку с разделителями-запятыми для перечисления компьютеров, с которых необходимо получить журналы событий.

### Пример 7. получение всех событий, содержащих определенное слово в сообщении

Эта команда возвращает все события в журнале системных событий, содержащие определенное слово в сообщении о событии. Возможно, значение указанного параметра **сообщения** включено в содержимое сообщения, но не отображается в консоли PowerShell.

```powershell
Get-EventLog -LogName System -Message *description*
```

```Output
Index Time          EntryType   Source       InstanceID   Message
----- ----          ---------   ------       ----------   -------
13821 Jan 17 19:17  Error       DCOM              10016   The description for Event ID '10016'...
13820 Jan 17 19:16  Error       DCOM              10016   The description for Event ID '10016'...
13819 Jan 17 19:08  Error       DCOM              10016   The description for Event ID '10016'...
```

`Get-EventLog`Командлет использует параметр " **/l** " для указания журнала системных событий. Параметр **Message** указывает слово для поиска в поле сообщения каждого события.

### Пример 8. Отображение значений свойств события

В этом примере показано, как отобразить все свойства и значения события.

```powershell
$A = Get-EventLog -LogName System -Newest 1
$A | Select-Object -Property *
```

```Output
EventID            : 10016
MachineName        : localhost
Data               : {}
Index              : 13821
Category           : (0)
CategoryNumber     : 0
EntryType          : Error
Message            : The description for Event ID '10016' in Source 'DCOM'...
Source             : DCOM
ReplacementStrings : {Local,...}
InstanceId         : 10016
TimeGenerated      : 1/17/2019 19:17:23
TimeWritten        : 1/17/2019 19:17:23
UserName           : username
Site               :
Container          :
```

`Get-EventLog`Командлет использует параметр " **/l** " для указания журнала системных событий. Последний **параметр выбирает** самый последний объект события. Объект хранится в `$A` переменной. Объект в `$A` переменной отправляется в командлет по конвейеру `Select-Object` .
`Select-Object` использует параметр **Property** со звездочкой ( `*` ) для выбора всех свойств объекта.

### Пример 9. получение событий из журнала событий с помощью источника и идентификатора события

Этот пример получает события для указанного источника и идентификатора события.

```powershell
Get-EventLog -LogName Application -Source Outlook | Where-Object {$_.EventID -eq 63} |
              Select-Object -Property Source, EventID, InstanceId, Message
```

```Output
Source   EventID   InstanceId   Message
------   -------   ----------   -------
Outlook       63   1073741887   The Exchange web service request succeeded.
Outlook       63   1073741887   Outlook detected a change notification.
Outlook       63   1073741887   The Exchange web service request succeeded.
```

`Get-EventLog`Командлет использует параметр " **/l** " для указания журнала событий приложения. Параметр **Source** указывает имя приложения, Outlook. Объекты отправляются по конвейеру в `Where-Object` командлет. Для каждого объекта в конвейере `Where-Object` командлет использует переменную `$_.EventID` для сравнения свойства идентификатора события с указанным значением. Объекты отправляются по конвейеру в `Select-Object` командлет. `Select-Object` использует параметр **Property** для выбора свойств, отображаемых в консоли PowerShell.

### Пример 10. получение событий и группировка по свойству

```powershell
Get-EventLog -LogName System -UserName NT* | Group-Object -Property UserName -NoElement |
              Select-Object -Property Count, Name
```

```Output
Count  Name
-----  ----
6031   NT AUTHORITY\SYSTEM
  42   NT AUTHORITY\LOCAL SERVICE
   4   NT AUTHORITY\NETWORK SERVICE
```

`Get-EventLog`Для указания системного журнала командлет использует параметр " **/l** ". Параметр **username** содержит `*` подстановочный знак звездочки () для указания части имени пользователя. Объекты событий отправляются по конвейеру в `Group-Object` командлет. `Group-Object` использует параметр **Property** , чтобы указать, что свойство **username** используется для группирования объектов и подсчитывает количество объектов для каждого имени пользователя. Параметр **элемента** удаления удаляет члены группы из выходных данных. Объекты отправляются по конвейеру в `Select-Object` командлет.
`Select-Object` использует параметр **Property** для выбора свойств, отображаемых в консоли PowerShell.

### Пример 11. получение событий, произошедших в указанный диапазон дат и времени

Этот пример возвращает события ошибки из журнала системных событий для указанного диапазона даты и времени. Параметры **Before** и **After** задают диапазон дат и времени, но исключаются из выходных данных.

```powershell
$Begin = Get-Date -Date '1/17/2019 08:00:00'
$End = Get-Date -Date '1/17/2019 17:00:00'
Get-EventLog -LogName System -EntryType Error -After $Begin -Before $End
```

```Output
Index Time          EntryType   Source   InstanceID  Message
----- ----          ---------   ------   ----------  -------
13821 Jan 17 13:40  Error       DCOM          10016  The description for Event ID...
13820 Jan 17 13:11  Error       DCOM          10016  The description for Event ID...
...
12372 Jan 17 10:08  Error       DCOM          10016  The description for Event ID...
12371 Jan 17 09:04  Error       DCOM          10016  The description for Event ID...
```

`Get-Date`Командлет использует параметр **Date** для указания даты и времени. Объекты **DateTime** хранятся в `$Begin` `$End` переменных и. `Get-EventLog`Для указания системного журнала командлет использует параметр " **/l** ". Параметр **EntryType** указывает тип события ошибки. Диапазон дат и времени задается параметром **After** и `$Begin` переменной и параметром **Before** и `$End` переменной.

## PARAMETERS

### -After

Возвращает события, произошедшие после указанной даты и времени. Дата и время параметра **After** исключаются из выходных данных. Введите объект **DateTime** , например значение, возвращаемое `Get-Date` командлетом.

```yaml
Type: System.DateTime
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Асбасеобжект

Указывает, что этот командлет возвращает стандартный объект **System. Diagnostics. EventLogEntry** для каждого события. Без этого параметра `Get-EventLog` возвращает расширенный объект **PSObject** с дополнительными свойствами **EventLogName** , **Source** и **InstanceId** .

Чтобы увидеть результат этого параметра, передаем события в `Get-Member` командлет и изучите значение **TypeName** в результате.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsString

Указывает, что этот командлет возвращает выходные данные в виде строк, а не объектов.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — До

Возвращает события, произошедшие до указанной даты и времени. Дата и время, указанные в параметре **Before** , исключаются из выходных данных. Введите объект **DateTime** , например значение, возвращаемое `Get-Date` командлетом.

```yaml
Type: System.DateTime
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Этот параметр указывает имя NetBIOS удаленного компьютера, IP-адрес или полное доменное имя (FQDN).

Если параметр **ComputerName** не указан, `Get-EventLog` по умолчанию используется локальный компьютер. Параметр также принимает точку (), `.` чтобы указать локальный компьютер.

Параметр **ComputerName** не зависит от удаленного взаимодействия Windows PowerShell. Можно использовать `Get-EventLog` с параметром **ComputerName** , даже если компьютер не настроен для выполнения удаленных команд.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EntryType

Указывает тип записи для событий, которые получает этот командлет, в виде массива строк.

Допустимые значения для этого параметра:

- Ошибка
- Сведения
- FailureAudit
- SuccessAudit
- Предупреждение

```yaml
Type: System.String[]
Parameter Sets: LogName
Aliases: ET
Accepted values: Error, Information, FailureAudit, SuccessAudit, Warning

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Index

Указывает значения индекса, которые необходимо получить из журнала событий. Параметр принимает строку значений с разделителями-запятыми.

```yaml
Type: System.Int32[]
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceId

Указывает идентификаторы экземпляров, которые необходимо получить из журнала событий. Параметр принимает строку значений с разделителями-запятыми.

```yaml
Type: System.Int64[]
Parameter Sets: LogName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -List

Отображает список журналов событий на компьютере.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogName

Указывает имя одного журнала событий. Чтобы найти имена журналов, используйте `Get-EventLog -List` . Можно использовать подстановочные знаки. Этот параметр обязателен.

```yaml
Type: System.String
Parameter Sets: LogName
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Message

Указывает строку в сообщении о событии. Этот параметр можно использовать для поиска сообщений, содержащих определенные слова или фразы. Разрешено использовать подстановочные знаки.

```yaml
Type: System.String
Parameter Sets: LogName
Aliases: MSG

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### — Самый новый

Начинается с самых новых событий и получает указанное число событий. Например, требуется указать количество событий `-Newest 100` . Указывает максимальное число возвращаемых событий.

```yaml
Type: System.Int32
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source

Указывает в виде массива строк источники, записанные в журнал, который получает этот командлет. Разрешено использовать подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: LogName
Aliases: ABO

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -UserName

Указывает в виде строкового массива имена пользователей, связанные с событиями. Введите имена или шаблоны имен, например `User01` , `User*` или `Domain01\User*` . Разрешено использовать подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

Вы не можете передать входные данные в `Get-EventLog` .

## Выходные данные

### System. Diagnostics. EventLogEntry. System. Diagnostics. EventLog. System.String

Если указан параметр " **/l** ", выходные данные представляют собой коллекцию объектов **System. Diagnostics. EventLogEntry** .

Если указан только параметр **List** , то выходные данные представляют собой коллекцию объектов **System. Diagnostics. EventLog** .

Если указаны оба параметра **List** и **AsString** , то выходные данные представляют собой коллекцию объектов **System. String** .

## ПРИМЕЧАНИЯ

Командлеты `Get-EventLog` и `Get-WinEvent` не поддерживаются в среда предустановки Windows (Windows PE).

## Связанные ссылки

[Clear-EventLog](Clear-EventLog.md)

[Get-WinEvent](../Microsoft.PowerShell.Diagnostics/Get-WinEvent.md)

[Group-Object](../Microsoft.PowerShell.Utility/Group-Object.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Select-Object](../Microsoft.PowerShell.Utility/Select-Object.md)

[Show-EventLog](Show-EventLog.md)

[Write-EventLog](Write-EventLog.md)
