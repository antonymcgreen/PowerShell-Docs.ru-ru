---
title: Все, что вы когда-либо хотели знать об инструкции switch
description: Инструкция switch в PowerShell обеспечивает возможности, которых нет в других языках.
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 685a5691599408a0d54ca99bf383bcd7702322a6
ms.sourcegitcommit: 0afff6edbe560e88372dd5f1cdf51d77f9349972
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2020
ms.locfileid: "86469724"
---
# <a name="everything-you-ever-wanted-to-know-about-the-switch-statement"></a>Все, что вы когда-либо хотели знать об инструкции switch

Как и многие другие языки, PowerShell содержит команды для управления потоком выполнения в скриптах. Одна из них — инструкция [switch][], которая обеспечивает в PowerShell возможности, отсутствующие в других языках. Сегодня мы подробно рассмотрим работу с `switch` в PowerShell.

> [!NOTE]
> [Оригинал][] этой статьи впервые был опубликован в блоге автора [@KevinMarquette][]. Команда разработчиков PowerShell благодарит Кевина за то, что он поделился с нами этим материалом. Читайте его блог — [PowerShellExplained.com][].

## <a name="the-if-statement"></a>Инструкция `if`

Одна из первых инструкций, которую вы изучите, — `if`. Она позволяет выполнять блок скрипта, если значение инструкции `$true`.

``` powershell
if ( Test-Path $Path )
{
    Remove-Item $Path
}
```

Инструкции `elseif` и `else` позволяют использовать гораздо более сложную логику. Ниже приведен пример, в котором у меня есть числовое значение, обозначающее день недели, а я хочу получить имя в виде строки.

``` powershell
$day = 3

if ( $day -eq 0 ) { $result = 'Sunday'        }
elseif ( $day -eq 1 ) { $result = 'Monday'    }
elseif ( $day -eq 2 ) { $result = 'Tuesday'   }
elseif ( $day -eq 3 ) { $result = 'Wednesday' }
elseif ( $day -eq 4 ) { $result = 'Thursday'  }
elseif ( $day -eq 5 ) { $result = 'Friday'    }
elseif ( $day -eq 6 ) { $result = 'Saturday'  }

$result
```

```Output
Wednesday
```

На самом деле это довольно типичная ситуация, и решить эту задачу можно множеством способов. В частности, с помощью инструкции `switch`.

## <a name="switch-statement"></a>Оператор switch

Инструкция `switch` позволяет указать переменную и список возможных значений. Если значение соответствует переменной, выполняется ее блок ScriptBlock.

``` powershell
$day = 3

switch ( $day )
{
    0 { $result = 'Sunday'    }
    1 { $result = 'Monday'    }
    2 { $result = 'Tuesday'   }
    3 { $result = 'Wednesday' }
    4 { $result = 'Thursday'  }
    5 { $result = 'Friday'    }
    6 { $result = 'Saturday'  }
}

$result
```

```Output
'Wednesday'
```

В этом примере значение `$day` соответствует одному из числовых значений, поэтому `$result` присваивается правильное имя. В данном случае мы просто присваиваем значение переменной, но в таких блоках скриптов можно выполнять любые команды PowerShell.

### <a name="assign-to-a-variable"></a>Присвоение значения переменной

Этот последний пример можно написать иначе.

``` powershell
$result = switch ( $day )
{
    0 { 'Sunday'    }
    1 { 'Monday'    }
    2 { 'Tuesday'   }
    3 { 'Wednesday' }
    4 { 'Thursday'  }
    5 { 'Friday'    }
    6 { 'Saturday'  }
}
```

Поместим значение в конвейер PowerShell и присвоим его переменной `$result`. Это же действие можно выполнить с помощью инструкций `if` и `foreach`.

### <a name="default"></a>По умолчанию

Воспользовавшись ключевым словом `default`, можно определить, что должно произойти при отсутствии совпадения.

``` powershell
$result = switch ( $day )
{
    0 { 'Sunday' }
    # ...
    6 { 'Saturday' }
    default { 'Unknown' }
}
```

Здесь по умолчанию возвращается значение `Unknown`.

### <a name="strings"></a>строк

Я в этих последних примерах сопоставлял числа, но вы также можете сопоставлять строки.

``` powershell
$item = 'Role'

switch ( $item )
{
    Component
    {
        'is a component'
    }
    Role
    {
        'is a role'
    }
    Location
    {
        'is a location'
    }
}
```

```Output
is a role
```

Я решил не заключать здесь совпадения с `Component`, `Role` и `Location` в кавычки, подчеркнув тем самым тот факт, что они необязательны. В большинстве случаев `switch` обрабатывает их как строку.

## <a name="arrays"></a>Массивы

Одна из замечательных особенностей PowerShell `switch` — особый способ обработки массивов. Если передать инструкции `switch` массив, она обработает каждый элемент в этой коллекции.

``` powershell
$roles = @('WEB','Database')

switch ( $roles ) {
    'Database'   { 'Configure SQL' }
    'WEB'        { 'Configure IIS' }
    'FileServer' { 'Configure Share' }
}
```

```Output
Configure IIS
Configure SQL
```

Если в массиве есть повторяющиеся элементы, они будут сопоставляться в соответствующем разделе несколько раз.

### <a name="psitem"></a>PSItem

С помощью `$PSItem` или `$_` можно ссылаться на текущий обработанный элемент. При выполнении простого сопоставления `$PSItem` — это сопоставляемое значение. В следующем разделе я покажу, как выполнить более сложные сопоставления с использованием этой переменной.

## <a name="parameters"></a>Параметры

Уникальная особенность инструкции `switch` в PowerShell заключается в наличии ряда [параметров-переключателей][], которые изменяют ее способ выполнения.

### <a name="-casesensitive"></a>-CaseSensitive

По умолчанию сопоставления выполняются без учета регистра. Если необходимо учитывать регистр, можно использовать параметр `-CaseSensitive`. Его можно использовать в сочетании с другими параметрами-переключателями.

### <a name="-wildcard"></a>-Wildcard

Поддержку подстановочных знаков в switch можно включить с помощью параметра `-wildcard`. При этом для каждого соответствия используется та же логика применения подстановочных знаков, что и у оператора `-like`.

``` powershell
$Message = 'Warning, out of disk space'

switch -Wildcard ( $message )
{
    'Error*'
    {
        Write-Error -Message $Message
    }
    'Warning*'
    {
        Write-Warning -Message $Message
    }
    default
    {
        Write-Information $message
    }
}
```

```Output
WARNING: Warning, out of disk space
```

В этом случае мы обрабатываем сообщение, а затем помещаем его в различные потоки на основе содержимого.

### <a name="-regex"></a>-Regex

Инструкция switch поддерживает сопоставление не только с помощью подстановочных знаков, но и с использованием регулярных выражений.

``` powershell
switch -Regex ( $message )
{
    '^Error'
    {
        Write-Error -Message $Message
    }
    '^Warning'
    {
        Write-Warning -Message $Message
    }
    default
    {
        Write-Information $message
    }
}
```

Дополнительные примеры приведены в другой моей статье, где описывается [множество способов использования регулярных выражений][].

### <a name="-file"></a>-File

Малоизвестная возможность инструкции switch заключается в том, что при использовании параметра `-File` она может обработать файл. Вместо того чтобы присваивать переменное выражение, используйте `-file` с путем к файлу.

``` powershell
switch -Wildcard -File $path
{
    'Error*'
    {
        Write-Error -Message $PSItem
    }
    'Warning*'
    {
        Write-Warning -Message $PSItem
    }
    default
    {
        Write-Output $PSItem
    }
}
```

Принцип действия будет таким же, как при обработке массива. В этом примере я использую этот параметр для сопоставления вместе с подстановочными знаками и `$PSItem`. В результате выполняется обработка файла журнала и преобразование его в предупреждения и сообщения об ошибках в зависимости от совпадений, полученных на основе регулярного выражения.

## <a name="advanced-details"></a>Дополнительные сведения

Теперь, когда вы знаете обо всех этих документированных возможностях, мы можем использовать их в контексте более сложной обработки.

### <a name="expressions"></a>Выражения

Инструкцию `switch` можно применять не только к переменной, но и к выражению.

``` powershell
switch ( ( Get-Service | Where status -eq 'running' ).name ) {...}
```

Результат вычисления выражения и будет тем значением, которое используется для сопоставления.

### <a name="multiple-matches"></a>Несколько совпадений

Возможно, вы уже догадались, что для сопоставления с помощью `switch` можно использовать несколько условий. Это особенно актуально при сопоставлении с использованием `-wildcard` или `-regex`. Одно и то же условие можно добавить несколько раз, и все они будут активированы.

``` powershell
switch ( 'Word' )
{
    'word' { 'lower case word match' }
    'Word' { 'mixed case word match' }
    'WORD' { 'upper case word match' }
}
```

```Output
lower case word match
mixed case word match
upper case word match
```

Здесь сработают все три инструкции. Это свидетельствует о том, что проверяется каждое условие (по порядку). Это справедливо и для обработки массивов, где каждое условие проверяется для каждого элемента.

### <a name="continue"></a>Continue

Как правило, в таких случаях добавляют инструкцию `break`, но сначала давайте разберемся, как использовать `continue`. Как и в цикле `foreach`, `continue` переходит к следующему элементу в коллекции или выходит из `switch`, если элементов не осталось. Мы можем переписать последний пример с использованием операторов continue, чтобы выполнялась только одна инструкция.

``` powershell
switch ( 'Word' )
{
    'word'
    {
        'lower case word match'
        continue
    }
    'Word'
    {
        'mixed case word match'
        continue
    }
    'WORD'
    {
        'upper case word match'
        continue
    }
}
```

```Output
lower case word match
```

Вместо того чтобы сопоставлять все три элемента, сопоставляется только первый из них, после чего switch переходит к следующему значению. Так как значений для обработки не осталось, выполнение switch завершается. В следующем примере показано, как подстановочный знак может сопоставляться с несколькими элементами.

``` powershell
switch -Wildcard -File $path
{
    '*Error*'
    {
        Write-Error -Message $PSItem
        continue
    }
    '*Warning*'
    {
        Write-Warning -Message $PSItem
        continue
    }
    default
    {
        Write-Output $PSItem
    }
}
```

Так как строка во входном файле может содержать как слово `Error`, так и слово `Warning`, необходимо, чтобы инструкция выполнялась только для первого из них, а затем продолжалась обработка файла.

### <a name="break"></a>Break

Инструкция `break` выполняет выход из switch. Для отдельных значений ее поведение такое же, как у `continue`. Разница проявляется при обработке массива. `break` останавливает всю обработку в switch, а `continue` выполняет переход к следующему элементу.

``` powershell
$Messages = @(
    'Downloading update'
    'Ran into errors downloading file'
    'Error: out of disk space'
    'Sending email'
    '...'
)

switch -Wildcard ($Messages)
{
    'Error*'
    {
        Write-Error -Message $PSItem
        break
    }
    '*Error*'
    {
        Write-Warning -Message $PSItem
        continue
    }
    '*Warning*'
    {
        Write-Warning -Message $PSItem
        continue
    }
    default
    {
        Write-Output $PSItem
    }
}
```

```Output
Downloading update
WARNING: Ran into errors downloading file
write-error -message $PSItem : Error: out of disk space
+ CategoryInfo          : NotSpecified: (:) [Write-Error], WriteErrorException
+ FullyQualifiedErrorId : Microsoft.PowerShell.Commands.WriteErrorException
```

В этом случае при совпадении с любой строкой, начинающейся с `Error`, выводится сообщение об ошибке и выполнение инструкции switch останавливается.
Вот что делает инструкция `break`. Если слово `Error` найдено в середине, а не в начале строки, она записывается как предупреждение. Сделаем то же самое для `Warning`. Строка может содержать как слово `Error`, так и слово `Warning`, но для обработки требуется только одно из них. Этот то, что делает инструкция `continue`.

### <a name="break-labels"></a>Метки прерывания

Инструкция `switch` поддерживает метки `break/continue` так же, как `foreach`.

``` powershell
:filelist foreach($path in $logs)
{
    :logFile switch -Wildcard -File $path
    {
        'Error*'
        {
            Write-Error -Message $PSItem
            break filelist
        }
        'Warning*'
        {
            Write-Error -Message $PSItem
            break logFile
        }
        default
        {
            Write-Output $PSItem
        }
    }
}
```

Мне лично не нравится использовать метки разрыва, но я хочу обратить на них внимание, так как при первом знакомстве с ними могут возникнуть определенные сложности. При наличии нескольких вложенных инструкций `switch` или `foreach` может потребоваться прерывание на разных уровнях, а не только на самом внутреннем элементе. В `switch` можно поместить метку, которая и будет целевым объектом для `break`.

### <a name="enum"></a>Перечисление.

В PowerShell 5.0 поддерживаются перечисления, которые можно использовать в switch.

``` powershell
enum Context {
    Component
    Role
    Location
}

$item = [Context]::Role

switch ( $item )
{
    Component
    {
        'is a component'
    }
    Role
    {
        'is a role'
    }
    Location
    {
        'is a location'
    }
}
```

```Output
is a role
```

Если вы хотите хранить все данные как строго типизированные перечисления, их можно взять в круглые скобки.

``` powershell
switch ($item )
{
    ([Context]::Component)
    {
        'is a component'
    }
    ([Context]::Role)
    {
        'is a role'
    }
    ([Context]::Location)
    {
        'is a location'
    }
}
```

Здесь круглые скобки необходимы, чтобы инструкция switch не интерпретировала значение `[Context]::Location` как литеральную строку.

### <a name="scriptblock"></a>ScriptBlock

При необходимости для оценки соответствия можно использовать блок ScriptBlock.

``` powershell
$age = 37

switch ( $age )
{
    {$PSItem -le 18}
    {
        'child'
    }
    {$PSItem -gt 18}
    {
        'adult'
    }
}
```

```Output
'adult'
```

Такой подход повышает сложность и может затруднить чтение `switch`. В большинстве случаев, когда требуется использовать что-то подобное, лучше воспользоваться инструкциями `if` и `elseif`. Я бы воспользовался этим вариантом, если бы у меня уже была большая инструкция switch и мне нужно было, чтобы два элемента попали в один и тот же блок оценки.

Мне кажется, что для улучшения читаемости блок ScriptBlock можно заключить в круглые скобки.

``` powershell
switch ( $age )
{
    ({$PSItem -le 18})
    {
        'child'
    }
    ({$PSItem -gt 18})
    {
        'adult'
    }
}
```

Он будет выполняться таким же образом, но при этом визуальная разбивка станет удобнее для быстрого просмотра.

### <a name="regex-matches"></a>Регулярное выражение $matches

Нам нужно вернуться к регулярному выражению, чтобы поработать над одним неочевидным аспектом. При использовании регулярного выражения заполняется переменная `$matches`. Использование переменной `$matches` подробно рассмотрено в статье о [Множество способов использования регулярных выражений][]. Здесь же приведен краткий пример, демонстрирующий ее в действии при использовании с именованными совпадениями.

``` powershell
$message = 'my ssn is 123-23-3456 and credit card: 1234-5678-1234-5678'

switch -regex ($message)
{
    '(?<SSN>\d\d\d-\d\d-\d\d\d\d)'
    {
        Write-Warning "message contains a SSN: $($matches.SSN)"
    }
    '(?<CC>\d\d\d\d-\d\d\d\d-\d\d\d\d-\d\d\d\d)'
    {
        Write-Warning "message contains a credit card number: $($matches.CC)"
    }
    '(?<Phone>\d\d\d-\d\d\d-\d\d\d\d)'
    {
        Write-Warning "message contains a phone number: $($matches.Phone)"
    }
}
```

```Output
WARNING: message may contain a SSN: 123-23-3456
WARNING: message may contain a credit card number: 1234-5678-1234-5678
```

### <a name="null"></a>$null

Вы можете выполнить сопоставление со значением `$null`, которое не обязательно должно быть значением по умолчанию.

``` powershell
$value = $null

switch ( $value )
{
    $null
    {
        'Value is null'
    }
    default
    {
        'value is not null'
    }
}

```Output
Value is null
```

То же касается пустой строки.

``` powershell
switch ( '' )
{
    ''
    {
        'Value is empty'
    }
    default
    {
        'value is a empty string'
    }
}

```Output
Value is empty
```

### <a name="constant-expression"></a>Константное выражение

Ли Дейли отмечает, что для вычисления элементов `[bool]` можно использовать константное выражение `$true`.
Представьте, что у нас есть несколько логических проверок, которые необходимо выполнить.

``` powershell
$isVisible = $false
$isEnabled = $true
$isSecure = $true

switch ( $true )
{
    $isEnabled
    {
        'Do-Action'
    }
    $isVisible
    {
        'Show-Animation'
    }
    $isSecure
    {
        'Enable-AdminMenu'
    }
}
```

```Output
Do-Action
Enabled-AdminMenu
```

Используя такой подход, можно непосредственно оценить состояние нескольких логических полей и выполнить над ними соответствующее действие. Его преимущество в том, что одно совпадение может отражать состояние значения, которое еще не было оценено.

``` powershell
$isVisible = $false
$isEnabled = $true
$isAdmin = $false

switch ( $true )
{
    $isEnabled
    {
        'Do-Action'
        $isVisible = $true
    }
    $isVisible
    {
        'Show-Animation'
    }
    $isAdmin
    {
        'Enable-AdminMenu'
    }
}
```

```Output
Do-Action
Show-Animation
```

Поскольку в этом примере для `$isEnabled` задано значение `$true`, для `$isVisible` также должно быть задано значение `$true`. Тогда при вычислении переменной `$isVisible` будет вызываться ее ScriptBlock. Это не совсем интуитивный, но весьма остроумный способ применения этой возможности.

### <a name="switch-automatic-variable"></a>Автоматическая переменная $switch

Когда инструкция `switch` обрабатывает значения, она создает перечислитель и вызывает его `$switch`. Это автоматически созданная PowerShell переменная, с которой можно работать напрямую.

Я узнал о ней здесь: [/u/frmadsen](https://www.reddit.com/user/frmadsen),

<div class="reddit-embed" data-embed-media="www.redditmedia.com" data-embed-parent="false" data-embed-live="false" data-embed-uuid="8f6edbf1-abc6-4513-971e-ccd1d202889d" data-embed-created="2018-12-25T22:05:33.986Z">а также из <a href="https://www.reddit.com/r/PowerShell/comments/a90rx2/what_should_i_it_student_learn_to_master/ecj2kji/">комментария</a> в обсуждении <a href="https://www.reddit.com/r/PowerShell/comments/a90rx2/what_should_i_it_student_learn_to_master/">Что нужно знать будущим ИТ-специалистам, чтобы овладеть PowerShell?</a>.</div><script async src="https://www.redditstatic.com/comment-embed.js"></script>

Получаем такие результаты:

```Output
2
4
```

При переходе перечислителя к следующему элементу тот не обрабатывается с помощью `switch`, но к его значению можно получить доступ напрямую. Как по мне, это уж слишком.

## <a name="other-patterns"></a>Прочие ситуации

### <a name="hashtables"></a>хэш-таблицы;

Одна из моих самых популярных публикаций посвящена [хэш-таблицам][]. Один из вариантов использования `hashtable` — таблица подстановки. Это альтернативный подход для типичной ситуации, в которой зачастую применяется инструкция `switch`.

``` powershell
$day = 3

$lookup = @{
    0 = 'Sunday'
    1 = 'Monday'
    2 = 'Tuesday'
    3 = 'Wednesday'
    4 = 'Thursday'
    5 = 'Friday'
    6 = 'Saturday'
}

$lookup[$day]
```

```Output
Wednesday
```

Если я использую `switch` лишь для подстановки, я часто применяю `hashtable`.

### <a name="enum"></a>Перечисление.

В PowerShell 5.0 появилась функция `Enum`, и в данном случае можно использовать также ее.

``` powershell
$day = 3

enum DayOfTheWeek {
    Sunday
    Monday
    Tuesday
    Wednesday
    Thursday
    Friday
    Saturday
}

[DayOfTheWeek]$day
```

```Output
Wednesday
```

Способов решения этой задачи очень много, так что на их обсуждение ушел бы целый день. Я же лишь хотел рассказать о том, что существуют различные варианты.

## <a name="final-words"></a>Заключение

Несмотря на свою кажущуюся простоту, инструкция switch зачастую предоставляет дополнительные возможности, о которых большинство даже и не подозревает. Если использовать их все вместе, получится довольно эффективный инструмент. Надеюсь, вы узнали что-то, о чем раньше и не подозревали.

<!-- link references -->
[Оригинал]: https://powershellexplained.com/2018-01-12-Powershell-switch-statement/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[switch]: /powershell/module/microsoft.powershell.core/about/about_switch
[параметров-переключателей]: https://www.powershellmagazine.com/2013/12/20/using-powershell-switch-vs-boolean-parameters-in-sma-runbooks/
[Множество способов использования регулярных выражений]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression
[хэш-таблицам]: everything-about-hashtable.md
