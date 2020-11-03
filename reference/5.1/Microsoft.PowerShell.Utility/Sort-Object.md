---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/sort-object?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Sort-Object
ms.openlocfilehash: 1d27641f94d82b85bab694b392c0f09bb3265517
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2020
ms.locfileid: "93230282"
---
# Sort-Object

## Краткий обзор
Сортирует объекты по значениям свойств.

## SYNTAX

### Default (по умолчанию)

```
Sort-Object [[-Property] <Object[]>] [-Descending] [-Unique] [-InputObject <psobject>]
 [-Culture <string>] [-CaseSensitive] [<CommonParameters>]
```

## DESCRIPTION

`Sort-Object`Командлет сортирует объекты в возрастающем или убывающем порядке на основе значений свойств объектов. Если свойства сортировки не включены в команду, PowerShell использует свойства сортировки по умолчанию первого входного объекта. Если тип входного объекта не имеет свойств сортировки по умолчанию, PowerShell пытается сравнить сами объекты. Дополнительные сведения см. в разделе " [Примечания](#notes) ".

Объекты можно сортировать по отдельному свойству или нескольким свойствам. Несколько свойств используют хэш-таблицы для сортировки в возрастающем порядке, по убыванию или в сочетании порядка сортировки. Свойства сортируются с учетом регистра или без учета регистра. Используйте параметр **UNIQUE** , чтобы исключить дубликаты из выходных данных.

## Примеры

### Пример 1. Сортировка текущего каталога по имени

Эта команда сортирует файлы и подкаталоги в каталоге.

```
PS> Get-ChildItem -Path C:\Test | Sort-Object

    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/13/2019     13:26             20 Bfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-a----         2/1/2019     08:43            183 CreateTestFile.ps1
d-----        2/25/2019     18:25                Files
d-----        2/25/2019     18:24                Logs
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
-a----        2/12/2019     16:24             23 Zsystemlog.log
```

`Get-ChildItem`Командлет получает файлы и подкаталоги из каталога, указанного параметром **path** , **C:\test** . Объекты отправляются по конвейеру в `Sort-Object` командлет.
`Sort-Object` не указывает свойство, поэтому выходные данные сортируются по свойству Sort по умолчанию, **Name** .

### Пример 2. Сортировка текущего каталога по длине файла

Эта команда отображает файлы в текущем каталоге по длине в порядке возрастания.

```
PS> Get-ChildItem -Path C:\Test -File | Sort-Object -Property Length

    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     13:26             20 Bfile.txt
-a----        2/12/2019     16:24             23 Zsystemlog.log
-a----        2/13/2019     08:55             26 anotherfile.txt
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
-a----         2/1/2019     08:43            183 CreateTestFile.ps1
-a----        2/12/2019     15:40         118014 Command.txt
```

`Get-ChildItem`Командлет получает файлы из каталога, указанного параметром **path** .
Параметр **File** указывает, что `Get-ChildItem` только получает объекты File. Объекты отправляются по конвейеру в `Sort-Object` командлет. `Sort-Object` использует параметр **length** для сортировки файлов по длине в порядке возрастания.

### Пример 3. Сортировка процессов по использованию памяти

В этом примере отображаются процессы с наибольшим использованием памяти в зависимости от размера рабочего множества (WS).

```
PS> Get-Process | Sort-Object -Property WS | Select-Object -Last 5

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    136   193.92     217.11     889.16   87492   8 OUTLOOK
    112   347.73     297.02      95.19  106908   8 Teams
    206   266.54     323.71      37.17   60620   8 MicrosoftEdgeCP
     35   552.19     549.94     131.66    6552   8 Code
      0     1.43     595.12       0.00    2780   0 Memory Compression
```

`Get-Process`Командлет возвращает список процессов, запущенных на компьютере. Объекты процесса отправляются по конвейеру в `Sort-Object` командлет. `Sort-Object` использует параметр **Property** для сортировки объектов по протоколу **WS** . Объекты отправляются по конвейеру в `Select-Object` командлет.
`Select-Object` использует **последний** параметр для указания последних пяти объектов, которые являются объектами с наибольшим использованием **WS** .

### Пример 4. Сортировка объектов Хисторинфо по идентификатору

Эта команда сортирует объекты **хисторинфо** сеанса PowerShell с помощью свойства **ID** . Каждый сеанс PowerShell имеет собственный журнал команд.

```
PS> Get-History | Sort-Object -Property Id -Descending

  Id CommandLine
  -- -----------
  10 Get-Command Sort-Object -Syntax
   9 $PSVersionTable
   8 Get-Command Sort-Object -Syntax
   7 Get-Command Sort-Object -ShowCommandInfo
   6 Get-ChildItem -Path C:\Test | Sort-Object -Property Length
   5 Get-Help Clear-History -online
   4 Get-Help Clear-History -full
   3 Get-ChildItem | Get-Member
   2 Get-Command Sort-Object -Syntax
   1 Set-Location C:\Test\
```

`Get-History`Командлет получает объекты журнала из текущего сеанса PowerShell. Объекты отправляются по конвейеру в `Sort-Object` командлет. `Sort-Object` использует параметр **Property** для сортировки объектов по **идентификатору** . Параметр **Descending** сортирует журнал команд от новых к старым.

### Пример 5. Использование хэш-таблицы для сортировки свойств в порядке возрастания и убывания

Эта команда использует два свойства для сортировки объектов, **Status** и **DisplayName** . **Состояние** сортируется в убывающем порядке, а **DisplayName** — по возрастанию.

Хэш-таблица используется для указания значения параметра **Свойства** . Хэш-таблица использует выражение для указания имен свойств и порядка сортировки. Дополнительные сведения о хэш-таблицах см. [здесь](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).

Свойство **Status** , используемое в хэш-таблице, является перечислимым свойством.
Дополнительные сведения см. в разделе [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).

```
PS C:\> Get-Service | Sort-Object -Property @{Expression = "Status"; Descending = $True}, @{Expression = "DisplayName"; Descending = $False}

Status   Name               DisplayName
------   ----               -----------
Running  Appinfo            Application Information
Running  BthAvctpSvc        AVCTP service
Running  BrokerInfrastru... Background Tasks Infrastructure Ser...
Running  BDESVC             BitLocker Drive Encryption Service
Running  CoreMessagingRe... CoreMessaging
Running  VaultSvc           Credential Manager
Running  DsSvc              Data Sharing Service
Running  Dhcp               DHCP Client
...
Stopped  ALG                Application Layer Gateway Service
Stopped  AppMgmt            Application Management
Stopped  BITS               Background Intelligent Transfer Ser...
Stopped  wbengine           Block Level Backup Engine Service
Stopped  BluetoothUserSe... Bluetooth User Support Service_14fb...
Stopped  COMSysApp          COM+ System Application
Stopped  smstsmgr           ConfigMgr Task Sequence Agent
Stopped  DeviceInstall      Device Install Service
Stopped  MSDTC              Distributed Transaction Coordinator
```

`Get-Service`Командлет возвращает список служб на компьютере. Объекты службы отправляются по конвейеру в `Sort-Object` командлет. `Sort-Object` использует параметр **Property** с хэш-таблицей для указания имен свойств и порядка сортировки. Параметр **Свойства** сортируется по двум свойствам, **состояние** в убывающем порядке и **DisplayName** в возрастающем порядке.

**Status** — это перечислимое свойство. Параметр **Stopped** имеет значение **1** , а его **выполнение** имеет значение **4** . Параметр **Descending** имеет значение, `$True` чтобы перед **остановленными** процессами отображались **выполняющиеся** процессы. **DisplayName** задает для параметра по **убыванию** значение, чтобы `$False` отсортировать отображаемые имена в алфавитном порядке.

### Пример 6. сортировка текстовых файлов по периоду времени

Эта команда сортирует текстовые файлы в порядке убывания интервала времени между **CreationTime** и **LastWriteTime** .

```
PS> Get-ChildItem -Path C:\Test\*.txt | Sort-Object -Property @{Expression = {$_.CreationTime - $_.LastWriteTime}; Descending = $False} | Format-Table CreationTime, LastWriteTime, FullName

CreationTime          LastWriteTime        FullName
------------          -------------        --------
11/21/2018 12:39:01   2/26/2019 08:59:36   C:\Test\test2.txt
12/4/2018 08:29:41    2/26/2019 08:57:05   C:\Test\powershell_list.txt
2/20/2019 08:15:59    2/26/2019 12:09:43   C:\Test\CreateTestFile.txt
2/20/2019 08:15:59    2/26/2019 12:07:41   C:\Test\Command.txt
2/20/2019 08:15:59    2/26/2019 08:57:52   C:\Test\ReadOnlyFile.txt
11/29/2018 15:16:50   12/4/2018 16:16:24   C:\Test\LogData.txt
2/25/2019 18:25:11    2/26/2019 12:08:47   C:\Test\Zsystemlog.txt
2/25/2019 18:25:11    2/26/2019 08:55:33   C:\Test\Bfile.txt
2/26/2019 08:46:59    2/26/2019 12:12:19   C:\Test\LogFile3.txt

```

`Get-ChildItem`Командлет использует параметр **path** для указания каталога **C:\test** и всех `*.txt` файлов. Объекты отправляются по конвейеру в `Sort-Object` командлет.
`Sort-Object` использует параметр **Property** с хэш-таблицей для определения интервала времени каждого файла между **CreationTime** и **LastWriteTime** . Параметр **Descending** имеет значение, чтобы `$False` Сортировать в порядке убывания к кратчайшему диапазону времени.

### Пример 7. Сортировка имен в текстовом файле

В этом примере показано, как отсортировать список из текстового файла. Исходный файл отображается в виде несортированного списка. `Sort-Object` Сортирует содержимое, а затем сортирует содержимое с **уникальным** параметром, который удаляет дубликаты.

```
PS> Get-Content -Path C:\Test\ServerNames.txt
localhost
server01
server25
LOCALHOST
Server19
server3
localhost

PS> Get-Content -Path C:\Test\ServerNames.txt | Sort-Object
localhost
LOCALHOST
localhost
server01
Server19
server25
server3

PS> Get-Content -Path C:\Test\ServerNames.txt | Sort-Object -Unique
localhost
server01
Server19
server25
server3
```

`Get-Content`Командлет использует параметр **path** , чтобы указать каталог и имя файла. Файл **ServerNames.txt** содержит Несортированный список имен компьютеров.

`Get-Content`Командлет использует параметр **path** , чтобы указать каталог и имя файла. Файл **ServerNames.txt** содержит Несортированный список имен компьютеров. Объекты отправляются по конвейеру в `Sort-Object` командлет. `Sort-Object` Сортирует список в порядке по умолчанию (по возрастанию).

`Get-Content`Командлет использует параметр **path** , чтобы указать каталог и имя файла. Файл **ServerNames.txt** содержит Несортированный список имен компьютеров. Объекты отправляются по конвейеру в `Sort-Object` командлет. `Sort-Object` использует параметр **UNIQUE** для удаления повторяющихся имен компьютеров. Список сортируется в порядке по умолчанию (по возрастанию).

### Пример 8. Сортировка строки в виде целого числа

В этом примере показано, как выполнить сортировку текстового файла, содержащего строковые объекты, в виде целых чисел. Можно отправить каждую команду вниз по конвейеру в `Get-Member` и убедиться, что объекты являются строками, а не целыми числами. В этих примерах `ProductId.txt` файл содержит Несортированный список номеров продуктов.

В первом примере `Get-Content` получает содержимое файла и линий каналов в `Sort-Object` командлет. `Sort-Object` Сортирует строковые объекты в возрастающем порядке.

```
PS> Get-Content -Path C:\Test\ProductId.txt | Sort-Object
0
1
12345
1500
2
2800
3500
4100
500
6200
77
88
99999

PS> Get-Content -Path C:\Test\ProductId.txt | Sort-Object {[int]$_}
0
1
2
77
88
500
1500
2800
3500
4100
6200
12345
99999
```

Во втором примере `Get-Content` получает содержимое файла и линий каналов в `Sort-Object` командлет. `Sort-Object` использует блок скрипта для преобразования строк в целые числа. В примере кода `[int]` преобразует строку в целое число и `$_` представляет каждую строку в том виде, в котором она поступает из конвейера. Целочисленные объекты отправляются по конвейеру в `Sort-Object` командлет.
`Sort-Object` Сортирует целочисленные объекты в числовом порядке.

`Get-Content`Командлет использует параметр **path** , чтобы указать каталог и имя файла. Файл **ProductId.txt** содержит Несортированный список номеров продуктов. Строковые объекты отправляются в командлет по конвейеру `ForEach-Object` . `ForEach-Object` использует блок скрипта для преобразования строк в целые числа. В примере кода `[int]` преобразует строку в целое число и `$_` представляет каждую строку в том виде, в котором она поступает из конвейера. Целочисленные объекты отправляются по конвейеру в `Sort-Object` командлет. `Sort-Object` Сортирует целочисленные объекты в числовом порядке.
## PARAMETERS

### -CaseSensitive

Указывает, что при сортировке учитывается регистр. По умолчанию сортировка выполняется без учета регистра.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Case-insensitive
Accept pipeline input: False
Accept wildcard characters: False
```

### -Culture

Указывает конфигурацию культуры, используемую для сортировки. Используется `Get-Culture` для вывода конфигурации языка и региональных параметров системы.

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

### -По убыванию

Указывает, что `Sort-Object` сортирует объекты в порядке убывания. По умолчанию результаты сортируются по возрастанию.

Для сортировки нескольких свойств с различными порядками сортировки используйте хэш-таблицу. Например, с помощью хэш-таблицы можно отсортировать одно свойство в возрастающем порядке и другое свойство в порядке убывания.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Ascending
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Чтобы отсортировать объекты, отправьте их по конвейеру в `Sort-Object` . При использовании параметра **InputObject** для отправки коллекции элементов `Sort-Object` получает один объект, представляющий коллекцию. Поскольку один объект не может быть отсортирован, `Sort-Object` возвращает всю коллекцию без изменений.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Property

Указывает имена свойств, которые `Sort-Object` используются для сортировки объектов. Разрешено использовать подстановочные знаки.
Объекты сортируются на основе значений свойств. Если свойство не задано, `Sort-Object` сортируется на основе свойств по умолчанию для типа объекта или самих объектов.

Несколько свойств можно сортировать в возрастающем порядке, по убыванию или в сочетании порядка сортировки. При указании нескольких свойств объекты сортируются по первому свойству. Если для первого свойства несколько объектов имеют одинаковое значение, эти объекты сортируются по второму свойству. Это продолжается до тех пор, пока не закончатся все указанные свойства или группы объектов.

Значение параметра **Свойства** может быть вычисляемым свойством. Чтобы создать вычисляемое свойство, используйте хэш-таблицу.

Ниже приведены допустимые ключи для хэш-таблицы.

- `expression` - `<string>` или `<script block>`
- `ascending` ни `descending` - `<boolean>`

Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: Default properties
Accept pipeline input: False
Accept wildcard characters: True
```

### — Уникальный

Указывает, что `Sort-Object` устраняет повторяющиеся значения и возвращает только уникальные элементы коллекции. Первый экземпляр уникального значения включается в отсортированные выходные данные.

**Уникальный** регистр не учитывается. Строки, которые различаются только регистром символов, считаются одинаковыми.
Например, символ и символ.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: All
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Management.Automation.PSObject

Объекты, которые должны быть отсортированы, можно передать по конвейеру `Sort-Object` .

## Выходные данные

### System.Management.Automation.PSObject

`Sort-Object` Возвращает отсортированные объекты.

## ПРИМЕЧАНИЯ

`Sort-Object`Командлет сортирует объекты на основе свойств, указанных в команде, или свойств сортировки по умолчанию для типа объекта. Свойства сортировки по умолчанию определяются с помощью `PropertySet` имени `DefaultKeyPropertySet` в `types.ps1xml` файле. Дополнительные сведения см. в разделе [about_Types.ps1XML](/powershell/module/Microsoft.PowerShell.Core/About/about_Types.ps1xml).

Если объект не имеет одного из указанных свойств, значение свойства для этого объекта интерпретируется `Sort-Object` как **null** и помещается в конец порядка сортировки.

Если свойства сортировки недоступны, PowerShell пытается сравнить сами объекты.
`Sort-Object` использует метод **Compare** для каждого свойства. Если свойство не реализует интерфейс **IComparable** , командлет преобразует значение свойства в строку и использует метод **Compare** для **System. String** . Дополнительные сведения см. в разделе [метод PSObject. CompareTo (Object)](/dotnet/api/system.management.automation.psobject.compareto).

При сортировке по перечисляемому свойству, такому как **Status** , `Sort-Object` сортирует их по значениям перечисления. Для служб Windows **Остановка** имеет значение **1** , а значение " **работает** " равно **4** .
**Остановлена** сортировка перед **выполнением** из-за перечислимых значений. Дополнительные сведения см. в разделе [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).

## Связанные ссылки

[about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)

[Compare-Object](Compare-Object.md)

[ForEach-Object](../Microsoft.PowerShell.Core/ForEach-Object.md)

[Group-Object](Group-Object.md)

[Measure-Object;](Measure-Object.md)

[New-Object](New-Object.md)

[Select-Object](Select-Object.md)

[Tee-Object](Tee-Object.md)
