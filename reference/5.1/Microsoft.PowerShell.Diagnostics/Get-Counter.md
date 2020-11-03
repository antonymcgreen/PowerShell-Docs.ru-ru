---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 10/30/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/get-counter?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Counter
ms.openlocfilehash: 7c1ab665fc7ffddc54ec936f80b76b4329291a3b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227006"
---
# Get-Counter

## Краткий обзор
Получает данные счетчиков производительности с локальных и удаленных компьютеров.

## SYNTAX

### CounterSet (по умолчанию)

```
Get-Counter [[-Counter] <String[]>] [-SampleInterval <Int32>] [-MaxSamples <Int64>] [-Continuous]
 [-ComputerName <String[]>] [<CommonParameters>]
```

### листсетсет

```
Get-Counter [-ListSet] <String[]> [-ComputerName <String[]>] [<CommonParameters>]
```

## DESCRIPTION

`Get-Counter`Командлет получает данные счетчика производительности непосредственно из инструментария наблюдения за производительностью в семействе операционных систем Windows. `Get-Counter` Возвращает данные о производительности с локального компьютера или удаленных компьютеров.

С помощью параметров можно `Get-Counter` указать один или несколько компьютеров, список наборов счетчиков производительности и содержащихся в них экземпляров, задать интервалы выборки и указать максимальное число выборок. Без параметров `Get-Counter` получает данные счетчика производительности для набора системных счетчиков.

Многие наборы счетчиков защищены списками управления доступом (ACL). Чтобы просмотреть все наборы счетчиков, откройте PowerShell с параметром **Запуск от имени администратора** .

## Примеры

### Пример 1. Получение списка наборов счетчиков

В этом примере получается список наборов счетчиков локального компьютера.

```powershell
Get-Counter -ListSet *
```

```Output
CounterSetName     : Processor
MachineName        : .
CounterSetType     : MultiInstance
Description        : The Processor performance object consists of counters that measure aspects ...
                     computer that performs arithmetic and logical computations, initiates ...
                     computer can have multiple processors.  The processor object represents ...
Paths              : {\Processor(*)\% Processor Time, \Processor(*)\% User Time, ...
PathsWithInstances : {\Processor(0)\% Processor Time, \Processor(1)\% Processor Time, ...
Counter            : {\Processor(*)\% Processor Time, \Processor(*)\% User Time, ...
```

`Get-Counter` использует параметр **List** со звездочкой ( `*` ) для получения списка наборов счетчиков.
Точка ( `.` ) в столбце **MachineName** представляет локальный компьютер.

### Пример 2. Указание SampleInterval и Макссамплес

Этот пример возвращает данные счетчика для всех процессоров на локальном компьютере. Данные собираются с интервалом в две секунды, пока не будут представлены три примера.

```powershell
Get-Counter -Counter "\Processor(_Total)\% Processor Time" -SampleInterval 2 -MaxSamples 3
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/18/2019 14:39:56        \\Computer01\processor(_total)\% processor time :
                          20.7144271584086

6/18/2019 14:39:58        \\Computer01\processor(_total)\% processor time :
                          10.4391790575511

6/18/2019 14:40:01        \\Computer01\processor(_total)\% processor time :
                          37.5968799396998
```

`Get-Counter` использует параметр **Counter** для указания пути счетчика `\Processor(_Total)\% Processor Time` . Параметр **SampleInterval** задает интервал в два секунды для проверки счетчика. **Макссамплес** определяет, что три — это максимальное число раз для проверки счетчика.

### Пример 3. получение непрерывных выборок счетчика

Этот пример получает непрерывные выборки для счетчика каждую секунду. Чтобы прерывать выполнение команды, нажмите клавиши <kbd>CTRL</kbd> + <kbd>C</kbd>. Чтобы указать более длинный интервал между выборками, используйте параметр **SampleInterval** .

```powershell
Get-Counter -Counter "\Processor(_Total)\% Processor Time" -Continuous
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/19/2019 15:35:03        \\Computer01\processor(_total)\% processor time :
                          43.8522842937022

6/19/2019 15:35:04        \\Computer01\processor(_total)\% processor time :
                          29.7896844697383

6/19/2019 15:35:05        \\Computer01\processor(_total)\% processor time :
                          29.4962645638135

6/19/2019 15:35:06        \\Computer01\processor(_total)\% processor time :
                          25.5901500127408
```

`Get-Counter` использует параметр **Counter** для указания `\Processor\% Processor Time` счетчика.
Параметр **непрерывно** задает получение образцов каждую секунду до тех пор, пока команда не будет остановлена с помощью <kbd>клавиши CTRL</kbd> + <kbd>C</kbd>.

### Пример 4. Алфавитный список наборов счетчиков

В этом примере используется конвейер для получения набора списка счетчиков, а затем сортировка списка в алфавитном порядке.

```powershell
Get-Counter -ListSet * | Sort-Object -Property CounterSetName | Format-Table -AutoSize
```

```Output
CounterSetName                        MachineName CounterSetType  Description
--------------                        ----------- --------------  -----------
.NET CLR Data                         .           SingleInstance  .Net CLR Data
.NET Data Provider for SqlServer      .           SingleInstance  Counters for System.Data.SqlClient
AppV Client Streamed Data Percentage  .           SingleInstance  Size of data streamed to disk ...
Authorization Manager Applications    .           SingleInstance  The set of Counters for ...
BitLocker                             .           MultiInstance   BitLocker Drive Encryption ...
Bluetooth Device                      .           SingleInstance  Counters related to a remote ...
Cache                                 .           SingleInstance  The Cache performance object ...
Client Side Caching                   .           SingleInstance  Performance counters for SMB ...
```

`Get-Counter` использует параметр **List** со звездочкой ( `*` ) для получения полного списка наборов счетчиков. Объекты **CounterSet** отправляются по конвейеру. `Sort-Object` использует параметр **Property** , чтобы указать, что объекты сортируются по **CounterSetName**. Объекты отправляются по конвейеру в `Format-Table` . Параметр **AutoSize** корректирует ширину столбцов для сокращения усечения.

Точка ( `.` ) в столбце **MachineName** представляет локальный компьютер.

### Пример 5. Запуск фонового задания для получения данных счетчика

В этом примере `Start-Job` выполняет команду в `Get-Counter` качестве фонового задания на локальном компьютере.
Чтобы просмотреть выходные данные счетчика производительности задания, используйте `Receive-Job` командлет.

```powershell
Start-Job -ScriptBlock {Get-Counter -Counter "\LogicalDisk(_Total)\% Free Space" -MaxSamples 1000}
```

```Output
Id     Name  PSJobTypeName   State    HasMoreData  Location   Command
--     ----  -------------   -----    -----------  --------   -------
1      Job1  BackgroundJob   Running  True         localhost  Get-Counter -Counter
```

`Start-Job` использует параметр **ScriptBlock** для выполнения `Get-Counter` команды. `Get-Counter` использует параметр **Counter** для указания пути счетчика `\LogicalDisk(_Total)\% Free Space` . Параметр **макссамплес** указывает, что получение образцов счетчика 1000.

### Пример 6. получение данных счетчиков с нескольких компьютеров

В этом примере используется переменная для получения данных счетчиков производительности с двух компьютеров.

```powershell
$DiskReads = "\LogicalDisk(C:)\Disk Reads/sec"
$DiskReads | Get-Counter -ComputerName Server01, Server02 -MaxSamples 10
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/21/2019 10:51:04        \\Server01\logicaldisk(c:)\disk reads/sec :
                          0

                          \\Server02\logicaldisk(c:)\disk reads/sec :
                          0.983050344269146
```

`$DiskReads`Переменная хранит `\LogicalDisk(C:)\Disk Reads/sec` путь счетчика. `$DiskReads`Переменная отправляется по конвейеру в `Get-Counter` . Значение **Counter** является первым параметром позиционирования и принимает путь, хранящийся в `$DiskReads` . **ComputerName** указывает два компьютера и **макссамплес** указывает на получение 10 образцов с каждого компьютера.

### Пример 7. Получение значений экземпляра счетчика из нескольких случайных компьютеров

В этом примере возвращается значение счетчика производительности на 50 случайных удаленных компьютеров в Организации. Параметр **ComputerName** использует случайные имена компьютеров, хранящиеся в переменной. Чтобы обновить имена компьютеров в переменной, повторно создайте переменную.

Альтернативой для имен серверов в параметре **ComputerName** является использование текстового файла. Пример:

`-ComputerName (Get-Random (Get-Content -Path C:\Servers.txt) -Count 50)`

Путь к счетчику содержит звездочку ( `*` ) в имени экземпляра для получения данных для каждого из процессоров удаленного компьютера.

```powershell
$Servers = Get-Random (Get-Content -Path C:\Servers.txt) -Count 50
$Counter = "\Processor(*)\% Processor Time"
Get-Counter -Counter $Counter -ComputerName $Servers
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/20/2019 12:20:35        \\Server01\processor(0)\% processor time :
                          6.52610319637854

                          \\Server01\processor(1)\% processor time :
                          3.41030663625782

                          \\Server01\processor(2)\% processor time :
                          9.64189975649925

                          \\Server01\processor(3)\% processor time :
                          1.85240835619747

                          \\Server01\processor(_total)\% processor time :
                          5.35768447160776
```

`Get-Random`Командлет использует `Get-Content` для выбора 50 случайных имен компьютеров из `Servers.txt` файла. Имена удаленных компьютеров хранятся в `$Servers` переменной. `\Processor(*)\% Processor Time`Путь к счетчику хранится в `$Counter` переменной. `Get-Counter` использует параметр **Counter** для указания счетчиков в `$Counter` переменной. Параметр **ComputerName** задает имена компьютеров в `$Servers` переменной.

### Пример 8. использование свойства Path для получения форматированных имен путей

В этом примере используется свойство **path** набора счетчиков, чтобы найти отформатированные имена путей для счетчиков производительности.

Конвейер используется с `Where-Object` командлетом для поиска подмножества имен путей. Чтобы найти набор счетчиков полный список путей к счетчикам, удалите конвейер ( `|` ) и `Where-Object` команду.

`$_`— Это автоматическая переменная для текущего объекта в конвейере.
Дополнительные сведения см. в разделе [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).

```powershell
(Get-Counter -ListSet Memory).Paths | Where-Object { $_ -like "*Cache*" }
```

```Output
\Memory\Cache Faults/sec
\Memory\Cache Bytes
\Memory\Cache Bytes Peak
\Memory\System Cache Resident Bytes
\Memory\Standby Cache Reserve Bytes
\Memory\Standby Cache Normal Priority Bytes
\Memory\Standby Cache Core Bytes
\Memory\Long-Term Average Standby Cache Lifetime (s)
```

`Get-Counter` использует параметр **List** для указания набора счетчиков **памяти** . Команда заключается в круглые скобки **, чтобы свойство** paths возвращало каждый путь в виде строки. Объекты отправляются по конвейеру в `Where-Object` . `Where-Object` использует переменную `$_` для обработки каждого объекта и использует `-like` оператор для поиска совпадений для строки `*Cache*` . Звездочки () являются символами- `*` шаблонами для любых символов.

### Пример 9. использование свойства Пассвисинстанцес для получения форматированных имен путей

Этот пример возвращает отформатированные имена путей, которые включают экземпляры счетчиков производительности " **физический диск** ".

```powershell
(Get-Counter -ListSet PhysicalDisk).PathsWithInstances
```

```Output
\PhysicalDisk(0 C:)\Current Disk Queue Length
\PhysicalDisk(_Total)\Current Disk Queue Length
\PhysicalDisk(0 C:)\% Disk Time
\PhysicalDisk(_Total)\% Disk Time
\PhysicalDisk(0 C:)\Avg. Disk Queue Length
\PhysicalDisk(_Total)\Avg. Disk Queue Length
\PhysicalDisk(0 C:)\% Disk Read Time
\PhysicalDisk(_Total)\% Disk Read Time
```

`Get-Counter` использует параметр **List** для указания набора счетчиков " **физический диск** ". Команда заключается в круглые скобки, чтобы свойство **пассвисинстанцес** возвращало каждый экземпляр пути в виде строки.

### Пример 10. получение одного значения для каждого счетчика в наборе счетчиков

В этом примере возвращается одно значение для каждого счетчика производительности в наборе счетчиков **памяти** на локальном компьютере.

```powershell
$MemCounters = (Get-Counter -ListSet Memory).Paths
Get-Counter -Counter $MemCounters
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/19/2019 12:05:00        \\Computer01\memory\page faults/sec :
                          868.772077545597

                          \\Computer01\memory\available bytes :
                          9031176192

                          \\Computer01\memory\committed bytes :
                          8242982912

                          \\Computer01\memory\commit limit :
                          19603333120
```

`Get-Counter` использует параметр **List** для указания набора счетчиков **памяти** . Команда заключается в круглые скобки **, чтобы свойство** paths возвращало каждый путь в виде строки. Пути хранятся в `$MemCounters` переменной. `Get-Counter` использует параметр **Counter** для указания путей к счетчику в `$MemCounters` переменной.

### Пример 11. Отображение значений свойств объекта

Значения свойств в объекте **перформанцекаунтерсампле** представляют образец каждого из данных. В этом примере мы используем свойства объекта **каунтерсамплес** для проверки, выбора, сортировки и группирования данных.

```powershell
$Counter = "\\Server01\Process(Idle)\% Processor Time"
$Data = Get-Counter $Counter
$Data.CounterSamples | Format-List -Property *
```

```Output
Path             : \\Server01\process(idle)\% processor time
InstanceName     : idle
CookedValue      : 198.467899571389
RawValue         : 14329160321003
SecondValue      : 128606459528326201
MultipleCount    : 1
CounterType      : Timer100Ns
Timestamp        : 6/19/2019 12:20:49
Timestamp100NSec : 128606207528320000
Status           : 0
DefaultScale     : 0
TimeBase         : 10000000
```

Путь к счетчику хранится в `$Counter` переменной. `Get-Counter` Возвращает один образец значений счетчика и сохраняет результаты в `$Data` переменной. `$Data`Переменная использует свойство **каунтерсамплес** для получения свойств объекта. Объект отправляется по конвейеру в `Format-List` . Параметр **Property** использует `*` подстановочный знак звездочки () для выбора всех свойств.

### Пример 12. значения массива счетчиков производительности

В этом примере переменная хранит каждый счетчик производительности. Свойство **каунтерсамплес** — это массив, который может отображать определенные значения счетчика.

Для просмотра каждого образца счетчика используйте `$Counter.CounterSamples` .

```powershell
$Counter = Get-Counter -Counter "\Processor(*)\% Processor Time"
$Counter.CounterSamples[0]
```

```Output
Path                                         InstanceName        CookedValue
----                                         ------------        -----------
\\Computer01\processor(0)\% processor time   0              1.33997091699662
```

`Get-Counter` использует параметр **Counter** для указания счетчика `\Processor(*)\% Processor Time` . Значения хранятся в `$Counter` переменной.
`$Counter.CounterSamples[0]` Отображает значение массива для первого значения счетчика.

### Пример 13. Сравнение значений счетчиков производительности

Этот пример находит количество процессорного времени, используемого каждым процессором на локальном компьютере. Свойство **каунтерсамплес** используется для сравнения данных счетчика с указанным значением.

Для просмотра каждого образца счетчика используйте `$Counter.CounterSamples` .

```powershell
$Counter = Get-Counter -Counter "\Processor(*)\% Processor Time"
$Counter.CounterSamples | Where-Object { $_.CookedValue -lt "20" }
```

```Output
Path                                         InstanceName        CookedValue
----                                         ------------        -----------
\\Computer01\processor(0)\% processor time   0              12.6398025240208
\\Computer01\processor(1)\% processor time   1              15.7598095767344
```

`Get-Counter` использует параметр **Counter** для указания счетчика `\Processor(*)\% Processor Time` . Значения хранятся в `$Counter` переменной. Объекты, хранящиеся в `$Counter.CounterSamples` , отправляются по конвейеру. `Where-Object` использует блок скрипта для сравнения значения каждого объекта с указанным значением 20. `$_.CookedValue`— Это переменная для текущего объекта в конвейере. Отображаются счетчики с **кукедвалуе** меньше 20.

### Пример 14. Сортировка данных счетчика производительности

В этом примере показано, как сортировать данные счетчиков производительности. В примере выполняется поиск процессов на компьютере, которые используют наибольшее время процессора во время выполнения примера.

```powershell
$Procs = Get-Counter -Counter "\Process(*)\% Processor Time"
$Procs.CounterSamples | Sort-Object -Property CookedValue -Descending |
   Format-Table -Property Path, InstanceName, CookedValue -AutoSize
```

```Output
Path                                                         InstanceName             CookedValue
----                                                         ------------             -----------
\\Computer01\process(_total)\% processor time                _total              395.464129650573
\\Computer01\process(idle)\% processor time                  idle                389.356575524695
\\Computer01\process(mssense)\% processor time               mssense             3.05377706293879
\\Computer01\process(csrss#1)\% processor time               csrss               1.52688853146939
\\Computer01\process(microsoftedgecp#10)\% processor time    microsoftedgecp     1.52688853146939
\\Computer01\process(runtimebroker#5)\% processor time       runtimebroker                      0
\\Computer01\process(settingsynchost)\% processor time       settingsynchost                    0
\\Computer01\process(microsoftedgecp#16)\% processor time    microsoftedgecp                    0
```

`Get-Counter` использует параметр **Counter** , чтобы указать `\Process(*)\% Processor Time` Счетчик для всех процессов на локальном компьютере. Результат сохраняется в `$Procs` переменной. `$Procs`Переменная со свойством **каунтерсамплес** отправляет объекты **перформанцекаунтерсампле** вниз по конвейеру. `Sort-Object` использует параметр **Property** для сортировки объектов по **Кукедвалуе** в порядке **убывания** . `Format-Table` использует параметр **Property** для выбора столбцов для выходных данных. Параметр **AutoSize** корректирует ширину столбцов для сокращения усечения.

## PARAMETERS

### -ComputerName

Указывает одно имя компьютера или разделенный запятыми массив имен **удаленных** компьютеров. Используйте имя NetBIOS, IP-адрес или полное доменное имя компьютера.

Чтобы получить данные счетчиков производительности с **локального** компьютера, исключите параметр **ComputerName** .
Для выходных данных, таких как **список** , содержащий столбец **MachineName** , точка ( `.` ) обозначает локальный компьютер.

`Get-Counter` не зависит от удаленного взаимодействия PowerShell. Параметр **ComputerName** можно использовать, даже если компьютер не настроен для выполнения удаленных команд.

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

### -Continuous

Если указан параметр **Continuous** , `Get-Counter` получает выборки до нажатия клавиши <kbd>CTRL</kbd> + <kbd>C</kbd>. Выборки получаются каждую секунду для каждого указанного счетчика производительности. Используйте параметр **SampleInterval** , чтобы увеличить интервал между непрерывными примерами.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Counter

Указывает путь к одному или нескольким путям счетчиков. Пути являются входными данными в виде массива с разделителями-запятыми, переменной или значений из текстового файла. Строки пути счетчика можно отправить по конвейеру в `Get-Counter` .

Пути счетчиков используют следующий синтаксис:

`\\ComputerName\CounterSet(Instance)\CounterName`

`\CounterSet(Instance)\CounterName`

Пример:

`\\Server01\Processor(*)\% User Time`

`\Processor(*)\% User Time`

Параметр `\\ComputerName` является необязательным в пути счетчика производительности. Если путь счетчика не содержит имя компьютера, `Get-Counter` использует локальный компьютер.

Звездочка ( `*` ) в экземпляре является символом-шаблоном для получения всех экземпляров счетчика.

```yaml
Type: System.String[]
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### — Список

Список наборов счетчиков производительности на компьютерах. `*`Для указания всех наборов счетчиков используйте звездочку (). Введите одно имя или строку с разделителями-запятыми в именах наборов счетчиков. Имена наборов счетчиков можно отправить по конвейеру.

Чтобы получить наборы счетчиков с отформатированными путями счетчиков, используйте параметр **List** . Свойства **paths** и **пассвисинстанцес** каждого набора счетчиков содержат отдельные пути счетчиков, отформатированные в виде строки.

Можно сохранить строки пути счетчика в переменной или использовать конвейер для отправки строки другой `Get-Counter` команде.

Например, для отправки каждого пути счетчика **процессора** в `Get-Counter` :

`Get-Counter -ListSet Processor | Get-Counter`

```yaml
Type: System.String[]
Parameter Sets: ListSetSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### -Макссамплес

Указывает число выборок, получаемых из каждого указанного счетчика производительности. Чтобы получить постоянный поток образцов, используйте параметр **Continuous** .

Если параметр **макссамплес** не указан, `Get-Counter` получает только один выборку для каждого указанного счетчика.

Чтобы получить большой набор данных, выполните в `Get-Counter` качестве фонового задания PowerShell. См. дополнительные сведения о [заданиях](../Microsoft.PowerShell.Core/About/about_Jobs.md).

```yaml
Type: System.Int64
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SampleInterval

Указывает количество секунд между выборками для каждого указанного счетчика производительности. Если параметр **SampleInterval** не указан, `Get-Counter` используется интервал в 1 секунду.

```yaml
Type: System.Int32
Parameter Sets: GetCounterSet
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

### System.String[]

`Get-Counter` принимает входные данные конвейера для путей счетчиков и имен наборов счетчиков.

## Выходные данные

### Microsoft. PowerShell. Commands. NOCOUNT. Counters, Microsoft. PowerShell. Commands. NOCOUNT. PerformanceCounterSampleSet, Microsoft. PowerShell. Commands. NOCOUNT. Перформанцекаунтерсампле

Чтобы просмотреть свойства объекта, отправьте выходные данные по конвейеру в `Get-Member` . Ниже приведены типы объектов, которые являются выходными данными.

**Параметр CounterSet** : **Microsoft. PowerShell. Commands. NOCOUNT. CounterSet**

Параметр **счетчика** : **Microsoft. PowerShell. Commands. NOCOUNT. PerformanceCounterSampleSet**

Свойство **каунтерсамплес** : **Microsoft. PowerShell. Commands. NOCOUNT. перформанцекаунтерсампле**

## ПРИМЕЧАНИЯ

Если параметры не указаны, `Get-Counter` получает один выборку для каждого указанного счетчика производительности. Используйте параметры **макссамплес** и **Continuous** для получения дополнительных образцов.

`Get-Counter` использует интервал в 1 секунду между образцами. Чтобы увеличить интервал, используйте параметр **SampleInterval** .

Значения **макссамплес** и **SampleInterval** применяются ко всем счетчикам на каждом компьютере в команде. Чтобы задать различные значения для разных счетчиков, введите отдельные `Get-Counter` команды.

## Связанные ссылки

[about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md)

[Format-List](../Microsoft.PowerShell.Utility/Format-List.md)

[Format-Table](../Microsoft.PowerShell.Utility/Format-Table.md)

[Get-Member](../Microsoft.PowerShell.Utility/Get-Member.md)

[Receive-Job.](../Microsoft.PowerShell.Core/Receive-Job.md)

[Start-Job](../Microsoft.PowerShell.Core/Start-Job.md)

[Where-Object](..//Microsoft.PowerShell.Core/Where-Object.md)
