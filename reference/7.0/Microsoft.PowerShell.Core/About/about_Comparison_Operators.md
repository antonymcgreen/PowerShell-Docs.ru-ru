---
description: Описывает операторы, которые сравнивают значения в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comparison_Operators
ms.openlocfilehash: d6096de14d0bb8c7ba86c0585806b86cf3bb921a
ms.sourcegitcommit: c9e56ec489522c706b8d6b8733f3f015d6d7e893
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "93232934"
---
# <a name="about-comparison-operators"></a>Сведения об операторах сравнения

## <a name="short-description"></a>Краткое описание
Описывает операторы, которые сравнивают значения в PowerShell.

## <a name="long-description"></a>Подробное описание

Операторы сравнения позволяют задавать условия для сравнения значений и поиска значений, соответствующих указанным шаблонам. Чтобы использовать оператор сравнения, укажите значения, которые необходимо сравнить с оператором, разделяющим эти значения.

PowerShell содержит следующие операторы сравнения:

| Тип        | Операторы    | Описание:                                 |
| ----------- | ------------ | --------------------------------------------|
| Равенство    | -eq          | равно                                      |
|             | -ne          | не равно                                  |
|             | -gt          | больше чем                                |
|             | -ge          | больше или равно                       |
|             | -lt          | меньше чем                                   |
|             | -le          | меньше или равно                          |
|             |              |                                             |
| Matching    | -like        | Возвращает значение true, если строка соответствует подстановочному знаку   |
|             |              | pattern                                     |
|             | -notlike     | Возвращает значение true, если строка не соответствует     |
|             |              | Шаблон подстановочного знака                            |
|             | -match       | Возвращает значение true, если строка соответствует регулярному выражению      |
|             |              | пакет $matches содержит совпадающие строки |
|             | -notmatch    | Возвращает значение true, если строка не соответствует     |
|             |              | шаблон регулярного выражения; $matches содержит сопоставление   |
|             |              | строки;                                     |
|             |              |                                             |
| Containment | -contains    | Возвращает значение true, если содержалось ссылочное значение |
|             |              | в коллекции                             |
|             | -notcontains | Возвращает значение true, если значение ссылки не       |
|             |              | содержится в коллекции                   |
|             | -in          | Возвращает значение true, если значение теста содержится в элементе |
|             |              | коллекция                                  |
|             | -notin       | Возвращает значение true, если тестовое значение не содержится  |
|             |              | в коллекции                             |
|             |              |                                             |
| Замена | -Replace     | Заменяет шаблон строки                   |
|             |              |                                             |
| Тип        | — имеет          | Возвращает значение true, если оба объекта одинаковы    |
|             |              | тип                                        |
|             | -IsNot       | Возвращает значение true, если объекты не совпадают|
|             |              | тип                                        |

По умолчанию все операторы сравнения не учитывают регистр. Чтобы выполнить оператор сравнения с учетом регистра, перед именем оператора введите `c` . Например, версия с учетом регистра `-eq` — `-ceq` . Чтобы явно сделать регистр без учета регистра, перед оператором следует использовать `i` . Например, явная версия без учета регистра `-eq` — `-ieq` .

Если входные данные оператора являются скалярным значением, операторы сравнения возвращают логическое значение. Если входные данные представляют собой коллекцию значений, то операторы сравнения возвращают все совпадающие значения. Если в коллекции нет совпадений, операторы сравнения возвращают пустой массив.

```powershell
PS> (1, 2 -eq 3).GetType().FullName
System.Object[]
```

Исключениями являются операторы включения, операторы in и операторы типа, которые всегда возвращают **логическое** значение.

> [!NOTE]
> Если необходимо сравнить значение с `$null` , необходимо разместить `$null` в левой части сравнения. При сравнении `$null` с **объектом []** результат равен **false** , поскольку объект сравнения является массивом. При сравнении массива со `$null` значением сравнения отфильтровывает все значения, `$null` хранящиеся в массиве. Пример:
>
> ```powershell
> PS> $null -ne $null, "hello"
> True
> PS> $null, "hello" -ne $null
> hello
> ```

### <a name="equality-operators"></a>Операторы равенства

Операторы равенства ( `-eq` , `-ne` ) возвращают значение true или совпадения, если одно или несколько входных значений идентичны заданному шаблону. Весь шаблон должен соответствовать всему значению.

Пример

#### <a name="-eq"></a>-eq

Описание: равно. Содержит идентичное значение.

Пример

```powershell
PS> 2 -eq 2
True

PS> 2 -eq 3
False

PS> 1,2,3 -eq 2
2
PS> "abc" -eq "abc"
True

PS> "abc" -eq "abc", "def"
False

PS> "abc", "def" -eq "abc"
abc
```

#### <a name="-ne"></a>-ne

Описание: не равно. Содержит другое значение.

Пример

```powershell
PS> "abc" -ne "def"
True

PS> "abc" -ne "abc"
False

PS> "abc" -ne "abc", "def"
True

PS> "abc", "def" -ne "abc"
def
```

#### <a name="-gt"></a>-gt

Описание: "больше чем".

Пример

```powershell
PS> 8 -gt 6
True

PS> 7, 8, 9 -gt 8
9
```

> [!NOTE]
> Это не следует путать с `>` оператором "больше" во многих других языках программирования. В PowerShell `>` используется для перенаправления. Дополнительные сведения см. в разделе [About_redirection](about_Redirection.md#potential-confusion-with-comparison-operators).

#### <a name="-ge"></a>-ge

Описание: больше или равно.

Пример

```powershell
PS> 8 -ge 8
True

PS> 7, 8, 9 -ge 8
8
9
```

#### <a name="-lt"></a>-lt

Описание: "меньше чем".

Пример

```powershell

PS> 8 -lt 6
False

PS> 7, 8, 9 -lt 8
7
```

#### <a name="-le"></a>-le

Описание: меньше или равно.

Пример

```powershell
PS> 6 -le 8
True

PS> 7, 8, 9 -le 8
7
8
```

### <a name="matching-operators"></a>Соответствующие операторы

Операторы LIKE ( `-like` и `-notlike` ) находят элементы, которые соответствуют или не соответствуют указанному шаблону с помощью выражений с подстановочными знаками.

Синтаксис:

```powershell
<string[]> -like <wildcard-expression>
<string[]> -notlike <wildcard-expression>
```

Операторы match ( `-match` и `-notmatch` ) находят элементы, которые соответствуют или не соответствуют заданному шаблону с помощью регулярных выражений.

Операторы match заполняют `$Matches` автоматическую переменную, если вход (левый аргумент) к оператору является одним скалярным объектом. Если входные данные скалярны, `-match` `-notmatch` операторы и возвращают логическое значение и присвойте значение `$Matches` автоматической переменной соответствующим компонентам аргумента.

Синтаксис:

```powershell
<string[]> -match <regular-expression>
<string[]> -notmatch <regular-expression>
```

#### <a name="-like"></a>-like

Описание: совпадение с использованием подстановочного знака ( \* ).

Пример

```powershell
PS> "PowerShell" -like "*shell"
True

PS> "PowerShell", "Server" -like "*shell"
PowerShell
```

#### <a name="-notlike"></a>-notlike

Описание: не совпадает с подстановочным знаком ( \* ).

Пример

```powershell
PS> "PowerShell" -notlike "*shell"
False

PS> "PowerShell", "Server" -notlike "*shell"
Server
```

### <a name="-match"></a>-match

Описание: соответствует строке с помощью регулярных выражений. Если входные данные скалярны, он заполняет `$Matches` автоматическую переменную.

Если входные данные являются коллекцией, `-match` `-notmatch` операторы и возвращают соответствующие члены этой коллекции, но оператор не заполняет `$Matches` переменную.

Например, следующая команда отправляет коллекцию строк `-match` оператору. `-match`Оператор возвращает элементы в коллекции, которые соответствуют. Он не заполняет `$Matches` автоматическую переменную.

```powershell
PS> "Sunday", "Monday", "Tuesday" -match "sun"
Sunday

PS> $Matches
PS>
```

В отличие от этого, следующая команда отправляет в оператор одну строку `-match` . `-match`Оператор возвращает логическое значение и заполняет `$Matches` автоматическую переменную. `$Matches`Автоматическая переменная является хэш- **таблицей** . Если группирование или захват не используются, заполняется только один ключ.
`0`Ключ представляет весь совпадающий текст. Дополнительные сведения о группировании и записи с помощью регулярных выражений см. в разделе [about_Regular_Expressions](about_Regular_Expressions.md).

```powershell
PS> "Sunday" -match "sun"
True

PS> $Matches

Name                           Value
----                           -----
0                              Sun
```

Важно отметить, что `$Matches` хэш-таблица будет содержать только первое вхождение любого совпадающего шаблона.

```powershell
PS> "Banana" -match "na"
True

PS> $Matches

Name                           Value
----                           -----
0                              na
```

> [!IMPORTANT]
> `0`Ключ является **целым числом** . Для доступа к сохраненному значению можно использовать любой метод **Hashtable** .
>
> ```powershell
> PS> "Good Dog" -match "Dog"
> True
>
> PS> $Matches[0]
> Dog
>
> PS> $Matches.Item(0)
> Dog
>
> PS> $Matches.0
> Dog
> ```

`-notmatch`Оператор заполняет `$Matches` автоматическую переменную, если входные данные скалярны и результат имеет значение false, при обнаружении совпадения.

```powershell
PS> "Sunday" -notmatch "rain"
True

PS> $matches
PS>

PS> "Sunday" -notmatch "day"
False

PS> $matches

Name                           Value
----                           -----
0                              day
```

#### <a name="-notmatch"></a>-notmatch

Описание: не соответствует строке. Использует регулярные выражения. Если входные данные скалярны, он заполняет `$Matches` автоматическую переменную.

Пример

```powershell
PS> "Sunday" -notmatch "sun"
False

PS> $matches
Name Value
---- -----
0    sun

PS> "Sunday", "Monday" -notmatch "sun"
Monday
```

### <a name="containment-operators"></a>Операторы вложения

Операторы включения ( `-contains` и `-notcontains` ) похожи на операторы равенства. Однако операторы включения всегда возвращают логическое значение, даже если входные данные являются коллекцией.

Кроме того, в отличие от операторов равенства, операторы вложения возвращают значение, как только они обнаруживают первое соответствие. Операторы равенства оценивают все входные данные, а затем возвращают все совпадения в коллекции.

#### <a name="-contains"></a>-contains

Описание: оператор вложения. Сообщает, включает ли коллекция ссылочных значений одно тестовое значение. Всегда возвращает логическое значение. Возвращает значение TRUE, только если тестовое значение точно совпадает по меньшей мере с одним из ссылочных значений.

Если тестовое значение является коллекцией, оператор Contains использует равенство ссылок. Он возвращает значение TRUE, только если одно из ссылочных значений является одним и тем же экземпляром объекта тестового значения.

В очень большой коллекции `-contains` оператор возвращает результаты быстрее, чем оператор Equal to.

Синтаксис:

`<Reference-values> -contains <Test-value>`

Примеры:

```powershell
PS> "abc", "def" -contains "def"
True

PS> "Windows", "PowerShell" -contains "Shell"
False  #Not an exact match

# Does the list of computers in $DomainServers include $ThisComputer?
PS> $DomainServers -contains $thisComputer
True

PS> "abc", "def", "ghi" -contains "abc", "def"
False

PS> $a = "abc", "def"
PS> "abc", "def", "ghi" -contains $a
False
PS> $a, "ghi" -contains $a
True
```

#### <a name="-notcontains"></a>-notcontains

Описание: оператор вложения. Сообщает, включает ли коллекция ссылочных значений одно тестовое значение. Всегда возвращает логическое значение. Возвращает значение TRUE, если тестовое значение не является точным соответствием по крайней мере одному из значений ссылок.

Если тестовое значение является коллекцией, оператор NotContains использует равенство ссылок.

Синтаксис:

`<Reference-values> -notcontains <Test-value>`

Примеры:

```powershell
PS> "Windows", "PowerShell" -notcontains "Shell"
True  #Not an exact match

# Get cmdlet parameters, but exclude common parameters
function get-parms ($cmdlet)
{
    $Common = "Verbose", "Debug", "WarningAction", "WarningVariable",
      "ErrorAction", "ErrorVariable", "OutVariable", "OutBuffer"

    $allparms = (Get-Command $Cmdlet).parametersets |
      foreach {$_.Parameters} |
        foreach {$_.Name} | Sort-Object | Get-Unique

    $allparms | where {$Common -notcontains $_ }
}

# Find unapproved verbs in the functions in my module
PS> $ApprovedVerbs = Get-Verb | foreach {$_.verb}
PS> $myVerbs = Get-Command -Module MyModule | foreach {$_.verb}
PS> $myVerbs | where {$ApprovedVerbs -notcontains $_}
ForEach
Sort
Tee
Where
```

#### <a name="-in"></a>-in

Описание: в операторе. Указывает, отображается ли тестовое значение в коллекции ссылочных значений. Всегда возвращает как логическое значение. Возвращает значение TRUE, только если тестовое значение точно совпадает по меньшей мере с одним из ссылочных значений.

Если тестовое значение является коллекцией, оператор in использует равенство ссылок.
Он возвращает значение TRUE, только если одно из ссылочных значений является одним и тем же экземпляром объекта тестового значения.

`-in`Оператор появился в PowerShell 3,0.

Синтаксис:

`<Test-value> -in <Reference-values>`

Примеры:

```powershell
PS> "def" -in "abc", "def"
True

PS> "Shell" -in "Windows", "PowerShell"
False  #Not an exact match

PS> "Windows" -in "Windows", "PowerShell"
True  #An exact match

PS> "Windows", "PowerShell" -in "Windows", "PowerShell", "ServerManager"
False  #Using reference equality

PS> $a = "Windows", "PowerShell"
PS> $a -in $a, "ServerManager"
True  #Using reference equality

# Does the list of computers in $DomainServers include $ThisComputer?
PS> $thisComputer -in  $domainServers
True
```

#### <a name="-notin"></a>-notin

Описание: указывает, отображается ли тестовое значение в коллекции ссылочных значений. Всегда возвращает логическое значение. Возвращает значение TRUE, если тестовое значение не является точным соответствием по крайней мере одному из значений ссылок.

Если тестовое значение является коллекцией, оператор in использует равенство ссылок.
Он возвращает значение TRUE, только если одно из ссылочных значений является одним и тем же экземпляром объекта тестового значения.

`-notin`Оператор появился в PowerShell 3,0.

Синтаксис:

`<Test-value> -notin <Reference-values>`

Примеры:

```powershell
PS> "def" -notin "abc", "def"
False

PS> "ghi" -notin "abc", "def"
True

PS> "Shell" -notin "Windows", "PowerShell"
True  #Not an exact match

PS> "Windows" -notin "Windows", "PowerShell"
False  #An exact match

# Find unapproved verbs in the functions in my module
PS> $ApprovedVerbs = Get-Verb | foreach {$_.verb}
PS> $MyVerbs = Get-Command -Module MyModule | foreach {$_.verb}

PS> $MyVerbs | where {$_ -notin $ApprovedVerbs}
ForEach
Sort
Tee
Where
```

### <a name="replacement-operator"></a>Оператор замены

`-replace`Оператор заменяет все или часть значения указанным значением с помощью регулярных выражений. Оператор можно использовать `-replace` для многих административных задач, таких как переименование файлов. Например, следующая команда изменяет расширения имен файлов всех txt в log:

```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.name -replace '\.txt$','.log' }
```

Синтаксис `-replace` оператора выглядит следующим образом, где `<original>` заполнитель представляет заменяемые символы, а `<substitute>` заполнитель представляет символы, которые будут заменены:

`<input> <operator> <original>, <substitute>`

По умолчанию `-replace` оператор не учитывает регистр. Чтобы сделать его чувствительным к регистру, используйте `-creplace` . Чтобы явно сделать регистр без учета регистра, используйте `-ireplace` .

Рассмотрим следующие примеры.

```powershell
PS> "book" -replace "B", "C"
```

```Output
Cook
```

```powershell
"book" -ireplace "B", "C"
```

```Output
Cook
```

```powershell
"book" -creplace "B", "C"
```

```Output
book
```

Можно также использовать регулярные выражения для динамической замены текста с помощью захваченных групп и подстановок. Дополнительные сведения см. в разделе [about_Regular_Expressions](about_Regular_Expressions.md).

### <a name="scriptblock-substitutions"></a>Подстановки ScriptBlock

Начиная с PowerShell 6, можно использовать аргумент **ScriptBlock** для текста *подстановки* . Блок **ScriptBlock** будет выполняться для каждого соответствия, найденного во *входной* строке.

В блоке **ScriptBlock** используйте `$_` автоматическую переменную для ссылки на текущий объект **System. Text. RegularExpressions. Match** . Объект **Match** предоставляет доступ к текущему вводимому тексту, а также другим полезным сведениям.

В этом примере каждая последовательность из трех десятичных знаков заменяется эквивалентным символом. Блок **ScriptBlock** выполняется для каждого набора из трех десятичных знаков, которые необходимо заменить.

```powershell
PS> "072101108108111" -replace "\d{3}", {[char][int]$_.Value}
Hello
```

### <a name="type-comparison"></a>Сравнение типов

Операторы сравнения типов ( `-is` и `-isnot` ) используются для определения того, является ли объект конкретным типом.

#### <a name="-is"></a>— имеет

Синтаксис:

`<object> -is <type reference>`

Пример

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -is [int]
True
PS> $a -is $b.GetType()
False
```

#### <a name="-isnot"></a>-IsNot

Синтаксис:

`<object> -isnot <type reference>`

Пример

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -isnot $b.GetType()
True
PS> $b -isnot [int]
True
```

## <a name="see-also"></a>СМ. ТАКЖЕ

- [about_Operators](about_Operators.md)
- [about_Regular_Expressions](about_Regular_Expressions.md)
- [about_Wildcards](about_Wildcards.md)
- [Compare-Object](xref:Microsoft.PowerShell.Utility.Compare-Object)
- [ForEach-Object](xref:Microsoft.PowerShell.Core.ForEach-Object)
- [Where-Object](xref:Microsoft.PowerShell.Core.Where-Object)
