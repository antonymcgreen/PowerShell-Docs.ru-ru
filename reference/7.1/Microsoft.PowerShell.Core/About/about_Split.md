---
description: Объясняет, как использовать оператор Split для разделения одной или нескольких строк на подстроки.
keywords: powershell,командлет
Locale: en-US
ms.date: 03/24/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_split?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Split
ms.openlocfilehash: 3ea193fe0706e2a15d9f7ef64f37e29a19186648
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93230897"
---
# <a name="about-split"></a>Сведения о разбиении

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
Объясняет, как использовать оператор Split для разделения одной или нескольких строк на подстроки.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Оператор Split разделяет одну или несколько строк на подстроки. Вы можете изменить следующие элементы операции разбиения:

- Разделитель. По умолчанию используется пробел, но можно указать символы, строки, шаблоны или блоки скриптов, указывающие разделитель. Оператор Split в PowerShell использует регулярное выражение в разделителе, а не простой символ.
- Максимальное число подстрок. По умолчанию возвращаются все подстроки. Если указать число, меньшее числа подстрок, оставшиеся подстроки объединяются в последнюю подстроку.
- Параметры, определяющие условия, при которых будет сопоставляться разделитель, например SimpleMatch и Multiline.

## <a name="syntax"></a>SYNTAX

На следующей схеме показан синтаксис оператора-split.

Имена параметров не отображаются в команде. Включайте только значения параметров. Значения должны присутствовать в порядке, указанном в схеме синтаксиса.

```
-Split <String>
-Split (<String[]>)
<String> -Split <Delimiter>[,<Max-substrings>[,"<Options>"]]
<String> -Split {<ScriptBlock>} [,<Max-substrings>]
```

Можно заменить `-iSplit` или `-cSplit` для `-split` в любой инструкции двоичного разделения (оператор разбиения, включающий разделитель или блок сценария). В `-iSplit` `-split` операторах и регистр не учитывается. В `-cSplit` операторе учитывается регистр, что означает, что при применении правил разделителей учитывается регистр.

## <a name="parameters"></a>PARAMETERS

### <a name="string-or-string"></a>\<String\> или \<String[]\>

Указывает одну или несколько строк для разбиения. При отправке нескольких строк все строки разбиваются с помощью одних и тех же правил разделителей.

Пример

```
-split "red yellow blue green"
red
yellow
blue
green
```

### \<Delimiter\>

Символы, которые обозначают конец подстроки. По умолчанию разделителем являются пробелы, включая пробелы и непечатаемые символы, например символ новой строки ( \` n) и знак табуляции ( \` t). При разбиении строк разделитель опускается из всех подстрок. Пример

```
"Lastname:FirstName:Address" -split ":"
Lastname
FirstName
Address
```

По умолчанию разделитель в результатах опускается. Чтобы сохранить все или часть разделителя, заключите в круглые скобки часть, которую необходимо сохранить.
Если \<Max-substrings\> параметр добавлен, это имеет приоритет, если команда разделяет коллекцию. Если включить разделитель как часть выходных данных, команда возвращает разделитель в составе выходных данных. Однако разделение строки для возврата разделителя в качестве части выходных данных не учитывается в качестве разбиения.

Примеры:

```
"Lastname:FirstName:Address" -split "(:)"
Lastname
:
FirstName
:
Address

"Lastname/:/FirstName/:/Address" -split "/(:)/"
Lastname
:
FirstName
:
Address
```

В следующем примере \<Max-substrings\> значение равно 3. Это приводит к трем разбиениям строковых значений, но всего за пять строк в результирующем выводе; разделитель включается после разбиения до тех пор, пока не будет достигнуто максимально допустимое число из трех подстрок. Дополнительные разделители в конечной подстроке становятся частью подстроки.

```powershell
'Chocolate-Vanilla-Strawberry-Blueberry' -split '(-)', 3
```

```Output
Chocolate
-
Vanilla
-
Strawberry-Blueberry
```

### \<Max-substrings\>

Указывает максимальное число разбиений строки. По умолчанию используются все подстроки, разделенные разделителем. Если подстроки больше, они объединяются с конечной подстрокой. Если число подстрок меньше, возвращаются все подстроки. Значение 0 возвращает все подстроки. Отрицательные значения возвращают количество подстрок, запрошенных начиная с конца входной строки.

> [!NOTE]
> В PowerShell 7 добавлена поддержка отрицательных значений.

**Max-substring** не задает максимальное количество возвращаемых объектов. Его значение равно максимальному количеству разделений строки.
Если в оператор отправляется более одной строки (массив строк) `-split` , то ограничение **Max-substring** применяется к каждой строке отдельно.

Пример

```powershell
$c = "Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune"
$c -split ",", 5
```

```Output
Mercury
Venus
Earth
Mars
Jupiter,Saturn,Uranus,Neptune
```

```powershell
$c = "Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune"
$c -split ",", -5
```

```Output
Mercury,Venus,Earth,Mars
Jupiter
Saturn
Uranus
Neptune
```

### \<ScriptBlock\>

Выражение, задающее правила для применения разделителя. Выражение должно иметь значение $true или $false. Заключите блок скрипта в фигурные скобки.

Пример

```powershell
$c = "Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune"
$c -split {$_ -eq "e" -or $_ -eq "p"}
```

```Output
M
rcury,V
nus,
arth,Mars,Ju
it
r,Saturn,Uranus,N

tun
```

### \<Options\>

Заключите имя параметра в кавычки. Параметры допустимы только в том случае, если \<Max-substrings\> параметр используется в инструкции.

Для параметра options используется следующий синтаксис:

```
"SimpleMatch [,IgnoreCase]"

"[RegexMatch] [,IgnoreCase] [,CultureInvariant]
[,IgnorePatternWhitespace] [,ExplicitCapture]
[,Singleline | ,Multiline]"
```

Параметры SimpleMatch:

- **SimpleMatch** : Используйте простое сравнение строк при вычислении разделителя. Не может использоваться с Режексматч.
- **IgnoreCase** : принудительное сопоставление без учета регистра, даже если указан оператор-ксплит.

Параметры Режексматч:

- **Режексматч** : используйте сопоставление регулярных выражений для вычисления разделителя. Это поведение по умолчанию. Не может использоваться с SimpleMatch.
- **IgnoreCase** : принудительное сопоставление без учета регистра, даже если указан оператор-ксплит.
- **CultureInvariant** : игнорирует культурные различия в языке, если оценка разделитель. Допустимо только с Режексматч.
- **IgnorePatternWhitespace** : игнорирует неэкранированные пробелы и комментарии, помеченные знаком решетки (#). Допустимо только с Режексматч.
- **Многострочный** : многострочный режим заставляет `^` и `$` сопоставлять начальную конец каждой строки, а не начало и конец входной строки.
- **SingleLine** : режим SingleLine обрабатывает входную строку как *SingleLine*.
  Он заставляет `.` символ соответствовать каждому символу (включая символы новой строки) вместо того, чтобы сопоставлять каждый символ, кроме символа новой строки `\n` .
- **ExplicitCapture** : игнорирует неименованные группы соответствия, чтобы в списке результатов возвращались только явные группы записи. Допустимо только с Режексматч.

## <a name="unary-and-binary-split-operators"></a>ОПЕРАТОРЫ УНАРного и БИНАРного разделения

Оператор унарного разбиения ( `-split <string>` ) имеет более высокий приоритет, чем запятая. В результате, если отправить разделенный запятыми список строк в оператор унарного разбиения, то разбиение выполняется только на первую строку (перед первой запятой).

Чтобы разделить более одной строки, используйте один из следующих шаблонов:

- Использование оператора двоичного разделения ( \<string[]\> -Split \<delimiter\> )
- Заключите все строки в круглые скобки
- Сохранить строки в переменной, а затем отправить переменную оператору Split

Рассмотрим следующий пример.

```
PS> -split "1 2", "a b"
1
2
a b
```

```
PS> "1 2", "a b" -split " "
1
2
a
b
```

```
PS> -split ("1 2", "a b")
1
2
a
b
```

```
PS> $a = "1 2", "a b"
PS> -split $a
1
2
a
b
```

## <a name="examples"></a>Примеры

Следующая инструкция разделяет строку на пробел.

```powershell
-split "Windows PowerShell 2.0`nWindows PowerShell with remoting"
```

```Output

Windows
PowerShell
2.0
Windows
PowerShell
with
remoting
```

Следующая инструкция разделяет строку на любую запятую.

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split ','
```

```Output
Mercury
Venus
Earth
Mars
Jupiter
Saturn
Uranus
Neptune
```

Следующая инструкция разделяет строку на шаблоне "ER".

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split 'er'
```

```Output
M
cury,Venus,Earth,Mars,Jupit
,Saturn,Uranus,Neptune
```

Следующая инструкция выполняет разбиение с учетом регистра по букве "N".

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -cSplit 'N'
```

```Output
Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,
eptune
```

Следующая инструкция разделяет строку на "e" и "t".

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split '[et]'
```

```Output
M
rcury,V
nus,
ar
h,Mars,Jupi

r,Sa
urn,Uranus,N
p
un
```

Следующая инструкция разделяет строку на "e" и "r", но ограничивает результирующие подстроки до шести подстрок.

```powershell
"Mercury,Venus,Earth,Mars,Jupiter,Saturn,Uranus,Neptune" -split '[er]', 6
```

```Output
M

cu
y,V
nus,
arth,Mars,Jupiter,Saturn,Uranus,Neptune
```

Следующая инструкция разделяет строку на три подстроки.

```powershell
"a,b,c,d,e,f,g,h" -split ",", 3
```

```Output
a
b
c,d,e,f,g,h
```

Следующая инструкция разделяет строку на три подстроки, начиная с конца строки.

```powershell
"a,b,c,d,e,f,g,h" -split ",", -3
```

```Output
a,b,c,d,e,f
g
h
```

Следующая инструкция разделяет две строки на три подстроки.
(Ограничение применяется к каждой строке независимо друг от друга.)

```powershell
"a,b,c,d", "e,f,g,h" -split ",", 3
```

```Output
a
b
c,d
e
f
g,h
```

Следующая инструкция разделяет каждую строку в строке Here в первой цифре. Он использует многострочный параметр для распознавания начала каждой строки и строки.

0 представляет значение "вернуть все" для параметра max-substring. Параметры, например Multiline, можно использовать, только если указано значение Max-substring.

```powershell
$a = @'
1The first line.
2The second line.
3The third of three lines.
'@
$a -split "^\d", 0, "multiline"
```

```Output

The first line.

The second line.

The third of three lines.
```

Следующая инструкция использует символ обратной косой черты для экранирования разделителя с точкой (.).

При использовании значения по умолчанию Режексматч точка, заключенная в кавычки ("."), интерпретируется так, чтобы соответствовать любому символу, кроме символа новой строки. В результате инструкция Split возвращает пустую строку для каждого символа, кроме новой строки.

```powershell
"This.is.a.test" -split "\."
```

```Output
This
is
a
test
```

В следующей инструкции используется параметр SimpleMatch для направления оператора-split на интерпретацию разделителя с точкой (.) буквально.

0 представляет значение "вернуть все" для параметра max-substring. Параметры, такие как SimpleMatch, можно использовать, только если указано значение Max-substring.

```powershell
"This.is.a.test" -split ".", 0, "simplematch"
```

```Output
This
is
a
test
```

Следующая инструкция разделяет строку на один из двух разделителей в зависимости от значения переменной.

```powershell
$i = 1
$c = "LastName, FirstName; Address, City, State, Zip"
$c -split $(if ($i -lt 1) {","} else {";"})
```

```Output
LastName, FirstName
 Address, City, State, Zip
```

## <a name="see-also"></a>СМ. ТАКЖЕ

[Split-Path](xref:Microsoft.PowerShell.Management.Split-Path)

[about_Operators](about_Operators.md)

[about_Comparison_Operators](about_Comparison_Operators.md)

[about_Join](about_Join.md)

