---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-content?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Content
ms.openlocfilehash: 951edd4219b3d35530b691be9faa8595da297b5c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228834"
---
# Get-Content

## Краткий обзор
Получает содержимое элемента в указанном расположении.

## SYNTAX

### Путь (по умолчанию)

```
Get-Content [-ReadCount <Int64>] [-TotalCount <Int64>] [-Tail <Int32>] [-Path] <String[]>
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force] [-Credential <PSCredential>]
 [-Delimiter <String>] [-Wait] [-Raw] [-Encoding <Encoding>] [-AsByteStream] [-Stream <String>]
 [<CommonParameters>]
```

### LiteralPath

```
Get-Content [-ReadCount <Int64>] [-TotalCount <Int64>] [-Tail <Int32>] -LiteralPath <String[]>
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Force] [-Credential <PSCredential>]
 [-Delimiter <String>] [-Wait] [-Raw] [-Encoding <Encoding>] [-AsByteStream] [-Stream <String>]
 [<CommonParameters>]
```

## DESCRIPTION

`Get-Content`Командлет возвращает содержимое элемента в расположении, указанном путем, например текст в файле или содержимое функции. Для файлов содержимое считывается по одной строке за раз и возвращает коллекцию объектов, каждая из которых представляет строку содержимого.

Начиная с версии PowerShell 3,0, `Get-Content` может также получить указанное число строк с начала или с конца элемента.

## Примеры

### Пример 1. получение содержимого текстового файла

Этот пример получает содержимое файла в текущем каталоге. `LineNumbers.txt`Файл содержит 100 строк в формате, **это строка X** и используется в нескольких примерах.

```powershell
1..100 | ForEach-Object { Add-Content -Path .\LineNumbers.txt -Value "This is line $_." }
Get-Content -Path .\LineNumbers.txt
```

```Output
This is Line 1
This is Line 2
...
This is line 99.
This is line 100.
```

Значения массива 1-100 отправляются в командлет по конвейеру `ForEach-Object` . `ForEach-Object` использует блок скрипта с `Add-Content` командлетом для создания `LineNumbers.txt` файла. Переменная `$_` представляет значения массива, так как каждый объект отправляется по конвейеру. `Get-Content`Командлет использует параметр **path** для указания `LineNumbers.txt` файла и отображает содержимое в консоли PowerShell.

### Пример 2. Ограничение числа строк Get-Content возвратов

Эта команда возвращает первые пять строк файла. Параметр **totalCount** используется для получения первых пяти строк содержимого. В этом примере используется `LineNumbers.txt` файл, созданный в примере 1.

```powershell
Get-Content -Path .\LineNumbers.txt -TotalCount 5
```

```Output
This is Line 1
This is Line 2
This is Line 3
This is Line 4
This is Line 5
```

### Пример 3. получение определенной строки содержимого из текстового файла

Эта команда возвращает определенное количество строк из файла, а затем отображает только последнюю строку этого содержимого. Параметр **totalCount** получает первые 25 строк содержимого. В этом примере используется `LineNumbers.txt` файл, созданный в примере 1.

```powershell
(Get-Content -Path .\LineNumbers.txt -TotalCount 25)[-1]
```

```Output
This is Line 25
```

`Get-Content`Команда заносится в круглые скобки, чтобы команда была выполнена перед переходом к следующему шагу. `Get-Content`Возвращает массив строк. Это позволяет добавить нотацию индекса после круглых скобок для получения определенного номера строки. В этом случае `[-1]` индекс задает последний индекс в возвращенном массиве из 25 полученных строк.

### Пример 4. Получение последней строки текстового файла

Эта команда получает первую строку и последнюю строку содержимого из файла. В этом примере используется `LineNumbers.txt` файл, созданный в примере 1.

```powershell
Get-Item -Path .\LineNumbers.txt | Get-Content -Tail 1
```

```Output
This is Line 100
```

В этом примере используется `Get-Item` командлет, чтобы продемонстрировать, что можно передать файлы в `Get-Content` параметр. Параметр **tail** получает последнюю строку файла. Этот метод выполняется быстрее, чем получение всех строк и использование `[-1]` нотации индекса.

### Пример 5. получение содержимого альтернативного потока данных

В этом примере описывается использование параметра **Stream** для получения содержимого альтернативного потока данных для файлов, хранящихся на томе NTFS Windows. В этом примере `Set-Content` командлет используется для создания примера содержимого в файле с именем `Stream.txt` .

```powershell
Set-Content -Path .\Stream.txt -Value 'This is the content of the Stream.txt file'
# Specify a wildcard to the Stream parameter to display all streams of the recently created file.
Get-Item -Path .\Stream.txt -Stream *
```

```Output
PSPath        : Microsoft.PowerShell.Core\FileSystem::C:\Test\Stream.txt::$DATA
PSParentPath  : Microsoft.PowerShell.Core\FileSystem::C:\Test
PSChildName   : Stream.txt::$DATA
PSDrive       : C
PSProvider    : Microsoft.PowerShell.Core\FileSystem
PSIsContainer : False
FileName      : C:\Test\Stream.txt
Stream        : :$DATA
Length        : 44
```

```powershell
# Retrieve the content of the primary, or $DATA stream.
Get-Content -Path .\Stream.txt -Stream $DATA
```

```Output
This is the content of the Stream.txt file
```

```powershell
# Use the Stream parameter of Add-Content to create a new Stream containing sample content.
Add-Content -Path .\Stream.txt -Stream NewStream -Value 'Added a stream named NewStream to Stream.txt'
# Use Get-Item to verify the stream was created.
Get-Item -Path .\Stream.txt -Stream *
```

```Output
PSPath        : Microsoft.PowerShell.Core\FileSystem::C:\Test\Stream.txt::$DATA
PSParentPath  : Microsoft.PowerShell.Core\FileSystem::C:\Test
PSChildName   : Stream.txt::$DATA
PSDrive       : C
PSProvider    : Microsoft.PowerShell.Core\FileSystem
PSIsContainer : False
FileName      : C:\Test\Stream.txt
Stream        : :$DATA
Length        : 44

PSPath        : Microsoft.PowerShell.Core\FileSystem::C:\Test\Stream.txt:NewStream
PSParentPath  : Microsoft.PowerShell.Core\FileSystem::C:\Test
PSChildName   : Stream.txt:NewStream
PSDrive       : C
PSProvider    : Microsoft.PowerShell.Core\FileSystem
PSIsContainer : False
FileName      : C:\Test\Stream.txt
Stream        : NewStream
Length        : 46
```

```powershell
# Retrieve the content of your newly created Stream.
Get-Content -Path .\Stream.txt -Stream NewStream
```

```Output
Added a stream named NewStream to Stream.txt
```

Параметр **Stream** является динамическим параметром [поставщика FileSystem](../microsoft.powershell.core/about/about_filesystem_provider.md#stream-systemstring).
По умолчанию `Get-Content` получает только данные из первичного или `$DATA` потока. **Потоки** можно использовать для хранения скрытых данных, таких как атрибуты, параметры безопасности или другие данные.

### Пример 6. получение необработанного содержимого

Команды в этом примере получают содержимое файла в виде одной строки, а не массива строк. По умолчанию без **необработанного** динамического параметра содержимое возвращается в виде массива строк, разделенных символами новой строки. В этом примере используется `LineNumbers.txt` файл, созданный в примере.
1.

```powershell
$raw = Get-Content -Path .\LineNumbers.txt -Raw
$lines = Get-Content -Path .\LineNumbers.txt
Write-Host "Raw contains $($raw.Count) lines."
Write-Host "Lines contains $($lines.Count) lines."
```

```Output
Raw contains 1 lines.
Lines contains 100 lines.
```

### Пример 7. Использование фильтров с Get-Content

Можно указать фильтр для `Get-Content` командлета. При использовании фильтров для уточнения параметра **path** необходимо включить конечную звездочку ( `*` ), чтобы указать содержимое пути.

Следующая команда возвращает содержимое всех `*.log` файлов в `C:\Temp` каталоге.

```powershell
Get-Content -Path C:\Temp\* -Filter *.log
```

### Пример 8. получение содержимого файла в виде массива байтов

В этом примере показано, как получить содержимое файла в виде `[byte[]]` одного объекта.

```powershell
$byteArray = Get-Content -Path C:\temp\test.txt -AsByteStream -Raw
Get-Member -InputObject $bytearray
```

```Output
   TypeName: System.Byte[]

Name           MemberType            Definition
----           ----------            ----------
Count          AliasProperty         Count = Length
Add            Method                int IList.Add(System.Object value)
```

Первая команда использует параметр **асбитестреам** для получения потока байтов из файла.
Параметр **RAW** гарантирует, что байты возвращаются в виде `[System.Byte[]]` . Если **необработанный** параметр отсутствовал, возвращаемое значение представляет собой поток байтов, интерпретируемый PowerShell как `[System.Object[]]` .

## PARAMETERS

### -Path

Указывает путь к элементу, где `Get-Content` получается содержимое. Можно использовать подстановочные знаки. Пути должны вести к элементам, а не к контейнерам. Например, нужно указать путь к одному или нескольким файлам, а не путь к каталогу.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -LiteralPath

Указывает путь к одному или нескольким расположениям. Значение **LiteralPath** используется точно так же, как оно введено. Никакие символы не интерпретируются как знаки подстановки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReadCount

Определяет количество строк содержимого, передаваемых по конвейеру за один раз. Значение по умолчанию — 1.
Если значение равно 0 (нулю), все содержимое отправляется за один раз.

Этот параметр не изменяет отображаемое содержимое, но влияет на время его отображения. При увеличении значения параметра **ReadCount** время, необходимое для возврата первой строки, возрастает, но общее время выполнения операции сокращается. Это может сделать заметное различие в больших элементах.

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TotalCount

Указывает число строк от начала файла или другого элемента. По умолчанию используется значение -1 (все строки).

Можно использовать имя параметра **totalCount** или его псевдонимы, **First** или **head** .

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases: First, Head

Required: False
Position: Named
Default value: -1
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### — Хвост

Указывает число строк из конца файла или другого элемента. Можно использовать имя параметра **tail** или его псевдонима **Last** . Этот параметр появился в PowerShell 3,0.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: Last

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Filter

Задает фильтр для уточнения параметра **пути** . Поставщик [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) является единственным установленным поставщиком PowerShell, поддерживающим использование фильтров. Синтаксис для языка фильтра **файловой** системы можно найти в [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).
Фильтры более эффективны, чем другие параметры, так как поставщик применяет их, когда командлет получает объекты, а не использует фильтры PowerShell для объектов после их извлечения.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Include

Указывает в виде массива строк элемент или элементы, которые этот командлет включает в операцию. Значение этого параметра определяет параметр **Path** . Введите элемент пути или шаблон, например `"*.txt"` . Можно использовать подстановочные знаки. Параметр **include** действует только в том случае, если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Exclude

Указывает в виде массива строк элемент или элементы, которые этот командлет исключает в операции.
Значение этого параметра определяет параметр **Path** .

Введите элемент пути или шаблон, например `*.txt` .
Можно использовать подстановочные знаки.

Параметр **Exclude** эффективен, только если команда включает содержимое элемента, например `C:\Windows\*` , где подстановочный знак указывает содержимое `C:\Windows` каталога.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Force

**Force** будет переопределять атрибут только для чтения или создавать каталоги для завершения пути к файлу. Параметр **Force** не пытается изменить разрешения файла или переопределить ограничения безопасности.

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

### -Credential

> [!NOTE]
> Этот параметр не поддерживается какими-либо поставщиками, установленными с помощью PowerShell.
> Чтобы выполнить олицетворение другого пользователя или повысить свои учетные данные при выполнении этого командлета, используйте [команду Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Delimiter

Задает разделитель, который `Get-Content` использует для разделения файла на объекты во время чтения. Значение по умолчанию — `\n` , символ конца строки. При чтении текстового файла `Get-Content` возвращает коллекцию строковых объектов, каждая из которых заканчивается символом конца строки. При вводе разделителя, который не существует в файле, `Get-Content` возвращает весь файл как отдельный объект без разделителей.

С помощью этого параметра можно разделить большой файл на небольшие файлы, указав разделитель файлов в качестве разделителя. Разделитель сохраняется (не удаляется) и становится последним элементом в каждом разделе файла.

**Разделитель** — это динамический параметр, который поставщик **FileSystem** добавляет в `Get-Content` командлет. Этот параметр работает только на дисках с файловой системой.

> [!NOTE]
> В настоящее время, если значение параметра- **разделителя** является пустой строкой, `Get-Content` не возвращает ничего. Это известная проблема. Для принудительного `Get-Content` возврата всего файла в виде одной строки с неограниченным разделителем. Введите значение, которое не существует в файле.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: End-of-line character
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wait

Сохраняет файл открытым после вывода всех существующих строк. Во время ожидания `Get-Content` проверяет файл один раз в секунду и выводит новые строки, если они есть. Можно прервать **Ожидание** , нажав клавиши **CTRL + C** . Ожидание также завершается, если файл удаляется, в этом случае сообщается о неустранимой ошибке.

**Wait** — это динамический параметр, который поставщик FileSystem добавляет в `Get-Content` командлет. Этот параметр работает только на дисках с файловой системой. **Wait** не может сочетаться с **RAW** .

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

### -RAW

Игнорирует символы новой строки и возвращает все содержимое файла в одной строке с сохраненными символами новой строки. По умолчанию символы новой строки в файле используются в качестве разделителей для разделения входных данных на массив строк. Этот параметр появился в PowerShell 3,0.

**RAW** — это динамический параметр, который поставщик **FileSystem** добавляет в `Get-Content` командлет. Этот параметр работает только на дисках файловой системы.

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

### -Encoding

Указывает тип кодировки для целевого файла. Значение по умолчанию — `utf8NoBOM`.

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

Кодирование — это динамический параметр, который поставщик **FileSystem** добавляет в `Get-Content` командлет.
Этот параметр доступен только в дисках файловой системы.

При чтении из двоичных файлов и записи в них используйте параметр **асбитестреам** и значение 0 для параметра **readCount** . Значение **readCount** , равное 0, считывает весь файл в одной операции чтения. Значение **readCount** по умолчанию, равное 1, считывает один байт в каждой операции чтения и преобразует каждый байт в отдельный объект, что приводит к ошибкам при использовании `Set-Content` командлета для записи байтов в файл, если не используется параметр **асбитестреам** .

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

### -Stream

Возвращает содержимое указанного альтернативного файлового потока NTFS из файла. Введите имя потока.
Подстановочные знаки не поддерживаются.

**Stream** — это динамический параметр, который поставщик **FileSystem** добавляет в `Get-Content` командлет.
Этот параметр работает только в дисках файловой системы в системах Windows. Этот параметр впервые появился в Windows PowerShell 3.0.

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

### -Асбитестреам

Указывает, что содержимое должно считываться как поток байтов. Параметр **асбитестреам** появился в Windows PowerShell 6,0.

При использовании параметра **асбитестреам** с параметром **Encoding** возникает предупреждение. Параметр **асбитестреам** игнорирует любую кодировку, и выходные данные возвращаются в виде потока байтов.

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

### Общие параметры

Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` . См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### System.Int64, System.String[], System.Management.Automation.PSCredential

Количество операций чтения, общее число, пути или учетные данные можно передать в `Get-Content` .

## Выходные данные

### System. Byte, System. String

`Get-Content` Возвращает строки или байты. Тип выходных данных зависит от типа содержимого, указанного в качестве входных данных.

## ПРИМЕЧАНИЯ

`Get-Content`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком. Чтобы получить поставщиков в сеансе, используйте `Get-PSProvider` командлет. Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

## Связанные ссылки

[about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[Add-Content](Add-Content.md)

[Clear-Content](Clear-Content.md)

[ForEach-Object](../Microsoft.PowerShell.Core/ForEach-Object.md)

[Get-PSProvider](Get-PSProvider.md)

[Set-Content](Set-Content.md)
