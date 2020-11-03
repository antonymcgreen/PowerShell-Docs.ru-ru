---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 1/8/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-csv?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Csv
ms.openlocfilehash: 6c738c11aaa5131cef0ad0457dc50b376152c1f0
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226110"
---
# Import-Csv

## Краткий обзор
Создает пользовательские объекты, подобные табличным, из элементов в файле с разделителями-запятыми (CSV).

## SYNTAX

### Делимитерпас (по умолчанию)

```
Import-Csv [[-Delimiter] <Char>] [-Path] <String[]> [-Header <String[]>] [-Encoding <Encoding>]
 [<CommonParameters>]
```

### делимитерлитералпас

```
Import-Csv [[-Delimiter] <Char>] -LiteralPath <String[]> [-Header <String[]>] [-Encoding <Encoding>]
 [<CommonParameters>]
```

### културепас

```
Import-Csv [-Path] <String[]> -UseCulture [-Header <String[]>] [-Encoding <Encoding>]
 [<CommonParameters>]
```

### културелитералпас

```
Import-Csv -LiteralPath <String[]> -UseCulture [-Header <String[]>] [-Encoding <Encoding>]
 [<CommonParameters>]
```

## DESCRIPTION

`Import-Csv`Командлет создает пользовательские объекты, подобные табличным, из элементов в CSV-файлах. Каждый столбец в CSV-файле становится свойством пользовательского объекта, а элементы в строках становятся значениями свойств. `Import-Csv` работает с любым CSV-файлом, включая файлы, созданные `Export-Csv` командлетом.

С помощью параметров `Import-Csv` командлета можно указать строку заголовков столбцов и разделитель элементов, а также `Import-Csv` использовать разделитель списка для текущего языка и региональных параметров в качестве разделителя элементов.

Также можно использовать `ConvertTo-Csv` `ConvertFrom-Csv` командлеты и для преобразования объектов в строки CSV (и обратно). Эти командлеты аналогичны `Export-CSV` `Import-Csv` командлетам и, за исключением того, что они не работают с файлами.

Если запись строки заголовка в CSV-файле содержит пустое значение или null, PowerShell вставляет имя строки заголовка по умолчанию и выводит предупреждающее сообщение.

Начиная с PowerShell 6,0, `Import-Csv` теперь поддерживает расширенный формат файла журнала W3C.

## Примеры

### Пример 1. Импорт объектов процессов

В этом примере показано, как экспортировать и импортировать CSV-файл объектов Process.

```powershell
Get-Process | Export-Csv -Path .\Processes.csv
$P = Import-Csv -Path .\Processes.csv
$P | Get-Member
```

```Output
   TypeName: System.Management.Automation.PSCustomObject

Name                       MemberType   Definition
----                       ----------   ----------
Equals                     Method       bool Equals(System.Object obj)
GetHashCode                Method       int GetHashCode()
GetType                    Method       type GetType()
ToString                   Method       string ToString()
BasePriority               NoteProperty string BasePriority=8
Company                    NoteProperty string Company=Microsoft Corporation
...
```

```powershell
$P | Format-Table
```

```Output
Name                   SI Handles VM            WS        PM        NPM    Path
----                   -- ------- --            --        --        ---    ----
ApplicationFrameHost   4  407     2199293489152 15884288  15151104  23792  C:\WINDOWS\system32\ApplicationFrameHost.exe
...
wininit                0  157     2199112204288 4591616   1630208   10376
winlogon               4  233     2199125549056 7659520   2826240   10992  C:\WINDOWS\System32\WinLogon.exe
WinStore.App           4  846     873435136     33652736  26607616  55432  C:\Program Files\WindowsApps\Microsoft.WindowsStore_11712.1001.13.0_x64__8weky...
WmiPrvSE               0  201     2199100219392 8830976   3297280   10632  C:\WINDOWS\system32\wbem\wmiprvse.exe
WmiPrvSE               0  407     2199157727232 18509824  12922880  16624  C:\WINDOWS\system32\wbem\wmiprvse.exe
WUDFHost               0  834     2199310204928 51945472  87441408  24984  C:\Windows\System32\WUDFHost.exe
```

`Get-Process`Командлет отправляет объекты процесса по конвейеру в `Export-Csv` . `Export-Csv`Командлет преобразует объекты процесса в строки CSV и сохраняет строки в файле Processes.csv. `Import-Csv`Командлет импортирует строки CSV из файла Processes.csv.
Строки сохраняются в `$P` переменной. `$P`Переменная отправляется в `Get-Member` командлет, который отображает свойства импортированных строк CSV. `$P`Переменная отправляется в командлет по конвейеру `Format-Table` и отображает объекты.

### Пример 2. Указание разделителя

В этом примере показано, как использовать параметр **разделителя** `Import-Csv` командлета.

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -Delimiter :
$P = Import-Csv -Path .\Processes.csv -Delimiter :
$P | Format-Table
```

`Get-Process`Командлет отправляет объекты процесса по конвейеру в `Export-Csv` . `Export-Csv`Командлет преобразует объекты процесса в строки CSV и сохраняет строки в файле Processes.csv.
Параметр- **Разделитель** используется для указания разделителя с двоеточием. `Import-Csv`Командлет импортирует строки CSV из файла Processes.csv. Строки сохраняются в `$P` переменной. В `$P` переменную отправляется в командлет по конвейеру `Format-Table` .

### Пример 3. Указание текущего языка и региональных параметров для разделителя

В этом примере показано, как использовать `Import-Csv` командлет с параметром **UseCulture** .

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-Process | Export-Csv -Path .\Processes.csv -UseCulture
Import-Csv -Path .\Processes.csv -UseCulture
```

`Get-Culture`Командлет использует вложенные свойства **TextInfo** и **ListSeparator** для получения разделителя списка по умолчанию текущего языка и региональных параметров. `Get-Process`Командлет отправляет объекты процесса по конвейеру в `Export-Csv` . `Export-Csv`Командлет преобразует объекты процесса в строки CSV и сохраняет строки в файле Processes.csv. Параметр **UseCulture** использует разделитель списка по умолчанию текущего языка и региональных параметров. `Import-Csv`Командлет импортирует строки CSV из файла Processes.csv.

### Пример 4. изменение имен свойств в импортированном объекте

В этом примере показано, как использовать параметр **Header** объекта `Import-Csv` для изменения имен свойств в результирующем импортируемом объекте.

```powershell
Start-Job -ScriptBlock { Get-Process } | Export-Csv -Path .\Jobs.csv -NoTypeInformation
$Header = 'State', 'MoreData', 'StatusMessage', 'Location', 'Command', 'StateInfo', 'Finished', 'InstanceId', 'Id', 'Name', 'ChildJobs', 'BeginTime', 'EndTime', 'JobType', 'Output', 'Error', 'Progress', 'Verbose', 'Debug', 'Warning', 'Information'
# Delete the default header from file
$A = Get-Content -Path .\Jobs.csv
$A = $A[1..($A.Count - 1)]
$A | Out-File -FilePath .\Jobs.csv
$J = Import-Csv -Path .\Jobs.csv -Header $Header
$J
```

```Output
State         : Running
MoreData      : True
StatusMessage :
Location      : localhost
Command       : Get-Process
StateInfo     : Running
Finished      : System.Threading.ManualResetEvent
InstanceId    : a259eb63-6824-4b97-a033-305108ae1c2e
Id            : 1
Name          : Job1
ChildJobs     : System.Collections.Generic.List`1[System.Management.Automation.Job]
BeginTime     : 12/20/2018 18:59:57
EndTime       :
JobType       : BackgroundJob
Output        : System.Management.Automation.PSDataCollection`1[System.Management.Automation.PSObject]
Error         : System.Management.Automation.PSDataCollection`1[System.Management.Automation.ErrorRecord]
Progress      : System.Management.Automation.PSDataCollection`1[System.Management.Automation.ProgressRecord]
Verbose       : System.Management.Automation.PSDataCollection`1[System.Management.Automation.VerboseRecord]
Debug         : System.Management.Automation.PSDataCollection`1[System.Management.Automation.DebugRecord]
Warning       : System.Management.Automation.PSDataCollection`1[System.Management.Automation.WarningRecord]
Information   : System.Management.Automation.PSDataCollection`1[System.Management.Automation.InformationRecord]
```

`Start-Job`Командлет запускает фоновое задание, которое выполняется `Get-Process` . Объект задания передается по конвейеру в `Export-Csv` командлет и преобразуется в строку CSV. Параметр **NoTypeInformation** удаляет заголовок сведений о типе из выходных данных CSV и является необязательным в PowerShell Core.
`$Header`Переменная содержит пользовательский заголовок, который заменяет следующие значения по умолчанию: **хасморедата** , **JobStateInfo** , **псбегинтиме** , **псендтиме** и **псжобтипенаме**. `$A`Переменная использует `Get-Content` командлет для получения строки CSV из файла Jobs.csv. `$A`Переменная используется для удаления заголовка по умолчанию из файла. `Out-File`Командлет сохраняет новую версию файла Jobs.csv в `$A` переменной. `Import-Csv`Командлет импортирует файл Jobs.csv и использует параметр **Header** для применения `$Header` переменной. `$J`Переменная содержит импортированный **PSCustomObject** и отображает объект в консоли PowerShell.

### Пример 5. Создание пользовательского объекта с помощью CSV-файла

В этом примере показано, как создать пользовательский объект в PowerShell с помощью CSV-файла.

```powershell
Get-Content -Path .\Links.csv
```

```Output
113207,about_Aliases
113208,about_Arithmetic_Operators
113209,about_Arrays
113210,about_Assignment_Operators
113212,about_Automatic_Variables
113213,about_Break
113214,about_Command_Precedence
113215,about_Command_Syntax
144309,about_Comment_Based_Help
113216,about_CommonParameters
113217,about_Comparison_Operators
113218,about_Continue
113219,about_Core_Commands
113220,about_Data_Section
```

```powershell
$A = Import-Csv -Path .\Links.csv -Header 'LinkID', 'TopicTitle'
$A | Get-Member
```

```Output
   TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
LinkID      NoteProperty string LinkID=113207
TopicTitle  NoteProperty string TopicTitle=about_Aliases
```

```powershell
$A | Where-Object -Property TopicTitle -Like '*alias*'
```

```Output
LinkID TopicTitle
------ ----------
113207 about_Aliases
```

Чтобы создать файл Links.csv, используйте значения, показанные в `Get-Content` выходных данных.

`Get-Content`Командлет отображает файл Links.csv. `Import-Csv`Командлет импортирует файл Links.csv. Параметр **Header** указывает имена свойств **LinkId** и **топиктитле**. Объекты хранятся в `$A` переменной. `Get-Member`Командлет показывает имена свойств из параметра **Header** . `Where-Object`Командлет выбирает объекты со свойством **топиктитле** , которое включает **псевдоним**.

### Пример 6. Импорт CSV-файла, в котором отсутствует значение

В этом примере показано, как `Import-Csv` командлет в PowerShell реагирует, когда строка заголовка в CSV-файле содержит пустое или пустое значение. `Import-Csv` заменяет имя по умолчанию для отсутствующей строки заголовка, которое стало именем свойства объекта, который `Import-Csv` возвращает значение.

```powershell
Get-Content -Path .\Projects.csv
```

```Output
ProjectID,ProjectName,,Completed
13,Inventory,Redmond,True
440,,FarEast,True
469,Marketing,Europe,False
```

```powershell
Import-Csv -Path .\Projects.csv
```

```Output
WARNING: One or more headers were not specified. Default names starting with "H" have been used in place of any missing headers.

ProjectID ProjectName H1      Completed
--------- ----------- --      ---------
13        Inventory   Redmond True
440                   FarEast True
469       Marketing   Europe  False
```

```powershell
(Import-Csv -Path .\Projects.csv).H1
```

```Output
WARNING: One or more headers were not specified. Default names starting with "H" have been used in place of any missing headers.
Redmond
FarEast
Europe
```

Чтобы создать файл Projects.csv, используйте значения, показанные в `Get-Content` выходных данных примера.

`Get-Content`Командлет отображает файл Projects.csv. В строке заголовка отсутствует значение между **имя_проекта** и **Completed**. `Import-Csv`Командлет импортирует файл Projects.csv и отображает предупреждающее сообщение, поскольку **H1** является именем заголовка по умолчанию. `(Import-Csv -Path
.\Projects.csv).H1`Команда возвращает значения свойств **H1** и отображает предупреждение.

## PARAMETERS

### -Delimiter

Задает разделитель для значений свойств в файле CSV.
Разделитель по умолчанию — запятая (,).

Введите символ, например двоеточие (:).
Указание точки с запятой (;) заключите его в одинарные кавычки.

Если в файле указать символ, отличный от действительного разделителя строк, то `Import-Csv` не сможет создать объекты из строк CSV и будет возвращать строки CSV.

```yaml
Type: System.Char
Parameter Sets: DelimiterPath, DelimiterLiteralPath
Aliases:

Required: False
Position: 1
Default value: comma (,)
Accept pipeline input: False
Accept wildcard characters: False
```

### -Encoding

Указывает кодировку для импортированного CSV-файла. Значение по умолчанию — `utf8NoBOM`.

Для этого параметра допустимы следующие значения:

- `ascii`: Использует кодировку для набора символов ASCII (7-разрядных).
- `bigendianunicode`: Кодируется в формате UTF-16 с обратным порядком байтов.
- `oem`: Использует кодировку по умолчанию для программ MS-DOS и консолей.
- `unicode`: Кодируется в формате UTF-16 с прямым порядком байтов.
- `utf7`: Кодируется в формате UTF-7.
- `utf8`: Кодируется в формате UTF-8.
- `utf8BOM`: Кодирует в формате UTF-8 с меткой порядка байтов (BOM)
- `utf8NoBOM`: Кодирует в формате UTF-8 без метки порядка байтов (BOM)
- `utf32`: Кодируется в формате UTF-32.

Начиная с PowerShell 6,2, параметр **кодировки** также разрешает числовые идентификаторы зарегистрированных кодовых страниц (например `-Encoding 1251` ,) или строковых имен зарегистрированных кодовых страниц (например `-Encoding "windows-1251"` ,). Дополнительные сведения см. в документации .NET по [кодированию. codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### -Header

Указывает альтернативную строку заголовков столбцов для импортируемого файла. Заголовок столбца определяет имена свойств объектов, созданных `Import-Csv` .

Введите заголовки столбцов в виде списка с разделителями-запятыми. Не заключайте в кавычки строку заголовка. Заключить заголовок каждого столбца в одинарные кавычки.

Если ввести меньшее количество заголовков столбцов, чем столбцы данных, оставшиеся столбцы данных будут удалены. Если ввести больше заголовков столбцов, чем столбцы данных, то будут созданы дополнительные заголовки столбцов с пустыми столбцами данных.

При использовании параметра **Header** удалите исходную строку заголовков из файла CSV. В противном случае `Import-Csv` создает дополнительный объект на основе элементов в строке заголовка.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LiteralPath

Указывает путь к импортируемому файлу CSV. В отличие от параметра **Path** , значение параметра **LiteralPath** используется в точности так, как вводится. Никакие символы не интерпретируются как знаки подстановки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

```yaml
Type: System.String[]
Parameter Sets: DelimiterLiteralPath, CultureLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Указывает путь к импортируемому файлу CSV.
Можно также передать по конвейеру путь к `Import-Csv` .

```yaml
Type: System.String[]
Parameter Sets: DelimiterPath, CulturePath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -UseCulture

Использует разделитель списка для текущего языка и региональных параметров в качестве разделителя элементов. Чтобы найти разделитель списка для языка и региональных параметров, используйте следующую команду: `(Get-Culture).TextInfo.ListSeparator` .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CulturePath, CultureLiteralPath
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

Можно передать строку, содержащую путь, в `Import-Csv` .

## Выходные данные

### Объект

Этот командлет возвращает объекты, описанные в содержимом CSV-файла.

## ПРИМЕЧАНИЯ

Поскольку импортированные объекты являются версиями CSV типа объекта, они не распознаются и не форматируются с помощью записей форматирования типов PowerShell, которые отформатируют версии объектов, отформатированные не в формате CSV.

Результатом выполнения `Import-Csv` команды является коллекция строк, образующих пользовательский объект, подобный табличному. Каждая строка представляет собой отдельную строку, поэтому для подсчета строк таблицы можно использовать свойство **Count** объекта. Столбцы представляют свойства объекта, а поля строк — значения этих свойств.

Строка заголовков столбцов определяет число столбцов и их имена. Имена столбцов также являются именами свойств объектов. Первая строка интерпретируется как заголовки столбцов, если только не используется параметр **Header** для указания заголовков столбцов. Если в какой-либо строке содержится больше значений, чем в строке заголовков, лишние значения игнорируются.

Если в строке заголовка столбца отсутствует значение или оно содержит значение null или пустое, `Import-Csv` то в качестве заголовка отсутствующего столбца и имени свойства используется **H** , за которым следует число.

В CSV-файле каждый объект представлен списком значений свойств объекта с разделителями-запятыми. Значения свойств преобразуются в строки с помощью метода **ToString ()** объекта, поэтому они представлены именем значения свойства. `Export-Csv` не экспортирует методы объекта.

`Import-Csv` также поддерживает расширенный формат журнала W3C. Строки, начинающиеся с `#` , обрабатываются как комментарии и пропускаются, если комментарий не начинается с `#Fields:` и содержит список имен столбцов с разделителями. В этом случае командлет использует эти имена столбцов. Это стандартный формат для Windows IIS и других журналов веб-сервера. Дополнительные сведения см. в разделе [Расширенный формат файла журнала](https://www.w3.org/TR/WD-logfile.html).

## Связанные ссылки

[ConvertFrom-Csv](ConvertFrom-Csv.md)

[ConvertTo-Csv](ConvertTo-Csv.md)

[Export-Csv](Export-Csv.md)

[Get-Culture](Get-Culture.md)
