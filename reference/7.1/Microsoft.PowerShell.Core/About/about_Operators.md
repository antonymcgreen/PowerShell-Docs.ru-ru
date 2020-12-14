---
description: Описание операторов, поддерживаемых PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 10/28/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_operators?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Operators
ms.openlocfilehash: 6f1c87ff7d15190b88d46338b60100057b576f3f
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "94889765"
---
# <a name="about-operators"></a>Об операторах

## <a name="short-description"></a>Краткое описание
Описание операторов, поддерживаемых PowerShell.

## <a name="long-description"></a>Подробное описание

Оператор — это элемент языка, который можно использовать в команде или выражении.
PowerShell поддерживает несколько типов операторов, помогающих управлять значениями.

### <a name="arithmetic-operators"></a>Арифметические операторы

Используйте арифметические операторы ( `+` , `-` ,, `*` `/` , `%` ) для вычисления значений в команде или выражении. С помощью этих операторов можно добавлять, вычитать, умножать или делить значения, а также вычислять остаток (остаток от деления) операции деления.

Оператор сложения объединяет элементы. Оператор умножения возвращает указанное количество копий каждого элемента. Арифметические операторы можно использовать для любого типа .NET, который их реализует, например: `Int` ,,, `String` `DateTime` `Hashtable` и.

Битовые операторы ( `-band` , `-bor` , `-bxor` , `-bnot` , `-shl` , `-shr` ) управляют битовыми шаблонами в значениях.

Дополнительные сведения см. в разделе [about_Arithmetic_Operators](about_Arithmetic_Operators.md).

### <a name="assignment-operators"></a>Операторы присваивания

Операторы присваивания (,,,, `=` `+=` `-=` `*=` `/=` , `%=` ) используются для назначения, изменения или добавления значений переменным. Арифметические операторы можно объединять с оператором присваивания, чтобы присвоить результат арифметической операции переменной.

Дополнительные сведения см. в разделе [about_Assignment_Operators](about_Assignment_Operators.md).

### <a name="comparison-operators"></a>Операторы сравнения

Используйте операторы сравнения ( `-eq` , `-ne` ,,, `-gt` `-lt` `-le` , `-ge` ) для сравнения значений и условий теста. Например, можно сравнить два строковых значения, чтобы определить, равны ли они.

Операторы сравнения также включают операторы, которые находят или заменяют закономерности в тексте. Операторы ( `-match` , `-notmatch` , `-replace` ) используют регулярные выражения, а ( `-like` , `-notlike` ) используют подстановочные знаки `*` .

Операторы сравнения вложений определяют, отображается ли тестовое значение в наборе ссылок ( `-in` ,, `-notin` `-contains` , `-notcontains` ).

Операторы сравнения типов ( `-is` , `-isnot` ) определяют, относится ли объект к данному типу.

Дополнительные сведения см. в разделе [about_Comparison_Operators](about_Comparison_Operators.md).

### <a name="logical-operators"></a>Логические операторы

Используйте логические операторы ( `-and` , `-or` , `-xor` , `-not` , `!` ) для подключения условных операторов к одному сложному условию. Например, логический оператор можно использовать `-and` для создания фильтра объектов с двумя различными условиями.

Дополнительные сведения см. в разделе [about_Logical_Operators](about_logical_operators.md).

### <a name="redirection-operators"></a>Операторы перенаправления

Используйте операторы перенаправления ( `>` ,, `>>` `2>` , `2>>` и `2>&1` ) для отправки выходных данных команды или выражения в текстовый файл. Операторы перенаправления работают как `Out-File` командлет (без параметров), но они также позволяют перенаправлять вывод ошибок в указанные файлы. Можно также использовать `Tee-Object` командлет для перенаправления выходных данных.

Дополнительные сведения см. в разделе [about_Redirection](about_Redirection.md)

### <a name="split-and-join-operators"></a>Операторы Split и Join

`-split`Операторы and `-join` делят и объединяют подстроки. `-split`Оператор разделяет строку на подстроки. `-join`Оператор объединяет несколько строк в одну строку.

Дополнительные сведения см. в разделе [about_Split](about_Split.md) и [about_Join](about_Join.md).

### <a name="type-operators"></a>Операторы работы с типами

Используйте операторы типа ( `-is` , `-isnot` ,), `-as` чтобы найти или изменить тип .NET Framework объекта.

Дополнительные сведения см. в разделе [about_Type_Operators](about_Type_Operators.md).

### <a name="unary-operators"></a>Унарные операторы

Используйте унарные операторы для увеличения или уменьшения числа переменных или свойств объектов, а также для присвоения целочисленных значений положительным или отрицательным числам. Например, чтобы увеличить переменную `$a` с `9` на `10` , введите `$a++` .

### <a name="special-operators"></a>Специальные операторы

Специальные операторы имеют особые варианты использования, которые не помещаются в любую другую группу операторов. Например, Специальные операторы позволяют выполнять команды, изменять тип данных значения или извлекать элементы из массива.

#### <a name="grouping-operator--"></a>Оператор группирования `( )`

Как и в других языках, `(...)` служит для переопределения приоритета операторов в выражениях. Например: `(1 + 2) / 3`

Однако в PowerShell существуют дополнительные поведения.

- `(...)` позволяет разрешить выходные данные _команды_ участвовать в выражении. Пример:

  ```powershell
  PS> (Get-Item *.txt).Count -gt 10
  True
  ```

- При использовании в качестве первого сегмента конвейера, заключение команды или выражения в круглые скобки неизменно приводит к _перечислению_ результата выражения. Если скобки заключают _команду_ в оболочку, она выполняется до завершения со всеми данными, _собранными в памяти_ до отправки результатов через конвейер.

#### <a name="subexpression-operator--"></a>Оператор части выражения `$( )`

Возвращает результат одной или нескольких инструкций. Для одного результата возвращает скалярное значение. Для нескольких результатов возвращает массив. Используйте этот параметр, если требуется использовать выражение в другом выражении. Например, чтобы внедрить результаты команды в строковое выражение.

```powershell
PS> "Today is $(Get-Date)"
Today is 12/02/2019 13:15:20

PS> "Folder list: $((dir c:\ -dir).Name -join ', ')"
Folder list: Program Files, Program Files (x86), Users, Windows
```

#### <a name="array-subexpression-operator--"></a>Оператор части выражения массива `@( )`

Возвращает результат одной или нескольких инструкций в виде массива. Если имеется только один элемент, массив содержит только один элемент.

```powershell
@(Get-CimInstance win32_logicalDisk)
```

#### <a name="hash-table-literal-syntax-"></a>Синтаксис литерала хэш-таблицы `@{}`

Как и часть выражения массива, этот синтаксис используется для объявления хэш-таблицы.
Дополнительные сведения см. в разделе [about_Hash_Tables](about_Hash_Tables.md).

#### <a name="call-operator-"></a>Оператор Call `&`

Выполняет команду, сценарий или блок скрипта. Оператор Call, также известный как «оператор вызова», позволяет выполнять команды, которые хранятся в переменных и представляются строками или блоками сценариев. Оператор Call выполняется в дочерней области. Дополнительные сведения об областях см. в разделе [about_Scopes](about_Scopes.md).

В этом примере команда сохраняется в строке и выполняется с помощью оператора Call.

```
PS> $c = "get-executionpolicy"
PS> $c
get-executionpolicy
PS> & $c
AllSigned
```

Оператор Call не выполняет синтаксический анализ строк. Это означает, что нельзя использовать параметры команды в строке при использовании оператора Call.

```
PS> $c = "Get-Service -Name Spooler"
PS> $c
Get-Service -Name Spooler
PS> & $c
& : The term 'Get-Service -Name Spooler' is not recognized as the name of a
cmdlet, function, script file, or operable program. Check the spelling of
the name, or if a path was included, verify that the path is correct and
try again.
```

Командлет [Invoke-Expression](xref:Microsoft.PowerShell.Utility.Invoke-Expression) может выполнять код, который вызывает ошибки синтаксического анализа при использовании оператора Call.

```
PS> & "1+1"
& : The term '1+1' is not recognized as the name of a cmdlet, function, script
file, or operable program. Check the spelling of the name, or if a path was
included, verify that the path is correct and try again.
At line:1 char:2
+ & "1+1"
+  ~~~~~
    + CategoryInfo          : ObjectNotFound: (1+1:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
PS> Invoke-Expression "1+1"
2
```

Оператор Call можно использовать для выполнения скриптов, использующих их имена файлов. В следующем примере показано имя файла скрипта, содержащего пробелы. При попытке выполнить скрипт PowerShell вместо этого отображает содержимое строки в кавычках, содержащей имя файла. Оператор Call позволяет выполнить содержимое строки, содержащей имя файла.

```
PS C:\Scripts> Get-ChildItem

    Directory: C:\Scripts


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        8/28/2018   1:36 PM             58 script name with spaces.ps1

PS C:\Scripts> ".\script name with spaces.ps1"
.\script name with spaces.ps1
PS C:\Scripts> & ".\script name with spaces.ps1"
Hello World!
```

Дополнительные сведения о блоках скриптов см. в разделе [about_Script_Blocks](about_Script_Blocks.md).

#### <a name="background-operator-"></a>Оператор Background `&`

Запускает конвейер перед в фоновом режиме в задании PowerShell. Этот оператор действует аналогично оператору управления UNIX "амперсанд ( `&` )", который выполняет команду до ее асинхронного выполнения в качестве задания.

Этот оператор функционально эквивалентен `Start-Job` . По умолчанию оператор Background запускает задания в текущем рабочем каталоге вызывающего объекта, который запустил параллельные задачи. В следующем примере демонстрируется базовое использование оператора фонового задания.

```powershell
Get-Process -Name pwsh &
```

Эта команда функционально эквивалентна следующему использованию `Start-Job` :

```powershell
Start-Job -ScriptBlock {Get-Process -Name pwsh}
```

Как и `Start-Job` в случае, `&` оператор Background возвращает `Job` объект. Этот объект можно использовать с `Receive-Job` и `Remove-Job` , точно так же, как если бы вы использовали `Start-Job` для запуска задания.

```powershell
$job = Get-Process -Name pwsh &
Receive-Job $job -Wait
```

```Output

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
      0     0.00     221.16      25.90    6988 988 pwsh
      0     0.00     140.12      29.87   14845 845 pwsh
      0     0.00      85.51       0.91   19639 988 pwsh

```

```powershell
Remove-Job $job
```

`&`Фоновый оператор также является признаком конца инструкции, как и оператором управления UNIX ( `&` ). Это позволяет вызывать дополнительные команды после `&` фонового оператора. В следующем примере демонстрируется вызов дополнительных команд после `&` оператора Background.

```powershell
$job = Get-Process -Name pwsh & Receive-Job $job -Wait
```

```Output

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
      0     0.00     221.16      25.90    6988 988 pwsh
      0     0.00     140.12      29.87   14845 845 pwsh
      0     0.00      85.51       0.91   19639 988 pwsh

```

Это эквивалентно следующему сценарию:

```powershell
$job = Start-Job -ScriptBlock {Get-Process -Name pwsh}
Receive-Job $job -Wait
```

Если требуется выполнить несколько команд, каждая из которых находится в собственном фоновом процессе, но все они находятся на одной строке, просто поместите их `&` между и после каждой команды.

```powershell
Get-Process -Name pwsh & Get-Service -Name BITS & Get-CimInstance -ClassName Win32_ComputerSystem &
```

Дополнительные сведения о заданиях PowerShell см. в разделе [about_Jobs](about_Jobs.md).

#### <a name="cast-operator--"></a>Оператор CAST `[ ]`

Преобразует или ограничивает объекты указанным типом. Если не удается преобразовать объекты, PowerShell выдает ошибку.

```powershell
[DateTime]"2/20/88" - [DateTime]"1/20/88"
[Int] (7/2)
[String] 1 + 0
[Int] '1' + 0
```

Приведение также можно выполнить, если переменная назначена с помощью [нотации приведения](about_Variables.md).

#### <a name="comma-operator-"></a>Запятая, оператор `,`

Как бинарный оператор, запятая создает массив или добавляет к создаваемому массиву. В режиме выражения в качестве унарного оператора запятая создает массив только с одним элементом. Поместите запятую перед элементом.

```powershell
$myArray = 1,2,3
$SingleArray = ,1
Write-Output (,1)
```

Поскольку `Write-Object` предполагает аргумент, выражение должно быть заключено в круглые скобки.

#### <a name="dot-sourcing-operator-"></a>Оператор "точка с точкой" `.`

Выполняет скрипт в текущей области, чтобы все функции, псевдонимы и переменные, создаваемые сценарием, добавлялись в текущую область, переопределяя существующие. Параметры, объявленные сценарием, становятся переменными. Параметры, для которых не было указано значение, становятся переменными без значения. Однако автоматическая переменная `$args` сохраняется.

```powershell
. c:\scripts\sample.ps1 1 2 -Also:3
```

> [!NOTE]
> За оператором «точка» следует пробел. Используйте пробел, чтобы отличить точку от символа точки ( `.` ), который представляет текущий каталог.
>
> В следующем примере сценарий Sample.ps1 в текущем каталоге выполняется в текущей области.
>
> ```powershell
> . .\sample.ps1
> ```

#### <a name="format-operator--f"></a>Format, оператор `-f`

Форматирует строки с помощью метода Format строковых объектов. Введите строку формата слева от оператора и объекты, которые должны быть отформатированы с правой стороны оператора.

```powershell
"{0} {1,-10} {2:N}" -f 1,"hello",[math]::pi
```

```output
1 hello      3.14
```

Если необходимо, чтобы фигурные скобки ( `{}` ) в форматируемой строке были заключены в квадратные скобки, их можно поэкранировать.

```powershell
"{0} vs. {{0}}" -f 'foo'
```

```Output
foo vs. {0}
```

Дополнительные сведения см. в разделе метод [String. Format](/dotnet/api/system.string.format) и [составное форматирование](/dotnet/standard/base-types/composite-formatting).

#### <a name="index-operator--"></a>Оператор индекса `[ ]`

Выбирает объекты из индексированных коллекций, таких как массивы и хэш-таблицы. Индексы массива отсчитываются от нуля, поэтому первый объект индексируется как `[0]` . Для массивов (только) для получения последних значений можно также использовать отрицательные индексы. Хэш-таблицы индексируются по значению ключа.

```
PS> $a = 1, 2, 3
PS> $a[0]
1
PS> $a[-1]
3
```

```powershell
(Get-HotFix | Sort-Object installedOn)[-1]
```

```powershell
$h = @{key="value"; name="PowerShell"; version="2.0"}
$h["name"]
```

```output
PowerShell
```

```powershell
$x = [xml]"<doc><intro>Once upon a time...</intro></doc>"
$x["doc"]
```

```output
intro
-----
Once upon a time...
```

#### <a name="pipeline-operator-"></a>Конвейерный оператор `|`

Отправляет ("pipe") выходные данные команды, предшествующей ей, с помощью команды, следующей за ней. Если выходные данные содержат более одного объекта ("Коллекция"), оператор конвейера посылает объекты по одному за раз.

```powershell
Get-Process | Get-Member
Get-Service | Where-Object {$_.StartType -eq 'Automatic'}
```

#### <a name="pipeline-chain-operators--and-"></a>Операторы цепочки конвейеров `&&` и `||`

Условно выполняет правый конвейер в зависимости от успешности конвейера левой части.

```powershell
# If Get-Process successfully finds a process called notepad,
# Stop-Process -Name notepad is called
Get-Process notepad && Stop-Process -Name notepad
```

```powershell
# If npm install fails, the node_modules directory is removed
npm install || Remove-Item -Recurse ./node_modules
```

Дополнительные сведения см. в разделе [About_Pipeline_Chain_Operators](About_Pipeline_Chain_Operators.md).

#### <a name="range-operator-"></a>Оператор Range `..`

Представляет последовательные целые числа в массиве целых чисел с учетом верхней и нижней границ.

```powershell
1..10
foreach ($a in 1..$max) {Write-Host $a}
```

Можно также создавать диапазоны в обратных последовательностях.

```powershell
10..1
5..-5 | ForEach-Object {Write-Output $_}
```

Начиная с PowerShell 6 оператор Range работает с **символами** , а также с **целыми числами**.

Чтобы создать диапазон символов, заключите эти символы в кавычки.

```powershell
PS> 'a'..'f'
a
b
c
d
e
f
```

```powershell
PS> 'F'..'A'
F
E
D
C
B
A
```

#### <a name="member-access-operator-"></a>Оператор доступа к членам `.`

Обращается к свойствам и методам объекта. Имя члена может быть выражением.

```powershell
$myProcess.peakWorkingSet
(Get-Process PowerShell).kill()
'OS', 'Platform' | Foreach-Object { $PSVersionTable. $_ }
```

#### <a name="static-member-operator-"></a>Статический оператор члена `::`

Вызывает статические свойства и методы класса .NET Framework. Чтобы найти статические свойства и методы объекта, используйте статический параметр `Get-Member` командлета.  Имя члена может быть выражением.

```powershell
[datetime]::Now
'MinValue', 'MaxValue' | Foreach-Object { [int]:: $_ }
```

#### <a name="ternary-operator--if-true--if-false"></a>Оператор Ternary `? <if-true> : <if-false>`

Оператор ternary можно использовать в качестве замены `if-else` инструкции в простых условных случаях.

Дополнительные сведения см. в разделе [about_If](about_If.md).

#### <a name="null-coalescing-operator-"></a>Оператор объединения со значением NULL `??`

Оператор объединения со значением NULL `??` возвращает значение левого операнда, если оно не равно NULL. В противном случае он вычисляет правый операнд и возвращает результат. Оператор `??` не вычисляет правый операнд, если значение левого операнда отлично от NULL.

```powershell
$x = $null
$x ?? 100
```

```Output
100
```

В следующем примере правый операнд не вычисляется.

```powershell
[string] $todaysDate = '1/10/2020'
$todaysDate ?? (Get-Date).ToShortDateString()
```

```Output
1/10/2020
```

#### <a name="null-coalescing-assignment-operator-"></a>Оператор присваивания, объединяющий значения NULL `??=`

Оператор присваивания, объединяющего значение null, `??=` присваивает значение правого операнда левому операнду только в том случае, если левый операнд принимает значение null. Оператор `??=` не вычисляет правый операнд, если значение левого операнда отлично от NULL.

```powershell
$x = $null
$x ??= 100
$x
```

```Output
100
```

В следующем примере правый операнд не вычисляется.

```powershell
[string] $todaysDate = '1/10/2020'
$todaysDate ??= (Get-Date).ToShortDateString()
```

```Output
1/10/2020
```

#### <a name="null-conditional-operators--and-"></a>Условные операторы NULL `?.` и `?[]`

> [!NOTE]
> Этот компонент был перемещен из экспериментального в основной в PowerShell 7,1.

Условный оператор NULL применяет к `?.` операнду доступ к элементу,, или к нему, `?[]` только если этот операнд принимает значение, отличное от NULL; в противном случае возвращается значение null.

Так как в PowerShell символ `?` может быть частью имени переменной, для использования этих операторов требуется формальное указание имени переменной. Поэтому имена переменных необходимо заключать в фигурные скобки `{}`, например `${a}`, в том числе если имена содержат символ `?`: `${a?}`.

В следующем примере возвращается значение **пропнаме** .

```powershell
$a = @{ PropName = 100 }
${a}?.PropName
```

```Output
100
```

Следующий пример вернет значение null, не пытаясь получить доступ к имени члена **пропнаме**.

```powershell
$a = $null
${a}?.PropName
```

Аналогичным образом будет возвращено значение элемента.

```powershell
$a = 1..10
${a}?[0]
```

```Output
1
```

Если операнд имеет значение null, доступ к элементу отсутствует, и возвращается значение null.

```PowerShell
$a = $null
${a}?[0]
```

> [!NOTE]
> Так как в PowerShell символ `?` может быть частью имени переменной, для использования этих операторов требуется формальное указание имени переменной. Поэтому имена переменных необходимо заключать в фигурные скобки `{}`, например `${a}`, в том числе если имена содержат символ `?`: `${a?}`.
>
> Синтаксис имени переменной `${<name>}` не должен путать с `$()` оператором части выражения. Дополнительные сведения см. в разделе Имя переменной в [about_Variables](about_Variables.md#variable-names-that-include-special-characters).

## <a name="see-also"></a>См. также раздел

[about_Arithmetic_Operators](about_Arithmetic_Operators.md)

[about_Assignment_Operators](about_Assignment_Operators.md)

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Logical_Operators](about_logical_operators.md)

[about_Operator_Precedence](about_operator_precedence.md)

[about_Type_Operators](about_Type_Operators.md)

[about_Pipeline_Chain_Operators](about_Pipeline_Chain_Operators.md)

[about_Split](about_Split.md)

[about_Join](about_Join.md)

[about_Redirection](about_Redirection.md)
