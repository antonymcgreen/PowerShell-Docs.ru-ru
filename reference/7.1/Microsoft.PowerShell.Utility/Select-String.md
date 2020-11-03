---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/select-string?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Select-String
ms.openlocfilehash: d231396e0ff167d6af644af008c7a22e9d6f99bb
ms.sourcegitcommit: 9a8bb1b459b5939c95e1f6d9499fcb13d01a58c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "93230486"
---
# Select-String

## Краткий обзор
Выполняет поиск текста в строках и файлах.

## SYNTAX

### Файл (по умолчанию)

```
Select-String [-Culture <String>] [-Pattern] <String[]> [-Path] <String[]> [-SimpleMatch]
 [-CaseSensitive] [-Quiet] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>]
 [-NotMatch] [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### обжектрав

```
Select-String [-Culture <String>] -InputObject <PSObject> [-Pattern] <String[]> -Raw [-SimpleMatch]
 [-CaseSensitive] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>] [-NotMatch]
 [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### Объект

```
Select-String [-Culture <String>] -InputObject <PSObject> [-Pattern] <String[]> [-SimpleMatch]
 [-CaseSensitive] [-Quiet] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>]
 [-NotMatch] [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### филерав

```
Select-String [-Culture <String>] [-Pattern] <String[]> [-Path] <String[]> -Raw [-SimpleMatch]
 [-CaseSensitive] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>] [-NotMatch]
 [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### литералфилерав

```
Select-String [-Culture <String>] [-Pattern] <String[]> -LiteralPath <String[]> -Raw [-SimpleMatch]
 [-CaseSensitive] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>] [-NotMatch]
 [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

### литералфиле

```
Select-String [-Culture <String>] [-Pattern] <String[]> -LiteralPath <String[]> [-SimpleMatch]
 [-CaseSensitive] [-Quiet] [-List] [-NoEmphasis] [-Include <String[]>] [-Exclude <String[]>]
 [-NotMatch] [-AllMatches] [-Encoding <Encoding>] [-Context <Int32[]>] [<CommonParameters>]
```

## DESCRIPTION

`Select-String`Командлет выполняет поиск текстовых и текстовых шаблонов во входных строках и файлах. Вы можете использовать `Select-String` аналогичные возможности **grep** в UNIX или **findstr.exe** в Windows.

`Select-String` основано на строках текста. По умолчанию `Select-String` находит первое совпадение в каждой строке и для каждого совпадения отображает имя файла, номер строки и весь текст в строке, содержащей совпадение. Можно направить `Select-String` Поиск нескольких совпадений в строке, отображаемый текст до и после соответствия или отобразить логическое значение (true или false), указывающее, найдено ли совпадение.

`Select-String` использует сопоставление регулярных выражений, но может также выполнять поиск, который ищет указанный текст в входных данных.

`Select-String` может отображать все текстовые совпадения или останавливаться после первого совпадения во входном файле.
`Select-String` может использоваться для вывода всего текста, не соответствующего указанному шаблону.

Можно также указать, что `Select-String` должна рассчитывать определенную кодировку символов, например при поиске файлов в Юникоде. `Select-String` для определения формата кодирования файла использует символ-отметку (BOM). Если файл не имеет BOM, предполагается, что используется кодировка UTF8.

## Примеры

### Пример 1. Поиск совпадения с учетом регистра

В этом примере учитывается регистр текста, который был отправлен по конвейеру в `Select-String` командлет.

```powershell
'Hello', 'HELLO' | Select-String -Pattern 'HELLO' -CaseSensitive -SimpleMatch
```

Текстовые строки **Hello** и **Hello** отправляются в командлет по конвейеру `Select-String` .
`Select-String` использует параметр **pattern** для указания **Hello** . Параметр **CaseSensitive** указывает, что Регистр должен совпадать только с шаблоном верхнего регистра. **SimpleMatch** является необязательным параметром и указывает, что строка в шаблоне не интерпретируется как регулярное выражение.
`Select-String` Отображает **Hello** в консоли PowerShell.

### Пример 2. Поиск совпадений в текстовых файлах

Эта команда выполняет поиск `.txt` в текущем каталоге всех файлов с расширением имени файла. В выходных данных отображаются строки в этих файлах, содержащие указанную строку.

```powershell
Get-Alias | Out-File -FilePath .\Alias.txt
Get-Command | Out-File -FilePath .\Command.txt
Select-String -Path .\*.txt -Pattern 'Get-'
```

```Output
Alias.txt:8:Alias            cat -> Get-Content
Alias.txt:28:Alias           dir -> Get-ChildItem
Alias.txt:43:Alias           gal -> Get-Alias
Command.txt:966:Cmdlet       Get-Acl
Command.txt:967:Cmdlet       Get-Alias
```

В этом примере `Get-Alias` и `Get-Command` используются с `Out-File` командлетом для создания двух текстовых файлов в текущем каталоге, **Alias.txt** и **Command.txt** .

`Select-String` использует параметр **path** с `*` подстановочным знаком звездочки () для поиска всех файлов в текущем каталоге с расширением имени файла `.txt` . Параметр **pattern** указывает текст, соответствующий **Get-** . `Select-String` Отображает выходные данные в консоли PowerShell. Имя файла и номер строки предшествуют каждой строке содержимого, содержащей соответствие для параметра **pattern** .

### Пример 3. Поиск соответствия шаблону

В этом примере выполняется поиск в нескольких файлах для поиска совпадений для указанного шаблона. В шаблоне используется квантификатор регулярного выражения. Дополнительные сведения см. в разделе [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/About_Regular_Expressions.md).

```powershell
Select-String -Path "$PSHOME\en-US\*.txt" -Pattern '\?'
```

```Output
C:\Program Files\PowerShell\6\en-US\default.help.txt:27:    beginning at https://go.microsoft.com/fwlink/?LinkID=108518.
C:\Program Files\PowerShell\6\en-US\default.help.txt:50:    or go to: https://go.microsoft.com/fwlink/?LinkID=210614
```

`Select-String`Командлет использует два параметра: **path** и **pattern** . Параметр **path** использует переменную `$PSHOME` , которая указывает каталог PowerShell. Оставшаяся часть пути включает подкаталог **en-US** и указывает каждый `*.txt` файл в каталоге. Параметр **pattern** указывает, что соответствует вопросительному знаку ( `?` ) в каждом файле. Обратная косая черта ( `\` ) используется в качестве escape-символа и необходима, поскольку вопросительный знак ( `?` ) является квантификатором регулярного выражения. `Select-String` Отображает выходные данные в консоли PowerShell. Имя файла и номер строки предшествуют каждой строке содержимого, содержащей соответствие для параметра **pattern** .

### Пример 4. Использование Select-String в функции

В этом примере создается функция для поиска шаблона в файлах справки PowerShell. В этом примере функция существует только в сеансе PowerShell. При закрытии сеанса PowerShell функция удаляется. Дополнительные сведения см. в разделе [about_Functions](../Microsoft.PowerShell.Core/About/about_Functions.md).

```
PS> Function Search-Help
>> {
>> $PSHelp = "$PSHOME\en-US\*.txt"
>> Select-String -Path $PSHelp -Pattern 'About_'
>> }
PS>

PS> Search-Help

C:\Program Files\PowerShell\6\en-US\default.help.txt:67:    The titles of conceptual topics begin with "About_".
C:\Program Files\PowerShell\6\en-US\default.help.txt:70:    Get-Help About_<topic-name>
C:\Program Files\PowerShell\6\en-US\default.help.txt:93:    Get-Help About_Modules : Displays help about PowerShell modules.
C:\Program Files\PowerShell\6\en-US\default.help.txt:97:    about_Updatable_Help
```

Функция создается в командной строке PowerShell. `Function`Команда использует имя **поиска-Help** . Нажмите клавишу **Ввод** , чтобы начать Добавление операторов в функцию. В `>>` командной строке добавьте каждую инструкцию и нажмите клавишу **Ввод** , как показано в примере. После добавления закрывающей скобки вы вернетесь в командную строку PowerShell.

Функция содержит две команды. `$PSHelp`Переменная хранит путь к файлам справки PowerShell. `$PSHOME` — это каталог установки PowerShell с подкаталогом **en-US** , который указывает каждый `*.txt` файл в каталоге.

`Select-String`Команда в функции использует **путь** и параметры **шаблона** . Параметр **path** использует `$PSHelp` переменную для получения пути. Параметр **pattern** использует строку **about_** в качестве условия поиска.

Чтобы запустить функцию, введите `Search-Help` . `Select-String`Команда функции отображает выходные данные в консоли PowerShell.

### Пример 5. Поиск строки в журнале событий Windows

В этом примере выполняется поиск строки в журнале событий Windows. Переменная `$_` представляет текущий объект в конвейере. Дополнительные сведения см. в разделе [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).

```powershell
$Events = Get-WinEvent -LogName Application -MaxEvents 50
$Events | Select-String -InputObject {$_.message} -Pattern 'Failed'
```

`Get-WinEvent`Командлет использует параметр " **/l** " для указания журнала приложения. Параметр **MaxEvents** возвращает 50 последних событий из журнала. Содержимое журнала хранится в переменной с именем `$Events` .

`$Events`Переменная отправляется в командлет по конвейеру `Select-String` . `Select-String` использует параметр **InputObject** . `$_`Переменная представляет текущий объект и `message` является свойством события. **Сбой** параметра **шаблона** , виды цветов строку, и поиск совпадений в `$_.message` . `Select-String` Отображает выходные данные в консоли PowerShell.

### Пример 6. Поиск строки в подкаталогах

В этом примере выполняется поиск заданной текстовой строки в каталоге и всех его подкаталогах.

```powershell
Get-ChildItem -Path C:\Windows\System32\*.txt -Recurse | Select-String -Pattern 'Microsoft' -CaseSensitive
```

`Get-ChildItem` использует параметр **path** для указания **C:\Windows\System32 \* . txt** . **Рекурсивный** параметр включает подкаталоги. Объекты отправляются по конвейеру в `Select-String` .

`Select-String` использует параметр **шаблона** и указывает строку **Microsoft** . Параметр **CaseSensitive** используется для сопоставления с точным регистром строки. `Select-String` Отображает выходные данные в консоли PowerShell.

> [!NOTE]
> В зависимости от ваших разрешений в выходных данных может отображаться сообщение об **отказе в доступе** .

### Пример 7. Поиск строк, не соответствующих шаблону

В этом примере показано, как исключить строки данных, которые не соответствуют шаблону.

```powershell
Get-Command | Out-File -FilePath .\Command.txt
Select-String -Path .\Command.txt -Pattern 'Get', 'Set'  -NotMatch
```

`Get-Command`Командлет отправляет объекты по конвейеру в, `Out-File` чтобы создать файл **Command.txt** в текущем каталоге. `Select-String` использует параметр **path** для указания файла **Command.txt** . Параметр **pattern** указывает **Get** и **Set** в качестве шаблона поиска. Параметр **NotMatch** исключает **Get** и **Set** из результатов.
`Select-String` Отображает выходные данные в консоли PowerShell, которые не включают **Get** или **Set** .

### Пример 8. Поиск строк до и после совпадения

В этом примере показано, как получить строки до и после совпадающего шаблона.

```powershell
Get-Command | Out-File -FilePath .\Command.txt
Select-String -Path .\Command.txt -Pattern 'Get-Computer' -Context 2, 3
```

```Output
  Command.txt:986:Cmdlet          Get-CmsMessage           6.1.0.0    Microsoft.PowerShell.Security
  Command.txt:987:Cmdlet          Get-Command              6.1.2.0    Microsoft.PowerShell.Core
> Command.txt:988:Cmdlet          Get-ComputerInfo         6.1.0.0    Microsoft.PowerShell.Management
  Command.txt:990:Cmdlet          Get-Content              6.1.0.0    Microsoft.PowerShell.Management
  Command.txt:991:Cmdlet          Get-ControlPanelItem     3.1.0.0    Microsoft.PowerShell.Management
  Command.txt:992:Cmdlet          Get-Credential           6.1.0.0    Microsoft.PowerShell.Security
```

`Get-Command`Командлет отправляет объекты по конвейеру в, `Out-File` чтобы создать файл **Command.txt** в текущем каталоге. `Select-String` использует параметр **path** для указания файла **Command.txt** . Параметр **pattern** указывает в качестве шаблона поиска командлет **Get-Computer** . Параметр **context** использует два значения, before и After, и помечает совпадения шаблона в выходных данных с помощью угловой скобки ( `>` ). Параметр **context** выводит две строки перед первым совпадением шаблона и три строки после последнего совпадения шаблона.

### Пример 9. Поиск всех совпадений шаблонов

В этом примере показано, как параметр **аллматчес** находит каждое совпадение шаблона в строке текста. По умолчанию `Select-String` находит только первое вхождение шаблона в строке текста. В этом примере используются свойства объекта, которые обнаруживаются с помощью `Get-Member` командлета.

```
PS> $A = Get-ChildItem -Path "$PSHOME\en-US\*.txt" | Select-String -Pattern 'PowerShell'

PS> $A

C:\Program Files\PowerShell\6\en-US\default.help.txt:3:    PowerShell Help System
C:\Program Files\PowerShell\6\en-US\default.help.txt:6:    Displays help about PowerShell cmdlets and concepts.
C:\Program Files\PowerShell\6\en-US\default.help.txt:9:    PowerShell Help describes PowerShell cmdlets

PS> $A.Matches

Groups   : {0}
Success  : True
Name     : 0
Captures : {0}
Index    : 4
Length   : 10
Value    : PowerShell

PS> $A.Matches.Length

8

PS> $B = Get-ChildItem -Path "$PSHOME\en-US\*.txt" | Select-String -Pattern 'PowerShell' -AllMatches

PS> $B.Matches.Length

9
```

`Get-ChildItem`Командлет использует параметр **path** . Параметр **path** использует переменную `$PSHOME` , которая указывает каталог PowerShell. Оставшаяся часть пути включает подкаталог **en-US** и указывает каждый `*.txt` файл в каталоге. `Get-ChildItem`Объекты хранятся в `$A` переменной. `$A`Переменная отправляется в командлет по конвейеру `Select-String` . `Select-String` использует параметр **pattern** для поиска строки **PowerShell** в каждом файле.

В командной строке PowerShell `$A` отобразится содержимое переменной. Существует строка, содержащая два вхождения строки **PowerShell** .

`$A.Matches`Свойство перечисляет первое вхождение шаблона **PowerShell** в каждой строке.

`$A.Matches.Length`Свойство подсчитывает первое вхождение шаблона **PowerShell** в каждой строке.

`$B`Переменная использует те же `Get-ChildItem` `Select-String` командлеты и, но добавляет параметр **аллматчес** . **Аллматчес** находит каждое вхождение шаблона **PowerShell** в каждой строке. Объекты, хранящиеся в `$A` переменных и, `$B` идентичны.

`$B.Matches.Length`Свойство увеличивается, так как для каждой строки учитывается каждое вхождение шаблона **PowerShell** .

## PARAMETERS

### -Аллматчес

Указывает, что командлет выполняет поиск нескольких совпадений в каждой строке текста. Без этого параметра `Select-String` находит только первое совпадение в каждой строке текста.

При `Select-String` обнаружении нескольких совпадений в строке текста он по-прежнему создает в строке только один объект **MatchInfo** , но свойство Match объекта содержит **Matches** все совпадения.

> [!NOTE]
> Этот параметр игнорируется при использовании в сочетании с параметром **SimpleMatch** . Если вы хотите вернуть все совпадения, а искомый шаблон содержит символы регулярного выражения, необходимо отфильтровать эти символы, а не использовать **SimpleMatch** . Дополнительные сведения о экранировании регулярных выражений см. в разделе [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md) .

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

### -CaseSensitive

Указывает, что в совпадении командлета учитывается регистр. По умолчанию в совпадениях не учитывается регистр.

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

### -Context

Захватывает указанное число строк до и после строки, соответствующей шаблону.

Если в качестве значения этого параметра вы введете одно число, оно будет определять количество записываемых строк до и после совпадения. Если вы укажете два числа, первое из них будет определять количество строк до совпадения, а второе — после совпадения. Например, `-Context 2,3`.

В отображении по умолчанию строки с совпадением обозначаются правой угловой скобкой ( `>` ) (ASCII 62) в первом столбце экрана. Строки без пометок формируют контекст.

Параметр **context** не изменяет число объектов, создаваемых `Select-String` .
`Select-String` создает один объект [MatchInfo](/dotnet/api/microsoft.powershell.commands.matchinfo) для каждого соответствия. Контекст хранится в виде массива строк в свойстве **context** объекта.

Когда выходные данные `Select-String` команды отправляются по конвейеру в другую `Select-String` команду, принимающая команда выполняет поиск только текста в соответствующей строке. Совпадающая строка является значением свойства **line** объекта **MatchInfo** , а не текстом в строках контекста. В результате параметр **контекста** не является допустимым для принимающей `Select-String` команды.

Когда контекст включает совпадение, объект **MatchInfo** для каждого соответствия включает все строки контекста, но перекрывающиеся линии отображаются только один раз на экране.

```yaml
Type: System.Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Culture

Указывает имя языка и региональных параметров для соответствия заданному шаблону. Параметр **culture** должен использоваться с параметром **SimpleMatch** . Поведение по умолчанию использует язык и региональные параметры текущего пространства выполнения PowerShell (сеанса).

Чтобы получить список всех поддерживаемых культур, используйте `Get-Culture -ListAvailable` команду.

Кроме того, этот параметр принимает следующие аргументы:

- CurrentCulture, то есть по умолчанию;
- Порядковый номер, который является нелингвистическим двоичным сравнением;
- Инвариант, который является независимым от языка и региональных параметров.

Команда with обеспечивает `Select-String -Culture Ordinal -CaseSensitive -SimpleMatch` самое быстрое двоичное сравнение.

Параметр **culture** использует заполнение по клавише TAB для прокрутки списка аргументов, задающих доступные языки и региональные параметры. Чтобы получить список всех доступных аргументов, используйте следующую команду:

`(Get-Command Select-String).Parameters.Culture.Attributes.ValidValues`

Дополнительные сведения о свойстве .NET CultureInfo.Name см. в разделе [CultureInfo.Name](/dotnet/api//system.globalization.cultureinfo.name).

Параметр **culture** появился в PowerShell 7.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Culture of the current PowerShell session
Accept pipeline input: False
Accept wildcard characters: False
```

### -Encoding

Указывает тип кодировки для целевого файла. Значение по умолчанию — `utf8NoBOM`.

Для этого параметра допустимы следующие значения:

- `ascii`: Использует кодировку для набора символов ASCII (7-разрядных).
- `bigendianunicode`: Кодируется в формате UTF-16 с обратным порядком байтов.
- `bigendianutf32`: Кодируется в формате UTF-32 с обратным порядком байтов.
- `oem`: Использует кодировку по умолчанию для программ MS-DOS и консолей.
- `unicode`: Кодируется в формате UTF-16 с прямым порядком байтов.
- `utf7`: Кодируется в формате UTF-7.
- `utf8`: Кодируется в формате UTF-8.
- `utf8BOM`: Кодирует в формате UTF-8 с меткой порядка байтов (BOM)
- `utf8NoBOM`: Кодирует в формате UTF-8 без метки порядка байтов (BOM)
- `utf32`: Кодируется в формате UTF-32.

Начиная с PowerShell 6,2, параметр **кодировки** также разрешает числовые идентификаторы зарегистрированных кодовых страниц (например `-Encoding 1251` ,) или строковых имен зарегистрированных кодовых страниц (например `-Encoding "windows-1251"` ,). Дополнительные сведения см. в документации .NET по [кодированию. codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).

> [!NOTE]
> Больше не рекомендуется использовать **UTF-7** *. В PowerShell 7,1 при указании параметра Encoding записывается предупреждение `utf7` . **Encoding**

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### -Exclude

Исключает указанные элементы. Значение этого параметра определяет параметр **Path** . Введите элемент пути или шаблон, например `*.txt` . Разрешено использовать подстановочные знаки.

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

### -Include

Включает указанные элементы. Значение этого параметра определяет параметр **Path** . Введите элемент пути или шаблон, например `*.txt` . Разрешено использовать подстановочные знаки.

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

### -InputObject

Задает текст для поиска. Укажите переменную, содержащую текст, либо введите команду или выражение, которые его возвращают.

Использование параметра **InputObject** не отличается от отправки строк вниз по конвейеру `Select-String` .

При передаче более одной строки в `Select-String` командлет он выполняет поиск указанного текста в каждой строке и возвращает каждую строку, содержащую искомый текст.

При использовании параметра **InputObject** для отправки коллекции строк `Select-String` обрабатывает коллекцию как единую объединенную строку. `Select-String` Возвращает строки в виде единицы, если находит искомый текст в любой строке.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: Object, ObjectRaw
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -List

Из каждого входного файла возвращается только первый экземпляр соответствующего текста. Это наиболее эффективный способ получения списка файлов с содержимым, соответствующим регулярному выражению.

По умолчанию `Select-String` возвращает объект **MatchInfo** для каждого найденного совпадения.

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

### -LiteralPath

Указывает путь к файлам для поиска. Значение параметра **LiteralPath** используется точно так же, как тип. Никакие символы не интерпретируются как знаки подстановки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности. Дополнительные сведения см. в разделе [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).

```yaml
Type: System.String[]
Parameter Sets: LiteralFileRaw, LiteralFile
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Выделение

По умолчанию `Select-String` выделяется строка, соответствующая шаблону, который вы искали с помощью параметра **pattern** . Параметр **выделения** отключает выделение.

Выделение использует отрицательные цвета в зависимости от цветов фона и текста PowerShell. Например, если цвета PowerShell представляют собой черный фон с белым текстом. Выделение представляет собой белый фон с черным текстом.

Этот параметр появился в PowerShell 7.

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

### -NotMatch

Параметр **NotMatch** находит текст, который не соответствует указанному шаблону.

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

### -Path

Указывает путь к файлам для поиска. Разрешено использовать подстановочные знаки. По умолчанию поиск выполняется в локальном каталоге.

Укажите файлы в каталоге, например `log1.txt` , `*.doc` или `*.*` . Если вы укажете только один каталог, команда завершится сбоем.

```yaml
Type: System.String[]
Parameter Sets: File, FileRaw
Aliases:

Required: True
Position: 1
Default value: Local directory
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Pattern

Задает текст для поиска в каждой строке. Значение шаблона рассматривается как регулярное выражение.

Дополнительные сведения о регулярных выражениях см. в разделе [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md).

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Quiet

Указывает, что командлет возвращает логическое значение (true или false) вместо объекта **MatchInfo** . Значение равно true, если шаблон найден. в противном случае значение равно false.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: File, Object, LiteralFile
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -RAW

Приводит к тому, что командлет выводит только совпадающие строки, а не объекты **MatchInfo** . Это приводит к поведению, наиболее похожему на команды Unix **grep** или Windows **findstr.exe** .

Этот параметр появился в PowerShell 7.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ObjectRaw, FileRaw, LiteralFileRaw
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -SimpleMatch

Указывает, что командлет использует простое соответствие, а не сопоставление регулярного выражения. При простое совпадение `Select-String` выполняет поиск текста в параметре **pattern** . Значение параметра **pattern** не интерпретируется как оператор регулярного выражения.

Кроме того, при использовании **SimpleMatch** свойство **Matches** возвращаемого объекта **MatchInfo** является пустым.

> [!NOTE]
> Если этот параметр используется с параметром **аллматчес** , **аллматчес** игнорируется.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Management.Automation.PSObject

Любой объект, имеющий метод **ToString** , можно передать в `Select-String` .

## Выходные данные

### Microsoft. PowerShell. Commands. MatchInfo, System. Boolean, System. String

По умолчанию выходные данные представляют собой набор объектов **MatchInfo** с по одному для каждого найденного совпадения. Если используется параметр **quiet** , то выходным значением является **логическое** значение, указывающее, был ли найден шаблон.
Если используется параметр **RAW** , выходные данные представляют собой набор **строковых** объектов, соответствующих шаблону.

## ПРИМЕЧАНИЯ

`Select-String` аналогичен **grep** в UNIX или **findstr.exe** в Windows.

Псевдоним **СЛС** для `Select-String` командлета появился в PowerShell 3,0.

> [!NOTE]
> В соответствии с [утвержденными командами для команд PowerShell](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands)официальный префикс псевдонима для `Select-*` командлетов — `sc` , а не `sl` . Таким образом, правильный псевдоним для `Select-String` должен иметь значение `scs` , а не `sls` . Это исключение из этого правила.

Чтобы использовать `Select-String` , введите текст, который требуется найти в качестве значения параметра **pattern** . Чтобы указать текст для поиска, используйте следующие критерии.

- Введите текст в строке в кавычках и затем передайте его в `Select-String` .
- Сохраните текстовую строку в переменной, а затем укажите переменную в качестве значения параметра **InputObject** .
- Если текст хранится в файлах, используйте параметр **path** , чтобы указать путь к файлам.

По умолчанию `Select-String` интерпретирует значение параметра **шаблона** как регулярное выражение. Дополнительные сведения см. в разделе [about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md). Для переопределения сопоставления регулярного выражения можно использовать параметр **SimpleMatch** . Параметр **SimpleMatch** находит экземпляры значения параметра **pattern** во входных данных.

Выходом по умолчанию `Select-String` является объект **MatchInfo** , который содержит подробные сведения о совпадениях. Информация в объекте полезна при поиске текста в файлах, так как объекты **MatchInfo** имеют такие свойства, как **filename** и **line** . Если входные данные не находятся в файле, значение этих параметров равно **InputStream** .

Если сведения в объекте **MatchInfo** не нужны, используйте параметр **quiet** . Параметр **quiet** возвращает логическое значение (true или false), указывающее, найдено ли совпадение вместо объекта **MatchInfo** .

При сопоставлении фраз `Select-String` использует текущий язык и региональные параметры, заданные для системы. Чтобы найти текущий язык и региональные параметры, используйте `Get-Culture` командлет.

Чтобы найти свойства объекта **MatchInfo** , введите следующую команду:

`Select-String -Path test.txt -Pattern 'test' | Get-Member | Format-List -Property *`

## Связанные ссылки

[about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[about_Comparison_Operators](../Microsoft.PowerShell.Core/About/about_Comparison_Operators.md)

[about_Functions](../Microsoft.PowerShell.Core/About/about_Functions.md)

[about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[about_Regular_Expressions](../Microsoft.PowerShell.Core/About/about_Regular_Expressions.md)

[Get-Alias](Get-Alias.md)

[Get-ChildItem](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[Get-Command](../Microsoft.PowerShell.Core/Get-Command.md)

[Get-Member](Get-Member.md)

[Get-WinEvent](../Microsoft.PowerShell.Diagnostics/Get-WinEvent.md)

[Out-File](Out-File.md)

