---
title: Все, что вы хотели знать об операторе if
description: Как и многие другие языки, PowerShell содержит операторы для условного исполнения кода в сценариях.
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: b6bafb99bfb8ecd0152bae841e5c58d4c27ccd3e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "86469758"
---
# <a name="everything-you-wanted-to-know-about-the-if-statement"></a>Все, что вы хотели знать об операторе `if`

Как и многие другие языки, PowerShell содержит операторы для условного исполнения кода в сценариях. Одним из таких операторов является оператор [if][]. Сегодня мы более подробно поговорим об одной из важнейших команд в PowerShell.

> [!NOTE]
> [Оригинал][] этой статьи впервые был опубликован в блоге автора [@KevinMarquette][]. Группа разработчиков PowerShell благодарит Кевина за то, что он поделился с нами этими материалами. Ознакомьтесь с его блогом на веб-сайте [PowerShellExplained.com][].

## <a name="conditional-execution"></a>Условное выполнение

В сценариях часто требуется принимать решения и применять различные логики в зависимости от этих решений.
Именно это имеется в виду под условным выполнением. У вас есть один оператор или значение для вычисления, а затем вы выполняете другой раздел кода на основе этого вычисления. Именно это и делает оператор `if`.

## <a name="the-if-statement"></a>Инструкция `if`

Ниже приведен простой пример оператора `if`.

```powershell
$condition = $true
if ( $condition )
{
    Write-Output "The condition was true"
}
```

Первое, что делает оператор `if`, — вычисляет выражение в круглых скобках. Если он имеет значение `$true`, то он выполняет `scriptblock` в фигурных скобках. Если значение равнялось `$false`, то этот блок сценария был бы пропущен.

В предыдущем примере оператор `if` только что вычислил переменную `$condition`. Он был равен `$true` и выполнил бы команду `Write-Output` в блоке сценария.

В некоторых языках можно поместить одну строку кода после оператора `if`, чтобы выполнить ее. В PowerShell все не так. Чтобы все работало правильно, необходимо указать полный `scriptblock` с фигурными скобками.

## <a name="comparison-operators"></a>Операторы сравнения

Оператор `if` чаще всего используется для сравнения двух элементов. PowerShell предлагает специальные операторы для различных сценариев сравнения. При использовании оператора сравнения значение в левой части сравнивается со значением в правой части.

### <a name="-eq-for-equality"></a>-eq для "равно"

`-eq` проверяет равенство двух значений, чтобы убедиться в том, что они равны друг другу.

```powershell
$value = Get-MysteryValue
if ( 5 -eq $value )
{
    # do something
}
```

В этом примере я беру известное значение `5` и сравниваю его с моим `$value`, чтобы понять, совпадают ли они.

Один из возможных вариантов использования — проверка состояния значения до того, как выполнено действие с ним. Можно получить службу и убедиться в том, что до вызова `Restart-Service` она имела состояние running.

В других языках, таких как C#, обычно используется `==` для проверки на равенство (например, `5 == $value`), но в PowerShell это невозможно. Еще одна распространенная ошибка, которую делают пользователи, — использование знака равенства (например, `5 = $value`), который зарезервирован для присвоения значений переменным. Если поместить известное значение слева, вероятность ошибки повышается.

Для этого оператора (как и для других) доступно несколько вариантов.

- `-eq` без учета регистра, равенство
- `-ieq` без учета регистра, равенство
- `-ceq` с учетом регистра, равенство

### <a name="-ne-not-equal"></a>-ne "не равно"

Для многих операторов предусмотрен связанный оператор, который выполняет проверку на противоположный результат. `-ne` проверяет, чтобы значения не были равны друг другу.

```powershell
if ( 5 -ne $value )
{
    # do something
}
```

Этот параметр позволяет убедиться в том, что действие выполняется только в том случае, если значение не равно `5`. В качестве одного из полезных примеров его использования можно проверить, имеет ли служба состояние running до того, как пытаться запустить ее.

**Варианты:**

- `-ne` без учета регистра, не равно
- `-ine` без учета регистра, не равно
- `-cne` с учетом регистра, не равно

Это инвертированные варианты `-eq`. Эти типы будут сгруппированы при перечислении вариантов для других операторов.

### <a name="-gt--ge--lt--le-for-greater-than-or-less-than"></a>-gt -ge -lt -le для "больше, чем" или "меньше, чем"

Эти операторы позволяют убедиться в том, что значение больше или меньше другого значения.
`-gt -ge -lt -le` означают GreaterThan, GreaterThanOrEqual, LessThan и LessThanOrEqual.

```powershell
if ( $value -gt 5 )
{
    # do something
}
```

**Варианты:**

- `-gt` "больше, чем"
- `-igt` "больше, чем", без учета регистра
- `-cgt` "больше, чем", с учетом регистра
- `-ge` "больше, чем" или "равно"
- `-ige` "больше, чем" или "равно", без учета регистра
- `-cge` "больше, чем" или "равно", с учетом регистра
- `-lt` "меньше, чем"
- `-ilt` "меньше, чем", без учета регистра
- `-clt` "меньше, чем", с учетом регистра
- `-le` "меньше, чем" или "равно"
- `-ile` "меньше, чем" или "равно", без учета регистра
- `-cle` "меньше, чем" или "равно", с учетом регистра

Я не знаю, зачем для этих операторов использовать параметры с учетом регистра или без учета регистра.

### <a name="-like-wildcard-matches"></a>Сопоставление с использованием подстановочного знака -like

PowerShell использует собственный синтаксис сопоставления шаблонов на основе подстановочных знаков, и его можно сочетать с оператором `-like`. Шаблоны с подстановочными знаками довольно просты.

- `?` сопоставляет любой отдельный символ
- `*` сопоставляет любое число символов

```powershell
$value = 'S-ATX-SQL01'
if ( $value -like 'S-*-SQL??')
{
    # do something
}
```

Важно отметить, что шаблон сопоставляет всю строку. Если необходимо сопоставить данные в середине строки, поместите `*` на обоих концах строки.

```powershell
$value = 'S-ATX-SQL02'
if ( $value -like '*SQL*')
{
    # do something
}
```

**Варианты:**

- `-like` без учета регистра, подстановочный знак
- `-ilike` без учета регистра, подстановочный знак
- `-clike` с учетом регистра, подстановочный знак
- `-notlike` без учета регистра, подстановочный знак, не сопоставлен
- `-inotlike` без учета регистра, подстановочный знак, не сопоставлен
- `-cnotlike` с учетом регистра, подстановочный знак, не сопоставлен

### <a name="-match-regular-expression"></a>Регулярное выражение -match

Оператор `-match` позволяет проверить строку на соответствие регулярному выражению. Используйте этот параметр, если шаблоны с подстановочными знаками не обеспечивают достаточной гибкости.

```powershell
$value = 'S-ATX-SQL01'
if ( $value -match 'S-\w\w\w-SQL\d\d')
{
    # do something
}
```

Шаблон регулярного выражения по умолчанию соответствует данным в любом месте строки. Поэтому можно указать подстроку, которую необходимо сопоставить следующим образом:

```powershell
$value = 'S-ATX-SQL01'
if ( $value -match 'SQL')
{
    # do something
}
```

Регулярные выражения представляют собой сложный язык сами по себе и достойны изучения. Я подробнее расскажу о `-match` и [множестве способов использования регулярных выражений][] в другой статье.

**Варианты:**

- `-match` без учета регистра, регулярное выражение
- `-imatch` без учета регистра, регулярное выражение
- `-cmatch` с учетом регистра, регулярное выражение
- `-notmatch` без учета регистра, регулярное выражение, не сопоставлено
- `-inotmatch` без учета регистра, регулярное выражение, не сопоставлено
- `-cnotmatch` с учетом регистра, регулярное выражение, не сопоставлено

### <a name="-is-of-type"></a>-is относится к типу

Тип значения можно проверить с помощью оператора `-is`.

```powershell
if ( $value -is [string] )
{
    # do something
}
```

Эту возможность можно использовать, если вы работаете с классами или принимаете различные объекты по конвейеру. В качестве входных данных может быть задана служба или имя службы. Затем проверьте, есть ли у вас служба, и получите службу, используя только ее имя.

```powershell
if ( $Service -isnot [System.ServiceProcess.ServiceController] )
{
    $Service = Get-Service -Name $Service
}
```

**Варианты:**

- `-is` относится к типу
- `-isnot` не относится к типу

## <a name="collection-operators"></a>Операторы коллекции

При использовании предыдущих операторов с одним значением результатом является `$true` или `$false`. При работе с коллекцией обработка выполняется несколько другим способом. Каждый элемент в коллекции вычисляется, и оператор возвращает каждое значение, результатом которого является `$true`.

```powershell
PS> 1,2,3,4 -eq 3
3
```

Эта операция по-прежнему работает корректно в операторе `if`. Поэтому оператор возвращает значение, и тогда вся инструкция равна `$true`.

```powershell
$array = 1..6
if ( $array -gt 3 )
{
    # do something
}
```

Здесь есть одна небольшая скрытая трудность, на которую нужно обратить внимание. При использовании оператора `-ne` таким образом легко по ошибке просмотреть логику в обратном направлении. Использование `-ne` с коллекцией возвращает `$true`, если какой-либо элемент в коллекции не совпадает с имеющимся значением.

```powershell
PS> 1,2,3 -ne 4
1
2
3
```

Это может показаться разумным, но у нас есть операторы `-contains` и `-in`, которые более эффективно справятся с этой задачей. При этом `-notcontains` выполняет то, что от него ожидается.

### <a name="-contains"></a>-contains

Оператор `-contains` проверяет коллекцию на наличие вашего значения. После обнаружения совпадения возвращается значение `$true`.

```powershell
$array = 1..6
if ( $array -contains 3 )
{
    # do something
}
```

Это самый удобный способ узнать, содержит ли коллекция ваше значение. При использовании `Where-Object` (или `-eq`) каждый раз выполняется обход всего списка, и работа значительно замедляется.

**Варианты:**

- `-contains` без учета регистра, совпадение
- `-icontains` без учета регистра, совпадение
- `-ccontains` с учетом регистра, совпадение
- `-notcontains` без учета регистра, не сопоставлено
- `-inotcontains` без учета регистра, не сопоставлено
- `-cnotcontains` с учетом регистра, не сопоставлено

### <a name="-in"></a>-in

Оператор `-in` похож на оператор `-contains` за исключением того, что коллекция находится в правой части.

```powershell
$array = 1..6
if ( 3 -in $array )
{
    # do something
}
```

**Варианты:**

- `-in` без учета регистра, совпадение
- `-iin` без учета регистра, совпадение
- `-cin` с учетом регистра, совпадение
- `-notin` без учета регистра, не сопоставлено
- `-inotin` без учета регистра, не сопоставлено
- `-cnotin` с учетом регистра, не сопоставлено

## <a name="logical-operators"></a>Логические операторы

Логические операторы используются для инверсии или объединения других выражений.

### <a name="-not"></a>-not

Оператор `-not` инвертирует выражение из `$false` в `$true` или из `$true` в `$false`. Ниже приведен пример, в котором требуется выполнить действие, когда `Test-Path` равно `$false`.

```powershell
if ( -not ( Test-Path -Path $path ) )
```

Большинство операторов, о которых мы говорили, используют вариант, в котором использование оператора `-not` не требуется. Однако в отдельных случаях это все-таки полезно.

### <a name="-operator"></a>! оператор

Можно использовать `!` как псевдоним для `-not`.

```powershell
if ( -not $value ){}
if ( !$value ){}
```

Как можно заметить, `!` чаще используется теми пользователями, которые переходят на PowerShell с других языков, таких как C#. Я предпочитаю печатать этот оператор, потому что мне его трудно увидеть при быстром просмотре сценариев.

### <a name="-and"></a>-and

Выражения можно объединять с помощью оператора `-and`. В этом случае обе стороны должны быть равны `$true`, чтобы все выражение было равно `$true`.

```powershell
if ( ($age -gt 13) -and ($age -lt 55) )
```

В этом примере `$age` должно быть равно 13 или более для левой части и менее 55 для правой части. Я добавил дополнительные круглые скобки, чтобы выделить эти данные в примере, но это необязательно, если выражение простое. Вот пример без дополнительных скобок.

```powershell
if ( $age -gt 13 -and $age -lt 55 )
```

Вычисления выполняются слева направо. Если первый элемент принимает значение `$false`, он преждевременно завершает работу и правильное сравнение не выполняется. Это удобно, если перед использованием значения необходимо убедиться в том, что оно существует. Например, `Test-Path` выдает ошибку, если присвоить ему путь `$null`.

```powershell
if ( $null -ne $path -and (Test-Path -Path $path) )
```

### <a name="-or"></a>-or

`-or` позволяет указать два выражения и возвращает значение `$true`, если одно из них равно `$true`.

```powershell
if ( $age -le 13 -or $age -ge 55 )
```

Как и в случае с оператором `-and`, вычисление выполняется слева направо. Однако если первая часть равна `$true`, то весь оператор равен `$true` и не обрабатывает оставшуюся часть выражения.

Обратите также внимание на то, как работает синтаксис для этих операторов. Потребуется два отдельных выражения. Я видел, что пользователи пытаются сделать что-то похожее на `$value -eq 5 -or 6`, не понимая, в чем их ошибка.

### <a name="-xor-exclusive-or"></a>-xor (исключающее ИЛИ)

Это немного необычный оператор. `-xor` позволяет принимать равным `$true` только одно выражение. Таким образом, если оба элемента равны `$false` или `$true`, все выражение равно `$false`. Еще один вариант — выражение равно `$true` только в том случае, если результаты выражения отличаются.

Вряд ли кто-то станет вообще использовать этот логический оператор, и я даже не могу придумать хороший пример, зачем я сам стал бы это делать.

## <a name="bitwise-operators"></a>Побитовые операторы

Побитовые операторы выполняют вычисления с битами в значениях и создают новое результирующее значение. Обучение работе с [побитовыми операторами][] не рассматривается в этой статье, однако здесь приведен их перечень.

- `-band` двоичное И
- `-bor` двоичное ИЛИ
- `-bxor` двоичное исключающее ИЛИ
- `-bnot` двоичное НЕ
- `-shl` сдвиг влево
- `-shr` сдвиг вправо

## <a name="powershell-expressions"></a>Выражения PowerShell

В операторе условия можно использовать обычные функции PowerShell.

```powershell
if ( Test-Path -Path $Path )
```

При выполнении `Test-Path` возвращает `$true` или `$false`. Это также относится к командам, которые возвращают другие значения.

```powershell
if ( Get-Process Notepad* )
```

Оператор принимает значение `$true`, если есть возвращаемый процесс, или `$false`, если такой процесс отсутствует. Вполне допустимо использовать выражения конвейера или другие операторы PowerShell:

```powershell
if ( Get-Process | Where Name -eq Notepad )
```

Эти выражения можно объединять друг с другом с помощью операторов `-and` и `-or`, однако, возможно, потребуется использование круглых скобок, чтобы разбить выражения на части.

```powershell
if ( (Get-Process) -and (Get-Service) )
```

### <a name="checking-for-null"></a>Проверка на наличие значения $null

Отсутствие результата или значение `$null` вычисляется как `$false` в операторе `if`. Если выполняется специальная проверка на наличие `$null`, рекомендуется размещать `$null` в левой части.

```powershell
if ( $null -eq $value )
```

При работе со значениями `$null` в PowerShell существует много нюансов. Если вы хотите узнать об этом больше, ознакомьтесь с моей статьей обо [всем, что необходимо знать о $null][].

### <a name="variable-assignment"></a>Присвоение значения переменной

Я чуть не забыл добавить этот раздел, хорошо, что [Прасун Карунан В.][] мне об этом напомнил.

```powershell
if ($process=Get-Process notepad -ErrorAction ignore) {$process} else {$false}
```

Обычно присвоенное переменной значение не передается в конвейер или в консоль. При присвоении переменной в части выражения оно передается в конвейер.

```powershell
PS> $first = 1
PS> ($second = 2)
2
```

Заметили, что присвоение `$first` не создает выходные данные, а присвоение `$second` — создает? Когда присвоение происходит в операторе `if`, оно выполняется точно так же, как присвоение `$second` выше. Далее приведен понятный пример возможного использования.

```powershell
if ( $process = Get-Process Notepad* )
{
    $process | Stop-Process
}
```

Если для `$process` присваивается значение, то работа оператора `$true` и `$process` прекращается.

Убедитесь в том, что вы не путаете его с `-eq`, так как это не проверка на равенство. Это малоизвестная функция, и большинство пользователей даже не представляют, что она так работает.

## <a name="alternate-execution-path"></a>Альтернативный путь выполнения

Оператор `if` позволяет указать действие не только, когда оператор равен `$true`, но и когда он равен `$false`. Именно здесь используется оператор `else`.

### <a name="else"></a>else

При использовании оператора `else` он всегда является последней частью оператора `if`.

```powershell
if ( Test-Path -Path $Path -PathType Leaf )
{
    Move-Item -Path $Path -Destination $archivePath
}
else
{
    Write-Warning "$path doesn't exist or isn't a file."
}
```

В этом примере мы проверяем `$path`, чтобы убедиться в том, что это файл. Если мы найдем файл, мы его переместим. В противном случае мы создаем предупреждение. Этот тип логики ветвления весьма распространен.

### <a name="nested-if"></a>Вложенное IF

Операторы `if` и `else` принимают блок сценария, поэтому мы можем поместить в них любую команду PowerShell, в том числе еще один оператор `if`. Это позволяет использовать гораздо более сложную логику.

```powershell
if ( Test-Path -Path $Path -PathType Leaf )
{
    Move-Item -Path $Path -Destination $archivePath
}
else
{
    if ( Test-Path -Path $Path )
    {
        Write-Warning "A file was required but a directory was found instead."
    }
    else
    {
        Write-Warning "$path could not be found."
    }
}
```

В этом примере мы сначала тестируем удачный путь, а затем используем его на практике. Если это не удалось сделать, выполняется еще одна проверка, чтобы указать более подробные сведения для пользователя.

### <a name="elseif"></a>elseif

Мы не ограничиваемся одной условной проверкой. Можно объединять операторы `if` и `else` в цепочку, а не вкладывать их с помощью оператора `elseif`.

```powershell
if ( Test-Path -Path $Path -PathType Leaf )
{
    Move-Item -Path $Path -Destination $archivePath
}
elseif ( Test-Path -Path $Path )
{
    Write-Warning "A file was required but a directory was found instead."
}
else
{
    Write-Warning "$path could not be found."
}
```

Они выполняются в направлении сверху вниз. Верхний оператор `if` вычисляется в первую очередь. Если это `$false`, вычисление выполняется для следующего оператора `elseif` или `else` в списке. Последний оператор `else` является действием по умолчанию, которое выполняется, если ни одно другое действие не возвращает `$true`.

### <a name="switch"></a>Параметр

На этом этапе я должен рассказать об операторе `switch`. Он предоставляет альтернативный синтаксис для выполнения нескольких сравнений со значением. С помощью `switch` указывается выражение, а полученный результат сравнивается с несколькими различными значениями. Если одно из этих значений совпадает, выполняется соответствующий блок кода. Взгляните на этот пример:

```powershell
$itemType = 'Role'
switch ( $itemType )
{
    'Component'
    {
        'is a component'
    }
    'Role'
    {
        'is a role'
    }
    'Location'
    {
        'is a location'
    }
}
```

Существует три возможных значения, которые могут совпадать с `$itemType`. В этом случае оно совпадает с `Role`. Я использовал этот простой пример, просто чтобы продемонстрировать работу оператора `switch`. В другой статье я подробно описываю [все, что вы хотите знать об операторе switch][].

## <a name="pipeline"></a>Pipeline

Конвейер — уникальная и важная функция PowerShell. Любое значение, которое не подавляется и не присваивается переменной, помещается в конвейер. `if` позволяет нам воспользоваться преимуществами конвейера таким способом, который не всегда очевиден.

```powershell
$discount = if ( $age -ge 55 )
{
    Get-SeniorDiscount
}
elseif ( $age -le 13 )
{
    Get-ChildDiscount
}
else
{
    0.00
}
```

Каждый блок сценария помещает в конвейер результаты выполнения команд или значение. Затем мы присваиваем результат оператора `if` переменной `$discount`. В этом примере можно так же легко присвоить эти значения переменной `$discount` непосредственно в каждом блоке ScriptBlock. Не сказал бы, что я часто использую эту возможность для оператора `if`, однако у меня есть пример недавнего использования.

### <a name="array-inline"></a>Массив в строке

У меня есть функция с именем [Invoke-SnowSql][], которая запускает исполняемый файл с несколькими аргументами командной строки. Вот фрагмент этой функции, где я создаю массив аргументов.

```powershell
$snowSqlParam = @(
    '--accountname', $Endpoint
    '--username', $Credential.UserName
    '--option', 'exit_on_error=true'
    '--option', 'output_format=csv'
    '--option', 'friendly=false'
    '--option', 'timing=false'
    if ($Debug)
    {
        '--option', 'log_level=DEBUG'
    }
    if ($Path)
    {
        '--filename', $Path
    }
    else
    {
        '--query', $singleLineQuery
    }
)
```

Переменные `$Debug` и `$Path` являются параметрами функции, которые указываются конечным пользователем.
Я вычисляю их в строке при инициализации массива. Если `$Debug` имеет значение true, эти значения помещаются в нужной точке в `$snowSqlParam`. То же самое верно для переменной `$Path`.

## <a name="simplify-complex-operations"></a>Упрощение сложных операций

Вы неизбежно столкнетесь с такой ситуацией, когда необходимо проверить множество сравнений и для просмотра оператора `If` придется долго прокручивать экран вправо.

```powershell
$user = Get-ADUser -Identity $UserName
if ( $null -ne $user -and $user.Department -eq 'Finance' -and $user.Title -match 'Senior' -and $user.HomeDrive -notlike '\\server\*' )
{
    # Do Something
}
```

Они могут быть трудночитаемыми, и из-за этого возможны ошибки. Эту проблему можно решить несколькими способами.

### <a name="line-continuation"></a>Продолжение строки

В PowerShell есть ряд операторов, которые позволяют переносить команды на следующую строку. Логические операторы `-and` и `-or` полезны, если нужно разбить выражение на несколько строк.

```powershell
if ($null -ne $user -and
    $user.Department -eq 'Finance' -and
    $user.Title -match 'Senior' -and
    $user.HomeDrive -notlike '\\server\*'
)
{
    # Do Something
}
```

Там выполняется еще много действий, но размещение каждого фрагмента в отдельной строке в корне меняет дело.
Я обычно использую эту функцию, если у меня более двух сравнений или мне приходится прокручивать экран вправо, чтобы прочитать любую часть логики.

### <a name="pre-calculating-results"></a>Предварительное вычисление результатов

Мы можем взять эту инструкцию из оператора `if` и просто проверить результат.

```powershell
$needsSecureHomeDrive = $null -ne $user -and
    $user.Department -eq 'Finance' -and
    $user.Title -match 'Senior' -and
    $user.HomeDrive -notlike '\\server\*'

if ( $needsSecureHomeDrive )
{
    # Do Something
}
```

Это гораздо более понятно, чем в предыдущем примере. У вас также есть возможность использовать имя переменной, которое разъясняет, что именно вы проверяете. Это также пример самодокументируемого кода, в котором сохраняются несущественные комментарии.

### <a name="multiple-if-statements"></a>Несколько операторов if

Можно разбить этот фрагмент на несколько операторов и проверить их по одному. В этом случае для объединения результатов используется флаг или переменная отслеживания.

```powershell

$skipUser = $false

if( $null -eq $user )
{
    $skipUser = $true
}

if( $user.Department -ne 'Finance' )
{
    Write-Verbose "isn't in Finance department"
    $skipUser = $true
}

if( $user.Title -match 'Senior' )
{
    Write-Verbose "Doesn't have Senior title"
    $skipUser = $true
}

if( $user.HomeDrive -like '\\server\*' )
{
    Write-Verbose "Home drive already configured"
    $skipUser = $true
}

if ( -not $skipUser )
{
    # do something
}
```

Мне нужно было инвертировать логику, чтобы логика флагов работала корректно. Каждое вычисление представляет собой отдельный оператор `if`. Преимущество такого подхода заключается в том, что при отладке вы сможете точно определить, что делает эта логика. В то же время мне удалось обеспечить гораздо более высокий уровень детализации.

Очевидным недостатком является то, что приходится писать гораздо больше кода. Код более сложен для просмотра, так как он занимает одну строку логики и разворачивает ее в 25 или более строк.

### <a name="using-functions"></a>Использование функций

Кроме того, можно переместить всю логику проверки в функцию. Посмотрите, насколько простым и понятным это выглядит.

```powershell
if ( Test-SecureDriveConfiguration -ADUser $user )
{
    # do something
}
```

Вам по-прежнему необходимо создать функцию для выполнения проверки, однако благодаря этому с кодом будет гораздо проще работать. Это упрощает тестирование кода. В тестах можно имитировать вызов `Test-ADDriveConfiguration`, и для этой функции потребуется всего два теста. В одном из них она возвращает `$true`, а во втором — `$false`. Тестировать другую функцию проще, потому что она совсем небольшая.

Текстовая область этой функции по-прежнему может состоять всего из одной строки, как это было в самом начале, или может быть расчлененной логикой, которую мы использовали в последнем разделе. Это эффективно в рамках обоих сценариев и позволяет легко изменить данную реализацию позднее.

## <a name="error-handling"></a>Обработка ошибок

Одной из основных целей использования оператора `if` является проверка наличия условий возникновения ошибок, прежде чем они появятся. Например, вы можете проверить, существует ли папка, до того, как попытаетесь ее создать.

```powershell
if ( -not (Test-Path -Path $folder) )
{
    New-Item -Type Directory -Path $folder
}
```

Я люблю говорить: если вы ожидаете, что возникнет исключение, значит, на самом деле это не исключение. Таким образом, лучше при любом удобном случае проверять свои значения и условия.

Более подробно о фактической обработке исключений см. в моей статье, где рассматривается [все, что вы хотели знать об исключениях][].

## <a name="final-words"></a>Заключение

Оператор `if` очень простой, но именно он является основополагающим компонентом PowerShell. Вы будете очень часто его использовать практически в каждом созданном вами сценарии. Надеюсь, теперь вы лучше понимаете его работу, чем раньше.

<!-- link references -->
[Оригинал]: https://powershellexplained.com/2019-08-11-Powershell-if-then-else-equals-operator/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[if]: /powershell/module/microsoft.powershell.core/about/about_if (если);
[побитовыми операторами]: /powershell/module/microsoft.powershell.core/about/about_arithmetic_operators#bitwise-operators
[множестве способов использования регулярных выражений]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression/
[все, что вы хотели знать об исключениях]: everything-about-exceptions.md
[всем, что необходимо знать о $null]: everything-about-null.md
[Прасун Карунан В.]: https://twitter.com/prasoonkarunan
[все, что вы хотите знать об операторе switch]: everything-about-switch.md
[Invoke-SnowSql]: https://github.com/loanDepot/SnowSQL/blob/a3731b52e4ab4ecb503fb81e2d8cb131e8f90410/SnowSQL/public/Invoke-SnowSql.ps1#L90
