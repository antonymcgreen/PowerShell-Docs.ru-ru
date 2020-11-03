---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 11/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/get-winevent?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WinEvent
ms.openlocfilehash: 72455745d4523a33cac4ccca5af9c8be29ac9e37
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229222"
---
# Get-WinEvent

## Краткий обзор
Получает события из журналов событий и файлов журналов трассировки событий на локальных и удаленных компьютерах.

## SYNTAX

### GetLogSet (по умолчанию)

```
Get-WinEvent [[-LogName] <String[]>] [-MaxEvents <Int64>] [-ComputerName <String>]
 [-Credential <PSCredential>] [-FilterXPath <String>] [-Force] [-Oldest] [<CommonParameters>]
```

### ListLogSet

```
Get-WinEvent [-ListLog] <String[]> [-ComputerName <String>] [-Credential <PSCredential>] [-Force]
 [<CommonParameters>]
```

### ListProviderSet

```
Get-WinEvent [-ListProvider] <String[]> [-ComputerName <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### GetProviderSet

```
Get-WinEvent [-ProviderName] <String[]> [-MaxEvents <Int64>] [-ComputerName <String>]
 [-Credential <PSCredential>] [-FilterXPath <String>] [-Force] [-Oldest] [<CommonParameters>]
```

### FileSet

```
Get-WinEvent [-Path] <String[]> [-MaxEvents <Int64>] [-Credential <PSCredential>]
 [-FilterXPath <String>] [-Oldest] [<CommonParameters>]
```

### HashQuerySet

```
Get-WinEvent [-MaxEvents <Int64>] [-ComputerName <String>] [-Credential <PSCredential>]
 [-FilterHashtable] <Hashtable[]> [-Force] [-Oldest] [<CommonParameters>]
```

### XmlQuerySet

```
Get-WinEvent [-MaxEvents <Int64>] [-ComputerName <String>] [-Credential <PSCredential>]
 [-FilterXml] <XmlDocument> [-Oldest] [<CommonParameters>]
```

## DESCRIPTION

`Get-WinEvent`Командлет получает события из журналов событий, включая классические журналы, такие как журналы **системы** и **приложений** . Командлет получает данные из журналов событий, созданных с помощью технологии журнала событий Windows, представленной в Windows Vista. И события в файлах журнала, создаваемых функцией **трассировки событий для Windows (ETW)**. По умолчанию `Get-WinEvent` возвращает сведения о событиях в порядке от новых к старым.

`Get-WinEvent` Список журналов событий и поставщиков журналов событий. Чтобы прервать выполнение команды, нажмите клавиши <kbd>CTRL</kbd> + <kbd>C</kbd>. События можно получить из выбранных журналов или из журналов, созданных выбранными поставщиками событий. Кроме того, можно объединять события из нескольких источников в одну команду.
`Get-WinEvent` позволяет фильтровать события с помощью запросов XPath, структурированных XML-запросов и запросов хэш-таблиц.

Если вы не используете PowerShell с правами администратора, могут появиться сообщения об ошибках, которые не позволяют получить сведения о журнале.

## Примеры

### Пример 1. получение всех журналов с локального компьютера

Эта команда возвращает все журналы событий на локальном компьютере. Журналы перечислены в порядке `Get-WinEvent` их получения. Сначала извлекаются классические журналы, а затем новые журналы событий Windows.
**RecordCount** журнала может иметь значение null, которое пустое или равно нулю.

```powershell
Get-WinEvent -ListLog *
```

```Output
LogMode   MaximumSizeInBytes RecordCount LogName
-------   ------------------ ----------- -------
Circular            15532032       14500 Application
Circular             1052672         117 Azure Information Protection
Circular             1052672        3015 CxAudioSvcLog
Circular            20971520             ForwardedEvents
Circular            20971520           0 HardwareEvents
```

`Get-WinEvent`Командлет получает данные журнала с компьютера. Параметр **листлог** использует `*` подстановочный знак звездочки () для вывода сведений о каждом журнале.

### Пример 2. получение классического журнала установки

Эта команда возвращает объект **EventLogConfiguration** , представляющий Классический журнал **установки** . Объект содержит сведения о журнале, такие как размер файла, поставщик, путь к файлу и включение журнала.

```powershell
Get-WinEvent -ListLog Setup | Format-List -Property *
```

```Output
FileSize                       : 69632
IsLogFull                      : False
LastAccessTime                 : 3/13/2019 09:41:46
LastWriteTime                  : 3/13/2019 09:41:46
OldestRecordNumber             : 1
RecordCount                    : 23
LogName                        : Setup
LogType                        : Operational
LogIsolation                   : Application
IsEnabled                      : True
IsClassicLog                   : False
SecurityDescriptor             : O:BAG:SYD: ...
LogFilePath                    : %SystemRoot%\System32\Winevt\Logs\Setup.evtx
MaximumSizeInBytes             : 1052672
LogMode                        : Circular
OwningProviderName             : Microsoft-Windows-Eventlog
ProviderNames                  : {Microsoft-Windows-WUSA, Microsoft-Windows-ActionQueue...
ProviderLevel                  :
ProviderKeywords               :
ProviderBufferSize             : 64
ProviderMinimumNumberOfBuffers : 0
ProviderMaximumNumberOfBuffers : 64
ProviderLatency                : 1000
ProviderControlGuid            :
```

`Get-WinEvent`Командлет использует параметр **листлог** для указания журнала **установки** . Объект отправляется по конвейеру в `Format-List` командлет. `Format-List` использует параметр **Property** с `*` подстановочным знаком звездочки () для вывода каждого свойства.

### Пример 3. получение журналов событий с сервера

Эта команда возвращает только журналы событий на локальном компьютере, которые содержат события. **RecordCount** журнала может иметь значение null или равняться нулю. В примере используется `$_` переменная. Дополнительные сведения см. в разделе [about_Automatic_Variables](../Microsoft.PowerShell.Core/about/about_automatic_variables.md).

```powershell
Get-WinEvent -ListLog * -ComputerName localhost | Where-Object { $_.RecordCount }
```

```Output
LogMode   MaximumSizeInBytes RecordCount LogName
-------   ------------------ ----------- -------
Circular            15532032       14546 Application
Circular             1052672         117 Azure Information Protection
Circular             1052672        2990 CxAudioSvcLog
Circular             1052672           9 MSFTVPN Setup
Circular             1052672         282 OAlerts
```

`Get-WinEvent`Командлет получает данные журнала с компьютера. Параметр **листлог** использует `*` подстановочный знак звездочки () для вывода сведений о каждом журнале. Параметр **ComputerName** задает получение журналов с локального компьютера, **localhost**. Объекты отправляются по конвейеру в `Where-Object` командлет. `Where-Object` использует `$_.RecordCount` для возврата только журналов, содержащих данные. `$_` переменная, представляющая текущий объект в конвейере. **RecordCount** — это свойство объекта со значением, отличным от NULL.

### Пример 4. получение журналов событий с нескольких серверов

Этот пример получает объекты, представляющие журналы событий **приложений** на трех компьютерах: Server01, Server02 и Server03. Используется ключевое слово **foreach** , так как параметр **ComputerName** принимает только одно значение. Дополнительные сведения см. в разделе [about_Foreach](../Microsoft.PowerShell.Core/about/about_Foreach.md).

```powershell
$S = 'Server01', 'Server02', 'Server03'
ForEach ($Server in $S) {
  Get-WinEvent -ListLog Application -ComputerName $Server |
    Select-Object LogMode, MaximumSizeInBytes, RecordCount, LogName,
      @{name='ComputerName'; expression={$Server}} |
    Format-Table -AutoSize
}
```

```Output
 LogMode MaximumSizeInBytes RecordCount LogName     ComputerName
 ------- ------------------ ----------- -------     ------------
Circular           15532032       14577 Application Server01
Circular           15532032        9689 Application Server02
Circular           15532032        5309 Application Server03
```

Переменная `$S` хранит имена трех серверов: **Server01** , **Server02** и **Server03**. Оператор **foreach** использует цикл для обработки каждого сервера `($Server in $S)` . Блок скрипта в фигурных скобках ( `{ }` ) выполняет `Get-WinEvent` команду. Параметр **листлог** указывает журнал **приложения** . Параметр **ComputerName** использует переменную `$Server` для получения сведений журнала с каждого сервера.

Объекты отправляются по конвейеру в `Select-Object` командлет. `Select-Object` Получает свойства **LogMode** , **максимумсизеинбитес** , **RecordCount** , имя **, а** также использует вычисляемое выражение для вывода имени **компьютера** с помощью `$Server` переменной. Объекты отправляются по конвейеру в `Format-Table` командлет для вывода выходных данных в консоли PowerShell. Параметр **AutoSize** форматирует выходные данные в соответствии с экраном экрана.

### Пример 5. получение поставщиков журнала событий и имен журналов

Эта команда возвращает поставщиков журналов событий и журналы, в которые они записываются.

```powershell
Get-WinEvent -ListProvider *
```

```Output
Name     : .NET Runtime
LogLinks : {Application}
Opcodes  : {}
Tasks    : {}

Name     : .NET Runtime Optimization Service
LogLinks : {Application}
Opcodes  : {}
Tasks    : {}
```

`Get-WinEvent`Командлет получает данные журнала с компьютера. Параметр **листпровидер** использует `*` подстановочный знак звездочки () для вывода сведений о каждом поставщике. В выходных данных **имя** является поставщиком, а **логлинкс** — журналом, в который записывает поставщик.

### Пример 6. получение всех поставщиков журнала событий, записывающих записи в конкретный журнал

Эта команда возвращает всех поставщиков, которые записывают в журнал **приложения** .

```powershell
(Get-WinEvent -ListLog Application).ProviderNames
```

```Output
.NET Runtime
.NET Runtime Optimization Service
Application
Application Error
Application Hang
Application Management
```

`Get-WinEvent`Командлет получает данные журнала с компьютера. Параметр **листлог** использует **приложение** для получения объектов для этого журнала. **Провидернамес** — это свойство объекта, в котором отображаются поставщики, записывающие записи в журнал **приложения** .

### Пример 7. Получение имен регистраторов событий, содержащих определенную строку

Эта команда получает регистраторы журнала событий с именами, которые содержат определенную строку в имени поставщика.

```powershell
Get-WinEvent -ListProvider *Policy*
```

```Output
Name     : Group Policy Applications
LogLinks : {Application}
Opcodes  : {}
Tasks    : {}

Name     : Group Policy Client
LogLinks : {Application}
Opcodes  : {}
Tasks    : {}

Name     : Group Policy Data Sources
LogLinks : {Application}
Opcodes  : {}
Tasks    : {}
```

`Get-WinEvent`Командлет получает данные журнала с компьютера. Параметр **листпровидер** использует `*` подстановочный знак звездочки () для поиска **политики** в любом месте имени поставщика.

### Пример 8. получение идентификаторов событий, создаваемых поставщиком событий

Эта команда выводит список идентификаторов событий, создаваемых поставщиком событий **Microsoft-Windows-GroupPolicy** вместе с описанием события.

```powershell
(Get-WinEvent -ListProvider Microsoft-Windows-GroupPolicy).Events | Format-Table Id, Description
```

```Output
  Id  Description
  --  -----------
1500  The Group Policy settings for the computer were processed successfully...
1501  The Group Policy settings for the user were processed successfully...
4115  Group Policy Service started.
4116  Started the Group Policy service initialization phase.
4117  Group Policy Session started.
```

`Get-WinEvent`Командлет получает данные журнала с компьютера. Параметр **листпровидер** указывает поставщик, **Microsoft-Windows-GroupPolicy**. Выражение заключено в круглые скобки и использует свойство **Events** для получения объектов. Объекты отправляются по конвейеру в `Format-Table` командлет. `Format-Table` Отображает **идентификатор** и **Описание** объектов событий.

### Пример 9. Получение сведений о журнале из свойств объекта события

В этом примере показано, как получить сведения о содержимом журнала с помощью свойств объекта события.
Объекты событий хранятся в переменной, а затем группируются и подсчитываются по **идентификатору события** и **уровню**.

```powershell
$Event = Get-WinEvent -LogName 'Windows PowerShell'
$Event.Count
$Event | Group-Object -Property Id -NoElement | Sort-Object -Property Count -Descending
$Event | Group-Object -Property LevelDisplayName -NoElement
```

```Output
195

Count  Name
-----  ----
  147  600
   22  400
   21  601
    3  403
    2  103

Count  Name
-----  ----
    2  Warning
  193  Information
```

`Get-WinEvent`Для указания журнала событий **Windows PowerShell** командлет использует параметр " **/l** ". Объекты событий хранятся в `$Event` переменной. Свойство **Count** объекта `$Event` показывает общее число зарегистрированных событий.

`$Event`Переменная отправляется в командлет по конвейеру `Group-Object` . `Group-Object` использует параметр **Property** для задания свойства **ID** и подсчитывает объекты по значению идентификатора события. Параметр **элемента** удаления удаляет другие свойства из выходных данных объектов. Сгруппированные объекты отправляются по конвейеру в `Sort-Object` командлет. `Sort-Object` использует параметр **Property** для сортировки объектов по **количеству**. Параметр **Descending** отображает выходные данные по количеству от самого высокого до самого низкого. В выходных данных столбец **Count** содержит общее число каждого события. В столбце **имя** содержатся идентификационные номера сгруппированных событий.

`$Event`Переменная отправляется в командлет по конвейеру `Group-Object` . `Group-Object` использует параметр **Property** для указания свойства **левелдисплайнаме** и подсчитывает объекты по **левелдисплайнаме**. Объекты группируются по уровням, например **предупреждениям** и **сведениям**.
Параметр **элемента** не удаляет другие свойства из выходных данных. В выходных данных столбец **Count** содержит общее число каждого события. Столбец **Name** содержит сгруппированные **левелдисплайнаме**.

### Пример 10. получение событий ошибки, в имени которых указана строка

В этом примере используется строка имен журналов с разделителями-запятыми. Выходные данные группируются по уровню, например ошибке или предупреждению, и имени журнала.

```powershell
Get-WinEvent -LogName *PowerShell*, Microsoft-Windows-Kernel-WHEA* |
  Group-Object -Property LevelDisplayName, LogName -NoElement |
    Format-Table -AutoSize
```

```Output
Count  Name
-----  ----
    1  Error, PowerShellCore/Operational
   26  Information, Microsoft-Windows-Kernel-WHEA/Operational
  488  Information, Microsoft-Windows-PowerShell/Operational
   77  Information, PowerShellCore/Operational
 9835  Information, Windows PowerShell
   19  Verbose, PowerShellCore/Operational
  444  Warning, Microsoft-Windows-PowerShell/Operational
  512  Warning, PowerShellCore/Operational
```

`Get-WinEvent`Командлет получает данные журнала с компьютера. Параметр **"имя** журнала" использует строку с разделителями-запятыми с `*` подстановочным знаком звездочки () для указания имен журналов. Объекты отправляются по конвейеру в `Group-Object` командлет. `Group-Object` использует параметр **Property** для группирования объектов по **левелдисплайнаме** **и в** качестве значения параметра. Параметр **элемента** не удаляет другие свойства из выходных данных. Сгруппированные объекты отправляются по конвейеру в `Format-Table` командлет. `Format-Table` использует параметр **AutoSize** для форматирования столбцов. Столбец **Count** содержит общее число каждого события. Столбец **Name** содержит сгруппированные **левелдисплайнаме** и имя. **LogName**

### Пример 11. получение событий из архивного журнала событий

`Get-WinEvent` может получать сведения о событиях из сохраненных файлов журнала. В этом примере используется архивный журнал PowerShell, хранящийся на локальном компьютере.

```powershell
Get-WinEvent -Path 'C:\Test\Windows PowerShell.evtx'
```

```Output
   ProviderName: PowerShell

TimeCreated              Id LevelDisplayName  Message
-----------              -- ----------------  -------
3/15/2019 13:54:13      403 Information       Engine state is changed from Available to Stopped...
3/15/2019 13:54:13      400 Information       Engine state is changed from None to Available...
3/15/2019 13:54:13      600 Information       Provider "Variable" is Started...
3/15/2019 13:54:13      600 Information       Provider "Function" is Started...
3/15/2019 13:54:13      600 Information       Provider "FileSystem" is Started...
```

`Get-WinEvent`Командлет получает данные журнала с компьютера. Параметр **path** указывает каталог и имя файла.

### Пример 12. получение определенного числа событий из архивного журнала событий

Эти команды получают определенное количество событий из архивного журнала событий. `Get-WinEvent` имеет параметры, которые могут получить максимальное число событий или самые старые события. В этом примере используется архивный журнал PowerShell, хранящийся в **к:\тест\повершеллкоре. evtx**.

```powershell
Get-WinEvent -Path 'C:\Test\PowerShellCore Operational.evtx' -MaxEvents 100
```

```Output
   ProviderName: PowerShellCore

TimeCreated                 Id   LevelDisplayName  Message
-----------                 --   ----------------  -------
3/15/2019 09:54:54        4104   Warning           Creating Scriptblock text (1 of 1):...
3/15/2019 09:37:13       40962   Information       PowerShell console is ready for user input
3/15/2019 07:56:24        4104   Warning           Creating Scriptblock text (1 of 1):...
...
3/7/2019 10:53:22        40961   Information       PowerShell console is starting up
3/7/2019 10:53:22         8197   Verbose           Runspace state changed to Opening
3/7/2019 10:53:22         8195   Verbose           Opening RunspacePool
```

`Get-WinEvent`Командлет получает данные журнала с компьютера. Параметр **path** указывает каталог и имя файла. Параметр **MaxEvents** указывает, что отображаются записи 100, от новых к старым.

### Пример 13. трассировка событий для Windows

Трассировка событий для Windows (ETW) записывает события в журнал по мере возникновения событий. События хранятся в порядке от самого старого до самого нового. Архивный файл ETW сохраняется как `.etl` **TraceLog. ETL**.
События перечисляются в том порядке, в котором они записываются в журнал, поэтому необходим *самый старый* параметр.

```powershell
Get-WinEvent -Path 'C:\Tracing\TraceLog.etl' -Oldest |
  Sort-Object -Property TimeCreated -Descending |
    Select-Object -First 100
```

`Get-WinEvent`Командлет получает данные журнала из архивного файла. Параметр **path** указывает каталог и имя файла. Самый **старый** параметр используется для вывода событий в том порядке, в котором они написаны, от старых к новым. Объекты отправляются по конвейеру в `Sort-Object` командлет `Sort-Object` сортирует объекты в порядке убывания по значению свойства **TimeCreated** . Объекты отправляются по конвейеру в `Select-Object` командлет, который отображает новые события 100.

### Пример 14. получение событий из журнала трассировки событий

В этом примере показано, как получить события из файла журнала трассировки событий ( `.etl` ) и архивного файла журнала Windows PowerShell ( `.evtx` ). Можно объединить несколько типов файлов в одну команду.
Так как файлы содержат один и тот же **.NET Framework** тип объекта .NET Framework **EventLogRecord** , их можно отфильтровать с помощью тех же свойств. Команде требуется **самый старый** параметр, так как он считывает из `.etl` файла, но самый **старый** параметр применяется к каждому файлу.

```powershell
Get-WinEvent -Path 'C:\Tracing\TraceLog.etl', 'C:\Test\Windows PowerShell.evtx' -Oldest |
  Where-Object { $_.Id -eq '403' }
```

`Get-WinEvent`Командлет получает данные журнала из архивных файлов. Параметр **path** использует список с разделителями-запятыми для указания каталога файлов и имени файла. Самый **старый** параметр используется для вывода событий в том порядке, в котором они написаны, от старых к новым. Объекты отправляются по конвейеру в `Where-Object` командлет. `Where-Object` использует блок скрипта для поиска событий с **идентификатором** **403**. `$_`Переменная представляет текущий объект в конвейере, а **идентификатор** — свойство идентификатора события.

### Пример 15. Фильтрация результатов журнала событий

В этом примере показаны различные методы фильтрации и выбора событий из журнала событий. Все эти команды получают события, произошедшие за последние 24 часа, из журнала событий **Windows PowerShell** .
Методы фильтрации более эффективны, чем использование `Where-Object` командлета. Фильтры применяются при извлечении объектов. `Where-Object` Извлекает все объекты, а затем применяет фильтры ко всем объектам.

```powershell
# Using the Where-Object cmdlet:
$Yesterday = (Get-Date) - (New-TimeSpan -Day 1)
Get-WinEvent -LogName 'Windows PowerShell' | Where-Object { $_.TimeCreated -ge $Yesterday }

# Using the FilterHashtable parameter:
$Yesterday = (Get-Date) - (New-TimeSpan -Day 1)
Get-WinEvent -FilterHashtable @{ LogName='Windows PowerShell'; Level=3; StartTime=$Yesterday }

# Using the FilterXML parameter:
$xmlQuery = @'
<QueryList>
  <Query Id="0" Path="Windows PowerShell">
    <Select Path="System">*[System[(Level=3) and
        TimeCreated[timediff(@SystemTime) &lt;= 86400000]]]</Select>
  </Query>
</QueryList>
'@
Get-WinEvent -FilterXML $xmlQuery

# Using the FilterXPath parameter:
$XPath = '*[System[Level=3 and TimeCreated[timediff(@SystemTime) &lt;= 86400000]]]'
Get-WinEvent -LogName 'Windows PowerShell' -FilterXPath $XPath
```

### Пример 16. Использование FilterHashtable для получения событий из журнала приложений

В этом примере используется параметр **FilterHashtable** для получения событий из журнала **приложений** . Хэш-таблица использует пары " **ключ-значение** ". Дополнительные сведения о параметре **FilterHashtable** см. в разделе [Создание запросов Get-WinEvent с помощью FilterHashtable](/powershell/scripting/samples/Creating-Get-WinEvent-queries-with-FilterHashtable).
Дополнительные сведения о хэш-таблицах см. [здесь](../Microsoft.PowerShell.Core/about/about_hash_tables.md).

```powershell
$Date = (Get-Date).AddDays(-2)
Get-WinEvent -FilterHashtable @{ LogName='Application'; StartTime=$Date; Id='1003' }
```

`Get-Date`Командлет использует метод **AddDays** для получения даты, которая в два дня предшествует текущей дате. Объект Date хранится в `$Date` переменной.

`Get-WinEvent`Командлет получает сведения о журнале. Параметр **FilterHashtable** используется для фильтрации выходных данных. Ключ **«имя журнала** » указывает значение в журнале **приложения** . Ключ **StartTime** использует значение, хранящееся в `$Date` переменной. Ключ **идентификатора** использует значение идентификатора события **1003**.

### Пример 17. Использование FilterHashtable для получения ошибок приложения

В этом примере используется параметр **FilterHashtable** для поиска ошибок приложения Internet Explorer, произошедших в течение прошлой недели.

```powershell
$StartTime = (Get-Date).AddDays(-7)
Get-WinEvent -FilterHashtable @{
  Logname='Application'
  ProviderName='Application Error'
  Data='iexplore.exe'
  StartTime=$StartTime
}
```

`Get-Date`Командлет использует метод **AddDays** для получения даты за семь дней до текущей даты. Объект Date хранится в `$StartTime` переменной.

`Get-WinEvent`Командлет получает сведения о журнале. Параметр **FilterHashtable** используется для фильтрации выходных данных. Ключ **«имя журнала** » указывает значение в журнале **приложения** . Ключ **providerName** использует значение, **Ошибка приложения** , которое является **источником** события. Ключ **данных** использует значение **iexplore.exe** ключ **StartTime** использует значение, хранящееся в `$StartTime` переменной.

### Пример 18. Использование Суппресшашфилтер для фильтрации ошибок приложения

Как и в примере 16 выше, в этом примере используется параметр **FilterHashtable** для получения событий из журнала **приложений** . Однако мы добавим ключ **суппресшашфилтер** , чтобы отфильтровать события уровня **информации** .

```powershell
$Date = (Get-Date).AddDays(-2)
$filter = @{
  LogName='Application'
  StartTime=$Date
  SuppressHashFilter=@{Level=4}
}
Get-WinEvent -FilterHashtable $filter
```

В этом примере `Get-WinEvent` получает из журнала **приложений** все события за последние два дня, за исключением тех, которые имеют **уровень** 4 (сведения).

## PARAMETERS

### -ComputerName

Указывает имя компьютера, который этот командлет получает для событий из журналов событий. Введите имя NetBIOS, IP-адрес или полное доменное имя (FQDN) компьютера. Значение по умолчанию — локальный компьютер, **localhost**. Этот параметр принимает только одно имя компьютера за один раз.

Чтобы получить журналы событий с удаленных компьютеров, настройте порт брандмауэра для службы журнала событий, чтобы разрешить удаленный доступ.

Этот командлет не зависит от удаленного взаимодействия PowerShell. Параметр **ComputerName** можно использовать, даже если компьютер не настроен для выполнения удаленных команд.

```yaml
Type: System.String
Parameter Sets: GetLogSet, ListLogSet, ListProviderSet, GetProviderSet, HashQuerySet, XmlQuerySet
Aliases: Cn

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Указывает учетную запись пользователя с разрешением на выполнение этого действия. Значение по умолчанию: текущий пользователь.

Введите имя пользователя, например **User01** или **Domain01\User01**. Или введите объект **PSCredential** , например, созданный `Get-Credential` командлетом. Если ввести имя пользователя, будет предложено ввести пароль. Если ввести только имя параметра, будет предложено ввести имя пользователя и пароль.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilterHashtable

Указывает запрос в формате хэш-таблицы для выбора событий из одного или нескольких журналов событий. Запрос содержит хэш-таблицу с одной или несколькими парами " **ключ-значение** ".

К запросам хэш-таблиц применяются следующие правила.

- Ключи и значения обрабатываются без учета регистра.
- Подстановочные знаки допустимы только в значениях, связанных с ключами " **/l** " и " **providerName** ".
- Каждый ключ может быть указан в каждой хэш-таблице только один раз.
- Значение **path** принимает пути к `.etl` файлам, `.evt` и `.evtx` файлов журналов.
- В одном и том же запросе можно использовать ключи " **/l** ", " **путь** " и " **providerName** ".
- Ключ **UserID** может принимать допустимый идентификатор безопасности (SID) или имя учетной записи домена, которое можно использовать для создания допустимого **объекта System. Security. Principal. NTAccount**.
- Значение типа **данных** принимает данные события в безымянном поле. Например, события в классических журналах событий.
- `<named-data>` Key представляет поле данных именованного события.

Если `Get-WinEvent` невозможно интерпретировать пару " **ключ-значение** ", он интерпретирует ключ как имя с учетом регистра для данных события в событии.

Допустимы следующие `Get-WinEvent` пары " **ключ-значение** ":

- **LogName**=`<String[]>`
- **ProviderName**=`<String[]>`
- **Путь**=`<String[]>`
- **Словами**=`<Long[]>`
- **УДОСТОВЕРЕНИЯ**=`<Int32[]>`
- **Уровню**=`<Int32[]>`
- **StartTime**=`<DateTime>`
- **Завершения**=`<DateTime>`
- **UserID**=`<SID>`
- **Data**=`<String[]>`
- `<named-data>`=`<String[]>`
- **суппресшашфилтер**=`<Hashtable>`

```yaml
Type: System.Collections.Hashtable[]
Parameter Sets: HashQuerySet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilterXml

Указывает структурированный запрос XML, который этот командлет выбирает для событий из одного или нескольких журналов событий.

Чтобы создать допустимый XML-запрос, используйте функции **создания пользовательского представления** и **фильтрации текущих журналов** в Просмотр событий Windows. Создайте запрос с помощью элементов в диалоговом окне, а затем перейдите на вкладку XML для просмотра запроса в формате XML. XML-файл можно скопировать с вкладки XML в значение параметра **FilterXml**. Дополнительные сведения о компонентах средства просмотра событий см. в справке средства.

Используйте XML-запрос для создания сложного запроса, содержащего несколько операторов XPath. Формат XML также позволяет использовать элемент " **ПОДАВЛЯТЬ XML** ", исключающий события из запроса. Дополнительные сведения о схеме XML для запросов к журналу событий см. в разделе [Схема запросов](/windows/win32/wes/queryschema-schema) и запросы событий XML статьи [Выбор событий](/previous-versions/aa385231(v=vs.85)).

Вы также можете создать элемент **подавлять** с помощью параметра **FilterHashtable** .

```yaml
Type: System.Xml.XmlDocument
Parameter Sets: XmlQuerySet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilterXPath

Указывает запрос XPath, который этот командлет выбирает события из одного или нескольких журналов.

Дополнительные сведения о языке XPath см. в разделах [Справочник по XPath](/previous-versions/dotnet/netframework-4.0/ms256115(v=vs.100)) и фильтры выбора в разделе [Выбор событий](/previous-versions/aa385231(v=vs.85)).

```yaml
Type: System.String
Parameter Sets: GetLogSet, GetProviderSet, FileSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Получает журналы отладки и аналитики в дополнение к другим журналам событий. Параметр **Force** необходим для получения журнала отладки или аналитики, когда значение параметра имени содержит подстановочные знаки.

По умолчанию `Get-WinEvent` командлет исключает эти журналы, если не указано полное имя журнала отладки или аналитики.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GetLogSet, ListLogSet, GetProviderSet, HashQuerySet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ListLog

Определяет журналы событий. Введите имена журналов событий в список, разделяя их запятыми. Разрешено использовать подстановочные знаки. Чтобы получить все журналы, используйте `*` подстановочный знак звездочки ().

```yaml
Type: System.String[]
Parameter Sets: ListLogSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -ListProvider

Указывает поставщики журнала событий, которые получает этот командлет. Поставщик журнала событий — это программа или служба, которая записывает события в журнал событий.

Введите имена поставщиков в список, разделяя их запятыми. Разрешено использовать подстановочные знаки. Чтобы получить поставщиков всех журналов событий на компьютере, используйте `*` подстановочный знак звездочки ().

```yaml
Type: System.String[]
Parameter Sets: ListProviderSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -LogName

Указывает журналы событий, из которых этот командлет получает события. Введите имена журналов событий в список, разделяя их запятыми. Разрешено использовать подстановочные знаки. Можно также передать имена журналов в `Get-WinEvent` командлет.

> [!NOTE]
> PowerShell не ограничивает объем журналов, которые можно запросить. Однако `Get-WinEvent` командлет запрашивает API Windows с ограничением в 256. Это может усложнить фильтрацию всех журналов за один раз. Это можно обойти, используя `foreach` цикл для прохода по каждому журналу следующим образом: `Get-WinEvent -ListLog * | ForEach-Object{ Get-WinEvent -LogName $_.Logname }`

```yaml
Type: System.String[]
Parameter Sets: GetLogSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -MaxEvents

Указывает максимальное число возвращаемых событий. Введите целое число, например 100. Значение по умолчанию: возврат всех событий в журналах или файлах.

```yaml
Type: System.Int64
Parameter Sets: GetLogSet, GetProviderSet, FileSet, HashQuerySet, XmlQuerySet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Oldest

Укажите, что этот командлет получает события в порядке с самым старым. По умолчанию события возвращаются в порядке "сначала новые".

Этот параметр необходим для получения событий из `.etl` файлов и `.evt` из журналов отладки и аналитики. В этих файлах события записываются в порядке "старые сначала", поэтому они могут быть возвращены только в том же порядке.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GetLogSet, GetProviderSet, FileSet, HashQuerySet, XmlQuerySet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Указывает путь к файлам журнала событий, из которых этот командлет получает события. Введите разделенный запятыми список путей к файлам или используйте подстановочные знаки для создания шаблонов путей к файлам.

`Get-WinEvent` поддерживает файлы с `.evt` `.evtx` расширениями, и `.etl` . В одну команду можно включить события из разных файлов и типов файлов.

```yaml
Type: System.String[]
Parameter Sets: FileSet
Aliases: PSPath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -ProviderName

Указывает в виде массива строк поставщики журналов событий, от которых этот командлет получает события. Введите разделенный запятыми список имен поставщиков или используйте подстановочные знаки для создания шаблонов имен поставщиков.

Поставщик журнала событий — это программа или служба, которая записывает события в журнал событий. Это не поставщик PowerShell.

```yaml
Type: System.String[]
Parameter Sets: GetProviderSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System. String, System.Xml.Xmlдокумент, System. Collections. Hashtable

Вы можете конвейерировать **(строку** ), запрос **Филтерксмл** или запрос **FilterHashtable** в `Get-WinEvent` .

## Выходные данные

### System.Diagnostics.Eventing.Reader.EventLogConfiguration, System.Diagnostics.Eventing.Reader.EventLogRecord, System.Diagnostics.Eventing.Reader.ProviderMetadata.

При использовании параметра **листлог** `Get-WinEvent` возвращает объекты **System. Diagnostics. Eventing. Reader. EventLogConfiguration** .

При использовании параметра **листпровидер** `Get-WinEvent` возвращает объекты **System. Diagnostics. Eventing. Reader. ProviderMetadata** .

При использовании всех остальных параметров `Get-WinEvent` возвращает объекты **System. Diagnostics. Eventing. Reader. EventLogRecord** .

## ПРИМЕЧАНИЯ

`Get-WinEvent` предназначен для замены `Get-EventLog` командлета на компьютерах под управлением Windows Vista и более поздних версий Windows. `Get-EventLog` Возвращает события только в классических журналах событий. Функция `Get-EventLog` поддерживается для совместимости с предыдущими версиями.

`Get-WinEvent` `Get-EventLog` Командлеты и не поддерживаются в среде предустановки Windows (Windows PE).

## Связанные ссылки

[about_Automatic_Variables](../Microsoft.PowerShell.Core/about/about_automatic_variables.md)

[about_Foreach](../Microsoft.PowerShell.Core/about/about_Foreach.md)

[about_Hash_Tables](../Microsoft.PowerShell.Core/about/about_hash_tables.md)

[Создание запросов Get-WinEvent с помощью FilterHashtable](/powershell/scripting/samples/Creating-Get-WinEvent-queries-with-FilterHashtable)

[Format-Table](../Microsoft.PowerShell.Utility/Format-Table.md)

[Group-Object](../Microsoft.PowerShell.Utility/Group-Object.md)

[Sort-Object](../Microsoft.PowerShell.Utility/Sort-Object.md)

[Where-Object](../Microsoft.PowerShell.Core/Where-Object.md)
