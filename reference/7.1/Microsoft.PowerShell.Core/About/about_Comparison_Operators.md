---
description: Описывает операторы, которые сравнивают значения в PowerShell.
Locale: en-US
ms.date: 01/20/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comparison_Operators
ms.openlocfilehash: aa2d2d09fe0eb35c42c5ee84083c8ee29354cf8f
ms.sourcegitcommit: 77f6225ab0c8ea9faa1fe46b2ea15c178ec170e3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100500182"
---
# <a name="about-comparison-operators"></a>Сведения об операторах сравнения

## <a name="short-description"></a>Краткое описание

Операторы сравнения в PowerShell могут либо сравнивать два значения, либо фильтровать элементы коллекции по входному значению.

## <a name="long-description"></a>Подробное описание

Операторы сравнения позволяют сравнивать значения или находить значения, соответствующие указанным шаблонам. PowerShell содержит следующие операторы сравнения:

|    Тип     |   Оператор   |              Тест сравнения              |
| ----------- | ------------ | ----------------------------------------- |
| Равенство    | -eq          | equals                                    |
|             | -ne          | не равно                                |
|             | -gt          | больше чем                              |
|             | -ge          | больше или равно                     |
|             | -lt          | меньше чем                                 |
|             | -le          | меньше или равно                        |
| Matching    | -like        | строка соответствует шаблону шаблона           |
|             | -notlike     | строка не соответствует шаблону шаблона    |
|             | -match       | строка соответствует шаблону регулярного выражения              |
|             | -notmatch    | строка не соответствует шаблону регулярного выражения       |
| Замена | -Replace     | заменяет строки, соответствующие шаблону регулярного выражения |
| Containment | -contains    | Коллекция содержит значение               |
|             | -notcontains | Коллекция не содержит значение       |
|             | -in          | значение находится в коллекции                  |
|             | -notin       | значение не находится в коллекции              |
| Type        | — имеет          | Оба объекта имеют одинаковый тип            |
|             | -IsNot       | объекты имеют разные типы         |

## <a name="common-features"></a>Общие возможности

По умолчанию все операторы сравнения не учитывают регистр. Чтобы выполнить оператор сравнения с учетом регистра, добавьте `c` после `-` . Например, `-ceq` — это версия с учетом регистра `-eq` . Чтобы сделать явный учет регистра нечувствительным, добавьте `i` перед `-` . Например, `-ieq` является явной версией без учета регистра `-eq` .

Если входные данные оператора являются скалярным значением, оператор возвращает **логическое** значение. Если входные данные являются коллекцией, оператор возвращает элементы коллекции, соответствующие правому значению выражения.
Если в коллекции нет совпадений, операторы сравнения возвращают пустой массив. Пример:

```powershell
$a = (1, 2 -eq 3)
$a.GetType().Name
$a.Count
```

```output
Object[]
0
```

Существует несколько исключений:

- Операторы включения и типа всегда возвращают **логическое** значение.
- `-replace`Оператор возвращает результат замены
- `-match`Операторы и `-notmatch` также заполняют `$Matches` автоматическую переменную

## <a name="equality-operators"></a>Операторы равенства

### <a name="-eq-and--ne"></a>-eq и -ne

Если левая часть является скалярной, `-eq` возвращает **значение true** , если правая часть является точным совпадением, в противном случае `-eq` возвращает **значение false**. `-ne` выполняет противоположный; При совпадении обоих сторон возвращается **значение false** . в противном случае `-ne` возвращает значение true.

Пример:

```powershell
2 -eq 2                 # Output: True
2 -eq 3                 # Output: False
"abc" -eq "abc"         # Output: True
"abc" -eq "abc", "def"  # Output: False
"abc" -ne "def"         # Output: True
"abc" -ne "abc"         # Output: False
"abc" -ne "abc", "def"  # Output: True
```

Если левая часть является коллекцией, `-eq` возвращает элементы, соответствующие правой части, и `-ne` отфильтровывает их.

Пример:

```powershell
1,2,3 -eq 2             # Output: 2
"abc", "def" -eq "abc"  # Output: abc
"abc", "def" -ne "abc"  # Output: def
```

Эти операторы обрабатывают все элементы коллекции. Пример:

```powershell
"zzz", "def", "zzz" -eq "zzz"
```

```output
zzz
zzz
```

Операторы равенства принимают любые два объекта, а не только скаляр или коллекция.
Однако результат сравнения не гарантируется для конечного пользователя.
В следующем примере показана эта ошибка.

```powershell
class MyFileInfoSet {
    [String]$File
    [Int64]$Size
}
$a = [MyFileInfoSet]@{File = "C:\Windows\explorer.exe"; Size = 4651032}
$b = [MyFileInfoSet]@{File = "C:\Windows\explorer.exe"; Size = 4651032}
$a -eq $b
```

```Output
False
```

В этом примере мы создали два объекта с одинаковыми свойствами. Однако результат проверки равенства имеет **значение false** , так как они являются разными объектами. Чтобы создать сравнимые классы, необходимо реализовать [System. IEquatable \<T> ][2] в своем классе. В следующем примере демонстрируется частичная реализация класса **мифилеинфосет** , который реализует [System. IEquatable \<T>][2] и имеет два свойства: **File** и **size**. `Equals()`Метод возвращает значение true, если свойства File и size двух объектов **мифилеинфосет** одинаковы.

```powershell
class MyFileInfoSet : System.IEquatable[Object] {
    [String]$File
    [Int64]$Size

    [bool] Equals([Object] $obj) {
        return ($this.File -eq $obj.File) -and ($this.Size -eq $obj.Size)
    }
}
$a = [MyFileInfoSet]@{File = "C:\Windows\explorer.exe"; Size = 4651032}
$b = [MyFileInfoSet]@{File = "C:\Windows\explorer.exe"; Size = 4651032}
$a -eq $b
```

```Output
True
```

Заметным примером сравнения произвольных объектов является определение того, равны ли они значению NULL. Но если необходимо определить, является ли переменная `$null` , необходимо разместить `$null` в левой части оператора равенства. Размещение с правой стороны не делает то, что вы ждете.

Например, пусть `$a` массив содержит элементы со значением NULL:

```powershell
$a = 1, 2, $null, 4, $null, 6
```

Следующие тесты `$a` не имеют значение null.

```powershell
$null -ne $a
```

```output
False
```

Однако в следующем примере фильтрами определенными все элементы NULL из `$a` :

```powershell
$a -ne $null # Output: 1, 2, 4, 6
```

```output
1
2
4
6
```

### <a name="-gt--ge--lt-and--le"></a>-gt,-GE,-lt и-Le

`-gt`, `-ge` , `-lt` и `-le` ведут себя точно так же. Если обе стороны скалярны, они возвращают **значение true** или **false** в зависимости от того, как сравниваются две стороны:

| Оператор | Возвращает значение true, если...                   |
| -------- | -------------------------------------- |
| -gt      | Левая часть больше          |
| -ge      | Левая часть больше или равна |
| -lt      | Левый край меньше          |
| -le      | Левая часть меньше или равна |

В следующих примерах все инструкции возвращают значение true.

```powershell
8 -gt 6  # Output: True
8 -ge 8  # Output: True
6 -lt 8  # Output: True
8 -le 8  # Output: True
```

> [!NOTE]
> В большинстве языков программирования оператор «больше» имеет значение `>` . В PowerShell этот символ используется для перенаправления. Дополнительные сведения см. в разделе [about_Redirection][3].

Если левая часть является коллекцией, эти операторы сравнивают каждый элемент коллекции с правой стороны. В зависимости от логики они либо сохраняют, либо отклоняют элемент.

Пример:

```powershell
$a=5, 6, 7, 8, 9

Write-Output "Test collection:"
$a

Write-Output "`nMembers greater than 7"
$a -gt 7

Write-Output "`nMembers greater than or equal to 7"
$a -ge 7

Write-Output "`nMembers smaller than 7"
$a -lt 7

Write-Output "`nMembers smaller than or equal to 7"
$a -le 7
```

```output
Test collection:
5
6
7
8
9

Members greater than 7
8
9

Members greater than or equal to 7
7
8
9

Members smaller than 7
5
6

Members smaller than or equal to 7
5
6
7
```

Эти операторы работают с любым классом, реализующим [System. IComparable][1].

Примеры:

```powershell
# Date comparison
[DateTime]'2001-11-12' -lt [DateTime]'2020-08-01' # True

# Sorting order comparison
'a' -lt 'z'           # True; 'a' comes before 'z'
'macOS' -ilt 'MacOS'  # False
'MacOS' -ilt 'macOS'  # False
'macOS' -clt 'MacOS'  # True; 'm' comes before 'M'
```

В следующем примере показано, что на клавиатуре QWERTY для американского типа «а» нет символа, который сортируется после «a». Он передает набор, содержащий все символы `-gt` оператора, для сравнения их с "a". Выходные данные представляют собой пустой массив.

```powershell
$a=' ','`','~','!','@','#','$','%','^','&','*','(',')','_','+','-','=',
   '{','}','[',']',':',';','"','''','\','|','/','?','.','>',',','<'
$a -gt 'a'
# Output: Nothing
```

Если две стороны операторов не являются достаточно сравнимыми, эти операторы вызывают неустранимую ошибку.

## <a name="matching-operators"></a>Соответствующие операторы

Операторы сопоставления ( `-like` ,, `-notlike` `-match` и `-notmatch` ) находят элементы, которые соответствуют или не соответствуют указанному шаблону. Шаблон для `-like` и `-notlike` является выражением-шаблоном (содержащим `*` , `?` и `[ ]` ), а `-match` также `-notmatch` принимает регулярное выражение (Regex).

Синтаксис:

```
<string[]> -like    <wildcard-expression>
<string[]> -notlike <wildcard-expression>
<string[]> -match    <regular-expression>
<string[]> -notmatch <regular-expression>
```

Если входные данные этих операторов являются скалярным значением, они возвращают **логическое** значение. Если входные данные являются коллекцией значений, операторы возвращают все совпадающие элементы. Если в коллекции нет совпадений, операторы возвращают пустой массив.

### <a name="-like-and--notlike"></a>-Like и-notlike

`-like` и `-notlike` ведут себя аналогично `-eq` и `-ne` , но правая часть может быть строкой, содержащей [подстановочные знаки](about_Wildcards.md).

Пример:

```powershell
"PowerShell" -like    "*shell"           # Output: True
"PowerShell" -notlike "*shell"           # Output: False
"PowerShell" -like    "Power?hell"       # Output: True
"PowerShell" -notlike "Power?hell"       # Output: False
"PowerShell" -like    "Power[p-w]hell"   # Output: True
"PowerShell" -notlike "Power[p-w]hell"   # Output: False

"PowerShell", "Server" -like "*shell"    # Output: PowerShell
"PowerShell", "Server" -notlike "*shell" # Output: Server
```

### <a name="-match-and--notmatch"></a>-Match и-notmatch

`-match` и `-notmatch` используют регулярные выражения для поиска шаблона в левой части значений. Регулярные выражения могут сопоставлять сложные шаблоны, такие как адреса электронной почты, пути UNC или отформатированные номера телефонов. Правая строка должна соответствовать правилам [регулярных выражений](about_Regular_Expressions.md) .

Скалярные примеры:

```powershell
# Partial match test, showing how differently -match and -like behave
"PowerShell" -match 'shell'        # Output: True
"PowerShell" -like  'shell'        # Output: False

# Regex syntax test
"PowerShell" -match    '^Power\w+' # Output: True
'bag'        -notmatch 'b[iou]g'   # Output: True
```

Если входные данные являются коллекцией, операторы возвращают соответствующие члены этой коллекции.

Примеры коллекций:

```powershell
"PowerShell", "Super PowerShell", "Power's hell" -match '^Power\w+'
# Output: PowerShell

"Rhell", "Chell", "Mel", "Smell", "Shell" -match "hell"
# Output: Rhell, Chell, Shell

"Bag", "Beg", "Big", "Bog", "Bug"  -match 'b[iou]g'
#Output: Big, Bog, Bug

"Bag", "Beg", "Big", "Bog", "Bug"  -notmatch 'b[iou]g'
#Output: Bag, Beg
```

`-match` и `-notmatch` поддерживают регулярные выражения группы записи. При каждом запуске они перезапишут `$Matches` автоматическую переменную. Если `<input>` является коллекцией, `$Matches` переменная имеет значение `$null` . `$Matches` — Это **хэш-таблица** , которая всегда содержит ключ с именем "0", в котором сохраняется все совпадение. Если регулярное выражение содержит группы захвата, `$Matches` содержит дополнительные ключи для каждой группы.

Пример:

```powershell
$string = 'The last logged on user was CONTOSO\jsmith'
$string -match 'was (?<domain>.+)\\(?<user>.+)'

$Matches

Write-Output "`nDomain name:"
$Matches.domain

Write-Output "`nUser name:"
$Matches.user
```

```output
True

Name                           Value
----                           -----
domain                         CONTOSO
user                           jsmith
0                              was CONTOSO\jsmith

Domain name:
CONTOSO

User name:
jsmith
```

Дополнительные сведения см. в разделе [about_Regular_Expressions](about_Regular_Expressions.md).

## <a name="replacement-operator"></a>Оператор замены

### <a name="replacement-with-regular-expressions"></a>Замена с помощью регулярных выражений

Например `-match` , `-replace` оператор использует регулярные выражения для поиска указанного шаблона. Но в отличие от `-match` он заменяет совпадения другим указанным значением.

Синтаксис:

```
<input> -replace <regular-expression>, <substitute>
```

Оператор заменяет все или часть значения указанным значением с помощью регулярных выражений. Оператор можно использовать для многих административных задач, таких как переименование файлов. Например, следующая команда изменяет расширения имен файлов всех `.txt` файлов на `.log` :

```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.name -replace '\.txt$','.log' }
```

По умолчанию `-replace` оператор не учитывает регистр. Чтобы сделать его чувствительным к регистру, используйте `-creplace` . Чтобы явно сделать регистр без учета регистра, используйте `-ireplace` .

Примеры:

```powershell
"book" -ireplace "B", "C" # Case insensitive
"book" -creplace "B", "C" # Case-sensitive; hence, nothing to replace
```

```Output
Cook
book
```

### <a name="regular-expressions-substitutions"></a>Подстановки регулярных выражений

Можно также использовать регулярные выражения для динамической замены текста с помощью захваченных групп и подстановок. На группы записи можно ссылаться в `<substitute>` строке, используя знак доллара ( `$` ) перед идентификатором группы.

В следующем примере `-replace` оператор принимает имя пользователя в формате `DomainName\Username` и преобразует его в `Username@DomainName` Формат:

```powershell
$SearchExp = '^(?<DomainName>[\w-.]+)\\(?<Username>[\w-.]+)$'
$ReplaceExp = '${Username}@${DomainName}'

'Contoso.local\John.Doe' -replace $SearchExp,$ReplaceExp
```

```output
John.Doe@Contoso.local
```

> [!WARNING]
> Этот `$` символ имеет синтатик роли в PowerShell и в регулярных выражениях:
>
> - В PowerShell между двойными кавычками они обозначают переменные и действуют как операторы части выражения.
> - В строках поиска регулярных выражений это означает конец строки.
> - В строках подстановки Regex он означает захваченные группы. Не забудьте поместить регулярные выражения в одинарные кавычки или вставить `` ` `` символ обратной черты () перед ними.

Пример:

```powershell
$1 = 'Goodbye'

'Hello World' -replace '(\w+) \w+', "$1 Universe"
# Output: Goodbye Universe

'Hello World' -replace '(\w+) \w+', '$1 Universe'
# Output: Hello Universe
```

`$$` в регулярном выражении обозначает литерал `$` . `$$`В строке подстановки, чтобы включить литерал `$` в результирующую замену. Пример:

```powershell
'5.72' -replace '(.+)', '$ $1' # Output: $ 5.72
'5.72' -replace '(.+)', '$$$1' # Output: $5.72
'5.72' -replace '(.+)', '$$1'  # Output: $1
```

Дополнительные сведения см. в разделе [about_Regular_Expressions](about_Regular_Expressions.md) и [подстановки в регулярных выражениях][4].

### <a name="substituting-in-a-collection"></a>Подстановка в коллекции

Если `<input>` `-replace` оператор to является коллекцией, PowerShell применяет замену к каждому значению в коллекции. Пример:

```powershell
"B1","B2","B3","B4","B5" -replace "B", 'a'
a1
a2
a3
a4
a5
```

### <a name="replacement-with-a-script-block"></a>Замена блоком сценария

В PowerShell 6 и более поздних версиях `-replace` оператор также принимает блок сценария, который выполняет замену. Блок скрипта выполняется один раз для каждого совпадения.

Синтаксис:

```powershell
<String> -replace <regular-expression>, {<Script-block>}
```

В блоке скрипта используйте `$_` автоматическую переменную для доступа к заменяемому входному тексту и другим полезным сведениям. Тип класса этой переменной — [System. Text. RegularExpressions. Match][2].

В следующем примере каждая последовательность из трех цифр заменяется эквивалентными символами. Блок скрипта выполняется для каждого набора из трех цифр, которые необходимо заменить.

```powershell
"072101108108111" -replace "\d{3}", {return [char][int]$_.Value}
```

```output
Hello
```

## <a name="containment-operators"></a>Операторы вложения

Операторы вложения ( `-contains` , `-notcontains` , `-in` и `-notin` ) похожи на операторы равенства, за исключением того, что они всегда возвращают **логическое** значение, даже если входные данные являются коллекцией. Эти операторы прекращают сравнение, как только они обнаруживают первое совпадение, в то время как операторы равенства оценивают все входные элементы. В очень больших коллекциях эти операторы возвращают более быстрый результат, чем операторы равенства.

Синтаксис:

```
<Collection> -contains <Test-object>
<Collection> -notcontains <Test-object>
<Test-object> -in <Collection>
<Test-object> -notin <Collection>
```

### <a name="-contains-and--notcontains"></a>-Contains и-notcontains

Эти операторы определяют, включает ли набор определенный элемент. `-contains` Возвращает значение true, если правая часть (тестовый объект) соответствует одному из элементов в наборе. `-notcontains` Вместо этого возвращает значение false. Если объект теста является коллекцией, эти операторы используют равенство ссылок, т. е. они проверяют, является ли один из элементов набора одним и тем же экземпляром тестового объекта.

Примеры:

```powershell
"abc", "def" -contains "def"                  # Output: True
"abc", "def" -notcontains "def"               # Output: False
"Windows", "PowerShell" -contains "Shell"     # Output: False
"Windows", "PowerShell" -notcontains "Shell"  # Output: True
"abc", "def", "ghi" -contains "abc", "def"    # Output: False
"abc", "def", "ghi" -notcontains "abc", "def" # Output: True
```

Более сложные примеры:

```powershell
$DomainServers = "ContosoDC1","ContosoDC2","ContosoFileServer","ContosoDNS",
                 "ContosoDHCP","ContosoWSUS"
$thisComputer  = "ContosoDC2"

$DomainServers -contains $thisComputer
# Output: True

$a = "abc", "def"
"abc", "def", "ghi" -contains $a # Output: False
$a, "ghi" -contains $a           # Output: True
```

### <a name="-in-and--notin"></a>-in и-notin

`-in` `notin` Операторы and были введены в PowerShell 3 в качестве синтаксических обратных `contains` `-notcontain` операторов и. `-in` Возвращает **значение true** , если левая `<test-object>` часть соответствует одному из элементов в наборе. `-notin` Вместо этого возвращает **значение false** . Если тестовый объект является набором, эти операторы используют равенство ссылок для проверки того, является ли один из элементов набора одним и тем же экземпляром тестового объекта.

Следующие примеры выполняют те же действия, что и примеры для `-contain` и `-notcontain` Do, но они записываются с помощью `-in` и `-notin` .

```powershell
"def" -in "abc", "def"                  # Output: True
"def" -notin "abc", "def"               # Output: False
"Shell" -in "Windows", "PowerShell"     # Output: False
"Shell" -notin "Windows", "PowerShell"  # Output: True
"abc", "def" -in "abc", "def", "ghi"    # Output: False
"abc", "def" -notin "abc", "def", "ghi" # Output: True
```

Более сложные примеры:

```powershell
$DomainServers = "ContosoDC1","ContosoDC2","ContosoFileServer","ContosoDNS",
                 "ContosoDHCP","ContosoWSUS"
$thisComputer  = "ContosoDC2"

$thisComputer -in $DomainServers
# Output: True

$a = "abc", "def"
$a -in "abc", "def", "ghi" # Output: False
$a -in $a, "ghi"           # Output: True
```

## <a name="type-comparison"></a>Сравнение типов

Операторы сравнения типов ( `-is` и `-isnot` ) используются для определения того, является ли объект конкретным типом.

Синтаксис:

```powershell
<object> -is <type-reference>
<object> -isnot <type-reference>
```

Пример:

```powershell
$a = 1
$b = "1"
$a -is [int]           # Output: True
$a -is $b.GetType()    # Output: False
$b -isnot [int]        # Output: True
$a -isnot $b.GetType() # Output: True
```

## <a name="see-also"></a>СМ. ТАКЖЕ

- [about_Operators](about_Operators.md)
- [about_Regular_Expressions](about_Regular_Expressions.md)
- [about_Wildcards](about_Wildcards.md)
- [Compare-Object](xref:Microsoft.PowerShell.Utility.Compare-Object)
- [ForEach-Object](xref:Microsoft.PowerShell.Core.ForEach-Object)
- [Where-Object](xref:Microsoft.PowerShell.Core.Where-Object)

[1]: /dotnet/api/system.icomparable
[2]: /dotnet/api/system.iequatable-1
[3]: /dotnet/api/system.text.regularexpressions.match
[4]: about_Redirection.md#potential-confusion-with-comparison-operators
[5]: /dotnet/standard/base-types/substitutions-in-regular-expressions
