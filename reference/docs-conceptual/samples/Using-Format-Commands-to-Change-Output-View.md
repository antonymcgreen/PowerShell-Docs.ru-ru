---
ms.date: 11/22/2019
keywords: powershell,командлет
title: Использование команд Format для изменения представления вывода
ms.openlocfilehash: f270d5ec5efe5caf506d6a8a45285990996f6ae6
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74417590"
---
# <a name="using-format-commands-to-change-output-view"></a>Использование команд Format для изменения представления вывода

PowerShell предоставляет набор командлетов, которые позволяют контролировать, какие свойства должны отображаться для определенных объектов. Имена всех этих командлетов начинаются глаголом `Format`. Они позволяют выбрать, какие свойства будут отображаться.

```powershell
Get-Command -Verb Format -Module Microsoft.PowerShell.Utility
```

```Output
CommandType     Name               Version    Source
-----------     ----               -------    ------
Cmdlet          Format-Custom      6.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Format-Hex         6.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Format-List        6.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Format-Table       6.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Format-Wide        6.1.0.0    Microsoft.PowerShell.Utility
```

В этой статье описываются командлеты `Format-Wide`, `Format-List` и `Format-Table`.

У каждого типа объектов в PowerShell есть свойства по умолчанию, которые используются, если вы не настроили отображаемые свойства. Для указания свойств, которые нужно отобразить, каждый командлет использует один и тот же параметр **Property**. Так как `Format-Wide` отображает только одно свойство, в параметре **Property** он принимает только одно значение, тогда как `Format-List` и `Format-Table` поддерживают списки с именами свойств.

В этом примере стандартные выходные данные командлета `Get-Process` показывают, что работают два экземпляра Internet Explorer.

```powershell
Get-Process -Name iexplore
```

Для объектов **Process** по умолчанию применяется формат со следующими свойствами.

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     32    25.52      10.25      13.11   12808   1 iexplore
     52    11.46      26.46       3.55   21748   1 iexplore
```

## <a name="using-format-wide-for-single-item-output"></a>Применение командлета Format-Wide для вывода с одним элементом

По умолчанию командлет `Format-Wide` отображает только свойство по умолчанию для объекта. Данные, связанные с каждым объектом, отображаются в одном столбце:

```powershell
Get-Command -Verb Format | Format-Wide
```

```Output
Format-Custom          Format-Hex
Format-List            Format-Table
Format-Wide
```

Можно также задать свойство, отличное от используемого по умолчанию:

```powershell
Get-Command -Verb Format | Format-Wide -Property Noun
```

```Output
Custom                 Hex
List                   Table
Wide
```

### <a name="controlling-format-wide-display-with-column"></a>Настройка отображения командлета Format-Wide с помощью параметра Column

С помощью командлета `Format-Wide` одновременно можно отобразить только одно свойство. Это удобно для отображения больших списков в нескольких столбцах.

```powershell
Get-Command -Verb Format | Format-Wide -Property Noun -Column 3
```

```Output
Custom                 Hex                  List
Table                  Wide

```

## <a name="using-format-list-for-a-list-view"></a>Использование командлета Format-List для представления в виде списка

Командлет `Format-List` показывает объект в виде списка, в котором каждое свойство снабжено меткой и отображается в отдельной строке:

```powershell
Get-Process -Name iexplore | Format-List
```

```Output
Id      : 12808
Handles : 578
CPU     : 13.140625
SI      : 1
Name    : iexplore

Id      : 21748
Handles : 641
CPU     : 3.59375
SI      : 1
Name    : iexplore
```

Можно указать произвольное число свойств:

```powershell
Get-Process -Name iexplore | Format-List -Property ProcessName,FileVersion,StartTime,Id
```

```Output
ProcessName : iexplore
FileVersion : 11.00.18362.1 (WinBuild.160101.0800)
StartTime   : 10/22/2019 11:23:58 AM
Id          : 12808

ProcessName : iexplore
FileVersion : 11.00.18362.1 (WinBuild.160101.0800)
StartTime   : 10/22/2019 11:23:57 AM
Id          : 21748
```

### <a name="getting-detailed-information-by-using-format-list-with-wildcards"></a>Получение подробных сведений с помощью подстановочных знаков в командлете Format-List

Командлет `Format-List` позволяет использовать подстановочные знаки в качестве значения параметра **Property**. Это дает возможность отображать подробные сведения. Часто объекты содержат больше информации, чем необходимо. Поэтому PowerShell по умолчанию выводит значения не всех свойств. Чтобы вывести список всех свойств объекта, используйте команду `Format-List -Property *`. Следующая команда формирует более 60 строк выходных данных для одного процесса:

```powershell
Get-Process -Name iexplore | Format-List -Property *
```

Команда `Format-List` полезна для вывода подробных сведений, но для получения сведений с большим числом элементов обычно удобнее использовать упрощенное табличное представление.

## <a name="using-format-table-for-tabular-output"></a>Применение командлета Format-Table для табличного вывода

Если вызвать командлет `Format-Table` без указания имен свойств для форматирования вывода команды `Get-Process`, вы получите такие же выходные данные, как и без командлета `Format`. По умолчанию PowerShell отображает объекты **Process** в табличном формате.

```powershell
Get-Service -Name win* | Format-Table
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  WinDefend          Windows Defender Antivirus Service
Running  WinHttpAutoProx... WinHTTP Web Proxy Auto-Discovery Se...
Running  Winmgmt            Windows Management Instrumentation
Running  WinRM              Windows Remote Management (WS-Manag...
```

### <a name="improving-format-table-output-autosize"></a>Улучшение вывода командлета Format-Table (параметр AutoSize)

Хотя табличное представление и полезно при выводе большого количества сведений, интерпретация данных может вызвать затруднения, если экран слишком узок и не вмещает все данные. В предыдущем примере выходные данные усекаются. Если указать параметр **AutoSize** при выполнении команды `Format-Table`, PowerShell вычислит ширину столбцов на основе размера отображаемых данных. Это повышает удобство чтения столбцов.

```powershell
Get-Service -Name win* | Format-Table -AutoSize
```

```Output
Status  Name                DisplayName
------  ----                -----------
Running WinDefend           Windows Defender Antivirus Service
Running WinHttpAutoProxySvc WinHTTP Web Proxy Auto-Discovery Service
Running Winmgmt             Windows Management Instrumentation
Running WinRM               Windows Remote Management (WS-Management)
```

Командлет `Format-Table` и в этом случае может усекать данные, но теперь только на правой границе экрана. Свойствам, за исключением последнего отображаемого, выделяется столько места, сколько нужно для корректного вывода самого длинного элемента данных.

```powershell
Get-Service -Name win* | Format-Table -Property Name,Status,StartType,DisplayName,DependentServices -AutoSize
```

```Output
Name                 Status StartType DisplayName                               DependentServi
                                                                                ces
----                 ------ --------- -----------                               --------------
WinDefend           Running Automatic Windows Defender Antivirus Service        {}
WinHttpAutoProxySvc Running    Manual WinHTTP Web Proxy Auto-Discovery Service  {NcaSvc, iphl…
Winmgmt             Running Automatic Windows Management Instrumentation        {vmms, TPHKLO…
WinRM               Running Automatic Windows Remote Management (WS-Management) {}
```

Команда `Format-Table` предполагает, что свойства перечислены в порядке важности. Поэтому она пытается полностью отобразить значения свойств, которые указаны в начале списка. Если команда `Format-Table` не может отобразить все свойства, она удаляет из представления некоторые столбцы. Это поведение можно увидеть в предыдущем примере для свойства **DependentServices**.

### <a name="wrapping-format-table-output-in-columns-wrap"></a>Перенос на следующую строку вывода командлета Format-Table в столбцах (параметр Wrap)

Длинные данные командлета `Format-Table` можно принудительно переносить на несколько строк в пределах столбца с помощью параметра **Wrap**. Использование параметра **Wrap** не всегда приводит к ожидаемому результату, так как без параметра **AutoSize** он применяет параметры по умолчанию:

```powershell
Get-Service -Name win* | Format-Table -Property Name,Status,StartType,DisplayName,DependentServices -Wrap
```

```Output
Name                 Status StartType DisplayName                               DependentServi
                                                                                ces
----                 ------ --------- -----------                               --------------
WinDefend           Running Automatic Windows Defender Antivirus Service        {}
WinHttpAutoProxySvc Running    Manual WinHTTP Web Proxy Auto-Discovery Service  {NcaSvc,
                                                                                iphlpsvc}
Winmgmt             Running Automatic Windows Management Instrumentation        {vmms,
                                                                                TPHKLOAD,
                                                                                SUService,
                                                                                smstsmgr…}
WinRM               Running Automatic Windows Remote Management (WS-Management) {}
```

Использование параметра **Wrap** без других параметров не очень замедляет обработку. Но применение параметра **AutoSize** к рекурсивному выводу списка файлов в каталоге со сложной структурой может потребовать значительного времени и потреблять много памяти.

Если загрузка системы для вашего сценария не критична, параметр **AutoSize** хорошо сочетается с параметром **Wrap**.
В этом случае ширина первых столбцов также позволяет выводить элементы в одной строке, а последний столбец при необходимости разбивается на несколько строк.

> [!NOTE]
> Возможно, некоторые столбцы не попадут в представление, если первым будет указан самый широкий столбец. Для получения лучших результатов выводите первыми элементы данных наименьшего объема.

В следующем примере первыми указаны наибольшие по размеру свойства.

```powershell
Get-Process -Name iexplore | Format-Table -Wrap -AutoSize -Property FileVersion,Path,Name,Id
```

Даже при использовании переноса строк столбец **Id** пришлось исключить:

```Output
FileVersion                          Path                                                  Nam
                                                                                           e
-----------                          ----                                                  ---
11.00.18362.1 (WinBuild.160101.0800) C:\Program Files (x86)\Internet Explorer\IEXPLORE.EXE iex
                                                                                           plo
                                                                                           re
11.00.18362.1 (WinBuild.160101.0800) C:\Program Files\Internet Explorer\iexplore.exe       iex
                                                                                           plo
                                                                                           re
```

### <a name="organizing-table-output--groupby"></a>Организация табличного вывода (параметр -GroupBy)

Другим полезным параметром управления табличным выводом является **GroupBy**. Длинные табличные списки особенно тяжелы для сравнения. Параметр **GroupBy** группирует выходные данные в соответствии со значением свойства. Например, можно сгруппировать службы по параметру **StartType**, чтобы упростить проверку, но исключить значение **StartType** из списка отображаемых свойств:

```powershell
Get-Service -Name win* | Sort-Object StartType | Format-Table -GroupBy StartType
```

```Output
   StartType: Automatic
Status   Name               DisplayName
------   ----               -----------
Running  WinDefend          Windows Defender Antivirus Service
Running  Winmgmt            Windows Management Instrumentation
Running  WinRM              Windows Remote Management (WS-Managem…

   StartType: Manual
Status   Name               DisplayName
------   ----               -----------
Running  WinHttpAutoProxyS… WinHTTP Web Proxy Auto-Discovery Serv…
```
